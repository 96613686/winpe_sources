# WimIsNetworkPermitted(_DOT11_SSID *,_DOT11_BSS_TYPE,ulong *)

- ea: `0x180013630`
- end: `0x180013ac4`
- name: `?WimIsNetworkPermitted@@YAHPEAU_DOT11_SSID@@W4_DOT11_BSS_TYPE@@PEAK@Z`
- size: `1172`
- prototype: `__int64 __fastcall(struct _DOT11_SSID *, enum _DOT11_BSS_TYPE, unsigned int *)`
- caller_count: `10`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180012900`
- `0x180015a00`
- `0x1800539ac`
- `0x180064040`
- `0x1800aa294`
- `0x18014d180`
- `0x18014d610`
- `0x180151df8`
- `0x180153068`
- `0x180153570`

## callees

- `0x180011530`
- `0x180013630`
- `0x180058d90`
- `0x1800c6774`
- `0x180106340`
- `0x18010730c`
- `0x1801222fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800136de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001372e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800139dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013a4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800136de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001372e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800139dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013a4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001368a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001371b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800139c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001368a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001371b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800139c3`

## pseudocode

```c

```
