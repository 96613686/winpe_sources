# BackgroundDownloadStatus::.cctor

- ea: `0x63970`
- end: `0x639d5`
- name: `BackgroundDownloadStatus::.cctor`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x63989`: `amountDownloaded`
- `0x639b1`: `isComplete`

## pseudocode

```c

```

## disassembly

```asm
0x63970  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SetupEnginePropertyPrefix
0x63975  ldstr    aBackgrounddown_0// "backgroundDownloadStatus."
0x6397a  call     string [mscorlib]System.String::Concat(string, string)
0x6397f  stsfld   string BackgroundDownloadStatus::PropertyPrefix
0x63984  ldsfld   string BackgroundDownloadStatus::PropertyPrefix
0x63989  ldstr    aAmountdownload// "amountDownloaded"
0x6398e  call     string [mscorlib]System.String::Concat(string, string)
0x63993  stsfld   string BackgroundDownloadStatus::AmountDownloadedProperty
0x63998  ldsfld   string BackgroundDownloadStatus::PropertyPrefix
0x6399d  ldstr    aTotalsize// "totalSize"
0x639a2  call     string [mscorlib]System.String::Concat(string, string)
0x639a7  stsfld   string BackgroundDownloadStatus::TotalSizeProperty
0x639ac  ldsfld   string BackgroundDownloadStatus::PropertyPrefix
0x639b1  ldstr    aIscomplete// "isComplete"
0x639b6  call     string [mscorlib]System.String::Concat(string, string)
0x639bb  stsfld   string BackgroundDownloadStatus::IsCompleteProperty
0x639c0  ldsfld   string BackgroundDownloadStatus::PropertyPrefix
0x639c5  ldstr    aPercentdownloa// "percentDownloaded"
0x639ca  call     string [mscorlib]System.String::Concat(string, string)
0x639cf  stsfld   string BackgroundDownloadStatus::PercentDownloadedProperty
0x639d4  ret
```
