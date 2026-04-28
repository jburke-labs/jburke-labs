# Hi, I'm Jason

**Systems Administrator · Homelab Builder · Cybersecurity Aspirant · Northern Ireland**

---

I work in IT systems administration and I'm building toward cloud infrastructure and cybersecurity roles through structured, hands-on practical work rather than certifications alone.

The projects here are real. They came from real ideas with real problems, real troubleshooting sessions, and real lessons learned the hard way. I have tried to ensure I documented properly throughout — not just "here is the config that worked," but why it worked, what broke first, how I isolated it, and what I would do differently next time.

I treat the lab like a proper technical environment. That means planned segmentation, documented runbooks, structured change decisions, and evidence that something actually works rather than just looks like it might.

---

## What I'm Building

**Project Cerberus** is my enterprise-style homelab — built around real enterprise hardware and designed to mirror the kind of environment I would expect to support or design in a real business.

The current environment includes:

- FortiGate 300D firewall handling edge security, NAT, inter-VLAN policy and VPN (old but gold, just a tad power hungry!)
- Cisco Catalyst 2960X providing core Layer 2 switching and VLAN trunking
- HPE ProLiant DL380 Gen9 and Dell PowerEdge R620 running Proxmox virtualisation
- Wazuh SIEM deployed and actively receiving telemetry from multiple endpoints
- Internal reverse proxy layer using NGINX Proxy Manager with wildcard certificate trust
- WireGuard VPN providing secure remote access through a double-NAT environment
- AdGuard Home handling internal DNS filtering, rewrites and query visibility
- Snipe-IT asset management platform running on a dedicated Docker host

The lab is being expanded in phases toward Windows enterprise infrastructure, purple team testing, Docker and Kubernetes testing, and Microsoft Azure / Entra ID / Intune integration where available.

---

## Projects

### 🏗️ [Project Cerberus — Infrastructure Overview](https://jburke-labs.github.io/project-cerberus)
Enterprise-style homelab built on physical enterprise hardware. FortiGate firewalling, Cisco switching, Proxmox virtualisation, shared storage planning, and a structured VLAN segmentation design across management, servers, storage, clients, security monitoring and guest networks.

---

### 🔐 [NGINX Proxy Manager + AdGuard + Wildcard Certificate](https://github.com/jburke-labs/nginx-proxy-wildcard-cert)
Migrated from a CLI-based NGINX reverse proxy to NGINX Proxy Manager, deployed internal DNS rewrites using AdGuard Home, and implemented a mkcert-generated wildcard certificate for `*.cerberus.home.arpa`. Resolved a Wazuh login loop caused by frontend SSL handling, diagnosed a stale browser trust state using DevTools, and created a repeatable internal service onboarding pattern. Full troubleshooting narrative documented.

**Tech:** NGINX Proxy Manager · AdGuard Home · mkcert · internal PKI · HTTPS · Proxmox LXC

---

### 🔒 [WireGuard VPN — Double NAT Deployment and Troubleshooting](https://github.com/jburke-labs/wireguard-vpn-deployment)
Deployed a WireGuard VPN server inside a Proxmox LXC, placed behind a FortiGate firewall operating in a double-NAT arrangement with a Virgin Media upstream router. Validated the full connection path end to end using FortiGate packet captures, tcpdump on the LXC, IP forwarding configuration, NAT masquerade rules, and structured peer configuration. The final root cause was a client endpoint set to an internal IP rather than the public address — found only after every other layer had been proven clean.

**Tech:** WireGuard · Proxmox LXC · FortiGate VIP · Linux networking · NAT · packet capture · WGDashboard

---

### 🖥️ [Snipe-IT Replatform — Proxmox LXC to Dedicated Docker Host](https://github.com/jburke-labs/snipe-it-replatform)
Migrated a production Snipe-IT asset management deployment from a Proxmox community-script LXC into a dedicated Ubuntu 24.04 host running Docker Compose with a Caddy reverse proxy and internal TLS. Carried out a full data migration covering 82 users, 148 assets and all uploads, resolving an upload path symlink mismatch and an APP_KEY alignment issue that would have caused silent decryption failures. Corporate deployment design included FortiGate ACL allowlisting, default-deny network posture, SSH hardening, and an ISO 27001-aligned evidence approach.

**Tech:** Docker Compose · Ubuntu 24.04 · Caddy · MariaDB · Snipe-IT · Laravel · internal TLS · ISO 27001

---

### 🛡️ [Wazuh SOC Automation Pipeline](https://github.com/jburke-labs/wazuh-soc-automation) *(Active Build)*
Designing and building a practical SIEM-to-response pipeline around Wazuh, which is already deployed and receiving telemetry from multiple endpoints. The architecture is intentionally staged: Wazuh handles detection, a promotion layer filters meaningful events, Shuffle manages orchestration and runbook execution, and DFIR-IRIS handles incident case management. Teams and Freshdesk are reserved for a later corporate integration phase. The first automated use case is SSH brute-force detection with a safe, time-bound IP containment response.

**Tech:** Wazuh · OpenSearch · Shuffle · DFIR-IRIS · Proxmox LXC · FortiGate syslog · detection engineering

---

## Skills

```
Infrastructure          Networking              Security
─────────────────────   ─────────────────────   ─────────────────────
Proxmox VE              FortiGate               Wazuh SIEM
VMware ESXi             Cisco Catalyst          AdGuard Home
Ubuntu / Debian         VLAN design             Firewall policy design
Windows Server          Inter-VLAN routing      Internal PKI / mkcert
Docker Compose          WireGuard VPN           Reverse proxy / TLS
Linux administration    DNS architecture        ISO 27001 alignment
Snipe-IT                NAT / double NAT        Packet capture / tcpdump
Proxmox Backup          Trunk / access ports    Structured troubleshooting
```

---

## How I Document

Every project here has a matching write-up that covers what I was trying to achieve, the decisions made along the way, what broke, how I isolated it, and what was left working at the end.

The Notion workspace behind these projects includes runbooks, STAR-format troubleshooting analyses, asset registers, interface maps, and phased roadmaps. Where a GitHub README gives you the summary, the Notion doc gives you the full depth.

I document this way because in a real environment, the person fixing something at 2am should not need to reverse-engineer what was built. They should be able to read a doc and understand it.

---

## Currently Working On

- Expanding Wazuh log collection across Windows, Linux, FortiGate and Proxmox
- Building the Shuffle and DFIR-IRIS layers for the SOC automation pipeline
- Planning the Windows enterprise virtual lab — DC01, DC02, ADCS, GPO baselines
- Designing the purple team testing range with isolated attack and defence VLANs
- Progressing toward AZ-104 and SC-200 certification

---

## Connect

- 💼 [LinkedIn](https://www.linkedin.com/in/jason-burke-822000142)
- 🌐 [Project Cerberus — Live Infrastructure Page](https://jburke-labs.github.io/project-cerberus)

---

*Everything here is built, broken, fixed and documented in a homelab in Northern Ireland while heavily caffeinated.*
