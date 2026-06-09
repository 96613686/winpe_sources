# RecoveryUnit::Dump(CDStream *)

- ea: `0x101ce6da0`
- end: `0x101ce96b1`
- name: `?Dump@RecoveryUnit@@QEAAHPEAVCDStream@@@Z`
- size: `10513`
- prototype: `int(RecoveryUnit *__hidden this, struct CDStream *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x101726350`

## callees

- `0x100401490`
- `0x10061fb80`
- `0x10120fe00`
- `0x1017d4380`
- `0x101823e20`
- `0x101c0ca00`
- `0x101c200d0`
- `0x101c367f0`
- `0x101c78a70`
- `0x101cb0850`
- `0x101ce6da0`
- `0x101d9b5e0`
- `0x102392160`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x101ce8ed2`
- `KERNEL32!GetTickCount64` at `0x101ce8ed2`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101ce7b17`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101ce7b23`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x101ce6e71`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x101ce6e71`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x101ce9631`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x101ce9666`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x101ce9631`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x101ce9666`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x101ce6de9`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x101ce6de9`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce6e28`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce6ec2`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce6f09`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce6f4c`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce6f6a`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce6f93`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce6fbd`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7131`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7157`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce71d9`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7342`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce73b7`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce73f7`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce741d`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7443`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce746e`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce749d`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce74cc`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce74fb`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7526`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7554`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce757b`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce75a2`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce75c9`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce75f0`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7617`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce763e`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7665`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce768c`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce76b3`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce76de`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce770c`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce773b`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7762`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7789`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce77b0`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce77d7`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce77fe`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7825`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce784c`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7873`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7899`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce78c0`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce78e7`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7921`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7948`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce796f`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7996`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce79bd`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce79e4`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7a0b`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7a32`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7a59`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7a88`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7aaf`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7ad6`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7afc`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7b63`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7bbd`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7d1d`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7d50`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7d76`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7d9c`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7dc2`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7de8`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7e0e`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7e34`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7eb6`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7f38`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7fba`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce7fe1`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8007`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce803b`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8062`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8089`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce80b0`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce80d3`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce80f6`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8119`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce813c`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce815f`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8182`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce81a5`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce81c8`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce81eb`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8211`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8237`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce825d`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8283`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce82a9`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce82cf`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce82f5`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce831b`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8341`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8367`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce838d`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce83b3`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce83d9`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce83ff`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8425`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce844b`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8471`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8497`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce84bd`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce84e3`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8509`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce852f`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8555`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce857b`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce85a1`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce85c7`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce85ed`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8613`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8639`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce865f`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8685`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce86ab`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce86d1`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce86f7`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce871d`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8743`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8769`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce878f`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce87b5`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce87db`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8801`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8827`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce884d`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8873`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8899`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce88bf`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce88e5`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce890b`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8931`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8957`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce897d`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce89a3`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce89c9`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce89ef`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8a15`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8a3b`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8a61`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8a87`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8aad`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8ad3`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8af9`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8b1f`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8b45`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8b6b`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8ba2`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8bc8`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8bee`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8c14`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8c3a`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8c60`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8c86`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8d08`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8d7d`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8e02`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8e25`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8e45`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8e68`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8f22`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8f44`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8f66`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8f89`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce8fe2`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce900f`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce903d`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce906b`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce9099`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce90c7`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce90f5`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce9123`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce9154`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce9185`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce91a8`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce91cb`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce923d`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce92ab`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce92dc`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce92ff`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce9322`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce9394`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce93b7`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce6e28`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce6ec2`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101ce6f09`

## string_xrefs

- `0x101ce78b6`: `m_ordLockPopLogicComplete`
- `0x101ce7731`: `m_concurrentSGAMUpdatesEnabled`
- `0x101ce7d92`: `m_StartupThread`
- `0x101ce7db8`: `m_RollbackThread`
- `0x101ce7aa5`: `m_AsyncRecoveryThreadStarted`
- `0x101ce7acc`: `m_DeferredXactResolveTaskReadyToRun`
- `0x101ce714d`: `m_CommitLsnTickCount`
- `0x101ce7338`: `m_LastCommitLsn`
- `0x101ce73ad`: `m_LastCommitLsnTime`
- `0x101ce7464`: `m_IsReadOnly`
- `0x101ce6e1e`: `m_IsAlreadyDumping`
- `0x101ce7127`: `m_CommitLsn`
- `0x101ce7634`: `m_NeedDirtyPageWriteHelp`
- `0x101ce765b`: `m_LimitDirtyPageWriteHelp`
- `0x101ce76d4`: `m_concurrentPFSUpdatesEnabled`
- `0x101ce7702`: `m_concurrentGAMUpdatesEnabled`
- `0x101ce751c`: `m_HasLogStartupBeenAttemptedForBackupRestore`
- `0x101ce85bd`: `DeletesInDdlTransaction`
- `0x101ce85e3`: `StaleVersionSpaceCleanupAttempts`
- `0x101ce84b3`: `VersionStoreOffRowForDelete`
- `0x101ce87f7`: `UpdatesOnAbortedRowsCount`
- `0x101ce881d`: `TxRollbackCount`
- `0x101ce8713`: `NestIdReadFromOffRowPVS`
- `0x101ce80a6`: `m_acquireTidLocksDuringRecovery`
- `0x101ce80c9`: `TxCommitCount`
- `0x101ce80ec`: `ShortTxRollbackCount`
- `0x101ce810f`: `LongTxRollbackCount`
- `0x101ce8132`: `CTRTxRollbackCount`
- `0x101ce8155`: `TempDbVersionStoreInserts`
- `0x101ce7dde`: `m_RedoThread`
- `0x101ce7e04`: `m_AsyncRecoveryThread`
- `0x101ce7eac`: `m_lastLazyCommitLSN`
- `0x101ce7f2e`: `m_forceCommitLSN`
- `0x101ce8031`: `m_snapshotMaxXdesIdAfterCrash`
- `0x101ce8337`: `InRowVersionSkippedInPlaceUpdateCtxt`
- `0x101ce835d`: `VersionStoreReads`
- `0x101ce8383`: `VersionStoreDeepReads`
- `0x101ce8178`: `TempDbVersionStoreSmallRowInserts`
- `0x101ce8279`: `InRowVersionSkippedCompressedPages`
- `0x101ce8e5e`: `Unexpected VersionedRecordReadCount CPU count`
- `0x101ce91c1`: `r.m_RedoThread`
- `0x101ce89bf`: `OffRowVersionPageSkippedOldestActiveXdesid`
- `0x101ce89e5`: `OffRowVersionPageSkippedOldestAbortedXdesid`
- `0x101ce8c30`: `MTVCv2 Total pages marked no versions by worker threads`
- `0x101ce8c56`: `MTVCv2 Total Pages dirtied by worker threads`
- `0x101ce8c7c`: `MTVCv2 Total Pages Read ahead by worker threads`
- `0x101ce8d73`: `m_LastUserCommitTime`
- `0x101ce8df8`: `InPageRecordReadCount`
- `0x101ce8e1b`: `VersionedRecordReadCount`
- `0x101ce8e3b`: `Unexpected InPageRecordReadCount CPU count`
- `0x101ce8b61`: `MTVCv2 Total Rows cleaned by worker threads`
- `0x101ce8b98`: `MTVCv2 worker threads MinInterestingTs`
- `0x101ce8bbe`: `MTVCv2 Total NonDataPages swept by worker threads`
- `0x101ce8be4`: `MTVCv2 Total Pages with version bit swept by worker threads`
- `0x101ce8c0a`: `MTVCv2 Total pages swept by worker threads`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RecoveryUnit::Dump(RecoveryUnit *this, struct CDStream *a2)
{
  unsigned __int8 *v4; // rdi
  char v5; // bl
  __int64 v6; // r13
  __int64 v7; // r12
  bool v8; // zf
  bool v9; // zf
  __int64 v10; // rax
  const wchar_t *v11; // r15
  const wchar_t *v12; // r9
  __int64 v13; // rax
  const wchar_t *v14; // r9
  __int64 v15; // rax
  const wchar_t *v16; // r9
  int v17; // ecx
  unsigned int v18; // eax
  int v19; // ebx
  int v20; // eax
  unsigned int v21; // ecx
  int v22; // eax
  unsigned int v23; // ecx
  int v24; // ecx
  unsigned int v25; // eax
  int v26; // edx
  int v27; // eax
  unsigned int v28; // ecx
  int v29; // eax
  unsigned int v30; // ecx
  int v31; // ecx
  unsigned int v32; // eax
  int v33; // ebx
  int v34; // eax
  unsigned int v35; // ecx
  int v36; // eax
  unsigned int v37; // ecx
  int v38; // ecx
  unsigned int v39; // eax
  int v40; // edx
  int v41; // eax
  unsigned int v42; // ecx
  int v43; // eax
  unsigned int v44; // ecx
  int v45; // eax
  int v46; // ecx
  __int64 v47; // rax
  __int64 v48; // rax
  int v49; // r9d
  unsigned __int64 v50; // rdx
  int v51; // ecx
  unsigned int v52; // eax
  unsigned __int64 v53; // rbx
  int v54; // eax
  unsigned int v55; // ecx
  int v56; // eax
  unsigned int v57; // ecx
  int v58; // eax
  unsigned int v59; // ecx
  int v60; // eax
  unsigned int v61; // ecx
  int v62; // eax
  unsigned int v63; // ecx
  int v64; // eax
  unsigned int v65; // ecx
  int v66; // eax
  int v67; // ecx
  unsigned int v68; // r9d
  __int64 v69; // rdx
  __int64 v70; // rbx
  __int64 v71; // rdi
  __m128i *v72; // r8
  signed __int64 v73; // xmm0_8
  signed __int64 v74; // rbx
  unsigned __int128 v75; // rt0
  int v76; // r15d
  int v77; // r12d
  ULONGLONG TickCount64; // rax
  unsigned __int64 v79; // r8
  int v80; // ebx
  const wchar_t *v81; // r9
  unsigned int i; // r12d
  unsigned __int64 v83; // rax
  char *v84; // r15
  const wchar_t *v85; // r9
  const wchar_t *v86; // r9
  const wchar_t *v87; // r9
  const wchar_t *v88; // r9
  const wchar_t *v89; // r9
  const wchar_t *v90; // r9
  const wchar_t *v91; // r9
  int v92; // eax
  int v93; // ecx
  FileMgr *v94; // rcx
  __int64 v95; // rcx
  __int64 v96; // rbx
  int v97; // edx
  int v98; // eax
  __int64 v99; // r8
  __int64 v100; // rcx
  __int64 v101; // rax
  RecoveryMgr *v102; // rcx
  DirtyPageMgr *v103; // rcx
  __int64 v104; // rcx
  TenantLogTracker *v105; // rcx
  __int64 v106; // rcx
  __int64 v107; // rcx
  __int64 v108; // rcx
  __int64 v109; // rcx
  LogBlockActivityTracer *v111; // rcx
  signed __int32 v112[8]; // [rsp+0h] [rbp-100h] BYREF
  __int64 v113; // [rsp+20h] [rbp-E0h]
  __int64 v114; // [rsp+28h] [rbp-D8h]
  char *v115; // [rsp+50h] [rbp-B0h]
  char v116; // [rsp+58h] [rbp-A8h]
  __int64 v117; // [rsp+60h] [rbp-A0h]
  __int64 v118; // [rsp+70h] [rbp-90h]
  __int64 v119; // [rsp+80h] [rbp-80h]
  __int64 v120; // [rsp+90h] [rbp-70h]
  __int64 v121; // [rsp+A0h] [rbp-60h]
  int v122; // [rsp+A8h] [rbp-58h]
  __int64 v123; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v124; // [rsp+C0h] [rbp-40h]
  int v125; // [rsp+D8h] [rbp-28h]
  __int64 v126; // [rsp+E0h] [rbp-20h]
  __m128i v127; // [rsp+F0h] [rbp-10h]
  __int64 v128; // [rsp+100h] [rbp+0h]
  __m128i v129; // [rsp+110h] [rbp+10h]
  _BYTE v130[528]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v131[144]; // [rsp+3B0h] [rbp+2B0h] BYREF

  v128 = -2;
  CAutoStreamHeader::CAutoStreamHeader((CAutoStreamHeader *)v130);
  v4 = (unsigned __int8 *)this + 8301;
  v115 = (char *)this + 8301;
  v5 = *((_BYTE *)this + 8301);
  v116 = v5;
  v6 = 0;
  v7 = 0;
  v124 = 0;
  if ( !*((_BYTE *)this + 8301) )
  {
    *((_BYTE *)this + 8301) = 1;
    if ( !CAutoStreamHeader::Init(
            (CAutoStreamHeader *)v130,
            a2,
            "RecoveryUnit %d:%d, @0x%p",
            (unsigned __int16)*((_DWORD *)this + 430),
            HIWORD(*((_DWORD *)this + 430)),
            this) )
    {
      v8 = v5 == 0;
      goto LABEL_329;
    }
    v10 = *((int *)this + 412);
    v11 = L"UNKNOWN";
    if ( (int)v10 >= 9 )
    {
      v12 = L"UNKNOWN";
    }
    else
    {
      _mm_lfence();
      v12 = (const wchar_t *)(&StartupStateNames)[v10];
      v5 = v116;
    }
    if ( CDStream::Write(a2, "m_StartupPhase", "%ls", v12) )
    {
      v13 = *((int *)this + 414);
      if ( (int)v13 >= 7 )
      {
        v14 = L"UNKNOWN";
      }
      else
      {
        _mm_lfence();
        v14 = (const wchar_t *)(&AvailabilityStateNames)[v13];
        v5 = v116;
      }
      if ( CDStream::Write(a2, "m_CurrentState", "%ls", v14) )
      {
        v15 = *((int *)this + 413);
        if ( (int)v15 >= 7 )
        {
          v16 = L"UNKNOWN";
        }
        else
        {
          _mm_lfence();
          v16 = (const wchar_t *)(&AvailabilityStateNames)[v15];
          v5 = v116;
        }
        CDStream::Write(a2, "m_TargetState", "%ls", v16);
      }
    }
    if ( !CDStream::Write(a2, "m_DbFragId", "%d", *((_DWORD *)this + 409)) )
    {
      v8 = v5 == 0;
      goto LABEL_329;
    }
    if ( !CDStream::Write(a2, "m_AllocUnitIdNext", "%I64d", *((_QWORD *)this + 205)) )
    {
      v8 = v5 == 0;
      goto LABEL_329;
    }
    if ( !CDStream::Write(a2, "m_OnDiskVersion", "%d", *((unsigned __int16 *)this + 831)) )
    {
      v8 = v5 == 0;
      goto LABEL_329;
    }
    v17 = *((_DWORD *)this + 517);
    do
    {
      v18 = v17 & 0xFFFFFFFE;
      v121 = *((_QWORD *)this + 257);
      v19 = *((unsigned __int16 *)this + 1032);
      _InterlockedOr(v112, 0);
      v17 = *((_DWORD *)this + 517);
    }
    while ( v18 != v17 );
    v20 = *((_DWORD *)this + 517);
    do
    {
      v21 = v20 & 0xFFFFFFFE;
      v117 = *((_QWORD *)this + 257);
      _InterlockedOr(v112, 0);
      v20 = *((_DWORD *)this + 517);
    }
    while ( v21 != v20 );
    v22 = *((_DWORD *)this + 517);
    do
    {
      v23 = v22 & 0xFFFFFFFE;
      v119 = *((_QWORD *)this + 257);
      _InterlockedOr(v112, 0);
      v22 = *((_DWORD *)this + 517);
    }
    while ( v23 != v22 );
    v24 = *((_DWORD *)this + 517);
    do
    {
      v25 = v24 & 0xFFFFFFFE;
      v121 = *((_QWORD *)this + 257);
      v26 = *((unsigned __int16 *)this + 1032);
      _InterlockedOr(v112, 0);
      v24 = *((_DWORD *)this + 517);
    }
    while ( v25 != v24 );
    v27 = *((_DWORD *)this + 517);
    do
    {
      v28 = v27 & 0xFFFFFFFE;
      v118 = *((_QWORD *)this + 257);
      _InterlockedOr(v112, 0);
      v27 = *((_DWORD *)this + 517);
    }
    while ( v28 != v27 );
    v29 = *((_DWORD *)this + 517);
    do
    {
      v30 = v29 & 0xFFFFFFFE;
      v120 = *((_QWORD *)this + 257);
      _InterlockedOr(v112, 0);
      v29 = *((_DWORD *)this + 517);
    }
    while ( v30 != v29 );
    if ( !CDStream::Write(
            a2,
            "m_CommitLsn",
            "%d:%d:%d (0x%08lx:%08lx:%04lx)",
            v120,
            HIDWORD(v118),
            v26,
            v119,
            HIDWORD(v117),
            v19) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "m_CommitLsnTickCount", "%I64d", *((_QWORD *)this + 259)) )
      goto LABEL_328;
    v120 = *((_QWORD *)this + 1153);
    v118 = v120;
    v121 = v120;
    v119 = v120;
    v117 = v120;
    if ( !CDStream::Write(
            a2,
            "m_seReplHoldLSN",
            "%d:%d:%d (0x%08lx:%08lx:%04lx)",
            v120,
            HIDWORD(v120),
            *((unsigned __int16 *)this + 4616),
            v120,
            HIDWORD(v120),
            *((unsigned __int16 *)this + 4616)) )
      goto LABEL_328;
    v31 = *((_DWORD *)this + 523);
    do
    {
      v32 = v31 & 0xFFFFFFFE;
      v121 = *((_QWORD *)this + 260);
      v33 = *((unsigned __int16 *)this + 1044);
      _InterlockedOr(v112, 0);
      v31 = *((_DWORD *)this + 523);
    }
    while ( v32 != v31 );
    v34 = *((_DWORD *)this + 523);
    do
    {
      v35 = v34 & 0xFFFFFFFE;
      v120 = *((_QWORD *)this + 260);
      _InterlockedOr(v112, 0);
      v34 = *((_DWORD *)this + 523);
    }
    while ( v35 != v34 );
    v36 = *((_DWORD *)this + 523);
    do
    {
      v37 = v36 & 0xFFFFFFFE;
      v118 = *((_QWORD *)this + 260);
      _InterlockedOr(v112, 0);
      v36 = *((_DWORD *)this + 523);
    }
    while ( v37 != v36 );
    v38 = *((_DWORD *)this + 523);
    do
    {
      v39 = v38 & 0xFFFFFFFE;
      v121 = *((_QWORD *)this + 260);
      v40 = *((unsigned __int16 *)this + 1044);
      _InterlockedOr(v112, 0);
      v38 = *((_DWORD *)this + 523);
    }
    while ( v39 != v38 );
    v41 = *((_DWORD *)this + 523);
    do
    {
      v42 = v41 & 0xFFFFFFFE;
      v119 = *((_QWORD *)this + 260);
      _InterlockedOr(v112, 0);
      v41 = *((_DWORD *)this + 523);
    }
    while ( v42 != v41 );
    v43 = *((_DWORD *)this + 523);
    do
    {
      v44 = v43 & 0xFFFFFFFE;
      v117 = *((_QWORD *)this + 260);
      _InterlockedOr(v112, 0);
      v43 = *((_DWORD *)this + 523);
    }
    while ( v44 != v43 );
    if ( !CDStream::Write(
            a2,
            "m_LastCommitLsn",
            "%d:%d:%d (0x%08lx:%08lx:%04lx)",
            v117,
            HIDWORD(v119),
            v40,
            v118,
            HIDWORD(v120),
            v33) )
      goto LABEL_328;
    LODWORD(v114) = 2;
    v113 = 0;
    v45 = ConvertDateToStrSafe((char *)this + 2096, v131, 128);
    if ( v45 > 0 )
    {
      v46 = 128;
      if ( v45 < 128 )
        v46 = v45;
      if ( (unsigned __int64)v46 >= 0x81 )
        goto LABEL_340;
      v131[v46] = 0;
      if ( !CDStream::Write(a2, "m_LastCommitLsnTime", "%hs", v131) )
        goto LABEL_328;
    }
    v47 = *((int *)this + 541);
    if ( (int)v47 < 3 )
    {
      _mm_lfence();
      v11 = (const wchar_t *)(&RecoveryModeNames)[v47];
    }
    if ( !CDStream::Write(a2, "m_RecoveryMode", "%ls", v11)
      || !CDStream::Write(a2, "m_LogHoldup", "%d", *((_DWORD *)this + 1630))
      || !CDStream::Write(a2, "m_CkptState.cps_pagesOutstanding", "%d", *((_DWORD *)this + 1649))
      || !CDStream::Write(a2, "m_IsReadOnly", "%d", *((_BYTE *)this + 7376) & 1)
      || !CDStream::Write(a2, "m_IsShuttingDown", "%d", (*((unsigned __int8 *)this + 7376) >> 2) & 1)
      || !CDStream::Write(a2, "m_NoLockReacquire", "%d", (*((unsigned __int8 *)this + 7376) >> 3) & 1)
      || !CDStream::Write(a2, "m_UsePrimaryLogForDBINFO", "%d", (*((unsigned __int8 *)this + 7376) >> 4) & 1)
      || !CDStream::Write(a2, "m_HasLogStartupBeenAttemptedForBackupRestore", "%d", *((_BYTE *)this + 7377) & 1)
      || !CDStream::Write(a2, "m_IsLogStateUsableByBackupRestore", "%d", (*((unsigned __int8 *)this + 7377) >> 1) & 1)
      || !CDStream::Write(a2, "m_MayHaveDeferred", "%d", *((unsigned __int8 *)this + 7378))
      || !CDStream::Write(a2, "m_DoRampup", "%d", *((unsigned __int8 *)this + 7379))
      || !CDStream::Write(a2, "m_IsCkptReqPending", "%d", *((unsigned __int8 *)this + 7380))
      || !CDStream::Write(a2, "m_IsOutOfSpace", "%d", *((unsigned __int8 *)this + 7381))
      || !CDStream::Write(a2, "m_IsDBBeingDropped", "%d", *((unsigned __int8 *)this + 7382))
      || !CDStream::Write(a2, "m_NeedDirtyPageWriteHelp", "%d", *((unsigned __int8 *)this + 7383))
      || !CDStream::Write(a2, "m_LimitDirtyPageWriteHelp", "%d", *((unsigned __int8 *)this + 7384))
      || !CDStream::Write(a2, "m_pvsEnabled", "%d", *((unsigned __int8 *)this + 7385))
      || !CDStream::Write(a2, "m_oldPVSVersionsCleaned", "%d", *((unsigned __int8 *)this + 7386))
      || !CDStream::Write(a2, "m_concurrentPFSUpdatesEnabled", "%d", *((_BYTE *)this + 7387) & 1)
      || !CDStream::Write(a2, "m_concurrentGAMUpdatesEnabled", "%d", (*((unsigned __int8 *)this + 7387) >> 1) & 1)
      || !CDStream::Write(a2, "m_concurrentSGAMUpdatesEnabled", "%d", (*((unsigned __int8 *)this + 7387) >> 2) & 1)
      || !CDStream::Write(a2, "m_IsCTREnabled", "%d", *((unsigned __int8 *)this + 7388))
      || !CDStream::Write(a2, "m_IsLogicalRevertNeeded", "%d", *((unsigned __int8 *)this + 7390))
      || !CDStream::Write(a2, "m_isCtrCleanupUnderUserTransactionEnabled", "%d", *((unsigned __int8 *)this + 7404))
      || !CDStream::Write(a2, "m_isTIDLockingEnabled", "%d", *((unsigned __int8 *)this + 7391))
      || !CDStream::Write(a2, "m_enableLockAfterQual", "%d", *((unsigned __int8 *)this + 7392))
      || !CDStream::Write(a2, "m_isDataOnlyLockingEnabled", "%d", *((unsigned __int8 *)this + 7393))
      || !CDStream::Write(a2, "m_olForceDisabled", "%d", *((unsigned __int8 *)this + 7394))
      || !CDStream::Write(a2, "m_areLockOrdinalsPopulatedStartup", "%d", *((unsigned __int8 *)this + 7395))
      || !CDStream::Write(a2, "m_countOfSwitchPartitionDDLs", "%d", *((_DWORD *)this + 1850))
      || !CDStream::Write(a2, "m_ordLockPopLogicComplete", "%d", *((unsigned __int8 *)this + 7396))
      || !CDStream::Write(a2, "m_RbIoFirstRecovery", "%d", *((unsigned __int8 *)this + 8672)) )
    {
      goto LABEL_328;
    }
    v48 = *((_QWORD *)this + 930);
    if ( !v48 || (v49 = 1, !*(_DWORD *)(v48 + 8)) )
      v49 = 0;
    if ( !CDStream::Write(a2, "IsRbIoForwarderMode", "%d", v49)
      || !CDStream::Write(a2, "UseDoOnlyLogicalRevert", "%d", *((unsigned __int8 *)this + 27400))
      || !CDStream::Write(a2, "RedoOnlyGhostCleanupEnabled", "%d", *((unsigned __int8 *)this + 27401))
      || !CDStream::Write(a2, "m_TransitionToLogging", "%d", *((unsigned __int8 *)this + 8298))
      || !CDStream::Write(a2, "m_IsWPR2OnBoxEnabled", "%d", *((unsigned __int8 *)this + 7405))
      || !CDStream::Write(a2, "m_IsInMemorydb", "%d", *((unsigned __int8 *)this + 7406))
      || !CDStream::Write(a2, "m_IsAcceptLogMode", "%d", *((unsigned __int8 *)this + 8272))
      || !CDStream::Write(a2, "m_IsLogAcceptSource", "%d", *((unsigned __int8 *)this + 8296))
      || !CDStream::Write(a2, "m_HasForeignFiles", "%d", *((unsigned __int8 *)this + 8273))
      || !CDStream::Write(a2, "m_IsLogReplica", "%d", (*((unsigned __int8 *)this + 7376) >> 5) & 1)
      || !CDStream::Write(a2, "m_AsyncRecoveryThreadStarted", "%d", *((unsigned __int8 *)this + 8274))
      || !CDStream::Write(a2, "m_DeferredXactResolveTaskReadyToRun", "%d", *((unsigned __int8 *)this + 8275))
      || !CDStream::Write(a2, "m_RedoBytes", "0x%I64x", *((_QWORD *)this + 1052)) )
    {
      goto LABEL_328;
    }
    v50 = *((_QWORD *)this + 1053);
    if ( v50 != -1 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
        v50 = 1000 * v50 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
      else
        v50 /= 0x2710u;
    }
    if ( !CDStream::Write(a2, "m_RedoTicks", "0x%I64x", v50) )
      goto LABEL_328;
    v51 = *((_DWORD *)this + 2110);
    do
    {
      v52 = v51 & 0xFFFFFFFE;
      v53 = *((_QWORD *)this + 1054);
      _InterlockedOr(v112, 0);
      v51 = *((_DWORD *)this + 2110);
    }
    while ( v52 != v51 );
    if ( !CDStream::Write(a2, "m_RedoThruBlock", "0x%I64x", HIDWORD(v53) | ((unsigned __int64)(unsigned int)v53 << 32)) )
      goto LABEL_328;
    v54 = *((_DWORD *)this + 2114);
    do
    {
      v55 = v54 & 0xFFFFFFFE;
      v125 = *((_DWORD *)this + 2113);
      _InterlockedOr(v112, 0);
      v54 = *((_DWORD *)this + 2114);
    }
    while ( v55 != v54 );
    v56 = *((_DWORD *)this + 2114);
    do
    {
      v57 = v56 & 0xFFFFFFFE;
      v126 = *(_QWORD *)((char *)this + 8444);
      _InterlockedOr(v112, 0);
      v56 = *((_DWORD *)this + 2114);
    }
    while ( v57 != v56 );
    v58 = *((_DWORD *)this + 2114);
    do
    {
      v59 = v58 & 0xFFFFFFFE;
      v120 = *(_QWORD *)((char *)this + 8444);
      _InterlockedOr(v112, 0);
      v58 = *((_DWORD *)this + 2114);
    }
    while ( v59 != v58 );
    v60 = *((_DWORD *)this + 2114);
    do
    {
      v61 = v60 & 0xFFFFFFFE;
      v121 = *(_QWORD *)((char *)this + 8444);
      v122 = *((_DWORD *)this + 2113);
      _InterlockedOr(v112, 0);
      v60 = *((_DWORD *)this + 2114);
    }
    while ( v61 != v60 );
    v62 = *((_DWORD *)this + 2114);
    do
    {
      v63 = v62 & 0xFFFFFFFE;
      v119 = *(_QWORD *)((char *)this + 8444);
      _InterlockedOr(v112, 0);
      v62 = *((_DWORD *)this + 2114);
    }
    while ( v63 != v62 );
    v64 = *((_DWORD *)this + 2114);
    do
    {
      v65 = v64 & 0xFFFFFFFE;
      v118 = *(_QWORD *)((char *)this + 8444);
      _InterlockedOr(v112, 0);
      v64 = *((_DWORD *)this + 2114);
    }
    while ( v65 != v64 );
    if ( !CDStream::Write(
            a2,
            "m_LastRedoneLSN",
            "%d:%d:%d (0x%08lx:%08lx:%04lx)",
            v118,
            HIDWORD(v119),
            (unsigned __int16)v122,
            v120,
            HIDWORD(v126),
            (unsigned __int16)v125) )
      goto LABEL_328;
    if ( !CDStream::Write(
            a2,
            "m_LastForkBlock",
            "0x%I64x",
            *((unsigned int *)this + 2116) | ((unsigned __int64)*((unsigned int *)this + 2115) << 32)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "m_RedoStopMark", "%ls", *((const wchar_t **)this + 1059)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "m_StartupThread", "0x%p", *((const void **)this + 902)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "m_RollbackThread", "0x%p", *((const void **)this + 903)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "m_RedoThread", "0x%p", *((const void **)this + 1060)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "m_AsyncRecoveryThread", "0x%p", *((const void **)this + 904)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "m_StartupTick", "%d", *((_DWORD *)this + 1814)) )
      goto LABEL_328;
    v120 = *(_QWORD *)((char *)this + 7260);
    v118 = v120;
    v121 = v120;
    v119 = v120;
    v117 = v120;
    if ( !CDStream::Write(
            a2,
            "m_lastLazyCommitLSN",
            "%d:%d:%d (0x%08lx:%08lx:%04lx)",
            v120,
            HIDWORD(v120),
            *((unsigned __int16 *)this + 3634),
            v120,
            HIDWORD(v120),
            *((unsigned __int16 *)this + 3634)) )
      goto LABEL_328;
    v120 = *((_QWORD *)this + 909);
    v118 = v120;
    v121 = v120;
    v119 = v120;
    v117 = v120;
    if ( !CDStream::Write(
            a2,
            "m_forceCommitLSN",
            "%d:%d:%d (0x%08lx:%08lx:%04lx)",
            v120,
            HIDWORD(v120),
            *((unsigned __int16 *)this + 3640),
            v120,
            HIDWORD(v120),
            *((unsigned __int16 *)this + 3640)) )
      goto LABEL_328;
    v120 = *((_QWORD *)this + 912);
    v118 = v120;
    v121 = v120;
    v119 = v120;
    v117 = v120;
    if ( !CDStream::Write(
            a2,
            "m_SplitLSN",
            "%d:%d:%d (0x%08lx:%08lx:%04lx)",
            v120,
            HIDWORD(v120),
            *((unsigned __int16 *)this + 3652),
            v120,
            HIDWORD(v120),
            *((unsigned __int16 *)this + 3652)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "m_IsDBBeingDropped", "%d", *((unsigned __int8 *)this + 7382)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "m_DelayedDurabilityOpts", "%d", *((_DWORD *)this + 534)) )
      goto LABEL_328;
    if ( !CDStream::Write(
            a2,
            "m_snapshotMaxXdesIdAfterCrash",
            "%I64d",
            *((unsigned int *)this + 512) + ((unsigned __int64)*((unsigned __int16 *)this + 1026) << 32)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "m_allowQdsCapture", "%d", *((unsigned __int8 *)this + 8299)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "m_alwaysProduceTidEnabled", "%d", *((unsigned __int8 *)this + 27465)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "m_acquireTidLocksDuringRecovery", "%d", *((unsigned __int8 *)this + 27471)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "TxCommitCount", "%I64d", *((_QWORD *)this + 7)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "ShortTxRollbackCount", "%I64d", *((_QWORD *)this + 8)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "LongTxRollbackCount", "%I64d", *((_QWORD *)this + 9)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "CTRTxRollbackCount", "%I64d", *((_QWORD *)this + 10)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "TempDbVersionStoreInserts", "%I64d", *((_QWORD *)this + 11)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "TempDbVersionStoreSmallRowInserts", "%I64d", *((_QWORD *)this + 12)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "PVSOffRowInserts", "%I64d", *((_QWORD *)this + 13)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "PVSOffRowLongTermInserts", "%I64d", *((_QWORD *)this + 14)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "VersionStoreChainedRowInserted", "%I64d", *((_QWORD *)this + 15)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "InRowVersionSkippedSameXdesCount", "%I64d", *((_QWORD *)this + 16)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "InRowVersionSkippedTimestampInteresting", "%I64d", *((_QWORD *)this + 27)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "InRowVersionSkippedSequence", "%I64d", *((_QWORD *)this + 28)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "InRowVersionSkippedCompressedPages", "%I64d", *((_QWORD *)this + 29)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "InRowVersionSkippedForwardedRecord", "%I64d", *((_QWORD *)this + 30)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "InRowVersionSkippedNoSpaceForGhostVerRec", "%I64d", *((_QWORD *)this + 31)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "InRowVersionSkippedNoSpaceForVerRecPtr", "%I64d", *((_QWORD *)this + 32)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "InRowVersionSkippedNotHobtDataPage", "%I64d", *((_QWORD *)this + 33)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "InRowVersionSkippedInPlaceUpdateCtxt", "%I64d", *((_QWORD *)this + 34)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "VersionStoreReads", "%I64d", *((_QWORD *)this + 17)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "VersionStoreDeepReads", "%I64d", *((_QWORD *)this + 18)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "VersionStoreInRowDiff", "%I64d", *((_QWORD *)this + 19)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "VersionStoreInRowFull", "%I64d", *((_QWORD *)this + 20)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "VersionStoreInRowGhost", "%I64d", *((_QWORD *)this + 21)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "VersionStoreRowTooLarge", "%I64d", *((_QWORD *)this + 22)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "VersionStoreDiffTooLarge", "%I64d", *((_QWORD *)this + 23)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "VersionStoreInRowPushedOff", "%I64d", *((_QWORD *)this + 24)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "VersionStoreInRowGhostPushedOff", "%I64d", *((_QWORD *)this + 25)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "VersionStoreOffRowForDelete", "%I64d", *((_QWORD *)this + 26)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "VersionStoreOffRowForLOB", "%I64d", *((_QWORD *)this + 35)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "VersionStorePointerReused", "%I64d", *((_QWORD *)this + 36)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "NonCtrMarkedTransactions", "%I64d", *((_QWORD *)this + 37)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "PersistedVersionStorePageCount", "%I64d", *((_QWORD *)this + 38)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "LongTermVersionStorePageCount", "%I64d", *((_QWORD *)this + 39)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "InsertsInDdlTransaction", "%I64d", *((_QWORD *)this + 40)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "DeletesInDdlTransaction", "%I64d", *((_QWORD *)this + 41)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "StaleVersionSpaceCleanupAttempts", "%I64d", *((_QWORD *)this + 42)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "StaleVersionSpaceCleanupPages", "%I64d", *((_QWORD *)this + 43)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "StaleVersionSpaceCleanupBytes", "%I64d", *((_QWORD *)this + 44)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "StaleVersionSpaceStrippedRows", "%I64d", *((_QWORD *)this + 45)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "StaleVersionSpaceUnGhostedRows", "%I64d", *((_QWORD *)this + 46)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "StaleVersionSpacePurgedRows", "%I64d", *((_QWORD *)this + 47)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "NestAbortedCount", "%I64d", *((_QWORD *)this + 48)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "SavePointAbortedCount", "%I64d", *((_QWORD *)this + 49)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "NestIdReadFromOffRowPVS", "%I64d", *((_QWORD *)this + 50)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "DeforwardingCount", "%I64d", *((_QWORD *)this + 51)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "BlobInsertsOffRowVersionInfo", "%I64d", *((_QWORD *)this + 53)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "BtreeLogicalRevertCount", "%I64d", *((_QWORD *)this + 62)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "HeapLogicalRevertCount", "%I64d", *((_QWORD *)this + 63)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "BlobLogicalRevertCount", "%I64d", *((_QWORD *)this + 64)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "UpdatesOnAbortedRowsCount", "%I64d", *((_QWORD *)this + 65)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "TxRollbackCount", "%I64d", *((_QWORD *)this + 66)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "InRowPagesSwept", "%I64d", *((_QWORD *)this + 73)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "InRowNonDataPagesSwept", "%I64d", *((_QWORD *)this + 74)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "InRowPagesSweptMarkedNoVersions", "%I64d", *((_QWORD *)this + 75)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "InRowNonDataPagesSweptPercent", "%I64d", *((_QWORD *)this + 76)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "CtrPagesSwept", "%I64d", *((_QWORD *)this + 77)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "CtrNonDataPagesSwept", "%I64d", *((_QWORD *)this + 78)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "CtrPagesSweptMarkedNoVersions", "%I64d", *((_QWORD *)this + 79)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "OffRowVersionPageNotEligbleForCleanup", "%I64d", *((_QWORD *)this + 115)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "OffRowVersionPageSkippedLowWaterMark", "%I64d", *((_QWORD *)this + 106)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "OffRowVersionPageSkippedTransactionNotCleaned", "%I64d", *((_QWORD *)this + 112)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "OffRowVersionPageSkippedOldestActiveXdesid", "%I64d", *((_QWORD *)this + 113)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "OffRowVersionPageSkippedOldestAbortedXdesid", "%I64d", *((_QWORD *)this + 114)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "OffRowVersionPageSkippedMinUsefulXts", "%I64d", *((_QWORD *)this + 107)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "OffRowVersionPageSkippedOldestSnapshot", "%I64d", *((_QWORD *)this + 108)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "TxStartedLongTimeAgo", "%I64d", *((_QWORD *)this + 116)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "MultipleVersionFromNestTran", "%I64d", *((_QWORD *)this + 120)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "WorkerMigrationCount", "%I32d", *((_DWORD *)this + 242)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "m_dirtyPageCountSnapshot", "%I64d", *((_QWORD *)this + 3414)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "MaxVersionChainLR", "%I32d", *((_DWORD *)this + 243)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "MaxVersionChainQuery", "%I32d", *((_DWORD *)this + 244)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "DoOnlyLRCount", "%I64d", *((_QWORD *)this + 123)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "MTVCv2 Total Rows cleaned by worker threads", "%I64d", *((unsigned int *)this + 259)) )
      goto LABEL_328;
    LODWORD(v123) = *((_DWORD *)this + 257);
    WORD2(v123) = *((_WORD *)this + 516);
    if ( !CDStream::Write(a2, "MTVCv2 worker threads MinInterestingTs", "%I64d", &v123) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "MTVCv2 Total NonDataPages swept by worker threads", "%I64d", *((_QWORD *)this + 147)) )
      goto LABEL_328;
    if ( !CDStream::Write(
            a2,
            "MTVCv2 Total Pages with version bit swept by worker threads",
            "%I64d",
            *((_QWORD *)this + 148)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "MTVCv2 Total pages swept by worker threads", "%I64d", *((_QWORD *)this + 149)) )
      goto LABEL_328;
    if ( !CDStream::Write(
            a2,
            "MTVCv2 Total pages marked no versions by worker threads",
            "%I64d",
            *((_QWORD *)this + 150)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "MTVCv2 Total Pages dirtied by worker threads", "%I64d", *((_QWORD *)this + 151)) )
      goto LABEL_328;
    if ( !CDStream::Write(a2, "MTVCv2 Total Pages Read ahead by worker threads", "%I64d", *((_QWORD *)this + 152)) )
      goto LABEL_328;
    v120 = *((_QWORD *)this + 264);
    v118 = v120;
    v121 = v120;
    v119 = v120;
    v117 = v120;
    if ( !CDStream::Write(
            a2,
            "m_UserQuorumLSN",
            "%d:%d:%d (0x%08lx:%08lx:%04lx)",
            v120,
            HIDWORD(v120),
            *((unsigned __int16 *)this + 1060),
            v120,
            HIDWORD(v120),
            *((unsigned __int16 *)this + 1060)) )
      goto LABEL_328;
    LODWORD(v114) = 2;
    v113 = 0;
    v66 = ConvertDateToStrSafe((char *)this + 2128, v131, 128);
    if ( v66 <= 0 )
    {
LABEL_231:
      v68 = *((_DWORD *)this + 8);
      if ( *((_DWORD *)this + 12) == v68 )
      {
        if ( v68 )
        {
          v69 = 0;
          v70 = v68;
          v71 = 0;
          do
          {
            v7 += *(_QWORD *)((v69 << *((_BYTE *)this + 36)) + *((_QWORD *)this + 3));
            v71 += *(_QWORD *)((v69++ << *((_BYTE *)this + 52)) + *((_QWORD *)this + 5));
            --v70;
          }
          while ( v70 );
          v124 = v71;
          v4 = (unsigned __int8 *)this + 8301;
        }
        if ( !CDStream::Write(a2, "InPageRecordReadCount", "%I64d", v7)
          || !CDStream::Write(a2, "VersionedRecordReadCount", "%I64d", v124) )
        {
          goto LABEL_328;
        }
      }
      else if ( !CDStream::Write(a2, "Unexpected InPageRecordReadCount CPU count", "%d", v68)
             || !CDStream::Write(a2, "Unexpected VersionedRecordReadCount CPU count", "%d", *((_DWORD *)this + 12)) )
      {
        goto LABEL_328;
      }
      v72 = (__m128i *)*((_QWORD *)this + 1083);
      if ( !v72 )
        goto LABEL_343;
      v127 = v129;
      v73 = _mm_srli_si128(*v72, 8).m128i_u64[0];
      v74 = v72->m128i_i64[0];
      v127.m128i_i64[0] = v129.m128i_i64[0];
      v127.m128i_i64[1] = _mm_srli_si128(v129, 8).m128i_u64[0];
      v75 = __PAIR128__(v127.m128i_u64[1], v129.m128i_u64[0]);
      _InterlockedCompareExchange128(v72->m128i_i64, v73, v74, (signed __int64 *)&v75);
      v76 = v75;
      v77 = DWORD2(v75);
      v127.m128i_i64[1] = *((_QWORD *)&v75 + 1);
      TickCount64 = GetTickCount64();
      v79 = (unsigned __int64)v75 >> 63;
      v80 = 0;
      if ( TickCount64 < (v75 & 0x7FFFFFFFFFFFFFFFLL) )
        v80 = v76 - TickCount64;
      v81 = L"false";
      if ( (_BYTE)v79 )
        v81 = L"true";
      if ( CDStream::Write(a2, "m_RbioRgGate.Enabled", "%s", (const char *)v81)
        && CDStream::Write(a2, "m_RbioRgGate.TimeoutMs", "%d", v80)
        && CDStream::Write(a2, "m_RbioRgGate.BpsLimit", "%d", v77)
        && CDStream::Write(a2, "m_RbioRgGate.WaitType", "%lx", v127.m128i_i32[3]) )
      {
LABEL_343:
        for ( i = 0; ; ++i )
        {
          v83 = *((_QWORD *)this + 1088);
          if ( v83 > 4 )
            v83 = 4;
          if ( i >= v83 )
            break;
          v84 = (char *)this + 104 * i + 8712;
          if ( !CDStream::Write(a2, "\nRedoHistory", "%d", i) )
            goto LABEL_328;
          v85 = L"false";
          if ( *v84 )
            v85 = L"true";
          if ( !CDStream::Write(a2, "r.m_MayHaveDeferred", "%ls", v85) )
            goto LABEL_328;
          v86 = L"false";
          if ( v84[1] )
            v86 = L"true";
          if ( !CDStream::Write(a2, "r.m_IsAcceptLogMode", "%ls", v86) )
            goto LABEL_328;
          v87 = L"false";
          if ( v84[2] )
            v87 = L"true";
          if ( !CDStream::Write(a2, "r.m_IsLogAcceptSource", "%ls", v87) )
            goto LABEL_328;
          v88 = L"false";
          if ( v84[3] )
            v88 = L"true";
          if ( !CDStream::Write(a2, "r.m_IsRedoPaused", "%ls", v88) )
            goto LABEL_328;
          v89 = L"false";
          if ( v84[4] )
            v89 = L"true";
          if ( !CDStream::Write(a2, "r.m_TransitionToLogging", "%ls", v89) )
            goto LABEL_328;
          v90 = L"false";
          if ( v84[5] )
            v90 = L"true";
          if ( !CDStream::Write(a2, "r.m_MayHaveNeverDoneLog", "%ls", v90) )
            goto LABEL_328;
          v91 = L"false";
          if ( v84[6] )
            v91 = L"true";
          if ( !CDStream::Write(a2, "r.m_AbortSet", "%ls", v91) )
            goto LABEL_328;
          if ( !CDStream::Write(
                  a2,
                  "r.m_RedoThruBlock",
                  "0x%I64x",
                  HIDWORD(*((_QWORD *)v84 + 1)) | ((unsigned __int64)(unsigned int)*((_QWORD *)v84 + 1) << 32)) )
            goto LABEL_328;
          if ( !CDStream::Write(
                  a2,
                  "r.m_LastForkBlock",
                  "0x%I64x",
                  HIDWORD(*((_QWORD *)v84 + 2)) | ((unsigned __int64)(unsigned int)*((_QWORD *)v84 + 2) << 32)) )
            goto LABEL_328;
          if ( !CDStream::Write(a2, "r.m_RedoStopMark", "%p", *((const void **)v84 + 3)) )
            goto LABEL_328;
          if ( !CDStream::Write(a2, "r.m_RedoThread", "%p", *((const void **)v84 + 12)) )
            goto LABEL_328;
          v120 = *((_QWORD *)v84 + 4);
          v118 = v120;
          v119 = v120;
          v117 = v120;
          if ( !CDStream::Write(
                  a2,
                  "r.m_RedoProgress.m_LastRedoneLSN",
                  "%d:%d:%d (0x%08lx:%08lx:%04lx)",
                  v120,
                  HIDWORD(v120),
                  *((unsigned __int16 *)v84 + 20),
                  v120,
                  HIDWORD(v120),
                  *((unsigned __int16 *)v84 + 20)) )
            goto LABEL_328;
          v124 = *(_QWORD *)(v84 + 44);
          v126 = v124;
          v123 = v124;
          v121 = v124;
          if ( !CDStream::Write(
                  a2,
                  "r.m_RedoProgress.m_LastReceivedLSN",
                  "%d:%d:%d (0x%08lx:%08lx:%04lx)",
                  v124,
                  HIDWORD(v124),
                  *((unsigned __int16 *)v84 + 26),
                  v124,
                  HIDWORD(v124),
                  *((unsigned __int16 *)v84 + 26))
            || !CDStream::Write(
                  a2,
                  "r.m_RedoTarget",
                  "0x%I64x",
                  HIDWORD(*((_QWORD *)v84 + 7)) | ((unsigned __int64)(unsigned int)*((_QWORD *)v84 + 7) << 32))
            || !CDStream::Write(a2, "r.m_RedoQueueBytes", "%I64d", *((_QWORD *)v84 + 8))
            || !CDStream::Write(a2, "r.m_RedoRate", "%I64d", *((_QWORD *)v84 + 9)) )
          {
            goto LABEL_328;
          }
          LODWORD(v114) = 2;
          v113 = 0;
          v92 = ConvertDateToStrSafe(v84 + 80, v131, 128);
          if ( v92 > 0 )
          {
            v93 = 128;
            if ( v92 < 128 )
              v93 = v92;
            if ( (unsigned __int64)v93 >= 0x81 )
              goto LABEL_340;
            v131[v93] = 0;
            if ( !CDStream::Write(a2, "r.m_LastKnownTime", "%hs", v131) )
              goto LABEL_328;
          }
          if ( !CDStream::Write(a2, "r.m_DropNotificationReason", "%d", *((_DWORD *)v84 + 22)) )
            goto LABEL_328;
        }
        v94 = (FileMgr *)*((_QWORD *)this + 212);
        if ( v94 )
          FileMgr::Dump(v94, a2);
        if ( !byte_1031852E4 || !*(_QWORD *)(*((_QWORD *)this + 214) + 5320LL) )
        {
          v95 = *((_QWORD *)this + 217);
          if ( v95 )
            (*(void (__fastcall **)(__int64, struct CDStream *))(*(_QWORD *)v95 + 136LL))(v95, a2);
        }
        LogTruncMgr::Dump((RecoveryUnit *)((char *)this + 2168), a2);
        XdesMgr::Dump((RecoveryUnit *)((char *)this + 6600), a2);
        v96 = *((_QWORD *)this + 213);
        if ( v96 )
        {
          v97 = 0x10000;
          v98 = *(_DWORD *)(v96 + 116) + 0xFFFF;
          if ( v98 >= 0x10000 )
          {
            v99 = v98;
            v100 = 0x10000;
            while ( 1 )
            {
              if ( v100 >= 0x10000 && v97 <= *(_DWORD *)(v96 + 116) + 0xFFFF )
              {
                v101 = *(_QWORD *)(*(_QWORD *)(v96 + 80) + v6);
                if ( v101 )
                {
                  if ( (*(_BYTE *)(v101 + 1616) & 4) == 0 )
                    break;
                }
              }
              ++v97;
              ++v100;
              v6 += 8;
              if ( v100 > v99 )
                goto LABEL_308;
            }
            StreamFileMgr::Dump(*((StreamFileMgr **)this + 213), a2);
          }
        }
LABEL_308:
        v102 = (RecoveryMgr *)*((_QWORD *)this + 229);
        if ( v102 )
          RecoveryMgr::Dump(v102, a2);
        v103 = (DirtyPageMgr *)*((_QWORD *)this + 235);
        if ( v103 )
          DirtyPageMgr::Dump(v103, a2);
        v104 = *((_QWORD *)this + 219);
        if ( v104 )
          (*(void (__fastcall **)(__int64, struct CDStream *))(*(_QWORD *)v104 + 8LL))(v104, a2);
        v105 = (TenantLogTracker *)*((_QWORD *)this + 220);
        if ( v105 )
          TenantLogTracker::Dump(v105, a2);
        v106 = *((_QWORD *)this + 902);
        if ( !v106
          || *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL)
                       + 96LL) == v106
          || (unsigned int)SEInternalTLS::Dump(v106, a2, 1) )
        {
          v107 = *((_QWORD *)this + 903);
          if ( !v107
            || *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL)
                         + 96LL) == v107
            || (unsigned int)SEInternalTLS::Dump(v107, a2, 1) )
          {
            v108 = *((_QWORD *)this + 1060);
            if ( !v108
              || *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL)
                           + 96LL) == v108
              || (unsigned int)SEInternalTLS::Dump(v108, a2, 1) )
            {
              v109 = *((_QWORD *)this + 904);
              if ( !v109
                || *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                         + SystemThread_TlsOffset
                                         + 8LL)
                             + 96LL) == v109
                || (unsigned int)SEInternalTLS::Dump(v109, a2, 1) )
              {
                v111 = (LogBlockActivityTracer *)*((_QWORD *)this + 931);
                if ( v111 )
                  LogBlockActivityTracer::Dump(v111, a2);
                v9 = v116 == 0;
                goto LABEL_336;
              }
            }
          }
        }
      }
LABEL_328:
      v8 = v116 == 0;
      goto LABEL_329;
    }
    v67 = 128;
    if ( v66 < 128 )
      v67 = v66;
    if ( (unsigned __int64)v67 < 0x81 )
    {
      v131[v67] = 0;
      if ( !CDStream::Write(a2, "m_LastUserCommitTime", "%hs", v131) )
        goto LABEL_328;
      goto LABEL_231;
    }
LABEL_340:
    _report_rangecheckfailure();
  }
  if ( !CDStream::Write(a2, "m_IsAlreadyDumping", "%d", *v4) )
  {
    v8 = v5 == 0;
LABEL_329:
    if ( v8 )
    {
      if ( *v4 )
        *v4 = 0;
    }
    CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v130);
    return 0;
  }
  v9 = v5 == 0;
LABEL_336:
  if ( v9 && *v4 )
    *v4 = 0;
  CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v130);
  return 1;
}

```

## disassembly

```asm
0x101ce6da0  push    rbp
0x101ce6da2  push    rsi
0x101ce6da3  push    rdi
0x101ce6da4  push    r12
0x101ce6da6  push    r13
0x101ce6da8  push    r14
0x101ce6daa  push    r15
0x101ce6dac  lea     rbp, [rsp-350h]
0x101ce6db4  sub     rsp, 450h
0x101ce6dbb  mov     [rbp+380h+var_380], 0FFFFFFFFFFFFFFFEh
0x101ce6dc3  mov     [rsp+480h+arg_10], rbx
0x101ce6dcb  mov     rax, cs:__security_cookie
0x101ce6dd2  xor     rax, rsp
0x101ce6dd5  mov     [rbp+380h+var_40], rax
0x101ce6ddc  mov     r14, rdx
0x101ce6ddf  mov     rsi, rcx
0x101ce6de2  lea     rcx, [rbp+380h+var_2E0]
0x101ce6de9  call    cs:__imp_??0CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::CAutoStreamHeader(void)
0x101ce6def  nop
0x101ce6df0  lea     rdi, [rsi+206Dh]
0x101ce6df7  mov     [rsp+480h+var_430], rdi
0x101ce6dfc  movzx   ebx, byte ptr [rdi]
0x101ce6dff  mov     [rsp+480h+var_428], bl
0x101ce6e03  xor     r13d, r13d
0x101ce6e06  mov     r12d, r13d
0x101ce6e09  mov     [rbp+380h+var_3C0], r13
0x101ce6e0d  movzx   eax, byte ptr [rdi]
0x101ce6e10  test    al, al
0x101ce6e12  jz      short loc_101CE6E41
0x101ce6e14  mov     r9d, eax
0x101ce6e17  lea     r8, aD_5; "%d"
0x101ce6e1e  lea     rdx, aMIsalreadydump; "m_IsAlreadyDumping"
0x101ce6e25  mov     rcx, r14
0x101ce6e28  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x101ce6e2e  nop
0x101ce6e2f  test    eax, eax
0x101ce6e31  jnz     short loc_101CE6E3A
0x101ce6e33  test    bl, bl
0x101ce6e35  jmp     loc_101CE9620
0x101ce6e3a  test    bl, bl
0x101ce6e3c  jmp     loc_101CE9655
0x101ce6e41  mov     byte ptr [rsi+206Dh], 1
0x101ce6e48  mov     eax, [rsi+6B8h]
0x101ce6e4e  mov     ecx, eax
0x101ce6e50  shr     ecx, 10h
0x101ce6e53  movzx   r9d, ax
0x101ce6e57  mov     [rsp+480h+var_458], rsi
0x101ce6e5c  mov     dword ptr [rsp+480h+var_460], ecx
0x101ce6e60  lea     r8, aRecoveryunitDD; "RecoveryUnit %d:%d, @0x%p"
0x101ce6e67  mov     rdx, r14
0x101ce6e6a  lea     rcx, [rbp+380h+var_2E0]
0x101ce6e71  call    cs:__imp_?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ; CAutoStreamHeader::Init(CDStream *,char const *,...)
0x101ce6e77  test    eax, eax
0x101ce6e79  jnz     short loc_101CE6E82
0x101ce6e7b  test    bl, bl
0x101ce6e7d  jmp     loc_101CE9620
0x101ce6e82  movsxd  rax, dword ptr [rsi+670h]
0x101ce6e89  lea     r15, aUnknown_4; "UNKNOWN"
0x101ce6e90  lea     rcx, __@@_PchSym_@00@UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq@4B2008FD98C1DD4
0x101ce6e97  cmp     eax, 9
0x101ce6e9a  jge     short loc_101CE6EAE
0x101ce6e9c  lfence
0x101ce6e9f  mov     r9, ds:rva ?StartupStateNames@@3PAPEA_WA[rcx+rax*8]; wchar_t * near * StartupStateNames ...
0x101ce6ea7  movzx   ebx, [rsp+480h+var_428]
0x101ce6eac  jmp     short loc_101CE6EB1
0x101ce6eae  mov     r9, r15
0x101ce6eb1  lea     r8, aLs; "%ls"
0x101ce6eb8  lea     rdx, aMStartupphase; "m_StartupPhase"
0x101ce6ebf  mov     rcx, r14
0x101ce6ec2  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x101ce6ec8  test    eax, eax
0x101ce6eca  jz      loc_101CE6F52
0x101ce6ed0  movsxd  rax, dword ptr [rsi+678h]
0x101ce6ed7  cmp     eax, 7
0x101ce6eda  jge     short loc_101CE6EF5
0x101ce6edc  lfence
0x101ce6edf  lea     r9, __@@_PchSym_@00@UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq@4B2008FD98C1DD4
0x101ce6ee6  mov     r9, ds:rva ?AvailabilityStateNames@@3PAPEA_WA[r9+rax*8]; wchar_t * near * AvailabilityStateNames ...
0x101ce6eee  movzx   ebx, [rsp+480h+var_428]
0x101ce6ef3  jmp     short loc_101CE6EF8
0x101ce6ef5  mov     r9, r15
0x101ce6ef8  lea     r8, aLs; "%ls"
0x101ce6eff  lea     rdx, aMCurrentstate; "m_CurrentState"
0x101ce6f06  mov     rcx, r14
0x101ce6f09  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x101ce6f0f  test    eax, eax
0x101ce6f11  jz      short loc_101CE6F52
0x101ce6f13  movsxd  rax, dword ptr [rsi+674h]
0x101ce6f1a  cmp     eax, 7
0x101ce6f1d  jge     short loc_101CE6F38
0x101ce6f1f  lfence
0x101ce6f22  lea     rcx, __@@_PchSym_@00@UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq@4B2008FD98C1DD4
0x101ce6f29  mov     r9, ds:rva ?AvailabilityStateNames@@3PAPEA_WA[rcx+rax*8]; wchar_t * near * AvailabilityStateNames ...
0x101ce6f31  movzx   ebx, [rsp+480h+var_428]
0x101ce6f36  jmp     short loc_101CE6F3B
0x101ce6f38  mov     r9, r15
0x101ce6f3b  lea     r8, aLs; "%ls"
0x101ce6f42  lea     rdx, aMTargetstate; "m_TargetState"
0x101ce6f49  mov     rcx, r14
0x101ce6f4c  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x101ce6f52  mov     r9d, [rsi+664h]
0x101ce6f59  lea     r8, aD_5; "%d"
0x101ce6f60  lea     rdx, aMDbfragid; "m_DbFragId"
0x101ce6f67  mov     rcx, r14
0x101ce6f6a  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x101ce6f70  test    eax, eax
0x101ce6f72  jnz     short loc_101CE6F7B
0x101ce6f74  test    bl, bl
0x101ce6f76  jmp     loc_101CE9620
0x101ce6f7b  mov     r9, [rsi+668h]
0x101ce6f82  lea     r8, aI64d_3; "%I64d"
0x101ce6f89  lea     rdx, aMAllocunitidne; "m_AllocUnitIdNext"
0x101ce6f90  mov     rcx, r14
0x101ce6f93  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x101ce6f99  test    eax, eax
0x101ce6f9b  jnz     short loc_101CE6FA4
0x101ce6f9d  test    bl, bl
0x101ce6f9f  jmp     loc_101CE9620
0x101ce6fa4  movzx   r9d, word ptr [rsi+67Eh]
0x101ce6fac  lea     r8, aD_5; "%d"
0x101ce6fb3  lea     rdx, aMOndiskversion; "m_OnDiskVersion"
0x101ce6fba  mov     rcx, r14
0x101ce6fbd  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x101ce6fc3  test    eax, eax
0x101ce6fc5  jnz     short loc_101CE6FCE
0x101ce6fc7  test    bl, bl
0x101ce6fc9  jmp     loc_101CE9620
0x101ce6fce  mov     ecx, [rsi+814h]
0x101ce6fd4  nop     dword ptr [rax+00h]
0x101ce6fd8  nop     dword ptr [rax+rax+00000000h]
0x101ce6fe0  and     ecx, 0FFFFFFFEh
0x101ce6fe3  mov     eax, ecx
0x101ce6fe5  movsd   xmm0, qword ptr [rsi+808h]
0x101ce6fed  movsd   [rbp+380h+var_3E0], xmm0
0x101ce6ff2  movzx   ebx, word ptr [rsi+810h]
0x101ce6ff9  lock or [rsp+480h+var_480], r12d
0x101ce6ffe  mov     ecx, [rsi+814h]
0x101ce7004  cmp     eax, ecx
0x101ce7006  jnz     short loc_101CE6FE0
0x101ce7008  mov     eax, [rsi+814h]
0x101ce700e  xchg    ax, ax
0x101ce7010  and     eax, 0FFFFFFFEh
0x101ce7013  mov     ecx, eax
0x101ce7015  movsd   xmm0, qword ptr [rsi+808h]
0x101ce701d  movsd   [rsp+480h+var_420], xmm0
0x101ce7023  lock or [rsp+480h+var_480], r12d
0x101ce7028  mov     eax, [rsi+814h]
0x101ce702e  cmp     ecx, eax
0x101ce7030  jnz     short loc_101CE7010
0x101ce7032  mov     eax, [rsi+814h]
0x101ce7038  nop     dword ptr [rax+rax+00000000h]
0x101ce7040  and     eax, 0FFFFFFFEh
0x101ce7043  mov     ecx, eax
0x101ce7045  movsd   xmm0, qword ptr [rsi+808h]
0x101ce704d  movsd   [rbp+380h+var_400], xmm0
0x101ce7052  lock or [rsp+480h+var_480], r12d
0x101ce7057  mov     eax, [rsi+814h]
0x101ce705d  cmp     ecx, eax
0x101ce705f  jnz     short loc_101CE7040
0x101ce7061  mov     ecx, [rsi+814h]
0x101ce7067  nop     word ptr [rax+rax+00000000h]
0x101ce7070  and     ecx, 0FFFFFFFEh
0x101ce7073  mov     eax, ecx
0x101ce7075  movsd   xmm0, qword ptr [rsi+808h]
0x101ce707d  movsd   [rbp+380h+var_3E0], xmm0
0x101ce7082  movzx   edx, word ptr [rsi+810h]
0x101ce7089  lock or [rsp+480h+var_480], r12d
0x101ce708e  mov     ecx, [rsi+814h]
0x101ce7094  cmp     eax, ecx
0x101ce7096  jnz     short loc_101CE7070
0x101ce7098  mov     eax, [rsi+814h]
0x101ce709e  xchg    ax, ax
0x101ce70a0  and     eax, 0FFFFFFFEh
0x101ce70a3  mov     ecx, eax
0x101ce70a5  movsd   xmm0, qword ptr [rsi+808h]
0x101ce70ad  movsd   [rsp+480h+var_410], xmm0
0x101ce70b3  lock or [rsp+480h+var_480], r12d
0x101ce70b8  mov     eax, [rsi+814h]
0x101ce70be  cmp     ecx, eax
0x101ce70c0  jnz     short loc_101CE70A0
0x101ce70c2  mov     eax, [rsi+814h]
0x101ce70c8  nop     dword ptr [rax+rax+00000000h]
0x101ce70d0  and     eax, 0FFFFFFFEh
0x101ce70d3  mov     ecx, eax
0x101ce70d5  movsd   xmm0, qword ptr [rsi+808h]
0x101ce70dd  movsd   [rbp+380h+var_3F0], xmm0
0x101ce70e2  lock or [rsp+480h+var_480], r12d
0x101ce70e7  mov     eax, [rsi+814h]
0x101ce70ed  cmp     ecx, eax
0x101ce70ef  jnz     short loc_101CE70D0
0x101ce70f1  mov     eax, ebx
0x101ce70f3  mov     rcx, [rsp+480h+var_420]
0x101ce70f8  shr     rcx, 20h
0x101ce70fc  mov     rbx, [rsp+480h+var_410]
0x101ce7101  shr     rbx, 20h
0x101ce7105  mov     [rsp+480h+var_440], eax
0x101ce7109  mov     [rsp+480h+var_448], ecx
0x101ce710d  mov     eax, dword ptr [rbp+380h+var_400]
0x101ce7110  mov     [rsp+480h+var_450], eax
0x101ce7114  mov     dword ptr [rsp+480h+var_458], edx
0x101ce7118  mov     dword ptr [rsp+480h+var_460], ebx
0x101ce711c  mov     r9d, dword ptr [rbp+380h+var_3F0]
0x101ce7120  lea     r8, aDDD0x08lx08lx0; "%d:%d:%d (0x%08lx:%08lx:%04lx)"
0x101ce7127  lea     rdx, aMCommitlsn_0; "m_CommitLsn"
0x101ce712e  mov     rcx, r14
0x101ce7131  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x101ce7137  test    eax, eax
0x101ce7139  jz      loc_101CE961B
0x101ce713f  mov     r9, [rsi+818h]
0x101ce7146  lea     r8, aI64d_3; "%I64d"
0x101ce714d  lea     rdx, aMCommitlsntick; "m_CommitLsnTickCount"
0x101ce7154  mov     rcx, r14
0x101ce7157  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x101ce715d  test    eax, eax
0x101ce715f  jz      loc_101CE961B
0x101ce7165  movsd   xmm0, qword ptr [rsi+2408h]
0x101ce716d  movsd   [rbp+380h+var_3E0], xmm0
0x101ce7172  movsd   [rbp+380h+var_3F0], xmm0
0x101ce7177  movsd   [rsp+480h+var_410], xmm0
0x101ce717d  movsd   [rbp+380h+var_3E0], xmm0
0x101ce7182  movsd   [rbp+380h+var_400], xmm0
0x101ce7187  movsd   [rsp+480h+var_420], xmm0
0x101ce718d  movzx   eax, word ptr [rsi+2410h]
0x101ce7194  mov     rcx, [rbp+380h+var_3F0]
0x101ce7198  shr     rcx, 20h
0x101ce719c  movzx   edx, word ptr [rsi+2410h]
0x101ce71a3  mov     rbx, [rbp+380h+var_400]
0x101ce71a7  shr     rbx, 20h
0x101ce71ab  mov     [rsp+480h+var_440], eax
0x101ce71af  mov     [rsp+480h+var_448], ecx
0x101ce71b3  mov     eax, dword ptr [rsp+480h+var_410]
0x101ce71b7  mov     [rsp+480h+var_450], eax
0x101ce71bb  mov     dword ptr [rsp+480h+var_458], edx
0x101ce71bf  mov     dword ptr [rsp+480h+var_460], ebx
0x101ce71c3  mov     r9d, dword ptr [rsp+480h+var_420]
0x101ce71c8  lea     r8, aDDD0x08lx08lx0; "%d:%d:%d (0x%08lx:%08lx:%04lx)"
0x101ce71cf  lea     rdx, aMSereplholdlsn; "m_seReplHoldLSN"
0x101ce71d6  mov     rcx, r14
0x101ce71d9  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x101ce71df  test    eax, eax
0x101ce71e1  jz      loc_101CE961B
0x101ce71e7  mov     ecx, [rsi+82Ch]
0x101ce71ed  nop     dword ptr [rax]
0x101ce71f0  and     ecx, 0FFFFFFFEh
0x101ce71f3  mov     eax, ecx
0x101ce71f5  movsd   xmm0, qword ptr [rsi+820h]
0x101ce71fd  movsd   [rbp+380h+var_3E0], xmm0
0x101ce7202  movzx   ebx, word ptr [rsi+828h]
0x101ce7209  lock or [rsp+480h+var_480], r12d
0x101ce720e  mov     ecx, [rsi+82Ch]
0x101ce7214  cmp     eax, ecx
0x101ce7216  jnz     short loc_101CE71F0
0x101ce7218  mov     eax, [rsi+82Ch]
0x101ce721e  xchg    ax, ax
0x101ce7220  and     eax, 0FFFFFFFEh
0x101ce7223  mov     ecx, eax
0x101ce7225  movsd   xmm0, qword ptr [rsi+820h]
0x101ce722d  movsd   [rbp+380h+var_3F0], xmm0
0x101ce7232  lock or [rsp+480h+var_480], r12d
0x101ce7237  mov     eax, [rsi+82Ch]
0x101ce723d  cmp     ecx, eax
0x101ce723f  jnz     short loc_101CE7220
0x101ce7241  mov     eax, [rsi+82Ch]
0x101ce7247  nop     word ptr [rax+rax+00000000h]
0x101ce7250  and     eax, 0FFFFFFFEh
0x101ce7253  mov     ecx, eax
0x101ce7255  movsd   xmm0, qword ptr [rsi+820h]
0x101ce725d  movsd   [rsp+480h+var_410], xmm0
0x101ce7263  lock or [rsp+480h+var_480], r12d
0x101ce7268  mov     eax, [rsi+82Ch]
0x101ce726e  cmp     ecx, eax
0x101ce7270  jnz     short loc_101CE7250
0x101ce7272  mov     ecx, [rsi+82Ch]
0x101ce7278  nop     dword ptr [rax+rax+00000000h]
0x101ce7280  and     ecx, 0FFFFFFFEh
0x101ce7283  mov     eax, ecx
0x101ce7285  movsd   xmm0, qword ptr [rsi+820h]
0x101ce728d  movsd   [rbp+380h+var_3E0], xmm0
0x101ce7292  movzx   edx, word ptr [rsi+828h]
0x101ce7299  lock or [rsp+480h+var_480], r12d
0x101ce729e  mov     ecx, [rsi+82Ch]
0x101ce72a4  cmp     eax, ecx
0x101ce72a6  jnz     short loc_101CE7280
0x101ce72a8  mov     eax, [rsi+82Ch]
0x101ce72ae  xchg    ax, ax
0x101ce72b0  and     eax, 0FFFFFFFEh
0x101ce72b3  mov     ecx, eax
0x101ce72b5  movsd   xmm0, qword ptr [rsi+820h]
0x101ce72bd  movsd   [rbp+380h+var_400], xmm0
0x101ce72c2  lock or [rsp+480h+var_480], r12d
0x101ce72c7  mov     eax, [rsi+82Ch]
0x101ce72cd  cmp     ecx, eax
0x101ce72cf  jnz     short loc_101CE72B0
0x101ce72d1  mov     eax, [rsi+82Ch]
0x101ce72d7  nop     word ptr [rax+rax+00000000h]
0x101ce72e0  and     eax, 0FFFFFFFEh
0x101ce72e3  mov     ecx, eax
0x101ce72e5  movsd   xmm0, qword ptr [rsi+820h]
0x101ce72ed  movsd   [rsp+480h+var_420], xmm0
0x101ce72f3  lock or [rsp+480h+var_480], r12d
  ... truncated ...
```
