# SampQueryLocalizableAccounts(_PSAMP_DEFINED_DOMAINS *,ulong,ulong,_DOMAIN_LOCALIZABLE_ACCOUNTS * *)

- ea: `0x18006facc`
- end: `0x18006fdb3`
- name: `?SampQueryLocalizableAccounts@@YAJPEAU_PSAMP_DEFINED_DOMAINS@@KKPEAPEAU_DOMAIN_LOCALIZABLE_ACCOUNTS@@@Z`
- size: `743`
- prototype: `int(struct _PSAMP_DEFINED_DOMAINS *, unsigned int, unsigned int, struct _DOMAIN_LOCALIZABLE_ACCOUNTS **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180058db0`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x18002d720`
- `0x1800412cc`
- `0x18006facc`
- `0x180077b3c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006fb7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006fb7d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006fb1c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006fb43`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006fb1c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006fb43`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18006fbad`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18006fbad`

## string_xrefs

- `0x18006fb76`: `SAMSRV.DLL`

## pseudocode

```c

```
