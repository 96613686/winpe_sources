# Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::.cctor

- ea: `0x8430`
- end: `0x8480`
- name: `Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::.cctor`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x8430`: `/finalizeinstall`
- `0x843a`: `/uninstall`
- `0x844e`: `vs_installer.windows.exe`
- `0x845d`: `.config`

## pseudocode

```c

```

## disassembly

```asm
0x8430  ldstr    aFinalizeinstal_0// "/finalizeinstall"
0x8435  stsfld   string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::FinalizeInstallerParameterName
0x843a  ldstr    aUninstall// "/uninstall"
0x843f  stsfld   string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::UninstallInstallerParameterName
0x8444  ldstr    a6f320b93Ee3c48// "6F320B93-EE3C-4826-85E0-ADF79F8D4C61"
0x8449  stsfld   string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::InstallerAddRemoveProgramsGuid
0x844e  ldstr    aVsInstallerWin// "vs_installer.windows.exe"
0x8453  stsfld   string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::InstallerFinalizerFileName
0x8458  ldsfld   string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::InstallerFinalizerFileName
0x845d  ldstr    aConfig// ".config"
0x8462  call     string [mscorlib]System.String::Concat(string, string)
0x8467  stsfld   string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::InstallerFinalizerConfigFileName
0x846c  ldc.r8   5.0
0x8475  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x847a  stsfld   valuetype [mscorlib]System.TimeSpan Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::ServiceStopTimeout
0x847f  ret
```
