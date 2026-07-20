# Systems, Services, and Identities
## Hosted Services
> Not actual hostnames for safety
> 
| Service | Hostname | Hosted On | Purpose |
|---|---|---|---|
| Primary Domain Controller | `DC01` | ESXi VM | Active Directory, primary authentication and directory services |
| Backup Domain Controller | `DC02` | ESXi VM | AD replication target, redundancy for authentication |
| Jump Box | `JUMP01` | ESXi VM | Sole entry point for remote administrative access to the server VLAN |
| RADIUS / NPS | `RADIUS01` | ESXi VM | 802.1X network authentication |
| Certificate Authority | `CA01` | ESXi VM | Internal PKI,  issues certificates for all lab services |
| Monitoring Dashboard | `GRAFANA01` | ESXi VM | Grafana, infrastructure metrics visualization |
| Uptime Monitoring | `KUMA01` | ESXi VM | Uptime Kuma, service availability checks |
| Logging | `SYSLOG01` | ESXi VM | Centralized syslog collection from all network switches |
| Imaging Server | `FOG01` | ESXi VM | PXE-boot network imaging pipeline |
| Asset Inventory | `SNIPEIT01` | ESXi VM | Snipe-IT,  inventory and asset tracking |
| Internal Wiki (BookStack) | `WIKI01` | ESXi VM | Internal documentation and knowledge base |
| Team Chat | `MATTERMOST01` | ESXi VM | Mattermost, class/program communication |
| File Server | `FS01` | Bare-metal (Windows Server) | Primary file storage and DHCP relay target |
| AI / ML Server | `AI01` | Bare-metal (Linux) | Dedicated AI/ML server (never had time to build out) |
| Backup Server | `BACKUP01` | Bare-metal (Windows Server) | Primary backup storage target |
| Backup & Replication | `VEEAM01` | Bare-metal (same host as `BACKUP01`) | Veeam, scheduled incremental backups |


## An Intial Problem We Faced

As we began to get deeper into administering the lab in 2024, we noticed a growing number of services we were missing that we required to effectively administer the lab and provide an effective learning environment. We also needed to standardize a things across the growing number of devices in the lab, like allowing for a consistent sign-on experience and keeping certain settings consistent across Windows devices.

## What We Built

- Administered a **75-user Active Directory domain** identity source for every student and teacher login across desktops, laptops, and
  services. Even configured Ubuntu laptops to allow domain credentials.
- Deployed and managed **Group Policy Objects (GPOs)** to standardize desktop
  configuration, software deployment, and security settings across the fleet
  without touching machines individually. One small fun example is we set the lock screen and wall paper to display the programs logo.
- Stood up multiple new VMs on our ESXi host including BookStack to hold an internal knowledge base, Mattermost to allow communication across the program, FOG for imaging needs, Uptime Kuma, and Grafana using the TIG stack (Telegraf, InfluxDB, Grafana)

## Result

- Sign-on and centrally managed permissions for 75 students across
  most devices in the lab
- Configuration rollout standardized through GPOs instead of manual
  per-machine setup, one fun exmaple is custom wallpaper/lock screen displaying program logo
- Multiple new services to make day-to-day operations smoother and increase program efficiancy
