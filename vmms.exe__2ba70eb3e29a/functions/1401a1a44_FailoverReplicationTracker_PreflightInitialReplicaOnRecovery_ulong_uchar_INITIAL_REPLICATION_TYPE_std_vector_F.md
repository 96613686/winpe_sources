# FailoverReplicationTracker::PreflightInitialReplicaOnRecovery(ulong,uchar *,INITIAL_REPLICATION_TYPE,std::vector<_FR_TRACKER_VHD_METADATA,std::allocator<_FR_TRACKER_VHD_METADATA>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1401a1a44`
- end: `0x1401a239c`
- name: `?PreflightInitialReplicaOnRecovery@FailoverReplicationTracker@@QEAAJKPEAEW4INITIAL_REPLICATION_TYPE@@AEBV?$vector@U_FR_TRACKER_VHD_METADATA@@V?$allocator@U_FR_TRACKER_VHD_METADATA@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z`
- size: `2392`
- prototype: `__int64 __usercall@<rax>(FailoverReplicationTracker *this@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config`

## callers

- `0x1403563c8`

## callees

- `0x14001a000`
- `0x140022640`
- `0x1400419e4`
- `0x140043dc8`
- `0x14005c630`
- `0x140071534`
- `0x140073cd0`
- `0x14007ee00`
- `0x14007ee50`
- `0x14007ee88`
- `0x14007eed8`
- `0x140090e4c`
- `0x14009b580`
- `0x14009d144`
- `0x1400d98b8`
- `0x1400e1338`
- `0x1401879a4`
- `0x140188e18`
- `0x1401a16f8`
- `0x1401a1a44`
- `0x1401b28f0`
- `0x1401eb154`
- `0x140209290`
- `0x14020c060`
- `0x14020ca1c`
- `0x1402407a4`
- `0x1402a6c54`
- `0x14033e9e8`
- `0x1404828e0`
- `0x140515f0c`
- `0x14053fa1c`
- `0x14053fb08`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1401a1d32`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1401a1d5c`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1401a1de5`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1401a1e10`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1401a1d32`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1401a1d5c`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1401a1de5`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1401a1e10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401a1f20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401a1fcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401a205d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401a20cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401a1f20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401a1fcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401a205d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401a20cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1401a1dc5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1401a1dc5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1401a1d8e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1401a1e49`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1401a1d8e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1401a1e49`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a1e6a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a1f10`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a1fbd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a204d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a20ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a1e6a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a1f10`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a1fbd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a204d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a20ae`
- `vsconfig!VsCreateConfigurationManager` at `0x1401a1b76`
- `vsconfig!VsCreateConfigurationManager` at `0x1401a1b76`

## string_xrefs

- `0x1401a211c`: `/configuration/global_settings/replication/settings`
- `0x1401a220e`: `/configuration/global_settings/replication/settings`

## pseudocode

```c

```
