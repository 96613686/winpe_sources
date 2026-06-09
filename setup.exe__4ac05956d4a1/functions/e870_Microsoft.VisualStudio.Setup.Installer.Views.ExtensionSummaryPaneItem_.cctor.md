# Microsoft.VisualStudio.Setup.Installer.Views.ExtensionSummaryPaneItem::.cctor

- ea: `0xe870`
- end: `0xe885`
- name: `Microsoft.VisualStudio.Setup.Installer.Views.ExtensionSummaryPaneItem::.cctor`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0xe870`: `Extension-Signature`
- `0xe87a`: `No-Extension-Signature`

## pseudocode

```c

```

## disassembly

```asm
0xe870  ldstr    aExtensionSigna_0// "Extension-Signature"
0xe875  stsfld   string Microsoft.VisualStudio.Setup.Installer.Views.ExtensionSummaryPaneItem::ExtensionSignatureTag
0xe87a  ldstr    aNoExtensionSig// "No-Extension-Signature"
0xe87f  stsfld   string Microsoft.VisualStudio.Setup.Installer.Views.ExtensionSummaryPaneItem::ExtensionNoSignatureTag
0xe884  ret
```
