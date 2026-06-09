# lck_MigrateLocks(XactLockInfo const *,LockRes const &,LockRes const &,LockRes const &,XDES *,PageId const &,HoBtId const &)

- ea: `0x100451de0`
- end: `0x1004520fd`
- name: `?lck_MigrateLocks@@YAHPEBVXactLockInfo@@AEBVLockRes@@11PEAVXDES@@AEBVPageId@@AEBVHoBtId@@@Z`
- size: `797`
- prototype: `int(const struct XactLockInfo *, const struct LockRes *, const struct LockRes *, const struct LockRes *, struct XDES *, const struct PageId *, const struct HoBtId *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x10044ef50`

## callees

- `0x100401490`
- `0x100403780`
- `0x100403940`
- `0x10040df90`
- `0x10040eb30`
- `0x1004162f0`
- `0x10041f420`
- `0x10042dce0`
- `0x10042dd10`
- `0x10044eec0`
- `0x100451de0`
- `0x10047b3f0`
- `0x1004ab7a0`
- `0x1004baa60`
- `0x1005a5d10`
- `0x1005b9170`
- `0x1005b93a0`
- `0x1005d8b90`
- `0x1006c6280`
- `0x1006c6560`
- `0x101760f70`
- `0x1018797e0`
- `0x1023af450`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x10188d63c`
- `KERNEL32!VirtualProtect` at `0x10188d9c4`
- `KERNEL32!VirtualProtect` at `0x10188dddb`
- `KERNEL32!VirtualProtect` at `0x10188d63c`
- `KERNEL32!VirtualProtect` at `0x10188d9c4`
- `KERNEL32!VirtualProtect` at `0x10188dddb`
- `KERNEL32!QueryPerformanceCounter` at `0x10188d554`
- `KERNEL32!QueryPerformanceCounter` at `0x10188d5ac`
- `KERNEL32!QueryPerformanceCounter` at `0x10188d8e2`
- `KERNEL32!QueryPerformanceCounter` at `0x10188d936`
- `KERNEL32!QueryPerformanceCounter` at `0x10188dcfb`
- `KERNEL32!QueryPerformanceCounter` at `0x10188dd4f`
- `KERNEL32!QueryPerformanceCounter` at `0x10188d554`
- `KERNEL32!QueryPerformanceCounter` at `0x10188d5ac`
- `KERNEL32!QueryPerformanceCounter` at `0x10188d8e2`
- `KERNEL32!QueryPerformanceCounter` at `0x10188d936`
- `KERNEL32!QueryPerformanceCounter` at `0x10188dcfb`
- `KERNEL32!QueryPerformanceCounter` at `0x10188dd4f`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1005a56d7`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1005a56fa`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1005a571e`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10188d0d5`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10188d123`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10188d184`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10188d452`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10188d6dc`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10188d796`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10188da63`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10188db03`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10188de6d`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10188df05`
- `sqldk!?sm_maxCpuCount@SOS_PublicGlobals@@2KA` at `0x1005a525e`
- `sqldk!?sm_maxCpuCount@SOS_PublicGlobals@@2KA` at `0x1005a53cb`
- `sqldk!?sm_maxCpuCount@SOS_PublicGlobals@@2KA` at `0x1005a58d0`
- `sqldk!?sm_maxCpuCount@SOS_PublicGlobals@@2KA` at `0x1005a5a1f`
- `sqldk!?sm_maxCpuCount@SOS_PublicGlobals@@2KA` at `0x10188d3bd`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10188d4ee`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10188d87c`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10188dc98`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10188d565`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10188d8f3`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10188dd0c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10188d53c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10188d594`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10188d8ca`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10188d91e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10188dce3`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10188dd37`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10188dfb5`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10188dfb5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10188df95`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10188df95`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10188df6a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10188df6a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10188cdb3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10188cdb3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1005a57bd`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1005a57bd`
- `sqldk!SystemThread_TlsIndex` at `0x1005a5079`
- `sqldk!SystemThread_TlsIndex` at `0x1005a51cc`
- `sqldk!SystemThread_TlsIndex` at `0x1005a521e`
- `sqldk!SystemThread_TlsIndex` at `0x1005a5339`
- `sqldk!SystemThread_TlsIndex` at `0x1005a538b`
- `sqldk!SystemThread_TlsIndex` at `0x1005a574e`
- `sqldk!SystemThread_TlsIndex` at `0x1005a5833`
- `sqldk!SystemThread_TlsIndex` at `0x1005a5888`
- `sqldk!SystemThread_TlsIndex` at `0x1005a5979`
- `sqldk!SystemThread_TlsIndex` at `0x1005a59ce`
- `sqldk!SystemThread_TlsIndex` at `0x1005a5ae8`
- `sqldk!SystemThread_TlsIndex` at `0x10188d2ea`
- `sqldk!SystemThread_TlsIndex` at `0x10188d366`
- `sqldk!SystemThread_TlsIndex` at `0x10188d50e`
- `sqldk!SystemThread_TlsIndex` at `0x10188d89c`
- `sqldk!SystemThread_TlsIndex` at `0x10188dcb5`
- `sqldk!SystemThread_TlsOffset` at `0x1005a5082`
- `sqldk!SystemThread_TlsOffset` at `0x1005a51d5`
- `sqldk!SystemThread_TlsOffset` at `0x1005a5227`
- `sqldk!SystemThread_TlsOffset` at `0x1005a5342`
- `sqldk!SystemThread_TlsOffset` at `0x1005a5394`
- `sqldk!SystemThread_TlsOffset` at `0x1005a5757`
- `sqldk!SystemThread_TlsOffset` at `0x1005a583c`
- `sqldk!SystemThread_TlsOffset` at `0x1005a5891`
- `sqldk!SystemThread_TlsOffset` at `0x1005a5982`
- `sqldk!SystemThread_TlsOffset` at `0x1005a59d7`
- `sqldk!SystemThread_TlsOffset` at `0x1005a5af1`
- `sqldk!SystemThread_TlsOffset` at `0x10188d2f3`
- `sqldk!SystemThread_TlsOffset` at `0x10188d36f`
- `sqldk!SystemThread_TlsOffset` at `0x10188d517`
- `sqldk!SystemThread_TlsOffset` at `0x10188d8a5`
- `sqldk!SystemThread_TlsOffset` at `0x10188dcbe`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1005a5770`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188ce05`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188ce3a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188ce77`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188ceac`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188d30e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188d38a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188d7dc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188d81d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188db72`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188dbb3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188dfa2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1005a5770`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188ce05`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188ce3a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188ce77`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188ceac`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188d30e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188d38a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188d7dc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188d81d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188db72`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188dbb3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10188dfa2`
- `sqldk!??_V@YAXPEAX@Z` at `0x10188ceea`
- `sqldk!??_V@YAXPEAX@Z` at `0x10188dfc2`
- `sqldk!??_V@YAXPEAX@Z` at `0x10188ceea`
- `sqldk!??_V@YAXPEAX@Z` at `0x10188dfc2`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188d0e1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188d12f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188d190`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188d1c8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188d1fa`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188d22a`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188d45e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188d6e8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188d7a2`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188da6f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188db0f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188de79`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188df11`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188d0e1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188d12f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188d190`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188d1c8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188d1fa`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188d22a`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188d45e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188d6e8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188d7a2`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188da6f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188db0f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188de79`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10188df11`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall lck_MigrateLocks(
        const struct XactLockInfo *a1,
        const struct LockRes *a2,
        const struct LockRes *a3,
        const struct LockRes *a4,
        struct XDES *a5,
        const struct PageId *a6,
        const struct HoBtId *a7)
{
  const struct LockRes *v7; // r12
  struct Lock *LockBlocks; // r14
  int v10; // r15d
  int v11; // esi
  unsigned int v12; // edx
  LockHashSlot *v13; // r13
  __int64 *v14; // rbx
  __int64 v16; // rdx
  struct CSessionTraceFlags *v17; // rcx
  LockHashSlot *v18; // r10
  LockHashSlot *v19; // rax
  LockHashSlot *v20; // r8
  LockHashSlot *v21; // rcx
  LockHashSlot *v22; // rdx
  LockHashSlot *v23; // rax
  LockHashSlot *v24; // rax
  LockHashSlot *v25; // rbx
  LockHashSlot *v26; // rbx
  struct LockMigrateLogInfo *v27; // rdi
  __int64 v28; // r13
  __int64 v29; // rdi
  __int64 v30; // rbx
  int v31; // eax
  char v32; // si
  __int64 v33; // rdi
  __int64 v34; // r8
  unsigned __int64 v35; // rdx
  __int64 v36; // rdi
  __int64 v37; // rbx
  int v38; // eax
  char v39; // si
  __int64 v40; // rdi
  __int64 v41; // r8
  unsigned __int64 v42; // rdx
  struct LockOwner *LockOwnerBlocks; // rcx
  __int64 v44; // rax
  LockHashSlot *v45; // r15
  struct Lock *v46; // rbx
  struct Lock *v47; // rdx
  struct Lock *v48; // r9
  __int64 v49; // r10
  __int64 v50; // r10
  __int64 v51; // r8
  int i; // eax
  int v53; // eax
  __int64 v54; // rdx
  __int64 v55; // r15
  char v56; // cl
  int v57; // r14d
  LockHashSlot *v58; // rbx
  LockHashSlot *v59; // rbx
  __int64 v60; // rbx
  __int64 v61; // rdi
  __int64 v62; // rcx
  struct IMemObj *v63; // rcx
  unsigned __int64 v64; // rax
  struct LockMigrateLogInfo *v65; // rax
  struct SList *v66; // rsi
  __int64 v67; // rbx
  __int64 v68; // r14
  int v69; // eax
  __int64 v70; // rbx
  __int64 v71; // rdx
  __int64 v72; // rcx
  struct ExternalLockValueBlockBase *v73; // r12
  __int64 v74; // r10
  struct SList **v75; // r8
  unsigned __int64 v76; // r9
  __int64 v77; // r14
  struct SList *v78; // rsi
  __int64 v79; // rbx
  __int64 v80; // r13
  int v81; // eax
  __int64 v82; // rbx
  __int64 v83; // r9
  __int64 v84; // r10
  char v85; // r8
  unsigned __int64 v86; // rdx
  __int64 v87; // r8
  unsigned __int64 v88; // r10
  __int64 v89; // rbx
  struct Worker *v90; // rcx
  __int64 v91; // rdi
  __int64 v92; // rsi
  __int64 FirstRealOwner; // rbx
  __int64 v94; // rcx
  __int64 v95; // rax
  char v96; // cl
  __int64 v97; // rdx
  __int64 v98; // rax
  int v99; // edx
  __int16 v100; // r8
  int v101; // ecx
  __int64 j; // rax
  _DWORD *v103; // r12
  XactLockInfo *v104; // rdi
  char v105; // cl
  XactLockInfo *v106; // rsi
  XactLockInfo *XactLockInfo; // rax
  unsigned int v108; // r8d
  XactLockInfo *v109; // r14
  __int64 v110; // rax
  LockHashSlot *v111; // rbx
  __int64 *v112; // rcx
  const wchar_t *v113; // rax
  unsigned __int64 v114; // rcx
  __int64 v115; // rax
  __int64 v116; // rax
  char v117; // cl
  __int64 v118; // rax
  char v119; // cl
  __int64 v120; // rax
  char v121; // cl
  __int64 v122; // rax
  int v123; // r8d
  LockHashSlot *v124; // rbx
  int v125; // r8d
  LockHashSlot *v126; // rbx
  int v127; // r8d
  int v128; // r8d
  int v129; // r8d
  int v130; // r8d
  struct ExternalLockValueBlockBase **v131; // rsi
  __int64 v132; // rbx
  __int64 v133; // r14
  int v134; // eax
  __int64 v135; // rbx
  __int64 v136; // rdx
  __int64 v137; // rcx
  struct ExternalLockValueBlockBase *v138; // r12
  __int64 v139; // r10
  struct ExternalLockValueBlockBase ***v140; // r8
  unsigned __int64 v141; // r9
  int v142; // r8d
  __int64 v143; // rdi
  DirtyPageMgr *QuadPart; // rbx
  signed __int64 UniqueThread_low; // r13
  __int64 v146; // rsi
  __int64 v147; // r8
  __int64 v148; // rcx
  DirtyPageMgr *v149; // rax
  struct ExternalLockValueBlockBase ***v150; // rcx
  unsigned __int64 v151; // rax
  SOS_ObjectStore *v152; // rcx
  __int64 PoolIdForObject; // r10
  __int64 v154; // r9
  __int64 v155; // rax
  _QWORD *v156; // r8
  __int64 v157; // rcx
  int v158; // r8d
  int v159; // r8d
  __int64 v160; // rdi
  DirtyPageMgr *v161; // rbx
  signed __int64 v162; // r13
  __int64 v163; // rsi
  __int64 v164; // r8
  __int64 v165; // rcx
  DirtyPageMgr *v166; // rax
  signed __int64 v167; // rax
  struct SList **v168; // rcx
  unsigned __int64 v169; // r8
  SOS_ObjectStore *v170; // rcx
  unsigned int v171; // eax
  __int64 v172; // r9
  __int64 v173; // r10
  _QWORD *v174; // r8
  __int64 v175; // rax
  __int64 v176; // rcx
  int v177; // r8d
  int v178; // r8d
  unsigned __int64 v179; // rax
  __int64 v180; // rax
  unsigned __int64 v181; // rdx
  __int64 v182; // rdx
  unsigned int v183; // ecx
  __int64 *v184; // rax
  __int64 v185; // rdi
  DirtyPageMgr *v186; // rbx
  signed __int64 v187; // r12
  __int64 v188; // r8
  __int64 v189; // rcx
  DirtyPageMgr *v190; // rax
  signed __int64 v191; // rax
  _QWORD *v192; // rcx
  unsigned __int64 v193; // rdx
  SOS_ObjectStore *v194; // rcx
  unsigned int v195; // eax
  __int64 v196; // r9
  __int64 v197; // r10
  _QWORD *v198; // r8
  __int64 v199; // rax
  __int64 v200; // rcx
  int v201; // r8d
  int v202; // r8d
  const struct SQLError *CurrentException; // rax
  char v204; // [rsp+30h] [rbp-4F8h]
  char v205; // [rsp+30h] [rbp-4F8h]
  char v206; // [rsp+30h] [rbp-4F8h]
  unsigned int v207; // [rsp+34h] [rbp-4F4h]
  int v208; // [rsp+38h] [rbp-4F0h]
  int v209; // [rsp+3Ch] [rbp-4ECh]
  struct LockMigrateLogInfo *v210; // [rsp+40h] [rbp-4E8h]
  int v211; // [rsp+48h] [rbp-4E0h]
  int v212; // [rsp+4Ch] [rbp-4DCh]
  struct SList *v213; // [rsp+50h] [rbp-4D8h]
  struct LockMigrateLogInfo *v214; // [rsp+58h] [rbp-4D0h]
  int v215; // [rsp+60h] [rbp-4C8h]
  int v216; // [rsp+64h] [rbp-4C4h]
  struct ExternalLockValueBlockBase **lpAddress; // [rsp+68h] [rbp-4C0h]
  struct SList *v218; // [rsp+70h] [rbp-4B8h] BYREF
  int v219; // [rsp+78h] [rbp-4B0h]
  int v220; // [rsp+7Ch] [rbp-4ACh]
  LockHashSlot *v221; // [rsp+80h] [rbp-4A8h]
  LockHashSlot *v222; // [rsp+88h] [rbp-4A0h]
  int v223; // [rsp+90h] [rbp-498h] BYREF
  const struct LockRes *v224; // [rsp+98h] [rbp-490h]
  LockHashSlot *v225; // [rsp+A0h] [rbp-488h]
  LockHashSlot *v226; // [rsp+A8h] [rbp-480h]
  struct LockMigrateLogInfo *v227; // [rsp+B0h] [rbp-478h]
  struct LockRes *v228; // [rsp+B8h] [rbp-470h]
  struct Lock *v229; // [rsp+C0h] [rbp-468h]
  __int64 v230; // [rsp+C8h] [rbp-460h]
  int v231; // [rsp+D0h] [rbp-458h]
  DWORD flOldProtect; // [rsp+D4h] [rbp-454h] BYREF
  DWORD v233; // [rsp+D8h] [rbp-450h] BYREF
  LockHashSlot *v234; // [rsp+E0h] [rbp-448h]
  struct LockRes *v235; // [rsp+E8h] [rbp-440h]
  LockHashSlot *v236; // [rsp+F0h] [rbp-438h]
  struct Lock *v237; // [rsp+F8h] [rbp-430h]
  LARGE_INTEGER PerformanceCount; // [rsp+100h] [rbp-428h] BYREF
  LARGE_INTEGER v239; // [rsp+108h] [rbp-420h] BYREF
  LARGE_INTEGER v240; // [rsp+110h] [rbp-418h] BYREF
  LARGE_INTEGER v241; // [rsp+118h] [rbp-410h] BYREF
  LARGE_INTEGER v242; // [rsp+120h] [rbp-408h] BYREF
  LARGE_INTEGER v243; // [rsp+128h] [rbp-400h] BYREF
  struct HoBtId *v244; // [rsp+130h] [rbp-3F8h]
  struct PageId *v245; // [rsp+138h] [rbp-3F0h]
  struct XDES *v246; // [rsp+140h] [rbp-3E8h]
  DWORD v247; // [rsp+148h] [rbp-3E0h] BYREF
  __int64 v248; // [rsp+150h] [rbp-3D8h]
  char v249; // [rsp+158h] [rbp-3D0h]
  __int64 v250; // [rsp+160h] [rbp-3C8h]
  char v251; // [rsp+168h] [rbp-3C0h]
  __int64 v252; // [rsp+170h] [rbp-3B8h]
  char v253; // [rsp+178h] [rbp-3B0h]
  __int64 v254; // [rsp+180h] [rbp-3A8h]
  char v255; // [rsp+188h] [rbp-3A0h]
  __int64 v256; // [rsp+190h] [rbp-398h]
  char v257; // [rsp+198h] [rbp-390h]
  _QWORD v258[4]; // [rsp+1A0h] [rbp-388h] BYREF
  _BYTE v259[32]; // [rsp+1C0h] [rbp-368h] BYREF
  int v260; // [rsp+1E0h] [rbp-348h] BYREF
  __int16 v261; // [rsp+1E4h] [rbp-344h]
  int v262; // [rsp+1E8h] [rbp-340h]
  __int16 v263; // [rsp+1ECh] [rbp-33Ch]
  int v264; // [rsp+1F0h] [rbp-338h]
  __int16 v265; // [rsp+1F4h] [rbp-334h]
  int v266; // [rsp+1F8h] [rbp-330h]
  __int16 v267; // [rsp+1FCh] [rbp-32Ch]
  int v268; // [rsp+200h] [rbp-328h]
  __int16 v269; // [rsp+204h] [rbp-324h]
  int v270; // [rsp+208h] [rbp-320h]
  __int16 v271; // [rsp+20Ch] [rbp-31Ch]
  int v272; // [rsp+210h] [rbp-318h]
  __int16 v273; // [rsp+214h] [rbp-314h]
  int v274; // [rsp+218h] [rbp-310h]
  __int16 v275; // [rsp+21Ch] [rbp-30Ch]
  int v276; // [rsp+220h] [rbp-308h]
  __int16 v277; // [rsp+224h] [rbp-304h]
  int v278; // [rsp+228h] [rbp-300h]
  __int16 v279; // [rsp+22Ch] [rbp-2FCh]
  int v280; // [rsp+230h] [rbp-2F8h]
  __int16 v281; // [rsp+234h] [rbp-2F4h]
  int v282; // [rsp+238h] [rbp-2F0h]
  __int16 v283; // [rsp+23Ch] [rbp-2ECh]
  int v284; // [rsp+240h] [rbp-2E8h]
  __int16 v285; // [rsp+244h] [rbp-2E4h]
  int v286; // [rsp+248h] [rbp-2E0h]
  __int16 v287; // [rsp+24Ch] [rbp-2DCh]
  int v288; // [rsp+250h] [rbp-2D8h]
  __int16 v289; // [rsp+254h] [rbp-2D4h]
  int v290; // [rsp+258h] [rbp-2D0h]
  __int16 v291; // [rsp+25Ch] [rbp-2CCh]
  int v292; // [rsp+260h] [rbp-2C8h]
  __int16 v293; // [rsp+264h] [rbp-2C4h]
  int v294; // [rsp+268h] [rbp-2C0h]
  __int16 v295; // [rsp+26Ch] [rbp-2BCh]
  int v296; // [rsp+270h] [rbp-2B8h]
  __int16 v297; // [rsp+274h] [rbp-2B4h]
  int v298; // [rsp+278h] [rbp-2B0h]
  __int16 v299; // [rsp+27Ch] [rbp-2ACh]
  int v300; // [rsp+280h] [rbp-2A8h]
  __int16 v301; // [rsp+284h] [rbp-2A4h]
  int v302; // [rsp+288h] [rbp-2A0h]
  __int16 v303; // [rsp+28Ch] [rbp-29Ch]
  int v304; // [rsp+290h] [rbp-298h]
  __int16 v305; // [rsp+294h] [rbp-294h]
  int v306; // [rsp+298h] [rbp-290h]
  __int16 v307; // [rsp+29Ch] [rbp-28Ch]
  int v308; // [rsp+2A0h] [rbp-288h]
  __int16 v309; // [rsp+2A4h] [rbp-284h]
  int v310; // [rsp+2A8h] [rbp-280h]
  __int16 v311; // [rsp+2ACh] [rbp-27Ch]
  int v312; // [rsp+2B0h] [rbp-278h]
  __int16 v313; // [rsp+2B4h] [rbp-274h]
  int v314; // [rsp+2B8h] [rbp-270h]
  __int16 v315; // [rsp+2BCh] [rbp-26Ch]
  int v316; // [rsp+2C0h] [rbp-268h]
  __int16 v317; // [rsp+2C4h] [rbp-264h]
  int v318; // [rsp+2C8h] [rbp-260h]
  __int16 v319; // [rsp+2CCh] [rbp-25Ch]
  int v320; // [rsp+2D0h] [rbp-258h]
  __int16 v321; // [rsp+2D4h] [rbp-254h]
  int v322; // [rsp+2D8h] [rbp-250h]
  __int16 v323; // [rsp+2DCh] [rbp-24Ch]
  wchar_t v324[256]; // [rsp+2E0h] [rbp-248h] BYREF

  v258[2] = -2;
  v7 = a4;
  v224 = a4;
  v228 = a3;
  v235 = a2;
  v246 = a5;
  v245 = a6;
  v244 = a7;
  lpAddress = 0;
  LockBlocks = 0;
  v213 = 0;
  v218 = 0;
  v209 = 0;
  v212 = 0;
  v220 = 0;
  v10 = 0;
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
  v296 = 0;
  v297 = 0;
  v298 = 0;
  v299 = 0;
  v300 = 0;
  v301 = 0;
  v302 = 0;
  v303 = 0;
  v304 = 0;
  v305 = 0;
  v306 = 0;
  v307 = 0;
  v308 = 0;
  v309 = 0;
  v310 = 0;
  v311 = 0;
  v312 = 0;
  v313 = 0;
  v314 = 0;
  v315 = 0;
  v316 = 0;
  v317 = 0;
  v318 = 0;
  v319 = 0;
  v320 = 0;
  v321 = 0;
  v322 = 0;
  v323 = 0;
  v216 = 0;
  v11 = 32;
  v211 = 32;
  v12 = *((_DWORD *)a2 + 1)
      ^ *((_DWORD *)a2 + 2)
      ^ *(_DWORD *)a2
      ^ (16 * *((unsigned __int16 *)a2 + 6))
      ^ ((*(_DWORD *)a2 ^ *((unsigned __int8 *)a2 + 14)) << 7);
  v13 = (LockHashSlot *)(theLockManager[0] + 16LL * (((v12 >> 10) ^ v12) & (dword_10317F808 - 1)));
  v236 = v13;
  LockHashSlot::LockSlot(v13);
  v14 = (__int64 *)*((_QWORD *)v13 + 2 * LockHashSlot::SLOTS_TO_SKIP + 1);
  if ( !v14 )
  {
LABEL_2:
    LockHashSlot::UnlockSlot(v13);
    return 0;
  }
  while ( *((_DWORD *)v14 + 26) != *(_DWORD *)a2
       || *((_DWORD *)v14 + 27) != *((_DWORD *)a2 + 1)
       || *((_WORD *)v14 + 58) != *((_WORD *)a2 + 6)
       || *((_BYTE *)v14 + 118) != *((_BYTE *)a2 + 14)
       || *((_DWORD *)v14 + 28) != *((_DWORD *)a2 + 2) )
  {
    v14 = (__int64 *)*v14;
    if ( !v14 )
      goto LABEL_2;
  }
  LockHashSlot::UnlockSlot(v13);
  if ( (byte_10317AC16 & 0x40) != 0
    || (v16 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
        *(_QWORD *)v16)
    && (v17 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v16 + 56LL)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v17, 0x4B6u) )
  {
    v223 = 512;
    v113 = LockRes::Format(a2, v324, &v223, 0, 0);
    traceprint(L"  -- Migrating key resource: %ls\n", v113);
  }
  v18 = (LockHashSlot *)(theLockManager[0]
                       + 16LL
                       * ((((*((_DWORD *)v7 + 1)
                           ^ *((_DWORD *)v7 + 2)
                           ^ *(_DWORD *)v7
                           ^ (16 * *((unsigned __int16 *)v7 + 6))
                           ^ ((*(_DWORD *)v7 ^ (unsigned int)*((unsigned __int8 *)v7 + 14)) << 7)) >> 10)
                         ^ *((_DWORD *)v7 + 1)
                         ^ *((_DWORD *)v7 + 2)
                         ^ *(_DWORD *)v7
                         ^ (16 * *((unsigned __int16 *)v7 + 6))
                         ^ ((*(_DWORD *)v7 ^ *((unsigned __int8 *)v7 + 14)) << 7))
                        & (dword_10317F808 - 1)));
  v222 = v18;
  v19 = (LockHashSlot *)(theLockManager[0]
                       + 16LL
                       * ((dword_10317F808 - 1)
                        & (*(_DWORD *)v228
                         ^ *((_DWORD *)v228 + 1)
                         ^ *((_DWORD *)v228 + 2)
                         ^ (16 * *((unsigned __int16 *)v228 + 6))
                         ^ ((*(_DWORD *)v228 ^ *((unsigned __int8 *)v228 + 14)) << 7)
                         ^ ((*(_DWORD *)v228
                           ^ *((_DWORD *)v228 + 1)
                           ^ *((_DWORD *)v228 + 2)
                           ^ (16 * *((unsigned __int16 *)v228 + 6))
                           ^ ((*(_DWORD *)v228 ^ (unsigned int)*((unsigned __int8 *)v228 + 14)) << 7)) >> 10))));
  v234 = v19;
  v20 = v13;
  v221 = v13;
  v21 = v19;
  v22 = v18;
  if ( v13 > v19 )
  {
    v21 = v13;
    v20 = v19;
    v221 = v19;
  }
  if ( v20 > v18 )
  {
    v22 = v20;
    v20 = v18;
    v221 = v18;
  }
  if ( v21 > v22 )
  {
    v23 = v22;
    v22 = v21;
    v21 = v23;
  }
  v24 = 0;
  if ( v21 != v22 )
    v24 = v22;
  v25 = v21;
  if ( v20 == v21 )
    v25 = v24;
  v225 = v25;
  v26 = 0;
  if ( v20 != v21 )
    v26 = v24;
  v226 = v26;
  v27 = (struct LockMigrateLogInfo *)&v260;
  v210 = (struct LockMigrateLogInfo *)&v260;
  v214 = (struct LockMigrateLogInfo *)&v260;
  v28 = 0;
LABEL_24:
  if ( !LockBlocks )
  {
    v29 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v30 = *(_QWORD *)(v29 + 256);
    if ( !v30 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v30 = *(_QWORD *)(v29 + 256);
    }
    v248 = v30;
    v31 = *(_DWORD *)(v30 + 800);
    if ( (v31 & 0x1000000) == 0 || (*(_BYTE *)(v30 + 616) & 0x40) != 0 )
    {
      v32 = 0;
    }
    else
    {
      v32 = 1;
      *(_DWORD *)(v30 + 800) = v31 & 0xFEFFFFFF;
    }
    v249 = v32;
    v33 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v34 = *(_QWORD *)(v33 + 256);
    if ( !v34 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v34 = *(_QWORD *)(v33 + 256);
    }
    v35 = qword_103182380 + ((unsigned __int64)*(unsigned int *)(*(_QWORD *)(v34 + 608) + 3688LL) << 7);
    if ( *(_DWORD *)(*(_QWORD *)(v34 + 608) + 3688LL) >= SOS_PublicGlobals::sm_maxCpuCount
      || !*(_QWORD *)v35
      || (*(_BYTE *)(v34 + 800) & 4) != 0 )
    {
      LockBlocks = LockManager::GetLockBlocks((LockManager *)theLockManager, (struct Worker *)v34);
    }
    else
    {
      _mm_lfence();
      LockBlocks = *(struct Lock **)v35;
      *(_QWORD *)v35 = **(_QWORD **)v35;
      *(_QWORD *)LockBlocks = 0;
      --*(_QWORD *)(v35 + 16);
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
    v213 = LockBlocks;
    if ( v32 )
      *(_DWORD *)(v30 + 800) |= 0x1000000u;
    if ( !LockBlocks )
      goto LABEL_99;
    *((_BYTE *)LockBlocks + 90) = 0;
    *((_QWORD *)LockBlocks + 13) = *(_QWORD *)v7;
    *((_DWORD *)LockBlocks + 28) = *((_DWORD *)v7 + 2);
    *((_WORD *)LockBlocks + 58) = *((_WORD *)v7 + 6);
    *((_BYTE *)LockBlocks + 118) = *((_BYTE *)v7 + 14);
    v27 = v214;
    v210 = v214;
    v11 = v211;
  }
  if ( v10 >= v11 )
  {
LABEL_55:
    if ( v27 != (struct LockMigrateLogInfo *)&v260 )
    {
      operator delete[](v27);
      v27 = (struct LockMigrateLogInfo *)&v260;
      v210 = (struct LockMigrateLogInfo *)&v260;
      v214 = (struct LockMigrateLogInfo *)&v260;
    }
    if ( v11 <= 32 )
      goto LABEL_58;
    v60 = v11;
    v231 = 18675;
    v61 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v62 = *(_QWORD *)(v61 + 256);
    if ( !v62 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v62 = *(_QWORD *)(v61 + 256);
    }
    v63 = *(struct IMemObj **)(v62 + 1000);
    v258[3] = v63;
    v64 = 8LL * v11;
    if ( !is_mul_ok(v11, 8u) )
      v64 = -1;
    v65 = (struct LockMigrateLogInfo *)operator new[](
                                         v64,
                                         v63,
                                         1,
                                         "sql\\ntdbms\\storeng\\dfs\\manager\\lckmgr.cpp",
                                         18675,
                                         5u);
    v27 = v65;
    v210 = v65;
    v227 = v65;
    if ( v65 )
    {
      do
      {
        *(_DWORD *)v65 = 0;
        *((_WORD *)v65 + 2) = 0;
        v65 = (struct LockMigrateLogInfo *)((char *)v65 + 8);
        --v60;
      }
      while ( v60 );
    }
    else
    {
      v27 = 0;
      v210 = 0;
    }
    v214 = v27;
    if ( v27 )
    {
LABEL_58:
      v219 = v11;
      v45 = v221;
      LockHashSlot::LockSlot(v221);
      if ( v225 )
        LockHashSlot::LockSlot(v225);
      if ( v226 )
        LockHashSlot::LockSlot(v226);
      v46 = LockHashSlot::LookupLock(v234, v228);
      v229 = v46;
      v237 = LockHashSlot::LookupLock(v236, v235);
      v47 = LockHashSlot::LookupLock(v222, v7);
      lpAddress = (struct ExternalLockValueBlockBase **)v47;
      if ( v47 )
      {
        v50 = 0;
      }
      else
      {
        v47 = LockBlocks;
        lpAddress = (struct ExternalLockValueBlockBase **)LockBlocks;
        v114 = 2 * LockHashSlot::SLOTS_TO_SKIP;
        *(_QWORD *)LockBlocks = *(_QWORD *)(v49 + 16 * LockHashSlot::SLOTS_TO_SKIP + 8);
        *(_QWORD *)(v49 + 8 * v114 + 8) = LockBlocks;
        *((_QWORD *)LockBlocks + 1) = v49;
        v50 = 0;
        v213 = 0;
        v220 = 1;
      }
      if ( v48 )
      {
        if ( v46 && (*((_BYTE *)v46 + 91) & 2) != 0 )
        {
          *((_QWORD *)v47 + 12) = *((_QWORD *)v46 + 12);
          *((_BYTE *)v47 + 91) |= 2u;
        }
        v51 = (unsigned int)v11;
        v207 = v11;
        for ( i = 0; ; i = v215 + 1 )
        {
          v215 = i;
          if ( i > 1 )
            break;
          v53 = v50;
          v208 = v50;
          v54 = v50;
          v230 = v50;
          do
          {
            v55 = *((_QWORD *)v48 + v54 + 2);
            if ( v55 )
            {
              do
              {
                v56 = *(_BYTE *)(v55 + 55);
                if ( (v56 & 1) == 0 )
                {
                  if ( *(_BYTE *)(v55 + 54) )
                    goto LABEL_80;
                  v115 = *(_QWORD *)(v55 + 40);
                  if ( (v56 & 2) != 0 )
                    v115 = *(_QWORD *)(v115 + 56);
                  if ( *(_DWORD *)(v115 + 80) != 7 )
                  {
LABEL_80:
                    v53 = v208;
                    goto LABEL_73;
                  }
                }
                v55 = *(_QWORD *)v55;
              }
              while ( v55 );
              v53 = v208;
            }
            v55 = v50;
LABEL_73:
            if ( v46 )
            {
              while ( v55 )
              {
                FirstRealOwner = Lock::GetFirstRealOwner(v46, (unsigned int)v53, v51);
                if ( FirstRealOwner )
                {
                  v103 = (_DWORD *)((char *)v27 + 8 * v28);
                  while ( 1 )
                  {
                    v106 = *(XactLockInfo **)(FirstRealOwner + 40);
                    if ( (*(_BYTE *)(FirstRealOwner + 55) & 2) != 0 )
                      v106 = (XactLockInfo *)*((_QWORD *)v106 + 7);
                    XactLockInfo = LockOwner::GetXactLockInfo((LockOwner *)v55);
                    v109 = XactLockInfo;
                    if ( XactLockInfo != v106 )
                    {
                      XactLockInfo::Lock(XactLockInfo);
                      v104 = (XactLockInfo *)*((_QWORD *)v109 + 16);
                      XactLockInfo::Unlock(v109);
                      if ( v104 != v106 )
                      {
                        while ( 1 )
                        {
                          FirstRealOwner = *(_QWORD *)FirstRealOwner;
                          if ( !FirstRealOwner )
                            break;
                          v105 = *(_BYTE *)(FirstRealOwner + 55);
                          if ( (v105 & 1) == 0 )
                          {
                            if ( *(_BYTE *)(FirstRealOwner + 54) )
                              goto LABEL_164;
                            v116 = *(_QWORD *)(FirstRealOwner + 40);
                            if ( (v105 & 2) != 0 )
                              v116 = *(_QWORD *)(v116 + 56);
                            if ( *(_DWORD *)(v116 + 80) != 7 )
                              goto LABEL_164;
                          }
                        }
                        v50 = 0;
LABEL_176:
                        v27 = v210;
                        break;
                      }
                      v108 = v207;
                      v50 = 0;
                    }
                    v110 = *(_QWORD *)FirstRealOwner;
                    if ( v215 )
                    {
                      v91 = FirstRealOwner;
                      v92 = FirstRealOwner;
                      FirstRealOwner = *(_QWORD *)FirstRealOwner;
                      if ( v110 )
                      {
                        while ( 1 )
                        {
                          v119 = *(_BYTE *)(FirstRealOwner + 55);
                          if ( (v119 & 1) == 0 )
                          {
                            if ( *(_BYTE *)(FirstRealOwner + 54) )
                              break;
                            v120 = *(_QWORD *)(FirstRealOwner + 40);
                            if ( (v119 & 2) != 0 )
                              v120 = *(_QWORD *)(v120 + 56);
                            if ( *(_DWORD *)(v120 + 80) != 7 )
                              break;
                          }
                          FirstRealOwner = *(_QWORD *)FirstRealOwner;
                          if ( !FirstRealOwner )
                            goto LABEL_149;
                        }
                      }
                      else
                      {
LABEL_149:
                        FirstRealOwner = v50;
                      }
                      LockOwner::CopyReference(v91, lpAddress, &v218);
                      v209 = 1;
                      v94 = 22LL * *(unsigned __int8 *)(v91 + 54);
                      if ( *((_BYTE *)&LCK_sufficient + v94 + 8)
                        && !*((_BYTE *)&LCK_sufficient + v94 + 5)
                        && ((v95 = *(_QWORD *)(v92 + 40), (v96 = *(_BYTE *)(v91 + 55) & 2) != 0)
                          ? (v97 = *(_QWORD *)(v95 + 56))
                          : (v97 = *(_QWORD *)(v92 + 40)),
                            *(_DWORD *)(v97 + 80) == 1) )
                      {
                        if ( v96 )
                          v95 = *(_QWORD *)(v95 + 56);
                        v98 = *(_QWORD *)(v95 + 88);
                        v99 = *(_DWORD *)(v98 + 40);
                        v100 = *(_WORD *)(v98 + 44);
                        v50 = 0;
                        v101 = 0;
                        for ( j = 0; j < v28; ++j )
                        {
                          if ( *((_WORD *)v210 + 4 * j + 2) == v100 && *((_DWORD *)v210 + 2 * j) == v99 )
                            break;
                          ++v101;
                        }
                        if ( v101 == v216 )
                        {
                          *v103 = v99;
                          *((_WORD *)v103 + 2) = v100;
                          *((_WORD *)v103 + 3) = 0;
                          ++v216;
                          ++v28;
                          v103 += 2;
                        }
                      }
                      else
                      {
LABEL_164:
                        v50 = 0;
                      }
                    }
                    else
                    {
                      FirstRealOwner = *(_QWORD *)FirstRealOwner;
                      if ( v110 )
                      {
                        while ( 1 )
                        {
                          v117 = *(_BYTE *)(FirstRealOwner + 55);
                          if ( (v117 & 1) == 0 )
                          {
                            if ( *(_BYTE *)(FirstRealOwner + 54) )
                              break;
                            v118 = *(_QWORD *)(FirstRealOwner + 40);
                            if ( (v117 & 2) != 0 )
                              v118 = *(_QWORD *)(v118 + 56);
                            if ( *(_DWORD *)(v118 + 80) != 7 )
                              break;
                          }
                          FirstRealOwner = *(_QWORD *)FirstRealOwner;
                          if ( !FirstRealOwner )
                            goto LABEL_172;
                        }
                      }
                      else
                      {
LABEL_172:
                        FirstRealOwner = v50;
                      }
                      if ( !v108 )
                      {
                        v11 = 2 * v211;
                        v211 *= 2;
                        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                        {
                          v123 = rand();
                          if ( v123 == 5 * (v123 / 5) )
                            Spinlock<183,7,257>::UpdateStatSnapshot();
                        }
                        *(_QWORD *)v221 = 0;
                        v124 = v225;
                        if ( v225 )
                        {
                          if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                          {
                            v125 = rand();
                            if ( v125 == 5 * (v125 / 5) )
                              Spinlock<183,7,257>::UpdateStatSnapshot();
                          }
                          *(_QWORD *)v124 = 0;
                        }
                        v126 = v226;
                        v27 = v210;
                        LockBlocks = v213;
                        v10 = v219;
                        v7 = v224;
                        if ( v226 )
                        {
                          if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                          {
                            v127 = rand();
                            if ( v127 == 5 * (v127 / 5) )
                              Spinlock<183,7,257>::UpdateStatSnapshot();
                          }
                          *(_QWORD *)v126 = 0;
                          v27 = v210;
                        }
                        goto LABEL_24;
                      }
                      v207 = v108 - 1;
                    }
                    if ( !FirstRealOwner )
                      goto LABEL_176;
                  }
                }
                v55 = *(_QWORD *)v55;
                if ( v55 )
                {
                  while ( 1 )
                  {
                    v121 = *(_BYTE *)(v55 + 55);
                    if ( (v121 & 1) == 0 )
                    {
                      if ( *(_BYTE *)(v55 + 54) )
                        break;
                      v122 = *(_QWORD *)(v55 + 40);
                      if ( (v121 & 2) != 0 )
                        v122 = *(_QWORD *)(v122 + 56);
                      if ( *(_DWORD *)(v122 + 80) != 7 )
                        break;
                    }
                    v55 = *(_QWORD *)v55;
                    if ( !v55 )
                      goto LABEL_178;
                  }
                }
                else
                {
LABEL_178:
                  v55 = v50;
                }
                v51 = v207;
                v53 = v208;
                v46 = v229;
              }
              v54 = v230;
              v48 = v237;
            }
            v208 = ++v53;
            v230 = ++v54;
          }
          while ( v53 <= 3 );
        }
        v47 = (struct Lock *)lpAddress;
        v7 = v224;
        v45 = v221;
      }
      v57 = v209;
      if ( v209 )
      {
        Lock::GrantLocks(v47);
        if ( v46 )
          Lock::GrantLocks(v46);
      }
      if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v128 = rand();
        if ( v128 == 5 * (v128 / 5) )
          Spinlock<183,7,257>::UpdateStatSnapshot();
      }
      *(_QWORD *)v45 = 0;
      v58 = v225;
      if ( v225 )
      {
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v129 = rand();
          if ( v129 == 5 * (v129 / 5) )
            Spinlock<183,7,257>::UpdateStatSnapshot();
        }
        *(_QWORD *)v58 = 0;
      }
      v59 = v226;
      if ( v226 )
      {
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v130 = rand();
          if ( v130 == 5 * (v130 / 5) )
            Spinlock<183,7,257>::UpdateStatSnapshot();
        }
        *(_QWORD *)v59 = 0;
      }
      goto LABEL_100;
    }
  }
  else
  {
    while ( 1 )
    {
      v36 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v37 = *(_QWORD *)(v36 + 256);
      if ( !v37 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v37 = *(_QWORD *)(v36 + 256);
      }
      v250 = v37;
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
      v251 = v39;
      v40 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v41 = *(_QWORD *)(v40 + 256);
      if ( !v41 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v41 = *(_QWORD *)(v40 + 256);
      }
      v42 = qword_103182380 + ((unsigned __int64)*(unsigned int *)(*(_QWORD *)(v41 + 608) + 3688LL) << 7);
      if ( *(_DWORD *)(*(_QWORD *)(v41 + 608) + 3688LL) >= SOS_PublicGlobals::sm_maxCpuCount
        || !*(_QWORD *)(v42 + 8)
        || (*(_BYTE *)(v41 + 800) & 4) != 0 )
      {
        LockOwnerBlocks = LockManager::GetLockOwnerBlocks((LockManager *)theLockManager, (struct Worker *)v41);
      }
      else
      {
        _mm_lfence();
        LockOwnerBlocks = *(struct LockOwner **)(v42 + 8);
        *(_QWORD *)(v42 + 8) = *(_QWORD *)LockOwnerBlocks;
        *(_QWORD *)LockOwnerBlocks = 0;
        --*(_QWORD *)(v42 + 24);
        v44 = *((_QWORD *)LockOwnerBlocks + 4);
        *(_QWORD *)LockOwnerBlocks = 0;
        *((_QWORD *)LockOwnerBlocks + 1) = 0;
        *((_QWORD *)LockOwnerBlocks + 2) = 0;
        *((_QWORD *)LockOwnerBlocks + 3) = 0;
        *((_QWORD *)LockOwnerBlocks + 5) = 0;
        *((_QWORD *)LockOwnerBlocks + 6) = 0;
        *((_QWORD *)LockOwnerBlocks + 7) = 0;
        *((_QWORD *)LockOwnerBlocks + 4) = v44;
      }
      if ( v39 )
        *(_DWORD *)(v37 + 800) |= 0x1000000u;
      if ( !LockOwnerBlocks )
        break;
      *(_QWORD *)LockOwnerBlocks = v218;
      v218 = LockOwnerBlocks;
      ++v10;
      v11 = v211;
      if ( v10 >= v211 )
      {
        v27 = v214;
        v210 = v214;
        goto LABEL_55;
      }
    }
  }
LABEL_99:
  v212 = 1;
  v57 = v209;
LABEL_100:
  if ( !v57 && v220 )
  {
    v111 = v222;
    LockHashSlot::LockSlot(v222);
    v112 = (__int64 *)*((_QWORD *)v111 + 2 * LockHashSlot::SLOTS_TO_SKIP + 1);
    if ( v112 )
    {
      while ( *((_DWORD *)v112 + 26) != *(_DWORD *)v7
           || *((_DWORD *)v112 + 27) != *((_DWORD *)v7 + 1)
           || *((_WORD *)v112 + 58) != *((_WORD *)v7 + 6)
           || *((_BYTE *)v112 + 118) != *((_BYTE *)v7 + 14)
           || *((_DWORD *)v112 + 28) != *((_DWORD *)v7 + 2) )
      {
        v112 = (__int64 *)*v112;
        if ( !v112 )
          goto LABEL_285;
      }
      v131 = lpAddress;
      if ( !lpAddress[2]
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
        LockHashSlot::RemoveLock(v111, (struct Lock *)lpAddress);
        v132 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v133 = *(_QWORD *)(v132 + 256);
        if ( !v133 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v133 = *(_QWORD *)(v132 + 256);
        }
        v252 = v133;
        v134 = *(_DWORD *)(v133 + 800);
        if ( (v134 & 0x1000000) == 0 || (*(_BYTE *)(v133 + 616) & 0x40) != 0 )
        {
          v206 = 0;
          v253 = 0;
        }
        else
        {
          v206 = 1;
          v253 = 1;
          *(_DWORD *)(v133 + 800) = v134 & 0xFEFFFFFF;
        }
        v135 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v136 = *(_QWORD *)(v135 + 256);
        if ( !v136 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v136 = *(_QWORD *)(v135 + 256);
        }
        v137 = *(unsigned int *)(*(_QWORD *)(v136 + 608) + 3688LL);
        if ( (*((_BYTE *)lpAddress + 91) & 4) != 0 )
          v138 = lpAddress[12];
        else
          v138 = 0;
        v139 = *((unsigned __int8 *)lpAddress + 119);
        if ( (unsigned int)v137 >= SOS_PublicGlobals::sm_maxCpuCount
          || (v140 = (struct ExternalLockValueBlockBase ***)(qword_103182380 + (v137 << 7)),
              v141 = (unsigned __int64)v140[2],
              v141 >= 0x3E8)
          || (*(_BYTE *)(v136 + 800) & 4) != 0
          || (_DWORD)v139 != *(unsigned __int16 *)(*(_QWORD *)(v136 + 992) + 160LL) )
        {
          v143 = *(_QWORD *)(theLockManager[5 * v139 + 3] + 2016);
          QuadPart = 0;
          UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
          if ( *(_DWORD *)(v143 + 40)
            || _InterlockedCompareExchange64((volatile signed __int64 *)(v143 + 40), UniqueThread_low, 0) )
          {
            v146 = 0;
            if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
            {
              v147 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset;
              if ( v147 && *(_QWORD *)(v147 + 272) == v147 )
                v146 = *(_QWORD *)(v147 + 256);
              if ( v146 )
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
            v148 = v143 + 40;
            if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
              Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v148, UniqueThread_low);
            else
              Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v148, v146, UniqueThread_low);
            if ( v146 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v239);
                v149 = (DirtyPageMgr *)v239.QuadPart;
              }
              else
              {
                v149 = MEMORY[0x7FFE0008];
              }
              if ( v149 < QuadPart )
                *(_QWORD *)(v146 + 3192) = *(_QWORD *)(v146 + 3192);
              else
                *(_QWORD *)(v146 + 3192) += v149 - QuadPart;
              v131 = lpAddress;
            }
            else
            {
              v131 = lpAddress;
            }
          }
          if ( *(_QWORD *)(v143 + 8) >= *(_QWORD *)v143 )
          {
            if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v159 = rand();
              if ( v159 == 5 * (v159 / 5) )
                Spinlock<34,1,268435714>::UpdateStatSnapshot();
            }
            *(_QWORD *)(v143 + 40) = 0;
            (*(void (__fastcall **)(struct ExternalLockValueBlockBase **))(v143 + 48))(v131);
          }
          else
          {
            if ( *(_BYTE *)(*(_QWORD *)(v143 + 32) + 5820LL) )
            {
              v150 = (struct ExternalLockValueBlockBase ***)(v143 + 16 * ((*(_DWORD *)(v143 + 1176) & 0x3F) + 9LL));
              *v131 = (struct ExternalLockValueBlockBase *)*v150;
              if ( !*v150 )
                v150[1] = v131;
              *v150 = v131;
              ++*(_QWORD *)(v143 + 1176);
              VirtualProtect(v131, 0x1000u, 1u, &flOldProtect);
            }
            else
            {
              *v131 = *(struct ExternalLockValueBlockBase **)(v143 + 128);
              if ( !*(_QWORD *)(v143 + 128) )
                *(_QWORD *)(v143 + 136) = v131;
              *(_QWORD *)(v143 + 128) = v131;
            }
            v151 = *(_QWORD *)(v143 + 1168) + 1LL;
            ++*(_QWORD *)(v143 + 8);
            v152 = *(SOS_ObjectStore **)(v143 + 32);
            if ( !*((_BYTE *)v152 + 5820) && v151 >= 0x20 )
            {
              PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v152, (struct SList *)v131);
              v154 = v143 + 8 * PoolIdForObject;
              v155 = *(_QWORD *)(v143 + 128);
              v156 = *(_QWORD **)(v143 + 136);
              if ( v156 != (_QWORD *)(v143 + 128) && v156 )
              {
                *v156 = *(_QWORD *)(v154 + 1184);
                *(_QWORD *)(v154 + 1184) = v155;
              }
              *(_QWORD *)(v143 + 128) = 0;
              *(_QWORD *)(v143 + 136) = v143 + 128;
              v151 = 0;
              v157 = *(_QWORD *)(v143 + 1696);
              if ( (v157 & (1LL << PoolIdForObject)) == 0 )
                *(_QWORD *)(v143 + 1696) = (1LL << PoolIdForObject) | v157;
            }
            *(_QWORD *)(v143 + 1168) = v151;
            if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v158 = rand();
              if ( v158 == 5 * (v158 / 5) )
                Spinlock<34,1,268435714>::UpdateStatSnapshot();
            }
            *(_QWORD *)(v143 + 40) = 0;
          }
        }
        else
        {
          v140[2] = (struct ExternalLockValueBlockBase **)(v141 + 1);
          *lpAddress = (struct ExternalLockValueBlockBase *)*v140;
          *v140 = lpAddress;
        }
        if ( v138 )
          LockManager::PutExternalLvb((LockManager *)theLockManager, v138);
        v111 = v222;
        if ( v206 )
          *(_DWORD *)(v133 + 800) |= 0x1000000u;
      }
    }
LABEL_285:
    if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v142 = rand();
      if ( v142 == 5 * (v142 / 5) )
        Spinlock<183,7,257>::UpdateStatSnapshot();
    }
    *(_QWORD *)v111 = 0;
  }
  v66 = v213;
  if ( v213 )
  {
    v67 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v68 = *(_QWORD *)(v67 + 256);
    if ( !v68 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v68 = *(_QWORD *)(v67 + 256);
    }
    v254 = v68;
    v69 = *(_DWORD *)(v68 + 800);
    if ( (v69 & 0x1000000) == 0 || (*(_BYTE *)(v68 + 616) & 0x40) != 0 )
    {
      v204 = 0;
      v255 = 0;
    }
    else
    {
      v204 = 1;
      v255 = 1;
      *(_DWORD *)(v68 + 800) = v69 & 0xFEFFFFFF;
    }
    v70 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v71 = *(_QWORD *)(v70 + 256);
    if ( !v71 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v71 = *(_QWORD *)(v70 + 256);
    }
    v72 = *(unsigned int *)(*(_QWORD *)(v71 + 608) + 3688LL);
    if ( (*((_BYTE *)v213 + 91) & 4) != 0 )
      v73 = (struct ExternalLockValueBlockBase *)*((_QWORD *)v213 + 12);
    else
      v73 = 0;
    v74 = *((unsigned __int8 *)v213 + 119);
    if ( (unsigned int)v72 >= SOS_PublicGlobals::sm_maxCpuCount
      || (v75 = (struct SList **)(qword_103182380 + (v72 << 7)), v76 = (unsigned __int64)v75[2], v76 >= 0x3E8)
      || (*(_BYTE *)(v71 + 800) & 4) != 0
      || (_DWORD)v74 != *(unsigned __int16 *)(*(_QWORD *)(v71 + 992) + 160LL) )
    {
      v160 = *(_QWORD *)(theLockManager[5 * v74 + 3] + 2016);
      v161 = 0;
      v162 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)(v160 + 40) || _InterlockedCompareExchange64((volatile signed __int64 *)(v160 + 40), v162, 0) )
      {
        v163 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v164 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v164 && *(_QWORD *)(v164 + 272) == v164 )
            v163 = *(_QWORD *)(v164 + 256);
          if ( v163 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v240);
              v161 = (DirtyPageMgr *)v240.QuadPart;
            }
            else
            {
              v161 = MEMORY[0x7FFE0008];
            }
          }
        }
        v165 = v160 + 40;
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v165, v162);
        else
          Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v165, v163, v162);
        if ( v163 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v241);
            v166 = (DirtyPageMgr *)v241.QuadPart;
          }
          else
          {
            v166 = MEMORY[0x7FFE0008];
          }
          if ( v166 < v161 )
            v167 = 0;
          else
            v167 = v166 - v161;
          *(_QWORD *)(v163 + 3192) += v167;
        }
        v66 = v213;
      }
      if ( *(_QWORD *)(v160 + 8) >= *(_QWORD *)v160 )
      {
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v178 = rand();
          if ( v178 == 5 * (v178 / 5) )
            Spinlock<34,1,268435714>::UpdateStatSnapshot();
        }
        *(_QWORD *)(v160 + 40) = 0;
        (*(void (__fastcall **)(struct SList *))(v160 + 48))(v66);
      }
      else
      {
        if ( *(_BYTE *)(*(_QWORD *)(v160 + 32) + 5820LL) )
        {
          v168 = (struct SList **)(v160 + 16 * ((*(_DWORD *)(v160 + 1176) & 0x3F) + 9LL));
          *(_QWORD *)v66 = *v168;
          if ( !*v168 )
            v168[1] = v66;
          *v168 = v66;
          ++*(_QWORD *)(v160 + 1176);
          VirtualProtect(v66, 0x1000u, 1u, &v233);
        }
        else
        {
          *(_QWORD *)v66 = *(_QWORD *)(v160 + 128);
          if ( !*(_QWORD *)(v160 + 128) )
            *(_QWORD *)(v160 + 136) = v66;
          *(_QWORD *)(v160 + 128) = v66;
        }
        v169 = *(_QWORD *)(v160 + 1168) + 1LL;
        ++*(_QWORD *)(v160 + 8);
        v170 = *(SOS_ObjectStore **)(v160 + 32);
        if ( !*((_BYTE *)v170 + 5820) && v169 >= 0x20 )
        {
          v171 = SOS_ObjectStore::GetPoolIdForObject(v170, v66);
          v172 = v160 + 8LL * v171;
          v173 = *(_QWORD *)(v160 + 128);
          v174 = *(_QWORD **)(v160 + 136);
          if ( v174 != (_QWORD *)(v160 + 128) && v174 )
          {
            *v174 = *(_QWORD *)(v172 + 1184);
            *(_QWORD *)(v172 + 1184) = v173;
          }
          *(_QWORD *)(v160 + 128) = 0;
          *(_QWORD *)(v160 + 136) = v160 + 128;
          v169 = 0;
          v175 = 1LL << v171;
          v176 = *(_QWORD *)(v160 + 1696);
          if ( (v175 & v176) == 0 )
            *(_QWORD *)(v160 + 1696) = v176 | v175;
        }
        *(_QWORD *)(v160 + 1168) = v169;
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v177 = rand();
          if ( v177 == 5 * (v177 / 5) )
            Spinlock<34,1,268435714>::UpdateStatSnapshot();
        }
        *(_QWORD *)(v160 + 40) = 0;
      }
    }
    else
    {
      v75[2] = (struct SList *)(v76 + 1);
      *(_QWORD *)v213 = *v75;
      *v75 = v213;
    }
    if ( v73 )
      LockManager::PutExternalLvb((LockManager *)theLockManager, v73);
    if ( v204 )
      *(_DWORD *)(v68 + 800) |= 0x1000000u;
  }
  if ( v218 )
  {
    v77 = 0;
    do
    {
      v78 = v218;
      v218 = *(struct SList **)v218;
      *(_QWORD *)v78 = 0;
      v79 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v80 = *(_QWORD *)(v79 + 256);
      if ( !v80 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v80 = *(_QWORD *)(v79 + 256);
      }
      v256 = v80;
      v81 = *(_DWORD *)(v80 + 800);
      if ( (v81 & 0x1000000) == 0 || (*(_BYTE *)(v80 + 616) & 0x40) != 0 )
      {
        v205 = 0;
        v257 = 0;
      }
      else
      {
        v205 = 1;
        v257 = 1;
        *(_DWORD *)(v80 + 800) = v81 & 0xFEFFFFFF;
      }
      v82 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v83 = *(_QWORD *)(v82 + 256);
      if ( !v83 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v83 = *(_QWORD *)(v82 + 256);
      }
      v84 = *(unsigned int *)(*(_QWORD *)(v83 + 608) + 3688LL);
      v85 = *((_BYTE *)v78 + 55);
      if ( (v85 & 0x10) != 0 || (v86 = *((_QWORD *)v78 + 4), v86 > 0x40) )
      {
        v179 = (unsigned __int64)v78 & 0xFFFFFFFFFFFFE000uLL;
        if ( ((unsigned __int64)v78 & 0xFFFFFFFFFFFFE000uLL) != 0
          && *(_WORD *)(((unsigned __int64)v78 & 0xFFFFFFFFFFFFE000uLL) + 4) == 512 )
        {
          v179 = *(_QWORD *)(((unsigned __int64)v78 & 0xFFFFFFFFFFFFE000uLL) + 0x28);
        }
        v180 = *(_QWORD *)(v179 + 8);
        v181 = (unsigned __int64)v78 & -*(_QWORD *)(v180 + 16);
        if ( v181 && *(_WORD *)(((unsigned __int64)v78 & -*(_QWORD *)(v180 + 16)) + 4) == 512 )
          v181 = *(_QWORD *)(((unsigned __int64)v78 & -*(_QWORD *)(v180 + 16)) + 0x28);
        v182 = *(_QWORD *)(v181 + 8);
        v183 = 0;
        v184 = qword_10317F830;
        while ( *(v184 - 1) != v182 && *v184 != v182 && v184[1] != v182 )
        {
          ++v183;
          v184 += 5;
          if ( v183 >= 0x41 )
          {
            LODWORD(v86) = -1;
            goto LABEL_398;
          }
        }
        LODWORD(v86) = v183;
LABEL_398:
        *((_QWORD *)v78 + 4) = (unsigned int)v86;
        *((_BYTE *)v78 + 55) = v85 & 0xEF;
      }
      if ( (unsigned int)v84 >= SOS_PublicGlobals::sm_maxCpuCount
        || (v87 = qword_103182380 + (v84 << 7), v88 = *(_QWORD *)(v87 + 24), v88 >= 0x3E8)
        || (*(_BYTE *)(v83 + 800) & 4) != 0
        || (_DWORD)v86 != *(unsigned __int16 *)(*(_QWORD *)(v83 + 992) + 160LL) )
      {
        v185 = *(_QWORD *)(theLockManager[5 * (unsigned int)v86 + 3] + 2016) + 1832LL;
        v186 = 0;
        v187 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)(*(_QWORD *)(theLockManager[5 * (unsigned int)v86 + 3] + 2016) + 1872LL)
          || _InterlockedCompareExchange64(
               (volatile signed __int64 *)(*(_QWORD *)(theLockManager[5 * (unsigned int)v86 + 3] + 2016) + 1872LL),
               v187,
               0) )
        {
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v188 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset;
            if ( v188 && *(_QWORD *)(v188 + 272) == v188 )
              v77 = *(_QWORD *)(v188 + 256);
            if ( v77 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v242);
                v186 = (DirtyPageMgr *)v242.QuadPart;
              }
              else
              {
                v186 = MEMORY[0x7FFE0008];
              }
            }
          }
          v189 = v185 + 40;
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v189, v187);
          else
            Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v189, v77, v187);
          if ( v77 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v243);
              v190 = (DirtyPageMgr *)v243.QuadPart;
            }
            else
            {
              v190 = MEMORY[0x7FFE0008];
            }
            if ( v190 < v186 )
              v191 = 0;
            else
              v191 = v190 - v186;
            *(_QWORD *)(v77 + 3192) += v191;
          }
          v77 = 0;
        }
        if ( *(_QWORD *)(v185 + 8) >= *(_QWORD *)v185 )
        {
          if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v202 = rand();
            if ( v202 == 5 * (v202 / 5) )
              Spinlock<34,1,268435714>::UpdateStatSnapshot();
          }
          *(_QWORD *)(v185 + 40) = 0;
          (*(void (__fastcall **)(struct SList *))(v185 + 48))(v78);
        }
        else
        {
          if ( *(_BYTE *)(*(_QWORD *)(v185 + 32) + 5820LL) )
          {
            v192 = (_QWORD *)(v185 + 16 * ((*(_DWORD *)(v185 + 1176) & 0x3F) + 9LL));
            *(_QWORD *)v78 = *v192;
            if ( !*v192 )
              v192[1] = v78;
            *v192 = v78;
            ++*(_QWORD *)(v185 + 1176);
            VirtualProtect(v78, 0x1000u, 1u, &v247);
          }
          else
          {
            *(_QWORD *)v78 = *(_QWORD *)(v185 + 128);
            if ( !*(_QWORD *)(v185 + 128) )
              *(_QWORD *)(v185 + 136) = v78;
            *(_QWORD *)(v185 + 128) = v78;
          }
          v193 = *(_QWORD *)(v185 + 1168) + 1LL;
          ++*(_QWORD *)(v185 + 8);
          v194 = *(SOS_ObjectStore **)(v185 + 32);
          if ( !*((_BYTE *)v194 + 5820) && v193 >= 0x20 )
          {
            v195 = SOS_ObjectStore::GetPoolIdForObject(v194, v78);
            v196 = v185 + 8LL * v195;
            v197 = *(_QWORD *)(v185 + 128);
            v198 = *(_QWORD **)(v185 + 136);
            if ( v198 != (_QWORD *)(v185 + 128) && v198 )
            {
              *v198 = *(_QWORD *)(v196 + 1184);
              *(_QWORD *)(v196 + 1184) = v197;
            }
            *(_QWORD *)(v185 + 128) = 0;
            *(_QWORD *)(v185 + 136) = v185 + 128;
            v193 = 0;
            v199 = 1LL << v195;
            v200 = *(_QWORD *)(v185 + 1696);
            if ( (v199 & v200) == 0 )
              *(_QWORD *)(v185 + 1696) = v200 | v199;
          }
          *(_QWORD *)(v185 + 1168) = v193;
          if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v201 = rand();
            if ( v201 == 5 * (v201 / 5) )
              Spinlock<34,1,268435714>::UpdateStatSnapshot();
          }
          *(_QWORD *)(v185 + 40) = 0;
        }
      }
      else
      {
        *(_QWORD *)(v87 + 24) = v88 + 1;
        *(_QWORD *)v78 = *(_QWORD *)(v87 + 8);
        *(_QWORD *)(v87 + 8) = v78;
      }
      if ( v205 )
        *(_DWORD *)(v80 + 800) |= 0x1000000u;
    }
    while ( v218 );
  }
  if ( v212 )
  {
    ex_raise(12, 4, 19, 5);
    utassert_fail(1u, "FALSE", "lckmgr.cpp", 18927, "Shouldn't continue from exception");
  }
  try
  {
    if ( v216 > 0 )
    {
      _mm_lfence();
      XDES::LogLockMigration(v246, v245, v244, v216, v214);
    }
  }
  catch ( SQLError v259 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v258, (const struct SQLError *)v259);
      if ( v214 != (struct LockMigrateLogInfo *)&v260 )
      {
        operator delete[](v214);
        v214 = (struct LockMigrateLogInfo *)&v260;
      }
      CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v258);
      ExceptionRethrow(CurrentException);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v258);
    }
    catch ( ShortStackException )
    {
    }
  }
  v89 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v90 = *(struct Worker **)(v89 + 256);
  if ( !v90 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v90 = *(struct Worker **)(v89 + 256);
  }
  if ( *((_DWORD *)v90 + 139) )
    ExceptionPostCatchActions(v90);
  if ( v214 != (struct LockMigrateLogInfo *)&v260 )
    operator delete[](v214);
  return 1;
}

```

## disassembly

```asm
0x100451de0  push    rbx
0x100451de2  push    rsi
0x100451de3  push    rdi
0x100451de4  push    r12
0x100451de6  push    r13
0x100451de8  push    r14
0x100451dea  push    r15
0x100451dec  sub     rsp, 4F0h
0x100451df3  mov     [rsp+528h+var_378], 0FFFFFFFFFFFFFFFEh
0x100451dff  mov     rax, cs:__security_cookie
0x100451e06  xor     rax, rsp
0x100451e09  mov     [rsp+528h+var_48], rax
0x100451e11  mov     r12, r9
0x100451e14  mov     [rsp+528h+var_490], r9
0x100451e1c  mov     [rsp+528h+var_470], r8
0x100451e24  mov     rdi, rdx
0x100451e27  mov     [rsp+528h+var_440], rdx
0x100451e2f  mov     rax, [rsp+528h+arg_20]
0x100451e37  mov     [rsp+528h+var_3E8], rax
0x100451e3f  mov     rax, [rsp+528h+arg_28]
0x100451e47  mov     [rsp+528h+var_3F0], rax
0x100451e4f  mov     rax, [rsp+528h+arg_30]
0x100451e57  mov     [rsp+528h+var_3F8], rax
0x100451e5f  xor     ecx, ecx
0x100451e61  mov     [rsp+528h+lpAddress], rcx
0x100451e66  mov     r14d, ecx
0x100451e69  mov     [rsp+528h+var_4D8], rcx
0x100451e6e  mov     [rsp+528h+var_4B8], rcx
0x100451e73  mov     [rsp+528h+var_4EC], ecx
0x100451e77  mov     [rsp+528h+var_4DC], ecx
0x100451e7b  mov     [rsp+528h+var_4AC], ecx
0x100451e7f  mov     r15d, ecx
0x100451e82  mov     [rsp+528h+var_348], ecx
0x100451e89  mov     [rsp+528h+var_344], cx
0x100451e91  mov     [rsp+528h+var_340], ecx
0x100451e98  mov     [rsp+528h+var_33C], cx
0x100451ea0  mov     [rsp+528h+var_338], ecx
0x100451ea7  mov     [rsp+528h+var_334], cx
0x100451eaf  mov     [rsp+528h+var_330], ecx
0x100451eb6  mov     [rsp+528h+var_32C], cx
0x100451ebe  mov     [rsp+528h+var_328], ecx
0x100451ec5  mov     [rsp+528h+var_324], cx
0x100451ecd  mov     [rsp+528h+var_320], ecx
0x100451ed4  mov     [rsp+528h+var_31C], cx
0x100451edc  mov     [rsp+528h+var_318], ecx
0x100451ee3  mov     [rsp+528h+var_314], cx
0x100451eeb  mov     [rsp+528h+var_310], ecx
0x100451ef2  mov     [rsp+528h+var_30C], cx
0x100451efa  mov     [rsp+528h+var_308], ecx
0x100451f01  mov     [rsp+528h+var_304], cx
0x100451f09  mov     [rsp+528h+var_300], ecx
0x100451f10  mov     [rsp+528h+var_2FC], cx
0x100451f18  mov     [rsp+528h+var_2F8], ecx
0x100451f1f  mov     [rsp+528h+var_2F4], cx
0x100451f27  mov     [rsp+528h+var_2F0], ecx
0x100451f2e  mov     [rsp+528h+var_2EC], cx
0x100451f36  mov     [rsp+528h+var_2E8], ecx
0x100451f3d  mov     [rsp+528h+var_2E4], cx
0x100451f45  mov     [rsp+528h+var_2E0], ecx
0x100451f4c  mov     [rsp+528h+var_2DC], cx
0x100451f54  mov     [rsp+528h+var_2D8], ecx
0x100451f5b  mov     [rsp+528h+var_2D4], cx
0x100451f63  mov     [rsp+528h+var_2D0], ecx
0x100451f6a  mov     [rsp+528h+var_2CC], cx
0x100451f72  mov     [rsp+528h+var_2C8], ecx
0x100451f79  mov     [rsp+528h+var_2C4], cx
0x100451f81  mov     [rsp+528h+var_2C0], ecx
0x100451f88  mov     [rsp+528h+var_2BC], cx
0x100451f90  mov     [rsp+528h+var_2B8], ecx
0x100451f97  mov     [rsp+528h+var_2B4], cx
0x100451f9f  mov     [rsp+528h+var_2B0], ecx
0x100451fa6  mov     [rsp+528h+var_2AC], cx
0x100451fae  mov     [rsp+528h+var_2A8], ecx
0x100451fb5  mov     [rsp+528h+var_2A4], cx
0x100451fbd  mov     [rsp+528h+var_2A0], ecx
0x100451fc4  mov     [rsp+528h+var_29C], cx
0x100451fcc  mov     [rsp+528h+var_298], ecx
0x100451fd3  mov     [rsp+528h+var_294], cx
0x100451fdb  mov     [rsp+528h+var_290], ecx
0x100451fe2  mov     [rsp+528h+var_28C], cx
0x100451fea  mov     [rsp+528h+var_288], ecx
0x100451ff1  mov     [rsp+528h+var_284], cx
0x100451ff9  mov     [rsp+528h+var_280], ecx
0x100452000  mov     [rsp+528h+var_27C], cx
0x100452008  mov     [rsp+528h+var_278], ecx
0x10045200f  mov     [rsp+528h+var_274], cx
0x100452017  mov     [rsp+528h+var_270], ecx
0x10045201e  mov     [rsp+528h+var_26C], cx
0x100452026  mov     [rsp+528h+var_268], ecx
0x10045202d  mov     [rsp+528h+var_264], cx
0x100452035  mov     [rsp+528h+var_260], ecx
0x10045203c  mov     [rsp+528h+var_25C], cx
0x100452044  mov     [rsp+528h+var_258], ecx
0x10045204b  mov     [rsp+528h+var_254], cx
0x100452053  mov     [rsp+528h+var_250], ecx
0x10045205a  mov     [rsp+528h+var_24C], cx
0x100452062  mov     [rsp+528h+var_4C4], ecx
0x100452066  mov     esi, 20h ; ' '
0x10045206b  mov     [rsp+528h+var_4E0], esi
0x10045206f  movzx   edx, byte ptr [rdx+0Eh]
0x100452073  xor     edx, [rdi]
0x100452075  shl     edx, 7
0x100452078  movzx   eax, word ptr [rdi+0Ch]
0x10045207c  shl     eax, 4
0x10045207f  xor     edx, eax
0x100452081  xor     edx, [rdi]
0x100452083  xor     edx, [rdi+8]
0x100452086  xor     edx, [rdi+4]
0x100452089  mov     eax, edx
0x10045208b  shr     eax, 0Ah
0x10045208e  xor     edx, eax
0x100452090  mov     r13d, cs:dword_10317F808
0x100452097  dec     r13d
0x10045209a  and     r13d, edx
0x10045209d  shl     r13, 4
0x1004520a1  add     r13, cs:?theLockManager@@3VLockManager@@A; LockManager theLockManager
0x1004520a8  mov     [rsp+528h+var_438], r13
0x1004520b0  mov     rcx, r13; this
0x1004520b3  call    ?LockSlot@LockHashSlot@@QEAAXXZ; LockHashSlot::LockSlot(void)
0x1004520b8  mov     rax, cs:?SLOTS_TO_SKIP@LockHashSlot@@2_KA; unsigned __int64 LockHashSlot::SLOTS_TO_SKIP
0x1004520bf  add     rax, rax
0x1004520c2  mov     rbx, [r13+rax*8+8]
0x1004520c7  test    rbx, rbx
0x1004520ca  jnz     loc_1005A5014
0x1004520d0  mov     rcx, r13; this
0x1004520d3  call    ?UnlockSlot@LockHashSlot@@QEAAXXZ; LockHashSlot::UnlockSlot(void)
0x1004520d8  xor     eax, eax
0x1004520da  mov     rcx, [rsp+528h+var_48]
0x1004520e2  xor     rcx, rsp; StackCookie
0x1004520e5  call    __security_check_cookie
0x1004520ea  add     rsp, 4F0h
0x1004520f1  pop     r15
0x1004520f3  pop     r14
0x1004520f5  pop     r13
0x1004520f7  pop     r12
0x1004520f9  pop     rdi
0x1004520fa  pop     rsi
0x1004520fb  pop     rbx
0x1004520fc  retn
0x1005a5014  mov     ecx, [rdi]
0x1005a5016  cmp     [rbx+68h], ecx
0x1005a5019  jnz     loc_1005BAD00
0x1005a501f  mov     eax, [rdi+4]
0x1005a5022  cmp     [rbx+6Ch], eax
0x1005a5025  jnz     loc_1005BAD00
0x1005a502b  movzx   eax, word ptr [rdi+0Ch]
0x1005a502f  cmp     [rbx+74h], ax
0x1005a5033  jnz     loc_1005BAD00
0x1005a5039  movzx   eax, byte ptr [rdi+0Eh]
0x1005a503d  cmp     [rbx+76h], al
0x1005a5040  jnz     loc_1005BAD00
0x1005a5046  mov     eax, [rdi+8]
0x1005a5049  cmp     [rbx+70h], eax
0x1005a504c  jnz     loc_1005BAD00
0x1005a5052  mov     rcx, r13; this
0x1005a5055  call    ?UnlockSlot@LockHashSlot@@QEAAXXZ; LockHashSlot::UnlockSlot(void)
0x1005a505a  test    rbx, rbx
0x1005a505d  jz      loc_1004520D8
0x1005a5063  test    cs:byte_10317AC16, 40h
0x1005a506a  jnz     loc_10188CDC1
0x1005a5070  mov     r8, gs:58h
0x1005a5079  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1005a5080  mov     ecx, [rax]
0x1005a5082  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1005a5089  mov     edx, [rax]
0x1005a508b  add     rdx, [r8+rcx*8]
0x1005a508f  mov     rax, [rdx]
0x1005a5092  test    rax, rax
0x1005a5095  jz      short loc_1005A50A7
0x1005a5097  mov     rax, [rax+38h]
0x1005a509b  mov     rcx, [rax]
0x1005a509e  test    rcx, rcx
0x1005a50a1  jnz     loc_10188CDAE
0x1005a50a7  movzx   edx, byte ptr [r12+0Eh]
0x1005a50ad  xor     edx, [r12]
0x1005a50b1  shl     edx, 7
0x1005a50b4  movzx   eax, word ptr [r12+0Ch]
0x1005a50ba  shl     eax, 4
0x1005a50bd  xor     edx, eax
0x1005a50bf  xor     edx, [r12]
0x1005a50c3  xor     edx, [r12+8]
0x1005a50c8  xor     edx, [r12+4]
0x1005a50cd  mov     eax, edx
0x1005a50cf  shr     eax, 0Ah
0x1005a50d2  xor     edx, eax
0x1005a50d4  mov     r9d, cs:dword_10317F808
0x1005a50db  dec     r9d
0x1005a50de  mov     r10d, r9d
0x1005a50e1  and     r10d, edx
0x1005a50e4  shl     r10, 4
0x1005a50e8  add     r10, cs:?theLockManager@@3VLockManager@@A; LockManager theLockManager
0x1005a50ef  mov     [rsp+528h+var_4A0], r10
0x1005a50f7  mov     r11, [rsp+528h+var_470]
0x1005a50ff  movzx   edx, byte ptr [r11+0Eh]
0x1005a5104  xor     edx, [r11]
0x1005a5107  shl     edx, 7
0x1005a510a  movzx   eax, word ptr [r11+0Ch]
0x1005a510f  shl     eax, 4
0x1005a5112  xor     edx, eax
0x1005a5114  xor     edx, [r11+8]
0x1005a5118  xor     edx, [r11+4]
0x1005a511c  xor     edx, [r11]
0x1005a511f  mov     eax, edx
0x1005a5121  shr     eax, 0Ah
0x1005a5124  xor     eax, edx
0x1005a5126  and     eax, r9d
0x1005a5129  shl     rax, 4
0x1005a512d  add     rax, cs:?theLockManager@@3VLockManager@@A; LockManager theLockManager
0x1005a5134  mov     [rsp+528h+var_448], rax
0x1005a513c  mov     r8, r13
0x1005a513f  mov     [rsp+528h+var_4A8], r13
0x1005a5147  mov     rcx, rax
0x1005a514a  mov     rdx, r10
0x1005a514d  cmp     r13, rax
0x1005a5150  jbe     short loc_1005A5160
0x1005a5152  mov     rcx, r13
0x1005a5155  mov     r8, rax
0x1005a5158  mov     [rsp+528h+var_4A8], rax
0x1005a5160  cmp     r8, r10
0x1005a5163  ja      loc_1005A5B3C
0x1005a5169  cmp     rcx, rdx
0x1005a516c  jbe     short loc_1005A5177
0x1005a516e  mov     rax, rdx
0x1005a5171  mov     rdx, rcx
0x1005a5174  mov     rcx, rax
0x1005a5177  xor     r9d, r9d
0x1005a517a  mov     eax, r9d
0x1005a517d  cmp     rcx, rdx
0x1005a5180  cmovnz  rax, rdx
0x1005a5184  mov     rbx, rcx
0x1005a5187  cmp     r8, rcx
0x1005a518a  cmovz   rbx, rax
0x1005a518e  mov     [rsp+528h+var_488], rbx
0x1005a5196  mov     ebx, r9d
0x1005a5199  cmovnz  rbx, rax
0x1005a519d  mov     [rsp+528h+var_480], rbx
0x1005a51a5  lea     rdi, [rsp+528h+var_348]
0x1005a51ad  mov     [rsp+528h+var_4E8], rdi
0x1005a51b2  mov     [rsp+528h+var_4D0], rdi
0x1005a51b7  mov     r13d, r9d
0x1005a51ba  test    r14, r14
0x1005a51bd  jnz     loc_1005A5323
0x1005a51c3  mov     rdx, gs:58h
0x1005a51cc  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1005a51d3  mov     ecx, [rax]
0x1005a51d5  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1005a51dc  mov     edi, [rax]
0x1005a51de  add     rdi, [rdx+rcx*8]
0x1005a51e2  mov     rbx, [rdi+100h]
0x1005a51e9  test    rbx, rbx
0x1005a51ec  jz      loc_10188CE03
0x1005a51f2  mov     [rsp+528h+var_3D8], rbx
0x1005a51fa  mov     eax, [rbx+320h]
0x1005a5200  bt      eax, 18h
0x1005a5204  jb      loc_10188CE18
0x1005a520a  xor     sil, sil
0x1005a520d  mov     [rsp+528h+var_3D0], sil
0x1005a5215  mov     rdx, gs:58h
0x1005a521e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1005a5225  mov     ecx, [rax]
0x1005a5227  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1005a522e  mov     edi, [rax]
0x1005a5230  add     rdi, [rdx+rcx*8]
0x1005a5234  mov     r8, [rdi+100h]
0x1005a523b  test    r8, r8
0x1005a523e  jz      loc_10188CE38
0x1005a5244  mov     rax, [r8+260h]
0x1005a524b  mov     ecx, [rax+0E68h]
0x1005a5251  mov     edx, ecx
0x1005a5253  shl     rdx, 7
0x1005a5257  add     rdx, cs:qword_103182380
0x1005a525e  mov     rax, cs:__imp_?sm_maxCpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_maxCpuCount
0x1005a5265  cmp     ecx, [rax]
0x1005a5267  jnb     loc_10188CE4D
0x1005a526d  cmp     qword ptr [rdx], 0
0x1005a5271  jz      loc_10188CE4D
0x1005a5277  test    byte ptr [r8+320h], 4
0x1005a527f  jnz     loc_10188CE4D
0x1005a5285  lfence
0x1005a5288  mov     r14, [rdx]
0x1005a528b  mov     rax, [r14]
0x1005a528e  mov     [rdx], rax
0x1005a5291  xor     r9d, r9d
0x1005a5294  mov     [r14], r9
0x1005a5297  dec     qword ptr [rdx+10h]
0x1005a529b  mov     [r14+8], r9
0x1005a529f  mov     [r14+10h], r9
0x1005a52a3  mov     [r14+18h], r9
0x1005a52a7  mov     [r14+20h], r9
0x1005a52ab  mov     [r14+28h], r9
0x1005a52af  mov     [r14+30h], r9
0x1005a52b3  mov     [r14+38h], r9
0x1005a52b7  mov     [r14+40h], r9
0x1005a52bb  mov     [r14+48h], r9
0x1005a52bf  mov     [r14+50h], r9
0x1005a52c3  mov     [r14+58h], r9w
0x1005a52c8  mov     [r14+5Bh], r9b
0x1005a52cc  jmp     short loc_1005A52CF
0x1005a52cf  mov     [rsp+528h+var_4D8], r14
0x1005a52d4  test    sil, sil
  ... truncated ...
```
