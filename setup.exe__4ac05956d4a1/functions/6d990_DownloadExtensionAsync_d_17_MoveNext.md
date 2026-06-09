# <DownloadExtensionAsync>d__17::MoveNext

- ea: `0x6d990`
- end: `0x6dbf4`
- name: `<DownloadExtensionAsync>d__17::MoveNext`
- size: `612`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x9310`
- `0x20a60`
- `0x2bcc0`
- `0x2c060`
- `0x2c070`
- `0x2c080`
- `0x3dcb0`
- `0x6c7a0`
- `0x6d990`

## string_xrefs

- `0x6daf9`: `Successfully downloaded and parsed the extension`
- `0x6db76`: `Failed to download and parse the extension`

## pseudocode

```c

```

## disassembly

```asm
0x6d990  ldarg.0
0x6d991  ldfld    int32 <DownloadExtensionAsync>d__17::<>1__state
0x6d996  stloc.0
0x6d997  ldarg.0
0x6d998  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager <DownloadExtensionAsync>d__17::<>4__this
0x6d99d  stloc.1
0x6d99e  ldloc.0
0x6d99f  brfalse.s loc_6D9C6
0x6d9a1  ldarg.0
0x6d9a2  ldloc.1
0x6d9a3  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x6d9a8  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Telemetry()
0x6d9ad  dup
0x6d9ae  brtrue.s loc_6D9B4
0x6d9b0  pop
0x6d9b1  ldnull
0x6d9b2  br.s     loc_6D9C1
0x6d9b4  ldsfld   string Extensions::DownloadExtensionEvent
0x6d9b9  ldnull
0x6d9ba  ldc.i4.0
0x6d9bb  ldc.i4.0
0x6d9bc  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x6d9c1  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <DownloadExtensionAsync>d__17::<downloadOperation>5__2
0x6d9c6  nop
0x6d9c7  ldloc.0
0x6d9c8  brfalse.s loc_6D9D5
0x6d9ca  ldarg.0
0x6d9cb  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x6d9d0  stfld    class [mscorlib]System.IO.MemoryStream <DownloadExtensionAsync>d__17::<downloadStream>5__3
0x6d9d5  nop
0x6d9d6  ldloc.0
0x6d9d7  brfalse.s loc_6DA39
0x6d9d9  ldloc.1
0x6d9da  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x6d9df  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.IExtensionServiceInternal Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions::get_ExtensionService()
0x6d9e4  ldarg.0
0x6d9e5  ldfld    class [System]System.Uri <DownloadExtensionAsync>d__17::extensionUri
0x6d9ea  ldarg.0
0x6d9eb  ldfld    class [mscorlib]System.IO.MemoryStream <DownloadExtensionAsync>d__17::<downloadStream>5__3
0x6d9f0  ldarg.0
0x6d9f1  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <DownloadExtensionAsync>d__17::token
0x6d9f6  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionDownloadSummary> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.IExtensionServiceInternal::DownloadAsync(class [System]System.Uri, class [mscorlib]System.IO.Stream, valuetype [mscorlib]System.Threading.CancellationToken)
0x6d9fb  ldc.i4.0
0x6d9fc  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionDownloadSummary>::ConfigureAwait(!!T0)
0x6da01  stloc.s  5
0x6da03  ldloca.s 5
0x6da05  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionDownloadSummary>::GetAwaiter()
0x6da0a  stloc.s  4
0x6da0c  ldloca.s 4
0x6da0e  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionDownloadSummary>::get_IsCompleted()
0x6da13  brtrue.s loc_6DA56
0x6da15  ldarg.0
0x6da16  ldc.i4.0
0x6da17  dup
0x6da18  stloc.0
0x6da19  stfld    int32 <DownloadExtensionAsync>d__17::<>1__state
0x6da1e  ldarg.0
0x6da1f  ldloc.s  4
0x6da21  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionDownloadSummary> <DownloadExtensionAsync>d__17::<>u__1
0x6da26  ldarg.0
0x6da27  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class ExtensionContentsSummary> <DownloadExtensionAsync>d__17::<>t__builder
0x6da2c  ldloca.s 4
0x6da2e  ldarg.0
0x6da2f  call     T0x2B000465
0x6da34  leave    loc_6DBF3
0x6da39  ldarg.0
0x6da3a  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionDownloadSummary> <DownloadExtensionAsync>d__17::<>u__1
0x6da3f  stloc.s  4
0x6da41  ldarg.0
0x6da42  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionDownloadSummary> <DownloadExtensionAsync>d__17::<>u__1
0x6da47  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionDownloadSummary>
0x6da4d  ldarg.0
0x6da4e  ldc.i4.m1
0x6da4f  dup
0x6da50  stloc.0
0x6da51  stfld    int32 <DownloadExtensionAsync>d__17::<>1__state
0x6da56  ldloca.s 4
0x6da58  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionDownloadSummary>::GetResult()
0x6da5d  stloc.3
0x6da5e  ldarg.0
0x6da5f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <DownloadExtensionAsync>d__17::<downloadOperation>5__2
0x6da64  dup
0x6da65  brtrue.s loc_6DA6A
0x6da67  pop
0x6da68  br.s     loc_6DA7F
0x6da6a  ldsfld   string Extensions::DownloadSucceededProperty
0x6da6f  ldloc.3
0x6da70  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionDownloadSummary::get_IsSuccess()
0x6da75  box      [mscorlib]System.Boolean
0x6da7a  call     void Microsoft.VisualStudio.Setup.Installer.CommonExtensions::SetProperty(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, string key, object value)
0x6da7f  ldloc.3
0x6da80  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionDownloadSummary::get_IsSuccess()
0x6da85  brfalse  loc_6DB6A
0x6da8a  ldloc.1
0x6da8b  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x6da90  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.IExtensionServiceInternal Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions::get_ExtensionService()
0x6da95  ldarg.0
0x6da96  ldfld    class [mscorlib]System.IO.MemoryStream <DownloadExtensionAsync>d__17::<downloadStream>5__3
0x6da9b  ldarg.0
0x6da9c  ldfld    class [mscorlib]System.Version <DownloadExtensionAsync>d__17::productVersion
0x6daa1  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.IExtensionService::ParseExtension(class [mscorlib]System.IO.Stream, class [mscorlib]System.Version)
0x6daa6  stloc.s  6
0x6daa8  ldarg.0
0x6daa9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <DownloadExtensionAsync>d__17::<downloadOperation>5__2
0x6daae  dup
0x6daaf  brtrue.s loc_6DAB4
0x6dab1  pop
0x6dab2  br.s     loc_6DAC8
0x6dab4  ldsfld   string Extensions::ParseSucceededProperty
0x6dab9  ldloc.s  6
0x6dabb  ldnull
0x6dabc  cgt.un
0x6dabe  box      [mscorlib]System.Boolean
0x6dac3  call     void Microsoft.VisualStudio.Setup.Installer.CommonExtensions::SetProperty(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, string key, object value)
0x6dac8  ldloc.s  6
0x6daca  brfalse  loc_6DB6A
0x6dacf  ldloc.1
0x6dad0  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x6dad5  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.IExtensionCache Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions::get_ExtensionCache()
0x6dada  ldarg.0
0x6dadb  ldfld    class [System]System.Uri <DownloadExtensionAsync>d__17::extensionUri
0x6dae0  ldloc.s  6
0x6dae2  ldarg.0
0x6dae3  ldfld    class [mscorlib]System.IO.MemoryStream <DownloadExtensionAsync>d__17::<downloadStream>5__3
0x6dae8  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.IExtensionCache::CacheExtension(class [System]System.Uri, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents, class [mscorlib]System.IO.Stream)
0x6daed  ldarg.0
0x6daee  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <DownloadExtensionAsync>d__17::<downloadOperation>5__2
0x6daf3  dup
0x6daf4  brtrue.s loc_6DAF9
0x6daf6  pop
0x6daf7  br.s     loc_6DB03
0x6daf9  ldstr    aSuccessfullyDo// "Successfully downloaded and parsed the "...
0x6dafe  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x6db03  ldloc.1
0x6db04  ldloc.s  6
0x6db06  ldarg.0
0x6db07  ldfld    class [mscorlib]System.IO.MemoryStream <DownloadExtensionAsync>d__17::<downloadStream>5__3
0x6db0c  ldloc.3
0x6db0d  ldarg.0
0x6db0e  ldfld    class [mscorlib]System.Version <DownloadExtensionAsync>d__17::productVersion
0x6db13  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class ExtensionContentsSummary> Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::DownloadEmbeddedExtensions(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents parentExtensionContents, class [mscorlib]System.IO.Stream parentExtensionStream, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionDownloadSummary parentDownloadSummary, class [mscorlib]System.Version productVersion)
0x6db18  stloc.s  7
0x6db1a  ldarg.0
0x6db1b  ldfld    class [mscorlib]System.IO.MemoryStream <DownloadExtensionAsync>d__17::<downloadStream>5__3
0x6db20  ldc.i4.0
0x6db21  conv.i8
0x6db22  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x6db27  ldloc.1
0x6db28  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x6db2d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IHashingService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions::get_HashingService()
0x6db32  ldarg.0
0x6db33  ldfld    class [mscorlib]System.IO.MemoryStream <DownloadExtensionAsync>d__17::<downloadStream>5__3
0x6db38  ldc.i4.1
0x6db39  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IHashingService::GetHashOfStream(class [mscorlib]System.IO.Stream, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.HashAlgorithms)
0x6db3e  stloc.s  8
0x6db40  ldloc.s  6
0x6db42  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents::get_CatalogJson()
0x6db47  call     class [System]System.Collections.Generic.ISet`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity> Microsoft.VisualStudio.Setup.Installer.Utilities.Utilities::GetComponentsFromExtensionCatalog(string catalogJson)
0x6db4c  stloc.s  9
0x6db4e  ldloc.s  6
0x6db50  ldloc.s  7
0x6db52  ldloc.3
0x6db53  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionDownloadSummary::get_VerificationResult()
0x6db58  ldloc.s  8
0x6db5a  ldloc.3
0x6db5b  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionDownloadSummary::get_Certificate()
0x6db60  ldloc.s  9
0x6db62  newobj   instance void ExtensionContentsSummary::.ctor(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents ExtensionContents, class [mscorlib]System.Collections.Generic.IDictionary`2<class [System]System.Uri, class ExtensionContentsSummary> EmbeddedExtensions, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult VerificationResult, string Sha256Hash, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Certificate, class [System]System.Collections.Generic.ISet`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity> ParsedComponents)
0x6db67  stloc.2
0x6db68  leave.s  loc_6DBDF
0x6db6a  ldarg.0
0x6db6b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <DownloadExtensionAsync>d__17::<downloadOperation>5__2
0x6db70  dup
0x6db71  brtrue.s loc_6DB76
0x6db73  pop
0x6db74  br.s     loc_6DB80
0x6db76  ldstr    aFailedToDownlo_3// "Failed to download and parse the extens"...
0x6db7b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x6db80  leave.s  loc_6DB9A
0x6db82  ldloc.0
0x6db83  ldc.i4.0
0x6db84  bge.s    loc_6DB99
0x6db86  ldarg.0
0x6db87  ldfld    class [mscorlib]System.IO.MemoryStream <DownloadExtensionAsync>d__17::<downloadStream>5__3
0x6db8c  brfalse.s loc_6DB99
0x6db8e  ldarg.0
0x6db8f  ldfld    class [mscorlib]System.IO.MemoryStream <DownloadExtensionAsync>d__17::<downloadStream>5__3
0x6db94  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6db99  endfinally
0x6db9a  ldarg.0
0x6db9b  ldnull
0x6db9c  stfld    class [mscorlib]System.IO.MemoryStream <DownloadExtensionAsync>d__17::<downloadStream>5__3
0x6dba1  leave.s  loc_6DBBB
0x6dba3  ldloc.0
0x6dba4  ldc.i4.0
0x6dba5  bge.s    loc_6DBBA
0x6dba7  ldarg.0
0x6dba8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <DownloadExtensionAsync>d__17::<downloadOperation>5__2
0x6dbad  brfalse.s loc_6DBBA
0x6dbaf  ldarg.0
0x6dbb0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <DownloadExtensionAsync>d__17::<downloadOperation>5__2
0x6dbb5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6dbba  endfinally
0x6dbbb  ldarg.0
0x6dbbc  ldnull
0x6dbbd  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <DownloadExtensionAsync>d__17::<downloadOperation>5__2
0x6dbc2  ldnull
0x6dbc3  stloc.2
0x6dbc4  leave.s  loc_6DBDF
0x6dbc6  stloc.s  0xA
0x6dbc8  ldarg.0
0x6dbc9  ldc.i4.s 0xFE
0x6dbcb  stfld    int32 <DownloadExtensionAsync>d__17::<>1__state
0x6dbd0  ldarg.0
0x6dbd1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class ExtensionContentsSummary> <DownloadExtensionAsync>d__17::<>t__builder
0x6dbd6  ldloc.s  0xA
0x6dbd8  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class ExtensionContentsSummary>::SetException(class [mscorlib]System.Exception)
0x6dbdd  leave.s  loc_6DBF3
0x6dbdf  ldarg.0
0x6dbe0  ldc.i4.s 0xFE
0x6dbe2  stfld    int32 <DownloadExtensionAsync>d__17::<>1__state
0x6dbe7  ldarg.0
0x6dbe8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class ExtensionContentsSummary> <DownloadExtensionAsync>d__17::<>t__builder
0x6dbed  ldloc.2
0x6dbee  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class ExtensionContentsSummary>::SetResult(var<u1>)
0x6dbf3  ret
```
