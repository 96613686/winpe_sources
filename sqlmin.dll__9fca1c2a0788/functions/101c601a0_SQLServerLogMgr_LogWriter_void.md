# SQLServerLogMgr::LogWriter(void *)

- ea: `0x101c601a0`
- end: `0x101c618df`
- name: `?LogWriter@SQLServerLogMgr@@SAPEAXPEAX@Z`
- size: `5951`
- prototype: `static void __noreturn(void *)`
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x100401010`
- `0x100401380`
- `0x1004013f0`
- `0x100401490`
- `0x100401fcf`
- `0x100402000`
- `0x100433070`
- `0x100437e20`
- `0x100437f20`
- `0x100438b60`
- `0x1005740b0`
- `0x1005d3620`
- `0x10068c700`
- `0x10068d480`
- `0x10068d630`
- `0x1017a9710`
- `0x101bd60c0`
- `0x101c30ea0`
- `0x101c31090`
- `0x101c312d0`
- `0x101c51530`
- `0x101c51e10`
- `0x101c52810`
- `0x101c601a0`
- `0x101c67d70`
- `0x1023aea90`
- `0x1023aecb0`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x101c60585`
- `KERNEL32!GetCurrentThread` at `0x101c605a4`
- `KERNEL32!GetCurrentThread` at `0x101c60585`
- `KERNEL32!GetCurrentThread` at `0x101c605a4`
- `KERNEL32!SetThreadPriorityBoost` at `0x101c605af`
- `KERNEL32!SetThreadPriorityBoost` at `0x101c605af`
- `KERNEL32!GetThreadPriorityBoost` at `0x101c60593`
- `KERNEL32!GetThreadPriorityBoost` at `0x101c60593`
- `KERNEL32!GetProcessPriorityBoost` at `0x101c60574`
- `KERNEL32!GetProcessPriorityBoost` at `0x101c60574`
- `KERNEL32!QueryPerformanceCounter` at `0x100401802`
- `KERNEL32!QueryPerformanceCounter` at `0x101c60424`
- `KERNEL32!QueryPerformanceCounter` at `0x101c6049b`
- `KERNEL32!QueryPerformanceCounter` at `0x101c6098d`
- `KERNEL32!QueryPerformanceCounter` at `0x101c60fd0`
- `KERNEL32!QueryPerformanceCounter` at `0x100401802`
- `KERNEL32!QueryPerformanceCounter` at `0x101c60424`
- `KERNEL32!QueryPerformanceCounter` at `0x101c6049b`
- `KERNEL32!QueryPerformanceCounter` at `0x101c6098d`
- `KERNEL32!QueryPerformanceCounter` at `0x101c60fd0`
- `KERNEL32!GetCurrentThreadId` at `0x1004014ce`
- `KERNEL32!GetCurrentThreadId` at `0x101c6095b`
- `KERNEL32!GetCurrentThreadId` at `0x1004014ce`
- `KERNEL32!GetCurrentThreadId` at `0x101c6095b`
- `KERNEL32!GetCurrentProcess` at `0x101c60566`
- `KERNEL32!GetCurrentProcess` at `0x101c60566`
- `sqldk!?TransferMemory@SOS_MemoryPool@@QEAAX_JW4MemoryBrokerType@@1@Z` at `0x101c60798`
- `sqldk!?TransferMemory@SOS_MemoryPool@@QEAAX_JW4MemoryBrokerType@@1@Z` at `0x101c6087f`
- `sqldk!?TransferMemory@SOS_MemoryPool@@QEAAX_JW4MemoryBrokerType@@1@Z` at `0x101c613b7`
- `sqldk!?TransferMemory@SOS_MemoryPool@@QEAAX_JW4MemoryBrokerType@@1@Z` at `0x101c60798`
- `sqldk!?TransferMemory@SOS_MemoryPool@@QEAAX_JW4MemoryBrokerType@@1@Z` at `0x101c6087f`
- `sqldk!?TransferMemory@SOS_MemoryPool@@QEAAX_JW4MemoryBrokerType@@1@Z` at `0x101c613b7`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100401643`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101c60374`
- `sqldk!?sm_NodeManager@SOS_PublicGlobals@@2VNodeManager@@A` at `0x1004015b2`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101c60448`
- `sqldk!?SOS_OS_NumberOfMemoryNodeInfos@@3KA` at `0x1004015bf`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004017e2`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100401856`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101c60404`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101c6047b`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101c6096d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101c60fb0`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101c610da`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x10040186e`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101c610ee`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101c60eba`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x100401774`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x1004017b9`
- `sqldk!?Dequeue@ResQueueBase@@QEAAPEAVSEListElem@@IK_N@Z` at `0x10040170b`
- `sqldk!?Dequeue@ResQueueBase@@QEAAPEAVSEListElem@@IK_N@Z` at `0x10040170b`
- `sqldk!?GetPool@MemoryPoolManager@@SAPEAVSOS_MemoryPool@@K@Z` at `0x101c60786`
- `sqldk!?GetPool@MemoryPoolManager@@SAPEAVSOS_MemoryPool@@K@Z` at `0x101c6086d`
- `sqldk!?GetPool@MemoryPoolManager@@SAPEAVSOS_MemoryPool@@K@Z` at `0x101c613a4`
- `sqldk!?GetPool@MemoryPoolManager@@SAPEAVSOS_MemoryPool@@K@Z` at `0x101c60786`
- `sqldk!?GetPool@MemoryPoolManager@@SAPEAVSOS_MemoryPool@@K@Z` at `0x101c6086d`
- `sqldk!?GetPool@MemoryPoolManager@@SAPEAVSOS_MemoryPool@@K@Z` at `0x101c613a4`
- `sqldk!??0SOS_LogGovernorStats@@QEAA@XZ` at `0x101c60a0f`
- `sqldk!??0SOS_LogGovernorStats@@QEAA@XZ` at `0x101c60a0f`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101c61822`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101c618a5`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101c61822`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101c618a5`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101c6172a`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101c6172a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1004014c8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101c61784`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1004014c8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101c61784`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c6054a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c6054a`
- `sqldk!SystemThread_TlsIndex` at `0x1004014ec`
- `sqldk!SystemThread_TlsIndex` at `0x100401555`
- `sqldk!SystemThread_TlsIndex` at `0x100401600`
- `sqldk!SystemThread_TlsIndex` at `0x10040169a`
- `sqldk!SystemThread_TlsIndex` at `0x10040199c`
- `sqldk!SystemThread_TlsIndex` at `0x10040282e`
- `sqldk!SystemThread_TlsIndex` at `0x1004028c0`
- `sqldk!SystemThread_TlsIndex` at `0x1004386ff`
- `sqldk!SystemThread_TlsIndex` at `0x101c602be`
- `sqldk!SystemThread_TlsIndex` at `0x101c603a7`
- `sqldk!SystemThread_TlsIndex` at `0x101c606ee`
- `sqldk!SystemThread_TlsIndex` at `0x101c607cb`
- `sqldk!SystemThread_TlsIndex` at `0x101c617ea`
- `sqldk!SystemThread_TlsIndex` at `0x101c6186d`
- `sqldk!SystemThread_TlsOffset` at `0x1004014f5`
- `sqldk!SystemThread_TlsOffset` at `0x10040155e`
- `sqldk!SystemThread_TlsOffset` at `0x100401609`
- `sqldk!SystemThread_TlsOffset` at `0x1004016a3`
- `sqldk!SystemThread_TlsOffset` at `0x1004019a5`
- `sqldk!SystemThread_TlsOffset` at `0x100402837`
- `sqldk!SystemThread_TlsOffset` at `0x1004028c9`
- `sqldk!SystemThread_TlsOffset` at `0x100438708`
- `sqldk!SystemThread_TlsOffset` at `0x101c602c7`
- `sqldk!SystemThread_TlsOffset` at `0x101c603b0`
- `sqldk!SystemThread_TlsOffset` at `0x101c606f7`
- `sqldk!SystemThread_TlsOffset` at `0x101c607d4`
- `sqldk!SystemThread_TlsOffset` at `0x101c617f3`
- `sqldk!SystemThread_TlsOffset` at `0x101c61876`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100401520`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100401589`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c60669`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c60722`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c607ff`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c6083d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c6089e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c61374`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c617ab`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c6180c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c6188f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100401520`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100401589`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c60669`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c60722`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c607ff`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c6083d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c6089e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c61374`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c617ab`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c6180c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c6188f`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c6068c`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c60828`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c608c1`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c617ce`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c6068c`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c60828`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c608c1`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c617ce`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100401655`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100401655`

## string_xrefs

- `0x101c61744`: `Write error during log flush.\n`
- `0x101c61733`: `SQLServerLogMgr::LogWriter`
- `0x101c60250`: `Logwriter Task`
- `0x1004014bf`: `index < sm_totalLogWriters`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall __noreturn SQLServerLogMgr::LogWriter(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22,
        __int64 a23,
        __int64 a24,
        __int64 a25,
        __int64 a26,
        __int64 a27,
        __int64 a28,
        __int64 a29,
        __int64 a30,
        __int64 a31,
        __int64 a32,
        __int64 a33,
        __int64 a34,
        __int64 a35,
        __int64 a36,
        __int64 a37,
        __int64 a38,
        __int64 a39,
        __int64 a40,
        __int64 a41,
        __int64 a42,
        __int64 a43,
        __int64 a44,
        __int64 a45,
        __int64 a46,
        __int64 a47,
        __int64 a48,
        __int64 a49,
        __int64 a50,
        __int64 a51,
        __int64 a52,
        __int64 a53,
        __int64 a54,
        __int64 a55,
        __int64 a56,
        __int64 a57,
        __int64 a58,
        __int64 a59,
        __int64 a60,
        __int64 a61,
        __int64 a62)
{
  __int64 v62; // rdi
  __int64 v63; // rax
  __int64 v64; // rbx
  __int64 v65; // rax
  __int64 v66; // rcx
  int v67; // r8d
  __int64 v68; // rdi
  __int64 v69; // rbx
  void *v70; // rcx
  unsigned int v71; // ebx
  struct SEListElem *v72; // rax
  _DWORD *v73; // r13
  _BYTE *v74; // rax
  unsigned __int64 v75; // rdx
  __int64 v76; // rdx
  int v77; // eax
  __int64 v78; // rbx
  __int64 v79; // r14
  __int64 v80; // r14
  unsigned int v81; // esi
  __int64 *v82; // r15
  __int64 v83; // rdi
  int v84; // ecx
  __int64 v85; // rbx
  __int64 v86; // r14
  __int64 v87; // r14
  unsigned int v88; // esi
  __int64 *v89; // r15
  __int64 v90; // rdi
  __int64 v91; // rdi
  __int64 v92; // rbx
  void *v93; // rcx
  __int64 v94; // rdi
  __int64 v95; // rbx
  void *v96; // rcx
  SQLServerLogMgr *v97; // rcx
  __int64 v98; // rax
  int v99; // eax
  BOOL v100; // ecx
  bool v101; // zf
  __int64 v102; // rbx
  __int64 v104; // rbx
  DirtyPageMgr *QuadPart; // rax
  DirtyPageMgr *v106; // rax
  __int64 v107; // rax
  unsigned int v108; // eax
  __int64 v109; // rbx
  struct CSessionTraceFlags *v110; // rcx
  HANDLE CurrentProcess; // rax
  HANDLE CurrentThread; // rax
  HANDLE v113; // rax
  __int64 v114; // rbx
  __int64 v115; // r14
  __int64 v116; // r14
  unsigned int v117; // esi
  __int64 *v118; // r15
  __int64 v119; // rdi
  struct SOS_MemoryPool *Pool; // rax
  __int64 v121; // rdi
  __int64 v122; // rbx
  void *v123; // rcx
  struct SOS_MemoryPool *v124; // rax
  DirtyPageMgr *v125; // rcx
  struct SEListElem *v126; // r15
  __int64 v127; // r12
  struct SEListElem *v128; // rsi
  unsigned __int16 v129; // bx
  unsigned __int64 v130; // rcx
  unsigned __int64 v131; // rdx
  DirtyPageMgr *v132; // rcx
  unsigned __int64 v133; // rax
  unsigned __int64 v134; // rcx
  unsigned __int64 v135; // rbx
  __int64 v136; // rbx
  __int64 v137; // rsi
  __int64 v138; // rax
  __int64 v139; // rax
  __int64 v140; // rdi
  SQLServerLogMgr **v141; // r14
  char v142; // cl
  char v143; // cl
  unsigned int v144; // r10d
  __int64 v145; // rdi
  struct SOS_MemoryPool *v146; // rax
  __int64 v147; // rax
  unsigned int v148; // ebx
  wchar_t *OSErrString; // rax
  __int64 v151; // rbx
  struct Worker *v152; // rcx
  __int64 v155; // rbx
  struct Worker *v156; // rcx
  _BYTE *v157; // rbp
  signed __int64 v158; // rax
  BOOL v159; // ecx
  char v160; // cl
  _QWORD *v161; // rdx
  __int64 v162; // rbx
  __int64 v164; // rbx
  DirtyPageMgr *v165; // rax
  __int64 *v166; // rcx
  DirtyPageMgr *v167; // rax
  unsigned __int64 v168; // rcx
  char *v169; // rax
  DWORD CurrentThreadId; // eax
  __int64 v171; // rcx
  unsigned int v172; // r8d
  GUID *v173; // r9
  int v174; // r8d
  int v175; // ecx
  _QWORD *v176; // r8
  __int64 v177; // rdx
  __int64 v178; // rax
  __crt_locale_pointers *DefaultLocale; // rax
  __int64 v180; // rax
  _QWORD *v181; // rdx
  __int64 v182; // rbx
  __int64 v183; // rax
  __int64 v184; // rcx
  unsigned int v185; // ebx
  __int64 v186; // rax
  signed __int32 v187; // ecx
  __int64 v188; // rax
  _DWORD *v189; // rax
  __int64 v190; // rcx
  _DWORD *v191; // rax
  signed __int64 v192; // rax
  BOOL v193; // ecx
  char v194; // cl
  _QWORD *v195; // rdx
  __int64 v196; // rbx
  __int64 v198; // rbx
  DirtyPageMgr *v199; // rax
  __int64 v200; // rcx
  DirtyPageMgr *v201; // rax
  unsigned __int64 v202; // rcx
  char *v203; // rax
  __int64 *v204; // rdx
  _QWORD *v205; // rcx
  __int64 v206; // rax
  _QWORD *v207; // r8
  __int64 v208; // rdx
  __int64 v210; // rax
  __int64 v211; // rbx
  ISOSHost_TaskImpl *v212; // rcx
  SOS_Node *v213; // rcx
  __int64 v214; // rdi
  ISOSHost_TaskImpl *v215; // rbx
  __int64 v216; // rax
  _QWORD *v217; // rsi
  _DWORD *v218; // rax
  signed __int64 v219; // rax
  BOOL v220; // ecx
  char v221; // cl
  _QWORD *v222; // rdx
  __int64 v223; // rbx
  __int64 v225; // rbx
  DirtyPageMgr *v226; // rax
  __int64 v227; // rcx
  DirtyPageMgr *v228; // rax
  unsigned __int64 v229; // rcx
  char *v230; // rax
  __int64 v231; // rbx
  __int64 v232; // rax
  _QWORD *v233; // rcx
  _QWORD *v234; // rdi
  _QWORD *v235; // rcx
  unsigned __int64 v236; // rax
  SOS_ObjectStore *v237; // rcx
  unsigned int PoolIdForObject; // eax
  char v239; // r9
  _QWORD *v240; // rdx
  _QWORD *v241; // r8
  __int64 v242; // r10
  _QWORD *v243; // rcx
  __int64 v244; // rdx
  __int64 v245; // rcx
  int v246; // r8d
  int v247; // r8d
  void *v248; // rcx
  _BYTE *v249; // rbp
  struct Worker *v250; // [rsp+28h] [rbp-2F20h]
  _BYTE v251[32]; // [rsp+0h] [rbp-2F48h] BYREF
  __int64 v252; // [rsp+50h] [rbp-2EF8h] BYREF
  __int64 v253; // [rsp+58h] [rbp-2EF0h]
  SQLServerLogMgr **v254; // [rsp+60h] [rbp-2EE8h]
  __int64 v255; // [rsp+68h] [rbp-2EE0h]
  struct SEListElem *v256; // [rsp+70h] [rbp-2ED8h]
  char v257; // [rsp+78h] [rbp-2ED0h]
  char v258; // [rsp+79h] [rbp-2ECFh]
  bool v259; // [rsp+7Ah] [rbp-2ECEh]
  unsigned __int16 v261; // [rsp+80h] [rbp-2EC8h]
  unsigned int i; // [rsp+84h] [rbp-2EC4h]
  unsigned int v263; // [rsp+88h] [rbp-2EC0h]
  int v264; // [rsp+8Ch] [rbp-2EBCh]
  __int64 v265; // [rsp+90h] [rbp-2EB8h]
  int v266; // [rsp+98h] [rbp-2EB0h]
  unsigned int v267; // [rsp+9Ch] [rbp-2EACh]
  unsigned int v268; // [rsp+A0h] [rbp-2EA8h]
  __int64 v269; // [rsp+A8h] [rbp-2EA0h]
  struct SEListElem *v270; // [rsp+B0h] [rbp-2E98h]
  int v271; // [rsp+C8h] [rbp-2E80h]
  __int64 v272; // [rsp+E8h] [rbp-2E60h]
  unsigned int v273; // [rsp+100h] [rbp-2E48h]
  unsigned int v274; // [rsp+128h] [rbp-2E20h]
  int v275; // [rsp+138h] [rbp-2E10h]
  unsigned int v276; // [rsp+13Ch] [rbp-2E0Ch]
  __int64 v277; // [rsp+140h] [rbp-2E08h]
  unsigned int v278; // [rsp+150h] [rbp-2DF8h]
  int v279; // [rsp+168h] [rbp-2DE0h] BYREF
  signed __int64 UniqueThread_low; // [rsp+170h] [rbp-2DD8h]
  int v281; // [rsp+198h] [rbp-2DB0h]
  int v282; // [rsp+19Ch] [rbp-2DACh]
  int v283; // [rsp+1A0h] [rbp-2DA8h]
  int v284; // [rsp+1A4h] [rbp-2DA4h]
  int v285; // [rsp+1A8h] [rbp-2DA0h]
  int v286; // [rsp+1ACh] [rbp-2D9Ch]
  unsigned __int64 v287; // [rsp+1B8h] [rbp-2D90h]
  __int64 v288; // [rsp+1C0h] [rbp-2D88h]
  DirtyPageMgr *v289; // [rsp+1C8h] [rbp-2D80h]
  unsigned __int64 v290; // [rsp+1D0h] [rbp-2D78h]
  __int64 v291; // [rsp+1F0h] [rbp-2D58h] BYREF
  __int64 v292; // [rsp+208h] [rbp-2D40h] BYREF
  int v293; // [rsp+210h] [rbp-2D38h]
  __int16 v294; // [rsp+214h] [rbp-2D34h]
  const wchar_t *v295; // [rsp+218h] [rbp-2D30h]
  int v296; // [rsp+220h] [rbp-2D28h]
  unsigned int v297; // [rsp+224h] [rbp-2D24h]
  int v298; // [rsp+228h] [rbp-2D20h]
  int v299; // [rsp+22Ch] [rbp-2D1Ch]
  int v300; // [rsp+230h] [rbp-2D18h]
  int v301; // [rsp+234h] [rbp-2D14h]
  int v302; // [rsp+238h] [rbp-2D10h]
  LARGE_INTEGER v303; // [rsp+2A0h] [rbp-2CA8h] BYREF
  DirtyPageMgr *v304; // [rsp+2A8h] [rbp-2CA0h]
  LARGE_INTEGER v305; // [rsp+2B0h] [rbp-2C98h] BYREF
  DirtyPageMgr *v306; // [rsp+2B8h] [rbp-2C90h]
  __int64 v307; // [rsp+2C8h] [rbp-2C80h]
  __int64 v308; // [rsp+2D0h] [rbp-2C78h]
  __int64 v309; // [rsp+2D8h] [rbp-2C70h]
  __int64 v310; // [rsp+2E0h] [rbp-2C68h]
  __int64 v311; // [rsp+2E8h] [rbp-2C60h]
  __int64 v312; // [rsp+2F0h] [rbp-2C58h]
  __int64 v313; // [rsp+2F8h] [rbp-2C50h]
  LARGE_INTEGER PerformanceCount; // [rsp+300h] [rbp-2C48h] BYREF
  DirtyPageMgr *v315; // [rsp+308h] [rbp-2C40h]
  LARGE_INTEGER v316; // [rsp+310h] [rbp-2C38h] BYREF
  DirtyPageMgr *v317; // [rsp+318h] [rbp-2C30h]
  __int64 v318; // [rsp+320h] [rbp-2C28h]
  __int64 v319; // [rsp+328h] [rbp-2C20h]
  LARGE_INTEGER v320; // [rsp+338h] [rbp-2C10h] BYREF
  _QWORD *v321; // [rsp+340h] [rbp-2C08h]
  __int64 v322; // [rsp+350h] [rbp-2BF8h]
  __int64 v323; // [rsp+360h] [rbp-2BE8h]
  __int64 v324; // [rsp+368h] [rbp-2BE0h]
  BOOL v325; // [rsp+3E4h] [rbp-2B64h]
  int v326; // [rsp+3E8h] [rbp-2B60h]
  int v327; // [rsp+3F0h] [rbp-2B58h] BYREF
  __int64 v328; // [rsp+3F8h] [rbp-2B50h]
  __int64 v329; // [rsp+400h] [rbp-2B48h]
  __int64 v330; // [rsp+408h] [rbp-2B40h]
  __int64 v331; // [rsp+410h] [rbp-2B38h]
  _QWORD *v332; // [rsp+418h] [rbp-2B30h]
  __int64 v333; // [rsp+420h] [rbp-2B28h]
  DirtyPageMgr *v334; // [rsp+428h] [rbp-2B20h]
  DirtyPageMgr *v335; // [rsp+430h] [rbp-2B18h]
  __int64 v336; // [rsp+438h] [rbp-2B10h]
  _QWORD *v337; // [rsp+440h] [rbp-2B08h]
  __int64 v338; // [rsp+448h] [rbp-2B00h]
  _QWORD *v339; // [rsp+450h] [rbp-2AF8h]
  __int64 v340; // [rsp+458h] [rbp-2AF0h]
  _QWORD *v341; // [rsp+460h] [rbp-2AE8h]
  __int64 v342; // [rsp+468h] [rbp-2AE0h]
  __int64 v343; // [rsp+470h] [rbp-2AD8h]
  __int64 v344; // [rsp+478h] [rbp-2AD0h]
  _QWORD *v345; // [rsp+480h] [rbp-2AC8h]
  __int64 v346; // [rsp+488h] [rbp-2AC0h]
  __int64 v347; // [rsp+490h] [rbp-2AB8h]
  _QWORD *v348; // [rsp+498h] [rbp-2AB0h]
  __int64 v349; // [rsp+4A0h] [rbp-2AA8h]
  __int64 v350; // [rsp+4A8h] [rbp-2AA0h]
  __int64 v351; // [rsp+4B0h] [rbp-2A98h]
  _QWORD *v352; // [rsp+4B8h] [rbp-2A90h]
  __int64 v353; // [rsp+4C0h] [rbp-2A88h]
  __int64 v354; // [rsp+4C8h] [rbp-2A80h]
  struct SEListElem *v355; // [rsp+4D0h] [rbp-2A78h]
  _QWORD *v356; // [rsp+4D8h] [rbp-2A70h]
  __int64 v357; // [rsp+4E0h] [rbp-2A68h]
  __int64 v358; // [rsp+4E8h] [rbp-2A60h]
  __int64 v359; // [rsp+4F0h] [rbp-2A58h]
  _QWORD *v360; // [rsp+4F8h] [rbp-2A50h]
  __int64 v361; // [rsp+500h] [rbp-2A48h]
  __int64 v362; // [rsp+508h] [rbp-2A40h]
  DirtyPageMgr *v363; // [rsp+510h] [rbp-2A38h]
  char *v364; // [rsp+518h] [rbp-2A30h]
  unsigned __int64 v365; // [rsp+520h] [rbp-2A28h]
  union _LARGE_INTEGER v366; // [rsp+528h] [rbp-2A20h]
  unsigned __int64 v367; // [rsp+530h] [rbp-2A18h]
  DirtyPageMgr *v368; // [rsp+538h] [rbp-2A10h]
  __int64 v369; // [rsp+540h] [rbp-2A08h]
  unsigned __int64 v370; // [rsp+548h] [rbp-2A00h]
  union _LARGE_INTEGER v371; // [rsp+550h] [rbp-29F8h]
  unsigned __int64 v372; // [rsp+558h] [rbp-29F0h]
  __int64 v373; // [rsp+560h] [rbp-29E8h]
  __int64 v374; // [rsp+568h] [rbp-29E0h]
  __int64 v375; // [rsp+570h] [rbp-29D8h]
  __int64 v376; // [rsp+578h] [rbp-29D0h]
  DirtyPageMgr *v377; // [rsp+580h] [rbp-29C8h]
  __int64 v378; // [rsp+588h] [rbp-29C0h]
  __int64 v379; // [rsp+590h] [rbp-29B8h]
  unsigned __int64 v380; // [rsp+598h] [rbp-29B0h]
  __int64 v381; // [rsp+5A0h] [rbp-29A8h]
  unsigned __int64 v382; // [rsp+5A8h] [rbp-29A0h]
  __int64 v383; // [rsp+5B0h] [rbp-2998h]
  unsigned __int64 v384; // [rsp+5B8h] [rbp-2990h]
  __int64 v385; // [rsp+5C0h] [rbp-2988h]
  _QWORD *v386; // [rsp+5C8h] [rbp-2980h]
  __int64 v387; // [rsp+5D0h] [rbp-2978h]
  __int64 v388; // [rsp+5D8h] [rbp-2970h]
  __int64 v389; // [rsp+5E0h] [rbp-2968h]
  _QWORD *v390; // [rsp+5E8h] [rbp-2960h]
  __int64 v391; // [rsp+5F0h] [rbp-2958h]
  __int64 v392; // [rsp+5F8h] [rbp-2950h]
  __int64 v393; // [rsp+848h] [rbp-2700h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+850h] [rbp-26F8h]
  __int64 *v395; // [rsp+858h] [rbp-26F0h]
  __int64 v396; // [rsp+880h] [rbp-26C8h]
  struct CSessionTraceFlags *v397; // [rsp+888h] [rbp-26C0h]
  signed __int64 v398; // [rsp+890h] [rbp-26B8h]
  _OWORD v399[3]; // [rsp+898h] [rbp-26B0h] BYREF
  __int128 v400; // [rsp+8C8h] [rbp-2680h]
  __int128 v401; // [rsp+8D8h] [rbp-2670h]
  __int128 v402; // [rsp+8E8h] [rbp-2660h]
  __int128 v403; // [rsp+8F8h] [rbp-2650h]
  __int64 v404; // [rsp+908h] [rbp-2640h]
  char v405[8]; // [rsp+910h] [rbp-2638h] BYREF
  __int16 v406; // [rsp+918h] [rbp-2630h]
  __int16 v407; // [rsp+91Ah] [rbp-262Eh]
  int v408; // [rsp+920h] [rbp-2628h]
  _QWORD **v409; // [rsp+928h] [rbp-2620h]
  char *v410; // [rsp+930h] [rbp-2618h]
  __int64 v411; // [rsp+938h] [rbp-2610h]
  _QWORD *v412; // [rsp+940h] [rbp-2608h] BYREF
  int v413; // [rsp+948h] [rbp-2600h]
  __int16 v414; // [rsp+94Ch] [rbp-25FCh]
  __int16 v415; // [rsp+94Eh] [rbp-25FAh]
  __int64 v416; // [rsp+950h] [rbp-25F8h]
  int v417; // [rsp+958h] [rbp-25F0h]
  __int16 v418; // [rsp+95Ch] [rbp-25ECh]
  __int16 v419; // [rsp+95Eh] [rbp-25EAh]
  __int64 v420; // [rsp+960h] [rbp-25E8h]
  int v421; // [rsp+968h] [rbp-25E0h]
  __int16 v422; // [rsp+96Ch] [rbp-25DCh]
  __int16 v423; // [rsp+96Eh] [rbp-25DAh]
  __int64 v424; // [rsp+970h] [rbp-25D8h]
  int v425; // [rsp+978h] [rbp-25D0h]
  __int16 v426; // [rsp+97Ch] [rbp-25CCh]
  __int16 v427; // [rsp+97Eh] [rbp-25CAh]
  __int64 v428; // [rsp+980h] [rbp-25C8h]
  int v429; // [rsp+988h] [rbp-25C0h]
  __int16 v430; // [rsp+98Ch] [rbp-25BCh]
  __int16 v431; // [rsp+98Eh] [rbp-25BAh]
  __int64 v432; // [rsp+990h] [rbp-25B8h]
  int v433; // [rsp+998h] [rbp-25B0h]
  __int16 v434; // [rsp+99Ch] [rbp-25ACh]
  __int16 v435; // [rsp+99Eh] [rbp-25AAh]
  __int64 v436; // [rsp+9A0h] [rbp-25A8h]
  int v437; // [rsp+9A8h] [rbp-25A0h]
  __int16 v438; // [rsp+9ACh] [rbp-259Ch]
  __int16 v439; // [rsp+9AEh] [rbp-259Ah]
  char v440; // [rsp+9B0h] [rbp-2598h] BYREF
  int v441; // [rsp+B60h] [rbp-23E8h]
  int v442; // [rsp+B64h] [rbp-23E4h]
  __int64 v443; // [rsp+B68h] [rbp-23E0h]
  _QWORD v444[20]; // [rsp+B70h] [rbp-23D8h] BYREF
  char v445[8]; // [rsp+C10h] [rbp-2338h] BYREF
  __int16 v446; // [rsp+C18h] [rbp-2330h]
  __int16 v447; // [rsp+C1Ah] [rbp-232Eh]
  int v448; // [rsp+C20h] [rbp-2328h]
  int **v449; // [rsp+C28h] [rbp-2320h]
  char *v450; // [rsp+C30h] [rbp-2318h]
  __int64 v451; // [rsp+C38h] [rbp-2310h]
  int *v452; // [rsp+C40h] [rbp-2308h] BYREF
  int v453; // [rsp+C48h] [rbp-2300h]
  __int16 v454; // [rsp+C4Ch] [rbp-22FCh]
  __int16 v455; // [rsp+C4Eh] [rbp-22FAh]
  GUID *v456; // [rsp+C50h] [rbp-22F8h]
  int v457; // [rsp+C58h] [rbp-22F0h]
  __int16 v458; // [rsp+C5Ch] [rbp-22ECh]
  __int16 v459; // [rsp+C5Eh] [rbp-22EAh]
  GUID *v460; // [rsp+C60h] [rbp-22E8h]
  int v461; // [rsp+C68h] [rbp-22E0h]
  __int16 v462; // [rsp+C6Ch] [rbp-22DCh]
  __int16 v463; // [rsp+C6Eh] [rbp-22DAh]
  char v464; // [rsp+C70h] [rbp-22D8h] BYREF
  int v465; // [rsp+E60h] [rbp-20E8h]
  int v466; // [rsp+E64h] [rbp-20E4h]
  __int64 v467; // [rsp+E68h] [rbp-20E0h]
  int v468; // [rsp+E70h] [rbp-20D8h] BYREF
  unsigned __int64 v469; // [rsp+E74h] [rbp-20D4h]
  __int64 v470; // [rsp+E7Ch] [rbp-20CCh]
  __int64 v471; // [rsp+E84h] [rbp-20C4h]
  __int64 v472; // [rsp+E8Ch] [rbp-20BCh]
  __int64 v473; // [rsp+E94h] [rbp-20B4h]
  __int64 v474; // [rsp+E9Ch] [rbp-20ACh]
  __int64 v475; // [rsp+EA4h] [rbp-20A4h]
  __int64 v476; // [rsp+EACh] [rbp-209Ch]
  __int64 v477; // [rsp+EB4h] [rbp-2094h]
  __int64 v478; // [rsp+EBCh] [rbp-208Ch]
  __int64 v479; // [rsp+EC4h] [rbp-2084h]
  __int64 v480; // [rsp+ECCh] [rbp-207Ch]
  __int64 v481; // [rsp+ED4h] [rbp-2074h]
  __int64 v482; // [rsp+EDCh] [rbp-206Ch]
  __int64 v483; // [rsp+F00h] [rbp-2048h] BYREF
  char v484[40]; // [rsp+F18h] [rbp-2030h] BYREF
  char v485[8]; // [rsp+F40h] [rbp-2008h] BYREF
  __int16 v486; // [rsp+F48h] [rbp-2000h]
  __int16 v487; // [rsp+F4Ah] [rbp-1FFEh]
  int v488; // [rsp+F50h] [rbp-1FF8h]
  _DWORD **v489; // [rsp+F58h] [rbp-1FF0h]
  char *v490; // [rsp+F60h] [rbp-1FE8h]
  __int64 v491; // [rsp+F68h] [rbp-1FE0h]
  _DWORD *v492; // [rsp+F70h] [rbp-1FD8h] BYREF
  int v493; // [rsp+F78h] [rbp-1FD0h]
  __int16 v494; // [rsp+F7Ch] [rbp-1FCCh]
  __int16 v495; // [rsp+F7Eh] [rbp-1FCAh]
  char v496; // [rsp+F80h] [rbp-1FC8h] BYREF
  int v497; // [rsp+1190h] [rbp-1DB8h]
  int v498; // [rsp+1194h] [rbp-1DB4h]
  __int64 v499; // [rsp+1198h] [rbp-1DB0h]
  _DWORD v500[2]; // [rsp+11A0h] [rbp-1DA8h] BYREF
  unsigned __int64 v501; // [rsp+11A8h] [rbp-1DA0h]
  int v502; // [rsp+11B0h] [rbp-1D98h]
  unsigned int v503; // [rsp+11B4h] [rbp-1D94h]
  char v504[8]; // [rsp+11C0h] [rbp-1D88h] BYREF
  __int16 v505; // [rsp+11C8h] [rbp-1D80h]
  __int16 v506; // [rsp+11CAh] [rbp-1D7Eh]
  int v507; // [rsp+11D0h] [rbp-1D78h]
  _DWORD **v508; // [rsp+11D8h] [rbp-1D70h]
  char *v509; // [rsp+11E0h] [rbp-1D68h]
  __int64 v510; // [rsp+11E8h] [rbp-1D60h]
  _DWORD *v511; // [rsp+11F0h] [rbp-1D58h] BYREF
  int v512; // [rsp+11F8h] [rbp-1D50h]
  __int16 v513; // [rsp+11FCh] [rbp-1D4Ch]
  __int16 v514; // [rsp+11FEh] [rbp-1D4Ah]
  char v515; // [rsp+1200h] [rbp-1D48h] BYREF
  int v516; // [rsp+1410h] [rbp-1B38h]
  int v517; // [rsp+1414h] [rbp-1B34h]
  __int64 v518; // [rsp+1418h] [rbp-1B30h]
  _DWORD v519[2]; // [rsp+1420h] [rbp-1B28h] BYREF
  unsigned __int64 v520; // [rsp+1428h] [rbp-1B20h]
  int v521; // [rsp+1430h] [rbp-1B18h]
  unsigned int v522; // [rsp+1434h] [rbp-1B14h]
  char v523[8]; // [rsp+1440h] [rbp-1B08h] BYREF
  __int16 v524; // [rsp+1448h] [rbp-1B00h]
  __int16 v525; // [rsp+144Ah] [rbp-1AFEh]
  int v526; // [rsp+1450h] [rbp-1AF8h]
  _DWORD **v527; // [rsp+1458h] [rbp-1AF0h]
  char *v528; // [rsp+1460h] [rbp-1AE8h]
  __int64 v529; // [rsp+1468h] [rbp-1AE0h]
  _DWORD *v530; // [rsp+1470h] [rbp-1AD8h] BYREF
  int v531; // [rsp+1478h] [rbp-1AD0h]
  __int16 v532; // [rsp+147Ch] [rbp-1ACCh]
  __int16 v533; // [rsp+147Eh] [rbp-1ACAh]
  char v534; // [rsp+1480h] [rbp-1AC8h] BYREF
  int v535; // [rsp+1690h] [rbp-18B8h]
  int v536; // [rsp+1694h] [rbp-18B4h]
  __int64 v537; // [rsp+1698h] [rbp-18B0h]
  _DWORD v538[2]; // [rsp+16A0h] [rbp-18A8h] BYREF
  unsigned __int64 v539; // [rsp+16A8h] [rbp-18A0h]
  unsigned int v540; // [rsp+16B0h] [rbp-1898h]
  int v541; // [rsp+16B4h] [rbp-1894h]
  char v542[48]; // [rsp+16C0h] [rbp-1888h] BYREF
  char v543[4608]; // [rsp+16F0h] [rbp-1858h] BYREF
  _BYTE v544[784]; // [rsp+28F0h] [rbp-658h] BYREF
  _BYTE v545[808]; // [rsp+2C00h] [rbp-348h] BYREF

  v393 = -2;
  v256 = 0;
  v263 = 8;
  v264 = 0;
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v484, 0, 0, 0, (int (*)(int, int, int, int, char *))HandleAndNoteToErrorlog, 0);
    v292 = 0;
    v293 = 0;
    v294 = 45;
    v295 = L"Logwriter Task";
    CAutoSetupExecContextsForInternalTasks::Setup(&v292, 0);
    try
    {
      ExcHandler::ExcHandler(
        (ExcHandler *)v542,
        0,
        0,
        0,
        (int (*)(int, int, int, int, char *))HandleAndNoteToErrorlog,
        0);
      v257 = byte_10317AF70;
      if ( (byte_10317AF70 & 1) != 0 )
        goto LABEL_35;
      v266 = 0;
      ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
      v395 = (__int64 *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset);
      v98 = *v395;
      v396 = v98;
      if ( v98 && (v110 = **(struct CSessionTraceFlags ***)(v98 + 56), (v397 = v110) != 0) )
      {
        v99 = CSessionTraceFlags::CheckSessionTraceInternal(v110, 0x1F80u);
        v266 = v99;
      }
      else
      {
        v99 = v266;
      }
      if ( v99 )
      {
LABEL_35:
        HIDWORD(v252) = 1;
        CurrentProcess = GetCurrentProcess();
        GetProcessPriorityBoost(CurrentProcess, (PBOOL)&v252 + 1);
        if ( HIDWORD(v252) )
        {
          CurrentThread = GetCurrentThread();
          GetThreadPriorityBoost(CurrentThread, (PBOOL)&v252 + 1);
          if ( HIDWORD(v252) )
          {
            v113 = GetCurrentThread();
            SetThreadPriorityBoost(v113, 0);
          }
        }
      }
      else
      {
        HIDWORD(v252) = 0;
      }
      v289 = 0;
      UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( (_DWORD)qword_103172600 )
      {
        v100 = 0;
      }
      else
      {
        v398 = _InterlockedCompareExchange64(&qword_103172600, UniqueThread_low, 0);
        v100 = v398 == 0;
      }
      v325 = v100;
      if ( !v100 )
      {
        if ( (SOS_PublicGlobals::sm_osStats & 0x80u) != 0 && (SOS_PublicGlobals::sm_osStats & 4) != 0 )
        {
          v288 = 0;
          v332 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v101 = v332[SystemThread_TlsIndex] + SystemThread_TlsOffset == 0;
          v102 = v332[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v333 = v102;
          if ( !v101 && *(_QWORD *)(v102 + 272) == v102 )
          {
            v104 = *(_QWORD *)(v102 + 256);
            v288 = v104;
          }
          else
          {
            v104 = v288;
          }
          v272 = v104;
          if ( v104 )
          {
            v326 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v303);
              QuadPart = (DirtyPageMgr *)v303.QuadPart;
              v304 = (DirtyPageMgr *)v303.QuadPart;
            }
            else
            {
              QuadPart = MEMORY[0x7FFE0008];
              v334 = MEMORY[0x7FFE0008];
              v304 = MEMORY[0x7FFE0008];
              v104 = v272;
            }
            v289 = QuadPart;
          }
        }
        else
        {
          v104 = 0;
          v272 = 0;
        }
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<126,13,258>::SpinToAcquireWithExponentialBackoff(&qword_103172600, UniqueThread_low);
        else
          Spinlock<126,13,258>::SpinToAcquireOptimistic(&qword_103172600, v104, UniqueThread_low);
        if ( v104 )
        {
          v296 = Base_PublicGlobals::sm_invariantTscAvailable;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v305);
            v106 = (DirtyPageMgr *)v305.QuadPart;
            v306 = (DirtyPageMgr *)v305.QuadPart;
          }
          else
          {
            v106 = MEMORY[0x7FFE0008];
            v335 = MEMORY[0x7FFE0008];
            v306 = MEMORY[0x7FFE0008];
            v104 = v272;
          }
          if ( v106 < v289 )
          {
            v107 = 0;
            v265 = 0;
          }
          else
          {
            v107 = v106 - v289;
            v265 = v107;
          }
          v253 = v107;
          v336 = v104 + 3192;
          *(_QWORD *)(v104 + 3192) += v107;
        }
      }
      v108 = 0;
      for ( i = 0; ; i = v108 )
      {
        v109 = v108;
        if ( v108 >= SQLServerLogMgr::sm_totalLogWriters )
          break;
        if ( !*((_DWORD *)&SQLServerLogMgr::sm_logWriTid + v108) )
          goto LABEL_125;
        ++v108;
      }
      utassert_fail(
        1u,
        "index < sm_totalLogWriters",
        "\"sql\\\\ntdbms\\\\storeng\\\\dfs\\\\trans\\\\logmgr.cpp\"",
        24472,
        0);
LABEL_125:
      *((_DWORD *)&SQLServerLogMgr::sm_logWriTid + v109) = GetCurrentThreadId();
      v337 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v62 = v337[SystemThread_TlsIndex] + SystemThread_TlsOffset;
      v338 = v62;
      v63 = *(_QWORD *)(v62 + 256);
      v307 = v63;
      if ( !v63 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v63 = *(_QWORD *)(v62 + 256);
        v307 = v63;
      }
      (&SQLServerLogMgr::sm_logWriSched)[v109] = *(struct SOS_Scheduler * near **)(v63 + 608);
      v339 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v64 = v339[SystemThread_TlsIndex] + SystemThread_TlsOffset;
      v340 = v64;
      v65 = *(_QWORD *)(v64 + 256);
      v308 = v65;
      if ( !v65 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v65 = *(_QWORD *)(v64 + 256);
        v308 = v65;
      }
      if ( (*(_BYTE *)(*(_QWORD *)(v65 + 608) + 5104LL) & 2) != 0 )
      {
        v297 = SOS_OS_NumberOfMemoryNodeInfos;
        v66 = SOS_PublicGlobals::sm_NodeManager[4];
        if ( v66 <= SOS_OS_NumberOfMemoryNodeInfos )
          LODWORD(v66) = SOS_OS_NumberOfMemoryNodeInfos;
        v271 = i + v66;
        v341 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v342 = v341[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v343 = *(_QWORD *)(v342 + 8);
        v344 = *(_QWORD *)(v343 + 96);
        *(_DWORD *)(v344 + 1248) = i + v66;
      }
      v258 = (char)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
      if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v67 = rand();
        if ( v67 == 5 * (v67 / 5) )
          Spinlock<126,13,258>::UpdateStatSnapshot();
      }
      qword_103172600 = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            v345 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v68 = v345[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v346 = v68;
            v69 = *(_QWORD *)(v68 + 256);
            v309 = v69;
            if ( !v69 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v69 = *(_QWORD *)(v68 + 256);
              v309 = v69;
            }
            v70 = *(void **)(v69 + 496);
            if ( v70 )
            {
              v347 = *(_QWORD *)(v69 + 496);
              operator delete[](v70);
              *(_QWORD *)(v69 + 496) = 0;
            }
            v256 = 0;
            if ( !byte_10317B618 )
              break;
            v327 = 4194644;
            v328 = 0;
            v330 = 0;
            v329 = 0;
            v331 = 0;
            SOS_Task::Sleep(1000, &v327);
            v348 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v114 = v348[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v349 = v114;
            v115 = *(_QWORD *)(v114 + 256);
            v310 = v115;
            if ( !v115 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v115 = *(_QWORD *)(v114 + 256);
              v310 = v115;
            }
            v116 = *(_QWORD *)(v115 + 600);
            v350 = v116;
            v117 = 0;
            v273 = 0;
            while ( v117 < 0x40 )
            {
              v118 = (__int64 *)(v116 + 8 * (v117 + 57LL));
              v119 = *v118;
              v351 = v119;
              if ( v119 )
              {
                Pool = MemoryPoolManager::GetPool(v117);
                SOS_MemoryPool::TransferMemory(Pool, v119 / 0x2000, 6);
                *(_QWORD *)(v116 + 432) -= v119;
                *v118 -= v119;
                *(_QWORD *)(v116 + 448) -= v119;
              }
              v273 = ++v117;
            }
            v352 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v121 = v352[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v353 = v121;
            v122 = *(_QWORD *)(v121 + 256);
            v311 = v122;
            if ( !v122 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v122 = *(_QWORD *)(v121 + 256);
              v311 = v122;
            }
            v123 = *(void **)(v122 + 496);
            if ( v123 )
            {
              v354 = *(_QWORD *)(v122 + 496);
              operator delete[](v123);
              *(_QWORD *)(v122 + 496) = 0;
            }
          }
          v71 = v263;
          v72 = ResQueueBase::Dequeue((ResQueueBase *)&SQLServerLogMgr::m_compQueue, 0x4000D9u, v263, 0);
          v128 = v72;
          v355 = v72;
          if ( v72 )
          {
            v270 = v72;
          }
          else
          {
            v128 = 0;
            v270 = 0;
          }
          v126 = v128;
          v256 = v128;
          if ( v128 )
            break;
          v84 = 128;
          if ( 2 * v71 < 0x80 )
            v84 = 2 * v71;
          v263 = v84;
          v356 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v85 = v356[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v357 = v85;
          v86 = *(_QWORD *)(v85 + 256);
          v312 = v86;
          if ( !v86 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v86 = *(_QWORD *)(v85 + 256);
            v312 = v86;
          }
          v87 = *(_QWORD *)(v86 + 600);
          v358 = v87;
          v88 = 0;
          v274 = 0;
          while ( v88 < 0x40 )
          {
            v89 = (__int64 *)(v87 + 8 * (v88 + 57LL));
            v90 = *v89;
            v359 = v90;
            if ( v90 )
            {
              v124 = MemoryPoolManager::GetPool(v88);
              SOS_MemoryPool::TransferMemory(v124, v90 / 0x2000, 6);
              *(_QWORD *)(v87 + 432) -= v90;
              *v89 -= v90;
              *(_QWORD *)(v87 + 448) -= v90;
            }
            v274 = ++v88;
          }
          v360 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v91 = v360[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v361 = v91;
          v92 = *(_QWORD *)(v91 + 256);
          v313 = v92;
          if ( !v92 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v92 = *(_QWORD *)(v91 + 256);
            v313 = v92;
          }
          v93 = *(void **)(v92 + 496);
          if ( v93 )
          {
            v362 = *(_QWORD *)(v92 + 496);
            operator delete[](v93);
            *(_QWORD *)(v92 + 496) = 0;
          }
        }
        v263 = 8;
        v141 = (SQLServerLogMgr **)((char *)v128 + 16);
        v254 = (SQLServerLogMgr **)((char *)v128 + 16);
        v140 = *((_QWORD *)v128 + 2);
        v255 = v140;
        v127 = v140;
        v277 = v140;
        v73 = (_DWORD *)((char *)v128 + 48);
        if ( *((_DWORD *)v128 + 12) != 1 )
        {
          v74 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
          v259 = CommonGlobalState::m_PerfCountersEnabled;
          if ( CommonGlobalState::m_PerfCountersEnabled )
          {
            PerfmonManager::IncrementCounterInstanceValue(
              (PerfmonManager *)&ResourceStr,
              5u,
              0x180u,
              1,
              *(unsigned __int16 *)(*(_QWORD *)(v140 + 8) + 1720LL),
              0);
            v74 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
          }
          if ( *v74 )
          {
            v129 = *(_WORD *)(*(_QWORD *)(v140 + 8) + 1720LL);
            v261 = v129;
            v298 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&PerformanceCount);
              v125 = (DirtyPageMgr *)PerformanceCount.QuadPart;
              v315 = (DirtyPageMgr *)PerformanceCount.QuadPart;
            }
            else
            {
              v125 = MEMORY[0x7FFE0008];
              v363 = MEMORY[0x7FFE0008];
              v315 = MEMORY[0x7FFE0008];
              v126 = v256;
              v127 = v277;
              v128 = v270;
              v129 = v261;
            }
            v364 = (char *)v128 + 40;
            v75 = *((_QWORD *)v128 + 5);
            if ( (unsigned __int64)v125 < v75 )
            {
              v130 = 0;
              v265 = 0;
            }
            else
            {
              v130 = (unsigned __int64)v125 - v75;
              v265 = v130;
            }
            v365 = v130;
            if ( v130 == -1 )
            {
              v131 = -1;
              v287 = -1;
            }
            else
            {
              v299 = Base_PublicGlobals::sm_invariantTscAvailable;
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                v366 = Base_PublicGlobals::sm_QueryPerformanceFrequency;
                v131 = 1000000 * v130 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                v287 = v131;
              }
              else
              {
                v131 = v130 / 0xA;
                v367 = v130 / 0xA;
                v287 = v130 / 0xA;
              }
            }
            PerfmonManager::IncrementCounterInstanceValue((PerfmonManager *)&ResourceStr, 5u, 0x188u, v131, v129, 0);
          }
        }
        v265 = 0x100000018LL;
        if ( (qword_10317F720 & 1) != 0 && (_DWORD)SQLServerLogMgr::sm_logWriTid == GetCurrentThreadId() )
        {
          v300 = Base_PublicGlobals::sm_invariantTscAvailable;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v316);
            v132 = (DirtyPageMgr *)v316.QuadPart;
            v317 = (DirtyPageMgr *)v316.QuadPart;
          }
          else
          {
            v132 = MEMORY[0x7FFE0008];
            v368 = MEMORY[0x7FFE0008];
            v317 = MEMORY[0x7FFE0008];
            v126 = v256;
            v127 = v277;
            v128 = v270;
          }
          v369 = v127 + 3184;
          v133 = *(_QWORD *)(v127 + 3184);
          if ( (unsigned __int64)v132 < v133 )
          {
            v134 = 0;
            v265 = 0;
          }
          else
          {
            v134 = (unsigned __int64)v132 - v133;
            v265 = v134;
          }
          v370 = v134;
          if ( v134 == -1 )
          {
            v135 = -1;
            v290 = -1;
          }
          else
          {
            v301 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              v371 = Base_PublicGlobals::sm_QueryPerformanceFrequency;
              v135 = 1000 * v134 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
              v290 = v135;
            }
            else
            {
              v135 = v134 / 0x2710;
              v372 = v134 / 0x2710;
              v290 = v134 / 0x2710;
            }
          }
          if ( v135 > 1000LL * dword_1031C91A8 )
          {
            SOS_LogGovernorStats::SOS_LogGovernorStats((SOS_LogGovernorStats *)v399);
            (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v127 + 584LL))(v127, v399);
            v269 = v127 + 2976;
            v446 = 0;
            v447 = 3;
            v448 = 0;
            v449 = &v452;
            v450 = &v464;
            v465 = 0;
            v466 = 0;
            v451 = 0;
            v467 = 0;
            v452 = &v468;
            v453 = 132;
            v454 = 2;
            v455 = 0;
            v456 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
            v457 = 16;
            v458 = 15;
            v459 = 0;
            v460 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
            v461 = 16;
            v462 = 16;
            v463 = 0;
            v468 = *(unsigned __int16 *)(*(_QWORD *)(v127 + 8) + 1720LL);
            v469 = v135;
            v470 = *(_QWORD *)(v127 + 2976);
            v471 = *(_QWORD *)(v127 + 2984);
            v472 = *(_QWORD *)(v127 + 2992);
            v473 = *(_QWORD *)(v127 + 3000);
            v474 = *(_QWORD *)(v127 + 3008);
            v475 = *(_QWORD *)(v127 + 3024);
            v476 = *(_QWORD *)(v127 + 3016);
            v477 = *(_QWORD *)(v127 + 3032);
            v478 = *(_QWORD *)(v127 + 3040);
            v479 = *(_QWORD *)(v127 + 3048);
            v480 = *(_QWORD *)(v127 + 3056);
            v275 = DWORD2(v401);
            v319 = DWORD2(v401) - *(_DWORD *)(v127 + 3136);
            v318 = *((_QWORD *)&v400 + 1);
            v136 = *((_QWORD *)&v400 + 1) - *(_QWORD *)(v127 + 3120);
            v373 = v136;
            v137 = v319;
            v481 = v319;
            v482 = v136;
            v374 = *(_QWORD *)(*(_QWORD *)(v127 + 8) + 1712LL) + 596LL;
            v456 = (GUID *)v374;
            v459 = 0;
            v375 = *(_QWORD *)(*(_QWORD *)(v127 + 8) + 1712LL) + 580LL;
            v460 = (GUID *)v375;
            v461 = 16;
            v462 = 16;
            v463 = 0;
            XeSqlPkg::log_production_stats::Publish((XeSqlPkg::log_production_stats *)v445);
            if ( dword_103172528 )
            {
              v281 = 24;
              v282 = 2;
              if ( (qword_10317F720 & 2) != 0 )
              {
                v406 = 0;
                v407 = 7;
                v408 = 0;
                v409 = &v412;
                v410 = &v440;
                v441 = 0;
                v442 = 0;
                v411 = 0;
                v443 = 0;
                v412 = v444;
                v413 = 152;
                v414 = 6;
                v415 = 0;
                v416 = 0;
                v417 = 0;
                v418 = 13;
                v419 = 0;
                v420 = 0;
                v421 = 0;
                v422 = 14;
                v423 = 0;
                v424 = 0;
                v425 = 0;
                v426 = 15;
                v427 = 0;
                v428 = 0;
                v429 = 0;
                v430 = 16;
                v431 = 0;
                v432 = 0;
                v433 = 0;
                v434 = 17;
                v435 = 0;
                v436 = 0;
                v437 = 0;
                v438 = 18;
                v439 = 0;
                memset_0(v545, 0, 0x316u);
                memset_0(v544, 0, sizeof(v544));
                v376 = *(_QWORD *)(*(_QWORD *)(v127 + 8) + 1712LL);
                v279 = 0;
                v138 = ((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v376, &v279);
                PrepareMdmXEvent<XeSqlPkg::log_production_stats_mdm>(v405, v138, L"MicrosoftSql", v545, 395, v544, 392);
                v444[0] = *(_QWORD *)v269;
                v444[1] = *(_QWORD *)(v127 + 2984);
                v444[2] = *(_QWORD *)(v127 + 2992);
                v444[3] = *(_QWORD *)(v127 + 3000);
                v444[4] = *(_QWORD *)(v127 + 3008);
                v444[5] = *(_QWORD *)(v127 + 3024);
                v444[6] = *(_QWORD *)(v127 + 3016);
                v444[7] = *(_QWORD *)(v127 + 3032);
                v444[8] = *(_QWORD *)(v127 + 3040);
                v444[9] = *(_QWORD *)(v127 + 3048);
                v444[10] = *(_QWORD *)(v127 + 3056);
                v444[11] = v137;
                v444[12] = v136;
                XeSqlPkg::log_production_stats_mdm::Publish((XeSqlPkg::log_production_stats_mdm *)v405);
              }
            }
            v321 = (_QWORD *)(v127 + 3184);
            v302 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v320);
              *(LARGE_INTEGER *)(v127 + 3184) = v320;
            }
            else
            {
              v377 = MEMORY[0x7FFE0008];
              *v321 = MEMORY[0x7FFE0008];
            }
            memset_0((void *)(v127 + 2976), 0, 0xD0u);
            v139 = v269;
            *(_OWORD *)(v269 + 88) = v399[0];
            *(_OWORD *)(v139 + 104) = v399[1];
            *(_OWORD *)(v139 + 120) = v399[2];
            *(_OWORD *)(v139 + 136) = v400;
            *(_OWORD *)(v139 + 152) = v401;
            *(_OWORD *)(v139 + 168) = v402;
            *(_OWORD *)(v139 + 184) = v403;
            *(_QWORD *)(v139 + 200) = v404;
            v126 = v256;
            v127 = v277;
            v128 = v270;
            v140 = v255;
          }
          v141 = v254;
        }
        v76 = *(_QWORD *)(v127 + 51200);
        if ( v76 )
        {
          if ( *(_BYTE *)(v76 + 209) )
          {
            v142 = v264++;
            if ( (v142 & 1) == 0 )
            {
              v264 = 0;
              LogPoolSharedCacheBufferFreePoolMgr::ReFill((LogPoolSharedCacheBufferFreePoolMgr *)(v76 + 304));
            }
          }
        }
        if ( *((_DWORD *)v128 + 8) == 1 )
          goto LABEL_161;
        v97 = (SQLServerLogMgr *)(unsigned int)(*((_DWORD *)v128 + 8) - 2);
        if ( *((_DWORD *)v128 + 8) == 2 )
          break;
        if ( *((_DWORD *)v128 + 8) == 3 )
        {
          v143 = 0;
          LOBYTE(v252) = 0;
          v144 = *((_DWORD *)v128 + 9);
          if ( v144 == 995
            || *((_DWORD *)v128 + 9) == 1237
            || *((_DWORD *)v128 + 9) == 1450
            || *((_DWORD *)v128 + 9) == 1453
            || *((_DWORD *)v128 + 9) == 1816 )
          {
            v143 = 1;
            LOBYTE(v252) = 1;
          }
          if ( v143 )
          {
            v145 = *((_QWORD *)v128 + 3);
            v378 = v145;
            if ( *(_BYTE *)(v145 + 51) )
            {
              v283 = 23;
              v284 = 0x400000;
              if ( (dword_10317F71C & 0x400000) != 0 )
              {
                v486 = 0;
                v487 = 1;
                v488 = 0;
                v489 = &v492;
                v490 = &v496;
                v497 = 0;
                v498 = 0;
                v491 = 0;
                v499 = 0;
                v492 = v500;
                v493 = 24;
                v494 = 0;
                v495 = 0;
                v500[0] = *(unsigned __int16 *)(*(_QWORD *)(v127 + 8) + 1720LL);
                v500[1] = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v145 + 24) + 112LL) + 32LL);
                v267 = 0;
                v268 = 0;
                v379 = v145 + 188;
                v267 = *(_DWORD *)(v145 + 188);
                v268 = *(_DWORD *)(v145 + 192);
                v380 = v268 | ((unsigned __int64)v267 << 32);
                v501 = v380;
                v502 = 4096;
                v503 = v144;
                XeSqlPkg::log_flush_retry::Publish((XeSqlPkg::log_flush_retry *)v485);
              }
              SQLServerLogMgr::UpdateFileHdr(
                (SQLServerLogMgr *)v127,
                *(struct LFCB **)(v145 + 24),
                v128,
                (struct LC *)v145);
            }
            else
            {
              v147 = *((_QWORD *)v128 + 9);
              if ( v147 )
              {
                v148 = *((_DWORD *)v128 + 16);
                v276 = v148;
                v322 = v147;
                while ( v147 )
                {
                  v148 += *(_DWORD *)(v147 + 8);
                  v276 = v148;
                  v147 = *(_QWORD *)(v147 + 16);
                  v322 = v147;
                }
                v253 = 0x40000000000017LL;
                if ( (dword_10317F71C & 0x400000) != 0 )
                {
                  v524 = 0;
                  v525 = 1;
                  v526 = 0;
                  v527 = &v530;
                  v528 = &v534;
                  v535 = 0;
                  v536 = 0;
                  v529 = 0;
                  v537 = 0;
                  v530 = v538;
                  v531 = 24;
                  v532 = 0;
                  v533 = 0;
                  v538[0] = *(unsigned __int16 *)(*(_QWORD *)(v127 + 8) + 1720LL);
                  v538[1] = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v145 + 24) + 112LL) + 32LL);
                  v254 = 0;
                  v383 = v145 + 188;
                  v254 = *(SQLServerLogMgr ***)(v145 + 188);
                  v384 = HIDWORD(v254) | ((unsigned __int64)(unsigned int)v254 << 32);
                  v539 = v384;
                  v540 = v148;
                  v541 = *((_DWORD *)v126 + 9);
                  XeSqlPkg::log_flush_retry::Publish((XeSqlPkg::log_flush_retry *)v523);
                }
                *((_DWORD *)v126 + 9) = 0;
                FCB::GatherWrite(
                  *(FCB **)(*(_QWORD *)(v145 + 24) + 112LL),
                  (struct SEListElem *)((char *)v126 + 56),
                  v148,
                  *(_QWORD *)(*(_QWORD *)(v145 + 24) + 56LL) + ((unsigned __int64)*(unsigned int *)(v145 + 192) << 9),
                  (void (*)(struct SOS_IOCompRequest *))SQLServerLogMgr::LogIOCompletion,
                  v126,
                  0,
                  0,
                  0);
              }
              else
              {
                v285 = 23;
                v286 = 0x400000;
                if ( (dword_10317F71C & 0x400000) != 0 )
                {
                  v505 = 0;
                  v506 = 1;
                  v507 = 0;
                  v508 = &v511;
                  v509 = &v515;
                  v516 = 0;
                  v517 = 0;
                  v510 = 0;
                  v518 = 0;
                  v511 = v519;
                  v512 = 24;
                  v513 = 0;
                  v514 = 0;
                  v519[0] = *(unsigned __int16 *)(*(_QWORD *)(v127 + 8) + 1720LL);
                  v519[1] = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v145 + 24) + 112LL) + 32LL);
                  v255 = 0;
                  v381 = v145 + 188;
                  v255 = *(_QWORD *)(v145 + 188);
                  v382 = HIDWORD(v255) | ((unsigned __int64)(unsigned int)v255 << 32);
                  v520 = v382;
                  v521 = *(unsigned __int16 *)(v145 + 182);
                  v522 = v144;
                  XeSqlPkg::log_flush_retry::Publish((XeSqlPkg::log_flush_retry *)v504);
                }
                *((_DWORD *)v128 + 9) = 0;
                (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned __int64, void (__fastcall *)(struct SOS_IOCompRequest *), struct SEListElem *, _QWORD, _QWORD, _QWORD, _QWORD, __int64, __int64))(**(_QWORD **)(*(_QWORD *)(v145 + 24) + 112LL) + 8LL))(
                  *(_QWORD *)(*(_QWORD *)(v145 + 24) + 112LL),
                  *(_QWORD *)(v145 + 104),
                  *(unsigned __int16 *)(v145 + 182),
                  *(_QWORD *)(*(_QWORD *)(v145 + 24) + 56LL) + ((unsigned __int64)*(unsigned int *)(v145 + 192) << 9),
                  SQLServerLogMgr::LogIOCompletion,
                  v128,
                  0,
                  0,
                  0,
                  0,
                  v252,
                  v253);
              }
            }
          }
          else
          {
            OSErrString = GetOSErrString(v144, (struct ErrorStringHolder *)v543, 0, 0);
            scierrlog(0x429Du, L"SQLServerLogMgr::LogWriter", OSErrString);
            log_unlocalized_systemmetadata(L"Write error during log flush.\n");
            SQLServerLogMgr::IoErrorLC(*v141, v128);
            v256 = 0;
          }
        }
LABEL_168:
        v386 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v78 = v386[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v387 = v78;
        v79 = *(_QWORD *)(v78 + 256);
        v323 = v79;
        if ( !v79 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v79 = *(_QWORD *)(v78 + 256);
          v323 = v79;
        }
        v80 = *(_QWORD *)(v79 + 600);
        v388 = v80;
        v81 = 0;
        v278 = 0;
        while ( v81 < 0x40 )
        {
          v82 = (__int64 *)(v80 + 8 * (v81 + 57LL));
          v83 = *v82;
          v389 = v83;
          if ( v83 )
          {
            v146 = MemoryPoolManager::GetPool(v81);
            SOS_MemoryPool::TransferMemory(v146, v83 / 0x2000, 6);
            *(_QWORD *)(v80 + 432) -= v83;
            *v82 -= v83;
            *(_QWORD *)(v80 + 448) -= v83;
          }
          v278 = ++v81;
        }
        v390 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v94 = v390[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v391 = v94;
        v95 = *(_QWORD *)(v94 + 256);
        v324 = v95;
        if ( !v95 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v95 = *(_QWORD *)(v94 + 256);
          v324 = v95;
        }
        v96 = *(void **)(v95 + 496);
        if ( v96 )
        {
          v392 = *(_QWORD *)(v95 + 496);
          operator delete[](v96);
          *(_QWORD *)(v95 + 496) = 0;
        }
      }
      if ( *v73 == 1 )
      {
        *v73 = 2;
        SQLServerLogMgr::ReadAndValidateBlock(v97, *((struct LC **)v128 + 3));
        SQLServerLogMgr::CompleteLCFlush((SQLServerLogMgr *)v127, v128, 0);
        goto LABEL_168;
      }
LABEL_161:
      SQLServerLogMgr::GetFlushQAccess((SQLServerLogMgr *)v127);
      v385 = v127 + 2448;
      *(_QWORD *)v128 = *(_QWORD *)(v127 + 2448);
      *(_QWORD *)(*(_QWORD *)(v127 + 2448) + 8LL) = v128;
      *(_QWORD *)(v127 + 2448) = v128;
      *((_QWORD *)v128 + 1) = v127 + 2448;
      v256 = 0;
      v77 = *(_DWORD *)(v127 + 2464);
      if ( !v77 )
      {
        utassert_fail(
          1u,
          "logmgr->m_ioMesgOutstanding > 0",
          "\"sql\\\\ntdbms\\\\storeng\\\\dfs\\\\trans\\\\logmgr.cpp\"",
          24714,
          0);
        v77 = *(_DWORD *)(v140 + 2464);
      }
      *(_DWORD *)(v127 + 2464) = v77 - 1;
      if ( byte_10316E9BF || (qword_10317AFE6 & 0x800000000LL) != 0 )
        SQLServerLogMgr::FlushLCNew((SQLServerLogMgr *)v127, 0);
      else
        SQLServerLogMgr::FlushLCOld((SQLServerLogMgr *)v127, 0);
      goto LABEL_168;
    }
    catch ( SQLError v291 )
    {
      v157 = v251;
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)(v157 + 2144), (const struct SQLError *)(v157 + 496));
        *((_QWORD *)v157 + 53) = &qword_103172600;
        *((_QWORD *)v157 + 52) = 0;
        *((_QWORD *)v157 + 51) = 0;
        *((_QWORD *)v157 + 41) = 0;
        *((_QWORD *)v157 + 13) = 0;
        *((_QWORD *)v157 + 12) = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        *((_DWORD *)v157 + 39) = 256;
        *((_QWORD *)v157 + 192) = &qword_103172600;
        if ( (_DWORD)qword_103172600 )
        {
          v159 = 0;
        }
        else
        {
          v158 = _InterlockedCompareExchange64(&qword_103172600, *((_QWORD *)v157 + 12), 0);
          *((_QWORD *)v157 + 193) = v158;
          *((_QWORD *)v157 + 194) = v158;
          v159 = v158 == 0;
        }
        *((_DWORD *)v157 + 143) = v159;
        if ( !v159 )
        {
          v160 = SOS_PublicGlobals::sm_osStats;
          if ( (SOS_PublicGlobals::sm_osStats & 0x80u) != 0 && (v160 & 4) != 0 )
          {
            *((_QWORD *)v157 + 59) = 0;
            *((_DWORD *)v157 + 144) = 88;
            v161 = NtCurrentTeb()->ThreadLocalStoragePointer;
            *((_QWORD *)v157 + 195) = v161;
            v101 = v161[SystemThread_TlsIndex] + SystemThread_TlsOffset == 0;
            v162 = v161[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            *((_QWORD *)v157 + 196) = v162;
            if ( !v101 && *(_QWORD *)(v162 + 272) == v162 )
            {
              v164 = *(_QWORD *)(v162 + 256);
              *((_QWORD *)v157 + 59) = v164;
            }
            else
            {
              v164 = *((_QWORD *)v157 + 59);
            }
          }
          else
          {
            v164 = 0;
          }
          *((_QWORD *)v157 + 13) = v164;
          if ( v164 )
          {
            *((_QWORD *)v157 + 197) = v157 + 480;
            *((_DWORD *)v157 + 145) = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              *((_DWORD *)v157 + 146) = QueryPerformanceCounter((LARGE_INTEGER *)v157 + 110);
              v165 = (DirtyPageMgr *)*((_QWORD *)v157 + 110);
              *((_QWORD *)v157 + 60) = v165;
            }
            else
            {
              v165 = MEMORY[0x7FFE0008];
              *((_QWORD *)v157 + 198) = MEMORY[0x7FFE0008];
              *((_QWORD *)v157 + 60) = v165;
              v164 = *((_QWORD *)v157 + 13);
            }
            *((_QWORD *)v157 + 199) = v165;
            *((_QWORD *)v157 + 41) = v165;
          }
          *((_DWORD *)v157 + 147) = 2;
          v166 = &qword_103172600;
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<126,13,258>::SpinToAcquireWithExponentialBackoff(v166, *((_QWORD *)v157 + 12));
          else
            Spinlock<126,13,258>::SpinToAcquireOptimistic(v166, v164, *((_QWORD *)v157 + 12));
          if ( v164 )
          {
            *((_QWORD *)v157 + 200) = v157 + 304;
            *((_DWORD *)v157 + 161) = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              *((_DWORD *)v157 + 148) = QueryPerformanceCounter((LARGE_INTEGER *)v157 + 111);
              v167 = (DirtyPageMgr *)*((_QWORD *)v157 + 111);
              *((_QWORD *)v157 + 38) = v167;
            }
            else
            {
              v167 = MEMORY[0x7FFE0008];
              *((_QWORD *)v157 + 201) = MEMORY[0x7FFE0008];
              *((_QWORD *)v157 + 38) = v167;
              v164 = *((_QWORD *)v157 + 13);
            }
            *((_QWORD *)v157 + 202) = v157 + 328;
            *((_QWORD *)v157 + 203) = v157 + 304;
            v168 = *((_QWORD *)v157 + 41);
            if ( (unsigned __int64)v167 < v168 )
            {
              v169 = 0;
              *((_QWORD *)v157 + 11) = 0;
            }
            else
            {
              v169 = (char *)v167 - v168;
              *((_QWORD *)v157 + 11) = v169;
            }
            *((_QWORD *)v157 + 11) = v169;
            *((_QWORD *)v157 + 204) = v169;
            *((_QWORD *)v157 + 205) = v164 + 3192;
            *(_QWORD *)(v164 + 3192) += v169;
          }
        }
        CurrentThreadId = GetCurrentThreadId();
        *((_DWORD *)v157 + 149) = CurrentThreadId;
        v171 = 0;
        *((_DWORD *)v157 + 85) = 0;
        v172 = SQLServerLogMgr::sm_totalLogWriters;
        while ( (unsigned int)v171 < v172 )
        {
          v173 = &____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4;
          if ( *((_DWORD *)&SQLServerLogMgr::sm_logWriTid + v171) == CurrentThreadId )
          {
            *(_DWORD *)&v173[3125044].Data4[4 * v171] = 0;
            (&SQLServerLogMgr::sm_logWriSched)[v171] = 0;
            break;
          }
          v171 = (unsigned int)(v171 + 1);
          *((_DWORD *)v157 + 85) = v171;
        }
        *((_QWORD *)v157 + 206) = &qword_103172600;
        v157[124] = (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v174 = rand();
          if ( v174 == 5 * (v174 / 5) )
            Spinlock<126,13,258>::UpdateStatSnapshot();
        }
        *((_QWORD *)v157 + 207) = &qword_103172600;
        qword_103172600 = 0;
        v175 = *((_DWORD *)v157 + 124);
        if ( v175 / 100 == 29 )
        {
          if ( v175 == 2905 )
          {
            *((_DWORD *)v157 + 150) = 88;
            v176 = NtCurrentTeb()->ThreadLocalStoragePointer;
            *((_QWORD *)v157 + 208) = v176;
            v177 = v176[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            *((_QWORD *)v157 + 209) = v177;
            *((_QWORD *)v157 + 210) = v177;
            v178 = *(_QWORD *)(v177 + 80);
            *((_QWORD *)v157 + 211) = v178;
            *((_QWORD *)v157 + 212) = v178;
            scierrlog(0x439Cu, L"LogWriter", (unsigned int)*(__int16 *)(v178 + 72));
          }
          else
          {
            DefaultLocale = GetDefaultLocale();
            LODWORD(v250) = *((_DWORD *)v157 + 127);
            snwprintf_s_l(
              (wchar_t *const)v157 + 4984,
              0x100u,
              0xFFFFFFFFFFFFFFFFuLL,
              L"Exception 0x%X",
              DefaultLocale,
              v250);
            *((_QWORD *)v157 + 213) = v157 + 9968;
            scierrlog(0x429Du, L"SQLServerLogMgr::LogWriter", v157 + 9968);
          }
          v175 = *((_DWORD *)v157 + 124);
        }
        v180 = *((_QWORD *)v157 + 14);
        if ( v180 )
        {
          if ( !*(_DWORD *)(v180 + 36) )
          {
            if ( *((_DWORD *)v157 + 128) != 1 )
              v175 = (unsigned __int16)v175;
            *(_DWORD *)(v180 + 36) = v175;
          }
          SQLServerLogMgr::IoErrorLC(*(SQLServerLogMgr **)(v180 + 16), (struct IOMesg *)v180);
        }
        *((_DWORD *)v157 + 151) = 88;
        v181 = NtCurrentTeb()->ThreadLocalStoragePointer;
        *((_QWORD *)v157 + 214) = v181;
        v182 = v181[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        *((_QWORD *)v157 + 215) = v182;
        v183 = *(_QWORD *)(v182 + 256);
        *((_QWORD *)v157 + 112) = v183;
        if ( !v183 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v183 = *(_QWORD *)(v182 + 256);
          *((_QWORD *)v157 + 112) = v183;
        }
        v184 = *(_QWORD *)(v183 + 608);
        *((_QWORD *)v157 + 216) = v184;
        v185 = SOS_Scheduler::EnqueueTask(v184, SQLServerLogMgr::LogWriter, 0, 2, v157 + 904);
        *((_DWORD *)v157 + 152) = v185;
        if ( v185 )
        {
          scierrlog(0x42E0u, L"log writer");
          if ( g_shouldInlineLogIo )
            SQLExit(185, 17120, v185, 1);
          else
            SQLExit(186);
        }
        else
        {
          v186 = *((_QWORD *)v157 + 113) + 16LL;
          *((_QWORD *)v157 + 114) = v186;
          v187 = _InterlockedDecrement((volatile signed __int32 *)(v186 + 24));
          *((_DWORD *)v157 + 153) = v187;
          *((_DWORD *)v157 + 154) = v187;
          if ( !v187 )
          {
            v188 = *((_QWORD *)v157 + 114);
            if ( *(_QWORD *)(v188 + 8) )
            {
              TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(v188);
            }
            else
            {
              v189 = (_DWORD *)(v188 - 16);
              *((_QWORD *)v157 + 23) = v189;
              v189 += 46;
              *((_QWORD *)v157 + 217) = v189;
              if ( *v189 == 2 )
              {
                v190 = *(_QWORD *)(*((_QWORD *)v157 + 23) + 160LL);
                *((_QWORD *)v157 + 218) = v190;
                v190 += 4952;
                *((_QWORD *)v157 + 43) = v190;
                *((_DWORD *)v157 + 88) = 0;
                *((_QWORD *)v157 + 219) = v190;
                *((_QWORD *)v157 + 220) = 0;
                *((_QWORD *)v157 + 221) = 0;
                *((_QWORD *)v157 + 33) = 0;
                *((_QWORD *)v157 + 35) = 0;
                *((_QWORD *)v157 + 36) = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
                *((_DWORD *)v157 + 155) = 256;
                v191 = (_DWORD *)*((_QWORD *)v157 + 43);
                *((_QWORD *)v157 + 222) = v191;
                if ( *v191 )
                {
                  v193 = 0;
                }
                else
                {
                  v192 = _InterlockedCompareExchange64(
                           *((volatile signed __int64 **)v157 + 43),
                           *((_QWORD *)v157 + 36),
                           0);
                  *((_QWORD *)v157 + 223) = v192;
                  *((_QWORD *)v157 + 224) = v192;
                  v193 = v192 == 0;
                }
                *((_DWORD *)v157 + 156) = v193;
                if ( !v193 )
                {
                  v194 = SOS_PublicGlobals::sm_osStats;
                  if ( (SOS_PublicGlobals::sm_osStats & 0x80u) != 0 && (v194 & 4) != 0 )
                  {
                    *((_QWORD *)v157 + 61) = 0;
                    *((_DWORD *)v157 + 248) = 88;
                    v195 = NtCurrentTeb()->ThreadLocalStoragePointer;
                    *((_QWORD *)v157 + 225) = v195;
                    v101 = v195[SystemThread_TlsIndex] + SystemThread_TlsOffset == 0;
                    v196 = v195[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                    *((_QWORD *)v157 + 226) = v196;
                    if ( !v101 && *(_QWORD *)(v196 + 272) == v196 )
                    {
                      v198 = *(_QWORD *)(v196 + 256);
                      *((_QWORD *)v157 + 61) = v198;
                    }
                    else
                    {
                      v198 = *((_QWORD *)v157 + 61);
                    }
                  }
                  else
                  {
                    v198 = 0;
                  }
                  *((_QWORD *)v157 + 35) = v198;
                  if ( v198 )
                  {
                    *((_QWORD *)v157 + 227) = v157 + 376;
                    *((_DWORD *)v157 + 214) = Base_PublicGlobals::sm_invariantTscAvailable;
                    if ( Base_PublicGlobals::sm_invariantTscAvailable )
                    {
                      *((_DWORD *)v157 + 176) = QueryPerformanceCounter((LARGE_INTEGER *)v157 + 115);
                      v199 = (DirtyPageMgr *)*((_QWORD *)v157 + 115);
                      *((_QWORD *)v157 + 47) = v199;
                    }
                    else
                    {
                      v199 = MEMORY[0x7FFE0008];
                      *((_QWORD *)v157 + 228) = MEMORY[0x7FFE0008];
                      *((_QWORD *)v157 + 47) = v199;
                      v198 = *((_QWORD *)v157 + 35);
                    }
                    *((_QWORD *)v157 + 229) = v199;
                    *((_QWORD *)v157 + 33) = v199;
                  }
                  *((_DWORD *)v157 + 238) = 2;
                  v200 = *((_QWORD *)v157 + 43);
                  if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
                    Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v200, *((_QWORD *)v157 + 36));
                  else
                    Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v200, v198, *((_QWORD *)v157 + 36));
                  if ( v198 )
                  {
                    *((_QWORD *)v157 + 230) = v157 + 272;
                    *((_DWORD *)v157 + 211) = Base_PublicGlobals::sm_invariantTscAvailable;
                    if ( Base_PublicGlobals::sm_invariantTscAvailable )
                    {
                      *((_DWORD *)v157 + 210) = QueryPerformanceCounter((LARGE_INTEGER *)v157 + 116);
                      v201 = (DirtyPageMgr *)*((_QWORD *)v157 + 116);
                      *((_QWORD *)v157 + 34) = v201;
                    }
                    else
                    {
                      v201 = MEMORY[0x7FFE0008];
                      *((_QWORD *)v157 + 231) = MEMORY[0x7FFE0008];
                      *((_QWORD *)v157 + 34) = v201;
                      v198 = *((_QWORD *)v157 + 35);
                    }
                    *((_QWORD *)v157 + 232) = v157 + 264;
                    *((_QWORD *)v157 + 233) = v157 + 272;
                    v202 = *((_QWORD *)v157 + 33);
                    if ( (unsigned __int64)v201 < v202 )
                    {
                      v203 = 0;
                      *((_QWORD *)v157 + 11) = 0;
                    }
                    else
                    {
                      v203 = (char *)v201 - v202;
                      *((_QWORD *)v157 + 11) = v203;
                    }
                    *((_QWORD *)v157 + 54) = v203;
                    *((_QWORD *)v157 + 234) = v203;
                    *((_QWORD *)v157 + 235) = v198 + 3192;
                    *(_QWORD *)(v198 + 3192) += v203;
                  }
                }
                *((_DWORD *)v157 + 88) = 1;
                v204 = (__int64 *)*((_QWORD *)v157 + 23);
                v205 = (_QWORD *)v204[1];
                *((_QWORD *)v157 + 236) = v205;
                v206 = *v204;
                *((_QWORD *)v157 + 237) = *v204;
                *(_QWORD *)(v206 + 8) = v205;
                *v205 = v206;
                v204[1] = 0;
                *v204 = 0;
                SpinlockHolder<11,2,268435714>::~SpinlockHolder<11,2,268435714>(v157 + 344);
              }
              *((_QWORD *)v157 + 48) = 0;
              *((_DWORD *)v157 + 159) = 88;
              v207 = NtCurrentTeb()->ThreadLocalStoragePointer;
              *((_QWORD *)v157 + 238) = v207;
              v101 = v207[SystemThread_TlsIndex] + SystemThread_TlsOffset == 0;
              v208 = v207[SystemThread_TlsIndex] + SystemThread_TlsOffset;
              *((_QWORD *)v157 + 239) = v208;
              if ( !v101 && *(_QWORD *)(v208 + 272) == v208 )
              {
                v210 = *(_QWORD *)(v208 + 256);
                *((_QWORD *)v157 + 48) = v210;
              }
              else
              {
                v210 = *((_QWORD *)v157 + 48);
              }
              *((_QWORD *)v157 + 240) = v210;
              v211 = *((_QWORD *)v157 + 23);
              if ( v210 && *(_QWORD *)(v210 + 528) == v211 )
              {
                if ( v211 )
                  v212 = (ISOSHost_TaskImpl *)(v211 - 8);
                else
                  v212 = 0;
                ISOSHost_TaskImpl::`scalar deleting destructor'(v212, 0);
              }
              else
              {
                v213 = *(SOS_Node **)(v211 + 168);
                if ( v213 && *((_QWORD *)v213 + 30) && !SOS_Node::IsTaskStoreDisabled(v213) )
                {
                  v214 = *(_QWORD *)(*(_QWORD *)(v211 + 168) + 240LL);
                  *((_QWORD *)v157 + 241) = v214;
                  v215 = (ISOSHost_TaskImpl *)(v211 - 8);
                  ISOSHost_TaskImpl::`scalar deleting destructor'(v215, 0);
                  *((_QWORD *)v157 + 26) = v215;
                  v216 = *(_QWORD *)(v214 + 2016);
                  *((_QWORD *)v157 + 54) = v216;
                  v217 = (_QWORD *)(v216 + 40);
                  *((_QWORD *)v157 + 24) = v216 + 40;
                  *((_QWORD *)v157 + 242) = 0;
                  *((_QWORD *)v157 + 243) = 0;
                  *((_QWORD *)v157 + 27) = 0;
                  *((_QWORD *)v157 + 30) = 0;
                  *((_QWORD *)v157 + 31) = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
                  *((_DWORD *)v157 + 204) = 256;
                  v218 = (_DWORD *)*((_QWORD *)v157 + 24);
                  *((_QWORD *)v157 + 244) = v218;
                  if ( *v218 )
                  {
                    v220 = 0;
                  }
                  else
                  {
                    v219 = _InterlockedCompareExchange64(
                             *((volatile signed __int64 **)v157 + 24),
                             *((_QWORD *)v157 + 31),
                             0);
                    *((_QWORD *)v157 + 245) = v219;
                    *((_QWORD *)v157 + 246) = v219;
                    v220 = v219 == 0;
                  }
                  *((_DWORD *)v157 + 167) = v220;
                  if ( !v220 )
                  {
                    v221 = SOS_PublicGlobals::sm_osStats;
                    if ( (SOS_PublicGlobals::sm_osStats & 0x80u) != 0 && (v221 & 4) != 0 )
                    {
                      *((_QWORD *)v157 + 49) = 0;
                      *((_DWORD *)v157 + 166) = 88;
                      v222 = NtCurrentTeb()->ThreadLocalStoragePointer;
                      *((_QWORD *)v157 + 247) = v222;
                      v101 = v222[SystemThread_TlsIndex] + SystemThread_TlsOffset == 0;
                      v223 = v222[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                      *((_QWORD *)v157 + 248) = v223;
                      if ( !v101 && *(_QWORD *)(v223 + 272) == v223 )
                      {
                        v225 = *(_QWORD *)(v223 + 256);
                        *((_QWORD *)v157 + 49) = v225;
                      }
                      else
                      {
                        v225 = *((_QWORD *)v157 + 49);
                      }
                    }
                    else
                    {
                      v225 = 0;
                    }
                    *((_QWORD *)v157 + 30) = v225;
                    if ( v225 )
                    {
                      *((_QWORD *)v157 + 249) = v157 + 400;
                      *((_DWORD *)v157 + 165) = Base_PublicGlobals::sm_invariantTscAvailable;
                      if ( Base_PublicGlobals::sm_invariantTscAvailable )
                      {
                        *((_DWORD *)v157 + 164) = QueryPerformanceCounter((LARGE_INTEGER *)v157 + 117);
                        v226 = (DirtyPageMgr *)*((_QWORD *)v157 + 117);
                        *((_QWORD *)v157 + 50) = v226;
                      }
                      else
                      {
                        v226 = MEMORY[0x7FFE0008];
                        *((_QWORD *)v157 + 250) = MEMORY[0x7FFE0008];
                        *((_QWORD *)v157 + 50) = v226;
                        v225 = *((_QWORD *)v157 + 30);
                      }
                      *((_QWORD *)v157 + 251) = v226;
                      *((_QWORD *)v157 + 27) = v226;
                    }
                    *((_DWORD *)v157 + 163) = 2;
                    v227 = *((_QWORD *)v157 + 24);
                    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
                      Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v227, *((_QWORD *)v157 + 31));
                    else
                      Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v227, v225, *((_QWORD *)v157 + 31));
                    if ( v225 )
                    {
                      *((_QWORD *)v157 + 252) = v157 + 224;
                      *((_DWORD *)v157 + 162) = Base_PublicGlobals::sm_invariantTscAvailable;
                      if ( Base_PublicGlobals::sm_invariantTscAvailable )
                      {
                        *((_DWORD *)v157 + 160) = QueryPerformanceCounter((LARGE_INTEGER *)v157 + 118);
                        v228 = (DirtyPageMgr *)*((_QWORD *)v157 + 118);
                        *((_QWORD *)v157 + 28) = v228;
                      }
                      else
                      {
                        v228 = MEMORY[0x7FFE0008];
                        *((_QWORD *)v157 + 253) = MEMORY[0x7FFE0008];
                        *((_QWORD *)v157 + 28) = v228;
                        v225 = *((_QWORD *)v157 + 30);
                      }
                      *((_QWORD *)v157 + 254) = v157 + 216;
                      *((_QWORD *)v157 + 255) = v157 + 224;
                      v229 = *((_QWORD *)v157 + 27);
                      if ( (unsigned __int64)v228 < v229 )
                      {
                        v230 = 0;
                        *((_QWORD *)v157 + 11) = 0;
                      }
                      else
                      {
                        v230 = (char *)v228 - v229;
                        *((_QWORD *)v157 + 11) = v230;
                      }
                      *((_QWORD *)v157 + 11) = v230;
                      *((_QWORD *)v157 + 256) = v230;
                      *((_QWORD *)v157 + 257) = v225 + 3192;
                      *(_QWORD *)(v225 + 3192) += v230;
                    }
                  }
                  v231 = *((_QWORD *)v157 + 54);
                  if ( *(_QWORD *)(v231 + 8) >= *(_QWORD *)v231 )
                  {
                    *((_QWORD *)v157 + 123) = v217;
                    v157[126] = (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
                    if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                    {
                      v247 = rand();
                      if ( v247 == 5 * (v247 / 5) )
                        Spinlock<34,1,268435714>::UpdateStatSnapshot();
                    }
                    *((_QWORD *)v157 + 123) = v217;
                    *v217 = 0;
                    (*(void (__fastcall **)(_QWORD))(v231 + 48))(*((_QWORD *)v157 + 26));
                  }
                  else
                  {
                    if ( *(_BYTE *)(*(_QWORD *)(v231 + 32) + 5820LL) )
                    {
                      v232 = *(_DWORD *)(v231 + 1176) & 0x3F;
                      *((_QWORD *)v157 + 258) = v232;
                      v233 = (_QWORD *)(v231 + 16 * (v232 + 9));
                      *((_QWORD *)v157 + 259) = v233;
                      v234 = (_QWORD *)*((_QWORD *)v157 + 26);
                      *v234 = *v233;
                      if ( !*v233 )
                        v233[1] = v234;
                      *v233 = v234;
                      ++*(_QWORD *)(v231 + 1176);
                      VirtualProtect(v234, 0x1000u, 1u, (PDWORD)v157 + 158);
                    }
                    else
                    {
                      v235 = (_QWORD *)(v231 + 128);
                      *((_QWORD *)v157 + 260) = v231 + 128;
                      v234 = (_QWORD *)*((_QWORD *)v157 + 26);
                      *v234 = *(_QWORD *)(v231 + 128);
                      if ( !*(_QWORD *)(v231 + 128) )
                        v235[1] = v234;
                      *v235 = v234;
                    }
                    v236 = *(_QWORD *)(v231 + 1168) + 1LL;
                    *((_QWORD *)v157 + 121) = v236;
                    ++*(_QWORD *)(v231 + 8);
                    v237 = *(SOS_ObjectStore **)(v231 + 32);
                    if ( !*((_BYTE *)v237 + 5820) && v236 >= 0x20 )
                    {
                      PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v237, (struct SList *)v234);
                      v239 = PoolIdForObject;
                      *((_DWORD *)v157 + 157) = PoolIdForObject;
                      v240 = (_QWORD *)(v231 + 128);
                      *((_QWORD *)v157 + 261) = v231 + 128;
                      v241 = (_QWORD *)(v231 + 8 * (PoolIdForObject + 148LL));
                      *((_QWORD *)v157 + 262) = v241;
                      v242 = *(_QWORD *)(v231 + 128);
                      *((_QWORD *)v157 + 263) = v242;
                      v243 = *(_QWORD **)(v231 + 136);
                      if ( v243 == (_QWORD *)(v231 + 128) )
                      {
                        *((_QWORD *)v157 + 120) = 0;
                      }
                      else
                      {
                        *((_QWORD *)v157 + 120) = v243;
                        if ( v243 )
                        {
                          *v243 = *v241;
                          *v241 = v242;
                        }
                      }
                      *v240 = 0;
                      v240[1] = v240;
                      v236 = 0;
                      *((_QWORD *)v157 + 121) = 0;
                      v244 = 1LL << v239;
                      *((_QWORD *)v157 + 264) = 1LL << v239;
                      v245 = *(_QWORD *)(v231 + 1696);
                      if ( (v245 & (1LL << v239)) == 0 )
                        *(_QWORD *)(v231 + 1696) = v244 | v245;
                    }
                    *(_QWORD *)(v231 + 1168) = v236;
                    *((_QWORD *)v157 + 122) = v217;
                    v157[125] = (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
                    if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                    {
                      v246 = rand();
                      if ( v246 == 5 * (v246 / 5) )
                        Spinlock<34,1,268435714>::UpdateStatSnapshot();
                    }
                    *((_QWORD *)v157 + 122) = v217;
                    *v217 = 0;
                  }
                }
                else
                {
                  v248 = (void *)(v211 - 8);
                  if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
                  {
                    VirtualFree(v248, 0, 0x8000u);
                  }
                  else if ( v248 )
                  {
                    ISOSHost_TaskImpl::`scalar deleting destructor'((ISOSHost_TaskImpl *)v248, 1u);
                  }
                }
              }
            }
          }
        }
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)(v157 + 2144));
      }
      catch ( ShortStackException )
      {
      }
      v151 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v152 = *(struct Worker **)(v151 + 256);
      if ( !v152 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v152 = *(struct Worker **)(v151 + 256);
      }
      if ( *((_DWORD *)v152 + 139) )
        ExceptionPostCatchActions(v152);
      if ( a62 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a62 + 16LL))(a62, 0);
      if ( a62 )
        (**(void (__fastcall ***)(__int64, __int64))a62)(a62, 1);
      ExcHandler::~ExcHandler((ExcHandler *)&STACK[0x3E48]);
    }
  }
  catch ( SQLError v483 )
  {
    v249 = v251;
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)(v249 + 2160), (const struct SQLError *)(v249 + 3840));
      scierrlog(0x42E0u, L"log writer");
      SQLExit(187);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)(v249 + 2160));
    }
    catch ( ShortStackException )
    {
    }
  }
  v155 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v156 = *(struct Worker **)(v155 + 256);
  if ( !v156 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v156 = *(struct Worker **)(v155 + 256);
  }
  if ( *((_DWORD *)v156 + 139) )
    ExceptionPostCatchActions(v156);
}

```

## disassembly

```asm
0x101c601a0  push    r13
0x101c601a2  push    r14
0x101c601a4  push    r15
0x101c601a6  mov     eax, 2F30h
0x101c601ab  call    _alloca_probe
0x101c601b0  sub     rsp, rax
0x101c601b3  mov     [rsp+2F48h+var_2700], 0FFFFFFFFFFFFFFFEh
0x101c601bf  mov     [rsp+2F48h+arg_0], rbx
0x101c601c7  mov     [rsp+2F48h+arg_8], rsi
0x101c601cf  mov     [rsp+2F48h+arg_10], rdi
0x101c601d7  mov     [rsp+2F48h+arg_18], r12
0x101c601df  mov     rax, cs:__security_cookie
0x101c601e6  xor     rax, rsp
0x101c601e9  mov     [rsp+2F48h+var_20], rax
0x101c601f1  xor     r13d, r13d
0x101c601f4  mov     [rsp+2F48h+var_2ED8], r13
0x101c601f9  mov     [rsp+2F48h+var_2EC0], 8
0x101c60204  mov     [rsp+2F48h+var_2EBC], r13d
0x101c6020c  xor     edx, edx; unsigned __int16
0x101c6020e  mov     [rsp+2F48h+var_2F20], r13; struct Worker *
0x101c60213  lea     rbx, ?HandleAndNoteToErrorlog@@YAHHHHHPEAD@Z; HandleAndNoteToErrorlog(int,int,int,int,char *)
0x101c6021a  mov     [rsp+2F48h+var_2F28], rbx; int (*)(int, int, int, int, char *)
0x101c6021f  xor     r9d, r9d; unsigned __int8
0x101c60222  xor     r8d, r8d; unsigned __int8
0x101c60225  lea     rcx, [rsp+2F48h+var_2030]; this
0x101c6022d  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x101c60232  nop
0x101c60233  mov     [rsp+2F48h+var_2D40], r13
0x101c6023b  mov     [rsp+2F48h+var_2D38], r13d
0x101c60243  mov     eax, 2Dh ; '-'
0x101c60248  mov     [rsp+2F48h+var_2D34], ax
0x101c60250  lea     rax, aLogwriterTask; "Logwriter Task"
0x101c60257  mov     [rsp+2F48h+var_2D30], rax
0x101c6025f  xor     r8d, r8d
0x101c60262  xor     edx, edx
0x101c60264  lea     rcx, [rsp+2F48h+var_2D40]
0x101c6026c  call    ?Setup@CAutoSetupExecContextsForInternalTasks@@QEAAXW4EStartupErrorHandling@1@PEAVXactWorkspace@@@Z; CAutoSetupExecContextsForInternalTasks::Setup(CAutoSetupExecContextsForInternalTasks::EStartupErrorHandling,XactWorkspace *)
0x101c60271  nop
0x101c60272  xor     edx, edx; unsigned __int16
0x101c60274  mov     [rsp+2F48h+var_2F20], r13; struct Worker *
0x101c60279  mov     [rsp+2F48h+var_2F28], rbx; int (*)(int, int, int, int, char *)
0x101c6027e  xor     r9d, r9d; unsigned __int8
0x101c60281  xor     r8d, r8d; unsigned __int8
0x101c60284  lea     rcx, [rsp+2F48h+var_1888]; this
0x101c6028c  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x101c60291  nop
0x101c60292  movzx   eax, cs:byte_10317AF70
0x101c60299  mov     [rsp+2F48h+var_2ED0], al
0x101c6029d  test    al, 1
0x101c6029f  jnz     loc_101C6055D
0x101c602a5  mov     [rsp+2F48h+var_2EB0], r13d
0x101c602ad  mov     r8, gs:58h
0x101c602b6  mov     [rsp+2F48h+var_26F8], r8
0x101c602be  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101c602c5  mov     ecx, [rax]
0x101c602c7  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101c602ce  mov     edx, [rax]
0x101c602d0  add     rdx, [r8+rcx*8]
0x101c602d4  mov     [rsp+2F48h+var_26F0], rdx
0x101c602dc  mov     rax, [rdx]
0x101c602df  mov     [rsp+2F48h+var_26C8], rax
0x101c602e7  test    rax, rax
0x101c602ea  jnz     loc_101C6052D
0x101c602f0  jmp     short loc_101C602F3
0x101c602f3  mov     eax, [rsp+2F48h+var_2EB0]
0x101c602fa  jmp     short loc_101C602FD
0x101c602fd  test    eax, eax
0x101c602ff  jnz     loc_101C6055D
0x101c60305  mov     edi, 1
0x101c6030a  mov     [rsp+2F48h+pDisablePriorityBoost], edi
0x101c6030e  mov     [rsp+2F48h+pDisablePriorityBoost], r13d
0x101c60313  jmp     short loc_101C60316
0x101c60316  mov     [rsp+2F48h+var_2D80], r13
0x101c6031e  mov     eax, gs:48h
0x101c60326  mov     ecx, eax
0x101c60328  mov     [rsp+2F48h+var_2DD8], rcx
0x101c60330  mov     eax, dword ptr cs:qword_103172600
0x101c60336  test    eax, eax
0x101c60338  jnz     loc_101C605BC
0x101c6033e  mov     rcx, [rsp+2F48h+var_2DD8]
0x101c60346  xor     eax, eax
0x101c60348  lock cmpxchg cs:qword_103172600, rcx
0x101c60351  mov     [rsp+2F48h+var_26B8], rax
0x101c60359  mov     ecx, r13d
0x101c6035c  test    rax, rax
0x101c6035f  setz    cl
0x101c60362  jmp     short loc_101C60365
0x101c60365  mov     [rsp+2F48h+var_2B64], ecx
0x101c6036c  test    ecx, ecx
0x101c6036e  jnz     loc_101C604EA
0x101c60374  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x101c6037b  mov     ecx, [rax]
0x101c6037d  test    cl, cl
0x101c6037f  jns     loc_101C60602
0x101c60385  test    cl, 4
0x101c60388  jz      loc_101C60602
0x101c6038e  mov     [rsp+2F48h+var_2D88], r13
0x101c60396  mov     rdx, gs:58h
0x101c6039f  mov     [rsp+2F48h+var_2B30], rdx
0x101c603a7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101c603ae  mov     ecx, [rax]
0x101c603b0  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101c603b7  mov     ebx, [rax]
0x101c603b9  add     rbx, [rdx+rcx*8]
0x101c603bd  mov     [rsp+2F48h+var_2B28], rbx
0x101c603c5  jz      loc_101C605C5
0x101c603cb  cmp     [rbx+110h], rbx
0x101c603d2  jnz     loc_101C605C5
0x101c603d8  mov     eax, edi
0x101c603da  jmp     short loc_101C603DD
0x101c603dd  test    eax, eax
0x101c603df  jz      loc_101C605CE
0x101c603e5  mov     rbx, [rbx+100h]
0x101c603ec  mov     [rsp+2F48h+var_2D88], rbx
0x101c603f4  jmp     short loc_101C603F7
0x101c603f7  mov     [rsp+2F48h+var_2E60], rbx
0x101c603ff  test    rbx, rbx
0x101c60402  jz      short loc_101C60448
0x101c60404  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x101c6040b  mov     ecx, [rax]
0x101c6040d  mov     [rsp+2F48h+var_2B60], ecx
0x101c60414  test    ecx, ecx
0x101c60416  jz      loc_101C605DC
0x101c6041c  lea     rcx, [rsp+2F48h+var_2CA8]; lpPerformanceCount
0x101c60424  call    cs:__imp_QueryPerformanceCounter
0x101c6042a  mov     rax, qword ptr [rsp+2F48h+var_2CA8]
0x101c60432  mov     [rsp+2F48h+var_2CA0], rax
0x101c6043a  jmp     short loc_101C6043D
0x101c6043d  mov     [rsp+2F48h+var_2D80], rax
0x101c60445  jmp     short loc_101C60448
0x101c60448  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x101c6044f  lea     rcx, qword_103172600
0x101c60456  cmp     byte ptr [rax+0C7h], 0
0x101c6045d  jge     loc_101C60613
0x101c60463  mov     r8, [rsp+2F48h+var_2DD8]
0x101c6046b  mov     rdx, rbx
0x101c6046e  call    ?SpinToAcquireOptimistic@?$Spinlock@$0HO@$0N@$0BAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<126,13,258>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x101c60473  jmp     short loc_101C60476
0x101c60476  test    rbx, rbx
0x101c60479  jz      short loc_101C604EA
0x101c6047b  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x101c60482  mov     ecx, [rax]
0x101c60484  mov     [rsp+2F48h+var_2D28], ecx
0x101c6048b  test    ecx, ecx
0x101c6048d  jz      loc_101C60627
0x101c60493  lea     rcx, [rsp+2F48h+var_2C98]; lpPerformanceCount
0x101c6049b  call    cs:__imp_QueryPerformanceCounter
0x101c604a1  mov     rax, qword ptr [rsp+2F48h+var_2C98]
0x101c604a9  mov     [rsp+2F48h+var_2C90], rax
0x101c604b1  jmp     short loc_101C604B4
0x101c604b4  mov     rcx, [rsp+2F48h+var_2D80]
0x101c604bc  cmp     rax, rcx
0x101c604bf  jb      loc_101C6064D
0x101c604c5  sub     rax, rcx
0x101c604c8  mov     [rsp+2F48h+var_2EB8], rax
0x101c604d0  jmp     short loc_101C604D3
0x101c604d3  mov     [rsp+2F48h+var_2EF0], rax
0x101c604d8  lea     rcx, [rbx+0C78h]
0x101c604df  mov     [rsp+2F48h+var_2B10], rcx
0x101c604e7  add     [rcx], rax
0x101c604ea  mov     [rsp+2F48h+var_2EC4], r13d
0x101c604f2  mov     eax, r13d
0x101c604f5  mov     [rsp+2F48h+var_2EC4], eax
0x101c604fc  lea     rsi, __@@_PchSym_@00@UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq@4B2008FD98C1DD4
0x101c60503  mov     ecx, cs:?sm_totalLogWriters@SQLServerLogMgr@@2KA; ulong SQLServerLogMgr::sm_totalLogWriters
0x101c60509  mov     ebx, eax
0x101c6050b  cmp     eax, ecx
0x101c6050d  jnb     loc_1004014AD
0x101c60513  cmp     rva ?sm_logWriTid@SQLServerLogMgr@@2PAKA[rsi+rbx*4], 0; ulong near * SQLServerLogMgr::sm_logWriTid ...
0x101c6051b  jz      loc_1004014CE
0x101c60521  inc     eax
0x101c60523  mov     [rsp+2F48h+var_2EC4], eax
0x101c6052a  jmp     short loc_101C60509
0x101c6052d  mov     rax, [rax+38h]
0x101c60531  mov     rcx, [rax]
0x101c60534  mov     [rsp+2F48h+var_26C0], rcx
0x101c6053c  test    rcx, rcx
0x101c6053f  jz      loc_101C602F3
0x101c60545  mov     edx, 1F80h
0x101c6054a  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x101c60550  mov     [rsp+2F48h+var_2EB0], eax
0x101c60557  jmp     loc_101C602FD
0x101c6055d  mov     edi, 1
0x101c60562  mov     [rsp+2F48h+pDisablePriorityBoost], edi
0x101c60566  call    cs:__imp_GetCurrentProcess
0x101c6056c  mov     rcx, rax; hProcess
0x101c6056f  lea     rdx, [rsp+2F48h+pDisablePriorityBoost]; pDisablePriorityBoost
0x101c60574  call    cs:__imp_GetProcessPriorityBoost
0x101c6057a  cmp     [rsp+2F48h+pDisablePriorityBoost], 0
0x101c6057f  jz      loc_101C60316
0x101c60585  call    cs:__imp_GetCurrentThread
0x101c6058b  mov     rcx, rax; hThread
0x101c6058e  lea     rdx, [rsp+2F48h+pDisablePriorityBoost]; pDisablePriorityBoost
0x101c60593  call    cs:__imp_GetThreadPriorityBoost
0x101c60599  cmp     [rsp+2F48h+pDisablePriorityBoost], 0
0x101c6059e  jz      loc_101C60316
0x101c605a4  call    cs:__imp_GetCurrentThread
0x101c605aa  mov     rcx, rax; hThread
0x101c605ad  xor     edx, edx; bDisablePriorityBoost
0x101c605af  call    cs:__imp_SetThreadPriorityBoost
0x101c605b5  nop
0x101c605b6  jmp     loc_101C60316
0x101c605bc  mov     ecx, r13d
0x101c605bf  jmp     loc_101C60365
0x101c605c5  mov     eax, r13d
0x101c605c8  jmp     loc_101C603DD
0x101c605ce  mov     rbx, [rsp+2F48h+var_2D88]
0x101c605d6  jmp     loc_101C603F7
0x101c605dc  mov     rax, ds:7FFE0008h
0x101c605e4  mov     [rsp+2F48h+var_2B20], rax
0x101c605ec  mov     [rsp+2F48h+var_2CA0], rax
0x101c605f4  mov     rbx, [rsp+2F48h+var_2E60]
0x101c605fc  jmp     loc_101C6043D
0x101c60602  mov     rbx, r13
0x101c60605  mov     [rsp+2F48h+var_2E60], rbx
0x101c6060d  jmp     loc_101C60448
0x101c60613  mov     rdx, [rsp+2F48h+var_2DD8]
0x101c6061b  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0HO@$0N@$0BAC@@@AEAAX_K@Z; Spinlock<126,13,258>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x101c60620  nop
0x101c60621  jmp     loc_101C60476
0x101c60627  mov     rax, ds:7FFE0008h
0x101c6062f  mov     [rsp+2F48h+var_2B18], rax
0x101c60637  mov     [rsp+2F48h+var_2C90], rax
0x101c6063f  mov     rbx, [rsp+2F48h+var_2E60]
0x101c60647  jmp     loc_101C604B4
0x101c6064d  mov     rax, r13
0x101c60650  mov     [rsp+2F48h+var_2EB8], rax
0x101c60658  jmp     loc_101C604D3
0x101c6065e  mov     rcx, rax
0x101c60661  jmp     loc_1004015E1
0x101c60667  xor     ecx, ecx
0x101c60669  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101c6066f  mov     rbx, [rdi+100h]
0x101c60676  mov     [rsp+2F48h+var_2C70], rbx
0x101c6067e  jmp     loc_1004016D0
0x101c60684  mov     [rsp+2F48h+var_2AB8], rcx
0x101c6068c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x101c60692  mov     [rbx+1F0h], r13
0x101c60699  jmp     loc_1004016E0
0x101c6069f  mov     [rsp+2F48h+var_2B58], 400154h
0x101c606aa  mov     [rsp+2F48h+var_2B50], r13
0x101c606b2  mov     [rsp+2F48h+var_2B40], r13
0x101c606ba  mov     [rsp+2F48h+var_2B48], r13
0x101c606c2  mov     [rsp+2F48h+var_2B38], r13
0x101c606ca  lea     rdx, [rsp+2F48h+var_2B58]
0x101c606d2  mov     ecx, 3E8h
0x101c606d7  call    ?Sleep@SOS_Task@@SA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z; SOS_Task::Sleep(ulong,SOS_WaitInfo const *)
0x101c606dc  nop
0x101c606dd  mov     rdx, gs:58h
0x101c606e6  mov     [rsp+2F48h+var_2AB0], rdx
0x101c606ee  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101c606f5  mov     ecx, [rax]
0x101c606f7  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101c606fe  mov     ebx, [rax]
0x101c60700  add     rbx, [rdx+rcx*8]
0x101c60704  mov     [rsp+2F48h+var_2AA8], rbx
0x101c6070c  mov     r14, [rbx+100h]
0x101c60713  mov     [rsp+2F48h+var_2C68], r14
0x101c6071b  test    r14, r14
0x101c6071e  jnz     short loc_101C60737
0x101c60720  xor     ecx, ecx
0x101c60722  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101c60728  mov     r14, [rbx+100h]
0x101c6072f  mov     [rsp+2F48h+var_2C68], r14
0x101c60737  mov     r14, [r14+258h]
0x101c6073e  mov     [rsp+2F48h+var_2AA0], r14
0x101c60746  mov     esi, r13d
0x101c60749  mov     [rsp+2F48h+var_2E48], r13d
0x101c60751  cmp     esi, 40h ; '@'
0x101c60754  jnb     short loc_101C607BA
0x101c60756  mov     r15d, esi
0x101c60759  lea     r15, [r15+39h]
0x101c6075d  lea     r15, [r14+r15*8]
0x101c60761  mov     rdi, [r15]
0x101c60764  mov     [rsp+2F48h+var_2A98], rdi
0x101c6076c  test    rdi, rdi
0x101c6076f  jz      short loc_101C607AF
0x101c60771  mov     rax, rdi
0x101c60774  cqo
0x101c60776  and     edx, 1FFFh
0x101c6077c  lea     rbx, [rdx+rax]
0x101c60780  sar     rbx, 0Dh
0x101c60784  mov     ecx, esi
0x101c60786  call    cs:__imp_?GetPool@MemoryPoolManager@@SAPEAVSOS_MemoryPool@@K@Z; MemoryPoolManager::GetPool(ulong)
0x101c6078c  mov     rcx, rax
0x101c6078f  xor     r9d, r9d
0x101c60792  mov     r8d, r12d
0x101c60795  mov     rdx, rbx
0x101c60798  call    cs:__imp_?TransferMemory@SOS_MemoryPool@@QEAAX_JW4MemoryBrokerType@@1@Z; SOS_MemoryPool::TransferMemory(__int64,MemoryBrokerType,MemoryBrokerType)
0x101c6079e  sub     [r14+1B0h], rdi
0x101c607a5  sub     [r15], rdi
0x101c607a8  sub     [r14+1C0h], rdi
0x101c607af  inc     esi
0x101c607b1  mov     [rsp+2F48h+var_2E48], esi
0x101c607b8  jmp     short loc_101C60751
0x101c607ba  mov     rdx, gs:58h
0x101c607c3  mov     [rsp+2F48h+var_2A90], rdx
0x101c607cb  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101c607d2  mov     ecx, [rax]
0x101c607d4  mov     rax, cs:__imp_SystemThread_TlsOffset
  ... truncated ...
```
