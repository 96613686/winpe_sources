# FailoverReplicationTracker::GenerateTransferFilesForDiskUpdateVer3(void)

- ea: `0x140335710`
- end: `0x1403367bd`
- name: `?GenerateTransferFilesForDiskUpdateVer3@FailoverReplicationTracker@@AEAAXXZ`
- size: `4269`
- prototype: `void __fastcall(FailoverReplicationTracker *__hidden this)`
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, installer_update`

## callers

- `0x140579900`

## callees

- `0x14001a000`
- `0x140022640`
- `0x1400342a0`
- `0x14004a3d8`
- `0x14004f3c4`
- `0x14005c630`
- `0x14006a638`
- `0x140071534`
- `0x14007eed8`
- `0x14009d144`
- `0x1400b4590`
- `0x1400f47f4`
- `0x1400f724c`
- `0x140155de0`
- `0x1401586a4`
- `0x1401879a4`
- `0x140188e18`
- `0x1401a31bc`
- `0x1401ddfbc`
- `0x1401ed14c`
- `0x1402407a4`
- `0x1402a6c54`
- `0x140306698`
- `0x140335710`
- `0x140336f60`
- `0x140337060`
- `0x14033e9e8`
- `0x140361ec4`
- `0x140403808`
- `0x1404828e0`
- `0x14048614c`
- `0x140486158`
- `0x140526ad8`
- `0x140576c94`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140335879`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1403358a3`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140335943`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14033596e`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140335d2d`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140335d57`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140335dde`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140335e08`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1403360ce`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1403360f8`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14033617a`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1403361a5`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1403364fd`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140336527`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1403365a8`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1403365d2`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140335879`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1403358a3`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140335943`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14033596e`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140335d2d`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140335d57`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140335dde`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140335e08`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1403360ce`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1403360f8`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14033617a`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1403361a5`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1403364fd`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140336527`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1403365a8`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1403365d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140335bbf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140335f3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140336450`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140336650`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140335bbf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140335f3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140336450`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140336650`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140335926`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140335db9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14033615a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140336591`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140335926`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140335db9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14033615a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140336591`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1403358d5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1403359ad`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140335d89`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140335e43`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14033612a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1403361de`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140336559`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1403365fe`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1403358d5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1403359ad`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140335d89`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140335e43`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14033612a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1403361de`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140336559`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1403365fe`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1403359d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140335b2a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140335e69`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140335f1e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140336202`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140336432`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140336615`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140336640`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1403359d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140335b2a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140335e69`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140335f1e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140336202`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140336432`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140336615`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140336640`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1403364cd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1403364cd`

## pseudocode

```c

```
