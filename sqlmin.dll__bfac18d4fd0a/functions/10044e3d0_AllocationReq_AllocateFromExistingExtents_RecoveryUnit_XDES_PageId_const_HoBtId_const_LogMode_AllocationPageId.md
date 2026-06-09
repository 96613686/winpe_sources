# AllocationReq::AllocateFromExistingExtents(RecoveryUnit *,XDES *,PageId const &,HoBtId const &,LogMode,AllocationPageId &,int &,int &,PageId &,AutoAllocationCaches &)

- ea: `0x10044e3d0`
- end: `0x10044e83b`
- name: `?AllocateFromExistingExtents@AllocationReq@@AEAAHPEAVRecoveryUnit@@PEAVXDES@@AEBVPageId@@AEBVHoBtId@@W4LogMode@@AEAVAllocationPageId@@AEAH6AEAV4@AEAVAutoAllocationCaches@@@Z`
- size: `1131`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1004558e0`

## callees

- `0x100401490`
- `0x100402d60`
- `0x100403030`
- `0x10042d380`
- `0x10043b450`
- `0x10044e3d0`
- `0x10044e850`
- `0x1004550c0`
- `0x10047fc70`
- `0x100483820`
- `0x1004844b0`
- `0x1004866c0`
- `0x1005b9af0`
- `0x1005f1a40`
- `0x1005f21c0`
- `0x101626860`
- `0x101626aa0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1005f2184`
- `KERNEL32!QueryPerformanceCounter` at `0x10161d9c7`
- `KERNEL32!QueryPerformanceCounter` at `0x10161daba`
- `KERNEL32!QueryPerformanceCounter` at `0x10161db0a`
- `KERNEL32!QueryPerformanceCounter` at `0x10161de3f`
- `KERNEL32!QueryPerformanceCounter` at `0x10161de8f`
- `KERNEL32!QueryPerformanceCounter` at `0x10161e6e6`
- `KERNEL32!QueryPerformanceCounter` at `0x10161e73a`
- `KERNEL32!QueryPerformanceCounter` at `0x1005f2184`
- `KERNEL32!QueryPerformanceCounter` at `0x10161d9c7`
- `KERNEL32!QueryPerformanceCounter` at `0x10161daba`
- `KERNEL32!QueryPerformanceCounter` at `0x10161db0a`
- `KERNEL32!QueryPerformanceCounter` at `0x10161de3f`
- `KERNEL32!QueryPerformanceCounter` at `0x10161de8f`
- `KERNEL32!QueryPerformanceCounter` at `0x10161e6e6`
- `KERNEL32!QueryPerformanceCounter` at `0x10161e73a`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10044e5f6`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100487c7b`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100488528`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10161e775`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1005f2122`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10161da54`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10161ddd9`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10161e680`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x1005f213d`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10161dacb`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10161de50`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10161e6f7`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1005f216c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10161d9b3`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10161daa2`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10161daf6`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10161de27`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10161de7b`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10161e6ce`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10161e722`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10161dd1d`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10161e21d`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10161dd1d`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10161e21d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161d949`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161d96b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161dbb4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161dbdd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161dc06`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161dd46`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161dd8f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161ddb7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161dfa4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161e024`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161e050`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161e252`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161e52e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161e80c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161d949`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161d96b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161dbb4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161dbdd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161dc06`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161dd46`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161dd8f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161ddb7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161dfa4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161e024`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161e050`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161e252`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161e52e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10161e80c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10161dc18`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10161dc18`
- `sqldk!SystemThread_TlsIndex` at `0x100487bd7`
- `sqldk!SystemThread_TlsIndex` at `0x100488483`
- `sqldk!SystemThread_TlsIndex` at `0x100488581`
- `sqldk!SystemThread_TlsIndex` at `0x100488685`
- `sqldk!SystemThread_TlsIndex` at `0x1005ba3fa`
- `sqldk!SystemThread_TlsIndex` at `0x1005ba5d4`
- `sqldk!SystemThread_TlsIndex` at `0x1005bb19b`
- `sqldk!SystemThread_TlsIndex` at `0x10161d981`
- `sqldk!SystemThread_TlsIndex` at `0x10161da74`
- `sqldk!SystemThread_TlsIndex` at `0x10161ddf9`
- `sqldk!SystemThread_TlsIndex` at `0x10161e1e5`
- `sqldk!SystemThread_TlsIndex` at `0x10161e5eb`
- `sqldk!SystemThread_TlsIndex` at `0x10161e6a0`
- `sqldk!SystemThread_TlsIndex` at `0x10161e8ab`
- `sqldk!SystemThread_TlsOffset` at `0x100487be0`
- `sqldk!SystemThread_TlsOffset` at `0x10048848c`
- `sqldk!SystemThread_TlsOffset` at `0x10048858a`
- `sqldk!SystemThread_TlsOffset` at `0x10048868e`
- `sqldk!SystemThread_TlsOffset` at `0x1005ba403`
- `sqldk!SystemThread_TlsOffset` at `0x1005ba5dd`
- `sqldk!SystemThread_TlsOffset` at `0x1005bb1a4`
- `sqldk!SystemThread_TlsOffset` at `0x10161d98a`
- `sqldk!SystemThread_TlsOffset` at `0x10161da7d`
- `sqldk!SystemThread_TlsOffset` at `0x10161de02`
- `sqldk!SystemThread_TlsOffset` at `0x10161e1ee`
- `sqldk!SystemThread_TlsOffset` at `0x10161e5f4`
- `sqldk!SystemThread_TlsOffset` at `0x10161e6a9`
- `sqldk!SystemThread_TlsOffset` at `0x10161e8b4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004885a3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004886a7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10161da39`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10161dd0a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10161dd55`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10161ddc6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10161e207`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10161e60f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10161e8cd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004885a3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004886a7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10161da39`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10161dd0a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10161dd55`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10161ddc6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10161e207`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10161e60f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10161e8cd`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10161da05`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10161db57`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10161dedc`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10161e781`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10161da05`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10161db57`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10161dedc`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10161e781`

## string_xrefs

- `0x10161d95a`: `AllocationCacheManager.cpp`
- `0x10161dd35`: `AllocationCacheManager.cpp`
- `0x10161dd78`: `AllocationCacheManager.cpp`
- `0x10161dda6`: `AllocationCacheManager.cpp`
- `0x10161e241`: `AllocationCacheManager.cpp`
- `0x10161e51d`: `AllocationCacheManager.cpp`
- `0x10161e7fb`: `AllocationCacheManager.cpp`
- `0x10161d93f`: `autoAllocationExtentCache.IsValid()`
- `0x10161dbfc`: `pageCache.IsValid() && pageCache.IsLatched()`
- `0x10161e046`: `pageCache.IsValid() && pageCache.IsLatched()`
- `0x10161dbd3`: `m_autoAllocationCaches.IsValid()`
- `0x10161e01a`: `m_autoAllocationCaches.IsValid()`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall AllocationReq::AllocateFromExistingExtents(
        _BYTE *a1,
        struct RecoveryUnit *a2,
        LARGE_INTEGER a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        _DWORD *a8,
        _DWORD *a9,
        struct PageId *a10,
        AutoAllocationCaches *a11)
{
  AutoAllocationCaches *v11; // r12
  __int64 v12; // rdx
  __int64 v13; // rcx
  PageCache *v14; // rsi
  __int64 v15; // rbx
  unsigned int v16; // r15d
  unsigned int v17; // r14d
  __int64 v18; // r13
  __int64 v19; // r15
  DirtyPageMgr *QuadPart; // rbx
  signed __int64 UniqueThread_low; // r12
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rbx
  struct PageId *v24; // r12
  __int64 v25; // r14
  _QWORD *v26; // rdx
  _DWORD *v27; // r13
  int v28; // eax
  LARGE_INTEGER v29; // r15
  unsigned int v30; // r8d
  __int64 v31; // r10
  char v32; // cl
  __int64 v33; // rcx
  __int16 v34; // cx
  _DWORD *v36; // r8
  PageCache *v37; // rsi
  __int64 v38; // rcx
  int v39; // eax
  unsigned int v40; // ebx
  __int64 v41; // rsi
  __int16 v42; // cx
  __int64 v43; // rcx
  __int64 v44; // rbx
  __int64 v45; // rdx
  __int64 v46; // r12
  PageCache *v47; // r13
  __int64 v48; // r14
  DirtyPageMgr *v49; // rbx
  signed __int64 v50; // r15
  __int64 v51; // r15
  __int64 v52; // rsi
  int v53; // eax
  __int16 v54; // ax
  __int64 v55; // rbx
  __int64 v56; // rdx
  __int64 v57; // r15
  DirtyPageMgr *v58; // rbx
  signed __int64 v59; // r12
  unsigned __int64 v60; // rcx
  unsigned __int64 v61; // rbx
  __int64 v62; // r14
  __int64 v63; // rbx
  __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // rbx
  __int64 v67; // rcx
  __int64 v68; // rdx
  int v69; // ecx
  _DWORD *v70; // r14
  __int64 v71; // rbx
  __int16 v72; // ax
  __int64 v73; // r8
  __int64 v74; // rax
  struct CSessionTraceFlags *v75; // rcx
  __int16 v76; // dx
  __int64 v77; // r9
  __int16 v78; // ax
  __int16 v79; // ax
  BOOL v80; // r15d
  __int64 v81; // rbx
  struct Worker *v82; // rcx
  PageCache *v83; // r14
  __int64 v84; // rsi
  int v85; // ebx
  __int64 v86; // rdx
  __int64 v87; // rcx
  __int64 v88; // r14
  __int64 v89; // rcx
  DirtyPageMgr *v90; // rax
  signed __int64 v91; // rcx
  __int64 v92; // rcx
  __int16 v93; // dx
  __int16 v94; // ax
  __int64 v95; // r8
  int v96; // eax
  __int64 v97; // rdx
  __int64 v98; // rcx
  __int64 v99; // r14
  __int64 v100; // r8
  __int64 v101; // rcx
  DirtyPageMgr *v102; // rax
  signed __int64 v103; // rcx
  int v104; // eax
  __int64 v105; // rdx
  __int64 v106; // rcx
  __int64 v107; // rsi
  __int64 v108; // r8
  __int64 v109; // rcx
  DirtyPageMgr *v110; // rax
  signed __int64 v111; // rcx
  int v112; // eax
  __int64 v113; // rdx
  __int64 v114; // rcx
  unsigned int v115; // r12d
  BOOL v116; // r15d
  __int64 v117; // r14
  unsigned __int16 v118; // ax
  __int16 v119; // cx
  LARGE_INTEGER v120; // r12
  __int64 v121; // r13
  __int64 v122; // rbx
  struct Worker *v123; // rcx
  __int64 v124; // rcx
  bool v125; // al
  struct PageId *v126; // r14
  _DWORD *v127; // r15
  unsigned int v128; // r8d
  __int64 v129; // r10
  char v130; // cl
  __int16 v131; // cx
  __int64 v132; // rcx
  __int64 v133; // rbx
  __int64 v134; // rdx
  __int64 v135; // r15
  PageCache *v136; // r13
  __int64 v137; // r14
  DirtyPageMgr *v138; // rbx
  signed __int64 v139; // r12
  __int64 v140; // rsi
  __int64 v141; // r8
  __int64 v142; // rcx
  DirtyPageMgr *v143; // rax
  signed __int64 v144; // rcx
  __int64 v145; // r12
  __int64 v146; // rsi
  int v147; // eax
  __int64 v148; // rdx
  __int64 v149; // rcx
  __int16 v150; // cx
  int v151; // eax
  __int64 v152; // rbx
  __int64 v153; // rcx
  __int64 v154; // rax
  __int16 v155; // cx
  __int64 v156; // rbx
  __int64 v157; // rax
  __int64 v158; // r9
  PageCache *v159; // r8
  __int64 v160; // rdx
  __int64 v161; // rax
  const struct SQLError *CurrentException; // rax
  __int64 v163; // rbx
  __int64 v164; // rax
  __int64 v165; // r9
  PageCache *v166; // r8
  __int64 v167; // rdx
  __int64 v168; // rax
  __int64 v169; // rbx
  const struct SQLError *v170; // rax
  int v171; // [rsp+28h] [rbp-450h]
  int v172; // [rsp+28h] [rbp-450h]
  int v173; // [rsp+60h] [rbp-418h] BYREF
  int v174; // [rsp+68h] [rbp-410h] BYREF
  PageCache *v175[2]; // [rsp+70h] [rbp-408h]
  __int64 v176; // [rsp+80h] [rbp-3F8h]
  __int64 v177; // [rsp+88h] [rbp-3F0h]
  char v178; // [rsp+90h] [rbp-3E8h]
  char v179; // [rsp+91h] [rbp-3E7h]
  unsigned int v180; // [rsp+94h] [rbp-3E4h] BYREF
  int v181; // [rsp+98h] [rbp-3E0h]
  unsigned int v182; // [rsp+9Ch] [rbp-3DCh]
  BOOL v183; // [rsp+A0h] [rbp-3D8h]
  __int64 v184; // [rsp+A8h] [rbp-3D0h] BYREF
  _DWORD *v185; // [rsp+B0h] [rbp-3C8h]
  struct RecoveryUnit *v186; // [rsp+B8h] [rbp-3C0h]
  struct PageId *v187; // [rsp+C0h] [rbp-3B8h] BYREF
  int v188; // [rsp+C8h] [rbp-3B0h]
  __int16 v189; // [rsp+CCh] [rbp-3ACh]
  __int16 v190; // [rsp+CEh] [rbp-3AAh]
  __int16 v191; // [rsp+D0h] [rbp-3A8h]
  __int16 v192; // [rsp+D4h] [rbp-3A4h]
  __int16 v193; // [rsp+D8h] [rbp-3A0h]
  BOOL v194; // [rsp+DCh] [rbp-39Ch]
  int v195; // [rsp+E0h] [rbp-398h]
  __int16 v196; // [rsp+E4h] [rbp-394h]
  AutoAllocationCaches *v197; // [rsp+E8h] [rbp-390h] BYREF
  int v198; // [rsp+F0h] [rbp-388h] BYREF
  __int16 v199; // [rsp+F4h] [rbp-384h]
  __int16 v200; // [rsp+F6h] [rbp-382h]
  __int64 v201; // [rsp+F8h] [rbp-380h] BYREF
  unsigned int v202; // [rsp+100h] [rbp-378h]
  LARGE_INTEGER v203; // [rsp+108h] [rbp-370h] BYREF
  LARGE_INTEGER v204; // [rsp+110h] [rbp-368h] BYREF
  int v205; // [rsp+118h] [rbp-360h]
  __int16 v206; // [rsp+11Ch] [rbp-35Ch]
  __int16 v207; // [rsp+11Eh] [rbp-35Ah]
  LARGE_INTEGER v208; // [rsp+120h] [rbp-358h]
  int v209; // [rsp+128h] [rbp-350h]
  int v210; // [rsp+12Ch] [rbp-34Ch]
  int v211; // [rsp+130h] [rbp-348h] BYREF
  int v212; // [rsp+134h] [rbp-344h]
  int v213; // [rsp+138h] [rbp-340h] BYREF
  unsigned int v214; // [rsp+13Ch] [rbp-33Ch] BYREF
  int v215; // [rsp+140h] [rbp-338h] BYREF
  int v216; // [rsp+144h] [rbp-334h]
  _DWORD *v217; // [rsp+148h] [rbp-330h]
  int v218; // [rsp+150h] [rbp-328h] BYREF
  __int16 v219; // [rsp+154h] [rbp-324h]
  __int16 v220; // [rsp+156h] [rbp-322h]
  int v221; // [rsp+158h] [rbp-320h] BYREF
  __int16 v222; // [rsp+15Ch] [rbp-31Ch]
  __int16 v223; // [rsp+15Eh] [rbp-31Ah]
  int v224; // [rsp+160h] [rbp-318h] BYREF
  __int16 v225; // [rsp+164h] [rbp-314h]
  __int16 v226; // [rsp+166h] [rbp-312h]
  int v227; // [rsp+168h] [rbp-310h] BYREF
  __int16 v228; // [rsp+16Ch] [rbp-30Ch]
  _DWORD *v229; // [rsp+170h] [rbp-308h]
  __int128 v230; // [rsp+178h] [rbp-300h] BYREF
  _QWORD v231[2]; // [rsp+188h] [rbp-2F0h] BYREF
  int v232; // [rsp+198h] [rbp-2E0h]
  char v233; // [rsp+19Ch] [rbp-2DCh]
  int v234; // [rsp+1A0h] [rbp-2D8h]
  char v235; // [rsp+1A4h] [rbp-2D4h]
  int v236; // [rsp+1A8h] [rbp-2D0h]
  __int16 v237; // [rsp+1ACh] [rbp-2CCh]
  __int16 v238; // [rsp+1AEh] [rbp-2CAh]
  __int64 v239; // [rsp+1B0h] [rbp-2C8h] BYREF
  char v240; // [rsp+1B8h] [rbp-2C0h]
  unsigned int v241; // [rsp+1BCh] [rbp-2BCh]
  __int64 v242; // [rsp+1C0h] [rbp-2B8h] BYREF
  char v243; // [rsp+1C8h] [rbp-2B0h]
  unsigned int v244; // [rsp+1CCh] [rbp-2ACh]
  int v245; // [rsp+1D0h] [rbp-2A8h]
  __int16 v246; // [rsp+1D4h] [rbp-2A4h]
  int v247; // [rsp+1D6h] [rbp-2A2h]
  __int16 v248; // [rsp+1DAh] [rbp-29Eh]
  int v249; // [rsp+1DCh] [rbp-29Ch]
  __int16 v250; // [rsp+1E0h] [rbp-298h]
  __int128 v251; // [rsp+1E8h] [rbp-290h] BYREF
  __int128 v252; // [rsp+1F8h] [rbp-280h] BYREF
  int v253; // [rsp+208h] [rbp-270h]
  char v254; // [rsp+20Ch] [rbp-26Ch]
  int v255; // [rsp+210h] [rbp-268h]
  char v256; // [rsp+214h] [rbp-264h]
  int v257; // [rsp+218h] [rbp-260h]
  int v258; // [rsp+21Ch] [rbp-25Ch]
  __int16 v259; // [rsp+220h] [rbp-258h]
  int v260; // [rsp+228h] [rbp-250h]
  int v261; // [rsp+22Ch] [rbp-24Ch]
  __int16 v262; // [rsp+230h] [rbp-248h]
  LARGE_INTEGER v263; // [rsp+238h] [rbp-240h] BYREF
  LARGE_INTEGER v264; // [rsp+240h] [rbp-238h] BYREF
  __int64 v265; // [rsp+248h] [rbp-230h]
  __int64 v266; // [rsp+250h] [rbp-228h]
  LARGE_INTEGER v267; // [rsp+258h] [rbp-220h] BYREF
  LARGE_INTEGER v268; // [rsp+260h] [rbp-218h] BYREF
  __int64 v269; // [rsp+268h] [rbp-210h]
  int v270; // [rsp+270h] [rbp-208h]
  int v271; // [rsp+274h] [rbp-204h]
  int v272; // [rsp+278h] [rbp-200h]
  LARGE_INTEGER v274; // [rsp+280h] [rbp-1F8h] BYREF
  __int64 v275; // [rsp+288h] [rbp-1F0h]
  LARGE_INTEGER PerformanceCount; // [rsp+290h] [rbp-1E8h] BYREF
  BOOL v277; // [rsp+298h] [rbp-1E0h] BYREF
  __int64 v278; // [rsp+2A0h] [rbp-1D8h]
  __int64 v279; // [rsp+2A8h] [rbp-1D0h]
  _BYTE v280[16]; // [rsp+2B0h] [rbp-1C8h] BYREF
  _BYTE v281[16]; // [rsp+2C0h] [rbp-1B8h] BYREF
  _BYTE v282[12]; // [rsp+2D0h] [rbp-1A8h] BYREF
  int v283; // [rsp+2DCh] [rbp-19Ch]
  __int16 v284; // [rsp+2E0h] [rbp-198h]
  __int64 v285; // [rsp+2F0h] [rbp-188h]
  __int64 v286; // [rsp+2F8h] [rbp-180h]
  PageCache *v287; // [rsp+300h] [rbp-178h]
  PageCache *v288; // [rsp+308h] [rbp-170h]
  __int64 v289; // [rsp+310h] [rbp-168h]
  __int64 v290; // [rsp+318h] [rbp-160h]
  PageCache *v291; // [rsp+320h] [rbp-158h]
  _QWORD *v292; // [rsp+328h] [rbp-150h]
  __int64 v293; // [rsp+330h] [rbp-148h]
  __int64 v294; // [rsp+338h] [rbp-140h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+340h] [rbp-138h]
  __int64 *v296; // [rsp+348h] [rbp-130h]
  __int64 v297; // [rsp+350h] [rbp-128h]
  struct CSessionTraceFlags *v298; // [rsp+358h] [rbp-120h]
  __int64 v299; // [rsp+360h] [rbp-118h]
  _QWORD *v300; // [rsp+368h] [rbp-110h]
  __int64 v301; // [rsp+370h] [rbp-108h]
  __int64 v302; // [rsp+378h] [rbp-100h]
  PageCache *v303; // [rsp+380h] [rbp-F8h]
  _QWORD *v304; // [rsp+388h] [rbp-F0h]
  _BYTE v305[24]; // [rsp+390h] [rbp-E8h] BYREF
  _BYTE v306[24]; // [rsp+3A8h] [rbp-D0h] BYREF
  _BYTE v307[12]; // [rsp+3C0h] [rbp-B8h] BYREF
  __int16 v308; // [rsp+3CCh] [rbp-ACh]
  char v309; // [rsp+3CEh] [rbp-AAh]
  int v310; // [rsp+3D0h] [rbp-A8h] BYREF
  __int16 v311; // [rsp+3D4h] [rbp-A4h]
  __int16 v312; // [rsp+3D6h] [rbp-A2h]
  int v313; // [rsp+3D8h] [rbp-A0h]
  __int16 v314; // [rsp+3DCh] [rbp-9Ch]
  __int16 v315; // [rsp+3DEh] [rbp-9Ah]
  int v316; // [rsp+3E0h] [rbp-98h]
  int v317; // [rsp+3E4h] [rbp-94h]
  __int16 v318; // [rsp+3E8h] [rbp-90h]
  __int16 v319; // [rsp+3EAh] [rbp-8Eh]
  int v320; // [rsp+3ECh] [rbp-8Ch]
  int v321; // [rsp+3F0h] [rbp-88h] BYREF
  __int16 v322; // [rsp+3F4h] [rbp-84h]
  __int16 v323; // [rsp+3F6h] [rbp-82h]
  int v324; // [rsp+3F8h] [rbp-80h]
  __int16 v325; // [rsp+3FCh] [rbp-7Ch]
  __int16 v326; // [rsp+3FEh] [rbp-7Ah]
  int v327; // [rsp+400h] [rbp-78h]
  int v328; // [rsp+404h] [rbp-74h]
  __int16 v329; // [rsp+408h] [rbp-70h]
  __int16 v330; // [rsp+40Ah] [rbp-6Eh]
  int v331; // [rsp+40Ch] [rbp-6Ch]
  int v332; // [rsp+410h] [rbp-68h] BYREF
  __int64 v333; // [rsp+414h] [rbp-64h]
  __int16 v334; // [rsp+41Ch] [rbp-5Ch]
  char v335; // [rsp+41Eh] [rbp-5Ah]
  int v336; // [rsp+420h] [rbp-58h] BYREF
  __int64 v337; // [rsp+424h] [rbp-54h]
  __int16 v338; // [rsp+42Ch] [rbp-4Ch]
  char v339; // [rsp+42Eh] [rbp-4Ah]

  v294 = -2;
  v208 = a3;
  v186 = a2;
  v185 = a1;
  v229 = a1;
  v203.QuadPart = (LONGLONG)a2;
  v204 = a3;
  v184 = a5;
  v201 = a7;
  *(_QWORD *)v307 = a9;
  v217 = a9;
  v187 = a10;
  v11 = a11;
  v197 = a11;
  v283 = 0;
  v284 = 0;
  v174 = 1;
  *(_OWORD *)v175 = 0;
  v176 = 0;
  v177 = 0;
  v12 = *(_QWORD *)a1;
  LOWORD(v180) = *(_WORD *)(*(_QWORD *)a1 + 32LL);
  v277 = (a1[8] & 2) == 0;
  v13 = *(_QWORD *)(v12 + 64);
  v278 = *(_QWORD *)(v12 + 56);
  v279 = v13;
  AutoAllocationCaches::GetAllocationExtentCache(a11, (struct AutoPageCache *)&v174);
  v14 = v175[0];
  if ( !v175[0] )
  {
    utassert_fail(1u, "autoAllocationExtentCache.IsValid()", "Alloc.cpp", 4851, 0);
    utassert_fail(1u, "IsValid()", "AllocationCacheManager.cpp", 2063, 0);
  }
  HIDWORD(v177) = 2;
  v171 = 0;
  v15 = v176;
  LODWORD(v177) = LatchBase::AcquireInternal(v176, 2, 0xFFFFFFFFLL);
  v16 = 0;
  while ( 1 )
  {
    v202 = v16;
    if ( v16 >= *((_DWORD *)v14 + 3) )
      break;
    v173 = 2;
    v17 = *((_DWORD *)v14 + 3);
    if ( v16 >= (3 * v17) >> 2 )
    {
      LatchBase::ReleaseInternal(v15, HIDWORD(v177));
      LODWORD(v177) = 0;
      AutoAllocationCaches::GrowCaches(v11, v17);
      HIDWORD(v177) = 2;
      v171 = 0;
      LODWORD(v177) = LatchBase::AcquireInternal(v15, 2, 0xFFFFFFFFLL);
    }
    v18 = 40LL * v16;
    v19 = v18 + *((_QWORD *)v14 + 5);
    QuadPart = 0;
    UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *(_DWORD *)(v19 + 24)
      || _InterlockedCompareExchange64((volatile signed __int64 *)(v19 + 24), UniqueThread_low, 0) )
    {
      v88 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v95 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v95 && *(_QWORD *)(v95 + 272) == v95 )
          v88 = *(_QWORD *)(v95 + 256);
        if ( v88 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v274);
            QuadPart = (DirtyPageMgr *)v274.QuadPart;
          }
          else
          {
            QuadPart = MEMORY[0x7FFE0008];
          }
        }
      }
      v89 = v19 + 24;
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<319,1,258>::SpinToAcquireWithExponentialBackoff(v89, UniqueThread_low);
      else
        Spinlock<319,1,258>::SpinToAcquireOptimistic(v89, v88, UniqueThread_low);
      if ( v88 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v90 = (DirtyPageMgr *)PerformanceCount.QuadPart;
        }
        else
        {
          v90 = MEMORY[0x7FFE0008];
        }
        v91 = v90 - QuadPart;
        if ( v90 < QuadPart )
          v91 = 0;
        *(_QWORD *)(v88 + 3192) += v91;
      }
    }
    v22 = *(_QWORD *)(*((_QWORD *)v14 + 5) + v18);
    v23 = HIWORD(v22);
    v24 = v187;
    *(_DWORD *)v187 = v22;
    *((_WORD *)v24 + 2) = WORD2(v22);
    v25 = *((_QWORD *)v14 + 5);
    if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v96 = rand();
      v97 = (unsigned int)(v96 / 5);
      v98 = (unsigned int)(5 * v97);
      if ( v96 == (_DWORD)v98 )
        Spinlock<319,1,258>::UpdateStatSnapshot(v98, v97);
    }
    *(_QWORD *)(v25 + v18 + 24) = 0;
    if ( !(_WORD)v23 )
    {
      *(_DWORD *)v24 = 0;
      *((_WORD *)v24 + 2) = 0;
LABEL_28:
      if ( !*((_WORD *)v24 + 2) )
        goto LABEL_29;
      goto LABEL_12;
    }
    if ( !*(_DWORD *)v24 )
      goto LABEL_28;
LABEL_12:
    if ( (unsigned int)IsPageValidForAllocation(v186, v24) )
      goto LABEL_13;
LABEL_29:
    v36 = *(_DWORD **)v307;
    if ( !**(_DWORD **)v307 )
    {
      v55 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v56 = *(_QWORD *)(v55 + 256);
      if ( !v56 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v56 = *(_QWORD *)(v55 + 256);
        v36 = *(_DWORD **)v307;
      }
      if ( _InterlockedCompareExchange64(
             (volatile signed __int64 *)(*((_QWORD *)v14 + 5) + v18 + 8),
             *(_QWORD *)(v56 + 600),
             0) )
      {
        goto LABEL_76;
      }
    }
    if ( *v36 )
    {
LABEL_31:
      **(_DWORD **)v307 = 1;
      v37 = v175[0];
      v38 = *((_QWORD *)v175[0] + 6);
      if ( (*(_BYTE *)(v38 + 24) & 3) == 0 )
        goto LABEL_32;
      if ( !*a8 )
      {
        if ( *(_DWORD *)(v38 + 28) || _InterlockedCompareExchange((volatile signed __int32 *)(v38 + 28), 1, 0) )
        {
LABEL_32:
          v39 = v177;
          v40 = HIDWORD(v177);
          v41 = v176;
          if ( (_DWORD)v177 )
          {
            LatchBase::ReleaseInternal(v176, HIDWORD(v177));
            v39 = 0;
            LODWORD(v177) = 0;
          }
          *(_OWORD *)v175 = 0;
          if ( !v39 )
            return 0;
          v86 = v40;
          v87 = v41;
LABEL_127:
          LatchBase::ReleaseInternal(v87, v86);
          LODWORD(v177) = 0;
          return 0;
        }
        v37 = v175[0];
      }
      v251 = 0;
      v252 = 0;
      v253 = 0;
      v254 = 0;
      v255 = 0;
      v256 = 0;
      v194 = *a8 == 0;
      v70 = v185;
      v71 = *(_QWORD *)v185;
      if ( !*(_QWORD *)v185 )
        utassert_fail(1u, "ap", "SpaceScan.cpp", 68, 0);
      *(_QWORD *)&v251 = v71;
      *((_QWORD *)&v251 + 1) = *(_QWORD *)v71;
      v72 = *(_WORD *)(v71 + 40);
      v218 = *(_DWORD *)(v71 + 36);
      v219 = v72;
      v220 = 0;
      AllocationCachesManager::GetAllocationCaches(
        *(AllocationCachesManager **)(*(_QWORD *)(*((_QWORD *)&v251 + 1) + 48LL) + 1816LL),
        (const struct AllocationCachesId *)&v218,
        (struct AutoAllocationCaches *)&v252);
      if ( !(_QWORD)v252 )
        utassert_fail(1u, "m_autoAllocationCaches.IsValid()", "SpaceScan.cpp", 81, 0);
      if ( !(_DWORD)v177 )
        utassert_fail(1u, "pageCache.IsValid() && pageCache.IsLatched()", "SpaceScan.cpp", 83, 0);
      v255 = *((_DWORD *)v37 + 14);
      LatchBase::ReleaseInternal(v176, HIDWORD(v177));
      LODWORD(v177) = 0;
      try
      {
        v319 = 0;
        v245 = 0;
        v246 = 0;
        v257 = 0;
        v258 = 0;
        v259 = 0;
        v247 = 0;
        v248 = 0;
        v313 = 0;
        v314 = 0;
        v315 = 0;
        v310 = 0;
        v311 = 0;
        v312 = 0;
        v320 = 0;
        v316 = 0;
        v317 = 0;
        v318 = 0;
        v73 = 1;
        v182 = 1;
        if ( *a8 )
          goto LABEL_190;
        v181 = 1;
        v188 = 0;
        v189 = 0;
        v190 = 0;
        if ( *(_WORD *)(*(_QWORD *)(**(_QWORD **)v70 + 48LL) + 1720LL) != 2 && (byte_10317AC11 & 0x10) == 0 )
        {
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          v296 = (__int64 *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset);
          v74 = *v296;
          v297 = v74;
          if ( v74 )
          {
            v75 = **(struct CSessionTraceFlags ***)(v74 + 56);
            v298 = v75;
            if ( v75 )
            {
              if ( CSessionTraceFlags::CheckSessionTraceInternal(v75, 0x48Cu) )
              {
                v73 = v182;
                goto LABEL_107;
              }
            }
          }
          v299 = *(_QWORD *)v70;
          v205 = *(_DWORD *)(v299 + 36);
          v76 = *(_WORD *)(v299 + 40);
          v206 = v76;
          v207 = 0;
          v188 = v205;
          v189 = v76;
          v190 = 0;
          v77 = *(_QWORD *)(*(_QWORD *)(v299 + 16) + 8LL);
          v301 = v77 + 960;
          v209 = 0;
          if ( v205 != *(_DWORD *)(v77 + 960) )
            goto LABEL_141;
          if ( v76 == 1 )
            v76 = 0;
          v191 = v76;
          v78 = 0;
          if ( *(_WORD *)(v77 + 964) != 1 )
            v78 = *(_WORD *)(v77 + 964);
          if ( v76 == v78 )
          {
            v209 = 1;
            if ( *(_QWORD *)(v77 + 1008) >= 6 * (*(_QWORD *)(v77 + 1016) / 8LL) )
              goto LABEL_103;
            v69 = 0;
LABEL_79:
            v181 = v69;
          }
          else
          {
LABEL_141:
            v265 = v77;
            v302 = v77 + 1144;
            if ( *(_QWORD *)(v77 + 1144) )
              v92 = *(_QWORD *)(v77 + 1144);
            else
              v92 = v265;
            v236 = *(_DWORD *)(v92 + 1080);
            v93 = *(_WORD *)(v92 + 1084);
            v237 = v93;
            v238 = 0;
            v210 = 0;
            if ( v205 != v236 )
              goto LABEL_187;
            v94 = v206;
            if ( v206 == 1 )
              v94 = 0;
            v192 = v94;
            if ( v93 == 1 )
              v93 = 0;
            v193 = v93;
            if ( v94 != v93 )
            {
LABEL_187:
              v69 = v181;
              if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v70 + 16LL) + 8LL) + 1064LL) < 6
                                                                                               * (*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v70 + 16LL) + 8LL) + 1072LL)
                                                                                                / 8LL) )
                v69 = 0;
              goto LABEL_79;
            }
            v210 = 1;
            if ( *(_QWORD *)(v92 + 1120) < 6 * (*(_QWORD *)(v92 + 1128) / 8LL) )
            {
              v69 = 0;
              goto LABEL_79;
            }
LABEL_103:
            v69 = v181;
          }
          v73 = v182;
          if ( !v69 )
            v73 = 3;
          v182 = v73;
        }
LABEL_107:
        if ( *a8 )
        {
LABEL_190:
          v73 = v73 & 0xFFFFFFFA | 4;
          v182 = v73;
        }
        v244 = v244 & 0xFFFFFFFC | 2;
        v243 = 0;
        v242 = 0;
        v211 = 0;
        SpaceScan::Scan(&v251, 1, v73, &v310, &v173, &v242, &v211, 0, 0);
        v195 = v313;
        v79 = v314;
        v196 = v314;
        *(_DWORD *)v24 = v313;
        *((_WORD *)v24 + 2) = v79;
      }
      catch ( SQLError v306 )
      {
        try
        {
          ExceptionBackout::ExceptionBackout((ExceptionBackout *)v281, (const struct SQLError *)v306);
          AutoPageCache::Latch(&v174, 2);
          if ( v194 )
          {
            v303 = v175[0];
            *(_DWORD *)(*((_QWORD *)v175[0] + 6) + 28LL) = 0;
            v194 = 0;
          }
          v270 = 88;
          v304 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v156 = v304[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v285 = v156;
          v157 = *(_QWORD *)(v156 + 256);
          v266 = v157;
          if ( !v157 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v157 = *(_QWORD *)(v156 + 256);
            v266 = v157;
          }
          v158 = *(_QWORD *)(v157 + 600);
          v286 = v158;
          v159 = v175[0];
          v287 = v175[0];
          v178 = 0;
          v160 = 0;
          v212 = 0;
          while ( (unsigned int)v160 < *((_DWORD *)v159 + 3) )
          {
            v161 = *((_QWORD *)v159 + 5);
            if ( *(_QWORD *)(v161 + 40 * v160 + 8) == v158 )
            {
              *(_QWORD *)(v161 + 40 * v160 + 8) = 0;
              v178 = 1;
            }
            v160 = (unsigned int)(v160 + 1);
            v212 = v160;
          }
          AutoPageCache::UnLatch((AutoPageCache *)&v174);
          CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v281);
          ExceptionRethrow(CurrentException);
          ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v281);
        }
        catch ( ShortStackException )
        {
        }
        v185 = v229;
        v186 = (struct RecoveryUnit *)v203.QuadPart;
        v208 = v204;
        v24 = v187;
      }
      v80 = v194;
      v81 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v82 = *(struct Worker **)(v81 + 256);
      if ( !v82 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v82 = *(struct Worker **)(v81 + 256);
      }
      if ( *((_DWORD *)v82 + 139) )
        ExceptionPostCatchActions(v82);
      v83 = v175[0];
      if ( !v175[0] )
        utassert_fail(1u, "IsValid()", "AllocationCacheManager.cpp", 2063, 0);
      HIDWORD(v177) = 2;
      v171 = 0;
      v84 = v176;
      v85 = LatchBase::AcquireInternal(v176, 2, 0xFFFFFFFFLL);
      LODWORD(v177) = v85;
      if ( v80 )
        *(_DWORD *)(*((_QWORD *)v83 + 6) + 28LL) = 0;
      if ( !*(_DWORD *)v24 && !*((_WORD *)v24 + 2) )
      {
        if ( (_QWORD)v252 )
          AutoAllocationCaches::Release((AutoAllocationCaches *)&v252);
        if ( v83 )
        {
          if ( v85 )
          {
            LatchBase::ReleaseInternal(v84, 2);
            v85 = 0;
            LODWORD(v177) = 0;
          }
          *(_OWORD *)v175 = 0;
        }
        if ( v85 )
        {
          v86 = 2;
          v87 = v84;
          goto LABEL_127;
        }
        return 0;
      }
      v27 = *(_DWORD **)v307;
      **(_DWORD **)v307 = 0;
      v26 = (_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset);
      if ( !v26[32] )
        SystemThread::MakeMiniSOSThread(0);
      if ( (_QWORD)v252 )
        AutoAllocationCaches::Release((AutoAllocationCaches *)&v252);
      goto LABEL_14;
    }
    v57 = v18 + *((_QWORD *)v14 + 5);
    v58 = 0;
    v59 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *(_DWORD *)(v57 + 24) || _InterlockedCompareExchange64((volatile signed __int64 *)(v57 + 24), v59, 0) )
    {
      v99 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v100 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v100 && *(_QWORD *)(v100 + 272) == v100 )
          v99 = *(_QWORD *)(v100 + 256);
        if ( v99 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v263);
            v58 = (DirtyPageMgr *)v263.QuadPart;
          }
          else
          {
            v58 = MEMORY[0x7FFE0008];
          }
        }
      }
      v101 = v57 + 24;
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<319,1,258>::SpinToAcquireWithExponentialBackoff(v101, v59);
      else
        Spinlock<319,1,258>::SpinToAcquireOptimistic(v101, v99, v59);
      if ( v99 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v264);
          v102 = (DirtyPageMgr *)v264.QuadPart;
        }
        else
        {
          v102 = MEMORY[0x7FFE0008];
        }
        v103 = v102 - v58;
        if ( v102 < v58 )
          v103 = 0;
        *(_QWORD *)(v99 + 3192) += v103;
      }
    }
    v60 = *(_QWORD *)(*((_QWORD *)v14 + 5) + v18);
    v61 = HIWORD(v60);
    v24 = v187;
    *(_DWORD *)v187 = v60;
    *((_WORD *)v24 + 2) = WORD2(v60);
    v62 = *((_QWORD *)v14 + 5);
    if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v104 = rand();
      v105 = (unsigned int)(v104 / 5);
      v106 = (unsigned int)(5 * v105);
      if ( v104 == (_DWORD)v106 )
        Spinlock<319,1,258>::UpdateStatSnapshot(v106, v105);
    }
    *(_QWORD *)(v62 + v18 + 24) = 0;
    if ( (_WORD)v61 )
    {
      if ( *(_DWORD *)v24 )
        goto LABEL_65;
    }
    else
    {
      *(_DWORD *)v24 = 0;
      *((_WORD *)v24 + 2) = 0;
    }
    if ( !*((_WORD *)v24 + 2) )
      goto LABEL_31;
LABEL_65:
    if ( !(unsigned int)IsPageValidForAllocation(v186, v24) )
      goto LABEL_31;
    v26 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v63 = v26[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v64 = *(_QWORD *)(v63 + 256);
    if ( !v64 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v64 = *(_QWORD *)(v63 + 256);
    }
    v65 = *((_QWORD *)v14 + 5);
    if ( *(_QWORD *)(v65 + v18 + 8) == *(_QWORD *)(v64 + 600) )
      *(_QWORD *)(v65 + v18 + 8) = 0;
    if ( *v217 )
      goto LABEL_31;
LABEL_13:
    v27 = *(_DWORD **)v307;
LABEL_14:
    v28 = v173;
    v29 = v208;
    if ( v173 == 2 )
    {
      LOBYTE(v26) = 4;
      v28 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))LockExtent)(
              v24,
              v26,
              0,
              (LARGE_INTEGER)v208.QuadPart);
      v173 = v28;
    }
    if ( (unsigned int)(v28 + 1) > 2 )
      goto LABEL_76;
    v213 = 0;
    v14 = v175[0];
    if ( !v175[0] )
      utassert_fail(1u, "IsValid()", "AllocationCacheManager.cpp", 2111, 0);
    v15 = v176;
    LatchBase::ReleaseInternal(v176, HIDWORD(v177));
    LODWORD(v177) = 0;
    v30 = v185[2];
    v31 = *(_QWORD *)v185;
    v221 = *(_DWORD *)(*(_QWORD *)v185 + 36LL);
    v222 = *(_WORD *)(v31 + 40);
    v223 = 0;
    v32 = (v30 >> 10) & 4 | 0x88;
    if ( (v30 & 0x2000) == 0 )
      v32 = (v30 >> 10) & 4;
    LOBYTE(v171) = v32;
    if ( (unsigned int)TargetExtentMgr::AllocPageFromTargetExtent(
                         &v277,
                         *(_QWORD *)v31,
                         v186,
                         (unsigned __int16)v180,
                         v24,
                         v171,
                         &v221,
                         v184,
                         a6,
                         &v227,
                         &v213,
                         0) )
    {
      v33 = v201;
      *(_DWORD *)(v201 + 8) = v227;
      *(_WORD *)(v33 + 12) = v228;
      *(_WORD *)(v33 + 14) = 0;
      *(_QWORD *)v33 = 0;
      *(_DWORD *)(v33 + 28) = 2;
      *(_QWORD *)(v33 + 16) = 0;
      *(_WORD *)(v33 + 24) = 0;
      if ( v173 != -1 )
      {
        v34 = *(_WORD *)(*(_QWORD *)(v29.QuadPart + 48) + 1720LL);
        v309 = 8;
        v308 = v34;
        *(_QWORD *)&v307[4] = 0;
        *(_DWORD *)v307 = *(_DWORD *)v24;
        *(_WORD *)&v307[4] = *((_WORD *)v24 + 2);
        lck_releaseClasses(v29.QuadPart + 56, v307, 0, 0);
      }
      if ( v14 )
        *(_OWORD *)v175 = 0;
      return 1;
    }
    if ( v173 != -1 )
    {
      v42 = *(_WORD *)(*(_QWORD *)(v29.QuadPart + 48) + 1720LL);
      v339 = 8;
      v338 = v42;
      v337 = 0;
      v336 = *(_DWORD *)v24;
      LOWORD(v337) = *((_WORD *)v24 + 2);
      lck_releaseClasses(v29.QuadPart + 56, &v336, 0, 0);
    }
    if ( !v14 )
      utassert_fail(1u, "IsValid()", "AllocationCacheManager.cpp", 2063, 0);
    HIDWORD(v177) = 2;
    LODWORD(v177) = LatchBase::AcquireInternal(v15, 2, 0xFFFFFFFFLL);
    v43 = *(_QWORD *)v185;
    v224 = *(_DWORD *)(*(_QWORD *)v185 + 36LL);
    v225 = *(_WORD *)(v43 + 40);
    v226 = 0;
    if ( !PageCache::RemoveEntry(
            v14,
            (const struct PageCacheTraceData *)v282,
            v24,
            &v214,
            v186,
            (const struct AllocUnitId *)&v224)
      || *v27 )
    {
LABEL_77:
      v16 = v202 + 1;
      v11 = v197;
    }
    else
    {
      v44 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v45 = *(_QWORD *)(v44 + 256);
      if ( !v45 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v45 = *(_QWORD *)(v44 + 256);
      }
      v46 = 40LL * v214;
      v47 = v175[0];
      if ( _InterlockedCompareExchange64(
             (volatile signed __int64 *)(*((_QWORD *)v175[0] + 5) + v46 + 8),
             *(_QWORD *)(v45 + 600),
             0) )
      {
        goto LABEL_76;
      }
      v48 = v46 + *((_QWORD *)v47 + 5);
      v49 = 0;
      v50 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)(v48 + 24) || _InterlockedCompareExchange64((volatile signed __int64 *)(v48 + 24), v50, 0) )
      {
        v107 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v108 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v108 && *(_QWORD *)(v108 + 272) == v108 )
            v107 = *(_QWORD *)(v108 + 256);
          if ( v107 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v267);
              v49 = (DirtyPageMgr *)v267.QuadPart;
            }
            else
            {
              v49 = MEMORY[0x7FFE0008];
            }
          }
        }
        v109 = v48 + 24;
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<319,1,258>::SpinToAcquireWithExponentialBackoff(v109, v50);
        else
          Spinlock<319,1,258>::SpinToAcquireOptimistic(v109, v107, v50);
        if ( v107 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v268);
            v110 = (DirtyPageMgr *)v268.QuadPart;
          }
          else
          {
            v110 = MEMORY[0x7FFE0008];
          }
          v111 = v110 - v49;
          if ( v110 < v49 )
            v111 = 0;
          *(_QWORD *)(v107 + 3192) += v111;
        }
      }
      v51 = *((_QWORD *)v47 + 5);
      v52 = *(_QWORD *)(v51 + v46);
      if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v112 = rand();
        v113 = (unsigned int)(v112 / 5);
        v114 = (unsigned int)(5 * v113);
        if ( v112 == (_DWORD)v114 )
          Spinlock<319,1,258>::UpdateStatSnapshot(v114, v113);
      }
      *(_QWORD *)(v51 + v46 + 24) = 0;
      v53 = 0;
      if ( HIWORD(v52) )
        v53 = v52;
      if ( v53 )
        goto LABEL_72;
      v54 = 0;
      if ( HIWORD(v52) )
        v54 = WORD2(v52);
      if ( v54 )
      {
LABEL_72:
        v66 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v67 = *(_QWORD *)(v66 + 256);
        if ( !v67 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v67 = *(_QWORD *)(v66 + 256);
        }
        v68 = *((_QWORD *)v47 + 5);
        if ( *(_QWORD *)(v68 + v46 + 8) == *(_QWORD *)(v67 + 600) )
          *(_QWORD *)(v68 + v46 + 8) = 0;
LABEL_76:
        v14 = v175[0];
        v15 = v176;
        goto LABEL_77;
      }
      **(_DWORD **)v307 = 1;
      v15 = v176;
      v14 = v175[0];
      v16 = v202 + 1;
      v11 = v197;
    }
  }
  if ( (*(_BYTE *)(*((_QWORD *)v14 + 6) + 24LL) & 3) == 0 )
  {
LABEL_292:
    if ( v14 )
    {
      if ( (_DWORD)v177 )
      {
        LatchBase::ReleaseInternal(v15, HIDWORD(v177));
        LODWORD(v177) = 0;
      }
      *(_OWORD *)v175 = 0;
    }
    goto LABEL_239;
  }
  v230 = 0;
  v231[0] = 0;
  v231[1] = 0;
  v232 = 0;
  v233 = 0;
  v234 = 0;
  v235 = 0;
  if ( *a8 )
  {
    v115 = 4;
    v116 = 0;
    v183 = 0;
  }
  else
  {
    v124 = *((_QWORD *)v14 + 6);
    if ( *(_DWORD *)(v124 + 28) )
    {
      v125 = 0;
    }
    else
    {
      v125 = _InterlockedCompareExchange((volatile signed __int32 *)(v124 + 28), 1, 0) == 0;
      v15 = v176;
      v14 = v175[0];
    }
    v116 = v125;
    v183 = v125;
    v115 = v125;
  }
  v117 = *(_QWORD *)v185;
  if ( !*(_QWORD *)v185 )
    utassert_fail(1u, "ap", "SpaceScan.cpp", 68, 0);
  *(_QWORD *)&v230 = v117;
  *((_QWORD *)&v230 + 1) = *(_QWORD *)v117;
  v118 = *(_WORD *)(v117 + 40);
  LODWORD(v197) = *(_DWORD *)(v117 + 36);
  HIDWORD(v197) = v118;
  AllocationCachesManager::GetAllocationCaches(
    *(AllocationCachesManager **)(*(_QWORD *)(*((_QWORD *)&v230 + 1) + 48LL) + 1816LL),
    (const struct AllocationCachesId *)&v197,
    (struct AutoAllocationCaches *)v231);
  if ( !v231[0] )
    utassert_fail(1u, "m_autoAllocationCaches.IsValid()", "SpaceScan.cpp", 81, 0);
  if ( !(_DWORD)v177 )
    utassert_fail(1u, "pageCache.IsValid() && pageCache.IsLatched()", "SpaceScan.cpp", 83, 0);
  v234 = *((_DWORD *)v14 + 14);
  LatchBase::ReleaseInternal(v15, HIDWORD(v177));
  LODWORD(v177) = 0;
  try
  {
    v330 = 0;
    v249 = 0;
    v250 = 0;
    v260 = 0;
    v261 = 0;
    v262 = 0;
    LODWORD(v217) = 0;
    WORD2(v217) = 0;
    v324 = 0;
    v325 = 0;
    v326 = 0;
    v321 = 0;
    v322 = 0;
    v323 = 0;
    v331 = 0;
    v327 = 0;
    v328 = 0;
    v329 = 0;
    v241 = v241 & 0xFFFFFFFC | 2;
    v240 = 0;
    v239 = 0;
    v215 = 0;
    SpaceScan::Scan(&v230, 1, v115, &v321, &v173, &v239, &v215, 0, 0);
    v195 = v324;
    v119 = v325;
    v196 = v325;
    v126 = v187;
    *(_DWORD *)v187 = v324;
    *((_WORD *)v126 + 2) = v119;
  }
  catch ( SQLError v305 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v280, (const struct SQLError *)v305);
      AutoPageCache::Latch(&v174, 2);
      if ( v183 )
      {
        v288 = v175[0];
        *(_DWORD *)(*((_QWORD *)v175[0] + 6) + 28LL) = 0;
        v183 = 0;
      }
      if ( **(_DWORD **)v307 )
      {
        v271 = 88;
        v300 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v163 = v300[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v289 = v163;
        v164 = *(_QWORD *)(v163 + 256);
        v269 = v164;
        if ( !v164 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v164 = *(_QWORD *)(v163 + 256);
          v269 = v164;
        }
        v165 = *(_QWORD *)(v164 + 600);
        v290 = v165;
        v166 = v175[0];
        v291 = v175[0];
        v179 = 0;
        v167 = 0;
        v216 = 0;
        while ( (unsigned int)v167 < *((_DWORD *)v166 + 3) )
        {
          v168 = *((_QWORD *)v166 + 5);
          if ( *(_QWORD *)(v168 + 40 * v167 + 8) == v165 )
          {
            *(_QWORD *)(v168 + 40 * v167 + 8) = 0;
            v179 = 1;
          }
          v167 = (unsigned int)(v167 + 1);
          v216 = v167;
        }
      }
      v272 = 88;
      v292 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v169 = v292[SystemThread_TlsIndex] + SystemThread_TlsOffset;
      v293 = v169;
      v275 = *(_QWORD *)(v169 + 256);
      if ( !v275 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v275 = *(_QWORD *)(v169 + 256);
      }
      AutoPageCache::UnLatch((AutoPageCache *)&v174);
      v170 = ExceptionBackout::GetCurrentException((ExceptionBackout *)v280);
      ExceptionRethrow(v170);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v280);
    }
    catch ( ShortStackException )
    {
    }
    v116 = v183;
    v185 = v229;
    v186 = (struct RecoveryUnit *)v203.QuadPart;
    v120 = v204;
    v126 = v187;
    goto LABEL_223;
  }
  v120 = v208;
LABEL_223:
  v121 = v201;
  v122 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v123 = *(struct Worker **)(v122 + 256);
  if ( !v123 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v123 = *(struct Worker **)(v122 + 256);
  }
  if ( *((_DWORD *)v123 + 139) )
    ExceptionPostCatchActions(v123);
  v14 = v175[0];
  if ( v116 )
  {
    if ( !v175[0] )
      utassert_fail(1u, "IsValid()", "AllocationCacheManager.cpp", 2063, 0);
    HIDWORD(v177) = 2;
    v172 = 0;
    v15 = v176;
    LODWORD(v177) = LatchBase::AcquireInternal(v176, 2, 0xFFFFFFFFLL);
    *(_DWORD *)(*((_QWORD *)v14 + 6) + 28LL) = 0;
    LatchBase::ReleaseInternal(v15, 2);
    LODWORD(v177) = 0;
  }
  else
  {
    v15 = v176;
  }
  if ( !*(_DWORD *)v126 && !*((_WORD *)v126 + 2) )
  {
    if ( v231[0] )
      AutoAllocationCaches::Release((AutoAllocationCaches *)v231);
    if ( v14 )
    {
      if ( (_DWORD)v177 )
      {
        LatchBase::ReleaseInternal(v15, HIDWORD(v177));
        LODWORD(v177) = 0;
      }
      *(_OWORD *)v175 = 0;
    }
LABEL_239:
    if ( !(_DWORD)v177 )
      return 0;
    v87 = v15;
    v86 = HIDWORD(v177);
    goto LABEL_127;
  }
  v127 = *(_DWORD **)v307;
  **(_DWORD **)v307 = 0;
  if ( (unsigned int)(v173 + 1) > 2 )
  {
LABEL_290:
    if ( v231[0] )
      AutoAllocationCaches::Release((AutoAllocationCaches *)v231);
    goto LABEL_292;
  }
  LODWORD(v201) = 0;
  v128 = v185[2];
  v129 = *(_QWORD *)v185;
  v198 = *(_DWORD *)(*(_QWORD *)v185 + 36LL);
  v199 = *(_WORD *)(v129 + 40);
  v200 = 0;
  v130 = (v128 >> 10) & 4 | 0x88;
  if ( (v128 & 0x2000) == 0 )
    v130 = (v128 >> 10) & 4;
  LOBYTE(v172) = v130;
  if ( !(unsigned int)TargetExtentMgr::AllocPageFromTargetExtent(
                        &v277,
                        *(_QWORD *)v129,
                        v186,
                        (unsigned __int16)v180,
                        v126,
                        v172,
                        &v198,
                        v184,
                        a6,
                        &v187,
                        &v201,
                        0) )
  {
    if ( v173 != -1 )
    {
      v131 = *(_WORD *)(*(_QWORD *)(v120.QuadPart + 48) + 1720LL);
      v335 = 8;
      v334 = v131;
      v333 = 0;
      v332 = *(_DWORD *)v126;
      LOWORD(v333) = *((_WORD *)v126 + 2);
      lck_releaseClasses(v120.QuadPart + 56, &v332, 0, 0);
    }
    if ( !v14 )
      utassert_fail(1u, "IsValid()", "AllocationCacheManager.cpp", 2063, 0);
    HIDWORD(v177) = 2;
    LODWORD(v177) = LatchBase::AcquireInternal(v15, 2, 0xFFFFFFFFLL);
    v132 = *(_QWORD *)v185;
    LODWORD(v184) = *(_DWORD *)(*(_QWORD *)v185 + 36LL);
    HIDWORD(v184) = *(unsigned __int16 *)(v132 + 40);
    if ( PageCache::RemoveEntry(
           v14,
           (const struct PageCacheTraceData *)v282,
           v126,
           &v180,
           v186,
           (const struct AllocUnitId *)&v184)
      && !*v127 )
    {
      v133 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v134 = *(_QWORD *)(v133 + 256);
      if ( !v134 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v134 = *(_QWORD *)(v133 + 256);
      }
      v135 = 40LL * v180;
      v136 = v175[0];
      if ( !_InterlockedCompareExchange64(
              (volatile signed __int64 *)(*((_QWORD *)v175[0] + 5) + v135 + 8),
              *(_QWORD *)(v134 + 600),
              0) )
      {
        v137 = v135 + *((_QWORD *)v136 + 5);
        v138 = 0;
        v139 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)(v137 + 24) || _InterlockedCompareExchange64((volatile signed __int64 *)(v137 + 24), v139, 0) )
        {
          v140 = 0;
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v141 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset;
            if ( v141 && *(_QWORD *)(v141 + 272) == v141 )
              v140 = *(_QWORD *)(v141 + 256);
            if ( v140 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v204);
                v138 = (DirtyPageMgr *)v204.QuadPart;
              }
              else
              {
                v138 = MEMORY[0x7FFE0008];
              }
            }
          }
          v142 = v137 + 24;
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<319,1,258>::SpinToAcquireWithExponentialBackoff(v142, v139);
          else
            Spinlock<319,1,258>::SpinToAcquireOptimistic(v142, v140, v139);
          if ( v140 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v203);
              v143 = (DirtyPageMgr *)v203.QuadPart;
            }
            else
            {
              v143 = MEMORY[0x7FFE0008];
            }
            v144 = v143 - v138;
            if ( v143 < v138 )
              v144 = 0;
            *(_QWORD *)(v140 + 3192) += v144;
          }
        }
        v145 = *((_QWORD *)v136 + 5);
        v146 = *(_QWORD *)(v135 + v145);
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v147 = rand();
          v148 = (unsigned int)(v147 / 5);
          v149 = (unsigned int)(5 * v148);
          if ( v147 == (_DWORD)v149 )
            Spinlock<319,1,258>::UpdateStatSnapshot(v149, v148);
        }
        *(_QWORD *)(v135 + v145 + 24) = 0;
        v150 = 0;
        if ( HIWORD(v146) )
          v150 = WORD2(v146);
        v151 = 0;
        if ( HIWORD(v146) )
          v151 = v146;
        if ( v151 || v150 )
        {
          v152 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v153 = *(_QWORD *)(v152 + 256);
          if ( !v153 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v153 = *(_QWORD *)(v152 + 256);
          }
          v154 = *((_QWORD *)v136 + 5);
          if ( *(_QWORD *)(v154 + v135 + 8) == *(_QWORD *)(v153 + 600) )
            *(_QWORD *)(v135 + v154 + 8) = 0;
        }
        else
        {
          **(_DWORD **)v307 = 1;
        }
      }
      v15 = v176;
      v14 = v175[0];
    }
    if ( !v14 )
      utassert_fail(1u, "IsValid()", "AllocationCacheManager.cpp", 2111, 0);
    LatchBase::ReleaseInternal(v15, 2);
    LODWORD(v177) = 0;
    goto LABEL_290;
  }
  *(_DWORD *)(v121 + 8) = (_DWORD)v187;
  *(_WORD *)(v121 + 12) = WORD2(v187);
  *(_WORD *)(v121 + 14) = 0;
  *(_QWORD *)v121 = 0;
  *(_DWORD *)(v121 + 28) = 2;
  *(_QWORD *)(v121 + 16) = 0;
  *(_WORD *)(v121 + 24) = 0;
  if ( v173 != -1 )
  {
    v155 = *(_WORD *)(*(_QWORD *)(v120.QuadPart + 48) + 1720LL);
    v309 = 8;
    v308 = v155;
    *(_QWORD *)&v307[4] = 0;
    *(_DWORD *)v307 = *(_DWORD *)v126;
    *(_WORD *)&v307[4] = *((_WORD *)v126 + 2);
    lck_releaseClasses(v120.QuadPart + 56, v307, 0, 0);
  }
  if ( v231[0] )
    AutoAllocationCaches::Release((AutoAllocationCaches *)v231);
  if ( v14 )
  {
    if ( (_DWORD)v177 )
    {
      LatchBase::ReleaseInternal(v15, HIDWORD(v177));
      LODWORD(v177) = 0;
    }
    *(_OWORD *)v175 = 0;
  }
  if ( (_DWORD)v177 )
  {
    LatchBase::ReleaseInternal(v15, HIDWORD(v177));
    LODWORD(v177) = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x10044e3d0  push    rbx
0x10044e3d2  push    rsi
0x10044e3d3  push    rdi
0x10044e3d4  push    r12
0x10044e3d6  push    r13
0x10044e3d8  push    r14
0x10044e3da  push    r15
0x10044e3dc  sub     rsp, 440h
0x10044e3e3  mov     [rsp+478h+var_140], 0FFFFFFFFFFFFFFFEh
0x10044e3ef  mov     rax, cs:__security_cookie
0x10044e3f6  xor     rax, rsp
0x10044e3f9  mov     [rsp+478h+var_48], rax
0x10044e401  mov     [rsp+478h+var_358], r8
0x10044e409  mov     [rsp+478h+var_3C0], rdx
0x10044e411  mov     [rsp+478h+var_3C8], rcx
0x10044e419  mov     [rsp+478h+var_308], rcx
0x10044e421  mov     qword ptr [rsp+478h+var_370], rdx
0x10044e429  mov     qword ptr [rsp+478h+var_368], r8
0x10044e431  mov     rax, [rsp+478h+arg_20]
0x10044e439  mov     [rsp+478h+var_3D0], rax
0x10044e441  mov     rax, [rsp+478h+arg_30]
0x10044e449  mov     [rsp+478h+var_380], rax
0x10044e451  mov     rax, [rsp+478h+arg_40]
0x10044e459  mov     qword ptr [rsp+478h+var_B8], rax
0x10044e461  mov     [rsp+478h+var_330], rax
0x10044e469  mov     r14, [rsp+478h+arg_48]
0x10044e471  mov     [rsp+478h+var_3B8], r14
0x10044e479  mov     r12, [rsp+478h+arg_50]
0x10044e481  mov     [rsp+478h+var_390], r12
0x10044e489  xor     edi, edi
0x10044e48b  mov     [rsp+478h+var_19C], edi
0x10044e492  mov     [rsp+478h+var_198], di
0x10044e49a  mov     r13d, 1
0x10044e4a0  mov     [rsp+478h+var_410], r13d
0x10044e4a5  xorps   xmm0, xmm0
0x10044e4a8  movdqu  xmmword ptr [rsp+478h+var_408], xmm0
0x10044e4ae  mov     [rsp+478h+var_3F8], rdi
0x10044e4b6  mov     [rsp+478h+var_3F0], rdi
0x10044e4be  mov     rdx, [rcx]
0x10044e4c1  movzx   eax, word ptr [rdx+20h]
0x10044e4c5  mov     word ptr [rsp+478h+var_3E4], ax
0x10044e4cd  test    byte ptr [rcx+8], 2
0x10044e4d1  mov     eax, edi
0x10044e4d3  cmovz   eax, r13d
0x10044e4d7  mov     [rsp+478h+var_1E0], eax
0x10044e4de  mov     rcx, [rdx+40h]
0x10044e4e2  mov     rax, [rdx+38h]
0x10044e4e6  mov     [rsp+478h+var_1D8], rax
0x10044e4ee  mov     [rsp+478h+var_1D0], rcx
0x10044e4f6  lea     rdx, [rsp+478h+var_410]; struct AutoPageCache *
0x10044e4fb  mov     rcx, r12; this
0x10044e4fe  call    ?GetAllocationExtentCache@AutoAllocationCaches@@QEAAXAEAVAutoPageCache@@@Z; AutoAllocationCaches::GetAllocationExtentCache(AutoPageCache &)
0x10044e503  mov     rsi, [rsp+478h+var_408]
0x10044e508  test    rsi, rsi
0x10044e50b  jz      loc_10161D92D
0x10044e511  mov     dword ptr [rsp+478h+var_3F0+4], 2
0x10044e51c  mov     [rsp+478h+var_438], edi
0x10044e520  mov     [rsp+478h+var_440], rdi
0x10044e525  mov     [rsp+478h+var_448], rdi
0x10044e52a  mov     dword ptr [rsp+478h+var_450], edi
0x10044e52e  mov     [rsp+478h+var_458], rdi
0x10044e533  xor     r9d, r9d
0x10044e536  lea     edx, [r9+2]
0x10044e53a  mov     r8d, 0FFFFFFFFh
0x10044e540  mov     rbx, [rsp+478h+var_3F8]
0x10044e548  mov     rcx, rbx
0x10044e54b  call    ?AcquireInternal@LatchBase@@AEAA?AW4AcquireResult@1@W4LATCH_TYPE@1@KPEAVLatchSuspendInfo@@PEAUSubLatchInfo@1@W4Releasor@1@PEA_KPEAVSOS_LsAccessCache@@W4LatchYieldBehavior@1@@Z; LatchBase::AcquireInternal(LatchBase::LATCH_TYPE,ulong,LatchSuspendInfo *,LatchBase::SubLatchInfo *,LatchBase::Releasor,unsigned __int64 *,SOS_LsAccessCache *,LatchBase::LatchYieldBehavior)
0x10044e550  mov     dword ptr [rsp+478h+var_3F0], eax
0x10044e557  mov     r15d, edi
0x10044e55a  mov     [rsp+478h+var_378], r15d
0x10044e562  cmp     r15d, [rsi+0Ch]
0x10044e566  jnb     loc_10161DF0E
0x10044e56c  mov     [rsp+478h+var_418], 2
0x10044e574  mov     r14d, [rsi+0Ch]
0x10044e578  lea     eax, [r14+r14*2]
0x10044e57c  shr     eax, 2
0x10044e57f  cmp     r15d, eax
0x10044e582  jnb     loc_1005F19CC
0x10044e588  mov     eax, r15d
0x10044e58b  lea     rcx, [rax+rax*4]
0x10044e58f  lea     r13, ds:0[rcx*8]
0x10044e597  mov     r15, [rsi+28h]
0x10044e59b  add     r15, r13
0x10044e59e  mov     rbx, rdi
0x10044e5a1  mov     eax, gs:48h
0x10044e5a9  mov     r12d, eax
0x10044e5ac  mov     eax, [r15+18h]
0x10044e5b0  test    eax, eax
0x10044e5b2  jnz     loc_1005F2122
0x10044e5b8  xor     eax, eax
0x10044e5ba  lock cmpxchg [r15+18h], r12
0x10044e5c0  mov     eax, edi
0x10044e5c2  setz    al
0x10044e5c5  test    eax, eax
0x10044e5c7  jz      loc_1005F2122
0x10044e5cd  mov     rax, [rsi+28h]
0x10044e5d1  mov     rcx, [rax+r13]
0x10044e5d5  mov     rbx, rcx
0x10044e5d8  shr     rbx, 30h
0x10044e5dc  mov     r12, [rsp+478h+var_3B8]
0x10044e5e4  mov     [r12], ecx
0x10044e5e8  shr     rcx, 20h
0x10044e5ec  mov     [r12+4], cx
0x10044e5f2  mov     r14, [rsi+28h]
0x10044e5f6  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10044e5fd  cmp     byte ptr [rax], 0
0x10044e600  jnz     loc_10161DA05
0x10044e606  mov     [r14+r13+18h], rdi
0x10044e60b  test    bx, bx
0x10044e60e  jz      loc_100487630
0x10044e614  cmp     dword ptr [r12], 0
0x10044e619  jz      loc_10048763D
0x10044e61f  mov     rdx, r12; struct PageId *
0x10044e622  mov     rcx, [rsp+478h+var_3C0]; struct RecoveryUnit *
0x10044e62a  call    ?IsPageValidForAllocation@@YAHPEAVRecoveryUnit@@AEBVPageId@@@Z; IsPageValidForAllocation(RecoveryUnit *,PageId const &)
0x10044e62f  test    eax, eax
0x10044e631  jz      loc_10048764A
0x10044e637  mov     r13, qword ptr [rsp+478h+var_B8]
0x10044e63f  mov     eax, [rsp+478h+var_418]
0x10044e643  mov     r15, [rsp+478h+var_358]
0x10044e64b  cmp     eax, 2
0x10044e64e  jnz     short loc_10044E664
0x10044e650  mov     r9, r15
0x10044e653  xor     r8d, r8d
0x10044e656  mov     dl, 4
0x10044e658  mov     rcx, r12
0x10044e65b  call    ?LockExtent@@YAHAEBVPageId@@W4LCK_MODE@@KPEAVXDES@@@Z; LockExtent(PageId const &,LCK_MODE,ulong,XDES *)
0x10044e660  mov     [rsp+478h+var_418], eax
0x10044e664  inc     eax
0x10044e666  cmp     eax, 2
0x10044e669  ja      loc_1004886CB
0x10044e66f  mov     [rsp+478h+var_340], edi
0x10044e676  mov     rsi, [rsp+478h+var_408]
0x10044e67b  test    rsi, rsi
0x10044e67e  jz      loc_10161DD6D
0x10044e684  mov     r14d, 1
0x10044e68a  mov     edx, dword ptr [rsp+478h+var_3F0+4]
0x10044e691  mov     rbx, [rsp+478h+var_3F8]
0x10044e699  mov     rcx, rbx
0x10044e69c  call    ?ReleaseInternal@LatchBase@@AEAA_NW4LATCH_TYPE@1@@Z; LatchBase::ReleaseInternal(LatchBase::LATCH_TYPE)
0x10044e6a1  mov     dword ptr [rsp+478h+var_3F0], edi
0x10044e6a8  mov     rcx, [rsp+478h+var_3C8]
0x10044e6b0  mov     r8d, [rcx+8]
0x10044e6b4  mov     eax, r8d
0x10044e6b7  shr     eax, 0Ah
0x10044e6ba  and     al, 4
0x10044e6bc  movzx   edx, al
0x10044e6bf  mov     r10, [rcx]
0x10044e6c2  mov     eax, [r10+24h]
0x10044e6c6  mov     [rsp+478h+var_320], eax
0x10044e6cd  movzx   eax, word ptr [r10+28h]
0x10044e6d2  mov     [rsp+478h+var_31C], ax
0x10044e6da  mov     [rsp+478h+var_31A], di
0x10044e6e2  movzx   eax, dl
0x10044e6e5  or      al, 88h
0x10044e6e7  movzx   ecx, al
0x10044e6ea  and     r8d, 2000h
0x10044e6f1  cmovz   ecx, edx
0x10044e6f4  mov     [rsp+478h+var_420], edi
0x10044e6f8  lea     rax, [rsp+478h+var_340]
0x10044e700  mov     [rsp+478h+var_428], rax
0x10044e705  lea     rax, [rsp+478h+var_310]
0x10044e70d  mov     [rsp+478h+var_430], rax
0x10044e712  mov     eax, [rsp+478h+arg_28]
0x10044e719  mov     [rsp+478h+var_438], eax
0x10044e71d  mov     rax, [rsp+478h+var_3D0]
0x10044e725  mov     [rsp+478h+var_440], rax
0x10044e72a  lea     rax, [rsp+478h+var_320]
0x10044e732  mov     [rsp+478h+var_448], rax
0x10044e737  mov     byte ptr [rsp+478h+var_450], cl
0x10044e73b  mov     [rsp+478h+var_458], r12
0x10044e740  movzx   r9d, word ptr [rsp+478h+var_3E4]
0x10044e749  mov     r8, [rsp+478h+var_3C0]
0x10044e751  mov     rdx, [r10]
0x10044e754  lea     rcx, [rsp+478h+var_1E0]
0x10044e75c  call    ?AllocPageFromTargetExtent@TargetExtentMgr@@QEBAHPEAVXDES@@PEAVRecoveryUnit@@GAEBVPageId@@EAEBVAllocUnitId@@AEBVHoBtId@@W4LogMode@@AEAV4@AEAHH@Z; TargetExtentMgr::AllocPageFromTargetExtent(XDES *,RecoveryUnit *,ushort,PageId const &,uchar,AllocUnitId const &,HoBtId const &,LogMode,PageId &,int &,int)
0x10044e761  test    eax, eax
0x10044e763  jz      loc_100487AB8
0x10044e769  mov     eax, [rsp+478h+var_310]
0x10044e770  mov     rcx, [rsp+478h+var_380]
0x10044e778  mov     [rcx+8], eax
0x10044e77b  movzx   eax, [rsp+478h+var_30C]
0x10044e783  mov     [rcx+0Ch], ax
0x10044e787  mov     [rcx+0Eh], di
0x10044e78b  mov     qword ptr [rcx], 0
0x10044e792  mov     dword ptr [rcx+1Ch], 2
0x10044e799  mov     qword ptr [rcx+10h], 0
0x10044e7a1  mov     [rcx+18h], di
0x10044e7a5  cmp     [rsp+478h+var_418], 0FFFFFFFFh
0x10044e7aa  jz      short loc_10044E804
0x10044e7ac  mov     rax, [r15+30h]
0x10044e7b0  movzx   ecx, word ptr [rax+6B8h]
0x10044e7b7  mov     [rsp+478h+var_AA], 8
0x10044e7bf  mov     [rsp+478h+var_AC], cx
0x10044e7c7  mov     qword ptr [rsp+478h+var_B8+4], 0
0x10044e7d3  mov     eax, [r12]
0x10044e7d7  mov     dword ptr [rsp+478h+var_B8], eax
0x10044e7de  movzx   eax, word ptr [r12+4]
0x10044e7e4  mov     word ptr [rsp+478h+var_B8+4], ax
0x10044e7ec  lea     rcx, [r15+38h]
0x10044e7f0  xor     r9d, r9d
0x10044e7f3  xor     r8d, r8d
0x10044e7f6  lea     rdx, [rsp+478h+var_B8]
0x10044e7fe  call    ?lck_releaseClasses@@YAHAEAVXactLockInfo@@AEAVLockRes@@KW4RefControl@LockRequest@@@Z; lck_releaseClasses(XactLockInfo &,LockRes &,ulong,LockRequest::RefControl)
0x10044e803  nop
0x10044e804  test    rsi, rsi
0x10044e807  jz      short loc_10044E812
0x10044e809  xorps   xmm0, xmm0
0x10044e80c  movdqu  xmmword ptr [rsp+478h+var_408], xmm0
0x10044e812  mov     eax, r14d
0x10044e815  jmp     short loc_10044E818
0x10044e818  mov     rcx, [rsp+478h+var_48]
0x10044e820  xor     rcx, rsp; StackCookie
0x10044e823  call    __security_check_cookie
0x10044e828  add     rsp, 440h
0x10044e82f  pop     r15
0x10044e831  pop     r14
0x10044e833  pop     r13
0x10044e835  pop     r12
0x10044e837  pop     rdi
0x10044e838  pop     rsi
0x10044e839  pop     rbx
0x10044e83a  retn
0x100487630  mov     [r12], edi
0x100487634  mov     [r12+4], di
0x10048763a  jmp     short loc_10048763D
0x10048763d  cmp     word ptr [r12+4], 0
0x100487644  jnz     loc_10044E61F
0x10048764a  mov     r8, qword ptr [rsp+478h+var_B8]
0x100487652  cmp     dword ptr [r8], 0
0x100487656  jz      loc_10048847A
0x10048765c  mov     eax, [r8]
0x10048765f  test    eax, eax
0x100487661  jz      loc_1004884C9
0x100487667  mov     r13d, 1
0x10048766d  mov     rax, qword ptr [rsp+478h+var_B8]
0x100487675  mov     [rax], r13d
0x100487678  mov     rsi, [rsp+478h+var_408]
0x10048767d  mov     rcx, [rsi+30h]
0x100487681  test    byte ptr [rcx+18h], 3
0x100487685  jnz     loc_1005BA1BF
0x10048768b  mov     eax, dword ptr [rsp+478h+var_3F0]
0x100487692  mov     ebx, dword ptr [rsp+478h+var_3F0+4]
0x100487699  mov     rsi, [rsp+478h+var_3F8]
0x1004876a1  test    eax, eax
0x1004876a3  jz      short loc_1004876B8
0x1004876a5  mov     edx, ebx
0x1004876a7  mov     rcx, rsi
0x1004876aa  call    ?ReleaseInternal@LatchBase@@AEAA_NW4LATCH_TYPE@1@@Z; LatchBase::ReleaseInternal(LatchBase::LATCH_TYPE)
0x1004876af  mov     eax, edi
0x1004876b1  mov     dword ptr [rsp+478h+var_3F0], eax
0x1004876b8  xorps   xmm0, xmm0
0x1004876bb  movdqu  xmmword ptr [rsp+478h+var_408], xmm0
0x1004876c1  test    eax, eax
0x1004876c3  jnz     loc_10161DD62
0x1004876c9  xor     eax, eax
0x1004876cb  jmp     loc_10044E818
0x100487ab8  cmp     [rsp+478h+var_418], 0FFFFFFFFh
0x100487abd  jz      short loc_100487B16
0x100487abf  mov     rax, [r15+30h]
0x100487ac3  movzx   ecx, word ptr [rax+6B8h]
0x100487aca  mov     [rsp+478h+var_4A], 8
0x100487ad2  mov     [rsp+478h+var_4C], cx
0x100487ada  mov     [rsp+478h+var_54], 0
0x100487ae6  mov     eax, [r12]
0x100487aea  mov     [rsp+478h+var_58], eax
0x100487af1  movzx   eax, word ptr [r12+4]
0x100487af7  mov     word ptr [rsp+478h+var_54], ax
0x100487aff  lea     rcx, [r15+38h]
0x100487b03  xor     r9d, r9d
0x100487b06  xor     r8d, r8d
0x100487b09  lea     rdx, [rsp+478h+var_58]
0x100487b11  call    ?lck_releaseClasses@@YAHAEAVXactLockInfo@@AEAVLockRes@@KW4RefControl@LockRequest@@@Z; lck_releaseClasses(XactLockInfo &,LockRes &,ulong,LockRequest::RefControl)
0x100487b16  test    rsi, rsi
0x100487b19  jz      loc_10161DD9B
0x100487b1f  mov     dword ptr [rsp+478h+var_3F0+4], 2
0x100487b2a  mov     [rsp+478h+var_438], edi
0x100487b2e  mov     [rsp+478h+var_440], rdi
0x100487b33  mov     [rsp+478h+var_448], rdi
0x100487b38  mov     dword ptr [rsp+478h+var_450], edi
0x100487b3c  mov     [rsp+478h+var_458], rdi
0x100487b41  xor     r9d, r9d
0x100487b44  lea     edx, [r9+2]
0x100487b48  mov     r8d, 0FFFFFFFFh
0x100487b4e  mov     rcx, rbx
0x100487b51  call    ?AcquireInternal@LatchBase@@AEAA?AW4AcquireResult@1@W4LATCH_TYPE@1@KPEAVLatchSuspendInfo@@PEAUSubLatchInfo@1@W4Releasor@1@PEA_KPEAVSOS_LsAccessCache@@W4LatchYieldBehavior@1@@Z; LatchBase::AcquireInternal(LatchBase::LATCH_TYPE,ulong,LatchSuspendInfo *,LatchBase::SubLatchInfo *,LatchBase::Releasor,unsigned __int64 *,SOS_LsAccessCache *,LatchBase::LatchYieldBehavior)
0x100487b56  mov     dword ptr [rsp+478h+var_3F0], eax
0x100487b5d  mov     rcx, [rsp+478h+var_3C8]
0x100487b65  mov     rcx, [rcx]
0x100487b68  mov     eax, [rcx+24h]
0x100487b6b  mov     [rsp+478h+var_318], eax
0x100487b72  movzx   eax, word ptr [rcx+28h]
0x100487b76  mov     [rsp+478h+var_314], ax
0x100487b7e  mov     [rsp+478h+var_312], di
0x100487b86  lea     rax, [rsp+478h+var_318]
0x100487b8e  mov     [rsp+478h+var_450], rax; struct AllocUnitId *
0x100487b93  mov     rax, [rsp+478h+var_3C0]
0x100487b9b  mov     [rsp+478h+var_458], rax; struct RecoveryUnit *
0x100487ba0  lea     r9, [rsp+478h+var_33C]; unsigned int *
0x100487ba8  mov     r8, r12; struct PageId *
  ... truncated ...
```
