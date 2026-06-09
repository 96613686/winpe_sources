# Events::.cctor

- ea: `0x905f0`
- end: `0x9062d`
- name: `Events::.cctor`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## string_xrefs

- `0x905f5`: `vsupdaterbootstrapper/`
- `0x90609`: `install-vsupdater`
- `0x9061d`: `uninstall-vsupdater`

## pseudocode

```c

```

## disassembly

```asm
0x905f0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x905f5  ldstr    aVsupdaterboots// "vsupdaterbootstrapper/"
0x905fa  call     string [mscorlib]System.String::Concat(string, string)
0x905ff  stsfld   string Events::Prefix
0x90604  ldsfld   string Events::Prefix
0x90609  ldstr    aInstallVsupdat// "install-vsupdater"
0x9060e  call     string [mscorlib]System.String::Concat(string, string)
0x90613  stsfld   string Events::InstallEvent
0x90618  ldsfld   string Events::Prefix
0x9061d  ldstr    aUninstallVsupd// "uninstall-vsupdater"
0x90622  call     string [mscorlib]System.String::Concat(string, string)
0x90627  stsfld   string Events::UninstallEvent
0x9062c  ret
```
