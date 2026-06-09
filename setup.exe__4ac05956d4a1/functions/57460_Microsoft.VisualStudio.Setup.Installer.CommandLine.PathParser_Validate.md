# Microsoft.VisualStudio.Setup.Installer.CommandLine.PathParser::Validate

- ea: `0x57460`
- end: `0x574dc`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.PathParser::Validate`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x55d00`
- `0x57460`
- `0x574e0`
- `0x59660`
- `0x59680`

## string_xrefs

- `0x57494`: `InstallPath`
- `0x574a4`: `CustomPaths`

## pseudocode

```c

```

## disassembly

```asm
0x57460  ldarg.1
0x57461  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_CustomPaths()
0x57466  call     T0x2B00002F
0x5746b  brtrue.s loc_574DB
0x5746d  ldarg.0
0x5746e  ldarg.1
0x5746f  call     instance class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> Microsoft.VisualStudio.Setup.Installer.CommandLine.PathParser::GetCustomPaths(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions options)
0x57474  stloc.0
0x57475  ldarg.1
0x57476  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_InstallPath()
0x5747b  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x57480  brtrue.s loc_574BF
0x57482  ldloc.0
0x57483  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommandLine.PathParser::InstallPathKey
0x57488  callvirt instance bool class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string>::ContainsKey(var<u1>)
0x5748d  brfalse.s loc_574BF
0x5748f  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_CannotSpecifyInstallPathTwice_Args2()
0x57494  ldstr    aInstallpath// "InstallPath"
0x57499  ldarg.1
0x5749a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5749f  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::GetOptionLongNameWithPrefix(string, class [mscorlib]System.Type optionName)
0x574a4  ldstr    aCustompaths// "CustomPaths"
0x574a9  ldarg.1
0x574aa  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x574af  call     string Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::GetOptionLongNameWithPrefix(string, class [mscorlib]System.Type optionName)
0x574b4  call     string [mscorlib]System.String::Format(string, object, object)
0x574b9  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x574be  throw
0x574bf  leave.s  loc_574DB
0x574c1  pop
0x574c2  rethrow
0x574c4  pop
0x574c5  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_InvalidPaths_Args1()
0x574ca  ldarg.1
0x574cb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_CustomPaths()
0x574d0  call     string [mscorlib]System.String::Format(string, object)
0x574d5  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x574da  throw
0x574db  ret
```
