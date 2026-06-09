# BlbGetReparseDirectoryNameForMountedVolume(ushort *,ushort *,ushort * *)

- ea: `0x1400fefd4`
- end: `0x1400ff234`
- name: `?BlbGetReparseDirectoryNameForMountedVolume@@YAJPEAG0PEAPEAG@Z`
- size: `608`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, service_task`

## callers

- `0x1400ff23c`
- `0x14011de34`

## callees

- `0x1400063b4`
- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb4c`
- `0x14001358c`
- `0x140014260`
- `0x14003c9cc`
- `0x14006a01c`
- `0x1400fefd4`
- `0x140134d20`

## import_xrefs

- `USER32!CharUpperBuffW` at `0x1400ff0be`
- `USER32!CharUpperBuffW` at `0x1400ff0be`
- `msvcrt!swscanf_s` at `0x1400ff108`
- `msvcrt!swscanf_s` at `0x1400ff108`
- `ole32!CoTaskMemAlloc` at `0x1400ff184`
- `ole32!CoTaskMemAlloc` at `0x1400ff184`
- `ole32!CoTaskMemFree` at `0x1400ff1c6`
- `ole32!CoTaskMemFree` at `0x1400ff1c6`
- `OLEAUT32!__imp_SysFreeString` at `0x1400ff20a`
- `OLEAUT32!__imp_SysFreeString` at `0x1400ff20a`
- `OLEAUT32!__imp_SysStringLen` at `0x1400ff0a6`
- `OLEAUT32!__imp_SysStringLen` at `0x1400ff0b3`
- `OLEAUT32!__imp_SysStringLen` at `0x1400ff0a6`
- `OLEAUT32!__imp_SysStringLen` at `0x1400ff0b3`

## string_xrefs

- `0x1400ff01c`: `wszMountedDeviceName`
- `0x1400ff04e`: `pwszReparsePointName`
- `0x1400ff160`: `WsbMountedVolumeFile%lu_%s`

## pseudocode

```c

```
