# QuerySwpadEnabledInitOnceCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800c2e20`
- end: `0x1800c2f7d`
- name: `?QuerySwpadEnabledInitOnceCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `349`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800a1d10`
- `0x1800c2e20`
- `0x1800cf008`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c2f37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c2f37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c2edb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c2edb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c2eab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c2eab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c2f1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c2f1a`

## pseudocode

```c

```
