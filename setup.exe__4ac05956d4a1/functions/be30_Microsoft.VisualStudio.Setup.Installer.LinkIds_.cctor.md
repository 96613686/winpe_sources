# Microsoft.VisualStudio.Setup.Installer.LinkIds::.cctor

- ea: `0xbe30`
- end: `0xbe8b`
- name: `Microsoft.VisualStudio.Setup.Installer.LinkIds::.cctor`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0xbe3a`: `UpdateDetailsUpdatedReleaseNotesLink`
- `0xbe44`: `UpdateDetailsChangeSettingsLink`
- `0xbe4e`: `UpdateDetailsCurrentReleaseNotesLink`
- `0xbe58`: `FooterReleaseNotesLink`
- `0xbe62`: `developer-news-more-news-link`
- `0xbe6c`: `workload-help-link`
- `0xbe76`: `ProductCardUpdateThirdPartyNoticesLink`
- `0xbe80`: `UpdateDialogThirdPartyNoticesLink`

## pseudocode

```c

```

## disassembly

```asm
0xbe30  ldstr    aProductcardpro// "ProductCardProgressReleaseNotes"
0xbe35  stsfld   string Microsoft.VisualStudio.Setup.Installer.LinkIds::ProductCardProgressReleaseNotesId
0xbe3a  ldstr    aUpdatedetailsu// "UpdateDetailsUpdatedReleaseNotesLink"
0xbe3f  stsfld   string Microsoft.VisualStudio.Setup.Installer.LinkIds::UpdateDetailsUpdatedReleaseNotesId
0xbe44  ldstr    aUpdatedetailsc// "UpdateDetailsChangeSettingsLink"
0xbe49  stsfld   string Microsoft.VisualStudio.Setup.Installer.LinkIds::UpdateDetailsChangeSettingsId
0xbe4e  ldstr    aUpdatedetailsc_0// "UpdateDetailsCurrentReleaseNotesLink"
0xbe53  stsfld   string Microsoft.VisualStudio.Setup.Installer.LinkIds::UpdateDetailsCurrentReleaseNotesId
0xbe58  ldstr    aFooterreleasen// "FooterReleaseNotesLink"
0xbe5d  stsfld   string Microsoft.VisualStudio.Setup.Installer.LinkIds::UpdateDialogFooterReleaseNotesId
0xbe62  ldstr    aDeveloperNewsM// "developer-news-more-news-link"
0xbe67  stsfld   string Microsoft.VisualStudio.Setup.Installer.LinkIds::ViewMoreOnlineId
0xbe6c  ldstr    aWorkloadHelpLi// "workload-help-link"
0xbe71  stsfld   string Microsoft.VisualStudio.Setup.Installer.LinkIds::HelpLinkId
0xbe76  ldstr    aProductcardupd// "ProductCardUpdateThirdPartyNoticesLink"
0xbe7b  stsfld   string Microsoft.VisualStudio.Setup.Installer.LinkIds::ProductCardUpdateDialogThirdPartyNoticesLinkId
0xbe80  ldstr    aUpdatedialogth// "UpdateDialogThirdPartyNoticesLink"
0xbe85  stsfld   string Microsoft.VisualStudio.Setup.Installer.LinkIds::UpdateDialogThirdPartyNoticesLinkId
0xbe8a  ret
```
