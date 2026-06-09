# <DownloadInstallerAsync>d__11::MoveNext

- ea: `0x7b460`
- end: `0x7b732`
- name: `<DownloadInstallerAsync>d__11::MoveNext`
- size: `722`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, installer_update`

## callees

- `0x7dd0`
- `0x7de0`
- `0x7df0`
- `0x2c4a0`
- `0x2c4b0`
- `0x2c4c0`
- `0x36790`
- `0x367a0`
- `0x367b0`
- `0x367c0`
- `0x3f600`
- `0x3f6d0`
- `0x3f770`
- `0x7b460`

## string_xrefs

- `0x7b4fa`: `DownloadInstallerAsync`
- `0x7b49d`: `Install operation failed with error: `
- `0x7b663`: `Install operation failed with error: `
- `0x7b475`: `Downloading installer self-update.`
- `0x7b491`: `Cannot download the installer since no update is required.`
- `0x7b647`: `User canceled the operation while invoking self update from {0}`
- `0x7b654`: `InstallerService`

## pseudocode

```c

```

## disassembly

```asm
0x7b460  ldarg.0
0x7b461  ldfld    int32 <DownloadInstallerAsync>d__11::<>1__state
0x7b466  stloc.0
0x7b467  ldarg.0
0x7b468  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService <DownloadInstallerAsync>d__11::<>4__this
0x7b46d  stloc.1
0x7b46e  ldloc.0
0x7b46f  brfalse  loc_7B52A
0x7b474  ldloc.1
0x7b475  ldstr    aDownloadingIns// "Downloading installer self-update."
0x7b47a  call     T0x2B000010
0x7b47f  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::TraceMessage(string format, object[] args)
0x7b484  ldarg.0
0x7b485  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel <DownloadInstallerAsync>d__11::updateInformation
0x7b48a  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::get_IsUpdateRequired()
0x7b48f  brtrue.s loc_7B4D2
0x7b491  ldstr    aCannotDownload// "Cannot download the installer since no "...
0x7b496  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7b49b  stloc.s  4
0x7b49d  ldstr    aInstallOperati// "Install operation failed with error: "
0x7b4a2  ldloc.s  4
0x7b4a4  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7b4a9  call     string [mscorlib]System.String::Concat(string, string)
0x7b4ae  stloc.s  5
0x7b4b0  ldloc.1
0x7b4b1  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::serviceOptions
0x7b4b6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x7b4bb  dup
0x7b4bc  brtrue.s loc_7B4C1
0x7b4be  pop
0x7b4bf  br.s     loc_7B4CF
0x7b4c1  ldloc.s  4
0x7b4c3  ldloc.s  5
0x7b4c5  call     T0x2B000010
0x7b4ca  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x7b4cf  ldloc.s  4
0x7b4d1  throw
0x7b4d2  ldloc.1
0x7b4d3  ldarg.0
0x7b4d4  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService <DownloadInstallerAsync>d__11::settings
0x7b4d9  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::InitializeSettings(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService settings)
0x7b4de  ldarg.0
0x7b4df  ldloc.1
0x7b4e0  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::serviceOptions
0x7b4e5  callvirt instance class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_InstallerUpdateManager()
0x7b4ea  stfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager <DownloadInstallerAsync>d__11::<selfUpdater>5__2
0x7b4ef  ldloc.1
0x7b4f0  ldloca.s 6
0x7b4f2  initobj  [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.TelemetryContext
0x7b4f8  ldloc.s  6
0x7b4fa  ldstr    aDownloadinstal// "DownloadInstallerAsync"
0x7b4ff  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::SetOperationTelemetryProperties(valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.TelemetryContext, string telemetryContext)
0x7b504  stloc.3
0x7b505  ldarg.0
0x7b506  ldloc.1
0x7b507  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::serviceOptions
0x7b50c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Telemetry()
0x7b511  dup
0x7b512  brtrue.s loc_7B518
0x7b514  pop
0x7b515  ldnull
0x7b516  br.s     loc_7B525
0x7b518  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ElevatedInstallProductEvent
0x7b51d  ldloc.3
0x7b51e  ldc.i4.0
0x7b51f  ldc.i4.0
0x7b520  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x7b525  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <DownloadInstallerAsync>d__11::<telemetryOperation>5__3
0x7b52a  nop
0x7b52b  ldloc.0
0x7b52c  pop
0x7b52d  nop
0x7b52e  ldloc.0
0x7b52f  brfalse  loc_7B605
0x7b534  ldarg.0
0x7b535  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager <DownloadInstallerAsync>d__11::<selfUpdater>5__2
0x7b53a  ldloc.1
0x7b53b  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::OnProgress(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs e)
0x7b541  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs>::.ctor(object, native int)
0x7b546  callvirt instance void Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager::add_Progress(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs> value)
0x7b54b  ldloc.1
0x7b54c  ldstr    aAwaitingExtrac// "Awaiting ExtractAsync with bootstrapper"...
0x7b551  ldc.i4.4
0x7b552  newarr   [mscorlib]System.Object
0x7b557  dup
0x7b558  ldc.i4.0
0x7b559  ldarg.0
0x7b55a  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel <DownloadInstallerAsync>d__11::updateInformation
0x7b55f  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::get_BootstrapperUrl()
0x7b564  stelem.ref
0x7b565  dup
0x7b566  ldc.i4.1
0x7b567  ldarg.0
0x7b568  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel <DownloadInstallerAsync>d__11::updateInformation
0x7b56d  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::get_OpcVersion()
0x7b572  stelem.ref
0x7b573  dup
0x7b574  ldc.i4.2
0x7b575  ldarg.0
0x7b576  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel <DownloadInstallerAsync>d__11::updateInformation
0x7b57b  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::get_OpcVersion()
0x7b580  stelem.ref
0x7b581  dup
0x7b582  ldc.i4.3
0x7b583  ldarg.0
0x7b584  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel <DownloadInstallerAsync>d__11::updateInformation
0x7b589  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::get_OpcUrl()
0x7b58e  stelem.ref
0x7b58f  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::TraceMessage(string format, object[] args)
0x7b594  ldarg.0
0x7b595  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager <DownloadInstallerAsync>d__11::<selfUpdater>5__2
0x7b59a  ldarg.0
0x7b59b  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel <DownloadInstallerAsync>d__11::updateInformation
0x7b5a0  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::get_BootstrapperUrl()
0x7b5a5  ldarg.0
0x7b5a6  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel <DownloadInstallerAsync>d__11::updateInformation
0x7b5ab  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::get_OpcVersion()
0x7b5b0  ldarg.0
0x7b5b1  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel <DownloadInstallerAsync>d__11::updateInformation
0x7b5b6  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::get_OpcVersion()
0x7b5bb  ldarg.0
0x7b5bc  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel <DownloadInstallerAsync>d__11::updateInformation
0x7b5c1  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::get_OpcUrl()
0x7b5c6  ldarg.0
0x7b5c7  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <DownloadInstallerAsync>d__11::token
0x7b5cc  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager::ExtractAsync(string bootstrapperUri, class [mscorlib]System.Version clientVersion, [opt] class [mscorlib]System.Version minimumRequiredVersion, [opt] string opcUrl, [opt] valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x7b5d1  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x7b5d6  stloc.s  7
0x7b5d8  ldloca.s 7
0x7b5da  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x7b5df  brtrue.s loc_7B622
0x7b5e1  ldarg.0
0x7b5e2  ldc.i4.0
0x7b5e3  dup
0x7b5e4  stloc.0
0x7b5e5  stfld    int32 <DownloadInstallerAsync>d__11::<>1__state
0x7b5ea  ldarg.0
0x7b5eb  ldloc.s  7
0x7b5ed  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <DownloadInstallerAsync>d__11::<>u__1
0x7b5f2  ldarg.0
0x7b5f3  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <DownloadInstallerAsync>d__11::<>t__builder
0x7b5f8  ldloca.s 7
0x7b5fa  ldarg.0
0x7b5fb  call     T0x2B000519
0x7b600  leave    loc_7B731
0x7b605  ldarg.0
0x7b606  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <DownloadInstallerAsync>d__11::<>u__1
0x7b60b  stloc.s  7
0x7b60d  ldarg.0
0x7b60e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <DownloadInstallerAsync>d__11::<>u__1
0x7b613  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x7b619  ldarg.0
0x7b61a  ldc.i4.m1
0x7b61b  dup
0x7b61c  stloc.0
0x7b61d  stfld    int32 <DownloadInstallerAsync>d__11::<>1__state
0x7b622  ldloca.s 7
0x7b624  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x7b629  stloc.2
0x7b62a  leave    loc_7B70F
0x7b62f  pop
0x7b630  ldarg.0
0x7b631  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <DownloadInstallerAsync>d__11::<telemetryOperation>5__3
0x7b636  dup
0x7b637  brtrue.s loc_7B63C
0x7b639  pop
0x7b63a  br.s     loc_7B646
0x7b63c  ldstr    aCancel_0// "Cancel"
0x7b641  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordCancel(string)
0x7b646  ldloc.1
0x7b647  ldstr    aUserCanceledTh_0// "User canceled the operation while invok"...
0x7b64c  ldc.i4.1
0x7b64d  newarr   [mscorlib]System.Object
0x7b652  dup
0x7b653  ldc.i4.0
0x7b654  ldstr    aInstallerservi_1// "InstallerService"
0x7b659  stelem.ref
0x7b65a  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::TraceMessage(string format, object[] args)
0x7b65f  rethrow
0x7b661  stloc.s  8
0x7b663  ldstr    aInstallOperati// "Install operation failed with error: "
0x7b668  ldloc.s  8
0x7b66a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7b66f  call     string [mscorlib]System.String::Concat(string, string)
0x7b674  stloc.s  9
0x7b676  ldloc.1
0x7b677  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::serviceOptions
0x7b67c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x7b681  dup
0x7b682  brtrue.s loc_7B687
0x7b684  pop
0x7b685  br.s     loc_7B695
0x7b687  ldloc.s  8
0x7b689  ldloc.s  9
0x7b68b  call     T0x2B000010
0x7b690  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x7b695  ldarg.0
0x7b696  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <DownloadInstallerAsync>d__11::<telemetryOperation>5__3
0x7b69b  dup
0x7b69c  brtrue.s loc_7B6A1
0x7b69e  pop
0x7b69f  br.s     loc_7B6B2
0x7b6a1  ldloc.s  9
0x7b6a3  ldloc.s  8
0x7b6a5  ldloc.s  8
0x7b6a7  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7b6ac  ldc.i4.1
0x7b6ad  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x7b6b2  rethrow
0x7b6b4  ldloc.0
0x7b6b5  ldc.i4.0
0x7b6b6  bge.s    loc_7B6CF
0x7b6b8  ldarg.0
0x7b6b9  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager <DownloadInstallerAsync>d__11::<selfUpdater>5__2
0x7b6be  ldloc.1
0x7b6bf  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::OnProgress(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs e)
0x7b6c5  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs>::.ctor(object, native int)
0x7b6ca  callvirt instance void Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager::remove_Progress(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs> value)
0x7b6cf  endfinally
0x7b6d0  ldloc.0
0x7b6d1  ldc.i4.0
0x7b6d2  bge.s    loc_7B6E7
0x7b6d4  ldarg.0
0x7b6d5  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <DownloadInstallerAsync>d__11::<telemetryOperation>5__3
0x7b6da  brfalse.s loc_7B6E7
0x7b6dc  ldarg.0
0x7b6dd  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <DownloadInstallerAsync>d__11::<telemetryOperation>5__3
0x7b6e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7b6e7  endfinally
0x7b6e8  stloc.s  0xA
0x7b6ea  ldarg.0
0x7b6eb  ldc.i4.s 0xFE
0x7b6ed  stfld    int32 <DownloadInstallerAsync>d__11::<>1__state
0x7b6f2  ldarg.0
0x7b6f3  ldnull
0x7b6f4  stfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager <DownloadInstallerAsync>d__11::<selfUpdater>5__2
0x7b6f9  ldarg.0
0x7b6fa  ldnull
0x7b6fb  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <DownloadInstallerAsync>d__11::<telemetryOperation>5__3
0x7b700  ldarg.0
0x7b701  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <DownloadInstallerAsync>d__11::<>t__builder
0x7b706  ldloc.s  0xA
0x7b708  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetException(class [mscorlib]System.Exception)
0x7b70d  leave.s  loc_7B731
0x7b70f  ldarg.0
0x7b710  ldc.i4.s 0xFE
0x7b712  stfld    int32 <DownloadInstallerAsync>d__11::<>1__state
0x7b717  ldarg.0
0x7b718  ldnull
0x7b719  stfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager <DownloadInstallerAsync>d__11::<selfUpdater>5__2
0x7b71e  ldarg.0
0x7b71f  ldnull
0x7b720  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <DownloadInstallerAsync>d__11::<telemetryOperation>5__3
0x7b725  ldarg.0
0x7b726  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <DownloadInstallerAsync>d__11::<>t__builder
0x7b72b  ldloc.2
0x7b72c  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetResult(var<u1>)
0x7b731  ret
```
