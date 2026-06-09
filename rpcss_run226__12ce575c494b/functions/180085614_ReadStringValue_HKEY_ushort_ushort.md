# ReadStringValue(HKEY__ *,ushort *,ushort * *)

- ea: `0x180085614`
- end: `0x180085a82`
- name: `?ReadStringValue@@YAKPEAUHKEY__@@PEAGPEAPEAG@Z`
- size: `1134`
- prototype: `unsigned int __fastcall(HKEY hKey, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a1ac`

## callees

- `0x180034540`
- `0x1800611d8`
- `0x180081210`
- `0x180085614`
- `0x1800b27e0`
- `0x18010a084`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008597b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008597b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800857b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008591c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180085954`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800859e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800859fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800857b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008591c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180085954`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800859e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800859fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180085765`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180085935`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180085765`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180085935`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800858fe`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800858fe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008567a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800857a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008567a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800857a0`

## string_xrefs

- `0x1800856db`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x18008573c`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x1800859c6`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x180085a49`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x1800856cf`: `ReadStringValue`
- `0x180085735`: `ReadStringValue`
- `0x1800859b1`: `ReadStringValue`
- `0x180085a34`: `ReadStringValue`

## pseudocode

```c

```
