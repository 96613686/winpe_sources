# Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::SetInstallerTelemetryContextProperties

- ea: `0xd630`
- end: `0xd8b8`
- name: `Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::SetInstallerTelemetryContextProperties`
- size: `648`
- prototype: ``
- caller_count: `2`
- callee_count: `29`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7b280`
- `0x7dac0`

## callees

- `0xd630`
- `0xdcc0`
- `0xdce0`
- `0xdd60`
- `0xddc0`
- `0xdde0`
- `0xde00`
- `0xde20`
- `0xde40`
- `0xde60`
- `0xde80`
- `0xdea0`
- `0xdec0`
- `0xdee0`
- `0xdf00`
- `0xdf20`
- `0xdf40`
- `0xdf60`
- `0xdf80`
- `0xdfa0`
- `0xdfc0`
- `0xdfe0`
- `0xe000`
- `0xe020`
- `0xe040`
- `0xe060`
- `0xe080`
- `0xe0a0`
- `0xe0c0`

## string_xrefs

- `0xd63a`: `install`

## pseudocode

```c

```

## disassembly

```asm
0xd630  ldarg.0
0xd631  brtrue.s loc_D634
0xd633  ret
0xd634  ldarg.0
0xd635  callvirt instance string Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_UserRequestedOperation()
0xd63a  ldstr    aInstall// "install"
0xd63f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd644  brfalse.s loc_D65C
0xd646  ldarg.1
0xd647  ldsfld   string ProductOperation::RejectRecommendedSelectionProperty
0xd64c  ldarg.0
0xd64d  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_RejectRecommendedSelection()
0xd652  box      [mscorlib]System.Boolean
0xd657  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd65c  ldarg.1
0xd65d  ldsfld   string ProductOperation::InstallSessionIdProperty
0xd662  ldarg.0
0xd663  callvirt instance string Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_InstallSessionId()
0xd668  dup
0xd669  brtrue.s loc_D671
0xd66b  pop
0xd66c  ldsfld   string [mscorlib]System.String::Empty
0xd671  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd676  ldarg.1
0xd677  ldsfld   string ProductOperation::FromImportProperty
0xd67c  ldarg.0
0xd67d  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_FromImport()
0xd682  box      [mscorlib]System.Boolean
0xd687  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd68c  ldarg.1
0xd68d  ldsfld   string ProductOperation::PackageCacheDriveProperty
0xd692  ldarg.0
0xd693  callvirt instance string Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_PackageCacheDrive()
0xd698  dup
0xd699  brtrue.s loc_D6A1
0xd69b  pop
0xd69c  ldsfld   string [mscorlib]System.String::Empty
0xd6a1  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd6a6  ldarg.1
0xd6a7  ldsfld   string ProductOperation::PackageCacheEnabledProperty
0xd6ac  ldarg.0
0xd6ad  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_PackageCacheEnabled()
0xd6b2  box      [mscorlib]System.Boolean
0xd6b7  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd6bc  ldarg.1
0xd6bd  ldsfld   string ProductOperation::PackageCachePathModifiedProperty
0xd6c2  ldarg.0
0xd6c3  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_PackageCachePathModified()
0xd6c8  box      [mscorlib]System.Boolean
0xd6cd  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd6d2  ldarg.1
0xd6d3  ldsfld   string ProductOperation::PackageCacheSettingModifiedProperty
0xd6d8  ldarg.0
0xd6d9  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_PackageCacheSettingModified()
0xd6de  box      [mscorlib]System.Boolean
0xd6e3  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd6e8  ldarg.1
0xd6e9  ldsfld   string ProductOperation::SharedInstallationDriveProperty
0xd6ee  ldarg.0
0xd6ef  callvirt instance string Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_SharedInstallationDrive()
0xd6f4  dup
0xd6f5  brtrue.s loc_D6FD
0xd6f7  pop
0xd6f8  ldsfld   string [mscorlib]System.String::Empty
0xd6fd  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd702  ldarg.1
0xd703  ldsfld   string ProductOperation::SharedInstallationPathModifiedProperty
0xd708  ldarg.0
0xd709  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_SharedInstallationPathModified()
0xd70e  box      [mscorlib]System.Boolean
0xd713  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd718  ldarg.1
0xd719  ldsfld   string ProductOperation::InstallationPathModifiedProperty
0xd71e  ldarg.0
0xd71f  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_InstallationPathModified()
0xd724  box      [mscorlib]System.Boolean
0xd729  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd72e  ldarg.1
0xd72f  ldsfld   string ProductOperation::SystemDriveProperty
0xd734  ldarg.0
0xd735  callvirt instance string Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_SystemDrive()
0xd73a  dup
0xd73b  brtrue.s loc_D743
0xd73d  pop
0xd73e  ldsfld   string [mscorlib]System.String::Empty
0xd743  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd748  ldarg.1
0xd749  ldsfld   string ProductOperation::TargetDriveProperty
0xd74e  ldarg.0
0xd74f  callvirt instance string Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_TargetDrive()
0xd754  dup
0xd755  brtrue.s loc_D75D
0xd757  pop
0xd758  ldsfld   string [mscorlib]System.String::Empty
0xd75d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd762  ldarg.1
0xd763  ldsfld   string ProductOperation::HasSSDProperty
0xd768  ldarg.0
0xd769  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_HasSSD()
0xd76e  box      [mscorlib]System.Boolean
0xd773  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd778  ldarg.1
0xd779  ldsfld   string ProductOperation::IsSystemDriveSSDProperty
0xd77e  ldarg.0
0xd77f  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_IsSystemDriveSSD()
0xd784  box      [mscorlib]System.Boolean
0xd789  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd78e  ldarg.1
0xd78f  ldsfld   string ProductOperation::IsTargetDriveSSDProperty
0xd794  ldarg.0
0xd795  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_IsTargetDriveSSD()
0xd79a  box      [mscorlib]System.Boolean
0xd79f  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd7a4  ldarg.1
0xd7a5  ldsfld   string ProductOperation::PreviewUpdateProperty
0xd7aa  ldarg.0
0xd7ab  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_PreviewUpdate()
0xd7b0  box      [mscorlib]System.Boolean
0xd7b5  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd7ba  ldarg.1
0xd7bb  ldsfld   string ProductOperation::FromFocusedUiProperty
0xd7c0  ldarg.0
0xd7c1  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_FromFocusedUi()
0xd7c6  box      [mscorlib]System.Boolean
0xd7cb  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd7d0  ldarg.1
0xd7d1  ldsfld   string ProductOperation::FromFocusedUiWithMissingPackagesProperty
0xd7d6  ldarg.0
0xd7d7  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_FromFocusedUiWithMissingPackages()
0xd7dc  box      [mscorlib]System.Boolean
0xd7e1  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd7e6  ldarg.1
0xd7e7  ldsfld   string ProductOperation::SelectedConfigPackageProperty
0xd7ec  ldarg.0
0xd7ed  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_SelectedConfigPackage()
0xd7f2  box      [mscorlib]System.Boolean
0xd7f7  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd7fc  ldarg.1
0xd7fd  ldsfld   string ProductOperation::SelectedMissingPackageProperty
0xd802  ldarg.0
0xd803  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_SelectedMissingPackage()
0xd808  box      [mscorlib]System.Boolean
0xd80d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd812  ldarg.1
0xd813  ldsfld   string ProductOperation::DidUserFilterComponents
0xd818  ldarg.0
0xd819  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_DidUserFilterComponents()
0xd81e  box      [mscorlib]System.Boolean
0xd823  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd828  ldarg.1
0xd829  ldsfld   string ProductOperation::DidUserSelectComponentFromFilteredList
0xd82e  ldarg.0
0xd82f  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_DidUserSelectComponentFromFilteredList()
0xd834  box      [mscorlib]System.Boolean
0xd839  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd83e  ldarg.1
0xd83f  ldsfld   string ProductOperation::InstallerServiceConnectionTypeProperty
0xd844  ldarg.0
0xd845  callvirt instance string Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_InstallerServiceConnectionType()
0xd84a  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd84f  ldarg.1
0xd850  ldsfld   string ProductOperation::IsFromAvailableTabProperty
0xd855  ldarg.0
0xd856  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_IsFromAvailableTab()
0xd85b  box      [mscorlib]System.Boolean
0xd860  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd865  ldarg.1
0xd866  ldsfld   string ProductOperation::SelectedAllPackagesProperty
0xd86b  ldarg.0
0xd86c  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_SelectedAllPackages()
0xd871  box      [mscorlib]System.Boolean
0xd876  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd87b  ldarg.0
0xd87c  callvirt instance string[] Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_SelectedAdvertisedComponentIds()
0xd881  brfalse.s loc_D89E
0xd883  ldarg.1
0xd884  ldsfld   string ProductOperation::SelectedAdvertisedComponentIdsProperty
0xd889  ldstr    asc_98B4C// ","
0xd88e  ldarg.0
0xd88f  callvirt instance string[] Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_SelectedAdvertisedComponentIds()
0xd894  call     string [mscorlib]System.String::Join(string, string[])
0xd899  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd89e  ldarg.0
0xd89f  callvirt instance string Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_RemoveOosSetting()
0xd8a4  brfalse.s loc_D8B7
0xd8a6  ldarg.1
0xd8a7  ldsfld   string ProductOperation::RemoveOosSettingProperty
0xd8ac  ldarg.0
0xd8ad  callvirt instance string Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext::get_RemoveOosSetting()
0xd8b2  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd8b7  ret
```
