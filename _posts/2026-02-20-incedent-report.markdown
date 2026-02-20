---
layout: post
title: "2026-IVN-01"
date: 2026-02-20
---
Incident Report ID:<a href="https://github.com/brandonelswick01/SOCPortfolio/blob/main/2026-IVN-01.md"></a>

Classification: High-Priority / Unauthorized Access Investigation

Status: Concluded / Reported to CISA

Investigator: Brandon Elswick / brandonelswick01

During independent research using Shodan, I identified a compromised Ivanti Connect Secure Gateway belonging to a major telecommunications infrastructure (China Telecom). The investigation uncovered that the gateway was being utilized as a Command & Control (C2) staging point for a global espionage campaign. Key findings include the identification of unauthorized geographic "Authentication Realms" (categorized by continent) and the presence of active kernel-level command suppression, consistent with known state-sponsored malware families (e.g., SPAWN/BRUSHFIRE). This research demonstrates the critical need for edge-device patchingand proactive threat hunting in entereprise enviroments..

Target IP: 133.45.x.x

Active Identification:

curl -v 113.45.[x].x nc -v 113.45.[x].x, nmap -sV 443 113.45.[x].x -O -A, nmap -p 80 113.45.[x].x

Forensic Verification: Intital Access: Explotation of Remote Services (T1133) - Leveraging the Ivanti Vulnerability

During a passive scan of servers on Shodan, I identified a target IP address. I executed the standard command, curl -v 113.45.x.x, to scrape random data but did not retrieve any useful information. Unsatisfied with the results, I opted to investigate further by entering the IP and port 443 into my web browser. To my surprise, JavaScript content loaded. Initially, it appeared to be standard; however, I soon noticed a comment that stated, "// Remember the last selected auth realm for 30 days."

javascript

function setLastRealm(value) {
  const expirationDate = new Date();
  expirationDate.setDate(expirationDate.getDate() + 30);

  const ivsHex = getCookieValue("DSIVS");

  document.cookie = `lastRealm${ivsHex}=${encodeURIComponent(value)}; expires=${expirationDate.toUTCString()}; secure`;
}
This discovery led me to suspect that I might have encountered an InfoStealer. As a result, I decided to pivot my focus to port 22, which was surprisingly open. The default root password remained unchanged, allowing me to log in instantly. Once logged in, I executed the command pwd to determine my current directory and then used ls to check for any accessible files or folders. Initially, I found none, so I navigated to the / directory and subsequently to /usr/share, where I ran the ls command again and discovered several directories. These directories were listed as: alsa, openh323, pwlib, snmp, terminfo, adn zoneinfo. When I ran the cd command into the folder label "zoneifo" I was imediatly disconnected byt the remote host.

Persistence: External Remote Services (T1133) - The ability to connect 10+ times back-to-back

I soon realized on after logging back in that I was able to navigate back to the files I previously have mentioned above. Once there, this time I called for ls -la zoneinfo This allowed me to few a few subdirectories labeled: Africa, America, Asia, Canada, and Alantic. I was diconnected again and again and again. To test the enviorment response to geographical origin, traffic was routed through a PRC-based proxy. This resulted in a shift in adversary TTPs: while non-RPC traffic was frequently disconnected.

Defense Evasion: Rootkit (T1014) - The "command suppression" behavior Discovery: File and Directory (T1083) -
