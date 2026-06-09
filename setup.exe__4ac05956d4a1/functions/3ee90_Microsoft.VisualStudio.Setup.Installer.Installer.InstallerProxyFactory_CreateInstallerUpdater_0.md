# Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::CreateInstallerUpdater_0

- ea: `0x3ee90`
- end: `0x3ef91`
- name: `Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::CreateInstallerUpdater_0`
- size: `257`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3e890`
- `0x3e930`
- `0x3ea00`

## callees

- `0x21a40`
- `0x2c4b0`
- `0x2c510`
- `0x2c6d0`
- `0x3e7a0`
- `0x3ee90`
- `0x40e80`
- `0x40ea0`
- `0x55720`
- `0x56880`
- `0x57640`
- `0x57f80`

## string_xrefs

- `0x3ef25`: `Created a {0}`
- `0x3ef71`: `InstallerOperationTelemetryDecorator`

## pseudocode

```c

```

## disassembly

```asm
0x3ee90  ldarg.0
0x3ee91  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ee96  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_InstallerSettingsService()
0x3ee9b  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService::get_NoUpdateInstaller()
0x3eea0  brfalse.s loc_3EEAD
0x3eea2  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_InstallerUpdateRequired()
0x3eea7  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.UpdateRequiredException::.ctor(string)
0x3eeac  throw
0x3eead  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.SelectedPackageParser::.ctor()
0x3eeb2  stloc.0
0x3eeb3  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.PathParser::.ctor()
0x3eeb8  stloc.1
0x3eeb9  ldarg.0
0x3eeba  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3eebf  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerUpdateOptionsProviderServiceOptions::.ctor(class [mscorlib]System.IServiceProvider services)
0x3eec4  stloc.2
0x3eec5  ldarg.s  6
0x3eec7  brtrue.s loc_3EED7
0x3eec9  ldloc.2
0x3eeca  ldloc.0
0x3eecb  ldloc.1
0x3eecc  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.InstallerUpdateOptionsProvider::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerUpdateOptionsProviderServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.CommandLine.ISelectedPackageParser selectedPackageParser, class Microsoft.VisualStudio.Setup.Installer.CommandLine.IPathParser pathParser)
0x3eed1  stloc.s  5
0x3eed3  ldloc.s  5
0x3eed5  br.s     loc_3EEE1
0x3eed7  ldloc.2
0x3eed8  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.BatchInstallerUpdateOptionsProvider::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerUpdateOptionsProviderServiceOptions serviceOptions)
0x3eedd  stloc.s  5
0x3eedf  ldloc.s  5
0x3eee1  stloc.3
0x3eee2  ldarg.1
0x3eee3  ldnull
0x3eee4  call     bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions::op_Inequality(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions)
0x3eee9  brfalse.s loc_3EF00
0x3eeeb  ldarg.0
0x3eeec  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3eef1  ldarg.2
0x3eef2  ldloc.3
0x3eef3  ldarg.1
0x3eef4  ldarg.3
0x3eef5  ldarg.s  5
0x3eef7  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdater::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerService installerService, class Microsoft.VisualStudio.Setup.Installer.CommandLine.IInstallerUpdateOptionsProvider optionsProvider, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions installerOptions, class Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel updateInfo, class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext installerTelemetryContext)
0x3eefc  stloc.s  4
0x3eefe  br.s     loc_3EF14
0x3ef00  ldarg.0
0x3ef01  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ef06  ldarg.2
0x3ef07  ldloc.3
0x3ef08  ldarg.s  4
0x3ef0a  ldarg.3
0x3ef0b  ldarg.s  5
0x3ef0d  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdater::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerService installerService, class Microsoft.VisualStudio.Setup.Installer.CommandLine.IInstallerUpdateOptionsProvider optionsProvider, class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase commandLineOptions, class Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel updateInfo, class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext installerTelemetryContext)
0x3ef12  stloc.s  4
0x3ef14  ldarg.0
0x3ef15  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ef1a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x3ef1f  dup
0x3ef20  brtrue.s loc_3EF25
0x3ef22  pop
0x3ef23  br.s     loc_3EF44
0x3ef25  ldstr    aCreatedA0// "Created a {0}"
0x3ef2a  ldc.i4.1
0x3ef2b  newarr   [mscorlib]System.Object
0x3ef30  dup
0x3ef31  ldc.i4.0
0x3ef32  ldloc.s  4
0x3ef34  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3ef39  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3ef3e  stelem.ref
0x3ef3f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x3ef44  ldarg.0
0x3ef45  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ef4a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x3ef4f  dup
0x3ef50  brtrue.s loc_3EF55
0x3ef52  pop
0x3ef53  br.s     loc_3EF7C
0x3ef55  ldstr    aDecorating0Wit// "Decorating {0} with {1}"
0x3ef5a  ldc.i4.2
0x3ef5b  newarr   [mscorlib]System.Object
0x3ef60  dup
0x3ef61  ldc.i4.0
0x3ef62  ldloc.s  4
0x3ef64  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3ef69  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3ef6e  stelem.ref
0x3ef6f  dup
0x3ef70  ldc.i4.1
0x3ef71  ldstr    aInstalleropera// "InstallerOperationTelemetryDecorator"
0x3ef76  stelem.ref
0x3ef77  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x3ef7c  ldarg.0
0x3ef7d  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ef82  ldloc.s  4
0x3ef84  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::UpdateInstallerEvent
0x3ef89  ldarg.s  5
0x3ef8b  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerOperationTelemetryDecorator::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions serviceOptions, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller installer, string eventName, class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext telemetryContext)
0x3ef90  ret
```
