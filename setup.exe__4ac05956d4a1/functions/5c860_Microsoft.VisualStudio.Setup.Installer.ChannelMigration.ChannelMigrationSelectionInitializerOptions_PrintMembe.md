# Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::PrintMembers

- ea: `0x5c860`
- end: `0x5c9b5`
- name: `Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::PrintMembers`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x5c820`

## callees

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

- `0x5c88d`: `, MigrateFromConfiguration = `
- `0x5c8b4`: `, InstallationPath = `
- `0x5c8cd`: `, ConfigPath = `
- `0x5c90d`: `, IncludeMarketplaceExtensions = `
- `0x5c934`: `, IncludeRecommended = `
- `0x5c95b`: `, IncludeExtensionPacks = `
- `0x5c982`: `, CloseCommand = `
- `0x5c99b`: `, RetryCommand = `

## pseudocode

```c

```

## disassembly

```asm
0x5c860  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::EnsureSufficientExecutionStack()
0x5c865  ldarg.1
0x5c866  ldstr    aMigratefromins// "MigrateFromInstance = "
0x5c86b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5c870  pop
0x5c871  ldarg.1
0x5c872  ldarg.0
0x5c873  call     instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_MigrateFromInstance()
0x5c878  stloc.0
0x5c879  ldloca.s 0
0x5c87b  constrained. [mscorlib]System.Boolean
0x5c881  callvirt instance string [mscorlib]System.Object::ToString()
0x5c886  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5c88b  pop
0x5c88c  ldarg.1
0x5c88d  ldstr    aMigratefromcon// ", MigrateFromConfiguration = "
0x5c892  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5c897  pop
0x5c898  ldarg.1
0x5c899  ldarg.0
0x5c89a  call     instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_MigrateFromConfiguration()
0x5c89f  stloc.0
0x5c8a0  ldloca.s 0
0x5c8a2  constrained. [mscorlib]System.Boolean
0x5c8a8  callvirt instance string [mscorlib]System.Object::ToString()
0x5c8ad  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5c8b2  pop
0x5c8b3  ldarg.1
0x5c8b4  ldstr    aInstallationpa_1// ", InstallationPath = "
0x5c8b9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5c8be  pop
0x5c8bf  ldarg.1
0x5c8c0  ldarg.0
0x5c8c1  call     instance string Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_InstallationPath()
0x5c8c6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x5c8cb  pop
0x5c8cc  ldarg.1
0x5c8cd  ldstr    aConfigpath// ", ConfigPath = "
0x5c8d2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5c8d7  pop
0x5c8d8  ldarg.1
0x5c8d9  ldarg.0
0x5c8da  call     instance string Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_ConfigPath()
0x5c8df  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x5c8e4  pop
0x5c8e5  ldarg.1
0x5c8e6  ldstr    aIncludeoutofsu// ", IncludeOutOfSupport = "
0x5c8eb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5c8f0  pop
0x5c8f1  ldarg.1
0x5c8f2  ldarg.0
0x5c8f3  call     instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_IncludeOutOfSupport()
0x5c8f8  stloc.0
0x5c8f9  ldloca.s 0
0x5c8fb  constrained. [mscorlib]System.Boolean
0x5c901  callvirt instance string [mscorlib]System.Object::ToString()
0x5c906  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5c90b  pop
0x5c90c  ldarg.1
0x5c90d  ldstr    aIncludemarketp// ", IncludeMarketplaceExtensions = "
0x5c912  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5c917  pop
0x5c918  ldarg.1
0x5c919  ldarg.0
0x5c91a  call     instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_IncludeMarketplaceExtensions()
0x5c91f  stloc.0
0x5c920  ldloca.s 0
0x5c922  constrained. [mscorlib]System.Boolean
0x5c928  callvirt instance string [mscorlib]System.Object::ToString()
0x5c92d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5c932  pop
0x5c933  ldarg.1
0x5c934  ldstr    aIncluderecomme_1// ", IncludeRecommended = "
0x5c939  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5c93e  pop
0x5c93f  ldarg.1
0x5c940  ldarg.0
0x5c941  call     instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_IncludeRecommended()
0x5c946  stloc.0
0x5c947  ldloca.s 0
0x5c949  constrained. [mscorlib]System.Boolean
0x5c94f  callvirt instance string [mscorlib]System.Object::ToString()
0x5c954  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5c959  pop
0x5c95a  ldarg.1
0x5c95b  ldstr    aIncludeextensi// ", IncludeExtensionPacks = "
0x5c960  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5c965  pop
0x5c966  ldarg.1
0x5c967  ldarg.0
0x5c968  call     instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_IncludeExtensionPacks()
0x5c96d  stloc.0
0x5c96e  ldloca.s 0
0x5c970  constrained. [mscorlib]System.Boolean
0x5c976  callvirt instance string [mscorlib]System.Object::ToString()
0x5c97b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5c980  pop
0x5c981  ldarg.1
0x5c982  ldstr    aClosecommand// ", CloseCommand = "
0x5c987  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5c98c  pop
0x5c98d  ldarg.1
0x5c98e  ldarg.0
0x5c98f  call     instance class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_CloseCommand()
0x5c994  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x5c999  pop
0x5c99a  ldarg.1
0x5c99b  ldstr    aRetrycommand// ", RetryCommand = "
0x5c9a0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5c9a5  pop
0x5c9a6  ldarg.1
0x5c9a7  ldarg.0
0x5c9a8  call     instance class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ChannelMigrationSelectionInitializerOptions::get_RetryCommand()
0x5c9ad  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x5c9b2  pop
0x5c9b3  ldc.i4.1
0x5c9b4  ret
```
