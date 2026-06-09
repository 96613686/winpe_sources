# WinHttpEtwBeginActivityIdInternal(_GUID const *,ulong,_GUID *,int *)

- ea: `0x180033190`
- end: `0x1800333fc`
- name: `?WinHttpEtwBeginActivityIdInternal@@YAXPEBU_GUID@@KPEAU1@PEAH@Z`
- size: `620`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, struct _GUID *, int *)`
- caller_count: `9`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180004720`
- `0x1800141e0`
- `0x18002a260`
- `0x180031490`
- `0x180037b20`
- `0x1800600c0`
- `0x18007f428`
- `0x180096560`
- `0x1800b12bc`

## callees

- `0x180033190`
- `0x180033404`
- `0x18009013c`
- `0x1800a1d10`
- `0x1800cdd70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800332c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800332c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800332b8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800332b8`
- `ntdll!EtwEventActivityIdControl` at `0x180033267`
- `ntdll!EtwEventActivityIdControl` at `0x18003331b`
- `ntdll!EtwEventActivityIdControl` at `0x180033267`
- `ntdll!EtwEventActivityIdControl` at `0x18003331b`

## pseudocode

```c

```
