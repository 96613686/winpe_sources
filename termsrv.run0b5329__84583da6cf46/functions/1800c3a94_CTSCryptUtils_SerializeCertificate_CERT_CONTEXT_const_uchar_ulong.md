# CTSCryptUtils::SerializeCertificate(_CERT_CONTEXT const *,uchar * *,ulong *)

- ea: `0x1800c3a94`
- end: `0x1800c3d2c`
- name: `?SerializeCertificate@CTSCryptUtils@@SAJPEBU_CERT_CONTEXT@@PEAPEAEPEAK@Z`
- size: `664`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180089040`

## callees

- `0x180006f24`
- `0x1800321d4`
- `0x180032724`
- `0x1800c3a94`
- `0x1800c3d88`
- `0x1800c40bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3ba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3c68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3ba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3c68`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x1800c3b98`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x1800c3c5a`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x1800c3b98`
- `CRYPT32!CertSerializeCertificateStoreElement` at `0x1800c3c5a`

## string_xrefs

- `0x1800c3bdf`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`
- `0x1800c3c9d`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`

## pseudocode

```c

```
