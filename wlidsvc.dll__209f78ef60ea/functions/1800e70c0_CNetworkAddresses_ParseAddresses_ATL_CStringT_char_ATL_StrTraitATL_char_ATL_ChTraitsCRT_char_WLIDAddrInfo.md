# CNetworkAddresses::ParseAddresses(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,_WLIDAddrInfo * *)

- ea: `0x1800e70c0`
- end: `0x1800e74ab`
- name: `?ParseAddresses@CNetworkAddresses@@SAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@PEAPEAU_WLIDAddrInfo@@@Z`
- size: `1003`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008a794`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x1800151c4`
- `0x1800167b8`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180037e48`
- `0x180046ba8`
- `0x1800a4778`
- `0x1800e70c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e7433`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e7443`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e744c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e7433`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e7443`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e744c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800e7222`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800e726e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800e72d6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800e7222`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800e726e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800e72d6`

## string_xrefs

- `0x1800e7129`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\networkaddresses.cpp`
- `0x1800e7393`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\networkaddresses.cpp`
- `0x1800e73b6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\networkaddresses.cpp`
- `0x1800e71cd`: `hr = SafeCopyMemory(&dwCount, sizeof(dwCount), pRawData, sizeof(DWORD))`
- `0x1800e739c`: `pTemp <= pBufferEnd`
- `0x1800e73bf`: `SUCCEEDED(hr = ULongPtrAdd((ULONG_PTR)pSource, pStoredAddresses[i].AddressLen, (ULONG_PTR*)&pTemp))`
- `0x1800e7377`: `hr = SafeCopyMemory(pAddrInfo->pAddrData[i].pAddress, pAddrInfo->pAddrData[i].cbAddressLen, pSource, pStoredAddresses[i].AddressLen)`

## pseudocode

```c

```
