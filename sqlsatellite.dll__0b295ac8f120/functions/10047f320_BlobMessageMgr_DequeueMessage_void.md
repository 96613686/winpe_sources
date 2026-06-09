# BlobMessageMgr::DequeueMessage(void)

- ea: `0x10047f320`
- end: `0x10047f4f1`
- name: `?DequeueMessage@BlobMessageMgr@@AEAAPEAVCSQLSatelliteBlobMessage@@XZ`
- size: `465`
- prototype: `struct CSQLSatelliteBlobMessage *__fastcall(BlobMessageMgr *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x10047ede0`

## callees

- `0x10047f320`
- `0x10047f570`
- `0x10047f670`
- `0x10047f890`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10047f3d2`
- `KERNEL32!QueryPerformanceCounter` at `0x10047f425`
- `KERNEL32!QueryPerformanceCounter` at `0x10047f3d2`
- `KERNEL32!QueryPerformanceCounter` at `0x10047f425`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10047f49a`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10047f3c2`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10047f414`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10047f3e7`
- `sqldk!SystemThread_TlsIndex` at `0x10047f394`
- `sqldk!SystemThread_TlsOffset` at `0x10047f39d`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10047f374`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10047f4a6`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10047f4a6`

## pseudocode

```c

```
