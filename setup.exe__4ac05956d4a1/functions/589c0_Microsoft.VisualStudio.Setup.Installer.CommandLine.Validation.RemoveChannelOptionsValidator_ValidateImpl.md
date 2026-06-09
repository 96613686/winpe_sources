# Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.RemoveChannelOptionsValidator::ValidateImpl

- ea: `0x589c0`
- end: `0x58a12`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.RemoveChannelOptionsValidator::ValidateImpl`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x588e0`
- `0x589c0`
- `0x58c90`
- `0x58d10`
- `0x59c30`

## string_xrefs

- `0x589ea`: `ChannelUri`
- `0x58a00`: `ChannelUri`

## pseudocode

```c

```

## disassembly

```asm
0x589c0  ldarg.1
0x589c1  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.RemoveChannelOptions
0x589c6  stloc.0
0x589c7  ldloc.0
0x589c8  brtrue.s loc_589CC
0x589ca  ldc.i4.0
0x589cb  ret
0x589cc  ldarg.0
0x589cd  ldloc.0
0x589ce  call     instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.NonVerbOptionsValidator::ValidateImpl(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions options)
0x589d3  pop
0x589d4  ldloc.0
0x589d5  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.RemoveChannelOptions::get_ChannelUri()
0x589da  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x589df  ldc.i4.0
0x589e0  ceq
0x589e2  brtrue.s loc_589FA
0x589e4  ldarg.1
0x589e5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x589ea  ldstr    aChanneluri_0// "ChannelUri"
0x589ef  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ValidationUtilities::GetRequiredOptionCommandLineErrorMessage(class [mscorlib]System.Type optionType, string requiredOption)
0x589f4  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x589f9  throw
0x589fa  ldloc.0
0x589fb  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.RemoveChannelOptions::get_ChannelUri()
0x58a00  ldstr    aChanneluri_0// "ChannelUri"
0x58a05  ldloc.0
0x58a06  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x58a0b  call     void Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ValidationUtilities::ValidateUri(string uri, string option, class [mscorlib]System.Type optionType)
0x58a10  ldc.i4.1
0x58a11  ret
```
