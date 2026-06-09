# SQLMemoryReport::UpdatePerfCounters(void)

- ea: `0x10040cde0`
- end: `0x10040d700`
- name: `?UpdatePerfCounters@SQLMemoryReport@@SAXXZ`
- size: `2336`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `33`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10040ac50`

## callees

- `0x100401490`
- `0x100402000`
- `0x100402620`
- `0x100402a60`
- `0x100405770`
- `0x1004058c0`
- `0x100405990`
- `0x100405a60`
- `0x100405ad0`
- `0x10040bbf0`
- `0x10040cde0`
- `0x10040d710`
- `0x10040d7e0`
- `0x10040d8c0`
- `0x1005666e0`
- `0x10060d810`
- `0x100644f50`
- `0x100645100`
- `0x1006452b0`
- `0x100645460`
- `0x100645610`
- `0x1006457c0`
- `0x100645970`
- `0x100645b20`
- `0x100645cd0`
- `0x100645e80`
- `0x100646030`
- `0x1006461e0`
- `0x1006925d0`
- `0x1006c66e0`
- `0x1006c6920`
- `0x100830ac0`
- `0x1019213f0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10189eece`
- `KERNEL32!QueryPerformanceCounter` at `0x10189ef11`
- `KERNEL32!QueryPerformanceCounter` at `0x10189f5b1`
- `KERNEL32!QueryPerformanceCounter` at `0x10189f5f9`
- `KERNEL32!QueryPerformanceCounter` at `0x10189eece`
- `KERNEL32!QueryPerformanceCounter` at `0x10189ef11`
- `KERNEL32!QueryPerformanceCounter` at `0x10189f5b1`
- `KERNEL32!QueryPerformanceCounter` at `0x10189f5f9`
- `sqlTsEs!?PrintStringW@@YAHPEA_WKPEB_WZZ` at `0x10189f2cc`
- `sqlTsEs!?PrintStringW@@YAHPEA_WKPEB_WZZ` at `0x10189f2cc`
- `sqldk!?GetMemoryBrokerClerks@ResourceMonitor@@QEAAPEAVMemoryBrokerClerkList@@XZ` at `0x10040d1d4`
- `sqldk!?GetMemoryBrokerClerks@ResourceMonitor@@QEAAPEAVMemoryBrokerClerkList@@XZ` at `0x10040d1d4`
- `sqldk!?GetNodeList@MemoryNodeManager@@QEAAPEAVMemoryNodeList@@XZ` at `0x10040c10b`
- `sqldk!?GetNodeList@MemoryNodeManager@@QEAAPEAVMemoryNodeList@@XZ` at `0x10040c10b`
- `sqldk!?GetPagesCommitted@MemoryNode@@QEBA_JXZ` at `0x10040c252`
- `sqldk!?GetPagesCommitted@MemoryNode@@QEBA_JXZ` at `0x10040c252`
- `sqldk!?GetTotalPagesReserved@MemoryNode@@SA_JXZ` at `0x10040cea4`
- `sqldk!?GetTotalPagesReserved@MemoryNode@@SA_JXZ` at `0x10040cea4`
- `sqldk!?GetPagesFree@MemoryNode@@QEBA_JXZ` at `0x10040c275`
- `sqldk!?GetPagesFree@MemoryNode@@QEBA_JXZ` at `0x10040c275`
- `sqldk!?GetPagesDecommitted@MemoryNode@@QEBA_JXZ` at `0x10040c284`
- `sqldk!?GetPagesDecommitted@MemoryNode@@QEBA_JXZ` at `0x10040c284`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040c1e6`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040d67a`
- `sqldk!?sm_isResourceManagerEnabled@SOS_PublicGlobals@@2HA` at `0x10040be7b`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10189ee73`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10189f554`
- `sqldk!?sm_MemoryNodeManager@SOS_PublicGlobals@@2VMemoryNodeManager@@A` at `0x10040c104`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10189eedb`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10189f5be`
- `sqldk!?MemoryNode_MemoryTargetPages@@3_JA` at `0x10040d019`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10189eebe`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10189ef01`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10189f5a2`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10189f5e9`
- `sqldk!?m_ProfilerTraceEnabled@CommonGlobalState@@2_NA` at `0x10040c6d2`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040bcb5`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040bdf6`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040be34`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040befb`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040bf57`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040bfc1`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c003`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c051`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c072`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c0ac`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c0cf`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c2a5`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c334`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c3b9`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c40f`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c4a9`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c4cc`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c53c`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c5c0`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c686`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040cebb`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040cf11`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040cf64`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040cfb7`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040d00d`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040d069`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040d0bf`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040d111`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040d378`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040d394`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040d3ff`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040d41b`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040d4a1`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040d506`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040d56e`
- `sqldk!?GetLocalTargetPages@MemoryNode@@QEBA_JXZ` at `0x10040c4bf`
- `sqldk!?GetLocalTargetPages@MemoryNode@@QEBA_JXZ` at `0x10040c4bf`
- `sqldk!?Destroy@MemoryNode@@AEAAXXZ` at `0x10040c680`
- `sqldk!?Destroy@MemoryNode@@AEAAXXZ` at `0x10189f6b5`
- `sqldk!?Destroy@MemoryNode@@AEAAXXZ` at `0x10040c680`
- `sqldk!?Destroy@MemoryNode@@AEAAXXZ` at `0x10189f6b5`
- `sqldk!?GetTotalPagesFree@MemoryNode@@SA_JXZ` at `0x10040ce68`
- `sqldk!?GetTotalPagesFree@MemoryNode@@SA_JXZ` at `0x10040ce68`
- `sqldk!?GetTotalPagesCommitted@MemoryNode@@SA_JXZ` at `0x10040ce40`
- `sqldk!?GetTotalPagesCommitted@MemoryNode@@SA_JXZ` at `0x10040ce40`
- `sqldk!?GetTotalPhysicalMemory@MemoryNode@@SA_KXZ` at `0x10040c74c`
- `sqldk!?GetTotalPhysicalMemory@MemoryNode@@SA_KXZ` at `0x10040c74c`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040d240`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040d25f`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040d2ad`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040d2c7`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040d240`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040d25f`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040d2ad`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040d2c7`
- `sqldk!SystemThread_TlsIndex` at `0x10040c6fb`
- `sqldk!SystemThread_TlsIndex` at `0x10189ee90`
- `sqldk!SystemThread_TlsIndex` at `0x10189f574`
- `sqldk!SystemThread_TlsIndex` at `0x10189fa31`
- `sqldk!SystemThread_TlsOffset` at `0x10040c704`
- `sqldk!SystemThread_TlsOffset` at `0x10189ee99`
- `sqldk!SystemThread_TlsOffset` at `0x10189f57d`
- `sqldk!SystemThread_TlsOffset` at `0x10189fa3a`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x10040d256`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x10040d2be`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x10040d256`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x10040d2be`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10189ef9c`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10189f66e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10189ef9c`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10189f66e`
- `sqllang!?CpagesInUse@CSqlMgr@@QEAAKXZ` at `0x10040c0c2`
- `sqllang!?CpagesInUse@CSqlMgr@@QEAAKXZ` at `0x10040c0c2`
- `sqllang!?GetSqlManager@@YAPEAVCSqlMgr@@XZ` at `0x10040c0b9`
- `sqllang!?GetSqlManager@@YAPEAVCSqlMgr@@XZ` at `0x10040c0b9`
- `sqllang!?ProduceRecord@CTraceController@@QEAAXH@Z` at `0x10189fa68`
- `sqllang!?ProduceRecord@CTraceController@@QEAAXH@Z` at `0x10189fa68`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void SQLMemoryReport::UpdatePerfCounters(void)
{
  double v0; // xmm0_8
  unsigned __int64 v1; // rax
  _QWORD **v2; // r8
  __int64 j; // rbx
  _BYTE *v4; // r8
  char *v5; // rdx
  char *v6; // rdx
  __int64 v7; // r10
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r9
  _BYTE *v11; // r8
  __int128 v12; // rax
  __int64 v13; // r11
  char *v14; // rdx
  __int64 v15; // rcx
  __int128 v16; // rax
  bool v17; // zf
  char *v18; // rdx
  char *v19; // rdx
  char *v20; // rdx
  __int64 v21; // rax
  _BYTE *v22; // r8
  char *v23; // r9
  CSqlMgr *SqlManager; // rax
  __int64 v25; // r8
  char *v26; // rdx
  struct MemoryNodeList *NodeList; // rbx
  __int64 v28; // rax
  unsigned __int16 *v29; // r12
  __int64 v30; // rdi
  struct MemoryNodeList *v31; // r14
  DirtyPageMgr *v32; // rbx
  signed __int64 v33; // rsi
  __int64 v34; // rdi
  signed __int32 v35; // ecx
  unsigned __int16 v36; // di
  unsigned __int64 v37; // r14
  unsigned int v38; // edx
  __int64 PagesCommitted; // r15
  unsigned __int64 v40; // rdi
  __int64 PagesFree; // rsi
  __int64 PagesDecommitted; // rax
  __int64 v43; // r15
  signed __int64 v44; // r9
  int v45; // edx
  unsigned __int64 v46; // r12
  __int64 v47; // rcx
  __int64 **v48; // rcx
  __int64 *v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // rtt
  signed __int64 v52; // r9
  int v53; // edx
  __int64 v54; // rcx
  __int64 *v55; // rcx
  __int64 v56; // rcx
  signed __int64 v57; // rdx
  __int64 v58; // kr00_8
  int v59; // eax
  signed __int64 v60; // r8
  int v61; // edx
  __int64 v62; // rcx
  __int64 *v63; // rcx
  __int64 v64; // rcx
  signed __int64 v65; // rdx
  signed __int64 v66; // r8
  int v67; // edx
  __int64 v68; // rcx
  __int64 *v69; // rcx
  __int64 v70; // rcx
  signed __int64 v71; // rdx
  signed __int64 v72; // r8
  int v73; // edx
  __int64 v74; // rcx
  __int64 *v75; // rcx
  __int64 v76; // rcx
  signed __int64 v77; // rdx
  signed __int64 v78; // r8
  __int64 v79; // rcx
  __int64 *v80; // rcx
  __int64 v81; // rcx
  signed __int64 v82; // rdx
  char *v83; // rdx
  int v84; // esi
  __int64 v85; // rax
  _DWORD *v86; // rax
  int v87; // r14d
  __int64 TotalPagesCommitted; // r15
  __int64 v89; // rax
  __int64 TotalPagesFree; // r14
  BPool *v91; // rsi
  __int64 v92; // rdi
  unsigned __int16 v93; // bx
  __int64 TotalPagesReserved; // rsi
  __int64 v95; // rbx
  __int64 v96; // rdi
  int v97; // r8d
  char *v98; // rdx
  int v99; // r8d
  char *v100; // rdx
  __int64 v101; // rsi
  int v102; // r8d
  char *v103; // rdx
  __int64 v104; // rbx
  int v105; // r8d
  char *v106; // rdx
  int v107; // r9d
  char *v108; // rdx
  int v109; // r8d
  char *v110; // rdx
  __int64 v111; // rcx
  char *v112; // rdx
  unsigned __int16 *v113; // r15
  __int64 v114; // rsi
  __int64 v115; // r14
  signed __int64 v116; // rdi
  struct SOS_Node *Next; // r15
  __int64 v118; // rsi
  struct MemoryBrokerClerkList *MemoryBrokerClerks; // r14
  DirtyPageMgr *v120; // r13
  unsigned int i; // r12d
  DirtyPageMgr *QuadPart; // rbx
  PerProcessGlobals *ClientProcessGlobals; // rax
  struct MemoryClerk **DefaultMemoryClerksForNode; // rbx
  struct MemoryClerk *v125; // rcx
  __int64 v126; // rsi
  PerProcessGlobals *v127; // rax
  struct MemoryClerk **v128; // rbx
  struct MemoryClerk *v129; // rcx
  __int64 v130; // r14
  _QWORD *v131; // rcx
  _QWORD *v132; // rcx
  double v133; // xmm0_8
  unsigned __int64 v134; // rax
  unsigned __int64 v135; // rsi
  signed __int64 v136; // rdx
  signed __int64 v137; // r8
  __int64 *v138; // rcx
  __int64 v139; // rcx
  signed __int64 v140; // r8
  __int64 v141; // rdx
  __int64 **v142; // rcx
  __int64 *v143; // rcx
  __int64 v144; // rdx
  __int64 v145; // rtt
  double v146; // xmm0_8
  unsigned __int64 v147; // rax
  signed __int64 v148; // rdx
  __int64 v149; // rcx
  __int64 *v150; // rcx
  __int64 v151; // rcx
  signed __int64 v152; // r8
  signed __int64 v153; // r8
  __int64 v154; // rcx
  __int64 *v155; // rcx
  __int64 v156; // rcx
  signed __int64 v157; // rdx
  signed __int64 v158; // r8
  __int64 v159; // rcx
  __int64 *v160; // rcx
  __int64 v161; // rcx
  signed __int64 v162; // rdx
  volatile signed __int64 *v163; // r15
  signed __int64 UniqueThread_low; // r14
  struct MemoryBrokerClerkList *v165; // rcx
  signed __int32 v166; // ecx
  __int64 v167; // rax
  DirtyPageMgr *v168; // rcx
  volatile signed __int32 *v169; // rsi
  __int64 v170; // r8
  DirtyPageMgr *v171; // rcx
  signed __int64 v172; // rax
  struct MemoryBrokerClerkList *v173; // rcx
  int v174; // eax
  __int64 v175; // rcx
  const wchar_t *v176; // rax
  __int64 v177; // rtt
  _QWORD *v178; // rbx
  __int64 v179; // rax
  _QWORD *v180; // rbx
  __int64 v181; // rtt
  volatile signed __int64 **v182; // r8
  char *v183; // r8
  __int64 v184; // rdi
  __int64 v185; // r8
  __int64 v186; // rcx
  DirtyPageMgr *v187; // rcx
  signed __int64 v188; // rax
  int v189; // eax
  __int64 v190; // rcx
  char *v191; // r9
  char *v192; // r9
  char *v193; // r9
  char *v194; // r9
  __int64 v195; // r15
  int v196; // edi
  unsigned __int64 v197; // rbx
  _DWORD *v198; // rcx
  signed __int32 v199[8]; // [rsp+0h] [rbp-100h] BYREF
  unsigned __int16 *v200; // [rsp+38h] [rbp-C8h]
  __int64 v201; // [rsp+40h] [rbp-C0h]
  struct MemoryBrokerClerkList *v202; // [rsp+48h] [rbp-B8h]
  __int64 v203; // [rsp+50h] [rbp-B0h]
  __int64 v204; // [rsp+58h] [rbp-A8h]
  __int128 v205; // [rsp+60h] [rbp-A0h]
  struct MemoryBrokerClerkList *v206; // [rsp+70h] [rbp-90h]
  __int64 v207; // [rsp+78h] [rbp-88h]
  int v208; // [rsp+80h] [rbp-80h]
  __int128 v209; // [rsp+88h] [rbp-78h] BYREF
  struct MemoryNodeList *v210; // [rsp+98h] [rbp-68h]
  __int64 v211; // [rsp+A0h] [rbp-60h]
  int v212; // [rsp+A8h] [rbp-58h]
  LARGE_INTEGER PerformanceCount; // [rsp+B0h] [rbp-50h] BYREF
  LARGE_INTEGER v214; // [rsp+B8h] [rbp-48h] BYREF
  LARGE_INTEGER v215; // [rsp+C0h] [rbp-40h] BYREF
  LARGE_INTEGER v216; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v217; // [rsp+D0h] [rbp-30h]
  __int64 v218; // [rsp+D8h] [rbp-28h]
  __int64 v219; // [rsp+E0h] [rbp-20h]
  __int64 v220; // [rsp+E8h] [rbp-18h]
  __int64 v221; // [rsp+F0h] [rbp-10h]
  _BYTE v222[40]; // [rsp+F8h] [rbp-8h] BYREF
  char v223[8]; // [rsp+120h] [rbp+20h] BYREF
  int v224; // [rsp+128h] [rbp+28h]
  int v225; // [rsp+130h] [rbp+30h]
  _QWORD *v226; // [rsp+138h] [rbp+38h]
  char *v227; // [rsp+140h] [rbp+40h]
  __int64 v228; // [rsp+148h] [rbp+48h]
  _QWORD v229[2]; // [rsp+150h] [rbp+50h] BYREF
  char v230; // [rsp+160h] [rbp+60h] BYREF
  __int64 v231; // [rsp+370h] [rbp+270h]
  __int64 v232; // [rsp+378h] [rbp+278h]
  char v233; // [rsp+380h] [rbp+280h] BYREF
  int v234; // [rsp+381h] [rbp+281h]
  char v235[8]; // [rsp+390h] [rbp+290h] BYREF
  int v236; // [rsp+398h] [rbp+298h]
  int v237; // [rsp+3A0h] [rbp+2A0h]
  _QWORD *v238; // [rsp+3A8h] [rbp+2A8h]
  char *v239; // [rsp+3B0h] [rbp+2B0h]
  __int64 v240; // [rsp+3B8h] [rbp+2B8h]
  _QWORD v241[2]; // [rsp+3C0h] [rbp+2C0h] BYREF
  char v242; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int64 v243; // [rsp+5E0h] [rbp+4E0h]
  __int64 v244; // [rsp+5E8h] [rbp+4E8h]
  __int64 v245; // [rsp+5F0h] [rbp+4F0h] BYREF
  __int16 v246; // [rsp+5F8h] [rbp+4F8h]
  char v247[8]; // [rsp+600h] [rbp+500h] BYREF
  int v248; // [rsp+608h] [rbp+508h]
  int v249; // [rsp+610h] [rbp+510h]
  _QWORD *v250; // [rsp+618h] [rbp+518h]
  char *v251; // [rsp+620h] [rbp+520h]
  __int64 v252; // [rsp+628h] [rbp+528h]
  _QWORD v253[2]; // [rsp+630h] [rbp+530h] BYREF
  char v254; // [rsp+640h] [rbp+540h] BYREF
  __int64 v255; // [rsp+850h] [rbp+750h]
  __int64 v256; // [rsp+858h] [rbp+758h]
  __int64 v257; // [rsp+860h] [rbp+760h] BYREF
  __int16 v258; // [rsp+868h] [rbp+768h]
  char v259[8]; // [rsp+870h] [rbp+770h] BYREF
  int v260; // [rsp+878h] [rbp+778h]
  int v261; // [rsp+880h] [rbp+780h]
  _QWORD *v262; // [rsp+888h] [rbp+788h]
  char *v263; // [rsp+890h] [rbp+790h]
  __int64 v264; // [rsp+898h] [rbp+798h]
  _QWORD v265[2]; // [rsp+8A0h] [rbp+7A0h] BYREF
  char v266; // [rsp+8B0h] [rbp+7B0h] BYREF
  __int64 v267; // [rsp+AC0h] [rbp+9C0h]
  __int64 v268; // [rsp+AC8h] [rbp+9C8h]
  __int64 v269; // [rsp+AD0h] [rbp+9D0h] BYREF
  __int16 v270; // [rsp+AD8h] [rbp+9D8h]
  char v271[8]; // [rsp+AE0h] [rbp+9E0h] BYREF
  int v272; // [rsp+AE8h] [rbp+9E8h]
  int v273; // [rsp+AF0h] [rbp+9F0h]
  _QWORD *v274; // [rsp+AF8h] [rbp+9F8h]
  char *v275; // [rsp+B00h] [rbp+A00h]
  __int64 v276; // [rsp+B08h] [rbp+A08h]
  _QWORD v277[2]; // [rsp+B10h] [rbp+A10h] BYREF
  char v278; // [rsp+B20h] [rbp+A20h] BYREF
  __int64 v279; // [rsp+D30h] [rbp+C30h]
  __int64 v280; // [rsp+D38h] [rbp+C38h]
  __int64 v281; // [rsp+D40h] [rbp+C40h] BYREF
  __int16 v282; // [rsp+D48h] [rbp+C48h]
  char v283[8]; // [rsp+D50h] [rbp+C50h] BYREF
  int v284; // [rsp+D58h] [rbp+C58h]
  int v285; // [rsp+D60h] [rbp+C60h]
  _QWORD *v286; // [rsp+D68h] [rbp+C68h]
  char *v287; // [rsp+D70h] [rbp+C70h]
  __int64 v288; // [rsp+D78h] [rbp+C78h]
  _QWORD v289[2]; // [rsp+D80h] [rbp+C80h] BYREF
  char v290; // [rsp+D90h] [rbp+C90h] BYREF
  __int64 v291; // [rsp+FA0h] [rbp+EA0h]
  __int64 v292; // [rsp+FA8h] [rbp+EA8h]
  signed __int64 v293; // [rsp+FB0h] [rbp+EB0h] BYREF
  __int16 v294; // [rsp+FB8h] [rbp+EB8h]
  char v295[8]; // [rsp+FC0h] [rbp+EC0h] BYREF
  int v296; // [rsp+FC8h] [rbp+EC8h]
  int v297; // [rsp+FD0h] [rbp+ED0h]
  _QWORD *v298; // [rsp+FD8h] [rbp+ED8h]
  char *v299; // [rsp+FE0h] [rbp+EE0h]
  __int64 v300; // [rsp+FE8h] [rbp+EE8h]
  _QWORD v301[2]; // [rsp+FF0h] [rbp+EF0h] BYREF
  char v302; // [rsp+1000h] [rbp+F00h] BYREF
  __int64 v303; // [rsp+1210h] [rbp+1110h]
  __int64 v304; // [rsp+1218h] [rbp+1118h]
  signed __int64 v305; // [rsp+1220h] [rbp+1120h] BYREF
  __int16 v306; // [rsp+1228h] [rbp+1128h]
  char v307[8]; // [rsp+1230h] [rbp+1130h] BYREF
  int v308; // [rsp+1238h] [rbp+1138h]
  int v309; // [rsp+1240h] [rbp+1140h]
  _QWORD *v310; // [rsp+1248h] [rbp+1148h]
  char *v311; // [rsp+1250h] [rbp+1150h]
  __int64 v312; // [rsp+1258h] [rbp+1158h]
  _QWORD v313[2]; // [rsp+1260h] [rbp+1160h] BYREF
  char v314; // [rsp+1270h] [rbp+1170h] BYREF
  __int64 v315; // [rsp+1480h] [rbp+1380h]
  __int64 v316; // [rsp+1488h] [rbp+1388h]
  __int64 v317; // [rsp+1490h] [rbp+1390h] BYREF
  char v318[8]; // [rsp+14A0h] [rbp+13A0h] BYREF
  int v319; // [rsp+14A8h] [rbp+13A8h]
  int v320; // [rsp+14B0h] [rbp+13B0h]
  _QWORD *v321; // [rsp+14B8h] [rbp+13B8h]
  char *v322; // [rsp+14C0h] [rbp+13C0h]
  __int64 v323; // [rsp+14C8h] [rbp+13C8h]
  _QWORD v324[2]; // [rsp+14D0h] [rbp+13D0h] BYREF
  char v325; // [rsp+14E0h] [rbp+13E0h] BYREF
  __int64 v326; // [rsp+16F0h] [rbp+15F0h]
  __int64 v327; // [rsp+16F8h] [rbp+15F8h]
  __int64 v328; // [rsp+1700h] [rbp+1600h] BYREF
  char v329[8]; // [rsp+1710h] [rbp+1610h] BYREF
  int v330; // [rsp+1718h] [rbp+1618h]
  int v331; // [rsp+1720h] [rbp+1620h]
  _QWORD *v332; // [rsp+1728h] [rbp+1628h]
  char *v333; // [rsp+1730h] [rbp+1630h]
  __int64 v334; // [rsp+1738h] [rbp+1638h]
  _QWORD v335[2]; // [rsp+1740h] [rbp+1640h] BYREF
  char v336; // [rsp+1750h] [rbp+1650h] BYREF
  __int64 v337; // [rsp+1960h] [rbp+1860h]
  __int64 v338; // [rsp+1968h] [rbp+1868h]
  __int64 v339; // [rsp+1970h] [rbp+1870h] BYREF
  char v340[8]; // [rsp+1980h] [rbp+1880h] BYREF
  int v341; // [rsp+1988h] [rbp+1888h]
  int v342; // [rsp+1990h] [rbp+1890h]
  _QWORD *v343; // [rsp+1998h] [rbp+1898h]
  char *v344; // [rsp+19A0h] [rbp+18A0h]
  __int64 v345; // [rsp+19A8h] [rbp+18A8h]
  _QWORD v346[2]; // [rsp+19B0h] [rbp+18B0h] BYREF
  char v347; // [rsp+19C0h] [rbp+18C0h] BYREF
  __int64 v348; // [rsp+1BD0h] [rbp+1AD0h]
  __int64 v349; // [rsp+1BD8h] [rbp+1AD8h]
  __int64 v350; // [rsp+1BE0h] [rbp+1AE0h] BYREF
  char v351[8]; // [rsp+1BF0h] [rbp+1AF0h] BYREF
  int v352; // [rsp+1BF8h] [rbp+1AF8h]
  int v353; // [rsp+1C00h] [rbp+1B00h]
  _QWORD *v354; // [rsp+1C08h] [rbp+1B08h]
  char *v355; // [rsp+1C10h] [rbp+1B10h]
  __int64 v356; // [rsp+1C18h] [rbp+1B18h]
  _QWORD v357[2]; // [rsp+1C20h] [rbp+1B20h] BYREF
  char v358; // [rsp+1C30h] [rbp+1B30h] BYREF
  __int64 v359; // [rsp+1E40h] [rbp+1D40h]
  __int64 v360; // [rsp+1E48h] [rbp+1D48h]
  __int64 v361; // [rsp+1E50h] [rbp+1D50h] BYREF
  char v362[8]; // [rsp+1E60h] [rbp+1D60h] BYREF
  int v363; // [rsp+1E68h] [rbp+1D68h]
  int v364; // [rsp+1E70h] [rbp+1D70h]
  _QWORD *v365; // [rsp+1E78h] [rbp+1D78h]
  char *v366; // [rsp+1E80h] [rbp+1D80h]
  __int64 v367; // [rsp+1E88h] [rbp+1D88h]
  _QWORD v368[2]; // [rsp+1E90h] [rbp+1D90h] BYREF
  char v369; // [rsp+1EA0h] [rbp+1DA0h] BYREF
  __int64 v370; // [rsp+20B0h] [rbp+1FB0h]
  __int64 v371; // [rsp+20B8h] [rbp+1FB8h]
  __int64 v372; // [rsp+20C0h] [rbp+1FC0h] BYREF
  wchar_t v373[12]; // [rsp+20D0h] [rbp+1FD0h] BYREF

  v219 = -2;
  TotalPagesCommitted = MemoryNode::GetTotalPagesCommitted();
  v218 = TotalPagesCommitted;
  v89 = TotalPagesCommitted - qword_10319A0B8;
  if ( qword_10319A0B8 > TotalPagesCommitted )
    v89 = qword_10319A0B8 - TotalPagesCommitted;
  v217 = v89;
  TotalPagesFree = MemoryNode::GetTotalPagesFree();
  v91 = qword_10317B628;
  v92 = 0;
  v93 = 0;
  do
    v92 += BPool::HashedCount(v91, v93++);
  while ( (unsigned int)v93 <= *((_DWORD *)v91 + 192) );
  TotalPagesReserved = MemoryNode::GetTotalPagesReserved();
  if ( TotalPagesReserved < 0 )
    TotalPagesReserved = 0;
  v95 = TotalPagesCommitted - v92 - TotalPagesFree;
  if ( v95 < 0 )
    v95 = 0;
  if ( CommonGlobalState::m_PerfCountersEnabled )
  {
    v96 = 8 * v92;
    v97 = 0;
    v98 = 0;
    if ( pCounterLookupBlocks )
      v98 = (char *)pCounterLookupBlocks + 38912;
    if ( v98 && *(_QWORD *)v98 )
    {
      *(_QWORD *)(*(_QWORD *)v98 + 16LL) = v96;
      v97 = 1;
    }
    if ( (g_XeSqlMinPkg_enabledBitmap & 0x80u) != 0 && v97 )
    {
      v308 = 0x10000;
      v309 = 0;
      v310 = v313;
      v311 = &v314;
      v315 = 0;
      v312 = 0;
      v316 = 0;
      v313[0] = &v317;
      v313[1] = 8;
      v317 = v96;
      XeSqlPkg::memory_manager_database_cache_memory::Publish((XeSqlPkg::memory_manager_database_cache_memory *)v307);
    }
  }
  if ( CommonGlobalState::m_PerfCountersEnabled )
  {
    v99 = 0;
    v100 = 0;
    if ( pCounterLookupBlocks )
      v100 = (char *)pCounterLookupBlocks + 38912;
    if ( v100 && *(_QWORD *)v100 )
    {
      *(_QWORD *)(*(_QWORD *)v100 + 24LL) = 8 * TotalPagesFree;
      v99 = 1;
    }
    if ( (g_XeSqlMinPkg_enabledBitmap & 0x100) != 0 && v99 )
    {
      v319 = 0x10000;
      v320 = 0;
      v321 = v324;
      v322 = &v325;
      v326 = 0;
      v323 = 0;
      v327 = 0;
      v324[0] = &v328;
      v324[1] = 8;
      v328 = 8 * TotalPagesFree;
      XeSqlPkg::memory_manager_free_memory::Publish((XeSqlPkg::memory_manager_free_memory *)v318);
    }
  }
  if ( CommonGlobalState::m_PerfCountersEnabled )
  {
    v101 = 8 * TotalPagesReserved;
    v102 = 0;
    v103 = 0;
    if ( pCounterLookupBlocks )
      v103 = (char *)pCounterLookupBlocks + 38912;
    if ( v103 && *(_QWORD *)v103 )
    {
      *(_QWORD *)(*(_QWORD *)v103 + 112LL) = v101;
      v102 = 1;
    }
    if ( (g_XeSqlMinPkg_enabledBitmap & 0x200) != 0 && v102 )
    {
      v330 = 0x10000;
      v331 = 0;
      v332 = v335;
      v333 = &v336;
      v337 = 0;
      v334 = 0;
      v338 = 0;
      v335[0] = &v339;
      v335[1] = 8;
      v339 = v101;
      XeSqlPkg::memory_manager_reserved_server_memory::Publish((XeSqlPkg::memory_manager_reserved_server_memory *)v329);
    }
  }
  if ( CommonGlobalState::m_PerfCountersEnabled )
  {
    v104 = 8 * v95;
    v105 = 0;
    v106 = 0;
    if ( pCounterLookupBlocks )
      v106 = (char *)pCounterLookupBlocks + 38912;
    if ( v106 && *(_QWORD *)v106 )
    {
      *(_QWORD *)(*(_QWORD *)v106 + 128LL) = v104;
      v105 = 1;
    }
    if ( (g_XeSqlMinPkg_enabledBitmap & 0x400) != 0 && v105 )
    {
      v341 = 0x10000;
      v342 = 0;
      v343 = v346;
      v344 = &v347;
      v348 = 0;
      v345 = 0;
      v349 = 0;
      v346[0] = &v350;
      v346[1] = 8;
      v350 = v104;
      XeSqlPkg::memory_manager_stolen_server_memory::Publish((XeSqlPkg::memory_manager_stolen_server_memory *)v340);
    }
  }
  if ( CommonGlobalState::m_PerfCountersEnabled )
  {
    v107 = 0;
    v108 = 0;
    if ( pCounterLookupBlocks )
      v108 = (char *)pCounterLookupBlocks + 38912;
    if ( v108 && *(_QWORD *)v108 )
    {
      *(_QWORD *)(*(_QWORD *)v108 + 152LL) = 8 * MemoryNode_MemoryTargetPages;
      v107 = 1;
    }
    if ( (g_XeSqlMinPkg_enabledBitmap & 0x800) != 0 && v107 )
    {
      v352 = 0x10000;
      v353 = 0;
      v354 = v357;
      v355 = &v358;
      v359 = 0;
      v356 = 0;
      v360 = 0;
      v357[0] = &v361;
      v357[1] = 8;
      v361 = 8 * MemoryNode_MemoryTargetPages;
      XeSqlPkg::memory_manager_target_server_memory::Publish((XeSqlPkg::memory_manager_target_server_memory *)v351);
    }
  }
  if ( CommonGlobalState::m_PerfCountersEnabled )
  {
    v109 = 0;
    v110 = 0;
    if ( pCounterLookupBlocks )
      v110 = (char *)pCounterLookupBlocks + 38912;
    if ( v110 && *(_QWORD *)v110 )
    {
      *(_QWORD *)(*(_QWORD *)v110 + 160LL) = 8 * TotalPagesCommitted;
      v109 = 1;
    }
    if ( (g_XeSqlMinPkg_enabledBitmap & 0x1000) != 0 && v109 )
    {
      v363 = 0x10000;
      v364 = 0;
      v365 = v368;
      v366 = &v369;
      v370 = 0;
      v367 = 0;
      v371 = 0;
      v368[0] = &v372;
      v368[1] = 8;
      v372 = 8 * TotalPagesCommitted;
      XeSqlPkg::memory_manager_total_server_memory::Publish((XeSqlPkg::memory_manager_total_server_memory *)v362);
    }
  }
  if ( CommonGlobalState::m_PerfCountersEnabled )
  {
    v111 = xmmword_103199FF0;
    v203 = *(_QWORD *)(xmmword_103199FF0 + 256);
    _InterlockedOr(v199, 0);
    v200 = *(unsigned __int16 **)(v111 + 192);
    v112 = 0;
    if ( pCounterLookupBlocks )
      v112 = (char *)pCounterLookupBlocks + 38912;
    if ( v112 && *(_QWORD *)v112 )
      *(_QWORD *)(*(_QWORD *)v112 + 136LL) = 8 * ((_QWORD)v200 + *(_QWORD *)(xmmword_103199FF0 + 1520) - v203);
  }
  SOS_NodeEnumIncludeUninitializedNodes::SOS_NodeEnumIncludeUninitializedNodes((SOS_NodeEnumIncludeUninitializedNodes *)v222);
  v113 = 0;
  v114 = 0;
  v201 = 0;
  v115 = 0;
  v203 = 0;
  v116 = 0x8000000000000000uLL;
  while ( 1 )
  {
    Next = SOS_NodeEnumIncludeUninitializedNodes::GetNext(
             (SOS_NodeEnumIncludeUninitializedNodes *)v222,
             (struct SOS_Node *)v113);
    v200 = (unsigned __int16 *)Next;
    if ( Next )
    {
      do
      {
        if ( (*((_BYTE *)Next + 1568) & 0x10) == 0 )
          break;
        Next = SOS_NodeEnumIncludeUninitializedNodes::GetNext((SOS_NodeEnumIncludeUninitializedNodes *)v222, Next);
      }
      while ( Next );
      v200 = (unsigned __int16 *)Next;
    }
    if ( !Next )
      break;
    if ( *((_WORD *)Next + 80) )
    {
      v118 = 0;
    }
    else
    {
      v0 = *((double *)Next + 125) * 1.0e10;
      v1 = 0;
      if ( v0 >= 9.223372036854776e18 )
      {
        v0 = v0 - 9.223372036854776e18;
        if ( v0 < 9.223372036854776e18 )
          v1 = 0x8000000000000000uLL;
      }
      v118 = 0;
      if ( CommonGlobalState::m_PerfCountersEnabled )
      {
        v2 = 0;
        if ( pCounterLookupBlocks )
          v2 = (_QWORD **)((char *)pCounterLookupBlocks + 38912);
        if ( v2 && *v2 )
          **v2 = v1 + (unsigned int)(int)v0;
      }
    }
    MemoryBrokerClerks = ResourceMonitor::GetMemoryBrokerClerks((struct SOS_Node *)((char *)Next + 944));
    v202 = MemoryBrokerClerks;
    v120 = 0;
    v205 = 0;
    v207 = 0;
    v208 = 0;
    v206 = MemoryBrokerClerks;
    *(_QWORD *)&v205 = TList<MemoryBrokerClerkList,MemoryBrokerClerk,8,TListSLock>::GetHead(MemoryBrokerClerks);
    *((_QWORD *)&v205 + 1) = TList<SOS_Node,SOS_DispatcherPoolBase,8,TListSLock>::GetTail(MemoryBrokerClerks);
    for ( i = 0; ; ++i )
    {
      QuadPart = 0;
      if ( !v120 )
      {
        QuadPart = (DirtyPageMgr *)v205;
        goto LABEL_67;
      }
      if ( !(_QWORD)v205 )
        goto LABEL_67;
      if ( (_QWORD)v205 == *((_QWORD *)&v205 + 1) )
        break;
      v163 = (volatile signed __int64 *)((char *)MemoryBrokerClerks + 16);
      UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)v163 || _InterlockedCompareExchange64(v163, UniqueThread_low, 0) )
      {
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v170 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v170 && *(_QWORD *)(v170 + 272) == v170 )
            v118 = *(_QWORD *)(v170 + 256);
          if ( v118 )
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
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(v163, UniqueThread_low);
        else
          Spinlock<19,1,268435714>::SpinToAcquireOptimistic(v163, v118, UniqueThread_low);
        if ( v118 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v214);
            v171 = (DirtyPageMgr *)v214.QuadPart;
          }
          else
          {
            v171 = MEMORY[0x7FFE0008];
          }
          v172 = 0;
          if ( v171 >= QuadPart )
            v172 = v171 - QuadPart;
          *(_QWORD *)(v118 + 3192) += v172;
        }
      }
      v165 = (struct MemoryBrokerClerkList *)*((_QWORD *)v120 + 2);
      MemoryBrokerClerks = v202;
      QuadPart = 0;
      if ( v165 != v202 )
      {
        if ( v165 )
          QuadPart = (struct MemoryBrokerClerkList *)((char *)v165 - 8);
        if ( QuadPart )
        {
          while ( 1 )
          {
            v166 = *((_DWORD *)QuadPart + 8);
            if ( v166 )
            {
              while ( v166 != _InterlockedCompareExchange((volatile signed __int32 *)QuadPart + 8, v166 + 1, v166) )
              {
                _mm_pause();
                v166 = *((_DWORD *)QuadPart + 8);
                if ( !v166 )
                  goto LABEL_330;
              }
              if ( v166 != -1 )
                break;
            }
LABEL_330:
            v173 = (struct MemoryBrokerClerkList *)*((_QWORD *)QuadPart + 2);
            QuadPart = 0;
            if ( v173 != MemoryBrokerClerks )
            {
              if ( v173 )
                QuadPart = (struct MemoryBrokerClerkList *)((char *)v173 - 8);
              if ( QuadPart )
                continue;
            }
            break;
          }
        }
      }
      if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v174 = rand();
        v175 = (unsigned int)(5 * (v174 / 5));
        if ( v174 == (_DWORD)v175 )
          Spinlock<19,1,268435714>::UpdateStatSnapshot(v175);
      }
      *v163 = 0;
      *(_QWORD *)&v205 = QuadPart;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v120 + 8, 0xFFFFFFFF) == 1 )
      {
        if ( *((_QWORD *)v120 + 2) )
          TList<SOS_Node,SOS_DispatcherPoolBase,8,TListSLock>::RemoveElem(*((_QWORD *)v120 + 3), v120);
        v167 = *(_QWORD *)v120;
        v168 = v120;
        goto LABEL_127;
      }
LABEL_67:
      v120 = QuadPart;
      if ( !QuadPart )
        goto LABEL_68;
      v133 = *((double *)QuadPart + 5) * 1.0e10;
      v134 = 0;
      if ( v133 >= 9.223372036854776e18 )
      {
        v133 = v133 - 9.223372036854776e18;
        if ( v133 < 9.223372036854776e18 )
          v134 = 0x8000000000000000uLL;
      }
      v135 = v134 + (unsigned int)(int)v133;
      if ( !(unsigned int)PerfmonManager::SetInstanceCounterValue((PerfmonManager *)&ResourceStr, 0, 8u, v135, i) )
      {
        v176 = (const wchar_t *)(*(__int64 (__fastcall **)(DirtyPageMgr *))(*(_QWORD *)QuadPart + 40LL))(QuadPart);
        PerfmonManager::AddInstance((PerfmonManager *)&ResourceStr, 0, v176, i);
        PerfmonManager::SetInstanceCounterValue((PerfmonManager *)&ResourceStr, 0, 8u, v135, i);
      }
      if ( CommonGlobalState::m_PerfCountersEnabled )
      {
        v137 = (*(__int64 (__fastcall **)(DirtyPageMgr *))(*(_QWORD *)QuadPart + 32LL))(QuadPart);
        if ( i < 0x10000 )
        {
          v136 = (signed __int64)*(&pCounterLookupBlocks + ((unsigned __int64)i >> 8));
          if ( v136 )
          {
            v138 = (__int64 *)(v136 + 8LL * (unsigned __int8)i);
            if ( v138 )
            {
              v139 = *v138;
              if ( v139 )
              {
                v136 = *(_QWORD *)(v139 + 16);
                if ( v136 != _InterlockedCompareExchange64((volatile signed __int64 *)(v139 + 16), v137, v136) )
                {
                  _m_prefetchw((const void *)(v139 + 16));
                  do
                  {
                    _mm_pause();
                    v136 = *(_QWORD *)(v139 + 16);
                  }
                  while ( v136 != _InterlockedCompareExchange64((volatile signed __int64 *)(v139 + 16), v137, v136) );
                }
                if ( (g_fObjectHasTotalInstance & 1) != 0 && pCounterLookupBlocks && *(_QWORD *)pCounterLookupBlocks )
                  v137 = _InterlockedExchangeAdd64(
                           (volatile signed __int64 *)(*(_QWORD *)pCounterLookupBlocks + 16LL),
                           v137 - v136);
              }
            }
          }
        }
        if ( CommonGlobalState::m_PerfCountersEnabled )
        {
          v140 = (*(__int64 (__fastcall **)(DirtyPageMgr *, signed __int64, signed __int64))(*(_QWORD *)QuadPart + 16LL))(
                   QuadPart,
                   v136,
                   v137);
          if ( i < 0x10000 )
          {
            v141 = (__int64)*(&pCounterLookupBlocks + ((unsigned __int64)i >> 8));
            if ( v141 )
            {
              v142 = (__int64 **)(v141 + 8LL * (unsigned __int8)i);
              if ( v142 )
              {
                v143 = *v142;
                if ( v143 )
                {
                  v144 = *v143;
                  v145 = *v143;
                  if ( v145 != _InterlockedCompareExchange64(v143, v140, *v143) )
                  {
                    _m_prefetchw(v143);
                    do
                    {
                      _mm_pause();
                      v144 = *v143;
                      v177 = *v143;
                    }
                    while ( v177 != _InterlockedCompareExchange64(v143, v140, *v143) );
                  }
                  if ( (g_fObjectHasTotalInstance & 1) != 0 && pCounterLookupBlocks && *(_QWORD *)pCounterLookupBlocks )
                    _InterlockedExchangeAdd64(*(volatile signed __int64 **)pCounterLookupBlocks, v140 - v144);
                }
              }
            }
          }
        }
      }
      v146 = *((double *)QuadPart + 6) * 1.0e10;
      v147 = 0;
      if ( v146 >= 9.223372036854776e18 )
      {
        v146 = v146 - 9.223372036854776e18;
        if ( v146 < 9.223372036854776e18 )
          v147 = 0x8000000000000000uLL;
      }
      v148 = v147 + (unsigned int)(int)v146;
      if ( CommonGlobalState::m_PerfCountersEnabled )
      {
        if ( i < 0x10000 )
        {
          v149 = (__int64)*(&pCounterLookupBlocks + ((unsigned __int64)i >> 8));
          if ( v149 )
          {
            v150 = (__int64 *)(v149 + 8LL * (unsigned __int8)i);
            if ( v150 )
            {
              v151 = *v150;
              if ( v151 )
              {
                v152 = *(_QWORD *)(v151 + 24);
                if ( v152 != _InterlockedCompareExchange64((volatile signed __int64 *)(v151 + 24), v148, v152) )
                {
                  _m_prefetchw((const void *)(v151 + 24));
                  do
                  {
                    _mm_pause();
                    v152 = *(_QWORD *)(v151 + 24);
                  }
                  while ( v152 != _InterlockedCompareExchange64((volatile signed __int64 *)(v151 + 24), v148, v152) );
                }
                if ( (g_fObjectHasTotalInstance & 1) != 0 && pCounterLookupBlocks && *(_QWORD *)pCounterLookupBlocks )
                  _InterlockedExchangeAdd64(
                    (volatile signed __int64 *)(*(_QWORD *)pCounterLookupBlocks + 24LL),
                    v148 - v152);
              }
            }
          }
        }
        if ( CommonGlobalState::m_PerfCountersEnabled )
        {
          v153 = *((_QWORD *)QuadPart + 8);
          if ( i < 0x10000 )
          {
            v154 = (__int64)*(&pCounterLookupBlocks + ((unsigned __int64)i >> 8));
            if ( v154 )
            {
              v155 = (__int64 *)(v154 + 8LL * (unsigned __int8)i);
              if ( v155 )
              {
                v156 = *v155;
                if ( v156 )
                {
                  v157 = *(_QWORD *)(v156 + 32);
                  if ( v157 != _InterlockedCompareExchange64((volatile signed __int64 *)(v156 + 32), v153, v157) )
                  {
                    _m_prefetchw((const void *)(v156 + 32));
                    do
                    {
                      _mm_pause();
                      v157 = *(_QWORD *)(v156 + 32);
                    }
                    while ( v157 != _InterlockedCompareExchange64((volatile signed __int64 *)(v156 + 32), v153, v157) );
                  }
                  if ( (g_fObjectHasTotalInstance & 1) != 0 && pCounterLookupBlocks && *(_QWORD *)pCounterLookupBlocks )
                    _InterlockedExchangeAdd64(
                      (volatile signed __int64 *)(*(_QWORD *)pCounterLookupBlocks + 32LL),
                      v153 - v157);
                }
              }
            }
          }
          if ( CommonGlobalState::m_PerfCountersEnabled )
          {
            v158 = *((_QWORD *)QuadPart + 9);
            if ( i < 0x10000 )
            {
              v159 = (__int64)*(&pCounterLookupBlocks + ((unsigned __int64)i >> 8));
              if ( v159 )
              {
                v160 = (__int64 *)(v159 + 8LL * (unsigned __int8)i);
                if ( v160 )
                {
                  v161 = *v160;
                  if ( v161 )
                  {
                    v162 = *(_QWORD *)(v161 + 40);
                    if ( v162 != _InterlockedCompareExchange64((volatile signed __int64 *)(v161 + 40), v158, v162) )
                    {
                      _m_prefetchw((const void *)(v161 + 40));
                      do
                      {
                        _mm_pause();
                        v162 = *(_QWORD *)(v161 + 40);
                      }
                      while ( v162 != _InterlockedCompareExchange64((volatile signed __int64 *)(v161 + 40), v158, v162) );
                    }
                    if ( (g_fObjectHasTotalInstance & 1) != 0 && pCounterLookupBlocks && *(_QWORD *)pCounterLookupBlocks )
                      _InterlockedExchangeAdd64(
                        (volatile signed __int64 *)(*(_QWORD *)pCounterLookupBlocks + 40LL),
                        v158 - v162);
                  }
                }
              }
            }
          }
        }
      }
      v118 = 0;
    }
    v169 = (volatile signed __int32 *)v205;
    *(_QWORD *)&v205 = 0;
    if ( _InterlockedExchangeAdd(v169 + 8, 0xFFFFFFFF) != 1 )
      goto LABEL_67;
    if ( !*((_QWORD *)v169 + 2) )
    {
      v167 = *(_QWORD *)v169;
      v168 = (DirtyPageMgr *)v169;
LABEL_127:
      (*(void (__fastcall **)(DirtyPageMgr *))(v167 + 8))(v168);
      goto LABEL_67;
    }
    TList<SOS_Node,SOS_DispatcherPoolBase,8,TListSLock>::RemoveElem(*((_QWORD *)v169 + 3), v169);
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v169 + 8LL))(v169);
LABEL_68:
    ClientProcessGlobals = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
    v113 = v200;
    DefaultMemoryClerksForNode = PerProcessGlobals::GetDefaultMemoryClerksForNode(ClientProcessGlobals, v200[80]);
    SOS_OS::GetClientProcessGlobals();
    v125 = DefaultMemoryClerksForNode[18];
    v126 = *((_QWORD *)v125 + 190) + v201;
    v202 = (struct MemoryBrokerClerkList *)*((_QWORD *)v125 + 32);
    _InterlockedOr(v199, 0);
    v200 = (unsigned __int16 *)*((_QWORD *)v125 + 24);
    v114 = (__int64)v200 + v126 - (_QWORD)v202;
    v201 = v114;
    v127 = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
    v128 = PerProcessGlobals::GetDefaultMemoryClerksForNode(v127, v113[80]);
    SOS_OS::GetClientProcessGlobals();
    v129 = v128[8];
    v130 = *((_QWORD *)v129 + 190) + v203;
    v202 = (struct MemoryBrokerClerkList *)*((_QWORD *)v129 + 32);
    _InterlockedOr(v199, 0);
    v203 = *((_QWORD *)v129 + 24);
    v115 = v130 - (_QWORD)v202 + v203;
    v203 = v115;
    v131 = (_QWORD *)v205;
    if ( (_QWORD)v205 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v205 + 32), 0xFFFFFFFF) == 1 )
      {
        v178 = v131;
        if ( v131[2] )
        {
          TList<SOS_Node,SOS_DispatcherPoolBase,8,TListSLock>::RemoveElem(v131[3], v131);
          v179 = *v178;
          v131 = v178;
        }
        else
        {
          v179 = *v131;
        }
        (*(void (__fastcall **)(_QWORD *))(v179 + 8))(v131);
      }
      *(_QWORD *)&v205 = 0;
    }
    v132 = (_QWORD *)*((_QWORD *)&v205 + 1);
    if ( !*((_QWORD *)&v205 + 1) )
    {
LABEL_70:
      v206 = 0;
      continue;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v205 + 1) + 32LL), 0xFFFFFFFF) != 1 )
    {
LABEL_139:
      *((_QWORD *)&v205 + 1) = 0;
      goto LABEL_70;
    }
    v180 = v132;
    if ( !v132[2] )
    {
      (*(void (__fastcall **)(_QWORD *))(*v132 + 8LL))(v132);
      goto LABEL_139;
    }
    TList<SOS_Node,SOS_DispatcherPoolBase,8,TListSLock>::RemoveElem(v132[3], v132);
    (*(void (__fastcall **)(_QWORD *))(*v180 + 8LL))(v180);
    *((_QWORD *)&v205 + 1) = 0;
    v206 = 0;
  }
  v4 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
  if ( CommonGlobalState::m_PerfCountersEnabled )
  {
    v5 = 0;
    if ( pCounterLookupBlocks )
      v5 = (char *)pCounterLookupBlocks + 38912;
    if ( v5 && *(_QWORD *)v5 )
    {
      *(_QWORD *)(*(_QWORD *)v5 + 8LL) = 8 * v114;
      v4 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
    }
    if ( *v4 )
    {
      v6 = 0;
      if ( pCounterLookupBlocks )
        v6 = (char *)pCounterLookupBlocks + 38912;
      if ( v6 && *(_QWORD *)v6 )
        *(_QWORD *)(*(_QWORD *)v6 + 104LL) = 8 * v115;
    }
  }
  SOS_NodeEnumIncludeUninitializedNodes::~SOS_NodeEnumIncludeUninitializedNodes((SOS_NodeEnumIncludeUninitializedNodes *)v222);
  v7 = SOS_PublicGlobals::sm_isResourceManagerEnabled != 0 ? 0x380 : 0;
  v8 = *(__int64 *)((char *)&qword_10318B9C8 + v7);
  if ( v8 <= *(__int64 *)((char *)&qword_10318B9C0 + v7) )
    v8 = *(__int64 *)((char *)&qword_10318B9C0 + v7);
  v9 = *(__int64 *)((char *)&qword_10318B6D0 + v7);
  if ( v9 <= *(__int64 *)((char *)&qword_10318B6C8 + v7) )
    v9 = *(__int64 *)((char *)&qword_10318B6C8 + v7);
  v10 = 0x7FFFFFFFFFFFFFFFLL;
  if ( (unsigned __int64)v9 >> 63 == (unsigned __int64)v8 >> 63
    && (unsigned __int64)v9 >> 63 != (unsigned __int64)(v8 + v9) > 0x7FFFFFFFFFFFFFFFLL )
  {
    if ( v9 > 0 && v8 > 0 )
      v116 = 0x7FFFFFFFFFFFFFFFLL;
  }
  else
  {
    v116 = v8 + v9;
  }
  v11 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
  if ( CommonGlobalState::m_PerfCountersEnabled )
  {
    v12 = v116 * (__int128)8LL;
    v220 = *((_QWORD *)&v12 + 1);
    v13 = 8 * v116;
    if ( (v116 & 0x1000000000000000LL) != 0 )
    {
      if ( *((_QWORD *)&v12 + 1) != -1 )
        goto LABEL_386;
    }
    else
    {
      if ( !*((_QWORD *)&v12 + 1) )
        goto LABEL_164;
LABEL_386:
      v13 = 0x7FFFFFFFFFFFFFFFLL;
    }
LABEL_164:
    v14 = 0;
    if ( pCounterLookupBlocks )
      v14 = (char *)pCounterLookupBlocks + 38912;
    if ( v14 && *(_QWORD *)v14 )
    {
      *(_QWORD *)(*(_QWORD *)v14 + 80LL) = v13;
      v11 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
    }
  }
  if ( *v11 )
  {
    v15 = *(__int64 *)((char *)&qword_10318B9C8 + v7) + *(__int64 *)((char *)&qword_10318B6D0 + v7);
    v16 = v15 * (__int128)8LL;
    v221 = *((_QWORD *)&v16 + 1);
    if ( (v15 & 0x1000000000000000LL) != 0 )
      v17 = *((_QWORD *)&v16 + 1) == -1;
    else
      v17 = *((_QWORD *)&v16 + 1) == 0;
    if ( v17 )
      v10 = v16;
    v18 = 0;
    if ( pCounterLookupBlocks )
      v18 = (char *)pCounterLookupBlocks + 38912;
    if ( v18 && *(_QWORD *)v18 )
    {
      *(_QWORD *)(*(_QWORD *)v18 + 32LL) = v10;
      v11 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
    }
    if ( *v11 )
    {
      v19 = 0;
      if ( pCounterLookupBlocks )
        v19 = (char *)pCounterLookupBlocks + 38912;
      if ( v19 && *(_QWORD *)v19 )
      {
        *(_QWORD *)(*(_QWORD *)v19 + 96LL) = *(int *)((char *)&qword_10318B700[33] + v7 + 4);
        v11 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
      }
      if ( *v11 )
      {
        v20 = 0;
        if ( pCounterLookupBlocks )
          v20 = (char *)pCounterLookupBlocks + 38912;
        if ( v20 && *(_QWORD *)v20 )
        {
          *(_QWORD *)(*(_QWORD *)v20 + 88LL) = *(__int64 *)((char *)qword_10318B9D8 + v7)
                                             + *(int *)((char *)&qword_10318B700[37] + v7);
          v11 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
        }
        if ( *v11 )
        {
          v21 = 8 * LockManager::GetPageCount((LockManager *)theLockManager);
          v22 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
          if ( CommonGlobalState::m_PerfCountersEnabled )
          {
            v23 = 0;
            if ( pCounterLookupBlocks )
              v23 = (char *)pCounterLookupBlocks + 38912;
            if ( v23 && *(_QWORD *)v23 )
            {
              *(_QWORD *)(*(_QWORD *)v23 + 40LL) = v21;
              v22 = *(_BYTE **)&CommonGlobalState::m_PerfCountersEnabled;
            }
            if ( *v22 )
            {
              SqlManager = GetSqlManager();
              v25 = 8LL * CSqlMgr::CpagesInUse(SqlManager);
              if ( CommonGlobalState::m_PerfCountersEnabled )
              {
                v26 = 0;
                if ( pCounterLookupBlocks )
                  v26 = (char *)pCounterLookupBlocks + 38912;
                if ( v26 && *(_QWORD *)v26 )
                  *(_QWORD *)(*(_QWORD *)v26 + 120LL) = v25;
              }
            }
          }
        }
      }
    }
  }
  NodeList = MemoryNodeManager::GetNodeList(SOS_PublicGlobals::sm_MemoryNodeManager);
  v209 = 0;
  v211 = 0;
  v212 = 0;
  v210 = NodeList;
  *(_QWORD *)&v209 = TList<MemoryNodeList,MemoryNode,0,TListSLock>::GetHead(NodeList);
  *((_QWORD *)&v209 + 1) = TList<CBpNativeShuffleStatsList,CBpNativeShuffleStats,0,TListSLock>::GetTail(NodeList);
  v28 = 0;
  v201 = 0;
  v29 = 0;
  while ( 1 )
  {
    j = 0;
    if ( !v28 )
    {
      j = v209;
      goto LABEL_219;
    }
    v30 = v209;
    if ( (_QWORD)v209 )
      break;
LABEL_219:
    v201 = j;
    if ( !j )
      goto LABEL_279;
    v36 = *(_WORD *)(j + 128);
    v37 = v36;
    v38 = 1 << (v36 & 0x1F);
    if ( (v38 & SQLMemoryReport::sm_onlineNodes[(unsigned __int64)v36 >> 5]) == 0 )
    {
      _InterlockedOr(&SQLMemoryReport::sm_onlineNodes[(unsigned __int64)*(unsigned __int16 *)(j + 128) >> 5], v38);
      PrintStringW(v373, 0xAu, L"%03hu", v36);
      PerfmonManager::AddInstance((PerfmonManager *)&ResourceStr, 0x14u, v373, v36);
    }
    PagesCommitted = MemoryNode::GetPagesCommitted((MemoryNode *)j);
    v203 = PagesCommitted;
    v40 = BPool::HashedCount(qword_10317B628, v36);
    PagesFree = MemoryNode::GetPagesFree((MemoryNode *)j);
    PagesDecommitted = MemoryNode::GetPagesDecommitted((MemoryNode *)j);
    v43 = PagesCommitted - PagesFree - v40;
    if ( v43 < 0 )
      v43 = 0;
    if ( PagesDecommitted < 0 )
      PagesDecommitted = 0;
    v204 = PagesDecommitted;
    v29 = (unsigned __int16 *)((char *)v29 + PagesDecommitted);
    v200 = v29;
    if ( !CommonGlobalState::m_PerfCountersEnabled )
      goto LABEL_413;
    v44 = 8 * v40;
    _mm_lfence();
    v45 = 0;
    v46 = v37 >> 8;
    v47 = (__int64)*(&pCounterLookupBlocks + (v37 >> 8));
    if ( v47 )
    {
      v48 = (__int64 **)(v47 + 8LL * (unsigned __int8)v37 + 40960);
      if ( v48 )
      {
        if ( *v48 )
        {
          _mm_lfence();
          v49 = *v48;
          v50 = *v49;
          v51 = *v49;
          if ( v51 != _InterlockedCompareExchange64(v49, v44, *v49) )
          {
            _m_prefetchw(v49);
            do
            {
              _mm_pause();
              v50 = *v49;
              v181 = *v49;
            }
            while ( v181 != _InterlockedCompareExchange64(v49, v44, *v49) );
          }
          if ( (g_fObjectHasTotalInstance & 0x100000) != 0 )
          {
            v182 = 0;
            if ( pCounterLookupBlocks )
              v182 = (volatile signed __int64 **)((char *)pCounterLookupBlocks + 40960);
            if ( v182 && *v182 )
              _InterlockedExchangeAdd64(*v182, v44 - v50);
          }
          v45 = 1;
        }
      }
    }
    if ( (g_XeSqlMinPkg_enabledBitmap & 0x2000) != 0 && v45 )
    {
      v236 = 0x10000;
      v237 = 0;
      v238 = v241;
      v239 = &v242;
      v243 = 0;
      v240 = 0;
      v244 = 0;
      v241[0] = &v245;
      v241[1] = 10;
      v245 = 8 * v40;
      v246 = v37;
      XeSqlPkg::memory_node_database_node_memory::Publish((XeSqlPkg::memory_node_database_node_memory *)v235);
    }
    v28 = j;
    if ( !CommonGlobalState::m_PerfCountersEnabled )
      goto LABEL_389;
    v52 = 8 * PagesFree;
    _mm_lfence();
    v53 = 0;
    v54 = (__int64)*(&pCounterLookupBlocks + v46);
    if ( v54 )
    {
      v55 = (__int64 *)(v54 + 8LL * (unsigned __int8)v37 + 40960);
      if ( v55 )
      {
        if ( *v55 )
        {
          _mm_lfence();
          v56 = *v55;
          v57 = *(_QWORD *)(v56 + 8);
          if ( v57 != _InterlockedCompareExchange64((volatile signed __int64 *)(v56 + 8), v52, v57) )
          {
            _m_prefetchw((const void *)(v56 + 8));
            do
            {
              _mm_pause();
              v57 = *(_QWORD *)(v56 + 8);
            }
            while ( v57 != _InterlockedCompareExchange64((volatile signed __int64 *)(v56 + 8), v52, v57) );
          }
          if ( (g_fObjectHasTotalInstance & 0x100000) != 0 )
          {
            v183 = 0;
            if ( pCounterLookupBlocks )
              v183 = (char *)pCounterLookupBlocks + 40960;
            if ( v183 && *(_QWORD *)v183 )
              _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v183 + 8LL), v52 - v57);
          }
          v53 = 1;
        }
      }
    }
    if ( (g_XeSqlMinPkg_enabledBitmap & 0x4000) != 0 && v53 )
    {
      v248 = 0x10000;
      v249 = 0;
      v250 = v253;
      v251 = &v254;
      v255 = 0;
      v252 = 0;
      v256 = 0;
      v253[0] = &v257;
      v253[1] = 10;
      v257 = 8 * PagesFree;
      v258 = v37;
      XeSqlPkg::memory_node_free_node_memory::Publish((XeSqlPkg::memory_node_free_node_memory *)v247);
    }
    v28 = j;
    if ( !CommonGlobalState::m_PerfCountersEnabled )
    {
LABEL_389:
      v29 = v200;
      continue;
    }
    v58 = *(_QWORD *)(j + 96) + 1LL;
    v59 = PerfmonManager::SetInstanceCounterValue((PerfmonManager *)&ResourceStr, 0x14u, 0x10u, 8 * (v58 / 2), v37);
    if ( (g_XeSqlMinPkg_enabledBitmap & 0x8000) != 0 && v59 )
    {
      v260 = 0x10000;
      v261 = 0;
      v262 = v265;
      v263 = &v266;
      v267 = 0;
      v264 = 0;
      v268 = 0;
      v265[0] = &v269;
      v265[1] = 10;
      v269 = 8 * (v58 / 2);
      v270 = v37;
      XeSqlPkg::memory_node_foreign_node_memory::Publish((XeSqlPkg::memory_node_foreign_node_memory *)v259);
    }
    if ( !CommonGlobalState::m_PerfCountersEnabled )
    {
      v29 = v200;
LABEL_413:
      v28 = j;
      continue;
    }
    v60 = 8 * v43;
    _mm_lfence();
    v61 = 0;
    v62 = (__int64)*(&pCounterLookupBlocks + v46);
    if ( v62 )
    {
      v63 = (__int64 *)(v62 + 8LL * (unsigned __int8)v37 + 40960);
      if ( v63 )
      {
        if ( *v63 )
        {
          _mm_lfence();
          v64 = *v63;
          v65 = *(_QWORD *)(v64 + 24);
          if ( v65 != _InterlockedCompareExchange64((volatile signed __int64 *)(v64 + 24), v60, v65) )
          {
            _m_prefetchw((const void *)(v64 + 24));
            do
            {
              _mm_pause();
              v65 = *(_QWORD *)(v64 + 24);
            }
            while ( v65 != _InterlockedCompareExchange64((volatile signed __int64 *)(v64 + 24), v60, v65) );
          }
          if ( (g_fObjectHasTotalInstance & 0x100000) != 0 )
          {
            v191 = 0;
            if ( pCounterLookupBlocks )
              v191 = (char *)pCounterLookupBlocks + 40960;
            if ( v191 && *(_QWORD *)v191 )
              _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v191 + 24LL), v60 - v65);
          }
          v61 = 1;
        }
      }
    }
    if ( (g_XeSqlMinPkg_enabledBitmap & 0x10000) != 0 && v61 )
    {
      v272 = 0x10000;
      v273 = 0;
      v274 = v277;
      v275 = &v278;
      v279 = 0;
      v276 = 0;
      v280 = 0;
      v277[0] = &v281;
      v277[1] = 10;
      v281 = 8 * v43;
      v282 = v37;
      XeSqlPkg::memory_node_stolen_node_memory::Publish((XeSqlPkg::memory_node_stolen_node_memory *)v271);
    }
    v28 = j;
    if ( !CommonGlobalState::m_PerfCountersEnabled )
      goto LABEL_389;
    v66 = 8 * MemoryNode::GetLocalTargetPages((MemoryNode *)j);
    v67 = 0;
    _mm_lfence();
    v68 = (__int64)*(&pCounterLookupBlocks + v46);
    if ( v68 )
    {
      v69 = (__int64 *)(v68 + 8LL * (unsigned __int8)v37 + 40960);
      if ( v69 )
      {
        if ( *v69 )
        {
          _mm_lfence();
          v70 = *v69;
          v71 = *(_QWORD *)(v70 + 40);
          if ( v71 != _InterlockedCompareExchange64((volatile signed __int64 *)(v70 + 40), v66, v71) )
          {
            _m_prefetchw((const void *)(v70 + 40));
            do
            {
              _mm_pause();
              v71 = *(_QWORD *)(v70 + 40);
            }
            while ( v71 != _InterlockedCompareExchange64((volatile signed __int64 *)(v70 + 40), v66, v71) );
          }
          if ( (g_fObjectHasTotalInstance & 0x100000) != 0 )
          {
            v192 = 0;
            if ( pCounterLookupBlocks )
              v192 = (char *)pCounterLookupBlocks + 40960;
            if ( v192 && *(_QWORD *)v192 )
              _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v192 + 40LL), v66 - v71);
          }
          v67 = 1;
        }
      }
    }
    if ( (g_XeSqlMinPkg_enabledBitmap & 0x20000) != 0 && v67 )
    {
      v284 = 0x10000;
      v285 = 0;
      v286 = v289;
      v287 = &v290;
      v291 = 0;
      v288 = 0;
      v292 = 0;
      v289[0] = &v293;
      v289[1] = 10;
      v293 = v66;
      v294 = v37;
      XeSqlPkg::memory_node_target_node_memory::Publish((XeSqlPkg::memory_node_target_node_memory *)v283);
    }
    v28 = j;
    if ( !CommonGlobalState::m_PerfCountersEnabled )
      goto LABEL_389;
    v72 = 8 * v203;
    _mm_lfence();
    v73 = 0;
    v74 = (__int64)*(&pCounterLookupBlocks + v46);
    if ( v74 )
    {
      v75 = (__int64 *)(v74 + 8LL * (unsigned __int8)v37 + 40960);
      if ( v75 )
      {
        if ( *v75 )
        {
          _mm_lfence();
          v76 = *v75;
          v77 = *(_QWORD *)(v76 + 48);
          if ( v77 != _InterlockedCompareExchange64((volatile signed __int64 *)(v76 + 48), v72, v77) )
          {
            _m_prefetchw((const void *)(v76 + 48));
            do
            {
              _mm_pause();
              v77 = *(_QWORD *)(v76 + 48);
            }
            while ( v77 != _InterlockedCompareExchange64((volatile signed __int64 *)(v76 + 48), v72, v77) );
          }
          if ( (g_fObjectHasTotalInstance & 0x100000) != 0 )
          {
            v193 = 0;
            if ( pCounterLookupBlocks )
              v193 = (char *)pCounterLookupBlocks + 40960;
            if ( v193 && *(_QWORD *)v193 )
              _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v193 + 48LL), v72 - v77);
          }
          v73 = 1;
        }
      }
    }
    if ( (g_XeSqlMinPkg_enabledBitmap & 0x40000) != 0 && v73 )
    {
      v296 = 0x10000;
      v297 = 0;
      v298 = v301;
      v299 = &v302;
      v303 = 0;
      v300 = 0;
      v304 = 0;
      v301[0] = &v305;
      v301[1] = 10;
      v305 = v72;
      v306 = v37;
      XeSqlPkg::memory_node_total_node_memory::Publish((XeSqlPkg::memory_node_total_node_memory *)v295);
    }
    v28 = j;
    v29 = v200;
    if ( CommonGlobalState::m_PerfCountersEnabled )
    {
      v78 = 8 * v204;
      _mm_lfence();
      v79 = (__int64)*(&pCounterLookupBlocks + ((unsigned __int64)(unsigned __int16)v37 >> 8));
      v28 = j;
      if ( v79 )
      {
        v80 = (__int64 *)(v79 + 8LL * (unsigned __int8)v37 + 40960);
        if ( !v80 || !*v80 )
          goto LABEL_480;
        _mm_lfence();
        v81 = *v80;
        v82 = *(_QWORD *)(v81 + 32);
        if ( v82 != _InterlockedCompareExchange64((volatile signed __int64 *)(v81 + 32), v78, v82) )
        {
          _m_prefetchw((const void *)(v81 + 32));
          do
          {
            _mm_pause();
            v82 = *(_QWORD *)(v81 + 32);
          }
          while ( v82 != _InterlockedCompareExchange64((volatile signed __int64 *)(v81 + 32), v78, v82) );
        }
        if ( (g_fObjectHasTotalInstance & 0x100000) == 0 )
        {
          v28 = j;
          continue;
        }
        v194 = 0;
        if ( pCounterLookupBlocks )
          v194 = (char *)pCounterLookupBlocks + 40960;
        if ( v194 && *(_QWORD *)v194 )
        {
          _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v194 + 32LL), v78 - v82);
          v28 = j;
        }
        else
        {
LABEL_480:
          v28 = j;
        }
      }
    }
  }
  if ( (_QWORD)v209 != *((_QWORD *)&v209 + 1) )
  {
    v31 = v210;
    v32 = 0;
    v33 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *((_DWORD *)v210 + 4) || _InterlockedCompareExchange64((volatile signed __int64 *)v210 + 2, v33, 0) )
    {
      v184 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v185 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v185 && *(_QWORD *)(v185 + 272) == v185 )
          v184 = *(_QWORD *)(v185 + 256);
        if ( v184 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v215);
            v32 = (DirtyPageMgr *)v215.QuadPart;
          }
          else
          {
            v32 = MEMORY[0x7FFE0008];
          }
        }
      }
      v186 = (__int64)v31 + 16;
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(v186, v33);
      else
        Spinlock<19,1,268435714>::SpinToAcquireOptimistic(v186, v184, v33);
      if ( v184 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v216);
          v187 = (DirtyPageMgr *)v216.QuadPart;
        }
        else
        {
          v187 = MEMORY[0x7FFE0008];
        }
        v188 = 0;
        if ( v187 >= v32 )
          v188 = v187 - v32;
        *(_QWORD *)(v184 + 3192) += v188;
      }
    }
    v34 = v201;
    for ( j = *(_QWORD *)(v201 + 8); ; j = *(_QWORD *)(j + 8) )
    {
LABEL_212:
      if ( (struct MemoryNodeList *)j == v31 )
      {
        j = 0;
        goto LABEL_217;
      }
      if ( !j )
        goto LABEL_217;
      v35 = *(_DWORD *)(j + 24);
      if ( v35 )
        break;
LABEL_434:
      ;
    }
    while ( v35 != _InterlockedCompareExchange((volatile signed __int32 *)(j + 24), v35 + 1, v35) )
    {
      _mm_pause();
      v35 = *(_DWORD *)(j + 24);
      if ( !v35 )
      {
        j = *(_QWORD *)(j + 8);
        goto LABEL_212;
      }
    }
    if ( v35 == -1 )
      goto LABEL_434;
LABEL_217:
    if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v189 = rand();
      v190 = (unsigned int)(5 * (v189 / 5));
      if ( v189 == (_DWORD)v190 )
        Spinlock<19,1,268435714>::UpdateStatSnapshot(v190);
    }
    *((_QWORD *)v31 + 2) = 0;
    *(_QWORD *)&v209 = j;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v34 + 24), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)(v34 + 8) )
        TList<SuperLatchManager,SuperLatchInfo,0,TListSLock>::RemoveElem(*(_QWORD *)(v34 + 16), v34);
      MemoryNode::Destroy((MemoryNode *)v34);
    }
    goto LABEL_219;
  }
  *(_QWORD *)&v209 = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v30 + 24), 0xFFFFFFFF) != 1 )
    goto LABEL_219;
  if ( *(_QWORD *)(v30 + 8) )
    TList<SuperLatchManager,SuperLatchInfo,0,TListSLock>::RemoveElem(*(_QWORD *)(v30 + 16), v30);
  MemoryNode::Destroy((MemoryNode *)v30);
LABEL_279:
  if ( CommonGlobalState::m_PerfCountersEnabled )
  {
    v83 = 0;
    if ( pCounterLookupBlocks )
      v83 = (char *)pCounterLookupBlocks + 38912;
    if ( v83 && *(_QWORD *)v83 )
      *(_QWORD *)(*(_QWORD *)v83 + 144LL) = 8LL * (_QWORD)v29;
  }
  v84 = WORD2(qword_10317F720) & 0x8000;
  if ( !CommonGlobalState::m_ProfilerTraceEnabled
    || (dword_10316ECC4 & 0x20000) == 0
    || (v85 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset
                        + 8LL)) == 0
    || (v86 = *(_DWORD **)(v85 + 48)) == 0
    || (v87 = 1, *v86) )
  {
    v87 = 0;
  }
  if ( ((qword_10317F720 & 0x800000000000LL) != 0 || v87)
    && (double)(int)v217 >= fmax(
                              (double)(int)((unsigned __int64)MemoryNode::GetTotalPhysicalMemory() >> 13) * 0.05,
                              128.0) )
  {
    v195 = v218;
    v196 = (v218 <= qword_10319A0B8) + 1;
    v197 = (unsigned __int64)(v218 << 13) >> 20;
    if ( v87 )
    {
      v198 = *(_DWORD **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                    + SystemThread_TlsOffset
                                    + 8LL)
                        + 48LL);
      v198[8] = v196;
      v198[9] = v197;
      v198[3] |= 0x2200000u;
      CTraceController::ProduceRecord((CTraceController *)byte_10316ECB8, 81);
    }
    if ( v84 )
    {
      v224 = 0x10000;
      v225 = 0;
      v226 = v229;
      v227 = &v230;
      v231 = 0;
      v228 = 0;
      v232 = 0;
      v229[0] = &v233;
      v229[1] = 5;
      v233 = v196;
      v234 = v197;
      XeSqlPkg::server_memory_change::Publish((XeSqlPkg::server_memory_change *)v223);
    }
    qword_10319A0B8 = v195;
  }
  SOS_MemoryNodeEnum::~SOS_MemoryNodeEnum((SOS_MemoryNodeEnum *)&v209);
}

```

## disassembly

```asm
0x10040cde0  push    rbp
0x10040cde2  push    r12
0x10040cde4  push    r13
0x10040cde6  push    r14
0x10040cde8  push    r15
0x10040cdea  lea     rbp, [rsp-2010h]
0x10040cdf2  mov     eax, 2110h
0x10040cdf7  call    _alloca_probe
0x10040cdfc  sub     rsp, rax
0x10040cdff  mov     [rbp+2030h+var_2050], 0FFFFFFFFFFFFFFFEh
0x10040ce07  mov     [rsp+2130h+arg_0], rbx
0x10040ce0f  mov     [rsp+2130h+arg_8], rsi
0x10040ce17  mov     [rsp+2130h+arg_10], rdi
0x10040ce1f  movaps  [rsp+2130h+var_30], xmm6
0x10040ce27  movaps  [rsp+2130h+var_40], xmm7
0x10040ce2f  mov     rax, cs:__security_cookie
0x10040ce36  xor     rax, rsp
0x10040ce39  mov     [rbp+2030h+var_48], rax
0x10040ce40  call    cs:__imp_?GetTotalPagesCommitted@MemoryNode@@SA_JXZ; MemoryNode::GetTotalPagesCommitted(void)
0x10040ce46  mov     r15, rax
0x10040ce49  mov     [rbp+2030h+var_2058], rax
0x10040ce4d  mov     rcx, cs:qword_10319A0B8
0x10040ce54  mov     rdx, rcx
0x10040ce57  sub     rdx, rax
0x10040ce5a  sub     rax, rcx
0x10040ce5d  cmp     rcx, r15
0x10040ce60  cmovg   rax, rdx
0x10040ce64  mov     [rbp+2030h+var_2060], rax
0x10040ce68  call    cs:__imp_?GetTotalPagesFree@MemoryNode@@SA_JXZ; MemoryNode::GetTotalPagesFree(void)
0x10040ce6e  mov     r14, rax
0x10040ce71  mov     rsi, cs:qword_10317B628
0x10040ce78  xor     r13d, r13d
0x10040ce7b  mov     edi, r13d
0x10040ce7e  movzx   ebx, r13w
0x10040ce82  movzx   edx, bx; unsigned __int16
0x10040ce85  mov     rcx, rsi; this
0x10040ce88  call    ?HashedCount@BPool@@QEBA_KG@Z; BPool::HashedCount(ushort)
0x10040ce8d  add     rdi, rax
0x10040ce90  inc     bx
0x10040ce93  movzx   eax, bx
0x10040ce96  cmp     eax, [rsi+300h]
0x10040ce9c  jbe     short loc_10040CE82
0x10040ce9e  mov     rbx, r15
0x10040cea1  sub     rbx, rdi
0x10040cea4  call    cs:__imp_?GetTotalPagesReserved@MemoryNode@@SA_JXZ; MemoryNode::GetTotalPagesReserved(void)
0x10040ceaa  mov     rsi, rax
0x10040cead  test    rax, rax
0x10040ceb0  cmovs   rsi, r13
0x10040ceb4  sub     rbx, r14
0x10040ceb7  cmovs   rbx, r13
0x10040cebb  mov     rcx, cs:__imp_?m_PerfCountersEnabled@CommonGlobalState@@2_NA; bool CommonGlobalState::m_PerfCountersEnabled
0x10040cec2  mov     r12d, 1
0x10040cec8  cmp     [rcx], r13b
0x10040cecb  jz      short loc_10040CF11
0x10040cecd  lea     rdi, ds:0[rdi*8]
0x10040ced5  mov     r8d, r13d
0x10040ced8  mov     rcx, cs:?pCounterLookupBlocks@@3PAPEAY1DK@BAA@PEA_KA; unsigned __int64 * (* near * pCounterLookupBlocks)[58][256]
0x10040cedf  lea     rax, [rcx+9800h]
0x10040cee6  mov     rdx, r13
0x10040cee9  test    rcx, rcx
0x10040ceec  cmovnz  rdx, rax
0x10040cef0  test    rdx, rdx
0x10040cef3  jz      short loc_10040CF04
0x10040cef5  mov     rax, [rdx]
0x10040cef8  test    rax, rax
0x10040cefb  jz      short loc_10040CF04
0x10040cefd  mov     [rax+10h], rdi
0x10040cf01  mov     r8d, r12d
0x10040cf04  test    byte ptr cs:?g_XeSqlMinPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$0FBI@@@@@A, 80h; XBitmap<StaticStorage<1304>> g_XeSqlMinPkg_enabledBitmap
0x10040cf0b  jnz     loc_10189EB4A
0x10040cf11  mov     rax, cs:__imp_?m_PerfCountersEnabled@CommonGlobalState@@2_NA; bool CommonGlobalState::m_PerfCountersEnabled
0x10040cf18  cmp     [rax], r13b
0x10040cf1b  jz      short loc_10040CF64
0x10040cf1d  lea     r9, ds:0[r14*8]
0x10040cf25  mov     r8d, r13d
0x10040cf28  mov     rcx, cs:?pCounterLookupBlocks@@3PAPEAY1DK@BAA@PEA_KA; unsigned __int64 * (* near * pCounterLookupBlocks)[58][256]
0x10040cf2f  lea     rax, [rcx+9800h]
0x10040cf36  mov     rdx, r13
0x10040cf39  test    rcx, rcx
0x10040cf3c  cmovnz  rdx, rax
0x10040cf40  test    rdx, rdx
0x10040cf43  jz      short loc_10040CF54
0x10040cf45  mov     rax, [rdx]
0x10040cf48  test    rax, rax
0x10040cf4b  jz      short loc_10040CF54
0x10040cf4d  mov     [rax+18h], r9
0x10040cf51  mov     r8d, r12d
0x10040cf54  test    cs:?g_XeSqlMinPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$0FBI@@@@@A, 100h; XBitmap<StaticStorage<1304>> g_XeSqlMinPkg_enabledBitmap
0x10040cf5e  jnz     loc_10189EBC8
0x10040cf64  mov     rax, cs:__imp_?m_PerfCountersEnabled@CommonGlobalState@@2_NA; bool CommonGlobalState::m_PerfCountersEnabled
0x10040cf6b  cmp     [rax], r13b
0x10040cf6e  jz      short loc_10040CFB7
0x10040cf70  lea     rsi, ds:0[rsi*8]
0x10040cf78  mov     r8d, r13d
0x10040cf7b  mov     rcx, cs:?pCounterLookupBlocks@@3PAPEAY1DK@BAA@PEA_KA; unsigned __int64 * (* near * pCounterLookupBlocks)[58][256]
0x10040cf82  lea     rax, [rcx+9800h]
0x10040cf89  mov     rdx, r13
0x10040cf8c  test    rcx, rcx
0x10040cf8f  cmovnz  rdx, rax
0x10040cf93  test    rdx, rdx
0x10040cf96  jz      short loc_10040CFA7
0x10040cf98  mov     rax, [rdx]
0x10040cf9b  test    rax, rax
0x10040cf9e  jz      short loc_10040CFA7
0x10040cfa0  mov     [rax+70h], rsi
0x10040cfa4  mov     r8d, r12d
0x10040cfa7  test    cs:?g_XeSqlMinPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$0FBI@@@@@A, 200h; XBitmap<StaticStorage<1304>> g_XeSqlMinPkg_enabledBitmap
0x10040cfb1  jnz     loc_10189EC46
0x10040cfb7  mov     rax, cs:__imp_?m_PerfCountersEnabled@CommonGlobalState@@2_NA; bool CommonGlobalState::m_PerfCountersEnabled
0x10040cfbe  cmp     [rax], r13b
0x10040cfc1  jz      short loc_10040D00D
0x10040cfc3  lea     rbx, ds:0[rbx*8]
0x10040cfcb  mov     r8d, r13d
0x10040cfce  mov     rcx, cs:?pCounterLookupBlocks@@3PAPEAY1DK@BAA@PEA_KA; unsigned __int64 * (* near * pCounterLookupBlocks)[58][256]
0x10040cfd5  lea     rax, [rcx+9800h]
0x10040cfdc  mov     rdx, r13
0x10040cfdf  test    rcx, rcx
0x10040cfe2  cmovnz  rdx, rax
0x10040cfe6  test    rdx, rdx
0x10040cfe9  jz      short loc_10040CFFD
0x10040cfeb  mov     rax, [rdx]
0x10040cfee  test    rax, rax
0x10040cff1  jz      short loc_10040CFFD
0x10040cff3  mov     [rax+80h], rbx
0x10040cffa  mov     r8d, r12d
0x10040cffd  test    cs:?g_XeSqlMinPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$0FBI@@@@@A, 400h; XBitmap<StaticStorage<1304>> g_XeSqlMinPkg_enabledBitmap
0x10040d007  jnz     loc_10189ECC4
0x10040d00d  mov     rax, cs:__imp_?m_PerfCountersEnabled@CommonGlobalState@@2_NA; bool CommonGlobalState::m_PerfCountersEnabled
0x10040d014  cmp     [rax], r13b
0x10040d017  jz      short loc_10040D069
0x10040d019  mov     rax, cs:__imp_?MemoryNode_MemoryTargetPages@@3_JA; __int64 MemoryNode_MemoryTargetPages
0x10040d020  mov     r8, [rax]
0x10040d023  shl     r8, 3
0x10040d027  mov     r9d, r13d
0x10040d02a  mov     rcx, cs:?pCounterLookupBlocks@@3PAPEAY1DK@BAA@PEA_KA; unsigned __int64 * (* near * pCounterLookupBlocks)[58][256]
0x10040d031  lea     rax, [rcx+9800h]
0x10040d038  mov     rdx, r13
0x10040d03b  test    rcx, rcx
0x10040d03e  cmovnz  rdx, rax
0x10040d042  test    rdx, rdx
0x10040d045  jz      short loc_10040D059
0x10040d047  mov     rax, [rdx]
0x10040d04a  test    rax, rax
0x10040d04d  jz      short loc_10040D059
0x10040d04f  mov     [rax+98h], r8
0x10040d056  mov     r9d, r12d
0x10040d059  test    cs:?g_XeSqlMinPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$0FBI@@@@@A, 800h; XBitmap<StaticStorage<1304>> g_XeSqlMinPkg_enabledBitmap
0x10040d063  jnz     loc_10189ED42
0x10040d069  mov     rax, cs:__imp_?m_PerfCountersEnabled@CommonGlobalState@@2_NA; bool CommonGlobalState::m_PerfCountersEnabled
0x10040d070  cmp     [rax], r13b
0x10040d073  jz      short loc_10040D0BF
0x10040d075  lea     r9, ds:0[r15*8]
0x10040d07d  mov     r8d, r13d
0x10040d080  mov     rcx, cs:?pCounterLookupBlocks@@3PAPEAY1DK@BAA@PEA_KA; unsigned __int64 * (* near * pCounterLookupBlocks)[58][256]
0x10040d087  lea     rax, [rcx+9800h]
0x10040d08e  mov     rdx, r13
0x10040d091  test    rcx, rcx
0x10040d094  cmovnz  rdx, rax
0x10040d098  test    rdx, rdx
0x10040d09b  jz      short loc_10040D0AF
0x10040d09d  mov     rax, [rdx]
0x10040d0a0  test    rax, rax
0x10040d0a3  jz      short loc_10040D0AF
0x10040d0a5  mov     [rax+0A0h], r9
0x10040d0ac  mov     r8d, r12d
0x10040d0af  test    cs:?g_XeSqlMinPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$0FBI@@@@@A, 1000h; XBitmap<StaticStorage<1304>> g_XeSqlMinPkg_enabledBitmap
0x10040d0b9  jnz     loc_10189EDC0
0x10040d0bf  mov     rax, cs:__imp_?m_PerfCountersEnabled@CommonGlobalState@@2_NA; bool CommonGlobalState::m_PerfCountersEnabled
0x10040d0c6  cmp     [rax], r13b
0x10040d0c9  jz      short loc_10040D149
0x10040d0cb  mov     rcx, qword ptr cs:xmmword_103199FF0
0x10040d0d2  mov     rax, [rcx+100h]
0x10040d0d9  mov     [rsp+2130h+var_20E0], rax
0x10040d0de  lock or [rsp+2130h+var_2130], r13d
0x10040d0e3  mov     rax, [rcx+0C0h]
0x10040d0ea  mov     [rsp+2130h+var_20F8], rax
0x10040d0ef  mov     rcx, qword ptr cs:xmmword_103199FF0
0x10040d0f6  mov     rax, [rsp+2130h+var_20E0]
0x10040d0fb  mov     rdx, [rcx+5F0h]
0x10040d102  sub     rdx, rax
0x10040d105  mov     r8, [rsp+2130h+var_20F8]
0x10040d10a  add     r8, rdx
0x10040d10d  shl     r8, 3
0x10040d111  mov     rax, cs:__imp_?m_PerfCountersEnabled@CommonGlobalState@@2_NA; bool CommonGlobalState::m_PerfCountersEnabled
0x10040d118  cmp     [rax], r13b
0x10040d11b  jz      short loc_10040D149
0x10040d11d  mov     rcx, cs:?pCounterLookupBlocks@@3PAPEAY1DK@BAA@PEA_KA; unsigned __int64 * (* near * pCounterLookupBlocks)[58][256]
0x10040d124  lea     rax, [rcx+9800h]
0x10040d12b  mov     rdx, r13
0x10040d12e  test    rcx, rcx
0x10040d131  cmovnz  rdx, rax
0x10040d135  test    rdx, rdx
0x10040d138  jz      short loc_10040D149
0x10040d13a  mov     rax, [rdx]
0x10040d13d  test    rax, rax
0x10040d140  jz      short loc_10040D149
0x10040d142  mov     [rax+88h], r8
0x10040d149  lea     rcx, [rbp+2030h+var_2038]; this
0x10040d14d  call    ??0SOS_NodeEnumIncludeUninitializedNodes@@QEAA@XZ; SOS_NodeEnumIncludeUninitializedNodes::SOS_NodeEnumIncludeUninitializedNodes(void)
0x10040d152  nop
0x10040d153  mov     r15, r13
0x10040d156  mov     rsi, r13
0x10040d159  mov     [rsp+2130h+var_20F0], r13
0x10040d15e  mov     r14, r13
0x10040d161  mov     [rsp+2130h+var_20E0], r13
0x10040d166  mov     rdi, 8000000000000000h
0x10040d170  movsd   xmm7, cs:__real@4202a05f20000000
0x10040d178  movsd   xmm6, cs:__real@43e0000000000000
0x10040d180  mov     rdx, r15; struct SOS_Node *
0x10040d183  lea     rcx, [rbp+2030h+var_2038]; this
0x10040d187  call    ?GetNext@SOS_NodeEnumIncludeUninitializedNodes@@QEAAPEAVSOS_Node@@PEAV2@@Z; SOS_NodeEnumIncludeUninitializedNodes::GetNext(SOS_Node *)
0x10040d18c  mov     r15, rax
0x10040d18f  mov     [rsp+2130h+var_20F8], rax
0x10040d194  test    rax, rax
0x10040d197  jz      short loc_10040D1B3
0x10040d199  nop     dword ptr [rax+rax]
0x10040d19d  nop     dword ptr [rax]
0x10040d1a0  test    byte ptr [r15+620h], 10h
0x10040d1a8  jnz     loc_10189EE3E
0x10040d1ae  mov     [rsp+2130h+var_20F8], r15
0x10040d1b3  test    r15, r15
0x10040d1b6  jz      loc_10040BDF6
0x10040d1bc  lea     rcx, [r15+3B0h]
0x10040d1c3  cmp     word ptr [r15+0A0h], 0
0x10040d1cc  jz      loc_10040BC98
0x10040d1d2  xor     esi, esi
0x10040d1d4  call    cs:__imp_?GetMemoryBrokerClerks@ResourceMonitor@@QEAAPEAVMemoryBrokerClerkList@@XZ; ResourceMonitor::GetMemoryBrokerClerks(void)
0x10040d1da  mov     r14, rax
0x10040d1dd  mov     [rsp+2130h+var_20E8], rax
0x10040d1e2  mov     r13, rsi
0x10040d1e5  xorps   xmm0, xmm0
0x10040d1e8  movdqu  [rsp+2130h+var_20D0], xmm0
0x10040d1ee  mov     [rsp+2130h+var_20B8], rsi
0x10040d1f3  mov     [rbp+2030h+var_20B0], esi
0x10040d1f6  mov     [rsp+2130h+var_20C0], rsi
0x10040d1fb  mov     [rsp+2130h+var_20C0], rax
0x10040d200  mov     rcx, rax
0x10040d203  call    ?GetHead@?$TList@VMemoryBrokerClerkList@@VMemoryBrokerClerk@@$07UTListSLock@@@@QEAAPEAVMemoryBrokerClerk@@XZ; TList<MemoryBrokerClerkList,MemoryBrokerClerk,8,TListSLock>::GetHead(void)
0x10040d208  mov     qword ptr [rsp+2130h+var_20D0], rax
0x10040d20d  mov     rcx, r14
0x10040d210  call    ?GetTail@?$TList@VSOS_Node@@VSOS_DispatcherPoolBase@@$07UTListSLock@@@@QEAAPEAVSOS_DispatcherPoolBase@@XZ; TList<SOS_Node,SOS_DispatcherPoolBase,8,TListSLock>::GetTail(void)
0x10040d215  mov     qword ptr [rsp+2130h+var_20D0+8], rax
0x10040d21a  mov     r12d, esi
0x10040d21d  mov     rbx, rsi
0x10040d220  test    r13, r13
0x10040d223  jnz     loc_10040D5DD
0x10040d229  mov     rbx, qword ptr [rsp+2130h+var_20D0]
0x10040d22e  jmp     short loc_10040D231
0x10040d231  mov     r13, rbx
0x10040d234  test    rbx, rbx
0x10040d237  jnz     loc_10040D339
0x10040d23d  xor     r13d, r13d
0x10040d240  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x10040d246  mov     rcx, rax
0x10040d249  mov     r15, [rsp+2130h+var_20F8]
0x10040d24e  movzx   edx, word ptr [r15+0A0h]
0x10040d256  call    cs:__imp_?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z; PerProcessGlobals::GetDefaultMemoryClerksForNode(ushort)
0x10040d25c  mov     rbx, rax
0x10040d25f  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x10040d265  mov     rcx, [rbx+90h]
0x10040d26c  mov     rsi, [rsp+2130h+var_20F0]
0x10040d271  add     rsi, [rcx+5F0h]
0x10040d278  mov     rax, [rcx+100h]
0x10040d27f  mov     [rsp+2130h+var_20E8], rax
0x10040d284  lock or [rsp+2130h+var_2130], 0
0x10040d289  mov     rax, [rcx+0C0h]
0x10040d290  mov     [rsp+2130h+var_20F8], rax
0x10040d295  mov     rax, [rsp+2130h+var_20E8]
0x10040d29a  sub     rsi, rax
0x10040d29d  mov     rax, rsi
0x10040d2a0  mov     rsi, [rsp+2130h+var_20F8]
0x10040d2a5  add     rsi, rax
0x10040d2a8  mov     [rsp+2130h+var_20F0], rsi
0x10040d2ad  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x10040d2b3  mov     rcx, rax
0x10040d2b6  movzx   edx, word ptr [r15+0A0h]
0x10040d2be  call    cs:__imp_?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z; PerProcessGlobals::GetDefaultMemoryClerksForNode(ushort)
0x10040d2c4  mov     rbx, rax
0x10040d2c7  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x10040d2cd  mov     rcx, [rbx+40h]
0x10040d2d1  mov     r14, [rsp+2130h+var_20E0]
0x10040d2d6  add     r14, [rcx+5F0h]
0x10040d2dd  mov     rax, [rcx+100h]
0x10040d2e4  mov     [rsp+2130h+var_20E8], rax
0x10040d2e9  lock or [rsp+2130h+var_2130], 0
0x10040d2ee  mov     rax, [rcx+0C0h]
0x10040d2f5  mov     [rsp+2130h+var_20E0], rax
0x10040d2fa  mov     rax, [rsp+2130h+var_20E8]
0x10040d2ff  sub     r14, rax
0x10040d302  mov     rax, r14
0x10040d305  mov     r14, [rsp+2130h+var_20E0]
0x10040d30a  add     r14, rax
0x10040d30d  mov     [rsp+2130h+var_20E0], r14
0x10040d312  mov     rcx, qword ptr [rsp+2130h+var_20D0]
0x10040d317  test    rcx, rcx
0x10040d31a  jnz     loc_10189F1DE
0x10040d320  mov     rcx, qword ptr [rsp+2130h+var_20D0+8]
0x10040d325  test    rcx, rcx
0x10040d328  jnz     loc_10040BCFD
0x10040d32e  mov     [rsp+2130h+var_20C0], r13
  ... truncated ...
```
