# LatchBase::Suspend(ulong,uint,LatchSuspendInfo *,LatchBase::SubLatchInfo *,LatchBase::Releasor)

- ea: `0x1004601d0`
- end: `0x1004608f9`
- name: `?Suspend@LatchBase@@AEAA?AW4AcquireResult@1@KIPEAVLatchSuspendInfo@@PEAUSubLatchInfo@1@W4Releasor@1@@Z`
- size: `1833`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x100402d60`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x100402eb0`
- `0x10040d950`
- `0x1004600d0`
- `0x1004601d0`
- `0x100460900`
- `0x100460930`
- `0x100472800`
- `0x100553e20`
- `0x10064b960`
- `0x10064bb10`
- `0x101874ac0`
- `0x1018764a0`
- `0x101876bb0`
- `0x1018774d0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10046050d`
- `KERNEL32!QueryPerformanceCounter` at `0x10046072b`
- `KERNEL32!QueryPerformanceCounter` at `0x101873953`
- `KERNEL32!QueryPerformanceCounter` at `0x101873c1e`
- `KERNEL32!QueryPerformanceCounter` at `0x101873ed7`
- `KERNEL32!QueryPerformanceCounter` at `0x101874190`
- `KERNEL32!QueryPerformanceCounter` at `0x1018744bf`
- `KERNEL32!QueryPerformanceCounter` at `0x10187471c`
- `KERNEL32!QueryPerformanceCounter` at `0x10187476d`
- `KERNEL32!QueryPerformanceCounter` at `0x1018749f6`
- `KERNEL32!QueryPerformanceCounter` at `0x10046050d`
- `KERNEL32!QueryPerformanceCounter` at `0x10046072b`
- `KERNEL32!QueryPerformanceCounter` at `0x101873953`
- `KERNEL32!QueryPerformanceCounter` at `0x101873c1e`
- `KERNEL32!QueryPerformanceCounter` at `0x101873ed7`
- `KERNEL32!QueryPerformanceCounter` at `0x101874190`
- `KERNEL32!QueryPerformanceCounter` at `0x1018744bf`
- `KERNEL32!QueryPerformanceCounter` at `0x10187471c`
- `KERNEL32!QueryPerformanceCounter` at `0x10187476d`
- `KERNEL32!QueryPerformanceCounter` at `0x1018749f6`
- `sqldk!?DebugBreakUncatchable@SOS_OS@@SAXXZ` at `0x101873de8`
- `sqldk!?DebugBreakUncatchable@SOS_OS@@SAXXZ` at `0x101873de8`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1004b9579`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004604f9`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10046052e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100460717`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100460742`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10187393f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101873c0a`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101873cec`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101873d63`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101873ec3`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101874113`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10187417c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1018742e3`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1018744ab`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1018745cb`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10187470c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10187475d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1018749e6`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101874a6f`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x10046053e`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x100460752`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101873cf8`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101873d6f`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x10187411f`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x1018742f8`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x1018745d7`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101874a7b`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x10046035f`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x1004605e4`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x100460702`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x100460772`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x101873925`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x10187397b`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x101873ea9`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x101873f01`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x101874162`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x1018741b8`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x1004603ad`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x1004603c9`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x1004607c1`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x1004607fe`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x1018739d5`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101873a10`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101873f5a`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101873f95`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101874212`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10187424c`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x10046069d`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x1018746f6`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x10046069d`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x1018746f6`
- `sqldk!?GetImageHelper@@YAAEAVCImageHelper@@XZ` at `0x100460652`
- `sqldk!?GetImageHelper@@YAAEAVCImageHelper@@XZ` at `0x100460652`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018738f5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10187409c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018738f5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10187409c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101874586`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101874586`
- `sqldk!SystemThread_TlsIndex` at `0x1004602b5`
- `sqldk!SystemThread_TlsIndex` at `0x100460309`
- `sqldk!SystemThread_TlsIndex` at `0x100460378`
- `sqldk!SystemThread_TlsIndex` at `0x10046078b`
- `sqldk!SystemThread_TlsIndex` at `0x101873994`
- `sqldk!SystemThread_TlsIndex` at `0x101873f1a`
- `sqldk!SystemThread_TlsIndex` at `0x1018741d1`
- `sqldk!SystemThread_TlsIndex` at `0x101874687`
- `sqldk!SystemThread_TlsIndex` at `0x1018747d7`
- `sqldk!SystemThread_TlsOffset` at `0x1004602be`
- `sqldk!SystemThread_TlsOffset` at `0x100460312`
- `sqldk!SystemThread_TlsOffset` at `0x100460381`
- `sqldk!SystemThread_TlsOffset` at `0x100460794`
- `sqldk!SystemThread_TlsOffset` at `0x10187399d`
- `sqldk!SystemThread_TlsOffset` at `0x101873f23`
- `sqldk!SystemThread_TlsOffset` at `0x1018741da`
- `sqldk!SystemThread_TlsOffset` at `0x101874690`
- `sqldk!SystemThread_TlsOffset` at `0x1018747e0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10187363d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1018737e9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1018739b9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101873f3e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1018741f6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101874661`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1018746ab`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1018747fc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10187363d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1018737e9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1018739b9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101873f3e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1018741f6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101874661`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1018746ab`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1018747fc`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101873804`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101873804`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall LatchBase::Suspend(_QWORD ***a1, unsigned int a2, unsigned int a3, _DWORD *a4, __int64 a5, int a6)
{
  unsigned int v7; // r10d
  unsigned int v8; // r9d
  int v10; // edi
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // r14
  __int64 v14; // rcx
  _DWORD *v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rbx
  _QWORD *ObjectDataImpl; // rax
  char *v20; // rdx
  int v21; // eax
  _QWORD **v22; // rcx
  unsigned __int64 v23; // rdx
  signed __int64 v24; // rtt
  LARGE_INTEGER v25; // rdi
  unsigned int v26; // r15d
  unsigned int v27; // r13d
  unsigned int v28; // ebx
  __int128 v29; // xmm0
  size_t v30; // rdx
  struct CImageHelper *ImageHelper; // rax
  struct LatchWaitInfo *Waiter; // r12
  int v33; // r15d
  signed __int64 v34; // rax
  _QWORD **v35; // rtt
  unsigned __int64 v36; // rdx
  signed __int64 v37; // rtt
  LARGE_INTEGER v38; // rcx
  unsigned __int64 v39; // rbx
  unsigned int v40; // ebx
  __int64 v41; // r14
  __int64 v42; // rax
  __int64 v43; // r10
  _BYTE *v44; // r8
  char *v45; // rdx
  char *v46; // rdx
  __int64 v47; // rcx
  unsigned __int64 v48; // rdx
  unsigned int v49; // ecx
  _QWORD *v51; // rbx
  _QWORD ***v52; // rcx
  _QWORD ***v53; // rcx
  int v54; // r8d
  signed __int64 v55; // rtt
  LARGE_INTEGER v56; // rcx
  _DWORD *v57; // r12
  unsigned __int64 v58; // rdx
  unsigned int v59; // ebx
  __int64 v60; // r14
  __int64 v61; // rax
  __int64 v62; // r10
  _BYTE *v63; // r8
  char *v64; // rdx
  char *v65; // rdx
  unsigned __int64 v66; // rdx
  _QWORD ***v67; // rcx
  _QWORD ***v68; // rcx
  DirtyPageMgr *v69; // rcx
  unsigned __int64 v70; // rcx
  unsigned __int64 v71; // rdx
  unsigned __int64 v72; // rdx
  signed __int64 v73; // rtt
  _QWORD *v74; // rdx
  _QWORD *i; // rcx
  int v76; // r15d
  int v77; // r14d
  int v78; // edx
  __int64 v79; // rbx
  unsigned __int64 v80; // rdx
  signed __int64 v81; // rtt
  LARGE_INTEGER v82; // rcx
  unsigned __int64 v83; // rdx
  unsigned int v84; // r14d
  __int64 v85; // rbx
  __int64 v86; // rax
  __int64 v87; // r10
  _BYTE *v88; // r8
  char *v89; // rdx
  char *v90; // rdx
  __int64 v91; // rcx
  unsigned __int64 v92; // rdx
  unsigned __int64 v93; // rdx
  signed __int64 v94; // rtt
  signed __int64 v95; // rtt
  _QWORD *v96; // rdx
  _QWORD *j; // rcx
  LARGE_INTEGER v98; // rcx
  unsigned __int64 v99; // rdx
  unsigned int v100; // ebx
  __int64 v101; // r14
  __int64 v102; // rax
  __int64 v103; // r10
  _BYTE *v104; // r9
  LockManager *v105; // rcx
  char *v106; // rdx
  char *v107; // rdx
  __int64 v108; // rcx
  unsigned __int64 v109; // r15
  _QWORD ***v110; // rcx
  _QWORD ***v111; // rcx
  unsigned int v112; // r15d
  DirtyPageMgr *v113; // rcx
  unsigned __int64 v114; // rcx
  unsigned __int64 v115; // rax
  __int64 v116; // rbx
  __int64 v117; // r14
  int v118; // eax
  int v119; // ebx
  DirtyPageMgr *QuadPart; // rax
  char *v121; // rbx
  _QWORD *v122; // rax
  DirtyPageMgr *v123; // rcx
  unsigned __int64 v124; // rax
  __int64 v125; // r14
  __int64 v126; // rbx
  int v127; // ecx
  _QWORD ***v128; // rcx
  _QWORD ***v129; // rcx
  unsigned __int64 v130; // rcx
  char v131; // r8
  _QWORD ***v132; // rdx
  __int64 v133; // rdx
  DirtyPageMgr *v134; // rcx
  unsigned __int64 v135; // rcx
  unsigned __int64 v136; // rax
  __int64 v137; // [rsp+20h] [rbp-E0h]
  char v138; // [rsp+40h] [rbp-C0h]
  unsigned int v139; // [rsp+44h] [rbp-BCh]
  __int64 v141; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v142; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v145; // [rsp+70h] [rbp-90h]
  unsigned int v146; // [rsp+88h] [rbp-78h]
  int v147; // [rsp+8Ch] [rbp-74h]
  unsigned int v148; // [rsp+90h] [rbp-70h]
  int v149; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v150; // [rsp+A4h] [rbp-5Ch]
  _BOOL8 v151; // [rsp+B0h] [rbp-50h]
  LARGE_INTEGER v152; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD *v153; // [rsp+C0h] [rbp-40h] BYREF
  int v154; // [rsp+C8h] [rbp-38h]
  void **v155; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v156[3]; // [rsp+D8h] [rbp-28h] BYREF
  int v157; // [rsp+F0h] [rbp-10h]
  int v158; // [rsp+F4h] [rbp-Ch]
  __int64 v159; // [rsp+F8h] [rbp-8h]
  unsigned int v160; // [rsp+100h] [rbp+0h]
  __int64 v161; // [rsp+108h] [rbp+8h]
  int v162; // [rsp+110h] [rbp+10h]
  BOOL v163; // [rsp+120h] [rbp+20h]
  _DWORD *v164; // [rsp+128h] [rbp+28h]
  LARGE_INTEGER PerformanceCount; // [rsp+130h] [rbp+30h] BYREF
  LARGE_INTEGER v166; // [rsp+138h] [rbp+38h] BYREF
  LARGE_INTEGER v167; // [rsp+140h] [rbp+40h] BYREF
  LARGE_INTEGER v168; // [rsp+148h] [rbp+48h] BYREF
  LARGE_INTEGER v169; // [rsp+150h] [rbp+50h] BYREF
  LARGE_INTEGER v170; // [rsp+158h] [rbp+58h] BYREF
  LARGE_INTEGER v171; // [rsp+160h] [rbp+60h] BYREF
  LARGE_INTEGER v172; // [rsp+168h] [rbp+68h] BYREF
  int v173; // [rsp+170h] [rbp+70h]
  __int64 v174; // [rsp+178h] [rbp+78h]
  __int128 v175; // [rsp+180h] [rbp+80h]
  _QWORD ***v176; // [rsp+190h] [rbp+90h]
  __int128 v177; // [rsp+198h] [rbp+98h]
  int v178; // [rsp+1A8h] [rbp+A8h]
  __int64 v179; // [rsp+1B0h] [rbp+B0h]
  unsigned int v180; // [rsp+1B8h] [rbp+B8h] BYREF
  _QWORD ***v181; // [rsp+1C0h] [rbp+C0h]
  __int64 v182; // [rsp+1C8h] [rbp+C8h]
  __int64 v183; // [rsp+1D0h] [rbp+D0h]
  __int64 v184; // [rsp+1D8h] [rbp+D8h]
  __int64 v185; // [rsp+1E0h] [rbp+E0h]
  char v186[8]; // [rsp+1F0h] [rbp+F0h] BYREF
  int v187; // [rsp+1F8h] [rbp+F8h]
  int v188; // [rsp+200h] [rbp+100h]
  _QWORD **v189; // [rsp+208h] [rbp+108h]
  _BYTE *v190; // [rsp+210h] [rbp+110h]
  __int64 v191; // [rsp+218h] [rbp+118h]
  _QWORD *v192; // [rsp+220h] [rbp+120h] BYREF
  __int64 v193; // [rsp+228h] [rbp+128h]
  _BYTE v194[528]; // [rsp+230h] [rbp+130h] BYREF
  __int64 v195; // [rsp+440h] [rbp+340h]
  __int64 v196; // [rsp+448h] [rbp+348h]
  _QWORD ***v197; // [rsp+450h] [rbp+350h] BYREF
  unsigned int v198; // [rsp+458h] [rbp+358h]
  int v199; // [rsp+45Ch] [rbp+35Ch]
  int v200; // [rsp+460h] [rbp+360h]
  int v201; // [rsp+464h] [rbp+364h]
  unsigned int v202; // [rsp+468h] [rbp+368h]
  int v203; // [rsp+46Ch] [rbp+36Ch]
  int v204; // [rsp+470h] [rbp+370h]
  bool v205; // [rsp+474h] [rbp+374h]
  bool v206; // [rsp+475h] [rbp+375h]
  bool v207; // [rsp+476h] [rbp+376h]
  char v208; // [rsp+477h] [rbp+377h]
  unsigned __int64 v209; // [rsp+478h] [rbp+378h]
  int v210; // [rsp+480h] [rbp+380h]
  __int16 v211; // [rsp+484h] [rbp+384h]
  int v212; // [rsp+486h] [rbp+386h]
  unsigned __int64 v213; // [rsp+48Ah] [rbp+38Ah]
  char v214; // [rsp+492h] [rbp+392h]
  char v215[8]; // [rsp+4A0h] [rbp+3A0h] BYREF
  int v216; // [rsp+4A8h] [rbp+3A8h]
  int v217; // [rsp+4B0h] [rbp+3B0h]
  _QWORD *v218; // [rsp+4B8h] [rbp+3B8h]
  char *v219; // [rsp+4C0h] [rbp+3C0h]
  __int64 v220; // [rsp+4C8h] [rbp+3C8h]
  _QWORD v221[2]; // [rsp+4D0h] [rbp+3D0h] BYREF
  char v222; // [rsp+4E0h] [rbp+3E0h] BYREF
  __int64 v223; // [rsp+6F0h] [rbp+5F0h]
  __int64 v224; // [rsp+6F8h] [rbp+5F8h]
  _QWORD ***v225; // [rsp+700h] [rbp+600h] BYREF
  unsigned int v226; // [rsp+708h] [rbp+608h]
  int v227; // [rsp+70Ch] [rbp+60Ch]
  int v228; // [rsp+710h] [rbp+610h]
  int v229; // [rsp+714h] [rbp+614h]
  unsigned int v230; // [rsp+718h] [rbp+618h]
  int v231; // [rsp+71Ch] [rbp+61Ch]
  int v232; // [rsp+720h] [rbp+620h]
  bool v233; // [rsp+724h] [rbp+624h]
  bool v234; // [rsp+725h] [rbp+625h]
  bool v235; // [rsp+726h] [rbp+626h]
  char v236; // [rsp+727h] [rbp+627h]
  unsigned __int64 v237; // [rsp+728h] [rbp+628h]
  int v238; // [rsp+730h] [rbp+630h]
  __int16 v239; // [rsp+734h] [rbp+634h]
  int v240; // [rsp+736h] [rbp+636h]
  __int64 v241; // [rsp+73Ah] [rbp+63Ah]
  char v242; // [rsp+742h] [rbp+642h]
  char v243[8]; // [rsp+750h] [rbp+650h] BYREF
  int v244; // [rsp+758h] [rbp+658h]
  int v245; // [rsp+760h] [rbp+660h]
  _QWORD *v246; // [rsp+768h] [rbp+668h]
  char *v247; // [rsp+770h] [rbp+670h]
  __int64 v248; // [rsp+778h] [rbp+678h]
  _QWORD v249[2]; // [rsp+780h] [rbp+680h] BYREF
  char v250; // [rsp+790h] [rbp+690h] BYREF
  __int64 v251; // [rsp+9A0h] [rbp+8A0h]
  __int64 v252; // [rsp+9A8h] [rbp+8A8h]
  _QWORD ***v253; // [rsp+9B0h] [rbp+8B0h] BYREF
  unsigned int v254; // [rsp+9B8h] [rbp+8B8h]
  int v255; // [rsp+9BCh] [rbp+8BCh]
  int v256; // [rsp+9C0h] [rbp+8C0h]
  int v257; // [rsp+9C4h] [rbp+8C4h]
  unsigned int v258; // [rsp+9C8h] [rbp+8C8h]
  int v259; // [rsp+9CCh] [rbp+8CCh]
  int v260; // [rsp+9D0h] [rbp+8D0h]
  bool v261; // [rsp+9D4h] [rbp+8D4h]
  bool v262; // [rsp+9D5h] [rbp+8D5h]
  bool v263; // [rsp+9D6h] [rbp+8D6h]
  unsigned int v264; // [rsp+9D7h] [rbp+8D7h]
  int v265; // [rsp+9DBh] [rbp+8DBh]
  __int16 v266; // [rsp+9DFh] [rbp+8DFh]
  int v267; // [rsp+9E1h] [rbp+8E1h]
  int v268; // [rsp+9F0h] [rbp+8F0h] BYREF
  _DWORD v269[5]; // [rsp+9F4h] [rbp+8F4h] BYREF
  __int64 v270; // [rsp+A08h] [rbp+908h]
  __int64 v271; // [rsp+B0Ch] [rbp+A0Ch]
  __int128 Src; // [rsp+B28h] [rbp+A28h] BYREF
  _QWORD ***v273; // [rsp+B38h] [rbp+A38h]
  wchar_t v274[264]; // [rsp+B50h] [rbp+A50h] BYREF

  v185 = -2;
  v7 = a3;
  v8 = a2;
  v10 = 67108896;
  v145 = 0;
  v156[1] = v156;
  v156[0] = v156;
  v156[2] = 0;
  v157 = 0;
  v158 = 1;
  v159 = 0;
  v155 = &EventAutoInternal<SuspendQueueSLock>::`vftable';
  v153 = 0;
  v154 = 0;
  v160 = 0;
  v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v12 = *(_QWORD *)(v11 + 256);
  if ( !v12 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v12 = *(_QWORD *)(v11 + 256);
    v8 = a2;
    v7 = a3;
  }
  v161 = *(_QWORD *)(v12 + 600);
  v162 = a6;
  v13 = 0;
  v141 = 0;
  v147 = 0;
  v138 = 0;
  v14 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset
                  + 8LL);
  if ( v14 )
  {
    v15 = *(_DWORD **)(v14 + 48);
    v164 = v15;
    if ( v15 )
    {
      v163 = *v15 == 0;
      *v15 = 1;
      goto LABEL_6;
    }
  }
  else
  {
    v164 = 0;
  }
  v163 = 0;
LABEL_6:
  if ( (dword_10317F6C8 & 0x1000) == 0 )
    goto LABEL_7;
  v244 = 0x10000;
  v245 = 0;
  v246 = v249;
  v247 = &v250;
  v251 = 0;
  v248 = 0;
  v252 = 0;
  v249[0] = &v253;
  v249[1] = 53;
  v253 = a1;
  v255 = (_DWORD)a1[3] & 0x3FFFFFFF;
  v256 = (unsigned __int64)a1[2] >> 36;
  v257 = ((unsigned __int64)a1[2] >> 12) & 0xFFFFFF;
  v258 = (unsigned int)a1[2] & 1;
  v259 = ((unsigned __int64)a1[2] >> 1) & 1;
  v260 = ((unsigned __int64)a1[2] >> 2) & 1;
  v261 = ((unsigned __int8)a1[2] & 8) != 0;
  v262 = ((unsigned __int8)a1[2] & 0x40) != 0;
  v263 = ((unsigned __int8)a1[2] & 0x20) != 0;
  if ( ((_DWORD)a1[3] & 0x3FFFFFFF) != 0x1C )
    goto LABEL_109;
  if ( ((_DWORD)a1[3] & 0x40000000) != 0 )
  {
    if ( !a5 )
    {
LABEL_109:
      v265 = 0;
      v266 = 0;
      v267 = 0;
      goto LABEL_107;
    }
    v52 = *(_QWORD ****)a5;
  }
  else
  {
    v52 = a1;
  }
  v53 = v52 - 19;
  if ( !v53 )
    goto LABEL_109;
  v265 = *((unsigned __int16 *)v53 + 22);
  v266 = *((_WORD *)v53 + 58);
  v267 = *((_DWORD *)v53 + 28);
LABEL_107:
  v254 = v7;
  v264 = v8;
  XeSqlPkg::latch_suspend_begin::Publish((XeSqlPkg::latch_suspend_begin *)v243);
LABEL_7:
  if ( CommonGlobalState::m_CollectingStatistics )
  {
    v16 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v17 = *(_QWORD *)(v16 + 256);
    if ( !v17 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v17 = *(_QWORD *)(v16 + 256);
    }
    v18 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v17 + 992) + 56LL) + 56LL);
    if ( CommonGlobalState::m_PerfCountersEnabled )
    {
      ObjectDataImpl = PerCPUDataImpl::GetObjectDataImpl((PerCPUDataImpl *)&qword_10316EC90);
      ++ObjectDataImpl[8];
      v20 = 0;
      if ( pCounterLookupBlocks )
        v20 = (char *)pCounterLookupBlocks + 24576;
      if ( v20 && *(_QWORD *)v20 )
        _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v20 + 16LL), 1u);
    }
    ++*(_QWORD *)(v18 + 8LL * ((_DWORD)a1[3] & 0x3FFFFFFF));
  }
  v21 = *((_DWORD *)a1 + 6);
  if ( (v21 & 0x3FFFFFFF) != 0x1C )
  {
    v151 = 0;
    if ( (v21 & 0x3FFFFFFF) == 0x6B )
    {
      v10 = 67108944;
      v151 = 0;
    }
    goto LABEL_24;
  }
  v13 = 0;
  v141 = 0;
  if ( (v21 & 0x40000000) != 0 )
  {
    if ( !a5 )
      goto LABEL_21;
    v13 = *(_QWORD *)a5 - 152LL;
  }
  else
  {
    v13 = (__int64)(a1 - 19);
  }
  v141 = v13;
LABEL_21:
  v138 = *((_BYTE *)qword_10317B628 + 48) & 1;
  if ( (*(_DWORD *)(v13 + 100) & 4) != 0 )
  {
    v10 = 67108928;
    v147 = (*(_DWORD *)(v13 + 100) >> 9) & 1;
  }
  else
  {
    v10 = 67108912;
  }
  v151 = (unsigned int)SOS_Task::IsDelayAbortOn() != 0;
LABEL_24:
  v148 = v10 + a3;
  v160 = v10 + a3;
  v22 = *a1;
  if ( *a1 )
  {
    v153 = *v22;
    *v22 = &v153;
  }
  else
  {
    v153 = &v153;
  }
  *a1 = &v153;
  while ( 1 )
  {
    v23 = (unsigned __int64)a1[2] & 0xFFFFFFFFFFFFFFE7uLL;
    if ( *a1 )
      v23 = (unsigned __int64)a1[2] & 0xFFFFFFFFFFFFFFE7uLL | 8;
    v24 = (signed __int64)a1[2];
    if ( v24 == _InterlockedCompareExchange64((volatile signed __int64 *)a1 + 2, v23, v24) )
      break;
    _mm_pause();
  }
  if ( ((_DWORD)a1[3] & 0x40000000) != 0 && *(_DWORD *)(a5 + 12) )
  {
    v51 = (_QWORD *)qword_103189630[*(unsigned __int16 *)(a5 + 16)];
    if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v54 = rand();
      if ( v54 == 5 * (v54 / 5) )
        Spinlock<255,3,258>::UpdateStatSnapshot();
    }
    *v51 = 0;
    *(_DWORD *)(a5 + 12) = 0;
  }
  if ( a4 )
  {
    *a4 = 0;
    a4[1] = 1;
    a4[2] = v10 == 67108928;
  }
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&PerformanceCount);
    v25 = PerformanceCount;
  }
  else
  {
    v25.QuadPart = (LONGLONG)MEMORY[0x7FFE0008];
  }
  if ( v25.QuadPart == -1 )
  {
    LODWORD(v142) = -1;
  }
  else if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    v142 = (unsigned __int64)(1000 * v25.QuadPart) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
  }
  else
  {
    v142 = v25.QuadPart / 0x2710uLL;
  }
  v26 = 0;
  v139 = 0;
  v146 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      memset_0(v269, 0, 0x134u);
      v268 = 0;
      v180 = v148;
      v181 = a1;
      v183 = 0;
      v182 = 0;
      v184 = 0;
      v27 = LatchBase::sm_warningTimeoutMs;
      if ( a2 == -1 )
      {
        v28 = LatchBase::sm_warningTimeoutMs;
        if ( ((_DWORD)a1[3] & 0x3FFFFFFF) == 0x1C && dword_103172528 && dword_103186698 )
        {
          v28 = dword_103186698;
          v27 = dword_103186698;
        }
      }
      else
      {
        v28 = a2 - v26;
        if ( a2 - v26 >= LatchBase::sm_warningTimeoutMs )
          v28 = LatchBase::sm_warningTimeoutMs;
      }
      if ( CommonGlobalState::m_CollectingStatistics )
      {
        if ( v13 )
        {
          LODWORD(v175) = *(_DWORD *)(v13 + 112);
          WORD2(v175) = *(_WORD *)(v13 + 116);
          DWORD2(v175) = *(_DWORD *)(v13 + 44);
          v176 = a1;
          v29 = v175;
          v273 = a1;
          v30 = 24;
        }
        else
        {
          *(_QWORD *)&v177 = a1;
          DWORD2(v177) = (_DWORD)a1[3] & 0x3FFFFFFF;
          v29 = v177;
          v30 = 16;
        }
        Src = v29;
        SOS_Task::SetupWaitReport(&Src, v30);
      }
      ImageHelper = GetImageHelper();
      if ( ImageHelper )
      {
        LODWORD(v271) = *(_DWORD *)ImageHelper != 0;
        HIDWORD(v271) = *((_DWORD *)ImageHelper + 886);
      }
      else
      {
        v271 = 0;
      }
      Waiter = LatchBase::FirstWaiter((LatchBase *)a1);
      LOBYTE(v137) = 1;
      v33 = WaitableBase::Wait(&v155, v28, &v180, 0, v137);
      while ( 1 )
      {
        v34 = (signed __int64)a1[2];
        if ( (v34 & 0x10) == 0 )
        {
          v35 = a1[2];
          if ( v35 == (_QWORD **)_InterlockedCompareExchange64((volatile signed __int64 *)a1 + 2, v34 | 0x10, v34) )
            break;
        }
        _mm_pause();
      }
      if ( !v33 || v154 == 1 )
      {
        while ( 1 )
        {
          v36 = (unsigned __int64)a1[2] & 0xFFFFFFFFFFFFFFE7uLL;
          if ( *a1 )
            v36 = (unsigned __int64)a1[2] & 0xFFFFFFFFFFFFFFE7uLL | 8;
          v37 = (signed __int64)a1[2];
          if ( v37 == _InterlockedCompareExchange64((volatile signed __int64 *)a1 + 2, v36, v37) )
            break;
          _mm_pause();
        }
        if ( CommonGlobalState::m_CollectingStatistics || a4 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v169);
            v38 = v169;
          }
          else
          {
            v38.QuadPart = (LONGLONG)MEMORY[0x7FFE0008];
          }
          if ( v38.QuadPart == -1 )
          {
            LODWORD(v39) = -1;
          }
          else if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            v39 = (unsigned __int64)(1000 * v38.QuadPart) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
          }
          else
          {
            v39 = v38.QuadPart / 0x2710uLL;
          }
          v40 = v39 - v142;
          if ( CommonGlobalState::m_CollectingStatistics )
          {
            v41 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            v42 = *(_QWORD *)(v41 + 256);
            if ( !v42 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v42 = *(_QWORD *)(v41 + 256);
            }
            v43 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v42 + 992) + 56LL) + 56LL);
            v44 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
            if ( CommonGlobalState::m_PerfCountersEnabled )
            {
              v45 = 0;
              if ( pCounterLookupBlocks )
                v45 = (char *)pCounterLookupBlocks + 24576;
              if ( v45 && *(_QWORD *)v45 )
              {
                _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v45 + 8LL), v40);
                v44 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
              }
              if ( *v44 )
              {
                v46 = 0;
                if ( pCounterLookupBlocks )
                  v46 = (char *)pCounterLookupBlocks + 24576;
                if ( v46 && *(_QWORD *)v46 )
                  _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v46 + 24LL), v40);
              }
            }
            v47 = (_DWORD)a1[3] & 0x3FFFFFFF;
            *(_QWORD *)(v43 + 8 * v47 + 1456) += v40;
            v48 = v40 + v145;
            if ( v48 > *(_QWORD *)(v43 + 8 * v47 + 2912) )
              *(_QWORD *)(v43 + 8 * v47 + 2912) = v48;
          }
          if ( a4 )
            *a4 += v40;
        }
        LatchBase::RecordAcquire(a1, a3, a5);
        if ( v33 )
        {
          v178 = 0;
          v116 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v117 = *(_QWORD *)(v116 + 256);
          if ( !v117 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v117 = *(_QWORD *)(v116 + 256);
          }
          v179 = v117;
          v118 = *(_DWORD *)(v117 + 616);
          v119 = !(*(_BYTE *)(v117 + 616) & 1);
          v178 = v119;
          *(_DWORD *)(v117 + 616) = v118 | 1;
          LOBYTE(v137) = 1;
          WaitableBase::Wait(&v155, 0xFFFFFFFFLL, &v180, 0, v137);
          *(_DWORD *)(v117 + 616) &= ~v119;
        }
        if ( v138 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v170);
            QuadPart = (DirtyPageMgr *)v170.QuadPart;
          }
          else
          {
            QuadPart = MEMORY[0x7FFE0008];
          }
          v121 = 0;
          if ( (unsigned __int64)QuadPart >= v25.QuadPart )
            v121 = (char *)QuadPart - v25.QuadPart;
          v122 = PerCPUDataImpl::GetObjectDataImpl((BPool *)((char *)qword_10317B628 + 64));
          *v122 += v121;
        }
        if ( v147 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v171);
            v123 = (DirtyPageMgr *)v171.QuadPart;
          }
          else
          {
            v123 = MEMORY[0x7FFE0008];
          }
          v124 = 0;
          if ( (unsigned __int64)v123 >= v25.QuadPart )
            v124 = (unsigned __int64)v123 - v25.QuadPart;
          _InterlockedExchangeAdd64(
            (volatile signed __int64 *)qword_10317B628
          + 128
          * (unsigned __int64)*(unsigned __int8 *)(((unsigned __int64)*(unsigned __int16 *)(v141 + 118) << *((_BYTE *)qword_10317B628 + 108))
                                                 + *((_QWORD *)qword_10317B628 + 12)
                                                 + 24)
          + 5089,
            v124);
        }
        if ( (dword_10317F6C8 & 0x2000) == 0 )
          goto LABEL_84;
        v173 = 0;
        v125 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v126 = *(_QWORD *)(v125 + 256);
        if ( !v126 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v126 = *(_QWORD *)(v125 + 256);
        }
        v174 = v126;
        v127 = *(_DWORD *)(v126 + 616);
        v173 = !(*(_BYTE *)(v126 + 616) & 1);
        *(_DWORD *)(v126 + 616) = v127 | 1;
        v187 = 0x10000;
        v188 = 0;
        v189 = &v192;
        v190 = v194;
        v195 = 0;
        v191 = 0;
        v196 = 0;
        v192 = &v197;
        v193 = 67;
        v197 = a1;
        v199 = (_DWORD)a1[3] & 0x3FFFFFFF;
        v200 = (unsigned __int64)a1[2] >> 36;
        v201 = ((unsigned __int64)a1[2] >> 12) & 0xFFFFFF;
        v202 = (unsigned int)a1[2] & 1;
        v203 = ((unsigned __int64)a1[2] >> 1) & 1;
        v204 = ((unsigned __int64)a1[2] >> 2) & 1;
        v205 = ((unsigned __int8)a1[2] & 8) != 0;
        v206 = ((unsigned __int8)a1[2] & 0x40) != 0;
        v207 = ((unsigned __int8)a1[2] & 0x20) != 0;
        if ( ((_DWORD)a1[3] & 0x3FFFFFFF) != 0x1C )
          goto LABEL_350;
        if ( ((_DWORD)a1[3] & 0x40000000) != 0 )
        {
          if ( !a5 )
            goto LABEL_350;
          v128 = *(_QWORD ****)a5;
        }
        else
        {
          v128 = a1;
        }
        v129 = v128 - 19;
        if ( v129 )
        {
          v210 = *((unsigned __int16 *)v129 + 22);
          v211 = *((_WORD *)v129 + 58);
          v212 = *((_DWORD *)v129 + 28);
          goto LABEL_335;
        }
LABEL_350:
        v210 = 0;
        v211 = 0;
        v212 = 0;
LABEL_335:
        v130 = 0;
        v131 = 0;
        if ( ((_DWORD)a1[3] & 0x3FFFFFFF) != 0x1C )
          goto LABEL_343;
        if ( ((_DWORD)a1[3] & 0x40000000) != 0 )
        {
          if ( !a5 )
            goto LABEL_343;
          a1 = *(_QWORD ****)a5;
        }
        v132 = a1 - 19;
        if ( a1 != (_QWORD ***)152 && (*((_DWORD *)v132 + 25) & 8) != 0 )
        {
          v133 = (__int64)*v132;
          if ( v133 )
          {
            v130 = (*(unsigned int *)(v133 + 24) | ((unsigned __int64)*(unsigned __int16 *)(v133 + 6) << 32)) << 16;
            v131 = *(_BYTE *)(v133 + 1);
          }
        }
LABEL_343:
        v213 = v130;
        v214 = v131;
        v198 = a3;
        v208 = 1;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v152);
          v134 = (DirtyPageMgr *)v152.QuadPart;
        }
        else
        {
          v134 = MEMORY[0x7FFE0008];
        }
        if ( (unsigned __int64)v134 < v25.QuadPart )
        {
          v135 = 0;
        }
        else
        {
          v135 = (unsigned __int64)v134 - v25.QuadPart;
          if ( v135 == -1 )
          {
            v136 = -1;
LABEL_348:
            v209 = v136;
            XeSqlPkg::latch_suspend_end::Publish((XeSqlPkg::latch_suspend_end *)v186);
            *(_DWORD *)(v126 + 616) &= ~v173;
LABEL_84:
            v49 = 1;
            goto LABEL_85;
          }
        }
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
          v136 = 1000000 * v135 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
        else
          v136 = v135 / 0xA;
        goto LABEL_348;
      }
      if ( v33 == 2 )
      {
        if ( v13 )
        {
          v55 = (signed __int64)a1[2];
          if ( v55 != _InterlockedCompareExchange64((volatile signed __int64 *)a1 + 2, v55 | 0x20, v55) )
            utassert_fail(1u, "success", "latch.cpp", 1850, 0);
        }
        if ( v153 == &v153 )
        {
          *a1 = 0;
        }
        else
        {
          v74 = *a1;
          for ( i = **a1; i != &v153; i = (_QWORD *)*i )
            v74 = i;
          *v74 = v153;
          if ( *a1 == &v153 )
            *a1 = (_QWORD **)v74;
        }
        v153 = 0;
        LatchBase::UnpendEligibleWaiters((LatchBase *)a1, (unsigned __int64)a1[2]);
        v57 = a4;
        if ( CommonGlobalState::m_CollectingStatistics || a4 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v166);
            v56 = v166;
          }
          else
          {
            v56.QuadPart = (LONGLONG)MEMORY[0x7FFE0008];
          }
          if ( v56.QuadPart == -1 )
          {
            LODWORD(v58) = -1;
          }
          else if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            v58 = (unsigned __int64)(1000 * v56.QuadPart) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
          }
          else
          {
            v58 = v56.QuadPart / 0x2710uLL;
          }
          v59 = v58 - v142;
          LODWORD(v142) = v58;
          if ( CommonGlobalState::m_CollectingStatistics )
          {
            v60 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            v61 = *(_QWORD *)(v60 + 256);
            if ( !v61 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v61 = *(_QWORD *)(v60 + 256);
            }
            v62 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v61 + 992) + 56LL) + 56LL);
            v63 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
            if ( CommonGlobalState::m_PerfCountersEnabled )
            {
              v64 = 0;
              if ( pCounterLookupBlocks )
                v64 = (char *)pCounterLookupBlocks + 24576;
              if ( v64 && *(_QWORD *)v64 )
              {
                _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v64 + 8LL), v59);
                v63 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
              }
              if ( *v63 )
              {
                v65 = 0;
                if ( pCounterLookupBlocks )
                  v65 = (char *)pCounterLookupBlocks + 24576;
                if ( v65 && *(_QWORD *)v65 )
                  _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v65 + 24LL), v59);
              }
            }
            v56.QuadPart = (_DWORD)a1[3] & 0x3FFFFFFF;
            *(_QWORD *)(v62 + 8 * v56.QuadPart + 1456) += v59;
            v66 = v59 + v145;
            v145 = v66;
            v13 = v141;
            if ( v66 > *(_QWORD *)(v62 + 8 * v56.QuadPart + 2912) )
              *(_QWORD *)(v62 + 8 * v56.QuadPart + 2912) = v66;
          }
          if ( a4 )
            *a4 += v59;
        }
        if ( (dword_10317F6C8 & 0x2000) == 0 )
          goto LABEL_166;
        v216 = 0x10000;
        v217 = 0;
        v218 = v221;
        v219 = &v222;
        v223 = 0;
        v220 = 0;
        v224 = 0;
        v221[0] = &v225;
        v221[1] = 67;
        v225 = a1;
        v227 = (_DWORD)a1[3] & 0x3FFFFFFF;
        v228 = (unsigned __int64)a1[2] >> 36;
        v229 = ((unsigned __int64)a1[2] >> 12) & 0xFFFFFF;
        v230 = (unsigned int)a1[2] & 1;
        v231 = ((unsigned __int64)a1[2] >> 1) & 1;
        v232 = ((unsigned __int64)a1[2] >> 2) & 1;
        v233 = ((unsigned __int8)a1[2] & 8) != 0;
        v234 = ((unsigned __int8)a1[2] & 0x40) != 0;
        v235 = ((unsigned __int8)a1[2] & 0x20) != 0;
        if ( ((_DWORD)a1[3] & 0x3FFFFFFF) != 0x1C )
          goto LABEL_180;
        if ( ((_DWORD)a1[3] & 0x40000000) != 0 )
        {
          if ( !a5 )
            goto LABEL_180;
          v67 = *(_QWORD ****)a5;
        }
        else
        {
          v67 = a1;
        }
        v68 = v67 - 19;
        if ( v68 )
        {
          v238 = *((unsigned __int16 *)v68 + 22);
          v239 = *((_WORD *)v68 + 58);
          v240 = *((_DWORD *)v68 + 28);
          goto LABEL_160;
        }
LABEL_180:
        v238 = 0;
        v239 = 0;
        v240 = 0;
LABEL_160:
        v241 = 0;
        v242 = 0;
        v226 = a3;
        v236 = 0;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v167);
          v69 = (DirtyPageMgr *)v167.QuadPart;
        }
        else
        {
          v69 = MEMORY[0x7FFE0008];
        }
        if ( (unsigned __int64)v69 < v25.QuadPart )
        {
          v70 = 0;
        }
        else
        {
          v70 = (unsigned __int64)v69 - v25.QuadPart;
          if ( v70 == -1 )
          {
            v71 = -1;
LABEL_165:
            v237 = v71;
            XeSqlPkg::latch_suspend_end::Publish((XeSqlPkg::latch_suspend_end *)v215);
LABEL_166:
            LOBYTE(v56.LowPart) = -111;
            ((void (__fastcall *)(_QWORD))RaiseExecutionAbortedError)((LARGE_INTEGER)v56.QuadPart);
            goto LABEL_167;
          }
        }
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
          v71 = 1000000 * v70 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
        else
          v71 = v70 / 0xA;
        goto LABEL_165;
      }
      if ( v33 == 258 )
        break;
      v57 = a4;
      while ( 1 )
      {
LABEL_167:
        v72 = (unsigned __int64)a1[2] & 0xFFFFFFFFFFFFFFE7uLL;
        if ( *a1 )
          v72 = (unsigned __int64)a1[2] & 0xFFFFFFFFFFFFFFE7uLL | 8;
        v73 = (signed __int64)a1[2];
        if ( v73 == _InterlockedCompareExchange64((volatile signed __int64 *)a1 + 2, v72, v73) )
          break;
        _mm_pause();
      }
      if ( !CommonGlobalState::m_CollectingStatistics )
      {
        v26 = v139;
        if ( !v57 )
          continue;
      }
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v172);
        v98 = v172;
      }
      else
      {
        v98.QuadPart = (LONGLONG)MEMORY[0x7FFE0008];
      }
      if ( v98.QuadPart == -1 )
      {
        LODWORD(v99) = -1;
      }
      else if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v99 = (unsigned __int64)(1000 * v98.QuadPart) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
      }
      else
      {
        v99 = v98.QuadPart / 0x2710uLL;
      }
      v100 = v99 - v142;
      LODWORD(v142) = v99;
      if ( CommonGlobalState::m_CollectingStatistics )
      {
        v101 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v102 = *(_QWORD *)(v101 + 256);
        if ( !v102 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v102 = *(_QWORD *)(v101 + 256);
        }
        v103 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v102 + 992) + 56LL) + 56LL);
        v104 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
        {
          v105 = pCounterLookupBlocks;
          v106 = 0;
          if ( pCounterLookupBlocks )
            v106 = (char *)pCounterLookupBlocks + 24576;
          if ( v106 && *(_QWORD *)v106 )
          {
            _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v106 + 8LL), v100);
            v104 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
            v105 = pCounterLookupBlocks;
          }
          if ( *v104 )
          {
            v107 = 0;
            if ( v105 )
              v107 = (char *)v105 + 24576;
            if ( v107 && *(_QWORD *)v107 )
              _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v107 + 24LL), v100);
          }
        }
        v108 = (_DWORD)a1[3] & 0x3FFFFFFF;
        *(_QWORD *)(v103 + 8 * v108 + 1456) += v100;
        v109 = v100 + v145;
        v145 = v109;
        if ( v109 > *(_QWORD *)(v103 + 8 * v108 + 2912) )
          *(_QWORD *)(v103 + 8 * v108 + 2912) = v109;
      }
      v13 = v141;
      v26 = v139;
      if ( v57 )
        *v57 += v100;
    }
    v76 = 0;
    v77 = 1;
    v139 += v28;
    if ( LatchBase::FirstWaiter((LatchBase *)a1) != Waiter && ((unsigned __int8)a1[2] & 0x20) == 0 )
    {
      v146 = v139;
      v77 = v78;
    }
    if ( (byte_10317ABE6 & 1) != 0 )
      SOS_OS::DebugBreakUncatchable();
    LatchBase::CollectTimeoutInfo((LatchBase *)a1, (struct LatchWaitInfo *)&v153, (struct TimeoutInfo *)&v268);
    v269[0] = a3;
    v79 = v141;
    v270 = v141;
    v269[1] = v139;
    if ( a2 == -1 )
    {
      if ( !v141 || v151 || v139 - v146 < v27 )
      {
        while ( 1 )
        {
          v80 = (unsigned __int64)a1[2] & 0xFFFFFFFFFFFFFFE7uLL;
          if ( *a1 )
            v80 = (unsigned __int64)a1[2] & 0xFFFFFFFFFFFFFFE7uLL | 8;
          v81 = (signed __int64)a1[2];
          if ( v81 == _InterlockedCompareExchange64((volatile signed __int64 *)a1 + 2, v80, v81) )
            break;
          _mm_pause();
        }
        if ( !v77 || v139 <= v27 )
          goto LABEL_203;
        goto LABEL_202;
      }
LABEL_239:
      v95 = (signed __int64)a1[2];
      if ( v95 != _InterlockedCompareExchange64((volatile signed __int64 *)a1 + 2, v95 | 0x20, v95) )
        utassert_fail(1u, "success", "latch.cpp", 1850, 0);
      goto LABEL_241;
    }
    if ( v139 < a2 )
    {
      while ( 1 )
      {
        v93 = (unsigned __int64)a1[2] & 0xFFFFFFFFFFFFFFE7uLL;
        if ( *a1 )
          v93 = (unsigned __int64)a1[2] & 0xFFFFFFFFFFFFFFE7uLL | 8;
        v94 = (signed __int64)a1[2];
        if ( v94 == _InterlockedCompareExchange64((volatile signed __int64 *)a1 + 2, v93, v94) )
          break;
        _mm_pause();
      }
      if ( !v77 )
        goto LABEL_203;
LABEL_202:
      LatchBase::PrintWarning((LatchBase *)a1, (struct TimeoutInfo *)&v268, 1, (struct LatchBase::SubLatchInfo *)a5);
LABEL_203:
      v76 = 1;
      goto LABEL_204;
    }
    if ( v141 )
      goto LABEL_239;
LABEL_241:
    if ( v153 == &v153 )
    {
      *a1 = 0;
    }
    else
    {
      v96 = *a1;
      for ( j = **a1; j != &v153; j = (_QWORD *)*j )
        v96 = j;
      *v96 = v153;
      if ( *a1 == &v153 )
        *a1 = (_QWORD **)v96;
    }
    v153 = 0;
    LatchBase::UnpendEligibleWaiters((LatchBase *)a1, (unsigned __int64)a1[2]);
LABEL_204:
    if ( CommonGlobalState::m_CollectingStatistics || a4 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v168);
        v82 = v168;
      }
      else
      {
        v82.QuadPart = (LONGLONG)MEMORY[0x7FFE0008];
      }
      if ( v82.QuadPart == -1 )
      {
        LODWORD(v83) = -1;
      }
      else if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v83 = (unsigned __int64)(1000 * v82.QuadPart) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
      }
      else
      {
        v83 = v82.QuadPart / 0x2710uLL;
      }
      v84 = v83 - v142;
      LODWORD(v142) = v83;
      if ( CommonGlobalState::m_CollectingStatistics )
      {
        v85 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v86 = *(_QWORD *)(v85 + 256);
        if ( !v86 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v86 = *(_QWORD *)(v85 + 256);
        }
        v87 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v86 + 992) + 56LL) + 56LL);
        v88 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
        if ( CommonGlobalState::m_PerfCountersEnabled )
        {
          v89 = 0;
          if ( pCounterLookupBlocks )
            v89 = (char *)pCounterLookupBlocks + 24576;
          if ( v89 && *(_QWORD *)v89 )
          {
            _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v89 + 8LL), v84);
            v88 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
          }
          if ( *v88 )
          {
            v90 = 0;
            if ( pCounterLookupBlocks )
              v90 = (char *)pCounterLookupBlocks + 24576;
            if ( v90 && *(_QWORD *)v90 )
              _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v90 + 24LL), v84);
          }
        }
        v91 = (_DWORD)a1[3] & 0x3FFFFFFF;
        *(_QWORD *)(v87 + 8 * v91 + 1456) += v84;
        v92 = v84 + v145;
        v145 = v92;
        v79 = v141;
        if ( v92 > *(_QWORD *)(v87 + 8 * v91 + 2912) )
          *(_QWORD *)(v87 + 8 * v91 + 2912) = v92;
      }
      if ( a4 )
        *a4 += v84;
    }
    if ( !v76 )
      break;
    v13 = v141;
    v26 = v139;
  }
  if ( (dword_10317F6C8 & 0x2000) != 0 )
  {
    v187 = 0x10000;
    v188 = 0;
    v189 = &v192;
    v190 = v194;
    v195 = 0;
    v191 = 0;
    v196 = 0;
    v192 = &v197;
    v193 = 67;
    v197 = a1;
    v199 = (_DWORD)a1[3] & 0x3FFFFFFF;
    v200 = (unsigned __int64)a1[2] >> 36;
    v201 = ((unsigned __int64)a1[2] >> 12) & 0xFFFFFF;
    v202 = (unsigned int)a1[2] & 1;
    v203 = ((unsigned __int64)a1[2] >> 1) & 1;
    v204 = ((unsigned __int64)a1[2] >> 2) & 1;
    v205 = ((unsigned __int8)a1[2] & 8) != 0;
    v206 = ((unsigned __int8)a1[2] & 0x40) != 0;
    v207 = ((unsigned __int8)a1[2] & 0x20) != 0;
    if ( ((_DWORD)a1[3] & 0x3FFFFFFF) != 0x1C )
      goto LABEL_299;
    if ( ((_DWORD)a1[3] & 0x40000000) != 0 )
    {
      if ( a5 )
      {
        v110 = *(_QWORD ****)a5;
        goto LABEL_287;
      }
      goto LABEL_299;
    }
    v110 = a1;
LABEL_287:
    v111 = v110 - 19;
    if ( v111 )
    {
      v210 = *((unsigned __int16 *)v111 + 22);
      v211 = *((_WORD *)v111 + 58);
      v212 = *((_DWORD *)v111 + 28);
    }
    else
    {
LABEL_299:
      v210 = 0;
      v211 = 0;
      v212 = 0;
    }
    v213 = 0;
    v214 = 0;
    v112 = a3;
    v198 = a3;
    v208 = 0;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v152);
      v113 = (DirtyPageMgr *)v152.QuadPart;
    }
    else
    {
      v113 = MEMORY[0x7FFE0008];
    }
    if ( (unsigned __int64)v113 < v25.QuadPart )
    {
      v114 = 0;
    }
    else
    {
      v114 = (unsigned __int64)v113 - v25.QuadPart;
      if ( v114 == -1 )
      {
        v115 = -1;
        goto LABEL_294;
      }
    }
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
      v115 = 1000000 * v114 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
    else
      v115 = v114 / 0xA;
LABEL_294:
    v209 = v115;
    XeSqlPkg::latch_suspend_end::Publish((XeSqlPkg::latch_suspend_end *)v186);
  }
  else
  {
    v112 = a3;
  }
  if ( v79 )
  {
    LatchBase::PrintWarning((LatchBase *)a1, (struct TimeoutInfo *)&v268, 0, (struct LatchBase::SubLatchInfo *)a5);
    memset_0(v274, 0, 0x208u);
    LatchBase::GetCommonDescription((struct LatchBase *)a1, v274, 0x208u);
    v149 = *(_DWORD *)(v79 + 112);
    v150 = *(_WORD *)(v79 + 116);
    LODWORD(v137) = v112;
    ex_raise(8, 45, 17, 1, v137, &v149, *(unsigned __int16 *)(v79 + 44), v274);
  }
  v49 = 0;
LABEL_85:
  if ( v163 )
    *v164 = 0;
  v155 = &EventAutoInternal<SuspendQueueSLock>::`vftable';
  return v49;
}

```

## disassembly

```asm
0x1004601d0  push    rbp
0x1004601d2  push    rbx
0x1004601d3  push    rsi
0x1004601d4  push    rdi
0x1004601d5  push    r12
0x1004601d7  push    r13
0x1004601d9  push    r14
0x1004601db  push    r15
0x1004601dd  lea     rbp, [rsp-0C78h]
0x1004601e5  sub     rsp, 0D78h
0x1004601ec  mov     [rbp+0CB0h+var_BD0], 0FFFFFFFFFFFFFFFEh
0x1004601f7  mov     rax, cs:__security_cookie
0x1004601fe  xor     rax, rsp
0x100460201  mov     [rbp+0CB0h+var_50], rax
0x100460208  mov     r12, r9
0x10046020b  mov     [rsp+0DB0h+var_D48], r9
0x100460210  mov     r10d, r8d
0x100460213  mov     [rsp+0DB0h+var_D68], r8d
0x100460218  mov     r9d, edx
0x10046021b  mov     [rsp+0DB0h+var_D50], edx
0x10046021f  mov     rsi, rcx
0x100460222  mov     r13, [rbp+0CB0h+arg_20]
0x100460229  mov     [rsp+0DB0h+var_D38], r13
0x10046022e  mov     edi, 4000020h
0x100460233  xor     r11d, r11d
0x100460236  mov     [rsp+0DB0h+var_D40], r11
0x10046023b  lea     rax, ??_7MinWaitableBase@@6B@; const MinWaitableBase::`vftable'
0x100460242  mov     [rbp+0CB0h+var_CE0], rax
0x100460246  mov     [rbp+0CB0h+var_CD8], r11
0x10046024a  mov     [rbp+0CB0h+var_CD0], r11
0x10046024e  lea     rax, [rbp+0CB0h+var_CD8]
0x100460252  mov     [rbp+0CB0h+var_CD0], rax
0x100460256  lea     rax, [rbp+0CB0h+var_CD8]
0x10046025a  mov     [rbp+0CB0h+var_CD8], rax
0x10046025e  lea     rax, ??_7WaitableBase@@6B@; const WaitableBase::`vftable'
0x100460265  mov     [rbp+0CB0h+var_CE0], rax
0x100460269  lea     rax, ??_7?$LockedWaitQueue@VWaitableBase@@USuspendQueueSLock@@@@6B@; const LockedWaitQueue<WaitableBase,SuspendQueueSLock>::`vftable'
0x100460270  mov     [rbp+0CB0h+var_CE0], rax
0x100460274  mov     [rbp+0CB0h+var_CC8], r11
0x100460278  lea     rax, ??_7?$EventInternal@USuspendQueueSLock@@@@6B@; const EventInternal<SuspendQueueSLock>::`vftable'
0x10046027f  mov     [rbp+0CB0h+var_CE0], rax
0x100460283  mov     [rbp+0CB0h+var_CC0], r11d
0x100460287  mov     r15d, 1
0x10046028d  mov     [rbp+0CB0h+var_CBC], r15d
0x100460291  mov     [rbp+0CB0h+var_CB8], r11
0x100460295  lea     rax, ??_7?$EventAutoInternal@USuspendQueueSLock@@@@6B@; const EventAutoInternal<SuspendQueueSLock>::`vftable'
0x10046029c  mov     [rbp+0CB0h+var_CE0], rax
0x1004602a0  mov     [rbp+0CB0h+var_CF0], r11
0x1004602a4  mov     [rbp+0CB0h+var_CE8], r11d
0x1004602a8  mov     [rbp+0CB0h+var_CB0], r11d
0x1004602ac  mov     rdx, gs:58h
0x1004602b5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004602bc  mov     ecx, [rax]
0x1004602be  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004602c5  mov     ebx, [rax]
0x1004602c7  add     rbx, [rdx+rcx*8]
0x1004602cb  mov     rax, [rbx+100h]
0x1004602d2  test    rax, rax
0x1004602d5  jz      loc_10187363B
0x1004602db  mov     rax, [rax+258h]
0x1004602e2  mov     [rbp+0CB0h+var_CA8], rax
0x1004602e6  mov     eax, [rbp+0CB0h+arg_28]
0x1004602ec  mov     [rbp+0CB0h+var_CA0], eax
0x1004602ef  mov     r14, r11
0x1004602f2  mov     [rsp+0DB0h+var_D60], r11
0x1004602f7  mov     [rbp+0CB0h+var_D24], r11d
0x1004602fb  mov     [rsp+0DB0h+var_D70], 0
0x100460300  mov     r8, gs:58h
0x100460309  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100460310  mov     ecx, [rax]
0x100460312  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100460319  mov     edx, [rax]
0x10046031b  add     rdx, [r8+rcx*8]
0x10046031f  mov     rcx, [rdx+8]
0x100460323  test    rcx, rcx
0x100460326  jz      loc_10187365D
0x10046032c  mov     rcx, [rcx+30h]
0x100460330  mov     [rbp+0CB0h+var_C88], rcx
0x100460334  test    rcx, rcx
0x100460337  jz      loc_101873661
0x10046033d  mov     eax, r11d
0x100460340  cmp     dword ptr [rcx], 0
0x100460343  setz    al
0x100460346  mov     [rbp+0CB0h+var_C90], eax
0x100460349  mov     [rcx], r15d
0x10046034c  jmp     short loc_10046034F
0x10046034f  test    cs:dword_10317F6C8, 1000h
0x100460359  jnz     loc_10187366B
0x10046035f  mov     rax, cs:__imp_?m_CollectingStatistics@CommonGlobalState@@2_NA; bool CommonGlobalState::m_CollectingStatistics
0x100460366  cmp     byte ptr [rax], 0
0x100460369  jz      loc_10046040E
0x10046036f  mov     rdx, gs:58h
0x100460378  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10046037f  mov     ecx, [rax]
0x100460381  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100460388  mov     ebx, [rax]
0x10046038a  add     rbx, [rdx+rcx*8]
0x10046038e  mov     rax, [rbx+100h]
0x100460395  test    rax, rax
0x100460398  jz      loc_1018737E7
0x10046039e  mov     rax, [rax+3E0h]
0x1004603a5  mov     rcx, [rax+38h]
0x1004603a9  mov     rbx, [rcx+38h]
0x1004603ad  mov     rax, cs:__imp_?m_PerfCountersEnabled@CommonGlobalState@@2_NA; bool CommonGlobalState::m_PerfCountersEnabled
0x1004603b4  cmp     byte ptr [rax], 0
0x1004603b7  jz      short loc_100460402
0x1004603b9  lea     rcx, qword_10316EC90; this
0x1004603c0  call    ?GetObjectDataImpl@PerCPUDataImpl@@IEBAPEAXXZ; PerCPUDataImpl::GetObjectDataImpl(void)
0x1004603c5  inc     qword ptr [rax+40h]
0x1004603c9  mov     rax, cs:__imp_?m_PerfCountersEnabled@CommonGlobalState@@2_NA; bool CommonGlobalState::m_PerfCountersEnabled
0x1004603d0  cmp     byte ptr [rax], 0
0x1004603d3  jz      short loc_100460402
0x1004603d5  mov     rcx, cs:?pCounterLookupBlocks@@3PAPEAY1DK@BAA@PEA_KA; unsigned __int64 * (* near * pCounterLookupBlocks)[58][256]
0x1004603dc  lea     rax, [rcx+6000h]
0x1004603e3  xor     edx, edx
0x1004603e5  test    rcx, rcx
0x1004603e8  cmovnz  rdx, rax
0x1004603ec  test    rdx, rdx
0x1004603ef  jz      short loc_100460402
0x1004603f1  mov     rcx, [rdx]
0x1004603f4  test    rcx, rcx
0x1004603f7  jz      short loc_100460402
0x1004603f9  mov     rax, r15
0x1004603fc  lock xadd [rcx+10h], rax
0x100460402  mov     eax, [rsi+18h]
0x100460405  and     eax, 3FFFFFFFh
0x10046040a  inc     qword ptr [rbx+rax*8]
0x10046040e  mov     eax, [rsi+18h]
0x100460411  and     eax, 3FFFFFFFh
0x100460416  cmp     eax, 1Ch
0x100460419  mov     eax, [rsi+18h]
0x10046041c  jnz     loc_1004B34EA
0x100460422  xor     r14d, r14d
0x100460425  mov     [rsp+0DB0h+var_D60], r14
0x10046042a  bt      eax, 1Eh
0x10046042e  jb      loc_1004B9598
0x100460434  lea     r14, [rsi-98h]
0x10046043b  mov     [rsp+0DB0h+var_D60], r14
0x100460440  mov     rax, cs:qword_10317B628
0x100460447  movzx   eax, byte ptr [rax+30h]
0x10046044b  and     al, 1
0x10046044d  mov     [rsp+0DB0h+var_D70], al
0x100460451  mov     eax, [r14+64h]
0x100460455  test    al, 4
0x100460457  jnz     loc_10047302C
0x10046045d  mov     edi, 4000030h
0x100460462  call    ?IsDelayAbortOn@SOS_Task@@SAHXZ; SOS_Task::IsDelayAbortOn(void)
0x100460467  xor     edx, edx
0x100460469  test    eax, eax
0x10046046b  setnz   dl
0x10046046e  mov     [rbp+0CB0h+var_D00], rdx
0x100460472  jmp     short loc_100460475
0x100460475  mov     eax, [rsp+0DB0h+var_D68]
0x100460479  add     eax, edi
0x10046047b  mov     [rbp+0CB0h+var_D20], eax
0x10046047e  mov     [rbp+0CB0h+var_CB0], eax
0x100460481  mov     rcx, [rsi]
0x100460484  test    rcx, rcx
0x100460487  jnz     loc_10045FFA3
0x10046048d  lea     rax, [rbp+0CB0h+var_CF0]
0x100460491  mov     [rbp+0CB0h+var_CF0], rax
0x100460495  jmp     short loc_100460498
0x100460498  lea     rax, [rbp+0CB0h+var_CF0]
0x10046049c  mov     [rsi], rax
0x10046049f  nop
0x1004604a0  mov     rax, [rsi+10h]
0x1004604a4  mov     rdx, rax
0x1004604a7  and     rdx, 0FFFFFFFFFFFFFFEFh
0x1004604ab  mov     rcx, rdx
0x1004604ae  or      rcx, 8
0x1004604b2  and     rdx, 0FFFFFFFFFFFFFFF7h
0x1004604b6  cmp     qword ptr [rsi], 0
0x1004604ba  cmovnz  rdx, rcx
0x1004604be  lock cmpxchg [rsi+10h], rdx
0x1004604c4  jnz     loc_1018737FC
0x1004604ca  mov     eax, [rsi+18h]
0x1004604cd  bt      eax, 1Eh
0x1004604d1  jb      loc_1004B955E
0x1004604d7  xor     r13d, r13d
0x1004604da  test    r12, r12
0x1004604dd  jz      short loc_1004604F9
0x1004604df  mov     [r12], r13d
0x1004604e3  mov     [r12+4], r15d
0x1004604e8  mov     eax, r13d
0x1004604eb  cmp     edi, 4000040h
0x1004604f1  setz    al
0x1004604f4  mov     [r12+8], eax
0x1004604f9  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100460500  cmp     dword ptr [rax], 0
0x100460503  jz      loc_101873836
0x100460509  lea     rcx, [rbp+0CB0h+PerformanceCount]; lpPerformanceCount
0x10046050d  call    cs:__imp_QueryPerformanceCounter
0x100460513  mov     rdi, qword ptr [rbp+0CB0h+PerformanceCount]
0x100460517  jmp     short loc_10046051A
0x10046051a  mov     rcx, 346DC5D63886594Bh
0x100460524  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x100460528  jz      loc_101873844
0x10046052e  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100460535  cmp     dword ptr [rax], 0
0x100460538  jz      loc_10187384F
0x10046053e  mov     rax, cs:__imp_?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A; _LARGE_INTEGER Base_PublicGlobals::sm_QueryPerformanceFrequency
0x100460545  mov     rcx, [rax]
0x100460548  imul    rax, rdi, 3E8h
0x10046054f  xor     edx, edx
0x100460551  div     rcx
0x100460554  mov     [rsp+0DB0h+var_D58], rax
0x100460559  jmp     short loc_10046055C
0x10046055c  mov     r15d, r13d
0x10046055f  mov     [rsp+0DB0h+var_D6C], r13d
0x100460564  mov     [rbp+0CB0h+var_D28], r13d
0x100460568  nop     dword ptr [rax+rax+00000000h]
0x100460570  xor     edx, edx; Val
0x100460572  mov     r8d, 134h; Size
0x100460578  lea     rcx, [rbp+0CB0h+var_3BC]; void *
0x10046057f  call    memset_0
0x100460584  mov     [rbp+0CB0h+var_3C0], r13d
0x10046058b  mov     eax, [rbp+0CB0h+var_D20]
0x10046058e  mov     [rbp+0CB0h+var_BF8], eax
0x100460594  mov     [rbp+0CB0h+var_BF0], rsi
0x10046059b  mov     [rbp+0CB0h+var_BE0], r13
0x1004605a2  mov     [rbp+0CB0h+var_BE8], r13
0x1004605a9  mov     [rbp+0CB0h+var_BD8], r13
0x1004605b0  mov     r13d, cs:?sm_warningTimeoutMs@LatchBase@@0IC; uint volatile LatchBase::sm_warningTimeoutMs
0x1004605b7  mov     eax, [rsp+0DB0h+var_D50]
0x1004605bb  cmp     eax, 0FFFFFFFFh
0x1004605be  jnz     loc_10187387C
0x1004605c4  mov     ebx, cs:?sm_warningTimeoutMs@LatchBase@@0IC; uint volatile LatchBase::sm_warningTimeoutMs
0x1004605ca  mov     eax, [rsi+18h]
0x1004605cd  and     eax, 3FFFFFFFh
0x1004605d2  cmp     eax, 1Ch
0x1004605d5  jnz     short loc_1004605E4
0x1004605d7  cmp     cs:dword_103172528, 0
0x1004605de  jnz     loc_101873864
0x1004605e4  mov     rax, cs:__imp_?m_CollectingStatistics@CommonGlobalState@@2_NA; bool CommonGlobalState::m_CollectingStatistics
0x1004605eb  cmp     byte ptr [rax], 0
0x1004605ee  jz      short loc_100460652
0x1004605f0  test    r14, r14
0x1004605f3  jz      loc_1004B350D
0x1004605f9  mov     eax, [r14+70h]
0x1004605fd  mov     dword ptr [rbp+0CB0h+var_C30], eax
0x100460603  movzx   eax, word ptr [r14+74h]
0x100460608  mov     word ptr [rbp+0CB0h+var_C30+4], ax
0x10046060f  mov     eax, [r14+2Ch]
0x100460613  mov     dword ptr [rbp+0CB0h+var_C30+8], eax
0x100460619  mov     [rbp+0CB0h+var_C20], rsi
0x100460620  movups  xmm0, [rbp+0CB0h+var_C30]
0x100460627  movsd   xmm1, [rbp+0CB0h+var_C20]
0x10046062f  movsd   [rbp+0CB0h+var_278], xmm1
0x100460637  mov     edx, 18h; Size
0x10046063c  jmp     short loc_10046063F
0x10046063f  movups  [rbp+0CB0h+Src], xmm0
0x100460646  lea     rcx, [rbp+0CB0h+Src]; Src
0x10046064d  call    ?SetupWaitReport@SOS_Task@@SAXPEAXK@Z; SOS_Task::SetupWaitReport(void *,ulong)
0x100460652  call    cs:__imp_?GetImageHelper@@YAAEAVCImageHelper@@XZ; GetImageHelper(void)
0x100460658  test    rax, rax
0x10046065b  jz      loc_10187389B
0x100460661  xor     ecx, ecx
0x100460663  cmp     [rax], ecx
0x100460665  setnz   cl
0x100460668  mov     dword ptr [rbp+0CB0h+var_2A4], ecx
0x10046066e  mov     eax, [rax+0DD8h]
0x100460674  mov     dword ptr [rbp+0CB0h+var_2A4+4], eax
0x10046067a  jmp     short loc_10046067D
0x10046067d  mov     rcx, rsi; this
0x100460680  call    ?FirstWaiter@LatchBase@@AEBAPEAULatchWaitInfo@@XZ; LatchBase::FirstWaiter(void)
0x100460685  mov     r12, rax
0x100460688  mov     byte ptr [rsp+0DB0h+var_D90], 1
0x10046068d  xor     r9d, r9d
0x100460690  lea     r8, [rbp+0CB0h+var_BF8]
0x100460697  mov     edx, ebx
0x100460699  lea     rcx, [rbp+0CB0h+var_CE0]
0x10046069d  call    cs:__imp_?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z; WaitableBase::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS,bool)
0x1004606a3  mov     r15d, eax
0x1004606a6  nop     word ptr [rax+rax+00000000h]
0x1004606b0  mov     rax, [rsi+10h]
0x1004606b4  test    al, 10h
0x1004606b6  jnz     loc_10045F765
0x1004606bc  mov     rcx, rax
0x1004606bf  or      rcx, 10h
0x1004606c3  lock cmpxchg [rsi+10h], rcx
0x1004606c9  jnz     loc_10045F765
0x1004606cf  test    r15d, r15d
0x1004606d2  jnz     loc_1018738A8
0x1004606d8  mov     rax, [rsi+10h]
0x1004606dc  mov     rdx, rax
0x1004606df  and     rdx, 0FFFFFFFFFFFFFFEFh
0x1004606e3  mov     rcx, rdx
0x1004606e6  or      rcx, 8
0x1004606ea  and     rdx, 0FFFFFFFFFFFFFFF7h
0x1004606ee  cmp     qword ptr [rsi], 0
0x1004606f2  cmovnz  rdx, rcx
0x1004606f6  lock cmpxchg [rsi+10h], rdx
0x1004606fc  jnz     loc_101874617
0x100460702  mov     rax, cs:__imp_?m_CollectingStatistics@CommonGlobalState@@2_NA; bool CommonGlobalState::m_CollectingStatistics
0x100460709  mov     r12, [rsp+0DB0h+var_D48]
0x10046070e  cmp     byte ptr [rax], 0
0x100460711  jz      loc_10187461F
0x100460717  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10046071e  cmp     dword ptr [rax], 0
0x100460721  jz      loc_10187462E
  ... truncated ...
```
