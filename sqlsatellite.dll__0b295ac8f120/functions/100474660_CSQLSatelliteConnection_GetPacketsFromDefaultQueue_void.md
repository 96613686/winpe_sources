# CSQLSatelliteConnection::GetPacketsFromDefaultQueue(void)

- ea: `0x100474660`
- end: `0x10047483d`
- name: `?GetPacketsFromDefaultQueue@CSQLSatelliteConnection@@QEAAPEAVSNI_Packet@@XZ`
- size: `477`
- prototype: `struct SNI_Packet *__fastcall(CSQLSatelliteConnection *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x100474850`

## callees

- `0x100415950`
- `0x100415a50`
- `0x100415c70`
- `0x100474660`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100474712`
- `KERNEL32!QueryPerformanceCounter` at `0x100474765`
- `KERNEL32!QueryPerformanceCounter` at `0x100474712`
- `KERNEL32!QueryPerformanceCounter` at `0x100474765`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1004747dd`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100474702`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100474754`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100474727`
- `sqldk!SystemThread_TlsIndex` at `0x1004746d4`
- `sqldk!SystemThread_TlsOffset` at `0x1004746dd`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004746b4`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004747e9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004747e9`

## pseudocode

```c

```
