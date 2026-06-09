# <DownloadVsUpdaterAsync>d__11::MoveNext

- ea: `0x61450`
- end: `0x61675`
- name: `<DownloadVsUpdaterAsync>d__11::MoveNext`
- size: `549`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x76a0`
- `0x76b0`
- `0x76e0`
- `0x61450`

## string_xrefs

- `0x614ad`: `Downloading VSUpdater to: {0}`
- `0x61508`: `Failed to create file stream for VSUpdater download.`
- `0x61517`: `Failed to create file stream for VSUpdater download.`
- `0x615bc`: `Failed to download VSUpdater from: {0}`
- `0x615d5`: `Failed to download VSUpdater.`
- `0x615f1`: `VSUpdater downloaded successfully to: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x61450  ldarg.0
0x61451  ldfld    int32 <DownloadVsUpdaterAsync>d__11::<>1__state
0x61456  stloc.0
0x61457  ldarg.0
0x61458  ldfld    class Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper <DownloadVsUpdaterAsync>d__11::<>4__this
0x6145d  stloc.1
0x6145e  ldloc.0
0x6145f  brfalse  loc_614E8
0x61464  ldloc.1
0x61465  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x6146a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_FileSystem()
0x6146f  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::GetTempFileName()
0x61474  stloc.3
0x61475  ldarg.0
0x61476  ldloc.3
0x61477  ldstr    aZip// ".zip"
0x6147c  call     string [mscorlib]System.IO.Path::ChangeExtension(string, string)
0x61481  stfld    string <DownloadVsUpdaterAsync>d__11::<tempPath>5__2
0x61486  ldloc.1
0x61487  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x6148c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_FileSystem()
0x61491  ldloc.3
0x61492  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x61497  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateDirectory(string)
0x6149c  ldloc.1
0x6149d  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x614a2  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x614a7  dup
0x614a8  brtrue.s loc_614AD
0x614aa  pop
0x614ab  br.s     loc_614C6
0x614ad  ldstr    aDownloadingVsu// "Downloading VSUpdater to: {0}"
0x614b2  ldc.i4.1
0x614b3  newarr   [mscorlib]System.Object
0x614b8  dup
0x614b9  ldc.i4.0
0x614ba  ldarg.0
0x614bb  ldfld    string <DownloadVsUpdaterAsync>d__11::<tempPath>5__2
0x614c0  stelem.ref
0x614c1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x614c6  ldarg.0
0x614c7  ldloc.1
0x614c8  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x614cd  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_FileSystem()
0x614d2  ldarg.0
0x614d3  ldfld    string <DownloadVsUpdaterAsync>d__11::<tempPath>5__2
0x614d8  ldc.i4.2
0x614d9  ldc.i4   0x1F4
0x614de  call     class [mscorlib]System.IO.Stream [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extensions::CreateFileWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem, string, int32, int32)
0x614e3  stfld    class [mscorlib]System.IO.Stream <DownloadVsUpdaterAsync>d__11::<fileStream>5__3
0x614e8  nop
0x614e9  ldloc.0
0x614ea  brfalse  loc_61585
0x614ef  ldarg.0
0x614f0  ldfld    class [mscorlib]System.IO.Stream <DownloadVsUpdaterAsync>d__11::<fileStream>5__3
0x614f5  brtrue.s loc_61522
0x614f7  ldloc.1
0x614f8  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x614fd  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x61502  dup
0x61503  brtrue.s loc_61508
0x61505  pop
0x61506  br.s     loc_61517
0x61508  ldstr    aFailedToCreate_4// "Failed to create file stream for VSUpda"...
0x6150d  call     T0x2B000010
0x61512  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x61517  ldstr    aFailedToCreate_4// "Failed to create file stream for VSUpda"...
0x6151c  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x61521  throw
0x61522  ldloc.1
0x61523  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x61528  callvirt instance class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IDownloadManager Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_DownloadManager()
0x6152d  ldarg.0
0x6152e  ldfld    class [System]System.Uri <DownloadVsUpdaterAsync>d__11::downloadUri
0x61533  ldarg.0
0x61534  ldfld    class [mscorlib]System.IO.Stream <DownloadVsUpdaterAsync>d__11::<fileStream>5__3
0x61539  ldnull
0x6153a  ldarg.0
0x6153b  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <DownloadVsUpdaterAsync>d__11::cancellationToken
0x61540  ldnull
0x61541  ldc.i4.0
0x61542  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadSummary> [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IDownloadManager::Download(class [System]System.Uri, class [mscorlib]System.IO.Stream, class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.ProgressUpdateCallback, valuetype [mscorlib]System.Threading.CancellationToken, class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadContext, bool)
0x61547  ldc.i4.0
0x61548  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadSummary>::ConfigureAwait(!!T0)
0x6154d  stloc.s  5
0x6154f  ldloca.s 5
0x61551  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadSummary>::GetAwaiter()
0x61556  stloc.s  4
0x61558  ldloca.s 4
0x6155a  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadSummary>::get_IsCompleted()
0x6155f  brtrue.s loc_615A2
0x61561  ldarg.0
0x61562  ldc.i4.0
0x61563  dup
0x61564  stloc.0
0x61565  stfld    int32 <DownloadVsUpdaterAsync>d__11::<>1__state
0x6156a  ldarg.0
0x6156b  ldloc.s  4
0x6156d  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadSummary> <DownloadVsUpdaterAsync>d__11::<>u__1
0x61572  ldarg.0
0x61573  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <DownloadVsUpdaterAsync>d__11::<>t__builder
0x61578  ldloca.s 4
0x6157a  ldarg.0
0x6157b  call     T0x2B0003FD
0x61580  leave    loc_61674
0x61585  ldarg.0
0x61586  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadSummary> <DownloadVsUpdaterAsync>d__11::<>u__1
0x6158b  stloc.s  4
0x6158d  ldarg.0
0x6158e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadSummary> <DownloadVsUpdaterAsync>d__11::<>u__1
0x61593  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadSummary>
0x61599  ldarg.0
0x6159a  ldc.i4.m1
0x6159b  dup
0x6159c  stloc.0
0x6159d  stfld    int32 <DownloadVsUpdaterAsync>d__11::<>1__state
0x615a2  ldloca.s 4
0x615a4  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadSummary>::GetResult()
0x615a9  brtrue.s loc_615E0
0x615ab  ldloc.1
0x615ac  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x615b1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x615b6  dup
0x615b7  brtrue.s loc_615BC
0x615b9  pop
0x615ba  br.s     loc_615D5
0x615bc  ldstr    aFailedToDownlo_0// "Failed to download VSUpdater from: {0}"
0x615c1  ldc.i4.1
0x615c2  newarr   [mscorlib]System.Object
0x615c7  dup
0x615c8  ldc.i4.0
0x615c9  ldarg.0
0x615ca  ldfld    class [System]System.Uri <DownloadVsUpdaterAsync>d__11::downloadUri
0x615cf  stelem.ref
0x615d0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x615d5  ldstr    aFailedToDownlo_1// "Failed to download VSUpdater."
0x615da  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x615df  throw
0x615e0  ldloc.1
0x615e1  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x615e6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x615eb  dup
0x615ec  brtrue.s loc_615F1
0x615ee  pop
0x615ef  br.s     loc_6160A
0x615f1  ldstr    aVsupdaterDownl// "VSUpdater downloaded successfully to: {"...
0x615f6  ldc.i4.1
0x615f7  newarr   [mscorlib]System.Object
0x615fc  dup
0x615fd  ldc.i4.0
0x615fe  ldarg.0
0x615ff  ldfld    string <DownloadVsUpdaterAsync>d__11::<tempPath>5__2
0x61604  stelem.ref
0x61605  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x6160a  ldarg.0
0x6160b  ldfld    string <DownloadVsUpdaterAsync>d__11::<tempPath>5__2
0x61610  stloc.2
0x61611  leave.s  loc_61652
0x61613  ldloc.0
0x61614  ldc.i4.0
0x61615  bge.s    loc_6162A
0x61617  ldarg.0
0x61618  ldfld    class [mscorlib]System.IO.Stream <DownloadVsUpdaterAsync>d__11::<fileStream>5__3
0x6161d  brfalse.s loc_6162A
0x6161f  ldarg.0
0x61620  ldfld    class [mscorlib]System.IO.Stream <DownloadVsUpdaterAsync>d__11::<fileStream>5__3
0x61625  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6162a  endfinally
0x6162b  stloc.s  6
0x6162d  ldarg.0
0x6162e  ldc.i4.s 0xFE
0x61630  stfld    int32 <DownloadVsUpdaterAsync>d__11::<>1__state
0x61635  ldarg.0
0x61636  ldnull
0x61637  stfld    string <DownloadVsUpdaterAsync>d__11::<tempPath>5__2
0x6163c  ldarg.0
0x6163d  ldnull
0x6163e  stfld    class [mscorlib]System.IO.Stream <DownloadVsUpdaterAsync>d__11::<fileStream>5__3
0x61643  ldarg.0
0x61644  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <DownloadVsUpdaterAsync>d__11::<>t__builder
0x61649  ldloc.s  6
0x6164b  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetException(class [mscorlib]System.Exception)
0x61650  leave.s  loc_61674
0x61652  ldarg.0
0x61653  ldc.i4.s 0xFE
0x61655  stfld    int32 <DownloadVsUpdaterAsync>d__11::<>1__state
0x6165a  ldarg.0
0x6165b  ldnull
0x6165c  stfld    string <DownloadVsUpdaterAsync>d__11::<tempPath>5__2
0x61661  ldarg.0
0x61662  ldnull
0x61663  stfld    class [mscorlib]System.IO.Stream <DownloadVsUpdaterAsync>d__11::<fileStream>5__3
0x61668  ldarg.0
0x61669  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <DownloadVsUpdaterAsync>d__11::<>t__builder
0x6166e  ldloc.2
0x6166f  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetResult(var<u1>)
0x61674  ret
```
