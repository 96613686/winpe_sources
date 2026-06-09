# MatsHelpers::WriteTelemetryJson(Microsoft::WRL::Wrappers::HString const &,_WLIDResponseParams * *)

- ea: `0x1800f1b50`
- end: `0x1800f1c34`
- name: `?WriteTelemetryJson@MatsHelpers@@CAJAEBVHString@Wrappers@WRL@Microsoft@@PEAPEAU_WLIDResponseParams@@@Z`
- size: `228`
- prototype: `static int(const struct Microsoft::WRL::Wrappers::HString *, struct _WLIDResponseParams **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f12dc`
- `0x1800f143c`

## callees

- `0x18002d36c`
- `0x180030120`
- `0x1800f1b50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f1c07`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f1c07`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800f1bae`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800f1bae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1bd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1bd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800f1ba2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800f1be2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800f1ba2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800f1be2`

## string_xrefs

- `0x1800f1b77`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\matshelpers.cpp`

## pseudocode

```c

```
