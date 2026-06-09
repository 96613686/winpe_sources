# process_request(IBatch *,SNI_Conn *,RequestType)

- ea: `0x100416ce0`
- end: `0x10041754c`
- name: `?process_request@@YA?AW4ECommandResult@@PEAVIBatch@@PEAVSNI_Conn@@W4RequestType@@@Z`
- size: `2156`
- prototype: ``
- caller_count: `0`
- callee_count: `35`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x100401070`
- `0x1004012d0`
- `0x100401340`
- `0x100401450`
- `0x100402d00`
- `0x1004035f0`
- `0x10040f190`
- `0x100416ce0`
- `0x1004190d0`
- `0x100419190`
- `0x100419220`
- `0x1004196c0`
- `0x100419a80`
- `0x10041a970`
- `0x10041abe0`
- `0x10041ac30`
- `0x10041ad00`
- `0x10041ad50`
- `0x10041b0c0`
- `0x10041b290`
- `0x10041b2e0`
- `0x10041b4f0`
- `0x1004572d0`
- `0x100457420`
- `0x10055a5d0`
- `0x100561a30`
- `0x1007a74d0`
- `0x100f039c0`
- `0x100f06750`
- `0x100f069e0`
- `0x100f06d70`
- `0x100f300e0`
- `0x10113af00`
- `0x101e88db0`
- `0x101e899b0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100419587`
- `KERNEL32!QueryPerformanceCounter` at `0x100f06f48`
- `KERNEL32!QueryPerformanceCounter` at `0x100f074aa`
- `KERNEL32!QueryPerformanceCounter` at `0x100f0756d`
- `KERNEL32!QueryPerformanceCounter` at `0x100f07d03`
- `KERNEL32!QueryPerformanceCounter` at `0x100419587`
- `KERNEL32!QueryPerformanceCounter` at `0x100f06f48`
- `KERNEL32!QueryPerformanceCounter` at `0x100f074aa`
- `KERNEL32!QueryPerformanceCounter` at `0x100f0756d`
- `KERNEL32!QueryPerformanceCounter` at `0x100f07d03`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x100f071a9`
- `sqldk!?sm_isResourceManagerEnabled@SOS_PublicGlobals@@2HA` at `0x100417244`
- `sqldk!?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A` at `0x100527634`
- `sqldk!?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A` at `0x100f07dcd`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x100419607`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x10041963a`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x100f07670`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x100f07d99`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x100f07e50`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100419572`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004195ec`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f06f2c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f0748a`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f0754d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f0765c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f07ceb`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f07d6e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f07e39`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f07eba`
- `sqldk!?SignalCookie@SOS_WaitableAddress@@SAXQEBX@Z` at `0x100f07bad`
- `sqldk!?SignalCookie@SOS_WaitableAddress@@SAXQEBX@Z` at `0x100f07bad`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x100456cc5`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100f06f1b`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100f06f1b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100f0786a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100f07ac0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100f0786a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100f07ac0`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f07380`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f0798b`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f07a7e`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f07380`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f0798b`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f07a7e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100f06e9f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100f06f02`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100f0710f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100f0719d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100f07306`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100f07404`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100f07771`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100f06e9f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100f06f02`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100f0710f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100f0719d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100f07306`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100f07404`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100f07771`
- `sqldk!SystemThread_TlsIndex` at `0x10041707b`
- `sqldk!SystemThread_TlsIndex` at `0x1004171f6`
- `sqldk!SystemThread_TlsIndex` at `0x1004174c1`
- `sqldk!SystemThread_TlsIndex` at `0x1004193dc`
- `sqldk!SystemThread_TlsIndex` at `0x100419545`
- `sqldk!SystemThread_TlsIndex` at `0x100455fbc`
- `sqldk!SystemThread_TlsIndex` at `0x100456d66`
- `sqldk!SystemThread_TlsIndex` at `0x100f07200`
- `sqldk!SystemThread_TlsIndex` at `0x100f077e4`
- `sqldk!SystemThread_TlsIndex` at `0x100f07ae7`
- `sqldk!SystemThread_TlsIndex` at `0x100f07cb3`
- `sqldk!SystemThread_TlsOffset` at `0x100417084`
- `sqldk!SystemThread_TlsOffset` at `0x1004171ff`
- `sqldk!SystemThread_TlsOffset` at `0x1004174ca`
- `sqldk!SystemThread_TlsOffset` at `0x1004193e5`
- `sqldk!SystemThread_TlsOffset` at `0x10041954e`
- `sqldk!SystemThread_TlsOffset` at `0x100455fc5`
- `sqldk!SystemThread_TlsOffset` at `0x100456d6f`
- `sqldk!SystemThread_TlsOffset` at `0x100f07209`
- `sqldk!SystemThread_TlsOffset` at `0x100f077ed`
- `sqldk!SystemThread_TlsOffset` at `0x100f07af0`
- `sqldk!SystemThread_TlsOffset` at `0x100f07cbc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f07007`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f07365`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f07818`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f07978`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f07a6b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f07b0b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f07cd7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f07e96`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f07007`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f07365`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f07818`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f07978`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f07a6b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f07b0b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f07cd7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f07e96`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100f0724f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100f0724f`
- `sqldk!?AccountForRequestCompletion@SOS_ResourceGroup@@QEAAXXZ` at `0x100419536`
- `sqldk!?AccountForRequestCompletion@SOS_ResourceGroup@@QEAAXXZ` at `0x100f07ca4`
- `sqldk!?AccountForRequestCompletion@SOS_ResourceGroup@@QEAAXXZ` at `0x100419536`
- `sqldk!?AccountForRequestCompletion@SOS_ResourceGroup@@QEAAXXZ` at `0x100f07ca4`
- `sqldk!?AccountForWorkerCompletion@SOS_ResourceGroup@@QEAAXG@Z` at `0x100419518`
- `sqldk!?AccountForWorkerCompletion@SOS_ResourceGroup@@QEAAXG@Z` at `0x100f07c86`
- `sqldk!?AccountForWorkerCompletion@SOS_ResourceGroup@@QEAAXG@Z` at `0x100419518`
- `sqldk!?AccountForWorkerCompletion@SOS_ResourceGroup@@QEAAXG@Z` at `0x100f07c86`
- `sqldk!?AccountForNewWorkerRequest@SOS_ResourceGroup@@QEAA?AW4SOS_RESULT@@HG@Z` at `0x10041726f`
- `sqldk!?AccountForNewWorkerRequest@SOS_ResourceGroup@@QEAA?AW4SOS_RESULT@@HG@Z` at `0x10041726f`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x100f072d0`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x100f072d0`
- `sqlmin!LatencyHistRecordCompletion` at `0x100f07799`
- `sqlmin!LatencyHistRecordCompletion` at `0x100f07799`
- `sqlmin!?SETaskSuspendingNotification@@YAXXZ` at `0x100f07447`
- `sqlmin!?SETaskSuspendingNotification@@YAXXZ` at `0x100f07447`
- `sqlmin!?IsSptEnforcementOn@@YA_NXZ` at `0x1004172f7`
- `sqlmin!?IsSptEnforcementOn@@YA_NXZ` at `0x1004172f7`
- `sqlmin!?EnforceAtRequestStart@SptPolicing@@QEAAXXZ` at `0x100f0731a`
- `sqlmin!?EnforceAtRequestStart@SptPolicing@@QEAAXXZ` at `0x100f0731a`
- `sqlmin!?AccountForQueryThreadUsage@@YAX_N@Z` at `0x100416dc8`
- `sqlmin!?AccountForQueryThreadUsage@@YAX_N@Z` at `0x1004194fa`
- `sqlmin!?AccountForQueryThreadUsage@@YAX_N@Z` at `0x100f07c68`
- `sqlmin!?AccountForQueryThreadUsage@@YAX_N@Z` at `0x100416dc8`
- `sqlmin!?AccountForQueryThreadUsage@@YAX_N@Z` at `0x1004194fa`
- `sqlmin!?AccountForQueryThreadUsage@@YAX_N@Z` at `0x100f07c68`
- `sqlmin!?IsLatchAcqRelTrackingExpensive@LatchBase@@SAHXZ` at `0x100419249`
- `sqlmin!?IsLatchAcqRelTrackingExpensive@LatchBase@@SAHXZ` at `0x100419249`
- `sqlmin!GetXdbServerGlobals` at `0x100f07126`
- `sqlmin!GetXdbServerGlobals` at `0x100f074cb`
- `sqlmin!GetXdbServerGlobals` at `0x100f07126`
- `sqlmin!GetXdbServerGlobals` at `0x100f074cb`
- `hkruntime!HkRtGetSystem` at `0x100f077b5`
- `hkruntime!HkRtGetSystem` at `0x100f078f5`
- `hkruntime!HkRtGetSystem` at `0x100f077b5`
- `hkruntime!HkRtGetSystem` at `0x100f078f5`
- `hkengine!HkSystemHelpGarbageCollector` at `0x100f077c6`
- `hkengine!HkSystemHelpGarbageCollector` at `0x100f07906`
- `hkengine!HkSystemHelpGarbageCollector` at `0x100f077c6`
- `hkengine!HkSystemHelpGarbageCollector` at `0x100f07906`

## string_xrefs

- `0x100f07722`: `ConnectionResiliency: Session was not killed. Task Aborted while killing session`

## pseudocode

```c
// Hidden C++ exception states: #wind=26 #try_helpers=1
__int64 __fastcall process_request(LARGE_INTEGER a1, struct SNI_Conn *a2, unsigned int a3)
{
  struct CBatch *QuadPart; // rdi
  LARGE_INTEGER v6; // rbx
  struct CConnection *v7; // r14
  __int64 v8; // rax
  __int64 v9; // rax
  SOS_LsAccessCache *v10; // rcx
  __int64 v11; // r15
  char v12; // r14
  struct CConnection *v13; // rdx
  void ***v14; // rcx
  int v15; // ebx
  struct CSession *v16; // rax
  LARGE_INTEGER v17; // r12
  __int64 v18; // rbx
  int v19; // r14d
  bool v20; // al
  unsigned __int64 v21; // rdx
  int v22; // eax
  LARGE_INTEGER v23; // r13
  __int16 v24; // ax
  BOOL v25; // r15d
  __int64 v26; // rbx
  __int64 v27; // r14
  __int64 v28; // r14
  unsigned int v29; // ebx
  __int64 v30; // rcx
  __int64 v31; // r15
  CBatchExecEnv *v32; // rbx
  __int64 v33; // rdx
  struct CExecLevel *v34; // rcx
  __int64 v35; // r14
  __int64 v36; // rbx
  struct Worker *v37; // rcx
  struct CConnection *v38; // r14
  struct CNetConnection *v39; // rax
  unsigned __int64 v40; // r12
  _QWORD *v41; // rcx
  DataVirtualizationResource *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rbx
  struct Worker *v45; // rcx
  __int64 v46; // rcx
  char v47; // al
  int v48; // ebx
  unsigned int v49; // r14d
  SOS_ResourceGroup *v50; // rbx
  __int64 v51; // rbx
  __int64 v52; // rax
  _QWORD *v53; // rbx
  CSbTransportMgr *v54; // rax
  __int64 v55; // rcx
  unsigned __int64 v56; // r8
  unsigned __int64 v57; // rdx
  unsigned __int64 v58; // r9
  unsigned __int64 v59; // rcx
  char *v60; // rdx
  char *v61; // rcx
  char *v62; // rcx
  _DWORD *v63; // r9
  unsigned __int64 v64; // r8
  unsigned __int64 v65; // rdx
  unsigned int v67; // eax
  _DWORD *v68; // rcx
  CBatchExecEnv *v69; // rbx
  bool v70; // zf
  struct CConnection *v71; // rbx
  int v72; // edx
  struct CExecLevel *v73; // rcx
  __int64 v74; // rbx
  struct Worker *v75; // rcx
  int v76; // r15d
  _QWORD *v77; // rcx
  LARGE_INTEGER v78; // rdi
  __int64 v79; // rbx
  __int64 v80; // rax
  unsigned int v81; // eax
  __int64 v82; // rbx
  bool v83; // cl
  unsigned __int8 v84; // al
  bool v85; // dl
  int v86; // eax
  unsigned int KillReasonForCloudError; // eax
  int v88; // r9d
  unsigned int v89; // r8d
  __int64 v90; // rcx
  struct CNetConnection *v91; // rax
  struct SNI_Conn *v92; // r9
  struct SNI_Conn *v93; // r8
  CSbTransportMgr *v94; // rax
  __m128i v95; // xmm6
  __int64 v96; // rax
  struct CSessionTraceFlags *v97; // rcx
  __int64 v98; // rax
  __int64 v99; // rdx
  int v100; // ebx
  __int64 v101; // rcx
  CSbTransportMgr *v102; // rax
  int v103; // r15d
  int v104; // r14d
  __int64 v105; // r8
  __int64 v106; // r9
  CSbTransportMgr *v107; // rdx
  unsigned __int64 v108; // rdx
  unsigned __int64 v109; // rdx
  __int64 v110; // rbx
  __int64 v111; // rax
  __int64 v112; // rbx
  __int64 v113; // rax
  __int64 v114; // rcx
  __int64 v115; // rcx
  __int64 v116; // rbx
  __int64 v117; // r15
  int v118; // eax
  int v119; // ebx
  int v120; // eax
  int v121; // eax
  int v122; // eax
  SOS_ResourceGroup *v123; // rbx
  __int64 v124; // rbx
  __int64 v125; // rax
  _QWORD *v126; // rbx
  CSbTransportMgr *v127; // rax
  __int64 v128; // rcx
  unsigned __int64 v129; // r9
  unsigned __int64 v130; // r8
  unsigned __int64 v131; // rdx
  char *v132; // rcx
  unsigned __int64 v133; // rax
  char *v134; // rcx
  char *v135; // rcx
  unsigned __int64 v136; // r8
  _DWORD *v137; // r9
  unsigned __int64 v138; // rdx
  __int64 v139; // rcx
  const struct SQLError *CurrentException; // rax
  int (*v141)(int, int, int, int, char *); // [rsp+20h] [rbp-758h]
  struct Worker *v142; // [rsp+28h] [rbp-750h]
  __int64 v143; // [rsp+30h] [rbp-748h]
  bool v144; // [rsp+40h] [rbp-738h] BYREF
  char v145; // [rsp+41h] [rbp-737h]
  char v146; // [rsp+42h] [rbp-736h]
  unsigned __int8 v147; // [rsp+43h] [rbp-735h]
  bool v148; // [rsp+44h] [rbp-734h] BYREF
  char v149; // [rsp+45h] [rbp-733h]
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp-730h] BYREF
  unsigned int v151; // [rsp+50h] [rbp-728h]
  unsigned int v152; // [rsp+54h] [rbp-724h]
  unsigned int v153; // [rsp+58h] [rbp-720h]
  struct CExecLevel *v154; // [rsp+60h] [rbp-718h] BYREF
  __int16 v155; // [rsp+68h] [rbp-710h]
  unsigned int v156; // [rsp+6Ch] [rbp-70Ch]
  int v157; // [rsp+70h] [rbp-708h]
  int v158; // [rsp+74h] [rbp-704h]
  CBatchExecEnv *BatchExecEnv; // [rsp+78h] [rbp-700h]
  struct CConnection *v160; // [rsp+80h] [rbp-6F8h]
  __int64 v161; // [rsp+88h] [rbp-6F0h]
  unsigned __int8 v162; // [rsp+90h] [rbp-6E8h]
  bool v164; // [rsp+93h] [rbp-6E5h]
  int v165; // [rsp+94h] [rbp-6E4h] BYREF
  int v166; // [rsp+98h] [rbp-6E0h]
  LARGE_INTEGER v167; // [rsp+A0h] [rbp-6D8h] BYREF
  __int64 v168; // [rsp+A8h] [rbp-6D0h]
  struct CParamExchange *v169; // [rsp+B0h] [rbp-6C8h] BYREF
  SOS_ResourceGroup *v170; // [rsp+B8h] [rbp-6C0h] BYREF
  __int64 v171; // [rsp+C0h] [rbp-6B8h]
  unsigned __int64 v172; // [rsp+C8h] [rbp-6B0h]
  int v173; // [rsp+D0h] [rbp-6A8h]
  int v174; // [rsp+D4h] [rbp-6A4h]
  unsigned __int64 v175; // [rsp+E0h] [rbp-698h]
  unsigned int v176; // [rsp+E8h] [rbp-690h]
  unsigned int v177; // [rsp+F0h] [rbp-688h] BYREF
  int v178; // [rsp+F4h] [rbp-684h]
  unsigned int v179; // [rsp+FCh] [rbp-67Ch]
  int v180; // [rsp+100h] [rbp-678h]
  unsigned __int64 v181; // [rsp+108h] [rbp-670h]
  __int64 v182; // [rsp+110h] [rbp-668h]
  __int64 v183; // [rsp+118h] [rbp-660h]
  LARGE_INTEGER v184; // [rsp+138h] [rbp-640h]
  int v185; // [rsp+140h] [rbp-638h]
  unsigned __int16 v186; // [rsp+144h] [rbp-634h]
  int v187; // [rsp+148h] [rbp-630h]
  int v188; // [rsp+14Ch] [rbp-62Ch]
  unsigned int v189; // [rsp+150h] [rbp-628h]
  __int64 v190; // [rsp+158h] [rbp-620h]
  int v191; // [rsp+160h] [rbp-618h]
  unsigned __int128 v192; // [rsp+168h] [rbp-610h]
  __int128 v193; // [rsp+178h] [rbp-600h]
  void **v194; // [rsp+190h] [rbp-5E8h] BYREF
  void ***v195; // [rsp+198h] [rbp-5E0h]
  int v196; // [rsp+1A0h] [rbp-5D8h]
  __int64 v197; // [rsp+1A8h] [rbp-5D0h]
  __int64 v198; // [rsp+1B0h] [rbp-5C8h]
  int v199; // [rsp+1B8h] [rbp-5C0h]
  int v200; // [rsp+1BCh] [rbp-5BCh]
  __int64 v201; // [rsp+1C0h] [rbp-5B8h]
  char v202; // [rsp+1C8h] [rbp-5B0h]
  __int64 v203; // [rsp+1D0h] [rbp-5A8h]
  _QWORD v204[2]; // [rsp+1D8h] [rbp-5A0h] BYREF
  int v205; // [rsp+1E8h] [rbp-590h]
  __int64 v206; // [rsp+1F0h] [rbp-588h]
  char *v207; // [rsp+200h] [rbp-578h] BYREF
  __time64_t Time[2]; // [rsp+208h] [rbp-570h] BYREF
  _DWORD v209[6]; // [rsp+218h] [rbp-560h] BYREF
  int v210; // [rsp+230h] [rbp-548h]
  int v211; // [rsp+234h] [rbp-544h]
  int v212; // [rsp+238h] [rbp-540h]
  int v213; // [rsp+23Ch] [rbp-53Ch]
  int v214; // [rsp+240h] [rbp-538h]
  int v215; // [rsp+248h] [rbp-530h]
  int v216; // [rsp+250h] [rbp-528h]
  int v217; // [rsp+254h] [rbp-524h]
  LARGE_INTEGER v218; // [rsp+270h] [rbp-508h] BYREF
  CSbTransportMgr *v219; // [rsp+278h] [rbp-500h]
  CSbTransportMgr *v220; // [rsp+280h] [rbp-4F8h]
  unsigned __int64 v221; // [rsp+288h] [rbp-4F0h]
  __int64 v222; // [rsp+290h] [rbp-4E8h]
  __int64 v223; // [rsp+298h] [rbp-4E0h]
  struct Worker *v224; // [rsp+2A0h] [rbp-4D8h]
  LARGE_INTEGER v225; // [rsp+2A8h] [rbp-4D0h] BYREF
  CSbTransportMgr *v226; // [rsp+2B0h] [rbp-4C8h]
  CSbTransportMgr *v227; // [rsp+2B8h] [rbp-4C0h]
  LARGE_INTEGER v228; // [rsp+2C0h] [rbp-4B8h] BYREF
  CSbTransportMgr *v229; // [rsp+2C8h] [rbp-4B0h]
  CSbTransportMgr *v230; // [rsp+2D0h] [rbp-4A8h]
  CSbTransportMgr *v231; // [rsp+2D8h] [rbp-4A0h]
  struct CNetConnection *v232; // [rsp+2E0h] [rbp-498h]
  CSbTransportMgr *v233; // [rsp+2E8h] [rbp-490h] BYREF
  __int64 v234; // [rsp+2F0h] [rbp-488h]
  __int64 v235; // [rsp+2F8h] [rbp-480h]
  BOOL v236; // [rsp+300h] [rbp-478h]
  char **System; // [rsp+308h] [rbp-470h]
  int v238; // [rsp+310h] [rbp-468h]
  int v239; // [rsp+318h] [rbp-460h]
  int v240; // [rsp+320h] [rbp-458h]
  unsigned int RequestThrottlingSeverity; // [rsp+324h] [rbp-454h]
  unsigned int v242; // [rsp+328h] [rbp-450h]
  int v243; // [rsp+32Ch] [rbp-44Ch]
  LARGE_INTEGER v244; // [rsp+330h] [rbp-448h] BYREF
  __int128 v245; // [rsp+338h] [rbp-440h]
  __int128 v246; // [rsp+348h] [rbp-430h]
  __int64 v247; // [rsp+358h] [rbp-420h]
  int v248; // [rsp+360h] [rbp-418h]
  int v249; // [rsp+370h] [rbp-408h] BYREF
  __int16 v250; // [rsp+374h] [rbp-404h]
  __int64 v251; // [rsp+378h] [rbp-400h]
  __int16 v252; // [rsp+380h] [rbp-3F8h]
  __int64 v253; // [rsp+388h] [rbp-3F0h]
  int v254; // [rsp+390h] [rbp-3E8h]
  __int64 v255; // [rsp+398h] [rbp-3E0h]
  __int64 v256; // [rsp+3A0h] [rbp-3D8h]
  unsigned __int64 v257; // [rsp+3A8h] [rbp-3D0h]
  int v258; // [rsp+3B0h] [rbp-3C8h]
  _BYTE v259[16]; // [rsp+3C0h] [rbp-3B8h] BYREF
  __m128i si128; // [rsp+3D0h] [rbp-3A8h] BYREF
  int v261; // [rsp+3E0h] [rbp-398h]
  int v262; // [rsp+3E8h] [rbp-390h] BYREF
  __int64 v263; // [rsp+3F0h] [rbp-388h]
  __int64 v264; // [rsp+3F8h] [rbp-380h]
  __int64 v265; // [rsp+400h] [rbp-378h]
  __int64 v266; // [rsp+408h] [rbp-370h]
  _QWORD *v268; // [rsp+418h] [rbp-360h]
  __int64 v269; // [rsp+420h] [rbp-358h]
  unsigned __int64 v270; // [rsp+428h] [rbp-350h]
  union _LARGE_INTEGER v271; // [rsp+430h] [rbp-348h]
  unsigned __int64 v272; // [rsp+438h] [rbp-340h]
  _QWORD *v273; // [rsp+440h] [rbp-338h]
  __int64 v274; // [rsp+448h] [rbp-330h]
  _QWORD *v275; // [rsp+450h] [rbp-328h]
  __int64 v276; // [rsp+458h] [rbp-320h]
  __int64 v277; // [rsp+460h] [rbp-318h]
  _QWORD *v278; // [rsp+468h] [rbp-310h]
  _QWORD *v279; // [rsp+470h] [rbp-308h]
  __int64 v280; // [rsp+478h] [rbp-300h]
  __int64 v281; // [rsp+480h] [rbp-2F8h]
  __int64 v282; // [rsp+488h] [rbp-2F0h]
  _QWORD *v283; // [rsp+490h] [rbp-2E8h]
  _QWORD *v284; // [rsp+498h] [rbp-2E0h]
  _QWORD *v285; // [rsp+4A0h] [rbp-2D8h]
  _QWORD *v287; // [rsp+4B0h] [rbp-2C8h]
  _QWORD *v288; // [rsp+4B8h] [rbp-2C0h]
  _QWORD *v289; // [rsp+4C0h] [rbp-2B8h]
  __int64 v290; // [rsp+4C8h] [rbp-2B0h]
  __int64 v291; // [rsp+4D0h] [rbp-2A8h]
  __int64 v292; // [rsp+4D8h] [rbp-2A0h]
  __int64 v293; // [rsp+4E0h] [rbp-298h]
  _QWORD *v294; // [rsp+4E8h] [rbp-290h]
  __int64 *v295; // [rsp+4F0h] [rbp-288h]
  __int64 v296; // [rsp+4F8h] [rbp-280h]
  _DWORD *v297; // [rsp+500h] [rbp-278h]
  _QWORD *v298; // [rsp+508h] [rbp-270h]
  void (*v299)(const wchar_t *, ...); // [rsp+560h] [rbp-218h]
  _BYTE v300[32]; // [rsp+568h] [rbp-210h] BYREF
  _QWORD *ThreadLocalStoragePointer; // [rsp+588h] [rbp-1F0h]
  __int64 *v302; // [rsp+590h] [rbp-1E8h]
  unsigned __int64 v303; // [rsp+598h] [rbp-1E0h]
  _QWORD *v304; // [rsp+5A0h] [rbp-1D8h]
  _QWORD *v305; // [rsp+5A8h] [rbp-1D0h]
  __int64 v306; // [rsp+5B0h] [rbp-1C8h]
  __int64 *v307; // [rsp+5B8h] [rbp-1C0h]
  __int64 v308; // [rsp+5C0h] [rbp-1B8h]
  struct CSessionTraceFlags *v309; // [rsp+5C8h] [rbp-1B0h]
  _WORD *v310; // [rsp+5D0h] [rbp-1A8h]
  __m128i v311; // [rsp+5D8h] [rbp-1A0h]
  _BYTE v312[40]; // [rsp+5E8h] [rbp-190h] BYREF
  _BYTE v313[24]; // [rsp+610h] [rbp-168h] BYREF
  _BYTE v314[40]; // [rsp+628h] [rbp-150h] BYREF
  _QWORD v315[26]; // [rsp+650h] [rbp-128h] BYREF

  v277 = -2;
  QuadPart = (struct CBatch *)a1.QuadPart;
  v167 = a1;
  v184 = a1;
  BatchExecEnv = 0;
  v6 = *(LARGE_INTEGER *)(a1.QuadPart + 24);
  PerformanceCount = v6;
  v160 = *(struct CConnection **)(a1.QuadPart + 32);
  v7 = v160;
  v244 = v6;
  v245 = 0;
  v246 = 0;
  v247 = 0;
  v248 = 0;
  v144 = 0;
  v156 = 0;
  v152 = 0;
  v153 = 0;
  v158 = 0;
  v166 = 0;
  v154 = 0;
  v169 = 0;
  v151 = 2;
  *(_DWORD *)(a1.QuadPart + 196) = 0;
  v148 = 0;
  v157 = 0;
  v190 = 0;
  v171 = 0;
  AccountForQueryThreadUsage(1);
  v173 = 0;
  v8 = *((_QWORD *)v7 + 3);
  v195 = 0;
  v196 = 0;
  v197 = 0;
  v198 = 0;
  v199 = 0;
  v200 = 1;
  v201 = 0;
  v202 = 1;
  v203 = v8;
  v194 = &CDeferMsgsAndEnvChangesConn::`vftable';
  v205 = 0;
  v204[1] = v204;
  v204[0] = v204;
  v206 = 0;
  *(_BYTE *)(*((_QWORD *)v7 + 3) + 56LL) = 1;
  v9 = *((_QWORD *)v7 + 3);
  v10 = (SOS_LsAccessCache *)(v9 + 48);
  if ( !*(_BYTE *)(v9 + 56) )
    v10 = 0;
  SOS_LsAccessCache::Init(v10);
  v11 = *(_QWORD *)((*(__int64 (__fastcall **)(struct CBatch *))(*(_QWORD *)QuadPart + 72LL))(QuadPart) + 368);
  v12 = 0;
  v149 = 0;
  v145 = 0;
  if ( !byte_102EDCB77
    || (v91 = (struct CNetConnection *)(*(__int64 (__fastcall **)(struct CBatch *))(*(_QWORD *)QuadPart + 72LL))(QuadPart),
        v146 = 1,
        !CheckIfConnectionShouldBeKilled(v91)) )
  {
    v146 = 0;
  }
  v147 = 0;
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v314, 0, 0, 0, (int (*)(int, int, int, int, char *))MSQLErrorHandlerFunc, 0);
    v192 = 0;
    v193 = 0;
    v13 = v160;
    v14 = (void ***)*((_QWORD *)v160 + 3);
    if ( v14 != &v194 )
    {
      v192 = __PAIR128__((unsigned __int64)v14, (unsigned __int64)v160);
      *(_QWORD *)&v193 = v195;
      *((_QWORD *)&v193 + 1) = &v194;
      v195 = v14;
      *((_QWORD *)v160 + 3) = &v194;
    }
    *((_DWORD *)QuadPart + 49) = 1;
    if ( (*(_BYTE *)(v11 + 48) & 2) != 0 && (*(_DWORD *)(v11 + 964) & 0x400000) != 0 )
    {
      v12 = 1;
      v149 = 1;
      if ( (unsigned int)SOS_RWLock::GetLock(v6.QuadPart + 1152, 2, 0xFFFFFFFFLL, &unk_102FD5BF8) )
        ex_raise(36, 1, 25, 17);
      v145 = 1;
    }
    v15 = *(_DWORD *)(v6.QuadPart + 260);
    v236 = v15 != 0;
    v185 = v15;
    CSession::NotifyBatchStart((CSession *)PerformanceCount.QuadPart, v13, v236);
    v16 = (struct CSession *)PerformanceCount.QuadPart;
    *(_BYTE *)(PerformanceCount.QuadPart + 4950) = 1;
    if ( v15 )
    {
      v92 = a2;
      v17 = PerformanceCount;
      ResetConnAndRedoLogin((struct CSession *)PerformanceCount.QuadPart, QuadPart, v160, v92, &v148);
    }
    else if ( *((_BYTE *)v16 + 259) )
    {
      v93 = a2;
      v17.QuadPart = (LONGLONG)v16;
      if ( !(unsigned int)FRedoLogin(v16, QuadPart, v93) )
        ex_raise(40, 3, 25, 14);
    }
    else
    {
      v17.QuadPart = (LONGLONG)v16;
    }
    v145 = v12;
    if ( v12 )
    {
      SOS_RWLock::ReleaseLock(v17.QuadPart + 1152, 2);
      v145 = 0;
    }
    if ( *((char *)qword_102ECFB10 + 1239) < 0 )
    {
      v238 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v218);
        v94 = (CSbTransportMgr *)v218.QuadPart;
      }
      else
      {
        v94 = MEMORY[0x7FFE0008];
        v219 = MEMORY[0x7FFE0008];
      }
      v220 = v94;
      v233 = v94;
    }
    *((_DWORD *)QuadPart + 49) = 2;
    CBatch::ResetPasswordMaskingHints(QuadPart);
    v164 = (*(_BYTE *)(v17.QuadPart + 272) & 0x10) != 0;
    if ( !CAutoSetupCXCtxtS::FInit((CAutoSetupCXCtxtS *)&v244, QuadPart, &v144, 1, v164) )
    {
      v40 = -1;
      v23 = PerformanceCount;
      goto LABEL_67;
    }
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v302 = (__int64 *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset);
    v223 = *v302;
    v182 = v223;
    v183 = *(_QWORD *)(v223 + 128);
    v18 = v183;
    v249 &= ~1u;
    v250 = 0;
    v251 = 0;
    v252 = 0;
    v253 = 0;
    v254 = 0;
    v255 = 0;
    v256 = 0;
    v257 = 0;
    v258 = 0;
    v165 = 0;
    CheckTerminate((struct CSession *)v17.QuadPart, QuadPart);
    BatchExecEnv = (CBatchExecEnv *)CBatch::GetBatchExecEnv(QuadPart, v18, a3);
    *((_DWORD *)QuadPart + 49) = 3;
    if ( *(_WORD *)(v17.QuadPart + 184) >= 5u )
    {
      if ( v185 != 1 || v148 )
      {
        v19 = 0;
        v191 = 0;
      }
      else
      {
        v19 = 1;
        v191 = 1;
      }
      CProtocolHeaderInfo::ReadTdsHeaders(&v249, QuadPart, a3);
      v20 = (*(_DWORD *)(v11 + 964) & 0x400000) != 0;
      if ( (*(_DWORD *)(v11 + 964) & 0x400000) == 0 || (*(_BYTE *)(v11 + 48) & 2) != 0 )
      {
        if ( v19 )
        {
          *(_QWORD *)(v18 + 512) = 0;
          *(_DWORD *)(v18 + 520) = 1;
        }
        else
        {
          v21 = v257;
          v221 = v257;
          if ( v20 && v257 )
          {
            v21 = ((unsigned __int64)(unsigned int)*(__int16 *)(v17.QuadPart + 16) << 32) + (unsigned int)v257;
            v303 = v21;
            v221 = v21;
          }
          v22 = v258;
          v239 = v258;
          *(_QWORD *)(v18 + 512) = v21;
          *(_DWORD *)(v18 + 520) = v22;
        }
        *(_DWORD *)(v18 + 76) |= 2u;
      }
    }
    v23 = PerformanceCount;
    if ( (*(_BYTE *)(PerformanceCount.QuadPart + 270) & 4) != 0 )
      v24 = *(_WORD *)(PerformanceCount.QuadPart + 972);
    else
      v24 = 0;
    v155 = v24;
    v25 = v24 == 0;
    v305 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v26 = v305[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v306 = v26;
    v27 = *(_QWORD *)(v26 + 256);
    v222 = v27;
    if ( !v27 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v27 = *(_QWORD *)(v26 + 256);
      v222 = v27;
    }
    v28 = *(_QWORD *)(v27 + 536);
    v168 = v28;
    v29 = 0;
    v176 = 0;
    v240 = SOS_PublicGlobals::sm_isResourceManagerEnabled;
    if ( SOS_PublicGlobals::sm_isResourceManagerEnabled )
    {
      v170 = (SOS_ResourceGroup *)v28;
      v29 = SOS_ResourceGroup::AccountForNewWorkerRequest(v28, v25, 1);
      v176 = v29;
      if ( v29 )
      {
        if ( v29 == -2113929216 )
        {
          v310 = (_WORD *)(GetXdbServerGlobals(v30) + 14190);
          if ( !*v310 )
            v29 = 0x80000000;
          v176 = v29;
        }
      }
      else
      {
        HIDWORD(v171) = 1;
      }
    }
    if ( v29 == 0x80000000 )
    {
      if ( *((_BYTE *)qword_102EF3550 + 1652) )
      {
        v311 = *(__m128i *)(v28 + 3352);
        v95 = v311;
        traceprint(L" [process_request] : Resource Group name %s\n", v28 + 260);
        traceprint(L" [process_request] : Resource Group Id %d\n", *(unsigned int *)(v28 + 164));
        LODWORD(v142) = (unsigned __int16)_mm_extract_epi16(v95, 5);
        LODWORD(v141) = (unsigned __int16)_mm_extract_epi16(v95, 4);
        traceprint(
          L" [process_request] : Resource Group Start Time [%4d-%02d-%02d %02d-%02d-%02d]\n ",
          (unsigned __int16)_mm_cvtsi128_si32(v95),
          (unsigned __int16)_mm_extract_epi16(v95, 1),
          (unsigned __int16)_mm_extract_epi16(v95, 3),
          v141,
          v142,
          (unsigned __int16)_mm_extract_epi16(v95, 6));
        traceprint(L" [process_request] : Resource Group Max Workers %d\n", *(unsigned __int16 *)(v28 + 148));
      }
      RequestThrottlingSeverity = GetRequestThrottlingSeverity((struct CSession *)v23.QuadPart, v160);
      LODWORD(v143) = *(unsigned __int16 *)(v28 + 148);
      LODWORD(v141) = 1;
      ex_raise(109, 28, RequestThrottlingSeverity, 1, v141, L"request", v143);
    }
    else if ( v29 == -2113929216 )
    {
      v242 = GetRequestThrottlingSeverity((struct CSession *)v23.QuadPart, v160);
      LODWORD(v141) = 1;
      ex_raise(109, 36, v242, 1, v141, L"request", *(unsigned __int16 *)(*(_QWORD *)(v28 + 3336) + 304LL));
    }
    else if ( !v155 )
    {
      v187 = *(_DWORD *)(v28 + 3380);
      if ( v187 == *(__int16 *)(v168 + 3372) + 1 )
      {
        v299 = SOS_OS_LogUnlocalizedRoutine;
        SOS_OS_LogUnlocalizedRoutine(L"Ignoring request limit check\n");
        v173 = 1;
      }
      v28 = v168;
    }
    if ( *(_DWORD *)(qword_102ECFB00 + 14504) )
    {
      if ( !byte_102EDCC6F && (*((_BYTE *)qword_102ECFB10 + 1294) & 8) == 0 )
      {
        v304 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v307 = (__int64 *)(v304[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v96 = *v307;
        v308 = v96;
        if ( !v96 || (v97 = **(struct CSessionTraceFlags ***)(v96 + 56), (v309 = v97) == 0) )
        {
          v28 = v168;
          goto LABEL_38;
        }
        v243 = CSessionTraceFlags::CheckSessionTraceInternal(v97, 0x2873u);
        v28 = v168;
        if ( !v243 )
          goto LABEL_38;
      }
      if ( (*(__int64 (__fastcall **)(struct CBatch *))(*(_QWORD *)QuadPart + 72LL))(QuadPart) )
      {
        v98 = (*(__int64 (__fastcall **)(struct CBatch *))(*(_QWORD *)QuadPart + 72LL))(QuadPart);
        LOBYTE(v99) = 2;
        if ( CPhysicalConnection::GetFeatureExtension(*(_QWORD *)(v98 + 368), v99) )
        {
          Time[0] = 0;
          v210 = *(_DWORD *)(*(_QWORD *)((*(__int64 (__fastcall **)(struct CBatch *))(*(_QWORD *)QuadPart + 72LL))(QuadPart)
                                       + 368)
                           + 52LL);
          v100 = v210;
          _time64(Time);
          if ( v100 > 0 && Time[0] > v100 + 300 )
            ex_raise(373, 96, 16, 1);
        }
      }
    }
LABEL_38:
    if ( IsSptEnforcementOn() )
      SptPolicing::EnforceAtRequestStart(*(SptPolicing **)(v23.QuadPart + 1080));
    *((_DWORD *)QuadPart + 49) = 4;
    v31 = *((_QWORD *)QuadPart + 15);
    v190 = v31;
    (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v31 + 752LL))(
      v31,
      *(_QWORD *)(v23.QuadPart + 648),
      v183);
    *((_DWORD *)QuadPart + 49) = 5;
    if ( !v173 )
      CAutoAccountGroupUsage::AccountGroupUsage(
        (CAutoAccountGroupUsage *)&v170,
        (struct SOS_ResourceGroup *)v28,
        (int (*)(void *))CSession::FCanBeThrottledStatic,
        (void *)v23.QuadPart);
    *((_DWORD *)QuadPart + 49) = 6;
    v32 = BatchExecEnv;
    v154 = (struct CExecLevel *)(*(__int64 (__fastcall **)(CBatchExecEnv *, __int64, struct CParamExchange **, int *))(*(_QWORD *)BatchExecEnv + 8LL))(
                                  BatchExecEnv,
                                  v223,
                                  &v169,
                                  &v165);
    *((_DWORD *)QuadPart + 49) = 7;
    v33 = v192;
    if ( (_QWORD)v192 )
    {
      *(_QWORD *)(*(_QWORD *)(v192 + 24) + 8LL) = v193;
      *(_QWORD *)(v33 + 24) = *((_QWORD *)&v192 + 1);
      v192 = 0;
      v193 = 0;
    }
    CDeferMsgsAndEnvChangesConn::FlushDeferred((CDeferMsgsAndEnvChangesConn *)&v194);
    v157 = 1;
    CBatchExecEnv::BatchSetup(v32, (struct CProtocolHeaderInfo *)&v249);
    v34 = v154;
    v35 = v182;
    while ( v34 )
    {
      *((_DWORD *)QuadPart + 49) = 8;
      *((_DWORD *)v34 + 6) &= ~8u;
      *((_DWORD *)v34 + 6) |= 4u;
      (*(void (__fastcall **)(CBatchExecEnv *))(*(_QWORD *)v32 + 24LL))(v32);
      try
      {
        *((_DWORD *)QuadPart + 49) = 9;
        (*(void (__fastcall **)(struct CExecLevel *, __int64, struct CParamExchange *, _QWORD))(*(_QWORD *)v154 + 152LL))(
          v154,
          v35,
          v169,
          0);
        if ( (*(unsigned __int8 (__fastcall **)(struct CExecLevel *))(*(_QWORD *)v154 + 144LL))(v154) )
        {
          *(_DWORD *)(v184.QuadPart + 196) = 11;
        }
        else
        {
          (*(void (__fastcall **)(CBatchExecEnv *, __int64, struct CExecLevel **, struct CParamExchange *))(*(_QWORD *)v32 + 32LL))(
            v32,
            v35,
            &v154,
            v169);
          *(_DWORD *)(v184.QuadPart + 196) = 10;
        }
      }
      catch ( SQLError v313 )
      {
        try
        {
          ExceptionBackout::ExceptionBackout((ExceptionBackout *)v259, (const struct SQLError *)v313);
          v139 = v183;
          v162 = *(_BYTE *)(v183 + 296);
          if ( v162 <= 2u )
          {
            *(_DWORD *)(v167.QuadPart + 196) = 11;
            *(_BYTE *)(v139 + 296) = 0;
            *(_DWORD *)(v139 + 76) &= ~0x2000000u;
          }
          else
          {
            CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v259);
            ExceptionRethrow(CurrentException);
          }
          ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v259);
        }
        catch ( ShortStackException )
        {
          JUMPOUT(0x100456A2FLL);
        }
        QuadPart = (struct CBatch *)v167.QuadPart;
        v23 = PerformanceCount;
      }
      v268 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v36 = v268[SystemThread_TlsIndex] + SystemThread_TlsOffset;
      v269 = v36;
      v37 = *(struct Worker **)(v36 + 256);
      v224 = v37;
      if ( !v37 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v37 = *(struct Worker **)(v36 + 256);
        v224 = v37;
      }
      if ( *((_DWORD *)v37 + 139) )
        ExceptionPostCatchActions(v37);
      if ( *((_DWORD *)QuadPart + 49) == 11 )
      {
        if ( (*((_DWORD *)v154 + 6) & 8) == 0 )
          (*(void (__fastcall **)(struct CExecLevel *))(*(_QWORD *)v154 + 160LL))(v154);
        *((_DWORD *)QuadPart + 49) = 12;
        v32 = BatchExecEnv;
        CBatchExecEnv::OnExecError(BatchExecEnv, &v154, v169, 0);
      }
      else
      {
        v32 = BatchExecEnv;
      }
      v34 = 0;
      v154 = 0;
      *((_DWORD *)QuadPart + 49) = 6;
      if ( !v165 )
        goto LABEL_56;
      if ( *(_BYTE *)(v23.QuadPart + 258) )
      {
        v144 = 1;
        v156 = 12;
        v152 = 4068;
        v153 = 1;
        ex_raise(40, 68, 20, 1);
        v34 = v154;
LABEL_56:
        v35 = v182;
        goto LABEL_57;
      }
      v35 = v182;
      v34 = (struct CExecLevel *)(*(__int64 (__fastcall **)(CBatchExecEnv *, __int64, struct CParamExchange **, int *))(*(_QWORD *)v32 + 16LL))(
                                   v32,
                                   v182,
                                   &v169,
                                   &v165);
      v154 = v34;
LABEL_57:
      v31 = v190;
    }
    if ( (unsigned int)LatchBase::IsLatchAcqRelTrackingExpensive() )
      SETaskSuspendingNotification();
    *((_DWORD *)QuadPart + 49) = 13;
    (*(void (__fastcall **)(CBatchExecEnv *))(*(_QWORD *)v32 + 40LL))(v32);
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v31 + 760LL))(v31, *(_QWORD *)(v35 + 128), v151);
    *((_DWORD *)QuadPart + 49) = 14;
    v38 = v160;
    CConnectionOutput::UnstructuredEndResultSet(*((CConnectionOutput **)v160 + 3), 0, 0, 0, 1);
    v39 = (struct CNetConnection *)(*(__int64 (__fastcall **)(struct CBatch *))(*(_QWORD *)QuadPart + 72LL))(QuadPart);
    v232 = v39;
    if ( !byte_102EDCB77
      || !CheckIfConnectionShouldBeKilled(v39)
      || (v146 = 1, !byte_102EDCB75)
      || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v31 + 624LL))(v31) )
    {
      v40 = -1;
      goto LABEL_62;
    }
    v101 = (unsigned int)Base_PublicGlobals::sm_invariantTscAvailable;
    v211 = Base_PublicGlobals::sm_invariantTscAvailable;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v225);
      v102 = (CSbTransportMgr *)v225.QuadPart;
      v227 = (CSbTransportMgr *)v225.QuadPart;
    }
    else
    {
      v102 = MEMORY[0x7FFE0008];
      v226 = MEMORY[0x7FFE0008];
      v227 = MEMORY[0x7FFE0008];
      v32 = BatchExecEnv;
    }
    v231 = v102;
    v103 = 3 * *(_DWORD *)(GetXdbServerGlobals(v101) + 8220);
    v188 = v103;
    CBatch::SetBatchExecState(QuadPart, 19);
    v147 = 1;
    v262 = 4195612;
    v263 = 0;
    v265 = 0;
    v264 = 0;
    v266 = 0;
    v104 = 0;
    v174 = 0;
    v40 = -1;
    while ( 2 )
    {
      if ( v104 != 2
        && !(*(unsigned __int8 (__fastcall **)(LONGLONG))(*(_QWORD *)(v23.QuadPart + 80) + 48LL))(v23.QuadPart + 80) )
      {
        v212 = Base_PublicGlobals::sm_invariantTscAvailable;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v228);
          v107 = (CSbTransportMgr *)v228.QuadPart;
          v230 = (CSbTransportMgr *)v228.QuadPart;
        }
        else
        {
          v229 = MEMORY[0x7FFE0008];
          v107 = MEMORY[0x7FFE0008];
          v230 = MEMORY[0x7FFE0008];
          v32 = BatchExecEnv;
          v103 = v188;
          v104 = v174;
        }
        if ( v107 < v231 )
          v108 = 0;
        else
          v108 = v107 - v231;
        v181 = v108;
        v270 = v108;
        if ( v108 == -1 )
        {
          v109 = -1;
          goto LABEL_197;
        }
        v213 = Base_PublicGlobals::sm_invariantTscAvailable;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          v271 = Base_PublicGlobals::sm_QueryPerformanceFrequency;
          v109 = 1000 * v108 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
          v181 = v109;
        }
        else
        {
          v109 = v108 / 0x2710;
          v272 = v109;
LABEL_197:
          v181 = v109;
        }
        if ( v109 >= v103 )
          break;
        v104 = SOS_Task::Sleep(100, &v262, v105, v106);
        v174 = v104;
        *(_BYTE *)(v23.QuadPart + 4950) = 0;
        continue;
      }
      break;
    }
    if ( (*(unsigned __int8 (__fastcall **)(LONGLONG))(*(_QWORD *)(v23.QuadPart + 80) + 48LL))(v23.QuadPart + 80) )
    {
      *((_DWORD *)v232 + 267) = 1;
      log_unlocalized_systemmetadata(L"%ls", L"ConnectionResiliency: Session killed");
      v38 = v160;
    }
    else
    {
      if ( v104 == 2 )
        log_unlocalized_systemmetadata(
          L"%ls",
          L"ConnectionResiliency: Session was not killed. Task Aborted while killing session");
      else
        log_unlocalized_systemmetadata(L"ConnectionResiliency: Session was not killed within %d ms", (unsigned int)v103);
      v38 = v160;
    }
LABEL_62:
    *((_DWORD *)QuadPart + 49) = 15;
    CBatchExecEnv::BatchCleanup(v32);
    (**(void (__fastcall ***)(CBatchExecEnv *, _QWORD))v32)(v32, 0);
    *((_DWORD *)QuadPart + 49) = 16;
    CAutoSetupCXCtxtS::Teardown((CAutoSetupCXCtxtS *)&v244);
    if ( *(_BYTE *)(v23.QuadPart + 258) )
    {
      *((_DWORD *)QuadPart + 49) = 17;
      if ( !(unsigned int)FCleanSessionForReuseDontKeepCtxt(QuadPart, (struct CSession *)v23.QuadPart, v38) )
        ex_raise(40, 3, 25, 15);
    }
    *((_DWORD *)QuadPart + 49) = 18;
    CSession::NotifyBatchFinish((CSession *)v23.QuadPart);
    v41 = (_QWORD *)*((_QWORD *)v38 + 3);
    v273 = v41;
    v41[4] = 0;
    (*(void (__fastcall **)(_QWORD *, _QWORD, _QWORD))(*v41 + 424LL))(v41, 0, v147);
    v42 = qword_102ECFB10;
    if ( *((char *)qword_102ECFB10 + 1239) < 0 && qword_103095800 )
    {
      LatencyHistRecordCompletion(qword_103095800, &v233, 0);
      v42 = qword_102ECFB10;
    }
    if ( (*((_BYTE *)v42 + 1233) & 0x40) == 0 && *(_BYTE *)(v183 + 600) )
    {
      if ( (*((_BYTE *)v42 + 1243) & 2) != 0 )
      {
        v275 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v110 = v275[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v276 = v110;
        v111 = *(_QWORD *)(v110 + 256);
        v234 = v111;
        if ( !v111 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v111 = *(_QWORD *)(v110 + 256);
          v234 = v111;
        }
        v186 = *(_WORD *)(*(_QWORD *)(v111 + 992) + 160LL);
        v112 = v186;
        if ( v186 != 64 )
        {
          if ( v186 >= 0x40u )
            utassert_fail(1u, "nodeId < MAX_NODES", "\"sql\\\\ntdbms\\\\msql\\\\ods\\\\c_events.cpp\"", 2449, 0);
          v207 = &byte_1030957C0[v112];
          if ( !_InterlockedCompareExchange8(&byte_1030957C0[v112], 1, 0) )
          {
            System = &v207;
            v315[1] = &v207;
            v315[0] = off_102813C70;
            v278 = v315;
            System = (char **)HkRtGetSystem();
            HkSystemHelpGarbageCollector(System);
            (*(void (__fastcall **)(_QWORD *))(v315[0] + 8LL))(v315);
          }
        }
      }
      else
      {
        v274 = HkRtGetSystem();
        HkSystemHelpGarbageCollector(v274);
      }
    }
    *(_BYTE *)(v183 + 600) = 0;
    *((_DWORD *)QuadPart + 49) = 21;
    CProtocolHeaderInfo::~CProtocolHeaderInfo((CProtocolHeaderInfo *)&v249);
LABEL_67:
    v43 = v192;
    if ( (_QWORD)v192 )
    {
      *(_QWORD *)(*(_QWORD *)(v192 + 24) + 8LL) = v193;
      *(_QWORD *)(v43 + 24) = *((_QWORD *)&v192 + 1);
      v192 = 0;
      v193 = 0;
    }
    ExcHandler::~ExcHandler((ExcHandler *)v314);
  }
  catch ( SQLError v177 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v300, (const struct SQLError *)&v177);
      if ( v167.QuadPart && *(_DWORD *)(v167.QuadPart + 196) == 19 )
        *(_DWORD *)(v167.QuadPart + 196) = 20;
      v78 = PerformanceCount;
      if ( v145 )
        SOS_RWLock::ReleaseLock(PerformanceCount.QuadPart + 1152, 2);
      if ( (int)v177 / 100 == 29 )
      {
        v214 = 88;
        v279 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v79 = v279[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v280 = v79;
        v80 = *(_QWORD *)(v79 + 256);
        v235 = v80;
        if ( !v80 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v80 = *(_QWORD *)(v79 + 256);
          v235 = v80;
        }
        v281 = v80;
        v215 = -33;
        v282 = v80 + 800;
        *(_DWORD *)(v80 + 800) &= ~0x20u;
        v166 = 1;
        v144 = 1;
        v156 = 13;
        if ( v180 == 1 )
          v81 = v177;
        else
          v81 = (unsigned __int16)v177;
        v152 = v81;
        v153 = v179;
        v158 = v178;
      }
      v216 = 88;
      v283 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v284 = (_QWORD *)(SystemThread_TlsOffset + v283[SystemThread_TlsIndex]);
      v285 = v284;
      if ( *v284 )
      {
        v217 = 88;
        v287 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v288 = (_QWORD *)(SystemThread_TlsOffset + v287[SystemThread_TlsIndex]);
        v289 = v288;
        v290 = *v288;
        v291 = v290;
        v82 = *(_QWORD *)(v290 + 128);
        v292 = v82;
        if ( v82 )
        {
          v83 = v144 || *(_BYTE *)(v82 + 296) >= 8u;
          v144 = v83;
          v84 = *(_BYTE *)(v82 + 296);
          v85 = v84 >= 7u || v84 == 5;
          v86 = v151;
          if ( v85 )
            v86 = 1;
          v151 = v86;
          if ( v83 && !v156 && (*(_BYTE *)(v78.QuadPart + 270) & 4) != 0 )
          {
            KillReasonForCloudError = (*(__int64 (__fastcall **)(LONGLONG))(*(_QWORD *)(v78.QuadPart + 80) + 56LL))(v78.QuadPart + 80);
            v189 = KillReasonForCloudError;
            v88 = v180;
            v89 = v177;
            if ( KillReasonForCloudError <= 1 )
            {
              if ( v180 == 1 )
                v90 = v177;
              else
                v90 = (unsigned __int16)v177;
              KillReasonForCloudError = GetKillReasonForCloudError(v90);
              v189 = KillReasonForCloudError;
            }
            v156 = KillReasonForCloudError;
            if ( v88 != 1 )
              v89 = (unsigned __int16)v89;
            v152 = v89;
            v153 = v179;
            v158 = v178;
          }
          *(_BYTE *)(v82 + 296) = 0;
          *(_DWORD *)(v82 + 76) &= ~0x2000000u;
        }
      }
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v300);
    }
    catch ( ShortStackException )
    {
    }
    v40 = -1;
    QuadPart = (struct CBatch *)v167.QuadPart;
    v23 = PerformanceCount;
  }
  v44 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v45 = *(struct Worker **)(v44 + 256);
  if ( !v45 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v45 = *(struct Worker **)(v44 + 256);
  }
  if ( *((_DWORD *)v45 + 139) )
    ExceptionPostCatchActions(v45);
  v46 = *((_QWORD *)QuadPart + 15);
  if ( !v46 || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v46 + 624LL))(v46) )
    *(_BYTE *)(v23.QuadPart + 4950) = 0;
  if ( v144
    || (v47 = (*(__int64 (__fastcall **)(LONGLONG))(*(_QWORD *)(v23.QuadPart + 80) + 48LL))(v23.QuadPart + 80)) != 0
    || *(_BYTE *)(v23.QuadPart + 265)
    || *((int *)QuadPart + 49) < 1 )
  {
    (*(void (__fastcall **)(LONGLONG, _QWORD, _QWORD, _QWORD))(*(_QWORD *)(v23.QuadPart + 80) + 40LL))(
      v23.QuadPart + 80,
      v156,
      v152,
      v153);
    v47 = 1;
  }
  v144 = v47;
  v48 = v157;
  while ( *((int *)QuadPart + 49) < 21 )
  {
    ExcHandler::ExcHandler((ExcHandler *)v312, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_backout, 0);
    v70 = v48 == 0;
    v71 = v160;
    if ( v70 )
    {
      v113 = *((_QWORD *)v160 + 2);
      if ( !v113 )
      {
        v114 = *((_QWORD *)v160 + 1);
        if ( v114 && (v115 = *(_QWORD *)(v114 + 96)) != 0 )
          v113 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v115 + 16LL))(v115);
        else
          v113 = 0;
      }
      v293 = v113;
      if ( v113 && !(unsigned int)CNetByteStream::FDrain(*(CNetByteStream **)(v113 + 160)) )
        CDeferMsgsAndEnvChangesConn::ClearDeferred((CDeferMsgsAndEnvChangesConn *)&v194);
      CDeferMsgsAndEnvChangesConn::FlushDeferred((CDeferMsgsAndEnvChangesConn *)&v194);
      v157 = 1;
    }
    v72 = *((_DWORD *)QuadPart + 49);
    switch ( v72 )
    {
      case 0:
      case 1:
      case 16:
      case 17:
        if ( v72 == 17 )
        {
          v144 = 1;
        }
        else if ( v72 < 1 )
        {
          goto LABEL_132;
        }
        CSession::NotifyBatchFinish((CSession *)v23.QuadPart);
LABEL_132:
        v77 = (_QWORD *)*((_QWORD *)v71 + 3);
        v298 = v77;
        v77[4] = 0;
        (*(void (__fastcall **)(_QWORD *, __int64))(*v77 + 432LL))(v77, 1);
LABEL_122:
        ExcHandler::~ExcHandler((ExcHandler *)v312);
        v74 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v75 = *(struct Worker **)(v74 + 256);
        if ( !v75 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v75 = *(struct Worker **)(v74 + 256);
        }
        if ( *((_DWORD *)v75 + 139) )
          ExceptionPostCatchActions(v75);
        v48 = v157;
        if ( v157 )
        {
          v76 = *((_DWORD *)&x_rgTopLevelErrorHandlingStates + *((int *)QuadPart + 49));
          if ( v76 == 19 && byte_102EDCB76 && !byte_102EDCB75 )
            utassert_fail(
              1u,
              "CFeatureSwitchesLangSvc::GetCurrentInstance()->FConnectionResiliencyForPlannedFailoversEnabled()",
              "batch.cpp",
              52,
              0);
          *((_DWORD *)QuadPart + 49) = v76;
        }
        break;
      case 2:
      case 3:
      case 4:
      case 15:
        CAutoSetupCXCtxtS::Teardown((CAutoSetupCXCtxtS *)&v244);
        goto LABEL_122;
      case 5:
      case 6:
      case 10:
      case 12:
        (*(void (__fastcall **)(CBatchExecEnv *))(*(_QWORD *)BatchExecEnv + 40LL))(BatchExecEnv);
        v67 = v151;
        if ( v144 )
          v67 = 1;
        v151 = v67;
        v294 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v295 = (__int64 *)(v294[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v296 = *v295;
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v190 + 760LL))(v190, *(_QWORD *)(v296 + 128), v67);
        goto LABEL_122;
      case 7:
      case 8:
      case 9:
        v73 = v154;
        *((_DWORD *)v154 + 6) &= ~8u;
        *((_DWORD *)v73 + 6) |= 4u;
        if ( (*((_DWORD *)v154 + 6) & 8) == 0 )
          (*(void (__fastcall **)(struct CExecLevel *))(*(_QWORD *)v154 + 160LL))(v154);
        goto LABEL_122;
      case 11:
        CBatchExecEnv::OnExecError(BatchExecEnv, &v154, v169, 1);
        goto LABEL_122;
      case 13:
        v68 = (_DWORD *)*((_QWORD *)v71 + 3);
        v297 = v68;
        if ( v68[11] )
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v68 + 376LL))(v68);
        CConnectionOutput::UnstructuredEndResultSet(*((CConnectionOutput **)v71 + 3), 1, 0, 0, 1);
        goto LABEL_122;
      case 14:
        v69 = BatchExecEnv;
        if ( BatchExecEnv )
        {
          CBatchExecEnv::BatchCleanup(BatchExecEnv);
          (**(void (__fastcall ***)(CBatchExecEnv *, _QWORD))v69)(v69, 0);
        }
        goto LABEL_122;
      case 18:
      case 19:
      case 20:
      case 21:
        goto LABEL_122;
      default:
        *((_DWORD *)QuadPart + 49) = 21;
        goto LABEL_122;
    }
  }
  v49 = v146 != 0;
  if ( v147 )
    v49 |= 0x10u;
  if ( v166 )
  {
    LODWORD(v160) = 0;
    v116 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v117 = *(_QWORD *)(v116 + 256);
    if ( !v117 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v117 = *(_QWORD *)(v116 + 256);
    }
    v161 = v117;
    v118 = *(_DWORD *)(v117 + 616);
    v119 = !(*(_BYTE *)(v117 + 616) & 1);
    LODWORD(v160) = v119;
    *(_DWORD *)(v117 + 616) = v118 | 1;
    ex_callprint(17310, 20, 1, (unsigned int)*(__int16 *)(v23.QuadPart + 16));
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v261 = 0;
    ReportProcessCloseConnectionEvent(QuadPart, 1, 0, v49, 13, &si128);
    *(_DWORD *)(v117 + 616) &= ~v119;
  }
  if ( (*(_BYTE *)(qword_102ECFB00 + 48) & 0x20) != 0 )
    SOS_WaitableAddress::SignalCookie((const void *const)(qword_102ECFB00 + 48));
  if ( v144 )
  {
    v209[0] = v152;
    v120 = v158;
    if ( !v152 )
      v120 = 20;
    v209[1] = v120;
    v209[2] = -1;
    v121 = v153;
    if ( !v152 )
      v121 = 9;
    v209[3] = v121;
    v209[4] = 0;
    if ( v152 )
      v122 = (*(__int64 (__fastcall **)(LONGLONG))(*(_QWORD *)(v23.QuadPart + 80) + 56LL))(v23.QuadPart + 80);
    else
      v122 = 29;
    ReportProcessCloseConnectionEvent(QuadPart, 1, 0, v49, v122, v209);
    v194 = &CDeferMsgsAndEnvChangesConn::`vftable';
    CDeferMsgsAndEnvChangesConn::ClearDeferred((CDeferMsgsAndEnvChangesConn *)&v194);
    v194 = &CConnectionOutput::`vftable';
    AccountForQueryThreadUsage(0);
    v123 = v170;
    if ( HIDWORD(v171) )
    {
      SOS_ResourceGroup::AccountForWorkerCompletion(v170, 1u);
      HIDWORD(v171) = 0;
    }
    if ( !(_DWORD)v171 )
      goto LABEL_270;
    SOS_ResourceGroup::AccountForRequestCompletion(v123);
    v124 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v125 = *(_QWORD *)(v124 + 256);
    if ( !v125 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v125 = *(_QWORD *)(v124 + 256);
    }
    v126 = *(_QWORD **)(v125 + 600);
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v167);
      v127 = (CSbTransportMgr *)v167.QuadPart;
    }
    else
    {
      v127 = MEMORY[0x7FFE0008];
    }
    v128 = v126[19];
    v129 = *(_QWORD *)(v128 + 3096);
    v130 = v126[47];
    v131 = *(_QWORD *)(v128 + 816);
    v132 = (char *)v127 - v131;
    if ( (unsigned __int64)v127 < v131 )
      v132 = 0;
    v133 = v129 - v130;
    if ( v129 < v130 )
      v133 = 0;
    v134 = &v132[v133];
    if ( (unsigned __int64)v134 < v172 )
    {
      v135 = 0;
    }
    else
    {
      v135 = &v134[-v172];
      if ( v135 == (char *)-1LL )
      {
        v136 = -1;
        v137 = *(_DWORD **)&Base_PublicGlobals::sm_invariantTscAvailable;
LABEL_264:
        v138 = v126[121];
        if ( v138 != -1 )
        {
          if ( *v137 )
            v40 = 1000 * v138 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
          else
            v40 = v138 / 0x2710;
        }
        if ( *((_QWORD *)v170 + 164) < (signed __int64)(v40 + v136)
          && v170 != (SOS_ResourceGroup *)((char *)&SOS_PublicGlobals::sm_ResourceManager + 3576) )
        {
          v175 = v40 + v136;
          *((_QWORD *)v170 + 164) = v40 + v136;
        }
LABEL_270:
        CAutoSetupCXCtxtS::Teardown((CAutoSetupCXCtxtS *)&v244);
        return 2;
      }
    }
    v137 = *(_DWORD **)&Base_PublicGlobals::sm_invariantTscAvailable;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
      v136 = (unsigned __int64)(1000LL * (_QWORD)v135) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
    else
      v136 = (unsigned __int64)v135 / 0x2710;
    goto LABEL_264;
  }
  v194 = &CDeferMsgsAndEnvChangesConn::`vftable';
  CDeferMsgsAndEnvChangesConn::ClearDeferred((CDeferMsgsAndEnvChangesConn *)&v194);
  v194 = &CConnectionOutput::`vftable';
  AccountForQueryThreadUsage(0);
  v50 = v170;
  if ( HIDWORD(v171) )
  {
    SOS_ResourceGroup::AccountForWorkerCompletion(v170, 1u);
    HIDWORD(v171) = 0;
  }
  if ( (_DWORD)v171 )
  {
    SOS_ResourceGroup::AccountForRequestCompletion(v50);
    v51 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v52 = *(_QWORD *)(v51 + 256);
    if ( !v52 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v52 = *(_QWORD *)(v51 + 256);
    }
    v53 = *(_QWORD **)(v52 + 600);
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&PerformanceCount);
      v54 = (CSbTransportMgr *)PerformanceCount.QuadPart;
    }
    else
    {
      v54 = MEMORY[0x7FFE0008];
    }
    v55 = v53[19];
    v56 = *(_QWORD *)(v55 + 3096);
    v57 = v53[47];
    v58 = *(_QWORD *)(v55 + 816);
    v59 = v56 - v57;
    if ( v56 < v57 )
      v59 = 0;
    v60 = (char *)v54 - v58;
    if ( (unsigned __int64)v54 < v58 )
      v60 = 0;
    v61 = &v60[v59];
    if ( (unsigned __int64)v61 < v172 )
    {
      v62 = 0;
      goto LABEL_102;
    }
    v62 = &v61[-v172];
    if ( v62 == (char *)-1LL )
    {
      v64 = -1;
      v63 = *(_DWORD **)&Base_PublicGlobals::sm_invariantTscAvailable;
    }
    else
    {
LABEL_102:
      v63 = *(_DWORD **)&Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
        v64 = (unsigned __int64)(1000LL * (_QWORD)v62) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
      else
        v64 = (unsigned __int64)v62 / 0x2710;
    }
    v65 = v53[121];
    if ( v65 != -1 )
    {
      if ( *v63 )
        v40 = 1000 * v65 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
      else
        v40 = v65 / 0x2710;
    }
    if ( *((_QWORD *)v170 + 164) < (signed __int64)(v40 + v64)
      && v170 != (SOS_ResourceGroup *)((char *)&SOS_PublicGlobals::sm_ResourceManager + 3576) )
    {
      v175 = v40 + v64;
      *((_QWORD *)v170 + 164) = v40 + v64;
    }
  }
  CAutoSetupCXCtxtS::Teardown((CAutoSetupCXCtxtS *)&v244);
  return 0;
}

```

## disassembly

```asm
0x100416ce0  mov     r11, rsp
0x100416ce3  push    rbx
0x100416ce4  push    rsi
0x100416ce5  push    rdi
0x100416ce6  push    r12
0x100416ce8  push    r13
0x100416cea  push    r14
0x100416cec  push    r15
0x100416cee  sub     rsp, 740h
0x100416cf5  mov     qword ptr [r11-318h], 0FFFFFFFFFFFFFFFEh
0x100416d00  movaps  xmmword ptr [r11-48h], xmm6
0x100416d05  mov     rax, cs:__security_cookie
0x100416d0c  xor     rax, rsp
0x100416d0f  mov     [rsp+778h+var_58], rax
0x100416d17  mov     r13d, r8d
0x100416d1a  mov     r12, rdx
0x100416d1d  mov     rdi, rcx
0x100416d20  mov     qword ptr [rsp+778h+var_6D8], rcx
0x100416d28  mov     [rsp+778h+var_640], rcx
0x100416d30  xor     esi, esi
0x100416d32  mov     [rsp+778h+var_700], rsi
0x100416d37  mov     rbx, [rcx+18h]
0x100416d3b  mov     qword ptr [rsp+778h+PerformanceCount], rbx
0x100416d40  mov     r14, [rcx+20h]
0x100416d44  mov     [rsp+778h+var_6F8], r14
0x100416d4c  mov     [r11-448h], rbx
0x100416d53  xorps   xmm0, xmm0
0x100416d56  movdqu  [rsp+778h+var_440], xmm0
0x100416d5f  xorps   xmm1, xmm1
0x100416d62  movdqu  [rsp+778h+var_430], xmm1
0x100416d6b  mov     [r11-420h], rsi
0x100416d72  mov     [rsp+778h+var_418], esi
0x100416d79  mov     [rsp+778h+var_738], sil
0x100416d7e  mov     [rsp+778h+var_70C], esi
0x100416d82  mov     [rsp+778h+var_724], esi
0x100416d86  mov     [rsp+778h+var_720], esi
0x100416d8a  mov     [rsp+778h+var_704], esi
0x100416d8e  mov     [rsp+778h+var_6E0], esi
0x100416d95  mov     [rsp+778h+var_718], rsi
0x100416d9a  mov     [r11-6C8h], rsi
0x100416da1  mov     [rsp+778h+var_728], 2
0x100416da9  mov     [rcx+0C4h], esi
0x100416daf  mov     [rsp+778h+var_734], sil
0x100416db4  mov     [rsp+778h+var_708], esi
0x100416db8  mov     [r11-620h], rsi
0x100416dbf  mov     [r11-6B8h], rsi
0x100416dc6  mov     cl, 1
0x100416dc8  call    cs:__imp_?AccountForQueryThreadUsage@@YAX_N@Z; AccountForQueryThreadUsage(bool)
0x100416dce  nop
0x100416dcf  mov     [rsp+778h+var_6A8], esi
0x100416dd6  mov     rax, [r14+18h]
0x100416dda  lea     rcx, ??_7CConnectionOutput@@6B@; const CConnectionOutput::`vftable'
0x100416de1  mov     [rsp+778h+var_5E8], rcx
0x100416de9  mov     [rsp+778h+var_5E0], rsi
0x100416df1  mov     [rsp+778h+var_5D8], esi
0x100416df8  mov     [rsp+778h+var_5D0], rsi
0x100416e00  mov     [rsp+778h+var_5C8], rsi
0x100416e08  mov     [rsp+778h+var_5C0], esi
0x100416e0f  mov     [rsp+778h+var_5BC], 1
0x100416e1a  mov     [rsp+778h+var_5B8], rsi
0x100416e22  mov     [rsp+778h+var_5B0], 1
0x100416e2a  lea     rcx, ??_7CPassThroughConn@@6B@; const CPassThroughConn::`vftable'
0x100416e31  mov     [rsp+778h+var_5E8], rcx
0x100416e39  mov     [rsp+778h+var_5A8], rax
0x100416e41  lea     rax, ??_7CDeferMsgsAndEnvChangesConn@@6B@; const CDeferMsgsAndEnvChangesConn::`vftable'
0x100416e48  mov     [rsp+778h+var_5E8], rax
0x100416e50  mov     [rsp+778h+var_5A0], rsi
0x100416e58  mov     [rsp+778h+var_598], rsi
0x100416e60  lea     rax, [rsp+778h+var_5A0]
0x100416e68  mov     [rsp+778h+var_598], rax
0x100416e70  lea     rax, [rsp+778h+var_5A0]
0x100416e78  mov     [rsp+778h+var_5A0], rax
0x100416e80  mov     [rsp+778h+var_590], esi
0x100416e87  lea     rax, [rsp+778h+var_5A0]
0x100416e8f  mov     [rsp+778h+var_598], rax
0x100416e97  lea     rax, [rsp+778h+var_5A0]
0x100416e9f  mov     [rsp+778h+var_5A0], rax
0x100416ea7  mov     [rsp+778h+var_588], rsi
0x100416eaf  mov     rax, [r14+18h]
0x100416eb3  mov     byte ptr [rax+38h], 1
0x100416eb7  mov     rax, [r14+18h]
0x100416ebb  lea     rcx, [rax+30h]
0x100416ebf  cmp     [rax+38h], sil
0x100416ec3  cmovz   rcx, rsi; this
0x100416ec7  call    ?Init@SOS_LsAccessCache@@QEAAXXZ; SOS_LsAccessCache::Init(void)
0x100416ecc  mov     rax, [rdi]
0x100416ecf  mov     rcx, rdi
0x100416ed2  call    qword ptr [rax+48h]
0x100416ed5  mov     r15, [rax+170h]
0x100416edc  xor     r14b, r14b
0x100416edf  mov     [rsp+778h+var_733], r14b
0x100416ee4  mov     [rsp+778h+var_737], r14b
0x100416ee9  cmp     cs:byte_102EDCB77, r14b
0x100416ef0  jnz     loc_100F06E2F
0x100416ef6  mov     [rsp+778h+var_736], r14b
0x100416efb  mov     [rsp+778h+var_735], r14b
0x100416f00  xor     edx, edx; unsigned __int16
0x100416f02  mov     [rsp+778h+var_750], rsi; struct Worker *
0x100416f07  lea     rax, ?MSQLErrorHandlerFunc@@YAHHHHHPEAD@Z; MSQLErrorHandlerFunc(int,int,int,int,char *)
0x100416f0e  mov     [rsp+778h+var_758], rax; int (*)(int, int, int, int, char *)
0x100416f13  xor     r9d, r9d; unsigned __int8
0x100416f16  xor     r8d, r8d; unsigned __int8
0x100416f19  lea     rcx, [rsp+778h+var_150]; this
0x100416f21  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x100416f26  nop
0x100416f27  xorps   xmm0, xmm0
0x100416f2a  movdqu  [rsp+778h+var_610], xmm0
0x100416f33  xorps   xmm1, xmm1
0x100416f36  movdqu  [rsp+778h+var_600], xmm1
0x100416f3f  mov     rdx, [rsp+778h+var_6F8]; struct CBatch *
0x100416f47  mov     rcx, [rdx+18h]
0x100416f4b  lea     rax, [rsp+778h+var_5E8]
0x100416f53  cmp     rcx, rax
0x100416f56  jz      short loc_100416F9C
0x100416f58  mov     qword ptr [rsp+778h+var_610], rdx
0x100416f60  mov     qword ptr [rsp+778h+var_610+8], rcx
0x100416f68  mov     rax, [rsp+778h+var_5E0]
0x100416f70  mov     qword ptr [rsp+778h+var_600], rax
0x100416f78  lea     rax, [rsp+778h+var_5E8]
0x100416f80  mov     qword ptr [rsp+778h+var_600+8], rax
0x100416f88  mov     [rsp+778h+var_5E0], rcx
0x100416f90  lea     rax, [rsp+778h+var_5E8]
0x100416f98  mov     [rdx+18h], rax
0x100416f9c  mov     dword ptr [rdi+0C4h], 1
0x100416fa6  test    byte ptr [r15+30h], 2
0x100416fab  jnz     loc_100F06E53
0x100416fb1  mov     ebx, [rbx+104h]
0x100416fb7  mov     r8d, esi
0x100416fba  test    ebx, ebx
0x100416fbc  setnz   r8b; int
0x100416fc0  mov     [rsp+778h+var_478], r8d
0x100416fc8  mov     [rsp+778h+var_638], ebx
0x100416fcf  mov     rcx, qword ptr [rsp+778h+PerformanceCount]; this
0x100416fd4  call    ?NotifyBatchStart@CSession@@QEAAXQEBVCBatch@@H@Z; CSession::NotifyBatchStart(CBatch const * const,int)
0x100416fd9  mov     rax, qword ptr [rsp+778h+PerformanceCount]
0x100416fde  mov     byte ptr [rax+1356h], 1
0x100416fe5  test    ebx, ebx
0x100416fe7  jnz     loc_100F06EB0
0x100416fed  cmp     byte ptr [rax+103h], 0
0x100416ff4  jnz     loc_100F06EDB
0x100416ffa  mov     r12, rax
0x100416ffd  mov     [rsp+778h+var_737], r14b
0x100417002  test    r14b, r14b
0x100417005  jnz     loc_100F06F0E
0x10041700b  mov     rax, cs:qword_102ECFB10
0x100417012  cmp     byte ptr [rax+4D7h], 0
0x100417019  jl      loc_100F06F2C
0x10041701f  mov     dword ptr [rdi+0C4h], 2
0x100417029  mov     rcx, rdi; this
0x10041702c  call    ?ResetPasswordMaskingHints@CBatch@@QEAAXXZ; CBatch::ResetPasswordMaskingHints(void)
0x100417031  movzx   eax, byte ptr [r12+110h]
0x10041703a  shr     al, 4
0x10041703d  and     al, 1
0x10041703f  mov     [rsp+778h+var_6E5], al
0x100417046  mov     byte ptr [rsp+778h+var_758], al; bool
0x10041704a  mov     r9b, 1; bool
0x10041704d  lea     r8, [rsp+778h+var_738]; bool *
0x100417052  mov     rdx, rdi; struct CBatch *
0x100417055  lea     rcx, [rsp+778h+var_448]; this
0x10041705d  call    ?FInit@CAutoSetupCXCtxtS@@QEAA_NPEAVCBatch@@PEA_N_N2@Z; CAutoSetupCXCtxtS::FInit(CBatch *,bool *,bool,bool)
0x100417062  test    al, al
0x100417064  jz      loc_100F07925
0x10041706a  mov     rdx, gs:58h
0x100417073  mov     [rsp+778h+var_1F0], rdx
0x10041707b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100417082  mov     ecx, [rax]
0x100417084  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041708b  mov     eax, [rax]
0x10041708d  add     rax, [rdx+rcx*8]
0x100417091  mov     [rsp+778h+var_1E8], rax
0x100417099  mov     rax, [rax]
0x10041709c  mov     [rsp+778h+var_4E0], rax
0x1004170a4  mov     [rsp+778h+var_668], rax
0x1004170ac  mov     rbx, [rax+80h]
0x1004170b3  mov     [rsp+778h+var_660], rbx
0x1004170bb  and     [rsp+778h+var_408], 0FFFFFFFEh
0x1004170c3  mov     [rsp+778h+var_404], si
0x1004170cb  mov     [rsp+778h+var_400], rsi
0x1004170d3  mov     [rsp+778h+var_3F8], si
0x1004170db  mov     [rsp+778h+var_3F0], rsi
0x1004170e3  mov     [rsp+778h+var_3E8], esi
0x1004170ea  mov     [rsp+778h+var_3E0], rsi
0x1004170f2  mov     [rsp+778h+var_3D8], rsi
0x1004170fa  mov     [rsp+778h+var_3D0], rsi
0x100417102  mov     [rsp+778h+var_3C8], esi
0x100417109  mov     [rsp+778h+var_6E4], esi
0x100417110  mov     rdx, rdi; struct CBatch *
0x100417113  mov     rcx, r12; struct CSession *
0x100417116  call    ?CheckTerminate@@YAXPEAVCSession@@PEAVCBatch@@@Z; CheckTerminate(CSession *,CBatch *)
0x10041711b  mov     r8d, r13d
0x10041711e  mov     rdx, rbx
0x100417121  mov     rcx, rdi
0x100417124  call    ?GetBatchExecEnv@CBatch@@QEAAPEAVCBatchExecEnv@@PEAVCExecLvlIntCtxt@@W4RequestType@@@Z; CBatch::GetBatchExecEnv(CExecLvlIntCtxt *,RequestType)
0x100417129  mov     [rsp+778h+var_700], rax
0x10041712e  mov     dword ptr [rdi+0C4h], 3
0x100417138  cmp     word ptr [r12+0B8h], 5
0x100417142  jb      short loc_1004171C1
0x100417144  cmp     [rsp+778h+var_638], 1
0x10041714c  jz      loc_100F06F82
0x100417152  mov     r14d, esi
0x100417155  mov     [rsp+778h+var_618], esi
0x10041715c  mov     r8d, r13d
0x10041715f  mov     rdx, rdi
0x100417162  lea     rcx, [rsp+778h+var_408]
0x10041716a  call    ?ReadTdsHeaders@CProtocolHeaderInfo@@QEAAXPEAVIBatch@@W4RequestType@@@Z; CProtocolHeaderInfo::ReadTdsHeaders(IBatch *,RequestType)
0x10041716f  mov     eax, [r15+3C4h]
0x100417176  shr     eax, 16h
0x100417179  and     al, 1
0x10041717b  jnz     loc_100F06FA1
0x100417181  test    r14d, r14d
0x100417184  jnz     loc_100F06FB2
0x10041718a  mov     rdx, [rsp+778h+var_3D0]
0x100417192  mov     [rsp+778h+var_4F0], rdx
0x10041719a  test    al, al
0x10041719c  jnz     loc_100F06FC9
0x1004171a2  mov     eax, [rsp+778h+var_3C8]
0x1004171a9  mov     [rsp+778h+var_460], eax
0x1004171b0  mov     [rbx+200h], rdx
0x1004171b7  mov     [rbx+208h], eax
0x1004171bd  or      dword ptr [rbx+4Ch], 2
0x1004171c1  mov     r13, qword ptr [rsp+778h+PerformanceCount]
0x1004171c6  test    byte ptr [r13+10Eh], 4
0x1004171ce  jnz     loc_100F06FF7
0x1004171d4  mov     eax, esi
0x1004171d6  mov     [rsp+778h+var_710], ax
0x1004171db  mov     r15d, esi
0x1004171de  test    ax, ax
0x1004171e1  setz    r15b
0x1004171e5  mov     rdx, gs:58h
0x1004171ee  mov     [rsp+778h+var_1D0], rdx
0x1004171f6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004171fd  mov     ecx, [rax]
0x1004171ff  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100417206  mov     ebx, [rax]
0x100417208  add     rbx, [rdx+rcx*8]
0x10041720c  mov     [rsp+778h+var_1C8], rbx
0x100417214  mov     r14, [rbx+100h]
0x10041721b  mov     [rsp+778h+var_4E8], r14
0x100417223  test    r14, r14
0x100417226  jz      loc_100F07005
0x10041722c  mov     r14, [r14+218h]
0x100417233  mov     [rsp+778h+var_6D0], r14
0x10041723b  mov     ebx, esi
0x10041723d  mov     [rsp+778h+var_690], ebx
0x100417244  mov     rax, cs:__imp_?sm_isResourceManagerEnabled@SOS_PublicGlobals@@2HA; int SOS_PublicGlobals::sm_isResourceManagerEnabled
0x10041724b  mov     ecx, [rax]
0x10041724d  mov     [rsp+778h+var_458], ecx
0x100417254  mov     r12d, 1
0x10041725a  test    ecx, ecx
0x10041725c  jz      short loc_10041728E
0x10041725e  mov     [rsp+778h+var_6C0], r14
0x100417266  mov     r8d, r12d
0x100417269  mov     edx, r15d
0x10041726c  mov     rcx, r14
0x10041726f  call    cs:__imp_?AccountForNewWorkerRequest@SOS_ResourceGroup@@QEAA?AW4SOS_RESULT@@HG@Z; SOS_ResourceGroup::AccountForNewWorkerRequest(int,ushort)
0x100417275  mov     ebx, eax
0x100417277  mov     [rsp+778h+var_690], eax
0x10041727e  test    eax, eax
0x100417280  jnz     loc_100F0711A
0x100417286  mov     [rsp+778h+var_6B4], r12d
0x10041728e  mov     ecx, 80000000h
0x100417293  cmp     ebx, ecx
0x100417295  jz      loc_100F07022
0x10041729b  cmp     ebx, 82000000h
0x1004172a1  jz      loc_100F07153
0x1004172a7  cmp     [rsp+778h+var_710], 0
0x1004172ad  jnz     short loc_1004172E3
0x1004172af  mov     eax, [r14+0D34h]
0x1004172b6  mov     [rsp+778h+var_630], eax
0x1004172bd  mov     rax, [rsp+778h+var_6D0]
0x1004172c5  movsx   eax, word ptr [rax+0D2Ch]
0x1004172cc  inc     eax
0x1004172ce  cmp     [rsp+778h+var_630], eax
0x1004172d5  jz      loc_100F071A9
0x1004172db  mov     r14, [rsp+778h+var_6D0]
0x1004172e3  mov     rax, cs:qword_102ECFB00
0x1004172ea  cmp     dword ptr [rax+38A8h], 0
0x1004172f1  jnz     loc_100F071D2
0x1004172f7  call    cs:__imp_?IsSptEnforcementOn@@YA_NXZ; IsSptEnforcementOn(void)
0x1004172fd  test    al, al
0x1004172ff  jnz     loc_100F07313
0x100417305  mov     dword ptr [rdi+0C4h], 4
0x10041730f  mov     r15, [rdi+78h]
0x100417313  mov     [rsp+778h+var_620], r15
0x10041731b  mov     rax, [r15]
0x10041731e  mov     r8, [rsp+778h+var_660]
0x100417326  mov     rdx, [r13+288h]
0x10041732d  mov     rcx, r15
0x100417330  call    qword ptr [rax+2F0h]
0x100417336  mov     dword ptr [rdi+0C4h], 5
0x100417340  cmp     [rsp+778h+var_6A8], 0
0x100417348  jnz     short loc_100417364
0x10041734a  mov     r9, r13; void *
0x10041734d  lea     r8, ?FCanBeThrottledStatic@CSession@@SAHPEAX@Z; int (*)(void *)
0x100417354  mov     rdx, r14; struct SOS_ResourceGroup *
0x100417357  lea     rcx, [rsp+778h+var_6C0]; this
0x10041735f  call    ?AccountGroupUsage@CAutoAccountGroupUsage@@QEAAXPEAVSOS_ResourceGroup@@P6AHPEAX@Z1@Z; CAutoAccountGroupUsage::AccountGroupUsage(SOS_ResourceGroup *,int (*)(void *),void *)
0x100417364  mov     dword ptr [rdi+0C4h], 6
0x10041736e  mov     rbx, [rsp+778h+var_700]
0x100417373  mov     rax, [rbx]
  ... truncated ...
```
