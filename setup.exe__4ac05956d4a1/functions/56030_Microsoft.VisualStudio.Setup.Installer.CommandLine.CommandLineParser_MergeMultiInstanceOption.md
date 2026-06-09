# Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::MergeMultiInstanceOption

- ea: `0x56030`
- end: `0x560ba`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::MergeMultiInstanceOption`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x55f70`

## callees

- `0x55bb0`
- `0x55d90`

## string_xrefs

- `0x56063`: `remove`
- `0x56030`: `installerFlight`
- `0x56085`: `removeProductLang`

## pseudocode

```c

```

## disassembly

```asm
0x56030  ldstr    aInstallerfligh_1// "installerFlight"
0x56035  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::GetOptionLongNameWithPrefix(string longName)
0x5603a  ldarg.1
0x5603b  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::HandleMultiInstanceOption(string option, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args)
0x56040  stloc.0
0x56041  ldstr    aFlight// "flight"
0x56046  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::GetOptionLongNameWithPrefix(string longName)
0x5604b  ldloc.0
0x5604c  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::HandleMultiInstanceOption(string option, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args)
0x56051  stloc.0
0x56052  ldstr    aAdd// "add"
0x56057  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::GetOptionLongNameWithPrefix(string longName)
0x5605c  ldloc.0
0x5605d  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::HandleMultiInstanceOption(string option, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args)
0x56062  stloc.0
0x56063  ldstr    aRemove// "remove"
0x56068  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::GetOptionLongNameWithPrefix(string longName)
0x5606d  ldloc.0
0x5606e  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::HandleMultiInstanceOption(string option, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args)
0x56073  stloc.0
0x56074  ldstr    aAddproductlang// "addProductLang"
0x56079  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::GetOptionLongNameWithPrefix(string longName)
0x5607e  ldloc.0
0x5607f  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::HandleMultiInstanceOption(string option, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args)
0x56084  stloc.0
0x56085  ldstr    aRemoveproductl// "removeProductLang"
0x5608a  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::GetOptionLongNameWithPrefix(string longName)
0x5608f  ldloc.0
0x56090  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::HandleMultiInstanceOption(string option, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args)
0x56095  stloc.0
0x56096  ldstr    aVsix// "vsix"
0x5609b  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::GetOptionLongNameWithPrefix(string longName)
0x560a0  ldloc.0
0x560a1  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::HandleMultiInstanceOption(string option, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args)
0x560a6  stloc.0
0x560a7  ldstr    aPath// "path"
0x560ac  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::GetOptionLongNameWithPrefix(string longName)
0x560b1  ldloc.0
0x560b2  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::HandleMultiInstanceOption(string option, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args)
0x560b7  stloc.0
0x560b8  ldloc.0
0x560b9  ret
```
