# GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x1800566cc`
- end: `0x180056a9a`
- name: `?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z`
- size: `974`
- prototype: `__int64 __usercall@<rax>(HKEY hkey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValue@<r8>, unsigned int@<r9d>, unsigned __int16 **)`
- caller_count: `10`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180038d84`
- `0x18005e598`
- `0x18005fde4`
- `0x180061b6c`
- `0x180073bd4`
- `0x1800cb334`
- `0x1800cba8c`
- `0x1800cbc2c`
- `0x1800cbe78`
- `0x1800e7ca4`

## callees

- `0x180034540`
- `0x1800566cc`
- `0x18008150c`
- `0x18009ffc0`
- `0x1800a12c4`
- `0x1800b3128`
- `0x1800ccbd4`
- `0x18010a084`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005682d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800569bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056a81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005682d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800569bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056a81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056742`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056985`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056742`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056985`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005671c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005678e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005671c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005678e`

## string_xrefs

- `0x1800567f9`: `onecore\com\combase\catalog\services.cxx`
- `0x180056916`: `onecore\com\combase\catalog\services.cxx`
- `0x1800569f0`: `onecore\com\combase\catalog\services.cxx`
- `0x180056a59`: `onecore\com\combase\catalog\services.cxx`
- `0x1800567ee`: `GetRegistryStringValue`
- `0x18005690a`: `GetRegistryStringValue`
- `0x1800569e4`: `GetRegistryStringValue`
- `0x180056a4d`: `GetRegistryStringValue`
- `0x1800569f7`: `GetRegistryStringValue returning %ws`

## pseudocode

```c

```
