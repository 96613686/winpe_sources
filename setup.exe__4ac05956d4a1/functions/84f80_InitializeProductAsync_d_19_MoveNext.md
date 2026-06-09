# <InitializeProductAsync>d__19::MoveNext

- ea: `0x84f80`
- end: `0x8514e`
- name: `<InitializeProductAsync>d__19::MoveNext`
- size: `462`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `installer_update`

## callees

- `0x13b50`
- `0x226d0`
- `0x2c870`
- `0x2d6b0`
- `0x35b40`
- `0x35ba0`
- `0x35bb0`
- `0x363c0`
- `0x3a740`
- `0x3b5a0`
- `0x3b5d0`
- `0x3b650`
- `0x3cb60`
- `0x4c700`
- `0x4c760`
- `0x4c770`
- `0x4c810`
- `0x4c830`
- `0x4c850`
- `0x593a0`
- `0x84f80`

## string_xrefs

- `0x84fbd`: `FocusedInstallViewModel`

## pseudocode

```c

```

## disassembly

```asm
0x84f80  ldarg.0
0x84f81  ldfld    int32 <InitializeProductAsync>d__19::<>1__state
0x84f86  stloc.0
0x84f87  ldarg.0
0x84f88  ldfld    class Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedInstallViewModel <InitializeProductAsync>d__19::<>4__this
0x84f8d  stloc.1
0x84f8e  ldloc.0
0x84f8f  brfalse  loc_8502C
0x84f94  ldloc.1
0x84f95  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedViewModelBase`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::get_Product()
0x84f9a  brtrue   loc_8511F
0x84f9f  ldarg.0
0x84fa0  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionViewModelServiceOptions <InitializeProductAsync>d__19::selectionServiceOptions
0x84fa5  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x84faa  dup
0x84fab  brtrue.s loc_84FB0
0x84fad  pop
0x84fae  br.s     loc_84FC8
0x84fb0  ldstr    aLoadingProduct// "Loading product from {0}"
0x84fb5  ldc.i4.1
0x84fb6  newarr   [mscorlib]System.Object
0x84fbb  dup
0x84fbc  ldc.i4.0
0x84fbd  ldstr    aFocusedinstall// "FocusedInstallViewModel"
0x84fc2  stelem.ref
0x84fc3  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x84fc8  ldloc.1
0x84fc9  ldloc.1
0x84fca  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedInstallViewModel::installOptions
0x84fcf  ldarg.0
0x84fd0  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionViewModelServiceOptions <InitializeProductAsync>d__19::selectionServiceOptions
0x84fd5  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IProductsRepository Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerViewModelServiceOptions::get_ProductsRepository()
0x84fda  call     class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel Microsoft.VisualStudio.Setup.Installer.Utilities.CommandLineUtilities::GetAvailableProductSummary(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions instanceOptions, class Microsoft.VisualStudio.Setup.Installer.Services.IProductsRepository productsRepository)
0x84fdf  call     instance void Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedInstallViewModel::set_ProductSummary(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel value)
0x84fe4  ldarg.0
0x84fe5  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionViewModelServiceOptions <InitializeProductAsync>d__19::selectionServiceOptions
0x84fea  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IProductsRepository Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerViewModelServiceOptions::get_ProductsRepository()
0x84fef  ldloc.1
0x84ff0  call     instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedInstallViewModel::get_ProductSummary()
0x84ff5  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel> Microsoft.VisualStudio.Setup.Installer.Services.IProductsProviderService::GetAvailableProductAsync(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel summary)
0x84ffa  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::GetAwaiter()
0x84fff  stloc.3
0x85000  ldloca.s 3
0x85002  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::get_IsCompleted()
0x85007  brtrue.s loc_85048
0x85009  ldarg.0
0x8500a  ldc.i4.0
0x8500b  dup
0x8500c  stloc.0
0x8500d  stfld    int32 <InitializeProductAsync>d__19::<>1__state
0x85012  ldarg.0
0x85013  ldloc.3
0x85014  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel> <InitializeProductAsync>d__19::<>u__1
0x85019  ldarg.0
0x8501a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeProductAsync>d__19::<>t__builder
0x8501f  ldloca.s 3
0x85021  ldarg.0
0x85022  call     T0x2B00058B
0x85027  leave    loc_8514D
0x8502c  ldarg.0
0x8502d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel> <InitializeProductAsync>d__19::<>u__1
0x85032  stloc.3
0x85033  ldarg.0
0x85034  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel> <InitializeProductAsync>d__19::<>u__1
0x85039  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>
0x8503f  ldarg.0
0x85040  ldc.i4.m1
0x85041  dup
0x85042  stloc.0
0x85043  stfld    int32 <InitializeProductAsync>d__19::<>1__state
0x85048  ldloca.s 3
0x8504a  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::GetResult()
0x8504f  stloc.2
0x85050  ldloc.1
0x85051  ldloc.2
0x85052  callvirt instance void class Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedViewModelBase`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::set_Product(var<u1>)
0x85057  ldloc.1
0x85058  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedViewModelBase`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::get_Product()
0x8505d  ldloc.1
0x8505e  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedInstallViewModel::GetOnSelectionHandler()
0x85064  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x85069  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel::add_SelectionChanged(class [mscorlib]System.Action value)
0x8506e  ldloc.1
0x8506f  call     instance void Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedInstallViewModel::PreSelectLanguage()
0x85074  ldloc.1
0x85075  ldloc.1
0x85076  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedViewModelBase`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::get_Product()
0x8507b  ldloc.1
0x8507c  call     instance string Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedInstallViewModel::GetCachePath()
0x85081  ldloc.1
0x85082  call     instance string Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedInstallViewModel::GetSharedPath()
0x85087  ldloc.1
0x85088  ldloc.1
0x85089  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedViewModelBase`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::get_Product()
0x8508e  call     instance string Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedInstallViewModel::GetInstallPath(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel product)
0x85093  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.ProductInstallSizes Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel::CalculateInstallSize(string, string cachePath, string sharedInstallationPath)
0x85098  call     instance void class Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedViewModelBase`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::set_InstallSizes(class Microsoft.VisualStudio.Setup.Installer.Models.Products.ProductInstallSizes)
0x8509d  ldloc.1
0x8509e  ldloc.1
0x8509f  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedInstallViewModel::<InitializeProductAsync>b__19_0()
0x850a5  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x850aa  ldc.i4.s 9
0x850ac  call     instance void Microsoft.VisualStudio.Setup.Installer.ViewModels.ViewModelBase::InvokeOnDispatcher(class [mscorlib]System.Action action, [opt] valuetype [WindowsBase]System.Windows.Threading.DispatcherPriority priority)
0x850b1  ldloc.1
0x850b2  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedViewModelBase`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::get_Product()
0x850b7  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Channel()
0x850bc  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel::get_IsRetired()
0x850c1  brfalse.s loc_850ED
0x850c3  ldloc.1
0x850c4  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedInstallViewModel::installOptions
0x850c9  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_LayoutPath()
0x850ce  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x850d3  brfalse.s loc_850E2
0x850d5  ldloc.1
0x850d6  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_RetiredChannelWarningMessageForFocusedUi()
0x850db  call     instance void class Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedViewModelBase`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::set_ErrorMessage(string)
0x850e0  br.s     loc_850ED
0x850e2  ldloc.1
0x850e3  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_RetiredChannelWarningMessageForLayoutInstallation()
0x850e8  call     instance void class Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedViewModelBase`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::set_WarningMessage(string)
0x850ed  ldloc.1
0x850ee  call     instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedInstallViewModel::get_ProductSummary()
0x850f3  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.ApplicabilityModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel::get_Applicability()
0x850f8  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.ApplicabilityModel::get_IsApplicable()
0x850fd  brtrue.s loc_8511F
0x850ff  ldloc.1
0x85100  ldloc.1
0x85101  call     instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedInstallViewModel::get_ProductSummary()
0x85106  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.ApplicabilityModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel::get_Applicability()
0x8510b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.ApplicabilityError> Microsoft.VisualStudio.Setup.Installer.Models.ApplicabilityModel::get_Errors()
0x85110  call     T0x2B000234
0x85115  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.ApplicabilityError::get_Message()
0x8511a  call     instance void class Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedViewModelBase`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::set_ErrorMessage(string)
0x8511f  leave.s  loc_8513A
0x85121  stloc.s  4
0x85123  ldarg.0
0x85124  ldc.i4.s 0xFE
0x85126  stfld    int32 <InitializeProductAsync>d__19::<>1__state
0x8512b  ldarg.0
0x8512c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeProductAsync>d__19::<>t__builder
0x85131  ldloc.s  4
0x85133  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x85138  leave.s  loc_8514D
0x8513a  ldarg.0
0x8513b  ldc.i4.s 0xFE
0x8513d  stfld    int32 <InitializeProductAsync>d__19::<>1__state
0x85142  ldarg.0
0x85143  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeProductAsync>d__19::<>t__builder
0x85148  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x8514d  ret
```
