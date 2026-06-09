# CFciConfigObject::SetAttributeValueToObjectValue(ushort const *,ushort const *,ulong,CFG_ATTRIB_ASSOC const *)

- ea: `0x180033f34`
- end: `0x1800343a2`
- name: `?SetAttributeValueToObjectValue@CFciConfigObject@@CAXPEBG0KPEBUCFG_ATTRIB_ASSOC@@@Z`
- size: `1134`
- prototype: `static void(const unsigned __int16 *, const unsigned __int16 *, unsigned int, const struct CFG_ATTRIB_ASSOC *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x180032eb8`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x180010bc4`
- `0x1800161d0`
- `0x18003191c`
- `0x180031b54`
- `0x180033f34`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!_wtoi` at `0x18003413e`
- `msvcrt!_wtoi` at `0x18003413e`
- `msvcrt!_wcstoui64` at `0x1800340b5`
- `msvcrt!_wcstoui64` at `0x180034115`
- `msvcrt!_wcstoui64` at `0x1800340b5`
- `msvcrt!_wcstoui64` at `0x180034115`
- `msvcrt!_errno` at `0x180034151`
- `msvcrt!_errno` at `0x180034151`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800340cd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800340d8`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800340cd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800340d8`

## string_xrefs

- `0x180033f6f`: `base\fs\fsrm\service\globalstore\fciconfigobject.cpp`
- `0x180033f7b`: `CFciConfigObject::SetAttributeValueToObjectValue`

## pseudocode

```c

```
