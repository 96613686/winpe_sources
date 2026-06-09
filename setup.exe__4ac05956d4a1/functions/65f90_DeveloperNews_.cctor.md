# DeveloperNews::.cctor

- ea: `0x65f90`
- end: `0x66009`
- name: `DeveloperNews::.cctor`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## string_xrefs

- `0x65fa9`: `DeveloperNews/force-update`
- `0x65fbd`: `DeveloperNews/update-feed`

## pseudocode

```c

```

## disassembly

```asm
0x65f90  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65f95  ldstr    aOperationresul// "operationResult"
0x65f9a  call     string [mscorlib]System.String::Concat(string, string)
0x65f9f  stsfld   string DeveloperNews::OperationResultProperty
0x65fa4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0x65fa9  ldstr    aDevelopernewsF// "DeveloperNews/force-update"
0x65fae  call     string [mscorlib]System.String::Concat(string, string)
0x65fb3  stsfld   string DeveloperNews::ForceNewsFeedUpdate
0x65fb8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0x65fbd  ldstr    aDevelopernewsU// "DeveloperNews/update-feed"
0x65fc2  call     string [mscorlib]System.String::Concat(string, string)
0x65fc7  stsfld   string DeveloperNews::UpdateNewsFeed
0x65fcc  ldsfld   string DeveloperNews::UpdateNewsFeed
0x65fd1  ldstr    aError// "-error"
0x65fd6  call     string [mscorlib]System.String::Concat(string, string)
0x65fdb  stsfld   string DeveloperNews::UpdateNewsFeedError
0x65fe0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65fe5  ldstr    aIscerterror// "iscerterror"
0x65fea  call     string [mscorlib]System.String::Concat(string, string)
0x65fef  stsfld   string DeveloperNews::IsCertError
0x65ff4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65ff9  ldstr    aDuration// "duration"
0x65ffe  call     string [mscorlib]System.String::Concat(string, string)
0x66003  stsfld   string DeveloperNews::Duration
0x66008  ret
```
