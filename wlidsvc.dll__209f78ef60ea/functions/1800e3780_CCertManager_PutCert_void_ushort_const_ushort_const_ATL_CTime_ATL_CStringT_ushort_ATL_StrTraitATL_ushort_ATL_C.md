# CCertManager::PutCert(void *,ushort const *,ushort const *,ATL::CTime,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x1800e3780`
- end: `0x1800e3aa3`
- name: `?PutCert@CCertManager@@QEAAJPEAXPEBG1VCTime@ATL@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z`
- size: `803`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x180061390`
- `0x1800e1a34`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x1800151c4`
- `0x1800167b8`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180026c18`
- `0x180046c18`
- `0x180089f80`
- `0x1800af71c`
- `0x1800e17cc`
- `0x1800e314c`
- `0x1800e3780`
- `0x1800e3aac`
- `0x1800e3b5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e38cd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e3a35`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e38cd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e3a35`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e3865`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e386f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e3950`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e395a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e3865`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e386f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e3950`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e395a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e38d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3a3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e38d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3a3e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e3886`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e3971`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e3886`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e3971`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e385b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e3946`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e385b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e3946`

## string_xrefs

- `0x1800e37d3`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e390e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e39e6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e3a21`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e383a`: `hr = GenerateMapIndex(pIdentity, cwstrServiceName, wstrMapIndex)`
- `0x1800e3a50`: `pIdentity != nullptr && cwstrBase64Cert != nullptr && cwstrServiceName != nullptr && *cwstrBase64Cert != L'\0' && *cwstrServiceName != L'\0'`

## pseudocode

```c

```
