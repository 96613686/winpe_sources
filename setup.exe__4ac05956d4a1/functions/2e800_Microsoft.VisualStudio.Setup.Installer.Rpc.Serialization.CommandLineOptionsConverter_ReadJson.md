# Microsoft.VisualStudio.Setup.Installer.Rpc.Serialization.CommandLineOptionsConverter::ReadJson

- ea: `0x2e800`
- end: `0x2e8b8`
- name: `Microsoft.VisualStudio.Setup.Installer.Rpc.Serialization.CommandLineOptionsConverter::ReadJson`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x2e800`

## string_xrefs

- `0x2e897`: `Unsupported command line verb: {0}`
- `0x2e8ad`: `Invalid command line object`

## pseudocode

```c

```

## disassembly

```asm
0x2e800  ldarg.1
0x2e801  call     class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::Load(class [Newtonsoft.Json]Newtonsoft.Json.JsonReader)
0x2e806  stloc.0
0x2e807  ldloc.0
0x2e808  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Rpc.Serialization.CommandLineOptionsConverter::VerbPropertyKey
0x2e80d  ldc.i4.3
0x2e80e  ldloca.s 1
0x2e810  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::TryGetValue(string, valuetype [mscorlib]System.StringComparison, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken&)
0x2e815  brfalse  loc_2E8AD
0x2e81a  ldloc.1
0x2e81b  callvirt T0x2B00021C
0x2e820  stloc.2
0x2e821  ldloc.2
0x2e822  ldc.i4.1
0x2e823  sub
0x2e824  switch   loc_2E843, loc_2E889, loc_2E851, loc_2E85F, loc_2E87B, loc_2E86D
0x2e841  br.s     loc_2E897
0x2e843  ldarg.s  4
0x2e845  ldloc.0
0x2e846  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.JsonReader [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::CreateReader()
0x2e84b  callvirt T0x2B00021D
0x2e850  ret
0x2e851  ldarg.s  4
0x2e853  ldloc.0
0x2e854  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.JsonReader [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::CreateReader()
0x2e859  callvirt T0x2B00021E
0x2e85e  ret
0x2e85f  ldarg.s  4
0x2e861  ldloc.0
0x2e862  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.JsonReader [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::CreateReader()
0x2e867  callvirt T0x2B00021F
0x2e86c  ret
0x2e86d  ldarg.s  4
0x2e86f  ldloc.0
0x2e870  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.JsonReader [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::CreateReader()
0x2e875  callvirt T0x2B000220
0x2e87a  ret
0x2e87b  ldarg.s  4
0x2e87d  ldloc.0
0x2e87e  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.JsonReader [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::CreateReader()
0x2e883  callvirt T0x2B000221
0x2e888  ret
0x2e889  ldarg.s  4
0x2e88b  ldloc.0
0x2e88c  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.JsonReader [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::CreateReader()
0x2e891  callvirt T0x2B000222
0x2e896  ret
0x2e897  ldstr    aUnsupportedCom// "Unsupported command line verb: {0}"
0x2e89c  ldloc.2
0x2e89d  box      Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineVerb
0x2e8a2  call     string [mscorlib]System.String::Format(string, object)
0x2e8a7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2e8ac  throw
0x2e8ad  ldstr    aInvalidCommand// "Invalid command line object"
0x2e8b2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2e8b7  throw
```
