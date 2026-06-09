# CAdReader::IsDomainJoined(void)

- ea: `0x180016408`
- end: `0x180016538`
- name: `?IsDomainJoined@CAdReader@@CA_NXZ`
- size: `304`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1800176f4`
- `0x180018064`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x180016408`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `NETAPI32!NetGetJoinInformation` at `0x1800164a4`
- `NETAPI32!NetGetJoinInformation` at `0x1800164a4`
- `NETAPI32!NetApiBufferFree` at `0x1800164c5`
- `NETAPI32!NetApiBufferFree` at `0x1800164c5`

## string_xrefs

- `0x180016440`: `ADREADRC`
- `0x180016428`: `base\fs\fsrm\service\globalstore\adreader.cpp`
- `0x180016434`: `CAdReader::IsDomainJoined`

## pseudocode

```c

```
