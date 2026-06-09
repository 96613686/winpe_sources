# Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::GetMissingProductMessage

- ea: `0x5a830`
- end: `0x5a989`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::GetMissingProductMessage`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x5a7d0`

## callees

- `0x9c50`
- `0x59380`
- `0x595c0`
- `0x59d90`
- `0x5a730`
- `0x5a830`
- `0x5a990`
- `0x5a9f0`
- `0x5aa50`
- `0x5aa90`

## string_xrefs

- `0x5a911`: `InstallPath`

## pseudocode

```c

```

## disassembly

```asm
0x5a830  ldarg.0
0x5a831  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5a836  stloc.0
0x5a837  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5a83c  stloc.1
0x5a83d  ldarg.0
0x5a83e  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions
0x5a843  stloc.2
0x5a844  ldloc.2
0x5a845  brtrue.s loc_5A886
0x5a847  ldarg.0
0x5a848  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ExportOptions
0x5a84d  stloc.3
0x5a84e  ldloc.3
0x5a84f  brtrue   loc_5A8D7
0x5a854  ldarg.0
0x5a855  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ResumeOptions
0x5a85a  stloc.s  4
0x5a85c  ldloc.s  4
0x5a85e  brtrue   loc_5A8FA
0x5a863  ldarg.0
0x5a864  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions
0x5a869  stloc.s  5
0x5a86b  ldloc.s  5
0x5a86d  brtrue   loc_5A92A
0x5a872  ldarg.0
0x5a873  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions
0x5a878  stloc.s  6
0x5a87a  ldloc.s  6
0x5a87c  brtrue   loc_5A94B
0x5a881  br       loc_5A96C
0x5a886  ldloc.1
0x5a887  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_NoProductFoundMessage()
0x5a88c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5a891  ldloc.1
0x5a892  ldsfld   string [mscorlib]System.String::Empty
0x5a897  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5a89c  ldloc.1
0x5a89d  ldloc.2
0x5a89e  ldloc.0
0x5a89f  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::GetChannelIdOrChannelUriMessage(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions options, class [mscorlib]System.Type optionType)
0x5a8a4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5a8a9  ldloc.1
0x5a8aa  ldstr    aProductid_0// "ProductId"
0x5a8af  ldloc.2
0x5a8b0  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ProductId()
0x5a8b5  ldloc.0
0x5a8b6  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::GetOptionValueMessage(string optionPropertyName, string optionValue, class [mscorlib]System.Type optionType)
0x5a8bb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5a8c0  ldloc.1
0x5a8c1  ldstr    aProductarch// "ProductArch"
0x5a8c6  ldloc.2
0x5a8c7  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions::get_ProductArch()
0x5a8cc  ldloc.0
0x5a8cd  call     void Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::AddProductArchMessage(class [mscorlib]System.Collections.Generic.IList`1<string> messages, string argumentName, string productArch, class [mscorlib]System.Type optionsType)
0x5a8d2  br       loc_5A982
0x5a8d7  ldloc.1
0x5a8d8  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_NoProductFoundMessage()
0x5a8dd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5a8e2  ldloc.1
0x5a8e3  ldsfld   string [mscorlib]System.String::Empty
0x5a8e8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5a8ed  ldloc.3
0x5a8ee  ldloc.0
0x5a8ef  ldloc.1
0x5a8f0  call     void Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::AddSelectInstanceMessages(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions options, class [mscorlib]System.Type optionType, class [mscorlib]System.Collections.Generic.IList`1<string> messages)
0x5a8f5  br       loc_5A982
0x5a8fa  ldloc.1
0x5a8fb  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_NoInstalledProductFoundMessage()
0x5a900  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5a905  ldloc.1
0x5a906  ldsfld   string [mscorlib]System.String::Empty
0x5a90b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5a910  ldloc.1
0x5a911  ldstr    aInstallpath// "InstallPath"
0x5a916  ldloc.s  4
0x5a918  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ResumeOptions::get_InstallPath()
0x5a91d  ldloc.0
0x5a91e  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::GetOptionValueMessage(string optionPropertyName, string optionValue, class [mscorlib]System.Type optionType)
0x5a923  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5a928  br.s     loc_5A982
0x5a92a  ldloc.1
0x5a92b  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_NoInstalledProductFoundMessage()
0x5a930  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5a935  ldloc.1
0x5a936  ldsfld   string [mscorlib]System.String::Empty
0x5a93b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5a940  ldloc.s  5
0x5a942  ldloc.0
0x5a943  ldloc.1
0x5a944  call     void Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::AddSelectInstanceMessages(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions options, class [mscorlib]System.Type optionType, class [mscorlib]System.Collections.Generic.IList`1<string> messages)
0x5a949  br.s     loc_5A982
0x5a94b  ldloc.1
0x5a94c  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_NoInstalledProductFoundMessage()
0x5a951  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5a956  ldloc.1
0x5a957  ldsfld   string [mscorlib]System.String::Empty
0x5a95c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5a961  ldloc.s  6
0x5a963  ldloc.0
0x5a964  ldloc.1
0x5a965  call     void Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::AddSelectInstanceMessages(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ModifySettingsOptions options, class [mscorlib]System.Type optionType, class [mscorlib]System.Collections.Generic.IList`1<string> messages)
0x5a96a  br.s     loc_5A982
0x5a96c  ldstr    aCannotDetermin// "Cannot determine missing product messag"...
0x5a971  ldloc.0
0x5a972  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x5a977  call     string [mscorlib]System.String::Concat(string, string)
0x5a97c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x5a981  throw
0x5a982  ldloc.1
0x5a983  call     string Microsoft.VisualStudio.Setup.Installer.CommonUtilities::CreateMultiLineErrorMessage(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> messages)
0x5a988  ret
```
