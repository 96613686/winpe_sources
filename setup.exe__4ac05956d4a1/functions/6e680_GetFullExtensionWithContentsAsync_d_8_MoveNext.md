# <GetFullExtensionWithContentsAsync>d__8::MoveNext

- ea: `0x6e680`
- end: `0x6efc4`
- name: `<GetFullExtensionWithContentsAsync>d__8::MoveNext`
- size: `2372`
- prototype: ``
- caller_count: `0`
- callee_count: `38`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x9310`
- `0x9cc0`
- `0x20390`
- `0x205f0`
- `0x20820`
- `0x20900`
- `0x209b0`
- `0x20a10`
- `0x20d30`
- `0x21730`
- `0x21750`
- `0x22900`
- `0x22960`
- `0x26930`
- `0x2bcb0`
- `0x2bcc0`
- `0x2bcd0`
- `0x2c070`
- `0x36440`
- `0x36e80`
- `0x37a10`
- `0x38ee0`
- `0x3a810`
- `0x3b530`
- `0x3b590`
- `0x3b5a0`
- `0x3b610`
- `0x3b630`
- `0x3bb00`
- `0x6c7f0`
- `0x6c830`
- `0x6c850`
- `0x6c870`
- `0x6c890`
- `0x6cbf0`
- `0x6d180`
- `0x6d1f0`
- `0x6e680`

## string_xrefs

- `0x6e7e6`: `Cannot add extensions to a product that doesn't support extensions.`
- `0x6e790`: `Creating a full extension model for `
- `0x6e8ad`: `Failed to download the extension from the given input.`
- `0x6e933`: `Failed to resolve extension dependencies.`
- `0x6ea2a`: `EmbeddedExtensionError`
- `0x6ea90`: `Failed to add new extension to the graph: Graph Construction Error`
- `0x6ed2d`: `Failed to add new extension to the graph: The extension already exists in the graph. Instead, selected the extension component that is already in the graph to proceed.`
- `0x6eda5`: `The provided extension does not have a proper Component authoring.`
- `0x6ee24`: `The provided extension was not added to graph.`
- `0x6eec8`: `The full model couldn't be created from the package reader.`
- `0x6eefe`: `Successfully created a full extension model.`

## pseudocode

```c

```

## disassembly

```asm
0x6e680  ldarg.0
0x6e681  ldfld    int32 <GetFullExtensionWithContentsAsync>d__8::<>1__state
0x6e686  stloc.0
0x6e687  ldarg.0
0x6e688  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager <GetFullExtensionWithContentsAsync>d__8::<>4__this
0x6e68d  stloc.1
0x6e68e  ldloc.0
0x6e68f  ldc.i4.2
0x6e690  ble.un   loc_6E76C
0x6e695  ldarg.0
0x6e696  newobj   instance void <>c__DisplayClass8_0::.ctor()
0x6e69b  stfld    class <>c__DisplayClass8_0 <GetFullExtensionWithContentsAsync>d__8::<>8__1
0x6e6a0  ldarg.0
0x6e6a1  ldfld    class <>c__DisplayClass8_0 <GetFullExtensionWithContentsAsync>d__8::<>8__1
0x6e6a6  ldarg.0
0x6e6a7  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <GetFullExtensionWithContentsAsync>d__8::product
0x6e6ac  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <>c__DisplayClass8_0::product
0x6e6b1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x6e6b6  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ProductIdProperty
0x6e6bb  stloc.s  5
0x6e6bd  dup
0x6e6be  ldloc.s  5
0x6e6c0  ldarg.0
0x6e6c1  ldfld    class <>c__DisplayClass8_0 <GetFullExtensionWithContentsAsync>d__8::<>8__1
0x6e6c6  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <>c__DisplayClass8_0::product
0x6e6cb  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Id()
0x6e6d0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6e6d5  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ChannelIdProperty
0x6e6da  stloc.s  6
0x6e6dc  dup
0x6e6dd  ldloc.s  6
0x6e6df  ldarg.0
0x6e6e0  ldfld    class <>c__DisplayClass8_0 <GetFullExtensionWithContentsAsync>d__8::<>8__1
0x6e6e5  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <>c__DisplayClass8_0::product
0x6e6ea  isinst   Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel
0x6e6ef  stloc.s  4
0x6e6f1  ldloc.s  4
0x6e6f3  brtrue.s loc_6E70C
0x6e6f5  ldarg.0
0x6e6f6  ldfld    class <>c__DisplayClass8_0 <GetFullExtensionWithContentsAsync>d__8::<>8__1
0x6e6fb  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <>c__DisplayClass8_0::product
0x6e700  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Channel()
0x6e705  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.IChannelModelSummary::get_Id()
0x6e70a  br.s     loc_6E718
0x6e70c  ldloc.s  4
0x6e70e  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModelSummary Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_InstalledChannel()
0x6e713  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.IChannelModelSummary::get_Id()
0x6e718  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6e71d  ldsfld   string Extensions::SupportsExtensionsProperty
0x6e722  stloc.s  7
0x6e724  dup
0x6e725  ldloc.s  7
0x6e727  ldarg.0
0x6e728  ldfld    class <>c__DisplayClass8_0 <GetFullExtensionWithContentsAsync>d__8::<>8__1
0x6e72d  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <>c__DisplayClass8_0::product
0x6e732  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.ProductFeatures Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel::get_ProductFeatures()
0x6e737  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.Products.ProductFeatures::get_SupportsExtensions()
0x6e73c  box      [mscorlib]System.Boolean
0x6e741  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6e746  stloc.3
0x6e747  ldarg.0
0x6e748  ldloc.1
0x6e749  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x6e74e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Telemetry()
0x6e753  dup
0x6e754  brtrue.s loc_6E75A
0x6e756  pop
0x6e757  ldnull
0x6e758  br.s     loc_6E767
0x6e75a  ldsfld   string Extensions::GetFullExtensionEvent
0x6e75f  ldloc.3
0x6e760  ldc.i4.0
0x6e761  ldc.i4.0
0x6e762  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x6e767  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <GetFullExtensionWithContentsAsync>d__8::<telemetryOperation>5__2
0x6e76c  nop
0x6e76d  ldloc.0
0x6e76e  switch   loc_6E877, loc_6E9C6, loc_6EB43
0x6e77f  ldloc.1
0x6e780  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x6e785  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Logger()
0x6e78a  dup
0x6e78b  brtrue.s loc_6E790
0x6e78d  pop
0x6e78e  br.s     loc_6E7B4
0x6e790  ldstr    aCreatingAFullE// "Creating a full extension model for "
0x6e795  ldarg.0
0x6e796  ldfld    class [System]System.Uri <GetFullExtensionWithContentsAsync>d__8::extensionUri
0x6e79b  callvirt instance string [System]System.Uri::get_OriginalString()
0x6e7a0  ldstr    asc_9EBEA// "."
0x6e7a5  call     string [mscorlib]System.String::Concat(string, string, string)
0x6e7aa  call     T0x2B000010
0x6e7af  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x6e7b4  ldarg.0
0x6e7b5  ldfld    class <>c__DisplayClass8_0 <GetFullExtensionWithContentsAsync>d__8::<>8__1
0x6e7ba  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <>c__DisplayClass8_0::product
0x6e7bf  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.ProductFeatures Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel::get_ProductFeatures()
0x6e7c4  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.Products.ProductFeatures::get_SupportsExtensions()
0x6e7c9  brtrue.s loc_6E812
0x6e7cb  ldarg.0
0x6e7cc  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <GetFullExtensionWithContentsAsync>d__8::<telemetryOperation>5__2
0x6e7d1  dup
0x6e7d2  brtrue.s loc_6E7D7
0x6e7d4  pop
0x6e7d5  br.s     loc_6E7E6
0x6e7d7  ldsfld   string Extensions::ResultProperty
0x6e7dc  ldstr    aBlock// "Block"
0x6e7e1  call     void Microsoft.VisualStudio.Setup.Installer.CommonExtensions::SetProperty(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, string key, object value)
0x6e7e6  ldstr    aCannotAddExten// "Cannot add extensions to a product that"...
0x6e7eb  stloc.s  0x12
0x6e7ed  ldloc.1
0x6e7ee  ldarg.0
0x6e7ef  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <GetFullExtensionWithContentsAsync>d__8::<telemetryOperation>5__2
0x6e7f4  ldarg.0
0x6e7f5  ldfld    class [System]System.Uri <GetFullExtensionWithContentsAsync>d__8::extensionUri
0x6e7fa  ldc.i4.4
0x6e7fb  ldloc.s  0x12
0x6e7fd  call     instance class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::RecordFullModelCreationFailureAndReturn(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, class [System]System.Uri extensionUri, valuetype Microsoft.VisualStudio.Setup.Installer.ExtensionModelErrorState errorState, [opt] string additionalMessage)
0x6e802  stloc.s  0x13
0x6e804  ldnull
0x6e805  ldloc.s  0x13
0x6e807  newobj   instance void ExtensionModelContentSummary::.ctor(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents ExtensionContents, class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary ExtensionModelSummary)
0x6e80c  stloc.2
0x6e80d  leave    loc_6EFA8
0x6e812  ldloc.1
0x6e813  ldarg.0
0x6e814  ldfld    class [System]System.Uri <GetFullExtensionWithContentsAsync>d__8::extensionUri
0x6e819  ldarg.0
0x6e81a  ldfld    class <>c__DisplayClass8_0 <GetFullExtensionWithContentsAsync>d__8::<>8__1
0x6e81f  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <>c__DisplayClass8_0::product
0x6e824  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.VersionBundle Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel::get_Versions()
0x6e829  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Installer.Models.VersionBundle::get_BuildVersion()
0x6e82e  ldarg.0
0x6e82f  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <GetFullExtensionWithContentsAsync>d__8::token
0x6e834  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class ExtensionContentsSummary> Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::DownloadExtensionAsync(class [System]System.Uri, class [mscorlib]System.Version extensionUri, valuetype [mscorlib]System.Threading.CancellationToken productVersion)
0x6e839  ldc.i4.0
0x6e83a  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class ExtensionContentsSummary>::ConfigureAwait(!!T0)
0x6e83f  stloc.s  0x16
0x6e841  ldloca.s 0x16
0x6e843  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class ExtensionContentsSummary>::GetAwaiter()
0x6e848  stloc.s  0x15
0x6e84a  ldloca.s 0x15
0x6e84c  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class ExtensionContentsSummary>::get_IsCompleted()
0x6e851  brtrue.s loc_6E894
0x6e853  ldarg.0
0x6e854  ldc.i4.0
0x6e855  dup
0x6e856  stloc.0
0x6e857  stfld    int32 <GetFullExtensionWithContentsAsync>d__8::<>1__state
0x6e85c  ldarg.0
0x6e85d  ldloc.s  0x15
0x6e85f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class ExtensionContentsSummary> <GetFullExtensionWithContentsAsync>d__8::<>u__1
0x6e864  ldarg.0
0x6e865  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class ExtensionModelContentSummary> <GetFullExtensionWithContentsAsync>d__8::<>t__builder
0x6e86a  ldloca.s 0x15
0x6e86c  ldarg.0
0x6e86d  call     T0x2B00046E
0x6e872  leave    loc_6EFC3
0x6e877  ldarg.0
0x6e878  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class ExtensionContentsSummary> <GetFullExtensionWithContentsAsync>d__8::<>u__1
0x6e87d  stloc.s  0x15
0x6e87f  ldarg.0
0x6e880  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class ExtensionContentsSummary> <GetFullExtensionWithContentsAsync>d__8::<>u__1
0x6e885  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class ExtensionContentsSummary>
0x6e88b  ldarg.0
0x6e88c  ldc.i4.m1
0x6e88d  dup
0x6e88e  stloc.0
0x6e88f  stfld    int32 <GetFullExtensionWithContentsAsync>d__8::<>1__state
0x6e894  ldloca.s 0x15
0x6e896  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class ExtensionContentsSummary>::GetResult()
0x6e89b  stloc.s  0x14
0x6e89d  ldarg.0
0x6e89e  ldloc.s  0x14
0x6e8a0  stfld    class ExtensionContentsSummary <GetFullExtensionWithContentsAsync>d__8::<extensionContentsSummary>5__3
0x6e8a5  ldarg.0
0x6e8a6  ldfld    class ExtensionContentsSummary <GetFullExtensionWithContentsAsync>d__8::<extensionContentsSummary>5__3
0x6e8ab  brtrue.s loc_6E8D9
0x6e8ad  ldstr    aFailedToDownlo_4// "Failed to download the extension from t"...
0x6e8b2  stloc.s  0x17
0x6e8b4  ldloc.1
0x6e8b5  ldarg.0
0x6e8b6  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <GetFullExtensionWithContentsAsync>d__8::<telemetryOperation>5__2
0x6e8bb  ldarg.0
0x6e8bc  ldfld    class [System]System.Uri <GetFullExtensionWithContentsAsync>d__8::extensionUri
0x6e8c1  ldc.i4.4
0x6e8c2  ldloc.s  0x17
0x6e8c4  call     instance class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::RecordFullModelCreationFailureAndReturn(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, class [System]System.Uri extensionUri, valuetype Microsoft.VisualStudio.Setup.Installer.ExtensionModelErrorState errorState, [opt] string additionalMessage)
0x6e8c9  stloc.s  0x18
0x6e8cb  ldnull
0x6e8cc  ldloc.s  0x18
0x6e8ce  newobj   instance void ExtensionModelContentSummary::.ctor(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents ExtensionContents, class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary ExtensionModelSummary)
0x6e8d3  stloc.2
0x6e8d4  leave    loc_6EFA8
0x6e8d9  ldloc.1
0x6e8da  ldarg.0
0x6e8db  ldfld    class [System]System.Uri <GetFullExtensionWithContentsAsync>d__8::extensionUri
0x6e8e0  ldarg.0
0x6e8e1  ldfld    class ExtensionContentsSummary <GetFullExtensionWithContentsAsync>d__8::<extensionContentsSummary>5__3
0x6e8e6  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents ExtensionContentsSummary::get_ExtensionContents()
0x6e8eb  ldarg.0
0x6e8ec  ldfld    class <>c__DisplayClass8_0 <GetFullExtensionWithContentsAsync>d__8::<>8__1
0x6e8f1  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <>c__DisplayClass8_0::product
0x6e8f6  ldarg.0
0x6e8f7  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <GetFullExtensionWithContentsAsync>d__8::<telemetryOperation>5__2
0x6e8fc  call     instance class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::ValidateSupportAndReturnErrorModel(class [System]System.Uri, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents extensionUri, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel extensionContents, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation product)
0x6e901  stloc.s  8
0x6e903  ldloc.s  8
0x6e905  brfalse.s loc_6E91F
0x6e907  ldarg.0
0x6e908  ldfld    class ExtensionContentsSummary <GetFullExtensionWithContentsAsync>d__8::<extensionContentsSummary>5__3
0x6e90d  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents ExtensionContentsSummary::get_ExtensionContents()
0x6e912  ldloc.s  8
0x6e914  newobj   instance void ExtensionModelContentSummary::.ctor(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents ExtensionContents, class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary ExtensionModelSummary)
0x6e919  stloc.2
0x6e91a  leave    loc_6EFA8
0x6e91f  ldloc.1
0x6e920  ldarg.0
0x6e921  ldfld    class ExtensionContentsSummary <GetFullExtensionWithContentsAsync>d__8::<extensionContentsSummary>5__3
0x6e926  ldarg.0
0x6e927  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <GetFullExtensionWithContentsAsync>d__8::<telemetryOperation>5__2
0x6e92c  call     instance bool Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::ValidateExtensionDependencies(class ExtensionContentsSummary extensionContentsSummary, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation)
0x6e931  brtrue.s loc_6E969
0x6e933  ldstr    aFailedToResolv// "Failed to resolve extension dependencie"...
0x6e938  stloc.s  0x19
0x6e93a  ldloc.1
0x6e93b  ldarg.0
0x6e93c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <GetFullExtensionWithContentsAsync>d__8::<telemetryOperation>5__2
0x6e941  ldarg.0
0x6e942  ldfld    class [System]System.Uri <GetFullExtensionWithContentsAsync>d__8::extensionUri
0x6e947  ldc.i4.3
0x6e948  ldloc.s  0x19
0x6e94a  call     instance class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::RecordFullModelCreationFailureAndReturn(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, class [System]System.Uri extensionUri, valuetype Microsoft.VisualStudio.Setup.Installer.ExtensionModelErrorState errorState, [opt] string additionalMessage)
0x6e94f  stloc.s  0x1A
0x6e951  ldarg.0
0x6e952  ldfld    class ExtensionContentsSummary <GetFullExtensionWithContentsAsync>d__8::<extensionContentsSummary>5__3
0x6e957  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents ExtensionContentsSummary::get_ExtensionContents()
0x6e95c  ldloc.s  0x1A
0x6e95e  newobj   instance void ExtensionModelContentSummary::.ctor(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents ExtensionContents, class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary ExtensionModelSummary)
0x6e963  stloc.2
0x6e964  leave    loc_6EFA8
0x6e969  ldloc.1
0x6e96a  ldarg.0
0x6e96b  ldfld    class ExtensionContentsSummary <GetFullExtensionWithContentsAsync>d__8::<extensionContentsSummary>5__3
0x6e970  ldarg.0
0x6e971  ldfld    class <>c__DisplayClass8_0 <GetFullExtensionWithContentsAsync>d__8::<>8__1
0x6e976  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <>c__DisplayClass8_0::product
0x6e97b  ldarg.0
0x6e97c  ldfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionOrigin <GetFullExtensionWithContentsAsync>d__8::origin
0x6e981  ldarg.0
0x6e982  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <GetFullExtensionWithContentsAsync>d__8::token
0x6e987  ldarg.0
0x6e988  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <GetFullExtensionWithContentsAsync>d__8::<telemetryOperation>5__2
0x6e98d  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::ExpandExtensionPackAsync(class ExtensionContentsSummary extensionContentsSummary, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel product, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionOrigin origin, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation)
0x6e992  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::GetAwaiter()
0x6e997  stloc.s  0x1C
0x6e999  ldloca.s 0x1C
0x6e99b  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::get_IsCompleted()
0x6e9a0  brtrue.s loc_6E9E3
0x6e9a2  ldarg.0
0x6e9a3  ldc.i4.1
0x6e9a4  dup
0x6e9a5  stloc.0
0x6e9a6  stfld    int32 <GetFullExtensionWithContentsAsync>d__8::<>1__state
0x6e9ab  ldarg.0
0x6e9ac  ldloc.s  0x1C
0x6e9ae  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <GetFullExtensionWithContentsAsync>d__8::<>u__2
0x6e9b3  ldarg.0
0x6e9b4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class ExtensionModelContentSummary> <GetFullExtensionWithContentsAsync>d__8::<>t__builder
0x6e9b9  ldloca.s 0x1C
0x6e9bb  ldarg.0
0x6e9bc  call     T0x2B00046F
0x6e9c1  leave    loc_6EFC3
0x6e9c6  ldarg.0
0x6e9c7  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <GetFullExtensionWithContentsAsync>d__8::<>u__2
0x6e9cc  stloc.s  0x1C
0x6e9ce  ldarg.0
0x6e9cf  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <GetFullExtensionWithContentsAsync>d__8::<>u__2
0x6e9d4  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>
0x6e9da  ldarg.0
0x6e9db  ldc.i4.m1
0x6e9dc  dup
0x6e9dd  stloc.0
0x6e9de  stfld    int32 <GetFullExtensionWithContentsAsync>d__8::<>1__state
0x6e9e3  ldloca.s 0x1C
0x6e9e5  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::GetResult()
0x6e9ea  stloc.s  0x1B
0x6e9ec  ldarg.0
0x6e9ed  ldloc.s  0x1B
0x6e9ef  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <GetFullExtensionWithContentsAsync>d__8::<packedExtensions>5__4
0x6e9f4  ldloc.1
0x6e9f5  ldarg.0
0x6e9f6  ldfld    class ExtensionContentsSummary <GetFullExtensionWithContentsAsync>d__8::<extensionContentsSummary>5__3
0x6e9fb  ldarg.0
0x6e9fc  ldfld    class <>c__DisplayClass8_0 <GetFullExtensionWithContentsAsync>d__8::<>8__1
0x6ea01  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <>c__DisplayClass8_0::product
0x6ea06  ldarg.0
0x6ea07  ldfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionOrigin <GetFullExtensionWithContentsAsync>d__8::origin
0x6ea0c  ldarg.0
0x6ea0d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <GetFullExtensionWithContentsAsync>d__8::<telemetryOperation>5__2
  ... truncated ...
```
