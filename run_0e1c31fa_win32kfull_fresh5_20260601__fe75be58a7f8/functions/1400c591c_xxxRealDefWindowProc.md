# xxxRealDefWindowProc

- ea: `0x1400c591c`
- end: `0x1400c79a5`
- name: `xxxRealDefWindowProc`
- size: `8329`
- prototype: `__int64 __fastcall(struct tagWND *, unsigned int, unsigned __int64, __int64)`
- caller_count: `2`
- callee_count: `110`
- tags: `authz_impersonation`

## callers

- `0x14000b0f0`
- `0x1400c5710`

## callees

- `0x140004c3c`
- `0x140004cd8`
- `0x140006e8c`
- `0x140009f7c`
- `0x14000b370`
- `0x14000b5bc`
- `0x14000ca28`
- `0x14000cd90`
- `0x14000f8f4`
- `0x14000f984`
- `0x14001cc54`
- `0x14001ec90`
- `0x14001f8a0`
- `0x140020370`
- `0x1400208b0`
- `0x1400209c0`
- `0x140020d30`
- `0x140023ac0`
- `0x140023be8`
- `0x140024100`
- `0x1400257a0`
- `0x1400258f4`
- `0x140027d10`
- `0x140027d44`
- `0x140028660`
- `0x1400286dc`
- `0x1400292ec`
- `0x14002936c`
- `0x14002bca4`
- `0x14002be7c`
- `0x14002cad8`
- `0x14002cf1c`
- `0x14002d524`
- `0x14002d6a4`
- `0x14002d848`
- `0x14002e99c`
- `0x140035420`
- `0x14005d094`
- `0x140085c00`
- `0x140085eb8`
- `0x1400a59f0`
- `0x1400a64a8`
- `0x1400abef8`
- `0x1400ae950`
- `0x1400aec3c`
- `0x1400af0e0`
- `0x1400b0b40`
- `0x1400b1334`
- `0x1400b162c`
- `0x1400b1810`

## import_xrefs

- `ntoskrnl!RtlUnicodeToMultiByteSize` at `0x1400c6327`
- `ntoskrnl!RtlUnicodeToMultiByteSize` at `0x1400c6327`
- `win32kbase!_GetDCEx` at `0x1400c5c3f`
- `win32kbase!_GetDCEx` at `0x1400c6d56`
- `win32kbase!_GetDCEx` at `0x1400c5c3f`
- `win32kbase!_GetDCEx` at `0x1400c6d56`
- `win32kbase!_ReleaseDC` at `0x1400c5c74`
- `win32kbase!_ReleaseDC` at `0x1400c6d76`
- `win32kbase!_ReleaseDC` at `0x1400c5c74`
- `win32kbase!_ReleaseDC` at `0x1400c6d76`
- `win32kbase!_GetKeyState` at `0x1400c6d18`
- `win32kbase!_GetKeyState` at `0x1400c6d18`
- `win32kbase!xxxActivateKeyboardLayout` at `0x1400c5f77`
- `win32kbase!xxxActivateKeyboardLayout` at `0x1400c5f77`
- `win32kbase!GetMouseKeyFlags` at `0x1400c7615`
- `win32kbase!GetMouseKeyFlags` at `0x1400c7615`
- `win32kbase!EtwTraceUIPIMsgError` at `0x1400c6110`
- `win32kbase!EtwTraceUIPIMsgError` at `0x1400c6110`
- `win32kbase!IsKeyboardDelegationTarget` at `0x1400c5f52`
- `win32kbase!IsKeyboardDelegationTarget` at `0x1400c5f52`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400c60ea`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400c60ea`
- `win32kbase!ValidateHwnd` at `0x1400c65fc`
- `win32kbase!ValidateHwnd` at `0x1400c65fc`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400c60a1`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400c60a1`
- `WIN32K!W32GetUserSessionState` at `0x1400c5e28`
- `WIN32K!W32GetUserSessionState` at `0x1400c5ef6`
- `WIN32K!W32GetUserSessionState` at `0x1400c5f35`
- `WIN32K!W32GetUserSessionState` at `0x1400c6275`
- `WIN32K!W32GetUserSessionState` at `0x1400c64ad`
- `WIN32K!W32GetUserSessionState` at `0x1400c69c5`
- `WIN32K!W32GetUserSessionState` at `0x1400c71b8`
- `WIN32K!W32GetUserSessionState` at `0x1400c71d5`
- `WIN32K!W32GetUserSessionState` at `0x1400c71f2`
- `WIN32K!W32GetUserSessionState` at `0x1400c7222`
- `WIN32K!W32GetUserSessionState` at `0x1400c726a`
- `WIN32K!W32GetUserSessionState` at `0x1400c7283`
- `WIN32K!W32GetUserSessionState` at `0x1400c72a0`
- `WIN32K!W32GetUserSessionState` at `0x1400c73d8`
- `WIN32K!W32GetUserSessionState` at `0x1400c73f9`
- `WIN32K!W32GetUserSessionState` at `0x1400c7412`
- `WIN32K!W32GetUserSessionState` at `0x1400c742d`
- `WIN32K!W32GetUserSessionState` at `0x1400c7446`
- `WIN32K!W32GetUserSessionState` at `0x1400c746d`
- `WIN32K!W32GetUserSessionState` at `0x1400c748e`
- `WIN32K!W32GetUserSessionState` at `0x1400c74af`
- `WIN32K!W32GetUserSessionState` at `0x1400c74dd`
- `WIN32K!W32GetUserSessionState` at `0x1400c74fb`
- `WIN32K!W32GetUserSessionState` at `0x1400c7519`
- `WIN32K!W32GetUserSessionState` at `0x1400c7782`
- `WIN32K!W32GetUserSessionState` at `0x1400c5e28`
- `WIN32K!W32GetUserSessionState` at `0x1400c5ef6`
- `WIN32K!W32GetUserSessionState` at `0x1400c5f35`
- `WIN32K!W32GetUserSessionState` at `0x1400c6275`
- `WIN32K!W32GetUserSessionState` at `0x1400c64ad`
- `WIN32K!W32GetUserSessionState` at `0x1400c69c5`
- `WIN32K!W32GetUserSessionState` at `0x1400c71b8`
- `WIN32K!W32GetUserSessionState` at `0x1400c71d5`
- `WIN32K!W32GetUserSessionState` at `0x1400c71f2`
- `WIN32K!W32GetUserSessionState` at `0x1400c7222`
- `WIN32K!W32GetUserSessionState` at `0x1400c726a`
- `WIN32K!W32GetUserSessionState` at `0x1400c7283`
- `WIN32K!W32GetUserSessionState` at `0x1400c72a0`
- `WIN32K!W32GetUserSessionState` at `0x1400c73d8`
- `WIN32K!W32GetUserSessionState` at `0x1400c73f9`
- `WIN32K!W32GetUserSessionState` at `0x1400c7412`
- `WIN32K!W32GetUserSessionState` at `0x1400c742d`
- `WIN32K!W32GetUserSessionState` at `0x1400c7446`
- `WIN32K!W32GetUserSessionState` at `0x1400c746d`
- `WIN32K!W32GetUserSessionState` at `0x1400c748e`
- `WIN32K!W32GetUserSessionState` at `0x1400c74af`
- `WIN32K!W32GetUserSessionState` at `0x1400c74dd`
- `WIN32K!W32GetUserSessionState` at `0x1400c74fb`
- `WIN32K!W32GetUserSessionState` at `0x1400c7519`
- `WIN32K!W32GetUserSessionState` at `0x1400c7782`

## pseudocode

```c

```
