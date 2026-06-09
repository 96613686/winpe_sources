# <ExtractAsync>d__13::MoveNext

- ea: `0x62790`
- end: `0x62d4a`
- name: `<ExtractAsync>d__13::MoveNext`
- size: `1466`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update`

## callees

- `0x7570`
- `0x7600`
- `0x7630`
- `0x8620`
- `0x8640`
- `0x8670`
- `0x86b0`
- `0x87a0`
- `0x87e0`
- `0x624b0`
- `0x62790`

## string_xrefs

- `0x628db`: `Downloading updated bootstrapper.`
- `0x6299e`: `Finished downloading updated bootstrapper.`
- `0x62a45`: `Finished deleting previous installers.`
- `0x62ab5`: `OfflineInstallerPath`
- `0x62b45`: `Finished extracting installer to {0}.`
- `0x62caf`: `Failed to hide directory: {0}, error: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x62790  ldarg.0
0x62791  ldfld    int32 <ExtractAsync>d__13::<>1__state
0x62796  stloc.0
0x62797  ldarg.0
0x62798  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager <ExtractAsync>d__13::<>4__this
0x6279d  stloc.1
0x6279e  ldloc.0
0x6279f  switch   loc_6292B, loc_62A10, loc_62A9E, loc_62A9E, loc_62C21
0x627b8  ldarg.0
0x627b9  newobj   instance void <>c__DisplayClass13_0::.ctor()
0x627be  stfld    class <>c__DisplayClass13_0 <ExtractAsync>d__13::<>8__1
0x627c3  ldarg.0
0x627c4  ldfld    class <>c__DisplayClass13_0 <ExtractAsync>d__13::<>8__1
0x627c9  ldarg.0
0x627ca  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager <ExtractAsync>d__13::<>4__this
0x627cf  stfld    class Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager <>c__DisplayClass13_0::<>4__this
0x627d4  ldarg.0
0x627d5  ldfld    class <>c__DisplayClass13_0 <ExtractAsync>d__13::<>8__1
0x627da  ldloc.1
0x627db  ldflda   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) int32 Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::operationId
0x627e0  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x627e5  stfld    int32 <>c__DisplayClass13_0::operationId
0x627ea  ldloc.1
0x627eb  ldarg.0
0x627ec  ldfld    class <>c__DisplayClass13_0 <ExtractAsync>d__13::<>8__1
0x627f1  ldfld    int32 <>c__DisplayClass13_0::operationId
0x627f6  ldc.r8   1.0
0x627ff  ldc.r8   0.0
0x62808  call     instance void Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::OnProgress(int32 operationId, float64 progress, float64 weight)
0x6280d  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloaderSettings::.ctor()
0x62812  dup
0x62813  ldc.i4.1
0x62814  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloaderSettings::set_CanThrowExceptions(bool)
0x62819  dup
0x6281a  ldc.i4.1
0x6281b  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloaderSettings::set_DownloadOverMeteredConnections(bool)
0x62820  dup
0x62821  ldc.i4.1
0x62822  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloaderSettings::set_UseGlobalDirectory(bool)
0x62827  dup
0x62828  ldarg.0
0x62829  ldfld    string <ExtractAsync>d__13::bootstrapperUri
0x6282e  newobj   instance void [System]System.Uri::.ctor(string)
0x62833  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloaderSettings::set_BootstrapperUri(class [System]System.Uri)
0x62838  dup
0x62839  ldarg.0
0x6283a  ldfld    class [mscorlib]System.Version <ExtractAsync>d__13::clientVersion
0x6283f  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloaderSettings::set_ClientVersion(class [mscorlib]System.Version)
0x62844  dup
0x62845  ldarg.0
0x62846  ldfld    string <ExtractAsync>d__13::opcUrl
0x6284b  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloaderSettings::set_OpcUrl(string)
0x62850  stloc.3
0x62851  ldloc.1
0x62852  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x62857  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x6285c  dup
0x6285d  brtrue.s loc_62862
0x6285f  pop
0x62860  br.s     loc_6287B
0x62862  ldstr    aGettingExtract// "Getting extraction source from bootstra"...
0x62867  ldc.i4.1
0x62868  newarr   [mscorlib]System.Object
0x6286d  dup
0x6286e  ldc.i4.0
0x6286f  ldarg.0
0x62870  ldfld    string <ExtractAsync>d__13::bootstrapperUri
0x62875  stelem.ref
0x62876  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x6287b  ldloc.1
0x6287c  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x62881  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperDownloaderFactory Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_BootstrapperDownloaderFactory()
0x62886  ldloc.1
0x62887  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::get_Services()
0x6288c  ldloc.3
0x6288d  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperDownloader [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperDownloaderFactory::Create(class [mscorlib]System.IServiceProvider, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloaderSettings)
0x62892  stloc.s  4
0x62894  ldloc.s  4
0x62896  ldarg.0
0x62897  ldfld    class <>c__DisplayClass13_0 <ExtractAsync>d__13::<>8__1
0x6289c  ldftn    instance void <>c__DisplayClass13_0::<ExtractAsync>b__0(object source, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs args)
0x628a2  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs>::.ctor(object, native int)
0x628a7  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperDownloader::add_Progress(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.ProgressEventArgs>)
0x628ac  ldarg.0
0x628ad  ldloc.s  4
0x628af  ldarg.0
0x628b0  ldfld    class [mscorlib]System.Version <ExtractAsync>d__13::minimumRequiredVersion
0x628b5  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperDownloader::GetCached(class [mscorlib]System.Version)
0x628ba  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation <ExtractAsync>d__13::<bootstrapperInformation>5__2
0x628bf  ldarg.0
0x628c0  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation <ExtractAsync>d__13::<bootstrapperInformation>5__2
0x628c5  brtrue   loc_6298D
0x628ca  ldloc.1
0x628cb  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x628d0  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x628d5  dup
0x628d6  brtrue.s loc_628DB
0x628d8  pop
0x628d9  br.s     loc_628EA
0x628db  ldstr    aDownloadingUpd// "Downloading updated bootstrapper."
0x628e0  call     T0x2B000010
0x628e5  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x628ea  ldloc.s  4
0x628ec  ldarg.0
0x628ed  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ExtractAsync>d__13::cancellationToken
0x628f2  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperDownloader::DownloadAsync(valuetype [mscorlib]System.Threading.CancellationToken)
0x628f7  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation>::GetAwaiter()
0x628fc  stloc.s  8
0x628fe  ldloca.s 8
0x62900  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation>::get_IsCompleted()
0x62905  brtrue.s loc_62948
0x62907  ldarg.0
0x62908  ldc.i4.0
0x62909  dup
0x6290a  stloc.0
0x6290b  stfld    int32 <ExtractAsync>d__13::<>1__state
0x62910  ldarg.0
0x62911  ldloc.s  8
0x62913  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation> <ExtractAsync>d__13::<>u__1
0x62918  ldarg.0
0x62919  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <ExtractAsync>d__13::<>t__builder
0x6291e  ldloca.s 8
0x62920  ldarg.0
0x62921  call     T0x2B000406
0x62926  leave    loc_62D49
0x6292b  ldarg.0
0x6292c  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation> <ExtractAsync>d__13::<>u__1
0x62931  stloc.s  8
0x62933  ldarg.0
0x62934  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation> <ExtractAsync>d__13::<>u__1
0x62939  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation>
0x6293f  ldarg.0
0x62940  ldc.i4.m1
0x62941  dup
0x62942  stloc.0
0x62943  stfld    int32 <ExtractAsync>d__13::<>1__state
0x62948  ldloca.s 8
0x6294a  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation>::GetResult()
0x6294f  stloc.s  7
0x62951  ldarg.0
0x62952  ldloc.s  7
0x62954  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation <ExtractAsync>d__13::<bootstrapperInformation>5__2
0x62959  ldarg.0
0x6295a  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation <ExtractAsync>d__13::<bootstrapperInformation>5__2
0x6295f  brtrue.s loc_6298D
0x62961  ldstr    aFailedToDownlo_2// "Failed to download the bootstrapper"
0x62966  stloc.s  9
0x62968  ldloc.1
0x62969  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x6296e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x62973  dup
0x62974  brtrue.s loc_62979
0x62976  pop
0x62977  br.s     loc_62985
0x62979  ldloc.s  9
0x6297b  call     T0x2B000010
0x62980  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x62985  ldloc.s  9
0x62987  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6298c  throw
0x6298d  ldloc.1
0x6298e  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x62993  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x62998  dup
0x62999  brtrue.s loc_6299E
0x6299b  pop
0x6299c  br.s     loc_629AD
0x6299e  ldstr    aFinishedDownlo// "Finished downloading updated bootstrapp"...
0x629a3  call     T0x2B000010
0x629a8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x629ad  ldloc.1
0x629ae  ldarg.0
0x629af  ldfld    class <>c__DisplayClass13_0 <ExtractAsync>d__13::<>8__1
0x629b4  ldfld    int32 <>c__DisplayClass13_0::operationId
0x629b9  ldc.r8   1.0
0x629c2  ldc.r8   0.8
0x629cb  call     instance void Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::OnProgress(int32 operationId, float64 progress, float64 weight)
0x629d0  ldloc.1
0x629d1  ldarg.0
0x629d2  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ExtractAsync>d__13::cancellationToken
0x629d7  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::DeletePreviousTemporaryInstallerDirectoriesAsync(valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x629dc  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x629e1  stloc.s  0xA
0x629e3  ldloca.s 0xA
0x629e5  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x629ea  brtrue.s loc_62A2D
0x629ec  ldarg.0
0x629ed  ldc.i4.1
0x629ee  dup
0x629ef  stloc.0
0x629f0  stfld    int32 <ExtractAsync>d__13::<>1__state
0x629f5  ldarg.0
0x629f6  ldloc.s  0xA
0x629f8  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <ExtractAsync>d__13::<>u__2
0x629fd  ldarg.0
0x629fe  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <ExtractAsync>d__13::<>t__builder
0x62a03  ldloca.s 0xA
0x62a05  ldarg.0
0x62a06  call     T0x2B000407
0x62a0b  leave    loc_62D49
0x62a10  ldarg.0
0x62a11  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <ExtractAsync>d__13::<>u__2
0x62a16  stloc.s  0xA
0x62a18  ldarg.0
0x62a19  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <ExtractAsync>d__13::<>u__2
0x62a1e  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x62a24  ldarg.0
0x62a25  ldc.i4.m1
0x62a26  dup
0x62a27  stloc.0
0x62a28  stfld    int32 <ExtractAsync>d__13::<>1__state
0x62a2d  ldloca.s 0xA
0x62a2f  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x62a34  ldloc.1
0x62a35  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x62a3a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x62a3f  dup
0x62a40  brtrue.s loc_62A45
0x62a42  pop
0x62a43  br.s     loc_62A54
0x62a45  ldstr    aFinishedDeleti// "Finished deleting previous installers."
0x62a4a  call     T0x2B000010
0x62a4f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x62a54  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x62a59  stloc.s  0xB
0x62a5b  ldloca.s 0xB
0x62a5d  ldstr    aN// "N"
0x62a62  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x62a67  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x62a6c  stloc.s  5
0x62a6e  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.BootstrapperConstants::InstallerSubDirectory
0x62a73  ldstr    asc_9EBEA// "."
0x62a78  ldloc.s  5
0x62a7a  call     string [mscorlib]System.String::Concat(string, string, string)
0x62a7f  stloc.s  6
0x62a81  ldloc.1
0x62a82  ldloc.1
0x62a83  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x62a88  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_FileSystem()
0x62a8d  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_SharedProgramsDirectory()
0x62a92  ldloc.s  6
0x62a94  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x62a99  stfld    string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::temporaryInstallerDirectory
0x62a9e  nop
0x62a9f  ldloc.0
0x62aa0  ldc.i4.2
0x62aa1  beq.s    loc_62B10
0x62aa3  ldloc.0
0x62aa4  ldc.i4.3
0x62aa5  beq      loc_62BC7
0x62aaa  ldarg.0
0x62aab  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation <ExtractAsync>d__13::<bootstrapperInformation>5__2
0x62ab0  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation::get_OfflineInstallerPath()
0x62ab5  ldstr    aOfflineinstall// "OfflineInstallerPath"
0x62aba  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x62abf  ldloc.1
0x62ac0  ldarg.0
0x62ac1  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation <ExtractAsync>d__13::<bootstrapperInformation>5__2
0x62ac6  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation::get_OfflineInstallerPath()
0x62acb  ldloc.1
0x62acc  ldfld    string Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::temporaryInstallerDirectory
0x62ad1  ldarg.0
0x62ad2  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ExtractAsync>d__13::cancellationToken
0x62ad7  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::ExtractOpcAsync(string offlineInstallerPath, string installerDirectory, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x62adc  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x62ae1  stloc.s  0xA
0x62ae3  ldloca.s 0xA
0x62ae5  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x62aea  brtrue.s loc_62B2D
0x62aec  ldarg.0
0x62aed  ldc.i4.2
0x62aee  dup
0x62aef  stloc.0
0x62af0  stfld    int32 <ExtractAsync>d__13::<>1__state
0x62af5  ldarg.0
0x62af6  ldloc.s  0xA
0x62af8  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <ExtractAsync>d__13::<>u__2
0x62afd  ldarg.0
0x62afe  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <ExtractAsync>d__13::<>t__builder
0x62b03  ldloca.s 0xA
0x62b05  ldarg.0
0x62b06  call     T0x2B000407
0x62b0b  leave    loc_62D49
0x62b10  ldarg.0
0x62b11  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <ExtractAsync>d__13::<>u__2
0x62b16  stloc.s  0xA
0x62b18  ldarg.0
0x62b19  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <ExtractAsync>d__13::<>u__2
0x62b1e  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x62b24  ldarg.0
0x62b25  ldc.i4.m1
0x62b26  dup
0x62b27  stloc.0
0x62b28  stfld    int32 <ExtractAsync>d__13::<>1__state
0x62b2d  ldloca.s 0xA
0x62b2f  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x62b34  ldloc.1
0x62b35  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x62b3a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x62b3f  dup
  ... truncated ...
```
