# CTSCryptUtils::UnprotectCredential(ushort *,ushort * *,ulong *)

- ea: `0x180042c7c`
- end: `0x180042feb`
- name: `?UnprotectCredential@CTSCryptUtils@@SAJPEAGPEAPEAGPEAK@Z`
- size: `879`
- prototype: `__int64 __fastcall(LPWSTR pszProtectedCredentials, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003a510`

## callees

- `0x180002130`
- `0x18001a880`
- `0x18001a8d0`
- `0x180021db8`
- `0x180042c7c`
- `0x18004301c`
- `0x180043070`
- `0x1800430f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042e32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042eab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042e32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042eab`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x180042e24`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x180042e9d`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x180042e24`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x180042e9d`

## string_xrefs

- `0x180042ee8`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`
- `0x180042f5c`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`

## pseudocode

```c

```
