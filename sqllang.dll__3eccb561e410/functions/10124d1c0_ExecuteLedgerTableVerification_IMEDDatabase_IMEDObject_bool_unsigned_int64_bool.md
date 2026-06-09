# ExecuteLedgerTableVerification(IMEDDatabase *,IMEDObject *,bool,unsigned __int64,bool)

- ea: `0x10124d1c0`
- end: `0x10124f7cc`
- name: `?ExecuteLedgerTableVerification@@YA_NPEAVIMEDDatabase@@PEAVIMEDObject@@_N_K2@Z`
- size: `9740`
- prototype: `bool __fastcall(struct IMEDDatabase *, struct IMEDObject *, bool, unsigned __int64, bool)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x10124f9f0`

## callees

- `0x100401070`
- `0x100401090`
- `0x100401400`
- `0x100401433`
- `0x100403080`
- `0x100407620`
- `0x100407bd0`
- `0x10041154d`
- `0x1004135e0`
- `0x1004223e0`
- `0x100430960`
- `0x10046cda0`
- `0x10046ce40`
- `0x10046cf40`
- `0x10046cf70`
- `0x100471e50`
- `0x10055a5d0`
- `0x10066ed40`
- `0x100670a70`
- `0x100a42fc0`
- `0x100a43170`
- `0x100c17b90`
- `0x100c18b40`
- `0x10124d1c0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10124d2d1`
- `KERNEL32!QueryPerformanceCounter` at `0x10124f1e4`
- `KERNEL32!QueryPerformanceCounter` at `0x10124f4f5`
- `KERNEL32!QueryPerformanceCounter` at `0x10124d2d1`
- `KERNEL32!QueryPerformanceCounter` at `0x10124f1e4`
- `KERNEL32!QueryPerformanceCounter` at `0x10124f4f5`
- `ole32!CoCreateGuid` at `0x10124dca0`
- `ole32!CoCreateGuid` at `0x10124dcc9`
- `ole32!CoCreateGuid` at `0x10124dca0`
- `ole32!CoCreateGuid` at `0x10124dcc9`
- `ole32!StringFromGUID2` at `0x10124dcbc`
- `ole32!StringFromGUID2` at `0x10124dce0`
- `ole32!StringFromGUID2` at `0x10124dcbc`
- `ole32!StringFromGUID2` at `0x10124dce0`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x10124f228`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x10124f59a`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10124d2be`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10124f1d1`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10124f21c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10124f4de`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10124f58e`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x10124ebd3`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x10124ebd3`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10124db0d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10124e97d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10124eb09`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10124db0d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10124e97d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10124eb09`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10124ef9b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10124ef9b`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124d94f`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124dbd2`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124e0d9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124d94f`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124dbd2`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124e0d9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10124db61`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10124eafe`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10124f031`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10124f0ec`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10124f1cb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10124db61`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10124eafe`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10124f031`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10124f0ec`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10124f1cb`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124d47f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124d55a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124d63b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124d7a2`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124d886`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124daac`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124dd5f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124de1c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124dea6`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124df78`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124e24d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124e45d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124e4f2`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124e71c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124d47f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124d55a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124d63b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124d7a2`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124d886`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124daac`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124dd5f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124de1c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124dea6`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124df78`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124e24d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124e45d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124e4f2`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10124e71c`
- `sqldk!SystemThread_TlsIndex` at `0x10124d41a`
- `sqldk!SystemThread_TlsIndex` at `0x10124d4fd`
- `sqldk!SystemThread_TlsIndex` at `0x10124d5df`
- `sqldk!SystemThread_TlsIndex` at `0x10124d73e`
- `sqldk!SystemThread_TlsIndex` at `0x10124d822`
- `sqldk!SystemThread_TlsIndex` at `0x10124d8f9`
- `sqldk!SystemThread_TlsIndex` at `0x10124d96e`
- `sqldk!SystemThread_TlsIndex` at `0x10124da5d`
- `sqldk!SystemThread_TlsIndex` at `0x10124db80`
- `sqldk!SystemThread_TlsIndex` at `0x10124dc07`
- `sqldk!SystemThread_TlsIndex` at `0x10124dcfd`
- `sqldk!SystemThread_TlsIndex` at `0x10124ddb9`
- `sqldk!SystemThread_TlsIndex` at `0x10124de44`
- `sqldk!SystemThread_TlsIndex` at `0x10124df14`
- `sqldk!SystemThread_TlsIndex` at `0x10124e083`
- `sqldk!SystemThread_TlsIndex` at `0x10124e0f4`
- `sqldk!SystemThread_TlsIndex` at `0x10124e184`
- `sqldk!SystemThread_TlsIndex` at `0x10124e1eb`
- `sqldk!SystemThread_TlsIndex` at `0x10124e2c7`
- `sqldk!SystemThread_TlsIndex` at `0x10124e3a4`
- `sqldk!SystemThread_TlsIndex` at `0x10124e3fb`
- `sqldk!SystemThread_TlsIndex` at `0x10124e490`
- `sqldk!SystemThread_TlsIndex` at `0x10124e579`
- `sqldk!SystemThread_TlsIndex` at `0x10124e5c6`
- `sqldk!SystemThread_TlsIndex` at `0x10124e6ba`
- `sqldk!SystemThread_TlsIndex` at `0x10124e7af`
- `sqldk!SystemThread_TlsIndex` at `0x10124e870`
- `sqldk!SystemThread_TlsIndex` at `0x10124e8bd`
- `sqldk!SystemThread_TlsIndex` at `0x10124eb9b`
- `sqldk!SystemThread_TlsIndex` at `0x10124ee55`
- `sqldk!SystemThread_TlsIndex` at `0x10124eeb6`
- `sqldk!SystemThread_TlsIndex` at `0x10124ef00`
- `sqldk!SystemThread_TlsIndex` at `0x10124ef2d`
- `sqldk!SystemThread_TlsIndex` at `0x10124f078`
- `sqldk!SystemThread_TlsIndex` at `0x10124f31e`
- `sqldk!SystemThread_TlsOffset` at `0x10124d423`
- `sqldk!SystemThread_TlsOffset` at `0x10124d506`
- `sqldk!SystemThread_TlsOffset` at `0x10124d5e8`
- `sqldk!SystemThread_TlsOffset` at `0x10124d747`
- `sqldk!SystemThread_TlsOffset` at `0x10124d82b`
- `sqldk!SystemThread_TlsOffset` at `0x10124d902`
- `sqldk!SystemThread_TlsOffset` at `0x10124d977`
- `sqldk!SystemThread_TlsOffset` at `0x10124da66`
- `sqldk!SystemThread_TlsOffset` at `0x10124db89`
- `sqldk!SystemThread_TlsOffset` at `0x10124dc10`
- `sqldk!SystemThread_TlsOffset` at `0x10124dd06`
- `sqldk!SystemThread_TlsOffset` at `0x10124ddc2`
- `sqldk!SystemThread_TlsOffset` at `0x10124de4d`
- `sqldk!SystemThread_TlsOffset` at `0x10124df1d`
- `sqldk!SystemThread_TlsOffset` at `0x10124e08c`
- `sqldk!SystemThread_TlsOffset` at `0x10124e0fd`
- `sqldk!SystemThread_TlsOffset` at `0x10124e18d`
- `sqldk!SystemThread_TlsOffset` at `0x10124e1f4`
- `sqldk!SystemThread_TlsOffset` at `0x10124e2d0`
- `sqldk!SystemThread_TlsOffset` at `0x10124e3ad`
- `sqldk!SystemThread_TlsOffset` at `0x10124e404`
- `sqldk!SystemThread_TlsOffset` at `0x10124e499`
- `sqldk!SystemThread_TlsOffset` at `0x10124e582`
- `sqldk!SystemThread_TlsOffset` at `0x10124e5cf`
- `sqldk!SystemThread_TlsOffset` at `0x10124e6c3`
- `sqldk!SystemThread_TlsOffset` at `0x10124e7b8`
- `sqldk!SystemThread_TlsOffset` at `0x10124e879`
- `sqldk!SystemThread_TlsOffset` at `0x10124e8c6`
- `sqldk!SystemThread_TlsOffset` at `0x10124eba4`
- `sqldk!SystemThread_TlsOffset` at `0x10124ee5e`
- `sqldk!SystemThread_TlsOffset` at `0x10124eebf`
- `sqldk!SystemThread_TlsOffset` at `0x10124ef09`
- `sqldk!SystemThread_TlsOffset` at `0x10124ef36`
- `sqldk!SystemThread_TlsOffset` at `0x10124f081`
- `sqldk!SystemThread_TlsOffset` at `0x10124f327`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124d43e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124d521`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124d603`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124d762`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124d846`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124d91d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124d992`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124da81`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124dba4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124dc2c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124dd21`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124dddd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124de68`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124df36`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e0a7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e118`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e1a6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e20f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e2e9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e3cd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e41f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e4b4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e59b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e5e8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e6de`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e7d1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e892`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e8df`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124ebbd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124f340`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124d43e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124d521`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124d603`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124d762`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124d846`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124d91d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124d992`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124da81`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124dba4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124dc2c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124dd21`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124dddd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124de68`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124df36`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e0a7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e118`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e1a6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e20f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e2e9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e3cd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e41f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e4b4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e59b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e5e8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10124e6de`

## string_xrefs

- `0x10124eb63`: `(@success BIT OUTPUT, @table_id INT, @max_digest_block_id BIGINT, @history_table_id INT)SET NOCOUNT ON	SET @success = 1	DECLARE @transaction_id BIGINT	CREATE TABLE #table_verification_errors (transaction_id BIGINT)	INSERT INTO #table_verification_errors	SELECT ISNULL(table_transaction_id /* transaction ID */, transaction_id)	FROM	(		SELECT			transactions.block_id,			getobjectledgerhash(table_hashes, @table_id) AS database_ledger_hash,			transaction_id,			[%s] /* start transaction ID */ AS table_`
- `0x10124eab3`: `(@success BIT OUTPUT, @table_id INT, @max_digest_block_id BIGINT, @history_table_id INT)SET NOCOUNT ON	SET @success = 1	DECLARE @transaction_id BIGINT	CREATE TABLE #table_verification_errors (transaction_id BIGINT)	INSERT INTO #table_verification_errors	SELECT ISNULL(table_transaction_id /* transaction ID */, transaction_id)	FROM	(		SELECT			transactions.block_id,			getobjectledgerhash(table_hashes, @table_id) AS database_ledger_hash,			transaction_id,			[%s] /* start transaction ID */ AS table_`
- `0x10124ef8d`: `rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
char __fastcall ExecuteLedgerTableVerification(
        struct IMEDDatabase *a1,
        struct IMEDObject *a2,
        char a3,
        unsigned __int64 a4,
        bool a5)
{
  unsigned __int64 v6; // r13
  CSbTransportMgr *QuadPart; // rsi
  __int64 v9; // rbx
  unsigned int v10; // eax
  struct IMEDSchema *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rax
  _QWORD *v14; // rbx
  __int64 v15; // rax
  IMEDName *v17; // rax
  unsigned __int64 v18; // r12
  __int64 v19; // rbx
  __int64 v20; // r10
  unsigned __int64 v21; // rax
  void *v22; // rbx
  __int64 v23; // rax
  IMEDName *v24; // rax
  unsigned __int64 v25; // r15
  __int64 v26; // rbx
  __int64 v27; // r10
  unsigned __int64 v28; // rax
  void *v29; // rbx
  __int64 v30; // rax
  IMEDName *v31; // rax
  unsigned __int64 v32; // rdi
  __int64 v33; // rbx
  __int64 v34; // r10
  unsigned __int64 v35; // rax
  void *v36; // rbx
  __int64 v37; // rax
  unsigned __int64 v38; // r14
  __int64 v39; // rax
  unsigned int v40; // eax
  struct IMEDDatabase *v41; // rdi
  __int64 v42; // r8
  struct IMEDObject *v43; // r13
  __int64 v44; // rbx
  unsigned int v45; // eax
  __int64 v46; // r9
  __int64 (__fastcall ***v47)(_QWORD); // rdi
  IMEDName *v48; // rax
  __int64 v49; // rbx
  __int64 v50; // r10
  unsigned __int64 v51; // rax
  void *v52; // rbx
  __int64 v53; // rax
  IMEDName *v54; // rax
  __int64 v55; // rbx
  __int64 v56; // r10
  unsigned __int64 v57; // rax
  void *v58; // rbx
  __int64 v59; // rax
  __int64 v60; // rbx
  LARGE_INTEGER *v61; // rdx
  wchar_t *v62; // rbx
  __int64 v63; // rdi
  __int64 v64; // rax
  __int64 v65; // rax
  struct IMemObj *v66; // rdi
  __int64 v67; // rbx
  unsigned int v68; // eax
  __int64 v69; // rax
  __int64 v70; // rbx
  __int64 v71; // rdx
  unsigned __int8 v72; // r8
  unsigned __int8 v73; // r9
  int v74; // ebx
  int v75; // edi
  struct __crt_locale_pointers *DefaultLocale; // rax
  int v77; // eax
  __int64 v78; // rbx
  LARGE_INTEGER *v79; // rdx
  wchar_t *v80; // rbx
  __int64 v81; // rdi
  int v82; // edi
  __int64 v83; // r15
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rbx
  __int64 v87; // r10
  unsigned __int64 v88; // rax
  unsigned int v89; // edi
  __int64 v90; // rbx
  __int64 v91; // r10
  unsigned __int64 v92; // rax
  __int64 v93; // rbx
  __int64 v94; // r10
  unsigned __int64 v95; // rax
  unsigned int v96; // ebx
  __int64 v97; // rdi
  __int64 v98; // rcx
  unsigned __int64 v99; // rax
  void *v100; // rbx
  void *v101; // rdi
  unsigned int v102; // r15d
  unsigned int v103; // r12d
  unsigned int v104; // r14d
  struct IMemObj *v105; // r13
  unsigned int v106; // r12d
  unsigned int v107; // esi
  unsigned int v108; // ebx
  __int64 v109; // rax
  __int64 v110; // rax
  __int64 v111; // rax
  int *v112; // r14
  unsigned int v113; // edi
  __int64 v114; // rbx
  __int64 v115; // rdx
  _QWORD *v116; // r15
  __int64 v117; // rbx
  __int64 v118; // rax
  __int64 v119; // rax
  __int64 v120; // rbx
  __int64 v121; // r10
  unsigned __int64 v122; // rax
  void *v123; // r14
  __int64 v124; // rax
  __int64 v125; // rax
  __int64 v126; // rbx
  __int64 v127; // r14
  int v128; // eax
  CObjName *v129; // rcx
  unsigned __int64 v130; // rdi
  wchar_t *v131; // rax
  __int64 v132; // rdx
  __int64 v133; // rbx
  __int64 v134; // r10
  unsigned __int64 v135; // rax
  __int64 v136; // rbx
  __int64 v137; // r10
  unsigned __int64 v138; // rax
  void *v139; // r14
  __int64 v140; // rax
  __int64 v141; // rax
  __int64 v142; // rbx
  __int64 v143; // r14
  unsigned __int64 v144; // rdi
  wchar_t *v145; // rax
  __int64 v146; // rbx
  __int64 v147; // r10
  unsigned __int64 v148; // rax
  __int64 v149; // rax
  __int64 v150; // rax
  wchar_t *v151; // r15
  wchar_t *v152; // r15
  __int64 v153; // rax
  wchar_t *v154; // r14
  struct __crt_locale_pointers *v155; // rax
  int v156; // eax
  struct __crt_locale_pointers *v157; // rax
  int v158; // eax
  __int64 v159; // rbx
  __int64 v160; // rcx
  struct IExecSql *ExecSql; // r15
  int v162; // edi
  struct IMEDObject *v163; // r12
  __int64 v164; // rbx
  unsigned int v165; // r14d
  char v166; // bl
  BaseXact *v167; // rax
  bool v168; // di
  __int64 v169; // rbx
  int *v170; // rax
  int v171; // ebx
  int v172; // ecx
  int v173; // eax
  CSbTransportMgr *v174; // rcx
  unsigned __int64 v175; // rcx
  unsigned __int64 v176; // r12
  unsigned __int64 v177; // r12
  bool v178; // r14
  char v179; // bl
  char v180; // r14
  char v181; // di
  struct IMEDDatabase *v182; // rdi
  __int64 v183; // rbx
  unsigned int v184; // eax
  __int64 v185; // r8
  struct IMEDObject *v186; // rbx
  __int64 v187; // rax
  __int64 v188; // r15
  __int64 v189; // rdi
  __int64 v190; // rcx
  struct IMEDObject *v191; // rdi
  wchar_t *LedgerViewDefinition; // rax
  wchar_t *v193; // r13
  __int64 v194; // rcx
  struct IMEDSchema *v195; // rbx
  __int64 v196; // r15
  __int64 v197; // r14
  int v198; // edi
  _QWORD *v199; // rbx
  __int64 v200; // rax
  unsigned __int64 v201; // rbx
  size_t v202; // r14
  CSbTransportMgr *v203; // rcx
  struct IMEDObject *v204; // rbx
  __int64 v205; // r14
  int v206; // edi
  struct IMEDObject *v207; // r15
  _QWORD *v208; // rbx
  __int64 v209; // rax
  unsigned __int64 v210; // rcx
  unsigned __int64 v211; // rsi
  unsigned __int64 v212; // rsi
  int v213; // [rsp+20h] [rbp-160h]
  wchar_t v214[4]; // [rsp+20h] [rbp-160h]
  int v215; // [rsp+20h] [rbp-160h]
  int v216; // [rsp+20h] [rbp-160h]
  int v217; // [rsp+20h] [rbp-160h]
  wchar_t v218[4]; // [rsp+20h] [rbp-160h]
  int v219; // [rsp+28h] [rbp-158h]
  struct CObjName *v220; // [rsp+28h] [rbp-158h]
  struct CObjName *v221; // [rsp+28h] [rbp-158h]
  struct CObjName *v222; // [rsp+28h] [rbp-158h]
  int v223; // [rsp+28h] [rbp-158h]
  struct CObjName *v224; // [rsp+28h] [rbp-158h]
  struct IMemObj *v225; // [rsp+30h] [rbp-150h]
  struct IMemObj *v226; // [rsp+30h] [rbp-150h]
  struct IMemObj *v227; // [rsp+30h] [rbp-150h]
  unsigned int v229; // [rsp+104h] [rbp-7Ch] BYREF
  char v230; // [rsp+108h] [rbp-78h]
  char v231; // [rsp+109h] [rbp-77h]
  unsigned int v232; // [rsp+10Ch] [rbp-74h] BYREF
  unsigned int v233; // [rsp+110h] [rbp-70h]
  wchar_t *v234; // [rsp+118h] [rbp-68h]
  wchar_t *v235; // [rsp+120h] [rbp-60h]
  unsigned int v236; // [rsp+128h] [rbp-58h] BYREF
  struct IMEDObject *v237; // [rsp+130h] [rbp-50h]
  unsigned int v238; // [rsp+138h] [rbp-48h]
  unsigned int v239; // [rsp+13Ch] [rbp-44h]
  struct IMEDObject *v240; // [rsp+140h] [rbp-40h]
  wchar_t *v241; // [rsp+148h] [rbp-38h]
  unsigned __int64 v242; // [rsp+150h] [rbp-30h]
  CObjName *v243; // [rsp+158h] [rbp-28h]
  wchar_t *v244; // [rsp+160h] [rbp-20h]
  unsigned int v245[2]; // [rsp+168h] [rbp-18h]
  int v246; // [rsp+170h] [rbp-10h] BYREF
  int v247; // [rsp+174h] [rbp-Ch] BYREF
  int v248; // [rsp+178h] [rbp-8h] BYREF
  int v249; // [rsp+17Ch] [rbp-4h] BYREF
  void *v250; // [rsp+180h] [rbp+0h]
  int v251; // [rsp+188h] [rbp+8h] BYREF
  struct IMEDDatabase *v252; // [rsp+190h] [rbp+10h]
  void *v253; // [rsp+198h] [rbp+18h]
  void *v254; // [rsp+1A0h] [rbp+20h]
  void *v255; // [rsp+1A8h] [rbp+28h]
  unsigned __int8 v256; // [rsp+1B0h] [rbp+30h] BYREF
  __int16 v257; // [rsp+1B1h] [rbp+31h]
  char v258; // [rsp+1B3h] [rbp+33h]
  int v259; // [rsp+1B4h] [rbp+34h]
  __int64 v260; // [rsp+1B8h] [rbp+38h]
  int v261; // [rsp+1C0h] [rbp+40h]
  __int64 v262; // [rsp+1C4h] [rbp+44h]
  int v263; // [rsp+1CCh] [rbp+4Ch]
  __int64 v264; // [rsp+1D0h] [rbp+50h] BYREF
  int v265; // [rsp+1D8h] [rbp+58h]
  __int128 v266; // [rsp+1E0h] [rbp+60h]
  CObjName *v267; // [rsp+1F0h] [rbp+70h]
  void *v268; // [rsp+1F8h] [rbp+78h]
  void *v269; // [rsp+200h] [rbp+80h]
  void *v270; // [rsp+208h] [rbp+88h]
  void *v271; // [rsp+210h] [rbp+90h]
  void *v272; // [rsp+218h] [rbp+98h]
  struct IMemObj *v273; // [rsp+220h] [rbp+A0h]
  LARGE_INTEGER PerformanceCount; // [rsp+228h] [rbp+A8h] BYREF
  struct IMEDSchema *v275; // [rsp+230h] [rbp+B0h]
  CSbTransportMgr *v276; // [rsp+238h] [rbp+B8h]
  unsigned int v277; // [rsp+240h] [rbp+C0h]
  LARGE_INTEGER v278; // [rsp+248h] [rbp+C8h] BYREF
  unsigned __int64 v279; // [rsp+250h] [rbp+D0h]
  LARGE_INTEGER v280; // [rsp+258h] [rbp+D8h] BYREF
  __int64 v281; // [rsp+260h] [rbp+E0h] BYREF
  int v282; // [rsp+268h] [rbp+E8h]
  __int64 v283; // [rsp+26Ch] [rbp+ECh]
  int v284; // [rsp+274h] [rbp+F4h]
  int v285; // [rsp+278h] [rbp+F8h]
  __int64 v286; // [rsp+27Ch] [rbp+FCh]
  __int128 v287; // [rsp+288h] [rbp+108h] BYREF
  __int64 v288; // [rsp+298h] [rbp+118h]
  int v289; // [rsp+2A4h] [rbp+124h]
  __int64 v290; // [rsp+2A8h] [rbp+128h]
  void *v291; // [rsp+2B0h] [rbp+130h]
  void *v292; // [rsp+2B8h] [rbp+138h]
  void *v293; // [rsp+2C0h] [rbp+140h]
  unsigned __int64 v294; // [rsp+2C8h] [rbp+148h]
  wchar_t *v295; // [rsp+2D0h] [rbp+150h]
  wchar_t *v296; // [rsp+2D8h] [rbp+158h]
  wchar_t *v297; // [rsp+2E0h] [rbp+160h]
  wchar_t *v298; // [rsp+2E8h] [rbp+168h]
  _QWORD *v299; // [rsp+2F0h] [rbp+170h]
  struct IExecSql *v300; // [rsp+2F8h] [rbp+178h]
  wchar_t *v301; // [rsp+300h] [rbp+180h]
  char v302[24]; // [rsp+308h] [rbp+188h] BYREF
  char v303[8]; // [rsp+320h] [rbp+1A0h] BYREF
  int v304; // [rsp+328h] [rbp+1A8h]
  int v305; // [rsp+330h] [rbp+1B0h]
  _QWORD *v306; // [rsp+338h] [rbp+1B8h]
  char *v307; // [rsp+340h] [rbp+1C0h]
  __int64 v308; // [rsp+348h] [rbp+1C8h]
  _QWORD v309[2]; // [rsp+350h] [rbp+1D0h] BYREF
  char v310; // [rsp+360h] [rbp+1E0h] BYREF
  __int64 v311; // [rsp+570h] [rbp+3F0h]
  __int64 v312; // [rsp+578h] [rbp+3F8h]
  _DWORD v313[2]; // [rsp+580h] [rbp+400h] BYREF
  char v314; // [rsp+588h] [rbp+408h]
  char v315; // [rsp+589h] [rbp+409h]
  __int64 v316; // [rsp+58Ah] [rbp+40Ah]
  int v317; // [rsp+592h] [rbp+412h]
  __int64 v318; // [rsp+596h] [rbp+416h]
  __int16 v319; // [rsp+59Eh] [rbp+41Eh]
  char v320[8]; // [rsp+5A0h] [rbp+420h] BYREF
  int v321; // [rsp+5A8h] [rbp+428h]
  int v322; // [rsp+5B0h] [rbp+430h]
  _QWORD *v323; // [rsp+5B8h] [rbp+438h]
  char *v324; // [rsp+5C0h] [rbp+440h]
  __int64 v325; // [rsp+5C8h] [rbp+448h]
  _QWORD v326[2]; // [rsp+5D0h] [rbp+450h] BYREF
  char v327; // [rsp+5E0h] [rbp+460h] BYREF
  __int64 v328; // [rsp+7F0h] [rbp+670h]
  __int64 v329; // [rsp+7F8h] [rbp+678h]
  _DWORD v330[2]; // [rsp+800h] [rbp+680h] BYREF
  char v331; // [rsp+808h] [rbp+688h]
  bool v332; // [rsp+809h] [rbp+689h]
  unsigned __int64 v333; // [rsp+80Ah] [rbp+68Ah]
  int v334; // [rsp+812h] [rbp+692h]
  unsigned __int64 v335; // [rsp+816h] [rbp+696h]
  char v336; // [rsp+81Eh] [rbp+69Eh]
  char v337; // [rsp+81Fh] [rbp+69Fh]
  char v338[8]; // [rsp+820h] [rbp+6A0h] BYREF
  int v339; // [rsp+828h] [rbp+6A8h]
  int v340; // [rsp+830h] [rbp+6B0h]
  _QWORD *v341; // [rsp+838h] [rbp+6B8h]
  char *v342; // [rsp+840h] [rbp+6C0h]
  __int64 v343; // [rsp+848h] [rbp+6C8h]
  _QWORD v344[2]; // [rsp+850h] [rbp+6D0h] BYREF
  char v345; // [rsp+860h] [rbp+6E0h] BYREF
  __int64 v346; // [rsp+A70h] [rbp+8F0h]
  __int64 v347; // [rsp+A78h] [rbp+8F8h]
  _DWORD v348[2]; // [rsp+A80h] [rbp+900h] BYREF
  char v349; // [rsp+A88h] [rbp+908h]
  _BYTE v350[48]; // [rsp+A90h] [rbp+910h] BYREF
  GUID pguid; // [rsp+AC0h] [rbp+940h] BYREF
  GUID rguid; // [rsp+AD0h] [rbp+950h] BYREF
  _OWORD v353[4]; // [rsp+AE0h] [rbp+960h] BYREF
  __int128 v354; // [rsp+B20h] [rbp+9A0h]
  __int64 v355; // [rsp+B30h] [rbp+9B0h]
  char v356[8]; // [rsp+B40h] [rbp+9C0h] BYREF
  int v357; // [rsp+B48h] [rbp+9C8h] BYREF
  __int128 v358; // [rsp+B50h] [rbp+9D0h]
  int v359; // [rsp+B60h] [rbp+9E0h]
  __int128 v360; // [rsp+B68h] [rbp+9E8h]
  __int128 v361; // [rsp+B78h] [rbp+9F8h]
  int v362; // [rsp+B90h] [rbp+A10h] BYREF
  __int64 v363; // [rsp+B98h] [rbp+A18h]
  __int64 v364; // [rsp+BA0h] [rbp+A20h]
  int v365; // [rsp+BA8h] [rbp+A28h]
  __int128 v366; // [rsp+BB0h] [rbp+A30h]
  __int128 v367; // [rsp+BC0h] [rbp+A40h]
  int v368; // [rsp+BD8h] [rbp+A58h] BYREF
  __int128 v369; // [rsp+BE0h] [rbp+A60h]
  int v370; // [rsp+BF0h] [rbp+A70h]
  __int128 v371; // [rsp+BF8h] [rbp+A78h]
  __int128 v372; // [rsp+C08h] [rbp+A88h]
  int v373; // [rsp+C20h] [rbp+AA0h] BYREF
  __int64 v374; // [rsp+C28h] [rbp+AA8h]
  __int64 v375; // [rsp+C30h] [rbp+AB0h]
  int v376; // [rsp+C38h] [rbp+AB8h]
  __int128 v377; // [rsp+C40h] [rbp+AC0h]
  __int128 v378; // [rsp+C50h] [rbp+AD0h]
  OLECHAR sz[40]; // [rsp+C60h] [rbp+AE0h] BYREF
  OLECHAR v380[40]; // [rsp+CB0h] [rbp+B30h] BYREF
  _BYTE Buf2[1024]; // [rsp+D00h] [rbp+B80h] BYREF

  v290 = -2;
  v279 = a4;
  v6 = (unsigned __int64)a2;
  v240 = a2;
  v252 = a1;
  if ( (dword_102EDCA28 & 0x40) != 0 )
  {
    v339 = 0x10000;
    v340 = 0;
    v341 = v344;
    v342 = &v345;
    v346 = 0;
    v343 = 0;
    v347 = 0;
    v344[0] = v348;
    v344[1] = 9;
    v348[0] = (*(__int64 (__fastcall **)(struct IMEDDatabase *))(*(_QWORD *)a1 + 16LL))(a1);
    v348[1] = (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)v6 + 8LL))(v6);
    v349 = a3;
    XeSqlPkg::ledger_table_verification_started::Publish((XeSqlPkg::ledger_table_verification_started *)v338);
  }
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&PerformanceCount);
    QuadPart = (CSbTransportMgr *)PerformanceCount.QuadPart;
  }
  else
  {
    QuadPart = MEMORY[0x7FFE0008];
  }
  v276 = QuadPart;
  v9 = *(_QWORD *)a1;
  v10 = (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)v6 + 24LL))(v6);
  v11 = (struct IMEDSchema *)(*(__int64 (__fastcall **)(struct IMEDDatabase *, _QWORD, _QWORD, __int64))(v9 + 216))(
                               a1,
                               v10,
                               0,
                               1);
  v275 = v11;
  v273 = (struct IMemObj *)(*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)v6 + 120LL))(v6);
  v237 = 0;
  v272 = 0;
  v271 = 0;
  v12 = (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)v6 + 120LL))(v6);
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v12 + 360LL))(v12, 0, 0);
  v281 = 0;
  v283 = 0;
  v284 = 0;
  v286 = 1;
  v285 = -1;
  v282 = -2;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 40LL))(v13, &v281);
  if ( (v281 & 0x1000) != 0 )
  {
    v14 = (_QWORD *)(*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)v6 + 40LL))(v6);
    v15 = (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)v6 + 40LL))(v6);
    ex_callprint(37438, 16, 1, *(unsigned int *)(v15 + 8), *v14);
    operator delete[](0);
    operator delete[](0);
    return 0;
  }
  v17 = (IMEDName *)(**(__int64 (__fastcall ***)(struct IMEDSchema *))v11)(v11);
  v18 = (unsigned __int64)(int)IMEDName::GetQuotedLengthCb(v17, 0x5Bu) >> 1;
  v19 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v20 = *(_QWORD *)(v19 + 256);
  if ( !v20 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v20 = *(_QWORD *)(v19 + 256);
  }
  v21 = 2LL * (unsigned int)(v18 + 1);
  if ( !is_mul_ok((unsigned int)(v18 + 1), 2u) )
    v21 = -1;
  v22 = operator new[](v21, *(struct IMemObj **)(v20 + 1000), "sql\\ntdbms\\msql\\proc\\specproc.cpp", 23896, 3u);
  v270 = v22;
  v291 = v22;
  v23 = (**(__int64 (__fastcall ***)(struct IMEDSchema *))v11)(v11);
  v251 = 0;
  FAddQuotes(*(const wchar_t **)v23, *(unsigned int *)(v23 + 8), (wchar_t *)v22, 2 * v18, 0x5Bu, &v251);
  *((_WORD *)v22 + (int)((unsigned __int64)v251 >> 1)) = 0;
  v24 = (IMEDName *)(*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)v6 + 40LL))(v6);
  v25 = (unsigned __int64)(int)IMEDName::GetQuotedLengthCb(v24, 0x5Bu) >> 1;
  v242 = v25;
  v26 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v27 = *(_QWORD *)(v26 + 256);
  if ( !v27 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v27 = *(_QWORD *)(v26 + 256);
  }
  v28 = 2LL * (unsigned int)(v25 + 1);
  if ( !is_mul_ok((unsigned int)(v25 + 1), 2u) )
    v28 = -1;
  v29 = operator new[](v28, *(struct IMemObj **)(v27 + 1000), "sql\\ntdbms\\msql\\proc\\specproc.cpp", 23900, 3u);
  v269 = v29;
  v292 = v29;
  v30 = (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)v6 + 40LL))(v6);
  v246 = 0;
  v233 = 2 * v25;
  FAddQuotes(*(const wchar_t **)v30, *(unsigned int *)(v30 + 8), (wchar_t *)v29, 2 * v25, 0x5Bu, &v246);
  *((_WORD *)v29 + (int)((unsigned __int64)v246 >> 1)) = 0;
  v31 = (IMEDName *)(*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)v6 + 40LL))(v6);
  v32 = (unsigned __int64)(int)IMEDName::GetQuotedLengthCb(v31, 0x27u) >> 1;
  v33 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v34 = *(_QWORD *)(v33 + 256);
  if ( !v34 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v34 = *(_QWORD *)(v33 + 256);
  }
  v35 = 2LL * (unsigned int)(v32 + 1);
  if ( !is_mul_ok((unsigned int)(v32 + 1), 2u) )
    v35 = -1;
  v36 = operator new[](v35, *(struct IMemObj **)(v34 + 1000), "sql\\ntdbms\\msql\\proc\\specproc.cpp", 23905, 3u);
  v268 = v36;
  v293 = v36;
  v37 = (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)v6 + 40LL))(v6);
  LODWORD(v38) = 0;
  v247 = 0;
  FAddQuotes(*(const wchar_t **)v37, *(unsigned int *)(v37 + 8), (wchar_t *)v36, 2 * v32, 0x27u, &v247);
  *((_WORD *)v36 + (int)((unsigned __int64)v247 >> 1)) = 0;
  LODWORD(v6) = 0;
  v243 = 0;
  v267 = 0;
  if ( !a3 )
  {
    v39 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v240 + 120LL))(v240);
    v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 696LL))(v39);
    v41 = v252;
    LODWORD(v225) = 0;
    LOBYTE(v219) = 1;
    LOBYTE(v213) = 0;
    LOBYTE(v42) = 1;
    v43 = (struct IMEDObject *)(*(__int64 (__fastcall **)(struct IMEDDatabase *, _QWORD, __int64, _QWORD, int, int))(*(_QWORD *)v252 + 120LL))(
                                 v252,
                                 v40,
                                 v42,
                                 0,
                                 v213,
                                 v219);
    v237 = v43;
    (*(void (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v43 + 120LL))(v43);
    v44 = *(_QWORD *)v41;
    v45 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v43 + 24LL))(v43);
    LOBYTE(v46) = 1;
    v47 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IMEDDatabase *, _QWORD, _QWORD, __int64))(v44 + 216))(
                                              v41,
                                              v45,
                                              0,
                                              v46);
    v48 = (IMEDName *)(**v47)(v47);
    v38 = (unsigned __int64)(int)IMEDName::GetQuotedLengthCb(v48, 0x5Bu) >> 1;
    v241 = (wchar_t *)v38;
    v49 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v50 = *(_QWORD *)(v49 + 256);
    if ( !v50 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v50 = *(_QWORD *)(v49 + 256);
    }
    v51 = 2LL * (unsigned int)(v38 + 1);
    if ( !is_mul_ok((unsigned int)(v38 + 1), 2u) )
      v51 = -1;
    v52 = operator new[](v51, *(struct IMemObj **)(v50 + 1000), "sql\\ntdbms\\msql\\proc\\specproc.cpp", 23926, 3u);
    if ( v52 )
      operator delete[](0);
    v272 = v52;
    v53 = (**v47)(v47);
    v248 = 0;
    FAddQuotes(*(const wchar_t **)v53, *(unsigned int *)(v53 + 8), (wchar_t *)v52, 2 * v38, 0x5Bu, &v248);
    *((_WORD *)v52 + (int)((unsigned __int64)v248 >> 1)) = 0;
    v54 = (IMEDName *)(*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v43 + 40LL))(v43);
    v6 = (unsigned __int64)(int)IMEDName::GetQuotedLengthCb(v54, 0x5Bu) >> 1;
    v55 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v56 = *(_QWORD *)(v55 + 256);
    if ( !v56 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v56 = *(_QWORD *)(v55 + 256);
    }
    v57 = 2LL * (unsigned int)(v6 + 1);
    if ( !is_mul_ok((unsigned int)(v6 + 1), 2u) )
      v57 = -1;
    v58 = operator new[](v57, *(struct IMemObj **)(v56 + 1000), "sql\\ntdbms\\msql\\proc\\specproc.cpp", 23930, 3u);
    if ( v58 )
      operator delete[](0);
    v271 = v58;
    v59 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v237 + 40LL))(v237);
    v249 = 0;
    FAddQuotes(*(const wchar_t **)v59, *(unsigned int *)(v59 + 8), (wchar_t *)v58, 2 * v6, 0x5Bu, &v249);
    *((_WORD *)v58 + (int)((unsigned __int64)v249 >> 1)) = 0;
    v236 = 23936;
    v60 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v61 = *(LARGE_INTEGER **)(v60 + 256);
    if ( !v61 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v61 = *(LARGE_INTEGER **)(v60 + 256);
    }
    PerformanceCount = v61[125];
    v62 = (wchar_t *)operator new(
                       0x50u,
                       (struct IMemObj *)PerformanceCount.QuadPart,
                       "sql\\ntdbms\\msql\\proc\\specproc.cpp",
                       23936,
                       3u);
    v244 = v62;
    if ( v62 )
    {
      v63 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v64 = *(_QWORD *)(v63 + 256);
      if ( !v64 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v64 = *(_QWORD *)(v63 + 256);
      }
      v65 = *(_QWORD *)(v64 + 1000);
      *(_QWORD *)v62 = &CObjName::`vftable';
      *((_QWORD *)v62 + 1) = 0;
      *((_QWORD *)v62 + 2) = 0;
      *((_QWORD *)v62 + 3) = 0;
      *((_QWORD *)v62 + 4) = 0;
      *((_QWORD *)v62 + 5) = 0;
      v62[24] = 0;
      *((_QWORD *)v62 + 7) = 0;
      v62[32] = 0;
      *((_QWORD *)v62 + 9) = v65;
      CObjName::ParseName((CObjName *)v62, L"NULL ", 10);
    }
    else
    {
      v62 = 0;
    }
    v243 = (CObjName *)v62;
    v66 = v273;
    if ( (*(unsigned int (__fastcall **)(struct IMemObj *))(*(_QWORD *)v273 + 800LL))(v273) != -1 )
    {
      v257 = 0;
      v258 = 0;
      v262 = 0;
      v256 = 0;
      v259 = 0;
      v260 = -1;
      v261 = 0;
      v263 = 0;
      v67 = *(_QWORD *)v66;
      v68 = (*(__int64 (__fastcall **)(struct IMemObj *))(*(_QWORD *)v66 + 800LL))(v66);
      v69 = (*(__int64 (__fastcall **)(struct IMemObj *, _QWORD, _QWORD))(v67 + 40))(v66, v68, 0);
      (*(void (__fastcall **)(__int64, unsigned __int8 *))(*(_QWORD *)v69 + 32LL))(v69, &v256);
      v70 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v71 = *(_QWORD *)(v70 + 256);
      if ( !v71 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v71 = *(_QWORD *)(v70 + 256);
      }
      v38 = (unsigned __int64)operator new[](
                                0x7Au,
                                *(struct IMemObj **)(v71 + 1000),
                                "sql\\ntdbms\\msql\\proc\\specproc.cpp",
                                23948,
                                3u);
      v294 = v38;
      v72 = HIBYTE(v261);
      if ( (unsigned __int8)(v256 + 16) <= 1u )
        v73 = byte_10241B7B3[4 * *((unsigned __int8 *)&xsm_rgOrdFromXvt + v256)];
      else
        v73 = HIBYTE(v261);
      if ( (unsigned __int8)(v256 + 16) <= 1u )
        v72 = byte_10241B7B3[4 * *((unsigned __int8 *)&xsm_rgOrdFromXvt + v256)];
      v74 = v73;
      v75 = v72;
      DefaultLocale = GetDefaultLocale();
      LODWORD(v220) = v74;
      *(_DWORD *)v214 = v75;
      v77 = StringCchPrintf_lW(
              (wchar_t *)v38,
              0x3Du,
              L"CONVERT(DATETIME2(%d), SYSMAXDATETIME(CONVERT(SMALLINT, %d)))",
              DefaultLocale,
              *(_QWORD *)v214,
              v220);
      if ( v77 < 0 )
      {
        _mm_lfence();
        LODWORD(v225) = v77;
        LODWORD(v221) = 23955;
        ex_raise(4, 7, 16, 1, "sql\\ntdbms\\msql\\proc\\specproc.cpp", v221);
      }
      v236 = 23957;
      v78 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v79 = *(LARGE_INTEGER **)(v78 + 256);
      if ( !v79 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v79 = *(LARGE_INTEGER **)(v78 + 256);
      }
      PerformanceCount = v79[125];
      v80 = (wchar_t *)operator new(
                         0x50u,
                         (struct IMemObj *)PerformanceCount.QuadPart,
                         "sql\\ntdbms\\msql\\proc\\specproc.cpp",
                         23957,
                         3u);
      v244 = v80;
      if ( v80 )
      {
        v81 = -1;
        do
          ++v81;
        while ( *(_WORD *)(v38 + 2 * v81) );
        v82 = 2 * v81;
        v83 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v84 = *(_QWORD *)(v83 + 256);
        if ( !v84 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v84 = *(_QWORD *)(v83 + 256);
        }
        v85 = *(_QWORD *)(v84 + 1000);
        *(_QWORD *)v80 = &CObjName::`vftable';
        *((_QWORD *)v80 + 1) = 0;
        *((_QWORD *)v80 + 2) = 0;
        *((_QWORD *)v80 + 3) = 0;
        *((_QWORD *)v80 + 4) = 0;
        *((_QWORD *)v80 + 5) = 0;
        v80[24] = 0;
        *((_QWORD *)v80 + 7) = 0;
        v80[32] = 0;
        *((_QWORD *)v80 + 9) = v85;
        CObjName::ParseName((CObjName *)v80, (const wchar_t *)v38, v82);
        LODWORD(v25) = v242;
      }
      else
      {
        v80 = 0;
      }
      v267 = (CObjName *)v80;
      operator delete[]((void *)v38);
      LODWORD(v38) = (_DWORD)v241;
    }
  }
  CoCreateGuid(&pguid);
  StringFromGUID2(&pguid, sz, 39);
  CoCreateGuid(&rguid);
  StringFromGUID2(&rguid, v380, 39);
  v239 = 266241;
  v86 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v87 = *(_QWORD *)(v86 + 256);
  if ( !v87 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v87 = *(_QWORD *)(v86 + 256);
  }
  v88 = 532482;
  if ( !is_mul_ok(0x41001u, 2u) )
    v88 = -1;
  v241 = (wchar_t *)operator new[](
                      v88,
                      *(struct IMemObj **)(v87 + 1000),
                      "sql\\ntdbms\\msql\\proc\\specproc.cpp",
                      23979,
                      3u);
  v295 = v241;
  memset_0(v241, 0, 0x82002u);
  v245[0] = 0;
  v89 = 0;
  v238 = 0;
  if ( !a3 )
  {
    v245[0] = 265532;
    v89 = 265731;
    v238 = 265731;
  }
  v90 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v91 = *(_QWORD *)(v90 + 256);
  if ( !v91 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v91 = *(_QWORD *)(v90 + 256);
  }
  v92 = 2LL * v245[0];
  if ( !is_mul_ok(v245[0], 2u) )
    v92 = -1;
  v234 = (wchar_t *)operator new[](
                      v92,
                      *(struct IMemObj **)(v91 + 1000),
                      "sql\\ntdbms\\msql\\proc\\specproc.cpp",
                      24004,
                      3u);
  v296 = v234;
  memset_0(v234, 0, 2 * v245[0]);
  v93 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v94 = *(_QWORD *)(v93 + 256);
  if ( !v94 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v94 = *(_QWORD *)(v93 + 256);
  }
  v95 = 2LL * v89;
  if ( !is_mul_ok(v89, 2u) )
    v95 = -1;
  v235 = (wchar_t *)operator new[](
                      v95,
                      *(struct IMemObj **)(v94 + 1000),
                      "sql\\ntdbms\\msql\\proc\\specproc.cpp",
                      24008,
                      3u);
  v297 = v235;
  memset_0(v235, 0, 2 * v89);
  if ( a3 )
    v96 = v18 + v233 + v239 + 4312;
  else
    v96 = v239 + v245[0] + v89 + v18 + 520 + 2 * (v18 + 520) + 3056 + 2 * (v25 + v38 + v6);
  v97 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v98 = *(_QWORD *)(v97 + 256);
  if ( !v98 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v98 = *(_QWORD *)(v97 + 256);
  }
  v242 = v96;
  v99 = 2LL * v96;
  if ( !is_mul_ok(v96, 2u) )
    v99 = -1;
  v244 = (wchar_t *)operator new[](
                      v99,
                      *(struct IMemObj **)(v98 + 1000),
                      "sql\\ntdbms\\msql\\proc\\specproc.cpp",
                      24047,
                      3u);
  v298 = v244;
  v100 = 0;
  v255 = 0;
  v250 = 0;
  v253 = 0;
  v101 = 0;
  v254 = 0;
  v102 = 0;
  v236 = 0;
  v103 = 0;
  v232 = 0;
  v104 = 0;
  v229 = 0;
  v233 = 1;
  v105 = v273;
  if ( (*(unsigned int (__fastcall **)(struct IMemObj *, _QWORD))(*(_QWORD *)v273 + 208LL))(v273, 0) )
  {
    _mm_lfence();
    v106 = v238;
    v107 = v245[0];
    v108 = v233;
    while ( 1 )
    {
      memset(v353, 0, sizeof(v353));
      v354 = 0;
      v355 = 0;
      v109 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v240 + 120LL))(v240);
      v110 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v109 + 224LL))(v109, v108, 0);
      (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v110 + 24LL))(v110, v353);
      v111 = (*(__int64 (__fastcall **)(struct IMemObj *, _QWORD, _QWORD))(*(_QWORD *)v105 + 224LL))(v105, v108, 0);
      v112 = (int *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
      v113 = ((unsigned __int64)(int)IMEDName::GetQuotedLengthCb((IMEDName *)v112, 0x5Bu) >> 1) + 1;
      v238 = 24069;
      v114 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v115 = *(_QWORD *)(v114 + 256);
      if ( !v115 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v115 = *(_QWORD *)(v114 + 256);
      }
      v273 = *(struct IMemObj **)(v115 + 1000);
      v116 = operator new(0x50u, v273, "sql\\ntdbms\\msql\\proc\\specproc.cpp", 24069, 3u);
      *(_QWORD *)v245 = v116;
      if ( v116 )
      {
        v117 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v118 = *(_QWORD *)(v117 + 256);
        if ( !v118 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v118 = *(_QWORD *)(v117 + 256);
        }
        v119 = *(_QWORD *)(v118 + 1000);
        *v116 = &CObjName::`vftable';
        v116[1] = 0;
        v116[2] = 0;
        v116[3] = 0;
        v116[4] = 0;
        v116[5] = 0;
        *((_WORD *)v116 + 24) = 0;
        v116[7] = 0;
        *((_WORD *)v116 + 32) = 0;
        v116[9] = v119;
      }
      else
      {
        v116 = 0;
      }
      v299 = v116;
      CObjName::AddPart((CObjName *)v116, *(const wchar_t **)v112, v112[2]);
      if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 256LL) )
        SystemThread::MakeMiniSOSThread(0);
      AppendLedgerColumnName(v241, v239, &v236, 1, (struct CObjName *)v116, 0, v225);
      switch ( (_DWORD)v354 )
      {
        case 8:
          if ( a3 )
            goto LABEL_179;
          v120 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v121 = *(_QWORD *)(v120 + 256);
          if ( !v121 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v121 = *(_QWORD *)(v120 + 256);
          }
          v122 = 2LL * v113;
          if ( !is_mul_ok(v113, 2u) )
            v122 = -1;
          v123 = operator new[](
                   v122,
                   *(struct IMemObj **)(v121 + 1000),
                   "sql\\ntdbms\\msql\\proc\\specproc.cpp",
                   24086,
                   3u);
          if ( v255 != v123 )
            operator delete[](v255);
          v255 = v123;
LABEL_101:
          v124 = (*(__int64 (__fastcall **)(struct IMemObj *, _QWORD, _QWORD))(*(_QWORD *)v105 + 224LL))(v105, v233, 0);
          v125 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
          v126 = v125;
          if ( *(_QWORD *)v125 && 2 * v113 >= (unsigned __int64)*(unsigned int *)(v125 + 8) + 2 )
          {
            _mm_lfence();
            memmove(v123, *(const void **)v125, *(unsigned int *)(v125 + 8));
            *((_WORD *)v123 + ((unsigned __int64)*(unsigned int *)(v126 + 8) >> 1)) = 0;
          }
          if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 256LL) )
            SystemThread::MakeMiniSOSThread(0);
          v127 = v232;
          if ( v232 )
          {
            if ( !&v234[v232] )
            {
              *_errno() = 22;
              goto LABEL_112;
            }
            if ( 2 * (unsigned __int64)(v107 - v232) < 4 )
            {
              memset_0(&v234[v232], 0, 2LL * (v107 - v232));
              *_errno() = 34;
LABEL_112:
              _invalid_parameter_noinfo();
            }
            else
            {
              memmove(&v234[v232], L", ", 4u);
            }
            v127 = (unsigned int)(v127 + 2);
          }
          v128 = CObjName::CbFullName(v243);
          v129 = v243;
          goto LABEL_115;
        case 0xA:
          if ( a3 )
            goto LABEL_179;
          v133 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v134 = *(_QWORD *)(v133 + 256);
          if ( !v134 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v134 = *(_QWORD *)(v133 + 256);
          }
          v135 = 2LL * v113;
          if ( !is_mul_ok(v113, 2u) )
            v135 = -1;
          v123 = operator new[](
                   v135,
                   *(struct IMemObj **)(v134 + 1000),
                   "sql\\ntdbms\\msql\\proc\\specproc.cpp",
                   24115,
                   3u);
          if ( v254 != v123 )
            operator delete[](v254);
          v254 = v123;
          goto LABEL_101;
        case 7:
          v136 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v137 = *(_QWORD *)(v136 + 256);
          if ( !v137 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v137 = *(_QWORD *)(v136 + 256);
          }
          v138 = 2LL * v113;
          if ( !is_mul_ok(v113, 2u) )
            v138 = -1;
          v139 = operator new[](
                   v138,
                   *(struct IMemObj **)(v137 + 1000),
                   "sql\\ntdbms\\msql\\proc\\specproc.cpp",
                   24142,
                   3u);
          if ( v250 != v139 )
            operator delete[](v250);
          v250 = v139;
          v140 = (*(__int64 (__fastcall **)(struct IMemObj *, _QWORD, _QWORD))(*(_QWORD *)v105 + 224LL))(v105, v233, 0);
          v141 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v140 + 16LL))(v140);
          v142 = v141;
          if ( *(_QWORD *)v141 && 2 * v113 >= (unsigned __int64)*(unsigned int *)(v141 + 8) + 2 )
            goto LABEL_136;
          break;
        case 9:
          v146 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v147 = *(_QWORD *)(v146 + 256);
          if ( !v147 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v147 = *(_QWORD *)(v146 + 256);
          }
          v148 = 2LL * v113;
          if ( !is_mul_ok(v113, 2u) )
            v148 = -1;
          v139 = operator new[](
                   v148,
                   *(struct IMemObj **)(v147 + 1000),
                   "sql\\ntdbms\\msql\\proc\\specproc.cpp",
                   24171,
                   3u);
          if ( v253 != v139 )
            operator delete[](v253);
          v253 = v139;
          v149 = (*(__int64 (__fastcall **)(struct IMemObj *, _QWORD, _QWORD))(*(_QWORD *)v105 + 224LL))(v105, v233, 0);
          v141 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v149 + 16LL))(v149);
          v142 = v141;
          if ( *(_QWORD *)v141 && 2 * v113 >= (unsigned __int64)*(unsigned int *)(v141 + 8) + 2 )
          {
LABEL_136:
            _mm_lfence();
            memmove(v139, *(const void **)v141, *(unsigned int *)(v141 + 8));
            *((_WORD *)v139 + ((unsigned __int64)*(unsigned int *)(v142 + 8) >> 1)) = 0;
          }
          break;
        default:
          if ( (v355 & 0x1000000000LL) != 0 )
          {
            if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 256LL) )
              SystemThread::MakeMiniSOSThread(0);
            v127 = v232;
            if ( v232 )
            {
              if ( !&v234[v232] )
              {
                *_errno() = 22;
                goto LABEL_170;
              }
              if ( 2 * (unsigned __int64)(v107 - v232) < 4 )
              {
                memset_0(&v234[v232], 0, 2LL * (v107 - v232));
                *_errno() = 34;
LABEL_170:
                _invalid_parameter_noinfo();
              }
              else
              {
                memmove(&v234[v232], L", ", 4u);
              }
              v127 = (unsigned int)(v127 + 2);
            }
            v128 = CObjName::CbFullName(v267);
            v129 = v267;
LABEL_115:
            v130 = (unsigned __int64)v128 >> 1;
            v131 = CObjName::WsFullName(v129);
            memcpy_s(&v234[v127], 2LL * (v107 - (unsigned int)v127), v131, 2LL * (unsigned int)v130);
            v132 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset;
            v232 = v130 + v127;
            if ( !*(_QWORD *)(v132 + 256) )
              SystemThread::MakeMiniSOSThread(0);
LABEL_178:
            AppendLedgerColumnName(v235, v106, &v229, 1, (struct CObjName *)v116, 0, v225);
          }
          else if ( !a3 )
          {
            if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 256LL) )
              SystemThread::MakeMiniSOSThread(0);
            AppendLedgerColumnName(v234, v107, &v232, 1, (struct CObjName *)v116, 0, v225);
            if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 256LL) )
              SystemThread::MakeMiniSOSThread(0);
            goto LABEL_178;
          }
LABEL_179:
          v104 = v229;
          goto LABEL_180;
      }
      if ( a3 )
        goto LABEL_179;
      if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 256LL) )
        SystemThread::MakeMiniSOSThread(0);
      AppendLedgerColumnName(v234, v107, &v232, 1, (struct CObjName *)v116, 0, v225);
      if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 256LL) )
        SystemThread::MakeMiniSOSThread(0);
      v143 = v229;
      if ( v229 )
      {
        if ( !&v235[v229] )
        {
          *_errno() = 22;
          goto LABEL_148;
        }
        if ( 2 * (unsigned __int64)(v106 - v229) < 4 )
        {
          memset_0(&v235[v229], 0, 2LL * (v106 - v229));
          *_errno() = 34;
LABEL_148:
          _invalid_parameter_noinfo();
        }
        else
        {
          memmove(&v235[v229], L", ", 4u);
        }
        v143 = (unsigned int)(v143 + 2);
      }
      v144 = (unsigned __int64)(int)CObjName::CbFullName(v243) >> 1;
      v145 = CObjName::WsFullName(v243);
      memcpy_s(&v235[v143], 2LL * (v106 - (unsigned int)v143), v145, 2LL * (unsigned int)v144);
      v104 = v144 + v143;
      v229 = v104;
LABEL_180:
      if ( v116 )
        (*(void (__fastcall **)(_QWORD *, __int64))*v116)(v116, 1);
      v108 = ++v233;
      if ( v108 > (*(unsigned int (__fastcall **)(struct IMemObj *, _QWORD))(*(_QWORD *)v105 + 208LL))(v105, 0) )
      {
        v100 = v255;
        v101 = v254;
        v102 = v236;
        v103 = v232;
        QuadPart = v276;
        break;
      }
    }
  }
  v150 = v102;
  v151 = v241;
  v241[v150] = 0;
  if ( !a3 )
  {
    v152 = v234;
    v234[v103] = 0;
    v153 = v104;
    v154 = v235;
    v235[v153] = 0;
    v155 = GetDefaultLocale();
    v156 = StringCchPrintf_lW(
             v244,
             v242,
             L"(@success BIT OUTPUT, @table_id INT, @max_digest_block_id BIGINT, @history_table_id INT)SET NOCOUNT ON\tSET"
              " @success = 1\tDECLARE @transaction_id BIGINT\tCREATE TABLE #table_verification_errors (transaction_id BIG"
              "INT)\tINSERT INTO #table_verification_errors\tSELECT ISNULL(table_transaction_id /* transaction ID */, tra"
              "nsaction_id)\tFROM\t(\t\tSELECT\t\t\ttransactions.block_id,\t\t\tgetobjectledgerhash(table_hashes, @table_"
              "id) AS database_ledger_hash,\t\t\ttransaction_id,\t\t\t[%s] /* start transaction ID */ AS table_transactio"
              "n_id,\t\t\thistory_table.computed_hash\t\tFROM sys.database_ledger_transactions transactions\t\tFULL JOIN\t"
              "\t(\t\t\tSELECT [%s] /* transaction ID */,\t\t\tMERKLE_TREE_AGG(row_hash) WITHIN GROUP (ORDER BY [%s]) /* "
              "seq num */ AS computed_hash\t\t\tFROM\t\t\t(SELECT LEDGERHASH(%s) as row_hash /* current table */, [%s] /*"
              " start_transaction_id */ AS [%s] /* xactID */, [%s] /* start_sequence_number */ AS [%s] /* seq num */ FROM"
              " %s.%s /* current table */ \t\tUNION ALL \t\tSELECT LEDGERHASH(%s) as row_hash /* inserted rows */, [%s] /"
              "* start_transaction_id */ AS [%s] /* xactID */, [%s] /* start_sequence_number */ AS [%s] /* seq num */ FRO"
              "M %s.%s /* history table */ \t\tUNION ALL \t\tSELECT LEDGERHASH(%s) as row_hash /* deleted rows */, [%s] /"
              "* end_transaction_id */ AS [%s] /* xactID */, [%s] /* end_sequence_number */ AS [%s] /* seq num */ FROM %s"
              ".%s /* history table */) joinedTable\t\t\tGROUP BY [%s] /* transaction ID */ \t\t) history_table\t\tON tra"
              "nsactions.transaction_id = history_table.[%s] /* transaction ID */ \t) result\tWHERE\t(block_id IS NULL OR"
              " block_id <= @max_digest_block_id)/*The block falls in the verified range or is null*/ \tAND\t/*Small cave"
              "at, the table transaction id can be NULL if the transaction did not update the table, however, in that cas"
              "e the hash should also be NULL*/ \t(transaction_id IS NULL OR (table_transaction_id IS NULL AND computed_h"
              "ash IS NOT NULL) OR database_ledger_hash != computed_hash OR (database_ledger_hash IS NULL AND computed_ha"
              "sh IS NOT NULL) OR (database_ledger_hash IS NOT NULL AND computed_hash IS NULL))\tDECLARE table_verificati"
              "on CURSOR FOR SELECT * FROM #table_verification_errors\tOPEN table_verification\tFETCH NEXT FROM table_ver"
              "ification INTO @transaction_id\tWHILE @@FETCH_STATUS = 0\t\tBEGIN\t\t/* When the query runs, sys.database_"
              "ledger_transactions may be read first and the user table later, in which case new transactions might be fo"
              "und in the table but not sys.database_ledger_transactions. */\t\t/* Double check if the transaction can no"
              "w be found and if the block ID for it is higher than what we are verifying. */\t\tIF @transaction_id IS NU"
              "LL OR NOT EXISTS (SELECT block_id FROM sys.database_ledger_transactions WHERE transaction_id = @transactio"
              "n_id AND block_id > @max_digest_block_id) \t\tBEGIN \t\t\tSET @success = 0\t\t\tRAISERROR(37371, 16, 1, %s"
              " /* current table */, @transaction_id) WITH LOG\t\tEND \t\tFETCH NEXT FROM table_verification INTO @transa"
              "ction_id\t\tEND\tCLOSE table_verification\tDEALLOCATE table_verification\tSET NOCOUNT OFF ",
             v155,
             sz,
             sz,
             v380,
             v241,
             v250,
             sz,
             v253,
             v380,
             v270,
             v269,
             v152,
             v250,
             sz,
             v253,
             v380,
             v272,
             v271,
             v154,
             v100,
             sz,
             v101,
             v380,
             v272,
             v271,
             sz,
             sz,
             v268);
    if ( v156 >= 0 )
      goto LABEL_190;
    LODWORD(v226) = v156;
    LODWORD(v222) = 24319;
    goto LABEL_187;
  }
  v157 = GetDefaultLocale();
  v158 = StringCchPrintf_lW(
           v244,
           v242,
           L"(@success BIT OUTPUT, @table_id INT, @max_digest_block_id BIGINT, @history_table_id INT)SET NOCOUNT ON\tSET @"
            "success = 1\tDECLARE @transaction_id BIGINT\tCREATE TABLE #table_verification_errors (transaction_id BIGINT)"
            "\tINSERT INTO #table_verification_errors\tSELECT ISNULL(table_transaction_id /* transaction ID */, transacti"
            "on_id)\tFROM\t(\t\tSELECT\t\t\ttransactions.block_id,\t\t\tgetobjectledgerhash(table_hashes, @table_id) AS d"
            "atabase_ledger_hash,\t\t\ttransaction_id,\t\t\t[%s] /* start transaction ID */ AS table_transaction_id,\t\t\t"
            "history_table.computed_hash\t\tFROM sys.database_ledger_transactions transactions\t\tFULL JOIN\t\t(\t\t\tSEL"
            "ECT [%s] /* transaction ID */,\t\t\tMERKLE_TREE_AGG(row_hash) WITHIN GROUP (ORDER BY [%s]) /* seq num */ AS "
            "computed_hash\t\t\tFROM\t\t\t(SELECT LEDGERHASH(%s) as row_hash, [%s] /* start_transaction_id */, [%s] /* st"
            "art_sequence_number */ FROM %s.%s /* current table */) joinedTable\t\t\tGROUP BY [%s] /* transaction ID */ \t"
            "\t) history_table\t\tON transactions.transaction_id = history_table.[%s] /* transaction ID */ \t) result\tWH"
            "ERE\t(block_id IS NULL OR block_id <= @max_digest_block_id)/*The block falls in the verified range or is nul"
            "l*/ \tAND\t/*Small caveat, the table transaction id can be NULL if the transaction did not update the table,"
            " however, in that case the hash should also be NULL*/ \t(transaction_id IS NULL OR (table_transaction_id IS "
            "NULL AND computed_hash IS NOT NULL) OR database_ledger_hash != computed_hash OR (database_ledger_hash IS NUL"
            "L AND computed_hash IS NOT NULL) OR (database_ledger_hash IS NOT NULL AND computed_hash IS NULL))\tDECLARE t"
            "able_verification CURSOR FOR SELECT * FROM #table_verification_errors\tOPEN table_verification\tFETCH NEXT F"
            "ROM table_verification INTO @transaction_id\tWHILE @@FETCH_STATUS = 0\t\tBEGIN\t\t/* When the query runs, sy"
            "s.database_ledger_transactions may be read first and the user table later, in which case new transactions mi"
            "ght be found in the table but not sys.database_ledger_transactions. */\t\t/* Double check if the transaction"
            " can now be found and if the block ID for it is higher than what we are verifying. */\t\tIF @transaction_id "
            "IS NULL OR NOT EXISTS (SELECT block_id FROM sys.database_ledger_transactions WHERE transaction_id = @transac"
            "tion_id AND block_id > @max_digest_block_id) \t\tBEGIN \t\t\tSET @success = 0\t\t\tRAISERROR(37371, 16, 1, %"
            "s /* current table */, @transaction_id) WITH LOG\t\tEND \t\tFETCH NEXT FROM table_verification INTO @transac"
            "tion_id\t\tEND\tCLOSE table_verification\tDEALLOCATE table_verification\tSET NOCOUNT OFF ",
           v157,
           v250,
           v250,
           v253,
           v151,
           v250,
           v253,
           v270,
           v269,
           v250,
           v250,
           v268);
  if ( v158 < 0 )
  {
    LODWORD(v226) = v158;
    LODWORD(v222) = 24279;
LABEL_187:
    _mm_lfence();
    ex_raise(4, 7, 16, 1, "sql\\ntdbms\\msql\\proc\\specproc.cpp", v222, v226);
  }
LABEL_190:
  v159 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v160 = *(_QWORD *)(v159 + 256);
  if ( !v160 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v160 = *(_QWORD *)(v159 + 256);
  }
  ExecSql = CreateExecSql(*(struct IMemObj **)(v160 + 1000), 0);
  v242 = (unsigned __int64)ExecSql;
  v300 = ExecSql;
  (*(void (__fastcall **)(struct IExecSql *, __int64))(*(_QWORD *)ExecSql + 192LL))(ExecSql, 4);
  `eh vector constructor iterator'(
    v356,
    0x48u,
    4u,
    (void (*)(void *))CAutoClearXVariant::CAutoClearXVariant,
    CAutoClearXVariant::~CAutoClearXVariant);
  v162 = 0;
  v357 = 26627;
  v358 = 0;
  v359 = 0;
  v360 = CTypeInfo::tiBit;
  v361 = xmmword_10305AE30;
  LOWORD(v215) = 0;
  (*(void (__fastcall **)(struct IExecSql *, _QWORD, int *, _QWORD, int, int, void *, int))(*(_QWORD *)ExecSql + 208LL))(
    ExecSql,
    0,
    &v357,
    0,
    v215,
    1,
    &CTypeInfo::tiBit,
    2);
  v362 = 14336;
  v363 = 0;
  v364 = 0;
  v365 = 0;
  v366 = CTypeInfo::tiI4NotNull;
  v367 = xmmword_102F21D40;
  v163 = v240;
  LODWORD(v363) = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v240 + 8LL))(v240);
  LOWORD(v216) = 0;
  (*(void (__fastcall **)(struct IExecSql *, __int64, int *, _QWORD, int, _DWORD, void *, int))(*(_QWORD *)ExecSql
                                                                                              + 208LL))(
    ExecSql,
    1,
    &v362,
    0,
    v216,
    0,
    &CTypeInfo::tiI4NotNull,
    1);
  v368 = 32512;
  v370 = 0;
  v371 = CTypeInfo::tiI8;
  v372 = xmmword_102EF7B88;
  v369 = v279;
  LOWORD(v217) = 0;
  (*(void (__fastcall **)(struct IExecSql *, __int64, int *, _QWORD, int, _DWORD, void *, int))(*(_QWORD *)ExecSql
                                                                                              + 208LL))(
    ExecSql,
    2,
    &v368,
    0,
    v217,
    0,
    &CTypeInfo::tiI8,
    1);
  v373 = 14336;
  v374 = 0;
  v375 = 0;
  v376 = 0;
  v377 = CTypeInfo::tiI4;
  v378 = xmmword_102EF7C30;
  if ( a3 )
    LOBYTE(v373) = 3;
  else
    LODWORD(v374) = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v237 + 8LL))(v237);
  v227 = (struct IMemObj *)&CTypeInfo::tiI4;
  v223 = 0;
  HIBYTE(v218[0]) = 0;
  (*(void (__fastcall **)(struct IExecSql *, __int64, int *))(*(_QWORD *)ExecSql + 208LL))(ExecSql, 3, &v373);
  (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)ExecSql + 96LL))(ExecSql);
  (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)ExecSql + 48LL))(ExecSql);
  v164 = **(_QWORD **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset)
                     + 64LL);
  v165 = *(_DWORD *)(v164 + 76);
  v277 = v165;
  *(_DWORD *)(v164 + 76) = 5;
  CDbAndSetOptsImplImport::SetIsolationLevel(5);
  *(_BYTE *)v164 |= 0x10u;
  v287 = 0;
  v288 = 0;
  v289 = 0;
  AutoOverrideMsqlXact::InitializeAndOverride(
    (AutoOverrideMsqlXact *)&v287,
    *(struct CMsqlXactManager **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                              + SystemThread_TlsIndex)
                                            + SystemThread_TlsOffset
                                            + 32LL)
                                + 72LL));
  v264 = 0;
  v266 = 0;
  v265 = 1;
  *(_QWORD *)&v266 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + SystemThread_TlsIndex)
                                           + SystemThread_TlsOffset)
                               + 144LL);
  v166 = *(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset)
                  + 152LL);
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v266 + 464LL))(v266) )
  {
    if ( v166 && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v266 + 488LL))(v266) )
      utassert_fail(
        1u,
        "rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()",
        "automsqlxact.cpp",
        235,
        0);
    (*(void (__fastcall **)(_QWORD, __int64, __int64, char *))(*(_QWORD *)v266 + 232LL))(v266, 2, 1, (char *)&v264 + 4);
    v265 = 1;
    LODWORD(v264) = 3;
  }
  else
  {
    LOBYTE(v227) = 0;
    LOBYTE(v162) = v166 != 0;
    (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64, __int64, int, int, struct IMemObj *, _QWORD, int))(*(_QWORD *)v266 + 8LL))(
      v266,
      L"ExecuteLedgerTableVerification",
      60,
      1,
      2,
      1,
      v227,
      0,
      v162);
    LODWORD(v264) = 1;
  }
  v167 = (BaseXact *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v266 + 432LL))(v266);
  if ( !BaseXact::IsSnapshotXact(v167) )
    ex_raise(374, 98, 16, 1);
  v168 = (*(unsigned int (__fastcall **)(struct IExecSql *, wchar_t *, __int64))(*(_QWORD *)ExecSql + 8LL))(
           ExecSql,
           v244,
           88) != 0;
  if ( (_DWORD)v264 )
    CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v264, 0);
  AutoOverrideMsqlXact::~AutoOverrideMsqlXact((AutoOverrideMsqlXact *)&v287);
  v169 = **(_QWORD **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset)
                     + 64LL);
  *(_DWORD *)(v169 + 76) = v165;
  CDbAndSetOptsImplImport::SetIsolationLevel(v165);
  *(_BYTE *)v169 |= 0x10u;
  if ( !v168 )
  {
    v170 = (int *)(*(__int64 (__fastcall **)(struct IExecSql *, char *))(*(_QWORD *)ExecSql + 176LL))(ExecSql, v302);
    v171 = *v170;
    v172 = v170[4];
    v173 = (unsigned __int16)*v170;
    if ( v172 != 1 )
      v171 = v173;
    if ( v171 == 3617 )
      ex_raise(373, 42, 16, 2);
    if ( (dword_102EDCA28 & 0x80u) != 0 )
    {
      v304 = 0x10000;
      v305 = 0;
      v306 = v309;
      v307 = &v310;
      v311 = 0;
      v308 = 0;
      v312 = 0;
      v309[0] = v313;
      v309[1] = 32;
      v313[0] = (*(__int64 (__fastcall **)(struct IMEDDatabase *))(*(_QWORD *)v252 + 16LL))(v252);
      v313[1] = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v163 + 8LL))(v163);
      v314 = a3;
      v315 = 0;
      v316 = 0;
      v317 = v171;
      v318 = 0;
      v319 = 257;
      XeSqlPkg::ledger_table_verification_completed::Publish((XeSqlPkg::ledger_table_verification_completed *)v303);
    }
    *(_DWORD *)v218 = v171;
    ex_raise(374, 36, 16, 1, *(_QWORD *)v218);
  }
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&v280);
    v174 = (CSbTransportMgr *)v280.QuadPart;
  }
  else
  {
    v174 = MEMORY[0x7FFE0008];
  }
  if ( v174 < QuadPart )
  {
    v175 = 0;
  }
  else
  {
    v175 = v174 - QuadPart;
    if ( v175 == -1 )
    {
      v176 = -1;
      goto LABEL_223;
    }
  }
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
    v176 = 1000 * v175 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
  else
    v176 = v175 / 0x2710;
LABEL_223:
  v177 = v176 / 0x3E8;
  v178 = (_BYTE)v358 != 0;
  v179 = FCheckIndexesForLedger(v240);
  v231 = v179;
  if ( v237 )
  {
    v179 &= FCheckIndexesForLedger(v237);
    v231 = v179;
  }
  v180 = v179 & v178;
  v181 = 1;
  if ( !a5 )
  {
    v182 = v252;
    v183 = *(_QWORD *)v252;
    v184 = (*(__int64 (__fastcall **)(struct IMemObj *))(*(_QWORD *)v105 + 880LL))(v105);
    LODWORD(v227) = 0;
    LOBYTE(v223) = 1;
    LOBYTE(v218[0]) = 0;
    LOBYTE(v185) = 1;
    v186 = (struct IMEDObject *)(*(__int64 (__fastcall **)(struct IMEDDatabase *, _QWORD, __int64, _QWORD, _DWORD, int, struct IMemObj *, _DWORD))(v183 + 120))(
                                  v182,
                                  v184,
                                  v185,
                                  0,
                                  *(_DWORD *)v218,
                                  v223,
                                  v227,
                                  0);
    v237 = v186;
    v187 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v186 + 168LL))(v186);
    v188 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v187 + 80LL))(v187);
    (*(void (__fastcall **)(struct IMemObj *, _BYTE *))(*(_QWORD *)v105 + 16LL))(v105, v350);
    v189 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v190 = *(_QWORD *)(v189 + 256);
    if ( !v190 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v190 = *(_QWORD *)(v189 + 256);
    }
    v191 = v240;
    LedgerViewDefinition = GetLedgerViewDefinition(
                             0,
                             v186,
                             v240,
                             v275,
                             v252,
                             *(struct IMemObj **)(v190 + 1000),
                             1,
                             (v350[40] & 8) != 0,
                             0,
                             0,
                             0,
                             0,
                             0);
    v193 = LedgerViewDefinition;
    v301 = LedgerViewDefinition;
    v194 = -1;
    do
      ++v194;
    while ( LedgerViewDefinition[v194] );
    v195 = (struct IMEDSchema *)(unsigned int)(2 * v194);
    v196 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v188 + 32LL))(v188, 0);
    v275 = (struct IMEDSchema *)(**(__int64 (__fastcall ***)(__int64))v196)(v196);
    if ( v195 == v275 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v196 + 8LL))(v196);
      v201 = 0;
      v230 = v180;
      while ( 1 )
      {
        v181 = 1;
        if ( v201 >= (unsigned __int64)v275 )
        {
LABEL_236:
          v180 = v230;
          goto LABEL_237;
        }
        _mm_lfence();
        v202 = (*(unsigned int (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v196 + 16LL))(v196, Buf2, 1024);
        if ( memcmp_0(&v193[v201 >> 1], Buf2, v202) )
          break;
        v201 += v202;
        if ( (unsigned int)v202 < 0x400 )
          goto LABEL_236;
      }
      _mm_lfence();
      v204 = v240;
      v205 = *(_QWORD *)(*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v240 + 40LL))(v240);
      v206 = *(_DWORD *)((*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v204 + 40LL))(v204) + 8);
      v207 = v237;
      v208 = (_QWORD *)(*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v237 + 40LL))(v237);
      v209 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v207 + 40LL))(v207);
      LODWORD(v224) = v206;
      ex_callprint(37499, 16, 2, *(unsigned int *)(v209 + 8), *v208, v224, v205);
      v181 = 0;
      v180 = 0;
    }
    else
    {
      v197 = *(_QWORD *)(*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v191 + 40LL))(v191);
      v198 = *(_DWORD *)((*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v191 + 40LL))(v191) + 8);
      v199 = (_QWORD *)(*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v237 + 40LL))(v237);
      v200 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v237 + 40LL))(v237);
      LODWORD(v224) = v198;
      ex_callprint(37499, 16, 1, *(unsigned int *)(v200 + 8), *v199, v224, v197);
      v181 = 0;
      v180 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v196 + 8LL))(v196);
    }
LABEL_237:
    operator delete[](v193);
    ExecSql = (struct IExecSql *)v242;
    v179 = v231;
  }
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&v278);
    v203 = (CSbTransportMgr *)v278.QuadPart;
  }
  else
  {
    v203 = MEMORY[0x7FFE0008];
  }
  if ( v203 < QuadPart )
  {
    v210 = 0;
LABEL_246:
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
      v211 = 1000 * v210 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
    else
      v211 = v210 / 0x2710;
    goto LABEL_249;
  }
  v210 = v203 - QuadPart;
  if ( v210 != -1 )
    goto LABEL_246;
  v211 = -1;
LABEL_249:
  v212 = v211 / 0x3E8;
  if ( (dword_102EDCA28 & 0x80u) != 0 )
  {
    v321 = 0x10000;
    v322 = 0;
    v323 = v326;
    v324 = &v327;
    v328 = 0;
    v325 = 0;
    v329 = 0;
    v326[0] = v330;
    v326[1] = 32;
    v330[0] = (*(__int64 (__fastcall **)(struct IMEDDatabase *))(*(_QWORD *)v252 + 16LL))(v252);
    v330[1] = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v240 + 8LL))(v240);
    v331 = a3;
    v332 = v180 != 0;
    v333 = v212;
    v334 = 0;
    v335 = v177;
    v336 = v179;
    v337 = v181;
    XeSqlPkg::ledger_table_verification_completed::Publish((XeSqlPkg::ledger_table_verification_completed *)v320);
  }
  `eh vector destructor iterator'(v356, 0x48u, 4u, CAutoClearXVariant::~CAutoClearXVariant);
  (*(void (__fastcall **)(struct IExecSql *, __int64))(*(_QWORD *)ExecSql + 224LL))(ExecSql, 1);
  operator delete[](v254);
  operator delete[](v253);
  operator delete[](v250);
  operator delete[](v255);
  operator delete[](v244);
  operator delete[](v235);
  operator delete[](v234);
  operator delete[](v241);
  if ( v267 )
    (**(void (__fastcall ***)(CObjName *, __int64))v267)(v267, 1);
  if ( v243 )
    (**(void (__fastcall ***)(CObjName *, __int64))v243)(v243, 1);
  operator delete[](v268);
  operator delete[](v269);
  operator delete[](v270);
  operator delete[](v271);
  operator delete[](v272);
  return v180;
}

```

## disassembly

```asm
0x10124d1c0  push    rbp
0x10124d1c2  push    rsi
0x10124d1c3  push    rdi
0x10124d1c4  push    r12
0x10124d1c6  push    r13
0x10124d1c8  push    r14
0x10124d1ca  push    r15
0x10124d1cc  lea     rbp, [rsp-0F90h]
0x10124d1d4  mov     eax, 1110h
0x10124d1d9  call    _alloca_probe
0x10124d1de  sub     rsp, rax
0x10124d1e1  mov     [rbp+0FC0h+var_E98], 0FFFFFFFFFFFFFFFEh
0x10124d1ec  mov     [rsp+1140h+arg_10], rbx
0x10124d1f4  mov     rax, cs:__security_cookie
0x10124d1fb  xor     rax, rsp
0x10124d1fe  mov     [rbp+0FC0h+var_40], rax
0x10124d205  mov     [rbp+0FC0h+var_EF0], r9
0x10124d20c  movzx   ebx, r8b
0x10124d210  mov     [rbp+0FC0h+var_1040], bl
0x10124d213  mov     r13, rdx
0x10124d216  mov     [rbp+0FC0h+var_1000], rdx
0x10124d21a  mov     rdi, rcx
0x10124d21d  mov     [rbp+0FC0h+var_FB0], rcx
0x10124d221  xor     r15d, r15d
0x10124d224  lea     r14d, [r15+1]
0x10124d228  test    byte ptr cs:dword_102EDCA28, 40h
0x10124d22f  jz      loc_10124D2BE
0x10124d235  mov     [rbp+0FC0h+var_918], 10000h
0x10124d23f  mov     [rbp+0FC0h+var_910], r15d
0x10124d246  lea     rax, [rbp+0FC0h+var_8F0]
0x10124d24d  mov     [rbp+0FC0h+var_908], rax
0x10124d254  lea     rax, [rbp+0FC0h+var_8E0]
0x10124d25b  mov     [rbp+0FC0h+var_900], rax
0x10124d262  mov     [rbp+0FC0h+var_6D0], r15
0x10124d269  mov     [rbp+0FC0h+var_8F8], r15
0x10124d270  mov     [rbp+0FC0h+var_6C8], r15
0x10124d277  lea     rax, [rbp+0FC0h+var_6C0]
0x10124d27e  mov     [rbp+0FC0h+var_8F0], rax
0x10124d285  mov     [rbp+0FC0h+var_8E8], 9
0x10124d290  mov     rax, [rcx]
0x10124d293  call    qword ptr [rax+10h]
0x10124d296  mov     [rbp+0FC0h+var_6C0], eax
0x10124d29c  mov     rax, [r13+0]
0x10124d2a0  mov     rcx, r13
0x10124d2a3  call    qword ptr [rax+8]
0x10124d2a6  mov     [rbp+0FC0h+var_6BC], eax
0x10124d2ac  mov     [rbp+0FC0h+var_6B8], bl
0x10124d2b2  lea     rcx, [rbp+0FC0h+var_920]; this
0x10124d2b9  call    ?Publish@ledger_table_verification_started@XeSqlPkg@@QEAAXXZ; XeSqlPkg::ledger_table_verification_started::Publish(void)
0x10124d2be  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10124d2c5  cmp     [rax], r15d
0x10124d2c8  jz      short loc_10124D2E0
0x10124d2ca  lea     rcx, [rbp+0FC0h+PerformanceCount]; lpPerformanceCount
0x10124d2d1  call    cs:__imp_QueryPerformanceCounter
0x10124d2d7  mov     rsi, qword ptr [rbp+0FC0h+PerformanceCount]
0x10124d2de  jmp     short loc_10124D2E8
0x10124d2e0  mov     rsi, ds:7FFE0008h
0x10124d2e8  mov     [rbp+0FC0h+var_F08], rsi
0x10124d2ef  mov     rbx, [rdi]
0x10124d2f2  mov     rax, [r13+0]
0x10124d2f6  mov     rcx, r13
0x10124d2f9  call    qword ptr [rax+18h]
0x10124d2fc  mov     edx, eax
0x10124d2fe  movzx   r9d, r14b
0x10124d302  xor     r8d, r8d
0x10124d305  mov     rcx, rdi
0x10124d308  call    qword ptr [rbx+0D8h]
0x10124d30e  mov     rdi, rax
0x10124d311  mov     [rbp+0FC0h+var_F10], rax
0x10124d318  mov     rdx, [r13+0]
0x10124d31c  mov     rcx, r13
0x10124d31f  call    qword ptr [rdx+78h]
0x10124d322  mov     [rbp+0FC0h+var_F20], rax
0x10124d329  mov     [rbp+0FC0h+var_1010], r15
0x10124d32d  mov     [rbp+0FC0h+var_F28], r15
0x10124d334  mov     [rbp+0FC0h+var_F30], r15
0x10124d33b  mov     rdx, [r13+0]
0x10124d33f  mov     rcx, r13
0x10124d342  call    qword ptr [rdx+78h]
0x10124d345  mov     r9, [rax]
0x10124d348  xor     r8d, r8d
0x10124d34b  xor     edx, edx
0x10124d34d  mov     rcx, rax
0x10124d350  call    qword ptr [r9+168h]
0x10124d357  mov     [rbp+0FC0h+var_EE0], r15
0x10124d35e  mov     [rbp+0FC0h+var_ED4], r15
0x10124d365  mov     [rbp+0FC0h+var_ECC], r15d
0x10124d36c  mov     [rbp+0FC0h+var_EC4], 1
0x10124d377  mov     [rbp+0FC0h+var_EC8], 0FFFFFFFFh
0x10124d381  mov     [rbp+0FC0h+var_ED8], 0FFFFFFFEh
0x10124d38b  mov     r8, [rax]
0x10124d38e  lea     rdx, [rbp+0FC0h+var_EE0]
0x10124d395  mov     rcx, rax
0x10124d398  call    qword ptr [r8+28h]
0x10124d39c  test    byte ptr [rbp+0FC0h+var_EE0+1], 10h
0x10124d3a3  jz      short loc_10124D3F3
0x10124d3a5  mov     rax, [r13+0]
0x10124d3a9  mov     rcx, r13
0x10124d3ac  call    qword ptr [rax+28h]
0x10124d3af  mov     rbx, rax
0x10124d3b2  mov     rdx, [r13+0]
0x10124d3b6  mov     rcx, r13
0x10124d3b9  call    qword ptr [rdx+28h]
0x10124d3bc  mov     rcx, [rbx]
0x10124d3bf  mov     qword ptr [rsp+1140h+var_1120], rcx
0x10124d3c4  mov     r9d, [rax+8]
0x10124d3c8  mov     r8d, r14d; int
0x10124d3cb  mov     edx, 10h; int
0x10124d3d0  mov     ecx, 923Eh; int
0x10124d3d5  call    ?ex_callprint@@YAXHHHZZ; ex_callprint(int,int,int,...)
0x10124d3da  nop
0x10124d3db  xor     ecx, ecx
0x10124d3dd  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10124d3e3  nop
0x10124d3e4  xor     ecx, ecx
0x10124d3e6  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10124d3ec  xor     al, al
0x10124d3ee  jmp     loc_10124F7A2
0x10124d3f3  mov     ebx, 5Bh ; '['
0x10124d3f8  mov     rax, [rdi]
0x10124d3fb  mov     rcx, rdi
0x10124d3fe  call    qword ptr [rax]
0x10124d400  mov     rcx, rax; this
0x10124d403  movzx   edx, bx; wchar_t
0x10124d406  call    ?GetQuotedLengthCb@IMEDName@@QEBAH_W@Z; IMEDName::GetQuotedLengthCb(wchar_t)
0x10124d40b  movsxd  r12, eax
0x10124d40e  shr     r12, 1
0x10124d411  mov     rdx, gs:58h
0x10124d41a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10124d421  mov     ecx, [rax]
0x10124d423  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10124d42a  mov     ebx, [rax]
0x10124d42c  add     rbx, [rdx+rcx*8]
0x10124d430  mov     r10, [rbx+100h]
0x10124d437  test    r10, r10
0x10124d43a  jnz     short loc_10124D44B
0x10124d43c  xor     ecx, ecx
0x10124d43e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10124d444  mov     r10, [rbx+100h]
0x10124d44b  lea     ecx, [r12+1]
0x10124d450  mov     eax, 2
0x10124d455  mul     rcx
0x10124d458  mov     r14, 0FFFFFFFFFFFFFFFFh
0x10124d45f  cmovo   rax, r14
0x10124d463  mov     byte ptr [rsp+1140h+var_1120], 3
0x10124d468  mov     r9d, 5D58h
0x10124d46e  lea     r8, aSqlNtdbmsMsqlP_21; "sql\\ntdbms\\msql\\proc\\specproc.cpp"
0x10124d475  mov     rdx, [r10+3E8h]
0x10124d47c  mov     rcx, rax
0x10124d47f  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10124d485  mov     rbx, rax
0x10124d488  mov     [rbp+0FC0h+var_F38], rax
0x10124d48f  mov     [rbp+0FC0h+var_E90], rax
0x10124d496  mov     rdx, [rdi]
0x10124d499  mov     rcx, rdi
0x10124d49c  call    qword ptr [rdx]
0x10124d49e  mov     [rbp+0FC0h+var_FB8], r15d
0x10124d4a2  lea     r9d, [r12+r12]; int
0x10124d4a6  lea     rcx, [rbp+0FC0h+var_FB8]
0x10124d4aa  mov     [rsp+1140h+var_1118], rcx; int *
0x10124d4af  mov     edi, 5Bh ; '['
0x10124d4b4  mov     [rsp+1140h+var_1120], di; wchar_t
0x10124d4b9  mov     r8, rbx; wchar_t *
0x10124d4bc  mov     edx, [rax+8]; Size
0x10124d4bf  mov     rcx, [rax]; Src
0x10124d4c2  call    ?FAddQuotes@@YA_NPEFB_WHPEA_WH_WPEAH@Z; FAddQuotes(wchar_t const *,int,wchar_t *,int,wchar_t,int *)
0x10124d4c7  movsxd  rax, [rbp+0FC0h+var_FB8]
0x10124d4cb  shr     rax, 1
0x10124d4ce  cdqe
0x10124d4d0  mov     [rbx+rax*2], r15w
0x10124d4d5  mov     rax, [r13+0]
0x10124d4d9  mov     rcx, r13
0x10124d4dc  call    qword ptr [rax+28h]
0x10124d4df  mov     rcx, rax; this
0x10124d4e2  movzx   edx, di; wchar_t
0x10124d4e5  call    ?GetQuotedLengthCb@IMEDName@@QEBAH_W@Z; IMEDName::GetQuotedLengthCb(wchar_t)
0x10124d4ea  movsxd  r15, eax
0x10124d4ed  shr     r15, 1
0x10124d4f0  mov     [rbp+0FC0h+var_FF0], r15
0x10124d4f4  mov     rdx, gs:58h
0x10124d4fd  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10124d504  mov     ecx, [rax]
0x10124d506  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10124d50d  mov     ebx, [rax]
0x10124d50f  add     rbx, [rdx+rcx*8]
0x10124d513  mov     r10, [rbx+100h]
0x10124d51a  test    r10, r10
0x10124d51d  jnz     short loc_10124D52E
0x10124d51f  xor     ecx, ecx
0x10124d521  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10124d527  mov     r10, [rbx+100h]
0x10124d52e  lea     ecx, [r15+1]
0x10124d532  mov     eax, 2
0x10124d537  mul     rcx
0x10124d53a  cmovo   rax, r14
0x10124d53e  mov     byte ptr [rsp+1140h+var_1120], 3
0x10124d543  mov     r9d, 5D5Ch
0x10124d549  lea     r8, aSqlNtdbmsMsqlP_21; "sql\\ntdbms\\msql\\proc\\specproc.cpp"
0x10124d550  mov     rdx, [r10+3E8h]
0x10124d557  mov     rcx, rax
0x10124d55a  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10124d560  mov     rbx, rax
0x10124d563  mov     [rbp+0FC0h+var_F40], rax
0x10124d56a  mov     [rbp+0FC0h+var_E88], rax
0x10124d571  mov     rdx, [r13+0]
0x10124d575  mov     rcx, r13
0x10124d578  call    qword ptr [rdx+28h]
0x10124d57b  xor     edi, edi
0x10124d57d  mov     [rbp+0FC0h+var_FD0], edi
0x10124d580  lea     ecx, [r15+r15]
0x10124d584  mov     [rbp+0FC0h+var_1030], ecx
0x10124d587  lea     rdx, [rbp+0FC0h+var_FD0]
0x10124d58b  mov     [rsp+1140h+var_1118], rdx; int *
0x10124d590  mov     edx, 5Bh ; '['
0x10124d595  mov     [rsp+1140h+var_1120], dx; wchar_t
0x10124d59a  mov     r9d, ecx; int
0x10124d59d  mov     r8, rbx; wchar_t *
0x10124d5a0  mov     edx, [rax+8]; Size
0x10124d5a3  mov     rcx, [rax]; Src
0x10124d5a6  call    ?FAddQuotes@@YA_NPEFB_WHPEA_WH_WPEAH@Z; FAddQuotes(wchar_t const *,int,wchar_t *,int,wchar_t,int *)
0x10124d5ab  movsxd  rax, [rbp+0FC0h+var_FD0]
0x10124d5af  shr     rax, 1
0x10124d5b2  cdqe
0x10124d5b4  mov     [rbx+rax*2], di
0x10124d5b8  lea     ebx, [rdi+27h]
0x10124d5bb  mov     rax, [r13+0]
0x10124d5bf  mov     rcx, r13
0x10124d5c2  call    qword ptr [rax+28h]
0x10124d5c5  mov     rcx, rax; this
0x10124d5c8  movzx   edx, bx; wchar_t
0x10124d5cb  call    ?GetQuotedLengthCb@IMEDName@@QEBAH_W@Z; IMEDName::GetQuotedLengthCb(wchar_t)
0x10124d5d0  movsxd  rdi, eax
0x10124d5d3  shr     rdi, 1
0x10124d5d6  mov     rdx, gs:58h
0x10124d5df  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10124d5e6  mov     ecx, [rax]
0x10124d5e8  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10124d5ef  mov     ebx, [rax]
0x10124d5f1  add     rbx, [rdx+rcx*8]
0x10124d5f5  mov     r10, [rbx+100h]
0x10124d5fc  test    r10, r10
0x10124d5ff  jnz     short loc_10124D610
0x10124d601  xor     ecx, ecx
0x10124d603  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10124d609  mov     r10, [rbx+100h]
0x10124d610  lea     ecx, [rdi+1]
0x10124d613  mov     eax, 2
0x10124d618  mul     rcx
0x10124d61b  cmovo   rax, r14
0x10124d61f  mov     byte ptr [rsp+1140h+var_1120], 3
0x10124d624  mov     r9d, 5D61h
0x10124d62a  lea     r8, aSqlNtdbmsMsqlP_21; "sql\\ntdbms\\msql\\proc\\specproc.cpp"
0x10124d631  mov     rdx, [r10+3E8h]
0x10124d638  mov     rcx, rax
0x10124d63b  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10124d641  mov     rbx, rax
0x10124d644  mov     [rbp+0FC0h+var_F48], rax
0x10124d648  mov     [rbp+0FC0h+var_E80], rax
0x10124d64f  mov     rdx, [r13+0]
0x10124d653  mov     rcx, r13
0x10124d656  call    qword ptr [rdx+28h]
0x10124d659  xor     r14d, r14d
0x10124d65c  mov     [rbp+0FC0h+var_FCC], r14d
0x10124d660  lea     r9d, [rdi+rdi]; int
0x10124d664  lea     rcx, [rbp+0FC0h+var_FCC]
0x10124d668  mov     [rsp+1140h+var_1118], rcx; int *
0x10124d66d  mov     ecx, 27h ; '''
0x10124d672  mov     [rsp+1140h+var_1120], cx; wchar_t
0x10124d677  mov     r8, rbx; wchar_t *
0x10124d67a  mov     edx, [rax+8]; Size
0x10124d67d  mov     rcx, [rax]; Src
0x10124d680  call    ?FAddQuotes@@YA_NPEFB_WHPEA_WH_WPEAH@Z; FAddQuotes(wchar_t const *,int,wchar_t *,int,wchar_t,int *)
0x10124d685  movsxd  rax, [rbp+0FC0h+var_FCC]
0x10124d689  shr     rax, 1
0x10124d68c  cdqe
0x10124d68e  mov     [rbx+rax*2], r14w
0x10124d693  xor     ebx, ebx
0x10124d695  mov     r13d, ebx
0x10124d698  mov     [rbp+0FC0h+var_FE8], rbx
0x10124d69c  mov     [rbp+0FC0h+var_F50], rbx
0x10124d6a0  cmp     [rbp+0FC0h+var_1040], bl
0x10124d6a3  jnz     loc_10124DC99
0x10124d6a9  mov     rcx, [rbp+0FC0h+var_1000]
0x10124d6ad  mov     rax, [rcx]
0x10124d6b0  call    qword ptr [rax+78h]
0x10124d6b3  mov     rdx, [rax]
0x10124d6b6  mov     rcx, rax
0x10124d6b9  call    qword ptr [rdx+2B8h]
0x10124d6bf  mov     rdi, [rbp+0FC0h+var_FB0]
0x10124d6c3  mov     r10, [rdi]
0x10124d6c6  mov     dword ptr [rsp+1140h+var_1108], ebx
0x10124d6ca  mov     dword ptr [rsp+1140h+var_1110], ebx; struct IMemObj *
0x10124d6ce  mov     byte ptr [rsp+1140h+var_1118], 1
0x10124d6d3  mov     byte ptr [rsp+1140h+var_1120], bl
0x10124d6d7  xor     r9d, r9d
0x10124d6da  mov     r8b, 1
0x10124d6dd  mov     edx, eax
0x10124d6df  mov     rcx, rdi
0x10124d6e2  call    qword ptr [r10+78h]
0x10124d6e6  mov     r13, rax
  ... truncated ...
```
