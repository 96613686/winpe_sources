# CTSCryptUtils::BinaryToString(uchar *,ulong,ushort * *,ulong *)

- ea: `0x180042178`
- end: `0x180042419`
- name: `?BinaryToString@CTSCryptUtils@@SAJPEAEKPEAPEAGPEAK@Z`
- size: `673`
- prototype: `__int64 __fastcall(BYTE *pbBinary, DWORD cbBinary, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003a510`

## callees

- `0x180002130`
- `0x18001a880`
- `0x18001a8d0`
- `0x180042178`
- `0x180043070`
- `0x1800430f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042266`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004234b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042266`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004234b`
- `CRYPT32!CryptBinaryToStringW` at `0x180042258`
- `CRYPT32!CryptBinaryToStringW` at `0x18004233d`
- `CRYPT32!CryptBinaryToStringW` at `0x180042258`
- `CRYPT32!CryptBinaryToStringW` at `0x18004233d`

## string_xrefs

- `0x18004229f`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`
- `0x180042380`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`

## pseudocode

```c

```
