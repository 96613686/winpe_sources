# <InvokeUpdatedInstallerAsync>d__12::MoveNext

- ea: `0x7bc80`
- end: `0x7bf14`
- name: `<InvokeUpdatedInstallerAsync>d__12::MoveNext`
- size: `660`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x7dd0`
- `0x7de0`
- `0x7e10`
- `0x2c4a0`
- `0x2c4b0`
- `0x2c4c0`
- `0x3f600`
- `0x3f6d0`
- `0x3f770`
- `0x7bc80`

## string_xrefs

- `0x7be42`: `Install operation failed with error: `
- `0x7be26`: `User canceled the operation while invoking self update from {0}`
- `0x7be33`: `InstallerService`
- `0x7bd0d`: `selfUpdate`
- `0x7bd7e`: `Invoking SelfUpdater with {0}`
- `0x7bdfa`: `Installer self-update complete. Updated elevated process started.`

## pseudocode

```c

```

## disassembly

```asm
0x7bc80  ldarg.0
0x7bc81  ldfld    int32 <InvokeUpdatedInstallerAsync>d__12::<>1__state
0x7bc86  stloc.0
0x7bc87  ldarg.0
0x7bc88  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService <InvokeUpdatedInstallerAsync>d__12::<>4__this
0x7bc8d  stloc.1
0x7bc8e  ldloc.0
0x7bc8f  brfalse.s loc_7BCDF
0x7bc91  ldloc.0
0x7bc92  ldc.i4.1
0x7bc93  beq      loc_7BD3D
0x7bc98  ldloc.1
0x7bc99  ldarg.0
0x7bc9a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService <InvokeUpdatedInstallerAsync>d__12::settings
0x7bc9f  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::InitializeSettings(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService settings)
0x7bca4  call     valuetype [mscorlib]System.Runtime.CompilerServices.YieldAwaitable [mscorlib]System.Threading.Tasks.Task::Yield()
0x7bca9  stloc.s  4
0x7bcab  ldloca.s 4
0x7bcad  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.YieldAwaitable/YieldAwaiter [mscorlib]System.Runtime.CompilerServices.YieldAwaitable::GetAwaiter()
0x7bcb2  stloc.3
0x7bcb3  ldloca.s 3
0x7bcb5  call     instance bool [mscorlib]System.Runtime.CompilerServices.YieldAwaitable/YieldAwaiter::get_IsCompleted()
0x7bcba  brtrue.s loc_7BCFB
0x7bcbc  ldarg.0
0x7bcbd  ldc.i4.0
0x7bcbe  dup
0x7bcbf  stloc.0
0x7bcc0  stfld    int32 <InvokeUpdatedInstallerAsync>d__12::<>1__state
0x7bcc5  ldarg.0
0x7bcc6  ldloc.3
0x7bcc7  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.YieldAwaitable/YieldAwaiter <InvokeUpdatedInstallerAsync>d__12::<>u__1
0x7bccc  ldarg.0
0x7bccd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InvokeUpdatedInstallerAsync>d__12::<>t__builder
0x7bcd2  ldloca.s 3
0x7bcd4  ldarg.0
0x7bcd5  call     T0x2B00051D
0x7bcda  leave    loc_7BF13
0x7bcdf  ldarg.0
0x7bce0  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.YieldAwaitable/YieldAwaiter <InvokeUpdatedInstallerAsync>d__12::<>u__1
0x7bce5  stloc.3
0x7bce6  ldarg.0
0x7bce7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.YieldAwaitable/YieldAwaiter <InvokeUpdatedInstallerAsync>d__12::<>u__1
0x7bcec  initobj  [mscorlib]System.Runtime.CompilerServices.YieldAwaitable/YieldAwaiter
0x7bcf2  ldarg.0
0x7bcf3  ldc.i4.m1
0x7bcf4  dup
0x7bcf5  stloc.0
0x7bcf6  stfld    int32 <InvokeUpdatedInstallerAsync>d__12::<>1__state
0x7bcfb  ldloca.s 3
0x7bcfd  call     instance void [mscorlib]System.Runtime.CompilerServices.YieldAwaitable/YieldAwaiter::GetResult()
0x7bd02  ldloc.1
0x7bd03  ldloca.s 5
0x7bd05  initobj  [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.TelemetryContext
0x7bd0b  ldloc.s  5
0x7bd0d  ldstr    aSelfupdate// "selfUpdate"
0x7bd12  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::SetOperationTelemetryProperties(valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.TelemetryContext, string telemetryContext)
0x7bd17  stloc.2
0x7bd18  ldarg.0
0x7bd19  ldloc.1
0x7bd1a  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::serviceOptions
0x7bd1f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Telemetry()
0x7bd24  dup
0x7bd25  brtrue.s loc_7BD2B
0x7bd27  pop
0x7bd28  ldnull
0x7bd29  br.s     loc_7BD38
0x7bd2b  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ElevatedInstallProductEvent
0x7bd30  ldloc.2
0x7bd31  ldc.i4.0
0x7bd32  ldc.i4.0
0x7bd33  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x7bd38  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InvokeUpdatedInstallerAsync>d__12::<telemetryOperation>5__2
0x7bd3d  nop
0x7bd3e  ldloc.0
0x7bd3f  ldc.i4.1
0x7bd40  beq.s    loc_7BD53
0x7bd42  ldarg.0
0x7bd43  ldloc.1
0x7bd44  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::serviceOptions
0x7bd49  callvirt instance class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_InstallerUpdateManager()
0x7bd4e  stfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager <InvokeUpdatedInstallerAsync>d__12::<selfUpdater>5__3
0x7bd53  nop
0x7bd54  ldloc.0
0x7bd55  ldc.i4.1
0x7bd56  beq.s    loc_7BDD4
0x7bd58  ldarg.0
0x7bd59  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager <InvokeUpdatedInstallerAsync>d__12::<selfUpdater>5__3
0x7bd5e  ldloc.1
0x7bd5f  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::OnProgress(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs e)
0x7bd65  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs>::.ctor(object, native int)
0x7bd6a  callvirt instance void Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager::add_Progress(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs> value)
0x7bd6f  ldarg.0
0x7bd70  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ElevateOptions <InvokeUpdatedInstallerAsync>d__12::elevateOptions
0x7bd75  ldc.i4.1
0x7bd76  call     T0x2B000225
0x7bd7b  stloc.s  6
0x7bd7d  ldloc.1
0x7bd7e  ldstr    aInvokingSelfup// "Invoking SelfUpdater with {0}"
0x7bd83  ldc.i4.1
0x7bd84  newarr   [mscorlib]System.Object
0x7bd89  dup
0x7bd8a  ldc.i4.0
0x7bd8b  ldloc.s  6
0x7bd8d  stelem.ref
0x7bd8e  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::TraceMessage(string format, object[] args)
0x7bd93  ldarg.0
0x7bd94  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager <InvokeUpdatedInstallerAsync>d__12::<selfUpdater>5__3
0x7bd99  ldloc.s  6
0x7bd9b  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess> Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager::InvokeAsync(string commandLine)
0x7bda0  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess>::GetAwaiter()
0x7bda5  stloc.s  7
0x7bda7  ldloca.s 7
0x7bda9  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess>::get_IsCompleted()
0x7bdae  brtrue.s loc_7BDF1
0x7bdb0  ldarg.0
0x7bdb1  ldc.i4.1
0x7bdb2  dup
0x7bdb3  stloc.0
0x7bdb4  stfld    int32 <InvokeUpdatedInstallerAsync>d__12::<>1__state
0x7bdb9  ldarg.0
0x7bdba  ldloc.s  7
0x7bdbc  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess> <InvokeUpdatedInstallerAsync>d__12::<>u__2
0x7bdc1  ldarg.0
0x7bdc2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InvokeUpdatedInstallerAsync>d__12::<>t__builder
0x7bdc7  ldloca.s 7
0x7bdc9  ldarg.0
0x7bdca  call     T0x2B00051E
0x7bdcf  leave    loc_7BF13
0x7bdd4  ldarg.0
0x7bdd5  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess> <InvokeUpdatedInstallerAsync>d__12::<>u__2
0x7bdda  stloc.s  7
0x7bddc  ldarg.0
0x7bddd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess> <InvokeUpdatedInstallerAsync>d__12::<>u__2
0x7bde2  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess>
0x7bde8  ldarg.0
0x7bde9  ldc.i4.m1
0x7bdea  dup
0x7bdeb  stloc.0
0x7bdec  stfld    int32 <InvokeUpdatedInstallerAsync>d__12::<>1__state
0x7bdf1  ldloca.s 7
0x7bdf3  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess>::GetResult()
0x7bdf8  pop
0x7bdf9  ldloc.1
0x7bdfa  ldstr    aInstallerSelfU// "Installer self-update complete. Updated"...
0x7bdff  call     T0x2B000010
0x7be04  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::TraceMessage(string format, object[] args)
0x7be09  leave    loc_7BE93
0x7be0e  pop
0x7be0f  ldarg.0
0x7be10  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InvokeUpdatedInstallerAsync>d__12::<telemetryOperation>5__2
0x7be15  dup
0x7be16  brtrue.s loc_7BE1B
0x7be18  pop
0x7be19  br.s     loc_7BE25
0x7be1b  ldstr    aCancel_0// "Cancel"
0x7be20  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordCancel(string)
0x7be25  ldloc.1
0x7be26  ldstr    aUserCanceledTh_0// "User canceled the operation while invok"...
0x7be2b  ldc.i4.1
0x7be2c  newarr   [mscorlib]System.Object
0x7be31  dup
0x7be32  ldc.i4.0
0x7be33  ldstr    aInstallerservi_1// "InstallerService"
0x7be38  stelem.ref
0x7be39  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::TraceMessage(string format, object[] args)
0x7be3e  rethrow
0x7be40  stloc.s  8
0x7be42  ldstr    aInstallOperati// "Install operation failed with error: "
0x7be47  ldloc.s  8
0x7be49  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7be4e  call     string [mscorlib]System.String::Concat(string, string)
0x7be53  stloc.s  9
0x7be55  ldloc.1
0x7be56  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::serviceOptions
0x7be5b  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x7be60  dup
0x7be61  brtrue.s loc_7BE66
0x7be63  pop
0x7be64  br.s     loc_7BE74
0x7be66  ldloc.s  8
0x7be68  ldloc.s  9
0x7be6a  call     T0x2B000010
0x7be6f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x7be74  ldarg.0
0x7be75  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InvokeUpdatedInstallerAsync>d__12::<telemetryOperation>5__2
0x7be7a  dup
0x7be7b  brtrue.s loc_7BE80
0x7be7d  pop
0x7be7e  br.s     loc_7BE91
0x7be80  ldloc.s  9
0x7be82  ldloc.s  8
0x7be84  ldloc.s  8
0x7be86  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7be8b  ldc.i4.1
0x7be8c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x7be91  rethrow
0x7be93  leave.s  loc_7BEB1
0x7be95  ldloc.0
0x7be96  ldc.i4.0
0x7be97  bge.s    loc_7BEB0
0x7be99  ldarg.0
0x7be9a  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager <InvokeUpdatedInstallerAsync>d__12::<selfUpdater>5__3
0x7be9f  ldloc.1
0x7bea0  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::OnProgress(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs e)
0x7bea6  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs>::.ctor(object, native int)
0x7beab  callvirt instance void Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager::remove_Progress(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs> value)
0x7beb0  endfinally
0x7beb1  leave.s  loc_7BEF2
0x7beb3  ldloc.0
0x7beb4  ldc.i4.0
0x7beb5  bge.s    loc_7BECA
0x7beb7  ldarg.0
0x7beb8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InvokeUpdatedInstallerAsync>d__12::<telemetryOperation>5__2
0x7bebd  brfalse.s loc_7BECA
0x7bebf  ldarg.0
0x7bec0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InvokeUpdatedInstallerAsync>d__12::<telemetryOperation>5__2
0x7bec5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7beca  endfinally
0x7becb  stloc.s  0xA
0x7becd  ldarg.0
0x7bece  ldc.i4.s 0xFE
0x7bed0  stfld    int32 <InvokeUpdatedInstallerAsync>d__12::<>1__state
0x7bed5  ldarg.0
0x7bed6  ldnull
0x7bed7  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InvokeUpdatedInstallerAsync>d__12::<telemetryOperation>5__2
0x7bedc  ldarg.0
0x7bedd  ldnull
0x7bede  stfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager <InvokeUpdatedInstallerAsync>d__12::<selfUpdater>5__3
0x7bee3  ldarg.0
0x7bee4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InvokeUpdatedInstallerAsync>d__12::<>t__builder
0x7bee9  ldloc.s  0xA
0x7beeb  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x7bef0  leave.s  loc_7BF13
0x7bef2  ldarg.0
0x7bef3  ldc.i4.s 0xFE
0x7bef5  stfld    int32 <InvokeUpdatedInstallerAsync>d__12::<>1__state
0x7befa  ldarg.0
0x7befb  ldnull
0x7befc  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InvokeUpdatedInstallerAsync>d__12::<telemetryOperation>5__2
0x7bf01  ldarg.0
0x7bf02  ldnull
0x7bf03  stfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager <InvokeUpdatedInstallerAsync>d__12::<selfUpdater>5__3
0x7bf08  ldarg.0
0x7bf09  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InvokeUpdatedInstallerAsync>d__12::<>t__builder
0x7bf0e  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x7bf13  ret
```
