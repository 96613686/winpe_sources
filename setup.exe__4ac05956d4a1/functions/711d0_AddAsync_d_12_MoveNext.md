# <AddAsync>d__12::MoveNext

- ea: `0x711d0`
- end: `0x7149a`
- name: `<AddAsync>d__12::MoveNext`
- size: `714`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x711d0`

## string_xrefs

- `0x712d8`: `UnableToDownloadChannelManifest_Args1`
- `0x71415`: `UnableToDownloadChannelManifest_Args1`
- `0x7137a`: `The channel manifest is already in the cache.`

## pseudocode

```c

```

## disassembly

```asm
0x711d0  ldarg.0
0x711d1  ldfld    int32 <AddAsync>d__12::<>1__state
0x711d6  stloc.0
0x711d7  ldarg.0
0x711d8  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.RemoteChannelManager <AddAsync>d__12::<>4__this
0x711dd  stloc.1
0x711de  ldloc.0
0x711df  brfalse.s loc_71242
0x711e1  ldloc.1
0x711e2  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelValidator Microsoft.VisualStudio.Setup.Installer.Services.RemoteChannelManager::channelValidator
0x711e7  ldarg.0
0x711e8  ldfld    class [System]System.Uri <AddAsync>d__12::channelUri
0x711ed  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelValidator::ValidateChannelUri(class [System]System.Uri)
0x711f2  ldarg.0
0x711f3  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <AddAsync>d__12::cancellationToken
0x711f8  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x711fd  ldloc.1
0x711fe  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelManagerBase::Initialize()
0x71203  ldloc.1
0x71204  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelDownloader [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelManagerBase::GetChannelDownloader()
0x71209  stloc.3
0x7120a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x7120f  dup
0x71210  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::ENGINEOPERATIONTYPE
0x71215  ldstr    aRemotechannela// "RemoteChannelAddAsync"
0x7121a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x7121f  stloc.s  4
0x71221  ldarg.0
0x71222  ldloc.1
0x71223  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.Services.RemoteChannelManager::telemetry
0x71228  dup
0x71229  brtrue.s loc_7122F
0x7122b  pop
0x7122c  ldnull
0x7122d  br.s     loc_7123D
0x7122f  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::ADDREMOTECHANNELOPERATIONEVENT
0x71234  ldloc.s  4
0x71236  ldc.i4.0
0x71237  ldc.i4.0
0x71238  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x7123d  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <AddAsync>d__12::<addAsyncOperation>5__2
0x71242  nop
0x71243  ldloc.0
0x71244  pop
0x71245  nop
0x71246  ldloc.0
0x71247  brfalse.s loc_712A0
0x71249  ldloc.3
0x7124a  ldarg.0
0x7124b  ldfld    class [System]System.Uri <AddAsync>d__12::channelUri
0x71250  ldloc.1
0x71251  call     instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelManagerBase::get_TemporaryCacheDirectory()
0x71256  ldarg.0
0x71257  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <AddAsync>d__12::cancellationToken
0x7125c  ldnull
0x7125d  ldloca.s 9
0x7125f  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>
0x71265  ldloc.s  9
0x71267  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelDownloader/ManifestDownloadSummary> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelDownloader::GetLatestChannelManifestAsync(class [System]System.Uri, string, valuetype [mscorlib]System.Threading.CancellationToken, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>)
0x7126c  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelDownloader/ManifestDownloadSummary>::GetAwaiter()
0x71271  stloc.s  8
0x71273  ldloca.s 8
0x71275  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelDownloader/ManifestDownloadSummary>::get_IsCompleted()
0x7127a  brtrue.s loc_712BD
0x7127c  ldarg.0
0x7127d  ldc.i4.0
0x7127e  dup
0x7127f  stloc.0
0x71280  stfld    int32 <AddAsync>d__12::<>1__state
0x71285  ldarg.0
0x71286  ldloc.s  8
0x71288  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelDownloader/ManifestDownloadSummary> <AddAsync>d__12::<>u__1
0x7128d  ldarg.0
0x7128e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair> <AddAsync>d__12::<>t__builder
0x71293  ldloca.s 8
0x71295  ldarg.0
0x71296  call     T0x2B000487
0x7129b  leave    loc_71499
0x712a0  ldarg.0
0x712a1  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelDownloader/ManifestDownloadSummary> <AddAsync>d__12::<>u__1
0x712a6  stloc.s  8
0x712a8  ldarg.0
0x712a9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelDownloader/ManifestDownloadSummary> <AddAsync>d__12::<>u__1
0x712ae  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelDownloader/ManifestDownloadSummary>
0x712b4  ldarg.0
0x712b5  ldc.i4.m1
0x712b6  dup
0x712b7  stloc.0
0x712b8  stfld    int32 <AddAsync>d__12::<>1__state
0x712bd  ldloca.s 8
0x712bf  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelDownloader/ManifestDownloadSummary>::GetResult()
0x712c4  stloc.s  6
0x712c6  ldloca.s 6
0x712c8  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelDownloader/ManifestDownloadSummary::get_Manifest()
0x712cd  stloc.s  5
0x712cf  ldloc.s  5
0x712d1  brtrue.s loc_712F2
0x712d3  call     class [mscorlib]System.Resources.ResourceManager [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ResourceManager()
0x712d8  ldstr    aUnabletodownlo// "UnableToDownloadChannelManifest_Args1"
0x712dd  ldc.i4.1
0x712de  newarr   [mscorlib]System.Object
0x712e3  dup
0x712e4  ldc.i4.0
0x712e5  ldarg.0
0x712e6  ldfld    class [System]System.Uri <AddAsync>d__12::channelUri
0x712eb  stelem.ref
0x712ec  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelManifestDownloadException::.ctor(class [mscorlib]System.Resources.ResourceManager, string, object[])
0x712f1  throw
0x712f2  ldarg.0
0x712f3  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <AddAsync>d__12::<addAsyncOperation>5__2
0x712f8  dup
0x712f9  brtrue.s loc_712FE
0x712fb  pop
0x712fc  br.s     loc_71313
0x712fe  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x71303  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::CHANNELDOWNLOADEDPROPERTY
0x71308  ldc.i4.1
0x71309  box      [mscorlib]System.Boolean
0x7130e  call     void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Utility.DictionaryUtility::ModifyDictionaryItem(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, string, object)
0x71313  ldarg.0
0x71314  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <AddAsync>d__12::<addAsyncOperation>5__2
0x71319  dup
0x7131a  brtrue.s loc_7131F
0x7131c  pop
0x7131d  br.s     loc_71335
0x7131f  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x71324  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::NEWCHANNELMANIFESTVERSION
0x71329  ldloc.s  5
0x7132b  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x71330  call     void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Utility.DictionaryUtility::ModifyDictionaryItem(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, string, object)
0x71335  ldloc.s  5
0x71337  ldarg.0
0x71338  ldfld    class [System]System.Uri <AddAsync>d__12::channelUri
0x7133d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::set_UpdateUri(class [System]System.Uri)
0x71342  ldloc.s  5
0x71344  ldc.i4.1
0x71345  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::set_CanUpdate(bool)
0x7134a  ldloc.s  5
0x7134c  ldnull
0x7134d  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest)
0x71352  stloc.s  7
0x71354  ldloc.1
0x71355  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IChannelRepository Microsoft.VisualStudio.Setup.Installer.Services.RemoteChannelManager::channelRepository
0x7135a  ldloc.s  7
0x7135c  ldc.i4.0
0x7135d  ldloca.s 9
0x7135f  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>
0x71365  ldloc.s  9
0x71367  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IChannelRepository::AddChannel(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair, bool, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>)
0x7136c  brtrue.s loc_71389
0x7136e  ldloc.1
0x7136f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.Services.RemoteChannelManager::logger
0x71374  dup
0x71375  brtrue.s loc_7137A
0x71377  pop
0x71378  br.s     loc_71389
0x7137a  ldstr    aTheChannelMani// "The channel manifest is already in the "...
0x7137f  call     T0x2B000010
0x71384  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x71389  ldloc.s  7
0x7138b  stloc.2
0x7138c  leave    loc_71485
0x71391  stloc.s  0xA
0x71393  ldloc.1
0x71394  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.Services.RemoteChannelManager::logger
0x71399  dup
0x7139a  brtrue.s loc_7139F
0x7139c  pop
0x7139d  br.s     loc_713B2
0x7139f  ldloc.s  0xA
0x713a1  ldloc.s  0xA
0x713a3  callvirt instance string [mscorlib]System.Exception::get_Message()
0x713a8  call     T0x2B000010
0x713ad  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x713b2  ldloc.s  0xA
0x713b4  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x713b9  ldc.i4   0x80070070
0x713be  beq.s    loc_713E5
0x713c0  ldloc.s  0xA
0x713c2  isinst   [mscorlib]System.IO.IOException
0x713c7  brfalse.s loc_7140E
0x713c9  ldloc.s  0xA
0x713cb  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x713d0  brfalse.s loc_7140E
0x713d2  ldloc.s  0xA
0x713d4  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x713d9  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x713de  ldc.i4   0x80070070
0x713e3  bne.un.s loc_7140E
0x713e5  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.OutOfDiskspaceException::.ctor()
0x713ea  stloc.s  0xB
0x713ec  ldarg.0
0x713ed  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <AddAsync>d__12::<addAsyncOperation>5__2
0x713f2  dup
0x713f3  brtrue.s loc_713F8
0x713f5  pop
0x713f6  br.s     loc_71450
0x713f8  ldloc.s  0xA
0x713fa  callvirt instance string [mscorlib]System.Exception::get_Message()
0x713ff  ldloc.s  0xB
0x71401  ldstr    aChannelManager// "Channel Manager Exception"
0x71406  ldc.i4.1
0x71407  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x7140c  br.s     loc_71450
0x7140e  ldloc.s  0xA
0x71410  call     class [mscorlib]System.Resources.ResourceManager [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ResourceManager()
0x71415  ldstr    aUnabletodownlo// "UnableToDownloadChannelManifest_Args1"
0x7141a  ldc.i4.1
0x7141b  newarr   [mscorlib]System.Object
0x71420  dup
0x71421  ldc.i4.0
0x71422  ldarg.0
0x71423  ldfld    class [System]System.Uri <AddAsync>d__12::channelUri
0x71428  stelem.ref
0x71429  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelManifestDownloadException::.ctor(class [mscorlib]System.Exception, class [mscorlib]System.Resources.ResourceManager, string, object[])
0x7142e  stloc.s  0xC
0x71430  ldarg.0
0x71431  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <AddAsync>d__12::<addAsyncOperation>5__2
0x71436  dup
0x71437  brtrue.s loc_7143C
0x71439  pop
0x7143a  br.s     loc_71450
0x7143c  ldloc.s  0xA
0x7143e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x71443  ldloc.s  0xC
0x71445  ldstr    aChannelManager// "Channel Manager Exception"
0x7144a  ldc.i4.1
0x7144b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x71450  ldnull
0x71451  stloc.2
0x71452  leave.s  loc_71485
0x71454  ldloc.0
0x71455  ldc.i4.0
0x71456  bge.s    loc_7146B
0x71458  ldarg.0
0x71459  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <AddAsync>d__12::<addAsyncOperation>5__2
0x7145e  brfalse.s loc_7146B
0x71460  ldarg.0
0x71461  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <AddAsync>d__12::<addAsyncOperation>5__2
0x71466  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7146b  endfinally
0x7146c  stloc.s  0xD
0x7146e  ldarg.0
0x7146f  ldc.i4.s 0xFE
0x71471  stfld    int32 <AddAsync>d__12::<>1__state
0x71476  ldarg.0
0x71477  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair> <AddAsync>d__12::<>t__builder
0x7147c  ldloc.s  0xD
0x7147e  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair>::SetException(class [mscorlib]System.Exception)
0x71483  leave.s  loc_71499
0x71485  ldarg.0
0x71486  ldc.i4.s 0xFE
0x71488  stfld    int32 <AddAsync>d__12::<>1__state
0x7148d  ldarg.0
0x7148e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair> <AddAsync>d__12::<>t__builder
0x71493  ldloc.2
0x71494  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair>::SetResult(var<u1>)
0x71499  ret
```
