# Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.ExportCommandLineHandler::ExitWithFailure

- ea: `0x5ab80`
- end: `0x5abbd`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.ExportCommandLineHandler::ExitWithFailure`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x8ba00`

## callees

- `0x229b0`
- `0x2bb50`
- `0x2bbb0`
- `0x5ab80`

## string_xrefs

- `0x5ab92`: `Failed to export installation configuration: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5ab80  ldarg.0
0x5ab81  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.ExportCommandLineHandler::serviceOptions
0x5ab86  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_Logger()
0x5ab8b  dup
0x5ab8c  brtrue.s loc_5AB91
0x5ab8e  pop
0x5ab8f  br.s     loc_5ABAB
0x5ab91  ldarg.1
0x5ab92  ldstr    aFailedToExport_0// "Failed to export installation configura"...
0x5ab97  ldc.i4.1
0x5ab98  newarr   [mscorlib]System.Object
0x5ab9d  dup
0x5ab9e  ldc.i4.0
0x5ab9f  ldarg.1
0x5aba0  callvirt instance string [mscorlib]System.Object::ToString()
0x5aba5  stelem.ref
0x5aba6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x5abab  ldarg.0
0x5abac  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.ExportCommandLineHandler::serviceOptions
0x5abb1  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_ShutdownService()
0x5abb6  ldc.i4.1
0x5abb7  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService::Shutdown(int32 exitCode)
0x5abbc  ret
```
