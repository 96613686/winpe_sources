# CSbMsgDispatcher::DispatchRecvMessages(CSbMsgDispatcher::CSbMsgDispatcherTask * const)

- ea: `0x100944db0`
- end: `0x100947ac6`
- name: `?DispatchRecvMessages@CSbMsgDispatcher@@QEAA_NQEAVCSbMsgDispatcherTask@1@@Z`
- size: `11542`
- prototype: `bool __fastcall(CSbMsgDispatcher *__hidden this, struct CSbMsgDispatcher::CSbMsgDispatcherTask *const)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x10093e0c0`

## callees

- `0x100401070`
- `0x100401090`
- `0x1004012d0`
- `0x100401340`
- `0x100401450`
- `0x100406280`
- `0x100409cb0`
- `0x1004223e0`
- `0x10083a160`
- `0x10083a1d0`
- `0x10083a3f0`
- `0x10083a660`
- `0x100854330`
- `0x100854550`
- `0x1008547c0`
- `0x100867690`
- `0x1008677f0`
- `0x10086bfb0`
- `0x10093f980`
- `0x100940900`
- `0x100940ab0`
- `0x100940c90`
- `0x100940e70`
- `0x100941040`
- `0x100944db0`
- `0x10094d070`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10094532b`
- `KERNEL32!QueryPerformanceCounter` at `0x1009453fe`
- `KERNEL32!QueryPerformanceCounter` at `0x100945d64`
- `KERNEL32!QueryPerformanceCounter` at `0x100945e31`
- `KERNEL32!QueryPerformanceCounter` at `0x1009461aa`
- `KERNEL32!QueryPerformanceCounter` at `0x100946277`
- `KERNEL32!QueryPerformanceCounter` at `0x100946c8a`
- `KERNEL32!QueryPerformanceCounter` at `0x100946ce8`
- `KERNEL32!QueryPerformanceCounter` at `0x100946e40`
- `KERNEL32!QueryPerformanceCounter` at `0x100946e99`
- `KERNEL32!QueryPerformanceCounter` at `0x1009470ca`
- `KERNEL32!QueryPerformanceCounter` at `0x100947128`
- `KERNEL32!QueryPerformanceCounter` at `0x100947280`
- `KERNEL32!QueryPerformanceCounter` at `0x1009472d9`
- `KERNEL32!QueryPerformanceCounter` at `0x100947571`
- `KERNEL32!QueryPerformanceCounter` at `0x1009475cf`
- `KERNEL32!QueryPerformanceCounter` at `0x1009476fd`
- `KERNEL32!QueryPerformanceCounter` at `0x100947758`
- `KERNEL32!QueryPerformanceCounter` at `0x10094532b`
- `KERNEL32!QueryPerformanceCounter` at `0x1009453fe`
- `KERNEL32!QueryPerformanceCounter` at `0x100945d64`
- `KERNEL32!QueryPerformanceCounter` at `0x100945e31`
- `KERNEL32!QueryPerformanceCounter` at `0x1009461aa`
- `KERNEL32!QueryPerformanceCounter` at `0x100946277`
- `KERNEL32!QueryPerformanceCounter` at `0x100946c8a`
- `KERNEL32!QueryPerformanceCounter` at `0x100946ce8`
- `KERNEL32!QueryPerformanceCounter` at `0x100946e40`
- `KERNEL32!QueryPerformanceCounter` at `0x100946e99`
- `KERNEL32!QueryPerformanceCounter` at `0x1009470ca`
- `KERNEL32!QueryPerformanceCounter` at `0x100947128`
- `KERNEL32!QueryPerformanceCounter` at `0x100947280`
- `KERNEL32!QueryPerformanceCounter` at `0x1009472d9`
- `KERNEL32!QueryPerformanceCounter` at `0x100947571`
- `KERNEL32!QueryPerformanceCounter` at `0x1009475cf`
- `KERNEL32!QueryPerformanceCounter` at `0x1009476fd`
- `KERNEL32!QueryPerformanceCounter` at `0x100947758`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x100945a45`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100946665`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10094669b`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10094688c`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x1009468c4`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x1009468fe`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x100946936`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x100946970`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x1009469a8`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x100946a0b`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x100946873`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100945392`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100945dc5`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10094620e`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100946ca2`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100946e58`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x1009470e2`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100947298`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100947589`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100947715`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100945260`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100945c99`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1009460df`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100946c28`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100946dde`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100947068`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10094721e`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10094750f`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10094769b`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1009454e3`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100945640`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10094577d`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100945fa5`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1009463cc`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100946d48`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100946f79`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100947188`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1009473be`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10094760b`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1009477f3`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100947918`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1009479d6`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10094530f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1009453e2`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100945d48`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100945e15`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10094618e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10094625b`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100946c76`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100946cd4`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100946e2c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100946e85`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1009470b6`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100947114`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10094726c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1009472c5`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10094755d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1009475bb`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1009476e9`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100947744`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x100945030`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x10094787c`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100947a5f`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x10094787c`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100947a5f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100945943`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100945943`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100946770`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1009467fe`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100946acb`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100946770`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1009467fe`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100946acb`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100945193`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100945193`
- `sqldk!SystemThread_TlsIndex` at `0x100944f8a`
- `sqldk!SystemThread_TlsIndex` at `0x10094511c`
- `sqldk!SystemThread_TlsIndex` at `0x10094529e`
- `sqldk!SystemThread_TlsIndex` at `0x10094583b`
- `sqldk!SystemThread_TlsIndex` at `0x1009458a4`
- `sqldk!SystemThread_TlsIndex` at `0x1009459d7`
- `sqldk!SystemThread_TlsIndex` at `0x100945a7a`
- `sqldk!SystemThread_TlsIndex` at `0x100945cd7`
- `sqldk!SystemThread_TlsIndex` at `0x10094611d`
- `sqldk!SystemThread_TlsIndex` at `0x1009464a8`
- `sqldk!SystemThread_TlsIndex` at `0x100946718`
- `sqldk!SystemThread_TlsIndex` at `0x1009467c6`
- `sqldk!SystemThread_TlsIndex` at `0x100946a93`
- `sqldk!SystemThread_TlsIndex` at `0x100946c48`
- `sqldk!SystemThread_TlsIndex` at `0x100946dfe`
- `sqldk!SystemThread_TlsIndex` at `0x100947088`
- `sqldk!SystemThread_TlsIndex` at `0x10094723e`
- `sqldk!SystemThread_TlsIndex` at `0x10094752f`
- `sqldk!SystemThread_TlsIndex` at `0x1009476bb`
- `sqldk!SystemThread_TlsOffset` at `0x100944f93`
- `sqldk!SystemThread_TlsOffset` at `0x100945125`
- `sqldk!SystemThread_TlsOffset` at `0x1009452a7`
- `sqldk!SystemThread_TlsOffset` at `0x100945844`
- `sqldk!SystemThread_TlsOffset` at `0x1009458ad`
- `sqldk!SystemThread_TlsOffset` at `0x1009459e0`
- `sqldk!SystemThread_TlsOffset` at `0x100945a83`
- `sqldk!SystemThread_TlsOffset` at `0x100945ce0`
- `sqldk!SystemThread_TlsOffset` at `0x100946126`
- `sqldk!SystemThread_TlsOffset` at `0x1009464b1`
- `sqldk!SystemThread_TlsOffset` at `0x100946721`
- `sqldk!SystemThread_TlsOffset` at `0x1009467cf`
- `sqldk!SystemThread_TlsOffset` at `0x100946a9c`
- `sqldk!SystemThread_TlsOffset` at `0x100946c51`
- `sqldk!SystemThread_TlsOffset` at `0x100946e07`
- `sqldk!SystemThread_TlsOffset` at `0x100947091`
- `sqldk!SystemThread_TlsOffset` at `0x100947247`
- `sqldk!SystemThread_TlsOffset` at `0x100947538`
- `sqldk!SystemThread_TlsOffset` at `0x1009476c4`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1009451b6`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1009455ec`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100945749`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100947894`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100947a77`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1009451b6`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1009455ec`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100945749`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100947894`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100947a77`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100945150`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009464dc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10094674a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009467e8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100946ab5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100945150`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009464dc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10094674a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009467e8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100946ab5`
- `sqlTsEs!?DateAdd@SQLDATE@@QEAAJJJ@Z` at `0x10094580a`
- `sqlTsEs!?DateAdd@SQLDATE@@QEAAJJJ@Z` at `0x10094580a`
- `sqlTsEs!?DateDiff@SQLDATE@@QEBAJJPEBU1@PEAJ@Z` at `0x100946862`
- `sqlTsEs!?DateDiff@SQLDATE@@QEBAJJPEBU1@PEAJ@Z` at `0x100946862`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009454f8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100945655`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100945792`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100945fba`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009463e1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100946d54`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100946f85`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100947194`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009473ca`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100947617`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009477ff`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100947924`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009479e2`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009454f8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100945655`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100945792`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100945fba`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009463e1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100946d54`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100946f85`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100947194`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009473ca`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100947617`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009477ff`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100947924`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009479e2`
- `sqlmin!?utgettime@@YAXPEAUSQLDATEBASE@@HPEA_N@Z` at `0x100945022`

## string_xrefs

- `0x100945187`: `sql\ntdbms\broker\src\ssbdispatcher.cpp`
- `0x100945a33`: `sql\ntdbms\broker\src\ssbdispatcher.cpp`
- `0x100945939`: `rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=32 #try_helpers=2
char __fastcall CSbMsgDispatcher::DispatchRecvMessages(
        CSbMsgDispatcher *this,
        struct CSbMsgDispatcher::CSbMsgDispatcherTask *const a2)
{
  CSbMsgDispatcher *v2; // r12
  __int64 v3; // rcx
  void ***v4; // rdx
  __int64 v5; // rbx
  __int64 v6; // rax
  void *v7; // rbx
  BOOL v8; // ecx
  __int64 v9; // rbx
  bool v10; // zf
  __int64 v11; // rbx
  __int64 v13; // rbx
  CSbTransportMgr *QuadPart; // rax
  volatile signed __int64 *v15; // rsi
  CSbTransportMgr *v16; // rax
  signed __int64 v17; // rax
  int v18; // r8d
  __int64 v19; // rdx
  int v21; // r8d
  __int64 v22; // rdx
  int v23; // r8d
  char v24; // si
  CSbMsgDispatcher::CSbReceivedDialog *v25; // rax
  CSbMsgDispatcher::CSbReceivedDialog *v26; // rbx
  _QWORD *v27; // rdx
  _QWORD *v28; // rcx
  __int64 v29; // rax
  char **v30; // rax
  BOOL v31; // ecx
  __int64 v32; // rbx
  __int64 v33; // rbx
  __int64 v35; // rbx
  CSbTransportMgr *v36; // rax
  volatile signed __int64 *v37; // r14
  CSbTransportMgr *v38; // rax
  signed __int64 v39; // rax
  CSbMsgDispatcher *v40; // rsi
  CSbMsgDispatcher::CSbReceivedDialog *v41; // rsi
  CSbMsgDispatcher::CSbReceivedDialog *v42; // r8
  _QWORD *v43; // rcx
  __int64 v44; // rax
  int v45; // r8d
  BOOL v46; // ecx
  __int64 v47; // rbx
  __int64 v48; // rbx
  __int64 v50; // rbx
  CSbTransportMgr *v51; // rax
  CSbTransportMgr *v52; // rax
  signed __int64 v53; // rax
  CSbMsgDispatcher *v54; // rbx
  CSbMsgDispatcher::CSbReceivedDialog *v55; // r8
  _QWORD *v56; // rcx
  __int64 v57; // rax
  int v58; // r8d
  __int64 v59; // rbx
  _QWORD *v60; // r8
  unsigned __int64 v61; // rax
  unsigned __int64 v62; // rdx
  __int64 v64; // rcx
  int v65; // eax
  int v68; // ecx
  struct Worker *v69; // rcx
  __int64 v70; // rbx
  __int64 v71; // rbx
  struct Worker *v72; // rcx
  unsigned __int8 i; // bl
  int v74; // ecx
  __int64 v75; // rbx
  struct Worker *v76; // rcx
  char v77; // si
  char **v78; // rcx
  CSbMsgDispatcher::CSbReceivedDialog *v79; // rbx
  char **v80; // rcx
  char **v81; // r15
  char **v82; // rdx
  __int64 *v83; // r14
  char **v84; // rcx
  CSbTransportMgr *v85; // rbx
  signed __int64 v86; // r12
  __int64 v87; // rsi
  __int64 v88; // r8
  CSbTransportMgr *v89; // rax
  signed __int64 v90; // rax
  _QWORD *v91; // rcx
  __int64 v92; // rax
  int v93; // r8d
  CSbTransportMgr *v94; // rbx
  signed __int64 v95; // r15
  __int64 v96; // rsi
  __int64 v97; // r8
  char *v98; // rcx
  CSbTransportMgr *v99; // rax
  signed __int64 v100; // rax
  CSbMsgDispatcher *v101; // rcx
  char *v102; // rdx
  _QWORD *v103; // rcx
  __int64 v104; // rax
  int v105; // r8d
  char **v106; // r15
  char **v107; // rdx
  __int64 *v108; // r14
  char **v109; // rcx
  CSbTransportMgr *v110; // rbx
  signed __int64 v111; // r12
  __int64 v112; // rsi
  __int64 v113; // r8
  CSbTransportMgr *v114; // rax
  signed __int64 v115; // rax
  _QWORD *v116; // rcx
  __int64 v117; // rax
  int v118; // r8d
  CSbTransportMgr *v119; // rbx
  signed __int64 v120; // r15
  __int64 v121; // rsi
  __int64 v122; // r8
  char *v123; // rcx
  CSbTransportMgr *v124; // rax
  signed __int64 v125; // rax
  CSbMsgDispatcher *v126; // rcx
  char *v127; // rdx
  _QWORD *v128; // rcx
  __int64 v129; // rax
  int v130; // r8d
  CSbMsgDispatcher::CSbReceivedDialog *v131; // rbx
  _QWORD *v132; // rdx
  __int64 v133; // rax
  char **v134; // rcx
  volatile signed __int64 *v135; // rsi
  _QWORD *v136; // rcx
  __int64 v137; // rax
  CSbTransportMgr *v138; // rbx
  signed __int64 v139; // r15
  __int64 v140; // r14
  __int64 v141; // r8
  CSbTransportMgr *v142; // rax
  signed __int64 v143; // rax
  int v144; // r8d
  CSbTransportMgr *v145; // rbx
  signed __int64 v146; // r14
  __int64 v147; // rsi
  __int64 v148; // r8
  CSbTransportMgr *v149; // rax
  signed __int64 v150; // rax
  __int64 v151; // rdx
  int v152; // r8d
  _QWORD *v153; // rcx
  __int64 v154; // rax
  int v155; // ecx
  _BYTE *v156; // rdx
  char *v157; // rbx
  int v158; // r8d
  char *v159; // rbx
  struct IUnknown *v160; // r8
  __int64 v161; // rdx
  int v162; // r8d
  _QWORD *v163; // rcx
  __int64 v164; // rax
  __int64 v165; // r9
  char v166; // [rsp+50h] [rbp-1A18h]
  volatile signed __int64 *v167; // [rsp+58h] [rbp-1A10h] BYREF
  int v168; // [rsp+60h] [rbp-1A08h]
  unsigned __int8 v169; // [rsp+68h] [rbp-1A00h]
  CSbMsgDispatcher::CSbReceivedDialog *v170; // [rsp+70h] [rbp-19F8h]
  char *v171; // [rsp+78h] [rbp-19F0h]
  char *v172; // [rsp+80h] [rbp-19E8h] BYREF
  char **v173; // [rsp+88h] [rbp-19E0h]
  bool v174; // [rsp+90h] [rbp-19D8h]
  char v175; // [rsp+91h] [rbp-19D7h]
  bool v176; // [rsp+92h] [rbp-19D6h]
  char v177; // [rsp+93h] [rbp-19D5h]
  bool v178; // [rsp+94h] [rbp-19D4h]
  bool v179; // [rsp+95h] [rbp-19D3h]
  bool v180; // [rsp+96h] [rbp-19D2h]
  bool v181; // [rsp+97h] [rbp-19D1h]
  bool v182; // [rsp+98h] [rbp-19D0h]
  bool v183; // [rsp+99h] [rbp-19CFh]
  bool v184; // [rsp+9Ah] [rbp-19CEh]
  bool v185; // [rsp+9Bh] [rbp-19CDh]
  bool v186; // [rsp+9Ch] [rbp-19CCh]
  bool v187; // [rsp+9Dh] [rbp-19CBh]
  bool v188; // [rsp+9Eh] [rbp-19CAh]
  char *v189; // [rsp+A0h] [rbp-19C8h] BYREF
  char **v190; // [rsp+A8h] [rbp-19C0h]
  __int128 v191; // [rsp+B0h] [rbp-19B8h]
  __int128 v192; // [rsp+C0h] [rbp-19A8h]
  int v193; // [rsp+D0h] [rbp-1998h]
  int v194; // [rsp+D4h] [rbp-1994h] BYREF
  CSbMsgDispatcher *v195; // [rsp+D8h] [rbp-1990h]
  __int64 v196; // [rsp+E0h] [rbp-1988h] BYREF
  int v197; // [rsp+E8h] [rbp-1980h]
  __int128 v198; // [rsp+F0h] [rbp-1978h]
  __int64 v199; // [rsp+100h] [rbp-1968h] BYREF
  __int128 v200; // [rsp+108h] [rbp-1960h] BYREF
  unsigned int v201; // [rsp+118h] [rbp-1950h]
  char *v202; // [rsp+120h] [rbp-1948h]
  __int64 v203; // [rsp+128h] [rbp-1940h]
  __int64 v204; // [rsp+130h] [rbp-1938h]
  __int64 v205; // [rsp+138h] [rbp-1930h]
  volatile signed __int64 *v206; // [rsp+140h] [rbp-1928h]
  int v207; // [rsp+148h] [rbp-1920h]
  volatile signed __int64 *v208; // [rsp+150h] [rbp-1918h]
  int v209; // [rsp+158h] [rbp-1910h]
  volatile signed __int64 *v210; // [rsp+160h] [rbp-1908h]
  int v211; // [rsp+168h] [rbp-1900h]
  BOOL v212; // [rsp+170h] [rbp-18F8h]
  int v213; // [rsp+178h] [rbp-18F0h]
  signed __int64 UniqueThread_low; // [rsp+180h] [rbp-18E8h]
  signed __int64 v215; // [rsp+188h] [rbp-18E0h]
  CSbTransportMgr *v216; // [rsp+190h] [rbp-18D8h] BYREF
  CSbTransportMgr *v217; // [rsp+198h] [rbp-18D0h] BYREF
  CSbTransportMgr *v218; // [rsp+1A0h] [rbp-18C8h] BYREF
  CSbMsgDispatcher *v219; // [rsp+1A8h] [rbp-18C0h]
  void *v220; // [rsp+1B0h] [rbp-18B8h]
  CSbTransportMgr *v221; // [rsp+1B8h] [rbp-18B0h] BYREF
  CSbTransportMgr *v222; // [rsp+1C0h] [rbp-18A8h] BYREF
  signed __int64 v223; // [rsp+1C8h] [rbp-18A0h]
  void *v224; // [rsp+1E8h] [rbp-1880h]
  CSbTransportMgr *v225; // [rsp+1F0h] [rbp-1878h] BYREF
  _QWORD v226[2]; // [rsp+1F8h] [rbp-1870h] BYREF
  int v227; // [rsp+208h] [rbp-1860h] BYREF
  __int64 v228; // [rsp+210h] [rbp-1858h]
  CSbTransportMgr *v229; // [rsp+218h] [rbp-1850h] BYREF
  __int64 v230; // [rsp+220h] [rbp-1848h]
  CSbTransportMgr *v231; // [rsp+228h] [rbp-1840h] BYREF
  CSbMsgDispatcher::CSbReceivedDialog *v232; // [rsp+230h] [rbp-1838h]
  __int64 v233; // [rsp+238h] [rbp-1830h]
  CSbTransportMgr *v234; // [rsp+240h] [rbp-1828h] BYREF
  __int16 *v235; // [rsp+248h] [rbp-1820h] BYREF
  __int64 v236; // [rsp+250h] [rbp-1818h]
  char v237; // [rsp+258h] [rbp-1810h]
  _QWORD *v238; // [rsp+260h] [rbp-1808h]
  int k; // [rsp+268h] [rbp-1800h]
  _QWORD *v240; // [rsp+270h] [rbp-17F8h]
  int j; // [rsp+278h] [rbp-17F0h]
  int v242; // [rsp+280h] [rbp-17E8h]
  BOOL v243; // [rsp+284h] [rbp-17E4h]
  int v244; // [rsp+288h] [rbp-17E0h]
  int v245; // [rsp+28Ch] [rbp-17DCh]
  int v246; // [rsp+290h] [rbp-17D8h]
  int v247; // [rsp+294h] [rbp-17D4h]
  int v248; // [rsp+298h] [rbp-17D0h]
  int v249; // [rsp+29Ch] [rbp-17CCh]
  BOOL v250; // [rsp+2A0h] [rbp-17C8h]
  int v251; // [rsp+2A4h] [rbp-17C4h]
  int v252; // [rsp+2A8h] [rbp-17C0h]
  BOOL v253; // [rsp+2ACh] [rbp-17BCh]
  int v254; // [rsp+2B0h] [rbp-17B8h]
  int v255; // [rsp+2B4h] [rbp-17B4h]
  BOOL v256; // [rsp+2B8h] [rbp-17B0h]
  int v257; // [rsp+2BCh] [rbp-17ACh]
  int v258; // [rsp+2C0h] [rbp-17A8h]
  __int64 v259; // [rsp+2C8h] [rbp-17A0h]
  LARGE_INTEGER PerformanceCount; // [rsp+2D0h] [rbp-1798h] BYREF
  LARGE_INTEGER v261; // [rsp+2D8h] [rbp-1790h] BYREF
  int v262; // [rsp+2E0h] [rbp-1788h]
  struct IMemObj *v263; // [rsp+2E8h] [rbp-1780h]
  __int64 v264; // [rsp+2F0h] [rbp-1778h]
  char **v265; // [rsp+2F8h] [rbp-1770h]
  char **v266; // [rsp+300h] [rbp-1768h]
  __int64 v267; // [rsp+308h] [rbp-1760h]
  CSbMsgDispatcher::CSbReceivedDialog *v268; // [rsp+310h] [rbp-1758h]
  LARGE_INTEGER v269; // [rsp+318h] [rbp-1750h] BYREF
  LARGE_INTEGER v270; // [rsp+320h] [rbp-1748h] BYREF
  __int64 v271; // [rsp+328h] [rbp-1740h]
  LARGE_INTEGER v272; // [rsp+330h] [rbp-1738h] BYREF
  LARGE_INTEGER v273; // [rsp+338h] [rbp-1730h] BYREF
  __int64 v274; // [rsp+340h] [rbp-1728h]
  CSbMsgDispatcher::CSbReceivedDialog *v275; // [rsp+348h] [rbp-1720h]
  _QWORD *v276; // [rsp+350h] [rbp-1718h]
  __int64 v277; // [rsp+358h] [rbp-1710h]
  void (__fastcall ***v278)(_QWORD, _QWORD); // [rsp+360h] [rbp-1708h]
  struct Worker *v279; // [rsp+368h] [rbp-1700h]
  int v280; // [rsp+370h] [rbp-16F8h]
  struct Worker *v281; // [rsp+378h] [rbp-16F0h]
  LARGE_INTEGER v282; // [rsp+380h] [rbp-16E8h] BYREF
  LARGE_INTEGER v283; // [rsp+388h] [rbp-16E0h] BYREF
  LARGE_INTEGER v284; // [rsp+390h] [rbp-16D8h] BYREF
  LARGE_INTEGER v285; // [rsp+398h] [rbp-16D0h] BYREF
  LARGE_INTEGER v286; // [rsp+3A0h] [rbp-16C8h] BYREF
  LARGE_INTEGER v287; // [rsp+3A8h] [rbp-16C0h] BYREF
  LARGE_INTEGER v288; // [rsp+3B0h] [rbp-16B8h] BYREF
  LARGE_INTEGER v289; // [rsp+3B8h] [rbp-16B0h] BYREF
  LARGE_INTEGER v290; // [rsp+3C0h] [rbp-16A8h] BYREF
  LARGE_INTEGER v291; // [rsp+3C8h] [rbp-16A0h] BYREF
  LARGE_INTEGER v292; // [rsp+3D0h] [rbp-1698h] BYREF
  LARGE_INTEGER v293; // [rsp+3D8h] [rbp-1690h] BYREF
  BOOL v294; // [rsp+3E0h] [rbp-1688h]
  int v295; // [rsp+3E4h] [rbp-1684h]
  struct Worker *v296; // [rsp+3E8h] [rbp-1680h]
  int v297; // [rsp+3F0h] [rbp-1678h]
  BOOL v298; // [rsp+3F4h] [rbp-1674h]
  int v299; // [rsp+3F8h] [rbp-1670h]
  int v300; // [rsp+3FCh] [rbp-166Ch]
  BOOL v301; // [rsp+400h] [rbp-1668h]
  int v302; // [rsp+404h] [rbp-1664h]
  _DWORD v303[14]; // [rsp+408h] [rbp-1660h] BYREF
  void **v304; // [rsp+440h] [rbp-1628h] BYREF
  void ***v305; // [rsp+448h] [rbp-1620h]
  int v306; // [rsp+450h] [rbp-1618h]
  __int64 v307; // [rsp+458h] [rbp-1610h]
  __int64 v308; // [rsp+460h] [rbp-1608h]
  __int64 v309; // [rsp+468h] [rbp-1600h]
  __int64 v310; // [rsp+470h] [rbp-15F8h]
  char v311; // [rsp+478h] [rbp-15F0h]
  __int64 v312; // [rsp+480h] [rbp-15E8h]
  char v313; // [rsp+490h] [rbp-15D8h]
  int v314; // [rsp+4B0h] [rbp-15B8h] BYREF
  __int64 v315; // [rsp+4B8h] [rbp-15B0h]
  __int64 v316; // [rsp+4C0h] [rbp-15A8h]
  __int64 v317; // [rsp+4C8h] [rbp-15A0h]
  __int64 v318; // [rsp+4D0h] [rbp-1598h]
  int v319; // [rsp+4D8h] [rbp-1590h] BYREF
  __int64 v320; // [rsp+4E0h] [rbp-1588h]
  __int64 v321; // [rsp+4E8h] [rbp-1580h]
  __int64 v322; // [rsp+4F0h] [rbp-1578h]
  __int64 v323; // [rsp+4F8h] [rbp-1570h]
  CSbTransportMgr *v324; // [rsp+500h] [rbp-1568h]
  CSbTransportMgr **v325; // [rsp+508h] [rbp-1560h]
  CSbTransportMgr **v326; // [rsp+510h] [rbp-1558h]
  char *v327; // [rsp+518h] [rbp-1550h]
  __int64 v328; // [rsp+520h] [rbp-1548h]
  char *v329; // [rsp+528h] [rbp-1540h]
  volatile signed __int64 *v330; // [rsp+530h] [rbp-1538h]
  volatile signed __int64 *v331; // [rsp+538h] [rbp-1530h]
  struct CSbTaskLocalStorage *v332; // [rsp+540h] [rbp-1528h]
  __int64 v333; // [rsp+548h] [rbp-1520h]
  void *v334; // [rsp+550h] [rbp-1518h]
  volatile signed __int64 *v335; // [rsp+558h] [rbp-1510h]
  volatile signed __int64 *v336; // [rsp+560h] [rbp-1508h]
  struct CSbTaskLocalStorage *v337; // [rsp+568h] [rbp-1500h]
  __int64 v338; // [rsp+570h] [rbp-14F8h]
  void *v339; // [rsp+578h] [rbp-14F0h]
  volatile signed __int64 *v340; // [rsp+580h] [rbp-14E8h]
  volatile signed __int64 *v341; // [rsp+588h] [rbp-14E0h]
  _QWORD *v342; // [rsp+590h] [rbp-14D8h]
  _QWORD *v343; // [rsp+598h] [rbp-14D0h]
  _QWORD *v344; // [rsp+5A0h] [rbp-14C8h]
  char *v345; // [rsp+5A8h] [rbp-14C0h]
  char *v346; // [rsp+5B0h] [rbp-14B8h]
  _QWORD *v347; // [rsp+5B8h] [rbp-14B0h]
  _QWORD *v348; // [rsp+5C0h] [rbp-14A8h]
  _QWORD *v349; // [rsp+5C8h] [rbp-14A0h]
  char *v350; // [rsp+5D0h] [rbp-1498h]
  char *v351; // [rsp+5D8h] [rbp-1490h]
  _QWORD *v352; // [rsp+5E0h] [rbp-1488h]
  _QWORD *v353; // [rsp+5E8h] [rbp-1480h]
  _QWORD *v354; // [rsp+5F0h] [rbp-1478h]
  char *v355; // [rsp+5F8h] [rbp-1470h]
  char *v356; // [rsp+600h] [rbp-1468h]
  __int64 v357; // [rsp+608h] [rbp-1460h]
  _QWORD *v358; // [rsp+610h] [rbp-1458h]
  _QWORD *v359; // [rsp+618h] [rbp-1450h]
  _QWORD *v360; // [rsp+620h] [rbp-1448h]
  __int64 v361; // [rsp+628h] [rbp-1440h]
  __int64 v362; // [rsp+630h] [rbp-1438h]
  __int64 v363; // [rsp+638h] [rbp-1430h]
  int *v364; // [rsp+640h] [rbp-1428h]
  char **v365; // [rsp+648h] [rbp-1420h]
  char *v366; // [rsp+650h] [rbp-1418h]
  _QWORD *v367; // [rsp+658h] [rbp-1410h]
  __int64 v368; // [rsp+660h] [rbp-1408h]
  char *v369; // [rsp+668h] [rbp-1400h]
  volatile signed __int64 *v370; // [rsp+670h] [rbp-13F8h]
  __int64 v371; // [rsp+678h] [rbp-13F0h]
  __int64 v372; // [rsp+680h] [rbp-13E8h]
  volatile signed __int64 *v373; // [rsp+688h] [rbp-13E0h]
  signed __int64 v374; // [rsp+690h] [rbp-13D8h]
  signed __int64 v375; // [rsp+698h] [rbp-13D0h]
  _QWORD *v376; // [rsp+6A0h] [rbp-13C8h]
  __int64 v377; // [rsp+6A8h] [rbp-13C0h]
  CSbTransportMgr **v378; // [rsp+6B0h] [rbp-13B8h]
  CSbTransportMgr *v379; // [rsp+6B8h] [rbp-13B0h]
  CSbTransportMgr *v380; // [rsp+6C0h] [rbp-13A8h]
  CSbTransportMgr **v381; // [rsp+6C8h] [rbp-13A0h]
  CSbTransportMgr *v382; // [rsp+6D0h] [rbp-1398h]
  CSbTransportMgr **v383; // [rsp+6D8h] [rbp-1390h]
  CSbTransportMgr **v384; // [rsp+6E0h] [rbp-1388h]
  char *v385; // [rsp+6E8h] [rbp-1380h]
  __int64 v386; // [rsp+6F0h] [rbp-1378h]
  char *v387; // [rsp+6F8h] [rbp-1370h]
  CSbMsgDispatcher::CSbReceivedDialog *v388; // [rsp+700h] [rbp-1368h]
  char *v389; // [rsp+708h] [rbp-1360h]
  _QWORD *v390; // [rsp+710h] [rbp-1358h]
  __int64 v391; // [rsp+718h] [rbp-1350h]
  volatile signed __int64 *v392; // [rsp+720h] [rbp-1348h]
  volatile signed __int64 *v393; // [rsp+728h] [rbp-1340h]
  __int64 v394; // [rsp+730h] [rbp-1338h]
  __int64 v395; // [rsp+738h] [rbp-1330h]
  volatile signed __int64 *v396; // [rsp+740h] [rbp-1328h]
  signed __int64 v397; // [rsp+748h] [rbp-1320h]
  signed __int64 v398; // [rsp+750h] [rbp-1318h]
  _QWORD *v399; // [rsp+758h] [rbp-1310h]
  __int64 v400; // [rsp+760h] [rbp-1308h]
  CSbTransportMgr **v401; // [rsp+768h] [rbp-1300h]
  CSbTransportMgr *v402; // [rsp+770h] [rbp-12F8h]
  CSbTransportMgr *v403; // [rsp+778h] [rbp-12F0h]
  CSbTransportMgr **v404; // [rsp+780h] [rbp-12E8h]
  CSbTransportMgr *v405; // [rsp+788h] [rbp-12E0h]
  CSbTransportMgr **v406; // [rsp+790h] [rbp-12D8h]
  CSbTransportMgr **v407; // [rsp+798h] [rbp-12D0h]
  char *v408; // [rsp+7A0h] [rbp-12C8h]
  __int64 v409; // [rsp+7A8h] [rbp-12C0h]
  char *v410; // [rsp+7B0h] [rbp-12B8h]
  CSbMsgDispatcher::CSbReceivedDialog *v411; // [rsp+7B8h] [rbp-12B0h]
  char *v412; // [rsp+7C0h] [rbp-12A8h]
  _QWORD *v413; // [rsp+7C8h] [rbp-12A0h]
  __int64 v414; // [rsp+7D0h] [rbp-1298h]
  volatile signed __int64 *v415; // [rsp+7D8h] [rbp-1290h]
  char *v416; // [rsp+7E0h] [rbp-1288h]
  char **v417; // [rsp+7E8h] [rbp-1280h]
  _QWORD *v418; // [rsp+7F0h] [rbp-1278h]
  __int64 v419; // [rsp+7F8h] [rbp-1270h]
  _QWORD *v420; // [rsp+800h] [rbp-1268h]
  unsigned __int64 v421; // [rsp+808h] [rbp-1260h]
  __int64 v422; // [rsp+810h] [rbp-1258h]
  __int64 v423; // [rsp+818h] [rbp-1250h]
  __int64 *v424; // [rsp+820h] [rbp-1248h]
  __int64 *v425; // [rsp+828h] [rbp-1240h]
  int *v426; // [rsp+830h] [rbp-1238h]
  int *v427; // [rsp+838h] [rbp-1230h]
  void (__fastcall ***v428)(_QWORD, _QWORD); // [rsp+840h] [rbp-1228h]
  _QWORD *v429; // [rsp+848h] [rbp-1220h]
  __int64 v430; // [rsp+850h] [rbp-1218h]
  struct CSbTaskLocalStorage *v431; // [rsp+858h] [rbp-1210h]
  __int64 v432; // [rsp+860h] [rbp-1208h]
  __int64 *v433; // [rsp+868h] [rbp-1200h]
  struct CSbTaskLocalStorage *BrokerTLS; // [rsp+870h] [rbp-11F8h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+878h] [rbp-11F0h]
  __int64 v436; // [rsp+880h] [rbp-11E8h]
  struct IMemObj *v437; // [rsp+888h] [rbp-11E0h]
  __int64 v438; // [rsp+890h] [rbp-11D8h]
  volatile signed __int64 *v439; // [rsp+898h] [rbp-11D0h]
  __int64 v440; // [rsp+8A0h] [rbp-11C8h]
  _QWORD v441[4]; // [rsp+8B8h] [rbp-11B0h] BYREF
  signed __int64 v442; // [rsp+8D8h] [rbp-1190h]
  signed __int64 v443; // [rsp+8E0h] [rbp-1188h]
  _QWORD *v444; // [rsp+8E8h] [rbp-1180h]
  __int64 v445; // [rsp+8F0h] [rbp-1178h]
  CSbTransportMgr **v446; // [rsp+8F8h] [rbp-1170h]
  CSbTransportMgr *v447; // [rsp+900h] [rbp-1168h]
  CSbTransportMgr *v448; // [rsp+908h] [rbp-1160h]
  CSbTransportMgr **v449; // [rsp+910h] [rbp-1158h]
  _BYTE v450[40]; // [rsp+940h] [rbp-1128h] BYREF
  _BYTE v451[40]; // [rsp+968h] [rbp-1100h] BYREF
  _BYTE v452[64]; // [rsp+990h] [rbp-10D8h] BYREF
  void *v453; // [rsp+9D0h] [rbp-1098h] BYREF
  __int64 v454; // [rsp+9D8h] [rbp-1090h]
  __int64 v455; // [rsp+9E0h] [rbp-1088h]
  __int64 v456; // [rsp+9E8h] [rbp-1080h] BYREF
  __int128 v457; // [rsp+9F0h] [rbp-1078h]
  __int128 v458; // [rsp+A00h] [rbp-1068h]
  __int64 v459; // [rsp+A10h] [rbp-1058h]
  __int16 v460; // [rsp+A20h] [rbp-1048h] BYREF
  int v461; // [rsp+1A20h] [rbp-48h]
  int v462; // [rsp+1A24h] [rbp-44h]
  __int64 v463; // [rsp+1A28h] [rbp-40h] BYREF

  v432 = -2;
  v2 = this;
  v195 = this;
  v219 = this;
  v166 = 1;
  v196 = 0;
  v197 = 1;
  v198 = 0;
  v453 = 0;
  v454 = 0;
  v455 = 0;
  v457 = 0;
  v458 = 0;
  v459 = 0;
  v170 = 0;
  v173 = &v172;
  v172 = (char *)&v172;
  v220 = 0;
  v314 = 4195067;
  v315 = 0;
  v317 = 0;
  v316 = 0;
  v318 = 0;
  v200 = 0;
  v201 = 0;
  v202 = (char *)this + 40;
  UcsReentrantAutoRWLock::Acquire(&v200, &v314, 1, 0xFFFFFFFFLL);
  v167 = (volatile signed __int64 *)((char *)v2 + 22112);
  v168 = 0;
  v305 = 0;
  v306 = 0;
  v307 = 0;
  v308 = 0;
  v309 = 0;
  v310 = 0;
  v311 = 1;
  v312 = 0;
  v313 = 1;
  v304 = &CSuppressOutput::`vftable';
  v3 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset)
                 + 112LL);
  v191 = 0;
  v192 = 0;
  v4 = *(void ****)(v3 + 24);
  if ( v4 != &v304 )
  {
    *(_QWORD *)&v191 = v3;
    *((_QWORD *)&v191 + 1) = v4;
    *(_QWORD *)&v192 = v305;
    *((_QWORD *)&v192 + 1) = &v304;
    v305 = v4;
    *(_QWORD *)(v3 + 24) = &v304;
  }
  utgettime((struct SQLDATEBASE *)&v199, 1, 0);
  ExcHandler::ExcHandler((ExcHandler *)v451, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_backout, 0);
  v433 = &v463;
  v460 = 0;
  v461 = 0;
  v462 = 0;
  v463 = -1;
  v235 = &v460;
  v236 = 0;
  v237 = 0;
  BrokerTLS = CSbTaskLocalStorage::GetBrokerTLS();
  v236 = *((_QWORD *)BrokerTLS + 9);
  *((_QWORD *)BrokerTLS + 9) = &v235;
  v279 = 0;
  ExcHandler::ExcHandler(
    (ExcHandler *)v450,
    0,
    0,
    0,
    (int (*)(int, int, int, int, char *))CSbAutoTaskErrorOutputCapture::ErrorHandler,
    0);
  v248 = 88;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v5 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
  v436 = v5;
  v6 = *(_QWORD *)(v5 + 256);
  v259 = v6;
  if ( !v6 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v6 = *(_QWORD *)(v5 + 256);
    v259 = v6;
  }
  v263 = *(struct IMemObj **)(v6 + 1000);
  v437 = v263;
  v7 = operator new[](0x18000u, v263, "sql\\ntdbms\\broker\\src\\ssbdispatcher.cpp", 2744, 8u);
  v224 = v7;
  if ( v7 )
  {
    v438 = 0;
    operator delete(0, 1u);
  }
  v220 = v7;
  v439 = v167;
  v440 = 0;
  v441[2] = 0;
  v225 = 0;
  v204 = 0;
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  v249 = 256;
  v441[3] = v167;
  if ( *(_DWORD *)v167 )
  {
    v8 = 0;
  }
  else
  {
    v442 = _InterlockedCompareExchange64(v167, UniqueThread_low, 0);
    v443 = v442;
    v8 = v442 == 0;
  }
  v250 = v8;
  if ( v8 )
  {
    v15 = v167;
  }
  else
  {
    if ( (SOS_PublicGlobals::sm_osStats & 0x80u) != 0 && (SOS_PublicGlobals::sm_osStats & 4) != 0 )
    {
      v228 = 0;
      v251 = 88;
      v444 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v9 = v444[SystemThread_TlsIndex];
      v10 = SystemThread_TlsOffset + v9 == 0;
      v11 = SystemThread_TlsOffset + v9;
      v445 = v11;
      if ( !v10 && *(_QWORD *)(v11 + 272) == v11 )
      {
        v13 = *(_QWORD *)(v11 + 256);
        v228 = v13;
      }
      else
      {
        v13 = v228;
      }
      v204 = v13;
      if ( v13 )
      {
        v446 = &v229;
        v252 = Base_PublicGlobals::sm_invariantTscAvailable;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          v253 = QueryPerformanceCounter(&PerformanceCount);
          QuadPart = (CSbTransportMgr *)PerformanceCount.QuadPart;
          v229 = (CSbTransportMgr *)PerformanceCount.QuadPart;
        }
        else
        {
          QuadPart = MEMORY[0x7FFE0008];
          v447 = MEMORY[0x7FFE0008];
          v229 = MEMORY[0x7FFE0008];
          v13 = v204;
        }
        v448 = QuadPart;
        v225 = QuadPart;
      }
    }
    else
    {
      v13 = v204;
    }
    v254 = 2;
    v15 = v167;
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v167, UniqueThread_low);
    else
      Spinlock<170,8,258>::SpinToAcquireOptimistic(v167, v13, UniqueThread_low);
    if ( v13 )
    {
      v449 = &v216;
      v255 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v256 = QueryPerformanceCounter(&v261);
        v16 = (CSbTransportMgr *)v261.QuadPart;
        v216 = (CSbTransportMgr *)v261.QuadPart;
      }
      else
      {
        v16 = MEMORY[0x7FFE0008];
        v324 = MEMORY[0x7FFE0008];
        v216 = MEMORY[0x7FFE0008];
        v15 = v167;
        v13 = v204;
      }
      v325 = &v225;
      v326 = &v216;
      if ( v16 < v225 )
      {
        v17 = 0;
        v171 = 0;
      }
      else
      {
        v17 = v16 - v225;
        v171 = (char *)v17;
      }
      v171 = (char *)v17;
      v327 = (char *)v17;
      v328 = v13 + 3192;
      *(_QWORD *)(v13 + 3192) += v17;
    }
  }
  v168 = 1;
  v329 = (char *)v2 + 22096;
  if ( *((CSbMsgDispatcher **)v2 + 2763) == (CSbMsgDispatcher *)((char *)v2 + 22096) )
  {
    *((_BYTE *)a2 + 648) = 0;
    v330 = v15;
    v174 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v18 = rand();
      if ( v18 == 5 * (v18 / 5) )
        Spinlock<170,8,258>::UpdateStatSnapshot();
    }
    v331 = v15;
    *v15 = 0;
    v168 = 0;
    v175 = 0;
    ExcHandler::~ExcHandler((ExcHandler *)v450);
    v332 = CSbTaskLocalStorage::GetBrokerTLS();
    *((_QWORD *)v332 + 9) = v236;
    ExcHandler::~ExcHandler((ExcHandler *)v451);
    v19 = v191;
    if ( (_QWORD)v191 )
    {
      *(_QWORD *)(*(_QWORD *)(v191 + 24) + 8LL) = v192;
      v333 = *(_QWORD *)(v19 + 24);
      *(_QWORD *)(v19 + 24) = *((_QWORD *)&v191 + 1);
      v191 = 0;
      v192 = 0;
    }
    v304 = &CConnectionOutput::`vftable';
    SpinlockHolder<170,8,258>::~SpinlockHolder<170,8,258>(&v167);
    UcsReentrantAutoRWLock::Release((UcsReentrantAutoRWLock *)&v200);
    v334 = v224;
    operator delete(v224, 1u);
    if ( (_DWORD)v196 )
      CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v196, 0);
    return 0;
  }
  if ( !*((_BYTE *)v2 + 22508) )
  {
    *((_BYTE *)a2 + 648) = 0;
    v335 = v167;
    v176 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v21 = rand();
      if ( v21 == 5 * (v21 / 5) )
        Spinlock<170,8,258>::UpdateStatSnapshot();
    }
    v336 = v167;
    *v167 = 0;
    v168 = 0;
    v177 = 0;
    ExcHandler::~ExcHandler((ExcHandler *)v450);
    v337 = CSbTaskLocalStorage::GetBrokerTLS();
    *((_QWORD *)v337 + 9) = v236;
    ExcHandler::~ExcHandler((ExcHandler *)v451);
    v22 = v191;
    if ( (_QWORD)v191 )
    {
      *(_QWORD *)(*(_QWORD *)(v191 + 24) + 8LL) = v192;
      v338 = *(_QWORD *)(v22 + 24);
      *(_QWORD *)(v22 + 24) = *((_QWORD *)&v191 + 1);
      v191 = 0;
      v192 = 0;
    }
    v304 = &CConnectionOutput::`vftable';
    SpinlockHolder<170,8,258>::~SpinlockHolder<170,8,258>(&v167);
    UcsReentrantAutoRWLock::Release((UcsReentrantAutoRWLock *)&v200);
    v339 = v224;
    operator delete(v224, 1u);
    if ( (_DWORD)v196 )
      CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v196, 0);
    return 0;
  }
  v340 = v167;
  v178 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v23 = rand();
    if ( v23 == 5 * (v23 / 5) )
      Spinlock<170,8,258>::UpdateStatSnapshot();
  }
  v341 = v167;
  *v167 = 0;
  v168 = 0;
  LODWORD(v454) = 98304;
  v453 = v224;
  utgettime((struct SQLDATEBASE *)&v456, 1, 0);
  SQLDATE::DateAdd((SQLDATE *)&v456, 9, 500);
  v212 = 0;
  v197 = 1;
  v257 = 88;
  v342 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v343 = (_QWORD *)(v342[SystemThread_TlsIndex] + SystemThread_TlsOffset);
  v344 = v343;
  v345 = (char *)*v343;
  v346 = v345;
  v171 = v345;
  *(_QWORD *)&v198 = *((_QWORD *)v345 + 18);
  v258 = 88;
  v347 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v348 = (_QWORD *)(v347[SystemThread_TlsIndex] + SystemThread_TlsOffset);
  v349 = v348;
  v350 = (char *)*v348;
  v351 = v350;
  v171 = v350;
  v24 = v350[152];
  v212 = v24 != 0;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v198 + 464LL))(v198) )
  {
    if ( v24 && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v198 + 488LL))(v198) )
      utassert_fail(
        1u,
        "rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()",
        "automsqlxact.cpp",
        235,
        0);
    (*(void (__fastcall **)(_QWORD, __int64, __int64, char *))(*(_QWORD *)v198 + 232LL))(v198, 2, 1, (char *)&v196 + 4);
    v197 = 1;
    LODWORD(v196) = 3;
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64, __int64, int, int, _BYTE, _QWORD, bool))(*(_QWORD *)v198 + 8LL))(
      v198,
      L"SbDispatchRecvMessages",
      44,
      1,
      2,
      1,
      0,
      0,
      v24 != 0);
    LODWORD(v196) = 1;
  }
  v262 = 88;
  v352 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v353 = (_QWORD *)(v352[SystemThread_TlsIndex] + SystemThread_TlsOffset);
  v354 = v353;
  v355 = (char *)*v353;
  v356 = v355;
  v171 = v355;
  v357 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v355 + 18) + 432LL))(*((_QWORD *)v355 + 18));
  v264 = g_metadataFactory(v263, v357, "sql\\ntdbms\\broker\\src\\ssbdispatcher.cpp", 2785);
  v278 = (void (__fastcall ***)(_QWORD, _QWORD))v264;
  v247 = 88;
  v358 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v359 = (_QWORD *)(v358[SystemThread_TlsIndex] + SystemThread_TlsOffset);
  v360 = v359;
  v361 = *v359;
  v362 = v361;
  v363 = v264;
  v226[0] = v361;
  v226[1] = v264;
  v364 = &v227;
  v227 = 0;
  while ( 2 )
  {
    v365 = &v172;
    if ( v173 == &v172 )
    {
      v265 = 0;
LABEL_69:
      v25 = 0;
      v266 = 0;
      goto LABEL_71;
    }
    v265 = v173;
    if ( !v173 )
      goto LABEL_69;
    v25 = (CSbMsgDispatcher::CSbReceivedDialog *)(v173 - 1);
    v266 = v173 - 1;
LABEL_71:
    while ( 1 )
    {
      v170 = v25;
      if ( !v25 )
        break;
      if ( *((_DWORD *)v25 + 25) == 1 )
      {
        v26 = v170;
        v27 = (_QWORD *)((char *)v170 + 8);
        v366 = (char *)v170 + 8;
        v28 = (_QWORD *)*((_QWORD *)v170 + 2);
        v367 = v28;
        v29 = *((_QWORD *)v170 + 1);
        v368 = v29;
        *(_QWORD *)(v29 + 8) = v28;
        *v28 = v29;
        v27[1] = 0;
        *v27 = 0;
        goto LABEL_170;
      }
      v369 = (char *)v170 + 8;
      v30 = (char **)*((_QWORD *)v170 + 2);
      if ( v30 == &v172 )
      {
        v267 = 0;
        goto LABEL_77;
      }
      v267 = *((_QWORD *)v170 + 2);
      if ( v30 )
      {
        v25 = (CSbMsgDispatcher::CSbReceivedDialog *)(v30 - 1);
        v268 = v25;
      }
      else
      {
LABEL_77:
        v25 = 0;
        v268 = 0;
      }
    }
    v370 = v167;
    v371 = 0;
    v372 = 0;
    v221 = 0;
    v205 = 0;
    v223 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    v280 = 256;
    v373 = v167;
    if ( *(_DWORD *)v167 )
    {
      v31 = 0;
    }
    else
    {
      v374 = _InterlockedCompareExchange64(v167, v223, 0);
      v375 = v374;
      v31 = v374 == 0;
    }
    v294 = v31;
    if ( v31 )
    {
      v37 = v167;
    }
    else
    {
      if ( (SOS_PublicGlobals::sm_osStats & 0x80u) != 0 && (SOS_PublicGlobals::sm_osStats & 4) != 0 )
      {
        v230 = 0;
        v295 = 88;
        v376 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v32 = v376[SystemThread_TlsIndex];
        v10 = SystemThread_TlsOffset + v32 == 0;
        v33 = SystemThread_TlsOffset + v32;
        v377 = v33;
        if ( !v10 && *(_QWORD *)(v33 + 272) == v33 )
        {
          v35 = *(_QWORD *)(v33 + 256);
          v230 = v35;
        }
        else
        {
          v35 = v230;
        }
        v205 = v35;
        if ( v35 )
        {
          v378 = &v231;
          v297 = Base_PublicGlobals::sm_invariantTscAvailable;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            v298 = QueryPerformanceCounter(&v269);
            v36 = (CSbTransportMgr *)v269.QuadPart;
            v231 = (CSbTransportMgr *)v269.QuadPart;
          }
          else
          {
            v36 = MEMORY[0x7FFE0008];
            v379 = MEMORY[0x7FFE0008];
            v231 = MEMORY[0x7FFE0008];
            v35 = v205;
          }
          v380 = v36;
          v221 = v36;
        }
      }
      else
      {
        v35 = v205;
      }
      v299 = 2;
      v37 = v167;
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v167, v223);
      else
        Spinlock<170,8,258>::SpinToAcquireOptimistic(v167, v35, v223);
      if ( v35 )
      {
        v381 = &v222;
        v300 = Base_PublicGlobals::sm_invariantTscAvailable;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          v301 = QueryPerformanceCounter(&v270);
          v38 = (CSbTransportMgr *)v270.QuadPart;
          v222 = (CSbTransportMgr *)v270.QuadPart;
        }
        else
        {
          v38 = MEMORY[0x7FFE0008];
          v382 = MEMORY[0x7FFE0008];
          v222 = MEMORY[0x7FFE0008];
          v37 = v167;
          v35 = v205;
        }
        v383 = &v221;
        v384 = &v222;
        if ( v38 < v221 )
        {
          v39 = 0;
          v171 = 0;
        }
        else
        {
          v39 = v38 - v221;
          v171 = (char *)v39;
        }
        v171 = (char *)v39;
        v385 = (char *)v39;
        v386 = v35 + 3192;
        *(_QWORD *)(v35 + 3192) += v39;
      }
    }
    v168 = 1;
    v387 = (char *)v2 + 22096;
    v40 = (CSbMsgDispatcher *)*((_QWORD *)v2 + 2763);
    if ( v40 == (CSbMsgDispatcher *)((char *)v2 + 22096) )
    {
      v271 = 0;
      goto LABEL_113;
    }
    v271 = *((_QWORD *)v2 + 2763);
    if ( v40 )
    {
      v41 = (CSbMsgDispatcher *)((char *)v40 - 8);
      v232 = v41;
      v42 = v41;
    }
    else
    {
LABEL_113:
      v41 = 0;
      v232 = 0;
      v42 = 0;
    }
    v388 = v41;
    if ( v42 )
    {
      v389 = (char *)v42 + 8;
      v43 = (_QWORD *)*((_QWORD *)v42 + 2);
      v390 = v43;
      v44 = *((_QWORD *)v42 + 1);
      v391 = v44;
      *(_QWORD *)(v44 + 8) = v43;
      *v43 = v44;
      *((_QWORD *)v42 + 2) = 0;
      *((_QWORD *)v42 + 1) = 0;
    }
    v26 = v41;
    v170 = v41;
    if ( v42 )
    {
      --*((_DWORD *)v2 + 5530);
      v26 = v170;
      v37 = v167;
      v41 = v232;
    }
    v392 = v37;
    v179 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v45 = rand();
      if ( v45 == 5 * (v45 / 5) )
        Spinlock<170,8,258>::UpdateStatSnapshot();
    }
    *v37 = 0;
    v168 = 0;
    if ( v41 )
      goto LABEL_170;
    if ( SHIDWORD(v455) <= 1 )
      goto LABEL_169;
    v319 = 4194400;
    v320 = 0;
    v322 = 0;
    v321 = 0;
    v323 = 0;
    if ( (unsigned int)SOS_Task::Sleep(0, &v319) != 2 )
    {
      v393 = v37;
      v394 = 0;
      v395 = 0;
      v218 = 0;
      v203 = 0;
      v215 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      v302 = 256;
      v396 = v167;
      if ( *(_DWORD *)v167 )
      {
        v46 = 0;
      }
      else
      {
        v397 = _InterlockedCompareExchange64(v167, v215, 0);
        v398 = v397;
        v46 = v397 == 0;
      }
      v303[6] = v46;
      if ( !v46 )
      {
        if ( (SOS_PublicGlobals::sm_osStats & 0x80u) != 0 && (SOS_PublicGlobals::sm_osStats & 4) != 0 )
        {
          v233 = 0;
          v303[7] = 88;
          v399 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v47 = v399[SystemThread_TlsIndex];
          v10 = SystemThread_TlsOffset + v47 == 0;
          v48 = SystemThread_TlsOffset + v47;
          v400 = v48;
          if ( !v10 && *(_QWORD *)(v48 + 272) == v48 )
          {
            v50 = *(_QWORD *)(v48 + 256);
            v233 = v50;
          }
          else
          {
            v50 = v233;
          }
          v203 = v50;
          if ( v50 )
          {
            v401 = &v234;
            v303[8] = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              v303[9] = QueryPerformanceCounter(&v272);
              v51 = (CSbTransportMgr *)v272.QuadPart;
              v234 = (CSbTransportMgr *)v272.QuadPart;
            }
            else
            {
              v51 = MEMORY[0x7FFE0008];
              v402 = MEMORY[0x7FFE0008];
              v234 = MEMORY[0x7FFE0008];
              v50 = v203;
            }
            v403 = v51;
            v218 = v51;
          }
        }
        else
        {
          v50 = v203;
        }
        v303[10] = 2;
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v167, v215);
        else
          Spinlock<170,8,258>::SpinToAcquireOptimistic(v167, v50, v215);
        if ( v50 )
        {
          v404 = &v217;
          v242 = Base_PublicGlobals::sm_invariantTscAvailable;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            v243 = QueryPerformanceCounter(&v273);
            v52 = (CSbTransportMgr *)v273.QuadPart;
            v217 = (CSbTransportMgr *)v273.QuadPart;
          }
          else
          {
            v52 = MEMORY[0x7FFE0008];
            v405 = MEMORY[0x7FFE0008];
            v217 = MEMORY[0x7FFE0008];
            v50 = v203;
          }
          v406 = &v218;
          v407 = &v217;
          if ( v52 < v218 )
          {
            v53 = 0;
            v171 = 0;
          }
          else
          {
            v53 = v52 - v218;
            v171 = (char *)v53;
          }
          v171 = (char *)v53;
          v408 = (char *)v53;
          v409 = v50 + 3192;
          *(_QWORD *)(v50 + 3192) += v53;
        }
      }
      v168 = 1;
      v410 = (char *)v2 + 22096;
      v54 = (CSbMsgDispatcher *)*((_QWORD *)v2 + 2763);
      if ( v54 == (CSbMsgDispatcher *)((char *)v2 + 22096) )
      {
        v274 = 0;
      }
      else
      {
        v274 = *((_QWORD *)v2 + 2763);
        if ( v54 )
        {
          v26 = (CSbMsgDispatcher *)((char *)v54 - 8);
          v275 = v26;
          v55 = v26;
          goto LABEL_161;
        }
      }
      v26 = 0;
      v275 = 0;
      v55 = 0;
LABEL_161:
      v411 = v26;
      if ( v55 )
      {
        v412 = (char *)v55 + 8;
        v56 = (_QWORD *)*((_QWORD *)v55 + 2);
        v413 = v56;
        v57 = *((_QWORD *)v55 + 1);
        v414 = v57;
        *(_QWORD *)(v57 + 8) = v56;
        *v56 = v57;
        *((_QWORD *)v55 + 2) = 0;
        *((_QWORD *)v55 + 1) = 0;
      }
      v170 = v26;
      if ( v55 )
      {
        --*((_DWORD *)v2 + 5530);
        v26 = v170;
      }
      v415 = v167;
      v180 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v58 = rand();
        if ( v58 == 5 * (v58 / 5) )
          Spinlock<170,8,258>::UpdateStatSnapshot();
      }
      *v167 = 0;
      v168 = 0;
LABEL_169:
      if ( !v26 )
        goto LABEL_197;
LABEL_170:
      v416 = (char *)v26 + 8;
      v417 = &v172;
      *((_QWORD *)v26 + 1) = v172;
      *((_QWORD *)v172 + 1) = (char *)v26 + 8;
      v172 = (char *)v26 + 8;
      *((_QWORD *)v26 + 2) = &v172;
      CSbMsgDispatcher::CSbReceivedDialog::Dispatch(
        v26,
        (struct CSsbClassifier *)v226,
        (struct SbReceivedMessageInfo *)&v453);
      v244 = 88;
      v418 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v59 = v418[SystemThread_TlsIndex] + SystemThread_TlsOffset;
      v419 = v59;
      v60 = *(_QWORD **)(v59 + 256);
      v276 = v60;
      if ( !v60 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v60 = *(_QWORD **)(v59 + 256);
        v276 = v60;
      }
      v420 = v60;
      v61 = __rdtsc();
      v421 = v61;
      v62 = v60[104];
      if ( v61 > v62 || v62 != 0x7FFFFFFFFFFFFFFFLL && v62 - v61 > *(_QWORD *)(v60[76] + 3568LL) )
      {
        v193 = SOS_Task::Sleep(0, &yieldWait);
        if ( v193 == 2 )
        {
          v166 = 0;
          goto LABEL_197;
        }
      }
      else
      {
        v277 = v60[75];
        v422 = v277 + 188;
        if ( (*(_DWORD *)(v277 + 188) & 4) != 0 )
        {
          v64 = *(_QWORD *)(v277 + 152);
          v423 = v64;
          if ( (*(_BYTE *)(v64 + 616) & 1) == 0 )
          {
            v65 = *(_DWORD *)(v64 + 800);
            if ( (v65 & 0x80u) == 0 && (v65 & 0x100) == 0 )
            {
              v193 = 2;
              v166 = 0;
              goto LABEL_197;
            }
          }
        }
        v193 = 0;
      }
      utgettime((struct SQLDATEBASE *)&v199, 1, 0);
      v424 = &v199;
      v425 = &v456;
      if ( v199 >= v456 )
      {
        v68 = 4;
        if ( v199 == v456 )
          v68 = 2;
      }
      else
      {
        v68 = 1;
      }
      if ( v68 == 4 )
        goto LABEL_197;
      continue;
    }
    break;
  }
  v166 = 0;
LABEL_197:
  v426 = &v227;
  if ( v227 )
  {
    v227 = 0;
    ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
  }
  v427 = &v227;
  if ( v227 )
  {
    v227 = 0;
    ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
  }
  v428 = v278;
  if ( v278 )
    (**v278)(v278, 1);
  ExcHandler::~ExcHandler((ExcHandler *)v450);
  v69 = v279;
  if ( !v279 )
  {
    v245 = 88;
    v429 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v70 = v429[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v430 = v70;
    v69 = *(struct Worker **)(v70 + 256);
    v296 = v69;
    if ( !v69 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v69 = *(struct Worker **)(v70 + 256);
      v296 = v69;
    }
  }
  v281 = v69;
  if ( *((_DWORD *)v69 + 139) )
    ExceptionPostCatchActions(v69);
  v431 = CSbTaskLocalStorage::GetBrokerTLS();
  *((_QWORD *)v431 + 9) = v236;
  ExcHandler::~ExcHandler((ExcHandler *)v451);
  v71 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v72 = *(struct Worker **)(v71 + 256);
  if ( !v72 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v72 = *(struct Worker **)(v71 + 256);
  }
  if ( *((_DWORD *)v72 + 139) )
    ExceptionPostCatchActions(v72);
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v452, 0, 0, 0, (int (*)(int, int, int, int, char *))SsbTaskErrorHandler, 0);
    if ( v166 )
    {
      CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v196, 0);
      SQLDATE::DateDiff((SQLDATE *)&v456, 9, (const struct SQLDATE *)&v199, &v194);
      v194 += 500;
      v181 = CommonGlobalState::m_CollectingStatistics;
      if ( CommonGlobalState::m_CollectingStatistics )
      {
        v182 = CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
          PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x1Du, 0x98u, SHIDWORD(v454), 0);
        v183 = CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
          PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x1Du, 0xB8u, SHIDWORD(v454), 0);
        v184 = CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
          PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x1Du, 0x90u, (int)v455, 0);
        v185 = CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
          PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x1Du, 0xB0u, (int)v455, 0);
        v186 = CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
          PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x1Du, 0x30u, (int)v455, 0);
        v187 = CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
          PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x1Du, 0xA0u, (int)v455, 0);
        for ( i = 1; ; ++i )
        {
          v169 = i;
          if ( i > 0xAu )
            break;
          v74 = *((_DWORD *)&v456 + i + 1);
          v246 = v74;
          if ( v74 > 0 )
          {
            v188 = CommonGlobalState::m_PerfCountersEnabled;
            if ( CommonGlobalState::m_PerfCountersEnabled )
            {
              v213 = v74;
              _mm_lfence();
              i = v169;
              PerfmonManager::IncrementCounterValue(
                (PerfmonManager *)qword_102ECFB00,
                0x1Du,
                *((_DWORD *)&CSsbBrokerXactNotify::sm_rgdwEnqueuedPriorityPerfCounters + v169 - 1),
                v213,
                0);
            }
          }
        }
      }
    }
    else
    {
      CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v196, 0);
    }
    ExcHandler::~ExcHandler((ExcHandler *)v452);
  }
  catch ( SQLError v303 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v441, (const struct SQLError *)v303);
      if ( v303[4] == 1 )
        v165 = v303[0];
      else
        v165 = LOWORD(v303[0]);
      SsbLogError(9644, 16, 15, v165, v303[3]);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v441);
    }
    catch ( ShortStackException )
    {
    }
    v2 = v219;
    v195 = v219;
  }
  v75 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v76 = *(struct Worker **)(v75 + 256);
  if ( !v76 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v76 = *(struct Worker **)(v75 + 256);
  }
  if ( *((_DWORD *)v76 + 139) )
    ExceptionPostCatchActions(v76);
  v77 = 0;
  v78 = &v189;
  v190 = &v189;
  v189 = (char *)&v189;
  if ( v173 == &v172 )
    goto LABEL_386;
  v79 = 0;
  if ( v173 )
    v79 = (CSbMsgDispatcher::CSbReceivedDialog *)(v173 - 1);
  v170 = v79;
  if ( !v79 )
    goto LABEL_386;
  do
  {
    if ( CSbMsgDispatcher::CSbReceivedDialog::ReturnToQueue(v79) )
      v77 = 1;
    v80 = (char **)*((_QWORD *)v79 + 2);
    if ( v80 == &v172 )
      v80 = 0;
    v79 = 0;
    if ( v80 )
      v79 = (CSbMsgDispatcher::CSbReceivedDialog *)(v80 - 1);
  }
  while ( v79 );
  v170 = 0;
  if ( v77 )
  {
    if ( v173 != &v172 )
    {
      v81 = 0;
      if ( v173 )
        v81 = v173 - 1;
      if ( v81 )
      {
        do
        {
          v82 = v81;
          v170 = (CSbMsgDispatcher::CSbReceivedDialog *)v81;
          v83 = (__int64 *)(v81 + 1);
          v84 = (char **)v81[2];
          if ( v84 == &v172 )
            v84 = 0;
          v81 = 0;
          if ( v84 )
            v81 = v84 - 1;
          v206 = (volatile signed __int64 *)(v82 + 14);
          v207 = 0;
          v85 = 0;
          v86 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
          if ( *((_DWORD *)v82 + 28) || _InterlockedCompareExchange64(v206, v86, 0) )
          {
            v87 = 0;
            if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
            {
              v88 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              if ( v88 && *(_QWORD *)(v88 + 272) == v88 )
                v87 = *(_QWORD *)(v88 + 256);
              if ( v87 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&v282);
                  v85 = (CSbTransportMgr *)v282.QuadPart;
                }
                else
                {
                  v85 = MEMORY[0x7FFE0008];
                }
              }
            }
            if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
              Spinlock<165,9,258>::SpinToAcquireWithExponentialBackoff(v206, v86);
            else
              Spinlock<165,9,258>::SpinToAcquireOptimistic(v206, v87, v86);
            if ( v87 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v283);
                v89 = (CSbTransportMgr *)v283.QuadPart;
              }
              else
              {
                v89 = MEMORY[0x7FFE0008];
              }
              if ( v89 < v85 )
                v90 = 0;
              else
                v90 = v89 - v85;
              *(_QWORD *)(v87 + 3192) += v90;
            }
          }
          v207 = 1;
          if ( *((_DWORD *)v170 + 25) == 2 )
          {
            v91 = (_QWORD *)v83[1];
            v92 = *v83;
            *(_QWORD *)(v92 + 8) = v91;
            *v91 = v92;
            v83[1] = 0;
            *v83 = 0;
            CSbMsgDispatcher::CSbReceivedDialog::MoveToRetiredQ(v170);
          }
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v93 = rand();
            if ( v93 == 5 * (v93 / 5) )
              Spinlock<165,9,258>::UpdateStatSnapshot();
          }
          *v206 = 0;
          v207 = 0;
        }
        while ( v81 );
        v2 = v195;
      }
    }
    v240 = (_QWORD *)((char *)v2 + 22144);
    j = 0;
    v94 = 0;
    v95 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *((_DWORD *)v2 + 5536) || _InterlockedCompareExchange64((volatile signed __int64 *)v2 + 2768, v95, 0) )
    {
      v96 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v97 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v97 && *(_QWORD *)(v97 + 272) == v97 )
          v96 = *(_QWORD *)(v97 + 256);
        if ( v96 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v284);
            v94 = (CSbTransportMgr *)v284.QuadPart;
          }
          else
          {
            v94 = MEMORY[0x7FFE0008];
          }
        }
      }
      v98 = (char *)v2 + 22144;
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v98, v95);
      else
        Spinlock<170,8,258>::SpinToAcquireOptimistic(v98, v96, v95);
      if ( v96 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v285);
          v99 = (CSbTransportMgr *)v285.QuadPart;
        }
        else
        {
          v99 = MEMORY[0x7FFE0008];
        }
        if ( v99 < v94 )
          v100 = 0;
        else
          v100 = v99 - v94;
        *(_QWORD *)(v96 + 3192) += v100;
      }
    }
    for ( j = 1; *((_DWORD *)v2 + 5538) > 0x64u; *((_QWORD *)v102 + 2) = &v189 )
    {
      v101 = (CSbMsgDispatcher *)*((_QWORD *)v2 + 2767);
      v102 = 0;
      if ( v101 != (CSbMsgDispatcher *)((char *)v2 + 22128) )
      {
        if ( v101 )
          v102 = (char *)v101 - 8;
        if ( v102 )
        {
          v103 = (_QWORD *)*((_QWORD *)v102 + 2);
          v104 = *((_QWORD *)v102 + 1);
          *(_QWORD *)(v104 + 8) = v103;
          *v103 = v104;
          *((_QWORD *)v102 + 2) = 0;
          *((_QWORD *)v102 + 1) = 0;
        }
      }
      --*((_DWORD *)v2 + 5538);
      v102[106] = 1;
      *((_QWORD *)v102 + 1) = v189;
      *((_QWORD *)v189 + 1) = v102 + 8;
      v189 = v102 + 8;
    }
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v105 = rand();
      if ( v105 == 5 * (v105 / 5) )
        Spinlock<170,8,258>::UpdateStatSnapshot();
    }
    *v240 = 0;
    j = 0;
    if ( v173 != &v172 )
    {
      v106 = 0;
      if ( v173 )
        v106 = v173 - 1;
      if ( v106 )
      {
        do
        {
          v107 = v106;
          v170 = (CSbMsgDispatcher::CSbReceivedDialog *)v106;
          v108 = (__int64 *)(v106 + 1);
          v109 = (char **)v106[2];
          if ( v109 == &v172 )
            v109 = 0;
          v106 = 0;
          if ( v109 )
            v106 = v109 - 1;
          v208 = (volatile signed __int64 *)(v107 + 14);
          v209 = 0;
          v110 = 0;
          v111 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
          if ( *((_DWORD *)v107 + 28) || _InterlockedCompareExchange64(v208, v111, 0) )
          {
            v112 = 0;
            if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
            {
              v113 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset;
              if ( v113 && *(_QWORD *)(v113 + 272) == v113 )
                v112 = *(_QWORD *)(v113 + 256);
              if ( v112 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&v286);
                  v110 = (CSbTransportMgr *)v286.QuadPart;
                }
                else
                {
                  v110 = MEMORY[0x7FFE0008];
                }
              }
            }
            if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
              Spinlock<165,9,258>::SpinToAcquireWithExponentialBackoff(v208, v111);
            else
              Spinlock<165,9,258>::SpinToAcquireOptimistic(v208, v112, v111);
            if ( v112 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v287);
                v114 = (CSbTransportMgr *)v287.QuadPart;
              }
              else
              {
                v114 = MEMORY[0x7FFE0008];
              }
              if ( v114 < v110 )
                v115 = 0;
              else
                v115 = v114 - v110;
              *(_QWORD *)(v112 + 3192) += v115;
            }
          }
          v209 = 1;
          if ( *((_DWORD *)v170 + 25) == 3 )
          {
            v116 = (_QWORD *)v108[1];
            v117 = *v108;
            *(_QWORD *)(v117 + 8) = v116;
            *v116 = v117;
            v108[1] = 0;
            *v108 = 0;
            CSbMsgDispatcher::CSbReceivedDialog::MoveToOutOfOrderQ(v170);
          }
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v118 = rand();
            if ( v118 == 5 * (v118 / 5) )
              Spinlock<165,9,258>::UpdateStatSnapshot();
          }
          *v208 = 0;
          v209 = 0;
        }
        while ( v106 );
        v2 = v195;
      }
    }
    v238 = (_QWORD *)((char *)v2 + 22176);
    k = 0;
    v119 = 0;
    v120 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *((_DWORD *)v2 + 5544) || _InterlockedCompareExchange64((volatile signed __int64 *)v2 + 2772, v120, 0) )
    {
      v121 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v122 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v122 && *(_QWORD *)(v122 + 272) == v122 )
          v121 = *(_QWORD *)(v122 + 256);
        if ( v121 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v288);
            v119 = (CSbTransportMgr *)v288.QuadPart;
          }
          else
          {
            v119 = MEMORY[0x7FFE0008];
          }
        }
      }
      v123 = (char *)v2 + 22176;
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v123, v120);
      else
        Spinlock<170,8,258>::SpinToAcquireOptimistic(v123, v121, v120);
      if ( v121 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v289);
          v124 = (CSbTransportMgr *)v289.QuadPart;
        }
        else
        {
          v124 = MEMORY[0x7FFE0008];
        }
        if ( v124 < v119 )
          v125 = 0;
        else
          v125 = v124 - v119;
        *(_QWORD *)(v121 + 3192) += v125;
      }
    }
    for ( k = 1; *((_DWORD *)v2 + 5546) > 0x12Cu; *((_QWORD *)v127 + 2) = &v189 )
    {
      v126 = (CSbMsgDispatcher *)*((_QWORD *)v2 + 2771);
      v127 = 0;
      if ( v126 != (CSbMsgDispatcher *)((char *)v2 + 22160) )
      {
        if ( v126 )
          v127 = (char *)v126 - 8;
        if ( v127 )
        {
          v128 = (_QWORD *)*((_QWORD *)v127 + 2);
          v129 = *((_QWORD *)v127 + 1);
          *(_QWORD *)(v129 + 8) = v128;
          *v128 = v129;
          *((_QWORD *)v127 + 2) = 0;
          *((_QWORD *)v127 + 1) = 0;
        }
      }
      *((_DWORD *)v2 + 5546) -= *((_DWORD *)v127 + 31);
      v127[106] = 1;
      *((_QWORD *)v127 + 1) = v189;
      *((_QWORD *)v189 + 1) = v127 + 8;
      v189 = v127 + 8;
    }
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v130 = rand();
      if ( v130 == 5 * (v130 / 5) )
        Spinlock<170,8,258>::UpdateStatSnapshot();
    }
    *v238 = 0;
    k = 0;
  }
  while ( 1 )
  {
    v78 = v190;
LABEL_386:
    if ( v78 == &v189 )
      break;
    v131 = 0;
    if ( v78 )
      v131 = (CSbMsgDispatcher::CSbReceivedDialog *)(v78 - 1);
    if ( !v131 )
      break;
    v132 = (_QWORD *)*((_QWORD *)v131 + 2);
    v133 = *((_QWORD *)v131 + 1);
    *(_QWORD *)(v133 + 8) = v132;
    *v132 = v133;
    *((_QWORD *)v131 + 2) = 0;
    *((_QWORD *)v131 + 1) = 0;
    v170 = v131;
    CSbMsgDispatcher::CSbReceivedDialog::Unhash(v131);
    CSbMsgDispatcher::CSbReceivedDialog::Release(v131);
  }
  v134 = v173;
  if ( v173 != &v172 )
  {
    while ( v134 != &v172 )
    {
      v135 = 0;
      if ( v134 )
        v135 = (volatile signed __int64 *)(v134 - 1);
      v170 = (CSbMsgDispatcher::CSbReceivedDialog *)v135;
      if ( !v135 )
        goto LABEL_422;
      v136 = (_QWORD *)*((_QWORD *)v135 + 2);
      v137 = *((_QWORD *)v135 + 1);
      *(_QWORD *)(v137 + 8) = v136;
      *v136 = v137;
      *((_QWORD *)v135 + 2) = 0;
      *((_QWORD *)v135 + 1) = 0;
      v210 = v135 + 14;
      v211 = 0;
      v138 = 0;
      v139 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *((_DWORD *)v135 + 28) || _InterlockedCompareExchange64(v210, v139, 0) )
      {
        v140 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v141 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v141 && *(_QWORD *)(v141 + 272) == v141 )
            v140 = *(_QWORD *)(v141 + 256);
          if ( v140 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v290);
              v138 = (CSbTransportMgr *)v290.QuadPart;
            }
            else
            {
              v138 = MEMORY[0x7FFE0008];
            }
          }
        }
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<165,9,258>::SpinToAcquireWithExponentialBackoff(v210, v139);
        else
          Spinlock<165,9,258>::SpinToAcquireOptimistic(v210, v140, v139);
        if ( v140 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v291);
            v142 = (CSbTransportMgr *)v291.QuadPart;
          }
          else
          {
            v142 = MEMORY[0x7FFE0008];
          }
          if ( v142 < v138 )
            v143 = 0;
          else
            v143 = v142 - v138;
          *(_QWORD *)(v140 + 3192) += v143;
        }
      }
      v211 = 1;
      CSbMsgDispatcher::CSbReceivedDialog::MoveToPendingQ((CSbMsgDispatcher::CSbReceivedDialog *)v135);
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v144 = rand();
        if ( v144 == 5 * (v144 / 5) )
          Spinlock<165,9,258>::UpdateStatSnapshot();
      }
      *v210 = 0;
      v211 = 0;
      v134 = v173;
    }
    v170 = 0;
  }
LABEL_422:
  v145 = 0;
  v146 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( *(_DWORD *)v167 || _InterlockedCompareExchange64(v167, v146, 0) )
  {
    v147 = 0;
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
    {
      v148 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( v148 && *(_QWORD *)(v148 + 272) == v148 )
        v147 = *(_QWORD *)(v148 + 256);
      if ( v147 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v292);
          v145 = (CSbTransportMgr *)v292.QuadPart;
        }
        else
        {
          v145 = MEMORY[0x7FFE0008];
        }
      }
    }
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v167, v146);
    else
      Spinlock<170,8,258>::SpinToAcquireOptimistic(v167, v147, v146);
    if ( v147 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v293);
        v149 = (CSbTransportMgr *)v293.QuadPart;
      }
      else
      {
        v149 = MEMORY[0x7FFE0008];
      }
      if ( v149 < v145 )
        v150 = 0;
      else
        v150 = v149 - v145;
      *(_QWORD *)(v147 + 3192) += v150;
    }
  }
  v168 = 1;
  if ( *((CSbMsgDispatcher **)v2 + 2763) == (CSbMsgDispatcher *)((char *)v2 + 22096) )
  {
    *((_BYTE *)a2 + 648) = 0;
    v151 = v191;
    if ( (_QWORD)v191 )
    {
      *(_QWORD *)(*(_QWORD *)(v191 + 24) + 8LL) = v192;
      *(_QWORD *)(v151 + 24) = *((_QWORD *)&v191 + 1);
      v191 = 0;
      v192 = 0;
    }
    v304 = &CConnectionOutput::`vftable';
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v152 = rand();
      if ( v152 == 5 * (v152 / 5) )
        Spinlock<170,8,258>::UpdateStatSnapshot();
    }
    *v167 = 0;
    v167 = 0;
    v168 = 0;
    if ( v201 )
    {
      CSbTaskLocalStorage::GetBrokerTLS();
      v153 = (_QWORD *)*((_QWORD *)&v200 + 1);
      v154 = v200;
      *(_QWORD *)(v200 + 8) = *((_QWORD *)&v200 + 1);
      *v153 = v154;
      v200 = 0u;
      SOS_RWLock::ReleaseLock(v202, v201);
      v201 = 0;
    }
    operator delete(v220, 1u);
    if ( (_DWORD)v196 )
      CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v196, 0);
    return 0;
  }
  else
  {
    if ( *((_DWORD *)v2 + 5530) > 1u )
    {
      v155 = 0;
      if ( *((int *)v2 + 270) > 0 )
      {
        v156 = (char *)v2 + 1736;
        while ( *v156 )
        {
          ++v155;
          v156 += 656;
          if ( v155 >= *((_DWORD *)v2 + 270) )
            goto LABEL_466;
        }
        v157 = (char *)v2 + 656 * v155;
        v157[1736] = 1;
        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v158 = rand();
          if ( v158 == 5 * (v158 / 5) )
            Spinlock<170,8,258>::UpdateStatSnapshot();
        }
        *v167 = 0;
        v168 = 0;
        v159 = v157 + 1088;
        _InterlockedIncrement((volatile signed __int32 *)v159 + 12);
        v160 = (struct IUnknown *)(v159 + 640);
        if ( !v159 )
          v160 = 0;
        CSbTaskManager::SubmitIdempotentTask(*((CSbTaskManager **)v159 + 71), (struct CSbIdempotentTask *)v159, v160, 1);
        _InterlockedDecrement((volatile signed __int32 *)v159 + 12);
      }
    }
LABEL_466:
    v161 = v191;
    if ( (_QWORD)v191 )
    {
      *(_QWORD *)(*(_QWORD *)(v191 + 24) + 8LL) = v192;
      *(_QWORD *)(v161 + 24) = *((_QWORD *)&v191 + 1);
      v191 = 0;
      v192 = 0;
    }
    v304 = &CConnectionOutput::`vftable';
    if ( v168 )
    {
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v162 = rand();
        if ( v162 == 5 * (v162 / 5) )
          Spinlock<170,8,258>::UpdateStatSnapshot();
      }
      *v167 = 0;
      v167 = 0;
      v168 = 0;
    }
    if ( v201 )
    {
      CSbTaskLocalStorage::GetBrokerTLS();
      v163 = (_QWORD *)*((_QWORD *)&v200 + 1);
      v164 = v200;
      *(_QWORD *)(v200 + 8) = *((_QWORD *)&v200 + 1);
      *v163 = v164;
      v200 = 0u;
      SOS_RWLock::ReleaseLock(v202, v201);
      v201 = 0;
    }
    operator delete(v220, 1u);
    if ( (_DWORD)v196 )
      CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v196, 0);
    return 1;
  }
}

```

## disassembly

```asm
0x100944db0  mov     [rsp+arg_8], rdx
0x100944db5  push    rdi
0x100944db6  push    r12
0x100944db8  push    r13
0x100944dba  push    r14
0x100944dbc  push    r15
0x100944dbe  mov     eax, 1A40h
0x100944dc3  call    _alloca_probe
0x100944dc8  sub     rsp, rax
0x100944dcb  mov     [rsp+1A68h+var_1208], 0FFFFFFFFFFFFFFFEh
0x100944dd7  mov     [rsp+1A68h+arg_10], rbx
0x100944ddf  mov     [rsp+1A68h+arg_18], rsi
0x100944de7  mov     rax, cs:__security_cookie
0x100944dee  xor     rax, rsp
0x100944df1  mov     [rsp+1A68h+var_38], rax
0x100944df9  mov     r12, rcx
0x100944dfc  mov     [rsp+1A68h+var_1990], rcx
0x100944e04  mov     [rsp+1A68h+var_18C0], rcx
0x100944e0c  mov     [rsp+1A68h+var_1A18], 1
0x100944e11  xor     edi, edi
0x100944e13  mov     [rsp+1A68h+var_1988], rdi
0x100944e1b  mov     r13d, 1
0x100944e21  mov     [rsp+1A68h+var_1980], r13d
0x100944e29  xorps   xmm0, xmm0
0x100944e2c  movdqu  [rsp+1A68h+var_1978], xmm0
0x100944e35  mov     [rsp+1A68h+var_1098], rdi
0x100944e3d  mov     [rsp+1A68h+var_1090], rdi
0x100944e45  mov     [rsp+1A68h+var_1088], rdi
0x100944e4d  movdqa  [rsp+1A68h+var_1078], xmm0
0x100944e56  xorps   xmm1, xmm1
0x100944e59  movdqa  [rsp+1A68h+var_1068], xmm1
0x100944e62  mov     [rsp+1A68h+var_1058], rdi
0x100944e6a  mov     [rsp+1A68h+var_19F8], rdi
0x100944e6f  lea     rax, [rsp+1A68h+var_19E8]
0x100944e77  mov     [rsp+1A68h+var_19E0], rax
0x100944e7f  lea     rax, [rsp+1A68h+var_19E8]
0x100944e87  mov     [rsp+1A68h+var_19E8], rax
0x100944e8f  mov     [rsp+1A68h+var_18B8], rdi
0x100944e97  mov     [rsp+1A68h+var_15B8], 4002FBh
0x100944ea2  mov     [rsp+1A68h+var_15B0], rdi
0x100944eaa  mov     [rsp+1A68h+var_15A0], rdi
0x100944eb2  mov     [rsp+1A68h+var_15A8], rdi
0x100944eba  mov     [rsp+1A68h+var_1598], rdi
0x100944ec2  movdqu  [rsp+1A68h+var_1960], xmm0
0x100944ecb  mov     [rsp+1A68h+var_1950], edi
0x100944ed2  lea     rax, [rcx+28h]
0x100944ed6  mov     [rsp+1A68h+var_1948], rax
0x100944ede  mov     r9d, 0FFFFFFFFh
0x100944ee4  mov     r8d, r13d
0x100944ee7  lea     rdx, [rsp+1A68h+var_15B8]
0x100944eef  lea     rcx, [rsp+1A68h+var_1960]
0x100944ef7  call    ?Acquire@UcsReentrantAutoRWLock@@QEAA_NPEBVSOS_WaitInfo@@W4RWLockMode@@K@Z; UcsReentrantAutoRWLock::Acquire(SOS_WaitInfo const *,RWLockMode,ulong)
0x100944efc  lea     rax, [r12+5660h]
0x100944f04  mov     [rsp+1A68h+var_1A10], rax
0x100944f09  mov     [rsp+1A68h+var_1A08], edi
0x100944f0d  lea     r15, ??_7CConnectionOutput@@6B@; const CConnectionOutput::`vftable'
0x100944f14  mov     [rsp+1A68h+var_1628], r15
0x100944f1c  mov     [rsp+1A68h+var_1620], rdi
0x100944f24  mov     [rsp+1A68h+var_1618], edi
0x100944f2b  mov     [rsp+1A68h+var_1610], rdi
0x100944f33  mov     [rsp+1A68h+var_1608], rdi
0x100944f3b  mov     [rsp+1A68h+var_1600], rdi
0x100944f43  mov     [rsp+1A68h+var_15F8], rdi
0x100944f4b  mov     [rsp+1A68h+var_15F0], r13b
0x100944f53  lea     rax, ??_7CSuppressOutputBase@@6B@; const CSuppressOutputBase::`vftable'
0x100944f5a  mov     [rsp+1A68h+var_1628], rax
0x100944f62  mov     [rsp+1A68h+var_15E8], rdi
0x100944f6a  mov     [rsp+1A68h+var_15D8], r13b
0x100944f72  lea     rax, ??_7CSuppressOutput@@6B@; const CSuppressOutput::`vftable'
0x100944f79  mov     [rsp+1A68h+var_1628], rax
0x100944f81  mov     rdx, gs:58h
0x100944f8a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100944f91  mov     ecx, [rax]
0x100944f93  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100944f9a  mov     eax, [rax]
0x100944f9c  add     rax, [rdx+rcx*8]
0x100944fa0  mov     rax, [rax]
0x100944fa3  mov     rcx, [rax+70h]
0x100944fa7  xorps   xmm0, xmm0
0x100944faa  movdqu  [rsp+1A68h+var_19B8], xmm0
0x100944fb3  xorps   xmm1, xmm1
0x100944fb6  movdqu  [rsp+1A68h+var_19A8], xmm1
0x100944fbf  mov     rdx, [rcx+18h]
0x100944fc3  lea     rax, [rsp+1A68h+var_1628]
0x100944fcb  cmp     rdx, rax
0x100944fce  jz      short loc_100945014
0x100944fd0  mov     qword ptr [rsp+1A68h+var_19B8], rcx
0x100944fd8  mov     qword ptr [rsp+1A68h+var_19B8+8], rdx
0x100944fe0  mov     rax, [rsp+1A68h+var_1620]
0x100944fe8  mov     qword ptr [rsp+1A68h+var_19A8], rax
0x100944ff0  lea     rax, [rsp+1A68h+var_1628]
0x100944ff8  mov     qword ptr [rsp+1A68h+var_19A8+8], rax
0x100945000  mov     [rsp+1A68h+var_1620], rdx
0x100945008  lea     rax, [rsp+1A68h+var_1628]
0x100945010  mov     [rcx+18h], rax
0x100945014  xor     r8d, r8d
0x100945017  mov     edx, r13d
0x10094501a  lea     rcx, [rsp+1A68h+var_1968]
0x100945022  call    cs:__imp_?utgettime@@YAXPEAUSQLDATEBASE@@HPEA_N@Z; utgettime(SQLDATEBASE *,int,bool *)
0x100945028  nop
0x100945029  xor     edx, edx; unsigned __int16
0x10094502b  mov     [rsp+1A68h+var_1A40], rdi; struct Worker *
0x100945030  mov     rax, cs:__imp_?hdl_backout@@YAHHHHHPEAD@Z; hdl_backout(int,int,int,int,char *)
0x100945037  mov     [rsp+1A68h+var_1A48], rax; int (*)(int, int, int, int, char *)
0x10094503c  xor     r9d, r9d; unsigned __int8
0x10094503f  xor     r8d, r8d; unsigned __int8
0x100945042  lea     rcx, [rsp+1A68h+var_1100]; this
0x10094504a  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x10094504f  nop
0x100945050  lea     rax, [rsp+1A68h+var_40]
0x100945058  mov     [rsp+1A68h+var_1200], rax
0x100945060  xor     eax, eax
0x100945062  mov     [rsp+1A68h+var_40], rax
0x10094506a  mov     [rsp+1A68h+var_1048], di
0x100945072  mov     [rsp+1A68h+var_48], edi
0x100945079  mov     [rsp+1A68h+var_44], edi
0x100945080  mov     [rsp+1A68h+var_40], 0FFFFFFFFFFFFFFFFh
0x10094508c  lea     rax, [rsp+1A68h+var_1048]
0x100945094  mov     [rsp+1A68h+var_1820], rax
0x10094509c  mov     [rsp+1A68h+var_1818], rdi
0x1009450a4  mov     [rsp+1A68h+var_1810], 0
0x1009450ac  call    ?GetBrokerTLS@CSbTaskLocalStorage@@SAAEAV1@XZ; CSbTaskLocalStorage::GetBrokerTLS(void)
0x1009450b1  mov     [rsp+1A68h+var_11F8], rax
0x1009450b9  mov     rcx, [rax+48h]
0x1009450bd  mov     [rsp+1A68h+var_1818], rcx
0x1009450c5  lea     rcx, [rsp+1A68h+var_1820]
0x1009450cd  mov     [rax+48h], rcx
0x1009450d1  mov     [rsp+1A68h+var_1700], rdi
0x1009450d9  xor     edx, edx; unsigned __int16
0x1009450db  mov     [rsp+1A68h+var_1A40], rdi; struct Worker *
0x1009450e0  lea     rax, ?ErrorHandler@CSbAutoTaskErrorOutputCapture@@SAHHHHHPEAD@Z; CSbAutoTaskErrorOutputCapture::ErrorHandler(int,int,int,int,char *)
0x1009450e7  mov     [rsp+1A68h+var_1A48], rax; int (*)(int, int, int, int, char *)
0x1009450ec  xor     r9d, r9d; unsigned __int8
0x1009450ef  xor     r8d, r8d; unsigned __int8
0x1009450f2  lea     rcx, [rsp+1A68h+var_1128]; this
0x1009450fa  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x1009450ff  nop
0x100945100  mov     [rsp+1A68h+var_17D0], 58h ; 'X'
0x10094510b  mov     rdx, gs:58h
0x100945114  mov     [rsp+1A68h+var_11F0], rdx
0x10094511c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100945123  mov     ecx, [rax]
0x100945125  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10094512c  mov     ebx, [rax]
0x10094512e  add     rbx, [rdx+rcx*8]
0x100945132  mov     [rsp+1A68h+var_11E8], rbx
0x10094513a  mov     rax, [rbx+100h]
0x100945141  mov     [rsp+1A68h+var_17A0], rax
0x100945149  test    rax, rax
0x10094514c  jnz     short loc_100945165
0x10094514e  xor     ecx, ecx
0x100945150  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100945156  mov     rax, [rbx+100h]
0x10094515d  mov     [rsp+1A68h+var_17A0], rax
0x100945165  mov     rdx, [rax+3E8h]
0x10094516c  mov     [rsp+1A68h+var_1780], rdx
0x100945174  mov     [rsp+1A68h+var_11E0], rdx
0x10094517c  mov     byte ptr [rsp+1A68h+var_1A48], 8
0x100945181  mov     r9d, 0AB8h
0x100945187  lea     r8, aSqlNtdbmsBroke_1; "sql\\ntdbms\\broker\\src\\ssbdispatcher"...
0x10094518e  mov     ecx, 18000h
0x100945193  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100945199  mov     rbx, rax
0x10094519c  mov     [rsp+1A68h+var_1880], rax
0x1009451a4  test    rax, rax
0x1009451a7  jz      short loc_1009451BC
0x1009451a9  mov     [rsp+1A68h+var_11D8], rdi
0x1009451b1  mov     rdx, r13
0x1009451b4  xor     ecx, ecx
0x1009451b6  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1009451bc  mov     [rsp+1A68h+var_18B8], rbx
0x1009451c4  mov     rax, [rsp+1A68h+var_1A10]
0x1009451c9  mov     [rsp+1A68h+var_11D0], rax
0x1009451d1  mov     [rsp+1A68h+var_11C8], rdi
0x1009451d9  mov     [rsp+1A68h+var_11A0], rdi
0x1009451e1  mov     [rsp+1A68h+var_1878], rdi
0x1009451e9  mov     [rsp+1A68h+var_1938], rdi
0x1009451f1  mov     eax, gs:48h
0x1009451f9  mov     ecx, eax
0x1009451fb  mov     [rsp+1A68h+var_18E8], rcx
0x100945203  mov     [rsp+1A68h+var_17CC], 100h
0x10094520e  mov     rax, [rsp+1A68h+var_1A10]
0x100945213  mov     [rsp+1A68h+var_1198], rax
0x10094521b  mov     eax, [rax]
0x10094521d  test    eax, eax
0x10094521f  jnz     short loc_10094524F
0x100945221  mov     rdx, [rsp+1A68h+var_18E8]
0x100945229  mov     rcx, [rsp+1A68h+var_1A10]
0x10094522e  xor     eax, eax
0x100945230  lock cmpxchg [rcx], rdx
0x100945235  mov     [rsp+1A68h+var_1190], rax
0x10094523d  mov     [rsp+1A68h+var_1188], rax
0x100945245  mov     ecx, edi
0x100945247  test    rax, rax
0x10094524a  setz    cl
0x10094524d  jmp     short loc_100945251
0x10094524f  mov     ecx, edi
0x100945251  mov     [rsp+1A68h+var_17C8], ecx
0x100945258  test    ecx, ecx
0x10094525a  jnz     loc_1009454A2
0x100945260  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100945267  mov     ecx, [rax]
0x100945269  test    cl, cl
0x10094526b  jns     loc_10094537C
0x100945271  test    cl, 4
0x100945274  jz      loc_10094537C
0x10094527a  mov     [rsp+1A68h+var_1858], rdi
0x100945282  mov     [rsp+1A68h+var_17C4], 58h ; 'X'
0x10094528d  mov     r8, gs:58h
0x100945296  mov     [rsp+1A68h+var_1180], r8
0x10094529e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1009452a5  mov     edx, [rax]
0x1009452a7  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1009452ae  mov     ecx, [rax]
0x1009452b0  mov     rbx, [r8+rdx*8]
0x1009452b4  add     rbx, rcx
0x1009452b7  mov     [rsp+1A68h+var_1178], rbx
0x1009452bf  jz      short loc_1009452CF
0x1009452c1  cmp     [rbx+110h], rbx
0x1009452c8  jnz     short loc_1009452CF
0x1009452ca  mov     eax, r13d
0x1009452cd  jmp     short loc_1009452D1
0x1009452cf  mov     eax, edi
0x1009452d1  test    eax, eax
0x1009452d3  jz      short loc_1009452E6
0x1009452d5  mov     rbx, [rbx+100h]
0x1009452dc  mov     [rsp+1A68h+var_1858], rbx
0x1009452e4  jmp     short loc_1009452EE
0x1009452e6  mov     rbx, [rsp+1A68h+var_1858]
0x1009452ee  mov     [rsp+1A68h+var_1938], rbx
0x1009452f6  test    rbx, rbx
0x1009452f9  jz      loc_100945384
0x1009452ff  lea     rax, [rsp+1A68h+var_1850]
0x100945307  mov     [rsp+1A68h+var_1170], rax
0x10094530f  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100945316  mov     ecx, [rax]
0x100945318  mov     [rsp+1A68h+var_17C0], ecx
0x10094531f  test    ecx, ecx
0x100945321  jz      short loc_10094534A
0x100945323  lea     rcx, [rsp+1A68h+PerformanceCount]; lpPerformanceCount
0x10094532b  call    cs:__imp_QueryPerformanceCounter
0x100945331  mov     [rsp+1A68h+var_17BC], eax
0x100945338  mov     rax, qword ptr [rsp+1A68h+PerformanceCount]
0x100945340  mov     [rsp+1A68h+var_1850], rax
0x100945348  jmp     short loc_10094536A
0x10094534a  mov     rax, ds:7FFE0008h
0x100945352  mov     [rsp+1A68h+var_1168], rax
0x10094535a  mov     [rsp+1A68h+var_1850], rax
0x100945362  mov     rbx, [rsp+1A68h+var_1938]
0x10094536a  mov     [rsp+1A68h+var_1160], rax
0x100945372  mov     [rsp+1A68h+var_1878], rax
0x10094537a  jmp     short loc_100945384
0x10094537c  mov     rbx, [rsp+1A68h+var_1938]
0x100945384  mov     r14d, 2
0x10094538a  mov     [rsp+1A68h+var_17B8], r14d
0x100945392  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100945399  mov     rsi, [rsp+1A68h+var_1A10]
0x10094539e  mov     rcx, rsi
0x1009453a1  cmp     byte ptr [rax+0C7h], 0
0x1009453a8  jge     short loc_1009453BC
0x1009453aa  mov     r8, [rsp+1A68h+var_18E8]
0x1009453b2  mov     rdx, rbx
0x1009453b5  call    ?SpinToAcquireOptimistic@?$Spinlock@$0KK@$07$0BAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<170,8,258>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x1009453ba  jmp     short loc_1009453C9
0x1009453bc  mov     rdx, [rsp+1A68h+var_18E8]
0x1009453c4  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0KK@$07$0BAC@@@AEAAX_K@Z; Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x1009453c9  test    rbx, rbx
0x1009453cc  jz      loc_1009454AD
0x1009453d2  lea     rax, [rsp+1A68h+var_18D8]
0x1009453da  mov     [rsp+1A68h+var_1158], rax
0x1009453e2  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1009453e9  mov     ecx, [rax]
0x1009453eb  mov     [rsp+1A68h+var_17B4], ecx
0x1009453f2  test    ecx, ecx
0x1009453f4  jz      short loc_10094541D
0x1009453f6  lea     rcx, [rsp+1A68h+var_1790]; lpPerformanceCount
0x1009453fe  call    cs:__imp_QueryPerformanceCounter
0x100945404  mov     [rsp+1A68h+var_17B0], eax
0x10094540b  mov     rax, qword ptr [rsp+1A68h+var_1790]
0x100945413  mov     [rsp+1A68h+var_18D8], rax
0x10094541b  jmp     short loc_100945442
0x10094541d  mov     rax, ds:7FFE0008h
0x100945425  mov     [rsp+1A68h+var_1568], rax
0x10094542d  mov     [rsp+1A68h+var_18D8], rax
0x100945435  mov     rsi, [rsp+1A68h+var_1A10]
0x10094543a  mov     rbx, [rsp+1A68h+var_1938]
0x100945442  lea     rcx, [rsp+1A68h+var_1878]
0x10094544a  mov     [rsp+1A68h+var_1560], rcx
0x100945452  lea     rcx, [rsp+1A68h+var_18D8]
0x10094545a  mov     [rsp+1A68h+var_1558], rcx
0x100945462  mov     rcx, [rsp+1A68h+var_1878]
0x10094546a  cmp     rax, rcx
0x10094546d  jb      short loc_100945479
0x10094546f  sub     rax, rcx
0x100945472  mov     [rsp+1A68h+var_19F0], rax
0x100945477  jmp     short loc_100945481
0x100945479  mov     rax, rdi
0x10094547c  mov     [rsp+1A68h+var_19F0], rax
0x100945481  mov     [rsp+1A68h+var_19F0], rax
0x100945486  mov     [rsp+1A68h+var_1550], rax
  ... truncated ...
```
