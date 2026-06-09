# ExtensionContentsSummary::PrintMembers

- ea: `0x6c8f0`
- end: `0x6c99b`
- name: `ExtensionContentsSummary::PrintMembers`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x6c8b0`

## callees

- `0x6c7f0`
- `0x6c810`
- `0x6c830`
- `0x6c850`
- `0x6c870`
- `0x6c890`

## string_xrefs

- `0x6c8f6`: `ExtensionContents = `
- `0x6c90f`: `, EmbeddedExtensions = `
- `0x6c981`: `, ParsedComponents = `

## pseudocode

```c

```

## disassembly

```asm
0x6c8f0  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::EnsureSufficientExecutionStack()
0x6c8f5  ldarg.1
0x6c8f6  ldstr    aExtensionconte_0// "ExtensionContents = "
0x6c8fb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6c900  pop
0x6c901  ldarg.1
0x6c902  ldarg.0
0x6c903  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents ExtensionContentsSummary::get_ExtensionContents()
0x6c908  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x6c90d  pop
0x6c90e  ldarg.1
0x6c90f  ldstr    aEmbeddedextens// ", EmbeddedExtensions = "
0x6c914  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6c919  pop
0x6c91a  ldarg.1
0x6c91b  ldarg.0
0x6c91c  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<class [System]System.Uri, class ExtensionContentsSummary> ExtensionContentsSummary::get_EmbeddedExtensions()
0x6c921  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x6c926  pop
0x6c927  ldarg.1
0x6c928  ldstr    aVerificationre// ", VerificationResult = "
0x6c92d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6c932  pop
0x6c933  ldarg.1
0x6c934  ldarg.0
0x6c935  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult ExtensionContentsSummary::get_VerificationResult()
0x6c93a  stloc.0
0x6c93b  ldloca.s 0
0x6c93d  constrained. [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult
0x6c943  callvirt instance string [mscorlib]System.Object::ToString()
0x6c948  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6c94d  pop
0x6c94e  ldarg.1
0x6c94f  ldstr    aSha256hash_0// ", Sha256Hash = "
0x6c954  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6c959  pop
0x6c95a  ldarg.1
0x6c95b  ldarg.0
0x6c95c  call     instance string ExtensionContentsSummary::get_Sha256Hash()
0x6c961  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x6c966  pop
0x6c967  ldarg.1
0x6c968  ldstr    aCertificate_0// ", Certificate = "
0x6c96d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6c972  pop
0x6c973  ldarg.1
0x6c974  ldarg.0
0x6c975  call     instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 ExtensionContentsSummary::get_Certificate()
0x6c97a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x6c97f  pop
0x6c980  ldarg.1
0x6c981  ldstr    aParsedcomponen// ", ParsedComponents = "
0x6c986  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6c98b  pop
0x6c98c  ldarg.1
0x6c98d  ldarg.0
0x6c98e  call     instance class [System]System.Collections.Generic.ISet`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity> ExtensionContentsSummary::get_ParsedComponents()
0x6c993  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x6c998  pop
0x6c999  ldc.i4.1
0x6c99a  ret
```
