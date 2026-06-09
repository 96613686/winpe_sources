# _ReadPolicies(void *,ulong *,_tagEASPolicy * *)

- ea: `0x140013620`
- end: `0x1400139ff`
- name: `?_ReadPolicies@@YAJPEAXPEAKPEAPEAU_tagEASPolicy@@@Z`
- size: `991`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned int *, struct _tagEASPolicy **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140015260`

## callees

- `0x140013620`
- `0x140038250`
- `0x14004ef60`
- `0x140098c6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140013886`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140013886`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400136b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400136b7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14001386b`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14001386b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400139a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400139b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400139e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400139a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400139b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400139e3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140013721`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140013771`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400137c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140013721`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140013771`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400137c7`

## string_xrefs

- `0x1400136f1`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x140013791`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x1400137fe`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x1400138a4`: `onecore\ds\security\eas\policyengine\common.cpp`

## pseudocode

```c

```
