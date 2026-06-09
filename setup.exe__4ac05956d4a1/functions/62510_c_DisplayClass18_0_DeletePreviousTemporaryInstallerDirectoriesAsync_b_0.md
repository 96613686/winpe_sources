# <>c__DisplayClass18_0::<DeletePreviousTemporaryInstallerDirectoriesAsync>b__0

- ea: `0x62510`
- end: `0x6266d`
- name: `<>c__DisplayClass18_0::<DeletePreviousTemporaryInstallerDirectoriesAsync>b__0`
- size: `349`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callees

- `0x7570`
- `0x7630`
- `0x62510`

## string_xrefs

- `0x625cc`: `Deleting directory: {0}`
- `0x62617`: `Failed to delete directory: {0}`
- `0x6265b`: `Failed to deleted previous temporary installers`

## pseudocode

```c

```

## disassembly

```asm
0x62510  ldarg.0
0x62511  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <>c__DisplayClass18_0::cancellationToken
0x62516  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x6251b  ldarg.0
0x6251c  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager <>c__DisplayClass18_0::<>4__this
0x62521  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x62526  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_FileSystem()
0x6252b  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_SharedProgramsDirectory()
0x62530  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.BootstrapperConstants::InstallerSubDirectory
0x62535  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x6253a  stloc.0
0x6253b  ldloc.0
0x6253c  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x62541  stloc.1
0x62542  ldarg.0
0x62543  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager <>c__DisplayClass18_0::<>4__this
0x62548  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x6254d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_FileSystem()
0x62552  ldloc.1
0x62553  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x62558  brtrue.s loc_6255F
0x6255a  leave    loc_6266C
0x6255f  ldloc.0
0x62560  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x62565  ldstr    asc_9EBEA// "."
0x6256a  call     string [mscorlib]System.String::Concat(string, string)
0x6256f  stloc.2
0x62570  ldarg.0
0x62571  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager <>c__DisplayClass18_0::<>4__this
0x62576  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x6257b  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_FileSystem()
0x62580  ldloc.1
0x62581  ldc.i4.0
0x62582  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::GetDirectories(string, bool)
0x62587  call     T0x2B000034
0x6258c  stloc.3
0x6258d  ldc.i4.0
0x6258e  stloc.s  4
0x62590  br       loc_62632
0x62595  ldloc.3
0x62596  ldloc.s  4
0x62598  ldelem.ref
0x62599  stloc.s  5
0x6259b  ldarg.0
0x6259c  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <>c__DisplayClass18_0::cancellationToken
0x625a1  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x625a6  ldloc.s  5
0x625a8  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x625ad  ldloc.2
0x625ae  ldc.i4.5
0x625af  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x625b4  brfalse.s loc_6262C
0x625b6  ldarg.0
0x625b7  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager <>c__DisplayClass18_0::<>4__this
0x625bc  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x625c1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x625c6  dup
0x625c7  brtrue.s loc_625CC
0x625c9  pop
0x625ca  br.s     loc_625E1
0x625cc  ldstr    aDeletingDirect// "Deleting directory: {0}"
0x625d1  ldc.i4.1
0x625d2  newarr   [mscorlib]System.Object
0x625d7  dup
0x625d8  ldc.i4.0
0x625d9  ldloc.s  5
0x625db  stelem.ref
0x625dc  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x625e1  ldarg.0
0x625e2  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager <>c__DisplayClass18_0::<>4__this
0x625e7  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x625ec  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_FileSystem()
0x625f1  ldloc.s  5
0x625f3  ldc.i4.1
0x625f4  ldc.i4.2
0x625f5  ldc.i4   0x1F4
0x625fa  call     bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extensions::TryDeleteDirectoryWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem, string, bool, int32, int32)
0x625ff  brtrue.s loc_6262C
0x62601  ldarg.0
0x62602  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager <>c__DisplayClass18_0::<>4__this
0x62607  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x6260c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x62611  dup
0x62612  brtrue.s loc_62617
0x62614  pop
0x62615  br.s     loc_6262C
0x62617  ldstr    aFailedToDelete_2// "Failed to delete directory: {0}"
0x6261c  ldc.i4.1
0x6261d  newarr   [mscorlib]System.Object
0x62622  dup
0x62623  ldc.i4.0
0x62624  ldloc.s  5
0x62626  stelem.ref
0x62627  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x6262c  ldloc.s  4
0x6262e  ldc.i4.1
0x6262f  add
0x62630  stloc.s  4
0x62632  ldloc.s  4
0x62634  ldloc.3
0x62635  ldlen
0x62636  conv.i4
0x62637  blt      loc_62595
0x6263c  leave.s  loc_6266C
0x6263e  pop
0x6263f  rethrow
0x62641  stloc.s  6
0x62643  ldarg.0
0x62644  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager <>c__DisplayClass18_0::<>4__this
0x62649  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerUpdateManager::serviceOptions
0x6264e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerUpdateManagerServiceOptions::get_Logger()
0x62653  dup
0x62654  brtrue.s loc_62659
0x62656  pop
0x62657  br.s     loc_6266A
0x62659  ldloc.s  6
0x6265b  ldstr    aFailedToDelete_3// "Failed to deleted previous temporary in"...
0x62660  call     T0x2B000010
0x62665  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x6266a  leave.s  loc_6266C
0x6266c  ret
```
