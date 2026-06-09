# DBMgr::SyncAndLinkReplicaSetupPhase(ReplicaState *,ulong,wchar_t *,int,ReplicaType,DBTABLE *,AsynchronousDiskPool *)

- ea: `0x101702520`
- end: `0x101707129`
- name: `?SyncAndLinkReplicaSetupPhase@DBMgr@@QEAAXPEAVReplicaState@@KPEA_WHW4ReplicaType@@PEAVDBTABLE@@PEAVAsynchronousDiskPool@@@Z`
- size: `19465`
- prototype: ``
- caller_count: `2`
- callee_count: `65`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x101701b50`
- `0x10170da80`

## callees

- `0x100401380`
- `0x1004013f0`
- `0x100401490`
- `0x100402000`
- `0x1004022e0`
- `0x100402620`
- `0x100402d60`
- `0x100403030`
- `0x10040da40`
- `0x10040da80`
- `0x10040eca0`
- `0x10041b5d0`
- `0x10041ba80`
- `0x10042d750`
- `0x10042db70`
- `0x10043ba50`
- `0x1004729d0`
- `0x10047bc10`
- `0x10047efc0`
- `0x10047ffb0`
- `0x100480030`
- `0x100569c10`
- `0x100569d30`
- `0x1005c8640`
- `0x1005cc960`
- `0x1005cccc0`
- `0x1005ce7c0`
- `0x1005cef70`
- `0x1005d9f70`
- `0x1005e0a50`
- `0x1005f1f00`
- `0x10069f4f0`
- `0x10072d4d0`
- `0x10072d690`
- `0x101648900`
- `0x101685890`
- `0x1016bf930`
- `0x1016bf9b0`
- `0x1016c9e80`
- `0x1016d4350`
- `0x1016f3940`
- `0x101702520`
- `0x101724350`
- `0x1017279b0`
- `0x10172e2f0`
- `0x101774330`
- `0x10179f660`
- `0x1017a3b30`
- `0x1017d4550`
- `0x101813de0`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x10170382d`
- `KERNEL32!VirtualProtect` at `0x101703a7f`
- `KERNEL32!VirtualProtect` at `0x10170485a`
- `KERNEL32!VirtualProtect` at `0x101704b47`
- `KERNEL32!VirtualProtect` at `0x10170585b`
- `KERNEL32!VirtualProtect` at `0x101705aaf`
- `KERNEL32!VirtualProtect` at `0x10170689a`
- `KERNEL32!VirtualProtect` at `0x101706bd3`
- `KERNEL32!VirtualProtect` at `0x10170382d`
- `KERNEL32!VirtualProtect` at `0x101703a7f`
- `KERNEL32!VirtualProtect` at `0x10170485a`
- `KERNEL32!VirtualProtect` at `0x101704b47`
- `KERNEL32!VirtualProtect` at `0x10170585b`
- `KERNEL32!VirtualProtect` at `0x101705aaf`
- `KERNEL32!VirtualProtect` at `0x10170689a`
- `KERNEL32!VirtualProtect` at `0x101706bd3`
- `KERNEL32!QueryPerformanceCounter` at `0x1017029c3`
- `KERNEL32!QueryPerformanceCounter` at `0x101702bea`
- `KERNEL32!QueryPerformanceCounter` at `0x101702cb0`
- `KERNEL32!QueryPerformanceCounter` at `0x10170307b`
- `KERNEL32!QueryPerformanceCounter` at `0x101704d74`
- `KERNEL32!QueryPerformanceCounter` at `0x101704e3a`
- `KERNEL32!QueryPerformanceCounter` at `0x10170519d`
- `KERNEL32!QueryPerformanceCounter` at `0x101705263`
- `KERNEL32!QueryPerformanceCounter` at `0x101706e67`
- `KERNEL32!QueryPerformanceCounter` at `0x101706f2d`
- `KERNEL32!QueryPerformanceCounter` at `0x1017029c3`
- `KERNEL32!QueryPerformanceCounter` at `0x101702bea`
- `KERNEL32!QueryPerformanceCounter` at `0x101702cb0`
- `KERNEL32!QueryPerformanceCounter` at `0x10170307b`
- `KERNEL32!QueryPerformanceCounter` at `0x101704d74`
- `KERNEL32!QueryPerformanceCounter` at `0x101704e3a`
- `KERNEL32!QueryPerformanceCounter` at `0x10170519d`
- `KERNEL32!QueryPerformanceCounter` at `0x101705263`
- `KERNEL32!QueryPerformanceCounter` at `0x101706e67`
- `KERNEL32!QueryPerformanceCounter` at `0x101706f2d`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101702dc1`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101704f33`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1017053a0`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101707051`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101702b39`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101704cc3`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1017050ec`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101706dbe`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101702c44`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101704dce`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x1017051f7`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101706ec1`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1017029a7`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101702bce`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101702c94`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10170305f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101704d58`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101704e1e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101705181`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101705247`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101706e4b`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101706f11`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1017044ac`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1017064ec`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x101703507`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x10170553b`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101703255`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101703285`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1017070f5`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1017070f5`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x101702644`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10170273f`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10170273f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017027c7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101703149`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017027c7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101703149`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017035c3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017055f7`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017035c3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017055f7`
- `sqldk!SystemThread_TlsIndex` at `0x101702b71`
- `sqldk!SystemThread_TlsIndex` at `0x101702ecb`
- `sqldk!SystemThread_TlsIndex` at `0x10170355c`
- `sqldk!SystemThread_TlsIndex` at `0x101703694`
- `sqldk!SystemThread_TlsIndex` at `0x101703e92`
- `sqldk!SystemThread_TlsIndex` at `0x101704538`
- `sqldk!SystemThread_TlsIndex` at `0x101704cfb`
- `sqldk!SystemThread_TlsIndex` at `0x101705124`
- `sqldk!SystemThread_TlsIndex` at `0x101705590`
- `sqldk!SystemThread_TlsIndex` at `0x1017056c2`
- `sqldk!SystemThread_TlsIndex` at `0x101705ed2`
- `sqldk!SystemThread_TlsIndex` at `0x101706578`
- `sqldk!SystemThread_TlsIndex` at `0x101706dee`
- `sqldk!SystemThread_TlsIndex` at `0x1017070bd`
- `sqldk!SystemThread_TlsOffset` at `0x101702b7a`
- `sqldk!SystemThread_TlsOffset` at `0x101702ed4`
- `sqldk!SystemThread_TlsOffset` at `0x101703565`
- `sqldk!SystemThread_TlsOffset` at `0x10170369d`
- `sqldk!SystemThread_TlsOffset` at `0x101703e9b`
- `sqldk!SystemThread_TlsOffset` at `0x101704541`
- `sqldk!SystemThread_TlsOffset` at `0x101704d04`
- `sqldk!SystemThread_TlsOffset` at `0x10170512d`
- `sqldk!SystemThread_TlsOffset` at `0x101705599`
- `sqldk!SystemThread_TlsOffset` at `0x1017056cb`
- `sqldk!SystemThread_TlsOffset` at `0x101705edb`
- `sqldk!SystemThread_TlsOffset` at `0x101706581`
- `sqldk!SystemThread_TlsOffset` at `0x101706df7`
- `sqldk!SystemThread_TlsOffset` at `0x1017070c6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101702efd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1017070df`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101702efd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1017070df`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101702dd6`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101704f48`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1017053b5`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101707066`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101702dd6`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101704f48`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1017053b5`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101707066`

## string_xrefs

- `0x101704f94`: `DBID: [%d] enabled copy-on-write for primary database`
- `0x10170542f`: `DBID: [%d] refresh files for consistent REDO copy activities`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall DBMgr::SyncAndLinkReplicaSetupPhase(
        DBMgr *a1,
        _QWORD *a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        RecoveryUnit *a7,
        struct AsynchronousDiskPool *a8)
{
  struct DatabaseStartupInfo *v11; // r15
  _QWORD *v12; // r14
  char *v13; // rdi
  __int64 v14; // rcx
  AsynchronousDiskAction *v15; // rax
  AsynchronousDiskAction *v16; // rax
  __int16 i; // di
  __int64 v18; // rcx
  ReplicaState *v19; // rsi
  DBMirroring *v20; // rdi
  LsMgr *LsMgrWithRef; // rax
  LsMgr *v22; // rdi
  struct LsMgr *v23; // rax
  struct LsMgr *v24; // rdi
  DirtyPageMgr *QuadPart; // rax
  char *v26; // rax
  RecoveryUnit *v27; // r14
  __int64 v28; // rax
  __int64 v29; // rdi
  bool v30; // zf
  __int64 v31; // rdi
  __int64 v32; // rdi
  DirtyPageMgr *v33; // rax
  DirtyPageMgr *v34; // rax
  __int64 v35; // rax
  _QWORD *v36; // rdi
  int v37; // r8d
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rdi
  __int64 v43; // rcx
  _DWORD *v44; // rcx
  int v45; // edi
  DirtyPageMgr *v46; // rax
  char *v47; // rax
  unsigned int v48; // r14d
  struct DBTABLE *v49; // rax
  RecoveryUnit *v50; // rdx
  __int64 v51; // r9
  unsigned int v52; // r14d
  _BYTE *v53; // rcx
  RecoveryUnit *v54; // rsi
  struct DBTABLE *v55; // rdi
  char *v56; // r12
  ReplicaState *v57; // r15
  char *v58; // rax
  RecoveryUnit *v59; // r13
  char *v60; // rdi
  __int64 FCB; // rsi
  int v62; // eax
  struct DBTABLE *v63; // r14
  __int64 v64; // rdi
  int v65; // eax
  RecoveryUnit *v66; // rdi
  __int64 v67; // rax
  struct CSessionTraceFlags *v68; // rcx
  struct SEInternalTLS *v69; // rcx
  _QWORD *v70; // r14
  __int64 v71; // rax
  __int64 v72; // rcx
  int *v73; // rdi
  void *v74; // rcx
  signed __int32 v75; // eax
  signed __int32 v76; // ett
  _QWORD *v77; // rdi
  unsigned int v78; // esi
  __int64 v79; // rcx
  int *v80; // rdi
  void *v81; // rcx
  signed __int32 v82; // eax
  signed __int32 v83; // ett
  signed __int32 v84; // eax
  signed __int32 v85; // ett
  _QWORD *v86; // rdi
  unsigned int v87; // esi
  _QWORD *v88; // rax
  unsigned int v89; // r8d
  __int64 v90; // rdx
  _DWORD *v91; // rcx
  _QWORD *v92; // r9
  __int64 v93; // rax
  unsigned int v94; // edx
  _QWORD *v95; // rcx
  unsigned int *v96; // r8
  __int64 v97; // rdx
  __int64 v98; // r11
  char v99; // al
  char v100; // al
  LSN *v101; // rsi
  _DWORD *v102; // rdi
  int v103; // eax
  int v104; // ecx
  LSN *v105; // rdx
  unsigned __int16 v106; // di
  __int64 v107; // r11
  char v108; // al
  char v109; // al
  unsigned __int16 v110; // r11
  RecoveryUnit *v112; // rdi
  __int64 v113; // r10
  __int64 v114; // rax
  __int64 v115; // rax
  __int64 v116; // rax
  int *v117; // rdx
  __int64 v118; // rcx
  DWORD v119; // ecx
  _DWORD **v120; // rax
  __int64 v121; // rdx
  __int64 v122; // r11
  char v123; // al
  char v124; // al
  __int16 v125; // r11
  __int64 v126; // xmm1_8
  __int64 v127; // rcx
  int *v128; // rdi
  void *v129; // rcx
  signed __int32 v130; // eax
  signed __int32 v131; // ett
  _QWORD *v132; // rdi
  unsigned int v133; // esi
  __int64 v134; // rcx
  int *v135; // rdi
  void *v136; // rcx
  signed __int32 v137; // eax
  signed __int32 v138; // ett
  _QWORD *v139; // rdi
  unsigned int v140; // esi
  __int64 v141; // rdi
  __int64 v142; // rdi
  __int64 v143; // rdi
  DirtyPageMgr *v144; // rax
  DirtyPageMgr *v145; // rax
  __int64 v146; // rax
  _QWORD *v147; // rdx
  int v148; // eax
  __int64 v149; // rcx
  __int64 v150; // rdi
  __int64 v151; // rdi
  __int64 v152; // rdi
  DirtyPageMgr *v153; // rax
  DirtyPageMgr *v154; // rax
  __int64 v155; // rax
  _QWORD *v156; // rdi
  int v157; // r8d
  __int64 v158; // rcx
  __int64 v159; // r15
  char *v160; // rax
  char *v161; // rdi
  __int64 v162; // rax
  int v163; // ecx
  struct DBTABLE *v164; // rdi
  RecoveryUnit *v165; // rdi
  __int64 v166; // rax
  struct CSessionTraceFlags *v167; // rcx
  struct SEInternalTLS *v168; // rcx
  _QWORD *v169; // r14
  __int64 v170; // rax
  __int64 v171; // rcx
  int *v172; // rdi
  void *v173; // rcx
  signed __int32 v174; // eax
  signed __int32 v175; // ett
  _QWORD *v176; // rdi
  unsigned int v177; // esi
  __int64 v178; // rcx
  int *v179; // rdi
  void *v180; // rcx
  signed __int32 v181; // eax
  signed __int32 v182; // ett
  signed __int32 v183; // eax
  signed __int32 v184; // ett
  _QWORD *v185; // rdi
  unsigned int v186; // esi
  _QWORD *v187; // rax
  unsigned int v188; // r8d
  __int64 v189; // rdx
  _DWORD *v190; // rcx
  _QWORD *v191; // r9
  __int64 v192; // rax
  unsigned int v193; // edx
  _QWORD *v194; // rcx
  unsigned int *v195; // r8
  __int64 v196; // rdx
  __int64 v197; // r11
  char v198; // al
  char v199; // al
  LSN *v200; // rsi
  _DWORD *v201; // rdi
  int v202; // eax
  int v203; // ecx
  LSN *v204; // rdx
  unsigned __int16 v205; // di
  __int64 v206; // r11
  char v207; // al
  char v208; // al
  unsigned __int16 v209; // r11
  RecoveryUnit *v211; // rdi
  __int64 v212; // r10
  __int64 v213; // rax
  __int64 v214; // rax
  __int64 v215; // rax
  int *v216; // rdx
  __int64 v217; // rcx
  DWORD v218; // ecx
  _DWORD **v219; // rax
  __int64 v220; // rdx
  __int64 v221; // r11
  char v222; // al
  char v223; // al
  __int16 v224; // r11
  __int64 v225; // xmm1_8
  __int64 v226; // rcx
  int *v227; // rdi
  void *v228; // rcx
  signed __int32 v229; // eax
  signed __int32 v230; // ett
  _QWORD *v231; // rdi
  unsigned int v232; // esi
  __int64 v233; // rax
  __int64 v234; // rcx
  int *v235; // rdi
  void *v236; // rcx
  signed __int32 v237; // eax
  signed __int32 v238; // ett
  _QWORD *v239; // rdi
  unsigned int v240; // esi
  __int64 v241; // rdi
  __int64 v242; // rdi
  __int64 v243; // rdi
  ReplicaState *v244; // rax
  DirtyPageMgr *v245; // rax
  __int64 v246; // rax
  const struct LSN *v247; // rdx
  _QWORD *v248; // rdi
  int v249; // eax
  __int64 v250; // rcx
  __int64 v251; // rbx
  struct Worker *v252; // rcx
  signed __int32 v253[8]; // [rsp+0h] [rbp-1AA8h] BYREF
  struct LSN *v254; // [rsp+20h] [rbp-1A88h]
  _QWORD *v255; // [rsp+60h] [rbp-1A48h] BYREF
  char v256; // [rsp+68h] [rbp-1A40h]
  int v257; // [rsp+6Ch] [rbp-1A3Ch]
  unsigned int v258; // [rsp+70h] [rbp-1A38h]
  int v259; // [rsp+78h] [rbp-1A30h] BYREF
  __int16 v260; // [rsp+7Ch] [rbp-1A2Ch]
  RecoveryUnit *v261; // [rsp+80h] [rbp-1A28h]
  char v262; // [rsp+88h] [rbp-1A20h]
  char v263; // [rsp+89h] [rbp-1A1Fh]
  char v264; // [rsp+8Ah] [rbp-1A1Eh]
  char v265; // [rsp+8Bh] [rbp-1A1Dh]
  char v266; // [rsp+8Ch] [rbp-1A1Ch]
  char v267; // [rsp+8Dh] [rbp-1A1Bh]
  char v268; // [rsp+8Eh] [rbp-1A1Ah]
  char v269; // [rsp+8Fh] [rbp-1A19h]
  int v270; // [rsp+90h] [rbp-1A18h]
  int v271; // [rsp+98h] [rbp-1A10h]
  int v272; // [rsp+A0h] [rbp-1A08h]
  int v273; // [rsp+A8h] [rbp-1A00h]
  int v274; // [rsp+B0h] [rbp-19F8h]
  int v275; // [rsp+B8h] [rbp-19F0h]
  int v276; // [rsp+C0h] [rbp-19E8h]
  int v277; // [rsp+C8h] [rbp-19E0h]
  RecoveryUnit *v278; // [rsp+D0h] [rbp-19D8h]
  __int64 v279; // [rsp+D8h] [rbp-19D0h]
  char *v280; // [rsp+E0h] [rbp-19C8h]
  struct DBTABLE *v281; // [rsp+E8h] [rbp-19C0h]
  __int64 v282; // [rsp+F0h] [rbp-19B8h] BYREF
  __int16 v283; // [rsp+F8h] [rbp-19B0h]
  __int64 v284; // [rsp+100h] [rbp-19A8h] BYREF
  __int16 v285; // [rsp+108h] [rbp-19A0h]
  char v286; // [rsp+110h] [rbp-1998h]
  char v287; // [rsp+111h] [rbp-1997h]
  char v288; // [rsp+112h] [rbp-1996h]
  bool v289; // [rsp+113h] [rbp-1995h]
  char v291; // [rsp+115h] [rbp-1993h]
  bool v292; // [rsp+116h] [rbp-1992h]
  char v293; // [rsp+117h] [rbp-1991h]
  char v294; // [rsp+118h] [rbp-1990h]
  char v295; // [rsp+119h] [rbp-198Fh]
  char v296; // [rsp+11Ah] [rbp-198Eh]
  char v297; // [rsp+11Bh] [rbp-198Dh]
  char v298; // [rsp+11Ch] [rbp-198Ch]
  char v299; // [rsp+11Dh] [rbp-198Bh]
  char v300; // [rsp+11Eh] [rbp-198Ah]
  char v301; // [rsp+11Fh] [rbp-1989h]
  char v302; // [rsp+120h] [rbp-1988h]
  char v303; // [rsp+121h] [rbp-1987h]
  char v304; // [rsp+122h] [rbp-1986h]
  bool v305; // [rsp+123h] [rbp-1985h]
  char v306; // [rsp+124h] [rbp-1984h]
  char v307; // [rsp+125h] [rbp-1983h]
  char v308; // [rsp+126h] [rbp-1982h]
  char v309; // [rsp+127h] [rbp-1981h]
  char v310; // [rsp+128h] [rbp-1980h]
  char v311; // [rsp+129h] [rbp-197Fh]
  char v312; // [rsp+12Ah] [rbp-197Eh]
  char v313; // [rsp+12Bh] [rbp-197Dh]
  char v314; // [rsp+12Ch] [rbp-197Ch]
  char v315; // [rsp+12Dh] [rbp-197Bh]
  __int16 v316; // [rsp+130h] [rbp-1978h]
  __int16 v317; // [rsp+138h] [rbp-1970h]
  __int16 v318; // [rsp+140h] [rbp-1968h]
  __int16 v319; // [rsp+148h] [rbp-1960h]
  __int16 v320; // [rsp+150h] [rbp-1958h]
  __int16 v321; // [rsp+158h] [rbp-1950h]
  __int16 v322; // [rsp+160h] [rbp-1948h]
  __int16 v323; // [rsp+168h] [rbp-1940h]
  __int16 v324; // [rsp+170h] [rbp-1938h]
  __int16 v325; // [rsp+178h] [rbp-1930h]
  __int16 v326; // [rsp+180h] [rbp-1928h]
  __int16 v327; // [rsp+188h] [rbp-1920h]
  __int16 v328; // [rsp+190h] [rbp-1918h]
  __int16 v329; // [rsp+198h] [rbp-1910h]
  __int16 v330; // [rsp+1A0h] [rbp-1908h]
  __int16 v331; // [rsp+1A8h] [rbp-1900h]
  __int16 v332; // [rsp+1B0h] [rbp-18F8h]
  __int64 v333; // [rsp+1B8h] [rbp-18F0h] BYREF
  __int16 v334; // [rsp+1C0h] [rbp-18E8h]
  char v335; // [rsp+1C8h] [rbp-18E0h]
  unsigned int v336; // [rsp+1CCh] [rbp-18DCh]
  __int16 v337; // [rsp+1D0h] [rbp-18D8h]
  __int64 v338; // [rsp+1D8h] [rbp-18D0h]
  ReplicaState *v339; // [rsp+1E0h] [rbp-18C8h] BYREF
  LSN v340; // [rsp+1E8h] [rbp-18C0h]
  DWORD LowPart; // [rsp+1F0h] [rbp-18B8h]
  LSN v342; // [rsp+1F4h] [rbp-18B4h]
  DWORD v343; // [rsp+1FCh] [rbp-18ACh]
  char *v344; // [rsp+200h] [rbp-18A8h]
  int v345; // [rsp+208h] [rbp-18A0h] BYREF
  unsigned int v346; // [rsp+20Ch] [rbp-189Ch] BYREF
  int v347; // [rsp+210h] [rbp-1898h]
  int v348; // [rsp+214h] [rbp-1894h]
  unsigned int v349; // [rsp+218h] [rbp-1890h] BYREF
  int v350; // [rsp+21Ch] [rbp-188Ch]
  int v351; // [rsp+220h] [rbp-1888h]
  __int64 v352; // [rsp+224h] [rbp-1884h]
  int v353; // [rsp+22Ch] [rbp-187Ch]
  __int64 v354; // [rsp+230h] [rbp-1878h]
  int v355; // [rsp+238h] [rbp-1870h]
  __int64 v356; // [rsp+240h] [rbp-1868h] BYREF
  unsigned __int16 v357; // [rsp+248h] [rbp-1860h]
  LSN v358; // [rsp+250h] [rbp-1858h] BYREF
  unsigned __int16 v359; // [rsp+258h] [rbp-1850h]
  __int64 v360; // [rsp+260h] [rbp-1848h] BYREF
  __int16 v361; // [rsp+268h] [rbp-1840h]
  __int64 v362; // [rsp+270h] [rbp-1838h] BYREF
  unsigned __int16 v363; // [rsp+278h] [rbp-1830h]
  LSN v364; // [rsp+280h] [rbp-1828h] BYREF
  unsigned __int16 v365; // [rsp+288h] [rbp-1820h]
  int v366; // [rsp+290h] [rbp-1818h] BYREF
  __int16 v367; // [rsp+294h] [rbp-1814h]
  int v368; // [rsp+298h] [rbp-1810h] BYREF
  __int16 v369; // [rsp+29Ch] [rbp-180Ch]
  int v370; // [rsp+2A0h] [rbp-1808h] BYREF
  __int16 v371; // [rsp+2A4h] [rbp-1804h]
  int v372; // [rsp+2A8h] [rbp-1800h] BYREF
  __int16 v373; // [rsp+2ACh] [rbp-17FCh]
  int v374; // [rsp+2B0h] [rbp-17F8h] BYREF
  __int16 v375; // [rsp+2B4h] [rbp-17F4h]
  int v376; // [rsp+2B8h] [rbp-17F0h] BYREF
  __int16 v377; // [rsp+2BCh] [rbp-17ECh]
  struct SEInternalTLS *SETLSFromTlsMaybeNull; // [rsp+2C0h] [rbp-17E8h]
  volatile signed __int64 *v379; // [rsp+2C8h] [rbp-17E0h]
  volatile signed __int64 *v380; // [rsp+2D0h] [rbp-17D8h]
  volatile signed __int64 *v381; // [rsp+2D8h] [rbp-17D0h]
  struct SEInternalTLS *v382; // [rsp+2E0h] [rbp-17C8h]
  volatile signed __int64 *v383; // [rsp+2E8h] [rbp-17C0h]
  DBMgr *v384; // [rsp+2F0h] [rbp-17B8h] BYREF
  int v385; // [rsp+2F8h] [rbp-17B0h]
  int v386; // [rsp+300h] [rbp-17A8h]
  int v387; // [rsp+308h] [rbp-17A0h]
  unsigned int v388; // [rsp+310h] [rbp-1798h]
  unsigned int v389; // [rsp+314h] [rbp-1794h]
  int v390; // [rsp+318h] [rbp-1790h]
  int v391; // [rsp+320h] [rbp-1788h]
  int v392; // [rsp+328h] [rbp-1780h]
  int v393; // [rsp+330h] [rbp-1778h]
  int v394; // [rsp+338h] [rbp-1770h]
  int v395; // [rsp+340h] [rbp-1768h]
  int v396; // [rsp+348h] [rbp-1760h]
  unsigned int v397; // [rsp+350h] [rbp-1758h]
  unsigned int v398; // [rsp+354h] [rbp-1754h]
  unsigned int v399; // [rsp+358h] [rbp-1750h] BYREF
  int v400; // [rsp+35Ch] [rbp-174Ch] BYREF
  int v401; // [rsp+360h] [rbp-1748h]
  int v402; // [rsp+368h] [rbp-1740h]
  int v403; // [rsp+370h] [rbp-1738h]
  int v404; // [rsp+378h] [rbp-1730h]
  int v405; // [rsp+380h] [rbp-1728h]
  int v406; // [rsp+388h] [rbp-1720h]
  BOOL v407; // [rsp+390h] [rbp-1718h]
  int v408; // [rsp+398h] [rbp-1710h]
  BOOL v409; // [rsp+3A0h] [rbp-1708h]
  int v410; // [rsp+3A8h] [rbp-1700h]
  int v411; // [rsp+3B0h] [rbp-16F8h]
  int v412; // [rsp+3B8h] [rbp-16F0h]
  int v413; // [rsp+3C0h] [rbp-16E8h]
  BOOL v414; // [rsp+3C8h] [rbp-16E0h]
  DirtyPageMgr *v415; // [rsp+3D0h] [rbp-16D8h] BYREF
  signed __int64 v416; // [rsp+3D8h] [rbp-16D0h]
  __int64 v417; // [rsp+3E0h] [rbp-16C8h]
  DirtyPageMgr *v418; // [rsp+3E8h] [rbp-16C0h] BYREF
  DirtyPageMgr *v419; // [rsp+3F0h] [rbp-16B8h] BYREF
  DirtyPageMgr *v420; // [rsp+3F8h] [rbp-16B0h] BYREF
  _QWORD *v421; // [rsp+400h] [rbp-16A8h]
  _QWORD *v422; // [rsp+408h] [rbp-16A0h]
  _QWORD *v423; // [rsp+410h] [rbp-1698h]
  _QWORD *v424; // [rsp+418h] [rbp-1690h]
  signed __int64 UniqueThread_low; // [rsp+420h] [rbp-1688h]
  int v426; // [rsp+428h] [rbp-1680h]
  DirtyPageMgr *v427; // [rsp+430h] [rbp-1678h] BYREF
  DirtyPageMgr *v428; // [rsp+438h] [rbp-1670h] BYREF
  signed __int64 v429; // [rsp+440h] [rbp-1668h]
  __int64 v430; // [rsp+448h] [rbp-1660h]
  DirtyPageMgr *v431; // [rsp+450h] [rbp-1658h] BYREF
  DirtyPageMgr *v432; // [rsp+458h] [rbp-1650h] BYREF
  _QWORD *v433; // [rsp+460h] [rbp-1648h]
  _QWORD *v434; // [rsp+468h] [rbp-1640h]
  _QWORD *v435; // [rsp+470h] [rbp-1638h]
  __int64 v436; // [rsp+478h] [rbp-1630h]
  _QWORD *v437; // [rsp+480h] [rbp-1628h]
  signed __int64 v438; // [rsp+488h] [rbp-1620h]
  __int64 v439; // [rsp+490h] [rbp-1618h]
  DirtyPageMgr *v440; // [rsp+498h] [rbp-1610h] BYREF
  unsigned __int16 v441; // [rsp+4A0h] [rbp-1608h]
  __int64 v442; // [rsp+4A8h] [rbp-1600h] BYREF
  __int16 v443; // [rsp+4B0h] [rbp-15F8h]
  __int16 v444; // [rsp+4B8h] [rbp-15F0h]
  unsigned __int16 v445; // [rsp+4C0h] [rbp-15E8h]
  int v446; // [rsp+4C8h] [rbp-15E0h] BYREF
  unsigned int v447; // [rsp+4CCh] [rbp-15DCh] BYREF
  BOOL v448; // [rsp+4D0h] [rbp-15D8h]
  __int16 v449; // [rsp+4D8h] [rbp-15D0h]
  unsigned __int16 v450; // [rsp+4E0h] [rbp-15C8h]
  unsigned __int16 v451; // [rsp+4E8h] [rbp-15C0h]
  __int16 v452; // [rsp+4F0h] [rbp-15B8h]
  __int16 v453; // [rsp+4F8h] [rbp-15B0h]
  __int64 v454; // [rsp+500h] [rbp-15A8h]
  __int64 v455; // [rsp+508h] [rbp-15A0h] BYREF
  __int16 v456; // [rsp+510h] [rbp-1598h]
  int v457; // [rsp+518h] [rbp-1590h]
  int v458; // [rsp+520h] [rbp-1588h]
  int v459; // [rsp+528h] [rbp-1580h]
  int v460; // [rsp+530h] [rbp-1578h]
  int v461; // [rsp+538h] [rbp-1570h] BYREF
  __int64 v462; // [rsp+540h] [rbp-1568h]
  __int64 v463; // [rsp+548h] [rbp-1560h] BYREF
  __int16 v464; // [rsp+550h] [rbp-1558h]
  __int64 v465; // [rsp+558h] [rbp-1550h] BYREF
  __int16 v466; // [rsp+560h] [rbp-1548h]
  unsigned int *v467; // [rsp+568h] [rbp-1540h]
  LSN *v468; // [rsp+570h] [rbp-1538h]
  unsigned int *v469; // [rsp+578h] [rbp-1530h]
  DirtyPageMgr *v470; // [rsp+580h] [rbp-1528h] BYREF
  DirtyPageMgr *v471; // [rsp+588h] [rbp-1520h] BYREF
  DirtyPageMgr *v472; // [rsp+590h] [rbp-1518h] BYREF
  LSN *v473; // [rsp+598h] [rbp-1510h]
  LSN v474; // [rsp+5A0h] [rbp-1508h] BYREF
  __int16 v475; // [rsp+5A8h] [rbp-1500h]
  __int64 v476; // [rsp+5B0h] [rbp-14F8h] BYREF
  __int16 v477; // [rsp+5B8h] [rbp-14F0h]
  int v478; // [rsp+5C0h] [rbp-14E8h]
  int v479; // [rsp+5C4h] [rbp-14E4h]
  __int16 v480; // [rsp+5C8h] [rbp-14E0h]
  LSN v481; // [rsp+5D0h] [rbp-14D8h] BYREF
  __int16 v482; // [rsp+5D8h] [rbp-14D0h]
  __int64 v483; // [rsp+5E0h] [rbp-14C8h] BYREF
  __int16 v484; // [rsp+5E8h] [rbp-14C0h]
  int v485; // [rsp+5F0h] [rbp-14B8h]
  int v486; // [rsp+5F4h] [rbp-14B4h]
  __int16 v487; // [rsp+5F8h] [rbp-14B0h]
  int v488; // [rsp+600h] [rbp-14A8h]
  int v489; // [rsp+604h] [rbp-14A4h]
  DWORD v490[14]; // [rsp+608h] [rbp-14A0h] BYREF
  int v491; // [rsp+640h] [rbp-1468h]
  int v492; // [rsp+644h] [rbp-1464h]
  BOOL v493; // [rsp+648h] [rbp-1460h]
  int v494; // [rsp+64Ch] [rbp-145Ch]
  int v495; // [rsp+650h] [rbp-1458h]
  int v496; // [rsp+654h] [rbp-1454h]
  BOOL v497; // [rsp+658h] [rbp-1450h]
  int v498; // [rsp+65Ch] [rbp-144Ch]
  int v499; // [rsp+660h] [rbp-1448h]
  BOOL v500; // [rsp+664h] [rbp-1444h]
  int v501; // [rsp+668h] [rbp-1440h]
  int v502; // [rsp+66Ch] [rbp-143Ch]
  int Lock; // [rsp+670h] [rbp-1438h]
  int v504; // [rsp+678h] [rbp-1430h]
  int v505; // [rsp+680h] [rbp-1428h]
  BOOL v506; // [rsp+684h] [rbp-1424h]
  unsigned int v507; // [rsp+688h] [rbp-1420h]
  unsigned int v508; // [rsp+68Ch] [rbp-141Ch]
  int v509; // [rsp+690h] [rbp-1418h]
  int v510; // [rsp+694h] [rbp-1414h]
  int v511; // [rsp+698h] [rbp-1410h]
  DWORD flOldProtect[4]; // [rsp+69Ch] [rbp-140Ch] BYREF
  DWORD v513[11]; // [rsp+6ACh] [rbp-13FCh] BYREF
  DWORD v514[4]; // [rsp+6D8h] [rbp-13D0h] BYREF
  DWORD v515[14]; // [rsp+6E8h] [rbp-13C0h] BYREF
  LsMgr *v516; // [rsp+720h] [rbp-1388h]
  struct LsMgr *v517; // [rsp+728h] [rbp-1380h]
  LARGE_INTEGER PerformanceCount; // [rsp+730h] [rbp-1378h] BYREF
  DirtyPageMgr *v519; // [rsp+738h] [rbp-1370h]
  __int64 v520; // [rsp+740h] [rbp-1368h]
  LARGE_INTEGER v521; // [rsp+748h] [rbp-1360h] BYREF
  DirtyPageMgr *v522; // [rsp+750h] [rbp-1358h]
  LARGE_INTEGER v523; // [rsp+758h] [rbp-1350h] BYREF
  DirtyPageMgr *v524; // [rsp+760h] [rbp-1348h]
  __int64 v525; // [rsp+768h] [rbp-1340h]
  __int64 v526; // [rsp+770h] [rbp-1338h]
  __int64 v527; // [rsp+778h] [rbp-1330h]
  LARGE_INTEGER v528; // [rsp+780h] [rbp-1328h] BYREF
  DirtyPageMgr *v529; // [rsp+788h] [rbp-1320h]
  __int64 v530; // [rsp+790h] [rbp-1318h] BYREF
  struct CSessionTraceFlags *v531; // [rsp+798h] [rbp-1310h]
  __int64 v532; // [rsp+7A0h] [rbp-1308h]
  char *v533; // [rsp+7A8h] [rbp-1300h]
  int *v534; // [rsp+7B0h] [rbp-12F8h]
  LONG *p_HighPart; // [rsp+7B8h] [rbp-12F0h]
  BOOL v536; // [rsp+7C0h] [rbp-12E8h]
  __int64 v537; // [rsp+7C8h] [rbp-12E0h]
  LARGE_INTEGER v538; // [rsp+7D0h] [rbp-12D8h] BYREF
  DirtyPageMgr *v539; // [rsp+7D8h] [rbp-12D0h]
  LARGE_INTEGER v540; // [rsp+7E0h] [rbp-12C8h] BYREF
  DirtyPageMgr *v541; // [rsp+7E8h] [rbp-12C0h]
  __int64 v542; // [rsp+7F0h] [rbp-12B8h]
  LARGE_INTEGER v543; // [rsp+7F8h] [rbp-12B0h] BYREF
  DirtyPageMgr *v544; // [rsp+800h] [rbp-12A8h]
  LARGE_INTEGER v545; // [rsp+808h] [rbp-12A0h] BYREF
  DirtyPageMgr *v546; // [rsp+810h] [rbp-1298h]
  __int64 v547; // [rsp+818h] [rbp-1290h]
  struct CSessionTraceFlags *v548; // [rsp+820h] [rbp-1288h]
  __int64 v549; // [rsp+828h] [rbp-1280h]
  char *v550; // [rsp+830h] [rbp-1278h]
  int *v551; // [rsp+838h] [rbp-1270h]
  LONG *v552; // [rsp+840h] [rbp-1268h]
  __int64 v553; // [rsp+848h] [rbp-1260h]
  LARGE_INTEGER v554; // [rsp+850h] [rbp-1258h] BYREF
  DirtyPageMgr *v555; // [rsp+858h] [rbp-1250h]
  LARGE_INTEGER v556; // [rsp+860h] [rbp-1248h] BYREF
  DirtyPageMgr *v557; // [rsp+868h] [rbp-1240h]
  _QWORD *v558; // [rsp+870h] [rbp-1238h]
  int v559; // [rsp+880h] [rbp-1228h]
  int v560; // [rsp+884h] [rbp-1224h]
  BOOL v561; // [rsp+888h] [rbp-1220h]
  char v562[4]; // [rsp+88Ch] [rbp-121Ch] BYREF
  int v563; // [rsp+890h] [rbp-1218h]
  int v564; // [rsp+894h] [rbp-1214h]
  int v565; // [rsp+898h] [rbp-1210h]
  DWORD v566[4]; // [rsp+89Ch] [rbp-120Ch] BYREF
  DWORD v567[11]; // [rsp+8ACh] [rbp-11FCh] BYREF
  DWORD v568; // [rsp+8D8h] [rbp-11D0h] BYREF
  __int64 v569; // [rsp+8DCh] [rbp-11CCh]
  __int16 v570; // [rsp+8E4h] [rbp-11C4h]
  __int16 v571; // [rsp+8E6h] [rbp-11C2h]
  __int64 v572; // [rsp+8E8h] [rbp-11C0h]
  __int16 v573; // [rsp+8F0h] [rbp-11B8h]
  __int16 v574; // [rsp+8F2h] [rbp-11B6h]
  signed __int32 v575; // [rsp+8F4h] [rbp-11B4h]
  signed __int32 v576; // [rsp+8F8h] [rbp-11B0h]
  unsigned __int64 v577; // [rsp+900h] [rbp-11A8h] BYREF
  int v578; // [rsp+908h] [rbp-11A0h]
  __int64 v579; // [rsp+910h] [rbp-1198h]
  unsigned __int64 v580; // [rsp+918h] [rbp-1190h] BYREF
  int v581; // [rsp+920h] [rbp-1188h]
  __int64 v582; // [rsp+928h] [rbp-1180h]
  signed __int64 v583; // [rsp+930h] [rbp-1178h]
  _QWORD *v584; // [rsp+938h] [rbp-1170h]
  __int64 v585; // [rsp+940h] [rbp-1168h]
  DirtyPageMgr **v586; // [rsp+948h] [rbp-1160h]
  DirtyPageMgr *v587; // [rsp+950h] [rbp-1158h]
  DirtyPageMgr **v588; // [rsp+958h] [rbp-1150h]
  DirtyPageMgr **v589; // [rsp+960h] [rbp-1148h]
  DirtyPageMgr **v590; // [rsp+968h] [rbp-1140h]
  __int64 v591; // [rsp+970h] [rbp-1138h]
  __int64 v592; // [rsp+978h] [rbp-1130h]
  _QWORD *v593; // [rsp+980h] [rbp-1128h]
  _QWORD *v594; // [rsp+988h] [rbp-1120h]
  _QWORD *v595; // [rsp+990h] [rbp-1118h]
  __int64 v596; // [rsp+998h] [rbp-1110h]
  __int64 v597; // [rsp+9A0h] [rbp-1108h]
  __int64 v598; // [rsp+9A8h] [rbp-1100h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+9B0h] [rbp-10F8h]
  __int64 v600; // [rsp+9B8h] [rbp-10F0h]
  __int64 v601; // [rsp+9C0h] [rbp-10E8h]
  int *v602; // [rsp+9C8h] [rbp-10E0h]
  _DWORD *v603; // [rsp+9D0h] [rbp-10D8h]
  __int64 v604; // [rsp+9D8h] [rbp-10D0h]
  __int64 v605; // [rsp+9E0h] [rbp-10C8h]
  DirtyPageMgr **v606; // [rsp+9E8h] [rbp-10C0h]
  unsigned __int64 *v607; // [rsp+9F0h] [rbp-10B8h]
  DirtyPageMgr **v608; // [rsp+9F8h] [rbp-10B0h]
  char *v609; // [rsp+A00h] [rbp-10A8h]
  _QWORD *v610; // [rsp+A08h] [rbp-10A0h]
  _QWORD *v611; // [rsp+A10h] [rbp-1098h]
  int *v612; // [rsp+A18h] [rbp-1090h]
  char *v613; // [rsp+A20h] [rbp-1088h]
  char *v614; // [rsp+A28h] [rbp-1080h]
  __int64 v615; // [rsp+A30h] [rbp-1078h]
  __int64 v616; // [rsp+A38h] [rbp-1070h]
  __int64 v617; // [rsp+A40h] [rbp-1068h]
  _QWORD *v618; // [rsp+A48h] [rbp-1060h]
  _QWORD *v619; // [rsp+A50h] [rbp-1058h]
  _QWORD *v620; // [rsp+A58h] [rbp-1050h]
  __int64 v621; // [rsp+A60h] [rbp-1048h]
  __int64 v622; // [rsp+A68h] [rbp-1040h]
  struct CSessionTraceFlags *v623; // [rsp+A70h] [rbp-1038h]
  _QWORD *v624; // [rsp+A78h] [rbp-1030h]
  __int64 v625; // [rsp+A80h] [rbp-1028h]
  __int64 v626; // [rsp+A88h] [rbp-1020h]
  __int64 v627; // [rsp+A90h] [rbp-1018h]
  __int64 v628; // [rsp+A98h] [rbp-1010h]
  char *v629; // [rsp+AA0h] [rbp-1008h]
  char *v630; // [rsp+AA8h] [rbp-1000h]
  char *v631; // [rsp+AB0h] [rbp-FF8h]
  __int64 v632; // [rsp+AB8h] [rbp-FF0h]
  __int64 v633; // [rsp+AC0h] [rbp-FE8h]
  __int64 v634; // [rsp+AC8h] [rbp-FE0h]
  char *v635; // [rsp+AD0h] [rbp-FD8h]
  char *v636; // [rsp+AD8h] [rbp-FD0h]
  char *v637; // [rsp+AE0h] [rbp-FC8h]
  __int64 v638; // [rsp+AE8h] [rbp-FC0h]
  __int64 v639; // [rsp+AF0h] [rbp-FB8h]
  __int64 v640; // [rsp+AF8h] [rbp-FB0h]
  __int64 v641; // [rsp+B00h] [rbp-FA8h]
  _DWORD *v642; // [rsp+B08h] [rbp-FA0h]
  _QWORD *v643; // [rsp+B10h] [rbp-F98h]
  __int64 v644; // [rsp+B18h] [rbp-F90h]
  __int64 v645; // [rsp+B20h] [rbp-F88h]
  int *v646; // [rsp+B28h] [rbp-F80h]
  __int64 v647; // [rsp+B30h] [rbp-F78h]
  __int64 *v648; // [rsp+B38h] [rbp-F70h]
  _DWORD *v649; // [rsp+B40h] [rbp-F68h]
  _QWORD *v650; // [rsp+B48h] [rbp-F60h]
  __int64 v651; // [rsp+B50h] [rbp-F58h]
  __int64 v652; // [rsp+B58h] [rbp-F50h]
  __int64 v653; // [rsp+B60h] [rbp-F48h]
  __int64 v654; // [rsp+B68h] [rbp-F40h]
  __int64 v655; // [rsp+B70h] [rbp-F38h]
  _DWORD *v656; // [rsp+B78h] [rbp-F30h]
  __int64 v657; // [rsp+B80h] [rbp-F28h]
  int *v658; // [rsp+B88h] [rbp-F20h]
  __int64 v659; // [rsp+B90h] [rbp-F18h]
  __int64 v660; // [rsp+B98h] [rbp-F10h]
  _WORD *v661; // [rsp+BA0h] [rbp-F08h]
  int **v662; // [rsp+BA8h] [rbp-F00h]
  GUID **v663; // [rsp+BB0h] [rbp-EF8h]
  GUID **v664; // [rsp+BB8h] [rbp-EF0h]
  wchar_t **v665; // [rsp+BC0h] [rbp-EE8h]
  wchar_t **v666; // [rsp+BC8h] [rbp-EE0h]
  __int64 *v667; // [rsp+BD0h] [rbp-ED8h]
  __int64 v668; // [rsp+BD8h] [rbp-ED0h]
  GUID **v669; // [rsp+BE0h] [rbp-EC8h]
  GUID **v670; // [rsp+BE8h] [rbp-EC0h]
  wchar_t *v671; // [rsp+BF0h] [rbp-EB8h]
  wchar_t **v672; // [rsp+BF8h] [rbp-EB0h]
  wchar_t *v673; // [rsp+C00h] [rbp-EA8h]
  wchar_t **v674; // [rsp+C08h] [rbp-EA0h]
  __int64 v675; // [rsp+C10h] [rbp-E98h]
  _DWORD **v676; // [rsp+C18h] [rbp-E90h]
  _QWORD *v677; // [rsp+C20h] [rbp-E88h]
  __int64 v678; // [rsp+C28h] [rbp-E80h]
  __int64 v679; // [rsp+C30h] [rbp-E78h]
  __int64 v680; // [rsp+C38h] [rbp-E70h]
  __int64 v681; // [rsp+C40h] [rbp-E68h]
  __int64 v682; // [rsp+C48h] [rbp-E60h]
  __int64 *v683; // [rsp+C50h] [rbp-E58h]
  __int64 v684; // [rsp+C58h] [rbp-E50h]
  int *v685; // [rsp+C60h] [rbp-E48h]
  __int64 v686; // [rsp+C68h] [rbp-E40h]
  __int64 *v687; // [rsp+C70h] [rbp-E38h]
  char *v688; // [rsp+C78h] [rbp-E30h]
  char *v689; // [rsp+C80h] [rbp-E28h]
  char *v690; // [rsp+C88h] [rbp-E20h]
  __int64 v691; // [rsp+C90h] [rbp-E18h]
  __int64 v692; // [rsp+C98h] [rbp-E10h]
  __int64 v693; // [rsp+CA0h] [rbp-E08h]
  __int64 *v694; // [rsp+CA8h] [rbp-E00h]
  __int64 *v695; // [rsp+CB0h] [rbp-DF8h]
  __int64 v696; // [rsp+CB8h] [rbp-DF0h]
  char *v697; // [rsp+CC0h] [rbp-DE8h]
  char *v698; // [rsp+CC8h] [rbp-DE0h]
  char *v699; // [rsp+CD0h] [rbp-DD8h]
  __int64 v700; // [rsp+CD8h] [rbp-DD0h]
  __int64 v701; // [rsp+CE0h] [rbp-DC8h]
  __int64 v702; // [rsp+CE8h] [rbp-DC0h]
  char *v703; // [rsp+CF0h] [rbp-DB8h]
  __int64 v704; // [rsp+CF8h] [rbp-DB0h]
  __int64 v705; // [rsp+D00h] [rbp-DA8h]
  char *v706; // [rsp+D08h] [rbp-DA0h]
  signed __int64 v707; // [rsp+D10h] [rbp-D98h]
  signed __int64 v708; // [rsp+D18h] [rbp-D90h]
  _QWORD *v709; // [rsp+D20h] [rbp-D88h]
  __int64 v710; // [rsp+D28h] [rbp-D80h]
  DirtyPageMgr **v711; // [rsp+D30h] [rbp-D78h]
  DirtyPageMgr *v712; // [rsp+D38h] [rbp-D70h]
  DirtyPageMgr **v713; // [rsp+D40h] [rbp-D68h]
  DirtyPageMgr **v714; // [rsp+D48h] [rbp-D60h]
  DirtyPageMgr **v715; // [rsp+D50h] [rbp-D58h]
  __int64 v716; // [rsp+D58h] [rbp-D50h]
  __int64 v717; // [rsp+D60h] [rbp-D48h]
  char *v718; // [rsp+D68h] [rbp-D40h]
  char *v719; // [rsp+D70h] [rbp-D38h]
  char *v720; // [rsp+D78h] [rbp-D30h]
  char *v721; // [rsp+D80h] [rbp-D28h]
  volatile signed __int64 *v722; // [rsp+D88h] [rbp-D20h]
  __int64 v723; // [rsp+D90h] [rbp-D18h]
  __int64 v724; // [rsp+D98h] [rbp-D10h]
  volatile signed __int64 *v725; // [rsp+DA0h] [rbp-D08h]
  signed __int64 v726; // [rsp+DA8h] [rbp-D00h]
  signed __int64 v727; // [rsp+DB0h] [rbp-CF8h]
  _QWORD *v728; // [rsp+DB8h] [rbp-CF0h]
  __int64 v729; // [rsp+DC0h] [rbp-CE8h]
  DirtyPageMgr **v730; // [rsp+DC8h] [rbp-CE0h]
  DirtyPageMgr *v731; // [rsp+DD0h] [rbp-CD8h]
  DirtyPageMgr **v732; // [rsp+DD8h] [rbp-CD0h]
  DirtyPageMgr **v733; // [rsp+DE0h] [rbp-CC8h]
  DirtyPageMgr **v734; // [rsp+DE8h] [rbp-CC0h]
  __int64 v735; // [rsp+DF0h] [rbp-CB8h]
  __int64 v736; // [rsp+DF8h] [rbp-CB0h]
  _QWORD *v737; // [rsp+E00h] [rbp-CA8h]
  _QWORD *v738; // [rsp+E08h] [rbp-CA0h]
  _QWORD *v739; // [rsp+E10h] [rbp-C98h]
  __int64 v740; // [rsp+E18h] [rbp-C90h]
  char *v741; // [rsp+E20h] [rbp-C88h]
  __int64 v742; // [rsp+E28h] [rbp-C80h]
  __int64 v743; // [rsp+E30h] [rbp-C78h]
  _QWORD *v744; // [rsp+E38h] [rbp-C70h]
  _QWORD *v745; // [rsp+E40h] [rbp-C68h]
  _QWORD *v746; // [rsp+E48h] [rbp-C60h]
  __int64 v747; // [rsp+E50h] [rbp-C58h]
  __int64 v748; // [rsp+E58h] [rbp-C50h]
  struct CSessionTraceFlags *v749; // [rsp+E60h] [rbp-C48h]
  _QWORD *v750; // [rsp+E68h] [rbp-C40h]
  __int64 v751; // [rsp+E70h] [rbp-C38h]
  __int64 v752; // [rsp+E78h] [rbp-C30h]
  __int64 v753; // [rsp+E80h] [rbp-C28h]
  __int64 v754; // [rsp+E88h] [rbp-C20h]
  char *v755; // [rsp+E90h] [rbp-C18h]
  char *v756; // [rsp+E98h] [rbp-C10h]
  char *v757; // [rsp+EA0h] [rbp-C08h]
  __int64 v758; // [rsp+EA8h] [rbp-C00h]
  __int64 v759; // [rsp+EB0h] [rbp-BF8h]
  __int64 v760; // [rsp+EB8h] [rbp-BF0h]
  char *v761; // [rsp+EC0h] [rbp-BE8h]
  char *v762; // [rsp+EC8h] [rbp-BE0h]
  char *v763; // [rsp+ED0h] [rbp-BD8h]
  __int64 v764; // [rsp+ED8h] [rbp-BD0h]
  __int64 v765; // [rsp+EE0h] [rbp-BC8h]
  __int64 v766; // [rsp+EE8h] [rbp-BC0h]
  __int64 v767; // [rsp+EF0h] [rbp-BB8h]
  _DWORD *v768; // [rsp+EF8h] [rbp-BB0h]
  _QWORD *v769; // [rsp+F00h] [rbp-BA8h]
  __int64 v770; // [rsp+F08h] [rbp-BA0h]
  __int64 v771; // [rsp+F10h] [rbp-B98h]
  int *v772; // [rsp+F18h] [rbp-B90h]
  __int64 v773; // [rsp+F20h] [rbp-B88h]
  __int64 *v774; // [rsp+F28h] [rbp-B80h]
  _DWORD *v775; // [rsp+F30h] [rbp-B78h]
  _QWORD *v776; // [rsp+F38h] [rbp-B70h]
  __int64 v777; // [rsp+F40h] [rbp-B68h]
  __int64 v778; // [rsp+F48h] [rbp-B60h]
  __int64 v779; // [rsp+F50h] [rbp-B58h]
  __int64 v780; // [rsp+F58h] [rbp-B50h]
  __int64 v781; // [rsp+F60h] [rbp-B48h]
  _DWORD *v782; // [rsp+F68h] [rbp-B40h]
  __int64 v783; // [rsp+F70h] [rbp-B38h]
  int *v784; // [rsp+F78h] [rbp-B30h]
  __int64 v785; // [rsp+F80h] [rbp-B28h]
  __int64 v786; // [rsp+F88h] [rbp-B20h]
  _WORD *v787; // [rsp+F90h] [rbp-B18h]
  int **v788; // [rsp+F98h] [rbp-B10h]
  GUID **v789; // [rsp+FA0h] [rbp-B08h]
  GUID **v790; // [rsp+FA8h] [rbp-B00h]
  wchar_t **v791; // [rsp+FB0h] [rbp-AF8h]
  wchar_t **v792; // [rsp+FB8h] [rbp-AF0h]
  __int64 *v793; // [rsp+FC0h] [rbp-AE8h]
  __int64 v794; // [rsp+FC8h] [rbp-AE0h]
  GUID **v795; // [rsp+FD0h] [rbp-AD8h]
  GUID **v796; // [rsp+FD8h] [rbp-AD0h]
  wchar_t *v797; // [rsp+FE0h] [rbp-AC8h]
  wchar_t **v798; // [rsp+FE8h] [rbp-AC0h]
  wchar_t *v799; // [rsp+FF0h] [rbp-AB8h]
  wchar_t **v800; // [rsp+FF8h] [rbp-AB0h]
  __int64 v801; // [rsp+1000h] [rbp-AA8h]
  _DWORD **v802; // [rsp+1008h] [rbp-AA0h]
  _QWORD *v803; // [rsp+1010h] [rbp-A98h]
  __int64 v804; // [rsp+1018h] [rbp-A90h]
  __int64 v805; // [rsp+1020h] [rbp-A88h]
  __int64 v806; // [rsp+1028h] [rbp-A80h]
  __int64 v807; // [rsp+1030h] [rbp-A78h]
  __int64 v808; // [rsp+1038h] [rbp-A70h]
  __int64 *v809; // [rsp+1040h] [rbp-A68h]
  __int64 v810; // [rsp+1048h] [rbp-A60h]
  int *v811; // [rsp+1050h] [rbp-A58h]
  __int64 v812; // [rsp+1058h] [rbp-A50h]
  __int64 *v813; // [rsp+1060h] [rbp-A48h]
  char *v814; // [rsp+1068h] [rbp-A40h]
  char *v815; // [rsp+1070h] [rbp-A38h]
  char *v816; // [rsp+1078h] [rbp-A30h]
  __int64 v817; // [rsp+1080h] [rbp-A28h]
  __int64 v818; // [rsp+1088h] [rbp-A20h]
  __int64 v819; // [rsp+1090h] [rbp-A18h]
  __int64 *v820; // [rsp+1098h] [rbp-A10h]
  __int64 *v821; // [rsp+10A0h] [rbp-A08h]
  __int64 v822; // [rsp+10A8h] [rbp-A00h]
  _QWORD *v823; // [rsp+10B0h] [rbp-9F8h]
  __int64 v824; // [rsp+10B8h] [rbp-9F0h]
  char *v825; // [rsp+10C0h] [rbp-9E8h]
  char *v826; // [rsp+10C8h] [rbp-9E0h]
  char *v827; // [rsp+10D0h] [rbp-9D8h]
  __int64 v828; // [rsp+10D8h] [rbp-9D0h]
  __int64 v829; // [rsp+10E0h] [rbp-9C8h]
  __int64 v830; // [rsp+10E8h] [rbp-9C0h]
  char *v831; // [rsp+10F0h] [rbp-9B8h]
  volatile signed __int64 *v832; // [rsp+10F8h] [rbp-9B0h]
  __int64 v833; // [rsp+1100h] [rbp-9A8h]
  __int64 v834; // [rsp+1108h] [rbp-9A0h]
  volatile signed __int64 *v835; // [rsp+1110h] [rbp-998h]
  signed __int64 v836; // [rsp+1118h] [rbp-990h]
  signed __int64 v837; // [rsp+1120h] [rbp-988h]
  _QWORD *v838; // [rsp+1128h] [rbp-980h]
  __int64 v839; // [rsp+1130h] [rbp-978h]
  __int64 v840; // [rsp+1138h] [rbp-970h]
  DBMgr **v841; // [rsp+1140h] [rbp-968h]
  ReplicaState *v842; // [rsp+1148h] [rbp-960h]
  DirtyPageMgr **v843; // [rsp+1150h] [rbp-958h]
  ReplicaState **v844; // [rsp+1158h] [rbp-950h]
  DirtyPageMgr **v845; // [rsp+1160h] [rbp-948h]
  __int64 v846; // [rsp+1168h] [rbp-940h]
  __int64 v847; // [rsp+1170h] [rbp-938h]
  _QWORD *v848; // [rsp+1178h] [rbp-930h]
  _QWORD *v849; // [rsp+1180h] [rbp-928h]
  _QWORD *v850; // [rsp+1188h] [rbp-920h]
  __int64 v851; // [rsp+1190h] [rbp-918h]
  _QWORD *v852; // [rsp+1198h] [rbp-910h]
  char *v853; // [rsp+11A0h] [rbp-908h]
  char *v854; // [rsp+11A8h] [rbp-900h]
  struct IMemObj *v855; // [rsp+11B0h] [rbp-8F8h]
  AsynchronousDiskAction *v856; // [rsp+11B8h] [rbp-8F0h]
  AsynchronousDiskAction *v857; // [rsp+11C0h] [rbp-8E8h]
  AsynchronousDiskAction *v858; // [rsp+11C8h] [rbp-8E0h]
  char *v859; // [rsp+11D0h] [rbp-8D8h]
  __int64 v860; // [rsp+11D8h] [rbp-8D0h]
  DBMirroring *v861; // [rsp+11E0h] [rbp-8C8h]
  DBMirroring *v862; // [rsp+11E8h] [rbp-8C0h]
  LsMgr *v863; // [rsp+11F0h] [rbp-8B8h]
  DBMirroring *v864; // [rsp+11F8h] [rbp-8B0h]
  struct LsMgr *v865; // [rsp+1200h] [rbp-8A8h]
  struct LsMgr *v866; // [rsp+1208h] [rbp-8A0h]
  char *v867; // [rsp+1210h] [rbp-898h]
  DirtyPageMgr **v868; // [rsp+1218h] [rbp-890h]
  unsigned __int64 *v869; // [rsp+1220h] [rbp-888h]
  DirtyPageMgr **v870; // [rsp+1228h] [rbp-880h]
  char *v871; // [rsp+1230h] [rbp-878h]
  _QWORD *v872; // [rsp+1238h] [rbp-870h]
  _QWORD *v873; // [rsp+1240h] [rbp-868h]
  volatile signed __int64 *v874; // [rsp+1248h] [rbp-860h]
  __int64 v875; // [rsp+1250h] [rbp-858h]
  _QWORD v876[4]; // [rsp+1258h] [rbp-850h] BYREF
  signed __int64 v877; // [rsp+1278h] [rbp-830h]
  char v878; // [rsp+1280h] [rbp-828h] BYREF
  int v879; // [rsp+1284h] [rbp-824h]
  int v880; // [rsp+1288h] [rbp-820h]
  char v881; // [rsp+1298h] [rbp-810h] BYREF
  int v882; // [rsp+129Ch] [rbp-80Ch]
  int v883; // [rsp+12A0h] [rbp-808h]
  char v884[8]; // [rsp+12B0h] [rbp-7F8h] BYREF
  _WORD v885[4]; // [rsp+12B8h] [rbp-7F0h] BYREF
  int v886; // [rsp+12C0h] [rbp-7E8h]
  int **v887; // [rsp+12C8h] [rbp-7E0h]
  char *v888; // [rsp+12D0h] [rbp-7D8h]
  __int64 v889; // [rsp+12D8h] [rbp-7D0h]
  int *v890; // [rsp+12E0h] [rbp-7C8h] BYREF
  int v891; // [rsp+12E8h] [rbp-7C0h]
  __int16 v892; // [rsp+12ECh] [rbp-7BCh]
  __int16 v893; // [rsp+12EEh] [rbp-7BAh]
  GUID *v894; // [rsp+12F0h] [rbp-7B8h] BYREF
  int v895; // [rsp+12F8h] [rbp-7B0h]
  __int16 v896; // [rsp+12FCh] [rbp-7ACh]
  __int16 v897; // [rsp+12FEh] [rbp-7AAh]
  GUID *v898; // [rsp+1300h] [rbp-7A8h] BYREF
  int v899; // [rsp+1308h] [rbp-7A0h]
  __int16 v900; // [rsp+130Ch] [rbp-79Ch]
  __int16 v901; // [rsp+130Eh] [rbp-79Ah]
  wchar_t *v902; // [rsp+1310h] [rbp-798h] BYREF
  int v903; // [rsp+1318h] [rbp-790h]
  __int16 v904; // [rsp+131Ch] [rbp-78Ch]
  __int16 v905; // [rsp+131Eh] [rbp-78Ah]
  wchar_t *v906; // [rsp+1320h] [rbp-788h] BYREF
  int v907; // [rsp+1328h] [rbp-780h]
  __int16 v908; // [rsp+132Ch] [rbp-77Ch]
  __int16 v909; // [rsp+132Eh] [rbp-77Ah]
  __int64 v910; // [rsp+1330h] [rbp-778h] BYREF
  int v911; // [rsp+1338h] [rbp-770h]
  __int16 v912; // [rsp+133Ch] [rbp-76Ch]
  __int16 v913; // [rsp+133Eh] [rbp-76Ah]
  char v914; // [rsp+1340h] [rbp-768h] BYREF
  int v915; // [rsp+1500h] [rbp-5A8h]
  int v916; // [rsp+1504h] [rbp-5A4h]
  __int64 v917; // [rsp+1508h] [rbp-5A0h]
  int v918; // [rsp+1510h] [rbp-598h] BYREF
  __int16 v919; // [rsp+1514h] [rbp-594h]
  int v920; // [rsp+1516h] [rbp-592h]
  char v921; // [rsp+151Ah] [rbp-58Eh]
  char v922; // [rsp+151Bh] [rbp-58Dh]
  char v923[8]; // [rsp+1550h] [rbp-558h] BYREF
  _WORD v924[4]; // [rsp+1558h] [rbp-550h] BYREF
  int v925; // [rsp+1560h] [rbp-548h]
  int **v926; // [rsp+1568h] [rbp-540h]
  char *v927; // [rsp+1570h] [rbp-538h]
  __int64 v928; // [rsp+1578h] [rbp-530h]
  int *v929; // [rsp+1580h] [rbp-528h] BYREF
  int v930; // [rsp+1588h] [rbp-520h]
  __int16 v931; // [rsp+158Ch] [rbp-51Ch]
  __int16 v932; // [rsp+158Eh] [rbp-51Ah]
  GUID *v933; // [rsp+1590h] [rbp-518h] BYREF
  int v934; // [rsp+1598h] [rbp-510h]
  __int16 v935; // [rsp+159Ch] [rbp-50Ch]
  __int16 v936; // [rsp+159Eh] [rbp-50Ah]
  GUID *v937; // [rsp+15A0h] [rbp-508h] BYREF
  int v938; // [rsp+15A8h] [rbp-500h]
  __int16 v939; // [rsp+15ACh] [rbp-4FCh]
  __int16 v940; // [rsp+15AEh] [rbp-4FAh]
  wchar_t *v941; // [rsp+15B0h] [rbp-4F8h] BYREF
  int v942; // [rsp+15B8h] [rbp-4F0h]
  __int16 v943; // [rsp+15BCh] [rbp-4ECh]
  __int16 v944; // [rsp+15BEh] [rbp-4EAh]
  wchar_t *v945; // [rsp+15C0h] [rbp-4E8h] BYREF
  int v946; // [rsp+15C8h] [rbp-4E0h]
  __int16 v947; // [rsp+15CCh] [rbp-4DCh]
  __int16 v948; // [rsp+15CEh] [rbp-4DAh]
  __int64 v949; // [rsp+15D0h] [rbp-4D8h] BYREF
  int v950; // [rsp+15D8h] [rbp-4D0h]
  __int16 v951; // [rsp+15DCh] [rbp-4CCh]
  __int16 v952; // [rsp+15DEh] [rbp-4CAh]
  char v953; // [rsp+15E0h] [rbp-4C8h] BYREF
  int v954; // [rsp+17A0h] [rbp-308h]
  int v955; // [rsp+17A4h] [rbp-304h]
  __int64 v956; // [rsp+17A8h] [rbp-300h]
  int v957; // [rsp+17B0h] [rbp-2F8h] BYREF
  __int16 v958; // [rsp+17B4h] [rbp-2F4h]
  int v959; // [rsp+17B6h] [rbp-2F2h]
  char v960; // [rsp+17BAh] [rbp-2EEh]
  char v961; // [rsp+17BBh] [rbp-2EDh]
  _BYTE v962[24]; // [rsp+17F0h] [rbp-2B8h] BYREF
  _BYTE v963[40]; // [rsp+1808h] [rbp-2A0h] BYREF
  _BYTE v964[320]; // [rsp+1830h] [rbp-278h] BYREF
  int v965; // [rsp+1970h] [rbp-138h] BYREF
  int v966; // [rsp+1974h] [rbp-134h]
  __int16 v967; // [rsp+1978h] [rbp-130h]
  _DWORD v968[2]; // [rsp+1980h] [rbp-128h] BYREF
  __int16 v969; // [rsp+1988h] [rbp-120h]
  int v970; // [rsp+1990h] [rbp-118h] BYREF
  GUID v971; // [rsp+1994h] [rbp-114h]
  wchar_t v972[24]; // [rsp+19A8h] [rbp-100h] BYREF
  wchar_t v973[24]; // [rsp+19D8h] [rbp-D0h] BYREF
  wchar_t v974[24]; // [rsp+1A08h] [rbp-A0h] BYREF
  wchar_t v975[24]; // [rsp+1A38h] [rbp-70h] BYREF

  v851 = -2;
  v336 = a3;
  v339 = (ReplicaState *)a2;
  v384 = a1;
  v261 = a7;
  v558 = a2;
  v281 = 0;
  v255 = 0;
  v256 = 0;
  v257 = 0;
  v970 = 0;
  v971 = x_AG_DB_IdBad;
  v442 = 0;
  v443 = 0;
  v455 = 0;
  v456 = 0;
  v333 = 0;
  v334 = 0;
  v360 = 0;
  v361 = 0;
  v11 = (struct DatabaseStartupInfo *)(a2 + 50);
  v338 = (__int64)(a2 + 7);
  utgettime((struct SQLDATEBASE *)&v530, 0, 0);
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v963, 0, 0, 0, hdl_prntbackout, 0);
    v12 = a2 + 115;
    v852 = a2 + 115;
    AsynchronousDiskPool::AsynchronousDiskPool((AsynchronousDiskPool *)v964, *((struct IMemObj **)v261 + 86));
    AsynchronousDiskPool::Init((AsynchronousDiskPool *)v964);
    v286 = (unsigned __int8)byte_10317ACC5 >> 2;
    if ( (byte_10317ACC5 & 4) != 0 )
      LogSystemMetadataNotSentToClient(L"DBID: [%d] creating sparse files", a3);
    v853 = (char *)(a2 + 7);
    v13 = (char *)a2[8];
    if ( v13 == v853 )
      v13 = 0;
    v854 = v13;
    v14 = v338;
    while ( 1 )
    {
      v280 = v13;
      if ( !v13 )
        break;
      if ( !*((_DWORD *)v13 + 228) )
      {
        v490[10] = 8752;
        v855 = qword_103172088;
        v15 = (AsynchronousDiskAction *)operator new(
                                          0x60u,
                                          qword_103172088,
                                          "sql\\ntdbms\\storeng\\dfs\\manager\\dbmgr.cpp",
                                          8752,
                                          5u);
        v856 = v15;
        if ( v15 )
          v16 = AsynchronousDiskAction::AsynchronousDiskAction(v15, (struct AsynchronousDiskPool *)v964);
        else
          v16 = 0;
        v857 = v16;
        v858 = v16;
        AsynchronousDiskAction::DeferCreating(v16, (struct FileDescription *)v13, a8);
        v14 = v338;
      }
      v13 = (char *)*((_QWORD *)v13 + 1);
      if ( v13 == (char *)v14 )
        v13 = 0;
      v859 = v13;
    }
    if ( !(unsigned int)AsynchronousDiskPool::WaitUntilDone((AsynchronousDiskPool *)v964) )
      ex_raise(18, 2, 25, 5);
    v316 = 0;
    for ( i = 0; !i; i = 1 )
    {
      v18 = *((_QWORD *)v261 + 578);
      v860 = v18;
      if ( v18 )
        BackupManager::BeginSyncWithBulkOps(*(BackupManager **)(v18 + 1960));
      v316 = 1;
    }
    v19 = v339;
    *((_BYTE *)v339 + 881) = 1;
    if ( *((_DWORD *)v261 + 412) == 770 && *((_QWORD *)v261 + 92) )
    {
      DBStartupTimer::DBStartupTimer(&v577, 2, v11);
      DBMirroring::UpdateTruncationLSNs(*((DBMirroring **)v261 + 92));
      v861 = (DBMirroring *)*((_QWORD *)v261 + 92);
      v20 = v861;
      ReplicaState::EnableDbmLogTruncation(v19);
      *((_QWORD *)v19 + 129) = v20;
      if ( v20 )
      {
        v862 = v20;
        LsMgrWithRef = DBMirroring::GetLsMgrWithRef(v20, 0);
        v22 = LsMgrWithRef;
        v863 = LsMgrWithRef;
        v516 = LsMgrWithRef;
        if ( LsMgrWithRef )
          LsMgr::DisableLogTruncation(LsMgrWithRef, (ReplicaState *)((char *)v19 + 1040));
        if ( v22 )
          (*(void (__fastcall **)(LsMgr *))(*(_QWORD *)v22 + 16LL))(v22);
      }
      v864 = (DBMirroring *)*((_QWORD *)v261 + 92);
      v23 = DBMirroring::GetLsMgrWithRef(v864, 0);
      v24 = v23;
      v865 = v23;
      v517 = v23;
      if ( v23 )
      {
        v866 = v23;
        *v12 = (char *)v23 + 109400;
        *((_DWORD *)v12 + 3) = 4;
        v490[12] = 4;
        v867 = (char *)v23 + 109400;
        v491 = LatchBase::AcquireInternal((__int64)v23 + 109400, 4, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0);
        *((_DWORD *)v12 + 2) = v491;
      }
      if ( v24 )
        (*(void (__fastcall **)(struct LsMgr *))(*(_QWORD *)v24 + 16LL))(v24);
      v868 = &v415;
      v492 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v493 = QueryPerformanceCounter(&PerformanceCount);
        QuadPart = (DirtyPageMgr *)PerformanceCount.QuadPart;
      }
      else
      {
        QuadPart = MEMORY[0x7FFE0008];
        v519 = MEMORY[0x7FFE0008];
      }
      v415 = QuadPart;
      v869 = &v577;
      v870 = &v415;
      if ( (unsigned __int64)QuadPart < v577 )
      {
        v26 = 0;
        v344 = 0;
      }
      else
      {
        v26 = (char *)QuadPart - v577;
        v344 = v26;
      }
      v871 = v26;
      v872 = (_QWORD *)(v579 + 8 * (v578 + 13LL));
      v873 = v872;
      *v872 += v26;
    }
    v27 = v261;
    v28 = *((_QWORD *)v261 + 578);
    if ( !*(_BYTE *)(v28 + 8272) )
    {
LABEL_71:
      ReplicaState::DisableLogTruncation(v19, &v442, 7);
      ReplicaState::DisableSLogTruncationAndCleanup(v19, &v455, 7);
      v39 = *((_QWORD *)v27 + 578);
      v596 = v39;
      if ( *(_WORD *)(v39 + 1662) < 0x27Bu )
      {
        v527 = 0;
      }
      else
      {
        v527 = *(_QWORD *)(v39 + 7360);
        if ( v527 )
        {
          v40 = *(_QWORD *)(*((_QWORD *)v19 + 2) + 4624LL);
          v597 = v40;
          if ( *(_WORD *)(v40 + 1662) < 0x27Bu )
            v41 = 0;
          else
            v41 = *(_QWORD *)(v40 + 7360);
          v598 = v41;
          v526 = v41 + 48;
          v461 = 0;
          v501 = 88;
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          v42 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v600 = v42;
          v43 = *(_QWORD *)(v42 + 256);
          v525 = v43;
          if ( !v43 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v43 = *(_QWORD *)(v42 + 256);
            v525 = v43;
          }
          v462 = v43;
          v601 = v43;
          v44 = (_DWORD *)(v43 + 616);
          v502 = *v44 & 1;
          v602 = &v461;
          v461 |= v502 ^ 1;
          v603 = v44;
          *v44 |= 1u;
          Lock = SOS_RWLock::GetLock(v526, 2, 0xFFFFFFFFLL, (char *)v19 + 952);
          *((_BYTE *)v19 + 992) = 1;
          v604 = v462;
          v504 = ~v461;
          v605 = v462 + 616;
          *(_DWORD *)(v462 + 616) &= ~v461;
        }
      }
      v45 = *((_DWORD *)v27 + 412);
      if ( (v45 & 2) == 0 && (unsigned int)RecoveryUnit::IsUpdateable(*((RecoveryUnit **)v27 + 578)) )
      {
        DBStartupTimer::DBStartupTimer(&v580, 33, v11);
        v288 = (unsigned __int8)byte_10317ACC5 >> 2;
        if ( (byte_10317ACC5 & 4) != 0 )
          LogSystemMetadataNotSentToClient(L"DBID: [%d] checkpointing", v336);
        CheckpointDB2(*((unsigned __int16 *)v27 + 20), 0, 1);
        CheckpointDB2(*((unsigned __int16 *)v27 + 20), 100, 1);
        v606 = &v420;
        v505 = Base_PublicGlobals::sm_invariantTscAvailable;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          v506 = QueryPerformanceCounter(&v528);
          v46 = (DirtyPageMgr *)v528.QuadPart;
        }
        else
        {
          v46 = MEMORY[0x7FFE0008];
          v529 = MEMORY[0x7FFE0008];
        }
        v420 = v46;
        v607 = &v580;
        v608 = &v420;
        if ( (unsigned __int64)v46 < v580 )
        {
          v47 = 0;
          v280 = 0;
        }
        else
        {
          v47 = (char *)v46 - v580;
          v280 = v47;
        }
        v609 = v47;
        v610 = (_QWORD *)(v582 + 8 * (v581 + 13LL));
        v611 = v610;
        *v610 += v47;
        v45 = *((_DWORD *)v27 + 412);
      }
      if ( (v45 & 2) != 0 && v45 != 770 )
        ex_raise(18, 23, 16, 5);
      v48 = *((_DWORD *)v27 + 158) & 0x7D3401C;
      v507 = v48;
      v49 = DBTABLE::Allocate(1);
      v281 = v49;
      *((_QWORD *)v19 + 3) = v49;
      v50 = v261;
      *((_QWORD *)v49 + 80) = v261;
      if ( a6 == 1 && a5 )
        *((_WORD *)v49 + 764) = *((_WORD *)v50 + 20);
      v612 = &v345;
      v345 = *((_DWORD *)v50 + 11);
      v51 = v48;
      v52 = v336;
      DBTABLE::Init(
        v281,
        v336,
        v11,
        v51,
        *((_DWORD *)v50 + 381),
        *((_DWORD *)v50 + 12),
        v530,
        v530,
        &v345,
        &v970,
        a5,
        a4);
      if ( a6 == 1 && a5 )
      {
        PerfmonManager::AddInstance((PerfmonManager *)&ResourceStr, 5u, (const wchar_t *)v281 + 468, v336);
        v53 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
        v289 = CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
        {
          PerfmonManager::SetInstanceCounterValue((PerfmonManager *)&ResourceStr, 5u, 0, 0, v336);
          v53 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
        }
        if ( *v53 )
          PerfmonManager::SetInstanceCounterValue((PerfmonManager *)&ResourceStr, 5u, 8u, 0, v336);
      }
      v54 = v261;
      v55 = v281;
      *((_DWORD *)v281 + 561) = *((_DWORD *)v261 + 561);
      *((_DWORD *)v55 + 562) = *((_DWORD *)v54 + 562);
      v56 = (char *)v338;
      FileMgr::StartupPreRecovery(*(FileMgr **)(*((_QWORD *)v55 + 578) + 1696LL), v11);
      if ( !a6 || (unsigned int)RecoveryUnit::GetHkDatabaseState(*((_QWORD *)v54 + 578)) == 1 )
        StreamFileMgr::StartupPreSQLRecovery(*(StreamFileMgr **)(*((_QWORD *)v55 + 578) + 1704LL), v11);
      DBMgr::SetDBTABLE(v384, v281);
      v57 = v339;
      *((_BYTE *)v339 + 884) = 1;
      v291 = (unsigned __int8)byte_10317ACC5 >> 2;
      if ( (byte_10317ACC5 & 4) != 0 )
        LogSystemMetadataNotSentToClient(L"DBID: [%d] associate replica files with primary", v52);
      v613 = v56;
      v58 = (char *)*((_QWORD *)v56 + 1);
      if ( v58 == v56 )
        v58 = 0;
      v614 = v58;
      v59 = v54;
      while ( 1 )
      {
        v280 = v58;
        if ( !v58 )
          break;
        v60 = v58;
        v441 = *((_WORD *)v58 + 18);
        v615 = *((_QWORD *)v59 + 578);
        FCB = FileMgr::GetFCB(*(_QWORD *)(v615 + 1696), v441, 0);
        v547 = FCB;
        v62 = *(_DWORD *)(FCB + 100);
        if ( v62 < 0 )
          goto LABEL_323;
        if ( (*(_BYTE *)(FCB + 124) & 1) == 0 )
          goto LABEL_323;
        if ( (v62 & 0x90000000) != 0 )
          goto LABEL_323;
        if ( *(_DWORD *)(FCB + 104) == 5 )
          goto LABEL_323;
        v444 = *((_WORD *)v60 + 18);
        v259 = 0;
        v260 = v444;
        v445 = *((_WORD *)v60 + 18);
        v63 = v281;
        v616 = *((_QWORD *)v281 + 578);
        v64 = FileMgr::GetFCB(*(_QWORD *)(v616 + 1696), v445, 0);
        v436 = v64;
        v65 = *(_DWORD *)(v64 + 100);
        if ( v65 < 0 || (*(_BYTE *)(v64 + 124) & 1) == 0 || (v65 & 0x90000000) != 0 || *(_DWORD *)(v64 + 104) == 5 )
          goto LABEL_323;
        FCB::SetReplica((FCB *)FCB, (struct FCB *)v64, *((struct RecoveryUnit **)v63 + 578));
        v617 = *((_QWORD *)v63 + 578);
        v508 = *(_DWORD *)(v617 + 1720);
        BPool::Deallocate(qword_10317B628, &v259, v508, 0, 3);
        SidePageTable::RemovePage(*(SidePageTable **)(v64 + 856), 0);
        v66 = (RecoveryUnit *)*((_QWORD *)v59 + 578);
        v278 = v66;
        v879 = 0;
        v880 = 0;
        v292 = CommonGlobalState::m_CollectingStatistics;
        if ( !CommonGlobalState::m_CollectingStatistics )
          goto LABEL_126;
        v293 = (unsigned __int8)byte_10317ABE6 >> 7;
        if ( byte_10317ABE6 < 0 )
          goto LABEL_126;
        v457 = 0;
        v509 = 88;
        v618 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v619 = (_QWORD *)(v618[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v620 = v619;
        v67 = *v619;
        v621 = v67;
        v622 = v67;
        if ( v67 && (v68 = **(struct CSessionTraceFlags ***)(v67 + 56), (v623 = v68) != 0) )
        {
          v531 = v68;
          v457 = CSessionTraceFlags::CheckSessionTraceInternal(v68, 0x337u);
          if ( v457 )
          {
            v66 = v278;
            goto LABEL_126;
          }
        }
        else
        {
          v531 = 0;
        }
        v510 = 88;
        v624 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v625 = v624[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v626 = v625;
        v71 = *(_QWORD *)(v625 + 8);
        v627 = v71;
        v628 = v71;
        v66 = v278;
        if ( v71 )
        {
          v69 = *(struct SEInternalTLS **)(v71 + 96);
          goto LABEL_127;
        }
LABEL_126:
        v69 = 0;
LABEL_127:
        SETLSFromTlsMaybeNull = v69;
        v70 = (_QWORD *)((char *)v66 + 1832);
        v532 = *((_QWORD *)v66 + 229);
        v469 = (unsigned int *)&v878;
        while ( 1 )
        {
          v346 = 0;
          if ( v255 )
          {
            v629 = (char *)v255 + 98;
            v317 = *((_WORD *)v255 + 49);
            if ( (v317 & 0x400) != 0 && (__int16)v257 >= 3 )
            {
              PageRef::UnfixLatchOnly((PageRef *)&v255);
LABEL_156:
              v66 = v278;
              goto LABEL_157;
            }
            v270 = (__int16)v257;
            v421 = v255;
            v630 = (char *)v255 + 98;
            v318 = *((_WORD *)v255 + 49);
            if ( (v318 & 8) != 0 )
            {
              if ( v270 == 3 )
              {
                v270 = 4;
                goto LABEL_139;
              }
              if ( v270 >= 2 )
              {
LABEL_139:
                v631 = (char *)v255 + 100;
                v458 = *((_DWORD *)v255 + 25);
                if ( (v458 & 8) != 0 )
                {
                  v72 = v255[18];
                  if ( v72 )
                  {
                    v632 = v255[18];
                    if ( *(_QWORD *)(v72 + 1880) )
                    {
                      _mm_lfence();
                      DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v72 + 1880), v255, (unsigned int)v270);
                    }
                  }
                }
              }
            }
            v294 = (unsigned __int8)byte_10317ABE5 >> 7;
            if ( byte_10317ABE5 < 0 )
            {
              v73 = (int *)v421 + 25;
              v633 = (__int64)v421 + 100;
              v459 = *((_DWORD *)v421 + 25);
              if ( (v459 & 8) != 0 && v270 >= 3 )
              {
                v634 = (__int64)v421 + 100;
                v460 = *v73;
                if ( (v460 & 0xC0000000) != 0x40000000 )
                {
                  v74 = (void *)*v421;
                  if ( *v421 )
                  {
                    v511 = 2;
                    if ( VirtualProtect(v74, 0x2000u, 2u, flOldProtect) )
                    {
                      _m_prefetchw(v73);
                      flOldProtect[1] = _InterlockedAnd(v73, 0x3FFFFFFFu);
                      _m_prefetchw(v73);
                      v75 = *v73;
                      do
                      {
                        v76 = v75;
                        v75 = _InterlockedCompareExchange(v73, v75 | 0x40000000, v75);
                      }
                      while ( v76 != v75 );
                      flOldProtect[2] = v75;
                    }
                  }
                }
              }
            }
            v77 = v421;
            v78 = v270;
            LatchBase::ReleaseInternal(v421 + 19, (unsigned int)v270);
            if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
            {
              v295 = (unsigned __int8)byte_10317AD4F >> 1;
              if ( (byte_10317AD4F & 2) != 0 )
                BUF::TraceLatchAcquireRelease(v77, 0, v78);
            }
            v257 &= 0xFFFF0000;
            v255 = 0;
            goto LABEL_156;
          }
LABEL_157:
          if ( *v70 )
          {
            PageRef::CatchupPageRedos((PageRef *)&v255, (const struct PageId *)&v259, v66);
            if ( v255 )
            {
              v635 = (char *)v255 + 98;
              v319 = *((_WORD *)v255 + 49);
              if ( (v319 & 0x400) != 0 && (__int16)v257 >= 3 )
              {
                PageRef::UnfixLatchOnly((PageRef *)&v255);
LABEL_185:
                v66 = v278;
                goto LABEL_186;
              }
              v271 = (__int16)v257;
              v422 = v255;
              v636 = (char *)v255 + 98;
              v320 = *((_WORD *)v255 + 49);
              if ( (v320 & 8) != 0 )
              {
                if ( v271 == 3 )
                {
                  v271 = 4;
                  goto LABEL_166;
                }
                if ( v271 >= 2 )
                {
LABEL_166:
                  v637 = (char *)v255 + 100;
                  v385 = *((_DWORD *)v255 + 25);
                  if ( (v385 & 8) != 0 )
                  {
                    v79 = v255[18];
                    if ( v79 )
                    {
                      v638 = v255[18];
                      if ( *(_QWORD *)(v79 + 1880) )
                      {
                        _mm_lfence();
                        DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v79 + 1880), v255, (unsigned int)v271);
                      }
                    }
                  }
                }
              }
              v296 = (unsigned __int8)byte_10317ABE5 >> 7;
              if ( byte_10317ABE5 < 0 )
              {
                v80 = (int *)v422 + 25;
                v639 = (__int64)v422 + 100;
                v386 = *((_DWORD *)v422 + 25);
                if ( (v386 & 8) != 0 && v271 >= 3 )
                {
                  v640 = (__int64)v422 + 100;
                  v387 = *v80;
                  if ( (v387 & 0xC0000000) != 0x40000000 )
                  {
                    v81 = (void *)*v422;
                    if ( *v422 )
                    {
                      flOldProtect[3] = 2;
                      if ( VirtualProtect(v81, 0x2000u, 2u, v513) )
                      {
                        _m_prefetchw(v80);
                        v82 = *v80;
                        do
                        {
                          v83 = v82;
                          v82 = _InterlockedCompareExchange(v80, v82 & 0x3FFFFFFF, v82);
                        }
                        while ( v83 != v82 );
                        v513[1] = v82;
                        _m_prefetchw(v80);
                        v84 = *v80;
                        do
                        {
                          v85 = v84;
                          v84 = _InterlockedCompareExchange(v80, v84 | 0x40000000, v84);
                        }
                        while ( v85 != v84 );
                        v513[2] = v84;
                      }
                    }
                  }
                }
              }
              v86 = v422;
              v87 = v271;
              LatchBase::ReleaseInternal(v422 + 19, (unsigned int)v271);
              if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
              {
                v297 = (unsigned __int8)byte_10317AD4F >> 1;
                if ( (byte_10317AD4F & 2) != 0 )
                  BUF::TraceLatchAcquireRelease(v86, 0, v87);
              }
              v257 &= 0xFFFF0000;
              v255 = 0;
              goto LABEL_185;
            }
          }
LABEL_186:
          LODWORD(v254) = 2;
          v88 = (_QWORD *)BPool::Get(qword_10317B628, v66, &v259, &v346, v254, v469);
          v255 = v88;
          v89 = v257 & 0xFFFF0000 | 2;
          v257 = v89;
          if ( SETLSFromTlsMaybeNull )
          {
            v90 = *v88;
            v641 = v90;
            v91 = (_DWORD *)((char *)SETLSFromTlsMaybeNull + 1280);
            v642 = v91;
            v92 = &v91[2 * (*v91 & 0xF) + 2];
            v643 = v92;
            if ( *v92 != v90 )
            {
              *v92 = v90;
              ++*(_QWORD *)v91;
              v89 = v257;
            }
          }
          v257 = v89 & 0xFFFFFF | (((v346 >> 3) & 1) << 24);
          v258 = v258 & 0xFFFFFF00 | (v346 >> 4) & 1;
          v93 = v532;
          if ( v532 )
          {
            if ( SETLSFromTlsMaybeNull )
            {
              if ( SETLSFromTlsMaybeNull == *((struct SEInternalTLS **)v66 + 903) )
              {
                v94 = (v89 & 0xFFFFFF | (((v346 >> 3) & 1) << 24)) >> 24;
                v513[3] = v94;
                v95 = (_QWORD *)(v532 + 22968);
                v644 = v532 + 22968;
                ++*(_QWORD *)(v532 + 23336);
                v96 = v469;
                if ( v469[1] )
                {
                  ++*(_QWORD *)(v93 + 23344);
                  v95[48] += *v96;
                  if ( v94 )
                  {
                    ++v95[49];
                    v95[50] += *v96;
                  }
                }
              }
            }
          }
          if ( !RecoveryUnit::IsRbIoDb(v66) || !*((_BYTE *)v66 + 8272) )
            goto LABEL_297;
          if ( !v259 || (LODWORD(v344) = 9, WORD2(v344) = 1, v259 == 9) && v260 == 1 )
          {
            v265 = 1;
            goto LABEL_297;
          }
          v265 = 0;
          v98 = *v255;
          v645 = v98;
          v262 = 0;
          if ( *(_WORD *)(v98 + 36)
            && ((v99 = *(_BYTE *)(v98 + 1), v99 != 11) && v99 != 8 && v99 != 9
             || *(_DWORD *)(v98 + 24) != 99
             || (v646 = &v366,
                 v647 = v98 + 32,
                 v366 = *(_DWORD *)(v98 + 32),
                 v367 = *(_WORD *)(v98 + 36),
                 !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v366, v97))
              ? (v100 = 0)
              : (v100 = 1),
                (v262 = v100) != 0) )
          {
            PageHeader::GetIcxLsn(v98, &v356);
          }
          else
          {
            v356 = *(_QWORD *)(v98 + 40);
            v357 = *(_WORD *)(v98 + 48);
          }
          v648 = &v356;
          v101 = (LSN *)((char *)v66 + 8444);
          v533 = (char *)v66 + 8444;
          v352 = 0;
          v353 = 0;
          v102 = (_DWORD *)((char *)v66 + 8456);
          v649 = v102;
          v103 = *v102;
          v347 = *v102;
          v534 = v102;
          do
          {
            v388 = v103 & 0xFFFFFFFE;
            v352 = *(_QWORD *)v533;
            v353 = *((_DWORD *)v533 + 2);
            _InterlockedOr(v253, 0);
            v347 = *v534;
            v103 = v347;
          }
          while ( v388 != v347 );
          if ( (unsigned int)v352 >= (unsigned int)v356
            && ((_DWORD)v352 != (_DWORD)v356
             || HIDWORD(v352) >= HIDWORD(v356) && (HIDWORD(v352) != HIDWORD(v356) || (unsigned __int16)v353 >= v357)) )
          {
            goto LABEL_297;
          }
          if ( !*((_BYTE *)v278 + 27336) )
          {
            v513[5] = 88;
            v650 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v651 = v650[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v652 = v651;
            v653 = *(_QWORD *)(v651 + 8);
            v654 = v653;
            v655 = *(_QWORD *)(v653 + 96);
            if ( v655 != *((_QWORD *)v278 + 1060) && !RecoveryUnit::IsParallelRedoThread(v278) )
              break;
          }
          v513[9] = 88;
          v677 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v678 = v677[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v679 = v678;
          v680 = *(_QWORD *)(v678 + 8);
          v681 = v680;
          v682 = *(_QWORD *)(v680 + 96);
          v66 = v278;
          if ( v682 == *((_QWORD *)v278 + 1060) || RecoveryUnit::IsParallelRedoThread(v278) )
            goto LABEL_297;
          if ( !SETLSFromTlsMaybeNull )
            SETLSFromTlsMaybeNull = GetSETLSFromTlsMaybeNull();
          v683 = &v284;
          v122 = *v255;
          v684 = v122;
          v264 = 0;
          if ( *(_WORD *)(v122 + 36)
            && ((v123 = *(_BYTE *)(v122 + 1), v123 != 11) && v123 != 8 && v123 != 9
             || *(_DWORD *)(v122 + 24) != 99
             || (v685 = &v370,
                 v686 = v122 + 32,
                 v370 = *(_DWORD *)(v122 + 32),
                 v371 = *(_WORD *)(v122 + 36),
                 !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v370, v121))
              ? (v124 = 0)
              : (v124 = 1),
                (v264 = v124) != 0) )
          {
            PageHeader::GetIcxLsn(v122, &v284);
            v125 = v285;
            v126 = v284;
          }
          else
          {
            v126 = *(_QWORD *)(v122 + 40);
            v284 = v126;
            v125 = *(_WORD *)(v122 + 48);
            v285 = v125;
          }
          v687 = &v284;
          v569 = v126;
          v570 = v125;
          v571 = 0;
          if ( v255 )
          {
            v688 = (char *)v255 + 98;
            v321 = *((_WORD *)v255 + 49);
            if ( (v321 & 0x400) != 0 && (__int16)v257 >= 3 )
            {
              PageRef::UnfixLatchOnly((PageRef *)&v255);
LABEL_294:
              v66 = v278;
              v126 = v284;
              v125 = v285;
              goto LABEL_295;
            }
            v272 = (__int16)v257;
            v423 = v255;
            v689 = (char *)v255 + 98;
            v322 = *((_WORD *)v255 + 49);
            if ( (v322 & 8) != 0 )
            {
              if ( v272 == 3 )
              {
                v272 = 4;
                goto LABEL_277;
              }
              if ( v272 >= 2 )
              {
LABEL_277:
                v690 = (char *)v255 + 100;
                v426 = *((_DWORD *)v255 + 25);
                if ( (v426 & 8) != 0 )
                {
                  v127 = v255[18];
                  if ( v127 )
                  {
                    v691 = v255[18];
                    if ( *(_QWORD *)(v127 + 1880) )
                    {
                      _mm_lfence();
                      DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v127 + 1880), v255, (unsigned int)v272);
                    }
                  }
                }
              }
            }
            v298 = (unsigned __int8)byte_10317ABE5 >> 7;
            if ( byte_10317ABE5 < 0 )
            {
              v128 = (int *)v423 + 25;
              v692 = (__int64)v423 + 100;
              v413 = *((_DWORD *)v423 + 25);
              if ( (v413 & 8) != 0 && v272 >= 3 )
              {
                v693 = (__int64)v423 + 100;
                v412 = *v128;
                if ( (v412 & 0xC0000000) != 0x40000000 )
                {
                  v129 = (void *)*v423;
                  if ( *v423 )
                  {
                    v513[10] = 2;
                    if ( VirtualProtect(v129, 0x2000u, 2u, v514) )
                    {
                      _m_prefetchw(v128);
                      v514[1] = _InterlockedAnd(v128, 0x3FFFFFFFu);
                      _m_prefetchw(v128);
                      v130 = *v128;
                      do
                      {
                        v131 = v130;
                        v130 = _InterlockedCompareExchange(v128, v130 | 0x40000000, v130);
                      }
                      while ( v131 != v130 );
                      v514[2] = v130;
                    }
                  }
                }
              }
            }
            v132 = v423;
            v133 = v272;
            LatchBase::ReleaseInternal(v423 + 19, (unsigned int)v272);
            if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
            {
              v299 = (unsigned __int8)byte_10317AD4F >> 1;
              if ( (byte_10317AD4F & 2) != 0 )
                BUF::TraceLatchAcquireRelease(v132, 0, v133);
            }
            v257 &= 0xFFFF0000;
            v255 = 0;
            goto LABEL_294;
          }
LABEL_295:
          v694 = &v476;
          v476 = v126;
          v477 = v125;
          v695 = &v463;
          v463 = v126;
          v464 = v125;
          v254 = 0;
          RecoveryMgr::WaitForRedoLsnToCatchUp(*v70, &v463, 4);
        }
        v473 = v101;
        v340.QuadPart = 0;
        LowPart = 0;
        v656 = v102;
        v104 = *v102;
        v348 = *v102;
        v105 = v101;
        p_HighPart = &v101[1].HighPart;
        while ( 1 )
        {
          v389 = v104 & 0xFFFFFFFE;
          v340 = *v105;
          LowPart = v105[1].LowPart;
          _InterlockedOr(v253, 0);
          v104 = *p_HighPart;
          v348 = v104;
          if ( v389 == v104 )
            break;
          v105 = v473;
        }
        v474 = v340;
        v106 = LowPart;
        v475 = LowPart;
        v107 = *v255;
        v657 = v107;
        v263 = 0;
        if ( *(_WORD *)(v107 + 36)
          && ((v108 = *(_BYTE *)(v107 + 1), v108 != 11) && v108 != 8 && v108 != 9
           || *(_DWORD *)(v107 + 24) != 99
           || (v658 = &v368,
               v659 = v107 + 32,
               v368 = *(_DWORD *)(v107 + 32),
               v369 = *(_WORD *)(v107 + 36),
               !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v368, v105))
            ? (v109 = 0)
            : (v109 = 1),
              (v263 = v109) != 0) )
        {
          PageHeader::GetIcxLsn(v107, &v358);
          v110 = v359;
        }
        else
        {
          v358 = *(LSN *)(v107 + 40);
          v110 = *(_WORD *)(v107 + 48);
          v359 = v110;
        }
        if ( v340.LowPart < v358.LowPart
          || v340.LowPart == v358.LowPart
          && (v340.HighPart < (unsigned int)v358.HighPart || v340.HighPart == v358.HighPart && v106 < v110) )
        {
          v112 = v278;
          v660 = *((_QWORD *)v278 + 214);
          LSN::FormatAsHexString(&v358, v972, &v447);
          LSN::FormatAsHexString(&v474, v973, &v447);
          v279 = 0x100000000001DLL;
          if ( (qword_10317F730 & 0x1000000000000LL) != 0 )
          {
            v449 = 6;
            v661 = v885;
            v885[0] = 0;
            v885[1] = 6;
            v886 = 0;
            v887 = &v890;
            v888 = &v914;
            v915 = 0;
            v916 = 0;
            v889 = 0;
            v917 = 0;
            v662 = &v890;
            v890 = &v918;
            v891 = 52;
            v892 = 5;
            v893 = 0;
            v663 = &v894;
            v894 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
            v895 = 16;
            v896 = 5;
            v897 = 0;
            v664 = &v898;
            v898 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
            v899 = 16;
            v900 = 6;
            v901 = 0;
            v665 = &v902;
            v902 = 0;
            v903 = 0;
            v904 = 7;
            v905 = 0;
            v666 = &v906;
            v906 = 0;
            v907 = 0;
            v908 = 8;
            v909 = 0;
            v667 = &v910;
            v910 = 0;
            v911 = 0;
            v912 = 9;
            v913 = 0;
            v918 = *((unsigned __int16 *)v112 + 860);
            v919 = v260;
            v920 = v259;
            v921 = -1;
            v668 = *v255;
            v922 = *(_BYTE *)(v668 + 1);
            v669 = &v894;
            v894 = (GUID *)(v113 + 596);
            v895 = 16;
            v896 = 5;
            v897 = 0;
            v670 = &v898;
            v898 = (GUID *)(v113 + 580);
            v899 = 16;
            v900 = 6;
            v901 = 0;
            v671 = v972;
            v114 = -1;
            do
              ++v114;
            while ( v972[v114] );
            v513[6] = 2 * v114;
            v672 = &v902;
            v902 = v972;
            v903 = 2 * v114;
            v904 = 7;
            v905 = 0;
            v673 = v973;
            v115 = -1;
            do
              ++v115;
            while ( v973[v115] );
            v513[7] = 2 * v115;
            v674 = &v906;
            v906 = v973;
            v907 = 2 * v115;
            v908 = 8;
            v909 = 0;
            v446 = 0;
            v116 = ((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v113, &v446);
            v117 = (int *)v116;
            v675 = v116;
            if ( v116 )
            {
              v118 = -1;
              do
                ++v118;
              while ( *(_WORD *)(v116 + 2 * v118) );
              v119 = 2 * v118;
            }
            else
            {
              v119 = 0;
            }
            v513[8] = v119;
            v120 = v887 + 10;
            v676 = v887 + 10;
            v887[10] = v117;
            *((_DWORD *)v120 + 2) = v119;
            *((_WORD *)v120 + 6) = 9;
            *((_WORD *)v120 + 7) = 0;
            XeSqlPkg::rbio_read_future_page::Publish((XeSqlPkg::rbio_read_future_page *)v884);
          }
        }
LABEL_297:
        v696 = *v255;
        v553 = v696;
        v279 = 0;
        FCB::RefreshHeaderFieldsFromBuffer(v436, 0, v696, 0);
        if ( v255 )
        {
          v697 = (char *)v255 + 98;
          v323 = *((_WORD *)v255 + 49);
          if ( (v323 & 0x400) != 0 && (__int16)v257 >= 3 )
          {
            PageRef::UnfixLatchOnly((PageRef *)&v255);
            goto LABEL_322;
          }
          v273 = (__int16)v257;
          v424 = v255;
          v698 = (char *)v255 + 98;
          v324 = *((_WORD *)v255 + 49);
          if ( (v324 & 8) != 0 )
          {
            if ( v273 == 3 )
            {
              v273 = 4;
              goto LABEL_305;
            }
            if ( v273 >= 2 )
            {
LABEL_305:
              v699 = (char *)v255 + 100;
              v411 = *((_DWORD *)v255 + 25);
              if ( (v411 & 8) != 0 )
              {
                v134 = v255[18];
                if ( v134 )
                {
                  v700 = v255[18];
                  if ( *(_QWORD *)(v134 + 1880) )
                  {
                    _mm_lfence();
                    DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v134 + 1880), v255, (unsigned int)v273);
                  }
                }
              }
            }
          }
          v300 = (unsigned __int8)byte_10317ABE5 >> 7;
          if ( byte_10317ABE5 < 0 )
          {
            v135 = (int *)v424 + 25;
            v701 = (__int64)v424 + 100;
            v410 = *((_DWORD *)v424 + 25);
            if ( (v410 & 8) != 0 && v273 >= 3 )
            {
              v702 = (__int64)v424 + 100;
              v408 = *v135;
              if ( (v408 & 0xC0000000) != 0x40000000 )
              {
                v136 = (void *)*v424;
                if ( *v424 )
                {
                  v514[3] = 2;
                  if ( VirtualProtect(v136, 0x2000u, 2u, v515) )
                  {
                    _m_prefetchw(v135);
                    v515[1] = _InterlockedAnd(v135, 0x3FFFFFFFu);
                    _m_prefetchw(v135);
                    v137 = *v135;
                    do
                    {
                      v138 = v137;
                      v137 = _InterlockedCompareExchange(v135, v137 | 0x40000000, v137);
                    }
                    while ( v138 != v137 );
                    v515[2] = v137;
                  }
                }
              }
            }
          }
          v139 = v424;
          v140 = v273;
          LatchBase::ReleaseInternal(v424 + 19, (unsigned int)v273);
          if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
          {
            v301 = (unsigned __int8)byte_10317AD4F >> 1;
            if ( (byte_10317AD4F & 2) != 0 )
              BUF::TraceLatchAcquireRelease(v139, 0, v140);
          }
          v257 &= 0xFFFF0000;
          v255 = 0;
        }
LABEL_322:
        v56 = (char *)v57 + 56;
LABEL_323:
        v58 = (char *)*((_QWORD *)v280 + 1);
        if ( v58 == v56 )
          v58 = 0;
        v703 = v58;
      }
      DBTABLE::InitReplicaDBFragments(v281);
      v379 = (volatile signed __int64 *)((char *)v59 + 5376);
      v704 = 0;
      v705 = 0;
      v428 = 0;
      v454 = 0;
      UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      v515[3] = 256;
      v706 = (char *)v59 + 5376;
      if ( *((_DWORD *)v59 + 1344) )
      {
        v409 = 0;
LABEL_330:
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84
          && (v537 = 0,
              v515[4] = 88,
              v709 = NtCurrentTeb()->ThreadLocalStoragePointer,
              v141 = v709[SystemThread_TlsIndex],
              v30 = SystemThread_TlsOffset + v141 == 0,
              v142 = SystemThread_TlsOffset + v141,
              v710 = v142,
              !v30)
          && *(_QWORD *)(v142 + 272) == v142 )
        {
          v143 = *(_QWORD *)(v142 + 256);
          v537 = v143;
        }
        else
        {
          v143 = 0;
        }
        v454 = v143;
        if ( v143 )
        {
          v711 = &v471;
          v515[5] = Base_PublicGlobals::sm_invariantTscAvailable;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            v515[6] = QueryPerformanceCounter(&v538);
            v144 = (DirtyPageMgr *)v538.QuadPart;
            v471 = (DirtyPageMgr *)v538.QuadPart;
          }
          else
          {
            v144 = MEMORY[0x7FFE0008];
            v539 = MEMORY[0x7FFE0008];
            v471 = MEMORY[0x7FFE0008];
            v143 = v454;
          }
          v712 = v144;
          v428 = v144;
        }
        v515[7] = 2;
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v379, UniqueThread_low);
        else
          Spinlock<148,10,258>::SpinToAcquireOptimistic(v379, v143, UniqueThread_low);
        if ( v143 )
        {
          v713 = &v427;
          v515[8] = Base_PublicGlobals::sm_invariantTscAvailable;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            v515[9] = QueryPerformanceCounter(&v540);
            v145 = (DirtyPageMgr *)v540.QuadPart;
            v427 = (DirtyPageMgr *)v540.QuadPart;
          }
          else
          {
            v145 = MEMORY[0x7FFE0008];
            v541 = MEMORY[0x7FFE0008];
            v427 = MEMORY[0x7FFE0008];
            v143 = v454;
          }
          v714 = &v428;
          v715 = &v427;
          if ( v145 < v428 )
          {
            v146 = 0;
            v279 = 0;
          }
          else
          {
            v146 = v145 - v428;
            v279 = v146;
          }
          v279 = v146;
          v716 = v146;
          v717 = v143 + 3192;
          *(_QWORD *)(v143 + 3192) += v146;
        }
      }
      else
      {
        v707 = _InterlockedCompareExchange64(v379, UniqueThread_low, 0);
        v708 = v707;
        v409 = v707 == 0;
        if ( v707 )
          goto LABEL_330;
      }
      v147 = (_QWORD *)((char *)v281 + 16);
      v718 = (char *)v281 + 16;
      v719 = (char *)v59 + 2664;
      *((_QWORD *)v281 + 3) = *((_QWORD *)v59 + 334);
      **((_QWORD **)v59 + 334) = v147;
      *((_QWORD *)v59 + 334) = v147;
      *v147 = (char *)v59 + 2664;
      ++*((_DWORD *)v59 + 670);
      *((_DWORD *)v59 + 158) |= 0x2000u;
      v720 = (char *)v59 + 5376;
      v335 = (char)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
      if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v148 = rand();
        v149 = (unsigned int)(5 * (v148 / 5));
        if ( v148 == (_DWORD)v149 )
          Spinlock<148,10,258>::UpdateStatSnapshot(v149);
      }
      v721 = (char *)v59 + 5376;
      *((_QWORD *)v59 + 672) = 0;
      v302 = (unsigned __int8)byte_10317ACC5 >> 2;
      if ( (byte_10317ACC5 & 4) != 0 )
        LogSystemMetadataNotSentToClient(
          L"DBID: [%d] enabled copy-on-write for primary database",
          *((unsigned __int16 *)v59 + 20));
      BPool::MarkBufsCopyOnWrite(qword_10317B628, *((_QWORD *)v59 + 578), 1);
      v333 = *((_QWORD *)v57 + 130);
      v334 = *((_WORD *)v57 + 524);
      v360 = v333;
      v361 = v334;
      v478 = 0;
      v479 = 0;
      v480 = 0;
      if ( !v334 && !v333 )
      {
        v381 = (volatile signed __int64 *)(*(_QWORD *)(*((_QWORD *)v59 + 578) + 1712LL) + 5376LL);
        v722 = v381;
        v723 = 0;
        v724 = 0;
        v432 = 0;
        v430 = 0;
        v429 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        v515[10] = 256;
        v725 = v381;
        if ( *(_DWORD *)v381 )
        {
          v448 = 0;
LABEL_362:
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84
            && (v542 = 0,
                v515[11] = 88,
                v728 = NtCurrentTeb()->ThreadLocalStoragePointer,
                v150 = v728[SystemThread_TlsIndex],
                v30 = SystemThread_TlsOffset + v150 == 0,
                v151 = SystemThread_TlsOffset + v150,
                v729 = v151,
                !v30)
            && *(_QWORD *)(v151 + 272) == v151 )
          {
            v152 = *(_QWORD *)(v151 + 256);
            v542 = v152;
          }
          else
          {
            v152 = 0;
          }
          v430 = v152;
          if ( v152 )
          {
            v730 = &v472;
            v515[12] = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              v536 = QueryPerformanceCounter(&v543);
              v153 = (DirtyPageMgr *)v543.QuadPart;
              v472 = (DirtyPageMgr *)v543.QuadPart;
            }
            else
            {
              v153 = MEMORY[0x7FFE0008];
              v544 = MEMORY[0x7FFE0008];
              v472 = MEMORY[0x7FFE0008];
              v152 = v430;
            }
            v731 = v153;
            v432 = v153;
          }
          v559 = 2;
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v381, v429);
          else
            Spinlock<148,10,258>::SpinToAcquireOptimistic(v381, v152, v429);
          if ( v152 )
          {
            v732 = &v431;
            v560 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              v561 = QueryPerformanceCounter(&v545);
              v154 = (DirtyPageMgr *)v545.QuadPart;
              v431 = (DirtyPageMgr *)v545.QuadPart;
            }
            else
            {
              v154 = MEMORY[0x7FFE0008];
              v546 = MEMORY[0x7FFE0008];
              v431 = MEMORY[0x7FFE0008];
              v152 = v430;
            }
            v733 = &v432;
            v734 = &v431;
            if ( v154 < v432 )
            {
              v155 = 0;
              v279 = 0;
            }
            else
            {
              v155 = v154 - v432;
              v279 = v155;
            }
            v279 = v155;
            v735 = v155;
            v736 = v152 + 3192;
            *(_QWORD *)(v152 + 3192) += v155;
          }
        }
        else
        {
          v726 = _InterlockedCompareExchange64(v381, v429, 0);
          v727 = v726;
          v448 = v726 == 0;
          if ( v726 )
            goto LABEL_362;
        }
        LogTruncMgr::GetStartLogSansBackupWithReason(
          (LogTruncMgr *)(*((_QWORD *)v59 + 578) + 2168LL),
          (struct LSN *)&v333,
          (enum _TruncationHoldup *)v562,
          1,
          0,
          0);
        LogTruncMgr::GetStartLogForSLog((LogTruncMgr *)(*((_QWORD *)v59 + 578) + 2168LL), (struct LSN *)&v360);
        if ( !a6 )
          RecoveryUnit::SetMaxGCLsn(*((RecoveryUnit **)v281 + 578), (const struct LSN *)&v333);
        v156 = (_QWORD *)(*(_QWORD *)(*((_QWORD *)v59 + 578) + 1712LL) + 5376LL);
        v737 = v156;
        v738 = v156;
        v303 = (char)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v157 = rand();
          v158 = (unsigned int)(5 * (v157 / 5));
          if ( v157 == (_DWORD)v158 )
            Spinlock<148,10,258>::UpdateStatSnapshot(v158);
        }
        v739 = v156;
        *v156 = 0;
      }
      ReplicaState::DisableLogTruncation(v57, &v333, 7);
      ReplicaState::DisableSLogTruncationAndCleanup(v57, &v360, 7);
      v304 = (unsigned __int8)byte_10317ACC5 >> 2;
      if ( (byte_10317ACC5 & 4) != 0 )
        LogSystemMetadataNotSentToClient(L"DBID: [%d] refresh files for consistent REDO copy activities", v336);
      v159 = v338;
      v740 = v338;
      v160 = *(char **)(v338 + 8);
      if ( v160 == (char *)v338 )
        v160 = 0;
      v741 = v160;
      while ( 2 )
      {
        v280 = v160;
        if ( v160 )
        {
          v161 = v160;
          v450 = *((_WORD *)v160 + 18);
          v742 = *((_QWORD *)v59 + 578);
          v162 = FileMgr::GetFCB(*(_QWORD *)(v742 + 1696), v450, 0);
          v547 = v162;
          v163 = *(_DWORD *)(v162 + 100);
          if ( v163 < 0 || (*(_BYTE *)(v162 + 124) & 1) == 0 || (v163 & 0x90000000) != 0 || *(_DWORD *)(v162 + 104) == 5 )
            goto LABEL_601;
          v451 = *((_WORD *)v161 + 18);
          v164 = v281;
          v743 = *((_QWORD *)v281 + 578);
          v436 = FileMgr::GetFCB(*(_QWORD *)(v743 + 1696), v451, 0);
          v452 = *(_WORD *)(v436 + 32);
          v259 = 0;
          v260 = v452;
          v165 = (RecoveryUnit *)*((_QWORD *)v164 + 578);
          v261 = v165;
          v882 = 0;
          v883 = 0;
          v305 = CommonGlobalState::m_CollectingStatistics;
          if ( !CommonGlobalState::m_CollectingStatistics )
            goto LABEL_405;
          v306 = (unsigned __int8)byte_10317ABE6 >> 7;
          if ( byte_10317ABE6 < 0 )
            goto LABEL_405;
          v390 = 0;
          v563 = 88;
          v744 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v745 = (_QWORD *)(v744[SystemThread_TlsIndex] + SystemThread_TlsOffset);
          v746 = v745;
          v166 = *v745;
          v747 = v166;
          v748 = v166;
          if ( !v166 )
            goto LABEL_411;
          v167 = **(struct CSessionTraceFlags ***)(v166 + 56);
          v749 = v167;
          if ( v167 )
          {
            v548 = v167;
            v390 = CSessionTraceFlags::CheckSessionTraceInternal(v167, 0x337u);
            if ( v390 )
            {
              v165 = v261;
              goto LABEL_405;
            }
          }
          else
          {
LABEL_411:
            v548 = 0;
          }
          v564 = 88;
          v750 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v751 = v750[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v752 = v751;
          v170 = *(_QWORD *)(v751 + 8);
          v753 = v170;
          v754 = v170;
          v165 = v261;
          if ( v170 )
            v168 = *(struct SEInternalTLS **)(v170 + 96);
          else
LABEL_405:
            v168 = 0;
          v382 = v168;
          v169 = (_QWORD *)((char *)v165 + 1832);
          v549 = *((_QWORD *)v165 + 229);
          v467 = (unsigned int *)&v881;
LABEL_407:
          v349 = 0;
          if ( v255 )
          {
            v755 = (char *)v255 + 98;
            v325 = *((_WORD *)v255 + 49);
            if ( (v325 & 0x400) != 0 && (__int16)v257 >= 3 )
            {
              PageRef::UnfixLatchOnly((PageRef *)&v255);
              goto LABEL_435;
            }
            v274 = (__int16)v257;
            v433 = v255;
            v756 = (char *)v255 + 98;
            v326 = *((_WORD *)v255 + 49);
            if ( (v326 & 8) != 0 )
            {
              if ( v274 == 3 )
              {
                v274 = 4;
                goto LABEL_418;
              }
              if ( v274 >= 2 )
              {
LABEL_418:
                v757 = (char *)v255 + 100;
                v391 = *((_DWORD *)v255 + 25);
                if ( (v391 & 8) != 0 )
                {
                  v171 = v255[18];
                  if ( v171 )
                  {
                    v758 = v255[18];
                    if ( *(_QWORD *)(v171 + 1880) )
                    {
                      _mm_lfence();
                      DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v171 + 1880), v255, (unsigned int)v274);
                    }
                  }
                }
              }
            }
            v307 = (unsigned __int8)byte_10317ABE5 >> 7;
            if ( byte_10317ABE5 < 0 )
            {
              v172 = (int *)v433 + 25;
              v759 = (__int64)v433 + 100;
              v392 = *((_DWORD *)v433 + 25);
              if ( (v392 & 8) != 0 && v274 >= 3 )
              {
                v760 = (__int64)v433 + 100;
                v393 = *v172;
                if ( (v393 & 0xC0000000) != 0x40000000 )
                {
                  v173 = (void *)*v433;
                  if ( *v433 )
                  {
                    v565 = 2;
                    if ( VirtualProtect(v173, 0x2000u, 2u, v566) )
                    {
                      _m_prefetchw(v172);
                      v566[1] = _InterlockedAnd(v172, 0x3FFFFFFFu);
                      _m_prefetchw(v172);
                      v174 = *v172;
                      do
                      {
                        v175 = v174;
                        v174 = _InterlockedCompareExchange(v172, v174 | 0x40000000, v174);
                      }
                      while ( v175 != v174 );
                      v566[2] = v174;
                    }
                  }
                }
              }
            }
            v176 = v433;
            v177 = v274;
            LatchBase::ReleaseInternal(v433 + 19, (unsigned int)v274);
            if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
            {
              v308 = (unsigned __int8)byte_10317AD4F >> 1;
              if ( (byte_10317AD4F & 2) != 0 )
                BUF::TraceLatchAcquireRelease(v176, 0, v177);
            }
            v257 &= 0xFFFF0000;
            v255 = 0;
LABEL_435:
            v165 = v261;
          }
          if ( *v169 )
          {
            PageRef::CatchupPageRedos((PageRef *)&v255, (const struct PageId *)&v259, v165);
            if ( v255 )
            {
              v761 = (char *)v255 + 98;
              v327 = *((_WORD *)v255 + 49);
              if ( (v327 & 0x400) != 0 && (__int16)v257 >= 3 )
              {
                PageRef::UnfixLatchOnly((PageRef *)&v255);
                goto LABEL_464;
              }
              v275 = (__int16)v257;
              v434 = v255;
              v762 = (char *)v255 + 98;
              v328 = *((_WORD *)v255 + 49);
              if ( (v328 & 8) != 0 )
              {
                if ( v275 == 3 )
                {
                  v275 = 4;
                  goto LABEL_445;
                }
                if ( v275 >= 2 )
                {
LABEL_445:
                  v763 = (char *)v255 + 100;
                  v394 = *((_DWORD *)v255 + 25);
                  if ( (v394 & 8) != 0 )
                  {
                    v178 = v255[18];
                    if ( v178 )
                    {
                      v764 = v255[18];
                      if ( *(_QWORD *)(v178 + 1880) )
                      {
                        _mm_lfence();
                        DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v178 + 1880), v255, (unsigned int)v275);
                      }
                    }
                  }
                }
              }
              v309 = (unsigned __int8)byte_10317ABE5 >> 7;
              if ( byte_10317ABE5 < 0 )
              {
                v179 = (int *)v434 + 25;
                v765 = (__int64)v434 + 100;
                v395 = *((_DWORD *)v434 + 25);
                if ( (v395 & 8) != 0 && v275 >= 3 )
                {
                  v766 = (__int64)v434 + 100;
                  v396 = *v179;
                  if ( (v396 & 0xC0000000) != 0x40000000 )
                  {
                    v180 = (void *)*v434;
                    if ( *v434 )
                    {
                      v566[3] = 2;
                      if ( VirtualProtect(v180, 0x2000u, 2u, v567) )
                      {
                        _m_prefetchw(v179);
                        v181 = *v179;
                        do
                        {
                          v182 = v181;
                          v181 = _InterlockedCompareExchange(v179, v181 & 0x3FFFFFFF, v181);
                        }
                        while ( v182 != v181 );
                        v567[1] = v181;
                        _m_prefetchw(v179);
                        v183 = *v179;
                        do
                        {
                          v184 = v183;
                          v183 = _InterlockedCompareExchange(v179, v183 | 0x40000000, v183);
                        }
                        while ( v184 != v183 );
                        v567[2] = v183;
                      }
                    }
                  }
                }
              }
              v185 = v434;
              v186 = v275;
              LatchBase::ReleaseInternal(v434 + 19, (unsigned int)v275);
              if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
              {
                v310 = (unsigned __int8)byte_10317AD4F >> 1;
                if ( (byte_10317AD4F & 2) != 0 )
                  BUF::TraceLatchAcquireRelease(v185, 0, v186);
              }
              v257 &= 0xFFFF0000;
              v255 = 0;
LABEL_464:
              v165 = v261;
            }
          }
          RecoveryUnit::PrePageUpdateHint(v165, (const struct PageId *)&v259);
          LODWORD(v254) = 4;
          v187 = (_QWORD *)BPool::Get(qword_10317B628, v165, &v259, &v349, v254, v467);
          v255 = v187;
          v188 = v257 & 0xFFFF0000 | 4;
          v257 = v188;
          if ( v382 )
          {
            v189 = *v187;
            v767 = v189;
            v190 = (_DWORD *)((char *)v382 + 1280);
            v768 = v190;
            v191 = &v190[2 * (*v190 & 0xF) + 2];
            v769 = v191;
            if ( *v191 != v189 )
            {
              *v191 = v189;
              ++*(_QWORD *)v190;
              v188 = v257;
            }
          }
          v257 = v188 & 0xFFFFFF | (((v349 >> 3) & 1) << 24);
          v258 = v258 & 0xFFFFFF00 | (v349 >> 4) & 1;
          v192 = v549;
          if ( v549 )
          {
            if ( v382 )
            {
              if ( v382 == *((struct SEInternalTLS **)v165 + 903) )
              {
                v193 = (v188 & 0xFFFFFF | (((v349 >> 3) & 1) << 24)) >> 24;
                v567[3] = v193;
                v194 = (_QWORD *)(v549 + 22968);
                v770 = v549 + 22968;
                ++*(_QWORD *)(v549 + 23336);
                v195 = v467;
                if ( v467[1] )
                {
                  ++*(_QWORD *)(v192 + 23344);
                  v194[48] += *v195;
                  if ( v193 )
                  {
                    ++v194[49];
                    v194[50] += *v195;
                  }
                }
              }
            }
          }
          if ( !RecoveryUnit::IsRbIoDb(v165) || !*((_BYTE *)v165 + 8272) )
            goto LABEL_576;
          if ( !v259 || (v336 = 9, v337 = 1, v259 == 9) && v260 == 1 )
          {
            v269 = 1;
            goto LABEL_576;
          }
          v269 = 0;
          v197 = *v255;
          v771 = v197;
          v266 = 0;
          if ( *(_WORD *)(v197 + 36)
            && ((v198 = *(_BYTE *)(v197 + 1), v198 != 11) && v198 != 8 && v198 != 9
             || *(_DWORD *)(v197 + 24) != 99
             || (v772 = &v376,
                 v773 = v197 + 32,
                 v376 = *(_DWORD *)(v197 + 32),
                 v377 = *(_WORD *)(v197 + 36),
                 !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v376, v196))
              ? (v199 = 0)
              : (v199 = 1),
                (v266 = v199) != 0) )
          {
            PageHeader::GetIcxLsn(v197, &v362);
          }
          else
          {
            v362 = *(_QWORD *)(v197 + 40);
            v363 = *(_WORD *)(v197 + 48);
          }
          v774 = &v362;
          v200 = (LSN *)((char *)v165 + 8444);
          v550 = (char *)v165 + 8444;
          v354 = 0;
          v355 = 0;
          v201 = (_DWORD *)((char *)v165 + 8456);
          v775 = v201;
          v202 = *v201;
          v350 = *v201;
          v551 = v201;
          do
          {
            v397 = v202 & 0xFFFFFFFE;
            v354 = *(_QWORD *)v550;
            v355 = *((_DWORD *)v550 + 2);
            _InterlockedOr(v253, 0);
            v350 = *v551;
            v202 = v350;
          }
          while ( v397 != v350 );
          if ( (unsigned int)v354 >= (unsigned int)v362
            && ((_DWORD)v354 != (_DWORD)v362
             || HIDWORD(v354) >= HIDWORD(v362) && (HIDWORD(v354) != HIDWORD(v362) || (unsigned __int16)v355 >= v363)) )
          {
            goto LABEL_576;
          }
          if ( !*((_BYTE *)v261 + 27336) )
          {
            v567[5] = 88;
            v776 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v777 = v776[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v778 = v777;
            v779 = *(_QWORD *)(v777 + 8);
            v780 = v779;
            v781 = *(_QWORD *)(v779 + 96);
            if ( v781 != *((_QWORD *)v261 + 1060) && !RecoveryUnit::IsParallelRedoThread(v261) )
            {
              v468 = v200;
              v342.QuadPart = 0;
              v343 = 0;
              v782 = v201;
              v203 = *v201;
              v351 = *v201;
              v204 = v200;
              v552 = &v200[1].HighPart;
              while ( 1 )
              {
                v398 = v203 & 0xFFFFFFFE;
                v342 = *v204;
                v343 = v204[1].LowPart;
                _InterlockedOr(v253, 0);
                v203 = *v552;
                v351 = v203;
                if ( v398 == v203 )
                  break;
                v204 = v468;
              }
              v481 = v342;
              v205 = v343;
              v482 = v343;
              v206 = *v255;
              v783 = v206;
              v267 = 0;
              if ( *(_WORD *)(v206 + 36)
                && ((v207 = *(_BYTE *)(v206 + 1), v207 != 11) && v207 != 8 && v207 != 9
                 || *(_DWORD *)(v206 + 24) != 99
                 || (v784 = &v372,
                     v785 = v206 + 32,
                     v372 = *(_DWORD *)(v206 + 32),
                     v373 = *(_WORD *)(v206 + 36),
                     !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v372, v204))
                  ? (v208 = 0)
                  : (v208 = 1),
                    (v267 = v208) != 0) )
              {
                PageHeader::GetIcxLsn(v206, &v364);
                v209 = v365;
              }
              else
              {
                v364 = *(LSN *)(v206 + 40);
                v209 = *(_WORD *)(v206 + 48);
                v365 = v209;
              }
              if ( v342.LowPart < v364.LowPart
                || v342.LowPart == v364.LowPart
                && (v342.HighPart < (unsigned int)v364.HighPart || v342.HighPart == v364.HighPart && v205 < v209) )
              {
                v211 = v261;
                v786 = *((_QWORD *)v261 + 214);
                LSN::FormatAsHexString(&v364, v974, &v399);
                LSN::FormatAsHexString(&v481, v975, &v399);
                v338 = 0x100000000001DLL;
                if ( (qword_10317F730 & 0x1000000000000LL) != 0 )
                {
                  v453 = 6;
                  v787 = v924;
                  v924[0] = 0;
                  v924[1] = 6;
                  v925 = 0;
                  v926 = &v929;
                  v927 = &v953;
                  v954 = 0;
                  v955 = 0;
                  v928 = 0;
                  v956 = 0;
                  v788 = &v929;
                  v929 = &v957;
                  v930 = 52;
                  v931 = 5;
                  v932 = 0;
                  v789 = &v933;
                  v933 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
                  v934 = 16;
                  v935 = 5;
                  v936 = 0;
                  v790 = &v937;
                  v937 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
                  v938 = 16;
                  v939 = 6;
                  v940 = 0;
                  v791 = &v941;
                  v941 = 0;
                  v942 = 0;
                  v943 = 7;
                  v944 = 0;
                  v792 = &v945;
                  v945 = 0;
                  v946 = 0;
                  v947 = 8;
                  v948 = 0;
                  v793 = &v949;
                  v949 = 0;
                  v950 = 0;
                  v951 = 9;
                  v952 = 0;
                  v957 = *((unsigned __int16 *)v211 + 860);
                  v958 = v260;
                  v959 = v259;
                  v960 = -1;
                  v794 = *v255;
                  v961 = *(_BYTE *)(v794 + 1);
                  v795 = &v933;
                  v933 = (GUID *)(v212 + 596);
                  v934 = 16;
                  v935 = 5;
                  v936 = 0;
                  v796 = &v937;
                  v937 = (GUID *)(v212 + 580);
                  v938 = 16;
                  v939 = 6;
                  v940 = 0;
                  v797 = v974;
                  v213 = -1;
                  do
                    ++v213;
                  while ( v974[v213] );
                  v567[6] = 2 * v213;
                  v798 = &v941;
                  v941 = v974;
                  v942 = 2 * v213;
                  v943 = 7;
                  v944 = 0;
                  v799 = v975;
                  v214 = -1;
                  do
                    ++v214;
                  while ( v975[v214] );
                  v567[7] = 2 * v214;
                  v800 = &v945;
                  v945 = v975;
                  v946 = 2 * v214;
                  v947 = 8;
                  v948 = 0;
                  v400 = 0;
                  v215 = ((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v212, &v400);
                  v216 = (int *)v215;
                  v801 = v215;
                  if ( v215 )
                  {
                    v217 = -1;
                    do
                      ++v217;
                    while ( *(_WORD *)(v215 + 2 * v217) );
                    v218 = 2 * v217;
                  }
                  else
                  {
                    v218 = 0;
                  }
                  v567[8] = v218;
                  v219 = v926 + 10;
                  v802 = v926 + 10;
                  v926[10] = v216;
                  *((_DWORD *)v219 + 2) = v218;
                  *((_WORD *)v219 + 6) = 9;
                  *((_WORD *)v219 + 7) = 0;
                  XeSqlPkg::rbio_read_future_page::Publish((XeSqlPkg::rbio_read_future_page *)v923);
                }
              }
LABEL_576:
              v822 = *v255;
              v553 = v822;
              v279 = 0;
              FCB::RefreshHeaderFieldsFromBuffer(v436, 0, v822, 0);
              v823 = v255;
              v488 = 1;
              v233 = BPool::PrepareToDirty(qword_10317B628, v255, 1, 0);
              v824 = v233;
              *(_WORD *)(v233 + 4) &= ~0x200u;
              *(_WORD *)(v233 + 4) &= ~0x1000u;
              *(_DWORD *)(v233 + 64) = 1;
              if ( v255 )
              {
                v825 = (char *)v255 + 98;
                v331 = *((_WORD *)v255 + 49);
                if ( (v331 & 0x400) != 0 && (__int16)v257 >= 3 )
                {
                  PageRef::UnfixLatchOnly((PageRef *)&v255);
                  goto LABEL_601;
                }
                v277 = (__int16)v257;
                v437 = v255;
                v826 = (char *)v255 + 98;
                v332 = *((_WORD *)v255 + 49);
                if ( (v332 & 8) != 0 )
                {
                  if ( v277 == 3 )
                  {
                    v277 = 4;
                    goto LABEL_584;
                  }
                  if ( v277 >= 2 )
                  {
LABEL_584:
                    v827 = (char *)v255 + 100;
                    v404 = *((_DWORD *)v255 + 25);
                    if ( (v404 & 8) != 0 )
                    {
                      v234 = v255[18];
                      if ( v234 )
                      {
                        v828 = v255[18];
                        if ( *(_QWORD *)(v234 + 1880) )
                        {
                          _mm_lfence();
                          DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v234 + 1880), v255, (unsigned int)v277);
                        }
                      }
                    }
                  }
                }
                v313 = (unsigned __int8)byte_10317ABE5 >> 7;
                if ( byte_10317ABE5 < 0 )
                {
                  v235 = (int *)v437 + 25;
                  v829 = (__int64)v437 + 100;
                  v405 = *((_DWORD *)v437 + 25);
                  if ( (v405 & 8) != 0 && v277 >= 3 )
                  {
                    v830 = (__int64)v437 + 100;
                    v406 = *v235;
                    if ( (v406 & 0xC0000000) != 0x40000000 )
                    {
                      v236 = (void *)*v437;
                      if ( *v437 )
                      {
                        v489 = 2;
                        if ( VirtualProtect(v236, 0x2000u, 2u, v490) )
                        {
                          _m_prefetchw(v235);
                          v490[1] = _InterlockedAnd(v235, 0x3FFFFFFFu);
                          _m_prefetchw(v235);
                          v237 = *v235;
                          do
                          {
                            v238 = v237;
                            v237 = _InterlockedCompareExchange(v235, v237 | 0x40000000, v237);
                          }
                          while ( v238 != v237 );
                          v490[2] = v237;
                        }
                      }
                    }
                  }
                }
                v239 = v437;
                v240 = v277;
                LatchBase::ReleaseInternal(v437 + 19, (unsigned int)v277);
                if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
                {
                  v314 = (unsigned __int8)byte_10317AD4F >> 1;
                  if ( (byte_10317AD4F & 2) != 0 )
                    BUF::TraceLatchAcquireRelease(v239, 0, v240);
                }
                v257 &= 0xFFFF0000;
                v255 = 0;
              }
LABEL_601:
              v160 = (char *)*((_QWORD *)v280 + 1);
              if ( v160 == (char *)v159 )
                v160 = 0;
              v831 = v160;
              continue;
            }
          }
          v567[9] = 88;
          v803 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v804 = v803[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v805 = v804;
          v806 = *(_QWORD *)(v804 + 8);
          v807 = v806;
          v808 = *(_QWORD *)(v806 + 96);
          v165 = v261;
          if ( v808 == *((_QWORD *)v261 + 1060) || RecoveryUnit::IsParallelRedoThread(v261) )
            goto LABEL_576;
          if ( !v382 )
            v382 = GetSETLSFromTlsMaybeNull();
          v809 = &v282;
          v221 = *v255;
          v810 = v221;
          v268 = 0;
          if ( *(_WORD *)(v221 + 36)
            && ((v222 = *(_BYTE *)(v221 + 1), v222 != 11) && v222 != 8 && v222 != 9
             || *(_DWORD *)(v221 + 24) != 99
             || (v811 = &v374,
                 v812 = v221 + 32,
                 v374 = *(_DWORD *)(v221 + 32),
                 v375 = *(_WORD *)(v221 + 36),
                 !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v374, v220))
              ? (v223 = 0)
              : (v223 = 1),
                (v268 = v223) != 0) )
          {
            PageHeader::GetIcxLsn(v221, &v282);
            v224 = v283;
            v225 = v282;
          }
          else
          {
            v225 = *(_QWORD *)(v221 + 40);
            v282 = v225;
            v224 = *(_WORD *)(v221 + 48);
            v283 = v224;
          }
          v813 = &v282;
          v572 = v225;
          v573 = v224;
          v574 = 0;
          if ( v255 )
          {
            v814 = (char *)v255 + 98;
            v329 = *((_WORD *)v255 + 49);
            if ( (v329 & 0x400) != 0 && (__int16)v257 >= 3 )
            {
              PageRef::UnfixLatchOnly((PageRef *)&v255);
              goto LABEL_573;
            }
            v276 = (__int16)v257;
            v435 = v255;
            v815 = (char *)v255 + 98;
            v330 = *((_WORD *)v255 + 49);
            if ( (v330 & 8) != 0 )
            {
              if ( v276 == 3 )
              {
                v276 = 4;
                goto LABEL_556;
              }
              if ( v276 >= 2 )
              {
LABEL_556:
                v816 = (char *)v255 + 100;
                v401 = *((_DWORD *)v255 + 25);
                if ( (v401 & 8) != 0 )
                {
                  v226 = v255[18];
                  if ( v226 )
                  {
                    v817 = v255[18];
                    if ( *(_QWORD *)(v226 + 1880) )
                    {
                      _mm_lfence();
                      DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v226 + 1880), v255, (unsigned int)v276);
                    }
                  }
                }
              }
            }
            v311 = (unsigned __int8)byte_10317ABE5 >> 7;
            if ( byte_10317ABE5 < 0 )
            {
              v227 = (int *)v435 + 25;
              v818 = (__int64)v435 + 100;
              v402 = *((_DWORD *)v435 + 25);
              if ( (v402 & 8) != 0 && v276 >= 3 )
              {
                v819 = (__int64)v435 + 100;
                v403 = *v227;
                if ( (v403 & 0xC0000000) != 0x40000000 )
                {
                  v228 = (void *)*v435;
                  if ( *v435 )
                  {
                    v567[10] = 2;
                    if ( VirtualProtect(v228, 0x2000u, 2u, &v568) )
                    {
                      _m_prefetchw(v227);
                      v575 = _InterlockedAnd(v227, 0x3FFFFFFFu);
                      _m_prefetchw(v227);
                      v229 = *v227;
                      do
                      {
                        v230 = v229;
                        v229 = _InterlockedCompareExchange(v227, v229 | 0x40000000, v229);
                      }
                      while ( v230 != v229 );
                      v576 = v229;
                    }
                  }
                }
              }
            }
            v231 = v435;
            v232 = v276;
            LatchBase::ReleaseInternal(v435 + 19, (unsigned int)v276);
            if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
            {
              v312 = (unsigned __int8)byte_10317AD4F >> 1;
              if ( (byte_10317AD4F & 2) != 0 )
                BUF::TraceLatchAcquireRelease(v231, 0, v232);
            }
            v257 &= 0xFFFF0000;
            v255 = 0;
LABEL_573:
            v225 = v282;
            v224 = v283;
            v165 = v261;
          }
          v820 = &v483;
          v483 = v225;
          v484 = v224;
          v821 = &v465;
          v465 = v225;
          v466 = v224;
          v254 = 0;
          RecoveryMgr::WaitForRedoLsnToCatchUp(*v169, &v465, 4);
          goto LABEL_407;
        }
        break;
      }
      if ( !a6 )
      {
        v968[0] = 0;
        v968[1] = 0;
        v969 = 0;
        v965 = 0;
        v966 = 0;
        v967 = 0;
        (*(void (__fastcall **)(_QWORD, _DWORD *))(**(_QWORD **)(*((_QWORD *)v59 + 578) + 1736LL) + 40LL))(
          *(_QWORD *)(*((_QWORD *)v59 + 578) + 1736LL),
          v968);
        XdesMgr::GetOldestBeginLsn((XdesMgr *)(*((_QWORD *)v59 + 578) + 6600LL), (struct LSN *)&v965, 1, 0);
        v380 = (volatile signed __int64 *)(*(_QWORD *)(*((_QWORD *)v59 + 578) + 1712LL) + 5376LL);
        v832 = v380;
        v833 = 0;
        v834 = 0;
        v339 = 0;
        v439 = 0;
        v438 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        v490[3] = 256;
        v835 = v380;
        if ( *(_DWORD *)v380 )
        {
          v407 = 0;
LABEL_609:
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84
            && (v490[4] = 88,
                v838 = NtCurrentTeb()->ThreadLocalStoragePointer,
                v241 = v838[SystemThread_TlsIndex],
                v30 = SystemThread_TlsOffset + v241 == 0,
                v242 = SystemThread_TlsOffset + v241,
                v839 = v242,
                !v30)
            && *(_QWORD *)(v242 + 272) == v242 )
          {
            v243 = *(_QWORD *)(v242 + 256);
            v840 = v243;
          }
          else
          {
            v243 = 0;
          }
          v439 = v243;
          if ( v243 )
          {
            v841 = &v384;
            v490[5] = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              v490[6] = QueryPerformanceCounter(&v554);
              v244 = (ReplicaState *)v554.QuadPart;
              v384 = (DBMgr *)v554.QuadPart;
            }
            else
            {
              v244 = MEMORY[0x7FFE0008];
              v555 = MEMORY[0x7FFE0008];
              v384 = MEMORY[0x7FFE0008];
              v243 = v439;
            }
            v842 = v244;
            v339 = v244;
          }
          v490[7] = 2;
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v380, v438);
          else
            Spinlock<148,10,258>::SpinToAcquireOptimistic(v380, v243, v438);
          if ( v243 )
          {
            v843 = &v440;
            v490[8] = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              v490[9] = QueryPerformanceCounter(&v556);
              v245 = (DirtyPageMgr *)v556.QuadPart;
              v440 = (DirtyPageMgr *)v556.QuadPart;
            }
            else
            {
              v245 = MEMORY[0x7FFE0008];
              v557 = MEMORY[0x7FFE0008];
              v440 = MEMORY[0x7FFE0008];
              v243 = v439;
            }
            v844 = &v339;
            v845 = &v440;
            if ( v245 < v339 )
            {
              v246 = 0;
              v279 = 0;
            }
            else
            {
              v246 = v245 - v339;
              v279 = v246;
            }
            v279 = v246;
            v846 = v246;
            v847 = v243 + 3192;
            *(_QWORD *)(v243 + 3192) += v246;
          }
        }
        else
        {
          v836 = _InterlockedCompareExchange64(v380, v438, 0);
          v837 = v836;
          v407 = v836 == 0;
          if ( v836 )
            goto LABEL_609;
        }
        v485 = 0;
        v486 = 0;
        v487 = 0;
        if ( v967 || v965 || (v247 = (const struct LSN *)v968, v966) )
          v247 = (const struct LSN *)&v965;
        RecoveryUnit::SetMaxGCLsn(*((RecoveryUnit **)v281 + 578), v247);
        v248 = (_QWORD *)(*(_QWORD *)(*((_QWORD *)v59 + 578) + 1712LL) + 5376LL);
        v848 = v248;
        v849 = v248;
        v315 = (char)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v249 = rand();
          v250 = (unsigned int)(5 * (v249 / 5));
          if ( v249 == (_DWORD)v250 )
            Spinlock<148,10,258>::UpdateStatSnapshot(v250);
        }
        v850 = v248;
        *v248 = 0;
      }
      AsynchronousDiskPool::~AsynchronousDiskPool((AsynchronousDiskPool *)v964);
      ExcHandler::~ExcHandler((ExcHandler *)v963);
      goto LABEL_647;
    }
    v383 = (volatile signed __int64 *)(*(_QWORD *)(v28 + 1712) + 5376LL);
    v874 = v383;
    v875 = 0;
    v876[2] = 0;
    v419 = 0;
    v417 = 0;
    v416 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    v494 = 256;
    v876[3] = v383;
    if ( *(_DWORD *)v383 )
    {
      v414 = 0;
    }
    else
    {
      v877 = _InterlockedCompareExchange64(v383, v416, 0);
      v583 = v877;
      v414 = v877 == 0;
      if ( !v877 )
      {
LABEL_67:
        LogTruncMgr::GetStartLog((LogTruncMgr *)(*((_QWORD *)v27 + 578) + 2168LL), (struct LSN *)&v442, 0, 1, 0, 0);
        LogTruncMgr::GetStartLogForSLog((LogTruncMgr *)(*((_QWORD *)v27 + 578) + 2168LL), (struct LSN *)&v455);
        v36 = (_QWORD *)(*(_QWORD *)(*((_QWORD *)v27 + 578) + 1712LL) + 5376LL);
        v593 = v36;
        v594 = v36;
        v287 = (char)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v37 = rand();
          v38 = (unsigned int)(5 * (v37 / 5));
          if ( v37 == (_DWORD)v38 )
            Spinlock<148,10,258>::UpdateStatSnapshot(v38);
        }
        v595 = v36;
        *v36 = 0;
        goto LABEL_71;
      }
    }
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84
      && (v520 = 0,
          v495 = 88,
          v584 = NtCurrentTeb()->ThreadLocalStoragePointer,
          v29 = v584[SystemThread_TlsIndex],
          v30 = SystemThread_TlsOffset + v29 == 0,
          v31 = SystemThread_TlsOffset + v29,
          v585 = v31,
          !v30)
      && *(_QWORD *)(v31 + 272) == v31 )
    {
      v32 = *(_QWORD *)(v31 + 256);
      v520 = v32;
    }
    else
    {
      v32 = 0;
    }
    v417 = v32;
    if ( v32 )
    {
      v586 = &v470;
      v496 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v497 = QueryPerformanceCounter(&v521);
        v33 = (DirtyPageMgr *)v521.QuadPart;
        v470 = (DirtyPageMgr *)v521.QuadPart;
      }
      else
      {
        v33 = MEMORY[0x7FFE0008];
        v522 = MEMORY[0x7FFE0008];
        v470 = MEMORY[0x7FFE0008];
        v32 = v417;
      }
      v587 = v33;
      v419 = v33;
    }
    v498 = 2;
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v383, v416);
    else
      Spinlock<148,10,258>::SpinToAcquireOptimistic(v383, v32, v416);
    if ( v32 )
    {
      v588 = &v418;
      v499 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v500 = QueryPerformanceCounter(&v523);
        v34 = (DirtyPageMgr *)v523.QuadPart;
        v418 = (DirtyPageMgr *)v523.QuadPart;
      }
      else
      {
        v34 = MEMORY[0x7FFE0008];
        v524 = MEMORY[0x7FFE0008];
        v418 = MEMORY[0x7FFE0008];
        v32 = v417;
      }
      v589 = &v419;
      v590 = &v418;
      if ( v34 < v419 )
      {
        v35 = 0;
        v344 = 0;
      }
      else
      {
        v35 = v34 - v419;
        v344 = (char *)v35;
      }
      v279 = v35;
      v591 = v35;
      v592 = v32 + 3192;
      *(_QWORD *)(v32 + 3192) += v35;
    }
    goto LABEL_67;
  }
  catch ( SQLError v962 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v876, (const struct SQLError *)v962);
      *((_DWORD *)v558 + 222) = 2;
      ex_raise(18, 23, 16, 2);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v876);
    }
    catch ( ShortStackException )
    {
    }
  }
LABEL_647:
  v251 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v252 = *(struct Worker **)(v251 + 256);
  if ( !v252 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v252 = *(struct Worker **)(v251 + 256);
  }
  if ( *((_DWORD *)v252 + 139) )
    ExceptionPostCatchActions(v252);
  PageRef::~PageRef((PageRef *)&v255);
}

```

## disassembly

```asm
0x101702520  push    rbx
0x101702522  push    rsi
0x101702523  push    rdi
0x101702524  push    r12
0x101702526  push    r13
0x101702528  push    r14
0x10170252a  push    r15
0x10170252c  mov     eax, 1A70h
0x101702531  call    _alloca_probe
0x101702536  sub     rsp, rax
0x101702539  mov     [rsp+1AA8h+var_918], 0FFFFFFFFFFFFFFFEh
0x101702545  mov     rax, cs:__security_cookie
0x10170254c  xor     rax, rsp
0x10170254f  mov     [rsp+1AA8h+var_40], rax
0x101702557  mov     r12, r9
0x10170255a  mov     esi, r8d
0x10170255d  mov     [rsp+1AA8h+var_18DC], r8d
0x101702565  mov     rdi, rdx
0x101702568  mov     [rsp+1AA8h+var_18C8], rdx
0x101702570  mov     [rsp+1AA8h+var_17B8], rcx
0x101702578  mov     rax, [rsp+1AA8h+arg_30]
0x101702580  mov     [rsp+1AA8h+var_1A28], rax
0x101702588  mov     [rsp+1AA8h+var_1238], rdx
0x101702590  xor     ebx, ebx
0x101702592  mov     [rsp+1AA8h+var_19C0], rbx
0x10170259a  mov     [rsp+1AA8h+var_1A48], rbx
0x10170259f  mov     [rsp+1AA8h+var_1A40], bl
0x1017025a3  mov     eax, [rsp+1AA8h+var_1A3C]
0x1017025a7  and     eax, 0FFFF0000h
0x1017025ac  mov     [rsp+1AA8h+var_1A3C], eax
0x1017025b0  and     eax, 0FF00FFFFh
0x1017025b5  mov     [rsp+1AA8h+var_1A3C], eax
0x1017025b9  mov     [rsp+1AA8h+var_1A3C], ebx
0x1017025bd  mov     [rsp+1AA8h+var_118], ebx
0x1017025c4  movups  xmm0, xmmword ptr cs:?x_AG_DB_IdBad@@3U_GUID@@B.Data1; _GUID const x_AG_DB_IdBad ...
0x1017025cb  movups  [rsp+1AA8h+var_114], xmm0
0x1017025d3  mov     [rsp+1AA8h+var_1600], rbx
0x1017025db  mov     [rsp+1AA8h+var_15F8], bx
0x1017025e3  mov     [rsp+1AA8h+var_15A0], rbx
0x1017025eb  mov     [rsp+1AA8h+var_1598], bx
0x1017025f3  mov     [rsp+1AA8h+var_18F0], rbx
0x1017025fb  mov     [rsp+1AA8h+var_18E8], bx
0x101702603  mov     [rsp+1AA8h+var_1848], rbx
0x10170260b  mov     [rsp+1AA8h+var_1840], bx
0x101702613  lea     r15, [rdx+190h]
0x10170261a  lea     rax, [rdx+38h]
0x10170261e  mov     [rsp+1AA8h+var_18D0], rax
0x101702626  lea     r13, [rdx+48h]
0x10170262a  xor     r8d, r8d; bool *
0x10170262d  xor     edx, edx; int
0x10170262f  lea     rcx, [rsp+1AA8h+var_1318]; struct SQLDATEBASE *
0x101702637  call    ?utgettime@@YAXPEAUSQLDATEBASE@@HPEA_N@Z; utgettime(SQLDATEBASE *,int,bool *)
0x10170263c  nop
0x10170263d  xor     edx, edx; unsigned __int16
0x10170263f  mov     [rsp+1AA8h+var_1A80], rbx; struct Worker *
0x101702644  mov     rax, cs:__imp_?hdl_prntbackout@@YAHHHHHPEAD@Z; hdl_prntbackout(int,int,int,int,char *)
0x10170264b  mov     [rsp+1AA8h+var_1A88], rax; int (*)(int, int, int, int, char *)
0x101702650  xor     r9d, r9d; unsigned __int8
0x101702653  xor     r8d, r8d; unsigned __int8
0x101702656  lea     rcx, [rsp+1AA8h+var_2A0]; this
0x10170265e  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x101702663  nop
0x101702664  lea     r14, [rdi+398h]
0x10170266b  mov     [rsp+1AA8h+var_910], r14
0x101702673  mov     rdx, [rsp+1AA8h+var_1A28]
0x10170267b  mov     rdx, [rdx+2B0h]; struct IMemObj *
0x101702682  lea     rcx, [rsp+1AA8h+var_278]; this
0x10170268a  call    ??0AsynchronousDiskPool@@QEAA@PEAVIMemObj@@@Z; AsynchronousDiskPool::AsynchronousDiskPool(IMemObj *)
0x10170268f  nop
0x101702690  lea     rcx, [rsp+1AA8h+var_278]; this
0x101702698  call    ?Init@AsynchronousDiskPool@@QEAAXXZ; AsynchronousDiskPool::Init(void)
0x10170269d  movzx   eax, cs:byte_10317ACC5
0x1017026a4  shr     al, 2
0x1017026a7  mov     [rsp+1AA8h+var_1998], al
0x1017026ae  test    al, 1
0x1017026b0  jz      short loc_1017026C0
0x1017026b2  mov     edx, esi
0x1017026b4  lea     rcx, aDbidDCreatingS; "DBID: [%d] creating sparse files"
0x1017026bb  call    ?LogSystemMetadataNotSentToClient@@YAXPEB_WZZ; LogSystemMetadataNotSentToClient(wchar_t const *,...)
0x1017026c0  lea     rax, [rdi+38h]
0x1017026c4  mov     [rsp+1AA8h+var_908], rax
0x1017026cc  mov     rdi, [rax+8]
0x1017026d0  cmp     rdi, rax
0x1017026d3  cmovz   rdi, rbx
0x1017026d7  mov     [rsp+1AA8h+var_900], rdi
0x1017026df  mov     rsi, [rsp+1AA8h+arg_38]
0x1017026e7  mov     rcx, [rsp+1AA8h+var_18D0]
0x1017026ef  mov     rax, rdi
0x1017026f2  mov     [rsp+1AA8h+var_19C8], rdi
0x1017026fa  test    rax, rax
0x1017026fd  jz      loc_1017027A8
0x101702703  cmp     dword ptr [rdi+390h], 0
0x10170270a  jz      short loc_10170270E
0x10170270c  jmp     short loc_10170278D
0x10170270e  mov     [rsp+1AA8h+var_1478], 2230h
0x101702719  mov     rdx, cs:qword_103172088
0x101702720  mov     [rsp+1AA8h+var_8F8], rdx
0x101702728  mov     byte ptr [rsp+1AA8h+var_1A88], 5
0x10170272d  mov     r9d, 2230h
0x101702733  lea     r8, aSqlNtdbmsStore_188; "sql\\ntdbms\\storeng\\dfs\\manager\\dbm"...
0x10170273a  mov     ecx, 60h ; '`'
0x10170273f  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x101702745  mov     [rsp+1AA8h+var_8F0], rax
0x10170274d  test    rax, rax
0x101702750  jz      short loc_101702764
0x101702752  lea     rdx, [rsp+1AA8h+var_278]; struct AsynchronousDiskPool *
0x10170275a  mov     rcx, rax; this
0x10170275d  call    ??0AsynchronousDiskAction@@QEAA@PEAVAsynchronousDiskPool@@@Z; AsynchronousDiskAction::AsynchronousDiskAction(AsynchronousDiskPool *)
0x101702762  jmp     short loc_101702767
0x101702764  mov     rax, rbx
0x101702767  mov     [rsp+1AA8h+var_8E8], rax
0x10170276f  mov     [rsp+1AA8h+var_8E0], rax
0x101702777  mov     r8, rsi; struct AsynchronousDiskPool *
0x10170277a  mov     rdx, rdi; struct FileDescription *
0x10170277d  mov     rcx, rax; this
0x101702780  call    ?DeferCreating@AsynchronousDiskAction@@QEAAXPEAVFileDescription@@PEAVAsynchronousDiskPool@@@Z; AsynchronousDiskAction::DeferCreating(FileDescription *,AsynchronousDiskPool *)
0x101702785  mov     rcx, [rsp+1AA8h+var_18D0]
0x10170278d  mov     rax, [rdi+8]
0x101702791  mov     rdi, rax
0x101702794  cmp     rax, rcx
0x101702797  cmovz   rdi, rbx
0x10170279b  mov     [rsp+1AA8h+var_8D8], rdi
0x1017027a3  jmp     loc_1017026EF
0x1017027a8  lea     rcx, [rsp+1AA8h+var_278]; this
0x1017027b0  call    ?WaitUntilDone@AsynchronousDiskPool@@QEAAHXZ; AsynchronousDiskPool::WaitUntilDone(void)
0x1017027b5  test    eax, eax
0x1017027b7  jnz     short loc_1017027CD
0x1017027b9  lea     edx, [rax+2]
0x1017027bc  lea     ecx, [rax+12h]
0x1017027bf  lea     r9d, [rax+5]
0x1017027c3  lea     r8d, [rax+19h]
0x1017027c7  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1017027cd  mov     [rsp+1AA8h+var_1978], bx
0x1017027d5  movzx   edi, bx
0x1017027d8  test    di, di
0x1017027db  jnz     short loc_10170281F
0x1017027dd  mov     rax, [rsp+1AA8h+var_1A28]
0x1017027e5  mov     rcx, [rax+1210h]
0x1017027ec  mov     [rsp+1AA8h+var_8D0], rcx
0x1017027f4  test    rcx, rcx
0x1017027f7  jnz     short loc_101702806
0x1017027f9  inc     di
0x1017027fc  mov     [rsp+1AA8h+var_1978], di
0x101702804  jmp     short loc_1017027D8
0x101702806  mov     rcx, [rcx+7A8h]; this
0x10170280d  call    ?BeginSyncWithBulkOps@BackupManager@@QEAAXXZ; BackupManager::BeginSyncWithBulkOps(void)
0x101702812  inc     di
0x101702815  mov     [rsp+1AA8h+var_1978], di
0x10170281d  jmp     short loc_1017027D8
0x10170281f  mov     rsi, [rsp+1AA8h+var_18C8]
0x101702827  mov     byte ptr [rsi+371h], 1
0x10170282e  mov     rdi, [rsp+1AA8h+var_1A28]
0x101702836  cmp     dword ptr [rdi+670h], 302h
0x101702840  jnz     loc_101702A6A
0x101702846  cmp     qword ptr [rdi+2E0h], 0
0x10170284e  jz      loc_101702A6A
0x101702854  mov     r8, r15
0x101702857  mov     edx, 2
0x10170285c  lea     rcx, [rsp+1AA8h+var_11A8]
0x101702864  call    ??0DBStartupTimer@@QEAA@W4DBStartupPhases@@PEAVDatabaseStartupInfo@@@Z; DBStartupTimer::DBStartupTimer(DBStartupPhases,DatabaseStartupInfo *)
0x101702869  nop
0x10170286a  mov     rcx, [rdi+2E0h]; this
0x101702871  call    ?UpdateTruncationLSNs@DBMirroring@@QEAAXXZ; DBMirroring::UpdateTruncationLSNs(void)
0x101702876  mov     rdi, [rdi+2E0h]
0x10170287d  mov     [rsp+1AA8h+var_8C8], rdi
0x101702885  mov     rcx, rsi; this
0x101702888  call    ?EnableDbmLogTruncation@ReplicaState@@QEAAXXZ; ReplicaState::EnableDbmLogTruncation(void)
0x10170288d  mov     [rsi+408h], rdi
0x101702894  test    rdi, rdi
0x101702897  jz      short loc_1017028E9
0x101702899  mov     [rsp+1AA8h+var_8C0], rdi
0x1017028a1  mov     [rsp+1AA8h+var_1388], rbx
0x1017028a9  xor     edx, edx; int
0x1017028ab  mov     rcx, rdi; this
0x1017028ae  call    ?GetLsMgrWithRef@DBMirroring@@QEAAPEAVLsMgr@@H@Z; DBMirroring::GetLsMgrWithRef(int)
0x1017028b3  mov     rdi, rax
0x1017028b6  mov     [rsp+1AA8h+var_8B8], rax
0x1017028be  mov     [rsp+1AA8h+var_1388], rax
0x1017028c6  test    rax, rax
0x1017028c9  jz      short loc_1017028DB
0x1017028cb  lea     rdx, [rsi+410h]; struct LSN *
0x1017028d2  mov     rcx, rax; this
0x1017028d5  call    ?DisableLogTruncation@LsMgr@@QEAAXAEAVLSN@@@Z; LsMgr::DisableLogTruncation(LSN &)
0x1017028da  nop
0x1017028db  test    rdi, rdi
0x1017028de  jz      short loc_1017028E9
0x1017028e0  mov     rax, [rdi]
0x1017028e3  mov     rcx, rdi
0x1017028e6  call    qword ptr [rax+10h]
0x1017028e9  mov     rax, [rsp+1AA8h+var_1A28]
0x1017028f1  mov     rcx, [rax+2E0h]; this
0x1017028f8  mov     [rsp+1AA8h+var_8B0], rcx
0x101702900  mov     [rsp+1AA8h+var_1380], rbx
0x101702908  xor     edx, edx; int
0x10170290a  call    ?GetLsMgrWithRef@DBMirroring@@QEAAPEAVLsMgr@@H@Z; DBMirroring::GetLsMgrWithRef(int)
0x10170290f  mov     rdi, rax
0x101702912  mov     [rsp+1AA8h+var_8A8], rax
0x10170291a  mov     [rsp+1AA8h+var_1380], rax
0x101702922  test    rax, rax
0x101702925  jz      short loc_101702988
0x101702927  mov     [rsp+1AA8h+var_8A0], rax
0x10170292f  lea     rcx, [rax+1AB58h]
0x101702936  mov     [r14], rcx
0x101702939  mov     dword ptr [r14+0Ch], 4
0x101702941  mov     [rsp+1AA8h+var_1470], 4
0x10170294c  mov     [rsp+1AA8h+var_898], rcx
0x101702954  mov     dword ptr [rsp+1AA8h+var_1A68], ebx
0x101702958  mov     [rsp+1AA8h+var_1A70], rbx
0x10170295d  mov     [rsp+1AA8h+var_1A78], rbx
0x101702962  mov     dword ptr [rsp+1AA8h+var_1A80], ebx
0x101702966  mov     [rsp+1AA8h+var_1A88], rbx
0x10170296b  xor     r9d, r9d
0x10170296e  lea     edx, [r9+4]
0x101702972  mov     r8d, 0FFFFFFFFh
0x101702978  call    ?AcquireInternal@LatchBase@@AEAA?AW4AcquireResult@1@W4LATCH_TYPE@1@KPEAVLatchSuspendInfo@@PEAUSubLatchInfo@1@W4Releasor@1@PEA_KPEAVSOS_LsAccessCache@@W4LatchYieldBehavior@1@@Z; LatchBase::AcquireInternal(LatchBase::LATCH_TYPE,ulong,LatchSuspendInfo *,LatchBase::SubLatchInfo *,LatchBase::Releasor,unsigned __int64 *,SOS_LsAccessCache *,LatchBase::LatchYieldBehavior)
0x10170297d  mov     [rsp+1AA8h+var_1468], eax
0x101702984  mov     [r14+8], eax
0x101702988  test    rdi, rdi
0x10170298b  jz      short loc_101702997
0x10170298d  mov     rax, [rdi]
0x101702990  mov     rcx, rdi
0x101702993  call    qword ptr [rax+10h]
0x101702996  nop
0x101702997  lea     rax, [rsp+1AA8h+var_16D8]
0x10170299f  mov     [rsp+1AA8h+var_890], rax
0x1017029a7  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1017029ae  mov     ecx, [rax]
0x1017029b0  mov     [rsp+1AA8h+var_1464], ecx
0x1017029b7  test    ecx, ecx
0x1017029b9  jz      short loc_1017029DA
0x1017029bb  lea     rcx, [rsp+1AA8h+PerformanceCount]; lpPerformanceCount
0x1017029c3  call    cs:__imp_QueryPerformanceCounter
0x1017029c9  mov     [rsp+1AA8h+var_1460], eax
0x1017029d0  mov     rax, qword ptr [rsp+1AA8h+PerformanceCount]
0x1017029d8  jmp     short loc_1017029EA
0x1017029da  mov     rax, ds:7FFE0008h
0x1017029e2  mov     [rsp+1AA8h+var_1370], rax
0x1017029ea  mov     [rsp+1AA8h+var_16D8], rax
0x1017029f2  lea     rcx, [rsp+1AA8h+var_11A8]
0x1017029fa  mov     [rsp+1AA8h+var_888], rcx
0x101702a02  lea     rcx, [rsp+1AA8h+var_16D8]
0x101702a0a  mov     [rsp+1AA8h+var_880], rcx
0x101702a12  mov     rcx, [rsp+1AA8h+var_11A8]
0x101702a1a  cmp     rax, rcx
0x101702a1d  jb      short loc_101702A2C
0x101702a1f  sub     rax, rcx
0x101702a22  mov     [rsp+1AA8h+var_18A8], rax
0x101702a2a  jmp     short loc_101702A37
0x101702a2c  mov     rax, rbx
0x101702a2f  mov     [rsp+1AA8h+var_18A8], rbx
0x101702a37  mov     [rsp+1AA8h+var_878], rax
0x101702a3f  movsxd  r8, [rsp+1AA8h+var_11A0]
0x101702a47  mov     rcx, [rsp+1AA8h+var_1198]
0x101702a4f  add     r8, 0Dh
0x101702a53  lea     r8, [rcx+r8*8]
0x101702a57  mov     [rsp+1AA8h+var_870], r8
0x101702a5f  mov     [rsp+1AA8h+var_868], r8
0x101702a67  add     [r8], rax
0x101702a6a  mov     r14, [rsp+1AA8h+var_1A28]
0x101702a72  mov     rax, [r14+1210h]
0x101702a79  cmp     byte ptr [rax+2050h], 0
0x101702a80  jz      loc_101702E08
0x101702a86  mov     rax, [rax+6B0h]
0x101702a8d  add     rax, 1500h
0x101702a93  mov     [rsp+1AA8h+var_17C0], rax
0x101702a9b  mov     [rsp+1AA8h+var_860], rax
0x101702aa3  mov     [rsp+1AA8h+var_858], rbx
0x101702aab  mov     [rsp+1AA8h+var_840], rbx
0x101702ab3  mov     [rsp+1AA8h+var_16B8], rbx
0x101702abb  mov     [rsp+1AA8h+var_16C8], rbx
0x101702ac3  mov     eax, gs:48h
0x101702acb  mov     ecx, eax
0x101702acd  mov     [rsp+1AA8h+var_16D0], rcx
0x101702ad5  mov     [rsp+1AA8h+var_145C], 100h
0x101702ae0  mov     rax, [rsp+1AA8h+var_17C0]
0x101702ae8  mov     [rsp+1AA8h+var_838], rax
0x101702af0  mov     eax, [rax]
0x101702af2  test    eax, eax
0x101702af4  jnz     short loc_101702B32
0x101702af6  mov     rdx, [rsp+1AA8h+var_16D0]
0x101702afe  mov     rcx, [rsp+1AA8h+var_17C0]
0x101702b06  xor     eax, eax
0x101702b08  lock cmpxchg [rcx], rdx
0x101702b0d  mov     [rsp+1AA8h+var_830], rax
0x101702b15  mov     [rsp+1AA8h+var_1178], rax
0x101702b1d  mov     eax, ebx
0x101702b1f  setz    al
0x101702b22  mov     [rsp+1AA8h+var_16E0], eax
0x101702b29  test    eax, eax
0x101702b2b  jz      short loc_101702B39
0x101702b2d  jmp     loc_101702D56
0x101702b32  mov     [rsp+1AA8h+var_16E0], ebx
0x101702b39  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x101702b40  mov     ecx, [rax]
0x101702b42  and     ecx, 84h
0x101702b48  cmp     cl, 84h
0x101702b4b  jnz     short loc_101702BAE
0x101702b4d  mov     [rsp+1AA8h+var_1368], rbx
0x101702b55  mov     [rsp+1AA8h+var_1458], 58h ; 'X'
0x101702b60  mov     r8, gs:58h
  ... truncated ...
```
