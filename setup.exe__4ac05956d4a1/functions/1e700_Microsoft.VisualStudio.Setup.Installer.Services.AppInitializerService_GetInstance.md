# Microsoft.VisualStudio.Setup.Installer.Services.AppInitializerService::GetInstance

- ea: `0x1e700`
- end: `0x1e7c3`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.AppInitializerService::GetInstance`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x6b620`

## callees

- `0x1e700`
- `0x2b6e0`
- `0x59620`
- `0x59640`
- `0x59660`
- `0x6b030`

## string_xrefs

- `0x1e745`: `No instance found for path `

## pseudocode

```c

```

## disassembly

```asm
0x1e700  newobj   instance void <>c__DisplayClass24_0::.ctor()
0x1e705  stloc.0
0x1e706  ldloc.0
0x1e707  ldarg.1
0x1e708  stfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions <>c__DisplayClass24_0::options
0x1e70d  ldarg.0
0x1e70e  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.AppInitializerService::serviceOptions
0x1e713  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IQueryFactory Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions::get_QueryFactory()
0x1e718  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IQuery [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IQueryFactory::Create()
0x1e71d  stloc.1
0x1e71e  ldloc.0
0x1e71f  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions <>c__DisplayClass24_0::options
0x1e724  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_InstallPath()
0x1e729  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1e72e  brtrue.s loc_1E763
0x1e730  ldloc.1
0x1e731  ldloc.0
0x1e732  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions <>c__DisplayClass24_0::options
0x1e737  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_InstallPath()
0x1e73c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IQuery::GetInstanceForPath(string)
0x1e741  dup
0x1e742  brtrue.s loc_1E760
0x1e744  pop
0x1e745  ldstr    aNoInstanceFoun// "No instance found for path "
0x1e74a  ldloc.0
0x1e74b  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions <>c__DisplayClass24_0::options
0x1e750  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_InstallPath()
0x1e755  call     string [mscorlib]System.String::Concat(string, string)
0x1e75a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1e75f  throw
0x1e760  stloc.2
0x1e761  leave.s  loc_1E7C1
0x1e763  ldloc.0
0x1e764  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_InvariantCultureIgnoreCase()
0x1e769  stfld    class [mscorlib]System.StringComparer <>c__DisplayClass24_0::comparer
0x1e76e  ldloc.1
0x1e76f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IQuery::GetAllInstances()
0x1e774  ldloc.0
0x1e775  ldftn    instance bool <>c__DisplayClass24_0::<GetInstance>b__0(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance x)
0x1e77b  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance, bool>::.ctor(object, native int)
0x1e780  call     T0x2B0000F4
0x1e785  dup
0x1e786  brtrue.s loc_1E7B4
0x1e788  pop
0x1e789  ldstr    aNoInstanceFoun_0// "No instance found with productId "
0x1e78e  ldloc.0
0x1e78f  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions <>c__DisplayClass24_0::options
0x1e794  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_ProductId()
0x1e799  ldstr    aAndChannelid// " and channelId "
0x1e79e  ldloc.0
0x1e79f  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions <>c__DisplayClass24_0::options
0x1e7a4  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_ChannelId()
0x1e7a9  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1e7ae  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1e7b3  throw
0x1e7b4  stloc.2
0x1e7b5  leave.s  loc_1E7C1
0x1e7b7  ldloc.1
0x1e7b8  brfalse.s loc_1E7C0
0x1e7ba  ldloc.1
0x1e7bb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e7c0  endfinally
0x1e7c1  ldloc.2
0x1e7c2  ret
```
