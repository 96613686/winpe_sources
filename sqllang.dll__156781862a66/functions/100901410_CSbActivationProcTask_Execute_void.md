# CSbActivationProcTask::Execute(void)

- ea: `0x100901410`
- end: `0x10090372d`
- name: `?Execute@CSbActivationProcTask@@EEAAXXZ`
- size: `8989`
- prototype: `void __fastcall(CSbActivationProcTask *__hidden this)`
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x100401070`
- `0x100401090`
- `0x1004012d0`
- `0x100401340`
- `0x10040cd80`
- `0x1004131b0`
- `0x100415d70`
- `0x100428720`
- `0x10042aa50`
- `0x1005361b0`
- `0x1006d99f0`
- `0x10083a1d0`
- `0x10083a3f0`
- `0x10083a660`
- `0x1008547c0`
- `0x1008ffd90`
- `0x1008ffe70`
- `0x100900040`
- `0x1009005c0`
- `0x100901410`
- `0x1009068e0`
- `0x100906cc0`
- `0x10093bad0`
- `0x100a06040`
- `0x100a06550`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10090164a`
- `KERNEL32!QueryPerformanceCounter` at `0x1009016a8`
- `KERNEL32!QueryPerformanceCounter` at `0x1009018c6`
- `KERNEL32!QueryPerformanceCounter` at `0x100901924`
- `KERNEL32!QueryPerformanceCounter` at `0x10090164a`
- `KERNEL32!QueryPerformanceCounter` at `0x1009016a8`
- `KERNEL32!QueryPerformanceCounter` at `0x1009018c6`
- `KERNEL32!QueryPerformanceCounter` at `0x100901924`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x100901c7f`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x100901de9`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x100901f20`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x100901c59`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x100901ef6`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100901662`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x1009018de`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1009015e9`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100901865`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1009016fe`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1009019f2`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100901e3d`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1009024b6`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10090269e`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100902871`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100902970`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100902b2d`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100902c55`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100902d46`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100902e2d`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100902f63`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100903047`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100903138`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10090325c`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10090337c`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10090353d`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10090359f`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100903647`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1009036c1`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100901637`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100901694`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1009018b3`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100901910`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1009034c7`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1009034c7`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1009017af`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100901820`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1009017af`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100901820`
- `sqldk!SystemThread_TlsIndex` at `0x100901482`
- `sqldk!SystemThread_TlsIndex` at `0x100901609`
- `sqldk!SystemThread_TlsIndex` at `0x100901755`
- `sqldk!SystemThread_TlsIndex` at `0x1009017c9`
- `sqldk!SystemThread_TlsIndex` at `0x100901885`
- `sqldk!SystemThread_TlsIndex` at `0x100901ade`
- `sqldk!SystemThread_TlsIndex` at `0x100901b16`
- `sqldk!SystemThread_TlsIndex` at `0x1009020a3`
- `sqldk!SystemThread_TlsIndex` at `0x10090214d`
- `sqldk!SystemThread_TlsIndex` at `0x1009021e9`
- `sqldk!SystemThread_TlsIndex` at `0x100902281`
- `sqldk!SystemThread_TlsIndex` at `0x100902381`
- `sqldk!SystemThread_TlsIndex` at `0x10090240d`
- `sqldk!SystemThread_TlsIndex` at `0x1009027d5`
- `sqldk!SystemThread_TlsIndex` at `0x100902ba8`
- `sqldk!SystemThread_TlsIndex` at `0x100902e91`
- `sqldk!SystemThread_TlsIndex` at `0x10090319c`
- `sqldk!SystemThread_TlsIndex` at `0x10090348f`
- `sqldk!SystemThread_TlsOffset` at `0x10090148b`
- `sqldk!SystemThread_TlsOffset` at `0x100901612`
- `sqldk!SystemThread_TlsOffset` at `0x10090175e`
- `sqldk!SystemThread_TlsOffset` at `0x1009017d2`
- `sqldk!SystemThread_TlsOffset` at `0x10090188e`
- `sqldk!SystemThread_TlsOffset` at `0x100901ae7`
- `sqldk!SystemThread_TlsOffset` at `0x100901b1f`
- `sqldk!SystemThread_TlsOffset` at `0x1009020ac`
- `sqldk!SystemThread_TlsOffset` at `0x100902156`
- `sqldk!SystemThread_TlsOffset` at `0x1009021f2`
- `sqldk!SystemThread_TlsOffset` at `0x10090228c`
- `sqldk!SystemThread_TlsOffset` at `0x10090238a`
- `sqldk!SystemThread_TlsOffset` at `0x100902416`
- `sqldk!SystemThread_TlsOffset` at `0x1009027e6`
- `sqldk!SystemThread_TlsOffset` at `0x100902bb1`
- `sqldk!SystemThread_TlsOffset` at `0x100902e9a`
- `sqldk!SystemThread_TlsOffset` at `0x1009031a5`
- `sqldk!SystemThread_TlsOffset` at `0x100903498`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100901777`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009017eb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009034b1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100901777`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009017eb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009034b1`
- `sqldk!??_V@YAXPEAX@Z` at `0x10090351f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1009035e7`
- `sqldk!??_V@YAXPEAX@Z` at `0x1009035f4`
- `sqldk!??_V@YAXPEAX@Z` at `0x1009036a8`
- `sqldk!??_V@YAXPEAX@Z` at `0x10090351f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1009035e7`
- `sqldk!??_V@YAXPEAX@Z` at `0x1009035f4`
- `sqldk!??_V@YAXPEAX@Z` at `0x1009036a8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10090170a`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009019fe`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100901e52`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009024cb`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009026b3`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100902886`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100902993`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100902a37`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100902b42`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100902c6a`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100902d5b`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100902e42`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100902f78`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10090305c`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10090314d`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100903271`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100903391`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100903549`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009035ab`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100903653`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009036cd`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10090170a`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009019fe`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100901e52`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009024cb`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009026b3`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100902886`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100902993`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100902a37`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100902b42`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100902c6a`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100902d5b`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100902e42`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100902f78`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10090305c`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10090314d`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100903271`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100903391`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100903549`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009035ab`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100903653`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1009036cd`
- `sqlmin!?IncrementCounterInstanceValue@PerfmonManager@@QEAAHKK_JKPEA_K@Z` at `0x100901cd4`
- `sqlmin!?IncrementCounterInstanceValue@PerfmonManager@@QEAAHKK_JKPEA_K@Z` at `0x100901e1e`
- `sqlmin!?IncrementCounterInstanceValue@PerfmonManager@@QEAAHKK_JKPEA_K@Z` at `0x100901f71`
- `sqlmin!?IncrementCounterInstanceValue@PerfmonManager@@QEAAHKK_JKPEA_K@Z` at `0x100901cd4`
- `sqlmin!?IncrementCounterInstanceValue@PerfmonManager@@QEAAHKK_JKPEA_K@Z` at `0x100901e1e`
- `sqlmin!?IncrementCounterInstanceValue@PerfmonManager@@QEAAHKK_JKPEA_K@Z` at `0x100901f71`
- `sqlmin!GetXdbServerGlobals` at `0x1009014fc`
- `sqlmin!GetXdbServerGlobals` at `0x100902116`
- `sqlmin!GetXdbServerGlobals` at `0x10090226c`
- `sqlmin!GetXdbServerGlobals` at `0x1009014fc`
- `sqlmin!GetXdbServerGlobals` at `0x100902116`
- `sqlmin!GetXdbServerGlobals` at `0x10090226c`

## string_xrefs

- `0x10090179e`: `sql\ntdbms\broker\src\ssbInternalActivation.cpp`
- `0x10090180f`: `sql\ntdbms\broker\src\ssbInternalActivation.cpp`
- `0x1009025ce`: `CSbActivationProcTask::Invoke`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
void __fastcall CSbActivationProcTask::Execute(CSbActivationProcTask *this)
{
  CSbActivationProcTask *v1; // rsi
  __int64 v2; // rcx
  __int16 v3; // cx
  __int64 v4; // rdx
  __int64 v5; // rcx
  struct CActiveServiceBroker *ActiveBrokerById; // r14
  __int64 v7; // rcx
  CSbTransportMgr *QuadPart; // rbx
  signed __int64 UniqueThread_low; // r15
  __int64 v10; // r14
  __int64 v11; // r8
  CSbTransportMgr *v12; // rax
  signed __int64 v13; // rax
  __int64 v14; // r14
  unsigned int v15; // r14d
  int v16; // r8d
  unsigned int v17; // r15d
  __int64 v18; // rbx
  __int64 v19; // rcx
  unsigned __int64 v20; // r12
  unsigned __int64 v21; // rax
  void *v22; // r15
  __int64 v23; // rbx
  __int64 v24; // rcx
  unsigned __int64 v25; // rax
  CSbTransportMgr *v26; // rbx
  signed __int64 v27; // r13
  __int64 v28; // r15
  __int64 v29; // r8
  CSbTransportMgr *v30; // rax
  signed __int64 v31; // rax
  const wchar_t *v32; // rcx
  __int64 v33; // rax
  int v34; // ebx
  _WORD *v35; // rcx
  unsigned __int64 v36; // rdx
  __int64 v37; // r8
  __int16 v38; // ax
  _WORD *v39; // rax
  int v40; // r8d
  __int64 v41; // rcx
  void ***v42; // rdx
  __int64 v43; // rbx
  __int64 v44; // r8
  int v45; // eax
  int v46; // ecx
  int v47; // r14d
  _QWORD *v48; // rbx
  int v49; // r8d
  unsigned int v50; // r12d
  __int64 v51; // rdx
  int v52; // eax
  int v53; // edx
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v55; // rbx
  __int64 v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // rcx
  char v60; // al
  __int64 v61; // rax
  __int64 XdbServerGlobals; // rax
  _QWORD *v63; // r8
  __int64 v64; // rcx
  char v65; // al
  __int64 v66; // rax
  int v67; // r15d
  _QWORD *v68; // r14
  int v69; // r8d
  int v70; // eax
  __int64 v71; // rax
  __int64 v72; // r8
  __int64 v73; // rax
  __int64 v74; // rdx
  int v75; // r15d
  _QWORD *v76; // r14
  int v77; // r8d
  bool v78; // cl
  __int64 v79; // r8
  int v80; // eax
  int v81; // r15d
  _QWORD *v82; // r14
  int v83; // r8d
  _QWORD *v84; // r14
  int v85; // r8d
  int v86; // eax
  unsigned int v87; // eax
  int v88; // r8d
  __int64 v89; // rdx
  bool v90; // r14
  _QWORD *v91; // r15
  int v92; // r8d
  __int64 v93; // rcx
  unsigned int v94; // r14d
  _QWORD *v95; // r14
  int v96; // r8d
  __int64 v97; // rax
  int v98; // r15d
  _QWORD *v99; // r14
  int v100; // r8d
  _QWORD *v101; // r14
  int v102; // r8d
  bool v103; // cl
  int v104; // eax
  _QWORD *v105; // r14
  int v106; // r8d
  __int64 v107; // rax
  int v108; // r15d
  _QWORD *v109; // r14
  int v110; // r8d
  _QWORD *v111; // r14
  int v112; // r8d
  int v113; // r14d
  _QWORD *v114; // rbx
  int v115; // r8d
  bool v116; // al
  __int64 v117; // rcx
  __int64 v118; // rdx
  int v119; // r14d
  _QWORD *v120; // rbx
  int v121; // r8d
  __int64 v122; // rbx
  struct Worker *v123; // rcx
  __int64 v124; // rdx
  volatile signed __int64 *v125; // rbx
  int v126; // r8d
  _QWORD *v127; // rbx
  int v128; // r8d
  __int64 v129; // rdx
  int v130; // r8d
  void *v131; // rcx
  int v132; // r8d
  CSbActivationProcTask *v133; // rbx
  int v134; // esi
  _QWORD *v135; // rdi
  int v136; // r8d
  __int64 v137; // rax
  int v138; // [rsp+20h] [rbp-12E8h]
  int v139; // [rsp+28h] [rbp-12E0h]
  char v140; // [rsp+60h] [rbp-12A8h]
  unsigned __int8 v141; // [rsp+62h] [rbp-12A6h]
  _QWORD *v142; // [rsp+68h] [rbp-12A0h] BYREF
  int v143; // [rsp+70h] [rbp-1298h]
  char v144; // [rsp+78h] [rbp-1290h]
  int v145; // [rsp+7Ch] [rbp-128Ch]
  bool v146; // [rsp+80h] [rbp-1288h]
  int v147; // [rsp+84h] [rbp-1284h]
  __int64 v148; // [rsp+88h] [rbp-1280h]
  unsigned __int16 v149; // [rsp+90h] [rbp-1278h]
  volatile signed __int64 *v150; // [rsp+98h] [rbp-1270h]
  int v151; // [rsp+A0h] [rbp-1268h]
  bool v152; // [rsp+A8h] [rbp-1260h]
  bool v153; // [rsp+A9h] [rbp-125Fh]
  bool v154; // [rsp+B0h] [rbp-1258h]
  bool v155; // [rsp+B8h] [rbp-1250h]
  bool v156; // [rsp+C0h] [rbp-1248h]
  bool v157; // [rsp+C8h] [rbp-1240h]
  bool v158; // [rsp+D0h] [rbp-1238h]
  bool v159; // [rsp+D8h] [rbp-1230h]
  bool v160; // [rsp+E0h] [rbp-1228h]
  bool v161; // [rsp+E8h] [rbp-1220h]
  bool v162; // [rsp+E9h] [rbp-121Fh]
  bool v163; // [rsp+EAh] [rbp-121Eh]
  bool v164; // [rsp+F0h] [rbp-1218h]
  bool v165; // [rsp+F8h] [rbp-1210h]
  bool v166; // [rsp+100h] [rbp-1208h]
  bool v167; // [rsp+108h] [rbp-1200h]
  bool v168; // [rsp+110h] [rbp-11F8h]
  bool v169; // [rsp+118h] [rbp-11F0h]
  bool v170; // [rsp+120h] [rbp-11E8h]
  bool v171; // [rsp+128h] [rbp-11E0h]
  bool v172; // [rsp+130h] [rbp-11D8h]
  bool v173; // [rsp+138h] [rbp-11D0h]
  bool v174; // [rsp+140h] [rbp-11C8h]
  bool v175; // [rsp+148h] [rbp-11C0h]
  bool v176; // [rsp+150h] [rbp-11B8h]
  bool v177; // [rsp+158h] [rbp-11B0h]
  bool v178; // [rsp+160h] [rbp-11A8h]
  bool v179; // [rsp+168h] [rbp-11A0h]
  bool v180; // [rsp+169h] [rbp-119Fh]
  bool v181; // [rsp+16Ah] [rbp-119Eh]
  bool v182; // [rsp+16Bh] [rbp-119Dh]
  bool v183; // [rsp+16Ch] [rbp-119Ch]
  bool v184; // [rsp+16Dh] [rbp-119Bh]
  void **v185; // [rsp+170h] [rbp-1198h] BYREF
  __int64 v186; // [rsp+178h] [rbp-1190h]
  __int64 v187; // [rsp+180h] [rbp-1188h] BYREF
  __int64 v188; // [rsp+188h] [rbp-1180h]
  _BYTE v189[2]; // [rsp+190h] [rbp-1178h] BYREF
  char v190; // [rsp+192h] [rbp-1176h]
  int v191; // [rsp+198h] [rbp-1170h]
  int v192; // [rsp+19Ch] [rbp-116Ch]
  __int16 v193; // [rsp+1A0h] [rbp-1168h]
  __int16 v194; // [rsp+1A8h] [rbp-1160h]
  unsigned int v195; // [rsp+1B0h] [rbp-1158h]
  __int64 v196; // [rsp+1B8h] [rbp-1150h]
  __int64 v197; // [rsp+1C0h] [rbp-1148h]
  CSbActivationProcTask *v198; // [rsp+1C8h] [rbp-1140h]
  __int64 v199; // [rsp+1D0h] [rbp-1138h]
  __int128 v200; // [rsp+1D8h] [rbp-1130h]
  __int128 v201; // [rsp+1E8h] [rbp-1120h]
  int v202; // [rsp+1F8h] [rbp-1110h]
  int v203; // [rsp+1FCh] [rbp-110Ch]
  int v204; // [rsp+200h] [rbp-1108h]
  int v205; // [rsp+208h] [rbp-1100h]
  int v206; // [rsp+210h] [rbp-10F8h]
  int v207; // [rsp+218h] [rbp-10F0h]
  int v208; // [rsp+21Ch] [rbp-10ECh]
  int v209; // [rsp+220h] [rbp-10E8h]
  int v210; // [rsp+228h] [rbp-10E0h]
  int v211; // [rsp+230h] [rbp-10D8h]
  int v212; // [rsp+234h] [rbp-10D4h]
  unsigned int v213; // [rsp+238h] [rbp-10D0h]
  int v214; // [rsp+240h] [rbp-10C8h]
  int v215; // [rsp+248h] [rbp-10C0h]
  int v216; // [rsp+250h] [rbp-10B8h]
  int v217; // [rsp+258h] [rbp-10B0h]
  int v218; // [rsp+260h] [rbp-10A8h]
  int v219; // [rsp+268h] [rbp-10A0h]
  int v220; // [rsp+270h] [rbp-1098h]
  int v221; // [rsp+278h] [rbp-1090h]
  int v222; // [rsp+280h] [rbp-1088h]
  int v223; // [rsp+288h] [rbp-1080h]
  int v224; // [rsp+290h] [rbp-1078h]
  unsigned int v225; // [rsp+294h] [rbp-1074h]
  unsigned int v226; // [rsp+298h] [rbp-1070h]
  int v227; // [rsp+29Ch] [rbp-106Ch]
  int v228; // [rsp+2A0h] [rbp-1068h]
  __int64 v229; // [rsp+2A8h] [rbp-1060h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+2B0h] [rbp-1058h] BYREF
  LARGE_INTEGER v231; // [rsp+2B8h] [rbp-1050h] BYREF
  LARGE_INTEGER v232; // [rsp+2C0h] [rbp-1048h] BYREF
  LARGE_INTEGER v233; // [rsp+2C8h] [rbp-1040h] BYREF
  unsigned __int64 v234; // [rsp+2D0h] [rbp-1038h] BYREF
  unsigned __int64 v235; // [rsp+2D8h] [rbp-1030h] BYREF
  int v236; // [rsp+2E0h] [rbp-1028h]
  int v237; // [rsp+2E8h] [rbp-1020h]
  void *v238; // [rsp+2F0h] [rbp-1018h]
  struct CActiveServiceBroker *v239; // [rsp+2F8h] [rbp-1010h]
  int v240; // [rsp+300h] [rbp-1008h]
  int v241; // [rsp+304h] [rbp-1004h]
  int v242; // [rsp+308h] [rbp-1000h]
  _DWORD v243[8]; // [rsp+310h] [rbp-FF8h] BYREF
  void **v244; // [rsp+330h] [rbp-FD8h] BYREF
  void ***v245; // [rsp+338h] [rbp-FD0h]
  int v246; // [rsp+340h] [rbp-FC8h]
  __int64 v247; // [rsp+348h] [rbp-FC0h]
  __int64 v248; // [rsp+350h] [rbp-FB8h]
  __int64 v249; // [rsp+358h] [rbp-FB0h]
  __int64 v250; // [rsp+360h] [rbp-FA8h]
  char v251; // [rsp+368h] [rbp-FA0h]
  __int64 v252; // [rsp+370h] [rbp-F98h]
  char v253; // [rsp+380h] [rbp-F88h]
  __int64 v254; // [rsp+388h] [rbp-F80h]
  __int64 v255; // [rsp+390h] [rbp-F78h]
  unsigned __int64 v256; // [rsp+398h] [rbp-F70h]
  _WORD *v257; // [rsp+3A0h] [rbp-F68h]
  unsigned __int64 **v258; // [rsp+3A8h] [rbp-F60h]
  _QWORD *v259; // [rsp+3B0h] [rbp-F58h]
  _QWORD *v260; // [rsp+3B8h] [rbp-F50h]
  __int64 v261; // [rsp+3C0h] [rbp-F48h]
  __int64 v262; // [rsp+3C8h] [rbp-F40h]
  unsigned __int64 v263; // [rsp+3D0h] [rbp-F38h]
  _WORD *v264; // [rsp+3D8h] [rbp-F30h]
  unsigned __int64 **v265; // [rsp+3E0h] [rbp-F28h]
  _QWORD *v266; // [rsp+3E8h] [rbp-F20h]
  _QWORD *v267; // [rsp+3F0h] [rbp-F18h]
  _QWORD *v268; // [rsp+3F8h] [rbp-F10h]
  __int64 v269; // [rsp+400h] [rbp-F08h]
  __int64 v270; // [rsp+408h] [rbp-F00h]
  __int64 v271; // [rsp+410h] [rbp-EF8h]
  _QWORD *v272; // [rsp+418h] [rbp-EF0h]
  _QWORD *v273; // [rsp+420h] [rbp-EE8h]
  _QWORD *v274; // [rsp+428h] [rbp-EE0h]
  __int64 v275; // [rsp+430h] [rbp-ED8h]
  __int64 v276; // [rsp+438h] [rbp-ED0h]
  __int64 v277; // [rsp+440h] [rbp-EC8h]
  __int64 v278; // [rsp+448h] [rbp-EC0h]
  _QWORD *v279; // [rsp+450h] [rbp-EB8h]
  const struct CCompExecCtxtBasic **v280; // [rsp+458h] [rbp-EB0h]
  const struct CCompExecCtxtBasic **v281; // [rsp+460h] [rbp-EA8h]
  const struct CCompExecCtxtBasic *v282; // [rsp+468h] [rbp-EA0h]
  const struct CCompExecCtxtBasic *v283; // [rsp+470h] [rbp-E98h]
  __int64 v284; // [rsp+478h] [rbp-E90h]
  _QWORD *v285; // [rsp+480h] [rbp-E88h]
  const struct CCompExecCtxtBasic **v286; // [rsp+488h] [rbp-E80h]
  const struct CCompExecCtxtBasic **v287; // [rsp+490h] [rbp-E78h]
  const struct CCompExecCtxtBasic *v288; // [rsp+498h] [rbp-E70h]
  const struct CCompExecCtxtBasic *v289; // [rsp+4A0h] [rbp-E68h]
  _QWORD *v290; // [rsp+4A8h] [rbp-E60h]
  _QWORD *v291; // [rsp+4B0h] [rbp-E58h]
  _QWORD *v292; // [rsp+4B8h] [rbp-E50h]
  __int64 v293; // [rsp+4C0h] [rbp-E48h]
  __int64 v294; // [rsp+4C8h] [rbp-E40h]
  __int64 v295; // [rsp+4D0h] [rbp-E38h]
  __int64 v296; // [rsp+4D8h] [rbp-E30h]
  _QWORD *v297; // [rsp+4E0h] [rbp-E28h]
  const struct CCompExecCtxtBasic **v298; // [rsp+4E8h] [rbp-E20h]
  const struct CCompExecCtxtBasic **v299; // [rsp+4F0h] [rbp-E18h]
  const struct CCompExecCtxtBasic *v300; // [rsp+4F8h] [rbp-E10h]
  const struct CCompExecCtxtBasic *v301; // [rsp+500h] [rbp-E08h]
  __int64 v302; // [rsp+508h] [rbp-E00h]
  _QWORD *v303; // [rsp+510h] [rbp-DF8h]
  _QWORD *v304; // [rsp+518h] [rbp-DF0h]
  _QWORD *v305; // [rsp+520h] [rbp-DE8h]
  __int64 v306; // [rsp+528h] [rbp-DE0h]
  __int64 v307; // [rsp+530h] [rbp-DD8h]
  _QWORD *v308; // [rsp+538h] [rbp-DD0h]
  _QWORD *v309; // [rsp+540h] [rbp-DC8h]
  __int64 v310; // [rsp+548h] [rbp-DC0h]
  __int64 *v311; // [rsp+550h] [rbp-DB8h]
  __int64 *v312; // [rsp+558h] [rbp-DB0h]
  __int64 v313; // [rsp+560h] [rbp-DA8h]
  __int64 v314; // [rsp+568h] [rbp-DA0h]
  _QWORD *v315; // [rsp+570h] [rbp-D98h]
  _QWORD *v316; // [rsp+578h] [rbp-D90h]
  __int64 v317; // [rsp+580h] [rbp-D88h]
  __int64 v318; // [rsp+588h] [rbp-D80h]
  char *v319; // [rsp+590h] [rbp-D78h]
  _QWORD *v320; // [rsp+598h] [rbp-D70h]
  _QWORD *v321; // [rsp+5A0h] [rbp-D68h]
  __int64 v322; // [rsp+5A8h] [rbp-D60h]
  __int64 v323; // [rsp+5B0h] [rbp-D58h]
  _QWORD *v324; // [rsp+5B8h] [rbp-D50h]
  _QWORD *v325; // [rsp+5C0h] [rbp-D48h]
  __int64 v326; // [rsp+5C8h] [rbp-D40h]
  _QWORD *v327; // [rsp+5D0h] [rbp-D38h]
  __int64 v328; // [rsp+5D8h] [rbp-D30h]
  _QWORD *v329; // [rsp+5E0h] [rbp-D28h]
  char *v330; // [rsp+5E8h] [rbp-D20h]
  _QWORD *v331; // [rsp+5F0h] [rbp-D18h]
  _QWORD *v332; // [rsp+5F8h] [rbp-D10h]
  __int64 v333; // [rsp+600h] [rbp-D08h]
  __int64 v334; // [rsp+608h] [rbp-D00h]
  _WORD *v335; // [rsp+610h] [rbp-CF8h]
  __int64 v336; // [rsp+618h] [rbp-CF0h]
  _QWORD *v337; // [rsp+620h] [rbp-CE8h]
  _QWORD *v338; // [rsp+628h] [rbp-CE0h]
  _QWORD *v339; // [rsp+630h] [rbp-CD8h]
  _QWORD *v340; // [rsp+638h] [rbp-CD0h]
  __int64 v341; // [rsp+640h] [rbp-CC8h]
  __int64 v342; // [rsp+648h] [rbp-CC0h]
  _QWORD *v343; // [rsp+650h] [rbp-CB8h]
  _QWORD *v344; // [rsp+658h] [rbp-CB0h]
  __int64 v345; // [rsp+660h] [rbp-CA8h]
  _QWORD *v346; // [rsp+668h] [rbp-CA0h]
  _QWORD *v347; // [rsp+670h] [rbp-C98h]
  __int64 v348; // [rsp+678h] [rbp-C90h]
  __int64 v349; // [rsp+680h] [rbp-C88h]
  _QWORD *v350; // [rsp+688h] [rbp-C80h]
  _QWORD *v351; // [rsp+690h] [rbp-C78h]
  _QWORD *v352; // [rsp+698h] [rbp-C70h]
  _QWORD *v353; // [rsp+6A0h] [rbp-C68h]
  __int64 v354; // [rsp+6A8h] [rbp-C60h]
  __int64 v355; // [rsp+6B0h] [rbp-C58h]
  __int64 v356; // [rsp+6B8h] [rbp-C50h]
  __int64 v357; // [rsp+6C0h] [rbp-C48h]
  _QWORD *v358; // [rsp+6C8h] [rbp-C40h]
  __int64 v359; // [rsp+6D0h] [rbp-C38h]
  _QWORD *v360; // [rsp+6D8h] [rbp-C30h]
  _QWORD *v361; // [rsp+6E0h] [rbp-C28h]
  __int64 v362; // [rsp+6E8h] [rbp-C20h]
  __int64 v363; // [rsp+6F0h] [rbp-C18h]
  _QWORD *v364; // [rsp+6F8h] [rbp-C10h]
  _QWORD *v365; // [rsp+700h] [rbp-C08h]
  _QWORD *v366; // [rsp+708h] [rbp-C00h]
  _QWORD *v367; // [rsp+710h] [rbp-BF8h]
  __int64 v368; // [rsp+718h] [rbp-BF0h]
  __int64 v369; // [rsp+720h] [rbp-BE8h]
  __int64 v370; // [rsp+728h] [rbp-BE0h]
  _QWORD *v371; // [rsp+730h] [rbp-BD8h]
  _QWORD *v372; // [rsp+738h] [rbp-BD0h]
  __int64 v373; // [rsp+740h] [rbp-BC8h]
  __int64 v374; // [rsp+748h] [rbp-BC0h]
  _QWORD *v375; // [rsp+750h] [rbp-BB8h]
  _QWORD *v376; // [rsp+758h] [rbp-BB0h]
  __int64 v377; // [rsp+760h] [rbp-BA8h]
  _QWORD *v378; // [rsp+768h] [rbp-BA0h]
  _QWORD *v379; // [rsp+770h] [rbp-B98h]
  _QWORD *v380; // [rsp+778h] [rbp-B90h]
  _QWORD *v381; // [rsp+780h] [rbp-B88h]
  _QWORD *v382; // [rsp+788h] [rbp-B80h]
  __int64 v383; // [rsp+790h] [rbp-B78h]
  __int64 v384; // [rsp+798h] [rbp-B70h]
  __int64 v385; // [rsp+7A0h] [rbp-B68h]
  __int64 v386; // [rsp+7A8h] [rbp-B60h]
  __int64 v387; // [rsp+7B0h] [rbp-B58h]
  __int64 v388; // [rsp+7B8h] [rbp-B50h]
  _QWORD v389[6]; // [rsp+7C0h] [rbp-B48h] BYREF
  _BYTE v390[40]; // [rsp+7F0h] [rbp-B18h] BYREF
  _BYTE v391[56]; // [rsp+818h] [rbp-AF0h] BYREF
  _BYTE v392[8]; // [rsp+850h] [rbp-AB8h] BYREF
  _WORD v393[4]; // [rsp+858h] [rbp-AB0h] BYREF
  int v394; // [rsp+860h] [rbp-AA8h]
  unsigned __int64 **v395; // [rsp+868h] [rbp-AA0h]
  char *v396; // [rsp+870h] [rbp-A98h]
  __int64 v397; // [rsp+878h] [rbp-A90h]
  unsigned __int64 *v398; // [rsp+880h] [rbp-A88h] BYREF
  int v399; // [rsp+888h] [rbp-A80h]
  __int16 v400; // [rsp+88Ch] [rbp-A7Ch]
  __int16 v401; // [rsp+88Eh] [rbp-A7Ah]
  char v402; // [rsp+890h] [rbp-A78h] BYREF
  int v403; // [rsp+AA0h] [rbp-868h]
  int v404; // [rsp+AA4h] [rbp-864h]
  __int64 v405; // [rsp+AA8h] [rbp-860h]
  unsigned __int64 v406; // [rsp+AB0h] [rbp-858h] BYREF
  int v407; // [rsp+AB8h] [rbp-850h]
  _BYTE v408[8]; // [rsp+AC0h] [rbp-848h] BYREF
  _WORD v409[4]; // [rsp+AC8h] [rbp-840h] BYREF
  int v410; // [rsp+AD0h] [rbp-838h]
  unsigned __int64 **v411; // [rsp+AD8h] [rbp-830h]
  char *v412; // [rsp+AE0h] [rbp-828h]
  __int64 v413; // [rsp+AE8h] [rbp-820h]
  unsigned __int64 *v414; // [rsp+AF0h] [rbp-818h] BYREF
  int v415; // [rsp+AF8h] [rbp-810h]
  __int16 v416; // [rsp+AFCh] [rbp-80Ch]
  __int16 v417; // [rsp+AFEh] [rbp-80Ah]
  char v418; // [rsp+B00h] [rbp-808h] BYREF
  int v419; // [rsp+D10h] [rbp-5F8h]
  int v420; // [rsp+D14h] [rbp-5F4h]
  __int64 v421; // [rsp+D18h] [rbp-5F0h]
  unsigned __int64 v422; // [rsp+D20h] [rbp-5E8h] BYREF
  int v423; // [rsp+D28h] [rbp-5E0h]
  _BYTE v424[1440]; // [rsp+D30h] [rbp-5D8h] BYREF

  v386 = -2;
  v1 = this;
  v198 = this;
  v145 = 0;
  v142 = 0;
  v143 = 0;
  v2 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset)
                 + 72LL);
  if ( v2 )
    v3 = *(_WORD *)(v2 + 16);
  else
    v3 = 0;
  *((_DWORD *)v1 + 26) = v3;
  *((_WORD *)v1 + 54) = v3;
  v229 = *(_QWORD *)(*((_QWORD *)v1 + 8) + 80LL);
  ActiveBrokerById = CActiveServiceBrokerMgr::GetActiveBrokerById(
                       (CActiveServiceBrokerMgr *)(*(_QWORD *)(qword_102ECFB00 + 43248) + 26664LL),
                       (const struct CSbAsbId *)&v229);
  v239 = ActiveBrokerById;
  if ( ActiveBrokerById
    && (!*(_DWORD *)(GetXdbServerGlobals(v5, v4) + 11976) || byte_102EDCE86)
    && *((_DWORD *)ActiveBrokerById + 114) == 1
    && (v7 = *(_QWORD *)(qword_102ECFB00 + 43248), *(_DWORD *)(v7 + 80) != 3)
    && *(_DWORD *)(v7 + 80)
    && !*((_BYTE *)ActiveBrokerById + 231) )
  {
    v149 = *((_WORD *)ActiveBrokerById + 102);
    v195 = *(_DWORD *)(*((_QWORD *)v1 + 8) + 88LL);
    v150 = (volatile signed __int64 *)(*(_QWORD *)(qword_102ECFB00 + 43248) + 25144LL);
    v151 = 0;
    for ( *((_QWORD *)v1 + 18) = 0; ; operator delete[](*((void **)v1 + 18)) )
    {
      QuadPart = 0;
      UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)v150 || _InterlockedCompareExchange64(v150, UniqueThread_low, 0) )
      {
        v10 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v11 && *(_QWORD *)(v11 + 272) == v11 )
            v10 = *(_QWORD *)(v11 + 256);
          if ( v10 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&PerformanceCount);
              QuadPart = (CSbTransportMgr *)PerformanceCount.QuadPart;
            }
            else
            {
              QuadPart = MEMORY[0x7FFE0008];
            }
          }
        }
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v150, UniqueThread_low);
        else
          Spinlock<170,8,258>::SpinToAcquireOptimistic(v150, v10, UniqueThread_low);
        if ( v10 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v231);
            v12 = (CSbTransportMgr *)v231.QuadPart;
          }
          else
          {
            v12 = MEMORY[0x7FFE0008];
          }
          if ( v12 < QuadPart )
            v13 = 0;
          else
            v13 = v12 - QuadPart;
          *(_QWORD *)(v10 + 3192) += v13;
        }
      }
      v151 = 1;
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)v1 + 8) + 96LL) + 2 * v14) );
      v15 = 2 * v14;
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v16 = rand();
        if ( v16 == 5 * (v16 / 5) )
          Spinlock<170,8,258>::UpdateStatSnapshot();
      }
      *v150 = 0;
      v151 = 0;
      v17 = (v15 >> 1) + 1;
      v18 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v19 = *(_QWORD *)(v18 + 256);
      if ( !v19 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v19 = *(_QWORD *)(v18 + 256);
      }
      v20 = v17;
      v21 = 2LL * v17;
      if ( !is_mul_ok(v17, 2u) )
        v21 = -1;
      v22 = operator new[](
              v21,
              *(struct IMemObj **)(v19 + 1000),
              "sql\\ntdbms\\broker\\src\\ssbInternalActivation.cpp",
              1844,
              8u);
      v188 = (__int64)v22;
      v23 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v24 = *(_QWORD *)(v23 + 256);
      if ( !v24 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v24 = *(_QWORD *)(v23 + 256);
      }
      v25 = 2 * v20;
      if ( !is_mul_ok(v20, 2u) )
        v25 = -1;
      *((_QWORD *)v1 + 18) = operator new[](
                               v25,
                               *(struct IMemObj **)(v24 + 1000),
                               "sql\\ntdbms\\broker\\src\\ssbInternalActivation.cpp",
                               1845,
                               8u);
      v26 = 0;
      v27 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)v150 || _InterlockedCompareExchange64(v150, v27, 0) )
      {
        v28 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v29 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v29 && *(_QWORD *)(v29 + 272) == v29 )
            v28 = *(_QWORD *)(v29 + 256);
          if ( v28 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v232);
              v26 = (CSbTransportMgr *)v232.QuadPart;
            }
            else
            {
              v26 = MEMORY[0x7FFE0008];
            }
          }
        }
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v150, v27);
        else
          Spinlock<170,8,258>::SpinToAcquireOptimistic(v150, v28, v27);
        if ( v28 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v233);
            v30 = (CSbTransportMgr *)v233.QuadPart;
          }
          else
          {
            v30 = MEMORY[0x7FFE0008];
          }
          if ( v30 < v26 )
            v31 = 0;
          else
            v31 = v30 - v26;
          *(_QWORD *)(v28 + 3192) += v31;
        }
        v22 = (void *)v188;
      }
      v151 = 1;
      v32 = *(const wchar_t **)(*((_QWORD *)v1 + 8) + 96LL);
      v33 = -1;
      do
        ++v33;
      while ( v32[v33] );
      if ( v15 == 2 * (_DWORD)v33 )
        break;
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v128 = rand();
        if ( v128 == 5 * (v128 / 5) )
          Spinlock<170,8,258>::UpdateStatSnapshot();
      }
      *v150 = 0;
      v151 = 0;
      operator delete[](v22);
    }
    v34 = CbParseQuotesW(v32, v15, (wchar_t *)v22, v15);
    v35 = (_WORD *)*((_QWORD *)v1 + 18);
    if ( v20 <= 0x7FFFFFFF )
    {
      v36 = 2147483646 - v20;
      v37 = *(_QWORD *)(*((_QWORD *)v1 + 8) + 96LL) - (_QWORD)v35;
      do
      {
        if ( !(v20 + v36) )
          break;
        v38 = *(_WORD *)((char *)v35 + v37);
        if ( !v38 )
          break;
        *v35++ = v38;
        --v20;
      }
      while ( v20 );
      v39 = v35 - 1;
      if ( v20 )
        v39 = v35;
      *v39 = 0;
    }
    else
    {
      *v35 = 0;
    }
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v40 = rand();
      if ( v40 == 5 * (v40 / 5) )
        Spinlock<170,8,258>::UpdateStatSnapshot();
    }
    *v150 = 0;
    v151 = 0;
    v238 = v22;
    WParseName::Parse((WParseName *)v391, (const wchar_t *)v22, v34);
    v245 = 0;
    v246 = 0;
    v247 = 0;
    v248 = 0;
    v249 = 0;
    v250 = 0;
    v251 = 1;
    v252 = 0;
    v253 = 1;
    v244 = &CSbActivationTaskExceptions::`vftable';
    v254 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                               + SystemThread_TlsIndex)
                                             + SystemThread_TlsOffset)
                                 + 128LL)
                     + 256LL);
    v41 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset)
                    + 112LL);
    v200 = 0;
    v201 = 0;
    v42 = *(void ****)(v41 + 24);
    if ( v42 != &v244 )
    {
      *(_QWORD *)&v200 = v41;
      *((_QWORD *)&v200 + 1) = v42;
      *(_QWORD *)&v201 = v245;
      *((_QWORD *)&v201 + 1) = &v244;
      v245 = v42;
      *(_QWORD *)(v41 + 24) = &v244;
    }
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v390, 0, 0, 0, (int (*)(int, int, int, int, char *))MSQLErrorHandlerFunc, 0);
      CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v142);
      v43 = *((_QWORD *)v1 + 8);
      v387 = v43;
      v388 = v43 + 208;
      v225 = *((_DWORD *)v1 + 26);
      v226 = *(_DWORD *)(v43 + 220) & (v225 + (v225 >> 20) + (v225 >> 10));
      v44 = *(_QWORD *)(v43 + 208) + 16LL * v226;
      v389[2] = v44;
      v389[3] = (char *)v1 + 88;
      v389[4] = v44;
      *((_QWORD *)v1 + 12) = *(_QWORD *)(v44 + 8);
      **(_QWORD **)(v44 + 8) = (char *)v1 + 88;
      *(_QWORD *)(v44 + 8) = (char *)v1 + 88;
      *((_QWORD *)v1 + 11) = v44;
      ++*(_DWORD *)(v43 + 224);
      v180 = CommonGlobalState::m_CollectingStatistics;
      if ( CommonGlobalState::m_CollectingStatistics && *(_BYTE *)(v43 + 244) )
      {
        v181 = CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
        {
          v389[5] = 1;
          v255 = qword_102ECFB00;
          v45 = PerfmonManager::IncrementCounterInstanceValue(
                  (PerfmonManager *)qword_102ECFB00,
                  0x1Fu,
                  0,
                  1,
                  *(unsigned __int16 *)(v43 + 116),
                  &v234);
          v227 = v45;
          v46 = *(unsigned __int16 *)(v43 + 116);
          v228 = v46;
          v256 = v234;
          v188 = 0x800000000LL;
          if ( (g_XeSqlPkg_enabledBitmap & 8) != 0 )
          {
            if ( v45 )
            {
              v194 = 1;
              v257 = v393;
              v393[0] = 0;
              v393[1] = 1;
              v394 = 0;
              v395 = &v398;
              v396 = &v402;
              v403 = 0;
              v404 = 0;
              v397 = 0;
              v405 = 0;
              v258 = &v398;
              v398 = &v406;
              v399 = 12;
              v400 = 0;
              v401 = 0;
              v406 = v234;
              v407 = v46;
              XeSqlPkg::broker_activation_task_started::Publish((XeSqlPkg::broker_activation_task_started *)v392);
            }
          }
        }
        v182 = CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
          PerfmonManager::IncrementCounterInstanceValue(
            (PerfmonManager *)qword_102ECFB00,
            0x1Fu,
            8u,
            1,
            *(unsigned __int16 *)(v43 + 116),
            0);
      }
      v47 = *(_DWORD *)(v43 + 128);
      v145 = v47;
      v48 = v142;
      v259 = v142;
      v183 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v49 = rand();
        if ( v49 == 5 * (v49 / 5) )
          Spinlock<165,9,258>::UpdateStatSnapshot();
      }
      v260 = v48;
      *v48 = 0;
      v143 = 0;
      v142 = 0;
      v50 = v149;
      v140 = SsbActivationTraceEvent((CSbActivationProcTask *)((char *)v1 + 152), v47, 0, 0, 1);
      while ( 1 )
      {
        v141 = 0;
        CSQLObject::CSQLObject((CSQLObject *)v424, (const struct WParseName *)v391, 1, 0, 1);
        v184 = CommonGlobalState::m_CollectingStatistics;
        if ( CommonGlobalState::m_CollectingStatistics )
        {
          v51 = *((_QWORD *)v1 + 8);
          if ( *(_BYTE *)(v51 + 244) )
          {
            v152 = CommonGlobalState::m_PerfCountersEnabled;
            if ( CommonGlobalState::m_PerfCountersEnabled )
            {
              v261 = 1;
              v262 = qword_102ECFB00;
              v52 = PerfmonManager::IncrementCounterInstanceValue(
                      (PerfmonManager *)qword_102ECFB00,
                      0x1Fu,
                      0x28u,
                      1,
                      *(unsigned __int16 *)(v51 + 116),
                      &v235);
              v236 = v52;
              v53 = *(unsigned __int16 *)(*((_QWORD *)v1 + 8) + 116LL);
              v237 = v53;
              v263 = v235;
              v191 = 0;
              v192 = 1;
              if ( (g_XeSqlPkg_enabledBitmap & 1) != 0 )
              {
                if ( v52 )
                {
                  v193 = 1;
                  v264 = v409;
                  v409[0] = 0;
                  v409[1] = 1;
                  v410 = 0;
                  v411 = &v414;
                  v412 = &v418;
                  v419 = 0;
                  v420 = 0;
                  v413 = 0;
                  v421 = 0;
                  v265 = &v414;
                  v414 = &v422;
                  v415 = 12;
                  v416 = 0;
                  v417 = 0;
                  v422 = v235;
                  v423 = v53;
                  XeSqlPkg::broker_activation_stored_procedure_invoked::Publish((XeSqlPkg::broker_activation_stored_procedure_invoked *)v408);
                }
              }
            }
          }
        }
        v240 = 88;
        ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
        v266 = ThreadLocalStoragePointer;
        v267 = (_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v268 = v267;
        v269 = *v267;
        v270 = v269;
        v55 = *(_QWORD *)(v269 + 128);
        v148 = v55;
        v147 = 0x400000;
        v56 = *(unsigned int *)(v55 + 80);
        v146 = (*(_DWORD *)(v55 + 80) & 0x400000) != 0;
        v271 = v55;
        LODWORD(v56) = v56 | 0x400000;
        *(_DWORD *)(v55 + 80) = v56;
        v58 = *(unsigned int *)(GetXdbServerGlobals(v56, ThreadLocalStoragePointer) + 8308);
        v241 = v58;
        if ( (_DWORD)v58 )
        {
          v242 = 88;
          v272 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v273 = (_QWORD *)(v272[SystemThread_TlsIndex] + SystemThread_TlsOffset);
          v274 = v273;
          v275 = *v273;
          v276 = v275;
          v59 = *(_QWORD *)(v275 + 72);
          v277 = v59;
          v196 = v59;
          v60 = *(_BYTE *)(v59 + 270);
          if ( (v60 & 4) != 0 )
          {
            v196 = 0;
          }
          else
          {
            v278 = v59;
            *(_BYTE *)(v59 + 270) = v60 | 4;
            *(_BYTE *)(v59 + 271) |= 1u;
            *(_DWORD *)(v59 + 404) = 1;
          }
          v243[6] = 88;
          v279 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v280 = (const struct CCompExecCtxtBasic **)(v279[SystemThread_TlsIndex] + SystemThread_TlsOffset);
          v281 = v280;
          v282 = *v280;
          v283 = v282;
          CSQLSource::Execute((CSQLSource *)v424, v282, 0, 0);
          v61 = v196;
          if ( v196 )
          {
            v284 = v196;
            *(_BYTE *)(v196 + 270) &= ~4u;
            *(_BYTE *)(v61 + 271) &= ~1u;
            *(_DWORD *)(v61 + 404) = 2;
          }
        }
        else
        {
          XdbServerGlobals = GetXdbServerGlobals(v58, v57);
          v63 = NtCurrentTeb()->ThreadLocalStoragePointer;
          if ( *(_DWORD *)(XdbServerGlobals + 11976) )
          {
            v202 = 88;
            v290 = v63;
            v291 = (_QWORD *)(v63[SystemThread_TlsIndex] + SystemThread_TlsOffset);
            v292 = v291;
            v293 = *v291;
            v294 = v293;
            v64 = *(_QWORD *)(v293 + 72);
            v295 = v64;
            v197 = v64;
            v65 = *(_BYTE *)(v64 + 270);
            if ( (v65 & 0x10) != 0 )
            {
              v197 = 0;
            }
            else
            {
              v296 = v64;
              *(_BYTE *)(v64 + 270) = v65 | 0x10;
              *(_BYTE *)(v64 + 271) |= 2u;
            }
            v203 = 88;
            v297 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v298 = (const struct CCompExecCtxtBasic **)(v297[SystemThread_TlsIndex] + SystemThread_TlsOffset);
            v299 = v298;
            v300 = *v298;
            v301 = v300;
            CSQLSource::Execute((CSQLSource *)v424, v300, 0, 0);
            v66 = v197;
            if ( v197 )
            {
              v302 = v197;
              *(_BYTE *)(v197 + 270) &= ~0x10u;
              *(_BYTE *)(v66 + 271) &= ~2u;
            }
          }
          else
          {
            v243[7] = 88;
            v285 = v63;
            v286 = (const struct CCompExecCtxtBasic **)(v63[SystemThread_TlsIndex] + SystemThread_TlsOffset);
            v287 = v286;
            v288 = *v286;
            v289 = v288;
            CSQLSource::Execute((CSQLSource *)v424, v288, 0, 0);
          }
        }
        v204 = 88;
        v303 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v304 = (_QWORD *)(v303[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v305 = v304;
        v306 = *v304;
        v307 = v306;
        v199 = v306;
        v199 = *(_QWORD *)(v306 + 144);
        if ( (*(int (**)(void))(*(_QWORD *)v199 + 624LL))() > 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v199 + 32LL))(v199);
          CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v142);
          v67 = CSbQueueMonitor::ActivatedTaskAborting(*((_QWORD *)v1 + 8), v1, 0, 4);
          v145 = v67;
          v68 = v142;
          v308 = v142;
          v153 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v69 = rand();
            if ( v69 == 5 * (v69 / 5) )
              Spinlock<165,9,258>::UpdateStatSnapshot();
          }
          v309 = v68;
          *v68 = 0;
          v143 = 0;
          v142 = 0;
          if ( v140 )
            SsbActivationTraceEvent_0(0, v67, 8415, 10, 1, 0);
          v154 = v146;
          v205 = 0x400000;
          v310 = v148;
          v70 = *(_DWORD *)(v55 + 80);
          if ( v146 )
          {
            *(_DWORD *)(v55 + 80) = v70 | 0x400000;
            goto LABEL_223;
          }
          goto LABEL_201;
        }
        v185 = &AutoReadOnlyIMA::`vftable';
        v186 = 0;
        v311 = &v187;
        v312 = &v187;
        v187 = 0;
        AutoReadOnlyIMA::Init((AutoReadOnlyIMA *)&v185, L"CSbActivationProcTask::Invoke", 0x3Au, 0);
        v71 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v186 + 56LL))(
                v186,
                v50,
                0,
                0,
                0,
                0);
        LOBYTE(v139) = 1;
        LOBYTE(v138) = 0;
        LOBYTE(v72) = 1;
        v73 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int, int, _DWORD, _DWORD))(*(_QWORD *)v71 + 120LL))(
                v71,
                v195,
                v72,
                0,
                v138,
                v139,
                0,
                0);
        v313 = v73;
        if ( !v73 )
        {
          CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v142);
          v74 = *((_QWORD *)v1 + 8);
          v314 = v74;
          if ( *(_DWORD *)(v74 + 128) == ++*(_DWORD *)(v74 + 132) )
            *(_BYTE *)(v74 + 242) = 1;
          v75 = CSbQueueMonitor::ActivatedTaskEnded(*((_QWORD *)v1 + 8), v1, 4);
          v145 = v75;
          v76 = v142;
          v315 = v142;
          v155 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v77 = rand();
            if ( v77 == 5 * (v77 / 5) )
              Spinlock<165,9,258>::UpdateStatSnapshot();
          }
          v316 = v76;
          *v76 = 0;
          v143 = 0;
          v142 = 0;
          if ( v140 )
            SsbActivationTraceEvent_0((CSbActivationProcTask *)((char *)v1 + 152), v75, 28085, 10, 1, 0);
          AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v185);
          v78 = v146;
          v156 = v146;
          v206 = 0x400000;
          v317 = v148;
LABEL_134:
          v70 = *(_DWORD *)(v55 + 80);
          if ( v78 )
          {
            *(_DWORD *)(v55 + 80) = v70 | 0x400000;
            goto LABEL_223;
          }
LABEL_201:
          *(_DWORD *)(v55 + 80) = v70 & 0xFFBFFFFF;
          goto LABEL_223;
        }
        v318 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v73 + 192LL))(v73);
        (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v318 + 8LL))(v318, v189);
        if ( (v190 & 1) == 0 || (v190 & 2) == 0 )
        {
          CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v142);
          v118 = *((_QWORD *)v1 + 8);
          v374 = v118;
          if ( *(_DWORD *)(v118 + 128) == ++*(_DWORD *)(v118 + 132) )
            *(_BYTE *)(v118 + 242) = 1;
          v119 = CSbQueueMonitor::ActivatedTaskEnded(*((_QWORD *)v1 + 8), v1, 4);
          v145 = v119;
          v120 = v142;
          v375 = v142;
          v177 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v121 = rand();
            if ( v121 == 5 * (v121 / 5) )
              Spinlock<165,9,258>::UpdateStatSnapshot();
          }
          v376 = v120;
          *v120 = 0;
          v143 = 0;
          v142 = 0;
          if ( v140 )
            SsbActivationTraceEvent_0((CSbActivationProcTask *)((char *)v1 + 152), v119, 28086, 10, 1, 0);
          AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v185);
          v116 = v146;
          v178 = v146;
          v223 = 0x400000;
          v117 = v148;
          v377 = v148;
          goto LABEL_220;
        }
        v207 = 88;
        v319 = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
        v79 = 8LL * SystemThread_TlsIndex;
        v320 = (_QWORD *)(SystemThread_TlsOffset + *(_QWORD *)&v319[v79]);
        v321 = v320;
        v322 = *v320;
        v323 = v322;
        v80 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v322 + 128) + 256LL) + 4LL);
        v208 = v80;
        if ( !v80 )
        {
          CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v142);
          v81 = CSbQueueMonitor::ActivatedTaskAborting(*((_QWORD *)v1 + 8), v1, 0, 4);
          v145 = v81;
          v82 = v142;
          v324 = v142;
          v157 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v83 = rand();
            if ( v83 == 5 * (v83 / 5) )
              Spinlock<165,9,258>::UpdateStatSnapshot();
          }
          v325 = v82;
          *v82 = 0;
          v143 = 0;
          v142 = 0;
          if ( v140 )
            SsbActivationTraceEvent_0(0, v81, 28087, 10, 1, 0);
          AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v185);
          v78 = v146;
          v158 = v146;
          v209 = 0x400000;
          v326 = v148;
          goto LABEL_134;
        }
        if ( v80 == 2 )
        {
          CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v142);
          v84 = v142;
          if ( *(_DWORD *)(*((_QWORD *)v1 + 8) + 128LL) <= *(__int16 *)(*((_QWORD *)v1 + 8) + 112LL) )
          {
            v327 = v142;
            v159 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v85 = rand();
              if ( v85 == 5 * (v85 / 5) )
                Spinlock<165,9,258>::UpdateStatSnapshot();
            }
            *v84 = 0;
            v143 = 0;
            v142 = 0;
            AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v185);
            v160 = v146;
            v210 = 0x400000;
            v328 = v148;
            v86 = *(_DWORD *)(v55 + 80);
            if ( v146 )
              v87 = v86 | 0x400000;
            else
              v87 = v86 & 0xFFBFFFFF;
            goto LABEL_153;
          }
          v329 = v142;
          v161 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v88 = rand();
            if ( v88 == 5 * (v88 / 5) )
              Spinlock<165,9,258>::UpdateStatSnapshot();
          }
          *v84 = 0;
          v143 = 0;
          v142 = 0;
        }
        else
        {
          v211 = 88;
          v330 = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
          v331 = (_QWORD *)(SystemThread_TlsOffset + *(_QWORD *)&v330[v79]);
          v332 = v331;
          v333 = *v331;
          v334 = v333;
          v335 = *(_WORD **)(*(_QWORD *)(v333 + 128) + 256LL);
          ++*v335;
        }
        v144 = 0;
        CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v142);
        v89 = *((_QWORD *)v1 + 8);
        v336 = v89;
        v90 = *(_DWORD *)(v89 + 128) == ++*(_DWORD *)(v89 + 132);
        if ( *(_DWORD *)(v89 + 128) == *(_DWORD *)(v89 + 132) )
          *(_BYTE *)(v89 + 242) = 1;
        v91 = v142;
        v337 = v142;
        v162 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v92 = rand();
          if ( v92 == 5 * (v92 / 5) )
            Spinlock<165,9,258>::UpdateStatSnapshot();
        }
        *v91 = 0;
        v143 = 0;
        v142 = 0;
        v141 = 1;
        v144 = 1;
        if ( !v90 )
          break;
        v212 = 88;
        v338 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v339 = (_QWORD *)(v338[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v340 = v339;
        v341 = *v339;
        v342 = v341;
        v93 = *((_QWORD *)v1 + 8);
        if ( **(_WORD **)(*(_QWORD *)(v341 + 128) + 256LL) >= 2u )
        {
          CSbQueueMonitor::GetSpinLock(v93, &v142);
          v107 = *((_QWORD *)v1 + 8);
          if ( *(_BYTE *)(v107 + 242) == 1 )
          {
            v108 = CSbQueueMonitor::ActivatedTaskEnded(*((_QWORD *)v1 + 8), v1, 4);
            v145 = v108;
            v109 = v142;
            v360 = v142;
            v171 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v110 = rand();
              if ( v110 == 5 * (v110 / 5) )
                Spinlock<165,9,258>::UpdateStatSnapshot();
            }
            v361 = v109;
            *v109 = 0;
            v143 = 0;
            v142 = 0;
            if ( v140 )
              SsbActivationTraceEvent((CSbActivationProcTask *)((char *)v1 + 152), v108, 0, 0, 0);
            AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v185);
            v78 = v146;
            v172 = v146;
            v219 = 0x400000;
            v362 = v148;
            goto LABEL_134;
          }
          v363 = *((_QWORD *)v1 + 8);
          --*(_DWORD *)(v107 + 132);
          v111 = v142;
          v364 = v142;
          v173 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v112 = rand();
            if ( v112 == 5 * (v112 / 5) )
              Spinlock<165,9,258>::UpdateStatSnapshot();
          }
          *v111 = 0;
          v143 = 0;
          v142 = 0;
          v220 = 88;
          v365 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v366 = (_QWORD *)(v365[SystemThread_TlsIndex] + SystemThread_TlsOffset);
          v367 = v366;
          v368 = *v366;
          v369 = v368;
          **(_WORD **)(*(_QWORD *)(v368 + 128) + 256LL) = 0;
          AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v185);
          v103 = v146;
          v174 = v146;
          v221 = 0x400000;
          v370 = v148;
        }
        else
        {
          v94 = CSbQueueMonitor::ScanQueue(v93);
          v213 = v94;
          if ( ((v94 - 2) & 0xFFFFFFFD) != 0 )
          {
            CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v142);
            if ( v94 == 3 )
            {
              CSbQueueMonitor::ActivatedTaskAborting(*((_QWORD *)v1 + 8), v1, 1, 0);
              v95 = v142;
              v343 = v142;
              v163 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
              if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v96 = rand();
                if ( v96 == 5 * (v96 / 5) )
                  Spinlock<165,9,258>::UpdateStatSnapshot();
              }
              v344 = v95;
              *v95 = 0;
              v143 = 0;
              v142 = 0;
              if ( v140 )
                SsbActivationTraceEvent(0, v145, 0, 0, 0);
              AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v185);
              v78 = v146;
              v164 = v146;
              v214 = 0x400000;
              v345 = v148;
              goto LABEL_134;
            }
            v97 = *((_QWORD *)v1 + 8);
            if ( *(_BYTE *)(v97 + 242) == 1 )
            {
              v98 = CSbQueueMonitor::ActivatedTaskEnded(*((_QWORD *)v1 + 8), v1, v94);
              v145 = v98;
              v99 = v142;
              v346 = v142;
              v165 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
              if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v100 = rand();
                if ( v100 == 5 * (v100 / 5) )
                  Spinlock<165,9,258>::UpdateStatSnapshot();
              }
              v347 = v99;
              *v99 = 0;
              v143 = 0;
              v142 = 0;
              if ( v140 )
                SsbActivationTraceEvent((CSbActivationProcTask *)((char *)v1 + 152), v98, 0, 0, 0);
              AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v185);
              v78 = v146;
              v166 = v146;
              v215 = 0x400000;
              v348 = v148;
              goto LABEL_134;
            }
            if ( v144 )
            {
              v349 = *((_QWORD *)v1 + 8);
              --*(_DWORD *)(v97 + 132);
            }
            v101 = v142;
            v350 = v142;
            v167 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v102 = rand();
              if ( v102 == 5 * (v102 / 5) )
                Spinlock<165,9,258>::UpdateStatSnapshot();
            }
            *v101 = 0;
            v143 = 0;
            v142 = 0;
            v216 = 88;
            v351 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v352 = (_QWORD *)(v351[SystemThread_TlsIndex] + SystemThread_TlsOffset);
            v353 = v352;
            v354 = *v352;
            v355 = v354;
            **(_WORD **)(*(_QWORD *)(v354 + 128) + 256LL) = 0;
            AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v185);
            v103 = v146;
            v168 = v146;
            v217 = 0x400000;
            v356 = v148;
          }
          else
          {
            CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v142);
            v357 = *((_QWORD *)v1 + 8);
            --*(_DWORD *)(v357 + 132);
            v105 = v142;
            v358 = v142;
            v169 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v106 = rand();
              if ( v106 == 5 * (v106 / 5) )
                Spinlock<165,9,258>::UpdateStatSnapshot();
            }
            *v105 = 0;
            v143 = 0;
            v142 = 0;
            AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v185);
            v103 = v146;
            v170 = v146;
            v218 = 0x400000;
            v359 = v148;
          }
        }
        v104 = *(_DWORD *)(v55 + 80);
        if ( v103 )
          v87 = v104 | 0x400000;
        else
          v87 = v104 & 0xFFBFFFFF;
LABEL_153:
        *(_DWORD *)(v55 + 80) = v87;
        CSQLObject::~CSQLObject((CSQLObject *)v424);
      }
      CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v142);
      v113 = CSbQueueMonitor::ActivatedTaskEnded(*((_QWORD *)v1 + 8), v1, 4);
      v145 = v113;
      v114 = v142;
      v371 = v142;
      v175 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v115 = rand();
        if ( v115 == 5 * (v115 / 5) )
          Spinlock<165,9,258>::UpdateStatSnapshot();
      }
      v372 = v114;
      *v114 = 0;
      v143 = 0;
      v142 = 0;
      if ( v140 )
        SsbActivationTraceEvent((CSbActivationProcTask *)((char *)v1 + 152), v113, 0, 0, 0);
      AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v185);
      v116 = v146;
      v176 = v146;
      v222 = 0x400000;
      v117 = v148;
      v373 = v148;
LABEL_220:
      if ( v116 )
        *(_DWORD *)(v117 + 80) |= 0x400000u;
      else
        *(_DWORD *)(v117 + 80) &= ~0x400000u;
LABEL_223:
      CSQLObject::~CSQLObject((CSQLObject *)v424);
      ExcHandler::~ExcHandler((ExcHandler *)v390);
    }
    catch ( SQLError v243 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v389, (const struct SQLError *)v243);
        v133 = v198;
        CSbQueueMonitor::GetSpinLock(*((_QWORD *)v198 + 8), &v142);
        v134 = CSbQueueMonitor::ActivatedTaskAborting(*((_QWORD *)v133 + 8), v133, v141, 0);
        v145 = v134;
        v135 = v142;
        v378 = v142;
        v179 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v136 = rand();
          if ( v136 == 5 * (v136 / 5) )
            Spinlock<165,9,258>::UpdateStatSnapshot();
        }
        v379 = v135;
        *v135 = 0;
        v143 = 0;
        if ( v140 )
          SsbActivationTraceEvent_0(0, v134, 28088, 16, 1, 0);
        v224 = 88;
        v380 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v381 = (_QWORD *)(v380[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v382 = v381;
        v383 = *v381;
        v384 = v383;
        v137 = *(_QWORD *)(v383 + 128);
        v385 = v137;
        *(_BYTE *)(v137 + 296) = 0;
        *(_DWORD *)(v137 + 76) &= ~0x2000000u;
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v389);
      }
      catch ( ShortStackException )
      {
      }
      v1 = v198;
    }
    v122 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v123 = *(struct Worker **)(v122 + 256);
    if ( !v123 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v123 = *(struct Worker **)(v122 + 256);
    }
    if ( *((_DWORD *)v123 + 139) )
      ExceptionPostCatchActions(v123);
    v124 = v200;
    if ( (_QWORD)v200 )
    {
      *(_QWORD *)(*(_QWORD *)(v200 + 24) + 8LL) = v201;
      *(_QWORD *)(v124 + 24) = *((_QWORD *)&v200 + 1);
      v200 = 0;
      v201 = 0;
    }
    v244 = &CConnectionOutput::`vftable';
    operator delete[](v238);
    v125 = v150;
    if ( v150 && v151 )
    {
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v126 = rand();
        if ( v126 == 5 * (v126 / 5) )
          Spinlock<170,8,258>::UpdateStatSnapshot();
      }
      *v125 = 0;
      v150 = 0;
      v151 = 0;
    }
    if ( v239 )
      (*(void (__fastcall **)(struct CActiveServiceBroker *))(*(_QWORD *)v239 + 56LL))(v239);
    v127 = v142;
  }
  else
  {
    CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v142);
    v129 = *((_QWORD *)v1 + 8);
    if ( *(_DWORD *)(v129 + 128) == ++*(_DWORD *)(v129 + 132) )
      *(_BYTE *)(v129 + 242) = 1;
    v145 = CSbQueueMonitor::ActivatedTaskEnded(*((_QWORD *)v1 + 8), v1, 4);
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v130 = rand();
      if ( v130 == 5 * (v130 / 5) )
        Spinlock<165,9,258>::UpdateStatSnapshot();
    }
    *v142 = 0;
    v143 = 0;
    v127 = 0;
    v142 = 0;
    if ( ActiveBrokerById )
      (*(void (__fastcall **)(struct CActiveServiceBroker *))(*(_QWORD *)ActiveBrokerById + 56LL))(ActiveBrokerById);
  }
  v131 = (void *)*((_QWORD *)v1 + 18);
  if ( v131 )
  {
    operator delete[](v131);
    *((_QWORD *)v1 + 18) = 0;
  }
  if ( v127 && v143 )
  {
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v132 = rand();
      if ( v132 == 5 * (v132 / 5) )
        Spinlock<165,9,258>::UpdateStatSnapshot();
    }
    *v127 = 0;
    v142 = 0;
    v143 = 0;
  }
}

```

## disassembly

```asm
0x100901410  push    rdi
0x100901412  push    r12
0x100901414  push    r13
0x100901416  push    r14
0x100901418  push    r15
0x10090141a  mov     eax, 12E0h
0x10090141f  call    _alloca_probe
0x100901424  sub     rsp, rax
0x100901427  mov     [rsp+1308h+var_B60], 0FFFFFFFFFFFFFFFEh
0x100901433  mov     [rsp+1308h+arg_8], rbx
0x10090143b  mov     [rsp+1308h+arg_10], rsi
0x100901443  mov     rax, cs:__security_cookie
0x10090144a  xor     rax, rsp
0x10090144d  mov     [rsp+1308h+var_38], rax
0x100901455  mov     rsi, rcx
0x100901458  mov     [rsp+1308h+var_1140], rcx
0x100901460  mov     [rsp+1308h+var_12A7], 0
0x100901465  xor     edi, edi
0x100901467  mov     [rsp+1308h+var_128C], edi
0x10090146b  mov     [rsp+1308h+var_12A0], rdi
0x100901470  mov     [rsp+1308h+var_1298], edi
0x100901474  mov     [rsp+1308h+var_12A8], dil
0x100901479  mov     rdx, gs:58h
0x100901482  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100901489  mov     ecx, [rax]
0x10090148b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100901492  mov     eax, [rax]
0x100901494  add     rax, [rdx+rcx*8]
0x100901498  mov     rax, [rax]
0x10090149b  mov     rcx, [rax+48h]
0x10090149f  test    rcx, rcx
0x1009014a2  jz      short loc_1009014AA
0x1009014a4  movzx   ecx, word ptr [rcx+10h]
0x1009014a8  jmp     short loc_1009014AC
0x1009014aa  mov     ecx, edi
0x1009014ac  movsx   eax, cx
0x1009014af  mov     [rsi+68h], eax
0x1009014b2  mov     [rsi+6Ch], cx
0x1009014b6  mov     rax, [rsi+40h]
0x1009014ba  mov     rcx, [rax+50h]
0x1009014be  mov     [rsp+1308h+var_1060], rcx
0x1009014c6  mov     rax, cs:qword_102ECFB00
0x1009014cd  mov     rcx, [rax+0A8F0h]
0x1009014d4  add     rcx, 6828h; this
0x1009014db  lea     rdx, [rsp+1308h+var_1060]; struct CSbAsbId *
0x1009014e3  call    ?GetActiveBrokerById@CActiveServiceBrokerMgr@@QEAAPEAVCActiveServiceBroker@@AEBVCSbAsbId@@@Z; CActiveServiceBrokerMgr::GetActiveBrokerById(CSbAsbId const &)
0x1009014e8  mov     r14, rax
0x1009014eb  mov     [rsp+1308h+var_1010], rax
0x1009014f3  test    rax, rax
0x1009014f6  jz      loc_1009035FF
0x1009014fc  call    cs:__imp_GetXdbServerGlobals
0x100901502  cmp     dword ptr [rax+2EC8h], 0
0x100901509  jz      short loc_100901518
0x10090150b  cmp     cs:byte_102EDCE86, 0
0x100901512  jz      loc_1009035FF
0x100901518  mov     eax, [r14+1C8h]
0x10090151f  cmp     eax, 1
0x100901522  jnz     loc_1009035FF
0x100901528  mov     rax, cs:qword_102ECFB00
0x10090152f  mov     rcx, [rax+0A8F0h]
0x100901536  mov     eax, [rcx+50h]
0x100901539  cmp     eax, 3
0x10090153c  jz      loc_1009035FF
0x100901542  mov     eax, [rcx+50h]
0x100901545  test    eax, eax
0x100901547  jz      loc_1009035FF
0x10090154d  cmp     byte ptr [r14+0E7h], 0
0x100901555  jnz     loc_1009035FF
0x10090155b  movzx   eax, word ptr [r14+0CCh]
0x100901563  mov     [rsp+1308h+var_1278], ax
0x10090156b  mov     rax, [rsi+40h]
0x10090156f  mov     eax, [rax+58h]
0x100901572  mov     [rsp+1308h+var_1158], eax
0x100901579  mov     rax, cs:qword_102ECFB00
0x100901580  mov     rcx, [rax+0A8F0h]
0x100901587  add     rcx, 6238h
0x10090158e  mov     [rsp+1308h+var_1270], rcx
0x100901596  mov     [rsp+1308h+var_1268], edi
0x10090159d  mov     [rsi+90h], rdi
0x1009015a4  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1009015ab  mov     r12d, 1
0x1009015b1  mov     rbx, rdi
0x1009015b4  mov     eax, gs:48h
0x1009015bc  mov     r15d, eax
0x1009015bf  mov     rax, [rsp+1308h+var_1270]
0x1009015c7  mov     ecx, [rax]
0x1009015c9  test    ecx, ecx
0x1009015cb  jnz     short loc_1009015E9
0x1009015cd  mov     rcx, [rsp+1308h+var_1270]
0x1009015d5  xor     eax, eax
0x1009015d7  lock cmpxchg [rcx], r15
0x1009015dc  mov     eax, edi
0x1009015de  setz    al
0x1009015e1  test    eax, eax
0x1009015e3  jnz     loc_1009016D4
0x1009015e9  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1009015f0  mov     ecx, [rax]
0x1009015f2  and     ecx, 84h
0x1009015f8  mov     r14, rdi
0x1009015fb  cmp     cl, 84h
0x1009015fe  jnz     short loc_100901662
0x100901600  mov     rdx, gs:58h
0x100901609  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100901610  mov     ecx, [rax]
0x100901612  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100901619  mov     r8d, [rax]
0x10090161c  add     r8, [rdx+rcx*8]
0x100901620  jz      short loc_100901632
0x100901622  cmp     [r8+110h], r8
0x100901629  jnz     short loc_100901632
0x10090162b  mov     r14, [r8+100h]
0x100901632  test    r14, r14
0x100901635  jz      short loc_100901662
0x100901637  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10090163e  cmp     [rax], ebx
0x100901640  jz      short loc_10090165A
0x100901642  lea     rcx, [rsp+1308h+PerformanceCount]; lpPerformanceCount
0x10090164a  call    cs:__imp_QueryPerformanceCounter
0x100901650  mov     rbx, qword ptr [rsp+1308h+PerformanceCount]
0x100901658  jmp     short loc_100901662
0x10090165a  mov     rbx, ds:7FFE0008h
0x100901662  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100901669  mov     rcx, [rsp+1308h+var_1270]
0x100901671  cmp     byte ptr [rax+0C7h], 0
0x100901678  jge     short loc_100901687
0x10090167a  mov     r8, r15
0x10090167d  mov     rdx, r14
0x100901680  call    ?SpinToAcquireOptimistic@?$Spinlock@$0KK@$07$0BAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<170,8,258>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100901685  jmp     short loc_10090168F
0x100901687  mov     rdx, r15
0x10090168a  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0KK@$07$0BAC@@@AEAAX_K@Z; Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10090168f  test    r14, r14
0x100901692  jz      short loc_1009016D4
0x100901694  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10090169b  cmp     dword ptr [rax], 0
0x10090169e  jz      short loc_1009016B8
0x1009016a0  lea     rcx, [rsp+1308h+var_1050]; lpPerformanceCount
0x1009016a8  call    cs:__imp_QueryPerformanceCounter
0x1009016ae  mov     rax, qword ptr [rsp+1308h+var_1050]
0x1009016b6  jmp     short loc_1009016C0
0x1009016b8  mov     rax, ds:7FFE0008h
0x1009016c0  cmp     rax, rbx
0x1009016c3  jb      short loc_1009016CA
0x1009016c5  sub     rax, rbx
0x1009016c8  jmp     short loc_1009016CD
0x1009016ca  mov     rax, rdi
0x1009016cd  add     [r14+0C78h], rax
0x1009016d4  mov     [rsp+1308h+var_1268], r12d
0x1009016dc  mov     rax, [rsi+40h]
0x1009016e0  mov     rcx, [rax+60h]
0x1009016e4  mov     r14, r13
0x1009016e7  nop     word ptr [rax+rax+00000000h]
0x1009016f0  inc     r14
0x1009016f3  cmp     word ptr [rcx+r14*2], 0
0x1009016f9  jnz     short loc_1009016F0
0x1009016fb  add     r14, r14
0x1009016fe  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x100901705  cmp     byte ptr [rax], 0
0x100901708  jz      short loc_100901731
0x10090170a  call    cs:__imp_rand
0x100901710  mov     r8d, eax
0x100901713  mov     eax, 66666667h
0x100901718  imul    r8d
0x10090171b  sar     edx, 1
0x10090171d  mov     ecx, edx
0x10090171f  shr     ecx, 1Fh
0x100901722  add     edx, ecx
0x100901724  lea     ecx, [rdx+rdx*4]
0x100901727  cmp     r8d, ecx
0x10090172a  jnz     short loc_100901731
0x10090172c  call    ?UpdateStatSnapshot@?$Spinlock@$0KK@$07$0BAC@@@AEAAXXZ; Spinlock<170,8,258>::UpdateStatSnapshot(void)
0x100901731  mov     rax, [rsp+1308h+var_1270]
0x100901739  mov     [rax], rdi
0x10090173c  mov     [rsp+1308h+var_1268], edi
0x100901743  mov     r15d, r14d
0x100901746  shr     r15d, 1
0x100901749  inc     r15d
0x10090174c  mov     rdx, gs:58h
0x100901755  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10090175c  mov     ecx, [rax]
0x10090175e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100901765  mov     ebx, [rax]
0x100901767  add     rbx, [rdx+rcx*8]
0x10090176b  mov     rcx, [rbx+100h]
0x100901772  test    rcx, rcx
0x100901775  jnz     short loc_100901784
0x100901777  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10090177d  mov     rcx, [rbx+100h]
0x100901784  mov     r12d, r15d
0x100901787  mov     eax, 2
0x10090178c  mul     r12
0x10090178f  cmovo   rax, r13
0x100901793  mov     byte ptr [rsp+1308h+var_12E8], 8
0x100901798  mov     r9d, 734h
0x10090179e  lea     r8, aSqlNtdbmsBroke_11; "sql\\ntdbms\\broker\\src\\ssbInternalAc"...
0x1009017a5  mov     rdx, [rcx+3E8h]
0x1009017ac  mov     rcx, rax
0x1009017af  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1009017b5  mov     r15, rax
0x1009017b8  mov     [rsp+1308h+var_1180], rax
0x1009017c0  mov     r8, gs:58h
0x1009017c9  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x1009017d0  mov     edx, [rcx]
0x1009017d2  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x1009017d9  mov     ebx, [rcx]
0x1009017db  add     rbx, [r8+rdx*8]
0x1009017df  mov     rcx, [rbx+100h]
0x1009017e6  test    rcx, rcx
0x1009017e9  jnz     short loc_1009017F8
0x1009017eb  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1009017f1  mov     rcx, [rbx+100h]
0x1009017f8  mov     eax, 2
0x1009017fd  mul     r12
0x100901800  cmovo   rax, r13
0x100901804  mov     byte ptr [rsp+1308h+var_12E8], 8
0x100901809  mov     r9d, 735h
0x10090180f  lea     r8, aSqlNtdbmsBroke_11; "sql\\ntdbms\\broker\\src\\ssbInternalAc"...
0x100901816  mov     rdx, [rcx+3E8h]
0x10090181d  mov     rcx, rax
0x100901820  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100901826  mov     [rsi+90h], rax
0x10090182d  mov     rbx, rdi
0x100901830  mov     eax, gs:48h
0x100901838  mov     r13d, eax
0x10090183b  mov     rax, [rsp+1308h+var_1270]
0x100901843  mov     ecx, [rax]
0x100901845  test    ecx, ecx
0x100901847  jnz     short loc_100901865
0x100901849  mov     rcx, [rsp+1308h+var_1270]
0x100901851  xor     eax, eax
0x100901853  lock cmpxchg [rcx], r13
0x100901858  mov     eax, edi
0x10090185a  setz    al
0x10090185d  test    eax, eax
0x10090185f  jnz     loc_100901958
0x100901865  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10090186c  mov     ecx, [rax]
0x10090186e  and     ecx, 84h
0x100901874  mov     r15, rdi
0x100901877  cmp     cl, 84h
0x10090187a  jnz     short loc_1009018DE
0x10090187c  mov     rdx, gs:58h
0x100901885  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10090188c  mov     ecx, [rax]
0x10090188e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100901895  mov     r8d, [rax]
0x100901898  add     r8, [rdx+rcx*8]
0x10090189c  jz      short loc_1009018AE
0x10090189e  cmp     [r8+110h], r8
0x1009018a5  jnz     short loc_1009018AE
0x1009018a7  mov     r15, [r8+100h]
0x1009018ae  test    r15, r15
0x1009018b1  jz      short loc_1009018DE
0x1009018b3  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1009018ba  cmp     [rax], ebx
0x1009018bc  jz      short loc_1009018D6
0x1009018be  lea     rcx, [rsp+1308h+var_1048]; lpPerformanceCount
0x1009018c6  call    cs:__imp_QueryPerformanceCounter
0x1009018cc  mov     rbx, qword ptr [rsp+1308h+var_1048]
0x1009018d4  jmp     short loc_1009018DE
0x1009018d6  mov     rbx, ds:7FFE0008h
0x1009018de  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x1009018e5  mov     rcx, [rsp+1308h+var_1270]
0x1009018ed  cmp     byte ptr [rax+0C7h], 0
0x1009018f4  jge     short loc_100901903
0x1009018f6  mov     r8, r13
0x1009018f9  mov     rdx, r15
0x1009018fc  call    ?SpinToAcquireOptimistic@?$Spinlock@$0KK@$07$0BAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<170,8,258>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100901901  jmp     short loc_10090190B
0x100901903  mov     rdx, r13
0x100901906  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0KK@$07$0BAC@@@AEAAX_K@Z; Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10090190b  test    r15, r15
0x10090190e  jz      short loc_100901950
0x100901910  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100901917  cmp     dword ptr [rax], 0
0x10090191a  jz      short loc_100901934
0x10090191c  lea     rcx, [rsp+1308h+var_1040]; lpPerformanceCount
0x100901924  call    cs:__imp_QueryPerformanceCounter
0x10090192a  mov     rax, qword ptr [rsp+1308h+var_1040]
0x100901932  jmp     short loc_10090193C
0x100901934  mov     rax, ds:7FFE0008h
0x10090193c  cmp     rax, rbx
0x10090193f  jb      short loc_100901946
0x100901941  sub     rax, rbx
0x100901944  jmp     short loc_100901949
0x100901946  mov     rax, rdi
0x100901949  add     [r15+0C78h], rax
0x100901950  mov     r15, [rsp+1308h+var_1180]
0x100901958  mov     eax, 1
0x10090195d  mov     [rsp+1308h+var_1268], eax
0x100901964  mov     rax, [rsi+40h]
0x100901968  mov     rcx, [rax+60h]; wchar_t *
0x10090196c  mov     r13, 0FFFFFFFFFFFFFFFFh
0x100901973  mov     rax, r13
0x100901976  inc     rax
0x100901979  cmp     word ptr [rcx+rax*2], 0
0x10090197e  jnz     short loc_100901976
0x100901980  add     rax, rax
0x100901983  cmp     r14d, eax
0x100901986  jnz     loc_10090359F
  ... truncated ...
```
