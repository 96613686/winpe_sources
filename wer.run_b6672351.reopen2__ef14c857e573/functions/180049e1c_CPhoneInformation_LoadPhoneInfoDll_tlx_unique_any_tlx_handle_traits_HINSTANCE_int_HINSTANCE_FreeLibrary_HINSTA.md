# CPhoneInformation::LoadPhoneInfoDll(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *,int (**)(_PHONE_INFORMATION_KEY,wchar_t *,unsigned __int64,unsigned __int64 *))

- ea: `0x180049e1c`
- end: `0x180049edd`
- name: `?LoadPhoneInfoDll@CPhoneInformation@@CAJPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEAP6AHW4_PHONE_INFORMATION_KEY@@PEA_W_KPEA_K@Z@Z`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180093a2c`

## callees

- `0x18001e7e8`
- `0x180039210`
- `0x180049e1c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180049e8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180049e8b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180049e3d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180049ec5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180049e3d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180049ec5`

## string_xrefs

- `0x180049e61`: `phoneinfo.dll`

## pseudocode

```c

```
