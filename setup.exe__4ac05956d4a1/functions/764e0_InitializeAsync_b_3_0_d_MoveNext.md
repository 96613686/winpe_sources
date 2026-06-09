# <<InitializeAsync>b__3_0>d::MoveNext

- ea: `0x764e0`
- end: `0x76602`
- name: `<<InitializeAsync>b__3_0>d::MoveNext`
- size: `290`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update`

## callees

- `0xa470`
- `0x11a90`
- `0x11f30`
- `0x19480`
- `0x2c7f0`
- `0x2d650`
- `0x2d6b0`
- `0x33e70`
- `0x33ea0`
- `0x33eb0`
- `0x764e0`

## string_xrefs

- `0x7658c`: `Failed to check for update for current instance: {0}`
- `0x765b6`: ` ProductCardUpdateMainPageViewModel`

## pseudocode

```c

```

## disassembly

```asm
0x764e0  ldarg.0
0x764e1  ldfld    int32 <<InitializeAsync>b__3_0>d::<>1__state
0x764e6  stloc.0
0x764e7  ldarg.0
0x764e8  ldfld    class Microsoft.VisualStudio.Setup.Installer.ProductCard.ViewModels.ProductCardUpdateMainPageViewModel <<InitializeAsync>b__3_0>d::<>4__this
0x764ed  stloc.1
0x764ee  ldloc.0
0x764ef  pop
0x764f0  nop
0x764f1  ldloc.0
0x764f2  brfalse.s loc_7654E
0x764f4  ldloc.1
0x764f5  ldloc.1
0x764f6  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerViewModelServiceOptions Microsoft.VisualStudio.Setup.Installer.ProductCard.ViewModels.ProductCardUpdateMainPageViewModel::serviceOptions
0x764fb  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateViewModelServiceOptions::.ctor(class [mscorlib]System.IServiceProvider provider)
0x76500  ldloc.1
0x76501  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel Microsoft.VisualStudio.Setup.Installer.ProductCard.ViewModels.ProductCardUpdateMainPageViewModel::product
0x76506  ldnull
0x76507  newobj   instance void Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateViewModelServiceOptions options, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel productModel, class Microsoft.VisualStudio.Setup.Installer.ViewModels.IProductActionViewModel changeUpdateSettingsViewModel)
0x7650c  call     instance void Microsoft.VisualStudio.Setup.Installer.ProductCard.ViewModels.ProductCardUpdateMainPageViewModel::set_UpdateDetailsViewModel(class Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.IUpdateDetailsViewModel value)
0x76511  ldloc.1
0x76512  call     instance class Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.IUpdateDetailsViewModel Microsoft.VisualStudio.Setup.Installer.ProductCard.ViewModels.ProductCardUpdateMainPageViewModel::get_UpdateDetailsViewModel()
0x76517  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.ViewModels.IViewModel::InitializeAsync()
0x7651c  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x76521  stloc.2
0x76522  ldloca.s 2
0x76524  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x76529  brtrue.s loc_7656A
0x7652b  ldarg.0
0x7652c  ldc.i4.0
0x7652d  dup
0x7652e  stloc.0
0x7652f  stfld    int32 <<InitializeAsync>b__3_0>d::<>1__state
0x76534  ldarg.0
0x76535  ldloc.2
0x76536  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<InitializeAsync>b__3_0>d::<>u__1
0x7653b  ldarg.0
0x7653c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<InitializeAsync>b__3_0>d::<>t__builder
0x76541  ldloca.s 2
0x76543  ldarg.0
0x76544  call     T0x2B0004D7
0x76549  leave    loc_76601
0x7654e  ldarg.0
0x7654f  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<InitializeAsync>b__3_0>d::<>u__1
0x76554  stloc.2
0x76555  ldarg.0
0x76556  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<InitializeAsync>b__3_0>d::<>u__1
0x7655b  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x76561  ldarg.0
0x76562  ldc.i4.m1
0x76563  dup
0x76564  stloc.0
0x76565  stfld    int32 <<InitializeAsync>b__3_0>d::<>1__state
0x7656a  ldloca.s 2
0x7656c  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x76571  ldloc.1
0x76572  ldc.i4.0
0x76573  call     instance void Microsoft.VisualStudio.Setup.Installer.ViewModels.LoadingViewModelBase::set_IsLoading(bool value)
0x76578  leave.s  loc_765D3
0x7657a  stloc.3
0x7657b  ldloc.1
0x7657c  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerViewModelServiceOptions Microsoft.VisualStudio.Setup.Installer.ProductCard.ViewModels.ProductCardUpdateMainPageViewModel::serviceOptions
0x76581  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x76586  dup
0x76587  brtrue.s loc_7658C
0x76589  pop
0x7658a  br.s     loc_765A5
0x7658c  ldstr    aFailedToCheckF_0// "Failed to check for update for current "...
0x76591  ldc.i4.1
0x76592  newarr   [mscorlib]System.Object
0x76597  dup
0x76598  ldc.i4.0
0x76599  ldloc.3
0x7659a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7659f  stelem.ref
0x765a0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x765a5  ldloc.1
0x765a6  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerViewModelServiceOptions Microsoft.VisualStudio.Setup.Installer.ProductCard.ViewModels.ProductCardUpdateMainPageViewModel::serviceOptions
0x765ab  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerViewModelServiceOptions::get_ErrorDialogService()
0x765b0  ldloc.3
0x765b1  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::InitializeVMFailed
0x765b6  ldstr    aProductcardupd_0// " ProductCardUpdateMainPageViewModel"
0x765bb  call     string [mscorlib]System.String::Concat(string, string)
0x765c0  call     void Microsoft.VisualStudio.Setup.Installer.Extensions::ShowError(class Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService errorService, class [mscorlib]System.Exception ex, [opt] string defaultErrorName)
0x765c5  ldloc.1
0x765c6  call     instance class [System]System.Windows.Input.ICommand Microsoft.VisualStudio.Setup.Installer.ProductCard.ViewModels.ProductCardUpdateMainPageViewModel::get_CloseCommand()
0x765cb  ldnull
0x765cc  callvirt instance void [System]System.Windows.Input.ICommand::Execute(object)
0x765d1  leave.s  loc_765D3
0x765d3  leave.s  loc_765EE
0x765d5  stloc.s  4
0x765d7  ldarg.0
0x765d8  ldc.i4.s 0xFE
0x765da  stfld    int32 <<InitializeAsync>b__3_0>d::<>1__state
0x765df  ldarg.0
0x765e0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<InitializeAsync>b__3_0>d::<>t__builder
0x765e5  ldloc.s  4
0x765e7  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x765ec  leave.s  loc_76601
0x765ee  ldarg.0
0x765ef  ldc.i4.s 0xFE
0x765f1  stfld    int32 <<InitializeAsync>b__3_0>d::<>1__state
0x765f6  ldarg.0
0x765f7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<InitializeAsync>b__3_0>d::<>t__builder
0x765fc  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x76601  ret
```
