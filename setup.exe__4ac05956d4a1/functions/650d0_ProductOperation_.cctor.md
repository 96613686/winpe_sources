# ProductOperation::.cctor

- ea: `0x650d0`
- end: `0x65905`
- name: `ProductOperation::.cctor`
- size: `2101`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x658f5`: `includeRecommendedOnUpdate`
- `0x65571`: `installedProducts`
- `0x650d5`: `install-product`
- `0x650e9`: `install-product-error`
- `0x65189`: `appVersionupdateTo`
- `0x6519d`: `appVersionupdateFrom`
- `0x651c5`: `installerid`
- `0x651d9`: `installsessionid`
- `0x65201`: `componentsadded`
- `0x65215`: `componentsremoved`
- `0x65229`: `componentsupdated`
- `0x6523d`: `componentsinstalled`
- `0x65251`: `componentsuninstalled`
- `0x65265`: `failedcomponentids`
- `0x65279`: `failedcomponentidscount`
- `0x6528d`: `installedcomponentids`
- `0x652a1`: `installedcomponentidscount`
- `0x652c9`: `workloadsremoved`
- `0x652dd`: `workloadsupdated`
- `0x652f1`: `workloadsinstalled`
- `0x65305`: `workloadsuninstalled`
- `0x65341`: `installedworkloadids`
- `0x65355`: `installedworkloadidscount`
- `0x65369`: `installedextensionidscount`
- `0x6537d`: `extensionsadded`
- `0x65391`: `extensionsaddedcount`
- `0x653a5`: `extensionsremoved`
- `0x653b9`: `extensionsremovedcount`
- `0x653cd`: `failedextensionids`
- `0x653e1`: `failedextensionidscount`
- `0x65459`: `skippedcomponentids`
- `0x6546d`: `skippedextensionids`
- `0x654e5`: `installstate`
- `0x654f9`: `actualinstallsizekb`
- `0x65521`: `numberofinstalls`
- `0x65535`: `isfirstinstallexperience`
- `0x6555d`: `rejectrecommendedselection`
- `0x655ad`: `numberofserviceerrors`
- `0x655c1`: `packagecacheenabled`
- `0x655d5`: `packagecachepathmodified`
- `0x655e9`: `packagecachesettingmodified`
- `0x655fd`: `packagecachedrive`
- `0x65611`: `sharedinstallationdrive`
- `0x65625`: `sharedinstallationpathmodified`
- `0x65639`: `installationpathmodified`
- `0x656d9`: `selectedAdvertisedComponentIds`
- `0x65729`: `selectedconfigpackage`
- `0x65779`: `fromlayouturi`
- `0x6578d`: `diduserfiltercomponents`
- `0x657a1`: `diduserselectcomponentfromfilteredlist`
- `0x657b5`: `previewUpdate`
- `0x65869`: `removeOosSetting`
- `0x6587d`: `installerServiceConnectionType`
- `0x658a5`: `installPathHasReparsePoint`
- `0x658b9`: `cachePathHasReparsePoint`
- `0x658cd`: `sharedPathHasReparsePoint`
- `0x658e1`: `numberOfExtensionDownloadFailures`

## pseudocode

```c

```

## disassembly

```asm
0x650d0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0x650d5  ldstr    aInstallProduct// "install-product"
0x650da  call     string [mscorlib]System.String::Concat(string, string)
0x650df  stsfld   string ProductOperation::InstallProductEvent
0x650e4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0x650e9  ldstr    aInstallProduct_0// "install-product-error"
0x650ee  call     string [mscorlib]System.String::Concat(string, string)
0x650f3  stsfld   string ProductOperation::InstallProductErrorEvent
0x650f8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0x650fd  ldstr    aEndoperationge// "EndOperationGetProductError"
0x65102  call     string [mscorlib]System.String::Concat(string, string)
0x65107  stsfld   string ProductOperation::EndOperationGetProductErrorEvent
0x6510c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0x65111  ldstr    aCancelOperatio// "cancel-operation"
0x65116  call     string [mscorlib]System.String::Concat(string, string)
0x6511b  stsfld   string ProductOperation::OperationCancelEvent
0x65120  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65125  ldstr    aProductid// "productId"
0x6512a  call     string [mscorlib]System.String::Concat(string, string)
0x6512f  stsfld   string ProductOperation::ProductIdProperty
0x65134  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65139  ldstr    aChannelid// "channelId"
0x6513e  call     string [mscorlib]System.String::Concat(string, string)
0x65143  stsfld   string ProductOperation::ChannelIdProperty
0x65148  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x6514d  ldstr    aInstanceid_0// "instanceId"
0x65152  call     string [mscorlib]System.String::Concat(string, string)
0x65157  stsfld   string ProductOperation::InstanceIdProperty
0x6515c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65161  ldstr    aProductarch_0// "productArch"
0x65166  call     string [mscorlib]System.String::Concat(string, string)
0x6516b  stsfld   string ProductOperation::ProductArchProperty
0x65170  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65175  ldstr    aAppversion// "appversion"
0x6517a  call     string [mscorlib]System.String::Concat(string, string)
0x6517f  stsfld   string ProductOperation::AppVersionProperty
0x65184  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65189  ldstr    aAppversionupda// "appVersionupdateTo"
0x6518e  call     string [mscorlib]System.String::Concat(string, string)
0x65193  stsfld   string ProductOperation::UpdateTo
0x65198  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x6519d  ldstr    aAppversionupda_0// "appVersionupdateFrom"
0x651a2  call     string [mscorlib]System.String::Concat(string, string)
0x651a7  stsfld   string ProductOperation::UpdateFrom
0x651ac  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x651b1  ldstr    aHowlaunched// "howlaunched"
0x651b6  call     string [mscorlib]System.String::Concat(string, string)
0x651bb  stsfld   string ProductOperation::HowLaunchedProperty
0x651c0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x651c5  ldstr    aInstallerid// "installerid"
0x651ca  call     string [mscorlib]System.String::Concat(string, string)
0x651cf  stsfld   string ProductOperation::InstallerIdProperty
0x651d4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x651d9  ldstr    aInstallsession_1// "installsessionid"
0x651de  call     string [mscorlib]System.String::Concat(string, string)
0x651e3  stsfld   string ProductOperation::InstallSessionIdProperty
0x651e8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x651ed  ldstr    aOperationname// "operationname"
0x651f2  call     string [mscorlib]System.String::Concat(string, string)
0x651f7  stsfld   string ProductOperation::OperationNameProperty
0x651fc  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65201  ldstr    aComponentsadde// "componentsadded"
0x65206  call     string [mscorlib]System.String::Concat(string, string)
0x6520b  stsfld   string ProductOperation::ComponentsAddedProperty
0x65210  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65215  ldstr    aComponentsremo// "componentsremoved"
0x6521a  call     string [mscorlib]System.String::Concat(string, string)
0x6521f  stsfld   string ProductOperation::ComponentsRemovedProperty
0x65224  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65229  ldstr    aComponentsupda// "componentsupdated"
0x6522e  call     string [mscorlib]System.String::Concat(string, string)
0x65233  stsfld   string ProductOperation::ComponentsUpdatedProperty
0x65238  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x6523d  ldstr    aComponentsinst// "componentsinstalled"
0x65242  call     string [mscorlib]System.String::Concat(string, string)
0x65247  stsfld   string ProductOperation::ComponentsInstalledProperty
0x6524c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65251  ldstr    aComponentsunin// "componentsuninstalled"
0x65256  call     string [mscorlib]System.String::Concat(string, string)
0x6525b  stsfld   string ProductOperation::ComponentsUninstalledProperty
0x65260  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65265  ldstr    aFailedcomponen// "failedcomponentids"
0x6526a  call     string [mscorlib]System.String::Concat(string, string)
0x6526f  stsfld   string ProductOperation::FailedComponentsProperty
0x65274  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65279  ldstr    aFailedcomponen_0// "failedcomponentidscount"
0x6527e  call     string [mscorlib]System.String::Concat(string, string)
0x65283  stsfld   string ProductOperation::FailedComponentsCountProperty
0x65288  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x6528d  ldstr    aInstalledcompo// "installedcomponentids"
0x65292  call     string [mscorlib]System.String::Concat(string, string)
0x65297  stsfld   string ProductOperation::InstalledComponentsProperty
0x6529c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x652a1  ldstr    aInstalledcompo_0// "installedcomponentidscount"
0x652a6  call     string [mscorlib]System.String::Concat(string, string)
0x652ab  stsfld   string ProductOperation::InstalledComponentsCountProperty
0x652b0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x652b5  ldstr    aWorkloadsadded// "workloadsadded"
0x652ba  call     string [mscorlib]System.String::Concat(string, string)
0x652bf  stsfld   string ProductOperation::WorkloadsAddedProperty
0x652c4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x652c9  ldstr    aWorkloadsremov// "workloadsremoved"
0x652ce  call     string [mscorlib]System.String::Concat(string, string)
0x652d3  stsfld   string ProductOperation::WorkloadsRemovedProperty
0x652d8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x652dd  ldstr    aWorkloadsupdat// "workloadsupdated"
0x652e2  call     string [mscorlib]System.String::Concat(string, string)
0x652e7  stsfld   string ProductOperation::WorkloadsUpdatedProperty
0x652ec  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x652f1  ldstr    aWorkloadsinsta// "workloadsinstalled"
0x652f6  call     string [mscorlib]System.String::Concat(string, string)
0x652fb  stsfld   string ProductOperation::WorkloadsInstalledProperty
0x65300  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65305  ldstr    aWorkloadsunins// "workloadsuninstalled"
0x6530a  call     string [mscorlib]System.String::Concat(string, string)
0x6530f  stsfld   string ProductOperation::WorkloadsUninstalledProperty
0x65314  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65319  ldstr    aFailedworkload// "failedworkloadids"
0x6531e  call     string [mscorlib]System.String::Concat(string, string)
0x65323  stsfld   string ProductOperation::FailedWorkloadsProperty
0x65328  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x6532d  ldstr    aFailedworkload_0// "failedworkloadidscount"
0x65332  call     string [mscorlib]System.String::Concat(string, string)
0x65337  stsfld   string ProductOperation::FailedWorkloadsCountProperty
0x6533c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65341  ldstr    aInstalledworkl// "installedworkloadids"
0x65346  call     string [mscorlib]System.String::Concat(string, string)
0x6534b  stsfld   string ProductOperation::InstalledWorkloadsProperty
0x65350  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65355  ldstr    aInstalledworkl_0// "installedworkloadidscount"
0x6535a  call     string [mscorlib]System.String::Concat(string, string)
0x6535f  stsfld   string ProductOperation::InstalledWorkloadsCountProperty
0x65364  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65369  ldstr    aInstalledexten// "installedextensionidscount"
0x6536e  call     string [mscorlib]System.String::Concat(string, string)
0x65373  stsfld   string ProductOperation::InstalledExtensionsCountProperty
0x65378  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x6537d  ldstr    aExtensionsadde// "extensionsadded"
0x65382  call     string [mscorlib]System.String::Concat(string, string)
0x65387  stsfld   string ProductOperation::ExtensionsAddedProperty
0x6538c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65391  ldstr    aExtensionsadde_0// "extensionsaddedcount"
0x65396  call     string [mscorlib]System.String::Concat(string, string)
0x6539b  stsfld   string ProductOperation::ExtensionsAddedCountProperty
0x653a0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x653a5  ldstr    aExtensionsremo// "extensionsremoved"
0x653aa  call     string [mscorlib]System.String::Concat(string, string)
0x653af  stsfld   string ProductOperation::ExtensionsRemovedProperty
0x653b4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x653b9  ldstr    aExtensionsremo_0// "extensionsremovedcount"
0x653be  call     string [mscorlib]System.String::Concat(string, string)
0x653c3  stsfld   string ProductOperation::ExtensionsRemovedCountProperty
0x653c8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x653cd  ldstr    aFailedextensio// "failedextensionids"
0x653d2  call     string [mscorlib]System.String::Concat(string, string)
0x653d7  stsfld   string ProductOperation::FailedExtensionsProperty
0x653dc  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x653e1  ldstr    aFailedextensio_0// "failedextensionidscount"
0x653e6  call     string [mscorlib]System.String::Concat(string, string)
0x653eb  stsfld   string ProductOperation::FailedExtensionsCountProperty
0x653f0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x653f5  ldstr    aFailedpackagei// "failedpackageids"
0x653fa  call     string [mscorlib]System.String::Concat(string, string)
0x653ff  stsfld   string ProductOperation::FailedPackagesProperty
0x65404  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65409  ldstr    aFailedpackaged// "failedpackagedetails"
0x6540e  call     string [mscorlib]System.String::Concat(string, string)
0x65413  stsfld   string ProductOperation::FailedPackageDetailsProperty
0x65418  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x6541d  ldstr    aFailedpackagei_0// "failedpackageidscount"
0x65422  call     string [mscorlib]System.String::Concat(string, string)
0x65427  stsfld   string ProductOperation::FailedPackagesCountProperty
0x6542c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65431  ldstr    aSkippedpackage// "skippedpackageids"
0x65436  call     string [mscorlib]System.String::Concat(string, string)
0x6543b  stsfld   string ProductOperation::SkippedPackagesProperty
0x65440  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65445  ldstr    aSkippedpackage_0// "skippedpackageidscount"
0x6544a  call     string [mscorlib]System.String::Concat(string, string)
0x6544f  stsfld   string ProductOperation::SkippedPackagesCountProperty
0x65454  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65459  ldstr    aSkippedcompone// "skippedcomponentids"
0x6545e  call     string [mscorlib]System.String::Concat(string, string)
0x65463  stsfld   string ProductOperation::SkippedComponentsProperty
0x65468  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x6546d  ldstr    aSkippedextensi// "skippedextensionids"
0x65472  call     string [mscorlib]System.String::Concat(string, string)
0x65477  stsfld   string ProductOperation::SkippedExtensionsProperty
0x6547c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65481  ldstr    aErrormessage_1// "errormessage"
0x65486  call     string [mscorlib]System.String::Concat(string, string)
0x6548b  stsfld   string ProductOperation::ErrorMessageProperty
0x65490  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65495  ldstr    aErrorcode// "errorcode"
0x6549a  call     string [mscorlib]System.String::Concat(string, string)
0x6549f  stsfld   string ProductOperation::ErrorCodeProperty
0x654a4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x654a9  ldstr    aErrorstack// "errorstack"
0x654ae  call     string [mscorlib]System.String::Concat(string, string)
0x654b3  stsfld   string ProductOperation::ErrorStackProperty
0x654b8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x654bd  ldstr    aIstorn// "istorn"
0x654c2  call     string [mscorlib]System.String::Concat(string, string)
0x654c7  stsfld   string ProductOperation::IsTornProperty
0x654cc  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x654d1  ldstr    aHascorepackage// "hascorepackagefailures"
0x654d6  call     string [mscorlib]System.String::Concat(string, string)
0x654db  stsfld   string ProductOperation::HasCorePackageFailuresProperty
0x654e0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x654e5  ldstr    aInstallstate// "installstate"
0x654ea  call     string [mscorlib]System.String::Concat(string, string)
0x654ef  stsfld   string ProductOperation::InstallStateProperty
0x654f4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x654f9  ldstr    aActualinstalls// "actualinstallsizekb"
0x654fe  call     string [mscorlib]System.String::Concat(string, string)
0x65503  stsfld   string ProductOperation::ActualInstallSizeKBProperty
0x65508  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x6550d  ldstr    aReboottype// "reboottype"
0x65512  call     string [mscorlib]System.String::Concat(string, string)
0x65517  stsfld   string ProductOperation::RebootTypeProperty
0x6551c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65521  ldstr    aNumberofinstal// "numberofinstalls"
0x65526  call     string [mscorlib]System.String::Concat(string, string)
0x6552b  stsfld   string ProductOperation::NumberOfInstallsProperty
0x65530  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65535  ldstr    aIsfirstinstall// "isfirstinstallexperience"
0x6553a  call     string [mscorlib]System.String::Concat(string, string)
0x6553f  stsfld   string ProductOperation::IsFirstInstallExperienceProperty
0x65544  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65549  ldstr    aOperationresul// "operationResult"
0x6554e  call     string [mscorlib]System.String::Concat(string, string)
0x65553  stsfld   string ProductOperation::OperationResultProperty
0x65558  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x6555d  ldstr    aRejectrecommen// "rejectrecommendedselection"
0x65562  call     string [mscorlib]System.String::Concat(string, string)
0x65567  stsfld   string ProductOperation::RejectRecommendedSelectionProperty
0x6556c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65571  ldstr    aInstalledprodu_0// "installedProducts"
0x65576  call     string [mscorlib]System.String::Concat(string, string)
0x6557b  stsfld   string ProductOperation::InstalledProductsProperty
0x65580  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65585  ldstr    aAvailableprodu// "availableProducts"
0x6558a  call     string [mscorlib]System.String::Concat(string, string)
0x6558f  stsfld   string ProductOperation::AvailableProductsProperty
0x65594  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65599  ldstr    aNumberofrpcerr// "numberofrpcerrors"
0x6559e  call     string [mscorlib]System.String::Concat(string, string)
0x655a3  stsfld   string ProductOperation::NumberOfRpcErrorsProperty
0x655a8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x655ad  ldstr    aNumberofservic// "numberofserviceerrors"
0x655b2  call     string [mscorlib]System.String::Concat(string, string)
0x655b7  stsfld   string ProductOperation::NumberOfServiceErrorsProperty
0x655bc  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x655c1  ldstr    aPackagecacheen// "packagecacheenabled"
0x655c6  call     string [mscorlib]System.String::Concat(string, string)
0x655cb  stsfld   string ProductOperation::PackageCacheEnabledProperty
0x655d0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x655d5  ldstr    aPackagecachepa// "packagecachepathmodified"
0x655da  call     string [mscorlib]System.String::Concat(string, string)
0x655df  stsfld   string ProductOperation::PackageCachePathModifiedProperty
0x655e4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x655e9  ldstr    aPackagecachese// "packagecachesettingmodified"
0x655ee  call     string [mscorlib]System.String::Concat(string, string)
0x655f3  stsfld   string ProductOperation::PackageCacheSettingModifiedProperty
0x655f8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x655fd  ldstr    aPackagecachedr// "packagecachedrive"
0x65602  call     string [mscorlib]System.String::Concat(string, string)
0x65607  stsfld   string ProductOperation::PackageCacheDriveProperty
0x6560c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65611  ldstr    aSharedinstalla_0// "sharedinstallationdrive"
0x65616  call     string [mscorlib]System.String::Concat(string, string)
0x6561b  stsfld   string ProductOperation::SharedInstallationDriveProperty
0x65620  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65625  ldstr    aSharedinstalla_1// "sharedinstallationpathmodified"
0x6562a  call     string [mscorlib]System.String::Concat(string, string)
0x6562f  stsfld   string ProductOperation::SharedInstallationPathModifiedProperty
0x65634  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65639  ldstr    aInstallationpa_2// "installationpathmodified"
0x6563e  call     string [mscorlib]System.String::Concat(string, string)
0x65643  stsfld   string ProductOperation::InstallationPathModifiedProperty
0x65648  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x6564d  ldstr    aSystemdrive// "systemdrive"
0x65652  call     string [mscorlib]System.String::Concat(string, string)
0x65657  stsfld   string ProductOperation::SystemDriveProperty
0x6565c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65661  ldstr    aTargetdrive// "targetdrive"
0x65666  call     string [mscorlib]System.String::Concat(string, string)
0x6566b  stsfld   string ProductOperation::TargetDriveProperty
0x65670  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65675  ldstr    aHasssd// "hasssd"
0x6567a  call     string [mscorlib]System.String::Concat(string, string)
0x6567f  stsfld   string ProductOperation::HasSSDProperty
0x65684  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65689  ldstr    aIssystemdrives// "issystemdrivessd"
0x6568e  call     string [mscorlib]System.String::Concat(string, string)
0x65693  stsfld   string ProductOperation::IsSystemDriveSSDProperty
0x65698  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x6569d  ldstr    aIstargetdrives// "istargetdrivessd"
0x656a2  call     string [mscorlib]System.String::Concat(string, string)
0x656a7  stsfld   string ProductOperation::IsTargetDriveSSDProperty
  ... truncated ...
```
