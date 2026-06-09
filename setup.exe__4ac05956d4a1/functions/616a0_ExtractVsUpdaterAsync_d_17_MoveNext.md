# <ExtractVsUpdaterAsync>d__17::MoveNext

- ea: `0x616a0`
- end: `0x61a94`
- name: `<ExtractVsUpdaterAsync>d__17::MoveNext`
- size: `1012`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callees

- `0x7140`
- `0x7380`
- `0x76a0`
- `0x76e0`
- `0x7720`
- `0x616a0`

## string_xrefs

- `0x616e4`: `{0} does not exist. Failed to extract VSUpdater.`
- `0x616fd`: `VSUpdater zip file not found.`
- `0x61788`: `VSUpdater zip at {0} is not validly signed.`
- `0x617a6`: `VSUpdaterInvalidSignatureFailureMessage_Args1`
- `0x61898`: `The installation path: `
- `0x6189f`: ` is outside of allowed directory: `
- `0x618d3`: `The installation path is outside the target directory`

## pseudocode

```c

```

## disassembly

```asm
0x616a0  ldarg.0
0x616a1  ldfld    int32 <ExtractVsUpdaterAsync>d__17::<>1__state
0x616a6  stloc.0
0x616a7  ldarg.0
0x616a8  ldfld    class Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper <ExtractVsUpdaterAsync>d__17::<>4__this
0x616ad  stloc.1
0x616ae  ldloc.0
0x616af  brfalse  loc_61752
0x616b4  ldloc.0
0x616b5  ldc.i4.1
0x616b6  beq      loc_61820
0x616bb  ldloc.1
0x616bc  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x616c1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_FileSystem()
0x616c6  ldarg.0
0x616c7  ldfld    string <ExtractVsUpdaterAsync>d__17::zipFilePath
0x616cc  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x616d1  brtrue.s loc_6170E
0x616d3  ldloc.1
0x616d4  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x616d9  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x616de  dup
0x616df  brtrue.s loc_616E4
0x616e1  pop
0x616e2  br.s     loc_616FD
0x616e4  ldstr    a0DoesNotExistF// "{0} does not exist. Failed to extract V"...
0x616e9  ldc.i4.1
0x616ea  newarr   [mscorlib]System.Object
0x616ef  dup
0x616f0  ldc.i4.0
0x616f1  ldarg.0
0x616f2  ldfld    string <ExtractVsUpdaterAsync>d__17::zipFilePath
0x616f7  stelem.ref
0x616f8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x616fd  ldstr    aVsupdaterZipFi// "VSUpdater zip file not found."
0x61702  ldarg.0
0x61703  ldfld    string <ExtractVsUpdaterAsync>d__17::zipFilePath
0x61708  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor(string, string)
0x6170d  throw
0x6170e  ldloc.1
0x6170f  ldarg.0
0x61710  ldfld    string <ExtractVsUpdaterAsync>d__17::zipFilePath
0x61715  ldarg.0
0x61716  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ExtractVsUpdaterAsync>d__17::token
0x6171b  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::IsVSUpdaterInZipMicrosoftSignedAsync(string zipFilePath, valuetype [mscorlib]System.Threading.CancellationToken token)
0x61720  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x61725  stloc.2
0x61726  ldloca.s 2
0x61728  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x6172d  brtrue.s loc_6176E
0x6172f  ldarg.0
0x61730  ldc.i4.0
0x61731  dup
0x61732  stloc.0
0x61733  stfld    int32 <ExtractVsUpdaterAsync>d__17::<>1__state
0x61738  ldarg.0
0x61739  ldloc.2
0x6173a  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <ExtractVsUpdaterAsync>d__17::<>u__1
0x6173f  ldarg.0
0x61740  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ExtractVsUpdaterAsync>d__17::<>t__builder
0x61745  ldloca.s 2
0x61747  ldarg.0
0x61748  call     T0x2B0003FE
0x6174d  leave    loc_61A93
0x61752  ldarg.0
0x61753  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <ExtractVsUpdaterAsync>d__17::<>u__1
0x61758  stloc.2
0x61759  ldarg.0
0x6175a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <ExtractVsUpdaterAsync>d__17::<>u__1
0x6175f  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x61765  ldarg.0
0x61766  ldc.i4.m1
0x61767  dup
0x61768  stloc.0
0x61769  stfld    int32 <ExtractVsUpdaterAsync>d__17::<>1__state
0x6176e  ldloca.s 2
0x61770  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x61775  brtrue.s loc_617C0
0x61777  ldloc.1
0x61778  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x6177d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x61782  dup
0x61783  brtrue.s loc_61788
0x61785  pop
0x61786  br.s     loc_617A1
0x61788  ldstr    aVsupdaterZipAt// "VSUpdater zip at {0} is not validly sig"...
0x6178d  ldc.i4.1
0x6178e  newarr   [mscorlib]System.Object
0x61793  dup
0x61794  ldc.i4.0
0x61795  ldarg.0
0x61796  ldfld    string <ExtractVsUpdaterAsync>d__17::zipFilePath
0x6179b  stelem.ref
0x6179c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x617a1  call     class [mscorlib]System.Resources.ResourceManager [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ResourceManager()
0x617a6  ldstr    aVsupdaterinval// "VSUpdaterInvalidSignatureFailureMessage"...
0x617ab  ldc.i4.1
0x617ac  newarr   [mscorlib]System.Object
0x617b1  dup
0x617b2  ldc.i4.0
0x617b3  ldarg.0
0x617b4  ldfld    string <ExtractVsUpdaterAsync>d__17::zipFilePath
0x617b9  stelem.ref
0x617ba  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Security.SignatureVerificationFailedException::.ctor(class [mscorlib]System.Resources.ResourceManager, string, object[])
0x617bf  throw
0x617c0  ldarg.0
0x617c1  ldloc.1
0x617c2  call     instance string Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::GetInstallationDirectory()
0x617c7  stfld    string <ExtractVsUpdaterAsync>d__17::<destinationDirectory>5__2
0x617cc  ldloc.1
0x617cd  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x617d2  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_FileSystem()
0x617d7  ldarg.0
0x617d8  ldfld    string <ExtractVsUpdaterAsync>d__17::<destinationDirectory>5__2
0x617dd  ldloca.s 3
0x617df  ldc.i4.0
0x617e0  ldc.i4.1
0x617e1  ldc.i4.2
0x617e2  ldc.i4   0x1F4
0x617e7  ldnull
0x617e8  call     bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extensions::DeleteDirectoryWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem, string, bool&, bool, bool, int32, int32, class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool>)
0x617ed  pop
0x617ee  ldloc.1
0x617ef  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x617f4  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_FileSystem()
0x617f9  ldarg.0
0x617fa  ldfld    string <ExtractVsUpdaterAsync>d__17::<destinationDirectory>5__2
0x617ff  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateDirectory(string)
0x61804  ldarg.0
0x61805  ldloc.1
0x61806  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x6180b  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedArchiveReader Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_CompressedArchiveReader()
0x61810  ldarg.0
0x61811  ldfld    string <ExtractVsUpdaterAsync>d__17::zipFilePath
0x61816  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedArchive [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedArchiveReader::Open(string)
0x6181b  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedArchive <ExtractVsUpdaterAsync>d__17::<archive>5__3
0x61820  nop
0x61821  ldloc.0
0x61822  ldc.i4.1
0x61823  beq.s    loc_6183B
0x61825  ldarg.0
0x61826  ldarg.0
0x61827  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedArchive <ExtractVsUpdaterAsync>d__17::<archive>5__3
0x6182c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedArchiveEntry> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedArchive::GetEntries()
0x61831  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedArchiveEntry>::GetEnumerator()
0x61836  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedArchiveEntry> <ExtractVsUpdaterAsync>d__17::<>7__wrap3
0x6183b  nop
0x6183c  ldloc.0
0x6183d  ldc.i4.1
0x6183e  beq      loc_61920
0x61843  br       loc_61A05
0x61848  ldarg.0
0x61849  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedArchiveEntry> <ExtractVsUpdaterAsync>d__17::<>7__wrap3
0x6184e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedArchiveEntry>::get_Current()
0x61853  stloc.s  4
0x61855  ldarg.0
0x61856  ldfld    string <ExtractVsUpdaterAsync>d__17::<destinationDirectory>5__2
0x6185b  ldloc.s  4
0x6185d  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedArchiveEntry::get_Path()
0x61862  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x61867  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x6186c  stloc.s  5
0x6186e  ldarg.0
0x6186f  ldfld    string <ExtractVsUpdaterAsync>d__17::<destinationDirectory>5__2
0x61874  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x61879  stloc.s  6
0x6187b  ldloc.s  5
0x6187d  ldloc.s  6
0x6187f  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::ContainsPath(string, string)
0x61884  brtrue.s loc_618DE
0x61886  ldloc.1
0x61887  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x6188c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x61891  dup
0x61892  brtrue.s loc_61897
0x61894  pop
0x61895  br.s     loc_618B5
0x61897  ldnull
0x61898  ldstr    aTheInstallatio// "The installation path: "
0x6189d  ldloc.s  5
0x6189f  ldstr    aIsOutsideOfAll// " is outside of allowed directory: "
0x618a4  ldloc.s  6
0x618a6  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x618ab  call     T0x2B000010
0x618b0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x618b5  ldloc.1
0x618b6  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x618bb  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_FileSystem()
0x618c0  ldloc.s  6
0x618c2  ldloca.s 3
0x618c4  ldc.i4.0
0x618c5  ldc.i4.1
0x618c6  ldc.i4.2
0x618c7  ldc.i4   0x1F4
0x618cc  ldnull
0x618cd  call     bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extensions::DeleteDirectoryWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem, string, bool&, bool, bool, int32, int32, class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool>)
0x618d2  pop
0x618d3  ldstr    aTheInstallatio_0// "The installation path is outside the ta"...
0x618d8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x618dd  throw
0x618de  ldloc.s  5
0x618e0  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x618e5  stloc.s  7
0x618e7  ldloc.s  7
0x618e9  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x618ee  brtrue.s loc_61902
0x618f0  ldloc.1
0x618f1  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x618f6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_FileSystem()
0x618fb  ldloc.s  7
0x618fd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateDirectory(string)
0x61902  ldloc.s  4
0x61904  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedArchiveEntry::get_Name()
0x61909  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x6190e  brtrue   loc_61A05
0x61913  ldarg.0
0x61914  ldloc.s  4
0x61916  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedArchiveEntry::GetStream()
0x6191b  stfld    class [mscorlib]System.IO.Stream <ExtractVsUpdaterAsync>d__17::<entryStream>5__5
0x61920  nop
0x61921  ldloc.0
0x61922  ldc.i4.1
0x61923  beq.s    loc_61940
0x61925  ldarg.0
0x61926  ldloc.1
0x61927  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x6192c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_FileSystem()
0x61931  ldloc.s  5
0x61933  ldc.i4.2
0x61934  ldc.i4.3
0x61935  ldc.i4.0
0x61936  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateFile(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileMode, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAccess, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileShare)
0x6193b  stfld    class [mscorlib]System.IO.Stream <ExtractVsUpdaterAsync>d__17::<fileStream>5__6
0x61940  nop
0x61941  ldloc.0
0x61942  ldc.i4.1
0x61943  beq.s    loc_6199F
0x61945  ldarg.0
0x61946  ldfld    class [mscorlib]System.IO.Stream <ExtractVsUpdaterAsync>d__17::<entryStream>5__5
0x6194b  ldarg.0
0x6194c  ldfld    class [mscorlib]System.IO.Stream <ExtractVsUpdaterAsync>d__17::<fileStream>5__6
0x61951  ldc.i4   0x14000
0x61956  ldarg.0
0x61957  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ExtractVsUpdaterAsync>d__17::token
0x6195c  callvirt instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.IO.Stream::CopyToAsync(class [mscorlib]System.IO.Stream, int32, valuetype [mscorlib]System.Threading.CancellationToken)
0x61961  ldc.i4.0
0x61962  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x61967  stloc.s  9
0x61969  ldloca.s 9
0x6196b  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x61970  stloc.s  8
0x61972  ldloca.s 8
0x61974  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x61979  brtrue.s loc_619BC
0x6197b  ldarg.0
0x6197c  ldc.i4.1
0x6197d  dup
0x6197e  stloc.0
0x6197f  stfld    int32 <ExtractVsUpdaterAsync>d__17::<>1__state
0x61984  ldarg.0
0x61985  ldloc.s  8
0x61987  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ExtractVsUpdaterAsync>d__17::<>u__2
0x6198c  ldarg.0
0x6198d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ExtractVsUpdaterAsync>d__17::<>t__builder
0x61992  ldloca.s 8
0x61994  ldarg.0
0x61995  call     T0x2B0003FF
0x6199a  leave    loc_61A93
0x6199f  ldarg.0
0x619a0  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ExtractVsUpdaterAsync>d__17::<>u__2
0x619a5  stloc.s  8
0x619a7  ldarg.0
0x619a8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ExtractVsUpdaterAsync>d__17::<>u__2
0x619ad  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x619b3  ldarg.0
0x619b4  ldc.i4.m1
0x619b5  dup
0x619b6  stloc.0
0x619b7  stfld    int32 <ExtractVsUpdaterAsync>d__17::<>1__state
0x619bc  ldloca.s 8
0x619be  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x619c3  leave.s  loc_619DD
0x619c5  ldloc.0
0x619c6  ldc.i4.0
0x619c7  bge.s    loc_619DC
0x619c9  ldarg.0
0x619ca  ldfld    class [mscorlib]System.IO.Stream <ExtractVsUpdaterAsync>d__17::<fileStream>5__6
0x619cf  brfalse.s loc_619DC
0x619d1  ldarg.0
0x619d2  ldfld    class [mscorlib]System.IO.Stream <ExtractVsUpdaterAsync>d__17::<fileStream>5__6
0x619d7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x619dc  endfinally
0x619dd  ldarg.0
0x619de  ldnull
0x619df  stfld    class [mscorlib]System.IO.Stream <ExtractVsUpdaterAsync>d__17::<fileStream>5__6
0x619e4  leave.s  loc_619FE
0x619e6  ldloc.0
0x619e7  ldc.i4.0
0x619e8  bge.s    loc_619FD
0x619ea  ldarg.0
  ... truncated ...
```
