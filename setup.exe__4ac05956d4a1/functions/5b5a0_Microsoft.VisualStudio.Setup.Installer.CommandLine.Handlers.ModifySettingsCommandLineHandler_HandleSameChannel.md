# Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.ModifySettingsCommandLineHandler::HandleSameChannel

- ea: `0x5b5a0`
- end: `0x5b5ca`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.ModifySettingsCommandLineHandler::HandleSameChannel`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x8d290`

## callees

- `0x229c0`
- `0x2bbb0`
- `0x59820`
- `0x59860`

## string_xrefs

- `0x5b5a0`: `'{0}' is already set to channel '{1}' for updates.`

## pseudocode

```c

```

## disassembly

```asm
0x5b5a0  ldstr    a0IsAlreadySetT// "'{0}' is already set to channel '{1}' f"...
0x5b5a5  ldarg.1
0x5b5a6  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions::get_InstallPath()
0x5b5ab  ldarg.1
0x5b5ac  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions::get_NewChannelUri()
0x5b5b1  call     string [mscorlib]System.String::Format(string, object, object)
0x5b5b6  stloc.0
0x5b5b7  ldarg.0
0x5b5b8  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.ModifySettingsCommandLineHandler::serviceOptions
0x5b5bd  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_ShutdownService()
0x5b5c2  ldc.i4.0
0x5b5c3  ldloc.0
0x5b5c4  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService::Shutdown(int32 exitCode, string message)
0x5b5c9  ret
```
