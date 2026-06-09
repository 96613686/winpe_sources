# Microsoft.VisualStudio.Setup.Installer.ViewModels.StartingViewModelProvider::GetUpdateDialogViewModel

- ea: `0x12b30`
- end: `0x12d46`
- name: `Microsoft.VisualStudio.Setup.Installer.ViewModels.StartingViewModelProvider::GetUpdateDialogViewModel`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: `installer_update, broker_com_uri`

## callers

- `0x67d50`

## callees

- `0x12b30`
- `0x18b10`
- `0x18b30`
- `0x19ee0`
- `0x2ba00`
- `0x2bb20`
- `0x2bdd0`
- `0x2c460`
- `0x2c7c0`
- `0x2c910`
- `0x2c970`
- `0x2d080`
- `0x2d150`
- `0x2d5d0`
- `0x2d6a0`
- `0x2f480`
- `0x38a70`
- `0x3e880`
- `0x3fbf0`
- `0x50b90`
- `0x50f40`
- `0x510e0`
- `0x51460`
- `0x53b10`
- `0x540f0`
- `0x55360`
- `0x57370`
- `0x57640`
- `0x57f80`
- `0x59280`
- `0x5aff0`
- `0x67e10`
- `0x67e90`
- `0x87330`

## string_xrefs

- `0x12d3b`: `Update dialog requires UpdateOptions`

## pseudocode

```c

```

## disassembly

```asm
0x12b30  newobj   instance void <>c__DisplayClass5_0::.ctor()
0x12b35  stloc.0
0x12b36  ldloc.0
0x12b37  ldarg.1
0x12b38  stfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions <>c__DisplayClass5_0::serviceOptions
0x12b3d  ldloc.0
0x12b3e  ldarg.3
0x12b3f  stfld    class Microsoft.VisualStudio.Setup.Installer.Services.IAppInitializerService <>c__DisplayClass5_0::appInitializer
0x12b44  ldloc.0
0x12b45  ldarg.2
0x12b46  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions
0x12b4b  stfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <>c__DisplayClass5_0::commandLineOptions
0x12b50  ldloc.0
0x12b51  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <>c__DisplayClass5_0::commandLineOptions
0x12b56  brfalse  loc_12D3B
0x12b5b  ldloc.0
0x12b5c  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions <>c__DisplayClass5_0::serviceOptions
0x12b61  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x12b66  stloc.1
0x12b67  ldloc.0
0x12b68  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions <>c__DisplayClass5_0::serviceOptions
0x12b6d  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.DialogFinalCommandServiceOptions::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x12b72  stloc.2
0x12b73  ldloc.0
0x12b74  ldloc.2
0x12b75  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.Commands.DialogFinalCommand::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.DialogFinalCommandServiceOptions serviceOptions)
0x12b7a  stfld    class Microsoft.VisualStudio.Setup.Installer.Dialogs.Commands.DialogFinalCommand <>c__DisplayClass5_0::finalCommand
0x12b7f  ldarg.2
0x12b80  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions
0x12b85  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.NonVerbOptionsLaunchProductArgumentsProvider::.ctor(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions commandLineOptions)
0x12b8a  stloc.3
0x12b8b  ldloc.0
0x12b8c  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions <>c__DisplayClass5_0::serviceOptions
0x12b91  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.LaunchProductCommandServiceOptions::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x12b96  ldloc.3
0x12b97  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Commands.LaunchProductCommand::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.LaunchProductCommandServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.CommandLine.ILaunchProductArgumentsProvider launchProductArgumentsProvider)
0x12b9c  stloc.s  4
0x12b9e  ldloc.0
0x12b9f  ldloc.2
0x12ba0  ldloc.0
0x12ba1  ldfld    class Microsoft.VisualStudio.Setup.Installer.Dialogs.Commands.DialogFinalCommand <>c__DisplayClass5_0::finalCommand
0x12ba6  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand`1<var<u1>> class Microsoft.VisualStudio.Setup.Installer.Commands.CommandHandlerBase`1<class Microsoft.VisualStudio.Setup.Installer.FinalErrorResult>::get_Command()
0x12bab  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.Commands.DialogPausedInstanceCommand::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.DialogFinalCommandServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand`1<class Microsoft.VisualStudio.Setup.Installer.FinalErrorResult> finalCommand)
0x12bb0  stfld    class Microsoft.VisualStudio.Setup.Installer.Dialogs.Commands.DialogPausedInstanceCommand <>c__DisplayClass5_0::pausedCommand
0x12bb5  ldloc.0
0x12bb6  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions <>c__DisplayClass5_0::serviceOptions
0x12bbb  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::.ctor(class [mscorlib]System.IServiceProvider services)
0x12bc0  stloc.s  5
0x12bc2  ldloc.s  5
0x12bc4  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions serviceOptions)
0x12bc9  stloc.s  6
0x12bcb  ldloc.0
0x12bcc  ldloc.s  5
0x12bce  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallOperationContextProviderServiceOptions::.ctor(class [mscorlib]System.IServiceProvider services)
0x12bd3  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallOperationContextProviderServiceOptions serviceOptions)
0x12bd8  stfld    class Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider <>c__DisplayClass5_0::contextProvider
0x12bdd  ldloc.0
0x12bde  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions <>c__DisplayClass5_0::serviceOptions
0x12be3  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateSettingsCommandServiceOptions::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x12be8  ldloc.0
0x12be9  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions <>c__DisplayClass5_0::serviceOptions
0x12bee  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateSettingsCommandServiceOptions::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x12bf3  call     class RpcFactory Microsoft.VisualStudio.Setup.Installer.ChangeChannel.Commands.UpdateSettingsCommand::CreateDefaultFactory(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateSettingsCommandServiceOptions serviceOptions)
0x12bf8  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ChangeChannel.Commands.UpdateSettingsCommand::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateSettingsCommandServiceOptions serviceOptions, class RpcFactory factory)
0x12bfd  stloc.s  7
0x12bff  ldloc.0
0x12c00  ldloc.1
0x12c01  ldloc.s  7
0x12c03  newobj   instance void Microsoft.VisualStudio.Setup.Installer.UpdateDialog.Commands.OpenUpdateSettingsCommand::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.Commands.ICommandHandler`1<class Microsoft.VisualStudio.Setup.Installer.Services.UpdateSettingsOptions> changeChannelCommand)
0x12c08  stfld    class Microsoft.VisualStudio.Setup.Installer.UpdateDialog.Commands.OpenUpdateSettingsCommand <>c__DisplayClass5_0::changeUpdateSettingsCommand
0x12c0d  ldloc.0
0x12c0e  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions <>c__DisplayClass5_0::serviceOptions
0x12c13  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.RestartCommandServiceOptions::.ctor(class [mscorlib]System.IServiceProvider services)
0x12c18  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Commands.RestartCommand::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.RestartCommandServiceOptions serviceOptions)
0x12c1d  stloc.s  8
0x12c1f  ldloc.0
0x12c20  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions <>c__DisplayClass5_0::serviceOptions
0x12c25  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProgressCommandServiceOptions::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x12c2a  pop
0x12c2b  ldloc.0
0x12c2c  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions <>c__DisplayClass5_0::serviceOptions
0x12c31  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::.ctor(class [mscorlib]System.IServiceProvider services)
0x12c36  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Models.Readers.InstallingProductReader::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions serviceOptions)
0x12c3b  stloc.s  9
0x12c3d  ldloc.0
0x12c3e  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions <>c__DisplayClass5_0::serviceOptions
0x12c43  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerViewModelServiceOptions::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x12c48  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Progress.ProgressViewModelFactory::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerViewModelServiceOptions serviceOptions)
0x12c4d  stloc.s  0xA
0x12c4f  ldloc.0
0x12c50  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions <>c__DisplayClass5_0::serviceOptions
0x12c55  ldloc.s  0xA
0x12c57  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.ViewModels.DialogProgressViewModelFactory::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.Progress.IProgressViewModelFactory progressFactory)
0x12c5c  stloc.s  0xB
0x12c5e  ldloc.0
0x12c5f  ldloc.1
0x12c60  ldloc.s  6
0x12c62  ldloc.s  9
0x12c64  ldloc.s  0xB
0x12c66  ldloc.0
0x12c67  ldfld    class Microsoft.VisualStudio.Setup.Installer.Dialogs.Commands.DialogFinalCommand <>c__DisplayClass5_0::finalCommand
0x12c6c  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand`1<var<u1>> class Microsoft.VisualStudio.Setup.Installer.Commands.CommandHandlerBase`1<class Microsoft.VisualStudio.Setup.Installer.FinalErrorResult>::get_Command()
0x12c71  ldloc.s  8
0x12c73  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand Microsoft.VisualStudio.Setup.Installer.Commands.CommandHandlerBase::get_Command()
0x12c78  ldloc.s  4
0x12c7a  ldsfld   class CreateResultHandler <>O::<0>__Create
0x12c7f  dup
0x12c80  brtrue.s loc_12C95
0x12c82  pop
0x12c83  ldnull
0x12c84  ldftn    class Microsoft.VisualStudio.Setup.Installer.Commands.IOperationResultHandler Microsoft.VisualStudio.Setup.Installer.Dialogs.Commands.DialogOperationResultHandler::Create(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand`1<class Microsoft.VisualStudio.Setup.Installer.FinalErrorResult> finalCommand, class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand restartCommand, class Microsoft.VisualStudio.Setup.Installer.Commands.ICommandHandler`1<class Microsoft.VisualStudio.Setup.Installer.Commands.LaunchProductOptions> launchCommand, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstallingProductModel installingProductModel)
0x12c8a  newobj   instance void CreateResultHandler::.ctor(object object, native int method)
0x12c8f  dup
0x12c90  stsfld   class CreateResultHandler <>O::<0>__Create
0x12c95  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.Commands.DialogInstallOperationCommand::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerFactory installerFactory, class Microsoft.VisualStudio.Setup.Installer.Models.Readers.IInstallingProductReader installingProductReader, class Microsoft.VisualStudio.Setup.Installer.Dialogs.ViewModels.IDialogProgressViewModelFactory viewModelFactory, class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand`1<class Microsoft.VisualStudio.Setup.Installer.FinalErrorResult> finalCommand, class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand restartCommand, class Microsoft.VisualStudio.Setup.Installer.Commands.ICommandHandler`1<class Microsoft.VisualStudio.Setup.Installer.Commands.LaunchProductOptions> launchCommand, class CreateResultHandler createResultHandler)
0x12c9a  stfld    class Microsoft.VisualStudio.Setup.Installer.Dialogs.Commands.DialogInstallOperationCommand <>c__DisplayClass5_0::operationCommand
0x12c9f  ldloc.0
0x12ca0  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <>c__DisplayClass5_0::commandLineOptions
0x12ca5  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_Continue()
0x12caa  brfalse.s loc_12D1E
0x12cac  newobj   instance void <>c__DisplayClass5_1::.ctor()
0x12cb1  stloc.s  0xC
0x12cb3  ldloc.s  0xC
0x12cb5  ldloc.0
0x12cb6  stfld    class <>c__DisplayClass5_0 <>c__DisplayClass5_1::CS$<>8__locals1
0x12cbb  ldloc.s  0xC
0x12cbd  ldloc.s  0xC
0x12cbf  ldfld    class <>c__DisplayClass5_0 <>c__DisplayClass5_1::CS$<>8__locals1
0x12cc4  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions <>c__DisplayClass5_0::serviceOptions
0x12cc9  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::.ctor(class [mscorlib]System.IServiceProvider services)
0x12cce  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.SelectedPackageParser::.ctor()
0x12cd3  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.PathParser::.ctor()
0x12cd8  ldloc.s  0xC
0x12cda  ldfld    class <>c__DisplayClass5_0 <>c__DisplayClass5_1::CS$<>8__locals1
0x12cdf  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider <>c__DisplayClass5_0::contextProvider
0x12ce4  ldloc.s  0xC
0x12ce6  ldfld    class <>c__DisplayClass5_0 <>c__DisplayClass5_1::CS$<>8__locals1
0x12ceb  ldfld    class Microsoft.VisualStudio.Setup.Installer.Dialogs.Commands.DialogInstallOperationCommand <>c__DisplayClass5_0::operationCommand
0x12cf0  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.CommandLine.ISelectedPackageParser selectedPackageParser, class Microsoft.VisualStudio.Setup.Installer.CommandLine.IPathParser pathParser, class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallOperationContextProvider contextProvider, class Microsoft.VisualStudio.Setup.Installer.Commands.ICommandHandler`1<class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext> operationHandler)
0x12cf5  stfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler <>c__DisplayClass5_1::continueHandler
0x12cfa  ldloc.s  0xC
0x12cfc  ldfld    class <>c__DisplayClass5_0 <>c__DisplayClass5_1::CS$<>8__locals1
0x12d01  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions <>c__DisplayClass5_0::serviceOptions
0x12d06  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IDispatcher Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Dispatcher()
0x12d0b  ldloc.s  0xC
0x12d0d  ldftn    instance class Microsoft.VisualStudio.Setup.Installer.Dialogs.ViewModels.InstallerUpdateContinuationViewModel <>c__DisplayClass5_1::<GetUpdateDialogViewModel>b__1()
0x12d13  newobj   instance void class [mscorlib]System.Func`1<class Microsoft.VisualStudio.Setup.Installer.Dialogs.ViewModels.InstallerUpdateContinuationViewModel>::.ctor(object, native int)
0x12d18  callvirt T0x2B0000A2
0x12d1d  ret
0x12d1e  ldloc.0
0x12d1f  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions <>c__DisplayClass5_0::serviceOptions
0x12d24  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IDispatcher Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Dispatcher()
0x12d29  ldloc.0
0x12d2a  ldftn    instance class Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel <>c__DisplayClass5_0::<GetUpdateDialogViewModel>b__0()
0x12d30  newobj   instance void class [mscorlib]System.Func`1<class Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel>::.ctor(object, native int)
0x12d35  callvirt T0x2B0000A3
0x12d3a  ret
0x12d3b  ldstr    aUpdateDialogRe// "Update dialog requires UpdateOptions"
0x12d40  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x12d45  throw
```
