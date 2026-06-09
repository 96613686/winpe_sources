# IsAutoProxyAutoLogonIfChallengedEnabledInitOnce

- ea: `0x180081050`
- end: `0x18008120c`
- name: `IsAutoProxyAutoLogonIfChallengedEnabledInitOnce`
- size: `444`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180081050`
- `0x1800a1d10`
- `0x1800cf124`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180081132`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180081132`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180081103`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180081103`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800810c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800810c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081141`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081141`

## pseudocode

```c

```
