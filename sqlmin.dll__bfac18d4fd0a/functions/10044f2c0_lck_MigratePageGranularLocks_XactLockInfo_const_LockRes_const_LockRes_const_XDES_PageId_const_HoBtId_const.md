# lck_MigratePageGranularLocks(XactLockInfo const *,LockRes const &,LockRes const &,XDES *,PageId const &,HoBtId const &)

- ea: `0x10044f2c0`
- end: `0x10044fdb7`
- name: `?lck_MigratePageGranularLocks@@YAHPEBVXactLockInfo@@AEBVLockRes@@1PEAVXDES@@AEBVPageId@@AEBVHoBtId@@@Z`
- size: `2807`
- prototype: `int(const struct XactLockInfo *, const struct LockRes *, const struct LockRes *, struct XDES *, const struct PageId *, const struct HoBtId *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x10044ef50`

## callees

- `0x100401490`
- `0x10040df90`
- `0x1004162f0`
- `0x10041f420`
- `0x10042dd10`
- `0x10044eec0`
- `0x10044f2c0`
- `0x10047b3f0`
- `0x1004ab7a0`
- `0x1004baa60`
- `0x1005b9170`
- `0x1005b93a0`
- `0x1005d8b90`
- `0x1006c6280`
- `0x1006c6560`
- `0x101760f70`
- `0x1018797e0`
- `0x1023af450`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x10188e4c3`
- `KERNEL32!VirtualProtect` at `0x10188e923`
- `KERNEL32!VirtualProtect` at `0x10188ed40`
- `KERNEL32!VirtualProtect` at `0x10188e4c3`
- `KERNEL32!VirtualProtect` at `0x10188e923`
- `KERNEL32!VirtualProtect` at `0x10188ed40`
- `KERNEL32!QueryPerformanceCounter` at `0x10188e5f8`
- `KERNEL32!QueryPerformanceCounter` at `0x10188e644`
- `KERNEL32!QueryPerformanceCounter` at `0x10188e834`
- `KERNEL32!QueryPerformanceCounter` at `0x10188e88c`
- `KERNEL32!QueryPerformanceCounter` at `0x10188ec5b`
- `KERNEL32!QueryPerformanceCounter` at `0x10188ecaf`
- `KERNEL32!QueryPerformanceCounter` at `0x10188e5f8`
- `KERNEL32!QueryPerformanceCounter` at `0x10188e644`
- `KERNEL32!QueryPerformanceCounter` at `0x10188e834`
- `KERNEL32!QueryPerformanceCounter` at `0x10188e88c`
- `KERNEL32!QueryPerformanceCounter` at `0x10188ec5b`
- `KERNEL32!QueryPerformanceCounter` at `0x10188ecaf`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10044fa26`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10044fa4e`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10045187b`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10188e2f5`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10188e350`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10188e553`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10188e6d4`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10188e9b5`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10188ea60`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10188edd2`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10188ee67`
- `sqldk!?sm_maxCpuCount@SOS_PublicGlobals@@2KA` at `0x10044f6e5`
- `sqldk!?sm_maxCpuCount@SOS_PublicGlobals@@2KA` at `0x10044f85b`
- `sqldk!?sm_maxCpuCount@SOS_PublicGlobals@@2KA` at `0x10044fb2e`
- `sqldk!?sm_maxCpuCount@SOS_PublicGlobals@@2KA` at `0x10044fc7a`
- `sqldk!?sm_maxCpuCount@SOS_PublicGlobals@@2KA` at `0x1004517e6`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10188e592`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10188e7ce`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10188ebf8`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10188e609`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10188e845`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10188ec6c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10188e5e0`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10188e630`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10188e81c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10188e874`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10188ec43`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10188ec97`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10188ef21`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10188ef21`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10188eef7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10188eef7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10188eecc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10188eecc`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10188dfd4`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10188dfd4`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10188e17d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10188e17d`
- `sqldk!SystemThread_TlsIndex` at `0x10044f55d`
- `sqldk!SystemThread_TlsIndex` at `0x10044f653`
- `sqldk!SystemThread_TlsIndex` at `0x10044f6a5`
- `sqldk!SystemThread_TlsIndex` at `0x10044f7c9`
- `sqldk!SystemThread_TlsIndex` at `0x10044f81b`
- `sqldk!SystemThread_TlsIndex` at `0x10044fa94`
- `sqldk!SystemThread_TlsIndex` at `0x10044fae9`
- `sqldk!SystemThread_TlsIndex` at `0x10044fbd4`
- `sqldk!SystemThread_TlsIndex` at `0x10044fc29`
- `sqldk!SystemThread_TlsIndex` at `0x10044fd49`
- `sqldk!SystemThread_TlsIndex` at `0x100451713`
- `sqldk!SystemThread_TlsIndex` at `0x10045178f`
- `sqldk!SystemThread_TlsIndex` at `0x10188e10a`
- `sqldk!SystemThread_TlsIndex` at `0x10188e5b2`
- `sqldk!SystemThread_TlsIndex` at `0x10188e7ee`
- `sqldk!SystemThread_TlsIndex` at `0x10188ec15`
- `sqldk!SystemThread_TlsOffset` at `0x10044f566`
- `sqldk!SystemThread_TlsOffset` at `0x10044f65c`
- `sqldk!SystemThread_TlsOffset` at `0x10044f6ae`
- `sqldk!SystemThread_TlsOffset` at `0x10044f7d2`
- `sqldk!SystemThread_TlsOffset` at `0x10044f824`
- `sqldk!SystemThread_TlsOffset` at `0x10044fa9d`
- `sqldk!SystemThread_TlsOffset` at `0x10044faf2`
- `sqldk!SystemThread_TlsOffset` at `0x10044fbdd`
- `sqldk!SystemThread_TlsOffset` at `0x10044fc32`
- `sqldk!SystemThread_TlsOffset` at `0x10044fd52`
- `sqldk!SystemThread_TlsOffset` at `0x10045171c`
- `sqldk!SystemThread_TlsOffset` at `0x100451798`
- `sqldk!SystemThread_TlsOffset` at `0x10188e113`
- `sqldk!SystemThread_TlsOffset` at `0x10188e5bb`
- `sqldk!SystemThread_TlsOffset` at `0x10188e7f7`
- `sqldk!SystemThread_TlsOffset` at `0x10188ec1e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100451737`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004517b3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188e025`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188e05a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188e07f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188e0b4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188e12c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188e723`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188e764`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188eacd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188eb0e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188ef0e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100451737`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004517b3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188e025`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188e05a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188e07f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188e0b4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188e12c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188e723`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188e764`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188eacd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188eb0e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188ef0e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10188e0da`
- `sqldk!??_V@YAXPEAX@Z` at `0x10188ef2e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10188e0da`
- `sqldk!??_V@YAXPEAX@Z` at `0x10188ef2e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100451887`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188e301`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188e35c`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188e38f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188e3c1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188e55f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188e6e0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188e9c1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188ea6c`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188edde`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188ee73`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100451887`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188e301`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188e35c`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188e38f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188e3c1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188e55f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188e6e0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188e9c1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188ea6c`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188edde`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188ee73`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall lck_MigratePageGranularLocks(
        const struct XactLockInfo *a1,
        const struct LockRes *a2,
        const struct LockRes *a3,
        struct XDES *a4,
        const struct PageId *a5,
        const struct HoBtId *a6)
{
  char v6; // cl
  _DWORD *v7; // r13
  __int64 *v8; // rdx
  __int64 *v9; // rdi
  __int64 *v10; // rsi
  __int64 v11; // rax
  char v12; // cl
  __int64 v13; // rdx
  __int64 v14; // rax
  int v15; // edx
  __int16 v16; // r8
  int v17; // ecx
  __int64 m; // rax
  bool k; // zf
  char v20; // cl
  __int64 v21; // rax
  __int64 v24; // r15
  struct Lock *LockBlocks; // r13
  int v26; // r12d
  int v27; // esi
  __int64 v28; // rdx
  struct CSessionTraceFlags *v29; // rcx
  LockHashSlot *v30; // r10
  LockHashSlot *v31; // rdx
  LockHashSlot *v32; // rcx
  LockHashSlot *v33; // rax
  LockHashSlot *v34; // rbx
  struct LockMigrateLogInfo *v35; // r14
  __int64 v36; // rdi
  __int64 v37; // rbx
  int v38; // eax
  char v39; // si
  __int64 v40; // rdi
  __int64 v41; // r8
  unsigned __int64 v42; // rdx
  struct LockRes *v43; // rbx
  __int64 v44; // rdi
  __int64 v45; // rbx
  int v46; // eax
  char v47; // si
  __int64 v48; // rdi
  __int64 v49; // r8
  unsigned __int64 v50; // rdx
  struct LockOwner *LockOwnerBlocks; // rcx
  __int64 v52; // rax
  struct Lock *v53; // rbx
  LockHashSlot *v54; // rdi
  struct Lock *v55; // r10
  int v56; // r8d
  int i; // r9d
  __int64 v58; // rdi
  __int64 **v59; // r11
  __int64 *j; // rbx
  LockHashSlot *v61; // rbx
  struct SList *v62; // rsi
  __int64 v63; // rbx
  __int64 v64; // r14
  int v65; // eax
  __int64 v66; // rbx
  __int64 v67; // rdx
  __int64 v68; // rcx
  struct ExternalLockValueBlockBase *v69; // r12
  __int64 v70; // r10
  struct SList **v71; // r8
  unsigned __int64 v72; // r9
  struct SList *v73; // rsi
  __int64 v74; // r14
  __int64 v75; // rbx
  __int64 v76; // r13
  int v77; // eax
  __int64 v78; // rbx
  __int64 v79; // r9
  __int64 v80; // r10
  char v81; // r8
  unsigned __int64 v82; // rdx
  __int64 v83; // r8
  unsigned __int64 v84; // r10
  unsigned int v85; // edi
  __int64 v86; // rbx
  struct Worker *v87; // rcx
  LockHashSlot *v89; // rbx
  struct ExternalLockValueBlockBase **v90; // rcx
  struct ExternalLockValueBlockBase **v91; // rsi
  __int64 v92; // rbx
  __int64 v93; // r14
  int v94; // eax
  __int64 v95; // rbx
  __int64 v96; // rdx
  __int64 v97; // rcx
  struct ExternalLockValueBlockBase *v98; // r12
  __int64 v99; // r10
  struct ExternalLockValueBlockBase ***v100; // r8
  unsigned __int64 v101; // r9
  int v102; // r8d
  const wchar_t *v103; // rax
  __int64 v104; // rbx
  __int64 v105; // rdi
  __int64 v106; // rcx
  struct IMemObj *v107; // rcx
  unsigned __int64 v108; // rax
  struct LockMigrateLogInfo *v109; // rax
  unsigned __int64 v110; // rcx
  __int64 v111; // rax
  char v112; // cl
  __int64 v113; // rax
  char v114; // cl
  __int64 v115; // rax
  int v116; // r8d
  LockHashSlot *v117; // rbx
  int v118; // r8d
  int v119; // r8d
  int v120; // r8d
  __int64 v121; // rdi
  DirtyPageMgr *QuadPart; // rbx
  signed __int64 UniqueThread_low; // r13
  struct ExternalLockValueBlockBase ***v124; // rcx
  unsigned __int64 v125; // rdx
  SOS_ObjectStore *v126; // rcx
  unsigned int PoolIdForObject; // eax
  __int64 v128; // r9
  __int64 v129; // r10
  _QWORD *v130; // r8
  __int64 v131; // rax
  __int64 v132; // rcx
  int v133; // r8d
  __int64 v134; // rsi
  __int64 v135; // r8
  __int64 v136; // rcx
  DirtyPageMgr *v137; // rax
  signed __int64 v138; // rcx
  int v139; // r8d
  __int64 v140; // rdi
  DirtyPageMgr *v141; // rbx
  signed __int64 v142; // r13
  __int64 v143; // rsi
  __int64 v144; // r8
  __int64 v145; // rcx
  DirtyPageMgr *v146; // rax
  signed __int64 v147; // rcx
  struct SList **v148; // rcx
  unsigned __int64 v149; // rax
  SOS_ObjectStore *v150; // rcx
  __int64 v151; // r10
  __int64 v152; // r9
  __int64 v153; // rax
  _QWORD *v154; // r8
  __int64 v155; // rcx
  int v156; // r8d
  int v157; // r8d
  unsigned __int64 v158; // rax
  __int64 v159; // rax
  unsigned __int64 v160; // rdx
  __int64 v161; // rdx
  unsigned int v162; // ecx
  __int64 *v163; // rax
  __int64 v164; // rdi
  DirtyPageMgr *v165; // rbx
  signed __int64 v166; // r12
  __int64 v167; // r8
  __int64 v168; // rcx
  DirtyPageMgr *v169; // rax
  signed __int64 v170; // rcx
  _QWORD *v171; // rcx
  unsigned __int64 v172; // rax
  SOS_ObjectStore *v173; // rcx
  __int64 v174; // r10
  __int64 v175; // r9
  __int64 v176; // rax
  _QWORD *v177; // r8
  __int64 v178; // rcx
  int v179; // r8d
  int v180; // r8d
  const struct SQLError *CurrentException; // rax
  char v182; // [rsp+30h] [rbp-4D8h]
  char v183; // [rsp+30h] [rbp-4D8h]
  char v184; // [rsp+30h] [rbp-4D8h]
  int v185; // [rsp+34h] [rbp-4D4h]
  int v186; // [rsp+38h] [rbp-4D0h]
  int v187; // [rsp+3Ch] [rbp-4CCh]
  int v188; // [rsp+40h] [rbp-4C8h]
  int v189; // [rsp+44h] [rbp-4C4h]
  int v190; // [rsp+48h] [rbp-4C0h]
  struct ExternalLockValueBlockBase **lpAddress; // [rsp+50h] [rbp-4B8h]
  struct SList *v192; // [rsp+58h] [rbp-4B0h]
  struct LockMigrateLogInfo *v193; // [rsp+60h] [rbp-4A8h]
  struct SList *v194; // [rsp+68h] [rbp-4A0h] BYREF
  int v195; // [rsp+70h] [rbp-498h]
  LockHashSlot *v196; // [rsp+78h] [rbp-490h]
  __int64 v197; // [rsp+80h] [rbp-488h]
  __int64 **v198; // [rsp+88h] [rbp-480h]
  int v199; // [rsp+90h] [rbp-478h] BYREF
  LockHashSlot *v200; // [rsp+98h] [rbp-470h]
  LockHashSlot *v201; // [rsp+A0h] [rbp-468h]
  struct LockRes *v202; // [rsp+A8h] [rbp-460h]
  struct LockMigrateLogInfo *v203; // [rsp+B0h] [rbp-458h]
  DWORD flOldProtect; // [rsp+B8h] [rbp-450h] BYREF
  DWORD v205; // [rsp+BCh] [rbp-44Ch] BYREF
  DWORD v206; // [rsp+C0h] [rbp-448h] BYREF
  struct LockRes *v207; // [rsp+C8h] [rbp-440h]
  LockHashSlot *v208; // [rsp+D0h] [rbp-438h]
  struct Lock *v209; // [rsp+D8h] [rbp-430h]
  LARGE_INTEGER PerformanceCount; // [rsp+E0h] [rbp-428h] BYREF
  LARGE_INTEGER v211; // [rsp+E8h] [rbp-420h] BYREF
  LARGE_INTEGER v212; // [rsp+F0h] [rbp-418h] BYREF
  LARGE_INTEGER v213; // [rsp+F8h] [rbp-410h] BYREF
  LARGE_INTEGER v214; // [rsp+100h] [rbp-408h] BYREF
  LARGE_INTEGER v215; // [rsp+108h] [rbp-400h] BYREF
  struct HoBtId *v216; // [rsp+110h] [rbp-3F8h]
  struct PageId *v217; // [rsp+118h] [rbp-3F0h]
  struct XDES *v218; // [rsp+120h] [rbp-3E8h]
  int v219; // [rsp+128h] [rbp-3E0h]
  __int64 v220; // [rsp+130h] [rbp-3D8h]
  char v221; // [rsp+138h] [rbp-3D0h]
  __int64 v222; // [rsp+140h] [rbp-3C8h]
  char v223; // [rsp+148h] [rbp-3C0h]
  __int64 v224; // [rsp+150h] [rbp-3B8h]
  char v225; // [rsp+158h] [rbp-3B0h]
  __int64 v226; // [rsp+160h] [rbp-3A8h]
  char v227; // [rsp+168h] [rbp-3A0h]
  __int64 v228; // [rsp+170h] [rbp-398h]
  char v229; // [rsp+178h] [rbp-390h]
  _QWORD v230[4]; // [rsp+180h] [rbp-388h] BYREF
  _BYTE v231[32]; // [rsp+1A0h] [rbp-368h] BYREF
  int v232; // [rsp+1C0h] [rbp-348h] BYREF
  __int16 v233; // [rsp+1C4h] [rbp-344h]
  int v234; // [rsp+1C8h] [rbp-340h]
  __int16 v235; // [rsp+1CCh] [rbp-33Ch]
  int v236; // [rsp+1D0h] [rbp-338h]
  __int16 v237; // [rsp+1D4h] [rbp-334h]
  int v238; // [rsp+1D8h] [rbp-330h]
  __int16 v239; // [rsp+1DCh] [rbp-32Ch]
  int v240; // [rsp+1E0h] [rbp-328h]
  __int16 v241; // [rsp+1E4h] [rbp-324h]
  int v242; // [rsp+1E8h] [rbp-320h]
  __int16 v243; // [rsp+1ECh] [rbp-31Ch]
  int v244; // [rsp+1F0h] [rbp-318h]
  __int16 v245; // [rsp+1F4h] [rbp-314h]
  int v246; // [rsp+1F8h] [rbp-310h]
  __int16 v247; // [rsp+1FCh] [rbp-30Ch]
  int v248; // [rsp+200h] [rbp-308h]
  __int16 v249; // [rsp+204h] [rbp-304h]
  int v250; // [rsp+208h] [rbp-300h]
  __int16 v251; // [rsp+20Ch] [rbp-2FCh]
  int v252; // [rsp+210h] [rbp-2F8h]
  __int16 v253; // [rsp+214h] [rbp-2F4h]
  int v254; // [rsp+218h] [rbp-2F0h]
  __int16 v255; // [rsp+21Ch] [rbp-2ECh]
  int v256; // [rsp+220h] [rbp-2E8h]
  __int16 v257; // [rsp+224h] [rbp-2E4h]
  int v258; // [rsp+228h] [rbp-2E0h]
  __int16 v259; // [rsp+22Ch] [rbp-2DCh]
  int v260; // [rsp+230h] [rbp-2D8h]
  __int16 v261; // [rsp+234h] [rbp-2D4h]
  int v262; // [rsp+238h] [rbp-2D0h]
  __int16 v263; // [rsp+23Ch] [rbp-2CCh]
  int v264; // [rsp+240h] [rbp-2C8h]
  __int16 v265; // [rsp+244h] [rbp-2C4h]
  int v266; // [rsp+248h] [rbp-2C0h]
  __int16 v267; // [rsp+24Ch] [rbp-2BCh]
  int v268; // [rsp+250h] [rbp-2B8h]
  __int16 v269; // [rsp+254h] [rbp-2B4h]
  int v270; // [rsp+258h] [rbp-2B0h]
  __int16 v271; // [rsp+25Ch] [rbp-2ACh]
  int v272; // [rsp+260h] [rbp-2A8h]
  __int16 v273; // [rsp+264h] [rbp-2A4h]
  int v274; // [rsp+268h] [rbp-2A0h]
  __int16 v275; // [rsp+26Ch] [rbp-29Ch]
  int v276; // [rsp+270h] [rbp-298h]
  __int16 v277; // [rsp+274h] [rbp-294h]
  int v278; // [rsp+278h] [rbp-290h]
  __int16 v279; // [rsp+27Ch] [rbp-28Ch]
  int v280; // [rsp+280h] [rbp-288h]
  __int16 v281; // [rsp+284h] [rbp-284h]
  int v282; // [rsp+288h] [rbp-280h]
  __int16 v283; // [rsp+28Ch] [rbp-27Ch]
  int v284; // [rsp+290h] [rbp-278h]
  __int16 v285; // [rsp+294h] [rbp-274h]
  int v286; // [rsp+298h] [rbp-270h]
  __int16 v287; // [rsp+29Ch] [rbp-26Ch]
  int v288; // [rsp+2A0h] [rbp-268h]
  __int16 v289; // [rsp+2A4h] [rbp-264h]
  int v290; // [rsp+2A8h] [rbp-260h]
  __int16 v291; // [rsp+2ACh] [rbp-25Ch]
  int v292; // [rsp+2B0h] [rbp-258h]
  __int16 v293; // [rsp+2B4h] [rbp-254h]
  int v294; // [rsp+2B8h] [rbp-250h]
  __int16 v295; // [rsp+2BCh] [rbp-24Ch]
  wchar_t v296[256]; // [rsp+2C0h] [rbp-248h] BYREF

  v230[2] = -2;
  v218 = a4;
  v202 = a3;
  v207 = a2;
  v217 = a5;
  v216 = a6;
  v24 = 0;
  lpAddress = 0;
  LockBlocks = 0;
  v192 = 0;
  v194 = 0;
  v26 = 0;
  v189 = 0;
  v195 = 0;
  v27 = 0;
  v185 = 0;
  v232 = 0;
  v233 = 0;
  v234 = 0;
  v235 = 0;
  v236 = 0;
  v237 = 0;
  v238 = 0;
  v239 = 0;
  v240 = 0;
  v241 = 0;
  v242 = 0;
  v243 = 0;
  v244 = 0;
  v245 = 0;
  v246 = 0;
  v247 = 0;
  v248 = 0;
  v249 = 0;
  v250 = 0;
  v251 = 0;
  v252 = 0;
  v253 = 0;
  v254 = 0;
  v255 = 0;
  v256 = 0;
  v257 = 0;
  v258 = 0;
  v259 = 0;
  v260 = 0;
  v261 = 0;
  v262 = 0;
  v263 = 0;
  v264 = 0;
  v265 = 0;
  v266 = 0;
  v267 = 0;
  v268 = 0;
  v269 = 0;
  v270 = 0;
  v271 = 0;
  v272 = 0;
  v273 = 0;
  v274 = 0;
  v275 = 0;
  v276 = 0;
  v277 = 0;
  v278 = 0;
  v279 = 0;
  v280 = 0;
  v281 = 0;
  v282 = 0;
  v283 = 0;
  v284 = 0;
  v285 = 0;
  v286 = 0;
  v287 = 0;
  v288 = 0;
  v289 = 0;
  v290 = 0;
  v291 = 0;
  v292 = 0;
  v293 = 0;
  v294 = 0;
  v295 = 0;
  v190 = 0;
  v188 = 32;
  if ( (byte_10317AC16 & 0x40) != 0
    || (v28 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
        *(_QWORD *)v28)
    && (v29 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v28 + 56LL)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v29, 0x4B6u) )
  {
    v199 = 512;
    v103 = LockRes::Format(a2, v296, &v199, 0, 0);
    traceprint(L"  -- Migrating non-intent lock resource: %ls\n", v103);
  }
  v30 = (LockHashSlot *)(theLockManager[0]
                       + 16LL
                       * ((((*((_DWORD *)a3 + 1)
                           ^ *((_DWORD *)a3 + 2)
                           ^ *(_DWORD *)a3
                           ^ (16 * *((unsigned __int16 *)a3 + 6))
                           ^ ((*(_DWORD *)a3 ^ (unsigned int)*((unsigned __int8 *)a3 + 14)) << 7)) >> 10)
                         ^ *((_DWORD *)a3 + 1)
                         ^ *((_DWORD *)a3 + 2)
                         ^ *(_DWORD *)a3
                         ^ (16 * *((unsigned __int16 *)a3 + 6))
                         ^ ((*(_DWORD *)a3 ^ *((unsigned __int8 *)a3 + 14)) << 7))
                        & (dword_10317F808 - 1)));
  v196 = v30;
  v31 = (LockHashSlot *)(theLockManager[0]
                       + 16LL
                       * ((dword_10317F808 - 1)
                        & (((*(_DWORD *)a2
                           ^ *((_DWORD *)a2 + 1)
                           ^ *((_DWORD *)a2 + 2)
                           ^ (16 * *((unsigned __int16 *)a2 + 6))
                           ^ ((*(_DWORD *)a2 ^ (unsigned int)*((unsigned __int8 *)a2 + 14)) << 7)) >> 10)
                         ^ *(_DWORD *)a2
                         ^ *((_DWORD *)a2 + 1)
                         ^ *((_DWORD *)a2 + 2)
                         ^ (16 * *((unsigned __int16 *)a2 + 6))
                         ^ ((*(_DWORD *)a2 ^ *((unsigned __int8 *)a2 + 14)) << 7))));
  v208 = v31;
  v32 = v30;
  if ( v31 <= v30 )
    v32 = v31;
  v200 = v32;
  v33 = v31;
  if ( v31 <= v30 )
    v33 = v30;
  v34 = 0;
  if ( v32 != v33 )
    v34 = v33;
  v201 = v34;
  v35 = (struct LockMigrateLogInfo *)&v232;
  v193 = (struct LockMigrateLogInfo *)&v232;
LABEL_11:
  if ( !LockBlocks )
  {
    v36 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v37 = *(_QWORD *)(v36 + 256);
    if ( !v37 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v37 = *(_QWORD *)(v36 + 256);
    }
    v222 = v37;
    v38 = *(_DWORD *)(v37 + 800);
    if ( (v38 & 0x1000000) == 0 || (*(_BYTE *)(v37 + 616) & 0x40) != 0 )
    {
      v39 = 0;
    }
    else
    {
      v39 = 1;
      *(_DWORD *)(v37 + 800) = v38 & 0xFEFFFFFF;
    }
    v223 = v39;
    v40 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v41 = *(_QWORD *)(v40 + 256);
    if ( !v41 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v41 = *(_QWORD *)(v40 + 256);
    }
    v42 = qword_103182380 + ((unsigned __int64)*(unsigned int *)(*(_QWORD *)(v41 + 608) + 3688LL) << 7);
    if ( *(_DWORD *)(*(_QWORD *)(v41 + 608) + 3688LL) >= SOS_PublicGlobals::sm_maxCpuCount
      || !*(_QWORD *)v42
      || (*(_BYTE *)(v41 + 800) & 4) != 0 )
    {
      LockBlocks = LockManager::GetLockBlocks((LockManager *)theLockManager, (struct Worker *)v41);
    }
    else
    {
      _mm_lfence();
      LockBlocks = *(struct Lock **)v42;
      *(_QWORD *)v42 = **(_QWORD **)v42;
      *(_QWORD *)LockBlocks = 0;
      --*(_QWORD *)(v42 + 16);
      *((_QWORD *)LockBlocks + 1) = 0;
      *((_QWORD *)LockBlocks + 2) = 0;
      *((_QWORD *)LockBlocks + 3) = 0;
      *((_QWORD *)LockBlocks + 4) = 0;
      *((_QWORD *)LockBlocks + 5) = 0;
      *((_QWORD *)LockBlocks + 6) = 0;
      *((_QWORD *)LockBlocks + 7) = 0;
      *((_QWORD *)LockBlocks + 8) = 0;
      *((_QWORD *)LockBlocks + 9) = 0;
      *((_QWORD *)LockBlocks + 10) = 0;
      *((_WORD *)LockBlocks + 44) = 0;
      *((_BYTE *)LockBlocks + 91) = 0;
    }
    v192 = LockBlocks;
    if ( v39 )
      *(_DWORD *)(v37 + 800) |= 0x1000000u;
    if ( !LockBlocks )
    {
LABEL_67:
      v189 = 1;
      goto LABEL_68;
    }
    *((_BYTE *)LockBlocks + 90) = 0;
    v43 = v202;
    *((_QWORD *)LockBlocks + 13) = *(_QWORD *)v202;
    *((_DWORD *)LockBlocks + 28) = *((_DWORD *)v43 + 2);
    *((_WORD *)LockBlocks + 58) = *((_WORD *)v43 + 6);
    *((_BYTE *)LockBlocks + 118) = *((_BYTE *)v43 + 14);
    v35 = v193;
    v27 = v185;
  }
  if ( v27 < v188 )
  {
    while ( 1 )
    {
      v44 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v45 = *(_QWORD *)(v44 + 256);
      if ( !v45 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v45 = *(_QWORD *)(v44 + 256);
      }
      v224 = v45;
      v46 = *(_DWORD *)(v45 + 800);
      if ( (v46 & 0x1000000) == 0 || (*(_BYTE *)(v45 + 616) & 0x40) != 0 )
      {
        v47 = 0;
      }
      else
      {
        v47 = 1;
        *(_DWORD *)(v45 + 800) = v46 & 0xFEFFFFFF;
      }
      v225 = v47;
      v48 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v49 = *(_QWORD *)(v48 + 256);
      if ( !v49 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v49 = *(_QWORD *)(v48 + 256);
      }
      v50 = qword_103182380 + ((unsigned __int64)*(unsigned int *)(*(_QWORD *)(v49 + 608) + 3688LL) << 7);
      if ( *(_DWORD *)(*(_QWORD *)(v49 + 608) + 3688LL) >= SOS_PublicGlobals::sm_maxCpuCount
        || !*(_QWORD *)(v50 + 8)
        || (*(_BYTE *)(v49 + 800) & 4) != 0 )
      {
        LockOwnerBlocks = LockManager::GetLockOwnerBlocks((LockManager *)theLockManager, (struct Worker *)v49);
      }
      else
      {
        _mm_lfence();
        LockOwnerBlocks = *(struct LockOwner **)(v50 + 8);
        *(_QWORD *)(v50 + 8) = *(_QWORD *)LockOwnerBlocks;
        *(_QWORD *)LockOwnerBlocks = 0;
        --*(_QWORD *)(v50 + 24);
        v52 = *((_QWORD *)LockOwnerBlocks + 4);
        *(_QWORD *)LockOwnerBlocks = 0;
        *((_QWORD *)LockOwnerBlocks + 1) = 0;
        *((_QWORD *)LockOwnerBlocks + 2) = 0;
        *((_QWORD *)LockOwnerBlocks + 3) = 0;
        *((_QWORD *)LockOwnerBlocks + 5) = 0;
        *((_QWORD *)LockOwnerBlocks + 6) = 0;
        *((_QWORD *)LockOwnerBlocks + 7) = 0;
        *((_QWORD *)LockOwnerBlocks + 4) = v52;
      }
      if ( v47 )
        *(_DWORD *)(v45 + 800) |= 0x1000000u;
      if ( !LockOwnerBlocks )
        goto LABEL_67;
      *(_QWORD *)LockOwnerBlocks = v194;
      v194 = LockOwnerBlocks;
      if ( ++v185 >= v188 )
      {
        v35 = v193;
        break;
      }
    }
  }
  if ( v35 != (struct LockMigrateLogInfo *)&v232 )
  {
    operator delete[](v35);
    v35 = (struct LockMigrateLogInfo *)&v232;
    v193 = (struct LockMigrateLogInfo *)&v232;
  }
  if ( v188 <= 32 )
    goto LABEL_45;
  v104 = v188;
  v219 = 19312;
  v105 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v106 = *(_QWORD *)(v105 + 256);
  if ( !v106 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v106 = *(_QWORD *)(v105 + 256);
  }
  v107 = *(struct IMemObj **)(v106 + 1000);
  v230[3] = v107;
  v108 = 8LL * v188;
  if ( !is_mul_ok(v188, 8u) )
    v108 = -1;
  v109 = (struct LockMigrateLogInfo *)operator new[](
                                        v108,
                                        v107,
                                        1,
                                        "sql\\ntdbms\\storeng\\dfs\\manager\\lckmgr.cpp",
                                        19312,
                                        5u);
  v35 = v109;
  v203 = v109;
  if ( v109 )
  {
    do
    {
      *(_DWORD *)v109 = 0;
      *((_WORD *)v109 + 2) = 0;
      v109 = (struct LockMigrateLogInfo *)((char *)v109 + 8);
      --v104;
    }
    while ( v104 );
  }
  else
  {
    v35 = 0;
  }
  v193 = v35;
  if ( v35 )
  {
LABEL_45:
    v185 = v188;
    LockHashSlot::LockSlot(v200);
    if ( v201 )
      LockHashSlot::LockSlot(v201);
    v53 = LockHashSlot::LookupLock(v208, v207);
    v209 = v53;
    v54 = v196;
    v55 = LockHashSlot::LookupLock(v196, v202);
    lpAddress = (struct ExternalLockValueBlockBase **)v55;
    if ( !v55 )
    {
      v55 = LockBlocks;
      lpAddress = (struct ExternalLockValueBlockBase **)LockBlocks;
      v110 = 2 * LockHashSlot::SLOTS_TO_SKIP;
      *(_QWORD *)LockBlocks = *((_QWORD *)v54 + 2 * LockHashSlot::SLOTS_TO_SKIP + 1);
      *((_QWORD *)v54 + v110 + 1) = LockBlocks;
      *((_QWORD *)LockBlocks + 1) = v54;
      v192 = 0;
      v195 = 1;
    }
    if ( v53 && (*((_BYTE *)v53 + 91) & 2) != 0 )
    {
      *((_QWORD *)v55 + 12) = *((_QWORD *)v53 + 12);
      *((_BYTE *)v55 + 91) |= 2u;
    }
    v56 = v188;
    v186 = v188;
    for ( i = 0; ; ++i )
    {
      v187 = i;
      if ( i > 1 || !v53 )
        break;
      v58 = 0;
      v197 = 0;
      v59 = (__int64 **)((char *)v53 + 16);
      v198 = (__int64 **)((char *)v53 + 16);
      do
      {
        for ( j = *v59; j; j = (__int64 *)*j )
        {
          v6 = *((_BYTE *)j + 55);
          if ( (v6 & 1) == 0 )
          {
            if ( *((_BYTE *)j + 54) )
              goto LABEL_118;
            v111 = j[5];
            if ( (v6 & 2) != 0 )
              v111 = *(_QWORD *)(v111 + 56);
            if ( *(_DWORD *)(v111 + 80) != 7 )
            {
LABEL_118:
              v7 = (_DWORD *)((char *)v35 + 8 * v24);
              while ( 1 )
              {
                v8 = (__int64 *)*j;
                if ( !dword_10319A5A4[5 * *((unsigned __int8 *)j + 54)] )
                {
                  j = (__int64 *)*j;
                  for ( k = v8 == 0; !k; k = j == 0 )
                  {
                    v20 = *((_BYTE *)j + 55);
                    if ( (v20 & 1) == 0 )
                    {
                      if ( *((_BYTE *)j + 54) )
                        goto LABEL_133;
                      v21 = j[5];
                      if ( (v20 & 2) != 0 )
                        v21 = *(_QWORD *)(v21 + 56);
                      if ( *(_DWORD *)(v21 + 80) != 7 )
                        goto LABEL_133;
                    }
                    j = (__int64 *)*j;
                  }
LABEL_134:
                  v59 = v198;
                  v58 = v197;
                  goto LABEL_58;
                }
                if ( i )
                {
                  v9 = j;
                  v10 = j;
                  j = (__int64 *)*j;
                  if ( v8 )
                  {
                    while ( 1 )
                    {
                      v114 = *((_BYTE *)j + 55);
                      if ( (v114 & 1) == 0 )
                      {
                        if ( *((_BYTE *)j + 54) )
                          break;
                        v115 = j[5];
                        if ( (v114 & 2) != 0 )
                          v115 = *(_QWORD *)(v115 + 56);
                        if ( *(_DWORD *)(v115 + 80) != 7 )
                          break;
                      }
                      j = (__int64 *)*j;
                      if ( !j )
                        goto LABEL_122;
                    }
                  }
                  else
                  {
LABEL_122:
                    j = 0;
                  }
                  LockOwner::CopyReference(v9, v55, &v194);
                  v26 = 1;
                  if ( *((_BYTE *)v9 + 54) == 5 )
                  {
                    v11 = v10[5];
                    v12 = *((_BYTE *)v9 + 55) & 2;
                    v13 = v12 ? *(_QWORD *)(v11 + 56) : v10[5];
                    if ( *(_DWORD *)(v13 + 80) == 1 )
                    {
                      if ( v12 )
                        v11 = *(_QWORD *)(v11 + 56);
                      v14 = *(_QWORD *)(v11 + 88);
                      v15 = *(_DWORD *)(v14 + 40);
                      v16 = *(_WORD *)(v14 + 44);
                      v17 = 0;
                      for ( m = 0; m < v24; ++m )
                      {
                        if ( *((_WORD *)v35 + 4 * m + 2) == v16 && *((_DWORD *)v35 + 2 * m) == v15 )
                          break;
                        ++v17;
                      }
                      if ( v17 == v190 )
                      {
                        *v7 = v15;
                        *((_WORD *)v7 + 2) = v16;
                        *((_WORD *)v7 + 3) = 1;
                        ++v190;
                        ++v24;
                        v7 += 2;
                      }
                    }
                  }
                  i = v187;
                  v56 = v186;
                }
                else
                {
                  j = (__int64 *)*j;
                  if ( v8 )
                  {
                    while ( 1 )
                    {
                      v112 = *((_BYTE *)j + 55);
                      if ( (v112 & 1) == 0 )
                      {
                        if ( *((_BYTE *)j + 54) )
                          break;
                        v113 = j[5];
                        if ( (v112 & 2) != 0 )
                          v113 = *(_QWORD *)(v113 + 56);
                        if ( *(_DWORD *)(v113 + 80) != 7 )
                          break;
                      }
                      j = (__int64 *)*j;
                      if ( !j )
                        goto LABEL_188;
                    }
                  }
                  else
                  {
LABEL_188:
                    j = 0;
                  }
                  if ( !v56 )
                  {
                    v188 *= 2;
                    if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                    {
                      v116 = rand();
                      if ( v116 == 5 * (v116 / 5) )
                        Spinlock<183,7,257>::UpdateStatSnapshot();
                    }
                    *(_QWORD *)v200 = 0;
                    v117 = v201;
                    LockBlocks = v192;
                    v27 = v185;
                    if ( v201 )
                    {
                      if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                      {
                        v118 = rand();
                        if ( v118 == 5 * (v118 / 5) )
                          Spinlock<183,7,257>::UpdateStatSnapshot();
                      }
                      *(_QWORD *)v117 = 0;
                    }
                    goto LABEL_11;
                  }
                  v186 = --v56;
                }
LABEL_133:
                v55 = (struct Lock *)lpAddress;
                if ( !j )
                  goto LABEL_134;
              }
            }
          }
        }
LABEL_58:
        v197 = ++v58;
        v198 = ++v59;
        v55 = (struct Lock *)lpAddress;
      }
      while ( v58 <= 3 );
      v53 = v209;
    }
    if ( v26 )
    {
      Lock::GrantLocks(v55);
      if ( v53 )
        Lock::GrantLocks(v53);
    }
    if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v119 = rand();
      if ( v119 == 5 * (v119 / 5) )
        Spinlock<183,7,257>::UpdateStatSnapshot();
    }
    *(_QWORD *)v200 = 0;
    v61 = v201;
    if ( v201 )
    {
      if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v120 = rand();
        if ( v120 == 5 * (v120 / 5) )
          Spinlock<183,7,257>::UpdateStatSnapshot();
      }
      *(_QWORD *)v61 = 0;
    }
  }
  else
  {
    v189 = 1;
  }
LABEL_68:
  if ( !v26 && v195 )
  {
    v89 = v196;
    LockHashSlot::LockSlot(v196);
    v90 = (struct ExternalLockValueBlockBase **)*((_QWORD *)v89 + 2 * LockHashSlot::SLOTS_TO_SKIP + 1);
    if ( v90 )
    {
      while ( *((_DWORD *)v90 + 26) != *(_DWORD *)v202
           || *((_DWORD *)v90 + 27) != *((_DWORD *)v202 + 1)
           || *((_WORD *)v90 + 58) != *((_WORD *)v202 + 6)
           || *((_BYTE *)v90 + 118) != *((_BYTE *)v202 + 14)
           || *((_DWORD *)v90 + 28) != *((_DWORD *)v202 + 2) )
      {
        v90 = (struct ExternalLockValueBlockBase **)*v90;
        if ( !v90 )
          goto LABEL_151;
      }
    }
    else
    {
LABEL_151:
      v90 = 0;
    }
    v91 = lpAddress;
    if ( v90 == lpAddress
      && !lpAddress[2]
      && !lpAddress[3]
      && !lpAddress[4]
      && !lpAddress[5]
      && !lpAddress[6]
      && !lpAddress[7]
      && !lpAddress[8]
      && !lpAddress[9]
      && !lpAddress[10]
      && !*((_WORD *)lpAddress + 44) )
    {
      LockHashSlot::RemoveLock(v89, (struct Lock *)lpAddress);
      v92 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v93 = *(_QWORD *)(v92 + 256);
      if ( !v93 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v93 = *(_QWORD *)(v92 + 256);
      }
      v226 = v93;
      v94 = *(_DWORD *)(v93 + 800);
      if ( (v94 & 0x1000000) == 0 || (*(_BYTE *)(v93 + 616) & 0x40) != 0 )
      {
        v184 = 0;
        v227 = 0;
      }
      else
      {
        v184 = 1;
        v227 = 1;
        *(_DWORD *)(v93 + 800) = v94 & 0xFEFFFFFF;
      }
      v95 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v96 = *(_QWORD *)(v95 + 256);
      if ( !v96 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v96 = *(_QWORD *)(v95 + 256);
      }
      v97 = *(unsigned int *)(*(_QWORD *)(v96 + 608) + 3688LL);
      if ( (*((_BYTE *)lpAddress + 91) & 4) != 0 )
        v98 = lpAddress[12];
      else
        v98 = 0;
      v99 = *((unsigned __int8 *)lpAddress + 119);
      if ( (unsigned int)v97 >= SOS_PublicGlobals::sm_maxCpuCount
        || (v100 = (struct ExternalLockValueBlockBase ***)(qword_103182380 + (v97 << 7)),
            v101 = (unsigned __int64)v100[2],
            v101 >= 0x3E8)
        || (*(_BYTE *)(v96 + 800) & 4) != 0
        || (_DWORD)v99 != *(unsigned __int16 *)(*(_QWORD *)(v96 + 992) + 160LL) )
      {
        v121 = *(_QWORD *)(theLockManager[5 * v99 + 3] + 2016);
        QuadPart = 0;
        UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)(v121 + 40)
          || _InterlockedCompareExchange64((volatile signed __int64 *)(v121 + 40), UniqueThread_low, 0) )
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
                QueryPerformanceCounter(&PerformanceCount);
                QuadPart = (DirtyPageMgr *)PerformanceCount.QuadPart;
              }
              else
              {
                QuadPart = MEMORY[0x7FFE0008];
              }
            }
          }
          v136 = v121 + 40;
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v136, UniqueThread_low);
          else
            Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v136, v134, UniqueThread_low);
          if ( v134 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v211);
              v137 = (DirtyPageMgr *)v211.QuadPart;
            }
            else
            {
              v137 = MEMORY[0x7FFE0008];
            }
            v138 = v137 - QuadPart;
            if ( v137 < QuadPart )
              v138 = 0;
            *(_QWORD *)(v134 + 3192) += v138;
            v91 = lpAddress;
          }
          else
          {
            v91 = lpAddress;
          }
        }
        if ( *(_QWORD *)(v121 + 8) >= *(_QWORD *)v121 )
        {
          if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v139 = rand();
            if ( v139 == 5 * (v139 / 5) )
              Spinlock<34,1,268435714>::UpdateStatSnapshot();
          }
          *(_QWORD *)(v121 + 40) = 0;
          (*(void (__fastcall **)(struct ExternalLockValueBlockBase **))(v121 + 48))(v91);
        }
        else
        {
          if ( *(_BYTE *)(*(_QWORD *)(v121 + 32) + 5820LL) )
          {
            v124 = (struct ExternalLockValueBlockBase ***)(v121 + 16 * ((*(_DWORD *)(v121 + 1176) & 0x3F) + 9LL));
            *v91 = (struct ExternalLockValueBlockBase *)*v124;
            if ( !*v124 )
              v124[1] = v91;
            *v124 = v91;
            ++*(_QWORD *)(v121 + 1176);
            VirtualProtect(v91, 0x1000u, 1u, &flOldProtect);
          }
          else
          {
            *v91 = *(struct ExternalLockValueBlockBase **)(v121 + 128);
            if ( !*(_QWORD *)(v121 + 128) )
              *(_QWORD *)(v121 + 136) = v91;
            *(_QWORD *)(v121 + 128) = v91;
          }
          v125 = *(_QWORD *)(v121 + 1168) + 1LL;
          ++*(_QWORD *)(v121 + 8);
          v126 = *(SOS_ObjectStore **)(v121 + 32);
          if ( !*((_BYTE *)v126 + 5820) && v125 >= 0x20 )
          {
            PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v126, (struct SList *)v91);
            v128 = v121 + 8LL * PoolIdForObject;
            v129 = *(_QWORD *)(v121 + 128);
            v130 = *(_QWORD **)(v121 + 136);
            if ( v130 != (_QWORD *)(v121 + 128) && v130 )
            {
              *v130 = *(_QWORD *)(v128 + 1184);
              *(_QWORD *)(v128 + 1184) = v129;
            }
            *(_QWORD *)(v121 + 128) = 0;
            *(_QWORD *)(v121 + 136) = v121 + 128;
            v125 = 0;
            v131 = 1LL << PoolIdForObject;
            v132 = *(_QWORD *)(v121 + 1696);
            if ( (v131 & v132) == 0 )
              *(_QWORD *)(v121 + 1696) = v132 | v131;
          }
          *(_QWORD *)(v121 + 1168) = v125;
          if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v133 = rand();
            if ( v133 == 5 * (v133 / 5) )
              Spinlock<34,1,268435714>::UpdateStatSnapshot();
          }
          *(_QWORD *)(v121 + 40) = 0;
        }
      }
      else
      {
        v100[2] = (struct ExternalLockValueBlockBase **)(v101 + 1);
        *lpAddress = (struct ExternalLockValueBlockBase *)*v100;
        *v100 = lpAddress;
      }
      if ( v98 )
        LockManager::PutExternalLvb((LockManager *)theLockManager, v98);
      v89 = v196;
      if ( v184 )
        *(_DWORD *)(v93 + 800) |= 0x1000000u;
    }
    if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v102 = rand();
      if ( v102 == 5 * (v102 / 5) )
        Spinlock<183,7,257>::UpdateStatSnapshot();
    }
    *(_QWORD *)v89 = 0;
  }
  v62 = v192;
  if ( v192 )
  {
    v63 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v64 = *(_QWORD *)(v63 + 256);
    if ( !v64 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v64 = *(_QWORD *)(v63 + 256);
    }
    v220 = v64;
    v65 = *(_DWORD *)(v64 + 800);
    if ( (v65 & 0x1000000) == 0 || (*(_BYTE *)(v64 + 616) & 0x40) != 0 )
    {
      v182 = 0;
      v221 = 0;
    }
    else
    {
      v182 = 1;
      v221 = 1;
      *(_DWORD *)(v64 + 800) = v65 & 0xFEFFFFFF;
    }
    v66 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v67 = *(_QWORD *)(v66 + 256);
    if ( !v67 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v67 = *(_QWORD *)(v66 + 256);
    }
    v68 = *(unsigned int *)(*(_QWORD *)(v67 + 608) + 3688LL);
    if ( (*((_BYTE *)v192 + 91) & 4) != 0 )
      v69 = (struct ExternalLockValueBlockBase *)*((_QWORD *)v192 + 12);
    else
      v69 = 0;
    v70 = *((unsigned __int8 *)v192 + 119);
    if ( (unsigned int)v68 >= SOS_PublicGlobals::sm_maxCpuCount
      || (v71 = (struct SList **)(qword_103182380 + (v68 << 7)), v72 = (unsigned __int64)v71[2], v72 >= 0x3E8)
      || (*(_BYTE *)(v67 + 800) & 4) != 0
      || (_DWORD)v70 != *(unsigned __int16 *)(*(_QWORD *)(v67 + 992) + 160LL) )
    {
      v140 = *(_QWORD *)(theLockManager[5 * v70 + 3] + 2016);
      v141 = 0;
      v142 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)(v140 + 40) || _InterlockedCompareExchange64((volatile signed __int64 *)(v140 + 40), v142, 0) )
      {
        v143 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v144 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v144 && *(_QWORD *)(v144 + 272) == v144 )
            v143 = *(_QWORD *)(v144 + 256);
          if ( v143 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v212);
              v141 = (DirtyPageMgr *)v212.QuadPart;
            }
            else
            {
              v141 = MEMORY[0x7FFE0008];
            }
          }
        }
        v145 = v140 + 40;
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v145, v142);
        else
          Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v145, v143, v142);
        if ( v143 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v213);
            v146 = (DirtyPageMgr *)v213.QuadPart;
          }
          else
          {
            v146 = MEMORY[0x7FFE0008];
          }
          v147 = v146 - v141;
          if ( v146 < v141 )
            v147 = 0;
          *(_QWORD *)(v143 + 3192) += v147;
          v62 = v192;
        }
        else
        {
          v62 = v192;
        }
      }
      if ( *(_QWORD *)(v140 + 8) >= *(_QWORD *)v140 )
      {
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v157 = rand();
          if ( v157 == 5 * (v157 / 5) )
            Spinlock<34,1,268435714>::UpdateStatSnapshot();
        }
        *(_QWORD *)(v140 + 40) = 0;
        (*(void (__fastcall **)(struct SList *))(v140 + 48))(v62);
      }
      else
      {
        if ( *(_BYTE *)(*(_QWORD *)(v140 + 32) + 5820LL) )
        {
          v148 = (struct SList **)(v140 + 16 * ((*(_DWORD *)(v140 + 1176) & 0x3F) + 9LL));
          *(_QWORD *)v62 = *v148;
          if ( !*v148 )
            v148[1] = v62;
          *v148 = v62;
          ++*(_QWORD *)(v140 + 1176);
          VirtualProtect(v62, 0x1000u, 1u, &v205);
        }
        else
        {
          *(_QWORD *)v62 = *(_QWORD *)(v140 + 128);
          if ( !*(_QWORD *)(v140 + 128) )
            *(_QWORD *)(v140 + 136) = v62;
          *(_QWORD *)(v140 + 128) = v62;
        }
        v149 = *(_QWORD *)(v140 + 1168) + 1LL;
        ++*(_QWORD *)(v140 + 8);
        v150 = *(SOS_ObjectStore **)(v140 + 32);
        if ( !*((_BYTE *)v150 + 5820) && v149 >= 0x20 )
        {
          v151 = SOS_ObjectStore::GetPoolIdForObject(v150, v62);
          v152 = v140 + 8 * v151;
          v153 = *(_QWORD *)(v140 + 128);
          v154 = *(_QWORD **)(v140 + 136);
          if ( v154 != (_QWORD *)(v140 + 128) && v154 )
          {
            *v154 = *(_QWORD *)(v152 + 1184);
            *(_QWORD *)(v152 + 1184) = v153;
          }
          *(_QWORD *)(v140 + 128) = 0;
          *(_QWORD *)(v140 + 136) = v140 + 128;
          v149 = 0;
          v155 = *(_QWORD *)(v140 + 1696);
          if ( (v155 & (1LL << v151)) == 0 )
            *(_QWORD *)(v140 + 1696) = (1LL << v151) | v155;
        }
        *(_QWORD *)(v140 + 1168) = v149;
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v156 = rand();
          if ( v156 == 5 * (v156 / 5) )
            Spinlock<34,1,268435714>::UpdateStatSnapshot();
        }
        *(_QWORD *)(v140 + 40) = 0;
      }
    }
    else
    {
      v71[2] = (struct SList *)(v72 + 1);
      *(_QWORD *)v192 = *v71;
      *v71 = v192;
    }
    if ( v69 )
      LockManager::PutExternalLvb((LockManager *)theLockManager, v69);
    if ( v182 )
      *(_DWORD *)(v64 + 800) |= 0x1000000u;
  }
  v73 = v194;
  if ( v194 )
  {
    v74 = 0;
    do
    {
      v194 = *(struct SList **)v73;
      *(_QWORD *)v73 = 0;
      v75 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v76 = *(_QWORD *)(v75 + 256);
      if ( !v76 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v76 = *(_QWORD *)(v75 + 256);
      }
      v228 = v76;
      v77 = *(_DWORD *)(v76 + 800);
      if ( (v77 & 0x1000000) == 0 || (*(_BYTE *)(v76 + 616) & 0x40) != 0 )
      {
        v183 = 0;
        v229 = 0;
      }
      else
      {
        v183 = 1;
        v229 = 1;
        *(_DWORD *)(v76 + 800) = v77 & 0xFEFFFFFF;
      }
      v78 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v79 = *(_QWORD *)(v78 + 256);
      if ( !v79 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v79 = *(_QWORD *)(v78 + 256);
      }
      v80 = *(unsigned int *)(*(_QWORD *)(v79 + 608) + 3688LL);
      v81 = *((_BYTE *)v73 + 55);
      if ( (v81 & 0x10) != 0 || (v82 = *((_QWORD *)v73 + 4), v82 > 0x40) )
      {
        v158 = (unsigned __int64)v73 & 0xFFFFFFFFFFFFE000uLL;
        if ( ((unsigned __int64)v73 & 0xFFFFFFFFFFFFE000uLL) != 0
          && *(_WORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFE000uLL) + 4) == 512 )
        {
          v158 = *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFE000uLL) + 0x28);
        }
        v159 = *(_QWORD *)(v158 + 8);
        v160 = (unsigned __int64)v73 & -*(_QWORD *)(v159 + 16);
        if ( v160 && *(_WORD *)(((unsigned __int64)v73 & -*(_QWORD *)(v159 + 16)) + 4) == 512 )
          v160 = *(_QWORD *)(((unsigned __int64)v73 & -*(_QWORD *)(v159 + 16)) + 0x28);
        v161 = *(_QWORD *)(v160 + 8);
        v162 = 0;
        v163 = qword_10317F830;
        while ( *(v163 - 1) != v161 && *v163 != v161 && v163[1] != v161 )
        {
          ++v162;
          v163 += 5;
          if ( v162 >= 0x41 )
          {
            LODWORD(v82) = -1;
            goto LABEL_348;
          }
        }
        LODWORD(v82) = v162;
LABEL_348:
        *((_QWORD *)v73 + 4) = (unsigned int)v82;
        *((_BYTE *)v73 + 55) = v81 & 0xEF;
      }
      if ( (unsigned int)v80 >= SOS_PublicGlobals::sm_maxCpuCount
        || (v83 = qword_103182380 + (v80 << 7), v84 = *(_QWORD *)(v83 + 24), v84 >= 0x3E8)
        || (*(_BYTE *)(v79 + 800) & 4) != 0
        || (_DWORD)v82 != *(unsigned __int16 *)(*(_QWORD *)(v79 + 992) + 160LL) )
      {
        v164 = *(_QWORD *)(theLockManager[5 * (unsigned int)v82 + 3] + 2016) + 1832LL;
        v165 = 0;
        v166 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)(*(_QWORD *)(theLockManager[5 * (unsigned int)v82 + 3] + 2016) + 1872LL)
          || _InterlockedCompareExchange64(
               (volatile signed __int64 *)(*(_QWORD *)(theLockManager[5 * (unsigned int)v82 + 3] + 2016) + 1872LL),
               v166,
               0) )
        {
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v167 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset;
            if ( v167 && *(_QWORD *)(v167 + 272) == v167 )
              v74 = *(_QWORD *)(v167 + 256);
            if ( v74 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v214);
                v165 = (DirtyPageMgr *)v214.QuadPart;
              }
              else
              {
                v165 = MEMORY[0x7FFE0008];
              }
            }
          }
          v168 = v164 + 40;
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v168, v166);
          else
            Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v168, v74, v166);
          if ( v74 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v215);
              v169 = (DirtyPageMgr *)v215.QuadPart;
            }
            else
            {
              v169 = MEMORY[0x7FFE0008];
            }
            v170 = v169 - v165;
            if ( v169 < v165 )
              v170 = 0;
            *(_QWORD *)(v74 + 3192) += v170;
          }
          v74 = 0;
        }
        if ( *(_QWORD *)(v164 + 8) >= *(_QWORD *)v164 )
        {
          if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v180 = rand();
            if ( v180 == 5 * (v180 / 5) )
              Spinlock<34,1,268435714>::UpdateStatSnapshot();
          }
          *(_QWORD *)(v164 + 40) = 0;
          (*(void (__fastcall **)(struct SList *))(v164 + 48))(v73);
        }
        else
        {
          if ( *(_BYTE *)(*(_QWORD *)(v164 + 32) + 5820LL) )
          {
            v171 = (_QWORD *)(v164 + 16 * ((*(_DWORD *)(v164 + 1176) & 0x3F) + 9LL));
            *(_QWORD *)v73 = *v171;
            if ( !*v171 )
              v171[1] = v73;
            *v171 = v73;
            ++*(_QWORD *)(v164 + 1176);
            VirtualProtect(v73, 0x1000u, 1u, &v206);
          }
          else
          {
            *(_QWORD *)v73 = *(_QWORD *)(v164 + 128);
            if ( !*(_QWORD *)(v164 + 128) )
              *(_QWORD *)(v164 + 136) = v73;
            *(_QWORD *)(v164 + 128) = v73;
          }
          v172 = *(_QWORD *)(v164 + 1168) + 1LL;
          ++*(_QWORD *)(v164 + 8);
          v173 = *(SOS_ObjectStore **)(v164 + 32);
          if ( !*((_BYTE *)v173 + 5820) && v172 >= 0x20 )
          {
            v174 = SOS_ObjectStore::GetPoolIdForObject(v173, v73);
            v175 = v164 + 8 * v174;
            v176 = *(_QWORD *)(v164 + 128);
            v177 = *(_QWORD **)(v164 + 136);
            if ( v177 != (_QWORD *)(v164 + 128) && v177 )
            {
              *v177 = *(_QWORD *)(v175 + 1184);
              *(_QWORD *)(v175 + 1184) = v176;
            }
            *(_QWORD *)(v164 + 128) = 0;
            *(_QWORD *)(v164 + 136) = v164 + 128;
            v172 = 0;
            v178 = *(_QWORD *)(v164 + 1696);
            if ( (v178 & (1LL << v174)) == 0 )
              *(_QWORD *)(v164 + 1696) = (1LL << v174) | v178;
          }
          *(_QWORD *)(v164 + 1168) = v172;
          if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v179 = rand();
            if ( v179 == 5 * (v179 / 5) )
              Spinlock<34,1,268435714>::UpdateStatSnapshot();
          }
          *(_QWORD *)(v164 + 40) = 0;
        }
      }
      else
      {
        *(_QWORD *)(v83 + 24) = v84 + 1;
        *(_QWORD *)v73 = *(_QWORD *)(v83 + 8);
        *(_QWORD *)(v83 + 8) = v73;
      }
      if ( v183 )
        *(_DWORD *)(v76 + 800) |= 0x1000000u;
      v73 = v194;
    }
    while ( v194 );
  }
  if ( v189 )
  {
    ex_raise(12, 4, 19, 6);
    utassert_fail(1u, "FALSE", "lckmgr.cpp", 19545, "Shouldn't continue from exception");
  }
  try
  {
    v85 = v190;
    if ( v190 > 0 )
    {
      _mm_lfence();
      XDES::LogLockMigration(v218, v217, v216, v190, v193);
    }
  }
  catch ( SQLError v231 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v230, (const struct SQLError *)v231);
      if ( v193 != (struct LockMigrateLogInfo *)&v232 )
      {
        operator delete[](v193);
        v193 = (struct LockMigrateLogInfo *)&v232;
      }
      CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v230);
      ExceptionRethrow(CurrentException);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v230);
    }
    catch ( ShortStackException )
    {
    }
    v85 = v190;
  }
  v86 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v87 = *(struct Worker **)(v86 + 256);
  if ( !v87 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v87 = *(struct Worker **)(v86 + 256);
  }
  if ( *((_DWORD *)v87 + 139) )
    ExceptionPostCatchActions(v87);
  if ( v193 != (struct LockMigrateLogInfo *)&v232 )
    operator delete[](v193);
  return v85;
}

```

## disassembly

```asm
0x10044f2c0  mov     r11, rsp
0x10044f2c3  push    rbx
0x10044f2c4  push    rsi
0x10044f2c5  push    rdi
0x10044f2c6  push    r12
0x10044f2c8  push    r13
0x10044f2ca  push    r14
0x10044f2cc  push    r15
0x10044f2ce  sub     rsp, 4D0h
0x10044f2d5  mov     qword ptr [r11-378h], 0FFFFFFFFFFFFFFFEh
0x10044f2e0  mov     rax, cs:__security_cookie
0x10044f2e7  xor     rax, rsp
0x10044f2ea  mov     [rsp+508h+var_48], rax
0x10044f2f2  mov     [rsp+508h+var_3E8], r9
0x10044f2fa  mov     rbx, r8
0x10044f2fd  mov     [rsp+508h+var_460], rbx
0x10044f305  mov     r14, rdx
0x10044f308  mov     [rsp+508h+var_440], rdx
0x10044f310  mov     rax, [rsp+508h+arg_20]
0x10044f318  mov     [rsp+508h+var_3F0], rax
0x10044f320  mov     rax, [rsp+508h+arg_28]
0x10044f328  mov     [rsp+508h+var_3F8], rax
0x10044f330  xor     r15d, r15d
0x10044f333  mov     [rsp+508h+lpAddress], r15
0x10044f338  mov     r13d, r15d
0x10044f33b  mov     [rsp+508h+var_4B0], r15
0x10044f340  mov     [rsp+508h+var_4A0], r15
0x10044f345  mov     r12d, r15d
0x10044f348  mov     [rsp+508h+var_4C4], r15d
0x10044f34d  mov     [rsp+508h+var_498], r15d
0x10044f352  mov     esi, r15d
0x10044f355  mov     [rsp+508h+var_4D4], r15d
0x10044f35a  mov     [r11-348h], r15d
0x10044f361  mov     [r11-344h], r15w
0x10044f369  mov     [r11-340h], r15d
0x10044f370  mov     [r11-33Ch], r15w
0x10044f378  mov     [r11-338h], r15d
0x10044f37f  mov     [r11-334h], r15w
0x10044f387  mov     [r11-330h], r15d
0x10044f38e  mov     [r11-32Ch], r15w
0x10044f396  mov     [r11-328h], r15d
0x10044f39d  mov     [r11-324h], r15w
0x10044f3a5  mov     [r11-320h], r15d
0x10044f3ac  mov     [r11-31Ch], r15w
0x10044f3b4  mov     [r11-318h], r15d
0x10044f3bb  mov     [r11-314h], r15w
0x10044f3c3  mov     [r11-310h], r15d
0x10044f3ca  mov     [r11-30Ch], r15w
0x10044f3d2  mov     [r11-308h], r15d
0x10044f3d9  mov     [r11-304h], r15w
0x10044f3e1  mov     [r11-300h], r15d
0x10044f3e8  mov     [r11-2FCh], r15w
0x10044f3f0  mov     [r11-2F8h], r15d
0x10044f3f7  mov     [r11-2F4h], r15w
0x10044f3ff  mov     [r11-2F0h], r15d
0x10044f406  mov     [r11-2ECh], r15w
0x10044f40e  mov     [r11-2E8h], r15d
0x10044f415  mov     [r11-2E4h], r15w
0x10044f41d  mov     [r11-2E0h], r15d
0x10044f424  mov     [r11-2DCh], r15w
0x10044f42c  mov     [r11-2D8h], r15d
0x10044f433  mov     [r11-2D4h], r15w
0x10044f43b  mov     [r11-2D0h], r15d
0x10044f442  mov     [r11-2CCh], r15w
0x10044f44a  mov     [r11-2C8h], r15d
0x10044f451  mov     [r11-2C4h], r15w
0x10044f459  mov     [r11-2C0h], r15d
0x10044f460  mov     [r11-2BCh], r15w
0x10044f468  mov     [r11-2B8h], r15d
0x10044f46f  mov     [r11-2B4h], r15w
0x10044f477  mov     [r11-2B0h], r15d
0x10044f47e  mov     [r11-2ACh], r15w
0x10044f486  mov     [r11-2A8h], r15d
0x10044f48d  mov     [r11-2A4h], r15w
0x10044f495  mov     [r11-2A0h], r15d
0x10044f49c  mov     [r11-29Ch], r15w
0x10044f4a4  mov     [r11-298h], r15d
0x10044f4ab  mov     [r11-294h], r15w
0x10044f4b3  mov     [r11-290h], r15d
0x10044f4ba  mov     [r11-28Ch], r15w
0x10044f4c2  mov     [r11-288h], r15d
0x10044f4c9  mov     [r11-284h], r15w
0x10044f4d1  mov     [r11-280h], r15d
0x10044f4d8  mov     [r11-27Ch], r15w
0x10044f4e0  mov     [r11-278h], r15d
0x10044f4e7  mov     [r11-274h], r15w
0x10044f4ef  mov     [r11-270h], r15d
0x10044f4f6  mov     [r11-26Ch], r15w
0x10044f4fe  mov     [r11-268h], r15d
0x10044f505  mov     [r11-264h], r15w
0x10044f50d  mov     [r11-260h], r15d
0x10044f514  mov     [r11-25Ch], r15w
0x10044f51c  mov     [r11-258h], r15d
0x10044f523  mov     [r11-254h], r15w
0x10044f52b  mov     [r11-250h], r15d
0x10044f532  mov     [r11-24Ch], r15w
0x10044f53a  mov     [rsp+508h+var_4C0], r15d
0x10044f53f  mov     [rsp+508h+var_4C8], 20h ; ' '
0x10044f547  test    cs:byte_10317AC16, 40h
0x10044f54e  jnz     loc_10188DFE2
0x10044f554  mov     r8, gs:58h
0x10044f55d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044f564  mov     ecx, [rax]
0x10044f566  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044f56d  mov     edx, [rax]
0x10044f56f  add     rdx, [r8+rcx*8]
0x10044f573  mov     rax, [rdx]
0x10044f576  test    rax, rax
0x10044f579  jz      short loc_10044F58B
0x10044f57b  mov     rax, [rax+38h]
0x10044f57f  mov     rcx, [rax]
0x10044f582  test    rcx, rcx
0x10044f585  jnz     loc_10188DFCF
0x10044f58b  movzx   edx, byte ptr [rbx+0Eh]
0x10044f58f  xor     edx, [rbx]
0x10044f591  shl     edx, 7
0x10044f594  movzx   eax, word ptr [rbx+0Ch]
0x10044f598  shl     eax, 4
0x10044f59b  xor     edx, eax
0x10044f59d  xor     edx, [rbx]
0x10044f59f  xor     edx, [rbx+8]
0x10044f5a2  xor     edx, [rbx+4]
0x10044f5a5  mov     eax, edx
0x10044f5a7  shr     eax, 0Ah
0x10044f5aa  xor     edx, eax
0x10044f5ac  mov     r9d, cs:dword_10317F808
0x10044f5b3  dec     r9d
0x10044f5b6  mov     r10d, r9d
0x10044f5b9  and     r10d, edx
0x10044f5bc  shl     r10, 4
0x10044f5c0  add     r10, cs:?theLockManager@@3VLockManager@@A; LockManager theLockManager
0x10044f5c7  mov     [rsp+508h+var_490], r10
0x10044f5cc  movzx   edx, byte ptr [r14+0Eh]
0x10044f5d1  xor     edx, [r14]
0x10044f5d4  shl     edx, 7
0x10044f5d7  movzx   eax, word ptr [r14+0Ch]
0x10044f5dc  shl     eax, 4
0x10044f5df  xor     edx, eax
0x10044f5e1  xor     edx, [r14+8]
0x10044f5e5  xor     edx, [r14+4]
0x10044f5e9  xor     edx, [r14]
0x10044f5ec  mov     eax, edx
0x10044f5ee  shr     eax, 0Ah
0x10044f5f1  xor     edx, eax
0x10044f5f3  and     edx, r9d
0x10044f5f6  shl     rdx, 4
0x10044f5fa  add     rdx, cs:?theLockManager@@3VLockManager@@A; LockManager theLockManager
0x10044f601  mov     [rsp+508h+var_438], rdx
0x10044f609  mov     rcx, r10
0x10044f60c  cmp     rdx, r10
0x10044f60f  cmovbe  rcx, rdx
0x10044f613  mov     [rsp+508h+var_470], rcx
0x10044f61b  mov     rax, rdx
0x10044f61e  cmovbe  rax, r10
0x10044f622  mov     rbx, r15
0x10044f625  cmp     rcx, rax
0x10044f628  cmovnz  rbx, rax
0x10044f62c  mov     [rsp+508h+var_468], rbx
0x10044f634  lea     r14, [rsp+508h+var_348]
0x10044f63c  mov     [rsp+508h+var_4A8], r14
0x10044f641  test    r13, r13
0x10044f644  jnz     loc_10044F7A6
0x10044f64a  mov     rdx, gs:58h
0x10044f653  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044f65a  mov     ecx, [rax]
0x10044f65c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044f663  mov     edi, [rax]
0x10044f665  add     rdi, [rdx+rcx*8]
0x10044f669  mov     rbx, [rdi+100h]
0x10044f670  test    rbx, rbx
0x10044f673  jz      loc_10188E023
0x10044f679  mov     [rsp+508h+var_3C8], rbx
0x10044f681  mov     eax, [rbx+320h]
0x10044f687  bt      eax, 18h
0x10044f68b  jb      loc_10188E038
0x10044f691  xor     sil, sil
0x10044f694  mov     [rsp+508h+var_3C0], sil
0x10044f69c  mov     rdx, gs:58h
0x10044f6a5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044f6ac  mov     ecx, [rax]
0x10044f6ae  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044f6b5  mov     edi, [rax]
0x10044f6b7  add     rdi, [rdx+rcx*8]
0x10044f6bb  mov     r8, [rdi+100h]
0x10044f6c2  test    r8, r8
0x10044f6c5  jz      loc_10188E058
0x10044f6cb  mov     rax, [r8+260h]
0x10044f6d2  mov     ecx, [rax+0E68h]
0x10044f6d8  mov     edx, ecx
0x10044f6da  shl     rdx, 7
0x10044f6de  add     rdx, cs:qword_103182380
0x10044f6e5  mov     rax, cs:__imp_?sm_maxCpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_maxCpuCount
0x10044f6ec  cmp     ecx, [rax]
0x10044f6ee  jnb     loc_100489F91
0x10044f6f4  cmp     qword ptr [rdx], 0
0x10044f6f8  jz      loc_100489F91
0x10044f6fe  test    byte ptr [r8+320h], 4
0x10044f706  jnz     loc_100489F91
0x10044f70c  lfence
0x10044f70f  mov     r13, [rdx]
0x10044f712  mov     rax, [r13+0]
0x10044f716  mov     [rdx], rax
0x10044f719  xor     eax, eax
0x10044f71b  mov     [r13+0], rax
0x10044f71f  dec     qword ptr [rdx+10h]
0x10044f723  mov     [r13+8], rax
0x10044f727  mov     [r13+10h], rax
0x10044f72b  mov     [r13+18h], rax
0x10044f72f  mov     [r13+20h], rax
0x10044f733  mov     [r13+28h], rax
0x10044f737  mov     [r13+30h], rax
0x10044f73b  mov     [r13+38h], rax
0x10044f73f  mov     [r13+40h], rax
0x10044f743  mov     [r13+48h], rax
0x10044f747  mov     [r13+50h], rax
0x10044f74b  mov     [r13+58h], ax
0x10044f750  mov     [r13+5Bh], al
0x10044f754  jmp     short loc_10044F757
0x10044f757  mov     [rsp+508h+var_4B0], r13
0x10044f75c  test    sil, sil
0x10044f75f  jnz     loc_10188E06D
0x10044f765  test    r13, r13
0x10044f768  jz      loc_10044FA64
0x10044f76e  mov     byte ptr [r13+5Ah], 0
0x10044f773  mov     rbx, [rsp+508h+var_460]
0x10044f77b  movsd   xmm0, qword ptr [rbx]
0x10044f77f  movsd   qword ptr [r13+68h], xmm0
0x10044f785  mov     eax, [rbx+8]
0x10044f788  mov     [r13+70h], eax
0x10044f78c  movzx   eax, word ptr [rbx+0Ch]
0x10044f790  mov     [r13+74h], ax
0x10044f795  movzx   eax, byte ptr [rbx+0Eh]
0x10044f799  mov     [r13+76h], al
0x10044f79d  mov     r14, [rsp+508h+var_4A8]
0x10044f7a2  mov     esi, [rsp+508h+var_4D4]
0x10044f7a6  cmp     esi, [rsp+508h+var_4C8]
0x10044f7aa  jge     loc_10044F8F9
0x10044f7b0  nop     word ptr [rax+rax]
0x10044f7b5  nop     word ptr [rax+rax+00000000h]
0x10044f7c0  mov     rdx, gs:58h
0x10044f7c9  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044f7d0  mov     ecx, [rax]
0x10044f7d2  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044f7d9  mov     edi, [rax]
0x10044f7db  add     rdi, [rdx+rcx*8]
0x10044f7df  mov     rbx, [rdi+100h]
0x10044f7e6  test    rbx, rbx
0x10044f7e9  jz      loc_10188E07D
0x10044f7ef  mov     [rsp+508h+var_3B8], rbx
0x10044f7f7  mov     eax, [rbx+320h]
0x10044f7fd  bt      eax, 18h
0x10044f801  jb      loc_10188E092
0x10044f807  xor     sil, sil
0x10044f80a  mov     [rsp+508h+var_3B0], sil
0x10044f812  mov     rdx, gs:58h
0x10044f81b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044f822  mov     ecx, [rax]
0x10044f824  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044f82b  mov     edi, [rax]
0x10044f82d  add     rdi, [rdx+rcx*8]
0x10044f831  mov     r8, [rdi+100h]
0x10044f838  test    r8, r8
0x10044f83b  jz      loc_10188E0B2
0x10044f841  mov     rax, [r8+260h]
0x10044f848  mov     ecx, [rax+0E68h]
0x10044f84e  mov     edx, ecx
0x10044f850  shl     rdx, 7
0x10044f854  add     rdx, cs:qword_103182380
0x10044f85b  mov     rax, cs:__imp_?sm_maxCpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_maxCpuCount
0x10044f862  cmp     ecx, [rax]
0x10044f864  jnb     loc_100489FA9
0x10044f86a  cmp     qword ptr [rdx+8], 0
0x10044f86f  jz      loc_100489FA9
0x10044f875  test    byte ptr [r8+320h], 4
0x10044f87d  jnz     loc_100489FA9
0x10044f883  lfence
0x10044f886  mov     rcx, [rdx+8]
0x10044f88a  mov     rax, [rcx]
0x10044f88d  mov     [rdx+8], rax
0x10044f891  xor     r8d, r8d
0x10044f894  mov     [rcx], r8
0x10044f897  dec     qword ptr [rdx+18h]
0x10044f89b  mov     rax, [rcx+20h]
0x10044f89f  mov     [rcx], r8
0x10044f8a2  mov     [rcx+8], r8
0x10044f8a6  mov     [rcx+10h], r8
0x10044f8aa  mov     [rcx+18h], r8
0x10044f8ae  mov     [rcx+28h], r8
0x10044f8b2  mov     [rcx+30h], r8
0x10044f8b6  mov     [rcx+38h], r8
0x10044f8ba  mov     [rcx+20h], rax
0x10044f8be  jmp     short loc_10044F8C1
0x10044f8c1  test    sil, sil
0x10044f8c4  jnz     loc_10188E0C7
0x10044f8ca  test    rcx, rcx
0x10044f8cd  jz      loc_10044FA64
0x10044f8d3  mov     rax, [rsp+508h+var_4A0]
0x10044f8d8  mov     [rcx], rax
0x10044f8db  mov     [rsp+508h+var_4A0], rcx
0x10044f8e0  mov     esi, [rsp+508h+var_4D4]
  ... truncated ...
```
