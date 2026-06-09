# FailoverReplicationTracker::CheckForPendingLogFileSizeOnRecoveryVer3(void)

- ea: `0x140533128`
- end: `0x140533783`
- name: `?CheckForPendingLogFileSizeOnRecoveryVer3@FailoverReplicationTracker@@QEAAXXZ`
- size: `1627`
- prototype: `void __fastcall(FailoverReplicationTracker *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1402a8040`

## callees

- `0x140022640`
- `0x14005c630`
- `0x14009caa4`
- `0x14009d144`
- `0x1400fc48c`
- `0x1401879a4`
- `0x140188e18`
- `0x1402407a4`
- `0x1402a8bc8`
- `0x1404828e0`
- `0x140531778`
- `0x140533128`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1405331cb`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1405331f5`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140533271`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053329c`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140533398`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1405333c2`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140533440`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053346b`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140533518`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140533542`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1405335c5`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1405335f0`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1405331cb`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1405331f5`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140533271`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053329c`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140533398`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1405333c2`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140533440`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14053346b`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140533518`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140533542`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1405335c5`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1405335f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140533310`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1405334ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140533310`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1405334ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14053366f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14053366f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1405335a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1405335a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140533258`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14053341e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140533258`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14053341e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140533227`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1405332cb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1405333f4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14053349a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140533574`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14053361f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140533227`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1405332cb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1405333f4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14053349a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140533574`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14053361f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1405332e3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140533300`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1405334b1`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1405334d2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140533636`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140533654`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1405332e3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140533300`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1405334b1`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1405334d2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140533636`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140533654`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140533326`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140533381`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140533326`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140533381`

## pseudocode

```c

```
