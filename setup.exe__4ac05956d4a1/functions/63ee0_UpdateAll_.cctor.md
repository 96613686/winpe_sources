# UpdateAll::.cctor

- ea: `0x63ee0`
- end: `0x63f31`
- name: `UpdateAll::.cctor`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## string_xrefs

- `0x63ee5`: `update-all`
- `0x63f0d`: `updatedProductsCount`

## pseudocode

```c

```

## disassembly

```asm
0x63ee0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEngineEventPrefix
0x63ee5  ldstr    aUpdateAll// "update-all"
0x63eea  call     string [mscorlib]System.String::Concat(string, string)
0x63eef  stsfld   string UpdateAll::UpdateAllEvent
0x63ef4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63ef9  ldstr    aTotalupdatable// "totalUpdatableProductsCount"
0x63efe  call     string [mscorlib]System.String::Concat(string, string)
0x63f03  stsfld   string UpdateAll::TotalUpdatableProductsCountProperty
0x63f08  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63f0d  ldstr    aUpdatedproduct// "updatedProductsCount"
0x63f12  call     string [mscorlib]System.String::Concat(string, string)
0x63f17  stsfld   string UpdateAll::UpdatedProductsCountProperty
0x63f1c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63f21  ldstr    aAggregatedresu// "aggregatedResult"
0x63f26  call     string [mscorlib]System.String::Concat(string, string)
0x63f2b  stsfld   string UpdateAll::AggregatedResultProperty
0x63f30  ret
```
