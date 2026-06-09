# xxxRealDefWindowProc

- ea: `0x1400ebc3c`
- end: `0x1400edcc5`
- name: `xxxRealDefWindowProc`
- size: `8329`
- prototype: `unsigned __int64 __fastcall(struct tagWND *, __int64, unsigned __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `110`
- tags: `authz_impersonation`

## callers

- `0x1400cf1d0`
- `0x1400eba30`

## callees

- `0x140005458`
- `0x140006438`
- `0x140006ad8`
- `0x140007e18`
- `0x140008a0c`
- `0x14000a36c`
- `0x14000a408`
- `0x140012790`
- `0x1400182d8`
- `0x140019430`
- `0x140019de0`
- `0x14001a8b0`
- `0x14001adf0`
- `0x14001af00`
- `0x14001b9c0`
- `0x14001e950`
- `0x14001ea78`
- `0x14001ef90`
- `0x1400206b0`
- `0x140020804`
- `0x140022c20`
- `0x140022c54`
- `0x140023570`
- `0x1400235ec`
- `0x1400241fc`
- `0x14002427c`
- `0x140026be4`
- `0x140026dbc`
- `0x140027a18`
- `0x140027e5c`
- `0x140028464`
- `0x1400285e4`
- `0x140028788`
- `0x14002a31c`
- `0x140030da0`
- `0x1400381cc`
- `0x140039338`
- `0x14003c054`
- `0x14003c61c`
- `0x140081b40`
- `0x1400824b0`
- `0x140082c38`
- `0x140086f20`
- `0x140094974`
- `0x140095638`
- `0x140096200`
- `0x140098244`
- `0x1400ba214`
- `0x1400bc768`
- `0x1400bc86c`

## import_xrefs

- `ntoskrnl!RtlUnicodeToMultiByteSize` at `0x1400ec647`
- `ntoskrnl!RtlUnicodeToMultiByteSize` at `0x1400ec647`
- `win32kbase!_GetDCEx` at `0x1400ebf5f`
- `win32kbase!_GetDCEx` at `0x1400ed076`
- `win32kbase!_GetDCEx` at `0x1400ebf5f`
- `win32kbase!_GetDCEx` at `0x1400ed076`
- `win32kbase!_ReleaseDC` at `0x1400ebf94`
- `win32kbase!_ReleaseDC` at `0x1400ed096`
- `win32kbase!_ReleaseDC` at `0x1400ebf94`
- `win32kbase!_ReleaseDC` at `0x1400ed096`
- `win32kbase!_GetKeyState` at `0x1400ed038`
- `win32kbase!_GetKeyState` at `0x1400ed038`
- `win32kbase!xxxActivateKeyboardLayout` at `0x1400ec297`
- `win32kbase!xxxActivateKeyboardLayout` at `0x1400ec297`
- `win32kbase!GetMouseKeyFlags` at `0x1400ed935`
- `win32kbase!GetMouseKeyFlags` at `0x1400ed935`
- `win32kbase!EtwTraceUIPIMsgError` at `0x1400ec430`
- `win32kbase!EtwTraceUIPIMsgError` at `0x1400ec430`
- `win32kbase!IsKeyboardDelegationTarget` at `0x1400ec272`
- `win32kbase!IsKeyboardDelegationTarget` at `0x1400ec272`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400ec40a`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400ec40a`
- `win32kbase!ValidateHwnd` at `0x1400ec91c`
- `win32kbase!ValidateHwnd` at `0x1400ec91c`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400ec3c1`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400ec3c1`
- `WIN32K!W32GetUserSessionState` at `0x1400ec148`
- `WIN32K!W32GetUserSessionState` at `0x1400ec216`
- `WIN32K!W32GetUserSessionState` at `0x1400ec255`
- `WIN32K!W32GetUserSessionState` at `0x1400ec595`
- `WIN32K!W32GetUserSessionState` at `0x1400ec7cd`
- `WIN32K!W32GetUserSessionState` at `0x1400ecce5`
- `WIN32K!W32GetUserSessionState` at `0x1400ed4d8`
- `WIN32K!W32GetUserSessionState` at `0x1400ed4f5`
- `WIN32K!W32GetUserSessionState` at `0x1400ed512`
- `WIN32K!W32GetUserSessionState` at `0x1400ed542`
- `WIN32K!W32GetUserSessionState` at `0x1400ed58a`
- `WIN32K!W32GetUserSessionState` at `0x1400ed5a3`
- `WIN32K!W32GetUserSessionState` at `0x1400ed5c0`
- `WIN32K!W32GetUserSessionState` at `0x1400ed6f8`
- `WIN32K!W32GetUserSessionState` at `0x1400ed719`
- `WIN32K!W32GetUserSessionState` at `0x1400ed732`
- `WIN32K!W32GetUserSessionState` at `0x1400ed74d`
- `WIN32K!W32GetUserSessionState` at `0x1400ed766`
- `WIN32K!W32GetUserSessionState` at `0x1400ed78d`
- `WIN32K!W32GetUserSessionState` at `0x1400ed7ae`
- `WIN32K!W32GetUserSessionState` at `0x1400ed7cf`
- `WIN32K!W32GetUserSessionState` at `0x1400ed7fd`
- `WIN32K!W32GetUserSessionState` at `0x1400ed81b`
- `WIN32K!W32GetUserSessionState` at `0x1400ed839`
- `WIN32K!W32GetUserSessionState` at `0x1400edaa2`
- `WIN32K!W32GetUserSessionState` at `0x1400ec148`
- `WIN32K!W32GetUserSessionState` at `0x1400ec216`
- `WIN32K!W32GetUserSessionState` at `0x1400ec255`
- `WIN32K!W32GetUserSessionState` at `0x1400ec595`
- `WIN32K!W32GetUserSessionState` at `0x1400ec7cd`
- `WIN32K!W32GetUserSessionState` at `0x1400ecce5`
- `WIN32K!W32GetUserSessionState` at `0x1400ed4d8`
- `WIN32K!W32GetUserSessionState` at `0x1400ed4f5`
- `WIN32K!W32GetUserSessionState` at `0x1400ed512`
- `WIN32K!W32GetUserSessionState` at `0x1400ed542`
- `WIN32K!W32GetUserSessionState` at `0x1400ed58a`
- `WIN32K!W32GetUserSessionState` at `0x1400ed5a3`
- `WIN32K!W32GetUserSessionState` at `0x1400ed5c0`
- `WIN32K!W32GetUserSessionState` at `0x1400ed6f8`
- `WIN32K!W32GetUserSessionState` at `0x1400ed719`
- `WIN32K!W32GetUserSessionState` at `0x1400ed732`
- `WIN32K!W32GetUserSessionState` at `0x1400ed74d`
- `WIN32K!W32GetUserSessionState` at `0x1400ed766`
- `WIN32K!W32GetUserSessionState` at `0x1400ed78d`
- `WIN32K!W32GetUserSessionState` at `0x1400ed7ae`
- `WIN32K!W32GetUserSessionState` at `0x1400ed7cf`
- `WIN32K!W32GetUserSessionState` at `0x1400ed7fd`
- `WIN32K!W32GetUserSessionState` at `0x1400ed81b`
- `WIN32K!W32GetUserSessionState` at `0x1400ed839`
- `WIN32K!W32GetUserSessionState` at `0x1400edaa2`

## pseudocode

```c

```
