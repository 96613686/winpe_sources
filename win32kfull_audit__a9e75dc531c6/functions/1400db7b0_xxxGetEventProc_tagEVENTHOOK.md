# xxxGetEventProc(tagEVENTHOOK *)

- ea: `0x1400db7b0`
- end: `0x1400dbb48`
- name: `?xxxGetEventProc@@YAP6AXPEAUHWINEVENTHOOK__@@KPEAUHWND__@@JJKK@ZPEAUtagEVENTHOOK@@@Z`
- size: `920`
- prototype: `void (*__fastcall(struct tagEVENTHOOK *, __int64, __int64, __int64))(HWINEVENTHOOK, unsigned int, HWND, int, int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001fdf8`

## callees

- `0x1400c5cf8`
- `0x1400db7b0`
- `0x1400dbb50`
- `0x1400dc1a4`

## import_xrefs

- `ntoskrnl!PsIsProtectedProcess` at `0x1400db8b6`
- `ntoskrnl!PsIsProtectedProcess` at `0x1400db8b6`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400db7d3`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400db7d3`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400db8a7`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400db8a7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400db891`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400dba14`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400db891`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400dba14`
- `win32kbase!?getDLT@DLT_WINEVENT@@SA?AW4DomainLockType@@XZ` at `0x1400db8ca`
- `win32kbase!?getDLT@DLT_WINEVENT@@SA?AW4DomainLockType@@XZ` at `0x1400db8ca`
- `win32kbase!?getDLT@DLT_HANDLEMANAGER@@SA?AW4DomainLockType@@XZ` at `0x1400db7e5`
- `win32kbase!?getDLT@DLT_HANDLEMANAGER@@SA?AW4DomainLockType@@XZ` at `0x1400db966`
- `win32kbase!?getDLT@DLT_HANDLEMANAGER@@SA?AW4DomainLockType@@XZ` at `0x1400db7e5`
- `win32kbase!?getDLT@DLT_HANDLEMANAGER@@SA?AW4DomainLockType@@XZ` at `0x1400db966`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x1400db7f3`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x1400db8d8`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x1400db974`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x1400db7f3`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x1400db8d8`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x1400db974`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400db843`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400db9bc`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400dba70`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400dbb2e`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400db843`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400db9bc`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400dba70`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400dbb2e`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400db95a`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400dbae9`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400dbafa`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400dbb20`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400db95a`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400dbae9`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400dbafa`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400dbb20`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400dba5f`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400dba81`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400dbab7`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400dbac5`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400dba5f`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400dba81`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400dbab7`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400dbac5`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400db885`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400db920`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400db9fe`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400dbaa7`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400db885`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400db920`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400db9fe`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400dbaa7`
- `win32kbase!_HMPheFromObject` at `0x1400db856`
- `win32kbase!_HMPheFromObject` at `0x1400db9cf`
- `win32kbase!_HMPheFromObject` at `0x1400db856`
- `win32kbase!_HMPheFromObject` at `0x1400db9cf`
- `WIN32K!W32GetUserSessionState` at `0x1400db7c0`
- `WIN32K!W32GetUserSessionState` at `0x1400db809`
- `WIN32K!W32GetUserSessionState` at `0x1400db8ec`
- `WIN32K!W32GetUserSessionState` at `0x1400db988`
- `WIN32K!W32GetUserSessionState` at `0x1400db7c0`
- `WIN32K!W32GetUserSessionState` at `0x1400db809`
- `WIN32K!W32GetUserSessionState` at `0x1400db8ec`
- `WIN32K!W32GetUserSessionState` at `0x1400db988`

## pseudocode

```c

```
