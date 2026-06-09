# xxxCreateDesktopEx2(tagWINDOWSTATION *,_ACCESS_STATE *,char,_UNICODE_STRING *,ulong,void * *)

- ea: `0x1401e673c`
- end: `0x1401e6b83`
- name: `?xxxCreateDesktopEx2@@YAJPEAUtagWINDOWSTATION@@PEAU_ACCESS_STATE@@DPEAU_UNICODE_STRING@@KPEAPEAX@Z`
- size: `1095`
- prototype: `__int64 __fastcall(struct tagWINDOWSTATION *, struct _ACCESS_STATE *, char, struct _UNICODE_STRING *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1401e65d0`

## callees

- `0x14002cea0`
- `0x1400bcaa0`
- `0x1401e673c`
- `0x1401e6b8c`
- `0x1401e6cd0`

## import_xrefs

- `ntoskrnl!RtlMapGenericMask` at `0x1401e6968`
- `ntoskrnl!RtlMapGenericMask` at `0x1401e6968`
- `ntoskrnl!ObCheckCreateObjectAccess` at `0x1401e677f`
- `ntoskrnl!ObCheckCreateObjectAccess` at `0x1401e677f`
- `ntoskrnl!RtlFreeHeap` at `0x1401e6afd`
- `ntoskrnl!RtlFreeHeap` at `0x1401e6afd`
- `ntoskrnl!PsGetProcessId` at `0x1401e69ef`
- `ntoskrnl!PsGetProcessId` at `0x1401e69ef`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401e6793`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401e6793`
- `ntoskrnl!ObfDereferenceObject` at `0x1401e69c8`
- `ntoskrnl!ObfDereferenceObject` at `0x1401e69c8`
- `win32kbase!UserLogError` at `0x1401e6adc`
- `win32kbase!UserLogError` at `0x1401e6adc`
- `win32kbase!LockObjectAssignment` at `0x1401e6904`
- `win32kbase!LockObjectAssignment` at `0x1401e6929`
- `win32kbase!LockObjectAssignment` at `0x1401e693c`
- `win32kbase!LockObjectAssignment` at `0x1401e6b2f`
- `win32kbase!LockObjectAssignment` at `0x1401e6b4b`
- `win32kbase!LockObjectAssignment` at `0x1401e6b72`
- `win32kbase!LockObjectAssignment` at `0x1401e6904`
- `win32kbase!LockObjectAssignment` at `0x1401e6929`
- `win32kbase!LockObjectAssignment` at `0x1401e693c`
- `win32kbase!LockObjectAssignment` at `0x1401e6b2f`
- `win32kbase!LockObjectAssignment` at `0x1401e6b4b`
- `win32kbase!LockObjectAssignment` at `0x1401e6b72`
- `win32kbase!GetProcessLuid` at `0x1401e6a12`
- `win32kbase!GetProcessLuid` at `0x1401e6a12`
- `win32kbase!CreateDesktopObObject` at `0x1401e67bb`
- `win32kbase!CreateDesktopObObject` at `0x1401e67bb`
- `win32kbase!GetDesktopHeapSize` at `0x1401e67f2`
- `win32kbase!GetDesktopHeapSize` at `0x1401e67f2`
- `win32kbase!DesktopMapping` at `0x1401e695e`
- `win32kbase!DesktopMapping` at `0x1401e6974`
- `win32kbase!Win32AllocPoolZInit` at `0x1401e6881`
- `win32kbase!Win32AllocPoolZInit` at `0x1401e6881`
- `WIN32K!W32GetUserSessionState` at `0x1401e69d9`
- `WIN32K!W32GetUserSessionState` at `0x1401e6a57`
- `WIN32K!W32GetUserSessionState` at `0x1401e6a79`
- `WIN32K!W32GetUserSessionState` at `0x1401e6a9e`
- `WIN32K!W32GetUserSessionState` at `0x1401e6abd`
- `WIN32K!W32GetUserSessionState` at `0x1401e6b19`
- `WIN32K!W32GetUserSessionState` at `0x1401e6b5c`
- `WIN32K!W32GetUserSessionState` at `0x1401e69d9`
- `WIN32K!W32GetUserSessionState` at `0x1401e6a57`
- `WIN32K!W32GetUserSessionState` at `0x1401e6a79`
- `WIN32K!W32GetUserSessionState` at `0x1401e6a9e`
- `WIN32K!W32GetUserSessionState` at `0x1401e6abd`
- `WIN32K!W32GetUserSessionState` at `0x1401e6b19`
- `WIN32K!W32GetUserSessionState` at `0x1401e6b5c`

## pseudocode

```c

```
