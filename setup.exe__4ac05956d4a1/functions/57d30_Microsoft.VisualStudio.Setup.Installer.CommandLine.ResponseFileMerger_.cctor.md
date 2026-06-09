# Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::.cctor

- ea: `0x57d30`
- end: `0x57d97`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::.cctor`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, installer_update, broker_com_uri`

## string_xrefs

- `0x57d47`: `remove`
- `0x57d86`: `remove`
- `0x57d5f`: `removeProductLang`

## pseudocode

```c

```

## disassembly

```asm
0x57d30  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x57d35  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x57d3a  dup
0x57d3b  ldstr    aAdd// "add"
0x57d40  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x57d45  pop
0x57d46  dup
0x57d47  ldstr    aRemove// "remove"
0x57d4c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x57d51  pop
0x57d52  dup
0x57d53  ldstr    aAddproductlang// "addProductLang"
0x57d58  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x57d5d  pop
0x57d5e  dup
0x57d5f  ldstr    aRemoveproductl// "removeProductLang"
0x57d64  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x57d69  pop
0x57d6a  stsfld   class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::SupportedMergeOptions
0x57d6f  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x57d74  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x57d79  dup
0x57d7a  ldstr    aAdd// "add"
0x57d7f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x57d84  pop
0x57d85  dup
0x57d86  ldstr    aRemove// "remove"
0x57d8b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x57d90  pop
0x57d91  stsfld   class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::SupportedMergeAppendedValuesOptions
0x57d96  ret
```
