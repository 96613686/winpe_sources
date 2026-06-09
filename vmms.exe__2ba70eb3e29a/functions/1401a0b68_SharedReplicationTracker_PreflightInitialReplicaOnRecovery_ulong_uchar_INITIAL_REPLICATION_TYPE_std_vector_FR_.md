# SharedReplicationTracker::PreflightInitialReplicaOnRecovery(ulong,uchar *,INITIAL_REPLICATION_TYPE,std::vector<_FR_TRACKER_VHD_METADATA,std::allocator<_FR_TRACKER_VHD_METADATA>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1401a0b68`
- end: `0x1401a16f1`
- name: `?PreflightInitialReplicaOnRecovery@SharedReplicationTracker@@QEAAJKPEAEW4INITIAL_REPLICATION_TYPE@@AEBV?$vector@U_FR_TRACKER_VHD_METADATA@@V?$allocator@U_FR_TRACKER_VHD_METADATA@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z`
- size: `2953`
- prototype: `__int64 __usercall@<rax>(FailoverReplicationTracker *this@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `39`
- tags: `registry_config`

## callers

- `0x1403563c8`

## callees

- `0x14001a000`
- `0x14001a024`
- `0x140022640`
- `0x1400419e4`
- `0x140043dc8`
- `0x14005c630`
- `0x140064a48`
- `0x140071534`
- `0x140073cd0`
- `0x14007bb80`
- `0x14007eed8`
- `0x14009b580`
- `0x14009d144`
- `0x1400b2bdc`
- `0x1400d98b8`
- `0x1400df0d8`
- `0x14011880c`
- `0x14011f288`
- `0x1401879a4`
- `0x140188e18`
- `0x14019f188`
- `0x1401a0b68`
- `0x1401a16f8`
- `0x1401b28f0`
- `0x1401cc838`
- `0x1401e8318`
- `0x14020c060`
- `0x1402407a4`
- `0x14024d020`
- `0x1402a6c54`
- `0x14031dd84`
- `0x14033bbe4`
- `0x14033e9e8`
- `0x140357f54`
- `0x1404828e0`
- `0x140515f0c`
- `0x14053fa1c`
- `0x14053fb08`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1401a0eb2`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1401a0edc`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1401a0f65`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1401a0f90`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1401a0eb2`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1401a0edc`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1401a0f65`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1401a0f90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401a10a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401a114e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401a11d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401a1255`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401a10a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401a114e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401a11d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401a1255`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1401a0f45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1401a0f45`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1401a0f0e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1401a0fcf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1401a0f0e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1401a0fcf`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a0ff2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a1093`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a113e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a11c3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a1237`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a0ff2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a1093`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a113e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a11c3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1401a1237`
- `vsconfig!VsCreateConfigurationManager` at `0x1401a0cba`
- `vsconfig!VsCreateConfigurationManager` at `0x1401a0cba`

## pseudocode

```c

```
