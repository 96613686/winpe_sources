# Microsoft.VisualStudio.Setup.Installer.CommandLine.NonVerbOptionsLaunchProductArgumentsProvider::.cctor

- ea: `0x57400`
- end: `0x57446`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.NonVerbOptionsLaunchProductArgumentsProvider::.cctor`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x57408`: `Microsoft.VisualStudio.Product.Community`
- `0x57420`: `Microsoft.VisualStudio.Product.CommunityX86`

## pseudocode

```c

```

## disassembly

```asm
0x57400  ldc.i4.6
0x57401  newarr   [mscorlib]System.String
0x57406  dup
0x57407  ldc.i4.0
0x57408  ldstr    aMicrosoftVisua_2// "Microsoft.VisualStudio.Product.Communit"...
0x5740d  stelem.ref
0x5740e  dup
0x5740f  ldc.i4.1
0x57410  ldstr    aMicrosoftVisua_4// "Microsoft.VisualStudio.Product.Professi"...
0x57415  stelem.ref
0x57416  dup
0x57417  ldc.i4.2
0x57418  ldstr    aMicrosoftVisua_6// "Microsoft.VisualStudio.Product.Enterpri"...
0x5741d  stelem.ref
0x5741e  dup
0x5741f  ldc.i4.3
0x57420  ldstr    aMicrosoftVisua_3// "Microsoft.VisualStudio.Product.Communit"...
0x57425  stelem.ref
0x57426  dup
0x57427  ldc.i4.4
0x57428  ldstr    aMicrosoftVisua_5// "Microsoft.VisualStudio.Product.Professi"...
0x5742d  stelem.ref
0x5742e  dup
0x5742f  ldc.i4.5
0x57430  ldstr    aMicrosoftVisua_7// "Microsoft.VisualStudio.Product.Enterpri"...
0x57435  stelem.ref
0x57436  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x5743b  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>, !!T0)
0x57440  stsfld   class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.NonVerbOptionsLaunchProductArgumentsProvider::DevEnvProducts
0x57445  ret
```
