# <SelectPackagesAsync>d__21::MoveNext

- ea: `0x79bb0`
- end: `0x7a731`
- name: `<SelectPackagesAsync>d__21::MoveNext`
- size: `2945`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, registry_config`

## callees

- `0x36c40`
- `0x36c60`
- `0x36c70`
- `0x36ca0`
- `0x36cc0`
- `0x36ce0`
- `0x37a90`
- `0x37ad0`
- `0x37ae0`
- `0x3b5f0`
- `0x3b600`
- `0x3b610`
- `0x3d220`
- `0x3d290`
- `0x3d300`
- `0x3d430`
- `0x3d540`
- `0x3d580`
- `0x3d5a0`
- `0x78e40`
- `0x79bb0`

## string_xrefs

- `0x7a33b`: `Adding packages from vsconfig`
- `0x7a5bb`: `Removing packages from --remove`

## pseudocode

```c

```

## disassembly

```asm
0x79bb0  ldarg.0
0x79bb1  ldfld    int32 <SelectPackagesAsync>d__21::<>1__state
0x79bb6  stloc.0
0x79bb7  ldloc.0
0x79bb8  switch   loc_79C91, loc_79DA9, loc_79FEC, loc_7A0FE, loc_7A397, loc_7A478, loc_7A668
0x79bd9  ldarg.0
0x79bda  ldarg.0
0x79bdb  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <SelectPackagesAsync>d__21::product
0x79be0  callvirt instance class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel> Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel::get_Workloads()
0x79be5  stfld    class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel> <SelectPackagesAsync>d__21::<workloads>5__2
0x79bea  ldarg.0
0x79beb  ldarg.0
0x79bec  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <SelectPackagesAsync>d__21::product
0x79bf1  callvirt instance class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel> Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel::get_Components()
0x79bf6  stfld    class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel> <SelectPackagesAsync>d__21::<components>5__3
0x79bfb  ldarg.0
0x79bfc  ldarg.0
0x79bfd  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <SelectPackagesAsync>d__21::product
0x79c02  callvirt instance class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel> Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel::get_Extensions()
0x79c07  stfld    class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel> <SelectPackagesAsync>d__21::<extensions>5__4
0x79c0c  ldarg.0
0x79c0d  ldsfld   class [mscorlib]System.Collections.Generic.IEqualityComparer`1<valuetype Microsoft.VisualStudio.Setup.Installer.Models.PackageWithSelection> Microsoft.VisualStudio.Setup.Installer.Models.PackageWithSelectionComparer::Default
0x79c12  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.VisualStudio.Setup.Installer.Models.PackageWithSelection>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x79c17  stfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.VisualStudio.Setup.Installer.Models.PackageWithSelection> <SelectPackagesAsync>d__21::<selectedPackages>5__5
0x79c1c  ldarg.0
0x79c1d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x79c22  stfld    class [mscorlib]System.Collections.Generic.List`1<string> <SelectPackagesAsync>d__21::<failedPackages>5__6
0x79c27  ldarg.0
0x79c28  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <SelectPackagesAsync>d__21::<failedPackages>5__6
0x79c2d  ldarg.0
0x79c2e  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionRecords <SelectPackagesAsync>d__21::extensionRecords
0x79c33  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionOrigin> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionRecords::get_UnknownExtensions()
0x79c38  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>> class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionOrigin>::get_Keys()
0x79c3d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x79c42  ldarg.0
0x79c43  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <SelectPackagesAsync>d__21::product
0x79c48  ldarg.0
0x79c49  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionRecords <SelectPackagesAsync>d__21::extensionRecords
0x79c4e  call     class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>> Microsoft.VisualStudio.Setup.Installer.Utilities.CommandLineUtilities::SelectExtensionsAsync(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel product, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionRecords extensions)
0x79c53  ldc.i4.0
0x79c54  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>>::ConfigureAwait(!!T0)
0x79c59  stloc.s  5
0x79c5b  ldloca.s 5
0x79c5d  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>>::GetAwaiter()
0x79c62  stloc.s  4
0x79c64  ldloca.s 4
0x79c66  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>>::get_IsCompleted()
0x79c6b  brtrue.s loc_79CAE
0x79c6d  ldarg.0
0x79c6e  ldc.i4.0
0x79c6f  dup
0x79c70  stloc.0
0x79c71  stfld    int32 <SelectPackagesAsync>d__21::<>1__state
0x79c76  ldarg.0
0x79c77  ldloc.s  4
0x79c79  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>> <SelectPackagesAsync>d__21::<>u__1
0x79c7e  ldarg.0
0x79c7f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.Installer.Models.PackageSelectionResults> <SelectPackagesAsync>d__21::<>t__builder
0x79c84  ldloca.s 4
0x79c86  ldarg.0
0x79c87  call     T0x2B000500
0x79c8c  leave    loc_7A730
0x79c91  ldarg.0
0x79c92  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>> <SelectPackagesAsync>d__21::<>u__1
0x79c97  stloc.s  4
0x79c99  ldarg.0
0x79c9a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>> <SelectPackagesAsync>d__21::<>u__1
0x79c9f  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>>
0x79ca5  ldarg.0
0x79ca6  ldc.i4.m1
0x79ca7  dup
0x79ca8  stloc.0
0x79ca9  stfld    int32 <SelectPackagesAsync>d__21::<>1__state
0x79cae  ldloca.s 4
0x79cb0  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary>>::GetResult()
0x79cb5  stloc.2
0x79cb6  ldarg.0
0x79cb7  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.VisualStudio.Setup.Installer.Models.PackageWithSelection> <SelectPackagesAsync>d__21::<selectedPackages>5__5
0x79cbc  ldloc.2
0x79cbd  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary, bool> <>c::<>9__21_0
0x79cc2  dup
0x79cc3  brtrue.s loc_79CDC
0x79cc5  pop
0x79cc6  ldsfld   class <>c <>c::<>9
0x79ccb  ldftn    instance bool <>c::<SelectPackagesAsync>b__21_0(class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary x)
0x79cd1  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary, bool>::.ctor(object, native int)
0x79cd6  dup
0x79cd7  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary, bool> <>c::<>9__21_0
0x79cdc  call     T0x2B000501
0x79ce1  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary, valuetype Microsoft.VisualStudio.Setup.Installer.Models.PackageWithSelection> <>c::<>9__21_1
0x79ce6  dup
0x79ce7  brtrue.s loc_79D00
0x79ce9  pop
0x79cea  ldsfld   class <>c <>c::<>9
0x79cef  ldftn    instance valuetype Microsoft.VisualStudio.Setup.Installer.Models.PackageWithSelection <>c::<SelectPackagesAsync>b__21_1(class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary x)
0x79cf5  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary, valuetype Microsoft.VisualStudio.Setup.Installer.Models.PackageWithSelection>::.ctor(object, native int)
0x79cfa  dup
0x79cfb  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary, valuetype Microsoft.VisualStudio.Setup.Installer.Models.PackageWithSelection> <>c::<>9__21_1
0x79d00  call     T0x2B000502
0x79d05  call     T0x2B000503
0x79d0a  ldarg.0
0x79d0b  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <SelectPackagesAsync>d__21::<failedPackages>5__6
0x79d10  ldloc.2
0x79d11  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary, bool> <>c::<>9__21_2
0x79d16  dup
0x79d17  brtrue.s loc_79D30
0x79d19  pop
0x79d1a  ldsfld   class <>c <>c::<>9
0x79d1f  ldftn    instance bool <>c::<SelectPackagesAsync>b__21_2(class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary x)
0x79d25  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary, bool>::.ctor(object, native int)
0x79d2a  dup
0x79d2b  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary, bool> <>c::<>9__21_2
0x79d30  call     T0x2B000501
0x79d35  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary, string> <>c::<>9__21_3
0x79d3a  dup
0x79d3b  brtrue.s loc_79D54
0x79d3d  pop
0x79d3e  ldsfld   class <>c <>c::<>9
0x79d43  ldftn    instance string <>c::<SelectPackagesAsync>b__21_3(class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary x)
0x79d49  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary, string>::.ctor(object, native int)
0x79d4e  dup
0x79d4f  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary, string> <>c::<>9__21_3
0x79d54  call     T0x2B000504
0x79d59  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x79d5e  ldarg.0
0x79d5f  ldfld    bool <SelectPackagesAsync>d__21::all
0x79d64  ldarg.0
0x79d65  ldfld    bool <SelectPackagesAsync>d__21::allWorkloads
0x79d6a  or
0x79d6b  brfalse  loc_79EC5
0x79d70  ldarg.0
0x79d71  ldfld    class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel> <SelectPackagesAsync>d__21::<workloads>5__2
0x79d76  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel, bool> <>c::<>9__21_8
0x79d7b  dup
0x79d7c  brtrue.s loc_79D95
0x79d7e  pop
0x79d7f  ldsfld   class <>c <>c::<>9
0x79d84  ldftn    instance bool <>c::<SelectPackagesAsync>b__21_8(class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel x)
0x79d8a  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel, bool>::.ctor(object, native int)
0x79d8f  dup
0x79d90  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel, bool> <>c::<>9__21_8
0x79d95  call     T0x2B000252
0x79d9a  stloc.s  6
0x79d9c  ldarg.0
0x79d9d  ldloc.s  6
0x79d9f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel>::GetEnumerator()
0x79da4  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel> <SelectPackagesAsync>d__21::<>7__wrap8
0x79da9  nop
0x79daa  ldloc.0
0x79dab  ldc.i4.1
0x79dac  beq.s    loc_79E2C
0x79dae  br       loc_79E94
0x79db3  ldarg.0
0x79db4  ldarg.0
0x79db5  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel> <SelectPackagesAsync>d__21::<>7__wrap8
0x79dba  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel>::get_Current()
0x79dbf  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel <SelectPackagesAsync>d__21::<workload>5__10
0x79dc4  ldarg.0
0x79dc5  ldarg.0
0x79dc6  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel <SelectPackagesAsync>d__21::<workload>5__10
0x79dcb  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IUISelectableModel::get_IsRequired()
0x79dd0  ldc.i4.0
0x79dd1  ceq
0x79dd3  ldarg.0
0x79dd4  ldfld    bool <SelectPackagesAsync>d__21::includeOptional
0x79dd9  and
0x79dda  stfld    bool <SelectPackagesAsync>d__21::<resolvedIncludeOptional>5__11
0x79ddf  ldarg.0
0x79de0  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel <SelectPackagesAsync>d__21::<workload>5__10
0x79de5  ldc.i4.2
0x79de6  ldarg.0
0x79de7  ldfld    bool <SelectPackagesAsync>d__21::includeRecommended
0x79dec  ldarg.0
0x79ded  ldfld    bool <SelectPackagesAsync>d__21::<resolvedIncludeOptional>5__11
0x79df2  ldnull
0x79df3  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IUISelectableModel::SelectAsync(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState newState, bool includeRecommended, bool includeOptional, [opt] class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> additionalTelemetryProperties)
0x79df8  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x79dfd  stloc.s  7
0x79dff  ldloca.s 7
0x79e01  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x79e06  brtrue.s loc_79E49
0x79e08  ldarg.0
0x79e09  ldc.i4.1
0x79e0a  dup
0x79e0b  stloc.0
0x79e0c  stfld    int32 <SelectPackagesAsync>d__21::<>1__state
0x79e11  ldarg.0
0x79e12  ldloc.s  7
0x79e14  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SelectPackagesAsync>d__21::<>u__2
0x79e19  ldarg.0
0x79e1a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.Installer.Models.PackageSelectionResults> <SelectPackagesAsync>d__21::<>t__builder
0x79e1f  ldloca.s 7
0x79e21  ldarg.0
0x79e22  call     T0x2B000505
0x79e27  leave    loc_7A730
0x79e2c  ldarg.0
0x79e2d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SelectPackagesAsync>d__21::<>u__2
0x79e32  stloc.s  7
0x79e34  ldarg.0
0x79e35  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SelectPackagesAsync>d__21::<>u__2
0x79e3a  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x79e40  ldarg.0
0x79e41  ldc.i4.m1
0x79e42  dup
0x79e43  stloc.0
0x79e44  stfld    int32 <SelectPackagesAsync>d__21::<>1__state
0x79e49  ldloca.s 7
0x79e4b  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x79e50  ldarg.0
0x79e51  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.VisualStudio.Setup.Installer.Models.PackageWithSelection> <SelectPackagesAsync>d__21::<selectedPackages>5__5
0x79e56  ldloca.s 8
0x79e58  initobj  Microsoft.VisualStudio.Setup.Installer.Models.PackageWithSelection
0x79e5e  ldloca.s 8
0x79e60  ldarg.0
0x79e61  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel <SelectPackagesAsync>d__21::<workload>5__10
0x79e66  call     instance void Microsoft.VisualStudio.Setup.Installer.Models.PackageWithSelection::set_Model(class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IUISelectableModel value)
0x79e6b  ldloca.s 8
0x79e6d  ldarg.0
0x79e6e  ldfld    bool <SelectPackagesAsync>d__21::includeRecommended
0x79e73  call     instance void Microsoft.VisualStudio.Setup.Installer.Models.PackageWithSelection::set_IncludeRecommended(bool value)
0x79e78  ldloca.s 8
0x79e7a  ldarg.0
0x79e7b  ldfld    bool <SelectPackagesAsync>d__21::<resolvedIncludeOptional>5__11
0x79e80  call     instance void Microsoft.VisualStudio.Setup.Installer.Models.PackageWithSelection::set_IncludeOptional(bool value)
0x79e85  ldloc.s  8
0x79e87  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.VisualStudio.Setup.Installer.Models.PackageWithSelection>::Add(var<u1>)
0x79e8c  pop
0x79e8d  ldarg.0
0x79e8e  ldnull
0x79e8f  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel <SelectPackagesAsync>d__21::<workload>5__10
0x79e94  ldarg.0
0x79e95  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel> <SelectPackagesAsync>d__21::<>7__wrap8
0x79e9a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x79e9f  brtrue   loc_79DB3
0x79ea4  leave.s  loc_79EBE
0x79ea6  ldloc.0
0x79ea7  ldc.i4.0
0x79ea8  bge.s    loc_79EBD
0x79eaa  ldarg.0
0x79eab  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel> <SelectPackagesAsync>d__21::<>7__wrap8
0x79eb0  brfalse.s loc_79EBD
0x79eb2  ldarg.0
0x79eb3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel> <SelectPackagesAsync>d__21::<>7__wrap8
0x79eb8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x79ebd  endfinally
0x79ebe  ldarg.0
0x79ebf  ldnull
0x79ec0  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel> <SelectPackagesAsync>d__21::<>7__wrap8
0x79ec5  ldarg.0
0x79ec6  ldfld    bool <SelectPackagesAsync>d__21::all
0x79ecb  brfalse  loc_7A1FC
0x79ed0  newobj   instance void <>c__DisplayClass21_0::.ctor()
0x79ed5  stloc.s  9
0x79ed7  ldarg.0
0x79ed8  ldfld    class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel> <SelectPackagesAsync>d__21::<workloads>5__2
0x79edd  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel, bool> <>c::<>9__21_9
0x79ee2  dup
0x79ee3  brtrue.s loc_79EFC
0x79ee5  pop
0x79ee6  ldsfld   class <>c <>c::<>9
0x79eeb  ldftn    instance bool <>c::<SelectPackagesAsync>b__21_9(class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel x)
0x79ef1  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel, bool>::.ctor(object, native int)
0x79ef6  dup
0x79ef7  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel, bool> <>c::<>9__21_9
0x79efc  call     T0x2B000252
0x79f01  ldloc.s  9
0x79f03  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x79f08  stfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass21_0::specialHiddenComponents
0x79f0d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel>::GetEnumerator()
0x79f12  stloc.s  0xB
0x79f14  br.s     loc_79F7A
0x79f16  ldloc.s  0xB
0x79f18  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IWorkloadModel>::get_Current()
0x79f1d  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.DependencyType> Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IUISelectableModel::get_ComponentDependencies()
0x79f22  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.DependencyType>, bool> <>c::<>9__21_12
0x79f27  dup
0x79f28  brtrue.s loc_79F41
0x79f2a  pop
0x79f2b  ldsfld   class <>c <>c::<>9
0x79f30  ldftn    instance bool <>c::<SelectPackagesAsync>b__21_12(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.DependencyType> x)
0x79f36  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.DependencyType>, bool>::.ctor(object, native int)
0x79f3b  dup
0x79f3c  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.DependencyType>, bool> <>c::<>9__21_12
0x79f41  call     T0x2B000506
0x79f46  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.DependencyType>, string> <>c::<>9__21_13
0x79f4b  dup
0x79f4c  brtrue.s loc_79F65
0x79f4e  pop
0x79f4f  ldsfld   class <>c <>c::<>9
0x79f54  ldftn    instance string <>c::<SelectPackagesAsync>b__21_13(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.DependencyType> x)
0x79f5a  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.DependencyType>, string>::.ctor(object, native int)
0x79f5f  dup
0x79f60  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.DependencyType>, string> <>c::<>9__21_13
0x79f65  call     T0x2B000507
0x79f6a  stloc.s  0xC
0x79f6c  ldloc.s  9
0x79f6e  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass21_0::specialHiddenComponents
0x79f73  ldloc.s  0xC
0x79f75  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x79f7a  ldloc.s  0xB
  ... truncated ...
```
