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
  int v96; // r8d
  __int64 v97; // r14
  __int64 v98; // r8
  __int64 v99; // rcx
  DirtyPageMgr *v100; // rax
  signed __int64 v101; // rcx
  int v102; // r8d
  __int64 v103; // rsi
  __int64 v104; // r8
  __int64 v105; // rcx
  DirtyPageMgr *v106; // rax
  signed __int64 v107; // rcx
  int v108; // r8d
  unsigned int v109; // r12d
  BOOL v110; // r15d
  __int64 v111; // r14
  unsigned __int16 v112; // ax
  __int16 v113; // cx
  LARGE_INTEGER v114; // r12
  __int64 v115; // r13
  __int64 v116; // rbx
  struct Worker *v117; // rcx
  __int64 v118; // rcx
  bool v119; // al
  struct PageId *v120; // r14
  _DWORD *v121; // r15
  unsigned int v122; // r8d
  __int64 v123; // r10
  char v124; // cl
  __int16 v125; // cx
  __int64 v126; // rcx
  __int64 v127; // rbx
  __int64 v128; // rdx
  __int64 v129; // r15
  PageCache *v130; // r13
  __int64 v131; // r14
  DirtyPageMgr *v132; // rbx
  signed __int64 v133; // r12
  __int64 v134; // rsi
  __int64 v135; // r8
  __int64 v136; // rcx
  DirtyPageMgr *v137; // rax
  signed __int64 v138; // rcx
  __int64 v139; // r12
  __int64 v140; // rsi
  int v141; // r8d
  __int16 v142; // cx
  int v143; // eax
  __int64 v144; // rbx
  __int64 v145; // rcx
  __int64 v146; // rax
  __int16 v147; // cx
  __int64 v148; // rbx
  __int64 v149; // rax
  __int64 v150; // r9
  PageCache *v151; // r8
  __int64 v152; // rdx
  __int64 v153; // rax
  const struct SQLError *CurrentException; // rax
  __int64 v155; // rbx
  __int64 v156; // rax
  __int64 v157; // r9
  PageCache *v158; // r8
  __int64 v159; // rdx
  __int64 v160; // rax
  __int64 v161; // rbx
  const struct SQLError *v162; // rax
  int v163; // [rsp+28h] [rbp-450h]
  int v164; // [rsp+28h] [rbp-450h]
  int v165; // [rsp+60h] [rbp-418h] BYREF
  int v166; // [rsp+68h] [rbp-410h] BYREF
  PageCache *v167[2]; // [rsp+70h] [rbp-408h]
  __int64 v168; // [rsp+80h] [rbp-3F8h]
  __int64 v169; // [rsp+88h] [rbp-3F0h]
  char v170; // [rsp+90h] [rbp-3E8h]
  char v171; // [rsp+91h] [rbp-3E7h]
  unsigned int v172; // [rsp+94h] [rbp-3E4h] BYREF
  int v173; // [rsp+98h] [rbp-3E0h]
  unsigned int v174; // [rsp+9Ch] [rbp-3DCh]
  BOOL v175; // [rsp+A0h] [rbp-3D8h]
  __int64 v176; // [rsp+A8h] [rbp-3D0h] BYREF
  _DWORD *v177; // [rsp+B0h] [rbp-3C8h]
  struct RecoveryUnit *v178; // [rsp+B8h] [rbp-3C0h]
  struct PageId *v179; // [rsp+C0h] [rbp-3B8h] BYREF
  int v180; // [rsp+C8h] [rbp-3B0h]
  __int16 v181; // [rsp+CCh] [rbp-3ACh]
  __int16 v182; // [rsp+CEh] [rbp-3AAh]
  __int16 v183; // [rsp+D0h] [rbp-3A8h]
  __int16 v184; // [rsp+D4h] [rbp-3A4h]
  __int16 v185; // [rsp+D8h] [rbp-3A0h]
  BOOL v186; // [rsp+DCh] [rbp-39Ch]
  int v187; // [rsp+E0h] [rbp-398h]
  __int16 v188; // [rsp+E4h] [rbp-394h]
  AutoAllocationCaches *v189; // [rsp+E8h] [rbp-390h] BYREF
  int v190; // [rsp+F0h] [rbp-388h] BYREF
  __int16 v191; // [rsp+F4h] [rbp-384h]
  __int16 v192; // [rsp+F6h] [rbp-382h]
  __int64 v193; // [rsp+F8h] [rbp-380h] BYREF
  unsigned int v194; // [rsp+100h] [rbp-378h]
  LARGE_INTEGER v195; // [rsp+108h] [rbp-370h] BYREF
  LARGE_INTEGER v196; // [rsp+110h] [rbp-368h] BYREF
  int v197; // [rsp+118h] [rbp-360h]
  __int16 v198; // [rsp+11Ch] [rbp-35Ch]
  __int16 v199; // [rsp+11Eh] [rbp-35Ah]
  LARGE_INTEGER v200; // [rsp+120h] [rbp-358h]
  int v201; // [rsp+128h] [rbp-350h]
  int v202; // [rsp+12Ch] [rbp-34Ch]
  int v203; // [rsp+130h] [rbp-348h] BYREF
  int v204; // [rsp+134h] [rbp-344h]
  int v205; // [rsp+138h] [rbp-340h] BYREF
  unsigned int v206; // [rsp+13Ch] [rbp-33Ch] BYREF
  int v207; // [rsp+140h] [rbp-338h] BYREF
  int v208; // [rsp+144h] [rbp-334h]
  _DWORD *v209; // [rsp+148h] [rbp-330h]
  int v210; // [rsp+150h] [rbp-328h] BYREF
  __int16 v211; // [rsp+154h] [rbp-324h]
  __int16 v212; // [rsp+156h] [rbp-322h]
  int v213; // [rsp+158h] [rbp-320h] BYREF
  __int16 v214; // [rsp+15Ch] [rbp-31Ch]
  __int16 v215; // [rsp+15Eh] [rbp-31Ah]
  int v216; // [rsp+160h] [rbp-318h] BYREF
  __int16 v217; // [rsp+164h] [rbp-314h]
  __int16 v218; // [rsp+166h] [rbp-312h]
  int v219; // [rsp+168h] [rbp-310h] BYREF
  __int16 v220; // [rsp+16Ch] [rbp-30Ch]
  _DWORD *v221; // [rsp+170h] [rbp-308h]
  __int128 v222; // [rsp+178h] [rbp-300h] BYREF
  _QWORD v223[2]; // [rsp+188h] [rbp-2F0h] BYREF
  int v224; // [rsp+198h] [rbp-2E0h]
  char v225; // [rsp+19Ch] [rbp-2DCh]
  int v226; // [rsp+1A0h] [rbp-2D8h]
  char v227; // [rsp+1A4h] [rbp-2D4h]
  int v228; // [rsp+1A8h] [rbp-2D0h]
  __int16 v229; // [rsp+1ACh] [rbp-2CCh]
  __int16 v230; // [rsp+1AEh] [rbp-2CAh]
  __int64 v231; // [rsp+1B0h] [rbp-2C8h] BYREF
  char v232; // [rsp+1B8h] [rbp-2C0h]
  unsigned int v233; // [rsp+1BCh] [rbp-2BCh]
  __int64 v234; // [rsp+1C0h] [rbp-2B8h] BYREF
  char v235; // [rsp+1C8h] [rbp-2B0h]
  unsigned int v236; // [rsp+1CCh] [rbp-2ACh]
  int v237; // [rsp+1D0h] [rbp-2A8h]
  __int16 v238; // [rsp+1D4h] [rbp-2A4h]
  int v239; // [rsp+1D6h] [rbp-2A2h]
  __int16 v240; // [rsp+1DAh] [rbp-29Eh]
  int v241; // [rsp+1DCh] [rbp-29Ch]
  __int16 v242; // [rsp+1E0h] [rbp-298h]
  __int128 v243; // [rsp+1E8h] [rbp-290h] BYREF
  __int128 v244; // [rsp+1F8h] [rbp-280h] BYREF
  int v245; // [rsp+208h] [rbp-270h]
  char v246; // [rsp+20Ch] [rbp-26Ch]
  int v247; // [rsp+210h] [rbp-268h]
  char v248; // [rsp+214h] [rbp-264h]
  int v249; // [rsp+218h] [rbp-260h]
  int v250; // [rsp+21Ch] [rbp-25Ch]
  __int16 v251; // [rsp+220h] [rbp-258h]
  int v252; // [rsp+228h] [rbp-250h]
  int v253; // [rsp+22Ch] [rbp-24Ch]
  __int16 v254; // [rsp+230h] [rbp-248h]
  LARGE_INTEGER v255; // [rsp+238h] [rbp-240h] BYREF
  LARGE_INTEGER v256; // [rsp+240h] [rbp-238h] BYREF
  __int64 v257; // [rsp+248h] [rbp-230h]
  __int64 v258; // [rsp+250h] [rbp-228h]
  LARGE_INTEGER v259; // [rsp+258h] [rbp-220h] BYREF
  LARGE_INTEGER v260; // [rsp+260h] [rbp-218h] BYREF
  __int64 v261; // [rsp+268h] [rbp-210h]
  int v262; // [rsp+270h] [rbp-208h]
  int v263; // [rsp+274h] [rbp-204h]
  int v264; // [rsp+278h] [rbp-200h]
  LARGE_INTEGER v266; // [rsp+280h] [rbp-1F8h] BYREF
  __int64 v267; // [rsp+288h] [rbp-1F0h]
  LARGE_INTEGER PerformanceCount; // [rsp+290h] [rbp-1E8h] BYREF
  BOOL v269; // [rsp+298h] [rbp-1E0h] BYREF
  __int64 v270; // [rsp+2A0h] [rbp-1D8h]
  __int64 v271; // [rsp+2A8h] [rbp-1D0h]
  _BYTE v272[16]; // [rsp+2B0h] [rbp-1C8h] BYREF
  _BYTE v273[16]; // [rsp+2C0h] [rbp-1B8h] BYREF
  _BYTE v274[12]; // [rsp+2D0h] [rbp-1A8h] BYREF
  int v275; // [rsp+2DCh] [rbp-19Ch]
  __int16 v276; // [rsp+2E0h] [rbp-198h]
  __int64 v277; // [rsp+2F0h] [rbp-188h]
  __int64 v278; // [rsp+2F8h] [rbp-180h]
  PageCache *v279; // [rsp+300h] [rbp-178h]
  PageCache *v280; // [rsp+308h] [rbp-170h]
  __int64 v281; // [rsp+310h] [rbp-168h]
  __int64 v282; // [rsp+318h] [rbp-160h]
  PageCache *v283; // [rsp+320h] [rbp-158h]
  _QWORD *v284; // [rsp+328h] [rbp-150h]
  __int64 v285; // [rsp+330h] [rbp-148h]
  __int64 v286; // [rsp+338h] [rbp-140h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+340h] [rbp-138h]
  __int64 *v288; // [rsp+348h] [rbp-130h]
  __int64 v289; // [rsp+350h] [rbp-128h]
  struct CSessionTraceFlags *v290; // [rsp+358h] [rbp-120h]
  __int64 v291; // [rsp+360h] [rbp-118h]
  _QWORD *v292; // [rsp+368h] [rbp-110h]
  __int64 v293; // [rsp+370h] [rbp-108h]
  __int64 v294; // [rsp+378h] [rbp-100h]
  PageCache *v295; // [rsp+380h] [rbp-F8h]
  _QWORD *v296; // [rsp+388h] [rbp-F0h]
  _BYTE v297[24]; // [rsp+390h] [rbp-E8h] BYREF
  _BYTE v298[24]; // [rsp+3A8h] [rbp-D0h] BYREF
  _BYTE v299[12]; // [rsp+3C0h] [rbp-B8h] BYREF
  __int16 v300; // [rsp+3CCh] [rbp-ACh]
  char v301; // [rsp+3CEh] [rbp-AAh]
  int v302; // [rsp+3D0h] [rbp-A8h] BYREF
  __int16 v303; // [rsp+3D4h] [rbp-A4h]
  __int16 v304; // [rsp+3D6h] [rbp-A2h]
  int v305; // [rsp+3D8h] [rbp-A0h]
  __int16 v306; // [rsp+3DCh] [rbp-9Ch]
  __int16 v307; // [rsp+3DEh] [rbp-9Ah]
  int v308; // [rsp+3E0h] [rbp-98h]
  int v309; // [rsp+3E4h] [rbp-94h]
  __int16 v310; // [rsp+3E8h] [rbp-90h]
  __int16 v311; // [rsp+3EAh] [rbp-8Eh]
  int v312; // [rsp+3ECh] [rbp-8Ch]
  int v313; // [rsp+3F0h] [rbp-88h] BYREF
  __int16 v314; // [rsp+3F4h] [rbp-84h]
  __int16 v315; // [rsp+3F6h] [rbp-82h]
  int v316; // [rsp+3F8h] [rbp-80h]
  __int16 v317; // [rsp+3FCh] [rbp-7Ch]
  __int16 v318; // [rsp+3FEh] [rbp-7Ah]
  int v319; // [rsp+400h] [rbp-78h]
  int v320; // [rsp+404h] [rbp-74h]
  __int16 v321; // [rsp+408h] [rbp-70h]
  __int16 v322; // [rsp+40Ah] [rbp-6Eh]
  int v323; // [rsp+40Ch] [rbp-6Ch]
  int v324; // [rsp+410h] [rbp-68h] BYREF
  __int64 v325; // [rsp+414h] [rbp-64h]
  __int16 v326; // [rsp+41Ch] [rbp-5Ch]
  char v327; // [rsp+41Eh] [rbp-5Ah]
  int v328; // [rsp+420h] [rbp-58h] BYREF
  __int64 v329; // [rsp+424h] [rbp-54h]
  __int16 v330; // [rsp+42Ch] [rbp-4Ch]
  char v331; // [rsp+42Eh] [rbp-4Ah]

  v286 = -2;
  v200 = a3;
  v178 = a2;
  v177 = a1;
  v221 = a1;
  v195.QuadPart = (LONGLONG)a2;
  v196 = a3;
  v176 = a5;
  v193 = a7;
  *(_QWORD *)v299 = a9;
  v209 = a9;
  v179 = a10;
  v11 = a11;
  v189 = a11;
  v275 = 0;
  v276 = 0;
  v166 = 1;
  *(_OWORD *)v167 = 0;
  v168 = 0;
  v169 = 0;
  v12 = *(_QWORD *)a1;
  LOWORD(v172) = *(_WORD *)(*(_QWORD *)a1 + 32LL);
  v269 = (a1[8] & 2) == 0;
  v13 = *(_QWORD *)(v12 + 64);
  v270 = *(_QWORD *)(v12 + 56);
  v271 = v13;
  AutoAllocationCaches::GetAllocationExtentCache(a11, (struct AutoPageCache *)&v166);
  v14 = v167[0];
  if ( !v167[0] )
  {
    utassert_fail(1u, "autoAllocationExtentCache.IsValid()", "Alloc.cpp", 4851, 0);
    utassert_fail(1u, "IsValid()", "AllocationCacheManager.cpp", 2063, 0);
  }
  HIDWORD(v169) = 2;
  v15 = v168;
  LODWORD(v169) = LatchBase::AcquireInternal(v168, 2, 0xFFFFFFFFLL, 0, 0, 0, 0, 0, 0);
  v16 = 0;
  while ( 1 )
  {
    v194 = v16;
    if ( v16 >= *((_DWORD *)v14 + 3) )
      break;
    v165 = 2;
    v17 = *((_DWORD *)v14 + 3);
    if ( v16 >= (3 * v17) >> 2 )
    {
      LatchBase::ReleaseInternal(v15, HIDWORD(v169));
      LODWORD(v169) = 0;
      AutoAllocationCaches::GrowCaches(v11, v17);
      HIDWORD(v169) = 2;
      LODWORD(v169) = LatchBase::AcquireInternal(v15, 2, 0xFFFFFFFFLL, 0, 0, 0, 0, 0, 0);
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
            QueryPerformanceCounter(&v266);
            QuadPart = (DirtyPageMgr *)v266.QuadPart;
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
    v24 = v179;
    *(_DWORD *)v179 = v22;
    *((_WORD *)v24 + 2) = WORD2(v22);
    v25 = *((_QWORD *)v14 + 5);
    if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v96 = rand();
      if ( v96 == 5 * (v96 / 5) )
        Spinlock<319,1,258>::UpdateStatSnapshot();
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
    if ( (unsigned int)IsPageValidForAllocation(v178, v24) )
      goto LABEL_13;
LABEL_29:
    v36 = *(_DWORD **)v299;
    if ( !**(_DWORD **)v299 )
    {
      v55 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v56 = *(_QWORD *)(v55 + 256);
      if ( !v56 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v56 = *(_QWORD *)(v55 + 256);
        v36 = *(_DWORD **)v299;
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
      **(_DWORD **)v299 = 1;
      v37 = v167[0];
      v38 = *((_QWORD *)v167[0] + 6);
      if ( (*(_BYTE *)(v38 + 24) & 3) == 0 )
        goto LABEL_32;
      if ( !*a8 )
      {
        if ( *(_DWORD *)(v38 + 28) || _InterlockedCompareExchange((volatile signed __int32 *)(v38 + 28), 1, 0) )
        {
LABEL_32:
          v39 = v169;
          v40 = HIDWORD(v169);
          v41 = v168;
          if ( (_DWORD)v169 )
          {
            LatchBase::ReleaseInternal(v168, HIDWORD(v169));
            v39 = 0;
            LODWORD(v169) = 0;
          }
          *(_OWORD *)v167 = 0;
          if ( !v39 )
            return 0;
          v86 = v40;
          v87 = v41;
LABEL_127:
          LatchBase::ReleaseInternal(v87, v86);
          LODWORD(v169) = 0;
          return 0;
        }
        v37 = v167[0];
      }
      v243 = 0;
      v244 = 0;
      v245 = 0;
      v246 = 0;
      v247 = 0;
      v248 = 0;
      v186 = *a8 == 0;
      v70 = v177;
      v71 = *(_QWORD *)v177;
      if ( !*(_QWORD *)v177 )
        utassert_fail(1u, "ap", "SpaceScan.cpp", 68, 0);
      *(_QWORD *)&v243 = v71;
      *((_QWORD *)&v243 + 1) = *(_QWORD *)v71;
      v72 = *(_WORD *)(v71 + 40);
      v210 = *(_DWORD *)(v71 + 36);
      v211 = v72;
      v212 = 0;
      AllocationCachesManager::GetAllocationCaches(
        *(AllocationCachesManager **)(*(_QWORD *)(*((_QWORD *)&v243 + 1) + 48LL) + 1816LL),
        (const struct AllocationCachesId *)&v210,
        (struct AutoAllocationCaches *)&v244);
      if ( !(_QWORD)v244 )
        utassert_fail(1u, "m_autoAllocationCaches.IsValid()", "SpaceScan.cpp", 81, 0);
      if ( !(_DWORD)v169 )
        utassert_fail(1u, "pageCache.IsValid() && pageCache.IsLatched()", "SpaceScan.cpp", 83, 0);
      v247 = *((_DWORD *)v37 + 14);
      LatchBase::ReleaseInternal(v168, HIDWORD(v169));
      LODWORD(v169) = 0;
      try
      {
        v311 = 0;
        v237 = 0;
        v238 = 0;
        v249 = 0;
        v250 = 0;
        v251 = 0;
        v239 = 0;
        v240 = 0;
        v305 = 0;
        v306 = 0;
        v307 = 0;
        v302 = 0;
        v303 = 0;
        v304 = 0;
        v312 = 0;
        v308 = 0;
        v309 = 0;
        v310 = 0;
        v73 = 1;
        v174 = 1;
        if ( *a8 )
          goto LABEL_190;
        v173 = 1;
        v180 = 0;
        v181 = 0;
        v182 = 0;
        if ( *(_WORD *)(*(_QWORD *)(**(_QWORD **)v70 + 48LL) + 1720LL) != 2 && (byte_10317AC11 & 0x10) == 0 )
        {
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          v288 = (__int64 *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset);
          v74 = *v288;
          v289 = v74;
          if ( v74 )
          {
            v75 = **(struct CSessionTraceFlags ***)(v74 + 56);
            v290 = v75;
            if ( v75 )
            {
              if ( CSessionTraceFlags::CheckSessionTraceInternal(v75, 0x48Cu) )
              {
                v73 = v174;
                goto LABEL_107;
              }
            }
          }
          v291 = *(_QWORD *)v70;
          v197 = *(_DWORD *)(v291 + 36);
          v76 = *(_WORD *)(v291 + 40);
          v198 = v76;
          v199 = 0;
          v180 = v197;
          v181 = v76;
          v182 = 0;
          v77 = *(_QWORD *)(*(_QWORD *)(v291 + 16) + 8LL);
          v293 = v77 + 960;
          v201 = 0;
          if ( v197 != *(_DWORD *)(v77 + 960) )
            goto LABEL_141;
          if ( v76 == 1 )
            v76 = 0;
          v183 = v76;
          v78 = 0;
          if ( *(_WORD *)(v77 + 964) != 1 )
            v78 = *(_WORD *)(v77 + 964);
          if ( v76 == v78 )
          {
            v201 = 1;
            if ( *(_QWORD *)(v77 + 1008) >= 6 * (*(_QWORD *)(v77 + 1016) / 8LL) )
              goto LABEL_103;
            v69 = 0;
LABEL_79:
            v173 = v69;
          }
          else
          {
LABEL_141:
            v257 = v77;
            v294 = v77 + 1144;
            if ( *(_QWORD *)(v77 + 1144) )
              v92 = *(_QWORD *)(v77 + 1144);
            else
              v92 = v257;
            v228 = *(_DWORD *)(v92 + 1080);
            v93 = *(_WORD *)(v92 + 1084);
            v229 = v93;
            v230 = 0;
            v202 = 0;
            if ( v197 != v228 )
              goto LABEL_187;
            v94 = v198;
            if ( v198 == 1 )
              v94 = 0;
            v184 = v94;
            if ( v93 == 1 )
              v93 = 0;
            v185 = v93;
            if ( v94 != v93 )
            {
LABEL_187:
              v69 = v173;
              if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v70 + 16LL) + 8LL) + 1064LL) < 6
                                                                                               * (*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v70 + 16LL) + 8LL) + 1072LL)
                                                                                                / 8LL) )
                v69 = 0;
              goto LABEL_79;
            }
            v202 = 1;
            if ( *(_QWORD *)(v92 + 1120) < 6 * (*(_QWORD *)(v92 + 1128) / 8LL) )
            {
              v69 = 0;
              goto LABEL_79;
            }
LABEL_103:
            v69 = v173;
          }
          v73 = v174;
          if ( !v69 )
            v73 = 3;
          v174 = v73;
        }
LABEL_107:
        if ( *a8 )
        {
LABEL_190:
          v73 = v73 & 0xFFFFFFFA | 4;
          v174 = v73;
        }
        v236 = v236 & 0xFFFFFFFC | 2;
        v235 = 0;
        v234 = 0;
        v203 = 0;
        SpaceScan::Scan(&v243, 1, v73, &v302, &v165, &v234, &v203);
        v187 = v305;
        v79 = v306;
        v188 = v306;
        *(_DWORD *)v24 = v305;
        *((_WORD *)v24 + 2) = v79;
      }
      catch ( SQLError v298 )
      {
        try
        {
          ExceptionBackout::ExceptionBackout((ExceptionBackout *)v273, (const struct SQLError *)v298);
          AutoPageCache::Latch(&v166, 2);
          if ( v186 )
          {
            v295 = v167[0];
            *(_DWORD *)(*((_QWORD *)v167[0] + 6) + 28LL) = 0;
            v186 = 0;
          }
          v262 = 88;
          v296 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v148 = v296[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v277 = v148;
          v149 = *(_QWORD *)(v148 + 256);
          v258 = v149;
          if ( !v149 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v149 = *(_QWORD *)(v148 + 256);
            v258 = v149;
          }
          v150 = *(_QWORD *)(v149 + 600);
          v278 = v150;
          v151 = v167[0];
          v279 = v167[0];
          v170 = 0;
          v152 = 0;
          v204 = 0;
          while ( (unsigned int)v152 < *((_DWORD *)v151 + 3) )
          {
            v153 = *((_QWORD *)v151 + 5);
            if ( *(_QWORD *)(v153 + 40 * v152 + 8) == v150 )
            {
              *(_QWORD *)(v153 + 40 * v152 + 8) = 0;
              v170 = 1;
            }
            v152 = (unsigned int)(v152 + 1);
            v204 = v152;
          }
          AutoPageCache::UnLatch((AutoPageCache *)&v166);
          CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v273);
          ExceptionRethrow(CurrentException);
          ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v273);
        }
        catch ( ShortStackException )
        {
        }
        v177 = v221;
        v178 = (struct RecoveryUnit *)v195.QuadPart;
        v200 = v196;
        v24 = v179;
      }
      v80 = v186;
      v81 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v82 = *(struct Worker **)(v81 + 256);
      if ( !v82 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v82 = *(struct Worker **)(v81 + 256);
      }
      if ( *((_DWORD *)v82 + 139) )
        ExceptionPostCatchActions(v82);
      v83 = v167[0];
      if ( !v167[0] )
        utassert_fail(1u, "IsValid()", "AllocationCacheManager.cpp", 2063, 0);
      HIDWORD(v169) = 2;
      v84 = v168;
      v85 = LatchBase::AcquireInternal(v168, 2, 0xFFFFFFFFLL, 0, 0, 0, 0, 0, 0);
      LODWORD(v169) = v85;
      if ( v80 )
        *(_DWORD *)(*((_QWORD *)v83 + 6) + 28LL) = 0;
      if ( !*(_DWORD *)v24 && !*((_WORD *)v24 + 2) )
      {
        if ( (_QWORD)v244 )
          AutoAllocationCaches::Release((AutoAllocationCaches *)&v244);
        if ( v83 )
        {
          if ( v85 )
          {
            LatchBase::ReleaseInternal(v84, 2);
            v85 = 0;
            LODWORD(v169) = 0;
          }
          *(_OWORD *)v167 = 0;
        }
        if ( v85 )
        {
          v86 = 2;
          v87 = v84;
          goto LABEL_127;
        }
        return 0;
      }
      v27 = *(_DWORD **)v299;
      **(_DWORD **)v299 = 0;
      v26 = (_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset);
      if ( !v26[32] )
        SystemThread::MakeMiniSOSThread(0);
      if ( (_QWORD)v244 )
        AutoAllocationCaches::Release((AutoAllocationCaches *)&v244);
      goto LABEL_14;
    }
    v57 = v18 + *((_QWORD *)v14 + 5);
    v58 = 0;
    v59 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *(_DWORD *)(v57 + 24) || _InterlockedCompareExchange64((volatile signed __int64 *)(v57 + 24), v59, 0) )
    {
      v97 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v98 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v98 && *(_QWORD *)(v98 + 272) == v98 )
          v97 = *(_QWORD *)(v98 + 256);
        if ( v97 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v255);
            v58 = (DirtyPageMgr *)v255.QuadPart;
          }
          else
          {
            v58 = MEMORY[0x7FFE0008];
          }
        }
      }
      v99 = v57 + 24;
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<319,1,258>::SpinToAcquireWithExponentialBackoff(v99, v59);
      else
        Spinlock<319,1,258>::SpinToAcquireOptimistic(v99, v97, v59);
      if ( v97 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v256);
          v100 = (DirtyPageMgr *)v256.QuadPart;
        }
        else
        {
          v100 = MEMORY[0x7FFE0008];
        }
        v101 = v100 - v58;
        if ( v100 < v58 )
          v101 = 0;
        *(_QWORD *)(v97 + 3192) += v101;
      }
    }
    v60 = *(_QWORD *)(*((_QWORD *)v14 + 5) + v18);
    v61 = HIWORD(v60);
    v24 = v179;
    *(_DWORD *)v179 = v60;
    *((_WORD *)v24 + 2) = WORD2(v60);
    v62 = *((_QWORD *)v14 + 5);
    if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v102 = rand();
      if ( v102 == 5 * (v102 / 5) )
        Spinlock<319,1,258>::UpdateStatSnapshot();
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
    if ( !(unsigned int)IsPageValidForAllocation(v178, v24) )
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
    if ( *v209 )
      goto LABEL_31;
LABEL_13:
    v27 = *(_DWORD **)v299;
LABEL_14:
    v28 = v165;
    v29 = v200;
    if ( v165 == 2 )
    {
      LOBYTE(v26) = 4;
      v28 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))LockExtent)(
              v24,
              v26,
              0,
              (LARGE_INTEGER)v200.QuadPart);
      v165 = v28;
    }
    if ( (unsigned int)(v28 + 1) > 2 )
      goto LABEL_76;
    v205 = 0;
    v14 = v167[0];
    if ( !v167[0] )
      utassert_fail(1u, "IsValid()", "AllocationCacheManager.cpp", 2111, 0);
    v15 = v168;
    LatchBase::ReleaseInternal(v168, HIDWORD(v169));
    LODWORD(v169) = 0;
    v30 = v177[2];
    v31 = *(_QWORD *)v177;
    v213 = *(_DWORD *)(*(_QWORD *)v177 + 36LL);
    v214 = *(_WORD *)(v31 + 40);
    v215 = 0;
    v32 = (v30 >> 10) & 4 | 0x88;
    if ( (v30 & 0x2000) == 0 )
      v32 = (v30 >> 10) & 4;
    LOBYTE(v163) = v32;
    if ( (unsigned int)TargetExtentMgr::AllocPageFromTargetExtent(
                         &v269,
                         *(_QWORD *)v31,
                         v178,
                         (unsigned __int16)v172,
                         v24,
                         v163,
                         &v213,
                         v176,
                         a6,
                         &v219,
                         &v205,
                         0) )
    {
      v33 = v193;
      *(_DWORD *)(v193 + 8) = v219;
      *(_WORD *)(v33 + 12) = v220;
      *(_WORD *)(v33 + 14) = 0;
      *(_QWORD *)v33 = 0;
      *(_DWORD *)(v33 + 28) = 2;
      *(_QWORD *)(v33 + 16) = 0;
      *(_WORD *)(v33 + 24) = 0;
      if ( v165 != -1 )
      {
        v34 = *(_WORD *)(*(_QWORD *)(v29.QuadPart + 48) + 1720LL);
        v301 = 8;
        v300 = v34;
        *(_QWORD *)&v299[4] = 0;
        *(_DWORD *)v299 = *(_DWORD *)v24;
        *(_WORD *)&v299[4] = *((_WORD *)v24 + 2);
        lck_releaseClasses(v29.QuadPart + 56, v299, 0, 0);
      }
      if ( v14 )
        *(_OWORD *)v167 = 0;
      return 1;
    }
    if ( v165 != -1 )
    {
      v42 = *(_WORD *)(*(_QWORD *)(v29.QuadPart + 48) + 1720LL);
      v331 = 8;
      v330 = v42;
      v329 = 0;
      v328 = *(_DWORD *)v24;
      LOWORD(v329) = *((_WORD *)v24 + 2);
      lck_releaseClasses(v29.QuadPart + 56, &v328, 0, 0);
    }
    if ( !v14 )
      utassert_fail(1u, "IsValid()", "AllocationCacheManager.cpp", 2063, 0);
    HIDWORD(v169) = 2;
    LODWORD(v169) = LatchBase::AcquireInternal(v15, 2, 0xFFFFFFFFLL, 0, 0, 0, 0, 0, 0);
    v43 = *(_QWORD *)v177;
    v216 = *(_DWORD *)(*(_QWORD *)v177 + 36LL);
    v217 = *(_WORD *)(v43 + 40);
    v218 = 0;
    if ( !PageCache::RemoveEntry(
            v14,
            (const struct PageCacheTraceData *)v274,
            v24,
            &v206,
            v178,
            (const struct AllocUnitId *)&v216)
      || *v27 )
    {
LABEL_77:
      v16 = v194 + 1;
      v11 = v189;
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
      v46 = 40LL * v206;
      v47 = v167[0];
      if ( _InterlockedCompareExchange64(
             (volatile signed __int64 *)(*((_QWORD *)v167[0] + 5) + v46 + 8),
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
        v103 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v104 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v104 && *(_QWORD *)(v104 + 272) == v104 )
            v103 = *(_QWORD *)(v104 + 256);
          if ( v103 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v259);
              v49 = (DirtyPageMgr *)v259.QuadPart;
            }
            else
            {
              v49 = MEMORY[0x7FFE0008];
            }
          }
        }
        v105 = v48 + 24;
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<319,1,258>::SpinToAcquireWithExponentialBackoff(v105, v50);
        else
          Spinlock<319,1,258>::SpinToAcquireOptimistic(v105, v103, v50);
        if ( v103 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v260);
            v106 = (DirtyPageMgr *)v260.QuadPart;
          }
          else
          {
            v106 = MEMORY[0x7FFE0008];
          }
          v107 = v106 - v49;
          if ( v106 < v49 )
            v107 = 0;
          *(_QWORD *)(v103 + 3192) += v107;
        }
      }
      v51 = *((_QWORD *)v47 + 5);
      v52 = *(_QWORD *)(v51 + v46);
      if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v108 = rand();
        if ( v108 == 5 * (v108 / 5) )
          Spinlock<319,1,258>::UpdateStatSnapshot();
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
        v14 = v167[0];
        v15 = v168;
        goto LABEL_77;
      }
      **(_DWORD **)v299 = 1;
      v15 = v168;
      v14 = v167[0];
      v16 = v194 + 1;
      v11 = v189;
    }
  }
  if ( (*(_BYTE *)(*((_QWORD *)v14 + 6) + 24LL) & 3) == 0 )
  {
LABEL_292:
    if ( v14 )
    {
      if ( (_DWORD)v169 )
      {
        LatchBase::ReleaseInternal(v15, HIDWORD(v169));
        LODWORD(v169) = 0;
      }
      *(_OWORD *)v167 = 0;
    }
    goto LABEL_239;
  }
  v222 = 0;
  v223[0] = 0;
  v223[1] = 0;
  v224 = 0;
  v225 = 0;
  v226 = 0;
  v227 = 0;
  if ( *a8 )
  {
    v109 = 4;
    v110 = 0;
    v175 = 0;
  }
  else
  {
    v118 = *((_QWORD *)v14 + 6);
    if ( *(_DWORD *)(v118 + 28) )
    {
      v119 = 0;
    }
    else
    {
      v119 = _InterlockedCompareExchange((volatile signed __int32 *)(v118 + 28), 1, 0) == 0;
      v15 = v168;
      v14 = v167[0];
    }
    v110 = v119;
    v175 = v119;
    v109 = v119;
  }
  v111 = *(_QWORD *)v177;
  if ( !*(_QWORD *)v177 )
    utassert_fail(1u, "ap", "SpaceScan.cpp", 68, 0);
  *(_QWORD *)&v222 = v111;
  *((_QWORD *)&v222 + 1) = *(_QWORD *)v111;
  v112 = *(_WORD *)(v111 + 40);
  LODWORD(v189) = *(_DWORD *)(v111 + 36);
  HIDWORD(v189) = v112;
  AllocationCachesManager::GetAllocationCaches(
    *(AllocationCachesManager **)(*(_QWORD *)(*((_QWORD *)&v222 + 1) + 48LL) + 1816LL),
    (const struct AllocationCachesId *)&v189,
    (struct AutoAllocationCaches *)v223);
  if ( !v223[0] )
    utassert_fail(1u, "m_autoAllocationCaches.IsValid()", "SpaceScan.cpp", 81, 0);
  if ( !(_DWORD)v169 )
    utassert_fail(1u, "pageCache.IsValid() && pageCache.IsLatched()", "SpaceScan.cpp", 83, 0);
  v226 = *((_DWORD *)v14 + 14);
  LatchBase::ReleaseInternal(v15, HIDWORD(v169));
  LODWORD(v169) = 0;
  try
  {
    v322 = 0;
    v241 = 0;
    v242 = 0;
    v252 = 0;
    v253 = 0;
    v254 = 0;
    LODWORD(v209) = 0;
    WORD2(v209) = 0;
    v316 = 0;
    v317 = 0;
    v318 = 0;
    v313 = 0;
    v314 = 0;
    v315 = 0;
    v323 = 0;
    v319 = 0;
    v320 = 0;
    v321 = 0;
    v233 = v233 & 0xFFFFFFFC | 2;
    v232 = 0;
    v231 = 0;
    v207 = 0;
    SpaceScan::Scan(&v222, 1, v109, &v313, &v165, &v231, &v207);
    v187 = v316;
    v113 = v317;
    v188 = v317;
    v120 = v179;
    *(_DWORD *)v179 = v316;
    *((_WORD *)v120 + 2) = v113;
  }
  catch ( SQLError v297 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v272, (const struct SQLError *)v297);
      AutoPageCache::Latch(&v166, 2);
      if ( v175 )
      {
        v280 = v167[0];
        *(_DWORD *)(*((_QWORD *)v167[0] + 6) + 28LL) = 0;
        v175 = 0;
      }
      if ( **(_DWORD **)v299 )
      {
        v263 = 88;
        v292 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v155 = v292[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v281 = v155;
        v156 = *(_QWORD *)(v155 + 256);
        v261 = v156;
        if ( !v156 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v156 = *(_QWORD *)(v155 + 256);
          v261 = v156;
        }
        v157 = *(_QWORD *)(v156 + 600);
        v282 = v157;
        v158 = v167[0];
        v283 = v167[0];
        v171 = 0;
        v159 = 0;
        v208 = 0;
        while ( (unsigned int)v159 < *((_DWORD *)v158 + 3) )
        {
          v160 = *((_QWORD *)v158 + 5);
          if ( *(_QWORD *)(v160 + 40 * v159 + 8) == v157 )
          {
            *(_QWORD *)(v160 + 40 * v159 + 8) = 0;
            v171 = 1;
          }
          v159 = (unsigned int)(v159 + 1);
          v208 = v159;
        }
      }
      v264 = 88;
      v284 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v161 = v284[SystemThread_TlsIndex] + SystemThread_TlsOffset;
      v285 = v161;
      v267 = *(_QWORD *)(v161 + 256);
      if ( !v267 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v267 = *(_QWORD *)(v161 + 256);
      }
      AutoPageCache::UnLatch((AutoPageCache *)&v166);
      v162 = ExceptionBackout::GetCurrentException((ExceptionBackout *)v272);
      ExceptionRethrow(v162);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v272);
    }
    catch ( ShortStackException )
    {
    }
    v110 = v175;
    v177 = v221;
    v178 = (struct RecoveryUnit *)v195.QuadPart;
    v114 = v196;
    v120 = v179;
    goto LABEL_223;
  }
  v114 = v200;
LABEL_223:
  v115 = v193;
  v116 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v117 = *(struct Worker **)(v116 + 256);
  if ( !v117 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v117 = *(struct Worker **)(v116 + 256);
  }
  if ( *((_DWORD *)v117 + 139) )
    ExceptionPostCatchActions(v117);
  v14 = v167[0];
  if ( v110 )
  {
    if ( !v167[0] )
      utassert_fail(1u, "IsValid()", "AllocationCacheManager.cpp", 2063, 0);
    HIDWORD(v169) = 2;
    v15 = v168;
    LODWORD(v169) = LatchBase::AcquireInternal(v168, 2, 0xFFFFFFFFLL, 0, 0, 0, 0, 0, 0);
    *(_DWORD *)(*((_QWORD *)v14 + 6) + 28LL) = 0;
    LatchBase::ReleaseInternal(v15, 2);
    LODWORD(v169) = 0;
  }
  else
  {
    v15 = v168;
  }
  if ( !*(_DWORD *)v120 && !*((_WORD *)v120 + 2) )
  {
    if ( v223[0] )
      AutoAllocationCaches::Release((AutoAllocationCaches *)v223);
    if ( v14 )
    {
      if ( (_DWORD)v169 )
      {
        LatchBase::ReleaseInternal(v15, HIDWORD(v169));
        LODWORD(v169) = 0;
      }
      *(_OWORD *)v167 = 0;
    }
LABEL_239:
    if ( !(_DWORD)v169 )
      return 0;
    v87 = v15;
    v86 = HIDWORD(v169);
    goto LABEL_127;
  }
  v121 = *(_DWORD **)v299;
  **(_DWORD **)v299 = 0;
  if ( (unsigned int)(v165 + 1) > 2 )
  {
LABEL_290:
    if ( v223[0] )
      AutoAllocationCaches::Release((AutoAllocationCaches *)v223);
    goto LABEL_292;
  }
  LODWORD(v193) = 0;
  v122 = v177[2];
  v123 = *(_QWORD *)v177;
  v190 = *(_DWORD *)(*(_QWORD *)v177 + 36LL);
  v191 = *(_WORD *)(v123 + 40);
  v192 = 0;
  v124 = (v122 >> 10) & 4 | 0x88;
  if ( (v122 & 0x2000) == 0 )
    v124 = (v122 >> 10) & 4;
  LOBYTE(v164) = v124;
  if ( !(unsigned int)TargetExtentMgr::AllocPageFromTargetExtent(
                        &v269,
                        *(_QWORD *)v123,
                        v178,
                        (unsigned __int16)v172,
                        v120,
                        v164,
                        &v190,
                        v176,
                        a6,
                        &v179,
                        &v193,
                        0) )
  {
    if ( v165 != -1 )
    {
      v125 = *(_WORD *)(*(_QWORD *)(v114.QuadPart + 48) + 1720LL);
      v327 = 8;
      v326 = v125;
      v325 = 0;
      v324 = *(_DWORD *)v120;
      LOWORD(v325) = *((_WORD *)v120 + 2);
      lck_releaseClasses(v114.QuadPart + 56, &v324, 0, 0);
    }
    if ( !v14 )
      utassert_fail(1u, "IsValid()", "AllocationCacheManager.cpp", 2063, 0);
    HIDWORD(v169) = 2;
    LODWORD(v169) = LatchBase::AcquireInternal(v15, 2, 0xFFFFFFFFLL, 0, 0, 0, 0, 0, 0);
    v126 = *(_QWORD *)v177;
    LODWORD(v176) = *(_DWORD *)(*(_QWORD *)v177 + 36LL);
    HIDWORD(v176) = *(unsigned __int16 *)(v126 + 40);
    if ( PageCache::RemoveEntry(
           v14,
           (const struct PageCacheTraceData *)v274,
           v120,
           &v172,
           v178,
           (const struct AllocUnitId *)&v176)
      && !*v121 )
    {
      v127 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v128 = *(_QWORD *)(v127 + 256);
      if ( !v128 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v128 = *(_QWORD *)(v127 + 256);
      }
      v129 = 40LL * v172;
      v130 = v167[0];
      if ( !_InterlockedCompareExchange64(
              (volatile signed __int64 *)(*((_QWORD *)v167[0] + 5) + v129 + 8),
              *(_QWORD *)(v128 + 600),
              0) )
      {
        v131 = v129 + *((_QWORD *)v130 + 5);
        v132 = 0;
        v133 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)(v131 + 24) || _InterlockedCompareExchange64((volatile signed __int64 *)(v131 + 24), v133, 0) )
        {
          v134 = 0;
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v135 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset;
            if ( v135 && *(_QWORD *)(v135 + 272) == v135 )
              v134 = *(_QWORD *)(v135 + 256);
            if ( v134 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v196);
                v132 = (DirtyPageMgr *)v196.QuadPart;
              }
              else
              {
                v132 = MEMORY[0x7FFE0008];
              }
            }
          }
          v136 = v131 + 24;
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<319,1,258>::SpinToAcquireWithExponentialBackoff(v136, v133);
          else
            Spinlock<319,1,258>::SpinToAcquireOptimistic(v136, v134, v133);
          if ( v134 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v195);
              v137 = (DirtyPageMgr *)v195.QuadPart;
            }
            else
            {
              v137 = MEMORY[0x7FFE0008];
            }
            v138 = v137 - v132;
            if ( v137 < v132 )
              v138 = 0;
            *(_QWORD *)(v134 + 3192) += v138;
          }
        }
        v139 = *((_QWORD *)v130 + 5);
        v140 = *(_QWORD *)(v129 + v139);
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v141 = rand();
          if ( v141 == 5 * (v141 / 5) )
            Spinlock<319,1,258>::UpdateStatSnapshot();
        }
        *(_QWORD *)(v129 + v139 + 24) = 0;
        v142 = 0;
        if ( HIWORD(v140) )
          v142 = WORD2(v140);
        v143 = 0;
        if ( HIWORD(v140) )
          v143 = v140;
        if ( v143 || v142 )
        {
          v144 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v145 = *(_QWORD *)(v144 + 256);
          if ( !v145 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v145 = *(_QWORD *)(v144 + 256);
          }
          v146 = *((_QWORD *)v130 + 5);
          if ( *(_QWORD *)(v146 + v129 + 8) == *(_QWORD *)(v145 + 600) )
            *(_QWORD *)(v129 + v146 + 8) = 0;
        }
        else
        {
          **(_DWORD **)v299 = 1;
        }
      }
      v15 = v168;
      v14 = v167[0];
    }
    if ( !v14 )
      utassert_fail(1u, "IsValid()", "AllocationCacheManager.cpp", 2111, 0);
    LatchBase::ReleaseInternal(v15, 2);
    LODWORD(v169) = 0;
    goto LABEL_290;
  }
  *(_DWORD *)(v115 + 8) = (_DWORD)v179;
  *(_WORD *)(v115 + 12) = WORD2(v179);
  *(_WORD *)(v115 + 14) = 0;
  *(_QWORD *)v115 = 0;
  *(_DWORD *)(v115 + 28) = 2;
  *(_QWORD *)(v115 + 16) = 0;
  *(_WORD *)(v115 + 24) = 0;
  if ( v165 != -1 )
  {
    v147 = *(_WORD *)(*(_QWORD *)(v114.QuadPart + 48) + 1720LL);
    v301 = 8;
    v300 = v147;
    *(_QWORD *)&v299[4] = 0;
    *(_DWORD *)v299 = *(_DWORD *)v120;
    *(_WORD *)&v299[4] = *((_WORD *)v120 + 2);
    lck_releaseClasses(v114.QuadPart + 56, v299, 0, 0);
  }
  if ( v223[0] )
    AutoAllocationCaches::Release((AutoAllocationCaches *)v223);
  if ( v14 )
  {
    if ( (_DWORD)v169 )
    {
      LatchBase::ReleaseInternal(v15, HIDWORD(v169));
      LODWORD(v169) = 0;
    }
    *(_OWORD *)v167 = 0;
  }
  if ( (_DWORD)v169 )
  {
    LatchBase::ReleaseInternal(v15, HIDWORD(v169));
    LODWORD(v169) = 0;
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
