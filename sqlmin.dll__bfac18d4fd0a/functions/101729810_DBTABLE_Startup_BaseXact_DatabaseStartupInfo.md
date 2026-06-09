# DBTABLE::Startup(BaseXact *,DatabaseStartupInfo &)

- ea: `0x101729810`
- end: `0x10172cbe9`
- name: `?Startup@DBTABLE@@QEAAXPEAVBaseXact@@AEAVDatabaseStartupInfo@@@Z`
- size: `13273`
- prototype: `void __fastcall(DBTABLE *__hidden this, struct BaseXact *, struct DatabaseStartupInfo *)`
- caller_count: `1`
- callee_count: `90`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1016fa0a0`

## callees

- `0x100401380`
- `0x1004013f0`
- `0x100401490`
- `0x100402000`
- `0x100402620`
- `0x1004049f0`
- `0x100404fd0`
- `0x10040da80`
- `0x10040fc00`
- `0x100415e90`
- `0x10041b5d0`
- `0x10041e3e0`
- `0x100423180`
- `0x100425e10`
- `0x100425e80`
- `0x10042db70`
- `0x10047bc10`
- `0x1004bff60`
- `0x1004c4220`
- `0x10055cea0`
- `0x10056a960`
- `0x10056afe0`
- `0x10056b1c0`
- `0x10056b280`
- `0x10056b530`
- `0x1005f1f00`
- `0x10061fb80`
- `0x10072d4d0`
- `0x10072d690`
- `0x10075b5c0`
- `0x10075be40`
- `0x100a52b30`
- `0x100a52ba0`
- `0x100abea90`
- `0x100abf730`
- `0x1011f5440`
- `0x1011f54e0`
- `0x10168bf50`
- `0x1016c6d00`
- `0x1016c7de0`
- `0x1016c8370`
- `0x1016d4350`
- `0x1016f5750`
- `0x101711430`
- `0x1017159c0`
- `0x101715b00`
- `0x101729280`
- `0x1017296d0`
- `0x101729810`
- `0x10172cc60`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10172a035`
- `KERNEL32!QueryPerformanceCounter` at `0x10172a0fb`
- `KERNEL32!QueryPerformanceCounter` at `0x10172a8f2`
- `KERNEL32!QueryPerformanceCounter` at `0x10172a9b8`
- `KERNEL32!QueryPerformanceCounter` at `0x10172b485`
- `KERNEL32!QueryPerformanceCounter` at `0x10172b54b`
- `KERNEL32!QueryPerformanceCounter` at `0x10172b995`
- `KERNEL32!QueryPerformanceCounter` at `0x10172ba68`
- `KERNEL32!QueryPerformanceCounter` at `0x10172be8b`
- `KERNEL32!QueryPerformanceCounter` at `0x10172bf51`
- `KERNEL32!QueryPerformanceCounter` at `0x10172a035`
- `KERNEL32!QueryPerformanceCounter` at `0x10172a0fb`
- `KERNEL32!QueryPerformanceCounter` at `0x10172a8f2`
- `KERNEL32!QueryPerformanceCounter` at `0x10172a9b8`
- `KERNEL32!QueryPerformanceCounter` at `0x10172b485`
- `KERNEL32!QueryPerformanceCounter` at `0x10172b54b`
- `KERNEL32!QueryPerformanceCounter` at `0x10172b995`
- `KERNEL32!QueryPerformanceCounter` at `0x10172ba68`
- `KERNEL32!QueryPerformanceCounter` at `0x10172be8b`
- `KERNEL32!QueryPerformanceCounter` at `0x10172bf51`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x10172a4d8`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x10172a4d8`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10172c7c5`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10172a1bd`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10172aaa2`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10172b603`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10172bb18`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10172c001`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101729f8c`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10172a849`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10172b3dc`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10172b8cb`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10172bde2`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10172a08f`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10172a94c`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10172b4df`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10172b9fc`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10172bee5`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10172a019`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10172a0df`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10172a8d6`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10172a99c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10172b469`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10172b52f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10172b979`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10172ba4c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10172be6f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10172bf35`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10172b049`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10172b070`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x10172c154`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x10172c2d7`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10172a2de`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10172a30f`
- `sqldk!?GetDeadlockPriority@SOS_Task@@QEBA?AW4TASK_DEADLOCK_PRIORITY@1@XZ` at `0x10172b2be`
- `sqldk!?GetDeadlockPriority@SOS_Task@@QEBA?AW4TASK_DEADLOCK_PRIORITY@1@XZ` at `0x10172b2be`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101729dfe`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10172bd0d`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10172caee`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101729dfe`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10172bd0d`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10172caee`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x101729954`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10172ad8d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10172ad8d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101729bec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101729c47`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10172c4ff`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101729bec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101729c47`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10172c4ff`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101729ea2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101729ee1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10172a76f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10172abfc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10172b09c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10172ca25`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101729ea2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101729ee1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10172a76f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10172abfc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10172b09c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10172ca25`
- `sqldk!SystemThread_TlsIndex` at `0x10172996c`
- `sqldk!SystemThread_TlsIndex` at `0x1017299b5`
- `sqldk!SystemThread_TlsIndex` at `0x101729da6`
- `sqldk!SystemThread_TlsIndex` at `0x101729fbc`
- `sqldk!SystemThread_TlsIndex` at `0x10172a5aa`
- `sqldk!SystemThread_TlsIndex` at `0x10172a879`
- `sqldk!SystemThread_TlsIndex` at `0x10172b153`
- `sqldk!SystemThread_TlsIndex` at `0x10172b268`
- `sqldk!SystemThread_TlsIndex` at `0x10172b40c`
- `sqldk!SystemThread_TlsIndex` at `0x10172b703`
- `sqldk!SystemThread_TlsIndex` at `0x10172b7c8`
- `sqldk!SystemThread_TlsIndex` at `0x10172b909`
- `sqldk!SystemThread_TlsIndex` at `0x10172bbc2`
- `sqldk!SystemThread_TlsIndex` at `0x10172bcb5`
- `sqldk!SystemThread_TlsIndex` at `0x10172be12`
- `sqldk!SystemThread_TlsIndex` at `0x10172c10c`
- `sqldk!SystemThread_TlsIndex` at `0x10172c28f`
- `sqldk!SystemThread_TlsIndex` at `0x10172c44a`
- `sqldk!SystemThread_TlsIndex` at `0x10172c483`
- `sqldk!SystemThread_TlsIndex` at `0x10172c9b2`
- `sqldk!SystemThread_TlsIndex` at `0x10172ca65`
- `sqldk!SystemThread_TlsIndex` at `0x10172cab6`
- `sqldk!SystemThread_TlsIndex` at `0x10172cb0e`
- `sqldk!SystemThread_TlsOffset` at `0x101729975`
- `sqldk!SystemThread_TlsOffset` at `0x1017299be`
- `sqldk!SystemThread_TlsOffset` at `0x101729daf`
- `sqldk!SystemThread_TlsOffset` at `0x101729fc5`
- `sqldk!SystemThread_TlsOffset` at `0x10172a5b3`
- `sqldk!SystemThread_TlsOffset` at `0x10172a882`
- `sqldk!SystemThread_TlsOffset` at `0x10172b15c`
- `sqldk!SystemThread_TlsOffset` at `0x10172b271`
- `sqldk!SystemThread_TlsOffset` at `0x10172b415`
- `sqldk!SystemThread_TlsOffset` at `0x10172b70c`
- `sqldk!SystemThread_TlsOffset` at `0x10172b7d1`
- `sqldk!SystemThread_TlsOffset` at `0x10172b912`
- `sqldk!SystemThread_TlsOffset` at `0x10172bbcb`
- `sqldk!SystemThread_TlsOffset` at `0x10172bcbe`
- `sqldk!SystemThread_TlsOffset` at `0x10172be1b`
- `sqldk!SystemThread_TlsOffset` at `0x10172c115`
- `sqldk!SystemThread_TlsOffset` at `0x10172c298`
- `sqldk!SystemThread_TlsOffset` at `0x10172c453`
- `sqldk!SystemThread_TlsOffset` at `0x10172c48c`
- `sqldk!SystemThread_TlsOffset` at `0x10172c9bb`
- `sqldk!SystemThread_TlsOffset` at `0x10172ca6e`
- `sqldk!SystemThread_TlsOffset` at `0x10172cabf`
- `sqldk!SystemThread_TlsOffset` at `0x10172cb17`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10172cb6c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10172cb9b`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10172cb6c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10172cb9b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1017299de`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101729dd8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10172a5dc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10172b29a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10172bbf6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10172bce7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10172c12e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10172c2b1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10172cad8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1017299de`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101729dd8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10172a5dc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10172b29a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10172bbf6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10172bce7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10172c12e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10172c2b1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10172cad8`
- `sqldk!??_V@YAXPEAX@Z` at `0x10172a653`
- `sqldk!??_V@YAXPEAX@Z` at `0x10172c359`
- `sqldk!??_V@YAXPEAX@Z` at `0x10172a653`
- `sqldk!??_V@YAXPEAX@Z` at `0x10172c359`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10172a424`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10172a424`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10172a430`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10172a430`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10172a1d2`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10172aab7`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10172b618`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10172bb2d`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10172c016`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10172a1d2`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10172aab7`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10172b618`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10172bb2d`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10172c016`
- `sqllang!?UnInitialize@AutoOverrideMsqlXact@@QEAAXXZ` at `0x10172c741`
- `sqllang!?UnInitialize@AutoOverrideMsqlXact@@QEAAXXZ` at `0x10172c741`
- `sqllang!??0CSECDEK@@QEAA@PEBEKPEAVIMemObj@@K@Z` at `0x10172adc1`
- `sqllang!??0CSECDEK@@QEAA@PEBEKPEAVIMemObj@@K@Z` at `0x10172adc1`
- `sqllang!?Initialize@CSECDEK@@QEAAXKHHU_GUID@@_N@Z` at `0x10172ae0a`
- `sqllang!?Initialize@CSECDEK@@QEAAXKHHU_GUID@@_N@Z` at `0x10172ae0a`
- `sqllang!?InitializeAndOverride@AutoOverrideMsqlXact@@QEAAXXZ` at `0x10172c434`
- `sqllang!?InitializeAndOverride@AutoOverrideMsqlXact@@QEAAXXZ` at `0x10172c434`
- `sqllang!??1AutoOverrideMsqlXact@@QEAA@XZ` at `0x10172c76a`
- `sqllang!??1AutoOverrideMsqlXact@@QEAA@XZ` at `0x10172c76a`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x10172aebf`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x10172aebf`
- `sqlfabric!ReadFabricProperty` at `0x10172a617`
- `sqlfabric!ReadFabricProperty` at `0x10172a617`

## string_xrefs

- `0x10172a55b`: `Copying dbt_inactiveDurationMin %d, dbt_deactivationCount %d, dbt_lastDeactivationDate %s, dbt_deactivationIntervalMin %d, dbt_needToAdjustInterval %d from bootpage.`
- `0x101729be3`: `RemapFileEntry::RfeMove == remapAction`
- `0x10172c4f6`: `rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=24 #try_helpers=1
void __fastcall DBTABLE::Startup(DBTABLE *this, struct BaseXact *a2, struct DatabaseStartupInfo *a3)
{
  struct DatabaseStartupInfo *v3; // r13
  DBTABLE *v4; // r15
  int (*v5)(int, int, int, int, char *); // r12
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rdx
  int v10; // ecx
  _OWORD *v11; // rax
  struct DatabaseStartupInfo *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rdx
  int v15; // ecx
  __int64 v16; // rcx
  char v17; // al
  wchar_t *v18; // rdi
  struct FCB *v19; // r14
  __int64 v20; // rdi
  struct Worker *v21; // rcx
  __int64 v22; // rax
  RecoveryUnit *v23; // rcx
  _QWORD *v24; // r13
  __int64 v25; // rdi
  bool v26; // zf
  __int64 v27; // rdi
  __int64 v28; // rdi
  DirtyPageMgr *QuadPart; // rax
  DirtyPageMgr *v30; // rax
  signed __int64 v31; // rax
  int v32; // r8d
  _BYTE *v33; // rcx
  int v34; // edi
  int v35; // eax
  __int64 v36; // rcx
  int v37; // eax
  int v38; // edx
  int v39; // eax
  wchar_t *v40; // r9
  __int64 v41; // rdi
  __int64 v42; // rcx
  struct RecoveryUnit *v43; // rcx
  __int64 v44; // rdx
  struct HaDrDbMgr *DbMgr; // rax
  BOOL v46; // edi
  __int64 v47; // rdi
  __int64 v48; // rdi
  __int64 v49; // rdi
  DirtyPageMgr *v50; // rax
  DirtyPageMgr *v51; // rax
  signed __int64 v52; // rax
  int v53; // r8d
  int v54; // eax
  __int16 v55; // dx
  int v56; // ecx
  __int64 v57; // rdx
  __int64 v58; // rcx
  CSECDEK *v59; // rax
  CSECDEK *v60; // rax
  RecoveryUnit *v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rdi
  char v64; // cl
  struct BaseXact *v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rdi
  __int64 v68; // rcx
  int v69; // eax
  struct RecoveryUnit *v70; // rcx
  __int64 v71; // rdi
  __int64 v72; // rdi
  __int64 v73; // rdi
  DirtyPageMgr *v74; // rax
  DirtyPageMgr *v75; // rax
  signed __int64 v76; // rax
  int v77; // r8d
  BOOL v78; // ecx
  __int64 v79; // rdi
  __int64 v80; // rdi
  __int64 v82; // rdi
  DirtyPageMgr *v83; // rax
  DirtyPageMgr *v84; // rax
  signed __int64 v85; // rax
  int v86; // r8d
  __int64 v87; // rdi
  __int64 v88; // rax
  __int64 v89; // r13
  __int64 v90; // rdi
  struct Worker *v91; // rcx
  struct CSECDEK *v92; // rdx
  __int64 v93; // rdi
  __int64 v94; // rdi
  __int64 v95; // rdi
  DirtyPageMgr *v96; // rax
  DirtyPageMgr *v97; // rax
  signed __int64 v98; // rax
  int v99; // r8d
  __int64 v100; // rdi
  __int64 v101; // rcx
  __int64 v102; // rdi
  __int64 v103; // r14
  int v104; // eax
  __int64 v105; // rcx
  int v106; // eax
  __int64 v107; // rcx
  __int64 v108; // rdi
  __int64 v109; // rcx
  __int64 v110; // r14
  __int64 v111; // rax
  wchar_t *v112; // rax
  wchar_t *v113; // rdi
  __int64 v114; // rcx
  _BYTE *v115; // rax
  char v116; // di
  struct XDES *v117; // r14
  struct IFidoGLMController *FidoGLMController; // rax
  unsigned __int16 v119; // ax
  struct IFidoLockManagerClient *FidoLockManagerClient; // rsi
  __int64 v121; // rdi
  struct DWFidoTxCtx *DWFidoTxCtx; // rax
  char v123; // cl
  int v124; // eax
  unsigned int v125; // ecx
  __int64 v126; // rsi
  __int64 v127; // rsi
  __int64 v128; // rdi
  struct Worker *v129; // rcx
  __int64 v130; // rbx
  __int64 v131; // rcx
  const struct SQLError *CurrentException; // rax
  int (*v133)(int, int, int, int, char *); // [rsp+20h] [rbp-14A8h]
  int (*v134)(int, int, int, int, char *); // [rsp+20h] [rbp-14A8h]
  int (*v135)(int, int, int, int, char *); // [rsp+20h] [rbp-14A8h]
  struct Worker *v136; // [rsp+28h] [rbp-14A0h]
  __int64 v137; // [rsp+30h] [rbp-1498h]
  char v138; // [rsp+51h] [rbp-1477h] BYREF
  char v139; // [rsp+52h] [rbp-1476h]
  char *v140; // [rsp+58h] [rbp-1470h]
  struct BaseXact *v141; // [rsp+60h] [rbp-1468h]
  __int64 v142; // [rsp+68h] [rbp-1460h]
  __int64 v143; // [rsp+70h] [rbp-1458h]
  bool v144; // [rsp+78h] [rbp-1450h]
  unsigned __int8 v146; // [rsp+80h] [rbp-1448h]
  char v147; // [rsp+88h] [rbp-1440h]
  unsigned __int8 v148; // [rsp+89h] [rbp-143Fh]
  char v149; // [rsp+8Ah] [rbp-143Eh]
  unsigned __int8 v150; // [rsp+8Bh] [rbp-143Dh]
  char v151; // [rsp+8Ch] [rbp-143Ch]
  char v152; // [rsp+8Dh] [rbp-143Bh]
  bool v153; // [rsp+8Eh] [rbp-143Ah]
  char v154; // [rsp+8Fh] [rbp-1439h]
  char v155; // [rsp+90h] [rbp-1438h]
  char v156; // [rsp+91h] [rbp-1437h]
  char v157; // [rsp+92h] [rbp-1436h]
  char v158; // [rsp+93h] [rbp-1435h]
  _DWORD v159[2]; // [rsp+98h] [rbp-1430h] BYREF
  int v160; // [rsp+A0h] [rbp-1428h] BYREF
  char v161; // [rsp+A4h] [rbp-1424h]
  bool v162; // [rsp+A5h] [rbp-1423h]
  char v163; // [rsp+A6h] [rbp-1422h]
  char v164; // [rsp+A7h] [rbp-1421h]
  volatile signed __int64 *v165; // [rsp+A8h] [rbp-1420h]
  unsigned int SourceSize; // [rsp+B0h] [rbp-1418h] BYREF
  int SourceSize_4; // [rsp+B4h] [rbp-1414h] BYREF
  int v168; // [rsp+B8h] [rbp-1410h]
  struct DatabaseStartupInfo *UniqueThread_low; // [rsp+C0h] [rbp-1408h]
  char *v170; // [rsp+C8h] [rbp-1400h]
  volatile signed __int64 *v171; // [rsp+D8h] [rbp-13F0h]
  volatile signed __int64 *v172; // [rsp+E0h] [rbp-13E8h]
  volatile signed __int64 *v173; // [rsp+E8h] [rbp-13E0h]
  _DWORD v174[2]; // [rsp+F0h] [rbp-13D8h] BYREF
  struct FCB *v175; // [rsp+F8h] [rbp-13D0h]
  DBTABLE *v176; // [rsp+100h] [rbp-13C8h]
  volatile signed __int64 *v177; // [rsp+108h] [rbp-13C0h]
  int v178; // [rsp+128h] [rbp-13A0h] BYREF
  int v179; // [rsp+12Ch] [rbp-139Ch] BYREF
  int v180; // [rsp+130h] [rbp-1398h]
  __int128 v181; // [rsp+138h] [rbp-1390h]
  int v182; // [rsp+148h] [rbp-1380h]
  __int64 v183; // [rsp+150h] [rbp-1378h]
  __int16 v184; // [rsp+158h] [rbp-1370h]
  int v185; // [rsp+160h] [rbp-1368h]
  int v186; // [rsp+164h] [rbp-1364h]
  int v187; // [rsp+168h] [rbp-1360h]
  BOOL v188; // [rsp+16Ch] [rbp-135Ch]
  int v189; // [rsp+170h] [rbp-1358h]
  int v190; // [rsp+174h] [rbp-1354h]
  int v191; // [rsp+178h] [rbp-1350h]
  BOOL v192; // [rsp+17Ch] [rbp-134Ch]
  unsigned int v193; // [rsp+180h] [rbp-1348h]
  int v194; // [rsp+184h] [rbp-1344h] BYREF
  BOOL v195; // [rsp+188h] [rbp-1340h]
  __int64 v196; // [rsp+190h] [rbp-1338h] BYREF
  BOOL v197; // [rsp+198h] [rbp-1330h]
  __int64 v198; // [rsp+1A0h] [rbp-1328h] BYREF
  unsigned int v199; // [rsp+1A8h] [rbp-1320h]
  __int64 v200; // [rsp+1B0h] [rbp-1318h]
  DirtyPageMgr *v201; // [rsp+1B8h] [rbp-1310h] BYREF
  DirtyPageMgr *v202; // [rsp+1C0h] [rbp-1308h] BYREF
  void *Source; // [rsp+1C8h] [rbp-1300h] BYREF
  signed __int64 v204; // [rsp+1D0h] [rbp-12F8h]
  __int64 v205; // [rsp+1D8h] [rbp-12F0h]
  DirtyPageMgr *v206; // [rsp+1E0h] [rbp-12E8h] BYREF
  DirtyPageMgr *v207; // [rsp+1E8h] [rbp-12E0h] BYREF
  signed __int64 v208; // [rsp+1F0h] [rbp-12D8h]
  DirtyPageMgr *v209; // [rsp+1F8h] [rbp-12D0h] BYREF
  DirtyPageMgr *v210; // [rsp+200h] [rbp-12C8h] BYREF
  signed __int64 v211; // [rsp+208h] [rbp-12C0h]
  __int64 v212; // [rsp+210h] [rbp-12B8h]
  DirtyPageMgr *v213; // [rsp+218h] [rbp-12B0h] BYREF
  DirtyPageMgr *v214; // [rsp+220h] [rbp-12A8h] BYREF
  signed __int64 v215; // [rsp+228h] [rbp-12A0h]
  __int64 v216; // [rsp+230h] [rbp-1298h]
  DirtyPageMgr *v217; // [rsp+238h] [rbp-1290h] BYREF
  DirtyPageMgr *v218; // [rsp+240h] [rbp-1288h] BYREF
  __int64 v219; // [rsp+248h] [rbp-1280h]
  __int64 v220; // [rsp+250h] [rbp-1278h] BYREF
  __int16 v221; // [rsp+258h] [rbp-1270h]
  __int16 v222; // [rsp+25Ah] [rbp-126Eh]
  _DWORD v223[3]; // [rsp+260h] [rbp-1268h] BYREF
  unsigned __int16 v224; // [rsp+26Ch] [rbp-125Ch]
  char v225; // [rsp+26Eh] [rbp-125Ah]
  __int64 v226; // [rsp+270h] [rbp-1258h]
  DirtyPageMgr *v227; // [rsp+278h] [rbp-1250h] BYREF
  DirtyPageMgr *v228; // [rsp+280h] [rbp-1248h] BYREF
  DirtyPageMgr *v229; // [rsp+288h] [rbp-1240h] BYREF
  DirtyPageMgr *v230; // [rsp+290h] [rbp-1238h] BYREF
  DirtyPageMgr *v231; // [rsp+298h] [rbp-1230h] BYREF
  __int64 v232; // [rsp+2A0h] [rbp-1228h]
  __int64 v233; // [rsp+2A8h] [rbp-1220h]
  __int64 v234; // [rsp+2B0h] [rbp-1218h]
  __int64 v235; // [rsp+2B8h] [rbp-1210h] BYREF
  __int16 v236; // [rsp+2C0h] [rbp-1208h]
  BOOL v237; // [rsp+2C8h] [rbp-1200h]
  int v238; // [rsp+2CCh] [rbp-11FCh]
  int v239; // [rsp+2D0h] [rbp-11F8h]
  int v240; // [rsp+2D4h] [rbp-11F4h]
  int v241; // [rsp+2D8h] [rbp-11F0h]
  int v242; // [rsp+2DCh] [rbp-11ECh]
  BOOL v243; // [rsp+2E0h] [rbp-11E8h]
  int v244; // [rsp+2E4h] [rbp-11E4h]
  int v245; // [rsp+2E8h] [rbp-11E0h]
  BOOL v246; // [rsp+2ECh] [rbp-11DCh]
  int v247; // [rsp+2F0h] [rbp-11D8h]
  int v248; // [rsp+2F8h] [rbp-11D0h]
  int v249; // [rsp+300h] [rbp-11C8h]
  unsigned int v250; // [rsp+304h] [rbp-11C4h]
  int v251; // [rsp+308h] [rbp-11C0h]
  int v252; // [rsp+30Ch] [rbp-11BCh]
  int v254; // [rsp+314h] [rbp-11B4h]
  int v255; // [rsp+318h] [rbp-11B0h]
  int v256; // [rsp+31Ch] [rbp-11ACh]
  int v257; // [rsp+320h] [rbp-11A8h]
  BOOL v258; // [rsp+324h] [rbp-11A4h]
  int v259; // [rsp+328h] [rbp-11A0h]
  int v260; // [rsp+32Ch] [rbp-119Ch]
  BOOL v261; // [rsp+330h] [rbp-1198h]
  int v262; // [rsp+334h] [rbp-1194h]
  BOOL v263; // [rsp+338h] [rbp-1190h]
  int v264; // [rsp+33Ch] [rbp-118Ch]
  int v265; // [rsp+340h] [rbp-1188h]
  BOOL v266; // [rsp+344h] [rbp-1184h]
  int v267; // [rsp+348h] [rbp-1180h]
  int v268; // [rsp+34Ch] [rbp-117Ch]
  BOOL v269; // [rsp+350h] [rbp-1178h]
  int v270; // [rsp+354h] [rbp-1174h]
  int v271; // [rsp+358h] [rbp-1170h]
  int v272; // [rsp+35Ch] [rbp-116Ch]
  int v273; // [rsp+360h] [rbp-1168h]
  int v274; // [rsp+364h] [rbp-1164h]
  BOOL v275; // [rsp+368h] [rbp-1160h]
  int v276; // [rsp+36Ch] [rbp-115Ch]
  int v277; // [rsp+370h] [rbp-1158h]
  BOOL v278; // [rsp+374h] [rbp-1154h]
  int v279; // [rsp+378h] [rbp-1150h]
  __int64 v280; // [rsp+380h] [rbp-1148h] BYREF
  wchar_t *v281; // [rsp+388h] [rbp-1140h] BYREF
  __int64 v282; // [rsp+390h] [rbp-1138h] BYREF
  struct Worker *v283; // [rsp+398h] [rbp-1130h]
  LARGE_INTEGER PerformanceCount; // [rsp+3A0h] [rbp-1128h] BYREF
  DirtyPageMgr *v285; // [rsp+3A8h] [rbp-1120h]
  LARGE_INTEGER v286; // [rsp+3B0h] [rbp-1118h] BYREF
  DirtyPageMgr *v287; // [rsp+3B8h] [rbp-1110h]
  __int64 v288; // [rsp+3C0h] [rbp-1108h]
  __int64 v289; // [rsp+3C8h] [rbp-1100h]
  struct HaDrDbMgr *v290; // [rsp+3D0h] [rbp-10F8h]
  LARGE_INTEGER v291; // [rsp+3D8h] [rbp-10F0h] BYREF
  DirtyPageMgr *v292; // [rsp+3E0h] [rbp-10E8h]
  LARGE_INTEGER v293; // [rsp+3E8h] [rbp-10E0h] BYREF
  DirtyPageMgr *v294; // [rsp+3F0h] [rbp-10D8h]
  __int64 v295; // [rsp+3F8h] [rbp-10D0h]
  LARGE_INTEGER v296; // [rsp+400h] [rbp-10C8h] BYREF
  DirtyPageMgr *v297; // [rsp+408h] [rbp-10C0h]
  LARGE_INTEGER v298; // [rsp+410h] [rbp-10B8h] BYREF
  DirtyPageMgr *v299; // [rsp+418h] [rbp-10B0h]
  LARGE_INTEGER v300; // [rsp+420h] [rbp-10A8h] BYREF
  LARGE_INTEGER v301; // [rsp+428h] [rbp-10A0h] BYREF
  __int64 v302; // [rsp+430h] [rbp-1098h]
  struct Worker *v303; // [rsp+438h] [rbp-1090h]
  LARGE_INTEGER v304; // [rsp+440h] [rbp-1088h] BYREF
  DirtyPageMgr *v305; // [rsp+448h] [rbp-1080h]
  LARGE_INTEGER v306; // [rsp+450h] [rbp-1078h] BYREF
  DirtyPageMgr *v307; // [rsp+458h] [rbp-1070h]
  int v308; // [rsp+460h] [rbp-1068h]
  int v309; // [rsp+464h] [rbp-1064h]
  int v310; // [rsp+468h] [rbp-1060h]
  int v311; // [rsp+46Ch] [rbp-105Ch]
  BOOL v312; // [rsp+470h] [rbp-1058h]
  int v313; // [rsp+474h] [rbp-1054h]
  int v314; // [rsp+478h] [rbp-1050h]
  BOOL v315; // [rsp+47Ch] [rbp-104Ch]
  __int128 v316; // [rsp+480h] [rbp-1048h]
  __int128 v317; // [rsp+490h] [rbp-1038h]
  __int128 v318; // [rsp+4A0h] [rbp-1028h]
  __int128 v319; // [rsp+4B0h] [rbp-1018h]
  __int64 v320; // [rsp+4C0h] [rbp-1008h]
  _BYTE v321[16]; // [rsp+4D0h] [rbp-FF8h] BYREF
  __int128 v322; // [rsp+4E0h] [rbp-FE8h] BYREF
  __int64 v323; // [rsp+4F0h] [rbp-FD8h]
  int v324; // [rsp+4FCh] [rbp-FCCh]
  _BYTE v325[80]; // [rsp+500h] [rbp-FC8h] BYREF
  signed __int64 v326; // [rsp+550h] [rbp-F78h]
  signed __int64 v327; // [rsp+558h] [rbp-F70h]
  _QWORD *v328; // [rsp+560h] [rbp-F68h]
  __int64 v329; // [rsp+568h] [rbp-F60h]
  __int64 v330; // [rsp+570h] [rbp-F58h]
  DirtyPageMgr **v331; // [rsp+578h] [rbp-F50h]
  DirtyPageMgr *v332; // [rsp+580h] [rbp-F48h]
  DirtyPageMgr **v333; // [rsp+588h] [rbp-F40h]
  DirtyPageMgr **v334; // [rsp+590h] [rbp-F38h]
  DirtyPageMgr **v335; // [rsp+598h] [rbp-F30h]
  char *v336; // [rsp+5A0h] [rbp-F28h]
  __int64 v337; // [rsp+5A8h] [rbp-F20h]
  char *v338; // [rsp+5B0h] [rbp-F18h]
  char *v339; // [rsp+5B8h] [rbp-F10h]
  __int64 *v340; // [rsp+5C0h] [rbp-F08h]
  char *v341; // [rsp+5C8h] [rbp-F00h]
  unsigned __int64 v342; // [rsp+5D0h] [rbp-EF8h]
  _QWORD *v343; // [rsp+5D8h] [rbp-EF0h]
  __int64 v344; // [rsp+5E0h] [rbp-EE8h]
  __int64 v345; // [rsp+5E8h] [rbp-EE0h]
  void *v346; // [rsp+5F0h] [rbp-ED8h]
  struct RecoveryUnit *v347; // [rsp+5F8h] [rbp-ED0h]
  __int64 v348; // [rsp+600h] [rbp-EC8h]
  struct HaDrDbMgr *v349; // [rsp+608h] [rbp-EC0h]
  __int64 v350; // [rsp+610h] [rbp-EB8h]
  __int64 v351; // [rsp+618h] [rbp-EB0h]
  char *v352; // [rsp+620h] [rbp-EA8h]
  signed __int64 v353; // [rsp+628h] [rbp-EA0h]
  signed __int64 v354; // [rsp+630h] [rbp-E98h]
  _QWORD *v355; // [rsp+638h] [rbp-E90h]
  __int64 v356; // [rsp+640h] [rbp-E88h]
  __int64 v357; // [rsp+648h] [rbp-E80h]
  DirtyPageMgr **v358; // [rsp+650h] [rbp-E78h]
  DirtyPageMgr *v359; // [rsp+658h] [rbp-E70h]
  DirtyPageMgr **v360; // [rsp+660h] [rbp-E68h]
  DirtyPageMgr **v361; // [rsp+668h] [rbp-E60h]
  DirtyPageMgr **v362; // [rsp+670h] [rbp-E58h]
  char *v363; // [rsp+678h] [rbp-E50h]
  __int64 v364; // [rsp+680h] [rbp-E48h]
  char *v365; // [rsp+688h] [rbp-E40h]
  char *v366; // [rsp+690h] [rbp-E38h]
  char *v367; // [rsp+698h] [rbp-E30h]
  __int64 v368; // [rsp+6A0h] [rbp-E28h]
  __int64 FCB; // [rsp+6A8h] [rbp-E20h]
  unsigned __int8 *v370; // [rsp+6B0h] [rbp-E18h]
  CSECDEK *v371; // [rsp+6B8h] [rbp-E10h]
  CSECDEK *v372; // [rsp+6C0h] [rbp-E08h]
  _BYTE *v373; // [rsp+6C8h] [rbp-E00h]
  _BYTE *v374; // [rsp+6D0h] [rbp-DF8h]
  _BYTE *v375; // [rsp+6D8h] [rbp-DF0h]
  __int64 *v376; // [rsp+6E0h] [rbp-DE8h]
  __int64 *v377; // [rsp+6E8h] [rbp-DE0h]
  __int64 v378; // [rsp+6F0h] [rbp-DD8h]
  __int64 v379; // [rsp+6F8h] [rbp-DD0h]
  __int64 v380; // [rsp+700h] [rbp-DC8h]
  __int64 v381; // [rsp+708h] [rbp-DC0h]
  __int64 v382; // [rsp+710h] [rbp-DB8h]
  _QWORD *v383; // [rsp+718h] [rbp-DB0h]
  __int64 v384; // [rsp+720h] [rbp-DA8h]
  __int64 v385; // [rsp+728h] [rbp-DA0h]
  __int64 v386; // [rsp+730h] [rbp-D98h]
  __int64 v387; // [rsp+738h] [rbp-D90h]
  char *v388; // [rsp+740h] [rbp-D88h]
  signed __int64 v389; // [rsp+748h] [rbp-D80h]
  signed __int64 v390; // [rsp+750h] [rbp-D78h]
  _QWORD *v391; // [rsp+758h] [rbp-D70h]
  __int64 v392; // [rsp+760h] [rbp-D68h]
  __int64 v393; // [rsp+768h] [rbp-D60h]
  DirtyPageMgr **v394; // [rsp+770h] [rbp-D58h]
  DirtyPageMgr *v395; // [rsp+778h] [rbp-D50h]
  DirtyPageMgr **v396; // [rsp+780h] [rbp-D48h]
  DirtyPageMgr **v397; // [rsp+788h] [rbp-D40h]
  DirtyPageMgr **v398; // [rsp+790h] [rbp-D38h]
  char *v399; // [rsp+798h] [rbp-D30h]
  __int64 v400; // [rsp+7A0h] [rbp-D28h]
  char *v401; // [rsp+7A8h] [rbp-D20h]
  char *v402; // [rsp+7B0h] [rbp-D18h]
  __int64 v403; // [rsp+7B8h] [rbp-D10h]
  __int64 v404; // [rsp+7C0h] [rbp-D08h]
  __int64 v405; // [rsp+7C8h] [rbp-D00h]
  char *v406; // [rsp+7D0h] [rbp-CF8h]
  signed __int64 v407; // [rsp+7D8h] [rbp-CF0h]
  signed __int64 v408; // [rsp+7E0h] [rbp-CE8h]
  _QWORD *v409; // [rsp+7E8h] [rbp-CE0h]
  __int64 v410; // [rsp+7F0h] [rbp-CD8h]
  DirtyPageMgr **v411; // [rsp+7F8h] [rbp-CD0h]
  DirtyPageMgr *v412; // [rsp+800h] [rbp-CC8h]
  DirtyPageMgr *v413; // [rsp+808h] [rbp-CC0h]
  DirtyPageMgr **v414; // [rsp+810h] [rbp-CB8h]
  DirtyPageMgr *v415; // [rsp+818h] [rbp-CB0h]
  DirtyPageMgr **v416; // [rsp+820h] [rbp-CA8h]
  DirtyPageMgr **v417; // [rsp+828h] [rbp-CA0h]
  char *v418; // [rsp+830h] [rbp-C98h]
  __int64 v419; // [rsp+838h] [rbp-C90h]
  char *v420; // [rsp+840h] [rbp-C88h]
  char *v421; // [rsp+848h] [rbp-C80h]
  _QWORD *v422; // [rsp+850h] [rbp-C78h]
  __int64 v423; // [rsp+858h] [rbp-C70h]
  __int64 v424; // [rsp+860h] [rbp-C68h]
  __int64 v425; // [rsp+868h] [rbp-C60h]
  __int64 v426; // [rsp+870h] [rbp-C58h]
  _QWORD *v427; // [rsp+878h] [rbp-C50h]
  __int64 v428; // [rsp+880h] [rbp-C48h]
  struct Worker *v429; // [rsp+888h] [rbp-C40h]
  __int64 v430; // [rsp+890h] [rbp-C38h]
  __int64 v431; // [rsp+898h] [rbp-C30h]
  char *v432; // [rsp+8A0h] [rbp-C28h]
  signed __int64 v433; // [rsp+8A8h] [rbp-C20h]
  signed __int64 v434; // [rsp+8B0h] [rbp-C18h]
  _QWORD *v435; // [rsp+8B8h] [rbp-C10h]
  __int64 v436; // [rsp+8C0h] [rbp-C08h]
  __int64 v437; // [rsp+8C8h] [rbp-C00h]
  DirtyPageMgr **v438; // [rsp+8D0h] [rbp-BF8h]
  DirtyPageMgr *v439; // [rsp+8D8h] [rbp-BF0h]
  DirtyPageMgr **v440; // [rsp+8E0h] [rbp-BE8h]
  DirtyPageMgr **v441; // [rsp+8E8h] [rbp-BE0h]
  DirtyPageMgr **v442; // [rsp+8F0h] [rbp-BD8h]
  char *v443; // [rsp+8F8h] [rbp-BD0h]
  __int64 v444; // [rsp+900h] [rbp-BC8h]
  char *v445; // [rsp+908h] [rbp-BC0h]
  char *v446; // [rsp+910h] [rbp-BB8h]
  __int64 v447; // [rsp+918h] [rbp-BB0h]
  char v448[8]; // [rsp+920h] [rbp-BA8h] BYREF
  __int64 v449; // [rsp+928h] [rbp-BA0h]
  __int64 v450; // [rsp+930h] [rbp-B98h]
  __int64 v451; // [rsp+938h] [rbp-B90h]
  __int64 v452; // [rsp+940h] [rbp-B88h]
  __int64 v453; // [rsp+948h] [rbp-B80h]
  __int64 v454; // [rsp+950h] [rbp-B78h]
  __int64 v455; // [rsp+958h] [rbp-B70h]
  _BYTE v456[16]; // [rsp+960h] [rbp-B68h] BYREF
  GUID v457; // [rsp+970h] [rbp-B58h] BYREF
  _QWORD *ThreadLocalStoragePointer; // [rsp+990h] [rbp-B38h]
  __int64 v459; // [rsp+998h] [rbp-B30h]
  __int64 v460; // [rsp+9A0h] [rbp-B28h]
  __int64 v461; // [rsp+9A8h] [rbp-B20h]
  __int64 v462; // [rsp+9B0h] [rbp-B18h]
  struct Worker *v463; // [rsp+9B8h] [rbp-B10h]
  _DWORD v464[8]; // [rsp+9C0h] [rbp-B08h] BYREF
  _OWORD v465[4]; // [rsp+9E0h] [rbp-AE8h] BYREF
  __int64 v466; // [rsp+A20h] [rbp-AA8h]
  _BYTE v467[24]; // [rsp+A30h] [rbp-A98h] BYREF
  _BYTE v468[40]; // [rsp+A48h] [rbp-A80h] BYREF
  int v469; // [rsp+A70h] [rbp-A58h]
  int v470; // [rsp+A74h] [rbp-A54h]
  int v471; // [rsp+A78h] [rbp-A50h]
  unsigned __int16 v472; // [rsp+A7Ch] [rbp-A4Ch]
  char v473; // [rsp+A7Eh] [rbp-A4Ah]
  int v474; // [rsp+A80h] [rbp-A48h] BYREF
  __int64 v475; // [rsp+A88h] [rbp-A40h] BYREF
  char v476; // [rsp+A90h] [rbp-A38h]
  int v477; // [rsp+A94h] [rbp-A34h]
  __int128 v478; // [rsp+AA0h] [rbp-A28h]
  __int64 v479; // [rsp+AB0h] [rbp-A18h]
  int v480; // [rsp+AB8h] [rbp-A10h]
  _BYTE v481[4]; // [rsp+AC0h] [rbp-A08h] BYREF
  unsigned __int16 v482; // [rsp+AC4h] [rbp-A04h]
  __int16 v483; // [rsp+AC6h] [rbp-A02h]
  int v484; // [rsp+AE4h] [rbp-9E4h]
  unsigned __int8 v485; // [rsp+BFAh] [rbp-8CEh]
  char v486; // [rsp+BFBh] [rbp-8CDh]
  char v487; // [rsp+C1Ah] [rbp-8AEh]
  int v488; // [rsp+C1Ch] [rbp-8ACh]
  int v489; // [rsp+C20h] [rbp-8A8h]
  __int16 v490; // [rsp+C24h] [rbp-8A4h]
  int v491; // [rsp+C40h] [rbp-888h]
  __int16 v492; // [rsp+C44h] [rbp-884h]
  int v493; // [rsp+C54h] [rbp-874h]
  __int64 v494; // [rsp+C7Ch] [rbp-84Ch]
  int v495; // [rsp+C84h] [rbp-844h]
  GUID v496; // [rsp+C88h] [rbp-840h]
  __int64 v497; // [rsp+C98h] [rbp-830h]
  int v498; // [rsp+CA0h] [rbp-828h]
  GUID v499; // [rsp+CA4h] [rbp-824h]
  int v500; // [rsp+CE4h] [rbp-7E4h]
  __int64 v501; // [rsp+D38h] [rbp-790h]
  __int64 v502; // [rsp+D4Ch] [rbp-77Ch]
  unsigned __int8 v503; // [rsp+D62h] [rbp-766h]
  int v504; // [rsp+D6Ch] [rbp-75Ch]
  unsigned __int8 v505[632]; // [rsp+DBCh] [rbp-70Ch] BYREF
  __int64 v506; // [rsp+1034h] [rbp-494h]
  __int64 v507; // [rsp+103Ch] [rbp-48Ch]
  __int64 v508; // [rsp+1044h] [rbp-484h]
  __int64 v509; // [rsp+104Ch] [rbp-47Ch]
  __int64 v510; // [rsp+1054h] [rbp-474h]
  __int64 v511; // [rsp+105Ch] [rbp-46Ch]
  __int64 v512; // [rsp+1078h] [rbp-450h]
  int v513; // [rsp+1084h] [rbp-444h]
  __int64 v514; // [rsp+10BCh] [rbp-40Ch]
  __int16 v515; // [rsp+10C4h] [rbp-404h]
  unsigned __int16 v516; // [rsp+10D2h] [rbp-3F6h]
  int v517; // [rsp+1110h] [rbp-3B8h]
  __int16 v518; // [rsp+1114h] [rbp-3B4h]
  __int16 v519; // [rsp+1116h] [rbp-3B2h]
  int v520; // [rsp+1118h] [rbp-3B0h]
  __int64 v521; // [rsp+111Ch] [rbp-3ACh] BYREF
  wchar_t v522[16]; // [rsp+11C0h] [rbp-308h] BYREF
  char v523[144]; // [rsp+11E0h] [rbp-2E8h] BYREF
  wchar_t v524[264]; // [rsp+1270h] [rbp-258h] BYREF

  v462 = -2;
  v3 = a3;
  v4 = this;
  v176 = this;
  v165 = (volatile signed __int64 *)this;
  v141 = a2;
  UniqueThread_low = a3;
  v474 = 0;
  v475 = 0;
  v476 = 0;
  v477 = 0;
  v479 = 0;
  v480 = 0;
  v478 = 0;
  v491 = 0;
  v492 = 0;
  v494 = 0;
  v495 = 0;
  v496 = GUID_NULL;
  v497 = 0;
  v498 = 0;
  v499 = GUID_NULL;
  v506 = 0;
  v507 = 0;
  v170 = 0;
  v508 = 0;
  v509 = 0;
  v510 = 0;
  v511 = 0;
  v512 = 0;
  v175 = 0;
  v168 = 0;
  v5 = hdl_prntbackout;
  v280 = 0;
  v6 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL)
                 + 96LL);
  v143 = *(_QWORD *)(v6 + 1272);
  v7 = v143;
  *(_QWORD *)(v6 + 1272) = v4;
  v450 = v7;
  v182 = 0;
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v9 = *(_QWORD *)(v8 + 256);
  v142 = v9;
  if ( !v9 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v9 = *(_QWORD *)(v8 + 256);
    v142 = v9;
  }
  v183 = v9;
  v10 = *(_DWORD *)(v9 + 616);
  v182 = !(*(_BYTE *)(v9 + 616) & 1);
  *(_DWORD *)(v9 + 616) = v10 | 1;
  *((_QWORD *)v3 + 5) = v141;
  v11 = (_OWORD *)((char *)v4 + 56);
  v12 = v3;
  v13 = 3;
  do
  {
    *v11 = *(_OWORD *)v12;
    v11[1] = *((_OWORD *)v12 + 1);
    v11[2] = *((_OWORD *)v12 + 2);
    v11[3] = *((_OWORD *)v12 + 3);
    v11[4] = *((_OWORD *)v12 + 4);
    v11[5] = *((_OWORD *)v12 + 5);
    v11[6] = *((_OWORD *)v12 + 6);
    v11 += 8;
    *(v11 - 1) = *((_OWORD *)v12 + 7);
    v12 = (struct DatabaseStartupInfo *)((char *)v12 + 128);
    --v13;
  }
  while ( v13 );
  *v11 = *(_OWORD *)v12;
  v11[1] = *((_OWORD *)v12 + 1);
  v11[2] = *((_OWORD *)v12 + 2);
  v11[3] = *((_OWORD *)v12 + 3);
  v11[4] = *((_OWORD *)v12 + 4);
  v11[5] = *((_OWORD *)v12 + 5);
  if ( (*((_BYTE *)v4 + 57) & 8) != 0 )
    v5 = (int (*)(int, int, int, int, char *))HandleAllAndPrintSpecificStartupErrors;
  ExcHandler::ExcHandler((ExcHandler *)v325, 0, 0, 0, v5, 0);
  v161 = byte_1031852E4;
  if ( !byte_1031852E4 || !*((_QWORD *)v4 + 665) )
    scierrlog(0x42F1u, *((unsigned int *)v4 + 232), (char *)v4 + 936);
  v14 = *((_QWORD *)v4 + 80);
  if ( v14 )
  {
    v15 = *(_DWORD *)(v14 + 632);
    v162 = (v15 & 0x2000) == 0;
    *(_DWORD *)(v14 + 632) = v15 | 0x2000;
    if ( (v15 & 0x2000) == 0 )
      BPool::MarkBufsCopyOnWrite(qword_10317B628, *(_QWORD *)(*((_QWORD *)v4 + 80) + 4624LL), 1);
  }
  RBPEX::NotifyDbStartup(*((_WORD *)v4 + 20), v4);
  v16 = *((_QWORD *)v4 + 17);
  v451 = v16;
  if ( v16 )
  {
    v185 = FileMgr::RemapLogicalFile(v16, 1, &GUID_NULL, &v280, &v281, &v282);
    if ( v185 == 1 )
      goto LABEL_17;
  }
  else
  {
    v185 = 0;
  }
  utassert_fail(1u, "RemapFileEntry::RfeMove == remapAction", "dbtable.cpp", 2329, 0);
LABEL_17:
  if ( (dword_103172528 || dword_1031852C8)
    && *((_QWORD *)v4 + 664)
    && *((_DWORD *)v3 + 2) == 2
    && *((char *)v3 + 3) >= 0
    && !RecoveryUnit::SetInfiniteLeaseIdsFromReplicaController(*((RecoveryUnit **)v4 + 578)) )
  {
    utassert_fail(1u, "GetPrimaryPru ()->SetInfiniteLeaseIdsFromReplicaController()", "dbtable.cpp", 2346, 0);
  }
  v17 = *((_BYTE *)v4 + 60);
  if ( (v17 & 4) != 0 )
  {
    RecoveryUnit::SetIsLogReplica(*((RecoveryUnit **)v4 + 578), 0);
    v17 = *((_BYTE *)v4 + 60);
  }
  if ( (v17 & 8) != 0 )
  {
    v452 = *((_QWORD *)v4 + 578);
    *(_BYTE *)(v452 + 7376) |= 0x40u;
  }
  v163 = byte_1031852E4;
  if ( !byte_1031852E4 || !*((_QWORD *)v4 + 665) )
  {
    v18 = v281;
    v19 = DBAllocFCB(*((struct IMemObj **)v4 + 86), v281, 0);
    v175 = v19;
    (*(void (__fastcall **)(struct FCB *, _QWORD, _QWORD, __int64, const wchar_t *, _QWORD, wchar_t *, __int64, int, int))(*(_QWORD *)v19 + 104LL))(
      v19,
      *((unsigned __int16 *)v4 + 20),
      0,
      1,
      &word_10280BED8,
      0,
      v18,
      v282,
      2,
      1);
    *((_WORD *)v19 + 66) = 1;
    v453 = 0;
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v468, 0, 0, 0, v5, 0);
      FCB::StartPrimaryFile(v19, (DBTABLE *)((char *)v4 + 56));
      v454 = *(_QWORD *)(*((_QWORD *)v4 + 578) + 1696LL);
      *(_DWORD *)(v454 + 136) |= 0x20u;
      ExcHandler::~ExcHandler((ExcHandler *)v468);
    }
    catch ( SQLError v464 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v456, (const struct SQLError *)v464);
        v187 = v464[0] / 100;
        v186 = v464[0] % 100;
        v168 = 1;
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v456);
      }
      catch ( ShortStackException )
      {
      }
      v4 = v176;
      v3 = UniqueThread_low;
    }
    v308 = 88;
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v20 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v460 = v20;
    v21 = *(struct Worker **)(v20 + 256);
    v283 = v21;
    if ( !v21 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v21 = *(struct Worker **)(v20 + 256);
      v283 = v21;
    }
    v463 = v21;
    if ( *((_DWORD *)v21 + 139) )
      ExceptionPostCatchActions(v21);
    FileMgr::SetFCB(*(FileMgr **)(*((_QWORD *)v4 + 578) + 1696LL), *((_WORD *)v175 + 16), v175);
    if ( v168 )
    {
      v22 = *((_QWORD *)v4 + 578);
      if ( (*((_BYTE *)v4 + 60) & 8) != 0 )
      {
        v455 = *((_QWORD *)v4 + 578);
        *(_BYTE *)(v22 + 7376) |= 0x40u;
        FileMgr::StartupPreRecovery(*(FileMgr **)(*((_QWORD *)v4 + 578) + 1696LL), v3);
      }
      else
      {
        v23 = (RecoveryUnit *)*((_QWORD *)v4 + 578);
        if ( *(_DWORD *)(v22 + 1776) && !*(_DWORD *)(v22 + 1780) )
        {
          ex_raise(90, 25, 16, 4, L"missing primary data file");
          v23 = (RecoveryUnit *)*((_QWORD *)v165 + 578);
        }
        RecoveryUnit::FixupForNoPrimary(v23, (DBTABLE *)((char *)v4 + 56), v141);
        *((_QWORD *)v4 + 17) = 0;
        ex_raise(v187, v186, 25, 0);
      }
    }
  }
  v24 = (_QWORD *)((char *)v4 + 5376);
  v165 = (volatile signed __int64 *)((char *)v4 + 5376);
  v459 = 0;
  v461 = 0;
  v202 = 0;
  v200 = 0;
  UniqueThread_low = (struct DatabaseStartupInfo *)LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  v309 = 256;
  v170 = (char *)v4 + 5376;
  if ( *((_DWORD *)v4 + 1344) )
  {
    v188 = 0;
  }
  else
  {
    v326 = _InterlockedCompareExchange64(v165, (signed __int64)UniqueThread_low, 0);
    v327 = v326;
    v188 = v326 == 0;
    if ( !v326 )
      goto LABEL_67;
  }
  if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84
    && (v310 = 88,
        v328 = NtCurrentTeb()->ThreadLocalStoragePointer,
        v25 = v328[SystemThread_TlsIndex],
        v26 = SystemThread_TlsOffset + v25 == 0,
        v27 = SystemThread_TlsOffset + v25,
        v329 = v27,
        !v26)
    && *(_QWORD *)(v27 + 272) == v27 )
  {
    v28 = *(_QWORD *)(v27 + 256);
    v330 = v28;
  }
  else
  {
    v28 = 0;
  }
  v200 = v28;
  if ( v28 )
  {
    v331 = &v231;
    v311 = Base_PublicGlobals::sm_invariantTscAvailable;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      v312 = QueryPerformanceCounter(&PerformanceCount);
      QuadPart = (DirtyPageMgr *)PerformanceCount.QuadPart;
      v231 = (DirtyPageMgr *)PerformanceCount.QuadPart;
    }
    else
    {
      QuadPart = MEMORY[0x7FFE0008];
      v285 = MEMORY[0x7FFE0008];
      v231 = MEMORY[0x7FFE0008];
      v28 = v200;
    }
    v332 = QuadPart;
    v202 = QuadPart;
  }
  v313 = 2;
  if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
    Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v165, UniqueThread_low);
  else
    Spinlock<148,10,258>::SpinToAcquireOptimistic(v165, v28, UniqueThread_low);
  if ( v28 )
  {
    v333 = &v201;
    v314 = Base_PublicGlobals::sm_invariantTscAvailable;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      v315 = QueryPerformanceCounter(&v286);
      v30 = (DirtyPageMgr *)v286.QuadPart;
      v201 = (DirtyPageMgr *)v286.QuadPart;
    }
    else
    {
      v30 = MEMORY[0x7FFE0008];
      v287 = MEMORY[0x7FFE0008];
      v201 = MEMORY[0x7FFE0008];
      v28 = v200;
    }
    v334 = &v202;
    v335 = &v201;
    if ( v30 < v202 )
    {
      v31 = 0;
      v140 = 0;
    }
    else
    {
      v31 = v30 - v202;
      v140 = (char *)v31;
    }
    v140 = (char *)v31;
    v336 = (char *)v31;
    v337 = v28 + 3192;
    *(_QWORD *)(v28 + 3192) += v31;
  }
LABEL_67:
  *((_DWORD *)v4 + 158) &= ~0x40000u;
  *((_DWORD *)v4 + 158) |= 0x80u;
  v338 = (char *)v4 + 5376;
  v164 = (char)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
  if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v32 = rand();
    if ( v32 == 5 * (v32 / 5) )
      Spinlock<148,10,258>::UpdateStatSnapshot();
  }
  v339 = (char *)v4 + 5376;
  *v24 = 0;
  if ( *((int *)v4 + 232) > 0 )
  {
    PerfmonManager::AddInstance(
      (PerfmonManager *)&ResourceStr,
      5u,
      (const wchar_t *)v4 + 468,
      *((unsigned __int16 *)v4 + 20));
    PerfmonManager::AddInstance(
      (PerfmonManager *)&ResourceStr,
      0x35u,
      (const wchar_t *)v4 + 468,
      *((unsigned __int16 *)v4 + 20));
    PerfmonManager::AddInstance(
      (PerfmonManager *)&ResourceStr,
      0x37u,
      (const wchar_t *)v4 + 468,
      *((unsigned __int16 *)v4 + 20));
    if ( GetMasterDbId() == *((_WORD *)v4 + 20) )
    {
      PerfmonManager::AddInstance((PerfmonManager *)&ResourceStr, 5u, L"_Total", 0);
      PerfmonManager::AddInstance((PerfmonManager *)&ResourceStr, 0xAu, L"_Total", 0);
      PerfmonManager::AddInstance((PerfmonManager *)&ResourceStr, 0x35u, L"_Total", 0);
      PerfmonManager::AddInstance((PerfmonManager *)&ResourceStr, 0x37u, L"_Total", 0);
    }
  }
  v33 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
  v144 = CommonGlobalState::m_PerfCountersEnabled;
  if ( CommonGlobalState::m_PerfCountersEnabled )
  {
    PerfmonManager::SetInstanceCounterValue((PerfmonManager *)&ResourceStr, 5u, 0, 0, *((unsigned __int16 *)v4 + 20));
    v33 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
  }
  if ( *v33 )
    PerfmonManager::SetInstanceCounterValue((PerfmonManager *)&ResourceStr, 5u, 8u, 0, *((unsigned __int16 *)v4 + 20));
  v140 = 0;
  BootPagePtr::Init(&v474, 0, *((_QWORD *)v4 + 578), 0);
  BootPagePtr::GetAccess(&v474, 2);
  BootPagePtr::CopyDbInfo((BootPagePtr *)&v474, (struct DBINFO *)v481);
  BootPagePtr::ReleaseAccess((BootPagePtr *)&v474, 0);
  *((_DWORD *)v4 + 564) = v493;
  *((_DWORD *)v4 + 654) = v517;
  if ( dword_103172528
    && !IsLogicalServerSystemDatabase((const wchar_t *)v4 + 468, *((_DWORD *)v4 + 232), *((unsigned __int16 *)v4 + 20)) )
  {
    *((_WORD *)v4 + 1300) = v518;
    v340 = &v521;
    v341 = (char *)v4 + 2608;
    v237 = (DBTABLE *)((char *)v4 + 2608) != 0;
    if ( v4 == (DBTABLE *)-2608LL )
    {
      *_errno() = 22;
      _invalid_parameter_noinfo();
    }
    else
    {
      *((_QWORD *)v4 + 326) = v521;
    }
    v238 = 258;
    v34 = 0;
    v190 = 0;
    HIDWORD(v134) = 0;
    v35 = ConvertDateToStrSafe((char *)v4 + 2608, v523, 128);
    v189 = v35;
    if ( v35 > 0 )
    {
      v288 = v35;
      if ( (unsigned __int64)v35 >= 0x82 )
        _report_rangecheckfailure(v36);
      _mm_lfence();
      v523[v288] = 0;
      v37 = FastDBCSToUnicode(0, v523, v189, v524, 128);
      v34 = v37;
      v190 = v37;
      if ( v37 )
      {
        v342 = 2LL * v37;
        if ( v342 >= 0x204 )
          _report_rangecheckfailure(2LL * v37);
        v524[v37] = 0;
      }
    }
    v38 = v520;
    *((_DWORD *)v4 + 651) = v520;
    v39 = v519;
    *((_WORD *)v4 + 1301) = v519;
    v40 = v524;
    if ( !v34 )
      v40 = (wchar_t *)&word_10280BED8;
    LODWORD(v136) = v39;
    LODWORD(v134) = v38;
    log_unlocalized_systemmetadata(
      L"Copying dbt_inactiveDurationMin %d, dbt_deactivationCount %d, dbt_lastDeactivationDate %s, dbt_deactivationInterva"
       "lMin %d, dbt_needToAdjustInterval %d from bootpage.",
      *((unsigned int *)v4 + 654),
      (unsigned int)*((__int16 *)v4 + 1300),
      v40,
      v134,
      v136);
  }
  if ( byte_10316EB3E && *((_WORD *)v4 + 20) == 1 )
  {
    SourceSize = 0;
    Source = 0;
    v239 = 88;
    v343 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v41 = v343[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v344 = v41;
    v42 = *(_QWORD *)(v41 + 256);
    v289 = v42;
    if ( !v42 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v42 = *(_QWORD *)(v41 + 256);
      v289 = v42;
    }
    v345 = *(_QWORD *)(v42 + 1000);
    if ( (int)ReadFabricProperty(v345, L"InactiveDurationMin", &SourceSize, &Source) >= 0 )
      memcpy_s((char *)v4 + 2616, 4u, Source, SourceSize);
    v346 = Source;
    operator delete[](Source);
  }
  RecoveryUnit::SetOnDiskVersion(*((RecoveryUnit **)v4 + 578), v482);
  if ( !FIsSupportedDbVersion(*((unsigned __int16 *)v4 + 20), v482) )
    RaiseDbVersionError(*((unsigned __int16 *)v4 + 20), v482, *((_DWORD *)v4 + 232), (const wchar_t *)v4 + 468);
  v43 = (struct RecoveryUnit *)*((_QWORD *)v4 + 578);
  v347 = v43;
  v191 = 1;
  v44 = *((_QWORD *)v43 + 214) + 784LL;
  v348 = v44;
  if ( !*(_DWORD *)v44
    || *(_QWORD *)(v44 + 4) == *(_QWORD *)&x_AG_DB_IdBad.Data1
    && *(_QWORD *)(v44 + 12) == *(_QWORD *)x_AG_DB_IdBad.Data4 )
  {
    v46 = 1;
  }
  else
  {
    v290 = 0;
    DbMgr = HadrRecoveryCallbacks::GetDbMgr(v43, 1);
    v349 = DbMgr;
    v290 = DbMgr;
    v46 = DbMgr && *((_DWORD *)DbMgr + 404);
    v191 = v46;
    if ( DbMgr )
      (*(void (__fastcall **)(struct HaDrDbMgr *))(*(_QWORD *)DbMgr + 16LL))(DbMgr);
  }
  if ( !v46 )
  {
    LODWORD(v137) = *((_DWORD *)v4 + 196);
    LODWORD(v133) = *((_DWORD *)v4 + 232);
    ex_raise(352, 62, 10, 1, v133, (char *)v4 + 936, v137);
  }
  if ( dword_103172528 || IsMiaaInstance() )
    log_unlocalized_systemmetadata(
      L"Version of database %.*ls at startup is %d.",
      *((unsigned int *)v4 + 232),
      (char *)v4 + 936,
      v482);
  v177 = (volatile signed __int64 *)((char *)v4 + 5376);
  v350 = 0;
  v351 = 0;
  v207 = 0;
  v205 = 0;
  v204 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  v240 = 256;
  v352 = (char *)v4 + 5376;
  if ( *(_DWORD *)v24 )
  {
    v192 = 0;
  }
  else
  {
    v353 = _InterlockedCompareExchange64(v177, v204, 0);
    v354 = v353;
    v192 = v353 == 0;
    if ( !v353 )
      goto LABEL_139;
  }
  if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84
    && (v241 = 88,
        v355 = NtCurrentTeb()->ThreadLocalStoragePointer,
        v47 = v355[SystemThread_TlsIndex],
        v26 = SystemThread_TlsOffset + v47 == 0,
        v48 = SystemThread_TlsOffset + v47,
        v356 = v48,
        !v26)
    && *(_QWORD *)(v48 + 272) == v48 )
  {
    v49 = *(_QWORD *)(v48 + 256);
    v357 = v49;
  }
  else
  {
    v49 = 0;
  }
  v205 = v49;
  if ( v49 )
  {
    v358 = &v229;
    v242 = Base_PublicGlobals::sm_invariantTscAvailable;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      v243 = QueryPerformanceCounter(&v291);
      v50 = (DirtyPageMgr *)v291.QuadPart;
      v229 = (DirtyPageMgr *)v291.QuadPart;
    }
    else
    {
      v50 = MEMORY[0x7FFE0008];
      v292 = MEMORY[0x7FFE0008];
      v229 = MEMORY[0x7FFE0008];
      v49 = v205;
    }
    v359 = v50;
    v207 = v50;
  }
  v244 = 2;
  if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
    Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v177, v204);
  else
    Spinlock<148,10,258>::SpinToAcquireOptimistic(v177, v49, v204);
  if ( v49 )
  {
    v360 = &v206;
    v245 = Base_PublicGlobals::sm_invariantTscAvailable;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      v246 = QueryPerformanceCounter(&v293);
      v51 = (DirtyPageMgr *)v293.QuadPart;
      v206 = (DirtyPageMgr *)v293.QuadPart;
    }
    else
    {
      v51 = MEMORY[0x7FFE0008];
      v294 = MEMORY[0x7FFE0008];
      v206 = MEMORY[0x7FFE0008];
      v49 = v205;
    }
    v361 = &v207;
    v362 = &v206;
    if ( v51 < v207 )
    {
      v52 = 0;
      v140 = 0;
    }
    else
    {
      v52 = v51 - v207;
      v140 = (char *)v52;
    }
    v140 = (char *)v52;
    v363 = (char *)v52;
    v364 = v49 + 3192;
    *(_QWORD *)(v49 + 3192) += v52;
  }
LABEL_139:
  DBTABLE::SetupCDBStateAndCollations(v4, (struct DBINFO *)v481);
  *((_WORD *)v4 + 1257) = v483;
  v146 = v485;
  *((_DWORD *)v4 + 11) = v485;
  if ( !*((_DWORD *)v4 + 12) )
    *((_DWORD *)v4 + 12) = v500;
  v365 = (char *)v4 + 5376;
  v147 = (char)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
  if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v53 = rand();
    if ( v53 == 5 * (v53 / 5) )
      Spinlock<148,10,258>::UpdateStatSnapshot();
  }
  v366 = (char *)v4 + 5376;
  *v24 = 0;
  v193 = v503;
  if ( v513 == 1 )
  {
    LOBYTE(v133) = 1;
    DBMgr::ErrorIsCDBAllowed(5, 2, *((unsigned int *)v4 + 232), (char *)v4 + 936, (_DWORD)v133, 0);
  }
  if ( *((_WORD *)v4 + 20) == 0x7FFF )
  {
    v199 = PrintSQLVersion(v504, v522, 0x10u);
    if ( v199 )
    {
      _mm_lfence();
      scierrlog(0x3BEu, v199, v522);
    }
  }
  if ( !(unsigned int)DBMgr::IsCurrentDbVer(v482, *((_BYTE *)v4 + 2361)) )
  {
    if ( *((_WORD *)v4 + 20) == 1 )
      *((_BYTE *)qword_10316ECA0 + 124) = 1;
    if ( (*((_DWORD *)v4 + 158) & 0x200000) != 0 )
      DBTABLE::HandleDownlevelStandby(v4);
  }
  v54 = *((_DWORD *)v4 + 158);
  if ( (v54 & 0x400) != 0 && (v54 & 0x200000) == 0 )
  {
    if ( (v484 & 0x40000000) != 0 )
      goto LABEL_159;
    LODWORD(v133) = *((_DWORD *)v4 + 232);
    ex_raise(34, 15, 16, 5, v133, (char *)v4 + 936);
  }
  if ( (v484 & 0x40000000) == 0 )
  {
    *((_DWORD *)v4 + 545) = 0;
    goto LABEL_161;
  }
LABEL_159:
  *((_DWORD *)v4 + 545) = 1;
  v367 = (char *)v4 + 2184;
  v55 = v490;
  v184 = v490;
  v56 = v489;
  v247 = v489;
  v248 = v488;
  *((_DWORD *)v4 + 546) = v488;
  *((_DWORD *)v4 + 547) = v56;
  *((_WORD *)v4 + 1096) = v55;
  v368 = *((_QWORD *)v4 + 578);
  FCB = FileMgr::GetFCB(*(_QWORD *)(v368 + 1696), 1, 0);
  *(_OWORD *)((char *)v4 + 2196) = *(_OWORD *)(FCB + 136);
LABEL_161:
  if ( !DBTABLE::IsRestoring(v4) && (v487 & 0x10) != 0 )
  {
    *((_BYTE *)v4 + 684) |= 4u;
    *((_BYTE *)v4 + 57) |= 0x80u;
  }
  if ( v486 )
  {
    if ( *((_WORD *)v4 + 20) == 1 )
    {
      dword_10316ECB0 |= 0x100u;
      if ( *((_DWORD *)v4 + 377) != 5 )
      {
        BootPagePtr::Release((BootPagePtr *)&v474, 0);
        v140 = 0;
        BootPagePtr::SetMasterFixups(&v474, 0, *((_QWORD *)v4 + 578), 1);
        v140 = 0;
        BootPagePtr::Init(&v474, 0, *((_QWORD *)v4 + 578), 0);
      }
    }
  }
  v370 = v505;
  v148 = v505[0];
  v149 = v505[0] & 0x1F;
  if ( (v505[0] & 0x1F) != 0 )
  {
    v249 = 2722;
    v59 = (CSECDEK *)operator new(
                       0x568u,
                       *((struct IMemObj **)v4 + 86),
                       "sql\\ntdbms\\storeng\\dfs\\manager\\dbtable.cpp",
                       2722,
                       5u);
    v371 = v59;
    if ( v59 )
      v60 = CSECDEK::CSECDEK(v59, v505, 0x258u, *((struct IMemObj **)v4 + 86), *((unsigned __int16 *)v4 + 20));
    else
      v60 = 0;
    v372 = v60;
    *((_QWORD *)v4 + 277) = v60;
    v457 = GUID_NULL;
    CSECDEK::Initialize(v60, *((unsigned __int16 *)v4 + 20), 0, 0, &v457, 0);
    v373 = (_BYTE *)*((_QWORD *)v4 + 277);
    v150 = *v373 & 0x1F;
    v374 = (_BYTE *)*((_QWORD *)v4 + 277);
    LODWORD(v135) = v150;
    LogSystemMetadata(
      L"[TDE] Database ID: [%d]: Creating DBTABLE DEK on startup 0x%p with state %ls (%d).",
      *((unsigned __int16 *)v4 + 20),
      *((_QWORD *)v4 + 277),
      off_102889E90[*v374 & 0x1F],
      v135);
    v375 = (_BYTE *)*((_QWORD *)v4 + 277);
    v58 = *v375 & 0x1F;
    switch ( *v375 & 0x1F )
    {
      case 2:
      case 3:
      case 4:
      case 6:
        DBMgr::UseTempdbEncryption(qword_10316ECA0);
        break;
      default:
        break;
    }
  }
  if ( *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v58, v57) + 110) )
    DBMgr::UseTempdbEncryption(qword_10316ECA0);
  if ( v193 > 1 )
    *((_DWORD *)v4 + 544) = DBTABLE::StartupDbMirroring(v4, (DBTABLE *)((char *)v4 + 56));
  v250 = v516 << 16;
  v376 = &v220;
  v377 = &v235;
  v235 = v514;
  v236 = v515;
  v220 = v514;
  v221 = v515;
  v222 = 0;
  HkHostDbCtxt::UpdateHkVersionAndReinitialize(*(_QWORD *)(*((_QWORD *)v4 + 578) + 26096LL), v250, &v220);
  DBTABLE::CalculateCurrentState(v4);
  StartupCoordinator::NotifyPhaseStart(v4, 2);
  DBTABLE::CalculateCurrentState(v4);
  StartupCoordinator::NotifyPhaseEnd(v4, 2);
  if ( dword_1031852C8 )
  {
    RecoveryUnit::RefreshHybridLAG(*((RecoveryUnit **)v4 + 578));
    v139 = 0;
    if ( byte_10316E805 )
    {
      v61 = (RecoveryUnit *)*((_QWORD *)v4 + 578);
      if ( *((_BYTE *)v61 + 8272) && *((_BYTE *)v61 + 27672) )
      {
        v139 = 1;
LABEL_188:
        v380 = *((_QWORD *)v4 + 578);
        BackupManager::LoadHybridAgBackupInfo(*(BackupManager **)(v380 + 1960));
        goto LABEL_189;
      }
      if ( RecoveryUnit::IsHybridLAGGlobalPrimary(v61) )
      {
        v62 = *((_QWORD *)v4 + 664);
        v378 = v62;
        if ( v62 )
        {
          v138 = 0;
          v251 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v62 + 848LL))(v62, &v138);
          if ( v251 < 0 )
          {
            v194 = 0;
            v63 = ((__int64 (__fastcall *)(DBTABLE *, int *))g_dbtableFactory[2])(v4, &v194);
            v379 = v63;
            SourceSize_4 = 0;
            ((void (__fastcall *)(DBTABLE *, int *))g_dbtableFactory[2])(v4, &SourceSize_4);
            LODWORD(v133) = SourceSize_4;
            ex_raise(419, 55, 21, 1, v133, v63);
          }
          v64 = v138;
          v139 = v138;
          *(_BYTE *)(*((_QWORD *)v4 + 578) + 27673LL) = v138;
          if ( v64 )
            goto LABEL_188;
        }
      }
    }
  }
LABEL_189:
  v252 = dword_103184474;
  if ( !dword_103184474 && !dword_1031852C8 && (*((_BYTE *)v4 + 60) & 2) == 0 )
    DBTABLE::StartDtcForDb(v4);
  if ( (unsigned int)DBTABLE::ShouldSkipRecovery(v4, (DBTABLE *)((char *)v4 + 56), 1) )
  {
    DBTABLE::SkipRecoveryStartup(v4);
    *((_QWORD *)v4 + 17) = 0;
    ExcHandler::~ExcHandler((ExcHandler *)v325);
    *(_DWORD *)(v142 + 616) &= ~v182;
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1272LL) = v143;
    BootPagePtr::~BootPagePtr((BootPagePtr *)&v474);
    return;
  }
  if ( *((_WORD *)v4 + 20) != 1 )
  {
    v65 = (struct BaseXact *)*((_QWORD *)v4 + 12);
    if ( v65 )
      DBMgr::LinkSnapshotsForStartup(qword_10316ECA0, v65, v4);
  }
  *((_BYTE *)v4 + 2212) |= 2u;
  v159[0] = 0;
  v159[1] = 0;
  if ( byte_10316E923 || (v151 = (unsigned __int8)byte_10317B183 >> 7, byte_10317B183 < 0) )
  {
    v152 = (unsigned __int8)byte_10317AFB0 >> 2;
    if ( (byte_10317AFB0 & 4) == 0 )
    {
      v381 = *((_QWORD *)v4 + 578);
      v66 = *(_QWORD *)(v381 + 1712) + 784LL;
      v382 = v66;
      if ( *(_DWORD *)v66 )
      {
        if ( *(_QWORD *)(v66 + 4) != *(_QWORD *)&x_AG_DB_IdBad.Data1
          || *(_QWORD *)(v66 + 12) != *(_QWORD *)x_AG_DB_IdBad.Data4 )
        {
          v254 = 88;
          v383 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v67 = v383[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v384 = v67;
          v68 = *(_QWORD *)(v67 + 256);
          v295 = v68;
          if ( !v68 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v68 = *(_QWORD *)(v67 + 256);
            v295 = v68;
          }
          v385 = *(_QWORD *)(v68 + 600);
          if ( (int)SOS_Task::GetDeadlockPriority() > -20 )
            AutoChangeDeadlockPriority::SetDeadlockPriority(v159, 4294967276LL);
        }
      }
    }
  }
  StartupCoordinator::NotifyPhaseStart(v4, 4);
  StartupCoordinator::NotifyPhaseEnd(v4, 4);
  v69 = *((_DWORD *)v4 + 158) & 0x140;
  v153 = v69 != 0;
  if ( (v69 & 0x140) != 0 || (*((_BYTE *)v4 + 58) & 0x10) != 0 && *((_DWORD *)v4 + 378) == 1 )
  {
    *((_QWORD *)v4 + 17) = 0;
    LODWORD(v137) = *((unsigned __int16 *)v4 + 20);
    LODWORD(v133) = *((_DWORD *)v4 + 232);
    ex_raise(34, 14, 25, 5, v133, (char *)v4 + 936, v137);
    AutoChangeDeadlockPriority::~AutoChangeDeadlockPriority((AutoChangeDeadlockPriority *)v159);
    ExcHandler::~ExcHandler((ExcHandler *)v325);
    *(_DWORD *)(v142 + 616) &= ~v182;
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1272LL) = v143;
    BootPagePtr::~BootPagePtr((BootPagePtr *)&v474);
    return;
  }
  v70 = (struct RecoveryUnit *)*((_QWORD *)v4 + 578);
  if ( (*((_BYTE *)v70 + 7376) & 0x20) != 0 )
  {
    v171 = (volatile signed __int64 *)((char *)v4 + 5376);
    v386 = 0;
    v387 = 0;
    v210 = 0;
    v219 = 0;
    v208 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    v255 = 256;
    v388 = (char *)v4 + 5376;
    if ( *(_DWORD *)v24 )
    {
      v195 = 0;
    }
    else
    {
      v389 = _InterlockedCompareExchange64(v171, v208, 0);
      v390 = v389;
      v195 = v389 == 0;
      if ( !v389 )
      {
LABEL_237:
        *((_DWORD *)v4 + 158) &= ~0x80u;
        *((_DWORD *)v4 + 381) &= ~0x10u;
        v401 = (char *)v4 + 5376;
        v154 = (char)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v77 = rand();
          if ( v77 == 5 * (v77 / 5) )
            Spinlock<148,10,258>::UpdateStatSnapshot();
        }
        v402 = (char *)v4 + 5376;
        *v24 = 0;
        DBTABLE::CalculateCurrentState(v4);
        StartupCoordinator::NotifyPhaseStart(v4, 5);
        StartupCoordinator::NotifyPhaseEnd(v4, 5);
        StartupCoordinator::NotifyPhaseStart(v4, 7);
        StartupCoordinator::NotifyPhaseEnd(v4, 7);
        StartupCoordinator::NotifyPhaseStart(v4, 8);
        StartupCoordinator::NotifyPhaseEnd(v4, 8);
        *((_BYTE *)v4 + 684) |= 2u;
        *((_QWORD *)v4 + 12) = 0;
        if ( RecoveryUnit::IsTraceEnabled() )
          RecoveryUnit::PrintTrace(*((RecoveryUnit **)v4 + 578), L"Log replica is online ...");
LABEL_242:
        AutoChangeDeadlockPriority::~AutoChangeDeadlockPriority((AutoChangeDeadlockPriority *)v159);
        ExcHandler::~ExcHandler((ExcHandler *)v325);
        *(_DWORD *)(v142 + 616) &= ~v182;
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset
                                          + 8LL)
                              + 96LL)
                  + 1272LL) = v143;
        BootPagePtr::~BootPagePtr((BootPagePtr *)&v474);
        return;
      }
    }
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84
      && (v256 = 88,
          v391 = NtCurrentTeb()->ThreadLocalStoragePointer,
          v71 = v391[SystemThread_TlsIndex],
          v26 = SystemThread_TlsOffset + v71 == 0,
          v72 = SystemThread_TlsOffset + v71,
          v392 = v72,
          !v26)
      && *(_QWORD *)(v72 + 272) == v72 )
    {
      v73 = *(_QWORD *)(v72 + 256);
      v393 = v73;
    }
    else
    {
      v73 = 0;
    }
    v219 = v73;
    if ( v73 )
    {
      v394 = &v230;
      v257 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v258 = QueryPerformanceCounter(&v296);
        v74 = (DirtyPageMgr *)v296.QuadPart;
        v230 = (DirtyPageMgr *)v296.QuadPart;
      }
      else
      {
        v74 = MEMORY[0x7FFE0008];
        v297 = MEMORY[0x7FFE0008];
        v230 = MEMORY[0x7FFE0008];
        v73 = v219;
      }
      v395 = v74;
      v210 = v74;
    }
    v259 = 2;
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v171, v208);
    else
      Spinlock<148,10,258>::SpinToAcquireOptimistic(v171, v73, v208);
    if ( v73 )
    {
      v396 = &v209;
      v260 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v261 = QueryPerformanceCounter(&v298);
        v75 = (DirtyPageMgr *)v298.QuadPart;
        v209 = (DirtyPageMgr *)v298.QuadPart;
      }
      else
      {
        v75 = MEMORY[0x7FFE0008];
        v299 = MEMORY[0x7FFE0008];
        v209 = MEMORY[0x7FFE0008];
        v73 = v219;
      }
      v397 = &v210;
      v398 = &v209;
      if ( v75 < v210 )
      {
        v76 = 0;
        v140 = 0;
      }
      else
      {
        v76 = v75 - v210;
        v140 = (char *)v76;
      }
      v140 = (char *)v76;
      v399 = (char *)v76;
      v400 = v73 + 3192;
      *(_QWORD *)(v73 + 3192) += v76;
    }
    goto LABEL_237;
  }
  if ( (unsigned int)HadrRecoveryCallbacks::ShouldNotCompleteRecovery(v70) )
  {
    StartupCoordinator::NotifyPhaseStart(v4, 5);
    StartupCoordinator::NotifyPhaseEnd(v4, 5);
    *((_BYTE *)v4 + 684) |= 2u;
    *((_QWORD *)v4 + 12) = 0;
    if ( RecoveryUnit::IsTraceEnabled() )
      RecoveryUnit::PrintTrace(
        *((RecoveryUnit **)v4 + 578),
        L"Exit after physical recovery with pending Hadron role change.");
    goto LABEL_242;
  }
  v160 = 0;
  v174[0] = 0;
  v174[1] = 0;
  v403 = 0;
  try
  {
    if ( (unsigned int)RecoveryUnit::GetHkDatabaseState(*((_QWORD *)v4 + 578)) != 1 )
    {
      v172 = (volatile signed __int64 *)((char *)v4 + 5376);
      v404 = 0;
      v405 = 0;
      v214 = 0;
      v211 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      v262 = 256;
      v406 = (char *)v4 + 5376;
      if ( *(_DWORD *)v24 )
      {
        v78 = 0;
      }
      else
      {
        v407 = _InterlockedCompareExchange64(v172, v211, 0);
        v408 = v407;
        v78 = v407 == 0;
      }
      v263 = v78;
      if ( !v78 )
      {
        if ( (SOS_PublicGlobals::sm_osStats & 0x80u) != 0 && (SOS_PublicGlobals::sm_osStats & 4) != 0 )
        {
          v233 = 0;
          v264 = 88;
          v409 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v79 = v409[SystemThread_TlsIndex];
          v26 = SystemThread_TlsOffset + v79 == 0;
          v80 = SystemThread_TlsOffset + v79;
          v410 = v80;
          if ( !v26 && *(_QWORD *)(v80 + 272) == v80 )
          {
            v82 = *(_QWORD *)(v80 + 256);
            v233 = v82;
          }
          else
          {
            v82 = v233;
          }
          v212 = v82;
          if ( v82 )
          {
            v411 = &v228;
            v265 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              v266 = QueryPerformanceCounter(&v300);
              v83 = (DirtyPageMgr *)v300.QuadPart;
              v228 = (DirtyPageMgr *)v300.QuadPart;
            }
            else
            {
              v83 = MEMORY[0x7FFE0008];
              v412 = MEMORY[0x7FFE0008];
              v228 = MEMORY[0x7FFE0008];
              v82 = v212;
            }
            v413 = v83;
            v214 = v83;
          }
        }
        else
        {
          v82 = 0;
          v212 = 0;
        }
        v267 = 2;
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v172, v211);
        else
          Spinlock<148,10,258>::SpinToAcquireOptimistic(v172, v82, v211);
        if ( v82 )
        {
          v414 = &v213;
          v268 = Base_PublicGlobals::sm_invariantTscAvailable;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            v269 = QueryPerformanceCounter(&v301);
            v84 = (DirtyPageMgr *)v301.QuadPart;
            v213 = (DirtyPageMgr *)v301.QuadPart;
          }
          else
          {
            v84 = MEMORY[0x7FFE0008];
            v415 = MEMORY[0x7FFE0008];
            v213 = MEMORY[0x7FFE0008];
            v82 = v212;
          }
          v416 = &v214;
          v417 = &v213;
          if ( v84 < v214 )
          {
            v85 = 0;
            v140 = 0;
          }
          else
          {
            v85 = v84 - v214;
            v140 = (char *)v85;
          }
          v140 = (char *)v85;
          v418 = (char *)v85;
          v419 = v82 + 3192;
          *(_QWORD *)(v82 + 3192) += v85;
        }
      }
      *((_DWORD *)v4 + 158) &= ~0x80u;
      v420 = (char *)v4 + 5376;
      v155 = (char)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
      if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v86 = rand();
        if ( v86 == 5 * (v86 / 5) )
          Spinlock<148,10,258>::UpdateStatSnapshot();
      }
      v421 = (char *)v4 + 5376;
      *v24 = 0;
      DBTABLE::CalculateCurrentState(v4);
    }
    if ( *((_WORD *)v4 + 20) == 1 )
      DBMgr::OpenDB(qword_10316ECA0, 0, 1, 10, 1, 80);
    if ( *(_BYTE *)(*((_QWORD *)v4 + 578) + 8272LL) )
    {
      v270 = 88;
      v422 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v87 = v422[SystemThread_TlsIndex] + SystemThread_TlsOffset;
      v423 = v87;
      v88 = *(_QWORD *)(v87 + 256);
      v302 = v88;
      if ( !v88 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v88 = *(_QWORD *)(v87 + 256);
        v302 = v88;
      }
      v424 = *(_QWORD *)(v88 + 600);
      AutoChangeDeadlockPriority::SetDeadlockPriority(v174, 4294967266LL);
      Worker::TaskAutoOffFlags::UnsetFlags(&v160, 1);
    }
    DBTABLE::StartupPostRecovery(v4, v141);
    v156 = byte_1031852E4;
    if ( byte_1031852E4 )
    {
      v157 = byte_1031852E4;
      if ( !*((_QWORD *)v4 + 665) )
        DBTABLE::StartDtcForDb(v4);
    }
  }
  catch ( SQLError v467 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v321, (const struct SQLError *)v467);
      v130 = *(_QWORD *)(*((_QWORD *)v176 + 578) + 1832LL);
      if ( v130 )
      {
        v425 = *(_QWORD *)(*((_QWORD *)v176 + 578) + 1832LL);
        v426 = v130 + 22272;
        v131 = *(_QWORD *)(v130 + 22272);
        if ( v131 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v131 + 32LL))(v131);
        *(_QWORD *)(v130 + 22288) = 0;
      }
      CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v321);
      ExceptionRethrow(CurrentException);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v321);
    }
    catch ( ShortStackException )
    {
    }
    v4 = v176;
  }
  v89 = v142;
  v271 = 88;
  v427 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v90 = v427[SystemThread_TlsIndex] + SystemThread_TlsOffset;
  v428 = v90;
  v91 = *(struct Worker **)(v90 + 256);
  v303 = v91;
  if ( !v91 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v91 = *(struct Worker **)(v90 + 256);
    v303 = v91;
  }
  v429 = v91;
  if ( *((_DWORD *)v91 + 139) )
    ExceptionPostCatchActions(v91);
  *((_QWORD *)v4 + 17) = 0;
  StartupCoordinator::NotifyPhaseStart(v4, 7);
  if ( (unsigned int)RecoveryUnit::GetHkDatabaseState(*((_QWORD *)v4 + 578)) == 1 )
  {
    v173 = (volatile signed __int64 *)((char *)v4 + 5376);
    v430 = 0;
    v431 = 0;
    v218 = 0;
    v216 = 0;
    v215 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    v272 = 256;
    v432 = (char *)v4 + 5376;
    if ( *((_DWORD *)v4 + 1344) )
    {
      v197 = 0;
    }
    else
    {
      v433 = _InterlockedCompareExchange64(v173, v215, 0);
      v434 = v433;
      v197 = v433 == 0;
      if ( !v433 )
      {
LABEL_321:
        *((_DWORD *)v4 + 158) &= ~0x80u;
        v445 = (char *)v4 + 5376;
        v158 = (char)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v99 = rand();
          if ( v99 == 5 * (v99 / 5) )
            Spinlock<148,10,258>::UpdateStatSnapshot();
        }
        v446 = (char *)v4 + 5376;
        *((_QWORD *)v4 + 672) = 0;
        DBTABLE::CalculateCurrentState(v4);
        if ( DBTABLE::IsOkToScan(v4) )
        {
          v198 = 0;
          if ( !v141 )
          {
            AutoReadOnlyXact::BeginStandAloneXact((AutoReadOnlyXact *)&v198, L"DBTABLE::Startup", 32);
            if ( v198 )
              v141 = (struct BaseXact *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v198 + 72LL))(v198);
            else
              v141 = 0;
          }
          DBTABLE::LoadCDBSettings(v4, v141);
          if ( v198 )
            (**(void (__fastcall ***)(__int64, __int64))v198)(v198, 1);
        }
        goto LABEL_331;
      }
    }
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84
      && (v273 = 88,
          v435 = NtCurrentTeb()->ThreadLocalStoragePointer,
          v93 = v435[SystemThread_TlsIndex],
          v26 = SystemThread_TlsOffset + v93 == 0,
          v94 = SystemThread_TlsOffset + v93,
          v436 = v94,
          !v26)
      && *(_QWORD *)(v94 + 272) == v94 )
    {
      v95 = *(_QWORD *)(v94 + 256);
      v437 = v95;
    }
    else
    {
      v95 = 0;
    }
    v216 = v95;
    if ( v95 )
    {
      v438 = &v227;
      v274 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v275 = QueryPerformanceCounter(&v304);
        v96 = (DirtyPageMgr *)v304.QuadPart;
        v227 = (DirtyPageMgr *)v304.QuadPart;
      }
      else
      {
        v96 = MEMORY[0x7FFE0008];
        v305 = MEMORY[0x7FFE0008];
        v227 = MEMORY[0x7FFE0008];
        v95 = v216;
      }
      v439 = v96;
      v218 = v96;
    }
    v276 = 2;
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v173, v215);
    else
      Spinlock<148,10,258>::SpinToAcquireOptimistic(v173, v95, v215);
    if ( v95 )
    {
      v440 = &v217;
      v277 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v278 = QueryPerformanceCounter(&v306);
        v97 = (DirtyPageMgr *)v306.QuadPart;
        v217 = (DirtyPageMgr *)v306.QuadPart;
      }
      else
      {
        v97 = MEMORY[0x7FFE0008];
        v307 = MEMORY[0x7FFE0008];
        v217 = MEMORY[0x7FFE0008];
        v95 = v216;
      }
      v441 = &v218;
      v442 = &v217;
      if ( v97 < v218 )
      {
        v98 = 0;
        v140 = 0;
      }
      else
      {
        v98 = v97 - v218;
        v140 = (char *)v98;
      }
      v140 = (char *)v98;
      v443 = (char *)v98;
      v444 = v95 + 3192;
      *(_QWORD *)(v95 + 3192) += v98;
    }
    goto LABEL_321;
  }
LABEL_331:
  if ( (*(_BYTE *)(*((_QWORD *)v4 + 578) + 7376LL) & 0x40) == 0 )
  {
    if ( *((_QWORD *)v4 + 277) )
    {
      if ( byte_10316E877 && (qword_10317ADF2 & 0x100) == 0 )
      {
        v100 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v101 = *(_QWORD *)(v100 + 256);
        if ( !v101 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v101 = *(_QWORD *)(v100 + 256);
        }
        v102 = g_metadataFactory(
                 *(_QWORD *)(v101 + 1000),
                 v141,
                 "sql\\ntdbms\\storeng\\dfs\\manager\\dbtable.cpp",
                 3099);
        v232 = v102;
        v447 = v102;
        v103 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v102 + 56LL))(
                 v102,
                 *((unsigned __int16 *)v4 + 20),
                 0,
                 0,
                 0,
                 0);
        v226 = v103;
        v104 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v103 + 2296LL))(v103);
        v105 = *((_QWORD *)v4 + 277);
        if ( v104 )
        {
          if ( byte_10316E877 && (qword_10317ADF2 & 0x100) == 0 )
          {
            *(_DWORD *)(v105 + 612) = v104;
            utgettime((struct SQLDATEBASE *)(v105 + 616), 1, 0);
          }
        }
        else
        {
          switch ( *(_BYTE *)v105 & 0x1F )
          {
            case 1:
            case 3:
              v106 = 4;
              break;
            case 2:
            case 4:
            case 5:
            case 6:
              v106 = 1;
              break;
            default:
              v106 = 0;
              break;
          }
          v107 = *((_QWORD *)v4 + 277);
          if ( byte_10316E877 && (qword_10317ADF2 & 0x100) == 0 )
          {
            *(_DWORD *)(v107 + 612) = v106;
            utgettime((struct SQLDATEBASE *)(v107 + 616), 1, 0);
          }
          v103 = v226;
          v102 = v232;
        }
        *(_QWORD *)(*((_QWORD *)v4 + 277) + 616LL) = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v103 + 2312LL))(
                                                                  v103,
                                                                  v448);
        (**(void (__fastcall ***)(__int64, __int64))v102)(v102, 1);
      }
      if ( byte_10316E878 || (qword_10317ADF2 & 0x80u) != 0LL )
      {
        v108 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v109 = *(_QWORD *)(v108 + 256);
        if ( !v109 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v109 = *(_QWORD *)(v108 + 256);
        }
        v110 = g_metadataFactory(
                 *(_QWORD *)(v109 + 1000),
                 v141,
                 "sql\\ntdbms\\storeng\\dfs\\manager\\dbtable.cpp",
                 3124);
        v449 = v110;
        v111 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v110 + 56LL))(
                 v110,
                 *((unsigned __int16 *)v4 + 20),
                 0,
                 0,
                 0,
                 0);
        v112 = (wchar_t *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v111 + 2328LL))(
                            v111,
                            *((_QWORD *)v4 + 86));
        v113 = v112;
        if ( v112 )
        {
          v114 = -1;
          do
            ++v114;
          while ( v112[v114] );
          v234 = 2 * v114;
          DBTABLE::SetTDEWorkgroupName(v4, v112, 2 * v114, 0);
          operator delete[](v113);
        }
        else
        {
          DBTABLE::SetTDEWorkgroupName(v4, 0, 0, 0);
        }
        (**(void (__fastcall ***)(__int64, __int64))v110)(v110, 1);
      }
    }
    DBTABLE::LogEncryptionScanState(v4, v92);
    v115 = (_BYTE *)*((_QWORD *)v4 + 277);
    if ( v115 )
    {
      switch ( *v115 & 0x1F )
      {
        case 2:
        case 4:
        case 5:
        case 6:
          if ( !byte_10316E877 || (qword_10317ADF2 & 0x100) != 0 || *(_DWORD *)(*((_QWORD *)v4 + 277) + 612LL) != 2 )
          {
            if ( byte_1031852E4 && *((_QWORD *)v4 + 665) )
            {
              v322 = 0;
              v323 = 0;
              v324 = 0;
              v178 = 0;
              v179 = 0;
              v180 = 1;
              v181 = 0;
              AutoOverrideMsqlXact::InitializeAndOverride((AutoOverrideMsqlXact *)&v322);
              v180 = 1;
              v234 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset);
              *(_QWORD *)&v181 = *(_QWORD *)(v234 + 144);
              v234 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset);
              v116 = *(_BYTE *)(v234 + 152);
              if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v181 + 464LL))(v181) )
              {
                if ( v116 && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v181 + 488LL))(v181) )
                  utassert_fail(
                    1u,
                    "rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()",
                    "automsqlxact.cpp",
                    235,
                    0);
                (*(void (__fastcall **)(_QWORD, __int64, __int64, int *))(*(_QWORD *)v181 + 232LL))(v181, 2, 1, &v179);
                v180 = 1;
                v178 = 3;
              }
              else
              {
                LOBYTE(v137) = 0;
                (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64, __int64, int, int, _DWORD, _QWORD, bool))(*(_QWORD *)v181 + 8LL))(
                  v181,
                  L"DBTABLE::Startup",
                  32,
                  1,
                  2,
                  1,
                  v137,
                  0,
                  v116 != 0);
                v178 = 1;
              }
              v117 = (struct XDES *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v181 + 648LL))(
                                      v181,
                                      *((unsigned __int16 *)v4 + 20));
              FidoGLMController = DBTABLE::GetFidoGLMController(v4);
              v473 = 1;
              v119 = (*(__int64 (__fastcall **)(struct IFidoGLMController *))(*(_QWORD *)FidoGLMController + 32LL))(FidoGLMController);
              v279 = v119;
              v473 = 2;
              v472 = v119;
              v469 = 10;
              v470 = 0;
              v471 = 0;
              v317 = 0;
              LODWORD(v318) = 0;
              *(_QWORD *)&v319 = 0;
              v320 = 0;
              *(_QWORD *)&v317 = (char *)v117 + 56;
              *(_QWORD *)((char *)&v316 + 4) = 0x400000000000000LL;
              LOBYTE(v316) = 5;
              DWORD2(v319) = 0;
              FidoLockManagerClient = GetFidoLockManagerClient();
              v465[0] = v316;
              v465[1] = v317;
              v465[2] = v318;
              v465[3] = v319;
              v466 = v320;
              v225 = v473;
              v223[0] = v469;
              v223[1] = v470;
              v223[2] = v471;
              v224 = v472;
              v121 = *(_QWORD *)FidoLockManagerClient;
              DWFidoTxCtx = GetDWFidoTxCtx(v117, 1);
              LOBYTE(v133) = 0;
              if ( (*(int (__fastcall **)(struct IFidoLockManagerClient *, struct DWFidoTxCtx *, _OWORD *, _DWORD *, _DWORD))(v121 + 8))(
                     FidoLockManagerClient,
                     DWFidoTxCtx,
                     v465,
                     v223,
                     (_DWORD)v133) >= 0 )
                DBTABLE::RestartReencryptionAfterRecovery(v4);
              CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v178, 0);
              AutoOverrideMsqlXact::UnInitialize((AutoOverrideMsqlXact *)&v322);
              if ( v178 )
                CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v178, 0);
              AutoOverrideMsqlXact::~AutoOverrideMsqlXact((AutoOverrideMsqlXact *)&v322);
            }
            else
            {
              DBTABLE::RestartReencryptionAfterRecovery(v4);
            }
          }
          break;
        default:
          break;
      }
    }
  }
  StartupCoordinator::NotifyPhaseEnd(v4, 7);
  if ( (*((_BYTE *)v4 + 59) & 1) == 0 )
    DBTABLE::StartupInDatabase(v4, *((unsigned __int8 *)v4 + 58) >> 7, v141);
  v123 = *((_BYTE *)v4 + 60);
  if ( (v123 & 8) != 0 || (*(_BYTE *)(*((_QWORD *)v4 + 578) + 7376LL) & 0x40) != 0 )
  {
    *((_BYTE *)v4 + 684) |= 2u;
    *((_QWORD *)v4 + 12) = 0;
    *((_BYTE *)v4 + 60) = v123 | 8;
    AutoChangeDeadlockPriority::~AutoChangeDeadlockPriority((AutoChangeDeadlockPriority *)v174);
    Worker::TaskAutoOffFlags::~TaskAutoOffFlags((Worker::TaskAutoOffFlags *)&v160);
    AutoChangeDeadlockPriority::~AutoChangeDeadlockPriority((AutoChangeDeadlockPriority *)v159);
    ExcHandler::~ExcHandler((ExcHandler *)v325);
    *(_DWORD *)(v89 + 616) &= ~v182;
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1272LL) = v143;
    BootPagePtr::~BootPagePtr((BootPagePtr *)&v474);
  }
  else
  {
    v124 = *((_DWORD *)s_pServerConf + 2);
    if ( v124 && v124 != 3 && !dword_103172554 )
    {
      v196 = v502;
      DBTABLE::LogLastKnownGoodCheckDB(v4, (struct SQLDATE *)&v196);
    }
    v196 = v501;
    if ( v501 )
      scierrlog(0xF13u, *((unsigned __int16 *)v4 + 20), &v196);
    if ( RecoveryUnit::IsTraceEnabled() )
      RecoveryUnit::PrintTrace(*((RecoveryUnit **)v4 + 578), L"%ls done.", L"DBTABLE::Startup");
    if ( (*((char *)v4 + 56) < 0 || (*((_BYTE *)v4 + 57) & 1) != 0) && !DBMgr::FVerifyContainment(v4, v141) )
      scierrlog(0x322Bu, *((unsigned int *)v4 + 232), (char *)v4 + 936);
    if ( v484 < 0 )
    {
      v125 = 12629;
      if ( (v484 & 0x8000000) == 0 )
        v125 = 12621;
      scierrlog(v125, *((unsigned int *)v4 + 232), (char *)v4 + 936);
    }
    v126 = *((_QWORD *)v4 + 578);
    if ( (*((_BYTE *)v4 + 59) & 1) == 0 )
    {
      WritePageRecorder2::CreateWPRBucketTable(
        (WritePageRecorder2 *)(v126 + 26120),
        *((struct RecoveryUnit **)v4 + 578),
        0,
        0);
      WritePageRecorder2::Start((WritePageRecorder2 *)(v126 + 26120), (struct RecoveryUnit *)v126);
      WPRStalePageMgr::Init((WPRStalePageMgr *)(v126 + 27136), (struct RecoveryUnit *)v126, 10);
    }
    *((_BYTE *)v4 + 684) |= 2u;
    *((_QWORD *)v4 + 12) = 0;
    AutoChangeDeadlockPriority::~AutoChangeDeadlockPriority((AutoChangeDeadlockPriority *)v174);
    Worker::TaskAutoOffFlags::~TaskAutoOffFlags((Worker::TaskAutoOffFlags *)&v160);
    AutoChangeDeadlockPriority::~AutoChangeDeadlockPriority((AutoChangeDeadlockPriority *)v159);
    ExcHandler::~ExcHandler((ExcHandler *)v325);
    v127 = v143;
    v128 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v129 = *(struct Worker **)(v128 + 256);
    if ( !v129 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v129 = *(struct Worker **)(v128 + 256);
    }
    if ( *((_DWORD *)v129 + 139) )
      ExceptionPostCatchActions(v129);
    *(_DWORD *)(v89 + 616) &= ~v182;
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1272LL) = v127;
    if ( v475 || (v474 & 1) != 0 )
    {
      if ( (v474 & 1) == 0 )
      {
        PageRef::Unlatch((PageRef *)&v475);
        if ( (_QWORD)v478 )
        {
          operator delete((void *)v478, 0x6FAu);
          *(_QWORD *)&v478 = 0;
        }
      }
      BootPagePtr::Release((BootPagePtr *)&v474, 0);
    }
    if ( (_QWORD)v478 )
    {
      operator delete((void *)v478, 0x6FAu);
      *(_QWORD *)&v478 = 0;
    }
    PageRef::~PageRef((PageRef *)&v475);
  }
}

```

## disassembly

```asm
0x101729810  push    rbx
0x101729812  push    rsi
0x101729813  push    rdi
0x101729814  push    r12
0x101729816  push    r13
0x101729818  push    r14
0x10172981a  push    r15
0x10172981c  mov     eax, 1490h
0x101729821  call    _alloca_probe
0x101729826  sub     rsp, rax
0x101729829  mov     [rsp+14C8h+var_B18], 0FFFFFFFFFFFFFFFEh
0x101729835  mov     rax, cs:__security_cookie
0x10172983c  xor     rax, rsp
0x10172983f  mov     [rsp+14C8h+var_48], rax
0x101729847  mov     r13, r8
0x10172984a  mov     r15, rcx
0x10172984d  mov     [rsp+14C8h+var_13C8], rcx
0x101729855  mov     [rsp+14C8h+var_1420], rcx
0x10172985d  mov     [rsp+14C8h+var_1468], rdx
0x101729862  mov     [rsp+14C8h+var_1408], r8
0x10172986a  xor     ebx, ebx
0x10172986c  mov     [rsp+14C8h+var_A48], ebx
0x101729873  mov     [rsp+14C8h+var_A40], rbx
0x10172987b  mov     [rsp+14C8h+var_A38], bl
0x101729882  mov     [rsp+14C8h+var_A34], ebx
0x101729889  mov     [rsp+14C8h+var_A18], rbx
0x101729891  mov     [rsp+14C8h+var_A10], ebx
0x101729898  xorps   xmm0, xmm0
0x10172989b  movdqa  [rsp+14C8h+var_A28], xmm0
0x1017298a4  mov     [rsp+14C8h+var_888], ebx
0x1017298ab  mov     [rsp+14C8h+var_884], bx
0x1017298b3  mov     [rsp+14C8h+var_84C], rbx
0x1017298bb  mov     [rsp+14C8h+var_844], ebx
0x1017298c2  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x1017298c9  movups  [rsp+14C8h+var_840], xmm1
0x1017298d1  mov     [rsp+14C8h+var_1400], rbx
0x1017298d9  movsd   xmm0, [rsp+14C8h+var_1400]
0x1017298e2  movsd   [rsp+14C8h+var_830], xmm0
0x1017298eb  mov     [rsp+14C8h+var_828], ebx
0x1017298f2  movups  [rsp+14C8h+var_824], xmm1
0x1017298fa  mov     [rsp+14C8h+var_494], rbx
0x101729902  mov     [rsp+14C8h+var_48C], rbx
0x10172990a  mov     [rsp+14C8h+var_1400], rbx
0x101729912  movsd   xmm0, [rsp+14C8h+var_1400]
0x10172991b  movsd   [rsp+14C8h+var_484], xmm0
0x101729924  mov     [rsp+14C8h+var_47C], rbx
0x10172992c  movsd   [rsp+14C8h+var_474], xmm0
0x101729935  mov     [rsp+14C8h+var_46C], rbx
0x10172993d  mov     [rsp+14C8h+var_450], rbx
0x101729945  mov     [rsp+14C8h+var_13D0], rbx
0x10172994d  mov     [rsp+14C8h+var_1410], ebx
0x101729954  mov     r12, cs:__imp_?hdl_prntbackout@@YAHHHHHPEAD@Z; hdl_prntbackout(int,int,int,int,char *)
0x10172995b  mov     [rsp+14C8h+var_1148], rbx
0x101729963  mov     rdx, gs:58h
0x10172996c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101729973  mov     ecx, [rax]
0x101729975  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10172997c  mov     eax, [rax]
0x10172997e  add     rax, [rdx+rcx*8]
0x101729982  mov     rax, [rax+8]
0x101729986  mov     rcx, [rax+60h]
0x10172998a  mov     rax, [rcx+4F8h]
0x101729991  mov     [rsp+14C8h+var_1458], rax
0x101729996  mov     [rcx+4F8h], r15
0x10172999d  mov     [rsp+14C8h+var_B98], rax
0x1017299a5  mov     [rsp+14C8h+var_1380], ebx
0x1017299ac  mov     rdx, gs:58h
0x1017299b5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1017299bc  mov     ecx, [rax]
0x1017299be  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1017299c5  mov     edi, [rax]
0x1017299c7  add     rdi, [rdx+rcx*8]
0x1017299cb  mov     rdx, [rdi+100h]
0x1017299d2  mov     [rsp+14C8h+var_1460], rdx
0x1017299d7  test    rdx, rdx
0x1017299da  jnz     short loc_1017299F0
0x1017299dc  xor     ecx, ecx
0x1017299de  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1017299e4  mov     rdx, [rdi+100h]
0x1017299eb  mov     [rsp+14C8h+var_1460], rdx
0x1017299f0  mov     [rsp+14C8h+var_1378], rdx
0x1017299f8  mov     ecx, [rdx+268h]
0x1017299fe  mov     eax, ecx
0x101729a00  and     eax, 1
0x101729a03  xor     eax, 1
0x101729a06  mov     [rsp+14C8h+var_1380], eax
0x101729a0d  or      ecx, 1
0x101729a10  mov     [rdx+268h], ecx
0x101729a16  mov     rax, [rsp+14C8h+var_1468]
0x101729a1b  mov     [r13+28h], rax
0x101729a1f  lea     rax, [r15+38h]
0x101729a23  mov     rcx, r13
0x101729a26  mov     edx, 3
0x101729a2b  nop     dword ptr [rax+rax+00h]
0x101729a30  movups  xmm0, xmmword ptr [rcx]
0x101729a33  movups  xmmword ptr [rax], xmm0
0x101729a36  movups  xmm1, xmmword ptr [rcx+10h]
0x101729a3a  movups  xmmword ptr [rax+10h], xmm1
0x101729a3e  movups  xmm0, xmmword ptr [rcx+20h]
0x101729a42  movups  xmmword ptr [rax+20h], xmm0
0x101729a46  movups  xmm1, xmmword ptr [rcx+30h]
0x101729a4a  movups  xmmword ptr [rax+30h], xmm1
0x101729a4e  movups  xmm0, xmmword ptr [rcx+40h]
0x101729a52  movups  xmmword ptr [rax+40h], xmm0
0x101729a56  movups  xmm1, xmmword ptr [rcx+50h]
0x101729a5a  movups  xmmword ptr [rax+50h], xmm1
0x101729a5e  movups  xmm0, xmmword ptr [rcx+60h]
0x101729a62  movups  xmmword ptr [rax+60h], xmm0
0x101729a66  lea     rax, [rax+80h]
0x101729a6d  movups  xmm1, xmmword ptr [rcx+70h]
0x101729a71  movups  xmmword ptr [rax-10h], xmm1
0x101729a75  lea     rcx, [rcx+80h]
0x101729a7c  sub     rdx, 1; unsigned __int16
0x101729a80  jnz     short loc_101729A30
0x101729a82  movups  xmm0, xmmword ptr [rcx]
0x101729a85  movups  xmmword ptr [rax], xmm0
0x101729a88  movups  xmm1, xmmword ptr [rcx+10h]
0x101729a8c  movups  xmmword ptr [rax+10h], xmm1
0x101729a90  movups  xmm0, xmmword ptr [rcx+20h]
0x101729a94  movups  xmmword ptr [rax+20h], xmm0
0x101729a98  movups  xmm1, xmmword ptr [rcx+30h]
0x101729a9c  movups  xmmword ptr [rax+30h], xmm1
0x101729aa0  movups  xmm0, xmmword ptr [rcx+40h]
0x101729aa4  movups  xmmword ptr [rax+40h], xmm0
0x101729aa8  movups  xmm1, xmmword ptr [rcx+50h]
0x101729aac  movups  xmmword ptr [rax+50h], xmm1
0x101729ab0  test    byte ptr [r15+39h], 8
0x101729ab5  lea     rax, ?HandleAllAndPrintSpecificStartupErrors@@YAHHHHHPEAD@Z; HandleAllAndPrintSpecificStartupErrors(int,int,int,int,char *)
0x101729abc  cmovnz  r12, rax
0x101729ac0  mov     [rsp+14C8h+var_14A0], rbx; struct Worker *
0x101729ac5  mov     [rsp+14C8h+var_14A8], r12; int (*)(int, int, int, int, char *)
0x101729aca  xor     r9d, r9d; unsigned __int8
0x101729acd  xor     r8d, r8d; unsigned __int8
0x101729ad0  lea     rcx, [rsp+14C8h+var_FC8]; this
0x101729ad8  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x101729add  nop
0x101729ade  movzx   eax, cs:byte_1031852E4
0x101729ae5  mov     [rsp+14C8h+var_1424], al
0x101729aec  test    al, al
0x101729aee  jz      short loc_101729AFA
0x101729af0  cmp     qword ptr [r15+14C8h], 0
0x101729af8  jnz     short loc_101729B12
0x101729afa  lea     r8, [r15+3A8h]
0x101729b01  mov     edx, [r15+3A0h]
0x101729b08  mov     ecx, 42F1h; unsigned int
0x101729b0d  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x101729b12  mov     rdx, [r15+280h]
0x101729b19  test    rdx, rdx
0x101729b1c  jz      short loc_101729B66
0x101729b1e  mov     ecx, [rdx+278h]
0x101729b24  mov     eax, ecx
0x101729b26  shr     eax, 0Dh
0x101729b29  not     al
0x101729b2b  and     al, 1
0x101729b2d  mov     [rsp+14C8h+var_1423], al
0x101729b34  bts     ecx, 0Dh
0x101729b38  mov     [rdx+278h], ecx
0x101729b3e  test    al, al
0x101729b40  jz      short loc_101729B66
0x101729b42  mov     rdx, [r15+280h]
0x101729b49  mov     esi, 1
0x101729b4e  mov     r8d, esi
0x101729b51  mov     rdx, [rdx+1210h]
0x101729b58  mov     rcx, cs:qword_10317B628
0x101729b5f  call    ?MarkBufsCopyOnWrite@BPool@@QEAAXPEAVRecoveryUnit@@W4CopyOnWriteMode@1@@Z; BPool::MarkBufsCopyOnWrite(RecoveryUnit *,BPool::CopyOnWriteMode)
0x101729b64  jmp     short loc_101729B6B
0x101729b66  mov     esi, 1
0x101729b6b  mov     rdx, r15; struct DBTABLE *
0x101729b6e  movzx   ecx, word ptr [r15+28h]; unsigned __int16
0x101729b73  call    ?NotifyDbStartup@RBPEX@@SAXGPEAVDBTABLE@@@Z; RBPEX::NotifyDbStartup(ushort,DBTABLE *)
0x101729b78  mov     rcx, [r15+88h]
0x101729b7f  mov     [rsp+14C8h+var_B90], rcx
0x101729b87  test    rcx, rcx
0x101729b8a  jnz     short loc_101729B95
0x101729b8c  mov     [rsp+14C8h+var_1368], ebx
0x101729b93  jmp     short loc_101729BD1
0x101729b95  lea     rax, [rsp+14C8h+var_1138]
0x101729b9d  mov     [rsp+14C8h+var_14A0], rax
0x101729ba2  lea     rax, [rsp+14C8h+var_1140]
0x101729baa  mov     [rsp+14C8h+var_14A8], rax
0x101729baf  lea     r9, [rsp+14C8h+var_1148]
0x101729bb7  lea     r8, GUID_NULL
0x101729bbe  mov     edx, esi
0x101729bc0  call    ?RemapLogicalFile@FileMgr@@SA?AW4Action@RemapFileEntry@@PEAV3@JAEBU_GUID@@AEAPEAV3@PEAPEB_WPEA_K@Z; FileMgr::RemapLogicalFile(RemapFileEntry *,long,_GUID const &,RemapFileEntry * &,wchar_t const * *,unsigned __int64 *)
0x101729bc5  mov     [rsp+14C8h+var_1368], eax
0x101729bcc  cmp     eax, 1
0x101729bcf  jz      short loc_101729BF2
0x101729bd1  mov     [rsp+14C8h+var_14A8], rbx
0x101729bd6  mov     r9d, 919h
0x101729bdc  lea     r8, aDbtableCpp; "dbtable.cpp"
0x101729be3  lea     rdx, aRemapfileentry; "RemapFileEntry::RfeMove == remapAction"
0x101729bea  mov     ecx, esi
0x101729bec  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101729bf2  cmp     cs:dword_103172528, 0
0x101729bf9  jnz     short loc_101729C04
0x101729bfb  cmp     cs:dword_1031852C8, 0
0x101729c02  jz      short loc_101729C4D
0x101729c04  cmp     qword ptr [r15+14C0h], 0
0x101729c0c  jz      short loc_101729C4D
0x101729c0e  cmp     dword ptr [r13+8], 2
0x101729c13  jnz     short loc_101729C4D
0x101729c15  cmp     byte ptr [r13+3], 0
0x101729c1a  jl      short loc_101729C4D
0x101729c1c  mov     rcx, [r15+1210h]; this
0x101729c23  call    ?SetInfiniteLeaseIdsFromReplicaController@RecoveryUnit@@QEAA_NXZ; RecoveryUnit::SetInfiniteLeaseIdsFromReplicaController(void)
0x101729c28  test    al, al
0x101729c2a  jnz     short loc_101729C4D
0x101729c2c  mov     [rsp+14C8h+var_14A8], rbx
0x101729c31  mov     r9d, 92Ah
0x101729c37  lea     r8, aDbtableCpp; "dbtable.cpp"
0x101729c3e  lea     rdx, aGetprimarypruS; "GetPrimaryPru ()->SetInfiniteLeaseIdsFr"...
0x101729c45  mov     ecx, esi
0x101729c47  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101729c4d  movzx   eax, byte ptr [r15+3Ch]
0x101729c52  test    al, 4
0x101729c54  jz      short loc_101729C69
0x101729c56  xor     edx, edx; bool
0x101729c58  mov     rcx, [r15+1210h]; this
0x101729c5f  call    ?SetIsLogReplica@RecoveryUnit@@QEAAX_N@Z; RecoveryUnit::SetIsLogReplica(bool)
0x101729c64  movzx   eax, byte ptr [r15+3Ch]
0x101729c69  test    al, 8
0x101729c6b  jz      short loc_101729C83
0x101729c6d  mov     rax, [r15+1210h]
0x101729c74  mov     [rsp+14C8h+var_B88], rax
0x101729c7c  or      byte ptr [rax+1CD0h], 40h
0x101729c83  movzx   eax, cs:byte_1031852E4
0x101729c8a  mov     [rsp+14C8h+var_1422], al
0x101729c91  test    al, al
0x101729c93  jz      short loc_101729CA3
0x101729c95  cmp     qword ptr [r15+14C8h], 0
0x101729c9d  jnz     loc_101729EE7
0x101729ca3  xor     r8d, r8d; struct FCBAllocDirectives *
0x101729ca6  mov     rdi, [rsp+14C8h+var_1140]
0x101729cae  mov     rdx, rdi; wchar_t *
0x101729cb1  mov     rcx, [r15+2B0h]; struct IMemObj *
0x101729cb8  call    ?DBAllocFCB@@YAPEAVFCB@@PEAVIMemObj@@PEB_WPEBUFCBAllocDirectives@@@Z; DBAllocFCB(IMemObj *,wchar_t const *,FCBAllocDirectives const *)
0x101729cbd  mov     r14, rax
0x101729cc0  mov     [rsp+14C8h+var_13D0], rax
0x101729cc8  mov     r10, [rax]
0x101729ccb  mov     r9d, esi
0x101729cce  xor     r8d, r8d
0x101729cd1  mov     [rsp+14C8h+var_1480], esi
0x101729cd5  mov     [rsp+14C8h+var_1488], 2
0x101729cdd  mov     rcx, [rsp+14C8h+var_1138]
0x101729ce5  mov     [rsp+14C8h+var_1490], rcx
0x101729cea  mov     [rsp+14C8h+var_1498], rdi
0x101729cef  mov     [rsp+14C8h+var_14A0], rbx
0x101729cf4  lea     rax, word_10280BED8
0x101729cfb  mov     [rsp+14C8h+var_14A8], rax
0x101729d00  movzx   edx, word ptr [r15+28h]
0x101729d05  mov     rcx, r14
0x101729d08  call    qword ptr [r10+68h]
0x101729d0c  mov     [r14+84h], si
0x101729d14  mov     [rsp+14C8h+var_B80], rbx
0x101729d1c  xor     edx, edx; unsigned __int16
0x101729d1e  mov     [rsp+14C8h+var_14A0], rbx; struct Worker *
0x101729d23  mov     [rsp+14C8h+var_14A8], r12; int (*)(int, int, int, int, char *)
0x101729d28  xor     r9d, r9d; unsigned __int8
0x101729d2b  xor     r8d, r8d; unsigned __int8
0x101729d2e  lea     rcx, [rsp+14C8h+var_A80]; this
0x101729d36  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x101729d3b  nop
0x101729d3c  lea     rdx, [r15+38h]; struct DatabaseStartupInfo *
0x101729d40  mov     rcx, r14; this
0x101729d43  call    ?StartPrimaryFile@FCB@@QEAAXAEAVDatabaseStartupInfo@@@Z; FCB::StartPrimaryFile(DatabaseStartupInfo &)
0x101729d48  mov     rax, [r15+1210h]
0x101729d4f  mov     rcx, [rax+6A0h]
0x101729d56  mov     [rsp+14C8h+var_B78], rcx
0x101729d5e  or      dword ptr [rcx+88h], 20h
0x101729d65  lea     rcx, [rsp+14C8h+var_A80]; this
0x101729d6d  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x101729d72  nop
0x101729d73  jmp     short loc_101729D8A
0x101729d75  xor     ebx, ebx
0x101729d77  lea     esi, [rbx+1]
0x101729d7a  mov     r15, [rsp+14C8h+var_13C8]
0x101729d82  mov     r13, [rsp+14C8h+var_1408]
0x101729d8a  mov     [rsp+14C8h+var_1068], 58h ; 'X'
0x101729d95  mov     rdx, gs:58h
0x101729d9e  mov     [rsp+14C8h+var_B38], rdx
0x101729da6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101729dad  mov     ecx, [rax]
0x101729daf  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101729db6  mov     edi, [rax]
0x101729db8  add     rdi, [rdx+rcx*8]
0x101729dbc  mov     [rsp+14C8h+var_B28], rdi
0x101729dc4  mov     rcx, [rdi+100h]
0x101729dcb  mov     [rsp+14C8h+var_1130], rcx
0x101729dd3  test    rcx, rcx
0x101729dd6  jnz     short loc_101729DED
0x101729dd8  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101729dde  mov     rcx, [rdi+100h]
0x101729de5  mov     [rsp+14C8h+var_1130], rcx
0x101729ded  mov     [rsp+14C8h+var_B10], rcx
0x101729df5  cmp     dword ptr [rcx+22Ch], 0
0x101729dfc  jz      short loc_101729E04
0x101729dfe  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x101729e04  mov     rcx, [r15+1210h]
0x101729e0b  mov     rax, [rsp+14C8h+var_13D0]
0x101729e13  mov     r8, rax; struct FCB *
  ... truncated ...
```
