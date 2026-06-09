# <SelectExtensionsAsync>d__15::MoveNext

- ea: `0x7e260`
- end: `0x7e41f`
- name: `<SelectExtensionsAsync>d__15::MoveNext`
- size: `447`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x22670`
- `0x226e0`
- `0x2b920`
- `0x43d30`
- `0x43ff0`
- `0x7e260`

## string_xrefs

- `0x7e295`: `Cannot load the installed product summary for migration.`
- `0x7e2b8`: `Cannot load full installed product for migration.`

## pseudocode

```c

```

## disassembly

```asm
0x7e260  ldarg.0
0x7e261  ldfld    int32 <SelectExtensionsAsync>d__15::<>1__state
0x7e266  stloc.0
0x7e267  ldarg.0
0x7e268  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer <SelectExtensionsAsync>d__15::<>4__this
0x7e26d  stloc.1
0x7e26e  ldloc.0
0x7e26f  brfalse  loc_7E31E
0x7e274  ldloc.0
0x7e275  ldc.i4.1
0x7e276  beq      loc_7E39F
0x7e27b  ldloc.1
0x7e27c  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::serviceOptions
0x7e281  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IProductsRepository Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions::get_ProductsRepository()
0x7e286  ldloc.1
0x7e287  ldfld    string Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::installationPath
0x7e28c  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel Microsoft.VisualStudio.Setup.Installer.Services.IProductsProviderService::GetInstalledProductSummary(string)
0x7e291  dup
0x7e292  brtrue.s loc_7E2A0
0x7e294  pop
0x7e295  ldstr    aCannotLoadTheI// "Cannot load the installed product summa"...
0x7e29a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7e29f  throw
0x7e2a0  stloc.3
0x7e2a1  ldarg.0
0x7e2a2  ldloc.1
0x7e2a3  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::serviceOptions
0x7e2a8  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IProductsRepository Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions::get_ProductsRepository()
0x7e2ad  ldloc.3
0x7e2ae  ldc.i4.1
0x7e2af  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductModel Microsoft.VisualStudio.Setup.Installer.Services.IProductsProviderService::GetInstalledProduct(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel summary, bool useScopedSelection)
0x7e2b4  dup
0x7e2b5  brtrue.s loc_7E2C3
0x7e2b7  pop
0x7e2b8  ldstr    aCannotLoadFull// "Cannot load full installed product for "...
0x7e2bd  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7e2c2  throw
0x7e2c3  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductModel <SelectExtensionsAsync>d__15::<migrateFromProduct>5__2
0x7e2c8  ldloc.1
0x7e2c9  ldarg.0
0x7e2ca  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <SelectExtensionsAsync>d__15::product
0x7e2cf  ldarg.0
0x7e2d0  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductModel <SelectExtensionsAsync>d__15::<migrateFromProduct>5__2
0x7e2d5  ldarg.0
0x7e2d6  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <SelectExtensionsAsync>d__15::cancellationToken
0x7e2db  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::SelectPerMachineExtensionsAsync(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel product, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductModel migrateFromProduct, [opt] valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x7e2e0  ldc.i4.0
0x7e2e1  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::ConfigureAwait(!!T0)
0x7e2e6  stloc.s  7
0x7e2e8  ldloca.s 7
0x7e2ea  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::GetAwaiter()
0x7e2ef  stloc.s  6
0x7e2f1  ldloca.s 6
0x7e2f3  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::get_IsCompleted()
0x7e2f8  brtrue.s loc_7E33B
0x7e2fa  ldarg.0
0x7e2fb  ldc.i4.0
0x7e2fc  dup
0x7e2fd  stloc.0
0x7e2fe  stfld    int32 <SelectExtensionsAsync>d__15::<>1__state
0x7e303  ldarg.0
0x7e304  ldloc.s  6
0x7e306  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <SelectExtensionsAsync>d__15::<>u__1
0x7e30b  ldarg.0
0x7e30c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <SelectExtensionsAsync>d__15::<>t__builder
0x7e311  ldloca.s 6
0x7e313  ldarg.0
0x7e314  call     T0x2B000538
0x7e319  leave    loc_7E41E
0x7e31e  ldarg.0
0x7e31f  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <SelectExtensionsAsync>d__15::<>u__1
0x7e324  stloc.s  6
0x7e326  ldarg.0
0x7e327  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <SelectExtensionsAsync>d__15::<>u__1
0x7e32c  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>
0x7e332  ldarg.0
0x7e333  ldc.i4.m1
0x7e334  dup
0x7e335  stloc.0
0x7e336  stfld    int32 <SelectExtensionsAsync>d__15::<>1__state
0x7e33b  ldloca.s 6
0x7e33d  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::GetResult()
0x7e342  stloc.s  5
0x7e344  ldarg.0
0x7e345  ldloc.s  5
0x7e347  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <SelectExtensionsAsync>d__15::<perMachineFailedExtensions>5__3
0x7e34c  ldloc.1
0x7e34d  ldarg.0
0x7e34e  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <SelectExtensionsAsync>d__15::product
0x7e353  ldarg.0
0x7e354  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductModel <SelectExtensionsAsync>d__15::<migrateFromProduct>5__2
0x7e359  ldarg.0
0x7e35a  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <SelectExtensionsAsync>d__15::cancellationToken
0x7e35f  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::SelectPerUserExtensionsAsync(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel product, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductModel migrateFromProduct, [opt] valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x7e364  ldc.i4.0
0x7e365  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::ConfigureAwait(!!T0)
0x7e36a  stloc.s  7
0x7e36c  ldloca.s 7
0x7e36e  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::GetAwaiter()
0x7e373  stloc.s  6
0x7e375  ldloca.s 6
0x7e377  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::get_IsCompleted()
0x7e37c  brtrue.s loc_7E3BC
0x7e37e  ldarg.0
0x7e37f  ldc.i4.1
0x7e380  dup
0x7e381  stloc.0
0x7e382  stfld    int32 <SelectExtensionsAsync>d__15::<>1__state
0x7e387  ldarg.0
0x7e388  ldloc.s  6
0x7e38a  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <SelectExtensionsAsync>d__15::<>u__1
0x7e38f  ldarg.0
0x7e390  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <SelectExtensionsAsync>d__15::<>t__builder
0x7e395  ldloca.s 6
0x7e397  ldarg.0
0x7e398  call     T0x2B000538
0x7e39d  leave.s  loc_7E41E
0x7e39f  ldarg.0
0x7e3a0  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <SelectExtensionsAsync>d__15::<>u__1
0x7e3a5  stloc.s  6
0x7e3a7  ldarg.0
0x7e3a8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <SelectExtensionsAsync>d__15::<>u__1
0x7e3ad  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>
0x7e3b3  ldarg.0
0x7e3b4  ldc.i4.m1
0x7e3b5  dup
0x7e3b6  stloc.0
0x7e3b7  stfld    int32 <SelectExtensionsAsync>d__15::<>1__state
0x7e3bc  ldloca.s 6
0x7e3be  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::GetResult()
0x7e3c3  stloc.s  4
0x7e3c5  ldarg.0
0x7e3c6  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <SelectExtensionsAsync>d__15::<perMachineFailedExtensions>5__3
0x7e3cb  ldloc.s  4
0x7e3cd  call     T0x2B0002EE
0x7e3d2  stloc.2
0x7e3d3  leave.s  loc_7E3FC
0x7e3d5  stloc.s  8
0x7e3d7  ldarg.0
0x7e3d8  ldc.i4.s 0xFE
0x7e3da  stfld    int32 <SelectExtensionsAsync>d__15::<>1__state
0x7e3df  ldarg.0
0x7e3e0  ldnull
0x7e3e1  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductModel <SelectExtensionsAsync>d__15::<migrateFromProduct>5__2
0x7e3e6  ldarg.0
0x7e3e7  ldnull
0x7e3e8  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <SelectExtensionsAsync>d__15::<perMachineFailedExtensions>5__3
0x7e3ed  ldarg.0
0x7e3ee  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <SelectExtensionsAsync>d__15::<>t__builder
0x7e3f3  ldloc.s  8
0x7e3f5  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::SetException(class [mscorlib]System.Exception)
0x7e3fa  leave.s  loc_7E41E
0x7e3fc  ldarg.0
0x7e3fd  ldc.i4.s 0xFE
0x7e3ff  stfld    int32 <SelectExtensionsAsync>d__15::<>1__state
0x7e404  ldarg.0
0x7e405  ldnull
0x7e406  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductModel <SelectExtensionsAsync>d__15::<migrateFromProduct>5__2
0x7e40b  ldarg.0
0x7e40c  ldnull
0x7e40d  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <SelectExtensionsAsync>d__15::<perMachineFailedExtensions>5__3
0x7e412  ldarg.0
0x7e413  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <SelectExtensionsAsync>d__15::<>t__builder
0x7e418  ldloc.2
0x7e419  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::SetResult(var<u1>)
0x7e41e  ret
```
