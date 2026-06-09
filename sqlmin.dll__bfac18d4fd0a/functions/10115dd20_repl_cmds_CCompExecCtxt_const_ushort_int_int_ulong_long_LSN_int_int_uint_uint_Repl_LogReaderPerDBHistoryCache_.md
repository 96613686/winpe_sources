# repl_cmds(CCompExecCtxt const &,ushort,int,int,ulong,long,LSN *,int,int,uint,uint,Repl_LogReaderPerDBHistoryCache *,wchar_t const *,int,int &)

- ea: `0x10115dd20`
- end: `0x10115f9e0`
- name: `?repl_cmds@@YAHAEBVCCompExecCtxt@@GHHKJPEAVLSN@@HHIIPEAVRepl_LogReaderPerDBHistoryCache@@PEB_WHAEAH@Z`
- size: `7360`
- prototype: `int(const struct CCompExecCtxt *, unsigned __int16, int, int, unsigned int, int, struct LSN *, int, int, unsigned int, unsigned int, struct Repl_LogReaderPerDBHistoryCache *, const wchar_t *, int, int *)`
- caller_count: `1`
- callee_count: `41`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x101159bf0`

## callees

- `0x100401380`
- `0x1004013f0`
- `0x100401490`
- `0x100462990`
- `0x100472800`
- `0x1004bff60`
- `0x1004d88b0`
- `0x100553eb0`
- `0x1005f1f00`
- `0x10072d4d0`
- `0x10072d690`
- `0x1007cbc90`
- `0x101140500`
- `0x101140c20`
- `0x1011434b0`
- `0x101152f80`
- `0x101157540`
- `0x1011579d0`
- `0x101157d00`
- `0x1011586f0`
- `0x10115a5b0`
- `0x10115b360`
- `0x10115ba20`
- `0x10115dd20`
- `0x10115f9f0`
- `0x101160850`
- `0x10116b2a0`
- `0x101172e00`
- `0x101173210`
- `0x101173460`
- `0x1011799a0`
- `0x10117a4e0`
- `0x10117a7a0`
- `0x10117d790`
- `0x10117da60`
- `0x101180630`
- `0x1011bccc0`
- `0x1011d8ca0`
- `0x1017371e0`
- `0x1023adf80`
- `0x1023aec40`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x10115de23`
- `KERNEL32!GetTickCount` at `0x10115e3ec`
- `KERNEL32!GetTickCount` at `0x10115e4e8`
- `KERNEL32!GetTickCount` at `0x10115e6a2`
- `KERNEL32!GetTickCount` at `0x10115f58c`
- `KERNEL32!GetTickCount` at `0x10115f5d7`
- `KERNEL32!GetTickCount` at `0x10115de23`
- `KERNEL32!GetTickCount` at `0x10115e3ec`
- `KERNEL32!GetTickCount` at `0x10115e4e8`
- `KERNEL32!GetTickCount` at `0x10115e6a2`
- `KERNEL32!GetTickCount` at `0x10115f58c`
- `KERNEL32!GetTickCount` at `0x10115f5d7`
- `KERNEL32!QueryPerformanceCounter` at `0x10115f03e`
- `KERNEL32!QueryPerformanceCounter` at `0x10115f0da`
- `KERNEL32!QueryPerformanceCounter` at `0x10115f332`
- `KERNEL32!QueryPerformanceCounter` at `0x10115f3ce`
- `KERNEL32!QueryPerformanceCounter` at `0x10115f844`
- `KERNEL32!QueryPerformanceCounter` at `0x10115f89d`
- `KERNEL32!QueryPerformanceCounter` at `0x10115f03e`
- `KERNEL32!QueryPerformanceCounter` at `0x10115f0da`
- `KERNEL32!QueryPerformanceCounter` at `0x10115f332`
- `KERNEL32!QueryPerformanceCounter` at `0x10115f3ce`
- `KERNEL32!QueryPerformanceCounter` at `0x10115f844`
- `KERNEL32!QueryPerformanceCounter` at `0x10115f89d`
- `sqlTsEs!?UICodePageFromCID@@YAIK@Z` at `0x10115dfcc`
- `sqlTsEs!?UICodePageFromCID@@YAIK@Z` at `0x10115dfcc`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10115decf`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10115f1a3`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10115f475`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10115f8fb`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10115efa1`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10115f295`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10115f7e2`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10115f07e`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10115f372`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10115f85c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10115f022`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10115f0be`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10115f316`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10115f3b2`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10115f830`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10115f889`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10115e102`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10115e3af`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10115e3af`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10115ea72`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10115ed99`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10115f77c`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10115ea72`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10115ed99`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10115f77c`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x10115e07b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10115e1f1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10115e237`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10115e31d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10115e566`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10115ebfd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10115f979`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10115e1f1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10115e237`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10115e31d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10115e566`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10115ebfd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10115f979`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10115e1cd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10115e2f9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10115f79b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10115e1cd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10115e2f9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10115f79b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10115ee13`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10115f6c9`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10115ee13`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10115f6c9`
- `sqldk!SystemThread_TlsIndex` at `0x10115ddd6`
- `sqldk!SystemThread_TlsIndex` at `0x10115de81`
- `sqldk!SystemThread_TlsIndex` at `0x10115dfa4`
- `sqldk!SystemThread_TlsIndex` at `0x10115e16c`
- `sqldk!SystemThread_TlsIndex` at `0x10115e298`
- `sqldk!SystemThread_TlsIndex` at `0x10115e6e9`
- `sqldk!SystemThread_TlsIndex` at `0x10115ea22`
- `sqldk!SystemThread_TlsIndex` at `0x10115eb18`
- `sqldk!SystemThread_TlsIndex` at `0x10115eb69`
- `sqldk!SystemThread_TlsIndex` at `0x10115ed49`
- `sqldk!SystemThread_TlsIndex` at `0x10115edcc`
- `sqldk!SystemThread_TlsIndex` at `0x10115efce`
- `sqldk!SystemThread_TlsIndex` at `0x10115f2c2`
- `sqldk!SystemThread_TlsIndex` at `0x10115f681`
- `sqldk!SystemThread_TlsIndex` at `0x10115f744`
- `sqldk!SystemThread_TlsIndex` at `0x10115f802`
- `sqldk!SystemThread_TlsOffset` at `0x10115dddf`
- `sqldk!SystemThread_TlsOffset` at `0x10115de8a`
- `sqldk!SystemThread_TlsOffset` at `0x10115dfad`
- `sqldk!SystemThread_TlsOffset` at `0x10115e175`
- `sqldk!SystemThread_TlsOffset` at `0x10115e2a1`
- `sqldk!SystemThread_TlsOffset` at `0x10115e6f2`
- `sqldk!SystemThread_TlsOffset` at `0x10115ea2b`
- `sqldk!SystemThread_TlsOffset` at `0x10115eb21`
- `sqldk!SystemThread_TlsOffset` at `0x10115eb72`
- `sqldk!SystemThread_TlsOffset` at `0x10115ed52`
- `sqldk!SystemThread_TlsOffset` at `0x10115edd5`
- `sqldk!SystemThread_TlsOffset` at `0x10115efd7`
- `sqldk!SystemThread_TlsOffset` at `0x10115f2cb`
- `sqldk!SystemThread_TlsOffset` at `0x10115f68a`
- `sqldk!SystemThread_TlsOffset` at `0x10115f74d`
- `sqldk!SystemThread_TlsOffset` at `0x10115f80b`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10115f610`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10115f610`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10115ddfa`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10115dea5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10115ea54`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10115ed7b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10115f766`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10115ddfa`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10115dea5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10115ea54`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10115ed7b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10115f766`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10115f1b8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10115f48a`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10115f907`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10115f1b8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10115f48a`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10115f907`
- `sqllang!?SetColumn@CColMetaData@@QEAAXGAEBVCTypeInfo@@PEB_WEHUColMDStatus@@1GHH@Z` at `0x10115e061`
- `sqllang!?SetColumn@CColMetaData@@QEAAXGAEBVCTypeInfo@@PEB_WEHUColMDStatus@@1GHH@Z` at `0x10115e061`
- `sqllang!?GetColMDStatUnset@@YA?AUColMDStatus@@XZ` at `0x10115e010`
- `sqllang!?GetColMDStatUnset@@YA?AUColMDStatus@@XZ` at `0x10115e010`
- `sqllang!??1CColMetaData@@UEAA@XZ` at `0x10115e0f2`
- `sqllang!??1CColMetaData@@UEAA@XZ` at `0x10115f9b5`
- `sqllang!??1CColMetaData@@UEAA@XZ` at `0x10115e0f2`
- `sqllang!??1CColMetaData@@UEAA@XZ` at `0x10115f9b5`
- `sqllang!?UnstructuredEndResultSet@CConnectionOutput@@QEAAXHPEA_KPEB_KH@Z` at `0x10115f998`
- `sqllang!?UnstructuredEndResultSet@CConnectionOutput@@QEAAXHPEA_KPEB_KH@Z` at `0x10115f998`
- `sqllang!?UnstructuredSendMeta@CConnectionOutput@@QEAAXPEBVCColMetaData@@FHPEBVCAuxMetaData@@HHH@Z` at `0x10115e372`
- `sqllang!?UnstructuredSendMeta@CConnectionOutput@@QEAAXPEBVCColMetaData@@FHPEBVCAuxMetaData@@HHH@Z` at `0x10115e372`

## string_xrefs

- `0x10115deed`: `CdcLogReaderTelemetryIntervalInMins`
- `0x10115e55c`: `pSynapseLinkDB != nullptr`
- `0x10115ebf1`: `rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall repl_cmds(
        const struct CCompExecCtxt *a1,
        unsigned __int16 a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        struct LSN *a7,
        int a8,
        int a9,
        unsigned int a10,
        unsigned int a11,
        struct Repl_LogReaderPerDBHistoryCache *a12,
        wchar_t *a13,
        int a14,
        int *a15)
{
  unsigned int v15; // r13d
  unsigned int v16; // r12d
  __int64 v18; // rbx
  __int64 v19; // rax
  struct IMemObj *v20; // rsi
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // r14
  _QWORD *ThreadLocalStoragePointer; // rdx
  unsigned int *DefaultCollationData; // rax
  unsigned int v28; // eax
  unsigned __int16 v29; // si
  struct REPL_RESULTSET_TITLE near **v30; // rbx
  __int16 ColMDStatUnset; // ax
  struct REPL_RESULTSET_TITLE near *v32; // r9
  __int64 v33; // rcx
  unsigned __int16 v34; // cx
  __int64 v36; // r15
  struct REPL_DATABASE_MEM *repl_mem; // rax
  __int64 v38; // rbx
  struct CReplTrace *v39; // rax
  struct ReplTranHash *v40; // rsi
  int v41; // edx
  int v42; // r12d
  struct CReplTrace *v43; // rax
  DWORD v44; // ebx
  unsigned int v45; // eax
  struct SynapseLinkDatabase *SynapseLinkDB; // rbx
  __int64 v47; // rax
  int appended; // ebx
  int v49; // ecx
  int v50; // ebx
  unsigned int v51; // r15d
  unsigned __int16 v52; // r12
  SynapseLinkDatabase *v53; // rbx
  int trans_cmds; // eax
  __int64 v55; // rbx
  struct Worker *v56; // rcx
  char v57; // si
  __int64 v58; // rax
  __int64 v59; // rdx
  __int64 v60; // rbx
  struct Worker *v61; // rcx
  __int64 v62; // rax
  struct CSessionTraceFlags *v63; // rcx
  bool v64; // zf
  __int64 v65; // rbx
  __int64 v66; // rbx
  DirtyPageMgr *v67; // rax
  DirtyPageMgr *v68; // rax
  signed __int64 v69; // rax
  int v70; // eax
  __int64 v71; // rcx
  __int64 v72; // rbx
  __int64 v73; // rbx
  DirtyPageMgr *QuadPart; // rax
  DirtyPageMgr *v75; // rax
  signed __int64 v76; // rax
  __int16 v77; // bx
  int v78; // eax
  __int64 v79; // rcx
  DWORD v80; // r15d
  __int64 v81; // rax
  struct CSessionTraceFlags *v82; // rcx
  struct CCompExecCtxt *v83; // r13
  __int64 v84; // rbx
  struct Worker *v85; // rcx
  unsigned int v86; // ebx
  volatile signed __int64 *v87; // r14
  DirtyPageMgr *v88; // rbx
  signed __int64 v89; // r15
  __int64 v90; // rsi
  __int64 v91; // r8
  DirtyPageMgr *v92; // rax
  signed __int64 v93; // rcx
  int v94; // r8d
  struct REPL_DATABASE_TIMER *repl_timer; // rax
  int v96; // [rsp+20h] [rbp-628h]
  unsigned int v97; // [rsp+30h] [rbp-618h]
  int v98; // [rsp+40h] [rbp-608h]
  int v99; // [rsp+B0h] [rbp-598h]
  unsigned __int16 v100; // [rsp+B4h] [rbp-594h]
  struct ReplTranHash *v102; // [rsp+C0h] [rbp-588h]
  __int64 v103; // [rsp+C8h] [rbp-580h]
  int v104; // [rsp+E0h] [rbp-568h] BYREF
  DWORD v105; // [rsp+E4h] [rbp-564h]
  char v106; // [rsp+E8h] [rbp-560h]
  char v107; // [rsp+EAh] [rbp-55Eh]
  int v108; // [rsp+ECh] [rbp-55Ch] BYREF
  unsigned int v109; // [rsp+F0h] [rbp-558h] BYREF
  unsigned int v110; // [rsp+F4h] [rbp-554h] BYREF
  int v111; // [rsp+F8h] [rbp-550h] BYREF
  int v112; // [rsp+FCh] [rbp-54Ch] BYREF
  DWORD v113; // [rsp+100h] [rbp-548h]
  struct CReplTrace *v114; // [rsp+108h] [rbp-540h]
  struct CCompExecCtxt *v115; // [rsp+110h] [rbp-538h]
  int v116; // [rsp+118h] [rbp-530h] BYREF
  int v117; // [rsp+11Ch] [rbp-52Ch] BYREF
  int v118; // [rsp+120h] [rbp-528h]
  __int128 v119; // [rsp+128h] [rbp-520h]
  volatile signed __int64 *v120; // [rsp+138h] [rbp-510h]
  volatile signed __int64 *v121; // [rsp+140h] [rbp-508h]
  __int64 v122; // [rsp+148h] [rbp-500h]
  __int64 v123; // [rsp+150h] [rbp-4F8h]
  struct CCompExecCtxt *v124; // [rsp+158h] [rbp-4F0h]
  signed __int64 UniqueThread_low; // [rsp+160h] [rbp-4E8h]
  struct Worker *v126; // [rsp+168h] [rbp-4E0h]
  BOOL v127; // [rsp+170h] [rbp-4D8h]
  DWORD TickCount; // [rsp+174h] [rbp-4D4h]
  int v129; // [rsp+178h] [rbp-4D0h]
  DWORD v130; // [rsp+17Ch] [rbp-4CCh]
  __int64 v131; // [rsp+180h] [rbp-4C8h]
  SynapseLinkDatabase *v132; // [rsp+188h] [rbp-4C0h]
  signed __int64 v133; // [rsp+190h] [rbp-4B8h]
  __int64 v134; // [rsp+198h] [rbp-4B0h]
  void **v135; // [rsp+1A0h] [rbp-4A8h] BYREF
  __int64 v136; // [rsp+1A8h] [rbp-4A0h]
  int v137; // [rsp+1B0h] [rbp-498h]
  __int64 v138; // [rsp+1B8h] [rbp-490h]
  char v139; // [rsp+1C0h] [rbp-488h]
  unsigned int v140; // [rsp+1C8h] [rbp-480h]
  __int64 v141; // [rsp+1D0h] [rbp-478h]
  __int16 v142; // [rsp+1D8h] [rbp-470h]
  DirtyPageMgr *v143; // [rsp+1E0h] [rbp-468h]
  __int64 v144; // [rsp+1E8h] [rbp-460h]
  __int64 v145; // [rsp+1F0h] [rbp-458h]
  SynapseLinkDatabase *v146; // [rsp+1F8h] [rbp-450h]
  struct CReplTrace *v147; // [rsp+200h] [rbp-448h]
  DirtyPageMgr *v148; // [rsp+210h] [rbp-438h]
  __int64 v149; // [rsp+218h] [rbp-430h] BYREF
  __int16 v150; // [rsp+220h] [rbp-428h]
  __int16 v151; // [rsp+222h] [rbp-426h]
  __int64 v152; // [rsp+228h] [rbp-420h] BYREF
  __int16 v153; // [rsp+230h] [rbp-418h]
  __int64 v154; // [rsp+238h] [rbp-410h] BYREF
  __int16 v155; // [rsp+240h] [rbp-408h]
  int v156; // [rsp+248h] [rbp-400h]
  int v157; // [rsp+24Ch] [rbp-3FCh]
  __int16 v158; // [rsp+250h] [rbp-3F8h]
  __int64 v159; // [rsp+258h] [rbp-3F0h] BYREF
  __int16 v160; // [rsp+260h] [rbp-3E8h]
  _QWORD v161[2]; // [rsp+270h] [rbp-3D8h] BYREF
  __int128 v162; // [rsp+280h] [rbp-3C8h]
  __int64 v163; // [rsp+290h] [rbp-3B8h]
  __int16 v164; // [rsp+298h] [rbp-3B0h]
  __int64 v165; // [rsp+29Ch] [rbp-3ACh]
  __int64 v166; // [rsp+2A8h] [rbp-3A0h]
  int v167; // [rsp+2B0h] [rbp-398h]
  struct REPL_DATABASE_MEM *v168; // [rsp+2C8h] [rbp-380h]
  struct Repl_LogReaderPerDBHistoryCache *v169; // [rsp+2D0h] [rbp-378h]
  int *v170; // [rsp+2D8h] [rbp-370h]
  wchar_t *v171; // [rsp+2E0h] [rbp-368h]
  struct CReplTrace *v172; // [rsp+2E8h] [rbp-360h]
  struct Worker *v173; // [rsp+2F0h] [rbp-358h]
  LARGE_INTEGER PerformanceCount; // [rsp+2F8h] [rbp-350h] BYREF
  DirtyPageMgr *v175; // [rsp+300h] [rbp-348h]
  DirtyPageMgr *v176; // [rsp+308h] [rbp-340h]
  LARGE_INTEGER v177; // [rsp+310h] [rbp-338h] BYREF
  DirtyPageMgr *v178; // [rsp+318h] [rbp-330h]
  DirtyPageMgr *v179; // [rsp+320h] [rbp-328h]
  LARGE_INTEGER v180; // [rsp+328h] [rbp-320h] BYREF
  DirtyPageMgr *v181; // [rsp+330h] [rbp-318h]
  DirtyPageMgr *v182; // [rsp+338h] [rbp-310h]
  LARGE_INTEGER v183; // [rsp+340h] [rbp-308h] BYREF
  DirtyPageMgr *v184; // [rsp+348h] [rbp-300h]
  DirtyPageMgr *v185; // [rsp+350h] [rbp-2F8h]
  LARGE_INTEGER v186; // [rsp+358h] [rbp-2F0h] BYREF
  LARGE_INTEGER v187; // [rsp+360h] [rbp-2E8h] BYREF
  unsigned __int64 v188; // [rsp+368h] [rbp-2E0h] BYREF
  int v189; // [rsp+370h] [rbp-2D8h]
  BOOL v190; // [rsp+378h] [rbp-2D0h]
  int v191; // [rsp+380h] [rbp-2C8h]
  BOOL v192; // [rsp+384h] [rbp-2C4h]
  int v193; // [rsp+388h] [rbp-2C0h]
  int v194; // [rsp+38Ch] [rbp-2BCh]
  BOOL v195; // [rsp+390h] [rbp-2B8h]
  int v196; // [rsp+394h] [rbp-2B4h]
  int v197; // [rsp+398h] [rbp-2B0h]
  __int64 v198; // [rsp+3A0h] [rbp-2A8h]
  __int16 v199; // [rsp+3A8h] [rbp-2A0h]
  _BYTE v200[24]; // [rsp+3C8h] [rbp-280h] BYREF
  _QWORD *v201; // [rsp+3E0h] [rbp-268h]
  __int64 *v202; // [rsp+3E8h] [rbp-260h]
  __int64 v203; // [rsp+3F0h] [rbp-258h]
  __int64 v204; // [rsp+3F8h] [rbp-250h]
  _QWORD *v205; // [rsp+400h] [rbp-248h]
  __int64 v206; // [rsp+408h] [rbp-240h]
  _QWORD *v207; // [rsp+410h] [rbp-238h]
  struct Worker **v208; // [rsp+418h] [rbp-230h]
  struct Worker *v209; // [rsp+420h] [rbp-228h]
  _QWORD *v210; // [rsp+428h] [rbp-220h]
  struct Worker **v211; // [rsp+430h] [rbp-218h]
  struct Worker *v212; // [rsp+438h] [rbp-210h]
  _QWORD *v213; // [rsp+440h] [rbp-208h]
  __int64 v214; // [rsp+448h] [rbp-200h]
  _QWORD *v215; // [rsp+450h] [rbp-1F8h]
  __int64 *v216; // [rsp+458h] [rbp-1F0h]
  __int64 v217; // [rsp+460h] [rbp-1E8h]
  struct CSessionTraceFlags *v218; // [rsp+468h] [rbp-1E0h]
  signed __int64 v219; // [rsp+470h] [rbp-1D8h]
  _QWORD *v220; // [rsp+478h] [rbp-1D0h]
  __int64 v221; // [rsp+480h] [rbp-1C8h]
  char *v222; // [rsp+488h] [rbp-1C0h]
  __int64 v223; // [rsp+490h] [rbp-1B8h]
  __int64 v224; // [rsp+498h] [rbp-1B0h]
  signed __int64 v225; // [rsp+4A0h] [rbp-1A8h]
  _QWORD *v226; // [rsp+4A8h] [rbp-1A0h]
  __int64 v227; // [rsp+4B0h] [rbp-198h]
  char *v228; // [rsp+4B8h] [rbp-190h]
  __int64 v229; // [rsp+4C0h] [rbp-188h]
  __int64 v230; // [rsp+4C8h] [rbp-180h]
  _QWORD *v231; // [rsp+4D0h] [rbp-178h]
  __int64 *v232; // [rsp+4D8h] [rbp-170h]
  __int64 v233; // [rsp+4E0h] [rbp-168h]
  struct CSessionTraceFlags *v234; // [rsp+4E8h] [rbp-160h]
  __int64 v235; // [rsp+520h] [rbp-128h]
  __int64 v236; // [rsp+528h] [rbp-120h]
  _QWORD *v237; // [rsp+530h] [rbp-118h]
  struct CReplTrace **v238; // [rsp+538h] [rbp-110h]
  struct CReplTrace *v239; // [rsp+540h] [rbp-108h]
  __int64 v240; // [rsp+548h] [rbp-100h]
  struct IMemObj *v241; // [rsp+550h] [rbp-F8h]
  _QWORD *v242; // [rsp+558h] [rbp-F0h]
  _BYTE v243[16]; // [rsp+560h] [rbp-E8h] BYREF
  _QWORD v244[6]; // [rsp+570h] [rbp-D8h] BYREF
  struct CReplTrace **v245; // [rsp+5A0h] [rbp-A8h]
  struct CReplTrace *v246; // [rsp+5A8h] [rbp-A0h]
  _BYTE v247[24]; // [rsp+5B8h] [rbp-90h] BYREF
  _BYTE v248[40]; // [rsp+5D0h] [rbp-78h] BYREF
  __int64 v249; // [rsp+5F8h] [rbp-50h] BYREF
  __int16 v250; // [rsp+600h] [rbp-48h]

  v223 = -2;
  v129 = a4;
  v15 = a3;
  v16 = a2;
  v100 = a2;
  v115 = a1;
  v124 = a1;
  v140 = a3;
  v169 = a12;
  v171 = a13;
  v170 = a15;
  v18 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v19 = *(_QWORD *)(v18 + 256);
  if ( !v19 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v19 = *(_QWORD *)(v18 + 256);
  }
  v20 = *(struct IMemObj **)(v19 + 1000);
  v147 = 0;
  TickCount = GetTickCount();
  v112 = 0;
  v108 = 0;
  v105 = 0;
  v127 = CDbAndSetOpts::LUserOpt1Get(**((CDbAndSetOpts ***)a1 + 8), 4u) != 0;
  v104 = 0;
  v111 = 0;
  v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v22 = *(_QWORD *)(v21 + 256);
  if ( !v22 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v22 = *(_QWORD *)(v21 + 256);
  }
  v131 = *(_QWORD *)(v22 + 600);
  CdcTelemetryIntervalInMilliSec = 0;
  if ( dword_103172528 )
  {
    (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, _BYTE, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
      s_pServerConf,
      L"Replication",
      L"CdcLogReaderTelemetryIntervalInMins",
      &CdcTelemetryIntervalInMin,
      0,
      0);
    CdcTelemetryIntervalInMilliSec = 60000 * CdcTelemetryIntervalInMin;
  }
  if ( a12 && (v23 = *((_QWORD *)a12 + 6)) != 0 && (v24 = *((__int16 *)a12 + 29), (_WORD)v24 != 0xFFFF) )
    v25 = v23 + 272 * v24;
  else
    v25 = 0;
  v122 = v25;
  v161[0] = &CColMetaData::`vftable';
  v161[1] = 0;
  v162 = 0;
  v163 = 0;
  v164 = 0;
  v165 = 0;
  v166 = 0;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  DefaultCollationData = (unsigned int *)CDbAndSetOptsImplImport::GetDefaultCollationData(
                                           (CDbAndSetOptsImplImport *)*(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset) + 80LL)
                                                                                          + 8LL),
                                           (unsigned __int16)ThreadLocalStoragePointer);
  v28 = UICodePageFromCID(*DefaultCollationData);
  CColMetaData::Init((CColMetaData *)v161, v20, 0xEu, *(_DWORD *)(**((_QWORD **)a1 + 8) + 44LL), v28);
  Raise_repl_logscan_sessionXEvent(v25, 0, v15);
  v29 = 0;
  v30 = &replcmdstitle;
  do
  {
    ColMDStatUnset = GetColMDStatUnset();
    v32 = v30[1];
    v33 = -1;
    do
      ++v33;
    while ( *((_WORD *)v32 + v33) );
    LOWORD(v98) = 0;
    LOWORD(v97) = ColMDStatUnset;
    LOBYTE(v96) = v33;
    CColMetaData::SetColumn(v161, v29++, *v30, v32, v96, 1, v97, 0, v98, 1, 0);
    v30 += 2;
  }
  while ( v29 < 0xEu );
  ExcHandler::ExcHandler((ExcHandler *)v248, 0, 0, 0, hdl_prntbackout, 0);
  if ( !dword_103172528 && (a6 & 0x800) == 0 && !(unsigned int)GetPeerToPeerDBInfo(v34, &v104, &v111) )
  {
    ex_replprint(18847, 16, 1);
    ExcHandler::~ExcHandler((ExcHandler *)v248);
    CColMetaData::~CColMetaData((CColMetaData *)v161);
    return 0;
  }
  v36 = g_dbtableFactory[4](v16);
  v103 = v36;
  repl_mem = get_repl_mem(v16);
  v168 = repl_mem;
  v38 = v131;
  if ( !repl_mem )
  {
    v236 = v131 + 188;
    if ( (*(_DWORD *)(v131 + 188) & 4) != 0 )
    {
      if ( (unsigned int)IsExecutionAbortedDueToAttention()
        || (v237 = NtCurrentTeb()->ThreadLocalStoragePointer,
            v238 = (struct CReplTrace **)(v237[SystemThread_TlsIndex] + SystemThread_TlsOffset),
            v39 = *v238,
            v239 = v39,
            (v114 = v39) != 0)
        && (v114 = v39, *(_BYTE *)(*((_QWORD *)v39 + 7) + 8LL))
        && !(unsigned int)SOS_Task::IsDelayAbortOn() )
      {
        ex_raise(36, 21, 16, 6);
      }
    }
    utassert_fail(1u, "db_mem", "replicat.cpp", 2314, 0);
    repl_mem = v168;
  }
  v40 = (struct ReplTranHash *)*((_QWORD *)repl_mem + 127);
  v102 = v40;
  if ( !v40 )
    utassert_fail(1u, "phash_table", "replicat.cpp", 2317, 0);
  v41 = 100000;
  if ( (int)v15 < 100000 )
    v41 = v15;
  v42 = ReplTranHash::ReInit(v40, 2 * v41);
  if ( !v42 )
  {
    v240 = v38 + 188;
    if ( (*(_DWORD *)(v38 + 188) & 4) != 0 )
    {
      if ( (unsigned int)IsExecutionAbortedDueToAttention()
        || (v242 = NtCurrentTeb()->ThreadLocalStoragePointer,
            v245 = (struct CReplTrace **)(v242[SystemThread_TlsIndex] + SystemThread_TlsOffset),
            v43 = *v245,
            v246 = v43,
            (v114 = v43) != 0)
        && (v114 = v43, *(_BYTE *)(*((_QWORD *)v43 + 7) + 8LL) != (_BYTE)v42)
        && !(unsigned int)SOS_Task::IsDelayAbortOn() )
      {
        ex_raise(36, 21, 16, 6);
      }
    }
    utassert_fail(1u, "fRetval", "replicat.cpp", 2325, 0);
  }
  CConnectionOutput::UnstructuredSendMeta(
    *(CConnectionOutput **)(*((_QWORD *)v115 + 14) + 24LL),
    (const struct CColMetaData *)v161,
    224,
    v127,
    0,
    0,
    0,
    0);
  v189 = 2329;
  v241 = qword_103172080;
  v172 = (struct CReplTrace *)operator new(
                                0x18u,
                                qword_103172080,
                                1,
                                "sql\\ntdbms\\srvrepl\\src\\replicat.cpp",
                                2329,
                                6u);
  v114 = v172;
  v147 = v172;
  repl_add_mem(v100, 18, 24);
  v44 = GetTickCount();
  v113 = v44;
  Raise_repl_logscan_sessionXEvent(v25, 1, v15);
  if ( *(_DWORD *)(v36 + 1512) == 5 || *(_BYTE *)(*(_QWORD *)(v36 + 4624) + 8272LL) )
    DBTABLE::RaiseReadonlyDbError((DBTABLE *)v36);
  v110 = 4;
  v109 = 3;
  AdjustLogScanRA(v100, &v110, &v109);
  v136 = 0;
  v137 = 3;
  v138 = 0;
  v139 = 0;
  v135 = &SLogIterForward::`vftable';
  ReplLogIterForward::ReplLogInit(
    (struct LogIterForward *)&v135,
    *(struct LogMgr **)(*(_QWORD *)(v36 + 4624) + 1736LL),
    v110,
    v109);
  if ( v25 )
    *(_DWORD *)(v25 + 24) = 2;
  v105 = GetTickCount() - v44;
  Raise_repl_logscan_sessionXEvent(v25, 0, v15);
  v132 = 0;
  v45 = a6;
  if ( (a6 & 0x800) != 0 )
  {
    v244[4] = SynapseLinkEnvironment::sm_environSynapseLink;
    if ( SynapseLinkEnvironment::sm_environSynapseLink )
    {
      SynapseLinkDB = SynapseLinkEnvironment::FindSynapseLinkDB(SynapseLinkEnvironment::sm_environSynapseLink, v100);
      v132 = SynapseLinkDB;
      if ( !SynapseLinkDB )
        utassert_fail(1u, "pSynapseLinkDB != nullptr", "replicat.cpp", 2360, 0);
      if ( !*((_QWORD *)SynapseLinkDB + 6) )
        *((_QWORD *)SynapseLinkDB + 6) = v169;
      v45 = a6;
      if ( v25 )
        *(_QWORD *)(v25 + 240) = SynapseLinkDB;
    }
  }
  if ( !(unsigned int)repl_cmds_get_xacts(
                        v115,
                        v40,
                        (struct LogIterForward *)&v135,
                        v100,
                        v15,
                        v129,
                        a5,
                        (struct CColMetaData *)v161,
                        (v45 >> 5) & 1,
                        a7,
                        a8,
                        a9,
                        a10,
                        v172,
                        v104,
                        v111,
                        a11,
                        (struct LOGREADERSCAN_HISTORYCACHE_SESSION *)v25,
                        v171,
                        a14,
                        v170) )
    v42 = 0;
  v99 = v42;
  if ( (byte_10317AF82 & 2) != 0 )
    log_unlocalized(L"[ReplDBTTrace] hash table contains %ld transactions\n", *((unsigned int *)v40 + 1));
  v130 = GetTickCount();
  v244[5] = v131 + 188;
  if ( (*(_DWORD *)(v131 + 188) & 4) == 0
    || !(unsigned int)IsExecutionAbortedDueToAttention()
    && ((v201 = NtCurrentTeb()->ThreadLocalStoragePointer,
         v202 = (__int64 *)(v201[SystemThread_TlsIndex] + SystemThread_TlsOffset),
         v47 = *v202,
         (v203 = v47) == 0)
     || !*(_BYTE *)(*(_QWORD *)(v47 + 56) + 8LL)
     || (unsigned int)SOS_Task::IsDelayAbortOn())
    || !byte_10316E68E )
  {
    Raise_repl_logscan_sessionXEvent(v25, 1, v15);
    appended = v42;
    if ( !v42 )
      goto LABEL_194;
    if ( !*((_DWORD *)v40 + 1) )
    {
      if ( (a6 & 0x40) != 0 )
      {
        (*(void (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(*(_QWORD *)(v36 + 4624) + 1736LL) + 368LL))(
          *(_QWORD *)(*(_QWORD *)(v36 + 4624) + 1736LL),
          &v249);
        v121 = (volatile signed __int64 *)(v36 + 5376);
        v143 = 0;
        v123 = 0;
        UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)(v36 + 5376)
          || (v225 = _InterlockedCompareExchange64(v121, UniqueThread_low, 0), v195 = v225 == 0, v225) )
        {
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v144 = 0;
            v226 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v64 = v226[SystemThread_TlsIndex] + SystemThread_TlsOffset == 0;
            v72 = v226[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v227 = v72;
            if ( v64 || *(_QWORD *)(v72 + 272) != v72 )
            {
              v73 = v144;
            }
            else
            {
              v73 = *(_QWORD *)(v72 + 256);
              v144 = v73;
            }
          }
          else
          {
            v73 = 0;
          }
          v123 = v73;
          if ( v73 )
          {
            v196 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v180);
              QuadPart = (DirtyPageMgr *)v180.QuadPart;
              v182 = (DirtyPageMgr *)v180.QuadPart;
            }
            else
            {
              QuadPart = MEMORY[0x7FFE0008];
              v181 = MEMORY[0x7FFE0008];
              v182 = MEMORY[0x7FFE0008];
              v73 = v123;
            }
            v143 = QuadPart;
          }
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v121, UniqueThread_low);
          else
            Spinlock<148,10,258>::SpinToAcquireOptimistic(v121, v73, UniqueThread_low);
          if ( v73 )
          {
            v197 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v183);
              v75 = (DirtyPageMgr *)v183.QuadPart;
              v185 = (DirtyPageMgr *)v183.QuadPart;
            }
            else
            {
              v75 = MEMORY[0x7FFE0008];
              v184 = MEMORY[0x7FFE0008];
              v185 = MEMORY[0x7FFE0008];
              v73 = v123;
            }
            if ( v75 < v143 )
              v76 = 0;
            else
              v76 = v75 - v143;
            v228 = (char *)v76;
            v229 = v73 + 3192;
            *(_QWORD *)(v73 + 3192) += v76;
          }
        }
        v141 = *(_QWORD *)(v36 + 2516);
        v77 = *(_WORD *)(v36 + 2524);
        v142 = v77;
        v230 = v36 + 5376;
        v106 = (char)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v78 = rand();
          v79 = (unsigned int)(5 * (v78 / 5));
          if ( v78 == (_DWORD)v79 )
            Spinlock<148,10,258>::UpdateStatSnapshot(v79);
        }
        *(_QWORD *)(v36 + 5376) = 0;
        v156 = 0;
        v157 = 0;
        v158 = 0;
        if ( v77 || v141 || IsLogRecordReplicated((const struct LSN *)&v249, (struct LogIterForward *)&v135) )
        {
          appended = v42;
        }
        else
        {
          v198 = v249;
          v199 = v250;
          v149 = v249;
          v150 = v250;
          v151 = 0;
          appended = AppendDummyLsnTimeMapping(&v149, v100);
          v99 = appended;
          if ( !appended )
            goto LABEL_199;
        }
      }
      goto LABEL_194;
    }
    v49 = *((_DWORD *)v40 + 6);
    v50 = v104;
    if ( v49 || v104 )
    {
      if ( v25 )
      {
        if ( v104 )
          *(_DWORD *)(v25 + 24) = (v49 != 0) + 4;
        else
          *(_DWORD *)(v25 + 24) = 3;
      }
      Raise_repl_logscan_sessionXEvent(v25, 0, v15);
      v51 = a11;
      if ( !repl_cmds_get_compensation_ranges(
              v40,
              (struct LogIterForward *)&v135,
              v50,
              (struct CColMetaData *)v161,
              a11,
              (struct LOGREADERSCAN_HISTORYCACHE_SESSION *)v25) )
      {
        appended = 0;
        v99 = 0;
        goto LABEL_199;
      }
      Raise_repl_logscan_sessionXEvent(v25, 1, v15);
    }
    else
    {
      v51 = a11;
    }
    if ( v25 )
      *(_DWORD *)(v25 + 24) = 6;
    Raise_repl_logscan_sessionXEvent(v25, 0, v15);
    v52 = v100;
    init_schema_version_cache(qword_103171DF8, v100);
    v159 = *((_QWORD *)v40 + 5);
    v160 = *((_WORD *)v40 + 24);
    if ( !(unsigned int)repl_cmds_get_alt_schemas(
                          (const struct LSN *)&v159,
                          v100,
                          0,
                          (struct LOGREADERSCAN_HISTORYCACHE_SESSION *)v25) )
    {
      appended = 0;
      v99 = 0;
      goto LABEL_199;
    }
    Raise_repl_logscan_sessionXEvent(v25, 1, v15);
    if ( (a6 & 0x40) == 0 )
    {
      v53 = v132;
      v146 = v132;
      try
      {
        if ( v132 )
        {
          v204 = *((_QWORD *)v40 + 10);
          v152 = *(_QWORD *)((char *)v40 + 52);
          v153 = *((_WORD *)v40 + 30);
          v154 = *((_QWORD *)v40 + 8);
          v155 = *((_WORD *)v40 + 36);
          SynapseLinkDatabase::SetupChangeBatch(v132, qword_103172080, &v154, &v152, v204, TickCount, v113, v130);
        }
        trans_cmds = get_trans_cmds(
                       v40,
                       (struct LogIterForward *)&v135,
                       v100,
                       &v112,
                       &v108,
                       (struct CColMetaData *)v161,
                       v51,
                       (struct LOGREADERSCAN_HISTORYCACHE_SESSION *)v25);
        v99 = trans_cmds;
        if ( trans_cmds )
        {
          if ( v53 )
          {
            trans_cmds = SynapseLinkDatabase::QueueAllChangeRowLists(v53);
            v99 = trans_cmds;
          }
          if ( trans_cmds )
            v53 = 0;
          v146 = v53;
        }
      }
      catch ( SQLError v200 )
      {
        try
        {
          ExceptionBackout::ExceptionBackout((ExceptionBackout *)v243, (const struct SQLError *)v200);
          ex_replprint(2u, v132, 0, 0, 0, (const struct SQLError *)v200, 0, L"repl_cmds");
          ExceptionPassOn((const struct SQLError *)v200);
          ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v243);
        }
        catch ( ShortStackException )
        {
        }
        v25 = v122;
        v115 = v124;
        v52 = a2;
        v100 = a2;
      }
      v205 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v55 = v205[SystemThread_TlsIndex] + SystemThread_TlsOffset;
      v206 = v55;
      v56 = *(struct Worker **)(v55 + 256);
      v173 = v56;
      if ( !v56 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v56 = *(struct Worker **)(v55 + 256);
        v173 = v56;
      }
      if ( *((_DWORD *)v56 + 139) )
        ExceptionPostCatchActions(v56);
      if ( v146 )
        SynapseLinkDatabase::CancelBatch(v146, 1);
      appended = v99;
LABEL_129:
      if ( !appended )
        goto LABEL_199;
      init_schema_version_cache(qword_103171DF8, v52);
      v120 = (volatile signed __int64 *)(v103 + 5376);
      v148 = 0;
      v134 = 0;
      v133 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)(v103 + 5376) || (v219 = _InterlockedCompareExchange64(v120, v133, 0), v192 = v219 == 0, v219) )
      {
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v145 = 0;
          v220 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v64 = v220[SystemThread_TlsIndex] + SystemThread_TlsOffset == 0;
          v65 = v220[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v221 = v65;
          if ( v64 || *(_QWORD *)(v65 + 272) != v65 )
          {
            v66 = v145;
          }
          else
          {
            v66 = *(_QWORD *)(v65 + 256);
            v145 = v66;
          }
        }
        else
        {
          v66 = 0;
        }
        v134 = v66;
        if ( v66 )
        {
          v193 = Base_PublicGlobals::sm_invariantTscAvailable;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&PerformanceCount);
            v67 = (DirtyPageMgr *)PerformanceCount.QuadPart;
            v176 = (DirtyPageMgr *)PerformanceCount.QuadPart;
          }
          else
          {
            v67 = MEMORY[0x7FFE0008];
            v175 = MEMORY[0x7FFE0008];
            v176 = MEMORY[0x7FFE0008];
            v66 = v134;
          }
          v148 = v67;
        }
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v120, v133);
        else
          Spinlock<148,10,258>::SpinToAcquireOptimistic(v120, v66, v133);
        if ( v66 )
        {
          v194 = Base_PublicGlobals::sm_invariantTscAvailable;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v177);
            v68 = (DirtyPageMgr *)v177.QuadPart;
            v179 = (DirtyPageMgr *)v177.QuadPart;
          }
          else
          {
            v68 = MEMORY[0x7FFE0008];
            v178 = MEMORY[0x7FFE0008];
            v179 = MEMORY[0x7FFE0008];
            v66 = v134;
          }
          if ( v68 < v148 )
            v69 = 0;
          else
            v69 = v68 - v148;
          v222 = (char *)v69;
          v235 = v66 + 3192;
          *(_QWORD *)(v66 + 3192) += v69;
        }
      }
      if ( v108 )
        *(float *)(v103 + 2580) = (float)v108 / 1000.0;
      v40 = v102;
      *(_DWORD *)(v103 + 2572) = *((_DWORD *)v102 + 1);
      v224 = v103 + 5376;
      v107 = (char)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
      if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v70 = rand();
        v71 = (unsigned int)(5 * (v70 / 5));
        if ( v70 == (_DWORD)v71 )
          Spinlock<148,10,258>::UpdateStatSnapshot(v71);
      }
      *(_QWORD *)(v103 + 5376) = 0;
      appended = v99;
LABEL_194:
      v80 = GetTickCount();
      v113 = v80;
      v136 = 0;
      if ( v138 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v138 + 72LL))(v138);
        if ( v138 )
          (**(void (__fastcall ***)(__int64, __int64))v138)(v138, 1);
        v138 = 0;
      }
      v105 += GetTickCount() - v80;
      if ( appended )
        goto LABEL_200;
      goto LABEL_199;
    }
    if ( v25 )
      *(_DWORD *)(v25 + 24) = 7;
    if ( (a6 & 1) != 0 && !(unsigned int)GetCDCLowerBoundaryLSN((struct AlignedLSN *)(v25 + 248)) )
    {
      appended = 0;
      v99 = 0;
      goto LABEL_199;
    }
    v116 = 0;
    v117 = 0;
    v119 = 0;
    v118 = 1;
    v207 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v208 = (struct Worker **)(v207[SystemThread_TlsIndex] + SystemThread_TlsOffset);
    v209 = *v208;
    v126 = v209;
    *(_QWORD *)&v119 = *((_QWORD *)v209 + 18);
    v210 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v211 = (struct Worker **)(v210[SystemThread_TlsIndex] + SystemThread_TlsOffset);
    v212 = *v211;
    v126 = v212;
    v57 = *((_BYTE *)v212 + 152);
    v190 = v57 != 0;
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v119 + 464LL))(v119) )
    {
      if ( v57 && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v119 + 488LL))(v119) )
        utassert_fail(
          1u,
          "rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()",
          "automsqlxact.cpp",
          235,
          0);
      (*(void (__fastcall **)(_QWORD, __int64, __int64, int *))(*(_QWORD *)v119 + 232LL))(v119, 2, 1, &v117);
      v118 = 1;
      v116 = 3;
    }
    else
    {
      (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64))(*(_QWORD *)v119 + 8LL))(v119, L"changeTable", 22);
      v116 = 1;
    }
    v58 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v119 + 648LL))(v119, v100);
    LOBYTE(v59) = 1;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v58 + 504LL))(v58, v59);
    try
    {
      Raise_repl_logscan_sessionXEvent(v25, 0, v15);
      v99 = get_trans_cmds(
              v102,
              (struct LogIterForward *)&v135,
              v100,
              &v112,
              &v108,
              (struct CColMetaData *)v161,
              v51,
              (struct LOGREADERSCAN_HISTORYCACHE_SESSION *)v25);
    }
    catch ( SQLError v247 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v244, (const struct SQLError *)v247);
        CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v116, 0);
        ex_replprint(22859, 16, 1);
        ExceptionPassOn((const struct SQLError *)v247);
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v244);
      }
      catch ( ShortStackException )
      {
      }
      v25 = v122;
      v115 = v124;
      v15 = v140;
      v52 = a2;
      v100 = a2;
    }
    v213 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v60 = v213[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v214 = v60;
    v61 = *(struct Worker **)(v60 + 256);
    v126 = v61;
    if ( !v61 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v61 = *(struct Worker **)(v60 + 256);
      v126 = v61;
    }
    if ( *((_DWORD *)v61 + 139) )
      ExceptionPostCatchActions(v61);
    appended = v99;
    if ( v99 )
    {
      if ( byte_10317AF82 >= 0 )
      {
        v215 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v216 = (__int64 *)(v215[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v62 = *v216;
        v217 = v62;
        if ( v62
          && (v63 = **(struct CSessionTraceFlags ***)(v62 + 56), (v218 = v63) != 0)
          && (v191 = CSessionTraceFlags::CheckSessionTraceInternal(v63, 0x2017u)) != 0 )
        {
          appended = v99;
        }
        else
        {
          appended = CompletingCDCBatchPopulating(v52, 1, (struct LOGREADERSCAN_HISTORYCACHE_SESSION *)v25);
          v99 = appended;
        }
      }
      if ( appended )
      {
        v40 = v102;
        appended = PopulateCDCLSNTimeMappingTable(v102, (struct LOGREADERSCAN_HISTORYCACHE_SESSION *)v25);
        v99 = appended;
        if ( appended )
        {
          CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v116, 0);
        }
        else
        {
          CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v116, 0);
          ex_replprint(22858, 16, 1);
        }
LABEL_127:
        Raise_repl_logscan_sessionXEvent(v25, 1, v15);
        if ( v116 )
          CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v116, 0);
        goto LABEL_129;
      }
      CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v116, 0);
      ex_replprint(22863, 16, 1);
    }
    else
    {
      CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v116, 0);
      ex_replprint(22859, 16, 2);
    }
    v40 = v102;
    goto LABEL_127;
  }
  appended = 0;
  v99 = 0;
LABEL_199:
  ReplDumpLogForFailure(v103, v40, v25);
LABEL_200:
  if ( v114 )
    operator delete(v114, 0x18u);
  repl_add_mem(v100, 18, 0);
  if ( v40 )
    ReplTranHash::ClearOffrowData(v40, v100);
  if ( !appended )
  {
    if ( *((_DWORD *)v40 + 1) )
    {
      if ( (a6 & 0x40) != 0 && byte_10317AF82 >= 0 )
      {
        v231 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v232 = (__int64 *)(v231[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v81 = *v232;
        v233 = v81;
        if ( !v81
          || (v82 = **(struct CSessionTraceFlags ***)(v81 + 56), (v234 = v82) == 0)
          || (v167 = CSessionTraceFlags::CheckSessionTraceInternal(v82, 0x2017u)) == 0 )
        {
          CompletingCDCBatchPopulating(v100, 0, 0);
        }
      }
    }
  }
  v135 = &SLogIterForward::`vftable';
  if ( v138 )
  {
    (**(void (__fastcall ***)(__int64, __int64))v138)(v138, 1);
    v138 = 0;
  }
  ExcHandler::~ExcHandler((ExcHandler *)v248);
  v83 = v115;
  v84 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v85 = *(struct Worker **)(v84 + 256);
  if ( !v85 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v85 = *(struct Worker **)(v84 + 256);
  }
  if ( *((_DWORD *)v85 + 139) )
    ExceptionPostCatchActions(v85);
  v86 = v99;
  if ( !v99 )
    ex_raise(36, 21, 16, 6);
  if ( v103 )
  {
    v87 = (volatile signed __int64 *)(v103 + 5376);
    v88 = 0;
    v89 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *(_DWORD *)(v103 + 5376) || _InterlockedCompareExchange64(v87, v89, 0) )
    {
      v90 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v91 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v91 && *(_QWORD *)(v91 + 272) == v91 )
          v90 = *(_QWORD *)(v91 + 256);
        if ( v90 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v186);
            v88 = (DirtyPageMgr *)v186.QuadPart;
          }
          else
          {
            v88 = MEMORY[0x7FFE0008];
          }
        }
      }
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v87, v89);
      else
        Spinlock<148,10,258>::SpinToAcquireOptimistic(v87, v90, v89);
      if ( v90 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v187);
          v92 = (DirtyPageMgr *)v187.QuadPart;
        }
        else
        {
          v92 = MEMORY[0x7FFE0008];
        }
        v93 = v92 - v88;
        if ( v92 < v88 )
          v93 = 0;
        *(_QWORD *)(v90 + 3192) += v93;
      }
    }
    *(_DWORD *)(v103 + 2584) = 0;
    *(_QWORD *)(v103 + 2588) = 0;
    *(_WORD *)(v103 + 2596) = 0;
    if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v94 = rand();
      if ( v94 == 5 * (v94 / 5) )
        Spinlock<148,10,258>::UpdateStatSnapshot((unsigned int)((unsigned __int64)(1717986919LL * v94) >> 32) >> 31);
    }
    *v87 = 0;
    v86 = v99;
  }
  if ( (byte_10317AF82 & 8) != 0 )
  {
    repl_timer = get_repl_timer(v100);
    if ( repl_timer )
      *((_DWORD *)repl_timer + 4) += v105;
  }
  if ( !v86 )
    utassert_fail(1u, "fRetval", "replicat.cpp", 2693, 0);
  CConnectionOutput::UnstructuredEndResultSet(*(CConnectionOutput **)(*((_QWORD *)v83 + 14) + 24LL), 0, &v188, 0, 0);
  **((_QWORD **)v83 + 15) = v188;
  CColMetaData::~CColMetaData((CColMetaData *)v161);
  return v86;
}

```

## disassembly

```asm
0x10115dd20  push    rbx
0x10115dd22  push    rsi
0x10115dd23  push    rdi
0x10115dd24  push    r12
0x10115dd26  push    r13
0x10115dd28  push    r14
0x10115dd2a  push    r15
0x10115dd2c  sub     rsp, 610h
0x10115dd33  mov     [rsp+648h+var_1B8], 0FFFFFFFFFFFFFFFEh
0x10115dd3f  mov     rax, cs:__security_cookie
0x10115dd46  xor     rax, rsp
0x10115dd49  mov     [rsp+648h+var_40], rax
0x10115dd51  mov     [rsp+648h+var_4D0], r9d
0x10115dd59  mov     r13d, r8d
0x10115dd5c  movzx   r12d, dx
0x10115dd60  mov     [rsp+648h+var_594], r12w
0x10115dd69  mov     r15, rcx
0x10115dd6c  mov     [rsp+648h+var_538], rcx
0x10115dd74  mov     [rsp+648h+var_4F0], rcx
0x10115dd7c  mov     [rsp+648h+var_590], r12w
0x10115dd85  mov     [rsp+648h+var_480], r8d
0x10115dd8d  mov     rax, [rsp+648h+arg_30]
0x10115dd95  mov     [rsp+648h+var_578], rax
0x10115dd9d  mov     r14, [rsp+648h+arg_58]
0x10115dda5  mov     [rsp+648h+var_378], r14
0x10115ddad  mov     rax, [rsp+648h+arg_60]
0x10115ddb5  mov     [rsp+648h+var_368], rax
0x10115ddbd  mov     rax, [rsp+648h+arg_70]
0x10115ddc5  mov     [rsp+648h+var_370], rax
0x10115ddcd  mov     rdx, gs:58h
0x10115ddd6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10115dddd  mov     ecx, [rax]
0x10115dddf  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10115dde6  mov     ebx, [rax]
0x10115dde8  add     rbx, [rdx+rcx*8]
0x10115ddec  mov     rax, [rbx+100h]
0x10115ddf3  test    rax, rax
0x10115ddf6  jnz     short loc_10115DE07
0x10115ddf8  xor     ecx, ecx
0x10115ddfa  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10115de00  mov     rax, [rbx+100h]
0x10115de07  mov     rsi, [rax+3E8h]
0x10115de0e  xor     edi, edi
0x10115de10  mov     [rsp+648h+var_448], rdi
0x10115de18  mov     [rsp+648h+var_598], 1
0x10115de23  call    cs:__imp_GetTickCount
0x10115de29  mov     [rsp+648h+var_4D4], eax
0x10115de30  mov     [rsp+648h+var_54C], edi
0x10115de37  mov     [rsp+648h+var_55C], edi
0x10115de3e  mov     [rsp+648h+var_580], rdi
0x10115de46  mov     [rsp+648h+var_564], edi
0x10115de4d  mov     rcx, [r15+40h]
0x10115de51  lea     edx, [rdi+4]; unsigned int
0x10115de54  mov     rcx, [rcx]; this
0x10115de57  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x10115de5c  mov     ecx, edi
0x10115de5e  test    eax, eax
0x10115de60  setnz   cl
0x10115de63  mov     [rsp+648h+var_4D8], ecx
0x10115de6a  mov     [rsp+648h+var_568], edi
0x10115de71  mov     [rsp+648h+var_550], edi
0x10115de78  mov     rdx, gs:58h
0x10115de81  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10115de88  mov     ecx, [rax]
0x10115de8a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10115de91  mov     ebx, [rax]
0x10115de93  add     rbx, [rdx+rcx*8]
0x10115de97  mov     rax, [rbx+100h]
0x10115de9e  test    rax, rax
0x10115dea1  jnz     short loc_10115DEB2
0x10115dea3  xor     ecx, ecx
0x10115dea5  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10115deab  mov     rax, [rbx+100h]
0x10115deb2  mov     rax, [rax+258h]
0x10115deb9  mov     [rsp+648h+var_4C8], rax
0x10115dec1  mov     cs:?CdcTelemetryIntervalInMilliSec@@3KA, edi; ulong CdcTelemetryIntervalInMilliSec
0x10115dec7  cmp     cs:dword_103172528, edi
0x10115decd  jz      short loc_10115DF11
0x10115decf  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x10115ded6  mov     rcx, [rax]
0x10115ded9  mov     rax, [rcx]
0x10115dedc  mov     [rsp+648h+var_620], rdi
0x10115dee1  mov     byte ptr [rsp+648h+var_628], dil
0x10115dee6  lea     r9, ?CdcTelemetryIntervalInMin@@3HA; int CdcTelemetryIntervalInMin
0x10115deed  lea     r8, aCdclogreaderte; "CdcLogReaderTelemetryIntervalInMins"
0x10115def4  lea     rdx, aReplication_0; "Replication"
0x10115defb  call    qword ptr [rax+208h]
0x10115df01  imul    eax, cs:?CdcTelemetryIntervalInMin@@3HA, 0EA60h; int CdcTelemetryIntervalInMin
0x10115df0b  mov     cs:?CdcTelemetryIntervalInMilliSec@@3KA, eax; ulong CdcTelemetryIntervalInMilliSec
0x10115df11  mov     [rsp+648h+var_588], rdi
0x10115df19  test    r14, r14
0x10115df1c  jz      short loc_10115DF3E
0x10115df1e  mov     rcx, [r14+30h]
0x10115df22  test    rcx, rcx
0x10115df25  jz      short loc_10115DF3E
0x10115df27  movsx   rax, word ptr [r14+3Ah]
0x10115df2c  cmp     ax, 0FFFFh
0x10115df30  jz      short loc_10115DF3E
0x10115df32  imul    r14, rax, 110h
0x10115df39  add     r14, rcx
0x10115df3c  jmp     short loc_10115DF41
0x10115df3e  mov     r14, rdi
0x10115df41  mov     [rsp+648h+var_500], r14
0x10115df49  lea     rax, ??_7IFidoRowGroupMetadataSerializer@@6B@; const IFidoRowGroupMetadataSerializer::`vftable'
0x10115df50  mov     [rsp+648h+var_3D8], rax
0x10115df58  lea     rax, ??_7CColMetaData@@6B@; const CColMetaData::`vftable'
0x10115df5f  mov     [rsp+648h+var_3D8], rax
0x10115df67  mov     [rsp+648h+var_3D0], rdi
0x10115df6f  xorps   xmm0, xmm0
0x10115df72  movdqa  [rsp+648h+var_3C8], xmm0
0x10115df7b  mov     [rsp+648h+var_3B8], rdi
0x10115df83  mov     [rsp+648h+var_3B0], di
0x10115df8b  mov     [rsp+648h+var_3AC], rdi
0x10115df93  mov     [rsp+648h+var_3A0], rdi
0x10115df9b  mov     rdx, gs:58h; unsigned __int16
0x10115dfa4  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10115dfab  mov     ecx, [rax]
0x10115dfad  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10115dfb4  mov     eax, [rax]
0x10115dfb6  add     rax, [rdx+rcx*8]
0x10115dfba  mov     rax, [rax]
0x10115dfbd  mov     rcx, [rax+50h]
0x10115dfc1  movzx   ecx, word ptr [rcx+8]; this
0x10115dfc5  call    ?GetDefaultCollationData@CDbAndSetOptsImplImport@@YAQEBVCDefaultCollation@@G@Z; CDbAndSetOptsImplImport::GetDefaultCollationData(ushort)
0x10115dfca  mov     ecx, [rax]
0x10115dfcc  call    cs:__imp_?UICodePageFromCID@@YAIK@Z; UICodePageFromCID(ulong)
0x10115dfd2  mov     rcx, [r15+40h]
0x10115dfd6  mov     r9, [rcx]
0x10115dfd9  mov     r8d, 0Eh; unsigned __int16
0x10115dfdf  mov     dword ptr [rsp+648h+var_628], eax; unsigned int
0x10115dfe3  mov     r9d, [r9+2Ch]; int
0x10115dfe7  mov     rdx, rsi; struct IMemObj *
0x10115dfea  lea     rcx, [rsp+648h+var_3D8]; this
0x10115dff2  call    ?Init@CColMetaData@@QEAAXPEAVIMemObj@@GJI@Z; CColMetaData::Init(IMemObj *,ushort,long,uint)
0x10115dff7  mov     r8d, r13d
0x10115dffa  xor     edx, edx
0x10115dffc  mov     rcx, r14
0x10115dfff  call    ?Raise_repl_logscan_sessionXEvent@@YAXPEAULOGREADERSCAN_HISTORYCACHE_SESSION@@W4LogreaderPhaseStates@XeSqlPkg@@H@Z; Raise_repl_logscan_sessionXEvent(LOGREADERSCAN_HISTORYCACHE_SESSION *,XeSqlPkg::LogreaderPhaseStates,int)
0x10115e004  movzx   esi, di
0x10115e007  lea     rbx, ?replcmdstitle@@3PAUREPL_RESULTSET_TITLE@@A; REPL_RESULTSET_TITLE near * replcmdstitle
0x10115e00e  xchg    ax, ax
0x10115e010  call    cs:__imp_?GetColMDStatUnset@@YA?AUColMDStatus@@XZ; GetColMDStatUnset(void)
0x10115e016  mov     r9, [rbx+8]
0x10115e01a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10115e021  inc     rcx
0x10115e024  cmp     word ptr [r9+rcx*2], 0
0x10115e02a  jnz     short loc_10115E021
0x10115e02c  mov     [rsp+648h+var_5F8], edi
0x10115e030  mov     dword ptr [rsp+648h+var_600], 1
0x10115e038  mov     word ptr [rsp+648h+var_608], di
0x10115e03d  mov     [rsp+648h+var_610], rdi
0x10115e042  mov     word ptr [rsp+648h+var_618], ax
0x10115e047  mov     dword ptr [rsp+648h+var_620], 1
0x10115e04f  mov     byte ptr [rsp+648h+var_628], cl
0x10115e053  mov     r8, [rbx]
0x10115e056  movzx   edx, si
0x10115e059  lea     rcx, [rsp+648h+var_3D8]
0x10115e061  call    cs:__imp_?SetColumn@CColMetaData@@QEAAXGAEBVCTypeInfo@@PEB_WEHUColMDStatus@@1GHH@Z; CColMetaData::SetColumn(ushort,CTypeInfo const &,wchar_t const *,uchar,int,ColMDStatus,wchar_t const *,ushort,int,int)
0x10115e067  inc     si
0x10115e06a  add     rbx, 10h
0x10115e06e  cmp     si, 0Eh
0x10115e072  jb      short loc_10115E010
0x10115e074  xor     edx, edx; unsigned __int16
0x10115e076  mov     [rsp+648h+var_620], rdi; struct Worker *
0x10115e07b  mov     rax, cs:__imp_?hdl_prntbackout@@YAHHHHHPEAD@Z; hdl_prntbackout(int,int,int,int,char *)
0x10115e082  mov     [rsp+648h+var_628], rax; int (*)(int, int, int, int, char *)
0x10115e087  xor     r9d, r9d; unsigned __int8
0x10115e08a  xor     r8d, r8d; unsigned __int8
0x10115e08d  lea     rcx, [rsp+648h+var_78]; this
0x10115e095  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x10115e09a  nop
0x10115e09b  cmp     cs:dword_103172528, 0
0x10115e0a2  jnz     short loc_10115E0FF
0x10115e0a4  test    [rsp+648h+arg_28], 800h
0x10115e0af  jnz     short loc_10115E0FF
0x10115e0b1  lea     r8, [rsp+648h+var_550]; int *
0x10115e0b9  lea     rdx, [rsp+648h+var_568]; int *
0x10115e0c1  call    ?GetPeerToPeerDBInfo@@YAHGAEAH0@Z; GetPeerToPeerDBInfo(ushort,int &,int &)
0x10115e0c6  test    eax, eax
0x10115e0c8  jnz     short loc_10115E0FF
0x10115e0ca  lea     edx, [rax+10h]; int
0x10115e0cd  mov     ecx, 499Fh; int
0x10115e0d2  lea     r8d, [rax+1]; int
0x10115e0d6  call    ?ex_replprint@@YAXHHHZZ; ex_replprint(int,int,int,...)
0x10115e0db  nop
0x10115e0dc  lea     rcx, [rsp+648h+var_78]; this
0x10115e0e4  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x10115e0e9  nop
0x10115e0ea  lea     rcx, [rsp+648h+var_3D8]
0x10115e0f2  call    cs:__imp_??1CColMetaData@@UEAA@XZ; CColMetaData::~CColMetaData(void)
0x10115e0f8  xor     eax, eax
0x10115e0fa  jmp     loc_10115F9BD
0x10115e0ff  mov     ecx, r12d
0x10115e102  mov     rax, cs:__imp_?g_dbtableFactory@@3UDBTableFactory@@A; DBTableFactory g_dbtableFactory
0x10115e109  call    qword ptr [rax+20h]
0x10115e10c  mov     r15, rax
0x10115e10f  mov     [rsp+648h+var_580], rax
0x10115e117  movzx   ecx, r12w; unsigned __int16
0x10115e11b  call    ?get_repl_mem@@YAPEAUREPL_DATABASE_MEM@@G@Z; get_repl_mem(ushort)
0x10115e120  mov     [rsp+648h+var_380], rax
0x10115e128  mov     rbx, [rsp+648h+var_4C8]
0x10115e130  test    rax, rax
0x10115e133  jnz     loc_10115E207
0x10115e139  lea     rax, [rbx+0BCh]
0x10115e140  mov     [rsp+648h+var_120], rax
0x10115e148  mov     eax, [rax]
0x10115e14a  test    al, 4
0x10115e14c  jz      loc_10115E1D3
0x10115e152  call    ?IsExecutionAbortedDueToAttention@@YAHXZ; IsExecutionAbortedDueToAttention(void)
0x10115e157  test    eax, eax
0x10115e159  jnz     short loc_10115E1BD
0x10115e15b  mov     r8, gs:58h
0x10115e164  mov     [rsp+648h+var_118], r8
0x10115e16c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10115e173  mov     ecx, [rax]
0x10115e175  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10115e17c  mov     edx, [rax]
0x10115e17e  add     rdx, [r8+rcx*8]
0x10115e182  mov     [rsp+648h+var_110], rdx
0x10115e18a  mov     rax, [rdx]
0x10115e18d  mov     [rsp+648h+var_108], rax
0x10115e195  mov     [rsp+648h+var_540], rax
0x10115e19d  test    rax, rax
0x10115e1a0  jz      short loc_10115E1D3
0x10115e1a2  mov     [rsp+648h+var_540], rax
0x10115e1aa  mov     rax, [rax+38h]
0x10115e1ae  cmp     byte ptr [rax+8], 0
0x10115e1b2  jz      short loc_10115E1D3
0x10115e1b4  call    ?IsDelayAbortOn@SOS_Task@@SAHXZ; SOS_Task::IsDelayAbortOn(void)
0x10115e1b9  test    eax, eax
0x10115e1bb  jnz     short loc_10115E1D3
0x10115e1bd  mov     edx, 15h
0x10115e1c2  lea     ecx, [rdx+0Fh]
0x10115e1c5  lea     r9d, [rdx-0Fh]
0x10115e1c9  lea     r8d, [rdx-5]
0x10115e1cd  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10115e1d3  mov     [rsp+648h+var_628], rdi
0x10115e1d8  mov     r9d, 90Ah
0x10115e1de  lea     r8, aReplicatCpp; "replicat.cpp"
0x10115e1e5  lea     rdx, aDbMem; "db_mem"
0x10115e1ec  mov     ecx, 1
0x10115e1f1  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10115e1f7  mov     r15, [rsp+648h+var_580]
0x10115e1ff  mov     rax, [rsp+648h+var_380]
0x10115e207  mov     rsi, [rax+3F8h]
0x10115e20e  mov     [rsp+648h+var_588], rsi
0x10115e216  test    rsi, rsi
0x10115e219  jnz     short loc_10115E23D
0x10115e21b  mov     [rsp+648h+var_628], rdi
0x10115e220  mov     r9d, 90Dh
0x10115e226  lea     r8, aReplicatCpp; "replicat.cpp"
0x10115e22d  lea     rdx, aPhashTable; "phash_table"
0x10115e234  lea     ecx, [rsi+1]
0x10115e237  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10115e23d  mov     edx, 186A0h
0x10115e242  cmp     r13d, edx
0x10115e245  cmovl   edx, r13d
0x10115e249  add     edx, edx; unsigned int
0x10115e24b  mov     rcx, rsi; this
0x10115e24e  call    ?ReInit@ReplTranHash@@QEAAHK@Z; ReplTranHash::ReInit(ulong)
0x10115e253  mov     r12d, eax
0x10115e256  mov     [rsp+648h+var_598], eax
0x10115e25d  test    eax, eax
0x10115e25f  jnz     loc_10115E33B
0x10115e265  lea     rax, [rbx+0BCh]
0x10115e26c  mov     [rsp+648h+var_100], rax
0x10115e274  mov     eax, [rax]
0x10115e276  test    al, 4
0x10115e278  jz      loc_10115E2FF
0x10115e27e  call    ?IsExecutionAbortedDueToAttention@@YAHXZ; IsExecutionAbortedDueToAttention(void)
0x10115e283  test    eax, eax
0x10115e285  jnz     short loc_10115E2E9
0x10115e287  mov     r8, gs:58h
0x10115e290  mov     [rsp+648h+var_F0], r8
0x10115e298  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10115e29f  mov     ecx, [rax]
0x10115e2a1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10115e2a8  mov     edx, [rax]
0x10115e2aa  add     rdx, [r8+rcx*8]
0x10115e2ae  mov     [rsp+648h+var_A8], rdx
0x10115e2b6  mov     rax, [rdx]
0x10115e2b9  mov     [rsp+648h+var_A0], rax
0x10115e2c1  mov     [rsp+648h+var_540], rax
0x10115e2c9  test    rax, rax
0x10115e2cc  jz      short loc_10115E2FF
0x10115e2ce  mov     [rsp+648h+var_540], rax
0x10115e2d6  mov     rax, [rax+38h]
0x10115e2da  cmp     [rax+8], r12b
0x10115e2de  jz      short loc_10115E2FF
0x10115e2e0  call    ?IsDelayAbortOn@SOS_Task@@SAHXZ; SOS_Task::IsDelayAbortOn(void)
0x10115e2e5  test    eax, eax
0x10115e2e7  jnz     short loc_10115E2FF
0x10115e2e9  mov     edx, 15h
0x10115e2ee  lea     ecx, [rdx+0Fh]
0x10115e2f1  lea     r9d, [rdx-0Fh]
0x10115e2f5  lea     r8d, [rdx-5]
0x10115e2f9  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10115e2ff  mov     [rsp+648h+var_628], rdi
0x10115e304  mov     r9d, 915h
0x10115e30a  lea     r8, aReplicatCpp; "replicat.cpp"
  ... truncated ...
```
