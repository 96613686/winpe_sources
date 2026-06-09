# CTSCryptUtils::SerializeCertificate(_CERT_CONTEXT const *,uchar * *,ulong *)

- ea: `0x1800c9af8`
- end: `0x1800c9da9`
- name: `?SerializeCertificate@CTSCryptUtils@@SAJPEBU_CERT_CONTEXT@@PEAPEAEPEAK@Z`
- size: `689`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18008cb20`

## callees

- `0x180006f84`
- `0x180033f44`
- `0x180034494`
- `0x1800c9af8`
- `0x1800c9e0c`
- `0x1800ca158`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9c10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9cde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9c10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9cde`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x1800c9bfc`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x1800c9cca`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x1800c9bfc`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x1800c9cca`

## string_xrefs

- `0x1800c9c4f`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`
- `0x1800c9d19`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`

## pseudocode

```c

```
