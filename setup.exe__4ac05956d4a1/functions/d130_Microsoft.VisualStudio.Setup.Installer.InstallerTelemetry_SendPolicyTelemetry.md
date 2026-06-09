# Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::SendPolicyTelemetry

- ea: `0xd130`
- end: `0xd4bf`
- name: `Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::SendPolicyTelemetry`
- size: `911`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x6b400`

## callees

- `0xd130`
- `0xdaf0`
- `0xdba0`
- `0xdbf0`
- `0xdc20`

## string_xrefs

- `0xd145`: `AdministratorUpdatesEnabled`
- `0xd17f`: `AdministratorUpdatesOptOut`
- `0xd19c`: `AutoUpdateDisabled`
- `0xd210`: `DisableRollback`
- `0xd267`: `RemoveOos`
- `0xd2be`: `ElevationServiceSupport`
- `0xd2db`: `ChannelUpdateDisabled`
- `0xd332`: `AdministratorUpdatesNotificationsEnabled`
- `0xd34f`: `AdministratorUpdateOnCloseOptOut`
- `0xd36c`: `VSthroughMUUpdatesOptOut`
- `0xd389`: `PreviewAutomaticUpdates`
- `0xd3a6`: `UpdateNotificationsOptOut`
- `0xd421`: `CachePath`
- `0xd43f`: `CompatibilityInstallationPath`
- `0xd45d`: `SharedInstallationPath`

## pseudocode

```c

```

## disassembly

```asm
0xd130  ldloca.s 0
0xd132  ldarg.2
0xd133  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd138  ldarg.1
0xd139  brfalse  loc_D49E
0xd13e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0xd143  stloc.1
0xd144  ldloc.1
0xd145  ldstr    aAdministratoru// "AdministratorUpdatesEnabled"
0xd14a  ldloc.0
0xd14b  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd150  callvirt instance valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.AutomaticUpdatesValue [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_AdministratorUpdatesEnabled()
0xd155  box      [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.AutomaticUpdatesValue
0xd15a  ldloca.s 0
0xd15c  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd161  ldloc.1
0xd162  ldstr    aAdministratorp// "AdministratorPromptToClose"
0xd167  ldloc.0
0xd168  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd16d  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_AdministratorPromptToClose()
0xd172  box      [mscorlib]System.Boolean
0xd177  ldloca.s 0
0xd179  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd17e  ldloc.1
0xd17f  ldstr    aAdministratoru_0// "AdministratorUpdatesOptOut"
0xd184  ldloc.0
0xd185  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd18a  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_AdministratorUpdatesOptOut()
0xd18f  box      [mscorlib]System.Boolean
0xd194  ldloca.s 0
0xd196  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd19b  ldloc.1
0xd19c  ldstr    aAutoupdatedisa// "AutoUpdateDisabled"
0xd1a1  ldloc.0
0xd1a2  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd1a7  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_AutoUpdateDisabled()
0xd1ac  box      [mscorlib]System.Boolean
0xd1b1  ldloca.s 0
0xd1b3  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd1b8  ldloc.1
0xd1b9  ldstr    aBackgrounddown// "BackgroundDownloadDisabled"
0xd1be  ldloc.0
0xd1bf  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd1c4  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_BackgroundDownloadDisabled()
0xd1c9  box      [mscorlib]System.Boolean
0xd1ce  ldloca.s 0
0xd1d0  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd1d5  ldloc.1
0xd1d6  ldstr    aDiagnosticmode// "DiagnosticMode"
0xd1db  ldloc.0
0xd1dc  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd1e1  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_DiagnosticMode()
0xd1e6  box      [mscorlib]System.Boolean
0xd1eb  ldloca.s 0
0xd1ed  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd1f2  ldloc.1
0xd1f3  ldstr    aDisablemicroso// "DisableMicrosoftChannelFeed"
0xd1f8  ldloc.0
0xd1f9  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd1fe  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_DisableMicrosoftChannelFeed()
0xd203  box      [mscorlib]System.Boolean
0xd208  ldloca.s 0
0xd20a  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd20f  ldloc.1
0xd210  ldstr    aDisablerollbac// "DisableRollback"
0xd215  ldloc.0
0xd216  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd21b  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_DisableRollback()
0xd220  box      [mscorlib]System.Boolean
0xd225  ldloca.s 0
0xd227  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd22c  ldloc.1
0xd22d  ldstr    aHideavailablet// "HideAvailableTab"
0xd232  ldloc.0
0xd233  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd238  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_HideAvailableTab()
0xd23d  box      [mscorlib]System.Boolean
0xd242  ldloca.s 0
0xd244  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd249  ldloc.1
0xd24a  ldstr    aIgnorechannelf// "IgnoreChannelFeedProductRestriction"
0xd24f  ldloc.0
0xd250  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd255  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_IgnoreChannelFeedProductRestriction()
0xd25a  box      [mscorlib]System.Boolean
0xd25f  ldloca.s 0
0xd261  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd266  ldloc.1
0xd267  ldstr    aRemoveoos// "RemoveOos"
0xd26c  ldloc.0
0xd26d  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd272  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_RemoveOos()
0xd277  box      [mscorlib]System.Boolean
0xd27c  ldloca.s 0
0xd27e  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd283  ldloc.1
0xd284  ldstr    aDisablesound// "DisableSound"
0xd289  ldloc.0
0xd28a  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd28f  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_DisableSound()
0xd294  box      [mscorlib]System.Boolean
0xd299  ldloca.s 0
0xd29b  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd2a0  ldloc.1
0xd2a1  ldstr    aDisableblocked// "DisableBlockedOSCheck"
0xd2a6  ldloc.0
0xd2a7  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd2ac  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_DisableBlockedOSCheck()
0xd2b1  box      [mscorlib]System.Boolean
0xd2b6  ldloca.s 0
0xd2b8  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd2bd  ldloc.1
0xd2be  ldstr    aElevationservi_4// "ElevationServiceSupport"
0xd2c3  ldloc.0
0xd2c4  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd2c9  callvirt instance valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ElevationServiceSupport [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_ElevationServiceSupport()
0xd2ce  box      [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ElevationServiceSupport
0xd2d3  ldloca.s 0
0xd2d5  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd2da  ldloc.1
0xd2db  ldstr    aChannelupdated// "ChannelUpdateDisabled"
0xd2e0  ldloc.0
0xd2e1  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd2e6  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_ChannelUpdateDisabled()
0xd2eb  box      [mscorlib]System.Boolean
0xd2f0  ldloca.s 0
0xd2f2  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd2f7  ldloc.1
0xd2f8  ldstr    aConcurrentdown// "ConcurrentDownloads"
0xd2fd  ldloc.0
0xd2fe  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd303  callvirt instance int32 [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_ConcurrentDownloads()
0xd308  box      [mscorlib]System.Int32
0xd30d  ldloca.s 0
0xd30f  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd314  ldloc.1
0xd315  ldstr    aKeepdownloaded// "KeepDownloadedPayloads"
0xd31a  ldloc.0
0xd31b  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd320  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_KeepDownloadedPayloads()
0xd325  box      [mscorlib]System.Boolean
0xd32a  ldloca.s 0
0xd32c  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd331  ldloc.1
0xd332  ldstr    aAdministratoru_1// "AdministratorUpdatesNotificationsEnable"...
0xd337  ldloc.0
0xd338  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd33d  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_AdministratorUpdatesNotificationsEnabled()
0xd342  box      [mscorlib]System.Boolean
0xd347  ldloca.s 0
0xd349  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd34e  ldloc.1
0xd34f  ldstr    aAdministratoru_2// "AdministratorUpdateOnCloseOptOut"
0xd354  ldloc.0
0xd355  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd35a  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_AdministratorUpdateOnCloseOptOut()
0xd35f  box      [mscorlib]System.Boolean
0xd364  ldloca.s 0
0xd366  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd36b  ldloc.1
0xd36c  ldstr    aVsthroughmuupd// "VSthroughMUUpdatesOptOut"
0xd371  ldloc.0
0xd372  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd377  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_VSthroughMUUpdatesOptOut()
0xd37c  box      [mscorlib]System.Boolean
0xd381  ldloca.s 0
0xd383  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd388  ldloc.1
0xd389  ldstr    aPreviewautomat// "PreviewAutomaticUpdates"
0xd38e  ldloc.0
0xd38f  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd394  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_PreviewAutomaticUpdates()
0xd399  box      [mscorlib]System.Boolean
0xd39e  ldloca.s 0
0xd3a0  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd3a5  ldloc.1
0xd3a6  ldstr    aUpdatenotifica// "UpdateNotificationsOptOut"
0xd3ab  ldloc.0
0xd3ac  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd3b1  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_UpdateNotificationsOptOut()
0xd3b6  box      [mscorlib]System.Boolean
0xd3bb  ldloca.s 0
0xd3bd  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd3c2  ldloc.1
0xd3c3  ldstr    aProductfeedbac// "ProductFeedbackDisabled"
0xd3c8  ldloc.0
0xd3c9  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd3ce  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_ProductFeedbackDisabled()
0xd3d3  box      [mscorlib]System.Boolean
0xd3d8  ldloca.s 0
0xd3da  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd3df  ldloc.1
0xd3e0  ldstr    aSurveysdisable// "SurveysDisabled"
0xd3e5  ldloc.0
0xd3e6  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd3eb  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_SurveysDisabled()
0xd3f0  box      [mscorlib]System.Boolean
0xd3f5  ldloca.s 0
0xd3f7  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd3fc  ldloc.1
0xd3fd  ldstr    aSkipngenafters// "SkipNgenAfterSetup"
0xd402  ldloc.0
0xd403  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd408  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_SkipNgenAfterSetup()
0xd40d  box      [mscorlib]System.Boolean
0xd412  ldloca.s 0
0xd414  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPolicyTelemetryProperty|1_0(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, valuetype <>c__DisplayClass1_0& properties)
0xd419  ldarg.0
0xd41a  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.DefaultPolicy::.ctor(class [mscorlib]System.IServiceProvider)
0xd41f  stloc.2
0xd420  ldloc.1
0xd421  ldstr    aCachepath// "CachePath"
0xd426  ldloc.0
0xd427  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd42c  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_CachePath()
0xd431  ldloc.2
0xd432  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.DefaultPolicy::get_CachePath()
0xd437  ldloca.s 0
0xd439  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPIITelemetryProperty|1_1(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, object defaultValue, valuetype <>c__DisplayClass1_0& userRequestedOperation)
0xd43e  ldloc.1
0xd43f  ldstr    aCompatibilityi// "CompatibilityInstallationPath"
0xd444  ldloc.0
0xd445  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd44a  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_CompatibilityInstallationPath()
0xd44f  ldloc.2
0xd450  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.DefaultPolicy::get_CompatibilityInstallationPath()
0xd455  ldloca.s 0
0xd457  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPIITelemetryProperty|1_1(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, object defaultValue, valuetype <>c__DisplayClass1_0& userRequestedOperation)
0xd45c  ldloc.1
0xd45d  ldstr    aSharedinstalla// "SharedInstallationPath"
0xd462  ldloc.0
0xd463  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd468  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_SharedInstallationPath()
0xd46d  ldloc.2
0xd46e  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.DefaultPolicy::get_SharedInstallationPath()
0xd473  ldloca.s 0
0xd475  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::<SendPolicyTelemetry>g__setPIITelemetryProperty|1_1(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> properties, string name, object value, object defaultValue, valuetype <>c__DisplayClass1_0& userRequestedOperation)
0xd47a  ldloc.1
0xd47b  ldarg.3
0xd47c  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::AddUpdateRelatedGroupPolicyRegValues(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry registryService)
0xd481  ldloc.1
0xd482  ldloc.0
0xd483  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService <>c__DisplayClass1_0::policyService
0xd488  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::SetAvailableTabProducts(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService policyService)
0xd48d  ldarg.1
0xd48e  brfalse.s loc_D49E
0xd490  ldarg.1
0xd491  ldsfld   string Policy::GroupPolicyEventName
0xd496  ldloc.1
0xd497  ldnull
0xd498  ldc.i4.0
0xd499  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteEvent(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, object, bool)
0xd49e  leave.s  loc_D4BE
0xd4a0  stloc.3
0xd4a1  ldarg.1
0xd4a2  brfalse.s loc_D4BC
0xd4a4  ldarg.1
0xd4a5  ldsfld   string Policy::GroupPolicyErrorEventName
0xd4aa  ldstr    aFailedToRecord// "Failed to record policy settings."
0xd4af  ldnull
0xd4b0  ldloc.3
0xd4b1  ldnull
0xd4b2  ldc.i4.0
0xd4b3  ldnull
0xd4b4  ldc.i4.0
0xd4b5  ldnull
0xd4b6  ldc.i4.0
0xd4b7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0xd4bc  leave.s  loc_D4BE
0xd4be  ret
```
