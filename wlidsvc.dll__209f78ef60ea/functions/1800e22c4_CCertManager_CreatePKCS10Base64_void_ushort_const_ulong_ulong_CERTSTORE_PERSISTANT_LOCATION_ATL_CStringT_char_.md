# CCertManager::CreatePKCS10Base64(void *,ushort const *,ulong,ulong,_CERTSTORE_PERSISTANT_LOCATION,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)

- ea: `0x1800e22c4`
- end: `0x1800e251d`
- name: `?CreatePKCS10Base64@CCertManager@@QEAAJPEAXPEBGKKW4_CERTSTORE_PERSISTANT_LOCATION@@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z`
- size: `601`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c9f2c`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x1800151c4`
- `0x18001a530`
- `0x18001a9c0`
- `0x180046c18`
- `0x180089f80`
- `0x1800a716c`
- `0x1800af71c`
- `0x1800e1638`
- `0x1800e22c4`
- `0x1800e2524`
- `0x1800e314c`
- `0x1800e3aac`
- `0x1800e3b5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e24cf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e24cf`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e2448`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e2452`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e2448`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e2452`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e24d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e24d9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e2469`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e2469`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e243e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e243e`

## string_xrefs

- `0x1800e2321`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e2368`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e238f`: `hr = GenerateMapIndex(pIdentity, cwstrServiceName, wstrMapIndex)`
- `0x1800e230b`: `CCertManager::CreatePKCS10Base64`
- `0x1800e240f`: `hr = certObject->CreatePKCS10Base64(dwKeySize, dwKeyGenFlags, (eStoreLocation == LOCATION_WINDOWS_CREDENTIAL_MANAGER) ? false : true, strBase64PKCS10)`

## pseudocode

```c

```
