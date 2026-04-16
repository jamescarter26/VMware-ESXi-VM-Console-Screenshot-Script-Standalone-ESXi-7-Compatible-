# VMware ESXi VM Console Screenshot Tool

A lightweight PowerShell automation script designed to capture console screenshots from VMware ESXi virtual machines **without requiring vCenter**.

Built using **VMware PowerCLI**, this tool allows administrators to remotely capture VM console images from standalone ESXi hosts for troubleshooting, monitoring, and documentation purposes.

---

## ✨ Features

* Capture console screenshots from VMware ESXi virtual machines
* Works with **standalone ESXi hosts** (no vCenter required)
* Compatible with **VMware ESXi 7.x**
* Uses **VMware PowerCLI**
* Automatic screenshot download from datastore
* Timestamped output files
* TLS 1.2 compatibility
* Retry logic for reliability
* Supports local or network destination paths

---

## 🧰 Requirements

Before using this script, ensure you have:

* **VMware ESXi 7.x**
* **PowerShell 5.1 or later**
* **VMware PowerCLI 12 or later**
* Network access to the ESXi host
* Credentials with permission to access the VM

Install VMware PowerCLI if needed:

```powershell
Install-Module VMware.PowerCLI -Scope CurrentUser
```

---

## 🚀 Usage

### Basic Command

```powershell
.\Take-VM-Screenshot.ps1 `
    <ESXiHost> `
    <VMName> `
    <DestinationPath> `
    <IgnoreInvalidCert>
```

---

### Example

```powershell
.\Take-VM-Screenshot.ps1 `
    192.168.1.50 `
    TestVM `
    C:\VMShots `
    True
```

This will:

1. Connect to the ESXi host
2. Capture a console screenshot
3. Save it locally
4. Name it with a timestamp

Example output:

```text
C:\VMShots\TestVM_2026-04-16_103000.png
```

---

## 📁 Parameters

| Parameter         | Description                    |
| ----------------- | ------------------------------ |
| ESXiHost          | IP address or hostname of ESXi |
| VMName            | Virtual machine name           |
| DestinationPath   | Local or network folder        |
| IgnoreInvalidCert | True or False                  |

---

## 🔐 Certificate Handling

If your ESXi uses a self-signed certificate, set:

```text
True
```

Otherwise:

```text
False
```

---

## 📦 Example Workflow

Typical usage scenario:

1. Troubleshooting a remote VM
2. Capturing console screen
3. Saving image locally
4. Attaching screenshot to ticket system

Useful for:

* Helpdesk workflows
* Infrastructure monitoring
* Remote diagnostics
* VM documentation
* Incident response

---

## 🧪 Tested Environment

This script has been tested on:

* VMware ESXi **7.0.3**
* VMware PowerCLI **12+**
* PowerShell **5.1**
* Standalone ESXi hosts

---

## 📸 Output Format

Screenshots are saved as:

```text
PNG format
```

Filename format:

```text
VMNAME_YYYY-MM-DD_HHMMSS.png
```

Example:

```text
WebServer01_2026-04-16_101530.png
```

---

## ⚠️ Limitations

* Requires VM to be powered on
* Console must be accessible
* ESXi permissions required
* Designed for standalone ESXi environments

---

## 🛠 Troubleshooting

### PowerCLI Not Installed

Install using:

```powershell
Install-Module VMware.PowerCLI
```

---

### Cannot Connect to ESXi

Check:

* IP address
* Network access
* Credentials
* Firewall rules

---

### Screenshot Not Created

Verify:

* VM exists
* VM is powered on
* Destination path exists
* Datastore access permissions

---

## 📚 Use Cases

This tool is useful for:

* Remote troubleshooting
* Automated monitoring
* Documentation capture
* VM state verification
* Helpdesk incident support
* Homelab automation

---

## 🔄 Version

Current version:

```text
v1.0.0
```

---

## 📄 License

This project is licensed under the **MIT License**.

See:

```text
LICENSE
```

for full details.

---

## 🤝 Contributing

Contributions are welcome.

Steps:

1. Fork the repository
2. Create a branch
3. Submit a Pull Request

---

## ⭐ Support

If this project helps you:

* Star the repository ⭐
* Share with others
* Submit improvements

---

## 👤 Author

Created by:

**James Carter**

System Administrator / Infrastructure Automation
