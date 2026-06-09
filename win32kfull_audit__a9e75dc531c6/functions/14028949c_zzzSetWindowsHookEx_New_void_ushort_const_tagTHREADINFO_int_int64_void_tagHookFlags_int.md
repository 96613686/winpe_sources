# zzzSetWindowsHookEx_New(void *,ushort const *,tagTHREADINFO *,int,__int64 (*)(void),tagHookFlags,int *)

- ea: `0x14028949c`
- end: `0x140289fa2`
- name: `?zzzSetWindowsHookEx_New@@YAPEAUHHOOK__@@PEAXPEBGPEAUtagTHREADINFO@@HP6A_JXZW4tagHookFlags@@PEAH@Z`
- size: `2822`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, __int64, char, _DWORD *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x14022f450`
- `0x1402c3ae0`

## callees

- `0x1400c18a0`
- `0x1400c58cc`
- `0x1400c5adc`
- `0x1400c5cf8`
- `0x1400dadac`
- `0x1400dd43c`
- `0x1400e2cb0`
- `0x1400e8c20`
- `0x14017cc14`
- `0x1401895f8`
- `0x14028949c`
- `0x1402aae84`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!KeDetachProcess` at `0x140289d8d`
- `ntoskrnl!KeDetachProcess` at `0x140289d8d`
- `ntoskrnl!KeAttachProcess` at `0x140289d15`
- `ntoskrnl!KeAttachProcess` at `0x140289d15`
- `ntoskrnl!RtlAreAllAccessesGranted` at `0x140289678`
- `ntoskrnl!RtlAreAllAccessesGranted` at `0x140289678`
- `win32kbase!?Enforced@UIPrivilegeIsolation@@YA_NXZ` at `0x1402898bc`
- `win32kbase!?Enforced@UIPrivilegeIsolation@@YA_NXZ` at `0x1402898bc`
- `win32kbase!HMAllocObject` at `0x140289b00`
- `win32kbase!HMAllocObject` at `0x140289b00`
- `win32kbase!HMFreeObject` at `0x140289ca0`
- `win32kbase!HMFreeObject` at `0x140289ca0`
- `WIN32K!W32GetUserSessionState` at `0x140289585`
- `WIN32K!W32GetUserSessionState` at `0x140289635`
- `WIN32K!W32GetUserSessionState` at `0x14028973a`
- `WIN32K!W32GetUserSessionState` at `0x1402897d9`
- `WIN32K!W32GetUserSessionState` at `0x140289884`
- `WIN32K!W32GetUserSessionState` at `0x14028996b`
- `WIN32K!W32GetUserSessionState` at `0x140289a13`
- `WIN32K!W32GetUserSessionState` at `0x140289a89`
- `WIN32K!W32GetUserSessionState` at `0x140289b73`
- `WIN32K!W32GetUserSessionState` at `0x140289c47`
- `WIN32K!W32GetUserSessionState` at `0x140289e6d`
- `WIN32K!W32GetUserSessionState` at `0x140289f2e`
- `WIN32K!W32GetUserSessionState` at `0x140289585`
- `WIN32K!W32GetUserSessionState` at `0x140289635`
- `WIN32K!W32GetUserSessionState` at `0x14028973a`
- `WIN32K!W32GetUserSessionState` at `0x1402897d9`
- `WIN32K!W32GetUserSessionState` at `0x140289884`
- `WIN32K!W32GetUserSessionState` at `0x14028996b`
- `WIN32K!W32GetUserSessionState` at `0x140289a13`
- `WIN32K!W32GetUserSessionState` at `0x140289a89`
- `WIN32K!W32GetUserSessionState` at `0x140289b73`
- `WIN32K!W32GetUserSessionState` at `0x140289c47`
- `WIN32K!W32GetUserSessionState` at `0x140289e6d`
- `WIN32K!W32GetUserSessionState` at `0x140289f2e`

## pseudocode

```c

```
