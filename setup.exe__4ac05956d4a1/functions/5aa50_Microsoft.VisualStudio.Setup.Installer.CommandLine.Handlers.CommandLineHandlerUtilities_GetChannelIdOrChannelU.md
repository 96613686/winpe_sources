# Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::GetChannelIdOrChannelUriMessage

- ea: `0x5aa50`
- end: `0x5aa81`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::GetChannelIdOrChannelUriMessage`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x5a830`
- `0x5a990`

## callees

- `0x59640`
- `0x596a0`
- `0x5a730`
- `0x5aa50`

## string_xrefs

- `0x5aa5d`: `ChannelUri`

## pseudocode

```c

```

## disassembly

```asm
0x5aa50  ldarg.0
0x5aa51  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_ChannelUri()
0x5aa56  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5aa5b  brtrue.s loc_5AA6F
0x5aa5d  ldstr    aChanneluri_0// "ChannelUri"
0x5aa62  ldarg.0
0x5aa63  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_ChannelUri()
0x5aa68  ldarg.1
0x5aa69  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::GetOptionValueMessage(string optionPropertyName, string optionValue, class [mscorlib]System.Type optionType)
0x5aa6e  ret
0x5aa6f  ldstr    aChannelid_0// "ChannelId"
0x5aa74  ldarg.0
0x5aa75  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_ChannelId()
0x5aa7a  ldarg.1
0x5aa7b  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::GetOptionValueMessage(string optionPropertyName, string optionValue, class [mscorlib]System.Type optionType)
0x5aa80  ret
```
