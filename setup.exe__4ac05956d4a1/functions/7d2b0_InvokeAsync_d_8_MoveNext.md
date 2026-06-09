# <InvokeAsync>d__8::MoveNext

- ea: `0x7d2b0`
- end: `0x7d63e`
- name: `<InvokeAsync>d__8::MoveNext`
- size: `910`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callees

- `0xa750`
- `0x21990`
- `0x2c4b0`
- `0x2c4d0`
- `0x2c4e0`
- `0x2c640`
- `0x3e3a0`
- `0x3e3b0`
- `0x40b30`
- `0x40f30`
- `0x40f60`
- `0x40f80`
- `0x41090`
- `0x410e0`
- `0x56840`
- `0x59300`
- `0x59310`
- `0x7d2b0`

## string_xrefs

- `0x7d2e0`: `Starting installer self-update.`
- `0x7d3c3`: `Failed to download the update: {0}, {1}`
- `0x7d3ec`: `InstallerDownloadFailedMessage`
- `0x7d5b5`: `Installer self-update completed. Requesting automatic shutdown of the older installer process.`

## pseudocode

```c

```

## disassembly

```asm
0x7d2b0  ldarg.0
0x7d2b1  ldfld    int32 <InvokeAsync>d__8::<>1__state
0x7d2b6  stloc.0
0x7d2b7  ldarg.0
0x7d2b8  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdater <InvokeAsync>d__8::<>4__this
0x7d2bd  stloc.1
0x7d2be  ldloc.0
0x7d2bf  ldc.i4.1
0x7d2c0  pop
0x7d2c1  pop
0x7d2c2  nop
0x7d2c3  ldloc.0
0x7d2c4  brfalse.s loc_7D2EF
0x7d2c6  ldloc.0
0x7d2c7  ldc.i4.1
0x7d2c8  beq      loc_7D4E4
0x7d2cd  ldnull
0x7d2ce  stloc.3
0x7d2cf  ldloc.1
0x7d2d0  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x7d2d5  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x7d2da  dup
0x7d2db  brtrue.s loc_7D2E0
0x7d2dd  pop
0x7d2de  br.s     loc_7D2EF
0x7d2e0  ldstr    aStartingInstal// "Starting installer self-update."
0x7d2e5  call     T0x2B000010
0x7d2ea  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x7d2ef  nop
0x7d2f0  ldloc.0
0x7d2f1  brfalse.s loc_7D349
0x7d2f3  ldarg.0
0x7d2f4  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerService <InvokeAsync>d__8::installer
0x7d2f9  ldloc.1
0x7d2fa  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x7d2ff  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_SettingsService()
0x7d304  ldloc.1
0x7d305  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdater::updateInfo
0x7d30a  ldarg.0
0x7d30b  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <InvokeAsync>d__8::token
0x7d310  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerService::DownloadInstallerAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService settings, class Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel updateInformation, valuetype [mscorlib]System.Threading.CancellationToken token)
0x7d315  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x7d31a  stloc.s  7
0x7d31c  ldloca.s 7
0x7d31e  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x7d323  brtrue.s loc_7D366
0x7d325  ldarg.0
0x7d326  ldc.i4.0
0x7d327  dup
0x7d328  stloc.0
0x7d329  stfld    int32 <InvokeAsync>d__8::<>1__state
0x7d32e  ldarg.0
0x7d32f  ldloc.s  7
0x7d331  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <InvokeAsync>d__8::<>u__1
0x7d336  ldarg.0
0x7d337  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <InvokeAsync>d__8::<>t__builder
0x7d33c  ldloca.s 7
0x7d33e  ldarg.0
0x7d33f  call     T0x2B000530
0x7d344  leave    loc_7D63D
0x7d349  ldarg.0
0x7d34a  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <InvokeAsync>d__8::<>u__1
0x7d34f  stloc.s  7
0x7d351  ldarg.0
0x7d352  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <InvokeAsync>d__8::<>u__1
0x7d357  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x7d35d  ldarg.0
0x7d35e  ldc.i4.m1
0x7d35f  dup
0x7d360  stloc.0
0x7d361  stfld    int32 <InvokeAsync>d__8::<>1__state
0x7d366  ldloca.s 7
0x7d368  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x7d36d  stloc.3
0x7d36e  leave    loc_7D43C
0x7d373  isinst   [mscorlib]System.Exception
0x7d378  dup
0x7d379  brtrue.s loc_7D37F
0x7d37b  pop
0x7d37c  ldc.i4.0
0x7d37d  br.s     loc_7D38B
0x7d37f  stloc.s  8
0x7d381  ldloc.s  8
0x7d383  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::IsOperationCanceledException(class [mscorlib]System.Exception error)
0x7d388  ldc.i4.0
0x7d389  cgt.un
0x7d38b  endfilter
0x7d38d  pop
0x7d38e  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::.ctor()
0x7d393  dup
0x7d394  ldloc.s  8
0x7d396  ldnull
0x7d397  call     class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ExtensionMethods::GetErrorInformation(class [mscorlib]System.Exception, string)
0x7d39c  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::set_Error(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation)
0x7d3a1  dup
0x7d3a2  ldc.i4.1
0x7d3a3  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::set_IsCanceled(bool)
0x7d3a8  stloc.2
0x7d3a9  leave    loc_7D629
0x7d3ae  stloc.s  9
0x7d3b0  ldloc.1
0x7d3b1  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x7d3b6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x7d3bb  dup
0x7d3bc  brtrue.s loc_7D3C1
0x7d3be  pop
0x7d3bf  br.s     loc_7D3E7
0x7d3c1  ldloc.s  9
0x7d3c3  ldstr    aFailedToDownlo_5// "Failed to download the update: {0}, {1}"
0x7d3c8  ldc.i4.2
0x7d3c9  newarr   [mscorlib]System.Object
0x7d3ce  dup
0x7d3cf  ldc.i4.0
0x7d3d0  ldloc.s  9
0x7d3d2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7d3d7  stelem.ref
0x7d3d8  dup
0x7d3d9  ldc.i4.1
0x7d3da  ldloc.s  9
0x7d3dc  callvirt instance string [mscorlib]System.Object::ToString()
0x7d3e1  stelem.ref
0x7d3e2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x7d3e7  call     class [mscorlib]System.Resources.ResourceManager [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ResourceManager()
0x7d3ec  ldstr    aInstallerdownl// "InstallerDownloadFailedMessage"
0x7d3f1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7d3f6  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x7d3fb  stloc.s  0xA
0x7d3fd  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::.ctor()
0x7d402  dup
0x7d403  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_InstallerDownloadFailedMessage()
0x7d408  ldloc.s  0xA
0x7d40a  ldloc.s  9
0x7d40c  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x7d411  ldloc.s  9
0x7d413  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x7d418  ldloc.s  9
0x7d41a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x7d41f  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7d424  ldnull
0x7d425  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation::.ctor(string, string, string, int32, string, string)
0x7d42a  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::set_Error(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation)
0x7d42f  dup
0x7d430  ldc.i4.0
0x7d431  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::set_IsCanceled(bool)
0x7d436  stloc.2
0x7d437  leave    loc_7D629
0x7d43c  ldloc.1
0x7d43d  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x7d442  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ISingletonService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_SingletonService()
0x7d447  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ISingletonService::ReleaseSingletonLock()
0x7d44c  pop
0x7d44d  ldloc.1
0x7d44e  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdater::ClearSessionId()
0x7d453  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x7d458  stloc.s  0xB
0x7d45a  ldloca.s 0xB
0x7d45c  constrained. [mscorlib]System.Guid
0x7d462  callvirt instance string [mscorlib]System.Object::ToString()
0x7d467  stloc.s  4
0x7d469  ldloc.1
0x7d46a  ldloc.s  4
0x7d46c  call     instance class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdater::GetInstallerUpdateOptions(string streamName)
0x7d471  stloc.s  5
0x7d473  ldloc.1
0x7d474  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdater::installerTelemetryContext
0x7d479  brfalse.s loc_7D4CB
0x7d47b  ldloc.s  5
0x7d47d  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_TelemetryContextSubDirectory()
0x7d482  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7d487  ldc.i4.0
0x7d488  cgt.un
0x7d48a  stloc.s  0xC
0x7d48c  ldloc.s  5
0x7d48e  stloc.s  0xD
0x7d490  ldloc.s  0xD
0x7d492  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_TelemetryContextSubDirectory()
0x7d497  brtrue.s loc_7D4B6
0x7d499  ldloc.s  0xD
0x7d49b  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x7d4a0  stloc.s  0xB
0x7d4a2  ldloca.s 0xB
0x7d4a4  ldstr    aN// "N"
0x7d4a9  call     instance string [mscorlib]System.Guid::ToString(string)
0x7d4ae  dup
0x7d4af  stloc.s  0xE
0x7d4b1  callvirt instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::set_TelemetryContextSubDirectory(string value)
0x7d4b6  ldloc.1
0x7d4b7  ldloc.s  5
0x7d4b9  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_TelemetryContextSubDirectory()
0x7d4be  ldloc.1
0x7d4bf  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdater::installerTelemetryContext
0x7d4c4  ldloc.s  0xC
0x7d4c6  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdater::TrySaveInstallerTelemetryContext(string contextGuid, class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext context, bool wasContextDirectoryNull)
0x7d4cb  ldloc.1
0x7d4cc  ldloc.s  4
0x7d4ce  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdater::WaitForNewInstallerAsync(string streamName)
0x7d4d3  stloc.s  6
0x7d4d5  ldarg.0
0x7d4d6  ldloc.1
0x7d4d7  ldloc.3
0x7d4d8  ldloc.s  5
0x7d4da  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdater::StartNewInstaller(string path, class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase installerOptions)
0x7d4df  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess <InvokeAsync>d__8::<process>5__2
0x7d4e4  nop
0x7d4e5  ldloc.0
0x7d4e6  ldc.i4.1
0x7d4e7  beq      loc_7D56F
0x7d4ec  ldloc.1
0x7d4ed  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.IInstallerUpdateOptionsProvider Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdater::installerUpdateOptionsProvider
0x7d4f2  ldloc.s  5
0x7d4f4  ldarg.0
0x7d4f5  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess <InvokeAsync>d__8::<process>5__2
0x7d4fa  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess::get_Id()
0x7d4ff  callvirt instance class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ElevateOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.IInstallerUpdateOptionsProvider::GetElevateUpdateOptions(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase installerOptions, int32 unelevatedProcessId)
0x7d504  stloc.s  0xF
0x7d506  ldarg.0
0x7d507  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerService <InvokeAsync>d__8::installer
0x7d50c  ldloc.s  0xF
0x7d50e  ldloc.1
0x7d50f  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x7d514  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_SettingsService()
0x7d519  ldarg.0
0x7d51a  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <InvokeAsync>d__8::token
0x7d51f  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerService::InvokeUpdatedInstallerAsync(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ElevateOptions elevatedOptions, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService settings, valuetype [mscorlib]System.Threading.CancellationToken token)
0x7d524  stloc.s  0x10
0x7d526  ldc.i4.2
0x7d527  newarr   [mscorlib]System.Threading.Tasks.Task
0x7d52c  dup
0x7d52d  ldc.i4.0
0x7d52e  ldloc.s  6
0x7d530  stelem.ref
0x7d531  dup
0x7d532  ldc.i4.1
0x7d533  ldloc.s  0x10
0x7d535  stelem.ref
0x7d536  call     class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.Task::WhenAll(class [mscorlib]System.Threading.Tasks.Task[])
0x7d53b  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x7d540  stloc.s  0x11
0x7d542  ldloca.s 0x11
0x7d544  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x7d549  brtrue.s loc_7D58C
0x7d54b  ldarg.0
0x7d54c  ldc.i4.1
0x7d54d  dup
0x7d54e  stloc.0
0x7d54f  stfld    int32 <InvokeAsync>d__8::<>1__state
0x7d554  ldarg.0
0x7d555  ldloc.s  0x11
0x7d557  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <InvokeAsync>d__8::<>u__2
0x7d55c  ldarg.0
0x7d55d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <InvokeAsync>d__8::<>t__builder
0x7d562  ldloca.s 0x11
0x7d564  ldarg.0
0x7d565  call     T0x2B000531
0x7d56a  leave    loc_7D63D
0x7d56f  ldarg.0
0x7d570  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <InvokeAsync>d__8::<>u__2
0x7d575  stloc.s  0x11
0x7d577  ldarg.0
0x7d578  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <InvokeAsync>d__8::<>u__2
0x7d57d  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x7d583  ldarg.0
0x7d584  ldc.i4.m1
0x7d585  dup
0x7d586  stloc.0
0x7d587  stfld    int32 <InvokeAsync>d__8::<>1__state
0x7d58c  ldloca.s 0x11
0x7d58e  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x7d593  ldloc.1
0x7d594  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x7d599  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IInstallChannelLifetimeManager Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_InstallChannelLifetimeManager()
0x7d59e  ldc.i4.0
0x7d59f  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.IInstallChannelLifetimeManager::set_CleanupInstallChannelsOnDispose(bool value)
0x7d5a4  ldloc.1
0x7d5a5  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x7d5aa  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x7d5af  dup
0x7d5b0  brtrue.s loc_7D5B5
0x7d5b2  pop
0x7d5b3  br.s     loc_7D5C4
0x7d5b5  ldstr    aInstallerSelfU_0// "Installer self-update completed. Reques"...
0x7d5ba  call     T0x2B000010
0x7d5bf  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7d5c4  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::.ctor()
0x7d5c9  dup
0x7d5ca  ldc.i4.1
0x7d5cb  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::set_AutoShutdown(bool)
0x7d5d0  stloc.2
0x7d5d1  leave.s  loc_7D629
0x7d5d3  ldloc.0
0x7d5d4  ldc.i4.0
0x7d5d5  bge.s    loc_7D5EA
0x7d5d7  ldarg.0
0x7d5d8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess <InvokeAsync>d__8::<process>5__2
0x7d5dd  brfalse.s loc_7D5EA
0x7d5df  ldarg.0
0x7d5e0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess <InvokeAsync>d__8::<process>5__2
0x7d5e5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7d5ea  endfinally
0x7d5eb  stloc.s  0x12
  ... truncated ...
```
