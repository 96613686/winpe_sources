# Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::CreateInstaller

- ea: `0x3eaf0`
- end: `0x3edc5`
- name: `Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::CreateInstaller`
- size: `725`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3e890`
- `0x3ea00`

## callees

- `0x2c4b0`
- `0x2c550`
- `0x2c580`
- `0x2c5b0`
- `0x3eaf0`
- `0x3edd0`
- `0x3ede0`
- `0x3ee30`
- `0x3ee40`
- `0x3ee50`
- `0x3ee60`
- `0x3ee70`
- `0x408c0`
- `0x408d0`
- `0x408e0`
- `0x416c0`
- `0x432d0`
- `0x433f0`
- `0x434a0`
- `0x43520`
- `0x435a0`
- `0x436e0`
- `0x43790`

## string_xrefs

- `0x3ed56`: `Created a {0}`
- `0x3eda0`: `UnelevatedInstallerTelemetryDecorator`

## pseudocode

```c

```

## disassembly

```asm
0x3eaf0  ldnull
0x3eaf1  stloc.1
0x3eaf2  ldarg.1
0x3eaf3  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext::get_Options()
0x3eaf8  stloc.s  0xA
0x3eafa  ldloc.s  0xA
0x3eafc  isinst   [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions
0x3eb01  stloc.3
0x3eb02  ldloc.3
0x3eb03  brtrue.s loc_3EB6A
0x3eb05  ldloc.s  0xA
0x3eb07  isinst   [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductRepairerOptions
0x3eb0c  stloc.s  4
0x3eb0e  ldloc.s  4
0x3eb10  brtrue   loc_3EBA6
0x3eb15  ldloc.s  0xA
0x3eb17  isinst   [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductModifierOptions
0x3eb1c  stloc.s  5
0x3eb1e  ldloc.s  5
0x3eb20  brtrue   loc_3EBE7
0x3eb25  ldloc.s  0xA
0x3eb27  isinst   [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions
0x3eb2c  stloc.s  6
0x3eb2e  ldloc.s  6
0x3eb30  brtrue   loc_3EC2A
0x3eb35  ldloc.s  0xA
0x3eb37  isinst   [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductUninstallerOptions
0x3eb3c  stloc.s  7
0x3eb3e  ldloc.s  7
0x3eb40  brtrue   loc_3EC6D
0x3eb45  ldloc.s  0xA
0x3eb47  isinst   [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductResumerOptions
0x3eb4c  stloc.s  8
0x3eb4e  ldloc.s  8
0x3eb50  brtrue   loc_3ECAE
0x3eb55  ldloc.s  0xA
0x3eb57  isinst   [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductReverterOptions
0x3eb5c  stloc.s  9
0x3eb5e  ldloc.s  9
0x3eb60  brtrue   loc_3ECEC
0x3eb65  br       loc_3ED2F
0x3eb6a  ldarg.0
0x3eb6b  ldloc.3
0x3eb6c  ldarg.2
0x3eb6d  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::CreateProductInstaller(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions options, class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerService installerService)
0x3eb72  stloc.0
0x3eb73  ldarg.0
0x3eb74  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3eb79  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_FileSystem()
0x3eb7e  ldarg.0
0x3eb7f  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3eb84  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IReparseAwareFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_ReparseAwareFileSystem()
0x3eb89  ldarg.0
0x3eb8a  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3eb8f  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_PolicyService()
0x3eb94  ldarg.1
0x3eb95  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext::get_Product()
0x3eb9a  ldloc.3
0x3eb9b  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.PropertyProviders.InstallTelemetryPropertyProvider::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IReparseAwareFileSystem reparseAwareFileSystem, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService policyService, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel product, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductInstallerOptions options)
0x3eba0  stloc.1
0x3eba1  br       loc_3ED45
0x3eba6  ldarg.0
0x3eba7  ldloc.s  4
0x3eba9  ldarg.2
0x3ebaa  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::CreateProductRepairer(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductRepairerOptions options, class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerService installerService)
0x3ebaf  stloc.0
0x3ebb0  ldarg.0
0x3ebb1  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ebb6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_FileSystem()
0x3ebbb  ldarg.0
0x3ebbc  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ebc1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IReparseAwareFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_ReparseAwareFileSystem()
0x3ebc6  ldarg.0
0x3ebc7  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ebcc  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_PolicyService()
0x3ebd1  ldarg.1
0x3ebd2  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext::get_Product()
0x3ebd7  castclass Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel
0x3ebdc  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.PropertyProviders.RepairTelemetryPropertyProvider::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IReparseAwareFileSystem reparseAwareFileSystem, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService policyService, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel product)
0x3ebe1  stloc.1
0x3ebe2  br       loc_3ED45
0x3ebe7  ldarg.0
0x3ebe8  ldloc.s  5
0x3ebea  ldarg.2
0x3ebeb  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::CreateProductModifier(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductModifierOptions options, class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerService installerService)
0x3ebf0  stloc.0
0x3ebf1  ldarg.0
0x3ebf2  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ebf7  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_FileSystem()
0x3ebfc  ldarg.0
0x3ebfd  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ec02  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IReparseAwareFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_ReparseAwareFileSystem()
0x3ec07  ldarg.0
0x3ec08  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ec0d  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_PolicyService()
0x3ec12  ldarg.1
0x3ec13  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext::get_Product()
0x3ec18  castclass Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel
0x3ec1d  ldloc.s  5
0x3ec1f  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.PropertyProviders.ModifyTelemetryPropertyProvider::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IReparseAwareFileSystem reparseAwareFileSystem, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService policyService, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel product, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductModifierOptions options)
0x3ec24  stloc.1
0x3ec25  br       loc_3ED45
0x3ec2a  ldarg.0
0x3ec2b  ldloc.s  6
0x3ec2d  ldarg.2
0x3ec2e  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::CreateProductUpdater(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions options, class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerService installerService)
0x3ec33  stloc.0
0x3ec34  ldarg.0
0x3ec35  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ec3a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_FileSystem()
0x3ec3f  ldarg.0
0x3ec40  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ec45  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IReparseAwareFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_ReparseAwareFileSystem()
0x3ec4a  ldarg.0
0x3ec4b  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ec50  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_PolicyService()
0x3ec55  ldarg.1
0x3ec56  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext::get_Product()
0x3ec5b  castclass Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel
0x3ec60  ldloc.s  6
0x3ec62  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.PropertyProviders.UpdateTelemetryPropertyProvider::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IReparseAwareFileSystem reparseAwareFileSystem, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService policyService, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel product, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions updateOptions)
0x3ec67  stloc.1
0x3ec68  br       loc_3ED45
0x3ec6d  ldarg.0
0x3ec6e  ldloc.s  7
0x3ec70  ldarg.2
0x3ec71  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::CreateProductUninstaller(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductUninstallerOptions options, class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerService installerService)
0x3ec76  stloc.0
0x3ec77  ldarg.0
0x3ec78  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ec7d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_FileSystem()
0x3ec82  ldarg.0
0x3ec83  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ec88  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IReparseAwareFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_ReparseAwareFileSystem()
0x3ec8d  ldarg.0
0x3ec8e  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ec93  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_PolicyService()
0x3ec98  ldarg.1
0x3ec99  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext::get_Product()
0x3ec9e  castclass Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel
0x3eca3  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.PropertyProviders.UninstallTelemetryPropertyProvider::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IReparseAwareFileSystem reparseAwareFileSystem, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService policyService, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel product)
0x3eca8  stloc.1
0x3eca9  br       loc_3ED45
0x3ecae  ldarg.0
0x3ecaf  ldloc.s  8
0x3ecb1  ldarg.2
0x3ecb2  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::CreateProductResumer(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductResumerOptions options, class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerService installerService)
0x3ecb7  stloc.0
0x3ecb8  ldarg.0
0x3ecb9  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ecbe  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_FileSystem()
0x3ecc3  ldarg.0
0x3ecc4  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ecc9  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IReparseAwareFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_ReparseAwareFileSystem()
0x3ecce  ldarg.0
0x3eccf  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ecd4  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_PolicyService()
0x3ecd9  ldarg.1
0x3ecda  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext::get_Product()
0x3ecdf  castclass Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel
0x3ece4  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.PropertyProviders.ResumeTelemetryPropertyProvider::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IReparseAwareFileSystem reparseAwareFileSystem, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService policyService, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel product)
0x3ece9  stloc.1
0x3ecea  br.s     loc_3ED45
0x3ecec  ldarg.1
0x3eced  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext::get_Product()
0x3ecf2  castclass Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel
0x3ecf7  stloc.2
0x3ecf8  ldarg.0
0x3ecf9  ldloc.s  9
0x3ecfb  ldarg.2
0x3ecfc  ldloc.2
0x3ecfd  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::CreateProductReverter(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductReverterOptions options, class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerService installerService, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel installedProduct)
0x3ed02  stloc.0
0x3ed03  ldarg.0
0x3ed04  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ed09  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_FileSystem()
0x3ed0e  ldarg.0
0x3ed0f  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ed14  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IReparseAwareFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_ReparseAwareFileSystem()
0x3ed19  ldarg.0
0x3ed1a  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ed1f  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_PolicyService()
0x3ed24  ldloc.2
0x3ed25  ldloc.s  9
0x3ed27  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.PropertyProviders.RollbackTelemetryPropertyProvider::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IReparseAwareFileSystem reparseAwareFileSystem, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService policyService, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel product, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductReverterOptions rollbackOptions)
0x3ed2c  stloc.1
0x3ed2d  br.s     loc_3ED45
0x3ed2f  ldstr    aTheProvidedOpe// "The provided operation context is not s"...
0x3ed34  ldarg.1
0x3ed35  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3ed3a  call     string [mscorlib]System.String::Format(string, object)
0x3ed3f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3ed44  throw
0x3ed45  ldarg.0
0x3ed46  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ed4b  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x3ed50  dup
0x3ed51  brtrue.s loc_3ED56
0x3ed53  pop
0x3ed54  br.s     loc_3ED74
0x3ed56  ldstr    aCreatedA0// "Created a {0}"
0x3ed5b  ldc.i4.1
0x3ed5c  newarr   [mscorlib]System.Object
0x3ed61  dup
0x3ed62  ldc.i4.0
0x3ed63  ldloc.0
0x3ed64  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3ed69  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3ed6e  stelem.ref
0x3ed6f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x3ed74  ldarg.0
0x3ed75  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3ed7a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x3ed7f  dup
0x3ed80  brtrue.s loc_3ED85
0x3ed82  pop
0x3ed83  br.s     loc_3EDAB
0x3ed85  ldstr    aDecorating0Wit// "Decorating {0} with {1}"
0x3ed8a  ldc.i4.2
0x3ed8b  newarr   [mscorlib]System.Object
0x3ed90  dup
0x3ed91  ldc.i4.0
0x3ed92  ldloc.0
0x3ed93  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3ed98  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3ed9d  stelem.ref
0x3ed9e  dup
0x3ed9f  ldc.i4.1
0x3eda0  ldstr    aUnelevatedinst// "UnelevatedInstallerTelemetryDecorator"
0x3eda5  stelem.ref
0x3eda6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x3edab  ldarg.0
0x3edac  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3edb1  ldloc.1
0x3edb2  ldloc.0
0x3edb3  ldarg.1
0x3edb4  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext::get_Product()
0x3edb9  ldarg.1
0x3edba  callvirt instance class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext::get_InstallerTelemetryContext()
0x3edbf  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.UnelevatedInstallerTelemetryDecorator::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.PropertyProviders.IInstallerTelemetryPropertyProvider propertyProvider, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller installer, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel product, class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext telemetryContext)
0x3edc4  ret
```
