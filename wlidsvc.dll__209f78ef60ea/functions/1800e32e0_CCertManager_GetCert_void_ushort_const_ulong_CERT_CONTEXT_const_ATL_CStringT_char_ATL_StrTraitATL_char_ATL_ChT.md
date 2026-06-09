# CCertManager::GetCert(void *,ushort const *,ulong &,_CERT_CONTEXT const * *,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> *)

- ea: `0x1800e32e0`
- end: `0x1800e35a3`
- name: `?GetCert@CCertManager@@QEAAJPEAXPEBGAEAKPEAPEBU_CERT_CONTEXT@@PEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z`
- size: `707`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002795c`
- `0x180069f50`

## callees

- `0x18000c050`
- `0x18000e008`
- `0x18000ed04`
- `0x1800151c4`
- `0x1800167b8`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180089f80`
- `0x1800e2098`
- `0x1800e314c`
- `0x1800e32e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e34ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e34ae`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e33f8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e3552`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e33f8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e3552`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e33ce`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e3405`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e33ce`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e3405`
- `CRYPT32!CertFreeCertificateContext` at `0x1800e3567`
- `CRYPT32!CertFreeCertificateContext` at `0x1800e3567`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800e34a0`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800e34a0`

## string_xrefs

- `0x1800e333b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e33a2`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e3482`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e352f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e338a`: `hr = GenerateMapIndex(pIdentity, cwstrServiceName, wstrMapIndex)`

## pseudocode

```c

```
