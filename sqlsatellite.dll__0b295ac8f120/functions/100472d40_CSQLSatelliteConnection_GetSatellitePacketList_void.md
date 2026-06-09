# CSQLSatelliteConnection::GetSatellitePacketList(void)

- ea: `0x100472d40`
- end: `0x100472ef2`
- name: `?GetSatellitePacketList@CSQLSatelliteConnection@@QEAAPEAVSatellitePacketList@@XZ`
- size: `434`
- prototype: `struct SatellitePacketList *__fastcall(CSQLSatelliteConnection *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x100408800`
- `0x100472000`

## callees

- `0x100415950`
- `0x100415a50`
- `0x100415c70`
- `0x100472d40`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100472df6`
- `KERNEL32!QueryPerformanceCounter` at `0x100472e49`
- `KERNEL32!QueryPerformanceCounter` at `0x100472df6`
- `KERNEL32!QueryPerformanceCounter` at `0x100472e49`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100472e9b`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100472de6`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100472e38`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100472e0b`
- `sqldk!SystemThread_TlsIndex` at `0x100472db8`
- `sqldk!SystemThread_TlsOffset` at `0x100472dc1`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100472d98`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100472ea7`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100472ea7`

## pseudocode

```c

```
