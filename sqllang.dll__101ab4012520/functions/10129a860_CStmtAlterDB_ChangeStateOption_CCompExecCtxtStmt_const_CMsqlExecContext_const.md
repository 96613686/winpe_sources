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
  __int64 v63; // rcx
  _DWORD *v64; // rsi
  __int64 v65; // rbx
  __int64 v66; // rax
  __int64 v67; // rbx
  __int64 v68; // rsi
  __int64 v69; // rbx
  __int64 v70; // rax
  int v71; // eax
  DWORD TickCount; // ebx
  signed int v73; // r8d
  DWORD v74; // eax
  struct CCompExecCtxt *v75; // r15
  DWORD v76; // ebx
  DWORD v77; // eax
  DWORD v78; // ebx
  signed int v79; // r8d
  DWORD v80; // eax
  DWORD v81; // ebx
  signed int v82; // r8d
  DWORD v83; // eax
  unsigned __int8 v84; // dl
  struct CCompExecCtxt *v85; // rbx
  struct IMetadataAccess *v86; // rsi
  __int64 v87; // rcx
  char v88; // cl
  unsigned __int8 v89; // al
  _OWORD *v90; // rcx
  _OWORD *v91; // rax
  __int64 v92; // rdx
  struct IMetadataAccess *v93; // rbx
  struct CCompExecCtxt *v94; // r14
  __int64 v95; // rcx
  __int64 v96; // rcx
  __int64 v97; // rax
  unsigned int v98; // r14d
  DBTABLE *v99; // r15
  int v100; // edx
  unsigned int REStatFromDbRegAttr; // eax
  __int64 v102; // rcx
  struct IFidoGLMController *FidoGLMController; // rax
  __int64 v104; // rdx
  _BYTE *v105; // rcx
  __int64 v106; // rax
  __int64 v107; // rdx
  _BYTE *v108; // rcx
  __int64 v109; // rax
  struct IFidoGLMController *v110; // rax
  char v111; // r8
  __int64 v112; // r9
  __int64 v113; // rdx
  __int64 v114; // r9
  int v115; // eax
  char v116; // r9
  char v117; // r9
  struct CChangeQDSDDLInfo *v118; // rdx
  char v119; // al
  char v120; // cl
  __int64 v121; // r8
  DBTABLE *v122; // rcx
  struct StretchDbDDLInfo *v123; // r8
  char v124; // r8
  bool v125; // al
  char v126; // cl
  __int64 v127; // r8
  __int64 v128; // r8
  __int64 v129; // r8
  __int64 v130; // r8
  __int64 v131; // r8
  const wchar_t *v132; // rax
  __int64 v133; // rcx
  char v134; // r8
  void (__fastcall ***v135)(_QWORD, _QWORD, _BYTE *, _QWORD); // rbx
  struct IFFtSql *FFtSql; // rax
  __int64 v137; // rbx
  struct IFFtSql *v138; // rbx
  __int64 v139; // rax
  __int64 v140; // rdx
  __int64 v141; // rcx
  char v142; // r15
  const struct CCompExecCtxtStmt *v143; // rcx
  struct CAutoMsqlXact *k; // rdx
  int v145; // ebx
  _DWORD *v146; // rax
  int v147; // edx
  __int64 v148; // rax
  struct IFFtSql *v149; // rax
  struct IFFtSql *v150; // rbx
  __int64 v151; // rax
  __int64 v152; // rax
  struct BaseXact *v153; // rax
  __int64 v154; // r8
  __int64 v155; // r13
  unsigned int v156; // r14d
  unsigned int v157; // esi
  int v158; // ebx
  struct IFFtSql *v159; // rax
  char v160; // bl
  __int64 v161; // rbx
  __int64 v162; // rcx
  __int64 v163; // r15
  __int64 v164; // rbx
  struct IFFtSql *v165; // rbx
  __int64 v166; // rax
  struct IFFtSql *v167; // rbx
  __int64 v168; // rax
  __int64 v169; // r9
  __int64 v170; // rbx
  __int64 v171; // rax
  __int64 v172; // rbx
  __int64 v173; // rax
  bool v174; // bl
  unsigned int v175; // ecx
  __int64 v176; // rbx
  struct Worker *v177; // rcx
  struct IFTCatList *v178; // [rsp+20h] [rbp-2BA8h]
  struct IFTCatList *v179; // [rsp+20h] [rbp-2BA8h]
  struct IFTCatList *v180; // [rsp+20h] [rbp-2BA8h]
  struct IFTCatList *v181; // [rsp+20h] [rbp-2BA8h]
  struct IFTCatList *v182; // [rsp+20h] [rbp-2BA8h]
  int v183; // [rsp+20h] [rbp-2BA8h]
  struct IFTCatList *v184; // [rsp+20h] [rbp-2BA8h]
  struct Worker *v185; // [rsp+28h] [rbp-2BA0h]
  struct IMetadataAccess *v186; // [rsp+30h] [rbp-2B98h]
  struct IMetadataAccess *v187; // [rsp+30h] [rbp-2B98h]
  int v188; // [rsp+88h] [rbp-2B40h]
  char v189; // [rsp+C0h] [rbp-2B08h]
  unsigned __int8 v190; // [rsp+C1h] [rbp-2B07h]
  unsigned int v191; // [rsp+C4h] [rbp-2B04h]
  unsigned int v192; // [rsp+C8h] [rbp-2B00h]
  char v193; // [rsp+D0h] [rbp-2AF8h]
  unsigned int *v194; // [rsp+D8h] [rbp-2AF0h]
  unsigned __int8 v195; // [rsp+E0h] [rbp-2AE8h]
  unsigned int v196; // [rsp+E4h] [rbp-2AE4h] BYREF
  int v197; // [rsp+E8h] [rbp-2AE0h]
  unsigned int v198; // [rsp+ECh] [rbp-2ADCh]
  char v199; // [rsp+F0h] [rbp-2AD8h]
  char v200; // [rsp+F1h] [rbp-2AD7h]
  char v201; // [rsp+F2h] [rbp-2AD6h]
  int v202; // [rsp+F4h] [rbp-2AD4h]
  int v203; // [rsp+F8h] [rbp-2AD0h]
  int v204; // [rsp+FCh] [rbp-2ACCh]
  int v205; // [rsp+100h] [rbp-2AC8h]
  struct CCompExecCtxt *v206; // [rsp+108h] [rbp-2AC0h]
  __int64 v207; // [rsp+110h] [rbp-2AB8h] BYREF
  int v208; // [rsp+118h] [rbp-2AB0h]
  __int128 v209; // [rsp+120h] [rbp-2AA8h]
  int v210; // [rsp+130h] [rbp-2A98h]
  struct IMetadataAccess *v211; // [rsp+138h] [rbp-2A90h]
  struct CCompExecCtxt *v212; // [rsp+140h] [rbp-2A88h]
  char v213; // [rsp+148h] [rbp-2A80h]
  char v214; // [rsp+149h] [rbp-2A7Fh]
  char v215; // [rsp+14Ah] [rbp-2A7Eh]
  unsigned __int8 v216; // [rsp+14Bh] [rbp-2A7Dh]
  char v217; // [rsp+14Ch] [rbp-2A7Ch]
  char v218; // [rsp+14Dh] [rbp-2A7Bh]
  char v219; // [rsp+14Eh] [rbp-2A7Ah]
  char v221; // [rsp+150h] [rbp-2A78h]
  int v222; // [rsp+154h] [rbp-2A74h]
  struct IMetadataAccess *v223; // [rsp+158h] [rbp-2A70h]
  char v224; // [rsp+160h] [rbp-2A68h]
  struct IFidoGLMController *v225; // [rsp+168h] [rbp-2A60h] BYREF
  int v226; // [rsp+170h] [rbp-2A58h]
  int v227; // [rsp+174h] [rbp-2A54h] BYREF
  int v228; // [rsp+178h] [rbp-2A50h]
  int v229; // [rsp+17Ch] [rbp-2A4Ch]
  struct BaseXact *v230; // [rsp+180h] [rbp-2A48h]
  struct IFTCatList *v231; // [rsp+188h] [rbp-2A40h] BYREF
  __int64 v232; // [rsp+190h] [rbp-2A38h]
  DWORD v233; // [rsp+198h] [rbp-2A30h]
  DWORD v234; // [rsp+19Ch] [rbp-2A2Ch]
  int v235; // [rsp+1A0h] [rbp-2A28h]
  int v236; // [rsp+1A4h] [rbp-2A24h]
  int v237; // [rsp+1A8h] [rbp-2A20h] BYREF
  int v238; // [rsp+1ACh] [rbp-2A1Ch]
  __int64 v239; // [rsp+1B0h] [rbp-2A18h]
  __int64 v240; // [rsp+1B8h] [rbp-2A10h]
  __int16 v241; // [rsp+1C0h] [rbp-2A08h]
  __int16 v242; // [rsp+1C8h] [rbp-2A00h]
  __int16 v243; // [rsp+1D0h] [rbp-29F8h]
  __int16 v244; // [rsp+1D8h] [rbp-29F0h]
  __int16 v245; // [rsp+1E0h] [rbp-29E8h]
  struct IMetadataAccess *v246; // [rsp+1E8h] [rbp-29E0h]
  __int64 v247; // [rsp+1F0h] [rbp-29D8h]
  __int16 v248; // [rsp+1F8h] [rbp-29D0h]
  __int64 v249; // [rsp+200h] [rbp-29C8h]
  __int16 v250; // [rsp+208h] [rbp-29C0h]
  __int64 v251; // [rsp+210h] [rbp-29B8h]
  void **v252; // [rsp+218h] [rbp-29B0h] BYREF
  __int64 v253; // [rsp+220h] [rbp-29A8h]
  __int64 v254; // [rsp+228h] [rbp-29A0h] BYREF
  int v255; // [rsp+230h] [rbp-2998h]
  int v256; // [rsp+234h] [rbp-2994h]
  int v257; // [rsp+238h] [rbp-2990h]
  int v258; // [rsp+23Ch] [rbp-298Ch]
  int v259; // [rsp+240h] [rbp-2988h]
  int v260; // [rsp+244h] [rbp-2984h]
  DWFidoTxCtx *DWFidoTxCtx; // [rsp+248h] [rbp-2980h] BYREF
  __int64 v262; // [rsp+250h] [rbp-2978h]
  int v263; // [rsp+258h] [rbp-2970h] BYREF
  char v264; // [rsp+25Ch] [rbp-296Ch]
  void **v265; // [rsp+260h] [rbp-2968h] BYREF
  __int64 v266; // [rsp+268h] [rbp-2960h]
  __int64 v267; // [rsp+270h] [rbp-2958h] BYREF
  __int64 v268; // [rsp+278h] [rbp-2950h]
  int v269; // [rsp+280h] [rbp-2948h]
  int v270; // [rsp+284h] [rbp-2944h]
  __int16 v271; // [rsp+288h] [rbp-2940h]
  int v272; // [rsp+290h] [rbp-2938h]
  int v273; // [rsp+294h] [rbp-2934h]
  __int16 v274; // [rsp+298h] [rbp-2930h]
  __int64 v275; // [rsp+2A0h] [rbp-2928h]
  int v276; // [rsp+2A8h] [rbp-2920h]
  __int64 v277; // [rsp+2B0h] [rbp-2918h]
  const struct CCompExecCtxtStmt *v278; // [rsp+2B8h] [rbp-2910h]
  CStmtAlterDB *v279; // [rsp+2C0h] [rbp-2908h]
  int v280; // [rsp+2C8h] [rbp-2900h]
  CSessionLockList **v281; // [rsp+2D0h] [rbp-28F8h]
  __int64 v282; // [rsp+2D8h] [rbp-28F0h]
  __int64 v283; // [rsp+2E0h] [rbp-28E8h]
  _BYTE *i; // [rsp+2E8h] [rbp-28E0h]
  __int64 v285; // [rsp+2F0h] [rbp-28D8h]
  _BYTE *j; // [rsp+2F8h] [rbp-28D0h]
  __int64 v287; // [rsp+300h] [rbp-28C8h]
  __int64 v288; // [rsp+308h] [rbp-28C0h]
  __int128 v289; // [rsp+320h] [rbp-28A8h] BYREF
  __int64 v290; // [rsp+330h] [rbp-2898h]
  int v291; // [rsp+33Ch] [rbp-288Ch]
  _WORD *v292; // [rsp+340h] [rbp-2888h]
  char **v293; // [rsp+348h] [rbp-2880h]
  _WORD *v294; // [rsp+350h] [rbp-2878h]
  char **v295; // [rsp+358h] [rbp-2870h]
  _WORD *v296; // [rsp+360h] [rbp-2868h]
  char **v297; // [rsp+368h] [rbp-2860h]
  _WORD *v298; // [rsp+370h] [rbp-2858h]
  char **v299; // [rsp+378h] [rbp-2850h]
  _WORD *v300; // [rsp+380h] [rbp-2848h]
  char **v301; // [rsp+388h] [rbp-2840h]
  _WORD *v302; // [rsp+390h] [rbp-2838h]
  char **v303; // [rsp+398h] [rbp-2830h]
  _WORD *v304; // [rsp+3A0h] [rbp-2828h]
  char **v305; // [rsp+3A8h] [rbp-2820h]
  _WORD *v306; // [rsp+3B0h] [rbp-2818h]
  char **v307; // [rsp+3B8h] [rbp-2810h]
  _BYTE *v308; // [rsp+3C0h] [rbp-2808h]
  _BYTE *v309; // [rsp+3C8h] [rbp-2800h]
  int *v310; // [rsp+3D0h] [rbp-27F8h]
  _BYTE *v311; // [rsp+3D8h] [rbp-27F0h]
  _BYTE *v312; // [rsp+3E0h] [rbp-27E8h]
  int *v313; // [rsp+3E8h] [rbp-27E0h]
  int *v314; // [rsp+3F0h] [rbp-27D8h]
  int *v315; // [rsp+3F8h] [rbp-27D0h]
  struct IMetadataAccess *v316; // [rsp+400h] [rbp-27C8h]
  __int64 v317; // [rsp+408h] [rbp-27C0h]
  struct IMetadataAccess *v318; // [rsp+410h] [rbp-27B8h]
  __int64 v319; // [rsp+418h] [rbp-27B0h]
  __int64 v320; // [rsp+420h] [rbp-27A8h]
  _BYTE *v321; // [rsp+428h] [rbp-27A0h]
  __int64 v322; // [rsp+430h] [rbp-2798h]
  __int64 *v323; // [rsp+438h] [rbp-2790h]
  struct _GUID v324; // [rsp+440h] [rbp-2788h] BYREF
  __int64 v325; // [rsp+450h] [rbp-2778h]
  __int64 v326; // [rsp+458h] [rbp-2770h]
  __int64 v327; // [rsp+460h] [rbp-2768h]
  __int64 *v328; // [rsp+468h] [rbp-2760h]
  _BYTE v329[64]; // [rsp+470h] [rbp-2758h] BYREF
  char v330[8]; // [rsp+4B0h] [rbp-2718h] BYREF
  _WORD v331[4]; // [rsp+4B8h] [rbp-2710h] BYREF
  int v332; // [rsp+4C0h] [rbp-2708h]
  char **v333; // [rsp+4C8h] [rbp-2700h]
  char *v334; // [rsp+4D0h] [rbp-26F8h]
  __int64 v335; // [rsp+4D8h] [rbp-26F0h]
  char *v336; // [rsp+4E0h] [rbp-26E8h] BYREF
  int v337; // [rsp+4E8h] [rbp-26E0h]
  __int16 v338; // [rsp+4ECh] [rbp-26DCh]
  __int16 v339; // [rsp+4EEh] [rbp-26DAh]
  char v340; // [rsp+4F0h] [rbp-26D8h] BYREF
  int v341; // [rsp+700h] [rbp-24C8h]
  int v342; // [rsp+704h] [rbp-24C4h]
  __int64 v343; // [rsp+708h] [rbp-24C0h]
  char v344; // [rsp+710h] [rbp-24B8h] BYREF
  __int64 v345; // [rsp+711h] [rbp-24B7h]
  bool v346; // [rsp+719h] [rbp-24AFh]
  char v347[8]; // [rsp+720h] [rbp-24A8h] BYREF
  _WORD v348[4]; // [rsp+728h] [rbp-24A0h] BYREF
  int v349; // [rsp+730h] [rbp-2498h]
  char **v350; // [rsp+738h] [rbp-2490h]
  char *v351; // [rsp+740h] [rbp-2488h]
  __int64 v352; // [rsp+748h] [rbp-2480h]
  char *v353; // [rsp+750h] [rbp-2478h] BYREF
  int v354; // [rsp+758h] [rbp-2470h]
  __int16 v355; // [rsp+75Ch] [rbp-246Ch]
  __int16 v356; // [rsp+75Eh] [rbp-246Ah]
  char v357; // [rsp+760h] [rbp-2468h] BYREF
  int v358; // [rsp+970h] [rbp-2258h]
  int v359; // [rsp+974h] [rbp-2254h]
  __int64 v360; // [rsp+978h] [rbp-2250h]
  char v361; // [rsp+980h] [rbp-2248h] BYREF
  __int64 v362; // [rsp+981h] [rbp-2247h]
  bool v363; // [rsp+989h] [rbp-223Fh]
  char v364[8]; // [rsp+990h] [rbp-2238h] BYREF
  _WORD v365[4]; // [rsp+998h] [rbp-2230h] BYREF
  int v366; // [rsp+9A0h] [rbp-2228h]
  char **v367; // [rsp+9A8h] [rbp-2220h]
  char *v368; // [rsp+9B0h] [rbp-2218h]
  __int64 v369; // [rsp+9B8h] [rbp-2210h]
  char *v370; // [rsp+9C0h] [rbp-2208h] BYREF
  int v371; // [rsp+9C8h] [rbp-2200h]
  __int16 v372; // [rsp+9CCh] [rbp-21FCh]
  __int16 v373; // [rsp+9CEh] [rbp-21FAh]
  char v374; // [rsp+9D0h] [rbp-21F8h] BYREF
  int v375; // [rsp+BE0h] [rbp-1FE8h]
  int v376; // [rsp+BE4h] [rbp-1FE4h]
  __int64 v377; // [rsp+BE8h] [rbp-1FE0h]
  char v378; // [rsp+BF0h] [rbp-1FD8h] BYREF
  __int64 v379; // [rsp+BF1h] [rbp-1FD7h]
  bool v380; // [rsp+BF9h] [rbp-1FCFh]
  char v381[8]; // [rsp+C00h] [rbp-1FC8h] BYREF
  _WORD v382[4]; // [rsp+C08h] [rbp-1FC0h] BYREF
  int v383; // [rsp+C10h] [rbp-1FB8h]
  char **v384; // [rsp+C18h] [rbp-1FB0h]
  char *v385; // [rsp+C20h] [rbp-1FA8h]
  __int64 v386; // [rsp+C28h] [rbp-1FA0h]
  char *v387; // [rsp+C30h] [rbp-1F98h] BYREF
  int v388; // [rsp+C38h] [rbp-1F90h]
  __int16 v389; // [rsp+C3Ch] [rbp-1F8Ch]
  __int16 v390; // [rsp+C3Eh] [rbp-1F8Ah]
  char v391; // [rsp+C40h] [rbp-1F88h] BYREF
  int v392; // [rsp+E50h] [rbp-1D78h]
  int v393; // [rsp+E54h] [rbp-1D74h]
  __int64 v394; // [rsp+E58h] [rbp-1D70h]
  char v395; // [rsp+E60h] [rbp-1D68h] BYREF
  __int64 v396; // [rsp+E61h] [rbp-1D67h]
  bool v397; // [rsp+E69h] [rbp-1D5Fh]
  char v398[8]; // [rsp+E70h] [rbp-1D58h] BYREF
  _WORD v399[4]; // [rsp+E78h] [rbp-1D50h] BYREF
  int v400; // [rsp+E80h] [rbp-1D48h]
  char **v401; // [rsp+E88h] [rbp-1D40h]
  char *v402; // [rsp+E90h] [rbp-1D38h]
  __int64 v403; // [rsp+E98h] [rbp-1D30h]
  char *v404; // [rsp+EA0h] [rbp-1D28h] BYREF
  int v405; // [rsp+EA8h] [rbp-1D20h]
  __int16 v406; // [rsp+EACh] [rbp-1D1Ch]
  __int16 v407; // [rsp+EAEh] [rbp-1D1Ah]
  char v408; // [rsp+EB0h] [rbp-1D18h] BYREF
  int v409; // [rsp+10C0h] [rbp-1B08h]
  int v410; // [rsp+10C4h] [rbp-1B04h]
  __int64 v411; // [rsp+10C8h] [rbp-1B00h]
  char v412; // [rsp+10D0h] [rbp-1AF8h] BYREF
  __int64 v413; // [rsp+10D1h] [rbp-1AF7h]
  char v414[8]; // [rsp+10E0h] [rbp-1AE8h] BYREF
  _WORD v415[4]; // [rsp+10E8h] [rbp-1AE0h] BYREF
  int v416; // [rsp+10F0h] [rbp-1AD8h]
  char **v417; // [rsp+10F8h] [rbp-1AD0h]
  char *v418; // [rsp+1100h] [rbp-1AC8h]
  __int64 v419; // [rsp+1108h] [rbp-1AC0h]
  char *v420; // [rsp+1110h] [rbp-1AB8h] BYREF
  int v421; // [rsp+1118h] [rbp-1AB0h]
  __int16 v422; // [rsp+111Ch] [rbp-1AACh]
  __int16 v423; // [rsp+111Eh] [rbp-1AAAh]
  char v424; // [rsp+1120h] [rbp-1AA8h] BYREF
  int v425; // [rsp+1330h] [rbp-1898h]
  int v426; // [rsp+1334h] [rbp-1894h]
  __int64 v427; // [rsp+1338h] [rbp-1890h]
  char v428; // [rsp+1340h] [rbp-1888h] BYREF
  __int64 v429; // [rsp+1341h] [rbp-1887h]
  char v430[8]; // [rsp+1350h] [rbp-1878h] BYREF
  _WORD v431[4]; // [rsp+1358h] [rbp-1870h] BYREF
  int v432; // [rsp+1360h] [rbp-1868h]
  char **v433; // [rsp+1368h] [rbp-1860h]
  char *v434; // [rsp+1370h] [rbp-1858h]
  __int64 v435; // [rsp+1378h] [rbp-1850h]
  char *v436; // [rsp+1380h] [rbp-1848h] BYREF
  int v437; // [rsp+1388h] [rbp-1840h]
  __int16 v438; // [rsp+138Ch] [rbp-183Ch]
  __int16 v439; // [rsp+138Eh] [rbp-183Ah]
  char v440; // [rsp+1390h] [rbp-1838h] BYREF
  int v441; // [rsp+15A0h] [rbp-1628h]
  int v442; // [rsp+15A4h] [rbp-1624h]
  __int64 v443; // [rsp+15A8h] [rbp-1620h]
  char v444; // [rsp+15B0h] [rbp-1618h] BYREF
  __int64 v445; // [rsp+15B1h] [rbp-1617h]
  char v446[8]; // [rsp+15C0h] [rbp-1608h] BYREF
  _WORD v447[4]; // [rsp+15C8h] [rbp-1600h] BYREF
  int v448; // [rsp+15D0h] [rbp-15F8h]
  char **v449; // [rsp+15D8h] [rbp-15F0h]
  char *v450; // [rsp+15E0h] [rbp-15E8h]
  __int64 v451; // [rsp+15E8h] [rbp-15E0h]
  char *v452; // [rsp+15F0h] [rbp-15D8h] BYREF
  int v453; // [rsp+15F8h] [rbp-15D0h]
  __int16 v454; // [rsp+15FCh] [rbp-15CCh]
  __int16 v455; // [rsp+15FEh] [rbp-15CAh]
  char v456; // [rsp+1600h] [rbp-15C8h] BYREF
  int v457; // [rsp+1810h] [rbp-13B8h]
  int v458; // [rsp+1814h] [rbp-13B4h]
  __int64 v459; // [rsp+1818h] [rbp-13B0h]
  char v460; // [rsp+1820h] [rbp-13A8h] BYREF
  __int64 v461; // [rsp+1821h] [rbp-13A7h]
  _BYTE v462[176]; // [rsp+1830h] [rbp-1398h] BYREF
  __int64 v463; // [rsp+18E0h] [rbp-12E8h]
  _BYTE v464[176]; // [rsp+18E8h] [rbp-12E0h] BYREF
  __int64 v465; // [rsp+1998h] [rbp-1230h]
  _BYTE v466[176]; // [rsp+19A0h] [rbp-1228h] BYREF
  __int64 v467; // [rsp+1A50h] [rbp-1178h]
  _BYTE v468[176]; // [rsp+1A58h] [rbp-1170h] BYREF
  __int64 v469; // [rsp+1B08h] [rbp-10C0h]
  _BYTE v470[400]; // [rsp+1B10h] [rbp-10B8h] BYREF
  _BYTE v471[24]; // [rsp+1CA0h] [rbp-F28h] BYREF
  unsigned __int8 *v472; // [rsp+1CB8h] [rbp-F10h]
  unsigned int v473; // [rsp+1CCCh] [rbp-EFCh]
  int v474; // [rsp+1DD8h] [rbp-DF0h]
  int v475; // [rsp+1DDCh] [rbp-DECh]
  int v476; // [rsp+1E10h] [rbp-DB8h]
  int v477; // [rsp+1E18h] [rbp-DB0h]
  unsigned __int8 v478; // [rsp+1E1Ch] [rbp-DACh]
  char v479; // [rsp+1E1Dh] [rbp-DABh]
  char v480; // [rsp+1E1Eh] [rbp-DAAh]
  char v481; // [rsp+1E21h] [rbp-DA7h]
  char v482; // [rsp+1E22h] [rbp-DA6h]
  _WORD v483[2]; // [rsp+1E30h] [rbp-D98h] BYREF
  int v484; // [rsp+1E34h] [rbp-D94h]
  int v485; // [rsp+1E38h] [rbp-D90h]
  int v486; // [rsp+1E3Ch] [rbp-D8Ch]
  char v487[512]; // [rsp+1E40h] [rbp-D88h] BYREF
  __int128 v488; // [rsp+2040h] [rbp-B88h]
  int v489; // [rsp+2050h] [rbp-B78h]
  _WORD v490[2]; // [rsp+2060h] [rbp-B68h] BYREF
  int v491; // [rsp+2064h] [rbp-B64h]
  int v492; // [rsp+2068h] [rbp-B60h]
  int v493; // [rsp+206Ch] [rbp-B5Ch]
  char v494[512]; // [rsp+2070h] [rbp-B58h] BYREF
  __int128 v495; // [rsp+2270h] [rbp-958h]
  int v496; // [rsp+2280h] [rbp-948h]
  _BYTE v497[376]; // [rsp+2290h] [rbp-938h] BYREF
  int v498; // [rsp+2408h] [rbp-7C0h]
  char v499; // [rsp+2413h] [rbp-7B5h]
  char v500[384]; // [rsp+2420h] [rbp-7A8h] BYREF
  int v501; // [rsp+25A0h] [rbp-628h] BYREF
  __int16 v502; // [rsp+25A4h] [rbp-624h]
  int v503; // [rsp+25B0h] [rbp-618h]
  _BYTE v504[952]; // [rsp+25DCh] [rbp-5ECh] BYREF
  _BYTE v505[68]; // [rsp+2994h] [rbp-234h] BYREF
  int v506; // [rsp+29D8h] [rbp-1F0h] BYREF
  __int16 v507; // [rsp+29DCh] [rbp-1ECh]
  char v508; // [rsp+29DEh] [rbp-1EAh]
  char v509; // [rsp+29DFh] [rbp-1E9h]
  char v510; // [rsp+2B20h] [rbp-A8h] BYREF

  v326 = -2;
  v240 = (__int64)a3;
  v3 = a2;
  v206 = a2;
  v279 = this;
  v278 = a2;
  v190 = 5;
  v193 = 0;
  v194 = 0;
  v289 = 0;
  v290 = 0;
  v291 = 0;
  v207 = 0;
  v208 = 1;
  v209 = 0;
  v196 = 0;
  v189 = 0;
  v200 = 0;
  memset_0(v471, 0, 0x188u);
  v477 = -1;
  v231 = 0;
  v5 = (int (*)(int, int, int, int, char *))hdl_prntbackout;
  v201 = 0;
  v229 = 0;
  v203 = 0;
  v472 = (unsigned __int8 *)&v510;
  if ( *((_DWORD *)this + 612) )
    v5 = (int (*)(int, int, int, int, char *))CTraceDataSTVFInfo::CUserArguments;
  ExcHandler::ExcHandler((ExcHandler *)v329, 0, 0, 0, v5, 0);
  AutoOverrideMsqlXact::InitializeAndOverride((AutoOverrideMsqlXact *)&v289);
  v208 = 1;
  v232 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset);
  *(_QWORD *)&v209 = *(_QWORD *)(v232 + 144);
  v232 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset);
  v276 = 1;
  v6 = (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v209 + 464LL))(v209) == 0;
  v7 = *(_QWORD *)v209;
  if ( v6 )
  {
    (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64, __int64, int, int, _BYTE, _QWORD, int))(v7 + 8))(
      v209,
      L"CStmtAlterDB::ChangeStateOption",
      62,
      1,
      2,
      1,
      0,
      0,
      1);
    LODWORD(v207) = 1;
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
    (*(void (__fastcall **)(_QWORD, __int64, __int64, char *))(*(_QWORD *)v209 + 232LL))(v209, 2, 1, (char *)&v207 + 4);
    v208 = 1;
    LODWORD(v207) = 3;
  }
  v230 = (struct BaseXact *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v209 + 432LL))(v209);
  (*(void (__fastcall **)(struct BaseXact *))(*(_QWORD *)v230 + 16LL))(v230);
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v9 = *(_QWORD *)(v8 + 256);
  if ( !v9 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v9 = *(_QWORD *)(v8 + 256);
  }
  v223 = (struct IMetadataAccess *)((__int64 (__fastcall *)(_QWORD, struct BaseXact *, const char *, __int64))g_metadataFactory)(
                                     *(_QWORD *)(v9 + 1000),
                                     v230,
                                     "sql\\ntdbms\\msql\\proc\\stdb.cpp",
                                     13762);
  v211 = v223;
  v10 = (*(__int64 (__fastcall **)(struct IMetadataAccess *))(*(_QWORD *)v223 + 72LL))(v223);
  v268 = v10;
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v10 + 8LL))(
          v10,
          *((_QWORD *)this + 276),
          *((unsigned int *)this + 554));
  v191 = v11;
  if ( !v11 )
  {
    LODWORD(v178) = *((_DWORD *)this + 554);
    ex_raise(50, 11, 14, 5, v178, *((_QWORD *)this + 276));
  }
  v473 = 85;
  if ( !(**(unsigned __int8 (__fastcall ***)(__int64, _QWORD, _BYTE *, _QWORD))v10)(v10, v11, v471, 0) )
  {
    LODWORD(v178) = *((_DWORD *)this + 554);
    ex_raise(50, 11, 14, 6, v178, *((_QWORD *)this + 276));
  }
  v12 = 8LL * SystemThread_TlsIndex;
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v12)
                                         + SystemThread_TlsOffset)
                             + 72LL)
                 + 270LL)
      & 4) != 0 )
  {
    v232 = *(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v12) + SystemThread_TlsOffset);
    v249 = v232;
    v249 = *(_QWORD *)(SystemThread_TlsOffset + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v12));
    v280 = *(unsigned __int16 *)(*(_QWORD *)(v249 + 80) + 8LL);
    TardisDbId = v11;
    v192 = v11;
    if ( v280 != v11 )
    {
      LODWORD(v178) = *((_DWORD *)this + 554);
      ex_raise(50, 11, 14, 10, v178, *((_QWORD *)this + 276));
    }
  }
  else
  {
    TardisDbId = v11;
    v192 = v11;
  }
  if ( (unsigned int)(*((_DWORD *)this + 612) - 1) <= 1 && (v481 & 0x10) != 0 )
  {
    LODWORD(v186) = *((_DWORD *)this + 554);
    ex_raise(50, 58, 16, 9, 48, L"VARDECIMAL_STORAGEFORMAT", v186, *((_QWORD *)this + 276));
  }
  v197 = 0;
  v198 = 0;
  v205 = 7;
  v204 = 7;
  v225 = 0;
  if ( (unsigned __int8)FGetFidoGLMController(&v225, TardisDbId) )
  {
    DWFidoTxCtx = GetDWFidoTxCtx(0, 1);
    v14 = (*(__int64 (__fastcall **)(CStmtAlterDB *))(*(_QWORD *)this + 120LL))(this);
    StartDwFidoTran(v14, &DWFidoTxCtx, v225, 0, 0);
    TardisDbId = DWFidoTxCtx::GetTardisDbId(DWFidoTxCtx, v225);
    v192 = TardisDbId;
    v191 = TardisDbId;
    v15 = (*(__int64 (__fastcall **)(struct IFidoGLMController *))(*(_QWORD *)v225 + 152LL))(v225);
    v16 = v203;
    if ( !v15 )
      v16 = 16;
    v203 = v16;
  }
  if ( !CAutoDb::FUse((CAutoDb *)&v196, TardisDbId, 0, 1, 0, 0) )
  {
    v17 = *(_DWORD *)(qword_102ECFB00 + 48);
    if ( (v17 & 0x20) != 0 || (v17 & 0x10) == 0 )
    {
      LODWORD(v179) = *((_DWORD *)this + 554);
      ex_raise(50, 11, 14, 7, v179, *((_QWORD *)this + 276));
    }
    if ( *((_DWORD *)this + 618) != 0x80000000 || *((_DWORD *)this + 607) != 3 )
    {
      CAutoDb::~CAutoDb((CAutoDb *)&v196);
      CAutoDb::FUse((CAutoDb *)&v196, TardisDbId, 0, 1, 1, 0);
      v190 = 4;
    }
    v210 = lockdb(TardisDbId, 43, v190, 6000, v203);
    if ( v210 < 0 )
      goto LABEL_43;
    _mm_lfence();
    v193 = 1;
    if ( v191 != (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v268 + 8LL))(
                   v268,
                   *((_QWORD *)this + 276),
                   *((unsigned int *)this + 554)) )
    {
      LODWORD(v180) = *((_DWORD *)this + 554);
      ex_raise(50, 11, 14, 8, v180, *((_QWORD *)this + 276));
    }
    v249 = 0;
    v319 = qword_102ECFB00;
    DBTABLE = DBMgr::TryToGetDBTABLE(*(_QWORD *)(qword_102ECFB00 + 32), 0, v191);
    v194 = (unsigned int *)DBTABLE;
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
        TardisDbId = v191;
        v192 = v191;
LABEL_43:
        v20 = (__int64)v194;
LABEL_44:
        CStmtAlterDB::PerformGeneralPermissionCheck(
          this,
          TardisDbId,
          v472,
          v473,
          0,
          *(struct ISecurityContext **)(*((_QWORD *)v3 + 15) + 264LL),
          v223);
        goto LABEL_130;
      }
    }
    _mm_lfence();
    v20 = DBTABLE;
    LODWORD(v180) = *(_DWORD *)(DBTABLE + 928);
    ex_raise(14, 68, 16, 5, v180, DBTABLE + 936);
LABEL_46:
    TardisDbId = v191;
    v192 = v191;
    goto LABEL_44;
  }
  v23 = v196;
  v192 = v196;
  v191 = v196;
  v320 = qword_102ECFB00;
  v24 = *(_QWORD *)(qword_102ECFB00 + 32);
  v247 = v24;
  switch ( v196 )
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
      v194 = (unsigned int *)v20;
      goto LABEL_58;
  }
  if ( v196 <= *(_DWORD *)(v24 + 76) && v196 )
  {
    _mm_lfence();
    v23 = v196;
    v20 = *(_QWORD *)(*(_QWORD *)(v247 + 40) + 8LL * (int)(v196 - 1));
    v194 = (unsigned int *)v20;
    v192 = v196;
  }
  else
  {
    v20 = 0;
    v194 = 0;
  }
LABEL_58:
  v321 = v462;
  CCompExecCtxt::CCompExecCtxt((CCompExecCtxt *)v462, v3);
  v463 = *((_QWORD *)v3 + 22);
  if ( (unsigned __int8)CStmtAlterDB::IsSDSDbOperation(v25, v223, v462) )
  {
    v26 = ((__int64 (__fastcall *)(_QWORD, struct BaseXact *, _QWORD, const char *, int))g_metadataFactory[3])(
            *(_QWORD *)(v20 + 688),
            v230,
            *(unsigned __int16 *)(v20 + 42),
            "sql\\ntdbms\\msql\\proc\\stdb.cpp",
            13927);
    v322 = v26;
    v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 72LL))(v26);
    v28 = DBTABLE::CbLogicalDbNameInternal((DBTABLE *)v20);
    v29 = DBTABLE::LogicalDbNameInternal((DBTABLE *)v20);
    v30 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v27 + 8LL))(v27, v29, v28);
    v473 = 85;
    (**(void (__fastcall ***)(__int64, _QWORD, _BYTE *, _QWORD))v27)(v27, v30, v471, 0);
    v325 = v26;
    (**(void (__fastcall ***)(__int64, __int64))v26)(v26, 1);
    v3 = v206;
  }
  CStmtAlterDB::PerformGeneralPermissionCheck(
    this,
    v23,
    v472,
    v473,
    1,
    *(struct ISecurityContext **)(*((_QWORD *)v3 + 15) + 264LL),
    v223);
  SEStatFromDbRegAttr = GetSEStatFromDbRegAttr((const struct MDAttrDbReg *)v471);
  v32 = SEStatFromDbRegAttr;
  v198 = SEStatFromDbRegAttr;
  v197 = SEStatFromDbRegAttr;
  v197 = *((_DWORD *)this + 602) | SEStatFromDbRegAttr & ~*((_DWORD *)this + 601);
  v33 = v197;
  AvailabilityFromStatus = GetAvailabilityFromStatus(SEStatFromDbRegAttr);
  v205 = AvailabilityFromStatus;
  v204 = GetAvailabilityFromStatus(v33);
  if ( AvailabilityFromStatus != v204
    || (v33 & 0x1000) != 0 && (v32 & 0x1000) == 0
    || (v33 & 0x400) != 0 && (v198 & 0x400) == 0 )
  {
    StopFTCrawls(v23, 0);
  }
  if ( !v205 && (unsigned int)(v204 - 5) <= 1 || (v33 & 0x400) == 0 && (v198 & 0x400) != 0 )
  {
    ClearFulltextCaches(v23);
    ClearCatalogCache(v23, v223);
    v36 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v37 = *(_QWORD *)(v36 + 256);
    if ( !v37 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v37 = *(_QWORD *)(v36 + 256);
    }
    v23 = v196;
    FullTextBuildDelayOperationPool(v196, 0, 0, &v231, *(struct IMemObj **)(v37 + 1000));
    v201 = 1;
    v192 = v191;
    v20 = (__int64)v194;
  }
  v38 = v20 + 4624;
  v39 = *(_QWORD *)(v20 + 4624);
  v40 = *(_QWORD *)(v39 + 1712);
  if ( !*(_DWORD *)(v40 + 784)
    || *(_QWORD *)(v40 + 788) == *(_QWORD *)&x_AG_DB_IdBad.Data1
    && *(_QWORD *)(v40 + 796) == *(_QWORD *)x_AG_DB_IdBad.Data4
    || !*(_BYTE *)(v39 + 8272) )
  {
    TardisDbId = v192;
    goto LABEL_84;
  }
  v257 = 0;
  v41 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset);
  if ( !v41 || (v42 = *(struct CSessionTraceFlags ***)(v41 + 56), (v43 = *v42) == 0) )
  {
    v251 = 0;
    goto LABEL_82;
  }
  v251 = (__int64)*v42;
  if ( !CSessionTraceFlags::CheckSessionTraceInternal(v43, 0xD86u) )
  {
LABEL_82:
    v20 = (__int64)v194;
    v44 = DBTABLE::LogicalDbNameInternal((DBTABLE *)v194);
    LODWORD(v182) = DBTABLE::CbLogicalDbNameInternal((DBTABLE *)v194);
    ex_raise(14, 68, 16, 3, v182, v44);
    TardisDbId = v191;
    v192 = v191;
    v23 = v196;
    goto LABEL_84;
  }
  TardisDbId = v191;
  v192 = v191;
  v20 = (__int64)v194;
  v23 = v196;
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
  v47 = (v197 ^ v198) & 0x800000;
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
      LODWORD(v182) = DBTABLE::CbLogicalDbNameInternal((DBTABLE *)v20);
      ex_raise(14, 68, 16, 6, v182, v49);
    }
  }
  LOBYTE(v35) = 4;
  v195 = 4;
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
  v195 = v35;
LABEL_104:
  v190 = v35;
  v210 = lockdb(v23, 43, v35, 6000, v203);
  if ( v210 >= 0 )
  {
    v193 = 1;
    if ( v50 == 5
      || ((v281 = (CSessionLockList **)v464,
           v51 = v206,
           CCompExecCtxt::CCompExecCtxt((CCompExecCtxt *)v464, v206),
           v465 = *((_QWORD *)v51 + 22),
           !(unsigned __int8)CStmtAlterDB::IsSDSDbOperation(v52, v223, v464))
       || (*((_DWORD *)this + 601) & 0x400) == 0 && (*((_DWORD *)this + 602) & 0x400) == 0
        ? (v53 = 0)
        : (v53 = 1),
          (v221 = v53, !*((_DWORD *)this + 634))
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
      if ( v210 >= 0 )
        goto LABEL_139;
      goto LABEL_131;
    }
    _mm_lfence();
    v54 = 0;
    v222 = 0;
    if ( v47 || *((_DWORD *)this + 613) )
    {
      v222 = 2;
      v54 = 3;
    }
    else
    {
      if ( !*((_DWORD *)this + 634) && !v53 )
      {
LABEL_128:
        v55 = *((unsigned int *)this + 635);
LABEL_129:
        v255 = v55;
        v20 = (__int64)v194;
        LOBYTE(v187) = 5;
        DBMgr::LockDBForStateChange(
          *(_QWORD *)(qword_102ECFB00 + 32),
          v196,
          v55,
          v194[232],
          v194 + 234,
          v54,
          (_DWORD)v187,
          -1);
        unlockdb(v196, 43, v195);
        v190 = 5;
        TardisDbId = v191;
        v192 = v191;
        goto LABEL_130;
      }
      v54 = 1;
    }
    v222 = v54;
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
  if ( v210 == -1 )
  {
    if ( (v479 & 1) != 0 )
    {
      v281 = *(CSessionLockList ***)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset);
      TardisDbId = v191;
      v192 = v191;
      if ( !CSessionLockList::IsHeldSingleUserLock(v281[11], v191) )
      {
        LODWORD(v181) = *((_DWORD *)this + 554);
        ex_raise(50, 64, 16, 1, v181, *((_QWORD *)this + 276));
      }
    }
    else
    {
      TardisDbId = v191;
      v192 = v191;
    }
    LODWORD(v181) = *((_DWORD *)this + 554);
    ex_raise(50, 61, 16, 1, v181, *((_QWORD *)this + 276));
  }
  else
  {
    TardisDbId = v191;
    v192 = v191;
  }
  LOBYTE(v22) = 68;
  lck_StandardHandler((unsigned int)v210, v22);
  v20 = (__int64)v194;
LABEL_139:
  if ( (*((_DWORD *)this + 604) & 0x400) != 0 || (*((_DWORD *)this + 603) & 0x400) != 0 )
  {
    if ( FSystemDBId(TardisDbId, 0x77u) )
      ex_raise(56, 0, 16, 2);
    MasterDbId = GetMasterDbId();
    LOBYTE(v185) = 1;
    if ( !(unsigned __int8)ISECManager::AccessCheck(
                             0,
                             MasterDbId,
                             0,
                             24,
                             11,
                             (_DWORD)v185,
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
    LOBYTE(v188) = 0;
    LOBYTE(v185) = 1;
    if ( !(unsigned __int8)ISECManager::AccessCheck(
                             0,
                             v57,
                             0,
                             24,
                             51,
                             (_DWORD)v185,
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
                             v188,
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
    LOBYTE(v188) = 0;
    LOBYTE(v185) = 1;
    if ( !(unsigned __int8)ISECManager::AccessCheck(
                             0,
                             TardisDbId,
                             TardisDbId,
                             0,
                             108,
                             (_DWORD)v185,
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
                             v188,
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
      v327 = 2 * v61;
      LODWORD(v187) = *((_DWORD *)this + 554);
      LODWORD(v181) = 2 * v61;
      ex_raise(50, 58, 16, 10, v181, v60, v187, *((_QWORD *)this + 276));
    }
    v62 = GetMasterDbId();
    LOBYTE(v188) = 0;
    LOBYTE(v185) = 1;
    if ( !(unsigned __int8)ISECManager::AccessCheck(
                             0,
                             v62,
                             0,
                             24,
                             51,
                             (_DWORD)v185,
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
                             v188,
                             0,
                             0,
                             0,
                             0,
                             0) )
      ex_raise(152, 47, 16, 11);
  }
  CAutoDb::~CAutoDb((CAutoDb *)&v196);
  if ( (v480 & 0x10) != 0 && (*((_DWORD *)this + 606) & 0x10000) != 0 && (*((_BYTE *)this + 2420) & 0x10) == 0
    || (v480 & 0x20) != 0 && (*((_BYTE *)this + 2424) & 0x10) != 0 && (*((_DWORD *)this + 605) & 0x10000) == 0 )
  {
    ex_raise(50, 67, 16, 1);
  }
  if ( v474 && !v475 )
    ex_raise(50, 93, 16, 1);
  v64 = (_DWORD *)((char *)this + 2424);
  if ( (*((_BYTE *)this + 2424) & 1) != 0 )
  {
    v63 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset)
                    + 72LL);
    if ( (*(_BYTE *)(v63 + 270) & 4) != 0 )
    {
      TardisDbId = v191;
      v192 = v191;
    }
    else
    {
      v239 = 0;
      v252 = &AutoReadOnlyIMA::`vftable';
      v253 = 0;
      v323 = &v254;
      v328 = &v254;
      v254 = 0;
      v65 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v66 = *(_QWORD *)(v65 + 256);
      if ( !v66 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v66 = *(_QWORD *)(v65 + 256);
      }
      v67 = *(_QWORD *)(v66 + 1000);
      AutoReadOnlyXact::BeginCompatibleXact((AutoReadOnlyXact *)&v254, L"MEMORY_OPTIMIZED_DATAFileGroupCheck", 70, 0);
      ((void (__fastcall *)(void ***, __int64))*v252)(&v252, v67);
      LODWORD(v185) = 0;
      LODWORD(v181) = 0;
      TardisDbId = v191;
      v192 = v191;
      v68 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v253 + 56LL))(v253, v191, 0, 0);
      v69 = v239;
      while ( 1 )
      {
        v70 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v68 + 696LL))(v68, v69, 1);
        v69 = v70;
        if ( !v70 )
          break;
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v70 + 24LL))(v70, &v263);
        if ( v263 == 4 && (v264 & 1) != 0 )
        {
          RaiseUnsupportedHekatonFeatureError(124, 6, 0);
          break;
        }
      }
      AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v252);
      v64 = (_DWORD *)((char *)this + 2424);
    }
    v20 = (__int64)v194;
  }
  if ( !v20 )
  {
    v20 = g_dbtableFactory[4](TardisDbId);
    v194 = (unsigned int *)v20;
    if ( !v20 )
      utassert_fail(1u, "dbtable", "stdb.cpp", 14261, 0);
  }
  v226 = 27;
  if ( *(_BYTE *)(GetXdbServerGlobals(v63) + 12004) )
  {
    if ( *(_QWORD *)(v20 + 5320) )
    {
      LOWORD(v181) = 0;
      v71 = CStatement::XretDwFidoExecuteOnGLMS(this, v240, TardisDbId, 0);
      v226 = v71;
      if ( v71 != 27 )
      {
        if ( v71 )
          ex_raise(50, 69, 16, 2);
      }
    }
  }
  if ( (*((_DWORD *)this + 604) & 0x100) != 0 )
  {
    TickCount = GetTickCount();
    v233 = TickCount;
    v240 = 0x200000002LL;
    if ( (qword_102F21DB4 & 0x200000000LL) != 0 )
    {
      v248 = 1;
      v292 = v348;
      v348[0] = 0;
      v348[1] = 1;
      v349 = 0;
      v350 = &v353;
      v351 = &v357;
      v358 = 0;
      v359 = 0;
      v352 = 0;
      v360 = 0;
      v293 = &v353;
      v353 = &v361;
      v354 = 10;
      v355 = 0;
      v356 = 0;
      v361 = 3;
      v362 = 0;
      v363 = (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                 + SystemThread_TlsIndex)
                                               + SystemThread_TlsOffset)
                                   + 72LL)
                       + 270LL)
            & 4) != 0;
      XeCloudPkg::database_ddl_stmt_tde_start::Publish((XeCloudPkg::database_ddl_stmt_tde_start *)v347);
      TardisDbId = v191;
      v192 = v191;
      v20 = (__int64)v194;
      TickCount = v233;
    }
    if ( *((_BYTE *)qword_102EF3550 + 760) || (v219 = *((_BYTE *)qword_102ECFB10 + 626) >> 7) != 0 )
    {
      v73 = *((_DWORD *)this + 582);
      if ( v73 > 0 )
      {
        if ( !DBTABLE::VerifyValidWorkgroup((DBTABLE *)v20, *((wchar_t **)this + 292), v73) )
          ex_raise(335, 59, 16, 1);
        DBTABLE::SetTDEWorkgroupName((DBTABLE *)v20, *((wchar_t **)this + 292), *((_DWORD *)this + 582), 1);
      }
    }
    CSECDEK::TurnOnEncryption((struct DBTABLE *)v20);
    v74 = GetTickCount();
    v239 = 0x400000002LL;
    if ( (qword_102F21DB4 & 0x400000000LL) != 0 )
    {
      v250 = 1;
      v294 = v399;
      v399[0] = 0;
      v399[1] = 1;
      v400 = 0;
      v401 = &v404;
      v402 = &v408;
      v409 = 0;
      v410 = 0;
      v403 = 0;
      v411 = 0;
      v295 = &v404;
      v404 = &v412;
      v405 = 9;
      v406 = 0;
      v407 = 0;
      v412 = 3;
      v413 = v74 - TickCount;
      XeCloudPkg::database_ddl_stmt_tde_succeeded::Publish((XeCloudPkg::database_ddl_stmt_tde_succeeded *)v398);
    }
    EncryptionWarningForHkV1(v20);
    goto LABEL_209;
  }
  if ( (*((_DWORD *)this + 603) & 0x100) == 0 )
  {
LABEL_209:
    v75 = v206;
    goto LABEL_210;
  }
  v78 = GetTickCount();
  v251 = 0x200000002LL;
  v75 = v206;
  if ( (qword_102F21DB4 & 0x200000000LL) != 0 )
  {
    v245 = 1;
    v296 = v331;
    v331[0] = 0;
    v331[1] = 1;
    v332 = 0;
    v333 = &v336;
    v334 = &v340;
    v341 = 0;
    v342 = 0;
    v335 = 0;
    v343 = 0;
    v297 = &v336;
    v336 = &v344;
    v337 = 10;
    v338 = 0;
    v339 = 0;
    v344 = 4;
    v345 = 0;
    v346 = (*(_BYTE *)(*((_QWORD *)v206 + 9) + 270LL) & 4) != 0;
    XeCloudPkg::database_ddl_stmt_tde_start::Publish((XeCloudPkg::database_ddl_stmt_tde_start *)v330);
  }
  if ( *((_BYTE *)qword_102EF3550 + 760) || (v218 = *((_BYTE *)qword_102ECFB10 + 626) >> 7) != 0 )
  {
    v79 = *((_DWORD *)this + 582);
    if ( v79 > 0 )
    {
      if ( !DBTABLE::VerifyValidWorkgroup((DBTABLE *)v20, *((wchar_t **)this + 292), v79) )
        ex_raise(335, 59, 16, 2);
      DBTABLE::SetTDEWorkgroupName((DBTABLE *)v20, *((wchar_t **)this + 292), *((_DWORD *)this + 582), 1);
    }
  }
  CSECDEK::TurnOffEncryption((struct DBTABLE *)v20);
  v80 = GetTickCount();
  v247 = 0x400000002LL;
  if ( (qword_102F21DB4 & 0x400000000LL) != 0 )
  {
    v244 = 1;
    v298 = v415;
    v415[0] = 0;
    v415[1] = 1;
    v416 = 0;
    v417 = &v420;
    v418 = &v424;
    v425 = 0;
    v426 = 0;
    v419 = 0;
    v427 = 0;
    v299 = &v420;
    v420 = &v428;
    v421 = 9;
    v422 = 0;
    v423 = 0;
    v428 = 4;
    v429 = v80 - v78;
    XeCloudPkg::database_ddl_stmt_tde_succeeded::Publish((XeCloudPkg::database_ddl_stmt_tde_succeeded *)v414);
  }
LABEL_210:
  if ( (*((_BYTE *)this + 2416) & 0x40) != 0 )
  {
    v76 = GetTickCount();
    v234 = v76;
    v223 = (struct IMetadataAccess *)0x200000002LL;
    if ( (qword_102F21DB4 & 0x200000000LL) != 0 )
    {
      v300 = v365;
      v365[0] = 0;
      v365[1] = 1;
      v366 = 0;
      v367 = &v370;
      v368 = &v374;
      v375 = 0;
      v376 = 0;
      v369 = 0;
      v377 = 0;
      v301 = &v370;
      v370 = &v378;
      v371 = 10;
      v372 = 0;
      v373 = 0;
      v378 = 3;
      v379 = 0;
      v380 = (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                 + SystemThread_TlsIndex)
                                               + SystemThread_TlsOffset)
                                   + 72LL)
                       + 270LL)
            & 4) != 0;
      XeCloudPkg::database_ddl_stmt_tde_start::Publish((XeCloudPkg::database_ddl_stmt_tde_start *)v364);
      TardisDbId = v191;
      v192 = v191;
      v20 = (__int64)v194;
      v76 = v234;
    }
    CSECDEK::SuspendScan((struct DBTABLE *)v20);
    v77 = GetTickCount();
    v259 = 2;
    v260 = 4;
    if ( (qword_102F21DB4 & 0x400000000LL) != 0 )
    {
      v243 = 1;
      v302 = v431;
      v431[0] = 0;
      v431[1] = 1;
      v432 = 0;
      v433 = &v436;
      v434 = &v440;
      v441 = 0;
      v442 = 0;
      v435 = 0;
      v443 = 0;
      v303 = &v436;
      v436 = &v444;
      v437 = 9;
      v438 = 0;
      v439 = 0;
      v444 = 3;
      v445 = v77 - v76;
      XeCloudPkg::database_ddl_stmt_tde_succeeded::Publish((XeCloudPkg::database_ddl_stmt_tde_succeeded *)v430);
    }
    EncryptionWarningForHkV1(v20);
  }
  else if ( (*((_BYTE *)this + 2412) & 0x40) != 0 )
  {
    v81 = GetTickCount();
    v255 = 2;
    v256 = 2;
    if ( (qword_102F21DB4 & 0x200000000LL) != 0 )
    {
      v242 = 1;
      v304 = v382;
      v382[0] = 0;
      v382[1] = 1;
      v383 = 0;
      v384 = &v387;
      v385 = &v391;
      v392 = 0;
      v393 = 0;
      v386 = 0;
      v394 = 0;
      v305 = &v387;
      v387 = &v395;
      v388 = 10;
      v389 = 0;
      v390 = 0;
      v395 = 4;
      v396 = 0;
      v397 = (*(_BYTE *)(*((_QWORD *)v75 + 9) + 270LL) & 4) != 0;
      XeCloudPkg::database_ddl_stmt_tde_start::Publish((XeCloudPkg::database_ddl_stmt_tde_start *)v381);
    }
    v82 = *((_DWORD *)this + 582);
    if ( v82 > 0 )
    {
      if ( !DBTABLE::VerifyValidWorkgroup((DBTABLE *)v20, *((wchar_t **)this + 292), v82) )
        ex_raise(335, 59, 16, 3);
      DBTABLE::SetTDEWorkgroupName((DBTABLE *)v20, *((wchar_t **)this + 292), *((_DWORD *)this + 582), 1);
    }
    CSECDEK::ResumeScan((struct DBTABLE *)v20);
    v83 = GetTickCount();
    v257 = 2;
    v258 = 4;
    if ( (qword_102F21DB4 & 0x400000000LL) != 0 )
    {
      v241 = 1;
      v306 = v447;
      v447[0] = 0;
      v447[1] = 1;
      v448 = 0;
      v449 = &v452;
      v450 = &v456;
      v457 = 0;
      v458 = 0;
      v451 = 0;
      v459 = 0;
      v307 = &v452;
      v452 = &v460;
      v453 = 9;
      v454 = 0;
      v455 = 0;
      v460 = 4;
      v461 = v83 - v81;
      XeCloudPkg::database_ddl_stmt_tde_succeeded::Publish((XeCloudPkg::database_ddl_stmt_tde_succeeded *)v446);
    }
  }
  CStmtAlterDB::VerifyAndErrorLogOptionChange(this);
  if ( (*((_DWORD *)this + 605) & 0x100000) != 0 || (*v64 & 0x100000) != 0 )
  {
    if ( (*((_DWORD *)this + 602) & 0x809E00) != 0 || (*((_DWORD *)this + 601) & 0x809E00) != 0 )
    {
      LODWORD(v181) = *(_DWORD *)(v20 + 928);
      ex_raise(50, 82, 16, 1, v181, v20 + 936);
    }
    if ( *((_DWORD *)this + 635) != -2 )
      ex_raise(50, 83, 16, 1);
    if ( (*((_DWORD *)this + 606) & 0x100000) != 0 )
    {
      v84 = *((_BYTE *)qword_102ECFB10 + 451);
      v217 = v84 >> 1;
      if ( (v84 & 2) != 0 || (v216 = v84, (v84 & 1) != 0) || (v215 = *((_BYTE *)qword_102ECFB10 + 450) >> 7) != 0 )
        ex_raise(50, 85, 16, 1);
    }
    if ( DbVerStateMgr::IsDbAlwaysVersioned((struct DBTABLE *)v20) )
      ex_callprint(3987, 10, 1);
  }
  v308 = v466;
  v85 = v206;
  CCompExecCtxt::CCompExecCtxt((CCompExecCtxt *)v466, v206);
  v467 = *((_QWORD *)v85 + 22);
  v86 = v211;
  if ( !(unsigned __int8)CStmtAlterDB::IsSDSDbOperation(v87, v211, v466) )
    goto LABEL_271;
  if ( (*((_DWORD *)this + 601) & 0x400) == 0 )
  {
    if ( (*((_DWORD *)this + 602) & 0x400) != 0 )
    {
      v88 = v478 >> 7;
      v89 = v478 | 0x80;
      goto LABEL_255;
    }
LABEL_271:
    v93 = 0;
    v246 = 0;
    v309 = v468;
    v94 = v206;
    CCompExecCtxt::CCompExecCtxt((CCompExecCtxt *)v468, v206);
    v469 = *((_QWORD *)v94 + 22);
    if ( (unsigned __int8)CStmtAlterDB::IsSDSDbOperation(v95, v86, v468)
      && *(_WORD *)(*(_QWORD *)(v20 + 4624) + 1674LL) == 3
      && !*(_DWORD *)(GetXdbServerGlobals(v96) + 8196) )
    {
      v93 = IMetadataAccessRemoteLogicalMasterGet(*(struct IMemObj **)(v20 + 688), v230);
      v97 = v282;
      if ( v93 )
        v97 = 0;
      v282 = v97;
      v246 = v93;
    }
    if ( (*((_DWORD *)this + 606) & 0xD3411D) != 0 || (*((_DWORD *)this + 605) & 0xD3411D) != 0 )
    {
      v93 = v246;
      v187 = v246;
      v185 = v230;
      v181 = (CStmtAlterDB *)((char *)this + 2420);
      v98 = v191;
      v192 = v191;
      DBMgr::ChangeDBSEOption(*(_QWORD *)(qword_102ECFB00 + 32), v191, v190);
      v20 = (__int64)v194;
      v86 = v211;
    }
    else
    {
      v98 = v192;
    }
    if ( *((_DWORD *)this + 618) != 0x80000000 )
    {
      v99 = (DBTABLE *)g_dbtableFactory[4](v98);
      if ( !v99 )
        utassert_fail(1u, "dbt", "stdb.cpp", 13043, 0);
      v100 = *((_DWORD *)this + 618);
      if ( v100 < 0 )
      {
        utassert_fail(1u, "m_RecoverySeconds >= 0", "stdb.cpp", 13044, 0);
        v100 = *((_DWORD *)this + 618);
      }
      DBTABLE::SetRecoveryTime(v99, v100);
    }
    if ( (*((_DWORD *)this + 604) & 0xD7D7FF7C) != 0 || (*((_DWORD *)this + 603) & 0xD7D7FF7C) != 0 )
    {
      REStatFromDbRegAttr = GetREStatFromDbRegAttr((const struct MDAttrDbReg *)v471);
      v102 = *((_DWORD *)this + 603) & REStatFromDbRegAttr;
      if ( (*((_BYTE *)this + 2412) & (unsigned __int8)REStatFromDbRegAttr & 4) != 0
        || (*((_BYTE *)this + 2416) & 4) != 0 && (REStatFromDbRegAttr & 4) == 0 )
      {
        v200 = 1;
      }
      if ( v20 && (v214 = *(_BYTE *)(GetXdbServerGlobals(v102) + 12004)) != 0 && *(_QWORD *)(v20 + 5320) && v226 != 27 )
      {
        FidoGLMController = DBTABLE::GetFidoGLMController((DBTABLE *)v20);
        if ( (*(unsigned __int8 (__fastcall **)(struct IFidoGLMController *))(*(_QWORD *)FidoGLMController + 152LL))(FidoGLMController) )
          utassert_fail(1u, "!dbtable->GetFidoGLMController()->FIsFidoGlmServer()", "stdb.cpp", 14534, 0);
        v310 = &v501;
        v501 = 0;
        v502 = 0;
        v311 = v504;
        v104 = 2;
        v283 = 2;
        v105 = v504;
        for ( i = v504; ; i = v105 )
        {
          v106 = v104--;
          v283 = v104;
          if ( !v106 )
            break;
          v269 = 0;
          v270 = 0;
          v271 = 0;
          *(_QWORD *)v105 = 0;
          *((_WORD *)v105 + 4) = 0;
          *((_WORD *)v105 + 5) = 0;
          *(GUID *)(v105 + 12) = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
          v105 += 28;
        }
        v312 = v505;
        v107 = 3;
        v285 = 3;
        v108 = v505;
        for ( j = v505; ; j = v108 )
        {
          v109 = v107--;
          v285 = v107;
          if ( !v109 )
            break;
          v272 = 0;
          v273 = 0;
          v274 = 0;
          *(_QWORD *)v108 = 0;
          *((_WORD *)v108 + 4) = 0;
          *((_DWORD *)v108 + 3) = 0;
          *((_WORD *)v108 + 5) = 0;
          v108 += 16;
        }
        v313 = &v506;
        v314 = &v506;
        v506 = 0;
        v507 = 0;
        v508 = 0;
        v509 = 0;
        v110 = DBTABLE::GetFidoGLMController((DBTABLE *)v20);
        (*(void (__fastcall **)(struct IFidoGLMController *, char *, _QWORD))(*(_QWORD *)v110 + 288LL))(v110, v500, 0);
        DBTABLE::SetRelStat((DBTABLE *)v20, v503);
        v111 = 0;
        v112 = *((_QWORD *)this + 316);
        v113 = v112;
        v287 = v112;
        while ( v113 )
        {
          if ( *(_DWORD *)(v112 + 8) == 12 )
          {
            if ( *(_DWORD *)v113 == 10 || *(_DWORD *)v113 == 11 || (unsigned int)(*(_DWORD *)v113 - 12) <= 1 )
              v111 |= 1u;
            v113 = *(_QWORD *)(v113 + 32);
            v287 = v113;
          }
        }
        if ( v111 )
          ex_callprint(9128, 10, 1);
      }
      else
      {
        DBMgr::ChangeDBREOption(
          *(_QWORD *)(qword_102ECFB00 + 32),
          v86,
          v98,
          v190,
          *((_DWORD *)this + 604),
          *((_DWORD *)this + 603),
          v93);
        if ( (*((_DWORD *)this + 604) & 0x100) != 0 )
        {
          LOBYTE(v114) = 4;
          DBMgr::ChangeDBREOption(*(_QWORD *)(qword_102ECFB00 + 32), v86, 2, v114, 256, 0, v93);
        }
      }
    }
    v115 = *((_DWORD *)this + 617);
    if ( v115 )
    {
      v315 = &v227;
      v227 = v115;
      v181 = v93;
      CStmtAlterDB::SetDBCompatibilityLevel(this, v20, &v227, &v207);
    }
    v116 = *((_BYTE *)this + 2544);
    if ( (v116 & 0x20) != 0 )
    {
      ProcessTemporalHistoryRetentionDDL(v86, v98, (struct DBTABLE *)v20, (v116 & 0x40) != 0, v181);
      v189 = 1;
    }
    v117 = *((_BYTE *)this + 2545);
    if ( (v117 & 0x10) != 0 )
    {
      ProcessDataRetentionDDL(v86, v98, (struct DBTABLE *)v20, (v117 & 0x20) != 0, v181);
      v189 = 1;
    }
    v316 = v93;
    if ( v93 )
      (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v93)(v93, 1);
    v118 = (struct CChangeQDSDDLInfo *)*((_QWORD *)this + 330);
    if ( v118 )
    {
      v119 = ProcessChangeQDSDDL((struct DBTABLE *)v20, v118);
      v120 = v189;
      if ( v119 )
        v120 = 1;
      v189 = v120;
    }
    if ( *((_QWORD *)this + 331) )
      ProcessChangeATDDL(v86, v20);
    v121 = *((unsigned int *)this + 607);
    if ( (_DWORD)v121 != 3 && *(_DWORD *)(*(_QWORD *)(v20 + 4624) + 2136LL) != (_DWORD)v121 )
    {
      DBMgr::ChangeDBLCOption(*(_QWORD *)(qword_102ECFB00 + 32), v98, v121, &v207);
      v189 = 1;
    }
    if ( *((_QWORD *)this + 329) )
    {
      v122 = *(DBTABLE **)(*(_QWORD *)(v20 + 4624) + 1712LL);
      if ( (*((_BYTE *)v122 + 60) & 1) != 0 && !DBTABLE::IsCOWReplicaDatabase(v122) )
      {
        if ( !*((_BYTE *)qword_102EF3550 + 1428) || (v213 = *((_BYTE *)qword_102ECFB10 + 1420) >> 5, (v213 & 1) != 0) )
          ex_raise(494, 10, 16, 1);
      }
      ProcessChangeTrackingDDL(v86, v98, *((struct CChangeTrackDbDDLInfo **)this + 329));
      v189 = 1;
    }
    v123 = (struct StretchDbDDLInfo *)*((_QWORD *)this + 332);
    if ( v123 )
    {
      ProcessStretchDDL(v86, v98, v123);
      v189 = 1;
    }
    v124 = *((_BYTE *)this + 2545);
    if ( v124 < 0 )
    {
      if ( *((_BYTE *)qword_102EF3550 + 204) || (v224 = *((_BYTE *)qword_102ECFB10 + 801) >> 6, (v224 & 1) != 0) )
      {
        v125 = ProcessDataTieredDDL(v86, v98, (v124 & 0x40) != 0);
        v126 = v189;
        if ( v125 )
          v126 = 1;
        v189 = v126;
      }
      else
      {
        ex_raise(196, 17, 16, 1);
      }
    }
    v127 = *((unsigned int *)this + 613);
    if ( (_DWORD)v127 )
    {
      LODWORD(v187) = *((_DWORD *)this + 568);
      DBMgr::ChangeADROption(*(_QWORD *)(qword_102ECFB00 + 32), v98, v127, &v207, v86, *((_QWORD *)this + 285), v187);
      v189 = 1;
    }
    v128 = *((unsigned int *)this + 615);
    if ( (_DWORD)v128 )
    {
      DBMgr::ChangeOLOption(*(_QWORD *)(qword_102ECFB00 + 32), v98, v128, &v207);
      v189 = 1;
    }
    v129 = *((unsigned __int8 *)this + 2456);
    if ( (_BYTE)v129 )
    {
      DBMgr::ChangeSPDOption(*(_QWORD *)(qword_102ECFB00 + 32), v98, v129, &v207);
      v189 = 1;
    }
    v130 = *((unsigned __int8 *)this + 2457);
    if ( (_BYTE)v130 )
    {
      DBMgr::ChangeSuspendForSnapshotBackupOption(*(_QWORD *)(qword_102ECFB00 + 32), v98, v130, &v207);
      v189 = 1;
    }
    v131 = *((unsigned __int8 *)this + 2464);
    if ( (_BYTE)v131 )
    {
      DBMgr::ChangeInMemorydbOption(*(_QWORD *)(qword_102ECFB00 + 32), v98, v131, &v207);
      v189 = 1;
    }
    if ( *((_DWORD *)this + 640) )
    {
      if ( FSystemDatabase(*((const wchar_t **)this + 276), *((_DWORD *)this + 554), v98, 1) )
      {
        v132 = LookupOptionName(47, (struct opttype *)&OptDBOptions);
        v133 = -1;
        do
          ++v133;
        while ( v132[v133] );
        v317 = 2 * v133;
        LODWORD(v187) = *((_DWORD *)this + 554);
        LODWORD(v181) = 2 * v133;
        ex_raise(50, 58, 16, 11, v181, v132, v187, *((_QWORD *)this + 276));
      }
      ProcessMixedPageAllocationSetting(v86, v98, *((unsigned int *)this + 640));
      v189 = 1;
    }
    v134 = *((_BYTE *)this + 2545);
    if ( (v134 & 8) != 0 )
    {
      ProcessScalableTempdbSetting(v86, v98, (v134 & 4) != 0);
      v189 = 1;
    }
    if ( (*((_DWORD *)this + 606) & 0x900000) != 0 )
    {
      v135 = (void (__fastcall ***)(_QWORD, _QWORD, _BYTE *, _QWORD))(*(__int64 (__fastcall **)(struct IMetadataAccess *))(*(_QWORD *)v86 + 72LL))(v86);
      memset_0(v497, 0, 0x188u);
      v498 = -1;
      (**v135)(v135, *(unsigned __int16 *)(v20 + 40), v497, 0);
      if ( (v499 & 8) != 0 )
        ex_callprint(33416, 10, 2);
    }
    if ( v20 )
    {
      if ( !(unsigned int)DBTABLE::GetCurrentState(v20) )
      {
        FFtSql = GetFFtSql();
        if ( (**(unsigned __int8 (__fastcall ***)(struct IFFtSql *))FFtSql)(FFtSql) )
        {
          if ( v205 != v204 || v197 != v198 )
          {
            LODWORD(v185) = 0;
            LODWORD(v181) = 1;
            v137 = (*(__int64 (__fastcall **)(struct IMetadataAccess *, _QWORD, _QWORD, _QWORD, struct IFTCatList *, struct Worker *))(*(_QWORD *)v86 + 56LL))(
                     v86,
                     *(unsigned __int16 *)(v20 + 40),
                     0,
                     0,
                     v181,
                     v185);
            v483[0] = 0;
            v484 = 0;
            v485 = 0;
            v486 = 0;
            v488 = 0;
            v489 = 0;
            memset_0(v487, 0, sizeof(v487));
            if ( (*(unsigned __int8 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v137 + 1216LL))(v137, v483) )
            {
              v199 = 0;
              v259 = 0;
              if ( v484 && (!v205 && v204 == 5 || (v197 & 0x1000) != 0 && (v198 & 0x1000) == 0) )
              {
                v484 = 0;
LABEL_387:
                v199 = 1;
                v489 |= 1u;
                v138 = GetFFtSql();
                v139 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v209 + 432LL))(v209);
                LOBYTE(v187) = 0;
                LOBYTE(v185) = 0;
                LOBYTE(v181) = 1;
                (*(void (__fastcall **)(struct IFFtSql *, __int64, __int64, _WORD *, _DWORD, _DWORD, struct IMetadataAccess *))(*(_QWORD *)v138 + 24LL))(
                  v138,
                  v20,
                  v139,
                  v483,
                  (_DWORD)v181,
                  (_DWORD)v185,
                  v187);
                goto LABEL_388;
              }
              if ( (v197 & 0x400) != 0 && (v198 & 0x400) == 0 && v484 == 2 )
              {
                v484 = 1;
                goto LABEL_387;
              }
            }
          }
        }
      }
    }
LABEL_388:
    v238 = 0;
    if ( (*((_DWORD *)this + 602) & 0x809E00) == 0 && (*((_DWORD *)this + 601) & 0x809E00) == 0 )
    {
      if ( *((_QWORD *)this + 319) )
      {
        if ( (v140 = *(_QWORD *)(v20 + 4624), v141 = *(_QWORD *)(v140 + 1712), *(_DWORD *)(v141 + 784))
          && (*(_QWORD *)(v141 + 788) != *(_QWORD *)&x_AG_DB_IdBad.Data1
           || *(_QWORD *)(v141 + 796) != *(_QWORD *)x_AG_DB_IdBad.Data4)
          && *(_BYTE *)(v140 + 8272)
          || *(_DWORD *)(v20 + 1648) && !DBTABLE::IsOnline((DBTABLE *)v20) )
        {
          LODWORD(v181) = *(_DWORD *)(v20 + 928);
          ex_raise(334, 46, 16, 1, v181, v20 + 936);
        }
      }
      v142 = 0;
      v228 = 0;
      v143 = 0;
      for ( k = 0; ; k = v143 )
      {
        v228 = (int)v143;
        if ( (int)k >= 5 )
          break;
        if ( *((_BYTE *)this + 8 * (int)k + 2672) )
        {
          v202 = (int)v143;
          goto LABEL_404;
        }
        v143 = (const struct CCompExecCtxtStmt *)(unsigned int)((_DWORD)k + 1);
      }
      v202 = -1;
LABEL_404:
      if ( !*((_QWORD *)this + 333) && v202 < 0 )
      {
LABEL_425:
        if ( *((_QWORD *)this + 319) )
        {
          v149 = GetFFtSql();
          if ( (**(unsigned __int8 (__fastcall ***)(struct IFFtSql *))v149)(v149) )
          {
            v150 = GetFFtSql();
            v151 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v209 + 432LL))(v209);
            LOBYTE(v187) = 0;
            LOBYTE(v185) = 1;
            LOBYTE(v181) = 1;
            (*(void (__fastcall **)(struct IFFtSql *, __int64, __int64, _QWORD, struct IFTCatList *, struct Worker *, struct IMetadataAccess *))(*(_QWORD *)v150 + 24LL))(
              v150,
              v20,
              v151,
              *((_QWORD *)this + 319),
              v181,
              v185,
              v187);
          }
        }
        if ( *((_DWORD *)this + 634) )
        {
          v152 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(qword_102ECFB00 + 43248) + 32LL))(*(_QWORD *)(qword_102ECFB00 + 43248));
          (*(void (__fastcall **)(__int64, struct IMetadataAccess *, __int64, _QWORD))(*(_QWORD *)v152 + 24LL))(
            v152,
            v86,
            v20,
            *((unsigned int *)this + 634));
        }
        if ( v189 )
        {
          v153 = (struct BaseXact *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v209 + 432LL))(v209);
          DBMgr::SyncBootPageWithDbReg((struct DBTABLE *)v20, v153, 0);
        }
        if ( v200 )
        {
          if ( (*((_BYTE *)this + 2416) & 4) != 0 )
          {
            MatchingPartitionIndexViewHelper::CreateMPIdxViews(v206, k, v86, v98);
          }
          else if ( (*((_BYTE *)this + 2412) & 4) != 0 )
          {
            MatchingPartitionIndexViewHelper::DropAllMPIdxViews(v143, k, v86, v98);
          }
        }
        v211 = 0;
        if ( v86 )
          (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v86)(v86, 1);
        CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v207, 0);
        if ( v142 || v202 >= 0 )
        {
          CheckpointDB(v98, 0, 0);
LABEL_511:
          if ( v20 && (v189 || v238) )
            DBTABLE::RefreshDbOptions((DBTABLE *)v20, 0);
LABEL_515:
          if ( v189 )
          {
            LOBYTE(v154) = 1;
            CCache::RemoveByDbid(v98, 15, v154);
          }
          if ( v193 )
            unlockdb(v98, 43, v190);
          v212 = v206;
          v212 = *(struct CCompExecCtxt **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset);
          v175 = *(unsigned __int16 *)(*((_QWORD *)v212 + 10) + 8LL);
          if ( v175 != v191 )
          {
            v212 = 0;
            DBMgr::TryToClose(*(_QWORD *)(qword_102ECFB00 + 32), 0);
          }
          if ( v231 )
          {
            v324 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
            FullTextRunDelayOperation(v175, 1, 0, &v324, v231);
          }
          if ( v225 )
            (*(void (__fastcall **)(struct IFidoGLMController *))(*(_QWORD *)v225 + 24LL))(v225);
          ExcHandler::~ExcHandler((ExcHandler *)v329);
          v176 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v177 = *(struct Worker **)(v176 + 256);
          if ( !v177 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v177 = *(struct Worker **)(v176 + 256);
          }
          if ( *((_DWORD *)v177 + 139) )
            ExceptionPostCatchActions(v177);
          if ( v231 )
            (**(void (__fastcall ***)(struct IFTCatList *))v231)(v231);
          if ( v196 )
          {
            v196 = 0;
            ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
          }
          if ( (_DWORD)v207 )
            goto LABEL_534;
          goto LABEL_535;
        }
LABEL_510:
        v98 = v192;
        goto LABEL_511;
      }
      if ( DBTABLE::IsOffline((DBTABLE *)v20) )
      {
        LODWORD(v181) = *(_DWORD *)(v20 + 928);
        ex_raise(9, 42, 14, 6, v181, v20 + 936);
      }
      v235 = *(_DWORD *)(v20 + 3888);
      v145 = v235;
      if ( v235 != v476 )
      {
        LODWORD(v181) = *((_DWORD *)this + 554);
        ex_raise(128, 43, 16, 1, v181, *((_QWORD *)this + 276));
      }
      v146 = (_DWORD *)*((_QWORD *)this + 333);
      if ( v145 == 1 )
      {
        if ( v146 && !*v146 )
        {
          if ( v202 >= 0 )
          {
            _mm_lfence();
            LODWORD(v181) = *((_DWORD *)&off_10303F0C0 + 4 * v202 + 2);
            ex_raise(128, 7, 16, 1, v181, (&off_10303F0C0)[2 * v202]);
          }
          v142 = 1;
          goto LABEL_423;
        }
      }
      else
      {
        if ( v146 && *v146 )
        {
          v142 = 1;
          if ( (v481 & 2) != 0
            || (v481 & 4) != 0
            || (v481 & 8) != 0
            || (v481 & 0x10) != 0
            || (v481 & 0x20) != 0
            || (v481 & 0x40) != 0
            || (v482 & 1) != 0 )
          {
            v147 = 38;
            goto LABEL_422;
          }
          if ( v481 < 0 )
          {
            v147 = 46;
LABEL_422:
            LODWORD(v181) = *((_DWORD *)this + 554);
            ex_raise(128, v147, 16, 1, v181, *((_QWORD *)this + 276));
          }
LABEL_423:
          v148 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v209 + 432LL))(v209);
          LOBYTE(v181) = 0;
          DBMgr::ErrorIsCDBAllowed(1, 1, 0, 0, (_DWORD)v181, v148);
          v98 = v191;
          v192 = v191;
          v86 = v211;
          CStmtAlterDB::ProcessContainedDBDDL(
            this,
            v206,
            v211,
            v191,
            (const struct MDAttrDbReg *)v471,
            *((struct CContainedDatabaseDDLInfo **)this + 333),
            (CStmtAlterDB *)((char *)this + 2672));
          v189 = 1;
LABEL_424:
          v20 = (__int64)v194;
          goto LABEL_425;
        }
        if ( v202 >= 0 )
        {
          _mm_lfence();
          LODWORD(v181) = *((_DWORD *)&off_10303F0C0 + 4 * v202 + 2);
          ex_raise(128, 7, 16, 1, v181, (&off_10303F0C0)[2 * v202]);
        }
      }
      v142 = 0;
      if ( v202 < 0 )
      {
        v98 = v191;
        v192 = v191;
        v86 = v211;
        goto LABEL_424;
      }
      goto LABEL_423;
    }
    if ( (*((_DWORD *)this + 601) & 0x400) != 0 && (v478 & 0x20) != 0 )
    {
      LODWORD(v181) = *((_DWORD *)this + 554);
      ex_raise(50, 63, 16, 1, v181, *((_QWORD *)this + 276));
    }
    if ( v201 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v268 + 88LL))(v268, v98);
    v211 = 0;
    v318 = v86;
    if ( v86 )
      (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v86)(v86, 1);
    CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v207, 0);
    DBMgr::ChangeDBState(
      *(DBMgr **)(qword_102ECFB00 + 32),
      v98,
      (const unsigned int *)this + 602,
      (const unsigned int *)this + 601,
      *((_DWORD *)this + 635));
    v262 = qword_102ECFB00;
    v155 = *(_QWORD *)(qword_102ECFB00 + 32);
    v288 = v155;
    switch ( v98 )
    {
      case 0x7FFCu:
        v20 = *(_QWORD *)(v155 + 104);
        break;
      case 0x7FFDu:
        v20 = *(_QWORD *)(v155 + 112);
        break;
      case 0x7FFFu:
        v20 = *(_QWORD *)(v155 + 88);
        break;
      default:
        if ( v98 > *(_DWORD *)(v155 + 76) || !v98 )
          goto LABEL_515;
        _mm_lfence();
        v192 = v191;
        v20 = *(_QWORD *)(*(_QWORD *)(v288 + 40) + 8LL * (int)(v191 - 1));
        break;
    }
    if ( !v20 )
      goto LABEL_510;
    if ( *(_DWORD *)(v20 + 3888) != v476 )
      scierrlog(0x322Bu, *((unsigned int *)this + 554), *((_QWORD *)this + 276));
    if ( (unsigned int)DBTABLE::GetCurrentState(v20) )
      goto LABEL_510;
    v156 = GetSEStatFromDbRegAttr((const struct MDAttrDbReg *)v471);
    v198 = v156;
    v197 = v156;
    v197 = *((_DWORD *)this + 602) | v156 & ~*((_DWORD *)this + 601);
    v157 = v197;
    v158 = GetAvailabilityFromStatus(v156);
    v205 = v158;
    v204 = GetAvailabilityFromStatus(v157);
    if ( v158 == v204 && v157 == v156
      || (v159 = GetFFtSql(), !(**(unsigned __int8 (__fastcall ***)(struct IFFtSql *))v159)(v159)) )
    {
LABEL_500:
      if ( (v156 & 0x1000) != 0 && (v157 & 0x1000) == 0 )
      {
        v265 = &AutoReadOnlyIMA::`vftable';
        v266 = 0;
        v212 = (struct CCompExecCtxt *)&v267;
        v267 = 0;
        v170 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v171 = *(_QWORD *)(v170 + 256);
        if ( !v171 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v171 = *(_QWORD *)(v170 + 256);
        }
        v172 = *(_QWORD *)(v171 + 1000);
        AutoReadOnlyXact::BeginCompatibleXact((AutoReadOnlyXact *)&v267, L"StretchDbStateChange", 40, 0);
        ((void (__fastcall *)(void ***, __int64))*v265)(&v265, v172);
        LODWORD(v185) = 0;
        v98 = v191;
        v173 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int, struct Worker *))(*(_QWORD *)v266 + 56LL))(
                 v266,
                 v191,
                 0,
                 0,
                 1,
                 v185);
        v237 = 0;
        v174 = v173 && (*(unsigned __int8 (__fastcall **)(__int64, int *))(*(_QWORD *)v173 + 1688LL))(v173, &v237);
        AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v265);
        if ( v174 )
        {
          EnqueueStretchDbid(v191);
          EnqueueRepopulateStretchSchemaTaskQueueTask(v191);
        }
        goto LABEL_511;
      }
      goto LABEL_510;
    }
    v208 = 1;
    v262 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset);
    *(_QWORD *)&v209 = *(_QWORD *)(v262 + 144);
    v262 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset);
    v160 = *(_BYTE *)(v262 + 152);
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v209 + 464LL))(v209) )
    {
      if ( v160 && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v209 + 488LL))(v209) )
        utassert_fail(
          1u,
          "rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()",
          "automsqlxact.cpp",
          235,
          0);
      (*(void (__fastcall **)(_QWORD, __int64, __int64, char *))(*(_QWORD *)v209 + 232LL))(
        v209,
        2,
        1,
        (char *)&v207 + 4);
      v208 = 1;
      LODWORD(v207) = 3;
    }
    else
    {
      LOBYTE(v187) = 0;
      LODWORD(v185) = 1;
      (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64, __int64, int, struct Worker *, struct IMetadataAccess *, _QWORD, bool))(*(_QWORD *)v209 + 8LL))(
        v209,
        L"FILESTREAM",
        20,
        1,
        2,
        v185,
        v187,
        0,
        v160 != 0);
      LODWORD(v207) = 1;
    }
    v275 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v209 + 432LL))(v209);
    v161 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v162 = *(_QWORD *)(v161 + 256);
    if ( !v162 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v162 = *(_QWORD *)(v161 + 256);
    }
    v163 = ((__int64 (__fastcall *)(_QWORD, __int64, const char *, __int64))g_metadataFactory)(
             *(_QWORD *)(v162 + 1000),
             v275,
             "sql\\ntdbms\\msql\\proc\\stdb.cpp",
             14912);
    v232 = v163;
    v277 = v163;
    LODWORD(v185) = 0;
    v192 = v191;
    v164 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int, struct Worker *))(*(_QWORD *)v163 + 56LL))(
             v163,
             v191,
             0,
             0,
             1,
             v185);
    v490[0] = 0;
    v491 = 0;
    v492 = 0;
    v493 = 0;
    v495 = 0;
    v496 = 0;
    memset_0(v494, 0, sizeof(v494));
    if ( (*(unsigned __int8 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v164 + 1216LL))(v164, v490) )
    {
      if ( !v204 && v205 )
      {
        LOWORD(v157) = v197;
        LOWORD(v156) = v198;
LABEL_491:
        if ( v491 != v492 && ((v157 & 0x400) == 0 || v491 != 1) )
        {
          v491 = v492;
          v496 |= 1u;
        }
        v165 = GetFFtSql();
        v166 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v209 + 432LL))(v209);
        LOBYTE(v187) = 1;
        LOBYTE(v185) = 1;
        LOBYTE(v183) = 1;
        (*(void (__fastcall **)(struct IFFtSql *, __int64, __int64, _WORD *, int, _DWORD, struct IMetadataAccess *))(*(_QWORD *)v165 + 24LL))(
          v165,
          v20,
          v166,
          v490,
          v183,
          (_DWORD)v185,
          v187);
        goto LABEL_499;
      }
      LOWORD(v157) = v197;
      LOWORD(v156) = v198;
      if ( (v197 & 0x1000) == 0 && (v198 & 0x1000) != 0 || (v197 & 0x400) == 0 && (v198 & 0x400) != 0 )
        goto LABEL_491;
      v167 = GetFFtSql();
      v168 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v209 + 432LL))(v209);
      LOBYTE(v183) = 0;
      LOBYTE(v169) = 1;
      v236 = (*(__int64 (__fastcall **)(struct IFFtSql *, __int64, __int64, __int64, int))(*(_QWORD *)v167 + 40LL))(
               v167,
               v20,
               v168,
               v169,
               v183);
      if ( v236 >= 0 )
      {
LABEL_499:
        v277 = 0;
        (**(void (__fastcall ***)(__int64, __int64))v163)(v163, 1);
        CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v207, 0);
        goto LABEL_500;
      }
      _mm_lfence();
      LODWORD(v185) = v236;
      LODWORD(v184) = 13030;
      scierrlogwithstate(0x827Du, 10, 15, 13105, v184, v185);
      v192 = v191;
      v163 = v232;
    }
    LOWORD(v156) = v198;
    LOWORD(v157) = v197;
    goto LABEL_499;
  }
  v88 = v478 >> 7;
  v89 = v478 & 0x7F;
LABEL_255:
  v478 = v89;
  if ( v88 != v89 >> 7 )
  {
    v229 = *(_DWORD *)(v20 + 2256);
    v90 = v470;
    v91 = v471;
    v92 = 3;
    do
    {
      *v90 = *v91;
      v90[1] = v91[1];
      v90[2] = v91[2];
      v90[3] = v91[3];
      v90[4] = v91[4];
      v90[5] = v91[5];
      v90[6] = v91[6];
      v90 += 8;
      *(v90 - 1) = v91[7];
      v91 += 8;
      --v92;
    }
    while ( v92 );
    *(_QWORD *)v90 = *(_QWORD *)v91;
    LOBYTE(v181) = 1;
    DBMgr::UpdateLogicalWriteStatus(*(_QWORD *)(qword_102ECFB00 + 32), v20, v470, v230, (_DWORD)v181);
  }
  v211 = 0;
  if ( v86 )
    (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v86)(v86, 1);
  CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v207, 0);
  if ( v193 )
    unlockdb(TardisDbId, 43, v190);
  if ( v225 )
    (*(void (__fastcall **)(struct IFidoGLMController *))(*(_QWORD *)v225 + 24LL))(v225);
  ExcHandler::~ExcHandler((ExcHandler *)v329);
  if ( v231 )
    (**(void (__fastcall ***)(struct IFTCatList *))v231)(v231);
  if ( v196 )
  {
    v196 = 0;
    ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
  }
  if ( (_DWORD)v207 )
LABEL_534:
    CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v207, 0);
LABEL_535:
  AutoOverrideMsqlXact::~AutoOverrideMsqlXact((AutoOverrideMsqlXact *)&v289);
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
