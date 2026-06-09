# Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::TryReuseDuplicateExtension

- ea: `0x20390`
- end: `0x204d6`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::TryReuseDuplicateExtension`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x6e680`

## callees

- `0x9cc0`
- `0x20390`
- `0x204e0`
- `0x2bcb0`
- `0x37980`
- `0x37a10`
- `0x3b610`
- `0x6c7f0`
- `0x6c830`
- `0x6c890`
- `0x6cbf0`
- `0x6d230`

## string_xrefs

- `0x20465`: `Reused duplicate extension (pack/explicit) for '{0}': {1}.`
- `0x204b5`: `Reusing duplicated extension failed for {0}: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x20390  newobj   instance void <>c__DisplayClass9_0::.ctor()
0x20395  stloc.0
0x20396  ldloc.0
0x20397  ldarg.2
0x20398  callvirt instance class [System]System.Collections.Generic.ISet`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity> ExtensionContentsSummary::get_ParsedComponents()
0x2039d  stfld    class [System]System.Collections.Generic.ISet`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity> <>c__DisplayClass9_0::parsedComponents
0x203a2  ldloc.0
0x203a3  ldloc.0
0x203a4  ldfld    class [System]System.Collections.Generic.ISet`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity> <>c__DisplayClass9_0::parsedComponents
0x203a9  dup
0x203aa  brtrue.s loc_203B0
0x203ac  pop
0x203ad  ldnull
0x203ae  br.s     loc_203FD
0x203b0  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, string> <>c::<>9__9_0
0x203b5  dup
0x203b6  brtrue.s loc_203CF
0x203b8  pop
0x203b9  ldsfld   class <>c <>c::<>9
0x203be  ldftn    instance string <>c::<TryReuseDuplicateExtension>b__9_0(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity c)
0x203c4  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, string>::.ctor(object, native int)
0x203c9  dup
0x203ca  stsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, string> <>c::<>9__9_0
0x203cf  call     T0x2B000121
0x203d4  ldsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__9_1
0x203d9  dup
0x203da  brtrue.s loc_203F3
0x203dc  pop
0x203dd  ldsfld   class <>c <>c::<>9
0x203e2  ldftn    instance bool <>c::<TryReuseDuplicateExtension>b__9_1(string id)
0x203e8  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x203ed  dup
0x203ee  stsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__9_1
0x203f3  call     T0x2B0000C3
0x203f8  call     T0x2B000122
0x203fd  dup
0x203fe  brtrue.s loc_20406
0x20400  pop
0x20401  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x20406  stfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass9_0::candidateIds
0x2040b  ldloc.0
0x2040c  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass9_0::candidateIds
0x20411  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x20416  brtrue.s loc_2041F
0x20418  ldnull
0x20419  stloc.2
0x2041a  leave    loc_204D4
0x2041f  ldarg.3
0x20420  callvirt instance class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel> Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel::get_Extensions()
0x20425  ldloc.0
0x20426  ldftn    instance bool <>c__DisplayClass9_0::<TryReuseDuplicateExtension>b__2(class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel e)
0x2042c  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel, bool>::.ctor(object, native int)
0x20431  call     T0x2B000123
0x20436  stloc.1
0x20437  ldloc.1
0x20438  brtrue.s loc_20441
0x2043a  ldnull
0x2043b  stloc.2
0x2043c  leave    loc_204D4
0x20441  ldarg.s  5
0x20443  brtrue.s loc_20454
0x20445  ldloc.1
0x20446  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel::get_AutomaticallyAddedByExtensionPack()
0x2044b  brfalse.s loc_20454
0x2044d  ldarg.0
0x2044e  ldloc.1
0x2044f  call     instance void Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::TryFlipPackFlagOff(class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel existingModel)
0x20454  ldarg.0
0x20455  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x2045a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Logger()
0x2045f  dup
0x20460  brtrue.s loc_20465
0x20462  pop
0x20463  br.s     loc_20480
0x20465  ldstr    aReusedDuplicat// "Reused duplicate extension (pack/explic"...
0x2046a  ldloc.1
0x2046b  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IUISelectableModel::get_Id()
0x20470  ldarg.1
0x20471  call     string [mscorlib]System.String::Format(string, object, object)
0x20476  call     T0x2B000010
0x2047b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x20480  ldarg.2
0x20481  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents ExtensionContentsSummary::get_ExtensionContents()
0x20486  ldloc.1
0x20487  ldarg.1
0x20488  callvirt instance string [System]System.Uri::get_OriginalString()
0x2048d  ldc.i4.0
0x2048e  ldarg.s  4
0x20490  ldarg.2
0x20491  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult ExtensionContentsSummary::get_VerificationResult()
0x20496  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary::.ctor(class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel Model, string ExtensionNameOrUri, valuetype Microsoft.VisualStudio.Setup.Installer.ExtensionModelErrorState ErrorState, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionOrigin Origin, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult VerificationResult)
0x2049b  newobj   instance void ExtensionModelContentSummary::.ctor(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents ExtensionContents, class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary ExtensionModelSummary)
0x204a0  stloc.2
0x204a1  leave.s  loc_204D4
0x204a3  stloc.3
0x204a4  ldarg.0
0x204a5  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x204aa  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Logger()
0x204af  dup
0x204b0  brtrue.s loc_204B5
0x204b2  pop
0x204b3  br.s     loc_204D0
0x204b5  ldstr    aReusingDuplica// "Reusing duplicated extension failed for"...
0x204ba  ldarg.1
0x204bb  ldloc.3
0x204bc  callvirt instance string [mscorlib]System.Exception::get_Message()
0x204c1  call     string [mscorlib]System.String::Format(string, object, object)
0x204c6  call     T0x2B000010
0x204cb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x204d0  ldnull
0x204d1  stloc.2
0x204d2  leave.s  loc_204D4
0x204d4  ldloc.2
0x204d5  ret
```
