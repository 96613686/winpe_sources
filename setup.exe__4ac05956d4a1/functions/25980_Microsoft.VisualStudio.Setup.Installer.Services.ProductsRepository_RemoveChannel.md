# Microsoft.VisualStudio.Setup.Installer.Services.ProductsRepository::RemoveChannel

- ea: `0x25980`
- end: `0x259e5`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.ProductsRepository::RemoveChannel`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0xa930`
- `0x22860`
- `0x25980`
- `0x25a90`
- `0x2d030`
- `0x2d040`
- `0x36450`

## string_xrefs

- `0x25996`: `Cannot remove a channel with installed products`

## pseudocode

```c

```

## disassembly

```asm
0x25980  ldarg.0
0x25981  ldarg.1
0x25982  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation Microsoft.VisualStudio.Setup.Installer.Services.ProductsRepository::CreateRemoveChannelOperation(class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel)
0x25987  stloc.0
0x25988  ldarg.0
0x25989  ldarg.1
0x2598a  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel> Microsoft.VisualStudio.Setup.Installer.Extensions::GetExistingProductSummaries(class Microsoft.VisualStudio.Setup.Installer.Services.IProductsProviderService productsProvider, class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel channel)
0x2598f  call     T0x2B0000AB
0x25994  brfalse.s loc_259A1
0x25996  ldstr    aCannotRemoveAC// "Cannot remove a channel with installed "...
0x2599b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x259a0  throw
0x259a1  ldarg.0
0x259a2  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductsRepositoryServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ProductsRepository::serviceOptions
0x259a7  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductsRepositoryServiceOptions::get_ChannelManager()
0x259ac  ldarg.1
0x259ad  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Models.IChannelModelSummary::get_UpdateUri()
0x259b2  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager::Remove(class [System]System.Uri)
0x259b7  ldarg.0
0x259b8  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductsRepositoryServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ProductsRepository::serviceOptions
0x259bd  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IRemoteChannelManager Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductsRepositoryServiceOptions::get_RemoteChannelManager()
0x259c2  ldarg.1
0x259c3  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Models.IChannelModelSummary::get_UpdateUri()
0x259c8  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.IRemoteChannelManager::Remove(class [System]System.Uri channelUri)
0x259cd  ldarg.0
0x259ce  ldfld    class ProductCollection`2<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel> Microsoft.VisualStudio.Setup.Installer.Services.ProductsRepository::availableProducts
0x259d3  callvirt instance void class ProductCollection`2<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel>::RefreshProducts()
0x259d8  leave.s  loc_259E4
0x259da  ldloc.0
0x259db  brfalse.s loc_259E3
0x259dd  ldloc.0
0x259de  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x259e3  endfinally
0x259e4  ret
```
