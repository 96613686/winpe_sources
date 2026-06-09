# xxxMouseEventDirect(ulong,ulong,ulong,ulong,unsigned __int64,unsigned __int64,unsigned __int64,int)

- ea: `0x14026f150`
- end: `0x14026f8b6`
- name: `?xxxMouseEventDirect@@YAHKKKK_K00H@Z`
- size: `1894`
- prototype: `__int64 __fastcall(__int64, __int64, int, int, unsigned __int64, unsigned __int64, unsigned __int64, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1401a7ddc`
- `0x14026f8bc`

## callees

- `0x140033b58`
- `0x1400dd43c`
- `0x1400e2cb0`
- `0x14012ae08`
- `0x1401986d8`
- `0x1401a797c`
- `0x140214aac`
- `0x14025b364`
- `0x140263008`
- `0x14026e764`
- `0x14026f150`
- `0x1402aae84`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14026f270`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026f270`
- `win32kbase!EtwTraceEndInjectMouse` at `0x14026f886`
- `win32kbase!EtwTraceEndInjectMouse` at `0x14026f886`
- `win32kbase!ResetAccessibilityCountersOnMouseInput` at `0x14026f872`
- `win32kbase!ResetAccessibilityCountersOnMouseInput` at `0x14026f872`
- `win32kbase!xxxProcessMouseEvent` at `0x14026f851`
- `win32kbase!xxxProcessMouseEvent` at `0x14026f851`
- `win32kbase!SynthesizeMouseInput` at `0x14026f830`
- `win32kbase!SynthesizeMouseInput` at `0x14026f830`
- `win32kbase!?Enforced@UIPrivilegeIsolation@@YA_NXZ` at `0x14026f7d9`
- `win32kbase!?Enforced@UIPrivilegeIsolation@@YA_NXZ` at `0x14026f7d9`
- `win32kbase!EtwTraceBeginInjectMouse` at `0x14026f488`
- `win32kbase!EtwTraceBeginInjectMouse` at `0x14026f488`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x14026f662`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x14026f6f6`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x14026f662`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x14026f6f6`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x14026f710`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x14026f710`
- `win32kbase!EnterCrit` at `0x14026f841`
- `win32kbase!EnterCrit` at `0x14026f841`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x14026f786`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x14026f786`
- `win32kbase!EngMulDiv` at `0x14026f6bf`
- `win32kbase!EngMulDiv` at `0x14026f6dd`
- `win32kbase!EngMulDiv` at `0x14026f742`
- `win32kbase!EngMulDiv` at `0x14026f75d`
- `win32kbase!EngMulDiv` at `0x14026f6bf`
- `win32kbase!EngMulDiv` at `0x14026f6dd`
- `win32kbase!EngMulDiv` at `0x14026f742`
- `win32kbase!EngMulDiv` at `0x14026f75d`
- `WIN32K!W32GetUserGdiSessionState` at `0x14026f260`
- `WIN32K!W32GetUserGdiSessionState` at `0x14026f260`
- `WIN32K!W32GetUserSessionState` at `0x14026f1af`
- `WIN32K!W32GetUserSessionState` at `0x14026f21c`
- `WIN32K!W32GetUserSessionState` at `0x14026f2d3`
- `WIN32K!W32GetUserSessionState` at `0x14026f326`
- `WIN32K!W32GetUserSessionState` at `0x14026f340`
- `WIN32K!W32GetUserSessionState` at `0x14026f3a2`
- `WIN32K!W32GetUserSessionState` at `0x14026f42f`
- `WIN32K!W32GetUserSessionState` at `0x14026f4ef`
- `WIN32K!W32GetUserSessionState` at `0x14026f679`
- `WIN32K!W32GetUserSessionState` at `0x14026f85d`
- `WIN32K!W32GetUserSessionState` at `0x14026f1af`
- `WIN32K!W32GetUserSessionState` at `0x14026f21c`
- `WIN32K!W32GetUserSessionState` at `0x14026f2d3`
- `WIN32K!W32GetUserSessionState` at `0x14026f326`
- `WIN32K!W32GetUserSessionState` at `0x14026f340`
- `WIN32K!W32GetUserSessionState` at `0x14026f3a2`
- `WIN32K!W32GetUserSessionState` at `0x14026f42f`
- `WIN32K!W32GetUserSessionState` at `0x14026f4ef`
- `WIN32K!W32GetUserSessionState` at `0x14026f679`
- `WIN32K!W32GetUserSessionState` at `0x14026f85d`
- `HAL!KeQueryPerformanceCounter` at `0x14026f4c3`
- `HAL!KeQueryPerformanceCounter` at `0x14026f4c3`

## pseudocode

```c

```
