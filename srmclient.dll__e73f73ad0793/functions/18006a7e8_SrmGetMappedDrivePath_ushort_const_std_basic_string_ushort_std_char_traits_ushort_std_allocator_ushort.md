# SrmGetMappedDrivePath(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18006a7e8`
- end: `0x18006aafc`
- name: `?SrmGetMappedDrivePath@@YA_NPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `788`
- prototype: `__int64 __fastcall(wchar_t *String2, void *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180065c60`

## callees

- `0x180001350`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000ee24`
- `0x180010bc4`
- `0x18001d7d4`
- `0x180069578`
- `0x18006a7e8`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07a2`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!iswalpha` at `0x18006a8e3`
- `msvcrt!iswalpha` at `0x18006a8e3`
- `KERNEL32!GetDriveTypeW` at `0x18006a902`
- `KERNEL32!GetDriveTypeW` at `0x18006a902`
- `MPR!WNetGetUniversalNameW` at `0x18006a956`
- `MPR!WNetGetUniversalNameW` at `0x18006a9a5`
- `MPR!WNetGetUniversalNameW` at `0x18006a956`
- `MPR!WNetGetUniversalNameW` at `0x18006a9a5`

## string_xrefs

- `0x18006a83e`: `SRMPATHH`
- `0x18006a832`: `SrmGetMappedDrivePath`
- `0x18006a826`: `base\fs\fsrm\utilities\inc\srmpath.h`

## pseudocode

```c

```
