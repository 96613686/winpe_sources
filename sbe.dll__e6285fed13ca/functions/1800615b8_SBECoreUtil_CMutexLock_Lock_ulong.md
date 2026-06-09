# SBECoreUtil::CMutexLock::Lock(ulong)

- ea: `0x1800615b8`
- end: `0x180061622`
- name: `?Lock@CMutexLock@SBECoreUtil@@QEAAKK@Z`
- size: `106`
- prototype: `unsigned int __fastcall(SBECoreUtil::CMutexLock *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800aef58`
- `0x1800af400`
- `0x1800b08e0`
- `0x1800b0900`

## callees

- `0x1800615b8`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800615e1`
- `KERNEL32!WaitForSingleObject` at `0x1800615e1`
- `KERNEL32!GetCurrentThreadId` at `0x180061604`
- `KERNEL32!GetCurrentThreadId` at `0x180061604`
- `KERNEL32!LeaveCriticalSection` at `0x1800615f4`
- `KERNEL32!LeaveCriticalSection` at `0x1800615f4`
- `KERNEL32!EnterCriticalSection` at `0x1800615ce`
- `KERNEL32!EnterCriticalSection` at `0x1800615ce`

## pseudocode

```c

```
