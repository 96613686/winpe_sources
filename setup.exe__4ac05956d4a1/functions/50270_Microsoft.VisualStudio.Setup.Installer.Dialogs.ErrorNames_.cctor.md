# Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::.cctor

- ea: `0x50270`
- end: `0x50433`
- name: `Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::.cctor`
- size: `451`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0x50284`: `Uninstall clicked`
- `0x5028e`: `Repair clicked`
- `0x50298`: `Deselecting required workloads/components`
- `0x502a2`: `Installer update required`
- `0x502ac`: `A product matching command line parameters not found`
- `0x502b6`: `Cannot remove a product with installed products`
- `0x502c0`: `Remove channel clicked`
- `0x502ca`: `No update available.`
- `0x502de`: `Export installation configuration success`
- `0x502e8`: `Failed to import configuration`
- `0x502f2`: `Failed to export configuration`
- `0x502fc`: `Unsupported command supplied for retired channel`
- `0x50306`: `The product attempting to be installed is not applicable to this system`
- `0x5031a`: `Recommend workload selection`
- `0x50324`: `ManifestSignatureVerificationFailedError`
- `0x5032e`: `A channels update is in progress, try again later`
- `0x50338`: `Cannot start another instance of the installer while one instance is running`
- `0x50356`: `The install operation failed`
- `0x50360`: `Failed to remove channel`
- `0x503a6`: `Failed to update all products`
- `0x503ba`: `Reboot recommended`
- `0x503ce`: `Rollback clicked`
- `0x503d8`: `Rollback warning dialog accepted`
- `0x503ec`: `Confirmation to remove out-of-support components`
- `0x503f6`: `There are no out-of-support components to remove`
- `0x50400`: `Removing out-of-support components due to policy/persistence setting.`
- `0x5040a`: `Confirmation to install private extensions via vsconfig.`
- `0x50414`: `Extensions are not yet fully downloaded`
- `0x5041e`: `Extensions are not validly signed`
- `0x50428`: `Couldn't get the component from either the components or the extensions dictionary in the summary pane.`

## pseudocode

```c

```

## disassembly

```asm
0x50270  ldstr    aCannotCloseWin// "Cannot close window while operation is "...
0x50275  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::WindowCloseWhileOperationIsRunning
0x5027a  ldstr    aRebootRequired// "Reboot required"
0x5027f  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::RebootRequired
0x50284  ldstr    aUninstallClick// "Uninstall clicked"
0x50289  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::UninstallPrompt
0x5028e  ldstr    aRepairClicked// "Repair clicked"
0x50293  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::RepairPrompt
0x50298  ldstr    aDeselectingReq// "Deselecting required workloads/componen"...
0x5029d  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::DeselectRequiredPackagePrompt
0x502a2  ldstr    aInstallerUpdat// "Installer update required"
0x502a7  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::InstallerUpdateRequired
0x502ac  ldstr    aAProductMatchi// "A product matching command line paramet"...
0x502b1  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::MatchingProductNotFound
0x502b6  ldstr    aCannotRemoveAP// "Cannot remove a product with installed "...
0x502bb  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::CannotRemoveChannelsWithInstalledProducts
0x502c0  ldstr    aRemoveChannelC// "Remove channel clicked"
0x502c5  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::RemoveChannelClicked
0x502ca  ldstr    aNoUpdateAvaila// "No update available."
0x502cf  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::NoUpdate
0x502d4  ldstr    aFailedToSelect// "Failed to select some artifacts"
0x502d9  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::ArtifactSelectionFailedWarning
0x502de  ldstr    aExportInstalla// "Export installation configuration succe"...
0x502e3  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::ExportConfigSucceeded
0x502e8  ldstr    aFailedToImport// "Failed to import configuration"
0x502ed  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::ImportConfigFailed
0x502f2  ldstr    aFailedToExport// "Failed to export configuration"
0x502f7  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::ExportConfigFailed
0x502fc  ldstr    aUnsupportedCom_0// "Unsupported command supplied for retire"...
0x50301  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::UnsupportedCommandForRetiredChannel
0x50306  ldstr    aTheProductAtte// "The product attempting to be installed "...
0x5030b  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::InapplicableProduct
0x50310  ldstr    aFailedToSelect_0// "Failed to select the product or clone s"...
0x50315  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::NoProductFoundToClone
0x5031a  ldstr    aRecommendWorkl// "Recommend workload selection"
0x5031f  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::RecommendWorkloadSelection
0x50324  ldstr    aManifestsignat// "ManifestSignatureVerificationFailedErro"...
0x50329  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::ManifestSignatureFailure
0x5032e  ldstr    aAChannelsUpdat// "A channels update is in progress, try a"...
0x50333  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::ChannelsLocked
0x50338  ldstr    aCannotStartAno// "Cannot start another instance of the in"...
0x5033d  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::OneInstance
0x50342  ldstr    aFailedToDownlo// "Failed to download channel"
0x50347  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::FailedToDownloadChannel
0x5034c  ldstr    aAnExceptionHap_0// "An exception happened while Initializin"...
0x50351  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::InitializeVMFailed
0x50356  ldstr    aTheInstallOper// "The install operation failed"
0x5035b  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::GenericOperationFailureError
0x50360  ldstr    aFailedToRemove_1// "Failed to remove channel"
0x50365  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::RemoveChannelFailure
0x5036a  ldstr    aDidnTFindSpeci// "Didn't find specified product in channe"...
0x5036f  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::ChannelProductMismatch
0x50374  ldstr    aProductIsPause// "Product is paused and doesn't support c"...
0x50379  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::PausedProductCommandLineBlockerError
0x5037e  ldstr    aAnExceptionHap_1// "An exception happened while initializin"...
0x50383  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::InitializeLightBoxFailed
0x50388  ldstr    aCanceledbyprec_0// "CanceledByPrecheck"
0x5038d  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::CanceledByPrecheck
0x50392  ldstr    aMessagebus// "MessageBus"
0x50397  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::MessageBus
0x5039c  ldstr    aFailedToChange_0// "Failed to change channel"
0x503a1  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::ChangeChannelFailure
0x503a6  ldstr    aFailedToUpdate// "Failed to update all products"
0x503ab  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::UpdateAllFailure
0x503b0  ldstr    aInvalidChannel// "Invalid channel for hopping"
0x503b5  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::InvalidChannelForHopping
0x503ba  ldstr    aRebootRecommen// "Reboot recommended"
0x503bf  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::RebootRecommended
0x503c4  ldstr    aFailedToLaunch// "Failed to launch product"
0x503c9  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::LaunchFailure
0x503ce  ldstr    aRollbackClicke// "Rollback clicked"
0x503d3  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::RollbackPrompt
0x503d8  ldstr    aRollbackWarnin// "Rollback warning dialog accepted"
0x503dd  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::RollbackWarningAcceptedPrompt
0x503e2  ldstr    aNoPreviousVers// "No previous version available."
0x503e7  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::NoPrevious
0x503ec  ldstr    aConfirmationTo// "Confirmation to remove out-of-support c"...
0x503f1  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::DeselectOosPackagePrompt
0x503f6  ldstr    aThereAreNoOutO// "There are no out-of-support components "...
0x503fb  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::NoOosPackageToRemovePrompt
0x50400  ldstr    aRemovingOutOfS// "Removing out-of-support components due "...
0x50405  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::RemoveOosComponentsInfoForPersistence
0x5040a  ldstr    aConfirmationTo_0// "Confirmation to install private extensi"...
0x5040f  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::PrivateExtensionWarning
0x50414  ldstr    aExtensionsAreN// "Extensions are not yet fully downloaded"
0x50419  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::ExtensionsNotDownloadedWarning
0x5041e  ldstr    aExtensionsAreN_0// "Extensions are not validly signed"
0x50423  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::ExtensionsInvalidlySignedError
0x50428  ldstr    aCouldnTGetTheC_0// "Couldn't get the component from either "...
0x5042d  stsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::GetSummaryPaneComponentIdFailedError
0x50432  ret
```
