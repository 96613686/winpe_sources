# Extensions::.cctor

- ea: `0x63ce0`
- end: `0x63ec1`
- name: `Extensions::.cctor`
- size: `481`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0x63ce5`: `add-extension-summaries`
- `0x63cf9`: `get-full-extension`
- `0x63d0d`: `get-embedded-extension`
- `0x63d21`: `download-extension`
- `0x63d35`: `absolute-uri-dependency-location`
- `0x63d49`: `supportsExtensions`
- `0x63dad`: `numberOfExtensionsToAdd`
- `0x63dc1`: `numberOfExtensionsAdded`
- `0x63dd5`: `isInvalidExtension`
- `0x63de9`: `InvalidExtensionType`
- `0x63dfd`: `loadedEmbeddedExtensions`
- `0x63e11`: `numberOfEmbeddedExtensions`
- `0x63e25`: `successfulPackedExtensionNames`
- `0x63e39`: `numberOfSuccessfulPackedExtensions`
- `0x63e4d`: `numberOfFailedPackedExtensions`
- `0x63e61`: `validatedExtensionDependencies`

## pseudocode

```c

```

## disassembly

```asm
0x63ce0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x63ce5  ldstr    aAddExtensionSu// "add-extension-summaries"
0x63cea  call     string [mscorlib]System.String::Concat(string, string)
0x63cef  stsfld   string Extensions::AddExtensionSummariesEvent
0x63cf4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x63cf9  ldstr    aGetFullExtensi// "get-full-extension"
0x63cfe  call     string [mscorlib]System.String::Concat(string, string)
0x63d03  stsfld   string Extensions::GetFullExtensionEvent
0x63d08  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x63d0d  ldstr    aGetEmbeddedExt// "get-embedded-extension"
0x63d12  call     string [mscorlib]System.String::Concat(string, string)
0x63d17  stsfld   string Extensions::GetEmbeddedExtensionEvent
0x63d1c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x63d21  ldstr    aDownloadExtens// "download-extension"
0x63d26  call     string [mscorlib]System.String::Concat(string, string)
0x63d2b  stsfld   string Extensions::DownloadExtensionEvent
0x63d30  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x63d35  ldstr    aAbsoluteUriDep// "absolute-uri-dependency-location"
0x63d3a  call     string [mscorlib]System.String::Concat(string, string)
0x63d3f  stsfld   string Extensions::AbsoluteUriDependencyLocationEvent
0x63d44  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63d49  ldstr    aSupportsextens// "supportsExtensions"
0x63d4e  call     string [mscorlib]System.String::Concat(string, string)
0x63d53  stsfld   string Extensions::SupportsExtensionsProperty
0x63d58  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63d5d  ldstr    aResult// "result"
0x63d62  call     string [mscorlib]System.String::Concat(string, string)
0x63d67  stsfld   string Extensions::ResultProperty
0x63d6c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63d71  ldstr    aDownloadsuccee// "downloadSucceeded"
0x63d76  call     string [mscorlib]System.String::Concat(string, string)
0x63d7b  stsfld   string Extensions::DownloadSucceededProperty
0x63d80  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63d85  ldstr    aParsesucceeded// "parseSucceeded"
0x63d8a  call     string [mscorlib]System.String::Concat(string, string)
0x63d8f  stsfld   string Extensions::ParseSucceededProperty
0x63d94  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63d99  ldstr    aReason// "reason"
0x63d9e  call     string [mscorlib]System.String::Concat(string, string)
0x63da3  stsfld   string Extensions::ReasonProperty
0x63da8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63dad  ldstr    aNumberofextens// "numberOfExtensionsToAdd"
0x63db2  call     string [mscorlib]System.String::Concat(string, string)
0x63db7  stsfld   string Extensions::NumberOfExtensionsToAddProperty
0x63dbc  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63dc1  ldstr    aNumberofextens_0// "numberOfExtensionsAdded"
0x63dc6  call     string [mscorlib]System.String::Concat(string, string)
0x63dcb  stsfld   string Extensions::NumberOfExtensionsAddedProperty
0x63dd0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63dd5  ldstr    aIsinvalidexten// "isInvalidExtension"
0x63dda  call     string [mscorlib]System.String::Concat(string, string)
0x63ddf  stsfld   string Extensions::InvalidExtensionProperty
0x63de4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63de9  ldstr    aInvalidextensi// "InvalidExtensionType"
0x63dee  call     string [mscorlib]System.String::Concat(string, string)
0x63df3  stsfld   string Extensions::InvalidExtensionTypeProperty
0x63df8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63dfd  ldstr    aLoadedembedded// "loadedEmbeddedExtensions"
0x63e02  call     string [mscorlib]System.String::Concat(string, string)
0x63e07  stsfld   string Extensions::LoadedEmbeddedExtensionsProperty
0x63e0c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63e11  ldstr    aNumberofembedd// "numberOfEmbeddedExtensions"
0x63e16  call     string [mscorlib]System.String::Concat(string, string)
0x63e1b  stsfld   string Extensions::NumberOfEmbeddedExtensionsProperty
0x63e20  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63e25  ldstr    aSuccessfulpack// "successfulPackedExtensionNames"
0x63e2a  call     string [mscorlib]System.String::Concat(string, string)
0x63e2f  stsfld   string Extensions::SuccessfulPackedExtensionNamesProperty
0x63e34  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63e39  ldstr    aNumberofsucces// "numberOfSuccessfulPackedExtensions"
0x63e3e  call     string [mscorlib]System.String::Concat(string, string)
0x63e43  stsfld   string Extensions::NumberOfSuccessfulPackedExtensionsProperty
0x63e48  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63e4d  ldstr    aNumberoffailed// "numberOfFailedPackedExtensions"
0x63e52  call     string [mscorlib]System.String::Concat(string, string)
0x63e57  stsfld   string Extensions::NumberOfFailedPackedExtensionsProperty
0x63e5c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63e61  ldstr    aValidatedexten// "validatedExtensionDependencies"
0x63e66  call     string [mscorlib]System.String::Concat(string, string)
0x63e6b  stsfld   string Extensions::ValidatedExtensionDependenciesProperty
0x63e70  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63e75  ldstr    aMoreInfoDepend// "more-info-dependencyId"
0x63e7a  call     string [mscorlib]System.String::Concat(string, string)
0x63e7f  stsfld   string Extensions::MoreInfoDependencyIdProperty
0x63e84  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63e89  ldstr    aMoreInfoLocati// "more-info-location"
0x63e8e  call     string [mscorlib]System.String::Concat(string, string)
0x63e93  stsfld   string Extensions::MoreInfoLocationProperty
0x63e98  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63e9d  ldstr    aMoreInfoParent// "more-info-parentVsixId"
0x63ea2  call     string [mscorlib]System.String::Concat(string, string)
0x63ea7  stsfld   string Extensions::MoreInfoParentVsixIdProperty
0x63eac  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63eb1  ldstr    aMoreInfoParent_0// "more-info-parentDisplayName"
0x63eb6  call     string [mscorlib]System.String::Concat(string, string)
0x63ebb  stsfld   string Extensions::MoreInfoParentDisplayNameProperty
0x63ec0  ret
```
