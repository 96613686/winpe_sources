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
  __int64 v25; // r9
  CSbMsgDispatcher::CSbReceivedDialog *v26; // rax
  CSbMsgDispatcher::CSbReceivedDialog *v27; // rbx
  _QWORD *v28; // rdx
  _QWORD *v29; // rcx
  __int64 v30; // rax
  char **v31; // rax
  BOOL v32; // ecx
  __int64 v33; // rbx
  __int64 v34; // rbx
  __int64 v36; // rbx
  CSbTransportMgr *v37; // rax
  volatile signed __int64 *v38; // r14
  CSbTransportMgr *v39; // rax
  signed __int64 v40; // rax
  CSbMsgDispatcher *v41; // rsi
  CSbMsgDispatcher::CSbReceivedDialog *v42; // rsi
  CSbMsgDispatcher::CSbReceivedDialog *v43; // r8
  _QWORD *v44; // rcx
  __int64 v45; // rax
  int v46; // eax
  BOOL v47; // ecx
  __int64 v48; // rbx
  __int64 v49; // rbx
  __int64 v51; // rbx
  CSbTransportMgr *v52; // rax
  CSbTransportMgr *v53; // rax
  signed __int64 v54; // rax
  CSbMsgDispatcher *v55; // rbx
  CSbMsgDispatcher::CSbReceivedDialog *v56; // r8
  _QWORD *v57; // rcx
  __int64 v58; // rax
  int v59; // r8d
  __int64 v60; // r9
  __int64 v61; // rbx
  _QWORD *v62; // r8
  unsigned __int64 v63; // rax
  unsigned __int64 v64; // rdx
  __int64 v66; // rcx
  int v67; // eax
  int v70; // ecx
  struct Worker *v71; // rcx
  __int64 v72; // rbx
  __int64 v73; // rbx
  struct Worker *v74; // rcx
  unsigned __int8 i; // bl
  int v76; // ecx
  __int64 v77; // rbx
  struct Worker *v78; // rcx
  char v79; // si
  char **v80; // rcx
  CSbMsgDispatcher::CSbReceivedDialog *v81; // rbx
  char **v82; // rcx
  char **v83; // r15
  char **v84; // rdx
  __int64 *v85; // r14
  char **v86; // rcx
  CSbTransportMgr *v87; // rbx
  signed __int64 v88; // r12
  __int64 v89; // rsi
  __int64 v90; // r8
  CSbTransportMgr *v91; // rax
  signed __int64 v92; // rax
  _QWORD *v93; // rcx
  __int64 v94; // rax
  int v95; // r8d
  CSbTransportMgr *v96; // rbx
  signed __int64 v97; // r15
  __int64 v98; // rsi
  __int64 v99; // r8
  char *v100; // rcx
  CSbTransportMgr *v101; // rax
  signed __int64 v102; // rax
  CSbMsgDispatcher *v103; // rcx
  char *v104; // rdx
  _QWORD *v105; // rcx
  __int64 v106; // rax
  int v107; // r8d
  char **v108; // r15
  char **v109; // rdx
  __int64 *v110; // r14
  char **v111; // rcx
  CSbTransportMgr *v112; // rbx
  signed __int64 v113; // r12
  __int64 v114; // rsi
  __int64 v115; // r8
  CSbTransportMgr *v116; // rax
  signed __int64 v117; // rax
  _QWORD *v118; // rcx
  __int64 v119; // rax
  int v120; // r8d
  CSbTransportMgr *v121; // rbx
  signed __int64 v122; // r15
  __int64 v123; // rsi
  __int64 v124; // r8
  char *v125; // rcx
  CSbTransportMgr *v126; // rax
  signed __int64 v127; // rax
  CSbMsgDispatcher *v128; // rcx
  char *v129; // rdx
  _QWORD *v130; // rcx
  __int64 v131; // rax
  int v132; // r8d
  CSbMsgDispatcher::CSbReceivedDialog *v133; // rbx
  _QWORD *v134; // rdx
  __int64 v135; // rax
  char **v136; // rcx
  volatile signed __int64 *v137; // rsi
  _QWORD *v138; // rcx
  __int64 v139; // rax
  CSbTransportMgr *v140; // rbx
  signed __int64 v141; // r15
  __int64 v142; // r14
  __int64 v143; // r8
  CSbTransportMgr *v144; // rax
  signed __int64 v145; // rax
  int v146; // r8d
  CSbTransportMgr *v147; // rbx
  signed __int64 v148; // r14
  __int64 v149; // rsi
  __int64 v150; // r8
  CSbTransportMgr *v151; // rax
  signed __int64 v152; // rax
  __int64 v153; // rdx
  int v154; // r8d
  _QWORD *v155; // rcx
  __int64 v156; // rax
  int v157; // ecx
  _BYTE *v158; // rdx
  char *v159; // rbx
  int v160; // r8d
  char *v161; // rbx
  struct IUnknown *v162; // r8
  __int64 v163; // rdx
  int v164; // r8d
  _QWORD *v165; // rcx
  __int64 v166; // rax
  __int64 v167; // r9
  char v168; // [rsp+50h] [rbp-1A18h]
  volatile signed __int64 *v169; // [rsp+58h] [rbp-1A10h] BYREF
  int v170; // [rsp+60h] [rbp-1A08h]
  unsigned __int8 v171; // [rsp+68h] [rbp-1A00h]
  CSbMsgDispatcher::CSbReceivedDialog *v172; // [rsp+70h] [rbp-19F8h]
  char *v173; // [rsp+78h] [rbp-19F0h]
  char *v174; // [rsp+80h] [rbp-19E8h] BYREF
  char **v175; // [rsp+88h] [rbp-19E0h]
  bool v176; // [rsp+90h] [rbp-19D8h]
  char v177; // [rsp+91h] [rbp-19D7h]
  bool v178; // [rsp+92h] [rbp-19D6h]
  char v179; // [rsp+93h] [rbp-19D5h]
  bool v180; // [rsp+94h] [rbp-19D4h]
  bool v181; // [rsp+95h] [rbp-19D3h]
  bool v182; // [rsp+96h] [rbp-19D2h]
  bool v183; // [rsp+97h] [rbp-19D1h]
  bool v184; // [rsp+98h] [rbp-19D0h]
  bool v185; // [rsp+99h] [rbp-19CFh]
  bool v186; // [rsp+9Ah] [rbp-19CEh]
  bool v187; // [rsp+9Bh] [rbp-19CDh]
  bool v188; // [rsp+9Ch] [rbp-19CCh]
  bool v189; // [rsp+9Dh] [rbp-19CBh]
  bool v190; // [rsp+9Eh] [rbp-19CAh]
  char *v191; // [rsp+A0h] [rbp-19C8h] BYREF
  char **v192; // [rsp+A8h] [rbp-19C0h]
  __int128 v193; // [rsp+B0h] [rbp-19B8h]
  __int128 v194; // [rsp+C0h] [rbp-19A8h]
  int v195; // [rsp+D0h] [rbp-1998h]
  int v196; // [rsp+D4h] [rbp-1994h] BYREF
  CSbMsgDispatcher *v197; // [rsp+D8h] [rbp-1990h]
  __int64 v198; // [rsp+E0h] [rbp-1988h] BYREF
  int v199; // [rsp+E8h] [rbp-1980h]
  __int128 v200; // [rsp+F0h] [rbp-1978h]
  __int64 v201; // [rsp+100h] [rbp-1968h] BYREF
  __int128 v202; // [rsp+108h] [rbp-1960h] BYREF
  unsigned int v203; // [rsp+118h] [rbp-1950h]
  char *v204; // [rsp+120h] [rbp-1948h]
  __int64 v205; // [rsp+128h] [rbp-1940h]
  __int64 v206; // [rsp+130h] [rbp-1938h]
  __int64 v207; // [rsp+138h] [rbp-1930h]
  volatile signed __int64 *v208; // [rsp+140h] [rbp-1928h]
  int v209; // [rsp+148h] [rbp-1920h]
  volatile signed __int64 *v210; // [rsp+150h] [rbp-1918h]
  int v211; // [rsp+158h] [rbp-1910h]
  volatile signed __int64 *v212; // [rsp+160h] [rbp-1908h]
  int v213; // [rsp+168h] [rbp-1900h]
  BOOL v214; // [rsp+170h] [rbp-18F8h]
  int v215; // [rsp+178h] [rbp-18F0h]
  signed __int64 UniqueThread_low; // [rsp+180h] [rbp-18E8h]
  signed __int64 v217; // [rsp+188h] [rbp-18E0h]
  CSbTransportMgr *v218; // [rsp+190h] [rbp-18D8h] BYREF
  CSbTransportMgr *v219; // [rsp+198h] [rbp-18D0h] BYREF
  CSbTransportMgr *v220; // [rsp+1A0h] [rbp-18C8h] BYREF
  CSbMsgDispatcher *v221; // [rsp+1A8h] [rbp-18C0h]
  void *v222; // [rsp+1B0h] [rbp-18B8h]
  CSbTransportMgr *v223; // [rsp+1B8h] [rbp-18B0h] BYREF
  CSbTransportMgr *v224; // [rsp+1C0h] [rbp-18A8h] BYREF
  signed __int64 v225; // [rsp+1C8h] [rbp-18A0h]
  void *v226; // [rsp+1E8h] [rbp-1880h]
  CSbTransportMgr *v227; // [rsp+1F0h] [rbp-1878h] BYREF
  _QWORD v228[2]; // [rsp+1F8h] [rbp-1870h] BYREF
  int v229; // [rsp+208h] [rbp-1860h] BYREF
  __int64 v230; // [rsp+210h] [rbp-1858h]
  CSbTransportMgr *v231; // [rsp+218h] [rbp-1850h] BYREF
  __int64 v232; // [rsp+220h] [rbp-1848h]
  CSbTransportMgr *v233; // [rsp+228h] [rbp-1840h] BYREF
  CSbMsgDispatcher::CSbReceivedDialog *v234; // [rsp+230h] [rbp-1838h]
  __int64 v235; // [rsp+238h] [rbp-1830h]
  CSbTransportMgr *v236; // [rsp+240h] [rbp-1828h] BYREF
  __int16 *v237; // [rsp+248h] [rbp-1820h] BYREF
  __int64 v238; // [rsp+250h] [rbp-1818h]
  char v239; // [rsp+258h] [rbp-1810h]
  _QWORD *v240; // [rsp+260h] [rbp-1808h]
  int k; // [rsp+268h] [rbp-1800h]
  _QWORD *v242; // [rsp+270h] [rbp-17F8h]
  int j; // [rsp+278h] [rbp-17F0h]
  int v244; // [rsp+280h] [rbp-17E8h]
  BOOL v245; // [rsp+284h] [rbp-17E4h]
  int v246; // [rsp+288h] [rbp-17E0h]
  int v247; // [rsp+28Ch] [rbp-17DCh]
  int v248; // [rsp+290h] [rbp-17D8h]
  int v249; // [rsp+294h] [rbp-17D4h]
  int v250; // [rsp+298h] [rbp-17D0h]
  int v251; // [rsp+29Ch] [rbp-17CCh]
  BOOL v252; // [rsp+2A0h] [rbp-17C8h]
  int v253; // [rsp+2A4h] [rbp-17C4h]
  int v254; // [rsp+2A8h] [rbp-17C0h]
  BOOL v255; // [rsp+2ACh] [rbp-17BCh]
  int v256; // [rsp+2B0h] [rbp-17B8h]
  int v257; // [rsp+2B4h] [rbp-17B4h]
  BOOL v258; // [rsp+2B8h] [rbp-17B0h]
  int v259; // [rsp+2BCh] [rbp-17ACh]
  int v260; // [rsp+2C0h] [rbp-17A8h]
  __int64 v261; // [rsp+2C8h] [rbp-17A0h]
  LARGE_INTEGER PerformanceCount; // [rsp+2D0h] [rbp-1798h] BYREF
  LARGE_INTEGER v263; // [rsp+2D8h] [rbp-1790h] BYREF
  int v264; // [rsp+2E0h] [rbp-1788h]
  struct IMemObj *v265; // [rsp+2E8h] [rbp-1780h]
  __int64 v266; // [rsp+2F0h] [rbp-1778h]
  char **v267; // [rsp+2F8h] [rbp-1770h]
  char **v268; // [rsp+300h] [rbp-1768h]
  __int64 v269; // [rsp+308h] [rbp-1760h]
  CSbMsgDispatcher::CSbReceivedDialog *v270; // [rsp+310h] [rbp-1758h]
  LARGE_INTEGER v271; // [rsp+318h] [rbp-1750h] BYREF
  LARGE_INTEGER v272; // [rsp+320h] [rbp-1748h] BYREF
  __int64 v273; // [rsp+328h] [rbp-1740h]
  LARGE_INTEGER v274; // [rsp+330h] [rbp-1738h] BYREF
  LARGE_INTEGER v275; // [rsp+338h] [rbp-1730h] BYREF
  __int64 v276; // [rsp+340h] [rbp-1728h]
  CSbMsgDispatcher::CSbReceivedDialog *v277; // [rsp+348h] [rbp-1720h]
  _QWORD *v278; // [rsp+350h] [rbp-1718h]
  __int64 v279; // [rsp+358h] [rbp-1710h]
  void (__fastcall ***v280)(_QWORD, _QWORD); // [rsp+360h] [rbp-1708h]
  struct Worker *v281; // [rsp+368h] [rbp-1700h]
  int v282; // [rsp+370h] [rbp-16F8h]
  struct Worker *v283; // [rsp+378h] [rbp-16F0h]
  LARGE_INTEGER v284; // [rsp+380h] [rbp-16E8h] BYREF
  LARGE_INTEGER v285; // [rsp+388h] [rbp-16E0h] BYREF
  LARGE_INTEGER v286; // [rsp+390h] [rbp-16D8h] BYREF
  LARGE_INTEGER v287; // [rsp+398h] [rbp-16D0h] BYREF
  LARGE_INTEGER v288; // [rsp+3A0h] [rbp-16C8h] BYREF
  LARGE_INTEGER v289; // [rsp+3A8h] [rbp-16C0h] BYREF
  LARGE_INTEGER v290; // [rsp+3B0h] [rbp-16B8h] BYREF
  LARGE_INTEGER v291; // [rsp+3B8h] [rbp-16B0h] BYREF
  LARGE_INTEGER v292; // [rsp+3C0h] [rbp-16A8h] BYREF
  LARGE_INTEGER v293; // [rsp+3C8h] [rbp-16A0h] BYREF
  LARGE_INTEGER v294; // [rsp+3D0h] [rbp-1698h] BYREF
  LARGE_INTEGER v295; // [rsp+3D8h] [rbp-1690h] BYREF
  BOOL v296; // [rsp+3E0h] [rbp-1688h]
  int v297; // [rsp+3E4h] [rbp-1684h]
  struct Worker *v298; // [rsp+3E8h] [rbp-1680h]
  int v299; // [rsp+3F0h] [rbp-1678h]
  BOOL v300; // [rsp+3F4h] [rbp-1674h]
  int v301; // [rsp+3F8h] [rbp-1670h]
  int v302; // [rsp+3FCh] [rbp-166Ch]
  BOOL v303; // [rsp+400h] [rbp-1668h]
  int v304; // [rsp+404h] [rbp-1664h]
  _DWORD v305[14]; // [rsp+408h] [rbp-1660h] BYREF
  void **v306; // [rsp+440h] [rbp-1628h] BYREF
  void ***v307; // [rsp+448h] [rbp-1620h]
  int v308; // [rsp+450h] [rbp-1618h]
  __int64 v309; // [rsp+458h] [rbp-1610h]
  __int64 v310; // [rsp+460h] [rbp-1608h]
  __int64 v311; // [rsp+468h] [rbp-1600h]
  __int64 v312; // [rsp+470h] [rbp-15F8h]
  char v313; // [rsp+478h] [rbp-15F0h]
  __int64 v314; // [rsp+480h] [rbp-15E8h]
  char v315; // [rsp+490h] [rbp-15D8h]
  int v316; // [rsp+4B0h] [rbp-15B8h] BYREF
  __int64 v317; // [rsp+4B8h] [rbp-15B0h]
  __int64 v318; // [rsp+4C0h] [rbp-15A8h]
  __int64 v319; // [rsp+4C8h] [rbp-15A0h]
  __int64 v320; // [rsp+4D0h] [rbp-1598h]
  int v321; // [rsp+4D8h] [rbp-1590h] BYREF
  __int64 v322; // [rsp+4E0h] [rbp-1588h]
  __int64 v323; // [rsp+4E8h] [rbp-1580h]
  __int64 v324; // [rsp+4F0h] [rbp-1578h]
  __int64 v325; // [rsp+4F8h] [rbp-1570h]
  CSbTransportMgr *v326; // [rsp+500h] [rbp-1568h]
  CSbTransportMgr **v327; // [rsp+508h] [rbp-1560h]
  CSbTransportMgr **v328; // [rsp+510h] [rbp-1558h]
  char *v329; // [rsp+518h] [rbp-1550h]
  __int64 v330; // [rsp+520h] [rbp-1548h]
  char *v331; // [rsp+528h] [rbp-1540h]
  volatile signed __int64 *v332; // [rsp+530h] [rbp-1538h]
  volatile signed __int64 *v333; // [rsp+538h] [rbp-1530h]
  struct CSbTaskLocalStorage *v334; // [rsp+540h] [rbp-1528h]
  __int64 v335; // [rsp+548h] [rbp-1520h]
  void *v336; // [rsp+550h] [rbp-1518h]
  volatile signed __int64 *v337; // [rsp+558h] [rbp-1510h]
  volatile signed __int64 *v338; // [rsp+560h] [rbp-1508h]
  struct CSbTaskLocalStorage *v339; // [rsp+568h] [rbp-1500h]
  __int64 v340; // [rsp+570h] [rbp-14F8h]
  void *v341; // [rsp+578h] [rbp-14F0h]
  volatile signed __int64 *v342; // [rsp+580h] [rbp-14E8h]
  volatile signed __int64 *v343; // [rsp+588h] [rbp-14E0h]
  _QWORD *v344; // [rsp+590h] [rbp-14D8h]
  _QWORD *v345; // [rsp+598h] [rbp-14D0h]
  _QWORD *v346; // [rsp+5A0h] [rbp-14C8h]
  char *v347; // [rsp+5A8h] [rbp-14C0h]
  char *v348; // [rsp+5B0h] [rbp-14B8h]
  _QWORD *v349; // [rsp+5B8h] [rbp-14B0h]
  _QWORD *v350; // [rsp+5C0h] [rbp-14A8h]
  _QWORD *v351; // [rsp+5C8h] [rbp-14A0h]
  char *v352; // [rsp+5D0h] [rbp-1498h]
  char *v353; // [rsp+5D8h] [rbp-1490h]
  _QWORD *v354; // [rsp+5E0h] [rbp-1488h]
  _QWORD *v355; // [rsp+5E8h] [rbp-1480h]
  _QWORD *v356; // [rsp+5F0h] [rbp-1478h]
  char *v357; // [rsp+5F8h] [rbp-1470h]
  char *v358; // [rsp+600h] [rbp-1468h]
  __int64 v359; // [rsp+608h] [rbp-1460h]
  _QWORD *v360; // [rsp+610h] [rbp-1458h]
  _QWORD *v361; // [rsp+618h] [rbp-1450h]
  _QWORD *v362; // [rsp+620h] [rbp-1448h]
  __int64 v363; // [rsp+628h] [rbp-1440h]
  __int64 v364; // [rsp+630h] [rbp-1438h]
  __int64 v365; // [rsp+638h] [rbp-1430h]
  int *v366; // [rsp+640h] [rbp-1428h]
  char **v367; // [rsp+648h] [rbp-1420h]
  char *v368; // [rsp+650h] [rbp-1418h]
  _QWORD *v369; // [rsp+658h] [rbp-1410h]
  __int64 v370; // [rsp+660h] [rbp-1408h]
  char *v371; // [rsp+668h] [rbp-1400h]
  volatile signed __int64 *v372; // [rsp+670h] [rbp-13F8h]
  __int64 v373; // [rsp+678h] [rbp-13F0h]
  __int64 v374; // [rsp+680h] [rbp-13E8h]
  volatile signed __int64 *v375; // [rsp+688h] [rbp-13E0h]
  signed __int64 v376; // [rsp+690h] [rbp-13D8h]
  signed __int64 v377; // [rsp+698h] [rbp-13D0h]
  _QWORD *v378; // [rsp+6A0h] [rbp-13C8h]
  __int64 v379; // [rsp+6A8h] [rbp-13C0h]
  CSbTransportMgr **v380; // [rsp+6B0h] [rbp-13B8h]
  CSbTransportMgr *v381; // [rsp+6B8h] [rbp-13B0h]
  CSbTransportMgr *v382; // [rsp+6C0h] [rbp-13A8h]
  CSbTransportMgr **v383; // [rsp+6C8h] [rbp-13A0h]
  CSbTransportMgr *v384; // [rsp+6D0h] [rbp-1398h]
  CSbTransportMgr **v385; // [rsp+6D8h] [rbp-1390h]
  CSbTransportMgr **v386; // [rsp+6E0h] [rbp-1388h]
  char *v387; // [rsp+6E8h] [rbp-1380h]
  __int64 v388; // [rsp+6F0h] [rbp-1378h]
  char *v389; // [rsp+6F8h] [rbp-1370h]
  CSbMsgDispatcher::CSbReceivedDialog *v390; // [rsp+700h] [rbp-1368h]
  char *v391; // [rsp+708h] [rbp-1360h]
  _QWORD *v392; // [rsp+710h] [rbp-1358h]
  __int64 v393; // [rsp+718h] [rbp-1350h]
  volatile signed __int64 *v394; // [rsp+720h] [rbp-1348h]
  volatile signed __int64 *v395; // [rsp+728h] [rbp-1340h]
  __int64 v396; // [rsp+730h] [rbp-1338h]
  __int64 v397; // [rsp+738h] [rbp-1330h]
  volatile signed __int64 *v398; // [rsp+740h] [rbp-1328h]
  signed __int64 v399; // [rsp+748h] [rbp-1320h]
  signed __int64 v400; // [rsp+750h] [rbp-1318h]
  _QWORD *v401; // [rsp+758h] [rbp-1310h]
  __int64 v402; // [rsp+760h] [rbp-1308h]
  CSbTransportMgr **v403; // [rsp+768h] [rbp-1300h]
  CSbTransportMgr *v404; // [rsp+770h] [rbp-12F8h]
  CSbTransportMgr *v405; // [rsp+778h] [rbp-12F0h]
  CSbTransportMgr **v406; // [rsp+780h] [rbp-12E8h]
  CSbTransportMgr *v407; // [rsp+788h] [rbp-12E0h]
  CSbTransportMgr **v408; // [rsp+790h] [rbp-12D8h]
  CSbTransportMgr **v409; // [rsp+798h] [rbp-12D0h]
  char *v410; // [rsp+7A0h] [rbp-12C8h]
  __int64 v411; // [rsp+7A8h] [rbp-12C0h]
  char *v412; // [rsp+7B0h] [rbp-12B8h]
  CSbMsgDispatcher::CSbReceivedDialog *v413; // [rsp+7B8h] [rbp-12B0h]
  char *v414; // [rsp+7C0h] [rbp-12A8h]
  _QWORD *v415; // [rsp+7C8h] [rbp-12A0h]
  __int64 v416; // [rsp+7D0h] [rbp-1298h]
  volatile signed __int64 *v417; // [rsp+7D8h] [rbp-1290h]
  char *v418; // [rsp+7E0h] [rbp-1288h]
  char **v419; // [rsp+7E8h] [rbp-1280h]
  _QWORD *v420; // [rsp+7F0h] [rbp-1278h]
  __int64 v421; // [rsp+7F8h] [rbp-1270h]
  _QWORD *v422; // [rsp+800h] [rbp-1268h]
  unsigned __int64 v423; // [rsp+808h] [rbp-1260h]
  __int64 v424; // [rsp+810h] [rbp-1258h]
  __int64 v425; // [rsp+818h] [rbp-1250h]
  __int64 *v426; // [rsp+820h] [rbp-1248h]
  __int64 *v427; // [rsp+828h] [rbp-1240h]
  int *v428; // [rsp+830h] [rbp-1238h]
  int *v429; // [rsp+838h] [rbp-1230h]
  void (__fastcall ***v430)(_QWORD, _QWORD); // [rsp+840h] [rbp-1228h]
  _QWORD *v431; // [rsp+848h] [rbp-1220h]
  __int64 v432; // [rsp+850h] [rbp-1218h]
  struct CSbTaskLocalStorage *v433; // [rsp+858h] [rbp-1210h]
  __int64 v434; // [rsp+860h] [rbp-1208h]
  __int64 *v435; // [rsp+868h] [rbp-1200h]
  struct CSbTaskLocalStorage *BrokerTLS; // [rsp+870h] [rbp-11F8h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+878h] [rbp-11F0h]
  __int64 v438; // [rsp+880h] [rbp-11E8h]
  struct IMemObj *v439; // [rsp+888h] [rbp-11E0h]
  __int64 v440; // [rsp+890h] [rbp-11D8h]
  volatile signed __int64 *v441; // [rsp+898h] [rbp-11D0h]
  __int64 v442; // [rsp+8A0h] [rbp-11C8h]
  _QWORD v443[4]; // [rsp+8B8h] [rbp-11B0h] BYREF
  signed __int64 v444; // [rsp+8D8h] [rbp-1190h]
  signed __int64 v445; // [rsp+8E0h] [rbp-1188h]
  _QWORD *v446; // [rsp+8E8h] [rbp-1180h]
  __int64 v447; // [rsp+8F0h] [rbp-1178h]
  CSbTransportMgr **v448; // [rsp+8F8h] [rbp-1170h]
  CSbTransportMgr *v449; // [rsp+900h] [rbp-1168h]
  CSbTransportMgr *v450; // [rsp+908h] [rbp-1160h]
  CSbTransportMgr **v451; // [rsp+910h] [rbp-1158h]
  _BYTE v452[40]; // [rsp+940h] [rbp-1128h] BYREF
  _BYTE v453[40]; // [rsp+968h] [rbp-1100h] BYREF
  _BYTE v454[64]; // [rsp+990h] [rbp-10D8h] BYREF
  void *v455; // [rsp+9D0h] [rbp-1098h] BYREF
  __int64 v456; // [rsp+9D8h] [rbp-1090h]
  __int64 v457; // [rsp+9E0h] [rbp-1088h]
  __int64 v458; // [rsp+9E8h] [rbp-1080h] BYREF
  __int128 v459; // [rsp+9F0h] [rbp-1078h]
  __int128 v460; // [rsp+A00h] [rbp-1068h]
  __int64 v461; // [rsp+A10h] [rbp-1058h]
  __int16 v462; // [rsp+A20h] [rbp-1048h] BYREF
  int v463; // [rsp+1A20h] [rbp-48h]
  int v464; // [rsp+1A24h] [rbp-44h]
  __int64 v465; // [rsp+1A28h] [rbp-40h] BYREF

  v434 = -2;
  v2 = this;
  v197 = this;
  v221 = this;
  v168 = 1;
  v198 = 0;
  v199 = 1;
  v200 = 0;
  v455 = 0;
  v456 = 0;
  v457 = 0;
  v459 = 0;
  v460 = 0;
  v461 = 0;
  v172 = 0;
  v175 = &v174;
  v174 = (char *)&v174;
  v222 = 0;
  v316 = 4195067;
  v317 = 0;
  v319 = 0;
  v318 = 0;
  v320 = 0;
  v202 = 0;
  v203 = 0;
  v204 = (char *)this + 40;
  UcsReentrantAutoRWLock::Acquire(&v202, &v316, 1, 0xFFFFFFFFLL);
  v169 = (volatile signed __int64 *)((char *)v2 + 22112);
  v170 = 0;
  v307 = 0;
  v308 = 0;
  v309 = 0;
  v310 = 0;
  v311 = 0;
  v312 = 0;
  v313 = 1;
  v314 = 0;
  v315 = 1;
  v306 = &CSuppressOutput::`vftable';
  v3 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset)
                 + 112LL);
  v193 = 0;
  v194 = 0;
  v4 = *(void ****)(v3 + 24);
  if ( v4 != &v306 )
  {
    *(_QWORD *)&v193 = v3;
    *((_QWORD *)&v193 + 1) = v4;
    *(_QWORD *)&v194 = v307;
    *((_QWORD *)&v194 + 1) = &v306;
    v307 = v4;
    *(_QWORD *)(v3 + 24) = &v306;
  }
  utgettime((struct SQLDATEBASE *)&v201, 1, 0);
  ExcHandler::ExcHandler((ExcHandler *)v453, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_backout, 0);
  v435 = &v465;
  v462 = 0;
  v463 = 0;
  v464 = 0;
  v465 = -1;
  v237 = &v462;
  v238 = 0;
  v239 = 0;
  BrokerTLS = CSbTaskLocalStorage::GetBrokerTLS();
  v238 = *((_QWORD *)BrokerTLS + 9);
  *((_QWORD *)BrokerTLS + 9) = &v237;
  v281 = 0;
  ExcHandler::ExcHandler(
    (ExcHandler *)v452,
    0,
    0,
    0,
    (int (*)(int, int, int, int, char *))CSbAutoTaskErrorOutputCapture::ErrorHandler,
    0);
  v250 = 88;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v5 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
  v438 = v5;
  v6 = *(_QWORD *)(v5 + 256);
  v261 = v6;
  if ( !v6 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v6 = *(_QWORD *)(v5 + 256);
    v261 = v6;
  }
  v265 = *(struct IMemObj **)(v6 + 1000);
  v439 = v265;
  v7 = operator new[](0x18000u, v265, "sql\\ntdbms\\broker\\src\\ssbdispatcher.cpp", 2744, 8u);
  v226 = v7;
  if ( v7 )
  {
    v440 = 0;
    operator delete(0, 1u);
  }
  v222 = v7;
  v441 = v169;
  v442 = 0;
  v443[2] = 0;
  v227 = 0;
  v206 = 0;
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  v251 = 256;
  v443[3] = v169;
  if ( *(_DWORD *)v169 )
  {
    v8 = 0;
  }
  else
  {
    v444 = _InterlockedCompareExchange64(v169, UniqueThread_low, 0);
    v445 = v444;
    v8 = v444 == 0;
  }
  v252 = v8;
  if ( v8 )
  {
    v15 = v169;
  }
  else
  {
    if ( (SOS_PublicGlobals::sm_osStats & 0x80u) != 0 && (SOS_PublicGlobals::sm_osStats & 4) != 0 )
    {
      v230 = 0;
      v253 = 88;
      v446 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v9 = v446[SystemThread_TlsIndex];
      v10 = SystemThread_TlsOffset + v9 == 0;
      v11 = SystemThread_TlsOffset + v9;
      v447 = v11;
      if ( !v10 && *(_QWORD *)(v11 + 272) == v11 )
      {
        v13 = *(_QWORD *)(v11 + 256);
        v230 = v13;
      }
      else
      {
        v13 = v230;
      }
      v206 = v13;
      if ( v13 )
      {
        v448 = &v231;
        v254 = Base_PublicGlobals::sm_invariantTscAvailable;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          v255 = QueryPerformanceCounter(&PerformanceCount);
          QuadPart = (CSbTransportMgr *)PerformanceCount.QuadPart;
          v231 = (CSbTransportMgr *)PerformanceCount.QuadPart;
        }
        else
        {
          QuadPart = MEMORY[0x7FFE0008];
          v449 = MEMORY[0x7FFE0008];
          v231 = MEMORY[0x7FFE0008];
          v13 = v206;
        }
        v450 = QuadPart;
        v227 = QuadPart;
      }
    }
    else
    {
      v13 = v206;
    }
    v256 = 2;
    v15 = v169;
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v169, UniqueThread_low);
    else
      Spinlock<170,8,258>::SpinToAcquireOptimistic(v169, v13, UniqueThread_low);
    if ( v13 )
    {
      v451 = &v218;
      v257 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v258 = QueryPerformanceCounter(&v263);
        v16 = (CSbTransportMgr *)v263.QuadPart;
        v218 = (CSbTransportMgr *)v263.QuadPart;
      }
      else
      {
        v16 = MEMORY[0x7FFE0008];
        v326 = MEMORY[0x7FFE0008];
        v218 = MEMORY[0x7FFE0008];
        v15 = v169;
        v13 = v206;
      }
      v327 = &v227;
      v328 = &v218;
      if ( v16 < v227 )
      {
        v17 = 0;
        v173 = 0;
      }
      else
      {
        v17 = v16 - v227;
        v173 = (char *)v17;
      }
      v173 = (char *)v17;
      v329 = (char *)v17;
      v330 = v13 + 3192;
      *(_QWORD *)(v13 + 3192) += v17;
    }
  }
  v170 = 1;
  v331 = (char *)v2 + 22096;
  if ( *((CSbMsgDispatcher **)v2 + 2763) == (CSbMsgDispatcher *)((char *)v2 + 22096) )
  {
    *((_BYTE *)a2 + 648) = 0;
    v332 = v15;
    v176 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v18 = rand();
      if ( v18 == 5 * (v18 / 5) )
        Spinlock<170,8,258>::UpdateStatSnapshot();
    }
    v333 = v15;
    *v15 = 0;
    v170 = 0;
    v177 = 0;
    ExcHandler::~ExcHandler((ExcHandler *)v452);
    v334 = CSbTaskLocalStorage::GetBrokerTLS();
    *((_QWORD *)v334 + 9) = v238;
    ExcHandler::~ExcHandler((ExcHandler *)v453);
    v19 = v193;
    if ( (_QWORD)v193 )
    {
      *(_QWORD *)(*(_QWORD *)(v193 + 24) + 8LL) = v194;
      v335 = *(_QWORD *)(v19 + 24);
      *(_QWORD *)(v19 + 24) = *((_QWORD *)&v193 + 1);
      v193 = 0;
      v194 = 0;
    }
    v306 = &CConnectionOutput::`vftable';
    SpinlockHolder<170,8,258>::~SpinlockHolder<170,8,258>(&v169);
    UcsReentrantAutoRWLock::Release((UcsReentrantAutoRWLock *)&v202);
    v336 = v226;
    operator delete(v226, 1u);
    if ( (_DWORD)v198 )
      CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v198, 0);
    return 0;
  }
  if ( !*((_BYTE *)v2 + 22508) )
  {
    *((_BYTE *)a2 + 648) = 0;
    v337 = v169;
    v178 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v21 = rand();
      if ( v21 == 5 * (v21 / 5) )
        Spinlock<170,8,258>::UpdateStatSnapshot();
    }
    v338 = v169;
    *v169 = 0;
    v170 = 0;
    v179 = 0;
    ExcHandler::~ExcHandler((ExcHandler *)v452);
    v339 = CSbTaskLocalStorage::GetBrokerTLS();
    *((_QWORD *)v339 + 9) = v238;
    ExcHandler::~ExcHandler((ExcHandler *)v453);
    v22 = v193;
    if ( (_QWORD)v193 )
    {
      *(_QWORD *)(*(_QWORD *)(v193 + 24) + 8LL) = v194;
      v340 = *(_QWORD *)(v22 + 24);
      *(_QWORD *)(v22 + 24) = *((_QWORD *)&v193 + 1);
      v193 = 0;
      v194 = 0;
    }
    v306 = &CConnectionOutput::`vftable';
    SpinlockHolder<170,8,258>::~SpinlockHolder<170,8,258>(&v169);
    UcsReentrantAutoRWLock::Release((UcsReentrantAutoRWLock *)&v202);
    v341 = v226;
    operator delete(v226, 1u);
    if ( (_DWORD)v198 )
      CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v198, 0);
    return 0;
  }
  v342 = v169;
  v180 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v23 = rand();
    if ( v23 == 5 * (v23 / 5) )
      Spinlock<170,8,258>::UpdateStatSnapshot();
  }
  v343 = v169;
  *v169 = 0;
  v170 = 0;
  LODWORD(v456) = 98304;
  v455 = v226;
  utgettime((struct SQLDATEBASE *)&v458, 1, 0);
  SQLDATE::DateAdd((SQLDATE *)&v458, 9, 500);
  v214 = 0;
  v199 = 1;
  v259 = 88;
  v344 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v345 = (_QWORD *)(v344[SystemThread_TlsIndex] + SystemThread_TlsOffset);
  v346 = v345;
  v347 = (char *)*v345;
  v348 = v347;
  v173 = v347;
  *(_QWORD *)&v200 = *((_QWORD *)v347 + 18);
  v260 = 88;
  v349 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v350 = (_QWORD *)(v349[SystemThread_TlsIndex] + SystemThread_TlsOffset);
  v351 = v350;
  v352 = (char *)*v350;
  v353 = v352;
  v173 = v352;
  v24 = v352[152];
  v214 = v24 != 0;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v200 + 464LL))(v200) )
  {
    if ( v24 && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v200 + 488LL))(v200) )
      utassert_fail(
        1u,
        "rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()",
        "automsqlxact.cpp",
        235,
        0);
    (*(void (__fastcall **)(_QWORD, __int64, __int64, char *))(*(_QWORD *)v200 + 232LL))(v200, 2, 1, (char *)&v198 + 4);
    v199 = 1;
    LODWORD(v198) = 3;
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64, __int64, int, int, _BYTE, _QWORD, bool))(*(_QWORD *)v200 + 8LL))(
      v200,
      L"SbDispatchRecvMessages",
      44,
      1,
      2,
      1,
      0,
      0,
      v24 != 0);
    LODWORD(v198) = 1;
  }
  v264 = 88;
  v354 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v355 = (_QWORD *)(v354[SystemThread_TlsIndex] + SystemThread_TlsOffset);
  v356 = v355;
  v357 = (char *)*v355;
  v358 = v357;
  v173 = v357;
  v359 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v357 + 18) + 432LL))(*((_QWORD *)v357 + 18));
  v266 = g_metadataFactory(v265, v359, "sql\\ntdbms\\broker\\src\\ssbdispatcher.cpp", 2785);
  v280 = (void (__fastcall ***)(_QWORD, _QWORD))v266;
  v249 = 88;
  v360 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v361 = (_QWORD *)(v360[SystemThread_TlsIndex] + SystemThread_TlsOffset);
  v362 = v361;
  v363 = *v361;
  v364 = v363;
  v365 = v266;
  v228[0] = v363;
  v228[1] = v266;
  v366 = &v229;
  v229 = 0;
  while ( 2 )
  {
    v367 = &v174;
    if ( v175 == &v174 )
    {
      v267 = 0;
LABEL_69:
      v26 = 0;
      v268 = 0;
      goto LABEL_71;
    }
    v267 = v175;
    if ( !v175 )
      goto LABEL_69;
    v26 = (CSbMsgDispatcher::CSbReceivedDialog *)(v175 - 1);
    v268 = v175 - 1;
LABEL_71:
    while ( 1 )
    {
      v172 = v26;
      if ( !v26 )
        break;
      if ( *((_DWORD *)v26 + 25) == 1 )
      {
        v27 = v172;
        v28 = (_QWORD *)((char *)v172 + 8);
        v368 = (char *)v172 + 8;
        v29 = (_QWORD *)*((_QWORD *)v172 + 2);
        v369 = v29;
        v30 = *((_QWORD *)v172 + 1);
        v370 = v30;
        *(_QWORD *)(v30 + 8) = v29;
        *v29 = v30;
        v28[1] = 0;
        *v28 = 0;
        goto LABEL_170;
      }
      v371 = (char *)v172 + 8;
      v31 = (char **)*((_QWORD *)v172 + 2);
      if ( v31 == &v174 )
      {
        v269 = 0;
        goto LABEL_77;
      }
      v269 = *((_QWORD *)v172 + 2);
      if ( v31 )
      {
        v26 = (CSbMsgDispatcher::CSbReceivedDialog *)(v31 - 1);
        v270 = v26;
      }
      else
      {
LABEL_77:
        v26 = 0;
        v270 = 0;
      }
    }
    v372 = v169;
    v373 = 0;
    v374 = 0;
    v223 = 0;
    v207 = 0;
    v225 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    v282 = 256;
    v375 = v169;
    if ( *(_DWORD *)v169 )
    {
      v32 = 0;
    }
    else
    {
      v376 = _InterlockedCompareExchange64(v169, v225, 0);
      v377 = v376;
      v32 = v376 == 0;
    }
    v296 = v32;
    if ( v32 )
    {
      v38 = v169;
    }
    else
    {
      if ( (SOS_PublicGlobals::sm_osStats & 0x80u) != 0 && (SOS_PublicGlobals::sm_osStats & 4) != 0 )
      {
        v232 = 0;
        v297 = 88;
        v378 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v33 = v378[SystemThread_TlsIndex];
        v10 = SystemThread_TlsOffset + v33 == 0;
        v34 = SystemThread_TlsOffset + v33;
        v379 = v34;
        if ( !v10 && *(_QWORD *)(v34 + 272) == v34 )
        {
          v36 = *(_QWORD *)(v34 + 256);
          v232 = v36;
        }
        else
        {
          v36 = v232;
        }
        v207 = v36;
        if ( v36 )
        {
          v380 = &v233;
          v299 = Base_PublicGlobals::sm_invariantTscAvailable;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            v300 = QueryPerformanceCounter(&v271);
            v37 = (CSbTransportMgr *)v271.QuadPart;
            v233 = (CSbTransportMgr *)v271.QuadPart;
          }
          else
          {
            v37 = MEMORY[0x7FFE0008];
            v381 = MEMORY[0x7FFE0008];
            v233 = MEMORY[0x7FFE0008];
            v36 = v207;
          }
          v382 = v37;
          v223 = v37;
        }
      }
      else
      {
        v36 = v207;
      }
      v301 = 2;
      v38 = v169;
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v169, v225);
      else
        Spinlock<170,8,258>::SpinToAcquireOptimistic(v169, v36, v225);
      if ( v36 )
      {
        v383 = &v224;
        v302 = Base_PublicGlobals::sm_invariantTscAvailable;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          v303 = QueryPerformanceCounter(&v272);
          v39 = (CSbTransportMgr *)v272.QuadPart;
          v224 = (CSbTransportMgr *)v272.QuadPart;
        }
        else
        {
          v39 = MEMORY[0x7FFE0008];
          v384 = MEMORY[0x7FFE0008];
          v224 = MEMORY[0x7FFE0008];
          v38 = v169;
          v36 = v207;
        }
        v385 = &v223;
        v386 = &v224;
        if ( v39 < v223 )
        {
          v40 = 0;
          v173 = 0;
        }
        else
        {
          v40 = v39 - v223;
          v173 = (char *)v40;
        }
        v173 = (char *)v40;
        v387 = (char *)v40;
        v388 = v36 + 3192;
        *(_QWORD *)(v36 + 3192) += v40;
      }
    }
    v170 = 1;
    v389 = (char *)v2 + 22096;
    v41 = (CSbMsgDispatcher *)*((_QWORD *)v2 + 2763);
    if ( v41 == (CSbMsgDispatcher *)((char *)v2 + 22096) )
    {
      v273 = 0;
      goto LABEL_113;
    }
    v273 = *((_QWORD *)v2 + 2763);
    if ( v41 )
    {
      v42 = (CSbMsgDispatcher *)((char *)v41 - 8);
      v234 = v42;
      v43 = v42;
    }
    else
    {
LABEL_113:
      v42 = 0;
      v234 = 0;
      v43 = 0;
    }
    v390 = v42;
    if ( v43 )
    {
      v391 = (char *)v43 + 8;
      v44 = (_QWORD *)*((_QWORD *)v43 + 2);
      v392 = v44;
      v45 = *((_QWORD *)v43 + 1);
      v393 = v45;
      *(_QWORD *)(v45 + 8) = v44;
      *v44 = v45;
      *((_QWORD *)v43 + 2) = 0;
      *((_QWORD *)v43 + 1) = 0;
    }
    v27 = v42;
    v172 = v42;
    if ( v43 )
    {
      --*((_DWORD *)v2 + 5530);
      v27 = v172;
      v38 = v169;
      v42 = v234;
    }
    v394 = v38;
    v181 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v46 = rand();
      v43 = (CSbMsgDispatcher::CSbReceivedDialog *)(unsigned int)v46;
      if ( v46 == 5 * (v46 / 5) )
        Spinlock<170,8,258>::UpdateStatSnapshot();
    }
    *v38 = 0;
    v170 = 0;
    if ( v42 )
      goto LABEL_170;
    if ( SHIDWORD(v457) <= 1 )
      goto LABEL_169;
    v321 = 4194400;
    v322 = 0;
    v324 = 0;
    v323 = 0;
    v325 = 0;
    if ( (unsigned int)SOS_Task::Sleep(0, &v321, v43, v25) != 2 )
    {
      v395 = v38;
      v396 = 0;
      v397 = 0;
      v220 = 0;
      v205 = 0;
      v217 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      v304 = 256;
      v398 = v169;
      if ( *(_DWORD *)v169 )
      {
        v47 = 0;
      }
      else
      {
        v399 = _InterlockedCompareExchange64(v169, v217, 0);
        v400 = v399;
        v47 = v399 == 0;
      }
      v305[6] = v47;
      if ( !v47 )
      {
        if ( (SOS_PublicGlobals::sm_osStats & 0x80u) != 0 && (SOS_PublicGlobals::sm_osStats & 4) != 0 )
        {
          v235 = 0;
          v305[7] = 88;
          v401 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v48 = v401[SystemThread_TlsIndex];
          v10 = SystemThread_TlsOffset + v48 == 0;
          v49 = SystemThread_TlsOffset + v48;
          v402 = v49;
          if ( !v10 && *(_QWORD *)(v49 + 272) == v49 )
          {
            v51 = *(_QWORD *)(v49 + 256);
            v235 = v51;
          }
          else
          {
            v51 = v235;
          }
          v205 = v51;
          if ( v51 )
          {
            v403 = &v236;
            v305[8] = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              v305[9] = QueryPerformanceCounter(&v274);
              v52 = (CSbTransportMgr *)v274.QuadPart;
              v236 = (CSbTransportMgr *)v274.QuadPart;
            }
            else
            {
              v52 = MEMORY[0x7FFE0008];
              v404 = MEMORY[0x7FFE0008];
              v236 = MEMORY[0x7FFE0008];
              v51 = v205;
            }
            v405 = v52;
            v220 = v52;
          }
        }
        else
        {
          v51 = v205;
        }
        v305[10] = 2;
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v169, v217);
        else
          Spinlock<170,8,258>::SpinToAcquireOptimistic(v169, v51, v217);
        if ( v51 )
        {
          v406 = &v219;
          v244 = Base_PublicGlobals::sm_invariantTscAvailable;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            v245 = QueryPerformanceCounter(&v275);
            v53 = (CSbTransportMgr *)v275.QuadPart;
            v219 = (CSbTransportMgr *)v275.QuadPart;
          }
          else
          {
            v53 = MEMORY[0x7FFE0008];
            v407 = MEMORY[0x7FFE0008];
            v219 = MEMORY[0x7FFE0008];
            v51 = v205;
          }
          v408 = &v220;
          v409 = &v219;
          if ( v53 < v220 )
          {
            v54 = 0;
            v173 = 0;
          }
          else
          {
            v54 = v53 - v220;
            v173 = (char *)v54;
          }
          v173 = (char *)v54;
          v410 = (char *)v54;
          v411 = v51 + 3192;
          *(_QWORD *)(v51 + 3192) += v54;
        }
      }
      v170 = 1;
      v412 = (char *)v2 + 22096;
      v55 = (CSbMsgDispatcher *)*((_QWORD *)v2 + 2763);
      if ( v55 == (CSbMsgDispatcher *)((char *)v2 + 22096) )
      {
        v276 = 0;
      }
      else
      {
        v276 = *((_QWORD *)v2 + 2763);
        if ( v55 )
        {
          v27 = (CSbMsgDispatcher *)((char *)v55 - 8);
          v277 = v27;
          v56 = v27;
          goto LABEL_161;
        }
      }
      v27 = 0;
      v277 = 0;
      v56 = 0;
LABEL_161:
      v413 = v27;
      if ( v56 )
      {
        v414 = (char *)v56 + 8;
        v57 = (_QWORD *)*((_QWORD *)v56 + 2);
        v415 = v57;
        v58 = *((_QWORD *)v56 + 1);
        v416 = v58;
        *(_QWORD *)(v58 + 8) = v57;
        *v57 = v58;
        *((_QWORD *)v56 + 2) = 0;
        *((_QWORD *)v56 + 1) = 0;
      }
      v172 = v27;
      if ( v56 )
      {
        --*((_DWORD *)v2 + 5530);
        v27 = v172;
      }
      v417 = v169;
      v182 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v59 = rand();
        if ( v59 == 5 * (v59 / 5) )
          Spinlock<170,8,258>::UpdateStatSnapshot();
      }
      *v169 = 0;
      v170 = 0;
LABEL_169:
      if ( !v27 )
        goto LABEL_197;
LABEL_170:
      v418 = (char *)v27 + 8;
      v419 = &v174;
      *((_QWORD *)v27 + 1) = v174;
      *((_QWORD *)v174 + 1) = (char *)v27 + 8;
      v174 = (char *)v27 + 8;
      *((_QWORD *)v27 + 2) = &v174;
      CSbMsgDispatcher::CSbReceivedDialog::Dispatch(
        v27,
        (struct CSsbClassifier *)v228,
        (struct SbReceivedMessageInfo *)&v455);
      v246 = 88;
      v420 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v61 = v420[SystemThread_TlsIndex] + SystemThread_TlsOffset;
      v421 = v61;
      v62 = *(_QWORD **)(v61 + 256);
      v278 = v62;
      if ( !v62 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v62 = *(_QWORD **)(v61 + 256);
        v278 = v62;
      }
      v422 = v62;
      v63 = __rdtsc();
      v423 = v63;
      v64 = v62[104];
      if ( v63 > v64 || v64 != 0x7FFFFFFFFFFFFFFFLL && v64 - v63 > *(_QWORD *)(v62[76] + 3568LL) )
      {
        v195 = SOS_Task::Sleep(0, &yieldWait, v62, v60);
        if ( v195 == 2 )
        {
          v168 = 0;
          goto LABEL_197;
        }
      }
      else
      {
        v279 = v62[75];
        v424 = v279 + 188;
        if ( (*(_DWORD *)(v279 + 188) & 4) != 0 )
        {
          v66 = *(_QWORD *)(v279 + 152);
          v425 = v66;
          if ( (*(_BYTE *)(v66 + 616) & 1) == 0 )
          {
            v67 = *(_DWORD *)(v66 + 800);
            if ( (v67 & 0x80u) == 0 && (v67 & 0x100) == 0 )
            {
              v195 = 2;
              v168 = 0;
              goto LABEL_197;
            }
          }
        }
        v195 = 0;
      }
      utgettime((struct SQLDATEBASE *)&v201, 1, 0);
      v426 = &v201;
      v427 = &v458;
      if ( v201 >= v458 )
      {
        v70 = 4;
        if ( v201 == v458 )
          v70 = 2;
      }
      else
      {
        v70 = 1;
      }
      if ( v70 == 4 )
        goto LABEL_197;
      continue;
    }
    break;
  }
  v168 = 0;
LABEL_197:
  v428 = &v229;
  if ( v229 )
  {
    v229 = 0;
    ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
  }
  v429 = &v229;
  if ( v229 )
  {
    v229 = 0;
    ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
  }
  v430 = v280;
  if ( v280 )
    (**v280)(v280, 1);
  ExcHandler::~ExcHandler((ExcHandler *)v452);
  v71 = v281;
  if ( !v281 )
  {
    v247 = 88;
    v431 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v72 = v431[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v432 = v72;
    v71 = *(struct Worker **)(v72 + 256);
    v298 = v71;
    if ( !v71 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v71 = *(struct Worker **)(v72 + 256);
      v298 = v71;
    }
  }
  v283 = v71;
  if ( *((_DWORD *)v71 + 139) )
    ExceptionPostCatchActions(v71);
  v433 = CSbTaskLocalStorage::GetBrokerTLS();
  *((_QWORD *)v433 + 9) = v238;
  ExcHandler::~ExcHandler((ExcHandler *)v453);
  v73 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v74 = *(struct Worker **)(v73 + 256);
  if ( !v74 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v74 = *(struct Worker **)(v73 + 256);
  }
  if ( *((_DWORD *)v74 + 139) )
    ExceptionPostCatchActions(v74);
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v454, 0, 0, 0, (int (*)(int, int, int, int, char *))SsbTaskErrorHandler, 0);
    if ( v168 )
    {
      CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v198, 0);
      SQLDATE::DateDiff((SQLDATE *)&v458, 9, (const struct SQLDATE *)&v201, &v196);
      v196 += 500;
      v183 = CommonGlobalState::m_CollectingStatistics;
      if ( CommonGlobalState::m_CollectingStatistics )
      {
        v184 = CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
          PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x1Du, 0x98u, SHIDWORD(v456), 0);
        v185 = CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
          PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x1Du, 0xB8u, SHIDWORD(v456), 0);
        v186 = CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
          PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x1Du, 0x90u, (int)v457, 0);
        v187 = CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
          PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x1Du, 0xB0u, (int)v457, 0);
        v188 = CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
          PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x1Du, 0x30u, (int)v457, 0);
        v189 = CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
          PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 0x1Du, 0xA0u, (int)v457, 0);
        for ( i = 1; ; ++i )
        {
          v171 = i;
          if ( i > 0xAu )
            break;
          v76 = *((_DWORD *)&v458 + i + 1);
          v248 = v76;
          if ( v76 > 0 )
          {
            v190 = CommonGlobalState::m_PerfCountersEnabled;
            if ( CommonGlobalState::m_PerfCountersEnabled )
            {
              v215 = v76;
              _mm_lfence();
              i = v171;
              PerfmonManager::IncrementCounterValue(
                (PerfmonManager *)qword_102ECFB00,
                0x1Du,
                CSsbBrokerXactNotify::sm_rgdwEnqueuedPriorityPerfCounters[v171 - 1],
                v215,
                0);
            }
          }
        }
      }
    }
    else
    {
      CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v198, 0);
    }
    ExcHandler::~ExcHandler((ExcHandler *)v454);
  }
  catch ( SQLError v305 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v443, (const struct SQLError *)v305);
      if ( v305[4] == 1 )
        v167 = v305[0];
      else
        v167 = LOWORD(v305[0]);
      SsbLogError(9644, 16, 15, v167, v305[3]);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v443);
    }
    catch ( ShortStackException )
    {
    }
    v2 = v221;
    v197 = v221;
  }
  v77 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v78 = *(struct Worker **)(v77 + 256);
  if ( !v78 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v78 = *(struct Worker **)(v77 + 256);
  }
  if ( *((_DWORD *)v78 + 139) )
    ExceptionPostCatchActions(v78);
  v79 = 0;
  v80 = &v191;
  v192 = &v191;
  v191 = (char *)&v191;
  if ( v175 == &v174 )
    goto LABEL_386;
  v81 = 0;
  if ( v175 )
    v81 = (CSbMsgDispatcher::CSbReceivedDialog *)(v175 - 1);
  v172 = v81;
  if ( !v81 )
    goto LABEL_386;
  do
  {
    if ( CSbMsgDispatcher::CSbReceivedDialog::ReturnToQueue(v81) )
      v79 = 1;
    v82 = (char **)*((_QWORD *)v81 + 2);
    if ( v82 == &v174 )
      v82 = 0;
    v81 = 0;
    if ( v82 )
      v81 = (CSbMsgDispatcher::CSbReceivedDialog *)(v82 - 1);
  }
  while ( v81 );
  v172 = 0;
  if ( v79 )
  {
    if ( v175 != &v174 )
    {
      v83 = 0;
      if ( v175 )
        v83 = v175 - 1;
      if ( v83 )
      {
        do
        {
          v84 = v83;
          v172 = (CSbMsgDispatcher::CSbReceivedDialog *)v83;
          v85 = (__int64 *)(v83 + 1);
          v86 = (char **)v83[2];
          if ( v86 == &v174 )
            v86 = 0;
          v83 = 0;
          if ( v86 )
            v83 = v86 - 1;
          v208 = (volatile signed __int64 *)(v84 + 14);
          v209 = 0;
          v87 = 0;
          v88 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
          if ( *((_DWORD *)v84 + 28) || _InterlockedCompareExchange64(v208, v88, 0) )
          {
            v89 = 0;
            if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
            {
              v90 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              if ( v90 && *(_QWORD *)(v90 + 272) == v90 )
                v89 = *(_QWORD *)(v90 + 256);
              if ( v89 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&v284);
                  v87 = (CSbTransportMgr *)v284.QuadPart;
                }
                else
                {
                  v87 = MEMORY[0x7FFE0008];
                }
              }
            }
            if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
              Spinlock<165,9,258>::SpinToAcquireWithExponentialBackoff(v208, v88);
            else
              Spinlock<165,9,258>::SpinToAcquireOptimistic(v208, v89, v88);
            if ( v89 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v285);
                v91 = (CSbTransportMgr *)v285.QuadPart;
              }
              else
              {
                v91 = MEMORY[0x7FFE0008];
              }
              if ( v91 < v87 )
                v92 = 0;
              else
                v92 = v91 - v87;
              *(_QWORD *)(v89 + 3192) += v92;
            }
          }
          v209 = 1;
          if ( *((_DWORD *)v172 + 25) == 2 )
          {
            v93 = (_QWORD *)v85[1];
            v94 = *v85;
            *(_QWORD *)(v94 + 8) = v93;
            *v93 = v94;
            v85[1] = 0;
            *v85 = 0;
            CSbMsgDispatcher::CSbReceivedDialog::MoveToRetiredQ(v172);
          }
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v95 = rand();
            if ( v95 == 5 * (v95 / 5) )
              Spinlock<165,9,258>::UpdateStatSnapshot();
          }
          *v208 = 0;
          v209 = 0;
        }
        while ( v83 );
        v2 = v197;
      }
    }
    v242 = (_QWORD *)((char *)v2 + 22144);
    j = 0;
    v96 = 0;
    v97 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *((_DWORD *)v2 + 5536) || _InterlockedCompareExchange64((volatile signed __int64 *)v2 + 2768, v97, 0) )
    {
      v98 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v99 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v99 && *(_QWORD *)(v99 + 272) == v99 )
          v98 = *(_QWORD *)(v99 + 256);
        if ( v98 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v286);
            v96 = (CSbTransportMgr *)v286.QuadPart;
          }
          else
          {
            v96 = MEMORY[0x7FFE0008];
          }
        }
      }
      v100 = (char *)v2 + 22144;
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v100, v97);
      else
        Spinlock<170,8,258>::SpinToAcquireOptimistic(v100, v98, v97);
      if ( v98 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v287);
          v101 = (CSbTransportMgr *)v287.QuadPart;
        }
        else
        {
          v101 = MEMORY[0x7FFE0008];
        }
        if ( v101 < v96 )
          v102 = 0;
        else
          v102 = v101 - v96;
        *(_QWORD *)(v98 + 3192) += v102;
      }
    }
    for ( j = 1; *((_DWORD *)v2 + 5538) > 0x64u; *((_QWORD *)v104 + 2) = &v191 )
    {
      v103 = (CSbMsgDispatcher *)*((_QWORD *)v2 + 2767);
      v104 = 0;
      if ( v103 != (CSbMsgDispatcher *)((char *)v2 + 22128) )
      {
        if ( v103 )
          v104 = (char *)v103 - 8;
        if ( v104 )
        {
          v105 = (_QWORD *)*((_QWORD *)v104 + 2);
          v106 = *((_QWORD *)v104 + 1);
          *(_QWORD *)(v106 + 8) = v105;
          *v105 = v106;
          *((_QWORD *)v104 + 2) = 0;
          *((_QWORD *)v104 + 1) = 0;
        }
      }
      --*((_DWORD *)v2 + 5538);
      v104[106] = 1;
      *((_QWORD *)v104 + 1) = v191;
      *((_QWORD *)v191 + 1) = v104 + 8;
      v191 = v104 + 8;
    }
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v107 = rand();
      if ( v107 == 5 * (v107 / 5) )
        Spinlock<170,8,258>::UpdateStatSnapshot();
    }
    *v242 = 0;
    j = 0;
    if ( v175 != &v174 )
    {
      v108 = 0;
      if ( v175 )
        v108 = v175 - 1;
      if ( v108 )
      {
        do
        {
          v109 = v108;
          v172 = (CSbMsgDispatcher::CSbReceivedDialog *)v108;
          v110 = (__int64 *)(v108 + 1);
          v111 = (char **)v108[2];
          if ( v111 == &v174 )
            v111 = 0;
          v108 = 0;
          if ( v111 )
            v108 = v111 - 1;
          v210 = (volatile signed __int64 *)(v109 + 14);
          v211 = 0;
          v112 = 0;
          v113 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
          if ( *((_DWORD *)v109 + 28) || _InterlockedCompareExchange64(v210, v113, 0) )
          {
            v114 = 0;
            if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
            {
              v115 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset;
              if ( v115 && *(_QWORD *)(v115 + 272) == v115 )
                v114 = *(_QWORD *)(v115 + 256);
              if ( v114 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&v288);
                  v112 = (CSbTransportMgr *)v288.QuadPart;
                }
                else
                {
                  v112 = MEMORY[0x7FFE0008];
                }
              }
            }
            if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
              Spinlock<165,9,258>::SpinToAcquireWithExponentialBackoff(v210, v113);
            else
              Spinlock<165,9,258>::SpinToAcquireOptimistic(v210, v114, v113);
            if ( v114 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v289);
                v116 = (CSbTransportMgr *)v289.QuadPart;
              }
              else
              {
                v116 = MEMORY[0x7FFE0008];
              }
              if ( v116 < v112 )
                v117 = 0;
              else
                v117 = v116 - v112;
              *(_QWORD *)(v114 + 3192) += v117;
            }
          }
          v211 = 1;
          if ( *((_DWORD *)v172 + 25) == 3 )
          {
            v118 = (_QWORD *)v110[1];
            v119 = *v110;
            *(_QWORD *)(v119 + 8) = v118;
            *v118 = v119;
            v110[1] = 0;
            *v110 = 0;
            CSbMsgDispatcher::CSbReceivedDialog::MoveToOutOfOrderQ(v172);
          }
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v120 = rand();
            if ( v120 == 5 * (v120 / 5) )
              Spinlock<165,9,258>::UpdateStatSnapshot();
          }
          *v210 = 0;
          v211 = 0;
        }
        while ( v108 );
        v2 = v197;
      }
    }
    v240 = (_QWORD *)((char *)v2 + 22176);
    k = 0;
    v121 = 0;
    v122 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *((_DWORD *)v2 + 5544) || _InterlockedCompareExchange64((volatile signed __int64 *)v2 + 2772, v122, 0) )
    {
      v123 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v124 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v124 && *(_QWORD *)(v124 + 272) == v124 )
          v123 = *(_QWORD *)(v124 + 256);
        if ( v123 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v290);
            v121 = (CSbTransportMgr *)v290.QuadPart;
          }
          else
          {
            v121 = MEMORY[0x7FFE0008];
          }
        }
      }
      v125 = (char *)v2 + 22176;
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v125, v122);
      else
        Spinlock<170,8,258>::SpinToAcquireOptimistic(v125, v123, v122);
      if ( v123 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v291);
          v126 = (CSbTransportMgr *)v291.QuadPart;
        }
        else
        {
          v126 = MEMORY[0x7FFE0008];
        }
        if ( v126 < v121 )
          v127 = 0;
        else
          v127 = v126 - v121;
        *(_QWORD *)(v123 + 3192) += v127;
      }
    }
    for ( k = 1; *((_DWORD *)v2 + 5546) > 0x12Cu; *((_QWORD *)v129 + 2) = &v191 )
    {
      v128 = (CSbMsgDispatcher *)*((_QWORD *)v2 + 2771);
      v129 = 0;
      if ( v128 != (CSbMsgDispatcher *)((char *)v2 + 22160) )
      {
        if ( v128 )
          v129 = (char *)v128 - 8;
        if ( v129 )
        {
          v130 = (_QWORD *)*((_QWORD *)v129 + 2);
          v131 = *((_QWORD *)v129 + 1);
          *(_QWORD *)(v131 + 8) = v130;
          *v130 = v131;
          *((_QWORD *)v129 + 2) = 0;
          *((_QWORD *)v129 + 1) = 0;
        }
      }
      *((_DWORD *)v2 + 5546) -= *((_DWORD *)v129 + 31);
      v129[106] = 1;
      *((_QWORD *)v129 + 1) = v191;
      *((_QWORD *)v191 + 1) = v129 + 8;
      v191 = v129 + 8;
    }
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v132 = rand();
      if ( v132 == 5 * (v132 / 5) )
        Spinlock<170,8,258>::UpdateStatSnapshot();
    }
    *v240 = 0;
    k = 0;
  }
  while ( 1 )
  {
    v80 = v192;
LABEL_386:
    if ( v80 == &v191 )
      break;
    v133 = 0;
    if ( v80 )
      v133 = (CSbMsgDispatcher::CSbReceivedDialog *)(v80 - 1);
    if ( !v133 )
      break;
    v134 = (_QWORD *)*((_QWORD *)v133 + 2);
    v135 = *((_QWORD *)v133 + 1);
    *(_QWORD *)(v135 + 8) = v134;
    *v134 = v135;
    *((_QWORD *)v133 + 2) = 0;
    *((_QWORD *)v133 + 1) = 0;
    v172 = v133;
    CSbMsgDispatcher::CSbReceivedDialog::Unhash(v133);
    CSbMsgDispatcher::CSbReceivedDialog::Release(v133);
  }
  v136 = v175;
  if ( v175 != &v174 )
  {
    while ( v136 != &v174 )
    {
      v137 = 0;
      if ( v136 )
        v137 = (volatile signed __int64 *)(v136 - 1);
      v172 = (CSbMsgDispatcher::CSbReceivedDialog *)v137;
      if ( !v137 )
        goto LABEL_422;
      v138 = (_QWORD *)*((_QWORD *)v137 + 2);
      v139 = *((_QWORD *)v137 + 1);
      *(_QWORD *)(v139 + 8) = v138;
      *v138 = v139;
      *((_QWORD *)v137 + 2) = 0;
      *((_QWORD *)v137 + 1) = 0;
      v212 = v137 + 14;
      v213 = 0;
      v140 = 0;
      v141 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *((_DWORD *)v137 + 28) || _InterlockedCompareExchange64(v212, v141, 0) )
      {
        v142 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v143 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v143 && *(_QWORD *)(v143 + 272) == v143 )
            v142 = *(_QWORD *)(v143 + 256);
          if ( v142 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v292);
              v140 = (CSbTransportMgr *)v292.QuadPart;
            }
            else
            {
              v140 = MEMORY[0x7FFE0008];
            }
          }
        }
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<165,9,258>::SpinToAcquireWithExponentialBackoff(v212, v141);
        else
          Spinlock<165,9,258>::SpinToAcquireOptimistic(v212, v142, v141);
        if ( v142 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v293);
            v144 = (CSbTransportMgr *)v293.QuadPart;
          }
          else
          {
            v144 = MEMORY[0x7FFE0008];
          }
          if ( v144 < v140 )
            v145 = 0;
          else
            v145 = v144 - v140;
          *(_QWORD *)(v142 + 3192) += v145;
        }
      }
      v213 = 1;
      CSbMsgDispatcher::CSbReceivedDialog::MoveToPendingQ((CSbMsgDispatcher::CSbReceivedDialog *)v137);
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v146 = rand();
        if ( v146 == 5 * (v146 / 5) )
          Spinlock<165,9,258>::UpdateStatSnapshot();
      }
      *v212 = 0;
      v213 = 0;
      v136 = v175;
    }
    v172 = 0;
  }
LABEL_422:
  v147 = 0;
  v148 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( *(_DWORD *)v169 || _InterlockedCompareExchange64(v169, v148, 0) )
  {
    v149 = 0;
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
    {
      v150 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( v150 && *(_QWORD *)(v150 + 272) == v150 )
        v149 = *(_QWORD *)(v150 + 256);
      if ( v149 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v294);
          v147 = (CSbTransportMgr *)v294.QuadPart;
        }
        else
        {
          v147 = MEMORY[0x7FFE0008];
        }
      }
    }
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v169, v148);
    else
      Spinlock<170,8,258>::SpinToAcquireOptimistic(v169, v149, v148);
    if ( v149 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v295);
        v151 = (CSbTransportMgr *)v295.QuadPart;
      }
      else
      {
        v151 = MEMORY[0x7FFE0008];
      }
      if ( v151 < v147 )
        v152 = 0;
      else
        v152 = v151 - v147;
      *(_QWORD *)(v149 + 3192) += v152;
    }
  }
  v170 = 1;
  if ( *((CSbMsgDispatcher **)v2 + 2763) == (CSbMsgDispatcher *)((char *)v2 + 22096) )
  {
    *((_BYTE *)a2 + 648) = 0;
    v153 = v193;
    if ( (_QWORD)v193 )
    {
      *(_QWORD *)(*(_QWORD *)(v193 + 24) + 8LL) = v194;
      *(_QWORD *)(v153 + 24) = *((_QWORD *)&v193 + 1);
      v193 = 0;
      v194 = 0;
    }
    v306 = &CConnectionOutput::`vftable';
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v154 = rand();
      if ( v154 == 5 * (v154 / 5) )
        Spinlock<170,8,258>::UpdateStatSnapshot();
    }
    *v169 = 0;
    v169 = 0;
    v170 = 0;
    if ( v203 )
    {
      CSbTaskLocalStorage::GetBrokerTLS();
      v155 = (_QWORD *)*((_QWORD *)&v202 + 1);
      v156 = v202;
      *(_QWORD *)(v202 + 8) = *((_QWORD *)&v202 + 1);
      *v155 = v156;
      v202 = 0u;
      SOS_RWLock::ReleaseLock(v204, v203);
      v203 = 0;
    }
    operator delete(v222, 1u);
    if ( (_DWORD)v198 )
      CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v198, 0);
    return 0;
  }
  else
  {
    if ( *((_DWORD *)v2 + 5530) > 1u )
    {
      v157 = 0;
      if ( *((int *)v2 + 270) > 0 )
      {
        v158 = (char *)v2 + 1736;
        while ( *v158 )
        {
          ++v157;
          v158 += 656;
          if ( v157 >= *((_DWORD *)v2 + 270) )
            goto LABEL_466;
        }
        v159 = (char *)v2 + 656 * v157;
        v159[1736] = 1;
        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v160 = rand();
          if ( v160 == 5 * (v160 / 5) )
            Spinlock<170,8,258>::UpdateStatSnapshot();
        }
        *v169 = 0;
        v170 = 0;
        v161 = v159 + 1088;
        _InterlockedIncrement((volatile signed __int32 *)v161 + 12);
        v162 = (struct IUnknown *)(v161 + 640);
        if ( !v161 )
          v162 = 0;
        CSbTaskManager::SubmitIdempotentTask(*((CSbTaskManager **)v161 + 71), (struct CSbIdempotentTask *)v161, v162, 1);
        _InterlockedDecrement((volatile signed __int32 *)v161 + 12);
      }
    }
LABEL_466:
    v163 = v193;
    if ( (_QWORD)v193 )
    {
      *(_QWORD *)(*(_QWORD *)(v193 + 24) + 8LL) = v194;
      *(_QWORD *)(v163 + 24) = *((_QWORD *)&v193 + 1);
      v193 = 0;
      v194 = 0;
    }
    v306 = &CConnectionOutput::`vftable';
    if ( v170 )
    {
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v164 = rand();
        if ( v164 == 5 * (v164 / 5) )
          Spinlock<170,8,258>::UpdateStatSnapshot();
      }
      *v169 = 0;
      v169 = 0;
      v170 = 0;
    }
    if ( v203 )
    {
      CSbTaskLocalStorage::GetBrokerTLS();
      v165 = (_QWORD *)*((_QWORD *)&v202 + 1);
      v166 = v202;
      *(_QWORD *)(v202 + 8) = *((_QWORD *)&v202 + 1);
      *v165 = v166;
      v202 = 0u;
      SOS_RWLock::ReleaseLock(v204, v203);
      v203 = 0;
    }
    operator delete(v222, 1u);
    if ( (_DWORD)v198 )
      CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v198, 0);
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
