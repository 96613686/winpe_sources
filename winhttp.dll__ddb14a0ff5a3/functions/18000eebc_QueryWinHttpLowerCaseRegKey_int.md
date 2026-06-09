# QueryWinHttpLowerCaseRegKey(int *)

- ea: `0x18000eebc`
- end: `0x18000f05b`
- name: `?QueryWinHttpLowerCaseRegKey@@YAJPEAH@Z`
- size: `415`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000eb88`
- `0x18000f744`
- `0x18006f7bc`

## callees

- `0x18000eebc`
- `0x1800a1d10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ef13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ef13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ef42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ef42`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000efde`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000efde`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000efa1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000efa1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ef51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ef51`

## pseudocode

```c

```
