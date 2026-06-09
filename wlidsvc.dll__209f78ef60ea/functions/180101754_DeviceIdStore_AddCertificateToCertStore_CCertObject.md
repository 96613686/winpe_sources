# DeviceIdStore::AddCertificateToCertStore(CCertObject *)

- ea: `0x180101754`
- end: `0x180101999`
- name: `?AddCertificateToCertStore@DeviceIdStore@@SAJPEAVCCertObject@@@Z`
- size: `581`
- prototype: `__int64 __fastcall(struct CCertObject *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800e006c`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x18000ed3c`
- `0x1800151c4`
- `0x180015860`
- `0x18002b370`
- `0x180039d60`
- `0x18003c814`
- `0x18004ff98`
- `0x1800a3b60`
- `0x1800f3a48`
- `0x180101754`
- `0x180107b00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801018f0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801018f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101860`
- `CRYPT32!CertOpenStore` at `0x1801017ee`
- `CRYPT32!CertOpenStore` at `0x1801017ee`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180101856`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180101856`

## string_xrefs

- `0x180101954`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`

## pseudocode

```c

```
