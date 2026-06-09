# Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.ModifySettingsCommandLineHandler::ShouldBlockModifySetting

- ea: `0x5b500`
- end: `0x5b59c`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.ModifySettingsCommandLineHandler::ShouldBlockModifySetting`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x8d290`

## callees

- `0xa1f0`
- `0x2bb50`
- `0x2bb70`
- `0x36e80`
- `0x3a7c0`
- `0x3b530`
- `0x5b500`

## string_xrefs

- `0x5b57a`: `Failed to parse Channel Manifest `

## pseudocode

```c

```

## disassembly

```asm
0x5b500  ldarg.1
0x5b501  callvirt instance valuetype Microsoft.VisualStudio.Setup.Installer.Models.Products.ProductInstallState Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_InstallState()
0x5b506  ldc.i4.3
0x5b507  bne.un.s loc_5B50B
0x5b509  ldc.i4.1
0x5b50a  ret
0x5b50b  ldarg.1
0x5b50c  callvirt instance valuetype Microsoft.VisualStudio.Setup.Installer.Models.Products.ProductInstallState Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_InstallState()
0x5b511  ldc.i4.1
0x5b512  bne.un   loc_5B598
0x5b517  ldarg.1
0x5b518  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::IsLayoutInstallation(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel product)
0x5b51d  brfalse.s loc_5B596
0x5b51f  ldarg.2
0x5b520  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5b525  brtrue.s loc_5B596
0x5b527  ldarg.0
0x5b528  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.ModifySettingsCommandLineHandler::serviceOptions
0x5b52d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_FileSystem()
0x5b532  ldarg.2
0x5b533  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x5b538  brfalse.s loc_5B596
0x5b53a  ldarg.0
0x5b53b  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.ModifySettingsCommandLineHandler::serviceOptions
0x5b540  ldarg.2
0x5b541  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifest::Parse(class [mscorlib]System.IServiceProvider, string)
0x5b546  stloc.0
0x5b547  ldloc.0
0x5b548  brfalse.s loc_5B566
0x5b54a  ldloc.0
0x5b54b  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x5b550  ldarg.1
0x5b551  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.VersionBundle Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel::get_Versions()
0x5b556  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Installer.Models.VersionBundle::get_BuildVersion()
0x5b55b  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x5b560  brfalse.s loc_5B566
0x5b562  ldc.i4.0
0x5b563  stloc.1
0x5b564  leave.s  loc_5B59A
0x5b566  leave.s  loc_5B596
0x5b568  stloc.2
0x5b569  ldarg.0
0x5b56a  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.ModifySettingsCommandLineHandler::serviceOptions
0x5b56f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_Logger()
0x5b574  dup
0x5b575  brtrue.s loc_5B57A
0x5b577  pop
0x5b578  br.s     loc_5B594
0x5b57a  ldstr    aFailedToParseC// "Failed to parse Channel Manifest "
0x5b57f  ldloc.2
0x5b580  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5b585  call     string [mscorlib]System.String::Concat(string, string)
0x5b58a  call     T0x2B000010
0x5b58f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5b594  leave.s  loc_5B596
0x5b596  ldc.i4.1
0x5b597  ret
0x5b598  ldc.i4.0
0x5b599  ret
0x5b59a  ldloc.1
0x5b59b  ret
```
