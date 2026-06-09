# xxxCreateDesktopEx2(tagWINDOWSTATION *,_ACCESS_STATE *,char,_UNICODE_STRING *,ulong,void * *)

- ea: `0x1401e34bc`
- end: `0x1401e3903`
- name: `?xxxCreateDesktopEx2@@YAJPEAUtagWINDOWSTATION@@PEAU_ACCESS_STATE@@DPEAU_UNICODE_STRING@@KPEAPEAX@Z`
- size: `1095`
- prototype: `__int64 __fastcall(struct tagWINDOWSTATION *, struct _ACCESS_STATE *, __int64, struct _UNICODE_STRING *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1401e3350`

## callees

- `0x140027de0`
- `0x1400e2cb0`
- `0x1401e34bc`
- `0x1401e390c`
- `0x1401e3a50`

## import_xrefs

- `ntoskrnl!RtlMapGenericMask` at `0x1401e36e8`
- `ntoskrnl!RtlMapGenericMask` at `0x1401e36e8`
- `ntoskrnl!ObCheckCreateObjectAccess` at `0x1401e34ff`
- `ntoskrnl!ObCheckCreateObjectAccess` at `0x1401e34ff`
- `ntoskrnl!RtlFreeHeap` at `0x1401e387d`
- `ntoskrnl!RtlFreeHeap` at `0x1401e387d`
- `ntoskrnl!PsGetProcessId` at `0x1401e376f`
- `ntoskrnl!PsGetProcessId` at `0x1401e376f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401e3513`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401e3513`
- `ntoskrnl!ObfDereferenceObject` at `0x1401e3748`
- `ntoskrnl!ObfDereferenceObject` at `0x1401e3748`
- `win32kbase!UserLogError` at `0x1401e385c`
- `win32kbase!UserLogError` at `0x1401e385c`
- `win32kbase!LockObjectAssignment` at `0x1401e3684`
- `win32kbase!LockObjectAssignment` at `0x1401e36a9`
- `win32kbase!LockObjectAssignment` at `0x1401e36bc`
- `win32kbase!LockObjectAssignment` at `0x1401e38af`
- `win32kbase!LockObjectAssignment` at `0x1401e38cb`
- `win32kbase!LockObjectAssignment` at `0x1401e38f2`
- `win32kbase!LockObjectAssignment` at `0x1401e3684`
- `win32kbase!LockObjectAssignment` at `0x1401e36a9`
- `win32kbase!LockObjectAssignment` at `0x1401e36bc`
- `win32kbase!LockObjectAssignment` at `0x1401e38af`
- `win32kbase!LockObjectAssignment` at `0x1401e38cb`
- `win32kbase!LockObjectAssignment` at `0x1401e38f2`
- `win32kbase!GetProcessLuid` at `0x1401e3792`
- `win32kbase!GetProcessLuid` at `0x1401e3792`
- `win32kbase!CreateDesktopObObject` at `0x1401e353b`
- `win32kbase!CreateDesktopObObject` at `0x1401e353b`
- `win32kbase!GetDesktopHeapSize` at `0x1401e3572`
- `win32kbase!GetDesktopHeapSize` at `0x1401e3572`
- `win32kbase!DesktopMapping` at `0x1401e36de`
- `win32kbase!DesktopMapping` at `0x1401e36f4`
- `win32kbase!Win32AllocPoolZInit` at `0x1401e3601`
- `win32kbase!Win32AllocPoolZInit` at `0x1401e3601`
- `WIN32K!W32GetUserSessionState` at `0x1401e3759`
- `WIN32K!W32GetUserSessionState` at `0x1401e37d7`
- `WIN32K!W32GetUserSessionState` at `0x1401e37f9`
- `WIN32K!W32GetUserSessionState` at `0x1401e381e`
- `WIN32K!W32GetUserSessionState` at `0x1401e383d`
- `WIN32K!W32GetUserSessionState` at `0x1401e3899`
- `WIN32K!W32GetUserSessionState` at `0x1401e38dc`
- `WIN32K!W32GetUserSessionState` at `0x1401e3759`
- `WIN32K!W32GetUserSessionState` at `0x1401e37d7`
- `WIN32K!W32GetUserSessionState` at `0x1401e37f9`
- `WIN32K!W32GetUserSessionState` at `0x1401e381e`
- `WIN32K!W32GetUserSessionState` at `0x1401e383d`
- `WIN32K!W32GetUserSessionState` at `0x1401e3899`
- `WIN32K!W32GetUserSessionState` at `0x1401e38dc`

## pseudocode

```c

```
