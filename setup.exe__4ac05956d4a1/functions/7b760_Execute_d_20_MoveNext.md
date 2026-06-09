# <Execute>d__20::MoveNext

- ea: `0x7b760`
- end: `0x7b9ce`
- name: `<Execute>d__20::MoveNext`
- size: `622`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xa750`
- `0x2c4a0`
- `0x2c4b0`
- `0x3f770`
- `0x7b760`

## string_xrefs

- `0x7b909`: `Install operation failed with error: `
- `0x7b8d0`: `InstallerService`
- `0x7b854`: `Install operation failed.`
- `0x7b8c3`: `User canceled the operation during executing elevated install product event from {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7b760  ldarg.0
0x7b761  ldfld    int32 <Execute>d__20::<>1__state
0x7b766  stloc.0
0x7b767  ldarg.0
0x7b768  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService <Execute>d__20::<>4__this
0x7b76d  stloc.1
0x7b76e  ldloc.0
0x7b76f  brfalse.s loc_7B7C9
0x7b771  ldarg.0
0x7b772  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase <Execute>d__20::installer
0x7b777  ldloc.1
0x7b778  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::OnProgress(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs e)
0x7b77e  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs>::.ctor(object, native int)
0x7b783  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::add_Progress(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs>)
0x7b788  ldarg.0
0x7b789  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase <Execute>d__20::installer
0x7b78e  ldloc.1
0x7b78f  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::OnPausable(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.PausableEventArgs e)
0x7b795  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.PausableEventArgs>::.ctor(object, native int)
0x7b79a  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::add_Pausable(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.PausableEventArgs>)
0x7b79f  ldarg.0
0x7b7a0  ldloc.1
0x7b7a1  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::serviceOptions
0x7b7a6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Telemetry()
0x7b7ab  dup
0x7b7ac  brtrue.s loc_7B7B2
0x7b7ae  pop
0x7b7af  ldnull
0x7b7b0  br.s     loc_7B7C4
0x7b7b2  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ElevatedInstallProductEvent
0x7b7b7  ldarg.0
0x7b7b8  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> <Execute>d__20::properties
0x7b7bd  ldc.i4.0
0x7b7be  ldc.i4.0
0x7b7bf  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x7b7c4  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <Execute>d__20::<telemetryOperation>5__2
0x7b7c9  nop
0x7b7ca  ldloc.0
0x7b7cb  pop
0x7b7cc  nop
0x7b7cd  ldloc.0
0x7b7ce  brfalse.s loc_7B815
0x7b7d0  ldarg.0
0x7b7d1  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase <Execute>d__20::installer
0x7b7d6  ldarg.0
0x7b7d7  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <Execute>d__20::token
0x7b7dc  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::InvokeAsync(valuetype [mscorlib]System.Threading.CancellationToken)
0x7b7e1  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::GetAwaiter()
0x7b7e6  stloc.s  4
0x7b7e8  ldloca.s 4
0x7b7ea  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::get_IsCompleted()
0x7b7ef  brtrue.s loc_7B832
0x7b7f1  ldarg.0
0x7b7f2  ldc.i4.0
0x7b7f3  dup
0x7b7f4  stloc.0
0x7b7f5  stfld    int32 <Execute>d__20::<>1__state
0x7b7fa  ldarg.0
0x7b7fb  ldloc.s  4
0x7b7fd  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <Execute>d__20::<>u__1
0x7b802  ldarg.0
0x7b803  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <Execute>d__20::<>t__builder
0x7b808  ldloca.s 4
0x7b80a  ldarg.0
0x7b80b  call     T0x2B00051A
0x7b810  leave    loc_7B9CD
0x7b815  ldarg.0
0x7b816  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <Execute>d__20::<>u__1
0x7b81b  stloc.s  4
0x7b81d  ldarg.0
0x7b81e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <Execute>d__20::<>u__1
0x7b823  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>
0x7b829  ldarg.0
0x7b82a  ldc.i4.m1
0x7b82b  dup
0x7b82c  stloc.0
0x7b82d  stfld    int32 <Execute>d__20::<>1__state
0x7b832  ldloca.s 4
0x7b834  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::GetResult()
0x7b839  stloc.3
0x7b83a  ldloc.3
0x7b83b  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::get_Error()
0x7b840  ldnull
0x7b841  call     bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation::op_Inequality(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation)
0x7b846  brfalse.s loc_7B88A
0x7b848  ldarg.0
0x7b849  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <Execute>d__20::<telemetryOperation>5__2
0x7b84e  dup
0x7b84f  brtrue.s loc_7B854
0x7b851  pop
0x7b852  br.s     loc_7B85E
0x7b854  ldstr    aInstallOperati_0// "Install operation failed."
0x7b859  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x7b85e  ldarg.0
0x7b85f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <Execute>d__20::<telemetryOperation>5__2
0x7b864  dup
0x7b865  brtrue.s loc_7B86A
0x7b867  pop
0x7b868  br.s     loc_7B88A
0x7b86a  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x7b86f  dup
0x7b870  brtrue.s loc_7B875
0x7b872  pop
0x7b873  br.s     loc_7B88A
0x7b875  ldsfld   string Errors::StackTraceProperty
0x7b87a  ldloc.3
0x7b87b  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::get_Error()
0x7b880  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation::get_StackTrace()
0x7b885  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x7b88a  ldloc.3
0x7b88b  stloc.2
0x7b88c  leave    loc_7B9B2
0x7b891  isinst   [mscorlib]System.Exception
0x7b896  dup
0x7b897  brtrue.s loc_7B89D
0x7b899  pop
0x7b89a  ldc.i4.0
0x7b89b  br.s     loc_7B8A9
0x7b89d  stloc.s  5
0x7b89f  ldloc.s  5
0x7b8a1  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::IsOperationCanceledException(class [mscorlib]System.Exception error)
0x7b8a6  ldc.i4.0
0x7b8a7  cgt.un
0x7b8a9  endfilter
0x7b8ab  pop
0x7b8ac  ldarg.0
0x7b8ad  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <Execute>d__20::<telemetryOperation>5__2
0x7b8b2  dup
0x7b8b3  brtrue.s loc_7B8B8
0x7b8b5  pop
0x7b8b6  br.s     loc_7B8C2
0x7b8b8  ldstr    aCancel_0// "Cancel"
0x7b8bd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordCancel(string)
0x7b8c2  ldloc.1
0x7b8c3  ldstr    aUserCanceledTh_1// "User canceled the operation during exec"...
0x7b8c8  ldc.i4.1
0x7b8c9  newarr   [mscorlib]System.Object
0x7b8ce  dup
0x7b8cf  ldc.i4.0
0x7b8d0  ldstr    aInstallerservi_1// "InstallerService"
0x7b8d5  stelem.ref
0x7b8d6  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::TraceMessage(string format, object[] args)
0x7b8db  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::.ctor()
0x7b8e0  dup
0x7b8e1  ldarg.0
0x7b8e2  ldfld    string <Execute>d__20::instanceId
0x7b8e7  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::set_InstanceId(string)
0x7b8ec  dup
0x7b8ed  ldc.i4.1
0x7b8ee  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::set_IsCanceled(bool)
0x7b8f3  dup
0x7b8f4  ldloc.s  5
0x7b8f6  ldnull
0x7b8f7  call     class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ExtensionMethods::GetErrorInformation(class [mscorlib]System.Exception, string)
0x7b8fc  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::set_Error(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation)
0x7b901  stloc.2
0x7b902  leave    loc_7B9B2
0x7b907  stloc.s  6
0x7b909  ldstr    aInstallOperati// "Install operation failed with error: "
0x7b90e  ldloc.s  6
0x7b910  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7b915  call     string [mscorlib]System.String::Concat(string, string)
0x7b91a  stloc.s  7
0x7b91c  ldloc.1
0x7b91d  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::serviceOptions
0x7b922  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x7b927  dup
0x7b928  brtrue.s loc_7B92D
0x7b92a  pop
0x7b92b  br.s     loc_7B93B
0x7b92d  ldloc.s  6
0x7b92f  ldloc.s  7
0x7b931  call     T0x2B000010
0x7b936  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x7b93b  ldarg.0
0x7b93c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <Execute>d__20::<telemetryOperation>5__2
0x7b941  dup
0x7b942  brtrue.s loc_7B947
0x7b944  pop
0x7b945  br.s     loc_7B958
0x7b947  ldloc.s  7
0x7b949  ldloc.s  6
0x7b94b  ldloc.s  6
0x7b94d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7b952  ldc.i4.1
0x7b953  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x7b958  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::.ctor()
0x7b95d  dup
0x7b95e  ldarg.0
0x7b95f  ldfld    string <Execute>d__20::instanceId
0x7b964  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::set_InstanceId(string)
0x7b969  dup
0x7b96a  ldloc.s  6
0x7b96c  ldnull
0x7b96d  call     class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ExtensionMethods::GetErrorInformation(class [mscorlib]System.Exception, string)
0x7b972  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::set_Error(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation)
0x7b977  stloc.2
0x7b978  leave.s  loc_7B9B2
0x7b97a  ldloc.0
0x7b97b  ldc.i4.0
0x7b97c  bge.s    loc_7B991
0x7b97e  ldarg.0
0x7b97f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <Execute>d__20::<telemetryOperation>5__2
0x7b984  brfalse.s loc_7B991
0x7b986  ldarg.0
0x7b987  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <Execute>d__20::<telemetryOperation>5__2
0x7b98c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7b991  endfinally
0x7b992  stloc.s  8
0x7b994  ldarg.0
0x7b995  ldc.i4.s 0xFE
0x7b997  stfld    int32 <Execute>d__20::<>1__state
0x7b99c  ldarg.0
0x7b99d  ldnull
0x7b99e  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <Execute>d__20::<telemetryOperation>5__2
0x7b9a3  ldarg.0
0x7b9a4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <Execute>d__20::<>t__builder
0x7b9a9  ldloc.s  8
0x7b9ab  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::SetException(class [mscorlib]System.Exception)
0x7b9b0  leave.s  loc_7B9CD
0x7b9b2  ldarg.0
0x7b9b3  ldc.i4.s 0xFE
0x7b9b5  stfld    int32 <Execute>d__20::<>1__state
0x7b9ba  ldarg.0
0x7b9bb  ldnull
0x7b9bc  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <Execute>d__20::<telemetryOperation>5__2
0x7b9c1  ldarg.0
0x7b9c2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <Execute>d__20::<>t__builder
0x7b9c7  ldloc.2
0x7b9c8  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::SetResult(var<u1>)
0x7b9cd  ret
```
