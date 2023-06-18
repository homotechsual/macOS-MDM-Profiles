# MDM Configuration Profiles

In this repository you'll find various MDM configuration profiles for macOS - tested with Microsoft Intune. Each profile is a separate file and can be downloaded individually.

## The Profiles

### Microsoft AutoUpdate

This profile was created by me and is not officially supported by Microsoft.

* #### [Background Services](mau_backgroundservices.mobileconfig)

  This profile prevents disabling the Microsoft AutoUpdate background services on macOS. The services covered are:

  * `com.microsoft.autoupdate.helper`
  * `com.microsoft.update.agent`

### Microsoft Defender for Endpoint/for Business

These profiles originally come from [Microsoft's repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).

* #### [Background Services](mdfb_backgroundservices.mobileconfig)

  This profile prevents disabling the Microsoft Defender for Endpoint/for Business background services on macOS. The services covered are:

  * `com.microsoft.fresno`
  * `com.microsoft.fresno.uninstall`
  * `com.microsoft.dlp.install_monitor`

* #### [Full Disk Access](mdfb_fulldiskaccess.mobileconfig)

  This profile configures full disk access for the Microsoft Defender for Endpoint/for Business application(s) and prevents removal of these permissions. Permissions are granted for the following applications:

  * `com.microsoft.wdav` - The Microsoft Defender application.
  * `com.microsoft.wdav.epsext` - The Microsoft Defender endpoint security extension.
  * `com.microsoft.dlp.daemon` - The Microsoft Data Loss Prevention daemon.

* #### [Network Filter](mdfb_networkfilter.mobileconfig)

  This profile configures the Microsoft Defender for Endpoint/for Business network filter on macOS and prevents this being disabled by the user.

* #### [Notifications](mdfb_notifications.mobileconfig)

  This profile configures the Microsoft Defender for Endpoint/for Business notification settings on macOS and prevents these being disabled by the user.

### Microsoft OneDrive

These profiles were created by me and are not officially supported by Microsoft.

* #### [Background Services](onedrive_backgroundservices.mobileconfig)

  This profile prevents disabling the Microsoft OneDrive background services on macOS. The services covered are:

  * `com.microsoft.OneDriveStandaloneUpdater` - The Microsoft OneDrive standalone updater.

* #### [Full Disk Access](onedrive_fulldiskaccess.mobileconfig)

  This profile configures full disk access for the Microsoft OneDrive application(s) and prevents removal of these permissions. Permissions are granted for the following applications:

  * `com.microsoft.OneDrive` - The Microsoft OneDrive application.

### Microsoft Teams

These profiles were created by me and are not officially supported by Microsoft.

* #### [Background Services](teams_backgroundservices.mobileconfig)

  This profile prevents disabling the Microsoft Teams background services on macOS. The services covered are:

  * `com.microsoft.teams.TeamsUpdaterDaemon` - The Microsoft Teams updater daemon.

### [NinjaOne](https://www.ninjaone.com) Agent (formerly NinjaRMM)

These profiles were created by me and are not officially supported by NinjaOne.

* #### [Background Services](noagent_backgroundservices.mobileconfig)

  This profile prevents disabling the NinjaOne Agent background services on macOS. The services covered are:

  * `com.ninjarmm.agentd` - The NinjaOne Agent.
  * `com.ninjarmm.patcher` - The NinjaOne Agent patcher.
  * `com.ninjarmm.njdialog` - The NinjaOne Agent dialog.
  * `com.ninjarmm.trayicon` - The NinjaOne Agent tray icon.

* #### [Full Disk Access](noagent_fulldiskaccess.mobileconfig)

  This profile configures full disk access for the NinjaOne Agent application(s) and prevents removal of these permissions. Permissions are granted for the following applications:

  * `ninjarmm-agent` - The NinjaOne Agent application.

* #### [Notifications](noagent_notifications.mobileconfig)

  This profile configures the NinjaOne Agent notification settings on macOS and prevents these being disabled by the user.

## Pushing Profiles to macOS with Microsoft Intune

You can push these profiles to macOS with Microsoft Intune. To do so, follow the steps outlined in [Microsoft's documentation](https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/mac-install-with-intune?view=o365-worldwide#create-system-configuration-profiles) ensuring you enter an appropriate name and description for each profile and upload the appropriate profile from this repository.

## Pushing Profiles to macOS with Jamf Pro

These profile files will contain enough information to use Jamf's Configure Privacy Preferences Policy Control wizard to create a PPPC profile. The steps should be similar to those outlined by [Microsoft's documentation](https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/mac-jamfpro-policies?view=o365-worldwide#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint) where they illustrate configuring Full Disk Access for Microsoft Defender for Endpoint/for Business.

When pushing out background services settings you can upload the profile directly as shown, again in [Microsoft's documentation](https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/mac-jamfpro-policies?view=o365-worldwide#step-9-configure-background-services) for Microsoft Defender for Endpoint/for Business.

The profiles haven't been tested with Jamf Pro, but should work. If you encounter any issues, please let me know.
