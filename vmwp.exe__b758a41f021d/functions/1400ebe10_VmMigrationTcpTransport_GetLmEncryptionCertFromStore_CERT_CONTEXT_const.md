# VmMigrationTcpTransport::GetLmEncryptionCertFromStore(_CERT_CONTEXT const * *)

- ea: `0x1400ebe10`
- end: `0x1400ebfa4`
- name: `?GetLmEncryptionCertFromStore@VmMigrationTcpTransport@@UEAAJPEAPEBU_CERT_CONTEXT@@@Z`
- size: `404`
- prototype: `__int64 __fastcall(VmMigrationTcpTransport *__hidden this, const struct _CERT_CONTEXT **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400364a0`
- `0x1400544a8`
- `0x140078628`
- `0x1400ebe10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ebf0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ebf5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ebf0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ebf5b`
- `CRYPT32!CertFindCertificateInStore` at `0x1400ebeb6`
- `CRYPT32!CertFindCertificateInStore` at `0x1400ebeb6`
- `CRYPT32!CertCloseStore` at `0x1400ebf2e`
- `CRYPT32!CertCloseStore` at `0x1400ebf2e`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1400ebefa`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1400ebefa`
- `CRYPT32!CertOpenStore` at `0x1400ebe72`
- `CRYPT32!CertOpenStore` at `0x1400ebe72`

## string_xrefs

- `0x1400ebf43`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

## pseudocode

```c

```
