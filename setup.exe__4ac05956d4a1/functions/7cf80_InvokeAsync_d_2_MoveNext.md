# <InvokeAsync>d__2::MoveNext

- ea: `0x7cf80`
- end: `0x7d230`
- name: `<InvokeAsync>d__2::MoveNext`
- size: `688`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0xa750`
- `0x21a60`
- `0x2c4b0`
- `0x2c4d0`
- `0x2c510`
- `0x3e3c0`
- `0x40b30`
- `0x7cf80`

## string_xrefs

- `0x7d067`: `Failed to finalize the installer update: {0}, {1}`
- `0x7d090`: `InstallerUpdateFailed`

## pseudocode

```c

```

## disassembly

```asm
0x7cf80  ldarg.0
0x7cf81  ldfld    int32 <InvokeAsync>d__2::<>1__state
0x7cf86  stloc.0
0x7cf87  ldarg.0
0x7cf88  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdateFinalizer <InvokeAsync>d__2::<>4__this
0x7cf8d  stloc.1
0x7cf8e  ldloc.0
0x7cf8f  ldc.i4.1
0x7cf90  pop
0x7cf91  pop
0x7cf92  nop
0x7cf93  ldloc.0
0x7cf94  brfalse.s loc_7CF9D
0x7cf96  ldloc.0
0x7cf97  ldc.i4.1
0x7cf98  beq      loc_7D0EB
0x7cf9d  nop
0x7cf9e  ldloc.0
0x7cf9f  brfalse.s loc_7CFEF
0x7cfa1  ldarg.0
0x7cfa2  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerService <InvokeAsync>d__2::installerService
0x7cfa7  ldloc.1
0x7cfa8  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x7cfad  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_SettingsService()
0x7cfb2  ldarg.0
0x7cfb3  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <InvokeAsync>d__2::token
0x7cfb8  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerService::FinalizeInstallerUpdateAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService settings, valuetype [mscorlib]System.Threading.CancellationToken token)
0x7cfbd  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x7cfc2  stloc.3
0x7cfc3  ldloca.s 3
0x7cfc5  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x7cfca  brtrue.s loc_7D00B
0x7cfcc  ldarg.0
0x7cfcd  ldc.i4.0
0x7cfce  dup
0x7cfcf  stloc.0
0x7cfd0  stfld    int32 <InvokeAsync>d__2::<>1__state
0x7cfd5  ldarg.0
0x7cfd6  ldloc.3
0x7cfd7  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <InvokeAsync>d__2::<>u__1
0x7cfdc  ldarg.0
0x7cfdd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <InvokeAsync>d__2::<>t__builder
0x7cfe2  ldloca.s 3
0x7cfe4  ldarg.0
0x7cfe5  call     T0x2B00052E
0x7cfea  leave    loc_7D22F
0x7cfef  ldarg.0
0x7cff0  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <InvokeAsync>d__2::<>u__1
0x7cff5  stloc.3
0x7cff6  ldarg.0
0x7cff7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <InvokeAsync>d__2::<>u__1
0x7cffc  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x7d002  ldarg.0
0x7d003  ldc.i4.m1
0x7d004  dup
0x7d005  stloc.0
0x7d006  stfld    int32 <InvokeAsync>d__2::<>1__state
0x7d00b  ldloca.s 3
0x7d00d  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x7d012  leave    loc_7D0E0
0x7d017  isinst   [mscorlib]System.Exception
0x7d01c  dup
0x7d01d  brtrue.s loc_7D023
0x7d01f  pop
0x7d020  ldc.i4.0
0x7d021  br.s     loc_7D02F
0x7d023  stloc.s  4
0x7d025  ldloc.s  4
0x7d027  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::IsOperationCanceledException(class [mscorlib]System.Exception error)
0x7d02c  ldc.i4.0
0x7d02d  cgt.un
0x7d02f  endfilter
0x7d031  pop
0x7d032  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::.ctor()
0x7d037  dup
0x7d038  ldloc.s  4
0x7d03a  ldnull
0x7d03b  call     class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ExtensionMethods::GetErrorInformation(class [mscorlib]System.Exception, string)
0x7d040  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::set_Error(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation)
0x7d045  dup
0x7d046  ldc.i4.1
0x7d047  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::set_IsCanceled(bool)
0x7d04c  stloc.2
0x7d04d  leave    loc_7D21B
0x7d052  stloc.s  5
0x7d054  ldloc.1
0x7d055  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x7d05a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x7d05f  dup
0x7d060  brtrue.s loc_7D065
0x7d062  pop
0x7d063  br.s     loc_7D08B
0x7d065  ldloc.s  5
0x7d067  ldstr    aFailedToFinali_2// "Failed to finalize the installer update"...
0x7d06c  ldc.i4.2
0x7d06d  newarr   [mscorlib]System.Object
0x7d072  dup
0x7d073  ldc.i4.0
0x7d074  ldloc.s  5
0x7d076  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7d07b  stelem.ref
0x7d07c  dup
0x7d07d  ldc.i4.1
0x7d07e  ldloc.s  5
0x7d080  callvirt instance string [mscorlib]System.Object::ToString()
0x7d085  stelem.ref
0x7d086  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x7d08b  call     class [mscorlib]System.Resources.ResourceManager [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ResourceManager()
0x7d090  ldstr    aInstallerupdat_1// "InstallerUpdateFailed"
0x7d095  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7d09a  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x7d09f  stloc.s  6
0x7d0a1  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::.ctor()
0x7d0a6  dup
0x7d0a7  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_InstallerUpdateFailed()
0x7d0ac  ldloc.s  6
0x7d0ae  ldloc.s  5
0x7d0b0  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x7d0b5  ldloc.s  5
0x7d0b7  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x7d0bc  ldloc.s  5
0x7d0be  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x7d0c3  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7d0c8  ldnull
0x7d0c9  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation::.ctor(string, string, string, int32, string, string)
0x7d0ce  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::set_Error(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation)
0x7d0d3  dup
0x7d0d4  ldc.i4.0
0x7d0d5  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::set_IsCanceled(bool)
0x7d0da  stloc.2
0x7d0db  leave    loc_7D21B
0x7d0e0  ldloc.1
0x7d0e1  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdateFinalizer::installer
0x7d0e6  brfalse  loc_7D1C0
0x7d0eb  nop
0x7d0ec  ldloc.0
0x7d0ed  ldc.i4.1
0x7d0ee  beq.s    loc_7D163
0x7d0f0  ldloc.1
0x7d0f1  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdateFinalizer::installer
0x7d0f6  ldloc.1
0x7d0f7  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::OnProgress(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs args)
0x7d0fd  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs>::.ctor(object, native int)
0x7d102  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller::add_Progress(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs>)
0x7d107  ldloc.1
0x7d108  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdateFinalizer::installer
0x7d10d  ldloc.1
0x7d10e  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::OnPausable(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.PausableEventArgs args)
0x7d114  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.PausableEventArgs>::.ctor(object, native int)
0x7d119  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller::add_Pausable(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.PausableEventArgs>)
0x7d11e  ldloc.1
0x7d11f  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdateFinalizer::installer
0x7d124  ldarg.0
0x7d125  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <InvokeAsync>d__2::token
0x7d12a  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller::InvokeAsync(valuetype [mscorlib]System.Threading.CancellationToken)
0x7d12f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::GetAwaiter()
0x7d134  stloc.s  7
0x7d136  ldloca.s 7
0x7d138  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::get_IsCompleted()
0x7d13d  brtrue.s loc_7D180
0x7d13f  ldarg.0
0x7d140  ldc.i4.1
0x7d141  dup
0x7d142  stloc.0
0x7d143  stfld    int32 <InvokeAsync>d__2::<>1__state
0x7d148  ldarg.0
0x7d149  ldloc.s  7
0x7d14b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <InvokeAsync>d__2::<>u__2
0x7d150  ldarg.0
0x7d151  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <InvokeAsync>d__2::<>t__builder
0x7d156  ldloca.s 7
0x7d158  ldarg.0
0x7d159  call     T0x2B00052F
0x7d15e  leave    loc_7D22F
0x7d163  ldarg.0
0x7d164  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <InvokeAsync>d__2::<>u__2
0x7d169  stloc.s  7
0x7d16b  ldarg.0
0x7d16c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <InvokeAsync>d__2::<>u__2
0x7d171  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>
0x7d177  ldarg.0
0x7d178  ldc.i4.m1
0x7d179  dup
0x7d17a  stloc.0
0x7d17b  stfld    int32 <InvokeAsync>d__2::<>1__state
0x7d180  ldloca.s 7
0x7d182  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::GetResult()
0x7d187  stloc.2
0x7d188  leave    loc_7D21B
0x7d18d  ldloc.0
0x7d18e  ldc.i4.0
0x7d18f  bge.s    loc_7D1BF
0x7d191  ldloc.1
0x7d192  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdateFinalizer::installer
0x7d197  ldloc.1
0x7d198  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::OnProgress(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs args)
0x7d19e  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs>::.ctor(object, native int)
0x7d1a3  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller::remove_Progress(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs>)
0x7d1a8  ldloc.1
0x7d1a9  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdateFinalizer::installer
0x7d1ae  ldloc.1
0x7d1af  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::OnPausable(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.PausableEventArgs args)
0x7d1b5  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.PausableEventArgs>::.ctor(object, native int)
0x7d1ba  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller::remove_Pausable(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.PausableEventArgs>)
0x7d1bf  endfinally
0x7d1c0  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::.ctor()
0x7d1c5  stloc.2
0x7d1c6  leave.s  loc_7D21B
0x7d1c8  stloc.s  8
0x7d1ca  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::.ctor()
0x7d1cf  dup
0x7d1d0  ldloc.s  8
0x7d1d2  ldnull
0x7d1d3  call     class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ExtensionMethods::GetErrorInformation(class [mscorlib]System.Exception, string)
0x7d1d8  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::set_Error(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation)
0x7d1dd  dup
0x7d1de  ldloc.s  8
0x7d1e0  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::IsOperationCanceledException(class [mscorlib]System.Exception error)
0x7d1e5  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::set_IsCanceled(bool)
0x7d1ea  stloc.2
0x7d1eb  leave.s  loc_7D21B
0x7d1ed  ldloc.0
0x7d1ee  ldc.i4.0
0x7d1ef  bge.s    loc_7D201
0x7d1f1  ldloc.1
0x7d1f2  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x7d1f7  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_InstallerSettingsService()
0x7d1fc  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService::ResetContinueSettings()
0x7d201  endfinally
0x7d202  stloc.s  9
0x7d204  ldarg.0
0x7d205  ldc.i4.s 0xFE
0x7d207  stfld    int32 <InvokeAsync>d__2::<>1__state
0x7d20c  ldarg.0
0x7d20d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <InvokeAsync>d__2::<>t__builder
0x7d212  ldloc.s  9
0x7d214  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::SetException(class [mscorlib]System.Exception)
0x7d219  leave.s  loc_7D22F
0x7d21b  ldarg.0
0x7d21c  ldc.i4.s 0xFE
0x7d21e  stfld    int32 <InvokeAsync>d__2::<>1__state
0x7d223  ldarg.0
0x7d224  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <InvokeAsync>d__2::<>t__builder
0x7d229  ldloc.2
0x7d22a  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::SetResult(var<u1>)
0x7d22f  ret
```
