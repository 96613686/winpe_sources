# CStoredIdentity::WriteToCertStore(_CERT_CONTEXT const *)

- ea: `0x1800c4730`
- end: `0x1800c4884`
- name: `?WriteToCertStore@CStoredIdentity@@AEAAJPEBU_CERT_CONTEXT@@@Z`
- size: `340`
- prototype: `int(CStoredIdentity *__hidden this, const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005b74c`

## callees

- `0x18000c050`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180034908`
- `0x18004ff98`
- `0x1800c4730`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c47d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c481e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c47d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c481e`
- `CRYPT32!CertOpenStore` at `0x1800c47be`
- `CRYPT32!CertOpenStore` at `0x1800c47be`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1800c4814`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1800c4814`

## string_xrefs

- `0x1800c4780`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\systemstore.cpp`
- `0x1800c484c`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\systemstore.cpp`
- `0x1800c4747`: `CStoredIdentity::WriteToCertStore`

## pseudocode

```c

```
