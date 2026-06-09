# <InitializeChannelsAsync>d__16::MoveNext

- ea: `0x6b620`
- end: `0x6ba06`
- name: `<InitializeChannelsAsync>d__16::MoveNext`
- size: `998`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `service_task`

## callees

- `0x1e520`
- `0x1e5c0`
- `0x1e5e0`
- `0x1e5f0`
- `0x1e700`
- `0x21990`
- `0x2b6c0`
- `0x2b700`
- `0x2b770`
- `0x2d6b0`
- `0x59120`
- `0x59140`
- `0x59520`
- `0x59860`
- `0x5a3a0`
- `0x6b620`

## string_xrefs

- `0x6b9b8`: `AppInitializerService`

## pseudocode

```c

```

## disassembly

```asm
0x6b620  ldarg.0
0x6b621  ldfld    int32 <InitializeChannelsAsync>d__16::<>1__state
0x6b626  stloc.0
0x6b627  ldarg.0
0x6b628  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.AppInitializerService <InitializeChannelsAsync>d__16::<>4__this
0x6b62d  stloc.1
0x6b62e  ldloc.0
0x6b62f  ldc.i4.2
0x6b630  pop
0x6b631  pop
0x6b632  nop
0x6b633  ldloc.0
0x6b634  brfalse.s loc_6B6B1
0x6b636  ldloc.0
0x6b637  ldc.i4.1
0x6b638  sub
0x6b639  ldc.i4.1
0x6b63a  ble.un   loc_6B80C
0x6b63f  ldloc.1
0x6b640  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.AppInitializerService::serviceOptions
0x6b645  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IInstallChannelLifetimeManager Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions::get_InstallChannelLifetimeManager()
0x6b64a  ldc.i4.1
0x6b64b  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.IInstallChannelLifetimeManager::set_CleanupInstallChannelsOnDispose(bool value)
0x6b650  ldarg.0
0x6b651  ldloc.1
0x6b652  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.AppInitializerService::serviceOptions
0x6b657  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions::get_ChannelManager()
0x6b65c  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <InitializeChannelsAsync>d__16::<channelManager>5__2
0x6b661  ldloc.1
0x6b662  ldarg.0
0x6b663  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <InitializeChannelsAsync>d__16::<channelManager>5__2
0x6b668  ldarg.0
0x6b669  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <InitializeChannelsAsync>d__16::token
0x6b66e  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.Services.AppInitializerService::TryInitializeChannelManagerAsync(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager channelManager, valuetype [mscorlib]System.Threading.CancellationToken token)
0x6b673  ldc.i4.0
0x6b674  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x6b679  stloc.s  8
0x6b67b  ldloca.s 8
0x6b67d  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x6b682  stloc.s  7
0x6b684  ldloca.s 7
0x6b686  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x6b68b  brtrue.s loc_6B6CE
0x6b68d  ldarg.0
0x6b68e  ldc.i4.0
0x6b68f  dup
0x6b690  stloc.0
0x6b691  stfld    int32 <InitializeChannelsAsync>d__16::<>1__state
0x6b696  ldarg.0
0x6b697  ldloc.s  7
0x6b699  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <InitializeChannelsAsync>d__16::<>u__1
0x6b69e  ldarg.0
0x6b69f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeChannelsAsync>d__16::<>t__builder
0x6b6a4  ldloca.s 7
0x6b6a6  ldarg.0
0x6b6a7  call     T0x2B000454
0x6b6ac  leave    loc_6BA05
0x6b6b1  ldarg.0
0x6b6b2  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <InitializeChannelsAsync>d__16::<>u__1
0x6b6b7  stloc.s  7
0x6b6b9  ldarg.0
0x6b6ba  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <InitializeChannelsAsync>d__16::<>u__1
0x6b6bf  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x6b6c5  ldarg.0
0x6b6c6  ldc.i4.m1
0x6b6c7  dup
0x6b6c8  stloc.0
0x6b6c9  stfld    int32 <InitializeChannelsAsync>d__16::<>1__state
0x6b6ce  ldloca.s 7
0x6b6d0  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x6b6d5  ldloc.1
0x6b6d6  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.AppInitializerService::serviceOptions
0x6b6db  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.ICommandLineOptionsService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions::get_CommandLineService()
0x6b6e0  callvirt T0x2B00007A
0x6b6e5  stloc.2
0x6b6e6  ldarg.0
0x6b6e7  ldnull
0x6b6e8  stfld    string <InitializeChannelsAsync>d__16::<channelUriStr>5__3
0x6b6ed  ldnull
0x6b6ee  stloc.3
0x6b6ef  ldnull
0x6b6f0  stloc.s  4
0x6b6f2  ldc.i4.0
0x6b6f3  stloc.s  5
0x6b6f5  ldloc.2
0x6b6f6  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IChannelOptions
0x6b6fb  stloc.s  6
0x6b6fd  ldloc.s  6
0x6b6ff  brfalse  loc_6B7BC
0x6b704  ldarg.0
0x6b705  ldloc.s  6
0x6b707  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IChannelOptions::get_ChannelUri()
0x6b70c  stfld    string <InitializeChannelsAsync>d__16::<channelUriStr>5__3
0x6b711  ldloc.s  6
0x6b713  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IChannelOptions::get_InstallChannelUri()
0x6b718  stloc.3
0x6b719  ldloc.s  6
0x6b71b  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions
0x6b720  stloc.s  9
0x6b722  ldloc.s  9
0x6b724  brtrue.s loc_6B735
0x6b726  ldloc.s  6
0x6b728  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions
0x6b72d  stloc.s  0xA
0x6b72f  ldloc.s  0xA
0x6b731  brtrue.s loc_6B753
0x6b733  br.s     loc_6B7A3
0x6b735  ldloc.s  9
0x6b737  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions::get_InstallCatalogUri()
0x6b73c  stloc.s  4
0x6b73e  ldarg.0
0x6b73f  ldfld    string <InitializeChannelsAsync>d__16::<channelUriStr>5__3
0x6b744  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6b749  ldc.i4.0
0x6b74a  ceq
0x6b74c  stloc.s  5
0x6b74e  br       loc_6B805
0x6b753  ldarg.0
0x6b754  ldfld    string <InitializeChannelsAsync>d__16::<channelUriStr>5__3
0x6b759  brtrue.s loc_6B773
0x6b75b  ldarg.0
0x6b75c  ldloc.1
0x6b75d  ldloc.s  0xA
0x6b75f  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance Microsoft.VisualStudio.Setup.Installer.Services.AppInitializerService::GetInstance(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions options)
0x6b764  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_ChannelUri()
0x6b769  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x6b76e  stfld    string <InitializeChannelsAsync>d__16::<channelUriStr>5__3
0x6b773  ldloc.s  0xA
0x6b775  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions::get_InstallCatalogUri()
0x6b77a  stloc.s  4
0x6b77c  ldloc.s  6
0x6b77e  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IChannelOptions::get_ChannelUri()
0x6b783  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6b788  brfalse.s loc_6B79E
0x6b78a  ldloc.3
0x6b78b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6b790  brfalse.s loc_6B79E
0x6b792  ldloc.s  4
0x6b794  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6b799  ldc.i4.0
0x6b79a  ceq
0x6b79c  br.s     loc_6B79F
0x6b79e  ldc.i4.1
0x6b79f  stloc.s  5
0x6b7a1  br.s     loc_6B805
0x6b7a3  ldloc.3
0x6b7a4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6b7a9  brfalse.s loc_6B7B7
0x6b7ab  ldloc.s  4
0x6b7ad  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6b7b2  ldc.i4.0
0x6b7b3  ceq
0x6b7b5  br.s     loc_6B7B8
0x6b7b7  ldc.i4.1
0x6b7b8  stloc.s  5
0x6b7ba  br.s     loc_6B805
0x6b7bc  ldloc.2
0x6b7bd  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions
0x6b7c2  stloc.s  0xB
0x6b7c4  ldloc.s  0xB
0x6b7c6  brfalse.s loc_6B805
0x6b7c8  ldloc.s  0xB
0x6b7ca  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions::get_NewChannelUri()
0x6b7cf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6b7d4  brtrue.s loc_6B805
0x6b7d6  ldloc.1
0x6b7d7  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.AppInitializerService::serviceOptions
0x6b7dc  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions::get_ChannelManager()
0x6b7e1  ldloc.s  0xB
0x6b7e3  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions::get_NewChannelUri()
0x6b7e8  newobj   instance void [System]System.Uri::.ctor(string)
0x6b7ed  ldc.i4.0
0x6b7ee  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager::GetChannel(class [System]System.Uri, bool)
0x6b7f3  ldnull
0x6b7f4  ceq
0x6b7f6  stloc.s  5
0x6b7f8  ldarg.0
0x6b7f9  ldloc.s  0xB
0x6b7fb  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions::get_NewChannelUri()
0x6b800  stfld    string <InitializeChannelsAsync>d__16::<channelUriStr>5__3
0x6b805  ldloc.s  5
0x6b807  brfalse  loc_6B986
0x6b80c  nop
0x6b80d  ldloc.0
0x6b80e  ldc.i4.1
0x6b80f  beq      loc_6B8AD
0x6b814  ldloc.0
0x6b815  ldc.i4.2
0x6b816  beq      loc_6B930
0x6b81b  ldarg.0
0x6b81c  ldarg.0
0x6b81d  ldfld    string <InitializeChannelsAsync>d__16::<channelUriStr>5__3
0x6b822  newobj   instance void [System]System.Uri::.ctor(string)
0x6b827  stfld    class [System]System.Uri <InitializeChannelsAsync>d__16::<channelUri>5__4
0x6b82c  ldloc.3
0x6b82d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6b832  brfalse.s loc_6B837
0x6b834  ldnull
0x6b835  br.s     loc_6B83D
0x6b837  ldloc.3
0x6b838  newobj   instance void [System]System.Uri::.ctor(string)
0x6b83d  stloc.s  0xC
0x6b83f  ldloc.s  4
0x6b841  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6b846  brfalse.s loc_6B84B
0x6b848  ldnull
0x6b849  br.s     loc_6B852
0x6b84b  ldloc.s  4
0x6b84d  newobj   instance void [System]System.Uri::.ctor(string)
0x6b852  stloc.s  0xD
0x6b854  ldarg.0
0x6b855  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <InitializeChannelsAsync>d__16::<channelManager>5__2
0x6b85a  ldarg.0
0x6b85b  ldfld    class [System]System.Uri <InitializeChannelsAsync>d__16::<channelUri>5__4
0x6b860  ldloc.s  0xC
0x6b862  ldarg.0
0x6b863  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <InitializeChannelsAsync>d__16::token
0x6b868  ldloc.s  0xD
0x6b86a  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager::AddAsync(class [System]System.Uri, class [System]System.Uri, valuetype [mscorlib]System.Threading.CancellationToken, class [System]System.Uri)
0x6b86f  ldc.i4.0
0x6b870  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair>::ConfigureAwait(!!T0)
0x6b875  stloc.s  0x10
0x6b877  ldloca.s 0x10
0x6b879  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair>::GetAwaiter()
0x6b87e  stloc.s  0xF
0x6b880  ldloca.s 0xF
0x6b882  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair>::get_IsCompleted()
0x6b887  brtrue.s loc_6B8CA
0x6b889  ldarg.0
0x6b88a  ldc.i4.1
0x6b88b  dup
0x6b88c  stloc.0
0x6b88d  stfld    int32 <InitializeChannelsAsync>d__16::<>1__state
0x6b892  ldarg.0
0x6b893  ldloc.s  0xF
0x6b895  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair> <InitializeChannelsAsync>d__16::<>u__2
0x6b89a  ldarg.0
0x6b89b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeChannelsAsync>d__16::<>t__builder
0x6b8a0  ldloca.s 0xF
0x6b8a2  ldarg.0
0x6b8a3  call     T0x2B000455
0x6b8a8  leave    loc_6BA05
0x6b8ad  ldarg.0
0x6b8ae  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair> <InitializeChannelsAsync>d__16::<>u__2
0x6b8b3  stloc.s  0xF
0x6b8b5  ldarg.0
0x6b8b6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair> <InitializeChannelsAsync>d__16::<>u__2
0x6b8bb  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair>
0x6b8c1  ldarg.0
0x6b8c2  ldc.i4.m1
0x6b8c3  dup
0x6b8c4  stloc.0
0x6b8c5  stfld    int32 <InitializeChannelsAsync>d__16::<>1__state
0x6b8ca  ldloca.s 0xF
0x6b8cc  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair>::GetResult()
0x6b8d1  stloc.s  0xE
0x6b8d3  ldloc.s  0xE
0x6b8d5  brtrue.s loc_6B8E5
0x6b8d7  ldloc.1
0x6b8d8  ldarg.0
0x6b8d9  ldfld    class [System]System.Uri <InitializeChannelsAsync>d__16::<channelUri>5__4
0x6b8de  call     instance void Microsoft.VisualStudio.Setup.Installer.Services.AppInitializerService::ShowChannelDownloadError(class [System]System.Uri channelUri)
0x6b8e3  br.s     loc_6B962
0x6b8e5  ldarg.0
0x6b8e6  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <InitializeChannelsAsync>d__16::<channelManager>5__2
0x6b8eb  ldloc.s  0xE
0x6b8ed  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<bool> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager::AddCatalogForChannelAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair)
0x6b8f2  ldc.i4.0
0x6b8f3  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0x6b8f8  stloc.s  0x12
0x6b8fa  ldloca.s 0x12
0x6b8fc  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0x6b901  stloc.s  0x11
0x6b903  ldloca.s 0x11
0x6b905  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::get_IsCompleted()
0x6b90a  brtrue.s loc_6B94D
0x6b90c  ldarg.0
0x6b90d  ldc.i4.2
0x6b90e  dup
0x6b90f  stloc.0
0x6b910  stfld    int32 <InitializeChannelsAsync>d__16::<>1__state
0x6b915  ldarg.0
0x6b916  ldloc.s  0x11
0x6b918  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <InitializeChannelsAsync>d__16::<>u__3
0x6b91d  ldarg.0
0x6b91e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeChannelsAsync>d__16::<>t__builder
0x6b923  ldloca.s 0x11
0x6b925  ldarg.0
0x6b926  call     T0x2B000456
0x6b92b  leave    loc_6BA05
0x6b930  ldarg.0
0x6b931  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <InitializeChannelsAsync>d__16::<>u__3
0x6b936  stloc.s  0x11
0x6b938  ldarg.0
0x6b939  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <InitializeChannelsAsync>d__16::<>u__3
0x6b93e  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>
0x6b944  ldarg.0
0x6b945  ldc.i4.m1
0x6b946  dup
0x6b947  stloc.0
  ... truncated ...
```
