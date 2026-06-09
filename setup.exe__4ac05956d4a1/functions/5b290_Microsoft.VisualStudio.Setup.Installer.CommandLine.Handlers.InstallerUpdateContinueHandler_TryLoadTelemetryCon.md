# Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler::TryLoadTelemetryContextFile

- ea: `0x5b290`
- end: `0x5b38d`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler::TryLoadTelemetryContextFile`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x5b250`

## callees

- `0x22300`
- `0x2bb50`
- `0x2bb70`
- `0x2bbc0`
- `0x3dbc0`
- `0x59260`
- `0x59300`
- `0x5b290`

## string_xrefs

- `0x5b2a1`: `Loading telemetry context subdirectory: `
- `0x5b378`: `Failed to create an installer telemetry context serializer and deserialize.`

## pseudocode

```c

```

## disassembly

```asm
0x5b290  ldarg.0
0x5b291  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler::serviceOptions
0x5b296  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_Logger()
0x5b29b  dup
0x5b29c  brtrue.s loc_5B2A1
0x5b29e  pop
0x5b29f  br.s     loc_5B2BB
0x5b2a1  ldstr    aLoadingTelemet// "Loading telemetry context subdirectory:"...
0x5b2a6  ldarg.1
0x5b2a7  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_TelemetryContextSubDirectory()
0x5b2ac  call     string [mscorlib]System.String::Concat(string, string)
0x5b2b1  call     T0x2B000010
0x5b2b6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5b2bb  ldarg.2
0x5b2bc  ldnull
0x5b2bd  stind.ref
0x5b2be  ldarg.1
0x5b2bf  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_TelemetryContextSubDirectory()
0x5b2c4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5b2c9  brtrue   loc_5B389
0x5b2ce  ldarg.0
0x5b2cf  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler::serviceOptions
0x5b2d4  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_FileSystem()
0x5b2d9  ldarg.1
0x5b2da  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_TelemetryContextSubDirectory()
0x5b2df  call     string Microsoft.VisualStudio.Setup.Installer.Utilities.Utilities::GetTelemetryContextFilePath(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string contextGuid)
0x5b2e4  stloc.0
0x5b2e5  ldarg.0
0x5b2e6  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler::serviceOptions
0x5b2eb  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_FileSystem()
0x5b2f0  ldloc.0
0x5b2f1  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x5b2f6  brfalse  loc_5B389
0x5b2fb  ldarg.0
0x5b2fc  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler::serviceOptions
0x5b301  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Services.InstallerTelemetryContextSerializer::.ctor([opt] class [mscorlib]System.IServiceProvider services)
0x5b306  stloc.1
0x5b307  ldarg.2
0x5b308  ldloc.1
0x5b309  ldarg.0
0x5b30a  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler::serviceOptions
0x5b30f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_FileSystem()
0x5b314  ldloc.0
0x5b315  call     T0x2B00038F
0x5b31a  stind.ref
0x5b31b  ldc.i4.1
0x5b31c  stloc.2
0x5b31d  leave.s  loc_5B38B
0x5b31f  stloc.3
0x5b320  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x5b325  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::LoadTelemetryContextSessionIdProperty
0x5b32a  stloc.s  5
0x5b32c  dup
0x5b32d  ldloc.s  5
0x5b32f  ldarg.1
0x5b330  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_InstallSessionId()
0x5b335  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5b33a  stloc.s  4
0x5b33c  ldarg.0
0x5b33d  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler::serviceOptions
0x5b342  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_Telemetry()
0x5b347  dup
0x5b348  brtrue.s loc_5B34D
0x5b34a  pop
0x5b34b  br.s     loc_5B366
0x5b34d  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::LoadTelemetryContextFailEvent
0x5b352  ldloc.3
0x5b353  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5b358  ldloc.s  4
0x5b35a  ldloc.3
0x5b35b  ldnull
0x5b35c  ldc.i4.0
0x5b35d  ldnull
0x5b35e  ldc.i4.0
0x5b35f  ldnull
0x5b360  ldc.i4.0
0x5b361  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x5b366  ldarg.0
0x5b367  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler::serviceOptions
0x5b36c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_Logger()
0x5b371  dup
0x5b372  brtrue.s loc_5B377
0x5b374  pop
0x5b375  br.s     loc_5B387
0x5b377  ldloc.3
0x5b378  ldstr    aFailedToCreate_3// "Failed to create an installer telemetry"...
0x5b37d  call     T0x2B000010
0x5b382  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x5b387  leave.s  loc_5B389
0x5b389  ldc.i4.0
0x5b38a  ret
0x5b38b  ldloc.2
0x5b38c  ret
```
