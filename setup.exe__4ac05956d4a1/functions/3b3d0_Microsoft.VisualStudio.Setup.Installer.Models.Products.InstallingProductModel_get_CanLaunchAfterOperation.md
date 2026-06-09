# Microsoft.VisualStudio.Setup.Installer.Models.Products.InstallingProductModel::get_CanLaunchAfterOperation

- ea: `0x3b3d0`
- end: `0x3b4e1`
- name: `Microsoft.VisualStudio.Setup.Installer.Models.Products.InstallingProductModel::get_CanLaunchAfterOperation`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3b2e0`

## callees

- `0x219d0`
- `0x219e0`
- `0x2c8e0`
- `0x2c8f0`
- `0x3b170`
- `0x3b210`
- `0x3b3d0`
- `0x599f0`

## string_xrefs

- `0x3b3e9`: `Microsoft.VisualStudio.Product.Community`
- `0x3b401`: `Microsoft.VisualStudio.Product.CommunityX86`

## pseudocode

```c

```

## disassembly

```asm
0x3b3d0  ldarg.0
0x3b3d1  ldflda   valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.Installer.Models.Products.InstallingProductModel::canLaunchAfterOperation
0x3b3d6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x3b3db  brtrue   loc_3B4D5
0x3b3e0  ldc.i4.s 9
0x3b3e2  newarr   [mscorlib]System.String
0x3b3e7  dup
0x3b3e8  ldc.i4.0
0x3b3e9  ldstr    aMicrosoftVisua_2// "Microsoft.VisualStudio.Product.Communit"...
0x3b3ee  stelem.ref
0x3b3ef  dup
0x3b3f0  ldc.i4.1
0x3b3f1  ldstr    aMicrosoftVisua_4// "Microsoft.VisualStudio.Product.Professi"...
0x3b3f6  stelem.ref
0x3b3f7  dup
0x3b3f8  ldc.i4.2
0x3b3f9  ldstr    aMicrosoftVisua_6// "Microsoft.VisualStudio.Product.Enterpri"...
0x3b3fe  stelem.ref
0x3b3ff  dup
0x3b400  ldc.i4.3
0x3b401  ldstr    aMicrosoftVisua_3// "Microsoft.VisualStudio.Product.Communit"...
0x3b406  stelem.ref
0x3b407  dup
0x3b408  ldc.i4.4
0x3b409  ldstr    aMicrosoftVisua_5// "Microsoft.VisualStudio.Product.Professi"...
0x3b40e  stelem.ref
0x3b40f  dup
0x3b410  ldc.i4.5
0x3b411  ldstr    aMicrosoftVisua_7// "Microsoft.VisualStudio.Product.Enterpri"...
0x3b416  stelem.ref
0x3b417  dup
0x3b418  ldc.i4.6
0x3b419  ldstr    aMicrosoftVisua_10// "Microsoft.VisualStudio.Product.SQL"
0x3b41e  stelem.ref
0x3b41f  dup
0x3b420  ldc.i4.7
0x3b421  ldstr    aMicrosoftVisua_11// "Microsoft.VisualStudio.Product.TeamExpl"...
0x3b426  stelem.ref
0x3b427  dup
0x3b428  ldc.i4.8
0x3b429  ldstr    aMicrosoftVisua_12// "Microsoft.VisualStudio.Product.WDExpres"...
0x3b42e  stelem.ref
0x3b42f  ldarg.0
0x3b430  call     instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.InstallingProductModel::get_Id()
0x3b435  call     T0x2B00009D
0x3b43a  brtrue.s loc_3B44D
0x3b43c  ldarg.0
0x3b43d  ldc.i4.0
0x3b43e  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x3b443  stfld    valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.Installer.Models.Products.InstallingProductModel::canLaunchAfterOperation
0x3b448  br       loc_3B4D5
0x3b44d  ldarg.0
0x3b44e  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallingProductServiceOptions Microsoft.VisualStudio.Setup.Installer.Models.Products.InstallingProductModel::serviceOptions
0x3b453  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallingProductServiceOptions::get_InstallerSettings()
0x3b458  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService::get_Passive()
0x3b45d  brfalse.s loc_3B4A1
0x3b45f  ldarg.0
0x3b460  ldarg.0
0x3b461  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallingProductServiceOptions Microsoft.VisualStudio.Setup.Installer.Models.Products.InstallingProductModel::serviceOptions
0x3b466  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.ICommandLineOptionsService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallingProductServiceOptions::get_CommandLineService()
0x3b46b  callvirt T0x2B00007A
0x3b470  dup
0x3b471  brtrue.s loc_3B477
0x3b473  pop
0x3b474  ldnull
0x3b475  br.s     loc_3B47C
0x3b477  call     instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions::get_DevenvLaunchArguments()
0x3b47c  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3b481  ldc.i4.0
0x3b482  ceq
0x3b484  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x3b489  stfld    valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.Installer.Models.Products.InstallingProductModel::canLaunchAfterOperation
0x3b48e  ldarg.0
0x3b48f  ldarg.0
0x3b490  ldflda   valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.Installer.Models.Products.InstallingProductModel::canLaunchAfterOperation
0x3b495  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x3b49a  stfld    bool Microsoft.VisualStudio.Setup.Installer.Models.Products.InstallingProductModel::launchAfterOperation
0x3b49f  br.s     loc_3B4D5
0x3b4a1  ldarg.0
0x3b4a2  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallingProductServiceOptions Microsoft.VisualStudio.Setup.Installer.Models.Products.InstallingProductModel::serviceOptions
0x3b4a7  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallingProductServiceOptions::get_InstallerSettings()
0x3b4ac  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService::get_Quiet()
0x3b4b1  brfalse.s loc_3B4C1
0x3b4b3  ldarg.0
0x3b4b4  ldc.i4.0
0x3b4b5  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x3b4ba  stfld    valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.Installer.Models.Products.InstallingProductModel::canLaunchAfterOperation
0x3b4bf  br.s     loc_3B4D5
0x3b4c1  ldarg.0
0x3b4c2  ldarg.0
0x3b4c3  call     instance valuetype Microsoft.VisualStudio.Setup.Installer.UserExecuteAction Microsoft.VisualStudio.Setup.Installer.Models.Products.InstallingProductModel::get_Action()
0x3b4c8  ldc.i4.1
0x3b4c9  ceq
0x3b4cb  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x3b4d0  stfld    valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.Installer.Models.Products.InstallingProductModel::canLaunchAfterOperation
0x3b4d5  ldarg.0
0x3b4d6  ldflda   valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.Installer.Models.Products.InstallingProductModel::canLaunchAfterOperation
0x3b4db  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x3b4e0  ret
```
