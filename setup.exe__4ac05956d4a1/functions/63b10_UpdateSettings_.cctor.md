# UpdateSettings::.cctor

- ea: `0x63b10`
- end: `0x63cb5`
- name: `UpdateSettings::.cctor`
- size: `421`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0x63b15`: `update-updatesettings`
- `0x63b3d`: `newChannelUri`
- `0x63b65`: `originalChannelUri`
- `0x63bc9`: `open-updatesettings`
- `0x63c2d`: `removeOos`
- `0x63c41`: `originalIncludeRecommendedOnUpdate`
- `0x63c55`: `newIncludeRecommendedOnUpdate`
- `0x63c69`: `didIncludeRecommendedOnUpdateChange`
- `0x63c7d`: `originalAutomaticallyUpdate`
- `0x63c91`: `newAutomaticallyUpdate`
- `0x63ca5`: `didAutomaticallyUpdateChange`

## pseudocode

```c

```

## disassembly

```asm
0x63b10  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x63b15  ldstr    aUpdateUpdatese// "update-updatesettings"
0x63b1a  call     string [mscorlib]System.String::Concat(string, string)
0x63b1f  stsfld   string UpdateSettings::UpdateSettingsEvent
0x63b24  ldsfld   string UpdateSettings::UpdateSettingsEvent
0x63b29  ldstr    aError// "-error"
0x63b2e  call     string [mscorlib]System.String::Concat(string, string)
0x63b33  stsfld   string UpdateSettings::UpdateSettingsErrorEvent
0x63b38  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63b3d  ldstr    aNewchanneluri_0// "newChannelUri"
0x63b42  call     string [mscorlib]System.String::Concat(string, string)
0x63b47  stsfld   string UpdateSettings::NewChannelUriProperty
0x63b4c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63b51  ldstr    aNewchannelid// "newChannelId"
0x63b56  call     string [mscorlib]System.String::Concat(string, string)
0x63b5b  stsfld   string UpdateSettings::NewChannelIdProperty
0x63b60  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63b65  ldstr    aOriginalchanne// "originalChannelUri"
0x63b6a  call     string [mscorlib]System.String::Concat(string, string)
0x63b6f  stsfld   string UpdateSettings::OriginalChannelUriProperty
0x63b74  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63b79  ldstr    aOriginalchanne_0// "originalChannelId"
0x63b7e  call     string [mscorlib]System.String::Concat(string, string)
0x63b83  stsfld   string UpdateSettings::OriginalChannelIdProperty
0x63b88  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63b8d  ldstr    aDidchannelidch// "didChannelIdChange"
0x63b92  call     string [mscorlib]System.String::Concat(string, string)
0x63b97  stsfld   string UpdateSettings::DidChannelIdChangeProperty
0x63b9c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63ba1  ldstr    aIssuccess// "isSuccess"
0x63ba6  call     string [mscorlib]System.String::Concat(string, string)
0x63bab  stsfld   string UpdateSettings::IsSuccessProperty
0x63bb0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63bb5  ldstr    aDidchannelchan// "didChannelChange"
0x63bba  call     string [mscorlib]System.String::Concat(string, string)
0x63bbf  stsfld   string UpdateSettings::DidChannelChangeProperty
0x63bc4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x63bc9  ldstr    aOpenUpdatesett// "open-updatesettings"
0x63bce  call     string [mscorlib]System.String::Concat(string, string)
0x63bd3  stsfld   string UpdateSettings::OpenChangeSettingsEvent
0x63bd8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63bdd  ldstr    aProductid// "productId"
0x63be2  call     string [mscorlib]System.String::Concat(string, string)
0x63be7  stsfld   string UpdateSettings::ProductIdProperty
0x63bec  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63bf1  ldstr    aChannelid// "channelId"
0x63bf6  call     string [mscorlib]System.String::Concat(string, string)
0x63bfb  stsfld   string UpdateSettings::ChannelIdProperty
0x63c00  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63c05  ldstr    aSource// "source"
0x63c0a  call     string [mscorlib]System.String::Concat(string, string)
0x63c0f  stsfld   string UpdateSettings::SourceProperty
0x63c14  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63c19  ldstr    aIschannelhop// "isChannelHop"
0x63c1e  call     string [mscorlib]System.String::Concat(string, string)
0x63c23  stsfld   string UpdateSettings::IsChannelHopProperty
0x63c28  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63c2d  ldstr    aRemoveoos_0// "removeOos"
0x63c32  call     string [mscorlib]System.String::Concat(string, string)
0x63c37  stsfld   string UpdateSettings::RemoveOosProperty
0x63c3c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63c41  ldstr    aOriginalinclud// "originalIncludeRecommendedOnUpdate"
0x63c46  call     string [mscorlib]System.String::Concat(string, string)
0x63c4b  stsfld   string UpdateSettings::OriginalIncludeRecommendedOnUpdate
0x63c50  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63c55  ldstr    aNewincludereco// "newIncludeRecommendedOnUpdate"
0x63c5a  call     string [mscorlib]System.String::Concat(string, string)
0x63c5f  stsfld   string UpdateSettings::NewIncludeRecommendedOnUpdate
0x63c64  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63c69  ldstr    aDidincludereco// "didIncludeRecommendedOnUpdateChange"
0x63c6e  call     string [mscorlib]System.String::Concat(string, string)
0x63c73  stsfld   string UpdateSettings::DidIncludeRecommendedOnUpdateChange
0x63c78  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63c7d  ldstr    aOriginalautoma// "originalAutomaticallyUpdate"
0x63c82  call     string [mscorlib]System.String::Concat(string, string)
0x63c87  stsfld   string UpdateSettings::OriginalAutomaticallyUpdate
0x63c8c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63c91  ldstr    aNewautomatical// "newAutomaticallyUpdate"
0x63c96  call     string [mscorlib]System.String::Concat(string, string)
0x63c9b  stsfld   string UpdateSettings::NewAutomaticallyUpdate
0x63ca0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63ca5  ldstr    aDidautomatical// "didAutomaticallyUpdateChange"
0x63caa  call     string [mscorlib]System.String::Concat(string, string)
0x63caf  stsfld   string UpdateSettings::DidAutomaticallyUpdateChange
0x63cb4  ret
```
