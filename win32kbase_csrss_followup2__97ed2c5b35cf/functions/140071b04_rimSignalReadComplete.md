# rimSignalReadComplete

- ea: `0x140071b04`
- end: `0x140071ff3`
- name: `rimSignalReadComplete`
- size: `1263`
- prototype: `__int64 __fastcall(struct RawInputManagerObject *, struct RIMDEV *, struct _IO_STATUS_BLOCK *)`
- caller_count: `3`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400e6060`
- `0x140120078`
- `0x140134f20`

## callees

- `0x140071b04`
- `0x140071ffc`
- `0x1400720e8`
- `0x140072140`
- `0x1400723f8`
- `0x14009552c`
- `0x1400b1d40`
- `0x1400e7904`
- `0x1402081cc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140071d01`
- `ntoskrnl!ZwClose` at `0x140071d01`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140071b6e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140071b6e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071b5d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071b5d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140071be3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140071be3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140071bd7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140071bd7`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140071d60`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140071d60`
- `ntoskrnl!ZwSetEvent` at `0x140071cee`
- `ntoskrnl!ZwSetEvent` at `0x140071cee`
- `ntoskrnl!KeSetTimer` at `0x140071fd0`
- `ntoskrnl!KeSetTimer` at `0x140071fd0`
- `WIN32K!W32GetUserSessionState` at `0x140071b4d`
- `WIN32K!W32GetUserSessionState` at `0x140071ba8`
- `WIN32K!W32GetUserSessionState` at `0x140071bc1`
- `WIN32K!W32GetUserSessionState` at `0x140071c49`
- `WIN32K!W32GetUserSessionState` at `0x140071dad`
- `WIN32K!W32GetUserSessionState` at `0x140071e54`
- `WIN32K!W32GetUserSessionState` at `0x140071f24`
- `WIN32K!W32GetUserSessionState` at `0x140071f87`
- `WIN32K!W32GetUserSessionState` at `0x140071fa0`
- `WIN32K!W32GetUserSessionState` at `0x140071fb3`
- `WIN32K!W32GetUserSessionState` at `0x140071b4d`
- `WIN32K!W32GetUserSessionState` at `0x140071ba8`
- `WIN32K!W32GetUserSessionState` at `0x140071bc1`
- `WIN32K!W32GetUserSessionState` at `0x140071c49`
- `WIN32K!W32GetUserSessionState` at `0x140071dad`
- `WIN32K!W32GetUserSessionState` at `0x140071e54`
- `WIN32K!W32GetUserSessionState` at `0x140071f24`
- `WIN32K!W32GetUserSessionState` at `0x140071f87`
- `WIN32K!W32GetUserSessionState` at `0x140071fa0`
- `WIN32K!W32GetUserSessionState` at `0x140071fb3`
- `HAL!KeQueryPerformanceCounter` at `0x140071b89`
- `HAL!KeQueryPerformanceCounter` at `0x140071ca7`
- `HAL!KeQueryPerformanceCounter` at `0x140071b89`
- `HAL!KeQueryPerformanceCounter` at `0x140071ca7`

## pseudocode

```c

```
