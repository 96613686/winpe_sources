# CPhoneInformation::LoadPhoneInfoDll(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *,int (**)(_PHONE_INFORMATION_KEY,wchar_t *,unsigned __int64,unsigned __int64 *))

- ea: `0x180047c10`
- end: `0x180047cbe`
- name: `?LoadPhoneInfoDll@CPhoneInformation@@CAJPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEAP6AHW4_PHONE_INFORMATION_KEY@@PEA_W_KPEA_K@Z@Z`
- size: `174`
- prototype: `__int64 __fastcall(HMODULE *, FARPROC *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18008f958`

## callees

- `0x18001e38c`
- `0x1800371c0`
- `0x180047c10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180047c79`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180047c79`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180047c31`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180047cad`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180047c31`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180047cad`

## string_xrefs

- `0x180047c4f`: `phoneinfo.dll`

## pseudocode

```c

```
