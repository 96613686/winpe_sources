# CMouseProcessor::ProcessMouseInputData(CMouseProcessor::MouseInputDataEx *,MouseInputProcessingState *,_MousePacketPerf &,_MOUSE_INPUT_DATA const *,tagUIPI_INFO_INT const *)

- ea: `0x14006e470`
- end: `0x14006ea04`
- name: `?ProcessMouseInputData@CMouseProcessor@@AEAAXPEAVMouseInputDataEx@1@PEAUMouseInputProcessingState@@AEAU_MousePacketPerf@@PEBU_MOUSE_INPUT_DATA@@PEBUtagUIPI_INFO_INT@@@Z`
- size: `1428`
- prototype: `void __fastcall(CMouseProcessor *__hidden this, struct CMouseProcessor::MouseInputDataEx *, struct MouseInputProcessingState *, struct _MousePacketPerf *, const struct _MOUSE_INPUT_DATA *, const struct tagUIPI_INFO_INT *)`
- caller_count: `2`
- callee_count: `21`
- tags: ``

## callers

- `0x1400cbefc`
- `0x1401c2aac`

## callees

- `0x140057b1c`
- `0x140068ef8`
- `0x14006d8b0`
- `0x14006d9b0`
- `0x14006de54`
- `0x14006e240`
- `0x14006e2a8`
- `0x14006e300`
- `0x14006e348`
- `0x14006e470`
- `0x14006ea0c`
- `0x14006fec0`
- `0x140070084`
- `0x1400700d8`
- `0x140070224`
- `0x14011b868`
- `0x14011b8c0`
- `0x14011cd94`
- `0x14015c474`
- `0x1401a3bfc`
- `0x1401a9f9c`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006e649`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006e649`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006e638`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006e638`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006e675`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006e675`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006e669`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006e669`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14006e68e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14006e68e`
- `WIN32K!W32GetUserSessionState` at `0x14006e4f1`
- `WIN32K!W32GetUserSessionState` at `0x14006e50a`
- `WIN32K!W32GetUserSessionState` at `0x14006e542`
- `WIN32K!W32GetUserSessionState` at `0x14006e608`
- `WIN32K!W32GetUserSessionState` at `0x14006e793`
- `WIN32K!W32GetUserSessionState` at `0x14006e7a2`
- `WIN32K!W32GetUserSessionState` at `0x14006e7d2`
- `WIN32K!W32GetUserSessionState` at `0x14006e7e1`
- `WIN32K!W32GetUserSessionState` at `0x14006e802`
- `WIN32K!W32GetUserSessionState` at `0x14006e811`
- `WIN32K!W32GetUserSessionState` at `0x14006e838`
- `WIN32K!W32GetUserSessionState` at `0x14006e847`
- `WIN32K!W32GetUserSessionState` at `0x14006e868`
- `WIN32K!W32GetUserSessionState` at `0x14006e884`
- `WIN32K!W32GetUserSessionState` at `0x14006e4f1`
- `WIN32K!W32GetUserSessionState` at `0x14006e50a`
- `WIN32K!W32GetUserSessionState` at `0x14006e542`
- `WIN32K!W32GetUserSessionState` at `0x14006e608`
- `WIN32K!W32GetUserSessionState` at `0x14006e793`
- `WIN32K!W32GetUserSessionState` at `0x14006e7a2`
- `WIN32K!W32GetUserSessionState` at `0x14006e7d2`
- `WIN32K!W32GetUserSessionState` at `0x14006e7e1`
- `WIN32K!W32GetUserSessionState` at `0x14006e802`
- `WIN32K!W32GetUserSessionState` at `0x14006e811`
- `WIN32K!W32GetUserSessionState` at `0x14006e838`
- `WIN32K!W32GetUserSessionState` at `0x14006e847`
- `WIN32K!W32GetUserSessionState` at `0x14006e868`
- `WIN32K!W32GetUserSessionState` at `0x14006e884`
- `HAL!KeQueryPerformanceCounter` at `0x14006e4aa`
- `HAL!KeQueryPerformanceCounter` at `0x14006e620`
- `HAL!KeQueryPerformanceCounter` at `0x14006e4aa`
- `HAL!KeQueryPerformanceCounter` at `0x14006e620`

## pseudocode

```c

```
