# IsCertInStore(_CERT_CONTEXT const * const,wchar_t *,bool *)

- ea: `0x18008a500`
- end: `0x18008a6ef`
- name: `?IsCertInStore@@YAJQEBU_CERT_CONTEXT@@PEA_WPEA_N@Z`
- size: `495`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *const, wchar_t *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18008b3d4`

## callees

- `0x18008a500`
- `0x180090bc8`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a5e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a5e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a661`
- `CRYPT32!CertFreeCertificateContext` at `0x18008a6c5`
- `CRYPT32!CertFreeCertificateContext` at `0x18008a6c5`
- `CRYPT32!CertCloseStore` at `0x18008a6b7`
- `CRYPT32!CertCloseStore` at `0x18008a6b7`
- `CRYPT32!CertControlStore` at `0x18008a625`
- `CRYPT32!CertControlStore` at `0x18008a625`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18008a558`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18008a558`
- `CRYPT32!CertFindCertificateInStore` at `0x18008a64c`
- `CRYPT32!CertFindCertificateInStore` at `0x18008a64c`
- `CRYPT32!CertOpenStore` at `0x18008a5d4`
- `CRYPT32!CertOpenStore` at `0x18008a5d4`

## pseudocode

```c

```
