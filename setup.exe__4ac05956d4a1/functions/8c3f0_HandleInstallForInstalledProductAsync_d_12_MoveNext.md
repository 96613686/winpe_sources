# <HandleInstallForInstalledProductAsync>d__12::MoveNext

- ea: `0x8c3f0`
- end: `0x8c756`
- name: `<HandleInstallForInstalledProductAsync>d__12::MoveNext`
- size: `870`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0xa1d0`
- `0xa540`
- `0xa5c0`
- `0xa5d0`
- `0x2bb50`
- `0x2bba0`
- `0x3a7f0`
- `0x3a910`
- `0x3c1b0`
- `0x3ce80`
- `0x59400`
- `0x59ee0`
- `0x59f00`
- `0x5a680`
- `0x5a750`
- `0x5abd0`
- `0x5ad50`
- `0x5ae70`
- `0x8c3f0`

## string_xrefs

- `0x8c536`: `Failed to check for updates in {0} for an installed product: {1}`
- `0x8c543`: `InstallCommandLineHandler`

## pseudocode

```c

```

## disassembly

```asm
0x8c3f0  ldarg.0
0x8c3f1  ldfld    int32 <HandleInstallForInstalledProductAsync>d__12::<>1__state
0x8c3f6  stloc.0
0x8c3f7  ldarg.0
0x8c3f8  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler <HandleInstallForInstalledProductAsync>d__12::<>4__this
0x8c3fd  stloc.1
0x8c3fe  ldloc.0
0x8c3ff  switch   loc_8C471, loc_8C4A9, loc_8C5AD, loc_8C634, loc_8C6E3
0x8c418  ldarg.0
0x8c419  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleInstallForInstalledProductAsync>d__12::installedProduct
0x8c41e  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::IsRebootRequired(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel product)
0x8c423  brfalse.s loc_8C499
0x8c425  ldloc.1
0x8c426  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::serviceOptions
0x8c42b  ldloc.1
0x8c42c  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::rebootCommand
0x8c431  call     class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::ShowRebootRequiredBlocker(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand rebootCommand)
0x8c436  ldc.i4.0
0x8c437  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x8c43c  stloc.3
0x8c43d  ldloca.s 3
0x8c43f  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x8c444  stloc.2
0x8c445  ldloca.s 2
0x8c447  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x8c44c  brtrue.s loc_8C48D
0x8c44e  ldarg.0
0x8c44f  ldc.i4.0
0x8c450  dup
0x8c451  stloc.0
0x8c452  stfld    int32 <HandleInstallForInstalledProductAsync>d__12::<>1__state
0x8c457  ldarg.0
0x8c458  ldloc.2
0x8c459  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleInstallForInstalledProductAsync>d__12::<>u__1
0x8c45e  ldarg.0
0x8c45f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleInstallForInstalledProductAsync>d__12::<>t__builder
0x8c464  ldloca.s 2
0x8c466  ldarg.0
0x8c467  call     T0x2B0005E1
0x8c46c  leave    loc_8C755
0x8c471  ldarg.0
0x8c472  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleInstallForInstalledProductAsync>d__12::<>u__1
0x8c477  stloc.2
0x8c478  ldarg.0
0x8c479  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleInstallForInstalledProductAsync>d__12::<>u__1
0x8c47e  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x8c484  ldarg.0
0x8c485  ldc.i4.m1
0x8c486  dup
0x8c487  stloc.0
0x8c488  stfld    int32 <HandleInstallForInstalledProductAsync>d__12::<>1__state
0x8c48d  ldloca.s 2
0x8c48f  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x8c494  leave    loc_8C742
0x8c499  ldarg.0
0x8c49a  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions <HandleInstallForInstalledProductAsync>d__12::options
0x8c49f  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::ShouldCheckForUpdates(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase options)
0x8c4a4  brfalse  loc_8C55A
0x8c4a9  nop
0x8c4aa  ldloc.0
0x8c4ab  ldc.i4.1
0x8c4ac  beq.s    loc_8C4FE
0x8c4ae  ldarg.0
0x8c4af  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleInstallForInstalledProductAsync>d__12::installedProduct
0x8c4b4  ldloca.s 4
0x8c4b6  initobj  [mscorlib]System.Threading.CancellationToken
0x8c4bc  ldloc.s  4
0x8c4be  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel::CheckForUpdates([opt] valuetype [mscorlib]System.Threading.CancellationToken token)
0x8c4c3  ldc.i4.0
0x8c4c4  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x8c4c9  stloc.3
0x8c4ca  ldloca.s 3
0x8c4cc  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x8c4d1  stloc.2
0x8c4d2  ldloca.s 2
0x8c4d4  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x8c4d9  brtrue.s loc_8C51A
0x8c4db  ldarg.0
0x8c4dc  ldc.i4.1
0x8c4dd  dup
0x8c4de  stloc.0
0x8c4df  stfld    int32 <HandleInstallForInstalledProductAsync>d__12::<>1__state
0x8c4e4  ldarg.0
0x8c4e5  ldloc.2
0x8c4e6  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleInstallForInstalledProductAsync>d__12::<>u__1
0x8c4eb  ldarg.0
0x8c4ec  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleInstallForInstalledProductAsync>d__12::<>t__builder
0x8c4f1  ldloca.s 2
0x8c4f3  ldarg.0
0x8c4f4  call     T0x2B0005E1
0x8c4f9  leave    loc_8C755
0x8c4fe  ldarg.0
0x8c4ff  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleInstallForInstalledProductAsync>d__12::<>u__1
0x8c504  stloc.2
0x8c505  ldarg.0
0x8c506  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleInstallForInstalledProductAsync>d__12::<>u__1
0x8c50b  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x8c511  ldarg.0
0x8c512  ldc.i4.m1
0x8c513  dup
0x8c514  stloc.0
0x8c515  stfld    int32 <HandleInstallForInstalledProductAsync>d__12::<>1__state
0x8c51a  ldloca.s 2
0x8c51c  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x8c521  leave.s  loc_8C55A
0x8c523  stloc.s  5
0x8c525  ldloc.1
0x8c526  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::serviceOptions
0x8c52b  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_Logger()
0x8c530  dup
0x8c531  brtrue.s loc_8C536
0x8c533  pop
0x8c534  br.s     loc_8C558
0x8c536  ldstr    aFailedToCheckF_1// "Failed to check for updates in {0} for "...
0x8c53b  ldc.i4.2
0x8c53c  newarr   [mscorlib]System.Object
0x8c541  dup
0x8c542  ldc.i4.0
0x8c543  ldstr    aInstallcommand// "InstallCommandLineHandler"
0x8c548  stelem.ref
0x8c549  dup
0x8c54a  ldc.i4.1
0x8c54b  ldloc.s  5
0x8c54d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x8c552  stelem.ref
0x8c553  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x8c558  leave.s  loc_8C55A
0x8c55a  ldarg.0
0x8c55b  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleInstallForInstalledProductAsync>d__12::installedProduct
0x8c560  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::ShouldBlockRetiredChannel(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel installedProduct)
0x8c565  brfalse.s loc_8C5D5
0x8c567  ldloc.1
0x8c568  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::serviceOptions
0x8c56d  call     class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::ShowRetiredChannelError(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions serviceOptions)
0x8c572  ldc.i4.0
0x8c573  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x8c578  stloc.3
0x8c579  ldloca.s 3
0x8c57b  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x8c580  stloc.2
0x8c581  ldloca.s 2
0x8c583  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x8c588  brtrue.s loc_8C5C9
0x8c58a  ldarg.0
0x8c58b  ldc.i4.2
0x8c58c  dup
0x8c58d  stloc.0
0x8c58e  stfld    int32 <HandleInstallForInstalledProductAsync>d__12::<>1__state
0x8c593  ldarg.0
0x8c594  ldloc.2
0x8c595  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleInstallForInstalledProductAsync>d__12::<>u__1
0x8c59a  ldarg.0
0x8c59b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleInstallForInstalledProductAsync>d__12::<>t__builder
0x8c5a0  ldloca.s 2
0x8c5a2  ldarg.0
0x8c5a3  call     T0x2B0005E1
0x8c5a8  leave    loc_8C755
0x8c5ad  ldarg.0
0x8c5ae  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleInstallForInstalledProductAsync>d__12::<>u__1
0x8c5b3  stloc.2
0x8c5b4  ldarg.0
0x8c5b5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleInstallForInstalledProductAsync>d__12::<>u__1
0x8c5ba  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x8c5c0  ldarg.0
0x8c5c1  ldc.i4.m1
0x8c5c2  dup
0x8c5c3  stloc.0
0x8c5c4  stfld    int32 <HandleInstallForInstalledProductAsync>d__12::<>1__state
0x8c5c9  ldloca.s 2
0x8c5cb  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x8c5d0  leave    loc_8C742
0x8c5d5  ldarg.0
0x8c5d6  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleInstallForInstalledProductAsync>d__12::installedProduct
0x8c5db  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.UpdateInformationModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_UpdateInformation()
0x8c5e0  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.Products.UpdateInformationModel::get_IsUpdateAvailable()
0x8c5e5  brfalse.s loc_8C65C
0x8c5e7  ldloc.1
0x8c5e8  ldarg.0
0x8c5e9  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleInstallForInstalledProductAsync>d__12::installedProduct
0x8c5ee  ldarg.0
0x8c5ef  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions <HandleInstallForInstalledProductAsync>d__12::options
0x8c5f4  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::HandleProductUpdateAsync(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel installedProduct, class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions options)
0x8c5f9  ldc.i4.0
0x8c5fa  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x8c5ff  stloc.3
0x8c600  ldloca.s 3
0x8c602  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x8c607  stloc.2
0x8c608  ldloca.s 2
0x8c60a  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x8c60f  brtrue.s loc_8C650
0x8c611  ldarg.0
0x8c612  ldc.i4.3
0x8c613  dup
0x8c614  stloc.0
0x8c615  stfld    int32 <HandleInstallForInstalledProductAsync>d__12::<>1__state
0x8c61a  ldarg.0
0x8c61b  ldloc.2
0x8c61c  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleInstallForInstalledProductAsync>d__12::<>u__1
0x8c621  ldarg.0
0x8c622  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleInstallForInstalledProductAsync>d__12::<>t__builder
0x8c627  ldloca.s 2
0x8c629  ldarg.0
0x8c62a  call     T0x2B0005E1
0x8c62f  leave    loc_8C755
0x8c634  ldarg.0
0x8c635  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleInstallForInstalledProductAsync>d__12::<>u__1
0x8c63a  stloc.2
0x8c63b  ldarg.0
0x8c63c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleInstallForInstalledProductAsync>d__12::<>u__1
0x8c641  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x8c647  ldarg.0
0x8c648  ldc.i4.m1
0x8c649  dup
0x8c64a  stloc.0
0x8c64b  stfld    int32 <HandleInstallForInstalledProductAsync>d__12::<>1__state
0x8c650  ldloca.s 2
0x8c652  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x8c657  leave    loc_8C742
0x8c65c  ldarg.0
0x8c65d  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions <HandleInstallForInstalledProductAsync>d__12::options
0x8c662  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.SelectionOptions::get_Add()
0x8c667  call     T0x2B00002F
0x8c66c  brfalse.s loc_8C692
0x8c66e  ldarg.0
0x8c66f  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions <HandleInstallForInstalledProductAsync>d__12::options
0x8c674  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.SelectionOptions::get_Remove()
0x8c679  call     T0x2B00002F
0x8c67e  brfalse.s loc_8C692
0x8c680  ldarg.0
0x8c681  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions <HandleInstallForInstalledProductAsync>d__12::options
0x8c686  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_Config()
0x8c68b  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x8c690  brtrue.s loc_8C709
0x8c692  ldloc.1
0x8c693  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.ICommandLineHandler Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::modifyCommandLineHandler
0x8c698  ldarg.0
0x8c699  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions <HandleInstallForInstalledProductAsync>d__12::options
0x8c69e  call     class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifyOptions Microsoft.VisualStudio.Setup.Installer.Utilities.CommandLineUtilities::ConvertToModify(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions options)
0x8c6a3  ldloca.s 4
0x8c6a5  initobj  [mscorlib]System.Threading.CancellationToken
0x8c6ab  ldloc.s  4
0x8c6ad  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.ICommandLineHandler::HandleAsync(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions options, [opt] valuetype [mscorlib]System.Threading.CancellationToken token)
0x8c6b2  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x8c6b7  stloc.s  6
0x8c6b9  ldloca.s 6
0x8c6bb  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x8c6c0  brtrue.s loc_8C700
0x8c6c2  ldarg.0
0x8c6c3  ldc.i4.4
0x8c6c4  dup
0x8c6c5  stloc.0
0x8c6c6  stfld    int32 <HandleInstallForInstalledProductAsync>d__12::<>1__state
0x8c6cb  ldarg.0
0x8c6cc  ldloc.s  6
0x8c6ce  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleInstallForInstalledProductAsync>d__12::<>u__2
0x8c6d3  ldarg.0
0x8c6d4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleInstallForInstalledProductAsync>d__12::<>t__builder
0x8c6d9  ldloca.s 6
0x8c6db  ldarg.0
0x8c6dc  call     T0x2B0005E2
0x8c6e1  leave.s  loc_8C755
0x8c6e3  ldarg.0
0x8c6e4  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleInstallForInstalledProductAsync>d__12::<>u__2
0x8c6e9  stloc.s  6
0x8c6eb  ldarg.0
0x8c6ec  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleInstallForInstalledProductAsync>d__12::<>u__2
0x8c6f1  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x8c6f7  ldarg.0
0x8c6f8  ldc.i4.m1
0x8c6f9  dup
0x8c6fa  stloc.0
0x8c6fb  stfld    int32 <HandleInstallForInstalledProductAsync>d__12::<>1__state
0x8c700  ldloca.s 6
0x8c702  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x8c707  leave.s  loc_8C742
0x8c709  ldloc.1
0x8c70a  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::serviceOptions
0x8c70f  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_InstallerSettings()
0x8c714  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::IsQuietOrPassive(class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService installerSettings)
0x8c719  brfalse.s loc_8C727
0x8c71b  ldloc.1
0x8c71c  ldarg.0
0x8c71d  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleInstallForInstalledProductAsync>d__12::installedProduct
0x8c722  call     instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::QuitWithProductInstalledError(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel installedProduct)
0x8c727  leave.s  loc_8C742
0x8c729  stloc.s  7
0x8c72b  ldarg.0
0x8c72c  ldc.i4.s 0xFE
0x8c72e  stfld    int32 <HandleInstallForInstalledProductAsync>d__12::<>1__state
0x8c733  ldarg.0
0x8c734  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleInstallForInstalledProductAsync>d__12::<>t__builder
0x8c739  ldloc.s  7
0x8c73b  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x8c740  leave.s  loc_8C755
0x8c742  ldarg.0
0x8c743  ldc.i4.s 0xFE
0x8c745  stfld    int32 <HandleInstallForInstalledProductAsync>d__12::<>1__state
0x8c74a  ldarg.0
0x8c74b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleInstallForInstalledProductAsync>d__12::<>t__builder
  ... truncated ...
```
