# Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::AddSelectInstanceMessages_0

- ea: `0x5a9f0`
- end: `0x5aa44`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::AddSelectInstanceMessages_0`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x5a830`

## callees

- `0x59820`
- `0x59840`
- `0x59880`
- `0x5a730`
- `0x5a9f0`

## string_xrefs

- `0x5aa16`: `ChannelUri`
- `0x5a9fe`: `InstallPath`

## pseudocode

```c

```

## disassembly

```asm
0x5a9f0  ldarg.0
0x5a9f1  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions::get_InstallPath()
0x5a9f6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5a9fb  brtrue.s loc_5AA15
0x5a9fd  ldarg.2
0x5a9fe  ldstr    aInstallpath// "InstallPath"
0x5aa03  ldarg.0
0x5aa04  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions::get_InstallPath()
0x5aa09  ldarg.1
0x5aa0a  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::GetOptionValueMessage(string optionPropertyName, string optionValue, class [mscorlib]System.Type optionType)
0x5aa0f  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x5aa14  ret
0x5aa15  ldarg.2
0x5aa16  ldstr    aChanneluri_0// "ChannelUri"
0x5aa1b  ldarg.0
0x5aa1c  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions::get_ChannelUri()
0x5aa21  ldarg.1
0x5aa22  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::GetOptionValueMessage(string optionPropertyName, string optionValue, class [mscorlib]System.Type optionType)
0x5aa27  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x5aa2c  ldarg.2
0x5aa2d  ldstr    aProductid_0// "ProductId"
0x5aa32  ldarg.0
0x5aa33  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions::get_ProductId()
0x5aa38  ldarg.1
0x5aa39  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::GetOptionValueMessage(string optionPropertyName, string optionValue, class [mscorlib]System.Type optionType)
0x5aa3e  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x5aa43  ret
```
