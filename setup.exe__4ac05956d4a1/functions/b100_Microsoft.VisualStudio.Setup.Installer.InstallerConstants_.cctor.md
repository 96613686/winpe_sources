# Microsoft.VisualStudio.Setup.Installer.InstallerConstants::.cctor

- ea: `0xb100`
- end: `0xb27c`
- name: `Microsoft.VisualStudio.Setup.Installer.InstallerConstants::.cctor`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xcd40`

## string_xrefs

- `0xb100`: `https://aka.ms/setup/updatesettings`
- `0xb10a`: `https://aka.ms/vsinstaller/systemrequirements`
- `0xb11e`: `https://aka.ms/vsinstaller/latestdownloads`
- `0xb128`: `https://go.microsoft.com/fwlink/?linkid=849619`
- `0xb132`: `https://go.microsoft.com/fwlink/?linkid=2066144`
- `0xb13c`: `https://go.microsoft.com/fwlink/?linkid=2066242`
- `0xb146`: `https://go.microsoft.com/fwlink/?linkid=834731`
- `0xb161`: `https://go.microsoft.com/fwlink/?linkid=834732`
- `0xb16b`: `https://go.microsoft.com/fwlink/?linkid=857708`
- `0xb175`: `https://aka.ms/vsinstaller/removechannelhelp`
- `0xb17b`: `RemoveChannelHelpLink`
- `0xb18a`: `https://aka.ms/vs/rollback`
- `0xb1c6`: `Microsoft.VisualStudio.Product.Community`
- `0xb1d2`: `Microsoft.VisualStudio.Product.CommunityX86`
- `0xb22b`: `installerTelemetryContext.json`
- `0xb235`: `rollback-from-channel`
- `0xb23f`: `rollback-from-friendlyname`
- `0xb249`: `rollback-from-version`
- `0xb253`: `rollback-to-version`
- `0xb267`: `setup-vs-rollback`
- `0xb271`: `vs-rollback-ticket-source`

## pseudocode

```c

```

## disassembly

```asm
0xb100  ldstr    aHttpsAkaMsSetu// "https://aka.ms/setup/updatesettings"
0xb105  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::ChangeUpdateSettingsUrl
0xb10a  ldstr    aHttpsAkaMsVsin// "https://aka.ms/vsinstaller/systemrequir"...
0xb10f  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::SystemRequirementsUrl
0xb114  ldstr    aVsSetup// "vs-setup"
0xb119  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::SetupExeName
0xb11e  ldstr    aHttpsAkaMsVsin_0// "https://aka.ms/vsinstaller/latestdownlo"...
0xb123  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::LatestVersionDownloadLink
0xb128  ldstr    aHttpsGoMicroso_1// "https://go.microsoft.com/fwlink/?linkid"...
0xb12d  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::TroubleshootingTipsLink
0xb132  ldstr    aHttpsGoMicroso_2// "https://go.microsoft.com/fwlink/?linkid"...
0xb137  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::NewsFeedUrl
0xb13c  ldstr    aHttpsGoMicroso_3// "https://go.microsoft.com/fwlink/?linkid"...
0xb141  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::AllNewsUrl
0xb146  ldstr    aHttpsGoMicroso_4// "https://go.microsoft.com/fwlink/?linkid"...
0xb14b  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::MicrosoftDeveloperCommunityUrl
0xb150  ldstr    aHttpsAkaMsVsst// "https://aka.ms/vsstatus"
0xb155  ldnull
0xb156  ldnull
0xb157  newobj   instance void Microsoft.VisualStudio.Setup.Installer.RichUri::.ctor(string path, [opt] string innerText, [opt] string linkId)
0xb15c  stsfld   class Microsoft.VisualStudio.Setup.Installer.RichUri Microsoft.VisualStudio.Setup.Installer.InstallerConstants::VisualStudioStatusUrl
0xb161  ldstr    aHttpsGoMicroso_5// "https://go.microsoft.com/fwlink/?linkid"...
0xb166  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::VisualStudioSupportUrl
0xb16b  ldstr    aHttpsGoMicroso_6// "https://go.microsoft.com/fwlink/?linkid"...
0xb170  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::FeedbackApiBaseFwlinkUrl
0xb175  ldstr    aHttpsAkaMsVsin_1// "https://aka.ms/vsinstaller/removechanne"...
0xb17a  ldnull
0xb17b  ldstr    aRemovechannelh// "RemoveChannelHelpLink"
0xb180  newobj   instance void Microsoft.VisualStudio.Setup.Installer.RichUri::.ctor(string path, [opt] string innerText, [opt] string linkId)
0xb185  stsfld   class Microsoft.VisualStudio.Setup.Installer.RichUri Microsoft.VisualStudio.Setup.Installer.InstallerConstants::RemoveChannelHelpTextUrl
0xb18a  ldstr    aHttpsAkaMsVsRo// "https://aka.ms/vs/rollback"
0xb18f  ldnull
0xb190  ldnull
0xb191  newobj   instance void Microsoft.VisualStudio.Setup.Installer.RichUri::.ctor(string path, [opt] string innerText, [opt] string linkId)
0xb196  stsfld   class Microsoft.VisualStudio.Setup.Installer.RichUri Microsoft.VisualStudio.Setup.Installer.InstallerConstants::RollbackHelpTextUrl
0xb19b  ldstr    aHttpsAkaMsVsSt// "https://aka.ms/vs/statusapi"
0xb1a0  newobj   instance void [System]System.Uri::.ctor(string)
0xb1a5  stsfld   class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.InstallerConstants::VSStatusPageAPI
0xb1aa  ldstr    aVisualstudiose// "VisualStudioSetup"
0xb1af  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::InstallerNameOnVSStatusPage
0xb1b4  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor()
0xb1b9  dup
0xb1ba  ldstr    aMicrosoftVisua_1// "Microsoft.VisualStudio.Product.Ssms"
0xb1bf  ldc.i4.0
0xb1c0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::set_Item(var<u1>, !!T0)
0xb1c5  dup
0xb1c6  ldstr    aMicrosoftVisua_2// "Microsoft.VisualStudio.Product.Communit"...
0xb1cb  ldc.i4.1
0xb1cc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::set_Item(var<u1>, !!T0)
0xb1d1  dup
0xb1d2  ldstr    aMicrosoftVisua_3// "Microsoft.VisualStudio.Product.Communit"...
0xb1d7  ldc.i4.1
0xb1d8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::set_Item(var<u1>, !!T0)
0xb1dd  dup
0xb1de  ldstr    aMicrosoftVisua_4// "Microsoft.VisualStudio.Product.Professi"...
0xb1e3  ldc.i4.2
0xb1e4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::set_Item(var<u1>, !!T0)
0xb1e9  dup
0xb1ea  ldstr    aMicrosoftVisua_5// "Microsoft.VisualStudio.Product.Professi"...
0xb1ef  ldc.i4.2
0xb1f0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::set_Item(var<u1>, !!T0)
0xb1f5  dup
0xb1f6  ldstr    aMicrosoftVisua_6// "Microsoft.VisualStudio.Product.Enterpri"...
0xb1fb  ldc.i4.3
0xb1fc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::set_Item(var<u1>, !!T0)
0xb201  dup
0xb202  ldstr    aMicrosoftVisua_7// "Microsoft.VisualStudio.Product.Enterpri"...
0xb207  ldc.i4.3
0xb208  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::set_Item(var<u1>, !!T0)
0xb20d  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, int32> Microsoft.VisualStudio.Setup.Installer.InstallerConstants::DefaultProductOrder
0xb212  ldstr    aRemotechannels// "_RemoteChannels"
0xb217  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::RemoteChannelSubdirectoryName
0xb21c  ldstr    aHttpAkaMsVsWor// "http://aka.ms/vs_workloads"
0xb221  newobj   instance void [System]System.Uri::.ctor(string)
0xb226  stsfld   class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.InstallerConstants::DefaultHelpLinkUri
0xb22b  ldstr    aInstallertelem// "installerTelemetryContext.json"
0xb230  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::InstallerTelemetryContextFileName
0xb235  ldstr    aRollbackFromCh// "rollback-from-channel"
0xb23a  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::RollbackFromChannelTag
0xb23f  ldstr    aRollbackFromFr// "rollback-from-friendlyname"
0xb244  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::RollbackFromFriendlyNameTag
0xb249  ldstr    aRollbackFromVe// "rollback-from-version"
0xb24e  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::RollbackFromVersionTag
0xb253  ldstr    aRollbackToVers// "rollback-to-version"
0xb258  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::RollbackToVersionTag
0xb25d  ldstr    aSourceDialog// "source-dialog"
0xb262  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::RollbackSourceDialogTag
0xb267  ldstr    aSetupVsRollbac// "setup-vs-rollback"
0xb26c  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::RollbackSourceDialogValueTag
0xb271  ldstr    aVsRollbackTick// "vs-rollback-ticket-source"
0xb276  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::RollbackTicketSourceTag
0xb27b  ret
```
