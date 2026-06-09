# ChannelMigration::.cctor

- ea: `0x64100`
- end: `0x6422d`
- name: `ChannelMigration::.cctor`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0x6412d`: `configure-migration`
- `0x64169`: `channelUpdateUri`
- `0x6417d`: `includeMarketplaceExtensions`
- `0x641cd`: `hasClonePath`
- `0x641e1`: `isFromCommandLine`
- `0x6421d`: `includeRecommendedOnUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x64100  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x64105  ldstr    aChannelmigrati_0// "channelmigration/"
0x6410a  call     string [mscorlib]System.String::Concat(string, string)
0x6410f  stsfld   string ChannelMigration::EventPrefix
0x64114  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x64119  ldstr    aChannelmigrati_1// "channelmigration."
0x6411e  call     string [mscorlib]System.String::Concat(string, string)
0x64123  stsfld   string ChannelMigration::PropertyPrefix
0x64128  ldsfld   string ChannelMigration::EventPrefix
0x6412d  ldstr    aConfigureMigra// "configure-migration"
0x64132  call     string [mscorlib]System.String::Concat(string, string)
0x64137  stsfld   string ChannelMigration::ChannelMigrationHandleConfigureEvent
0x6413c  ldsfld   string ChannelMigration::EventPrefix
0x64141  ldstr    aInitDialog// "init-dialog"
0x64146  call     string [mscorlib]System.String::Concat(string, string)
0x6414b  stsfld   string ChannelMigration::ChannelMigrationInitEvent
0x64150  ldsfld   string ChannelMigration::EventPrefix
0x64155  ldstr    aHandlerError// "handler-error"
0x6415a  call     string [mscorlib]System.String::Concat(string, string)
0x6415f  stsfld   string ChannelMigration::ChannelMigrationHandlerFaultEvent
0x64164  ldsfld   string ChannelMigration::PropertyPrefix
0x64169  ldstr    aChannelupdateu// "channelUpdateUri"
0x6416e  call     string [mscorlib]System.String::Concat(string, string)
0x64173  stsfld   string ChannelMigration::ChannelUpdateUri
0x64178  ldsfld   string ChannelMigration::PropertyPrefix
0x6417d  ldstr    aIncludemarketp_1// "includeMarketplaceExtensions"
0x64182  call     string [mscorlib]System.String::Concat(string, string)
0x64187  stsfld   string ChannelMigration::IncludeMarketplaceExtensions
0x6418c  ldsfld   string ChannelMigration::PropertyPrefix
0x64191  ldstr    aIncludeoutofsu_1// "includeOutOfSupport"
0x64196  call     string [mscorlib]System.String::Concat(string, string)
0x6419b  stsfld   string ChannelMigration::IncludeOutOfSupport
0x641a0  ldsfld   string ChannelMigration::PropertyPrefix
0x641a5  ldstr    aMigratefromins_1// "migrateFromInstance"
0x641aa  call     string [mscorlib]System.String::Concat(string, string)
0x641af  stsfld   string ChannelMigration::MigrateFromInstance
0x641b4  ldsfld   string ChannelMigration::PropertyPrefix
0x641b9  ldstr    aProductid// "productId"
0x641be  call     string [mscorlib]System.String::Concat(string, string)
0x641c3  stsfld   string ChannelMigration::ProductId
0x641c8  ldsfld   string ChannelMigration::PropertyPrefix
0x641cd  ldstr    aHasclonepath// "hasClonePath"
0x641d2  call     string [mscorlib]System.String::Concat(string, string)
0x641d7  stsfld   string ChannelMigration::HasClonePath
0x641dc  ldsfld   string ChannelMigration::PropertyPrefix
0x641e1  ldstr    aIsfromcommandl// "isFromCommandLine"
0x641e6  call     string [mscorlib]System.String::Concat(string, string)
0x641eb  stsfld   string ChannelMigration::IsFromCommandLine
0x641f0  ldsfld   string ChannelMigration::PropertyPrefix
0x641f5  ldstr    aMigrationcandi_0// "migrationCandidateCount"
0x641fa  call     string [mscorlib]System.String::Concat(string, string)
0x641ff  stsfld   string ChannelMigration::MigrationCandidateCount
0x64204  ldsfld   string ChannelMigration::PropertyPrefix
0x64209  ldstr    aSelectedmigrat_0// "selectedMigrationCandidateType"
0x6420e  call     string [mscorlib]System.String::Concat(string, string)
0x64213  stsfld   string ChannelMigration::SelectedMigrationCandidateType
0x64218  ldsfld   string ChannelMigration::PropertyPrefix
0x6421d  ldstr    aIncluderecomme_2// "includeRecommendedOnUpdate"
0x64222  call     string [mscorlib]System.String::Concat(string, string)
0x64227  stsfld   string ChannelMigration::IncludeRecommendedOnUpdate
0x6422c  ret
```
