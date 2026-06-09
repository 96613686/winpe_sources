# ConstructDeviceInfo(_CERT_CONTEXT const *,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,ushort * *,uchar * *,ulong *)

- ea: `0x1800b13bc`
- end: `0x1800b1597`
- name: `?ConstructDeviceInfo@@YAJPEBU_CERT_CONTEXT@@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@PEAPEAGPEAPEAEPEAK@Z`
- size: `475`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800931e4`
- `0x180099d08`
- `0x18009a930`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x180013510`
- `0x1800151c4`
- `0x180015860`
- `0x18002b33c`
- `0x180030120`
- `0x180037e48`
- `0x1800a3b60`
- `0x1800b13bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b1484`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b1546`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b1554`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b1484`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b1546`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b1554`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b149a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b14ee`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b149a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b14ee`

## string_xrefs

- `0x1800b1426`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800b1537`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800b14dc`: `hr = StringCchCopyW(wszKeypair, wstrKeypair.GetLength() + 1, wstrKeypair.GetBuffer())`
- `0x1800b151b`: `hr = SafeCopyMemory(pbDeviceCert, pCertCtxt->cbCertEncoded, pCertCtxt->pbCertEncoded, pCertCtxt->cbCertEncoded)`

## pseudocode

```c

```
