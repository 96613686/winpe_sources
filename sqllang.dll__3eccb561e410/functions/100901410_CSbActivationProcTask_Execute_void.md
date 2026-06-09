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
  __int64 v4; // rcx
  struct CActiveServiceBroker *ActiveBrokerById; // r14
  __int64 v6; // rcx
  CSbTransportMgr *QuadPart; // rbx
  signed __int64 UniqueThread_low; // r15
  __int64 v9; // r14
  __int64 v10; // r8
  CSbTransportMgr *v11; // rax
  signed __int64 v12; // rax
  __int64 v13; // r14
  unsigned int v14; // r14d
  int v15; // r8d
  unsigned int v16; // r15d
  __int64 v17; // rbx
  __int64 v18; // rcx
  unsigned __int64 v19; // r12
  unsigned __int64 v20; // rax
  void *v21; // r15
  __int64 v22; // rbx
  __int64 v23; // rcx
  unsigned __int64 v24; // rax
  CSbTransportMgr *v25; // rbx
  signed __int64 v26; // r13
  __int64 v27; // r15
  __int64 v28; // r8
  CSbTransportMgr *v29; // rax
  signed __int64 v30; // rax
  const wchar_t *v31; // rcx
  __int64 v32; // rax
  int v33; // ebx
  _WORD *v34; // rcx
  unsigned __int64 v35; // rdx
  __int64 v36; // r8
  __int16 v37; // ax
  _WORD *v38; // rax
  int v39; // r8d
  __int64 v40; // rcx
  void ***v41; // rdx
  __int64 v42; // rbx
  __int64 v43; // r8
  int v44; // eax
  int v45; // ecx
  int v46; // r14d
  _QWORD *v47; // rbx
  int v48; // r8d
  unsigned int v49; // r12d
  __int64 v50; // rdx
  int v51; // eax
  int v52; // edx
  __int64 v53; // rbx
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  char v57; // al
  __int64 v58; // rax
  __int64 XdbServerGlobals; // rax
  _QWORD *v60; // r8
  __int64 v61; // rcx
  char v62; // al
  __int64 v63; // rax
  int v64; // r15d
  _QWORD *v65; // r14
  int v66; // r8d
  int v67; // eax
  __int64 v68; // rax
  __int64 v69; // r8
  __int64 v70; // rax
  __int64 v71; // rdx
  int v72; // r15d
  _QWORD *v73; // r14
  int v74; // r8d
  bool v75; // cl
  __int64 v76; // r8
  int v77; // eax
  int v78; // r15d
  _QWORD *v79; // r14
  int v80; // r8d
  _QWORD *v81; // r14
  int v82; // r8d
  int v83; // eax
  unsigned int v84; // eax
  int v85; // r8d
  __int64 v86; // rdx
  bool v87; // r14
  _QWORD *v88; // r15
  int v89; // r8d
  __int64 v90; // rcx
  unsigned int v91; // r14d
  _QWORD *v92; // r14
  int v93; // r8d
  __int64 v94; // rax
  int v95; // r15d
  _QWORD *v96; // r14
  int v97; // r8d
  _QWORD *v98; // r14
  int v99; // r8d
  bool v100; // cl
  int v101; // eax
  _QWORD *v102; // r14
  int v103; // r8d
  __int64 v104; // rax
  int v105; // r15d
  _QWORD *v106; // r14
  int v107; // r8d
  _QWORD *v108; // r14
  int v109; // r8d
  int v110; // r14d
  _QWORD *v111; // rbx
  int v112; // r8d
  bool v113; // al
  __int64 v114; // rcx
  __int64 v115; // rdx
  int v116; // r14d
  _QWORD *v117; // rbx
  int v118; // r8d
  __int64 v119; // rbx
  struct Worker *v120; // rcx
  __int64 v121; // rdx
  volatile signed __int64 *v122; // rbx
  int v123; // r8d
  _QWORD *v124; // rbx
  int v125; // r8d
  __int64 v126; // rdx
  int v127; // r8d
  void *v128; // rcx
  int v129; // r8d
  CSbActivationProcTask *v130; // rbx
  int v131; // esi
  _QWORD *v132; // rdi
  int v133; // r8d
  __int64 v134; // rax
  int v135; // [rsp+20h] [rbp-12E8h]
  int v136; // [rsp+28h] [rbp-12E0h]
  char v137; // [rsp+60h] [rbp-12A8h]
  unsigned __int8 v138; // [rsp+62h] [rbp-12A6h]
  _QWORD *v139; // [rsp+68h] [rbp-12A0h] BYREF
  int v140; // [rsp+70h] [rbp-1298h]
  char v141; // [rsp+78h] [rbp-1290h]
  int v142; // [rsp+7Ch] [rbp-128Ch]
  bool v143; // [rsp+80h] [rbp-1288h]
  int v144; // [rsp+84h] [rbp-1284h]
  __int64 v145; // [rsp+88h] [rbp-1280h]
  unsigned __int16 v146; // [rsp+90h] [rbp-1278h]
  volatile signed __int64 *v147; // [rsp+98h] [rbp-1270h]
  int v148; // [rsp+A0h] [rbp-1268h]
  bool v149; // [rsp+A8h] [rbp-1260h]
  bool v150; // [rsp+A9h] [rbp-125Fh]
  bool v151; // [rsp+B0h] [rbp-1258h]
  bool v152; // [rsp+B8h] [rbp-1250h]
  bool v153; // [rsp+C0h] [rbp-1248h]
  bool v154; // [rsp+C8h] [rbp-1240h]
  bool v155; // [rsp+D0h] [rbp-1238h]
  bool v156; // [rsp+D8h] [rbp-1230h]
  bool v157; // [rsp+E0h] [rbp-1228h]
  bool v158; // [rsp+E8h] [rbp-1220h]
  bool v159; // [rsp+E9h] [rbp-121Fh]
  bool v160; // [rsp+EAh] [rbp-121Eh]
  bool v161; // [rsp+F0h] [rbp-1218h]
  bool v162; // [rsp+F8h] [rbp-1210h]
  bool v163; // [rsp+100h] [rbp-1208h]
  bool v164; // [rsp+108h] [rbp-1200h]
  bool v165; // [rsp+110h] [rbp-11F8h]
  bool v166; // [rsp+118h] [rbp-11F0h]
  bool v167; // [rsp+120h] [rbp-11E8h]
  bool v168; // [rsp+128h] [rbp-11E0h]
  bool v169; // [rsp+130h] [rbp-11D8h]
  bool v170; // [rsp+138h] [rbp-11D0h]
  bool v171; // [rsp+140h] [rbp-11C8h]
  bool v172; // [rsp+148h] [rbp-11C0h]
  bool v173; // [rsp+150h] [rbp-11B8h]
  bool v174; // [rsp+158h] [rbp-11B0h]
  bool v175; // [rsp+160h] [rbp-11A8h]
  bool v176; // [rsp+168h] [rbp-11A0h]
  bool v177; // [rsp+169h] [rbp-119Fh]
  bool v178; // [rsp+16Ah] [rbp-119Eh]
  bool v179; // [rsp+16Bh] [rbp-119Dh]
  bool v180; // [rsp+16Ch] [rbp-119Ch]
  bool v181; // [rsp+16Dh] [rbp-119Bh]
  void **v182; // [rsp+170h] [rbp-1198h] BYREF
  __int64 v183; // [rsp+178h] [rbp-1190h]
  __int64 v184; // [rsp+180h] [rbp-1188h] BYREF
  __int64 v185; // [rsp+188h] [rbp-1180h]
  _BYTE v186[2]; // [rsp+190h] [rbp-1178h] BYREF
  char v187; // [rsp+192h] [rbp-1176h]
  int v188; // [rsp+198h] [rbp-1170h]
  int v189; // [rsp+19Ch] [rbp-116Ch]
  __int16 v190; // [rsp+1A0h] [rbp-1168h]
  __int16 v191; // [rsp+1A8h] [rbp-1160h]
  unsigned int v192; // [rsp+1B0h] [rbp-1158h]
  __int64 v193; // [rsp+1B8h] [rbp-1150h]
  __int64 v194; // [rsp+1C0h] [rbp-1148h]
  CSbActivationProcTask *v195; // [rsp+1C8h] [rbp-1140h]
  __int64 v196; // [rsp+1D0h] [rbp-1138h]
  __int128 v197; // [rsp+1D8h] [rbp-1130h]
  __int128 v198; // [rsp+1E8h] [rbp-1120h]
  int v199; // [rsp+1F8h] [rbp-1110h]
  int v200; // [rsp+1FCh] [rbp-110Ch]
  int v201; // [rsp+200h] [rbp-1108h]
  int v202; // [rsp+208h] [rbp-1100h]
  int v203; // [rsp+210h] [rbp-10F8h]
  int v204; // [rsp+218h] [rbp-10F0h]
  int v205; // [rsp+21Ch] [rbp-10ECh]
  int v206; // [rsp+220h] [rbp-10E8h]
  int v207; // [rsp+228h] [rbp-10E0h]
  int v208; // [rsp+230h] [rbp-10D8h]
  int v209; // [rsp+234h] [rbp-10D4h]
  unsigned int v210; // [rsp+238h] [rbp-10D0h]
  int v211; // [rsp+240h] [rbp-10C8h]
  int v212; // [rsp+248h] [rbp-10C0h]
  int v213; // [rsp+250h] [rbp-10B8h]
  int v214; // [rsp+258h] [rbp-10B0h]
  int v215; // [rsp+260h] [rbp-10A8h]
  int v216; // [rsp+268h] [rbp-10A0h]
  int v217; // [rsp+270h] [rbp-1098h]
  int v218; // [rsp+278h] [rbp-1090h]
  int v219; // [rsp+280h] [rbp-1088h]
  int v220; // [rsp+288h] [rbp-1080h]
  int v221; // [rsp+290h] [rbp-1078h]
  unsigned int v222; // [rsp+294h] [rbp-1074h]
  unsigned int v223; // [rsp+298h] [rbp-1070h]
  int v224; // [rsp+29Ch] [rbp-106Ch]
  int v225; // [rsp+2A0h] [rbp-1068h]
  __int64 v226; // [rsp+2A8h] [rbp-1060h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+2B0h] [rbp-1058h] BYREF
  LARGE_INTEGER v228; // [rsp+2B8h] [rbp-1050h] BYREF
  LARGE_INTEGER v229; // [rsp+2C0h] [rbp-1048h] BYREF
  LARGE_INTEGER v230; // [rsp+2C8h] [rbp-1040h] BYREF
  unsigned __int64 v231; // [rsp+2D0h] [rbp-1038h] BYREF
  unsigned __int64 v232; // [rsp+2D8h] [rbp-1030h] BYREF
  int v233; // [rsp+2E0h] [rbp-1028h]
  int v234; // [rsp+2E8h] [rbp-1020h]
  void *v235; // [rsp+2F0h] [rbp-1018h]
  struct CActiveServiceBroker *v236; // [rsp+2F8h] [rbp-1010h]
  int v237; // [rsp+300h] [rbp-1008h]
  int v238; // [rsp+304h] [rbp-1004h]
  int v239; // [rsp+308h] [rbp-1000h]
  _DWORD v240[8]; // [rsp+310h] [rbp-FF8h] BYREF
  void **v241; // [rsp+330h] [rbp-FD8h] BYREF
  void ***v242; // [rsp+338h] [rbp-FD0h]
  int v243; // [rsp+340h] [rbp-FC8h]
  __int64 v244; // [rsp+348h] [rbp-FC0h]
  __int64 v245; // [rsp+350h] [rbp-FB8h]
  __int64 v246; // [rsp+358h] [rbp-FB0h]
  __int64 v247; // [rsp+360h] [rbp-FA8h]
  char v248; // [rsp+368h] [rbp-FA0h]
  __int64 v249; // [rsp+370h] [rbp-F98h]
  char v250; // [rsp+380h] [rbp-F88h]
  __int64 v251; // [rsp+388h] [rbp-F80h]
  __int64 v252; // [rsp+390h] [rbp-F78h]
  unsigned __int64 v253; // [rsp+398h] [rbp-F70h]
  _WORD *v254; // [rsp+3A0h] [rbp-F68h]
  unsigned __int64 **v255; // [rsp+3A8h] [rbp-F60h]
  _QWORD *v256; // [rsp+3B0h] [rbp-F58h]
  _QWORD *v257; // [rsp+3B8h] [rbp-F50h]
  __int64 v258; // [rsp+3C0h] [rbp-F48h]
  __int64 v259; // [rsp+3C8h] [rbp-F40h]
  unsigned __int64 v260; // [rsp+3D0h] [rbp-F38h]
  _WORD *v261; // [rsp+3D8h] [rbp-F30h]
  unsigned __int64 **v262; // [rsp+3E0h] [rbp-F28h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+3E8h] [rbp-F20h]
  _QWORD *v264; // [rsp+3F0h] [rbp-F18h]
  _QWORD *v265; // [rsp+3F8h] [rbp-F10h]
  __int64 v266; // [rsp+400h] [rbp-F08h]
  __int64 v267; // [rsp+408h] [rbp-F00h]
  __int64 v268; // [rsp+410h] [rbp-EF8h]
  _QWORD *v269; // [rsp+418h] [rbp-EF0h]
  _QWORD *v270; // [rsp+420h] [rbp-EE8h]
  _QWORD *v271; // [rsp+428h] [rbp-EE0h]
  __int64 v272; // [rsp+430h] [rbp-ED8h]
  __int64 v273; // [rsp+438h] [rbp-ED0h]
  __int64 v274; // [rsp+440h] [rbp-EC8h]
  __int64 v275; // [rsp+448h] [rbp-EC0h]
  _QWORD *v276; // [rsp+450h] [rbp-EB8h]
  const struct CCompExecCtxtBasic **v277; // [rsp+458h] [rbp-EB0h]
  const struct CCompExecCtxtBasic **v278; // [rsp+460h] [rbp-EA8h]
  const struct CCompExecCtxtBasic *v279; // [rsp+468h] [rbp-EA0h]
  const struct CCompExecCtxtBasic *v280; // [rsp+470h] [rbp-E98h]
  __int64 v281; // [rsp+478h] [rbp-E90h]
  _QWORD *v282; // [rsp+480h] [rbp-E88h]
  const struct CCompExecCtxtBasic **v283; // [rsp+488h] [rbp-E80h]
  const struct CCompExecCtxtBasic **v284; // [rsp+490h] [rbp-E78h]
  const struct CCompExecCtxtBasic *v285; // [rsp+498h] [rbp-E70h]
  const struct CCompExecCtxtBasic *v286; // [rsp+4A0h] [rbp-E68h]
  _QWORD *v287; // [rsp+4A8h] [rbp-E60h]
  _QWORD *v288; // [rsp+4B0h] [rbp-E58h]
  _QWORD *v289; // [rsp+4B8h] [rbp-E50h]
  __int64 v290; // [rsp+4C0h] [rbp-E48h]
  __int64 v291; // [rsp+4C8h] [rbp-E40h]
  __int64 v292; // [rsp+4D0h] [rbp-E38h]
  __int64 v293; // [rsp+4D8h] [rbp-E30h]
  _QWORD *v294; // [rsp+4E0h] [rbp-E28h]
  const struct CCompExecCtxtBasic **v295; // [rsp+4E8h] [rbp-E20h]
  const struct CCompExecCtxtBasic **v296; // [rsp+4F0h] [rbp-E18h]
  const struct CCompExecCtxtBasic *v297; // [rsp+4F8h] [rbp-E10h]
  const struct CCompExecCtxtBasic *v298; // [rsp+500h] [rbp-E08h]
  __int64 v299; // [rsp+508h] [rbp-E00h]
  _QWORD *v300; // [rsp+510h] [rbp-DF8h]
  _QWORD *v301; // [rsp+518h] [rbp-DF0h]
  _QWORD *v302; // [rsp+520h] [rbp-DE8h]
  __int64 v303; // [rsp+528h] [rbp-DE0h]
  __int64 v304; // [rsp+530h] [rbp-DD8h]
  _QWORD *v305; // [rsp+538h] [rbp-DD0h]
  _QWORD *v306; // [rsp+540h] [rbp-DC8h]
  __int64 v307; // [rsp+548h] [rbp-DC0h]
  __int64 *v308; // [rsp+550h] [rbp-DB8h]
  __int64 *v309; // [rsp+558h] [rbp-DB0h]
  __int64 v310; // [rsp+560h] [rbp-DA8h]
  __int64 v311; // [rsp+568h] [rbp-DA0h]
  _QWORD *v312; // [rsp+570h] [rbp-D98h]
  _QWORD *v313; // [rsp+578h] [rbp-D90h]
  __int64 v314; // [rsp+580h] [rbp-D88h]
  __int64 v315; // [rsp+588h] [rbp-D80h]
  char *v316; // [rsp+590h] [rbp-D78h]
  _QWORD *v317; // [rsp+598h] [rbp-D70h]
  _QWORD *v318; // [rsp+5A0h] [rbp-D68h]
  __int64 v319; // [rsp+5A8h] [rbp-D60h]
  __int64 v320; // [rsp+5B0h] [rbp-D58h]
  _QWORD *v321; // [rsp+5B8h] [rbp-D50h]
  _QWORD *v322; // [rsp+5C0h] [rbp-D48h]
  __int64 v323; // [rsp+5C8h] [rbp-D40h]
  _QWORD *v324; // [rsp+5D0h] [rbp-D38h]
  __int64 v325; // [rsp+5D8h] [rbp-D30h]
  _QWORD *v326; // [rsp+5E0h] [rbp-D28h]
  char *v327; // [rsp+5E8h] [rbp-D20h]
  _QWORD *v328; // [rsp+5F0h] [rbp-D18h]
  _QWORD *v329; // [rsp+5F8h] [rbp-D10h]
  __int64 v330; // [rsp+600h] [rbp-D08h]
  __int64 v331; // [rsp+608h] [rbp-D00h]
  _WORD *v332; // [rsp+610h] [rbp-CF8h]
  __int64 v333; // [rsp+618h] [rbp-CF0h]
  _QWORD *v334; // [rsp+620h] [rbp-CE8h]
  _QWORD *v335; // [rsp+628h] [rbp-CE0h]
  _QWORD *v336; // [rsp+630h] [rbp-CD8h]
  _QWORD *v337; // [rsp+638h] [rbp-CD0h]
  __int64 v338; // [rsp+640h] [rbp-CC8h]
  __int64 v339; // [rsp+648h] [rbp-CC0h]
  _QWORD *v340; // [rsp+650h] [rbp-CB8h]
  _QWORD *v341; // [rsp+658h] [rbp-CB0h]
  __int64 v342; // [rsp+660h] [rbp-CA8h]
  _QWORD *v343; // [rsp+668h] [rbp-CA0h]
  _QWORD *v344; // [rsp+670h] [rbp-C98h]
  __int64 v345; // [rsp+678h] [rbp-C90h]
  __int64 v346; // [rsp+680h] [rbp-C88h]
  _QWORD *v347; // [rsp+688h] [rbp-C80h]
  _QWORD *v348; // [rsp+690h] [rbp-C78h]
  _QWORD *v349; // [rsp+698h] [rbp-C70h]
  _QWORD *v350; // [rsp+6A0h] [rbp-C68h]
  __int64 v351; // [rsp+6A8h] [rbp-C60h]
  __int64 v352; // [rsp+6B0h] [rbp-C58h]
  __int64 v353; // [rsp+6B8h] [rbp-C50h]
  __int64 v354; // [rsp+6C0h] [rbp-C48h]
  _QWORD *v355; // [rsp+6C8h] [rbp-C40h]
  __int64 v356; // [rsp+6D0h] [rbp-C38h]
  _QWORD *v357; // [rsp+6D8h] [rbp-C30h]
  _QWORD *v358; // [rsp+6E0h] [rbp-C28h]
  __int64 v359; // [rsp+6E8h] [rbp-C20h]
  __int64 v360; // [rsp+6F0h] [rbp-C18h]
  _QWORD *v361; // [rsp+6F8h] [rbp-C10h]
  _QWORD *v362; // [rsp+700h] [rbp-C08h]
  _QWORD *v363; // [rsp+708h] [rbp-C00h]
  _QWORD *v364; // [rsp+710h] [rbp-BF8h]
  __int64 v365; // [rsp+718h] [rbp-BF0h]
  __int64 v366; // [rsp+720h] [rbp-BE8h]
  __int64 v367; // [rsp+728h] [rbp-BE0h]
  _QWORD *v368; // [rsp+730h] [rbp-BD8h]
  _QWORD *v369; // [rsp+738h] [rbp-BD0h]
  __int64 v370; // [rsp+740h] [rbp-BC8h]
  __int64 v371; // [rsp+748h] [rbp-BC0h]
  _QWORD *v372; // [rsp+750h] [rbp-BB8h]
  _QWORD *v373; // [rsp+758h] [rbp-BB0h]
  __int64 v374; // [rsp+760h] [rbp-BA8h]
  _QWORD *v375; // [rsp+768h] [rbp-BA0h]
  _QWORD *v376; // [rsp+770h] [rbp-B98h]
  _QWORD *v377; // [rsp+778h] [rbp-B90h]
  _QWORD *v378; // [rsp+780h] [rbp-B88h]
  _QWORD *v379; // [rsp+788h] [rbp-B80h]
  __int64 v380; // [rsp+790h] [rbp-B78h]
  __int64 v381; // [rsp+798h] [rbp-B70h]
  __int64 v382; // [rsp+7A0h] [rbp-B68h]
  __int64 v383; // [rsp+7A8h] [rbp-B60h]
  __int64 v384; // [rsp+7B0h] [rbp-B58h]
  __int64 v385; // [rsp+7B8h] [rbp-B50h]
  _QWORD v386[6]; // [rsp+7C0h] [rbp-B48h] BYREF
  _BYTE v387[40]; // [rsp+7F0h] [rbp-B18h] BYREF
  _BYTE v388[56]; // [rsp+818h] [rbp-AF0h] BYREF
  _BYTE v389[8]; // [rsp+850h] [rbp-AB8h] BYREF
  _WORD v390[4]; // [rsp+858h] [rbp-AB0h] BYREF
  int v391; // [rsp+860h] [rbp-AA8h]
  unsigned __int64 **v392; // [rsp+868h] [rbp-AA0h]
  char *v393; // [rsp+870h] [rbp-A98h]
  __int64 v394; // [rsp+878h] [rbp-A90h]
  unsigned __int64 *v395; // [rsp+880h] [rbp-A88h] BYREF
  int v396; // [rsp+888h] [rbp-A80h]
  __int16 v397; // [rsp+88Ch] [rbp-A7Ch]
  __int16 v398; // [rsp+88Eh] [rbp-A7Ah]
  char v399; // [rsp+890h] [rbp-A78h] BYREF
  int v400; // [rsp+AA0h] [rbp-868h]
  int v401; // [rsp+AA4h] [rbp-864h]
  __int64 v402; // [rsp+AA8h] [rbp-860h]
  unsigned __int64 v403; // [rsp+AB0h] [rbp-858h] BYREF
  int v404; // [rsp+AB8h] [rbp-850h]
  _BYTE v405[8]; // [rsp+AC0h] [rbp-848h] BYREF
  _WORD v406[4]; // [rsp+AC8h] [rbp-840h] BYREF
  int v407; // [rsp+AD0h] [rbp-838h]
  unsigned __int64 **v408; // [rsp+AD8h] [rbp-830h]
  char *v409; // [rsp+AE0h] [rbp-828h]
  __int64 v410; // [rsp+AE8h] [rbp-820h]
  unsigned __int64 *v411; // [rsp+AF0h] [rbp-818h] BYREF
  int v412; // [rsp+AF8h] [rbp-810h]
  __int16 v413; // [rsp+AFCh] [rbp-80Ch]
  __int16 v414; // [rsp+AFEh] [rbp-80Ah]
  char v415; // [rsp+B00h] [rbp-808h] BYREF
  int v416; // [rsp+D10h] [rbp-5F8h]
  int v417; // [rsp+D14h] [rbp-5F4h]
  __int64 v418; // [rsp+D18h] [rbp-5F0h]
  unsigned __int64 v419; // [rsp+D20h] [rbp-5E8h] BYREF
  int v420; // [rsp+D28h] [rbp-5E0h]
  _BYTE v421[1440]; // [rsp+D30h] [rbp-5D8h] BYREF

  v383 = -2;
  v1 = this;
  v195 = this;
  v142 = 0;
  v139 = 0;
  v140 = 0;
  v2 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset)
                 + 72LL);
  if ( v2 )
    v3 = *(_WORD *)(v2 + 16);
  else
    v3 = 0;
  *((_DWORD *)v1 + 26) = v3;
  *((_WORD *)v1 + 54) = v3;
  v226 = *(_QWORD *)(*((_QWORD *)v1 + 8) + 80LL);
  ActiveBrokerById = CActiveServiceBrokerMgr::GetActiveBrokerById(
                       (CActiveServiceBrokerMgr *)(*(_QWORD *)(qword_102ECFB00 + 43248) + 26664LL),
                       (const struct CSbAsbId *)&v226);
  v236 = ActiveBrokerById;
  if ( ActiveBrokerById
    && (!*(_DWORD *)(GetXdbServerGlobals(v4) + 11976) || byte_102EDCE86)
    && *((_DWORD *)ActiveBrokerById + 114) == 1
    && (v6 = *(_QWORD *)(qword_102ECFB00 + 43248), *(_DWORD *)(v6 + 80) != 3)
    && *(_DWORD *)(v6 + 80)
    && !*((_BYTE *)ActiveBrokerById + 231) )
  {
    v146 = *((_WORD *)ActiveBrokerById + 102);
    v192 = *(_DWORD *)(*((_QWORD *)v1 + 8) + 88LL);
    v147 = (volatile signed __int64 *)(*(_QWORD *)(qword_102ECFB00 + 43248) + 25144LL);
    v148 = 0;
    for ( *((_QWORD *)v1 + 18) = 0; ; operator delete[](*((void **)v1 + 18)) )
    {
      QuadPart = 0;
      UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)v147 || _InterlockedCompareExchange64(v147, UniqueThread_low, 0) )
      {
        v9 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v10 && *(_QWORD *)(v10 + 272) == v10 )
            v9 = *(_QWORD *)(v10 + 256);
          if ( v9 )
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
          Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v147, UniqueThread_low);
        else
          Spinlock<170,8,258>::SpinToAcquireOptimistic(v147, v9, UniqueThread_low);
        if ( v9 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v228);
            v11 = (CSbTransportMgr *)v228.QuadPart;
          }
          else
          {
            v11 = MEMORY[0x7FFE0008];
          }
          if ( v11 < QuadPart )
            v12 = 0;
          else
            v12 = v11 - QuadPart;
          *(_QWORD *)(v9 + 3192) += v12;
        }
      }
      v148 = 1;
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)v1 + 8) + 96LL) + 2 * v13) );
      v14 = 2 * v13;
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v15 = rand();
        if ( v15 == 5 * (v15 / 5) )
          Spinlock<170,8,258>::UpdateStatSnapshot();
      }
      *v147 = 0;
      v148 = 0;
      v16 = (v14 >> 1) + 1;
      v17 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v18 = *(_QWORD *)(v17 + 256);
      if ( !v18 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v18 = *(_QWORD *)(v17 + 256);
      }
      v19 = v16;
      v20 = 2LL * v16;
      if ( !is_mul_ok(v16, 2u) )
        v20 = -1;
      v21 = operator new[](
              v20,
              *(struct IMemObj **)(v18 + 1000),
              "sql\\ntdbms\\broker\\src\\ssbInternalActivation.cpp",
              1844,
              8u);
      v185 = (__int64)v21;
      v22 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v23 = *(_QWORD *)(v22 + 256);
      if ( !v23 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v23 = *(_QWORD *)(v22 + 256);
      }
      v24 = 2 * v19;
      if ( !is_mul_ok(v19, 2u) )
        v24 = -1;
      *((_QWORD *)v1 + 18) = operator new[](
                               v24,
                               *(struct IMemObj **)(v23 + 1000),
                               "sql\\ntdbms\\broker\\src\\ssbInternalActivation.cpp",
                               1845,
                               8u);
      v25 = 0;
      v26 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)v147 || _InterlockedCompareExchange64(v147, v26, 0) )
      {
        v27 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v28 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v28 && *(_QWORD *)(v28 + 272) == v28 )
            v27 = *(_QWORD *)(v28 + 256);
          if ( v27 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v229);
              v25 = (CSbTransportMgr *)v229.QuadPart;
            }
            else
            {
              v25 = MEMORY[0x7FFE0008];
            }
          }
        }
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<170,8,258>::SpinToAcquireWithExponentialBackoff(v147, v26);
        else
          Spinlock<170,8,258>::SpinToAcquireOptimistic(v147, v27, v26);
        if ( v27 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v230);
            v29 = (CSbTransportMgr *)v230.QuadPart;
          }
          else
          {
            v29 = MEMORY[0x7FFE0008];
          }
          if ( v29 < v25 )
            v30 = 0;
          else
            v30 = v29 - v25;
          *(_QWORD *)(v27 + 3192) += v30;
        }
        v21 = (void *)v185;
      }
      v148 = 1;
      v31 = *(const wchar_t **)(*((_QWORD *)v1 + 8) + 96LL);
      v32 = -1;
      do
        ++v32;
      while ( v31[v32] );
      if ( v14 == 2 * (_DWORD)v32 )
        break;
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v125 = rand();
        if ( v125 == 5 * (v125 / 5) )
          Spinlock<170,8,258>::UpdateStatSnapshot();
      }
      *v147 = 0;
      v148 = 0;
      operator delete[](v21);
    }
    v33 = CbParseQuotesW(v31, v14, (wchar_t *)v21, v14);
    v34 = (_WORD *)*((_QWORD *)v1 + 18);
    if ( v19 <= 0x7FFFFFFF )
    {
      v35 = 2147483646 - v19;
      v36 = *(_QWORD *)(*((_QWORD *)v1 + 8) + 96LL) - (_QWORD)v34;
      do
      {
        if ( !(v19 + v35) )
          break;
        v37 = *(_WORD *)((char *)v34 + v36);
        if ( !v37 )
          break;
        *v34++ = v37;
        --v19;
      }
      while ( v19 );
      v38 = v34 - 1;
      if ( v19 )
        v38 = v34;
      *v38 = 0;
    }
    else
    {
      *v34 = 0;
    }
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v39 = rand();
      if ( v39 == 5 * (v39 / 5) )
        Spinlock<170,8,258>::UpdateStatSnapshot();
    }
    *v147 = 0;
    v148 = 0;
    v235 = v21;
    WParseName::Parse((WParseName *)v388, (const wchar_t *)v21, v33);
    v242 = 0;
    v243 = 0;
    v244 = 0;
    v245 = 0;
    v246 = 0;
    v247 = 0;
    v248 = 1;
    v249 = 0;
    v250 = 1;
    v241 = &CSbActivationTaskExceptions::`vftable';
    v251 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                               + SystemThread_TlsIndex)
                                             + SystemThread_TlsOffset)
                                 + 128LL)
                     + 256LL);
    v40 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset)
                    + 112LL);
    v197 = 0;
    v198 = 0;
    v41 = *(void ****)(v40 + 24);
    if ( v41 != &v241 )
    {
      *(_QWORD *)&v197 = v40;
      *((_QWORD *)&v197 + 1) = v41;
      *(_QWORD *)&v198 = v242;
      *((_QWORD *)&v198 + 1) = &v241;
      v242 = v41;
      *(_QWORD *)(v40 + 24) = &v241;
    }
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v387, 0, 0, 0, (int (*)(int, int, int, int, char *))MSQLErrorHandlerFunc, 0);
      CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v139);
      v42 = *((_QWORD *)v1 + 8);
      v384 = v42;
      v385 = v42 + 208;
      v222 = *((_DWORD *)v1 + 26);
      v223 = *(_DWORD *)(v42 + 220) & (v222 + (v222 >> 20) + (v222 >> 10));
      v43 = *(_QWORD *)(v42 + 208) + 16LL * v223;
      v386[2] = v43;
      v386[3] = (char *)v1 + 88;
      v386[4] = v43;
      *((_QWORD *)v1 + 12) = *(_QWORD *)(v43 + 8);
      **(_QWORD **)(v43 + 8) = (char *)v1 + 88;
      *(_QWORD *)(v43 + 8) = (char *)v1 + 88;
      *((_QWORD *)v1 + 11) = v43;
      ++*(_DWORD *)(v42 + 224);
      v177 = CommonGlobalState::m_CollectingStatistics;
      if ( CommonGlobalState::m_CollectingStatistics && *(_BYTE *)(v42 + 244) )
      {
        v178 = CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
        {
          v386[5] = 1;
          v252 = qword_102ECFB00;
          v44 = PerfmonManager::IncrementCounterInstanceValue(
                  (PerfmonManager *)qword_102ECFB00,
                  0x1Fu,
                  0,
                  1,
                  *(unsigned __int16 *)(v42 + 116),
                  &v231);
          v224 = v44;
          v45 = *(unsigned __int16 *)(v42 + 116);
          v225 = v45;
          v253 = v231;
          v185 = 0x800000000LL;
          if ( (g_XeSqlPkg_enabledBitmap & 8) != 0 )
          {
            if ( v44 )
            {
              v191 = 1;
              v254 = v390;
              v390[0] = 0;
              v390[1] = 1;
              v391 = 0;
              v392 = &v395;
              v393 = &v399;
              v400 = 0;
              v401 = 0;
              v394 = 0;
              v402 = 0;
              v255 = &v395;
              v395 = &v403;
              v396 = 12;
              v397 = 0;
              v398 = 0;
              v403 = v231;
              v404 = v45;
              XeSqlPkg::broker_activation_task_started::Publish((XeSqlPkg::broker_activation_task_started *)v389);
            }
          }
        }
        v179 = CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
          PerfmonManager::IncrementCounterInstanceValue(
            (PerfmonManager *)qword_102ECFB00,
            0x1Fu,
            8u,
            1,
            *(unsigned __int16 *)(v42 + 116),
            0);
      }
      v46 = *(_DWORD *)(v42 + 128);
      v142 = v46;
      v47 = v139;
      v256 = v139;
      v180 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v48 = rand();
        if ( v48 == 5 * (v48 / 5) )
          Spinlock<165,9,258>::UpdateStatSnapshot();
      }
      v257 = v47;
      *v47 = 0;
      v140 = 0;
      v139 = 0;
      v49 = v146;
      v137 = SsbActivationTraceEvent((CSbActivationProcTask *)((char *)v1 + 152), v46, 0, 0, 1);
      while ( 1 )
      {
        v138 = 0;
        CSQLObject::CSQLObject((CSQLObject *)v421, (const struct WParseName *)v388, 1, 0, 1);
        v181 = CommonGlobalState::m_CollectingStatistics;
        if ( CommonGlobalState::m_CollectingStatistics )
        {
          v50 = *((_QWORD *)v1 + 8);
          if ( *(_BYTE *)(v50 + 244) )
          {
            v149 = CommonGlobalState::m_PerfCountersEnabled;
            if ( CommonGlobalState::m_PerfCountersEnabled )
            {
              v258 = 1;
              v259 = qword_102ECFB00;
              v51 = PerfmonManager::IncrementCounterInstanceValue(
                      (PerfmonManager *)qword_102ECFB00,
                      0x1Fu,
                      0x28u,
                      1,
                      *(unsigned __int16 *)(v50 + 116),
                      &v232);
              v233 = v51;
              v52 = *(unsigned __int16 *)(*((_QWORD *)v1 + 8) + 116LL);
              v234 = v52;
              v260 = v232;
              v188 = 0;
              v189 = 1;
              if ( (g_XeSqlPkg_enabledBitmap & 1) != 0 )
              {
                if ( v51 )
                {
                  v190 = 1;
                  v261 = v406;
                  v406[0] = 0;
                  v406[1] = 1;
                  v407 = 0;
                  v408 = &v411;
                  v409 = &v415;
                  v416 = 0;
                  v417 = 0;
                  v410 = 0;
                  v418 = 0;
                  v262 = &v411;
                  v411 = &v419;
                  v412 = 12;
                  v413 = 0;
                  v414 = 0;
                  v419 = v232;
                  v420 = v52;
                  XeSqlPkg::broker_activation_stored_procedure_invoked::Publish((XeSqlPkg::broker_activation_stored_procedure_invoked *)v405);
                }
              }
            }
          }
        }
        v237 = 88;
        ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
        v264 = (_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v265 = v264;
        v266 = *v264;
        v267 = v266;
        v53 = *(_QWORD *)(v266 + 128);
        v145 = v53;
        v144 = 0x400000;
        v54 = *(unsigned int *)(v53 + 80);
        v143 = (*(_DWORD *)(v53 + 80) & 0x400000) != 0;
        v268 = v53;
        LODWORD(v54) = v54 | 0x400000;
        *(_DWORD *)(v53 + 80) = v54;
        v55 = *(unsigned int *)(GetXdbServerGlobals(v54) + 8308);
        v238 = v55;
        if ( (_DWORD)v55 )
        {
          v239 = 88;
          v269 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v270 = (_QWORD *)(v269[SystemThread_TlsIndex] + SystemThread_TlsOffset);
          v271 = v270;
          v272 = *v270;
          v273 = v272;
          v56 = *(_QWORD *)(v272 + 72);
          v274 = v56;
          v193 = v56;
          v57 = *(_BYTE *)(v56 + 270);
          if ( (v57 & 4) != 0 )
          {
            v193 = 0;
          }
          else
          {
            v275 = v56;
            *(_BYTE *)(v56 + 270) = v57 | 4;
            *(_BYTE *)(v56 + 271) |= 1u;
            *(_DWORD *)(v56 + 404) = 1;
          }
          v240[6] = 88;
          v276 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v277 = (const struct CCompExecCtxtBasic **)(v276[SystemThread_TlsIndex] + SystemThread_TlsOffset);
          v278 = v277;
          v279 = *v277;
          v280 = v279;
          CSQLSource::Execute((CSQLSource *)v421, v279, 0, 0);
          v58 = v193;
          if ( v193 )
          {
            v281 = v193;
            *(_BYTE *)(v193 + 270) &= ~4u;
            *(_BYTE *)(v58 + 271) &= ~1u;
            *(_DWORD *)(v58 + 404) = 2;
          }
        }
        else
        {
          XdbServerGlobals = GetXdbServerGlobals(v55);
          v60 = NtCurrentTeb()->ThreadLocalStoragePointer;
          if ( *(_DWORD *)(XdbServerGlobals + 11976) )
          {
            v199 = 88;
            v287 = v60;
            v288 = (_QWORD *)(v60[SystemThread_TlsIndex] + SystemThread_TlsOffset);
            v289 = v288;
            v290 = *v288;
            v291 = v290;
            v61 = *(_QWORD *)(v290 + 72);
            v292 = v61;
            v194 = v61;
            v62 = *(_BYTE *)(v61 + 270);
            if ( (v62 & 0x10) != 0 )
            {
              v194 = 0;
            }
            else
            {
              v293 = v61;
              *(_BYTE *)(v61 + 270) = v62 | 0x10;
              *(_BYTE *)(v61 + 271) |= 2u;
            }
            v200 = 88;
            v294 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v295 = (const struct CCompExecCtxtBasic **)(v294[SystemThread_TlsIndex] + SystemThread_TlsOffset);
            v296 = v295;
            v297 = *v295;
            v298 = v297;
            CSQLSource::Execute((CSQLSource *)v421, v297, 0, 0);
            v63 = v194;
            if ( v194 )
            {
              v299 = v194;
              *(_BYTE *)(v194 + 270) &= ~0x10u;
              *(_BYTE *)(v63 + 271) &= ~2u;
            }
          }
          else
          {
            v240[7] = 88;
            v282 = v60;
            v283 = (const struct CCompExecCtxtBasic **)(v60[SystemThread_TlsIndex] + SystemThread_TlsOffset);
            v284 = v283;
            v285 = *v283;
            v286 = v285;
            CSQLSource::Execute((CSQLSource *)v421, v285, 0, 0);
          }
        }
        v201 = 88;
        v300 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v301 = (_QWORD *)(v300[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v302 = v301;
        v303 = *v301;
        v304 = v303;
        v196 = v303;
        v196 = *(_QWORD *)(v303 + 144);
        if ( (*(int (**)(void))(*(_QWORD *)v196 + 624LL))() > 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v196 + 32LL))(v196);
          CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v139);
          v64 = CSbQueueMonitor::ActivatedTaskAborting(*((_QWORD *)v1 + 8), v1, 0, 4);
          v142 = v64;
          v65 = v139;
          v305 = v139;
          v150 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v66 = rand();
            if ( v66 == 5 * (v66 / 5) )
              Spinlock<165,9,258>::UpdateStatSnapshot();
          }
          v306 = v65;
          *v65 = 0;
          v140 = 0;
          v139 = 0;
          if ( v137 )
            SsbActivationTraceEvent_0(0, v64, 8415, 10, 1, 0);
          v151 = v143;
          v202 = 0x400000;
          v307 = v145;
          v67 = *(_DWORD *)(v53 + 80);
          if ( v143 )
          {
            *(_DWORD *)(v53 + 80) = v67 | 0x400000;
            goto LABEL_223;
          }
          goto LABEL_201;
        }
        v182 = &AutoReadOnlyIMA::`vftable';
        v183 = 0;
        v308 = &v184;
        v309 = &v184;
        v184 = 0;
        AutoReadOnlyIMA::Init((AutoReadOnlyIMA *)&v182, L"CSbActivationProcTask::Invoke", 0x3Au, 0);
        v68 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v183 + 56LL))(
                v183,
                v49,
                0,
                0,
                0,
                0);
        LOBYTE(v136) = 1;
        LOBYTE(v135) = 0;
        LOBYTE(v69) = 1;
        v70 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int, int, _DWORD, _DWORD))(*(_QWORD *)v68 + 120LL))(
                v68,
                v192,
                v69,
                0,
                v135,
                v136,
                0,
                0);
        v310 = v70;
        if ( !v70 )
        {
          CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v139);
          v71 = *((_QWORD *)v1 + 8);
          v311 = v71;
          if ( *(_DWORD *)(v71 + 128) == ++*(_DWORD *)(v71 + 132) )
            *(_BYTE *)(v71 + 242) = 1;
          v72 = CSbQueueMonitor::ActivatedTaskEnded(*((_QWORD *)v1 + 8), v1, 4);
          v142 = v72;
          v73 = v139;
          v312 = v139;
          v152 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v74 = rand();
            if ( v74 == 5 * (v74 / 5) )
              Spinlock<165,9,258>::UpdateStatSnapshot();
          }
          v313 = v73;
          *v73 = 0;
          v140 = 0;
          v139 = 0;
          if ( v137 )
            SsbActivationTraceEvent_0((CSbActivationProcTask *)((char *)v1 + 152), v72, 28085, 10, 1, 0);
          AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v182);
          v75 = v143;
          v153 = v143;
          v203 = 0x400000;
          v314 = v145;
LABEL_134:
          v67 = *(_DWORD *)(v53 + 80);
          if ( v75 )
          {
            *(_DWORD *)(v53 + 80) = v67 | 0x400000;
            goto LABEL_223;
          }
LABEL_201:
          *(_DWORD *)(v53 + 80) = v67 & 0xFFBFFFFF;
          goto LABEL_223;
        }
        v315 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v70 + 192LL))(v70);
        (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v315 + 8LL))(v315, v186);
        if ( (v187 & 1) == 0 || (v187 & 2) == 0 )
        {
          CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v139);
          v115 = *((_QWORD *)v1 + 8);
          v371 = v115;
          if ( *(_DWORD *)(v115 + 128) == ++*(_DWORD *)(v115 + 132) )
            *(_BYTE *)(v115 + 242) = 1;
          v116 = CSbQueueMonitor::ActivatedTaskEnded(*((_QWORD *)v1 + 8), v1, 4);
          v142 = v116;
          v117 = v139;
          v372 = v139;
          v174 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v118 = rand();
            if ( v118 == 5 * (v118 / 5) )
              Spinlock<165,9,258>::UpdateStatSnapshot();
          }
          v373 = v117;
          *v117 = 0;
          v140 = 0;
          v139 = 0;
          if ( v137 )
            SsbActivationTraceEvent_0((CSbActivationProcTask *)((char *)v1 + 152), v116, 28086, 10, 1, 0);
          AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v182);
          v113 = v143;
          v175 = v143;
          v220 = 0x400000;
          v114 = v145;
          v374 = v145;
          goto LABEL_220;
        }
        v204 = 88;
        v316 = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
        v76 = 8LL * SystemThread_TlsIndex;
        v317 = (_QWORD *)(SystemThread_TlsOffset + *(_QWORD *)&v316[v76]);
        v318 = v317;
        v319 = *v317;
        v320 = v319;
        v77 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v319 + 128) + 256LL) + 4LL);
        v205 = v77;
        if ( !v77 )
        {
          CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v139);
          v78 = CSbQueueMonitor::ActivatedTaskAborting(*((_QWORD *)v1 + 8), v1, 0, 4);
          v142 = v78;
          v79 = v139;
          v321 = v139;
          v154 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v80 = rand();
            if ( v80 == 5 * (v80 / 5) )
              Spinlock<165,9,258>::UpdateStatSnapshot();
          }
          v322 = v79;
          *v79 = 0;
          v140 = 0;
          v139 = 0;
          if ( v137 )
            SsbActivationTraceEvent_0(0, v78, 28087, 10, 1, 0);
          AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v182);
          v75 = v143;
          v155 = v143;
          v206 = 0x400000;
          v323 = v145;
          goto LABEL_134;
        }
        if ( v77 == 2 )
        {
          CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v139);
          v81 = v139;
          if ( *(_DWORD *)(*((_QWORD *)v1 + 8) + 128LL) <= *(__int16 *)(*((_QWORD *)v1 + 8) + 112LL) )
          {
            v324 = v139;
            v156 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v82 = rand();
              if ( v82 == 5 * (v82 / 5) )
                Spinlock<165,9,258>::UpdateStatSnapshot();
            }
            *v81 = 0;
            v140 = 0;
            v139 = 0;
            AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v182);
            v157 = v143;
            v207 = 0x400000;
            v325 = v145;
            v83 = *(_DWORD *)(v53 + 80);
            if ( v143 )
              v84 = v83 | 0x400000;
            else
              v84 = v83 & 0xFFBFFFFF;
            goto LABEL_153;
          }
          v326 = v139;
          v158 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v85 = rand();
            if ( v85 == 5 * (v85 / 5) )
              Spinlock<165,9,258>::UpdateStatSnapshot();
          }
          *v81 = 0;
          v140 = 0;
          v139 = 0;
        }
        else
        {
          v208 = 88;
          v327 = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
          v328 = (_QWORD *)(SystemThread_TlsOffset + *(_QWORD *)&v327[v76]);
          v329 = v328;
          v330 = *v328;
          v331 = v330;
          v332 = *(_WORD **)(*(_QWORD *)(v330 + 128) + 256LL);
          ++*v332;
        }
        v141 = 0;
        CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v139);
        v86 = *((_QWORD *)v1 + 8);
        v333 = v86;
        v87 = *(_DWORD *)(v86 + 128) == ++*(_DWORD *)(v86 + 132);
        if ( *(_DWORD *)(v86 + 128) == *(_DWORD *)(v86 + 132) )
          *(_BYTE *)(v86 + 242) = 1;
        v88 = v139;
        v334 = v139;
        v159 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v89 = rand();
          if ( v89 == 5 * (v89 / 5) )
            Spinlock<165,9,258>::UpdateStatSnapshot();
        }
        *v88 = 0;
        v140 = 0;
        v139 = 0;
        v138 = 1;
        v141 = 1;
        if ( !v87 )
          break;
        v209 = 88;
        v335 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v336 = (_QWORD *)(v335[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v337 = v336;
        v338 = *v336;
        v339 = v338;
        v90 = *((_QWORD *)v1 + 8);
        if ( **(_WORD **)(*(_QWORD *)(v338 + 128) + 256LL) >= 2u )
        {
          CSbQueueMonitor::GetSpinLock(v90, &v139);
          v104 = *((_QWORD *)v1 + 8);
          if ( *(_BYTE *)(v104 + 242) == 1 )
          {
            v105 = CSbQueueMonitor::ActivatedTaskEnded(*((_QWORD *)v1 + 8), v1, 4);
            v142 = v105;
            v106 = v139;
            v357 = v139;
            v168 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v107 = rand();
              if ( v107 == 5 * (v107 / 5) )
                Spinlock<165,9,258>::UpdateStatSnapshot();
            }
            v358 = v106;
            *v106 = 0;
            v140 = 0;
            v139 = 0;
            if ( v137 )
              SsbActivationTraceEvent((CSbActivationProcTask *)((char *)v1 + 152), v105, 0, 0, 0);
            AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v182);
            v75 = v143;
            v169 = v143;
            v216 = 0x400000;
            v359 = v145;
            goto LABEL_134;
          }
          v360 = *((_QWORD *)v1 + 8);
          --*(_DWORD *)(v104 + 132);
          v108 = v139;
          v361 = v139;
          v170 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v109 = rand();
            if ( v109 == 5 * (v109 / 5) )
              Spinlock<165,9,258>::UpdateStatSnapshot();
          }
          *v108 = 0;
          v140 = 0;
          v139 = 0;
          v217 = 88;
          v362 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v363 = (_QWORD *)(v362[SystemThread_TlsIndex] + SystemThread_TlsOffset);
          v364 = v363;
          v365 = *v363;
          v366 = v365;
          **(_WORD **)(*(_QWORD *)(v365 + 128) + 256LL) = 0;
          AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v182);
          v100 = v143;
          v171 = v143;
          v218 = 0x400000;
          v367 = v145;
        }
        else
        {
          v91 = CSbQueueMonitor::ScanQueue(v90);
          v210 = v91;
          if ( ((v91 - 2) & 0xFFFFFFFD) != 0 )
          {
            CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v139);
            if ( v91 == 3 )
            {
              CSbQueueMonitor::ActivatedTaskAborting(*((_QWORD *)v1 + 8), v1, 1, 0);
              v92 = v139;
              v340 = v139;
              v160 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
              if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v93 = rand();
                if ( v93 == 5 * (v93 / 5) )
                  Spinlock<165,9,258>::UpdateStatSnapshot();
              }
              v341 = v92;
              *v92 = 0;
              v140 = 0;
              v139 = 0;
              if ( v137 )
                SsbActivationTraceEvent(0, v142, 0, 0, 0);
              AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v182);
              v75 = v143;
              v161 = v143;
              v211 = 0x400000;
              v342 = v145;
              goto LABEL_134;
            }
            v94 = *((_QWORD *)v1 + 8);
            if ( *(_BYTE *)(v94 + 242) == 1 )
            {
              v95 = CSbQueueMonitor::ActivatedTaskEnded(*((_QWORD *)v1 + 8), v1, v91);
              v142 = v95;
              v96 = v139;
              v343 = v139;
              v162 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
              if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v97 = rand();
                if ( v97 == 5 * (v97 / 5) )
                  Spinlock<165,9,258>::UpdateStatSnapshot();
              }
              v344 = v96;
              *v96 = 0;
              v140 = 0;
              v139 = 0;
              if ( v137 )
                SsbActivationTraceEvent((CSbActivationProcTask *)((char *)v1 + 152), v95, 0, 0, 0);
              AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v182);
              v75 = v143;
              v163 = v143;
              v212 = 0x400000;
              v345 = v145;
              goto LABEL_134;
            }
            if ( v141 )
            {
              v346 = *((_QWORD *)v1 + 8);
              --*(_DWORD *)(v94 + 132);
            }
            v98 = v139;
            v347 = v139;
            v164 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v99 = rand();
              if ( v99 == 5 * (v99 / 5) )
                Spinlock<165,9,258>::UpdateStatSnapshot();
            }
            *v98 = 0;
            v140 = 0;
            v139 = 0;
            v213 = 88;
            v348 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v349 = (_QWORD *)(v348[SystemThread_TlsIndex] + SystemThread_TlsOffset);
            v350 = v349;
            v351 = *v349;
            v352 = v351;
            **(_WORD **)(*(_QWORD *)(v351 + 128) + 256LL) = 0;
            AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v182);
            v100 = v143;
            v165 = v143;
            v214 = 0x400000;
            v353 = v145;
          }
          else
          {
            CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v139);
            v354 = *((_QWORD *)v1 + 8);
            --*(_DWORD *)(v354 + 132);
            v102 = v139;
            v355 = v139;
            v166 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v103 = rand();
              if ( v103 == 5 * (v103 / 5) )
                Spinlock<165,9,258>::UpdateStatSnapshot();
            }
            *v102 = 0;
            v140 = 0;
            v139 = 0;
            AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v182);
            v100 = v143;
            v167 = v143;
            v215 = 0x400000;
            v356 = v145;
          }
        }
        v101 = *(_DWORD *)(v53 + 80);
        if ( v100 )
          v84 = v101 | 0x400000;
        else
          v84 = v101 & 0xFFBFFFFF;
LABEL_153:
        *(_DWORD *)(v53 + 80) = v84;
        CSQLObject::~CSQLObject((CSQLObject *)v421);
      }
      CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v139);
      v110 = CSbQueueMonitor::ActivatedTaskEnded(*((_QWORD *)v1 + 8), v1, 4);
      v142 = v110;
      v111 = v139;
      v368 = v139;
      v172 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v112 = rand();
        if ( v112 == 5 * (v112 / 5) )
          Spinlock<165,9,258>::UpdateStatSnapshot();
      }
      v369 = v111;
      *v111 = 0;
      v140 = 0;
      v139 = 0;
      if ( v137 )
        SsbActivationTraceEvent((CSbActivationProcTask *)((char *)v1 + 152), v110, 0, 0, 0);
      AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v182);
      v113 = v143;
      v173 = v143;
      v219 = 0x400000;
      v114 = v145;
      v370 = v145;
LABEL_220:
      if ( v113 )
        *(_DWORD *)(v114 + 80) |= 0x400000u;
      else
        *(_DWORD *)(v114 + 80) &= ~0x400000u;
LABEL_223:
      CSQLObject::~CSQLObject((CSQLObject *)v421);
      ExcHandler::~ExcHandler((ExcHandler *)v387);
    }
    catch ( SQLError v240 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v386, (const struct SQLError *)v240);
        v130 = v195;
        CSbQueueMonitor::GetSpinLock(*((_QWORD *)v195 + 8), &v139);
        v131 = CSbQueueMonitor::ActivatedTaskAborting(*((_QWORD *)v130 + 8), v130, v138, 0);
        v142 = v131;
        v132 = v139;
        v375 = v139;
        v176 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v133 = rand();
          if ( v133 == 5 * (v133 / 5) )
            Spinlock<165,9,258>::UpdateStatSnapshot();
        }
        v376 = v132;
        *v132 = 0;
        v140 = 0;
        if ( v137 )
          SsbActivationTraceEvent_0(0, v131, 28088, 16, 1, 0);
        v221 = 88;
        v377 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v378 = (_QWORD *)(v377[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v379 = v378;
        v380 = *v378;
        v381 = v380;
        v134 = *(_QWORD *)(v380 + 128);
        v382 = v134;
        *(_BYTE *)(v134 + 296) = 0;
        *(_DWORD *)(v134 + 76) &= ~0x2000000u;
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v386);
      }
      catch ( ShortStackException )
      {
      }
      v1 = v195;
    }
    v119 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v120 = *(struct Worker **)(v119 + 256);
    if ( !v120 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v120 = *(struct Worker **)(v119 + 256);
    }
    if ( *((_DWORD *)v120 + 139) )
      ExceptionPostCatchActions(v120);
    v121 = v197;
    if ( (_QWORD)v197 )
    {
      *(_QWORD *)(*(_QWORD *)(v197 + 24) + 8LL) = v198;
      *(_QWORD *)(v121 + 24) = *((_QWORD *)&v197 + 1);
      v197 = 0;
      v198 = 0;
    }
    v241 = &CConnectionOutput::`vftable';
    operator delete[](v235);
    v122 = v147;
    if ( v147 && v148 )
    {
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v123 = rand();
        if ( v123 == 5 * (v123 / 5) )
          Spinlock<170,8,258>::UpdateStatSnapshot();
      }
      *v122 = 0;
      v147 = 0;
      v148 = 0;
    }
    if ( v236 )
      (*(void (__fastcall **)(struct CActiveServiceBroker *))(*(_QWORD *)v236 + 56LL))(v236);
    v124 = v139;
  }
  else
  {
    CSbQueueMonitor::GetSpinLock(*((_QWORD *)v1 + 8), &v139);
    v126 = *((_QWORD *)v1 + 8);
    if ( *(_DWORD *)(v126 + 128) == ++*(_DWORD *)(v126 + 132) )
      *(_BYTE *)(v126 + 242) = 1;
    v142 = CSbQueueMonitor::ActivatedTaskEnded(*((_QWORD *)v1 + 8), v1, 4);
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v127 = rand();
      if ( v127 == 5 * (v127 / 5) )
        Spinlock<165,9,258>::UpdateStatSnapshot();
    }
    *v139 = 0;
    v140 = 0;
    v124 = 0;
    v139 = 0;
    if ( ActiveBrokerById )
      (*(void (__fastcall **)(struct CActiveServiceBroker *))(*(_QWORD *)ActiveBrokerById + 56LL))(ActiveBrokerById);
  }
  v128 = (void *)*((_QWORD *)v1 + 18);
  if ( v128 )
  {
    operator delete[](v128);
    *((_QWORD *)v1 + 18) = 0;
  }
  if ( v124 && v140 )
  {
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v129 = rand();
      if ( v129 == 5 * (v129 / 5) )
        Spinlock<165,9,258>::UpdateStatSnapshot();
    }
    *v124 = 0;
    v139 = 0;
    v140 = 0;
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
