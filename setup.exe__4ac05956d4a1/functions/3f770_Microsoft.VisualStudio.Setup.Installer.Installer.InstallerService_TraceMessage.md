# Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::TraceMessage

- ea: `0x3f770`
- end: `0x3f792`
- name: `Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::TraceMessage`
- size: `34`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3f600`
- `0x7b460`
- `0x7b760`
- `0x7b9f0`
- `0x7bc80`

## callees

- `0x2c4b0`
- `0x3f770`

## string_xrefs

- `0x3f780`: `[InstallerService]: `

## pseudocode

```c

```

## disassembly

```asm
0x3f770  ldarg.0
0x3f771  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::serviceOptions
0x3f776  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x3f77b  dup
0x3f77c  brtrue.s loc_3F780
0x3f77e  pop
0x3f77f  ret
0x3f780  ldstr    aInstallerservi// "[InstallerService]: "
0x3f785  ldarg.1
0x3f786  call     string [mscorlib]System.String::Concat(string, string)
0x3f78b  ldarg.2
0x3f78c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x3f791  ret
```
