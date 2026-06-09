# XdesRMReadWrite::RollbackToLsn(LSN const &,LogIter &,IndexErrorTable *,AllocUnitId const &)

- ea: `0x1005b4980`
- end: `0x1005b49c5`
- name: `?RollbackToLsn@XdesRMReadWrite@@QEAAXAEBVLSN@@AEAVLogIter@@PEAVIndexErrorTable@@AEBVAllocUnitId@@@Z`
- size: `69`
- prototype: `void __fastcall(XdesRMReadWrite *__hidden this, const struct LSN *, struct LogIter *, struct IndexErrorTable *, const struct AllocUnitId *)`
- caller_count: `11`
- callee_count: `62`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1004c2450`
- `0x1005ae5c0`
- `0x101cd4370`
- `0x101cd4ff0`
- `0x101cd5910`
- `0x101d75720`
- `0x101d78640`
- `0x101d8cdc0`
- `0x101d8ea80`
- `0x101d994c0`
- `0x101d9af10`

## callees

- `0x100401010`
- `0x100401380`
- `0x1004013f0`
- `0x100401490`
- `0x100401fcf`
- `0x100402000`
- `0x100403030`
- `0x100403dc0`
- `0x10040da80`
- `0x100415e90`
- `0x100416bb0`
- `0x100445560`
- `0x10045f010`
- `0x10046bfd0`
- `0x10047bc10`
- `0x10047ffb0`
- `0x1004807a0`
- `0x1004a1740`
- `0x1004c4220`
- `0x1004d2c70`
- `0x100553e20`
- `0x1005b1000`
- `0x1005b1210`
- `0x1005b1260`
- `0x1005b1c20`
- `0x1005b4980`
- `0x1005dc8a0`
- `0x1006abf70`
- `0x100865880`
- `0x101647120`
- `0x1016c9e80`
- `0x1018c9d70`
- `0x101970b40`
- `0x101a45380`
- `0x101b44340`
- `0x101b46a10`
- `0x101b58870`
- `0x101b60910`
- `0x101b83cf0`
- `0x101b84050`
- `0x101b84450`
- `0x101b847d0`
- `0x101bdf770`
- `0x101c39410`
- `0x101cd9730`
- `0x101cdbfc0`
- `0x101cdf010`
- `0x101d0c800`
- `0x101d6ab40`
- `0x101d71ee0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x101d7167e`
- `KERNEL32!SetLastError` at `0x101d7167e`
- `KERNEL32!VirtualProtect` at `0x101d701b5`
- `KERNEL32!VirtualProtect` at `0x101d71d93`
- `KERNEL32!VirtualProtect` at `0x101d701b5`
- `KERNEL32!VirtualProtect` at `0x101d71d93`
- `KERNEL32!QueryPerformanceCounter` at `0x1005b164f`
- `KERNEL32!QueryPerformanceCounter` at `0x1005b17a9`
- `KERNEL32!QueryPerformanceCounter` at `0x101d6fdd4`
- `KERNEL32!QueryPerformanceCounter` at `0x1005b164f`
- `KERNEL32!QueryPerformanceCounter` at `0x1005b17a9`
- `KERNEL32!QueryPerformanceCounter` at `0x101d6fdd4`
- `KERNEL32!GetLastError` at `0x101d71595`
- `KERNEL32!GetLastError` at `0x101d71595`
- `sqlTsEs!?ConvertToWstr@SQLDATE@@QEBAJPEA_WKPEAKJPEBQEB_WW4EPadding@@@Z` at `0x1005b3839`
- `sqlTsEs!?ConvertToWstr@SQLDATE@@QEBAJPEA_WKPEAKJPEBQEB_WW4EPadding@@@Z` at `0x1005b3839`
- `sqldk!?hdl_rethrow@@YAHHHHHPEAD@Z` at `0x1005b1900`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1005b162f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1005b1789`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1005b1823`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101d6fdb8`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x1005b183b`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101d71a08`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101d71b67`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101d71e89`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101d71ebe`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101d71a08`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101d71b67`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101d71e89`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101d71ebe`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x101d718ee`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101d71651`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101d71651`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d6fa9a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d6fbe2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d702bc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d70322`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d70514`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d70549`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d709fe`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d70a33`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d713da`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d7141b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d71ad2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d6fa9a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d6fbe2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d702bc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d70322`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d70514`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d70549`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d709fe`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d70a33`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d713da`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d7141b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d71ad2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1005b3960`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d6fbb1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d7146f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1005b3960`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d6fbb1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d7146f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d71120`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d716c3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d71120`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d716c3`
- `sqldk!SystemThread_TlsIndex` at `0x1005b12f6`
- `sqldk!SystemThread_TlsIndex` at `0x1005b143c`
- `sqldk!SystemThread_TlsIndex` at `0x1005b1499`
- `sqldk!SystemThread_TlsIndex` at `0x1005b1acb`
- `sqldk!SystemThread_TlsIndex` at `0x1005b1b35`
- `sqldk!SystemThread_TlsIndex` at `0x1005b3a75`
- `sqldk!SystemThread_TlsIndex` at `0x1005b3ab1`
- `sqldk!SystemThread_TlsIndex` at `0x1005b3ae9`
- `sqldk!SystemThread_TlsIndex` at `0x101d6faee`
- `sqldk!SystemThread_TlsIndex` at `0x101d71053`
- `sqldk!SystemThread_TlsIndex` at `0x101d715db`
- `sqldk!SystemThread_TlsIndex` at `0x101d719b0`
- `sqldk!SystemThread_TlsOffset` at `0x1005b12ff`
- `sqldk!SystemThread_TlsOffset` at `0x1005b1445`
- `sqldk!SystemThread_TlsOffset` at `0x1005b14aa`
- `sqldk!SystemThread_TlsOffset` at `0x1005b1ad4`
- `sqldk!SystemThread_TlsOffset` at `0x1005b1b3e`
- `sqldk!SystemThread_TlsOffset` at `0x1005b3a7e`
- `sqldk!SystemThread_TlsOffset` at `0x1005b3aba`
- `sqldk!SystemThread_TlsOffset` at `0x1005b3af2`
- `sqldk!SystemThread_TlsOffset` at `0x101d6faf7`
- `sqldk!SystemThread_TlsOffset` at `0x101d7105c`
- `sqldk!SystemThread_TlsOffset` at `0x101d715e4`
- `sqldk!SystemThread_TlsOffset` at `0x101d719b9`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101d71529`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101d71529`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d6fa65`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d719e2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d71b4c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d71b76`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d71e76`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d71eab`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d6fa65`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d719e2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d71b4c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d71b76`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d71e76`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d71eab`
- `sqldk!??_V@YAXPEAX@Z` at `0x101d70445`
- `sqldk!??_V@YAXPEAX@Z` at `0x101d71a29`
- `sqldk!??_V@YAXPEAX@Z` at `0x101d71a49`
- `sqldk!??_V@YAXPEAX@Z` at `0x101d70445`
- `sqldk!??_V@YAXPEAX@Z` at `0x101d71a29`
- `sqldk!??_V@YAXPEAX@Z` at `0x101d71a49`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x101d7033f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x101d7033f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x101d7034b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x101d7034b`
- `sqllang!?CheckPermRuleAuditOnly@ISECManager@@SAXW4ESECSecuredOperation@@PEAVIMemObj@@PEAVIMetadataAccess@@KKHW4EObjType@@PEAUAuditEventInfo@@_JU_GUID@@PEAVBatchAuditAdditionalInfo@@HPEAVBaseXact@@K@Z` at `0x101d7197c`
- `sqllang!?CheckPermRuleAuditOnly@ISECManager@@SAXW4ESECSecuredOperation@@PEAVIMemObj@@PEAVIMetadataAccess@@KKHW4EObjType@@PEAUAuditEventInfo@@_JU_GUID@@PEAVBatchAuditAdditionalInfo@@HPEAVBaseXact@@K@Z` at `0x101d7197c`
- `hkengine!HkTransactionRollbackToLastHkTempDbSavePoint` at `0x101d7051d`
- `hkengine!HkTransactionRollbackToLastHkTempDbSavePoint` at `0x101d70a07`
- `hkengine!HkTransactionRollbackToLastHkTempDbSavePoint` at `0x101d7051d`
- `hkengine!HkTransactionRollbackToLastHkTempDbSavePoint` at `0x101d70a07`
- `hkengine!HkScopeExit` at `0x101d7055d`
- `hkengine!HkScopeExit` at `0x101d70a47`
- `hkengine!HkScopeExit` at `0x101d7055d`
- `hkengine!HkScopeExit` at `0x101d70a47`
- `hkengine!HkScopeEnter` at `0x101d704ef`
- `hkengine!HkScopeEnter` at `0x101d709d9`
- `hkengine!HkScopeEnter` at `0x101d704ef`
- `hkengine!HkScopeEnter` at `0x101d709d9`
- `hkruntime!HkRtGetSystem` at `0x101d704b3`
- `hkruntime!HkRtGetSystem` at `0x101d7099d`
- `hkruntime!HkRtGetSystem` at `0x101d704b3`
- `hkruntime!HkRtGetSystem` at `0x101d7099d`

## string_xrefs

- `0x1005b38de`: `RollbackToLsn for system xact: XdesId 0x%x:0x%x; Tran start time: %ls; Begin Tran LSN 0x%x:0x%x:0x%x; Tran Name:%.*ls`
- `0x101d71aab`: `Unexpected log record during rollback`
- `0x101d6fbd9`: `curr->GetXdesId () == m_xdesId`

## pseudocode

```c
// Hidden C++ exception states: #wind=21 #try_helpers=3
void __fastcall XdesRMReadWrite::RollbackToLsn(
        XdesRMReadWrite *this,
        const struct LSN *a2,
        struct LogIter *a3,
        struct IndexErrorTable *a4,
        const struct AllocUnitId *a5)
{
  __int64 v6; // rcx
  struct LogIter *v7; // r14
  __int64 v9; // rbx
  __int64 v10; // rsi
  int v11; // eax
  int v12; // edi
  __int64 v13; // rcx
  _DWORD *v14; // rbx
  XDES *v15; // rdi
  BOOL v16; // ecx
  __int64 v17; // r9
  __int16 v18; // ax
  __int64 v20; // xmm0_8
  __int16 v21; // ax
  __int64 v22; // r13
  _DWORD *v23; // rax
  _DWORD *v24; // rcx
  const struct LSN *v25; // rbx
  unsigned int v26; // eax
  BOOL v27; // eax
  __int64 v28; // rcx
  const struct LSN *v29; // rax
  _DWORD *v30; // r15
  unsigned int *v31; // r14
  BOOL v33; // ebx
  DirtyPageMgr *v34; // rcx
  unsigned __int64 v35; // rcx
  unsigned __int64 v36; // rdx
  __int64 v37; // rdi
  unsigned int v38; // eax
  int (*v39)(int, int, int, int, char *); // rax
  int v40; // eax
  struct IndexErrorTable::IetEntry *Entry; // rax
  unsigned int v42; // eax
  __int64 FCB; // rbx
  const struct LSN *v45; // rax
  struct Worker *v46; // rcx
  __int64 v47; // rbx
  __int64 v48; // rbx
  _QWORD *v49; // r8
  unsigned __int64 v50; // rax
  unsigned __int64 v51; // rdx
  unsigned int v53; // eax
  __int64 v55; // rax
  int v56; // ebx
  __int64 v57; // rcx
  __int64 v58; // rax
  int v59; // eax
  volatile signed __int32 *v60; // rbx
  DatasetSession *v61; // rbx
  struct Worker *v62; // rcx
  __int64 v63; // rbx
  __int64 v64; // rbx
  struct Worker *v65; // rcx
  RecoveryUnit *v66; // rdi
  _DWORD *v67; // rax
  __int64 v68; // r8
  __int64 v69; // rcx
  __int64 v70; // rcx
  const struct LogScanStats *v71; // rax
  bool v72; // al
  __int64 v73; // rbx
  __int64 v74; // rax
  __int64 v75; // rbx
  ProgressReport *v76; // rsi
  __int64 v77; // rcx
  char v78; // al
  __int64 v79; // r8
  __int16 v80; // dx
  BOOL v81; // eax
  __int64 v82; // rcx
  volatile signed __int32 *v83; // rbx
  void *v84; // rcx
  __int64 v85; // rbx
  unsigned int v86; // edi
  __int64 v87; // rax
  void *v88; // r15
  __int64 v90; // rsi
  unsigned int v91; // edi
  unsigned int i; // eax
  _QWORD **v93; // rbx
  _QWORD *v94; // rcx
  RecoveryUnit *v95; // rcx
  __int64 v96; // rbx
  bool v97; // r9
  _BYTE *v98; // rax
  volatile signed __int32 *v99; // rbx
  DatasetSession *v100; // rbx
  int *v101; // rbx
  HoBtFactory *v102; // rcx
  const struct HoBtId *v103; // rdx
  RecoveryUnit *v104; // rcx
  __int64 v105; // rbx
  int v106; // edx
  unsigned __int8 v107; // bl
  unsigned int SchemaScopeId; // eax
  __int64 v109; // rdx
  const struct LSN *v110; // rax
  const struct LSN *v111; // r8
  __int64 v112; // rax
  int v113; // eax
  __int64 v114; // rdi
  XDES *v115; // r13
  struct CSessionTraceFlags *v116; // rcx
  int v117; // eax
  __int64 v118; // r9
  const struct XDES *v119; // rdx
  __int64 v120; // rcx
  const struct XDES *v121; // rdx
  void *v122; // rbx
  const wchar_t *v123; // rsi
  struct IFileSystemHandler *v124; // rax
  unsigned int v125; // ebx
  DWORD LastError; // edi
  __int64 v127; // rax
  int v128; // eax
  wchar_t *OSErrString; // rax
  struct CSessionTraceFlags *v130; // rcx
  __int128 v131; // xmm6
  unsigned __int16 v132; // r14
  __int64 v133; // r12
  int v134; // edi
  const unsigned __int8 *v135; // r15
  unsigned int v136; // esi
  __int64 v137; // rcx
  int j; // ecx
  __int64 v139; // rax
  __int64 v140; // rbx
  struct Worker *v141; // rcx
  int v142; // eax
  __int64 v144; // rcx
  volatile signed __int32 *v145; // rbx
  void *v146; // rcx
  __int64 v147; // rbx
  unsigned int v148; // edi
  __int64 v149; // rax
  struct PageRef *v150; // [rsp+20h] [rbp-3AE8h]
  struct Worker *v151; // [rsp+28h] [rbp-3AE0h]
  __int64 v152; // [rsp+30h] [rbp-3AD8h]
  __int64 v153; // [rsp+38h] [rbp-3AD0h]
  struct LogIter *v154; // [rsp+70h] [rbp-3A98h]
  XDES *v155; // [rsp+78h] [rbp-3A90h]
  BOOL v156; // [rsp+80h] [rbp-3A88h]
  char v157; // [rsp+84h] [rbp-3A84h]
  int v158; // [rsp+88h] [rbp-3A80h]
  __int64 v159; // [rsp+90h] [rbp-3A78h]
  __int64 v160; // [rsp+98h] [rbp-3A70h] BYREF
  char v161; // [rsp+A0h] [rbp-3A68h]
  int v162; // [rsp+A4h] [rbp-3A64h]
  int v163; // [rsp+B0h] [rbp-3A58h]
  int v164; // [rsp+B8h] [rbp-3A50h]
  __int64 v165; // [rsp+C8h] [rbp-3A40h]
  unsigned __int16 v166; // [rsp+D0h] [rbp-3A38h]
  unsigned __int16 v167; // [rsp+DCh] [rbp-3A2Ch]
  XdesRMReadWrite *v168; // [rsp+E0h] [rbp-3A28h]
  char v169; // [rsp+E8h] [rbp-3A20h]
  char v170; // [rsp+E9h] [rbp-3A1Fh]
  char v171; // [rsp+EAh] [rbp-3A1Eh]
  char v172; // [rsp+EBh] [rbp-3A1Dh]
  char v173; // [rsp+ECh] [rbp-3A1Ch]
  char v174; // [rsp+EDh] [rbp-3A1Bh]
  char v175; // [rsp+EFh] [rbp-3A19h]
  DirtyPageMgr *QuadPart; // [rsp+F0h] [rbp-3A18h] BYREF
  char v177; // [rsp+FAh] [rbp-3A0Eh]
  IndexErrorTable *v178; // [rsp+100h] [rbp-3A08h]
  int v179; // [rsp+108h] [rbp-3A00h]
  int v180; // [rsp+10Ch] [rbp-39FCh] BYREF
  __int16 v181; // [rsp+110h] [rbp-39F8h]
  __int16 v182; // [rsp+112h] [rbp-39F6h]
  void *Source; // [rsp+118h] [rbp-39F0h]
  int v184; // [rsp+120h] [rbp-39E8h] BYREF
  __int16 v185; // [rsp+124h] [rbp-39E4h]
  __int16 v186; // [rsp+126h] [rbp-39E2h]
  unsigned __int64 v187; // [rsp+128h] [rbp-39E0h]
  int v188; // [rsp+130h] [rbp-39D8h]
  unsigned int v189; // [rsp+138h] [rbp-39D0h] BYREF
  int v190; // [rsp+140h] [rbp-39C8h]
  int v191; // [rsp+144h] [rbp-39C4h]
  int v192; // [rsp+148h] [rbp-39C0h]
  BOOL v193; // [rsp+14Ch] [rbp-39BCh]
  int v194; // [rsp+150h] [rbp-39B8h]
  int v195; // [rsp+154h] [rbp-39B4h]
  __int16 v196; // [rsp+158h] [rbp-39B0h]
  int v197; // [rsp+15Ch] [rbp-39ACh] BYREF
  __int16 v198; // [rsp+160h] [rbp-39A8h]
  __int16 v199; // [rsp+168h] [rbp-39A0h]
  __int16 v200; // [rsp+170h] [rbp-3998h]
  __int16 v201; // [rsp+178h] [rbp-3990h]
  __int16 v202; // [rsp+180h] [rbp-3988h]
  unsigned __int16 v203; // [rsp+188h] [rbp-3980h]
  __int16 v204; // [rsp+1A0h] [rbp-3968h]
  __int16 v205; // [rsp+1A8h] [rbp-3960h]
  __int16 v206; // [rsp+1C0h] [rbp-3948h]
  int v207; // [rsp+1C8h] [rbp-3940h]
  unsigned int v208[39]; // [rsp+1CCh] [rbp-393Ch] BYREF
  int v209[4]; // [rsp+268h] [rbp-38A0h] BYREF
  int v210; // [rsp+278h] [rbp-3890h]
  int v211; // [rsp+27Ch] [rbp-388Ch]
  unsigned int v212; // [rsp+280h] [rbp-3888h]
  DWORD v213; // [rsp+284h] [rbp-3884h]
  unsigned int v214; // [rsp+288h] [rbp-3880h]
  int v215; // [rsp+28Ch] [rbp-387Ch]
  int v216; // [rsp+290h] [rbp-3878h] BYREF
  DirtyPageMgr *v217; // [rsp+298h] [rbp-3870h] BYREF
  __int64 v218; // [rsp+2A0h] [rbp-3868h]
  int v219; // [rsp+2A8h] [rbp-3860h] BYREF
  __int16 v220; // [rsp+2ACh] [rbp-385Ch]
  __int16 v221; // [rsp+2AEh] [rbp-385Ah]
  __int64 v222; // [rsp+2B0h] [rbp-3858h] BYREF
  int v223; // [rsp+2B8h] [rbp-3850h] BYREF
  __int64 v224; // [rsp+2C0h] [rbp-3848h]
  struct LogIter *v225; // [rsp+2C8h] [rbp-3840h]
  IndexErrorTable *v226; // [rsp+2D8h] [rbp-3830h]
  int v227; // [rsp+2E0h] [rbp-3828h]
  _QWORD v228[2]; // [rsp+2E8h] [rbp-3820h] BYREF
  int v229; // [rsp+2F8h] [rbp-3810h]
  __int16 v230; // [rsp+2FCh] [rbp-380Ch]
  __int16 v231; // [rsp+2FEh] [rbp-380Ah]
  __int64 v232; // [rsp+300h] [rbp-3808h]
  __int16 v233; // [rsp+308h] [rbp-3800h]
  __int64 v234; // [rsp+338h] [rbp-37D0h] BYREF
  __int64 v235; // [rsp+340h] [rbp-37C8h] BYREF
  struct CSessionTraceFlags *v236; // [rsp+348h] [rbp-37C0h]
  void (__fastcall ***v237)(_QWORD, XDES *); // [rsp+350h] [rbp-37B8h] BYREF
  const struct LSN *v238; // [rsp+358h] [rbp-37B0h]
  unsigned __int64 v239; // [rsp+360h] [rbp-37A8h] BYREF
  struct CSessionTraceFlags *v240; // [rsp+368h] [rbp-37A0h]
  unsigned __int64 v241; // [rsp+370h] [rbp-3798h]
  int v242; // [rsp+380h] [rbp-3788h] BYREF
  __int16 v243; // [rsp+384h] [rbp-3784h]
  int v244; // [rsp+388h] [rbp-3780h]
  int v245; // [rsp+38Ch] [rbp-377Ch] BYREF
  __int16 v246; // [rsp+390h] [rbp-3778h]
  __int16 v247; // [rsp+392h] [rbp-3776h]
  __int64 v248; // [rsp+398h] [rbp-3770h]
  unsigned __int64 v249; // [rsp+3A0h] [rbp-3768h]
  __int64 v250; // [rsp+3A8h] [rbp-3760h]
  _BYTE *v251; // [rsp+3B0h] [rbp-3758h]
  _BYTE *v252; // [rsp+3B8h] [rbp-3750h]
  _BYTE *v253; // [rsp+3C0h] [rbp-3748h]
  char v254; // [rsp+3C8h] [rbp-3740h]
  char v255; // [rsp+3C9h] [rbp-373Fh]
  char v256; // [rsp+3CAh] [rbp-373Eh]
  int v257; // [rsp+3E8h] [rbp-3720h]
  __int64 v258; // [rsp+3F0h] [rbp-3718h]
  int v259; // [rsp+3F8h] [rbp-3710h]
  int v260; // [rsp+3FCh] [rbp-370Ch]
  __int16 v261; // [rsp+400h] [rbp-3708h]
  int v262; // [rsp+408h] [rbp-3700h]
  int v263; // [rsp+40Ch] [rbp-36FCh]
  __int16 v264; // [rsp+410h] [rbp-36F8h]
  int v265; // [rsp+450h] [rbp-36B8h]
  int v266; // [rsp+454h] [rbp-36B4h]
  __int16 v267; // [rsp+458h] [rbp-36B0h]
  DWORD flOldProtect; // [rsp+460h] [rbp-36A8h] BYREF
  int v269; // [rsp+468h] [rbp-36A0h]
  int v270; // [rsp+470h] [rbp-3698h]
  int v271; // [rsp+474h] [rbp-3694h]
  int HkTempDbSavePoint; // [rsp+478h] [rbp-3690h]
  DWORD v273; // [rsp+47Ch] [rbp-368Ch] BYREF
  int v274; // [rsp+480h] [rbp-3688h]
  int v275; // [rsp+488h] [rbp-3680h]
  int v276; // [rsp+490h] [rbp-3678h]
  int v277; // [rsp+494h] [rbp-3674h]
  int v278; // [rsp+498h] [rbp-3670h]
  int v279; // [rsp+4A0h] [rbp-3668h]
  unsigned int v280[2]; // [rsp+4A4h] [rbp-3664h] BYREF
  unsigned int v281; // [rsp+4ACh] [rbp-365Ch] BYREF
  unsigned int v282[10]; // [rsp+4B0h] [rbp-3658h] BYREF
  int v283; // [rsp+4D8h] [rbp-3630h]
  int v284; // [rsp+4E0h] [rbp-3628h]
  volatile signed __int32 v285; // [rsp+4E8h] [rbp-3620h]
  int v286; // [rsp+4F0h] [rbp-3618h]
  LARGE_INTEGER PerformanceCount; // [rsp+500h] [rbp-3608h] BYREF
  LARGE_INTEGER v290; // [rsp+510h] [rbp-35F8h] BYREF
  int v291; // [rsp+518h] [rbp-35F0h]
  int v292; // [rsp+51Ch] [rbp-35ECh]
  struct IndexErrorTable::IetEntry *v293; // [rsp+520h] [rbp-35E8h]
  struct AllocUnitId *v294; // [rsp+528h] [rbp-35E0h]
  DatasetSession *v295; // [rsp+530h] [rbp-35D8h]
  XdesRMReadWrite *v296; // [rsp+538h] [rbp-35D0h]
  char *v297; // [rsp+540h] [rbp-35C8h] BYREF
  _QWORD v298[2]; // [rsp+548h] [rbp-35C0h] BYREF
  __int64 v299; // [rsp+558h] [rbp-35B0h]
  __int64 v300; // [rsp+560h] [rbp-35A8h]
  const wchar_t *v301; // [rsp+568h] [rbp-35A0h]
  struct Worker *v302; // [rsp+570h] [rbp-3598h]
  __int64 v303; // [rsp+578h] [rbp-3590h]
  struct Worker *v304; // [rsp+5A0h] [rbp-3568h]
  struct Worker *v305; // [rsp+5A8h] [rbp-3560h]
  struct Worker *v306; // [rsp+5B0h] [rbp-3558h]
  LARGE_INTEGER v307; // [rsp+5B8h] [rbp-3550h] BYREF
  __int64 v308; // [rsp+5C0h] [rbp-3548h]
  DatasetSession *v309; // [rsp+5C8h] [rbp-3540h]
  struct Worker *v310; // [rsp+5D8h] [rbp-3530h]
  int v311; // [rsp+5F4h] [rbp-3514h]
  int v312; // [rsp+5F8h] [rbp-3510h]
  int v313; // [rsp+5FCh] [rbp-350Ch]
  int v314; // [rsp+600h] [rbp-3508h]
  int v315; // [rsp+604h] [rbp-3504h]
  int v316; // [rsp+608h] [rbp-3500h]
  BOOL v317; // [rsp+610h] [rbp-34F8h]
  int v318; // [rsp+618h] [rbp-34F0h]
  int v319; // [rsp+620h] [rbp-34E8h]
  volatile signed __int32 v320; // [rsp+628h] [rbp-34E0h]
  int v321; // [rsp+630h] [rbp-34D8h]
  _QWORD *v322; // [rsp+638h] [rbp-34D0h]
  __int128 v323; // [rsp+640h] [rbp-34C8h]
  DirtyPageMgr **v324; // [rsp+688h] [rbp-3480h]
  unsigned __int64 *v325; // [rsp+690h] [rbp-3478h]
  union _LARGE_INTEGER v326; // [rsp+698h] [rbp-3470h]
  union _LARGE_INTEGER v327; // [rsp+6A0h] [rbp-3468h]
  __int64 v328; // [rsp+6A8h] [rbp-3460h]
  unsigned __int64 *v329; // [rsp+6B0h] [rbp-3458h]
  unsigned __int64 v330; // [rsp+6B8h] [rbp-3450h]
  unsigned __int64 v331; // [rsp+6C0h] [rbp-3448h]
  __int64 v332; // [rsp+6C8h] [rbp-3440h]
  const struct LogScanStats *v333; // [rsp+6D0h] [rbp-3438h]
  __int64 v334; // [rsp+6D8h] [rbp-3430h]
  DirtyPageMgr **p_QuadPart; // [rsp+6E0h] [rbp-3428h]
  DirtyPageMgr *v336; // [rsp+6E8h] [rbp-3420h]
  __int64 v337; // [rsp+6F0h] [rbp-3418h]
  __int64 v338; // [rsp+6F8h] [rbp-3410h]
  ProgressReport *v339; // [rsp+700h] [rbp-3408h]
  _WORD *v340; // [rsp+708h] [rbp-3400h]
  int **v341; // [rsp+710h] [rbp-33F8h]
  int (*v342)(int, int, int, int, char *); // [rsp+718h] [rbp-33F0h]
  __int64 v343; // [rsp+720h] [rbp-33E8h]
  __int64 v344; // [rsp+728h] [rbp-33E0h]
  __int64 v345; // [rsp+730h] [rbp-33D8h]
  __int64 v346; // [rsp+738h] [rbp-33D0h]
  __int64 v347; // [rsp+740h] [rbp-33C8h]
  __int64 v348; // [rsp+748h] [rbp-33C0h]
  __int64 v349; // [rsp+750h] [rbp-33B8h]
  __int64 v350; // [rsp+758h] [rbp-33B0h]
  __int64 v351; // [rsp+760h] [rbp-33A8h]
  __int64 v352; // [rsp+768h] [rbp-33A0h]
  __int64 v353; // [rsp+770h] [rbp-3398h]
  __int64 v354; // [rsp+778h] [rbp-3390h]
  struct FGCB *FgOrThrow; // [rsp+780h] [rbp-3388h]
  __int64 v356; // [rsp+788h] [rbp-3380h]
  __int64 v357; // [rsp+790h] [rbp-3378h]
  __int64 v358; // [rsp+798h] [rbp-3370h]
  __int64 *v359; // [rsp+7A0h] [rbp-3368h]
  __int64 v360; // [rsp+7A8h] [rbp-3360h]
  const unsigned __int8 *Data; // [rsp+7B0h] [rbp-3358h]
  __int64 v362; // [rsp+7B8h] [rbp-3350h]
  __int64 v363; // [rsp+7C0h] [rbp-3348h]
  _QWORD **v364; // [rsp+7C8h] [rbp-3340h]
  _QWORD *v365; // [rsp+7D0h] [rbp-3338h]
  _QWORD *v366; // [rsp+7D8h] [rbp-3330h]
  __int64 v367; // [rsp+7E0h] [rbp-3328h]
  __int64 System; // [rsp+7E8h] [rbp-3320h]
  int *v369; // [rsp+7F0h] [rbp-3318h]
  int *v370; // [rsp+7F8h] [rbp-3310h]
  _BYTE *v371; // [rsp+800h] [rbp-3308h]
  _BYTE *v372; // [rsp+808h] [rbp-3300h]
  _BYTE *v373; // [rsp+810h] [rbp-32F8h]
  _BYTE *v374; // [rsp+818h] [rbp-32F0h]
  __int64 v375; // [rsp+820h] [rbp-32E8h]
  DatasetSession *v376; // [rsp+828h] [rbp-32E0h]
  __int64 v377; // [rsp+830h] [rbp-32D8h]
  int *v378; // [rsp+838h] [rbp-32D0h]
  int *v379; // [rsp+840h] [rbp-32C8h]
  int *v380; // [rsp+848h] [rbp-32C0h]
  __int64 v381; // [rsp+850h] [rbp-32B8h]
  int *v382; // [rsp+858h] [rbp-32B0h]
  int *v383; // [rsp+860h] [rbp-32A8h]
  int *v384; // [rsp+868h] [rbp-32A0h]
  __int64 v385; // [rsp+870h] [rbp-3298h]
  __int64 v386; // [rsp+878h] [rbp-3290h]
  __int64 v387; // [rsp+880h] [rbp-3288h]
  __int64 v388; // [rsp+888h] [rbp-3280h]
  __int64 v389; // [rsp+890h] [rbp-3278h]
  __int64 v390; // [rsp+898h] [rbp-3270h]
  __int64 v391; // [rsp+8A0h] [rbp-3268h]
  __int64 v392; // [rsp+8A8h] [rbp-3260h]
  int *v393; // [rsp+8B0h] [rbp-3258h]
  _WORD *v394; // [rsp+8B8h] [rbp-3250h]
  _QWORD *v395; // [rsp+8C0h] [rbp-3248h]
  _QWORD *v396; // [rsp+8C8h] [rbp-3240h]
  _QWORD *v397; // [rsp+8D0h] [rbp-3238h]
  __int64 v398; // [rsp+8D8h] [rbp-3230h]
  __int64 v399; // [rsp+8E0h] [rbp-3228h]
  struct CSessionTraceFlags *v400; // [rsp+8E8h] [rbp-3220h]
  int *v401; // [rsp+8F0h] [rbp-3218h]
  __int64 *v402; // [rsp+8F8h] [rbp-3210h]
  __int64 v403; // [rsp+900h] [rbp-3208h]
  int *v404; // [rsp+908h] [rbp-3200h]
  __int64 v405; // [rsp+910h] [rbp-31F8h]
  __int64 v406; // [rsp+918h] [rbp-31F0h]
  void *v408; // [rsp+928h] [rbp-31E0h]
  struct IFileSystemHandler *v409; // [rsp+930h] [rbp-31D8h]
  _QWORD *v410; // [rsp+938h] [rbp-31D0h]
  _QWORD *v411; // [rsp+940h] [rbp-31C8h]
  _QWORD *v412; // [rsp+948h] [rbp-31C0h]
  __int64 v413; // [rsp+950h] [rbp-31B8h]
  __int64 v414; // [rsp+958h] [rbp-31B0h]
  struct CSessionTraceFlags *v415; // [rsp+960h] [rbp-31A8h]
  __int64 v416; // [rsp+968h] [rbp-31A0h]
  __int64 v417; // [rsp+970h] [rbp-3198h]
  const unsigned __int8 *v418; // [rsp+978h] [rbp-3190h]
  __int128 *v419; // [rsp+980h] [rbp-3188h]
  __int64 v420; // [rsp+988h] [rbp-3180h]
  _QWORD *v421; // [rsp+990h] [rbp-3178h]
  __int64 v422; // [rsp+998h] [rbp-3170h]
  struct Worker *v423; // [rsp+9A0h] [rbp-3168h]
  void *v424; // [rsp+9A8h] [rbp-3160h]
  void *v425; // [rsp+9B0h] [rbp-3158h]
  _QWORD *v426; // [rsp+A20h] [rbp-30E8h]
  __int64 v427; // [rsp+A28h] [rbp-30E0h]
  _QWORD *v428; // [rsp+A30h] [rbp-30D8h]
  __int64 v429; // [rsp+A38h] [rbp-30D0h]
  _QWORD *v430; // [rsp+A40h] [rbp-30C8h]
  unsigned __int64 v431; // [rsp+A48h] [rbp-30C0h]
  __int64 v432; // [rsp+A50h] [rbp-30B8h]
  __int64 v433; // [rsp+A58h] [rbp-30B0h]
  __int64 v434; // [rsp+A60h] [rbp-30A8h]
  __int64 v435; // [rsp+A68h] [rbp-30A0h]
  __int64 v436; // [rsp+A70h] [rbp-3098h]
  __int64 v437; // [rsp+A78h] [rbp-3090h]
  __int64 v438; // [rsp+A80h] [rbp-3088h]
  __int64 v439; // [rsp+A88h] [rbp-3080h]
  DatasetSession *v440; // [rsp+A90h] [rbp-3078h]
  __int64 v441; // [rsp+AC8h] [rbp-3040h]
  char *ThreadLocalStoragePointer; // [rsp+AD0h] [rbp-3038h]
  __int64 v443; // [rsp+AD8h] [rbp-3030h]
  __int64 v444; // [rsp+AE0h] [rbp-3028h]
  __int64 v445; // [rsp+AE8h] [rbp-3020h]
  char *v446; // [rsp+AF0h] [rbp-3018h]
  __int64 v447; // [rsp+AF8h] [rbp-3010h]
  __int64 v448; // [rsp+B00h] [rbp-3008h]
  __int64 v449; // [rsp+B08h] [rbp-3000h]
  char *v450; // [rsp+B10h] [rbp-2FF8h]
  DirtyPageMgr **v451; // [rsp+B18h] [rbp-2FF0h]
  __int128 v452; // [rsp+B20h] [rbp-2FE8h] BYREF
  _QWORD v453[18]; // [rsp+B30h] [rbp-2FD8h] BYREF
  __int128 v454; // [rsp+BC0h] [rbp-2F48h]
  _BYTE v455[24]; // [rsp+BD0h] [rbp-2F38h] BYREF
  _BYTE v456[40]; // [rsp+BE8h] [rbp-2F20h] BYREF
  _BYTE v457[40]; // [rsp+C10h] [rbp-2EF8h] BYREF
  _BYTE v458[40]; // [rsp+C38h] [rbp-2ED0h] BYREF
  char v459[8]; // [rsp+C60h] [rbp-2EA8h] BYREF
  _WORD v460[4]; // [rsp+C68h] [rbp-2EA0h] BYREF
  int v461; // [rsp+C70h] [rbp-2E98h]
  int **v462; // [rsp+C78h] [rbp-2E90h]
  char *v463; // [rsp+C80h] [rbp-2E88h]
  __int64 v464; // [rsp+C88h] [rbp-2E80h]
  int *v465; // [rsp+C90h] [rbp-2E78h] BYREF
  int v466; // [rsp+C98h] [rbp-2E70h]
  __int16 v467; // [rsp+C9Ch] [rbp-2E6Ch]
  __int16 v468; // [rsp+C9Eh] [rbp-2E6Ah]
  char v469; // [rsp+CA0h] [rbp-2E68h] BYREF
  int v470; // [rsp+EB0h] [rbp-2C58h]
  int v471; // [rsp+EB4h] [rbp-2C54h]
  __int64 v472; // [rsp+EB8h] [rbp-2C50h]
  int v473; // [rsp+EC0h] [rbp-2C48h] BYREF
  __int16 v474; // [rsp+EC4h] [rbp-2C44h]
  unsigned int v475; // [rsp+EC6h] [rbp-2C42h]
  int v476; // [rsp+ECAh] [rbp-2C3Eh]
  bool v477; // [rsp+ECEh] [rbp-2C3Ah]
  char v478[2]; // [rsp+ED0h] [rbp-2C38h] BYREF
  __int16 v479; // [rsp+ED2h] [rbp-2C36h]
  int v480; // [rsp+EE0h] [rbp-2C28h]
  int v481; // [rsp+EF0h] [rbp-2C18h]
  int v482; // [rsp+F00h] [rbp-2C08h]
  int v483; // [rsp+F10h] [rbp-2BF8h]
  int v484; // [rsp+F20h] [rbp-2BE8h]
  int v485; // [rsp+F30h] [rbp-2BD8h]
  int v486; // [rsp+F40h] [rbp-2BC8h]
  int v487; // [rsp+F50h] [rbp-2BB8h]
  int v488; // [rsp+F54h] [rbp-2BB4h]
  void *v489; // [rsp+F58h] [rbp-2BB0h]
  int v490; // [rsp+F60h] [rbp-2BA8h]
  void *v491; // [rsp+F68h] [rbp-2BA0h]
  int v492; // [rsp+F70h] [rbp-2B98h]
  char v493; // [rsp+F74h] [rbp-2B94h]
  __int128 v494; // [rsp+F75h] [rbp-2B93h] BYREF
  const unsigned __int8 *v495; // [rsp+F88h] [rbp-2B80h]
  unsigned int v496; // [rsp+F90h] [rbp-2B78h]
  __int64 v497; // [rsp+FA0h] [rbp-2B68h] BYREF
  __int16 v498; // [rsp+FA8h] [rbp-2B60h]
  char v499; // [rsp+FB0h] [rbp-2B58h] BYREF
  __int16 v500; // [rsp+FB2h] [rbp-2B56h]
  __int16 v501; // [rsp+FBEh] [rbp-2B4Ah]
  int v502; // [rsp+FC0h] [rbp-2B48h] BYREF
  __int16 v503; // [rsp+FC4h] [rbp-2B44h]
  char v504; // [rsp+FC6h] [rbp-2B42h]
  char v505; // [rsp+FC7h] [rbp-2B41h]
  int v506; // [rsp+FC8h] [rbp-2B40h] BYREF
  __int16 v507; // [rsp+FCCh] [rbp-2B3Ch]
  __int16 v508; // [rsp+FCEh] [rbp-2B3Ah]
  __int16 v509; // [rsp+FD0h] [rbp-2B38h]
  __int16 v510; // [rsp+FD2h] [rbp-2B36h]
  char v511; // [rsp+FD8h] [rbp-2B30h] BYREF
  __int16 v512; // [rsp+FDAh] [rbp-2B2Eh]
  __int16 v513; // [rsp+FE6h] [rbp-2B22h]
  int v514; // [rsp+FE8h] [rbp-2B20h] BYREF
  __int16 v515; // [rsp+FECh] [rbp-2B1Ch]
  char v516; // [rsp+FEEh] [rbp-2B1Ah]
  char v517; // [rsp+FEFh] [rbp-2B19h]
  int v518; // [rsp+FF0h] [rbp-2B18h] BYREF
  __int16 v519; // [rsp+FF4h] [rbp-2B14h]
  __int16 v520; // [rsp+FF6h] [rbp-2B12h]
  __int16 v521; // [rsp+FF8h] [rbp-2B10h]
  __int16 v522; // [rsp+FFAh] [rbp-2B0Eh]
  char v523[16]; // [rsp+1000h] [rbp-2B08h] BYREF
  int v524; // [rsp+1010h] [rbp-2AF8h] BYREF
  __int16 v525; // [rsp+1014h] [rbp-2AF4h]
  __int64 v526; // [rsp+1018h] [rbp-2AF0h] BYREF
  __int16 v527; // [rsp+1020h] [rbp-2AE8h]
  int v528; // [rsp+1022h] [rbp-2AE6h] BYREF
  __int16 v529; // [rsp+1026h] [rbp-2AE2h]
  int v530; // [rsp+1028h] [rbp-2AE0h]
  int v531; // [rsp+102Ch] [rbp-2ADCh]
  _BYTE v532[16]; // [rsp+1030h] [rbp-2AD8h] BYREF
  char v533; // [rsp+1040h] [rbp-2AC8h] BYREF
  __int16 v534; // [rsp+1042h] [rbp-2AC6h]
  __int64 v535; // [rsp+1044h] [rbp-2AC4h]
  __int16 v536; // [rsp+104Ch] [rbp-2ABCh]
  __int16 v537; // [rsp+104Eh] [rbp-2ABAh]
  int v538; // [rsp+1050h] [rbp-2AB8h] BYREF
  __int16 v539; // [rsp+1054h] [rbp-2AB4h]
  char v540; // [rsp+1056h] [rbp-2AB2h]
  char v541; // [rsp+1057h] [rbp-2AB1h]
  int v542; // [rsp+1058h] [rbp-2AB0h]
  unsigned __int8 v543; // [rsp+105Ch] [rbp-2AACh]
  _WORD v544[72]; // [rsp+1060h] [rbp-2AA8h] BYREF
  char v545[16]; // [rsp+10F0h] [rbp-2A18h] BYREF
  char v546[16]; // [rsp+1100h] [rbp-2A08h] BYREF
  char v547[16]; // [rsp+1110h] [rbp-29F8h] BYREF
  char v548[16]; // [rsp+1120h] [rbp-29E8h] BYREF
  char v549[16]; // [rsp+1130h] [rbp-29D8h] BYREF
  char v550[32]; // [rsp+1140h] [rbp-29C8h] BYREF
  char v551[16]; // [rsp+1160h] [rbp-29A8h] BYREF
  char v552[16]; // [rsp+1170h] [rbp-2998h] BYREF
  char v553[16]; // [rsp+1180h] [rbp-2988h] BYREF
  char v554[16]; // [rsp+1190h] [rbp-2978h] BYREF
  char v555[16]; // [rsp+11A0h] [rbp-2968h] BYREF
  char v556[16]; // [rsp+11B0h] [rbp-2958h] BYREF
  char v557[16]; // [rsp+11C0h] [rbp-2948h] BYREF
  char v558[4096]; // [rsp+11D0h] [rbp-2938h] BYREF
  _BYTE v559[6000]; // [rsp+21D0h] [rbp-1938h] BYREF
  _DWORD v560[4]; // [rsp+3940h] [rbp-1C8h] BYREF
  _QWORD v561[3]; // [rsp+3950h] [rbp-1B8h] BYREF
  _BYTE v562[4]; // [rsp+3968h] [rbp-1A0h] BYREF
  _BYTE Destination[20]; // [rsp+396Ch] [rbp-19Ch] BYREF
  _OWORD v564[2]; // [rsp+3980h] [rbp-188h] BYREF
  __int64 v565; // [rsp+39A0h] [rbp-168h]
  int v566; // [rsp+39A8h] [rbp-160h]
  __int16 v567; // [rsp+39ACh] [rbp-15Ch]
  wchar_t v568[128]; // [rsp+39B0h] [rbp-158h] BYREF

  v441 = -2;
  v178 = a4;
  v7 = a3;
  v154 = a3;
  Source = a2;
  v155 = this;
  v168 = this;
  v296 = this;
  v238 = a2;
  v225 = a3;
  v226 = a4;
  v294 = a5;
  v257 = 0;
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  v258 = v10;
  v11 = *(_DWORD *)(v10 + 616);
  v12 = v11 & 0x27 ^ 0x27;
  v257 = v12;
  *(_DWORD *)(v10 + 616) = v11 | 0x27;
  v156 = 0;
  v13 = *((_QWORD *)this + 6);
  v228[0] = &TxLogDataReadAhead::`vftable';
  v228[1] = v13;
  v229 = NullPageId;
  v230 = word_1031997E8;
  v231 = 0;
  if ( !v13 )
    utassert_fail(1u, "recoveryUnit != NULL", "recovery.cpp", 24838, 0);
  v228[0] = &UndoLogDataReadAhead::`vftable';
  v188 = 1;
  v160 = 0;
  v161 = 0;
  v162 = 0;
  v158 = 0;
  *((_BYTE *)this + 8884) = 0;
  v14 = (_DWORD *)((char *)this + 8640);
  if ( !*((_WORD *)this + 4324) && !*v14 && !*((_DWORD *)this + 2161) )
  {
    PageRef::~PageRef((PageRef *)&v160);
    v228[0] = &IDbCopyRestoreCallback::`vftable';
    *(_DWORD *)(v10 + 616) &= ~v12;
    return;
  }
  v15 = v155;
  *((_DWORD *)v155 + 182) &= ~4u;
  *((_DWORD *)v155 + 182) |= 2u;
  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset
                        + 8LL)
            + 40LL) = -1;
  if ( (*(unsigned int (__fastcall **)(XDES *))(*(_QWORD *)v15 + 632LL))(v15) )
  {
    v66 = (RecoveryUnit *)*((_QWORD *)v155 + 6);
    if ( (unsigned int)RecoveryUnit::IsRecoveryThread(v66)
      && (v67 = (_DWORD *)*((_QWORD *)v66 + 229)) != 0
      && v67[8] != 2 )
    {
      v68 = 0;
      v69 = *(_QWORD *)(*(_QWORD *)v67 + 26096LL);
      if ( v69 )
        v68 = *(_QWORD *)(v69 + 264);
      v15 = v155;
      if ( v68 != *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                        + SystemThread_TlsOffset
                                        + 8LL)
                            + 96LL) )
      {
        v16 = (*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v155 + 136LL))(v155) != 0;
        v156 = v16;
        goto LABEL_12;
      }
    }
    else
    {
      v15 = v155;
    }
  }
  v16 = 0;
LABEL_12:
  v193 = v16;
  ThreadLocalStoragePointer = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v17 = 8LL * SystemThread_TlsIndex;
  v443 = SystemThread_TlsOffset + *(_QWORD *)&ThreadLocalStoragePointer[v17];
  v444 = *(_QWORD *)(v443 + 8);
  v445 = *(_QWORD *)(v444 + 96);
  v157 = *(_BYTE *)(v445 + 1185);
  v446 = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v447 = SystemThread_TlsOffset + *(_QWORD *)&v446[v17];
  v448 = *(_QWORD *)(v447 + 8);
  v449 = *(_QWORD *)(v448 + 96);
  *(_BYTE *)(v449 + 1185) = 2;
  v310 = 0;
  ExcHandler::ExcHandler((ExcHandler *)v458, 0, 0, 0, (int (*)(int, int, int, int, char *))XdesExceptionHandler, 0);
  v18 = *((_WORD *)v15 + 4353);
  if ( v18 != -1 )
    *((_WORD *)v15 + 4353) = v18 + 1;
  v259 = -1;
  v260 = -1;
  v261 = -1;
  v450 = (char *)this + 8640;
  if ( *((_WORD *)this + 4324) == 0xFFFF && *v14 == -1 && *((_DWORD *)this + 2161) == -1 )
  {
    v20 = *(_QWORD *)((char *)v15 + 8732);
    v21 = *((_WORD *)v15 + 4370);
  }
  else
  {
    v20 = *(_QWORD *)v14;
    v21 = *((_WORD *)this + 4324);
  }
  v498 = v21;
  v497 = v20;
  (*(void (__fastcall **)(struct LogIter *, __int64 *, _QWORD *, _QWORD, _DWORD, _DWORD, _BYTE, _QWORD))(*(_QWORD *)v7 + 48LL))(
    v7,
    &v497,
    v228,
    0,
    0,
    0,
    0,
    0);
  v179 = 0;
  v451 = &QuadPart;
  v311 = Base_PublicGlobals::sm_invariantTscAvailable;
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&PerformanceCount);
    QuadPart = (DirtyPageMgr *)PerformanceCount.QuadPart;
  }
  else
  {
    v453[10] = MEMORY[0x7FFE0008];
    QuadPart = MEMORY[0x7FFE0008];
  }
  while ( 1 )
  {
    v22 = (*(__int64 (__fastcall **)(struct LogIter *))(*(_QWORD *)v7 + 40LL))(v7);
    v159 = v22;
    if ( !v22 )
      break;
    v23 = (_DWORD *)(*(__int64 (__fastcall **)(struct LogIter *, char *))(*(_QWORD *)v7 + 24LL))(v7, v551);
    v24 = v23;
    v453[11] = v23;
    v25 = (const struct LSN *)Source;
    v27 = 1;
    if ( *v23 >= *(_DWORD *)Source )
    {
      if ( *v23 != *(_DWORD *)Source
        || (v26 = v23[1], v26 >= *((_DWORD *)Source + 1))
        && (v26 != *((_DWORD *)Source + 1) || *((_WORD *)v24 + 4) >= *((_WORD *)Source + 4)) )
      {
        v27 = 0;
      }
    }
    if ( v27 || v179 )
      goto LABEL_112;
    v28 = *(_QWORD *)(*((_QWORD *)v15 + 6) + 1736LL);
    if ( v28 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v28 + 776LL))(v28) == 7 )
    {
      v70 = *(_QWORD *)(*((_QWORD *)v15 + 6) + 1712LL);
      LODWORD(v150) = *(_DWORD *)(v70 + 928);
      ex_raise(90, 1, 21, 33, v150, v70 + 936);
    }
    v29 = (const struct LSN *)(*(__int64 (__fastcall **)(struct LogIter *, char *))(*(_QWORD *)v7 + 24LL))(v7, v552);
    XdesRMReadWrite::UndoVirtualLogRecsToLSN(v15, v29);
    v30 = (_DWORD *)((char *)v15 + 40);
    v453[12] = (char *)v15 + 40;
    v31 = (unsigned int *)(v22 + 16);
    v453[13] = v22 + 16;
    if ( *(_WORD *)(v22 + 20) != *((_WORD *)v15 + 22) || *v31 != *v30 )
      utassert_fail(1u, "curr->GetXdesId () == m_xdesId", "xdes.cpp", 7203, 0);
    v33 = v156;
    if ( v156 )
    {
      v71 = (const struct LogScanStats *)(*(__int64 (__fastcall **)(struct LogIter *))(*(_QWORD *)v154 + 56LL))(v154);
      RecoveryMgr::UpdateRecoveryStatus(*(RecoveryMgr **)(*((_QWORD *)v15 + 6) + 1832LL), 1u, v71);
      v33 = v156;
    }
    v453[14] = &v217;
    v312 = Base_PublicGlobals::sm_invariantTscAvailable;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v307);
      v34 = (DirtyPageMgr *)v307.QuadPart;
      v217 = (DirtyPageMgr *)v307.QuadPart;
    }
    else
    {
      v34 = MEMORY[0x7FFE0008];
      v453[15] = MEMORY[0x7FFE0008];
      v217 = MEMORY[0x7FFE0008];
    }
    v453[16] = &QuadPart;
    v324 = &v217;
    if ( v34 < QuadPart )
    {
      v35 = 0;
      v187 = 0;
    }
    else
    {
      v35 = v34 - QuadPart;
      v187 = v35;
    }
    v239 = v35;
    v325 = &v239;
    if ( v35 == -1 )
    {
      v36 = -1;
      v241 = -1;
    }
    else
    {
      v313 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v326 = Base_PublicGlobals::sm_QueryPerformanceFrequency;
        v327 = Base_PublicGlobals::sm_QueryPerformanceFrequency;
        v328 = 1;
        v36 = v35 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
        v241 = v35 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
      }
      else
      {
        v329 = &v239;
        v314 = -7;
        v315 = 10000000;
        v36 = v35 / 0x989680;
        v330 = v35 / 0x989680;
        v241 = v35 / 0x989680;
      }
    }
    v331 = v36;
    if ( v36 > 0x3C )
    {
      if ( v33 )
      {
        v72 = 1;
        if ( !byte_10316E73B )
        {
          v169 = qword_10317AD29;
          if ( (qword_10317AD29 & 1) == 0 )
            v72 = 0;
        }
        if ( v72 && RecoveryUnit::IsTraceEnabled() )
        {
          v332 = *((_QWORD *)v15 + 21);
          v73 = v332;
          wcscpy(v568, L" ");
          memset_0(&v568[2], 0, 0xFCu);
          if ( v73 )
          {
            (*(void (__fastcall **)(__int64, wchar_t *, __int64))(*(_QWORD *)v73 + 16LL))(v73, v568, 128);
            v74 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v73 + 8LL))(v73);
            RecoveryUnit::PrintTrace(
              *((RecoveryUnit **)v15 + 6),
              L"Undo Status, current transaction: %.*ls (XactId: %I64d)",
              128,
              v568,
              v74);
          }
          v333 = (const struct LogScanStats *)(*(__int64 (__fastcall **)(struct LogIter *))(*(_QWORD *)v154 + 56LL))(v154);
          v334 = *(_QWORD *)(*((_QWORD *)v15 + 6) + 1832LL);
          RecoveryStatus::OutputUndoStats((RecoveryStatus *)(v334 + 22968), v333);
        }
      }
      p_QuadPart = &QuadPart;
      v316 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v290);
        QuadPart = (DirtyPageMgr *)v290.QuadPart;
      }
      else
      {
        v336 = MEMORY[0x7FFE0008];
        QuadPart = MEMORY[0x7FFE0008];
      }
    }
    v37 = *((_QWORD *)v15 + 1142);
    if ( v37 )
    {
      v337 = v37;
      ++*(_QWORD *)(v37 + 8);
      if ( *(_QWORD *)(v37 + 32) )
      {
        v38 = ++*(_DWORD *)(v37 + 40);
        if ( v38 >= 0x3E8 )
        {
          v75 = v38;
          v338 = *(unsigned int *)(v37 + 40);
          v76 = *(ProgressReport **)(v37 + 32);
          v339 = v76;
          ProgressReport::GetAccess(v76);
          v77 = v75 + *((_QWORD *)v76 + 4);
          if ( v77 >= *((_QWORD *)v76 + 3) )
            v77 = *((_QWORD *)v76 + 3);
          *((_QWORD *)v76 + 4) = v77;
          ProgressReport::ReleaseAccess(v76);
          *(_DWORD *)(v37 + 40) = 0;
        }
      }
    }
    v291 = 33;
    v292 = 0x1000000;
    if ( (qword_10317F744 & 0x1000000) != 0 )
    {
      v206 = 1;
      v340 = v460;
      v460[0] = 0;
      v460[1] = 1;
      v461 = 0;
      v462 = &v465;
      v463 = &v469;
      v470 = 0;
      v471 = 0;
      v464 = 0;
      v472 = 0;
      v341 = &v465;
      v465 = &v473;
      v466 = 15;
      v467 = 0;
      v468 = 0;
      v15 = v155;
      v473 = *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)v155 + 6) + 1712LL) + 40LL);
      v474 = *(_WORD *)(v22 + 20);
      v475 = *v31;
      v476 = *(unsigned __int8 *)(v22 + 22);
      v78 = (*(__int64 (__fastcall **)(XDES *))(*(_QWORD *)v155 + 136LL))(v155);
      v317 = v78 == 0;
      v477 = v78 == 0;
      XeSqlPkg::log_record_undo::Publish((XeSqlPkg::log_record_undo *)v459);
    }
    else
    {
      v15 = v155;
    }
    *((_QWORD *)v15 + 1087) = *(_QWORD *)(v22 + 4);
    *((_WORD *)v15 + 4352) = *(_WORD *)(v22 + 12);
    v39 = hdl_rethrow;
    if ( v178 )
      v39 = (int (*)(int, int, int, int, char *))HandleAndNoteToErrorlog;
    v342 = v39;
    v304 = 0;
    ExcHandler::ExcHandler((ExcHandler *)v457, 0, 0, 0, v39, 0);
    if ( v158 )
    {
      if ( *(_BYTE *)(v22 + 22) < 0x7Fu )
      {
        v343 = v22 + 24;
        LODWORD(v187) = *(_DWORD *)(v22 + 24);
        v80 = *(_WORD *)(v22 + 28);
        WORD2(v187) = v80;
        v79 = v160;
        v344 = v160 + 112;
        v81 = *(_DWORD *)(v160 + 112) != (_DWORD)v187 || *(_WORD *)(v160 + 116) != v80;
        if ( !v81 && *(__int16 *)(v22 + 30) == v207 )
          goto LABEL_56;
        v158 = 0;
      }
      else
      {
        v158 = 0;
        v79 = v160;
      }
      if ( !v79 )
        goto LABEL_56;
      v345 = v79 + 98;
      v199 = *(_WORD *)(v79 + 98);
      if ( (v199 & 0x400) != 0 && (__int16)v162 >= 3 )
      {
        PageRef::UnfixLatchOnly((PageRef *)&v160);
        goto LABEL_56;
      }
      v164 = (__int16)v162;
      v218 = v160;
      v346 = v79 + 98;
      v200 = *(_WORD *)(v79 + 98);
      if ( (v200 & 8) != 0 )
      {
        if ( v164 == 3 )
        {
          v164 = 4;
          goto LABEL_185;
        }
        if ( v164 >= 2 )
        {
LABEL_185:
          v347 = v160 + 100;
          v318 = *(_DWORD *)(v160 + 100);
          if ( (v318 & 8) != 0 )
          {
            v82 = *(_QWORD *)(v160 + 144);
            if ( v82 )
            {
              v348 = *(_QWORD *)(v160 + 144);
              if ( *(_QWORD *)(v82 + 1880) )
              {
                _mm_lfence();
                DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v82 + 1880), v160, (unsigned int)v164);
              }
            }
          }
        }
      }
      v170 = (unsigned __int8)byte_10317ABE5 >> 7;
      if ( byte_10317ABE5 < 0 )
      {
        v83 = (volatile signed __int32 *)(v218 + 100);
        v349 = v218 + 100;
        v319 = *(_DWORD *)(v218 + 100);
        if ( (v319 & 8) != 0 && v164 >= 3 )
        {
          v350 = v218 + 100;
          v320 = *v83;
          if ( (v320 & 0xC0000000) != 0x40000000 )
          {
            v84 = *(void **)v218;
            if ( *(_QWORD *)v218 )
            {
              v321 = 2;
              if ( VirtualProtect(v84, 0x2000u, 2u, &flOldProtect) )
              {
                _InterlockedAnd(v83, 0x3FFFFFFFu);
                _InterlockedOr(v83, 0x40000000u);
              }
            }
          }
        }
      }
      v85 = v218;
      v86 = v164;
      LatchBase::ReleaseInternal(v218 + 152, (unsigned int)v164);
      if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
      {
        v171 = (unsigned __int8)byte_10317AD4F >> 1;
        if ( (byte_10317AD4F & 2) != 0 )
          BUF::TraceLatchAcquireRelease(v85, 0, v86);
      }
      v162 &= 0xFFFF0000;
      v160 = 0;
      v15 = v155;
    }
LABEL_56:
    *((_BYTE *)v15 + 8884) = *(_BYTE *)(v22 + 22);
    v40 = *(unsigned __int8 *)(v22 + 22);
    if ( (unsigned __int8)v40 >= 0x7Fu )
    {
      v53 = v40 - 128;
      if ( v53 <= 0x72 )
      {
        switch ( *((_BYTE *)&loc_1005B3640 + (int)v53) )
        {
          case 0:
            v262 = 0;
            v263 = 0;
            v264 = 0;
            v356 = v22 + 4;
            if ( *(_WORD *)(v22 + 12) || *(_DWORD *)(v22 + 4) || *(_DWORD *)(v22 + 8) )
              utassert_fail(1u, "curr->GetPrevLsn () == NullLSN", "xdes.cpp", 7467, 0);
            if ( (*((_BYTE *)v15 + 536) & 2) != 0 && RecoveryUnit::IsTraceEnabled() )
            {
              v209[0] = 0;
              v357 = v22;
              v358 = v22 + 40;
              v359 = &v222;
              v270 = 1;
              if ( v22 == -40 )
              {
                v222 = 0;
                v271 = 0;
                *_errno() = 22;
                _invalid_parameter_noinfo();
              }
              else
              {
                v222 = *(_QWORD *)(v22 + 40);
              }
              memset(v564, 0, sizeof(v564));
              v565 = 0;
              v566 = 0;
              v567 = 0;
              if ( (unsigned int)SQLDATE::ConvertToWstr(&v222, v564, 22, v209, 21, 0, 2) )
              {
                v360 = 0;
                LOWORD(v564[0]) = 0;
              }
              v55 = (*(__int64 (__fastcall **)(struct LogIter *, char *))(*(_QWORD *)v154 + 24LL))(v154, v555);
              v165 = *(_QWORD *)v55;
              v166 = *(_WORD *)(v55 + 8);
              v56 = v166;
              Data = VarLogData::GetData((VarLogData *)(v22 + 76), 0, v208);
              LODWORD(v153) = v56;
              LODWORD(v152) = HIDWORD(v165);
              LODWORD(v151) = v165;
              RecoveryUnit::PrintTrace(
                *((RecoveryUnit **)v15 + 6),
                L"RollbackToLsn for system xact: XdesId 0x%x:0x%x; Tran start time: %ls; Begin Tran LSN 0x%x:0x%x:0x%x; Tran Name:%.*ls",
                *(unsigned __int16 *)(v22 + 20),
                *v31,
                v564,
                v151,
                v152,
                v153,
                (unsigned __int64)v208[0] >> 1,
                Data);
            }
            goto LABEL_110;
          case 1:
            v179 = 1;
            goto LABEL_110;
          case 2:
            goto LABEL_110;
          case 3:
            v7 = v154;
            v87 = (*(__int64 (__fastcall **)(struct LogIter *, char *))(*(_QWORD *)v154 + 24LL))(v154, v556);
            v362 = v87;
            v88 = Source;
            if ( *(_WORD *)(v87 + 8) != *((_WORD *)Source + 4)
              || *(_DWORD *)v87 != *(_DWORD *)Source
              || *(_DWORD *)(v87 + 4) != *((_DWORD *)Source + 1) )
            {
              goto LABEL_237;
            }
            if ( !(*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v15 + 136LL))(v15) )
            {
              v90 = *((_QWORD *)v15 + 1159);
              if ( v90 )
              {
                v363 = *((_QWORD *)v15 + 1159);
                v91 = 0;
                v227 = 0;
                for ( i = 0; i < *(_DWORD *)(v90 + 12); i = v91 )
                {
                  v93 = (_QWORD **)(*(_QWORD *)(v90 + 16) + 8LL * i);
                  v364 = v93;
                  while ( 1 )
                  {
                    v94 = *v93;
                    if ( !*v93 )
                      break;
                    v365 = *v93;
                    *v93 = (_QWORD *)*v94;
                    v366 = v94;
                    operator delete[](v94);
                  }
                  v227 = ++v91;
                }
                *(_DWORD *)(v90 + 24) = 0;
                v15 = v155;
              }
            }
            v95 = (RecoveryUnit *)*((_QWORD *)v15 + 6);
            if ( *((_WORD *)v95 + 860) == 2 )
            {
              v96 = *((_QWORD *)v15 + 84);
              v367 = v96;
              if ( v96 )
              {
                if ( RecoveryUnit::FHkTempdbActive(v95) )
                {
                  v234 = 0;
                  System = HkRtGetSystem();
                  if ( (int)HkScopeEnter(System, 1, 2, 0xFFFF, 0xFFFF, 0, &v234) < 0 )
                    utassert_fail(1u, "SUCCEEDED(hr)", "xdes.cpp", 7551, 0);
                  HkTempDbSavePoint = HkTransactionRollbackToLastHkTempDbSavePoint(v96);
                  if ( HkTempDbSavePoint < 0 )
                    utassert_fail(1u, "SUCCEEDED(hr)", "xdes.cpp", 7554, 0);
                  if ( v234 )
                    HkScopeExit();
                }
              }
            }
            if ( *((_DWORD *)v15 + 56) )
            {
              v369 = &v242;
              v242 = 0;
              v243 = 0;
              v244 = 0;
              v370 = &v245;
              v247 = 0;
              v248 = 0;
              v249 = 20;
              v250 = 0;
              v251 = v562;
              v253 = Destination;
              v255 = 0;
              v256 = 0;
              v252 = v562;
              v246 = 0;
              v245 = 0;
              v371 = v562;
              v562[2] = 0;
              v372 = v562;
              v562[0] = 4;
              v373 = v562;
              v562[1] = 7;
              v172 = 1;
              v254 = 1;
              v562[3] = 14;
              memcpy_s(Destination, 0xAu, v88, 0xAu);
              v250 = v253 + 10 - v251;
              v98 = v253 + 10;
              v252 = v253 + 10;
              v253 += 14;
              if ( v253 - v251 < v249 )
              {
                v374 = v98;
                *v98 = 0;
                v98[1] = 0;
                v98[2] = 0;
                v98[3] = 4;
              }
              XDES::LogLocks(v15, (const struct LogLockCollection *)&v242, 0, v97);
            }
            else
            {
LABEL_237:
              XDES::LogNoOpCLRForSavepoint(v15);
            }
            goto LABEL_70;
          case 4:
            if ( (*(_BYTE *)(v22 + 14) & 1) != 0 )
              goto LABEL_110;
            v375 = v22;
            v99 = (volatile signed __int32 *)*((_QWORD *)v15 + 1101);
            if ( v99 )
            {
              v295 = (DatasetSession *)*((_QWORD *)v15 + 1101);
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v99 + 408LL))(v99);
              if ( !_InterlockedDecrement(v99 + 150) )
              {
                v100 = v295;
                if ( *((_DWORD *)v295 + 2) )
                  DatasetSession::GoDormant(v295);
                v376 = v100;
                (**(void (__fastcall ***)(DatasetSession *, __int64))v100)(v100, 1);
              }
              *((_QWORD *)v15 + 1101) = 0;
            }
            v101 = (int *)(v22 + 24);
            v102 = *(HoBtFactory **)(*((_QWORD *)v296 + 6) + 1808LL);
            v103 = (const struct HoBtId *)(v22 + 24);
            if ( (*((_BYTE *)v15 + 728) & 1) != 0 )
            {
              HoBtFactory::MarkForRefresh(v102, v103, 1);
              HoBtFactory::TryToFreeHoBt(
                *(HoBtFactory **)(*((_QWORD *)v15 + 6) + 1808LL),
                (const struct HoBtId *)(v22 + 24),
                1);
              v274 = *(unsigned __int16 *)(v22 + 32);
              v377 = v22 + 24;
              v378 = &v514;
              v514 = 0;
              v515 = 0;
              v379 = &v518;
              v518 = 0;
              v519 = 0;
              v520 = 0;
              v516 = -119;
              v512 = 36;
              v517 = 0;
              v513 = 0;
              v380 = &v518;
              v518 = *v101;
              v519 = *(_WORD *)(v22 + 28);
              v521 = v274;
              v522 = 0;
              v223 = 36;
              v297 = &v511;
              if ( !(unsigned int)XDES::IsActive(v15) )
                (*(void (__fastcall **)(XDES *))(*(_QWORD *)v15 + 624LL))(v15);
              (*(void (__fastcall **)(XDES *, __int64, int *, char **, char *))(*(_QWORD *)v15 + 648LL))(
                v15,
                1,
                &v223,
                &v297,
                v557);
            }
            else
            {
              HoBtFactory::MarkForRefresh(v102, v103, 0);
              v275 = *(unsigned __int16 *)(v22 + 32);
              v381 = v22 + 24;
              v382 = &v502;
              v502 = 0;
              v503 = 0;
              v383 = &v506;
              v506 = 0;
              v507 = 0;
              v508 = 0;
              v504 = -119;
              v500 = 36;
              v505 = 0;
              v501 = 0;
              v384 = &v506;
              v506 = *v101;
              v507 = *(_WORD *)(v22 + 28);
              v509 = v275;
              v510 = 0;
              v216 = 36;
              v298[0] = &v499;
              if ( !(unsigned int)XDES::IsActive(v15) )
                (*(void (__fastcall **)(XDES *))(*(_QWORD *)v15 + 624LL))(v15);
              (*(void (__fastcall **)(XDES *, __int64, int *, _QWORD *, char *))(*(_QWORD *)v15 + 648LL))(
                v15,
                1,
                &v216,
                v298,
                v545);
            }
            v104 = (RecoveryUnit *)*((_QWORD *)v15 + 6);
            if ( *((_WORD *)v104 + 860) != 2 )
              goto LABEL_110;
            v105 = *((_QWORD *)v15 + 84);
            v385 = v105;
            if ( !v105 || !RecoveryUnit::FHkTempdbActive(v104) )
              goto LABEL_110;
            v235 = 0;
            v386 = HkRtGetSystem();
            if ( (int)HkScopeEnter(v386, 1, 2, 0xFFFF, 0xFFFF, 0, &v235) < 0 )
              utassert_fail(1u, "SUCCEEDED(hr)", "xdes.cpp", 7616, 0);
            v276 = HkTransactionRollbackToLastHkTempDbSavePoint(v105);
            if ( v276 < 0 )
              utassert_fail(1u, "SUCCEEDED(hr)", "xdes.cpp", 7619, 0);
            if ( v235 )
              HkScopeExit();
            v7 = v154;
            goto LABEL_70;
          case 5:
            v392 = v22;
            v107 = *(_BYTE *)(v22 + 28);
            v277 = v107;
            if ( (*(_BYTE *)(v22 + 14) & 1) == 0 )
            {
              v323 = (unsigned __int64)v15;
              SchemaScopeId = IdentityLogRecord::GetSchemaScopeId((IdentityLogRecord *)v22);
              v189 = SchemaScopeId;
              v278 = *(_DWORD *)(v22 + 24);
              v393 = &v538;
              v538 = 0;
              v539 = 0;
              v542 = v278;
              v543 = v107;
              v394 = v544;
              v544[0] = 0;
              v265 = 0;
              v266 = 0;
              v267 = 0;
              v535 = 0;
              v536 = 0;
              v540 = -117;
              v541 = 0;
              v537 = 0;
              v534 = 32;
              v109 = 1;
              v190 = 1;
              if ( !SchemaScopeId )
              {
                SchemaScopeId = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v15 + 6) + 1712LL) + 2888LL);
                v189 = SchemaScopeId;
              }
              v560[0] = 29;
              v561[0] = &v533;
              if ( SchemaScopeId != 1 )
              {
                v544[1] = 0;
                v560[1] = 0;
                v561[1] = 0;
                v279 = 4;
                v544[2] = 4;
                v544[0] = 2;
                v560[2] = 4;
                v561[2] = &v189;
                v109 = 3;
                v190 = 3;
                v298[1] = 38;
                v560[0] = 38;
                v537 = 16;
              }
              (*(void (__fastcall **)(XDES *, __int64, _DWORD *, _QWORD *, char *))(*(_QWORD *)v15 + 648LL))(
                v15,
                v109,
                v560,
                v561,
                v547);
            }
            goto LABEL_110;
          case 6:
            if ( (*(_BYTE *)(v22 + 14) & 1) == 0 )
            {
              v387 = v22;
              if ( (*((_BYTE *)v15 + 728) & 1) != 0 && (*((_BYTE *)v15 + 536) & 2) != 0 )
                CountRecoveryManager::RecoveryUndoHoBtCountDelta(
                  *(CountRecoveryManager **)(*((_QWORD *)v15 + 6) + 9192LL),
                  (const struct HoBtCountDelta *)(v22 + 24),
                  v15);
              else
                HoBtCountDelta::Undo((HoBtCountDelta *)(v22 + 24), v15);
            }
            goto LABEL_110;
          case 7:
            v7 = v154;
            v300 = (*(__int64 (__fastcall **)(struct LogIter *, char *))(*(_QWORD *)v154 + 24LL))(v154, v550);
            v299 = *((_QWORD *)v15 + 6);
            v173 = (unsigned __int8)qword_10317AE30 >> 5;
            if ( (qword_10317AE30 & 0x20) != 0 )
              goto LABEL_70;
            v191 = 0;
            v395 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v396 = (_QWORD *)(v395[SystemThread_TlsIndex] + SystemThread_TlsOffset);
            v397 = v396;
            v112 = *v396;
            v398 = v112;
            v399 = v112;
            if ( !v112 )
            {
              v236 = 0;
LABEL_289:
              v113 = v191;
              goto LABEL_290;
            }
            v116 = **(struct CSessionTraceFlags ***)(v112 + 56);
            v400 = v116;
            if ( !v116 )
            {
              v236 = 0;
              goto LABEL_289;
            }
            v236 = v116;
            v113 = CSessionTraceFlags::CheckSessionTraceInternal(v116, 0x1585u);
            v191 = v113;
LABEL_290:
            if ( v113 )
              goto LABEL_70;
            v114 = v299;
            if ( *(_QWORD *)(*(_QWORD *)(v299 + 1712) + 640LL) )
            {
              if ( *(_BYTE *)(v22 + 22) != 0x93
                || (v115 = v155, (*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v155 + 136LL))(v155)) )
              {
                v15 = v155;
                goto LABEL_70;
              }
            }
            else
            {
              v115 = v155;
            }
            if ( (*(_BYTE *)(v159 + 14) & 1) != 0 )
            {
              v15 = v155;
            }
            else
            {
              FsRecoveryOperation::FsRecoveryOperation((FsRecoveryOperation *)v559);
              (*(void (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v114 + 1736) + 40LL))(
                *(_QWORD *)(v114 + 1736),
                v532);
              if ( (*((_DWORD *)v115 + 134) & 5) == 1 )
              {
                v117 = *((_DWORD *)v115 + 182) & 1;
                v215 = v117;
              }
              else
              {
                v215 = 0;
                v117 = 0;
              }
              v118 = v114;
              v15 = v155;
              FsRecoveryOperation::Init(v559, v155, v30, v118, v300, v159, 2 * v117 + 1, v532);
              FsRecoveryOperation::Undo((FsRecoveryOperation *)v559);
            }
            break;
          case 8:
            HandleDbVerLogRecord(v15, (const struct LogRec *)v22, *((struct RecoveryUnit **)v15 + 6));
            goto LABEL_110;
          case 9:
            if ( (*(_BYTE *)(v22 + 14) & 1) == 0 )
            {
              v401 = &v524;
              v524 = 0;
              v525 = 0;
              v402 = &v526;
              v526 = *(_QWORD *)(v22 + 24);
              v527 = *(_WORD *)(v22 + 32);
              v403 = v22 + 34;
              v404 = &v528;
              v528 = *(_DWORD *)(v22 + 34);
              v529 = *(_WORD *)(v22 + 38);
              v530 = *(_DWORD *)(v22 + 40);
              v531 = *(_DWORD *)(v22 + 44);
              CopyVersionInfoLog::Log((CopyVersionInfoLog *)v523, v15);
            }
            goto LABEL_110;
          case 0xA:
            v180 = 0;
            v181 = 0;
            v182 = 0;
            v388 = v22;
            (*(void (__fastcall **)(XDES *))(*(_QWORD *)v15 + 472LL))(v15);
            *((_DWORD *)v15 + 182) |= 4u;
            v197 = *(_DWORD *)(v22 + 30);
            v198 = *(_WORD *)(v22 + 34);
            v389 = v22 + 24;
            v180 = *(_DWORD *)(v22 + 24);
            v181 = *(_WORD *)(v22 + 28);
            DropAllocationUnitInRollback(v15, &v180, &v197, 2);
            *((_DWORD *)v15 + 182) &= ~4u;
            LOBYTE(v150) = -82;
            (*(void (__fastcall **)(XDES *, int *, int *, _QWORD, _DWORD))(*(_QWORD *)v15 + 480LL))(
              v15,
              &v180,
              &v197,
              *(unsigned int *)(v22 + 36),
              (_DWORD)v150);
            goto LABEL_110;
          case 0xB:
            v184 = 0;
            v185 = 0;
            v186 = 0;
            v390 = v22;
            v106 = *((_DWORD *)v15 + 182) | 4;
            *((_DWORD *)v15 + 182) = v106;
            v391 = v22 + 32;
            v184 = *(_DWORD *)(v22 + 32);
            v185 = *(_WORD *)(v22 + 36);
            if ( (v106 & 1) != 0 )
              ++*((_DWORD *)v15 + 2283);
            DropAllocationUnitInRollback(v15, &v184, v22 + 24, 3);
            *((_DWORD *)v15 + 182) &= ~4u;
            goto LABEL_110;
          case 0xC:
            v7 = v154;
            v110 = (const struct LSN *)(*(__int64 (__fastcall **)(struct LogIter *, char *))(*(_QWORD *)v154 + 24LL))(
                                         v154,
                                         v548);
            LogRec_FulltextCreate::Undo((LogRec_FulltextCreate *)v22, v15, v110);
            goto LABEL_70;
          case 0xD:
            v7 = v154;
            (*(void (__fastcall **)(struct LogIter *, char *))(*(_QWORD *)v154 + 24LL))(v154, v549);
            LogRec_FulltextDrop::Undo((LogRec_FulltextDrop *)v22, v15, v111);
            goto LABEL_70;
          case 0xE:
            XDES::LogTextInfo(v15, (const struct TextInfo *)(v22 + 24));
            goto LABEL_110;
          case 0xF:
            XDES::LogReplNoop(v15, (struct LSN *)v546);
            goto LABEL_110;
          case 0x10:
            XDES::LogFilestreamInfo(v15, (const struct FilestreamInfo *)(v22 + 24));
            goto LABEL_110;
          case 0x11:
            RollbackBulkTempPageAllocation((const struct BulkAllocLog *)v22, v15);
            goto LABEL_110;
          case 0x12:
            v123 = (const wchar_t *)VarLogData::GetData((VarLogData *)(v22 + 28), 0, v280);
            v301 = v123;
            v124 = DBGetHandlerForPath(v123, 0);
            v409 = v124;
            if ( v124 )
            {
              v125 = (*(__int64 (__fastcall **)(struct IFileSystemHandler *, const wchar_t *, _QWORD))(*(_QWORD *)v124 + 144LL))(
                       v124,
                       v123,
                       0);
              v214 = v125;
            }
            else
            {
              SetLastError(0x32u);
              v125 = 0;
              v214 = 0;
            }
            v280[1] = v125;
            LastError = GetLastError();
            v213 = LastError;
            if ( v125 )
              goto LABEL_341;
            v174 = (unsigned __int8)byte_10317AC62 >> 2;
            if ( (byte_10317AC62 & 4) != 0 )
              goto LABEL_340;
            v192 = 0;
            v410 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v411 = (_QWORD *)(v410[SystemThread_TlsIndex] + SystemThread_TlsOffset);
            v412 = v411;
            v127 = *v411;
            v413 = v127;
            v414 = v127;
            if ( !v127 )
            {
              v240 = 0;
LABEL_337:
              v128 = v192;
              goto LABEL_338;
            }
            v130 = **(struct CSessionTraceFlags ***)(v127 + 56);
            v415 = v130;
            if ( !v130 )
            {
              v240 = 0;
              goto LABEL_337;
            }
            v240 = v130;
            v128 = CSessionTraceFlags::CheckSessionTraceInternal(v130, 0x712u);
            v192 = v128;
LABEL_338:
            if ( v128 )
            {
              LastError = v213;
              v123 = v301;
LABEL_340:
              OSErrString = GetOSErrString(LastError, (struct ErrorStringHolder *)v558, 0, 0);
              traceprint(L"OS Error %d (%ls) deleting file %ls \n", LastError, OSErrString, v123);
            }
LABEL_341:
            v15 = v155;
            goto LABEL_110;
          case 0x13:
            if ( (*(_BYTE *)(v22 + 14) & 1) == 0 )
              XdesRMReadWrite::UndoRangeLogRecord(v15, (const struct RangeLog *)v22);
            goto LABEL_110;
          case 0x14:
            if ( (*(_BYTE *)(v22 + 14) & 1) == 0 )
              InvalidateCacheLog::UndoFromRollback((InvalidateCacheLog *)v22, v15, *((struct RecoveryUnit **)v15 + 6));
            goto LABEL_110;
          case 0x15:
            v405 = v22;
            switch ( *(_DWORD *)(v22 + 24) )
            {
              case 0x11:
              case 0x12:
              case 0x13:
                HandleUndoCSIType<HoBtRowGroupAttribute>(v15, v22);
                break;
              case 0x21:
              case 0x22:
              case 0x23:
                HandleUndoCSIType<ColumnStoreColumnSegmentAttribute>(v15, v22);
                break;
              case 0x31:
              case 0x32:
              case 0x33:
                HandleUndoCSIType<ColumnStoreDictionaryAttribute>(v15, v22);
                break;
              case 0x41:
              case 0x43:
                HandleUndoCSIType<unsigned long>(v15, v22);
                break;
              default:
                utassert_fail(1u, "FALSE", "HoBtRowGroup.cpp", 4976, "Invalid switch value");
                break;
            }
            if ( (*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v15 + 136LL))(v15)
              || !XDES::ShouldLogToSLog((const struct LogRec *)v22, v119)
              || (*(_BYTE *)(v22 + 14) & 1) != 0
              || *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v15 + 6) + 1712LL) + 640LL) )
            {
              goto LABEL_110;
            }
            goto LABEL_315;
          case 0x16:
            if ( *(_DWORD *)(*((_QWORD *)v15 + 6) + 1668LL) < 0x335u )
              utassert_fail(1u, "m_recoveryUnit->GetRDBVersion () >= SQL15_DBUFF_FLUSH", "xdes.cpp", 7945, 0);
            v406 = v22;
            if ( !*(_QWORD *)(v22 + 32) )
            {
              v120 = *(_QWORD *)(*((_QWORD *)v15 + 6) + 1712LL);
              LODWORD(v150) = *(_DWORD *)(v120 + 928);
              ex_raise(90, 4, 23, 4, v150, v120 + 936);
            }
            if ( (*(_BYTE *)(v22 + 14) & 1) == 0 )
            {
              v237 = 0;
              CSIDeleteBufferLogRecord::GetOperationHandler(v22, &v237, v15);
              v122 = v237;
              (**v237)(v237, v15);
              v408 = v122;
              operator delete(v122, 0x10u);
            }
            if ( (*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v15 + 136LL))(v15)
              || !XDES::ShouldLogToSLog((const struct LogRec *)v22, v121)
              || (*(_BYTE *)(v22 + 14) & 1) != 0
              || *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v15 + 6) + 1712LL) + 640LL) )
            {
              goto LABEL_110;
            }
LABEL_315:
            XdesRMReadWrite::AppendColumnstoreCLR(v15, **((const struct LogRec ***)v15 + 1105));
            goto LABEL_110;
          case 0x17:
            v416 = v22;
            v131 = *(_OWORD *)(v22 + 24);
            v454 = v131;
            v132 = 0;
            v167 = 0;
            v133 = *(_QWORD *)(v22 + 40);
            v417 = v133;
            v134 = 0;
            v211 = 0;
            if ( !(unsigned int)LogRec::HasVarLogData((LogRec *)v22) )
              goto LABEL_341;
            v135 = VarLogData::GetData((VarLogData *)(v22 + 48), 0, &v281);
            v418 = v135;
            v136 = 0;
            v212 = 0;
            if ( VarLogData::GetData((VarLogData *)(v22 + 48), 0, v282) )
            {
              v203 = *(_WORD *)(v22 + 50);
              v136 = v203 / 0x14u;
              v212 = v136;
            }
            v282[1] = v136;
            v137 = *((_QWORD *)v155 + 6);
            if ( v137 )
            {
              v132 = *(_WORD *)(*(_QWORD *)(v137 + 1712) + 40LL);
              v167 = v132;
              v134 = *(unsigned __int8 *)(v137 + 8272);
              v211 = v134;
            }
            else
            {
              v139 = *((_QWORD *)v155 + 26);
              if ( v139 )
              {
                v132 = *(_WORD *)(v139 + 258);
                v167 = v132;
              }
            }
            if ( !byte_10316E616 || !v132 || !v133 || v134 || !v136 || !v135 )
            {
              v15 = v155;
              goto LABEL_110;
            }
            v479 = 0;
            v480 = 0;
            v481 = 0;
            v482 = 0;
            v483 = 0;
            v484 = 0;
            v485 = 0;
            v486 = 0;
            v487 = 0;
            v488 = 0;
            v490 = 0;
            v492 = 0;
            v493 = 0;
            v419 = &v494;
            v210 = 0;
            for ( j = 0; j < 1; v210 = j )
              *(&v494 + j++) = 0;
            v495 = v135;
            v496 = v136;
            v420 = 0;
            try
            {
              ExcHandler::ExcHandler((ExcHandler *)v456, 0, 0, 0, hdl_prntbackout, 0);
              v452 = v131;
              v15 = v155;
              ISECManager::CheckPermRuleAuditOnly(
                1329876565,
                0,
                0,
                v132,
                v132,
                1,
                0,
                v478,
                v133,
                &v452,
                0,
                1,
                *((_QWORD *)v155 + 82),
                -1);
              ExcHandler::~ExcHandler((ExcHandler *)v456);
            }
            catch ( SQLError v455 )
            {
              try
              {
                ExceptionBackout::ExceptionBackout((ExceptionBackout *)v453, (const struct SQLError *)v455);
                ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v453);
              }
              catch ( ShortStackException )
              {
              }
              v156 = v193;
              v15 = v168;
              v155 = v168;
              Source = v238;
              v7 = v225;
              v154 = v225;
              v178 = v226;
              goto LABEL_364;
            }
            v7 = v154;
LABEL_364:
            v421 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v140 = v421[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v422 = v140;
            v141 = *(struct Worker **)(v140 + 256);
            v302 = v141;
            if ( !v141 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v141 = *(struct Worker **)(v140 + 256);
              v302 = v141;
            }
            v423 = v141;
            if ( *((_DWORD *)v141 + 139) )
              ExceptionPostCatchActions(v141);
            if ( v490 )
            {
              v424 = v489;
              operator delete[](v489);
            }
            if ( v492 )
            {
              v425 = v491;
              operator delete[](v491);
            }
            goto LABEL_70;
          case 0x18:
            goto LABEL_372;
        }
        goto LABEL_70;
      }
LABEL_372:
      utassert_fail(1u, "0", "xdes.cpp", 8064, "Unexpected log record during rollback");
    }
    else
    {
      v303 = v22;
      if ( v178 )
      {
        v201 = *(_WORD *)(v22 + 46);
        v269 = *(_DWORD *)(v22 + 32);
        v219 = v269;
        v220 = v201;
        v221 = 0;
        Entry = IndexErrorTable::FindEntry(v178, (const struct AllocUnitId *)&v219);
        v293 = Entry;
      }
      else
      {
        v293 = 0;
        Entry = 0;
      }
      if ( (*(_BYTE *)(v22 + 14) & 1) == 0 && !Entry )
      {
        v351 = v22 + 24;
        v195 = *(_DWORD *)(v22 + 24);
        v42 = *(unsigned __int16 *)(v22 + 28);
        v196 = v42;
        v202 = v42;
        v352 = *((_QWORD *)v15 + 6);
        FCB = FileMgr::GetFCB(*(_QWORD *)(v352 + 1696), v42, 0);
        v353 = FCB;
        if ( !FCB )
          utassert_fail(1u, "fcb", "xdes.cpp", 7397, 0);
        if ( *(_DWORD *)(FCB + 104) != 5 )
        {
          if ( (*(_BYTE *)(FCB + 124) & 1) != 0 && (*(_DWORD *)(FCB + 100) & 0x90000000) == 0 )
          {
            v7 = v154;
            v45 = (const struct LSN *)(*(__int64 (__fastcall **)(struct LogIter *, char *))(*(_QWORD *)v154 + 24LL))(
                                        v154,
                                        v553);
            XdesRMReadWrite::UndoPageOperation(v15, (const struct PageLog *)v22, v45, v294, (struct PageRef *)&v160);
            if ( v160 )
            {
              v158 = 1;
              v207 = *(__int16 *)(v22 + 30);
            }
            else
            {
              v158 = 0;
            }
            goto LABEL_70;
          }
          v57 = *((_QWORD *)v15 + 6);
          v58 = *(_QWORD *)(v57 + 1832);
          v354 = v58;
          if ( !v58 || (!*(_QWORD *)(v58 + 24512) || !*(_DWORD *)(v58 + 24520) ? (v59 = 0) : (v59 = 1), !v59) )
          {
            FgOrThrow = FGMgr::FindFgOrThrow(*(FGMgr **)(v57 + 1688), *(__int16 *)(FCB + 132));
            ex_raise(34, 10, 16, 1, (char *)FgOrThrow + 100);
          }
        }
      }
    }
LABEL_110:
    v7 = v154;
LABEL_70:
    ExcHandler::~ExcHandler((ExcHandler *)v457);
    v46 = v304;
    if ( !v304 )
    {
      v426 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v47 = v426[SystemThread_TlsIndex] + SystemThread_TlsOffset;
      v427 = v47;
      v46 = *(struct Worker **)(v47 + 256);
      v305 = v46;
      if ( !v46 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v46 = *(struct Worker **)(v47 + 256);
        v305 = v46;
      }
    }
    v306 = v46;
    if ( *((_DWORD *)v46 + 139) )
      ExceptionPostCatchActions(v46);
    if ( !v158 )
    {
      v428 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v6 = SystemThread_TlsIndex;
      v48 = v428[SystemThread_TlsIndex] + SystemThread_TlsOffset;
      v429 = v48;
      v49 = *(_QWORD **)(v48 + 256);
      v322 = v49;
      if ( !v49 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v49 = *(_QWORD **)(v48 + 256);
        v322 = v49;
      }
      v430 = v49;
      v50 = __rdtsc();
      v431 = v50;
      v51 = v49[104];
      if ( v50 > v51
        || (v6 = 0x7FFFFFFFFFFFFFFFLL, v51 != 0x7FFFFFFFFFFFFFFFLL)
        && (v6 = v49[76], v51 - v50 > *(_QWORD *)(v6 + 3568)) )
      {
        v194 = SOS_Task::Sleep(0, yieldWait);
        if ( v194 == 2 )
        {
LABEL_382:
          LOBYTE(v6) = -51;
          RaiseExecutionAbortedError(v6);
        }
      }
      else
      {
        v308 = v49[75];
        v432 = v308 + 188;
        if ( (*(_DWORD *)(v308 + 188) & 4) != 0 )
        {
          v6 = *(_QWORD *)(v308 + 152);
          v433 = v6;
          if ( (*(_BYTE *)(v6 + 616) & 1) == 0 )
          {
            v142 = *(_DWORD *)(v6 + 800);
            if ( (v142 & 0x80u) == 0 && (v142 & 0x100) == 0 )
            {
              v194 = 2;
              goto LABEL_382;
            }
          }
        }
        v194 = 0;
      }
    }
  }
  v25 = (const struct LSN *)Source;
LABEL_112:
  if ( !(*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v15 + 136LL))(v15) )
    XdesRMReadWrite::UndoVirtualLogRecsToLSN(v15, v25);
  if ( v160 )
  {
    v434 = v160 + 98;
    v204 = *(_WORD *)(v160 + 98);
    if ( (v204 & 0x400) != 0 && (__int16)v162 >= 3 )
    {
      PageRef::UnfixLatchOnly((PageRef *)&v160);
      goto LABEL_115;
    }
    v163 = (__int16)v162;
    v224 = v160;
    v435 = v160 + 98;
    v205 = *(_WORD *)(v160 + 98);
    if ( (v205 & 8) == 0 )
      goto LABEL_393;
    if ( v163 == 3 )
    {
      v163 = 4;
    }
    else if ( v163 < 2 )
    {
LABEL_393:
      v175 = (unsigned __int8)byte_10317ABE5 >> 7;
      if ( byte_10317ABE5 < 0 )
      {
        v145 = (volatile signed __int32 *)(v224 + 100);
        v438 = v224 + 100;
        v284 = *(_DWORD *)(v224 + 100);
        if ( (v284 & 8) != 0 && v163 >= 3 )
        {
          v439 = v224 + 100;
          v285 = *v145;
          if ( (v285 & 0xC0000000) != 0x40000000 )
          {
            v146 = *(void **)v224;
            if ( *(_QWORD *)v224 )
            {
              v286 = 2;
              if ( VirtualProtect(v146, 0x2000u, 2u, &v273) )
              {
                _InterlockedAnd(v145, 0x3FFFFFFFu);
                _InterlockedOr(v145, 0x40000000u);
              }
            }
          }
        }
      }
      v147 = v224;
      v148 = v163;
      LatchBase::ReleaseInternal(v224 + 152, (unsigned int)v163);
      if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
      {
        v177 = (unsigned __int8)byte_10317AD4F >> 1;
        if ( (byte_10317AD4F & 2) != 0 )
          BUF::TraceLatchAcquireRelease(v147, 0, v148);
      }
      v162 &= 0xFFFF0000;
      v160 = 0;
      v15 = v155;
      goto LABEL_115;
    }
    v436 = v160 + 100;
    v283 = *(_DWORD *)(v160 + 100);
    if ( (v283 & 8) != 0 )
    {
      v144 = *(_QWORD *)(v160 + 144);
      if ( v144 )
      {
        v437 = *(_QWORD *)(v160 + 144);
        if ( *(_QWORD *)(v144 + 1880) )
        {
          _mm_lfence();
          DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v144 + 1880), v160, (unsigned int)v163);
        }
      }
    }
    goto LABEL_393;
  }
LABEL_115:
  if ( !v22 || v179 )
  {
    v232 = 0;
    v233 = 0;
    *((_QWORD *)v15 + 1080) = 0;
    *((_WORD *)v15 + 4324) = 0;
  }
  else
  {
    v149 = (*(__int64 (__fastcall **)(struct LogIter *, char *))(*(_QWORD *)v7 + 24LL))(v7, v554);
    *((_QWORD *)v15 + 1080) = *(_QWORD *)v149;
    *((_WORD *)v15 + 4324) = *(_WORD *)(v149 + 8);
  }
  v60 = (volatile signed __int32 *)*((_QWORD *)v15 + 1101);
  if ( v60 )
  {
    v309 = (DatasetSession *)*((_QWORD *)v15 + 1101);
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v60 + 408LL))(v60);
    if ( !_InterlockedDecrement(v60 + 150) )
    {
      v61 = v309;
      if ( *((_DWORD *)v309 + 2) )
        DatasetSession::GoDormant(v309);
      v440 = v61;
      (**(void (__fastcall ***)(DatasetSession *, __int64))v61)(v61, 1);
    }
    *((_QWORD *)v15 + 1101) = 0;
  }
  ExcHandler::~ExcHandler((ExcHandler *)v458);
  v62 = v310;
  if ( !v310 )
  {
    v63 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v62 = *(struct Worker **)(v63 + 256);
    if ( !v62 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v62 = *(struct Worker **)(v63 + 256);
    }
  }
  if ( *((_DWORD *)v62 + 139) )
    ExceptionPostCatchActions(v62);
  *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL)
                       + 96LL)
           + 1185LL) = v157;
  v64 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v65 = *(struct Worker **)(v64 + 256);
  if ( !v65 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v65 = *(struct Worker **)(v64 + 256);
  }
  if ( *((_DWORD *)v65 + 139) )
    ExceptionPostCatchActions(v65);
  *((_DWORD *)v15 + 182) &= ~2u;
  PageRef::~PageRef((PageRef *)&v160);
  v228[0] = &IDbCopyRestoreCallback::`vftable';
  *(_DWORD *)(v258 + 616) &= ~v257;
}

```

## disassembly

```asm
0x1005b4980  push    rbx
0x1005b4982  push    rsi
0x1005b4983  push    rdi
0x1005b4984  push    r12
0x1005b4986  push    r13
0x1005b4988  push    r14
0x1005b498a  push    r15
0x1005b498c  mov     eax, 3AD0h
0x1005b4991  call    _alloca_probe
0x1005b4996  sub     rsp, rax
0x1005b4999  mov     [rsp+3B08h+var_3040], 0FFFFFFFFFFFFFFFEh
0x1005b49a5  movaps  [rsp+3B08h+var_48], xmm6
0x1005b49ad  mov     rax, cs:__security_cookie
0x1005b49b4  xor     rax, rsp
0x1005b49b7  mov     [rsp+3B08h+var_58], rax
0x1005b49bf  jmp     loc_1005B1287
0x1004b93ce  mov     eax, esi
0x1004b93d0  jmp     loc_1005B1BC0
0x1004b93d6  lea     rdx, ?yieldWait@@3VSOS_WaitInfo@@B; "c@"
0x1004b93dd  xor     ecx, ecx
0x1004b93df  call    ?Sleep@SOS_Task@@SA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z; SOS_Task::Sleep(ulong,SOS_WaitInfo const *)
0x1004b93e4  mov     [rsp+3B08h+var_39B8], eax
0x1004b93eb  cmp     eax, 2
0x1004b93ee  jnz     loc_1005B1C05
0x1004b93f4  jmp     loc_101D71BE7
0x1005b1287  mov     rax, r9
0x1005b128a  mov     [rsp+3B08h+var_3A08], rax
0x1005b1292  mov     r14, r8
0x1005b1295  mov     [rsp+3B08h+var_3A98], r8
0x1005b129a  mov     [rsp+3B08h+Source], rdx
0x1005b12a2  mov     r13, rcx
0x1005b12a5  mov     [rsp+3B08h+var_3A90], rcx
0x1005b12aa  mov     [rsp+3B08h+var_3A28], rcx
0x1005b12b2  mov     [rsp+3B08h+var_35D0], rcx
0x1005b12ba  mov     [rsp+3B08h+var_37B0], rdx
0x1005b12c2  mov     [rsp+3B08h+var_3840], r8
0x1005b12ca  mov     [rsp+3B08h+var_3830], rax
0x1005b12d2  mov     rax, [rsp+3B08h+arg_20]
0x1005b12da  mov     [rsp+3B08h+var_35E0], rax
0x1005b12e2  xor     r12d, r12d
0x1005b12e5  mov     [rsp+3B08h+var_3720], r12d
0x1005b12ed  mov     rdx, gs:58h
0x1005b12f6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1005b12fd  mov     ecx, [rax]
0x1005b12ff  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1005b1306  mov     ebx, [rax]
0x1005b1308  add     rbx, [rdx+rcx*8]
0x1005b130c  mov     rsi, [rbx+100h]
0x1005b1313  test    rsi, rsi
0x1005b1316  jz      loc_101D6FA63
0x1005b131c  mov     [rsp+3B08h+var_3718], rsi
0x1005b1324  mov     eax, [rsi+268h]
0x1005b132a  mov     edi, eax
0x1005b132c  and     edi, 27h
0x1005b132f  xor     edi, 27h
0x1005b1332  mov     [rsp+3B08h+var_3720], edi
0x1005b1339  or      eax, 27h
0x1005b133c  mov     [rsi+268h], eax
0x1005b1342  mov     [rsp+3B08h+var_3A78], r12
0x1005b134a  mov     [rsp+3B08h+var_3A88], r12d
0x1005b1352  mov     rcx, [r13+30h]
0x1005b1356  lea     rax, ??_7IDbCopyRestoreCallback@@6B@; const IDbCopyRestoreCallback::`vftable'
0x1005b135d  mov     [rsp+3B08h+var_3820], rax
0x1005b1365  lea     rax, ??_7TxLogDataReadAhead@@6B@; const TxLogDataReadAhead::`vftable'
0x1005b136c  mov     [rsp+3B08h+var_3820], rax
0x1005b1374  mov     [rsp+3B08h+var_3818], rcx
0x1005b137c  mov     eax, cs:?NullPageId@@3VPageId@@B; PageId const NullPageId
0x1005b1382  mov     [rsp+3B08h+var_3810], eax
0x1005b1389  movzx   eax, cs:word_1031997E8
0x1005b1390  mov     [rsp+3B08h+var_380C], ax
0x1005b1398  mov     [rsp+3B08h+var_380A], r12w
0x1005b13a1  test    rcx, rcx
0x1005b13a4  jz      loc_101D6FA78
0x1005b13aa  mov     r15d, 1
0x1005b13b0  lea     rax, ??_7UndoLogDataReadAhead@@6B@; const UndoLogDataReadAhead::`vftable'
0x1005b13b7  mov     [rsp+3B08h+var_3820], rax
0x1005b13bf  mov     [rsp+3B08h+var_39D8], r15d
0x1005b13c7  mov     [rsp+3B08h+var_3A70], r12
0x1005b13cf  mov     [rsp+3B08h+var_3A68], 0
0x1005b13d7  mov     eax, [rsp+3B08h+var_3A64]
0x1005b13de  and     eax, 0FFFF0000h
0x1005b13e3  mov     [rsp+3B08h+var_3A64], eax
0x1005b13ea  and     eax, 0FF00FFFFh
0x1005b13ef  mov     [rsp+3B08h+var_3A64], eax
0x1005b13f6  mov     [rsp+3B08h+var_3A64], r12d
0x1005b13fe  mov     [rsp+3B08h+var_3A80], r12d
0x1005b1406  mov     byte ptr [r13+22B4h], 0
0x1005b140e  lea     rbx, [r13+21C0h]
0x1005b1415  cmp     word ptr [rbx+8], 0
0x1005b141a  jz      loc_1005B3B53
0x1005b1420  mov     rdi, [rsp+3B08h+var_3A90]
0x1005b1425  and     dword ptr [rdi+2D8h], 0FFFFFFFBh
0x1005b142c  or      dword ptr [rdi+2D8h], 2
0x1005b1433  mov     rdx, gs:58h
0x1005b143c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1005b1443  mov     ecx, [rax]
0x1005b1445  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1005b144c  mov     eax, [rax]
0x1005b144e  add     rax, [rdx+rcx*8]
0x1005b1452  mov     rax, [rax+8]
0x1005b1456  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1005b145d  mov     [rax+28h], r15d
0x1005b1461  mov     rax, [rdi]
0x1005b1464  mov     rcx, rdi
0x1005b1467  call    qword ptr [rax+278h]
0x1005b146d  test    eax, eax
0x1005b146f  jnz     loc_101D6FAA6
0x1005b1475  mov     esi, 1
0x1005b147a  mov     ecx, [rsp+3B08h+var_3A88]
0x1005b1481  mov     [rsp+3B08h+var_39BC], ecx
0x1005b1488  mov     rdx, gs:58h
0x1005b1491  mov     [rsp+3B08h+var_3038], rdx
0x1005b1499  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1005b14a0  mov     ecx, [rax]
0x1005b14a2  lea     r9, ds:0[rcx*8]
0x1005b14aa  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1005b14b1  mov     r8d, [rax]
0x1005b14b4  mov     rcx, [rdx+r9]
0x1005b14b8  lea     rcx, [r8+rcx]
0x1005b14bc  mov     [rsp+3B08h+var_3030], rcx
0x1005b14c4  mov     rax, [rcx+8]
0x1005b14c8  mov     [rsp+3B08h+var_3028], rax
0x1005b14d0  mov     rcx, [rax+60h]
0x1005b14d4  mov     [rsp+3B08h+var_3020], rcx
0x1005b14dc  movzx   eax, byte ptr [rcx+4A1h]
0x1005b14e3  mov     [rsp+3B08h+var_3A84], al
0x1005b14ea  mov     rax, gs:58h
0x1005b14f3  mov     [rsp+3B08h+var_3018], rax
0x1005b14fb  mov     rcx, [r9+rax]
0x1005b14ff  lea     rcx, [r8+rcx]
0x1005b1503  mov     [rsp+3B08h+var_3010], rcx
0x1005b150b  mov     rax, [rcx+8]
0x1005b150f  mov     [rsp+3B08h+var_3008], rax
0x1005b1517  mov     rcx, [rax+60h]
0x1005b151b  mov     [rsp+3B08h+var_3000], rcx
0x1005b1523  mov     byte ptr [rcx+4A1h], 2
0x1005b152a  mov     [rsp+3B08h+var_3530], r12
0x1005b1532  xor     edx, edx; unsigned __int16
0x1005b1534  mov     [rsp+3B08h+var_3AE0], r12; struct Worker *
0x1005b1539  lea     rax, ?XdesExceptionHandler@@YAHHHHHPEAD@Z; XdesExceptionHandler(int,int,int,int,char *)
0x1005b1540  mov     [rsp+3B08h+var_3AE8], rax; int (*)(int, int, int, int, char *)
0x1005b1545  xor     r9d, r9d; unsigned __int8
0x1005b1548  xor     r8d, r8d; unsigned __int8
0x1005b154b  lea     rcx, [rsp+3B08h+var_2ED0]; this
0x1005b1553  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x1005b1558  nop
0x1005b1559  movzx   eax, word ptr [rdi+2202h]
0x1005b1560  mov     ecx, 0FFFFh
0x1005b1565  cmp     ax, cx
0x1005b1568  jnb     short loc_1005B1574
0x1005b156a  inc     ax
0x1005b156d  mov     [rdi+2202h], ax
0x1005b1574  mov     [rsp+3B08h+var_3710], 0FFFFFFFFh
0x1005b157f  mov     [rsp+3B08h+var_370C], 0FFFFFFFFh
0x1005b158a  mov     [rsp+3B08h+var_3708], cx
0x1005b1592  mov     [rsp+3B08h+var_2FF8], rbx
0x1005b159a  cmp     [rbx+8], cx
0x1005b159e  jnz     loc_101D6FB4B
0x1005b15a4  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1005b15a7  jnz     loc_101D6FB4B
0x1005b15ad  cmp     dword ptr [rbx+4], 0FFFFFFFFh
0x1005b15b1  jnz     loc_101D6FB4B
0x1005b15b7  mov     eax, esi
0x1005b15b9  jmp     short loc_1005B15BC
0x1005b15bc  test    eax, eax
0x1005b15be  jz      loc_101D6FB54
0x1005b15c4  movsd   xmm0, qword ptr [rdi+221Ch]
0x1005b15cc  movzx   eax, word ptr [rdi+2224h]
0x1005b15d3  jmp     short loc_1005B15D6
0x1005b15d6  mov     [rsp+3B08h+var_2B60], ax
0x1005b15de  movsd   [rsp+3B08h+var_2B68], xmm0
0x1005b15e7  mov     rax, [r14]
0x1005b15ea  mov     [rsp+3B08h+var_3AD0], r12
0x1005b15ef  mov     byte ptr [rsp+3B08h+var_3AD8], 0
0x1005b15f4  mov     dword ptr [rsp+3B08h+var_3AE0], r12d
0x1005b15f9  mov     dword ptr [rsp+3B08h+var_3AE8], r12d
0x1005b15fe  xor     r9d, r9d
0x1005b1601  lea     r8, [rsp+3B08h+var_3820]
0x1005b1609  lea     rdx, [rsp+3B08h+var_2B68]
0x1005b1611  mov     rcx, r14
0x1005b1614  call    qword ptr [rax+30h]
0x1005b1617  mov     [rsp+3B08h+var_3A00], r12d
0x1005b161f  lea     rax, [rsp+3B08h+var_3A18]
0x1005b1627  mov     [rsp+3B08h+var_2FF0], rax
0x1005b162f  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1005b1636  mov     ecx, [rax]
0x1005b1638  mov     [rsp+3B08h+var_3514], ecx
0x1005b163f  test    ecx, ecx
0x1005b1641  jz      loc_101D6FB62
0x1005b1647  lea     rcx, [rsp+3B08h+PerformanceCount]; lpPerformanceCount
0x1005b164f  call    cs:__imp_QueryPerformanceCounter
0x1005b1655  mov     rax, qword ptr [rsp+3B08h+PerformanceCount]
0x1005b165d  mov     [rsp+3B08h+var_3A18], rax
0x1005b1665  jmp     short loc_1005B1668
0x1005b1668  mov     [rsp+3B08h+var_3A78], r12
0x1005b1670  mov     rax, [r14]
0x1005b1673  mov     rcx, r14
0x1005b1676  call    qword ptr [rax+28h]
0x1005b1679  mov     r13, rax
0x1005b167c  mov     [rsp+3B08h+var_3A78], rax
0x1005b1684  test    rax, rax
0x1005b1687  jz      loc_1005B3979
0x1005b168d  mov     r8, [r14]
0x1005b1690  lea     rdx, [rsp+3B08h+var_29A8]
0x1005b1698  mov     rcx, r14
0x1005b169b  call    qword ptr [r8+18h]
0x1005b169f  mov     rcx, rax
0x1005b16a2  mov     [rsp+3B08h+var_2F80], rax
0x1005b16aa  mov     edx, [rax]
0x1005b16ac  mov     rbx, [rsp+3B08h+Source]
0x1005b16b4  cmp     edx, [rbx]
0x1005b16b6  jb      loc_1005B354F
0x1005b16bc  jnz     short loc_1005B16D0
0x1005b16be  mov     eax, [rax+4]
0x1005b16c1  cmp     eax, [rbx+4]
0x1005b16c4  jb      loc_1005B354F
0x1005b16ca  jz      loc_1005B3541
0x1005b16d0  mov     eax, r12d
0x1005b16d3  jmp     short loc_1005B16D6
0x1005b16d6  test    eax, eax
0x1005b16d8  jnz     loc_1005B3981
0x1005b16de  cmp     [rsp+3B08h+var_3A00], eax
0x1005b16e5  jnz     loc_1005B3981
0x1005b16eb  mov     rax, [rdi+30h]
0x1005b16ef  mov     rcx, [rax+6C8h]
0x1005b16f6  test    rcx, rcx
0x1005b16f9  jz      short loc_1005B170D
0x1005b16fb  mov     rax, [rcx]
0x1005b16fe  call    qword ptr [rax+308h]
0x1005b1704  cmp     eax, 7
0x1005b1707  jz      loc_101D6FB80
0x1005b170d  mov     rax, [r14]
0x1005b1710  lea     rdx, [rsp+3B08h+var_2998]
0x1005b1718  mov     rcx, r14
0x1005b171b  call    qword ptr [rax+18h]
0x1005b171e  mov     rdx, rax; struct LSN *
0x1005b1721  mov     rcx, rdi; this
0x1005b1724  call    ?UndoVirtualLogRecsToLSN@XdesRMReadWrite@@IEAAXAEBVLSN@@@Z; XdesRMReadWrite::UndoVirtualLogRecsToLSN(LSN const &)
0x1005b1729  lea     r15, [rdi+28h]
0x1005b172d  mov     [rsp+3B08h+var_2F78], r15
0x1005b1735  lea     r14, [r13+10h]
0x1005b1739  mov     [rsp+3B08h+var_2F70], r14
0x1005b1741  movzx   eax, word ptr [r15+4]
0x1005b1746  cmp     [r14+4], ax
0x1005b174b  jnz     loc_101D6FBBE
0x1005b1751  mov     eax, [r15]
0x1005b1754  cmp     [r14], eax
0x1005b1757  jnz     loc_101D6FBBE
0x1005b175d  mov     eax, esi
0x1005b175f  jmp     short loc_1005B1762
0x1005b1762  test    eax, eax
0x1005b1764  jz      loc_101D6FBC7
0x1005b176a  mov     ebx, [rsp+3B08h+var_3A88]
0x1005b1771  test    ebx, ebx
0x1005b1773  jnz     loc_101D6FBEF
0x1005b1779  lea     rax, [rsp+3B08h+var_3870]
0x1005b1781  mov     [rsp+3B08h+var_2F68], rax
0x1005b1789  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1005b1790  mov     ecx, [rax]
0x1005b1792  mov     [rsp+3B08h+var_3510], ecx
0x1005b1799  test    ecx, ecx
0x1005b179b  jz      loc_101D6FC20
0x1005b17a1  lea     rcx, [rsp+3B08h+var_3550]; lpPerformanceCount
0x1005b17a9  call    cs:__imp_QueryPerformanceCounter
0x1005b17af  mov     rcx, qword ptr [rsp+3B08h+var_3550]
0x1005b17b7  mov     [rsp+3B08h+var_3870], rcx
0x1005b17bf  jmp     short loc_1005B17C2
0x1005b17c2  lea     rax, [rsp+3B08h+var_3A18]
0x1005b17ca  mov     [rsp+3B08h+var_2F58], rax
0x1005b17d2  lea     rax, [rsp+3B08h+var_3870]
0x1005b17da  mov     [rsp+3B08h+var_3480], rax
0x1005b17e2  mov     rax, [rsp+3B08h+var_3A18]
0x1005b17ea  cmp     rcx, rax
0x1005b17ed  jb      loc_101D6FC46
0x1005b17f3  sub     rcx, rax
0x1005b17f6  mov     [rsp+3B08h+var_39E0], rcx
0x1005b17fe  jmp     short loc_1005B1801
0x1005b1801  mov     [rsp+3B08h+var_37A8], rcx
0x1005b1809  lea     rax, [rsp+3B08h+var_37A8]
0x1005b1811  mov     [rsp+3B08h+var_3478], rax
0x1005b1819  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1005b181d  jz      loc_101D6FC57
0x1005b1823  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1005b182a  mov     edx, [rax]
0x1005b182c  mov     [rsp+3B08h+var_350C], edx
0x1005b1833  test    edx, edx
0x1005b1835  jz      loc_101D6FC68
0x1005b183b  mov     r8, cs:__imp_?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A; _LARGE_INTEGER Base_PublicGlobals::sm_QueryPerformanceFrequency
0x1005b1842  mov     r8, [r8]
0x1005b1845  mov     [rsp+3B08h+var_3470], r8
0x1005b184d  mov     [rsp+3B08h+var_3468], r8
0x1005b1855  mov     [rsp+3B08h+var_3460], rsi
0x1005b185d  xor     edx, edx
0x1005b185f  mov     rax, rcx
0x1005b1862  div     r8
0x1005b1865  mov     rdx, rax
0x1005b1868  mov     [rsp+3B08h+var_3798], rax
0x1005b1870  jmp     short loc_1005B1873
0x1005b1873  mov     [rsp+3B08h+var_3448], rdx
0x1005b187b  cmp     rdx, 3Ch ; '<'
  ... truncated ...
```
