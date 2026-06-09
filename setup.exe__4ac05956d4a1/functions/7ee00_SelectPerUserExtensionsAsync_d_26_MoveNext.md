# <SelectPerUserExtensionsAsync>d__26::MoveNext

- ea: `0x7ee00`
- end: `0x7f157`
- name: `<SelectPerUserExtensionsAsync>d__26::MoveNext`
- size: `855`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x2b950`
- `0x2b960`
- `0x3dde0`
- `0x3de40`
- `0x43f50`
- `0x44040`
- `0x44090`
- `0x7ee00`

## string_xrefs

- `0x7ef82`: `Skipping extension pack `
- `0x7ee4f`: `There are no per-user extensions to migrate.`
- `0x7eeb0`: `extension.vsixmanifest`
- `0x7eee4`: `Skipping directory {0} as it does not contain a valid VSIX manifest.`
- `0x7efd5`: `Skipping embedded extension child `
- `0x7f03e`: `Excluding {0} pre-discovered packed extensions.`
- `0x7f07f`: `Found {0} per-user extensions to select from.`

## pseudocode

```c

```

## disassembly

```asm
0x7ee00  ldarg.0
0x7ee01  ldfld    int32 <SelectPerUserExtensionsAsync>d__26::<>1__state
0x7ee06  stloc.0
0x7ee07  ldarg.0
0x7ee08  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer <SelectPerUserExtensionsAsync>d__26::<>4__this
0x7ee0d  stloc.1
0x7ee0e  ldloc.0
0x7ee0f  brfalse  loc_7F0EE
0x7ee14  ldloc.1
0x7ee15  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::serviceOptions
0x7ee1a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions::get_FileSystem()
0x7ee1f  ldarg.0
0x7ee20  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductModel <SelectPerUserExtensionsAsync>d__26::migrateFromProduct
0x7ee25  call     string Microsoft.VisualStudio.Setup.Installer.Utilities.Utilities::GetPerUserExtensionsDirectory(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductModel product)
0x7ee2a  stloc.3
0x7ee2b  ldloc.1
0x7ee2c  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::serviceOptions
0x7ee31  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions::get_FileSystem()
0x7ee36  ldloc.3
0x7ee37  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x7ee3c  brtrue.s loc_7EE69
0x7ee3e  ldloc.1
0x7ee3f  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::serviceOptions
0x7ee44  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions::get_Logger()
0x7ee49  dup
0x7ee4a  brtrue.s loc_7EE4F
0x7ee4c  pop
0x7ee4d  br.s     loc_7EE5E
0x7ee4f  ldstr    aThereAreNoPerU// "There are no per-user extensions to mig"...
0x7ee54  call     T0x2B000010
0x7ee59  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7ee5e  call     T0x2B000032
0x7ee63  stloc.2
0x7ee64  leave    loc_7F13B
0x7ee69  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x7ee6e  stloc.s  4
0x7ee70  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x7ee75  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x7ee7a  stloc.s  5
0x7ee7c  ldarg.0
0x7ee7d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x7ee82  stfld    class [mscorlib]System.Collections.Generic.List`1<string> <SelectPerUserExtensionsAsync>d__26::<failedExtensionPacks>5__2
0x7ee87  ldloc.1
0x7ee88  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::serviceOptions
0x7ee8d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions::get_FileSystem()
0x7ee92  ldloc.3
0x7ee93  ldc.i4.0
0x7ee94  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::GetDirectories(string, bool)
0x7ee99  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x7ee9e  stloc.s  6
0x7eea0  br       loc_7F005
0x7eea5  ldloc.s  6
0x7eea7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x7eeac  stloc.s  7
0x7eeae  ldloc.s  7
0x7eeb0  ldstr    aExtensionVsixm// "extension.vsixmanifest"
0x7eeb5  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x7eeba  stloc.s  8
0x7eebc  ldloc.1
0x7eebd  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::serviceOptions
0x7eec2  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions::get_FileSystem()
0x7eec7  ldloc.s  8
0x7eec9  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x7eece  brtrue.s loc_7EEFE
0x7eed0  ldloc.1
0x7eed1  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::serviceOptions
0x7eed6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions::get_Logger()
0x7eedb  dup
0x7eedc  brtrue.s loc_7EEE4
0x7eede  pop
0x7eedf  br       loc_7F005
0x7eee4  ldstr    aSkippingDirect// "Skipping directory {0} as it does not c"...
0x7eee9  ldc.i4.1
0x7eeea  newarr   [mscorlib]System.Object
0x7eeef  dup
0x7eef0  ldc.i4.0
0x7eef1  ldloc.s  7
0x7eef3  stelem.ref
0x7eef4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7eef9  br       loc_7F005
0x7eefe  ldloc.1
0x7eeff  ldloc.s  5
0x7ef01  ldloc.s  7
0x7ef03  call     instance bool Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::AddPackedExtensionIds(class [System]System.Collections.Generic.ISet`1<string> excludedPackIds, string directory)
0x7ef08  stloc.s  9
0x7ef0a  ldloc.1
0x7ef0b  ldloc.s  7
0x7ef0d  call     instance bool Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::IsEmbeddedExtensionChild(string directory)
0x7ef12  stloc.s  0xA
0x7ef14  ldloc.1
0x7ef15  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::serviceOptions
0x7ef1a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions::get_FileSystem()
0x7ef1f  ldloc.1
0x7ef20  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::serviceOptions
0x7ef25  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions::get_Logger()
0x7ef2a  ldloc.s  8
0x7ef2c  call     valuetype [mscorlib]System.ValueTuple`2<string, string> Microsoft.VisualStudio.Setup.Installer.Utilities.Utilities::TryGetExtensionVsixIdFromManifest(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger fileSystem, string logger)
0x7ef31  dup
0x7ef32  ldfld    var<u1> valuetype [mscorlib]System.ValueTuple`2<string, string>::Item1
0x7ef37  stloc.s  0xB
0x7ef39  ldfld    var<u1> valuetype [mscorlib]System.ValueTuple`2<string, string>::Item2
0x7ef3e  stloc.s  0xC
0x7ef40  ldloc.s  0xB
0x7ef42  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7ef47  brtrue   loc_7F005
0x7ef4c  ldloc.s  9
0x7ef4e  brfalse.s loc_7EFC0
0x7ef50  ldloc.1
0x7ef51  ldfld    bool Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::includeExtensionPacks
0x7ef56  brtrue.s loc_7EFC0
0x7ef58  ldloc.s  0xC
0x7ef5a  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x7ef5f  brfalse.s loc_7EF65
0x7ef61  ldloc.s  0xB
0x7ef63  br.s     loc_7EF67
0x7ef65  ldloc.s  0xC
0x7ef67  stloc.s  0xD
0x7ef69  ldloc.1
0x7ef6a  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::serviceOptions
0x7ef6f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions::get_Logger()
0x7ef74  dup
0x7ef75  brtrue.s loc_7EF7A
0x7ef77  pop
0x7ef78  br.s     loc_7EFB1
0x7ef7a  ldc.i4.5
0x7ef7b  newarr   [mscorlib]System.String
0x7ef80  dup
0x7ef81  ldc.i4.0
0x7ef82  ldstr    aSkippingExtens// "Skipping extension pack "
0x7ef87  stelem.ref
0x7ef88  dup
0x7ef89  ldc.i4.1
0x7ef8a  ldloc.s  0xD
0x7ef8c  stelem.ref
0x7ef8d  dup
0x7ef8e  ldc.i4.2
0x7ef8f  ldstr    asc_A3916// " ("
0x7ef94  stelem.ref
0x7ef95  dup
0x7ef96  ldc.i4.3
0x7ef97  ldloc.s  0xB
0x7ef99  stelem.ref
0x7ef9a  dup
0x7ef9b  ldc.i4.4
0x7ef9c  ldstr    asc_A391C// ")."
0x7efa1  stelem.ref
0x7efa2  call     string [mscorlib]System.String::Concat(string[])
0x7efa7  call     T0x2B000010
0x7efac  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7efb1  ldarg.0
0x7efb2  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <SelectPerUserExtensionsAsync>d__26::<failedExtensionPacks>5__2
0x7efb7  ldloc.s  0xD
0x7efb9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7efbe  br.s     loc_7F005
0x7efc0  ldloc.s  0xA
0x7efc2  brfalse.s loc_7EFFC
0x7efc4  ldloc.1
0x7efc5  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::serviceOptions
0x7efca  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions::get_Logger()
0x7efcf  dup
0x7efd0  brtrue.s loc_7EFD5
0x7efd2  pop
0x7efd3  br.s     loc_7EFF0
0x7efd5  ldstr    aSkippingEmbedd// "Skipping embedded extension child "
0x7efda  ldloc.s  0xB
0x7efdc  ldstr    asc_9EBEA// "."
0x7efe1  call     string [mscorlib]System.String::Concat(string, string, string)
0x7efe6  call     T0x2B000010
0x7efeb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7eff0  ldloc.s  5
0x7eff2  ldloc.s  0xB
0x7eff4  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x7eff9  pop
0x7effa  br.s     loc_7F005
0x7effc  ldloc.s  4
0x7effe  ldloc.s  0xB
0x7f000  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7f005  ldloc.s  6
0x7f007  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7f00c  brtrue   loc_7EEA5
0x7f011  leave.s  loc_7F023
0x7f013  ldloc.0
0x7f014  ldc.i4.0
0x7f015  bge.s    loc_7F022
0x7f017  ldloc.s  6
0x7f019  brfalse.s loc_7F022
0x7f01b  ldloc.s  6
0x7f01d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7f022  endfinally
0x7f023  ldloc.s  5
0x7f025  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<string>::get_Count()
0x7f02a  ldc.i4.0
0x7f02b  ble.s    loc_7F06E
0x7f02d  ldloc.1
0x7f02e  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::serviceOptions
0x7f033  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions::get_Logger()
0x7f038  dup
0x7f039  brtrue.s loc_7F03E
0x7f03b  pop
0x7f03c  br.s     loc_7F05E
0x7f03e  ldstr    aExcluding0PreD// "Excluding {0} pre-discovered packed ext"...
0x7f043  ldloc.s  5
0x7f045  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<string>::get_Count()
0x7f04a  box      [mscorlib]System.Int32
0x7f04f  call     string [mscorlib]System.String::Format(string, object)
0x7f054  call     T0x2B000010
0x7f059  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7f05e  ldloc.s  4
0x7f060  ldloc.s  5
0x7f062  call     T0x2B00050C
0x7f067  call     T0x2B000122
0x7f06c  stloc.s  4
0x7f06e  ldloc.1
0x7f06f  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::serviceOptions
0x7f074  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions::get_Logger()
0x7f079  dup
0x7f07a  brtrue.s loc_7F07F
0x7f07c  pop
0x7f07d  br.s     loc_7F09F
0x7f07f  ldstr    aFound0PerUserE// "Found {0} per-user extensions to select"...
0x7f084  ldloc.s  4
0x7f086  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x7f08b  box      [mscorlib]System.Int32
0x7f090  call     string [mscorlib]System.String::Format(string, object)
0x7f095  call     T0x2B000010
0x7f09a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7f09f  ldloc.1
0x7f0a0  ldarg.0
0x7f0a1  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <SelectPerUserExtensionsAsync>d__26::product
0x7f0a6  ldloc.s  4
0x7f0a8  ldarg.0
0x7f0a9  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <SelectPerUserExtensionsAsync>d__26::cancellationToken
0x7f0ae  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::SelectMarketplaceExtensionsFromVsixIdsAsync(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel product, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> vsixIds, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x7f0b3  ldc.i4.0
0x7f0b4  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x7f0b9  stloc.s  0xF
0x7f0bb  ldloca.s 0xF
0x7f0bd  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x7f0c2  stloc.s  0xE
0x7f0c4  ldloca.s 0xE
0x7f0c6  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x7f0cb  brtrue.s loc_7F10B
0x7f0cd  ldarg.0
0x7f0ce  ldc.i4.0
0x7f0cf  dup
0x7f0d0  stloc.0
0x7f0d1  stfld    int32 <SelectPerUserExtensionsAsync>d__26::<>1__state
0x7f0d6  ldarg.0
0x7f0d7  ldloc.s  0xE
0x7f0d9  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SelectPerUserExtensionsAsync>d__26::<>u__1
0x7f0de  ldarg.0
0x7f0df  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <SelectPerUserExtensionsAsync>d__26::<>t__builder
0x7f0e4  ldloca.s 0xE
0x7f0e6  ldarg.0
0x7f0e7  call     T0x2B000543
0x7f0ec  leave.s  loc_7F156
0x7f0ee  ldarg.0
0x7f0ef  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SelectPerUserExtensionsAsync>d__26::<>u__1
0x7f0f4  stloc.s  0xE
0x7f0f6  ldarg.0
0x7f0f7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SelectPerUserExtensionsAsync>d__26::<>u__1
0x7f0fc  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x7f102  ldarg.0
0x7f103  ldc.i4.m1
0x7f104  dup
0x7f105  stloc.0
0x7f106  stfld    int32 <SelectPerUserExtensionsAsync>d__26::<>1__state
0x7f10b  ldloca.s 0xE
0x7f10d  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x7f112  ldarg.0
0x7f113  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <SelectPerUserExtensionsAsync>d__26::<failedExtensionPacks>5__2
0x7f118  stloc.2
0x7f119  leave.s  loc_7F13B
0x7f11b  stloc.s  0x10
0x7f11d  ldarg.0
0x7f11e  ldc.i4.s 0xFE
0x7f120  stfld    int32 <SelectPerUserExtensionsAsync>d__26::<>1__state
0x7f125  ldarg.0
0x7f126  ldnull
0x7f127  stfld    class [mscorlib]System.Collections.Generic.List`1<string> <SelectPerUserExtensionsAsync>d__26::<failedExtensionPacks>5__2
0x7f12c  ldarg.0
0x7f12d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <SelectPerUserExtensionsAsync>d__26::<>t__builder
0x7f132  ldloc.s  0x10
0x7f134  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::SetException(class [mscorlib]System.Exception)
0x7f139  leave.s  loc_7F156
0x7f13b  ldarg.0
0x7f13c  ldc.i4.s 0xFE
0x7f13e  stfld    int32 <SelectPerUserExtensionsAsync>d__26::<>1__state
0x7f143  ldarg.0
0x7f144  ldnull
0x7f145  stfld    class [mscorlib]System.Collections.Generic.List`1<string> <SelectPerUserExtensionsAsync>d__26::<failedExtensionPacks>5__2
0x7f14a  ldarg.0
0x7f14b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <SelectPerUserExtensionsAsync>d__26::<>t__builder
0x7f150  ldloc.2
0x7f151  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::SetResult(var<u1>)
0x7f156  ret
```
