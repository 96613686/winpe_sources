# <FinalizeInstallerUpdateAsync>d__13::MoveNext

- ea: `0x7b9f0`
- end: `0x7bb3f`
- name: `<FinalizeInstallerUpdateAsync>d__13::MoveNext`
- size: `335`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x7dd0`
- `0x7de0`
- `0x7e20`
- `0x2c4b0`
- `0x2c4c0`
- `0x3f6d0`
- `0x3f770`
- `0x7b9f0`

## string_xrefs

- `0x7bab2`: `Install operation failed with error: `
- `0x7ba23`: `Finalizing the installer update.`

## pseudocode

```c

```

## disassembly

```asm
0x7b9f0  ldarg.0
0x7b9f1  ldfld    int32 <FinalizeInstallerUpdateAsync>d__13::<>1__state
0x7b9f6  stloc.0
0x7b9f7  ldarg.0
0x7b9f8  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService <FinalizeInstallerUpdateAsync>d__13::<>4__this
0x7b9fd  stloc.1
0x7b9fe  ldloc.0
0x7b9ff  brfalse.s loc_7BA1E
0x7ba01  ldloc.1
0x7ba02  ldarg.0
0x7ba03  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService <FinalizeInstallerUpdateAsync>d__13::settings
0x7ba08  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::InitializeSettings(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService settings)
0x7ba0d  ldarg.0
0x7ba0e  ldloc.1
0x7ba0f  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::serviceOptions
0x7ba14  callvirt instance class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_InstallerUpdateManager()
0x7ba19  stfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager <FinalizeInstallerUpdateAsync>d__13::<updater>5__2
0x7ba1e  nop
0x7ba1f  ldloc.0
0x7ba20  brfalse.s loc_7BA8C
0x7ba22  ldloc.1
0x7ba23  ldstr    aFinalizingTheI// "Finalizing the installer update."
0x7ba28  call     T0x2B000010
0x7ba2d  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::TraceMessage(string format, object[] args)
0x7ba32  ldarg.0
0x7ba33  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager <FinalizeInstallerUpdateAsync>d__13::<updater>5__2
0x7ba38  ldloc.1
0x7ba39  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::OnProgress(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs e)
0x7ba3f  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs>::.ctor(object, native int)
0x7ba44  callvirt instance void Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager::add_Progress(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs> value)
0x7ba49  ldarg.0
0x7ba4a  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager <FinalizeInstallerUpdateAsync>d__13::<updater>5__2
0x7ba4f  ldarg.0
0x7ba50  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <FinalizeInstallerUpdateAsync>d__13::token
0x7ba55  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager::UpdateAsync([opt] valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x7ba5a  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x7ba5f  stloc.2
0x7ba60  ldloca.s 2
0x7ba62  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x7ba67  brtrue.s loc_7BAA8
0x7ba69  ldarg.0
0x7ba6a  ldc.i4.0
0x7ba6b  dup
0x7ba6c  stloc.0
0x7ba6d  stfld    int32 <FinalizeInstallerUpdateAsync>d__13::<>1__state
0x7ba72  ldarg.0
0x7ba73  ldloc.2
0x7ba74  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <FinalizeInstallerUpdateAsync>d__13::<>u__1
0x7ba79  ldarg.0
0x7ba7a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <FinalizeInstallerUpdateAsync>d__13::<>t__builder
0x7ba7f  ldloca.s 2
0x7ba81  ldarg.0
0x7ba82  call     T0x2B00051B
0x7ba87  leave    loc_7BB3E
0x7ba8c  ldarg.0
0x7ba8d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <FinalizeInstallerUpdateAsync>d__13::<>u__1
0x7ba92  stloc.2
0x7ba93  ldarg.0
0x7ba94  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <FinalizeInstallerUpdateAsync>d__13::<>u__1
0x7ba99  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x7ba9f  ldarg.0
0x7baa0  ldc.i4.m1
0x7baa1  dup
0x7baa2  stloc.0
0x7baa3  stfld    int32 <FinalizeInstallerUpdateAsync>d__13::<>1__state
0x7baa8  ldloca.s 2
0x7baaa  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x7baaf  leave.s  loc_7BAE4
0x7bab1  stloc.3
0x7bab2  ldstr    aInstallOperati// "Install operation failed with error: "
0x7bab7  ldloc.3
0x7bab8  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7babd  call     string [mscorlib]System.String::Concat(string, string)
0x7bac2  stloc.s  4
0x7bac4  ldloc.1
0x7bac5  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::serviceOptions
0x7baca  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x7bacf  dup
0x7bad0  brtrue.s loc_7BAD5
0x7bad2  pop
0x7bad3  br.s     loc_7BAE2
0x7bad5  ldloc.3
0x7bad6  ldloc.s  4
0x7bad8  call     T0x2B000010
0x7badd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x7bae2  rethrow
0x7bae4  leave.s  loc_7BB02
0x7bae6  ldloc.0
0x7bae7  ldc.i4.0
0x7bae8  bge.s    loc_7BB01
0x7baea  ldarg.0
0x7baeb  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager <FinalizeInstallerUpdateAsync>d__13::<updater>5__2
0x7baf0  ldloc.1
0x7baf1  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::OnProgress(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs e)
0x7baf7  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs>::.ctor(object, native int)
0x7bafc  callvirt instance void Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager::remove_Progress(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs> value)
0x7bb01  endfinally
0x7bb02  leave.s  loc_7BB24
0x7bb04  stloc.s  5
0x7bb06  ldarg.0
0x7bb07  ldc.i4.s 0xFE
0x7bb09  stfld    int32 <FinalizeInstallerUpdateAsync>d__13::<>1__state
0x7bb0e  ldarg.0
0x7bb0f  ldnull
0x7bb10  stfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager <FinalizeInstallerUpdateAsync>d__13::<updater>5__2
0x7bb15  ldarg.0
0x7bb16  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <FinalizeInstallerUpdateAsync>d__13::<>t__builder
0x7bb1b  ldloc.s  5
0x7bb1d  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x7bb22  leave.s  loc_7BB3E
0x7bb24  ldarg.0
0x7bb25  ldc.i4.s 0xFE
0x7bb27  stfld    int32 <FinalizeInstallerUpdateAsync>d__13::<>1__state
0x7bb2c  ldarg.0
0x7bb2d  ldnull
0x7bb2e  stfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerUpdateManager <FinalizeInstallerUpdateAsync>d__13::<updater>5__2
0x7bb33  ldarg.0
0x7bb34  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <FinalizeInstallerUpdateAsync>d__13::<>t__builder
0x7bb39  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x7bb3e  ret
```
