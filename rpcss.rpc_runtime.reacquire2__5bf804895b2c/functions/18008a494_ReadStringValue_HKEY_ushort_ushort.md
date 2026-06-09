# ReadStringValue(HKEY__ *,ushort *,ushort * *)

- ea: `0x18008a494`
- end: `0x18008a94d`
- name: `?ReadStringValue@@YAKPEAUHKEY__@@PEAGPEAPEAG@Z`
- size: `1209`
- prototype: `unsigned int __fastcall(HKEY hKey, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010b00`

## callees

- `0x180034260`
- `0x180064ed0`
- `0x1800855d8`
- `0x18008a494`
- `0x1800b7ac0`
- `0x180112d84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a833`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a64e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a7c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a806`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a8a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a8c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a64e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a7c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a806`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a8a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a8c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008a5eb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008a7e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008a5eb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008a7e1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18008a79a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18008a79a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008a4fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008a630`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008a4fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008a630`

## string_xrefs

- `0x18008a561`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x18008a5c2`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x18008a884`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x18008a913`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x18008a555`: `ReadStringValue`
- `0x18008a5bb`: `ReadStringValue`
- `0x18008a86f`: `ReadStringValue`
- `0x18008a8fe`: `ReadStringValue`

## pseudocode

```c

```
