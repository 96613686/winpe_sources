# Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::.cctor

- ea: `0x9620`
- end: `0x9b3f`
- name: `Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::.cctor`
- size: `1311`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x9652`: `initialize-updatedialog`
- `0x967f`: `uninstall-installer`
- `0x9693`: `update-installer`
- `0x96a7`: `finalize-installerupdate`
- `0x96bb`: `installertype`
- `0x96cf`: `finalize-install`
- `0x96e3`: `unobservedtaskexception`
- `0x97e7`: `installSessionId`
- `0x9a67`: `commandline-import-configuration-error`
- `0x9ab7`: `rollback.from`
- `0x9acb`: `rollback.to`
- `0x9adf`: `update-channel-error`
- `0x9b07`: `remoteLinkId`

## pseudocode

```c

```

## disassembly

```asm
0x9620  ldstr    aVsSetupengine// "vs/setupengine/"
0x9625  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x962a  ldstr    aVsSetupengine_0// "VS.SetupEngine."
0x962f  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x9634  ldstr    aPerf// "perf/"
0x9639  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::PerfInfix
0x963e  ldstr    aBulletins// "bulletins/"
0x9643  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::BulletinsInfix
0x9648  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x964d  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::PerfInfix
0x9652  ldstr    aInitializeUpda// "initialize-updatedialog"
0x9657  call     string [mscorlib]System.String::Concat(string, string, string)
0x965c  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::PerfInitializeUpdateDialogEvent
0x9661  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x9666  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::PerfInfix
0x966b  ldstr    aInitializeIpa// "initialize-ipa"
0x9670  call     string [mscorlib]System.String::Concat(string, string, string)
0x9675  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::PerfInitializeIPAEvent
0x967a  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x967f  ldstr    aUninstallInsta// "uninstall-installer"
0x9684  call     string [mscorlib]System.String::Concat(string, string)
0x9689  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::UninstallInstallerEvent
0x968e  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x9693  ldstr    aUpdateInstalle// "update-installer"
0x9698  call     string [mscorlib]System.String::Concat(string, string)
0x969d  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::UpdateInstallerEvent
0x96a2  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x96a7  ldstr    aFinalizeInstal// "finalize-installerupdate"
0x96ac  call     string [mscorlib]System.String::Concat(string, string)
0x96b1  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::FinalizeInstallerUpdateEvent
0x96b6  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x96bb  ldstr    aInstallertype// "installertype"
0x96c0  call     string [mscorlib]System.String::Concat(string, string)
0x96c5  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::InstallerTypeProperty
0x96ca  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x96cf  ldstr    aFinalizeInstal_0// "finalize-install"
0x96d4  call     string [mscorlib]System.String::Concat(string, string)
0x96d9  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::FinalizeInstallEvent
0x96de  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x96e3  ldstr    aUnobservedtask// "unobservedtaskexception"
0x96e8  call     string [mscorlib]System.String::Concat(string, string)
0x96ed  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::UnobservedTaskExceptionEvent
0x96f2  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x96f7  ldstr    aWindowLoaded// "window/loaded"
0x96fc  call     string [mscorlib]System.String::Concat(string, string)
0x9701  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::WindowLoadedEvent
0x9706  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x970b  ldstr    aWindowtype// "windowtype"
0x9710  call     string [mscorlib]System.String::Concat(string, string)
0x9715  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::WindowTypeProperty
0x971a  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x971f  ldstr    aTimesinceappst// "timesinceappstart"
0x9724  call     string [mscorlib]System.String::Concat(string, string)
0x9729  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::TimeSinceAppStartProperty
0x972e  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x9733  ldstr    aInitTelemetry// "init-telemetry"
0x9738  call     string [mscorlib]System.String::Concat(string, string)
0x973d  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::TelemetryInitializedEvent
0x9742  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x9747  ldstr    aOperationdurat// "operationduration"
0x974c  call     string [mscorlib]System.String::Concat(string, string)
0x9751  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::OperationDurationProperty
0x9756  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x975b  ldstr    aChangeTheme// "change-theme"
0x9760  call     string [mscorlib]System.String::Concat(string, string)
0x9765  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ThemeChangedEvent
0x976a  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x976f  ldstr    aThemechangedfr// "themechangedfrom"
0x9774  call     string [mscorlib]System.String::Concat(string, string)
0x9779  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ThemeChangedFromProperty
0x977e  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x9783  ldstr    aThemechangedto// "themechangedto"
0x9788  call     string [mscorlib]System.String::Concat(string, string)
0x978d  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ThemeChangedToProperty
0x9792  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x9797  ldstr    aThemesaved// "themesaved"
0x979c  call     string [mscorlib]System.String::Concat(string, string)
0x97a1  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ThemeSavedProperty
0x97a6  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x97ab  ldstr    aInitTheme// "init-theme"
0x97b0  call     string [mscorlib]System.String::Concat(string, string)
0x97b5  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ThemeLoadededEvent
0x97ba  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x97bf  ldstr    aTheme// "theme"
0x97c4  call     string [mscorlib]System.String::Concat(string, string)
0x97c9  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ThemeProperty
0x97ce  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x97d3  ldstr    aLoadTelemetryc// "load-telemetrycontext-error"
0x97d8  call     string [mscorlib]System.String::Concat(string, string)
0x97dd  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::LoadTelemetryContextFailEvent
0x97e2  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x97e7  ldstr    aInstallsession// "installSessionId"
0x97ec  call     string [mscorlib]System.String::Concat(string, string)
0x97f1  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::LoadTelemetryContextSessionIdProperty
0x97f6  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x97fb  ldstr    aSaveTelemetryc// "save-telemetrycontext-error"
0x9800  call     string [mscorlib]System.String::Concat(string, string)
0x9805  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SaveTelemetryContextFailEvent
0x980a  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x980f  ldstr    aWasnull// "wasnull"
0x9814  call     string [mscorlib]System.String::Concat(string, string)
0x9819  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SaveTelemetryContextGuidNullProperty
0x981e  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x9823  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::BulletinsInfix
0x9828  ldstr    aGetBulletinsEr// "get-bulletins-error"
0x982d  call     string [mscorlib]System.String::Concat(string, string, string)
0x9832  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::GetBulletinActionsFaultEvent
0x9837  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x983c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::BulletinsInfix
0x9841  ldstr    aGetBulletinsTi// "get-bulletins-timeout"
0x9846  call     string [mscorlib]System.String::Concat(string, string, string)
0x984b  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::GetBulletinActionsTimeoutEvent
0x9850  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x9855  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::BulletinsInfix
0x985a  ldstr    aShowBulletin// "show-bulletin"
0x985f  call     string [mscorlib]System.String::Concat(string, string, string)
0x9864  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ShowBulletinEvent
0x9869  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x986e  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::BulletinsInfix
0x9873  ldstr    aCollapseBullet// "collapse-bulletins"
0x9878  call     string [mscorlib]System.String::Concat(string, string, string)
0x987d  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::CollapseBulletinEvent
0x9882  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x9887  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::BulletinsInfix
0x988c  ldstr    aExpandBulletin// "expand-bulletins"
0x9891  call     string [mscorlib]System.String::Concat(string, string, string)
0x9896  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ExpandBulletinEvent
0x989b  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x98a0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::BulletinsInfix
0x98a5  ldstr    aClickThumbsup// "click-thumbsup"
0x98aa  call     string [mscorlib]System.String::Concat(string, string, string)
0x98af  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ThumbsUpClickedEvent
0x98b4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x98b9  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::BulletinsInfix
0x98be  ldstr    aClickThumbsdow// "click-thumbsdown"
0x98c3  call     string [mscorlib]System.String::Concat(string, string, string)
0x98c8  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ThumbsDownClickedEvent
0x98cd  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x98d2  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::BulletinsInfix
0x98d7  ldstr    aShowBulletinIn// "show-bulletin-initial-state"
0x98dc  call     string [mscorlib]System.String::Concat(string, string, string)
0x98e1  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ShowBulletinInitialStateEvent
0x98e6  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x98eb  ldstr    aBulletinid// "bulletinId"
0x98f0  call     string [mscorlib]System.String::Concat(string, string)
0x98f5  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::BulletinIdProperty
0x98fa  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x98ff  ldstr    aRuleid// "ruleId"
0x9904  call     string [mscorlib]System.String::Concat(string, string)
0x9909  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::BulletinRuleIdProperty
0x990e  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x9913  ldstr    aCarouselid// "carouselId"
0x9918  call     string [mscorlib]System.String::Concat(string, string)
0x991d  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::CarouselIdProperty
0x9922  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x9927  ldstr    aBulletinversio// "bulletinVersionRange"
0x992c  call     string [mscorlib]System.String::Concat(string, string)
0x9931  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::CarouselVersionRangeProperty
0x9936  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x993b  ldstr    aBulletinchanne// "bulletinChannelIds"
0x9940  call     string [mscorlib]System.String::Concat(string, string)
0x9945  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::CarouselChannelIdsProperty
0x994a  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x994f  ldstr    aBulletinworklo// "bulletinWorkloadIds"
0x9954  call     string [mscorlib]System.String::Concat(string, string)
0x9959  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::CarouselWorkloadIdsProperty
0x995e  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x9963  ldstr    aBulletinpolici// "bulletinPolicies"
0x9968  call     string [mscorlib]System.String::Concat(string, string)
0x996d  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::CarouselPoliciesProperty
0x9972  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x9977  ldstr    aIscarouselbutt// "iscarouselbuttonclicked"
0x997c  call     string [mscorlib]System.String::Concat(string, string)
0x9981  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::BulletinCarouselButtonClickedProperty
0x9986  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x998b  ldstr    aIscollapsed// "iscollapsed"
0x9990  call     string [mscorlib]System.String::Concat(string, string)
0x9995  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::IsCollapsedProperty
0x999a  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x999f  ldstr    aConvertBulleti// "convert-bulletin-error"
0x99a4  call     string [mscorlib]System.String::Concat(string, string)
0x99a9  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ConvertBulletinErrorEvent
0x99ae  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x99b3  ldstr    aShowVssettings// "show-vssettings"
0x99b8  call     string [mscorlib]System.String::Concat(string, string)
0x99bd  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ShowVSSettingsEvent
0x99c2  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x99c7  ldstr    aExpandVssettin// "expand-vssettings"
0x99cc  call     string [mscorlib]System.String::Concat(string, string)
0x99d1  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::VSSettingsExpandedEvent
0x99d6  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x99db  ldstr    aInitializeLigh// "initialize-lightbox-error"
0x99e0  call     string [mscorlib]System.String::Concat(string, string)
0x99e5  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::InitializeLightBoxFailEvent
0x99ea  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x99ef  ldstr    aApprunError// "apprun-error"
0x99f4  call     string [mscorlib]System.String::Concat(string, string)
0x99f9  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ApplicationFaultEvent
0x99fe  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x9a03  ldstr    aElevationGetWi// "elevation-get-windowhandle-error"
0x9a08  call     string [mscorlib]System.String::Concat(string, string)
0x9a0d  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ElevationGetWindowHandleFaultEvent
0x9a12  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x9a17  ldstr    aLaunchProduct// "launch-product"
0x9a1c  call     string [mscorlib]System.String::Concat(string, string)
0x9a21  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::LaunchProductEventName
0x9a26  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x9a2b  ldstr    aProductid// "productId"
0x9a30  call     string [mscorlib]System.String::Concat(string, string)
0x9a35  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ProductIdProperty
0x9a3a  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x9a3f  ldstr    aChannelid// "channelId"
0x9a44  call     string [mscorlib]System.String::Concat(string, string)
0x9a49  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ChannelIdProperty
0x9a4e  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x9a53  ldstr    aIsautolaunch// "isAutolaunch"
0x9a58  call     string [mscorlib]System.String::Concat(string, string)
0x9a5d  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::IsAutolaunchProperty
0x9a62  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x9a67  ldstr    aCommandlineImp// "commandline-import-configuration-error"
0x9a6c  call     string [mscorlib]System.String::Concat(string, string)
0x9a71  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SelectionInitializerFaultEvent
0x9a76  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x9a7b  ldstr    aInitializertyp// "initializertype"
0x9a80  call     string [mscorlib]System.String::Concat(string, string)
0x9a85  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SelectionInitializerTypeProperty
0x9a8a  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x9a8f  ldstr    aStack// "stack"
0x9a94  call     string [mscorlib]System.String::Concat(string, string)
0x9a99  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::StackProperty
0x9a9e  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x9aa3  ldstr    aErrorcode// "errorcode"
0x9aa8  call     string [mscorlib]System.String::Concat(string, string)
0x9aad  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ErrorCodeProperty
0x9ab2  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x9ab7  ldstr    aRollbackFrom// "rollback.from"
0x9abc  call     string [mscorlib]System.String::Concat(string, string)
0x9ac1  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::RollbackFromProperty
0x9ac6  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x9acb  ldstr    aRollbackTo// "rollback.to"
0x9ad0  call     string [mscorlib]System.String::Concat(string, string)
0x9ad5  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::RollbackToProperty
0x9ada  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x9adf  ldstr    aUpdateChannelE// "update-channel-error"
0x9ae4  call     string [mscorlib]System.String::Concat(string, string)
0x9ae9  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::UpdateChannelFaultEvent
0x9aee  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x9af3  ldstr    aDismissRemotes// "dismiss-remotestatus"
0x9af8  call     string [mscorlib]System.String::Concat(string, string)
0x9afd  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::DismissRemoteStatusBarEvent
0x9b02  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x9b07  ldstr    aRemotelinkid// "remoteLinkId"
0x9b0c  call     string [mscorlib]System.String::Concat(string, string)
0x9b11  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::RemoteStatusLinkProperty
0x9b16  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x9b1b  ldstr    aRemotenoticeid// "remoteNoticeId"
0x9b20  call     string [mscorlib]System.String::Concat(string, string)
0x9b25  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::RemoteStatusNoticeIdProperty
0x9b2a  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x9b2f  ldstr    aSetProcessrigh// "set-processrights-error"
0x9b34  call     string [mscorlib]System.String::Concat(string, string)
0x9b39  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetElevatedProcessRightsErrorEvent
0x9b3e  ret
```
