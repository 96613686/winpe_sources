# Microsoft.VisualStudio.Setup.Installer.ChannelMigration.MigrationTargetArgs::PrintMembers

- ea: `0x5ce70`
- end: `0x5cf02`
- name: `Microsoft.VisualStudio.Setup.Installer.ChannelMigration.MigrationTargetArgs::PrintMembers`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x5ce30`

## callees

- `0x5cd90`
- `0x5cdb0`
- `0x5cdd0`
- `0x5cdf0`
- `0x5ce10`

## string_xrefs

- `0x5cee8`: `, ConfigPath = `
- `0x5ce8f`: `, IncludeRecommended = `

## pseudocode

```c

```

## disassembly

```asm
0x5ce70  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::EnsureSufficientExecutionStack()
0x5ce75  ldarg.1
0x5ce76  ldstr    aProduct_1// "Product = "
0x5ce7b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5ce80  pop
0x5ce81  ldarg.1
0x5ce82  ldarg.0
0x5ce83  call     instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel Microsoft.VisualStudio.Setup.Installer.ChannelMigration.MigrationTargetArgs::get_Product()
0x5ce88  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x5ce8d  pop
0x5ce8e  ldarg.1
0x5ce8f  ldstr    aIncluderecomme_1// ", IncludeRecommended = "
0x5ce94  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5ce99  pop
0x5ce9a  ldarg.1
0x5ce9b  ldarg.0
0x5ce9c  call     instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.MigrationTargetArgs::get_IncludeRecommended()
0x5cea1  stloc.0
0x5cea2  ldloca.s 0
0x5cea4  constrained. [mscorlib]System.Boolean
0x5ceaa  callvirt instance string [mscorlib]System.Object::ToString()
0x5ceaf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5ceb4  pop
0x5ceb5  ldarg.1
0x5ceb6  ldstr    aSelectioniniti// ", SelectionInitializer = "
0x5cebb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5cec0  pop
0x5cec1  ldarg.1
0x5cec2  ldarg.0
0x5cec3  call     instance class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ISelectionInitializer Microsoft.VisualStudio.Setup.Installer.ChannelMigration.MigrationTargetArgs::get_SelectionInitializer()
0x5cec8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x5cecd  pop
0x5cece  ldarg.1
0x5cecf  ldstr    aMigratefrom// ", MigrateFrom = "
0x5ced4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5ced9  pop
0x5ceda  ldarg.1
0x5cedb  ldarg.0
0x5cedc  call     instance string Microsoft.VisualStudio.Setup.Installer.ChannelMigration.MigrationTargetArgs::get_MigrateFrom()
0x5cee1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x5cee6  pop
0x5cee7  ldarg.1
0x5cee8  ldstr    aConfigpath// ", ConfigPath = "
0x5ceed  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5cef2  pop
0x5cef3  ldarg.1
0x5cef4  ldarg.0
0x5cef5  call     instance string Microsoft.VisualStudio.Setup.Installer.ChannelMigration.MigrationTargetArgs::get_ConfigPath()
0x5cefa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x5ceff  pop
0x5cf00  ldc.i4.1
0x5cf01  ret
```
