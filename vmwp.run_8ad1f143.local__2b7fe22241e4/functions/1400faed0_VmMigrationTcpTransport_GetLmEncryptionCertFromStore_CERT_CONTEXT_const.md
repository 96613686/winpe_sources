# VmMigrationTcpTransport::GetLmEncryptionCertFromStore(_CERT_CONTEXT const * *)

- ea: `0x1400faed0`
- end: `0x1400fb064`
- name: `?GetLmEncryptionCertFromStore@VmMigrationTcpTransport@@UEAAJPEAPEBU_CERT_CONTEXT@@@Z`
- size: `404`
- prototype: `__int64 __fastcall(VmMigrationTcpTransport *__hidden this, const struct _CERT_CONTEXT **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140042260`
- `0x14005497c`
- `0x14006af58`
- `0x1400faed0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400fafce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400fb01b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400fafce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400fb01b`
- `CRYPT32!CertFindCertificateInStore` at `0x1400faf76`
- `CRYPT32!CertFindCertificateInStore` at `0x1400faf76`
- `CRYPT32!CertCloseStore` at `0x1400fafee`
- `CRYPT32!CertCloseStore` at `0x1400fafee`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1400fafba`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1400fafba`
- `CRYPT32!CertOpenStore` at `0x1400faf32`
- `CRYPT32!CertOpenStore` at `0x1400faf32`

## string_xrefs

- `0x1400fb003`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

## pseudocode

```c

```
