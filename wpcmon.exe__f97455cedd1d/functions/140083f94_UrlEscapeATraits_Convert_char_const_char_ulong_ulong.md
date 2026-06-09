# UrlEscapeATraits::Convert(char const *,char *,ulong *,ulong)

- ea: `0x140083f94`
- end: `0x140084261`
- name: `?Convert@UrlEscapeATraits@@SA_NPEBDPEADPEAKK@Z`
- size: `717`
- prototype: `bool __fastcall(LPCCH lpMultiByteStr, char *, DWORD *pcchEscaped, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14004b674`

## callees

- `0x140005554`
- `0x140006314`
- `0x140007938`
- `0x14001f62c`
- `0x14002f2e0`
- `0x140083f94`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x140084146`
- `KERNEL32!WideCharToMultiByte` at `0x140084176`
- `KERNEL32!WideCharToMultiByte` at `0x140084146`
- `KERNEL32!WideCharToMultiByte` at `0x140084176`
- `KERNEL32!MultiByteToWideChar` at `0x140083ff0`
- `KERNEL32!MultiByteToWideChar` at `0x14008403e`
- `KERNEL32!MultiByteToWideChar` at `0x140083ff0`
- `KERNEL32!MultiByteToWideChar` at `0x14008403e`
- `SHLWAPI!UrlEscapeW` at `0x1400840f3`
- `SHLWAPI!UrlEscapeW` at `0x1400840f3`

## string_xrefs

- `0x14008421f`: `shellcommon\shell\wpccore\corelib\url.cpp`
- `0x140084237`: `shellcommon\shell\wpccore\corelib\url.cpp`
- `0x14008424f`: `shellcommon\shell\wpccore\corelib\url.cpp`

## pseudocode

```c

```
