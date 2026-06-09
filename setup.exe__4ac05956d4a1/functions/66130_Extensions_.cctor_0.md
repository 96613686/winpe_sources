# Extensions::.cctor_0

- ea: `0x66130`
- end: `0x66195`
- name: `Extensions::.cctor_0`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0x6613a`: `individual-components-page`
- `0x66149`: `invalid-extension-name`
- `0x66185`: `download-extensionmodel-failure`

## pseudocode

```c

```

## disassembly

```asm
0x66130  ldstr    aSummaryPane// "summary-pane"
0x66135  stsfld   string Extensions::SummaryPaneSelectionSourceSummaryPaneProperty
0x6613a  ldstr    aIndividualComp// "individual-components-page"
0x6613f  stsfld   string Extensions::SummaryPaneSelectionSourceIndividualComponentsPageProperty
0x66144  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0x66149  ldstr    aInvalidExtensi// "invalid-extension-name"
0x6614e  call     string [mscorlib]System.String::Concat(string, string)
0x66153  stsfld   string Extensions::InvalidExtensionNameEvent
0x66158  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0x6615d  ldstr    aSerializationE// "serialization-error"
0x66162  call     string [mscorlib]System.String::Concat(string, string)
0x66167  stsfld   string Extensions::SerializationErrorEvent
0x6616c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x66171  ldstr    aOperation// "operation"
0x66176  call     string [mscorlib]System.String::Concat(string, string)
0x6617b  stsfld   string Extensions::SerializationErrorOperationTypeProperty
0x66180  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0x66185  ldstr    aDownloadExtens_0// "download-extensionmodel-failure"
0x6618a  call     string [mscorlib]System.String::Concat(string, string)
0x6618f  stsfld   string Extensions::DownloadingExtensionModelFailureEvent
0x66194  ret
```
