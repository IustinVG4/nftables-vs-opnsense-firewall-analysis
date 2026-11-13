# Open-Source Firewall Comparative Analysis: NFtables vs. OPNsense

Comparative implementation and security testing of CLI-based (`nftables`) and GUI-based (`OPNsense`) firewalls for Year 3 Cyber Security at TU Dublin.

## 📌 Purpose & Outcome

* **Purpose:** Compare how effectively Linux `nftables` and FreeBSD `OPNsense` defend a segmented web server against Denial-of-Service (SYN flood) and reconnaissance (`Nmap`) attacks, while evaluating configuration complexity.

* **Outcome:** Deployed a 3-VM lab (`Attacker` -> `Firewall` -> `Victim` Nginx server). Demonstrated how rate-limiting rules (`limit rate 5/second` in `nftables` and `virusprot` connection limits in `OPNsense`) block flood traffic while keeping legitimate HTTP (`TCP/80`) traffic accessible.

## 🛠️ Technologies & Methods

* **Firewalls & OS:** `nftables` (Ubuntu Linux), `OPNsense` (FreeBSD), Kali Linux, Nginx web server

* **Testing Tools:** `hping3` (SYN flood testing), `Nmap` (port scanning), `curl` (service availability checks)

* **Networking:** Dual-subnet routing (`192.168.10.0/24` WAN and `192.168.20.0/24` LAN), stateful packet inspection

## 👨‍💻 Individual Contribution
Completed in a two-person team (**Iustin Valatucianu** and **Aoife Castaneto**)

* Configured and tested virtualised firewall and client VMs across the two-subnet topology.(Both)

* Executed live HTTP availability testing (`curl`) during active `hping3` SYN floods to measure performance impact.(Both)

* Configured OPNsense connection-rate limiting (`virusprot`) and verified attack mitigation via live firewall logs.(**Iustin Valatucianu**)

* Performed `Nmap` port scans and analysed rule-ordering/debugging trade-offs between CLI and GUI firewall administration.(**Aoife Castaneto**)

## 📂 Evidence Included in This Repository

* `NetworkSecurity_Project.pdf` — Full comparative report containing the 3-VM network topology diagram, `nftables` ruleset code, CPU/network resource graphs, `hping3`/`Nmap` terminal outputs, and OPNsense live firewall logs.
