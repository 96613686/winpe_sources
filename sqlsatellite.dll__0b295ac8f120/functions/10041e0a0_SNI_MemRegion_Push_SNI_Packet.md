# SNI_MemRegion::Push(SNI_Packet *)

- ea: `0x10041e0a0`
- end: `0x10041e37e`
- name: `?Push@SNI_MemRegion@@QEAAXPEAVSNI_Packet@@@Z`
- size: `734`
- prototype: `void(SNI_MemRegion *__hidden this, struct SNI_Packet *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x10041f180`

## callees

- `0x10040ce80`
- `0x10040d0c0`
- `0x10040d370`
- `0x10040d490`
- `0x10041e0a0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10041e152`
- `KERNEL32!QueryPerformanceCounter` at `0x10041e1ac`
- `KERNEL32!QueryPerformanceCounter` at `0x10041e152`
- `KERNEL32!QueryPerformanceCounter` at `0x10041e1ac`
- `KERNEL32!VirtualProtect` at `0x10041e23e`
- `KERNEL32!VirtualProtect` at `0x10041e23e`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10041e2ed`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10041e331`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041e13f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041e198`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10041e16a`
- `sqldk!SystemThread_TlsIndex` at `0x10041e111`
- `sqldk!SystemThread_TlsOffset` at `0x10041e11a`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10041e0ec`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041e2f9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041e33d`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041e2f9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041e33d`

## pseudocode

```c

```
