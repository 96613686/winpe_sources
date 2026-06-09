# HaDrDbMgr::ResyncWithPrimary(ulong,int,bool,int,bool)

- ea: `0x100acc4f0`
- end: `0x100acf55c`
- name: `?ResyncWithPrimary@HaDrDbMgr@@IEAA_NKH_NH0@Z`
- size: `12396`
- prototype: `bool __fastcall(HaDrDbMgr *__hidden this, unsigned int, int, bool, int, bool)`
- caller_count: `4`
- callee_count: `45`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x100a9aa90`
- `0x100abb240`
- `0x100abbea0`
- `0x100acfda0`

## callees

- `0x100401380`
- `0x1004013f0`
- `0x100401490`
- `0x100402000`
- `0x100402050`
- `0x100402200`
- `0x1004022e0`
- `0x100402920`
- `0x100415c30`
- `0x10041eb60`
- `0x1004ab5a0`
- `0x1004bf030`
- `0x100553e20`
- `0x1005cd060`
- `0x10063df30`
- `0x100aa7000`
- `0x100aab850`
- `0x100abca30`
- `0x100abe370`
- `0x100abe550`
- `0x100ac3cc0`
- `0x100ac6780`
- `0x100ac6e60`
- `0x100ac8c50`
- `0x100aca720`
- `0x100acc4f0`
- `0x100acf5a0`
- `0x100acf6e0`
- `0x100ad5010`
- `0x100ae1160`
- `0x100aea8c0`
- `0x100af2fe0`
- `0x100af3940`
- `0x100b0e8a0`
- `0x100b17d40`
- `0x100b3feb0`
- `0x100b40190`
- `0x100b49790`
- `0x100b4c980`
- `0x100b4cae0`
- `0x100b4cf70`
- `0x100b4de40`
- `0x100b4e3c0`
- `0x1023aea90`
- `0x1023aef40`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100acda60`
- `KERNEL32!QueryPerformanceCounter` at `0x100acdabe`
- `KERNEL32!QueryPerformanceCounter` at `0x100ace3b9`
- `KERNEL32!QueryPerformanceCounter` at `0x100ace41e`
- `KERNEL32!QueryPerformanceCounter` at `0x100aced92`
- `KERNEL32!QueryPerformanceCounter` at `0x100acedf8`
- `KERNEL32!QueryPerformanceCounter` at `0x100acda60`
- `KERNEL32!QueryPerformanceCounter` at `0x100acdabe`
- `KERNEL32!QueryPerformanceCounter` at `0x100ace3b9`
- `KERNEL32!QueryPerformanceCounter` at `0x100ace41e`
- `KERNEL32!QueryPerformanceCounter` at `0x100aced92`
- `KERNEL32!QueryPerformanceCounter` at `0x100acedf8`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100acd9fe`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100ace357`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100aced30`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100acda80`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100ace3e0`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100acedba`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100acda4c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100acdaaa`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100ace3a5`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100ace40a`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100aced7e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100acede4`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x100acd0c0`
- `sqldk!?g_pAutoXactFactory@@3PEAVIAutoXactFactory@@EA` at `0x100acd053`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x100acce5f`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x100acea24`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100acca1b`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100accc9a`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100acd829`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100acdbe8`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100acdd59`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100acdf7a`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100acf3a6`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100acca1b`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100accc9a`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100acd829`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100acdbe8`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100acdd59`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100acdf7a`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100acf3a6`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100accfe0`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100ace18d`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100ace285`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100ace6f8`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100aceaf8`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100acf0ff`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100accfe0`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100ace18d`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100ace285`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100ace6f8`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100aceaf8`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100acf0ff`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x100acce6d`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x100acdfb1`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x100ace19b`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x100ace5bc`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x100acef28`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100acceee`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100accf19`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100accf4a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100ace917`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100acceee`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100accf19`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100accf4a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100ace917`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100acc967`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100acd653`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100acec2d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100acc967`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100acd653`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100acec2d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100acc61c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100accc15`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100accd9b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100acd1ea`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100acd722`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100acd7a3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100acdb65`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100acde2d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100ace0ee`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100ace545`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100ace799`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100ace84d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100aceb79`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100aceeb1`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100acf177`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100acf2be`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100acc61c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100accc15`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100accd9b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100acd1ea`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100acd722`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100acd7a3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100acdb65`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100acde2d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100ace0ee`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100ace545`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100ace799`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100ace84d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100aceb79`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100aceeb1`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100acf177`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100acf2be`
- `sqldk!SystemThread_TlsIndex` at `0x100acc5ed`
- `sqldk!SystemThread_TlsIndex` at `0x100acc6cd`
- `sqldk!SystemThread_TlsIndex` at `0x100acca69`
- `sqldk!SystemThread_TlsIndex` at `0x100accbe2`
- `sqldk!SystemThread_TlsIndex` at `0x100accce8`
- `sqldk!SystemThread_TlsIndex` at `0x100accd64`
- `sqldk!SystemThread_TlsIndex` at `0x100accfa8`
- `sqldk!SystemThread_TlsIndex` at `0x100acd1b7`
- `sqldk!SystemThread_TlsIndex` at `0x100acd6f3`
- `sqldk!SystemThread_TlsIndex` at `0x100acd770`
- `sqldk!SystemThread_TlsIndex` at `0x100acd899`
- `sqldk!SystemThread_TlsIndex` at `0x100acda1e`
- `sqldk!SystemThread_TlsIndex` at `0x100acdb32`
- `sqldk!SystemThread_TlsIndex` at `0x100acddfe`
- `sqldk!SystemThread_TlsIndex` at `0x100ace074`
- `sqldk!SystemThread_TlsIndex` at `0x100ace154`
- `sqldk!SystemThread_TlsIndex` at `0x100ace24d`
- `sqldk!SystemThread_TlsIndex` at `0x100ace377`
- `sqldk!SystemThread_TlsIndex` at `0x100ace512`
- `sqldk!SystemThread_TlsIndex` at `0x100ace6c0`
- `sqldk!SystemThread_TlsIndex` at `0x100ace766`
- `sqldk!SystemThread_TlsIndex` at `0x100ace81a`
- `sqldk!SystemThread_TlsIndex` at `0x100aceac0`
- `sqldk!SystemThread_TlsIndex` at `0x100aceb42`
- `sqldk!SystemThread_TlsIndex` at `0x100aced50`
- `sqldk!SystemThread_TlsIndex` at `0x100acee7e`
- `sqldk!SystemThread_TlsIndex` at `0x100acf0c6`
- `sqldk!SystemThread_TlsIndex` at `0x100acf144`
- `sqldk!SystemThread_TlsIndex` at `0x100acf28b`
- `sqldk!SystemThread_TlsIndex` at `0x100acf408`
- `sqldk!SystemThread_TlsIndex` at `0x100acf4c8`
- `sqldk!SystemThread_TlsOffset` at `0x100acc5f6`
- `sqldk!SystemThread_TlsOffset` at `0x100acc6d6`
- `sqldk!SystemThread_TlsOffset` at `0x100acca72`
- `sqldk!SystemThread_TlsOffset` at `0x100accbeb`
- `sqldk!SystemThread_TlsOffset` at `0x100acccf1`
- `sqldk!SystemThread_TlsOffset` at `0x100accd6d`
- `sqldk!SystemThread_TlsOffset` at `0x100accfb1`
- `sqldk!SystemThread_TlsOffset` at `0x100acd1c0`
- `sqldk!SystemThread_TlsOffset` at `0x100acd6fc`
- `sqldk!SystemThread_TlsOffset` at `0x100acd779`
- `sqldk!SystemThread_TlsOffset` at `0x100acd8a2`
- `sqldk!SystemThread_TlsOffset` at `0x100acda27`
- `sqldk!SystemThread_TlsOffset` at `0x100acdb3b`
- `sqldk!SystemThread_TlsOffset` at `0x100acde07`
- `sqldk!SystemThread_TlsOffset` at `0x100ace07d`
- `sqldk!SystemThread_TlsOffset` at `0x100ace15d`
- `sqldk!SystemThread_TlsOffset` at `0x100ace256`
- `sqldk!SystemThread_TlsOffset` at `0x100ace380`
- `sqldk!SystemThread_TlsOffset` at `0x100ace51b`
- `sqldk!SystemThread_TlsOffset` at `0x100ace6c9`
- `sqldk!SystemThread_TlsOffset` at `0x100ace76f`
- `sqldk!SystemThread_TlsOffset` at `0x100ace823`
- `sqldk!SystemThread_TlsOffset` at `0x100aceac9`
- `sqldk!SystemThread_TlsOffset` at `0x100aceb4b`
- `sqldk!SystemThread_TlsOffset` at `0x100aced59`
- `sqldk!SystemThread_TlsOffset` at `0x100acee87`
- `sqldk!SystemThread_TlsOffset` at `0x100acf0cf`
- `sqldk!SystemThread_TlsOffset` at `0x100acf14d`
- `sqldk!SystemThread_TlsOffset` at `0x100acf294`
- `sqldk!SystemThread_TlsOffset` at `0x100acf411`
- `sqldk!SystemThread_TlsOffset` at `0x100acf4d1`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100acf08d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100acf08d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100accfca`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100ace177`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100ace26f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100ace6e2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100aceae2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100acf0e9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100accfca`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100ace177`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100ace26f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100ace6e2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100aceae2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100acf0e9`

## string_xrefs

- `0x100ace7fc`: `ResyncWithPrimary - After the first log-snipping during UNDO [%d] - EOL: %08.8X:%08.8X:%04.4X Recovery: %08.8X:%08.8X:%04.4X Undo: %08.8X:%08.8X:%04.4X`
- `0x100ace108`: `HADR_FQDR_XRF: Successfully updated the extended recovery fork stack from primary. Database id: %d, duringStartDB: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=50
char __fastcall HaDrDbMgr::ResyncWithPrimary(
        HaDrDbMgr *this,
        int a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        bool a6)
{
  int v6; // r14d
  unsigned int v7; // r13d
  HaDrDbMgr *v8; // rsi
  HaDrDbMgr *v9; // rdi
  __int64 v10; // rdx
  struct CSessionTraceFlags *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdx
  char *v14; // rcx
  __int64 v15; // rcx
  int Lock; // eax
  __int64 v17; // rcx
  char *v18; // rcx
  __int64 v19; // r12
  char *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  char *v24; // rcx
  char *v25; // rcx
  __int64 v26; // rax
  __int64 (__fastcall ***v27)(_QWORD); // rcx
  __int64 (__fastcall ***v28)(_QWORD); // rcx
  __int64 v29; // rax
  int v30; // ecx
  __int64 v31; // rax
  struct CSessionTraceFlags *v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rdx
  struct CSessionTraceFlags *v36; // rcx
  __int64 (__fastcall ***v37)(_QWORD); // rcx
  int (*v38)(int, int, int, int, char *); // rax
  __int64 v39; // rdi
  __int64 v40; // rcx
  __int64 v41; // rdi
  struct Worker *v42; // rcx
  __int64 v43; // r14
  __int64 v44; // rdi
  char *v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rdi
  __int64 v48; // rax
  __int64 v49; // rax
  char *v50; // rcx
  __int64 v51; // r9
  __int64 v52; // rdx
  struct CSessionTraceFlags *v53; // rcx
  signed __int32 v54; // r8d
  bool v55; // zf
  signed __int32 v56; // eax
  __int64 v57; // rdi
  char v58; // al
  __int64 v59; // rcx
  __int64 v60; // rcx
  unsigned int v61; // eax
  unsigned int v62; // eax
  __int64 (__fastcall ***v63)(_QWORD); // rcx
  __int64 (__fastcall ***v64)(_QWORD); // rcx
  struct RecoveryUnit *v65; // rax
  int v66; // ecx
  int v67; // ecx
  __int64 v68; // rax
  struct CSessionTraceFlags *v69; // rcx
  __int64 v70; // rax
  struct CSessionTraceFlags *v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 (__fastcall ***v74)(_QWORD); // rcx
  __int64 (__fastcall ***v75)(_QWORD); // rcx
  __int64 v76; // rax
  __int64 (__fastcall ***v77)(_QWORD); // rcx
  struct RecoveryUnit *v78; // rax
  HaDrDbMgr *v79; // r14
  volatile signed __int64 *v80; // r13
  DirtyPageMgr *QuadPart; // rdi
  signed __int64 UniqueThread_low; // rdx
  __int64 v83; // r12
  __int64 v84; // r8
  DirtyPageMgr *v85; // rax
  signed __int64 v86; // rcx
  __int64 v87; // rax
  struct CSessionTraceFlags *v88; // rcx
  __int64 v89; // rcx
  char *v90; // rdi
  int v91; // ecx
  unsigned int v92; // r14d
  unsigned int v93; // r9d
  unsigned int v94; // eax
  __int16 v95; // r8
  int v96; // eax
  char *v97; // rcx
  __int64 v98; // rax
  char *v99; // rcx
  __int64 v100; // rdx
  struct CSessionTraceFlags *v101; // rcx
  char *v102; // rcx
  __int64 v103; // rax
  unsigned int v104; // eax
  unsigned int v105; // ecx
  char *v106; // rcx
  __int64 v107; // rax
  int v108; // ecx
  __int64 v109; // rax
  struct CSessionTraceFlags *v110; // rcx
  int v111; // eax
  __int64 v112; // r14
  struct Worker *v113; // rcx
  __int64 v114; // rdi
  struct Worker *v115; // rcx
  unsigned int v116; // ecx
  unsigned int v117; // eax
  __int64 (__fastcall ***v118)(_QWORD); // rcx
  __int64 (__fastcall ***v119)(_QWORD); // rcx
  struct RecoveryUnit *v120; // rax
  HaDrDbMgr *v121; // r14
  volatile signed __int64 *v122; // r9
  DirtyPageMgr *v123; // rdi
  signed __int64 v124; // rdx
  __int64 v125; // r13
  __int64 v126; // r8
  DirtyPageMgr *v127; // rax
  signed __int64 v128; // rcx
  signed __int32 v129; // edx
  signed __int32 v130; // eax
  __int64 v131; // rdx
  struct CSessionTraceFlags *v132; // rcx
  struct IHaDrDbMgr *v133; // rdx
  unsigned int v134; // r12d
  __int64 v135; // rdi
  struct Worker *v136; // rcx
  __int64 (__fastcall ***v137)(_QWORD); // rcx
  __int64 (__fastcall ***v138)(_QWORD); // rcx
  struct RecoveryUnit *v139; // rax
  __int64 v140; // rdx
  struct CSessionTraceFlags *v141; // rcx
  __int64 v142; // rax
  struct CSessionTraceFlags *v143; // rcx
  int v144; // edi
  HaDrDbMgr *v145; // rcx
  __int64 (__fastcall ***v146)(_QWORD); // rcx
  __int64 (__fastcall ***v147)(_QWORD); // rcx
  __int64 v148; // rax
  __int64 *v149; // rcx
  __int64 (__fastcall ***v150)(_QWORD); // rcx
  char *v151; // rcx
  char *v152; // rcx
  __int64 v153; // rax
  __int64 v154; // rdi
  struct Worker *v155; // rcx
  __int64 (__fastcall ***v156)(_QWORD); // rcx
  __int64 v157; // rax
  __int64 v158; // rdx
  struct CSessionTraceFlags *v159; // rcx
  char *v160; // r14
  __int64 (__fastcall ***v161)(_QWORD); // rcx
  __int64 (__fastcall ***v162)(_QWORD); // rcx
  __int64 v163; // rax
  __int64 (__fastcall ***v164)(_QWORD); // rcx
  struct RecoveryUnit *v165; // rax
  volatile signed __int64 *v166; // r9
  DirtyPageMgr *v167; // rdi
  signed __int64 v168; // rdx
  __int64 v169; // r12
  __int64 v170; // r8
  DirtyPageMgr *v171; // rax
  signed __int64 v172; // rcx
  __int64 v173; // rdx
  struct CSessionTraceFlags *v174; // rcx
  __int64 (__fastcall ***v175)(_QWORD); // rcx
  volatile signed __int32 *v176; // rcx
  __int64 v177; // r13
  struct Worker *v178; // rcx
  char *v179; // rcx
  __int64 v180; // rax
  struct CSessionTraceFlags *v181; // rcx
  __int64 (__fastcall ***v182)(_QWORD); // rcx
  __int64 v183; // rax
  __int64 (__fastcall ***v184)(_QWORD); // rcx
  __int64 v185; // rax
  char *v186; // rcx
  __int64 v187; // rdx
  struct CSessionTraceFlags *v188; // rcx
  unsigned __int32 v189; // eax
  __int64 v190; // rcx
  __int64 v191; // rcx
  __int64 v192; // rcx
  __int64 v193; // rcx
  struct CSessionTraceFlags *v194; // rcx
  int v195; // eax
  int v196; // eax
  HaDrDbMgr *v197; // rbx
  int v198; // eax
  HaDrDbMgr *v199; // rbx
  int v200; // ecx
  int v201; // eax
  int v202; // edx
  int v203; // edx
  int v204; // edx
  int v205; // edx
  int v206; // edx
  int v207; // edx
  int v208; // edx
  int v209; // edx
  int v210; // eax
  int v211; // eax
  HaDrDbMgr *v212; // rbx
  int v213; // ecx
  int v214; // eax
  int v215; // edx
  int v216; // edx
  int v217; // edx
  int v218; // edx
  int v219; // edx
  int v220; // edx
  int v221; // edx
  int v222; // edx
  int v223; // eax
  int v224; // eax
  HaDrDbMgr *v225; // rbx
  struct LSN *v226; // [rsp+20h] [rbp-1088h]
  struct LSN *v227; // [rsp+20h] [rbp-1088h]
  int v228; // [rsp+20h] [rbp-1088h]
  struct LSN *v229; // [rsp+20h] [rbp-1088h]
  struct Worker *v230; // [rsp+28h] [rbp-1080h]
  struct Worker *v231; // [rsp+28h] [rbp-1080h]
  struct Worker *v232; // [rsp+28h] [rbp-1080h]
  int *v233; // [rsp+30h] [rbp-1078h]
  bool v234[8]; // [rsp+38h] [rbp-1070h]
  __int64 v235; // [rsp+40h] [rbp-1068h]
  __int64 v236; // [rsp+48h] [rbp-1060h]
  __int64 v237; // [rsp+50h] [rbp-1058h]
  bool v238; // [rsp+90h] [rbp-1018h]
  signed __int64 v239; // [rsp+98h] [rbp-1010h]
  signed __int64 v240; // [rsp+98h] [rbp-1010h]
  signed __int64 v241; // [rsp+98h] [rbp-1010h]
  int v242; // [rsp+A0h] [rbp-1008h]
  int v243; // [rsp+A0h] [rbp-1008h]
  bool v244; // [rsp+A8h] [rbp-1000h]
  int v246; // [rsp+B8h] [rbp-FF0h]
  unsigned __int8 v247; // [rsp+BCh] [rbp-FECh]
  unsigned int v248; // [rsp+C0h] [rbp-FE8h]
  unsigned int v249; // [rsp+C4h] [rbp-FE4h]
  unsigned int v250; // [rsp+D0h] [rbp-FD8h]
  char *v252; // [rsp+E0h] [rbp-FC8h]
  unsigned int v253; // [rsp+E8h] [rbp-FC0h]
  __int64 v254; // [rsp+F0h] [rbp-FB8h]
  char *v255; // [rsp+F0h] [rbp-FB8h]
  volatile signed __int64 *v256; // [rsp+F0h] [rbp-FB8h]
  struct HadrEstablishDB *v257; // [rsp+F8h] [rbp-FB0h]
  int v259; // [rsp+114h] [rbp-F94h] BYREF
  int v260; // [rsp+118h] [rbp-F90h]
  int v261; // [rsp+11Ch] [rbp-F8Ch]
  int v262; // [rsp+120h] [rbp-F88h]
  int v263; // [rsp+124h] [rbp-F84h]
  int v264; // [rsp+128h] [rbp-F80h]
  int v265; // [rsp+12Ch] [rbp-F7Ch] BYREF
  _QWORD *v266; // [rsp+130h] [rbp-F78h] BYREF
  _QWORD v267[2]; // [rsp+138h] [rbp-F70h] BYREF
  __int16 v268; // [rsp+148h] [rbp-F60h]
  __int64 v269; // [rsp+150h] [rbp-F58h]
  _DWORD v270[2]; // [rsp+158h] [rbp-F50h] BYREF
  __int16 v271; // [rsp+160h] [rbp-F48h]
  _DWORD v272[2]; // [rsp+168h] [rbp-F40h] BYREF
  __int16 v273; // [rsp+170h] [rbp-F38h]
  char *v274; // [rsp+178h] [rbp-F30h]
  _WORD *v275; // [rsp+180h] [rbp-F28h]
  _DWORD v276[2]; // [rsp+188h] [rbp-F20h] BYREF
  __int16 v277; // [rsp+190h] [rbp-F18h]
  _DWORD v278[2]; // [rsp+1A0h] [rbp-F08h] BYREF
  __int16 v279; // [rsp+1A8h] [rbp-F00h]
  int v280; // [rsp+1B0h] [rbp-EF8h]
  int v281; // [rsp+1B4h] [rbp-EF4h]
  __int16 v282; // [rsp+1B8h] [rbp-EF0h]
  int v283; // [rsp+1C0h] [rbp-EE8h]
  int v284; // [rsp+1C4h] [rbp-EE4h]
  __int16 v285; // [rsp+1C8h] [rbp-EE0h]
  int v286; // [rsp+1D0h] [rbp-ED8h]
  int v287; // [rsp+1D4h] [rbp-ED4h]
  __int16 v288; // [rsp+1D8h] [rbp-ED0h]
  int v289; // [rsp+1E0h] [rbp-EC8h]
  int v290; // [rsp+1E4h] [rbp-EC4h]
  __int16 v291; // [rsp+1E8h] [rbp-EC0h]
  int v292; // [rsp+1F0h] [rbp-EB8h]
  int v293; // [rsp+1F4h] [rbp-EB4h]
  __int16 v294; // [rsp+1F8h] [rbp-EB0h]
  int v295; // [rsp+200h] [rbp-EA8h]
  int v296; // [rsp+204h] [rbp-EA4h]
  __int16 v297; // [rsp+208h] [rbp-EA0h]
  __int64 v298; // [rsp+210h] [rbp-E98h]
  __int16 v299; // [rsp+218h] [rbp-E90h]
  int v300; // [rsp+220h] [rbp-E88h]
  int v301; // [rsp+224h] [rbp-E84h]
  __int16 v302; // [rsp+228h] [rbp-E80h]
  int v303; // [rsp+230h] [rbp-E78h]
  int v304; // [rsp+234h] [rbp-E74h]
  __int16 v305; // [rsp+238h] [rbp-E70h]
  int v306; // [rsp+240h] [rbp-E68h]
  int v307; // [rsp+244h] [rbp-E64h]
  __int16 v308; // [rsp+248h] [rbp-E60h]
  int v309; // [rsp+250h] [rbp-E58h]
  int v310; // [rsp+254h] [rbp-E54h]
  __int16 v311; // [rsp+258h] [rbp-E50h]
  int v312; // [rsp+260h] [rbp-E48h]
  int v313; // [rsp+264h] [rbp-E44h]
  __int16 v314; // [rsp+268h] [rbp-E40h]
  int v315; // [rsp+270h] [rbp-E38h]
  int v316; // [rsp+274h] [rbp-E34h]
  __int16 v317; // [rsp+278h] [rbp-E30h]
  int v318; // [rsp+280h] [rbp-E28h]
  int v319; // [rsp+284h] [rbp-E24h]
  __int16 v320; // [rsp+288h] [rbp-E20h]
  int v321; // [rsp+290h] [rbp-E18h]
  int v322; // [rsp+294h] [rbp-E14h]
  __int16 v323; // [rsp+298h] [rbp-E10h]
  int v324; // [rsp+2A0h] [rbp-E08h]
  int v325; // [rsp+2A4h] [rbp-E04h]
  __int16 v326; // [rsp+2A8h] [rbp-E00h]
  struct CSessionTraceFlags *v327; // [rsp+2B0h] [rbp-DF8h]
  struct CSessionTraceFlags *v328; // [rsp+2B8h] [rbp-DF0h]
  struct CSessionTraceFlags *v329; // [rsp+2C0h] [rbp-DE8h]
  struct CSessionTraceFlags *v330; // [rsp+2C8h] [rbp-DE0h]
  struct CSessionTraceFlags *v331; // [rsp+2D0h] [rbp-DD8h]
  struct CSessionTraceFlags *v332; // [rsp+2D8h] [rbp-DD0h]
  __int64 v333; // [rsp+2E0h] [rbp-DC8h] BYREF
  __int16 v334; // [rsp+2E8h] [rbp-DC0h]
  __int16 v335; // [rsp+2EAh] [rbp-DBEh]
  __int128 v336; // [rsp+2F0h] [rbp-DB8h] BYREF
  int v337; // [rsp+300h] [rbp-DA8h]
  __int128 v338; // [rsp+308h] [rbp-DA0h] BYREF
  int v339; // [rsp+318h] [rbp-D90h]
  signed __int32 v340; // [rsp+320h] [rbp-D88h]
  signed __int32 v341; // [rsp+324h] [rbp-D84h]
  int v342; // [rsp+328h] [rbp-D80h]
  int v343; // [rsp+330h] [rbp-D78h]
  int v344; // [rsp+338h] [rbp-D70h]
  int v345; // [rsp+340h] [rbp-D68h]
  int v346; // [rsp+348h] [rbp-D60h]
  int v347; // [rsp+350h] [rbp-D58h]
  int v348; // [rsp+358h] [rbp-D50h]
  int v349; // [rsp+360h] [rbp-D48h]
  int v350; // [rsp+368h] [rbp-D40h]
  int v351; // [rsp+370h] [rbp-D38h]
  int v352; // [rsp+378h] [rbp-D30h]
  int v353; // [rsp+380h] [rbp-D28h]
  int v354; // [rsp+388h] [rbp-D20h]
  int v355; // [rsp+390h] [rbp-D18h]
  int v356; // [rsp+398h] [rbp-D10h]
  int v357; // [rsp+3A0h] [rbp-D08h]
  int v358; // [rsp+3A8h] [rbp-D00h]
  int v359; // [rsp+3B0h] [rbp-CF8h]
  int v360; // [rsp+3B8h] [rbp-CF0h]
  int v361; // [rsp+3C0h] [rbp-CE8h]
  int v362; // [rsp+3C8h] [rbp-CE0h]
  __int64 v363; // [rsp+3D0h] [rbp-CD8h]
  __int64 v364; // [rsp+3D8h] [rbp-CD0h]
  LARGE_INTEGER PerformanceCount; // [rsp+3E0h] [rbp-CC8h] BYREF
  LARGE_INTEGER v366; // [rsp+3E8h] [rbp-CC0h] BYREF
  LARGE_INTEGER v367; // [rsp+3F0h] [rbp-CB8h] BYREF
  LARGE_INTEGER v368; // [rsp+3F8h] [rbp-CB0h] BYREF
  LARGE_INTEGER v369; // [rsp+400h] [rbp-CA8h] BYREF
  LARGE_INTEGER v370; // [rsp+408h] [rbp-CA0h] BYREF
  volatile signed __int32 *v371; // [rsp+410h] [rbp-C98h]
  char *v372; // [rsp+418h] [rbp-C90h]
  int v373; // [rsp+420h] [rbp-C88h]
  int v374; // [rsp+428h] [rbp-C80h]
  int v375; // [rsp+430h] [rbp-C78h]
  int v376; // [rsp+438h] [rbp-C70h]
  int v377; // [rsp+440h] [rbp-C68h]
  int v378; // [rsp+448h] [rbp-C60h]
  int v379; // [rsp+450h] [rbp-C58h]
  int v380; // [rsp+458h] [rbp-C50h]
  int v381; // [rsp+460h] [rbp-C48h]
  int v382; // [rsp+468h] [rbp-C40h]
  int v383; // [rsp+470h] [rbp-C38h]
  int v384; // [rsp+478h] [rbp-C30h]
  int v385; // [rsp+480h] [rbp-C28h]
  int v386; // [rsp+488h] [rbp-C20h]
  int v387; // [rsp+490h] [rbp-C18h]
  int v388; // [rsp+498h] [rbp-C10h]
  int v389; // [rsp+4A0h] [rbp-C08h]
  int v390; // [rsp+4A8h] [rbp-C00h]
  int v391; // [rsp+4B0h] [rbp-BF8h]
  int v392; // [rsp+4B8h] [rbp-BF0h]
  int v393; // [rsp+4C0h] [rbp-BE8h]
  __int64 v394; // [rsp+4D0h] [rbp-BD8h] BYREF
  int v395; // [rsp+4D8h] [rbp-BD0h]
  int v396; // [rsp+4E0h] [rbp-BC8h]
  char *v397; // [rsp+4E8h] [rbp-BC0h] BYREF
  int v398; // [rsp+4F0h] [rbp-BB8h]
  char *v399; // [rsp+4F8h] [rbp-BB0h]
  int v400; // [rsp+500h] [rbp-BA8h]
  char *v401; // [rsp+508h] [rbp-BA0h] BYREF
  int v402; // [rsp+510h] [rbp-B98h]
  char *v403; // [rsp+518h] [rbp-B90h] BYREF
  int v404; // [rsp+520h] [rbp-B88h]
  int v405; // [rsp+528h] [rbp-B80h]
  int v406; // [rsp+530h] [rbp-B78h]
  int v407; // [rsp+538h] [rbp-B70h]
  int v408; // [rsp+540h] [rbp-B68h]
  int v409; // [rsp+548h] [rbp-B60h] BYREF
  __int64 *v410; // [rsp+550h] [rbp-B58h]
  __int64 v411; // [rsp+558h] [rbp-B50h]
  int v412; // [rsp+560h] [rbp-B48h]
  __int128 v413; // [rsp+570h] [rbp-B38h] BYREF
  int v414; // [rsp+580h] [rbp-B28h]
  __int128 v415; // [rsp+590h] [rbp-B18h] BYREF
  int v416; // [rsp+5A0h] [rbp-B08h]
  __int128 v417; // [rsp+5B0h] [rbp-AF8h] BYREF
  int v418; // [rsp+5C0h] [rbp-AE8h]
  __int128 v419; // [rsp+5D0h] [rbp-AD8h] BYREF
  int v420; // [rsp+5E0h] [rbp-AC8h]
  __int128 v421; // [rsp+5F0h] [rbp-AB8h] BYREF
  int v422; // [rsp+600h] [rbp-AA8h]
  __int128 v423; // [rsp+610h] [rbp-A98h] BYREF
  int v424; // [rsp+620h] [rbp-A88h]
  __int128 v425; // [rsp+630h] [rbp-A78h] BYREF
  int v426; // [rsp+640h] [rbp-A68h]
  __int128 v427; // [rsp+650h] [rbp-A58h] BYREF
  int v428; // [rsp+660h] [rbp-A48h]
  int v429; // [rsp+668h] [rbp-A40h] BYREF
  __int64 v430; // [rsp+670h] [rbp-A38h]
  __int64 v431; // [rsp+678h] [rbp-A30h]
  __int64 v432; // [rsp+680h] [rbp-A28h]
  __int64 v433; // [rsp+688h] [rbp-A20h]
  int v434; // [rsp+690h] [rbp-A18h] BYREF
  __int64 v435; // [rsp+698h] [rbp-A10h]
  __int64 v436; // [rsp+6A0h] [rbp-A08h]
  __int64 v437; // [rsp+6A8h] [rbp-A00h]
  __int64 v438; // [rsp+6B0h] [rbp-9F8h]
  __int64 v439; // [rsp+6B8h] [rbp-9F0h]
  struct CSessionTraceFlags *v440; // [rsp+6C0h] [rbp-9E8h]
  char *v441; // [rsp+6C8h] [rbp-9E0h]
  char *v442; // [rsp+6D0h] [rbp-9D8h]
  char *v443; // [rsp+6D8h] [rbp-9D0h]
  __int64 v444; // [rsp+6E0h] [rbp-9C8h]
  _DWORD *v445; // [rsp+6E8h] [rbp-9C0h]
  volatile signed __int32 **v446; // [rsp+6F0h] [rbp-9B8h]
  char *v447; // [rsp+6F8h] [rbp-9B0h]
  volatile signed __int32 **v448; // [rsp+700h] [rbp-9A8h]
  volatile signed __int32 *v449; // [rsp+708h] [rbp-9A0h]
  _QWORD *v450; // [rsp+710h] [rbp-998h]
  _QWORD *v451; // [rsp+718h] [rbp-990h]
  _QWORD *v452; // [rsp+720h] [rbp-988h]
  __int64 v453; // [rsp+728h] [rbp-980h]
  __int64 v454; // [rsp+730h] [rbp-978h]
  struct CSessionTraceFlags *v455; // [rsp+738h] [rbp-970h]
  char *v456; // [rsp+740h] [rbp-968h]
  char *v457; // [rsp+748h] [rbp-960h]
  char *v458; // [rsp+750h] [rbp-958h]
  __int64 v459; // [rsp+758h] [rbp-950h]
  __int64 v460; // [rsp+760h] [rbp-948h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+768h] [rbp-940h]
  _QWORD *v462; // [rsp+770h] [rbp-938h]
  _QWORD *v463; // [rsp+778h] [rbp-930h]
  __int64 v464; // [rsp+780h] [rbp-928h]
  __int64 v465; // [rsp+788h] [rbp-920h]
  struct CSessionTraceFlags *v466; // [rsp+790h] [rbp-918h]
  char *v467; // [rsp+798h] [rbp-910h]
  char *v468; // [rsp+7A0h] [rbp-908h]
  _QWORD *v469; // [rsp+7A8h] [rbp-900h]
  _QWORD *v470; // [rsp+7B0h] [rbp-8F8h]
  _QWORD *v471; // [rsp+7B8h] [rbp-8F0h]
  __int64 v472; // [rsp+7C0h] [rbp-8E8h]
  __int64 v473; // [rsp+7C8h] [rbp-8E0h]
  struct CSessionTraceFlags *v474; // [rsp+7D0h] [rbp-8D8h]
  _QWORD *v475; // [rsp+7D8h] [rbp-8D0h]
  _QWORD *v476; // [rsp+7E0h] [rbp-8C8h]
  _QWORD *v477; // [rsp+7E8h] [rbp-8C0h]
  __int64 v478; // [rsp+7F0h] [rbp-8B8h]
  __int64 v479; // [rsp+7F8h] [rbp-8B0h]
  struct CSessionTraceFlags *v480; // [rsp+800h] [rbp-8A8h]
  char *v481; // [rsp+808h] [rbp-8A0h]
  char *v482; // [rsp+810h] [rbp-898h]
  char *v483; // [rsp+818h] [rbp-890h]
  _DWORD *v484; // [rsp+820h] [rbp-888h]
  char *v485; // [rsp+828h] [rbp-880h]
  _BYTE v486[16]; // [rsp+830h] [rbp-878h] BYREF
  _BYTE v487[16]; // [rsp+840h] [rbp-868h] BYREF
  _BYTE v488[16]; // [rsp+850h] [rbp-858h] BYREF
  _BYTE v489[16]; // [rsp+860h] [rbp-848h] BYREF
  _BYTE v490[16]; // [rsp+870h] [rbp-838h] BYREF
  _BYTE v491[16]; // [rsp+880h] [rbp-828h] BYREF
  _QWORD *v492; // [rsp+890h] [rbp-818h]
  _QWORD *v493; // [rsp+898h] [rbp-810h]
  _QWORD *v494; // [rsp+8A0h] [rbp-808h]
  __int64 v495; // [rsp+8A8h] [rbp-800h]
  __int64 v496; // [rsp+8B0h] [rbp-7F8h]
  struct CSessionTraceFlags *v497; // [rsp+8B8h] [rbp-7F0h]
  char *v498; // [rsp+8C0h] [rbp-7E8h]
  char *v499; // [rsp+8C8h] [rbp-7E0h]
  char *v500; // [rsp+8D0h] [rbp-7D8h]
  _DWORD *v501; // [rsp+8D8h] [rbp-7D0h]
  char *v502; // [rsp+8E0h] [rbp-7C8h]
  _QWORD *v503; // [rsp+8E8h] [rbp-7C0h]
  _QWORD *v504; // [rsp+8F0h] [rbp-7B8h]
  _QWORD *v505; // [rsp+8F8h] [rbp-7B0h]
  __int64 v506; // [rsp+900h] [rbp-7A8h]
  __m128i v507; // [rsp+908h] [rbp-7A0h]
  __m128i v508; // [rsp+918h] [rbp-790h]
  __m128i v509; // [rsp+928h] [rbp-780h]
  __m128i v510; // [rsp+938h] [rbp-770h]
  __m128i v511; // [rsp+948h] [rbp-760h]
  __m128i v512; // [rsp+958h] [rbp-750h]
  __m128i v513; // [rsp+968h] [rbp-740h]
  __m128i v514; // [rsp+978h] [rbp-730h]
  _BYTE v515[24]; // [rsp+988h] [rbp-720h] BYREF
  _BYTE v516[40]; // [rsp+9A0h] [rbp-708h] BYREF
  _BYTE v517[40]; // [rsp+9C8h] [rbp-6E0h] BYREF
  _BYTE v518[40]; // [rsp+9F0h] [rbp-6B8h] BYREF
  _BYTE v519[40]; // [rsp+A18h] [rbp-690h] BYREF
  _BYTE v520[40]; // [rsp+A40h] [rbp-668h] BYREF
  _BYTE v521[40]; // [rsp+A68h] [rbp-640h] BYREF
  __int64 v522; // [rsp+A90h] [rbp-618h] BYREF
  unsigned __int16 v523; // [rsp+A98h] [rbp-610h]
  __int64 v524; // [rsp+AA0h] [rbp-608h] BYREF
  unsigned __int16 v525; // [rsp+AA8h] [rbp-600h]
  _QWORD v526[2]; // [rsp+AB0h] [rbp-5F8h] BYREF
  _QWORD v527[2]; // [rsp+AC0h] [rbp-5E8h] BYREF
  char v528; // [rsp+AD0h] [rbp-5D8h]
  __int64 v529; // [rsp+AD8h] [rbp-5D0h]
  HaDrDbMgr *v530; // [rsp+AE0h] [rbp-5C8h]
  __int64 v531; // [rsp+AE8h] [rbp-5C0h]
  __int64 v532; // [rsp+AF0h] [rbp-5B8h]
  int v533; // [rsp+AF8h] [rbp-5B0h]
  __int16 v534; // [rsp+AFCh] [rbp-5ACh]
  __int64 v535; // [rsp+AFEh] [rbp-5AAh]
  __int16 v536; // [rsp+B06h] [rbp-5A2h]
  __int64 v537; // [rsp+B10h] [rbp-598h] BYREF
  __int16 v538; // [rsp+B18h] [rbp-590h]
  _DWORD v539[2]; // [rsp+B20h] [rbp-588h] BYREF
  __int16 v540; // [rsp+B28h] [rbp-580h]
  __int64 v541; // [rsp+B30h] [rbp-578h] BYREF
  __int16 v542; // [rsp+B38h] [rbp-570h]
  __int64 v543; // [rsp+B40h] [rbp-568h] BYREF
  __int16 v544; // [rsp+B48h] [rbp-560h]
  __int64 v545; // [rsp+B50h] [rbp-558h] BYREF
  __int16 v546; // [rsp+B58h] [rbp-550h]
  _QWORD v547[2]; // [rsp+B60h] [rbp-548h] BYREF
  _DWORD v548[2]; // [rsp+B70h] [rbp-538h] BYREF
  __int16 v549; // [rsp+B78h] [rbp-530h]
  GUID v550; // [rsp+B7Ch] [rbp-52Ch]
  int v551; // [rsp+B8Ch] [rbp-51Ch]
  volatile signed __int32 *v552; // [rsp+B90h] [rbp-518h] BYREF
  _BYTE v553[16]; // [rsp+B98h] [rbp-510h] BYREF
  __int128 v554; // [rsp+BA8h] [rbp-500h]
  __int128 v555; // [rsp+BB8h] [rbp-4F0h]
  _BYTE v556[1088]; // [rsp+BD0h] [rbp-4D8h] BYREF

  v459 = -2;
  v6 = (unsigned __int8)a4;
  v238 = a4;
  v7 = a3;
  v250 = a3;
  LODWORD(v274) = a2;
  v8 = this;
  v9 = this;
  v244 = a4;
  v275 = 0;
  v259 = -1;
  v246 = -1;
  v248 = 0;
  v265 = 0;
  v522 = 0;
  v523 = 0;
  if ( (qword_10317B028 & 2) != 0
    || (v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
        *(_QWORD *)v10)
    && (v11 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v10 + 56LL)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v11, 0x2541u) )
  {
    LogSystemMetadataNotSentToClient(
      L"ResyncWithPrimary - Entering ... [%d] - EOL: %08.8X:%08.8X:%04.4X Recovery: %08.8X:%08.8X:%04.4X Undo: %08.8X:%08.8X:%04.4X",
      *((unsigned int *)v8 + 70),
      *((unsigned int *)v8 + 50),
      *((unsigned int *)v8 + 51),
      *((unsigned __int16 *)v8 + 104),
      *((_DWORD *)v8 + 410),
      *((_DWORD *)v8 + 411),
      1,
      *((_DWORD *)v8 + 53),
      *((_DWORD *)v8 + 54),
      *((unsigned __int16 *)v8 + 110));
  }
  if ( !v7 )
  {
    v248 = *((_DWORD *)v8 + 70);
    v247 = 3;
    v249 = 17;
    v12 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                              + SystemThread_TlsIndex)
                                            + SystemThread_TlsOffset
                                            + 8LL)
                                + 104LL)
                    + 40LL);
    LOBYTE(v233) = 0;
    LOBYTE(a4) = 3;
    v246 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, int, _DWORD, _DWORD))(*(_QWORD *)v12 + 160LL))(
             v12,
             v248,
             17,
             a4,
             -1,
             0,
             (_DWORD)v233);
    if ( v246 < 0 )
    {
      _mm_lfence();
      LOBYTE(v13) = 14;
      lck_StandardHandler((unsigned int)v246, v13);
    }
  }
  v269 = 0;
  v524 = 0;
  v525 = 0;
  v14 = (char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136;
  v15 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 24LL))(v14);
  v526[0] = &HadrExtendedRecoveryForkStack::`vftable';
  v526[1] = v15;
  v528 = 0;
  v527[1] = v527;
  v527[0] = v527;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  v526[0] = &HadrRemoteExtendedRecoveryForkStack::`vftable';
  v529 = 0;
  v530 = v8;
  v531 = 0;
  v532 = 64;
  v533 = 0;
  v534 = 0;
  v535 = 0;
  v536 = 0;
  v266 = v526;
  v267[0] = 0;
  AutoHadrXrfMutex::Wait((AutoHadrXrfMutex *)v267);
  v267[1] = 0;
  v268 = 1;
  if ( v526 )
  {
    v267[0] = (*(__int64 (__fastcall **)(_QWORD *))(*v266 + 8LL))(v526);
    AutoHadrXrfMutex::Wait((AutoHadrXrfMutex *)v267);
  }
  if ( (*((_DWORD *)v8 + 366) & 2) == 0 || *((_DWORD *)v8 + 400) )
  {
    v192 = v267[0];
    if ( v267[0] )
    {
      *(_QWORD *)(v267[0] + 48LL) = 0;
      EventAutoInternal<SuspendQueueSLock>::Signal(v192, 0);
      v267[0] = 0;
    }
    HadrExtendedRecoveryForkStack::~HadrExtendedRecoveryForkStack((HadrExtendedRecoveryForkStack *)v526);
    if ( v246 >= 0 )
    {
      v193 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                 + SystemThread_TlsIndex)
                                               + SystemThread_TlsOffset
                                               + 8LL)
                                   + 104LL)
                       + 40LL);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v193 + 168LL))(
        v193,
        v248,
        v249,
        v247,
        0);
    }
    return 0;
  }
  v429 = 4195175;
  v430 = 0;
  v432 = 0;
  v431 = 0;
  v433 = 0;
  v252 = (char *)v8 + 4584;
  v253 = 0;
  Lock = SOS_RWLock::GetLock((char *)v8 + 4584, 1, 0xFFFFFFFFLL, &v429);
  if ( Lock )
  {
    if ( Lock == 2 )
    {
      LOBYTE(v17) = 20;
      RaiseExecutionAbortedError(v17);
    }
  }
  else
  {
    v253 = 1;
  }
  v18 = (char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 4LL) + 136;
  v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 24LL))(v18);
  v254 = v19;
  v275 = (_WORD *)v19;
  if ( !v19 )
    ex_raise(195, 15, 17, 1);
  if ( *((_BYTE *)v8 + 1576)
    && (v20 = (char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136,
        (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v20 + 32LL))(v20))
    || (v554 = *(_OWORD *)((char *)v8 + 812), v555 = *(_OWORD *)((char *)v8 + 828), *(_OWORD *)(v19 + 472) == v554)
    && *(_OWORD *)(v19 + 488) == v555 )
  {
    if ( v253 )
      SOS_RWLock::ReleaseLock(v252, v253);
    v21 = v267[0];
    if ( v267[0] )
    {
      *(_QWORD *)(v267[0] + 48LL) = 0;
      EventAutoInternal<SuspendQueueSLock>::Signal(v21, 0);
      v267[0] = 0;
    }
    HadrExtendedRecoveryForkStack::~HadrExtendedRecoveryForkStack((HadrExtendedRecoveryForkStack *)v526);
    if ( v246 >= 0 )
    {
      v22 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                + SystemThread_TlsIndex)
                                              + SystemThread_TlsOffset
                                              + 8LL)
                                  + 104LL)
                      + 40LL);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v22 + 168LL))(
        v22,
        v248,
        v249,
        v247,
        0);
    }
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    return 1;
  }
  DbMgrPartner::StopScan((DbMgrPartner *)v19);
  v24 = (char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136;
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v24 + 8LL))(v24) )
  {
    v25 = (char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136;
    v26 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v25 + 8LL))(v25);
    v541 = 0;
    v542 = 0;
    (*(void (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v26 + 144LL))(v26, &v541, 0);
  }
  HadrExtendedRecoveryForkStack::Reset((HadrExtendedRecoveryForkStack *)v526);
  v529 = v19;
  if ( *((_DWORD *)v8 + 401)
    || (v27 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136), !(**v27)(v27))
    || (v28 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136),
        v29 = (**v28)(v28),
        v30 = *(_DWORD *)(v29 + 1656),
        v30 != 4)
    && *(_DWORD *)(v29 + 1652) != 4
    && v30 != 3 )
  {
    v37 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136);
    if ( !(**v37)(v37) )
      goto LABEL_311;
    HaDrDbMgr::ValidateNewSecondaryStatus(v8, *((_DWORD *)v8 + 401));
    *((_QWORD *)v8 + 205) = -1;
    try
    {
      v38 = (int (*)(int, int, int, int, char *))hdl_backout;
      if ( *((_DWORD *)v8 + 401) )
        v38 = hdl_prntbackout;
      ExcHandler::ExcHandler((ExcHandler *)v516, 0, 0, 0, v38, 0);
      v39 = HaDrDbMgr::SendEstablishDBAndWaitForReponse(v8, v19, (unsigned int)v274, *((_DWORD *)v8 + 401) != 0, v6);
      v460 = v39;
      v269 = v39;
      if ( !v39 )
        utassert_fail(1u, "a_conversation != NULL", "hadrdbmgrinternal.cpp", 3357, 0);
      v40 = *(_QWORD *)(v39 + 72);
      if ( !v40 )
      {
        utassert_fail(1u, "a_conversation->GetMessage () != NULL", "hadrdbmgrinternal.cpp", 3358, 0);
        v40 = *(_QWORD *)(v39 + 72);
      }
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v40 + 88LL))(v40) != 8 )
        utassert_fail(
          1u,
          "a_conversation->GetMessage ()->GetMessageType () == HADR_MSG_TYPE(EstablishDB)",
          "hadrdbmgrinternal.cpp",
          3359,
          0);
      v257 = *(struct HadrEstablishDB **)(v39 + 72);
      ExcHandler::~ExcHandler((ExcHandler *)v516);
    }
    catch ( SQLError v427 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v486, (const struct SQLError *)&v427);
        v350 = 9537;
        if ( (qword_10317B028 & 2) != 0 )
          goto LABEL_401;
        v351 = 88;
        ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
        v462 = (_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v463 = v462;
        v464 = *v462;
        v465 = v464;
        if ( v464 )
        {
          v194 = **(struct CSessionTraceFlags ***)(v464 + 56);
          v466 = v194;
          if ( v194 )
          {
            v330 = v194;
            v195 = CSessionTraceFlags::CheckSessionTraceInternal(v194, 0x2541u);
LABEL_400:
            if ( !v195 )
            {
LABEL_402:
              v413 = v427;
              v414 = v428;
              ex_raisecontrol(&v413);
              ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v486);
              goto LABEL_563;
            }
LABEL_401:
            v467 = (char *)this + 1640;
            v352 = *((_DWORD *)this + 411);
            v353 = *((_DWORD *)this + 410);
            v318 = v353;
            v319 = v352;
            v320 = 1;
            v468 = (char *)this + 1640;
            v354 = v352;
            v355 = *((_DWORD *)this + 410);
            v292 = v355;
            v293 = v352;
            v294 = 1;
            v372 = (char *)this + 1640;
            v356 = v352;
            v357 = *((_DWORD *)this + 410);
            v321 = v357;
            v322 = v352;
            v323 = 1;
            LogSystemMetadataNotSentToClient(
              L"ResyncWithPrimary - Failed to send establishdb message to primary [%d] - EOL: %08.8X:%08.8X:%04.4X Recover"
               "y: %08.8X:%08.8X:%04.4X Undo: %08.8X:%08.8X:%04.4X",
              *((unsigned int *)this + 70),
              *((unsigned int *)this + 50),
              *((unsigned int *)this + 51),
              *((unsigned __int16 *)this + 104),
              v357,
              v352,
              1,
              *((_DWORD *)this + 53),
              *((_DWORD *)this + 54),
              *((unsigned __int16 *)this + 110));
            goto LABEL_402;
          }
          v330 = 0;
        }
        else
        {
          v330 = 0;
        }
        v195 = 0;
        goto LABEL_400;
      }
      catch ( ShortStackException )
      {
      }
LABEL_563:
      v238 = v244;
      v250 = a3;
      v8 = this;
    }
    v41 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v42 = *(struct Worker **)(v41 + 256);
    if ( !v42 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v42 = *(struct Worker **)(v41 + 256);
    }
    if ( *((_DWORD *)v42 + 139) )
      ExceptionPostCatchActions(v42);
    if ( !dword_103172528 && a6 && !FSystemDBId(*((_DWORD *)v8 + 70)) )
    {
      v333 = *((_QWORD *)v257 + 16);
      v334 = *((_WORD *)v257 + 68);
      v335 = *((_WORD *)v257 + 69);
      v363 = 0;
      v43 = (*(__int64 (__fastcall **)(struct IAutoXactFactory *))(*(_QWORD *)g_pAutoXactFactory + 8LL))(g_pAutoXactFactory);
      v363 = v43;
      (*(void (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v43 + 8LL))(
        v43,
        L"HaDrDbMgr::PersistPrimaryHardenedLsn",
        72);
      v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 64LL))(v43);
      v45 = (char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136;
      v46 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v45 + 24LL))(v45);
      v47 = ((__int64 (__fastcall **)(__int64, __int64, const char *, __int64))g_metadataFactory)[5](
              v46,
              v44,
              "sql\\ntdbms\\hadr\\src\\HadrDbMgrInternal.cpp",
              3210);
      v364 = v47;
      v48 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v47 + 56LL))(
              v47,
              1,
              0,
              0,
              0,
              0);
      v49 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v48 + 752LL))(v48);
      v409 = 44288;
      v412 = 0;
      v410 = &v333;
      v411 = 10;
      LOBYTE(v228) = 1;
      (*(void (__fastcall **)(__int64, __int64, int *, _QWORD, int))(*(_QWORD *)v49 + 16LL))(
        v49,
        76,
        &v409,
        *((unsigned int *)v8 + 70),
        v228);
      v364 = 0;
      (**(void (__fastcall ***)(__int64, __int64))v47)(v47, 1);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 32LL))(v43);
      (**(void (__fastcall ***)(__int64, __int64))v43)(v43, 1);
    }
    v50 = (char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136;
    if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v50 + 32LL))(v50) && byte_10316EAF2 )
    {
      if ( (qword_10317B028 & 2) != 0
        || (v52 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset,
            *(_QWORD *)v52)
        && (v53 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v52 + 56LL)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v53, 0x2541u) )
      {
        LODWORD(v237) = *((unsigned __int16 *)v8 + 110);
        LODWORD(v236) = *((_DWORD *)v8 + 54);
        LODWORD(v235) = *((_DWORD *)v8 + 53);
        *(_DWORD *)v234 = 1;
        LODWORD(v233) = *((_DWORD *)this + 411);
        LODWORD(v231) = *((_DWORD *)v8 + 410);
        LODWORD(v227) = *((unsigned __int16 *)v8 + 104);
        LogSystemMetadataNotSentToClient(
          L"ResyncWithPrimary - Stop Primary scan manager before updating recovery fork on forwarder.  [%d] - EOL: %08.8X:"
           "%08.8X:%04.4X Recovery: %08.8X:%08.8X:%04.4X Undo: %08.8X:%08.8X:%04.4X",
          *((unsigned int *)v8 + 70),
          *((unsigned int *)v8 + 50),
          *((unsigned int *)v8 + 51),
          v227,
          v231,
          v233,
          *(_QWORD *)v234,
          v235,
          v236,
          v237);
      }
      if ( (*(_BYTE *)(*((_QWORD *)this + 216) + 1464LL) & 1) != 0 && (*((_BYTE *)this + 1816) & 1) != 0 )
      {
LABEL_88:
        v54 = *((_DWORD *)this + 473);
        do
        {
          if ( (v54 & 1) != 0 )
          {
            _mm_pause();
            goto LABEL_88;
          }
          v56 = _InterlockedCompareExchange((volatile signed __int32 *)this + 473, v54 | 1, v54);
          v55 = v54 == v56;
          v54 = v56;
        }
        while ( !v55 );
        *((_BYTE *)this + 1888) = 0;
        *((_DWORD *)this + 473) = v56 + 2;
      }
      LOBYTE(v227) = 0;
      LOBYTE(v51) = 1;
      (*(void (__fastcall **)(__int64, __int64, _QWORD, __int64, _DWORD))(*((_QWORD *)v8 + 211) + 8LL))(
        (__int64)v8 + 1688,
        1,
        0,
        v51,
        (_DWORD)v227);
    }
    DbMgrPartner::SetState(v19, 1, "HaDrDbMgr::ResyncWithPrimary");
    v508 = *(__m128i *)(v19 + 488);
    v509 = v508;
    v510 = v508;
    v511 = v508;
    v512 = v508;
    v513 = v508;
    v514 = v508;
    v507 = v508;
    LODWORD(v237) = (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v508, 8));
    LODWORD(v236) = HIWORD(v508.m128i_i64[0]);
    LODWORD(v235) = v508.m128i_u16[2];
    *(_DWORD *)v234 = _mm_cvtsi128_si32(v508);
    v57 = v19;
    LODWORD(v231) = *(_DWORD *)(v19 + 520);
    scierrlog(
      0x89C2u,
      35417,
      35418,
      *((unsigned int *)v8 + 71),
      (char *)v8 + 288,
      v231,
      v19 + 524,
      *(_QWORD *)v234,
      v235,
      v236,
      v237,
      _mm_srli_si128(v508, 8).m128i_u8[1],
      _mm_srli_si128(v508, 8).m128i_u8[2],
      _mm_srli_si128(v508, 8).m128i_u8[3],
      _mm_srli_si128(v508, 8).m128i_u8[4],
      _mm_srli_si128(v508, 8).m128i_u8[5],
      _mm_srli_si128(v508, 8).m128i_u8[6],
      *(__int32 *)((char *)&_mm_srli_si128(v508, 8).m128i_i32[1] + 3));
    v58 = 0;
    if ( dword_103172528 )
    {
      v59 = *((_QWORD *)v8 + 124);
      if ( v59 )
        v58 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v59 + 736LL))(v59, v19 + 472);
    }
    HaDrDbMgr::ValidateNewSecondaryRecoveryPoint(
      v8,
      v257,
      (struct HadrExtendedRecoveryForkIterator *)&v266,
      v238,
      (struct LSN *)&v524,
      (struct LSN *)v553,
      &v265,
      v58);
    if ( dword_103172528 )
    {
      v60 = *((_QWORD *)v8 + 124);
      if ( v60 )
      {
        if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v60 + 176LL))(v60)
          && !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)v8 + 124) + 184LL))(*((_QWORD *)v8 + 124)) )
        {
          if ( (v61 = *((_DWORD *)v8 + 50), (unsigned int)v524 < v61)
            || (_DWORD)v524 == v61
            && ((v62 = *((_DWORD *)v8 + 51), HIDWORD(v524) < v62) || HIDWORD(v524) == v62 && v525 < *((_WORD *)v8 + 104))
            || (v63 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136),
                (**v63)(v63))
            && (v64 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136),
                v65 = (struct RecoveryUnit *)(**v64)(v64),
                (unsigned int)HadrRecoveryCallbacks::IsPageUndoInProgress(v65)) )
          {
            (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v8 + 124) + 648LL))(*((_QWORD *)v8 + 124), 13);
            v394 = *((_QWORD *)v8 + 25);
            v395 = *((_DWORD *)v8 + 52);
            v66 = *((_DWORD *)v8 + 411);
            v278[0] = *((_DWORD *)v8 + 410);
            v278[1] = v66;
            v279 = 1;
            LODWORD(v232) = *((_DWORD *)v8 + 70);
            ex_raise(416, 42, 25, 0, (char *)v8 + 288, v232, v278, &v394);
          }
        }
      }
    }
    if ( *((_DWORD *)v8 + 401) )
    {
      v67 = *((_DWORD *)v8 + 2998);
      if ( (unsigned int)(v67 - 1) > 2 && (unsigned int)(v67 - 6) > 1 || byte_10316E81E )
      {
        while ( !v528 )
          (*(void (__fastcall **)(_QWORD *))(v526[0] + 16LL))(v526);
        HadrLocalExtendedRecoveryForkStack::CopyRecoveryForkStack(
          (HaDrDbMgr *)((char *)v8 + 11696),
          (struct HadrExtendedRecoveryForkIterator *)&v266);
        if ( (qword_10317B028 & 2) != 0
          || (v68 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset)) != 0
          && (v69 = **(struct CSessionTraceFlags ***)(v68 + 56)) != 0
          && CSessionTraceFlags::CheckSessionTraceInternal(v69, 0x2541u) )
        {
          LogSystemMetadataNotSentToClient(
            L"HADR_FQDR_XRF: Successfully copied the extended recovery fork stack from primary. Database id: %d",
            *((unsigned int *)v8 + 70));
        }
      }
      HaDrDbMgr::BringSecondaryIntoHadron(v8, v257, v238);
      HadrDbMgrTruncationMgr::PersistTruncationLsnInBootPage((HaDrDbMgr *)((char *)v8 + 4200));
      if ( (qword_10317B028 & 2) != 0
        || (v70 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset)) != 0
        && (v71 = **(struct CSessionTraceFlags ***)(v70 + 56)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v71, 0x2541u) )
      {
        LODWORD(v237) = *((unsigned __int16 *)v8 + 110);
        LODWORD(v236) = *((_DWORD *)v8 + 54);
        LODWORD(v235) = *((_DWORD *)v8 + 53);
        *(_DWORD *)v234 = 1;
        LODWORD(v233) = *((_DWORD *)this + 411);
        LODWORD(v232) = *((_DWORD *)v8 + 410);
        LODWORD(v229) = *((unsigned __int16 *)v8 + 104);
        LogSystemMetadataNotSentToClient(
          L"ResyncWithPrimary - Restart Database for Join [%d] - EOL: %08.8X:%08.8X:%04.4X Recovery: %08.8X:%08.8X:%04.4X "
           "Undo: %08.8X:%08.8X:%04.4X",
          *((unsigned int *)v8 + 70),
          *((unsigned int *)v8 + 50),
          *((unsigned int *)v8 + 51),
          v229,
          v232,
          v233,
          *(_QWORD *)v234,
          v235,
          v236,
          v237);
      }
      SOS_RWLock::ReleaseLock(v252, v253);
      HaDrDbMgr::AsyncDbRestart(v8, 0, 0);
      v72 = v267[0];
      if ( v267[0] )
      {
        *(_QWORD *)(v267[0] + 48LL) = 0;
        EventAutoInternal<SuspendQueueSLock>::Signal(v72, 0);
        v267[0] = 0;
      }
LABEL_127:
      HadrExtendedRecoveryForkStack::~HadrExtendedRecoveryForkStack((HadrExtendedRecoveryForkStack *)v526);
      if ( v269 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v269 + 16LL))(v269);
      if ( v246 >= 0 )
      {
        v73 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                  + SystemThread_TlsIndex)
                                                + SystemThread_TlsOffset
                                                + 8LL)
                                    + 104LL)
                        + 40LL);
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v73 + 168LL))(
          v73,
          v248,
          v249,
          v247,
          0);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
      return 0;
    }
    if ( (unsigned int)HaDrDbMgr::GetSuspendResumeFromMetaData(v8, &v259) == 2 )
    {
      v74 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136);
      if ( (**v74)(v74)
        && ((v75 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136),
             v76 = (**v75)(v75),
             *(_WORD *)(v76 + 7316))
         || *(_QWORD *)(v76 + 7308)
         || (v77 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136),
             v78 = (struct RecoveryUnit *)(**v77)(v77),
             (unsigned int)HadrRecoveryCallbacks::IsPageUndoPending(v78))) )
      {
        v79 = this;
        v80 = (volatile signed __int64 *)((char *)this + 4416);
        v397 = (char *)this + 4416;
        v398 = 0;
        QuadPart = 0;
        UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        v239 = UniqueThread_low;
        if ( *((_DWORD *)this + 1104) || _InterlockedCompareExchange64(v80, UniqueThread_low, 0) )
        {
          v83 = 0;
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v84 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            if ( v84 && *(_QWORD *)(v84 + 272) == v84 )
              v83 = *(_QWORD *)(v84 + 256);
            if ( v83 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&PerformanceCount);
                QuadPart = (DirtyPageMgr *)PerformanceCount.QuadPart;
              }
              else
              {
                QuadPart = MEMORY[0x7FFE0008];
              }
            }
            UniqueThread_low = v239;
          }
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(v80, UniqueThread_low);
          else
            Spinlock<25,1,268435714>::SpinToAcquireOptimistic(v80, v83, UniqueThread_low);
          if ( v83 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v366);
              v85 = (DirtyPageMgr *)v366.QuadPart;
            }
            else
            {
              v85 = MEMORY[0x7FFE0008];
            }
            v86 = v85 - QuadPart;
            if ( v85 < QuadPart )
              v86 = 0;
            *(_QWORD *)(v83 + 3192) += v86;
          }
        }
        v398 = 1;
        *((_DWORD *)this + 1106) = 0;
        *((_QWORD *)this + 554) = 0;
        SpinlockHolder<25,1,268435714>::~SpinlockHolder<25,1,268435714>(&v397);
        v57 = v254;
      }
      else
      {
        v79 = this;
      }
      if ( (qword_10317B028 & 2) != 0
        || (v87 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset)) != 0
        && (v88 = **(struct CSessionTraceFlags ***)(v87 + 56)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v88, 0x2541u) )
      {
        LODWORD(v237) = *((unsigned __int16 *)v8 + 110);
        LODWORD(v236) = *((_DWORD *)v8 + 54);
        LODWORD(v235) = *((_DWORD *)v8 + 53);
        *(_DWORD *)v234 = 1;
        LODWORD(v233) = *((_DWORD *)v79 + 411);
        LODWORD(v232) = *((_DWORD *)v8 + 410);
        LODWORD(v229) = *((unsigned __int16 *)v8 + 104);
        LogSystemMetadataNotSentToClient(
          L"ResyncWithPrimary - Suspended Exit [%d] - EOL: %08.8X:%08.8X:%04.4X Recovery: %08.8X:%08.8X:%04.4X Undo: %08.8X:%08.8X:%04.4X",
          *((unsigned int *)v8 + 70),
          *((unsigned int *)v8 + 50),
          *((unsigned int *)v8 + 51),
          v229,
          v232,
          v233,
          *(_QWORD *)v234,
          v235,
          v236,
          v237);
      }
      if ( v253 )
        SOS_RWLock::ReleaseLock(v252, v253);
      v89 = v267[0];
      if ( v267[0] )
      {
        *(_QWORD *)(v267[0] + 48LL) = 0;
        EventAutoInternal<SuspendQueueSLock>::Signal(v89, 0);
        v267[0] = 0;
      }
      goto LABEL_127;
    }
    v90 = (char *)v8 + 1640;
    v255 = (char *)v8 + 1640;
    *((_QWORD *)v8 + 205) = *((_QWORD *)v257 + 26);
    v91 = *((_DWORD *)v8 + 2998);
    if ( ((unsigned int)(v91 - 1) > 2 && (unsigned int)(v91 - 6) > 1 || byte_10316E81E)
      && (*((_BYTE *)v257 + 378) & 4) == 0 )
    {
      *(_QWORD *)v90 = v524;
    }
    v434 = 4195168;
    v435 = 0;
    v437 = 0;
    v436 = 0;
    v438 = 0;
    v399 = (char *)v8 + 4648;
    v92 = 0;
    v400 = 0;
    if ( !(unsigned int)SOS_RWLock::GetLock((char *)v8 + 4648, 2, 0xFFFFFFFFLL, &v434) )
    {
      v92 = 2;
      v400 = 2;
      v93 = *((_DWORD *)v257 + 20);
      if ( v93 > *((_DWORD *)v8 + 1054)
        || v93 == *((_DWORD *)v8 + 1054)
        && ((v94 = *((_DWORD *)v257 + 21), v94 > *((_DWORD *)v8 + 1055))
         || v94 == *((_DWORD *)v8 + 1055) && *((_WORD *)v257 + 44) > *((_WORD *)v8 + 2112)) )
      {
        v95 = *((_WORD *)v257 + 44);
        v96 = *((_DWORD *)v257 + 21);
        *((_DWORD *)v8 + 1054) = v93;
        *((_DWORD *)v8 + 1055) = v96;
        *((_WORD *)v8 + 2112) = v95;
      }
      HadrDbMgrTruncationMgr::UpdateHadronTruncationLsn((HaDrDbMgr *)((char *)v8 + 4200), 0);
    }
    if ( v92 )
    {
      SOS_RWLock::ReleaseLock((char *)v8 + 4648, v92);
      v400 = 0;
    }
    v97 = (char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136;
    v98 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v97 + 8LL))(v97);
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v98 + 368LL))(v98, &v522);
    if ( *((_WORD *)v8 + 104) != v523 || *((_QWORD *)v8 + 25) != v522 )
    {
      v99 = (char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136;
      if ( !(*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v99 + 32LL))(v99) )
      {
        if ( (qword_10317B028 & 2) != 0
          || (v100 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset,
              *(_QWORD *)v100)
          && (v101 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v100 + 56LL)) != 0
          && CSessionTraceFlags::CheckSessionTraceInternal(v101, 0x2541u) )
        {
          *(_DWORD *)v234 = v523;
          LODWORD(v233) = HIDWORD(v522);
          LODWORD(v232) = v522;
          LODWORD(v229) = *((unsigned __int16 *)v8 + 104);
          LogSystemMetadataNotSentToClient(
            L"HADR_FQDR_XRF: The hardened Lsn is different with end of log Lsn for database id : %d  hardened Lsn: %08.8X:"
             "%08.8X:%04.4X end of log Lsn: %08.8X:%08.8X:%04.4X",
            *((unsigned int *)v8 + 70),
            *((unsigned int *)v8 + 50),
            *((unsigned int *)v8 + 51),
            v229,
            v232,
            v233,
            *(_QWORD *)v234);
        }
        v242 = v523;
        *((_QWORD *)v8 + 25) = v522;
        *((_DWORD *)v8 + 52) = v242;
      }
    }
    v102 = (char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136;
    v103 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v102 + 8LL))(v102);
    v104 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v103 + 320LL))(v103);
    v7 = v250;
    if ( v250 )
    {
      if ( *((_DWORD *)v8 + 366) == 2 )
      {
        v105 = *((_DWORD *)v8 + 411);
        if ( *(_DWORD *)v90 >= *((_DWORD *)v8 + 50)
          && (*(_DWORD *)v90 != *((_DWORD *)v8 + 50)
           || v105 >= *((_DWORD *)v8 + 51) && (v105 != *((_DWORD *)v8 + 51) || *((_WORD *)v8 + 104) <= 1u))
          && v104 > (unsigned int)v522 )
        {
          _mm_lfence();
          LogSystemMetadataNotSentToClient(
            L"Clear empty VLF [%d] for database id : %d",
            v104,
            *((unsigned int *)v8 + 70));
          v106 = (char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136;
          v107 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v106 + 8LL))(v106);
          (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v107 + 304LL))(v107, &v522);
        }
      }
    }
    SOS_RWLock::ReleaseLock(v252, v253);
    v253 = 0;
    v108 = *((_DWORD *)v8 + 2998);
    if ( ((unsigned int)(v108 - 1) <= 2 || (unsigned int)(v108 - 6) <= 1) && !byte_10316E81E )
      goto LABEL_541;
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v517, 0, 0, 0, hdl_prntbackout, 0);
      if ( (*((_BYTE *)v257 + 378) & 4) != 0 )
        goto LABEL_216;
      v543 = v535;
      v544 = v536;
      HadrLocalExtendedRecoveryForkStack::UpdateRecoveryForkStack(
        (HaDrDbMgr *)((char *)v8 + 11696),
        (struct HadrExtendedRecoveryForkIterator *)&v266,
        (struct LSN *)v553,
        (struct LSN *)&v543,
        (struct LSN *)&v524);
      if ( (qword_10317B028 & 2) != 0 )
        goto LABEL_215;
      v260 = 0;
      v358 = 88;
      v469 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v470 = (_QWORD *)(v469[SystemThread_TlsIndex] + SystemThread_TlsOffset);
      v471 = v470;
      v109 = *v470;
      v472 = v109;
      v473 = v109;
      if ( v109 )
      {
        v110 = **(struct CSessionTraceFlags ***)(v109 + 56);
        v474 = v110;
        if ( v110 )
        {
          v329 = v110;
          v111 = CSessionTraceFlags::CheckSessionTraceInternal(v110, 0x2541u);
          v260 = v111;
LABEL_214:
          if ( !v111 )
          {
LABEL_216:
            ExcHandler::~ExcHandler((ExcHandler *)v517);
            goto LABEL_538;
          }
LABEL_215:
          LogSystemMetadataNotSentToClient(
            L"HADR_FQDR_XRF: Successfully updated the extended recovery fork stack from primary. Database id: %d, duringStartDB: %d",
            *((unsigned int *)v8 + 70),
            v250);
          goto LABEL_216;
        }
        v329 = 0;
      }
      else
      {
        v329 = 0;
      }
      v111 = v260;
      goto LABEL_214;
    }
    catch ( SQLError v415 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v487, (const struct SQLError *)&v415);
        v359 = 9537;
        if ( (qword_10317B028 & 2) != 0 )
          goto LABEL_413;
        v261 = 0;
        v360 = 88;
        v475 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v476 = (_QWORD *)(v475[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v477 = v476;
        v478 = *v476;
        v479 = v478;
        if ( v478 )
        {
          v480 = **(struct CSessionTraceFlags ***)(v478 + 56);
          if ( v480 )
          {
            v328 = v480;
            v196 = CSessionTraceFlags::CheckSessionTraceInternal(v480, 0x2541u);
            v261 = v196;
LABEL_411:
            if ( !v196 )
            {
              v197 = this;
LABEL_414:
              HaDrDbMgr::Suspend(v197, 1, 0);
              v417 = v415;
              v418 = v416;
              ex_raisecontrol(&v417);
              ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v487);
              goto LABEL_568;
            }
LABEL_413:
            v197 = this;
            v481 = (char *)this + 1640;
            v361 = *((_DWORD *)this + 411);
            v362 = *((_DWORD *)this + 410);
            v280 = v362;
            v281 = v361;
            v282 = 1;
            v482 = (char *)this + 1640;
            v373 = v361;
            v374 = *((_DWORD *)this + 410);
            v283 = v374;
            v284 = v361;
            v285 = 1;
            v483 = (char *)this + 1640;
            v375 = v361;
            v376 = *((_DWORD *)this + 410);
            v286 = v376;
            v287 = v361;
            v288 = 1;
            LogSystemMetadataNotSentToClient(
              L"ResyncWithPrimary - Error during XRF stack Update [%d] - EOL: %08.8X:%08.8X:%04.4X Recovery: %08.8X:%08.8X"
               ":%04.4X Undo: %08.8X:%08.8X:%04.4X",
              *((unsigned int *)this + 70),
              *((unsigned int *)this + 50),
              *((unsigned int *)this + 51),
              *((unsigned __int16 *)this + 104),
              v376,
              v361,
              1,
              *((_DWORD *)this + 53),
              *((_DWORD *)this + 54),
              *((unsigned __int16 *)this + 110));
            goto LABEL_414;
          }
          v328 = 0;
        }
        else
        {
          v328 = 0;
        }
        v196 = v261;
        goto LABEL_411;
      }
      catch ( ShortStackException )
      {
      }
LABEL_568:
      v7 = a3;
      v250 = a3;
      v8 = this;
      v90 = v255;
    }
LABEL_538:
    v112 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v113 = *(struct Worker **)(v112 + 256);
    if ( !v113 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v113 = *(struct Worker **)(v112 + 256);
    }
    if ( *((_DWORD *)v113 + 139) )
      ExceptionPostCatchActions(v113);
LABEL_541:
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v518, 0, 0, 0, hdl_prntbackout, 0);
      v484 = v272;
      v485 = v90;
      v377 = *((_DWORD *)v90 + 1);
      v378 = *(_DWORD *)v90;
      v272[0] = v378;
      v272[1] = v377;
      v273 = 1;
      HaDrDbMgr::SyncFixCorruptedPage(v8, v272);
      ExcHandler::~ExcHandler((ExcHandler *)v518);
    }
    catch ( SQLError v336 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v488, (const struct SQLError *)&v336);
        v379 = 9537;
        if ( (qword_10317B028 & 2) != 0 )
          goto LABEL_425;
        v262 = 0;
        v380 = 88;
        v492 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v493 = (_QWORD *)(v492[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v494 = v493;
        v495 = *v493;
        v496 = v495;
        if ( v495 )
        {
          v497 = **(struct CSessionTraceFlags ***)(v495 + 56);
          if ( v497 )
          {
            v332 = v497;
            v198 = CSessionTraceFlags::CheckSessionTraceInternal(v497, 0x2541u);
            v262 = v198;
LABEL_423:
            if ( !v198 )
            {
              v199 = this;
              goto LABEL_426;
            }
LABEL_425:
            v199 = this;
            v498 = (char *)this + 1640;
            v381 = *((_DWORD *)this + 411);
            v382 = *((_DWORD *)this + 410);
            v289 = v382;
            v290 = v381;
            v291 = 1;
            v499 = (char *)this + 1640;
            v383 = v381;
            v384 = *((_DWORD *)this + 410);
            v312 = v384;
            v313 = v381;
            v314 = 1;
            v500 = (char *)this + 1640;
            v385 = v381;
            v386 = *((_DWORD *)this + 410);
            v295 = v386;
            v296 = v381;
            v297 = 1;
            LogSystemMetadataNotSentToClient(
              L"ResyncWithPrimary - Error during fixing corrupted pages [%d] - EOL: %08.8X:%08.8X:%04.4X Recovery: %08.8X:"
               "%08.8X:%04.4X Undo: %08.8X:%08.8X:%04.4X",
              *((unsigned int *)this + 70),
              *((unsigned int *)this + 50),
              *((unsigned int *)this + 51),
              *((unsigned __int16 *)this + 104),
              v386,
              v381,
              1,
              *((_DWORD *)this + 53),
              *((_DWORD *)this + 54),
              *((unsigned __int16 *)this + 110));
LABEL_426:
            v200 = v337;
            v201 = v336;
            if ( v337 == 1 )
              v202 = v336;
            else
              v202 = (unsigned __int16)v336;
            if ( v202 == 35250 )
              goto LABEL_462;
            v203 = v337 == 1 ? v336 : (unsigned __int16)v336;
            if ( v203 == 35293 )
              goto LABEL_462;
            v204 = v337 == 1 ? v336 : (unsigned __int16)v336;
            if ( v204 == 35289 )
              goto LABEL_462;
            v205 = v337 == 1 ? v336 : (unsigned __int16)v336;
            if ( v205 == 35290 )
              goto LABEL_462;
            v206 = v337 == 1 ? v336 : (unsigned __int16)v336;
            if ( v206 == 3617 )
              goto LABEL_462;
            v207 = v337 == 1 ? v336 : (unsigned __int16)v336;
            if ( v207 == 1222 )
              goto LABEL_462;
            v208 = v337 == 1 ? v336 : (unsigned __int16)v336;
            if ( v208 == 1205 )
              goto LABEL_462;
            v209 = v337 == 1 ? v336 : (unsigned __int16)v336;
            if ( v209 == 701 )
              goto LABEL_462;
            if ( v337 != 1 )
              v201 = (unsigned __int16)v336;
            if ( v201 == 19515 )
LABEL_462:
              v210 = 1;
            else
              v210 = 0;
            if ( !v210 )
            {
              HaDrDbMgr::Suspend(v199, 1, 0);
              v200 = v337;
            }
            v419 = v336;
            v420 = v200;
            ex_raisecontrol(&v419);
            ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v488);
            goto LABEL_573;
          }
          v332 = 0;
        }
        else
        {
          v332 = 0;
        }
        v198 = v262;
        goto LABEL_423;
      }
      catch ( ShortStackException )
      {
      }
LABEL_573:
      v7 = a3;
      v250 = a3;
      v8 = this;
    }
    v114 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v115 = *(struct Worker **)(v114 + 256);
    if ( !v115 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v115 = *(struct Worker **)(v114 + 256);
    }
    if ( *((_DWORD *)v115 + 139) )
      ExceptionPostCatchActions(v115);
    v116 = *((_DWORD *)v8 + 411);
    v117 = *((_DWORD *)v8 + 410);
    if ( v117 < (unsigned int)v522
      || v117 == (_DWORD)v522 && (v116 < HIDWORD(v522) || v116 == HIDWORD(v522) && v523 > 1u)
      || (v118 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136),
          (**v118)(v118))
      && (v119 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136),
          v120 = (struct RecoveryUnit *)(**v119)(v119),
          (unsigned int)HadrRecoveryCallbacks::IsPageUndoInProgress(v120)) )
    {
      v121 = this;
      v122 = (volatile signed __int64 *)((char *)this + 4416);
      v401 = (char *)this + 4416;
      v402 = 0;
      v123 = 0;
      v124 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      v240 = v124;
      if ( *((_DWORD *)this + 1104) || _InterlockedCompareExchange64(v122, v124, 0) )
      {
        v125 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v126 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v126 && *(_QWORD *)(v126 + 272) == v126 )
            v125 = *(_QWORD *)(v126 + 256);
          if ( v125 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v367);
              v123 = (DirtyPageMgr *)v367.QuadPart;
              v122 = (volatile signed __int64 *)((char *)this + 4416);
            }
            else
            {
              v123 = MEMORY[0x7FFE0008];
            }
          }
          v124 = v240;
        }
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(v122, v124);
        else
          Spinlock<25,1,268435714>::SpinToAcquireOptimistic(v122, v125, v124);
        if ( v125 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v368);
            v127 = (DirtyPageMgr *)v368.QuadPart;
          }
          else
          {
            v127 = MEMORY[0x7FFE0008];
          }
          v128 = v127 - v123;
          if ( v127 < v123 )
            v128 = 0;
          *(_QWORD *)(v125 + 3192) += v128;
        }
        v7 = v250;
      }
      v402 = 1;
      *((_DWORD *)this + 1106) = 0;
      *((_QWORD *)this + 554) = 0;
      SpinlockHolder<25,1,268435714>::~SpinlockHolder<25,1,268435714>(&v401);
      *((_BYTE *)v8 + 11816) = 1;
      if ( v7 )
      {
        HadrDbMgrState::ChangeState((char *)v8 + 24, 2);
        v298 = 0;
        v299 = 0;
LABEL_256:
        v129 = *((_DWORD *)v8 + 561);
        do
        {
          if ( (v129 & 1) != 0 )
          {
            _mm_pause();
            goto LABEL_256;
          }
          v130 = _InterlockedCompareExchange((volatile signed __int32 *)v8 + 561, v129 | 1, v129);
          v55 = v129 == v130;
          v129 = v130;
        }
        while ( !v55 );
        *((_QWORD *)v8 + 279) = 0;
        *((_DWORD *)v8 + 560) = 0;
        *((_DWORD *)v8 + 561) = v130 + 2;
        if ( (qword_10317B028 & 2) != 0
          || (v131 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset,
              *(_QWORD *)v131)
          && (v132 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v131 + 56LL)) != 0
          && CSessionTraceFlags::CheckSessionTraceInternal(v132, 0x2541u) )
        {
          LODWORD(v237) = *((unsigned __int16 *)v8 + 110);
          LODWORD(v236) = *((_DWORD *)v8 + 54);
          LODWORD(v235) = *((_DWORD *)v8 + 53);
          *(_DWORD *)v234 = 1;
          LODWORD(v233) = *((_DWORD *)this + 411);
          LODWORD(v230) = *((_DWORD *)v8 + 410);
          LODWORD(v226) = *((unsigned __int16 *)v8 + 104);
          LogSystemMetadataNotSentToClient(
            L"ResyncWithPrimary - UNDO [%d] - EOL: %08.8X:%08.8X:%04.4X Recovery: %08.8X:%08.8X:%04.4X Undo: %08.8X:%08.8X:%04.4X",
            *((unsigned int *)v8 + 70),
            *((unsigned int *)v8 + 50),
            *((unsigned int *)v8 + 51),
            v226,
            v230,
            v233,
            *(_QWORD *)v234,
            v235,
            v236,
            v237);
        }
        try
        {
          ExcHandler::ExcHandler((ExcHandler *)v519, 0, 0, 0, hdl_prntbackout, 0);
          if ( v8 )
            v133 = (HaDrDbMgr *)((char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136);
          else
            v133 = 0;
          HaDrUndoMgr::HaDrUndoMgr((HaDrUndoMgr *)v556, v133);
          v501 = v270;
          v502 = (char *)v8 + 1640;
          v387 = *((_DWORD *)v8 + 411);
          v388 = *((_DWORD *)v8 + 410);
          v270[0] = v388;
          v270[1] = v387;
          v271 = 1;
          v134 = a5;
          HaDrUndoMgr::UndoToLSN(v556, v270, a5);
          HaDrUndoMgr::~HaDrUndoMgr((HaDrUndoMgr *)v556);
          ExcHandler::~ExcHandler((ExcHandler *)v519);
        }
        catch ( SQLError v338 )
        {
          try
          {
            ExceptionBackout::ExceptionBackout((ExceptionBackout *)v489, (const struct SQLError *)&v338);
            v389 = 9537;
            if ( (qword_10317B028 & 2) != 0 )
              goto LABEL_476;
            v263 = 0;
            v390 = 88;
            v503 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v504 = (_QWORD *)(v503[SystemThread_TlsIndex] + SystemThread_TlsOffset);
            v505 = v504;
            v506 = *v504;
            v439 = v506;
            if ( v506 )
            {
              v440 = **(struct CSessionTraceFlags ***)(v506 + 56);
              if ( v440 )
              {
                v331 = v440;
                v211 = CSessionTraceFlags::CheckSessionTraceInternal(v440, 0x2541u);
                v263 = v211;
LABEL_474:
                if ( !v211 )
                {
                  v212 = this;
                  goto LABEL_477;
                }
LABEL_476:
                v212 = this;
                v441 = (char *)this + 1640;
                v391 = *((_DWORD *)this + 411);
                v392 = *((_DWORD *)this + 410);
                v300 = v392;
                v301 = v391;
                v302 = 1;
                v442 = (char *)this + 1640;
                v393 = v391;
                v396 = *((_DWORD *)this + 410);
                v303 = v396;
                v304 = v391;
                v305 = 1;
                v443 = (char *)this + 1640;
                v405 = v391;
                v406 = *((_DWORD *)this + 410);
                v306 = v406;
                v307 = v391;
                v308 = 1;
                LogSystemMetadataNotSentToClient(
                  L"ResyncWithPrimary - Error during UNDO [%d] - EOL: %08.8X:%08.8X:%04.4X Recovery: %08.8X:%08.8X:%04.4X "
                   "Undo: %08.8X:%08.8X:%04.4X",
                  *((unsigned int *)this + 70),
                  *((unsigned int *)this + 50),
                  *((unsigned int *)this + 51),
                  *((unsigned __int16 *)this + 104),
                  v406,
                  v391,
                  1,
                  *((_DWORD *)this + 53),
                  *((_DWORD *)this + 54),
                  *((unsigned __int16 *)this + 110));
LABEL_477:
                v213 = v339;
                v214 = v338;
                if ( v339 == 1 )
                  v215 = v338;
                else
                  v215 = (unsigned __int16)v338;
                if ( v215 == 35250 )
                  goto LABEL_513;
                v216 = v339 == 1 ? v338 : (unsigned __int16)v338;
                if ( v216 == 35293 )
                  goto LABEL_513;
                v217 = v339 == 1 ? v338 : (unsigned __int16)v338;
                if ( v217 == 35289 )
                  goto LABEL_513;
                v218 = v339 == 1 ? v338 : (unsigned __int16)v338;
                if ( v218 == 35290 )
                  goto LABEL_513;
                v219 = v339 == 1 ? v338 : (unsigned __int16)v338;
                if ( v219 == 3617 )
                  goto LABEL_513;
                v220 = v339 == 1 ? v338 : (unsigned __int16)v338;
                if ( v220 == 1222 )
                  goto LABEL_513;
                v221 = v339 == 1 ? v338 : (unsigned __int16)v338;
                if ( v221 == 1205 )
                  goto LABEL_513;
                v222 = v339 == 1 ? v338 : (unsigned __int16)v338;
                if ( v222 == 701 )
                  goto LABEL_513;
                if ( v339 != 1 )
                  v214 = (unsigned __int16)v338;
                if ( v214 == 19515 )
LABEL_513:
                  v223 = 1;
                else
                  v223 = 0;
                if ( !v223 )
                {
                  HaDrDbMgr::Suspend(v212, 1, 0);
                  v213 = v339;
                }
                v421 = v338;
                v422 = v213;
                ex_raisecontrol(&v421);
                ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v489);
                goto LABEL_578;
              }
              v331 = 0;
            }
            else
            {
              v331 = 0;
            }
            v211 = v263;
            goto LABEL_474;
          }
          catch ( ShortStackException )
          {
          }
LABEL_578:
          v134 = a5;
          v7 = a3;
          v8 = this;
          v121 = this;
        }
        v135 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v136 = *(struct Worker **)(v135 + 256);
        if ( !v136 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v136 = *(struct Worker **)(v135 + 256);
        }
        if ( *((_DWORD *)v136 + 139) )
          ExceptionPostCatchActions(v136);
        v137 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136);
        if ( (**v137)(v137)
          && (v138 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136),
              v139 = (struct RecoveryUnit *)(**v138)(v138),
              (unsigned int)HadrRecoveryCallbacks::IsPageUndoInProgress(v139)) )
        {
          if ( v134 )
          {
            if ( (qword_10317B028 & 2) != 0
              || (v140 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset,
                  *(_QWORD *)v140)
              && (v141 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v140 + 56LL)) != 0
              && CSessionTraceFlags::CheckSessionTraceInternal(v141, 0x2541u) )
            {
              LODWORD(v237) = *((unsigned __int16 *)v8 + 110);
              LODWORD(v236) = *((_DWORD *)v8 + 54);
              LODWORD(v235) = *((_DWORD *)v8 + 53);
              *(_DWORD *)v234 = 1;
              LODWORD(v233) = *((_DWORD *)v121 + 411);
              LODWORD(v230) = *((_DWORD *)v8 + 410);
              LODWORD(v226) = *((unsigned __int16 *)v8 + 104);
              LogSystemMetadataNotSentToClient(
                L"ResyncWithPrimary - After the first log-snipping during UNDO [%d] - EOL: %08.8X:%08.8X:%04.4X Recovery: "
                 "%08.8X:%08.8X:%04.4X Undo: %08.8X:%08.8X:%04.4X",
                *((unsigned int *)v8 + 70),
                *((unsigned int *)v8 + 50),
                *((unsigned int *)v8 + 51),
                v226,
                v230,
                v233,
                *(_QWORD *)v234,
                v235,
                v236,
                v237);
            }
          }
          else
          {
            utassert_fail(1u, "0", "hadrdbmgrinternal.cpp", 3776, 0);
          }
        }
        else
        {
          HaDrDbMgr::DeleteRecoveryLsnFromMetadata(v8);
          v146 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136);
          if ( (**v146)(v146) )
          {
            v147 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136);
            v148 = (**v147)(v147);
            v545 = *(_QWORD *)(v148 + 7308);
            v546 = *(_WORD *)(v148 + 7316);
            v149 = &v545;
          }
          else
          {
            v537 = 0;
            v538 = 0;
            v149 = &v537;
          }
          v243 = *((unsigned __int16 *)v149 + 4);
          *(_QWORD *)((char *)v8 + 212) = *v149;
          *((_DWORD *)v8 + 55) = v243;
          v150 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136);
          if ( (**v150)(v150) )
          {
            v151 = (char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136;
            if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v151 + 8LL))(v151) )
            {
              try
              {
                ExcHandler::ExcHandler((ExcHandler *)v520, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_backout, 0);
                v152 = (char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136;
                v153 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v152 + 8LL))(v152);
                v539[0] = 0;
                v539[1] = 0;
                v540 = 0;
                (*(void (__fastcall **)(__int64, _DWORD *, _QWORD))(*(_QWORD *)v153 + 144LL))(v153, v539, 0);
                ExcHandler::~ExcHandler((ExcHandler *)v520);
              }
              catch ( SQLError v515 )
              {
                try
                {
                  ExceptionBackout::ExceptionBackout((ExceptionBackout *)v490, (const struct SQLError *)v515);
                  ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v490);
                }
                catch ( ShortStackException )
                {
                }
                v7 = a3;
                v8 = this;
                v121 = this;
              }
              v154 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset;
              v155 = *(struct Worker **)(v154 + 256);
              if ( !v155 )
              {
                SystemThread::MakeMiniSOSThread(0);
                v155 = *(struct Worker **)(v154 + 256);
              }
              if ( *((_DWORD *)v155 + 139) )
                ExceptionPostCatchActions(v155);
              v156 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136);
              v157 = (**v156)(v156);
              BPool::FlushCache(qword_10317B628, 0, v157, 100);
            }
          }
          if ( (qword_10317B028 & 2) != 0
            || (v158 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset,
                *(_QWORD *)v158)
            && (v159 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v158 + 56LL)) != 0
            && CSessionTraceFlags::CheckSessionTraceInternal(v159, 0x2541u) )
          {
            LODWORD(v237) = *((unsigned __int16 *)v8 + 110);
            LODWORD(v236) = *((_DWORD *)v8 + 54);
            LODWORD(v235) = *((_DWORD *)v8 + 53);
            *(_DWORD *)v234 = 1;
            LODWORD(v233) = *((_DWORD *)v121 + 411);
            LODWORD(v230) = *((_DWORD *)v8 + 410);
            LODWORD(v226) = *((unsigned __int16 *)v8 + 104);
            LogSystemMetadataNotSentToClient(
              L"ResyncWithPrimary - After UNDO [%d] - EOL: %08.8X:%08.8X:%04.4X Recovery: %08.8X:%08.8X:%04.4X Undo: %08.8X:%08.8X:%04.4X",
              *((unsigned int *)v8 + 70),
              *((unsigned int *)v8 + 50),
              *((unsigned int *)v8 + 51),
              v226,
              v230,
              v233,
              *(_QWORD *)v234,
              v235,
              v236,
              v237);
          }
        }
      }
      if ( (qword_10317B028 & 2) != 0
        || (v142 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset)) != 0
        && (v143 = **(struct CSessionTraceFlags ***)(v142 + 56)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v143, 0x2541u) )
      {
        LODWORD(v237) = *((unsigned __int16 *)v8 + 110);
        LODWORD(v236) = *((_DWORD *)v8 + 54);
        LODWORD(v235) = *((_DWORD *)v8 + 53);
        *(_DWORD *)v234 = 1;
        LODWORD(v233) = *((_DWORD *)v121 + 411);
        LODWORD(v230) = *((_DWORD *)v8 + 410);
        LODWORD(v226) = *((unsigned __int16 *)v8 + 104);
        LogSystemMetadataNotSentToClient(
          L"ResyncWithPrimary - Restart Database [%d] - EOL: %08.8X:%08.8X:%04.4X Recovery: %08.8X:%08.8X:%04.4X Undo: %08"
           ".8X:%08.8X:%04.4X",
          *((unsigned int *)v8 + 70),
          *((unsigned int *)v8 + 50),
          *((unsigned int *)v8 + 51),
          v226,
          v230,
          v233,
          *(_QWORD *)v234,
          v235,
          v236,
          v237);
      }
      if ( byte_10316E754 )
      {
        v144 = *((_DWORD *)v8 + 70);
        if ( (unsigned int)IsReplicatedMasterEnabled() || (unsigned int)IsContainedAGEnabledInstance() )
        {
          if ( v144 == 32763 )
            HaDrDbMgr::DelayKillingSessionsHoldingReplMasterLocks(v145);
          else
            IsContainedAGEnabledInstance();
        }
      }
      HaDrDbMgr::AsyncDbRestart(v8, 1, 0);
      LODWORD(v226) = *((_DWORD *)v8 + 71);
      ex_raise(352, 78, 17, 1, v226, (char *)v8 + 288);
    }
    HaDrDbMgr::DeleteRecoveryLsnFromMetadata(v8);
    v9 = this;
    goto LABEL_311;
  }
  if ( (unsigned int)HaDrDbMgr::GetSuspendResumeFromMetaData(v8, &v259) == 2 )
  {
    if ( (qword_10317B028 & 2) != 0
      || (v31 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset)) != 0
      && (v32 = **(struct CSessionTraceFlags ***)(v31 + 56)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v32, 0x2541u) )
    {
      LODWORD(v237) = *((unsigned __int16 *)v8 + 110);
      LODWORD(v236) = *((_DWORD *)v8 + 54);
      LODWORD(v235) = *((_DWORD *)v8 + 53);
      *(_DWORD *)v234 = 1;
      LODWORD(v233) = *((_DWORD *)v8 + 411);
      LODWORD(v230) = *((_DWORD *)v8 + 410);
      LODWORD(v226) = *((unsigned __int16 *)v8 + 104);
      LogSystemMetadataNotSentToClient(
        L"ResyncWithPrimary - Suspended + Damaged Exit [%d] - EOL: %08.8X:%08.8X:%04.4X Recovery: %08.8X:%08.8X:%04.4X Und"
         "o: %08.8X:%08.8X:%04.4X",
        *((unsigned int *)v8 + 70),
        *((unsigned int *)v8 + 50),
        *((unsigned int *)v8 + 51),
        v226,
        v230,
        v233,
        *(_QWORD *)v234,
        v235,
        v236,
        v237);
    }
    if ( v253 )
      SOS_RWLock::ReleaseLock(v252, v253);
    v33 = v267[0];
    if ( v267[0] )
    {
      *(_QWORD *)(v267[0] + 48LL) = 0;
      EventAutoInternal<SuspendQueueSLock>::Signal(v33, 0);
      v267[0] = 0;
    }
    HadrExtendedRecoveryForkStack::~HadrExtendedRecoveryForkStack((HadrExtendedRecoveryForkStack *)v526);
    if ( v246 >= 0 )
    {
      v34 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                + SystemThread_TlsIndex)
                                              + SystemThread_TlsOffset
                                              + 8LL)
                                  + 104LL)
                      + 40LL);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v34 + 168LL))(
        v34,
        v248,
        v249,
        v247,
        0);
    }
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    return 0;
  }
  if ( (qword_10317B028 & 2) != 0
    || (v35 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
        *(_QWORD *)v35)
    && (v36 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v35 + 56LL)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v36, 0x2541u) )
  {
    LODWORD(v237) = *((unsigned __int16 *)v8 + 110);
    LODWORD(v236) = *((_DWORD *)v8 + 54);
    LODWORD(v235) = *((_DWORD *)v8 + 53);
    *(_DWORD *)v234 = 1;
    LODWORD(v233) = *((_DWORD *)v8 + 411);
    LODWORD(v230) = *((_DWORD *)v8 + 410);
    LODWORD(v226) = *((unsigned __int16 *)v8 + 104);
    LogSystemMetadataNotSentToClient(
      L"ResyncWithPrimary - Damaged [%d] - EOL: %08.8X:%08.8X:%04.4X Recovery: %08.8X:%08.8X:%04.4X Undo: %08.8X:%08.8X:%04.4X",
      *((unsigned int *)v8 + 70),
      *((unsigned int *)v8 + 50),
      *((unsigned int *)v8 + 51),
      v226,
      v230,
      v233,
      *(_QWORD *)v234,
      v235,
      v236,
      v237);
  }
LABEL_311:
  v160 = (char *)v8 + 136;
  v274 = (char *)v8 + 136;
  v161 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*((_QWORD *)v8 + 17) + 8LL) + 136);
  if ( (**v161)(v161) )
  {
    v162 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*(_QWORD *)v160 + 8LL) + 136);
    v163 = (**v162)(v162);
    if ( *(_WORD *)(v163 + 7316)
      || *(_QWORD *)(v163 + 7308)
      || (v164 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*(_QWORD *)v160 + 8LL) + 136),
          v165 = (struct RecoveryUnit *)(**v164)(v164),
          (unsigned int)HadrRecoveryCallbacks::IsPageUndoPending(v165)) )
    {
      v166 = (volatile signed __int64 *)((char *)v9 + 4416);
      v256 = (volatile signed __int64 *)((char *)v9 + 4416);
      v403 = (char *)v9 + 4416;
      v404 = 0;
      v167 = 0;
      v168 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      v241 = v168;
      if ( *(_DWORD *)v166 || _InterlockedCompareExchange64(v166, v168, 0) )
      {
        v169 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v170 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v170 && *(_QWORD *)(v170 + 272) == v170 )
            v169 = *(_QWORD *)(v170 + 256);
          if ( v169 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v369);
              v167 = (DirtyPageMgr *)v369.QuadPart;
              v166 = v256;
            }
            else
            {
              v167 = MEMORY[0x7FFE0008];
            }
          }
          v168 = v241;
        }
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(v166, v168);
        else
          Spinlock<25,1,268435714>::SpinToAcquireOptimistic(v166, v169, v168);
        if ( v169 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v370);
            v171 = (DirtyPageMgr *)v370.QuadPart;
          }
          else
          {
            v171 = MEMORY[0x7FFE0008];
          }
          v172 = v171 - v167;
          if ( v171 < v167 )
            v172 = 0;
          *(_QWORD *)(v169 + 3192) += v172;
        }
      }
      v404 = 1;
      v9 = this;
      *((_DWORD *)this + 1106) = 0;
      *((_QWORD *)this + 554) = 0;
      SpinlockHolder<25,1,268435714>::~SpinlockHolder<25,1,268435714>(&v403);
      *((_BYTE *)v8 + 11816) = 1;
    }
  }
  if ( !v7 && !*((_DWORD *)v8 + 403) )
  {
    if ( (qword_10317B028 & 2) != 0
      || (v173 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
          *(_QWORD *)v173)
      && (v174 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v173 + 56LL)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v174, 0x2541u) )
    {
      LODWORD(v237) = *((unsigned __int16 *)v8 + 110);
      LODWORD(v236) = *((_DWORD *)v8 + 54);
      LODWORD(v235) = *((_DWORD *)v8 + 53);
      *(_DWORD *)v234 = 1;
      LODWORD(v233) = *((_DWORD *)v9 + 411);
      LODWORD(v230) = *((_DWORD *)v8 + 410);
      LODWORD(v226) = *((unsigned __int16 *)v8 + 104);
      LogSystemMetadataNotSentToClient(
        L"ResyncWithPrimary - No Undo Needed [%d] - EOL: %08.8X:%08.8X:%04.4X Recovery: %08.8X:%08.8X:%04.4X Undo: %08.8X:%08.8X:%04.4X",
        *((unsigned int *)v8 + 70),
        *((unsigned int *)v8 + 50),
        *((unsigned int *)v8 + 51),
        v226,
        v230,
        v233,
        *(_QWORD *)v234,
        v235,
        v236,
        v237);
    }
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v521, 0, 0, 0, hdl_prntbackout, 0);
      v175 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*(_QWORD *)v160 + 8LL) + 136);
      v444 = (**v175)(v175);
      v547[0] = 0;
      v547[1] = v444;
      v445 = v548;
      v548[0] = 0;
      v548[1] = 0;
      v549 = 0;
      v550 = GUID_NULL;
      v551 = 0;
      v446 = &v552;
      v552 = 0;
      v447 = (char *)v8 + 1640;
      v407 = *((_DWORD *)v8 + 411);
      v408 = *((_DWORD *)v8 + 410);
      v276[0] = v408;
      v276[1] = v407;
      v277 = 1;
      CHadrFsUndoManager::UndoToLsn((CHadrFsUndoManager *)v547, (const struct LSN *)v276, 0, 0);
      v448 = &v552;
      if ( v552 )
      {
        v371 = v552;
        v340 = _InterlockedDecrement(v552);
        v341 = v340;
        if ( !v340 )
        {
          v176 = v371;
          v449 = v371;
          if ( v371 )
          {
            *((_QWORD *)v371 + 4) = &EventManualInternal<SuspendQueueSLock>::`vftable';
            operator delete((void *)v176, 0x58u);
          }
        }
      }
      ExcHandler::~ExcHandler((ExcHandler *)v521);
    }
    catch ( SQLError v423 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v491, (const struct SQLError *)&v423);
        v342 = 9537;
        if ( (qword_10317B028 & 2) != 0 )
          goto LABEL_528;
        v264 = 0;
        v343 = 88;
        v450 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v451 = (_QWORD *)(v450[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v452 = v451;
        v453 = *v451;
        v454 = v453;
        if ( v453 )
        {
          v455 = **(struct CSessionTraceFlags ***)(v453 + 56);
          if ( v455 )
          {
            v327 = v455;
            v224 = CSessionTraceFlags::CheckSessionTraceInternal(v455, 0x2541u);
            v264 = v224;
LABEL_526:
            if ( !v224 )
            {
              v225 = this;
LABEL_529:
              HaDrDbMgr::Suspend(v225, 1, 0);
              v425 = v423;
              v426 = v424;
              ex_raisecontrol(&v425);
              ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v491);
              goto LABEL_588;
            }
LABEL_528:
            v225 = this;
            v456 = (char *)this + 1640;
            v344 = *((_DWORD *)this + 411);
            v345 = *((_DWORD *)this + 410);
            v309 = v345;
            v310 = v344;
            v311 = 1;
            v457 = (char *)this + 1640;
            v346 = v344;
            v347 = *((_DWORD *)this + 410);
            v324 = v347;
            v325 = v344;
            v326 = 1;
            v458 = (char *)this + 1640;
            v348 = v344;
            v349 = *((_DWORD *)this + 410);
            v315 = v349;
            v316 = v344;
            v317 = 1;
            LogSystemMetadataNotSentToClient(
              L"ResyncWithPrimary - Error during FS UNDO [%d] - EOL: %08.8X:%08.8X:%04.4X Recovery: %08.8X:%08.8X:%04.4X U"
               "ndo: %08.8X:%08.8X:%04.4X",
              *((unsigned int *)this + 70),
              *((unsigned int *)this + 50),
              *((unsigned int *)this + 51),
              *((unsigned __int16 *)this + 104),
              v349,
              v344,
              1,
              *((_DWORD *)this + 53),
              *((_DWORD *)this + 54),
              *((unsigned __int16 *)this + 110));
            goto LABEL_529;
          }
          v327 = 0;
        }
        else
        {
          v327 = 0;
        }
        v224 = v264;
        goto LABEL_526;
      }
      catch ( ShortStackException )
      {
      }
LABEL_588:
      v160 = v274;
      v8 = this;
      v9 = this;
    }
    v177 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v178 = *(struct Worker **)(v177 + 256);
    if ( !v178 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v178 = *(struct Worker **)(v177 + 256);
    }
    if ( *((_DWORD *)v178 + 139) )
      ExceptionPostCatchActions(v178);
    v179 = (char *)v8 + *(int *)(*(_QWORD *)v160 + 8LL) + 136;
    if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v179 + 32LL))(v179) && v265 )
    {
      if ( (qword_10317B028 & 2) != 0
        || (v180 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset)) != 0
        && (v181 = **(struct CSessionTraceFlags ***)(v180 + 56)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v181, 0x2541u) )
      {
        LODWORD(v237) = *((unsigned __int16 *)v8 + 110);
        LODWORD(v236) = *((_DWORD *)v8 + 54);
        LODWORD(v235) = *((_DWORD *)v8 + 53);
        *(_DWORD *)v234 = 1;
        LODWORD(v233) = *((_DWORD *)v9 + 411);
        LODWORD(v230) = *((_DWORD *)v8 + 410);
        LODWORD(v226) = *((unsigned __int16 *)v8 + 104);
        LogSystemMetadataNotSentToClient(
          L"ResyncWithPrimary - Force secondary resync for forwarder [%d] - EOL: %08.8X:%08.8X:%04.4X Recovery: %08.8X:%08"
           ".8X:%04.4X Undo: %08.8X:%08.8X:%04.4X",
          *((unsigned int *)v8 + 70),
          *((unsigned int *)v8 + 50),
          *((unsigned int *)v8 + 51),
          v226,
          v230,
          v233,
          *(_QWORD *)v234,
          v235,
          v236,
          v237);
      }
      HadrDbMgrScansController::Restart((char *)v8 + 1688, 0, 0);
    }
    v182 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*(_QWORD *)v160 + 8LL) + 136);
    v183 = (**v182)(v182);
    if ( v275[424] != *(_WORD *)(v183 + 1662) )
    {
      v184 = (__int64 (__fastcall ***)(_QWORD))((char *)v8 + *(int *)(*(_QWORD *)v160 + 8LL) + 136);
      v185 = (**v184)(v184);
      HaDrDbMgr::StartVersionUpgrade(v8, *(_WORD *)(v185 + 1662), 0);
    }
  }
  v186 = (char *)v8 + *(int *)(*(_QWORD *)v160 + 8LL) + 136;
  if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v186 + 32LL))(v186) && byte_10316EAF2 )
  {
    if ( (qword_10317B028 & 2) != 0
      || (v187 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
          *(_QWORD *)v187)
      && (v188 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v187 + 56LL)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v188, 0x2541u) )
    {
      LODWORD(v237) = *((unsigned __int16 *)v8 + 110);
      LODWORD(v236) = *((_DWORD *)v8 + 54);
      LODWORD(v235) = *((_DWORD *)v8 + 53);
      *(_DWORD *)v234 = 1;
      LODWORD(v233) = *((_DWORD *)v9 + 411);
      LODWORD(v230) = *((_DWORD *)v8 + 410);
      LODWORD(v226) = *((unsigned __int16 *)v8 + 104);
      LogSystemMetadataNotSentToClient(
        L"ResyncWithPrimary - Start Primary Scan Manager on forwarder.  [%d] - EOL: %08.8X:%08.8X:%04.4X Recovery: %08.8X:"
         "%08.8X:%04.4X Undo: %08.8X:%08.8X:%04.4X",
        *((unsigned int *)v8 + 70),
        *((unsigned int *)v8 + 50),
        *((unsigned int *)v8 + 51),
        v226,
        v230,
        v233,
        *(_QWORD *)v234,
        v235,
        v236,
        v237);
    }
    if ( (*(_BYTE *)(*((_QWORD *)v9 + 216) + 1464LL) & 1) != 0 && (*((_BYTE *)v9 + 1816) & 1) != 0 )
    {
LABEL_372:
      LODWORD(v187) = *((_DWORD *)v9 + 473);
      do
      {
        if ( (v187 & 1) != 0 )
        {
          _mm_pause();
          goto LABEL_372;
        }
        v189 = _InterlockedCompareExchange((volatile signed __int32 *)v9 + 473, v187 | 1, v187);
        v55 = (_DWORD)v187 == v189;
        v187 = v189;
      }
      while ( !v55 );
      *((_BYTE *)v9 + 1888) = 1;
      *((_DWORD *)v9 + 473) = v189 + 2;
    }
    LOBYTE(v187) = 1;
    (**((void (__fastcall ***)(__int64, __int64, _QWORD))v8 + 211))((__int64)v8 + 1688, v187, 0);
  }
  if ( v253 )
    SOS_RWLock::ReleaseLock(v252, v253);
  v190 = v267[0];
  if ( v267[0] )
  {
    *(_QWORD *)(v267[0] + 48LL) = 0;
    EventAutoInternal<SuspendQueueSLock>::Signal(v190, 0);
    v267[0] = 0;
  }
  HadrExtendedRecoveryForkStack::~HadrExtendedRecoveryForkStack((HadrExtendedRecoveryForkStack *)v526);
  if ( v269 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v269 + 16LL))(v269);
  if ( v246 >= 0 )
  {
    v191 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                               + SystemThread_TlsIndex)
                                             + SystemThread_TlsOffset
                                             + 8LL)
                                 + 104LL)
                     + 40LL);
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v191 + 168LL))(
      v191,
      v248,
      v249,
      v247,
      0);
  }
  if ( !v275 )
    return 1;
  (*(void (__fastcall **)(_WORD *))(*(_QWORD *)v275 + 16LL))(v275);
  return 1;
}

```

## disassembly

```asm
0x100acc4f0  push    rbx
0x100acc4f2  push    rsi
0x100acc4f3  push    rdi
0x100acc4f4  push    r12
0x100acc4f6  push    r13
0x100acc4f8  push    r14
0x100acc4fa  push    r15
0x100acc4fc  mov     eax, 1070h
0x100acc501  call    _alloca_probe
0x100acc506  sub     rsp, rax
0x100acc509  mov     [rsp+10A8h+var_950], 0FFFFFFFFFFFFFFFEh
0x100acc515  movaps  [rsp+10A8h+var_48], xmm6
0x100acc51d  movaps  [rsp+10A8h+var_58], xmm7
0x100acc525  movaps  [rsp+10A8h+var_68], xmm8
0x100acc52e  movaps  [rsp+10A8h+var_78], xmm9
0x100acc537  movaps  [rsp+10A8h+var_88], xmm10
0x100acc540  mov     rax, cs:__security_cookie
0x100acc547  xor     rax, rsp
0x100acc54a  mov     [rsp+10A8h+var_98], rax
0x100acc552  movzx   r14d, r9b
0x100acc556  mov     [rsp+10A8h+var_1018], r14b
0x100acc55e  mov     r13d, r8d
0x100acc561  mov     [rsp+10A8h+var_FD8], r8d
0x100acc569  mov     dword ptr [rsp+10A8h+var_F30], edx
0x100acc570  mov     rsi, rcx
0x100acc573  mov     [rsp+10A8h+var_FF8], rcx
0x100acc57b  mov     rdi, rcx
0x100acc57e  mov     [rsp+10A8h+var_FD0], rcx
0x100acc586  mov     [rsp+10A8h+var_FA0], r8d
0x100acc58e  mov     [rsp+10A8h+var_1000], r14b
0x100acc596  xor     ebx, ebx
0x100acc598  mov     [rsp+10A8h+var_F28], rbx
0x100acc5a0  mov     [rsp+10A8h+var_F94], 0FFFFFFFFh
0x100acc5ab  mov     [rsp+10A8h+var_FF0], 0FFFFFFFFh
0x100acc5b6  mov     [rsp+10A8h+var_FE8], ebx
0x100acc5bd  mov     [rsp+10A8h+var_FE0], ebx
0x100acc5c4  mov     [rsp+10A8h+var_F7C], ebx
0x100acc5cb  mov     [rsp+10A8h+var_618], rbx
0x100acc5d3  mov     [rsp+10A8h+var_610], bx
0x100acc5db  test    byte ptr cs:qword_10317B028, 2
0x100acc5e2  jnz     short loc_100ACC62E
0x100acc5e4  mov     r8, gs:58h
0x100acc5ed  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100acc5f4  mov     ecx, [rax]
0x100acc5f6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100acc5fd  mov     edx, [rax]
0x100acc5ff  add     rdx, [r8+rcx*8]
0x100acc603  mov     rax, [rdx]
0x100acc606  test    rax, rax
0x100acc609  jz      short loc_100ACC626
0x100acc60b  mov     rax, [rax+38h]
0x100acc60f  mov     rcx, [rax]
0x100acc612  test    rcx, rcx
0x100acc615  jz      short loc_100ACC626
0x100acc617  mov     edx, 2541h
0x100acc61c  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100acc622  test    eax, eax
0x100acc624  jnz     short loc_100ACC62E
0x100acc626  mov     r15d, 1
0x100acc62c  jmp     short loc_100ACC699
0x100acc62e  mov     r8d, [rsi+66Ch]
0x100acc635  mov     edx, [rsi+668h]
0x100acc63b  movzx   eax, word ptr [rsi+0DCh]
0x100acc642  movzx   ecx, word ptr [rsi+0D0h]
0x100acc649  mov     dword ptr [rsp+10A8h+var_1058], eax
0x100acc64d  mov     eax, [rsi+0D8h]
0x100acc653  mov     dword ptr [rsp+10A8h+var_1060], eax
0x100acc657  mov     eax, [rsi+0D4h]
0x100acc65d  mov     dword ptr [rsp+10A8h+var_1068], eax
0x100acc661  mov     r15d, 1
0x100acc667  mov     dword ptr [rsp+10A8h+var_1070], r15d
0x100acc66c  mov     dword ptr [rsp+10A8h+var_1078], r8d
0x100acc671  mov     dword ptr [rsp+10A8h+var_1080], edx
0x100acc675  mov     dword ptr [rsp+10A8h+var_1088], ecx
0x100acc679  mov     r9d, [rsi+0CCh]
0x100acc680  mov     r8d, [rsi+0C8h]
0x100acc687  mov     edx, [rsi+118h]
0x100acc68d  lea     rcx, aResyncwithprim_17; "ResyncWithPrimary - Entering ... [%d] -"...
0x100acc694  call    ?LogSystemMetadataNotSentToClient@@YAXPEB_WZZ; LogSystemMetadataNotSentToClient(wchar_t const *,...)
0x100acc699  test    r13d, r13d
0x100acc69c  jnz     loc_100ACC72F
0x100acc6a2  mov     r10d, [rsi+118h]
0x100acc6a9  mov     [rsp+10A8h+var_FE8], r10d
0x100acc6b1  mov     [rsp+10A8h+var_FEC], 3
0x100acc6b9  mov     [rsp+10A8h+var_FE4], 11h
0x100acc6c4  mov     rdx, gs:58h
0x100acc6cd  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100acc6d4  mov     ecx, [rax]
0x100acc6d6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100acc6dd  mov     eax, [rax]
0x100acc6df  add     rax, [rdx+rcx*8]
0x100acc6e3  mov     rax, [rax+8]
0x100acc6e7  mov     rcx, [rax+68h]
0x100acc6eb  mov     rcx, [rcx+28h]
0x100acc6ef  mov     rax, [rcx]
0x100acc6f2  mov     byte ptr [rsp+10A8h+var_1078], r13b
0x100acc6f7  mov     dword ptr [rsp+10A8h+var_1080], ebx
0x100acc6fb  mov     dword ptr [rsp+10A8h+var_1088], 0FFFFFFFFh
0x100acc703  mov     r9b, 3
0x100acc706  lea     r8d, [r13+11h]
0x100acc70a  mov     edx, r10d
0x100acc70d  call    qword ptr [rax+0A0h]
0x100acc713  mov     [rsp+10A8h+var_FF0], eax
0x100acc71a  test    eax, eax
0x100acc71c  jns     short loc_100ACC72F
0x100acc71e  lfence
0x100acc721  mov     dl, 0Eh
0x100acc723  mov     ecx, [rsp+10A8h+var_FF0]
0x100acc72a  call    ?lck_StandardHandler@@YAXW4LCK_RESULT@@W4ABORT_AND_LCK_EXCEPTIONS@@@Z; lck_StandardHandler(LCK_RESULT,ABORT_AND_LCK_EXCEPTIONS)
0x100acc72f  mov     [rsp+10A8h+var_F58], rbx
0x100acc737  mov     [rsp+10A8h+var_FB0], rbx
0x100acc73f  mov     [rsp+10A8h+var_608], rbx
0x100acc747  mov     [rsp+10A8h+var_600], bx
0x100acc74f  mov     rax, [rsi+88h]
0x100acc756  movsxd  rcx, dword ptr [rax+8]
0x100acc75a  add     rcx, 88h
0x100acc761  add     rcx, rsi
0x100acc764  mov     rax, [rcx]
0x100acc767  call    qword ptr [rax+18h]
0x100acc76a  mov     rcx, rax
0x100acc76d  lea     rax, ??_7HadrExtendedRecoveryForkStack@@6B@; const HadrExtendedRecoveryForkStack::`vftable'
0x100acc774  mov     [rsp+10A8h+var_5F8], rax
0x100acc77c  mov     [rsp+10A8h+var_5F0], rcx
0x100acc784  xorps   xmm0, xmm0
0x100acc787  movdqa  [rsp+10A8h+var_5E8], xmm0
0x100acc790  lea     rax, [rsp+10A8h+var_5E8]
0x100acc798  mov     qword ptr [rsp+10A8h+var_5E8+8], rax
0x100acc7a0  lea     rax, [rsp+10A8h+var_5E8]
0x100acc7a8  mov     qword ptr [rsp+10A8h+var_5E8], rax
0x100acc7b0  mov     [rsp+10A8h+var_5D8], 0
0x100acc7b8  lea     rax, [rsp+10A8h+var_5E8]
0x100acc7c0  mov     qword ptr [rsp+10A8h+var_5E8+8], rax
0x100acc7c8  lea     rax, [rsp+10A8h+var_5E8]
0x100acc7d0  mov     qword ptr [rsp+10A8h+var_5E8], rax
0x100acc7d8  test    rcx, rcx
0x100acc7db  jz      short loc_100ACC7E4
0x100acc7dd  mov     rax, [rcx]
0x100acc7e0  call    qword ptr [rax+8]
0x100acc7e3  nop
0x100acc7e4  lea     rax, ??_7HadrRemoteExtendedRecoveryForkStack@@6B@; const HadrRemoteExtendedRecoveryForkStack::`vftable'
0x100acc7eb  mov     [rsp+10A8h+var_5F8], rax
0x100acc7f3  mov     [rsp+10A8h+var_5D0], rbx
0x100acc7fb  mov     [rsp+10A8h+var_5C8], rsi
0x100acc803  mov     [rsp+10A8h+var_5C0], rbx
0x100acc80b  mov     [rsp+10A8h+var_5B8], 40h ; '@'
0x100acc817  mov     [rsp+10A8h+var_5B0], ebx
0x100acc81e  mov     [rsp+10A8h+var_5AC], bx
0x100acc826  mov     [rsp+10A8h+var_5AA], rbx
0x100acc82e  mov     [rsp+10A8h+var_5A2], bx
0x100acc836  lea     rax, [rsp+10A8h+var_5F8]
0x100acc83e  mov     [rsp+10A8h+var_F78], rax
0x100acc846  mov     [rsp+10A8h+var_F70], rbx
0x100acc84e  lea     rcx, [rsp+10A8h+var_F70]; this
0x100acc856  call    ?Wait@AutoHadrXrfMutex@@AEAAXXZ; AutoHadrXrfMutex::Wait(void)
0x100acc85b  nop
0x100acc85c  mov     [rsp+10A8h+var_F68], rbx
0x100acc864  mov     [rsp+10A8h+var_F60], 1
0x100acc86e  mov     rcx, [rsp+10A8h+var_F78]
0x100acc876  test    rcx, rcx
0x100acc879  jz      short loc_100ACC897
0x100acc87b  mov     rax, [rcx]
0x100acc87e  call    qword ptr [rax+8]
0x100acc881  mov     [rsp+10A8h+var_F70], rax
0x100acc889  lea     rcx, [rsp+10A8h+var_F70]; this
0x100acc891  call    ?Wait@AutoHadrXrfMutex@@AEAAXXZ; AutoHadrXrfMutex::Wait(void)
0x100acc896  nop
0x100acc897  mov     eax, [rsi+5B8h]
0x100acc89d  shr     eax, 1
0x100acc89f  test    al, 1
0x100acc8a1  jz      loc_100ACF487
0x100acc8a7  cmp     dword ptr [rsi+640h], 0
0x100acc8ae  jnz     loc_100ACF487
0x100acc8b4  mov     [rsp+10A8h+var_A40], 400367h
0x100acc8bf  mov     [rsp+10A8h+var_A38], rbx
0x100acc8c7  mov     [rsp+10A8h+var_A28], rbx
0x100acc8cf  mov     [rsp+10A8h+var_A30], rbx
0x100acc8d7  mov     [rsp+10A8h+var_A20], rbx
0x100acc8df  lea     rcx, [rsi+11E8h]
0x100acc8e6  mov     [rsp+10A8h+var_FC8], rcx
0x100acc8ee  mov     [rsp+10A8h+var_FC0], ebx
0x100acc8f5  lea     r9, [rsp+10A8h+var_A40]
0x100acc8fd  mov     r8d, 0FFFFFFFFh
0x100acc903  mov     edx, r15d
0x100acc906  call    ?GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z; SOS_RWLock::GetLock(RWLockMode,ulong,SOS_WaitInfo const *)
0x100acc90b  test    eax, eax
0x100acc90d  jnz     short loc_100ACC919
0x100acc90f  mov     [rsp+10A8h+var_FC0], r15d
0x100acc917  jmp     short loc_100ACC925
0x100acc919  cmp     eax, 2
0x100acc91c  jnz     short loc_100ACC925
0x100acc91e  mov     cl, 14h
0x100acc920  call    ?RaiseExecutionAbortedError@@YAXW4ABORT_AND_LCK_EXCEPTIONS@@@Z; RaiseExecutionAbortedError(ABORT_AND_LCK_EXCEPTIONS)
0x100acc925  mov     rax, [rsi+88h]
0x100acc92c  movsxd  rcx, dword ptr [rax+4]
0x100acc930  add     rcx, 88h
0x100acc937  add     rcx, rsi
0x100acc93a  mov     rax, [rcx]
0x100acc93d  call    qword ptr [rax+18h]
0x100acc940  mov     r12, rax
0x100acc943  mov     [rsp+10A8h+var_FB8], rax
0x100acc94b  mov     [rsp+10A8h+var_F28], rax
0x100acc953  test    rax, rax
0x100acc956  jnz     short loc_100ACC96D
0x100acc958  mov     r9d, r15d
0x100acc95b  lea     edx, [rax+0Fh]
0x100acc95e  mov     ecx, 0C3h
0x100acc963  lea     r8d, [rax+11h]
0x100acc967  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100acc96d  cmp     byte ptr [rsi+628h], 0
0x100acc974  jz      short loc_100ACC995
0x100acc976  mov     rax, [rsi+88h]
0x100acc97d  movsxd  rcx, dword ptr [rax+8]
0x100acc981  add     rcx, 88h
0x100acc988  add     rcx, rsi
0x100acc98b  mov     rax, [rcx]
0x100acc98e  call    qword ptr [rax+20h]
0x100acc991  test    al, al
0x100acc993  jnz     short loc_100ACCA08
0x100acc995  movups  xmm1, xmmword ptr [rsi+32Ch]
0x100acc99c  movups  [rsp+10A8h+var_500], xmm1
0x100acc9a4  movups  xmm0, xmmword ptr [rsi+33Ch]
0x100acc9ab  movups  [rsp+10A8h+var_4F0], xmm0
0x100acc9b3  movq    rax, xmm1
0x100acc9b8  cmp     [r12+1D8h], rax
0x100acc9c0  jnz     loc_100ACCAD1
0x100acc9c6  mov     rax, [r12+1E0h]
0x100acc9ce  cmp     rax, qword ptr [rsp+10A8h+var_500+8]
0x100acc9d6  jnz     loc_100ACCAD1
0x100acc9dc  mov     rax, [r12+1E8h]
0x100acc9e4  cmp     rax, qword ptr [rsp+10A8h+var_4F0]
0x100acc9ec  jnz     loc_100ACCAD1
0x100acc9f2  mov     rax, [r12+1F0h]
0x100acc9fa  cmp     rax, qword ptr [rsp+10A8h+var_4F0+8]
0x100acca02  jnz     loc_100ACCAD1
0x100acca08  mov     edx, [rsp+10A8h+var_FC0]
0x100acca0f  test    edx, edx
0x100acca11  jz      short loc_100ACCA28
0x100acca13  mov     rcx, [rsp+10A8h+var_FC8]
0x100acca1b  call    cs:__imp_?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z; SOS_RWLock::ReleaseLock(RWLockMode)
0x100acca21  mov     [rsp+10A8h+var_FC0], ebx
0x100acca28  mov     rcx, [rsp+10A8h+var_F70]
0x100acca30  test    rcx, rcx
0x100acca33  jz      short loc_100ACCA48
0x100acca35  mov     [rcx+30h], rbx
0x100acca39  xor     edx, edx
0x100acca3b  call    ?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x100acca40  mov     [rsp+10A8h+var_F70], rbx
0x100acca48  lea     rcx, [rsp+10A8h+var_5F8]; this
0x100acca50  call    ??1HadrExtendedRecoveryForkStack@@UEAA@XZ; HadrExtendedRecoveryForkStack::~HadrExtendedRecoveryForkStack(void)
0x100acca55  nop
0x100acca56  cmp     [rsp+10A8h+var_FF0], 0
0x100acca5e  jl      short loc_100ACCABB
0x100acca60  mov     rdx, gs:58h
0x100acca69  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100acca70  mov     ecx, [rax]
0x100acca72  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100acca79  mov     eax, [rax]
0x100acca7b  add     rax, [rdx+rcx*8]
0x100acca7f  mov     rax, [rax+8]
0x100acca83  mov     rcx, [rax+68h]
0x100acca87  mov     rcx, [rcx+28h]
0x100acca8b  mov     rax, [rcx]
0x100acca8e  mov     dword ptr [rsp+10A8h+var_1088], ebx
0x100acca92  movzx   r9d, [rsp+10A8h+var_FEC]
0x100acca9b  mov     r8d, [rsp+10A8h+var_FE4]
0x100accaa3  mov     edx, [rsp+10A8h+var_FE8]
0x100accaaa  call    qword ptr [rax+0A8h]
0x100accab0  mov     [rsp+10A8h+var_FF0], 0FFFFFFFFh
0x100accabb  test    r12, r12
0x100accabe  jz      short loc_100ACCACA
0x100accac0  mov     rax, [r12]
0x100accac4  mov     rcx, r12
0x100accac7  call    qword ptr [rax+10h]
0x100accaca  mov     al, 1
0x100accacc  jmp     loc_100ACF51C
0x100accad1  mov     rcx, r12; this
0x100accad4  call    ?StopScan@DbMgrPartner@@QEAAXXZ; DbMgrPartner::StopScan(void)
0x100accad9  mov     rax, [rsi+88h]
0x100accae0  movsxd  rcx, dword ptr [rax+8]
0x100accae4  add     rcx, 88h
0x100accaeb  add     rcx, rsi
0x100accaee  mov     rax, [rcx]
0x100accaf1  call    qword ptr [rax+8]
0x100accaf4  test    rax, rax
0x100accaf7  jz      short loc_100ACCB3C
0x100accaf9  mov     rax, [rsi+88h]
0x100accb00  movsxd  rcx, dword ptr [rax+8]
0x100accb04  add     rcx, 88h
0x100accb0b  add     rcx, rsi
0x100accb0e  mov     rax, [rcx]
0x100accb11  call    qword ptr [rax+8]
0x100accb14  mov     [rsp+10A8h+var_578], rbx
0x100accb1c  mov     [rsp+10A8h+var_570], bx
0x100accb24  mov     r9, [rax]
0x100accb27  xor     r8d, r8d
0x100accb2a  lea     rdx, [rsp+10A8h+var_578]
0x100accb32  mov     rcx, rax
0x100accb35  call    qword ptr [r9+90h]
0x100accb3c  lea     rcx, [rsp+10A8h+var_5F8]; this
0x100accb44  call    ?Reset@HadrExtendedRecoveryForkStack@@IEAAXXZ; HadrExtendedRecoveryForkStack::Reset(void)
  ... truncated ...
```
