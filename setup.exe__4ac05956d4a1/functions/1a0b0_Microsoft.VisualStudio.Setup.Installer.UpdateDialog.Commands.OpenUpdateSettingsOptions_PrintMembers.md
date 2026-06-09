# Microsoft.VisualStudio.Setup.Installer.UpdateDialog.Commands.OpenUpdateSettingsOptions::PrintMembers

- ea: `0x1a0b0`
- end: `0x1a0e9`
- name: `Microsoft.VisualStudio.Setup.Installer.UpdateDialog.Commands.OpenUpdateSettingsOptions::PrintMembers`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1a070`

## callees

- `0x1a050`
- `0x1a060`

## string_xrefs

- `0x1a0b6`: `UpdatePageViewModel = `
- `0x1a0cf`: `, InstalledProduct = `

## pseudocode

```c

```

## disassembly

```asm
0x1a0b0  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::EnsureSufficientExecutionStack()
0x1a0b5  ldarg.1
0x1a0b6  ldstr    aUpdatepageview// "UpdatePageViewModel = "
0x1a0bb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a0c0  pop
0x1a0c1  ldarg.1
0x1a0c2  ldarg.0
0x1a0c3  call     instance class Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.IUpdateMainPageViewModel Microsoft.VisualStudio.Setup.Installer.UpdateDialog.Commands.OpenUpdateSettingsOptions::get_UpdatePageViewModel()
0x1a0c8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x1a0cd  pop
0x1a0ce  ldarg.1
0x1a0cf  ldstr    aInstalledprodu// ", InstalledProduct = "
0x1a0d4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a0d9  pop
0x1a0da  ldarg.1
0x1a0db  ldarg.0
0x1a0dc  call     instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel Microsoft.VisualStudio.Setup.Installer.UpdateDialog.Commands.OpenUpdateSettingsOptions::get_InstalledProduct()
0x1a0e1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x1a0e6  pop
0x1a0e7  ldc.i4.1
0x1a0e8  ret
```
