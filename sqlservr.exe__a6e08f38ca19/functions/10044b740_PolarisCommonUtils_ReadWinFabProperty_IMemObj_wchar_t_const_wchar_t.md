# PolarisCommonUtils::ReadWinFabProperty(IMemObj *,wchar_t const *,wchar_t * *)

- ea: `0x10044b740`
- end: `0x10044b880`
- name: `?ReadWinFabProperty@PolarisCommonUtils@@SAJPEAVIMemObj@@PEB_WPEAPEA_W@Z`
- size: `320`
- prototype: `__int64 __fastcall(struct IMemObj *, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10044b1d0`

## callees

- `0x10044b740`

## import_xrefs

- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10044b806`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10044b806`
- `hostregdll!HostReg_GetPropertyValueAsBinary` at `0x10044b7be`
- `hostregdll!HostReg_GetPropertyValueAsBinary` at `0x10044b849`
- `hostregdll!HostReg_GetPropertyValueAsBinary` at `0x10044b7be`
- `hostregdll!HostReg_GetPropertyValueAsBinary` at `0x10044b849`
- `hostregdll!HostReg_GetApplicationName` at `0x10044b784`
- `hostregdll!HostReg_GetApplicationName` at `0x10044b784`

## string_xrefs

- `0x10044b7dd`: `sql\ntdbms\msql\proc\PolarisCommonUtils.cpp`

## pseudocode

```c

```
