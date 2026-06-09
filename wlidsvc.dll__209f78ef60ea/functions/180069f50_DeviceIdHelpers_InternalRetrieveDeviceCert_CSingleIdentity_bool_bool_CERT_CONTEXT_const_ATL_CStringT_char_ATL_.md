# DeviceIdHelpers::InternalRetrieveDeviceCert(CSingleIdentity *,bool,bool,_CERT_CONTEXT const * *,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> *)

- ea: `0x180069f50`
- end: `0x18006a2c2`
- name: `?InternalRetrieveDeviceCert@DeviceIdHelpers@@SAJPEAVCSingleIdentity@@_N1PEAPEBU_CERT_CONTEXT@@PEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z`
- size: `882`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x180071920`
- `0x1800a1550`

## callees

- `0x18000c050`
- `0x18000e008`
- `0x18000ed04`
- `0x1800151c4`
- `0x180015fdc`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180033218`
- `0x180069f50`
- `0x1800c5604`
- `0x1800e32e0`
- `0x180106e00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a1ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a22c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a1ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a22c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006a064`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006a0a0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006a064`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006a0a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006a031`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006a074`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006a031`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006a074`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x18006a191`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x18006a1bb`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x18006a191`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x18006a1bb`

## string_xrefs

- `0x180069fd4`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidhelpers.cpp`
- `0x18006a0a9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidhelpers.cpp`

## pseudocode

```c

```
