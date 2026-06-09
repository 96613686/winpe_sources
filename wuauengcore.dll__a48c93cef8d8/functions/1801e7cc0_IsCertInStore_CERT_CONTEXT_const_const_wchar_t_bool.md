# IsCertInStore(_CERT_CONTEXT const * const,wchar_t *,bool *)

- ea: `0x1801e7cc0`
- end: `0x1801e7e9b`
- name: `?IsCertInStore@@YAJQEBU_CERT_CONTEXT@@PEA_WPEA_N@Z`
- size: `475`
- prototype: `int(const struct _CERT_CONTEXT *const, wchar_t *, bool *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1801e8ef8`
- `0x1801e9228`
- `0x1801e99e0`

## callees

- `0x18012b618`
- `0x1801e7cc0`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e7d1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e7d98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e7e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e7d1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e7d98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e7e17`
- `CRYPT32!CertControlStore` at `0x1801e7ddb`
- `CRYPT32!CertControlStore` at `0x1801e7ddb`
- `CRYPT32!CertOpenStore` at `0x1801e7d8a`
- `CRYPT32!CertOpenStore` at `0x1801e7d8a`
- `CRYPT32!CertFreeCertificateContext` at `0x1801e7e7b`
- `CRYPT32!CertFreeCertificateContext` at `0x1801e7e7b`
- `CRYPT32!CertCloseStore` at `0x1801e7e6d`
- `CRYPT32!CertCloseStore` at `0x1801e7e6d`
- `CRYPT32!CertFindCertificateInStore` at `0x1801e7e02`
- `CRYPT32!CertFindCertificateInStore` at `0x1801e7e02`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1801e7d15`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1801e7d15`

## pseudocode

```c

```
