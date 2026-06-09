# InstallerUpdateInfo::.cctor

- ea: `0x63fc0`
- end: `0x64061`
- name: `InstallerUpdateInfo::.cctor`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## string_xrefs

- `0x63fc5`: `get-installerupdateinfo-noweb`
- `0x64001`: `channelManagerSuggestingUpdate`
- `0x64029`: `updateRequiredVersion`
- `0x64051`: `get-installerupdateinfo-noweb-fault`

## pseudocode

```c

```

## disassembly

```asm
0x63fc0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x63fc5  ldstr    aGetInstallerup// "get-installerupdateinfo-noweb"
0x63fca  call     string [mscorlib]System.String::Concat(string, string)
0x63fcf  stsfld   string InstallerUpdateInfo::UpdateInstallerNowebEvent
0x63fd4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63fd9  ldstr    aLayoutopcversi// "layoutOpcVersion"
0x63fde  call     string [mscorlib]System.String::Concat(string, string)
0x63fe3  stsfld   string InstallerUpdateInfo::LayoutOpcVersionProperty
0x63fe8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63fed  ldstr    aCurrentclientv// "currentClientVersion"
0x63ff2  call     string [mscorlib]System.String::Concat(string, string)
0x63ff7  stsfld   string InstallerUpdateInfo::CurrentClientVersionProperty
0x63ffc  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x64001  ldstr    aChannelmanager// "channelManagerSuggestingUpdate"
0x64006  call     string [mscorlib]System.String::Concat(string, string)
0x6400b  stsfld   string InstallerUpdateInfo::ChannelManagerSuggestingUpdateProperty
0x64010  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x64015  ldstr    aChannelmanager_0// "channelManagerSuggestedVersion"
0x6401a  call     string [mscorlib]System.String::Concat(string, string)
0x6401f  stsfld   string InstallerUpdateInfo::ChannelManagerSuggestedVersionProperty
0x64024  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x64029  ldstr    aUpdaterequired// "updateRequiredVersion"
0x6402e  call     string [mscorlib]System.String::Concat(string, string)
0x64033  stsfld   string InstallerUpdateInfo::UpdateRequiredProperty
0x64038  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x6403d  ldstr    aTargetclientve// "targetClientVersion"
0x64042  call     string [mscorlib]System.String::Concat(string, string)
0x64047  stsfld   string InstallerUpdateInfo::TargetClientVersionProperty
0x6404c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x64051  ldstr    aGetInstallerup_0// "get-installerupdateinfo-noweb-fault"
0x64056  call     string [mscorlib]System.String::Concat(string, string)
0x6405b  stsfld   string InstallerUpdateInfo::UpdateInstallerNowebExceptionEvent
0x64060  ret
```
