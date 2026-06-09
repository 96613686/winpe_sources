# <HandleInstallAsync>d__14::MoveNext

- ea: `0x8c010`
- end: `0x8c3c7`
- name: `<HandleInstallAsync>d__14::MoveNext`
- size: `951`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `installer_update`

## callees

- `0x21b50`
- `0x2bb50`
- `0x2bc20`
- `0x2c300`
- `0x2cd40`
- `0x35ba0`
- `0x363c0`
- `0x3a740`
- `0x3b5a0`
- `0x3dcf0`
- `0x53c50`
- `0x555c0`
- `0x55630`
- `0x59280`
- `0x593a0`
- `0x59400`
- `0x595a0`
- `0x5a680`
- `0x5abf0`
- `0x5adf0`
- `0x5aea0`
- `0x5aee0`
- `0x5af20`
- `0x8c010`

## string_xrefs

- `0x8c06a`: `Attempting an automatic migration.`

## pseudocode

```c

```

## disassembly

```asm
0x8c010  ldarg.0
0x8c011  ldfld    int32 <HandleInstallAsync>d__14::<>1__state
0x8c016  stloc.0
0x8c017  ldarg.0
0x8c018  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler <HandleInstallAsync>d__14::<>4__this
0x8c01d  stloc.1
0x8c01e  ldloc.0
0x8c01f  switch   loc_8C0C3, loc_8C171, loc_8C1F1, loc_8C28C, loc_8C374
0x8c038  ldloc.1
0x8c039  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::serviceOptions
0x8c03e  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IMigrationEligibilityService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_MigrationEligibilityService()
0x8c043  ldarg.0
0x8c044  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel <HandleInstallAsync>d__14::product
0x8c049  ldarg.0
0x8c04a  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions <HandleInstallAsync>d__14::options
0x8c04f  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Services.IMigrationEligibilityService::ShouldTriggerAutoMigration(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel product, class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions installOptions)
0x8c054  brfalse  loc_8C10E
0x8c059  ldloc.1
0x8c05a  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::serviceOptions
0x8c05f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_Logger()
0x8c064  dup
0x8c065  brtrue.s loc_8C06A
0x8c067  pop
0x8c068  br.s     loc_8C079
0x8c06a  ldstr    aAttemptingAnAu// "Attempting an automatic migration."
0x8c06f  call     T0x2B000010
0x8c074  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x8c079  ldloc.1
0x8c07a  ldarg.0
0x8c07b  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions <HandleInstallAsync>d__14::options
0x8c080  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::HandleMigrationAsync(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions options)
0x8c085  ldc.i4.0
0x8c086  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0x8c08b  stloc.s  6
0x8c08d  ldloca.s 6
0x8c08f  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0x8c094  stloc.s  5
0x8c096  ldloca.s 5
0x8c098  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::get_IsCompleted()
0x8c09d  brtrue.s loc_8C0E0
0x8c09f  ldarg.0
0x8c0a0  ldc.i4.0
0x8c0a1  dup
0x8c0a2  stloc.0
0x8c0a3  stfld    int32 <HandleInstallAsync>d__14::<>1__state
0x8c0a8  ldarg.0
0x8c0a9  ldloc.s  5
0x8c0ab  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <HandleInstallAsync>d__14::<>u__1
0x8c0b0  ldarg.0
0x8c0b1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleInstallAsync>d__14::<>t__builder
0x8c0b6  ldloca.s 5
0x8c0b8  ldarg.0
0x8c0b9  call     T0x2B0005DE
0x8c0be  leave    loc_8C3C6
0x8c0c3  ldarg.0
0x8c0c4  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <HandleInstallAsync>d__14::<>u__1
0x8c0c9  stloc.s  5
0x8c0cb  ldarg.0
0x8c0cc  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <HandleInstallAsync>d__14::<>u__1
0x8c0d1  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>
0x8c0d7  ldarg.0
0x8c0d8  ldc.i4.m1
0x8c0d9  dup
0x8c0da  stloc.0
0x8c0db  stfld    int32 <HandleInstallAsync>d__14::<>1__state
0x8c0e0  ldloca.s 5
0x8c0e2  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::GetResult()
0x8c0e7  brfalse.s loc_8C0EE
0x8c0e9  leave    loc_8C3B3
0x8c0ee  ldloc.1
0x8c0ef  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::serviceOptions
0x8c0f4  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_Logger()
0x8c0f9  dup
0x8c0fa  brtrue.s loc_8C0FF
0x8c0fc  pop
0x8c0fd  br.s     loc_8C10E
0x8c0ff  ldstr    aAutomaticMigra// "Automatic migration bypassed."
0x8c104  call     T0x2B000010
0x8c109  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x8c10e  ldarg.0
0x8c10f  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel <HandleInstallAsync>d__14::product
0x8c114  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Channel()
0x8c119  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel::get_IsRetired()
0x8c11e  brfalse.s loc_8C19A
0x8c120  ldarg.0
0x8c121  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions <HandleInstallAsync>d__14::options
0x8c126  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_LayoutPath()
0x8c12b  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x8c130  brfalse.s loc_8C19A
0x8c132  ldloc.1
0x8c133  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::serviceOptions
0x8c138  call     class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::ShowRetiredChannelError(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions serviceOptions)
0x8c13d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x8c142  stloc.s  7
0x8c144  ldloca.s 7
0x8c146  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x8c14b  brtrue.s loc_8C18E
0x8c14d  ldarg.0
0x8c14e  ldc.i4.1
0x8c14f  dup
0x8c150  stloc.0
0x8c151  stfld    int32 <HandleInstallAsync>d__14::<>1__state
0x8c156  ldarg.0
0x8c157  ldloc.s  7
0x8c159  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleInstallAsync>d__14::<>u__2
0x8c15e  ldarg.0
0x8c15f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleInstallAsync>d__14::<>t__builder
0x8c164  ldloca.s 7
0x8c166  ldarg.0
0x8c167  call     T0x2B0005DF
0x8c16c  leave    loc_8C3C6
0x8c171  ldarg.0
0x8c172  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleInstallAsync>d__14::<>u__2
0x8c177  stloc.s  7
0x8c179  ldarg.0
0x8c17a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleInstallAsync>d__14::<>u__2
0x8c17f  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x8c185  ldarg.0
0x8c186  ldc.i4.m1
0x8c187  dup
0x8c188  stloc.0
0x8c189  stfld    int32 <HandleInstallAsync>d__14::<>1__state
0x8c18e  ldloca.s 7
0x8c190  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x8c195  leave    loc_8C3B3
0x8c19a  ldarg.0
0x8c19b  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel <HandleInstallAsync>d__14::product
0x8c1a0  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.ApplicabilityModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel::get_Applicability()
0x8c1a5  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.ApplicabilityModel::get_IsApplicable()
0x8c1aa  brtrue.s loc_8C21A
0x8c1ac  ldloc.1
0x8c1ad  ldarg.0
0x8c1ae  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel <HandleInstallAsync>d__14::product
0x8c1b3  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.ApplicabilityModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel::get_Applicability()
0x8c1b8  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::ShowNotApplicableProductError(class Microsoft.VisualStudio.Setup.Installer.Models.ApplicabilityModel applicability)
0x8c1bd  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x8c1c2  stloc.s  7
0x8c1c4  ldloca.s 7
0x8c1c6  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x8c1cb  brtrue.s loc_8C20E
0x8c1cd  ldarg.0
0x8c1ce  ldc.i4.2
0x8c1cf  dup
0x8c1d0  stloc.0
0x8c1d1  stfld    int32 <HandleInstallAsync>d__14::<>1__state
0x8c1d6  ldarg.0
0x8c1d7  ldloc.s  7
0x8c1d9  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleInstallAsync>d__14::<>u__2
0x8c1de  ldarg.0
0x8c1df  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleInstallAsync>d__14::<>t__builder
0x8c1e4  ldloca.s 7
0x8c1e6  ldarg.0
0x8c1e7  call     T0x2B0005DF
0x8c1ec  leave    loc_8C3C6
0x8c1f1  ldarg.0
0x8c1f2  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleInstallAsync>d__14::<>u__2
0x8c1f7  stloc.s  7
0x8c1f9  ldarg.0
0x8c1fa  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleInstallAsync>d__14::<>u__2
0x8c1ff  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x8c205  ldarg.0
0x8c206  ldc.i4.m1
0x8c207  dup
0x8c208  stloc.0
0x8c209  stfld    int32 <HandleInstallAsync>d__14::<>1__state
0x8c20e  ldloca.s 7
0x8c210  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x8c215  leave    loc_8C3B3
0x8c21a  ldarg.0
0x8c21b  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions <HandleInstallAsync>d__14::options
0x8c220  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_Continue()
0x8c225  brfalse  loc_8C2B5
0x8c22a  ldarg.0
0x8c22b  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions <HandleInstallAsync>d__14::options
0x8c230  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions::get_InstallerOnlyUpdate()
0x8c235  brtrue.s loc_8C2B5
0x8c237  ldloc.1
0x8c238  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.IInstallerUpdateContinueHandler Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::continueHandler
0x8c23d  ldarg.0
0x8c23e  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions <HandleInstallAsync>d__14::options
0x8c243  ldarg.0
0x8c244  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel <HandleInstallAsync>d__14::product
0x8c249  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.IInstallerUpdateContinueHandler::HandleInstallAsync(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions installOptions, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel productSummary)
0x8c24e  ldc.i4.0
0x8c24f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x8c254  stloc.s  9
0x8c256  ldloca.s 9
0x8c258  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x8c25d  stloc.s  8
0x8c25f  ldloca.s 8
0x8c261  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x8c266  brtrue.s loc_8C2A9
0x8c268  ldarg.0
0x8c269  ldc.i4.3
0x8c26a  dup
0x8c26b  stloc.0
0x8c26c  stfld    int32 <HandleInstallAsync>d__14::<>1__state
0x8c271  ldarg.0
0x8c272  ldloc.s  8
0x8c274  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleInstallAsync>d__14::<>u__3
0x8c279  ldarg.0
0x8c27a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleInstallAsync>d__14::<>t__builder
0x8c27f  ldloca.s 8
0x8c281  ldarg.0
0x8c282  call     T0x2B0005E0
0x8c287  leave    loc_8C3C6
0x8c28c  ldarg.0
0x8c28d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleInstallAsync>d__14::<>u__3
0x8c292  stloc.s  8
0x8c294  ldarg.0
0x8c295  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleInstallAsync>d__14::<>u__3
0x8c29a  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x8c2a0  ldarg.0
0x8c2a1  ldc.i4.m1
0x8c2a2  dup
0x8c2a3  stloc.0
0x8c2a4  stfld    int32 <HandleInstallAsync>d__14::<>1__state
0x8c2a9  ldloca.s 8
0x8c2ab  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x8c2b0  leave    loc_8C3B3
0x8c2b5  ldloc.1
0x8c2b6  ldarg.0
0x8c2b7  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions <HandleInstallAsync>d__14::options
0x8c2bc  call     instance class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ISelectionInitializer Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::GetSelectionInitializer(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions options)
0x8c2c1  stloc.2
0x8c2c2  ldloc.1
0x8c2c3  ldarg.0
0x8c2c4  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions <HandleInstallAsync>d__14::options
0x8c2c9  ldarg.0
0x8c2ca  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel <HandleInstallAsync>d__14::product
0x8c2cf  ldarg.0
0x8c2d0  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel <HandleInstallAsync>d__14::product
0x8c2d5  ldarg.0
0x8c2d6  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions <HandleInstallAsync>d__14::options
0x8c2db  call     bool Microsoft.VisualStudio.Setup.Installer.Utilities.Utilities::GetDefaultIncludeRecommendedOnUpdateSetting(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel product, class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions options)
0x8c2e0  ldloc.2
0x8c2e1  ldarg.0
0x8c2e2  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions <HandleInstallAsync>d__14::options
0x8c2e7  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_Config()
0x8c2ec  ldnull
0x8c2ed  call     instance class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::CreateInstallDetailsProvider(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions options, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel product, bool includeRecommended, [opt] class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ISelectionInitializer selectionInitializer, [opt] string configPath, [opt] string migrateFrom)
0x8c2f2  stloc.3
0x8c2f3  ldloc.1
0x8c2f4  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::serviceOptions
0x8c2f9  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallationDetailsServiceOptions::.ctor(class [mscorlib]System.IServiceProvider services)
0x8c2fe  ldarg.0
0x8c2ff  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel <HandleInstallAsync>d__14::product
0x8c304  ldloc.1
0x8c305  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.ICommandHandler`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase> Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::installerUpdateCommand
0x8c30a  ldarg.0
0x8c30b  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions <HandleInstallAsync>d__14::options
0x8c310  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Commands.InstallDetailsErrorHandlingCommand::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallationDetailsServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel product, class Microsoft.VisualStudio.Setup.Installer.Commands.ICommandHandler`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase> installerUpdateCommand, class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase commandLineOptions)
0x8c315  stloc.s  4
0x8c317  ldloc.1
0x8c318  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallCommandLineHandler::serviceOptions
0x8c31d  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductCardServiceOptions::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x8c322  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Commands.ViewInstallationDetailsCommand::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductCardServiceOptions serviceOptions)
0x8c327  ldloc.3
0x8c328  ldloc.s  4
0x8c32a  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand`1<var<u1>> class Microsoft.VisualStudio.Setup.Installer.Commands.CommandHandlerBase`1<class [mscorlib]System.Exception>::get_Command()
0x8c32f  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Commands.ViewInstallationDetailsCommandArgs::.ctor(class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.IInstallationDetailsProvider detailsProvider, class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand`1<class [mscorlib]System.Exception> errorHandler)
0x8c334  callvirt instance class [mscorlib]System.Threading.Tasks.Task class Microsoft.VisualStudio.Setup.Installer.Commands.CommandHandlerBase`1<class Microsoft.VisualStudio.Setup.Installer.Commands.ViewInstallationDetailsCommandArgs>::HandleAsync(var<u1>)
0x8c339  ldc.i4.0
0x8c33a  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x8c33f  stloc.s  9
0x8c341  ldloca.s 9
0x8c343  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x8c348  stloc.s  8
0x8c34a  ldloca.s 8
0x8c34c  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x8c351  brtrue.s loc_8C391
0x8c353  ldarg.0
0x8c354  ldc.i4.4
0x8c355  dup
0x8c356  stloc.0
0x8c357  stfld    int32 <HandleInstallAsync>d__14::<>1__state
0x8c35c  ldarg.0
0x8c35d  ldloc.s  8
0x8c35f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleInstallAsync>d__14::<>u__3
0x8c364  ldarg.0
0x8c365  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleInstallAsync>d__14::<>t__builder
0x8c36a  ldloca.s 8
0x8c36c  ldarg.0
0x8c36d  call     T0x2B0005E0
0x8c372  leave.s  loc_8C3C6
0x8c374  ldarg.0
0x8c375  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleInstallAsync>d__14::<>u__3
0x8c37a  stloc.s  8
0x8c37c  ldarg.0
0x8c37d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleInstallAsync>d__14::<>u__3
0x8c382  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x8c388  ldarg.0
0x8c389  ldc.i4.m1
0x8c38a  dup
0x8c38b  stloc.0
0x8c38c  stfld    int32 <HandleInstallAsync>d__14::<>1__state
0x8c391  ldloca.s 8
0x8c393  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x8c398  leave.s  loc_8C3B3
0x8c39a  stloc.s  0xA
  ... truncated ...
```
