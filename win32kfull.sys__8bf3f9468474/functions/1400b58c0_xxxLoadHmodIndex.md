# xxxLoadHmodIndex

- ea: `0x1400b58c0`
- end: `0x1400b5f0d`
- name: `xxxLoadHmodIndex`
- size: `1613`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14000b5bc`
- `0x1400b5520`
- `0x1400c459c`

## callees

- `0x1400b58c0`
- `0x1400b63d0`
- `0x1400b68e0`
- `0x1400b7330`
- `0x1400b7790`
- `0x1400b77dc`
- `0x1400c2a10`
- `0x140120fd0`
- `0x140121a20`
- `0x1401be2f4`
- `0x1401e9520`
- `0x1401f3048`
- `0x140341ff0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1400b5e12`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400b5e12`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400b59dd`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400b59dd`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b5b27`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b5b5e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b5d92`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b5df5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b5eab`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b5b27`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b5b5e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b5d92`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b5df5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b5eab`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400b58ff`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400b59af`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400b59c6`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400b58ff`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400b59af`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400b59c6`
- `win32kbase!UserGetAtomNameFromAtomTable` at `0x1400b5b12`
- `win32kbase!UserGetAtomNameFromAtomTable` at `0x1400b5ddb`
- `win32kbase!UserGetAtomNameFromAtomTable` at `0x1400b5b12`
- `win32kbase!UserGetAtomNameFromAtomTable` at `0x1400b5ddb`
- `win32kbase!?getDLT@DLT_CLIENTLIB@@SA?AW4DomainLockType@@XZ` at `0x1400b5917`
- `win32kbase!?getDLT@DLT_CLIENTLIB@@SA?AW4DomainLockType@@XZ` at `0x1400b5c3d`
- `win32kbase!?getDLT@DLT_CLIENTLIB@@SA?AW4DomainLockType@@XZ` at `0x1400b5917`
- `win32kbase!?getDLT@DLT_CLIENTLIB@@SA?AW4DomainLockType@@XZ` at `0x1400b5c3d`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x1400b5925`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x1400b5c4b`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x1400b5925`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x1400b5c4b`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400b5e82`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400b5e93`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400b5ed5`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400b5e82`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400b5e93`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1400b5ed5`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5976`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5c9c`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5e56`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5976`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5c9c`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5e56`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400b5a61`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400b5c2c`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400b5d59`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400b5a61`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400b5c2c`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400b5d59`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5a2b`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5b89`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5d7d`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5a2b`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5b89`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400b5d7d`
- `WIN32K!W32GetUserSessionState` at `0x1400b593b`
- `WIN32K!W32GetUserSessionState` at `0x1400b5987`
- `WIN32K!W32GetUserSessionState` at `0x1400b599a`
- `WIN32K!W32GetUserSessionState` at `0x1400b5a77`
- `WIN32K!W32GetUserSessionState` at `0x1400b5a9f`
- `WIN32K!W32GetUserSessionState` at `0x1400b5ade`
- `WIN32K!W32GetUserSessionState` at `0x1400b5af2`
- `WIN32K!W32GetUserSessionState` at `0x1400b5b33`
- `WIN32K!W32GetUserSessionState` at `0x1400b5bed`
- `WIN32K!W32GetUserSessionState` at `0x1400b5c61`
- `WIN32K!W32GetUserSessionState` at `0x1400b5cbe`
- `WIN32K!W32GetUserSessionState` at `0x1400b5cf3`
- `WIN32K!W32GetUserSessionState` at `0x1400b5d07`
- `WIN32K!W32GetUserSessionState` at `0x1400b5da3`
- `WIN32K!W32GetUserSessionState` at `0x1400b5db8`
- `WIN32K!W32GetUserSessionState` at `0x1400b593b`
- `WIN32K!W32GetUserSessionState` at `0x1400b5987`
- `WIN32K!W32GetUserSessionState` at `0x1400b599a`
- `WIN32K!W32GetUserSessionState` at `0x1400b5a77`
- `WIN32K!W32GetUserSessionState` at `0x1400b5a9f`
- `WIN32K!W32GetUserSessionState` at `0x1400b5ade`
- `WIN32K!W32GetUserSessionState` at `0x1400b5af2`
- `WIN32K!W32GetUserSessionState` at `0x1400b5b33`
- `WIN32K!W32GetUserSessionState` at `0x1400b5bed`
- `WIN32K!W32GetUserSessionState` at `0x1400b5c61`
- `WIN32K!W32GetUserSessionState` at `0x1400b5cbe`
- `WIN32K!W32GetUserSessionState` at `0x1400b5cf3`
- `WIN32K!W32GetUserSessionState` at `0x1400b5d07`
- `WIN32K!W32GetUserSessionState` at `0x1400b5da3`
- `WIN32K!W32GetUserSessionState` at `0x1400b5db8`

## pseudocode

```c

```
