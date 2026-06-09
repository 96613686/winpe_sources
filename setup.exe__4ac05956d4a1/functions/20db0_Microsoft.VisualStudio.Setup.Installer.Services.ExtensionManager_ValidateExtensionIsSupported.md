# Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::ValidateExtensionIsSupported

- ea: `0x20db0`
- end: `0x20e2a`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::ValidateExtensionIsSupported`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x20d30`

## callees

- `0x20db0`
- `0x2bcb0`
- `0x2c060`
- `0x36450`
- `0x36e80`
- `0x3b530`
- `0x3b590`
- `0x3b5a0`
- `0x3b5b0`

## string_xrefs

- `0x20deb`: `Product with ID {0} and channel {1} does not support the extension at {2}`

## pseudocode

```c

```

## disassembly

```asm
0x20db0  ldarg.0
0x20db1  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x20db6  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.IExtensionServiceInternal Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions::get_ExtensionService()
0x20dbb  ldarg.2
0x20dbc  ldarg.3
0x20dbd  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Id()
0x20dc2  ldarg.3
0x20dc3  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.VersionBundle Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel::get_Versions()
0x20dc8  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Installer.Models.VersionBundle::get_BuildVersion()
0x20dcd  ldarg.3
0x20dce  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_ProductArch()
0x20dd3  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.IExtensionService::ProductSupportsExtension(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents, string, class [mscorlib]System.Version, string)
0x20dd8  brtrue.s loc_20E18
0x20dda  ldarg.0
0x20ddb  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x20de0  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Logger()
0x20de5  dup
0x20de6  brtrue.s loc_20DEB
0x20de8  pop
0x20de9  br.s     loc_20E16
0x20deb  ldstr    aProductWithId0// "Product with ID {0} and channel {1} doe"...
0x20df0  ldc.i4.3
0x20df1  newarr   [mscorlib]System.Object
0x20df6  dup
0x20df7  ldc.i4.0
0x20df8  ldarg.3
0x20df9  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Id()
0x20dfe  stelem.ref
0x20dff  dup
0x20e00  ldc.i4.1
0x20e01  ldarg.3
0x20e02  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Channel()
0x20e07  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Models.IChannelModelSummary::get_UpdateUri()
0x20e0c  stelem.ref
0x20e0d  dup
0x20e0e  ldc.i4.2
0x20e0f  ldarg.1
0x20e10  stelem.ref
0x20e11  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x20e16  ldc.i4.2
0x20e17  ret
0x20e18  ldarg.0
0x20e19  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x20e1e  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.IExtensionServiceInternal Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions::get_ExtensionService()
0x20e23  ldarg.2
0x20e24  callvirt instance valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.SupportedExtensionResult [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.IExtensionService::IsSupportedExtension(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents)
0x20e29  ret
```
