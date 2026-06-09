# Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.UpdateCommandLineHandler::TryGetInstalledProduct

- ea: `0x5baa0`
- end: `0x5bc02`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.UpdateCommandLineHandler::TryGetInstalledProduct`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x8e6d0`

## callees

- `0x22670`
- `0x22690`
- `0x226a0`
- `0x2bb30`
- `0x2bb50`
- `0x59320`
- `0x59360`
- `0x59380`
- `0x5a340`
- `0x5a440`
- `0x5baa0`

## string_xrefs

- `0x5bb57`: `Failed to find product with channelUri '{0}' and productId '{1}'`

## pseudocode

```c

```

## disassembly

```asm
0x5baa0  ldarg.2
0x5baa1  ldnull
0x5baa2  stind.ref
0x5baa3  ldarg.1
0x5baa4  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions::get_InstallPath()
0x5baa9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5baae  brtrue.s loc_5BB00
0x5bab0  ldarg.2
0x5bab1  ldarg.0
0x5bab2  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.UpdateCommandLineHandler::serviceOptions
0x5bab7  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IProductsRepository Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_ProductsRepository()
0x5babc  ldarg.1
0x5babd  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions::get_InstallPath()
0x5bac2  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel Microsoft.VisualStudio.Setup.Installer.Services.IProductsProviderService::GetInstalledProductSummary(string)
0x5bac7  stind.ref
0x5bac8  leave.s  loc_5BAF7
0x5baca  pop
0x5bacb  ldarg.0
0x5bacc  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.UpdateCommandLineHandler::serviceOptions
0x5bad1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_Logger()
0x5bad6  dup
0x5bad7  brtrue.s loc_5BADC
0x5bad9  pop
0x5bada  br.s     loc_5BAF5
0x5badc  ldstr    aFailedToFindPr_0// "Failed to find product at '{0}'"
0x5bae1  ldc.i4.1
0x5bae2  newarr   [mscorlib]System.Object
0x5bae7  dup
0x5bae8  ldc.i4.0
0x5bae9  ldarg.1
0x5baea  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions::get_InstallPath()
0x5baef  stelem.ref
0x5baf0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5baf5  leave.s  loc_5BAF7
0x5baf7  ldarg.2
0x5baf8  ldind.ref
0x5baf9  ldnull
0x5bafa  ceq
0x5bafc  ldc.i4.0
0x5bafd  ceq
0x5baff  ret
0x5bb00  ldarg.1
0x5bb01  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ChannelUri()
0x5bb06  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5bb0b  brtrue.s loc_5BB81
0x5bb0d  ldarg.1
0x5bb0e  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ProductId()
0x5bb13  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5bb18  brtrue.s loc_5BB81
0x5bb1a  ldarg.2
0x5bb1b  ldarg.0
0x5bb1c  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.UpdateCommandLineHandler::serviceOptions
0x5bb21  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IProductsRepository Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_ProductsRepository()
0x5bb26  ldarg.1
0x5bb27  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ProductId()
0x5bb2c  ldarg.1
0x5bb2d  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ChannelUri()
0x5bb32  newobj   instance void [System]System.Uri::.ctor(string)
0x5bb37  ldarg.1
0x5bb38  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions::get_ProductArch()
0x5bb3d  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel Microsoft.VisualStudio.Setup.Installer.Services.IProductsProviderService::GetInstalledProductSummary(string, class [System]System.Uri productId, string channelUri)
0x5bb42  stind.ref
0x5bb43  leave.s  loc_5BB7B
0x5bb45  pop
0x5bb46  ldarg.0
0x5bb47  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.UpdateCommandLineHandler::serviceOptions
0x5bb4c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_Logger()
0x5bb51  dup
0x5bb52  brtrue.s loc_5BB57
0x5bb54  pop
0x5bb55  br.s     loc_5BB79
0x5bb57  ldstr    aFailedToFindPr// "Failed to find product with channelUri "...
0x5bb5c  ldc.i4.2
0x5bb5d  newarr   [mscorlib]System.Object
0x5bb62  dup
0x5bb63  ldc.i4.0
0x5bb64  ldarg.1
0x5bb65  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ChannelUri()
0x5bb6a  stelem.ref
0x5bb6b  dup
0x5bb6c  ldc.i4.1
0x5bb6d  ldarg.1
0x5bb6e  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ProductId()
0x5bb73  stelem.ref
0x5bb74  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5bb79  leave.s  loc_5BB7B
0x5bb7b  ldarg.2
0x5bb7c  ldind.ref
0x5bb7d  brfalse.s loc_5BB81
0x5bb7f  ldc.i4.1
0x5bb80  ret
0x5bb81  ldarg.1
0x5bb82  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ProductId()
0x5bb87  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5bb8c  brtrue.s loc_5BC00
0x5bb8e  ldarg.1
0x5bb8f  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ChannelId()
0x5bb94  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5bb99  brtrue.s loc_5BC00
0x5bb9b  ldarg.2
0x5bb9c  ldarg.0
0x5bb9d  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.UpdateCommandLineHandler::serviceOptions
0x5bba2  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IProductsRepository Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_ProductsRepository()
0x5bba7  ldarg.1
0x5bba8  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ProductId()
0x5bbad  ldarg.1
0x5bbae  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ChannelId()
0x5bbb3  ldarg.1
0x5bbb4  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions::get_ProductArch()
0x5bbb9  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel Microsoft.VisualStudio.Setup.Installer.Services.IProductsProviderService::GetInstalledProductSummary(string, string productId, string channelId)
0x5bbbe  stind.ref
0x5bbbf  leave.s  loc_5BBF7
0x5bbc1  pop
0x5bbc2  ldarg.0
0x5bbc3  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.UpdateCommandLineHandler::serviceOptions
0x5bbc8  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_Logger()
0x5bbcd  dup
0x5bbce  brtrue.s loc_5BBD3
0x5bbd0  pop
0x5bbd1  br.s     loc_5BBF5
0x5bbd3  ldstr    aFailedToFindPr_1// "Failed to find product with channelId '"...
0x5bbd8  ldc.i4.2
0x5bbd9  newarr   [mscorlib]System.Object
0x5bbde  dup
0x5bbdf  ldc.i4.0
0x5bbe0  ldarg.1
0x5bbe1  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ChannelId()
0x5bbe6  stelem.ref
0x5bbe7  dup
0x5bbe8  ldc.i4.1
0x5bbe9  ldarg.1
0x5bbea  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_ProductId()
0x5bbef  stelem.ref
0x5bbf0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5bbf5  leave.s  loc_5BBF7
0x5bbf7  ldarg.2
0x5bbf8  ldind.ref
0x5bbf9  ldnull
0x5bbfa  ceq
0x5bbfc  ldc.i4.0
0x5bbfd  ceq
0x5bbff  ret
0x5bc00  ldc.i4.0
0x5bc01  ret
```
