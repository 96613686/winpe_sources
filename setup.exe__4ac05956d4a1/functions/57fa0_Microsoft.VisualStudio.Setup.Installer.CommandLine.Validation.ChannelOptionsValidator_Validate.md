# Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ChannelOptionsValidator::Validate

- ea: `0x57fa0`
- end: `0x58025`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ChannelOptionsValidator::Validate`
- size: `133`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x58390`
- `0x58400`
- `0x58bc0`

## callees

- `0x57fa0`
- `0x58cd0`
- `0x58d10`
- `0x59120`
- `0x59140`

## string_xrefs

- `0x57fc9`: `ChannelUri`
- `0x57ff1`: `ChannelUri`
- `0x57fce`: `InstallChannelUri`
- `0x58014`: `InstallChannelUri`

## pseudocode

```c

```

## disassembly

```asm
0x57fa0  ldarg.0
0x57fa1  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IChannelOptions::get_InstallChannelUri()
0x57fa6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x57fab  brtrue.s loc_57FDE
0x57fad  ldarg.0
0x57fae  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IChannelOptions::get_ChannelUri()
0x57fb3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x57fb8  brfalse.s loc_57FDE
0x57fba  ldarg.0
0x57fbb  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions
0x57fc0  brfalse.s loc_57FC3
0x57fc2  ret
0x57fc3  ldarg.0
0x57fc4  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x57fc9  ldstr    aChanneluri_0// "ChannelUri"
0x57fce  ldstr    aInstallchannel// "InstallChannelUri"
0x57fd3  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ValidationUtilities::GetRequiredOptionCommandLineErrorMessage(class [mscorlib]System.Type optionType, string requiredOption, string providedOption)
0x57fd8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x57fdd  throw
0x57fde  ldarg.0
0x57fdf  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IChannelOptions::get_ChannelUri()
0x57fe4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x57fe9  brtrue.s loc_58001
0x57feb  ldarg.0
0x57fec  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IChannelOptions::get_ChannelUri()
0x57ff1  ldstr    aChanneluri_0// "ChannelUri"
0x57ff6  ldarg.0
0x57ff7  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x57ffc  call     void Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ValidationUtilities::ValidateUri(string uri, string option, class [mscorlib]System.Type optionType)
0x58001  ldarg.0
0x58002  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IChannelOptions::get_InstallChannelUri()
0x58007  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5800c  brtrue.s loc_58024
0x5800e  ldarg.0
0x5800f  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IChannelOptions::get_InstallChannelUri()
0x58014  ldstr    aInstallchannel// "InstallChannelUri"
0x58019  ldarg.0
0x5801a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5801f  call     void Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ValidationUtilities::ValidateUri(string uri, string option, class [mscorlib]System.Type optionType)
0x58024  ret
```
