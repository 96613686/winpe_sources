# UpdateDialog::.cctor

- ea: `0x65920`
- end: `0x65985`
- name: `UpdateDialog::.cctor`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## string_xrefs

- `0x65975`: `UpdateVersion`
- `0x65925`: `show-updatedialog`

## pseudocode

```c

```

## disassembly

```asm
0x65920  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0x65925  ldstr    aShowUpdatedial// "show-updatedialog"
0x6592a  call     string [mscorlib]System.String::Concat(string, string)
0x6592f  stsfld   string UpdateDialog::ShowUpdateDialogEvent
0x65934  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65939  ldstr    aChannelid// "channelId"
0x6593e  call     string [mscorlib]System.String::Concat(string, string)
0x65943  stsfld   string UpdateDialog::ChannelIdProperty
0x65948  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x6594d  ldstr    aProductid// "productId"
0x65952  call     string [mscorlib]System.String::Concat(string, string)
0x65957  stsfld   string UpdateDialog::ProductIdProperty
0x6595c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65961  ldstr    aCurrentversion_0// "currentVersion"
0x65966  call     string [mscorlib]System.String::Concat(string, string)
0x6596b  stsfld   string UpdateDialog::CurrentVersionProperty
0x65970  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65975  ldstr    aUpdateversion// "UpdateVersion"
0x6597a  call     string [mscorlib]System.String::Concat(string, string)
0x6597f  stsfld   string UpdateDialog::UpdateVersionProperty
0x65984  ret
```
