# Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::PartitionExtensions

- ea: `0x43db0`
- end: `0x43f0e`
- name: `Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::PartitionExtensions`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x7ebd0`

## callees

- `0x2b950`
- `0x37950`
- `0x37990`
- `0x37a10`
- `0x37a20`
- `0x3b5f0`
- `0x43db0`
- `0x7de40`

## string_xrefs

- `0x43e4b`: `Skipping extension pack `

## pseudocode

```c

```

## disassembly

```asm
0x43db0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel>::.ctor()
0x43db5  stloc.0
0x43db6  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x43dbb  stloc.1
0x43dbc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x43dc1  stloc.2
0x43dc2  ldarg.2
0x43dc3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel>::GetEnumerator()
0x43dc8  stloc.3
0x43dc9  br       loc_43EEE
0x43dce  newobj   instance void <>c__DisplayClass22_0::.ctor()
0x43dd3  stloc.s  4
0x43dd5  ldloc.s  4
0x43dd7  ldloc.3
0x43dd8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel>::get_Current()
0x43ddd  stfld    class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel <>c__DisplayClass22_0::extension
0x43de2  ldarg.0
0x43de3  ldfld    bool Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::includeExtensionPacks
0x43de8  brtrue   loc_43E8E
0x43ded  ldloc.s  4
0x43def  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel <>c__DisplayClass22_0::extension
0x43df4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel::get_PackedExtensions()
0x43df9  call     T0x2B00002F
0x43dfe  brtrue   loc_43E8E
0x43e03  ldloc.s  4
0x43e05  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel <>c__DisplayClass22_0::extension
0x43e0a  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IUISelectableModel::get_Name()
0x43e0f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x43e14  brfalse.s loc_43E24
0x43e16  ldloc.s  4
0x43e18  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel <>c__DisplayClass22_0::extension
0x43e1d  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IUISelectableModel::get_Id()
0x43e22  br.s     loc_43E30
0x43e24  ldloc.s  4
0x43e26  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel <>c__DisplayClass22_0::extension
0x43e2b  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IUISelectableModel::get_Name()
0x43e30  stloc.s  6
0x43e32  ldarg.0
0x43e33  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::serviceOptions
0x43e38  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CloneSelectionServiceOptions::get_Logger()
0x43e3d  dup
0x43e3e  brtrue.s loc_43E43
0x43e40  pop
0x43e41  br.s     loc_43E84
0x43e43  ldc.i4.5
0x43e44  newarr   [mscorlib]System.String
0x43e49  dup
0x43e4a  ldc.i4.0
0x43e4b  ldstr    aSkippingExtens// "Skipping extension pack "
0x43e50  stelem.ref
0x43e51  dup
0x43e52  ldc.i4.1
0x43e53  ldloc.s  6
0x43e55  stelem.ref
0x43e56  dup
0x43e57  ldc.i4.2
0x43e58  ldstr    asc_A3916// " ("
0x43e5d  stelem.ref
0x43e5e  dup
0x43e5f  ldc.i4.3
0x43e60  ldloc.s  4
0x43e62  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel <>c__DisplayClass22_0::extension
0x43e67  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IUISelectableModel::get_Id()
0x43e6c  stelem.ref
0x43e6d  dup
0x43e6e  ldc.i4.4
0x43e6f  ldstr    asc_A391C// ")."
0x43e74  stelem.ref
0x43e75  call     string [mscorlib]System.String::Concat(string[])
0x43e7a  call     T0x2B000010
0x43e7f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x43e84  ldloc.2
0x43e85  ldloc.s  6
0x43e87  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x43e8c  br.s     loc_43EEE
0x43e8e  ldarg.1
0x43e8f  callvirt instance class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel> Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel::get_Components()
0x43e94  ldloc.s  4
0x43e96  ldftn    instance bool <>c__DisplayClass22_0::<PartitionExtensions>b__0(class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel e)
0x43e9c  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel, bool>::.ctor(object, native int)
0x43ea1  call     T0x2B0002AD
0x43ea6  stloc.s  5
0x43ea8  ldloc.s  5
0x43eaa  brfalse.s loc_43EC9
0x43eac  ldsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.VisualStudio.Setup.Installer.InstallationDetails.CloneSelectionInitializer::BlockedIds
0x43eb1  ldloc.s  5
0x43eb3  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IUISelectableModel::get_Id()
0x43eb8  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0x43ebd  brtrue.s loc_43EC9
0x43ebf  ldloc.0
0x43ec0  ldloc.s  5
0x43ec2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel>::Add(var<u1>)
0x43ec7  br.s     loc_43EEE
0x43ec9  ldloc.s  4
0x43ecb  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel <>c__DisplayClass22_0::extension
0x43ed0  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel::get_VsixId()
0x43ed5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x43eda  brtrue.s loc_43EEE
0x43edc  ldloc.1
0x43edd  ldloc.s  4
0x43edf  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel <>c__DisplayClass22_0::extension
0x43ee4  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel::get_VsixId()
0x43ee9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x43eee  ldloc.3
0x43eef  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x43ef4  brtrue   loc_43DCE
0x43ef9  leave.s  loc_43F05
0x43efb  ldloc.3
0x43efc  brfalse.s loc_43F04
0x43efe  ldloc.3
0x43eff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x43f04  endfinally
0x43f05  ldloc.0
0x43f06  ldloc.1
0x43f07  ldloc.2
0x43f08  newobj   instance void valuetype [mscorlib]System.ValueTuple`3<class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel>, class [mscorlib]System.Collections.Generic.List`1<string>, class [mscorlib]System.Collections.Generic.List`1<string>>::.ctor(var<u1>, !!T0, var<u1>)
0x43f0d  ret
```
