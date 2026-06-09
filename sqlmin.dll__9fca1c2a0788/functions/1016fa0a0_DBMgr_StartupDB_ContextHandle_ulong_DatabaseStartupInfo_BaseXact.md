# DBMgr::StartupDB(ContextHandle,ulong,DatabaseStartupInfo &,BaseXact *)

- ea: `0x1016fa0a0`
- end: `0x1016fc7f9`
- name: `?StartupDB@DBMgr@@QEAAXVContextHandle@@KAEAVDatabaseStartupInfo@@PEAVBaseXact@@@Z`
- size: `10073`
- prototype: ``
- caller_count: `26`
- callee_count: `62`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x100aac420`
- `0x1011f4f40`
- `0x1016f3cc0`
- `0x1016f5750`
- `0x1016f7850`
- `0x1016fde90`
- `0x1017004c0`
- `0x10170b150`
- `0x10170e8c0`
- `0x10170fa00`
- `0x101712be0`
- `0x101715d90`
- `0x101716b90`
- `0x101b94c50`
- `0x101b96170`
- `0x101b96fb0`
- `0x101b98900`
- `0x101b99490`
- `0x101b9dad0`
- `0x101b9e470`
- `0x101e2f0b0`
- `0x101ff0590`
- `0x1020b2840`
- `0x102464410`
- `0x1025ca134`
- `0x10269732e`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x100402000`
- `0x100402200`
- `0x1004025c0`
- `0x10040fc00`
- `0x100415c30`
- `0x1004161c0`
- `0x10041ba80`
- `0x10041e8f0`
- `0x100420af0`
- `0x10046221a`
- `0x1004a7d40`
- `0x1004ab1b0`
- `0x1004ab250`
- `0x1004bf030`
- `0x1004c4220`
- `0x10053fe80`
- `0x10056afe0`
- `0x10056b1c0`
- `0x10056b280`
- `0x10056b530`
- `0x1005bfc50`
- `0x10063fad0`
- `0x10063fbb0`
- `0x10063fc00`
- `0x10063fc50`
- `0x100650960`
- `0x100651020`
- `0x100a59a10`
- `0x100abfea0`
- `0x100abfef0`
- `0x100abffd0`
- `0x100ac3d60`
- `0x100ac4180`
- `0x100bc1b70`
- `0x100bd8ab0`
- `0x100bdcdb0`
- `0x100c0a9c0`
- `0x101648900`
- `0x1016c6d00`
- `0x1016c79b0`
- `0x1016c7fb0`
- `0x1016c83e0`
- `0x1016f9570`
- `0x1016fa0a0`
- `0x1017214d0`
- `0x101721520`
- `0x101721560`
- `0x101721680`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1016fa20a`
- `KERNEL32!QueryPerformanceCounter` at `0x1016fb521`
- `KERNEL32!QueryPerformanceCounter` at `0x1016fb766`
- `KERNEL32!QueryPerformanceCounter` at `0x1016fb926`
- `KERNEL32!QueryPerformanceCounter` at `0x1016fba7d`
- `KERNEL32!QueryPerformanceCounter` at `0x1016fa20a`
- `KERNEL32!QueryPerformanceCounter` at `0x1016fb521`
- `KERNEL32!QueryPerformanceCounter` at `0x1016fb766`
- `KERNEL32!QueryPerformanceCounter` at `0x1016fb926`
- `KERNEL32!QueryPerformanceCounter` at `0x1016fba7d`
- `ole32!StringFromGUID2` at `0x1016fa3cd`
- `ole32!StringFromGUID2` at `0x1016fa3cd`
- `ole32!CoCreateGuid` at `0x1016fba10`
- `ole32!CoCreateGuid` at `0x1016fba10`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1016fb7f4`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1016fb811`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016fa1f7`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016fb50d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016fb752`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016fb912`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016fb981`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016fba69`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016fbad8`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016fbca6`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x1016fb98d`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x1016fbae4`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x1016fbcb2`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1016fbb41`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1016fbd90`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1016fc081`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x1016fad4c`
- `sqldk!?g_pAutoXactFactory@@3PEAVIAutoXactFactory@@EA` at `0x1016fa718`
- `sqldk!?ResetDeadlock@SOS_Task@@SAXXZ` at `0x1016fa50a`
- `sqldk!?ResetDeadlock@SOS_Task@@SAXXZ` at `0x1016fa50a`
- `sqldk!?ResetAbort@SOS_Task@@SAXW4TASK_ABORT_TYPE@1@@Z` at `0x1016fa504`
- `sqldk!?ResetAbort@SOS_Task@@SAXW4TASK_ABORT_TYPE@1@@Z` at `0x1016fa504`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x1016facde`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x1016facde`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1016fc41b`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1016fc41b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016fa6e2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016fa705`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016fba2b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016fbc26`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016fbe5e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016fa6e2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016fa705`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016fba2b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016fbc26`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016fbe5e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016faa7c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016fb8fb`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016faa7c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016fb8fb`
- `sqldk!SystemThread_TlsIndex` at `0x1016fa189`
- `sqldk!SystemThread_TlsIndex` at `0x1016fa1ba`
- `sqldk!SystemThread_TlsIndex` at `0x1016fa235`
- `sqldk!SystemThread_TlsIndex` at `0x1016fa26d`
- `sqldk!SystemThread_TlsIndex` at `0x1016fa404`
- `sqldk!SystemThread_TlsIndex` at `0x1016fa489`
- `sqldk!SystemThread_TlsIndex` at `0x1016fa539`
- `sqldk!SystemThread_TlsIndex` at `0x1016fa577`
- `sqldk!SystemThread_TlsIndex` at `0x1016fa64c`
- `sqldk!SystemThread_TlsIndex` at `0x1016fa68a`
- `sqldk!SystemThread_TlsIndex` at `0x1016fa7c8`
- `sqldk!SystemThread_TlsIndex` at `0x1016fa864`
- `sqldk!SystemThread_TlsIndex` at `0x1016fa8a2`
- `sqldk!SystemThread_TlsIndex` at `0x1016faa3d`
- `sqldk!SystemThread_TlsIndex` at `0x1016fad01`
- `sqldk!SystemThread_TlsIndex` at `0x1016fb8cc`
- `sqldk!SystemThread_TlsIndex` at `0x1016fc1ea`
- `sqldk!SystemThread_TlsIndex` at `0x1016fc228`
- `sqldk!SystemThread_TlsIndex` at `0x1016fc312`
- `sqldk!SystemThread_TlsIndex` at `0x1016fc350`
- `sqldk!SystemThread_TlsIndex` at `0x1016fc3e3`
- `sqldk!SystemThread_TlsIndex` at `0x1016fc453`
- `sqldk!SystemThread_TlsIndex` at `0x1016fc509`
- `sqldk!SystemThread_TlsIndex` at `0x1016fc567`
- `sqldk!SystemThread_TlsIndex` at `0x1016fc5ca`
- `sqldk!SystemThread_TlsIndex` at `0x1016fc61f`
- `sqldk!SystemThread_TlsIndex` at `0x1016fc65d`
- `sqldk!SystemThread_TlsIndex` at `0x1016fc6d8`
- `sqldk!SystemThread_TlsIndex` at `0x1016fc720`
- `sqldk!SystemThread_TlsIndex` at `0x1016fc78a`
- `sqldk!SystemThread_TlsOffset` at `0x1016fa192`
- `sqldk!SystemThread_TlsOffset` at `0x1016fa1c3`
- `sqldk!SystemThread_TlsOffset` at `0x1016fa23e`
- `sqldk!SystemThread_TlsOffset` at `0x1016fa276`
- `sqldk!SystemThread_TlsOffset` at `0x1016fa40d`
- `sqldk!SystemThread_TlsOffset` at `0x1016fa492`
- `sqldk!SystemThread_TlsOffset` at `0x1016fa542`
- `sqldk!SystemThread_TlsOffset` at `0x1016fa580`
- `sqldk!SystemThread_TlsOffset` at `0x1016fa655`
- `sqldk!SystemThread_TlsOffset` at `0x1016fa693`
- `sqldk!SystemThread_TlsOffset` at `0x1016fa7d1`
- `sqldk!SystemThread_TlsOffset` at `0x1016fa86d`
- `sqldk!SystemThread_TlsOffset` at `0x1016fa8ab`
- `sqldk!SystemThread_TlsOffset` at `0x1016faa46`
- `sqldk!SystemThread_TlsOffset` at `0x1016fad0a`
- `sqldk!SystemThread_TlsOffset` at `0x1016fb8d5`
- `sqldk!SystemThread_TlsOffset` at `0x1016fc1f3`
- `sqldk!SystemThread_TlsOffset` at `0x1016fc231`
- `sqldk!SystemThread_TlsOffset` at `0x1016fc31b`
- `sqldk!SystemThread_TlsOffset` at `0x1016fc359`
- `sqldk!SystemThread_TlsOffset` at `0x1016fc3ec`
- `sqldk!SystemThread_TlsOffset` at `0x1016fc45c`
- `sqldk!SystemThread_TlsOffset` at `0x1016fc512`
- `sqldk!SystemThread_TlsOffset` at `0x1016fc570`
- `sqldk!SystemThread_TlsOffset` at `0x1016fc5d3`
- `sqldk!SystemThread_TlsOffset` at `0x1016fc628`
- `sqldk!SystemThread_TlsOffset` at `0x1016fc666`
- `sqldk!SystemThread_TlsOffset` at `0x1016fc6e1`
- `sqldk!SystemThread_TlsOffset` at `0x1016fc729`
- `sqldk!SystemThread_TlsOffset` at `0x1016fc793`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1016fafce`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1016fb18d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1016fafce`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1016fb18d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016fa428`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016fad23`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016fc405`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016fa428`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016fad23`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016fc405`
- `sqllang!??0CAutoSetDiagOptions@@QEAA@XZ` at `0x1016fa1f0`
- `sqllang!??0CAutoSetDiagOptions@@QEAA@XZ` at `0x1016fa1f0`
- `sqllang!??1CAutoSetDiagOptions@@QEAA@XZ` at `0x1016fa529`
- `sqllang!??1CAutoSetDiagOptions@@QEAA@XZ` at `0x1016fa63c`
- `sqllang!??1CAutoSetDiagOptions@@QEAA@XZ` at `0x1016fa854`
- `sqllang!??1CAutoSetDiagOptions@@QEAA@XZ` at `0x1016fc1da`
- `sqllang!??1CAutoSetDiagOptions@@QEAA@XZ` at `0x1016fc302`
- `sqllang!??1CAutoSetDiagOptions@@QEAA@XZ` at `0x1016fc60f`
- `sqllang!??1CAutoSetDiagOptions@@QEAA@XZ` at `0x1016fa529`
- `sqllang!??1CAutoSetDiagOptions@@QEAA@XZ` at `0x1016fa63c`
- `sqllang!??1CAutoSetDiagOptions@@QEAA@XZ` at `0x1016fa854`
- `sqllang!??1CAutoSetDiagOptions@@QEAA@XZ` at `0x1016fc1da`
- `sqllang!??1CAutoSetDiagOptions@@QEAA@XZ` at `0x1016fc302`
- `sqllang!??1CAutoSetDiagOptions@@QEAA@XZ` at `0x1016fc60f`
- `sqllang!?SetSystemTaskIfNoneSet@CAutoSetDiagOptions@@QEAAXF@Z` at `0x1016fa29f`
- `sqllang!?SetSystemTaskIfNoneSet@CAutoSetDiagOptions@@QEAAXF@Z` at `0x1016fa29f`

## string_xrefs

- `0x1016fa3e8`: `HadrRuntimeCallbacks::WaitForAgMasterReady (%ls), return %ld`

## pseudocode

```c
// Hidden C++ exception states: #wind=29 #try_helpers=1
void __fastcall DBMgr::StartupDB(DBMgr *a1, __int64 a2, unsigned int a3, __int64 a4, struct BaseXact *a5)
{
  __int64 v5; // r12
  DirtyPageMgr *QuadPart; // rsi
  char v8; // al
  __int64 v9; // rcx
  __int64 v10; // r9
  int v11; // r14d
  CHadrArManager *Instance; // rax
  CHadrArController *ContainedAgControllerWithRef; // rax
  CHadrArController *v14; // rdi
  char *v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // r15
  int v18; // ecx
  DBMgr *v19; // rdi
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rcx
  struct BaseXact *v26; // rax
  __int64 v27; // rdi
  struct DBTABLE *v28; // r14
  struct BaseXact *ThreadLocalStoragePointer; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  int v32; // ecx
  __int64 v33; // r8
  char v34; // al
  struct BaseXact *v35; // r15
  int v36; // eax
  char v37; // al
  __int64 v38; // rdx
  __int64 *v39; // rax
  struct CSessionTraceFlags *v40; // rcx
  __int64 v41; // r15
  struct XDES *v42; // rax
  int v43; // edx
  int v44; // eax
  __int64 v45; // rdi
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rdi
  __int64 v49; // rax
  char v50; // r15
  __int16 v51; // r12
  __int64 v52; // rax
  __int64 v53; // rax
  unsigned __int64 v54; // rax
  unsigned __int64 v55; // rcx
  RecoveryUnit **v56; // rdx
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rax
  int v60; // edx
  char v61; // al
  DirtyPageMgr *v62; // rax
  __int64 v63; // rax
  unsigned int v64; // eax
  __int64 v65; // r8
  __int64 v66; // r8
  DirtyPageMgr *v67; // rax
  __int64 v68; // rax
  bool v69; // dl
  __int64 v70; // rdx
  struct CSessionTraceFlags *v71; // rcx
  bool v72; // di
  DirtyPageMgr *v73; // rcx
  unsigned __int64 v74; // rcx
  unsigned __int64 v75; // rdx
  DirtyPageMgr *v76; // rcx
  unsigned __int64 v77; // rcx
  unsigned __int64 v78; // rdx
  const wchar_t *v79; // rax
  _QWORD *v80; // rdx
  _QWORD *v81; // rcx
  _QWORD *v82; // rax
  __int64 v83; // rcx
  _QWORD *v84; // rax
  struct RecoveryUnit *v85; // rdi
  int v86; // r15d
  int v87; // eax
  unsigned __int64 v88; // rdx
  unsigned __int64 v89; // rdi
  const wchar_t *v90; // rsi
  const wchar_t *v91; // rax
  _QWORD *v92; // rdx
  _QWORD *v93; // rcx
  _QWORD *v94; // rax
  struct RecoveryUnit *v95; // rdi
  __int64 v96; // rax
  int v97; // eax
  __int64 v98; // rax
  unsigned int *v99; // rdx
  __int64 v100; // rcx
  int v101; // ecx
  unsigned int **v102; // rax
  unsigned int **v103; // rcx
  unsigned int **v104; // rcx
  DBMgr *v105; // rsi
  __int64 v106; // rax
  __int64 v107; // rax
  __int16 i; // cx
  __int64 v109; // rdx
  __int64 v110; // rcx
  __int64 v111; // rax
  __int16 j; // cx
  __int64 v113; // rdx
  __int64 v114; // rcx
  __int64 v115; // rdi
  struct Worker *v116; // rcx
  __int64 v117; // rcx
  __int64 v118; // rdi
  __int64 v119; // rcx
  __int64 v120; // rcx
  __int64 v121; // rcx
  __int64 v122; // rcx
  __int64 v123; // rcx
  wchar_t *v124; // [rsp+20h] [rbp-1028h]
  struct MDAttrDbReg *v125; // [rsp+28h] [rbp-1020h]
  int v126; // [rsp+30h] [rbp-1018h]
  char v127; // [rsp+40h] [rbp-1008h]
  char v128; // [rsp+40h] [rbp-1008h]
  char v129; // [rsp+41h] [rbp-1007h]
  __int64 v130; // [rsp+48h] [rbp-1000h]
  bool v131; // [rsp+51h] [rbp-FF7h]
  bool v132; // [rsp+52h] [rbp-FF6h]
  int v133; // [rsp+54h] [rbp-FF4h]
  int v134; // [rsp+54h] [rbp-FF4h]
  int v135; // [rsp+58h] [rbp-FF0h] BYREF
  unsigned __int8 v136; // [rsp+5Ch] [rbp-FECh]
  unsigned int v137; // [rsp+60h] [rbp-FE8h]
  unsigned int v138; // [rsp+64h] [rbp-FE4h]
  int v139; // [rsp+68h] [rbp-FE0h]
  int v140; // [rsp+70h] [rbp-FD8h]
  int v141; // [rsp+74h] [rbp-FD4h]
  DBMgr *v142; // [rsp+78h] [rbp-FD0h]
  struct BaseXact *v143; // [rsp+80h] [rbp-FC8h]
  RecoveryUnit **v144; // [rsp+88h] [rbp-FC0h]
  __int64 v145; // [rsp+90h] [rbp-FB8h] BYREF
  char v146; // [rsp+98h] [rbp-FB0h]
  char v147; // [rsp+99h] [rbp-FAFh]
  __int16 v148; // [rsp+9Ch] [rbp-FACh]
  __int16 v149; // [rsp+A0h] [rbp-FA8h]
  bool v150; // [rsp+A4h] [rbp-FA4h]
  int v151; // [rsp+A8h] [rbp-FA0h]
  int v152; // [rsp+B0h] [rbp-F98h] BYREF
  unsigned __int8 v153; // [rsp+B4h] [rbp-F94h]
  unsigned int v154; // [rsp+B8h] [rbp-F90h]
  unsigned int v155; // [rsp+BCh] [rbp-F8Ch]
  int v156; // [rsp+C0h] [rbp-F88h]
  __int64 v157; // [rsp+C8h] [rbp-F80h] BYREF
  int v158; // [rsp+D0h] [rbp-F78h]
  __int64 v159; // [rsp+D8h] [rbp-F70h]
  __int64 v160; // [rsp+E0h] [rbp-F68h]
  __int64 v161; // [rsp+E8h] [rbp-F60h]
  int v162; // [rsp+F0h] [rbp-F58h] BYREF
  int v163; // [rsp+F8h] [rbp-F50h]
  __int64 v164; // [rsp+100h] [rbp-F48h]
  int v165; // [rsp+108h] [rbp-F40h]
  __int64 v166; // [rsp+110h] [rbp-F38h]
  __int64 v167; // [rsp+118h] [rbp-F30h]
  RecoveryUnit **v168; // [rsp+120h] [rbp-F28h]
  unsigned int v169; // [rsp+128h] [rbp-F20h]
  int v170; // [rsp+130h] [rbp-F18h] BYREF
  int v171; // [rsp+134h] [rbp-F14h]
  int v172; // [rsp+138h] [rbp-F10h] BYREF
  __int64 v173; // [rsp+140h] [rbp-F08h]
  int v174; // [rsp+148h] [rbp-F00h] BYREF
  _BYTE v175[16]; // [rsp+150h] [rbp-EF8h] BYREF
  int v176; // [rsp+160h] [rbp-EE8h]
  __int64 v177; // [rsp+168h] [rbp-EE0h] BYREF
  __int16 v178; // [rsp+170h] [rbp-ED8h]
  __int16 v179; // [rsp+172h] [rbp-ED6h]
  DBMgr *v180; // [rsp+178h] [rbp-ED0h]
  __int64 v181; // [rsp+180h] [rbp-EC8h] BYREF
  unsigned int v182; // [rsp+188h] [rbp-EC0h]
  _WORD v183[2]; // [rsp+190h] [rbp-EB8h] BYREF
  __int128 v184; // [rsp+194h] [rbp-EB4h]
  char v185; // [rsp+1A4h] [rbp-EA4h]
  __int64 v186; // [rsp+1A8h] [rbp-EA0h] BYREF
  __int16 v187; // [rsp+1B0h] [rbp-E98h]
  DirtyPageMgr *v188; // [rsp+1B8h] [rbp-E90h]
  LARGE_INTEGER v189; // [rsp+1C0h] [rbp-E88h] BYREF
  DirtyPageMgr *v190; // [rsp+1C8h] [rbp-E80h]
  struct DBTABLE *v191; // [rsp+1D0h] [rbp-E78h]
  __int64 v192; // [rsp+1D8h] [rbp-E70h]
  _DWORD *v193; // [rsp+1E0h] [rbp-E68h]
  __int64 v194; // [rsp+1E8h] [rbp-E60h]
  __int64 v195; // [rsp+1F0h] [rbp-E58h]
  LARGE_INTEGER PerformanceCount; // [rsp+1F8h] [rbp-E50h] BYREF
  CHadrArController *v197; // [rsp+200h] [rbp-E48h]
  unsigned __int64 v198; // [rsp+208h] [rbp-E40h]
  __int64 v199; // [rsp+210h] [rbp-E38h]
  LARGE_INTEGER v200; // [rsp+218h] [rbp-E30h] BYREF
  DirtyPageMgr *v201; // [rsp+220h] [rbp-E28h]
  LARGE_INTEGER v202; // [rsp+228h] [rbp-E20h] BYREF
  DirtyPageMgr *v203; // [rsp+230h] [rbp-E18h]
  LARGE_INTEGER v204; // [rsp+238h] [rbp-E10h] BYREF
  unsigned __int64 v205; // [rsp+250h] [rbp-DF8h] BYREF
  int v206; // [rsp+258h] [rbp-DF0h]
  __int64 v207; // [rsp+260h] [rbp-DE8h]
  unsigned __int64 v208; // [rsp+268h] [rbp-DE0h] BYREF
  int v209; // [rsp+270h] [rbp-DD8h]
  __int64 v210; // [rsp+278h] [rbp-DD0h]
  __int64 v211; // [rsp+280h] [rbp-DC8h]
  __int64 v212; // [rsp+288h] [rbp-DC0h]
  __int64 v213; // [rsp+290h] [rbp-DB8h]
  __int64 v214; // [rsp+298h] [rbp-DB0h]
  __int64 v215; // [rsp+2A0h] [rbp-DA8h]
  unsigned __int64 v216; // [rsp+2A8h] [rbp-DA0h]
  unsigned __int64 v217; // [rsp+2B0h] [rbp-D98h]
  __int64 v218; // [rsp+2B8h] [rbp-D90h]
  __int64 v219; // [rsp+2C0h] [rbp-D88h]
  __int64 *v220; // [rsp+2C8h] [rbp-D80h]
  __int64 v221; // [rsp+2D0h] [rbp-D78h]
  __int64 v222; // [rsp+2D8h] [rbp-D70h]
  __int64 *v223; // [rsp+2E0h] [rbp-D68h]
  __int64 *v224; // [rsp+2E8h] [rbp-D60h]
  __int64 *v225; // [rsp+2F0h] [rbp-D58h]
  GUID v226; // [rsp+300h] [rbp-D48h] BYREF
  _DWORD *v227; // [rsp+310h] [rbp-D38h]
  __int64 *v228; // [rsp+318h] [rbp-D30h]
  char v229[8]; // [rsp+320h] [rbp-D28h] BYREF
  __int16 v230; // [rsp+328h] [rbp-D20h]
  __int16 v231; // [rsp+32Ah] [rbp-D1Eh]
  int v232; // [rsp+330h] [rbp-D18h]
  unsigned int **v233; // [rsp+338h] [rbp-D10h]
  char *v234; // [rsp+340h] [rbp-D08h]
  __int64 v235; // [rsp+348h] [rbp-D00h]
  unsigned int *v236; // [rsp+350h] [rbp-CF8h] BYREF
  int v237; // [rsp+358h] [rbp-CF0h]
  __int16 v238; // [rsp+35Ch] [rbp-CECh]
  __int16 v239; // [rsp+35Eh] [rbp-CEAh]
  char *v240; // [rsp+360h] [rbp-CE8h]
  int v241; // [rsp+368h] [rbp-CE0h]
  __int16 v242; // [rsp+36Ch] [rbp-CDCh]
  __int16 v243; // [rsp+36Eh] [rbp-CDAh]
  __int64 v244; // [rsp+370h] [rbp-CD8h]
  int v245; // [rsp+378h] [rbp-CD0h]
  __int16 v246; // [rsp+37Ch] [rbp-CCCh]
  __int16 v247; // [rsp+37Eh] [rbp-CCAh]
  GUID *v248; // [rsp+380h] [rbp-CC8h]
  int v249; // [rsp+388h] [rbp-CC0h]
  __int16 v250; // [rsp+38Ch] [rbp-CBCh]
  __int16 v251; // [rsp+38Eh] [rbp-CBAh]
  GUID *v252; // [rsp+390h] [rbp-CB8h]
  int v253; // [rsp+398h] [rbp-CB0h]
  __int16 v254; // [rsp+39Ch] [rbp-CACh]
  __int16 v255; // [rsp+39Eh] [rbp-CAAh]
  char v256; // [rsp+3A0h] [rbp-CA8h] BYREF
  int v257; // [rsp+570h] [rbp-AD8h]
  int v258; // [rsp+574h] [rbp-AD4h]
  __int64 v259; // [rsp+578h] [rbp-AD0h]
  unsigned int v260; // [rsp+580h] [rbp-AC8h] BYREF
  _BYTE v261[24]; // [rsp+5D0h] [rbp-A78h] BYREF
  _QWORD *v262; // [rsp+5E8h] [rbp-A60h]
  unsigned int v263; // [rsp+830h] [rbp-818h]
  unsigned __int16 v264; // [rsp+834h] [rbp-814h]
  unsigned __int64 v265; // [rsp+836h] [rbp-812h]
  _BYTE v266[24]; // [rsp+870h] [rbp-7D8h] BYREF
  _QWORD *v267; // [rsp+888h] [rbp-7C0h]
  unsigned int v268; // [rsp+AD0h] [rbp-578h]
  unsigned __int16 ForeignFileId; // [rsp+AD4h] [rbp-574h]
  unsigned __int64 v270; // [rsp+AD6h] [rbp-572h]
  int v271; // [rsp+B10h] [rbp-538h] BYREF
  __int64 v272; // [rsp+B18h] [rbp-530h] BYREF
  char v273; // [rsp+B20h] [rbp-528h]
  int v274; // [rsp+B24h] [rbp-524h]
  __int128 v275; // [rsp+B30h] [rbp-518h]
  int v276; // [rsp+B40h] [rbp-508h]
  int v277; // [rsp+B44h] [rbp-504h]
  __int16 v278; // [rsp+B48h] [rbp-500h]
  __int16 v279; // [rsp+B4Ah] [rbp-4FEh]
  __int64 v280; // [rsp+B50h] [rbp-4F8h] BYREF
  int v281; // [rsp+B58h] [rbp-4F0h]
  __int16 v282; // [rsp+B5Ch] [rbp-4ECh]
  char v283; // [rsp+B5Eh] [rbp-4EAh]
  int v284; // [rsp+B60h] [rbp-4E8h] BYREF
  __int64 v285; // [rsp+B68h] [rbp-4E0h] BYREF
  char v286; // [rsp+B70h] [rbp-4D8h]
  int v287; // [rsp+B74h] [rbp-4D4h]
  __int128 v288; // [rsp+B80h] [rbp-4C8h]
  _DWORD v289[2]; // [rsp+B90h] [rbp-4B8h] BYREF
  __int16 v290; // [rsp+B98h] [rbp-4B0h]
  __int16 v291; // [rsp+B9Ah] [rbp-4AEh]
  GUID rguid; // [rsp+BA0h] [rbp-4A8h] BYREF
  GUID pguid; // [rsp+BB0h] [rbp-498h] BYREF
  int v294; // [rsp+BC0h] [rbp-488h] BYREF
  __int64 v295; // [rsp+BC8h] [rbp-480h] BYREF
  char v296; // [rsp+BD0h] [rbp-478h]
  int v297; // [rsp+BD4h] [rbp-474h]
  __int128 v298; // [rsp+BE0h] [rbp-468h]
  _DWORD v299[2]; // [rsp+BF0h] [rbp-458h] BYREF
  __int16 v300; // [rsp+BF8h] [rbp-450h]
  __int16 v301; // [rsp+BFAh] [rbp-44Eh]
  GUID v302; // [rsp+C00h] [rbp-448h]
  OLECHAR sz; // [rsp+C10h] [rbp-438h] BYREF
  char v304[72]; // [rsp+C12h] [rbp-436h] BYREF
  int v305; // [rsp+C5Ah] [rbp-3EEh]
  _BYTE v306[376]; // [rsp+C60h] [rbp-3E8h] BYREF
  int v307; // [rsp+DD8h] [rbp-270h]
  unsigned __int8 v308; // [rsp+DDCh] [rbp-26Ch]
  char v309; // [rsp+DDDh] [rbp-26Bh]
  char v310; // [rsp+DE2h] [rbp-266h]
  wchar_t v311[261]; // [rsp+DF0h] [rbp-258h] BYREF

  v221 = -2;
  v5 = a4;
  v199 = a4;
  v142 = a1;
  v180 = a1;
  v169 = a3;
  v192 = a4;
  v143 = a5;
  v135 = -1;
  v137 = 0;
  v139 = 0;
  v152 = -1;
  v154 = 0;
  v156 = 0;
  v162 = -1;
  v163 = 0;
  v130 = 0;
  memset_0(v306, 0, 0x188u);
  v307 = -1;
  v157 = 0;
  v129 = 0;
  v141 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + SystemThread_TlsIndex)
                                           + SystemThread_TlsOffset
                                           + 8LL)
                               + 96LL)
                   + 1160LL);
  v140 = (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                              + SystemThread_TlsIndex)
                                            + SystemThread_TlsOffset
                                            + 8LL)
                                + 96LL)
                    + 1144LL) >> 5)
       & 1;
  CAutoSetDiagOptions::CAutoSetDiagOptions((CAutoSetDiagOptions *)v175);
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&PerformanceCount);
    QuadPart = (DirtyPageMgr *)PerformanceCount.QuadPart;
  }
  else
  {
    QuadPart = MEMORY[0x7FFE0008];
  }
  v8 = *(_BYTE *)(v5 + 2);
  if ( (v8 & 8) != 0 )
  {
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1160LL) = a3;
    v8 = *(_BYTE *)(v5 + 2);
  }
  if ( (v8 & 0x40) != 0 )
  {
    v9 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL)
                   + 96LL);
    *(_DWORD *)(v9 + 1144) |= 0x20u;
  }
  CAutoSetDiagOptions::SetSystemTaskIfNoneSet((CAutoSetDiagOptions *)v175, 38);
  v11 = -1;
  if ( (*(_BYTE *)(v5 + 1) & 0x41) == 0 )
    v11 = 20000;
  if ( a3 != 1
    && (!(unsigned int)IsReplicatedMasterEnabled() && !(unsigned int)IsContainedAGEnabledInstance()
     || a3 != 32763 && (!(unsigned int)IsContainedAGEnabledInstance() || !IsContainedAgMasterDBId(a3))) )
  {
    HadrMetadataManager::GetAGIDByDBID(&v226, a3, 0);
    rguid = v226;
    if ( *(_QWORD *)&v226.Data1 != *(_QWORD *)&GUID_NULL.Data1 || *(_QWORD *)rguid.Data4 != *(_QWORD *)GUID_NULL.Data4 )
    {
      if ( (unsigned int)IsContainedAGEnabledInstance() )
      {
        v197 = 0;
        if ( (unsigned int)IsContainedAGEnabledInstance() )
        {
          Instance = CHadrArManager::GetInstance();
          ContainedAgControllerWithRef = CHadrArManager::GetContainedAgControllerWithRef(Instance, &rguid);
          v14 = ContainedAgControllerWithRef;
          v197 = ContainedAgControllerWithRef;
          if ( ContainedAgControllerWithRef )
          {
            CHadrArController::WaitForAgMasterReady(ContainedAgControllerWithRef, 0xFFFFFFFF);
            v15 = (char *)v14 + *(int *)(*((_QWORD *)v14 + 1) + 4LL) + 8;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))(v15);
          }
        }
      }
      v302 = rguid;
      StringFromGUID2(&rguid, &sz, 39);
      v305 = 0;
      LogSystemMetadata(L"HadrRuntimeCallbacks::WaitForAgMasterReady (%ls), return %ld", v304, 1);
    }
  }
  v165 = 0;
  v16 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v17 = *(_QWORD *)(v16 + 256);
  if ( !v17 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v17 = *(_QWORD *)(v16 + 256);
  }
  v166 = v17;
  v18 = *(_DWORD *)(v17 + 616);
  v165 = !(*(_BYTE *)(v17 + 616) & 1);
  *(_DWORD *)(v17 + 616) = v18 | 1;
  v19 = v142;
  while ( 1 )
  {
    if ( *(_QWORD *)(v5 + 72) )
    {
      LODWORD(v22) = 0;
    }
    else
    {
      v137 = a3;
      v136 = 5;
      v138 = 17;
      v20 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                + SystemThread_TlsIndex)
                                              + SystemThread_TlsOffset
                                              + 8LL)
                                  + 104LL)
                      + 40LL);
      LOBYTE(v126) = 0;
      LOBYTE(v10) = 5;
      v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, int, int, int))(*(_QWORD *)v20 + 160LL))(
              v20,
              a3,
              17,
              v10,
              v11,
              v139,
              v126);
      v22 = (unsigned int)v21;
      v135 = v21;
      v151 = v21;
      if ( v21 < 0 )
      {
        if ( *(char *)v5 >= 0 )
        {
          _mm_lfence();
          LOBYTE(v22) = 28;
          lck_StandardHandler((unsigned int)v135, v22);
          LODWORD(v22) = v151;
        }
        else if ( (unsigned int)(v21 + 3) <= 1 )
        {
          SOS_Task::ResetAbort(0x7FFFFFFF, (unsigned int)v21);
          SOS_Task::ResetDeadlock();
          *(_DWORD *)(v17 + 616) &= ~v165;
          CAutoSetDiagOptions::~CAutoSetDiagOptions((CAutoSetDiagOptions *)v175);
          v23 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL);
          if ( v140 )
            *(_DWORD *)(v23 + 1144) |= 0x20u;
          else
            *(_DWORD *)(v23 + 1144) &= ~0x20u;
          goto LABEL_33;
        }
      }
    }
    if ( a3 == 32764 )
      break;
    if ( a3 == 32765 )
    {
      v24 = *((_QWORD *)v19 + 14);
      goto LABEL_45;
    }
    if ( a3 == 0x7FFF )
    {
      v24 = *((_QWORD *)v19 + 11);
      goto LABEL_45;
    }
    if ( a3 <= *((_DWORD *)v142 + 19) && a3 )
    {
      v24 = *(_QWORD *)(*((_QWORD *)v142 + 5) + 8LL * (int)(a3 - 1));
      v19 = v142;
      goto LABEL_45;
    }
    v19 = v142;
LABEL_51:
    if ( (int)v22 >= 0 )
    {
      if ( (dword_10316ECB0 & 0x20) != 0 )
      {
        LODWORD(v124) = a3;
        ex_raise(9, 4, 16, 2, v124);
      }
      if ( dword_1033C1040 )
      {
        LODWORD(v124) = a3;
        ex_raise(9, 4, 16, 4, v124);
      }
      v26 = v143;
      if ( v143 )
      {
        v27 = 0;
      }
      else
      {
        v27 = (*(__int64 (__fastcall **)(struct IAutoXactFactory *))(*(_QWORD *)g_pAutoXactFactory + 8LL))(g_pAutoXactFactory);
        v130 = v27;
        (*(void (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v27 + 16LL))(
          v27,
          L"DBMgr::StartupDB",
          32);
        v26 = (struct BaseXact *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 64LL))(v27);
        v143 = v26;
      }
      v28 = DBMgr::InitAndSetDB(
              v142,
              a3,
              (struct DatabaseStartupInfo *)v5,
              v26,
              (wchar_t (*)[261])v311,
              (struct MDAttrDbReg *)v306);
      v191 = v28;
      HadrDbMgrAutoSetupContainedAgMaster::HadrDbMgrAutoSetupContainedAgMaster(
        (HadrDbMgrAutoSetupContainedAgMaster *)v183,
        *((unsigned __int16 *)v28 + 20));
      v145 = 0;
      if ( *((_DWORD *)v28 + 377) == 6 )
      {
        ThreadLocalStoragePointer = (struct BaseXact *)NtCurrentTeb()->ThreadLocalStoragePointer;
        if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                               + SystemThread_TlsOffset
                                               + 8LL)
                                   + 96LL)
                       + 1160LL) != a3 )
        {
          DBTABLE::CompleteOfflineStartup(v28, ThreadLocalStoragePointer);
          if ( v130 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v130 + 56LL))(v130) )
          {
            if ( *((struct BaseXact **)v28 + 12) == v143 )
              *((_QWORD *)v28 + 12) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v130 + 32LL))(v130);
          }
          HadrDbMgrAutoSetupContainedAgMaster::~HadrDbMgrAutoSetupContainedAgMaster((HadrDbMgrAutoSetupContainedAgMaster *)v183);
          *(_DWORD *)(v17 + 616) &= ~v165;
          CAutoSetDiagOptions::~CAutoSetDiagOptions((CAutoSetDiagOptions *)v175);
          v30 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL);
          if ( v140 )
            *(_DWORD *)(v30 + 1144) |= 0x20u;
          else
            *(_DWORD *)(v30 + 1144) &= ~0x20u;
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                              + SystemThread_TlsIndex)
                                            + SystemThread_TlsOffset
                                            + 8LL)
                                + 96LL)
                    + 1160LL) = v141;
          if ( v130 )
            (**(void (__fastcall ***)(__int64, __int64))v130)(v130, 1);
          AutoStartupLock::~AutoStartupLock((AutoStartupLock *)&v162);
          AutoDbLock::~AutoDbLock((AutoDbLock *)&v152);
          AutoDbLock::~AutoDbLock((AutoDbLock *)&v135);
          return;
        }
        v27 = v130;
      }
      AutoSetDBUpgradeThread::Set((AutoSetDBUpgradeThread *)&v145, v28);
      if ( (*(_BYTE *)(v5 + 3) & 4) != 0 )
      {
        LOBYTE(v124) = 0;
        LOBYTE(v31) = 3;
        v32 = AutoDbLock::Acquire(&v152, a3, v31, 0, (_DWORD)v124, 17);
        v151 = v32;
        if ( v32 >= 0 )
        {
          LOBYTE(v33) = 5;
          v32 = AutoStartupLock::Acquire(&v162, a3, v33, 0);
          v151 = v32;
          if ( v32 >= 0 && !*(_QWORD *)(v5 + 72) )
            *(_QWORD *)(v5 + 72) = &v135;
        }
        *(_BYTE *)(v5 + 3) &= ~4u;
        v34 = 0;
        if ( v32 >= 0 )
          v34 = 4;
        *(_BYTE *)(v5 + 3) |= v34;
      }
      v35 = v143;
      DBTABLE::Startup(v28, v143, (struct DatabaseStartupInfo *)v5);
      v36 = *((_DWORD *)v28 + 378);
      if ( (!v36 || (v150 = v36 == 5)) && (*((_DWORD *)v28 + 412) & 2) == 0 )
      {
        v37 = *((_BYTE *)v28 + 58);
        if ( (v37 & 0x20) == 0 || (v37 & 4) != 0 )
        {
          v127 = (*((_DWORD *)v28 + 158) & 0x400) != 0;
          LODWORD(v168) = dword_103172554;
          if ( dword_103172554 )
          {
            v146 = (unsigned __int8)byte_10317AC4A >> 3;
            if ( (byte_10317AC4A & 8) == 0 )
            {
              LODWORD(v144) = 0;
              v38 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              if ( *(_QWORD *)v38
                && (v39 = *(__int64 **)(*(_QWORD *)v38 + 56LL), (v40 = (struct CSessionTraceFlags *)*v39) != 0) )
              {
                v173 = *v39;
                if ( CSessionTraceFlags::CheckSessionTraceInternal(v40, 0x653u) )
                {
LABEL_91:
                  v27 = v130;
                  goto LABEL_92;
                }
              }
              else
              {
                v173 = 0;
              }
              if ( a3 <= 3
                || a3 == 0x7FFF
                || *(char *)v5 >= 0 && (*(_BYTE *)(v5 + 1) & 1) == 0
                || (*((_DWORD *)v28 + 158) & 0x200000) != 0 )
              {
                goto LABEL_91;
              }
              v27 = v130;
              if ( v127 != v308 >> 7 )
              {
                v129 = 1;
                v144 = (RecoveryUnit **)((char *)v28 + 4624);
                v41 = *((_QWORD *)v28 + 578);
                v167 = v41;
                goto LABEL_93;
              }
            }
          }
LABEL_92:
          v144 = (RecoveryUnit **)((char *)v28 + 4624);
          v41 = *((_QWORD *)v28 + 578);
          v167 = v41;
          if ( a3 < 3 )
          {
LABEL_96:
            if ( !v129 )
            {
LABEL_131:
              v168 = (RecoveryUnit **)((char *)v28 + 4624);
              if ( dword_103172528 )
              {
                v284 = 0;
                v220 = &v285;
                v285 = 0;
                v286 = 0;
                v287 = 0;
                v193 = v289;
                v289[0] = 0;
                v289[1] = 0;
                v290 = 0;
                v291 = 0;
                v288 = 0;
                if ( byte_10316E626 )
                {
                  v193 = 0;
                  BootPagePtr::Init(&v284, 0, *((_QWORD *)v28 + 578), 0);
                  BootPagePtr::GetAccess(&v284, 2);
                  if ( (v284 & 1) != 0 )
                  {
                    v128 = *(_BYTE *)(v288 + 1780) & 1;
                  }
                  else
                  {
                    v128 = *(_BYTE *)(*(unsigned __int16 *)(*(_QWORD *)v285 + 8190LL) + *(_QWORD *)v285 + 1780LL) & 1;
                    PageRef::Unlatch((PageRef *)&v285);
                    v144 = v168;
                    if ( (_QWORD)v288 )
                    {
                      v222 = v288;
                      operator delete((void *)v288, 0x6FAu);
                      *(_QWORD *)&v288 = 0;
                      v144 = v168;
                    }
                  }
                  BootPagePtr::Release((BootPagePtr *)&v284, 0);
                  if ( v128 )
                  {
                    RecoveryUnit::SetLogTruncationFlagForAuxiliaryReplica(*v144, 1);
                    LogSystemMetadata(L"Current SQL Azure instance is hosted on Auxiliary Replica");
                  }
                }
                BootPagePtr::~BootPagePtr((BootPagePtr *)&v284);
              }
              if ( (unsigned int)RecoveryUnit::IsUpdateable((RecoveryUnit *)v41) )
              {
                if ( (*(_BYTE *)(v5 + 2) & 0x20) == 0 )
                {
                  v147 = byte_1031852E4;
                  if ( !byte_1031852E4 || !*(_QWORD *)(*(_QWORD *)(v41 + 1712) + 5320LL) )
                  {
                    v271 = 0;
                    v223 = &v272;
                    v272 = 0;
                    v273 = 0;
                    v274 = 0;
                    v276 = 0;
                    v277 = 0;
                    v278 = 0;
                    v279 = 0;
                    v275 = 0;
                    v194 = 0;
                    BootPagePtr::Init(&v271, 0, v41, 0);
                    BootPagePtr::GetAccess(&v271, 2);
                    if ( (v271 & 1) != 0 )
                    {
                      v51 = *(_WORD *)(v275 + 390);
                    }
                    else
                    {
                      v51 = *(_WORD *)(*(unsigned __int16 *)(*(_QWORD *)v272 + 8190LL) + *(_QWORD *)v272 + 390LL);
                      PageRef::Unlatch((PageRef *)&v272);
                      if ( (_QWORD)v275 )
                      {
                        v195 = v275;
                        operator delete((void *)v275, 0x6FAu);
                        *(_QWORD *)&v275 = 0;
                      }
                    }
                    BootPagePtr::Release((BootPagePtr *)&v271, 0);
                    if ( (v51 & 2) != 0 && *(_BYTE *)(v41 + 27464) )
                    {
                      LogSystemMetadata(L"Invalidating RbIoFlags on VLDB Reverse Migration target.");
                      BootPagePtr::ResetRbIoFlags((BootPagePtr *)&v271, (struct RecoveryUnit *)v41);
                      LogSystemMetadata(L"Resetting database MaxSizeBytes for VLDB Reverse Migration target.");
                      BootPagePtr::SetDatabaseMaxSizeBytes((BootPagePtr *)&v271, (struct RecoveryUnit *)v41, 0);
                    }
                    v195 = 0;
                    BootPagePtr::Init(&v271, 0, v41, 0);
                    BootPagePtr::GetAccess(&v271, 4);
                    if ( (v271 & 1) != 0 )
                      v52 = v275;
                    else
                      v52 = *(_QWORD *)v272 + *(unsigned __int16 *)(*(_QWORD *)v272 + 8190LL);
                    v144 = (RecoveryUnit **)v52;
                    v228 = &v177;
                    v225 = &v186;
                    v186 = *(_QWORD *)(v52 + 588);
                    v187 = *(_WORD *)(v52 + 596);
                    v177 = v186;
                    v178 = v187;
                    v179 = 0;
                    RecoveryUnit::SetUndoLSN(v41, &v177);
                    v53 = -1;
                    do
                      ++v53;
                    while ( *((_WORD *)v28 + v53 + 468) );
                    v211 = 2 * v53;
                    if ( !memcmp_0((char *)v28 + 936, (char *)v144 + 52, (unsigned int)(2 * v53)) )
                    {
                      v60 = 0;
                    }
                    else
                    {
                      v54 = 0;
                      v198 = 0;
                      v55 = 0;
                      v56 = v144;
                      while ( v55 < 0x100 )
                      {
                        *((_BYTE *)v56 + v54 + 52) = 32;
                        v54 = v55 + 1;
                        v198 = ++v55;
                      }
                      v57 = -1;
                      do
                        ++v57;
                      while ( *((_WORD *)v28 + v57 + 468) );
                      v212 = 2 * v57;
                      if ( (unsigned int)(2 * v57) >= 0x100 )
                      {
                        LODWORD(v59) = 256;
                      }
                      else
                      {
                        v58 = -1;
                        do
                          ++v58;
                        while ( *((_WORD *)v28 + v58 + 468) );
                        v59 = 2 * v58;
                        v213 = v59;
                      }
                      *((_DWORD *)v56 + 77) = v59;
                      memmove((char *)v56 + 52, (char *)v28 + 936, (unsigned int)v59);
                      v60 = 1;
                    }
                    BootPagePtr::ReleaseAccess((BootPagePtr *)&v271, v60);
                    BootPagePtr::~BootPagePtr((BootPagePtr *)&v271);
                    v5 = v199;
                  }
                }
              }
              DBStartupTimer::DBStartupTimer(&v208, 9, (char *)v28 + 56);
              if ( (*((_BYTE *)v28 + 57) & 0x20) == 0 )
              {
                v61 = *((_BYTE *)v28 + 56);
                if ( (v61 & 8) == 0
                  && (*((_BYTE *)v28 + 58) & 0x18) == 0
                  && (v61 & 0x20) == 0
                  && (*((_BYTE *)v28 + 59) & 1) == 0
                  && (v61 & 0x10) == 0
                  && !*((_WORD *)v28 + 764)
                  && !*((_DWORD *)v28 + 1164) )
                {
                  if ( (unsigned int)DBTABLE::IsOnline(v28) )
                  {
                    if ( (**(unsigned __int8 (__fastcall ***)(__int64))qword_1031C4710)(qword_1031C4710) )
                    {
                      if ( a3 > 3 && a3 != 0x7FFF && !FSystemDBName((const wchar_t *)v28 + 468, *((_DWORD *)v28 + 232)) )
                      {
                        LOBYTE(v124) = 1;
                        v176 = (*(__int64 (__fastcall **)(__int64, struct DBTABLE *, struct BaseXact *, _QWORD, _DWORD))(*(_QWORD *)qword_1031C4710 + 40LL))(
                                 qword_1031C4710,
                                 v28,
                                 v143,
                                 0,
                                 (_DWORD)v124);
                        if ( v176 < 0 )
                        {
                          _mm_lfence();
                          LODWORD(v125) = v176;
                          LODWORD(v124) = 13030;
                          scierrlogwithstate(0x827Du, 10, 2, 13105, v124, v125);
                          v27 = v130;
                          v41 = v167;
                        }
                      }
                    }
                  }
                }
              }
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v200);
                v62 = (DirtyPageMgr *)v200.QuadPart;
                v201 = (DirtyPageMgr *)v200.QuadPart;
              }
              else
              {
                v62 = MEMORY[0x7FFE0008];
                v160 = (__int64)MEMORY[0x7FFE0008];
                v201 = MEMORY[0x7FFE0008];
                v27 = v130;
                v41 = v167;
              }
              if ( (unsigned __int64)v62 < v208 )
              {
                v63 = 0;
                v160 = 0;
              }
              else
              {
                v63 = (__int64)v62 - v208;
                v160 = v63;
              }
              v214 = v63;
              *(_QWORD *)(v210 + 8LL * v209 + 104) += v63;
              DBStartupTimer::DBStartupTimer(&v205, 10, (char *)v28 + 56);
              HadrRecoveryCallbacks::ReportFullTextRecoveryStarted((struct RecoveryUnit *)v41);
              if ( (!(unsigned int)DBTABLE::ShouldSkipFulltextRecovery(v28, (struct DatabaseStartupInfo *)v5)
                 || *((_DWORD *)v28 + 378) == 5
                 || (*((_DWORD *)v28 + 158) & 0x200400) != 0)
                && (*(_BYTE *)v5 & 8) == 0
                && *(int *)(*((_QWORD *)v28 + 578) + 1648LL) > 6 )
              {
                (*(void (__fastcall **)(_QWORD, struct DBTABLE *, struct BaseXact *))(**((_QWORD **)v142 + 28) + 8LL))(
                  *((_QWORD *)v142 + 28),
                  v28,
                  v143);
              }
              if ( !(unsigned int)DBTABLE::ShouldSkipFulltextRecovery(v28, (struct DatabaseStartupInfo *)v5) )
                (*(void (__fastcall **)(_QWORD, struct DBTABLE *, struct BaseXact *))(**((_QWORD **)v142 + 28) + 96LL))(
                  *((_QWORD *)v142 + 28),
                  v28,
                  v143);
              if ( (*(_BYTE *)(v5 + 2) & 8) != 0 )
                (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v142 + 28) + 48LL))(*((_QWORD *)v142 + 28), a3);
              if ( (*(_BYTE *)(v5 + 3) & 8) != 0
                && !(unsigned int)DBTABLE::ShouldSkipFulltextRecovery(v28, (struct DatabaseStartupInfo *)v5) )
              {
                LOWORD(v64) = RecoveryUnit::GetRestoreFlags(*((RecoveryUnit **)v28 + 578));
                v134 = (v64 >> 9) & 1;
                if ( ((unsigned int)IsReplicatedMasterEnabled() || byte_10316E81B || (byte_10317AFB1 & 1) != 0)
                  && (byte_10316E615 || (byte_10317AF38 & 4) != 0) )
                {
                  if ( (*(_BYTE *)(v5 + 2) & 0x48) == 0x48 || v134 )
                    LOBYTE(v65) = 1;
                  else
                    v65 = 0;
                  (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)v142 + 28) + 40LL))(
                    *((_QWORD *)v142 + 28),
                    a3,
                    v65);
                }
                else
                {
                  if ( (*(_BYTE *)(v5 + 2) & 0x48) == 0x48 || (v66 = 0, v134) )
                    v66 = 1;
                  (*(void (__fastcall **)(_QWORD, _QWORD, __int64, struct BaseXact *))(**((_QWORD **)v142 + 28) + 32LL))(
                    *((_QWORD *)v142 + 28),
                    a3,
                    v66,
                    v143);
                }
                if ( v134 )
                  RecoveryUnit::ChangeRestoreFlags(*((RecoveryUnit **)v28 + 578), 0, 0x200u);
              }
              HadrRecoveryCallbacks::ReportFullTextRecoveryCompleted((struct RecoveryUnit *)v41);
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v202);
                v67 = (DirtyPageMgr *)v202.QuadPart;
                v203 = (DirtyPageMgr *)v202.QuadPart;
              }
              else
              {
                v67 = MEMORY[0x7FFE0008];
                v159 = (__int64)MEMORY[0x7FFE0008];
                v203 = MEMORY[0x7FFE0008];
                v27 = v130;
              }
              if ( (unsigned __int64)v67 < v205 )
              {
                v68 = 0;
                v159 = 0;
              }
              else
              {
                v68 = (__int64)v67 - v205;
                v159 = v68;
              }
              v215 = v68;
              *(_QWORD *)(v207 + 8LL * v206 + 104) += v68;
              if ( a3 == 2 && !dword_103172550 )
              {
                v69 = *(_BYTE *)((*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf
                                                                                          + 504LL))(s_pServerConf)
                               + 269) != 0;
                if ( *((_DWORD *)s_pServerConf + 2) == 2
                  && (dword_103172538
                   || *((_BYTE *)s_pServerConf + 17)
                   && !dword_10316ECB4
                   && !dword_10317253C
                   && !dword_103172574
                   && (!dword_103185704 || !dword_103172528))
                  && (dword_10317A9FC & 0x20) == 0
                  && ((byte_10316EB6B || (qword_10317AD66 & 0x80u) != 0LL) && (qword_10317AD66 & 0x100) == 0 || v69) )
                {
                  CHkTempdbTables::SetupHkTempdb(v28);
                }
              }
              if ( v27 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v27 + 56LL))(v27) )
              {
                if ( *((struct BaseXact **)v28 + 12) == v143 )
                  *((_QWORD *)v28 + 12) = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 32LL))(v27);
              }
              v72 = 1;
              if ( (byte_10317AC61 & 8) == 0 )
              {
                v70 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset;
                if ( !*(_QWORD *)v70
                  || (v71 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v70 + 56LL)) == 0
                  || !CSessionTraceFlags::CheckSessionTraceInternal(v71, 0x70Bu) )
                {
                  v72 = 0;
                }
              }
              v131 = v72;
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v204);
                v73 = (DirtyPageMgr *)v204.QuadPart;
              }
              else
              {
                v164 = (__int64)MEMORY[0x7FFE0008];
                v73 = MEMORY[0x7FFE0008];
              }
              v188 = v73;
              if ( v73 < QuadPart )
              {
                v74 = 0;
                v164 = 0;
              }
              else
              {
                v74 = v73 - QuadPart;
                v164 = v74;
              }
              v216 = v74;
              if ( v74 == -1 )
              {
                v75 = -1;
              }
              else if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                v75 = v74 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
              }
              else
              {
                v75 = v74 / 0x989680;
              }
              v132 = v75 > 0xA;
              if ( !v72 && v75 <= 0xA )
              {
                v164 = 0x200000000000003LL;
                if ( (dword_10317F6CC & 0x2000000) == 0 )
                {
LABEL_306:
                  AutoSetDBUpgradeThread::Clear((AutoSetDBUpgradeThread *)&v145);
                  if ( RecoveryUnit::IsTraceEnabled() )
                    RecoveryUnit::PrintTrace(*((RecoveryUnit **)v28 + 578), L"%ls done.", L"DBMgr::StartupDB");
                  HadrRecoveryCallbacks::ReportStartupCompleted(*((struct RecoveryUnit **)v28 + 578));
                  v160 = 0x2000000000000003LL;
                  if ( (dword_10317F6CC & 0x20000000) != 0 )
                  {
                    v230 = 0;
                    v231 = 5;
                    v232 = 0;
                    v233 = &v236;
                    v234 = &v256;
                    v257 = 0;
                    v258 = 0;
                    v235 = 0;
                    v259 = 0;
                    v236 = &v260;
                    v237 = 36;
                    v238 = 4;
                    v239 = 0;
                    v240 = 0;
                    v241 = 0;
                    v242 = 1;
                    v243 = 0;
                    v244 = 0;
                    v245 = 0;
                    v246 = 2;
                    v247 = 0;
                    v248 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
                    v249 = 16;
                    v250 = 3;
                    v251 = 0;
                    v252 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
                    v253 = 16;
                    v254 = 4;
                    v255 = 0;
                    v260 = a3;
                    if ( v28 == (struct DBTABLE *)-936LL )
                    {
                      v97 = 0;
                    }
                    else
                    {
                      v96 = -1;
                      do
                        ++v96;
                      while ( *((_WORD *)v28 + v96 + 468) );
                      v97 = 2 * v96;
                    }
                    v240 = (char *)v28 + 936;
                    v241 = v97;
                    v242 = 1;
                    v243 = 0;
                    v170 = 0;
                    v98 = ((__int64 (__fastcall *)(struct DBTABLE *, int *))g_dbtableFactory[2])(v28, &v170);
                    v99 = (unsigned int *)v98;
                    if ( v98 )
                    {
                      v100 = -1;
                      do
                        ++v100;
                      while ( *(_WORD *)(v98 + 2 * v100) );
                      v101 = 2 * v100;
                    }
                    else
                    {
                      v101 = 0;
                    }
                    v102 = v233;
                    v233[4] = v99;
                    *((_DWORD *)v102 + 10) = v101;
                    *((_WORD *)v102 + 22) = 2;
                    *((_WORD *)v102 + 23) = 0;
                    v103 = v233;
                    v233[6] = (unsigned int *)((char *)v28 + 596);
                    *((_DWORD *)v103 + 14) = 16;
                    *((_WORD *)v103 + 30) = 3;
                    *((_WORD *)v103 + 31) = 0;
                    v104 = v233;
                    v233[8] = (unsigned int *)((char *)v28 + 580);
                    *((_DWORD *)v104 + 18) = 16;
                    *((_WORD *)v104 + 38) = 4;
                    *((_WORD *)v104 + 39) = 0;
                    XeSqlPkg::database_started::Publish((XeSqlPkg::database_started *)v229);
                  }
                  v105 = v142;
                  v115 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset;
                  v116 = *(struct Worker **)(v115 + 256);
                  if ( !v116 )
                  {
                    SystemThread::MakeMiniSOSThread(0);
                    v116 = *(struct Worker **)(v115 + 256);
                  }
                  if ( *((_DWORD *)v116 + 139) )
                    ExceptionPostCatchActions(v116);
                  if ( v145 )
                  {
                    v117 = *(_QWORD *)(v145 + 4624);
                    if ( v117 )
                      *(_QWORD *)(v117 + 7216) = 0;
                    v145 = 0;
                  }
                  v118 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                 + SystemThread_TlsIndex)
                                               + SystemThread_TlsOffset)
                                   + 72LL);
                  if ( v185 && (unsigned int)IsContainedAGEnabledInstance() )
                  {
                    *(_OWORD *)(v118 + 4912) = v184;
                    *(_WORD *)(v118 + 4928) = v183[0];
                    *(_WORD *)(v118 + 4930) = v183[1];
                  }
                  if ( *(char *)v5 < 0
                    && (v309 & 4) != 0
                    && (v310 & 2) == 0
                    && !*(_QWORD *)(*((_QWORD *)v28 + 578) + 1832LL)
                    && (byte_10317AD49 & 0x10) == 0 )
                  {
                    if ( v135 >= 0 )
                    {
                      v119 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                 + SystemThread_TlsIndex)
                                                               + SystemThread_TlsOffset
                                                               + 8LL)
                                                   + 104LL)
                                       + 40LL);
                      LODWORD(v124) = v139;
                      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, wchar_t *))(*(_QWORD *)v119 + 168LL))(
                        v119,
                        v137,
                        v138,
                        v136,
                        v124);
                      v135 = -1;
                    }
                    if ( v152 >= 0 )
                    {
                      v120 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                 + SystemThread_TlsIndex)
                                                               + SystemThread_TlsOffset
                                                               + 8LL)
                                                   + 104LL)
                                       + 40LL);
                      LODWORD(v124) = v156;
                      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, wchar_t *))(*(_QWORD *)v120 + 168LL))(
                        v120,
                        v154,
                        v155,
                        v153,
                        v124);
                      v152 = -1;
                    }
                    DBMgr::TryToClose(
                      v105,
                      *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset),
                      a3);
                  }
                  *(_DWORD *)(v166 + 616) &= ~v165;
                  CAutoSetDiagOptions::~CAutoSetDiagOptions((CAutoSetDiagOptions *)v175);
                  v121 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                 + SystemThread_TlsIndex)
                                               + SystemThread_TlsOffset
                                               + 8LL)
                                   + 96LL);
                  if ( v140 )
                    *(_DWORD *)(v121 + 1144) |= 0x20u;
                  else
                    *(_DWORD *)(v121 + 1144) &= ~0x20u;
                  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                      + SystemThread_TlsIndex)
                                                    + SystemThread_TlsOffset
                                                    + 8LL)
                                        + 96LL)
                            + 1160LL) = v141;
                  if ( v130 )
                    (**(void (__fastcall ***)(__int64, __int64))v130)(v130, 1);
                  if ( v162 >= 0 )
                  {
                    v283 = 2;
                    v282 = v163;
                    v280 = 5;
                    v281 = 0;
                    CSessionLockList::ReleaseLock(
                      *(CSessionLockList **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                         + SystemThread_TlsIndex)
                                                       + SystemThread_TlsOffset)
                                           + 88LL),
                      (struct LockRes *)&v280);
                    v162 = -1;
                  }
                  if ( v152 >= 0 )
                  {
                    v122 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + SystemThread_TlsIndex)
                                                             + SystemThread_TlsOffset
                                                             + 8LL)
                                                 + 104LL)
                                     + 40LL);
                    LODWORD(v124) = v156;
                    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, wchar_t *))(*(_QWORD *)v122 + 168LL))(
                      v122,
                      v154,
                      v155,
                      v153,
                      v124);
                    v152 = -1;
                  }
                  goto LABEL_383;
                }
              }
              pguid = GUID_NULL;
              if ( CoCreateGuid(&pguid) < 0 )
                ex_raise(36, 8, 16, 3);
              v159 = 0x200000000000003LL;
              if ( (dword_10317F6CC & 0x2000000) != 0 )
              {
                XeSqlPkg::database_recovery_times::database_recovery_times((XeSqlPkg::database_recovery_times *)v266);
                v268 = a3;
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&v189);
                  v76 = (DirtyPageMgr *)v189.QuadPart;
                }
                else
                {
                  v161 = (__int64)MEMORY[0x7FFE0008];
                  v76 = MEMORY[0x7FFE0008];
                }
                v190 = v76;
                if ( v76 < QuadPart )
                {
                  v77 = 0;
                  v161 = 0;
                }
                else
                {
                  v77 = v76 - QuadPart;
                  v161 = v77;
                }
                v217 = v77;
                if ( v77 == -1 )
                {
                  v78 = -1;
                }
                else if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  v78 = 1000 * v77 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                }
                else
                {
                  v78 = v77 / 0x2710;
                }
                v270 = v78;
                XeSqlPkg::redo_pfs_page_lsn_inconsistency::Setredo_lsn(
                  (XeSqlPkg::redo_pfs_page_lsn_inconsistency *)v266,
                  (const wchar_t *const)v28 + 468);
                v174 = 0;
                v79 = (const wchar_t *)((__int64 (__fastcall *)(struct DBTABLE *, int *))g_dbtableFactory[2])(
                                         v28,
                                         &v174);
                XeSqlPkg::dw_backup_app_lock_end::Setphysical_database_name(
                  (XeSqlPkg::dw_backup_app_lock_end *)v266,
                  v79);
                v80 = v267;
                v267[6] = (char *)v28 + 596;
                *((_DWORD *)v80 + 14) = 16;
                *((_WORD *)v80 + 30) = 5;
                *((_WORD *)v80 + 31) = 0;
                v81 = v267;
                v267[8] = (char *)v28 + 580;
                *((_DWORD *)v81 + 18) = 16;
                *((_WORD *)v81 + 38) = 6;
                *((_WORD *)v81 + 39) = 0;
                v82 = v267;
                v267[10] = &pguid;
                *((_DWORD *)v82 + 22) = 16;
                *((_WORD *)v82 + 46) = 7;
                *((_WORD *)v82 + 47) = 0;
                v83 = -1;
                do
                  ++v83;
                while ( aTotal_0[v83] );
                v84 = v267;
                v267[12] = L"Total";
                *((_DWORD *)v84 + 26) = 2 * v83;
                *((_WORD *)v84 + 54) = 8;
                *((_WORD *)v84 + 55) = 0;
                v85 = (struct RecoveryUnit *)*((_QWORD *)v28 + 578);
                if ( !v85 )
                {
                  LODWORD(v124) = 0;
                  ex_raise(9, 30, 21, 1, v124, (char *)v28 + 936);
                }
                ForeignFileId = GetForeignFileId(v85);
                XeSqlPkg::database_recovery_times::Publish((XeSqlPkg::database_recovery_times *)v266);
              }
              v86 = 4;
              v171 = 4;
              v87 = 4;
              while ( 1 )
              {
                if ( v87 >= 43 )
                  goto LABEL_306;
                v88 = *((_QWORD *)v28 + v87 + 20);
                if ( v88 == -1 )
                {
                  v89 = -1;
LABEL_289:
                  if ( v131 || v89 >= 0x64 )
                  {
                    if ( v132 || v131 )
                    {
                      v90 = (const wchar_t *)((char *)v28 + 936);
                      LogSystemMetadata(
                        L"DBSTARTUP (%ls, %d): %ls took %I64d ms\n",
                        (char *)v28 + 936,
                        a3,
                        (&DBStartupTimeNames)[v86],
                        v89);
                    }
                    else
                    {
                      v90 = (const wchar_t *)((char *)v28 + 936);
                    }
                    v161 = 0x200000000000003LL;
                    if ( (dword_10317F6CC & 0x2000000) != 0 )
                    {
                      XeSqlPkg::database_recovery_times::database_recovery_times((XeSqlPkg::database_recovery_times *)v261);
                      v263 = a3;
                      v265 = v89;
                      XeSqlPkg::redo_pfs_page_lsn_inconsistency::Setredo_lsn(
                        (XeSqlPkg::redo_pfs_page_lsn_inconsistency *)v261,
                        v90);
                      v172 = 0;
                      v91 = (const wchar_t *)((__int64 (__fastcall *)(struct DBTABLE *, int *))g_dbtableFactory[2])(
                                               v28,
                                               &v172);
                      XeSqlPkg::dw_backup_app_lock_end::Setphysical_database_name(
                        (XeSqlPkg::dw_backup_app_lock_end *)v261,
                        v91);
                      v92 = v262;
                      v262[6] = (char *)v28 + 596;
                      *((_DWORD *)v92 + 14) = 16;
                      *((_WORD *)v92 + 30) = 5;
                      *((_WORD *)v92 + 31) = 0;
                      v93 = v262;
                      v262[8] = (char *)v28 + 580;
                      *((_DWORD *)v93 + 18) = 16;
                      *((_WORD *)v93 + 38) = 6;
                      *((_WORD *)v93 + 39) = 0;
                      v94 = v262;
                      v262[10] = &pguid;
                      *((_DWORD *)v94 + 22) = 16;
                      *((_WORD *)v94 + 46) = 7;
                      *((_WORD *)v94 + 47) = 0;
                      XeSqlPkg::database_recovery_times::Setrecovery_step(
                        (XeSqlPkg::database_recovery_times *)v261,
                        (const wchar_t *const)(&DBStartupTimeNames)[v86]);
                      v95 = (struct RecoveryUnit *)*((_QWORD *)v28 + 578);
                      if ( !v95 )
                      {
                        LODWORD(v124) = 0;
                        ex_raise(9, 30, 21, 1, v124, v90);
                      }
                      v264 = GetForeignFileId(v95);
                      XeSqlPkg::database_recovery_times::Publish((XeSqlPkg::database_recovery_times *)v261);
                    }
                    v171 = ++v86;
                    v87 = v86;
                  }
                  else
                  {
                    v171 = ++v86;
                    v87 = v86;
                  }
                }
                else
                {
                  if ( Base_PublicGlobals::sm_invariantTscAvailable )
                    v89 = 1000 * v88 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                  else
                    v89 = v88 / 0x2710;
                  if ( v89 )
                    goto LABEL_289;
                  v171 = ++v86;
                  v87 = v86;
                }
              }
            }
LABEL_97:
            if ( (unsigned int)RecoveryUnit::IsUpdateable((RecoveryUnit *)v41) )
            {
              v294 = 0;
              v224 = &v295;
              v295 = 0;
              v296 = 0;
              v297 = 0;
              v227 = v299;
              v299[0] = 0;
              v299[1] = 0;
              v300 = 0;
              v301 = 0;
              v298 = 0;
              *(_BYTE *)(v41 + 7376) &= ~2u;
              v181 = 0;
              v182 = 0;
              if ( *(_QWORD *)(v41 + 1832) )
                RecoveryUnit::GetRecoveryMgrLock(v41, &v181, 1);
              v133 = *((_DWORD *)v28 + 158);
              v42 = (struct XDES *)(*(__int64 (__fastcall **)(struct BaseXact *, __int64))(*(_QWORD *)v143 + 280LL))(
                                     v143,
                                     v41);
              BootPagePtr::SetDbinfoStatusWithXact((BootPagePtr *)&v294, v42, v133 & 0xFFDB783D);
              if ( (v133 & 8) != 0 )
              {
                v158 = 2;
                v43 = 2;
              }
              else if ( (v133 & 4) != 0 )
              {
                v158 = 1;
                v43 = 1;
              }
              else
              {
                v158 = 0;
                v43 = 0;
              }
              if ( *(_DWORD *)(v41 + 2164) != v43 )
              {
                if ( (v133 & 8) != 0 )
                  v44 = 2;
                else
                  v44 = (v133 & 4) != 0;
                *(_DWORD *)(v41 + 2164) = v44;
              }
              if ( v182 )
              {
                SOS_RWLock::ReleaseLock(v181, v182);
                v182 = 0;
              }
              BootPagePtr::~BootPagePtr((BootPagePtr *)&v294);
            }
            v45 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            v46 = *(_QWORD *)(v45 + 256);
            if ( !v46 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v46 = *(_QWORD *)(v45 + 256);
            }
            v47 = g_metadataFactory(
                    *(_QWORD *)(v46 + 1000),
                    v143,
                    "sql\\ntdbms\\storeng\\dfs\\manager\\dbmgr.cpp",
                    5176);
            v48 = v47;
            v218 = v47;
            if ( v129 )
            {
              v49 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 72LL))(v47);
              v50 = v127;
              v308 = (v127 << 7) | v308 & 0x7F;
              (*(void (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v49 + 96LL))(v49, a3, 96, v306);
            }
            else
            {
              v50 = v127;
            }
            v173 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v48 + 88LL))(v48);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v173 + 24LL))(v173, a3, 0, &v157);
            if ( v129 || (v157 & 0x800000000LL) != 0 && !v50 )
            {
              BYTE4(v157) = (8 * (v50 & 1)) | BYTE4(v157) & 0xF3 | (4 * (v50 & 1)) & 0xF7;
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64, __int64 *))(*(_QWORD *)v173 + 32LL))(
                v173,
                a3,
                0,
                12,
                &v157);
            }
            v219 = v48;
            (**(void (__fastcall ***)(__int64, __int64))v48)(v48, 1);
            v27 = v130;
            v41 = v167;
            goto LABEL_131;
          }
LABEL_93:
          if ( (*(_BYTE *)(v41 + 7376) & 2) != 0 && DBTABLE::IsOkToWrite(v28) && (*(_BYTE *)(v5 + 2) & 0x20) == 0 )
            goto LABEL_97;
          goto LABEL_96;
        }
      }
      if ( v27 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v27 + 56LL))(v27) )
      {
        if ( *((struct BaseXact **)v28 + 12) == v35 )
          *((_QWORD *)v28 + 12) = 0;
        v106 = *(_QWORD *)v27;
        if ( (*((_DWORD *)v28 + 158) & 0x140) != 0 )
          (*(void (__fastcall **)(__int64))(v106 + 48))(v27);
        else
          (*(void (__fastcall **)(__int64))(v106 + 32))(v27);
        v107 = v145;
        if ( v145 )
        {
          v148 = 0;
          for ( i = 0; !i; i = 1 )
          {
            v109 = *(_QWORD *)(v107 + 4624);
            if ( v109 )
              *(_QWORD *)(v109 + 7216) = 0;
            v148 = 1;
          }
          v145 = 0;
        }
        HadrDbMgrAutoSetupContainedAgMaster::~HadrDbMgrAutoSetupContainedAgMaster((HadrDbMgrAutoSetupContainedAgMaster *)v183);
        *(_DWORD *)(v166 + 616) &= ~v165;
        CAutoSetDiagOptions::~CAutoSetDiagOptions((CAutoSetDiagOptions *)v175);
        v110 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL)
                         + 96LL);
        if ( v140 )
          *(_DWORD *)(v110 + 1144) |= 0x20u;
        else
          *(_DWORD *)(v110 + 1144) &= ~0x20u;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset
                                          + 8LL)
                              + 96LL)
                  + 1160LL) = v141;
        if ( !v130 )
          goto LABEL_340;
      }
      else
      {
        v111 = v145;
        if ( v145 )
        {
          v149 = 0;
          for ( j = 0; !j; j = 1 )
          {
            v113 = *(_QWORD *)(v111 + 4624);
            if ( v113 )
              *(_QWORD *)(v113 + 7216) = 0;
            v149 = 1;
          }
          v145 = 0;
        }
        HadrDbMgrAutoSetupContainedAgMaster::~HadrDbMgrAutoSetupContainedAgMaster((HadrDbMgrAutoSetupContainedAgMaster *)v183);
        *(_DWORD *)(v166 + 616) &= ~v165;
        CAutoSetDiagOptions::~CAutoSetDiagOptions((CAutoSetDiagOptions *)v175);
        v114 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL)
                         + 96LL);
        if ( v140 )
          *(_DWORD *)(v114 + 1144) |= 0x20u;
        else
          *(_DWORD *)(v114 + 1144) &= ~0x20u;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset
                                          + 8LL)
                              + 96LL)
                  + 1160LL) = v141;
        if ( !v130 )
          goto LABEL_340;
      }
      (**(void (__fastcall ***)(__int64, __int64))v130)(v130, 1);
LABEL_340:
      AutoStartupLock::~AutoStartupLock((AutoStartupLock *)&v162);
      AutoDbLock::~AutoDbLock((AutoDbLock *)&v152);
      AutoDbLock::~AutoDbLock((AutoDbLock *)&v135);
      return;
    }
  }
  v24 = *((_QWORD *)v19 + 13);
LABEL_45:
  if ( !v24 || *(_QWORD *)(v5 + 48) )
    goto LABEL_51;
  *(_DWORD *)(v17 + 616) &= ~v165;
  CAutoSetDiagOptions::~CAutoSetDiagOptions((CAutoSetDiagOptions *)v175);
  v25 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset
                              + 8LL)
                  + 96LL);
  if ( v140 )
    *(_DWORD *)(v25 + 1144) |= 0x20u;
  else
    *(_DWORD *)(v25 + 1144) &= ~0x20u;
LABEL_33:
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                    + SystemThread_TlsOffset
                                    + 8LL)
                        + 96LL)
            + 1160LL) = v141;
LABEL_383:
  if ( v135 >= 0 )
  {
    v123 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                               + SystemThread_TlsIndex)
                                             + SystemThread_TlsOffset
                                             + 8LL)
                                 + 104LL)
                     + 40LL);
    LODWORD(v124) = v139;
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, wchar_t *))(*(_QWORD *)v123 + 168LL))(
      v123,
      v137,
      v138,
      v136,
      v124);
  }
}

```

## disassembly

```asm
0x1016fa0a0  push    rbx
0x1016fa0a2  push    rsi
0x1016fa0a3  push    rdi
0x1016fa0a4  push    r12
0x1016fa0a6  push    r13
0x1016fa0a8  push    r14
0x1016fa0aa  push    r15
0x1016fa0ac  mov     eax, 1010h
0x1016fa0b1  call    _alloca_probe
0x1016fa0b6  sub     rsp, rax
0x1016fa0b9  mov     [rsp+1048h+var_D78], 0FFFFFFFFFFFFFFFEh
0x1016fa0c5  mov     rax, cs:__security_cookie
0x1016fa0cc  xor     rax, rsp
0x1016fa0cf  mov     [rsp+1048h+var_48], rax
0x1016fa0d7  mov     r12, r9
0x1016fa0da  mov     [rsp+1048h+var_E38], r9
0x1016fa0e2  mov     r13d, r8d
0x1016fa0e5  mov     [rsp+1048h+var_FD0], rcx
0x1016fa0ea  mov     [rsp+1048h+var_ED0], rcx
0x1016fa0f2  mov     [rsp+1048h+var_F20], r8d
0x1016fa0fa  mov     [rsp+1048h+var_E70], r9
0x1016fa102  mov     rax, [rsp+1048h+arg_20]
0x1016fa10a  mov     [rsp+1048h+var_FC8], rax
0x1016fa112  mov     [rsp+1048h+var_FF0], 0FFFFFFFFh
0x1016fa11a  xor     ebx, ebx
0x1016fa11c  mov     [rsp+1048h+var_FE8], ebx
0x1016fa120  mov     [rsp+1048h+var_FE0], ebx
0x1016fa124  mov     [rsp+1048h+var_F98], 0FFFFFFFFh
0x1016fa12f  mov     [rsp+1048h+var_F90], ebx
0x1016fa136  mov     [rsp+1048h+var_F88], ebx
0x1016fa13d  mov     [rsp+1048h+var_F58], 0FFFFFFFFh
0x1016fa148  mov     [rsp+1048h+var_F50], ebx
0x1016fa14f  mov     [rsp+1048h+var_1000], rbx
0x1016fa154  xor     edx, edx; Val
0x1016fa156  mov     r8d, 188h; Size
0x1016fa15c  lea     rcx, [rsp+1048h+var_3E8]; void *
0x1016fa164  call    memset_0
0x1016fa169  mov     [rsp+1048h+var_270], 0FFFFFFFFh
0x1016fa174  mov     [rsp+1048h+var_F80], rbx
0x1016fa17c  mov     [rsp+1048h+var_1007], bl
0x1016fa180  mov     rdx, gs:58h
0x1016fa189  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1016fa190  mov     ecx, [rax]
0x1016fa192  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1016fa199  mov     eax, [rax]
0x1016fa19b  add     rax, [rdx+rcx*8]
0x1016fa19f  mov     rax, [rax+8]
0x1016fa1a3  mov     rcx, [rax+60h]
0x1016fa1a7  mov     eax, [rcx+488h]
0x1016fa1ad  mov     [rsp+1048h+var_FD4], eax
0x1016fa1b1  mov     rdx, gs:58h
0x1016fa1ba  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1016fa1c1  mov     ecx, [rax]
0x1016fa1c3  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1016fa1ca  mov     eax, [rax]
0x1016fa1cc  add     rax, [rdx+rcx*8]
0x1016fa1d0  mov     rax, [rax+8]
0x1016fa1d4  mov     rcx, [rax+60h]
0x1016fa1d8  mov     eax, [rcx+478h]
0x1016fa1de  shr     eax, 5
0x1016fa1e1  and     eax, 1
0x1016fa1e4  mov     [rsp+1048h+var_FD8], eax
0x1016fa1e8  lea     rcx, [rsp+1048h+var_EF8]
0x1016fa1f0  call    cs:__imp_??0CAutoSetDiagOptions@@QEAA@XZ; CAutoSetDiagOptions::CAutoSetDiagOptions(void)
0x1016fa1f6  nop
0x1016fa1f7  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1016fa1fe  cmp     [rax], ebx
0x1016fa200  jz      short loc_1016FA21A
0x1016fa202  lea     rcx, [rsp+1048h+PerformanceCount]; lpPerformanceCount
0x1016fa20a  call    cs:__imp_QueryPerformanceCounter
0x1016fa210  mov     rsi, qword ptr [rsp+1048h+PerformanceCount]
0x1016fa218  jmp     short loc_1016FA222
0x1016fa21a  mov     rsi, ds:7FFE0008h
0x1016fa222  movzx   eax, byte ptr [r12+2]
0x1016fa228  test    al, 8
0x1016fa22a  jz      short loc_1016FA260
0x1016fa22c  mov     rdx, gs:58h
0x1016fa235  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1016fa23c  mov     ecx, [rax]
0x1016fa23e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1016fa245  mov     eax, [rax]
0x1016fa247  add     rax, [rdx+rcx*8]
0x1016fa24b  mov     rax, [rax+8]
0x1016fa24f  mov     rcx, [rax+60h]
0x1016fa253  mov     [rcx+488h], r13d
0x1016fa25a  movzx   eax, byte ptr [r12+2]
0x1016fa260  test    al, 40h
0x1016fa262  jz      short loc_1016FA292
0x1016fa264  mov     rdx, gs:58h
0x1016fa26d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1016fa274  mov     ecx, [rax]
0x1016fa276  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1016fa27d  mov     eax, [rax]
0x1016fa27f  add     rax, [rdx+rcx*8]
0x1016fa283  mov     rax, [rax+8]
0x1016fa287  mov     rcx, [rax+60h]
0x1016fa28b  or      dword ptr [rcx+478h], 20h
0x1016fa292  mov     edx, 26h ; '&'
0x1016fa297  lea     rcx, [rsp+1048h+var_EF8]
0x1016fa29f  call    cs:__imp_?SetSystemTaskIfNoneSet@CAutoSetDiagOptions@@QEAAXF@Z; CAutoSetDiagOptions::SetSystemTaskIfNoneSet(short)
0x1016fa2a5  test    byte ptr [r12+1], 41h
0x1016fa2ab  mov     eax, 4E20h
0x1016fa2b0  mov     r14d, 0FFFFFFFFh
0x1016fa2b6  cmovz   r14d, eax
0x1016fa2ba  cmp     r13d, 1
0x1016fa2be  jz      loc_1016FA3F4
0x1016fa2c4  call    ?IsReplicatedMasterEnabled@@YAHXZ; IsReplicatedMasterEnabled(void)
0x1016fa2c9  test    eax, eax
0x1016fa2cb  jnz     short loc_1016FA2D6
0x1016fa2cd  call    ?IsContainedAGEnabledInstance@@YAHXZ; IsContainedAGEnabledInstance(void)
0x1016fa2d2  test    eax, eax
0x1016fa2d4  jz      short loc_1016FA2FD
0x1016fa2d6  cmp     r13d, 7FFBh
0x1016fa2dd  jz      loc_1016FA3F4
0x1016fa2e3  call    ?IsContainedAGEnabledInstance@@YAHXZ; IsContainedAGEnabledInstance(void)
0x1016fa2e8  test    eax, eax
0x1016fa2ea  jz      short loc_1016FA2FD
0x1016fa2ec  movzx   ecx, r13w; unsigned __int16
0x1016fa2f0  call    ?IsContainedAgMasterDBId@@YA_NG@Z; IsContainedAgMasterDBId(ushort)
0x1016fa2f5  test    al, al
0x1016fa2f7  jnz     loc_1016FA3F4
0x1016fa2fd  xor     r8d, r8d
0x1016fa300  mov     edx, r13d
0x1016fa303  lea     rcx, [rsp+1048h+var_D48]
0x1016fa30b  call    ?GetAGIDByDBID@HadrMetadataManager@@SA?AV?$HadrSinglePartId@$0A@@@KPEAVBaseXact@@@Z; HadrMetadataManager::GetAGIDByDBID(ulong,BaseXact *)
0x1016fa310  movaps  xmm0, [rsp+1048h+var_D48]
0x1016fa318  movaps  xmmword ptr [rsp+1048h+rguid.Data1], xmm0
0x1016fa320  movq    rax, xmm0
0x1016fa325  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1016fa32c  jnz     short loc_1016FA343
0x1016fa32e  mov     rax, qword ptr [rsp+1048h+rguid.Data4]
0x1016fa336  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1016fa33d  jz      loc_1016FA3F4
0x1016fa343  call    ?IsContainedAGEnabledInstance@@YAHXZ; IsContainedAGEnabledInstance(void)
0x1016fa348  test    eax, eax
0x1016fa34a  jz      short loc_1016FA3A7
0x1016fa34c  mov     [rsp+1048h+var_E48], rbx
0x1016fa354  call    ?IsContainedAGEnabledInstance@@YAHXZ; IsContainedAGEnabledInstance(void)
0x1016fa359  test    eax, eax
0x1016fa35b  jz      short loc_1016FA3A7
0x1016fa35d  call    ?GetInstance@CHadrArManager@@SAPEAV1@XZ; CHadrArManager::GetInstance(void)
0x1016fa362  mov     rcx, rax; this
0x1016fa365  lea     rdx, [rsp+1048h+rguid]; struct _GUID *
0x1016fa36d  call    ?GetContainedAgControllerWithRef@CHadrArManager@@QEAAPEAVCHadrArController@@AEBU_GUID@@@Z; CHadrArManager::GetContainedAgControllerWithRef(_GUID const &)
0x1016fa372  mov     rdi, rax
0x1016fa375  mov     [rsp+1048h+var_E48], rax
0x1016fa37d  test    rax, rax
0x1016fa380  jz      short loc_1016FA3A7
0x1016fa382  mov     edx, 0FFFFFFFFh; unsigned int
0x1016fa387  mov     rcx, rax; this
0x1016fa38a  call    ?WaitForAgMasterReady@CHadrArController@@QEAAHK@Z; CHadrArController::WaitForAgMasterReady(ulong)
0x1016fa38f  nop
0x1016fa390  mov     rcx, [rdi+8]
0x1016fa394  movsxd  rcx, dword ptr [rcx+4]
0x1016fa398  add     rcx, 8
0x1016fa39c  add     rcx, rdi
0x1016fa39f  mov     rax, [rcx]
0x1016fa3a2  call    qword ptr [rax+10h]
0x1016fa3a5  jmp     short $+2
0x1016fa3a7  movaps  xmm0, xmmword ptr [rsp+1048h+rguid.Data1]
0x1016fa3af  movaps  [rsp+1048h+var_448], xmm0
0x1016fa3b7  mov     r8d, 27h ; '''; cchMax
0x1016fa3bd  lea     rdx, [rsp+1048h+sz]; lpsz
0x1016fa3c5  lea     rcx, [rsp+1048h+rguid]; rguid
0x1016fa3cd  call    cs:__imp_StringFromGUID2
0x1016fa3d3  mov     [rsp+1048h+var_3EE], ebx
0x1016fa3da  mov     r8d, 1
0x1016fa3e0  lea     rdx, [rsp+1048h+var_436]
0x1016fa3e8  lea     rcx, aHadrruntimecal; "HadrRuntimeCallbacks::WaitForAgMasterRe"...
0x1016fa3ef  call    ?LogSystemMetadata@@YAXPEB_WZZ; LogSystemMetadata(wchar_t const *,...)
0x1016fa3f4  mov     [rsp+1048h+var_F40], ebx
0x1016fa3fb  mov     rdx, gs:58h
0x1016fa404  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1016fa40b  mov     ecx, [rax]
0x1016fa40d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1016fa414  mov     edi, [rax]
0x1016fa416  add     rdi, [rdx+rcx*8]
0x1016fa41a  mov     r15, [rdi+100h]
0x1016fa421  test    r15, r15
0x1016fa424  jnz     short loc_1016FA435
0x1016fa426  xor     ecx, ecx
0x1016fa428  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1016fa42e  mov     r15, [rdi+100h]
0x1016fa435  mov     [rsp+1048h+var_F38], r15
0x1016fa43d  mov     ecx, [r15+268h]
0x1016fa444  mov     eax, ecx
0x1016fa446  and     eax, 1
0x1016fa449  xor     eax, 1
0x1016fa44c  mov     [rsp+1048h+var_F40], eax
0x1016fa453  or      ecx, 1
0x1016fa456  mov     [r15+268h], ecx
0x1016fa45d  mov     rdi, [rsp+1048h+var_FD0]
0x1016fa462  cmp     qword ptr [r12+48h], 0
0x1016fa468  jnz     loc_1016FA5BB
0x1016fa46e  mov     [rsp+1048h+var_FE8], r13d
0x1016fa473  mov     [rsp+1048h+var_FEC], 5
0x1016fa478  mov     [rsp+1048h+var_FE4], 11h
0x1016fa480  mov     rdx, gs:58h
0x1016fa489  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1016fa490  mov     ecx, [rax]
0x1016fa492  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1016fa499  mov     eax, [rax]
0x1016fa49b  add     rax, [rdx+rcx*8]
0x1016fa49f  mov     rax, [rax+8]
0x1016fa4a3  mov     rcx, [rax+68h]
0x1016fa4a7  mov     rcx, [rcx+28h]
0x1016fa4ab  mov     r10, [rcx]
0x1016fa4ae  mov     byte ptr [rsp+1048h+var_1018], 0
0x1016fa4b3  mov     eax, [rsp+1048h+var_FE0]
0x1016fa4b7  mov     dword ptr [rsp+1048h+var_1020], eax
0x1016fa4bb  mov     dword ptr [rsp+1048h+var_1028], r14d
0x1016fa4c0  mov     r9b, 5
0x1016fa4c3  mov     r8d, 11h
0x1016fa4c9  mov     edx, r13d
0x1016fa4cc  call    qword ptr [r10+0A0h]
0x1016fa4d3  mov     edx, eax
0x1016fa4d5  mov     [rsp+1048h+var_FF0], eax
0x1016fa4d9  mov     [rsp+1048h+var_FA0], eax
0x1016fa4e0  test    eax, eax
0x1016fa4e2  jns     loc_1016FA5BD
0x1016fa4e8  cmp     byte ptr [r12], 0
0x1016fa4ed  jge     loc_1016FA5A4
0x1016fa4f3  lea     ecx, [rax+3]
0x1016fa4f6  cmp     ecx, 1
0x1016fa4f9  ja      loc_1016FA5BD
0x1016fa4ff  mov     ecx, 7FFFFFFFh
0x1016fa504  call    cs:__imp_?ResetAbort@SOS_Task@@SAXW4TASK_ABORT_TYPE@1@@Z; SOS_Task::ResetAbort(SOS_Task::TASK_ABORT_TYPE)
0x1016fa50a  call    cs:__imp_?ResetDeadlock@SOS_Task@@SAXXZ; SOS_Task::ResetDeadlock(void)
0x1016fa510  nop
0x1016fa511  mov     eax, [rsp+1048h+var_F40]
0x1016fa518  not     eax
0x1016fa51a  and     [r15+268h], eax
0x1016fa521  lea     rcx, [rsp+1048h+var_EF8]
0x1016fa529  call    cs:__imp_??1CAutoSetDiagOptions@@QEAA@XZ; CAutoSetDiagOptions::~CAutoSetDiagOptions(void)
0x1016fa52f  nop
0x1016fa530  mov     rdx, gs:58h
0x1016fa539  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1016fa540  mov     ecx, [rax]
0x1016fa542  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1016fa549  mov     eax, [rax]
0x1016fa54b  add     rax, [rdx+rcx*8]
0x1016fa54f  mov     rax, [rax+8]
0x1016fa553  mov     rcx, [rax+60h]
0x1016fa557  cmp     [rsp+1048h+var_FD8], 0
0x1016fa55c  jz      short loc_1016FA567
0x1016fa55e  or      dword ptr [rcx+478h], 20h
0x1016fa565  jmp     short loc_1016FA56E
0x1016fa567  and     dword ptr [rcx+478h], 0FFFFFFDFh
0x1016fa56e  mov     rdx, gs:58h
0x1016fa577  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1016fa57e  mov     ecx, [rax]
0x1016fa580  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1016fa587  mov     eax, [rax]
0x1016fa589  add     rax, [rdx+rcx*8]
0x1016fa58d  mov     rax, [rax+8]
0x1016fa591  mov     rcx, [rax+60h]
0x1016fa595  mov     eax, [rsp+1048h+var_FD4]
0x1016fa599  mov     [rcx+488h], eax
0x1016fa59f  jmp     loc_1016FC77A
0x1016fa5a4  lfence
0x1016fa5a7  mov     dl, 1Ch
0x1016fa5a9  mov     ecx, [rsp+1048h+var_FF0]
0x1016fa5ad  call    ?lck_StandardHandler@@YAXW4LCK_RESULT@@W4ABORT_AND_LCK_EXCEPTIONS@@@Z; lck_StandardHandler(LCK_RESULT,ABORT_AND_LCK_EXCEPTIONS)
0x1016fa5b2  mov     edx, [rsp+1048h+var_FA0]
0x1016fa5b9  jmp     short loc_1016FA5BD
0x1016fa5bb  mov     edx, ebx
0x1016fa5bd  mov     eax, r13d
0x1016fa5c0  sub     eax, 7FFCh
0x1016fa5c5  jz      short loc_1016FA60B
0x1016fa5c7  sub     eax, 1
0x1016fa5ca  jz      short loc_1016FA605
0x1016fa5cc  cmp     eax, 2
0x1016fa5cf  jz      short loc_1016FA5FF
0x1016fa5d1  mov     r8, [rsp+1048h+var_FD0]
0x1016fa5d6  cmp     r13d, [r8+4Ch]
0x1016fa5da  ja      loc_1016FA6B7
0x1016fa5e0  test    r13d, r13d
0x1016fa5e3  jz      loc_1016FA6B7
0x1016fa5e9  lea     eax, [r13-1]
0x1016fa5ed  movsxd  rcx, eax
0x1016fa5f0  mov     rax, [r8+28h]
0x1016fa5f4  mov     r8, [rax+rcx*8]
0x1016fa5f8  mov     rdi, [rsp+1048h+var_FD0]
0x1016fa5fd  jmp     short loc_1016FA60F
0x1016fa5ff  mov     r8, [rdi+58h]
0x1016fa603  jmp     short loc_1016FA60F
0x1016fa605  mov     r8, [rdi+70h]
0x1016fa609  jmp     short loc_1016FA60F
0x1016fa60b  mov     r8, [rdi+68h]
0x1016fa60f  test    r8, r8
0x1016fa612  jz      loc_1016FA6BA
0x1016fa618  cmp     qword ptr [r12+30h], 0
0x1016fa61e  jnz     loc_1016FA6BA
0x1016fa624  mov     eax, [rsp+1048h+var_F40]
0x1016fa62b  not     eax
0x1016fa62d  and     [r15+268h], eax
0x1016fa634  lea     rcx, [rsp+1048h+var_EF8]
0x1016fa63c  call    cs:__imp_??1CAutoSetDiagOptions@@QEAA@XZ; CAutoSetDiagOptions::~CAutoSetDiagOptions(void)
0x1016fa642  nop
0x1016fa643  mov     rdx, gs:58h
  ... truncated ...
```
