# <HandleAsync>d__2::MoveNext

- ea: `0x88f60`
- end: `0x892e3`
- name: `<HandleAsync>d__2::MoveNext`
- size: `899`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0xa5d0`
- `0xa750`
- `0x229c0`
- `0x2b9c0`
- `0x2ba50`
- `0x2baa0`
- `0x54020`
- `0x88f60`

## string_xrefs

- `0x8908c`: `InstallerUpdateRequired`
- `0x8912d`: `Failed to cancel channel update check`
- `0x891fa`: `Unhandled exception {0} encountered determining install operation result - {1}`

## pseudocode

```c

```

## disassembly

```asm
0x88f60  ldarg.0
0x88f61  ldfld    int32 valuetype <HandleAsync>d__2<var<u1>>::<>1__state
0x88f66  stloc.0
0x88f67  ldarg.0
0x88f68  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.InstallOperationCommandBase`1<var<u1>> valuetype <HandleAsync>d__2<var<u1>>::<>4__this
0x88f6d  stloc.1
0x88f6e  ldloc.0
0x88f6f  switch   loc_88F92, loc_88F92, loc_891A7, loc_8927E
0x88f84  ldarg.0
0x88f85  ldc.i4.0
0x88f86  stfld    bool valuetype <HandleAsync>d__2<var<u1>>::<retry>5__2
0x88f8b  ldarg.0
0x88f8c  ldc.i4.0
0x88f8d  stfld    int32 valuetype <HandleAsync>d__2<var<u1>>::<>7__wrap3
0x88f92  nop
0x88f93  ldloc.0
0x88f94  brfalse.s loc_88FE5
0x88f96  ldloc.0
0x88f97  ldc.i4.1
0x88f98  beq      loc_89049
0x88f9d  ldloc.1
0x88f9e  ldarg.0
0x88f9f  ldfld    var<u1> valuetype <HandleAsync>d__2<var<u1>>::parameter
0x88fa4  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> class Microsoft.VisualStudio.Setup.Installer.Commands.InstallOperationCommandBase`1<var<u1>>::GetResultAsync(var<u1>)
0x88fa9  ldc.i4.0
0x88faa  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::ConfigureAwait(!!T0)
0x88faf  stloc.s  4
0x88fb1  ldloca.s 4
0x88fb3  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::GetAwaiter()
0x88fb8  stloc.3
0x88fb9  ldloca.s 3
0x88fbb  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::get_IsCompleted()
0x88fc0  brtrue.s loc_89001
0x88fc2  ldarg.0
0x88fc3  ldc.i4.0
0x88fc4  dup
0x88fc5  stloc.0
0x88fc6  stfld    int32 valuetype <HandleAsync>d__2<var<u1>>::<>1__state
0x88fcb  ldarg.0
0x88fcc  ldloc.3
0x88fcd  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> valuetype <HandleAsync>d__2<var<u1>>::<>u__1
0x88fd2  ldarg.0
0x88fd3  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder valuetype <HandleAsync>d__2<var<u1>>::<>t__builder
0x88fd8  ldloca.s 3
0x88fda  ldarg.0
0x88fdb  call     T0x2B0005C1
0x88fe0  leave    loc_892E2
0x88fe5  ldarg.0
0x88fe6  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> valuetype <HandleAsync>d__2<var<u1>>::<>u__1
0x88feb  stloc.3
0x88fec  ldarg.0
0x88fed  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> valuetype <HandleAsync>d__2<var<u1>>::<>u__1
0x88ff2  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>
0x88ff8  ldarg.0
0x88ff9  ldc.i4.m1
0x88ffa  dup
0x88ffb  stloc.0
0x88ffc  stfld    int32 valuetype <HandleAsync>d__2<var<u1>>::<>1__state
0x89001  ldloca.s 3
0x89003  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::GetResult()
0x89008  stloc.2
0x89009  ldloc.1
0x8900a  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Commands.IOperationResultHandler class Microsoft.VisualStudio.Setup.Installer.Commands.InstallOperationCommandBase`1<var<u1>>::get_ResultHandler()
0x8900f  ldloc.2
0x89010  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.Commands.IOperationResultHandler::HandleAsync(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult result)
0x89015  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x8901a  stloc.s  5
0x8901c  ldloca.s 5
0x8901e  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x89023  brtrue.s loc_89066
0x89025  ldarg.0
0x89026  ldc.i4.1
0x89027  dup
0x89028  stloc.0
0x89029  stfld    int32 valuetype <HandleAsync>d__2<var<u1>>::<>1__state
0x8902e  ldarg.0
0x8902f  ldloc.s  5
0x89031  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter valuetype <HandleAsync>d__2<var<u1>>::<>u__2
0x89036  ldarg.0
0x89037  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder valuetype <HandleAsync>d__2<var<u1>>::<>t__builder
0x8903c  ldloca.s 5
0x8903e  ldarg.0
0x8903f  call     T0x2B0005C2
0x89044  leave    loc_892E2
0x89049  ldarg.0
0x8904a  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter valuetype <HandleAsync>d__2<var<u1>>::<>u__2
0x8904f  stloc.s  5
0x89051  ldarg.0
0x89052  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter valuetype <HandleAsync>d__2<var<u1>>::<>u__2
0x89057  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x8905d  ldarg.0
0x8905e  ldc.i4.m1
0x8905f  dup
0x89060  stloc.0
0x89061  stfld    int32 valuetype <HandleAsync>d__2<var<u1>>::<>1__state
0x89066  ldloca.s 5
0x89068  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x8906d  leave    loc_890F5
0x89072  stloc.s  6
0x89074  ldloc.1
0x89075  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions class Microsoft.VisualStudio.Setup.Installer.Commands.InstallOperationCommandBase`1<var<u1>>::get_ServiceOptions()
0x8907a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerBaseServiceOptions::get_Logger()
0x8907f  dup
0x89080  brtrue.s loc_89085
0x89082  pop
0x89083  br.s     loc_890A5
0x89085  ldloc.s  6
0x89087  call     class [mscorlib]System.Resources.ResourceManager [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ResourceManager()
0x8908c  ldstr    aInstallerupdat_2// "InstallerUpdateRequired"
0x89091  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x89096  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x8909b  call     T0x2B000010
0x890a0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x890a5  ldloc.1
0x890a6  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions class Microsoft.VisualStudio.Setup.Installer.Commands.InstallOperationCommandBase`1<var<u1>>::get_ServiceOptions()
0x890ab  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions::get_InstallerSettings()
0x890b0  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::IsQuietOrPassive(class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService installerSettings)
0x890b5  brfalse.s loc_890CD
0x890b7  ldloc.1
0x890b8  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions class Microsoft.VisualStudio.Setup.Installer.Commands.InstallOperationCommandBase`1<var<u1>>::get_ServiceOptions()
0x890bd  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions::get_ShutdownService()
0x890c2  ldc.i4.1
0x890c3  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_InstallerUpdateRequired()
0x890c8  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService::Shutdown(int32 exitCode, string message)
0x890cd  leave.s  loc_890F5
0x890cf  stloc.s  7
0x890d1  ldarg.0
0x890d2  ldloc.s  7
0x890d4  stfld    object valuetype <HandleAsync>d__2<var<u1>>::<>7__wrap2
0x890d9  ldarg.0
0x890da  ldc.i4.1
0x890db  stfld    int32 valuetype <HandleAsync>d__2<var<u1>>::<>7__wrap3
0x890e0  leave.s  loc_890F5
0x890e2  stloc.s  8
0x890e4  ldarg.0
0x890e5  ldloc.s  8
0x890e7  stfld    object valuetype <HandleAsync>d__2<var<u1>>::<>7__wrap2
0x890ec  ldarg.0
0x890ed  ldc.i4.2
0x890ee  stfld    int32 valuetype <HandleAsync>d__2<var<u1>>::<>7__wrap3
0x890f3  leave.s  loc_890F5
0x890f5  ldarg.0
0x890f6  ldfld    int32 valuetype <HandleAsync>d__2<var<u1>>::<>7__wrap3
0x890fb  stloc.s  9
0x890fd  ldloc.s  9
0x890ff  ldc.i4.1
0x89100  beq.s    loc_8910F
0x89102  ldloc.s  9
0x89104  ldc.i4.2
0x89105  beq      loc_891DA
0x8910a  br       loc_892A2
0x8910f  ldarg.0
0x89110  ldfld    object valuetype <HandleAsync>d__2<var<u1>>::<>7__wrap2
0x89115  castclass Microsoft.VisualStudio.Setup.ChannelsLockedException
0x8911a  stloc.s  0xA
0x8911c  ldloc.1
0x8911d  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions class Microsoft.VisualStudio.Setup.Installer.Commands.InstallOperationCommandBase`1<var<u1>>::get_ServiceOptions()
0x89122  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerBaseServiceOptions::get_Logger()
0x89127  dup
0x89128  brtrue.s loc_8912D
0x8912a  pop
0x8912b  br.s     loc_8913C
0x8912d  ldstr    aFailedToCancel// "Failed to cancel channel update check"
0x89132  call     T0x2B000010
0x89137  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x8913c  ldloc.1
0x8913d  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions class Microsoft.VisualStudio.Setup.Installer.Commands.InstallOperationCommandBase`1<var<u1>>::get_ServiceOptions()
0x89142  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions::get_InstallerSettings()
0x89147  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::IsQuietOrPassive(class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService installerSettings)
0x8914c  brfalse.s loc_8916B
0x8914e  ldloc.1
0x8914f  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions class Microsoft.VisualStudio.Setup.Installer.Commands.InstallOperationCommandBase`1<var<u1>>::get_ServiceOptions()
0x89154  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions::get_ShutdownService()
0x89159  ldc.i4.1
0x8915a  ldloc.s  0xA
0x8915c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x89161  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService::Shutdown(int32 exitCode, string message)
0x89166  leave    loc_892CF
0x8916b  ldloc.1
0x8916c  ldloc.s  0xA
0x8916e  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> class Microsoft.VisualStudio.Setup.Installer.Commands.InstallOperationCommandBase`1<var<u1>>::ShouldRetryChannelLockAsync(class Microsoft.VisualStudio.Setup.ChannelsLockedException)
0x89173  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x89178  stloc.s  0xC
0x8917a  ldloca.s 0xC
0x8917c  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x89181  brtrue.s loc_891C4
0x89183  ldarg.0
0x89184  ldc.i4.2
0x89185  dup
0x89186  stloc.0
0x89187  stfld    int32 valuetype <HandleAsync>d__2<var<u1>>::<>1__state
0x8918c  ldarg.0
0x8918d  ldloc.s  0xC
0x8918f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> valuetype <HandleAsync>d__2<var<u1>>::<>u__3
0x89194  ldarg.0
0x89195  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder valuetype <HandleAsync>d__2<var<u1>>::<>t__builder
0x8919a  ldloca.s 0xC
0x8919c  ldarg.0
0x8919d  call     T0x2B0005C3
0x891a2  leave    loc_892E2
0x891a7  ldarg.0
0x891a8  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> valuetype <HandleAsync>d__2<var<u1>>::<>u__3
0x891ad  stloc.s  0xC
0x891af  ldarg.0
0x891b0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> valuetype <HandleAsync>d__2<var<u1>>::<>u__3
0x891b5  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x891bb  ldarg.0
0x891bc  ldc.i4.m1
0x891bd  dup
0x891be  stloc.0
0x891bf  stfld    int32 valuetype <HandleAsync>d__2<var<u1>>::<>1__state
0x891c4  ldloca.s 0xC
0x891c6  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x891cb  stloc.s  0xB
0x891cd  ldarg.0
0x891ce  ldloc.s  0xB
0x891d0  stfld    bool valuetype <HandleAsync>d__2<var<u1>>::<retry>5__2
0x891d5  br       loc_892A2
0x891da  ldarg.0
0x891db  ldfld    object valuetype <HandleAsync>d__2<var<u1>>::<>7__wrap2
0x891e0  castclass [mscorlib]System.Exception
0x891e5  stloc.s  0xD
0x891e7  ldloc.1
0x891e8  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions class Microsoft.VisualStudio.Setup.Installer.Commands.InstallOperationCommandBase`1<var<u1>>::get_ServiceOptions()
0x891ed  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerBaseServiceOptions::get_Logger()
0x891f2  dup
0x891f3  brtrue.s loc_891F8
0x891f5  pop
0x891f6  br.s     loc_8921E
0x891f8  ldloc.s  0xD
0x891fa  ldstr    aUnhandledExcep// "Unhandled exception {0} encountered det"...
0x891ff  ldc.i4.2
0x89200  newarr   [mscorlib]System.Object
0x89205  dup
0x89206  ldc.i4.0
0x89207  ldloc.s  0xD
0x89209  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x8920e  stelem.ref
0x8920f  dup
0x89210  ldc.i4.1
0x89211  ldloc.s  0xD
0x89213  callvirt instance string [mscorlib]System.Exception::get_Message()
0x89218  stelem.ref
0x89219  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x8921e  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::.ctor()
0x89223  dup
0x89224  ldloc.s  0xD
0x89226  ldnull
0x89227  call     class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ExtensionMethods::GetErrorInformation(class [mscorlib]System.Exception, string)
0x8922c  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::set_Error(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation)
0x89231  dup
0x89232  ldloc.s  0xD
0x89234  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::IsOperationCanceledException(class [mscorlib]System.Exception error)
0x89239  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::set_IsCanceled(bool)
0x8923e  stloc.s  0xE
0x89240  ldloc.1
0x89241  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Commands.IOperationResultHandler class Microsoft.VisualStudio.Setup.Installer.Commands.InstallOperationCommandBase`1<var<u1>>::get_ResultHandler()
0x89246  ldloc.s  0xE
0x89248  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.Commands.IOperationResultHandler::HandleAsync(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult result)
0x8924d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x89252  stloc.s  5
0x89254  ldloca.s 5
0x89256  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x8925b  brtrue.s loc_8929B
0x8925d  ldarg.0
0x8925e  ldc.i4.3
0x8925f  dup
0x89260  stloc.0
0x89261  stfld    int32 valuetype <HandleAsync>d__2<var<u1>>::<>1__state
0x89266  ldarg.0
0x89267  ldloc.s  5
0x89269  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter valuetype <HandleAsync>d__2<var<u1>>::<>u__2
0x8926e  ldarg.0
0x8926f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder valuetype <HandleAsync>d__2<var<u1>>::<>t__builder
0x89274  ldloca.s 5
0x89276  ldarg.0
0x89277  call     T0x2B0005C2
0x8927c  leave.s  loc_892E2
0x8927e  ldarg.0
0x8927f  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter valuetype <HandleAsync>d__2<var<u1>>::<>u__2
0x89284  stloc.s  5
0x89286  ldarg.0
0x89287  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter valuetype <HandleAsync>d__2<var<u1>>::<>u__2
0x8928c  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x89292  ldarg.0
0x89293  ldc.i4.m1
0x89294  dup
0x89295  stloc.0
0x89296  stfld    int32 valuetype <HandleAsync>d__2<var<u1>>::<>1__state
0x8929b  ldloca.s 5
0x8929d  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x892a2  ldarg.0
0x892a3  ldnull
0x892a4  stfld    object valuetype <HandleAsync>d__2<var<u1>>::<>7__wrap2
0x892a9  ldarg.0
0x892aa  ldfld    bool valuetype <HandleAsync>d__2<var<u1>>::<retry>5__2
0x892af  brtrue   loc_88F84
0x892b4  leave.s  loc_892CF
0x892b6  stloc.s  0xF
0x892b8  ldarg.0
  ... truncated ...
```
