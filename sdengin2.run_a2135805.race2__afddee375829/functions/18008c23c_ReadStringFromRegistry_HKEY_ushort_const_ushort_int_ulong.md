# _ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int,ulong)

- ea: `0x18008c23c`
- end: `0x18008c4a0`
- name: `?_ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGHK@Z`
- size: `612`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpValueName@<rdx>, unsigned __int16 **@<r8>, int@<r9d>, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18008bb6c`
- `0x18008bc00`
- `0x18008c040`

## callees

- `0x180009d0c`
- `0x180072e08`
- `0x180072f14`
- `0x18008c23c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008c2e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008c3dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008c2e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008c3dc`
- `ole32!CoTaskMemAlloc` at `0x18008c38a`
- `ole32!CoTaskMemAlloc` at `0x18008c38a`

## string_xrefs

- `0x18008c26a`: `_ReadStringFromRegistry`

## pseudocode

```c

```
