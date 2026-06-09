# IsSmartCardCert_Helper(_CERT_CONTEXT const *,int &)

- ea: `0x18009d99c`
- end: `0x18009db7c`
- name: `?IsSmartCardCert_Helper@@YAJPEBU_CERT_CONTEXT@@AEAH@Z`
- size: `480`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCert, int *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180111aa0`
- `0x180111ea0`

## callees

- `0x18000ed04`
- `0x1800151c4`
- `0x18001921c`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180037358`
- `0x180039c38`
- `0x18009d99c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009da30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dabb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009db19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009da30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dabb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009db19`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18009da26`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18009da26`
- `CRYPTSP!CryptGetUserKey` at `0x18009daa9`
- `CRYPTSP!CryptGetUserKey` at `0x18009daa9`
- `CRYPTSP!CryptGetKeyParam` at `0x18009db0f`
- `CRYPTSP!CryptGetKeyParam` at `0x18009db0f`

## string_xrefs

- `0x18009d9ea`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x18009da56`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x18009dada`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`

## pseudocode

```c

```
