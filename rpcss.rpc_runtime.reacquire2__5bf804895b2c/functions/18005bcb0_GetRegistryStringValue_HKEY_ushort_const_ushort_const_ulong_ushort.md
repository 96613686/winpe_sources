# GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x18005bcb0`
- end: `0x18005c0ad`
- name: `?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z`
- size: `1021`
- prototype: `__int64 __usercall@<rax>(HKEY hkey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValue@<r8>, unsigned int@<r9d>, unsigned __int16 **)`
- caller_count: `10`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180040264`
- `0x180063694`
- `0x180064f44`
- `0x180067128`
- `0x1800782dc`
- `0x1800d1474`
- `0x1800d1c38`
- `0x1800d1de0`
- `0x1800d2040`
- `0x1800ef344`

## callees

- `0x180034260`
- `0x18005bcb0`
- `0x1800858f0`
- `0x1800a543c`
- `0x1800a6768`
- `0x1800b8428`
- `0x1800d2e14`
- `0x180112d84`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005be27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005bfc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c08d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005be27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005bfc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c08d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005bd2c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005bf85`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005bd2c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005bf85`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005bd00`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005bd7e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005bd00`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005bd7e`

## string_xrefs

- `0x18005bdf3`: `onecore\com\combase\catalog\services.cxx`
- `0x18005bf16`: `onecore\com\combase\catalog\services.cxx`
- `0x18005bffc`: `onecore\com\combase\catalog\services.cxx`
- `0x18005c065`: `onecore\com\combase\catalog\services.cxx`
- `0x18005bde8`: `GetRegistryStringValue`
- `0x18005bf0a`: `GetRegistryStringValue`
- `0x18005bff0`: `GetRegistryStringValue`
- `0x18005c059`: `GetRegistryStringValue`
- `0x18005c003`: `GetRegistryStringValue returning %ws`

## pseudocode

```c

```
