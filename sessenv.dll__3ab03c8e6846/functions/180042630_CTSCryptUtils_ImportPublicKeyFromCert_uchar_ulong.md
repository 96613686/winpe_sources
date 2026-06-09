# CTSCryptUtils::ImportPublicKeyFromCert(uchar *,ulong)

- ea: `0x180042630`
- end: `0x1800427f7`
- name: `?ImportPublicKeyFromCert@CTSCryptUtils@@QEAAJPEAEK@Z`
- size: `455`
- prototype: `__int64 __fastcall(BCRYPT_KEY_HANDLE *phKey, BYTE *pbElement, DWORD cbElement)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003a510`

## callees

- `0x180002130`
- `0x180042420`
- `0x180042630`
- `0x180042a60`
- `0x18004301c`
- `0x180043070`
- `0x1800430f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042738`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x18004272a`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x18004272a`
- `CRYPT32!CertFreeCertificateContext` at `0x1800427df`
- `CRYPT32!CertFreeCertificateContext` at `0x1800427df`

## string_xrefs

- `0x18004276d`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`

## pseudocode

```c

```
