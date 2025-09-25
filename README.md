# EIGRP-dynamic-routing
EIGRP dynamic routing on three routers so that all LANs (192.168.1.0, 172.16.0.0, 192.168.2.0) can communicate with each other without manually adding static routes.

The lab uses three routers connected in a triangle. Each router connects to a separate LAN via a switch:-

- -R1 → 192.168.1.0/24 (PC0, PC1)
- -R2 → 172.16.0.0/24 (PC2, PC3)
- -R3 → 192.168.2.0/24 (PC4, PC5)
- - Inter-router links: 10.0.0.0/30 and 20.0.0.0/30

Commands configure EIGRP on the routers:-

- #router eigrp 100
- #network 192.168.1.0 0.0.0.255
- #network 10.0.0.0 0.0.0.3
- #no auto-summary

no auto-summary → avoids classful routing}

Command to Verify that EIGRP is working:-

Use these commands:
-show ip eigrp neighbors → shows established neighbor relationships
-show ip route → check if EIGRP routes appear with D (for EIGRP)
-ping between PCs in different LANs (e.g., PC0 → PC4) to confirm connectivity

The expected result of the lab:-

-All PCs from different networks should communicate successfully. For example:
-PC0 (192.168.1.10) should ping PC5 (192.168.2.20)
-PC2 (172.16.0.10) should ping PC1 (192.168.1.20)
-The routing table on each router should contain all three LAN networks learned dynamically via   EIGRP.

