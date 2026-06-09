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
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rdi
  __int64 v42; // rcx
  _DWORD *v43; // rcx
  int v44; // edi
  DirtyPageMgr *v45; // rax
  char *v46; // rax
  unsigned int v47; // r14d
  struct DBTABLE *v48; // rax
  RecoveryUnit *v49; // rdx
  __int64 v50; // r9
  unsigned int v51; // r14d
  _BYTE *v52; // rcx
  RecoveryUnit *v53; // rsi
  struct DBTABLE *v54; // rdi
  char *v55; // r12
  ReplicaState *v56; // r15
  char *v57; // rax
  RecoveryUnit *v58; // r13
  char *v59; // rdi
  __int64 FCB; // rsi
  int v61; // eax
  struct DBTABLE *v62; // r14
  __int64 v63; // rdi
  int v64; // eax
  RecoveryUnit *v65; // rdi
  __int64 v66; // rax
  struct CSessionTraceFlags *v67; // rcx
  struct SEInternalTLS *v68; // rcx
  _QWORD *v69; // r14
  __int64 v70; // rax
  __int64 v71; // rcx
  int *v72; // rdi
  void *v73; // rcx
  signed __int32 v74; // eax
  signed __int32 v75; // ett
  _QWORD *v76; // rdi
  unsigned int v77; // esi
  __int64 v78; // rcx
  int *v79; // rdi
  void *v80; // rcx
  signed __int32 v81; // eax
  signed __int32 v82; // ett
  signed __int32 v83; // eax
  signed __int32 v84; // ett
  _QWORD *v85; // rdi
  unsigned int v86; // esi
  _QWORD *v87; // rax
  unsigned int v88; // r8d
  __int64 v89; // rdx
  _DWORD *v90; // rcx
  _QWORD *v91; // r9
  __int64 v92; // rax
  unsigned int v93; // edx
  _QWORD *v94; // rcx
  unsigned int *v95; // r8
  __int64 v96; // rdx
  __int64 v97; // r11
  char v98; // al
  char v99; // al
  LSN *v100; // rsi
  _DWORD *v101; // rdi
  int v102; // eax
  int v103; // ecx
  LSN *v104; // rdx
  unsigned __int16 v105; // di
  __int64 v106; // r11
  char v107; // al
  char v108; // al
  unsigned __int16 v109; // r11
  RecoveryUnit *v111; // rdi
  __int64 v112; // r10
  __int64 v113; // rax
  __int64 v114; // rax
  __int64 v115; // rax
  int *v116; // rdx
  __int64 v117; // rcx
  DWORD v118; // ecx
  _DWORD **v119; // rax
  __int64 v120; // rdx
  __int64 v121; // r11
  char v122; // al
  char v123; // al
  __int16 v124; // r11
  __int64 v125; // xmm1_8
  __int64 v126; // rcx
  int *v127; // rdi
  void *v128; // rcx
  signed __int32 v129; // eax
  signed __int32 v130; // ett
  _QWORD *v131; // rdi
  unsigned int v132; // esi
  __int64 v133; // rcx
  int *v134; // rdi
  void *v135; // rcx
  signed __int32 v136; // eax
  signed __int32 v137; // ett
  _QWORD *v138; // rdi
  unsigned int v139; // esi
  __int64 v140; // rdi
  __int64 v141; // rdi
  __int64 v142; // rdi
  DirtyPageMgr *v143; // rax
  DirtyPageMgr *v144; // rax
  __int64 v145; // rax
  _QWORD *v146; // rdx
  int v147; // r8d
  __int64 v148; // rdi
  __int64 v149; // rdi
  __int64 v150; // rdi
  DirtyPageMgr *v151; // rax
  DirtyPageMgr *v152; // rax
  __int64 v153; // rax
  _QWORD *v154; // rdi
  int v155; // r8d
  __int64 v156; // r15
  char *v157; // rax
  char *v158; // rdi
  __int64 v159; // rax
  int v160; // ecx
  struct DBTABLE *v161; // rdi
  RecoveryUnit *v162; // rdi
  __int64 v163; // rax
  struct CSessionTraceFlags *v164; // rcx
  struct SEInternalTLS *v165; // rcx
  _QWORD *v166; // r14
  __int64 v167; // rax
  __int64 v168; // rcx
  int *v169; // rdi
  void *v170; // rcx
  signed __int32 v171; // eax
  signed __int32 v172; // ett
  _QWORD *v173; // rdi
  unsigned int v174; // esi
  __int64 v175; // rcx
  int *v176; // rdi
  void *v177; // rcx
  signed __int32 v178; // eax
  signed __int32 v179; // ett
  signed __int32 v180; // eax
  signed __int32 v181; // ett
  _QWORD *v182; // rdi
  unsigned int v183; // esi
  _QWORD *v184; // rax
  unsigned int v185; // r8d
  __int64 v186; // rdx
  _DWORD *v187; // rcx
  _QWORD *v188; // r9
  __int64 v189; // rax
  unsigned int v190; // edx
  _QWORD *v191; // rcx
  unsigned int *v192; // r8
  __int64 v193; // rdx
  __int64 v194; // r11
  char v195; // al
  char v196; // al
  LSN *v197; // rsi
  _DWORD *v198; // rdi
  int v199; // eax
  int v200; // ecx
  LSN *v201; // rdx
  unsigned __int16 v202; // di
  __int64 v203; // r11
  char v204; // al
  char v205; // al
  unsigned __int16 v206; // r11
  RecoveryUnit *v208; // rdi
  __int64 v209; // r10
  __int64 v210; // rax
  __int64 v211; // rax
  __int64 v212; // rax
  int *v213; // rdx
  __int64 v214; // rcx
  DWORD v215; // ecx
  _DWORD **v216; // rax
  __int64 v217; // rdx
  __int64 v218; // r11
  char v219; // al
  char v220; // al
  __int16 v221; // r11
  __int64 v222; // xmm1_8
  __int64 v223; // rcx
  int *v224; // rdi
  void *v225; // rcx
  signed __int32 v226; // eax
  signed __int32 v227; // ett
  _QWORD *v228; // rdi
  unsigned int v229; // esi
  __int64 v230; // rax
  __int64 v231; // rcx
  int *v232; // rdi
  void *v233; // rcx
  signed __int32 v234; // eax
  signed __int32 v235; // ett
  _QWORD *v236; // rdi
  unsigned int v237; // esi
  __int64 v238; // rdi
  __int64 v239; // rdi
  __int64 v240; // rdi
  ReplicaState *v241; // rax
  DirtyPageMgr *v242; // rax
  __int64 v243; // rax
  const struct LSN *v244; // rdx
  _QWORD *v245; // rdi
  int v246; // r8d
  __int64 v247; // rbx
  struct Worker *v248; // rcx
  signed __int32 v249[8]; // [rsp+0h] [rbp-1AA8h] BYREF
  struct LSN *v250; // [rsp+20h] [rbp-1A88h]
  _QWORD *v251; // [rsp+60h] [rbp-1A48h] BYREF
  char v252; // [rsp+68h] [rbp-1A40h]
  int v253; // [rsp+6Ch] [rbp-1A3Ch]
  unsigned int v254; // [rsp+70h] [rbp-1A38h]
  int v255; // [rsp+78h] [rbp-1A30h] BYREF
  __int16 v256; // [rsp+7Ch] [rbp-1A2Ch]
  RecoveryUnit *v257; // [rsp+80h] [rbp-1A28h]
  char v258; // [rsp+88h] [rbp-1A20h]
  char v259; // [rsp+89h] [rbp-1A1Fh]
  char v260; // [rsp+8Ah] [rbp-1A1Eh]
  char v261; // [rsp+8Bh] [rbp-1A1Dh]
  char v262; // [rsp+8Ch] [rbp-1A1Ch]
  char v263; // [rsp+8Dh] [rbp-1A1Bh]
  char v264; // [rsp+8Eh] [rbp-1A1Ah]
  char v265; // [rsp+8Fh] [rbp-1A19h]
  int v266; // [rsp+90h] [rbp-1A18h]
  int v267; // [rsp+98h] [rbp-1A10h]
  int v268; // [rsp+A0h] [rbp-1A08h]
  int v269; // [rsp+A8h] [rbp-1A00h]
  int v270; // [rsp+B0h] [rbp-19F8h]
  int v271; // [rsp+B8h] [rbp-19F0h]
  int v272; // [rsp+C0h] [rbp-19E8h]
  int v273; // [rsp+C8h] [rbp-19E0h]
  RecoveryUnit *v274; // [rsp+D0h] [rbp-19D8h]
  __int64 v275; // [rsp+D8h] [rbp-19D0h]
  char *v276; // [rsp+E0h] [rbp-19C8h]
  struct DBTABLE *v277; // [rsp+E8h] [rbp-19C0h]
  __int64 v278; // [rsp+F0h] [rbp-19B8h] BYREF
  __int16 v279; // [rsp+F8h] [rbp-19B0h]
  __int64 v280; // [rsp+100h] [rbp-19A8h] BYREF
  __int16 v281; // [rsp+108h] [rbp-19A0h]
  char v282; // [rsp+110h] [rbp-1998h]
  char v283; // [rsp+111h] [rbp-1997h]
  char v284; // [rsp+112h] [rbp-1996h]
  bool v285; // [rsp+113h] [rbp-1995h]
  char v287; // [rsp+115h] [rbp-1993h]
  bool v288; // [rsp+116h] [rbp-1992h]
  char v289; // [rsp+117h] [rbp-1991h]
  char v290; // [rsp+118h] [rbp-1990h]
  char v291; // [rsp+119h] [rbp-198Fh]
  char v292; // [rsp+11Ah] [rbp-198Eh]
  char v293; // [rsp+11Bh] [rbp-198Dh]
  char v294; // [rsp+11Ch] [rbp-198Ch]
  char v295; // [rsp+11Dh] [rbp-198Bh]
  char v296; // [rsp+11Eh] [rbp-198Ah]
  char v297; // [rsp+11Fh] [rbp-1989h]
  char v298; // [rsp+120h] [rbp-1988h]
  char v299; // [rsp+121h] [rbp-1987h]
  char v300; // [rsp+122h] [rbp-1986h]
  bool v301; // [rsp+123h] [rbp-1985h]
  char v302; // [rsp+124h] [rbp-1984h]
  char v303; // [rsp+125h] [rbp-1983h]
  char v304; // [rsp+126h] [rbp-1982h]
  char v305; // [rsp+127h] [rbp-1981h]
  char v306; // [rsp+128h] [rbp-1980h]
  char v307; // [rsp+129h] [rbp-197Fh]
  char v308; // [rsp+12Ah] [rbp-197Eh]
  char v309; // [rsp+12Bh] [rbp-197Dh]
  char v310; // [rsp+12Ch] [rbp-197Ch]
  char v311; // [rsp+12Dh] [rbp-197Bh]
  __int16 v312; // [rsp+130h] [rbp-1978h]
  __int16 v313; // [rsp+138h] [rbp-1970h]
  __int16 v314; // [rsp+140h] [rbp-1968h]
  __int16 v315; // [rsp+148h] [rbp-1960h]
  __int16 v316; // [rsp+150h] [rbp-1958h]
  __int16 v317; // [rsp+158h] [rbp-1950h]
  __int16 v318; // [rsp+160h] [rbp-1948h]
  __int16 v319; // [rsp+168h] [rbp-1940h]
  __int16 v320; // [rsp+170h] [rbp-1938h]
  __int16 v321; // [rsp+178h] [rbp-1930h]
  __int16 v322; // [rsp+180h] [rbp-1928h]
  __int16 v323; // [rsp+188h] [rbp-1920h]
  __int16 v324; // [rsp+190h] [rbp-1918h]
  __int16 v325; // [rsp+198h] [rbp-1910h]
  __int16 v326; // [rsp+1A0h] [rbp-1908h]
  __int16 v327; // [rsp+1A8h] [rbp-1900h]
  __int16 v328; // [rsp+1B0h] [rbp-18F8h]
  __int64 v329; // [rsp+1B8h] [rbp-18F0h] BYREF
  __int16 v330; // [rsp+1C0h] [rbp-18E8h]
  char v331; // [rsp+1C8h] [rbp-18E0h]
  unsigned int v332; // [rsp+1CCh] [rbp-18DCh]
  __int16 v333; // [rsp+1D0h] [rbp-18D8h]
  __int64 v334; // [rsp+1D8h] [rbp-18D0h]
  ReplicaState *v335; // [rsp+1E0h] [rbp-18C8h] BYREF
  LSN v336; // [rsp+1E8h] [rbp-18C0h]
  DWORD LowPart; // [rsp+1F0h] [rbp-18B8h]
  LSN v338; // [rsp+1F4h] [rbp-18B4h]
  DWORD v339; // [rsp+1FCh] [rbp-18ACh]
  char *v340; // [rsp+200h] [rbp-18A8h]
  int v341; // [rsp+208h] [rbp-18A0h] BYREF
  unsigned int v342; // [rsp+20Ch] [rbp-189Ch] BYREF
  int v343; // [rsp+210h] [rbp-1898h]
  int v344; // [rsp+214h] [rbp-1894h]
  unsigned int v345; // [rsp+218h] [rbp-1890h] BYREF
  int v346; // [rsp+21Ch] [rbp-188Ch]
  int v347; // [rsp+220h] [rbp-1888h]
  __int64 v348; // [rsp+224h] [rbp-1884h]
  int v349; // [rsp+22Ch] [rbp-187Ch]
  __int64 v350; // [rsp+230h] [rbp-1878h]
  int v351; // [rsp+238h] [rbp-1870h]
  __int64 v352; // [rsp+240h] [rbp-1868h] BYREF
  unsigned __int16 v353; // [rsp+248h] [rbp-1860h]
  LSN v354; // [rsp+250h] [rbp-1858h] BYREF
  unsigned __int16 v355; // [rsp+258h] [rbp-1850h]
  __int64 v356; // [rsp+260h] [rbp-1848h] BYREF
  __int16 v357; // [rsp+268h] [rbp-1840h]
  __int64 v358; // [rsp+270h] [rbp-1838h] BYREF
  unsigned __int16 v359; // [rsp+278h] [rbp-1830h]
  LSN v360; // [rsp+280h] [rbp-1828h] BYREF
  unsigned __int16 v361; // [rsp+288h] [rbp-1820h]
  int v362; // [rsp+290h] [rbp-1818h] BYREF
  __int16 v363; // [rsp+294h] [rbp-1814h]
  int v364; // [rsp+298h] [rbp-1810h] BYREF
  __int16 v365; // [rsp+29Ch] [rbp-180Ch]
  int v366; // [rsp+2A0h] [rbp-1808h] BYREF
  __int16 v367; // [rsp+2A4h] [rbp-1804h]
  int v368; // [rsp+2A8h] [rbp-1800h] BYREF
  __int16 v369; // [rsp+2ACh] [rbp-17FCh]
  int v370; // [rsp+2B0h] [rbp-17F8h] BYREF
  __int16 v371; // [rsp+2B4h] [rbp-17F4h]
  int v372; // [rsp+2B8h] [rbp-17F0h] BYREF
  __int16 v373; // [rsp+2BCh] [rbp-17ECh]
  struct SEInternalTLS *SETLSFromTlsMaybeNull; // [rsp+2C0h] [rbp-17E8h]
  volatile signed __int64 *v375; // [rsp+2C8h] [rbp-17E0h]
  volatile signed __int64 *v376; // [rsp+2D0h] [rbp-17D8h]
  volatile signed __int64 *v377; // [rsp+2D8h] [rbp-17D0h]
  struct SEInternalTLS *v378; // [rsp+2E0h] [rbp-17C8h]
  volatile signed __int64 *v379; // [rsp+2E8h] [rbp-17C0h]
  DBMgr *v380; // [rsp+2F0h] [rbp-17B8h] BYREF
  int v381; // [rsp+2F8h] [rbp-17B0h]
  int v382; // [rsp+300h] [rbp-17A8h]
  int v383; // [rsp+308h] [rbp-17A0h]
  unsigned int v384; // [rsp+310h] [rbp-1798h]
  unsigned int v385; // [rsp+314h] [rbp-1794h]
  int v386; // [rsp+318h] [rbp-1790h]
  int v387; // [rsp+320h] [rbp-1788h]
  int v388; // [rsp+328h] [rbp-1780h]
  int v389; // [rsp+330h] [rbp-1778h]
  int v390; // [rsp+338h] [rbp-1770h]
  int v391; // [rsp+340h] [rbp-1768h]
  int v392; // [rsp+348h] [rbp-1760h]
  unsigned int v393; // [rsp+350h] [rbp-1758h]
  unsigned int v394; // [rsp+354h] [rbp-1754h]
  unsigned int v395; // [rsp+358h] [rbp-1750h] BYREF
  int v396; // [rsp+35Ch] [rbp-174Ch] BYREF
  int v397; // [rsp+360h] [rbp-1748h]
  int v398; // [rsp+368h] [rbp-1740h]
  int v399; // [rsp+370h] [rbp-1738h]
  int v400; // [rsp+378h] [rbp-1730h]
  int v401; // [rsp+380h] [rbp-1728h]
  int v402; // [rsp+388h] [rbp-1720h]
  BOOL v403; // [rsp+390h] [rbp-1718h]
  int v404; // [rsp+398h] [rbp-1710h]
  BOOL v405; // [rsp+3A0h] [rbp-1708h]
  int v406; // [rsp+3A8h] [rbp-1700h]
  int v407; // [rsp+3B0h] [rbp-16F8h]
  int v408; // [rsp+3B8h] [rbp-16F0h]
  int v409; // [rsp+3C0h] [rbp-16E8h]
  BOOL v410; // [rsp+3C8h] [rbp-16E0h]
  DirtyPageMgr *v411; // [rsp+3D0h] [rbp-16D8h] BYREF
  signed __int64 v412; // [rsp+3D8h] [rbp-16D0h]
  __int64 v413; // [rsp+3E0h] [rbp-16C8h]
  DirtyPageMgr *v414; // [rsp+3E8h] [rbp-16C0h] BYREF
  DirtyPageMgr *v415; // [rsp+3F0h] [rbp-16B8h] BYREF
  DirtyPageMgr *v416; // [rsp+3F8h] [rbp-16B0h] BYREF
  _QWORD *v417; // [rsp+400h] [rbp-16A8h]
  _QWORD *v418; // [rsp+408h] [rbp-16A0h]
  _QWORD *v419; // [rsp+410h] [rbp-1698h]
  _QWORD *v420; // [rsp+418h] [rbp-1690h]
  signed __int64 UniqueThread_low; // [rsp+420h] [rbp-1688h]
  int v422; // [rsp+428h] [rbp-1680h]
  DirtyPageMgr *v423; // [rsp+430h] [rbp-1678h] BYREF
  DirtyPageMgr *v424; // [rsp+438h] [rbp-1670h] BYREF
  signed __int64 v425; // [rsp+440h] [rbp-1668h]
  __int64 v426; // [rsp+448h] [rbp-1660h]
  DirtyPageMgr *v427; // [rsp+450h] [rbp-1658h] BYREF
  DirtyPageMgr *v428; // [rsp+458h] [rbp-1650h] BYREF
  _QWORD *v429; // [rsp+460h] [rbp-1648h]
  _QWORD *v430; // [rsp+468h] [rbp-1640h]
  _QWORD *v431; // [rsp+470h] [rbp-1638h]
  __int64 v432; // [rsp+478h] [rbp-1630h]
  _QWORD *v433; // [rsp+480h] [rbp-1628h]
  signed __int64 v434; // [rsp+488h] [rbp-1620h]
  __int64 v435; // [rsp+490h] [rbp-1618h]
  DirtyPageMgr *v436; // [rsp+498h] [rbp-1610h] BYREF
  unsigned __int16 v437; // [rsp+4A0h] [rbp-1608h]
  __int64 v438; // [rsp+4A8h] [rbp-1600h] BYREF
  __int16 v439; // [rsp+4B0h] [rbp-15F8h]
  __int16 v440; // [rsp+4B8h] [rbp-15F0h]
  unsigned __int16 v441; // [rsp+4C0h] [rbp-15E8h]
  int v442; // [rsp+4C8h] [rbp-15E0h] BYREF
  unsigned int v443; // [rsp+4CCh] [rbp-15DCh] BYREF
  BOOL v444; // [rsp+4D0h] [rbp-15D8h]
  __int16 v445; // [rsp+4D8h] [rbp-15D0h]
  unsigned __int16 v446; // [rsp+4E0h] [rbp-15C8h]
  unsigned __int16 v447; // [rsp+4E8h] [rbp-15C0h]
  __int16 v448; // [rsp+4F0h] [rbp-15B8h]
  __int16 v449; // [rsp+4F8h] [rbp-15B0h]
  __int64 v450; // [rsp+500h] [rbp-15A8h]
  __int64 v451; // [rsp+508h] [rbp-15A0h] BYREF
  __int16 v452; // [rsp+510h] [rbp-1598h]
  int v453; // [rsp+518h] [rbp-1590h]
  int v454; // [rsp+520h] [rbp-1588h]
  int v455; // [rsp+528h] [rbp-1580h]
  int v456; // [rsp+530h] [rbp-1578h]
  int v457; // [rsp+538h] [rbp-1570h] BYREF
  __int64 v458; // [rsp+540h] [rbp-1568h]
  __int64 v459; // [rsp+548h] [rbp-1560h] BYREF
  __int16 v460; // [rsp+550h] [rbp-1558h]
  __int64 v461; // [rsp+558h] [rbp-1550h] BYREF
  __int16 v462; // [rsp+560h] [rbp-1548h]
  unsigned int *v463; // [rsp+568h] [rbp-1540h]
  LSN *v464; // [rsp+570h] [rbp-1538h]
  unsigned int *v465; // [rsp+578h] [rbp-1530h]
  DirtyPageMgr *v466; // [rsp+580h] [rbp-1528h] BYREF
  DirtyPageMgr *v467; // [rsp+588h] [rbp-1520h] BYREF
  DirtyPageMgr *v468; // [rsp+590h] [rbp-1518h] BYREF
  LSN *v469; // [rsp+598h] [rbp-1510h]
  LSN v470; // [rsp+5A0h] [rbp-1508h] BYREF
  __int16 v471; // [rsp+5A8h] [rbp-1500h]
  __int64 v472; // [rsp+5B0h] [rbp-14F8h] BYREF
  __int16 v473; // [rsp+5B8h] [rbp-14F0h]
  int v474; // [rsp+5C0h] [rbp-14E8h]
  int v475; // [rsp+5C4h] [rbp-14E4h]
  __int16 v476; // [rsp+5C8h] [rbp-14E0h]
  LSN v477; // [rsp+5D0h] [rbp-14D8h] BYREF
  __int16 v478; // [rsp+5D8h] [rbp-14D0h]
  __int64 v479; // [rsp+5E0h] [rbp-14C8h] BYREF
  __int16 v480; // [rsp+5E8h] [rbp-14C0h]
  int v481; // [rsp+5F0h] [rbp-14B8h]
  int v482; // [rsp+5F4h] [rbp-14B4h]
  __int16 v483; // [rsp+5F8h] [rbp-14B0h]
  int v484; // [rsp+600h] [rbp-14A8h]
  int v485; // [rsp+604h] [rbp-14A4h]
  DWORD v486[14]; // [rsp+608h] [rbp-14A0h] BYREF
  int v487; // [rsp+640h] [rbp-1468h]
  int v488; // [rsp+644h] [rbp-1464h]
  BOOL v489; // [rsp+648h] [rbp-1460h]
  int v490; // [rsp+64Ch] [rbp-145Ch]
  int v491; // [rsp+650h] [rbp-1458h]
  int v492; // [rsp+654h] [rbp-1454h]
  BOOL v493; // [rsp+658h] [rbp-1450h]
  int v494; // [rsp+65Ch] [rbp-144Ch]
  int v495; // [rsp+660h] [rbp-1448h]
  BOOL v496; // [rsp+664h] [rbp-1444h]
  int v497; // [rsp+668h] [rbp-1440h]
  int v498; // [rsp+66Ch] [rbp-143Ch]
  int Lock; // [rsp+670h] [rbp-1438h]
  int v500; // [rsp+678h] [rbp-1430h]
  int v501; // [rsp+680h] [rbp-1428h]
  BOOL v502; // [rsp+684h] [rbp-1424h]
  unsigned int v503; // [rsp+688h] [rbp-1420h]
  unsigned int v504; // [rsp+68Ch] [rbp-141Ch]
  int v505; // [rsp+690h] [rbp-1418h]
  int v506; // [rsp+694h] [rbp-1414h]
  int v507; // [rsp+698h] [rbp-1410h]
  DWORD flOldProtect[4]; // [rsp+69Ch] [rbp-140Ch] BYREF
  DWORD v509[11]; // [rsp+6ACh] [rbp-13FCh] BYREF
  DWORD v510[4]; // [rsp+6D8h] [rbp-13D0h] BYREF
  DWORD v511[14]; // [rsp+6E8h] [rbp-13C0h] BYREF
  LsMgr *v512; // [rsp+720h] [rbp-1388h]
  struct LsMgr *v513; // [rsp+728h] [rbp-1380h]
  LARGE_INTEGER PerformanceCount; // [rsp+730h] [rbp-1378h] BYREF
  DirtyPageMgr *v515; // [rsp+738h] [rbp-1370h]
  __int64 v516; // [rsp+740h] [rbp-1368h]
  LARGE_INTEGER v517; // [rsp+748h] [rbp-1360h] BYREF
  DirtyPageMgr *v518; // [rsp+750h] [rbp-1358h]
  LARGE_INTEGER v519; // [rsp+758h] [rbp-1350h] BYREF
  DirtyPageMgr *v520; // [rsp+760h] [rbp-1348h]
  __int64 v521; // [rsp+768h] [rbp-1340h]
  __int64 v522; // [rsp+770h] [rbp-1338h]
  __int64 v523; // [rsp+778h] [rbp-1330h]
  LARGE_INTEGER v524; // [rsp+780h] [rbp-1328h] BYREF
  DirtyPageMgr *v525; // [rsp+788h] [rbp-1320h]
  __int64 v526; // [rsp+790h] [rbp-1318h] BYREF
  struct CSessionTraceFlags *v527; // [rsp+798h] [rbp-1310h]
  __int64 v528; // [rsp+7A0h] [rbp-1308h]
  char *v529; // [rsp+7A8h] [rbp-1300h]
  int *v530; // [rsp+7B0h] [rbp-12F8h]
  LONG *p_HighPart; // [rsp+7B8h] [rbp-12F0h]
  BOOL v532; // [rsp+7C0h] [rbp-12E8h]
  __int64 v533; // [rsp+7C8h] [rbp-12E0h]
  LARGE_INTEGER v534; // [rsp+7D0h] [rbp-12D8h] BYREF
  DirtyPageMgr *v535; // [rsp+7D8h] [rbp-12D0h]
  LARGE_INTEGER v536; // [rsp+7E0h] [rbp-12C8h] BYREF
  DirtyPageMgr *v537; // [rsp+7E8h] [rbp-12C0h]
  __int64 v538; // [rsp+7F0h] [rbp-12B8h]
  LARGE_INTEGER v539; // [rsp+7F8h] [rbp-12B0h] BYREF
  DirtyPageMgr *v540; // [rsp+800h] [rbp-12A8h]
  LARGE_INTEGER v541; // [rsp+808h] [rbp-12A0h] BYREF
  DirtyPageMgr *v542; // [rsp+810h] [rbp-1298h]
  __int64 v543; // [rsp+818h] [rbp-1290h]
  struct CSessionTraceFlags *v544; // [rsp+820h] [rbp-1288h]
  __int64 v545; // [rsp+828h] [rbp-1280h]
  char *v546; // [rsp+830h] [rbp-1278h]
  int *v547; // [rsp+838h] [rbp-1270h]
  LONG *v548; // [rsp+840h] [rbp-1268h]
  __int64 v549; // [rsp+848h] [rbp-1260h]
  LARGE_INTEGER v550; // [rsp+850h] [rbp-1258h] BYREF
  DirtyPageMgr *v551; // [rsp+858h] [rbp-1250h]
  LARGE_INTEGER v552; // [rsp+860h] [rbp-1248h] BYREF
  DirtyPageMgr *v553; // [rsp+868h] [rbp-1240h]
  _QWORD *v554; // [rsp+870h] [rbp-1238h]
  int v555; // [rsp+880h] [rbp-1228h]
  int v556; // [rsp+884h] [rbp-1224h]
  BOOL v557; // [rsp+888h] [rbp-1220h]
  char v558[4]; // [rsp+88Ch] [rbp-121Ch] BYREF
  int v559; // [rsp+890h] [rbp-1218h]
  int v560; // [rsp+894h] [rbp-1214h]
  int v561; // [rsp+898h] [rbp-1210h]
  DWORD v562[4]; // [rsp+89Ch] [rbp-120Ch] BYREF
  DWORD v563[11]; // [rsp+8ACh] [rbp-11FCh] BYREF
  DWORD v564; // [rsp+8D8h] [rbp-11D0h] BYREF
  __int64 v565; // [rsp+8DCh] [rbp-11CCh]
  __int16 v566; // [rsp+8E4h] [rbp-11C4h]
  __int16 v567; // [rsp+8E6h] [rbp-11C2h]
  __int64 v568; // [rsp+8E8h] [rbp-11C0h]
  __int16 v569; // [rsp+8F0h] [rbp-11B8h]
  __int16 v570; // [rsp+8F2h] [rbp-11B6h]
  signed __int32 v571; // [rsp+8F4h] [rbp-11B4h]
  signed __int32 v572; // [rsp+8F8h] [rbp-11B0h]
  unsigned __int64 v573; // [rsp+900h] [rbp-11A8h] BYREF
  int v574; // [rsp+908h] [rbp-11A0h]
  __int64 v575; // [rsp+910h] [rbp-1198h]
  unsigned __int64 v576; // [rsp+918h] [rbp-1190h] BYREF
  int v577; // [rsp+920h] [rbp-1188h]
  __int64 v578; // [rsp+928h] [rbp-1180h]
  signed __int64 v579; // [rsp+930h] [rbp-1178h]
  _QWORD *v580; // [rsp+938h] [rbp-1170h]
  __int64 v581; // [rsp+940h] [rbp-1168h]
  DirtyPageMgr **v582; // [rsp+948h] [rbp-1160h]
  DirtyPageMgr *v583; // [rsp+950h] [rbp-1158h]
  DirtyPageMgr **v584; // [rsp+958h] [rbp-1150h]
  DirtyPageMgr **v585; // [rsp+960h] [rbp-1148h]
  DirtyPageMgr **v586; // [rsp+968h] [rbp-1140h]
  __int64 v587; // [rsp+970h] [rbp-1138h]
  __int64 v588; // [rsp+978h] [rbp-1130h]
  _QWORD *v589; // [rsp+980h] [rbp-1128h]
  _QWORD *v590; // [rsp+988h] [rbp-1120h]
  _QWORD *v591; // [rsp+990h] [rbp-1118h]
  __int64 v592; // [rsp+998h] [rbp-1110h]
  __int64 v593; // [rsp+9A0h] [rbp-1108h]
  __int64 v594; // [rsp+9A8h] [rbp-1100h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+9B0h] [rbp-10F8h]
  __int64 v596; // [rsp+9B8h] [rbp-10F0h]
  __int64 v597; // [rsp+9C0h] [rbp-10E8h]
  int *v598; // [rsp+9C8h] [rbp-10E0h]
  _DWORD *v599; // [rsp+9D0h] [rbp-10D8h]
  __int64 v600; // [rsp+9D8h] [rbp-10D0h]
  __int64 v601; // [rsp+9E0h] [rbp-10C8h]
  DirtyPageMgr **v602; // [rsp+9E8h] [rbp-10C0h]
  unsigned __int64 *v603; // [rsp+9F0h] [rbp-10B8h]
  DirtyPageMgr **v604; // [rsp+9F8h] [rbp-10B0h]
  char *v605; // [rsp+A00h] [rbp-10A8h]
  _QWORD *v606; // [rsp+A08h] [rbp-10A0h]
  _QWORD *v607; // [rsp+A10h] [rbp-1098h]
  int *v608; // [rsp+A18h] [rbp-1090h]
  char *v609; // [rsp+A20h] [rbp-1088h]
  char *v610; // [rsp+A28h] [rbp-1080h]
  __int64 v611; // [rsp+A30h] [rbp-1078h]
  __int64 v612; // [rsp+A38h] [rbp-1070h]
  __int64 v613; // [rsp+A40h] [rbp-1068h]
  _QWORD *v614; // [rsp+A48h] [rbp-1060h]
  _QWORD *v615; // [rsp+A50h] [rbp-1058h]
  _QWORD *v616; // [rsp+A58h] [rbp-1050h]
  __int64 v617; // [rsp+A60h] [rbp-1048h]
  __int64 v618; // [rsp+A68h] [rbp-1040h]
  struct CSessionTraceFlags *v619; // [rsp+A70h] [rbp-1038h]
  _QWORD *v620; // [rsp+A78h] [rbp-1030h]
  __int64 v621; // [rsp+A80h] [rbp-1028h]
  __int64 v622; // [rsp+A88h] [rbp-1020h]
  __int64 v623; // [rsp+A90h] [rbp-1018h]
  __int64 v624; // [rsp+A98h] [rbp-1010h]
  char *v625; // [rsp+AA0h] [rbp-1008h]
  char *v626; // [rsp+AA8h] [rbp-1000h]
  char *v627; // [rsp+AB0h] [rbp-FF8h]
  __int64 v628; // [rsp+AB8h] [rbp-FF0h]
  __int64 v629; // [rsp+AC0h] [rbp-FE8h]
  __int64 v630; // [rsp+AC8h] [rbp-FE0h]
  char *v631; // [rsp+AD0h] [rbp-FD8h]
  char *v632; // [rsp+AD8h] [rbp-FD0h]
  char *v633; // [rsp+AE0h] [rbp-FC8h]
  __int64 v634; // [rsp+AE8h] [rbp-FC0h]
  __int64 v635; // [rsp+AF0h] [rbp-FB8h]
  __int64 v636; // [rsp+AF8h] [rbp-FB0h]
  __int64 v637; // [rsp+B00h] [rbp-FA8h]
  _DWORD *v638; // [rsp+B08h] [rbp-FA0h]
  _QWORD *v639; // [rsp+B10h] [rbp-F98h]
  __int64 v640; // [rsp+B18h] [rbp-F90h]
  __int64 v641; // [rsp+B20h] [rbp-F88h]
  int *v642; // [rsp+B28h] [rbp-F80h]
  __int64 v643; // [rsp+B30h] [rbp-F78h]
  __int64 *v644; // [rsp+B38h] [rbp-F70h]
  _DWORD *v645; // [rsp+B40h] [rbp-F68h]
  _QWORD *v646; // [rsp+B48h] [rbp-F60h]
  __int64 v647; // [rsp+B50h] [rbp-F58h]
  __int64 v648; // [rsp+B58h] [rbp-F50h]
  __int64 v649; // [rsp+B60h] [rbp-F48h]
  __int64 v650; // [rsp+B68h] [rbp-F40h]
  __int64 v651; // [rsp+B70h] [rbp-F38h]
  _DWORD *v652; // [rsp+B78h] [rbp-F30h]
  __int64 v653; // [rsp+B80h] [rbp-F28h]
  int *v654; // [rsp+B88h] [rbp-F20h]
  __int64 v655; // [rsp+B90h] [rbp-F18h]
  __int64 v656; // [rsp+B98h] [rbp-F10h]
  _WORD *v657; // [rsp+BA0h] [rbp-F08h]
  int **v658; // [rsp+BA8h] [rbp-F00h]
  GUID **v659; // [rsp+BB0h] [rbp-EF8h]
  GUID **v660; // [rsp+BB8h] [rbp-EF0h]
  wchar_t **v661; // [rsp+BC0h] [rbp-EE8h]
  wchar_t **v662; // [rsp+BC8h] [rbp-EE0h]
  __int64 *v663; // [rsp+BD0h] [rbp-ED8h]
  __int64 v664; // [rsp+BD8h] [rbp-ED0h]
  GUID **v665; // [rsp+BE0h] [rbp-EC8h]
  GUID **v666; // [rsp+BE8h] [rbp-EC0h]
  wchar_t *v667; // [rsp+BF0h] [rbp-EB8h]
  wchar_t **v668; // [rsp+BF8h] [rbp-EB0h]
  wchar_t *v669; // [rsp+C00h] [rbp-EA8h]
  wchar_t **v670; // [rsp+C08h] [rbp-EA0h]
  __int64 v671; // [rsp+C10h] [rbp-E98h]
  _DWORD **v672; // [rsp+C18h] [rbp-E90h]
  _QWORD *v673; // [rsp+C20h] [rbp-E88h]
  __int64 v674; // [rsp+C28h] [rbp-E80h]
  __int64 v675; // [rsp+C30h] [rbp-E78h]
  __int64 v676; // [rsp+C38h] [rbp-E70h]
  __int64 v677; // [rsp+C40h] [rbp-E68h]
  __int64 v678; // [rsp+C48h] [rbp-E60h]
  __int64 *v679; // [rsp+C50h] [rbp-E58h]
  __int64 v680; // [rsp+C58h] [rbp-E50h]
  int *v681; // [rsp+C60h] [rbp-E48h]
  __int64 v682; // [rsp+C68h] [rbp-E40h]
  __int64 *v683; // [rsp+C70h] [rbp-E38h]
  char *v684; // [rsp+C78h] [rbp-E30h]
  char *v685; // [rsp+C80h] [rbp-E28h]
  char *v686; // [rsp+C88h] [rbp-E20h]
  __int64 v687; // [rsp+C90h] [rbp-E18h]
  __int64 v688; // [rsp+C98h] [rbp-E10h]
  __int64 v689; // [rsp+CA0h] [rbp-E08h]
  __int64 *v690; // [rsp+CA8h] [rbp-E00h]
  __int64 *v691; // [rsp+CB0h] [rbp-DF8h]
  __int64 v692; // [rsp+CB8h] [rbp-DF0h]
  char *v693; // [rsp+CC0h] [rbp-DE8h]
  char *v694; // [rsp+CC8h] [rbp-DE0h]
  char *v695; // [rsp+CD0h] [rbp-DD8h]
  __int64 v696; // [rsp+CD8h] [rbp-DD0h]
  __int64 v697; // [rsp+CE0h] [rbp-DC8h]
  __int64 v698; // [rsp+CE8h] [rbp-DC0h]
  char *v699; // [rsp+CF0h] [rbp-DB8h]
  __int64 v700; // [rsp+CF8h] [rbp-DB0h]
  __int64 v701; // [rsp+D00h] [rbp-DA8h]
  char *v702; // [rsp+D08h] [rbp-DA0h]
  signed __int64 v703; // [rsp+D10h] [rbp-D98h]
  signed __int64 v704; // [rsp+D18h] [rbp-D90h]
  _QWORD *v705; // [rsp+D20h] [rbp-D88h]
  __int64 v706; // [rsp+D28h] [rbp-D80h]
  DirtyPageMgr **v707; // [rsp+D30h] [rbp-D78h]
  DirtyPageMgr *v708; // [rsp+D38h] [rbp-D70h]
  DirtyPageMgr **v709; // [rsp+D40h] [rbp-D68h]
  DirtyPageMgr **v710; // [rsp+D48h] [rbp-D60h]
  DirtyPageMgr **v711; // [rsp+D50h] [rbp-D58h]
  __int64 v712; // [rsp+D58h] [rbp-D50h]
  __int64 v713; // [rsp+D60h] [rbp-D48h]
  char *v714; // [rsp+D68h] [rbp-D40h]
  char *v715; // [rsp+D70h] [rbp-D38h]
  char *v716; // [rsp+D78h] [rbp-D30h]
  char *v717; // [rsp+D80h] [rbp-D28h]
  volatile signed __int64 *v718; // [rsp+D88h] [rbp-D20h]
  __int64 v719; // [rsp+D90h] [rbp-D18h]
  __int64 v720; // [rsp+D98h] [rbp-D10h]
  volatile signed __int64 *v721; // [rsp+DA0h] [rbp-D08h]
  signed __int64 v722; // [rsp+DA8h] [rbp-D00h]
  signed __int64 v723; // [rsp+DB0h] [rbp-CF8h]
  _QWORD *v724; // [rsp+DB8h] [rbp-CF0h]
  __int64 v725; // [rsp+DC0h] [rbp-CE8h]
  DirtyPageMgr **v726; // [rsp+DC8h] [rbp-CE0h]
  DirtyPageMgr *v727; // [rsp+DD0h] [rbp-CD8h]
  DirtyPageMgr **v728; // [rsp+DD8h] [rbp-CD0h]
  DirtyPageMgr **v729; // [rsp+DE0h] [rbp-CC8h]
  DirtyPageMgr **v730; // [rsp+DE8h] [rbp-CC0h]
  __int64 v731; // [rsp+DF0h] [rbp-CB8h]
  __int64 v732; // [rsp+DF8h] [rbp-CB0h]
  _QWORD *v733; // [rsp+E00h] [rbp-CA8h]
  _QWORD *v734; // [rsp+E08h] [rbp-CA0h]
  _QWORD *v735; // [rsp+E10h] [rbp-C98h]
  __int64 v736; // [rsp+E18h] [rbp-C90h]
  char *v737; // [rsp+E20h] [rbp-C88h]
  __int64 v738; // [rsp+E28h] [rbp-C80h]
  __int64 v739; // [rsp+E30h] [rbp-C78h]
  _QWORD *v740; // [rsp+E38h] [rbp-C70h]
  _QWORD *v741; // [rsp+E40h] [rbp-C68h]
  _QWORD *v742; // [rsp+E48h] [rbp-C60h]
  __int64 v743; // [rsp+E50h] [rbp-C58h]
  __int64 v744; // [rsp+E58h] [rbp-C50h]
  struct CSessionTraceFlags *v745; // [rsp+E60h] [rbp-C48h]
  _QWORD *v746; // [rsp+E68h] [rbp-C40h]
  __int64 v747; // [rsp+E70h] [rbp-C38h]
  __int64 v748; // [rsp+E78h] [rbp-C30h]
  __int64 v749; // [rsp+E80h] [rbp-C28h]
  __int64 v750; // [rsp+E88h] [rbp-C20h]
  char *v751; // [rsp+E90h] [rbp-C18h]
  char *v752; // [rsp+E98h] [rbp-C10h]
  char *v753; // [rsp+EA0h] [rbp-C08h]
  __int64 v754; // [rsp+EA8h] [rbp-C00h]
  __int64 v755; // [rsp+EB0h] [rbp-BF8h]
  __int64 v756; // [rsp+EB8h] [rbp-BF0h]
  char *v757; // [rsp+EC0h] [rbp-BE8h]
  char *v758; // [rsp+EC8h] [rbp-BE0h]
  char *v759; // [rsp+ED0h] [rbp-BD8h]
  __int64 v760; // [rsp+ED8h] [rbp-BD0h]
  __int64 v761; // [rsp+EE0h] [rbp-BC8h]
  __int64 v762; // [rsp+EE8h] [rbp-BC0h]
  __int64 v763; // [rsp+EF0h] [rbp-BB8h]
  _DWORD *v764; // [rsp+EF8h] [rbp-BB0h]
  _QWORD *v765; // [rsp+F00h] [rbp-BA8h]
  __int64 v766; // [rsp+F08h] [rbp-BA0h]
  __int64 v767; // [rsp+F10h] [rbp-B98h]
  int *v768; // [rsp+F18h] [rbp-B90h]
  __int64 v769; // [rsp+F20h] [rbp-B88h]
  __int64 *v770; // [rsp+F28h] [rbp-B80h]
  _DWORD *v771; // [rsp+F30h] [rbp-B78h]
  _QWORD *v772; // [rsp+F38h] [rbp-B70h]
  __int64 v773; // [rsp+F40h] [rbp-B68h]
  __int64 v774; // [rsp+F48h] [rbp-B60h]
  __int64 v775; // [rsp+F50h] [rbp-B58h]
  __int64 v776; // [rsp+F58h] [rbp-B50h]
  __int64 v777; // [rsp+F60h] [rbp-B48h]
  _DWORD *v778; // [rsp+F68h] [rbp-B40h]
  __int64 v779; // [rsp+F70h] [rbp-B38h]
  int *v780; // [rsp+F78h] [rbp-B30h]
  __int64 v781; // [rsp+F80h] [rbp-B28h]
  __int64 v782; // [rsp+F88h] [rbp-B20h]
  _WORD *v783; // [rsp+F90h] [rbp-B18h]
  int **v784; // [rsp+F98h] [rbp-B10h]
  GUID **v785; // [rsp+FA0h] [rbp-B08h]
  GUID **v786; // [rsp+FA8h] [rbp-B00h]
  wchar_t **v787; // [rsp+FB0h] [rbp-AF8h]
  wchar_t **v788; // [rsp+FB8h] [rbp-AF0h]
  __int64 *v789; // [rsp+FC0h] [rbp-AE8h]
  __int64 v790; // [rsp+FC8h] [rbp-AE0h]
  GUID **v791; // [rsp+FD0h] [rbp-AD8h]
  GUID **v792; // [rsp+FD8h] [rbp-AD0h]
  wchar_t *v793; // [rsp+FE0h] [rbp-AC8h]
  wchar_t **v794; // [rsp+FE8h] [rbp-AC0h]
  wchar_t *v795; // [rsp+FF0h] [rbp-AB8h]
  wchar_t **v796; // [rsp+FF8h] [rbp-AB0h]
  __int64 v797; // [rsp+1000h] [rbp-AA8h]
  _DWORD **v798; // [rsp+1008h] [rbp-AA0h]
  _QWORD *v799; // [rsp+1010h] [rbp-A98h]
  __int64 v800; // [rsp+1018h] [rbp-A90h]
  __int64 v801; // [rsp+1020h] [rbp-A88h]
  __int64 v802; // [rsp+1028h] [rbp-A80h]
  __int64 v803; // [rsp+1030h] [rbp-A78h]
  __int64 v804; // [rsp+1038h] [rbp-A70h]
  __int64 *v805; // [rsp+1040h] [rbp-A68h]
  __int64 v806; // [rsp+1048h] [rbp-A60h]
  int *v807; // [rsp+1050h] [rbp-A58h]
  __int64 v808; // [rsp+1058h] [rbp-A50h]
  __int64 *v809; // [rsp+1060h] [rbp-A48h]
  char *v810; // [rsp+1068h] [rbp-A40h]
  char *v811; // [rsp+1070h] [rbp-A38h]
  char *v812; // [rsp+1078h] [rbp-A30h]
  __int64 v813; // [rsp+1080h] [rbp-A28h]
  __int64 v814; // [rsp+1088h] [rbp-A20h]
  __int64 v815; // [rsp+1090h] [rbp-A18h]
  __int64 *v816; // [rsp+1098h] [rbp-A10h]
  __int64 *v817; // [rsp+10A0h] [rbp-A08h]
  __int64 v818; // [rsp+10A8h] [rbp-A00h]
  _QWORD *v819; // [rsp+10B0h] [rbp-9F8h]
  __int64 v820; // [rsp+10B8h] [rbp-9F0h]
  char *v821; // [rsp+10C0h] [rbp-9E8h]
  char *v822; // [rsp+10C8h] [rbp-9E0h]
  char *v823; // [rsp+10D0h] [rbp-9D8h]
  __int64 v824; // [rsp+10D8h] [rbp-9D0h]
  __int64 v825; // [rsp+10E0h] [rbp-9C8h]
  __int64 v826; // [rsp+10E8h] [rbp-9C0h]
  char *v827; // [rsp+10F0h] [rbp-9B8h]
  volatile signed __int64 *v828; // [rsp+10F8h] [rbp-9B0h]
  __int64 v829; // [rsp+1100h] [rbp-9A8h]
  __int64 v830; // [rsp+1108h] [rbp-9A0h]
  volatile signed __int64 *v831; // [rsp+1110h] [rbp-998h]
  signed __int64 v832; // [rsp+1118h] [rbp-990h]
  signed __int64 v833; // [rsp+1120h] [rbp-988h]
  _QWORD *v834; // [rsp+1128h] [rbp-980h]
  __int64 v835; // [rsp+1130h] [rbp-978h]
  __int64 v836; // [rsp+1138h] [rbp-970h]
  DBMgr **v837; // [rsp+1140h] [rbp-968h]
  ReplicaState *v838; // [rsp+1148h] [rbp-960h]
  DirtyPageMgr **v839; // [rsp+1150h] [rbp-958h]
  ReplicaState **v840; // [rsp+1158h] [rbp-950h]
  DirtyPageMgr **v841; // [rsp+1160h] [rbp-948h]
  __int64 v842; // [rsp+1168h] [rbp-940h]
  __int64 v843; // [rsp+1170h] [rbp-938h]
  _QWORD *v844; // [rsp+1178h] [rbp-930h]
  _QWORD *v845; // [rsp+1180h] [rbp-928h]
  _QWORD *v846; // [rsp+1188h] [rbp-920h]
  __int64 v847; // [rsp+1190h] [rbp-918h]
  _QWORD *v848; // [rsp+1198h] [rbp-910h]
  char *v849; // [rsp+11A0h] [rbp-908h]
  char *v850; // [rsp+11A8h] [rbp-900h]
  struct IMemObj *v851; // [rsp+11B0h] [rbp-8F8h]
  AsynchronousDiskAction *v852; // [rsp+11B8h] [rbp-8F0h]
  AsynchronousDiskAction *v853; // [rsp+11C0h] [rbp-8E8h]
  AsynchronousDiskAction *v854; // [rsp+11C8h] [rbp-8E0h]
  char *v855; // [rsp+11D0h] [rbp-8D8h]
  __int64 v856; // [rsp+11D8h] [rbp-8D0h]
  DBMirroring *v857; // [rsp+11E0h] [rbp-8C8h]
  DBMirroring *v858; // [rsp+11E8h] [rbp-8C0h]
  LsMgr *v859; // [rsp+11F0h] [rbp-8B8h]
  DBMirroring *v860; // [rsp+11F8h] [rbp-8B0h]
  struct LsMgr *v861; // [rsp+1200h] [rbp-8A8h]
  struct LsMgr *v862; // [rsp+1208h] [rbp-8A0h]
  char *v863; // [rsp+1210h] [rbp-898h]
  DirtyPageMgr **v864; // [rsp+1218h] [rbp-890h]
  unsigned __int64 *v865; // [rsp+1220h] [rbp-888h]
  DirtyPageMgr **v866; // [rsp+1228h] [rbp-880h]
  char *v867; // [rsp+1230h] [rbp-878h]
  _QWORD *v868; // [rsp+1238h] [rbp-870h]
  _QWORD *v869; // [rsp+1240h] [rbp-868h]
  volatile signed __int64 *v870; // [rsp+1248h] [rbp-860h]
  __int64 v871; // [rsp+1250h] [rbp-858h]
  _QWORD v872[4]; // [rsp+1258h] [rbp-850h] BYREF
  signed __int64 v873; // [rsp+1278h] [rbp-830h]
  char v874; // [rsp+1280h] [rbp-828h] BYREF
  int v875; // [rsp+1284h] [rbp-824h]
  int v876; // [rsp+1288h] [rbp-820h]
  char v877; // [rsp+1298h] [rbp-810h] BYREF
  int v878; // [rsp+129Ch] [rbp-80Ch]
  int v879; // [rsp+12A0h] [rbp-808h]
  char v880[8]; // [rsp+12B0h] [rbp-7F8h] BYREF
  _WORD v881[4]; // [rsp+12B8h] [rbp-7F0h] BYREF
  int v882; // [rsp+12C0h] [rbp-7E8h]
  int **v883; // [rsp+12C8h] [rbp-7E0h]
  char *v884; // [rsp+12D0h] [rbp-7D8h]
  __int64 v885; // [rsp+12D8h] [rbp-7D0h]
  int *v886; // [rsp+12E0h] [rbp-7C8h] BYREF
  int v887; // [rsp+12E8h] [rbp-7C0h]
  __int16 v888; // [rsp+12ECh] [rbp-7BCh]
  __int16 v889; // [rsp+12EEh] [rbp-7BAh]
  GUID *v890; // [rsp+12F0h] [rbp-7B8h] BYREF
  int v891; // [rsp+12F8h] [rbp-7B0h]
  __int16 v892; // [rsp+12FCh] [rbp-7ACh]
  __int16 v893; // [rsp+12FEh] [rbp-7AAh]
  GUID *v894; // [rsp+1300h] [rbp-7A8h] BYREF
  int v895; // [rsp+1308h] [rbp-7A0h]
  __int16 v896; // [rsp+130Ch] [rbp-79Ch]
  __int16 v897; // [rsp+130Eh] [rbp-79Ah]
  wchar_t *v898; // [rsp+1310h] [rbp-798h] BYREF
  int v899; // [rsp+1318h] [rbp-790h]
  __int16 v900; // [rsp+131Ch] [rbp-78Ch]
  __int16 v901; // [rsp+131Eh] [rbp-78Ah]
  wchar_t *v902; // [rsp+1320h] [rbp-788h] BYREF
  int v903; // [rsp+1328h] [rbp-780h]
  __int16 v904; // [rsp+132Ch] [rbp-77Ch]
  __int16 v905; // [rsp+132Eh] [rbp-77Ah]
  __int64 v906; // [rsp+1330h] [rbp-778h] BYREF
  int v907; // [rsp+1338h] [rbp-770h]
  __int16 v908; // [rsp+133Ch] [rbp-76Ch]
  __int16 v909; // [rsp+133Eh] [rbp-76Ah]
  char v910; // [rsp+1340h] [rbp-768h] BYREF
  int v911; // [rsp+1500h] [rbp-5A8h]
  int v912; // [rsp+1504h] [rbp-5A4h]
  __int64 v913; // [rsp+1508h] [rbp-5A0h]
  int v914; // [rsp+1510h] [rbp-598h] BYREF
  __int16 v915; // [rsp+1514h] [rbp-594h]
  int v916; // [rsp+1516h] [rbp-592h]
  char v917; // [rsp+151Ah] [rbp-58Eh]
  char v918; // [rsp+151Bh] [rbp-58Dh]
  char v919[8]; // [rsp+1550h] [rbp-558h] BYREF
  _WORD v920[4]; // [rsp+1558h] [rbp-550h] BYREF
  int v921; // [rsp+1560h] [rbp-548h]
  int **v922; // [rsp+1568h] [rbp-540h]
  char *v923; // [rsp+1570h] [rbp-538h]
  __int64 v924; // [rsp+1578h] [rbp-530h]
  int *v925; // [rsp+1580h] [rbp-528h] BYREF
  int v926; // [rsp+1588h] [rbp-520h]
  __int16 v927; // [rsp+158Ch] [rbp-51Ch]
  __int16 v928; // [rsp+158Eh] [rbp-51Ah]
  GUID *v929; // [rsp+1590h] [rbp-518h] BYREF
  int v930; // [rsp+1598h] [rbp-510h]
  __int16 v931; // [rsp+159Ch] [rbp-50Ch]
  __int16 v932; // [rsp+159Eh] [rbp-50Ah]
  GUID *v933; // [rsp+15A0h] [rbp-508h] BYREF
  int v934; // [rsp+15A8h] [rbp-500h]
  __int16 v935; // [rsp+15ACh] [rbp-4FCh]
  __int16 v936; // [rsp+15AEh] [rbp-4FAh]
  wchar_t *v937; // [rsp+15B0h] [rbp-4F8h] BYREF
  int v938; // [rsp+15B8h] [rbp-4F0h]
  __int16 v939; // [rsp+15BCh] [rbp-4ECh]
  __int16 v940; // [rsp+15BEh] [rbp-4EAh]
  wchar_t *v941; // [rsp+15C0h] [rbp-4E8h] BYREF
  int v942; // [rsp+15C8h] [rbp-4E0h]
  __int16 v943; // [rsp+15CCh] [rbp-4DCh]
  __int16 v944; // [rsp+15CEh] [rbp-4DAh]
  __int64 v945; // [rsp+15D0h] [rbp-4D8h] BYREF
  int v946; // [rsp+15D8h] [rbp-4D0h]
  __int16 v947; // [rsp+15DCh] [rbp-4CCh]
  __int16 v948; // [rsp+15DEh] [rbp-4CAh]
  char v949; // [rsp+15E0h] [rbp-4C8h] BYREF
  int v950; // [rsp+17A0h] [rbp-308h]
  int v951; // [rsp+17A4h] [rbp-304h]
  __int64 v952; // [rsp+17A8h] [rbp-300h]
  int v953; // [rsp+17B0h] [rbp-2F8h] BYREF
  __int16 v954; // [rsp+17B4h] [rbp-2F4h]
  int v955; // [rsp+17B6h] [rbp-2F2h]
  char v956; // [rsp+17BAh] [rbp-2EEh]
  char v957; // [rsp+17BBh] [rbp-2EDh]
  _BYTE v958[24]; // [rsp+17F0h] [rbp-2B8h] BYREF
  _BYTE v959[40]; // [rsp+1808h] [rbp-2A0h] BYREF
  _BYTE v960[320]; // [rsp+1830h] [rbp-278h] BYREF
  int v961; // [rsp+1970h] [rbp-138h] BYREF
  int v962; // [rsp+1974h] [rbp-134h]
  __int16 v963; // [rsp+1978h] [rbp-130h]
  _DWORD v964[2]; // [rsp+1980h] [rbp-128h] BYREF
  __int16 v965; // [rsp+1988h] [rbp-120h]
  int v966; // [rsp+1990h] [rbp-118h] BYREF
  GUID v967; // [rsp+1994h] [rbp-114h]
  wchar_t v968[24]; // [rsp+19A8h] [rbp-100h] BYREF
  wchar_t v969[24]; // [rsp+19D8h] [rbp-D0h] BYREF
  wchar_t v970[24]; // [rsp+1A08h] [rbp-A0h] BYREF
  wchar_t v971[24]; // [rsp+1A38h] [rbp-70h] BYREF

  v847 = -2;
  v332 = a3;
  v335 = (ReplicaState *)a2;
  v380 = a1;
  v257 = a7;
  v554 = a2;
  v277 = 0;
  v251 = 0;
  v252 = 0;
  v253 = 0;
  v966 = 0;
  v967 = x_AG_DB_IdBad;
  v438 = 0;
  v439 = 0;
  v451 = 0;
  v452 = 0;
  v329 = 0;
  v330 = 0;
  v356 = 0;
  v357 = 0;
  v11 = (struct DatabaseStartupInfo *)(a2 + 50);
  v334 = (__int64)(a2 + 7);
  utgettime((struct SQLDATEBASE *)&v526, 0, 0);
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v959, 0, 0, 0, hdl_prntbackout, 0);
    v12 = a2 + 115;
    v848 = a2 + 115;
    AsynchronousDiskPool::AsynchronousDiskPool((AsynchronousDiskPool *)v960, *((struct IMemObj **)v257 + 86));
    AsynchronousDiskPool::Init((AsynchronousDiskPool *)v960);
    v282 = (unsigned __int8)byte_10317ACC5 >> 2;
    if ( (byte_10317ACC5 & 4) != 0 )
      LogSystemMetadataNotSentToClient(L"DBID: [%d] creating sparse files", a3);
    v849 = (char *)(a2 + 7);
    v13 = (char *)a2[8];
    if ( v13 == v849 )
      v13 = 0;
    v850 = v13;
    v14 = v334;
    while ( 1 )
    {
      v276 = v13;
      if ( !v13 )
        break;
      if ( !*((_DWORD *)v13 + 228) )
      {
        v486[10] = 8752;
        v851 = qword_103172088;
        v15 = (AsynchronousDiskAction *)operator new(
                                          0x60u,
                                          qword_103172088,
                                          "sql\\ntdbms\\storeng\\dfs\\manager\\dbmgr.cpp",
                                          8752,
                                          5u);
        v852 = v15;
        if ( v15 )
          v16 = AsynchronousDiskAction::AsynchronousDiskAction(v15, (struct AsynchronousDiskPool *)v960);
        else
          v16 = 0;
        v853 = v16;
        v854 = v16;
        AsynchronousDiskAction::DeferCreating(v16, (struct FileDescription *)v13, a8);
        v14 = v334;
      }
      v13 = (char *)*((_QWORD *)v13 + 1);
      if ( v13 == (char *)v14 )
        v13 = 0;
      v855 = v13;
    }
    if ( !(unsigned int)AsynchronousDiskPool::WaitUntilDone((AsynchronousDiskPool *)v960) )
      ex_raise(18, 2, 25, 5);
    v312 = 0;
    for ( i = 0; !i; i = 1 )
    {
      v18 = *((_QWORD *)v257 + 578);
      v856 = v18;
      if ( v18 )
        BackupManager::BeginSyncWithBulkOps(*(BackupManager **)(v18 + 1960));
      v312 = 1;
    }
    v19 = v335;
    *((_BYTE *)v335 + 881) = 1;
    if ( *((_DWORD *)v257 + 412) == 770 && *((_QWORD *)v257 + 92) )
    {
      DBStartupTimer::DBStartupTimer(&v573, 2, v11);
      DBMirroring::UpdateTruncationLSNs(*((DBMirroring **)v257 + 92));
      v857 = (DBMirroring *)*((_QWORD *)v257 + 92);
      v20 = v857;
      ReplicaState::EnableDbmLogTruncation(v19);
      *((_QWORD *)v19 + 129) = v20;
      if ( v20 )
      {
        v858 = v20;
        LsMgrWithRef = DBMirroring::GetLsMgrWithRef(v20, 0);
        v22 = LsMgrWithRef;
        v859 = LsMgrWithRef;
        v512 = LsMgrWithRef;
        if ( LsMgrWithRef )
          LsMgr::DisableLogTruncation(LsMgrWithRef, (ReplicaState *)((char *)v19 + 1040));
        if ( v22 )
          (*(void (__fastcall **)(LsMgr *))(*(_QWORD *)v22 + 16LL))(v22);
      }
      v860 = (DBMirroring *)*((_QWORD *)v257 + 92);
      v23 = DBMirroring::GetLsMgrWithRef(v860, 0);
      v24 = v23;
      v861 = v23;
      v513 = v23;
      if ( v23 )
      {
        v862 = v23;
        *v12 = (char *)v23 + 109400;
        *((_DWORD *)v12 + 3) = 4;
        v486[12] = 4;
        v863 = (char *)v23 + 109400;
        v487 = LatchBase::AcquireInternal((__int64)v23 + 109400, 4, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0);
        *((_DWORD *)v12 + 2) = v487;
      }
      if ( v24 )
        (*(void (__fastcall **)(struct LsMgr *))(*(_QWORD *)v24 + 16LL))(v24);
      v864 = &v411;
      v488 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v489 = QueryPerformanceCounter(&PerformanceCount);
        QuadPart = (DirtyPageMgr *)PerformanceCount.QuadPart;
      }
      else
      {
        QuadPart = MEMORY[0x7FFE0008];
        v515 = MEMORY[0x7FFE0008];
      }
      v411 = QuadPart;
      v865 = &v573;
      v866 = &v411;
      if ( (unsigned __int64)QuadPart < v573 )
      {
        v26 = 0;
        v340 = 0;
      }
      else
      {
        v26 = (char *)QuadPart - v573;
        v340 = v26;
      }
      v867 = v26;
      v868 = (_QWORD *)(v575 + 8 * (v574 + 13LL));
      v869 = v868;
      *v868 += v26;
    }
    v27 = v257;
    v28 = *((_QWORD *)v257 + 578);
    if ( !*(_BYTE *)(v28 + 8272) )
    {
LABEL_71:
      ReplicaState::DisableLogTruncation(v19, &v438, 7);
      ReplicaState::DisableSLogTruncationAndCleanup(v19, &v451, 7);
      v38 = *((_QWORD *)v27 + 578);
      v592 = v38;
      if ( *(_WORD *)(v38 + 1662) < 0x27Bu )
      {
        v523 = 0;
      }
      else
      {
        v523 = *(_QWORD *)(v38 + 7360);
        if ( v523 )
        {
          v39 = *(_QWORD *)(*((_QWORD *)v19 + 2) + 4624LL);
          v593 = v39;
          if ( *(_WORD *)(v39 + 1662) < 0x27Bu )
            v40 = 0;
          else
            v40 = *(_QWORD *)(v39 + 7360);
          v594 = v40;
          v522 = v40 + 48;
          v457 = 0;
          v497 = 88;
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          v41 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v596 = v41;
          v42 = *(_QWORD *)(v41 + 256);
          v521 = v42;
          if ( !v42 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v42 = *(_QWORD *)(v41 + 256);
            v521 = v42;
          }
          v458 = v42;
          v597 = v42;
          v43 = (_DWORD *)(v42 + 616);
          v498 = *v43 & 1;
          v598 = &v457;
          v457 |= v498 ^ 1;
          v599 = v43;
          *v43 |= 1u;
          Lock = SOS_RWLock::GetLock(v522, 2, 0xFFFFFFFFLL, (char *)v19 + 952);
          *((_BYTE *)v19 + 992) = 1;
          v600 = v458;
          v500 = ~v457;
          v601 = v458 + 616;
          *(_DWORD *)(v458 + 616) &= ~v457;
        }
      }
      v44 = *((_DWORD *)v27 + 412);
      if ( (v44 & 2) == 0 && (unsigned int)RecoveryUnit::IsUpdateable(*((RecoveryUnit **)v27 + 578)) )
      {
        DBStartupTimer::DBStartupTimer(&v576, 33, v11);
        v284 = (unsigned __int8)byte_10317ACC5 >> 2;
        if ( (byte_10317ACC5 & 4) != 0 )
          LogSystemMetadataNotSentToClient(L"DBID: [%d] checkpointing", v332);
        CheckpointDB2(*((unsigned __int16 *)v27 + 20), 0, 1);
        CheckpointDB2(*((unsigned __int16 *)v27 + 20), 100, 1);
        v602 = &v416;
        v501 = Base_PublicGlobals::sm_invariantTscAvailable;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          v502 = QueryPerformanceCounter(&v524);
          v45 = (DirtyPageMgr *)v524.QuadPart;
        }
        else
        {
          v45 = MEMORY[0x7FFE0008];
          v525 = MEMORY[0x7FFE0008];
        }
        v416 = v45;
        v603 = &v576;
        v604 = &v416;
        if ( (unsigned __int64)v45 < v576 )
        {
          v46 = 0;
          v276 = 0;
        }
        else
        {
          v46 = (char *)v45 - v576;
          v276 = v46;
        }
        v605 = v46;
        v606 = (_QWORD *)(v578 + 8 * (v577 + 13LL));
        v607 = v606;
        *v606 += v46;
        v44 = *((_DWORD *)v27 + 412);
      }
      if ( (v44 & 2) != 0 && v44 != 770 )
        ex_raise(18, 23, 16, 5);
      v47 = *((_DWORD *)v27 + 158) & 0x7D3401C;
      v503 = v47;
      v48 = DBTABLE::Allocate(1);
      v277 = v48;
      *((_QWORD *)v19 + 3) = v48;
      v49 = v257;
      *((_QWORD *)v48 + 80) = v257;
      if ( a6 == 1 && a5 )
        *((_WORD *)v48 + 764) = *((_WORD *)v49 + 20);
      v608 = &v341;
      v341 = *((_DWORD *)v49 + 11);
      v50 = v47;
      v51 = v332;
      DBTABLE::Init(
        v277,
        v332,
        v11,
        v50,
        *((_DWORD *)v49 + 381),
        *((_DWORD *)v49 + 12),
        v526,
        v526,
        &v341,
        &v966,
        a5,
        a4);
      if ( a6 == 1 && a5 )
      {
        PerfmonManager::AddInstance((PerfmonManager *)&ResourceStr, 5u, (const wchar_t *)v277 + 468, v332);
        v52 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
        v285 = CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
        {
          PerfmonManager::SetInstanceCounterValue((PerfmonManager *)&ResourceStr, 5u, 0, 0, v332);
          v52 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
        }
        if ( *v52 )
          PerfmonManager::SetInstanceCounterValue((PerfmonManager *)&ResourceStr, 5u, 8u, 0, v332);
      }
      v53 = v257;
      v54 = v277;
      *((_DWORD *)v277 + 561) = *((_DWORD *)v257 + 561);
      *((_DWORD *)v54 + 562) = *((_DWORD *)v53 + 562);
      v55 = (char *)v334;
      FileMgr::StartupPreRecovery(*(FileMgr **)(*((_QWORD *)v54 + 578) + 1696LL), v11);
      if ( !a6 || (unsigned int)RecoveryUnit::GetHkDatabaseState(*((_QWORD *)v53 + 578)) == 1 )
        StreamFileMgr::StartupPreSQLRecovery(*(StreamFileMgr **)(*((_QWORD *)v54 + 578) + 1704LL), v11);
      DBMgr::SetDBTABLE(v380, v277);
      v56 = v335;
      *((_BYTE *)v335 + 884) = 1;
      v287 = (unsigned __int8)byte_10317ACC5 >> 2;
      if ( (byte_10317ACC5 & 4) != 0 )
        LogSystemMetadataNotSentToClient(L"DBID: [%d] associate replica files with primary", v51);
      v609 = v55;
      v57 = (char *)*((_QWORD *)v55 + 1);
      if ( v57 == v55 )
        v57 = 0;
      v610 = v57;
      v58 = v53;
      while ( 1 )
      {
        v276 = v57;
        if ( !v57 )
          break;
        v59 = v57;
        v437 = *((_WORD *)v57 + 18);
        v611 = *((_QWORD *)v58 + 578);
        FCB = FileMgr::GetFCB(*(_QWORD *)(v611 + 1696), v437, 0);
        v543 = FCB;
        v61 = *(_DWORD *)(FCB + 100);
        if ( v61 < 0 )
          goto LABEL_323;
        if ( (*(_BYTE *)(FCB + 124) & 1) == 0 )
          goto LABEL_323;
        if ( (v61 & 0x90000000) != 0 )
          goto LABEL_323;
        if ( *(_DWORD *)(FCB + 104) == 5 )
          goto LABEL_323;
        v440 = *((_WORD *)v59 + 18);
        v255 = 0;
        v256 = v440;
        v441 = *((_WORD *)v59 + 18);
        v62 = v277;
        v612 = *((_QWORD *)v277 + 578);
        v63 = FileMgr::GetFCB(*(_QWORD *)(v612 + 1696), v441, 0);
        v432 = v63;
        v64 = *(_DWORD *)(v63 + 100);
        if ( v64 < 0 || (*(_BYTE *)(v63 + 124) & 1) == 0 || (v64 & 0x90000000) != 0 || *(_DWORD *)(v63 + 104) == 5 )
          goto LABEL_323;
        FCB::SetReplica((FCB *)FCB, (struct FCB *)v63, *((struct RecoveryUnit **)v62 + 578));
        v613 = *((_QWORD *)v62 + 578);
        v504 = *(_DWORD *)(v613 + 1720);
        BPool::Deallocate(qword_10317B628, &v255, v504, 0, 3);
        SidePageTable::RemovePage(*(SidePageTable **)(v63 + 856), 0);
        v65 = (RecoveryUnit *)*((_QWORD *)v58 + 578);
        v274 = v65;
        v875 = 0;
        v876 = 0;
        v288 = CommonGlobalState::m_CollectingStatistics;
        if ( !CommonGlobalState::m_CollectingStatistics )
          goto LABEL_126;
        v289 = (unsigned __int8)byte_10317ABE6 >> 7;
        if ( byte_10317ABE6 < 0 )
          goto LABEL_126;
        v453 = 0;
        v505 = 88;
        v614 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v615 = (_QWORD *)(v614[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v616 = v615;
        v66 = *v615;
        v617 = v66;
        v618 = v66;
        if ( v66 && (v67 = **(struct CSessionTraceFlags ***)(v66 + 56), (v619 = v67) != 0) )
        {
          v527 = v67;
          v453 = CSessionTraceFlags::CheckSessionTraceInternal(v67, 0x337u);
          if ( v453 )
          {
            v65 = v274;
            goto LABEL_126;
          }
        }
        else
        {
          v527 = 0;
        }
        v506 = 88;
        v620 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v621 = v620[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v622 = v621;
        v70 = *(_QWORD *)(v621 + 8);
        v623 = v70;
        v624 = v70;
        v65 = v274;
        if ( v70 )
        {
          v68 = *(struct SEInternalTLS **)(v70 + 96);
          goto LABEL_127;
        }
LABEL_126:
        v68 = 0;
LABEL_127:
        SETLSFromTlsMaybeNull = v68;
        v69 = (_QWORD *)((char *)v65 + 1832);
        v528 = *((_QWORD *)v65 + 229);
        v465 = (unsigned int *)&v874;
        while ( 1 )
        {
          v342 = 0;
          if ( v251 )
          {
            v625 = (char *)v251 + 98;
            v313 = *((_WORD *)v251 + 49);
            if ( (v313 & 0x400) != 0 && (__int16)v253 >= 3 )
            {
              PageRef::UnfixLatchOnly((PageRef *)&v251);
LABEL_156:
              v65 = v274;
              goto LABEL_157;
            }
            v266 = (__int16)v253;
            v417 = v251;
            v626 = (char *)v251 + 98;
            v314 = *((_WORD *)v251 + 49);
            if ( (v314 & 8) != 0 )
            {
              if ( v266 == 3 )
              {
                v266 = 4;
                goto LABEL_139;
              }
              if ( v266 >= 2 )
              {
LABEL_139:
                v627 = (char *)v251 + 100;
                v454 = *((_DWORD *)v251 + 25);
                if ( (v454 & 8) != 0 )
                {
                  v71 = v251[18];
                  if ( v71 )
                  {
                    v628 = v251[18];
                    if ( *(_QWORD *)(v71 + 1880) )
                    {
                      _mm_lfence();
                      DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v71 + 1880), v251, (unsigned int)v266);
                    }
                  }
                }
              }
            }
            v290 = (unsigned __int8)byte_10317ABE5 >> 7;
            if ( byte_10317ABE5 < 0 )
            {
              v72 = (int *)v417 + 25;
              v629 = (__int64)v417 + 100;
              v455 = *((_DWORD *)v417 + 25);
              if ( (v455 & 8) != 0 && v266 >= 3 )
              {
                v630 = (__int64)v417 + 100;
                v456 = *v72;
                if ( (v456 & 0xC0000000) != 0x40000000 )
                {
                  v73 = (void *)*v417;
                  if ( *v417 )
                  {
                    v507 = 2;
                    if ( VirtualProtect(v73, 0x2000u, 2u, flOldProtect) )
                    {
                      _m_prefetchw(v72);
                      flOldProtect[1] = _InterlockedAnd(v72, 0x3FFFFFFFu);
                      _m_prefetchw(v72);
                      v74 = *v72;
                      do
                      {
                        v75 = v74;
                        v74 = _InterlockedCompareExchange(v72, v74 | 0x40000000, v74);
                      }
                      while ( v75 != v74 );
                      flOldProtect[2] = v74;
                    }
                  }
                }
              }
            }
            v76 = v417;
            v77 = v266;
            LatchBase::ReleaseInternal(v417 + 19, (unsigned int)v266);
            if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
            {
              v291 = (unsigned __int8)byte_10317AD4F >> 1;
              if ( (byte_10317AD4F & 2) != 0 )
                BUF::TraceLatchAcquireRelease(v76, 0, v77);
            }
            v253 &= 0xFFFF0000;
            v251 = 0;
            goto LABEL_156;
          }
LABEL_157:
          if ( *v69 )
          {
            PageRef::CatchupPageRedos((PageRef *)&v251, (const struct PageId *)&v255, v65);
            if ( v251 )
            {
              v631 = (char *)v251 + 98;
              v315 = *((_WORD *)v251 + 49);
              if ( (v315 & 0x400) != 0 && (__int16)v253 >= 3 )
              {
                PageRef::UnfixLatchOnly((PageRef *)&v251);
LABEL_185:
                v65 = v274;
                goto LABEL_186;
              }
              v267 = (__int16)v253;
              v418 = v251;
              v632 = (char *)v251 + 98;
              v316 = *((_WORD *)v251 + 49);
              if ( (v316 & 8) != 0 )
              {
                if ( v267 == 3 )
                {
                  v267 = 4;
                  goto LABEL_166;
                }
                if ( v267 >= 2 )
                {
LABEL_166:
                  v633 = (char *)v251 + 100;
                  v381 = *((_DWORD *)v251 + 25);
                  if ( (v381 & 8) != 0 )
                  {
                    v78 = v251[18];
                    if ( v78 )
                    {
                      v634 = v251[18];
                      if ( *(_QWORD *)(v78 + 1880) )
                      {
                        _mm_lfence();
                        DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v78 + 1880), v251, (unsigned int)v267);
                      }
                    }
                  }
                }
              }
              v292 = (unsigned __int8)byte_10317ABE5 >> 7;
              if ( byte_10317ABE5 < 0 )
              {
                v79 = (int *)v418 + 25;
                v635 = (__int64)v418 + 100;
                v382 = *((_DWORD *)v418 + 25);
                if ( (v382 & 8) != 0 && v267 >= 3 )
                {
                  v636 = (__int64)v418 + 100;
                  v383 = *v79;
                  if ( (v383 & 0xC0000000) != 0x40000000 )
                  {
                    v80 = (void *)*v418;
                    if ( *v418 )
                    {
                      flOldProtect[3] = 2;
                      if ( VirtualProtect(v80, 0x2000u, 2u, v509) )
                      {
                        _m_prefetchw(v79);
                        v81 = *v79;
                        do
                        {
                          v82 = v81;
                          v81 = _InterlockedCompareExchange(v79, v81 & 0x3FFFFFFF, v81);
                        }
                        while ( v82 != v81 );
                        v509[1] = v81;
                        _m_prefetchw(v79);
                        v83 = *v79;
                        do
                        {
                          v84 = v83;
                          v83 = _InterlockedCompareExchange(v79, v83 | 0x40000000, v83);
                        }
                        while ( v84 != v83 );
                        v509[2] = v83;
                      }
                    }
                  }
                }
              }
              v85 = v418;
              v86 = v267;
              LatchBase::ReleaseInternal(v418 + 19, (unsigned int)v267);
              if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
              {
                v293 = (unsigned __int8)byte_10317AD4F >> 1;
                if ( (byte_10317AD4F & 2) != 0 )
                  BUF::TraceLatchAcquireRelease(v85, 0, v86);
              }
              v253 &= 0xFFFF0000;
              v251 = 0;
              goto LABEL_185;
            }
          }
LABEL_186:
          LODWORD(v250) = 2;
          v87 = (_QWORD *)BPool::Get(qword_10317B628, v65, &v255, &v342, v250, v465);
          v251 = v87;
          v88 = v253 & 0xFFFF0000 | 2;
          v253 = v88;
          if ( SETLSFromTlsMaybeNull )
          {
            v89 = *v87;
            v637 = v89;
            v90 = (_DWORD *)((char *)SETLSFromTlsMaybeNull + 1280);
            v638 = v90;
            v91 = &v90[2 * (*v90 & 0xF) + 2];
            v639 = v91;
            if ( *v91 != v89 )
            {
              *v91 = v89;
              ++*(_QWORD *)v90;
              v88 = v253;
            }
          }
          v253 = v88 & 0xFFFFFF | (((v342 >> 3) & 1) << 24);
          v254 = v254 & 0xFFFFFF00 | (v342 >> 4) & 1;
          v92 = v528;
          if ( v528 )
          {
            if ( SETLSFromTlsMaybeNull )
            {
              if ( SETLSFromTlsMaybeNull == *((struct SEInternalTLS **)v65 + 903) )
              {
                v93 = (v88 & 0xFFFFFF | (((v342 >> 3) & 1) << 24)) >> 24;
                v509[3] = v93;
                v94 = (_QWORD *)(v528 + 22968);
                v640 = v528 + 22968;
                ++*(_QWORD *)(v528 + 23336);
                v95 = v465;
                if ( v465[1] )
                {
                  ++*(_QWORD *)(v92 + 23344);
                  v94[48] += *v95;
                  if ( v93 )
                  {
                    ++v94[49];
                    v94[50] += *v95;
                  }
                }
              }
            }
          }
          if ( !RecoveryUnit::IsRbIoDb(v65) || !*((_BYTE *)v65 + 8272) )
            goto LABEL_297;
          if ( !v255 || (LODWORD(v340) = 9, WORD2(v340) = 1, v255 == 9) && v256 == 1 )
          {
            v261 = 1;
            goto LABEL_297;
          }
          v261 = 0;
          v97 = *v251;
          v641 = v97;
          v258 = 0;
          if ( *(_WORD *)(v97 + 36)
            && ((v98 = *(_BYTE *)(v97 + 1), v98 != 11) && v98 != 8 && v98 != 9
             || *(_DWORD *)(v97 + 24) != 99
             || (v642 = &v362,
                 v643 = v97 + 32,
                 v362 = *(_DWORD *)(v97 + 32),
                 v363 = *(_WORD *)(v97 + 36),
                 !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v362, v96))
              ? (v99 = 0)
              : (v99 = 1),
                (v258 = v99) != 0) )
          {
            PageHeader::GetIcxLsn(v97, &v352);
          }
          else
          {
            v352 = *(_QWORD *)(v97 + 40);
            v353 = *(_WORD *)(v97 + 48);
          }
          v644 = &v352;
          v100 = (LSN *)((char *)v65 + 8444);
          v529 = (char *)v65 + 8444;
          v348 = 0;
          v349 = 0;
          v101 = (_DWORD *)((char *)v65 + 8456);
          v645 = v101;
          v102 = *v101;
          v343 = *v101;
          v530 = v101;
          do
          {
            v384 = v102 & 0xFFFFFFFE;
            v348 = *(_QWORD *)v529;
            v349 = *((_DWORD *)v529 + 2);
            _InterlockedOr(v249, 0);
            v343 = *v530;
            v102 = v343;
          }
          while ( v384 != v343 );
          if ( (unsigned int)v348 >= (unsigned int)v352
            && ((_DWORD)v348 != (_DWORD)v352
             || HIDWORD(v348) >= HIDWORD(v352) && (HIDWORD(v348) != HIDWORD(v352) || (unsigned __int16)v349 >= v353)) )
          {
            goto LABEL_297;
          }
          if ( !*((_BYTE *)v274 + 27336) )
          {
            v509[5] = 88;
            v646 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v647 = v646[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v648 = v647;
            v649 = *(_QWORD *)(v647 + 8);
            v650 = v649;
            v651 = *(_QWORD *)(v649 + 96);
            if ( v651 != *((_QWORD *)v274 + 1060) && !RecoveryUnit::IsParallelRedoThread(v274) )
              break;
          }
          v509[9] = 88;
          v673 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v674 = v673[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v675 = v674;
          v676 = *(_QWORD *)(v674 + 8);
          v677 = v676;
          v678 = *(_QWORD *)(v676 + 96);
          v65 = v274;
          if ( v678 == *((_QWORD *)v274 + 1060) || RecoveryUnit::IsParallelRedoThread(v274) )
            goto LABEL_297;
          if ( !SETLSFromTlsMaybeNull )
            SETLSFromTlsMaybeNull = GetSETLSFromTlsMaybeNull();
          v679 = &v280;
          v121 = *v251;
          v680 = v121;
          v260 = 0;
          if ( *(_WORD *)(v121 + 36)
            && ((v122 = *(_BYTE *)(v121 + 1), v122 != 11) && v122 != 8 && v122 != 9
             || *(_DWORD *)(v121 + 24) != 99
             || (v681 = &v366,
                 v682 = v121 + 32,
                 v366 = *(_DWORD *)(v121 + 32),
                 v367 = *(_WORD *)(v121 + 36),
                 !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v366, v120))
              ? (v123 = 0)
              : (v123 = 1),
                (v260 = v123) != 0) )
          {
            PageHeader::GetIcxLsn(v121, &v280);
            v124 = v281;
            v125 = v280;
          }
          else
          {
            v125 = *(_QWORD *)(v121 + 40);
            v280 = v125;
            v124 = *(_WORD *)(v121 + 48);
            v281 = v124;
          }
          v683 = &v280;
          v565 = v125;
          v566 = v124;
          v567 = 0;
          if ( v251 )
          {
            v684 = (char *)v251 + 98;
            v317 = *((_WORD *)v251 + 49);
            if ( (v317 & 0x400) != 0 && (__int16)v253 >= 3 )
            {
              PageRef::UnfixLatchOnly((PageRef *)&v251);
LABEL_294:
              v65 = v274;
              v125 = v280;
              v124 = v281;
              goto LABEL_295;
            }
            v268 = (__int16)v253;
            v419 = v251;
            v685 = (char *)v251 + 98;
            v318 = *((_WORD *)v251 + 49);
            if ( (v318 & 8) != 0 )
            {
              if ( v268 == 3 )
              {
                v268 = 4;
                goto LABEL_277;
              }
              if ( v268 >= 2 )
              {
LABEL_277:
                v686 = (char *)v251 + 100;
                v422 = *((_DWORD *)v251 + 25);
                if ( (v422 & 8) != 0 )
                {
                  v126 = v251[18];
                  if ( v126 )
                  {
                    v687 = v251[18];
                    if ( *(_QWORD *)(v126 + 1880) )
                    {
                      _mm_lfence();
                      DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v126 + 1880), v251, (unsigned int)v268);
                    }
                  }
                }
              }
            }
            v294 = (unsigned __int8)byte_10317ABE5 >> 7;
            if ( byte_10317ABE5 < 0 )
            {
              v127 = (int *)v419 + 25;
              v688 = (__int64)v419 + 100;
              v409 = *((_DWORD *)v419 + 25);
              if ( (v409 & 8) != 0 && v268 >= 3 )
              {
                v689 = (__int64)v419 + 100;
                v408 = *v127;
                if ( (v408 & 0xC0000000) != 0x40000000 )
                {
                  v128 = (void *)*v419;
                  if ( *v419 )
                  {
                    v509[10] = 2;
                    if ( VirtualProtect(v128, 0x2000u, 2u, v510) )
                    {
                      _m_prefetchw(v127);
                      v510[1] = _InterlockedAnd(v127, 0x3FFFFFFFu);
                      _m_prefetchw(v127);
                      v129 = *v127;
                      do
                      {
                        v130 = v129;
                        v129 = _InterlockedCompareExchange(v127, v129 | 0x40000000, v129);
                      }
                      while ( v130 != v129 );
                      v510[2] = v129;
                    }
                  }
                }
              }
            }
            v131 = v419;
            v132 = v268;
            LatchBase::ReleaseInternal(v419 + 19, (unsigned int)v268);
            if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
            {
              v295 = (unsigned __int8)byte_10317AD4F >> 1;
              if ( (byte_10317AD4F & 2) != 0 )
                BUF::TraceLatchAcquireRelease(v131, 0, v132);
            }
            v253 &= 0xFFFF0000;
            v251 = 0;
            goto LABEL_294;
          }
LABEL_295:
          v690 = &v472;
          v472 = v125;
          v473 = v124;
          v691 = &v459;
          v459 = v125;
          v460 = v124;
          v250 = 0;
          RecoveryMgr::WaitForRedoLsnToCatchUp(*v69, &v459, 4);
        }
        v469 = v100;
        v336.QuadPart = 0;
        LowPart = 0;
        v652 = v101;
        v103 = *v101;
        v344 = *v101;
        v104 = v100;
        p_HighPart = &v100[1].HighPart;
        while ( 1 )
        {
          v385 = v103 & 0xFFFFFFFE;
          v336 = *v104;
          LowPart = v104[1].LowPart;
          _InterlockedOr(v249, 0);
          v103 = *p_HighPart;
          v344 = v103;
          if ( v385 == v103 )
            break;
          v104 = v469;
        }
        v470 = v336;
        v105 = LowPart;
        v471 = LowPart;
        v106 = *v251;
        v653 = v106;
        v259 = 0;
        if ( *(_WORD *)(v106 + 36)
          && ((v107 = *(_BYTE *)(v106 + 1), v107 != 11) && v107 != 8 && v107 != 9
           || *(_DWORD *)(v106 + 24) != 99
           || (v654 = &v364,
               v655 = v106 + 32,
               v364 = *(_DWORD *)(v106 + 32),
               v365 = *(_WORD *)(v106 + 36),
               !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v364, v104))
            ? (v108 = 0)
            : (v108 = 1),
              (v259 = v108) != 0) )
        {
          PageHeader::GetIcxLsn(v106, &v354);
          v109 = v355;
        }
        else
        {
          v354 = *(LSN *)(v106 + 40);
          v109 = *(_WORD *)(v106 + 48);
          v355 = v109;
        }
        if ( v336.LowPart < v354.LowPart
          || v336.LowPart == v354.LowPart
          && (v336.HighPart < (unsigned int)v354.HighPart || v336.HighPart == v354.HighPart && v105 < v109) )
        {
          v111 = v274;
          v656 = *((_QWORD *)v274 + 214);
          LSN::FormatAsHexString(&v354, v968, &v443);
          LSN::FormatAsHexString(&v470, v969, &v443);
          v275 = 0x100000000001DLL;
          if ( (qword_10317F730 & 0x1000000000000LL) != 0 )
          {
            v445 = 6;
            v657 = v881;
            v881[0] = 0;
            v881[1] = 6;
            v882 = 0;
            v883 = &v886;
            v884 = &v910;
            v911 = 0;
            v912 = 0;
            v885 = 0;
            v913 = 0;
            v658 = &v886;
            v886 = &v914;
            v887 = 52;
            v888 = 5;
            v889 = 0;
            v659 = &v890;
            v890 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
            v891 = 16;
            v892 = 5;
            v893 = 0;
            v660 = &v894;
            v894 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
            v895 = 16;
            v896 = 6;
            v897 = 0;
            v661 = &v898;
            v898 = 0;
            v899 = 0;
            v900 = 7;
            v901 = 0;
            v662 = &v902;
            v902 = 0;
            v903 = 0;
            v904 = 8;
            v905 = 0;
            v663 = &v906;
            v906 = 0;
            v907 = 0;
            v908 = 9;
            v909 = 0;
            v914 = *((unsigned __int16 *)v111 + 860);
            v915 = v256;
            v916 = v255;
            v917 = -1;
            v664 = *v251;
            v918 = *(_BYTE *)(v664 + 1);
            v665 = &v890;
            v890 = (GUID *)(v112 + 596);
            v891 = 16;
            v892 = 5;
            v893 = 0;
            v666 = &v894;
            v894 = (GUID *)(v112 + 580);
            v895 = 16;
            v896 = 6;
            v897 = 0;
            v667 = v968;
            v113 = -1;
            do
              ++v113;
            while ( v968[v113] );
            v509[6] = 2 * v113;
            v668 = &v898;
            v898 = v968;
            v899 = 2 * v113;
            v900 = 7;
            v901 = 0;
            v669 = v969;
            v114 = -1;
            do
              ++v114;
            while ( v969[v114] );
            v509[7] = 2 * v114;
            v670 = &v902;
            v902 = v969;
            v903 = 2 * v114;
            v904 = 8;
            v905 = 0;
            v442 = 0;
            v115 = ((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v112, &v442);
            v116 = (int *)v115;
            v671 = v115;
            if ( v115 )
            {
              v117 = -1;
              do
                ++v117;
              while ( *(_WORD *)(v115 + 2 * v117) );
              v118 = 2 * v117;
            }
            else
            {
              v118 = 0;
            }
            v509[8] = v118;
            v119 = v883 + 10;
            v672 = v883 + 10;
            v883[10] = v116;
            *((_DWORD *)v119 + 2) = v118;
            *((_WORD *)v119 + 6) = 9;
            *((_WORD *)v119 + 7) = 0;
            XeSqlPkg::rbio_read_future_page::Publish((XeSqlPkg::rbio_read_future_page *)v880);
          }
        }
LABEL_297:
        v692 = *v251;
        v549 = v692;
        v275 = 0;
        FCB::RefreshHeaderFieldsFromBuffer(v432, 0, v692, 0);
        if ( v251 )
        {
          v693 = (char *)v251 + 98;
          v319 = *((_WORD *)v251 + 49);
          if ( (v319 & 0x400) != 0 && (__int16)v253 >= 3 )
          {
            PageRef::UnfixLatchOnly((PageRef *)&v251);
            goto LABEL_322;
          }
          v269 = (__int16)v253;
          v420 = v251;
          v694 = (char *)v251 + 98;
          v320 = *((_WORD *)v251 + 49);
          if ( (v320 & 8) != 0 )
          {
            if ( v269 == 3 )
            {
              v269 = 4;
              goto LABEL_305;
            }
            if ( v269 >= 2 )
            {
LABEL_305:
              v695 = (char *)v251 + 100;
              v407 = *((_DWORD *)v251 + 25);
              if ( (v407 & 8) != 0 )
              {
                v133 = v251[18];
                if ( v133 )
                {
                  v696 = v251[18];
                  if ( *(_QWORD *)(v133 + 1880) )
                  {
                    _mm_lfence();
                    DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v133 + 1880), v251, (unsigned int)v269);
                  }
                }
              }
            }
          }
          v296 = (unsigned __int8)byte_10317ABE5 >> 7;
          if ( byte_10317ABE5 < 0 )
          {
            v134 = (int *)v420 + 25;
            v697 = (__int64)v420 + 100;
            v406 = *((_DWORD *)v420 + 25);
            if ( (v406 & 8) != 0 && v269 >= 3 )
            {
              v698 = (__int64)v420 + 100;
              v404 = *v134;
              if ( (v404 & 0xC0000000) != 0x40000000 )
              {
                v135 = (void *)*v420;
                if ( *v420 )
                {
                  v510[3] = 2;
                  if ( VirtualProtect(v135, 0x2000u, 2u, v511) )
                  {
                    _m_prefetchw(v134);
                    v511[1] = _InterlockedAnd(v134, 0x3FFFFFFFu);
                    _m_prefetchw(v134);
                    v136 = *v134;
                    do
                    {
                      v137 = v136;
                      v136 = _InterlockedCompareExchange(v134, v136 | 0x40000000, v136);
                    }
                    while ( v137 != v136 );
                    v511[2] = v136;
                  }
                }
              }
            }
          }
          v138 = v420;
          v139 = v269;
          LatchBase::ReleaseInternal(v420 + 19, (unsigned int)v269);
          if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
          {
            v297 = (unsigned __int8)byte_10317AD4F >> 1;
            if ( (byte_10317AD4F & 2) != 0 )
              BUF::TraceLatchAcquireRelease(v138, 0, v139);
          }
          v253 &= 0xFFFF0000;
          v251 = 0;
        }
LABEL_322:
        v55 = (char *)v56 + 56;
LABEL_323:
        v57 = (char *)*((_QWORD *)v276 + 1);
        if ( v57 == v55 )
          v57 = 0;
        v699 = v57;
      }
      DBTABLE::InitReplicaDBFragments(v277);
      v375 = (volatile signed __int64 *)((char *)v58 + 5376);
      v700 = 0;
      v701 = 0;
      v424 = 0;
      v450 = 0;
      UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      v511[3] = 256;
      v702 = (char *)v58 + 5376;
      if ( *((_DWORD *)v58 + 1344) )
      {
        v405 = 0;
LABEL_330:
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84
          && (v533 = 0,
              v511[4] = 88,
              v705 = NtCurrentTeb()->ThreadLocalStoragePointer,
              v140 = v705[SystemThread_TlsIndex],
              v30 = SystemThread_TlsOffset + v140 == 0,
              v141 = SystemThread_TlsOffset + v140,
              v706 = v141,
              !v30)
          && *(_QWORD *)(v141 + 272) == v141 )
        {
          v142 = *(_QWORD *)(v141 + 256);
          v533 = v142;
        }
        else
        {
          v142 = 0;
        }
        v450 = v142;
        if ( v142 )
        {
          v707 = &v467;
          v511[5] = Base_PublicGlobals::sm_invariantTscAvailable;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            v511[6] = QueryPerformanceCounter(&v534);
            v143 = (DirtyPageMgr *)v534.QuadPart;
            v467 = (DirtyPageMgr *)v534.QuadPart;
          }
          else
          {
            v143 = MEMORY[0x7FFE0008];
            v535 = MEMORY[0x7FFE0008];
            v467 = MEMORY[0x7FFE0008];
            v142 = v450;
          }
          v708 = v143;
          v424 = v143;
        }
        v511[7] = 2;
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v375, UniqueThread_low);
        else
          Spinlock<148,10,258>::SpinToAcquireOptimistic(v375, v142, UniqueThread_low);
        if ( v142 )
        {
          v709 = &v423;
          v511[8] = Base_PublicGlobals::sm_invariantTscAvailable;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            v511[9] = QueryPerformanceCounter(&v536);
            v144 = (DirtyPageMgr *)v536.QuadPart;
            v423 = (DirtyPageMgr *)v536.QuadPart;
          }
          else
          {
            v144 = MEMORY[0x7FFE0008];
            v537 = MEMORY[0x7FFE0008];
            v423 = MEMORY[0x7FFE0008];
            v142 = v450;
          }
          v710 = &v424;
          v711 = &v423;
          if ( v144 < v424 )
          {
            v145 = 0;
            v275 = 0;
          }
          else
          {
            v145 = v144 - v424;
            v275 = v145;
          }
          v275 = v145;
          v712 = v145;
          v713 = v142 + 3192;
          *(_QWORD *)(v142 + 3192) += v145;
        }
      }
      else
      {
        v703 = _InterlockedCompareExchange64(v375, UniqueThread_low, 0);
        v704 = v703;
        v405 = v703 == 0;
        if ( v703 )
          goto LABEL_330;
      }
      v146 = (_QWORD *)((char *)v277 + 16);
      v714 = (char *)v277 + 16;
      v715 = (char *)v58 + 2664;
      *((_QWORD *)v277 + 3) = *((_QWORD *)v58 + 334);
      **((_QWORD **)v58 + 334) = v146;
      *((_QWORD *)v58 + 334) = v146;
      *v146 = (char *)v58 + 2664;
      ++*((_DWORD *)v58 + 670);
      *((_DWORD *)v58 + 158) |= 0x2000u;
      v716 = (char *)v58 + 5376;
      v331 = (char)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
      if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v147 = rand();
        if ( v147 == 5 * (v147 / 5) )
          Spinlock<148,10,258>::UpdateStatSnapshot();
      }
      v717 = (char *)v58 + 5376;
      *((_QWORD *)v58 + 672) = 0;
      v298 = (unsigned __int8)byte_10317ACC5 >> 2;
      if ( (byte_10317ACC5 & 4) != 0 )
        LogSystemMetadataNotSentToClient(
          L"DBID: [%d] enabled copy-on-write for primary database",
          *((unsigned __int16 *)v58 + 20));
      BPool::MarkBufsCopyOnWrite(qword_10317B628, *((_QWORD *)v58 + 578), 1);
      v329 = *((_QWORD *)v56 + 130);
      v330 = *((_WORD *)v56 + 524);
      v356 = v329;
      v357 = v330;
      v474 = 0;
      v475 = 0;
      v476 = 0;
      if ( !v330 && !v329 )
      {
        v377 = (volatile signed __int64 *)(*(_QWORD *)(*((_QWORD *)v58 + 578) + 1712LL) + 5376LL);
        v718 = v377;
        v719 = 0;
        v720 = 0;
        v428 = 0;
        v426 = 0;
        v425 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        v511[10] = 256;
        v721 = v377;
        if ( *(_DWORD *)v377 )
        {
          v444 = 0;
LABEL_362:
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84
            && (v538 = 0,
                v511[11] = 88,
                v724 = NtCurrentTeb()->ThreadLocalStoragePointer,
                v148 = v724[SystemThread_TlsIndex],
                v30 = SystemThread_TlsOffset + v148 == 0,
                v149 = SystemThread_TlsOffset + v148,
                v725 = v149,
                !v30)
            && *(_QWORD *)(v149 + 272) == v149 )
          {
            v150 = *(_QWORD *)(v149 + 256);
            v538 = v150;
          }
          else
          {
            v150 = 0;
          }
          v426 = v150;
          if ( v150 )
          {
            v726 = &v468;
            v511[12] = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              v532 = QueryPerformanceCounter(&v539);
              v151 = (DirtyPageMgr *)v539.QuadPart;
              v468 = (DirtyPageMgr *)v539.QuadPart;
            }
            else
            {
              v151 = MEMORY[0x7FFE0008];
              v540 = MEMORY[0x7FFE0008];
              v468 = MEMORY[0x7FFE0008];
              v150 = v426;
            }
            v727 = v151;
            v428 = v151;
          }
          v555 = 2;
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v377, v425);
          else
            Spinlock<148,10,258>::SpinToAcquireOptimistic(v377, v150, v425);
          if ( v150 )
          {
            v728 = &v427;
            v556 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              v557 = QueryPerformanceCounter(&v541);
              v152 = (DirtyPageMgr *)v541.QuadPart;
              v427 = (DirtyPageMgr *)v541.QuadPart;
            }
            else
            {
              v152 = MEMORY[0x7FFE0008];
              v542 = MEMORY[0x7FFE0008];
              v427 = MEMORY[0x7FFE0008];
              v150 = v426;
            }
            v729 = &v428;
            v730 = &v427;
            if ( v152 < v428 )
            {
              v153 = 0;
              v275 = 0;
            }
            else
            {
              v153 = v152 - v428;
              v275 = v153;
            }
            v275 = v153;
            v731 = v153;
            v732 = v150 + 3192;
            *(_QWORD *)(v150 + 3192) += v153;
          }
        }
        else
        {
          v722 = _InterlockedCompareExchange64(v377, v425, 0);
          v723 = v722;
          v444 = v722 == 0;
          if ( v722 )
            goto LABEL_362;
        }
        LogTruncMgr::GetStartLogSansBackupWithReason(
          (LogTruncMgr *)(*((_QWORD *)v58 + 578) + 2168LL),
          (struct LSN *)&v329,
          (enum _TruncationHoldup *)v558,
          1,
          0,
          0);
        LogTruncMgr::GetStartLogForSLog((LogTruncMgr *)(*((_QWORD *)v58 + 578) + 2168LL), (struct LSN *)&v356);
        if ( !a6 )
          RecoveryUnit::SetMaxGCLsn(*((RecoveryUnit **)v277 + 578), (const struct LSN *)&v329);
        v154 = (_QWORD *)(*(_QWORD *)(*((_QWORD *)v58 + 578) + 1712LL) + 5376LL);
        v733 = v154;
        v734 = v154;
        v299 = (char)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v155 = rand();
          if ( v155 == 5 * (v155 / 5) )
            Spinlock<148,10,258>::UpdateStatSnapshot();
        }
        v735 = v154;
        *v154 = 0;
      }
      ReplicaState::DisableLogTruncation(v56, &v329, 7);
      ReplicaState::DisableSLogTruncationAndCleanup(v56, &v356, 7);
      v300 = (unsigned __int8)byte_10317ACC5 >> 2;
      if ( (byte_10317ACC5 & 4) != 0 )
        LogSystemMetadataNotSentToClient(L"DBID: [%d] refresh files for consistent REDO copy activities", v332);
      v156 = v334;
      v736 = v334;
      v157 = *(char **)(v334 + 8);
      if ( v157 == (char *)v334 )
        v157 = 0;
      v737 = v157;
      while ( 2 )
      {
        v276 = v157;
        if ( v157 )
        {
          v158 = v157;
          v446 = *((_WORD *)v157 + 18);
          v738 = *((_QWORD *)v58 + 578);
          v159 = FileMgr::GetFCB(*(_QWORD *)(v738 + 1696), v446, 0);
          v543 = v159;
          v160 = *(_DWORD *)(v159 + 100);
          if ( v160 < 0 || (*(_BYTE *)(v159 + 124) & 1) == 0 || (v160 & 0x90000000) != 0 || *(_DWORD *)(v159 + 104) == 5 )
            goto LABEL_601;
          v447 = *((_WORD *)v158 + 18);
          v161 = v277;
          v739 = *((_QWORD *)v277 + 578);
          v432 = FileMgr::GetFCB(*(_QWORD *)(v739 + 1696), v447, 0);
          v448 = *(_WORD *)(v432 + 32);
          v255 = 0;
          v256 = v448;
          v162 = (RecoveryUnit *)*((_QWORD *)v161 + 578);
          v257 = v162;
          v878 = 0;
          v879 = 0;
          v301 = CommonGlobalState::m_CollectingStatistics;
          if ( !CommonGlobalState::m_CollectingStatistics )
            goto LABEL_405;
          v302 = (unsigned __int8)byte_10317ABE6 >> 7;
          if ( byte_10317ABE6 < 0 )
            goto LABEL_405;
          v386 = 0;
          v559 = 88;
          v740 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v741 = (_QWORD *)(v740[SystemThread_TlsIndex] + SystemThread_TlsOffset);
          v742 = v741;
          v163 = *v741;
          v743 = v163;
          v744 = v163;
          if ( !v163 )
            goto LABEL_411;
          v164 = **(struct CSessionTraceFlags ***)(v163 + 56);
          v745 = v164;
          if ( v164 )
          {
            v544 = v164;
            v386 = CSessionTraceFlags::CheckSessionTraceInternal(v164, 0x337u);
            if ( v386 )
            {
              v162 = v257;
              goto LABEL_405;
            }
          }
          else
          {
LABEL_411:
            v544 = 0;
          }
          v560 = 88;
          v746 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v747 = v746[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v748 = v747;
          v167 = *(_QWORD *)(v747 + 8);
          v749 = v167;
          v750 = v167;
          v162 = v257;
          if ( v167 )
            v165 = *(struct SEInternalTLS **)(v167 + 96);
          else
LABEL_405:
            v165 = 0;
          v378 = v165;
          v166 = (_QWORD *)((char *)v162 + 1832);
          v545 = *((_QWORD *)v162 + 229);
          v463 = (unsigned int *)&v877;
LABEL_407:
          v345 = 0;
          if ( v251 )
          {
            v751 = (char *)v251 + 98;
            v321 = *((_WORD *)v251 + 49);
            if ( (v321 & 0x400) != 0 && (__int16)v253 >= 3 )
            {
              PageRef::UnfixLatchOnly((PageRef *)&v251);
              goto LABEL_435;
            }
            v270 = (__int16)v253;
            v429 = v251;
            v752 = (char *)v251 + 98;
            v322 = *((_WORD *)v251 + 49);
            if ( (v322 & 8) != 0 )
            {
              if ( v270 == 3 )
              {
                v270 = 4;
                goto LABEL_418;
              }
              if ( v270 >= 2 )
              {
LABEL_418:
                v753 = (char *)v251 + 100;
                v387 = *((_DWORD *)v251 + 25);
                if ( (v387 & 8) != 0 )
                {
                  v168 = v251[18];
                  if ( v168 )
                  {
                    v754 = v251[18];
                    if ( *(_QWORD *)(v168 + 1880) )
                    {
                      _mm_lfence();
                      DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v168 + 1880), v251, (unsigned int)v270);
                    }
                  }
                }
              }
            }
            v303 = (unsigned __int8)byte_10317ABE5 >> 7;
            if ( byte_10317ABE5 < 0 )
            {
              v169 = (int *)v429 + 25;
              v755 = (__int64)v429 + 100;
              v388 = *((_DWORD *)v429 + 25);
              if ( (v388 & 8) != 0 && v270 >= 3 )
              {
                v756 = (__int64)v429 + 100;
                v389 = *v169;
                if ( (v389 & 0xC0000000) != 0x40000000 )
                {
                  v170 = (void *)*v429;
                  if ( *v429 )
                  {
                    v561 = 2;
                    if ( VirtualProtect(v170, 0x2000u, 2u, v562) )
                    {
                      _m_prefetchw(v169);
                      v562[1] = _InterlockedAnd(v169, 0x3FFFFFFFu);
                      _m_prefetchw(v169);
                      v171 = *v169;
                      do
                      {
                        v172 = v171;
                        v171 = _InterlockedCompareExchange(v169, v171 | 0x40000000, v171);
                      }
                      while ( v172 != v171 );
                      v562[2] = v171;
                    }
                  }
                }
              }
            }
            v173 = v429;
            v174 = v270;
            LatchBase::ReleaseInternal(v429 + 19, (unsigned int)v270);
            if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
            {
              v304 = (unsigned __int8)byte_10317AD4F >> 1;
              if ( (byte_10317AD4F & 2) != 0 )
                BUF::TraceLatchAcquireRelease(v173, 0, v174);
            }
            v253 &= 0xFFFF0000;
            v251 = 0;
LABEL_435:
            v162 = v257;
          }
          if ( *v166 )
          {
            PageRef::CatchupPageRedos((PageRef *)&v251, (const struct PageId *)&v255, v162);
            if ( v251 )
            {
              v757 = (char *)v251 + 98;
              v323 = *((_WORD *)v251 + 49);
              if ( (v323 & 0x400) != 0 && (__int16)v253 >= 3 )
              {
                PageRef::UnfixLatchOnly((PageRef *)&v251);
                goto LABEL_464;
              }
              v271 = (__int16)v253;
              v430 = v251;
              v758 = (char *)v251 + 98;
              v324 = *((_WORD *)v251 + 49);
              if ( (v324 & 8) != 0 )
              {
                if ( v271 == 3 )
                {
                  v271 = 4;
                  goto LABEL_445;
                }
                if ( v271 >= 2 )
                {
LABEL_445:
                  v759 = (char *)v251 + 100;
                  v390 = *((_DWORD *)v251 + 25);
                  if ( (v390 & 8) != 0 )
                  {
                    v175 = v251[18];
                    if ( v175 )
                    {
                      v760 = v251[18];
                      if ( *(_QWORD *)(v175 + 1880) )
                      {
                        _mm_lfence();
                        DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v175 + 1880), v251, (unsigned int)v271);
                      }
                    }
                  }
                }
              }
              v305 = (unsigned __int8)byte_10317ABE5 >> 7;
              if ( byte_10317ABE5 < 0 )
              {
                v176 = (int *)v430 + 25;
                v761 = (__int64)v430 + 100;
                v391 = *((_DWORD *)v430 + 25);
                if ( (v391 & 8) != 0 && v271 >= 3 )
                {
                  v762 = (__int64)v430 + 100;
                  v392 = *v176;
                  if ( (v392 & 0xC0000000) != 0x40000000 )
                  {
                    v177 = (void *)*v430;
                    if ( *v430 )
                    {
                      v562[3] = 2;
                      if ( VirtualProtect(v177, 0x2000u, 2u, v563) )
                      {
                        _m_prefetchw(v176);
                        v178 = *v176;
                        do
                        {
                          v179 = v178;
                          v178 = _InterlockedCompareExchange(v176, v178 & 0x3FFFFFFF, v178);
                        }
                        while ( v179 != v178 );
                        v563[1] = v178;
                        _m_prefetchw(v176);
                        v180 = *v176;
                        do
                        {
                          v181 = v180;
                          v180 = _InterlockedCompareExchange(v176, v180 | 0x40000000, v180);
                        }
                        while ( v181 != v180 );
                        v563[2] = v180;
                      }
                    }
                  }
                }
              }
              v182 = v430;
              v183 = v271;
              LatchBase::ReleaseInternal(v430 + 19, (unsigned int)v271);
              if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
              {
                v306 = (unsigned __int8)byte_10317AD4F >> 1;
                if ( (byte_10317AD4F & 2) != 0 )
                  BUF::TraceLatchAcquireRelease(v182, 0, v183);
              }
              v253 &= 0xFFFF0000;
              v251 = 0;
LABEL_464:
              v162 = v257;
            }
          }
          RecoveryUnit::PrePageUpdateHint(v162, (const struct PageId *)&v255);
          LODWORD(v250) = 4;
          v184 = (_QWORD *)BPool::Get(qword_10317B628, v162, &v255, &v345, v250, v463);
          v251 = v184;
          v185 = v253 & 0xFFFF0000 | 4;
          v253 = v185;
          if ( v378 )
          {
            v186 = *v184;
            v763 = v186;
            v187 = (_DWORD *)((char *)v378 + 1280);
            v764 = v187;
            v188 = &v187[2 * (*v187 & 0xF) + 2];
            v765 = v188;
            if ( *v188 != v186 )
            {
              *v188 = v186;
              ++*(_QWORD *)v187;
              v185 = v253;
            }
          }
          v253 = v185 & 0xFFFFFF | (((v345 >> 3) & 1) << 24);
          v254 = v254 & 0xFFFFFF00 | (v345 >> 4) & 1;
          v189 = v545;
          if ( v545 )
          {
            if ( v378 )
            {
              if ( v378 == *((struct SEInternalTLS **)v162 + 903) )
              {
                v190 = (v185 & 0xFFFFFF | (((v345 >> 3) & 1) << 24)) >> 24;
                v563[3] = v190;
                v191 = (_QWORD *)(v545 + 22968);
                v766 = v545 + 22968;
                ++*(_QWORD *)(v545 + 23336);
                v192 = v463;
                if ( v463[1] )
                {
                  ++*(_QWORD *)(v189 + 23344);
                  v191[48] += *v192;
                  if ( v190 )
                  {
                    ++v191[49];
                    v191[50] += *v192;
                  }
                }
              }
            }
          }
          if ( !RecoveryUnit::IsRbIoDb(v162) || !*((_BYTE *)v162 + 8272) )
            goto LABEL_576;
          if ( !v255 || (v332 = 9, v333 = 1, v255 == 9) && v256 == 1 )
          {
            v265 = 1;
            goto LABEL_576;
          }
          v265 = 0;
          v194 = *v251;
          v767 = v194;
          v262 = 0;
          if ( *(_WORD *)(v194 + 36)
            && ((v195 = *(_BYTE *)(v194 + 1), v195 != 11) && v195 != 8 && v195 != 9
             || *(_DWORD *)(v194 + 24) != 99
             || (v768 = &v372,
                 v769 = v194 + 32,
                 v372 = *(_DWORD *)(v194 + 32),
                 v373 = *(_WORD *)(v194 + 36),
                 !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v372, v193))
              ? (v196 = 0)
              : (v196 = 1),
                (v262 = v196) != 0) )
          {
            PageHeader::GetIcxLsn(v194, &v358);
          }
          else
          {
            v358 = *(_QWORD *)(v194 + 40);
            v359 = *(_WORD *)(v194 + 48);
          }
          v770 = &v358;
          v197 = (LSN *)((char *)v162 + 8444);
          v546 = (char *)v162 + 8444;
          v350 = 0;
          v351 = 0;
          v198 = (_DWORD *)((char *)v162 + 8456);
          v771 = v198;
          v199 = *v198;
          v346 = *v198;
          v547 = v198;
          do
          {
            v393 = v199 & 0xFFFFFFFE;
            v350 = *(_QWORD *)v546;
            v351 = *((_DWORD *)v546 + 2);
            _InterlockedOr(v249, 0);
            v346 = *v547;
            v199 = v346;
          }
          while ( v393 != v346 );
          if ( (unsigned int)v350 >= (unsigned int)v358
            && ((_DWORD)v350 != (_DWORD)v358
             || HIDWORD(v350) >= HIDWORD(v358) && (HIDWORD(v350) != HIDWORD(v358) || (unsigned __int16)v351 >= v359)) )
          {
            goto LABEL_576;
          }
          if ( !*((_BYTE *)v257 + 27336) )
          {
            v563[5] = 88;
            v772 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v773 = v772[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v774 = v773;
            v775 = *(_QWORD *)(v773 + 8);
            v776 = v775;
            v777 = *(_QWORD *)(v775 + 96);
            if ( v777 != *((_QWORD *)v257 + 1060) && !RecoveryUnit::IsParallelRedoThread(v257) )
            {
              v464 = v197;
              v338.QuadPart = 0;
              v339 = 0;
              v778 = v198;
              v200 = *v198;
              v347 = *v198;
              v201 = v197;
              v548 = &v197[1].HighPart;
              while ( 1 )
              {
                v394 = v200 & 0xFFFFFFFE;
                v338 = *v201;
                v339 = v201[1].LowPart;
                _InterlockedOr(v249, 0);
                v200 = *v548;
                v347 = v200;
                if ( v394 == v200 )
                  break;
                v201 = v464;
              }
              v477 = v338;
              v202 = v339;
              v478 = v339;
              v203 = *v251;
              v779 = v203;
              v263 = 0;
              if ( *(_WORD *)(v203 + 36)
                && ((v204 = *(_BYTE *)(v203 + 1), v204 != 11) && v204 != 8 && v204 != 9
                 || *(_DWORD *)(v203 + 24) != 99
                 || (v780 = &v368,
                     v781 = v203 + 32,
                     v368 = *(_DWORD *)(v203 + 32),
                     v369 = *(_WORD *)(v203 + 36),
                     !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v368, v201))
                  ? (v205 = 0)
                  : (v205 = 1),
                    (v263 = v205) != 0) )
              {
                PageHeader::GetIcxLsn(v203, &v360);
                v206 = v361;
              }
              else
              {
                v360 = *(LSN *)(v203 + 40);
                v206 = *(_WORD *)(v203 + 48);
                v361 = v206;
              }
              if ( v338.LowPart < v360.LowPart
                || v338.LowPart == v360.LowPart
                && (v338.HighPart < (unsigned int)v360.HighPart || v338.HighPart == v360.HighPart && v202 < v206) )
              {
                v208 = v257;
                v782 = *((_QWORD *)v257 + 214);
                LSN::FormatAsHexString(&v360, v970, &v395);
                LSN::FormatAsHexString(&v477, v971, &v395);
                v334 = 0x100000000001DLL;
                if ( (qword_10317F730 & 0x1000000000000LL) != 0 )
                {
                  v449 = 6;
                  v783 = v920;
                  v920[0] = 0;
                  v920[1] = 6;
                  v921 = 0;
                  v922 = &v925;
                  v923 = &v949;
                  v950 = 0;
                  v951 = 0;
                  v924 = 0;
                  v952 = 0;
                  v784 = &v925;
                  v925 = &v953;
                  v926 = 52;
                  v927 = 5;
                  v928 = 0;
                  v785 = &v929;
                  v929 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
                  v930 = 16;
                  v931 = 5;
                  v932 = 0;
                  v786 = &v933;
                  v933 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
                  v934 = 16;
                  v935 = 6;
                  v936 = 0;
                  v787 = &v937;
                  v937 = 0;
                  v938 = 0;
                  v939 = 7;
                  v940 = 0;
                  v788 = &v941;
                  v941 = 0;
                  v942 = 0;
                  v943 = 8;
                  v944 = 0;
                  v789 = &v945;
                  v945 = 0;
                  v946 = 0;
                  v947 = 9;
                  v948 = 0;
                  v953 = *((unsigned __int16 *)v208 + 860);
                  v954 = v256;
                  v955 = v255;
                  v956 = -1;
                  v790 = *v251;
                  v957 = *(_BYTE *)(v790 + 1);
                  v791 = &v929;
                  v929 = (GUID *)(v209 + 596);
                  v930 = 16;
                  v931 = 5;
                  v932 = 0;
                  v792 = &v933;
                  v933 = (GUID *)(v209 + 580);
                  v934 = 16;
                  v935 = 6;
                  v936 = 0;
                  v793 = v970;
                  v210 = -1;
                  do
                    ++v210;
                  while ( v970[v210] );
                  v563[6] = 2 * v210;
                  v794 = &v937;
                  v937 = v970;
                  v938 = 2 * v210;
                  v939 = 7;
                  v940 = 0;
                  v795 = v971;
                  v211 = -1;
                  do
                    ++v211;
                  while ( v971[v211] );
                  v563[7] = 2 * v211;
                  v796 = &v941;
                  v941 = v971;
                  v942 = 2 * v211;
                  v943 = 8;
                  v944 = 0;
                  v396 = 0;
                  v212 = ((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v209, &v396);
                  v213 = (int *)v212;
                  v797 = v212;
                  if ( v212 )
                  {
                    v214 = -1;
                    do
                      ++v214;
                    while ( *(_WORD *)(v212 + 2 * v214) );
                    v215 = 2 * v214;
                  }
                  else
                  {
                    v215 = 0;
                  }
                  v563[8] = v215;
                  v216 = v922 + 10;
                  v798 = v922 + 10;
                  v922[10] = v213;
                  *((_DWORD *)v216 + 2) = v215;
                  *((_WORD *)v216 + 6) = 9;
                  *((_WORD *)v216 + 7) = 0;
                  XeSqlPkg::rbio_read_future_page::Publish((XeSqlPkg::rbio_read_future_page *)v919);
                }
              }
LABEL_576:
              v818 = *v251;
              v549 = v818;
              v275 = 0;
              FCB::RefreshHeaderFieldsFromBuffer(v432, 0, v818, 0);
              v819 = v251;
              v484 = 1;
              v230 = BPool::PrepareToDirty(qword_10317B628, v251, 1, 0);
              v820 = v230;
              *(_WORD *)(v230 + 4) &= ~0x200u;
              *(_WORD *)(v230 + 4) &= ~0x1000u;
              *(_DWORD *)(v230 + 64) = 1;
              if ( v251 )
              {
                v821 = (char *)v251 + 98;
                v327 = *((_WORD *)v251 + 49);
                if ( (v327 & 0x400) != 0 && (__int16)v253 >= 3 )
                {
                  PageRef::UnfixLatchOnly((PageRef *)&v251);
                  goto LABEL_601;
                }
                v273 = (__int16)v253;
                v433 = v251;
                v822 = (char *)v251 + 98;
                v328 = *((_WORD *)v251 + 49);
                if ( (v328 & 8) != 0 )
                {
                  if ( v273 == 3 )
                  {
                    v273 = 4;
                    goto LABEL_584;
                  }
                  if ( v273 >= 2 )
                  {
LABEL_584:
                    v823 = (char *)v251 + 100;
                    v400 = *((_DWORD *)v251 + 25);
                    if ( (v400 & 8) != 0 )
                    {
                      v231 = v251[18];
                      if ( v231 )
                      {
                        v824 = v251[18];
                        if ( *(_QWORD *)(v231 + 1880) )
                        {
                          _mm_lfence();
                          DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v231 + 1880), v251, (unsigned int)v273);
                        }
                      }
                    }
                  }
                }
                v309 = (unsigned __int8)byte_10317ABE5 >> 7;
                if ( byte_10317ABE5 < 0 )
                {
                  v232 = (int *)v433 + 25;
                  v825 = (__int64)v433 + 100;
                  v401 = *((_DWORD *)v433 + 25);
                  if ( (v401 & 8) != 0 && v273 >= 3 )
                  {
                    v826 = (__int64)v433 + 100;
                    v402 = *v232;
                    if ( (v402 & 0xC0000000) != 0x40000000 )
                    {
                      v233 = (void *)*v433;
                      if ( *v433 )
                      {
                        v485 = 2;
                        if ( VirtualProtect(v233, 0x2000u, 2u, v486) )
                        {
                          _m_prefetchw(v232);
                          v486[1] = _InterlockedAnd(v232, 0x3FFFFFFFu);
                          _m_prefetchw(v232);
                          v234 = *v232;
                          do
                          {
                            v235 = v234;
                            v234 = _InterlockedCompareExchange(v232, v234 | 0x40000000, v234);
                          }
                          while ( v235 != v234 );
                          v486[2] = v234;
                        }
                      }
                    }
                  }
                }
                v236 = v433;
                v237 = v273;
                LatchBase::ReleaseInternal(v433 + 19, (unsigned int)v273);
                if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
                {
                  v310 = (unsigned __int8)byte_10317AD4F >> 1;
                  if ( (byte_10317AD4F & 2) != 0 )
                    BUF::TraceLatchAcquireRelease(v236, 0, v237);
                }
                v253 &= 0xFFFF0000;
                v251 = 0;
              }
LABEL_601:
              v157 = (char *)*((_QWORD *)v276 + 1);
              if ( v157 == (char *)v156 )
                v157 = 0;
              v827 = v157;
              continue;
            }
          }
          v563[9] = 88;
          v799 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v800 = v799[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v801 = v800;
          v802 = *(_QWORD *)(v800 + 8);
          v803 = v802;
          v804 = *(_QWORD *)(v802 + 96);
          v162 = v257;
          if ( v804 == *((_QWORD *)v257 + 1060) || RecoveryUnit::IsParallelRedoThread(v257) )
            goto LABEL_576;
          if ( !v378 )
            v378 = GetSETLSFromTlsMaybeNull();
          v805 = &v278;
          v218 = *v251;
          v806 = v218;
          v264 = 0;
          if ( *(_WORD *)(v218 + 36)
            && ((v219 = *(_BYTE *)(v218 + 1), v219 != 11) && v219 != 8 && v219 != 9
             || *(_DWORD *)(v218 + 24) != 99
             || (v807 = &v370,
                 v808 = v218 + 32,
                 v370 = *(_DWORD *)(v218 + 32),
                 v371 = *(_WORD *)(v218 + 36),
                 !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v370, v217))
              ? (v220 = 0)
              : (v220 = 1),
                (v264 = v220) != 0) )
          {
            PageHeader::GetIcxLsn(v218, &v278);
            v221 = v279;
            v222 = v278;
          }
          else
          {
            v222 = *(_QWORD *)(v218 + 40);
            v278 = v222;
            v221 = *(_WORD *)(v218 + 48);
            v279 = v221;
          }
          v809 = &v278;
          v568 = v222;
          v569 = v221;
          v570 = 0;
          if ( v251 )
          {
            v810 = (char *)v251 + 98;
            v325 = *((_WORD *)v251 + 49);
            if ( (v325 & 0x400) != 0 && (__int16)v253 >= 3 )
            {
              PageRef::UnfixLatchOnly((PageRef *)&v251);
              goto LABEL_573;
            }
            v272 = (__int16)v253;
            v431 = v251;
            v811 = (char *)v251 + 98;
            v326 = *((_WORD *)v251 + 49);
            if ( (v326 & 8) != 0 )
            {
              if ( v272 == 3 )
              {
                v272 = 4;
                goto LABEL_556;
              }
              if ( v272 >= 2 )
              {
LABEL_556:
                v812 = (char *)v251 + 100;
                v397 = *((_DWORD *)v251 + 25);
                if ( (v397 & 8) != 0 )
                {
                  v223 = v251[18];
                  if ( v223 )
                  {
                    v813 = v251[18];
                    if ( *(_QWORD *)(v223 + 1880) )
                    {
                      _mm_lfence();
                      DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v223 + 1880), v251, (unsigned int)v272);
                    }
                  }
                }
              }
            }
            v307 = (unsigned __int8)byte_10317ABE5 >> 7;
            if ( byte_10317ABE5 < 0 )
            {
              v224 = (int *)v431 + 25;
              v814 = (__int64)v431 + 100;
              v398 = *((_DWORD *)v431 + 25);
              if ( (v398 & 8) != 0 && v272 >= 3 )
              {
                v815 = (__int64)v431 + 100;
                v399 = *v224;
                if ( (v399 & 0xC0000000) != 0x40000000 )
                {
                  v225 = (void *)*v431;
                  if ( *v431 )
                  {
                    v563[10] = 2;
                    if ( VirtualProtect(v225, 0x2000u, 2u, &v564) )
                    {
                      _m_prefetchw(v224);
                      v571 = _InterlockedAnd(v224, 0x3FFFFFFFu);
                      _m_prefetchw(v224);
                      v226 = *v224;
                      do
                      {
                        v227 = v226;
                        v226 = _InterlockedCompareExchange(v224, v226 | 0x40000000, v226);
                      }
                      while ( v227 != v226 );
                      v572 = v226;
                    }
                  }
                }
              }
            }
            v228 = v431;
            v229 = v272;
            LatchBase::ReleaseInternal(v431 + 19, (unsigned int)v272);
            if ( LatchBase::sm_acquireReleaseEnforcementExpensive )
            {
              v308 = (unsigned __int8)byte_10317AD4F >> 1;
              if ( (byte_10317AD4F & 2) != 0 )
                BUF::TraceLatchAcquireRelease(v228, 0, v229);
            }
            v253 &= 0xFFFF0000;
            v251 = 0;
LABEL_573:
            v222 = v278;
            v221 = v279;
            v162 = v257;
          }
          v816 = &v479;
          v479 = v222;
          v480 = v221;
          v817 = &v461;
          v461 = v222;
          v462 = v221;
          v250 = 0;
          RecoveryMgr::WaitForRedoLsnToCatchUp(*v166, &v461, 4);
          goto LABEL_407;
        }
        break;
      }
      if ( !a6 )
      {
        v964[0] = 0;
        v964[1] = 0;
        v965 = 0;
        v961 = 0;
        v962 = 0;
        v963 = 0;
        (*(void (__fastcall **)(_QWORD, _DWORD *))(**(_QWORD **)(*((_QWORD *)v58 + 578) + 1736LL) + 40LL))(
          *(_QWORD *)(*((_QWORD *)v58 + 578) + 1736LL),
          v964);
        XdesMgr::GetOldestBeginLsn((XdesMgr *)(*((_QWORD *)v58 + 578) + 6600LL), (struct LSN *)&v961, 1, 0);
        v376 = (volatile signed __int64 *)(*(_QWORD *)(*((_QWORD *)v58 + 578) + 1712LL) + 5376LL);
        v828 = v376;
        v829 = 0;
        v830 = 0;
        v335 = 0;
        v435 = 0;
        v434 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        v486[3] = 256;
        v831 = v376;
        if ( *(_DWORD *)v376 )
        {
          v403 = 0;
LABEL_609:
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84
            && (v486[4] = 88,
                v834 = NtCurrentTeb()->ThreadLocalStoragePointer,
                v238 = v834[SystemThread_TlsIndex],
                v30 = SystemThread_TlsOffset + v238 == 0,
                v239 = SystemThread_TlsOffset + v238,
                v835 = v239,
                !v30)
            && *(_QWORD *)(v239 + 272) == v239 )
          {
            v240 = *(_QWORD *)(v239 + 256);
            v836 = v240;
          }
          else
          {
            v240 = 0;
          }
          v435 = v240;
          if ( v240 )
          {
            v837 = &v380;
            v486[5] = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              v486[6] = QueryPerformanceCounter(&v550);
              v241 = (ReplicaState *)v550.QuadPart;
              v380 = (DBMgr *)v550.QuadPart;
            }
            else
            {
              v241 = MEMORY[0x7FFE0008];
              v551 = MEMORY[0x7FFE0008];
              v380 = MEMORY[0x7FFE0008];
              v240 = v435;
            }
            v838 = v241;
            v335 = v241;
          }
          v486[7] = 2;
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v376, v434);
          else
            Spinlock<148,10,258>::SpinToAcquireOptimistic(v376, v240, v434);
          if ( v240 )
          {
            v839 = &v436;
            v486[8] = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              v486[9] = QueryPerformanceCounter(&v552);
              v242 = (DirtyPageMgr *)v552.QuadPart;
              v436 = (DirtyPageMgr *)v552.QuadPart;
            }
            else
            {
              v242 = MEMORY[0x7FFE0008];
              v553 = MEMORY[0x7FFE0008];
              v436 = MEMORY[0x7FFE0008];
              v240 = v435;
            }
            v840 = &v335;
            v841 = &v436;
            if ( v242 < v335 )
            {
              v243 = 0;
              v275 = 0;
            }
            else
            {
              v243 = v242 - v335;
              v275 = v243;
            }
            v275 = v243;
            v842 = v243;
            v843 = v240 + 3192;
            *(_QWORD *)(v240 + 3192) += v243;
          }
        }
        else
        {
          v832 = _InterlockedCompareExchange64(v376, v434, 0);
          v833 = v832;
          v403 = v832 == 0;
          if ( v832 )
            goto LABEL_609;
        }
        v481 = 0;
        v482 = 0;
        v483 = 0;
        if ( v963 || v961 || (v244 = (const struct LSN *)v964, v962) )
          v244 = (const struct LSN *)&v961;
        RecoveryUnit::SetMaxGCLsn(*((RecoveryUnit **)v277 + 578), v244);
        v245 = (_QWORD *)(*(_QWORD *)(*((_QWORD *)v58 + 578) + 1712LL) + 5376LL);
        v844 = v245;
        v845 = v245;
        v311 = (char)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v246 = rand();
          if ( v246 == 5 * (v246 / 5) )
            Spinlock<148,10,258>::UpdateStatSnapshot();
        }
        v846 = v245;
        *v245 = 0;
      }
      AsynchronousDiskPool::~AsynchronousDiskPool((AsynchronousDiskPool *)v960);
      ExcHandler::~ExcHandler((ExcHandler *)v959);
      goto LABEL_647;
    }
    v379 = (volatile signed __int64 *)(*(_QWORD *)(v28 + 1712) + 5376LL);
    v870 = v379;
    v871 = 0;
    v872[2] = 0;
    v415 = 0;
    v413 = 0;
    v412 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    v490 = 256;
    v872[3] = v379;
    if ( *(_DWORD *)v379 )
    {
      v410 = 0;
    }
    else
    {
      v873 = _InterlockedCompareExchange64(v379, v412, 0);
      v579 = v873;
      v410 = v873 == 0;
      if ( !v873 )
      {
LABEL_67:
        LogTruncMgr::GetStartLog((LogTruncMgr *)(*((_QWORD *)v27 + 578) + 2168LL), (struct LSN *)&v438, 0, 1, 0, 0);
        LogTruncMgr::GetStartLogForSLog((LogTruncMgr *)(*((_QWORD *)v27 + 578) + 2168LL), (struct LSN *)&v451);
        v36 = (_QWORD *)(*(_QWORD *)(*((_QWORD *)v27 + 578) + 1712LL) + 5376LL);
        v589 = v36;
        v590 = v36;
        v283 = (char)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v37 = rand();
          if ( v37 == 5 * (v37 / 5) )
            Spinlock<148,10,258>::UpdateStatSnapshot();
        }
        v591 = v36;
        *v36 = 0;
        goto LABEL_71;
      }
    }
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84
      && (v516 = 0,
          v491 = 88,
          v580 = NtCurrentTeb()->ThreadLocalStoragePointer,
          v29 = v580[SystemThread_TlsIndex],
          v30 = SystemThread_TlsOffset + v29 == 0,
          v31 = SystemThread_TlsOffset + v29,
          v581 = v31,
          !v30)
      && *(_QWORD *)(v31 + 272) == v31 )
    {
      v32 = *(_QWORD *)(v31 + 256);
      v516 = v32;
    }
    else
    {
      v32 = 0;
    }
    v413 = v32;
    if ( v32 )
    {
      v582 = &v466;
      v492 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v493 = QueryPerformanceCounter(&v517);
        v33 = (DirtyPageMgr *)v517.QuadPart;
        v466 = (DirtyPageMgr *)v517.QuadPart;
      }
      else
      {
        v33 = MEMORY[0x7FFE0008];
        v518 = MEMORY[0x7FFE0008];
        v466 = MEMORY[0x7FFE0008];
        v32 = v413;
      }
      v583 = v33;
      v415 = v33;
    }
    v494 = 2;
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v379, v412);
    else
      Spinlock<148,10,258>::SpinToAcquireOptimistic(v379, v32, v412);
    if ( v32 )
    {
      v584 = &v414;
      v495 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v496 = QueryPerformanceCounter(&v519);
        v34 = (DirtyPageMgr *)v519.QuadPart;
        v414 = (DirtyPageMgr *)v519.QuadPart;
      }
      else
      {
        v34 = MEMORY[0x7FFE0008];
        v520 = MEMORY[0x7FFE0008];
        v414 = MEMORY[0x7FFE0008];
        v32 = v413;
      }
      v585 = &v415;
      v586 = &v414;
      if ( v34 < v415 )
      {
        v35 = 0;
        v340 = 0;
      }
      else
      {
        v35 = v34 - v415;
        v340 = (char *)v35;
      }
      v275 = v35;
      v587 = v35;
      v588 = v32 + 3192;
      *(_QWORD *)(v32 + 3192) += v35;
    }
    goto LABEL_67;
  }
  catch ( SQLError v958 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v872, (const struct SQLError *)v958);
      *((_DWORD *)v554 + 222) = 2;
      ex_raise(18, 23, 16, 2);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v872);
    }
    catch ( ShortStackException )
    {
    }
  }
LABEL_647:
  v247 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v248 = *(struct Worker **)(v247 + 256);
  if ( !v248 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v248 = *(struct Worker **)(v247 + 256);
  }
  if ( *((_DWORD *)v248 + 139) )
    ExceptionPostCatchActions(v248);
  PageRef::~PageRef((PageRef *)&v251);
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
