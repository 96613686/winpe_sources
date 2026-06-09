# GetProcessName(ulong,CVssAutoString<CVssAutoLocalPtr<ushort *>> &)

- ea: `0x140070da0`
- end: `0x140070fc3`
- name: `?GetProcessName@@YAXKAEAV?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@@Z`
- size: `547`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140038a30`
- `0x140054884`
- `0x1400b9a3c`

## callees

- `0x14000e640`
- `0x1400137c0`
- `0x140013b00`
- `0x140031730`
- `0x14003c174`
- `0x140070da0`
- `0x140070fcc`
- `0x1400921dc`
- `0x1400921e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070e60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070f2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070e60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070f2b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140070e42`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140070e42`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140070ee5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140070ee5`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x140070f21`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x140070f21`

## string_xrefs

- `0x140070dbe`: `base\stor\vss\modules\sec\security.cxx`
- `0x140070eb3`: `OpenProcess`

## pseudocode

```c

```
