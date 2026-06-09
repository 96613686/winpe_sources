# _ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int,ulong)

- ea: `0x1800887ac`
- end: `0x1800889fd`
- name: `?_ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGHK@Z`
- size: `593`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpValueName@<rdx>, unsigned __int16 **@<r8>, int@<r9d>, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180088110`
- `0x1800881a0`
- `0x1800885bc`

## callees

- `0x180009a98`
- `0x18006fe84`
- `0x18006ff8c`
- `0x1800887ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180088856`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180088940`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180088856`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180088940`
- `ole32!CoTaskMemAlloc` at `0x1800888f4`
- `ole32!CoTaskMemAlloc` at `0x1800888f4`

## string_xrefs

- `0x1800887da`: `_ReadStringFromRegistry`

## pseudocode

```c

```
