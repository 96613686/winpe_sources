# SharedProperties::.cctor

- ea: `0x65c30`
- end: `0x65d71`
- name: `SharedProperties::.cctor`
- size: `321`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## string_xrefs

- `0x65d11`: `updatefromvs`
- `0x65d25`: `installerversion`

## pseudocode

```c

```

## disassembly

```asm
0x65c30  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65c35  ldstr    aSource// "source"
0x65c3a  call     string [mscorlib]System.String::Concat(string, string)
0x65c3f  stsfld   string SharedProperties::SourceProperty
0x65c44  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65c49  ldstr    aApplicationbra// "applicationbranchname"
0x65c4e  call     string [mscorlib]System.String::Concat(string, string)
0x65c53  stsfld   string SharedProperties::BranchProperty
0x65c58  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65c5d  ldstr    aProcesstype// "processtype"
0x65c62  call     string [mscorlib]System.String::Concat(string, string)
0x65c67  stsfld   string SharedProperties::ProcessType
0x65c6c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65c71  ldstr    aLocale// "locale"
0x65c76  call     string [mscorlib]System.String::Concat(string, string)
0x65c7b  stsfld   string SharedProperties::LocaleProperty
0x65c80  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65c85  ldstr    aCampaign// "campaign"
0x65c8a  call     string [mscorlib]System.String::Concat(string, string)
0x65c8f  stsfld   string SharedProperties::CampaignProperty
0x65c94  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65c99  ldstr    aActivityid// "activityid"
0x65c9e  call     string [mscorlib]System.String::Concat(string, string)
0x65ca3  stsfld   string SharedProperties::ActivityIdProperty
0x65ca8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65cad  ldstr    aStartmethod// "startmethod"
0x65cb2  call     string [mscorlib]System.String::Concat(string, string)
0x65cb7  stsfld   string SharedProperties::StartMethodProperty
0x65cbc  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65cc1  ldstr    aQuiet_1// "quiet"
0x65cc6  call     string [mscorlib]System.String::Concat(string, string)
0x65ccb  stsfld   string SharedProperties::QuietProperty
0x65cd0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65cd5  ldstr    aPassive_0// "passive"
0x65cda  call     string [mscorlib]System.String::Concat(string, string)
0x65cdf  stsfld   string SharedProperties::PassiveProperty
0x65ce4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65ce9  ldstr    aForce// "force"
0x65cee  call     string [mscorlib]System.String::Concat(string, string)
0x65cf3  stsfld   string SharedProperties::ForceProperty
0x65cf8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65cfd  ldstr    aNoweb// "noweb"
0x65d02  call     string [mscorlib]System.String::Concat(string, string)
0x65d07  stsfld   string SharedProperties::NoWebProperty
0x65d0c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65d11  ldstr    aUpdatefromvs// "updatefromvs"
0x65d16  call     string [mscorlib]System.String::Concat(string, string)
0x65d1b  stsfld   string SharedProperties::UpdateFromVSProperty
0x65d20  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65d25  ldstr    aInstallerversi// "installerversion"
0x65d2a  call     string [mscorlib]System.String::Concat(string, string)
0x65d2f  stsfld   string SharedProperties::InstallerVersionProperty
0x65d34  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65d39  ldstr    aIselevated// "iselevated"
0x65d3e  call     string [mscorlib]System.String::Concat(string, string)
0x65d43  stsfld   string SharedProperties::IsElevated
0x65d48  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65d4d  ldstr    aIssystem// "issystem"
0x65d52  call     string [mscorlib]System.String::Concat(string, string)
0x65d57  stsfld   string SharedProperties::IsSystem
0x65d5c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65d61  ldstr    aIsadmin// "isadmin"
0x65d66  call     string [mscorlib]System.String::Concat(string, string)
0x65d6b  stsfld   string SharedProperties::IsAdmin
0x65d70  ret
```
