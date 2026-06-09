# Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::AddSelectInstanceMessages

- ea: `0x5a990`
- end: `0x5a9ec`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::AddSelectInstanceMessages`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x5a830`

## callees

- `0x59620`
- `0x59660`
- `0x596c0`
- `0x5a730`
- `0x5a990`
- `0x5aa50`
- `0x5aa90`

## string_xrefs

- `0x5a99e`: `InstallPath`

## pseudocode

```c

```

## disassembly

```asm
0x5a990  ldarg.0
0x5a991  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_InstallPath()
0x5a996  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5a99b  brtrue.s loc_5A9B5
0x5a99d  ldarg.2
0x5a99e  ldstr    aInstallpath// "InstallPath"
0x5a9a3  ldarg.0
0x5a9a4  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_InstallPath()
0x5a9a9  ldarg.1
0x5a9aa  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::GetOptionValueMessage(string optionPropertyName, string optionValue, class [mscorlib]System.Type optionType)
0x5a9af  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x5a9b4  ret
0x5a9b5  ldarg.2
0x5a9b6  ldarg.0
0x5a9b7  ldarg.1
0x5a9b8  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::GetChannelIdOrChannelUriMessage(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions options, class [mscorlib]System.Type optionType)
0x5a9bd  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x5a9c2  ldarg.2
0x5a9c3  ldstr    aProductid_0// "ProductId"
0x5a9c8  ldarg.0
0x5a9c9  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_ProductId()
0x5a9ce  ldarg.1
0x5a9cf  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::GetOptionValueMessage(string optionPropertyName, string optionValue, class [mscorlib]System.Type optionType)
0x5a9d4  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x5a9d9  ldarg.2
0x5a9da  ldstr    aProductarch// "ProductArch"
0x5a9df  ldarg.0
0x5a9e0  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_ProductArch()
0x5a9e5  ldarg.1
0x5a9e6  call     void Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::AddProductArchMessage(class [mscorlib]System.Collections.Generic.IList`1<string> messages, string argumentName, string productArch, class [mscorlib]System.Type optionsType)
0x5a9eb  ret
```
