# <SelectPerMachineExtensionsAsync>d__20::MoveNext

- ea: `0x7ebd0`
- end: `0x7edd3`
- name: `<SelectPerMachineExtensionsAsync>d__20::MoveNext`
- size: `515`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x2b950`
- `0x43d80`
- `0x43db0`
- `0x43f10`
- `0x43f50`
- `0x7ebd0`

## string_xrefs

- `0x7ec53`: `Found {0} in-catalog and {1} per-machine extensions to select from.`
- `0x7ed83`: `Failed to clone extensions: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7ebd0  ldarg.0
0x7ebd1  ldfld    int32 <SelectPerMachineExtensionsAsync>d__20::<>1__state
0x7ebd6  stloc.0
0x7ebd7  ldarg.0
0x7ebd8  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer <SelectPerMachineExtensionsAsync>d__20::<>4__this
0x7ebdd  stloc.1
0x7ebde  ldloc.0
0x7ebdf  ldc.i4.1
0x7ebe0  pop
0x7ebe1  pop
0x7ebe2  nop
0x7ebe3  ldloc.0
0x7ebe4  brfalse  loc_7ECC9
0x7ebe9  ldloc.0
0x7ebea  ldc.i4.1
0x7ebeb  beq      loc_7ED43
0x7ebf0  ldloc.1
0x7ebf1  ldarg.0
0x7ebf2  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductModel <SelectPerMachineExtensionsAsync>d__20::migrateFromProduct
0x7ebf7  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel> Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::GetInstalledPerMachineExtensions(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductModel migrateFromProduct)
0x7ebfc  stloc.3
0x7ebfd  ldloc.3
0x7ebfe  call     T0x2B00004B
0x7ec03  brtrue.s loc_7EC10
0x7ec05  call     T0x2B000032
0x7ec0a  stloc.2
0x7ec0b  leave    loc_7EDBE
0x7ec10  ldloc.1
0x7ec11  ldarg.0
0x7ec12  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <SelectPerMachineExtensionsAsync>d__20::product
0x7ec17  ldloc.3
0x7ec18  call     instance valuetype [mscorlib]System.ValueTuple`3<class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel>, class [mscorlib]System.Collections.Generic.List`1<string>, class [mscorlib]System.Collections.Generic.List`1<string>> Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::PartitionExtensions(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel> product)
0x7ec1d  stloc.s  5
0x7ec1f  ldloc.s  5
0x7ec21  ldfld    var<u1> valuetype [mscorlib]System.ValueTuple`3<class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel>, class [mscorlib]System.Collections.Generic.List`1<string>, class [mscorlib]System.Collections.Generic.List`1<string>>::Item1
0x7ec26  stloc.s  4
0x7ec28  ldarg.0
0x7ec29  ldloc.s  5
0x7ec2b  ldfld    var<u1> valuetype [mscorlib]System.ValueTuple`3<class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel>, class [mscorlib]System.Collections.Generic.List`1<string>, class [mscorlib]System.Collections.Generic.List`1<string>>::Item2
0x7ec30  stfld    class [mscorlib]System.Collections.Generic.List`1<string> <SelectPerMachineExtensionsAsync>d__20::<vsixIdsToQuery>5__2
0x7ec35  ldarg.0
0x7ec36  ldloc.s  5
0x7ec38  ldfld    var<u1> valuetype [mscorlib]System.ValueTuple`3<class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel>, class [mscorlib]System.Collections.Generic.List`1<string>, class [mscorlib]System.Collections.Generic.List`1<string>>::Item3
0x7ec3d  stfld    class [mscorlib]System.Collections.Generic.List`1<string> <SelectPerMachineExtensionsAsync>d__20::<failedExtensionPacks>5__3
0x7ec42  ldloc.1
0x7ec43  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::serviceOptions
0x7ec48  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions::get_Logger()
0x7ec4d  dup
0x7ec4e  brtrue.s loc_7EC53
0x7ec50  pop
0x7ec51  br.s     loc_7EC83
0x7ec53  ldstr    aFound0InCatalo// "Found {0} in-catalog and {1} per-machin"...
0x7ec58  ldloc.s  4
0x7ec5a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel>::get_Count()
0x7ec5f  box      [mscorlib]System.Int32
0x7ec64  ldarg.0
0x7ec65  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <SelectPerMachineExtensionsAsync>d__20::<vsixIdsToQuery>5__2
0x7ec6a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x7ec6f  box      [mscorlib]System.Int32
0x7ec74  call     string [mscorlib]System.String::Format(string, object, object)
0x7ec79  call     T0x2B000010
0x7ec7e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7ec83  ldloc.1
0x7ec84  ldloc.s  4
0x7ec86  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::SelectInCatalogExtensionsAsync(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel> inCatalogExtensions)
0x7ec8b  ldc.i4.0
0x7ec8c  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x7ec91  stloc.s  7
0x7ec93  ldloca.s 7
0x7ec95  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x7ec9a  stloc.s  6
0x7ec9c  ldloca.s 6
0x7ec9e  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x7eca3  brtrue.s loc_7ECE6
0x7eca5  ldarg.0
0x7eca6  ldc.i4.0
0x7eca7  dup
0x7eca8  stloc.0
0x7eca9  stfld    int32 <SelectPerMachineExtensionsAsync>d__20::<>1__state
0x7ecae  ldarg.0
0x7ecaf  ldloc.s  6
0x7ecb1  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SelectPerMachineExtensionsAsync>d__20::<>u__1
0x7ecb6  ldarg.0
0x7ecb7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <SelectPerMachineExtensionsAsync>d__20::<>t__builder
0x7ecbc  ldloca.s 6
0x7ecbe  ldarg.0
0x7ecbf  call     T0x2B000542
0x7ecc4  leave    loc_7EDD2
0x7ecc9  ldarg.0
0x7ecca  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SelectPerMachineExtensionsAsync>d__20::<>u__1
0x7eccf  stloc.s  6
0x7ecd1  ldarg.0
0x7ecd2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SelectPerMachineExtensionsAsync>d__20::<>u__1
0x7ecd7  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x7ecdd  ldarg.0
0x7ecde  ldc.i4.m1
0x7ecdf  dup
0x7ece0  stloc.0
0x7ece1  stfld    int32 <SelectPerMachineExtensionsAsync>d__20::<>1__state
0x7ece6  ldloca.s 6
0x7ece8  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x7eced  ldloc.1
0x7ecee  ldarg.0
0x7ecef  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <SelectPerMachineExtensionsAsync>d__20::product
0x7ecf4  ldarg.0
0x7ecf5  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <SelectPerMachineExtensionsAsync>d__20::<vsixIdsToQuery>5__2
0x7ecfa  ldarg.0
0x7ecfb  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <SelectPerMachineExtensionsAsync>d__20::cancellationToken
0x7ed00  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::SelectMarketplaceExtensionsFromVsixIdsAsync(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel product, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> vsixIds, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x7ed05  ldc.i4.0
0x7ed06  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x7ed0b  stloc.s  7
0x7ed0d  ldloca.s 7
0x7ed0f  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x7ed14  stloc.s  6
0x7ed16  ldloca.s 6
0x7ed18  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x7ed1d  brtrue.s loc_7ED60
0x7ed1f  ldarg.0
0x7ed20  ldc.i4.1
0x7ed21  dup
0x7ed22  stloc.0
0x7ed23  stfld    int32 <SelectPerMachineExtensionsAsync>d__20::<>1__state
0x7ed28  ldarg.0
0x7ed29  ldloc.s  6
0x7ed2b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SelectPerMachineExtensionsAsync>d__20::<>u__1
0x7ed30  ldarg.0
0x7ed31  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <SelectPerMachineExtensionsAsync>d__20::<>t__builder
0x7ed36  ldloca.s 6
0x7ed38  ldarg.0
0x7ed39  call     T0x2B000542
0x7ed3e  leave    loc_7EDD2
0x7ed43  ldarg.0
0x7ed44  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SelectPerMachineExtensionsAsync>d__20::<>u__1
0x7ed49  stloc.s  6
0x7ed4b  ldarg.0
0x7ed4c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SelectPerMachineExtensionsAsync>d__20::<>u__1
0x7ed51  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x7ed57  ldarg.0
0x7ed58  ldc.i4.m1
0x7ed59  dup
0x7ed5a  stloc.0
0x7ed5b  stfld    int32 <SelectPerMachineExtensionsAsync>d__20::<>1__state
0x7ed60  ldloca.s 6
0x7ed62  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x7ed67  ldarg.0
0x7ed68  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <SelectPerMachineExtensionsAsync>d__20::<failedExtensionPacks>5__3
0x7ed6d  stloc.2
0x7ed6e  leave.s  loc_7EDBE
0x7ed70  stloc.s  8
0x7ed72  ldloc.1
0x7ed73  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::serviceOptions
0x7ed78  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions::get_Logger()
0x7ed7d  dup
0x7ed7e  brtrue.s loc_7ED83
0x7ed80  pop
0x7ed81  br.s     loc_7ED9D
0x7ed83  ldstr    aFailedToCloneE// "Failed to clone extensions: {0}"
0x7ed88  ldc.i4.1
0x7ed89  newarr   [mscorlib]System.Object
0x7ed8e  dup
0x7ed8f  ldc.i4.0
0x7ed90  ldloc.s  8
0x7ed92  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7ed97  stelem.ref
0x7ed98  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x7ed9d  call     T0x2B000032
0x7eda2  stloc.2
0x7eda3  leave.s  loc_7EDBE
0x7eda5  stloc.s  9
0x7eda7  ldarg.0
0x7eda8  ldc.i4.s 0xFE
0x7edaa  stfld    int32 <SelectPerMachineExtensionsAsync>d__20::<>1__state
0x7edaf  ldarg.0
0x7edb0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <SelectPerMachineExtensionsAsync>d__20::<>t__builder
0x7edb5  ldloc.s  9
0x7edb7  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::SetException(class [mscorlib]System.Exception)
0x7edbc  leave.s  loc_7EDD2
0x7edbe  ldarg.0
0x7edbf  ldc.i4.s 0xFE
0x7edc1  stfld    int32 <SelectPerMachineExtensionsAsync>d__20::<>1__state
0x7edc6  ldarg.0
0x7edc7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <SelectPerMachineExtensionsAsync>d__20::<>t__builder
0x7edcc  ldloc.2
0x7edcd  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::SetResult(var<u1>)
0x7edd2  ret
```
