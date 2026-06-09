# GetRootCAThumbPrint(_CERT_CONTEXT const *,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)

- ea: `0x18000e030`
- end: `0x18000e2a2`
- name: `?GetRootCAThumbPrint@@YAJPEBU_CERT_CONTEXT@@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z`
- size: `626`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18000edec`

## callees

- `0x180002da0`
- `0x18000a914`
- `0x18000ba8c`
- `0x18000cc9c`
- `0x18000cdac`
- `0x18000d3b4`
- `0x18000e030`
- `0x18000e870`
- `0x18000ed94`
- `0x180052e48`
- `0x1800530e4`
- `0x180054518`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e1c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e1c8`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000e1be`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000e1be`
- `CRYPT32!CertGetCertificateChain` at `0x18000e12c`
- `CRYPT32!CertGetCertificateChain` at `0x18000e12c`

## string_xrefs

- `0x18000e0bd`: `clientcore\ds\ext\live\identity\api\classic\certtokenwlidcli.cpp`

## pseudocode

```c

```
