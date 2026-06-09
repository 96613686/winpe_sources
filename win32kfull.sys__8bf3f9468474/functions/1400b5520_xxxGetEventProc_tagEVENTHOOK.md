# xxxGetEventProc(tagEVENTHOOK *)

- ea: `0x1400b5520`
- end: `0x1400b58b8`
- name: `?xxxGetEventProc@@YAP6AXPEAUHWINEVENTHOOK__@@KPEAUHWND__@@JJKK@ZPEAUtagEVENTHOOK@@@Z`
- size: `920`
- prototype: `void (*__fastcall(struct tagEVENTHOOK *))(HWINEVENTHOOK, unsigned int, HWND, int, int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140024f68`

## callees

- `0x1400b5520`
- `0x1400b58c0`
- `0x1400b5f14`
- `0x140120fd0`

## import_xrefs

- `ntoskrnl!PsIsProtectedProcess` at `0x1400b5626`
- `ntoskrnl!PsIsProtectedProcess` at `0x1400b5626`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400b5543`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400b5543`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b5617`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b5617`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400b5601`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400b5784`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400b5601`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400b5784`
- `win32kbase!?getDLT@DLT_WINEVENT@@SA?AW4DomainLockType@@XZ` at `0x1400b563a`
- `win32kbase!?getDLT@DLT_WINEVENT@@SA?AW4DomainLockType@@XZ` at `0x1400b563a`
- `win32kbase!?getDLT@DLT_HANDLEMANAGER@@SA?AW4DomainLockType@@XZ` at `0x1400b5555`
- `win32kbase!?getDLT@DLT_HANDLEMANAGER@@SA?AW4DomainLockType@@XZ` at `0x1400b56d6`
- `win32kbase!?getDLT@DLT_HANDLEMANAGER@@SA?AW4DomainLockType@@XZ` at `0x1400b5555`
- `win32kbase!?getDLT@DLT_HANDLEMANAGER@@SA?AW4DomainLockType@@XZ` at `0x1400b56d6`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x1400b5563`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x1400b5648`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x1400b56e4`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x1400b5563`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x1400b5648`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x1400b56e4`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400b55b3`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400b572c`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400b57e0`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400b589e`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400b55b3`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400b572c`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400b57e0`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400b589e`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b56ca`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5859`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b586a`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5890`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b56ca`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5859`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b586a`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5890`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400b57cf`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400b57f1`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400b5827`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400b5835`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400b57cf`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400b57f1`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400b5827`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400b5835`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b55f5`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5690`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b576e`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5817`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b55f5`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5690`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b576e`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5817`
- `win32kbase!_HMPheFromObject` at `0x1400b55c6`
- `win32kbase!_HMPheFromObject` at `0x1400b573f`
- `win32kbase!_HMPheFromObject` at `0x1400b55c6`
- `win32kbase!_HMPheFromObject` at `0x1400b573f`
- `WIN32K!W32GetUserSessionState` at `0x1400b5530`
- `WIN32K!W32GetUserSessionState` at `0x1400b5579`
- `WIN32K!W32GetUserSessionState` at `0x1400b565c`
- `WIN32K!W32GetUserSessionState` at `0x1400b56f8`
- `WIN32K!W32GetUserSessionState` at `0x1400b5530`
- `WIN32K!W32GetUserSessionState` at `0x1400b5579`
- `WIN32K!W32GetUserSessionState` at `0x1400b565c`
- `WIN32K!W32GetUserSessionState` at `0x1400b56f8`

## pseudocode

```c

```
