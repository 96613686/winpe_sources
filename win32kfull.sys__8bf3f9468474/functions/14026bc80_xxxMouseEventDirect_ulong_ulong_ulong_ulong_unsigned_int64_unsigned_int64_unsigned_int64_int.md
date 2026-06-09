# xxxMouseEventDirect(ulong,ulong,ulong,ulong,unsigned __int64,unsigned __int64,unsigned __int64,int)

- ea: `0x14026bc80`
- end: `0x14026c3ca`
- name: `?xxxMouseEventDirect@@YAHKKKK_K00H@Z`
- size: `1866`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int, unsigned int, unsigned __int64, unsigned __int64, unsigned __int64, int)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x1401ac8bc`
- `0x14026c3d0`

## callees

- `0x1400381a8`
- `0x1400b71ac`
- `0x1400bcaa0`
- `0x140124878`
- `0x1401751f4`
- `0x1401957e4`
- `0x1401ac45c`
- `0x140259b84`
- `0x140260964`
- `0x14026b294`
- `0x14026bc80`
- `0x140341ff0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14026bda4`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026bda4`
- `win32kbase!EtwTraceEndInjectMouse` at `0x14026c39a`
- `win32kbase!EtwTraceEndInjectMouse` at `0x14026c39a`
- `win32kbase!ResetAccessibilityCountersOnMouseInput` at `0x14026c386`
- `win32kbase!ResetAccessibilityCountersOnMouseInput` at `0x14026c386`
- `win32kbase!xxxProcessMouseEvent` at `0x14026c365`
- `win32kbase!xxxProcessMouseEvent` at `0x14026c365`
- `win32kbase!SynthesizeMouseInput` at `0x14026c344`
- `win32kbase!SynthesizeMouseInput` at `0x14026c344`
- `win32kbase!EtwTraceBeginInjectMouse` at `0x14026bfbd`
- `win32kbase!EtwTraceBeginInjectMouse` at `0x14026bfbd`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x14026c196`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x14026c22a`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x14026c196`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x14026c22a`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x14026c244`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x14026c244`
- `win32kbase!EnterCrit` at `0x14026c355`
- `win32kbase!EnterCrit` at `0x14026c355`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x14026c2bc`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x14026c2bc`
- `win32kbase!EngMulDiv` at `0x14026c1f3`
- `win32kbase!EngMulDiv` at `0x14026c211`
- `win32kbase!EngMulDiv` at `0x14026c276`
- `win32kbase!EngMulDiv` at `0x14026c291`
- `win32kbase!EngMulDiv` at `0x14026c1f3`
- `win32kbase!EngMulDiv` at `0x14026c211`
- `win32kbase!EngMulDiv` at `0x14026c276`
- `win32kbase!EngMulDiv` at `0x14026c291`
- `WIN32K!W32GetUserGdiSessionState` at `0x14026bd94`
- `WIN32K!W32GetUserGdiSessionState` at `0x14026bd94`
- `WIN32K!W32GetUserSessionState` at `0x14026bce4`
- `WIN32K!W32GetUserSessionState` at `0x14026bd51`
- `WIN32K!W32GetUserSessionState` at `0x14026be07`
- `WIN32K!W32GetUserSessionState` at `0x14026be5b`
- `WIN32K!W32GetUserSessionState` at `0x14026be75`
- `WIN32K!W32GetUserSessionState` at `0x14026bed7`
- `WIN32K!W32GetUserSessionState` at `0x14026bf64`
- `WIN32K!W32GetUserSessionState` at `0x14026c023`
- `WIN32K!W32GetUserSessionState` at `0x14026c1ad`
- `WIN32K!W32GetUserSessionState` at `0x14026c371`
- `WIN32K!W32GetUserSessionState` at `0x14026bce4`
- `WIN32K!W32GetUserSessionState` at `0x14026bd51`
- `WIN32K!W32GetUserSessionState` at `0x14026be07`
- `WIN32K!W32GetUserSessionState` at `0x14026be5b`
- `WIN32K!W32GetUserSessionState` at `0x14026be75`
- `WIN32K!W32GetUserSessionState` at `0x14026bed7`
- `WIN32K!W32GetUserSessionState` at `0x14026bf64`
- `WIN32K!W32GetUserSessionState` at `0x14026c023`
- `WIN32K!W32GetUserSessionState` at `0x14026c1ad`
- `WIN32K!W32GetUserSessionState` at `0x14026c371`
- `HAL!KeQueryPerformanceCounter` at `0x14026bff7`
- `HAL!KeQueryPerformanceCounter` at `0x14026bff7`

## pseudocode

```c

```
