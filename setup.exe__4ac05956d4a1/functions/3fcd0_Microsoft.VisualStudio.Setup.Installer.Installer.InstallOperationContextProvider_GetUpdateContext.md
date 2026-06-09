# Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::GetUpdateContext

- ea: `0x3fcd0`
- end: `0x3ff2e`
- name: `Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::GetUpdateContext`
- size: `606`
- prototype: ``
- caller_count: `0`
- callee_count: `43`
- tags: `installer_update, broker_com_uri`

## callees

- `0xa0b0`
- `0x21bc0`
- `0x21bd0`
- `0x21be0`
- `0x2c4a0`
- `0x2c4d0`
- `0x2c5b0`
- `0x2c920`
- `0x36450`
- `0x36e80`
- `0x3a7a0`
- `0x3a7f0`
- `0x3a840`
- `0x3a860`
- `0x3a8b0`
- `0x3a8c0`
- `0x3a8e0`
- `0x3b5a0`
- `0x3c1c0`
- `0x3fcd0`
- `0x403e0`
- `0x40590`
- `0x405a0`
- `0x40690`
- `0x408a0`
- `0x408f0`
- `0x40970`
- `0x40980`
- `0x40990`
- `0x41570`
- `0x41580`
- `0x41590`
- `0x415a0`
- `0x415b0`
- `0x415c0`
- `0x415d0`
- `0x415e0`
- `0x415f0`
- `0x41610`
- `0x41630`
- `0x41650`
- `0x41670`
- `0x41680`

## string_xrefs

- `0x3fd51`: `Can not find the update version of product.`

## pseudocode

```c

```

## disassembly

```asm
0x3fcd0  ldarg.0
0x3fcd1  ldarg.2
0x3fcd2  call     instance string Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::GetSessionId(class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContextOptions options)
0x3fcd7  stloc.0
0x3fcd8  ldarg.0
0x3fcd9  ldarg.1
0x3fcda  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductIdentityModel::get_InstallationPath()
0x3fcdf  ldloc.0
0x3fce0  ldarg.2
0x3fce1  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::get_ProductKey()
0x3fce6  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::GetResumeArguments(string installationPath, string installSessionId, [opt] string productKey)
0x3fceb  ldarg.1
0x3fcec  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductIdentityModel::get_InstanceId()
0x3fcf1  stloc.1
0x3fcf2  ldarg.0
0x3fcf3  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallOperationContextProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::serviceOptions
0x3fcf8  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_SettingsService()
0x3fcfd  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService::get_UpdateFromVS()
0x3fd02  stloc.2
0x3fd03  ldarg.2
0x3fd04  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::get_UpdateVersion()
0x3fd09  stloc.3
0x3fd0a  ldloc.3
0x3fd0b  brtrue.s loc_3FD2D
0x3fd0d  ldarg.1
0x3fd0e  isinst   Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductModel
0x3fd13  stloc.s  4
0x3fd15  ldloc.s  4
0x3fd17  brfalse.s loc_3FD2D
0x3fd19  ldloc.s  4
0x3fd1b  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.UpdateInformationModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductModel::get_UpdateInformation()
0x3fd20  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.VersionBundle Microsoft.VisualStudio.Setup.Installer.Models.Products.UpdateInformationModel::get_LatestVersion()
0x3fd25  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Installer.Models.VersionBundle::get_BuildVersion()
0x3fd2a  stloc.3
0x3fd2b  br.s     loc_3FD4E
0x3fd2d  ldloc.3
0x3fd2e  brtrue.s loc_3FD4E
0x3fd30  ldarg.1
0x3fd31  isinst   Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel
0x3fd36  stloc.s  0xA
0x3fd38  ldloc.s  0xA
0x3fd3a  brfalse.s loc_3FD4E
0x3fd3c  ldloc.s  0xA
0x3fd3e  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.UpdateInformationModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_UpdateInformation()
0x3fd43  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.VersionBundle Microsoft.VisualStudio.Setup.Installer.Models.Products.UpdateInformationModel::get_LatestVersion()
0x3fd48  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Installer.Models.VersionBundle::get_BuildVersion()
0x3fd4d  stloc.3
0x3fd4e  ldloc.3
0x3fd4f  brtrue.s loc_3FD5C
0x3fd51  ldstr    aCanNotFindTheU// "Can not find the update version of prod"...
0x3fd56  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3fd5b  throw
0x3fd5c  ldnull
0x3fd5d  stloc.s  5
0x3fd5f  ldarg.2
0x3fd60  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::get_ChannelUri()
0x3fd65  dup
0x3fd66  brtrue.s loc_3FD74
0x3fd68  pop
0x3fd69  ldarg.1
0x3fd6a  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Channel()
0x3fd6f  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Models.IChannelModelSummary::get_UpdateUri()
0x3fd74  stloc.s  6
0x3fd76  ldarg.0
0x3fd77  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallOperationContextProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::serviceOptions
0x3fd7c  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.INicknameService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallOperationContextProviderServiceOptions::get_NicknameService()
0x3fd81  ldarg.1
0x3fd82  ldloc.s  6
0x3fd84  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Services.INicknameService::IsNicknameRequired(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel product, [opt] class [System]System.Uri targetChannelUri)
0x3fd89  brfalse.s loc_3FDBB
0x3fd8b  ldarg.0
0x3fd8c  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallOperationContextProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::serviceOptions
0x3fd91  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.INicknameService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallOperationContextProviderServiceOptions::get_NicknameService()
0x3fd96  ldarg.1
0x3fd97  ldarg.1
0x3fd98  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_Nickname()
0x3fd9d  ldloc.s  6
0x3fd9f  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Services.INicknameService::IsValidNickname(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel product, string nickname, [opt] class [System]System.Uri targetChannelUri)
0x3fda4  brtrue.s loc_3FDBB
0x3fda6  ldarg.0
0x3fda7  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallOperationContextProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::serviceOptions
0x3fdac  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.INicknameService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallOperationContextProviderServiceOptions::get_NicknameService()
0x3fdb1  ldarg.1
0x3fdb2  ldloc.s  6
0x3fdb4  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Services.INicknameService::SuggestNickname(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel product, [opt] class [System]System.Uri targetChannelUri)
0x3fdb9  stloc.s  5
0x3fdbb  ldc.i4.0
0x3fdbc  stloc.s  7
0x3fdbe  ldstr    aNotset// "NotSet"
0x3fdc3  stloc.s  8
0x3fdc5  ldarg.0
0x3fdc6  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallOperationContextProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::serviceOptions
0x3fdcb  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_PolicyService()
0x3fdd0  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_RemoveOos()
0x3fdd5  brfalse.s loc_3FDE3
0x3fdd7  ldc.i4.1
0x3fdd8  stloc.s  7
0x3fdda  ldstr    aPolicyset// "PolicySet"
0x3fddf  stloc.s  8
0x3fde1  br.s     loc_3FE2B
0x3fde3  ldarg.2
0x3fde4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::get_RemoveOos()
0x3fde9  stloc.s  0xB
0x3fdeb  ldloca.s 0xB
0x3fded  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x3fdf2  brfalse.s loc_3FE19
0x3fdf4  ldarg.2
0x3fdf5  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::get_RemoveOos()
0x3fdfa  stloc.s  0xB
0x3fdfc  ldloca.s 0xB
0x3fdfe  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x3fe03  stloc.s  7
0x3fe05  ldloc.s  7
0x3fe07  brtrue.s loc_3FE10
0x3fe09  ldstr    aOptionsetfalse// "OptionSetFalse"
0x3fe0e  br.s     loc_3FE15
0x3fe10  ldstr    aOptionsettrue// "OptionSetTrue"
0x3fe15  stloc.s  8
0x3fe17  br.s     loc_3FE2B
0x3fe19  ldarg.1
0x3fe1a  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_RemoveOos()
0x3fe1f  brfalse.s loc_3FE2B
0x3fe21  ldc.i4.1
0x3fe22  stloc.s  7
0x3fe24  ldstr    aInstanceset// "InstanceSet"
0x3fe29  stloc.s  8
0x3fe2b  ldarg.2
0x3fe2c  callvirt instance class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext Microsoft.VisualStudio.Setup.Installer.Installer.OperationContextOptions::get_InstallerTelemetryContext()
0x3fe31  dup
0x3fe32  brtrue.s loc_3FE63
0x3fe34  pop
0x3fe35  ldarg.0
0x3fe36  ldc.i4.2
0x3fe37  ldarg.1
0x3fe38  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductIdentityModel::get_InstallationPath()
0x3fe3d  ldarg.1
0x3fe3e  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductIdentityModel::get_InstallationPath()
0x3fe43  ldloc.0
0x3fe44  ldc.i4.0
0x3fe45  ldarg.2
0x3fe46  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::get_IsFocusedUi()
0x3fe4b  ldc.i4.0
0x3fe4c  ldc.i4.0
0x3fe4d  ldarg.2
0x3fe4e  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Installer.OperationContextOptions::get_FromCommandLine()
0x3fe53  ldarg.2
0x3fe54  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::get_PreviewUpdate()
0x3fe59  ldc.i4.0
0x3fe5a  ldc.i4.0
0x3fe5b  ldloc.s  8
0x3fe5d  ldc.i4.0
0x3fe5e  call     instance class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::GetTelemetryContext(valuetype Microsoft.VisualStudio.Setup.Installer.UserExecuteAction action, string defaultInstallationPath, string installationPath, string installSessionId, bool packageCacheSettingModified, bool isFocusedUi, bool selectedMissingPackage, bool selectedConfigPackage, bool fromCommandLine, bool previewUpdate, bool fromImport, bool isFromAvailableTab, string removeOos, bool selectedAllPackages)
0x3fe63  stloc.s  9
0x3fe65  ldloc.1
0x3fe66  ldarg.1
0x3fe67  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductIdentityModel::get_InstallationPath()
0x3fe6c  ldloc.2
0x3fe6d  ldloc.3
0x3fe6e  ldarg.0
0x3fe6f  ldarg.2
0x3fe70  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.OperationMode> Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::get_OperationMode()
0x3fe75  call     instance valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.OperationMode Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::GetOperationMode(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.OperationMode> operationMode)
0x3fe7a  ldloc.s  7
0x3fe7c  ldarg.1
0x3fe7d  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_IncludeRecommendedOnUpdate()
0x3fe82  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::.ctor(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments, string, string, bool, class [mscorlib]System.Version, valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.OperationMode, bool, bool)
0x3fe87  dup
0x3fe88  ldarg.2
0x3fe89  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::get_InstallLayoutPath()
0x3fe8e  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::set_InstallLayoutPath(string)
0x3fe93  dup
0x3fe94  ldarg.2
0x3fe95  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::get_LayoutPath()
0x3fe9a  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::set_LayoutPath(string)
0x3fe9f  dup
0x3fea0  ldarg.2
0x3fea1  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::get_ProductKey()
0x3fea6  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::set_ProductKey(string)
0x3feab  dup
0x3feac  ldarg.2
0x3fead  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::get_VsFlights()
0x3feb2  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::set_VisualStudioFlights(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x3feb7  dup
0x3feb8  ldloc.s  9
0x3feba  ldarg.0
0x3febb  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallOperationContextProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallOperationContextProvider::serviceOptions
0x3fec0  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Telemetry()
0x3fec5  call     valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.TelemetryContext Microsoft.VisualStudio.Setup.Installer.Extensions::GetEngineTelemetryContext(class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext installerTelemetryContext, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry telemetry)
0x3feca  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions::set_TelemetryContext(valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.TelemetryContext)
0x3fecf  dup
0x3fed0  ldarg.2
0x3fed1  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::get_ChannelUri()
0x3fed6  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::set_ChannelUri(class [System]System.Uri)
0x3fedb  dup
0x3fedc  ldarg.2
0x3fedd  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::get_InstallChannelUri()
0x3fee2  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::set_InstallChannelUri(class [System]System.Uri)
0x3fee7  dup
0x3fee8  ldarg.2
0x3fee9  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::get_InstallCatalogUri()
0x3feee  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::set_InstallCatalogUri(class [System]System.Uri)
0x3fef3  dup
0x3fef4  ldloc.s  5
0x3fef6  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::set_Nickname(string)
0x3fefb  dup
0x3fefc  ldarg.2
0x3fefd  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Installer.OperationContextOptions::get_KeepWindowsUpdateOn()
0x3ff02  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions::set_KeepWindowsUpdateOn(bool)
0x3ff07  dup
0x3ff08  ldarg.2
0x3ff09  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::get_LayoutUri()
0x3ff0e  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::set_LayoutUri(class [System]System.Uri)
0x3ff13  dup
0x3ff14  ldarg.2
0x3ff15  callvirt instance valuetype [mscorlib]System.Guid Microsoft.VisualStudio.Setup.Installer.Installer.UpdateContextOptions::get_WUProgressCBClsID()
0x3ff1a  callvirt instance modreq([Microsoft.VisualStudio.Setup.Common]System.Runtime.CompilerServices.IsExternalInit) void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::set_WUProgressCBClsID(valuetype [mscorlib]System.Guid)
0x3ff1f  ldarg.1
0x3ff20  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext::.ctor(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions options, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel product)
0x3ff25  dup
0x3ff26  ldloc.s  9
0x3ff28  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext::set_InstallerTelemetryContext(class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext value)
0x3ff2d  ret
```
