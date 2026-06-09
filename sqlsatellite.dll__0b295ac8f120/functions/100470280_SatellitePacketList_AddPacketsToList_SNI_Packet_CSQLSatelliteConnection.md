# SatellitePacketList::AddPacketsToList(SNI_Packet *,CSQLSatelliteConnection *)

- ea: `0x100470280`
- end: `0x1004704b2`
- name: `?AddPacketsToList@SatellitePacketList@@QEAAXPEAVSNI_Packet@@PEAVCSQLSatelliteConnection@@@Z`
- size: `562`
- prototype: `void __fastcall(SatellitePacketList *__hidden this, struct SNI_Packet *, struct CSQLSatelliteConnection *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x100472000`

## callees

- `0x10040bbb0`
- `0x100415950`
- `0x100415a50`
- `0x100415c70`
- `0x100470280`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100470344`
- `KERNEL32!QueryPerformanceCounter` at `0x10047039a`
- `KERNEL32!QueryPerformanceCounter` at `0x100470344`
- `KERNEL32!QueryPerformanceCounter` at `0x10047039a`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10047042a`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100470331`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100470389`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10047035c`
- `sqldk!SystemThread_TlsIndex` at `0x100470303`
- `sqldk!SystemThread_TlsOffset` at `0x10047030c`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004702e3`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100470436`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100470436`

## pseudocode

```c

```
