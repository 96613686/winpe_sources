# CStmtAlterDB::ChangeStateOption(CCompExecCtxtStmt const &,CMsqlExecContext const *)

- ea: `0x10129a860`
- end: `0x10129e954`
- name: `?ChangeStateOption@CStmtAlterDB@@QEBAXAEBVCCompExecCtxtStmt@@PEBVCMsqlExecContext@@@Z`
- size: `16628`
- prototype: `void __fastcall(CStmtAlterDB *__hidden this, const struct CCompExecCtxtStmt *, const struct CMsqlExecContext *)`
- caller_count: `1`
- callee_count: `56`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x101293060`

## callees

- `0x100401070`
- `0x100401090`
- `0x1004012d0`
- `0x100401340`
- `0x100401433`
- `0x100409cb0`
- `0x10040aaa0`
- `0x1004135e0`
- `0x1004223e0`
- `0x100536250`
- `0x10055a5d0`
- `0x1006d7fb0`
- `0x1006d99f0`
- `0x1008bba20`
- `0x1009617d0`
- `0x100a54ea0`
- `0x100a55050`
- `0x100bc2640`
- `0x100bc28b0`
- `0x100ccf470`
- `0x100d4e1e0`
- `0x100d4e4d0`
- `0x100d69b40`
- `0x100d69cd0`
- `0x1010efc20`
- `0x101147010`
- `0x101174c30`
- `0x1011d09b0`
- `0x10127f150`
- `0x101292fa0`
- `0x10129a500`
- `0x10129a740`
- `0x10129a860`
- `0x10129ea20`
- `0x10129f0e0`
- `0x10129f1e0`
- `0x10129f690`
- `0x10129f810`
- `0x1012a0390`
- `0x1012a04b0`
- `0x1012a05d0`
- `0x1012a11d0`
- `0x1012a2720`
- `0x1012a2930`
- `0x1012a3dc0`
- `0x101405280`
- `0x1014e2f80`
- `0x1014e3060`
- `0x1014e3230`
- `0x1014e3310`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x10129c132`
- `KERNEL32!GetTickCount` at `0x10129c313`
- `KERNEL32!GetTickCount` at `0x10129c424`
- `KERNEL32!GetTickCount` at `0x10129c584`
- `KERNEL32!GetTickCount` at `0x10129c695`
- `KERNEL32!GetTickCount` at `0x10129c834`
- `KERNEL32!GetTickCount` at `0x10129c93d`
- `KERNEL32!GetTickCount` at `0x10129caa8`
- `KERNEL32!GetTickCount` at `0x10129c132`
- `KERNEL32!GetTickCount` at `0x10129c313`
- `KERNEL32!GetTickCount` at `0x10129c424`
- `KERNEL32!GetTickCount` at `0x10129c584`
- `KERNEL32!GetTickCount` at `0x10129c695`
- `KERNEL32!GetTickCount` at `0x10129c834`
- `KERNEL32!GetTickCount` at `0x10129c93d`
- `KERNEL32!GetTickCount` at `0x10129caa8`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x10129ab6e`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x10129b248`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x10129e3d0`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10129c071`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10129cecb`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10129d0a7`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10129e8ff`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x10129a957`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129aa85`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129c0a7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129d0d5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129d105`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129d1ec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129e2e6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129aa85`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129c0a7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129d0d5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129d105`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129d1ec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10129e2e6`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10129e8ca`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10129e8ca`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129abe9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129ac3c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129ad0e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129ad7f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129aebf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129afa6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129b014`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129b113`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129b566`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129b5e3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129b623`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129b69d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129b988`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129b9c9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129ba36`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129bae0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129bb2f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129bbd6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129bc36`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129bcd4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129bd68`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129be10`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129be74`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129be9d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129c11a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129c2e9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129c80a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129ca7e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129cc07`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129cc2e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129cc91`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129d61c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129d6a9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129d887`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129db9b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129dc38`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129dc82`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129dd2a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129defd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129df89`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129e049`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129abe9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129ac3c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129ad0e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129ad7f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129aebf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129afa6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129b014`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129b113`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129b566`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129b5e3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129b623`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129b69d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129b988`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129b9c9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129ba36`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129bae0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129bb2f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129bbd6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129bc36`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129bcd4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129bd68`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129be10`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129be74`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129be9d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129c11a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129c2e9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129c80a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129ca7e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129cc07`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129cc2e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129cc91`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129d61c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129d6a9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129d887`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129db9b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129dc38`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129dc82`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129dd2a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129defd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129df89`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10129e049`
- `sqldk!SystemThread_TlsIndex` at `0x10129a9dd`
- `sqldk!SystemThread_TlsIndex` at `0x10129aa16`
- `sqldk!SystemThread_TlsIndex` at `0x10129ab23`
- `sqldk!SystemThread_TlsIndex` at `0x10129ac4b`
- `sqldk!SystemThread_TlsIndex` at `0x10129b3f1`
- `sqldk!SystemThread_TlsIndex` at `0x10129b4c6`
- `sqldk!SystemThread_TlsIndex` at `0x10129b91d`
- `sqldk!SystemThread_TlsIndex` at `0x10129bebd`
- `sqldk!SystemThread_TlsIndex` at `0x10129bf37`
- `sqldk!SystemThread_TlsIndex` at `0x10129c22d`
- `sqldk!SystemThread_TlsIndex` at `0x10129c51f`
- `sqldk!SystemThread_TlsIndex` at `0x10129cfd6`
- `sqldk!SystemThread_TlsIndex` at `0x10129e233`
- `sqldk!SystemThread_TlsIndex` at `0x10129e26c`
- `sqldk!SystemThread_TlsIndex` at `0x10129e385`
- `sqldk!SystemThread_TlsIndex` at `0x10129e65d`
- `sqldk!SystemThread_TlsIndex` at `0x10129e7db`
- `sqldk!SystemThread_TlsIndex` at `0x10129e892`
- `sqldk!SystemThread_TlsOffset` at `0x10129a9e6`
- `sqldk!SystemThread_TlsOffset` at `0x10129aa1f`
- `sqldk!SystemThread_TlsOffset` at `0x10129ab2c`
- `sqldk!SystemThread_TlsOffset` at `0x10129ac5c`
- `sqldk!SystemThread_TlsOffset` at `0x10129b3fa`
- `sqldk!SystemThread_TlsOffset` at `0x10129b4cf`
- `sqldk!SystemThread_TlsOffset` at `0x10129b926`
- `sqldk!SystemThread_TlsOffset` at `0x10129bec6`
- `sqldk!SystemThread_TlsOffset` at `0x10129bf40`
- `sqldk!SystemThread_TlsOffset` at `0x10129c236`
- `sqldk!SystemThread_TlsOffset` at `0x10129c528`
- `sqldk!SystemThread_TlsOffset` at `0x10129cfdf`
- `sqldk!SystemThread_TlsOffset` at `0x10129e23c`
- `sqldk!SystemThread_TlsOffset` at `0x10129e275`
- `sqldk!SystemThread_TlsOffset` at `0x10129e38e`
- `sqldk!SystemThread_TlsOffset` at `0x10129e666`
- `sqldk!SystemThread_TlsOffset` at `0x10129e7e4`
- `sqldk!SystemThread_TlsOffset` at `0x10129e89b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10129ab45`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10129b415`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10129bf5b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10129e3a7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10129e681`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10129e8b4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10129ab45`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10129b415`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10129bf5b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10129e3a7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10129e681`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10129e8b4`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10129b4fd`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10129b4fd`
- `sqlmin!?GetTardisDbId@DWFidoTxCtx@@QEAAGPEAVIFidoGLMController@@@Z` at `0x10129ae1d`
- `sqlmin!?GetTardisDbId@DWFidoTxCtx@@QEAAGPEAVIFidoGLMController@@@Z` at `0x10129ae1d`
- `sqlmin!?SetRelStat@DBTABLE@@QEAAXJ@Z` at `0x10129d37f`
- `sqlmin!?SetRelStat@DBTABLE@@QEAAXJ@Z` at `0x10129d37f`
- `sqlmin!?FSystemDatabase@@YA_NPEB_WKK_N@Z` at `0x10129bc1b`
- `sqlmin!?FSystemDatabase@@YA_NPEB_WKK_N@Z` at `0x10129d814`
- `sqlmin!?FSystemDatabase@@YA_NPEB_WKK_N@Z` at `0x10129bc1b`
- `sqlmin!?FSystemDatabase@@YA_NPEB_WKK_N@Z` at `0x10129d814`
- `sqlmin!?ErrorIsCDBAllowed@DBMgr@@SAHW4CDB_ALLOWED_TYPE@@W4CDB_ALLOWED_ERROR@@KPEB_W_NPEAVBaseXact@@@Z` at `0x10129dd55`
- `sqlmin!?ErrorIsCDBAllowed@DBMgr@@SAHW4CDB_ALLOWED_TYPE@@W4CDB_ALLOWED_ERROR@@KPEB_W_NPEAVBaseXact@@@Z` at `0x10129dd55`
- `sqlmin!?FGetFidoGLMController@@YA_NAEAV?$CAutoRefc@VIFidoGLMController@@@@K@Z` at `0x10129adc3`
- `sqlmin!?FGetFidoGLMController@@YA_NAEAV?$CAutoRefc@VIFidoGLMController@@@@K@Z` at `0x10129adc3`
- `sqlmin!?lockdb@@YA?AW4LCK_RESULT@@KW4EDBRefType@@W4LCK_MODE@@KI@Z` at `0x10129af34`
- `sqlmin!?lockdb@@YA?AW4LCK_RESULT@@KW4EDBRefType@@W4LCK_MODE@@KI@Z` at `0x10129b70b`
- `sqlmin!?lockdb@@YA?AW4LCK_RESULT@@KW4EDBRefType@@W4LCK_MODE@@KI@Z` at `0x10129af34`
- `sqlmin!?lockdb@@YA?AW4LCK_RESULT@@KW4EDBRefType@@W4LCK_MODE@@KI@Z` at `0x10129b70b`
- `sqlmin!?unlockdb@@YAXKW4EDBRefType@@W4LCK_MODE@@I@Z` at `0x10129b8cd`
- `sqlmin!?unlockdb@@YAXKW4EDBRefType@@W4LCK_MODE@@I@Z` at `0x10129ce6d`
- `sqlmin!?unlockdb@@YAXKW4EDBRefType@@W4LCK_MODE@@I@Z` at `0x10129e7ac`
- `sqlmin!?unlockdb@@YAXKW4EDBRefType@@W4LCK_MODE@@I@Z` at `0x10129b8cd`
- `sqlmin!?unlockdb@@YAXKW4EDBRefType@@W4LCK_MODE@@I@Z` at `0x10129ce6d`
- `sqlmin!?unlockdb@@YAXKW4EDBRefType@@W4LCK_MODE@@I@Z` at `0x10129e7ac`
- `sqlmin!?GetFFtSql@@YAAEAVIFFtSql@@XZ` at `0x10129d95c`
- `sqlmin!?GetFFtSql@@YAAEAVIFFtSql@@XZ` at `0x10129daa0`
- `sqlmin!?GetFFtSql@@YAAEAVIFFtSql@@XZ` at `0x10129ddcb`
- `sqlmin!?GetFFtSql@@YAAEAVIFFtSql@@XZ` at `0x10129dddd`
- `sqlmin!?GetFFtSql@@YAAEAVIFFtSql@@XZ` at `0x10129e206`
- `sqlmin!?GetFFtSql@@YAAEAVIFFtSql@@XZ` at `0x10129e4f6`
- `sqlmin!?GetFFtSql@@YAAEAVIFFtSql@@XZ` at `0x10129e544`
- `sqlmin!?GetFFtSql@@YAAEAVIFFtSql@@XZ` at `0x10129d95c`

## string_xrefs

- `0x10129aa7b`: `rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()`
- `0x10129e2dc`: `rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=25 #try_helpers=1
void __fastcall CStmtAlterDB::ChangeStateOption(
        CStmtAlterDB *this,
        const struct CCompExecCtxtStmt *a2,
        const struct CMsqlExecContext *a3)
{
  struct CCompExecCtxt *v3; // r15
  int (*v5)(int, int, int, int, char *); // rax
  bool v6; // zf
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rbx
  unsigned int v11; // esi
  __int64 v12; // r8
  unsigned int TardisDbId; // r14d
  unsigned int v14; // eax
  char v15; // al
  int v16; // ecx
  int v17; // ecx
  __int64 DBTABLE; // rbx
  __int64 v19; // rax
  __int64 v20; // r13
  __int64 v21; // rcx
  __int64 v22; // rdx
  unsigned int v23; // ebx
  __int64 v24; // r13
  __int64 v25; // rcx
  __int64 v26; // r15
  __int64 v27; // r14
  unsigned int v28; // esi
  const wchar_t *v29; // rax
  unsigned int v30; // eax
  unsigned int SEStatFromDbRegAttr; // eax
  __int16 v32; // r15
  unsigned int v33; // r14d
  int AvailabilityFromStatus; // esi
  __int64 v35; // r8
  __int64 v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rsi
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // rax
  struct CSessionTraceFlags **v42; // rax
  struct CSessionTraceFlags *v43; // rcx
  const wchar_t *v44; // rbx
  DBTABLE *v45; // rcx
  const wchar_t *v46; // rax
  int v47; // r15d
  __int64 v48; // rcx
  const wchar_t *v49; // rsi
  char v50; // si
  struct CCompExecCtxt *v51; // rbx
  __int64 v52; // rcx
  char v53; // al
  int v54; // ecx
  __int64 v55; // r8
  unsigned __int16 MasterDbId; // ax
  unsigned __int16 v57; // ax
  int v58; // eax
  int v59; // ecx
  const wchar_t *v60; // rax
  __int64 v61; // rcx
  unsigned __int16 v62; // ax
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v64; // rcx
  _DWORD *v65; // rsi
  __int64 v66; // rbx
  __int64 v67; // rax
  __int64 v68; // rbx
  __int64 v69; // rsi
  __int64 v70; // rbx
  __int64 v71; // rax
  int v72; // eax
  DWORD TickCount; // ebx
  signed int v74; // r8d
  DWORD v75; // eax
  struct CCompExecCtxt *v76; // r15
  DWORD v77; // ebx
  DWORD v78; // eax
  DWORD v79; // ebx
  signed int v80; // r8d
  DWORD v81; // eax
  DWORD v82; // ebx
  signed int v83; // r8d
  DWORD v84; // eax
  unsigned __int8 v85; // dl
  struct CCompExecCtxt *v86; // rbx
  struct IMetadataAccess *v87; // rsi
  __int64 v88; // rcx
  char v89; // cl
  unsigned __int8 v90; // al
  _OWORD *v91; // rcx
  _OWORD *v92; // rax
  __int64 v93; // rdx
  struct IMetadataAccess *v94; // rbx
  struct CCompExecCtxt *v95; // r14
  __int64 v96; // rcx
  __int64 v97; // rdx
  __int64 v98; // rcx
  __int64 v99; // rax
  unsigned int v100; // r14d
  DBTABLE *v101; // r15
  int v102; // edx
  unsigned int REStatFromDbRegAttr; // eax
  __int64 v104; // rdx
  __int64 v105; // rcx
  struct IFidoGLMController *FidoGLMController; // rax
  __int64 v107; // rdx
  _BYTE *v108; // rcx
  __int64 v109; // rax
  __int64 v110; // rdx
  _BYTE *v111; // rcx
  __int64 v112; // rax
  struct IFidoGLMController *v113; // rax
  char v114; // r8
  __int64 v115; // r9
  __int64 v116; // rdx
  __int64 v117; // r9
  int v118; // eax
  char v119; // r9
  char v120; // r9
  struct CChangeQDSDDLInfo *v121; // rdx
  char v122; // al
  char v123; // cl
  __int64 v124; // r8
  DBTABLE *v125; // rcx
  struct StretchDbDDLInfo *v126; // r8
  char v127; // r8
  bool v128; // al
  char v129; // cl
  __int64 v130; // r8
  __int64 v131; // r8
  __int64 v132; // r8
  __int64 v133; // r8
  __int64 v134; // r8
  const wchar_t *v135; // rax
  __int64 v136; // rcx
  char v137; // r8
  void (__fastcall ***v138)(_QWORD, _QWORD, _BYTE *, _QWORD); // rbx
  struct IFFtSql *FFtSql; // rax
  __int64 v140; // rbx
  struct IFFtSql *v141; // rbx
  __int64 v142; // rax
  __int64 v143; // rdx
  __int64 v144; // rcx
  char v145; // r15
  const struct CCompExecCtxtStmt *v146; // rcx
  struct CAutoMsqlXact *k; // rdx
  int v148; // ebx
  _DWORD *v149; // rax
  int v150; // edx
  __int64 v151; // rax
  struct IFFtSql *v152; // rax
  struct IFFtSql *v153; // rbx
  __int64 v154; // rax
  __int64 v155; // rax
  struct BaseXact *v156; // rax
  __int64 v157; // r8
  __int64 v158; // r13
  unsigned int v159; // r14d
  unsigned int v160; // esi
  int v161; // ebx
  struct IFFtSql *v162; // rax
  char v163; // bl
  __int64 v164; // rbx
  __int64 v165; // rcx
  __int64 v166; // r15
  __int64 v167; // rbx
  struct IFFtSql *v168; // rbx
  __int64 v169; // rax
  struct IFFtSql *v170; // rbx
  __int64 v171; // rax
  __int64 v172; // r9
  __int64 v173; // rbx
  __int64 v174; // rax
  __int64 v175; // rbx
  __int64 v176; // rax
  bool v177; // bl
  unsigned int v178; // ecx
  __int64 v179; // rbx
  struct Worker *v180; // rcx
  struct IFTCatList *v181; // [rsp+20h] [rbp-2BA8h]
  struct IFTCatList *v182; // [rsp+20h] [rbp-2BA8h]
  struct IFTCatList *v183; // [rsp+20h] [rbp-2BA8h]
  struct IFTCatList *v184; // [rsp+20h] [rbp-2BA8h]
  struct IFTCatList *v185; // [rsp+20h] [rbp-2BA8h]
  int v186; // [rsp+20h] [rbp-2BA8h]
  struct IFTCatList *v187; // [rsp+20h] [rbp-2BA8h]
  struct Worker *v188; // [rsp+28h] [rbp-2BA0h]
  struct IMetadataAccess *v189; // [rsp+30h] [rbp-2B98h]
  struct IMetadataAccess *v190; // [rsp+30h] [rbp-2B98h]
  int v191; // [rsp+88h] [rbp-2B40h]
  char v192; // [rsp+C0h] [rbp-2B08h]
  unsigned __int8 v193; // [rsp+C1h] [rbp-2B07h]
  unsigned int v194; // [rsp+C4h] [rbp-2B04h]
  unsigned int v195; // [rsp+C8h] [rbp-2B00h]
  char v196; // [rsp+D0h] [rbp-2AF8h]
  unsigned int *v197; // [rsp+D8h] [rbp-2AF0h]
  unsigned __int8 v198; // [rsp+E0h] [rbp-2AE8h]
  unsigned int v199; // [rsp+E4h] [rbp-2AE4h] BYREF
  int v200; // [rsp+E8h] [rbp-2AE0h]
  unsigned int v201; // [rsp+ECh] [rbp-2ADCh]
  char v202; // [rsp+F0h] [rbp-2AD8h]
  char v203; // [rsp+F1h] [rbp-2AD7h]
  char v204; // [rsp+F2h] [rbp-2AD6h]
  int v205; // [rsp+F4h] [rbp-2AD4h]
  int v206; // [rsp+F8h] [rbp-2AD0h]
  int v207; // [rsp+FCh] [rbp-2ACCh]
  int v208; // [rsp+100h] [rbp-2AC8h]
  struct CCompExecCtxt *v209; // [rsp+108h] [rbp-2AC0h]
  __int64 v210; // [rsp+110h] [rbp-2AB8h] BYREF
  int v211; // [rsp+118h] [rbp-2AB0h]
  __int128 v212; // [rsp+120h] [rbp-2AA8h]
  int v213; // [rsp+130h] [rbp-2A98h]
  struct IMetadataAccess *v214; // [rsp+138h] [rbp-2A90h]
  struct CCompExecCtxt *v215; // [rsp+140h] [rbp-2A88h]
  char v216; // [rsp+148h] [rbp-2A80h]
  char v217; // [rsp+149h] [rbp-2A7Fh]
  char v218; // [rsp+14Ah] [rbp-2A7Eh]
  unsigned __int8 v219; // [rsp+14Bh] [rbp-2A7Dh]
  char v220; // [rsp+14Ch] [rbp-2A7Ch]
  char v221; // [rsp+14Dh] [rbp-2A7Bh]
  char v222; // [rsp+14Eh] [rbp-2A7Ah]
  char v224; // [rsp+150h] [rbp-2A78h]
  int v225; // [rsp+154h] [rbp-2A74h]
  struct IMetadataAccess *v226; // [rsp+158h] [rbp-2A70h]
  char v227; // [rsp+160h] [rbp-2A68h]
  struct IFidoGLMController *v228; // [rsp+168h] [rbp-2A60h] BYREF
  int v229; // [rsp+170h] [rbp-2A58h]
  int v230; // [rsp+174h] [rbp-2A54h] BYREF
  int v231; // [rsp+178h] [rbp-2A50h]
  int v232; // [rsp+17Ch] [rbp-2A4Ch]
  struct BaseXact *v233; // [rsp+180h] [rbp-2A48h]
  struct IFTCatList *v234; // [rsp+188h] [rbp-2A40h] BYREF
  __int64 v235; // [rsp+190h] [rbp-2A38h]
  DWORD v236; // [rsp+198h] [rbp-2A30h]
  DWORD v237; // [rsp+19Ch] [rbp-2A2Ch]
  int v238; // [rsp+1A0h] [rbp-2A28h]
  int v239; // [rsp+1A4h] [rbp-2A24h]
  int v240; // [rsp+1A8h] [rbp-2A20h] BYREF
  int v241; // [rsp+1ACh] [rbp-2A1Ch]
  __int64 v242; // [rsp+1B0h] [rbp-2A18h]
  __int64 v243; // [rsp+1B8h] [rbp-2A10h]
  __int16 v244; // [rsp+1C0h] [rbp-2A08h]
  __int16 v245; // [rsp+1C8h] [rbp-2A00h]
  __int16 v246; // [rsp+1D0h] [rbp-29F8h]
  __int16 v247; // [rsp+1D8h] [rbp-29F0h]
  __int16 v248; // [rsp+1E0h] [rbp-29E8h]
  struct IMetadataAccess *v249; // [rsp+1E8h] [rbp-29E0h]
  __int64 v250; // [rsp+1F0h] [rbp-29D8h]
  __int16 v251; // [rsp+1F8h] [rbp-29D0h]
  __int64 v252; // [rsp+200h] [rbp-29C8h]
  __int16 v253; // [rsp+208h] [rbp-29C0h]
  __int64 v254; // [rsp+210h] [rbp-29B8h]
  void **v255; // [rsp+218h] [rbp-29B0h] BYREF
  __int64 v256; // [rsp+220h] [rbp-29A8h]
  __int64 v257; // [rsp+228h] [rbp-29A0h] BYREF
  int v258; // [rsp+230h] [rbp-2998h]
  int v259; // [rsp+234h] [rbp-2994h]
  int v260; // [rsp+238h] [rbp-2990h]
  int v261; // [rsp+23Ch] [rbp-298Ch]
  int v262; // [rsp+240h] [rbp-2988h]
  int v263; // [rsp+244h] [rbp-2984h]
  DWFidoTxCtx *DWFidoTxCtx; // [rsp+248h] [rbp-2980h] BYREF
  __int64 v265; // [rsp+250h] [rbp-2978h]
  int v266; // [rsp+258h] [rbp-2970h] BYREF
  char v267; // [rsp+25Ch] [rbp-296Ch]
  void **v268; // [rsp+260h] [rbp-2968h] BYREF
  __int64 v269; // [rsp+268h] [rbp-2960h]
  __int64 v270; // [rsp+270h] [rbp-2958h] BYREF
  __int64 v271; // [rsp+278h] [rbp-2950h]
  int v272; // [rsp+280h] [rbp-2948h]
  int v273; // [rsp+284h] [rbp-2944h]
  __int16 v274; // [rsp+288h] [rbp-2940h]
  int v275; // [rsp+290h] [rbp-2938h]
  int v276; // [rsp+294h] [rbp-2934h]
  __int16 v277; // [rsp+298h] [rbp-2930h]
  __int64 v278; // [rsp+2A0h] [rbp-2928h]
  int v279; // [rsp+2A8h] [rbp-2920h]
  __int64 v280; // [rsp+2B0h] [rbp-2918h]
  const struct CCompExecCtxtStmt *v281; // [rsp+2B8h] [rbp-2910h]
  CStmtAlterDB *v282; // [rsp+2C0h] [rbp-2908h]
  int v283; // [rsp+2C8h] [rbp-2900h]
  CSessionLockList **v284; // [rsp+2D0h] [rbp-28F8h]
  __int64 v285; // [rsp+2D8h] [rbp-28F0h]
  __int64 v286; // [rsp+2E0h] [rbp-28E8h]
  _BYTE *i; // [rsp+2E8h] [rbp-28E0h]
  __int64 v288; // [rsp+2F0h] [rbp-28D8h]
  _BYTE *j; // [rsp+2F8h] [rbp-28D0h]
  __int64 v290; // [rsp+300h] [rbp-28C8h]
  __int64 v291; // [rsp+308h] [rbp-28C0h]
  __int128 v292; // [rsp+320h] [rbp-28A8h] BYREF
  __int64 v293; // [rsp+330h] [rbp-2898h]
  int v294; // [rsp+33Ch] [rbp-288Ch]
  _WORD *v295; // [rsp+340h] [rbp-2888h]
  char **v296; // [rsp+348h] [rbp-2880h]
  _WORD *v297; // [rsp+350h] [rbp-2878h]
  char **v298; // [rsp+358h] [rbp-2870h]
  _WORD *v299; // [rsp+360h] [rbp-2868h]
  char **v300; // [rsp+368h] [rbp-2860h]
  _WORD *v301; // [rsp+370h] [rbp-2858h]
  char **v302; // [rsp+378h] [rbp-2850h]
  _WORD *v303; // [rsp+380h] [rbp-2848h]
  char **v304; // [rsp+388h] [rbp-2840h]
  _WORD *v305; // [rsp+390h] [rbp-2838h]
  char **v306; // [rsp+398h] [rbp-2830h]
  _WORD *v307; // [rsp+3A0h] [rbp-2828h]
  char **v308; // [rsp+3A8h] [rbp-2820h]
  _WORD *v309; // [rsp+3B0h] [rbp-2818h]
  char **v310; // [rsp+3B8h] [rbp-2810h]
  _BYTE *v311; // [rsp+3C0h] [rbp-2808h]
  _BYTE *v312; // [rsp+3C8h] [rbp-2800h]
  int *v313; // [rsp+3D0h] [rbp-27F8h]
  _BYTE *v314; // [rsp+3D8h] [rbp-27F0h]
  _BYTE *v315; // [rsp+3E0h] [rbp-27E8h]
  int *v316; // [rsp+3E8h] [rbp-27E0h]
  int *v317; // [rsp+3F0h] [rbp-27D8h]
  int *v318; // [rsp+3F8h] [rbp-27D0h]
  struct IMetadataAccess *v319; // [rsp+400h] [rbp-27C8h]
  __int64 v320; // [rsp+408h] [rbp-27C0h]
  struct IMetadataAccess *v321; // [rsp+410h] [rbp-27B8h]
  __int64 v322; // [rsp+418h] [rbp-27B0h]
  __int64 v323; // [rsp+420h] [rbp-27A8h]
  _BYTE *v324; // [rsp+428h] [rbp-27A0h]
  __int64 v325; // [rsp+430h] [rbp-2798h]
  __int64 *v326; // [rsp+438h] [rbp-2790h]
  struct _GUID v327; // [rsp+440h] [rbp-2788h] BYREF
  __int64 v328; // [rsp+450h] [rbp-2778h]
  __int64 v329; // [rsp+458h] [rbp-2770h]
  __int64 v330; // [rsp+460h] [rbp-2768h]
  __int64 *v331; // [rsp+468h] [rbp-2760h]
  _BYTE v332[64]; // [rsp+470h] [rbp-2758h] BYREF
  char v333[8]; // [rsp+4B0h] [rbp-2718h] BYREF
  _WORD v334[4]; // [rsp+4B8h] [rbp-2710h] BYREF
  int v335; // [rsp+4C0h] [rbp-2708h]
  char **v336; // [rsp+4C8h] [rbp-2700h]
  char *v337; // [rsp+4D0h] [rbp-26F8h]
  __int64 v338; // [rsp+4D8h] [rbp-26F0h]
  char *v339; // [rsp+4E0h] [rbp-26E8h] BYREF
  int v340; // [rsp+4E8h] [rbp-26E0h]
  __int16 v341; // [rsp+4ECh] [rbp-26DCh]
  __int16 v342; // [rsp+4EEh] [rbp-26DAh]
  char v343; // [rsp+4F0h] [rbp-26D8h] BYREF
  int v344; // [rsp+700h] [rbp-24C8h]
  int v345; // [rsp+704h] [rbp-24C4h]
  __int64 v346; // [rsp+708h] [rbp-24C0h]
  char v347; // [rsp+710h] [rbp-24B8h] BYREF
  __int64 v348; // [rsp+711h] [rbp-24B7h]
  bool v349; // [rsp+719h] [rbp-24AFh]
  char v350[8]; // [rsp+720h] [rbp-24A8h] BYREF
  _WORD v351[4]; // [rsp+728h] [rbp-24A0h] BYREF
  int v352; // [rsp+730h] [rbp-2498h]
  char **v353; // [rsp+738h] [rbp-2490h]
  char *v354; // [rsp+740h] [rbp-2488h]
  __int64 v355; // [rsp+748h] [rbp-2480h]
  char *v356; // [rsp+750h] [rbp-2478h] BYREF
  int v357; // [rsp+758h] [rbp-2470h]
  __int16 v358; // [rsp+75Ch] [rbp-246Ch]
  __int16 v359; // [rsp+75Eh] [rbp-246Ah]
  char v360; // [rsp+760h] [rbp-2468h] BYREF
  int v361; // [rsp+970h] [rbp-2258h]
  int v362; // [rsp+974h] [rbp-2254h]
  __int64 v363; // [rsp+978h] [rbp-2250h]
  char v364; // [rsp+980h] [rbp-2248h] BYREF
  __int64 v365; // [rsp+981h] [rbp-2247h]
  bool v366; // [rsp+989h] [rbp-223Fh]
  char v367[8]; // [rsp+990h] [rbp-2238h] BYREF
  _WORD v368[4]; // [rsp+998h] [rbp-2230h] BYREF
  int v369; // [rsp+9A0h] [rbp-2228h]
  char **v370; // [rsp+9A8h] [rbp-2220h]
  char *v371; // [rsp+9B0h] [rbp-2218h]
  __int64 v372; // [rsp+9B8h] [rbp-2210h]
  char *v373; // [rsp+9C0h] [rbp-2208h] BYREF
  int v374; // [rsp+9C8h] [rbp-2200h]
  __int16 v375; // [rsp+9CCh] [rbp-21FCh]
  __int16 v376; // [rsp+9CEh] [rbp-21FAh]
  char v377; // [rsp+9D0h] [rbp-21F8h] BYREF
  int v378; // [rsp+BE0h] [rbp-1FE8h]
  int v379; // [rsp+BE4h] [rbp-1FE4h]
  __int64 v380; // [rsp+BE8h] [rbp-1FE0h]
  char v381; // [rsp+BF0h] [rbp-1FD8h] BYREF
  __int64 v382; // [rsp+BF1h] [rbp-1FD7h]
  bool v383; // [rsp+BF9h] [rbp-1FCFh]
  char v384[8]; // [rsp+C00h] [rbp-1FC8h] BYREF
  _WORD v385[4]; // [rsp+C08h] [rbp-1FC0h] BYREF
  int v386; // [rsp+C10h] [rbp-1FB8h]
  char **v387; // [rsp+C18h] [rbp-1FB0h]
  char *v388; // [rsp+C20h] [rbp-1FA8h]
  __int64 v389; // [rsp+C28h] [rbp-1FA0h]
  char *v390; // [rsp+C30h] [rbp-1F98h] BYREF
  int v391; // [rsp+C38h] [rbp-1F90h]
  __int16 v392; // [rsp+C3Ch] [rbp-1F8Ch]
  __int16 v393; // [rsp+C3Eh] [rbp-1F8Ah]
  char v394; // [rsp+C40h] [rbp-1F88h] BYREF
  int v395; // [rsp+E50h] [rbp-1D78h]
  int v396; // [rsp+E54h] [rbp-1D74h]
  __int64 v397; // [rsp+E58h] [rbp-1D70h]
  char v398; // [rsp+E60h] [rbp-1D68h] BYREF
  __int64 v399; // [rsp+E61h] [rbp-1D67h]
  bool v400; // [rsp+E69h] [rbp-1D5Fh]
  char v401[8]; // [rsp+E70h] [rbp-1D58h] BYREF
  _WORD v402[4]; // [rsp+E78h] [rbp-1D50h] BYREF
  int v403; // [rsp+E80h] [rbp-1D48h]
  char **v404; // [rsp+E88h] [rbp-1D40h]
  char *v405; // [rsp+E90h] [rbp-1D38h]
  __int64 v406; // [rsp+E98h] [rbp-1D30h]
  char *v407; // [rsp+EA0h] [rbp-1D28h] BYREF
  int v408; // [rsp+EA8h] [rbp-1D20h]
  __int16 v409; // [rsp+EACh] [rbp-1D1Ch]
  __int16 v410; // [rsp+EAEh] [rbp-1D1Ah]
  char v411; // [rsp+EB0h] [rbp-1D18h] BYREF
  int v412; // [rsp+10C0h] [rbp-1B08h]
  int v413; // [rsp+10C4h] [rbp-1B04h]
  __int64 v414; // [rsp+10C8h] [rbp-1B00h]
  char v415; // [rsp+10D0h] [rbp-1AF8h] BYREF
  __int64 v416; // [rsp+10D1h] [rbp-1AF7h]
  char v417[8]; // [rsp+10E0h] [rbp-1AE8h] BYREF
  _WORD v418[4]; // [rsp+10E8h] [rbp-1AE0h] BYREF
  int v419; // [rsp+10F0h] [rbp-1AD8h]
  char **v420; // [rsp+10F8h] [rbp-1AD0h]
  char *v421; // [rsp+1100h] [rbp-1AC8h]
  __int64 v422; // [rsp+1108h] [rbp-1AC0h]
  char *v423; // [rsp+1110h] [rbp-1AB8h] BYREF
  int v424; // [rsp+1118h] [rbp-1AB0h]
  __int16 v425; // [rsp+111Ch] [rbp-1AACh]
  __int16 v426; // [rsp+111Eh] [rbp-1AAAh]
  char v427; // [rsp+1120h] [rbp-1AA8h] BYREF
  int v428; // [rsp+1330h] [rbp-1898h]
  int v429; // [rsp+1334h] [rbp-1894h]
  __int64 v430; // [rsp+1338h] [rbp-1890h]
  char v431; // [rsp+1340h] [rbp-1888h] BYREF
  __int64 v432; // [rsp+1341h] [rbp-1887h]
  char v433[8]; // [rsp+1350h] [rbp-1878h] BYREF
  _WORD v434[4]; // [rsp+1358h] [rbp-1870h] BYREF
  int v435; // [rsp+1360h] [rbp-1868h]
  char **v436; // [rsp+1368h] [rbp-1860h]
  char *v437; // [rsp+1370h] [rbp-1858h]
  __int64 v438; // [rsp+1378h] [rbp-1850h]
  char *v439; // [rsp+1380h] [rbp-1848h] BYREF
  int v440; // [rsp+1388h] [rbp-1840h]
  __int16 v441; // [rsp+138Ch] [rbp-183Ch]
  __int16 v442; // [rsp+138Eh] [rbp-183Ah]
  char v443; // [rsp+1390h] [rbp-1838h] BYREF
  int v444; // [rsp+15A0h] [rbp-1628h]
  int v445; // [rsp+15A4h] [rbp-1624h]
  __int64 v446; // [rsp+15A8h] [rbp-1620h]
  char v447; // [rsp+15B0h] [rbp-1618h] BYREF
  __int64 v448; // [rsp+15B1h] [rbp-1617h]
  char v449[8]; // [rsp+15C0h] [rbp-1608h] BYREF
  _WORD v450[4]; // [rsp+15C8h] [rbp-1600h] BYREF
  int v451; // [rsp+15D0h] [rbp-15F8h]
  char **v452; // [rsp+15D8h] [rbp-15F0h]
  char *v453; // [rsp+15E0h] [rbp-15E8h]
  __int64 v454; // [rsp+15E8h] [rbp-15E0h]
  char *v455; // [rsp+15F0h] [rbp-15D8h] BYREF
  int v456; // [rsp+15F8h] [rbp-15D0h]
  __int16 v457; // [rsp+15FCh] [rbp-15CCh]
  __int16 v458; // [rsp+15FEh] [rbp-15CAh]
  char v459; // [rsp+1600h] [rbp-15C8h] BYREF
  int v460; // [rsp+1810h] [rbp-13B8h]
  int v461; // [rsp+1814h] [rbp-13B4h]
  __int64 v462; // [rsp+1818h] [rbp-13B0h]
  char v463; // [rsp+1820h] [rbp-13A8h] BYREF
  __int64 v464; // [rsp+1821h] [rbp-13A7h]
  _BYTE v465[176]; // [rsp+1830h] [rbp-1398h] BYREF
  __int64 v466; // [rsp+18E0h] [rbp-12E8h]
  _BYTE v467[176]; // [rsp+18E8h] [rbp-12E0h] BYREF
  __int64 v468; // [rsp+1998h] [rbp-1230h]
  _BYTE v469[176]; // [rsp+19A0h] [rbp-1228h] BYREF
  __int64 v470; // [rsp+1A50h] [rbp-1178h]
  _BYTE v471[176]; // [rsp+1A58h] [rbp-1170h] BYREF
  __int64 v472; // [rsp+1B08h] [rbp-10C0h]
  _BYTE v473[400]; // [rsp+1B10h] [rbp-10B8h] BYREF
  _BYTE v474[24]; // [rsp+1CA0h] [rbp-F28h] BYREF
  unsigned __int8 *v475; // [rsp+1CB8h] [rbp-F10h]
  unsigned int v476; // [rsp+1CCCh] [rbp-EFCh]
  int v477; // [rsp+1DD8h] [rbp-DF0h]
  int v478; // [rsp+1DDCh] [rbp-DECh]
  int v479; // [rsp+1E10h] [rbp-DB8h]
  int v480; // [rsp+1E18h] [rbp-DB0h]
  unsigned __int8 v481; // [rsp+1E1Ch] [rbp-DACh]
  char v482; // [rsp+1E1Dh] [rbp-DABh]
  char v483; // [rsp+1E1Eh] [rbp-DAAh]
  char v484; // [rsp+1E21h] [rbp-DA7h]
  char v485; // [rsp+1E22h] [rbp-DA6h]
  _WORD v486[2]; // [rsp+1E30h] [rbp-D98h] BYREF
  int v487; // [rsp+1E34h] [rbp-D94h]
  int v488; // [rsp+1E38h] [rbp-D90h]
  int v489; // [rsp+1E3Ch] [rbp-D8Ch]
  char v490[512]; // [rsp+1E40h] [rbp-D88h] BYREF
  __int128 v491; // [rsp+2040h] [rbp-B88h]
  int v492; // [rsp+2050h] [rbp-B78h]
  _WORD v493[2]; // [rsp+2060h] [rbp-B68h] BYREF
  int v494; // [rsp+2064h] [rbp-B64h]
  int v495; // [rsp+2068h] [rbp-B60h]
  int v496; // [rsp+206Ch] [rbp-B5Ch]
  char v497[512]; // [rsp+2070h] [rbp-B58h] BYREF
  __int128 v498; // [rsp+2270h] [rbp-958h]
  int v499; // [rsp+2280h] [rbp-948h]
  _BYTE v500[376]; // [rsp+2290h] [rbp-938h] BYREF
  int v501; // [rsp+2408h] [rbp-7C0h]
  char v502; // [rsp+2413h] [rbp-7B5h]
  char v503[384]; // [rsp+2420h] [rbp-7A8h] BYREF
  int v504; // [rsp+25A0h] [rbp-628h] BYREF
  __int16 v505; // [rsp+25A4h] [rbp-624h]
  int v506; // [rsp+25B0h] [rbp-618h]
  _BYTE v507[952]; // [rsp+25DCh] [rbp-5ECh] BYREF
  _BYTE v508[68]; // [rsp+2994h] [rbp-234h] BYREF
  int v509; // [rsp+29D8h] [rbp-1F0h] BYREF
  __int16 v510; // [rsp+29DCh] [rbp-1ECh]
  char v511; // [rsp+29DEh] [rbp-1EAh]
  char v512; // [rsp+29DFh] [rbp-1E9h]
  char v513; // [rsp+2B20h] [rbp-A8h] BYREF

  v329 = -2;
  v243 = (__int64)a3;
  v3 = a2;
  v209 = a2;
  v282 = this;
  v281 = a2;
  v193 = 5;
  v196 = 0;
  v197 = 0;
  v292 = 0;
  v293 = 0;
  v294 = 0;
  v210 = 0;
  v211 = 1;
  v212 = 0;
  v199 = 0;
  v192 = 0;
  v203 = 0;
  memset_0(v474, 0, 0x188u);
  v480 = -1;
  v234 = 0;
  v5 = (int (*)(int, int, int, int, char *))hdl_prntbackout;
  v204 = 0;
  v232 = 0;
  v206 = 0;
  v475 = (unsigned __int8 *)&v513;
  if ( *((_DWORD *)this + 612) )
    v5 = (int (*)(int, int, int, int, char *))CTraceDataSTVFInfo::CUserArguments;
  ExcHandler::ExcHandler((ExcHandler *)v332, 0, 0, 0, v5, 0);
  AutoOverrideMsqlXact::InitializeAndOverride((AutoOverrideMsqlXact *)&v292);
  v211 = 1;
  v235 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset);
  *(_QWORD *)&v212 = *(_QWORD *)(v235 + 144);
  v235 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset);
  v279 = 1;
  v6 = (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v212 + 464LL))(v212) == 0;
  v7 = *(_QWORD *)v212;
  if ( v6 )
  {
    (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64, __int64, int, int, _BYTE, _QWORD, int))(v7 + 8))(
      v212,
      L"CStmtAlterDB::ChangeStateOption",
      62,
      1,
      2,
      1,
      0,
      0,
      1);
    LODWORD(v210) = 1;
  }
  else
  {
    if ( (*(unsigned __int8 (**)(void))(v7 + 488))() )
      utassert_fail(
        1u,
        "rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()",
        "automsqlxact.cpp",
        235,
        0);
    (*(void (__fastcall **)(_QWORD, __int64, __int64, char *))(*(_QWORD *)v212 + 232LL))(v212, 2, 1, (char *)&v210 + 4);
    v211 = 1;
    LODWORD(v210) = 3;
  }
  v233 = (struct BaseXact *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v212 + 432LL))(v212);
  (*(void (__fastcall **)(struct BaseXact *))(*(_QWORD *)v233 + 16LL))(v233);
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v9 = *(_QWORD *)(v8 + 256);
  if ( !v9 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v9 = *(_QWORD *)(v8 + 256);
  }
  v226 = (struct IMetadataAccess *)((__int64 (__fastcall *)(_QWORD, struct BaseXact *, const char *, __int64))g_metadataFactory)(
                                     *(_QWORD *)(v9 + 1000),
                                     v233,
                                     "sql\\ntdbms\\msql\\proc\\stdb.cpp",
                                     13762);
  v214 = v226;
  v10 = (*(__int64 (__fastcall **)(struct IMetadataAccess *))(*(_QWORD *)v226 + 72LL))(v226);
  v271 = v10;
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v10 + 8LL))(
          v10,
          *((_QWORD *)this + 276),
          *((unsigned int *)this + 554));
  v194 = v11;
  if ( !v11 )
  {
    LODWORD(v181) = *((_DWORD *)this + 554);
    ex_raise(50, 11, 14, 5, v181, *((_QWORD *)this + 276));
  }
  v476 = 85;
  if ( !(**(unsigned __int8 (__fastcall ***)(__int64, _QWORD, _BYTE *, _QWORD))v10)(v10, v11, v474, 0) )
  {
    LODWORD(v181) = *((_DWORD *)this + 554);
    ex_raise(50, 11, 14, 6, v181, *((_QWORD *)this + 276));
  }
  v12 = 8LL * SystemThread_TlsIndex;
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v12)
                                         + SystemThread_TlsOffset)
                             + 72LL)
                 + 270LL)
      & 4) != 0 )
  {
    v235 = *(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v12) + SystemThread_TlsOffset);
    v252 = v235;
    v252 = *(_QWORD *)(SystemThread_TlsOffset + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v12));
    v283 = *(unsigned __int16 *)(*(_QWORD *)(v252 + 80) + 8LL);
    TardisDbId = v11;
    v195 = v11;
    if ( v283 != v11 )
    {
      LODWORD(v181) = *((_DWORD *)this + 554);
      ex_raise(50, 11, 14, 10, v181, *((_QWORD *)this + 276));
    }
  }
  else
  {
    TardisDbId = v11;
    v195 = v11;
  }
  if ( (unsigned int)(*((_DWORD *)this + 612) - 1) <= 1 && (v484 & 0x10) != 0 )
  {
    LODWORD(v189) = *((_DWORD *)this + 554);
    ex_raise(50, 58, 16, 9, 48, L"VARDECIMAL_STORAGEFORMAT", v189, *((_QWORD *)this + 276));
  }
  v200 = 0;
  v201 = 0;
  v208 = 7;
  v207 = 7;
  v228 = 0;
  if ( (unsigned __int8)FGetFidoGLMController(&v228, TardisDbId) )
  {
    DWFidoTxCtx = GetDWFidoTxCtx(0, 1);
    v14 = (*(__int64 (__fastcall **)(CStmtAlterDB *))(*(_QWORD *)this + 120LL))(this);
    StartDwFidoTran(v14, &DWFidoTxCtx, v228, 0, 0);
    TardisDbId = DWFidoTxCtx::GetTardisDbId(DWFidoTxCtx, v228);
    v195 = TardisDbId;
    v194 = TardisDbId;
    v15 = (*(__int64 (__fastcall **)(struct IFidoGLMController *))(*(_QWORD *)v228 + 152LL))(v228);
    v16 = v206;
    if ( !v15 )
      v16 = 16;
    v206 = v16;
  }
  if ( !CAutoDb::FUse((CAutoDb *)&v199, TardisDbId, 0, 1, 0, 0) )
  {
    v17 = *(_DWORD *)(qword_102ECFB00 + 48);
    if ( (v17 & 0x20) != 0 || (v17 & 0x10) == 0 )
    {
      LODWORD(v182) = *((_DWORD *)this + 554);
      ex_raise(50, 11, 14, 7, v182, *((_QWORD *)this + 276));
    }
    if ( *((_DWORD *)this + 618) != 0x80000000 || *((_DWORD *)this + 607) != 3 )
    {
      CAutoDb::~CAutoDb((CAutoDb *)&v199);
      CAutoDb::FUse((CAutoDb *)&v199, TardisDbId, 0, 1, 1, 0);
      v193 = 4;
    }
    v213 = lockdb(TardisDbId, 43, v193, 6000, v206);
    if ( v213 < 0 )
      goto LABEL_43;
    _mm_lfence();
    v196 = 1;
    if ( v194 != (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v271 + 8LL))(
                   v271,
                   *((_QWORD *)this + 276),
                   *((unsigned int *)this + 554)) )
    {
      LODWORD(v183) = *((_DWORD *)this + 554);
      ex_raise(50, 11, 14, 8, v183, *((_QWORD *)this + 276));
    }
    v252 = 0;
    v322 = qword_102ECFB00;
    DBTABLE = DBMgr::TryToGetDBTABLE(*(_QWORD *)(qword_102ECFB00 + 32), 0, v194);
    v197 = (unsigned int *)DBTABLE;
    if ( (unsigned int)DBTABLE::GetCurrentState(DBTABLE) == 1 )
    {
      v19 = LookupAvailabilityName(1);
      ex_raise(50, 52, 16, 1, L"ALTER DATABASE", v19);
    }
    if ( (*(_DWORD *)(DBTABLE + 1648) & 2) == 0 )
    {
      _mm_lfence();
      v20 = DBTABLE;
      v21 = *(_QWORD *)(*(_QWORD *)(DBTABLE + 4624) + 1712LL);
      if ( !*(_DWORD *)(v21 + 784)
        || *(_QWORD *)(v21 + 788) == *(_QWORD *)&x_AG_DB_IdBad.Data1
        && *(_QWORD *)(v21 + 796) == *(_QWORD *)x_AG_DB_IdBad.Data4 )
      {
        goto LABEL_46;
      }
      _mm_lfence();
      if ( !*(_BYTE *)(*(_QWORD *)(DBTABLE + 4624) + 8272LL) )
      {
        TardisDbId = v194;
        v195 = v194;
LABEL_43:
        v20 = (__int64)v197;
LABEL_44:
        CStmtAlterDB::PerformGeneralPermissionCheck(
          this,
          TardisDbId,
          v475,
          v476,
          0,
          *(struct ISecurityContext **)(*((_QWORD *)v3 + 15) + 264LL),
          v226);
        goto LABEL_130;
      }
    }
    _mm_lfence();
    v20 = DBTABLE;
    LODWORD(v183) = *(_DWORD *)(DBTABLE + 928);
    ex_raise(14, 68, 16, 5, v183, DBTABLE + 936);
LABEL_46:
    TardisDbId = v194;
    v195 = v194;
    goto LABEL_44;
  }
  v23 = v199;
  v195 = v199;
  v194 = v199;
  v323 = qword_102ECFB00;
  v24 = *(_QWORD *)(qword_102ECFB00 + 32);
  v250 = v24;
  switch ( v199 )
  {
    case 0x7FFCu:
      v20 = *(_QWORD *)(v24 + 104);
      goto LABEL_57;
    case 0x7FFDu:
      v20 = *(_QWORD *)(v24 + 112);
      goto LABEL_57;
    case 0x7FFFu:
      v20 = *(_QWORD *)(v24 + 88);
LABEL_57:
      v197 = (unsigned int *)v20;
      goto LABEL_58;
  }
  if ( v199 <= *(_DWORD *)(v24 + 76) && v199 )
  {
    _mm_lfence();
    v23 = v199;
    v20 = *(_QWORD *)(*(_QWORD *)(v250 + 40) + 8LL * (int)(v199 - 1));
    v197 = (unsigned int *)v20;
    v195 = v199;
  }
  else
  {
    v20 = 0;
    v197 = 0;
  }
LABEL_58:
  v324 = v465;
  CCompExecCtxt::CCompExecCtxt((CCompExecCtxt *)v465, v3);
  v466 = *((_QWORD *)v3 + 22);
  if ( (unsigned __int8)CStmtAlterDB::IsSDSDbOperation(v25, v226, v465) )
  {
    v26 = ((__int64 (__fastcall *)(_QWORD, struct BaseXact *, _QWORD, const char *, int))g_metadataFactory[3])(
            *(_QWORD *)(v20 + 688),
            v233,
            *(unsigned __int16 *)(v20 + 42),
            "sql\\ntdbms\\msql\\proc\\stdb.cpp",
            13927);
    v325 = v26;
    v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 72LL))(v26);
    v28 = DBTABLE::CbLogicalDbNameInternal((DBTABLE *)v20);
    v29 = DBTABLE::LogicalDbNameInternal((DBTABLE *)v20);
    v30 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v27 + 8LL))(v27, v29, v28);
    v476 = 85;
    (**(void (__fastcall ***)(__int64, _QWORD, _BYTE *, _QWORD))v27)(v27, v30, v474, 0);
    v328 = v26;
    (**(void (__fastcall ***)(__int64, __int64))v26)(v26, 1);
    v3 = v209;
  }
  CStmtAlterDB::PerformGeneralPermissionCheck(
    this,
    v23,
    v475,
    v476,
    1,
    *(struct ISecurityContext **)(*((_QWORD *)v3 + 15) + 264LL),
    v226);
  SEStatFromDbRegAttr = GetSEStatFromDbRegAttr((const struct MDAttrDbReg *)v474);
  v32 = SEStatFromDbRegAttr;
  v201 = SEStatFromDbRegAttr;
  v200 = SEStatFromDbRegAttr;
  v200 = *((_DWORD *)this + 602) | SEStatFromDbRegAttr & ~*((_DWORD *)this + 601);
  v33 = v200;
  AvailabilityFromStatus = GetAvailabilityFromStatus(SEStatFromDbRegAttr);
  v208 = AvailabilityFromStatus;
  v207 = GetAvailabilityFromStatus(v33);
  if ( AvailabilityFromStatus != v207
    || (v33 & 0x1000) != 0 && (v32 & 0x1000) == 0
    || (v33 & 0x400) != 0 && (v201 & 0x400) == 0 )
  {
    StopFTCrawls(v23, 0);
  }
  if ( !v208 && (unsigned int)(v207 - 5) <= 1 || (v33 & 0x400) == 0 && (v201 & 0x400) != 0 )
  {
    ClearFulltextCaches(v23);
    ClearCatalogCache(v23, v226);
    v36 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v37 = *(_QWORD *)(v36 + 256);
    if ( !v37 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v37 = *(_QWORD *)(v36 + 256);
    }
    v23 = v199;
    FullTextBuildDelayOperationPool(v199, 0, 0, &v234, *(struct IMemObj **)(v37 + 1000));
    v204 = 1;
    v195 = v194;
    v20 = (__int64)v197;
  }
  v38 = v20 + 4624;
  v39 = *(_QWORD *)(v20 + 4624);
  v40 = *(_QWORD *)(v39 + 1712);
  if ( !*(_DWORD *)(v40 + 784)
    || *(_QWORD *)(v40 + 788) == *(_QWORD *)&x_AG_DB_IdBad.Data1
    && *(_QWORD *)(v40 + 796) == *(_QWORD *)x_AG_DB_IdBad.Data4
    || !*(_BYTE *)(v39 + 8272) )
  {
    TardisDbId = v195;
    goto LABEL_84;
  }
  v260 = 0;
  v41 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset);
  if ( !v41 || (v42 = *(struct CSessionTraceFlags ***)(v41 + 56), (v43 = *v42) == 0) )
  {
    v254 = 0;
    goto LABEL_82;
  }
  v254 = (__int64)*v42;
  if ( !CSessionTraceFlags::CheckSessionTraceInternal(v43, 0xD86u) )
  {
LABEL_82:
    v20 = (__int64)v197;
    v44 = DBTABLE::LogicalDbNameInternal((DBTABLE *)v197);
    LODWORD(v185) = DBTABLE::CbLogicalDbNameInternal((DBTABLE *)v197);
    ex_raise(14, 68, 16, 3, v185, v44);
    TardisDbId = v194;
    v195 = v194;
    v23 = v199;
    goto LABEL_84;
  }
  TardisDbId = v194;
  v195 = v194;
  v20 = (__int64)v197;
  v23 = v199;
LABEL_84:
  if ( *(_DWORD *)(qword_102ECFB00 + 14504) )
  {
    v45 = *(DBTABLE **)(*(_QWORD *)v38 + 1712LL);
    if ( (*((_BYTE *)v45 + 60) & 1) != 0 && !DBTABLE::IsCOWReplicaDatabase(v45) && *(_BYTE *)(*(_QWORD *)v38 + 8272LL) )
    {
      v46 = DBTABLE::LogicalDbNameInternal((DBTABLE *)v20);
      ex_raise(406, 81, 16, 1, v46);
    }
  }
  v47 = (v200 ^ v201) & 0x800000;
  if ( v47 )
  {
    if ( *(_QWORD *)(*(_QWORD *)v38 + 1752LL) )
      ex_raise(90, 27, 16, 2);
    if ( *(_DWORD *)(v20 + 1648)
      || (v48 = *(_QWORD *)(*(_QWORD *)v38 + 1712LL), *(_DWORD *)(v48 + 784))
      && (*(_QWORD *)(v48 + 788) != *(_QWORD *)&x_AG_DB_IdBad.Data1
       || *(_QWORD *)(v48 + 796) != *(_QWORD *)x_AG_DB_IdBad.Data4)
      && *(_BYTE *)(*(_QWORD *)v38 + 8272LL) )
    {
      v49 = DBTABLE::LogicalDbNameInternal((DBTABLE *)v20);
      LODWORD(v185) = DBTABLE::CbLogicalDbNameInternal((DBTABLE *)v20);
      ex_raise(14, 68, 16, 6, v185, v49);
    }
  }
  LOBYTE(v35) = 4;
  v198 = 4;
  if ( (unsigned int)(*((_DWORD *)this + 612) - 1) <= 1 || *((_QWORD *)this + 333) )
  {
    LOBYTE(v35) = 5;
  }
  else
  {
    v50 = 4;
    if ( !*((_BYTE *)this + 2457) )
      goto LABEL_104;
    LOBYTE(v35) = 3;
  }
  v50 = v35;
  v198 = v35;
LABEL_104:
  v193 = v35;
  v213 = lockdb(v23, 43, v35, 6000, v206);
  if ( v213 >= 0 )
  {
    v196 = 1;
    if ( v50 == 5
      || ((v284 = (CSessionLockList **)v467,
           v51 = v209,
           CCompExecCtxt::CCompExecCtxt((CCompExecCtxt *)v467, v209),
           v468 = *((_QWORD *)v51 + 22),
           !(unsigned __int8)CStmtAlterDB::IsSDSDbOperation(v52, v226, v467))
       || (*((_DWORD *)this + 601) & 0x400) == 0 && (*((_DWORD *)this + 602) & 0x400) == 0
        ? (v53 = 0)
        : (v53 = 1),
          (v224 = v53, !*((_DWORD *)this + 634))
       && !*((_QWORD *)this + 319)
       && (*((_BYTE *)this + 2412) & 4) == 0
       && (*((_BYTE *)this + 2416) & 4) == 0
       && !v47
       && !v53
       && !*((_DWORD *)this + 613)
       && !*((_BYTE *)this + 2464)
       && !*((_DWORD *)this + 615)) )
    {
LABEL_130:
      if ( v213 >= 0 )
        goto LABEL_139;
      goto LABEL_131;
    }
    _mm_lfence();
    v54 = 0;
    v225 = 0;
    if ( v47 || *((_DWORD *)this + 613) )
    {
      v225 = 2;
      v54 = 3;
    }
    else
    {
      if ( !*((_DWORD *)this + 634) && !v53 )
      {
LABEL_128:
        v55 = *((unsigned int *)this + 635);
LABEL_129:
        v258 = v55;
        v20 = (__int64)v197;
        LOBYTE(v190) = 5;
        DBMgr::LockDBForStateChange(
          *(_QWORD *)(qword_102ECFB00 + 32),
          v199,
          v55,
          v197[232],
          v197 + 234,
          v54,
          (_DWORD)v190,
          -1);
        unlockdb(v199, 43, v198);
        v193 = 5;
        TardisDbId = v194;
        v195 = v194;
        goto LABEL_130;
      }
      v54 = 1;
    }
    v225 = v54;
    if ( v53 )
    {
      v55 = 0;
      if ( *((int *)this + 635) <= 0 )
        goto LABEL_129;
    }
    goto LABEL_128;
  }
LABEL_131:
  _mm_lfence();
  if ( v213 == -1 )
  {
    if ( (v482 & 1) != 0 )
    {
      v284 = *(CSessionLockList ***)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset);
      TardisDbId = v194;
      v195 = v194;
      if ( !CSessionLockList::IsHeldSingleUserLock(v284[11], v194) )
      {
        LODWORD(v184) = *((_DWORD *)this + 554);
        ex_raise(50, 64, 16, 1, v184, *((_QWORD *)this + 276));
      }
    }
    else
    {
      TardisDbId = v194;
      v195 = v194;
    }
    LODWORD(v184) = *((_DWORD *)this + 554);
    ex_raise(50, 61, 16, 1, v184, *((_QWORD *)this + 276));
  }
  else
  {
    TardisDbId = v194;
    v195 = v194;
  }
  LOBYTE(v22) = 68;
  lck_StandardHandler((unsigned int)v213, v22);
  v20 = (__int64)v197;
LABEL_139:
  if ( (*((_DWORD *)this + 604) & 0x400) != 0 || (*((_DWORD *)this + 603) & 0x400) != 0 )
  {
    if ( FSystemDBId(TardisDbId, 0x77u) )
      ex_raise(56, 0, 16, 2);
    MasterDbId = GetMasterDbId();
    LOBYTE(v188) = 1;
    if ( !(unsigned __int8)ISECManager::AccessCheck(
                             0,
                             MasterDbId,
                             0,
                             24,
                             11,
                             (_DWORD)v188,
                             0,
                             0,
                             30,
                             0,
                             0,
                             0,
                             0,
                             -1,
                             0,
                             0,
                             0,
                             0,
                             0,
                             0,
                             0,
                             0,
                             0) )
      ex_raise(152, 47, 16, 1);
  }
  if ( (*((_DWORD *)this + 604) & 0x200) != 0 || (*((_DWORD *)this + 603) & 0x200) != 0 )
  {
    if ( FSystemDBId(TardisDbId, 0x46u) )
      ex_raise(153, 9, 16, 1);
    v57 = GetMasterDbId();
    LOBYTE(v191) = 0;
    LOBYTE(v188) = 1;
    if ( !(unsigned __int8)ISECManager::AccessCheck(
                             0,
                             v57,
                             0,
                             24,
                             51,
                             (_DWORD)v188,
                             0,
                             0,
                             30,
                             0,
                             0,
                             0,
                             0,
                             -1,
                             0,
                             0,
                             0,
                             v191,
                             0,
                             0,
                             0,
                             0,
                             0) )
      ex_raise(152, 47, 16, 1);
  }
  v58 = *((_DWORD *)this + 604);
  if ( (v58 & 0x100) != 0
    || (v59 = *((_DWORD *)this + 603), (v59 & 0x100) != 0)
    || (v58 & 0x40) != 0
    || (v59 & 0x40) != 0 )
  {
    if ( FSystemDatabase(*((const wchar_t **)this + 276), *((_DWORD *)this + 554), TardisDbId, 1) )
      ex_raise(331, 2, 16, 1);
    LOBYTE(v191) = 0;
    LOBYTE(v188) = 1;
    if ( !(unsigned __int8)ISECManager::AccessCheck(
                             0,
                             TardisDbId,
                             TardisDbId,
                             0,
                             108,
                             (_DWORD)v188,
                             0,
                             0,
                             30,
                             0,
                             0,
                             0,
                             0,
                             -1,
                             0,
                             0,
                             0,
                             v191,
                             0,
                             0,
                             0,
                             0,
                             0) )
      ex_raise(152, 47, 16, 1);
  }
  if ( (*((_DWORD *)this + 604) & 0x8000) != 0 || (*((_DWORD *)this + 603) & 0x8000) != 0 )
  {
    if ( FNonSvcBrokerDb(TardisDbId) )
    {
      v60 = LookupOptionName(39, (struct opttype *)&OptDBOptions);
      v61 = -1;
      do
        ++v61;
      while ( v60[v61] );
      v330 = 2 * v61;
      LODWORD(v190) = *((_DWORD *)this + 554);
      LODWORD(v184) = 2 * v61;
      ex_raise(50, 58, 16, 10, v184, v60, v190, *((_QWORD *)this + 276));
    }
    v62 = GetMasterDbId();
    LOBYTE(v191) = 0;
    LOBYTE(v188) = 1;
    if ( !(unsigned __int8)ISECManager::AccessCheck(
                             0,
                             v62,
                             0,
                             24,
                             51,
                             (_DWORD)v188,
                             0,
                             0,
                             30,
                             0,
                             0,
                             0,
                             0,
                             -1,
                             0,
                             0,
                             0,
                             v191,
                             0,
                             0,
                             0,
                             0,
                             0) )
      ex_raise(152, 47, 16, 11);
  }
  CAutoDb::~CAutoDb((CAutoDb *)&v199);
  if ( (v483 & 0x10) != 0 && (*((_DWORD *)this + 606) & 0x10000) != 0 && (*((_BYTE *)this + 2420) & 0x10) == 0
    || (v483 & 0x20) != 0 && (*((_BYTE *)this + 2424) & 0x10) != 0 && (*((_DWORD *)this + 605) & 0x10000) == 0 )
  {
    ex_raise(50, 67, 16, 1);
  }
  if ( v477 && !v478 )
    ex_raise(50, 93, 16, 1);
  v65 = (_DWORD *)((char *)this + 2424);
  if ( (*((_BYTE *)this + 2424) & 1) != 0 )
  {
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v64 = *(_QWORD *)(*(_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset) + 72LL);
    if ( (*(_BYTE *)(v64 + 270) & 4) != 0 )
    {
      TardisDbId = v194;
      v195 = v194;
    }
    else
    {
      v242 = 0;
      v255 = &AutoReadOnlyIMA::`vftable';
      v256 = 0;
      v326 = &v257;
      v331 = &v257;
      v257 = 0;
      v66 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v67 = *(_QWORD *)(v66 + 256);
      if ( !v67 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v67 = *(_QWORD *)(v66 + 256);
      }
      v68 = *(_QWORD *)(v67 + 1000);
      AutoReadOnlyXact::BeginCompatibleXact((AutoReadOnlyXact *)&v257, L"MEMORY_OPTIMIZED_DATAFileGroupCheck", 70, 0);
      ((void (__fastcall *)(void ***, __int64))*v255)(&v255, v68);
      LODWORD(v188) = 0;
      LODWORD(v184) = 0;
      TardisDbId = v194;
      v195 = v194;
      v69 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v256 + 56LL))(v256, v194, 0, 0);
      v70 = v242;
      while ( 1 )
      {
        v71 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v69 + 696LL))(v69, v70, 1);
        v70 = v71;
        if ( !v71 )
          break;
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v71 + 24LL))(v71, &v266);
        if ( v266 == 4 && (v267 & 1) != 0 )
        {
          RaiseUnsupportedHekatonFeatureError(124, 6, 0);
          break;
        }
      }
      AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v255);
      v65 = (_DWORD *)((char *)this + 2424);
    }
    v20 = (__int64)v197;
  }
  if ( !v20 )
  {
    v20 = g_dbtableFactory[4](TardisDbId);
    v197 = (unsigned int *)v20;
    if ( !v20 )
      utassert_fail(1u, "dbtable", "stdb.cpp", 14261, 0);
  }
  v229 = 27;
  if ( *(_BYTE *)(GetXdbServerGlobals(v64, ThreadLocalStoragePointer) + 12004) )
  {
    if ( *(_QWORD *)(v20 + 5320) )
    {
      LOWORD(v184) = 0;
      v72 = CStatement::XretDwFidoExecuteOnGLMS(this, v243, TardisDbId, 0);
      v229 = v72;
      if ( v72 != 27 )
      {
        if ( v72 )
          ex_raise(50, 69, 16, 2);
      }
    }
  }
  if ( (*((_DWORD *)this + 604) & 0x100) != 0 )
  {
    TickCount = GetTickCount();
    v236 = TickCount;
    v243 = 0x200000002LL;
    if ( (qword_102F21DB4 & 0x200000000LL) != 0 )
    {
      v251 = 1;
      v295 = v351;
      v351[0] = 0;
      v351[1] = 1;
      v352 = 0;
      v353 = &v356;
      v354 = &v360;
      v361 = 0;
      v362 = 0;
      v355 = 0;
      v363 = 0;
      v296 = &v356;
      v356 = &v364;
      v357 = 10;
      v358 = 0;
      v359 = 0;
      v364 = 3;
      v365 = 0;
      v366 = (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                 + SystemThread_TlsIndex)
                                               + SystemThread_TlsOffset)
                                   + 72LL)
                       + 270LL)
            & 4) != 0;
      XeCloudPkg::database_ddl_stmt_tde_start::Publish((XeCloudPkg::database_ddl_stmt_tde_start *)v350);
      TardisDbId = v194;
      v195 = v194;
      v20 = (__int64)v197;
      TickCount = v236;
    }
    if ( *((_BYTE *)qword_102EF3550 + 760) || (v222 = *((_BYTE *)qword_102ECFB10 + 626) >> 7) != 0 )
    {
      v74 = *((_DWORD *)this + 582);
      if ( v74 > 0 )
      {
        if ( !DBTABLE::VerifyValidWorkgroup((DBTABLE *)v20, *((wchar_t **)this + 292), v74) )
          ex_raise(335, 59, 16, 1);
        DBTABLE::SetTDEWorkgroupName((DBTABLE *)v20, *((wchar_t **)this + 292), *((_DWORD *)this + 582), 1);
      }
    }
    CSECDEK::TurnOnEncryption((struct DBTABLE *)v20);
    v75 = GetTickCount();
    v242 = 0x400000002LL;
    if ( (qword_102F21DB4 & 0x400000000LL) != 0 )
    {
      v253 = 1;
      v297 = v402;
      v402[0] = 0;
      v402[1] = 1;
      v403 = 0;
      v404 = &v407;
      v405 = &v411;
      v412 = 0;
      v413 = 0;
      v406 = 0;
      v414 = 0;
      v298 = &v407;
      v407 = &v415;
      v408 = 9;
      v409 = 0;
      v410 = 0;
      v415 = 3;
      v416 = v75 - TickCount;
      XeCloudPkg::database_ddl_stmt_tde_succeeded::Publish((XeCloudPkg::database_ddl_stmt_tde_succeeded *)v401);
    }
    EncryptionWarningForHkV1(v20);
    goto LABEL_209;
  }
  if ( (*((_DWORD *)this + 603) & 0x100) == 0 )
  {
LABEL_209:
    v76 = v209;
    goto LABEL_210;
  }
  v79 = GetTickCount();
  v254 = 0x200000002LL;
  v76 = v209;
  if ( (qword_102F21DB4 & 0x200000000LL) != 0 )
  {
    v248 = 1;
    v299 = v334;
    v334[0] = 0;
    v334[1] = 1;
    v335 = 0;
    v336 = &v339;
    v337 = &v343;
    v344 = 0;
    v345 = 0;
    v338 = 0;
    v346 = 0;
    v300 = &v339;
    v339 = &v347;
    v340 = 10;
    v341 = 0;
    v342 = 0;
    v347 = 4;
    v348 = 0;
    v349 = (*(_BYTE *)(*((_QWORD *)v209 + 9) + 270LL) & 4) != 0;
    XeCloudPkg::database_ddl_stmt_tde_start::Publish((XeCloudPkg::database_ddl_stmt_tde_start *)v333);
  }
  if ( *((_BYTE *)qword_102EF3550 + 760) || (v221 = *((_BYTE *)qword_102ECFB10 + 626) >> 7) != 0 )
  {
    v80 = *((_DWORD *)this + 582);
    if ( v80 > 0 )
    {
      if ( !DBTABLE::VerifyValidWorkgroup((DBTABLE *)v20, *((wchar_t **)this + 292), v80) )
        ex_raise(335, 59, 16, 2);
      DBTABLE::SetTDEWorkgroupName((DBTABLE *)v20, *((wchar_t **)this + 292), *((_DWORD *)this + 582), 1);
    }
  }
  CSECDEK::TurnOffEncryption((struct DBTABLE *)v20);
  v81 = GetTickCount();
  v250 = 0x400000002LL;
  if ( (qword_102F21DB4 & 0x400000000LL) != 0 )
  {
    v247 = 1;
    v301 = v418;
    v418[0] = 0;
    v418[1] = 1;
    v419 = 0;
    v420 = &v423;
    v421 = &v427;
    v428 = 0;
    v429 = 0;
    v422 = 0;
    v430 = 0;
    v302 = &v423;
    v423 = &v431;
    v424 = 9;
    v425 = 0;
    v426 = 0;
    v431 = 4;
    v432 = v81 - v79;
    XeCloudPkg::database_ddl_stmt_tde_succeeded::Publish((XeCloudPkg::database_ddl_stmt_tde_succeeded *)v417);
  }
LABEL_210:
  if ( (*((_BYTE *)this + 2416) & 0x40) != 0 )
  {
    v77 = GetTickCount();
    v237 = v77;
    v226 = (struct IMetadataAccess *)0x200000002LL;
    if ( (qword_102F21DB4 & 0x200000000LL) != 0 )
    {
      v303 = v368;
      v368[0] = 0;
      v368[1] = 1;
      v369 = 0;
      v370 = &v373;
      v371 = &v377;
      v378 = 0;
      v379 = 0;
      v372 = 0;
      v380 = 0;
      v304 = &v373;
      v373 = &v381;
      v374 = 10;
      v375 = 0;
      v376 = 0;
      v381 = 3;
      v382 = 0;
      v383 = (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                 + SystemThread_TlsIndex)
                                               + SystemThread_TlsOffset)
                                   + 72LL)
                       + 270LL)
            & 4) != 0;
      XeCloudPkg::database_ddl_stmt_tde_start::Publish((XeCloudPkg::database_ddl_stmt_tde_start *)v367);
      TardisDbId = v194;
      v195 = v194;
      v20 = (__int64)v197;
      v77 = v237;
    }
    CSECDEK::SuspendScan((struct DBTABLE *)v20);
    v78 = GetTickCount();
    v262 = 2;
    v263 = 4;
    if ( (qword_102F21DB4 & 0x400000000LL) != 0 )
    {
      v246 = 1;
      v305 = v434;
      v434[0] = 0;
      v434[1] = 1;
      v435 = 0;
      v436 = &v439;
      v437 = &v443;
      v444 = 0;
      v445 = 0;
      v438 = 0;
      v446 = 0;
      v306 = &v439;
      v439 = &v447;
      v440 = 9;
      v441 = 0;
      v442 = 0;
      v447 = 3;
      v448 = v78 - v77;
      XeCloudPkg::database_ddl_stmt_tde_succeeded::Publish((XeCloudPkg::database_ddl_stmt_tde_succeeded *)v433);
    }
    EncryptionWarningForHkV1(v20);
  }
  else if ( (*((_BYTE *)this + 2412) & 0x40) != 0 )
  {
    v82 = GetTickCount();
    v258 = 2;
    v259 = 2;
    if ( (qword_102F21DB4 & 0x200000000LL) != 0 )
    {
      v245 = 1;
      v307 = v385;
      v385[0] = 0;
      v385[1] = 1;
      v386 = 0;
      v387 = &v390;
      v388 = &v394;
      v395 = 0;
      v396 = 0;
      v389 = 0;
      v397 = 0;
      v308 = &v390;
      v390 = &v398;
      v391 = 10;
      v392 = 0;
      v393 = 0;
      v398 = 4;
      v399 = 0;
      v400 = (*(_BYTE *)(*((_QWORD *)v76 + 9) + 270LL) & 4) != 0;
      XeCloudPkg::database_ddl_stmt_tde_start::Publish((XeCloudPkg::database_ddl_stmt_tde_start *)v384);
    }
    v83 = *((_DWORD *)this + 582);
    if ( v83 > 0 )
    {
      if ( !DBTABLE::VerifyValidWorkgroup((DBTABLE *)v20, *((wchar_t **)this + 292), v83) )
        ex_raise(335, 59, 16, 3);
      DBTABLE::SetTDEWorkgroupName((DBTABLE *)v20, *((wchar_t **)this + 292), *((_DWORD *)this + 582), 1);
    }
    CSECDEK::ResumeScan((struct DBTABLE *)v20);
    v84 = GetTickCount();
    v260 = 2;
    v261 = 4;
    if ( (qword_102F21DB4 & 0x400000000LL) != 0 )
    {
      v244 = 1;
      v309 = v450;
      v450[0] = 0;
      v450[1] = 1;
      v451 = 0;
      v452 = &v455;
      v453 = &v459;
      v460 = 0;
      v461 = 0;
      v454 = 0;
      v462 = 0;
      v310 = &v455;
      v455 = &v463;
      v456 = 9;
      v457 = 0;
      v458 = 0;
      v463 = 4;
      v464 = v84 - v82;
      XeCloudPkg::database_ddl_stmt_tde_succeeded::Publish((XeCloudPkg::database_ddl_stmt_tde_succeeded *)v449);
    }
  }
  CStmtAlterDB::VerifyAndErrorLogOptionChange(this);
  if ( (*((_DWORD *)this + 605) & 0x100000) != 0 || (*v65 & 0x100000) != 0 )
  {
    if ( (*((_DWORD *)this + 602) & 0x809E00) != 0 || (*((_DWORD *)this + 601) & 0x809E00) != 0 )
    {
      LODWORD(v184) = *(_DWORD *)(v20 + 928);
      ex_raise(50, 82, 16, 1, v184, v20 + 936);
    }
    if ( *((_DWORD *)this + 635) != -2 )
      ex_raise(50, 83, 16, 1);
    if ( (*((_DWORD *)this + 606) & 0x100000) != 0 )
    {
      v85 = *((_BYTE *)qword_102ECFB10 + 451);
      v220 = v85 >> 1;
      if ( (v85 & 2) != 0 || (v219 = v85, (v85 & 1) != 0) || (v218 = *((_BYTE *)qword_102ECFB10 + 450) >> 7) != 0 )
        ex_raise(50, 85, 16, 1);
    }
    if ( DbVerStateMgr::IsDbAlwaysVersioned((struct DBTABLE *)v20) )
      ex_callprint(3987, 10, 1);
  }
  v311 = v469;
  v86 = v209;
  CCompExecCtxt::CCompExecCtxt((CCompExecCtxt *)v469, v209);
  v470 = *((_QWORD *)v86 + 22);
  v87 = v214;
  if ( !(unsigned __int8)CStmtAlterDB::IsSDSDbOperation(v88, v214, v469) )
    goto LABEL_271;
  if ( (*((_DWORD *)this + 601) & 0x400) == 0 )
  {
    if ( (*((_DWORD *)this + 602) & 0x400) != 0 )
    {
      v89 = v481 >> 7;
      v90 = v481 | 0x80;
      goto LABEL_255;
    }
LABEL_271:
    v94 = 0;
    v249 = 0;
    v312 = v471;
    v95 = v209;
    CCompExecCtxt::CCompExecCtxt((CCompExecCtxt *)v471, v209);
    v472 = *((_QWORD *)v95 + 22);
    if ( (unsigned __int8)CStmtAlterDB::IsSDSDbOperation(v96, v87, v471)
      && *(_WORD *)(*(_QWORD *)(v20 + 4624) + 1674LL) == 3
      && !*(_DWORD *)(GetXdbServerGlobals(v98, v97) + 8196) )
    {
      v94 = IMetadataAccessRemoteLogicalMasterGet(*(struct IMemObj **)(v20 + 688), v233);
      v99 = v285;
      if ( v94 )
        v99 = 0;
      v285 = v99;
      v249 = v94;
    }
    if ( (*((_DWORD *)this + 606) & 0xD3411D) != 0 || (*((_DWORD *)this + 605) & 0xD3411D) != 0 )
    {
      v94 = v249;
      v190 = v249;
      v188 = v233;
      v184 = (CStmtAlterDB *)((char *)this + 2420);
      v100 = v194;
      v195 = v194;
      DBMgr::ChangeDBSEOption(*(_QWORD *)(qword_102ECFB00 + 32), v194, v193);
      v20 = (__int64)v197;
      v87 = v214;
    }
    else
    {
      v100 = v195;
    }
    if ( *((_DWORD *)this + 618) != 0x80000000 )
    {
      v101 = (DBTABLE *)g_dbtableFactory[4](v100);
      if ( !v101 )
        utassert_fail(1u, "dbt", "stdb.cpp", 13043, 0);
      v102 = *((_DWORD *)this + 618);
      if ( v102 < 0 )
      {
        utassert_fail(1u, "m_RecoverySeconds >= 0", "stdb.cpp", 13044, 0);
        v102 = *((_DWORD *)this + 618);
      }
      DBTABLE::SetRecoveryTime(v101, v102);
    }
    if ( (*((_DWORD *)this + 604) & 0xD7D7FF7C) != 0 || (*((_DWORD *)this + 603) & 0xD7D7FF7C) != 0 )
    {
      REStatFromDbRegAttr = GetREStatFromDbRegAttr((const struct MDAttrDbReg *)v474);
      v105 = *((_DWORD *)this + 603) & REStatFromDbRegAttr;
      if ( (*((_BYTE *)this + 2412) & (unsigned __int8)REStatFromDbRegAttr & 4) != 0
        || (*((_BYTE *)this + 2416) & 4) != 0 && (REStatFromDbRegAttr & 4) == 0 )
      {
        v203 = 1;
      }
      if ( v20
        && (v217 = *(_BYTE *)(GetXdbServerGlobals(v105, v104) + 12004)) != 0
        && *(_QWORD *)(v20 + 5320)
        && v229 != 27 )
      {
        FidoGLMController = DBTABLE::GetFidoGLMController((DBTABLE *)v20);
        if ( (*(unsigned __int8 (__fastcall **)(struct IFidoGLMController *))(*(_QWORD *)FidoGLMController + 152LL))(FidoGLMController) )
          utassert_fail(1u, "!dbtable->GetFidoGLMController()->FIsFidoGlmServer()", "stdb.cpp", 14534, 0);
        v313 = &v504;
        v504 = 0;
        v505 = 0;
        v314 = v507;
        v107 = 2;
        v286 = 2;
        v108 = v507;
        for ( i = v507; ; i = v108 )
        {
          v109 = v107--;
          v286 = v107;
          if ( !v109 )
            break;
          v272 = 0;
          v273 = 0;
          v274 = 0;
          *(_QWORD *)v108 = 0;
          *((_WORD *)v108 + 4) = 0;
          *((_WORD *)v108 + 5) = 0;
          *(GUID *)(v108 + 12) = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
          v108 += 28;
        }
        v315 = v508;
        v110 = 3;
        v288 = 3;
        v111 = v508;
        for ( j = v508; ; j = v111 )
        {
          v112 = v110--;
          v288 = v110;
          if ( !v112 )
            break;
          v275 = 0;
          v276 = 0;
          v277 = 0;
          *(_QWORD *)v111 = 0;
          *((_WORD *)v111 + 4) = 0;
          *((_DWORD *)v111 + 3) = 0;
          *((_WORD *)v111 + 5) = 0;
          v111 += 16;
        }
        v316 = &v509;
        v317 = &v509;
        v509 = 0;
        v510 = 0;
        v511 = 0;
        v512 = 0;
        v113 = DBTABLE::GetFidoGLMController((DBTABLE *)v20);
        (*(void (__fastcall **)(struct IFidoGLMController *, char *, _QWORD))(*(_QWORD *)v113 + 288LL))(v113, v503, 0);
        DBTABLE::SetRelStat((DBTABLE *)v20, v506);
        v114 = 0;
        v115 = *((_QWORD *)this + 316);
        v116 = v115;
        v290 = v115;
        while ( v116 )
        {
          if ( *(_DWORD *)(v115 + 8) == 12 )
          {
            if ( *(_DWORD *)v116 == 10 || *(_DWORD *)v116 == 11 || (unsigned int)(*(_DWORD *)v116 - 12) <= 1 )
              v114 |= 1u;
            v116 = *(_QWORD *)(v116 + 32);
            v290 = v116;
          }
        }
        if ( v114 )
          ex_callprint(9128, 10, 1);
      }
      else
      {
        DBMgr::ChangeDBREOption(
          *(_QWORD *)(qword_102ECFB00 + 32),
          v87,
          v100,
          v193,
          *((_DWORD *)this + 604),
          *((_DWORD *)this + 603),
          v94);
        if ( (*((_DWORD *)this + 604) & 0x100) != 0 )
        {
          LOBYTE(v117) = 4;
          DBMgr::ChangeDBREOption(*(_QWORD *)(qword_102ECFB00 + 32), v87, 2, v117, 256, 0, v94);
        }
      }
    }
    v118 = *((_DWORD *)this + 617);
    if ( v118 )
    {
      v318 = &v230;
      v230 = v118;
      v184 = v94;
      CStmtAlterDB::SetDBCompatibilityLevel(this, v20, &v230, &v210);
    }
    v119 = *((_BYTE *)this + 2544);
    if ( (v119 & 0x20) != 0 )
    {
      ProcessTemporalHistoryRetentionDDL(v87, v100, (struct DBTABLE *)v20, (v119 & 0x40) != 0, v184);
      v192 = 1;
    }
    v120 = *((_BYTE *)this + 2545);
    if ( (v120 & 0x10) != 0 )
    {
      ProcessDataRetentionDDL(v87, v100, (struct DBTABLE *)v20, (v120 & 0x20) != 0, v184);
      v192 = 1;
    }
    v319 = v94;
    if ( v94 )
      (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v94)(v94, 1);
    v121 = (struct CChangeQDSDDLInfo *)*((_QWORD *)this + 330);
    if ( v121 )
    {
      v122 = ProcessChangeQDSDDL((struct DBTABLE *)v20, v121);
      v123 = v192;
      if ( v122 )
        v123 = 1;
      v192 = v123;
    }
    if ( *((_QWORD *)this + 331) )
      ProcessChangeATDDL(v87, v20);
    v124 = *((unsigned int *)this + 607);
    if ( (_DWORD)v124 != 3 && *(_DWORD *)(*(_QWORD *)(v20 + 4624) + 2136LL) != (_DWORD)v124 )
    {
      DBMgr::ChangeDBLCOption(*(_QWORD *)(qword_102ECFB00 + 32), v100, v124, &v210);
      v192 = 1;
    }
    if ( *((_QWORD *)this + 329) )
    {
      v125 = *(DBTABLE **)(*(_QWORD *)(v20 + 4624) + 1712LL);
      if ( (*((_BYTE *)v125 + 60) & 1) != 0 && !DBTABLE::IsCOWReplicaDatabase(v125) )
      {
        if ( !*((_BYTE *)qword_102EF3550 + 1428) || (v216 = *((_BYTE *)qword_102ECFB10 + 1420) >> 5, (v216 & 1) != 0) )
          ex_raise(494, 10, 16, 1);
      }
      ProcessChangeTrackingDDL(v87, v100, *((struct CChangeTrackDbDDLInfo **)this + 329));
      v192 = 1;
    }
    v126 = (struct StretchDbDDLInfo *)*((_QWORD *)this + 332);
    if ( v126 )
    {
      ProcessStretchDDL(v87, v100, v126);
      v192 = 1;
    }
    v127 = *((_BYTE *)this + 2545);
    if ( v127 < 0 )
    {
      if ( *((_BYTE *)qword_102EF3550 + 204) || (v227 = *((_BYTE *)qword_102ECFB10 + 801) >> 6, (v227 & 1) != 0) )
      {
        v128 = ProcessDataTieredDDL(v87, v100, (v127 & 0x40) != 0);
        v129 = v192;
        if ( v128 )
          v129 = 1;
        v192 = v129;
      }
      else
      {
        ex_raise(196, 17, 16, 1);
      }
    }
    v130 = *((unsigned int *)this + 613);
    if ( (_DWORD)v130 )
    {
      LODWORD(v190) = *((_DWORD *)this + 568);
      DBMgr::ChangeADROption(*(_QWORD *)(qword_102ECFB00 + 32), v100, v130, &v210, v87, *((_QWORD *)this + 285), v190);
      v192 = 1;
    }
    v131 = *((unsigned int *)this + 615);
    if ( (_DWORD)v131 )
    {
      DBMgr::ChangeOLOption(*(_QWORD *)(qword_102ECFB00 + 32), v100, v131, &v210);
      v192 = 1;
    }
    v132 = *((unsigned __int8 *)this + 2456);
    if ( (_BYTE)v132 )
    {
      DBMgr::ChangeSPDOption(*(_QWORD *)(qword_102ECFB00 + 32), v100, v132, &v210);
      v192 = 1;
    }
    v133 = *((unsigned __int8 *)this + 2457);
    if ( (_BYTE)v133 )
    {
      DBMgr::ChangeSuspendForSnapshotBackupOption(*(_QWORD *)(qword_102ECFB00 + 32), v100, v133, &v210);
      v192 = 1;
    }
    v134 = *((unsigned __int8 *)this + 2464);
    if ( (_BYTE)v134 )
    {
      DBMgr::ChangeInMemorydbOption(*(_QWORD *)(qword_102ECFB00 + 32), v100, v134, &v210);
      v192 = 1;
    }
    if ( *((_DWORD *)this + 640) )
    {
      if ( FSystemDatabase(*((const wchar_t **)this + 276), *((_DWORD *)this + 554), v100, 1) )
      {
        v135 = LookupOptionName(47, (struct opttype *)&OptDBOptions);
        v136 = -1;
        do
          ++v136;
        while ( v135[v136] );
        v320 = 2 * v136;
        LODWORD(v190) = *((_DWORD *)this + 554);
        LODWORD(v184) = 2 * v136;
        ex_raise(50, 58, 16, 11, v184, v135, v190, *((_QWORD *)this + 276));
      }
      ProcessMixedPageAllocationSetting(v87, v100, *((unsigned int *)this + 640));
      v192 = 1;
    }
    v137 = *((_BYTE *)this + 2545);
    if ( (v137 & 8) != 0 )
    {
      ProcessScalableTempdbSetting(v87, v100, (v137 & 4) != 0);
      v192 = 1;
    }
    if ( (*((_DWORD *)this + 606) & 0x900000) != 0 )
    {
      v138 = (void (__fastcall ***)(_QWORD, _QWORD, _BYTE *, _QWORD))(*(__int64 (__fastcall **)(struct IMetadataAccess *))(*(_QWORD *)v87 + 72LL))(v87);
      memset_0(v500, 0, 0x188u);
      v501 = -1;
      (**v138)(v138, *(unsigned __int16 *)(v20 + 40), v500, 0);
      if ( (v502 & 8) != 0 )
        ex_callprint(33416, 10, 2);
    }
    if ( v20 )
    {
      if ( !(unsigned int)DBTABLE::GetCurrentState(v20) )
      {
        FFtSql = GetFFtSql();
        if ( (**(unsigned __int8 (__fastcall ***)(struct IFFtSql *))FFtSql)(FFtSql) )
        {
          if ( v208 != v207 || v200 != v201 )
          {
            LODWORD(v188) = 0;
            LODWORD(v184) = 1;
            v140 = (*(__int64 (__fastcall **)(struct IMetadataAccess *, _QWORD, _QWORD, _QWORD, struct IFTCatList *, struct Worker *))(*(_QWORD *)v87 + 56LL))(
                     v87,
                     *(unsigned __int16 *)(v20 + 40),
                     0,
                     0,
                     v184,
                     v188);
            v486[0] = 0;
            v487 = 0;
            v488 = 0;
            v489 = 0;
            v491 = 0;
            v492 = 0;
            memset_0(v490, 0, sizeof(v490));
            if ( (*(unsigned __int8 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v140 + 1216LL))(v140, v486) )
            {
              v202 = 0;
              v262 = 0;
              if ( v487 && (!v208 && v207 == 5 || (v200 & 0x1000) != 0 && (v201 & 0x1000) == 0) )
              {
                v487 = 0;
LABEL_387:
                v202 = 1;
                v492 |= 1u;
                v141 = GetFFtSql();
                v142 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v212 + 432LL))(v212);
                LOBYTE(v190) = 0;
                LOBYTE(v188) = 0;
                LOBYTE(v184) = 1;
                (*(void (__fastcall **)(struct IFFtSql *, __int64, __int64, _WORD *, _DWORD, _DWORD, struct IMetadataAccess *))(*(_QWORD *)v141 + 24LL))(
                  v141,
                  v20,
                  v142,
                  v486,
                  (_DWORD)v184,
                  (_DWORD)v188,
                  v190);
                goto LABEL_388;
              }
              if ( (v200 & 0x400) != 0 && (v201 & 0x400) == 0 && v487 == 2 )
              {
                v487 = 1;
                goto LABEL_387;
              }
            }
          }
        }
      }
    }
LABEL_388:
    v241 = 0;
    if ( (*((_DWORD *)this + 602) & 0x809E00) == 0 && (*((_DWORD *)this + 601) & 0x809E00) == 0 )
    {
      if ( *((_QWORD *)this + 319) )
      {
        if ( (v143 = *(_QWORD *)(v20 + 4624), v144 = *(_QWORD *)(v143 + 1712), *(_DWORD *)(v144 + 784))
          && (*(_QWORD *)(v144 + 788) != *(_QWORD *)&x_AG_DB_IdBad.Data1
           || *(_QWORD *)(v144 + 796) != *(_QWORD *)x_AG_DB_IdBad.Data4)
          && *(_BYTE *)(v143 + 8272)
          || *(_DWORD *)(v20 + 1648) && !DBTABLE::IsOnline((DBTABLE *)v20) )
        {
          LODWORD(v184) = *(_DWORD *)(v20 + 928);
          ex_raise(334, 46, 16, 1, v184, v20 + 936);
        }
      }
      v145 = 0;
      v231 = 0;
      v146 = 0;
      for ( k = 0; ; k = v146 )
      {
        v231 = (int)v146;
        if ( (int)k >= 5 )
          break;
        if ( *((_BYTE *)this + 8 * (int)k + 2672) )
        {
          v205 = (int)v146;
          goto LABEL_404;
        }
        v146 = (const struct CCompExecCtxtStmt *)(unsigned int)((_DWORD)k + 1);
      }
      v205 = -1;
LABEL_404:
      if ( !*((_QWORD *)this + 333) && v205 < 0 )
      {
LABEL_425:
        if ( *((_QWORD *)this + 319) )
        {
          v152 = GetFFtSql();
          if ( (**(unsigned __int8 (__fastcall ***)(struct IFFtSql *))v152)(v152) )
          {
            v153 = GetFFtSql();
            v154 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v212 + 432LL))(v212);
            LOBYTE(v190) = 0;
            LOBYTE(v188) = 1;
            LOBYTE(v184) = 1;
            (*(void (__fastcall **)(struct IFFtSql *, __int64, __int64, _QWORD, struct IFTCatList *, struct Worker *, struct IMetadataAccess *))(*(_QWORD *)v153 + 24LL))(
              v153,
              v20,
              v154,
              *((_QWORD *)this + 319),
              v184,
              v188,
              v190);
          }
        }
        if ( *((_DWORD *)this + 634) )
        {
          v155 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(qword_102ECFB00 + 43248) + 32LL))(*(_QWORD *)(qword_102ECFB00 + 43248));
          (*(void (__fastcall **)(__int64, struct IMetadataAccess *, __int64, _QWORD))(*(_QWORD *)v155 + 24LL))(
            v155,
            v87,
            v20,
            *((unsigned int *)this + 634));
        }
        if ( v192 )
        {
          v156 = (struct BaseXact *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v212 + 432LL))(v212);
          DBMgr::SyncBootPageWithDbReg((struct DBTABLE *)v20, v156, 0);
        }
        if ( v203 )
        {
          if ( (*((_BYTE *)this + 2416) & 4) != 0 )
          {
            MatchingPartitionIndexViewHelper::CreateMPIdxViews(v209, k, v87, v100);
          }
          else if ( (*((_BYTE *)this + 2412) & 4) != 0 )
          {
            MatchingPartitionIndexViewHelper::DropAllMPIdxViews(v146, k, v87, v100);
          }
        }
        v214 = 0;
        if ( v87 )
          (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v87)(v87, 1);
        CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v210, 0);
        if ( v145 || v205 >= 0 )
        {
          CheckpointDB(v100, 0, 0);
LABEL_511:
          if ( v20 && (v192 || v241) )
            DBTABLE::RefreshDbOptions((DBTABLE *)v20, 0);
LABEL_515:
          if ( v192 )
          {
            LOBYTE(v157) = 1;
            CCache::RemoveByDbid(v100, 15, v157);
          }
          if ( v196 )
            unlockdb(v100, 43, v193);
          v215 = v209;
          v215 = *(struct CCompExecCtxt **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset);
          v178 = *(unsigned __int16 *)(*((_QWORD *)v215 + 10) + 8LL);
          if ( v178 != v194 )
          {
            v215 = 0;
            DBMgr::TryToClose(*(_QWORD *)(qword_102ECFB00 + 32), 0);
          }
          if ( v234 )
          {
            v327 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
            FullTextRunDelayOperation(v178, 1, 0, &v327, v234);
          }
          if ( v228 )
            (*(void (__fastcall **)(struct IFidoGLMController *))(*(_QWORD *)v228 + 24LL))(v228);
          ExcHandler::~ExcHandler((ExcHandler *)v332);
          v179 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v180 = *(struct Worker **)(v179 + 256);
          if ( !v180 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v180 = *(struct Worker **)(v179 + 256);
          }
          if ( *((_DWORD *)v180 + 139) )
            ExceptionPostCatchActions(v180);
          if ( v234 )
            (**(void (__fastcall ***)(struct IFTCatList *))v234)(v234);
          if ( v199 )
          {
            v199 = 0;
            ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
          }
          if ( (_DWORD)v210 )
            goto LABEL_534;
          goto LABEL_535;
        }
LABEL_510:
        v100 = v195;
        goto LABEL_511;
      }
      if ( DBTABLE::IsOffline((DBTABLE *)v20) )
      {
        LODWORD(v184) = *(_DWORD *)(v20 + 928);
        ex_raise(9, 42, 14, 6, v184, v20 + 936);
      }
      v238 = *(_DWORD *)(v20 + 3888);
      v148 = v238;
      if ( v238 != v479 )
      {
        LODWORD(v184) = *((_DWORD *)this + 554);
        ex_raise(128, 43, 16, 1, v184, *((_QWORD *)this + 276));
      }
      v149 = (_DWORD *)*((_QWORD *)this + 333);
      if ( v148 == 1 )
      {
        if ( v149 && !*v149 )
        {
          if ( v205 >= 0 )
          {
            _mm_lfence();
            LODWORD(v184) = *((_DWORD *)&off_10303F0C0 + 4 * v205 + 2);
            ex_raise(128, 7, 16, 1, v184, (&off_10303F0C0)[2 * v205]);
          }
          v145 = 1;
          goto LABEL_423;
        }
      }
      else
      {
        if ( v149 && *v149 )
        {
          v145 = 1;
          if ( (v484 & 2) != 0
            || (v484 & 4) != 0
            || (v484 & 8) != 0
            || (v484 & 0x10) != 0
            || (v484 & 0x20) != 0
            || (v484 & 0x40) != 0
            || (v485 & 1) != 0 )
          {
            v150 = 38;
            goto LABEL_422;
          }
          if ( v484 < 0 )
          {
            v150 = 46;
LABEL_422:
            LODWORD(v184) = *((_DWORD *)this + 554);
            ex_raise(128, v150, 16, 1, v184, *((_QWORD *)this + 276));
          }
LABEL_423:
          v151 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v212 + 432LL))(v212);
          LOBYTE(v184) = 0;
          DBMgr::ErrorIsCDBAllowed(1, 1, 0, 0, (_DWORD)v184, v151);
          v100 = v194;
          v195 = v194;
          v87 = v214;
          CStmtAlterDB::ProcessContainedDBDDL(
            this,
            v209,
            v214,
            v194,
            (const struct MDAttrDbReg *)v474,
            *((struct CContainedDatabaseDDLInfo **)this + 333),
            (CStmtAlterDB *)((char *)this + 2672));
          v192 = 1;
LABEL_424:
          v20 = (__int64)v197;
          goto LABEL_425;
        }
        if ( v205 >= 0 )
        {
          _mm_lfence();
          LODWORD(v184) = *((_DWORD *)&off_10303F0C0 + 4 * v205 + 2);
          ex_raise(128, 7, 16, 1, v184, (&off_10303F0C0)[2 * v205]);
        }
      }
      v145 = 0;
      if ( v205 < 0 )
      {
        v100 = v194;
        v195 = v194;
        v87 = v214;
        goto LABEL_424;
      }
      goto LABEL_423;
    }
    if ( (*((_DWORD *)this + 601) & 0x400) != 0 && (v481 & 0x20) != 0 )
    {
      LODWORD(v184) = *((_DWORD *)this + 554);
      ex_raise(50, 63, 16, 1, v184, *((_QWORD *)this + 276));
    }
    if ( v204 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v271 + 88LL))(v271, v100);
    v214 = 0;
    v321 = v87;
    if ( v87 )
      (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v87)(v87, 1);
    CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v210, 0);
    DBMgr::ChangeDBState(
      *(DBMgr **)(qword_102ECFB00 + 32),
      v100,
      (const unsigned int *)this + 602,
      (const unsigned int *)this + 601,
      *((_DWORD *)this + 635));
    v265 = qword_102ECFB00;
    v158 = *(_QWORD *)(qword_102ECFB00 + 32);
    v291 = v158;
    switch ( v100 )
    {
      case 0x7FFCu:
        v20 = *(_QWORD *)(v158 + 104);
        break;
      case 0x7FFDu:
        v20 = *(_QWORD *)(v158 + 112);
        break;
      case 0x7FFFu:
        v20 = *(_QWORD *)(v158 + 88);
        break;
      default:
        if ( v100 > *(_DWORD *)(v158 + 76) || !v100 )
          goto LABEL_515;
        _mm_lfence();
        v195 = v194;
        v20 = *(_QWORD *)(*(_QWORD *)(v291 + 40) + 8LL * (int)(v194 - 1));
        break;
    }
    if ( !v20 )
      goto LABEL_510;
    if ( *(_DWORD *)(v20 + 3888) != v479 )
      scierrlog(0x322Bu, *((unsigned int *)this + 554), *((_QWORD *)this + 276));
    if ( (unsigned int)DBTABLE::GetCurrentState(v20) )
      goto LABEL_510;
    v159 = GetSEStatFromDbRegAttr((const struct MDAttrDbReg *)v474);
    v201 = v159;
    v200 = v159;
    v200 = *((_DWORD *)this + 602) | v159 & ~*((_DWORD *)this + 601);
    v160 = v200;
    v161 = GetAvailabilityFromStatus(v159);
    v208 = v161;
    v207 = GetAvailabilityFromStatus(v160);
    if ( v161 == v207 && v160 == v159
      || (v162 = GetFFtSql(), !(**(unsigned __int8 (__fastcall ***)(struct IFFtSql *))v162)(v162)) )
    {
LABEL_500:
      if ( (v159 & 0x1000) != 0 && (v160 & 0x1000) == 0 )
      {
        v268 = &AutoReadOnlyIMA::`vftable';
        v269 = 0;
        v215 = (struct CCompExecCtxt *)&v270;
        v270 = 0;
        v173 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v174 = *(_QWORD *)(v173 + 256);
        if ( !v174 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v174 = *(_QWORD *)(v173 + 256);
        }
        v175 = *(_QWORD *)(v174 + 1000);
        AutoReadOnlyXact::BeginCompatibleXact((AutoReadOnlyXact *)&v270, L"StretchDbStateChange", 40, 0);
        ((void (__fastcall *)(void ***, __int64))*v268)(&v268, v175);
        LODWORD(v188) = 0;
        v100 = v194;
        v176 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int, struct Worker *))(*(_QWORD *)v269 + 56LL))(
                 v269,
                 v194,
                 0,
                 0,
                 1,
                 v188);
        v240 = 0;
        v177 = v176 && (*(unsigned __int8 (__fastcall **)(__int64, int *))(*(_QWORD *)v176 + 1688LL))(v176, &v240);
        AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v268);
        if ( v177 )
        {
          EnqueueStretchDbid(v194);
          EnqueueRepopulateStretchSchemaTaskQueueTask(v194);
        }
        goto LABEL_511;
      }
      goto LABEL_510;
    }
    v211 = 1;
    v265 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset);
    *(_QWORD *)&v212 = *(_QWORD *)(v265 + 144);
    v265 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset);
    v163 = *(_BYTE *)(v265 + 152);
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v212 + 464LL))(v212) )
    {
      if ( v163 && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v212 + 488LL))(v212) )
        utassert_fail(
          1u,
          "rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()",
          "automsqlxact.cpp",
          235,
          0);
      (*(void (__fastcall **)(_QWORD, __int64, __int64, char *))(*(_QWORD *)v212 + 232LL))(
        v212,
        2,
        1,
        (char *)&v210 + 4);
      v211 = 1;
      LODWORD(v210) = 3;
    }
    else
    {
      LOBYTE(v190) = 0;
      LODWORD(v188) = 1;
      (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64, __int64, int, struct Worker *, struct IMetadataAccess *, _QWORD, bool))(*(_QWORD *)v212 + 8LL))(
        v212,
        L"FILESTREAM",
        20,
        1,
        2,
        v188,
        v190,
        0,
        v163 != 0);
      LODWORD(v210) = 1;
    }
    v278 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v212 + 432LL))(v212);
    v164 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v165 = *(_QWORD *)(v164 + 256);
    if ( !v165 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v165 = *(_QWORD *)(v164 + 256);
    }
    v166 = ((__int64 (__fastcall *)(_QWORD, __int64, const char *, __int64))g_metadataFactory)(
             *(_QWORD *)(v165 + 1000),
             v278,
             "sql\\ntdbms\\msql\\proc\\stdb.cpp",
             14912);
    v235 = v166;
    v280 = v166;
    LODWORD(v188) = 0;
    v195 = v194;
    v167 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int, struct Worker *))(*(_QWORD *)v166 + 56LL))(
             v166,
             v194,
             0,
             0,
             1,
             v188);
    v493[0] = 0;
    v494 = 0;
    v495 = 0;
    v496 = 0;
    v498 = 0;
    v499 = 0;
    memset_0(v497, 0, sizeof(v497));
    if ( (*(unsigned __int8 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v167 + 1216LL))(v167, v493) )
    {
      if ( !v207 && v208 )
      {
        LOWORD(v160) = v200;
        LOWORD(v159) = v201;
LABEL_491:
        if ( v494 != v495 && ((v160 & 0x400) == 0 || v494 != 1) )
        {
          v494 = v495;
          v499 |= 1u;
        }
        v168 = GetFFtSql();
        v169 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v212 + 432LL))(v212);
        LOBYTE(v190) = 1;
        LOBYTE(v188) = 1;
        LOBYTE(v186) = 1;
        (*(void (__fastcall **)(struct IFFtSql *, __int64, __int64, _WORD *, int, _DWORD, struct IMetadataAccess *))(*(_QWORD *)v168 + 24LL))(
          v168,
          v20,
          v169,
          v493,
          v186,
          (_DWORD)v188,
          v190);
        goto LABEL_499;
      }
      LOWORD(v160) = v200;
      LOWORD(v159) = v201;
      if ( (v200 & 0x1000) == 0 && (v201 & 0x1000) != 0 || (v200 & 0x400) == 0 && (v201 & 0x400) != 0 )
        goto LABEL_491;
      v170 = GetFFtSql();
      v171 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v212 + 432LL))(v212);
      LOBYTE(v186) = 0;
      LOBYTE(v172) = 1;
      v239 = (*(__int64 (__fastcall **)(struct IFFtSql *, __int64, __int64, __int64, int))(*(_QWORD *)v170 + 40LL))(
               v170,
               v20,
               v171,
               v172,
               v186);
      if ( v239 >= 0 )
      {
LABEL_499:
        v280 = 0;
        (**(void (__fastcall ***)(__int64, __int64))v166)(v166, 1);
        CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v210, 0);
        goto LABEL_500;
      }
      _mm_lfence();
      LODWORD(v188) = v239;
      LODWORD(v187) = 13030;
      scierrlogwithstate(0x827Du, 10, 15, 13105, v187, v188);
      v195 = v194;
      v166 = v235;
    }
    LOWORD(v159) = v201;
    LOWORD(v160) = v200;
    goto LABEL_499;
  }
  v89 = v481 >> 7;
  v90 = v481 & 0x7F;
LABEL_255:
  v481 = v90;
  if ( v89 != v90 >> 7 )
  {
    v232 = *(_DWORD *)(v20 + 2256);
    v91 = v473;
    v92 = v474;
    v93 = 3;
    do
    {
      *v91 = *v92;
      v91[1] = v92[1];
      v91[2] = v92[2];
      v91[3] = v92[3];
      v91[4] = v92[4];
      v91[5] = v92[5];
      v91[6] = v92[6];
      v91 += 8;
      *(v91 - 1) = v92[7];
      v92 += 8;
      --v93;
    }
    while ( v93 );
    *(_QWORD *)v91 = *(_QWORD *)v92;
    LOBYTE(v184) = 1;
    DBMgr::UpdateLogicalWriteStatus(*(_QWORD *)(qword_102ECFB00 + 32), v20, v473, v233, (_DWORD)v184);
  }
  v214 = 0;
  if ( v87 )
    (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v87)(v87, 1);
  CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v210, 0);
  if ( v196 )
    unlockdb(TardisDbId, 43, v193);
  if ( v228 )
    (*(void (__fastcall **)(struct IFidoGLMController *))(*(_QWORD *)v228 + 24LL))(v228);
  ExcHandler::~ExcHandler((ExcHandler *)v332);
  if ( v234 )
    (**(void (__fastcall ***)(struct IFTCatList *))v234)(v234);
  if ( v199 )
  {
    v199 = 0;
    ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
  }
  if ( (_DWORD)v210 )
LABEL_534:
    CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v210, 0);
LABEL_535:
  AutoOverrideMsqlXact::~AutoOverrideMsqlXact((AutoOverrideMsqlXact *)&v292);
}

```

## disassembly

```asm
0x10129a860  push    rbx
0x10129a862  push    rsi
0x10129a863  push    rdi
0x10129a864  push    r12
0x10129a866  push    r13
0x10129a868  push    r14
0x10129a86a  push    r15
0x10129a86c  mov     eax, 2B90h
0x10129a871  call    _alloca_probe
0x10129a876  sub     rsp, rax
0x10129a879  mov     [rsp+2BC8h+var_2770], 0FFFFFFFFFFFFFFFEh
0x10129a885  mov     rax, cs:__security_cookie
0x10129a88c  xor     rax, rsp
0x10129a88f  mov     [rsp+2BC8h+var_48], rax
0x10129a897  mov     [rsp+2BC8h+var_2A10], r8
0x10129a89f  mov     r15, rdx
0x10129a8a2  mov     [rsp+2BC8h+var_2AC0], rdx
0x10129a8aa  mov     r12, rcx
0x10129a8ad  mov     [rsp+2BC8h+var_2908], rcx
0x10129a8b5  mov     [rsp+2BC8h+var_2910], rdx
0x10129a8bd  xor     edi, edi
0x10129a8bf  mov     [rsp+2BC8h+var_2B04], edi
0x10129a8c6  mov     [rsp+2BC8h+var_2B07], 5
0x10129a8ce  mov     [rsp+2BC8h+var_2AF8], dil
0x10129a8d6  mov     [rsp+2BC8h+var_2AF0], rdi
0x10129a8de  xorps   xmm0, xmm0
0x10129a8e1  movdqu  [rsp+2BC8h+var_28A8], xmm0
0x10129a8ea  mov     [rsp+2BC8h+var_2898], rdi
0x10129a8f2  mov     [rsp+2BC8h+var_288C], edi
0x10129a8f9  mov     [rsp+2BC8h+var_2AB8], rdi
0x10129a901  mov     r13d, 1
0x10129a907  mov     [rsp+2BC8h+var_2AB0], r13d
0x10129a90f  movdqu  [rsp+2BC8h+var_2AA8], xmm0
0x10129a918  mov     [rsp+2BC8h+var_2AE4], edi
0x10129a91f  mov     [rsp+2BC8h+var_2B08], dil
0x10129a927  mov     [rsp+2BC8h+var_2AD7], dil
0x10129a92f  xor     edx, edx; Val
0x10129a931  mov     r8d, 188h; Size
0x10129a937  lea     rcx, [rsp+2BC8h+var_F28]; void *
0x10129a93f  call    memset_0
0x10129a944  mov     [rsp+2BC8h+var_DB0], 0FFFFFFFFh
0x10129a94f  mov     [rsp+2BC8h+var_2A40], rdi
0x10129a957  mov     rax, cs:__imp_?hdl_prntbackout@@YAHHHHHPEAD@Z; hdl_prntbackout(int,int,int,int,char *)
0x10129a95e  mov     [rsp+2BC8h+var_2AD6], dil
0x10129a966  mov     [rsp+2BC8h+var_2AE6], dil
0x10129a96e  mov     [rsp+2BC8h+var_2A4C], edi
0x10129a975  mov     [rsp+2BC8h+var_2AD0], edi
0x10129a97c  lea     rcx, [rsp+2BC8h+var_A8]
0x10129a984  mov     [rsp+2BC8h+var_F10], rcx
0x10129a98c  lea     rcx, ?CUserArguments@CTraceDataSTVFInfo@@UEBAHXZ; CTraceDataSTVFInfo::CUserArguments(void)
0x10129a993  cmp     [r12+990h], edi
0x10129a99b  cmovnz  rax, rcx
0x10129a99f  xor     edx, edx; unsigned __int16
0x10129a9a1  mov     [rsp+2BC8h+var_2BA0], rdi; struct Worker *
0x10129a9a6  mov     [rsp+2BC8h+var_2BA8], rax; int (*)(int, int, int, int, char *)
0x10129a9ab  xor     r9d, r9d; unsigned __int8
0x10129a9ae  xor     r8d, r8d; unsigned __int8
0x10129a9b1  lea     rcx, [rsp+2BC8h+var_2758]; this
0x10129a9b9  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x10129a9be  nop
0x10129a9bf  lea     rcx, [rsp+2BC8h+var_28A8]; this
0x10129a9c7  call    ?InitializeAndOverride@AutoOverrideMsqlXact@@QEAAXXZ; AutoOverrideMsqlXact::InitializeAndOverride(void)
0x10129a9cc  mov     [rsp+2BC8h+var_2AB0], r13d
0x10129a9d4  mov     rdx, gs:58h
0x10129a9dd  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10129a9e4  mov     ecx, [rax]
0x10129a9e6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10129a9ed  mov     eax, [rax]
0x10129a9ef  add     rax, [rdx+rcx*8]
0x10129a9f3  mov     rax, [rax]
0x10129a9f6  mov     [rsp+2BC8h+var_2A38], rax
0x10129a9fe  mov     rax, [rax+90h]
0x10129aa05  mov     qword ptr [rsp+2BC8h+var_2AA8], rax
0x10129aa0d  mov     rdx, gs:58h
0x10129aa16  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10129aa1d  mov     ecx, [rax]
0x10129aa1f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10129aa26  mov     eax, [rax]
0x10129aa28  add     rax, [rdx+rcx*8]
0x10129aa2c  mov     rax, [rax]
0x10129aa2f  mov     [rsp+2BC8h+var_2A38], rax
0x10129aa37  mov     [rsp+2BC8h+var_2920], r13d
0x10129aa3f  mov     rcx, qword ptr [rsp+2BC8h+var_2AA8]
0x10129aa47  mov     rax, [rcx]
0x10129aa4a  call    qword ptr [rax+1D0h]
0x10129aa50  mov     rcx, qword ptr [rsp+2BC8h+var_2AA8]
0x10129aa58  test    al, al
0x10129aa5a  mov     rax, [rcx]
0x10129aa5d  jz      short loc_10129AAC1
0x10129aa5f  call    qword ptr [rax+1E8h]
0x10129aa65  test    al, al
0x10129aa67  jz      short loc_10129AA8B
0x10129aa69  mov     [rsp+2BC8h+var_2BA8], rdi
0x10129aa6e  mov     r9d, 0EBh
0x10129aa74  lea     r8, aAutomsqlxactCp; "automsqlxact.cpp"
0x10129aa7b  lea     rdx, ?szExpression@?9??BeginNestedXact@CAutoMsqlXact@@QEAAXPEB_WHW4ReadWriteMode@CMsqlXact@@W4DistributionMode@4@W4NestedXactOption@4@W4CTRSupportOption@4@@Z@4QBDB; "rwMode == CMsqlXact::ReadOnly || ctrOpt"...
0x10129aa82  mov     ecx, r13d
0x10129aa85  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10129aa8b  mov     rcx, qword ptr [rsp+2BC8h+var_2AA8]
0x10129aa93  mov     rax, [rcx]
0x10129aa96  lea     r9, [rsp+2BC8h+var_2AB8+4]
0x10129aa9e  mov     r8d, r13d
0x10129aaa1  mov     edx, 2
0x10129aaa6  call    qword ptr [rax+0E8h]
0x10129aaac  mov     [rsp+2BC8h+var_2AB0], r13d
0x10129aab4  mov     dword ptr [rsp+2BC8h+var_2AB8], 3
0x10129aabf  jmp     short loc_10129AAF8
0x10129aac1  mov     [rsp+2BC8h+var_2B88], r13d
0x10129aac6  mov     [rsp+2BC8h+var_2B90], rdi
0x10129aacb  mov     byte ptr [rsp+2BC8h+var_2B98], 0
0x10129aad0  mov     dword ptr [rsp+2BC8h+var_2BA0], r13d
0x10129aad5  mov     dword ptr [rsp+2BC8h+var_2BA8], 2
0x10129aadd  mov     r9d, r13d
0x10129aae0  mov     r8d, 3Eh ; '>'
0x10129aae6  lea     rdx, aCstmtalterdbCh; "CStmtAlterDB::ChangeStateOption"
0x10129aaed  call    qword ptr [rax+8]
0x10129aaf0  mov     dword ptr [rsp+2BC8h+var_2AB8], r13d
0x10129aaf8  mov     rcx, qword ptr [rsp+2BC8h+var_2AA8]
0x10129ab00  mov     rax, [rcx]
0x10129ab03  call    qword ptr [rax+1B0h]
0x10129ab09  mov     [rsp+2BC8h+var_2A48], rax
0x10129ab11  mov     rdx, [rax]
0x10129ab14  mov     rcx, rax
0x10129ab17  call    qword ptr [rdx+10h]
0x10129ab1a  mov     rdx, gs:58h
0x10129ab23  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10129ab2a  mov     ecx, [rax]
0x10129ab2c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10129ab33  mov     ebx, [rax]
0x10129ab35  add     rbx, [rdx+rcx*8]
0x10129ab39  mov     rcx, [rbx+100h]
0x10129ab40  test    rcx, rcx
0x10129ab43  jnz     short loc_10129AB52
0x10129ab45  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10129ab4b  mov     rcx, [rbx+100h]
0x10129ab52  mov     r9d, 35C2h
0x10129ab58  lea     r8, aSqlNtdbmsMsqlP_120; "sql\\ntdbms\\msql\\proc\\stdb.cpp"
0x10129ab5f  mov     rdx, [rsp+2BC8h+var_2A48]
0x10129ab67  mov     rcx, [rcx+3E8h]
0x10129ab6e  mov     rax, cs:__imp_?g_metadataFactory@@3UMetadataFactory@@A; MetadataFactory g_metadataFactory
0x10129ab75  call    qword ptr [rax]
0x10129ab77  mov     [rsp+2BC8h+var_2A70], rax
0x10129ab7f  mov     [rsp+2BC8h+var_2A90], rax
0x10129ab87  mov     rdx, [rax]
0x10129ab8a  mov     rcx, rax
0x10129ab8d  call    qword ptr [rdx+48h]
0x10129ab90  mov     rbx, rax
0x10129ab93  mov     [rsp+2BC8h+var_2950], rax
0x10129ab9b  mov     r9, [rax]
0x10129ab9e  mov     r8d, [r12+8A8h]
0x10129aba6  mov     rdx, [r12+8A0h]
0x10129abae  mov     rcx, rax
0x10129abb1  call    qword ptr [r9+8]
0x10129abb5  mov     esi, eax
0x10129abb7  mov     [rsp+2BC8h+var_2B04], eax
0x10129abbe  test    eax, eax
0x10129abc0  jnz     short loc_10129ABEF
0x10129abc2  mov     rcx, [r12+8A0h]
0x10129abca  mov     [rsp+2BC8h+var_2BA0], rcx
0x10129abcf  mov     ecx, [r12+8A8h]
0x10129abd7  mov     dword ptr [rsp+2BC8h+var_2BA8], ecx
0x10129abdb  lea     edx, [rax+0Bh]
0x10129abde  lea     ecx, [rax+32h]
0x10129abe1  lea     r9d, [rax+5]
0x10129abe5  lea     r8d, [rax+0Eh]
0x10129abe9  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10129abef  mov     [rsp+2BC8h+var_EFC], 55h ; 'U'
0x10129abfa  mov     rax, [rbx]
0x10129abfd  xor     r9d, r9d
0x10129ac00  lea     r8, [rsp+2BC8h+var_F28]
0x10129ac08  mov     edx, esi
0x10129ac0a  mov     rcx, rbx
0x10129ac0d  call    qword ptr [rax]
0x10129ac0f  test    al, al
0x10129ac11  jnz     short loc_10129AC42
0x10129ac13  mov     rax, [r12+8A0h]
0x10129ac1b  mov     [rsp+2BC8h+var_2BA0], rax
0x10129ac20  mov     eax, [r12+8A8h]
0x10129ac28  mov     dword ptr [rsp+2BC8h+var_2BA8], eax
0x10129ac2c  mov     edx, 0Bh
0x10129ac31  lea     ecx, [rdx+27h]
0x10129ac34  lea     r9d, [rdx-5]
0x10129ac38  lea     r8d, [rdx+3]
0x10129ac3c  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10129ac42  mov     rdx, gs:58h
0x10129ac4b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10129ac52  mov     ecx, [rax]
0x10129ac54  lea     r8, ds:0[rcx*8]
0x10129ac5c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10129ac63  mov     r9d, [rax]
0x10129ac66  mov     rax, [r8+rdx]
0x10129ac6a  mov     rcx, [rax+r9]
0x10129ac6e  mov     rax, [rcx+48h]
0x10129ac72  test    byte ptr [rax+10Eh], 4
0x10129ac79  jz      loc_10129AD16
0x10129ac7f  mov     rax, gs:58h
0x10129ac88  mov     rax, [r8+rax]
0x10129ac8c  mov     rcx, [rax+r9]
0x10129ac90  mov     [rsp+2BC8h+var_2A38], rcx
0x10129ac98  mov     [rsp+2BC8h+var_29C8], rcx
0x10129aca0  mov     [rsp+2BC8h+var_29C8], rcx
0x10129aca8  mov     rax, gs:58h
0x10129acb1  mov     rax, [r8+rax]
0x10129acb5  mov     rax, [r9+rax]
0x10129acb9  mov     [rsp+2BC8h+var_29C8], rax
0x10129acc1  mov     rax, [rax+50h]
0x10129acc5  movzx   ecx, word ptr [rax+8]
0x10129acc9  mov     [rsp+2BC8h+var_2900], ecx
0x10129acd0  mov     r14d, [rsp+2BC8h+var_2B04]
0x10129acd8  mov     [rsp+2BC8h+var_2B00], r14d
0x10129ace0  cmp     ecx, r14d
0x10129ace3  jz      short loc_10129AD26
0x10129ace5  mov     rax, [r12+8A0h]
0x10129aced  mov     [rsp+2BC8h+var_2BA0], rax
0x10129acf2  mov     eax, [r12+8A8h]
0x10129acfa  mov     dword ptr [rsp+2BC8h+var_2BA8], eax
0x10129acfe  mov     edx, 0Bh
0x10129ad03  lea     ecx, [rdx+27h]
0x10129ad06  lea     r9d, [rdx-1]
0x10129ad0a  lea     r8d, [rdx+3]
0x10129ad0e  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10129ad14  jmp     short loc_10129AD26
0x10129ad16  mov     r14d, [rsp+2BC8h+var_2B04]
0x10129ad1e  mov     [rsp+2BC8h+var_2B00], r14d
0x10129ad26  mov     eax, [r12+990h]
0x10129ad2e  dec     eax
0x10129ad30  cmp     eax, 1
0x10129ad33  ja      short loc_10129AD87
0x10129ad35  test    [rsp+2BC8h+var_DA7], 10h
0x10129ad3d  jz      short loc_10129AD87
0x10129ad3f  mov     rax, [r12+8A0h]
0x10129ad47  mov     [rsp+2BC8h+var_2B90], rax
0x10129ad4c  mov     eax, [r12+8A8h]
0x10129ad54  mov     dword ptr [rsp+2BC8h+var_2B98], eax
0x10129ad58  lea     rax, aVardecimalStor_1; "VARDECIMAL_STORAGEFORMAT"
0x10129ad5f  mov     [rsp+2BC8h+var_2BA0], rax
0x10129ad64  mov     [rsp+2BC8h+var_2BA8], 30h ; '0'
0x10129ad6d  mov     esi, 10h
0x10129ad72  lea     r9d, [rsi-7]
0x10129ad76  mov     r8d, esi
0x10129ad79  lea     edx, [rsi+2Ah]
0x10129ad7c  lea     ecx, [rsi+22h]
0x10129ad7f  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10129ad85  jmp     short loc_10129AD8C
0x10129ad87  mov     esi, 10h
0x10129ad8c  mov     [rsp+2BC8h+var_2AE0], edi
0x10129ad93  mov     [rsp+2BC8h+var_2ADC], edi
0x10129ad9a  mov     [rsp+2BC8h+var_2AC8], 7
0x10129ada5  mov     [rsp+2BC8h+var_2ACC], 7
0x10129adb0  mov     [rsp+2BC8h+var_2A60], rdi
0x10129adb8  mov     edx, r14d
0x10129adbb  lea     rcx, [rsp+2BC8h+var_2A60]
0x10129adc3  call    cs:__imp_?FGetFidoGLMController@@YA_NAEAV?$CAutoRefc@VIFidoGLMController@@@@K@Z; FGetFidoGLMController(CAutoRefc<IFidoGLMController> &,ulong)
0x10129adc9  test    al, al
0x10129adcb  jz      loc_10129AE5B
0x10129add1  mov     dl, 1
0x10129add3  xor     ecx, ecx
0x10129add5  call    cs:__imp_?GetDWFidoTxCtx@@YAPEAVDWFidoTxCtx@@PEAVXDES@@_N@Z; GetDWFidoTxCtx(XDES *,bool)
0x10129addb  mov     [rsp+2BC8h+var_2980], rax
0x10129ade3  mov     rax, [r12]
0x10129ade7  mov     rcx, r12
0x10129adea  call    qword ptr [rax+78h]
0x10129aded  mov     ecx, eax
0x10129adef  mov     [rsp+2BC8h+var_2BA8], rdi
0x10129adf4  xor     r9d, r9d
0x10129adf7  mov     r8, [rsp+2BC8h+var_2A60]
0x10129adff  lea     rdx, [rsp+2BC8h+var_2980]
0x10129ae07  call    cs:__imp_?StartDwFidoTran@@YAXW4FidoTransactionType@@PEAPEAVDWFidoTxCtx@@PEAVIFidoGLMController@@W4FidoTxTag@@PEAVFidoPointInTimeCtx@@@Z; StartDwFidoTran(FidoTransactionType,DWFidoTxCtx * *,IFidoGLMController *,FidoTxTag,FidoPointInTimeCtx *)
0x10129ae0d  mov     rdx, [rsp+2BC8h+var_2A60]
0x10129ae15  mov     rcx, [rsp+2BC8h+var_2980]
0x10129ae1d  call    cs:__imp_?GetTardisDbId@DWFidoTxCtx@@QEAAGPEAVIFidoGLMController@@@Z; DWFidoTxCtx::GetTardisDbId(IFidoGLMController *)
0x10129ae23  movzx   r14d, ax
0x10129ae27  mov     [rsp+2BC8h+var_2B00], r14d
0x10129ae2f  mov     [rsp+2BC8h+var_2B04], r14d
0x10129ae37  mov     rcx, [rsp+2BC8h+var_2A60]
0x10129ae3f  mov     rax, [rcx]
0x10129ae42  call    qword ptr [rax+98h]
0x10129ae48  mov     ecx, [rsp+2BC8h+var_2AD0]
0x10129ae4f  test    al, al
0x10129ae51  cmovz   ecx, esi
0x10129ae54  mov     [rsp+2BC8h+var_2AD0], ecx
0x10129ae5b  mov     dword ptr [rsp+2BC8h+var_2BA0], edi; unsigned int
0x10129ae5f  mov     byte ptr [rsp+2BC8h+var_2BA8], 0; bool
0x10129ae64  mov     r9b, 1; bool
0x10129ae67  xor     r8d, r8d; struct BaseXact *
0x10129ae6a  mov     edx, r14d; unsigned int
0x10129ae6d  lea     rcx, [rsp+2BC8h+var_2AE4]; this
0x10129ae75  call    ?FUse@CAutoDb@@QEAA_NKPEAVBaseXact@@_N1K@Z; CAutoDb::FUse(ulong,BaseXact *,bool,bool,ulong)
0x10129ae7a  test    al, al
0x10129ae7c  jnz     loc_10129B12E
0x10129ae82  mov     rax, cs:qword_102ECFB00
0x10129ae89  mov     ecx, [rax+30h]
0x10129ae8c  test    cl, 20h
0x10129ae8f  jnz     short loc_10129AE96
0x10129ae91  test    cl, 10h
0x10129ae94  jnz     short loc_10129AEC5
0x10129ae96  mov     rax, [r12+8A0h]
0x10129ae9e  mov     [rsp+2BC8h+var_2BA0], rax
0x10129aea3  mov     eax, [r12+8A8h]
0x10129aeab  mov     dword ptr [rsp+2BC8h+var_2BA8], eax
  ... truncated ...
```
