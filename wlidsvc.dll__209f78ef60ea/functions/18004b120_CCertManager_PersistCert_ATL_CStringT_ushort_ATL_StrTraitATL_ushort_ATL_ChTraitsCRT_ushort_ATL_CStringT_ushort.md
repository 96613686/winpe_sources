# CCertManager::PersistCert(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)

- ea: `0x18004b120`
- end: `0x18004b3e5`
- name: `?PersistCert@CCertManager@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004aff8`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x18000ed3c`
- `0x180014330`
- `0x180014824`
- `0x1800151c4`
- `0x180019424`
- `0x180019780`
- `0x18001a530`
- `0x18001a9c0`
- `0x180021b28`
- `0x180021bbc`
- `0x1800396e8`
- `0x1800419a4`
- `0x18004b120`
- `0x18008b4ac`
- `0x180098518`
- `0x1800a3b60`
- `0x1800a4718`
- `0x1800e079c`
- `0x1800e35ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004b399`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004b399`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18004b1f1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18004b1fb`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18004b1f1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18004b1fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b3a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b3a3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004b212`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004b212`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b1e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b1e7`

## string_xrefs

- `0x18004b1c4`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x18004b36b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x18004b330`: `hr = CCertManager::GetServiceName(wstrIndex, wstrServiceName)`
- `0x18004b31e`: `hr = CCertificateInfo::WriteToCache(wstrUserName, CW2A(wstrServiceName), pCertObj)`

## pseudocode

```c

```
