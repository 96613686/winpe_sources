# <HandleAsync>d__7::MoveNext_0

- ea: `0x8a840`
- end: `0x8ae27`
- name: `<HandleAsync>d__7::MoveNext_0`
- size: `1511`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `installer_update`

## callees

- `0x9310`
- `0xa750`
- `0xab10`
- `0x2b9c0`
- `0x2b9d0`
- `0x2bae0`
- `0x368e0`
- `0x389a0`
- `0x3e040`
- `0x3e300`
- `0x3e440`
- `0x408d0`
- `0x409a0`
- `0x414c0`
- `0x4fbe0`
- `0x53b40`
- `0x53b50`
- `0x554f0`
- `0x55580`
- `0x55590`
- `0x8a840`

## string_xrefs

- `0x8acdf`: `Unhandled exception {0} encountered determining install operation result - {1}`
- `0x8aba2`: `No result returned for Update all operation.`

## pseudocode

```c

```

## disassembly

```asm
0x8a840  ldarg.0
0x8a841  ldfld    int32 <HandleAsync>d__7::<>1__state
0x8a846  stloc.0
0x8a847  ldarg.0
0x8a848  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.UpdateAllCommand <HandleAsync>d__7::<>4__this
0x8a84d  stloc.1
0x8a84e  ldloc.0
0x8a84f  ldc.i4.3
0x8a850  ble.un.s loc_8A8CB
0x8a852  ldarg.0
0x8a853  ldsfld   string UpdateAll::UpdateAllEvent
0x8a858  stfld    string <HandleAsync>d__7::<eventName>5__2
0x8a85d  ldarg.0
0x8a85e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::.ctor()
0x8a863  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <HandleAsync>d__7::<results>5__3
0x8a868  ldarg.0
0x8a869  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x8a86e  stfld    class [mscorlib]System.Collections.Generic.List`1<string> <HandleAsync>d__7::<resultsTelemetry>5__4
0x8a873  ldarg.0
0x8a874  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x8a879  ldsfld   string UpdateAll::TotalUpdatableProductsCountProperty
0x8a87e  stloc.2
0x8a87f  dup
0x8a880  ldloc.2
0x8a881  ldarg.0
0x8a882  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.UpdateAllCommandOptions <HandleAsync>d__7::options
0x8a887  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel> Microsoft.VisualStudio.Setup.Installer.Commands.UpdateAllCommandOptions::get_Products()
0x8a88c  call     T0x2B0000AA
0x8a891  box      [mscorlib]System.Int32
0x8a896  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8a89b  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> <HandleAsync>d__7::<properties>5__5
0x8a8a0  ldarg.0
0x8a8a1  ldloc.1
0x8a8a2  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.UpdateAllCommand::serviceOptions
0x8a8a7  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerBaseServiceOptions::get_Telemetry()
0x8a8ac  dup
0x8a8ad  brtrue.s loc_8A8B3
0x8a8af  pop
0x8a8b0  ldnull
0x8a8b1  br.s     loc_8A8C6
0x8a8b3  ldarg.0
0x8a8b4  ldfld    string <HandleAsync>d__7::<eventName>5__2
0x8a8b9  ldarg.0
0x8a8ba  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> <HandleAsync>d__7::<properties>5__5
0x8a8bf  ldc.i4.0
0x8a8c0  ldc.i4.0
0x8a8c1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x8a8c6  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <HandleAsync>d__7::<telemetryOperation>5__6
0x8a8cb  nop
0x8a8cc  ldloc.0
0x8a8cd  ldc.i4.2
0x8a8ce  ble.un.s loc_8A8DE
0x8a8d0  ldloc.0
0x8a8d1  ldc.i4.3
0x8a8d2  beq      loc_8ADAB
0x8a8d7  ldarg.0
0x8a8d8  ldc.i4.0
0x8a8d9  stfld    int32 <HandleAsync>d__7::<>7__wrap7
0x8a8de  nop
0x8a8df  ldloc.0
0x8a8e0  ldc.i4.1
0x8a8e1  ble.un.s loc_8A8EA
0x8a8e3  ldloc.0
0x8a8e4  ldc.i4.2
0x8a8e5  beq      loc_8AC76
0x8a8ea  nop
0x8a8eb  ldloc.0
0x8a8ec  ldc.i4.1
0x8a8ed  ble.un   loc_8A9A5
0x8a8f2  ldloc.1
0x8a8f3  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.UpdateAllCommand::serviceOptions
0x8a8f8  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IPublishSubscribeService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions::get_PublishSubscribeService()
0x8a8fd  ldc.i4.1
0x8a8fe  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Events.BatchedOperationStateChangeEvent::.ctor(bool isOperationInProgress)
0x8a903  callvirt T0x2B0005CE
0x8a908  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext>::.ctor()
0x8a90d  stloc.s  5
0x8a90f  ldarg.0
0x8a910  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.UpdateAllCommandOptions <HandleAsync>d__7::options
0x8a915  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel> Microsoft.VisualStudio.Setup.Installer.Commands.UpdateAllCommandOptions::get_Products()
0x8a91a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel>::GetEnumerator()
0x8a91f  stloc.s  6
0x8a921  br.s     loc_8A977
0x8a923  ldloc.s  6
0x8a925  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel>::get_Current()
0x8a92a  stloc.s  7
0x8a92c  ldnull
0x8a92d  ldc.i4.0
0x8a92e  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.OperationMode>::.ctor(var<u1>)
0x8a933  ldnull
0x8a934  ldnull
0x8a935  ldnull
0x8a936  ldnull
0x8a937  ldc.i4.0
0x8a938  ldc.i4.0
0x8a939  ldc.i4.0
0x8a93a  ldloca.s 0xA
0x8a93c  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x8a942  ldloc.s  0xA
0x8a944  ldnull
0x8a945  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::.ctor(string installSessionId, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.OperationMode> operationMode, string productKey, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> vsFlights, string layoutPath, string installLayoutPath, bool isFocusedUi, bool previewUpdate, bool keepWindowsUpdateOn, valuetype [mscorlib]System.Nullable`1<bool> removeOos, class [System]System.Uri layoutUri)
0x8a94a  dup
0x8a94b  ldarg.0
0x8a94c  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.UpdateAllCommandOptions <HandleAsync>d__7::options
0x8a951  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Commands.UpdateAllCommandOptions::get_FromCommandLine()
0x8a956  callvirt instance modreq(System.Runtime.CompilerServices.IsExternalInit) void Microsoft.VisualStudio.Setup.Installer.Installer.OperationContextOptions::set_FromCommandLine(bool value)
0x8a95b  stloc.s  8
0x8a95d  ldloc.1
0x8a95e  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallOperationContextProvider Microsoft.VisualStudio.Setup.Installer.Commands.UpdateAllCommand::contextProvider
0x8a963  ldloc.s  7
0x8a965  ldloc.s  8
0x8a967  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext Microsoft.VisualStudio.Setup.Installer.Installer.IInstallOperationContextProvider::GetUpdateContext(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel installedProduct, class Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions options)
0x8a96c  stloc.s  9
0x8a96e  ldloc.s  5
0x8a970  ldloc.s  9
0x8a972  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext>::Add(var<u1>)
0x8a977  ldloc.s  6
0x8a979  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8a97e  brtrue.s loc_8A923
0x8a980  leave.s  loc_8A992
0x8a982  ldloc.0
0x8a983  ldc.i4.0
0x8a984  bge.s    loc_8A991
0x8a986  ldloc.s  6
0x8a988  brfalse.s loc_8A991
0x8a98a  ldloc.s  6
0x8a98c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8a991  endfinally
0x8a992  ldarg.0
0x8a993  ldloc.1
0x8a994  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerFactory Microsoft.VisualStudio.Setup.Installer.Commands.UpdateAllCommand::installerFactory
0x8a999  ldloc.s  5
0x8a99b  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Installer.IBatchUpdater Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerFactory::CreateBatchUpdater(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext> operationContexts)
0x8a9a0  stfld    class Microsoft.VisualStudio.Setup.Installer.Installer.IBatchUpdater <HandleAsync>d__7::<batchUpdater>5__9
0x8a9a5  nop
0x8a9a6  ldloc.0
0x8a9a7  ldc.i4.1
0x8a9a8  ble.un.s loc_8A9B7
0x8a9aa  ldarg.0
0x8a9ab  ldloc.s  5
0x8a9ad  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext>::GetEnumerator()
0x8a9b2  stfld    valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext> <HandleAsync>d__7::<>7__wrap9
0x8a9b7  nop
0x8a9b8  ldloc.0
0x8a9b9  brfalse  loc_8AA5C
0x8a9be  ldloc.0
0x8a9bf  ldc.i4.1
0x8a9c0  beq      loc_8AAEF
0x8a9c5  br       loc_8AB23
0x8a9ca  ldarg.0
0x8a9cb  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext> <HandleAsync>d__7::<>7__wrap9
0x8a9d0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext>::get_Current()
0x8a9d5  stloc.s  0xB
0x8a9d7  ldarg.0
0x8a9d8  ldarg.0
0x8a9d9  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.IBatchUpdater <HandleAsync>d__7::<batchUpdater>5__9
0x8a9de  ldloc.s  0xB
0x8a9e0  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext::get_Product()
0x8a9e5  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller Microsoft.VisualStudio.Setup.Installer.Installer.IBatchUpdater::GetInstaller(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel)
0x8a9ea  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller <HandleAsync>d__7::<installer>5__11
0x8a9ef  ldarg.0
0x8a9f0  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller <HandleAsync>d__7::<installer>5__11
0x8a9f5  brfalse  loc_8AB1C
0x8a9fa  ldarg.0
0x8a9fb  ldloc.1
0x8a9fc  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Readers.IInstallingProductReader Microsoft.VisualStudio.Setup.Installer.Commands.UpdateAllCommand::productReader
0x8aa01  ldloc.s  0xB
0x8aa03  ldarg.0
0x8aa04  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller <HandleAsync>d__7::<installer>5__11
0x8aa09  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstallingProductModel Microsoft.VisualStudio.Setup.Installer.Models.Readers.IInstallingProductReader::ReadInstallingProduct(class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext operationContext, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller installer)
0x8aa0e  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstallingProductModel <HandleAsync>d__7::<installingProductModel>5__12
0x8aa13  ldarg.0
0x8aa14  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstallingProductModel <HandleAsync>d__7::<installingProductModel>5__12
0x8aa19  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> Microsoft.VisualStudio.Setup.Installer.Models.IOperationModel::InvokeAsync()
0x8aa1e  ldc.i4.0
0x8aa1f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::ConfigureAwait(!!T0)
0x8aa24  stloc.s  0xE
0x8aa26  ldloca.s 0xE
0x8aa28  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::GetAwaiter()
0x8aa2d  stloc.s  0xD
0x8aa2f  ldloca.s 0xD
0x8aa31  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::get_IsCompleted()
0x8aa36  brtrue.s loc_8AA79
0x8aa38  ldarg.0
0x8aa39  ldc.i4.0
0x8aa3a  dup
0x8aa3b  stloc.0
0x8aa3c  stfld    int32 <HandleAsync>d__7::<>1__state
0x8aa41  ldarg.0
0x8aa42  ldloc.s  0xD
0x8aa44  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <HandleAsync>d__7::<>u__1
0x8aa49  ldarg.0
0x8aa4a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsync>d__7::<>t__builder
0x8aa4f  ldloca.s 0xD
0x8aa51  ldarg.0
0x8aa52  call     T0x2B0005CF
0x8aa57  leave    loc_8AE26
0x8aa5c  ldarg.0
0x8aa5d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <HandleAsync>d__7::<>u__1
0x8aa62  stloc.s  0xD
0x8aa64  ldarg.0
0x8aa65  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <HandleAsync>d__7::<>u__1
0x8aa6a  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>
0x8aa70  ldarg.0
0x8aa71  ldc.i4.m1
0x8aa72  dup
0x8aa73  stloc.0
0x8aa74  stfld    int32 <HandleAsync>d__7::<>1__state
0x8aa79  ldloca.s 0xD
0x8aa7b  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::GetResult()
0x8aa80  stloc.s  0xC
0x8aa82  ldarg.0
0x8aa83  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <HandleAsync>d__7::<results>5__3
0x8aa88  ldloc.s  0xC
0x8aa8a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::Add(var<u1>)
0x8aa8f  ldarg.0
0x8aa90  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <HandleAsync>d__7::<resultsTelemetry>5__4
0x8aa95  ldloc.1
0x8aa96  ldarg.0
0x8aa97  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstallingProductModel <HandleAsync>d__7::<installingProductModel>5__12
0x8aa9c  ldarg.0
0x8aa9d  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller <HandleAsync>d__7::<installer>5__11
0x8aaa2  ldloc.s  0xC
0x8aaa4  call     instance string Microsoft.VisualStudio.Setup.Installer.Commands.UpdateAllCommand::GetResultTelemetry(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstallingProductModel installingProduct, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller installer, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult result)
0x8aaa9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8aaae  ldloc.1
0x8aaaf  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.IBatchedOperationResultHandler Microsoft.VisualStudio.Setup.Installer.Commands.UpdateAllCommand::resultHandler
0x8aab4  ldloc.s  0xC
0x8aab6  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.VisualStudio.Setup.Installer.Commands.IBatchedOperationResultHandler::HandleAsync(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult result)
0x8aabb  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x8aac0  stloc.s  0xF
0x8aac2  ldloca.s 0xF
0x8aac4  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x8aac9  brtrue.s loc_8AB0C
0x8aacb  ldarg.0
0x8aacc  ldc.i4.1
0x8aacd  dup
0x8aace  stloc.0
0x8aacf  stfld    int32 <HandleAsync>d__7::<>1__state
0x8aad4  ldarg.0
0x8aad5  ldloc.s  0xF
0x8aad7  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <HandleAsync>d__7::<>u__2
0x8aadc  ldarg.0
0x8aadd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsync>d__7::<>t__builder
0x8aae2  ldloca.s 0xF
0x8aae4  ldarg.0
0x8aae5  call     T0x2B0005D0
0x8aaea  leave    loc_8AE26
0x8aaef  ldarg.0
0x8aaf0  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <HandleAsync>d__7::<>u__2
0x8aaf5  stloc.s  0xF
0x8aaf7  ldarg.0
0x8aaf8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <HandleAsync>d__7::<>u__2
0x8aafd  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x8ab03  ldarg.0
0x8ab04  ldc.i4.m1
0x8ab05  dup
0x8ab06  stloc.0
0x8ab07  stfld    int32 <HandleAsync>d__7::<>1__state
0x8ab0c  ldloca.s 0xF
0x8ab0e  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x8ab13  brtrue.s loc_8AB33
0x8ab15  ldarg.0
0x8ab16  ldnull
0x8ab17  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstallingProductModel <HandleAsync>d__7::<installingProductModel>5__12
0x8ab1c  ldarg.0
0x8ab1d  ldnull
0x8ab1e  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller <HandleAsync>d__7::<installer>5__11
0x8ab23  ldarg.0
0x8ab24  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext> <HandleAsync>d__7::<>7__wrap9
0x8ab29  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext>::MoveNext()
0x8ab2e  brtrue   loc_8A9CA
0x8ab33  leave.s  loc_8AB4B
0x8ab35  ldloc.0
0x8ab36  ldc.i4.0
0x8ab37  bge.s    loc_8AB4A
0x8ab39  ldarg.0
0x8ab3a  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext> <HandleAsync>d__7::<>7__wrap9
0x8ab3f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext>
0x8ab45  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ab4a  endfinally
0x8ab4b  ldarg.0
0x8ab4c  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext> <HandleAsync>d__7::<>7__wrap9
0x8ab51  initobj  valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext>
0x8ab57  leave.s  loc_8AB71
0x8ab59  ldloc.0
0x8ab5a  ldc.i4.0
0x8ab5b  bge.s    loc_8AB70
0x8ab5d  ldarg.0
0x8ab5e  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.IBatchUpdater <HandleAsync>d__7::<batchUpdater>5__9
0x8ab63  brfalse.s loc_8AB70
0x8ab65  ldarg.0
0x8ab66  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.IBatchUpdater <HandleAsync>d__7::<batchUpdater>5__9
0x8ab6b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ab70  endfinally
0x8ab71  ldarg.0
0x8ab72  ldnull
0x8ab73  stfld    class Microsoft.VisualStudio.Setup.Installer.Installer.IBatchUpdater <HandleAsync>d__7::<batchUpdater>5__9
0x8ab78  leave.s  loc_8AB95
0x8ab7a  ldloc.0
  ... truncated ...
```
