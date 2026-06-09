# Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::.cctor

- ea: `0xb580`
- end: `0xbe19`
- name: `Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::.cctor`
- size: `2201`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0xb5d5`: `downloadThenInstall`
- `0xb639`: `AllowMUUpdateService`
- `0xb64d`: `installWhileDownloading`
- `0xb661`: `nocache`
- `0xb689`: `noUpdateInstaller`
- `0xb6b1`: `updatePhase`
- `0xb6c5`: `includeRecommended`
- `0xb715`: `UpdateVersion`
- `0xb779`: `initialize-updatedetails`
- `0xb7b5`: `hasEngineUpdate`
- `0xb87d`: `withConfig`
- `0xb8f5`: `elevated-install-product`
- `0xb909`: `selfupdate-install-product`
- `0xb91d`: `detected-app-update`
- `0xb945`: `CommonErrorsCount`
- `0xb96d`: `InstallerErrorsCount`
- `0xb995`: `clicked-link`
- `0xb9bd`: `linkId`
- `0xb9d1`: `absoluteUri`
- `0xb9f9`: `BrowserWindow/create-window`
- `0xba35`: `ComponentSelection`
- `0xba49`: `ExtensionSelection`
- `0xba85`: `isExtension`
- `0xba99`: `extensionId`
- `0xbaad`: `extensionName`
- `0xbad5`: `areComponentsFiltered`
- `0xbae9`: `componentIds`
- `0xbb39`: `FocusedWindow/select-component`
- `0xbb61`: `isConfigPackage`
- `0xbc29`: `filter-components`
- `0xbc79`: `remove-channel`
- `0xbcb5`: `received-productupdate-notification`
- `0xbcdd`: `wasManifestUpdated`
- `0xbcf1`: `wasChannelFeedUpdated`
- `0xbd05`: `show-commonerrorsolution`
- `0xbd19`: `timeout-commonerrorsolution-store`
- `0xbd55`: `viewMoreInfoLink`
- `0xbd69`: `hide-help-link`
- `0xbd7d`: `show-help-link`
- `0xbda5`: `open-log-error`
- `0xbdb9`: `parse-commandline`
- `0xbdcd`: `start-commandline-op`
- `0xbde1`: `end-commandline-op`
- `0xbe09`: `get-summarypanecomponentid-error`

## pseudocode

```c

```

## disassembly

```asm
0xb580  ldstr    aVsWillow// "vs/willow/"
0xb585  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xb58a  ldstr    aVsWillow_0// "vs.willow."
0xb58f  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb594  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xb599  ldstr    aUnhandledexcep// "UnhandledExceptionThrown"
0xb59e  call     string [mscorlib]System.String::Concat(string, string)
0xb5a3  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::UnhandledExceptionEvent
0xb5a8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb5ad  ldstr    aAction// "action"
0xb5b2  call     string [mscorlib]System.String::Concat(string, string)
0xb5b7  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::InstallerActionProperty
0xb5bc  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb5c1  ldstr    aIsfocusedui// "isfocusedui"
0xb5c6  call     string [mscorlib]System.String::Concat(string, string)
0xb5cb  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::IsFocusedUiProperty
0xb5d0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb5d5  ldstr    aDownloadthenin// "downloadThenInstall"
0xb5da  call     string [mscorlib]System.String::Concat(string, string)
0xb5df  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::DownloadThenInstallProperty
0xb5e4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xb5e9  ldstr    aDetectedAbnorm// "detected-abnormalshutdown"
0xb5ee  call     string [mscorlib]System.String::Concat(string, string)
0xb5f3  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::AbnormalShutdownDetectedEvent
0xb5f8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb5fd  ldstr    aAbnormalshutdo// "abnormalShutdownSession"
0xb602  call     string [mscorlib]System.String::Concat(string, string)
0xb607  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::AbnormalShutdownSessionProperty
0xb60c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xb611  ldstr    aElevationrequi// "elevationRequiredError"
0xb616  call     string [mscorlib]System.String::Concat(string, string)
0xb61b  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ElevationRequiredErrorEvent
0xb620  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb625  ldstr    aVerb// "verb"
0xb62a  call     string [mscorlib]System.String::Concat(string, string)
0xb62f  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::VerbProperty
0xb634  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb639  ldstr    aAllowmuupdates// "AllowMUUpdateService"
0xb63e  call     string [mscorlib]System.String::Concat(string, string)
0xb643  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::AllowMUUpdateServiceProperty
0xb648  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb64d  ldstr    aInstallwhiledo// "installWhileDownloading"
0xb652  call     string [mscorlib]System.String::Concat(string, string)
0xb657  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::InstallWhileDownloadingProperty
0xb65c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb661  ldstr    aNocache// "nocache"
0xb666  call     string [mscorlib]System.String::Concat(string, string)
0xb66b  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::NoCacheProperty
0xb670  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb675  ldstr    aNorestart// "noRestart"
0xb67a  call     string [mscorlib]System.String::Concat(string, string)
0xb67f  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::NoRestartProperty
0xb684  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb689  ldstr    aNoupdateinstal// "noUpdateInstaller"
0xb68e  call     string [mscorlib]System.String::Concat(string, string)
0xb693  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::NoUpdateInstallerProperty
0xb698  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb69d  ldstr    aUserrequestedo// "userRequestedOperation"
0xb6a2  call     string [mscorlib]System.String::Concat(string, string)
0xb6a7  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::UserRequestedOperationProperty
0xb6ac  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb6b1  ldstr    aUpdatephase// "updatePhase"
0xb6b6  call     string [mscorlib]System.String::Concat(string, string)
0xb6bb  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::UpdatePhaseProperty
0xb6c0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb6c5  ldstr    aIncluderecomme// "includeRecommended"
0xb6ca  call     string [mscorlib]System.String::Concat(string, string)
0xb6cf  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::IncludeRecommendedProperty
0xb6d4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb6d9  ldstr    aIncludeoptiona// "includeOptional"
0xb6de  call     string [mscorlib]System.String::Concat(string, string)
0xb6e3  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::IncludeOptionalProperty
0xb6e8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xb6ed  ldstr    aGetReleasenote// "get-releasenotes"
0xb6f2  call     string [mscorlib]System.String::Concat(string, string)
0xb6f7  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::GetReleaseNotes
0xb6fc  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb701  ldstr    aCurrentversion// "CurrentVersion"
0xb706  call     string [mscorlib]System.String::Concat(string, string)
0xb70b  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::InstalledVersion
0xb710  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb715  ldstr    aUpdateversion// "UpdateVersion"
0xb71a  call     string [mscorlib]System.String::Concat(string, string)
0xb71f  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::UpdateVersion
0xb724  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb729  ldstr    aSku// "Sku"
0xb72e  call     string [mscorlib]System.String::Concat(string, string)
0xb733  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::TargetedSku
0xb738  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb73d  ldstr    aChannel// "Channel"
0xb742  call     string [mscorlib]System.String::Concat(string, string)
0xb747  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::TargetedChannel
0xb74c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb751  ldstr    aShowdefaulrele// "ShowDefaulReleasenotes"
0xb756  call     string [mscorlib]System.String::Concat(string, string)
0xb75b  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::DefaultReleaseNotes
0xb760  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb765  ldstr    aTimeout// "Timeout"
0xb76a  call     string [mscorlib]System.String::Concat(string, string)
0xb76f  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ReleaseNotesTimeout
0xb774  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xb779  ldstr    aInitializeUpda_0// "initialize-updatedetails"
0xb77e  call     string [mscorlib]System.String::Concat(string, string)
0xb783  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::InitializeUpdateDetails
0xb788  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb78d  ldstr    aAdvertisedpack// "AdvertisedPackagesShown"
0xb792  call     string [mscorlib]System.String::Concat(string, string)
0xb797  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::AdvertisedPackagesShown
0xb79c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb7a1  ldstr    aReleasenotessh// "ReleaseNotesShown"
0xb7a6  call     string [mscorlib]System.String::Concat(string, string)
0xb7ab  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ReleaseNotesShown
0xb7b0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb7b5  ldstr    aHasengineupdat// "hasEngineUpdate"
0xb7ba  call     string [mscorlib]System.String::Concat(string, string)
0xb7bf  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::HasEngineUpdate
0xb7c4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xb7c9  ldstr    aToggleAutolaun// "toggle-autolaunch"
0xb7ce  call     string [mscorlib]System.String::Concat(string, string)
0xb7d3  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ToggleAutoLaunchEvent
0xb7d8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb7dd  ldstr    aCheckboxstate// "checkboxState"
0xb7e2  call     string [mscorlib]System.String::Concat(string, string)
0xb7e7  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::AutoLaunchCheckBoxProperty
0xb7ec  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xb7f1  ldstr    aShowErrordialo// "show-errordialog"
0xb7f6  call     string [mscorlib]System.String::Concat(string, string)
0xb7fb  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ShowErrorDialogEvent
0xb800  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb805  ldstr    aRecordederrorn// "recordedErrorName"
0xb80a  call     string [mscorlib]System.String::Concat(string, string)
0xb80f  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::RecordedErrorNameProperty
0xb814  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb819  ldstr    aUseraction// "userAction"
0xb81e  call     string [mscorlib]System.String::Concat(string, string)
0xb823  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::UserActionProperty
0xb828  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb82d  ldstr    aButtonname// "buttonName"
0xb832  call     string [mscorlib]System.String::Concat(string, string)
0xb837  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ButtonNameProperty
0xb83c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xb841  ldstr    aShowFocusedUi// "show-focused-ui"
0xb846  call     string [mscorlib]System.String::Concat(string, string)
0xb84b  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ShowFocusedUiEvent
0xb850  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb855  ldstr    aRequestedopera// "requestedOperation"
0xb85a  call     string [mscorlib]System.String::Concat(string, string)
0xb85f  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::RequestedOperationProperty
0xb864  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb869  ldstr    aActualoperatio// "actualOperation"
0xb86e  call     string [mscorlib]System.String::Concat(string, string)
0xb873  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ActualOperationProperty
0xb878  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb87d  ldstr    aWithconfig// "withConfig"
0xb882  call     string [mscorlib]System.String::Concat(string, string)
0xb887  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WithConfigProperty
0xb88c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb891  ldstr    aWithpackages// "withPackages"
0xb896  call     string [mscorlib]System.String::Concat(string, string)
0xb89b  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WithAddProperty
0xb8a0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xb8a5  ldstr    aPage// "page"
0xb8aa  call     string [mscorlib]System.String::Concat(string, string)
0xb8af  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::PageEvent
0xb8b4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb8b9  ldstr    aPagename// "pagename"
0xb8be  call     string [mscorlib]System.String::Concat(string, string)
0xb8c3  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::PageNameProperty
0xb8c8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb8cd  ldstr    aMessage// "message"
0xb8d2  call     string [mscorlib]System.String::Concat(string, string)
0xb8d7  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::MessageProperty
0xb8dc  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xb8e1  ldstr    aButton// "button"
0xb8e6  call     string [mscorlib]System.String::Concat(string, string)
0xb8eb  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ButtonEvent
0xb8f0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xb8f5  ldstr    aElevatedInstal// "elevated-install-product"
0xb8fa  call     string [mscorlib]System.String::Concat(string, string)
0xb8ff  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ElevatedInstallProductEvent
0xb904  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xb909  ldstr    aSelfupdateInst// "selfupdate-install-product"
0xb90e  call     string [mscorlib]System.String::Concat(string, string)
0xb913  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::SelfUpdateInstallProductEvent
0xb918  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xb91d  ldstr    aDetectedAppUpd// "detected-app-update"
0xb922  call     string [mscorlib]System.String::Concat(string, string)
0xb927  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::SelfUpdateDetectedEvent
0xb92c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xb931  ldstr    aGetErrordetail// "Get-ErrorDetails"
0xb936  call     string [mscorlib]System.String::Concat(string, string)
0xb93b  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::GetErrorDetails
0xb940  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb945  ldstr    aCommonerrorsco// "CommonErrorsCount"
0xb94a  call     string [mscorlib]System.String::Concat(string, string)
0xb94f  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::CommonErrorCount
0xb954  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb959  ldstr    aPackageerrorsc// "PackageErrorsCount"
0xb95e  call     string [mscorlib]System.String::Concat(string, string)
0xb963  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::PackageErrorCount
0xb968  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb96d  ldstr    aInstallererror// "InstallerErrorsCount"
0xb972  call     string [mscorlib]System.String::Concat(string, string)
0xb977  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::InstallerErrorCount
0xb97c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb981  ldstr    aGenericerrorsc// "GenericErrorsCount"
0xb986  call     string [mscorlib]System.String::Concat(string, string)
0xb98b  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::GenericErrorCount
0xb990  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xb995  ldstr    aClickedLink// "clicked-link"
0xb99a  call     string [mscorlib]System.String::Concat(string, string)
0xb99f  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ClickedLink
0xb9a4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb9a9  ldstr    aInnertext// "innerText"
0xb9ae  call     string [mscorlib]System.String::Concat(string, string)
0xb9b3  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::InnerText
0xb9b8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb9bd  ldstr    aLinkid// "linkId"
0xb9c2  call     string [mscorlib]System.String::Concat(string, string)
0xb9c7  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::LinkId
0xb9cc  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xb9d1  ldstr    aAbsoluteuri// "absoluteUri"
0xb9d6  call     string [mscorlib]System.String::Concat(string, string)
0xb9db  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::AbsoluteUri
0xb9e0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xb9e5  ldstr    aAppStartOptedO// "app-start-opted-out"
0xb9ea  call     string [mscorlib]System.String::Concat(string, string)
0xb9ef  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::AppStartOptedOutEvent
0xb9f4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xb9f9  ldstr    aBrowserwindowC// "BrowserWindow/create-window"
0xb9fe  call     string [mscorlib]System.String::Concat(string, string)
0xba03  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::MainWindowCreateEvent
0xba08  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xba0d  ldstr    aBrowserwindowS// "BrowserWindow/Show"
0xba12  call     string [mscorlib]System.String::Concat(string, string)
0xba17  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::MainWindowShowEvent
0xba1c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xba21  ldstr    aWorkloadselect// "WorkloadSelection"
0xba26  call     string [mscorlib]System.String::Concat(string, string)
0xba2b  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WorkloadSelectionEvent
0xba30  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xba35  ldstr    aComponentselec// "ComponentSelection"
0xba3a  call     string [mscorlib]System.String::Concat(string, string)
0xba3f  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ComponentSelectionEvent
0xba44  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xba49  ldstr    aExtensionselec// "ExtensionSelection"
0xba4e  call     string [mscorlib]System.String::Concat(string, string)
0xba53  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ExtensionSelectionEvent
0xba58  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xba5d  ldstr    aWorkloadid// "workloadId"
0xba62  call     string [mscorlib]System.String::Concat(string, string)
0xba67  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WorkloadIdProperty
0xba6c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xba71  ldstr    aWorkloadname// "workloadName"
0xba76  call     string [mscorlib]System.String::Concat(string, string)
0xba7b  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WorkloadNameProperty
0xba80  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xba85  ldstr    aIsextension// "isExtension"
0xba8a  call     string [mscorlib]System.String::Concat(string, string)
0xba8f  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::IsExtensionProperty
0xba94  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xba99  ldstr    aExtensionid// "extensionId"
0xba9e  call     string [mscorlib]System.String::Concat(string, string)
0xbaa3  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ExtensionIdProperty
0xbaa8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xbaad  ldstr    aExtensionname// "extensionName"
0xbab2  call     string [mscorlib]System.String::Concat(string, string)
0xbab7  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ExtensionNameProperty
0xbabc  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xbac1  ldstr    aSource// "source"
0xbac6  call     string [mscorlib]System.String::Concat(string, string)
0xbacb  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::SourceProperty
0xbad0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xbad5  ldstr    aArecomponentsf// "areComponentsFiltered"
0xbada  call     string [mscorlib]System.String::Concat(string, string)
0xbadf  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::AreComponentsFilteredProperty
0xbae4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xbae9  ldstr    aComponentids// "componentIds"
0xbaee  call     string [mscorlib]System.String::Concat(string, string)
0xbaf3  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ComponentIdsProperty
0xbaf8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xbafd  ldstr    aLanguageselect// "LanguageSelection"
0xbb02  call     string [mscorlib]System.String::Concat(string, string)
0xbb07  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::LanguageSelectionEvent
0xbb0c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xbb11  ldstr    aLocale// "locale"
0xbb16  call     string [mscorlib]System.String::Concat(string, string)
0xbb1b  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::LocaleProperty
0xbb20  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xbb25  ldstr    aFocusedwindowS// "FocusedWindow/select-workload"
0xbb2a  call     string [mscorlib]System.String::Concat(string, string)
0xbb2f  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::FocusedWindowWorkloadSelectionEvent
0xbb34  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0xbb39  ldstr    aFocusedwindowS_0// "FocusedWindow/select-component"
0xbb3e  call     string [mscorlib]System.String::Concat(string, string)
0xbb43  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::FocusedWindowComponentSelectionEvent
0xbb48  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0xbb4d  ldstr    aPackageid// "packageId"
0xbb52  call     string [mscorlib]System.String::Concat(string, string)
0xbb57  stsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::PackageIdProperty
  ... truncated ...
```
