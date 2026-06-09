# <<InitializeAsync>b__15_0>d::MoveNext

- ea: `0x698d0`
- end: `0x69f8f`
- name: `<<InitializeAsync>b__15_0>d::MoveNext`
- size: `1727`
- prototype: ``
- caller_count: `0`
- callee_count: `41`
- tags: `installer_update`

## callees

- `0xa1d0`
- `0xa1f0`
- `0xaf80`
- `0x11650`
- `0x11a90`
- `0x11f30`
- `0x19a30`
- `0x19ab0`
- `0x19ae0`
- `0x19af0`
- `0x19b00`
- `0x19b30`
- `0x19b50`
- `0x19c50`
- `0x21620`
- `0x21780`
- `0x22670`
- `0x229b0`
- `0x229c0`
- `0x22cb0`
- `0x2b710`
- `0x2b750`
- `0x2c870`
- `0x2d650`
- `0x2d670`
- `0x2d6a0`
- `0x2d6b0`
- `0x2d6c0`
- `0x363c0`
- `0x3a7c0`
- `0x3a7f0`
- `0x3a870`
- `0x3a8c0`
- `0x3b5a0`
- `0x3c1b0`
- `0x3cbe0`
- `0x3cd20`
- `0x54080`
- `0x55080`
- `0x698d0`
- `0x6a0d0`

## string_xrefs

- `0x699df`: `Update page status: {0}`
- `0x69ccc`: `Update page status: {0}`
- `0x69d4e`: `Update page status: {0}`
- `0x69c42`: `UpdateInformation`
- `0x699ec`: `CheckingForUpdate`
- `0x69c35`: `{0}: Update available`
- `0x69cd9`: `UpdateAvailable`
- `0x69d5b`: `NoUpdate`
- `0x69d82`: `No update available`
- `0x69dfc`: `No update available`
- `0x69dd1`: `Update check was cancelled`
- `0x69e84`: `Update check was cancelled`
- `0x69e1e`: `Failed to check for updates`
- `0x69eef`: `Failed to initialize the update dialog: {0}`
- `0x69f15`: `Failed to initialize update dialog`
- `0x69f1c`: `Failed to initialize the update dialog`

## pseudocode

```c

```

## disassembly

```asm
0x698d0  ldarg.0
0x698d1  ldfld    int32 <<InitializeAsync>b__15_0>d::<>1__state
0x698d6  stloc.0
0x698d7  ldarg.0
0x698d8  ldfld    class Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel <<InitializeAsync>b__15_0>d::<>4__this
0x698dd  stloc.1
0x698de  ldloc.0
0x698df  ldc.i4.2
0x698e0  ble.un.s loc_698F7
0x698e2  ldloc.1
0x698e3  ldc.i4.1
0x698e4  call     instance void Microsoft.VisualStudio.Setup.Installer.ViewModels.LoadingViewModelBase::set_IsLoading(bool value)
0x698e9  ldloc.1
0x698ea  ldc.i4.1
0x698eb  call     instance void Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::set_Status(valuetype Microsoft.VisualStudio.Setup.Installer.ViewModels.SetupPageStatus value)
0x698f0  ldarg.0
0x698f1  ldnull
0x698f2  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <<InitializeAsync>b__15_0>d::<telemetryOperation>5__2
0x698f7  nop
0x698f8  ldloc.0
0x698f9  ldc.i4.2
0x698fa  ble.un.s loc_6992A
0x698fc  ldarg.0
0x698fd  ldarg.0
0x698fe  ldloc.1
0x698ff  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::serviceOptions
0x69904  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Telemetry()
0x69909  dup
0x6990a  brtrue.s loc_69910
0x6990c  pop
0x6990d  ldnull
0x6990e  br.s     loc_6991D
0x69910  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::PerfInitializeUpdateDialogEvent
0x69915  ldnull
0x69916  ldc.i4.0
0x69917  ldc.i4.0
0x69918  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x6991d  dup
0x6991e  stloc.2
0x6991f  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <<InitializeAsync>b__15_0>d::<telemetryOperation>5__2
0x69924  ldloc.2
0x69925  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <<InitializeAsync>b__15_0>d::<>7__wrap2
0x6992a  nop
0x6992b  ldloc.0
0x6992c  brfalse.s loc_69995
0x6992e  ldloc.0
0x6992f  ldc.i4.1
0x69930  sub
0x69931  ldc.i4.1
0x69932  ble.un   loc_69A47
0x69937  ldarg.0
0x69938  newobj   instance void <>c__DisplayClass15_0::.ctor()
0x6993d  stfld    class <>c__DisplayClass15_0 <<InitializeAsync>b__15_0>d::<>8__1
0x69942  ldarg.0
0x69943  ldfld    class <>c__DisplayClass15_0 <<InitializeAsync>b__15_0>d::<>8__1
0x69948  ldloc.1
0x69949  stfld    class Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel <>c__DisplayClass15_0::<>4__this
0x6994e  ldloc.1
0x6994f  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.IAppInitializerService Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::appInitializer
0x69954  ldloca.s 4
0x69956  initobj  [mscorlib]System.Threading.CancellationToken
0x6995c  ldloc.s  4
0x6995e  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.Services.IAppInitializerService::InitializeAsync([opt] valuetype [mscorlib]System.Threading.CancellationToken token)
0x69963  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x69968  stloc.3
0x69969  ldloca.s 3
0x6996b  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x69970  brtrue.s loc_699B1
0x69972  ldarg.0
0x69973  ldc.i4.0
0x69974  dup
0x69975  stloc.0
0x69976  stfld    int32 <<InitializeAsync>b__15_0>d::<>1__state
0x6997b  ldarg.0
0x6997c  ldloc.3
0x6997d  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<InitializeAsync>b__15_0>d::<>u__1
0x69982  ldarg.0
0x69983  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<InitializeAsync>b__15_0>d::<>t__builder
0x69988  ldloca.s 3
0x6998a  ldarg.0
0x6998b  call     T0x2B000444
0x69990  leave    loc_69F8E
0x69995  ldarg.0
0x69996  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<InitializeAsync>b__15_0>d::<>u__1
0x6999b  stloc.3
0x6999c  ldarg.0
0x6999d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<InitializeAsync>b__15_0>d::<>u__1
0x699a2  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x699a8  ldarg.0
0x699a9  ldc.i4.m1
0x699aa  dup
0x699ab  stloc.0
0x699ac  stfld    int32 <<InitializeAsync>b__15_0>d::<>1__state
0x699b1  ldloca.s 3
0x699b3  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x699b8  ldarg.0
0x699b9  ldfld    class <>c__DisplayClass15_0 <<InitializeAsync>b__15_0>d::<>8__1
0x699be  ldloc.1
0x699bf  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::serviceOptions
0x699c4  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateViewModelServiceOptions::.ctor(class [mscorlib]System.IServiceProvider provider)
0x699c9  stfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateViewModelServiceOptions <>c__DisplayClass15_0::updateServiceOptions
0x699ce  ldloc.1
0x699cf  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::serviceOptions
0x699d4  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x699d9  dup
0x699da  brtrue.s loc_699DF
0x699dc  pop
0x699dd  br.s     loc_699F7
0x699df  ldstr    aUpdatePageStat// "Update page status: {0}"
0x699e4  ldc.i4.1
0x699e5  newarr   [mscorlib]System.Object
0x699ea  dup
0x699eb  ldc.i4.0
0x699ec  ldstr    aCheckingforupd// "CheckingForUpdate"
0x699f1  stelem.ref
0x699f2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x699f7  ldarg.0
0x699f8  ldloc.1
0x699f9  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::updateOptions
0x699fe  call     bool Microsoft.VisualStudio.Setup.Installer.Utilities.CommandLineUtilities::IsQuietOrPassive(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions options)
0x69a03  stfld    bool <<InitializeAsync>b__15_0>d::<isQuietOrPassive>5__4
0x69a08  ldloc.1
0x69a09  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::tokenSource
0x69a0e  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x69a13  stloc.s  4
0x69a15  ldloca.s 4
0x69a17  call     instance bool [mscorlib]System.Threading.CancellationToken::get_IsCancellationRequested()
0x69a1c  brtrue   loc_69E6B
0x69a21  ldarg.0
0x69a22  ldloc.1
0x69a23  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::tokenSource
0x69a28  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x69a2d  stloc.s  4
0x69a2f  ldloca.s 4
0x69a31  ldloc.1
0x69a32  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::<InitializeAsync>b__15_1()
0x69a38  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x69a3d  call     instance valuetype [mscorlib]System.Threading.CancellationTokenRegistration [mscorlib]System.Threading.CancellationToken::Register(class [mscorlib]System.Action)
0x69a42  stfld    valuetype [mscorlib]System.Threading.CancellationTokenRegistration <<InitializeAsync>b__15_0>d::<ctr>5__5
0x69a47  nop
0x69a48  ldloc.0
0x69a49  ldc.i4.1
0x69a4a  beq      loc_69B1C
0x69a4f  ldloc.0
0x69a50  ldc.i4.2
0x69a51  beq      loc_69C8A
0x69a56  ldarg.0
0x69a57  ldloc.1
0x69a58  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::updateOptions
0x69a5d  ldarg.0
0x69a5e  ldfld    class <>c__DisplayClass15_0 <<InitializeAsync>b__15_0>d::<>8__1
0x69a63  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateViewModelServiceOptions <>c__DisplayClass15_0::updateServiceOptions
0x69a68  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IProductsRepository Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerViewModelServiceOptions::get_ProductsRepository()
0x69a6d  call     class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel Microsoft.VisualStudio.Setup.Installer.Utilities.CommandLineUtilities::GetInstalledProductSummary(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions instanceOptions, class Microsoft.VisualStudio.Setup.Installer.Services.IProductsRepository productsRepository)
0x69a72  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <<InitializeAsync>b__15_0>d::<productSummary>5__6
0x69a77  ldloc.1
0x69a78  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_UpdateDialogLicenseText_Args2()
0x69a7d  ldarg.0
0x69a7e  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <<InitializeAsync>b__15_0>d::<productSummary>5__6
0x69a83  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_ThirdPartyNoticesUri()
0x69a88  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LinkIds::UpdateDialogThirdPartyNoticesLinkId
0x69a8d  call     string [mscorlib]System.String::Format(string, object, object)
0x69a92  call     instance void Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::set_LicenseText(string value)
0x69a97  ldarg.0
0x69a98  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <<InitializeAsync>b__15_0>d::<productSummary>5__6
0x69a9d  callvirt instance valuetype Microsoft.VisualStudio.Setup.Installer.Models.Products.ProductInstallState Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_InstallState()
0x69aa2  ldc.i4.3
0x69aa3  bne.un.s loc_69AC3
0x69aa5  ldloc.1
0x69aa6  ldc.i4.0
0x69aa7  call     instance void Microsoft.VisualStudio.Setup.Installer.ViewModels.LoadingViewModelBase::set_IsLoading(bool value)
0x69aac  ldloc.1
0x69aad  ldc.i4.7
0x69aae  call     instance void Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::set_Status(valuetype Microsoft.VisualStudio.Setup.Installer.ViewModels.SetupPageStatus value)
0x69ab3  ldloc.1
0x69ab4  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::pausedCommand
0x69ab9  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand::Execute()
0x69abe  br       loc_69E3E
0x69ac3  ldloc.1
0x69ac4  ldarg.0
0x69ac5  ldfld    class <>c__DisplayClass15_0 <<InitializeAsync>b__15_0>d::<>8__1
0x69aca  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateViewModelServiceOptions <>c__DisplayClass15_0::updateServiceOptions
0x69acf  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IUpdateProviderService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateViewModelServiceOptions::get_UpdateProvider()
0x69ad4  ldarg.0
0x69ad5  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <<InitializeAsync>b__15_0>d::<productSummary>5__6
0x69ada  ldloc.1
0x69adb  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::tokenSource
0x69ae0  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x69ae5  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::CheckForUpdate(class Microsoft.VisualStudio.Setup.Installer.Services.IUpdateProviderService updateProvider, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel product, valuetype [mscorlib]System.Threading.CancellationToken token)
0x69aea  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x69aef  stloc.3
0x69af0  ldloca.s 3
0x69af2  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x69af7  brtrue.s loc_69B38
0x69af9  ldarg.0
0x69afa  ldc.i4.1
0x69afb  dup
0x69afc  stloc.0
0x69afd  stfld    int32 <<InitializeAsync>b__15_0>d::<>1__state
0x69b02  ldarg.0
0x69b03  ldloc.3
0x69b04  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<InitializeAsync>b__15_0>d::<>u__1
0x69b09  ldarg.0
0x69b0a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<InitializeAsync>b__15_0>d::<>t__builder
0x69b0f  ldloca.s 3
0x69b11  ldarg.0
0x69b12  call     T0x2B000444
0x69b17  leave    loc_69F8E
0x69b1c  ldarg.0
0x69b1d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<InitializeAsync>b__15_0>d::<>u__1
0x69b22  stloc.3
0x69b23  ldarg.0
0x69b24  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<InitializeAsync>b__15_0>d::<>u__1
0x69b29  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x69b2f  ldarg.0
0x69b30  ldc.i4.m1
0x69b31  dup
0x69b32  stloc.0
0x69b33  stfld    int32 <<InitializeAsync>b__15_0>d::<>1__state
0x69b38  ldloca.s 3
0x69b3a  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x69b3f  ldarg.0
0x69b40  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <<InitializeAsync>b__15_0>d::<productSummary>5__6
0x69b45  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::ShouldBlockRetiredChannel(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel installedProduct)
0x69b4a  brfalse.s loc_69B57
0x69b4c  ldloc.1
0x69b4d  call     instance void Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::HandleRetiredChannelError()
0x69b52  leave    loc_69F74
0x69b57  nop
0x69b58  ldloc.1
0x69b59  ldarg.0
0x69b5a  ldfld    class <>c__DisplayClass15_0 <<InitializeAsync>b__15_0>d::<>8__1
0x69b5f  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateViewModelServiceOptions <>c__DisplayClass15_0::updateServiceOptions
0x69b64  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IProductsRepository Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerViewModelServiceOptions::get_ProductsRepository()
0x69b69  ldarg.0
0x69b6a  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <<InitializeAsync>b__15_0>d::<productSummary>5__6
0x69b6f  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductIdentityModel::get_InstallationPath()
0x69b74  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel Microsoft.VisualStudio.Setup.Installer.Services.IProductsProviderService::GetInstalledProductSummary(string)
0x69b79  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::product
0x69b7e  leave.s  loc_69BC6
0x69b80  stloc.s  5
0x69b82  ldloc.1
0x69b83  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::serviceOptions
0x69b88  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x69b8d  dup
0x69b8e  brtrue.s loc_69B93
0x69b90  pop
0x69b91  br.s     loc_69BB8
0x69b93  ldstr    aFailedToRetrie// "Failed to retrieve full product, fall b"...
0x69b98  ldc.i4.0
0x69b99  box      [mscorlib]System.Int32
0x69b9e  call     string [mscorlib]System.String::Format(string, object)
0x69ba3  ldc.i4.1
0x69ba4  newarr   [mscorlib]System.Object
0x69ba9  dup
0x69baa  ldc.i4.0
0x69bab  ldloc.s  5
0x69bad  callvirt instance string [mscorlib]System.Exception::get_Message()
0x69bb2  stelem.ref
0x69bb3  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x69bb8  ldloc.1
0x69bb9  ldarg.0
0x69bba  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <<InitializeAsync>b__15_0>d::<productSummary>5__6
0x69bbf  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::product
0x69bc4  leave.s  loc_69BC6
0x69bc6  ldarg.0
0x69bc7  ldfld    class <>c__DisplayClass15_0 <<InitializeAsync>b__15_0>d::<>8__1
0x69bcc  ldloc.1
0x69bcd  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::OnChangeUpdateSettings()
0x69bd3  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x69bd8  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Commands.RelayCommand::.ctor(class [mscorlib]System.Action execute)
0x69bdd  stfld    class Microsoft.VisualStudio.Setup.Installer.Commands.RelayCommand <>c__DisplayClass15_0::changeSettingsCommand
0x69be2  ldloc.1
0x69be3  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::serviceOptions
0x69be8  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IDispatcher Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Dispatcher()
0x69bed  ldarg.0
0x69bee  ldfld    class <>c__DisplayClass15_0 <<InitializeAsync>b__15_0>d::<>8__1
0x69bf3  ldftn    instance void <>c__DisplayClass15_0::<InitializeAsync>b__2()
0x69bf9  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x69bfe  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.IDispatcher::Invoke(class [mscorlib]System.Action action)
0x69c03  ldloc.1
0x69c04  call     instance valuetype Microsoft.VisualStudio.Setup.Installer.ViewModels.SetupPageStatus Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::get_Status()
0x69c09  ldc.i4.1
0x69c0a  bne.un   loc_69DAC
0x69c0f  ldloc.1
0x69c10  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::product
0x69c15  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.UpdateInformationModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_UpdateInformation()
0x69c1a  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.Products.UpdateInformationModel::get_IsUpdateAvailable()
0x69c1f  brfalse  loc_69D2F
0x69c24  ldloc.1
0x69c25  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::serviceOptions
0x69c2a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x69c2f  dup
0x69c30  brtrue.s loc_69C35
0x69c32  pop
0x69c33  br.s     loc_69C4D
0x69c35  ldstr    a0UpdateAvailab// "{0}: Update available"
0x69c3a  ldc.i4.1
0x69c3b  newarr   [mscorlib]System.Object
0x69c40  dup
  ... truncated ...
```
