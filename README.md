# EnterpriseCertTrust

## Overview
EnterpriseCertTrust is a lightweight tool and configuration guide for enabling and managing `security.enterprise_roots.enabled` in Firefox, ensuring seamless certificate trust integration with enterprise-managed root certificates.

## Features
- Automates enabling **enterprise root certificate trust** in Firefox.
- Provides **PowerShell, Bash, and Registry scripts** for easy configuration.
- Guides for **enterprise deployment** via Group Policy (GPO) or JSON policies.
- Debugging and troubleshooting tips for certificate validation issues.

## Installation & Usage
### Windows
Run the PowerShell script to enable enterprise root certificates:
```powershell
Set-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Mozilla\Firefox" -Name "Certificates" -Value "EnterpriseRootsEnabled" -Type DWord
```

### macOS
Use the following command to enable enterprise root certificates:
```bash
defaults write "/Library/Preferences/org.mozilla.firefox" "EnterpriseRootsEnabled" -bool true
```

### Linux
Create a policy file to import enterprise root certificates:
```bash
echo '{ "policies": { "Certificates": { "ImportEnterpriseRoots": true } } }' | sudo tee /etc/firefox/policies/policies.json > /dev/null
```

## Troubleshooting
If certificates are not recognized:
1. Verify that the setting is correctly applied.
2. Restart Firefox and check `about:config`.
3. Ensure system certificates are properly installed.

## Contribution
We welcome contributions! Submit a pull request or report issues in our repository.

---

# GitHub Issue Template for Bug Reports

## Describe the Bug
Provide a clear and concise description of the bug, including any relevant details or error messages.

## Steps to Reproduce
List the steps needed to reproduce the issue:
1. Navigate to '...'
2. Click on '...'
3. Perform action '...'
4. Observe the error

## Expected Behavior
Describe what you expected to happen instead of the encountered issue.

## Screenshots
If applicable, attach screenshots or screen recordings to help illustrate the problem.

## System Information
### Desktop:
- **OS:** [e.g., Windows 11, macOS Ventura]
- **Browser:** [e.g., Chrome, Firefox, Edge]
- **Version:** [e.g., 115.0]

### Smartphone:
- **Device:** [e.g., iPhone 13, Samsung Galaxy S22]
- **OS:** [e.g., iOS 17, Android 14]
- **Browser:** [e.g., Safari, Chrome]
- **Version:** [e.g., 22]

## Logs & Error Messages
If applicable, copy and paste any error messages or relevant logs.

## Additional Context
Include any other relevant details that might help in troubleshooting.

---
**Commit Message:**
**update issue templates and add README**

### Extended Commit Description:
- Improved issue reproduction steps for clarity
- Added sections for logs and error messages
- Enhanced system information fields
- Refined additional context section for completeness
- Added README with project overview, features, installation, and troubleshooting guidance
