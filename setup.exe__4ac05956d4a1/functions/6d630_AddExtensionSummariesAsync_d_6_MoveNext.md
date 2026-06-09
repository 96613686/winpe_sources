# <AddExtensionSummariesAsync>d__6::MoveNext

- ea: `0x6d630`
- end: `0x6d961`
- name: `<AddExtensionSummariesAsync>d__6::MoveNext`
- size: `817`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x9310`
- `0x20e30`
- `0x20e80`
- `0x2bcb0`
- `0x2bcc0`
- `0x36440`
- `0x3a810`
- `0x3b590`
- `0x3b5a0`
- `0x3b630`
- `0x3bb00`
- `0x6d630`

## string_xrefs

- `0x6d788`: `Product does not support extensions.`
- `0x6d7be`: `Cannot add extensions to a product that doesn't support extensions.`
- `0x6d8d1`: `Successfully added {0} extension summary(s) to the product.`

## pseudocode

```c

```

## disassembly

```asm
0x6d630  ldarg.0
0x6d631  ldfld    int32 <AddExtensionSummariesAsync>d__6::<>1__state
0x6d636  stloc.0
0x6d637  ldarg.0
0x6d638  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager <AddExtensionSummariesAsync>d__6::<>4__this
0x6d63d  stloc.1
0x6d63e  ldloc.0
0x6d63f  ldc.i4.1
0x6d640  ble.un   loc_6D75C
0x6d645  ldarg.0
0x6d646  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionRecords <AddExtensionSummariesAsync>d__6::extensions
0x6d64b  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionOrigin> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionRecords::get_Uris()
0x6d650  call     T0x2B000461
0x6d655  brtrue.s loc_6D674
0x6d657  ldarg.0
0x6d658  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionRecords <AddExtensionSummariesAsync>d__6::extensions
0x6d65d  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionOrigin> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionRecords::get_MarketPlaceItemNames()
0x6d662  call     T0x2B000461
0x6d667  brtrue.s loc_6D674
0x6d669  call     T0x2B000462
0x6d66e  stloc.2
0x6d66f  leave    loc_6D94C
0x6d674  ldarg.0
0x6d675  ldarg.0
0x6d676  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionRecords <AddExtensionSummariesAsync>d__6::extensions
0x6d67b  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionOrigin> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionRecords::get_Uris()
0x6d680  call     T0x2B000461
0x6d685  ldarg.0
0x6d686  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionRecords <AddExtensionSummariesAsync>d__6::extensions
0x6d68b  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionOrigin> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionRecords::get_MarketPlaceItemNames()
0x6d690  call     T0x2B000461
0x6d695  add
0x6d696  stfld    int32 <AddExtensionSummariesAsync>d__6::<extensionsCount>5__2
0x6d69b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x6d6a0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ProductIdProperty
0x6d6a5  stloc.s  5
0x6d6a7  dup
0x6d6a8  ldloc.s  5
0x6d6aa  ldarg.0
0x6d6ab  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <AddExtensionSummariesAsync>d__6::product
0x6d6b0  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Id()
0x6d6b5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6d6ba  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ChannelIdProperty
0x6d6bf  stloc.s  6
0x6d6c1  dup
0x6d6c2  ldloc.s  6
0x6d6c4  ldarg.0
0x6d6c5  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <AddExtensionSummariesAsync>d__6::product
0x6d6ca  isinst   Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel
0x6d6cf  stloc.s  4
0x6d6d1  ldloc.s  4
0x6d6d3  brtrue.s loc_6D6E7
0x6d6d5  ldarg.0
0x6d6d6  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <AddExtensionSummariesAsync>d__6::product
0x6d6db  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Channel()
0x6d6e0  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.IChannelModelSummary::get_Id()
0x6d6e5  br.s     loc_6D6F3
0x6d6e7  ldloc.s  4
0x6d6e9  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModelSummary Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_InstalledChannel()
0x6d6ee  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.IChannelModelSummary::get_Id()
0x6d6f3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6d6f8  ldsfld   string Extensions::SupportsExtensionsProperty
0x6d6fd  stloc.s  7
0x6d6ff  dup
0x6d700  ldloc.s  7
0x6d702  ldarg.0
0x6d703  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <AddExtensionSummariesAsync>d__6::product
0x6d708  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.ProductFeatures Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel::get_ProductFeatures()
0x6d70d  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.Products.ProductFeatures::get_SupportsExtensions()
0x6d712  box      [mscorlib]System.Boolean
0x6d717  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6d71c  ldsfld   string Extensions::NumberOfExtensionsToAddProperty
0x6d721  stloc.s  8
0x6d723  dup
0x6d724  ldloc.s  8
0x6d726  ldarg.0
0x6d727  ldfld    int32 <AddExtensionSummariesAsync>d__6::<extensionsCount>5__2
0x6d72c  box      [mscorlib]System.Int32
0x6d731  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6d736  stloc.3
0x6d737  ldarg.0
0x6d738  ldloc.1
0x6d739  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x6d73e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Telemetry()
0x6d743  dup
0x6d744  brtrue.s loc_6D74A
0x6d746  pop
0x6d747  ldnull
0x6d748  br.s     loc_6D757
0x6d74a  ldsfld   string Extensions::AddExtensionSummariesEvent
0x6d74f  ldloc.3
0x6d750  ldc.i4.0
0x6d751  ldc.i4.0
0x6d752  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x6d757  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <AddExtensionSummariesAsync>d__6::<telemetryOperation>5__3
0x6d75c  nop
0x6d75d  ldloc.0
0x6d75e  brfalse  loc_6D824
0x6d763  ldloc.0
0x6d764  ldc.i4.1
0x6d765  beq      loc_6D88C
0x6d76a  ldarg.0
0x6d76b  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <AddExtensionSummariesAsync>d__6::product
0x6d770  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.ProductFeatures Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel::get_ProductFeatures()
0x6d775  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.Products.ProductFeatures::get_SupportsExtensions()
0x6d77a  brtrue.s loc_6D7D8
0x6d77c  ldarg.0
0x6d77d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <AddExtensionSummariesAsync>d__6::<telemetryOperation>5__3
0x6d782  dup
0x6d783  brtrue.s loc_6D788
0x6d785  pop
0x6d786  br.s     loc_6D792
0x6d788  ldstr    aProductDoesNot// "Product does not support extensions."
0x6d78d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x6d792  ldarg.0
0x6d793  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <AddExtensionSummariesAsync>d__6::<telemetryOperation>5__3
0x6d798  dup
0x6d799  brtrue.s loc_6D79E
0x6d79b  pop
0x6d79c  br.s     loc_6D7AD
0x6d79e  ldsfld   string Extensions::ResultProperty
0x6d7a3  ldstr    aBlock// "Block"
0x6d7a8  call     void Microsoft.VisualStudio.Setup.Installer.CommonExtensions::SetProperty(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, string key, object value)
0x6d7ad  ldloc.1
0x6d7ae  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x6d7b3  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Logger()
0x6d7b8  dup
0x6d7b9  brtrue.s loc_6D7BE
0x6d7bb  pop
0x6d7bc  br.s     loc_6D7CD
0x6d7be  ldstr    aCannotAddExten// "Cannot add extensions to a product that"...
0x6d7c3  call     T0x2B000010
0x6d7c8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x6d7cd  call     T0x2B000462
0x6d7d2  stloc.2
0x6d7d3  leave    loc_6D94C
0x6d7d8  ldloc.1
0x6d7d9  ldarg.0
0x6d7da  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <AddExtensionSummariesAsync>d__6::product
0x6d7df  ldarg.0
0x6d7e0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionRecords <AddExtensionSummariesAsync>d__6::extensions
0x6d7e5  ldarg.0
0x6d7e6  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <AddExtensionSummariesAsync>d__6::token
0x6d7eb  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionQueryResult> Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::GetExtensionUrisAsync(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel product, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionRecords extensions, [opt] valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x6d7f0  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionQueryResult>::GetAwaiter()
0x6d7f5  stloc.s  0xB
0x6d7f7  ldloca.s 0xB
0x6d7f9  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionQueryResult>::get_IsCompleted()
0x6d7fe  brtrue.s loc_6D841
0x6d800  ldarg.0
0x6d801  ldc.i4.0
0x6d802  dup
0x6d803  stloc.0
0x6d804  stfld    int32 <AddExtensionSummariesAsync>d__6::<>1__state
0x6d809  ldarg.0
0x6d80a  ldloc.s  0xB
0x6d80c  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionQueryResult> <AddExtensionSummariesAsync>d__6::<>u__1
0x6d811  ldarg.0
0x6d812  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>> <AddExtensionSummariesAsync>d__6::<>t__builder
0x6d817  ldloca.s 0xB
0x6d819  ldarg.0
0x6d81a  call     T0x2B000463
0x6d81f  leave    loc_6D960
0x6d824  ldarg.0
0x6d825  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionQueryResult> <AddExtensionSummariesAsync>d__6::<>u__1
0x6d82a  stloc.s  0xB
0x6d82c  ldarg.0
0x6d82d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionQueryResult> <AddExtensionSummariesAsync>d__6::<>u__1
0x6d832  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionQueryResult>
0x6d838  ldarg.0
0x6d839  ldc.i4.m1
0x6d83a  dup
0x6d83b  stloc.0
0x6d83c  stfld    int32 <AddExtensionSummariesAsync>d__6::<>1__state
0x6d841  ldloca.s 0xB
0x6d843  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionQueryResult>::GetResult()
0x6d848  stloc.s  9
0x6d84a  ldloc.1
0x6d84b  ldloc.s  9
0x6d84d  ldarg.0
0x6d84e  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <AddExtensionSummariesAsync>d__6::product
0x6d853  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>> Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::AddExtensionModelsAsync(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionQueryResult extensionQueryResult, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel product)
0x6d858  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>>::GetAwaiter()
0x6d85d  stloc.s  0xC
0x6d85f  ldloca.s 0xC
0x6d861  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>>::get_IsCompleted()
0x6d866  brtrue.s loc_6D8A9
0x6d868  ldarg.0
0x6d869  ldc.i4.1
0x6d86a  dup
0x6d86b  stloc.0
0x6d86c  stfld    int32 <AddExtensionSummariesAsync>d__6::<>1__state
0x6d871  ldarg.0
0x6d872  ldloc.s  0xC
0x6d874  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>> <AddExtensionSummariesAsync>d__6::<>u__2
0x6d879  ldarg.0
0x6d87a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>> <AddExtensionSummariesAsync>d__6::<>t__builder
0x6d87f  ldloca.s 0xC
0x6d881  ldarg.0
0x6d882  call     T0x2B000464
0x6d887  leave    loc_6D960
0x6d88c  ldarg.0
0x6d88d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>> <AddExtensionSummariesAsync>d__6::<>u__2
0x6d892  stloc.s  0xC
0x6d894  ldarg.0
0x6d895  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>> <AddExtensionSummariesAsync>d__6::<>u__2
0x6d89a  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>>
0x6d8a0  ldarg.0
0x6d8a1  ldc.i4.m1
0x6d8a2  dup
0x6d8a3  stloc.0
0x6d8a4  stfld    int32 <AddExtensionSummariesAsync>d__6::<>1__state
0x6d8a9  ldloca.s 0xC
0x6d8ab  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>>::GetResult()
0x6d8b0  ldarg.0
0x6d8b1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <AddExtensionSummariesAsync>d__6::<telemetryOperation>5__3
0x6d8b6  dup
0x6d8b7  brtrue.s loc_6D8BC
0x6d8b9  pop
0x6d8ba  br.s     loc_6D8D1
0x6d8bc  ldsfld   string Extensions::NumberOfExtensionsAddedProperty
0x6d8c1  ldarg.0
0x6d8c2  ldfld    int32 <AddExtensionSummariesAsync>d__6::<extensionsCount>5__2
0x6d8c7  box      [mscorlib]System.Int32
0x6d8cc  call     void Microsoft.VisualStudio.Setup.Installer.CommonExtensions::SetProperty(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, string key, object value)
0x6d8d1  ldstr    aSuccessfullyAd_1// "Successfully added {0} extension summar"...
0x6d8d6  ldarg.0
0x6d8d7  ldfld    int32 <AddExtensionSummariesAsync>d__6::<extensionsCount>5__2
0x6d8dc  box      [mscorlib]System.Int32
0x6d8e1  call     string [mscorlib]System.String::Format(string, object)
0x6d8e6  stloc.s  0xA
0x6d8e8  ldarg.0
0x6d8e9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <AddExtensionSummariesAsync>d__6::<telemetryOperation>5__3
0x6d8ee  dup
0x6d8ef  brtrue.s loc_6D8F4
0x6d8f1  pop
0x6d8f2  br.s     loc_6D8FB
0x6d8f4  ldloc.s  0xA
0x6d8f6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x6d8fb  ldloc.1
0x6d8fc  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x6d901  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Logger()
0x6d906  dup
0x6d907  brtrue.s loc_6D90C
0x6d909  pop
0x6d90a  br.s     loc_6D918
0x6d90c  ldloc.s  0xA
0x6d90e  call     T0x2B000010
0x6d913  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x6d918  stloc.2
0x6d919  leave.s  loc_6D94C
0x6d91b  ldloc.0
0x6d91c  ldc.i4.0
0x6d91d  bge.s    loc_6D932
0x6d91f  ldarg.0
0x6d920  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <AddExtensionSummariesAsync>d__6::<telemetryOperation>5__3
0x6d925  brfalse.s loc_6D932
0x6d927  ldarg.0
0x6d928  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <AddExtensionSummariesAsync>d__6::<telemetryOperation>5__3
0x6d92d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d932  endfinally
0x6d933  stloc.s  0xD
0x6d935  ldarg.0
0x6d936  ldc.i4.s 0xFE
0x6d938  stfld    int32 <AddExtensionSummariesAsync>d__6::<>1__state
0x6d93d  ldarg.0
0x6d93e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>> <AddExtensionSummariesAsync>d__6::<>t__builder
0x6d943  ldloc.s  0xD
0x6d945  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>>::SetException(class [mscorlib]System.Exception)
0x6d94a  leave.s  loc_6D960
0x6d94c  ldarg.0
0x6d94d  ldc.i4.s 0xFE
0x6d94f  stfld    int32 <AddExtensionSummariesAsync>d__6::<>1__state
0x6d954  ldarg.0
0x6d955  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>> <AddExtensionSummariesAsync>d__6::<>t__builder
0x6d95a  ldloc.2
0x6d95b  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>>::SetResult(var<u1>)
0x6d960  ret
```
