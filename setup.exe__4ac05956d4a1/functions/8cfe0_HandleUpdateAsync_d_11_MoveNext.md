# <HandleUpdateAsync>d__11::MoveNext

- ea: `0x8cfe0`
- end: `0x8d1aa`
- name: `<HandleUpdateAsync>d__11::MoveNext`
- size: `458`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0xace0`
- `0x2bb50`
- `0x3cdd0`
- `0x3e440`
- `0x41510`
- `0x41600`
- `0x41620`
- `0x41640`
- `0x41660`
- `0x41690`
- `0x59320`
- `0x59340`
- `0x593a0`
- `0x593e0`
- `0x5a280`
- `0x5a2c0`
- `0x5a2e0`
- `0x5a320`
- `0x5a380`
- `0x5a3a0`
- `0x5a4c0`
- `0x5b250`
- `0x8cfe0`

## string_xrefs

- `0x8d032`: `Unable to parse the WUProgressCBClsID: `

## pseudocode

```c

```

## disassembly

```asm
0x8cfe0  ldarg.0
0x8cfe1  ldfld    int32 <HandleUpdateAsync>d__11::<>1__state
0x8cfe6  stloc.0
0x8cfe7  ldarg.0
0x8cfe8  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler <HandleUpdateAsync>d__11::<>4__this
0x8cfed  stloc.1
0x8cfee  ldloc.0
0x8cfef  brfalse  loc_8D157
0x8cff4  ldarg.0
0x8cff5  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleUpdateAsync>d__11::updateOptions
0x8cffa  call     valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.OperationMode> Microsoft.VisualStudio.Setup.Installer.Utilities.CommandLineUtilities::GetOperationMode(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase options)
0x8cfff  stloc.2
0x8d000  ldarg.0
0x8d001  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleUpdateAsync>d__11::updateOptions
0x8d006  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions::get_WUProgressCBClsID()
0x8d00b  ldloca.s 3
0x8d00d  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x8d012  brtrue.s loc_8D051
0x8d014  ldarg.0
0x8d015  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleUpdateAsync>d__11::updateOptions
0x8d01a  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions::get_WUProgressCBClsID()
0x8d01f  brfalse.s loc_8D051
0x8d021  ldloc.1
0x8d022  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler::serviceOptions
0x8d027  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_Logger()
0x8d02c  dup
0x8d02d  brtrue.s loc_8D032
0x8d02f  pop
0x8d030  br.s     loc_8D051
0x8d032  ldstr    aUnableToParseT// "Unable to parse the WUProgressCBClsID: "
0x8d037  ldarg.0
0x8d038  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleUpdateAsync>d__11::updateOptions
0x8d03d  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions::get_WUProgressCBClsID()
0x8d042  call     string [mscorlib]System.String::Concat(string, string)
0x8d047  call     T0x2B000010
0x8d04c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x8d051  ldloc.1
0x8d052  ldarg.0
0x8d053  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleUpdateAsync>d__11::updateOptions
0x8d058  ldarg.0
0x8d059  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleUpdateAsync>d__11::updateOptions
0x8d05e  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions::get_FocusedUi()
0x8d063  call     instance class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler::GetInstallerTelemetryContext(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase options, bool isFocusedUi)
0x8d068  ldloc.2
0x8d069  ldarg.0
0x8d06a  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleUpdateAsync>d__11::updateOptions
0x8d06f  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions::get_ProductKey()
0x8d074  ldarg.0
0x8d075  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleUpdateAsync>d__11::updateOptions
0x8d07a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions::get_VisualStudioFlight()
0x8d07f  ldarg.0
0x8d080  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleUpdateAsync>d__11::updateOptions
0x8d085  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_LayoutPath()
0x8d08a  ldarg.0
0x8d08b  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleUpdateAsync>d__11::updateOptions
0x8d090  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions::get_InstallLayoutPath()
0x8d095  ldarg.0
0x8d096  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleUpdateAsync>d__11::updateOptions
0x8d09b  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_LayoutUri()
0x8d0a0  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::.ctor(class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext installerTelemetryContext, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.OperationMode> operationMode, string productKey, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> vsFlights, string layoutPath, string installLayoutPath, class [System]System.Uri layoutUri)
0x8d0a5  dup
0x8d0a6  ldarg.0
0x8d0a7  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleUpdateAsync>d__11::updateOptions
0x8d0ac  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ChannelUri()
0x8d0b1  ldc.i4.0
0x8d0b2  call     class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Extensions::SafeToUri(string uriString, [opt] valuetype [System]System.UriKind uriKind)
0x8d0b7  callvirt instance modreq(System.Runtime.CompilerServices.IsExternalInit) void Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::set_ChannelUri(class [System]System.Uri value)
0x8d0bc  dup
0x8d0bd  ldarg.0
0x8d0be  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleUpdateAsync>d__11::updateOptions
0x8d0c3  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_InstallChannelUri()
0x8d0c8  ldc.i4.0
0x8d0c9  call     class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Extensions::SafeToUri(string uriString, [opt] valuetype [System]System.UriKind uriKind)
0x8d0ce  callvirt instance modreq(System.Runtime.CompilerServices.IsExternalInit) void Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::set_InstallChannelUri(class [System]System.Uri value)
0x8d0d3  dup
0x8d0d4  ldarg.0
0x8d0d5  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleUpdateAsync>d__11::updateOptions
0x8d0da  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions::get_InstallCatalogUri()
0x8d0df  ldc.i4.0
0x8d0e0  call     class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Extensions::SafeToUri(string uriString, [opt] valuetype [System]System.UriKind uriKind)
0x8d0e5  callvirt instance modreq(System.Runtime.CompilerServices.IsExternalInit) void Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::set_InstallCatalogUri(class [System]System.Uri value)
0x8d0ea  dup
0x8d0eb  ldarg.0
0x8d0ec  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleUpdateAsync>d__11::updateOptions
0x8d0f1  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions::get_UpdateVersion()
0x8d0f6  callvirt instance modreq(System.Runtime.CompilerServices.IsExternalInit) void Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::set_UpdateVersion(class [mscorlib]System.Version value)
0x8d0fb  dup
0x8d0fc  ldloc.3
0x8d0fd  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::set_WUProgressCBClsID(valuetype [mscorlib]System.Guid value)
0x8d102  stloc.s  4
0x8d104  ldloc.1
0x8d105  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallOperationContextProvider Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler::contextProvider
0x8d10a  ldarg.0
0x8d10b  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleUpdateAsync>d__11::productSummary
0x8d110  ldloc.s  4
0x8d112  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext Microsoft.VisualStudio.Setup.Installer.Installer.IInstallOperationContextProvider::GetUpdateContext(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel installedProduct, class Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions options)
0x8d117  stloc.s  5
0x8d119  ldloc.1
0x8d11a  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.ICommandHandler`1<class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext> Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler::operationHandler
0x8d11f  ldloc.s  5
0x8d121  callvirt instance class [mscorlib]System.Threading.Tasks.Task class Microsoft.VisualStudio.Setup.Installer.Commands.ICommandHandler`1<class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext>::HandleAsync(var<u1>)
0x8d126  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x8d12b  stloc.s  6
0x8d12d  ldloca.s 6
0x8d12f  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x8d134  brtrue.s loc_8D174
0x8d136  ldarg.0
0x8d137  ldc.i4.0
0x8d138  dup
0x8d139  stloc.0
0x8d13a  stfld    int32 <HandleUpdateAsync>d__11::<>1__state
0x8d13f  ldarg.0
0x8d140  ldloc.s  6
0x8d142  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleUpdateAsync>d__11::<>u__1
0x8d147  ldarg.0
0x8d148  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleUpdateAsync>d__11::<>t__builder
0x8d14d  ldloca.s 6
0x8d14f  ldarg.0
0x8d150  call     T0x2B0005E8
0x8d155  leave.s  loc_8D1A9
0x8d157  ldarg.0
0x8d158  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleUpdateAsync>d__11::<>u__1
0x8d15d  stloc.s  6
0x8d15f  ldarg.0
0x8d160  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleUpdateAsync>d__11::<>u__1
0x8d165  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x8d16b  ldarg.0
0x8d16c  ldc.i4.m1
0x8d16d  dup
0x8d16e  stloc.0
0x8d16f  stfld    int32 <HandleUpdateAsync>d__11::<>1__state
0x8d174  ldloca.s 6
0x8d176  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x8d17b  leave.s  loc_8D196
0x8d17d  stloc.s  7
0x8d17f  ldarg.0
0x8d180  ldc.i4.s 0xFE
0x8d182  stfld    int32 <HandleUpdateAsync>d__11::<>1__state
0x8d187  ldarg.0
0x8d188  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleUpdateAsync>d__11::<>t__builder
0x8d18d  ldloc.s  7
0x8d18f  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x8d194  leave.s  loc_8D1A9
0x8d196  ldarg.0
0x8d197  ldc.i4.s 0xFE
0x8d199  stfld    int32 <HandleUpdateAsync>d__11::<>1__state
0x8d19e  ldarg.0
0x8d19f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleUpdateAsync>d__11::<>t__builder
0x8d1a4  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x8d1a9  ret
```
