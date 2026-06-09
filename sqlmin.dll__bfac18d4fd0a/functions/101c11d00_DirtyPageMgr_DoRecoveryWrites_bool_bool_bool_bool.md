# DirtyPageMgr::DoRecoveryWrites(bool,bool,bool,bool)

- ea: `0x101c11d00`
- end: `0x101c13f27`
- name: `?DoRecoveryWrites@DirtyPageMgr@@QEAAX_N000@Z`
- size: `8743`
- prototype: `void __usercall(DirtyPageMgr *__hidden this@<rcx>, bool@<dl>, bool@<r8b>, bool@<r9b>, bool)`
- caller_count: `4`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x100401a30`
- `0x10043ba50`
- `0x1005d37c0`
- `0x1005f4060`

## callees

- `0x100401010`
- `0x100401380`
- `0x1004013f0`
- `0x100401490`
- `0x100402740`
- `0x10064f990`
- `0x10064fb40`
- `0x1016c9600`
- `0x1016ddcd0`
- `0x101c11d00`
- `0x101c1c090`
- `0x1023aecb0`
- `0x1023af450`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x101c121cc`
- `KERNEL32!QueryPerformanceCounter` at `0x101c123e3`
- `KERNEL32!QueryPerformanceCounter` at `0x101c124c8`
- `KERNEL32!QueryPerformanceCounter` at `0x101c13c97`
- `KERNEL32!QueryPerformanceCounter` at `0x101c121cc`
- `KERNEL32!QueryPerformanceCounter` at `0x101c123e3`
- `KERNEL32!QueryPerformanceCounter` at `0x101c124c8`
- `KERNEL32!QueryPerformanceCounter` at `0x101c13c97`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101c121ba`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101c123cf`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101c12424`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101c124b4`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101c124f2`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101c13c83`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101c13cca`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101c12430`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101c124fe`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101c13cd6`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101c131ab`
- `sqldk!?OSYieldNoAbort@Worker@@QEAAXXZ` at `0x101c13a9e`
- `sqldk!?OSYieldNoAbort@Worker@@QEAAXXZ` at `0x101c13a9e`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101c1364d`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101c1364d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c125f4`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12709`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c129ba`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12a0d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12aea`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12b3d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12c89`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12d49`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12d9c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12e7a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12ec5`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12f90`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12fe3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c13171`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c133c2`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c13558`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c137e7`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c1383a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c13c1e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c13c69`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c125f4`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12709`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c129ba`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12a0d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12aea`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12b3d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12c89`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12d49`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12d9c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12e7a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12ec5`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12f90`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c12fe3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c13171`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c133c2`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c13558`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c137e7`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c1383a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c13c1e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c13c69`
- `sqldk!SystemThread_TlsIndex` at `0x101c122e9`
- `sqldk!SystemThread_TlsIndex` at `0x101c125bd`
- `sqldk!SystemThread_TlsIndex` at `0x101c1269d`
- `sqldk!SystemThread_TlsIndex` at `0x101c126da`
- `sqldk!SystemThread_TlsIndex` at `0x101c128eb`
- `sqldk!SystemThread_TlsIndex` at `0x101c1298b`
- `sqldk!SystemThread_TlsIndex` at `0x101c129d6`
- `sqldk!SystemThread_TlsIndex` at `0x101c12abb`
- `sqldk!SystemThread_TlsIndex` at `0x101c12b06`
- `sqldk!SystemThread_TlsIndex` at `0x101c12c5a`
- `sqldk!SystemThread_TlsIndex` at `0x101c12d1a`
- `sqldk!SystemThread_TlsIndex` at `0x101c12d65`
- `sqldk!SystemThread_TlsIndex` at `0x101c12e4b`
- `sqldk!SystemThread_TlsIndex` at `0x101c12e96`
- `sqldk!SystemThread_TlsIndex` at `0x101c12f61`
- `sqldk!SystemThread_TlsIndex` at `0x101c12fb4`
- `sqldk!SystemThread_TlsIndex` at `0x101c1311a`
- `sqldk!SystemThread_TlsIndex` at `0x101c1336a`
- `sqldk!SystemThread_TlsIndex` at `0x101c13419`
- `sqldk!SystemThread_TlsIndex` at `0x101c13509`
- `sqldk!SystemThread_TlsIndex` at `0x101c13615`
- `sqldk!SystemThread_TlsIndex` at `0x101c137b8`
- `sqldk!SystemThread_TlsIndex` at `0x101c13803`
- `sqldk!SystemThread_TlsIndex` at `0x101c13a2b`
- `sqldk!SystemThread_TlsIndex` at `0x101c13bef`
- `sqldk!SystemThread_TlsIndex` at `0x101c13c3a`
- `sqldk!SystemThread_TlsIndex` at `0x101c13ec3`
- `sqldk!SystemThread_TlsOffset` at `0x101c122f2`
- `sqldk!SystemThread_TlsOffset` at `0x101c125c6`
- `sqldk!SystemThread_TlsOffset` at `0x101c126a6`
- `sqldk!SystemThread_TlsOffset` at `0x101c126e3`
- `sqldk!SystemThread_TlsOffset` at `0x101c128f4`
- `sqldk!SystemThread_TlsOffset` at `0x101c12994`
- `sqldk!SystemThread_TlsOffset` at `0x101c129df`
- `sqldk!SystemThread_TlsOffset` at `0x101c12ac4`
- `sqldk!SystemThread_TlsOffset` at `0x101c12b0f`
- `sqldk!SystemThread_TlsOffset` at `0x101c12c63`
- `sqldk!SystemThread_TlsOffset` at `0x101c12d23`
- `sqldk!SystemThread_TlsOffset` at `0x101c12d6e`
- `sqldk!SystemThread_TlsOffset` at `0x101c12e54`
- `sqldk!SystemThread_TlsOffset` at `0x101c12e9f`
- `sqldk!SystemThread_TlsOffset` at `0x101c12f6a`
- `sqldk!SystemThread_TlsOffset` at `0x101c12fbd`
- `sqldk!SystemThread_TlsOffset` at `0x101c13123`
- `sqldk!SystemThread_TlsOffset` at `0x101c13373`
- `sqldk!SystemThread_TlsOffset` at `0x101c13422`
- `sqldk!SystemThread_TlsOffset` at `0x101c13512`
- `sqldk!SystemThread_TlsOffset` at `0x101c1361e`
- `sqldk!SystemThread_TlsOffset` at `0x101c137c1`
- `sqldk!SystemThread_TlsOffset` at `0x101c1380c`
- `sqldk!SystemThread_TlsOffset` at `0x101c13a34`
- `sqldk!SystemThread_TlsOffset` at `0x101c13bf8`
- `sqldk!SystemThread_TlsOffset` at `0x101c13c43`
- `sqldk!SystemThread_TlsOffset` at `0x101c13ecc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c1290f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c13637`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c13a4d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c1290f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c13637`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c13a4d`
- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x101c12e03`
- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x101c12e03`

## string_xrefs

- `0x101c133ed`: `DPM::DoRecoveryWrites DB %d:%d aborted.`
- `0x101c1319f`: `DPM::DoRecoveryWrites DB %d:%d queued %d pages write.`
- `0x101c12ee5`: `DPM::DoRecoveryWrites DB %d:%d found same page in the second loop and exit.`
- `0x101c12dc4`: `DPM::DoRecoveryWrites DB %d:%d found no writeable page and exit. is_helper %u.`
- `0x101c12cce`: `DPM::DoRecoveryWrites DB %d:%d picked %3u pages from DPLists[%03u]. entries %I64u, searched %I64u, is_helper %d.`
- `0x101c12b61`: `DPM::DoRecoveryWrites DB %d:%d found empty lists and exit.`
- `0x101c12a34`: `DPM::DoRecoveryWrites DB %d:%d helper found empty DPList[%u] and exit.`
- `0x101c12825`: `DPM::DoRecoveryWrites DB %d:%d started. allowance %.2lf s, target %.2lf s, current %.2lf s, is_helper %d.`
- `0x101c13dd3`: `DPM::DoRecoveryWrites DB %d:%d write %6u pages (total %6u pages) and exit. allowance %.2lf s, current %.2lf s (%I64d pages), IO_throttle %d ms, elapsed %.2lf s.`
- `0x101c13ae6`: `DPM::DoRecoveryWrites DB %d:%d helper write %6u pages from DPList[%03u]. entries %4I64d, searched %4I64d.`
- `0x101c13900`: `DPM::DoRecoveryWrites DB %d:%d write %6u pages from DPList[%03u]. entries %4I64d, searched %4I64d, picked %3I64d, allowance %.2lf s, current %.2lf s (%I64d pages), IO_throttle %d ms`
- `0x101c13736`: `DirtyPageMgr::DoRecoveryWrites`
- `0x101c12687`: `DPM::DoRecoveryWrites DB %d:%d helpers bail out since current < target.allowance %I64d ms, target %I64d ms, current %I64d ms, is_helper %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
void __fastcall DirtyPageMgr::DoRecoveryWrites(DirtyPageMgr *this, unsigned __int8 a2, char a3, char a4, bool a5)
{
  int v6; // r15d
  unsigned __int64 v8; // rbx
  DirtyPageMgr *QuadPart; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  double v12; // xmm7_8
  int v13; // r12d
  int v14; // ecx
  int v15; // eax
  int v16; // r9d
  double v17; // xmm0_8
  int v18; // r8d
  __int64 v19; // rcx
  __int64 v20; // rsi
  LARGE_INTEGER v21; // rcx
  LARGE_INTEGER v22; // rcx
  unsigned __int64 v23; // rdx
  __int64 v24; // r12
  unsigned __int64 v25; // r10
  unsigned __int64 v26; // rdx
  __int64 v27; // r8
  _QWORD *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rdx
  struct CSessionTraceFlags *v31; // rcx
  __int64 v32; // rdx
  _QWORD *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rdx
  struct CSessionTraceFlags *v36; // rcx
  double v37; // xmm6_8
  __int64 v38; // rcx
  __int64 v39; // r8
  _QWORD *v40; // rax
  __int64 v41; // rdx
  double v42; // xmm0_8
  double v43; // xmm0_8
  double v44; // xmm1_8
  double v45; // xmm1_8
  __int64 v46; // rcx
  double v47; // xmm3_8
  __int64 v48; // rax
  unsigned int v49; // ecx
  struct DirtyPageLists *v50; // rsi
  unsigned __int64 v51; // r13
  __int64 v52; // r14
  unsigned int v53; // r14d
  __int64 v54; // rsi
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rdx
  struct CSessionTraceFlags *v58; // rcx
  __int64 v59; // rdx
  struct CSessionTraceFlags *v60; // rcx
  unsigned __int64 v61; // rax
  unsigned __int64 v62; // r8
  struct DirtyPageLists *v63; // rcx
  __int64 v64; // rdx
  struct CSessionTraceFlags *v65; // rcx
  __int64 v66; // rdx
  struct CSessionTraceFlags *v67; // rcx
  size_t v68; // r12
  unsigned __int64 v69; // rsi
  __int64 v70; // rax
  struct CSessionTraceFlags *v71; // rcx
  __int64 v72; // rdx
  struct CSessionTraceFlags *v73; // rcx
  __int64 v74; // rdx
  struct CSessionTraceFlags *v75; // rcx
  __int64 v76; // rdx
  struct CSessionTraceFlags *v77; // rcx
  __int64 v78; // rdx
  struct CSessionTraceFlags *v79; // rcx
  unsigned __int64 v80; // rsi
  __int64 v81; // r14
  _QWORD *v82; // rax
  __int64 v83; // rcx
  __int64 v84; // rdx
  struct CSessionTraceFlags *v85; // rcx
  __int64 v86; // rdx
  struct CSessionTraceFlags *v87; // rcx
  unsigned int v88; // r15d
  __int64 v89; // rcx
  __int64 v90; // rdx
  __int64 v91; // r8
  volatile signed __int64 *v92; // rsi
  size_t i; // r14
  unsigned int v94; // esi
  __int64 v95; // rax
  struct CSessionTraceFlags *v96; // rcx
  unsigned int v97; // ecx
  unsigned int v98; // eax
  __int64 v99; // rax
  struct CSessionTraceFlags *v100; // rcx
  __int64 v101; // rax
  struct CSessionTraceFlags *v102; // rcx
  __int64 v103; // rsi
  struct Worker *v104; // rcx
  size_t v105; // r9
  size_t v106; // rdx
  __int64 v107; // r8
  _QWORD *v108; // rax
  __int64 v109; // rcx
  unsigned __int64 v110; // rsi
  __int64 v111; // r14
  _QWORD *v112; // rax
  __int64 v113; // rcx
  __int64 v114; // rdx
  struct CSessionTraceFlags *v115; // rcx
  __int64 v116; // rdx
  struct CSessionTraceFlags *v117; // rcx
  double v118; // xmm1_8
  double v119; // xmm1_8
  __int64 v120; // rcx
  double v121; // xmm0_8
  __int64 v122; // rax
  __int64 v123; // rsi
  Worker *v124; // rcx
  unsigned __int64 v125; // rax
  unsigned __int64 v126; // r8
  __int64 v127; // rdx
  struct CSessionTraceFlags *v128; // rcx
  __int64 v129; // rdx
  struct CSessionTraceFlags *v130; // rcx
  unsigned int v131; // r15d
  DirtyPageMgr *v132; // rcx
  unsigned __int64 v133; // rcx
  double v134; // xmm0_8
  double v135; // xmm0_8
  double v136; // xmm1_8
  double v137; // xmm1_8
  __int64 v138; // rcx
  double v139; // xmm2_8
  __int64 v140; // rax
  int (*v141)(int, int, int, int, char *); // [rsp+20h] [rbp-F68h]
  __int64 v142; // [rsp+38h] [rbp-F50h]
  __int64 v143; // [rsp+40h] [rbp-F48h]
  __int64 v144; // [rsp+58h] [rbp-F30h]
  char v145; // [rsp+60h] [rbp-F28h]
  unsigned int v146; // [rsp+64h] [rbp-F24h]
  unsigned int v147; // [rsp+70h] [rbp-F18h]
  __int64 v148; // [rsp+78h] [rbp-F10h]
  unsigned int v149; // [rsp+80h] [rbp-F08h]
  unsigned int v150; // [rsp+84h] [rbp-F04h]
  __int16 v151; // [rsp+88h] [rbp-F00h]
  unsigned int v152; // [rsp+8Ch] [rbp-EFCh]
  unsigned int v153; // [rsp+90h] [rbp-EF8h]
  int v154; // [rsp+94h] [rbp-EF4h]
  unsigned int v155; // [rsp+98h] [rbp-EF0h]
  unsigned int v156; // [rsp+9Ch] [rbp-EECh]
  int v157; // [rsp+A4h] [rbp-EE4h]
  __int64 v158; // [rsp+A8h] [rbp-EE0h]
  unsigned __int64 v159; // [rsp+B0h] [rbp-ED8h]
  __int64 v160; // [rsp+B8h] [rbp-ED0h]
  unsigned int v161; // [rsp+D0h] [rbp-EB8h]
  __int64 v162; // [rsp+F0h] [rbp-E98h]
  int v163; // [rsp+F8h] [rbp-E90h] BYREF
  __int128 v164; // [rsp+100h] [rbp-E88h] BYREF
  size_t v165; // [rsp+110h] [rbp-E78h]
  int v166; // [rsp+118h] [rbp-E70h] BYREF
  __int128 v167; // [rsp+120h] [rbp-E68h] BYREF
  LARGE_INTEGER v168; // [rsp+130h] [rbp-E58h] BYREF
  DirtyPageMgr *v169; // [rsp+138h] [rbp-E50h]
  DirtyPageMgr *v170; // [rsp+140h] [rbp-E48h]
  struct CSessionTraceFlags *v171; // [rsp+148h] [rbp-E40h]
  volatile signed __int64 *v172; // [rsp+150h] [rbp-E38h]
  struct CSessionTraceFlags *v173; // [rsp+158h] [rbp-E30h]
  struct CSessionTraceFlags *v174; // [rsp+160h] [rbp-E28h]
  volatile signed __int64 *v175; // [rsp+168h] [rbp-E20h]
  __int64 v176; // [rsp+170h] [rbp-E18h]
  __int64 v177; // [rsp+178h] [rbp-E10h]
  size_t v178; // [rsp+180h] [rbp-E08h]
  DirtyPageMgr *v179; // [rsp+188h] [rbp-E00h]
  size_t v180; // [rsp+190h] [rbp-DF8h]
  volatile signed __int64 *v181; // [rsp+198h] [rbp-DF0h]
  LARGE_INTEGER v182; // [rsp+1A0h] [rbp-DE8h] BYREF
  DirtyPageMgr *v183; // [rsp+1A8h] [rbp-DE0h]
  LARGE_INTEGER v184; // [rsp+1B0h] [rbp-DD8h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+1B8h] [rbp-DD0h] BYREF
  _QWORD v186[2]; // [rsp+1C0h] [rbp-DC8h] BYREF
  char v187; // [rsp+1D0h] [rbp-DB8h]
  __int64 v188; // [rsp+1D8h] [rbp-DB0h]
  char v189; // [rsp+1E0h] [rbp-DA8h]
  size_t NumOfElements; // [rsp+1E8h] [rbp-DA0h]
  __int64 v191; // [rsp+1F0h] [rbp-D98h]
  unsigned __int64 v192; // [rsp+1F8h] [rbp-D90h]
  __int128 v193; // [rsp+200h] [rbp-D88h]
  __int64 v194; // [rsp+210h] [rbp-D78h]
  int v195; // [rsp+220h] [rbp-D68h] BYREF
  __int64 v196; // [rsp+228h] [rbp-D60h]
  __int64 v197; // [rsp+230h] [rbp-D58h]
  __int64 v198; // [rsp+238h] [rbp-D50h]
  __int64 v199; // [rsp+240h] [rbp-D48h]
  struct CSessionTraceFlags *v200; // [rsp+248h] [rbp-D40h]
  __int64 v201; // [rsp+250h] [rbp-D38h]
  __int64 v202; // [rsp+258h] [rbp-D30h]
  unsigned __int64 v203; // [rsp+260h] [rbp-D28h]
  unsigned __int64 v204; // [rsp+268h] [rbp-D20h]
  _QWORD *v205; // [rsp+270h] [rbp-D18h]
  __int64 *v206; // [rsp+278h] [rbp-D10h]
  __int64 v207; // [rsp+280h] [rbp-D08h]
  struct CSessionTraceFlags *v208; // [rsp+288h] [rbp-D00h]
  _QWORD *v209; // [rsp+290h] [rbp-CF8h]
  __int64 *v210; // [rsp+298h] [rbp-CF0h]
  __int64 v211; // [rsp+2A0h] [rbp-CE8h]
  struct CSessionTraceFlags *v212; // [rsp+2A8h] [rbp-CE0h]
  _QWORD *v213; // [rsp+2B0h] [rbp-CD8h]
  __int64 v214; // [rsp+2B8h] [rbp-CD0h]
  __int64 v215; // [rsp+2C0h] [rbp-CC8h]
  __int64 v216; // [rsp+2C8h] [rbp-CC0h]
  __int64 v217; // [rsp+2D0h] [rbp-CB8h]
  __int64 v218; // [rsp+2D8h] [rbp-CB0h]
  __int64 v219; // [rsp+2E0h] [rbp-CA8h]
  __int64 v220; // [rsp+2E8h] [rbp-CA0h]
  __int64 v221; // [rsp+300h] [rbp-C88h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+308h] [rbp-C80h]
  __int64 *v223; // [rsp+310h] [rbp-C78h]
  __int64 v224; // [rsp+318h] [rbp-C70h]
  _BYTE v225[64]; // [rsp+320h] [rbp-C68h] BYREF
  char v226[8]; // [rsp+360h] [rbp-C28h] BYREF
  int v227; // [rsp+368h] [rbp-C20h]
  int v228; // [rsp+370h] [rbp-C18h]
  _QWORD *v229; // [rsp+378h] [rbp-C10h]
  char *v230; // [rsp+380h] [rbp-C08h]
  __int64 v231; // [rsp+388h] [rbp-C00h]
  _QWORD v232[2]; // [rsp+390h] [rbp-BF8h] BYREF
  char v233; // [rsp+3A0h] [rbp-BE8h] BYREF
  __int64 v234; // [rsp+5B0h] [rbp-9D8h]
  __int64 v235; // [rsp+5B8h] [rbp-9D0h]
  int v236; // [rsp+5C0h] [rbp-9C8h] BYREF
  __int64 v237; // [rsp+5C4h] [rbp-9C4h]
  unsigned __int64 v238; // [rsp+5CCh] [rbp-9BCh]
  __int64 v239; // [rsp+5D4h] [rbp-9B4h]
  int v240; // [rsp+5DCh] [rbp-9ACh]
  __int64 v241; // [rsp+5E0h] [rbp-9A8h]
  __int64 v242; // [rsp+5E8h] [rbp-9A0h]
  char v243[8]; // [rsp+5F0h] [rbp-998h] BYREF
  int v244; // [rsp+5F8h] [rbp-990h]
  int v245; // [rsp+600h] [rbp-988h]
  _QWORD *v246; // [rsp+608h] [rbp-980h]
  char *v247; // [rsp+610h] [rbp-978h]
  __int64 v248; // [rsp+618h] [rbp-970h]
  _QWORD v249[2]; // [rsp+620h] [rbp-968h] BYREF
  char v250; // [rsp+630h] [rbp-958h] BYREF
  __int64 v251; // [rsp+840h] [rbp-748h]
  __int64 v252; // [rsp+848h] [rbp-740h]
  int v253; // [rsp+850h] [rbp-738h] BYREF
  __int64 v254; // [rsp+854h] [rbp-734h]
  unsigned __int64 v255; // [rsp+85Ch] [rbp-72Ch]
  __int64 v256; // [rsp+864h] [rbp-724h]
  __int64 v257; // [rsp+86Ch] [rbp-71Ch]
  __int64 v258; // [rsp+874h] [rbp-714h]
  char v259[8]; // [rsp+880h] [rbp-708h] BYREF
  int v260; // [rsp+888h] [rbp-700h]
  int v261; // [rsp+890h] [rbp-6F8h]
  _QWORD *v262; // [rsp+898h] [rbp-6F0h]
  char *v263; // [rsp+8A0h] [rbp-6E8h]
  __int64 v264; // [rsp+8A8h] [rbp-6E0h]
  _QWORD v265[2]; // [rsp+8B0h] [rbp-6D8h] BYREF
  char v266; // [rsp+8C0h] [rbp-6C8h] BYREF
  __int64 v267; // [rsp+AD0h] [rbp-4B8h]
  __int64 v268; // [rsp+AD8h] [rbp-4B0h]
  int v269; // [rsp+AE0h] [rbp-4A8h] BYREF
  __int64 v270; // [rsp+AE4h] [rbp-4A4h]
  unsigned __int64 v271; // [rsp+AECh] [rbp-49Ch]
  __int64 v272; // [rsp+AF4h] [rbp-494h]
  __int64 v273; // [rsp+AFCh] [rbp-48Ch]
  _DWORD v274[3]; // [rsp+B04h] [rbp-484h]
  _WORD Base[512]; // [rsp+B10h] [rbp-478h] BYREF

  v221 = -2;
  v6 = a2;
  v179 = this;
  v170 = this;
  v169 = this;
  v8 = 0;
  Base[3] = 0;
  Base[7] = 0;
  Base[11] = 0;
  Base[15] = 0;
  Base[19] = 0;
  Base[23] = 0;
  Base[27] = 0;
  Base[31] = 0;
  Base[35] = 0;
  Base[39] = 0;
  Base[43] = 0;
  Base[47] = 0;
  Base[51] = 0;
  Base[55] = 0;
  Base[59] = 0;
  Base[63] = 0;
  Base[67] = 0;
  Base[71] = 0;
  Base[75] = 0;
  Base[79] = 0;
  Base[83] = 0;
  Base[87] = 0;
  Base[91] = 0;
  Base[95] = 0;
  Base[99] = 0;
  Base[103] = 0;
  Base[107] = 0;
  Base[111] = 0;
  Base[115] = 0;
  Base[119] = 0;
  Base[123] = 0;
  Base[127] = 0;
  Base[131] = 0;
  Base[135] = 0;
  Base[139] = 0;
  Base[143] = 0;
  Base[147] = 0;
  Base[151] = 0;
  Base[155] = 0;
  Base[159] = 0;
  Base[163] = 0;
  Base[167] = 0;
  Base[171] = 0;
  Base[175] = 0;
  Base[179] = 0;
  Base[183] = 0;
  Base[187] = 0;
  Base[191] = 0;
  Base[195] = 0;
  Base[199] = 0;
  Base[203] = 0;
  Base[207] = 0;
  Base[211] = 0;
  Base[215] = 0;
  Base[219] = 0;
  Base[223] = 0;
  Base[227] = 0;
  Base[231] = 0;
  Base[235] = 0;
  Base[239] = 0;
  Base[243] = 0;
  Base[247] = 0;
  Base[251] = 0;
  Base[255] = 0;
  Base[259] = 0;
  Base[263] = 0;
  Base[267] = 0;
  Base[271] = 0;
  Base[275] = 0;
  Base[279] = 0;
  Base[283] = 0;
  Base[287] = 0;
  Base[291] = 0;
  Base[295] = 0;
  Base[299] = 0;
  Base[303] = 0;
  Base[307] = 0;
  Base[311] = 0;
  Base[315] = 0;
  Base[319] = 0;
  Base[323] = 0;
  Base[327] = 0;
  Base[331] = 0;
  Base[335] = 0;
  Base[339] = 0;
  Base[343] = 0;
  Base[347] = 0;
  Base[351] = 0;
  Base[355] = 0;
  Base[359] = 0;
  Base[363] = 0;
  Base[367] = 0;
  Base[371] = 0;
  Base[375] = 0;
  Base[379] = 0;
  Base[383] = 0;
  Base[387] = 0;
  Base[391] = 0;
  Base[395] = 0;
  Base[399] = 0;
  Base[403] = 0;
  Base[407] = 0;
  Base[411] = 0;
  Base[415] = 0;
  Base[419] = 0;
  Base[423] = 0;
  Base[427] = 0;
  Base[431] = 0;
  Base[435] = 0;
  Base[439] = 0;
  Base[443] = 0;
  Base[447] = 0;
  Base[451] = 0;
  Base[455] = 0;
  Base[459] = 0;
  Base[463] = 0;
  Base[467] = 0;
  Base[471] = 0;
  Base[475] = 0;
  Base[479] = 0;
  Base[483] = 0;
  Base[487] = 0;
  Base[491] = 0;
  Base[495] = 0;
  Base[499] = 0;
  Base[503] = 0;
  Base[507] = 0;
  Base[511] = 0;
  v157 = 0;
  v151 = 0;
  v146 = 0;
  v150 = 0;
  v163 = 0;
  v164 = 0;
  v166 = 0;
  v167 = 0;
  v149 = 0;
  v153 = 0;
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&v184);
    QuadPart = (DirtyPageMgr *)v184.QuadPart;
  }
  else
  {
    QuadPart = MEMORY[0x7FFE0008];
  }
  v183 = QuadPart;
  if ( dword_103172528 )
  {
    if ( !byte_10316E99D || !word_103185B6E )
    {
      v10 = *(_QWORD *)(*((_QWORD *)this + 34) + 1712LL);
      if ( v10 )
      {
        v11 = *(_QWORD *)(v10 + 2296);
        if ( v11 )
        {
          v12 = (double)*(int *)(v11 + 52);
          v13 = *(_DWORD *)(v11 + 56);
          goto LABEL_21;
        }
      }
    }
    v14 = dword_103186EF4;
    v15 = dword_103186EF4;
    v16 = dword_103186EEC;
    if ( dword_103186EF4 < 0 )
      v15 = dword_103186EEC;
    v17 = (double)v15;
    v18 = dword_1031E0918;
  }
  else
  {
    v18 = dword_1031E0918;
    v17 = (double)dword_1031E0918;
    v14 = dword_103186EF4;
    v16 = dword_103186EEC;
  }
  if ( v17 <= 0.0 )
  {
    v12 = *(double *)&qword_1031E0928;
  }
  else
  {
    if ( !dword_103172528 )
    {
      v12 = (double)v18;
LABEL_20:
      v13 = dword_1031E0920;
      goto LABEL_21;
    }
    if ( v14 < 0 )
      v14 = v16;
    v12 = (double)v14;
  }
  if ( !dword_103172528 )
    goto LABEL_20;
  v13 = dword_103186EF8;
  if ( dword_103186EF8 < 0 )
    v13 = dword_103186EF0;
LABEL_21:
  v154 = v13;
  v19 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset
                              + 8LL)
                  + 96LL);
  v20 = *(_QWORD *)(v19 + 1272);
  *(_QWORD *)(v19 + 1272) = *(_QWORD *)(*((_QWORD *)this + 34) + 1712LL);
  v162 = v20;
  if ( (_BYTE)v6 && !a3 && (v12 != 0.0 || v13) )
    goto LABEL_66;
  if ( a5 )
  {
    _InterlockedIncrement64((volatile signed __int64 *)this + 11);
  }
  else if ( (_BYTE)v6 )
  {
    _InterlockedIncrement64((volatile signed __int64 *)this + 10);
  }
  else
  {
    ++*((_QWORD *)this + 9);
  }
  if ( v12 > 0.0 )
  {
    v166 = 2;
    *(_QWORD *)&v167 = (unsigned int)(int)(1048576000.0 / (v12 * 128.0));
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&PerformanceCount);
      v21 = PerformanceCount;
    }
    else
    {
      v21.QuadPart = (LONGLONG)MEMORY[0x7FFE0008];
    }
    if ( v21.QuadPart == -1 )
    {
      *((_QWORD *)&v167 + 1) = 0xFFFFFFFF00000LL;
    }
    else if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      *((_QWORD *)&v167 + 1) = (unsigned __int64)(unsigned int)((unsigned __int64)(1000 * v21.QuadPart)
                                                              / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart) << 20;
    }
    else
    {
      *((_QWORD *)&v167 + 1) = (unsigned __int64)(unsigned int)(v21.QuadPart / 0x2710uLL) << 20;
    }
  }
  if ( v13 )
  {
    v163 = 1;
    *(_QWORD *)&v164 = (unsigned int)(int)(1048576000.0 / (double)v13);
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v168);
      v22 = v168;
    }
    else
    {
      v22.QuadPart = (LONGLONG)MEMORY[0x7FFE0008];
    }
    if ( v22.QuadPart == -1 )
    {
      LODWORD(v23) = -1;
    }
    else if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      v23 = (unsigned __int64)(1000 * v22.QuadPart) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
    }
    else
    {
      v23 = v22.QuadPart / 0x2710uLL;
    }
    *((_QWORD *)&v164 + 1) = (unsigned __int64)(unsigned int)v23 << 20;
  }
  v24 = -1;
  v148 = -1;
  v25 = *((_QWORD *)this + 2) - (*((_QWORD *)this + 2) >> 8);
  v159 = v25;
  if ( (_BYTE)v6 )
  {
    if ( !a3 )
    {
      v26 = 0;
      v27 = 0;
      v28 = (_QWORD *)(*((_QWORD *)this + 35) + 120LL);
      v29 = *((int *)this + 63) + 1LL;
      do
      {
        v26 += *v28;
        v27 += v28[1];
        v28 += 24;
        --v29;
      }
      while ( v29 );
      *(_QWORD *)(*((_QWORD *)this + 34) + 27312LL) = v27;
      if ( v26 < v25 )
      {
        if ( (qword_10317AD29 & 0x40000000000LL) == 0 )
        {
          v30 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( !*(_QWORD *)v30 )
            goto LABEL_66;
          v31 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v30 + 56LL);
          if ( !v31 || !CSessionTraceFlags::CheckSessionTraceInternal(v31, 0xD72u) )
            goto LABEL_66;
          v25 = v159;
        }
        _mm_lfence();
        v32 = 0;
        v33 = (_QWORD *)(*((_QWORD *)this + 35) + 120LL);
        v34 = *((int *)this + 63) + 1LL;
        do
        {
          v8 += *v33;
          v32 += v33[1];
          v33 += 24;
          --v34;
        }
        while ( v34 );
        *(_QWORD *)(*((_QWORD *)this + 34) + 27312LL) = v32;
        traceprint(
          L"DPM::DoRecoveryWrites DB %d:%d helpers bail out since current < target.allowance %I64d ms, target %I64d ms, cu"
           "rrent %I64d ms, is_helper %d.",
          *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1720LL),
          *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1632LL),
          *((_QWORD *)this + 2) >> 10,
          v25 >> 10,
          v8 >> 10,
          v6);
LABEL_66:
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset
                                          + 8LL)
                              + 96LL)
                  + 1272LL) = v20;
        return;
      }
    }
  }
  if ( (qword_10317AD29 & 0x40000000000LL) == 0 )
  {
    v35 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    if ( !*(_QWORD *)v35
      || (v36 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v35 + 56LL)) == 0
      || !CSessionTraceFlags::CheckSessionTraceInternal(v36, 0xD72u) )
    {
      v37 = DOUBLE_1000000_0;
      goto LABEL_85;
    }
    v25 = v159;
  }
  v38 = 0;
  v39 = 0;
  v40 = (_QWORD *)(*((_QWORD *)this + 35) + 120LL);
  v41 = *((int *)this + 63) + 1LL;
  do
  {
    v38 += *v40;
    v39 += v40[1];
    v40 += 24;
    --v41;
  }
  while ( v41 );
  *(_QWORD *)(*((_QWORD *)this + 34) + 27312LL) = v39;
  if ( v38 < 0 )
    v42 = (double)(int)(v38 & 1 | ((unsigned __int64)v38 >> 1)) + (double)(int)(v38 & 1 | ((unsigned __int64)v38 >> 1));
  else
    v42 = (double)(int)v38;
  v37 = DOUBLE_1000000_0;
  v43 = v42 / 1000000.0;
  if ( (v25 & 0x8000000000000000uLL) != 0LL )
    v44 = (double)(int)(v25 & 1 | (v25 >> 1)) + (double)(int)(v25 & 1 | (v25 >> 1));
  else
    v44 = (double)(int)v25;
  v45 = v44 / 1000000.0;
  v46 = *((_QWORD *)this + 2);
  if ( v46 < 0 )
  {
    v48 = *((_QWORD *)this + 2) & 1LL | ((unsigned __int64)v46 >> 1);
    v47 = (double)(int)v48 + (double)(int)v48;
  }
  else
  {
    v47 = (double)(int)v46;
  }
  traceprint(
    L"DPM::DoRecoveryWrites DB %d:%d started. allowance %.2lf s, target %.2lf s, current %.2lf s, is_helper %d.",
    *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1720LL),
    *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1632LL),
    v47 / 1000000.0,
    v45,
    v43,
    v6);
LABEL_85:
  v145 = 0;
  v49 = dword_103205C1C;
  v155 = dword_103205C1C;
  if ( byte_10316EBE3 && dword_103205C1C == 64 && (unsigned int)dword_103186600 > 0x2000 )
  {
    if ( (unsigned int)dword_103186600 >> 13 < 0x40 )
      v49 = (unsigned int)dword_103186600 >> 13;
    v155 = v49;
    dword_103205C1C = v49;
  }
  v161 = v49;
  while ( 2 )
  {
    while ( 2 )
    {
      v50 = 0;
      v156 = 0;
      v51 = 0;
      v52 = 0;
      v158 = 0;
      if ( *((_BYTE *)this + 256) || !*((_BYTE *)this + 258) )
        goto LABEL_158;
      if ( (_BYTE)v6 )
      {
        v53 = *((_DWORD *)v169 + 63);
        v54 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v55 = *(_QWORD *)(v54 + 256);
        if ( !v55 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v55 = *(_QWORD *)(v54 + 256);
        }
        v56 = v53 & (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v55 + 600) + 160LL) + 3688LL) >> dword_10317F694);
        v52 = (unsigned int)v56;
        v160 = (unsigned int)v56;
        v50 = (struct DirtyPageLists *)(*((_QWORD *)this + 35) + 192 * v56);
        v51 = *((_QWORD *)v50 + 16);
        if ( !v51 )
        {
          if ( (qword_10317AD33 & 2) != 0
            || (v57 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset,
                *(_QWORD *)v57)
            && (v58 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v57 + 56LL)) != 0
            && CSessionTraceFlags::CheckSessionTraceInternal(v58, 0xD99u)
            || (qword_10317AD29 & 0x40000000000LL) != 0
            || (v59 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset,
                *(_QWORD *)v59)
            && (v60 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v59 + 56LL)) != 0
            && CSessionTraceFlags::CheckSessionTraceInternal(v60, 0xD72u) )
          {
            traceprint(
              L"DPM::DoRecoveryWrites DB %d:%d helper found empty DPList[%u] and exit.",
              *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1720LL),
              *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1632LL),
              v52);
          }
          goto LABEL_158;
        }
      }
      else
      {
        v61 = 0;
        v62 = *((int *)v169 + 63);
        v63 = (struct DirtyPageLists *)*((_QWORD *)this + 35);
        do
        {
          if ( (!(_DWORD)v62 || v24 != v61) && *((_QWORD *)v63 + 16) > v51 )
          {
            v50 = v63;
            v51 = *((_QWORD *)v63 + 16);
            v52 = v61;
          }
          ++v61;
          v63 = (struct DirtyPageLists *)((char *)v63 + 192);
        }
        while ( v61 <= v62 );
        v160 = v52;
        if ( !v50 )
        {
          if ( (qword_10317AD33 & 2) != 0
            || (v64 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset,
                *(_QWORD *)v64)
            && (v65 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v64 + 56LL)) != 0
            && CSessionTraceFlags::CheckSessionTraceInternal(v65, 0xD99u)
            || (qword_10317AD29 & 0x40000000000LL) != 0
            || (v66 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset,
                *(_QWORD *)v66)
            && (v67 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v66 + 56LL)) != 0
            && CSessionTraceFlags::CheckSessionTraceInternal(v67, 0xD72u) )
          {
            traceprint(
              L"DPM::DoRecoveryWrites DB %d:%d found empty lists and exit.",
              *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1720LL),
              *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1632LL));
          }
          goto LABEL_158;
        }
      }
      v186[0] = Base;
      v186[1] = 128;
      v187 = 1;
      v188 = 0;
      v189 = 0;
      NumOfElements = 0;
      v191 = 0;
      v192 = 0;
      v193 = 0;
      v194 = 0;
      DirtyPageMgr::CollectPageIdsForWrite(this, v50, 0, (struct DirtyPageMgr::CollectPageIdsParam *)v186);
      v68 = NumOfElements;
      if ( NumOfElements < 0x80 )
      {
        DirtyPageMgr::CollectPageIdsForWrite(this, v50, 1, (struct DirtyPageMgr::CollectPageIdsParam *)v186);
        v68 = NumOfElements;
      }
      v178 = v68;
      v158 = v191;
      v177 = v191;
      v69 = v192;
      if ( v191 )
      {
        if ( (qword_10317AD29 & 0x40000000000LL) != 0
          || (v70 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset)) != 0
          && (v71 = **(struct CSessionTraceFlags ***)(v70 + 56)) != 0
          && CSessionTraceFlags::CheckSessionTraceInternal(v71, 0xD72u) )
        {
          _mm_lfence();
          LODWORD(v142) = (unsigned __int8)v6;
          traceprint(
            L"DPM::DoRecoveryWrites DB %d:%d picked %3u pages from DPLists[%03u]. entries %I64u, searched %I64u, is_helper %d.",
            *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1720LL),
            *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1632LL),
            v68,
            v52,
            v51,
            v158,
            v142);
        }
      }
      if ( !v68 )
      {
        v24 = v148;
        if ( !(_BYTE)v6 && v148 != -1 )
        {
          v24 = -1;
          v148 = -1;
          continue;
        }
        if ( (qword_10317AD33 & 2) != 0
          || (v72 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset,
              *(_QWORD *)v72)
          && (v73 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v72 + 56LL)) != 0
          && CSessionTraceFlags::CheckSessionTraceInternal(v73, 0xD99u)
          || (qword_10317AD29 & 0x40000000000LL) != 0
          || (v74 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset,
              *(_QWORD *)v74)
          && (v75 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v74 + 56LL)) != 0
          && CSessionTraceFlags::CheckSessionTraceInternal(v75, 0xD72u) )
        {
          traceprint(
            L"DPM::DoRecoveryWrites DB %d:%d found no writeable page and exit. is_helper %u.",
            *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1720LL),
            *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1632LL),
            (unsigned __int8)v6);
        }
        goto LABEL_158;
      }
      break;
    }
    v148 = v52;
    v176 = v52;
    if ( v68 > 1 )
    {
      _mm_lfence();
      qsort(Base, v68, 8u, QSortPageId);
    }
    if ( v157 == v274[2 * v68 + 1] && v151 == LOWORD(v274[2 * v68 + 2]) )
    {
      if ( (qword_10317AD33 & 2) != 0
        || (v76 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset,
            *(_QWORD *)v76)
        && (v77 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v76 + 56LL)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v77, 0xD99u)
        || (qword_10317AD29 & 0x40000000000LL) != 0
        || (v78 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset,
            *(_QWORD *)v78)
        && (v79 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v78 + 56LL)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v79, 0xD72u) )
      {
        traceprint(
          L"DPM::DoRecoveryWrites DB %d:%d found same page in the second loop and exit.",
          *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1720LL),
          *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1632LL));
      }
      break;
    }
    v180 = v69 / v68;
    if ( a5 )
    {
      v89 = 136;
      v90 = 144;
      v91 = 200;
    }
    else
    {
      v89 = 120;
      v90 = 128;
      v91 = 192;
    }
    v175 = (volatile signed __int64 *)((char *)v170 + v91);
    v172 = (volatile signed __int64 *)((char *)v170 + v90);
    v92 = (volatile signed __int64 *)((char *)v170 + v89);
    v181 = (volatile signed __int64 *)((char *)v170 + v89);
    for ( i = 0; ; ++i )
    {
      v165 = i;
      if ( i >= v68 )
        goto LABEL_227;
      v152 = 0;
      ExcHandler::ExcHandler(
        (ExcHandler *)v225,
        0,
        0,
        0,
        (int (*)(int, int, int, int, char *))HandleAndNoteToErrorlog,
        0);
      _InterlockedIncrement64((volatile signed __int64 *)this + 12);
      if ( (_BYTE)v6 )
        _InterlockedIncrement64(v92);
      v94 = BPool::WriteOnlyIfDirty(qword_10317B628, *((_QWORD *)this + 34), &Base[4 * i], 4, 0);
      v147 = v94;
      if ( !v94 )
      {
        _InterlockedIncrement64((volatile signed __int64 *)this + 13);
        goto LABEL_215;
      }
      if ( (qword_10317AD29 & 0x40000000000LL) != 0 )
        goto LABEL_183;
      ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
      v223 = (__int64 *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset);
      v95 = *v223;
      v224 = v95;
      if ( !v95 || (v96 = **(struct CSessionTraceFlags ***)(v95 + 56), (v200 = v96) == 0) )
      {
        v171 = 0;
        goto LABEL_184;
      }
      v171 = v96;
      if ( CSessionTraceFlags::CheckSessionTraceInternal(v96, 0xD72u) )
LABEL_183:
        traceprint(
          L"DPM::DoRecoveryWrites DB %d:%d queued %d pages write.",
          *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1720LL),
          *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1632LL),
          v94);
LABEL_184:
      if ( CommonGlobalState::m_PerfCountersEnabled )
        PerfmonManager::IncrementCounterValue((PerfmonManager *)&ResourceStr, 1u, 0x78u, v94, 0);
      v201 = v94;
      _InterlockedExchangeAdd64((volatile signed __int64 *)this + 14, v94);
      if ( (_BYTE)v6 )
      {
        v202 = v94;
        _InterlockedExchangeAdd64(v172, v94);
      }
      if ( v146 )
      {
        if ( v12 <= 0.0 )
        {
          v97 = 0;
        }
        else
        {
          v203 = v94 * (_QWORD)v167;
          _InterlockedExchangeAdd64((volatile signed __int64 *)&v167 + 1, v203);
          v97 = Throttle::DelayTime((Throttle *)&v166);
          v152 = v97;
        }
        if ( v154 )
        {
          v204 = v164 * ((v155 + v94 - 1 - (v155 + v94 - 1) % v161) / v155);
          _InterlockedExchangeAdd64((volatile signed __int64 *)&v164 + 1, v204);
          v98 = Throttle::DelayTime((Throttle *)&v163);
          v97 = v152;
          if ( v152 <= v98 )
          {
            v97 = Throttle::DelayTime((Throttle *)&v163);
            v152 = v97;
          }
        }
        if ( v97 )
        {
          _mm_lfence();
          v195 = 4194400;
          v196 = 0;
          v198 = 0;
          v197 = 0;
          v199 = 0;
          if ( (unsigned int)SOS_Task::Sleep(v152, &v195) == 2 )
          {
            if ( (qword_10317AD33 & 2) == 0 )
            {
              v205 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v206 = (__int64 *)(v205[SystemThread_TlsIndex] + SystemThread_TlsOffset);
              v99 = *v206;
              v207 = v99;
              if ( v99 && (v100 = **(struct CSessionTraceFlags ***)(v99 + 56), (v208 = v100) != 0) )
              {
                v173 = v100;
                if ( CSessionTraceFlags::CheckSessionTraceInternal(v100, 0xD99u) )
                  goto LABEL_202;
              }
              else
              {
                v173 = 0;
              }
              if ( (qword_10317AD29 & 0x40000000000LL) == 0 )
              {
                v209 = NtCurrentTeb()->ThreadLocalStoragePointer;
                v210 = (__int64 *)(v209[SystemThread_TlsIndex] + SystemThread_TlsOffset);
                v101 = *v210;
                v211 = v101;
                if ( !v101 || (v102 = **(struct CSessionTraceFlags ***)(v101 + 56), (v212 = v102) == 0) )
                {
                  v174 = 0;
                  goto LABEL_203;
                }
                v174 = v102;
                if ( !CSessionTraceFlags::CheckSessionTraceInternal(v102, 0xD72u) )
                {
LABEL_203:
                  ExcHandler::~ExcHandler((ExcHandler *)v225);
                  v213 = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v214 = v213[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                  v215 = *(_QWORD *)(v214 + 8);
                  v216 = *(_QWORD *)(v215 + 96);
                  v217 = v162;
                  v218 = v216 + 1272;
                  *(_QWORD *)(v216 + 1272) = v162;
                  return;
                }
              }
            }
LABEL_202:
            traceprint(
              L"DPM::DoRecoveryWrites DB %d:%d aborted.",
              *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1720LL),
              *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1632LL));
            goto LABEL_203;
          }
          v149 += v152;
          v153 += v152;
          v219 = v152;
          _InterlockedExchangeAdd64((volatile signed __int64 *)this + 23, v152);
          if ( (_BYTE)v6 )
          {
            v220 = v152;
            _InterlockedExchangeAdd64(v175, v152);
          }
        }
      }
      v156 += v94;
      v150 += v94;
      v146 += v94;
LABEL_215:
      ExcHandler::~ExcHandler((ExcHandler *)v225);
      v103 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v104 = *(struct Worker **)(v103 + 256);
      if ( !v104 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v104 = *(struct Worker **)(v103 + 256);
      }
      if ( *((_DWORD *)v104 + 139) )
        ExceptionPostCatchActions(v104);
      v105 = v180 * v147;
      if ( *((_BYTE *)this + 256) )
        break;
      v157 = *(_DWORD *)&Base[4 * i];
      v151 = Base[4 * i + 2];
      v106 = 0;
      v107 = 0;
      v108 = (_QWORD *)(*((_QWORD *)this + 35) + 120LL);
      v109 = *((int *)this + 63) + 1LL;
      do
      {
        v106 += *v108;
        v107 += v108[1];
        v108 += 24;
        --v109;
      }
      while ( v109 );
      *(_QWORD *)(*((_QWORD *)this + 34) + 27312LL) = v107;
      if ( v106 < v105 + v159 || (_BYTE)v6 && !a4 )
        break;
      v92 = v181;
    }
    v145 = 1;
LABEL_227:
    if ( a5 && (qword_10317AD66 & 0x400000000000000LL) != 0 )
    {
      LODWORD(v141) = v149;
      log_unlocalized_systemmetadata(
        L"[VersionCleaner][DbId:%d][%ls] Total written pages: %d, IO_throttle %d ms",
        *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1720LL),
        L"DirtyPageMgr::DoRecoveryWrites",
        v146,
        v141);
    }
    if ( !(_BYTE)v6 && v156 )
    {
      v110 = 0;
      v111 = 0;
      v112 = (_QWORD *)(*((_QWORD *)this + 35) + 120LL);
      v113 = *((int *)this + 63) + 1LL;
      do
      {
        v110 += *v112;
        v111 += v112[1];
        v112 += 24;
        --v113;
      }
      while ( v113 );
      *(_QWORD *)(*((_QWORD *)this + 34) + 27312LL) = v111;
      if ( (qword_10317AD33 & 2) != 0
        || (v114 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset,
            *(_QWORD *)v114)
        && (v115 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v114 + 56LL)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v115, 0xD99u)
        || (qword_10317AD29 & 0x40000000000LL) != 0
        || (v116 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset,
            *(_QWORD *)v116)
        && (v117 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v116 + 56LL)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v117, 0xD72u) )
      {
        _mm_lfence();
        if ( (v110 & 0x8000000000000000uLL) != 0LL )
          v118 = (double)(int)(v110 & 1 | (v110 >> 1)) + (double)(int)(v110 & 1 | (v110 >> 1));
        else
          v118 = (double)(int)v110;
        v119 = v118 / v37;
        v120 = *((_QWORD *)this + 2);
        if ( v120 < 0 )
        {
          v122 = *((_QWORD *)this + 2) & 1LL | ((unsigned __int64)v120 >> 1);
          v121 = (double)(int)v122 + (double)(int)v122;
        }
        else
        {
          v121 = (double)(int)v120;
        }
        LODWORD(v144) = v149;
        traceprint(
          L"DPM::DoRecoveryWrites DB %d:%d write %6u pages from DPList[%03u]. entries %4I64d, searched %4I64d, picked %3I6"
           "4d, allowance %.2lf s, current %.2lf s (%I64d pages), IO_throttle %d ms",
          *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1720LL),
          *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1632LL),
          v156,
          v160,
          v51,
          v158,
          v68,
          v121 / v37,
          v119,
          v111,
          v144);
      }
      if ( (dword_10317F6CC & 0x10000) != 0 && v150 >= 0x1000 )
      {
        v244 = 0x10000;
        v245 = 0;
        v246 = v249;
        v247 = &v250;
        v251 = 0;
        v248 = 0;
        v252 = 0;
        v249[0] = &v253;
        v249[1] = 44;
        v253 = *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1720LL);
        v254 = v111;
        v255 = v110 >> 10;
        v256 = *((_QWORD *)this + 2) >> 10;
        v257 = v150;
        v258 = v153;
        XeSqlPkg::recovery_background_write::Publish((XeSqlPkg::recovery_background_write *)v243);
        v150 = 0;
        v153 = 0;
      }
    }
    if ( !v145 && (!(_BYTE)v6 || a4) )
    {
      v123 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v124 = *(Worker **)(v123 + 256);
      if ( !v124 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v124 = *(Worker **)(v123 + 256);
      }
      v125 = __rdtsc();
      v126 = *((_QWORD *)v124 + 104);
      if ( v125 > v126
        || (v24 = v148, v126 != 0x7FFFFFFFFFFFFFFFLL) && v126 - v125 > *(_QWORD *)(*((_QWORD *)v124 + 76) + 3568LL) )
      {
        Worker::OSYieldNoAbort(v124);
        v24 = v148;
      }
      continue;
    }
    break;
  }
  v24 = v148;
LABEL_158:
  if ( !v146 )
    goto LABEL_295;
  v80 = 0;
  v81 = 0;
  v82 = (_QWORD *)(*((_QWORD *)this + 35) + 120LL);
  v83 = *((int *)this + 63) + 1LL;
  do
  {
    v80 += *v82;
    v81 += v82[1];
    v82 += 24;
    --v83;
  }
  while ( v83 );
  *(_QWORD *)(*((_QWORD *)this + 34) + 27312LL) = v81;
  if ( (_BYTE)v6 )
  {
    if ( (qword_10317AD33 & 2) != 0
      || (v84 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
          *(_QWORD *)v84)
      && (v85 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v84 + 56LL)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v85, 0xD99u)
      || (qword_10317AD29 & 0x40000000000LL) != 0
      || (v86 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
          *(_QWORD *)v86)
      && (v87 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v86 + 56LL)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v87, 0xD72u) )
    {
      _mm_lfence();
      v88 = v146;
      traceprint(
        L"DPM::DoRecoveryWrites DB %d:%d helper write %6u pages from DPList[%03u]. entries %4I64d, searched %4I64d.",
        *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1720LL),
        *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1632LL),
        v146,
        v24,
        v51,
        v158);
    }
    else
    {
      v88 = v146;
    }
    if ( (dword_10317F6CC & 0x20000) != 0 )
    {
      v227 = 0x10000;
      v228 = 0;
      v229 = v232;
      v230 = &v233;
      v234 = 0;
      v231 = 0;
      v235 = 0;
      v232[0] = &v236;
      v232[1] = 48;
      v236 = *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1720LL);
      v237 = v81;
      v238 = v80 >> 10;
      v239 = *((_QWORD *)this + 2) >> 10;
      v240 = v24;
      v241 = v88;
      v242 = v149;
      XeSqlPkg::recovery_helper_write::Publish((XeSqlPkg::recovery_helper_write *)v226);
    }
    goto LABEL_295;
  }
  if ( (qword_10317AD33 & 2) != 0
    || (v127 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
        *(_QWORD *)v127)
    && (v128 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v127 + 56LL)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v128, 0xD99u)
    || (qword_10317AD29 & 0x40000000000LL) != 0
    || (v129 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
        *(_QWORD *)v129)
    && (v130 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v129 + 56LL)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v130, 0xD72u) )
  {
    _mm_lfence();
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v182);
      v132 = (DirtyPageMgr *)v182.QuadPart;
    }
    else
    {
      v132 = MEMORY[0x7FFE0008];
    }
    if ( v132 < v183 )
    {
      v133 = 0;
    }
    else
    {
      v133 = v132 - v183;
      if ( v133 == -1 )
        goto LABEL_283;
    }
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
      v133 = 1000 * v133 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
    else
      v133 /= 0x2710u;
LABEL_283:
    if ( (v133 & 0x8000000000000000uLL) != 0LL )
      v134 = (double)(int)(v133 & 1 | (v133 >> 1)) + (double)(int)(v133 & 1 | (v133 >> 1));
    else
      v134 = (double)(int)v133;
    v135 = v134 / 1000.0;
    if ( (v80 & 0x8000000000000000uLL) != 0LL )
      v136 = (double)(int)(v80 & 1 | (v80 >> 1)) + (double)(int)(v80 & 1 | (v80 >> 1));
    else
      v136 = (double)(int)v80;
    v137 = v136 / v37;
    v138 = *((_QWORD *)this + 2);
    if ( v138 < 0 )
    {
      v140 = *((_QWORD *)this + 2) & 1LL | ((unsigned __int64)v138 >> 1);
      v139 = (double)(int)v140 + (double)(int)v140;
    }
    else
    {
      v139 = (double)(int)v138;
    }
    LODWORD(v143) = v149;
    LODWORD(v141) = v146;
    v131 = v150;
    traceprint(
      L"DPM::DoRecoveryWrites DB %d:%d write %6u pages (total %6u pages) and exit. allowance %.2lf s, current %.2lf s (%I6"
       "4d pages), IO_throttle %d ms, elapsed %.2lf s.",
      *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1720LL),
      *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1632LL),
      v150,
      v141,
      v139 / v37,
      v137,
      v81,
      v143,
      v135);
    goto LABEL_293;
  }
  v131 = v150;
LABEL_293:
  if ( (dword_10317F6CC & 0x10000) != 0 )
  {
    v260 = 0x10000;
    v261 = 0;
    v262 = v265;
    v263 = &v266;
    v267 = 0;
    v264 = 0;
    v268 = 0;
    v265[0] = &v269;
    v265[1] = 44;
    v269 = *(unsigned __int16 *)(*((_QWORD *)this + 34) + 1720LL);
    v270 = v81;
    v271 = v80 >> 10;
    v272 = *((_QWORD *)this + 2) >> 10;
    v273 = v131;
    *(_QWORD *)v274 = v153;
    XeSqlPkg::recovery_background_write::Publish((XeSqlPkg::recovery_background_write *)v259);
  }
LABEL_295:
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                    + SystemThread_TlsOffset
                                    + 8LL)
                        + 96LL)
            + 1272LL) = v162;
}

```

## disassembly

```asm
0x101c11d00  mov     r11, rsp
0x101c11d03  mov     [r11+20h], r9b
0x101c11d07  push    rbx
0x101c11d08  push    rsi
0x101c11d09  push    rdi
0x101c11d0a  push    r12
0x101c11d0c  push    r13
0x101c11d0e  push    r14
0x101c11d10  push    r15
0x101c11d12  sub     rsp, 0F50h
0x101c11d19  mov     qword ptr [r11-0C88h], 0FFFFFFFFFFFFFFFEh
0x101c11d24  movaps  xmmword ptr [r11-48h], xmm6
0x101c11d29  movaps  xmmword ptr [r11-58h], xmm7
0x101c11d2e  movaps  xmmword ptr [r11-68h], xmm8
0x101c11d33  mov     rax, cs:__security_cookie
0x101c11d3a  xor     rax, rsp
0x101c11d3d  mov     [rsp+0F88h+var_78], rax
0x101c11d45  movzx   r14d, r8b
0x101c11d49  movzx   r15d, dl
0x101c11d4d  mov     rdi, rcx
0x101c11d50  mov     [rsp+0F88h+var_E00], rcx
0x101c11d58  mov     [rsp+0F88h+var_E48], rcx
0x101c11d60  mov     [rsp+0F88h+var_E50], rcx
0x101c11d68  mov     [rsp+0F88h+var_F20], r15b
0x101c11d6d  xor     ebx, ebx
0x101c11d6f  mov     [rsp+0F88h+var_472], bx
0x101c11d77  mov     [rsp+0F88h+var_46A], bx
0x101c11d7f  mov     [rsp+0F88h+var_462], bx
0x101c11d87  mov     [rsp+0F88h+var_45A], bx
0x101c11d8f  mov     [rsp+0F88h+var_452], bx
0x101c11d97  mov     [rsp+0F88h+var_44A], bx
0x101c11d9f  mov     [rsp+0F88h+var_442], bx
0x101c11da7  mov     [rsp+0F88h+var_43A], bx
0x101c11daf  mov     [rsp+0F88h+var_432], bx
0x101c11db7  mov     [rsp+0F88h+var_42A], bx
0x101c11dbf  mov     [rsp+0F88h+var_422], bx
0x101c11dc7  mov     [rsp+0F88h+var_41A], bx
0x101c11dcf  mov     [rsp+0F88h+var_412], bx
0x101c11dd7  mov     [rsp+0F88h+var_40A], bx
0x101c11ddf  mov     [rsp+0F88h+var_402], bx
0x101c11de7  mov     [rsp+0F88h+var_3FA], bx
0x101c11def  mov     [rsp+0F88h+var_3F2], bx
0x101c11df7  mov     [rsp+0F88h+var_3EA], bx
0x101c11dff  mov     [rsp+0F88h+var_3E2], bx
0x101c11e07  mov     [rsp+0F88h+var_3DA], bx
0x101c11e0f  mov     [rsp+0F88h+var_3D2], bx
0x101c11e17  mov     [rsp+0F88h+var_3CA], bx
0x101c11e1f  mov     [rsp+0F88h+var_3C2], bx
0x101c11e27  mov     [rsp+0F88h+var_3BA], bx
0x101c11e2f  mov     [rsp+0F88h+var_3B2], bx
0x101c11e37  mov     [rsp+0F88h+var_3AA], bx
0x101c11e3f  mov     [rsp+0F88h+var_3A2], bx
0x101c11e47  mov     [rsp+0F88h+var_39A], bx
0x101c11e4f  mov     [rsp+0F88h+var_392], bx
0x101c11e57  mov     [rsp+0F88h+var_38A], bx
0x101c11e5f  mov     [rsp+0F88h+var_382], bx
0x101c11e67  mov     [rsp+0F88h+var_37A], bx
0x101c11e6f  mov     [rsp+0F88h+var_372], bx
0x101c11e77  mov     [rsp+0F88h+var_36A], bx
0x101c11e7f  mov     [rsp+0F88h+var_362], bx
0x101c11e87  mov     [rsp+0F88h+var_35A], bx
0x101c11e8f  mov     [rsp+0F88h+var_352], bx
0x101c11e97  mov     [rsp+0F88h+var_34A], bx
0x101c11e9f  mov     [rsp+0F88h+var_342], bx
0x101c11ea7  mov     [rsp+0F88h+var_33A], bx
0x101c11eaf  mov     [rsp+0F88h+var_332], bx
0x101c11eb7  mov     [rsp+0F88h+var_32A], bx
0x101c11ebf  mov     [rsp+0F88h+var_322], bx
0x101c11ec7  mov     [rsp+0F88h+var_31A], bx
0x101c11ecf  mov     [rsp+0F88h+var_312], bx
0x101c11ed7  mov     [rsp+0F88h+var_30A], bx
0x101c11edf  mov     [rsp+0F88h+var_302], bx
0x101c11ee7  mov     [rsp+0F88h+var_2FA], bx
0x101c11eef  mov     [rsp+0F88h+var_2F2], bx
0x101c11ef7  mov     [rsp+0F88h+var_2EA], bx
0x101c11eff  mov     [rsp+0F88h+var_2E2], bx
0x101c11f07  mov     [rsp+0F88h+var_2DA], bx
0x101c11f0f  mov     [rsp+0F88h+var_2D2], bx
0x101c11f17  mov     [rsp+0F88h+var_2CA], bx
0x101c11f1f  mov     [rsp+0F88h+var_2C2], bx
0x101c11f27  mov     [rsp+0F88h+var_2BA], bx
0x101c11f2f  mov     [rsp+0F88h+var_2B2], bx
0x101c11f37  mov     [rsp+0F88h+var_2AA], bx
0x101c11f3f  mov     [rsp+0F88h+var_2A2], bx
0x101c11f47  mov     [rsp+0F88h+var_29A], bx
0x101c11f4f  mov     [rsp+0F88h+var_292], bx
0x101c11f57  mov     [rsp+0F88h+var_28A], bx
0x101c11f5f  mov     [rsp+0F88h+var_282], bx
0x101c11f67  mov     [rsp+0F88h+var_27A], bx
0x101c11f6f  mov     [rsp+0F88h+var_272], bx
0x101c11f77  mov     [rsp+0F88h+var_26A], bx
0x101c11f7f  mov     [rsp+0F88h+var_262], bx
0x101c11f87  mov     [rsp+0F88h+var_25A], bx
0x101c11f8f  mov     [rsp+0F88h+var_252], bx
0x101c11f97  mov     [rsp+0F88h+var_24A], bx
0x101c11f9f  mov     [rsp+0F88h+var_242], bx
0x101c11fa7  mov     [rsp+0F88h+var_23A], bx
0x101c11faf  mov     [rsp+0F88h+var_232], bx
0x101c11fb7  mov     [rsp+0F88h+var_22A], bx
0x101c11fbf  mov     [rsp+0F88h+var_222], bx
0x101c11fc7  mov     [rsp+0F88h+var_21A], bx
0x101c11fcf  mov     [rsp+0F88h+var_212], bx
0x101c11fd7  mov     [rsp+0F88h+var_20A], bx
0x101c11fdf  mov     [rsp+0F88h+var_202], bx
0x101c11fe7  mov     [rsp+0F88h+var_1FA], bx
0x101c11fef  mov     [rsp+0F88h+var_1F2], bx
0x101c11ff7  mov     [rsp+0F88h+var_1EA], bx
0x101c11fff  mov     [rsp+0F88h+var_1E2], bx
0x101c12007  mov     [rsp+0F88h+var_1DA], bx
0x101c1200f  mov     [rsp+0F88h+var_1D2], bx
0x101c12017  mov     [rsp+0F88h+var_1CA], bx
0x101c1201f  mov     [rsp+0F88h+var_1C2], bx
0x101c12027  mov     [rsp+0F88h+var_1BA], bx
0x101c1202f  mov     [rsp+0F88h+var_1B2], bx
0x101c12037  mov     [rsp+0F88h+var_1AA], bx
0x101c1203f  mov     [rsp+0F88h+var_1A2], bx
0x101c12047  mov     [rsp+0F88h+var_19A], bx
0x101c1204f  mov     [rsp+0F88h+var_192], bx
0x101c12057  mov     [rsp+0F88h+var_18A], bx
0x101c1205f  mov     [rsp+0F88h+var_182], bx
0x101c12067  mov     [rsp+0F88h+var_17A], bx
0x101c1206f  mov     [rsp+0F88h+var_172], bx
0x101c12077  mov     [rsp+0F88h+var_16A], bx
0x101c1207f  mov     [rsp+0F88h+var_162], bx
0x101c12087  mov     [rsp+0F88h+var_15A], bx
0x101c1208f  mov     [rsp+0F88h+var_152], bx
0x101c12097  mov     [rsp+0F88h+var_14A], bx
0x101c1209f  mov     [rsp+0F88h+var_142], bx
0x101c120a7  mov     [rsp+0F88h+var_13A], bx
0x101c120af  mov     [rsp+0F88h+var_132], bx
0x101c120b7  mov     [rsp+0F88h+var_12A], bx
0x101c120bf  mov     [rsp+0F88h+var_122], bx
0x101c120c7  mov     [rsp+0F88h+var_11A], bx
0x101c120cf  mov     [rsp+0F88h+var_112], bx
0x101c120d7  mov     [rsp+0F88h+var_10A], bx
0x101c120df  mov     [rsp+0F88h+var_102], bx
0x101c120e7  mov     [rsp+0F88h+var_FA], bx
0x101c120ef  mov     [rsp+0F88h+var_F2], bx
0x101c120f7  mov     [rsp+0F88h+var_EA], bx
0x101c120ff  mov     [rsp+0F88h+var_E2], bx
0x101c12107  mov     [rsp+0F88h+var_DA], bx
0x101c1210f  mov     [rsp+0F88h+var_D2], bx
0x101c12117  mov     [rsp+0F88h+var_CA], bx
0x101c1211f  mov     [rsp+0F88h+var_C2], bx
0x101c12127  mov     [rsp+0F88h+var_BA], bx
0x101c1212f  mov     [rsp+0F88h+var_B2], bx
0x101c12137  mov     [rsp+0F88h+var_AA], bx
0x101c1213f  mov     [rsp+0F88h+var_A2], bx
0x101c12147  mov     [rsp+0F88h+var_9A], bx
0x101c1214f  mov     [rsp+0F88h+var_92], bx
0x101c12157  mov     [rsp+0F88h+var_8A], bx
0x101c1215f  mov     [rsp+0F88h+var_82], bx
0x101c12167  mov     [r11-7Ah], bx
0x101c1216c  mov     [rsp+0F88h+var_EE4], ebx
0x101c12173  mov     [rsp+0F88h+var_F00], bx
0x101c1217b  mov     [rsp+0F88h+var_F24], ebx
0x101c1217f  mov     [rsp+0F88h+var_F04], ebx
0x101c12186  mov     [rsp+0F88h+var_E90], ebx
0x101c1218d  xorps   xmm0, xmm0
0x101c12190  movdqu  [rsp+0F88h+var_E88], xmm0
0x101c12199  mov     [rsp+0F88h+var_E70], ebx
0x101c121a0  xorps   xmm1, xmm1
0x101c121a3  movdqu  [rsp+0F88h+var_E68], xmm1
0x101c121ac  mov     [rsp+0F88h+var_F08], ebx
0x101c121b3  mov     [rsp+0F88h+var_EF8], ebx
0x101c121ba  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x101c121c1  cmp     [rax], ebx
0x101c121c3  jz      short loc_101C121DC
0x101c121c5  lea     rcx, [r11-0DD8h]; lpPerformanceCount
0x101c121cc  call    cs:__imp_QueryPerformanceCounter
0x101c121d2  mov     rax, [rsp+0F88h+var_DD8]
0x101c121da  jmp     short loc_101C121E4
0x101c121dc  mov     rax, ds:7FFE0008h
0x101c121e4  mov     [rsp+0F88h+var_DE0], rax
0x101c121ec  mov     edx, cs:dword_103172528
0x101c121f2  test    edx, edx
0x101c121f4  jz      short loc_101C1226D
0x101c121f6  cmp     cs:byte_10316E99D, bl
0x101c121fc  jz      short loc_101C12207
0x101c121fe  cmp     cs:word_103185B6E, bx
0x101c12205  jnz     short loc_101C12247
0x101c12207  mov     rax, [rdi+110h]
0x101c1220e  mov     rcx, [rax+6B0h]
0x101c12215  test    rcx, rcx
0x101c12218  jz      short loc_101C12247
0x101c1221a  mov     rcx, [rcx+8F8h]
0x101c12221  test    rcx, rcx
0x101c12224  jz      short loc_101C12247
0x101c12226  mov     eax, [rcx+34h]
0x101c12229  xorps   xmm7, xmm7
0x101c1222c  cvtsi2sd xmm7, rax
0x101c12231  movsd   [rsp+0F88h+var_EB0], xmm7
0x101c1223a  mov     r12d, [rcx+38h]
0x101c1223e  xorps   xmm8, xmm8
0x101c12242  jmp     loc_101C122CA
0x101c12247  mov     ecx, cs:dword_103186EF4
0x101c1224d  mov     eax, ecx
0x101c1224f  mov     r9d, cs:dword_103186EEC
0x101c12256  test    ecx, ecx
0x101c12258  cmovs   eax, r9d
0x101c1225c  movd    xmm0, eax
0x101c12260  cvtdq2pd xmm0, xmm0
0x101c12264  mov     r8d, cs:dword_1031E0918
0x101c1226b  jmp     short loc_101C12289
0x101c1226d  mov     r8d, cs:dword_1031E0918
0x101c12274  xorps   xmm0, xmm0
0x101c12277  cvtsi2sd xmm0, r8
0x101c1227c  mov     ecx, cs:dword_103186EF4
0x101c12282  mov     r9d, cs:dword_103186EEC
0x101c12289  xorps   xmm8, xmm8
0x101c1228d  comisd  xmm0, xmm8
0x101c12292  jbe     loc_101C12352
0x101c12298  test    edx, edx
0x101c1229a  jz      short loc_101C122AF
0x101c1229c  test    ecx, ecx
0x101c1229e  cmovs   ecx, r9d
0x101c122a2  movd    xmm7, ecx
0x101c122a6  cvtdq2pd xmm7, xmm7
0x101c122aa  jmp     loc_101C1235A
0x101c122af  mov     eax, r8d
0x101c122b2  xorps   xmm7, xmm7
0x101c122b5  cvtsi2sd xmm7, rax
0x101c122ba  movsd   [rsp+0F88h+var_EB0], xmm7
0x101c122c3  mov     r12d, cs:dword_1031E0920
0x101c122ca  mov     [rsp+0F88h+var_EF4], r12d
0x101c122d2  mov     rax, [rdi+110h]
0x101c122d9  mov     r8, [rax+6B0h]
0x101c122e0  mov     rdx, gs:58h
0x101c122e9  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101c122f0  mov     ecx, [rax]
0x101c122f2  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101c122f9  mov     eax, [rax]
0x101c122fb  add     rax, [rdx+rcx*8]
0x101c122ff  mov     rax, [rax+8]
0x101c12303  mov     rcx, [rax+60h]
0x101c12307  mov     rsi, [rcx+4F8h]
0x101c1230e  mov     [rcx+4F8h], r8
0x101c12315  mov     [rsp+0F88h+var_E98], rsi
0x101c1231d  test    r15b, r15b
0x101c12320  jz      short loc_101C12341
0x101c12322  test    r14b, r14b
0x101c12325  jnz     short loc_101C12341
0x101c12327  ucomisd xmm7, xmm8
0x101c1232c  jp      loc_101C12694
0x101c12332  jnz     loc_101C12694
0x101c12338  test    r12d, r12d
0x101c1233b  jnz     loc_101C12694
0x101c12341  cmp     [rsp+0F88h+arg_20], 0
0x101c12349  jz      short loc_101C12382
0x101c1234b  lock inc qword ptr [rdi+58h]
0x101c12350  jmp     short loc_101C12392
0x101c12352  movsd   xmm7, cs:qword_1031E0928
0x101c1235a  movsd   [rsp+0F88h+var_EB0], xmm7
0x101c12363  test    edx, edx
0x101c12365  jz      loc_101C122C3
0x101c1236b  mov     r12d, cs:dword_103186EF8
0x101c12372  test    r12d, r12d
0x101c12375  cmovs   r12d, cs:dword_103186EF0
0x101c1237d  jmp     loc_101C122CA
0x101c12382  test    r15b, r15b
0x101c12385  jz      short loc_101C1238E
0x101c12387  lock inc qword ptr [rdi+50h]
0x101c1238c  jmp     short loc_101C12392
0x101c1238e  inc     qword ptr [rdi+48h]
0x101c12392  movsd   xmm6, cs:__real@41cf400000000000
0x101c1239a  comisd  xmm7, xmm8
0x101c1239f  jbe     loc_101C12473
0x101c123a5  mov     [rsp+0F88h+var_E70], 2
0x101c123b0  movaps  xmm1, xmm7
0x101c123b3  mulsd   xmm1, cs:__real@4060000000000000
0x101c123bb  movaps  xmm0, xmm6
0x101c123be  divsd   xmm0, xmm1
0x101c123c2  cvttsd2si rax, xmm0
0x101c123c7  mov     qword ptr [rsp+0F88h+var_E68], rax
0x101c123cf  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x101c123d6  cmp     dword ptr [rax], 0
0x101c123d9  jz      short loc_101C123F3
0x101c123db  lea     rcx, [rsp+0F88h+PerformanceCount]; lpPerformanceCount
0x101c123e3  call    cs:__imp_QueryPerformanceCounter
0x101c123e9  mov     rcx, qword ptr [rsp+0F88h+PerformanceCount]
0x101c123f1  jmp     short loc_101C123FB
0x101c123f3  mov     rcx, ds:7FFE0008h
0x101c123fb  mov     r9, 0FFFFFFFFFFFFFFFFh
0x101c12402  mov     r13, 346DC5D63886594Bh
0x101c1240c  cmp     rcx, r9
0x101c1240f  jnz     short loc_101C12424
0x101c12411  mov     rdx, r9
0x101c12414  mov     eax, edx
0x101c12416  shl     rax, 14h
0x101c1241a  mov     qword ptr [rsp+0F88h+var_E68+8], rax
0x101c12422  jmp     short loc_101C12484
0x101c12424  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x101c1242b  cmp     dword ptr [rax], 0
0x101c1242e  jz      short loc_101C12459
0x101c12430  mov     rax, cs:__imp_?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A; _LARGE_INTEGER Base_PublicGlobals::sm_QueryPerformanceFrequency
0x101c12437  mov     r8, [rax]
0x101c1243a  imul    rax, rcx, 3E8h
0x101c12441  xor     edx, edx
0x101c12443  div     r8
0x101c12446  mov     rdx, rax
  ... truncated ...
```
