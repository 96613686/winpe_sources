# Microsoft.VisualStudio.Setup.Installer.Commands.MigrateToChannelCommand::SelectChannelMigrationProductId

- ea: `0x54800`
- end: `0x54891`
- name: `Microsoft.VisualStudio.Setup.Installer.Commands.MigrateToChannelCommand::SelectChannelMigrationProductId`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x89530`

## callees

- `0x21b30`
- `0x3b590`
- `0x54800`
- `0x59380`
- `0x89620`

## string_xrefs

- `0x54838`: `Microsoft.VisualStudio.Product.Community`
- `0x5485f`: `Microsoft.VisualStudio.Product.Community`
- `0x5488b`: `Microsoft.VisualStudio.Product.Community`

## pseudocode

```c

```

## disassembly

```asm
0x54800  newobj   instance void <>c__DisplayClass11_0::.ctor()
0x54805  stloc.0
0x54806  ldarg.0
0x54807  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions Microsoft.VisualStudio.Setup.Installer.Commands.MigrateToChannelCommand::installOptions
0x5480c  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ProductId()
0x54811  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x54816  brtrue.s loc_54824
0x54818  ldarg.0
0x54819  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions Microsoft.VisualStudio.Setup.Installer.Commands.MigrateToChannelCommand::installOptions
0x5481e  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ProductId()
0x54823  ret
0x54824  ldarg.1
0x54825  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x5482a  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x5482f  stloc.1
0x54830  ldloc.0
0x54831  ldarg.0
0x54832  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.IMigrationEligibilityService Microsoft.VisualStudio.Setup.Installer.Commands.MigrateToChannelCommand::migrationEligibilityService
0x54837  ldloc.1
0x54838  ldstr    aMicrosoftVisua_2// "Microsoft.VisualStudio.Product.Communit"...
0x5483d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel> Microsoft.VisualStudio.Setup.Installer.Services.IMigrationEligibilityService::GetEligibleMigrationSources(int32 targetMajorVersion, string targetProductId)
0x54842  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel> <>c__DisplayClass11_0::eligibleProducts
0x54847  ldc.i4.3
0x54848  newarr   [mscorlib]System.String
0x5484d  dup
0x5484e  ldc.i4.0
0x5484f  ldstr    aMicrosoftVisua_6// "Microsoft.VisualStudio.Product.Enterpri"...
0x54854  stelem.ref
0x54855  dup
0x54856  ldc.i4.1
0x54857  ldstr    aMicrosoftVisua_4// "Microsoft.VisualStudio.Product.Professi"...
0x5485c  stelem.ref
0x5485d  dup
0x5485e  ldc.i4.2
0x5485f  ldstr    aMicrosoftVisua_2// "Microsoft.VisualStudio.Product.Communit"...
0x54864  stelem.ref
0x54865  ldloc.0
0x54866  ldftn    instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel> <>c__DisplayClass11_0::<SelectChannelMigrationProductId>b__0(string id)
0x5486c  newobj   instance void class [mscorlib]System.Func`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel>>::.ctor(object, native int)
0x54871  call     T0x2B000356
0x54876  call     T0x2B000357
0x5487b  dup
0x5487c  brtrue.s loc_54882
0x5487e  pop
0x5487f  ldnull
0x54880  br.s     loc_54887
0x54882  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Id()
0x54887  dup
0x54888  brtrue.s loc_54890
0x5488a  pop
0x5488b  ldstr    aMicrosoftVisua_2// "Microsoft.VisualStudio.Product.Communit"...
0x54890  ret
```
