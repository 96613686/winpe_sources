# CSQLSatelliteConnection::AddMessageToQueue(uchar *,SNI_Packet *,bool *)

- ea: `0x100471430`
- end: `0x10047160c`
- name: `?AddMessageToQueue@CSQLSatelliteConnection@@EEAAJPEAEPEAVSNI_Packet@@PEA_N@Z`
- size: `476`
- prototype: `__int64 __fastcall(CSQLSatelliteConnection *__hidden this, unsigned __int8 *, struct SNI_Packet *, bool *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x10040d680`
- `0x100415950`
- `0x100415a50`
- `0x100415c70`
- `0x100471430`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1004714ef`
- `KERNEL32!QueryPerformanceCounter` at `0x100471548`
- `KERNEL32!QueryPerformanceCounter` at `0x1004714ef`
- `KERNEL32!QueryPerformanceCounter` at `0x100471548`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1004715a5`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004714dc`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100471534`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100471507`
- `sqldk!SystemThread_TlsIndex` at `0x1004714ae`
- `sqldk!SystemThread_TlsOffset` at `0x1004714b7`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10047148e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004715b1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004715b1`

## pseudocode

```c

```
