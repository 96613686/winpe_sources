# <TryFinalizeInstallerAsync>d__25::MoveNext

- ea: `0x6ba30`
- end: `0x6bbe6`
- name: `<TryFinalizeInstallerAsync>d__25::MoveNext`
- size: `438`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update`

## callees

- `0xa8f0`
- `0x2d6b0`
- `0x2d6c0`
- `0x59bd0`
- `0x6ba30`

## string_xrefs

- `0x6baa8`: `Failed to finalize the installer due to a missing service`
- `0x6bb3d`: `Finalized installer.`
- `0x6bb5c`: `Failed to finalize the installer with error. {0}`
- `0x6bb82`: `Failed to finalize the installer`
- `0x6bb89`: `Failed to finalize the installer`

## pseudocode

```c

```

## disassembly

```asm
0x6ba30  ldarg.0
0x6ba31  ldfld    int32 <TryFinalizeInstallerAsync>d__25::<>1__state
0x6ba36  stloc.0
0x6ba37  ldarg.0
0x6ba38  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.AppInitializerService <TryFinalizeInstallerAsync>d__25::<>4__this
0x6ba3d  stloc.1
0x6ba3e  ldloc.0
0x6ba3f  brfalse.s loc_6BA7D
0x6ba41  ldarg.0
0x6ba42  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions <TryFinalizeInstallerAsync>d__25::options
0x6ba47  dup
0x6ba48  brtrue.s loc_6BA4E
0x6ba4a  pop
0x6ba4b  ldc.i4.0
0x6ba4c  br.s     loc_6BA53
0x6ba4e  call     instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions::get_FinalizeInstall()
0x6ba53  brfalse  loc_6BBB7
0x6ba58  ldarg.0
0x6ba59  ldloc.1
0x6ba5a  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.AppInitializerService::serviceOptions
0x6ba5f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Telemetry()
0x6ba64  dup
0x6ba65  brtrue.s loc_6BA6B
0x6ba67  pop
0x6ba68  ldnull
0x6ba69  br.s     loc_6BA78
0x6ba6b  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::FinalizeInstallEvent
0x6ba70  ldnull
0x6ba71  ldc.i4.0
0x6ba72  ldc.i4.0
0x6ba73  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x6ba78  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <TryFinalizeInstallerAsync>d__25::<operation>5__2
0x6ba7d  nop
0x6ba7e  ldloc.0
0x6ba7f  pop
0x6ba80  nop
0x6ba81  ldloc.0
0x6ba82  brfalse  loc_6BB0D
0x6ba87  ldloc.1
0x6ba88  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.Installer.Services.AppInitializerService::services
0x6ba8d  ldc.i4.0
0x6ba8e  call     T0x2B000457
0x6ba93  stloc.2
0x6ba94  ldloc.2
0x6ba95  brtrue.s loc_6BABC
0x6ba97  ldloc.1
0x6ba98  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.AppInitializerService::serviceOptions
0x6ba9d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x6baa2  dup
0x6baa3  brtrue.s loc_6BAA8
0x6baa5  pop
0x6baa6  br.s     loc_6BAB7
0x6baa8  ldstr    aFailedToFinali// "Failed to finalize the installer due to"...
0x6baad  call     T0x2B000010
0x6bab2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x6bab7  leave    loc_6BBD2
0x6babc  ldloc.1
0x6babd  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.Installer.Services.AppInitializerService::services
0x6bac2  ldc.i4.0
0x6bac3  call     T0x2B0000F6
0x6bac8  dup
0x6bac9  brtrue.s loc_6BAD1
0x6bacb  pop
0x6bacc  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.FileSystem::Default
0x6bad1  stloc.3
0x6bad2  ldloc.2
0x6bad3  ldloc.3
0x6bad4  call     class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.Extensions::FinalizeInstallerAsync(class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerFinalizerService finalizer, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem)
0x6bad9  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x6bade  stloc.s  4
0x6bae0  ldloca.s 4
0x6bae2  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x6bae7  brtrue.s loc_6BB2A
0x6bae9  ldarg.0
0x6baea  ldc.i4.0
0x6baeb  dup
0x6baec  stloc.0
0x6baed  stfld    int32 <TryFinalizeInstallerAsync>d__25::<>1__state
0x6baf2  ldarg.0
0x6baf3  ldloc.s  4
0x6baf5  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <TryFinalizeInstallerAsync>d__25::<>u__1
0x6bafa  ldarg.0
0x6bafb  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <TryFinalizeInstallerAsync>d__25::<>t__builder
0x6bb00  ldloca.s 4
0x6bb02  ldarg.0
0x6bb03  call     T0x2B000458
0x6bb08  leave    loc_6BBE5
0x6bb0d  ldarg.0
0x6bb0e  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <TryFinalizeInstallerAsync>d__25::<>u__1
0x6bb13  stloc.s  4
0x6bb15  ldarg.0
0x6bb16  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <TryFinalizeInstallerAsync>d__25::<>u__1
0x6bb1b  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x6bb21  ldarg.0
0x6bb22  ldc.i4.m1
0x6bb23  dup
0x6bb24  stloc.0
0x6bb25  stfld    int32 <TryFinalizeInstallerAsync>d__25::<>1__state
0x6bb2a  ldloca.s 4
0x6bb2c  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x6bb31  ldarg.0
0x6bb32  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <TryFinalizeInstallerAsync>d__25::<operation>5__2
0x6bb37  dup
0x6bb38  brtrue.s loc_6BB3D
0x6bb3a  pop
0x6bb3b  br.s     loc_6BB47
0x6bb3d  ldstr    aFinalizedInsta// "Finalized installer."
0x6bb42  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x6bb47  leave.s  loc_6BB96
0x6bb49  stloc.s  5
0x6bb4b  ldloc.1
0x6bb4c  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.AppInitializerService::serviceOptions
0x6bb51  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x6bb56  dup
0x6bb57  brtrue.s loc_6BB5C
0x6bb59  pop
0x6bb5a  br.s     loc_6BB76
0x6bb5c  ldstr    aFailedToFinali_0// "Failed to finalize the installer with e"...
0x6bb61  ldc.i4.1
0x6bb62  newarr   [mscorlib]System.Object
0x6bb67  dup
0x6bb68  ldc.i4.0
0x6bb69  ldloc.s  5
0x6bb6b  callvirt instance string [mscorlib]System.Object::ToString()
0x6bb70  stelem.ref
0x6bb71  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x6bb76  ldarg.0
0x6bb77  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <TryFinalizeInstallerAsync>d__25::<operation>5__2
0x6bb7c  dup
0x6bb7d  brtrue.s loc_6BB82
0x6bb7f  pop
0x6bb80  br.s     loc_6BB94
0x6bb82  ldstr    aFailedToFinali_1// "Failed to finalize the installer"
0x6bb87  ldloc.s  5
0x6bb89  ldstr    aFailedToFinali_1// "Failed to finalize the installer"
0x6bb8e  ldc.i4.0
0x6bb8f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x6bb94  leave.s  loc_6BB96
0x6bb96  leave.s  loc_6BBB0
0x6bb98  ldloc.0
0x6bb99  ldc.i4.0
0x6bb9a  bge.s    loc_6BBAF
0x6bb9c  ldarg.0
0x6bb9d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <TryFinalizeInstallerAsync>d__25::<operation>5__2
0x6bba2  brfalse.s loc_6BBAF
0x6bba4  ldarg.0
0x6bba5  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <TryFinalizeInstallerAsync>d__25::<operation>5__2
0x6bbaa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6bbaf  endfinally
0x6bbb0  ldarg.0
0x6bbb1  ldnull
0x6bbb2  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <TryFinalizeInstallerAsync>d__25::<operation>5__2
0x6bbb7  leave.s  loc_6BBD2
0x6bbb9  stloc.s  6
0x6bbbb  ldarg.0
0x6bbbc  ldc.i4.s 0xFE
0x6bbbe  stfld    int32 <TryFinalizeInstallerAsync>d__25::<>1__state
0x6bbc3  ldarg.0
0x6bbc4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <TryFinalizeInstallerAsync>d__25::<>t__builder
0x6bbc9  ldloc.s  6
0x6bbcb  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x6bbd0  leave.s  loc_6BBE5
0x6bbd2  ldarg.0
0x6bbd3  ldc.i4.s 0xFE
0x6bbd5  stfld    int32 <TryFinalizeInstallerAsync>d__25::<>1__state
0x6bbda  ldarg.0
0x6bbdb  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <TryFinalizeInstallerAsync>d__25::<>t__builder
0x6bbe0  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x6bbe5  ret
```
