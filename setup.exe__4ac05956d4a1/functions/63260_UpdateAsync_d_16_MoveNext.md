# <UpdateAsync>d__16::MoveNext

- ea: `0x63260`
- end: `0x63656`
- name: `<UpdateAsync>d__16::MoveNext`
- size: `1014`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x7570`
- `0x75d0`
- `0x7630`
- `0x7640`
- `0x86b0`
- `0x87e0`
- `0x8840`
- `0x8890`
- `0x63260`

## string_xrefs

- `0x632e1`: `.complete`
- `0x634b7`: `.complete`
- `0x632ff`: `The installer has not been extracted successfully`
- `0x63333`: `Updating installer`
- `0x6341c`: `Failed to update source: {0}`
- `0x6345d`: `InstallerUpdateManager`
- `0x63471`: `UpdateDirectory`
- `0x634f6`: `Failed to delete file: {0}, error: {1}`
- `0x63541`: `Failed to schedule deleting directory on reboot: {0}`
- `0x6356f`: `Failed to schedule deleting directory on reboot: {0}, error: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x63260  ldarg.0
0x63261  ldfld    int32 <UpdateAsync>d__16::<>1__state
0x63266  stloc.0
0x63267  ldarg.0
0x63268  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager <UpdateAsync>d__16::<>4__this
0x6326d  stloc.1
0x6326e  ldloc.0
0x6326f  brfalse  loc_63392
0x63274  ldloc.0
0x63275  ldc.i4.1
0x63276  beq      loc_635D7
0x6327b  ldloc.1
0x6327c  ldfld    string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::temporaryInstallerDirectory
0x63281  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x63286  brfalse.s loc_632AC
0x63288  ldloc.1
0x63289  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x6328e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_ProcessService()
0x63293  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService::GetCurrentProcess()
0x63298  stloc.s  7
0x6329a  ldloc.1
0x6329b  ldloc.s  7
0x6329d  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess::get_MainModuleFileName()
0x632a2  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x632a7  stfld    string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::temporaryInstallerDirectory
0x632ac  ldarg.0
0x632ad  ldloc.1
0x632ae  ldflda   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) int32 Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::operationId
0x632b3  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x632b8  stfld    int32 <UpdateAsync>d__16::<operationId>5__2
0x632bd  ldloc.1
0x632be  ldarg.0
0x632bf  ldfld    int32 <UpdateAsync>d__16::<operationId>5__2
0x632c4  ldc.r8   1.0
0x632cd  ldc.r8   0.0
0x632d6  call     instance void Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::OnProgress(int32 operationId, float64 progress, float64 weight)
0x632db  ldloc.1
0x632dc  ldfld    string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::temporaryInstallerDirectory
0x632e1  ldstr    aComplete// ".complete"
0x632e6  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x632eb  stloc.2
0x632ec  ldloc.1
0x632ed  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x632f2  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_FileSystem()
0x632f7  ldloc.2
0x632f8  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x632fd  brtrue.s loc_6330A
0x632ff  ldstr    aTheInstallerHa// "The installer has not been extracted su"...
0x63304  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x63309  throw
0x6330a  ldloc.1
0x6330b  ldfld    string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::temporaryInstallerDirectory
0x63310  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.BootstrapperConstants::InstallerFileName
0x63315  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x6331a  stloc.3
0x6331b  ldloc.1
0x6331c  ldloc.3
0x6331d  call     instance void Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::ValidateMicrosoftSignature(string path)
0x63322  ldloc.1
0x63323  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x63328  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x6332d  dup
0x6332e  brtrue.s loc_63333
0x63330  pop
0x63331  br.s     loc_63342
0x63333  ldstr    aUpdatingInstal// "Updating installer"
0x63338  call     T0x2B000010
0x6333d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x63342  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.CopierSettings::.ctor()
0x63347  dup
0x63348  ldc.i4.1
0x63349  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.CopierSettings::set_DeleteAfterReboot(bool)
0x6334e  stloc.s  4
0x63350  ldloc.1
0x63351  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::get_Services()
0x63356  ldloc.s  4
0x63358  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Copier::.ctor(class [mscorlib]System.IServiceProvider, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.CopierSettings)
0x6335d  stloc.s  5
0x6335f  ldloc.s  5
0x63361  ldloc.1
0x63362  ldftn    instance void Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::<UpdateAsync>b__16_0(object source, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.CopierProgressEventArgs args)
0x63368  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.CopierProgressEventArgs>::.ctor(object, native int)
0x6336d  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Copier::add_Progress(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.CopierProgressEventArgs>)
0x63372  ldarg.0
0x63373  ldloc.1
0x63374  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x63379  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_FileSystem()
0x6337e  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_SharedProgramsDirectory()
0x63383  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.BootstrapperConstants::InstallerSubDirectory
0x63388  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x6338d  stfld    string <UpdateAsync>d__16::<finalInstallerDirectory>5__3
0x63392  nop
0x63393  ldloc.0
0x63394  brfalse.s loc_633F1
0x63396  ldloc.s  5
0x63398  ldloc.1
0x63399  ldfld    string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::temporaryInstallerDirectory
0x6339e  ldarg.0
0x6339f  ldfld    string <UpdateAsync>d__16::<finalInstallerDirectory>5__3
0x633a4  ldc.i4.1
0x633a5  newarr   [mscorlib]System.String
0x633aa  dup
0x633ab  ldc.i4.0
0x633ac  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceName
0x633b1  stelem.ref
0x633b2  ldarg.0
0x633b3  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <UpdateAsync>d__16::cancellationToken
0x633b8  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Copier::SafeUpdateDirectoryAsync(string, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, valuetype [mscorlib]System.Threading.CancellationToken)
0x633bd  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x633c2  stloc.s  8
0x633c4  ldloca.s 8
0x633c6  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x633cb  brtrue.s loc_6340E
0x633cd  ldarg.0
0x633ce  ldc.i4.0
0x633cf  dup
0x633d0  stloc.0
0x633d1  stfld    int32 <UpdateAsync>d__16::<>1__state
0x633d6  ldarg.0
0x633d7  ldloc.s  8
0x633d9  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <UpdateAsync>d__16::<>u__1
0x633de  ldarg.0
0x633df  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <UpdateAsync>d__16::<>t__builder
0x633e4  ldloca.s 8
0x633e6  ldarg.0
0x633e7  call     T0x2B00040A
0x633ec  leave    loc_63655
0x633f1  ldarg.0
0x633f2  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <UpdateAsync>d__16::<>u__1
0x633f7  stloc.s  8
0x633f9  ldarg.0
0x633fa  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <UpdateAsync>d__16::<>u__1
0x633ff  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x63405  ldarg.0
0x63406  ldc.i4.m1
0x63407  dup
0x63408  stloc.0
0x63409  stfld    int32 <UpdateAsync>d__16::<>1__state
0x6340e  ldloca.s 8
0x63410  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x63415  leave    loc_634B1
0x6341a  stloc.s  9
0x6341c  ldstr    aFailedToUpdate_0// "Failed to update source: {0}"
0x63421  ldloc.s  9
0x63423  callvirt instance string [mscorlib]System.Exception::get_Message()
0x63428  call     string [mscorlib]System.String::Format(string, object)
0x6342d  stloc.s  0xA
0x6342f  ldloc.1
0x63430  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x63435  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x6343a  dup
0x6343b  brtrue.s loc_63440
0x6343d  pop
0x6343e  br.s     loc_6344E
0x63440  ldloc.s  9
0x63442  ldloc.s  0xA
0x63444  call     T0x2B000010
0x63449  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x6344e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x63453  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x63458  stloc.s  0xC
0x6345a  dup
0x6345b  ldloc.s  0xC
0x6345d  ldstr    aInstallerupdat_0// "InstallerUpdateManager"
0x63462  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x63467  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x6346c  stloc.s  0xD
0x6346e  dup
0x6346f  ldloc.s  0xD
0x63471  ldstr    aUpdatedirector// "UpdateDirectory"
0x63476  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6347b  stloc.s  0xB
0x6347d  ldloc.1
0x6347e  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x63483  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Telemetry()
0x63488  dup
0x63489  brtrue.s loc_6348E
0x6348b  pop
0x6348c  br.s     loc_634A9
0x6348e  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x63493  ldloc.s  9
0x63495  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6349a  ldloc.s  0xB
0x6349c  ldloc.s  9
0x6349e  ldnull
0x6349f  ldc.i4.0
0x634a0  ldnull
0x634a1  ldc.i4.0
0x634a2  ldnull
0x634a3  ldc.i4.0
0x634a4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x634a9  ldloc.s  0xA
0x634ab  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x634b0  throw
0x634b1  ldarg.0
0x634b2  ldfld    string <UpdateAsync>d__16::<finalInstallerDirectory>5__3
0x634b7  ldstr    aComplete// ".complete"
0x634bc  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x634c1  stloc.s  6
0x634c3  ldloc.1
0x634c4  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x634c9  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_FileSystem()
0x634ce  ldloc.s  6
0x634d0  ldloca.s 0xE
0x634d2  ldc.i4.0
0x634d3  ldc.i4.2
0x634d4  ldc.i4   0x1F4
0x634d9  ldnull
0x634da  ldnull
0x634db  call     bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extensions::DeleteFileWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem, string, bool&, bool, int32, int32, class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool>, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger)
0x634e0  pop
0x634e1  leave.s  loc_63517
0x634e3  stloc.s  0xF
0x634e5  ldloc.1
0x634e6  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x634eb  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x634f0  dup
0x634f1  brtrue.s loc_634F6
0x634f3  pop
0x634f4  br.s     loc_63515
0x634f6  ldstr    aFailedToDelete_4// "Failed to delete file: {0}, error: {1}"
0x634fb  ldc.i4.2
0x634fc  newarr   [mscorlib]System.Object
0x63501  dup
0x63502  ldc.i4.0
0x63503  ldloc.s  6
0x63505  stelem.ref
0x63506  dup
0x63507  ldc.i4.1
0x63508  ldloc.s  0xF
0x6350a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6350f  stelem.ref
0x63510  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x63515  leave.s  loc_63517
0x63517  nop
0x63518  ldloc.1
0x63519  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x6351e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_FileSystem()
0x63523  ldloc.1
0x63524  ldfld    string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::temporaryInstallerDirectory
0x63529  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::ForceDeleteDirectoryOnReboot(string)
0x6352e  brtrue.s loc_6355A
0x63530  ldloc.1
0x63531  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x63536  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x6353b  dup
0x6353c  brtrue.s loc_63541
0x6353e  pop
0x6353f  br.s     loc_6355A
0x63541  ldstr    aFailedToSchedu// "Failed to schedule deleting directory o"...
0x63546  ldc.i4.1
0x63547  newarr   [mscorlib]System.Object
0x6354c  dup
0x6354d  ldc.i4.0
0x6354e  ldloc.1
0x6354f  ldfld    string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::temporaryInstallerDirectory
0x63554  stelem.ref
0x63555  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x6355a  leave.s  loc_63594
0x6355c  stloc.s  0x10
0x6355e  ldloc.1
0x6355f  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x63564  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x63569  dup
0x6356a  brtrue.s loc_6356F
0x6356c  pop
0x6356d  br.s     loc_63592
0x6356f  ldstr    aFailedToSchedu_0// "Failed to schedule deleting directory o"...
0x63574  ldc.i4.2
0x63575  newarr   [mscorlib]System.Object
0x6357a  dup
0x6357b  ldc.i4.0
0x6357c  ldloc.1
0x6357d  ldfld    string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::temporaryInstallerDirectory
0x63582  stelem.ref
0x63583  dup
0x63584  ldc.i4.1
0x63585  ldloc.s  0x10
0x63587  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6358c  stelem.ref
0x6358d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x63592  leave.s  loc_63594
0x63594  ldloc.1
0x63595  ldarg.0
0x63596  ldfld    string <UpdateAsync>d__16::<finalInstallerDirectory>5__3
0x6359b  ldarg.0
0x6359c  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <UpdateAsync>d__16::cancellationToken
0x635a1  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::TryExecuteFinalizerAsync(string finalInstallerDirectory, [opt] valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x635a6  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x635ab  stloc.s  8
0x635ad  ldloca.s 8
0x635af  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x635b4  brtrue.s loc_635F4
0x635b6  ldarg.0
0x635b7  ldc.i4.1
0x635b8  dup
0x635b9  stloc.0
0x635ba  stfld    int32 <UpdateAsync>d__16::<>1__state
0x635bf  ldarg.0
0x635c0  ldloc.s  8
  ... truncated ...
```
