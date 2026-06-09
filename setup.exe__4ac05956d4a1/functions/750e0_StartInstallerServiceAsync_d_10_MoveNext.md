# <StartInstallerServiceAsync>d__10::MoveNext

- ea: `0x750e0`
- end: `0x752cd`
- name: `<StartInstallerServiceAsync>d__10::MoveNext`
- size: `493`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, installer_update`

## callees

- `0x219d0`
- `0x219e0`
- `0x21a20`
- `0x22c90`
- `0x29bf0`
- `0x2dd90`
- `0x2f2c0`
- `0x2f300`
- `0x2f350`
- `0x2f360`
- `0x34a30`
- `0x750e0`

## string_xrefs

- `0x7527c`: `ElevationServiceStartInstallerError_Args1`

## pseudocode

```c

```

## disassembly

```asm
0x750e0  ldarg.0
0x750e1  ldfld    int32 <StartInstallerServiceAsync>d__10::<>1__state
0x750e6  stloc.0
0x750e7  ldarg.0
0x750e8  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector <StartInstallerServiceAsync>d__10::<>4__this
0x750ed  stloc.1
0x750ee  ldloc.0
0x750ef  brfalse  loc_7523A
0x750f4  ldarg.0
0x750f5  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.IRpcStream <StartInstallerServiceAsync>d__10::windowsServiceStream
0x750fa  callvirt instance class [mscorlib]System.IO.Stream Microsoft.VisualStudio.Setup.Installer.Rpc.IRpcStream::get_BaseStream()
0x750ff  call     T0x2B0004CF
0x75104  ldloc.1
0x75105  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector::serviceOptions
0x7510a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_Telemetry()
0x7510f  dup
0x75110  brtrue.s loc_75116
0x75112  pop
0x75113  ldnull
0x75114  br.s     loc_7511B
0x75116  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::SerializeSettings()
0x7511b  stloc.3
0x7511c  ldloc.1
0x7511d  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector::serviceOptions
0x75122  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.Globalization.ILocaleService Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_LocaleService()
0x75127  dup
0x75128  brtrue.s loc_7512E
0x7512a  pop
0x7512b  ldnull
0x7512c  br.s     loc_7513F
0x7512e  callvirt instance class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.Installer.Services.Globalization.ILocaleService::GetLocale()
0x75133  dup
0x75134  brtrue.s loc_7513A
0x75136  pop
0x75137  ldnull
0x75138  br.s     loc_7513F
0x7513a  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x7513f  dup
0x75140  brtrue.s loc_75152
0x75142  pop
0x75143  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x75148  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentUICulture()
0x7514d  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x75152  stloc.s  4
0x75154  ldloc.1
0x75155  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector::serviceOptions
0x7515a  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_InstallerSettings()
0x7515f  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService::get_CampaignId()
0x75164  stloc.s  5
0x75166  ldloc.1
0x75167  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector::serviceOptions
0x7516c  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_InstallerSettings()
0x75171  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService::get_Passive()
0x75176  stloc.s  6
0x75178  ldloc.1
0x75179  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector::serviceOptions
0x7517e  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_InstallerSettings()
0x75183  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService::get_Quiet()
0x75188  stloc.s  7
0x7518a  ldloc.1
0x7518b  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector::serviceOptions
0x75190  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IWindowService Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_WindowService()
0x75195  dup
0x75196  brtrue.s loc_7519D
0x75198  pop
0x75199  ldc.i4.0
0x7519a  conv.i8
0x7519b  br.s     loc_751AB
0x7519d  callvirt instance native int Microsoft.VisualStudio.Setup.Installer.Services.IWindowService::GetWindowHandle()
0x751a2  stloc.s  0xB
0x751a4  ldloca.s 0xB
0x751a6  call     instance int64 [mscorlib]System.IntPtr::ToInt64()
0x751ab  stloc.s  8
0x751ad  newobj   instance void [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest::.ctor()
0x751b2  dup
0x751b3  ldloc.1
0x751b4  ldfld    string Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector::activityId
0x751b9  callvirt instance modreq([VSInstallerElevationService.Contracts]System.Runtime.CompilerServices.IsExternalInit) void [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest::set_ActivityId(string)
0x751be  dup
0x751bf  ldloc.s  5
0x751c1  callvirt instance modreq([VSInstallerElevationService.Contracts]System.Runtime.CompilerServices.IsExternalInit) void [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest::set_CampaignId(string)
0x751c6  dup
0x751c7  ldloc.s  8
0x751c9  callvirt instance modreq([VSInstallerElevationService.Contracts]System.Runtime.CompilerServices.IsExternalInit) void [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest::set_Handle(int64)
0x751ce  dup
0x751cf  ldloc.s  6
0x751d1  callvirt instance modreq([VSInstallerElevationService.Contracts]System.Runtime.CompilerServices.IsExternalInit) void [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest::set_IsPassive(bool)
0x751d6  dup
0x751d7  ldloc.s  7
0x751d9  callvirt instance modreq([VSInstallerElevationService.Contracts]System.Runtime.CompilerServices.IsExternalInit) void [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest::set_IsQuiet(bool)
0x751de  dup
0x751df  ldloc.s  4
0x751e1  callvirt instance modreq([VSInstallerElevationService.Contracts]System.Runtime.CompilerServices.IsExternalInit) void [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest::set_Locale(string)
0x751e6  dup
0x751e7  ldloc.3
0x751e8  callvirt instance modreq([VSInstallerElevationService.Contracts]System.Runtime.CompilerServices.IsExternalInit) void [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest::set_SerializedSession(string)
0x751ed  stloc.s  9
0x751ef  ldloc.s  9
0x751f1  ldarg.0
0x751f2  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <StartInstallerServiceAsync>d__10::token
0x751f7  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult> [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.IElevationRequestService::StartInstallerServiceAsync(class [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest, valuetype [mscorlib]System.Threading.CancellationToken)
0x751fc  ldc.i4.0
0x751fd  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult>::ConfigureAwait(!!T0)
0x75202  stloc.s  0xD
0x75204  ldloca.s 0xD
0x75206  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult>::GetAwaiter()
0x7520b  stloc.s  0xC
0x7520d  ldloca.s 0xC
0x7520f  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult>::get_IsCompleted()
0x75214  brtrue.s loc_75257
0x75216  ldarg.0
0x75217  ldc.i4.0
0x75218  dup
0x75219  stloc.0
0x7521a  stfld    int32 <StartInstallerServiceAsync>d__10::<>1__state
0x7521f  ldarg.0
0x75220  ldloc.s  0xC
0x75222  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult> <StartInstallerServiceAsync>d__10::<>u__1
0x75227  ldarg.0
0x75228  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <StartInstallerServiceAsync>d__10::<>t__builder
0x7522d  ldloca.s 0xC
0x7522f  ldarg.0
0x75230  call     T0x2B0004D0
0x75235  leave    loc_752CC
0x7523a  ldarg.0
0x7523b  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult> <StartInstallerServiceAsync>d__10::<>u__1
0x75240  stloc.s  0xC
0x75242  ldarg.0
0x75243  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult> <StartInstallerServiceAsync>d__10::<>u__1
0x75248  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult>
0x7524e  ldarg.0
0x7524f  ldc.i4.m1
0x75250  dup
0x75251  stloc.0
0x75252  stfld    int32 <StartInstallerServiceAsync>d__10::<>1__state
0x75257  ldloca.s 0xC
0x75259  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult>::GetResult()
0x7525e  stloc.s  0xA
0x75260  ldloc.s  0xA
0x75262  callvirt instance bool [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult::get_IsSuccess()
0x75267  brfalse.s loc_75277
0x75269  ldloc.s  0xA
0x7526b  callvirt instance string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult::get_PipeName()
0x75270  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x75275  brfalse.s loc_75295
0x75277  call     class [mscorlib]System.Resources.ResourceManager [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ResourceManager()
0x7527c  ldstr    aElevationservi_8// "ElevationServiceStartInstallerError_Arg"...
0x75281  ldc.i4.1
0x75282  newarr   [mscorlib]System.Object
0x75287  dup
0x75288  ldc.i4.0
0x75289  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceDisplayName
0x7528e  stelem.ref
0x7528f  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Pipe.LocalizedPipeException::.ctor(class [mscorlib]System.Resources.ResourceManager resources, string resourceId, object[] args)
0x75294  throw
0x75295  ldloc.s  0xA
0x75297  callvirt instance string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult::get_PipeName()
0x7529c  stloc.2
0x7529d  leave.s  loc_752B8
0x7529f  stloc.s  0xE
0x752a1  ldarg.0
0x752a2  ldc.i4.s 0xFE
0x752a4  stfld    int32 <StartInstallerServiceAsync>d__10::<>1__state
0x752a9  ldarg.0
0x752aa  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <StartInstallerServiceAsync>d__10::<>t__builder
0x752af  ldloc.s  0xE
0x752b1  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetException(class [mscorlib]System.Exception)
0x752b6  leave.s  loc_752CC
0x752b8  ldarg.0
0x752b9  ldc.i4.s 0xFE
0x752bb  stfld    int32 <StartInstallerServiceAsync>d__10::<>1__state
0x752c0  ldarg.0
0x752c1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <StartInstallerServiceAsync>d__10::<>t__builder
0x752c6  ldloc.2
0x752c7  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetResult(var<u1>)
0x752cc  ret
```
