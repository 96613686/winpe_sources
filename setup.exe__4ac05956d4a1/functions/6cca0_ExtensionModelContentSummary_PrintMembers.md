# ExtensionModelContentSummary::PrintMembers

- ea: `0x6cca0`
- end: `0x6ccd9`
- name: `ExtensionModelContentSummary::PrintMembers`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x6cc60`

## callees

- `0x6cc20`
- `0x6cc40`

## string_xrefs

- `0x6cca6`: `ExtensionContents = `
- `0x6ccbf`: `, ExtensionModelSummary = `

## pseudocode

```c

```

## disassembly

```asm
0x6cca0  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::EnsureSufficientExecutionStack()
0x6cca5  ldarg.1
0x6cca6  ldstr    aExtensionconte_0// "ExtensionContents = "
0x6ccab  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6ccb0  pop
0x6ccb1  ldarg.1
0x6ccb2  ldarg.0
0x6ccb3  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents ExtensionModelContentSummary::get_ExtensionContents()
0x6ccb8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x6ccbd  pop
0x6ccbe  ldarg.1
0x6ccbf  ldstr    aExtensionmodel_1// ", ExtensionModelSummary = "
0x6ccc4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6ccc9  pop
0x6ccca  ldarg.1
0x6cccb  ldarg.0
0x6cccc  call     instance class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary ExtensionModelContentSummary::get_ExtensionModelSummary()
0x6ccd1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x6ccd6  pop
0x6ccd7  ldc.i4.1
0x6ccd8  ret
```
