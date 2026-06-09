# <TryExecuteFinalizerAsync>d__25::MoveNext

- ea: `0x63050`
- end: `0x6323a`
- name: `<TryExecuteFinalizerAsync>d__25::MoveNext`
- size: `490`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x7560`
- `0x7630`
- `0x7790`
- `0x7da0`
- `0x87e0`
- `0x63050`

## string_xrefs

- `0x63075`: `Attempting to finalize the installer.`
- `0x630c7`: `No version file could be found for the installer under {0}`
- `0x631cf`: `Finalizer failed to complete with error: {0}`
- `0x631fc`: `Finalizer completed successfully.`

## pseudocode

```c

```

## disassembly

```asm
0x63050  ldarg.0
0x63051  ldfld    int32 <TryExecuteFinalizerAsync>d__25::<>1__state
0x63056  stloc.0
0x63057  ldarg.0
0x63058  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager <TryExecuteFinalizerAsync>d__25::<>4__this
0x6305d  stloc.1
0x6305e  ldloc.0
0x6305f  brfalse  loc_6310D
0x63064  ldloc.1
0x63065  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x6306a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x6306f  dup
0x63070  brtrue.s loc_63075
0x63072  pop
0x63073  br.s     loc_63084
0x63075  ldstr    aAttemptingToFi// "Attempting to finalize the installer."
0x6307a  call     T0x2B000010
0x6307f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x63084  ldloc.1
0x63085  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x6308a  callvirt instance class Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerFinalizerService Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_InstallerFinalizerService()
0x6308f  stloc.2
0x63090  ldarg.0
0x63091  ldfld    string <TryExecuteFinalizerAsync>d__25::finalInstallerDirectory
0x63096  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.BootstrapperConstants::InstallerFileName
0x6309b  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x630a0  stloc.3
0x630a1  ldarg.0
0x630a2  ldfld    string <TryExecuteFinalizerAsync>d__25::finalInstallerDirectory
0x630a7  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceExeName
0x630ac  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x630b1  stloc.s  4
0x630b3  ldloc.1
0x630b4  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::get_Services()
0x630b9  ldarg.0
0x630ba  ldfld    string <TryExecuteFinalizerAsync>d__25::finalInstallerDirectory
0x630bf  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Client::GetInstallerVersion(class [mscorlib]System.IServiceProvider, string)
0x630c4  dup
0x630c5  brtrue.s loc_630FE
0x630c7  ldstr    aNoVersionFileC// "No version file could be found for the "...
0x630cc  ldarg.0
0x630cd  ldfld    string <TryExecuteFinalizerAsync>d__25::finalInstallerDirectory
0x630d2  call     string [mscorlib]System.String::Format(string, object)
0x630d7  stloc.s  6
0x630d9  ldloc.1
0x630da  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x630df  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x630e4  dup
0x630e5  brtrue.s loc_630EA
0x630e7  pop
0x630e8  br.s     loc_630F6
0x630ea  ldloc.s  6
0x630ec  call     T0x2B000010
0x630f1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x630f6  ldloc.s  6
0x630f8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x630fd  throw
0x630fe  callvirt instance string [mscorlib]System.Object::ToString()
0x63103  ldloc.3
0x63104  ldloc.s  4
0x63106  newobj   instance void Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::.ctor(string applicationVersion, string targetPath, string elevationServicePath)
0x6310b  stloc.s  5
0x6310d  nop
0x6310e  ldloc.0
0x6310f  brfalse.s loc_63174
0x63111  ldc.i4.2
0x63112  newarr   [mscorlib]System.Threading.Tasks.Task
0x63117  dup
0x63118  ldc.i4.0
0x63119  ldloc.2
0x6311a  ldloc.s  5
0x6311c  ldarg.0
0x6311d  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <TryExecuteFinalizerAsync>d__25::cancellationToken
0x63122  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Bootstrapper.IInstallerFinalizerService::InstallAsync(class Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions options, [opt] valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x63127  stelem.ref
0x63128  dup
0x63129  ldc.i4.1
0x6312a  ldc.i4   0x1388
0x6312f  ldarg.0
0x63130  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <TryExecuteFinalizerAsync>d__25::cancellationToken
0x63135  call     class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.Task::Delay(int32, valuetype [mscorlib]System.Threading.CancellationToken)
0x6313a  stelem.ref
0x6313b  call     class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Threading.Tasks.Task> [mscorlib]System.Threading.Tasks.Task::WhenAny(class [mscorlib]System.Threading.Tasks.Task[])
0x63140  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Threading.Tasks.Task>::GetAwaiter()
0x63145  stloc.s  7
0x63147  ldloca.s 7
0x63149  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Threading.Tasks.Task>::get_IsCompleted()
0x6314e  brtrue.s loc_63191
0x63150  ldarg.0
0x63151  ldc.i4.0
0x63152  dup
0x63153  stloc.0
0x63154  stfld    int32 <TryExecuteFinalizerAsync>d__25::<>1__state
0x63159  ldarg.0
0x6315a  ldloc.s  7
0x6315c  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Threading.Tasks.Task> <TryExecuteFinalizerAsync>d__25::<>u__1
0x63161  ldarg.0
0x63162  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <TryExecuteFinalizerAsync>d__25::<>t__builder
0x63167  ldloca.s 7
0x63169  ldarg.0
0x6316a  call     T0x2B000409
0x6316f  leave    loc_63239
0x63174  ldarg.0
0x63175  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Threading.Tasks.Task> <TryExecuteFinalizerAsync>d__25::<>u__1
0x6317a  stloc.s  7
0x6317c  ldarg.0
0x6317d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Threading.Tasks.Task> <TryExecuteFinalizerAsync>d__25::<>u__1
0x63182  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Threading.Tasks.Task>
0x63188  ldarg.0
0x63189  ldc.i4.m1
0x6318a  dup
0x6318b  stloc.0
0x6318c  stfld    int32 <TryExecuteFinalizerAsync>d__25::<>1__state
0x63191  ldloca.s 7
0x63193  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Threading.Tasks.Task>::GetResult()
0x63198  pop
0x63199  leave.s  loc_631EB
0x6319b  isinst   [mscorlib]System.Exception
0x631a0  dup
0x631a1  brtrue.s loc_631A7
0x631a3  pop
0x631a4  ldc.i4.0
0x631a5  br.s     loc_631B9
0x631a7  stloc.s  8
0x631a9  ldloc.s  8
0x631ab  isinst   [mscorlib]System.OperationCanceledException
0x631b0  ldnull
0x631b1  cgt.un
0x631b3  ldc.i4.0
0x631b4  ceq
0x631b6  ldc.i4.0
0x631b7  cgt.un
0x631b9  endfilter
0x631bb  pop
0x631bc  ldloc.1
0x631bd  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x631c2  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x631c7  dup
0x631c8  brtrue.s loc_631CD
0x631ca  pop
0x631cb  br.s     loc_631E9
0x631cd  ldloc.s  8
0x631cf  ldstr    aFinalizerFaile_0// "Finalizer failed to complete with error"...
0x631d4  ldc.i4.1
0x631d5  newarr   [mscorlib]System.Object
0x631da  dup
0x631db  ldc.i4.0
0x631dc  ldloc.s  8
0x631de  callvirt instance string [mscorlib]System.Exception::get_Message()
0x631e3  stelem.ref
0x631e4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x631e9  leave.s  loc_63226
0x631eb  ldloc.1
0x631ec  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x631f1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x631f6  dup
0x631f7  brtrue.s loc_631FC
0x631f9  pop
0x631fa  br.s     loc_6320B
0x631fc  ldstr    aFinalizerCompl_0// "Finalizer completed successfully."
0x63201  call     T0x2B000010
0x63206  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x6320b  leave.s  loc_63226
0x6320d  stloc.s  9
0x6320f  ldarg.0
0x63210  ldc.i4.s 0xFE
0x63212  stfld    int32 <TryExecuteFinalizerAsync>d__25::<>1__state
0x63217  ldarg.0
0x63218  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <TryExecuteFinalizerAsync>d__25::<>t__builder
0x6321d  ldloc.s  9
0x6321f  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x63224  leave.s  loc_63239
0x63226  ldarg.0
0x63227  ldc.i4.s 0xFE
0x63229  stfld    int32 <TryExecuteFinalizerAsync>d__25::<>1__state
0x6322e  ldarg.0
0x6322f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <TryExecuteFinalizerAsync>d__25::<>t__builder
0x63234  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x63239  ret
```
