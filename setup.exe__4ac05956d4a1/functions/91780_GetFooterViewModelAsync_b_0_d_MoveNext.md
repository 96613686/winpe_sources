# <<GetFooterViewModelAsync>b__0>d::MoveNext

- ea: `0x91780`
- end: `0x919db`
- name: `<<GetFooterViewModelAsync>b__0>d::MoveNext`
- size: `603`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x2d6a0`
- `0x44f00`
- `0x452b0`
- `0x45360`
- `0x453e0`
- `0x463b0`
- `0x47bc0`
- `0x53b10`
- `0x805e0`
- `0x91780`

## string_xrefs

- `0x917d2`: `FooterViewModel cannot be created twice with different DetailsPageViewModel`
- `0x91800`: `Tab view models need to be created before footer view model for InstallDetailsProvider.`

## pseudocode

```c

```

## disassembly

```asm
0x91780  ldarg.0
0x91781  ldfld    int32 <<GetFooterViewModelAsync>b__0>d::<>1__state
0x91786  stloc.0
0x91787  ldarg.0
0x91788  ldfld    class <>c__DisplayClass46_0 <<GetFooterViewModelAsync>b__0>d::<>4__this
0x9178d  stloc.1
0x9178e  ldloc.0
0x9178f  brfalse  loc_91895
0x91794  ldloc.0
0x91795  ldc.i4.1
0x91796  beq      loc_918F7
0x9179b  ldarg.0
0x9179c  newobj   instance void <>c__DisplayClass46_1::.ctor()
0x917a1  stfld    class <>c__DisplayClass46_1 <<GetFooterViewModelAsync>b__0>d::<>8__1
0x917a6  ldarg.0
0x917a7  ldfld    class <>c__DisplayClass46_1 <<GetFooterViewModelAsync>b__0>d::<>8__1
0x917ac  ldloc.1
0x917ad  stfld    class <>c__DisplayClass46_0 <>c__DisplayClass46_1::CS$<>8__locals1
0x917b2  ldloc.1
0x917b3  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider <>c__DisplayClass46_0::<>4__this
0x917b8  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.IInstallationDetailsPageViewModel Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider::detailsPageViewModel
0x917bd  brfalse.s loc_917DD
0x917bf  ldloc.1
0x917c0  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider <>c__DisplayClass46_0::<>4__this
0x917c5  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.IInstallationDetailsPageViewModel Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider::detailsPageViewModel
0x917ca  ldloc.1
0x917cb  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.IInstallationDetailsPageViewModel <>c__DisplayClass46_0::detailsPageViewModel
0x917d0  beq.s    loc_917DD
0x917d2  ldstr    aFooterviewmode_0// "FooterViewModel cannot be created twice"...
0x917d7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x917dc  throw
0x917dd  ldloc.1
0x917de  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider <>c__DisplayClass46_0::<>4__this
0x917e3  ldloc.1
0x917e4  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.IInstallationDetailsPageViewModel <>c__DisplayClass46_0::detailsPageViewModel
0x917e9  stfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.IInstallationDetailsPageViewModel Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider::detailsPageViewModel
0x917ee  ldloc.1
0x917ef  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider <>c__DisplayClass46_0::<>4__this
0x917f4  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.IInstallationDetailsPageViewModel Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider::detailsPageViewModel
0x917f9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ViewModels.ITabbedViewModel> Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.IInstallationDetailsPageViewModel::get_TabViewModels()
0x917fe  brtrue.s loc_9180B
0x91800  ldstr    aTabViewModelsN// "Tab view models need to be created befo"...
0x91805  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9180a  throw
0x9180b  ldarg.0
0x9180c  ldfld    class <>c__DisplayClass46_1 <<GetFooterViewModelAsync>b__0>d::<>8__1
0x91811  ldloc.1
0x91812  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider <>c__DisplayClass46_0::<>4__this
0x91817  ldloc.1
0x91818  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider <>c__DisplayClass46_0::<>4__this
0x9181d  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.IInstallationDetailsPageViewModel Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider::detailsPageViewModel
0x91822  ldloc.1
0x91823  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider <>c__DisplayClass46_0::<>4__this
0x91828  ldfld    int32 Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider::advancedSettingsTabIndex
0x9182d  call     instance class Microsoft.VisualStudio.Setup.Installer.Commands.RelayCommand Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider::GetOpenAdvancedSettingsCommand(class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.IInstallationDetailsPageViewModel, int32 detailsPageViewModel)
0x91832  stfld    class Microsoft.VisualStudio.Setup.Installer.Commands.RelayCommand <>c__DisplayClass46_1::openAdvancedSettingsCommand
0x91837  ldloc.1
0x91838  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider <>c__DisplayClass46_0::<>4__this
0x9183d  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.IInstallationDetailsPageViewModel Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider::detailsPageViewModel
0x91842  ldloc.1
0x91843  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider <>c__DisplayClass46_0::<>4__this
0x91848  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider::OnDetailsPageChanged(object sender, class [System]System.ComponentModel.PropertyChangedEventArgs e)
0x9184e  newobj   instance void [System]System.ComponentModel.PropertyChangedEventHandler::.ctor(object, native int)
0x91853  callvirt instance void [System]System.ComponentModel.INotifyPropertyChanged::add_PropertyChanged(class [System]System.ComponentModel.PropertyChangedEventHandler)
0x91858  ldloc.1
0x91859  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider <>c__DisplayClass46_0::<>4__this
0x9185e  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider::InitializeAsync()
0x91863  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x91868  stloc.3
0x91869  ldloca.s 3
0x9186b  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x91870  brtrue.s loc_918B1
0x91872  ldarg.0
0x91873  ldc.i4.0
0x91874  dup
0x91875  stloc.0
0x91876  stfld    int32 <<GetFooterViewModelAsync>b__0>d::<>1__state
0x9187b  ldarg.0
0x9187c  ldloc.3
0x9187d  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<GetFooterViewModelAsync>b__0>d::<>u__1
0x91882  ldarg.0
0x91883  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.IFooterViewModel> <<GetFooterViewModelAsync>b__0>d::<>t__builder
0x91888  ldloca.s 3
0x9188a  ldarg.0
0x9188b  call     T0x2B000616
0x91890  leave    loc_919DA
0x91895  ldarg.0
0x91896  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<GetFooterViewModelAsync>b__0>d::<>u__1
0x9189b  stloc.3
0x9189c  ldarg.0
0x9189d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<GetFooterViewModelAsync>b__0>d::<>u__1
0x918a2  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x918a8  ldarg.0
0x918a9  ldc.i4.m1
0x918aa  dup
0x918ab  stloc.0
0x918ac  stfld    int32 <<GetFooterViewModelAsync>b__0>d::<>1__state
0x918b1  ldloca.s 3
0x918b3  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x918b8  ldloc.1
0x918b9  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider <>c__DisplayClass46_0::<>4__this
0x918be  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel> Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider::GetProductAsync()
0x918c3  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::GetAwaiter()
0x918c8  stloc.s  5
0x918ca  ldloca.s 5
0x918cc  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::get_IsCompleted()
0x918d1  brtrue.s loc_91914
0x918d3  ldarg.0
0x918d4  ldc.i4.1
0x918d5  dup
0x918d6  stloc.0
0x918d7  stfld    int32 <<GetFooterViewModelAsync>b__0>d::<>1__state
0x918dc  ldarg.0
0x918dd  ldloc.s  5
0x918df  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel> <<GetFooterViewModelAsync>b__0>d::<>u__2
0x918e4  ldarg.0
0x918e5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.IFooterViewModel> <<GetFooterViewModelAsync>b__0>d::<>t__builder
0x918ea  ldloca.s 5
0x918ec  ldarg.0
0x918ed  call     T0x2B000617
0x918f2  leave    loc_919DA
0x918f7  ldarg.0
0x918f8  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel> <<GetFooterViewModelAsync>b__0>d::<>u__2
0x918fd  stloc.s  5
0x918ff  ldarg.0
0x91900  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel> <<GetFooterViewModelAsync>b__0>d::<>u__2
0x91905  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>
0x9190b  ldarg.0
0x9190c  ldc.i4.m1
0x9190d  dup
0x9190e  stloc.0
0x9190f  stfld    int32 <<GetFooterViewModelAsync>b__0>d::<>1__state
0x91914  ldloca.s 5
0x91916  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel>::GetResult()
0x9191b  stloc.s  4
0x9191d  ldarg.0
0x9191e  ldfld    class <>c__DisplayClass46_1 <<GetFooterViewModelAsync>b__0>d::<>8__1
0x91923  ldloc.s  4
0x91925  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel <>c__DisplayClass46_1::product
0x9192a  ldarg.0
0x9192b  ldfld    class <>c__DisplayClass46_1 <<GetFooterViewModelAsync>b__0>d::<>8__1
0x91930  ldloc.1
0x91931  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider <>c__DisplayClass46_0::<>4__this
0x91936  ldarg.0
0x91937  ldfld    class <>c__DisplayClass46_1 <<GetFooterViewModelAsync>b__0>d::<>8__1
0x9193c  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel <>c__DisplayClass46_1::product
0x91941  call     instance class Microsoft.VisualStudio.Setup.Installer.Models.IInstallationSettingsModel Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider::GetSettingsModel(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel product)
0x91946  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.IInstallationSettingsModel <>c__DisplayClass46_1::settingsModel
0x9194b  ldarg.0
0x9194c  ldfld    class <>c__DisplayClass46_1 <<GetFooterViewModelAsync>b__0>d::<>8__1
0x91951  ldarg.0
0x91952  ldfld    class <>c__DisplayClass46_1 <<GetFooterViewModelAsync>b__0>d::<>8__1
0x91957  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductModel <>c__DisplayClass46_1::product
0x9195c  ldloc.1
0x9195d  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider <>c__DisplayClass46_0::<>4__this
0x91962  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallationDetailsServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider::serviceOptions
0x91967  newobj   instance void Microsoft.VisualStudio.Setup.Installer.InstallationDetails.RemoveOosCommand::.ctor(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel product, class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallationDetailsServiceOptions serviceOptions)
0x9196c  call     instance class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand Microsoft.VisualStudio.Setup.Installer.Commands.CommandHandlerBase::get_Command()
0x91971  stfld    class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand <>c__DisplayClass46_1::removeOosCommand
0x91976  ldloc.1
0x91977  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider <>c__DisplayClass46_0::<>4__this
0x9197c  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallationDetailsServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.InstallDetailsProvider::serviceOptions
0x91981  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IDispatcher Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Dispatcher()
0x91986  ldarg.0
0x91987  ldfld    class <>c__DisplayClass46_1 <<GetFooterViewModelAsync>b__0>d::<>8__1
0x9198c  ldftn    instance class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.InstallationDetailsFooterViewModel <>c__DisplayClass46_1::<GetFooterViewModelAsync>b__1()
0x91992  newobj   instance void class [mscorlib]System.Func`1<class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.InstallationDetailsFooterViewModel>::.ctor(object, native int)
0x91997  callvirt T0x2B000565
0x9199c  stloc.2
0x9199d  leave.s  loc_919BF
0x9199f  stloc.s  6
0x919a1  ldarg.0
0x919a2  ldc.i4.s 0xFE
0x919a4  stfld    int32 <<GetFooterViewModelAsync>b__0>d::<>1__state
0x919a9  ldarg.0
0x919aa  ldnull
0x919ab  stfld    class <>c__DisplayClass46_1 <<GetFooterViewModelAsync>b__0>d::<>8__1
0x919b0  ldarg.0
0x919b1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.IFooterViewModel> <<GetFooterViewModelAsync>b__0>d::<>t__builder
0x919b6  ldloc.s  6
0x919b8  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.IFooterViewModel>::SetException(class [mscorlib]System.Exception)
0x919bd  leave.s  loc_919DA
0x919bf  ldarg.0
0x919c0  ldc.i4.s 0xFE
0x919c2  stfld    int32 <<GetFooterViewModelAsync>b__0>d::<>1__state
0x919c7  ldarg.0
0x919c8  ldnull
0x919c9  stfld    class <>c__DisplayClass46_1 <<GetFooterViewModelAsync>b__0>d::<>8__1
0x919ce  ldarg.0
0x919cf  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.IFooterViewModel> <<GetFooterViewModelAsync>b__0>d::<>t__builder
0x919d4  ldloc.2
0x919d5  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.IFooterViewModel>::SetResult(var<u1>)
0x919da  ret
```
