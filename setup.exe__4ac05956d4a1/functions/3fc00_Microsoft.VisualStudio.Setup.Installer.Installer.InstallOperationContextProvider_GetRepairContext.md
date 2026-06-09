# Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::GetRepairContext

- ea: `0x3fc00`
- end: `0x3fcc9`
- name: `Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::GetRepairContext`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0xa0b0`
- `0x2c4a0`
- `0x2c4b0`
- `0x3a8b0`
- `0x3a8c0`
- `0x3c6e0`
- `0x3c780`
- `0x3fc00`
- `0x403e0`
- `0x405a0`
- `0x40690`
- `0x408a0`
- `0x408f0`
- `0x40970`
- `0x40980`
- `0x40990`

## string_xrefs

- `0x3fca4`: `Product Repair Options: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3fc00  ldarg.0
0x3fc01  ldarg.2
0x3fc02  call     instance string Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::GetSessionId(class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContextOptions options)
0x3fc07  stloc.0
0x3fc08  ldarg.2
0x3fc09  callvirt instance class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext Microsoft.VisualStudio.Setup.Installer.Installer.OperationContextOptions::get_InstallerTelemetryContext()
0x3fc0e  dup
0x3fc0f  brtrue.s loc_3FC35
0x3fc11  pop
0x3fc12  ldarg.0
0x3fc13  ldc.i4.5
0x3fc14  ldarg.1
0x3fc15  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductIdentityModel::get_InstallationPath()
0x3fc1a  ldarg.1
0x3fc1b  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductIdentityModel::get_InstallationPath()
0x3fc20  ldloc.0
0x3fc21  ldc.i4.0
0x3fc22  ldc.i4.0
0x3fc23  ldc.i4.0
0x3fc24  ldc.i4.0
0x3fc25  ldarg.2
0x3fc26  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Installer.OperationContextOptions::get_FromCommandLine()
0x3fc2b  ldc.i4.0
0x3fc2c  ldc.i4.0
0x3fc2d  ldc.i4.0
0x3fc2e  ldnull
0x3fc2f  ldc.i4.0
0x3fc30  call     instance class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::GetTelemetryContext(valuetype Microsoft.VisualStudio.Setup.Installer.UserExecuteAction action, string defaultInstallationPath, string installationPath, string installSessionId, bool packageCacheSettingModified, bool isFocusedUi, bool selectedMissingPackage, bool selectedConfigPackage, bool fromCommandLine, bool previewUpdate, bool fromImport, bool isFromAvailableTab, string removeOos, bool selectedAllPackages)
0x3fc35  stloc.1
0x3fc36  ldarg.0
0x3fc37  ldarg.1
0x3fc38  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductIdentityModel::get_InstallationPath()
0x3fc3d  ldloc.0
0x3fc3e  ldnull
0x3fc3f  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::GetResumeArguments(string installationPath, string installSessionId, [opt] string productKey)
0x3fc44  stloc.2
0x3fc45  ldarg.1
0x3fc46  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductIdentityModel::get_InstanceId()
0x3fc4b  stloc.3
0x3fc4c  ldloc.2
0x3fc4d  ldloc.3
0x3fc4e  ldarg.1
0x3fc4f  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductIdentityModel::get_InstallationPath()
0x3fc54  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductRepairerOptions::.ctor(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments, string, string)
0x3fc59  dup
0x3fc5a  ldloc.1
0x3fc5b  ldarg.0
0x3fc5c  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallOperationContextProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::serviceOptions
0x3fc61  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Telemetry()
0x3fc66  call     valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.TelemetryContext Microsoft.VisualStudio.Setup.Installer.Extensions::GetEngineTelemetryContext(class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext installerTelemetryContext, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry telemetry)
0x3fc6b  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions::set_TelemetryContext(valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.TelemetryContext)
0x3fc70  dup
0x3fc71  ldarg.2
0x3fc72  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Installer.OperationContextOptions::get_KeepWindowsUpdateOn()
0x3fc77  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions::set_KeepWindowsUpdateOn(bool)
0x3fc7c  stloc.s  4
0x3fc7e  ldnull
0x3fc7f  ldloc.3
0x3fc80  ldloc.2
0x3fc81  ldc.i4.0
0x3fc82  call     T0x2B000032
0x3fc87  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::.ctor(string installerPath, string instanceId, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments resumeArguments, valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.OperationMode downloadThenInstall, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> installerFlight)
0x3fc8c  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::GetStandardOptionsLogContent()
0x3fc91  stloc.s  5
0x3fc93  ldarg.0
0x3fc94  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallOperationContextProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::serviceOptions
0x3fc99  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x3fc9e  dup
0x3fc9f  brtrue.s loc_3FCA4
0x3fca1  pop
0x3fca2  br.s     loc_3FCB9
0x3fca4  ldstr    aProductRepairO// "Product Repair Options: {0}"
0x3fca9  ldc.i4.1
0x3fcaa  newarr   [mscorlib]System.Object
0x3fcaf  dup
0x3fcb0  ldc.i4.0
0x3fcb1  ldloc.s  5
0x3fcb3  stelem.ref
0x3fcb4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x3fcb9  ldloc.s  4
0x3fcbb  ldarg.1
0x3fcbc  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext::.ctor(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions options, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel product)
0x3fcc1  dup
0x3fcc2  ldloc.1
0x3fcc3  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext::set_InstallerTelemetryContext(class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext value)
0x3fcc8  ret
```
