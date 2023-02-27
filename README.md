# MASSaRCE

Check where you have access in an Active Directory environment!

## Usage

```
PS C:\> Import-Module .\MASSaRCE.ps1
PS C:\> Connect-MassWinRM -Command hostname -Username lab\Administrator
dc01
file01
ws01
PS C:\> Connect-MassRDP -Username lab\Administrator
Press ENTER to launch RDP to DC01, or 's' to skip: 
Press ENTER to launch RDP to FILE01, or 's' to skip:
Press ENTER to launch RDP to WS01, or 's' to skip:

```

## What is this?

This is a simple PowerShell script that allows you to run commands on many remote systems in an Active Directory environment, mainly to learn which systems you have administrative access to. It currently supports WinRM and RDP.

## Dependencies

Requires the [ActiveDirectory PowerShell module](https://docs.microsoft.com/en-us/powershell/module/activedirectory/?view=windowsserver2019-ps) to be installed. If you lack the privileges to install it on the target system, see the standalone [ADModule](https://github.com/samratashok/ADModule) repo.

## OpSec

This is one of the least stealthy things you can do! You have been warned. 

Currently, Connect-MassRDP saves the password locally in cmdkey for all targets. You might wish to delete them.

## Disclaimer

This tool should be used for authorized testing and/or educational purposes only.

## Credits

Thank you [Jaap Brasser](http://www.jaapbrasser.com) for RDP connection functionality.
