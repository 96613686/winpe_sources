# Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::DownloadEmbeddedExtensions

- ea: `0x20a60`
- end: `0x20d24`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::DownloadEmbeddedExtensions`
- size: `708`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x20a60`
- `0x6d990`

## callees

- `0x20a60`
- `0x2bcb0`
- `0x2bcc0`
- `0x2c060`
- `0x2c080`
- `0x3dcb0`
- `0x6c7a0`

## string_xrefs

- `0x20b30`: `Skipping absolute URI dependency location '`
- `0x20b4e`: `' in extension '`
- `0x20b68`: `). Absolute URIs are not embedded extensions.`
- `0x20cad`: `Could not load embedded extension `

## pseudocode

```c

```

## disassembly

```asm
0x20a60  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class ExtensionContentsSummary>::.ctor()
0x20a65  stloc.0
0x20a66  ldarg.0
0x20a67  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x20a6c  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.IExtensionServiceInternal Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions::get_ExtensionService()
0x20a71  ldarg.1
0x20a72  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionDependency> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.IExtensionServiceInternal::ParseExtensionDependencies(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents)
0x20a77  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionDependency>::GetEnumerator()
0x20a7c  stloc.1
0x20a7d  br       loc_20D0B
0x20a82  ldloc.1
0x20a83  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionDependency>::get_Current()
0x20a88  stloc.2
0x20a89  ldloc.2
0x20a8a  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionDependency::get_Location()
0x20a8f  brfalse  loc_20CE0
0x20a94  ldloc.2
0x20a95  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionDependency::get_Location()
0x20a9a  ldc.i4.1
0x20a9b  ldloca.s 3
0x20a9d  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x20aa2  brfalse  loc_20BEF
0x20aa7  ldloc.2
0x20aa8  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionDependency::get_Id()
0x20aad  dup
0x20aae  brtrue.s loc_20AB6
0x20ab0  pop
0x20ab1  ldstr    aUnknown_0// "unknown"
0x20ab6  stloc.s  4
0x20ab8  ldarg.1
0x20ab9  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionManifest [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents::get_ExtensionManifest()
0x20abe  dup
0x20abf  brtrue.s loc_20AC5
0x20ac1  pop
0x20ac2  ldnull
0x20ac3  br.s     loc_20AE2
0x20ac5  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.Metadata [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionManifest::get_Metadata()
0x20aca  dup
0x20acb  brtrue.s loc_20AD1
0x20acd  pop
0x20ace  ldnull
0x20acf  br.s     loc_20AE2
0x20ad1  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.Identity [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.Metadata::get_Identity()
0x20ad6  dup
0x20ad7  brtrue.s loc_20ADD
0x20ad9  pop
0x20ada  ldnull
0x20adb  br.s     loc_20AE2
0x20add  call     instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.Identity::get_Id()
0x20ae2  dup
0x20ae3  brtrue.s loc_20AEB
0x20ae5  pop
0x20ae6  ldstr    aUnknown_0// "unknown"
0x20aeb  stloc.s  5
0x20aed  ldarg.1
0x20aee  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionManifest [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents::get_ExtensionManifest()
0x20af3  dup
0x20af4  brtrue.s loc_20AFA
0x20af6  pop
0x20af7  ldnull
0x20af8  br.s     loc_20B0B
0x20afa  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.Metadata [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionManifest::get_Metadata()
0x20aff  dup
0x20b00  brtrue.s loc_20B06
0x20b02  pop
0x20b03  ldnull
0x20b04  br.s     loc_20B0B
0x20b06  call     instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.Metadata::get_DisplayName()
0x20b0b  dup
0x20b0c  brtrue.s loc_20B14
0x20b0e  pop
0x20b0f  ldstr    aUnknown_0// "unknown"
0x20b14  stloc.s  6
0x20b16  ldarg.0
0x20b17  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x20b1c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Logger()
0x20b21  dup
0x20b22  brtrue.s loc_20B27
0x20b24  pop
0x20b25  br.s     loc_20B7D
0x20b27  ldc.i4.s 9
0x20b29  newarr   [mscorlib]System.String
0x20b2e  dup
0x20b2f  ldc.i4.0
0x20b30  ldstr    aSkippingAbsolu// "Skipping absolute URI dependency locati"...
0x20b35  stelem.ref
0x20b36  dup
0x20b37  ldc.i4.1
0x20b38  ldloc.2
0x20b39  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionDependency::get_Location()
0x20b3e  stelem.ref
0x20b3f  dup
0x20b40  ldc.i4.2
0x20b41  ldstr    aForDependency// "' for dependency '"
0x20b46  stelem.ref
0x20b47  dup
0x20b48  ldc.i4.3
0x20b49  ldloc.s  4
0x20b4b  stelem.ref
0x20b4c  dup
0x20b4d  ldc.i4.4
0x20b4e  ldstr    aInExtension// "' in extension '"
0x20b53  stelem.ref
0x20b54  dup
0x20b55  ldc.i4.5
0x20b56  ldloc.s  5
0x20b58  stelem.ref
0x20b59  dup
0x20b5a  ldc.i4.6
0x20b5b  ldstr    asc_9D8B8// "' ("
0x20b60  stelem.ref
0x20b61  dup
0x20b62  ldc.i4.7
0x20b63  ldloc.s  6
0x20b65  stelem.ref
0x20b66  dup
0x20b67  ldc.i4.8
0x20b68  ldstr    aAbsoluteUrisAr// "). Absolute URIs are not embedded exten"...
0x20b6d  stelem.ref
0x20b6e  call     string [mscorlib]System.String::Concat(string[])
0x20b73  call     T0x2B000010
0x20b78  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x20b7d  ldarg.0
0x20b7e  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x20b83  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Telemetry()
0x20b88  dup
0x20b89  brtrue.s loc_20B91
0x20b8b  pop
0x20b8c  br       loc_20D0B
0x20b91  ldsfld   string Extensions::AbsoluteUriDependencyLocationEvent
0x20b96  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x20b9b  ldsfld   string Extensions::MoreInfoDependencyIdProperty
0x20ba0  stloc.s  7
0x20ba2  dup
0x20ba3  ldloc.s  7
0x20ba5  ldloc.s  4
0x20ba7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x20bac  ldsfld   string Extensions::MoreInfoLocationProperty
0x20bb1  stloc.s  8
0x20bb3  dup
0x20bb4  ldloc.s  8
0x20bb6  ldloc.2
0x20bb7  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionDependency::get_Location()
0x20bbc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x20bc1  ldsfld   string Extensions::MoreInfoParentVsixIdProperty
0x20bc6  stloc.s  9
0x20bc8  dup
0x20bc9  ldloc.s  9
0x20bcb  ldloc.s  5
0x20bcd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x20bd2  ldsfld   string Extensions::MoreInfoParentDisplayNameProperty
0x20bd7  stloc.s  0xA
0x20bd9  dup
0x20bda  ldloc.s  0xA
0x20bdc  ldloc.s  6
0x20bde  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x20be3  ldnull
0x20be4  ldc.i4.0
0x20be5  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteEvent(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, object, bool)
0x20bea  br       loc_20D0B
0x20bef  ldarg.2
0x20bf0  ldc.i4.0
0x20bf1  conv.i8
0x20bf2  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x20bf7  ldarg.0
0x20bf8  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x20bfd  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.IExtensionServiceInternal Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions::get_ExtensionService()
0x20c02  ldarg.2
0x20c03  ldloc.2
0x20c04  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionDependency::get_Location()
0x20c09  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.IExtensionServiceInternal::GetEmbeddedExtensionStream(class [mscorlib]System.IO.Stream, string)
0x20c0e  stloc.s  0xB
0x20c10  ldloc.s  0xB
0x20c12  brfalse  loc_20C9C
0x20c17  ldarg.0
0x20c18  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x20c1d  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.IExtensionServiceInternal Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions::get_ExtensionService()
0x20c22  ldloc.s  0xB
0x20c24  ldarg.s  4
0x20c26  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.IExtensionService::ParseExtension(class [mscorlib]System.IO.Stream, class [mscorlib]System.Version)
0x20c2b  stloc.s  0xC
0x20c2d  ldloc.s  0xC
0x20c2f  brfalse  loc_20CD2
0x20c34  ldloc.s  0xB
0x20c36  ldc.i4.0
0x20c37  conv.i8
0x20c38  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x20c3d  ldarg.0
0x20c3e  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x20c43  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IHashingService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions::get_HashingService()
0x20c48  ldloc.s  0xB
0x20c4a  ldc.i4.1
0x20c4b  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IHashingService::GetHashOfStream(class [mscorlib]System.IO.Stream, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.HashAlgorithms)
0x20c50  stloc.s  0xD
0x20c52  ldarg.0
0x20c53  ldloc.s  0xC
0x20c55  ldloc.s  0xB
0x20c57  ldarg.3
0x20c58  ldarg.s  4
0x20c5a  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class ExtensionContentsSummary> Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::DownloadEmbeddedExtensions(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents parentExtensionContents, class [mscorlib]System.IO.Stream parentExtensionStream, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionDownloadSummary parentDownloadSummary, class [mscorlib]System.Version productVersion)
0x20c5f  stloc.s  0xE
0x20c61  ldloc.s  0xC
0x20c63  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents::get_CatalogJson()
0x20c68  call     class [System]System.Collections.Generic.ISet`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity> Microsoft.VisualStudio.Setup.Installer.Utilities.Utilities::GetComponentsFromExtensionCatalog(string catalogJson)
0x20c6d  stloc.s  0xF
0x20c6f  ldloc.0
0x20c70  ldloc.2
0x20c71  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionDependency::get_Location()
0x20c76  ldc.i4.2
0x20c77  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x20c7c  ldloc.s  0xC
0x20c7e  ldloc.s  0xE
0x20c80  ldarg.3
0x20c81  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionDownloadSummary::get_VerificationResult()
0x20c86  ldloc.s  0xD
0x20c88  ldarg.3
0x20c89  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionDownloadSummary::get_Certificate()
0x20c8e  ldloc.s  0xF
0x20c90  newobj   instance void ExtensionContentsSummary::.ctor(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents ExtensionContents, class [mscorlib]System.Collections.Generic.IDictionary`2<class [System]System.Uri, class ExtensionContentsSummary> EmbeddedExtensions, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult VerificationResult, string Sha256Hash, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Certificate, class [System]System.Collections.Generic.ISet`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity> ParsedComponents)
0x20c95  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class ExtensionContentsSummary>::Add(var<u1>, !!T0)
0x20c9a  leave.s  loc_20D0B
0x20c9c  ldarg.0
0x20c9d  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x20ca2  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Logger()
0x20ca7  dup
0x20ca8  brtrue.s loc_20CAD
0x20caa  pop
0x20cab  leave.s  loc_20D0B
0x20cad  ldstr    aCouldNotLoadEm// "Could not load embedded extension "
0x20cb2  ldloc.2
0x20cb3  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionDependency::get_Id()
0x20cb8  ldstr    aAt// " at "
0x20cbd  ldloc.2
0x20cbe  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionDependency::get_Location()
0x20cc3  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x20cc8  call     T0x2B000010
0x20ccd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x20cd2  leave.s  loc_20D0B
0x20cd4  ldloc.s  0xB
0x20cd6  brfalse.s loc_20CDF
0x20cd8  ldloc.s  0xB
0x20cda  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20cdf  endfinally
0x20ce0  ldarg.0
0x20ce1  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x20ce6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Logger()
0x20ceb  dup
0x20cec  brtrue.s loc_20CF1
0x20cee  pop
0x20cef  br.s     loc_20D0B
0x20cf1  ldstr    aCannotFindLoca// "Cannot find location for dependency "
0x20cf6  ldloc.2
0x20cf7  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionDependency::get_Id()
0x20cfc  call     string [mscorlib]System.String::Concat(string, string)
0x20d01  call     T0x2B000010
0x20d06  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x20d0b  ldloc.1
0x20d0c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x20d11  brtrue   loc_20A82
0x20d16  leave.s  loc_20D22
0x20d18  ldloc.1
0x20d19  brfalse.s loc_20D21
0x20d1b  ldloc.1
0x20d1c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20d21  endfinally
0x20d22  ldloc.0
0x20d23  ret
```
