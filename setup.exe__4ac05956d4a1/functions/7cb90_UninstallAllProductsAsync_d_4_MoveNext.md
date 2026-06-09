# <UninstallAllProductsAsync>d__4::MoveNext

- ea: `0x7cb90`
- end: `0x7ce1e`
- name: `<UninstallAllProductsAsync>d__4::MoveNext`
- size: `654`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0xa120`
- `0x226c0`
- `0x2c4b0`
- `0x2c4f0`
- `0x3a8c0`
- `0x40b30`
- `0x40c60`
- `0x7c9f0`
- `0x7cb90`

## string_xrefs

- `0x7cd0e`: `Failed to uninstall '{0}'`
- `0x7cdc3`: `Exception thrown while uninstalling a product`

## pseudocode

```c

```

## disassembly

```asm
0x7cb90  ldarg.0
0x7cb91  ldfld    int32 <UninstallAllProductsAsync>d__4::<>1__state
0x7cb96  stloc.0
0x7cb97  ldarg.0
0x7cb98  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUninstaller <UninstallAllProductsAsync>d__4::<>4__this
0x7cb9d  stloc.1
0x7cb9e  ldloc.0
0x7cb9f  pop
0x7cba0  nop
0x7cba1  ldloc.0
0x7cba2  brfalse  loc_7CC7F
0x7cba7  ldloc.1
0x7cba8  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x7cbad  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IProductsRepository Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_ProductsRepository()
0x7cbb2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel> Microsoft.VisualStudio.Setup.Installer.Services.IProductsProviderService::GetInstalledProductSummaries()
0x7cbb7  call     T0x2B00052B
0x7cbbc  stloc.2
0x7cbbd  ldloc.2
0x7cbbe  call     T0x2B0000AA
0x7cbc3  stloc.3
0x7cbc4  ldarg.0
0x7cbc5  ldc.r8   0.0
0x7cbce  stfld    float64 <UninstallAllProductsAsync>d__4::<productProgress>5__2
0x7cbd3  ldarg.0
0x7cbd4  ldc.r8   1.0
0x7cbdd  ldloc.3
0x7cbde  conv.r8
0x7cbdf  div
0x7cbe0  stfld    float64 <UninstallAllProductsAsync>d__4::<progressIncrement>5__3
0x7cbe5  ldarg.0
0x7cbe6  ldloc.2
0x7cbe7  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel[] <UninstallAllProductsAsync>d__4::<>7__wrap3
0x7cbec  ldarg.0
0x7cbed  ldc.i4.0
0x7cbee  stfld    int32 <UninstallAllProductsAsync>d__4::<>7__wrap4
0x7cbf3  br       loc_7CD92
0x7cbf8  ldarg.0
0x7cbf9  ldarg.0
0x7cbfa  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel[] <UninstallAllProductsAsync>d__4::<>7__wrap3
0x7cbff  ldarg.0
0x7cc00  ldfld    int32 <UninstallAllProductsAsync>d__4::<>7__wrap4
0x7cc05  ldelem.ref
0x7cc06  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <UninstallAllProductsAsync>d__4::<product>5__6
0x7cc0b  ldarg.0
0x7cc0c  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <UninstallAllProductsAsync>d__4::token
0x7cc11  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x7cc16  ldloc.1
0x7cc17  ldloc.1
0x7cc18  ldarg.0
0x7cc19  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <UninstallAllProductsAsync>d__4::<product>5__6
0x7cc1e  call     string Microsoft.VisualStudio.Setup.Installer.Extensions::GetDisplayName(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel product)
0x7cc23  ldarg.0
0x7cc24  ldfld    float64 <UninstallAllProductsAsync>d__4::<productProgress>5__2
0x7cc29  ldc.i4.5
0x7cc2a  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs::.ctor(string, float64, valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ProgressType)
0x7cc2f  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::OnProgress(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs args)
0x7cc34  ldarg.0
0x7cc35  ldloc.1
0x7cc36  ldfld    class CreateUninstaller Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUninstaller::createUninstaller
0x7cc3b  ldarg.0
0x7cc3c  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerService <UninstallAllProductsAsync>d__4::installerService
0x7cc41  ldarg.0
0x7cc42  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <UninstallAllProductsAsync>d__4::<product>5__6
0x7cc47  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller CreateUninstaller::Invoke(class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerService installerService, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel installedProduct)
0x7cc4c  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller <UninstallAllProductsAsync>d__4::<uninstaller>5__7
0x7cc51  ldarg.0
0x7cc52  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller <UninstallAllProductsAsync>d__4::<uninstaller>5__7
0x7cc57  ldloc.1
0x7cc58  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::OnProgress(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs args)
0x7cc5e  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs>::.ctor(object, native int)
0x7cc63  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller::add_Progress(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs>)
0x7cc68  ldarg.0
0x7cc69  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller <UninstallAllProductsAsync>d__4::<uninstaller>5__7
0x7cc6e  ldloc.1
0x7cc6f  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::OnPausable(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.PausableEventArgs args)
0x7cc75  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.PausableEventArgs>::.ctor(object, native int)
0x7cc7a  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller::add_Pausable(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.PausableEventArgs>)
0x7cc7f  nop
0x7cc80  ldloc.0
0x7cc81  brfalse.s loc_7CCD2
0x7cc83  ldarg.0
0x7cc84  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller <UninstallAllProductsAsync>d__4::<uninstaller>5__7
0x7cc89  ldarg.0
0x7cc8a  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <UninstallAllProductsAsync>d__4::token
0x7cc8f  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller::InvokeAsync(valuetype [mscorlib]System.Threading.CancellationToken)
0x7cc94  ldc.i4.0
0x7cc95  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::ConfigureAwait(!!T0)
0x7cc9a  stloc.s  5
0x7cc9c  ldloca.s 5
0x7cc9e  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::GetAwaiter()
0x7cca3  stloc.s  4
0x7cca5  ldloca.s 4
0x7cca7  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::get_IsCompleted()
0x7ccac  brtrue.s loc_7CCEF
0x7ccae  ldarg.0
0x7ccaf  ldc.i4.0
0x7ccb0  dup
0x7ccb1  stloc.0
0x7ccb2  stfld    int32 <UninstallAllProductsAsync>d__4::<>1__state
0x7ccb7  ldarg.0
0x7ccb8  ldloc.s  4
0x7ccba  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <UninstallAllProductsAsync>d__4::<>u__1
0x7ccbf  ldarg.0
0x7ccc0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <UninstallAllProductsAsync>d__4::<>t__builder
0x7ccc5  ldloca.s 4
0x7ccc7  ldarg.0
0x7ccc8  call     T0x2B00052C
0x7cccd  leave    loc_7CE1D
0x7ccd2  ldarg.0
0x7ccd3  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <UninstallAllProductsAsync>d__4::<>u__1
0x7ccd8  stloc.s  4
0x7ccda  ldarg.0
0x7ccdb  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult> <UninstallAllProductsAsync>d__4::<>u__1
0x7cce0  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>
0x7cce6  ldarg.0
0x7cce7  ldc.i4.m1
0x7cce8  dup
0x7cce9  stloc.0
0x7ccea  stfld    int32 <UninstallAllProductsAsync>d__4::<>1__state
0x7ccef  ldloca.s 4
0x7ccf1  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult>::GetResult()
0x7ccf6  pop
0x7ccf7  leave.s  loc_7CD2E
0x7ccf9  stloc.s  6
0x7ccfb  ldloc.1
0x7ccfc  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x7cd01  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x7cd06  dup
0x7cd07  brtrue.s loc_7CD0C
0x7cd09  pop
0x7cd0a  br.s     loc_7CD2C
0x7cd0c  ldloc.s  6
0x7cd0e  ldstr    aFailedToUninst// "Failed to uninstall '{0}'"
0x7cd13  ldc.i4.1
0x7cd14  newarr   [mscorlib]System.Object
0x7cd19  dup
0x7cd1a  ldc.i4.0
0x7cd1b  ldarg.0
0x7cd1c  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <UninstallAllProductsAsync>d__4::<product>5__6
0x7cd21  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductIdentityModel::get_InstallationPath()
0x7cd26  stelem.ref
0x7cd27  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x7cd2c  leave.s  loc_7CD2E
0x7cd2e  leave.s  loc_7CD63
0x7cd30  ldloc.0
0x7cd31  ldc.i4.0
0x7cd32  bge.s    loc_7CD62
0x7cd34  ldarg.0
0x7cd35  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller <UninstallAllProductsAsync>d__4::<uninstaller>5__7
0x7cd3a  ldloc.1
0x7cd3b  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::OnProgress(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs args)
0x7cd41  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs>::.ctor(object, native int)
0x7cd46  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller::remove_Progress(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs>)
0x7cd4b  ldarg.0
0x7cd4c  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller <UninstallAllProductsAsync>d__4::<uninstaller>5__7
0x7cd51  ldloc.1
0x7cd52  ldftn    instance void Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::OnPausable(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.PausableEventArgs args)
0x7cd58  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.PausableEventArgs>::.ctor(object, native int)
0x7cd5d  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller::remove_Pausable(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.PausableEventArgs>)
0x7cd62  endfinally
0x7cd63  ldarg.0
0x7cd64  ldarg.0
0x7cd65  ldfld    float64 <UninstallAllProductsAsync>d__4::<productProgress>5__2
0x7cd6a  ldarg.0
0x7cd6b  ldfld    float64 <UninstallAllProductsAsync>d__4::<progressIncrement>5__3
0x7cd70  add
0x7cd71  stfld    float64 <UninstallAllProductsAsync>d__4::<productProgress>5__2
0x7cd76  ldarg.0
0x7cd77  ldnull
0x7cd78  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller <UninstallAllProductsAsync>d__4::<uninstaller>5__7
0x7cd7d  ldarg.0
0x7cd7e  ldnull
0x7cd7f  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <UninstallAllProductsAsync>d__4::<product>5__6
0x7cd84  ldarg.0
0x7cd85  ldarg.0
0x7cd86  ldfld    int32 <UninstallAllProductsAsync>d__4::<>7__wrap4
0x7cd8b  ldc.i4.1
0x7cd8c  add
0x7cd8d  stfld    int32 <UninstallAllProductsAsync>d__4::<>7__wrap4
0x7cd92  ldarg.0
0x7cd93  ldfld    int32 <UninstallAllProductsAsync>d__4::<>7__wrap4
0x7cd98  ldarg.0
0x7cd99  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel[] <UninstallAllProductsAsync>d__4::<>7__wrap3
0x7cd9e  ldlen
0x7cd9f  conv.i4
0x7cda0  blt      loc_7CBF8
0x7cda5  ldarg.0
0x7cda6  ldnull
0x7cda7  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel[] <UninstallAllProductsAsync>d__4::<>7__wrap3
0x7cdac  leave.s  loc_7CDD4
0x7cdae  stloc.s  7
0x7cdb0  ldloc.1
0x7cdb1  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x7cdb6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x7cdbb  dup
0x7cdbc  brtrue.s loc_7CDC1
0x7cdbe  pop
0x7cdbf  br.s     loc_7CDD2
0x7cdc1  ldloc.s  7
0x7cdc3  ldstr    aExceptionThrow// "Exception thrown while uninstalling a p"...
0x7cdc8  call     T0x2B000010
0x7cdcd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x7cdd2  leave.s  loc_7CDD4
0x7cdd4  ldloc.1
0x7cdd5  ldloc.1
0x7cdd6  call     string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Resources::get_FinishingUp()
0x7cddb  ldc.r8   1.0
0x7cde4  ldc.i4.5
0x7cde5  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs::.ctor(string, float64, valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ProgressType)
0x7cdea  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::OnProgress(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs args)
0x7cdef  leave.s  loc_7CE0A
0x7cdf1  stloc.s  8
0x7cdf3  ldarg.0
0x7cdf4  ldc.i4.s 0xFE
0x7cdf6  stfld    int32 <UninstallAllProductsAsync>d__4::<>1__state
0x7cdfb  ldarg.0
0x7cdfc  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <UninstallAllProductsAsync>d__4::<>t__builder
0x7ce01  ldloc.s  8
0x7ce03  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x7ce08  leave.s  loc_7CE1D
0x7ce0a  ldarg.0
0x7ce0b  ldc.i4.s 0xFE
0x7ce0d  stfld    int32 <UninstallAllProductsAsync>d__4::<>1__state
0x7ce12  ldarg.0
0x7ce13  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <UninstallAllProductsAsync>d__4::<>t__builder
0x7ce18  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x7ce1d  ret
```
