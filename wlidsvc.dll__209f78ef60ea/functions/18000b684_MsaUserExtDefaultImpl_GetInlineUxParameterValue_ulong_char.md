# MsaUserExtDefaultImpl::GetInlineUxParameterValue(ulong,char * *)

- ea: `0x18000b684`
- end: `0x18000b86f`
- name: `?GetInlineUxParameterValue@MsaUserExtDefaultImpl@@YAJKPEAPEAD@Z`
- size: `491`
- prototype: `__int64 __fastcall(MsaUserExtDefaultImpl *__hidden this, unsigned int, char **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180047b5c`

## callees

- `0x18000a354`
- `0x18000b684`
- `0x18000c050`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18004e41c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b78c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b78c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b830`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b830`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b7d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b7d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b71f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b71f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b74d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b74d`

## string_xrefs

- `0x18000b768`: `TokenBroker`
- `0x18000b7e5`: `hr = spCopy.Allocate(bytesNeeded)`
- `0x18000b7c4`: `hr = StringCbCopyA(spCopy, bytesNeeded, inlineUxParam)`

## pseudocode

```c

```
