# ReadVersion(HINSTANCE__ *,ushort *,ushort *,ushort *,ushort *)

- ea: `0x38395c2c0`
- end: `0x38395c588`
- name: `?ReadVersion@@YAFPEAUHINSTANCE__@@PEAG111@Z`
- size: `712`
- prototype: `__int16 __fastcall(HINSTANCE, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x38386f930`
- `0x383923d40`
- `0x3839244b0`

## callees

- `0x3838434c0`
- `0x38386d3f4`
- `0x38391aed0`
- `0x38395c2c0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x38395c315`
- `KERNEL32!GetModuleFileNameW` at `0x38395c315`
- `VERSION!VerQueryValueW` at `0x38395c478`
- `VERSION!VerQueryValueW` at `0x38395c478`
- `VERSION!GetFileVersionInfoW` at `0x38395c426`
- `VERSION!GetFileVersionInfoW` at `0x38395c426`
- `VERSION!GetFileVersionInfoSizeW` at `0x38395c36f`
- `VERSION!GetFileVersionInfoSizeW` at `0x38395c36f`

## pseudocode

```c

```
