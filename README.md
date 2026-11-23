# Networking Lab Series — Lab 1: Securing a SOHO Network from Scratch

Kicking off my hands-on Cisco Packet Tracer lab series! For Lab 1 ("The SOHO Ghost Office"), I designed, addressed, and hardened a Small Office / Home Office network from a blank slate—including a mid-project security compliance twist.

🔧 What I Built & Configured:
• VLSM IPv4 Subnetting: Carved 192.168.10.0/24 into four equal /26 subnets (255.255.255.192, 62 usable hosts each) to eliminate IP wastage and reserve clean blocks for future growth.
• Topology & Gateway Setup: Wired a Cisco router (SOHO-R1), Layer 2 switch (SOHO-S1), and 3 workstations (PC-1 to PC-3), assigning .1 as the default gateway and bringing the LAN interface online.
• Baseline Device Hardening: Configured unique hostnames, hashed enable secret credentials, and a legal banner motd warning prior to login.
• Security Twist — SSHv2 Only: Replaced cleartext Telnet with SSH v2 by configuring a local domain name, generating 2048-bit RSA keys, creating local admin credentials, and locking line vty interfaces strictly to transport input ssh.

✅ Verification:
Tested remote access from PC-1 (192.168.10.2) via ssh -l admin 192.168.10.1—confirming the MOTD banner display, encrypted session authentication, and full privileged access (SOHO-R1#).
