# CSdCommonImpl::_IsValidStagingArea(ushort const *,unsigned __int64 *)

- ea: `0x18004c4c4`
- end: `0x18004c71b`
- name: `?_IsValidStagingArea@CSdCommonImpl@@CAJPEBGPEA_K@Z`
- size: `599`
- prototype: `__int64 __fastcall(WCHAR *Src, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004d6d8`

## callees

- `0x18004c4c4`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180085d80`
- `0x18008f5d0`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!GetDiskFreeSpaceExW` at `0x18004c693`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x18004c693`
- `KERNEL32!GetVolumePathNameW` at `0x18004c5c6`
- `KERNEL32!GetVolumePathNameW` at `0x18004c5c6`
- `KERNEL32!GetDriveTypeW` at `0x18004c598`
- `KERNEL32!GetDriveTypeW` at `0x18004c598`
- `KERNEL32!GetVolumeInformationW` at `0x18004c642`
- `KERNEL32!GetVolumeInformationW` at `0x18004c642`

## string_xrefs

- `0x18004c504`: `CSdCommonImpl::_IsValidStagingArea`

## pseudocode

```c

```
