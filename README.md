# agentlookout

Remove unwanted macOS launch agents

```
$ agentlookout
Will delete unrecognized launch agents:
  - /Library/LaunchAgents/com.adobe.AdobeCreativeCloud.plist
  - /Library/LaunchDaemons/com.adobe.acc.installer.v2.plist
  - /Library/LaunchDaemons/net.mullvad.daemon.plist
Delete? [y/n]
```

## Install

1. Define your allowed launch agents at the top of the `agentlookout` file
2. Run `make install` to install to `/usr/local/bin/agentlookout`

Can be uninstalled by running `make uninstall`.

## Usage

Run `agentlookout` with root access to find all launch agents not included in the exception list. Before deletion all launch agents that will be removed are listed and user is asked to confirm they want to delete.

## What is a launch agent?

On macOS launch agents are one of the methods that applications launch at startup. The user is never asked if they want a launch agent installed and as such multiple daemons build up (Creative Cloud and Chrome are the worst offenders). There is a valid need for launch agents and as such selected ones can be excluded from deletion.

## Disclaimer

`agentlookout` touches system level files at root access which can lead to a non-functioning system. I am not responsible for any damage to your system at the result of this script. Please make sure you understand what you are doing before running or modifying the script in any way.