# <FinalizeInstallerAsync>d__6::MoveNext

- ea: `0x8fdd0`
- end: `0x8ff35`
- name: `<FinalizeInstallerAsync>d__6::MoveNext`
- size: `357`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0xa8f0`
- `0x8fdd0`

## string_xrefs

- `0x8fe7a`: `Finalized installer.`
- `0x8feb1`: `Failed to finalize the installer with error. {0}`
- `0x8fed7`: `Failed to finalize the installer`
- `0x8fede`: `Failed to finalize the installer`
- `0x8fe90`: `Successfully finalized the installer`

## pseudocode

```c

```

## disassembly

```asm
0x8fdd0  ldarg.0
0x8fdd1  ldfld    int32 <FinalizeInstallerAsync>d__6::<>1__state
0x8fdd6  stloc.0
0x8fdd7  ldarg.0
0x8fdd8  ldfld    class Microsoft.VisualStudio.Setup.Installer.Application.FinalizeInstallerApplication <FinalizeInstallerAsync>d__6::<>4__this
0x8fddd  stloc.1
0x8fdde  ldloc.0
0x8fddf  brfalse.s loc_8FE01
0x8fde1  ldarg.0
0x8fde2  ldloc.1
0x8fde3  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.Application.FinalizeInstallerApplication::telemetry
0x8fde8  dup
0x8fde9  brtrue.s loc_8FDEF
0x8fdeb  pop
0x8fdec  ldnull
0x8fded  br.s     loc_8FDFC
0x8fdef  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::FinalizeInstallEvent
0x8fdf4  ldnull
0x8fdf5  ldc.i4.0
0x8fdf6  ldc.i4.0
0x8fdf7  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x8fdfc  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <FinalizeInstallerAsync>d__6::<operation>5__2
0x8fe01  nop
0x8fe02  ldloc.0
0x8fe03  pop
0x8fe04  nop
0x8fe05  ldloc.0
0x8fe06  brfalse.s loc_8FE4B
0x8fe08  ldloc.1
0x8fe09  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerFinalizerService Microsoft.VisualStudio.Setup.Installer.Application.FinalizeInstallerApplication::installerFinalizer
0x8fe0e  ldloc.1
0x8fe0f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.Application.FinalizeInstallerApplication::fileSystem
0x8fe14  call     class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.Extensions::FinalizeInstallerAsync(class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerFinalizerService finalizer, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem)
0x8fe19  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x8fe1e  stloc.3
0x8fe1f  ldloca.s 3
0x8fe21  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x8fe26  brtrue.s loc_8FE67
0x8fe28  ldarg.0
0x8fe29  ldc.i4.0
0x8fe2a  dup
0x8fe2b  stloc.0
0x8fe2c  stfld    int32 <FinalizeInstallerAsync>d__6::<>1__state
0x8fe31  ldarg.0
0x8fe32  ldloc.3
0x8fe33  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <FinalizeInstallerAsync>d__6::<>u__1
0x8fe38  ldarg.0
0x8fe39  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <FinalizeInstallerAsync>d__6::<>t__builder
0x8fe3e  ldloca.s 3
0x8fe40  ldarg.0
0x8fe41  call     T0x2B000604
0x8fe46  leave    loc_8FF34
0x8fe4b  ldarg.0
0x8fe4c  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <FinalizeInstallerAsync>d__6::<>u__1
0x8fe51  stloc.3
0x8fe52  ldarg.0
0x8fe53  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <FinalizeInstallerAsync>d__6::<>u__1
0x8fe58  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x8fe5e  ldarg.0
0x8fe5f  ldc.i4.m1
0x8fe60  dup
0x8fe61  stloc.0
0x8fe62  stfld    int32 <FinalizeInstallerAsync>d__6::<>1__state
0x8fe67  ldloca.s 3
0x8fe69  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x8fe6e  ldarg.0
0x8fe6f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <FinalizeInstallerAsync>d__6::<operation>5__2
0x8fe74  dup
0x8fe75  brtrue.s loc_8FE7A
0x8fe77  pop
0x8fe78  br.s     loc_8FE84
0x8fe7a  ldstr    aFinalizedInsta// "Finalized installer."
0x8fe7f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x8fe84  ldloc.1
0x8fe85  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.Application.FinalizeInstallerApplication::logger
0x8fe8a  dup
0x8fe8b  brtrue.s loc_8FE90
0x8fe8d  pop
0x8fe8e  br.s     loc_8FE9F
0x8fe90  ldstr    aSuccessfullyFi// "Successfully finalized the installer"
0x8fe95  call     T0x2B000010
0x8fe9a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x8fe9f  ldc.i4.1
0x8fea0  stloc.2
0x8fea1  leave.s  loc_8FF20
0x8fea3  stloc.s  4
0x8fea5  ldloc.1
0x8fea6  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.Application.FinalizeInstallerApplication::logger
0x8feab  dup
0x8feac  brtrue.s loc_8FEB1
0x8feae  pop
0x8feaf  br.s     loc_8FECB
0x8feb1  ldstr    aFailedToFinali_0// "Failed to finalize the installer with e"...
0x8feb6  ldc.i4.1
0x8feb7  newarr   [mscorlib]System.Object
0x8febc  dup
0x8febd  ldc.i4.0
0x8febe  ldloc.s  4
0x8fec0  callvirt instance string [mscorlib]System.Object::ToString()
0x8fec5  stelem.ref
0x8fec6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x8fecb  ldarg.0
0x8fecc  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <FinalizeInstallerAsync>d__6::<operation>5__2
0x8fed1  dup
0x8fed2  brtrue.s loc_8FED7
0x8fed4  pop
0x8fed5  br.s     loc_8FEE9
0x8fed7  ldstr    aFailedToFinali_1// "Failed to finalize the installer"
0x8fedc  ldloc.s  4
0x8fede  ldstr    aFailedToFinali_1// "Failed to finalize the installer"
0x8fee3  ldc.i4.0
0x8fee4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x8fee9  leave.s  loc_8FEEB
0x8feeb  ldc.i4.0
0x8feec  stloc.2
0x8feed  leave.s  loc_8FF20
0x8feef  ldloc.0
0x8fef0  ldc.i4.0
0x8fef1  bge.s    loc_8FF06
0x8fef3  ldarg.0
0x8fef4  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <FinalizeInstallerAsync>d__6::<operation>5__2
0x8fef9  brfalse.s loc_8FF06
0x8fefb  ldarg.0
0x8fefc  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <FinalizeInstallerAsync>d__6::<operation>5__2
0x8ff01  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ff06  endfinally
0x8ff07  stloc.s  5
0x8ff09  ldarg.0
0x8ff0a  ldc.i4.s 0xFE
0x8ff0c  stfld    int32 <FinalizeInstallerAsync>d__6::<>1__state
0x8ff11  ldarg.0
0x8ff12  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <FinalizeInstallerAsync>d__6::<>t__builder
0x8ff17  ldloc.s  5
0x8ff19  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetException(class [mscorlib]System.Exception)
0x8ff1e  leave.s  loc_8FF34
0x8ff20  ldarg.0
0x8ff21  ldc.i4.s 0xFE
0x8ff23  stfld    int32 <FinalizeInstallerAsync>d__6::<>1__state
0x8ff28  ldarg.0
0x8ff29  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <FinalizeInstallerAsync>d__6::<>t__builder
0x8ff2e  ldloc.2
0x8ff2f  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetResult(var<u1>)
0x8ff34  ret
```
