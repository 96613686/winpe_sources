# <<InitializeAsync>b__8_0>d::MoveNext

- ea: `0x670e0`
- end: `0x6739a`
- name: `<<InitializeAsync>b__8_0>d::MoveNext`
- size: `698`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x10fe0`
- `0x11a90`
- `0x11f30`
- `0x12030`
- `0x12040`
- `0x12050`
- `0x12100`
- `0x21620`
- `0x216e0`
- `0x229a0`
- `0x22cb0`
- `0x2b700`
- `0x2b710`
- `0x2b750`
- `0x2d6b0`
- `0x2d6c0`
- `0x55080`
- `0x670e0`

## string_xrefs

- `0x67325`: `Command line handling cancelled due to shutdown.`

## pseudocode

```c

```

## disassembly

```asm
0x670e0  ldarg.0
0x670e1  ldfld    int32 <<InitializeAsync>b__8_0>d::<>1__state
0x670e6  stloc.0
0x670e7  ldarg.0
0x670e8  ldfld    class Microsoft.VisualStudio.Setup.Installer.ViewModels.MainPageViewModel <<InitializeAsync>b__8_0>d::<>4__this
0x670ed  stloc.1
0x670ee  ldloc.0
0x670ef  ldc.i4.2
0x670f0  pop
0x670f1  pop
0x670f2  nop
0x670f3  ldloc.0
0x670f4  switch   loc_6718B, loc_67232, loc_672E0
0x67105  ldloc.1
0x67106  ldfld    bool Microsoft.VisualStudio.Setup.Installer.ViewModels.MainPageViewModel::isInitialized
0x6710b  brfalse.s loc_67112
0x6710d  leave    loc_67386
0x67112  ldloc.1
0x67113  stloc.2
0x67114  ldc.i4.0
0x67115  stloc.3
0x67116  ldloc.2
0x67117  ldloca.s 3
0x67119  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x6711e  ldloc.1
0x6711f  ldfld    bool Microsoft.VisualStudio.Setup.Installer.ViewModels.MainPageViewModel::isInitialized
0x67124  brfalse.s loc_6712B
0x67126  leave    loc_67386
0x6712b  ldloc.1
0x6712c  ldc.i4.1
0x6712d  stfld    bool Microsoft.VisualStudio.Setup.Installer.ViewModels.MainPageViewModel::isInitialized
0x67132  leave.s  loc_67142
0x67134  ldloc.0
0x67135  ldc.i4.0
0x67136  bge.s    loc_67141
0x67138  ldloc.3
0x67139  brfalse.s loc_67141
0x6713b  ldloc.2
0x6713c  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x67141  endfinally
0x67142  ldloc.1
0x67143  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.IAppInitializerService Microsoft.VisualStudio.Setup.Installer.ViewModels.MainPageViewModel::appInitializer
0x67148  ldloca.s 5
0x6714a  initobj  [mscorlib]System.Threading.CancellationToken
0x67150  ldloc.s  5
0x67152  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.Services.IAppInitializerService::InitializeAsync([opt] valuetype [mscorlib]System.Threading.CancellationToken token)
0x67157  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x6715c  stloc.s  4
0x6715e  ldloca.s 4
0x67160  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x67165  brtrue.s loc_671A8
0x67167  ldarg.0
0x67168  ldc.i4.0
0x67169  dup
0x6716a  stloc.0
0x6716b  stfld    int32 <<InitializeAsync>b__8_0>d::<>1__state
0x67170  ldarg.0
0x67171  ldloc.s  4
0x67173  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<InitializeAsync>b__8_0>d::<>u__1
0x67178  ldarg.0
0x67179  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<InitializeAsync>b__8_0>d::<>t__builder
0x6717e  ldloca.s 4
0x67180  ldarg.0
0x67181  call     T0x2B000423
0x67186  leave    loc_67399
0x6718b  ldarg.0
0x6718c  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<InitializeAsync>b__8_0>d::<>u__1
0x67191  stloc.s  4
0x67193  ldarg.0
0x67194  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<InitializeAsync>b__8_0>d::<>u__1
0x67199  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x6719f  ldarg.0
0x671a0  ldc.i4.m1
0x671a1  dup
0x671a2  stloc.0
0x671a3  stfld    int32 <<InitializeAsync>b__8_0>d::<>1__state
0x671a8  ldloca.s 4
0x671aa  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x671af  ldloc.1
0x671b0  call     instance class Microsoft.VisualStudio.Setup.Installer.ViewModels.IInstalledPageViewModel Microsoft.VisualStudio.Setup.Installer.ViewModels.MainPageViewModel::get_InstalledPageVM()
0x671b5  ldloc.1
0x671b6  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.ViewModels.MainPageViewModel::OnShowAvailableProducts()
0x671bc  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x671c1  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Commands.RelayCommand::.ctor(class [mscorlib]System.Action execute)
0x671c6  callvirt instance void Microsoft.VisualStudio.Setup.Installer.ViewModels.IInstalledPageViewModel::set_ViewAvailableProductsCommand(class [System]System.Windows.Input.ICommand value)
0x671cb  ldloc.1
0x671cc  call     instance class Microsoft.VisualStudio.Setup.Installer.DeveloperNews.ViewModels.IDeveloperNewsViewModel Microsoft.VisualStudio.Setup.Installer.ViewModels.MainPageViewModel::get_DeveloperNewsVM()
0x671d1  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.ViewModels.IViewModel::InitializeAsync()
0x671d6  pop
0x671d7  ldc.i4.2
0x671d8  newarr   [mscorlib]System.Threading.Tasks.Task
0x671dd  dup
0x671de  ldc.i4.0
0x671df  ldloc.1
0x671e0  call     instance class Microsoft.VisualStudio.Setup.Installer.ViewModels.IInstalledPageViewModel Microsoft.VisualStudio.Setup.Installer.ViewModels.MainPageViewModel::get_InstalledPageVM()
0x671e5  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.ViewModels.IViewModel::InitializeAsync()
0x671ea  stelem.ref
0x671eb  dup
0x671ec  ldc.i4.1
0x671ed  ldloc.1
0x671ee  call     instance class Microsoft.VisualStudio.Setup.Installer.ViewModels.IAvailablePageViewModel Microsoft.VisualStudio.Setup.Installer.ViewModels.MainPageViewModel::get_AvailablePageVM()
0x671f3  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.ViewModels.IViewModel::InitializeAsync()
0x671f8  stelem.ref
0x671f9  call     class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.Task::WhenAll(class [mscorlib]System.Threading.Tasks.Task[])
0x671fe  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x67203  stloc.s  4
0x67205  ldloca.s 4
0x67207  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x6720c  brtrue.s loc_6724F
0x6720e  ldarg.0
0x6720f  ldc.i4.1
0x67210  dup
0x67211  stloc.0
0x67212  stfld    int32 <<InitializeAsync>b__8_0>d::<>1__state
0x67217  ldarg.0
0x67218  ldloc.s  4
0x6721a  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<InitializeAsync>b__8_0>d::<>u__1
0x6721f  ldarg.0
0x67220  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<InitializeAsync>b__8_0>d::<>t__builder
0x67225  ldloca.s 4
0x67227  ldarg.0
0x67228  call     T0x2B000423
0x6722d  leave    loc_67399
0x67232  ldarg.0
0x67233  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<InitializeAsync>b__8_0>d::<>u__1
0x67238  stloc.s  4
0x6723a  ldarg.0
0x6723b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<InitializeAsync>b__8_0>d::<>u__1
0x67240  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x67246  ldarg.0
0x67247  ldc.i4.m1
0x67248  dup
0x67249  stloc.0
0x6724a  stfld    int32 <<InitializeAsync>b__8_0>d::<>1__state
0x6724f  ldloca.s 4
0x67251  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x67256  ldloc.1
0x67257  ldloc.1
0x67258  ldflda   string Microsoft.VisualStudio.Setup.Installer.ViewModels.MainPageViewModel::loadingText
0x6725d  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_AlmostThere()
0x67262  ldnull
0x67263  ldstr    aLoadingtext// "LoadingText"
0x67268  call     T0x2B000082
0x6726d  pop
0x6726e  ldloc.1
0x6726f  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.ViewModels.MainPageViewModel::serviceOptions
0x67274  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Telemetry()
0x67279  dup
0x6727a  brtrue.s loc_6727F
0x6727c  pop
0x6727d  br.s     loc_6728C
0x6727f  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::BeginCommandLineOperationEvent
0x67284  ldnull
0x67285  ldnull
0x67286  ldc.i4.0
0x67287  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteEvent(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, object, bool)
0x6728c  ldloc.1
0x6728d  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.ViewModels.MainPageViewModel::serviceOptions
0x67292  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.ICommandLineOptionsService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions::get_CommandLineService()
0x67297  ldloc.1
0x67298  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.ViewModels.MainPageViewModel::serviceOptions
0x6729d  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions::get_ShutdownService()
0x672a2  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService::get_ShutdownToken()
0x672a7  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.Services.ICommandLineOptionsService::HandleCommandlineAsync([opt] valuetype [mscorlib]System.Threading.CancellationToken token)
0x672ac  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x672b1  stloc.s  4
0x672b3  ldloca.s 4
0x672b5  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x672ba  brtrue.s loc_672FD
0x672bc  ldarg.0
0x672bd  ldc.i4.2
0x672be  dup
0x672bf  stloc.0
0x672c0  stfld    int32 <<InitializeAsync>b__8_0>d::<>1__state
0x672c5  ldarg.0
0x672c6  ldloc.s  4
0x672c8  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<InitializeAsync>b__8_0>d::<>u__1
0x672cd  ldarg.0
0x672ce  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<InitializeAsync>b__8_0>d::<>t__builder
0x672d3  ldloca.s 4
0x672d5  ldarg.0
0x672d6  call     T0x2B000423
0x672db  leave    loc_67399
0x672e0  ldarg.0
0x672e1  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<InitializeAsync>b__8_0>d::<>u__1
0x672e6  stloc.s  4
0x672e8  ldarg.0
0x672e9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<InitializeAsync>b__8_0>d::<>u__1
0x672ee  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x672f4  ldarg.0
0x672f5  ldc.i4.m1
0x672f6  dup
0x672f7  stloc.0
0x672f8  stfld    int32 <<InitializeAsync>b__8_0>d::<>1__state
0x672fd  ldloca.s 4
0x672ff  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x67304  ldloc.1
0x67305  call     instance void Microsoft.VisualStudio.Setup.Installer.ViewModels.MainPageViewModel::StartCheckingForUpdates()
0x6730a  ldloc.1
0x6730b  ldc.i4.0
0x6730c  call     instance void Microsoft.VisualStudio.Setup.Installer.ViewModels.LoadingViewModelBase::set_IsLoading(bool value)
0x67311  leave.s  loc_67336
0x67313  pop
0x67314  ldloc.1
0x67315  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.ViewModels.MainPageViewModel::serviceOptions
0x6731a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x6731f  dup
0x67320  brtrue.s loc_67325
0x67322  pop
0x67323  br.s     loc_67334
0x67325  ldstr    aCommandLineHan// "Command line handling cancelled due to "...
0x6732a  call     T0x2B000010
0x6732f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x67334  leave.s  loc_67336
0x67336  leave.s  loc_6736B
0x67338  ldloc.0
0x67339  ldc.i4.0
0x6733a  bge.s    loc_6736A
0x6733c  ldloc.1
0x6733d  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.ViewModels.MainPageViewModel::serviceOptions
0x67342  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Telemetry()
0x67347  dup
0x67348  brtrue.s loc_6734D
0x6734a  pop
0x6734b  br.s     loc_6735A
0x6734d  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::EndCommandLineOperationEvent
0x67352  ldnull
0x67353  ldnull
0x67354  ldc.i4.0
0x67355  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteEvent(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, object, bool)
0x6735a  ldloc.1
0x6735b  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.ViewModels.MainPageViewModel::serviceOptions
0x67360  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IWindowService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions::get_WindowService()
0x67365  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.IWindowService::ShowWindow()
0x6736a  endfinally
0x6736b  leave.s  loc_67386
0x6736d  stloc.s  6
0x6736f  ldarg.0
0x67370  ldc.i4.s 0xFE
0x67372  stfld    int32 <<InitializeAsync>b__8_0>d::<>1__state
0x67377  ldarg.0
0x67378  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<InitializeAsync>b__8_0>d::<>t__builder
0x6737d  ldloc.s  6
0x6737f  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x67384  leave.s  loc_67399
0x67386  ldarg.0
0x67387  ldc.i4.s 0xFE
0x67389  stfld    int32 <<InitializeAsync>b__8_0>d::<>1__state
0x6738e  ldarg.0
0x6738f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<InitializeAsync>b__8_0>d::<>t__builder
0x67394  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x67399  ret
```
