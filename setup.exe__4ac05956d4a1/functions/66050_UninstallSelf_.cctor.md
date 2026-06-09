# UninstallSelf::.cctor

- ea: `0x66050`
- end: `0x6608d`
- name: `UninstallSelf::.cctor`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## string_xrefs

- `0x66055`: `AppUninstallSelfRequested`
- `0x66069`: `AppUninstall`
- `0x6607d`: `AppUninstallSelfFailed`

## pseudocode

```c

```

## disassembly

```asm
0x66050  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0x66055  ldstr    aAppuninstallse// "AppUninstallSelfRequested"
0x6605a  call     string [mscorlib]System.String::Concat(string, string)
0x6605f  stsfld   string UninstallSelf::UninstallRequested
0x66064  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0x66069  ldstr    aAppuninstall// "AppUninstall"
0x6606e  call     string [mscorlib]System.String::Concat(string, string)
0x66073  stsfld   string UninstallSelf::UninstallStarted
0x66078  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0x6607d  ldstr    aAppuninstallse_0// "AppUninstallSelfFailed"
0x66082  call     string [mscorlib]System.String::Concat(string, string)
0x66087  stsfld   string UninstallSelf::UninstallFailed
0x6608c  ret
```
