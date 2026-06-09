# Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::PreProcessArgs

- ea: `0x55f70`
- end: `0x56026`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::PreProcessArgs`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x55e30`

## callees

- `0x55d90`
- `0x56030`
- `0x560c0`
- `0x56110`
- `0x56560`

## string_xrefs

- `0x55f88`: `uninstall`
- `0x55f7a`: `finalizeInstall`

## pseudocode

```c

```

## disassembly

```asm
0x55f70  ldarg.0
0x55f71  ldarg.1
0x55f72  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::MergeMultiInstanceOption(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args)
0x55f77  stloc.0
0x55f78  ldarg.0
0x55f79  ldloc.0
0x55f7a  ldstr    aFinalizeinstal_2// "finalizeInstall"
0x55f7f  ldarg.2
0x55f80  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::RemoveSpecialArg(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args, string argument, [out] bool& foundArgument)
0x55f85  stloc.0
0x55f86  ldarg.0
0x55f87  ldloc.0
0x55f88  ldstr    aUninstall_0// "uninstall"
0x55f8d  ldarg.3
0x55f8e  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::RemoveSpecialArg(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args, string argument, [out] bool& foundArgument)
0x55f93  stloc.0
0x55f94  ldarg.0
0x55f95  ldloc.0
0x55f96  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::MoveVerbToFront(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args)
0x55f9b  stloc.0
0x55f9c  ldarg.0
0x55f9d  ldloc.0
0x55f9e  ldstr    aV// "-v"
0x55fa3  ldstr    aVersion_1// "--version"
0x55fa8  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::ConvertAlias(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args, string alias, string supportedOption)
0x55fad  stloc.0
0x55fae  ldarg.0
0x55faf  ldloc.0
0x55fb0  ldstr    aH// "--h"
0x55fb5  ldstr    aHelp// "--help"
0x55fba  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::ConvertAlias(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args, string alias, string supportedOption)
0x55fbf  stloc.0
0x55fc0  ldarg.0
0x55fc1  ldloc.0
0x55fc2  ldstr    aH_0// "-h"
0x55fc7  ldstr    aHelp// "--help"
0x55fcc  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::ConvertAlias(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args, string alias, string supportedOption)
0x55fd1  stloc.0
0x55fd2  ldarg.0
0x55fd3  ldloc.0
0x55fd4  ldstr    asc_A7AAA// "--?"
0x55fd9  ldstr    aHelp// "--help"
0x55fde  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::ConvertAlias(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args, string alias, string supportedOption)
0x55fe3  stloc.0
0x55fe4  ldarg.0
0x55fe5  ldloc.0
0x55fe6  ldstr    asc_A7AB2// "-?"
0x55feb  ldstr    aHelp// "--help"
0x55ff0  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::ConvertAlias(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args, string alias, string supportedOption)
0x55ff5  stloc.0
0x55ff6  ldarg.0
0x55ff7  ldloc.0
0x55ff8  ldstr    aP// "-p"
0x55ffd  ldstr    aPassive_0// "passive"
0x56002  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::GetOptionLongNameWithPrefix(string longName)
0x56007  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::ConvertAlias(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args, string alias, string supportedOption)
0x5600c  stloc.0
0x5600d  ldarg.0
0x5600e  ldloc.0
0x5600f  ldstr    aQ// "-q"
0x56014  ldstr    aQuiet_1// "quiet"
0x56019  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::GetOptionLongNameWithPrefix(string longName)
0x5601e  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::ConvertAlias(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> args, string alias, string supportedOption)
0x56023  stloc.0
0x56024  ldloc.0
0x56025  ret
```
