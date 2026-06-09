# Microsoft.VisualStudio.Setup.Installer.Utilities.CommandLineUtilities::GetInstalledProductSummary

- ea: `0x3cbe0`
- end: `0x3cc5e`
- name: `Microsoft.VisualStudio.Setup.Installer.Utilities.CommandLineUtilities::GetInstalledProductSummary`
- size: `126`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x19ea0`
- `0x4c9d0`
- `0x5a590`
- `0x5a5f0`
- `0x698d0`

## callees

- `0x22690`
- `0x226a0`
- `0x3cbe0`
- `0x3ccb0`
- `0x59620`
- `0x59640`
- `0x59660`
- `0x596a0`
- `0x596c0`

## string_xrefs

- `0x3cc2a`: `No instance matching the command line parameters`
- `0x3cc52`: `No instance matching the command line parameters`

## pseudocode

```c

```

## disassembly

```asm
0x3cbe0  ldarg.0
0x3cbe1  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_InstallPath()
0x3cbe6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3cbeb  brtrue.s loc_3CBFA
0x3cbed  ldarg.0
0x3cbee  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_InstallPath()
0x3cbf3  ldarg.1
0x3cbf4  call     class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel Microsoft.VisualStudio.Setup.Installer.Utilities.CommandLineUtilities::GetInstalledProductSummary(string installPath, class Microsoft.VisualStudio.Setup.Installer.Services.IProductsRepository productsRepository)
0x3cbf9  ret
0x3cbfa  ldarg.0
0x3cbfb  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_ChannelUri()
0x3cc00  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3cc05  brtrue.s loc_3CC36
0x3cc07  ldarg.0
0x3cc08  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_ChannelUri()
0x3cc0d  newobj   instance void [System]System.Uri::.ctor(string)
0x3cc12  stloc.0
0x3cc13  ldarg.1
0x3cc14  ldarg.0
0x3cc15  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_ProductId()
0x3cc1a  ldloc.0
0x3cc1b  ldarg.0
0x3cc1c  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_ProductArch()
0x3cc21  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel Microsoft.VisualStudio.Setup.Installer.Services.IProductsProviderService::GetInstalledProductSummary(string, class [System]System.Uri productId, string channelUri)
0x3cc26  dup
0x3cc27  brtrue.s loc_3CC35
0x3cc29  pop
0x3cc2a  ldstr    aNoInstanceMatc// "No instance matching the command line p"...
0x3cc2f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3cc34  throw
0x3cc35  ret
0x3cc36  ldarg.1
0x3cc37  ldarg.0
0x3cc38  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_ProductId()
0x3cc3d  ldarg.0
0x3cc3e  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_ChannelId()
0x3cc43  ldarg.0
0x3cc44  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions::get_ProductArch()
0x3cc49  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel Microsoft.VisualStudio.Setup.Installer.Services.IProductsProviderService::GetInstalledProductSummary(string, string productId, string channelId)
0x3cc4e  dup
0x3cc4f  brtrue.s loc_3CC5D
0x3cc51  pop
0x3cc52  ldstr    aNoInstanceMatc// "No instance matching the command line p"...
0x3cc57  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3cc5c  throw
0x3cc5d  ret
```
