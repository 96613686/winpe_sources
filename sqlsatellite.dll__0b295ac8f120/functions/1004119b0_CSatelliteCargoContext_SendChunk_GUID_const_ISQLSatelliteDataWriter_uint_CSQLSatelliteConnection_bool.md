# CSatelliteCargoContext::SendChunk(_GUID const *,ISQLSatelliteDataWriter *,uint,CSQLSatelliteConnection *,bool)

- ea: `0x1004119b0`
- end: `0x10041211f`
- name: `?SendChunk@CSatelliteCargoContext@@QEAAJPEBU_GUID@@PEAVISQLSatelliteDataWriter@@IPEAVCSQLSatelliteConnection@@_N@Z`
- size: `1903`
- prototype: `__int64 __fastcall(CSatelliteCargoContext *__hidden this, const struct _GUID *, struct ISQLSatelliteDataWriter *, unsigned int, struct CSQLSatelliteConnection *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x100406650`

## callees

- `0x100411680`
- `0x1004119b0`
- `0x10041b270`
- `0x10041b420`
- `0x10041b780`
- `0x10041f180`
- `0x100478d40`
- `0x100479130`
- `0x100479360`
- `0x100487cd6`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100411a10`
- `KERNEL32!QueryPerformanceCounter` at `0x100412077`
- `KERNEL32!QueryPerformanceCounter` at `0x100411a10`
- `KERNEL32!QueryPerformanceCounter` at `0x100412077`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x1004120b6`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100411a00`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100412067`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004120a1`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100411c8a`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100411da0`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100411e5f`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100411f93`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100411c8a`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100411da0`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100411e5f`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100411f93`
- `sqldk!??_V@YAXPEAX@Z` at `0x100411d15`
- `sqldk!??_V@YAXPEAX@Z` at `0x100411d15`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100411b4b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100411b4b`

## pseudocode

```c

```
