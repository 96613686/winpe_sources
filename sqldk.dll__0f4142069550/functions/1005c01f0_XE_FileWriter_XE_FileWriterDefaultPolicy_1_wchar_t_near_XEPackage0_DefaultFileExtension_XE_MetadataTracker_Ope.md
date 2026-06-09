# XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::OpenAzureContainerIfNeeded(void)

- ea: `0x1005c01f0`
- end: `0x1005c0405`
- name: `?OpenAzureContainerIfNeeded@?$XE_FileWriter@V?$XE_FileWriterDefaultPolicy@$00$1?DefaultFileExtension@XEPackage0@@3PA_WA@@VXE_MetadataTracker@@@@AEAA_NXZ`
- size: `533`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1005be5b0`
- `0x1005bf9c0`

## callees

- `0x100403070`
- `0x100404bf2`
- `0x1005c01f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1005c03b4`
- `KERNEL32!GetLastError` at `0x1005c03b4`
- `VCRUNTIME140!wcschr` at `0x1005c028a`
- `VCRUNTIME140!wcschr` at `0x1005c02a8`
- `VCRUNTIME140!wcschr` at `0x1005c028a`
- `VCRUNTIME140!wcschr` at `0x1005c02a8`

## string_xrefs

- `0x1005c03c2`: `[Error] XESession Target failed to open container %ls. Error %d`

## pseudocode

```c

```
