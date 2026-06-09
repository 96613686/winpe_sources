# <HandleAsync>d__6::MoveNext

- ea: `0x690c0`
- end: `0x694ec`
- name: `<HandleAsync>d__6::MoveNext`
- size: `1068`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, installer_update`

## callees

- `0x6f00`
- `0x18ba0`
- `0x18be0`
- `0x18c10`
- `0x18ca0`
- `0x18e80`
- `0x18ea0`
- `0x1dbd0`
- `0x1dc50`
- `0x21ac0`
- `0x2d5f0`
- `0x4fe00`
- `0x4fe10`
- `0x68e00`
- `0x690c0`

## string_xrefs

- `0x693be`: `Successfully updated settings.`

## pseudocode

```c

```

## disassembly

```asm
0x690c0  ldarg.0
0x690c1  ldfld    int32 <HandleAsync>d__6::<>1__state
0x690c6  stloc.0
0x690c7  ldarg.0
0x690c8  ldfld    class Microsoft.VisualStudio.Setup.Installer.ChangeChannel.Commands.UpdateSettingsCommand <HandleAsync>d__6::<>4__this
0x690cd  stloc.1
0x690ce  ldloc.0
0x690cf  ldc.i4.4
0x690d0  ble.un.s loc_6912A
0x690d2  ldloc.0
0x690d3  ldc.i4.5
0x690d4  beq      loc_6948B
0x690d9  ldloc.1
0x690da  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateSettingsCommandServiceOptions Microsoft.VisualStudio.Setup.Installer.ChangeChannel.Commands.UpdateSettingsCommand::serviceOptions
0x690df  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IPublishSubscribeService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateSettingsCommandServiceOptions::get_PubSubService()
0x690e4  ldarg.0
0x690e5  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.UpdateSettingsOptions <HandleAsync>d__6::options
0x690ea  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Services.UpdateSettingsOptions::get_InstanceId()
0x690ef  call     class Microsoft.VisualStudio.Setup.Installer.Events.UpdateSettingsOperationStateChangeEvent Microsoft.VisualStudio.Setup.Installer.Events.UpdateSettingsOperationStateChangeEvent::CreateStartedEvent(string instanceId)
0x690f4  callvirt T0x2B00043B
0x690f9  ldarg.0
0x690fa  ldloc.1
0x690fb  ldarg.0
0x690fc  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.UpdateSettingsOptions <HandleAsync>d__6::options
0x69101  call     instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel Microsoft.VisualStudio.Setup.Installer.ChangeChannel.Commands.UpdateSettingsCommand::TryGetOriginalProduct(class Microsoft.VisualStudio.Setup.Installer.Services.UpdateSettingsOptions)
0x69106  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleAsync>d__6::<originalProduct>5__2
0x6910b  ldarg.0
0x6910c  ldc.i4.1
0x6910d  stfld    bool <HandleAsync>d__6::<succeeded>5__3
0x69112  ldarg.0
0x69113  ldloc.1
0x69114  ldarg.0
0x69115  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.UpdateSettingsOptions <HandleAsync>d__6::options
0x6911a  ldarg.0
0x6911b  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleAsync>d__6::<originalProduct>5__2
0x69120  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation Microsoft.VisualStudio.Setup.Installer.ChangeChannel.Commands.UpdateSettingsCommand::StartTelemetryOperation(class Microsoft.VisualStudio.Setup.Installer.Services.UpdateSettingsOptions options, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel originalProduct)
0x69125  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <HandleAsync>d__6::<operation>5__4
0x6912a  nop
0x6912b  ldloc.0
0x6912c  ldc.i4.4
0x6912d  pop
0x6912e  pop
0x6912f  nop
0x69130  ldloc.0
0x69131  brfalse.s loc_69183
0x69133  ldloc.0
0x69134  ldc.i4.1
0x69135  sub
0x69136  ldc.i4.3
0x69137  ble.un   loc_691CF
0x6913c  ldloc.1
0x6913d  ldarg.0
0x6913e  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.UpdateSettingsOptions <HandleAsync>d__6::options
0x69143  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.ChangeChannel.Commands.UpdateSettingsCommand::AddChannelAsync(class Microsoft.VisualStudio.Setup.Installer.Services.UpdateSettingsOptions options)
0x69148  ldc.i4.0
0x69149  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x6914e  stloc.3
0x6914f  ldloca.s 3
0x69151  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x69156  stloc.2
0x69157  ldloca.s 2
0x69159  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x6915e  brtrue.s loc_6919F
0x69160  ldarg.0
0x69161  ldc.i4.0
0x69162  dup
0x69163  stloc.0
0x69164  stfld    int32 <HandleAsync>d__6::<>1__state
0x69169  ldarg.0
0x6916a  ldloc.2
0x6916b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleAsync>d__6::<>u__1
0x69170  ldarg.0
0x69171  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsync>d__6::<>t__builder
0x69176  ldloca.s 2
0x69178  ldarg.0
0x69179  call     T0x2B00043C
0x6917e  leave    loc_694EB
0x69183  ldarg.0
0x69184  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleAsync>d__6::<>u__1
0x69189  stloc.2
0x6918a  ldarg.0
0x6918b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleAsync>d__6::<>u__1
0x69190  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x69196  ldarg.0
0x69197  ldc.i4.m1
0x69198  dup
0x69199  stloc.0
0x6919a  stfld    int32 <HandleAsync>d__6::<>1__state
0x6919f  ldloca.s 2
0x691a1  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x691a6  ldloc.1
0x691a7  ldarg.0
0x691a8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <HandleAsync>d__6::<operation>5__4
0x691ad  ldarg.0
0x691ae  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleAsync>d__6::<originalProduct>5__2
0x691b3  ldarg.0
0x691b4  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.UpdateSettingsOptions <HandleAsync>d__6::options
0x691b9  call     instance void Microsoft.VisualStudio.Setup.Installer.ChangeChannel.Commands.UpdateSettingsCommand::AddNewChannelProperties(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation operation, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel originalProduct, class Microsoft.VisualStudio.Setup.Installer.Services.UpdateSettingsOptions options)
0x691be  ldarg.0
0x691bf  ldloc.1
0x691c0  ldfld    class RpcFactory Microsoft.VisualStudio.Setup.Installer.ChangeChannel.Commands.UpdateSettingsCommand::factory
0x691c5  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Rpc.IRpcService RpcFactory::Invoke()
0x691ca  stfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.IRpcService <HandleAsync>d__6::<rpcClient>5__5
0x691cf  nop
0x691d0  ldloc.0
0x691d1  ldc.i4.1
0x691d2  sub
0x691d3  switch   loc_69236, loc_692A5, loc_69326, loc_6938F
0x691e8  ldarg.0
0x691e9  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.IRpcService <HandleAsync>d__6::<rpcClient>5__5
0x691ee  call     valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationToken::get_None()
0x691f3  callvirt T0x2B00043D
0x691f8  ldc.i4.0
0x691f9  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerUpdateSettingsService>::ConfigureAwait(!!T0)
0x691fe  stloc.s  5
0x69200  ldloca.s 5
0x69202  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerUpdateSettingsService>::GetAwaiter()
0x69207  stloc.s  4
0x69209  ldloca.s 4
0x6920b  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerUpdateSettingsService>::get_IsCompleted()
0x69210  brtrue.s loc_69253
0x69212  ldarg.0
0x69213  ldc.i4.1
0x69214  dup
0x69215  stloc.0
0x69216  stfld    int32 <HandleAsync>d__6::<>1__state
0x6921b  ldarg.0
0x6921c  ldloc.s  4
0x6921e  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerUpdateSettingsService> <HandleAsync>d__6::<>u__2
0x69223  ldarg.0
0x69224  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsync>d__6::<>t__builder
0x69229  ldloca.s 4
0x6922b  ldarg.0
0x6922c  call     T0x2B00043E
0x69231  leave    loc_694EB
0x69236  ldarg.0
0x69237  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerUpdateSettingsService> <HandleAsync>d__6::<>u__2
0x6923c  stloc.s  4
0x6923e  ldarg.0
0x6923f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerUpdateSettingsService> <HandleAsync>d__6::<>u__2
0x69244  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerUpdateSettingsService>
0x6924a  ldarg.0
0x6924b  ldc.i4.m1
0x6924c  dup
0x6924d  stloc.0
0x6924e  stfld    int32 <HandleAsync>d__6::<>1__state
0x69253  ldloca.s 4
0x69255  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerUpdateSettingsService>::GetResult()
0x6925a  ldarg.0
0x6925b  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.UpdateSettingsOptions <HandleAsync>d__6::options
0x69260  call     valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationToken::get_None()
0x69265  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.Services.IInstallerUpdateSettingsService::ChangeUpdateSettingsAsync(class Microsoft.VisualStudio.Setup.Installer.Services.UpdateSettingsOptions options, valuetype [mscorlib]System.Threading.CancellationToken token)
0x6926a  ldc.i4.0
0x6926b  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x69270  stloc.3
0x69271  ldloca.s 3
0x69273  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x69278  stloc.2
0x69279  ldloca.s 2
0x6927b  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x69280  brtrue.s loc_692C1
0x69282  ldarg.0
0x69283  ldc.i4.2
0x69284  dup
0x69285  stloc.0
0x69286  stfld    int32 <HandleAsync>d__6::<>1__state
0x6928b  ldarg.0
0x6928c  ldloc.2
0x6928d  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleAsync>d__6::<>u__1
0x69292  ldarg.0
0x69293  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsync>d__6::<>t__builder
0x69298  ldloca.s 2
0x6929a  ldarg.0
0x6929b  call     T0x2B00043C
0x692a0  leave    loc_694EB
0x692a5  ldarg.0
0x692a6  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleAsync>d__6::<>u__1
0x692ab  stloc.2
0x692ac  ldarg.0
0x692ad  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleAsync>d__6::<>u__1
0x692b2  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x692b8  ldarg.0
0x692b9  ldc.i4.m1
0x692ba  dup
0x692bb  stloc.0
0x692bc  stfld    int32 <HandleAsync>d__6::<>1__state
0x692c1  ldloca.s 2
0x692c3  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x692c8  ldarg.0
0x692c9  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.UpdateSettingsOptions <HandleAsync>d__6::options
0x692ce  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Services.UpdateSettingsOptions::get_AutomaticallyUpdate()
0x692d3  brfalse  loc_693B2
0x692d8  ldarg.0
0x692d9  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.IRpcService <HandleAsync>d__6::<rpcClient>5__5
0x692de  call     valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationToken::get_None()
0x692e3  callvirt T0x2B00043F
0x692e8  ldc.i4.0
0x692e9  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.Services.IVSUpdaterBootstrapper>::ConfigureAwait(!!T0)
0x692ee  stloc.s  7
0x692f0  ldloca.s 7
0x692f2  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class Microsoft.VisualStudio.Setup.Services.IVSUpdaterBootstrapper>::GetAwaiter()
0x692f7  stloc.s  6
0x692f9  ldloca.s 6
0x692fb  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class Microsoft.VisualStudio.Setup.Services.IVSUpdaterBootstrapper>::get_IsCompleted()
0x69300  brtrue.s loc_69343
0x69302  ldarg.0
0x69303  ldc.i4.3
0x69304  dup
0x69305  stloc.0
0x69306  stfld    int32 <HandleAsync>d__6::<>1__state
0x6930b  ldarg.0
0x6930c  ldloc.s  6
0x6930e  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class Microsoft.VisualStudio.Setup.Services.IVSUpdaterBootstrapper> <HandleAsync>d__6::<>u__3
0x69313  ldarg.0
0x69314  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsync>d__6::<>t__builder
0x69319  ldloca.s 6
0x6931b  ldarg.0
0x6931c  call     T0x2B000440
0x69321  leave    loc_694EB
0x69326  ldarg.0
0x69327  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class Microsoft.VisualStudio.Setup.Services.IVSUpdaterBootstrapper> <HandleAsync>d__6::<>u__3
0x6932c  stloc.s  6
0x6932e  ldarg.0
0x6932f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class Microsoft.VisualStudio.Setup.Services.IVSUpdaterBootstrapper> <HandleAsync>d__6::<>u__3
0x69334  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class Microsoft.VisualStudio.Setup.Services.IVSUpdaterBootstrapper>
0x6933a  ldarg.0
0x6933b  ldc.i4.m1
0x6933c  dup
0x6933d  stloc.0
0x6933e  stfld    int32 <HandleAsync>d__6::<>1__state
0x69343  ldloca.s 6
0x69345  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class Microsoft.VisualStudio.Setup.Services.IVSUpdaterBootstrapper>::GetResult()
0x6934a  call     valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationToken::get_None()
0x6934f  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Services.IVSUpdaterBootstrapper::InstallAsync([opt] valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x69354  ldc.i4.0
0x69355  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x6935a  stloc.3
0x6935b  ldloca.s 3
0x6935d  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x69362  stloc.2
0x69363  ldloca.s 2
0x69365  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x6936a  brtrue.s loc_693AB
0x6936c  ldarg.0
0x6936d  ldc.i4.4
0x6936e  dup
0x6936f  stloc.0
0x69370  stfld    int32 <HandleAsync>d__6::<>1__state
0x69375  ldarg.0
0x69376  ldloc.2
0x69377  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleAsync>d__6::<>u__1
0x6937c  ldarg.0
0x6937d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsync>d__6::<>t__builder
0x69382  ldloca.s 2
0x69384  ldarg.0
0x69385  call     T0x2B00043C
0x6938a  leave    loc_694EB
0x6938f  ldarg.0
0x69390  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleAsync>d__6::<>u__1
0x69395  stloc.2
0x69396  ldarg.0
0x69397  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleAsync>d__6::<>u__1
0x6939c  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x693a2  ldarg.0
0x693a3  ldc.i4.m1
0x693a4  dup
0x693a5  stloc.0
0x693a6  stfld    int32 <HandleAsync>d__6::<>1__state
0x693ab  ldloca.s 2
0x693ad  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x693b2  ldarg.0
0x693b3  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <HandleAsync>d__6::<operation>5__4
0x693b8  dup
0x693b9  brtrue.s loc_693BE
0x693bb  pop
0x693bc  br.s     loc_693C8
0x693be  ldstr    aSuccessfullyUp_0// "Successfully updated settings."
0x693c3  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x693c8  leave.s  loc_693E2
0x693ca  ldloc.0
0x693cb  ldc.i4.0
0x693cc  bge.s    loc_693E1
0x693ce  ldarg.0
0x693cf  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.IRpcService <HandleAsync>d__6::<rpcClient>5__5
0x693d4  brfalse.s loc_693E1
0x693d6  ldarg.0
0x693d7  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.IRpcService <HandleAsync>d__6::<rpcClient>5__5
0x693dc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x693e1  endfinally
0x693e2  ldarg.0
0x693e3  ldnull
0x693e4  stfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.IRpcService <HandleAsync>d__6::<rpcClient>5__5
0x693e9  leave.s  loc_69404
0x693eb  stloc.s  8
0x693ed  ldarg.0
0x693ee  ldc.i4.0
0x693ef  stfld    bool <HandleAsync>d__6::<succeeded>5__3
0x693f4  ldloc.1
0x693f5  ldarg.0
0x693f6  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <HandleAsync>d__6::<operation>5__4
  ... truncated ...
```
