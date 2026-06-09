# <InitializeAsync>d__14::MoveNext_0

- ea: `0x8f200`
- end: `0x8f5a6`
- name: `<InitializeAsync>d__14::MoveNext_0`
- size: `934`
- prototype: ``
- caller_count: `0`
- callee_count: `34`
- tags: `registry_config`

## callees

- `0x11f30`
- `0x21b30`
- `0x22660`
- `0x226d0`
- `0x2a090`
- `0x2b860`
- `0x2c870`
- `0x2d6b0`
- `0x2d6d0`
- `0x36c00`
- `0x36e80`
- `0x3a770`
- `0x3a780`
- `0x3b520`
- `0x3b530`
- `0x3b550`
- `0x3b590`
- `0x3b640`
- `0x5d3c0`
- `0x5d410`
- `0x5d490`
- `0x5d4c0`
- `0x5d520`
- `0x5d550`
- `0x5d580`
- `0x5d5b0`
- `0x5d5e0`
- `0x5d630`
- `0x5d640`
- `0x5d770`
- `0x5d800`
- `0x5d8b0`
- `0x5dbf0`
- `0x8f200`

## string_xrefs

- `0x8f2ab`: `RetryingFromConfig`

## pseudocode

```c

```

## disassembly

```asm
0x8f200  ldarg.0
0x8f201  ldfld    int32 <InitializeAsync>d__14::<>1__state
0x8f206  stloc.0
0x8f207  ldarg.0
0x8f208  ldfld    class Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel <InitializeAsync>d__14::<>4__this
0x8f20d  stloc.1
0x8f20e  ldloc.0
0x8f20f  ldc.i4.2
0x8f210  ble.un.s loc_8F224
0x8f212  ldarg.0
0x8f213  ldloc.1
0x8f214  ldsfld   string ChannelMigration::ChannelMigrationInitEvent
0x8f219  ldnull
0x8f21a  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::StartTelemetryOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> eventName)
0x8f21f  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InitializeAsync>d__14::<operation>5__2
0x8f224  nop
0x8f225  ldloc.0
0x8f226  ldc.i4.2
0x8f227  pop
0x8f228  pop
0x8f229  nop
0x8f22a  ldloc.0
0x8f22b  switch   loc_8F274, loc_8F336, loc_8F441
0x8f23c  ldloc.1
0x8f23d  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::<>n__0()
0x8f242  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x8f247  stloc.3
0x8f248  ldloca.s 3
0x8f24a  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x8f24f  brtrue.s loc_8F290
0x8f251  ldarg.0
0x8f252  ldc.i4.0
0x8f253  dup
0x8f254  stloc.0
0x8f255  stfld    int32 <InitializeAsync>d__14::<>1__state
0x8f25a  ldarg.0
0x8f25b  ldloc.3
0x8f25c  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <InitializeAsync>d__14::<>u__1
0x8f261  ldarg.0
0x8f262  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeAsync>d__14::<>t__builder
0x8f267  ldloca.s 3
0x8f269  ldarg.0
0x8f26a  call     T0x2B0005FE
0x8f26f  leave    loc_8F5A5
0x8f274  ldarg.0
0x8f275  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <InitializeAsync>d__14::<>u__1
0x8f27a  stloc.3
0x8f27b  ldarg.0
0x8f27c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <InitializeAsync>d__14::<>u__1
0x8f281  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x8f287  ldarg.0
0x8f288  ldc.i4.m1
0x8f289  dup
0x8f28a  stloc.0
0x8f28b  stfld    int32 <InitializeAsync>d__14::<>1__state
0x8f290  ldloca.s 3
0x8f292  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x8f297  ldloc.1
0x8f298  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::availableProductSummary
0x8f29d  brfalse.s loc_8F2BA
0x8f29f  ldarg.0
0x8f2a0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InitializeAsync>d__14::<operation>5__2
0x8f2a5  dup
0x8f2a6  brtrue.s loc_8F2AB
0x8f2a8  pop
0x8f2a9  br.s     loc_8F2B5
0x8f2ab  ldstr    aRetryingfromco// "RetryingFromConfig"
0x8f2b0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x8f2b5  leave    loc_8F58B
0x8f2ba  ldloc.1
0x8f2bb  ldloc.1
0x8f2bc  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ChannelMigrationPageServiceOptions Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::get_ServiceOptions()
0x8f2c1  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IProductsRepository Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerViewModelServiceOptions::get_ProductsRepository()
0x8f2c6  ldloc.1
0x8f2c7  ldfld    string Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::productId
0x8f2cc  ldloc.1
0x8f2cd  ldfld    class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::channelUpdateUri
0x8f2d2  ldnull
0x8f2d3  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel Microsoft.VisualStudio.Setup.Installer.Services.IProductsProviderService::GetAvailableProductSummary(string, class [System]System.Uri productId, string channelUri)
0x8f2d8  dup
0x8f2d9  brtrue.s loc_8F2E7
0x8f2db  pop
0x8f2dc  ldstr    aExpectedAvaila// "Expected available product summary to m"...
0x8f2e1  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8f2e6  throw
0x8f2e7  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::availableProductSummary
0x8f2ec  ldloc.1
0x8f2ed  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ChannelMigrationPageServiceOptions Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::get_ServiceOptions()
0x8f2f2  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IProductsRepository Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerViewModelServiceOptions::get_ProductsRepository()
0x8f2f7  ldloc.1
0x8f2f8  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::availableProductSummary
0x8f2fd  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel> Microsoft.VisualStudio.Setup.Installer.Services.IProductsProviderService::GetAvailableProductAsync(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel summary)
0x8f302  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::GetAwaiter()
0x8f307  stloc.s  5
0x8f309  ldloca.s 5
0x8f30b  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::get_IsCompleted()
0x8f310  brtrue.s loc_8F353
0x8f312  ldarg.0
0x8f313  ldc.i4.1
0x8f314  dup
0x8f315  stloc.0
0x8f316  stfld    int32 <InitializeAsync>d__14::<>1__state
0x8f31b  ldarg.0
0x8f31c  ldloc.s  5
0x8f31e  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel> <InitializeAsync>d__14::<>u__2
0x8f323  ldarg.0
0x8f324  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeAsync>d__14::<>t__builder
0x8f329  ldloca.s 5
0x8f32b  ldarg.0
0x8f32c  call     T0x2B0005FF
0x8f331  leave    loc_8F5A5
0x8f336  ldarg.0
0x8f337  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel> <InitializeAsync>d__14::<>u__2
0x8f33c  stloc.s  5
0x8f33e  ldarg.0
0x8f33f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel> <InitializeAsync>d__14::<>u__2
0x8f344  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>
0x8f34a  ldarg.0
0x8f34b  ldc.i4.m1
0x8f34c  dup
0x8f34d  stloc.0
0x8f34e  stfld    int32 <InitializeAsync>d__14::<>1__state
0x8f353  ldloca.s 5
0x8f355  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::GetResult()
0x8f35a  stloc.s  4
0x8f35c  ldarg.0
0x8f35d  ldloc.s  4
0x8f35f  dup
0x8f360  brtrue.s loc_8F36E
0x8f362  pop
0x8f363  ldstr    aExpectedAvaila_0// "Expected available product to migrate t"...
0x8f368  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8f36d  throw
0x8f36e  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel <InitializeAsync>d__14::<availableProduct>5__3
0x8f373  ldloc.1
0x8f374  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ChannelMigrationTitle_Args()
0x8f379  ldarg.0
0x8f37a  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel <InitializeAsync>d__14::<availableProduct>5__3
0x8f37f  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.PackageResources Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel::get_Resources()
0x8f384  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.PackageResources::get_Name()
0x8f389  call     string [mscorlib]System.String::Format(string, object)
0x8f38e  call     instance void Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::set_Title(string value)
0x8f393  ldloc.1
0x8f394  ldloc.1
0x8f395  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::availableProductSummary
0x8f39a  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel::get_PromotionText()
0x8f39f  call     instance void Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::set_AdvertisingText(string value)
0x8f3a4  ldloc.1
0x8f3a5  ldloc.1
0x8f3a6  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::availableProductSummary
0x8f3ab  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel::get_PromotionUri()
0x8f3b0  call     instance void Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::set_InstructionMoreInfoLink(class [System]System.Uri value)
0x8f3b5  ldloc.1
0x8f3b6  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ChannelMigrationLicenseText_Args()
0x8f3bb  ldarg.0
0x8f3bc  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel <InitializeAsync>d__14::<availableProduct>5__3
0x8f3c1  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel::get_LicenseUri()
0x8f3c6  ldarg.0
0x8f3c7  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel <InitializeAsync>d__14::<availableProduct>5__3
0x8f3cc  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel::get_ThirdPartyNoticesUri()
0x8f3d1  call     string [mscorlib]System.String::Format(string, object, object)
0x8f3d6  call     instance void Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::set_LicenseText(string value)
0x8f3db  ldloc.1
0x8f3dc  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ChannelMigrationExtensionToolTip_Args()
0x8f3e1  ldarg.0
0x8f3e2  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel <InitializeAsync>d__14::<availableProduct>5__3
0x8f3e7  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.PackageResources Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel::get_Resources()
0x8f3ec  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.PackageResources::get_Name()
0x8f3f1  call     string [mscorlib]System.String::Format(string, object)
0x8f3f6  call     instance void Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::set_ExtensionToolTip(string value)
0x8f3fb  ldloc.1
0x8f3fc  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ChannelMigrationPageServiceOptions Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::get_ServiceOptions()
0x8f401  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.Features.IFeatureService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_FeatureService()
0x8f406  ldc.i4.s 0x10
0x8f408  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.VisualStudio.Setup.Installer.Services.Features.IFeatureService::IsEnabledAsync(valuetype Microsoft.VisualStudio.Setup.Installer.Services.Features.FeatureFlag feature)
0x8f40d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x8f412  stloc.s  7
0x8f414  ldloca.s 7
0x8f416  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x8f41b  brtrue.s loc_8F45E
0x8f41d  ldarg.0
0x8f41e  ldc.i4.2
0x8f41f  dup
0x8f420  stloc.0
0x8f421  stfld    int32 <InitializeAsync>d__14::<>1__state
0x8f426  ldarg.0
0x8f427  ldloc.s  7
0x8f429  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <InitializeAsync>d__14::<>u__3
0x8f42e  ldarg.0
0x8f42f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeAsync>d__14::<>t__builder
0x8f434  ldloca.s 7
0x8f436  ldarg.0
0x8f437  call     T0x2B000600
0x8f43c  leave    loc_8F5A5
0x8f441  ldarg.0
0x8f442  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <InitializeAsync>d__14::<>u__3
0x8f447  stloc.s  7
0x8f449  ldarg.0
0x8f44a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <InitializeAsync>d__14::<>u__3
0x8f44f  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x8f455  ldarg.0
0x8f456  ldc.i4.m1
0x8f457  dup
0x8f458  stloc.0
0x8f459  stfld    int32 <InitializeAsync>d__14::<>1__state
0x8f45e  ldloca.s 7
0x8f460  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x8f465  stloc.s  6
0x8f467  ldloc.1
0x8f468  ldloc.s  6
0x8f46a  call     instance void Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::set_ExtensionMigrationFeatureEnabled(bool value)
0x8f46f  ldloc.1
0x8f470  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ChannelMigrationPageServiceOptions Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::get_ServiceOptions()
0x8f475  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IMigrationEligibilityService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ChannelMigrationPageServiceOptions::get_MigrationEligibilityService()
0x8f47a  ldarg.0
0x8f47b  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel <InitializeAsync>d__14::<availableProduct>5__3
0x8f480  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.VersionBundle Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel::get_Versions()
0x8f485  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Installer.Models.VersionBundle::get_BuildVersion()
0x8f48a  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x8f48f  ldarg.0
0x8f490  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel <InitializeAsync>d__14::<availableProduct>5__3
0x8f495  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Id()
0x8f49a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel> Microsoft.VisualStudio.Setup.Installer.Services.IMigrationEligibilityService::GetEligibleMigrationSources(int32 targetMajorVersion, string targetProductId)
0x8f49f  ldloc.1
0x8f4a0  ldftn    instance class Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.InstanceMigrationCandidateViewModel Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::<InitializeAsync>b__14_0(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel x)
0x8f4a6  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel, class Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.InstanceMigrationCandidateViewModel>::.ctor(object, native int)
0x8f4ab  call     T0x2B000601
0x8f4b0  stloc.2
0x8f4b1  ldloc.1
0x8f4b2  ldloc.2
0x8f4b3  newobj   instance void class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.IInstanceMigrationCandidateViewModel>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x8f4b8  call     instance void Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::set_MigrationCandidateList(class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.IInstanceMigrationCandidateViewModel> value)
0x8f4bd  ldloc.1
0x8f4be  ldloc.1
0x8f4bf  call     instance class Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.IInstanceMigrationCandidateViewModel Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::SelectMigrationCandidateBasedOnClonePath()
0x8f4c4  call     instance void Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::set_SelectedMigrationCandidate(class Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.IInstanceMigrationCandidateViewModel value)
0x8f4c9  ldloc.1
0x8f4ca  call     instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::get_MigrateFromInstanceEnabled()
0x8f4cf  brtrue.s loc_8F4E0
0x8f4d1  ldloc.1
0x8f4d2  call     instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::get_MigrateFromConfiguration()
0x8f4d7  brtrue.s loc_8F4E0
0x8f4d9  ldloc.1
0x8f4da  ldc.i4.1
0x8f4db  call     instance void Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::set_NewInstallation(bool value)
0x8f4e0  ldarg.0
0x8f4e1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InitializeAsync>d__14::<operation>5__2
0x8f4e6  dup
0x8f4e7  brtrue.s loc_8F4EC
0x8f4e9  pop
0x8f4ea  br.s     loc_8F4F6
0x8f4ec  ldstr    aInitialized// "Initialized"
0x8f4f1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x8f4f6  ldarg.0
0x8f4f7  ldnull
0x8f4f8  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel <InitializeAsync>d__14::<availableProduct>5__3
0x8f4fd  leave.s  loc_8F543
0x8f4ff  stloc.s  8
0x8f501  ldloc.1
0x8f502  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ChannelMigrationPageServiceOptions Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::get_ServiceOptions()
0x8f507  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x8f50c  dup
0x8f50d  brtrue.s loc_8F512
0x8f50f  pop
0x8f510  br.s     loc_8F523
0x8f512  ldloc.s  8
0x8f514  ldstr    aFailedToInitia_7// "Failed to initialize the Channel Migrat"...
0x8f519  call     T0x2B000010
0x8f51e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x8f523  ldarg.0
0x8f524  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InitializeAsync>d__14::<operation>5__2
0x8f529  dup
0x8f52a  brtrue.s loc_8F52F
0x8f52c  pop
0x8f52d  br.s     loc_8F541
0x8f52f  ldstr    aFailedToInitia_7// "Failed to initialize the Channel Migrat"...
0x8f534  ldloc.s  8
0x8f536  ldstr    aChannelMigrati_1// "Channel Migration Page Init Error"
0x8f53b  ldc.i4.1
0x8f53c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x8f541  rethrow
0x8f543  leave.s  loc_8F551
0x8f545  ldloc.0
0x8f546  ldc.i4.0
0x8f547  bge.s    loc_8F550
0x8f549  ldloc.1
0x8f54a  ldc.i4.0
0x8f54b  call     instance void Microsoft.VisualStudio.Setup.Installer.ViewModels.LoadingViewModelBase::set_IsLoading(bool value)
0x8f550  endfinally
0x8f551  leave.s  loc_8F58B
0x8f553  ldloc.0
0x8f554  ldc.i4.0
0x8f555  bge.s    loc_8F56A
0x8f557  ldarg.0
0x8f558  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InitializeAsync>d__14::<operation>5__2
0x8f55d  brfalse.s loc_8F56A
0x8f55f  ldarg.0
0x8f560  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InitializeAsync>d__14::<operation>5__2
0x8f565  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8f56a  endfinally
  ... truncated ...
```
