# CMouseProcessor::ProcessMouseInputData(CMouseProcessor::MouseInputDataEx *,MouseInputProcessingState *,_MousePacketPerf &,_MOUSE_INPUT_DATA const *,tagUIPI_INFO_INT const *)

- ea: `0x1400458a0`
- end: `0x140045e34`
- name: `?ProcessMouseInputData@CMouseProcessor@@AEAAXPEAVMouseInputDataEx@1@PEAUMouseInputProcessingState@@AEAU_MousePacketPerf@@PEBU_MOUSE_INPUT_DATA@@PEBUtagUIPI_INFO_INT@@@Z`
- size: `1428`
- prototype: `void __fastcall(CMouseProcessor *__hidden this, struct CMouseProcessor::MouseInputDataEx *, struct MouseInputProcessingState *, struct _MousePacketPerf *, const struct _MOUSE_INPUT_DATA *, const struct tagUIPI_INFO_INT *)`
- caller_count: `2`
- callee_count: `21`
- tags: ``

## callers

- `0x1400becfc`
- `0x1401c3bdc`

## callees

- `0x140040328`
- `0x140044ce0`
- `0x140044de0`
- `0x140045284`
- `0x140045670`
- `0x1400456d8`
- `0x140045730`
- `0x140045778`
- `0x1400458a0`
- `0x140045e3c`
- `0x1400472f0`
- `0x1400474b4`
- `0x140047508`
- `0x140047654`
- `0x14008930c`
- `0x14011e498`
- `0x14011e4f0`
- `0x140120514`
- `0x14015ea54`
- `0x1401a4a54`
- `0x1401aab9c`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140045a79`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140045a79`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140045a68`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140045a68`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140045aa5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140045aa5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140045a99`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140045a99`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140045abe`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140045abe`
- `WIN32K!W32GetUserSessionState` at `0x140045921`
- `WIN32K!W32GetUserSessionState` at `0x14004593a`
- `WIN32K!W32GetUserSessionState` at `0x140045972`
- `WIN32K!W32GetUserSessionState` at `0x140045a38`
- `WIN32K!W32GetUserSessionState` at `0x140045bc3`
- `WIN32K!W32GetUserSessionState` at `0x140045bd2`
- `WIN32K!W32GetUserSessionState` at `0x140045c02`
- `WIN32K!W32GetUserSessionState` at `0x140045c11`
- `WIN32K!W32GetUserSessionState` at `0x140045c32`
- `WIN32K!W32GetUserSessionState` at `0x140045c41`
- `WIN32K!W32GetUserSessionState` at `0x140045c68`
- `WIN32K!W32GetUserSessionState` at `0x140045c77`
- `WIN32K!W32GetUserSessionState` at `0x140045c98`
- `WIN32K!W32GetUserSessionState` at `0x140045cb4`
- `WIN32K!W32GetUserSessionState` at `0x140045921`
- `WIN32K!W32GetUserSessionState` at `0x14004593a`
- `WIN32K!W32GetUserSessionState` at `0x140045972`
- `WIN32K!W32GetUserSessionState` at `0x140045a38`
- `WIN32K!W32GetUserSessionState` at `0x140045bc3`
- `WIN32K!W32GetUserSessionState` at `0x140045bd2`
- `WIN32K!W32GetUserSessionState` at `0x140045c02`
- `WIN32K!W32GetUserSessionState` at `0x140045c11`
- `WIN32K!W32GetUserSessionState` at `0x140045c32`
- `WIN32K!W32GetUserSessionState` at `0x140045c41`
- `WIN32K!W32GetUserSessionState` at `0x140045c68`
- `WIN32K!W32GetUserSessionState` at `0x140045c77`
- `WIN32K!W32GetUserSessionState` at `0x140045c98`
- `WIN32K!W32GetUserSessionState` at `0x140045cb4`
- `HAL!KeQueryPerformanceCounter` at `0x1400458da`
- `HAL!KeQueryPerformanceCounter` at `0x140045a50`
- `HAL!KeQueryPerformanceCounter` at `0x1400458da`
- `HAL!KeQueryPerformanceCounter` at `0x140045a50`

## pseudocode

```c

```
