# SatellitePacketList::GetPacketsList(CSQLSatelliteConnection * *)

- ea: `0x1004700c0`
- end: `0x100470275`
- name: `?GetPacketsList@SatellitePacketList@@QEAAPEAVSNI_Packet@@PEAPEAVCSQLSatelliteConnection@@@Z`
- size: `437`
- prototype: `struct SNI_Packet *__fastcall(SatellitePacketList *__hidden this, struct CSQLSatelliteConnection **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x100470c20`

## callees

- `0x100415950`
- `0x100415a50`
- `0x100415c70`
- `0x1004700c0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100470179`
- `KERNEL32!QueryPerformanceCounter` at `0x1004701d2`
- `KERNEL32!QueryPerformanceCounter` at `0x100470179`
- `KERNEL32!QueryPerformanceCounter` at `0x1004701d2`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100470223`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100470166`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004701be`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100470191`
- `sqldk!SystemThread_TlsIndex` at `0x100470138`
- `sqldk!SystemThread_TlsOffset` at `0x100470141`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100470118`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10047022f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10047022f`

## pseudocode

```c

```
