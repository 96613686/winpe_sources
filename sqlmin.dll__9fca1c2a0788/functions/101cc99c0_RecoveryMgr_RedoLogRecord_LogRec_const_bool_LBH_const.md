# RecoveryMgr::RedoLogRecord(LogRec const *,bool,LBH const *)

- ea: `0x101cc99c0`
- end: `0x101ccd1e0`
- name: `?RedoLogRecord@RecoveryMgr@@AEAAXPEBVLogRec@@_NPEBVLBH@@@Z`
- size: `14368`
- prototype: `void __fastcall(RecoveryMgr *__hidden this, const struct LogRec *, bool, const struct LBH *)`
- caller_count: `2`
- callee_count: `68`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x101cc7260`
- `0x101cd0460`

## callees

- `0x100401010`
- `0x100401380`
- `0x1004013f0`
- `0x100401490`
- `0x100403030`
- `0x10040da80`
- `0x100415e90`
- `0x10041ba80`
- `0x100441e00`
- `0x100445560`
- `0x10045cdf0`
- `0x10045f030`
- `0x10046221a`
- `0x10047bc10`
- `0x100553e20`
- `0x1005ca770`
- `0x1005d22b0`
- `0x1005f1f00`
- `0x10068cf70`
- `0x10068d120`
- `0x10072d4d0`
- `0x10072d690`
- `0x100abf8b0`
- `0x1011f5660`
- `0x1011f59a0`
- `0x1011ff520`
- `0x1014314f0`
- `0x10171d4e0`
- `0x101790e00`
- `0x1017f5530`
- `0x101806950`
- `0x10181b7c0`
- `0x101843b30`
- `0x1018f4830`
- `0x101bdf900`
- `0x101c06a70`
- `0x101c0a560`
- `0x101c37920`
- `0x101c827c0`
- `0x101c837a0`
- `0x101c86c40`
- `0x101c8dd40`
- `0x101cad280`
- `0x101cb2900`
- `0x101cb2a60`
- `0x101cb66c0`
- `0x101cb8d40`
- `0x101cb9a30`
- `0x101cc5490`
- `0x101cc9820`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x101ccc690`
- `KERNEL32!QueryPerformanceCounter` at `0x101ccc6ee`
- `KERNEL32!QueryPerformanceCounter` at `0x101ccc825`
- `KERNEL32!QueryPerformanceCounter` at `0x101ccc883`
- `KERNEL32!QueryPerformanceCounter` at `0x101ccccb1`
- `KERNEL32!QueryPerformanceCounter` at `0x101cccd10`
- `KERNEL32!QueryPerformanceCounter` at `0x101ccc690`
- `KERNEL32!QueryPerformanceCounter` at `0x101ccc6ee`
- `KERNEL32!QueryPerformanceCounter` at `0x101ccc825`
- `KERNEL32!QueryPerformanceCounter` at `0x101ccc883`
- `KERNEL32!QueryPerformanceCounter` at `0x101ccccb1`
- `KERNEL32!QueryPerformanceCounter` at `0x101cccd10`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101ccc744`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101ccc8d2`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101ccc62e`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101ccc7c3`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101ccc6a8`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101ccc83d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101ccc67c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101ccc6da`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101ccc811`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101ccc86f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cccc9e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101ccccfd`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cccd44`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101cccd58`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101ccacd4`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101ccacd4`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101cca00c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101cca00c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cc9b21`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cca0a9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cca4c5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccac2c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccb2fa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccb4b1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccb4e1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccb5c2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccb6a2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccb9af`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccba76`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccbb1d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccbcd5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccbd47`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccbe4f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccbf24`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccbff8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccc293`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccc351`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccc3fc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cc9b21`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cca0a9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cca4c5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccac2c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccb2fa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccb4b1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccb4e1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccb5c2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccb6a2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccb9af`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccba76`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccbb1d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccbcd5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccbd47`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccbe4f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccbf24`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccbff8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccc293`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccc351`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ccc3fc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccb471`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccb59c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccb67c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccb989`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccba50`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccbe29`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccbefe`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccbfd2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccc26f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccc32d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccb471`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccb59c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccb67c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccb989`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccba50`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccbe29`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccbefe`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccbfd2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccc26f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101ccc32d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cc9a83`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cc9ad5`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cca56f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101ccad31`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101ccae67`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101ccaf8b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cccb95`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cc9a83`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cc9ad5`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cca56f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101ccad31`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101ccae67`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101ccaf8b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cccb95`
- `sqldk!SystemThread_TlsIndex` at `0x101cc9a54`
- `sqldk!SystemThread_TlsIndex` at `0x101cc9aa6`
- `sqldk!SystemThread_TlsIndex` at `0x101cca537`
- `sqldk!SystemThread_TlsIndex` at `0x101ccac9c`
- `sqldk!SystemThread_TlsIndex` at `0x101ccacfa`
- `sqldk!SystemThread_TlsIndex` at `0x101ccae30`
- `sqldk!SystemThread_TlsIndex` at `0x101ccaf54`
- `sqldk!SystemThread_TlsIndex` at `0x101ccb410`
- `sqldk!SystemThread_TlsIndex` at `0x101ccb547`
- `sqldk!SystemThread_TlsIndex` at `0x101ccb627`
- `sqldk!SystemThread_TlsIndex` at `0x101ccb934`
- `sqldk!SystemThread_TlsIndex` at `0x101ccb9fb`
- `sqldk!SystemThread_TlsIndex` at `0x101ccbdd4`
- `sqldk!SystemThread_TlsIndex` at `0x101ccbea9`
- `sqldk!SystemThread_TlsIndex` at `0x101ccbf7d`
- `sqldk!SystemThread_TlsIndex` at `0x101ccc21a`
- `sqldk!SystemThread_TlsIndex` at `0x101ccc2d8`
- `sqldk!SystemThread_TlsIndex` at `0x101ccc64e`
- `sqldk!SystemThread_TlsIndex` at `0x101ccc7e3`
- `sqldk!SystemThread_TlsIndex` at `0x101cccb5d`
- `sqldk!SystemThread_TlsOffset` at `0x101cc9a5d`
- `sqldk!SystemThread_TlsOffset` at `0x101cc9aaf`
- `sqldk!SystemThread_TlsOffset` at `0x101cca540`
- `sqldk!SystemThread_TlsOffset` at `0x101ccaca5`
- `sqldk!SystemThread_TlsOffset` at `0x101ccad03`
- `sqldk!SystemThread_TlsOffset` at `0x101ccae39`
- `sqldk!SystemThread_TlsOffset` at `0x101ccaf5d`
- `sqldk!SystemThread_TlsOffset` at `0x101ccb419`
- `sqldk!SystemThread_TlsOffset` at `0x101ccb550`
- `sqldk!SystemThread_TlsOffset` at `0x101ccb630`
- `sqldk!SystemThread_TlsOffset` at `0x101ccb93d`
- `sqldk!SystemThread_TlsOffset` at `0x101ccba04`
- `sqldk!SystemThread_TlsOffset` at `0x101ccbddd`
- `sqldk!SystemThread_TlsOffset` at `0x101ccbeb2`
- `sqldk!SystemThread_TlsOffset` at `0x101ccbf86`
- `sqldk!SystemThread_TlsOffset` at `0x101ccc223`
- `sqldk!SystemThread_TlsOffset` at `0x101ccc2e1`
- `sqldk!SystemThread_TlsOffset` at `0x101ccc657`
- `sqldk!SystemThread_TlsOffset` at `0x101ccc7ec`
- `sqldk!SystemThread_TlsOffset` at `0x101cccb66`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cc9fc0`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cc9fc0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101ccacbe`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101ccacbe`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101ccc750`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101ccc8de`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101ccc750`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101ccc8de`
- `sqllang!?FullTextMarkDroppedFilesAsUsable@@YAXPEAVRecoveryUnit@@@Z` at `0x101ccca1d`
- `sqllang!?FullTextMarkDroppedFilesAsUsable@@YAXPEAVRecoveryUnit@@@Z` at `0x101ccca1d`
- `rbio!RbIoFsUpdateSafeLsn` at `0x101ccceb8`
- `rbio!RbIoFsUpdateSafeLsn` at `0x101ccceb8`
- `rbio!RbIoFsRegisterPageLsn` at `0x101cccf08`
- `rbio!RbIoFsRegisterPageLsn` at `0x101cccf08`
- `hkengine!HkRedoUpdateLastRedoneBlock` at `0x101ccd064`
- `hkengine!HkRedoUpdateLastRedoneBlock` at `0x101ccd064`

## string_xrefs

- `0x101ccadff`: `REDO LSN %.*ls (0x%ls), XdesId 0x%04lx:%08lx redid %ls on page %d:%d.\n`
- `0x101ccaf36`: `REDO LSN %.*ls (0x%ls), XdesId 0x%04lx:%08lx deferred %ls on page %d:%d.\n`
- `0x101ccb056`: `REDO LSN %.*ls (0x%ls), XdesId 0x%04lx:%08lx skipped %ls on page %d:%d.\n`
- `0x101cccc4e`: `REDO LSN %.*ls (0x%ls), XdesId 0x%04lx:%08lx skipped %ls on page %d:%d due to DPT logic.\n`
- `0x101cca62a`: `REDO LSN %.*ls (0x%ls), XdesId 0x%04lx:%08lx skipped %ls on bad page %d:%d.\n`
- `0x101cc9b15`: `!IsForeignLogApply () || lp->IsPageOp () || LOP_END_CKPT == lp->log_op || LOP_CREATE_FILE == lp->log_op`
- `0x101cca4b5`: `(LOP_FILE_HDR_MODIFY == lp->GetOpCode ()) || m_recoveryUnit->IsIntendedUpdateable ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall RecoveryMgr::RedoLogRecord(RecoveryMgr *this, const struct LogRec *a2, char a3, const struct LBH *a4)
{
  struct LBH *v4; // r14
  const struct LogRec *v5; // r15
  RecoveryMgr *v6; // rsi
  struct LSN *v7; // rdi
  struct RecXdes *v8; // rbx
  __int64 v9; // r13
  __int64 v10; // rdx
  struct CSessionTraceFlags *v11; // rcx
  int v12; // r14d
  __int64 v13; // rdx
  struct CSessionTraceFlags *v14; // rcx
  unsigned __int8 v15; // al
  unsigned __int8 v16; // r8
  unsigned __int64 v17; // rax
  const struct LOG_OPERATION near *const *v18; // r12
  const struct LOG_OPERATION near *const *v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // r14
  unsigned __int8 *v24; // rax
  __int64 Xdes; // rax
  __int64 v26; // rdx
  struct RecXdes *v27; // r14
  int v28; // ecx
  int v29; // eax
  int v30; // r9d
  char v31; // al
  _QWORD *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // r15
  struct IMemObj *v35; // rax
  _QWORD *v36; // rax
  unsigned __int64 v37; // rax
  char v38; // al
  __int64 v39; // rcx
  __int64 v40; // rcx
  char v41; // r9
  char v42; // al
  bool v43; // zf
  unsigned int *v44; // r14
  struct LBH *Entry; // r9
  RecoveryUnit *v46; // rcx
  int v47; // r15d
  char v48; // r14
  RecoveryUnit *v49; // r8
  int v50; // r10d
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  int v54; // ecx
  unsigned int v55; // eax
  unsigned __int16 v56; // dx
  unsigned int v57; // eax
  __int64 v58; // rcx
  int v59; // eax
  int v60; // ecx
  __int64 v61; // rax
  struct CSessionTraceFlags *v62; // rcx
  unsigned __int8 v63; // dl
  unsigned __int64 v64; // rax
  int v65; // eax
  int v66; // ecx
  struct LBH *v67; // r14
  int v68; // eax
  unsigned int v69; // ecx
  int (*v70)(int, int, int, int, char *); // rax
  RecoveryUnit *v71; // rcx
  __int64 v72; // rax
  ParallelRedoManager *v73; // rcx
  unsigned __int8 *RedoValidationBuffer; // r14
  unsigned int TotalLength; // eax
  const struct PageLog *v76; // rax
  int v77; // eax
  ParallelRedoManager *v78; // r10
  struct LBH *v79; // r14
  const struct LogRec **v80; // r13
  unsigned int v81; // r14d
  char *v82; // rbx
  unsigned int v83; // eax
  char *v84; // rbx
  __int64 v85; // rax
  __int64 LogOpString; // rax
  __int16 v87; // r9
  __int64 v88; // rcx
  int v89; // ecx
  __int64 v90; // rbx
  struct Worker *v91; // rcx
  __int64 v92; // rdx
  struct CSessionTraceFlags *v93; // rcx
  int v94; // r10d
  unsigned __int8 v95; // dl
  unsigned __int64 v96; // rax
  struct LSN *v97; // r8
  int v98; // ecx
  __int64 v99; // rax
  struct CSessionTraceFlags *v100; // rcx
  int v101; // r10d
  unsigned __int8 v102; // dl
  unsigned __int64 v103; // rax
  struct LSN *v104; // r8
  int v105; // ecx
  __int64 v106; // rax
  struct CSessionTraceFlags *v107; // rcx
  int v108; // r10d
  unsigned __int8 v109; // dl
  unsigned __int64 v110; // rax
  struct LSN *v111; // r8
  int v112; // ecx
  char v113; // al
  unsigned int v114; // ebx
  const unsigned __int8 *Data; // rax
  const unsigned __int8 *v116; // r8
  unsigned __int8 v117; // r9
  unsigned __int16 v118; // ax
  unsigned __int16 v119; // cx
  __int16 v120; // r8
  unsigned int v121; // r14d
  const unsigned __int8 *v122; // r12
  unsigned __int16 v123; // dx
  __int64 v124; // rax
  __int64 v125; // rax
  unsigned int v126; // r8d
  __int64 v127; // rax
  __int64 v128; // rax
  __int64 v129; // rax
  __int64 v130; // rax
  const unsigned __int8 *v131; // rax
  unsigned int v132; // r14d
  unsigned __int16 v133; // r9
  const unsigned __int8 *v134; // rdx
  __int16 v135; // cx
  __int16 v136; // cx
  struct RecVersioningInfo *VersioningInfo; // rax
  __int64 v138; // rdx
  int v139; // r8d
  __int64 v140; // rax
  __int64 v141; // rax
  __int64 v142; // rax
  __int64 v143; // rax
  char v144; // cl
  bool v145; // zf
  int v146; // r12d
  int v147; // r14d
  const unsigned __int8 *v148; // rax
  const unsigned __int8 *v149; // r8
  unsigned __int8 v150; // r9
  unsigned __int16 v151; // ax
  unsigned __int16 v152; // cx
  __int16 v153; // ax
  __int16 v154; // r8
  unsigned int v155; // ebx
  const unsigned __int8 *v156; // r14
  unsigned __int16 v157; // dx
  __int64 v158; // rax
  __int64 v159; // rax
  unsigned int v160; // r8d
  __int64 v161; // rax
  __int64 v162; // rax
  __int64 v163; // rax
  __int64 v164; // rax
  const unsigned __int8 *v165; // rax
  unsigned int v166; // ebx
  unsigned __int16 v167; // r9
  const unsigned __int8 *v168; // rdx
  __int16 v169; // cx
  __int16 v170; // cx
  struct RecVersioningInfo *v171; // rax
  __int64 v172; // rdx
  int v173; // r8d
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 v176; // rax
  __int64 v177; // rax
  char v178; // cl
  const unsigned __int8 *v179; // r13
  unsigned int v180; // ebx
  const struct LSN *v181; // r12
  unsigned __int16 *v182; // r14
  __int64 FileOperationFCB; // rax
  __int64 *v184; // rcx
  __int64 v185; // rax
  char v186; // al
  RecoveryUnit *v187; // rax
  __int64 v188; // r12
  DirtyPageMgr *v189; // rbx
  signed __int64 UniqueThread_low; // r13
  __int64 v191; // r14
  __int64 v192; // r8
  __int64 v193; // rcx
  DirtyPageMgr *v194; // rax
  signed __int64 v195; // rax
  RecoveryUnit *v196; // rax
  __int64 v197; // rbx
  int v198; // r8d
  __int64 v199; // r12
  DirtyPageMgr *v200; // rbx
  signed __int64 v201; // r13
  __int64 v202; // r14
  __int64 v203; // r8
  __int64 v204; // rcx
  DirtyPageMgr *v205; // rax
  signed __int64 v206; // rax
  RecoveryUnit *v207; // rcx
  unsigned __int16 v208; // r14
  __int64 v209; // rbx
  int v210; // r8d
  RecoveryUnit *v211; // r10
  __int64 v212; // rdx
  __int64 v213; // rax
  RecoveryUnit *v214; // rbx
  __int64 v215; // rdx
  __int64 v216; // rcx
  __int64 v217; // rcx
  RecoveryUnit *v218; // rcx
  BPool *v219; // rbx
  RecoveryMgr *v220; // rcx
  __int64 v221; // rax
  struct CSessionTraceFlags *v222; // rcx
  unsigned __int8 v223; // dl
  unsigned __int64 v224; // rax
  struct LSN *v225; // r8
  int v226; // eax
  int v227; // ecx
  DirtyPageMgr *QuadPart; // rbx
  unsigned int Ahead; // r12d
  DirtyPageMgr *v230; // rcx
  unsigned __int64 v231; // rcx
  unsigned __int64 v232; // r8
  unsigned __int64 v233; // rax
  __int64 *v234; // rdx
  int v235; // ecx
  unsigned int v236; // eax
  __int64 v237; // rax
  __int64 FCB; // r12
  char *v239; // rdx
  struct LBH *v240; // r9
  __int64 v241; // r8
  int v242; // eax
  unsigned int v243; // ecx
  __int64 v244; // rbx
  __int64 v245; // rax
  __int64 v246; // r11
  unsigned int *RedoneLSN; // rax
  __int64 v248; // rcx
  int v249; // ecx
  int v250; // eax
  int v251; // edx
  int v252; // edx
  int v253; // edx
  char *v254; // rsi
  _DWORD *v255; // rbx
  RecoveryMgr *v256; // rdi
  struct RecXdes *v257; // r14
  __int64 v258; // r8
  unsigned int *v259; // rbx
  int v260; // ecx
  __int16 v261; // ax
  BOOL v262; // eax
  const struct SQLError *CurrentException; // rax
  int v264; // ecx
  int v265; // eax
  int v266; // edx
  __int64 v267; // rax
  __int64 v268; // rdx
  __int16 v269; // r8
  __int64 v270; // rcx
  __int64 v271; // rcx
  bool v272; // al
  BOOL v273; // eax
  char *v274; // rsi
  char v275; // r11
  bool v276; // r8
  struct LBH *v277; // rax
  __int64 v278; // rbx
  signed __int32 v279[8]; // [rsp+0h] [rbp-EE8h] BYREF
  struct DptEntry *v280; // [rsp+20h] [rbp-EC8h]
  struct Worker *v281; // [rsp+28h] [rbp-EC0h]
  struct LSN *v282; // [rsp+30h] [rbp-EB8h]
  struct ParallelRedoWorkerStats *v283; // [rsp+38h] [rbp-EB0h]
  __int64 v284; // [rsp+40h] [rbp-EA8h]
  int v285; // [rsp+48h] [rbp-EA0h]
  unsigned __int16 v286; // [rsp+50h] [rbp-E98h]
  struct LBH *v287; // [rsp+58h] [rbp-E90h]
  __int16 v288; // [rsp+60h] [rbp-E88h] BYREF
  unsigned __int16 v289; // [rsp+62h] [rbp-E86h] BYREF
  unsigned int v290; // [rsp+64h] [rbp-E84h]
  const unsigned __int8 *v291; // [rsp+68h] [rbp-E80h]
  __int64 v292; // [rsp+70h] [rbp-E78h]
  unsigned int v293; // [rsp+78h] [rbp-E70h]
  unsigned __int16 v294; // [rsp+7Ch] [rbp-E6Ch]
  unsigned __int64 v295; // [rsp+7Eh] [rbp-E6Ah]
  _TBYTE v296; // [rsp+86h] [rbp-E62h]
  int v297; // [rsp+90h] [rbp-E58h]
  char v298; // [rsp+98h] [rbp-E50h]
  struct RecXdes *v299; // [rsp+A0h] [rbp-E48h]
  __int16 v300; // [rsp+A8h] [rbp-E40h] BYREF
  unsigned __int16 v301; // [rsp+AAh] [rbp-E3Eh] BYREF
  int v302; // [rsp+ACh] [rbp-E3Ch]
  const unsigned __int8 *v303; // [rsp+B0h] [rbp-E38h]
  __int64 v304; // [rsp+B8h] [rbp-E30h]
  unsigned int v305; // [rsp+C0h] [rbp-E28h]
  unsigned __int16 v306; // [rsp+C4h] [rbp-E24h]
  unsigned __int64 v307; // [rsp+C6h] [rbp-E22h]
  _TBYTE v308; // [rsp+CEh] [rbp-E1Ah]
  int v309; // [rsp+D8h] [rbp-E10h]
  unsigned int v310; // [rsp+E0h] [rbp-E08h]
  __int16 v311; // [rsp+E4h] [rbp-E04h]
  void *Buf1; // [rsp+E8h] [rbp-E00h]
  char *v313; // [rsp+F0h] [rbp-DF8h]
  __int64 v314; // [rsp+F8h] [rbp-DF0h]
  unsigned int v315; // [rsp+108h] [rbp-DE0h]
  RecoveryMgr *v316; // [rsp+110h] [rbp-DD8h]
  char v317; // [rsp+118h] [rbp-DD0h]
  char v318; // [rsp+119h] [rbp-DCFh]
  unsigned int v319; // [rsp+11Ch] [rbp-DCCh] BYREF
  const struct LogRec *v320; // [rsp+120h] [rbp-DC8h]
  RecoveryMgr *v321; // [rsp+128h] [rbp-DC0h] BYREF
  unsigned int v322; // [rsp+130h] [rbp-DB8h] BYREF
  unsigned int v323; // [rsp+134h] [rbp-DB4h] BYREF
  unsigned int v324; // [rsp+138h] [rbp-DB0h] BYREF
  int v325; // [rsp+13Ch] [rbp-DACh]
  unsigned int v326; // [rsp+140h] [rbp-DA8h] BYREF
  unsigned int v327; // [rsp+144h] [rbp-DA4h] BYREF
  const struct LogRec *v328; // [rsp+148h] [rbp-DA0h] BYREF
  int v329; // [rsp+150h] [rbp-D98h] BYREF
  __int16 v330; // [rsp+154h] [rbp-D94h]
  int v331; // [rsp+158h] [rbp-D90h] BYREF
  __int16 v332; // [rsp+15Ch] [rbp-D8Ch]
  unsigned int v333; // [rsp+160h] [rbp-D88h] BYREF
  __int16 v334; // [rsp+164h] [rbp-D84h]
  struct BUF *v335; // [rsp+168h] [rbp-D80h] BYREF
  char v336; // [rsp+170h] [rbp-D78h]
  int v337; // [rsp+174h] [rbp-D74h]
  __int128 v338; // [rsp+180h] [rbp-D68h] BYREF
  int v339; // [rsp+190h] [rbp-D58h]
  __int16 v340; // [rsp+198h] [rbp-D50h]
  unsigned __int16 v341; // [rsp+1A0h] [rbp-D48h]
  unsigned int v342; // [rsp+1A4h] [rbp-D44h]
  int v343; // [rsp+1A8h] [rbp-D40h]
  unsigned int v344; // [rsp+1ACh] [rbp-D3Ch] BYREF
  unsigned int v345; // [rsp+1B0h] [rbp-D38h] BYREF
  unsigned int v346; // [rsp+1B4h] [rbp-D34h] BYREF
  unsigned int v347; // [rsp+1B8h] [rbp-D30h] BYREF
  int v348; // [rsp+1C0h] [rbp-D28h] BYREF
  __int16 v349; // [rsp+1C4h] [rbp-D24h]
  __int64 v350; // [rsp+1D0h] [rbp-D18h] BYREF
  __int64 v351; // [rsp+1D8h] [rbp-D10h]
  unsigned int v352; // [rsp+1E0h] [rbp-D08h] BYREF
  __int16 v353; // [rsp+1E4h] [rbp-D04h]
  int v354; // [rsp+1F0h] [rbp-CF8h] BYREF
  __int16 v355; // [rsp+1F4h] [rbp-CF4h]
  unsigned int v356; // [rsp+200h] [rbp-CE8h] BYREF
  __int16 v357; // [rsp+204h] [rbp-CE4h]
  __int64 v358; // [rsp+208h] [rbp-CE0h]
  __int64 v359; // [rsp+218h] [rbp-CD0h] BYREF
  char v360; // [rsp+220h] [rbp-CC8h]
  int v361; // [rsp+224h] [rbp-CC4h]
  _DWORD v362[2]; // [rsp+230h] [rbp-CB8h] BYREF
  __int16 v363; // [rsp+238h] [rbp-CB0h]
  unsigned int v364[2]; // [rsp+240h] [rbp-CA8h] BYREF
  int v365; // [rsp+248h] [rbp-CA0h]
  unsigned __int16 v366; // [rsp+24Ch] [rbp-C9Ch]
  unsigned int v367; // [rsp+24Eh] [rbp-C9Ah]
  unsigned __int16 v368; // [rsp+252h] [rbp-C96h]
  __int64 v369; // [rsp+258h] [rbp-C90h] BYREF
  __int16 v370; // [rsp+260h] [rbp-C88h]
  int v371; // [rsp+268h] [rbp-C80h]
  int v372; // [rsp+26Ch] [rbp-C7Ch]
  __int16 v373; // [rsp+270h] [rbp-C78h]
  __int64 v374; // [rsp+278h] [rbp-C70h] BYREF
  __int16 v375; // [rsp+280h] [rbp-C68h]
  __int64 v376; // [rsp+288h] [rbp-C60h] BYREF
  __int16 v377; // [rsp+290h] [rbp-C58h]
  __int64 v378; // [rsp+298h] [rbp-C50h] BYREF
  __int16 v379; // [rsp+2A0h] [rbp-C48h]
  __int64 v380; // [rsp+2A8h] [rbp-C40h] BYREF
  __int16 v381; // [rsp+2B0h] [rbp-C38h]
  unsigned int v382[2]; // [rsp+2B8h] [rbp-C30h] BYREF
  __int64 v383; // [rsp+2C0h] [rbp-C28h]
  LARGE_INTEGER PerformanceCount; // [rsp+2C8h] [rbp-C20h] BYREF
  LARGE_INTEGER v385; // [rsp+2D0h] [rbp-C18h] BYREF
  LARGE_INTEGER v386; // [rsp+2D8h] [rbp-C10h] BYREF
  LARGE_INTEGER v387; // [rsp+2E0h] [rbp-C08h] BYREF
  LARGE_INTEGER v388; // [rsp+2E8h] [rbp-C00h] BYREF
  LARGE_INTEGER v389; // [rsp+2F0h] [rbp-BF8h] BYREF
  unsigned int v390[4]; // [rsp+2F8h] [rbp-BF0h] BYREF
  int v391; // [rsp+308h] [rbp-BE0h] BYREF
  _QWORD v392[2]; // [rsp+310h] [rbp-BD8h] BYREF
  int v393; // [rsp+320h] [rbp-BC8h]
  _QWORD v394[2]; // [rsp+328h] [rbp-BC0h] BYREF
  _BYTE v395[16]; // [rsp+338h] [rbp-BB0h] BYREF
  int v396; // [rsp+348h] [rbp-BA0h] BYREF
  __int64 v397; // [rsp+350h] [rbp-B98h]
  __int64 v398; // [rsp+358h] [rbp-B90h]
  __int64 v399; // [rsp+360h] [rbp-B88h]
  __int64 v400; // [rsp+368h] [rbp-B80h]
  int v401; // [rsp+370h] [rbp-B78h] BYREF
  __int64 v402; // [rsp+378h] [rbp-B70h]
  __int64 v403; // [rsp+380h] [rbp-B68h]
  __int64 v404; // [rsp+388h] [rbp-B60h]
  __int64 v405; // [rsp+390h] [rbp-B58h]
  char *v406; // [rsp+398h] [rbp-B50h]
  struct BUF *v407; // [rsp+3A0h] [rbp-B48h]
  __int64 v408; // [rsp+3A8h] [rbp-B40h]
  char *v409; // [rsp+3B0h] [rbp-B38h]
  __int64 v410; // [rsp+3B8h] [rbp-B30h]
  __int64 v411; // [rsp+3C0h] [rbp-B28h]
  __int64 v412; // [rsp+3C8h] [rbp-B20h]
  char *v413; // [rsp+3D0h] [rbp-B18h]
  int *v414; // [rsp+3D8h] [rbp-B10h]
  char *v415; // [rsp+3E0h] [rbp-B08h]
  unsigned int *v416; // [rsp+3E8h] [rbp-B00h]
  struct BUF *v417; // [rsp+3F0h] [rbp-AF8h]
  __int64 v418; // [rsp+3F8h] [rbp-AF0h]
  struct BUF *v419; // [rsp+400h] [rbp-AE8h]
  __int64 v420; // [rsp+408h] [rbp-AE0h]
  unsigned int *v421; // [rsp+410h] [rbp-AD8h]
  __int64 v422; // [rsp+418h] [rbp-AD0h]
  __int64 v423; // [rsp+420h] [rbp-AC8h]
  unsigned __int8 *v424; // [rsp+428h] [rbp-AC0h]
  char *v425; // [rsp+430h] [rbp-AB8h]
  RecoveryUnit *v426; // [rsp+438h] [rbp-AB0h]
  __int64 v427; // [rsp+440h] [rbp-AA8h]
  char *v428; // [rsp+448h] [rbp-AA0h]
  const struct LogRec **v429; // [rsp+450h] [rbp-A98h]
  unsigned __int64 v430; // [rsp+458h] [rbp-A90h]
  __int64 v431; // [rsp+460h] [rbp-A88h]
  int *v432; // [rsp+468h] [rbp-A80h]
  char *v433; // [rsp+470h] [rbp-A78h]
  int *v434; // [rsp+478h] [rbp-A70h]
  _DWORD *v435; // [rsp+480h] [rbp-A68h]
  char *v436; // [rsp+488h] [rbp-A60h]
  char *v437; // [rsp+490h] [rbp-A58h]
  _BYTE v438[40]; // [rsp+498h] [rbp-A50h] BYREF
  char v439[8]; // [rsp+4C0h] [rbp-A28h] BYREF
  __int16 v440; // [rsp+4C8h] [rbp-A20h]
  __int16 v441; // [rsp+4CAh] [rbp-A1Eh]
  int v442; // [rsp+4D0h] [rbp-A18h]
  int **v443; // [rsp+4D8h] [rbp-A10h]
  char *v444; // [rsp+4E0h] [rbp-A08h]
  __int64 v445; // [rsp+4E8h] [rbp-A00h]
  int *v446; // [rsp+4F0h] [rbp-9F8h] BYREF
  int v447; // [rsp+4F8h] [rbp-9F0h]
  __int16 v448; // [rsp+4FCh] [rbp-9ECh]
  __int16 v449; // [rsp+4FEh] [rbp-9EAh]
  __int64 v450; // [rsp+500h] [rbp-9E8h]
  int v451; // [rsp+508h] [rbp-9E0h]
  __int16 v452; // [rsp+50Ch] [rbp-9DCh]
  __int16 v453; // [rsp+50Eh] [rbp-9DAh]
  char v454; // [rsp+510h] [rbp-9D8h] BYREF
  int v455; // [rsp+710h] [rbp-7D8h]
  int v456; // [rsp+714h] [rbp-7D4h]
  __int64 v457; // [rsp+718h] [rbp-7D0h]
  int v458; // [rsp+720h] [rbp-7C8h] BYREF
  unsigned __int64 v459; // [rsp+724h] [rbp-7C4h]
  int v460; // [rsp+72Ch] [rbp-7BCh]
  int v461; // [rsp+730h] [rbp-7B8h]
  char v462[8]; // [rsp+740h] [rbp-7A8h] BYREF
  int v463; // [rsp+748h] [rbp-7A0h]
  int v464; // [rsp+750h] [rbp-798h]
  int **v465; // [rsp+758h] [rbp-790h]
  char *v466; // [rsp+760h] [rbp-788h]
  __int64 v467; // [rsp+768h] [rbp-780h]
  int *v468; // [rsp+770h] [rbp-778h] BYREF
  int v469; // [rsp+778h] [rbp-770h]
  int v470; // [rsp+77Ch] [rbp-76Ch]
  __int64 v471; // [rsp+780h] [rbp-768h]
  int v472; // [rsp+788h] [rbp-760h]
  int v473; // [rsp+78Ch] [rbp-75Ch]
  char v474; // [rsp+790h] [rbp-758h] BYREF
  __int64 v475; // [rsp+990h] [rbp-558h]
  __int64 v476; // [rsp+998h] [rbp-550h]
  int v477; // [rsp+9A0h] [rbp-548h] BYREF
  unsigned __int64 v478; // [rsp+9A4h] [rbp-544h]
  int v479; // [rsp+9ACh] [rbp-53Ch]
  int v480; // [rsp+9B0h] [rbp-538h]
  _BYTE v481[80]; // [rsp+9C0h] [rbp-528h] BYREF
  __int64 v482; // [rsp+A10h] [rbp-4D8h] BYREF
  __int16 v483; // [rsp+A18h] [rbp-4D0h]
  __int64 v484; // [rsp+A20h] [rbp-4C8h] BYREF
  __int16 v485; // [rsp+A28h] [rbp-4C0h]
  int v486; // [rsp+A2Ch] [rbp-4BCh]
  __int64 v487; // [rsp+A30h] [rbp-4B8h] BYREF
  __int16 v488; // [rsp+A38h] [rbp-4B0h]
  int v489; // [rsp+A3Ch] [rbp-4ACh]
  _BYTE v490[16]; // [rsp+A40h] [rbp-4A8h] BYREF
  _BYTE v491[16]; // [rsp+A50h] [rbp-498h] BYREF
  __int128 Buf2; // [rsp+A60h] [rbp-488h] BYREF
  __int128 v493; // [rsp+A70h] [rbp-478h]
  __int128 v494; // [rsp+A80h] [rbp-468h]
  wchar_t v495[48]; // [rsp+A90h] [rbp-458h] BYREF
  wchar_t v496[48]; // [rsp+AF0h] [rbp-3F8h] BYREF
  wchar_t v497[48]; // [rsp+B50h] [rbp-398h] BYREF
  wchar_t v498[48]; // [rsp+BB0h] [rbp-338h] BYREF
  wchar_t v499[48]; // [rsp+C10h] [rbp-2D8h] BYREF
  wchar_t v500[56]; // [rsp+C70h] [rbp-278h] BYREF
  wchar_t v501[56]; // [rsp+CE0h] [rbp-208h] BYREF
  wchar_t v502[56]; // [rsp+D50h] [rbp-198h] BYREF
  wchar_t v503[56]; // [rsp+DC0h] [rbp-128h] BYREF
  wchar_t v504[56]; // [rsp+E30h] [rbp-B8h] BYREF

  v420 = -2;
  v4 = a4;
  v287 = a4;
  LOBYTE(v286) = a3;
  v5 = a2;
  v320 = a2;
  v6 = this;
  v321 = this;
  v316 = this;
  *(_QWORD *)v364 = this;
  v328 = a2;
  v7 = 0;
  v325 = 0;
  v8 = 0;
  v299 = 0;
  v9 = 0;
  if ( (qword_10317AD33 & 0x100000) != 0
    || (v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
        *(_QWORD *)v10)
    && (v11 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v10 + 56LL)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v11, 0xDACu) )
  {
    v12 = 0;
    while ( 1 )
    {
      if ( (qword_10317AD33 & 0x100000) == 0 )
      {
        v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( !*(_QWORD *)v13 )
          break;
        v14 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v13 + 56LL);
        if ( !v14 || !CSessionTraceFlags::CheckSessionTraceInternal(v14, 0xDACu) )
          break;
      }
      if ( v12 == 12 * (v12 / 12) )
        log_unlocalized_systemmetadata(
          L"[%ls] Redo on database '%.*ls' is suspended since traceflag is enabled",
          L"RecoveryMgr::RedoLogRecord",
          *(unsigned int *)(*(_QWORD *)(*(_QWORD *)v6 + 1712LL) + 928LL),
          *(_QWORD *)(*(_QWORD *)v6 + 1712LL) + 936LL);
      ++v12;
      v401 = 4194400;
      v402 = 0;
      v404 = 0;
      v403 = 0;
      v405 = 0;
      if ( (unsigned int)SOS_Task::Sleep(5000, &v401) == 2 )
      {
        LOBYTE(v248) = -122;
        RaiseExecutionAbortedError(v248);
      }
    }
    v4 = v287;
  }
  if ( (*((_DWORD *)v6 + 9) & 0x80) != 0 )
  {
    v15 = *((_BYTE *)v5 + 22);
    if ( v15 >= 0x7Fu && v15 != 0x99 && v15 != 0x86 )
      utassert_fail(
        1u,
        "!IsForeignLogApply () || lp->IsPageOp () || LOP_END_CKPT == lp->log_op || LOP_CREATE_FILE == lp->log_op",
        "recovery.cpp",
        12417,
        0);
  }
  if ( (dword_10317F71C & 0x20000000) != 0 )
  {
    v463 = 0x20000;
    v464 = 0;
    v465 = &v468;
    v466 = &v474;
    v475 = 0;
    v467 = 0;
    v476 = 0;
    v468 = &v477;
    v469 = 28;
    v470 = 1;
    v471 = 0;
    v472 = 0;
    v473 = 4;
    v477 = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)v6 + 1712LL) + 40LL);
    v478 = *((unsigned int *)v6 + 5534) | ((unsigned __int64)*((unsigned int *)v6 + 5533) << 32);
    v479 = *((unsigned __int16 *)v6 + 11070);
    v16 = *((_BYTE *)v5 + 22);
    v480 = v16;
    v17 = 0;
    v18 = &logOperations;
    v19 = &logOperations;
    while ( *(_BYTE *)v19 != v16 )
    {
      if ( *(_BYTE *)v19 <= v16 )
      {
        ++v17;
        v19 += 2;
        if ( v17 < 0x57 )
          continue;
      }
      v20 = 0;
LABEL_22:
      v21 = 0;
      goto LABEL_23;
    }
    v20 = *((_QWORD *)v19 + 1);
    if ( !v20 )
      goto LABEL_22;
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(v20 + 2 * v22) );
    v21 = 2 * v22;
LABEL_23:
    v471 = v20;
    v472 = v21;
    XeSqlPkg::redo_single_record::Publish((XeSqlPkg::redo_single_record *)v462);
  }
  else
  {
    v18 = &logOperations;
  }
  if ( !(_BYTE)v286 )
  {
    if ( v4 )
    {
      v23 = *((_QWORD *)v6 + 4234);
      if ( v23 )
      {
        if ( (*(_BYTE *)(v23 + 528) & 1) != 0 && (*((_WORD *)v6 + 11070) == 1 || !*(_QWORD *)(v23 + 512)) )
        {
          v24 = LogCacheMgr::PutLogBlock(*(LogCacheMgr **)(v23 + 456), v287);
          *(_QWORD *)(v23 + 512) = v24;
          *(_BYTE *)(v23 + 520) = 0;
          if ( !v24 )
          {
            log_unlocalized_systemmetadata(
              L"Failed to EnqueueLogBlock at lsn %x:%x:%x",
              *((unsigned int *)v6 + 5533),
              *((unsigned int *)v6 + 5534),
              *((unsigned __int16 *)v6 + 11070));
            RecoveryMgr::ShutdownParallelRedoMgr(v6, 0);
            *(_BYTE *)(*(_QWORD *)v6 + 26105LL) = 0;
          }
        }
      }
    }
  }
  if ( (*((_BYTE *)v5 + 14) & 2) != 0 && (*((_DWORD *)v6 + 9) & 0x80) == 0 )
  {
    v348 = *((_DWORD *)v5 + 4);
    v349 = *((_WORD *)v5 + 10);
    Xdes = RecXdesTable::FindXdes((char *)v6 + 23456, &v348);
    v27 = (struct RecXdes *)Xdes;
    v8 = (struct RecXdes *)Xdes;
    v299 = (struct RecXdes *)Xdes;
    if ( Xdes )
    {
      v28 = *(_DWORD *)(Xdes + 60) - 10;
      v299 = (struct RecXdes *)Xdes;
      if ( (v28 & 0xFFFFFFFD) != 0 && (*(_BYTE *)(*(_QWORD *)v6 + 7376LL) & 0x40) == 0 )
      {
        v9 = *(_QWORD *)(Xdes + 128);
        if ( (!(_BYTE)v286 || !*((_QWORD *)v6 + 4234) || (*((_DWORD *)v6 + 9) & 0x80) != 0)
          && (unsigned int)RecoveryUnit::IsRecoveryReacquiringLocks(*(RecoveryUnit **)v6)
          && (*((_DWORD *)v6 + 9) & 0x80) == 0 )
        {
          LogLockCollection::LogLockCollection((LogLockCollection *)v481, v5);
          if ( *((_BYTE *)v6 + 33904) && !RecoveryMgr::IsXdesTranActive(v6, (const struct LogRec *)((char *)v5 + 16)) )
            *((_DWORD *)v27 + 71) = 1;
          v394[0] = &LogLockCollectionAcquire::`vftable';
          v394[1] = v9;
          v29 = 0;
          v30 = 0;
          if ( *((_DWORD *)v27 + 22) != 3 )
          {
            LOBYTE(v29) = *((_DWORD *)v27 + 71) != 0;
            v30 = v29;
          }
          LogLockCollection::ApplyLocks(
            (LogLockCollection *)v481,
            *(_WORD *)(*(_QWORD *)(v9 + 48) + 1720LL),
            (struct LogLockCollectionCallback *)v394,
            v30);
        }
        if ( !*((_DWORD *)v27 + 71) )
          XdesRMReadWrite::RedoReserveForUndo((XdesRMReadWrite *)v9, v5, (RecoveryMgr *)((char *)v6 + 22132));
        v299 = v8;
        if ( *(_BYTE *)(*(_QWORD *)v6 + 7390LL) )
        {
          v299 = v8;
          if ( XDES::ShouldLogToSLog(v5, (const struct XDES *)v26) )
          {
            v299 = v8;
            if ( (*((_WORD *)v5 + 7) & 0x100) != 0 )
            {
              v299 = v8;
              if ( (*((_DWORD *)v6 + 9) & 0x80) == 0 )
              {
                v26 = *((_QWORD *)v6 + 4236);
                if ( v26 || (v299 = v8, !(_BYTE)v286) )
                {
                  XdesRMReadWrite::AttachSLogRecForUndo((XdesRMReadWrite *)v9, (struct SLogRec *)v26);
                  v26 = **((_QWORD **)v6 + 4236);
                  v31 = *(_BYTE *)(v26 + 22);
                  if ( v31 == -33 || (v8 = v27, v299 = v27, v31 == -32) )
                  {
                    if ( (*(_BYTE *)(v26 + 14) & 1) != 0 )
                    {
                      v32 = *(_QWORD **)(v9 + 9296);
                      *(_QWORD *)(v9 + 9296) = v32[1];
                      *v32 = v26;
                      v32[1] = 0;
                      if ( *(_QWORD *)(v9 + 9280) )
                        *(_QWORD *)(*(_QWORD *)(v9 + 9288) + 8LL) = v32;
                      else
                        *(_QWORD *)(v9 + 9280) = v32;
                      *(_QWORD *)(v9 + 9288) = v32;
                      v8 = v27;
                      v299 = v27;
                    }
                    else
                    {
                      v33 = *(_QWORD *)(v9 + 9280);
                      v8 = v27;
                      v299 = v27;
                      if ( v33 )
                      {
                        v299 = v27;
                        v34 = v33;
                        do
                        {
                          v34 = *(_QWORD *)(v34 + 8);
                          operator delete(*(void **)(v9 + 9280), 0x10u);
                          *(_QWORD *)(v9 + 9280) = v34;
                        }
                        while ( v34 );
                        v5 = v320;
                      }
                      *(_QWORD *)(v9 + 9288) = 0;
                      v35 = (struct IMemObj *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v9 + 48)
                                                                                              + 1744LL)
                                                                                + 120LL))(*(_QWORD *)(*(_QWORD *)(v9 + 48) + 1744LL));
                      v36 = operator new(0x10u, v35, "sql\\ntdbms\\storeng\\dfs\\trans\\xdes.cpp", 8389, 5u);
                      *v36 = 0;
                      v36[1] = *(_QWORD *)(v9 + 9296);
                      *(_QWORD *)(v9 + 9296) = v36;
                    }
                  }
                  *((_QWORD *)v6 + 4236) = 0;
                }
              }
            }
          }
        }
        if ( (*((_BYTE *)v5 + 14) & 1) != 0 )
        {
          v37 = *((_QWORD *)v6 + 2876);
          if ( v37 >= 2 )
            *((_QWORD *)v6 + 2876) = v37 - 2;
          if ( !byte_10316EAE9
            && (qword_10317AD6F & 0x800000000000000LL) == 0
            && (*((_BYTE *)v5 + 15) & 1) != ((*((_DWORD *)v8 + 14) & 0x240) == 64) )
          {
            v38 = *((_BYTE *)v5 + 22);
            if ( v38 != -12 && v38 != -115 )
              utassert_fail(
                1u,
                "CFeatureSwitchesMin::GetCurrentInstance()->FSkipCtrRedoShortTranAssertEnabled() || (!!lp->IsFlagOn (LogR"
                "ec::LOG_TO_SLOG)) == recXdes->DoesXactSupportCTR () || lp->GetOpCode () == LOP_CTR_NEST_ABORT || lp->Get"
                "OpCode () == LOP_LOCK_XACT",
                "recovery.cpp",
                12599,
                0);
          }
        }
        if ( *((_BYTE *)v6 + 24536) || (v39 = *((_QWORD *)v6 + 2780)) == 0 )
        {
LABEL_90:
          if ( !*((_BYTE *)v6 + 24536) )
            goto LABEL_94;
          goto LABEL_91;
        }
        LOBYTE(v26) = 1;
LABEL_89:
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 64LL))(v39, v26);
        goto LABEL_90;
      }
    }
  }
  if ( !*((_BYTE *)v6 + 24536) )
  {
    v39 = *((_QWORD *)v6 + 2780);
    if ( !v39 )
      goto LABEL_94;
    v26 = 0;
    goto LABEL_89;
  }
LABEL_91:
  if ( v8 )
  {
    v40 = *((_QWORD *)v8 + 16);
    if ( v40 )
    {
      *(_QWORD *)(v40 + 8732) = *(_QWORD *)((char *)v8 + 76);
      *(_WORD *)(v40 + 8740) = *((_WORD *)v8 + 42);
    }
  }
LABEL_94:
  if ( *((_BYTE *)v5 + 22) >= 0x7Fu )
  {
    RecoveryMgr::RedoLogicalOp(v6, v5, v286, v8);
    goto LABEL_639;
  }
  Buf1 = v5;
  v313 = (char *)v5;
  if ( !(unsigned int)RecoveryUnit::IsRecoveryReacquiringLocks(*(RecoveryUnit **)v6) )
  {
    v42 = *((_BYTE *)v5 + 23);
    if ( v42 == 11 )
    {
      if ( v41 != 4 )
        goto LABEL_106;
      v43 = *((_WORD *)v5 + 15) == 0;
    }
    else
    {
      if ( v42 != 8 || v41 != 7 )
        goto LABEL_106;
      v43 = *((_WORD *)v5 + 15) == 1;
    }
    if ( v43 && (*((_BYTE *)v5 + 14) & 1) == 0 )
      RecoveryMgr::AcquireAllocationLock(v6, v5, (RecoveryMgr *)((char *)v6 + 22132));
  }
LABEL_106:
  v44 = (unsigned int *)((char *)v5 + 24);
  v356 = *((_DWORD *)v5 + 6);
  v357 = *((_WORD *)v5 + 14);
  Entry = DirtyPageTablePartition::FindEntry(
            *(DirtyPageTablePartition **)(**((_QWORD **)v6 + 3056)
                                        + 8LL * (v356 % *(_DWORD *)(*((_QWORD *)v6 + 3056) + 8LL))),
            (const struct PageId *)&v356);
  v287 = Entry;
  if ( dword_103172528 )
  {
    v46 = *(RecoveryUnit **)v6;
    v314 = *(_QWORD *)(*(_QWORD *)v6 + 27168LL);
    if ( *((_WORD *)v46 + 13588) || v314 )
    {
      v47 = 0;
      v48 = 0;
      while ( 1 )
      {
        v49 = *(RecoveryUnit **)v6;
        v314 = *(_QWORD *)(*(_QWORD *)v6 + 27168LL);
        if ( *((_WORD *)v49 + 13588) != *((_WORD *)v6 + 11070) )
          break;
        v50 = *((_DWORD *)v6 + 5533);
        if ( v314 != *(_QWORD *)((char *)v6 + 22132) )
          break;
        v48 = 1;
        if ( v47 == 12 * (v47 / 12) )
        {
          v51 = *((_QWORD *)v49 + 214);
          LODWORD(v282) = *((unsigned __int16 *)v6 + 11070);
          LODWORD(v281) = *((_DWORD *)v6 + 5534);
          LODWORD(v280) = v50;
          log_unlocalized_systemmetadata(
            L"[%ls] Redo on database '%.*ls' will be skipped at LSN 0x%x:0x%x:0x%x",
            L"RecoveryMgr::RedoLogRecord",
            *(unsigned int *)(v51 + 928),
            v51 + 936,
            v280,
            v281,
            v282);
        }
        ++v47;
        v396 = 4194400;
        v397 = 0;
        v399 = 0;
        v398 = 0;
        v400 = 0;
        if ( (unsigned int)SOS_Task::Sleep(5000, &v396) == 2 )
        {
          LOBYTE(v52) = -122;
          RaiseExecutionAbortedError(v52);
        }
        RecoveryUnit::SetupRedoSkipLsnFromWinfab(*(RecoveryUnit **)v6);
      }
      v43 = v48 == 0;
      v5 = v320;
      v44 = (unsigned int *)((char *)v320 + 24);
      if ( !v43 )
      {
        v53 = *((_QWORD *)v49 + 214);
        LODWORD(v282) = *((unsigned __int16 *)v6 + 11070);
        LODWORD(v281) = *((_DWORD *)v6 + 5534);
        LODWORD(v280) = *((_DWORD *)v6 + 5533);
        log_unlocalized_systemmetadata(
          L"[%ls] Redo on database '%.*ls' is skipped at LSN 0x%x:0x%x:0x%x",
          L"RecoveryMgr::RedoLogRecord",
          *(unsigned int *)(v53 + 928),
          v53 + 936,
          v280,
          v281,
          v282);
        goto LABEL_639;
      }
      Entry = v287;
    }
  }
  if ( !Entry )
    goto LABEL_587;
  if ( !(unsigned int)RecoveryMgr::SkipParallelRedo(v6, v5) )
  {
LABEL_138:
    if ( *((_BYTE *)v5 + 22) == 16 )
      goto LABEL_142;
    goto LABEL_139;
  }
  v54 = *((_DWORD *)Entry + 12);
  do
  {
    v55 = v54 & 0xFFFFFFFE;
    v314 = *(_QWORD *)((char *)Entry + 36);
    v56 = *((_WORD *)Entry + 22);
    _InterlockedOr(v279, 0);
    v54 = *((_DWORD *)Entry + 12);
  }
  while ( v55 != v54 );
  v57 = *((_DWORD *)v6 + 5533);
  if ( v57 >= (unsigned int)v314
    && (v57 != (_DWORD)v314
     || *((_DWORD *)v6 + 5534) >= HIDWORD(v314)
     && (*((_DWORD *)v6 + 5534) != HIDWORD(v314) || *((_WORD *)v6 + 11070) >= v56)) )
  {
    goto LABEL_137;
  }
  v58 = *(_QWORD *)(*(_QWORD *)v6 + 1712LL);
  if ( (*(_BYTE *)(v58 + 60) & 1) == 0 || *(_QWORD *)(v58 + 640) || !*((_BYTE *)v6 + 24536) )
    goto LABEL_587;
  if ( !*v44 || *v44 == 9 && *((_WORD *)v44 + 2) == 1 )
  {
LABEL_137:
    Buf1 = v313;
    goto LABEL_138;
  }
  if ( *((_BYTE *)v5 + 22) != 19 )
  {
LABEL_587:
    if ( (qword_10317AD29 & 8) != 0 )
      goto LABEL_591;
    v221 = *(_QWORD *)(SystemThread_TlsOffset
                     + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex));
    if ( !v221 || (v222 = **(struct CSessionTraceFlags ***)(v221 + 56)) == 0 )
    {
LABEL_599:
      if ( *((_BYTE *)v6 + 24536) || (*((_BYTE *)v5 + 14) & 1) != 0 )
      {
        if ( !Entry )
          goto LABEL_622;
      }
      else if ( !Entry )
      {
        if ( v9 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v9 + 136LL))(v9) )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v388);
            QuadPart = (DirtyPageMgr *)v388.QuadPart;
          }
          else
          {
            QuadPart = MEMORY[0x7FFE0008];
          }
          LODWORD(v321) = *v44;
          WORD2(v321) = *((_WORD *)v44 + 2);
          Ahead = BPool::PessimisticReadAhead(
                    qword_10317B628,
                    *(struct RecoveryUnit **)v6,
                    (const struct PageId *)&v321,
                    0);
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v389);
            v230 = (DirtyPageMgr *)v389.QuadPart;
          }
          else
          {
            v230 = MEMORY[0x7FFE0008];
          }
          if ( v230 < QuadPart )
          {
            v231 = 0;
            v232 = 0;
          }
          else
          {
            v231 = v230 - QuadPart;
            v232 = v231;
            if ( v231 == -1 )
            {
              v233 = -1;
LABEL_617:
              ++*((_QWORD *)v6 + 2907);
              if ( !Ahead )
                ++*((_QWORD *)v6 + 2908);
              if ( v233 )
                ++*((_QWORD *)v6 + 2910);
              *((_QWORD *)v6 + 2909) += v232;
              goto LABEL_622;
            }
          }
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
            v233 = 1000 * v231 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
          else
            v233 = v231 / 0x2710;
          goto LABEL_617;
        }
LABEL_622:
        v484 = 0;
        v485 = 0;
        v486 = 0;
        v234 = &v484;
        goto LABEL_623;
      }
      v487 = *(_QWORD *)((char *)Entry + 36);
      v488 = *((_WORD *)Entry + 22);
      v489 = *((_DWORD *)Entry + 12);
      v234 = &v487;
LABEL_623:
      v235 = *((_DWORD *)v234 + 3);
      v374 = *v234;
      v375 = *((_WORD *)v234 + 4);
      do
      {
        v236 = v235 & 0xFFFFFFFE;
        _InterlockedOr(v279, 0);
        v235 = *((_DWORD *)v234 + 3);
      }
      while ( v236 != v235 );
      v380 = *(_QWORD *)((char *)v6 + 22132);
      v381 = *((_WORD *)v6 + 11070);
      LOBYTE(v285) = 0;
      LOBYTE(v284) = 1;
      LOBYTE(v283) = 0;
      LOBYTE(v282) = 0;
      LOBYTE(v281) = 0;
      LOBYTE(v280) = 1;
      RecoveryMgr::RedoRbAddElement(
        v6,
        v5,
        &v380,
        &v374,
        (_DWORD)v280,
        (_DWORD)v281,
        (_DWORD)v282,
        (_DWORD)v283,
        v284,
        v285);
      v237 = *(_QWORD *)(*(_QWORD *)v6 + 1712LL);
      if ( (*(_BYTE *)(v237 + 60) & 1) != 0 && !*(_QWORD *)(v237 + 640) )
      {
        FCB = FileMgr::GetFCB(*(_QWORD *)(*(_QWORD *)v6 + 1696LL), *((unsigned __int16 *)v5 + 14), 0);
        if ( (*(_BYTE *)(FCB + 100) & 0x40) == 0 )
        {
          (*(void (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(*(_QWORD *)v6 + 1736LL) + 368LL))(
            *(_QWORD *)(*(_QWORD *)v6 + 1736LL),
            v490);
          v239 = (char *)v6 + 22132;
          if ( *((_BYTE *)v5 + 22) == 16 )
            RbIoFsUpdateSafeLsn(FCB, v239);
          else
            RbIoFsRegisterPageLsn(FCB, v239, v490, *v44);
        }
      }
      v240 = v287;
      if ( v287 )
      {
        v241 = *((_QWORD *)v6 + 3056);
        if ( v241 )
          v7 = *(struct LSN **)(*(_QWORD *)v241 + 8LL * (unsigned int)(*((_DWORD *)v287 + 4) % *(_DWORD *)(v241 + 8)));
        v242 = *((_DWORD *)v287 + 12);
        do
        {
          v243 = v242 & 0xFFFFFFFE;
          v376 = *(_QWORD *)((char *)v240 + 36);
          v377 = *((_WORD *)v240 + 22);
          _InterlockedOr(v279, 0);
          v242 = *((_DWORD *)v240 + 12);
        }
        while ( v243 != v242 );
        DptEntry::UpdateFirstLsn(v240, &v376, v7);
      }
      goto LABEL_639;
    }
    if ( CSessionTraceFlags::CheckSessionTraceInternal(v222, 0xD4Bu) )
    {
LABEL_591:
      v327 = 100;
      GetLsnAsDecimalString((RecoveryMgr *)((char *)v6 + 22132), &v327, v504);
      LSN::FormatAsHexString((LSN *)((char *)v6 + 22132), v499, v364);
      v223 = *((_BYTE *)v5 + 22);
      v224 = 0;
      while ( *(_BYTE *)v18 != v223 )
      {
        if ( *(_BYTE *)v18 <= v223 )
        {
          ++v224;
          v18 += 2;
          if ( v224 < 0x57 )
            continue;
        }
        v225 = 0;
        goto LABEL_597;
      }
      v225 = (struct LSN *)*((_QWORD *)v18 + 1);
LABEL_597:
      v226 = *((unsigned __int16 *)v5 + 14);
      v227 = *((unsigned __int16 *)v5 + 10);
      LODWORD(v284) = *v44;
      LODWORD(v283) = v226;
      v282 = v225;
      LODWORD(v281) = *((_DWORD *)v5 + 4);
      LODWORD(v280) = v227;
      traceprint(
        L"REDO LSN %.*ls (0x%ls), XdesId 0x%04lx:%08lx skipped %ls on page %d:%d due to DPT logic.\n",
        (unsigned __int64)v327 >> 1,
        v504,
        v499,
        v280,
        v281,
        v225,
        v283,
        v284);
    }
    Entry = v287;
    goto LABEL_599;
  }
  Buf1 = v313;
LABEL_139:
  if ( (*(_BYTE *)(*(_QWORD *)v6 + 7376LL) & 1) != 0 || *(_DWORD *)(*(_QWORD *)v6 + 1652LL) == 5 )
  {
    utassert_fail(
      1u,
      "(LOP_FILE_HDR_MODIFY == lp->GetOpCode ()) || m_recoveryUnit->IsIntendedUpdateable ()",
      "recovery.cpp",
      12821,
      0);
    Entry = v287;
  }
LABEL_142:
  if ( *((_DWORD *)v6 + 6140) )
  {
    if ( !v8 || (v59 = 0, *((_DWORD *)v8 + 22) != 3) )
      v59 = 1;
  }
  else
  {
    v59 = 0;
  }
  *((_DWORD *)v6 + 6141) = v59;
  v60 = *((_DWORD *)Entry + 14);
  if ( *((_DWORD *)Entry + 18) != 1 )
    v60 = (unsigned __int16)v60;
  if ( v60 && (unsigned int)RecoveryMgr::CanDeferAfterError(v6, (struct LBH *)((char *)Entry + 56), v8) )
  {
    if ( (qword_10317AD29 & 8) != 0
      || (v61 = *(_QWORD *)(SystemThread_TlsOffset
                          + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
      && (v62 = **(struct CSessionTraceFlags ***)(v61 + 56)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v62, 0xD4Bu) )
    {
      v323 = 100;
      GetLsnAsDecimalString((RecoveryMgr *)((char *)v6 + 22132), &v323, v500);
      LSN::FormatAsHexString((LSN *)((char *)v6 + 22132), v495, v382);
      v63 = *((_BYTE *)v5 + 22);
      v64 = 0;
      while ( *(_BYTE *)v18 != v63 )
      {
        if ( *(_BYTE *)v18 <= v63 )
        {
          ++v64;
          v18 += 2;
          if ( v64 < 0x57 )
            continue;
        }
        goto LABEL_161;
      }
      v7 = (struct LSN *)*((_QWORD *)v18 + 1);
LABEL_161:
      v65 = *((unsigned __int16 *)v5 + 14);
      v66 = *((unsigned __int16 *)v5 + 10);
      LODWORD(v284) = *v44;
      LODWORD(v283) = v65;
      v282 = v7;
      LODWORD(v281) = *((_DWORD *)v5 + 4);
      LODWORD(v280) = v66;
      traceprint(
        L"REDO LSN %.*ls (0x%ls), XdesId 0x%04lx:%08lx skipped %ls on bad page %d:%d.\n",
        (unsigned __int64)v323 >> 1,
        v500,
        v495,
        v280,
        v281,
        v7,
        v283,
        v284);
    }
    v67 = v287;
    v68 = *((_DWORD *)v287 + 12);
    do
    {
      v69 = v68 & 0xFFFFFFFE;
      v378 = *(_QWORD *)((char *)v67 + 36);
      v379 = *((_WORD *)v67 + 22);
      _InterlockedOr(v279, 0);
      v68 = *((_DWORD *)v67 + 12);
    }
    while ( v69 != v68 );
    v369 = *(_QWORD *)((char *)v6 + 22132);
    v370 = *((_WORD *)v6 + 11070);
    LOBYTE(v285) = 0;
    LOBYTE(v284) = 0;
    LOBYTE(v283) = 0;
    LOBYTE(v282) = 0;
    LOBYTE(v281) = 0;
    LOBYTE(v280) = 1;
    RecoveryMgr::RedoRbAddElement(
      v6,
      v5,
      &v369,
      &v378,
      (_DWORD)v280,
      (_DWORD)v281,
      (_DWORD)v282,
      (_DWORD)v283,
      v284,
      v285);
    goto LABEL_639;
  }
  v70 = (int (*)(int, int, int, int, char *))DeferExceptionHandler;
  if ( !*((_DWORD *)v6 + 6141) )
    v70 = (int (*)(int, int, int, int, char *))RecoveryExceptionHandler;
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v438, 0, 0, 0, v70, 0);
    v71 = *(RecoveryUnit **)v316;
    if ( ((*((_DWORD *)v6 + 9) & 0x80) != 0 || *((_BYTE *)v71 + 8300)) && *((_BYTE *)v5 + 22) == 16 )
    {
      v421 = v44;
      v365 = *v44;
      v366 = *((_WORD *)v44 + 2);
      v422 = *((_QWORD *)v71 + 212);
      v72 = FileMgr::GetFCB(v422, v366, 1);
      v423 = v72;
      if ( !v72 || (*(_BYTE *)(v72 + 100) & 0x40) == 0 )
      {
        v73 = (ParallelRedoManager *)*((_QWORD *)v6 + 4234);
        if ( v73 )
          ParallelRedoManager::DrainRedoWorkers(v73, L"LOP_FILE_HDR_MODIFY", (RecoveryMgr *)((char *)v6 + 22132));
      }
      RecoveryMgr::RedoFileHeaderModify(v6, v5, (RecoveryMgr *)((char *)v6 + 22132), v287);
      v315 = 0;
LABEL_209:
      ExcHandler::~ExcHandler((ExcHandler *)v438);
      goto LABEL_709;
    }
    LODWORD(v493) = 0;
    WORD2(v493) = 0;
    LOBYTE(v286) = byte_10316E8C1;
    v317 = byte_10316E8C1;
    if ( byte_10316E8C1
      && (RedoValidationBuffer = RecoveryMgr::GetRedoValidationBuffer(v6),
          v424 = RedoValidationBuffer,
          Buf2 = *(_OWORD *)v5,
          v493 = *((_OWORD *)v5 + 1),
          v494 = *((_OWORD *)v5 + 2),
          RedoValidationBuffer) )
    {
      TotalLength = LogRec::GetTotalLength(v5);
      v342 = TotalLength;
      if ( *((_BYTE *)v5 + 22) == 10 )
      {
        if ( TotalLength < 0x34 )
          TotalLength = 52;
        v342 = TotalLength;
      }
      memcpy_s(RedoValidationBuffer, 0x6000u, v5, TotalLength);
      v76 = (const struct PageLog *)RedoValidationBuffer;
      Buf1 = RedoValidationBuffer;
      v313 = (char *)RedoValidationBuffer;
    }
    else
    {
      v76 = (const struct PageLog *)Buf1;
    }
    v298 = 0;
    if ( *((_QWORD *)v6 + 4234) )
    {
      v77 = RecoveryMgr::SkipParallelRedo(v6, v76);
      v79 = v287;
      if ( !v77 )
      {
        v80 = (const struct LogRec **)((char *)v6 + 22132);
        if ( ParallelRedoManager::EnqueueLogRecord(v78, v5, (RecoveryMgr *)((char *)v6 + 22132), v8, v287) )
        {
          v81 = 0;
          v315 = 0;
          v325 = 1;
          v298 = 1;
LABEL_194:
          if ( (_BYTE)v286 && memcmp_0(Buf1, &Buf2, 0x30u) )
          {
            v358 = 0x4000000000000017LL;
            if ( (dword_10317F71C & 0x40000000) != 0 )
            {
              v320 = 0;
              v429 = v80;
              v320 = *v80;
              v314 = 0x4000000000000017LL;
              v440 = 0;
              v441 = 2;
              v442 = 0;
              v443 = &v446;
              v444 = &v454;
              v455 = 0;
              v456 = 0;
              v445 = 0;
              v457 = 0;
              v446 = &v458;
              v447 = 28;
              v448 = 1;
              v449 = 0;
              v450 = 0;
              v451 = 0;
              v452 = 4;
              v453 = 0;
              v341 = *(_WORD *)(*(_QWORD *)(*(_QWORD *)v6 + 1712LL) + 40LL);
              v458 = v341;
              v430 = HIDWORD(v320) | ((unsigned __int64)(unsigned int)v320 << 32);
              v459 = v430;
              v460 = *((unsigned __int16 *)v6 + 11070);
              v461 = *((unsigned __int8 *)v5 + 22);
              LogOpString = GetLogOpString((unsigned __int8)v461);
              v431 = LogOpString;
              if ( LogOpString )
              {
                v88 = -1;
                do
                  ++v88;
                while ( *(_WORD *)(LogOpString + 2 * v88) );
                v89 = 2 * v88;
              }
              else
              {
                v89 = 0;
              }
              v343 = v89;
              v450 = LogOpString;
              v451 = v89;
              v452 = v87;
              v453 = 0;
              XeSqlPkg::log_header_corruption_during_redo::Publish((XeSqlPkg::log_header_corruption_during_redo *)v439);
            }
            if ( HadrRecoveryCallbacks::IsHadrForwarderRole(*(struct RecoveryUnit **)v6) )
            {
              LODWORD(v281) = *((unsigned __int8 *)v5 + 22);
              utassert_fail(
                1u,
                "false",
                "recovery.cpp",
                12996,
                "Forwarder redo log header check failed for logop %d.",
                v281);
            }
            else
            {
              v318 = HIBYTE(qword_10317AD29);
              if ( (qword_10317AD29 & 0x100000000000000LL) != 0 )
              {
                LODWORD(v281) = *((unsigned __int8 *)v5 + 22);
                utassert_fail(1u, "false", "recovery.cpp", 13006, "Redo log header check failed for logop %d.", v281);
              }
            }
          }
          if ( v81 )
            ++*((_QWORD *)v6 + 3068);
          goto LABEL_209;
        }
        RecoveryMgr::ShutdownParallelRedoMgr(v6, 0);
      }
    }
    else
    {
      v79 = v287;
    }
    v80 = (const struct LogRec **)((char *)v6 + 22132);
    v82 = (char *)Buf1;
    v83 = RecoveryMgr::RedoPageOperationInternal(
            v6,
            (const struct PageLog *)Buf1,
            (RecoveryMgr *)((char *)v6 + 22132),
            v79,
            0,
            0,
            0,
            0);
    v81 = v83;
    v382[1] = v83;
    v315 = v83;
    if ( *((_BYTE *)v5 + 22) == 21 && !v83 )
    {
      v84 = v82 + 24;
      v425 = v84;
      v367 = *(_DWORD *)v84;
      v368 = *((_WORD *)v84 + 2);
      v426 = *(RecoveryUnit **)v6;
      v85 = FileMgr::GetFCB(*((_QWORD *)v426 + 212), v368, 1);
      v427 = v85;
      if ( v85 )
      {
        v428 = v84;
        v310 = *(_DWORD *)v84;
        v311 = *((_WORD *)v84 + 2);
        if ( v310 < *(_DWORD *)(v85 + 128) )
          RecoveryMgr::UnconditionalEncryptRedo(v6, (const struct PageLog *)Buf1, (RecoveryMgr *)((char *)v6 + 22132));
      }
    }
    goto LABEL_194;
  }
  catch ( SQLError v338 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v395, (const struct SQLError *)&v338);
      v249 = v339;
      v250 = v338;
      if ( v339 == 1 )
        v251 = v338;
      else
        v251 = (unsigned __int16)v338;
      if ( v251 == 829
        || (v339 != 1 ? (v252 = (unsigned __int16)v338) : (v252 = v338),
            v252 == 823 || (v339 != 1 ? (v253 = (unsigned __int16)v338) : (v253 = v338), v253 == 824)) )
      {
        v254 = v313;
        v256 = v321;
      }
      else
      {
        v432 = &v329;
        v254 = v313;
        v255 = v313 + 24;
        v433 = v313 + 24;
        v329 = *((_DWORD *)v313 + 6);
        v330 = *((_WORD *)v313 + 14);
        v256 = v321;
        DumpPageForFailures(*(_QWORD *)v321, &v329);
        v434 = &v331;
        v354 = NullXdesId;
        v355 = word_10318AB38;
        v435 = v255;
        v331 = *v255;
        v332 = *((_WORD *)v254 + 14);
        DumpLogForFailures(
          L"for RedoLogRecord failure - filter on PageId",
          *(_QWORD *)v256,
          0,
          (char *)v256 + 22108,
          &v331,
          &v354);
        v249 = v339;
        v250 = v338;
      }
      if ( dword_103172528 || dword_1031852C8 )
      {
        if ( v249 != 1 )
          v250 = (unsigned __int16)v250;
        if ( v250 == 701 )
          ReportFaultOnDbId(*(unsigned __int16 *)(*(_QWORD *)v256 + 1720LL), 0, 47);
      }
      v257 = v299;
      RecoveryMgr::RaiseIfUndeferrable(v256, (struct SQLError *)&v338, v299);
      v310 = 9;
      v311 = 1;
      v259 = (unsigned int *)(v254 + 24);
      v436 = v254 + 24;
      v260 = *((_DWORD *)v254 + 6);
      LODWORD(v316) = v260;
      v261 = *((_WORD *)v254 + 14);
      WORD2(v316) = v261;
      v262 = v260 == 9 && v261 == 1;
      if ( v262 || (v437 = v254 + 24, LODWORD(Buf1) = v260, WORD2(Buf1) = *((_WORD *)v254 + 14), !v260) )
      {
        CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v395);
        ExceptionRethrow(CurrentException);
      }
      v264 = v339;
      v265 = v338;
      if ( v339 == 1 )
        v266 = v338;
      else
        v266 = (unsigned __int16)v338;
      if ( v266 != 829 )
      {
        if ( v339 != 1 )
          v265 = (unsigned __int16)v338;
        if ( v265 != 836 )
        {
          v335 = 0;
          v336 = 0;
          v337 = 0;
          v406 = v254 + 24;
          v352 = *v259;
          v353 = *((_WORD *)v254 + 14);
          LOBYTE(v258) = -1;
          PageRef::FixNoError(&v335, &v352, v258, 4, *(_QWORD *)v256, 0, 0, 1);
          v407 = v335;
          v390[2] = 1;
          v267 = BPool::PrepareToDirty(qword_10317B628, v335, 1, 0);
          v408 = v267;
          *(_WORD *)(v267 + 4) &= ~0x200u;
          *(_WORD *)(v267 + 4) &= ~0x1000u;
          *(_DWORD *)(v267 + 64) = 1;
          v409 = v254 + 24;
          v268 = *v259;
          LODWORD(v299) = v268;
          WORD2(v299) = *((_WORD *)v254 + 14);
          v269 = WORD2(v299);
          v410 = *(_QWORD *)v335;
          v270 = v410 + 32;
          v411 = v410 + 32;
          *(_DWORD *)(v410 + 32) = v268;
          *(_WORD *)(v270 + 4) = v269;
          v412 = *(_QWORD *)v256;
          v271 = *(_QWORD *)(v412 + 1712);
          v272 = (*(_BYTE *)(v271 + 60) & 1) != 0 && !*(_QWORD *)(v271 + 640);
          if ( !v272 && (*((_DWORD *)v256 + 9) & 0x80) == 0 || v254[22] != 21 )
            goto LABEL_697;
          v371 = 0;
          v372 = 0;
          v273 = 0;
          v373 = 0;
          v274 = v254 + 36;
          v413 = v274;
          if ( !*((_WORD *)v274 + 4) && !*(_DWORD *)v274 )
            v273 = *((_DWORD *)v274 + 1) == 0;
          if ( !v273 )
          {
LABEL_697:
            v414 = (int *)&v333;
            v415 = (char *)v335 + 98;
            v340 = *((_WORD *)v335 + 49);
            v416 = v259;
            v333 = *v259;
            v334 = *((_WORD *)v259 + 2);
            IsConcurrentUpdateSupportedPageId(&v333, v268);
            PageHeader::SetLsn(*(PageHeader **)v335, (const struct LSN *)(v313 + 36), v276, (v275 & 8) != 0);
          }
          v417 = v335;
          v418 = *(_QWORD *)v256;
          DirtyPageMgr::PreNonLoggedDirty(*(DirtyPageMgr **)(v418 + 1880), v335, 1);
          BUF::MarkRestorePending(v335, 1);
          v362[0] = 0;
          v362[1] = 0;
          v363 = 0;
          v419 = v335;
          BPool::Dirty(qword_10317B628, v335, 0, (struct LSN *)v362);
          PageRef::~PageRef((PageRef *)&v335);
          v264 = v339;
        }
      }
      v277 = v287;
      *(_OWORD *)((char *)v287 + 56) = v338;
      *((_DWORD *)v277 + 18) = v264;
      v315 = 0;
      v383 = 0;
      if ( v257 )
      {
        v278 = *((_QWORD *)v257 + 16);
        v383 = v278;
        if ( v278 )
        {
          if ( (unsigned int)RecoveryUnit::IsHadronDrivingRecovery(*(RecoveryUnit **)v256) )
          {
            v43 = (*((_WORD *)v328 + 7) & 0x80) == 0;
            v390[1] = *((_WORD *)v328 + 7) & 0x80;
            if ( (unsigned int)RecoveryMgr::NeedToTrackVersions(v256, (const struct LogRec *)((char *)v328 + 16), !v43) )
            {
              if ( (*(_BYTE *)(v278 + 536) & 2) == 0 )
                XVB::Enqueue(*(XVB **)(v278 + 208), 0);
            }
          }
        }
      }
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v395);
    }
    catch ( ShortStackException )
    {
    }
    LODWORD(v7) = 0;
    v18 = &logOperations;
    Buf1 = v313;
    v316 = *(RecoveryMgr **)v364;
    v5 = v328;
    v6 = *(RecoveryMgr **)v364;
  }
LABEL_709:
  v90 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v91 = *(struct Worker **)(v90 + 256);
  if ( !v91 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v91 = *(struct Worker **)(v90 + 256);
  }
  if ( *((_DWORD *)v91 + 139) )
    ExceptionPostCatchActions(v91);
  if ( v315 )
  {
    if ( (qword_10317AD29 & 8) != 0
      || (v92 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
          *(_QWORD *)v92)
      && (v93 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v92 + 56LL)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v93, 0xD4Bu) )
    {
      v344 = 92;
      v324 = 100;
      GetLsnAsDecimalString((RecoveryMgr *)((char *)v6 + 22132), &v324, v501);
      LSN::FormatAsHexString((LSN *)((char *)v6 + 22132), v496, &v344);
      v94 = *((unsigned __int16 *)v313 + 14);
      v95 = *((_BYTE *)v5 + 22);
      v96 = 0;
      while ( *(_BYTE *)v18 != v95 )
      {
        if ( *(_BYTE *)v18 <= v95 )
        {
          ++v96;
          v18 += 2;
          if ( v96 < 0x57 )
            continue;
        }
        v97 = 0;
        goto LABEL_225;
      }
      v97 = (struct LSN *)*((_QWORD *)v18 + 1);
LABEL_225:
      v98 = *((unsigned __int16 *)v5 + 10);
      LODWORD(v284) = *((_DWORD *)v313 + 6);
      LODWORD(v283) = v94;
      v282 = v97;
      LODWORD(v281) = *((_DWORD *)v5 + 4);
      LODWORD(v280) = v98;
      traceprint(
        L"REDO LSN %.*ls (0x%ls), XdesId 0x%04lx:%08lx redid %ls on page %d:%d.\n",
        (unsigned __int64)v324 >> 1,
        v501,
        v496,
        v280,
        v281,
        v97,
        v283,
        v284);
    }
    goto LABEL_250;
  }
  if ( v325 )
  {
    if ( (qword_10317AD29 & 8) != 0
      || (v99 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset)) != 0
      && (v100 = **(struct CSessionTraceFlags ***)(v99 + 56)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v100, 0xD4Bu) )
    {
      v345 = 92;
      v326 = 100;
      GetLsnAsDecimalString((RecoveryMgr *)((char *)v6 + 22132), &v326, v502);
      LSN::FormatAsHexString((LSN *)((char *)v6 + 22132), v497, &v345);
      v101 = *((unsigned __int16 *)v313 + 14);
      v102 = *((_BYTE *)v5 + 22);
      v103 = 0;
      while ( *(_BYTE *)v18 != v102 )
      {
        if ( *(_BYTE *)v18 <= v102 )
        {
          ++v103;
          v18 += 2;
          if ( v103 < 0x57 )
            continue;
        }
        v104 = 0;
        goto LABEL_237;
      }
      v104 = (struct LSN *)*((_QWORD *)v18 + 1);
LABEL_237:
      v105 = *((unsigned __int16 *)v5 + 10);
      LODWORD(v284) = *((_DWORD *)v313 + 6);
      LODWORD(v283) = v101;
      v282 = v104;
      LODWORD(v281) = *((_DWORD *)v5 + 4);
      LODWORD(v280) = v105;
      traceprint(
        L"REDO LSN %.*ls (0x%ls), XdesId 0x%04lx:%08lx deferred %ls on page %d:%d.\n",
        (unsigned __int64)v326 >> 1,
        v502,
        v497,
        v280,
        v281,
        v104,
        v283,
        v284);
    }
  }
  else if ( (qword_10317AD29 & 8) != 0
         || (v106 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset)) != 0
         && (v107 = **(struct CSessionTraceFlags ***)(v106 + 56)) != 0
         && CSessionTraceFlags::CheckSessionTraceInternal(v107, 0xD4Bu) )
  {
    v346 = 92;
    v322 = 100;
    GetLsnAsDecimalString((RecoveryMgr *)((char *)v6 + 22132), &v322, v503);
    LSN::FormatAsHexString((LSN *)((char *)v6 + 22132), v498, &v346);
    v108 = *((unsigned __int16 *)v313 + 14);
    v109 = *((_BYTE *)v5 + 22);
    v110 = 0;
    while ( *(_BYTE *)v18 != v109 )
    {
      if ( *(_BYTE *)v18 <= v109 )
      {
        ++v110;
        v18 += 2;
        if ( v110 < 0x57 )
          continue;
      }
      v111 = 0;
      goto LABEL_248;
    }
    v111 = (struct LSN *)*((_QWORD *)v18 + 1);
LABEL_248:
    v112 = *((unsigned __int16 *)v5 + 10);
    LODWORD(v284) = *((_DWORD *)v313 + 6);
    LODWORD(v283) = v108;
    v282 = v111;
    LODWORD(v281) = *((_DWORD *)v5 + 4);
    LODWORD(v280) = v112;
    traceprint(
      L"REDO LSN %.*ls (0x%ls), XdesId 0x%04lx:%08lx skipped %ls on page %d:%d.\n",
      (unsigned __int64)v322 >> 1,
      v503,
      v498,
      v280,
      v281,
      v111,
      v283,
      v284);
  }
  if ( *((_DWORD *)v6 + 8) == 3 )
  {
LABEL_250:
    v113 = *((_BYTE *)v5 + 22);
    if ( v113 == 4 )
    {
      v186 = *((_BYTE *)v5 + 23);
      if ( (v186 == 20 || v186 == 23) && (*((_DWORD *)v6 + 9) & 0x80) == 0 )
      {
        v187 = *(RecoveryUnit **)v6;
        v286 = *(_WORD *)(*(_QWORD *)v6 + 1662LL);
        v188 = *((_QWORD *)v187 + 214);
        v189 = 0;
        UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)(v188 + 5376)
          || _InterlockedCompareExchange64((volatile signed __int64 *)(v188 + 5376), UniqueThread_low, 0) )
        {
          v191 = 0;
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v192 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset;
            if ( v192 && *(_QWORD *)(v192 + 272) == v192 )
              v191 = *(_QWORD *)(v192 + 256);
            if ( v191 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&PerformanceCount);
                v189 = (DirtyPageMgr *)PerformanceCount.QuadPart;
              }
              else
              {
                v189 = MEMORY[0x7FFE0008];
              }
            }
          }
          v193 = v188 + 5376;
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v193, UniqueThread_low);
          else
            Spinlock<148,10,258>::SpinToAcquireOptimistic(v193, v191, UniqueThread_low);
          if ( v191 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v385);
              v194 = (DirtyPageMgr *)v385.QuadPart;
            }
            else
            {
              v194 = MEMORY[0x7FFE0008];
            }
            if ( v194 < v189 )
              v195 = 0;
            else
              v195 = v194 - v189;
            *(_QWORD *)(v191 + 3192) += v195;
          }
        }
        v196 = *(RecoveryUnit **)v6;
        v358 = *(_QWORD *)(*(_QWORD *)v6 + 2216LL);
        LOWORD(v310) = *((_WORD *)v196 + 1112);
        v197 = *((_QWORD *)v196 + 214);
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v198 = rand();
          if ( v198 == 5 * (v198 / 5) )
            Spinlock<148,10,258>::UpdateStatSnapshot();
        }
        *(_QWORD *)(v197 + 5376) = 0;
        RecoveryUnit::RefreshBootPageFields(*(RecoveryUnit **)v6);
        v199 = *(_QWORD *)(*(_QWORD *)v6 + 1712LL);
        v200 = 0;
        v201 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)(v199 + 5376)
          || _InterlockedCompareExchange64((volatile signed __int64 *)(v199 + 5376), v201, 0) )
        {
          v202 = 0;
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v203 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset;
            if ( v203 && *(_QWORD *)(v203 + 272) == v203 )
              v202 = *(_QWORD *)(v203 + 256);
            if ( v202 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v386);
                v200 = (DirtyPageMgr *)v386.QuadPart;
              }
              else
              {
                v200 = MEMORY[0x7FFE0008];
              }
            }
          }
          v204 = v199 + 5376;
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v204, v201);
          else
            Spinlock<148,10,258>::SpinToAcquireOptimistic(v204, v202, v201);
          if ( v202 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v387);
              v205 = (DirtyPageMgr *)v387.QuadPart;
            }
            else
            {
              v205 = MEMORY[0x7FFE0008];
            }
            if ( v205 < v200 )
              v206 = 0;
            else
              v206 = v205 - v200;
            *(_QWORD *)(v202 + 3192) += v206;
          }
        }
        v207 = *(RecoveryUnit **)v6;
        v314 = *(_QWORD *)(*(_QWORD *)v6 + 2216LL);
        v208 = *((_WORD *)v207 + 1112);
        v209 = *((_QWORD *)v207 + 214);
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v210 = rand();
          if ( v210 == 5 * (v210 / 5) )
            Spinlock<148,10,258>::UpdateStatSnapshot();
        }
        *(_QWORD *)(v209 + 5376) = 0;
        v211 = *(RecoveryUnit **)v6;
        if ( v286 != *(_WORD *)(*(_QWORD *)v6 + 1662LL) )
        {
          v212 = *((_QWORD *)v211 + 214);
          LODWORD(v281) = *(unsigned __int16 *)(*(_QWORD *)v6 + 1662LL);
          LODWORD(v280) = v286;
          RecoveryUnit::LogSqlError(v211, 0x3E1u, *(unsigned int *)(v212 + 928), v212 + 936, v280, v281);
          v211 = *(RecoveryUnit **)v316;
        }
        if ( *((_BYTE *)v211 + 8272) )
        {
          v213 = *((_QWORD *)v211 + 214);
          if ( (*(_BYTE *)(v213 + 684) & 2) != 0 )
          {
            DBMgr::RestoreSpecificDatabaseOptions(qword_10316ECA0, *(unsigned __int16 *)(v213 + 40), 131292189, 1);
            v214 = *(RecoveryUnit **)v6;
            v215 = *(_QWORD *)(*(_QWORD *)v6 + 1712LL);
            if ( ((unsigned int)v314 > (unsigned int)v358
               || (_DWORD)v314 == (_DWORD)v358
               && (HIDWORD(v314) > HIDWORD(v358) || HIDWORD(v314) == HIDWORD(v358) && v208 > (unsigned __int16)v310))
              && ((*(_BYTE *)(v215 + 684) & 2) != 0 || (*(_BYTE *)(v215 + 56) & 8) == 0) )
            {
              v216 = *((_DWORD *)qword_10316ECA0 + 19) ? **((_QWORD **)qword_10316ECA0 + 5) : 0LL;
              if ( (unsigned int)RecoveryUnit::IsUpdateable(*(RecoveryUnit **)(v216 + 4624)) )
              {
                FileMgr::MarkDroppedFilesAsUsable(*((_QWORD *)v214 + 212));
                StreamFileMgr::MarkDroppedFilesAsUsable(*((StreamFileMgr **)v214 + 213));
                FullTextMarkDroppedFilesAsUsable(v214);
              }
            }
          }
        }
      }
    }
    else if ( v113 == 16 )
    {
      v288 = -1;
      v291 = 0;
      v290 = 0;
      v295 = 0;
      *(_QWORD *)((char *)&v296 + 2) = 0;
      v292 = 0;
      v114 = 0;
      v302 = 0;
      v307 = 0;
      *(_QWORD *)((char *)&v308 + 2) = 0;
      v304 = 0;
      v482 = 0;
      v483 = 1;
      Data = VarLogData::GetData((const struct LogRec *)((char *)v5 + 62), 0, &v319);
      v116 = Data;
      v43 = (*Data & 1) == 0;
      v303 = Data;
      if ( v43 )
      {
        v300 = 0;
        v121 = 0;
        LODWORD(v308) = 0;
        switch ( *Data & 0xE )
        {
          case 0:
          case 2:
          case 8:
          case 0xC:
            v121 = *((unsigned __int16 *)Data + 1);
            if ( v121 - 1 > 0x1F9D )
            {
              RaiseInconsistencyError(Data, 6);
              v114 = v302;
            }
            break;
          case 1:
          case 3:
          case 5:
          case 7:
          case 9:
          case 0xB:
          case 0xD:
            utassert_fail(
              1u,
              "FALSE",
              "Sql\\Ntdbms\\storeng\\drs\\include\\fixedvarrecord.inl",
              294,
              "Invalid switch value");
            v114 = v302;
            break;
          case 4:
            v121 = 9;
            break;
          case 6:
          case 0xA:
            break;
          case 0xE:
            v121 = 1;
            break;
        }
        LODWORD(v304) = v121;
      }
      else
      {
        v300 = 1;
        v117 = *Data;
        switch ( byte_101CCD118[*Data & 0x1C] )
        {
          case 0:
            v118 = Data[1];
            if ( (v118 & 0x80u) != 0 )
            {
              v119 = HIBYTE(*(_WORD *)(v116 + 1)) | ((*(_WORD *)(v116 + 1) & 0x7F) << 8);
              v301 = v119;
              LOWORD(v305) = 3;
              v120 = 3;
            }
            else
            {
              v119 = v118;
              v301 = v118;
              LOWORD(v305) = 2;
              v120 = 2;
            }
            v306 = v120 + (((unsigned int)v119 + 1) >> 1);
            if ( v119 > 0x1Eu )
              HIWORD(v305) = (v119 - 1) / 30;
            else
              HIWORD(v305) = 0;
            v309 = 0;
            v121 = 0;
            break;
          case 1:
            if ( (v117 & 0x1C) == 4 && (v117 & 2) != 0 )
            {
              v305 = 0;
              v301 = 0;
              v306 = 0;
              LOWORD(v308) = 0;
              v114 = 15;
              v302 = 15;
              v309 = 1;
              v121 = 0;
            }
            else
            {
              v305 = 0;
              v301 = 0;
              v306 = 0;
              LOWORD(v308) = 0;
              v114 = 1;
              v302 = 1;
              v309 = 0;
              v121 = 0;
            }
            break;
          case 2:
            v305 = 0;
            v301 = 0;
            v306 = 0;
            LOWORD(v308) = 0;
            v114 = 9;
            v302 = 9;
            v309 = 0;
            v121 = 0;
            break;
          case 3:
            utassert_fail(1u, "FALSE", "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl", 207, "Invalid switch value");
            v114 = v302;
            v121 = 0;
            break;
        }
      }
      if ( v300 )
      {
        if ( !v114 )
        {
          CDRecord::Resize((CDRecord *)&v301);
          v114 = v302;
        }
        if ( v114 >= 9 )
          goto LABEL_372;
        if ( (*v303 & 0x1C) != 0 )
        {
          v145 = (*v303 & 0x1C) == 12;
LABEL_370:
          if ( v145 )
            goto LABEL_371;
LABEL_372:
          v146 = 9;
          goto LABEL_373;
        }
      }
      else
      {
        if ( !v114 )
        {
          v301 = 0;
          HIDWORD(v304) = v121;
          v114 = v121;
          if ( (*v303 & 0x10) != 0 )
          {
            v114 = (((unsigned int)*(unsigned __int16 *)&v303[v121] + 7) >> 3) + v121 + 2;
            HIDWORD(v304) = v114;
          }
          if ( (*v303 & 0x20) != 0 )
          {
            v122 = &v303[v114];
            v123 = *(_WORD *)v122;
            v306 = v123;
            if ( !v123 )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v124 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v124 )
                {
                  v125 = *(_QWORD *)(v124 + 96);
                  if ( v125 )
                  {
                    if ( *(_BYTE *)(v125 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                      else
                        ex_raise(34, 68, 21, 1003);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v303, 3);
              v123 = v306;
            }
            v126 = HIDWORD(v304) + 2 + 2 * v123;
            v305 = v126;
            if ( v126 > 0x1F9E )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v127 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v127 )
                {
                  v128 = *(_QWORD *)(v127 + 96);
                  if ( v128 )
                  {
                    if ( *(_BYTE *)(v128 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v303, 4);
              v123 = v306;
              v126 = v305;
            }
            v114 = *(_WORD *)&v122[2 * v123] & 0x7FFF;
            v302 = v114;
            if ( v126 > v114 )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v129 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v129 )
                {
                  v130 = *(_QWORD *)(v129 + 96);
                  if ( v130 )
                  {
                    if ( *(_BYTE *)(v130 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v303, 4);
              v123 = v306;
              v126 = v305;
              v114 = v302;
            }
            while ( *(__int16 *)&v122[2 * v123] < 0 )
            {
              v131 = &v303[HIDWORD(v304)];
              if ( v123 == 1 )
                v132 = v126;
              else
                v132 = *(_WORD *)&v131[2 * v123 - 2] & 0x7FFF;
              if ( v132 < v126 || (*(_WORD *)&v131[2 * v123] & 0x7FFFu) < v132 )
              {
                RaiseInconsistencyError(v303, 7);
                v123 = v306;
                v126 = v305;
                v114 = v302;
              }
              if ( v132 < v126 || v132 > v114 )
                goto LABEL_362;
              v133 = *(_WORD *)&v303[v132];
              if ( v133 == 5 )
              {
                v301 |= 2u;
                v306 = v123 - 1;
                WORD2(v308) = v132;
                v134 = &v303[(unsigned __int16)v132];
                v135 = *((_WORD *)v134 + 1);
                if ( (v135 & 0x4000) != 0 )
                  v136 = WORD3(v308) ^ (WORD3(v308) ^ v135) & 0x3800;
                else
                  v136 = WORD3(v308) & 0xC7FF;
                WORD3(v308) = v136 ^ (*((_WORD *)v134 + 1) ^ v136) & 0x7FF;
                break;
              }
              if ( v133 >= 0x400u )
              {
                v301 |= 1u;
                v43 = v123-- == 1;
                v306 = v123;
                if ( !v43 )
                  continue;
              }
              break;
            }
          }
          else
          {
            v302 = v114;
            v306 = 0;
            v305 = v114;
          }
          if ( (*v303 & 0x40) != 0 )
          {
            LODWORD(v308) = v114;
            v302 = v114 + 14;
            VersioningInfo = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v301);
            v138 = HIWORD(*(_QWORD *)VersioningInfo);
            v139 = 0;
            if ( (((__int16)v138 ^ ((unsigned int)(__int16)v138 >> 1)) & 0x2000) != 0 )
            {
              if ( (v138 & 0x4000) != 0 )
                LOWORD(v138) = v138 | 0x2000;
              else
                LOWORD(v138) = v138 & 0xDFFF;
            }
            if ( (_WORD)v138 == 0xFFFC )
              v139 = (unsigned __int16)WORD2(*(_QWORD *)VersioningInfo) >> 5;
            v114 = v139 + v302;
            v302 += v139;
          }
          else
          {
            LODWORD(v308) = 0;
          }
          if ( v307 && v307 < (unsigned __int64)&v303[v114] )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v140 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v140 )
              {
                v141 = *(_QWORD *)(v140 + 96);
                if ( v141 )
                {
                  if ( *(_BYTE *)(v141 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                    else
                      ex_raise(34, 68, 21, 1018);
                  }
                }
              }
            }
            RaiseInconsistencyError(v303, 18);
            v114 = v302;
          }
          if ( v114 - 1 > 0x3F3B )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v142 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v142 )
              {
                v143 = *(_QWORD *)(v142 + 96);
                if ( v143 )
                {
                  if ( *(_BYTE *)(v143 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                    else
                      ex_raise(34, 68, 21, 1005);
                  }
                }
              }
            }
            RaiseInconsistencyError(v303, 5);
            v114 = v302;
          }
        }
LABEL_362:
        if ( v114 >= 9 )
          goto LABEL_372;
        v144 = *v303 & 0xE;
        if ( v144 )
        {
          v145 = v144 == 12;
          goto LABEL_370;
        }
      }
LABEL_371:
      v146 = 9;
      v114 = 9;
LABEL_373:
      v147 = 1;
      if ( v114 != v319 )
        utassert_fail(1u, "oldFileHeader.Size () == fileHdrRowSize", "recovery.cpp", 13287, 0);
      v148 = VarLogData::GetData((const struct LogRec *)((char *)v5 + 62), 1u, &v319);
      v149 = v148;
      v43 = (*v148 & 1) == 0;
      v291 = v148;
      if ( v43 )
      {
        v288 = 0;
        v155 = 0;
        LODWORD(v296) = 0;
        switch ( *v148 & 0xE )
        {
          case 0:
          case 2:
          case 8:
          case 0xC:
            v155 = *((unsigned __int16 *)v148 + 1);
            if ( v155 - 1 > 0x1F9D )
              RaiseInconsistencyError(v148, 6);
            break;
          case 1:
          case 3:
          case 5:
          case 7:
          case 9:
          case 0xB:
          case 0xD:
            utassert_fail(
              1u,
              "FALSE",
              "Sql\\Ntdbms\\storeng\\drs\\include\\fixedvarrecord.inl",
              294,
              "Invalid switch value");
            break;
          case 4:
            v155 = 9;
            break;
          case 6:
          case 0xA:
            break;
          case 0xE:
            v155 = 1;
            break;
        }
        LODWORD(v292) = v155;
      }
      else
      {
        v288 = 1;
        v150 = *v148;
        switch ( *v148 & 0x1C )
        {
          case 0:
          case 0xC:
          case 0x10:
          case 0x14:
          case 0x18:
          case 0x1C:
            v151 = v148[1];
            if ( (v151 & 0x80u) != 0 )
            {
              v152 = HIBYTE(*(_WORD *)(v149 + 1)) | ((*(_WORD *)(v149 + 1) & 0x7F) << 8);
              v289 = v152;
              v153 = 3;
              v154 = 3;
            }
            else
            {
              v152 = v151;
              v289 = v151;
              v153 = 2;
              v154 = 2;
            }
            LOWORD(v293) = v153;
            v294 = v154 + (((unsigned int)v152 + 1) >> 1);
            if ( v152 > 0x1Eu )
              HIWORD(v293) = (v152 - 1) / 30;
            else
              HIWORD(v293) = 0;
            v297 = 0;
            v155 = 0;
            break;
          case 1:
          case 2:
          case 3:
          case 5:
          case 6:
          case 7:
          case 9:
          case 0xA:
          case 0xB:
          case 0xD:
          case 0xE:
          case 0xF:
          case 0x11:
          case 0x12:
          case 0x13:
          case 0x15:
          case 0x16:
          case 0x17:
          case 0x19:
          case 0x1A:
          case 0x1B:
            utassert_fail(1u, "FALSE", "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl", 207, "Invalid switch value");
            v155 = 0;
            break;
          case 4:
            if ( (v150 & 0x1C) == 4 && (v150 & 2) != 0 )
            {
              v293 = 0;
              v289 = 0;
              v294 = 0;
              LOWORD(v296) = 0;
              v290 = 15;
              v297 = 1;
              v155 = 0;
            }
            else
            {
              v293 = 0;
              v289 = 0;
              v294 = 0;
              LOWORD(v296) = 0;
              v290 = 1;
              v297 = 0;
              v155 = 0;
            }
            break;
          case 8:
            v293 = 0;
            v289 = 0;
            v294 = 0;
            LOWORD(v296) = 0;
            v290 = 9;
            v297 = 0;
            v155 = 0;
            break;
        }
      }
      if ( v288 )
      {
        if ( !v290 )
          CDRecord::Resize((CDRecord *)&v289);
        if ( v290 >= 9 || (*v291 & 0x1C) != 0 && (*v291 & 0x1C) != 0xC )
          v310 = v290;
        else
          v310 = 9;
        v146 = v310;
      }
      else
      {
        if ( !v290 )
        {
          v289 = 0;
          HIDWORD(v292) = v155;
          if ( (*v291 & 0x10) != 0 )
          {
            v155 += (((unsigned int)*(unsigned __int16 *)&v291[v155] + 7) >> 3) + 2;
            HIDWORD(v292) = v155;
          }
          if ( (*v291 & 0x20) != 0 )
          {
            v156 = &v291[v155];
            v157 = *(_WORD *)v156;
            v294 = v157;
            if ( !v157 )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v158 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v158 )
                {
                  v159 = *(_QWORD *)(v158 + 96);
                  if ( v159 )
                  {
                    if ( *(_BYTE *)(v159 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                      else
                        ex_raise(34, 68, 21, 1003);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v291, 3);
              v157 = v294;
            }
            v160 = HIDWORD(v292) + 2 + 2 * v157;
            v293 = v160;
            if ( v160 > 0x1F9E )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v161 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v161 )
                {
                  v162 = *(_QWORD *)(v161 + 96);
                  if ( v162 )
                  {
                    if ( *(_BYTE *)(v162 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v291, 4);
              v157 = v294;
              v160 = v293;
            }
            v290 = *(_WORD *)&v156[2 * v157] & 0x7FFF;
            if ( v160 > v290 )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v163 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v163 )
                {
                  v164 = *(_QWORD *)(v163 + 96);
                  if ( v164 )
                  {
                    if ( *(_BYTE *)(v164 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v291, 4);
              v157 = v294;
              v160 = v293;
            }
            while ( *(__int16 *)&v156[2 * v157] < 0 )
            {
              v165 = &v291[HIDWORD(v292)];
              if ( v157 == 1 )
                v166 = v160;
              else
                v166 = *(_WORD *)&v165[2 * v157 - 2] & 0x7FFF;
              if ( v166 < v160 || (*(_WORD *)&v165[2 * v157] & 0x7FFFu) < v166 )
              {
                RaiseInconsistencyError(v291, 7);
                v157 = v294;
                v160 = v293;
              }
              if ( v166 < v160 || v166 > v290 )
                goto LABEL_485;
              v167 = *(_WORD *)&v291[v166];
              if ( v167 == 5 )
              {
                v289 |= 2u;
                v294 = v157 - 1;
                WORD2(v296) = v166;
                v168 = &v291[(unsigned __int16)v166];
                v169 = *((_WORD *)v168 + 1);
                if ( (v169 & 0x4000) != 0 )
                  v170 = WORD3(v296) ^ (WORD3(v296) ^ v169) & 0x3800;
                else
                  v170 = WORD3(v296) & 0xC7FF;
                WORD3(v296) = v170 ^ (*((_WORD *)v168 + 1) ^ v170) & 0x7FF;
                break;
              }
              if ( v167 >= 0x400u )
              {
                v289 |= 1u;
                v43 = v157-- == 1;
                v294 = v157;
                if ( !v43 )
                  continue;
              }
              break;
            }
          }
          else
          {
            v290 = v155;
            v294 = 0;
            v293 = v155;
          }
          if ( (*v291 & 0x40) != 0 )
          {
            LODWORD(v296) = v290;
            v290 += 14;
            v171 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v289);
            v172 = HIWORD(*(_QWORD *)v171);
            v173 = 0;
            if ( (((__int16)v172 ^ ((unsigned int)(__int16)v172 >> 1)) & 0x2000) != 0 )
            {
              if ( (v172 & 0x4000) != 0 )
                LOWORD(v172) = v172 | 0x2000;
              else
                LOWORD(v172) = v172 & 0xDFFF;
            }
            if ( (_WORD)v172 == 0xFFFC )
              v173 = (unsigned __int16)WORD2(*(_QWORD *)v171) >> 5;
            v290 += v173;
          }
          else
          {
            LODWORD(v296) = 0;
          }
          if ( v295 && v295 < (unsigned __int64)&v291[v290] )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v174 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v174 )
              {
                v175 = *(_QWORD *)(v174 + 96);
                if ( v175 )
                {
                  if ( *(_BYTE *)(v175 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                    else
                      ex_raise(34, 68, 21, 1018);
                  }
                }
              }
            }
            RaiseInconsistencyError(v291, 18);
          }
          if ( v290 - 1 > 0x3F3B )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v176 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v176 )
              {
                v177 = *(_QWORD *)(v176 + 96);
                if ( v177 )
                {
                  if ( *(_BYTE *)(v177 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                    else
                      ex_raise(34, 68, 21, 1005);
                  }
                }
              }
            }
            RaiseInconsistencyError(v291, 5);
          }
        }
LABEL_485:
        if ( v290 >= 9 || (v178 = *v291 & 0xE) != 0 && v178 != 12 )
          v146 = v290;
        v147 = 1;
      }
      if ( v146 != v319 )
        utassert_fail(1u, "newFileHeader.Size () == fileHdrRowSize", "recovery.cpp", 13292, 0);
      v179 = VarLogData::GetData((const struct LogRec *)((char *)v5 + 62), 3u, &v347);
      v180 = v347 >> 5;
      if ( *((_WORD *)v5 + 31) <= 2u )
        v181 = (const struct LSN *)&v482;
      else
        v181 = (const struct LSN *)VarLogData::GetData((const struct LogRec *)((char *)v5 + 62), 2u, v390);
      if ( *((_DWORD *)v6 + 8) != 3 && (*((_DWORD *)v6 + 9) & 0x80) == 0 )
        v147 = 0;
      if ( (unsigned int)GlobalFileHeader::GetFileTypeFromRecord(&v300) == 2 )
      {
        v393 = 0;
        v392[1] = v392;
        v392[0] = v392;
        v350 = 0;
        v351 = 0;
        v182 = (unsigned __int16 *)Buf1;
        FileOperationFCB = FileMgr::GetFileOperationFCB(
                             *(_QWORD *)(*(_QWORD *)v6 + 1696LL),
                             *((unsigned __int16 *)Buf1 + 14),
                             &v350,
                             4);
        FCB::RefreshHeaderFields(FileOperationFCB, 1);
        v391 = 7;
        v184 = *(__int64 **)(*(_QWORD *)v6 + 1736LL);
        v185 = *v184;
        LODWORD(v280) = v180;
        (*(void (__fastcall **)(__int64 *, _QWORD, __int16 *, __int16 *, struct DptEntry *, const unsigned __int8 *, int *))(v185 + 512))(
          v184,
          v182[14],
          &v300,
          &v288,
          v280,
          v179,
          &v391);
        (*(void (__fastcall **)(_QWORD, int *))(**(_QWORD **)(*(_QWORD *)v6 + 1736LL) + 520LL))(
          *(_QWORD *)(*(_QWORD *)v6 + 1736LL),
          &v391);
        if ( (_DWORD)v351 )
        {
          LatchBase::ReleaseInternal(v350, HIDWORD(v351));
          LODWORD(v351) = 0;
        }
      }
      else
      {
        FileMgr::RedoDataFileHeaderModify(
          *(FileMgr **)(*(_QWORD *)v6 + 1696LL),
          *((_WORD *)Buf1 + 14),
          (const struct Record *)&v300,
          (const struct Record *)&v288,
          v147,
          v181,
          (RecoveryMgr *)((char *)v6 + 22132),
          1);
      }
    }
    if ( (*((_BYTE *)v287 + 22) & 2) != 0
      && *((_WORD *)v6 + 11070) == *((_WORD *)v287 + 16)
      && *((_DWORD *)v6 + 5533) == *((_DWORD *)v287 + 6)
      && *((_DWORD *)v6 + 5534) == *((_DWORD *)v287 + 7) )
    {
      v217 = *((_QWORD *)v287 + 10);
      LODWORD(v328) = *(_DWORD *)(v217 + 16);
      WORD2(v328) = *(_WORD *)(v217 + 20);
      v218 = *(RecoveryUnit **)v6;
      v219 = qword_10317B628;
      v359 = 0;
      v360 = 0;
      v361 = 0;
      if ( (unsigned int)BPool::Search(qword_10317B628, &v328, *((unsigned int *)v218 + 430), &v359)
        && (*(_DWORD *)(v359 + 100) & 0x800) == 0
        && (*(_DWORD *)(v359 + 100) & 2) != 0
        && (*(_DWORD *)(v359 + 100) & 4) == 0 )
      {
        LODWORD(v7) = BPool::WriteMultiple(v219, v359, 3, 0);
      }
      PageRef::~PageRef((PageRef *)&v359);
      v220 = v316;
      _InterlockedIncrement64((volatile signed __int64 *)v316 + 2911);
      _InterlockedExchangeAdd64((volatile signed __int64 *)v220 + 2912, (unsigned int)v7);
    }
  }
LABEL_639:
  RecoveryMgr::SetLastRedoneLSN(v6, (RecoveryMgr *)((char *)v6 + 22132));
  SequencedObject<AlignedLSN,SequencedWaitInfo<AlignedLSN>,1>::Update((char *)v6 + 22160, (char *)v6 + 22132);
  GetLogRecDateTime(v5, (RecoveryMgr *)((char *)v6 + 22248));
  if ( *(_BYTE *)(*(_QWORD *)v6 + 8272LL) )
  {
    v244 = *(_QWORD *)(*(_QWORD *)v6 + 26096LL);
    if ( *(_QWORD *)v244 )
    {
      if ( !*(_BYTE *)(v244 + 7040) )
      {
        if ( *(_DWORD *)(v244 + 1344) > 0x10000u )
        {
          if ( *((_BYTE *)v6 + 22212) )
          {
            RedoneLSN = (unsigned int *)RecoveryMgr::GetRedoneLSN(v6, v491, 0);
            if ( *(_QWORD *)v244 )
            {
              if ( *(_DWORD *)(v244 + 1344) >= 0x20000u )
                HkRedoUpdateLastRedoneBlock(*(_QWORD *)v244, RedoneLSN[1] | ((unsigned __int64)*RedoneLSN << 32));
            }
          }
        }
        else
        {
          v245 = RecoveryMgr::GetRedoneLSN(v6, v491, 0);
          (*(void (__fastcall **)(_QWORD, __int64))(v246 + 24))(*(_QWORD *)(v244 + 88), v245);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x101cc99c0  push    rbx
0x101cc99c2  push    rsi
0x101cc99c3  push    rdi
0x101cc99c4  push    r12
0x101cc99c6  push    r13
0x101cc99c8  push    r14
0x101cc99ca  push    r15
0x101cc99cc  sub     rsp, 0EB0h
0x101cc99d3  mov     [rsp+0EE8h+var_AE0], 0FFFFFFFFFFFFFFFEh
0x101cc99df  mov     rax, cs:__security_cookie
0x101cc99e6  xor     rax, rsp
0x101cc99e9  mov     [rsp+0EE8h+var_48], rax
0x101cc99f1  mov     r14, r9
0x101cc99f4  mov     [rsp+0EE8h+var_E90], r9
0x101cc99f9  mov     byte ptr [rsp+0EE8h+var_E98], r8b
0x101cc99fe  mov     r15, rdx
0x101cc9a01  mov     [rsp+0EE8h+var_DC8], rdx
0x101cc9a09  mov     rsi, rcx
0x101cc9a0c  mov     [rsp+0EE8h+var_DC0], rcx
0x101cc9a14  mov     [rsp+0EE8h+var_DD8], rcx
0x101cc9a1c  mov     qword ptr [rsp+0EE8h+var_CA8], rcx
0x101cc9a24  mov     [rsp+0EE8h+var_DA0], rdx
0x101cc9a2c  xor     edi, edi
0x101cc9a2e  mov     [rsp+0EE8h+var_DAC], edi
0x101cc9a35  mov     ebx, edi
0x101cc9a37  mov     [rsp+0EE8h+var_E48], rbx
0x101cc9a3f  mov     r13d, edi
0x101cc9a42  test    byte ptr cs:qword_10317AD33+2, 10h
0x101cc9a49  jnz     short loc_101CC9A8D
0x101cc9a4b  mov     r8, gs:58h
0x101cc9a54  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101cc9a5b  mov     ecx, [rax]
0x101cc9a5d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101cc9a64  mov     edx, [rax]
0x101cc9a66  add     rdx, [r8+rcx*8]
0x101cc9a6a  mov     rax, [rdx]
0x101cc9a6d  test    rax, rax
0x101cc9a70  jz      short loc_101CC9AE8
0x101cc9a72  mov     rax, [rax+38h]
0x101cc9a76  mov     rcx, [rax]
0x101cc9a79  test    rcx, rcx
0x101cc9a7c  jz      short loc_101CC9AE8
0x101cc9a7e  mov     edx, 0DACh
0x101cc9a83  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x101cc9a89  test    eax, eax
0x101cc9a8b  jz      short loc_101CC9AE8
0x101cc9a8d  mov     r14d, edi
0x101cc9a90  test    byte ptr cs:qword_10317AD33+2, 10h
0x101cc9a97  jnz     loc_101CCD06C
0x101cc9a9d  mov     r8, gs:58h
0x101cc9aa6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101cc9aad  mov     ecx, [rax]
0x101cc9aaf  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101cc9ab6  mov     edx, [rax]
0x101cc9ab8  add     rdx, [r8+rcx*8]
0x101cc9abc  mov     rax, [rdx]
0x101cc9abf  test    rax, rax
0x101cc9ac2  jz      short loc_101CC9AE3
0x101cc9ac4  mov     rax, [rax+38h]
0x101cc9ac8  mov     rcx, [rax]
0x101cc9acb  test    rcx, rcx
0x101cc9ace  jz      short loc_101CC9AE3
0x101cc9ad0  mov     edx, 0DACh
0x101cc9ad5  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x101cc9adb  test    eax, eax
0x101cc9add  jnz     loc_101CCD06C
0x101cc9ae3  mov     r14, [rsp+0EE8h+var_E90]
0x101cc9ae8  mov     eax, [rsi+24h]
0x101cc9aeb  shr     eax, 7
0x101cc9aee  test    al, 1
0x101cc9af0  jz      short loc_101CC9B27
0x101cc9af2  movzx   eax, byte ptr [r15+16h]
0x101cc9af7  cmp     al, 7Fh
0x101cc9af9  jb      short loc_101CC9B27
0x101cc9afb  cmp     al, 99h
0x101cc9afd  jz      short loc_101CC9B27
0x101cc9aff  cmp     al, 86h
0x101cc9b01  jz      short loc_101CC9B27
0x101cc9b03  mov     [rsp+0EE8h+var_EC8], rdi
0x101cc9b08  mov     r9d, 3081h
0x101cc9b0e  lea     r8, aRecoveryCpp; "recovery.cpp"
0x101cc9b15  lea     rdx, aIsforeignlogap_0; "!IsForeignLogApply () || lp->IsPageOp ("...
0x101cc9b1c  mov     ecx, 1
0x101cc9b21  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101cc9b27  test    cs:dword_10317F71C, 20000000h
0x101cc9b31  jz      loc_101CC9C74
0x101cc9b37  mov     [rsp+0EE8h+var_7A0], 20000h
0x101cc9b42  mov     [rsp+0EE8h+var_798], edi
0x101cc9b49  lea     rax, [rsp+0EE8h+var_778]
0x101cc9b51  mov     [rsp+0EE8h+var_790], rax
0x101cc9b59  lea     rax, [rsp+0EE8h+var_758]
0x101cc9b61  mov     [rsp+0EE8h+var_788], rax
0x101cc9b69  mov     [rsp+0EE8h+var_558], rdi
0x101cc9b71  mov     [rsp+0EE8h+var_780], rdi
0x101cc9b79  mov     [rsp+0EE8h+var_550], rdi
0x101cc9b81  lea     rax, [rsp+0EE8h+var_548]
0x101cc9b89  mov     [rsp+0EE8h+var_778], rax
0x101cc9b91  mov     [rsp+0EE8h+var_770], 1Ch
0x101cc9b9c  mov     [rsp+0EE8h+var_76C], 1
0x101cc9ba7  mov     [rsp+0EE8h+var_768], rdi
0x101cc9baf  mov     [rsp+0EE8h+var_760], edi
0x101cc9bb6  mov     [rsp+0EE8h+var_75C], 4
0x101cc9bc1  mov     rax, [rsi]
0x101cc9bc4  mov     rcx, [rax+6B0h]
0x101cc9bcb  movzx   eax, word ptr [rcx+28h]
0x101cc9bcf  mov     [rsp+0EE8h+var_548], eax
0x101cc9bd6  mov     ecx, [rsi+5674h]
0x101cc9bdc  shl     rcx, 20h
0x101cc9be0  mov     eax, [rsi+5678h]
0x101cc9be6  or      rcx, rax
0x101cc9be9  mov     [rsp+0EE8h+var_544], rcx
0x101cc9bf1  movzx   eax, word ptr [rsi+567Ch]
0x101cc9bf8  mov     [rsp+0EE8h+var_53C], eax
0x101cc9bff  movzx   r8d, byte ptr [r15+16h]
0x101cc9c04  mov     [rsp+0EE8h+var_538], r8d
0x101cc9c0c  mov     rax, rdi
0x101cc9c0f  lea     r12, ?logOperations@@3QBULOG_OPERATION@@B; LOG_OPERATION const near * const logOperations
0x101cc9c16  mov     rcx, r12
0x101cc9c19  nop     dword ptr [rax+00000000h]
0x101cc9c20  cmp     [rcx], r8b
0x101cc9c23  jz      short loc_101CC9C57
0x101cc9c25  ja      short loc_101CC9C34
0x101cc9c27  inc     rax
0x101cc9c2a  add     rcx, 10h
0x101cc9c2e  cmp     rax, 57h ; 'W'
0x101cc9c32  jb      short loc_101CC9C20
0x101cc9c34  mov     rcx, rdi
0x101cc9c37  mov     eax, edi
0x101cc9c39  mov     [rsp+0EE8h+var_768], rcx
0x101cc9c41  mov     [rsp+0EE8h+var_760], eax
0x101cc9c48  lea     rcx, [rsp+0EE8h+var_7A8]; this
0x101cc9c50  call    ?Publish@redo_single_record@XeSqlPkg@@QEAAXXZ; XeSqlPkg::redo_single_record::Publish(void)
0x101cc9c55  jmp     short loc_101CC9C7B
0x101cc9c57  mov     rcx, [rcx+8]
0x101cc9c5b  test    rcx, rcx
0x101cc9c5e  jz      short loc_101CC9C37
0x101cc9c60  mov     rax, 0FFFFFFFFFFFFFFFFh
0x101cc9c67  inc     rax
0x101cc9c6a  cmp     [rcx+rax*2], bx
0x101cc9c6e  jnz     short loc_101CC9C67
0x101cc9c70  add     eax, eax
0x101cc9c72  jmp     short loc_101CC9C39
0x101cc9c74  lea     r12, ?logOperations@@3QBULOG_OPERATION@@B; LOG_OPERATION const near * const logOperations
0x101cc9c7b  cmp     byte ptr [rsp+0EE8h+var_E98], bl
0x101cc9c7f  jnz     loc_101CC9D0F
0x101cc9c85  test    r14, r14
0x101cc9c88  jz      loc_101CC9D0F
0x101cc9c8e  mov     r14, [rsi+8450h]
0x101cc9c95  test    r14, r14
0x101cc9c98  jz      short loc_101CC9D0F
0x101cc9c9a  test    byte ptr [r14+210h], 1
0x101cc9ca2  jz      short loc_101CC9D0F
0x101cc9ca4  cmp     word ptr [rsi+567Ch], 1
0x101cc9cac  jz      short loc_101CC9CB7
0x101cc9cae  cmp     [r14+200h], rbx
0x101cc9cb5  jnz     short loc_101CC9D0F
0x101cc9cb7  mov     rdx, [rsp+0EE8h+var_E90]; struct LBH *
0x101cc9cbc  mov     rcx, [r14+1C8h]; this
0x101cc9cc3  call    ?PutLogBlock@LogCacheMgr@@QEAAPEAEPEBVLBH@@@Z; LogCacheMgr::PutLogBlock(LBH const *)
0x101cc9cc8  mov     [r14+200h], rax
0x101cc9ccf  mov     [r14+208h], bl
0x101cc9cd6  test    rax, rax
0x101cc9cd9  jnz     short loc_101CC9D0F
0x101cc9cdb  movzx   r9d, word ptr [rsi+567Ch]
0x101cc9ce3  mov     r8d, [rsi+5678h]
0x101cc9cea  mov     edx, [rsi+5674h]
0x101cc9cf0  lea     rcx, aFailedToEnqueu_4; "Failed to EnqueueLogBlock at lsn %x:%x:"...
0x101cc9cf7  call    ?log_unlocalized_systemmetadata@@YAXPEB_WZZ; log_unlocalized_systemmetadata(wchar_t const *,...)
0x101cc9cfc  xor     edx, edx; bool
0x101cc9cfe  mov     rcx, rsi; this
0x101cc9d01  call    ?ShutdownParallelRedoMgr@RecoveryMgr@@QEAAX_N@Z; RecoveryMgr::ShutdownParallelRedoMgr(bool)
0x101cc9d06  mov     rax, [rsi]
0x101cc9d09  mov     [rax+65F9h], bl
0x101cc9d0f  test    byte ptr [r15+0Eh], 2
0x101cc9d14  jz      loc_101CCA0C8
0x101cc9d1a  mov     eax, [rsi+24h]
0x101cc9d1d  shr     eax, 7
0x101cc9d20  test    al, 1
0x101cc9d22  jnz     loc_101CCA0C8
0x101cc9d28  mov     eax, [r15+10h]
0x101cc9d2c  mov     [rsp+0EE8h+var_D28], eax
0x101cc9d33  movzx   eax, word ptr [r15+14h]
0x101cc9d38  mov     [rsp+0EE8h+var_D24], ax
0x101cc9d40  lea     rcx, [rsi+5BA0h]
0x101cc9d47  lea     rdx, [rsp+0EE8h+var_D28]
0x101cc9d4f  call    ?FindXdes@RecXdesTable@@QEAAPEAVRecXdes@@VXdesId@@@Z; RecXdesTable::FindXdes(XdesId)
0x101cc9d54  mov     r14, rax
0x101cc9d57  mov     rbx, rax
0x101cc9d5a  mov     [rsp+0EE8h+var_E48], rax
0x101cc9d62  test    rax, rax
0x101cc9d65  jz      loc_101CCA0C8
0x101cc9d6b  mov     ecx, [rax+3Ch]
0x101cc9d6e  sub     ecx, 0Ah
0x101cc9d71  mov     [rsp+0EE8h+var_E48], rax
0x101cc9d79  test    ecx, 0FFFFFFFDh
0x101cc9d7f  jz      loc_101CCA0C8
0x101cc9d85  mov     rcx, [rsi]; this
0x101cc9d88  test    byte ptr [rcx+1CD0h], 40h
0x101cc9d8f  jnz     loc_101CCA0C8
0x101cc9d95  mov     r13, [rax+80h]
0x101cc9d9c  cmp     byte ptr [rsp+0EE8h+var_E98], dil
0x101cc9da1  jz      short loc_101CC9DBA
0x101cc9da3  cmp     [rsi+8450h], rdi
0x101cc9daa  jz      short loc_101CC9DBA
0x101cc9dac  mov     eax, [rsi+24h]
0x101cc9daf  shr     eax, 7
0x101cc9db2  test    al, 1
0x101cc9db4  jz      loc_101CC9E58
0x101cc9dba  call    ?IsRecoveryReacquiringLocks@RecoveryUnit@@QEBAHXZ; RecoveryUnit::IsRecoveryReacquiringLocks(void)
0x101cc9dbf  test    eax, eax
0x101cc9dc1  jz      loc_101CC9E58
0x101cc9dc7  mov     eax, [rsi+24h]
0x101cc9dca  shr     eax, 7
0x101cc9dcd  test    al, 1
0x101cc9dcf  jnz     loc_101CC9E58
0x101cc9dd5  mov     rdx, r15; struct LogRec *
0x101cc9dd8  lea     rcx, [rsp+0EE8h+var_528]; this
0x101cc9de0  call    ??0LogLockCollection@@QEAA@PEBVLogRec@@@Z; LogLockCollection::LogLockCollection(LogRec const *)
0x101cc9de5  cmp     [rsi+8470h], dil
0x101cc9dec  jz      short loc_101CC9E09
0x101cc9dee  lea     rdx, [r15+10h]; struct XdesId *
0x101cc9df2  mov     rcx, rsi; this
0x101cc9df5  call    ?IsXdesTranActive@RecoveryMgr@@QEAA_NAEBVXdesId@@@Z; RecoveryMgr::IsXdesTranActive(XdesId const &)
0x101cc9dfa  test    al, al
0x101cc9dfc  jnz     short loc_101CC9E09
0x101cc9dfe  mov     dword ptr [r14+11Ch], 1
0x101cc9e09  lea     rax, ??_7LogLockCollectionAcquire@@6B@; const LogLockCollectionAcquire::`vftable'
0x101cc9e10  mov     [rsp+0EE8h+var_BC0], rax
0x101cc9e18  mov     [rsp+0EE8h+var_BB8], r13
0x101cc9e20  mov     eax, edi
0x101cc9e22  cmp     [r14+11Ch], edi
0x101cc9e29  setnz   al
0x101cc9e2c  mov     r9d, edi
0x101cc9e2f  cmp     dword ptr [r14+58h], 3
0x101cc9e34  cmovnz  r9d, eax; int
0x101cc9e38  mov     rax, [r13+30h]
0x101cc9e3c  lea     r8, [rsp+0EE8h+var_BC0]; struct LogLockCollectionCallback *
0x101cc9e44  movzx   edx, word ptr [rax+6B8h]; unsigned __int16
0x101cc9e4b  lea     rcx, [rsp+0EE8h+var_528]; this
0x101cc9e53  call    ?ApplyLocks@LogLockCollection@@AEAAXGAEAVLogLockCollectionCallback@@H@Z; LogLockCollection::ApplyLocks(ushort,LogLockCollectionCallback &,int)
0x101cc9e58  cmp     [r14+11Ch], edi
0x101cc9e5f  jnz     short loc_101CC9E73
0x101cc9e61  lea     r8, [rsi+5674h]; struct LSN *
0x101cc9e68  mov     rdx, r15; struct LogRec *
0x101cc9e6b  mov     rcx, r13; this
0x101cc9e6e  call    ?RedoReserveForUndo@XdesRMReadWrite@@QEAAXAEBVLogRec@@AEAVLSN@@@Z; XdesRMReadWrite::RedoReserveForUndo(LogRec const &,LSN &)
0x101cc9e73  mov     [rsp+0EE8h+var_E48], rbx
0x101cc9e7b  mov     rax, [rsi]
0x101cc9e7e  cmp     [rax+1CDEh], dil
0x101cc9e85  jz      loc_101CCA02E
0x101cc9e8b  mov     [rsp+0EE8h+var_E48], rbx
0x101cc9e93  mov     rcx, r15; struct LogRec *
0x101cc9e96  call    ?ShouldLogToSLog@XDES@@SA_NPEBVLogRec@@PEBV1@@Z; XDES::ShouldLogToSLog(LogRec const *,XDES const *)
0x101cc9e9b  test    al, al
0x101cc9e9d  jz      loc_101CCA02E
0x101cc9ea3  mov     [rsp+0EE8h+var_E48], rbx
0x101cc9eab  mov     eax, 100h
0x101cc9eb0  test    [r15+0Eh], ax
0x101cc9eb5  jz      loc_101CCA02E
0x101cc9ebb  mov     [rsp+0EE8h+var_E48], rbx
0x101cc9ec3  mov     eax, [rsi+24h]
0x101cc9ec6  shr     eax, 7
0x101cc9ec9  test    al, 1
0x101cc9ecb  jnz     loc_101CCA02E
0x101cc9ed1  mov     rdx, [rsi+8460h]; struct SLogRec *
0x101cc9ed8  test    rdx, rdx
0x101cc9edb  jnz     short loc_101CC9EF0
0x101cc9edd  mov     [rsp+0EE8h+var_E48], rbx
0x101cc9ee5  cmp     byte ptr [rsp+0EE8h+var_E98], dil
0x101cc9eea  jnz     loc_101CCA02E
0x101cc9ef0  mov     rcx, r13; this
0x101cc9ef3  call    ?AttachSLogRecForUndo@XdesRMReadWrite@@QEAAXPEAVSLogRec@@@Z; XdesRMReadWrite::AttachSLogRecForUndo(SLogRec *)
0x101cc9ef8  mov     rax, [rsi+8460h]
0x101cc9eff  mov     rdx, [rax]
0x101cc9f02  movzx   eax, byte ptr [rdx+16h]
0x101cc9f06  cmp     al, 0DFh
0x101cc9f08  jz      short loc_101CC9F1D
0x101cc9f0a  mov     rbx, r14
0x101cc9f0d  mov     [rsp+0EE8h+var_E48], rbx
0x101cc9f15  cmp     al, 0E0h
0x101cc9f17  jnz     loc_101CCA027
0x101cc9f1d  test    byte ptr [rdx+0Eh], 1
0x101cc9f21  jz      short loc_101CC9F85
0x101cc9f23  mov     rcx, [r13+2450h]
0x101cc9f2a  mov     rax, [rcx+8]
0x101cc9f2e  mov     [r13+2450h], rax
0x101cc9f35  mov     [rcx], rdx
0x101cc9f38  mov     [rcx+8], rdi
0x101cc9f3c  cmp     [r13+2440h], rdi
0x101cc9f43  jnz     short loc_101CC9F63
0x101cc9f45  mov     [r13+2440h], rcx
0x101cc9f4c  mov     [r13+2448h], rcx
0x101cc9f53  mov     rbx, r14
0x101cc9f56  mov     [rsp+0EE8h+var_E48], rbx
0x101cc9f5e  jmp     loc_101CCA027
0x101cc9f63  mov     rax, [r13+2448h]
0x101cc9f6a  mov     [rax+8], rcx
0x101cc9f6e  mov     [r13+2448h], rcx
0x101cc9f75  mov     rbx, r14
0x101cc9f78  mov     [rsp+0EE8h+var_E48], rbx
  ... truncated ...
```
