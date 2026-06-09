# Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerFactory::Create

- ea: `0x5c5b0`
- end: `0x5c642`
- name: `Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerFactory::Create`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x2b900`
- `0x2d290`
- `0x43b10`
- `0x44a10`
- `0x5c5b0`
- `0x5c6e0`
- `0x5c700`
- `0x5c720`
- `0x5c740`
- `0x5c760`
- `0x5c780`
- `0x5c7a0`
- `0x5c7c0`
- `0x5c7e0`
- `0x5c800`

## string_xrefs

- `0x5c5c0`: `InstallationPath must not be null when MigrateFromInstance is true.`
- `0x5c611`: `ConfigPath must not be null when MigrateFromConfiguration is true.`

## pseudocode

```c

```

## disassembly

```asm
0x5c5b0  ldarg.1
0x5c5b1  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_MigrateFromInstance()
0x5c5b6  brfalse.s loc_5C5FF
0x5c5b8  ldarg.1
0x5c5b9  callvirt instance string Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_InstallationPath()
0x5c5be  brtrue.s loc_5C5D0
0x5c5c0  ldstr    aInstallationpa_0// "InstallationPath must not be null when "...
0x5c5c5  ldstr    aOptions// "options"
0x5c5ca  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x5c5cf  throw
0x5c5d0  ldarg.0
0x5c5d1  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ChannelMigrationPageServiceOptions Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerFactory::serviceOptions
0x5c5d6  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions::.ctor(class [mscorlib]System.IServiceProvider services)
0x5c5db  ldarg.1
0x5c5dc  callvirt instance string Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_InstallationPath()
0x5c5e1  ldarg.1
0x5c5e2  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_IncludeOutOfSupport()
0x5c5e7  ldarg.1
0x5c5e8  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_IncludeMarketplaceExtensions()
0x5c5ed  ldarg.1
0x5c5ee  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_IncludeRecommended()
0x5c5f3  ldarg.1
0x5c5f4  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_IncludeExtensionPacks()
0x5c5f9  newobj   instance void Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions serviceOptions, string installationPath, bool includeOutOfSupport, bool includeExtensions, bool includeRecommended, bool includeExtensionPacks)
0x5c5fe  ret
0x5c5ff  ldarg.1
0x5c600  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_MigrateFromConfiguration()
0x5c605  brfalse.s loc_5C640
0x5c607  ldarg.1
0x5c608  callvirt instance string Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_ConfigPath()
0x5c60d  dup
0x5c60e  brtrue.s loc_5C621
0x5c610  pop
0x5c611  ldstr    aConfigpathMust// "ConfigPath must not be null when Migrat"...
0x5c616  ldstr    aOptions// "options"
0x5c61b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x5c620  throw
0x5c621  stloc.0
0x5c622  ldarg.0
0x5c623  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ChannelMigrationPageServiceOptions Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerFactory::serviceOptions
0x5c628  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionViewModelServiceOptions::.ctor(class [mscorlib]System.IServiceProvider services)
0x5c62d  ldloc.0
0x5c62e  ldarg.1
0x5c62f  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_CloseCommand()
0x5c634  ldarg.1
0x5c635  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_RetryCommand()
0x5c63a  newobj   instance void Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ImportDialogSelectionInitializer::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionViewModelServiceOptions selectionServiceOptions, string configPath, class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand closeCommand, class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand retryCommand)
0x5c63f  ret
0x5c640  ldnull
0x5c641  ret
```
