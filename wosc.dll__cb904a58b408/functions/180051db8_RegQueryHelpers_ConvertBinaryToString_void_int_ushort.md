# RegQueryHelpers::ConvertBinaryToString(void *,int,ushort * *)

- ea: `0x180051db8`
- end: `0x180051ef4`
- name: `?ConvertBinaryToString@RegQueryHelpers@@CAJPEAXHPEAPEAG@Z`
- size: `316`
- prototype: `__int64 __fastcall(BYTE *pbBinary, DWORD cbBinary, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180052094`

## callees

- `0x180009e38`
- `0x18000e5ac`
- `0x180019a94`
- `0x180026660`
- `0x180051db8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051df8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051e8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051df8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051e8e`
- `CRYPT32!CryptBinaryToStringW` at `0x180051dee`
- `CRYPT32!CryptBinaryToStringW` at `0x180051e84`
- `CRYPT32!CryptBinaryToStringW` at `0x180051dee`
- `CRYPT32!CryptBinaryToStringW` at `0x180051e84`

## string_xrefs

- `0x180051e1c`: `onecore\base\flighting\common\regvalet\regqueryhelpers.cpp`
- `0x180051ec5`: `onecore\base\flighting\common\regvalet\regqueryhelpers.cpp`

## pseudocode

```c

```
