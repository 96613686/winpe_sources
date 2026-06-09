# DeployHkDatabaseCheckpoint(ulong,uint,bool,LSN *)

- ea: `0x101e2f390`
- end: `0x101e2fe01`
- name: `?DeployHkDatabaseCheckpoint@@YAXKI_NPEAVLSN@@@Z`
- size: `2673`
- prototype: `void __fastcall(unsigned int, unsigned int, bool, struct LSN *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x101e283c0`

## callees

- `0x100401070`
- `0x100401090`
- `0x1004022e0`
- `0x10083a060`
- `0x100a29ad0`
- `0x101e2f2a0`
- `0x101e2f390`
- `0x101e38ad0`
- `0x101e88d30`
- `0x101e88db0`

## import_xrefs

- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101e2f3df`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e2f60c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e2f68d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e2f763`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e2f885`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e2fa37`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e2fa81`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e2fb78`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e2f60c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e2f68d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e2f763`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e2f885`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e2fa37`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e2fa81`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e2fb78`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101e2fc43`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101e2fc43`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e2f41f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e2f706`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e2fca4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e2f41f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e2f706`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e2fca4`
- `sqldk!SystemThread_TlsIndex` at `0x101e2f54a`
- `sqldk!SystemThread_TlsIndex` at `0x101e2fc0b`
- `sqldk!SystemThread_TlsOffset` at `0x101e2f553`
- `sqldk!SystemThread_TlsOffset` at `0x101e2fc14`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e2f576`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e2fc2d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e2f576`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e2fc2d`
- `sqlmin!??1BootPagePtr@@QEAA@XZ` at `0x101e2fdd8`
- `sqlmin!??1BootPagePtr@@QEAA@XZ` at `0x101e2fdd8`
- `sqlmin!?GetDatabase@HkHostDbCtxt@@QEBAPEAUHkDatabase@@XZ` at `0x101e2f893`
- `sqlmin!?GetDatabase@HkHostDbCtxt@@QEBAPEAUHkDatabase@@XZ` at `0x101e2f8ad`
- `sqlmin!?GetDatabase@HkHostDbCtxt@@QEBAPEAUHkDatabase@@XZ` at `0x101e2fb8a`
- `sqlmin!?GetDatabase@HkHostDbCtxt@@QEBAPEAUHkDatabase@@XZ` at `0x101e2f893`
- `sqlmin!?GetDatabase@HkHostDbCtxt@@QEBAPEAUHkDatabase@@XZ` at `0x101e2f8ad`
- `sqlmin!?GetDatabase@HkHostDbCtxt@@QEBAPEAUHkDatabase@@XZ` at `0x101e2fb8a`
- `sqlmin!?Init@BootPagePtr@@QEAAXVContextHandle@@PEAVRecoveryUnit@@I@Z` at `0x101e2f623`
- `sqlmin!?Init@BootPagePtr@@QEAAXVContextHandle@@PEAVRecoveryUnit@@I@Z` at `0x101e2f623`
- `sqlmin!?GetAccess@BootPagePtr@@QEAAHW4LATCH_TYPE@LatchBase@@W4BLATCH_FLAGS@@@Z` at `0x101e2f638`
- `sqlmin!?GetAccess@BootPagePtr@@QEAAHW4LATCH_TYPE@LatchBase@@W4BLATCH_FLAGS@@@Z` at `0x101e2f638`
- `sqlmin!?ReleaseAccess@BootPagePtr@@QEAAXH@Z` at `0x101e2f6c5`
- `sqlmin!?ReleaseAccess@BootPagePtr@@QEAAXH@Z` at `0x101e2fd58`
- `sqlmin!?ReleaseAccess@BootPagePtr@@QEAAXH@Z` at `0x101e2f6c5`
- `sqlmin!?ReleaseAccess@BootPagePtr@@QEAAXH@Z` at `0x101e2fd58`
- `sqlmin!?Release@BootPagePtr@@QEAAXH@Z` at `0x101e2f6d5`
- `sqlmin!?Release@BootPagePtr@@QEAAXH@Z` at `0x101e2fd68`
- `sqlmin!?Release@BootPagePtr@@QEAAXH@Z` at `0x101e2f6d5`
- `sqlmin!?Release@BootPagePtr@@QEAAXH@Z` at `0x101e2fd68`
- `sqlmin!?Release@AutoDbLock@@QEAAXXZ` at `0x101e2f982`
- `sqlmin!?Release@AutoDbLock@@QEAAXXZ` at `0x101e2fa9a`
- `sqlmin!?Release@AutoDbLock@@QEAAXXZ` at `0x101e2fdc9`
- `sqlmin!?Release@AutoDbLock@@QEAAXXZ` at `0x101e2f982`
- `sqlmin!?Release@AutoDbLock@@QEAAXXZ` at `0x101e2fa9a`
- `sqlmin!?Release@AutoDbLock@@QEAAXXZ` at `0x101e2fdc9`
- `sqlmin!?Acquire@AutoDbLock@@QEAA?AW4LCK_RESULT@@KW4LCK_MODE@@K_NW4EDBRefType@@@Z` at `0x101e2f78d`
- `sqlmin!?Acquire@AutoDbLock@@QEAA?AW4LCK_RESULT@@KW4LCK_MODE@@K_NW4EDBRefType@@@Z` at `0x101e2f9cc`
- `sqlmin!?Acquire@AutoDbLock@@QEAA?AW4LCK_RESULT@@KW4LCK_MODE@@K_NW4EDBRefType@@@Z` at `0x101e2fad8`
- `sqlmin!?Acquire@AutoDbLock@@QEAA?AW4LCK_RESULT@@KW4LCK_MODE@@K_NW4EDBRefType@@@Z` at `0x101e2f78d`
- `sqlmin!?Acquire@AutoDbLock@@QEAA?AW4LCK_RESULT@@KW4LCK_MODE@@K_NW4EDBRefType@@@Z` at `0x101e2f9cc`
- `sqlmin!?Acquire@AutoDbLock@@QEAA?AW4LCK_RESULT@@KW4LCK_MODE@@K_NW4EDBRefType@@@Z` at `0x101e2fad8`
- `sqlmin!?ComputeTargetHkVersion@HkHostDbCtxt@@QEAAIG@Z` at `0x101e2fa57`
- `sqlmin!?ComputeTargetHkVersion@HkHostDbCtxt@@QEAAIG@Z` at `0x101e2fa57`
- `sqlmin!?HkHostLogHkDeployRecord@@YAXKW4HkDeployStage@@I_NPEAVLSN@@@Z` at `0x101e2f7ce`
- `sqlmin!?HkHostLogHkDeployRecord@@YAXKW4HkDeployStage@@I_NPEAVLSN@@@Z` at `0x101e2f7ce`
- `sqlmin!?HkHostIsVersionDeployOnly@@YA_NPEAVRecoveryUnit@@@Z` at `0x101e2f6de`
- `sqlmin!?HkHostIsVersionDeployOnly@@YA_NPEAVRecoveryUnit@@@Z` at `0x101e2f6de`
- `sqlmin!?IsInRecovery@RecoveryUnit@@QEBA_NXZ` at `0x101e2fb30`
- `sqlmin!?IsInRecovery@RecoveryUnit@@QEBA_NXZ` at `0x101e2fb30`
- `sqlmin!?HkHostStartController@@YAXPEAVRecoveryUnit@@@Z` at `0x101e2fb81`
- `sqlmin!?HkHostStartController@@YAXPEAVRecoveryUnit@@@Z` at `0x101e2fb81`
- `sqlmin!??0CAutoLogTrunc@@QEAA@PEAVRecoveryUnit@@_N@Z` at `0x101e2f4d3`
- `sqlmin!??0CAutoLogTrunc@@QEAA@PEAVRecoveryUnit@@_N@Z` at `0x101e2f4d3`
- `sqlmin!??1CAutoLogTrunc@@QEAA@XZ` at `0x101e2fdb0`
- `sqlmin!??1CAutoLogTrunc@@QEAA@XZ` at `0x101e2fdb0`
- `sqlmin!?DisableLogTruncation@CAutoLogTrunc@@QEAAXAEBVLSN@@W4_TruncationHoldup@@@Z` at `0x101e2f4f5`
- `sqlmin!?DisableLogTruncation@CAutoLogTrunc@@QEAAXAEBVLSN@@W4_TruncationHoldup@@@Z` at `0x101e2f4f5`
- `sqlmin!?HkHostGetDeferInitialCheckpoint@@YA_NPEAUHkRestoreParams@@@Z` at `0x101e2f71d`
- `sqlmin!?HkHostGetDeferInitialCheckpoint@@YA_NPEAUHkRestoreParams@@@Z` at `0x101e2f71d`
- `sqlmin!?HkHostRestartHkDatabase@@YAXPEAVRecoveryUnit@@_NI@Z` at `0x101e2fa07`
- `sqlmin!?HkHostRestartHkDatabase@@YAXPEAVRecoveryUnit@@_NI@Z` at `0x101e2fa07`
- `sqlmin!?HkHostCreateInitialCheckpoint@@YAXPEAVRecoveryUnit@@PEAVLSN@@@Z` at `0x101e2fb14`
- `sqlmin!?HkHostCreateInitialCheckpoint@@YAXPEAVRecoveryUnit@@PEAVLSN@@@Z` at `0x101e2fb14`
- `sqlmin!?HkHostSetDeferInitialLsn@@YAXPEAUHkRestoreParams@@PEAVLSN@@@Z` at `0x101e2fbdb`
- `sqlmin!?HkHostSetDeferInitialLsn@@YAXPEAUHkRestoreParams@@PEAVLSN@@@Z` at `0x101e2fbdb`
- `sqlmin!?GetOnDiskVersion@RecoveryUnit@@QEBAGXZ` at `0x101e2fa4b`
- `sqlmin!?GetOnDiskVersion@RecoveryUnit@@QEBAGXZ` at `0x101e2fa4b`
- `sqlmin!?IsOnline@DBTABLE@@QEBAHXZ` at `0x101e2f847`
- `sqlmin!?IsOnline@DBTABLE@@QEBAHXZ` at `0x101e2f847`
- `sqlmin!?CbLogicalDbNameInternal@DBTABLE@@QEBAKXZ` at `0x101e2f8fe`
- `sqlmin!?CbLogicalDbNameInternal@DBTABLE@@QEBAKXZ` at `0x101e2fc7c`
- `sqlmin!?CbLogicalDbNameInternal@DBTABLE@@QEBAKXZ` at `0x101e2f8fe`
- `sqlmin!?CbLogicalDbNameInternal@DBTABLE@@QEBAKXZ` at `0x101e2fc7c`
- `sqlmin!?LogicalDbNameInternal@DBTABLE@@QEBAPEB_WXZ` at `0x101e2f8ee`
- `sqlmin!?LogicalDbNameInternal@DBTABLE@@QEBAPEB_WXZ` at `0x101e2fc6c`
- `sqlmin!?LogicalDbNameInternal@DBTABLE@@QEBAPEB_WXZ` at `0x101e2f8ee`
- `sqlmin!?LogicalDbNameInternal@DBTABLE@@QEBAPEB_WXZ` at `0x101e2fc6c`
- `sqlmin!?lck_StandardHandler@@YAXW4LCK_RESULT@@W4ABORT_AND_LCK_EXCEPTIONS@@@Z` at `0x101e2f7aa`
- `sqlmin!?lck_StandardHandler@@YAXW4LCK_RESULT@@W4ABORT_AND_LCK_EXCEPTIONS@@@Z` at `0x101e2f9e9`
- `sqlmin!?lck_StandardHandler@@YAXW4LCK_RESULT@@W4ABORT_AND_LCK_EXCEPTIONS@@@Z` at `0x101e2faf5`
- `sqlmin!?lck_StandardHandler@@YAXW4LCK_RESULT@@W4ABORT_AND_LCK_EXCEPTIONS@@@Z` at `0x101e2f7aa`
- `sqlmin!?lck_StandardHandler@@YAXW4LCK_RESULT@@W4ABORT_AND_LCK_EXCEPTIONS@@@Z` at `0x101e2f9e9`
- `sqlmin!?lck_StandardHandler@@YAXW4LCK_RESULT@@W4ABORT_AND_LCK_EXCEPTIONS@@@Z` at `0x101e2faf5`
- `hkengine!HkDatabaseSetOpenForFileAllocations` at `0x101e2fb93`
- `hkengine!HkDatabaseSetOpenForFileAllocations` at `0x101e2fb93`
- `hkengine!HkDatabaseIsPendingRestartForCkptUndeploy` at `0x101e2f89c`
- `hkengine!HkDatabaseIsPendingRestartForCkptUndeploy` at `0x101e2f8b6`
- `hkengine!HkDatabaseIsPendingRestartForCkptUndeploy` at `0x101e2f89c`
- `hkengine!HkDatabaseIsPendingRestartForCkptUndeploy` at `0x101e2f8b6`

## string_xrefs

- `0x101e2f683`: `dbinfo->dbi_hkCompatibilityMode != HKMAJOR(HK_VERSION_INVALID)`
- `0x101e2fa77`: `!(!isMediaRecovery) || (hkDbCtxt->HkEngineVersion == hkDbCtxt->ComputeTargetHkVersion( pru->GetOnDiskVersion()))`

## pseudocode

```c

```
