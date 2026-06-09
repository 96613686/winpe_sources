# Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.UnelevatedInstallerTelemetryDecorator::SetResultProperties

- ea: `0x41c40`
- end: `0x41d68`
- name: `Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.UnelevatedInstallerTelemetryDecorator::SetResultProperties`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7dac0`

## callees

- `0x9310`
- `0x22680`
- `0x226e0`
- `0x2c4a0`
- `0x2c4b0`
- `0x2c500`
- `0x41c40`
- `0x41d70`
- `0x41e20`
- `0x424c0`
- `0x42e10`

## string_xrefs

- `0x41cee`: `Unable to construct a full product from the installed product summary.`

## pseudocode

```c

```

## disassembly

```asm
0x41c40  ldarg.2
0x41c41  ldstr    aResult// "result"
0x41c46  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x41c4b  ldnull
0x41c4c  stloc.0
0x41c4d  ldarg.0
0x41c4e  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.UnelevatedInstallerTelemetryDecorator::serviceOptions
0x41c53  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IProductsProviderService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_ProductsProvider()
0x41c58  stloc.1
0x41c59  ldarg.2
0x41c5a  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::get_InstanceId()
0x41c5f  brfalse.s loc_41C84
0x41c61  ldarg.1
0x41c62  ldsfld   string ProductOperation::InstanceIdProperty
0x41c67  ldarg.2
0x41c68  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::get_InstanceId()
0x41c6d  call     void Microsoft.VisualStudio.Setup.Installer.CommonExtensions::SetProperty(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, string key, object value)
0x41c72  ldloc.1
0x41c73  ldarg.2
0x41c74  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::get_InstanceId()
0x41c79  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel Microsoft.VisualStudio.Setup.Installer.Services.IProductsProviderService::GetInstalledProductSummaryForInstanceId(string)
0x41c7e  stloc.0
0x41c7f  leave.s  loc_41C84
0x41c81  pop
0x41c82  leave.s  loc_41C84
0x41c84  ldarg.0
0x41c85  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.PropertyProviders.IInstallerTelemetryPropertyProvider Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.UnelevatedInstallerTelemetryDecorator::propertyProvider
0x41c8a  ldarg.1
0x41c8b  brtrue.s loc_41C90
0x41c8d  ldnull
0x41c8e  br.s     loc_41C96
0x41c90  ldarg.1
0x41c91  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x41c96  ldarg.2
0x41c97  ldloc.0
0x41c98  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.PropertyProviders.IInstallerTelemetryPropertyProvider::AddOperationEndProperties(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult result, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel installedProduct)
0x41c9d  ldarg.2
0x41c9e  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::get_Error()
0x41ca3  ldnull
0x41ca4  call     bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation::op_Inequality(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation)
0x41ca9  brfalse.s loc_41CB3
0x41cab  ldarg.0
0x41cac  ldarg.1
0x41cad  ldarg.2
0x41cae  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.UnelevatedInstallerTelemetryDecorator::SetErrorResult(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult result)
0x41cb3  ldnull
0x41cb4  stloc.2
0x41cb5  ldloc.0
0x41cb6  brfalse  loc_41D5D
0x41cbb  ldarg.0
0x41cbc  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.UnelevatedInstallerTelemetryDecorator::serviceOptions
0x41cc1  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IProductsProviderService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_ProductsProvider()
0x41cc6  ldloc.0
0x41cc7  ldc.i4.1
0x41cc8  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductModel Microsoft.VisualStudio.Setup.Installer.Services.IProductsProviderService::GetInstalledProduct(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel summary, bool useScopedSelection)
0x41ccd  stloc.2
0x41cce  ldarg.0
0x41ccf  ldarg.1
0x41cd0  ldloc.2
0x41cd1  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.UnelevatedInstallerTelemetryDecorator::SetInstallSizeProperty(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductModel fullProduct)
0x41cd6  leave    loc_41D5D
0x41cdb  stloc.3
0x41cdc  ldarg.0
0x41cdd  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.UnelevatedInstallerTelemetryDecorator::serviceOptions
0x41ce2  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x41ce7  dup
0x41ce8  brtrue.s loc_41CED
0x41cea  pop
0x41ceb  br.s     loc_41CFD
0x41ced  ldloc.3
0x41cee  ldstr    aUnableToConstr// "Unable to construct a full product from"...
0x41cf3  call     T0x2B000010
0x41cf8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x41cfd  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x41d02  dup
0x41d03  ldsfld   string ProductOperation::ErrorMessageProperty
0x41d08  ldloc.3
0x41d09  callvirt instance string [mscorlib]System.Exception::get_Message()
0x41d0e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x41d13  dup
0x41d14  ldsfld   string ProductOperation::ErrorCodeProperty
0x41d19  ldloc.3
0x41d1a  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x41d1f  box      [mscorlib]System.Int32
0x41d24  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x41d29  dup
0x41d2a  ldsfld   string ProductOperation::ErrorStackProperty
0x41d2f  ldloc.3
0x41d30  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x41d35  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x41d3a  stloc.s  4
0x41d3c  ldarg.0
0x41d3d  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.UnelevatedInstallerTelemetryDecorator::serviceOptions
0x41d42  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Telemetry()
0x41d47  dup
0x41d48  brtrue.s loc_41D4D
0x41d4a  pop
0x41d4b  br.s     loc_41D5B
0x41d4d  ldsfld   string ProductOperation::EndOperationGetProductErrorEvent
0x41d52  ldloc.s  4
0x41d54  ldnull
0x41d55  ldc.i4.0
0x41d56  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteEvent(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, object, bool)
0x41d5b  leave.s  loc_41D5D
0x41d5d  ldarg.0
0x41d5e  ldarg.1
0x41d5f  ldloc.0
0x41d60  ldloc.2
0x41d61  ldarg.3
0x41d62  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.Telemetry.UnelevatedInstallerTelemetryDecorator::SetPackageDiffProperties(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel product, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductModel fullProduct, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Installer.IIdVersionTypeDescriptor> before)
0x41d67  ret
```
