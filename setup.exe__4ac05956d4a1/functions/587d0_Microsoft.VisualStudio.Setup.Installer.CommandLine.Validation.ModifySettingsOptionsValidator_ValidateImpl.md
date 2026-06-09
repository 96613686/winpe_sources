# Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ModifySettingsOptionsValidator::ValidateImpl

- ea: `0x587d0`
- end: `0x588b7`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ModifySettingsOptionsValidator::ValidateImpl`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x587d0`
- `0x588e0`
- `0x58cb0`
- `0x58cd0`
- `0x58d10`
- `0x59820`
- `0x59840`
- `0x59860`
- `0x59880`

## string_xrefs

- `0x5882e`: `ChannelUri`
- `0x58858`: `ChannelUri`
- `0x58871`: `ChannelUri`
- `0x5888c`: `ChannelUri`
- `0x58838`: `InstallPath`
- `0x588a5`: `NewChannelUri`

## pseudocode

```c

```

## disassembly

```asm
0x587d0  ldarg.1
0x587d1  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions
0x587d6  stloc.0
0x587d7  ldloc.0
0x587d8  brtrue.s loc_587DC
0x587da  ldc.i4.0
0x587db  ret
0x587dc  ldarg.0
0x587dd  ldloc.0
0x587de  call     instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.NonVerbOptionsValidator::ValidateImpl(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions options)
0x587e3  pop
0x587e4  ldloc.0
0x587e5  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions::get_InstallPath()
0x587ea  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x587ef  ldc.i4.0
0x587f0  ceq
0x587f2  ldloc.0
0x587f3  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions::get_ProductId()
0x587f8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x587fd  ldc.i4.0
0x587fe  ceq
0x58800  stloc.1
0x58801  ldloc.0
0x58802  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions::get_ChannelUri()
0x58807  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5880c  ldc.i4.0
0x5880d  ceq
0x5880f  stloc.2
0x58810  ldloc.0
0x58811  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions::get_NewChannelUri()
0x58816  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5881b  ldc.i4.0
0x5881c  ceq
0x5881e  stloc.3
0x5881f  dup
0x58820  brtrue.s loc_58848
0x58822  ldloc.2
0x58823  brtrue.s loc_58848
0x58825  ldloc.1
0x58826  brtrue.s loc_58848
0x58828  ldarg.1
0x58829  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5882e  ldstr    aChanneluri_0// "ChannelUri"
0x58833  ldstr    aProductid_0// "ProductId"
0x58838  ldstr    aInstallpath// "InstallPath"
0x5883d  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ValidationUtilities::GetRequiredSelectInstanceOptionsErrorMessage(class [mscorlib]System.Type optionType, string requiredOption1, string requiredOption2, string requiredOption3)
0x58842  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x58847  throw
0x58848  brtrue.s loc_5889C
0x5884a  ldloc.1
0x5884b  brtrue.s loc_58868
0x5884d  ldarg.1
0x5884e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x58853  ldstr    aProductid_0// "ProductId"
0x58858  ldstr    aChanneluri_0// "ChannelUri"
0x5885d  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ValidationUtilities::GetRequiredOptionCommandLineErrorMessage(class [mscorlib]System.Type optionType, string requiredOption, string providedOption)
0x58862  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x58867  throw
0x58868  ldloc.2
0x58869  brtrue.s loc_58886
0x5886b  ldarg.1
0x5886c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x58871  ldstr    aChanneluri_0// "ChannelUri"
0x58876  ldstr    aProductid_0// "ProductId"
0x5887b  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ValidationUtilities::GetRequiredOptionCommandLineErrorMessage(class [mscorlib]System.Type optionType, string requiredOption, string providedOption)
0x58880  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x58885  throw
0x58886  ldloc.0
0x58887  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions::get_ChannelUri()
0x5888c  ldstr    aChanneluri_0// "ChannelUri"
0x58891  ldloc.0
0x58892  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x58897  call     void Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ValidationUtilities::ValidateUri(string uri, string option, class [mscorlib]System.Type optionType)
0x5889c  ldloc.3
0x5889d  brfalse.s loc_588B5
0x5889f  ldloc.0
0x588a0  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions::get_NewChannelUri()
0x588a5  ldstr    aNewchanneluri// "NewChannelUri"
0x588aa  ldloc.0
0x588ab  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x588b0  call     void Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ValidationUtilities::ValidateUri(string uri, string option, class [mscorlib]System.Type optionType)
0x588b5  ldc.i4.1
0x588b6  ret
```
