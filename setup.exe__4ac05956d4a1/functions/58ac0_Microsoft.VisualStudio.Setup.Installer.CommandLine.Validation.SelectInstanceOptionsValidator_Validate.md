# Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.SelectInstanceOptionsValidator::Validate

- ea: `0x58ac0`
- end: `0x58b98`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.SelectInstanceOptionsValidator::Validate`
- size: `216`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x58390`
- `0x58690`
- `0x58a40`
- `0x58bc0`
- `0x58c10`

## callees

- `0x572d0`
- `0x572e0`
- `0x58ac0`
- `0x58cb0`
- `0x58cd0`
- `0x58cf0`
- `0x59620`
- `0x59640`
- `0x59660`
- `0x596a0`

## string_xrefs

- `0x58b52`: `ChannelUri`
- `0x58b87`: `ChannelUri`
- `0x58b33`: `InstallPath`

## pseudocode

```c

```

## disassembly

```asm
0x58ac0  ldarg.1
0x58ac1  ldarg.0
0x58ac2  callvirt instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.IPathParser::Validate(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions options)
0x58ac7  ldarg.1
0x58ac8  ldarg.0
0x58ac9  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> Microsoft.VisualStudio.Setup.Installer.CommandLine.IPathParser::GetCustomPaths(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions options)
0x58ace  stloc.0
0x58acf  ldarg.0
0x58ad0  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_InstallPath()
0x58ad5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x58ada  brfalse.s loc_58AE9
0x58adc  ldloc.0
0x58add  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommandLine.PathParser::InstallPathKey
0x58ae2  callvirt instance bool class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string>::ContainsKey(var<u1>)
0x58ae7  br.s     loc_58AEA
0x58ae9  ldc.i4.1
0x58aea  ldarg.0
0x58aeb  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_ProductId()
0x58af0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x58af5  ldc.i4.0
0x58af6  ceq
0x58af8  stloc.1
0x58af9  ldarg.0
0x58afa  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_ChannelId()
0x58aff  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x58b04  ldc.i4.0
0x58b05  ceq
0x58b07  stloc.2
0x58b08  ldarg.0
0x58b09  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_ChannelUri()
0x58b0e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x58b13  ldc.i4.0
0x58b14  ceq
0x58b16  stloc.3
0x58b17  dup
0x58b18  brtrue.s loc_58B43
0x58b1a  ldloc.1
0x58b1b  brtrue.s loc_58B43
0x58b1d  ldloc.2
0x58b1e  brtrue.s loc_58B43
0x58b20  ldloc.3
0x58b21  brtrue.s loc_58B43
0x58b23  ldarg.0
0x58b24  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x58b29  ldstr    aChannelid_0// "ChannelId"
0x58b2e  ldstr    aProductid_0// "ProductId"
0x58b33  ldstr    aInstallpath// "InstallPath"
0x58b38  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ValidationUtilities::GetRequiredSelectInstanceOptionsErrorMessage(class [mscorlib]System.Type optionType, string requiredOption1, string requiredOption2, string requiredOption3)
0x58b3d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x58b42  throw
0x58b43  brtrue.s loc_58B97
0x58b45  ldloc.1
0x58b46  brtrue.s loc_58B71
0x58b48  ldloc.3
0x58b49  brtrue.s loc_58B52
0x58b4b  ldstr    aChannelid_0// "ChannelId"
0x58b50  br.s     loc_58B57
0x58b52  ldstr    aChanneluri_0// "ChannelUri"
0x58b57  stloc.s  4
0x58b59  ldarg.0
0x58b5a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x58b5f  ldstr    aProductid_0// "ProductId"
0x58b64  ldloc.s  4
0x58b66  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ValidationUtilities::GetRequiredOptionCommandLineErrorMessage(class [mscorlib]System.Type optionType, string requiredOption, string providedOption)
0x58b6b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x58b70  throw
0x58b71  ldloc.2
0x58b72  brtrue.s loc_58B97
0x58b74  ldloc.3
0x58b75  brtrue.s loc_58B97
0x58b77  ldarg.0
0x58b78  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x58b7d  ldstr    aProductid_0// "ProductId"
0x58b82  ldstr    aChannelid_0// "ChannelId"
0x58b87  ldstr    aChanneluri_0// "ChannelUri"
0x58b8c  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Validation.ValidationUtilities::GetRequiredOptionCommandLineErrorMessage(class [mscorlib]System.Type optionType, string providedOption, string requiredOption1, string requiredOption2)
0x58b91  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x58b96  throw
0x58b97  ret
```
