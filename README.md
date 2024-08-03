# Best-Practices-Proxmox

Configure Update Procedure Correctly:
Disable enterprise repositories and add no-subscription repositories for updates.
Steps: Go to the repository section, disable enterprise repositories, add no-subscription repositories, refresh updates, and click on upgrade.

Enable Notifications:
Set up email notifications for system events.
Steps: Go to Data Center > Notifications, add a new notification target using SMTP, and configure notification matchers to use this target.

Issue Trusted TLS Certificates:
Get rid of browser certificate warnings by using trusted certificates.
Steps: Register a public domain and use a DNS provider like Cloudflare. In Proxmox, go to Data Center > ACME, configure the DNS challenge with Cloudflare API, and order certificates.

Configure Storage Options:
Set up appropriate storage locations for VM backups and other data.
Steps: In Data Center > Storage, add and configure storage options like NFS for backups. Define what each storage can hold (e.g., disk images, backup files).

Set Up Backup Jobs:
Regularly back up VMs to prevent data loss.
Steps: Go to Data Center > Backup, create backup jobs, select VMs to back up, set schedule and target storage, and configure notifications for backup results.

Enable PCI Passthrough:
Pass through hardware devices like graphics cards or storage controllers to VMs.
Steps: Ensure IOMMU is enabled in BIOS, verify it's enabled in Proxmox, and add PCI devices in the VM's hardware section.

Follow Best Practices for Creating VMs:
Use optimized settings for VM performance and compatibility.
Steps: When creating a VM, choose the appropriate OS type, enable virtIO drivers, use QEMU guest agent, configure TPM and UEFI for Windows, and select virtIO for network interfaces.

Create VM Templates:
Simplify VM provisioning by using templates.
Steps: Prepare a VM, reset machine-specific settings (like SSH keys), convert the VM to a template, and clone new VMs from this template.
