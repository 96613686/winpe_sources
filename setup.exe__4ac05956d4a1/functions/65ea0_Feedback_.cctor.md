# Feedback::.cctor

- ea: `0x65ea0`
- end: `0x65f7d`
- name: `Feedback::.cctor`
- size: `221`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x65ea5`: `open-vsfeedback`
- `0x65eb9`: `open-vsfeedback-error`

## pseudocode

```c

```

## disassembly

```asm
0x65ea0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0x65ea5  ldstr    aOpenVsfeedback// "open-vsfeedback"
0x65eaa  call     string [mscorlib]System.String::Concat(string, string)
0x65eaf  stsfld   string Feedback::OpenFeedbackEvent
0x65eb4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0x65eb9  ldstr    aOpenVsfeedback_0// "open-vsfeedback-error"
0x65ebe  call     string [mscorlib]System.String::Concat(string, string)
0x65ec3  stsfld   string Feedback::OpenFeedbackErrorEvent
0x65ec8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65ecd  ldstr    aExename// "exeName"
0x65ed2  call     string [mscorlib]System.String::Concat(string, string)
0x65ed7  stsfld   string Feedback::ExeNameProperty
0x65edc  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65ee1  ldstr    aExeversion// "exeVersion"
0x65ee6  call     string [mscorlib]System.String::Concat(string, string)
0x65eeb  stsfld   string Feedback::ExeVersionProperty
0x65ef0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65ef5  ldstr    aOs// "os"
0x65efa  call     string [mscorlib]System.String::Concat(string, string)
0x65eff  stsfld   string Feedback::OsProperty
0x65f04  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65f09  ldstr    aCulture// "culture"
0x65f0e  call     string [mscorlib]System.String::Concat(string, string)
0x65f13  stsfld   string Feedback::CultureProperty
0x65f18  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65f1d  ldstr    aUiculture// "uiCulture"
0x65f22  call     string [mscorlib]System.String::Concat(string, string)
0x65f27  stsfld   string Feedback::UiCultureProperty
0x65f2c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65f31  ldstr    aSessionid// "sessionId"
0x65f36  call     string [mscorlib]System.String::Concat(string, string)
0x65f3b  stsfld   string Feedback::SessionIdProperty
0x65f40  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65f45  ldstr    aIsmicrosoftint// "isMicrosoftInternal"
0x65f4a  call     string [mscorlib]System.String::Concat(string, string)
0x65f4f  stsfld   string Feedback::IsMicrosoftInternalProperty
0x65f54  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65f59  ldstr    aChannelids// "channelIds"
0x65f5e  call     string [mscorlib]System.String::Concat(string, string)
0x65f63  stsfld   string Feedback::ChannelIdsProperty
0x65f68  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65f6d  ldstr    aIssuggestion// "isSuggestion"
0x65f72  call     string [mscorlib]System.String::Concat(string, string)
0x65f77  stsfld   string Feedback::IsSuggestionFeedbackProperty
0x65f7c  ret
```
