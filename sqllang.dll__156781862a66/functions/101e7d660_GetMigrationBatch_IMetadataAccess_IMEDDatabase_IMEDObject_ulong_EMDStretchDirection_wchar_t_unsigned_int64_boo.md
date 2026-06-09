# GetMigrationBatch(IMetadataAccess *,IMEDDatabase *,IMEDObject *,ulong,EMDStretchDirection,wchar_t * *,unsigned __int64 *,bool,bool)

- ea: `0x101e7d660`
- end: `0x101e7ea61`
- name: `?GetMigrationBatch@@YAJPEAVIMetadataAccess@@PEAVIMEDDatabase@@PEAVIMEDObject@@KW4EMDStretchDirection@@PEAPEA_WPEA_K_N6@Z`
- size: `5121`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x101e64a80`
- `0x101e80e00`

## callees

- `0x1004012d0`
- `0x100401340`
- `0x100430960`
- `0x100baf020`
- `0x100baf090`
- `0x101e472e0`
- `0x101e53d80`
- `0x101e65d90`
- `0x101e6e0f0`
- `0x101e6e230`
- `0x101e6e3d0`
- `0x101e6e440`
- `0x101e77f30`
- `0x101e7cfa0`
- `0x101e7d3b0`
- `0x101e7d660`
- `0x101e852e0`
- `0x101e85d40`

## import_xrefs

- `sqldk!?SetDeadlockPriority@SOS_Task@@QEAAXW4TASK_DEADLOCK_PRIORITY@1@@Z` at `0x101e7ea46`
- `sqldk!?SetDeadlockPriority@SOS_Task@@QEAAXW4TASK_DEADLOCK_PRIORITY@1@@Z` at `0x101e7ea46`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x101e7d76b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101e7da72`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101e7dc82`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101e7de6c`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101e7e608`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101e7da72`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101e7dc82`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101e7de6c`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101e7e608`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101e7e9c8`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101e7e9c8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e7d6d2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e7d7b5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e7d7f9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e7d883`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e7e2be`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e7e2fa`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e7e363`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e7d6d2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e7d7b5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e7d7f9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e7d883`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e7e2be`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e7e2fa`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e7e363`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e7d94d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e7d9dd`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e7da11`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e7dc52`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e7de37`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e7e06b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e7e187`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e7e3fc`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e7e5d3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e7d94d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e7d9dd`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e7da11`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e7dc52`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e7de37`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e7e06b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e7e187`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e7e3fc`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e7e5d3`
- `sqldk!SystemThread_TlsIndex` at `0x101e7e990`
- `sqldk!SystemThread_TlsIndex` at `0x101e7ea09`
- `sqldk!SystemThread_TlsOffset` at `0x101e7e999`
- `sqldk!SystemThread_TlsOffset` at `0x101e7ea12`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101e7e95a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101e7e9ef`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101e7e95a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101e7e9ef`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e7e9b2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e7ea2b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e7e9b2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e7ea2b`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7d85f`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7db30`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7db4a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7dc74`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7de56`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e028`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e037`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e041`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e08d`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e1a9`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e27d`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e5f2`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e872`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e881`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e890`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e89a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e8a4`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e8f6`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e900`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e90a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e914`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7d85f`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7db30`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7db4a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7dc74`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7de56`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e028`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e037`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e041`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e08d`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e1a9`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e27d`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e5f2`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e872`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e881`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e890`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e89a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e8a4`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e8f6`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e900`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e90a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e7e914`
- `sqlTsEs!?WszFromWsz@@YAPEA_WPEAVIMemObj@@PEB_WPEAH@Z` at `0x101e7e25b`
- `sqlTsEs!?WszFromWsz@@YAPEA_WPEAVIMemObj@@PEB_WPEAH@Z` at `0x101e7e25b`
- `sqlmin!?utgettime@@YAXPEAUSQLDATEBASE@@HPEA_N@Z` at `0x101e7d750`
- `sqlmin!?utgettime@@YAXPEAUSQLDATEBASE@@HPEA_N@Z` at `0x101e7d750`

## string_xrefs

- `0x101e7de9a`: `lastUpdated`
- `0x101e7e68c`: `lastUpdated`
- `0x101e7d941`: `sql\ntdbms\stretch\src\stretchtask.cpp`
- `0x101e7d9d2`: `sql\ntdbms\stretch\src\stretchtask.cpp`
- `0x101e7da06`: `sql\ntdbms\stretch\src\stretchtask.cpp`
- `0x101e7dad3`: `sql\ntdbms\stretch\src\stretchtask.cpp`
- `0x101e7dc45`: `sql\ntdbms\stretch\src\stretchtask.cpp`
- `0x101e7dcc3`: `sql\ntdbms\stretch\src\stretchtask.cpp`
- `0x101e7de2a`: `sql\ntdbms\stretch\src\stretchtask.cpp`
- `0x101e7dffc`: `sql\ntdbms\stretch\src\stretchtask.cpp`
- `0x101e7e05f`: `sql\ntdbms\stretch\src\stretchtask.cpp`
- `0x101e7e17a`: `sql\ntdbms\stretch\src\stretchtask.cpp`
- `0x101e7e3f0`: `sql\ntdbms\stretch\src\stretchtask.cpp`
- `0x101e7e5c6`: `sql\ntdbms\stretch\src\stretchtask.cpp`
- `0x101e7e83e`: `sql\ntdbms\stretch\src\stretchtask.cpp`
- `0x101e7e80f`: `%ls SET XACT_ABORT ON; SET LOCK_TIMEOUT %lu; SET TRANSACTION ISOLATION LEVEL READ COMMITTED; DECLARE @transactionName nvarchar(32) = N'StretchMigration'; BEGIN TRAN @transactionName; DECLARE @checkpointName nvarchar(32) = N'%ls'; SAVE TRAN @checkpointName; IF NOT EXISTS (SELECT 1 FROM sys.objects WHERE  name = '%ls' and type = 'IT') BEGIN SET @numOfRowsMigrated = 0; IF @@TRANCOUNT > 0 AND XACT_STATE() <> 0 BEGIN ROLLBACK TRAN @checkpointName; COMMIT TRAN @transactionName; END RETURN; END IF @fSk`
- `0x101e7dfcd`: `%ls SET XACT_ABORT ON; SET LOCK_TIMEOUT %lu; SET TRANSACTION ISOLATION LEVEL READ COMMITTED;%ls DECLARE @transactionName nvarchar(32) = N'StretchUnmigration'; BEGIN TRAN @transactionName; BEGIN DECLARE @expectedMaxBatchID bigint; DECLARE @maxRemoteBatchID bigint; SELECT @expectedMaxBatchID = ISNULL(GetRemoteDataArchiveBatchID(DB_ID(), %ld, 0, 0 /*forInternalQuery*/), 0); SELECT @maxRemoteBatchID = ISNULL(MAX([batchID--%ld]), 0) FROM %ls; IF (@expectedMaxBatchID > @maxRemoteBatchID) BEGIN SET @nu`

## pseudocode

```c

```
