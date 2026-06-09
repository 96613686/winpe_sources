# Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary::PrintMembers

- ea: `0x9de0`
- end: `0x9e8e`
- name: `Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary::PrintMembers`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x9da0`

## callees

- `0x9d00`
- `0x9d20`
- `0x9d40`
- `0x9d60`
- `0x9d80`

## string_xrefs

- `0x9dff`: `, ExtensionNameOrUri = `

## pseudocode

```c

```

## disassembly

```asm
0x9de0  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::EnsureSufficientExecutionStack()
0x9de5  ldarg.1
0x9de6  ldstr    aModel// "Model = "
0x9deb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9df0  pop
0x9df1  ldarg.1
0x9df2  ldarg.0
0x9df3  call     instance class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary::get_Model()
0x9df8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x9dfd  pop
0x9dfe  ldarg.1
0x9dff  ldstr    aExtensionnameo// ", ExtensionNameOrUri = "
0x9e04  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9e09  pop
0x9e0a  ldarg.1
0x9e0b  ldarg.0
0x9e0c  call     instance string Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary::get_ExtensionNameOrUri()
0x9e11  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x9e16  pop
0x9e17  ldarg.1
0x9e18  ldstr    aErrorstate// ", ErrorState = "
0x9e1d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9e22  pop
0x9e23  ldarg.1
0x9e24  ldarg.0
0x9e25  call     instance valuetype Microsoft.VisualStudio.Setup.Installer.ExtensionModelErrorState Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary::get_ErrorState()
0x9e2a  stloc.0
0x9e2b  ldloca.s 0
0x9e2d  constrained. Microsoft.VisualStudio.Setup.Installer.ExtensionModelErrorState
0x9e33  callvirt instance string [mscorlib]System.Object::ToString()
0x9e38  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9e3d  pop
0x9e3e  ldarg.1
0x9e3f  ldstr    aOrigin// ", Origin = "
0x9e44  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9e49  pop
0x9e4a  ldarg.1
0x9e4b  ldarg.0
0x9e4c  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionOrigin Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary::get_Origin()
0x9e51  stloc.1
0x9e52  ldloca.s 1
0x9e54  constrained. [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionOrigin
0x9e5a  callvirt instance string [mscorlib]System.Object::ToString()
0x9e5f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9e64  pop
0x9e65  ldarg.1
0x9e66  ldstr    aVerificationre// ", VerificationResult = "
0x9e6b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9e70  pop
0x9e71  ldarg.1
0x9e72  ldarg.0
0x9e73  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary::get_VerificationResult()
0x9e78  stloc.2
0x9e79  ldloca.s 2
0x9e7b  constrained. [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult
0x9e81  callvirt instance string [mscorlib]System.Object::ToString()
0x9e86  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9e8b  pop
0x9e8c  ldc.i4.1
0x9e8d  ret
```
