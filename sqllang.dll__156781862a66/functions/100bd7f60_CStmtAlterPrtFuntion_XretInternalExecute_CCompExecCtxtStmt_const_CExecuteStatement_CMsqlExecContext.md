# CStmtAlterPrtFuntion::XretInternalExecute(CCompExecCtxtStmt const &,CExecuteStatement *,CMsqlExecContext *)

- ea: `0x100bd7f60`
- end: `0x100bd9bfa`
- name: `?XretInternalExecute@CStmtAlterPrtFuntion@@QEBA?AW4EXRetType@@AEBVCCompExecCtxtStmt@@PEAVCExecuteStatement@@PEAVCMsqlExecContext@@@Z`
- size: `7322`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x100bd9c00`
- `0x100c2a870`

## callees

- `0x100401070`
- `0x100407430`
- `0x10040b790`
- `0x100414dc0`
- `0x100421810`
- `0x100421920`
- `0x1004260a0`
- `0x100426290`
- `0x100444380`
- `0x100444d90`
- `0x1004450b0`
- `0x10044b4c0`
- `0x100454360`
- `0x100537840`
- `0x100682450`
- `0x1006fa910`
- `0x10075c350`
- `0x100760df0`
- `0x10079cc60`
- `0x100b4d510`
- `0x100b96e00`
- `0x100bace30`
- `0x100bacee0`
- `0x100bd4b40`
- `0x100bd6080`
- `0x100bd6690`
- `0x100bd7f60`
- `0x100c31c10`
- `0x1011d53b0`
- `0x101d46310`

## import_xrefs

- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100bd9b1b`
- `sqldk!?m_ProfilerTraceEnabled@CommonGlobalState@@2_NA` at `0x100bd9a61`
- `sqldk!?GetDeadlockPriority@SOS_Task@@QEBA?AW4TASK_DEADLOCK_PRIORITY@1@XZ` at `0x100bd8398`
- `sqldk!?GetDeadlockPriority@SOS_Task@@QEBA?AW4TASK_DEADLOCK_PRIORITY@1@XZ` at `0x100bd8398`
- `sqldk!?SetDeadlockPriority@SOS_Task@@QEAAXW4TASK_DEADLOCK_PRIORITY@1@@Z` at `0x100bd83ad`
- `sqldk!?SetDeadlockPriority@SOS_Task@@QEAAXW4TASK_DEADLOCK_PRIORITY@1@@Z` at `0x100bd9bc2`
- `sqldk!?SetDeadlockPriority@SOS_Task@@QEAAXW4TASK_DEADLOCK_PRIORITY@1@@Z` at `0x100bd83ad`
- `sqldk!?SetDeadlockPriority@SOS_Task@@QEAAXW4TASK_DEADLOCK_PRIORITY@1@@Z` at `0x100bd9bc2`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100bd9044`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100bd90c6`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100bd96f9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100bd9044`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100bd90c6`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100bd96f9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd7ff1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd80c2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd81b4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd8439`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd8464`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd849b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd8533`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd85e9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd8712`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd87ce`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd88a5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd8a63`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd8abf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd9523`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd957a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd7ff1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd80c2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd81b4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd8439`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd8464`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd849b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd8533`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd85e9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd8712`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd87ce`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd88a5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd8a63`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd8abf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd9523`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100bd957a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100bd93bc`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100bd93bc`
- `sqldk!SystemThread_TlsIndex` at `0x100bd8000`
- `sqldk!SystemThread_TlsIndex` at `0x100bd80fe`
- `sqldk!SystemThread_TlsIndex` at `0x100bd82ac`
- `sqldk!SystemThread_TlsIndex` at `0x100bd830b`
- `sqldk!SystemThread_TlsIndex` at `0x100bd835d`
- `sqldk!SystemThread_TlsIndex` at `0x100bd8e0d`
- `sqldk!SystemThread_TlsIndex` at `0x100bd935c`
- `sqldk!SystemThread_TlsIndex` at `0x100bd9619`
- `sqldk!SystemThread_TlsIndex` at `0x100bd9660`
- `sqldk!SystemThread_TlsIndex` at `0x100bd9a8b`
- `sqldk!SystemThread_TlsIndex` at `0x100bd9b89`
- `sqldk!SystemThread_TlsOffset` at `0x100bd8009`
- `sqldk!SystemThread_TlsOffset` at `0x100bd8107`
- `sqldk!SystemThread_TlsOffset` at `0x100bd82b5`
- `sqldk!SystemThread_TlsOffset` at `0x100bd8314`
- `sqldk!SystemThread_TlsOffset` at `0x100bd8366`
- `sqldk!SystemThread_TlsOffset` at `0x100bd8e16`
- `sqldk!SystemThread_TlsOffset` at `0x100bd9365`
- `sqldk!SystemThread_TlsOffset` at `0x100bd9622`
- `sqldk!SystemThread_TlsOffset` at `0x100bd9669`
- `sqldk!SystemThread_TlsOffset` at `0x100bd9a94`
- `sqldk!SystemThread_TlsOffset` at `0x100bd9b92`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100bd8122`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100bd8381`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100bd8e31`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100bd9380`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100bd9bab`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100bd8122`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100bd8381`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100bd8e31`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100bd9380`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100bd9bab`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100bd82db`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100bd833a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100bd82db`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100bd833a`
- `sqldk!??_V@YAXPEAX@Z` at `0x100bd910e`
- `sqldk!??_V@YAXPEAX@Z` at `0x100bd91f8`
- `sqldk!??_V@YAXPEAX@Z` at `0x100bd9817`
- `sqldk!??_V@YAXPEAX@Z` at `0x100bd910e`
- `sqldk!??_V@YAXPEAX@Z` at `0x100bd91f8`
- `sqldk!??_V@YAXPEAX@Z` at `0x100bd9817`
- `sqlTsEs!?CmpCompare@CXVariant@@QEBAKPEBVCTypeInfo@@0AEBV1@@Z` at `0x100bd8a2f`
- `sqlTsEs!?CmpCompare@CXVariant@@QEBAKPEBVCTypeInfo@@0AEBV1@@Z` at `0x100bd8a2f`
- `sqlmin!??0AutoLockedHoBtAccess@@QEAA@XZ` at `0x100bd984c`
- `sqlmin!??0AutoLockedHoBtAccess@@QEAA@XZ` at `0x100bd98c7`
- `sqlmin!??0AutoLockedHoBtAccess@@QEAA@XZ` at `0x100bd984c`
- `sqlmin!??0AutoLockedHoBtAccess@@QEAA@XZ` at `0x100bd98c7`
- `sqlmin!??1AutoLockedHoBtAccess@@QEAA@XZ` at `0x100bd9942`
- `sqlmin!??1AutoLockedHoBtAccess@@QEAA@XZ` at `0x100bd9950`
- `sqlmin!??1AutoLockedHoBtAccess@@QEAA@XZ` at `0x100bd9942`
- `sqlmin!??1AutoLockedHoBtAccess@@QEAA@XZ` at `0x100bd9950`
- `sqlmin!?Init@AutoLockedHoBtAccess@@QEAAHPEAVXDES@@_KW4LCK_MODE@@W4ACCESSTYPE@@HHPEAW4LCK_RESULT@@K@Z` at `0x100bd989d`
- `sqlmin!?Init@AutoLockedHoBtAccess@@QEAAHPEAVXDES@@_KW4LCK_MODE@@W4ACCESSTYPE@@HHPEAW4LCK_RESULT@@K@Z` at `0x100bd9917`
- `sqlmin!?Init@AutoLockedHoBtAccess@@QEAAHPEAVXDES@@_KW4LCK_MODE@@W4ACCESSTYPE@@HHPEAW4LCK_RESULT@@K@Z` at `0x100bd989d`
- `sqlmin!?Init@AutoLockedHoBtAccess@@QEAAHPEAVXDES@@_KW4LCK_MODE@@W4ACCESSTYPE@@HHPEAW4LCK_RESULT@@K@Z` at `0x100bd9917`
- `sqlmin!?CheckPartitionEmpty@DDLAgent@@SA_NPEAVXDES@@PEAVIMEDIndex@@K_NJ@Z` at `0x100bd924b`
- `sqlmin!?CheckPartitionEmpty@DDLAgent@@SA_NPEAVXDES@@PEAVIMEDIndex@@K_NJ@Z` at `0x100bd9269`
- `sqlmin!?CheckPartitionEmpty@DDLAgent@@SA_NPEAVXDES@@PEAVIMEDIndex@@K_NJ@Z` at `0x100bd924b`
- `sqlmin!?CheckPartitionEmpty@DDLAgent@@SA_NPEAVXDES@@PEAVIMEDIndex@@K_NJ@Z` at `0x100bd9269`
- `sqlmin!?GetRowsetAndColumnModCounts@DDLAgent@@SAXPEAVIMEDIndex@@KAEAURowsetCountsForQp@@KPEBKPEA_J@Z` at `0x100bd92ed`
- `sqlmin!?GetRowsetAndColumnModCounts@DDLAgent@@SAXPEAVIMEDIndex@@KAEAURowsetCountsForQp@@KPEBKPEA_J@Z` at `0x100bd930e`
- `sqlmin!?GetRowsetAndColumnModCounts@DDLAgent@@SAXPEAVIMEDIndex@@KAEAURowsetCountsForQp@@KPEBKPEA_J@Z` at `0x100bd92ed`
- `sqlmin!?GetRowsetAndColumnModCounts@DDLAgent@@SAXPEAVIMEDIndex@@KAEAURowsetCountsForQp@@KPEBKPEA_J@Z` at `0x100bd930e`
- `sqlmin!?GetModCounterBeforeDrop@AutoLockedHoBtAccess@@QEAA_JXZ` at `0x100bd98aa`
- `sqlmin!?GetModCounterBeforeDrop@AutoLockedHoBtAccess@@QEAA_JXZ` at `0x100bd98aa`
- `sqlmin!?Release@AutoLockedHoBtAccess@@QEAAXXZ` at `0x100bd98ba`
- `sqlmin!?Release@AutoLockedHoBtAccess@@QEAAXXZ` at `0x100bd9934`
- `sqlmin!?Release@AutoLockedHoBtAccess@@QEAAXXZ` at `0x100bd98ba`
- `sqlmin!?Release@AutoLockedHoBtAccess@@QEAAXXZ` at `0x100bd9934`
- `sqlmin!?BumpAllColumnMods@AutoLockedHoBtAccess@@QEAAX_J@Z` at `0x100bd9927`
- `sqlmin!?BumpAllColumnMods@AutoLockedHoBtAccess@@QEAAX_J@Z` at `0x100bd9927`
- `sqlmin!?IsSnapshotXact@BaseXact@@QEAAHXZ` at `0x100bd7fd7`
- `sqlmin!?IsSnapshotXact@BaseXact@@QEAAHXZ` at `0x100bd7fd7`
- `sqlmin!GetXdbServerGlobals` at `0x100bd887b`
- `sqlmin!GetXdbServerGlobals` at `0x100bd9148`
- `sqlmin!GetXdbServerGlobals` at `0x100bd9157`
- `sqlmin!GetXdbServerGlobals` at `0x100bd9166`
- `sqlmin!GetXdbServerGlobals` at `0x100bd94bc`
- `sqlmin!GetXdbServerGlobals` at `0x100bd94eb`
- `sqlmin!GetXdbServerGlobals` at `0x100bd9533`
- `sqlmin!GetXdbServerGlobals` at `0x100bd887b`
- `sqlmin!GetXdbServerGlobals` at `0x100bd9148`
- `sqlmin!GetXdbServerGlobals` at `0x100bd9157`
- `sqlmin!GetXdbServerGlobals` at `0x100bd9166`
- `sqlmin!GetXdbServerGlobals` at `0x100bd94bc`
- `sqlmin!GetXdbServerGlobals` at `0x100bd94eb`
- `sqlmin!GetXdbServerGlobals` at `0x100bd9533`

## string_xrefs

- `0x100bd90b6`: `Sql\Ntdbms\msql\ddl\XmlCompressionOption.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CStmtAlterPrtFuntion::XretInternalExecute(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v7; // r12
  __int64 v8; // rbx
  BaseXact *v9; // rax
  __int64 v10; // r14
  int v11; // edx
  __int64 v12; // r9
  __int64 v13; // r8
  struct IMEDPrtFunction *v14; // r13
  __int64 v15; // rbx
  __int64 v16; // rdx
  struct IMemObj *v17; // rsi
  __int64 v18; // rdi
  __int64 v19; // rbx
  __int64 v20; // rax
  unsigned int v21; // edi
  int v22; // eax
  bool v23; // bl
  DataVirtualizationResource *v24; // rax
  __int64 v25; // rdx
  struct CSessionTraceFlags *v26; // rcx
  __int64 v27; // rdx
  struct CSessionTraceFlags *v28; // rcx
  char v29; // al
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rbx
  unsigned int DeadlockPriority; // edi
  unsigned int v34; // eax
  __int64 v35; // r8
  __int64 v36; // rdi
  _QWORD *v37; // rbx
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 i; // r15
  __int64 v41; // rax
  unsigned int v42; // eax
  _QWORD *v43; // rbx
  __int64 v44; // r8
  unsigned int v45; // r13d
  __int64 v46; // rax
  struct IMEDRelation *v47; // r14
  __int64 v48; // rdi
  _QWORD *v49; // r12
  __int64 v50; // rax
  __int64 v51; // rsi
  _QWORD *v52; // rbx
  struct BaseXact *v53; // rax
  int v54; // ebx
  unsigned int v55; // eax
  __int64 v56; // rax
  int v57; // r9d
  __int64 v58; // r11
  __int64 v59; // rcx
  bool v60; // al
  int v61; // ecx
  struct IMemObj *v62; // r15
  CXVariant *v63; // rsi
  unsigned int v64; // edi
  __int64 v65; // r8
  unsigned int v66; // ebx
  unsigned int v67; // r14d
  const struct CXVariant *v68; // rax
  bool v69; // zf
  unsigned int v70; // edi
  unsigned int v71; // r13d
  __int64 v72; // rbx
  __int64 v73; // r8
  __int64 v74; // rbx
  unsigned int v75; // eax
  __int64 v76; // r9
  __int64 v77; // r8
  __int64 v78; // rax
  __int64 v79; // r8
  struct IMEDPrtFunction *v80; // r14
  __int64 v81; // rdx
  __int64 v82; // r8
  __int64 v83; // rsi
  __int64 v84; // r8
  __int64 v85; // rdi
  __int64 v86; // r8
  __int64 v87; // rax
  __int64 v88; // r8
  __int64 v89; // rbx
  unsigned int v90; // eax
  __int64 v91; // rbx
  unsigned int v92; // eax
  __int64 v93; // r14
  __int64 v94; // rsi
  __int64 v95; // r8
  __int64 v96; // rax
  __int64 v97; // r8
  __int64 v98; // rbx
  __int64 v99; // r8
  __int64 v100; // rdi
  __int64 v101; // rbx
  unsigned int v102; // eax
  __int64 v103; // rbx
  unsigned int v104; // eax
  unsigned int v105; // esi
  __int64 v106; // rax
  struct IMEDRelation *v107; // r12
  __int64 v108; // rax
  __int64 v109; // rbx
  __int64 v110; // rax
  struct IMEDIndex *j; // rdx
  struct IMEDIndex *v112; // rdi
  __int64 v113; // rbx
  unsigned int v114; // eax
  __int64 v115; // rax
  __int64 v116; // rbx
  __int64 v117; // rax
  __int64 v118; // rdx
  __int64 v119; // rax
  unsigned int v120; // ebx
  unsigned int v121; // r12d
  unsigned int k; // ebx
  __int64 v123; // rcx
  unsigned int v124; // eax
  unsigned int v125; // ecx
  __int64 v126; // rdx
  __int64 v127; // r14
  unsigned int v128; // esi
  __int64 v129; // r15
  struct IMEDIndex *v130; // rbx
  int v131; // edi
  char v132; // di
  __int64 v133; // rdx
  __int64 v134; // rcx
  bool v135; // di
  struct IMEDIndex *v136; // rdx
  unsigned int v137; // ebx
  struct IMEDIndex *v138; // rsi
  int v139; // edi
  bool v140; // r15
  bool v141; // al
  bool v142; // r12
  unsigned int v143; // edi
  char v144; // bl
  __int64 v145; // rcx
  unsigned __int64 v146; // r12
  __int64 v147; // rbx
  __int64 v148; // r10
  unsigned __int64 v149; // rax
  __int64 v150; // rcx
  void *v151; // rdi
  unsigned int v152; // ebx
  unsigned int v153; // eax
  __int64 v154; // rax
  int v155; // eax
  char v156; // r15
  __int64 v157; // rdx
  unsigned int v158; // ebx
  unsigned int v159; // eax
  __int64 v160; // rdi
  int v161; // edx
  BOOL v162; // ecx
  __int64 v163; // rax
  int v164; // ecx
  __int64 v165; // rbx
  bool v166; // r15
  CSQLStrings *v167; // rax
  __int64 v168; // r8
  CSQLStrings *v169; // rax
  __int64 v170; // rcx
  __int64 v171; // rcx
  unsigned int v172; // ecx
  unsigned int v173; // ecx
  unsigned int v174; // r15d
  __int64 v175; // r9
  __int64 ModCounterBeforeDrop; // rbx
  __int64 v177; // r9
  unsigned int v178; // ebx
  __int64 v179; // rsi
  struct IMEDIndex *v180; // rdx
  __int64 v181; // rax
  _DWORD *v182; // rax
  int v183; // eax
  __int64 v184; // rbx
  __int64 v185; // rax
  __int64 v186; // rbx
  __int64 v187; // rcx
  struct CXVariant *v189; // [rsp+20h] [rbp-E0h]
  struct CXVariant *v190; // [rsp+20h] [rbp-E0h]
  struct CXVariant *v191; // [rsp+20h] [rbp-E0h]
  wchar_t *v192; // [rsp+28h] [rbp-D8h]
  wchar_t *v193; // [rsp+28h] [rbp-D8h]
  wchar_t *v194; // [rsp+28h] [rbp-D8h]
  wchar_t *Src; // [rsp+30h] [rbp-D0h]
  __int64 v196; // [rsp+38h] [rbp-C8h]
  bool v197[8]; // [rsp+38h] [rbp-C8h]
  bool *v198; // [rsp+40h] [rbp-C0h]
  bool v199; // [rsp+60h] [rbp-A0h]
  unsigned int v200; // [rsp+64h] [rbp-9Ch]
  unsigned int v201; // [rsp+68h] [rbp-98h]
  unsigned int v202; // [rsp+6Ch] [rbp-94h]
  struct IMEDPrtFunction *v204; // [rsp+78h] [rbp-88h]
  __int64 v205; // [rsp+80h] [rbp-80h]
  _BYTE v206[4]; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v207; // [rsp+90h] [rbp-70h]
  unsigned int v208; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v209; // [rsp+98h] [rbp-68h]
  int v210; // [rsp+9Ch] [rbp-64h]
  struct IMemObj *v211; // [rsp+A0h] [rbp-60h]
  __int64 v212; // [rsp+A8h] [rbp-58h]
  unsigned int v213; // [rsp+B0h] [rbp-50h]
  unsigned int v214; // [rsp+B4h] [rbp-4Ch]
  __int64 v215; // [rsp+B8h] [rbp-48h]
  struct CCompExecCtxtStmt *v216; // [rsp+C0h] [rbp-40h]
  int v217; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v218; // [rsp+CCh] [rbp-34h]
  struct IMEDRelation *v219; // [rsp+D0h] [rbp-30h]
  __int64 v220; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v221; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v222; // [rsp+ECh] [rbp-14h]
  int v223; // [rsp+F0h] [rbp-10h]
  __int64 v224; // [rsp+F8h] [rbp-8h]
  _BYTE v225[16]; // [rsp+100h] [rbp+0h] BYREF
  __int16 v226; // [rsp+110h] [rbp+10h]
  unsigned __int8 v227; // [rsp+112h] [rbp+12h]
  unsigned __int8 v228; // [rsp+113h] [rbp+13h]
  int v229; // [rsp+114h] [rbp+14h]
  void **v230; // [rsp+120h] [rbp+20h] BYREF
  __int128 v231; // [rsp+128h] [rbp+28h]
  char v232; // [rsp+138h] [rbp+38h]
  __int64 v233; // [rsp+140h] [rbp+40h]
  int v234; // [rsp+148h] [rbp+48h] BYREF
  char v235; // [rsp+14Ch] [rbp+4Ch]
  _QWORD *v236; // [rsp+150h] [rbp+50h]
  __int64 v237; // [rsp+158h] [rbp+58h]
  char v238; // [rsp+160h] [rbp+60h] BYREF
  _DWORD *v239; // [rsp+168h] [rbp+68h]
  int v240; // [rsp+170h] [rbp+70h]
  __int64 v241; // [rsp+178h] [rbp+78h]
  int v242; // [rsp+180h] [rbp+80h] BYREF
  _DWORD *v243; // [rsp+188h] [rbp+88h]
  int v244; // [rsp+190h] [rbp+90h]
  __int64 v245; // [rsp+198h] [rbp+98h]
  void *v246; // [rsp+1A0h] [rbp+A0h]
  __int64 v247; // [rsp+1A8h] [rbp+A8h]
  bool v248; // [rsp+1B0h] [rbp+B0h]
  int v249; // [rsp+1B8h] [rbp+B8h]
  struct CEsComp *v250; // [rsp+1C0h] [rbp+C0h] BYREF
  int v251; // [rsp+1C8h] [rbp+C8h] BYREF
  int v252; // [rsp+1D0h] [rbp+D0h] BYREF
  void *v253; // [rsp+1D8h] [rbp+D8h]
  int v254; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v255; // [rsp+1E8h] [rbp+E8h]
  int v256; // [rsp+1F8h] [rbp+F8h]
  __int64 v257; // [rsp+200h] [rbp+100h] BYREF
  int v258; // [rsp+208h] [rbp+108h]
  __int64 v259; // [rsp+20Ch] [rbp+10Ch]
  int v260; // [rsp+214h] [rbp+114h]
  int v261; // [rsp+218h] [rbp+118h]
  __int64 v262; // [rsp+21Ch] [rbp+11Ch]
  __int64 v263; // [rsp+228h] [rbp+128h] BYREF
  int v264; // [rsp+230h] [rbp+130h]
  __int64 v265; // [rsp+234h] [rbp+134h]
  int v266; // [rsp+23Ch] [rbp+13Ch]
  int v267; // [rsp+240h] [rbp+140h]
  __int64 v268; // [rsp+244h] [rbp+144h]
  __int64 v269; // [rsp+250h] [rbp+150h] BYREF
  int v270; // [rsp+258h] [rbp+158h]
  __int64 v271; // [rsp+25Ch] [rbp+15Ch]
  int v272; // [rsp+264h] [rbp+164h]
  int v273; // [rsp+268h] [rbp+168h]
  __int64 v274; // [rsp+26Ch] [rbp+16Ch]
  __int64 v275; // [rsp+278h] [rbp+178h] BYREF
  int v276; // [rsp+280h] [rbp+180h]
  _QWORD v277[5]; // [rsp+290h] [rbp+190h] BYREF
  int v278; // [rsp+2B8h] [rbp+1B8h]
  void *v279; // [rsp+2C0h] [rbp+1C0h]
  int v280; // [rsp+2C8h] [rbp+1C8h]
  unsigned int *v281; // [rsp+2D0h] [rbp+1D0h]
  unsigned int v282; // [rsp+2D8h] [rbp+1D8h]
  BOOL v283; // [rsp+2DCh] [rbp+1DCh]
  CSQLStrings *v284; // [rsp+2E0h] [rbp+1E0h]
  __int64 v285; // [rsp+2E8h] [rbp+1E8h]
  __int64 v286; // [rsp+2F0h] [rbp+1F0h]
  bool v287; // [rsp+2F8h] [rbp+1F8h]
  struct IMemObj *v288; // [rsp+300h] [rbp+200h]
  __int128 v289; // [rsp+310h] [rbp+210h] BYREF
  __int128 v290; // [rsp+320h] [rbp+220h]
  __int128 v291; // [rsp+330h] [rbp+230h]
  __int128 v292; // [rsp+340h] [rbp+240h]
  __int128 v293; // [rsp+350h] [rbp+250h]
  __int128 v294; // [rsp+360h] [rbp+260h] BYREF
  __int128 v295; // [rsp+370h] [rbp+270h]
  __int128 v296; // [rsp+380h] [rbp+280h]
  __int128 v297; // [rsp+390h] [rbp+290h]
  __int128 v298; // [rsp+3A0h] [rbp+2A0h]
  _BYTE v299[112]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _BYTE v300[112]; // [rsp+420h] [rbp+320h] BYREF
  _BYTE v301[160]; // [rsp+490h] [rbp+390h] BYREF
  __int64 v302; // [rsp+530h] [rbp+430h]
  __int64 v303; // [rsp+538h] [rbp+438h]
  char v304; // [rsp+540h] [rbp+440h]
  __int64 v305; // [rsp+560h] [rbp+460h]
  _BYTE v306[56]; // [rsp+5A0h] [rbp+4A0h] BYREF
  struct XDES *v307; // [rsp+5D8h] [rbp+4D8h]
  __int128 v308; // [rsp+670h] [rbp+570h]
  char v309; // [rsp+680h] [rbp+580h]
  _BYTE v310[848]; // [rsp+8F0h] [rbp+7F0h] BYREF
  int v311; // [rsp+C40h] [rbp+B40h] BYREF
  unsigned int v312; // [rsp+C44h] [rbp+B44h]
  char v313; // [rsp+C48h] [rbp+B48h]
  unsigned __int8 v314[2]; // [rsp+C50h] [rbp+B50h] BYREF
  unsigned __int8 v315; // [rsp+C54h] [rbp+B54h]
  unsigned __int8 v316; // [rsp+C55h] [rbp+B55h]
  int v317; // [rsp+C58h] [rbp+B58h]
  _QWORD v318[2]; // [rsp+C60h] [rbp+B60h] BYREF
  int v319; // [rsp+C70h] [rbp+B70h]
  __int64 v320; // [rsp+C78h] [rbp+B78h]
  __int64 v321; // [rsp+C80h] [rbp+B80h]
  __int64 v322; // [rsp+C88h] [rbp+B88h]
  int v323; // [rsp+C90h] [rbp+B90h]
  __int64 v324; // [rsp+C98h] [rbp+B98h]
  char v325[8]; // [rsp+CA0h] [rbp+BA0h] BYREF
  int v326; // [rsp+CA8h] [rbp+BA8h]

  v285 = -2;
  v212 = a3;
  v216 = (struct CCompExecCtxtStmt *)a2;
  v7 = a1;
  v8 = *(_QWORD *)(a2 + 144);
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v8 + 496LL))(v8) )
  {
    v9 = (BaseXact *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 432LL))(v8);
    if ( BaseXact::IsSnapshotXact(v9) )
      ex_raise(39, 64, 16, 1);
  }
  v214 = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                       + SystemThread_TlsIndex)
                                                     + SystemThread_TlsOffset)
                                         + 80LL)
                             + 8LL);
  v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(**(_QWORD **)(a3 + 56) + 56LL))(
          *(_QWORD *)(a3 + 56),
          v214,
          0,
          0,
          0,
          0);
  v205 = v10;
  v11 = *(_DWORD *)(v7 + 2216);
  v275 = *(_QWORD *)(v7 + 2208);
  v276 = v11;
  LOBYTE(v12) = 1;
  LOBYTE(v13) = 5;
  v14 = (struct IMEDPrtFunction *)(*(__int64 (__fastcall **)(__int64, __int64 *, __int64, __int64))(*(_QWORD *)v10
                                                                                                  + 640LL))(
                                    v10,
                                    &v275,
                                    v13,
                                    v12);
  v204 = v14;
  if ( !v14 )
  {
    LODWORD(v192) = 13143;
    LODWORD(v189) = 13088;
    ex_raise(151, 51, 16, 1, v189, v192, *(_DWORD *)(v7 + 2216), *(_QWORD *)(v7 + 2208));
  }
  v202 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *))(*(_QWORD *)v14 + 8LL))(v14);
  (*(void (__fastcall **)(struct IMEDPrtFunction *, int *))(*(_QWORD *)v14 + 24LL))(v14, &v311);
  if ( (v313 & 2) != 0 )
    goto LABEL_10;
  v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v16 = *(_QWORD *)(v15 + 256);
  if ( !v16 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v16 = *(_QWORD *)(v15 + 256);
  }
  if ( !(unsigned __int8)ISECManager::CheckPermRule(
                           1279346256,
                           *(_QWORD *)(v16 + 1000),
                           *(_QWORD *)(a3 + 56),
                           v214,
                           v214,
                           v202,
                           -1,
                           0,
                           1,
                           0,
                           0,
                           0) )
  {
LABEL_10:
    LODWORD(Src) = *(_DWORD *)(v7 + 2216);
    LODWORD(v192) = 13143;
    LODWORD(v189) = 13088;
    ex_raise(151, 51, 16, 1, v189, v192, Src, *(_QWORD *)(v7 + 2208));
  }
  v17 = *(struct IMemObj **)(a4 + 120);
  v211 = v17;
  v288 = v17;
  CExecutionCollection::CExecutionCollection((CExecutionCollection *)v301);
  v18 = *(_QWORD *)(v212 + 128);
  v19 = *(_QWORD *)(v212 + 56);
  CExecutionCollection::AllocateMembers((CExecutionCollection *)v301, *(struct CEnvCollection **)(v7 + 112), v17);
  v303 = v19;
  if ( v19 )
    v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  else
    v20 = 0;
  v302 = v20;
  if ( v18 )
  {
    v305 = v18;
    *(_QWORD *)(v18 + 432) = v301;
  }
  v304 |= 8u;
  v21 = CEnvCollection::XretSchemaChanged(*(_QWORD *)(v7 + 112), a2, v301, -1);
  if ( v21 )
    goto LABEL_277;
  if ( *(_BYTE *)a2 )
  {
    v22 = *(_DWORD *)(a2 + 104);
  }
  else
  {
    CExecLvlIntCtxt::GetCurCompatLevel(*(_QWORD *)(a2 + 128), &v217, a2);
    v22 = v217;
  }
  v23 = v22 >= 140;
  if ( v22 >= 140 || byte_102EDCA9A )
  {
LABEL_26:
    v24 = qword_102ECFB10;
    goto LABEL_27;
  }
  v24 = qword_102ECFB10;
  if ( (*((_BYTE *)qword_102ECFB10 + 154) & 0x20) == 0 )
  {
    v25 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    if ( !*(_QWORD *)v25 )
      goto LABEL_33;
    v26 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v25 + 56LL);
    if ( !v26 || !CSessionTraceFlags::CheckSessionTraceInternal(v26, 0x4D5u) )
      goto LABEL_33;
    goto LABEL_26;
  }
LABEL_27:
  if ( !v23
    || !byte_102EDCA99
    && (*((_BYTE *)v24 + 154) & 0x40) == 0
    && ((v27 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
         !*(_QWORD *)v27)
     || (v28 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v27 + 56LL)) == 0
     || !CSessionTraceFlags::CheckSessionTraceInternal(v28, 0x4D6u)) )
  {
    v29 = 0;
    goto LABEL_35;
  }
LABEL_33:
  v29 = 1;
LABEL_35:
  v215 = 0;
  if ( v29 )
  {
    v30 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v31 = *(_QWORD *)(v30 + 256);
    if ( !v31 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v31 = *(_QWORD *)(v30 + 256);
    }
    v32 = *(_QWORD *)(v31 + 600);
    DeadlockPriority = SOS_Task::GetDeadlockPriority(v32);
    if ( DeadlockPriority != 10 )
    {
      SOS_Task::SetDeadlockPriority(v32, 10);
      v215 = DeadlockPriority | 0x100000000LL;
    }
  }
  v318[0] = &CPreAlterPrtFunc::`vftable';
  v318[1] = 0;
  v320 = 0;
  v321 = 0;
  v319 = 0;
  v322 = 0;
  v323 = 0;
  v324 = 0;
  CPreAlterPrtFunc::Init((CPreAlterPrtFunc *)v318, v14, v17);
  if ( !*(_QWORD *)(v7 + 2248) )
    ex_raise(77, 14, 16, 1);
  if ( *(_BYTE *)(v7 + 2220) || v312 == 1 && (ex_raise(77, 16, 16, 2), *(_BYTE *)(v7 + 2220)) )
  {
    if ( v312 == 15000 )
    {
      LODWORD(v189) = 15000;
      ex_raise(77, 19, 16, 1, v189);
    }
  }
  v34 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *))(*(_QWORD *)v14 + 80LL))(v14);
  if ( v34 )
  {
    LOBYTE(v192) = 1;
    LOBYTE(v189) = 0;
    LOBYTE(v35) = 1;
    v36 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD))(*(_QWORD *)v10 + 120LL))(
            v10,
            v34,
            v35,
            0,
            (_DWORD)v189,
            (_DWORD)v192,
            0,
            0);
    v37 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 40LL))(v36);
    *(_DWORD *)v197 = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 40LL))(v36) + 8);
    LODWORD(v193) = *(_DWORD *)(v7 + 2216);
    ex_raise(37, 29, 16, 3, L"ALTER PARTITION FUNCTION", v193, *(_QWORD *)(v7 + 2208), *(_QWORD *)v197, *v37);
  }
  v257 = 0;
  v259 = 0;
  v260 = 0;
  v262 = 1;
  v261 = -1;
  v258 = -2;
  LOBYTE(v35) = 5;
  for ( i = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *, _QWORD, __int64))(*(_QWORD *)v14 + 72LL))(v14, 0, v35);
        i;
        i = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *, __int64, __int64))(*(_QWORD *)v204 + 72LL))(
              v204,
              i,
              v44) )
  {
    v41 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)i + 40LL))(i);
    if ( *(_BYTE *)(v7 + 2220) )
    {
      v42 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      if ( v312 >= v42 )
      {
        v43 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)i + 16LL))(i);
        LODWORD(v189) = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)i + 16LL))(i) + 8);
        ex_raise(77, 10, 16, 1, v189, *v43);
      }
    }
    v45 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)i + 56LL))(i, 0);
    if ( v45 )
    {
      do
      {
        LODWORD(Src) = 0;
        LOBYTE(v192) = 1;
        LOBYTE(v189) = 0;
        LOBYTE(v44) = 2;
        v46 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, struct CXVariant *, _DWORD, wchar_t *, _DWORD))(*(_QWORD *)v10 + 120LL))(
                v10,
                v45,
                v44,
                0,
                v189,
                (_DWORD)v192,
                Src,
                0);
        v47 = (struct IMEDRelation *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 120LL))(v46);
        v48 = (**(__int64 (__fastcall ***)(struct IMEDRelation *))v47)(v47);
        v49 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v48 + 40LL))(v48);
        (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v48 + 96LL))(v48, v325);
        if ( v326 == 8277 )
        {
          v50 = (*(__int64 (__fastcall **)(struct IMEDRelation *, __int64))(*(_QWORD *)v47 + 232LL))(v47, 1);
          v51 = v50;
          if ( v50 )
          {
            (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v50 + 40LL))(v50, &v257);
            if ( (v257 & 0x1000) != 0 )
            {
              v52 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 24LL))(v51);
              LODWORD(v198) = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 24LL))(v51) + 8);
              LODWORD(Src) = *(_DWORD *)(a1 + 2216);
              LODWORD(v189) = *((_DWORD *)v49 + 2);
              ex_raise(77, 25, 16, 1, v189, *v49, Src, *(_QWORD *)(a1 + 2208), v198, *v52);
            }
          }
          CIndexDDL::CIndexDDL((CIndexDDL *)v310, *(struct IMetadataAccess **)(v212 + 56), v47, v211, 0, 0, 0, 0, 0);
          v53 = (struct BaseXact *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v212 + 56) + 16LL))(*(_QWORD *)(v212 + 56));
          CIndexDDL::InvalidateTxtPtrs((CIndexDDL *)v310, v53);
          CIndexDDL::~CIndexDDL((CIndexDDL *)v310);
        }
        v54 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
        v55 = (**(__int64 (__fastcall ***)(__int64))v48)(v48);
        if ( CExecLvlIntCtxt::FTableIsTriggerTarget(*((CExecLvlIntCtxt **)v216 + 16), v55, v54) )
        {
          LODWORD(v192) = *((_DWORD *)v49 + 2);
          ex_raise(17, 13, 16, 10, L"ALTER PARTITION FUNCTION", v192, *v49);
        }
        v45 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)i + 56LL))(i, v45);
        v10 = v205;
      }
      while ( v45 );
      v7 = a1;
    }
    v14 = v204;
    LOBYTE(v44) = 5;
  }
  v254 = 3;
  v255 = 0;
  v256 = 0;
  v250 = *(struct CEsComp **)(v7 + 2248);
  if ( v250 )
    CExprProcessor::Eval(v216, *(struct CExecContext **)(v212 + 128), 1u, &v250, (struct CXVariant *const)&v254);
  if ( *(_BYTE *)(GetXdbServerGlobals(v39, v38) + 12004) && (_BYTE)v254 == 3 )
    ex_raise(224, 44, 16, 2);
  v56 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *, __int64))(*(_QWORD *)v14 + 48LL))(v14, 1);
  (*(void (__fastcall **)(__int64, unsigned __int8 *))(*(_QWORD *)v56 + 8LL))(v56, v314);
  CTypeInfo::Init((CTypeInfo *)v225, v314[0]);
  v59 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + v225[0]);
  if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsNumeric + v59) )
  {
    v227 = v315;
    v228 = v316;
    v226 = (unsigned __int8)byte_102445B17[v315];
  }
  else if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsVarTime + v59) )
  {
    CTypeInfo::SetPrecScaleLenForVarTime((__int64)v225, v316);
  }
  else if ( !*((_BYTE *)&CTypeInfo::sxm_rgfIsConstantMaxLength + v59) )
  {
    if ( !v57
      && *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWStringOrBinary + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v58)) == 1 )
    {
      LOWORD(v57) = (*((_BYTE *)&CTypeInfo::sxm_rgfIsWString + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v58)) != 0) + 1;
    }
    v226 = v57;
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + v59) || ((v225[0] - 35) & 0xBF) == 0 )
    {
      v60 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)v225);
      v61 = v229;
      if ( v60 )
        v61 = v317;
      v229 = v61;
    }
  }
  v62 = v211;
  v63 = CheckPrtRangeTypConversion(
          (struct CXVariant *)&v254,
          *(struct CTypeInfo **)(v7 + 2240),
          (struct CTypeInfo *)v225,
          v211,
          1u);
  v64 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *))(*(_QWORD *)v14 + 56LL))(v14);
  v66 = 5;
  v67 = 1;
  v207 = 1;
  if ( v64 )
  {
    _mm_lfence();
    do
    {
      v68 = (const struct CXVariant *)(*(__int64 (__fastcall **)(struct IMEDPrtFunction *, _QWORD, struct IMemObj *))(*(_QWORD *)v14 + 64LL))(
                                        v14,
                                        v67,
                                        v211);
      v66 = CXVariant::CmpCompare(v63, (const struct CTypeInfo *)v225, (const struct CTypeInfo *)v225, v68);
      if ( !*(_BYTE *)(v7 + 2220)
        || (v66 == 2 || v66 == 88) && (LODWORD(v190) = v67, ex_raise(77, 21, 16, 1, v190), !*(_BYTE *)(v7 + 2220)) )
      {
        if ( v66 == 2 )
          break;
        v69 = v66 == 88;
      }
      else
      {
        if ( v66 == 1 )
          break;
        v69 = v66 == 40;
      }
      if ( v69 )
        break;
      ++v67;
    }
    while ( v67 <= v64 );
    v207 = v67;
  }
  if ( !*(_BYTE *)(v7 + 2220) && v66 != 2 && v66 != 88 )
    ex_raise(77, 15, 16, 1);
  v208 = 0;
  v70 = v67 + 1;
  v71 = v67 + 1;
  if ( (v313 & 1) != 0 )
    v70 = v67;
  else
    v71 = v67;
  v200 = v70;
  LOBYTE(v65) = 2;
  v72 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *, _QWORD, __int64))(*(_QWORD *)v204 + 72LL))(v204, 0, v65);
  if ( v72 )
  {
    do
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 40LL))(v72);
      LOBYTE(v73) = 2;
      v72 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *, __int64, __int64))(*(_QWORD *)v204 + 72LL))(
              v204,
              v72,
              v73);
    }
    while ( v72 );
    v62 = v211;
  }
  v74 = *(_QWORD *)v205;
  v75 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *))(*(_QWORD *)v204 + 8LL))(v204);
  LOBYTE(v76) = 1;
  LOBYTE(v77) = 2;
  (*(void (__fastcall **)(__int64, _QWORD, __int64, __int64))(v74 + 648))(v205, v75, v77, v76);
  v78 = *(_QWORD *)v204;
  if ( *(_BYTE *)(v7 + 2220) )
  {
    v79 = v67;
    v80 = v204;
    (*(void (__fastcall **)(struct IMEDPrtFunction *, CXVariant *, __int64))(v78 + 112))(v204, v63, v79);
  }
  else
  {
    v81 = v67;
    v80 = v204;
    (*(void (__fastcall **)(struct IMEDPrtFunction *, __int64))(v78 + 120))(v204, v81);
  }
  (*(void (__fastcall **)(struct IMEDPrtFunction *))(*(_QWORD *)v80 + 96LL))(v80);
  LOBYTE(v82) = 2;
  v83 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *, _QWORD, __int64))(*(_QWORD *)v80 + 72LL))(v80, 0, v82);
  if ( v83 )
  {
    do
    {
      v85 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v83 + 40LL))(v83);
      LOBYTE(v86) = 1;
      v87 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v85 + 24LL))(v85, 1, v86);
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v87 + 24LL))(v87, &v251);
      if ( v251 == 3 )
      {
        if ( *(_BYTE *)(v7 + 2220) )
        {
          v89 = *(_QWORD *)v85;
          v90 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(v89 + 56))(v85, v90, v71);
        }
        else
        {
          if ( !v311 )
          {
            v91 = *(_QWORD *)v85;
            v92 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(v91 + 56))(v85, v71, v92);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 48LL))(v85);
        }
      }
      LOBYTE(v88) = 2;
      v83 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *, __int64, __int64))(*(_QWORD *)v80 + 72LL))(
              v80,
              v83,
              v88);
    }
    while ( v83 );
    v70 = v200;
  }
  LOBYTE(v84) = 2;
  v93 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *, __int64, __int64))(*(_QWORD *)v80 + 72LL))(v80, v83, v84);
  v233 = v93;
  if ( v93 )
  {
    while ( 1 )
    {
      v94 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v93 + 40LL))(v93);
      LOBYTE(v95) = 1;
      v96 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v94 + 24LL))(v94, 1, v95);
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v96 + 24LL))(v96, &v252);
      if ( v252 != 3 )
      {
        v199 = 0;
        if ( !*(_BYTE *)(v7 + 2220) && !v311 )
        {
          LOBYTE(v97) = 1;
          v98 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v94 + 24LL))(v94, v71, v97);
          LOBYTE(v99) = 1;
          v100 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v94 + 24LL))(v94, v70, v99);
          LODWORD(v98) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v98 + 8LL))(v98);
          if ( (_DWORD)v98 == (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v100 + 8LL))(v100) )
            v199 = 1;
        }
        if ( *(_BYTE *)(v7 + 2220) )
        {
          v101 = *(_QWORD *)v94;
          v102 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(v101 + 56))(v94, v102, v71);
        }
        else
        {
          if ( !v311 )
          {
            v103 = *(_QWORD *)v94;
            v104 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(v103 + 56))(v94, v71, v104);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 48LL))(v94);
        }
        v105 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v93 + 56LL))(v93, 0);
        v210 = v105;
        if ( v105 )
          break;
      }
LABEL_265:
      LOBYTE(v97) = 2;
      v93 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *, __int64, __int64))(*(_QWORD *)v204 + 72LL))(
              v204,
              v93,
              v97);
      v233 = v93;
      v70 = v200;
      if ( !v93 )
        goto LABEL_266;
    }
LABEL_130:
    LOBYTE(v192) = 1;
    LOBYTE(v190) = 0;
    LOBYTE(v97) = 2;
    v106 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _DWORD, wchar_t *, _DWORD, _DWORD))(*(_QWORD *)v205 + 120LL))(
             v205,
             v105,
             v97,
             0,
             (_DWORD)v190,
             v192,
             0,
             0);
    v107 = (struct IMEDRelation *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v106 + 120LL))(v106);
    v219 = v107;
    v108 = (**(__int64 (__fastcall ***)(struct IMEDRelation *))v107)(v107);
    v236 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v108 + 40LL))(v108);
    CIndexDDL::CIndexDDL((CIndexDDL *)v306, *(struct IMetadataAccess **)(v212 + 56), v107, v62, 0, 0, 0, 0, 0);
    v109 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v110 = *(_QWORD *)(v109 + 256);
    if ( !v110 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v110 = *(_QWORD *)(v109 + 256);
    }
    v221 = *(_QWORD *)(v110 + 1000);
    v222 = 0;
    v223 = 4;
    v224 = 0;
    for ( j = 0; ; j = v112 )
    {
      v112 = (struct IMEDIndex *)(*(__int64 (__fastcall **)(struct IMEDRelation *, struct IMEDIndex *, _QWORD))(*(_QWORD *)v107 + 360LL))(
                                   v107,
                                   j,
                                   0);
      if ( !v112 )
      {
        v124 = v222;
        v121 = 0;
        goto LABEL_149;
      }
      v113 = *(_QWORD *)v205;
      v114 = (*(__int64 (__fastcall **)(struct IMEDIndex *))(*(_QWORD *)v112 + 224LL))(v112);
      v115 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(v113 + 680))(v205, v114, 1);
      v116 = v115;
      if ( v115 )
      {
        v117 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v115 + 40LL))(v115);
        if ( v117 )
        {
          LOBYTE(v118) = 1;
          v119 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v117 + 8LL))(v117, v118);
          if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v119 + 8LL))(v119) == v202 )
          {
            v120 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v116 + 8LL))(v116);
            if ( v120 < (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v93 + 8LL))(v93) )
            {
              v121 = 0;
              for ( k = 0; k < v222; ++k )
              {
                v123 = *(_QWORD *)(v224 + 8LL * k);
                if ( v123 )
                {
                  v69 = (*(_DWORD *)(v123 + 8))-- == 1;
                  if ( v69 )
                    (**(void (__fastcall ***)(__int64, __int64))v123)(v123, 1);
                }
              }
              v124 = 0;
              v222 = 0;
LABEL_149:
              v218 = v124;
              if ( !v124 )
                goto LABEL_263;
              v125 = 0;
              v213 = 0;
              v126 = 0;
              v237 = 0;
              while ( 2 )
              {
                if ( v125 >= v124 )
                {
                  v127 = 0;
                }
                else
                {
                  v127 = *(_QWORD *)(v224 + 8 * v126);
                  if ( v127 )
                    v121 = *(_DWORD *)(v127 + 28);
                }
                v201 = v121;
                if ( *(_BYTE *)(a1 + 2220) )
                {
                  v128 = 0;
                  if ( v121 )
                  {
                    v129 = 0;
                    do
                    {
                      if ( v128 >= *(_DWORD *)(v127 + 28) )
                        v130 = 0;
                      else
                        v130 = *(struct IMEDIndex **)(v129 + *(_QWORD *)(v127 + 40));
                      (*(void (__fastcall **)(struct IMEDIndex *, _QWORD, int *))(*(_QWORD *)v130 + 248LL))(
                        v130,
                        v207,
                        &v234);
                      v131 = v234;
                      v244 = 1;
                      v243 = operator new(0x10u, v211, "Sql\\Ntdbms\\msql\\ddl\\tabcreat.cpp", 1288, 3u);
                      *v243 = v131;
                      v243[2] = v71;
                      v243[3] = v71;
                      v243[1] = 13088;
                      v242 = 0;
                      v245 = 0;
                      *(_QWORD *)&v308 = &v242;
                      v309 |= 2u;
                      v132 = v235;
                      if ( v235 )
                      {
                        v240 = 1;
                        v239 = operator new(0x10u, v211, "Sql\\Ntdbms\\msql\\ddl\\XmlCompressionOption.cpp", 534, 3u);
                        *(_BYTE *)v239 = v132;
                        v239[2] = v71;
                        v239[3] = v71;
                        v239[1] = 13088;
                        v238 = 0;
                        v241 = 0;
                        *((_QWORD *)&v308 + 1) = &v238;
                        v309 |= 4u;
                        operator delete[](v239);
                      }
                      v135 = (*(unsigned int (__fastcall **)(struct IMEDIndex *))(*(_QWORD *)v130 + 8LL))(v130) == 1
                          && (SMD::FHasNciOnCci(v219)
                           || ((*(_BYTE *)(qword_102ECFB00 + 48500) & 1) != 0
                            || !*(_DWORD *)(qword_102ECFB00 + 14504)
                            && *(_BYTE *)(GetXdbServerGlobals(v134, v133) + 12004)
                            || *(_BYTE *)(GetXdbServerGlobals(v134, v133) + 12004))
                           && (*(_BYTE *)(GetXdbServerGlobals(v134, v133) + 12004)
                            || *((_BYTE *)qword_102EF3550 + 717)
                            || (*((_BYTE *)qword_102ECFB10 + 1431) & 0x40) != 0))
                          || SMD::FHasOriginalLocator(v130, v207);
                      if ( v128 >= *(_DWORD *)(v127 + 28) )
                        v136 = 0;
                      else
                        v136 = *(struct IMEDIndex **)(v129 + *(_QWORD *)(v127 + 40));
                      CIndexDDL::CreateRowsets((CIndexDDL *)v306, v136, v71);
                      if ( v135 )
                        CIndexDDL::CheckAndAddOriginalLocatorColumn((CIndexDDL *)v306, v130, v71);
                      v308 = 0;
                      operator delete[](v243);
                      ++v128;
                      v129 += 8;
                    }
                    while ( v128 < v121 );
                  }
                }
                v208 = v71;
                v137 = v200;
                v209 = v200;
                if ( *(_DWORD *)(v127 + 28) )
                  v138 = **(struct IMEDIndex ***)(v127 + 40);
                else
                  v138 = 0;
                v139 = v210;
                v140 = DDLAgent::CheckPartitionEmpty(v307, v138, v71, 1, v210);
                v141 = DDLAgent::CheckPartitionEmpty(v307, v138, v200, 1, v139);
                v142 = v141;
                if ( v140 && (v143 = v71, v141) )
                {
LABEL_240:
                  v145 = a1;
                }
                else
                {
                  v144 = 0;
                  v294 = 0;
                  v295 = 0;
                  v296 = 0;
                  v297 = 0;
                  v298 = 0;
                  v289 = 0;
                  v290 = 0;
                  v291 = 0;
                  v292 = 0;
                  v293 = 0;
                  DDLAgent::GetRowsetAndColumnModCounts(v138, v71, (struct RowsetCountsForQp *)&v294, 0, 0, 0);
                  DDLAgent::GetRowsetAndColumnModCounts(v138, v200, (struct RowsetCountsForQp *)&v289, 0, 0, 0);
                  v145 = a1;
                  if ( !*(_BYTE *)(a1 + 2220) )
                  {
                    if ( v199 )
                    {
                      if ( v140 || v142 )
                        v144 = 1;
                    }
                    else
                    {
                      v144 = v140;
                    }
                  }
                  if ( !v144 )
                  {
                    v146 = (*(unsigned int (__fastcall **)(struct IMEDIndex *))(*(_QWORD *)v138 + 136LL))(v138);
                    v147 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset;
                    v148 = *(_QWORD *)(v147 + 256);
                    if ( !v148 )
                    {
                      SystemThread::MakeMiniSOSThread(0);
                      v148 = *(_QWORD *)(v147 + 256);
                    }
                    v149 = 4 * v146;
                    if ( !is_mul_ok(v146, 4u) )
                      v149 = -1;
                    v151 = operator new[](
                             v149,
                             *(struct IMemObj **)(v148 + 1000),
                             "Sql\\Ntdbms\\msql\\ddl\\prtddl.cpp",
                             2071,
                             3u);
                    v253 = v151;
                    v246 = v151;
                    v152 = 1;
                    if ( (_DWORD)v146 )
                    {
                      _mm_lfence();
                      do
                      {
                        v153 = (*(__int64 (__fastcall **)(struct IMEDIndex *, _QWORD))(*(_QWORD *)v138 + 144LL))(
                                 v138,
                                 v152);
                        v154 = (*(__int64 (__fastcall **)(struct IMEDIndex *, _QWORD))(*(_QWORD *)v138 + 64LL))(
                                 v138,
                                 v153);
                        v155 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v154 + 16LL))(v154);
                        v150 = v152 - 1;
                        *((_DWORD *)v151 + v150) = v155;
                        ++v152;
                      }
                      while ( v152 <= (unsigned int)v146 );
                    }
                    v156 = 0;
                    v157 = 0;
                    v158 = 0;
                    v159 = v201;
                    if ( v201 )
                    {
                      v160 = 0;
                      do
                      {
                        if ( v158 >= *(_DWORD *)(v127 + 28) )
                        {
                          v150 = 0;
                        }
                        else
                        {
                          v150 = *(_QWORD *)(v160 + *(_QWORD *)(v127 + 40));
                          v159 = v201;
                        }
                        if ( v150 )
                        {
                          v269 = 0;
                          v271 = 0;
                          v272 = 0;
                          v274 = 1;
                          v273 = -1;
                          v270 = -2;
                          (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v150 + 40LL))(v150, &v269);
                          if ( (v269 & 0x200000) != 0 )
                          {
                            v156 = 1;
                            break;
                          }
                          v159 = v201;
                          v157 = 0;
                        }
                        ++v158;
                        v160 += 8;
                      }
                      while ( v158 < v159 );
                    }
                    if ( v199 )
                    {
                      if ( *((__int64 *)&v295 + 1) <= *((__int64 *)&v290 + 1)
                        || *(_BYTE *)(GetXdbServerGlobals(v150, v157) + 12004) )
                      {
                        v209 = v200;
                        v143 = v71;
                      }
                      else
                      {
                        v209 = v71;
                        v143 = v200;
                      }
                      v208 = v143;
                      if ( v156 && !*(_BYTE *)(GetXdbServerGlobals(v150, v157) + 12004) )
                      {
                        LODWORD(v191) = *((_DWORD *)v236 + 2);
                        ex_raise(353, 44, 15, 1, v191, *v236);
                      }
                    }
                    else
                    {
                      v143 = v71;
                      if ( v156 && !*(_BYTE *)(GetXdbServerGlobals(v150, v157) + 12004) )
                      {
                        v161 = 46;
                        if ( !*(_BYTE *)(a1 + 2220) )
                          v161 = 45;
                        LODWORD(v191) = *((_DWORD *)v236 + 2);
                        ex_raise(353, v161, 15, 1, v191, *v236);
                        v143 = v71;
                      }
                    }
                    v162 = *(_BYTE *)(a1 + 2220) == 0;
                    v163 = *(_QWORD *)(v212 + 56);
                    v277[0] = &CRelOpSrcRepartition::`vftable';
                    v277[1] = v163;
                    v277[2] = v219;
                    v277[3] = v318;
                    v277[4] = v204;
                    v278 = v146;
                    v279 = v253;
                    v280 = 1;
                    v281 = &v208;
                    v282 = v209;
                    v283 = v162;
                    v247 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                   + SystemThread_TlsIndex)
                                                 + SystemThread_TlsOffset)
                                     + 128LL);
                    v164 = *(_DWORD *)(v247 + 76);
                    v248 = (v164 & 0x2000) != 0;
                    *(_DWORD *)(v247 + 76) = v164 | 0x2000;
                    v165 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                   + SystemThread_TlsIndex)
                                                 + SystemThread_TlsOffset)
                                     + 128LL);
                    v286 = v165;
                    LODWORD(v163) = *(_DWORD *)(v165 + 76);
                    v166 = (v163 & 0x100000) != 0;
                    v287 = v166;
                    *(_DWORD *)(v165 + 76) = v163 | 0x100000;
                    v230 = &CExecDMLInternal::`vftable';
                    v231 = 0;
                    v232 = 1;
                    *(_QWORD *)&v231 = v277;
                    v249 = 8175;
                    v167 = (CSQLStrings *)operator new(0x570u, v211, "Sql\\Ntdbms\\msql\\ddl\\cnstcrt.cpp", 8175, 3u);
                    v284 = v167;
                    if ( v167 )
                      v169 = CSQLStrings::CSQLStrings(v167, 0, 0, 0, (struct ICallerParse *)&v230, 0, 0, 0, 0, 0, 1, 0);
                    else
                      v169 = 0;
                    *((_QWORD *)&v231 + 1) = v169;
                    *((_DWORD *)v169 + 144) |= 0x400u;
                    v170 = *(_QWORD *)(*((_QWORD *)&v231 + 1) + 72LL);
                    if ( !v170 )
                    {
                      v171 = *(_QWORD *)(*((_QWORD *)&v231 + 1) + 416LL);
                      if ( v171 )
                        v170 = *(_QWORD *)(v171 + 88);
                      else
                        v170 = 0;
                    }
                    LOBYTE(v168) = 2;
                    CCache::EventPlanNotCached(v170, 36, v168);
                    if ( (*(unsigned int (__fastcall **)(struct IMEDRelation *))(*(_QWORD *)v219 + 696LL))(v219) )
                      *(_DWORD *)(*((_QWORD *)&v231 + 1) + 580LL) |= 8u;
                    CExecDMLInternal::Execute((CExecDMLInternal *)&v230, v216);
                    v230 = &CExecDMLInternal::`vftable';
                    if ( *((_QWORD *)&v231 + 1) )
                      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)&v231 + 1) + 136LL))(
                        *((_QWORD *)&v231 + 1),
                        1);
                    v172 = *(_DWORD *)(v165 + 76) & 0xFFEFFFFF;
                    if ( v166 )
                      v172 = *(_DWORD *)(v165 + 76) | 0x100000;
                    *(_DWORD *)(v165 + 76) = v172;
                    v173 = *(_DWORD *)(v247 + 76) & 0xFFFFDFFF;
                    if ( v248 )
                      v173 = *(_DWORD *)(v247 + 76) | 0x2000;
                    *(_DWORD *)(v247 + 76) = v173;
                    operator delete[](v246);
                    v137 = v200;
                    goto LABEL_240;
                  }
                  v143 = v71;
                  v137 = v200;
                  if ( v199 && *((_QWORD *)&v295 + 1) != *((_QWORD *)&v290 + 1) && v142 )
                    v143 = v200;
                }
                if ( *(_BYTE *)(v145 + 2220) )
                {
                  v121 = 0;
                }
                else
                {
                  v174 = v137;
                  if ( v143 == v137 )
                    v174 = v71;
                  if ( v174 == v143 )
                  {
                    v121 = 0;
                  }
                  else
                  {
                    AutoLockedHoBtAccess::AutoLockedHoBtAccess((AutoLockedHoBtAccess *)v300);
                    (*(void (__fastcall **)(struct IMEDIndex *, _QWORD, __int64 *, _BYTE *))(*(_QWORD *)v138 + 272LL))(
                      v138,
                      v143,
                      &v220,
                      v206);
                    v121 = 0;
                    LODWORD(v192) = 0;
                    LOBYTE(v175) = 1;
                    AutoLockedHoBtAccess::Init(v300, v307, v220, v175, 0, v192, 1, 0, 0);
                    ModCounterBeforeDrop = AutoLockedHoBtAccess::GetModCounterBeforeDrop((AutoLockedHoBtAccess *)v300);
                    AutoLockedHoBtAccess::Release((AutoLockedHoBtAccess *)v300);
                    AutoLockedHoBtAccess::AutoLockedHoBtAccess((AutoLockedHoBtAccess *)v299);
                    (*(void (__fastcall **)(struct IMEDIndex *, _QWORD, __int64 *, _BYTE *))(*(_QWORD *)v138 + 272LL))(
                      v138,
                      v174,
                      &v220,
                      v206);
                    LODWORD(v194) = 0;
                    LOBYTE(v177) = 1;
                    AutoLockedHoBtAccess::Init(v299, v307, v220, v177, 0, v194, 1, 0, 0);
                    AutoLockedHoBtAccess::BumpAllColumnMods((AutoLockedHoBtAccess *)v299, ModCounterBeforeDrop);
                    AutoLockedHoBtAccess::Release((AutoLockedHoBtAccess *)v299);
                    AutoLockedHoBtAccess::~AutoLockedHoBtAccess((AutoLockedHoBtAccess *)v299);
                    AutoLockedHoBtAccess::~AutoLockedHoBtAccess((AutoLockedHoBtAccess *)v300);
                  }
                  v178 = 0;
                  if ( v201 )
                  {
                    v179 = 0;
                    do
                    {
                      if ( v178 >= *(_DWORD *)(v127 + 28) )
                        v180 = 0;
                      else
                        v180 = *(struct IMEDIndex **)(v179 + *(_QWORD *)(v127 + 40));
                      CIndexDDL::DropRowset((CIndexDDL *)v306, v180, v143, 0);
                      ++v178;
                      v179 += 8;
                    }
                    while ( v178 < v201 );
                  }
                }
                v125 = v213 + 1;
                v213 = v125;
                v126 = ++v237;
                if ( v125 < v218 )
                {
                  v124 = v222;
                  continue;
                }
                break;
              }
              v62 = v211;
              v93 = v233;
              v105 = v210;
LABEL_263:
              CTDynArray<CScalarStatsInfo *,CFnI_Default<CScalarStatsInfo *>,CFnD_Refc<CScalarStatsInfo>,CMemObjAlloc<0>>::~CTDynArray<CScalarStatsInfo *,CFnI_Default<CScalarStatsInfo *>,CFnD_Refc<CScalarStatsInfo>,CMemObjAlloc<0>>(&v221);
              CIndexDDL::~CIndexDDL((CIndexDDL *)v306);
              v105 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v93 + 56LL))(v93, v105);
              v210 = v105;
              if ( !v105 )
              {
                v7 = a1;
                goto LABEL_265;
              }
              goto LABEL_130;
            }
            v263 = 0;
            v265 = 0;
            v266 = 0;
            v268 = 1;
            v267 = -1;
            v264 = -2;
            (*(void (__fastcall **)(struct IMEDIndex *, __int64 *))(*(_QWORD *)v112 + 40LL))(v112, &v263);
            if ( (v263 & 0x2000) == 0 && (v263 & 0x1000) == 0 )
              AddIndexToMatrix((struct DRgPDRgPimidx *)&v221, v112);
          }
        }
      }
    }
  }
LABEL_266:
  if ( ((unsigned __int8)qword_102EDC9FC & 0x10) != 0
    || CommonGlobalState::m_ProfilerTraceEnabled
    && (*(_BYTE *)(qword_102ECFB00 + 80) & 0x10) != 0
    && (v181 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL)) != 0
    && (v182 = *(_DWORD **)(v181 + 48)) != 0
    && !*v182 )
  {
    v183 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v205 + 16LL))(v205);
    LODWORD(v196) = 0;
    CTraceDDL::TraceDDL(
      164,
      v216,
      v183,
      v202,
      18000,
      *(_DWORD *)(v7 + 2216),
      *(const wchar_t **)(v7 + 2208),
      v196,
      0,
      0);
  }
  v184 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v212 + 56) + 16LL))(*(_QWORD *)(v212 + 56));
  v185 = g_dbtableFactory[4](v214);
  (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v184 + 272LL))(
    v184,
    *(unsigned __int16 *)(v185 + 40),
    *(_QWORD *)(v185 + 4624));
  (*(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64, int, int))(*(_QWORD *)qword_102F1B290 + 64LL))(
    qword_102F1B290,
    v214,
    v202,
    2,
    66316,
    1);
  v21 = 0;
  CPreAlterPrtFunc::~CPreAlterPrtFunc((CPreAlterPrtFunc *)v318);
  if ( HIDWORD(v215) )
  {
    v186 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v187 = *(_QWORD *)(v186 + 256);
    if ( !v187 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v187 = *(_QWORD *)(v186 + 256);
    }
    SOS_Task::SetDeadlockPriority(*(_QWORD *)(v187 + 600), (unsigned int)v215);
  }
LABEL_277:
  CExecutionCollection::~CExecutionCollection((CExecutionCollection *)v301);
  return v21;
}

```

## disassembly

```asm
0x100bd7f60  push    rbp
0x100bd7f62  push    rbx
0x100bd7f63  push    rsi
0x100bd7f64  push    rdi
0x100bd7f65  push    r12
0x100bd7f67  push    r13
0x100bd7f69  push    r14
0x100bd7f6b  push    r15
0x100bd7f6d  lea     rbp, [rsp-0BC8h]
0x100bd7f75  sub     rsp, 0CC8h
0x100bd7f7c  mov     [rbp+0C00h+var_A18], 0FFFFFFFFFFFFFFFEh
0x100bd7f87  mov     rax, cs:__security_cookie
0x100bd7f8e  xor     rax, rsp
0x100bd7f91  mov     [rbp+0C00h+var_50], rax
0x100bd7f98  mov     rdi, r9
0x100bd7f9b  mov     rsi, r8
0x100bd7f9e  mov     [rbp+0C00h+var_C58], r8
0x100bd7fa2  mov     r15, rdx
0x100bd7fa5  mov     [rbp+0C00h+var_C40], rdx
0x100bd7fa9  mov     r12, rcx
0x100bd7fac  mov     [rsp+0D00h+var_C90], rcx
0x100bd7fb1  mov     rbx, [rdx+90h]
0x100bd7fb8  mov     rax, [rbx]
0x100bd7fbb  mov     rcx, rbx
0x100bd7fbe  call    qword ptr [rax+1F0h]
0x100bd7fc4  test    al, al
0x100bd7fc6  jz      short loc_100BD7FF7
0x100bd7fc8  mov     rax, [rbx]
0x100bd7fcb  mov     rcx, rbx
0x100bd7fce  call    qword ptr [rax+1B0h]
0x100bd7fd4  mov     rcx, rax
0x100bd7fd7  call    cs:__imp_?IsSnapshotXact@BaseXact@@QEAAHXZ; BaseXact::IsSnapshotXact(void)
0x100bd7fdd  test    eax, eax
0x100bd7fdf  jz      short loc_100BD7FF7
0x100bd7fe1  mov     edx, 40h ; '@'
0x100bd7fe6  lea     ecx, [rdx-19h]
0x100bd7fe9  lea     r9d, [rdx-3Fh]
0x100bd7fed  lea     r8d, [rdx-30h]
0x100bd7ff1  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100bd7ff7  mov     rdx, gs:58h
0x100bd8000  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100bd8007  mov     ecx, [rax]
0x100bd8009  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100bd8010  mov     eax, [rax]
0x100bd8012  add     rax, [rdx+rcx*8]
0x100bd8016  mov     rax, [rax]
0x100bd8019  mov     rcx, [rax+50h]
0x100bd801d  movzx   ebx, word ptr [rcx+8]
0x100bd8021  mov     [rbp+0C00h+var_C4C], ebx
0x100bd8024  mov     rcx, [rsi+38h]
0x100bd8028  mov     rax, [rcx]
0x100bd802b  xor     edx, edx
0x100bd802d  mov     dword ptr [rsp+0D00h+var_CD8], edx
0x100bd8031  mov     dword ptr [rsp+0D00h+var_CE0], edx
0x100bd8035  xor     r9d, r9d
0x100bd8038  xor     r8d, r8d
0x100bd803b  mov     edx, ebx
0x100bd803d  call    qword ptr [rax+38h]
0x100bd8040  mov     r14, rax
0x100bd8043  mov     [rbp+0C00h+var_C80], rax
0x100bd8047  mov     edx, [r12+8A8h]
0x100bd804f  mov     rcx, [r12+8A0h]
0x100bd8057  mov     [rbp+0C00h+var_A88], rcx
0x100bd805e  mov     [rbp+0C00h+var_A80], edx
0x100bd8064  mov     r10, [rax]
0x100bd8067  mov     r9b, 1
0x100bd806a  mov     r8b, 5
0x100bd806d  lea     rdx, [rbp+0C00h+var_A88]
0x100bd8074  mov     rcx, rax
0x100bd8077  call    qword ptr [r10+280h]
0x100bd807e  mov     r13, rax
0x100bd8081  mov     [rsp+0D00h+var_C88], rax
0x100bd8086  test    rax, rax
0x100bd8089  jnz     short loc_100BD80C8
0x100bd808b  mov     rcx, [r12+8A0h]
0x100bd8093  mov     qword ptr [rsp+0D00h+var_CC8], rcx
0x100bd8098  mov     ecx, [r12+8A8h]
0x100bd80a0  mov     dword ptr [rsp+0D00h+Src], ecx
0x100bd80a4  mov     dword ptr [rsp+0D00h+var_CD8], 3357h
0x100bd80ac  mov     dword ptr [rsp+0D00h+var_CE0], 3320h
0x100bd80b4  lea     edx, [rax+33h]
0x100bd80b7  lea     ecx, [rdx+64h]
0x100bd80ba  lea     r9d, [rax+1]
0x100bd80be  lea     r8d, [rax+10h]
0x100bd80c2  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100bd80c8  mov     rax, [r13+0]
0x100bd80cc  mov     rcx, r13
0x100bd80cf  call    qword ptr [rax+8]
0x100bd80d2  mov     [rsp+0D00h+var_C94], eax
0x100bd80d6  mov     r8, [r13+0]
0x100bd80da  lea     rdx, [rbp+0C00h+var_C0]
0x100bd80e1  mov     rcx, r13
0x100bd80e4  call    qword ptr [r8+18h]
0x100bd80e8  test    [rbp+0C00h+var_B8], 2
0x100bd80ef  jnz     loc_100BD817B
0x100bd80f5  mov     r8, gs:58h
0x100bd80fe  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x100bd8105  mov     edx, [rcx]
0x100bd8107  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x100bd810e  mov     ebx, [rcx]
0x100bd8110  add     rbx, [r8+rdx*8]
0x100bd8114  mov     rdx, [rbx+100h]
0x100bd811b  test    rdx, rdx
0x100bd811e  jnz     short loc_100BD812F
0x100bd8120  xor     ecx, ecx
0x100bd8122  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100bd8128  mov     rdx, [rbx+100h]
0x100bd812f  xor     eax, eax
0x100bd8131  mov     qword ptr [rsp+0D00h+var_CA8], rax
0x100bd8136  mov     qword ptr [rsp+0D00h+var_CB0], rax
0x100bd813b  mov     byte ptr [rsp+0D00h+var_CB8], al
0x100bd813f  mov     byte ptr [rsp+0D00h+var_CC0], 1
0x100bd8144  mov     dword ptr [rsp+0D00h+var_CC8], eax
0x100bd8148  mov     dword ptr [rsp+0D00h+Src], 0FFFFFFFFh
0x100bd8150  mov     eax, [rsp+0D00h+var_C94]
0x100bd8154  mov     dword ptr [rsp+0D00h+var_CD8], eax
0x100bd8158  mov     eax, [rbp+0C00h+var_C4C]
0x100bd815b  mov     dword ptr [rsp+0D00h+var_CE0], eax
0x100bd815f  mov     r9d, eax
0x100bd8162  mov     r8, [rsi+38h]
0x100bd8166  mov     rdx, [rdx+3E8h]
0x100bd816d  mov     ecx, 4C414650h
0x100bd8172  call    ?CheckPermRule@ISECManager@@SAEW4ESECSecuredOperation@@PEAVIMemObj@@PEAVIMetadataAccess@@KKKKW4EObjType@@EEPEAVIUserToken@@PEAVISecContextToken@@@Z; ISECManager::CheckPermRule(ESECSecuredOperation,IMemObj *,IMetadataAccess *,ulong,ulong,ulong,ulong,EObjType,uchar,uchar,IUserToken *,ISecContextToken *)
0x100bd8177  test    al, al
0x100bd8179  jnz     short loc_100BD81BA
0x100bd817b  mov     rax, [r12+8A0h]
0x100bd8183  mov     qword ptr [rsp+0D00h+var_CC8], rax
0x100bd8188  mov     eax, [r12+8A8h]
0x100bd8190  mov     dword ptr [rsp+0D00h+Src], eax
0x100bd8194  mov     dword ptr [rsp+0D00h+var_CD8], 3357h
0x100bd819c  mov     dword ptr [rsp+0D00h+var_CE0], 3320h
0x100bd81a4  mov     edx, 33h ; '3'
0x100bd81a9  lea     ecx, [rdx+64h]
0x100bd81ac  lea     r9d, [rdx-32h]
0x100bd81b0  lea     r8d, [rdx-23h]
0x100bd81b4  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100bd81ba  mov     rsi, [rdi+78h]
0x100bd81be  mov     [rbp+0C00h+var_C60], rsi
0x100bd81c2  mov     [rbp+0C00h+var_A00], rsi
0x100bd81c9  lea     rcx, [rbp+0C00h+var_870]; this
0x100bd81d0  call    ??0CExecutionCollection@@QEAA@XZ; CExecutionCollection::CExecutionCollection(void)
0x100bd81d5  nop
0x100bd81d6  mov     rax, [rbp+0C00h+var_C58]
0x100bd81da  mov     rdi, [rax+80h]
0x100bd81e1  mov     rbx, [rax+38h]
0x100bd81e5  mov     r8, rsi; struct IMemObj *
0x100bd81e8  mov     rdx, [r12+70h]; struct CEnvCollection *
0x100bd81ed  lea     rcx, [rbp+0C00h+var_870]; this
0x100bd81f4  call    ?AllocateMembers@CExecutionCollection@@QEAAXPEAVCEnvCollection@@PEAVIMemObj@@@Z; CExecutionCollection::AllocateMembers(CEnvCollection *,IMemObj *)
0x100bd81f9  mov     [rbp+0C00h+var_7C8], rbx
0x100bd8200  test    rbx, rbx
0x100bd8203  jz      short loc_100BD8210
0x100bd8205  mov     rax, [rbx]
0x100bd8208  mov     rcx, rbx
0x100bd820b  call    qword ptr [rax+10h]
0x100bd820e  jmp     short loc_100BD8212
0x100bd8210  xor     eax, eax
0x100bd8212  mov     [rbp+0C00h+var_7D0], rax
0x100bd8219  test    rdi, rdi
0x100bd821c  jz      short loc_100BD8233
0x100bd821e  mov     [rbp+0C00h+var_7A0], rdi
0x100bd8225  lea     rax, [rbp+0C00h+var_870]
0x100bd822c  mov     [rdi+1B0h], rax
0x100bd8233  or      [rbp+0C00h+var_7C0], 8
0x100bd823a  mov     r9, 0FFFFFFFFFFFFFFFFh
0x100bd8241  lea     r8, [rbp+0C00h+var_870]
0x100bd8248  mov     rdx, r15
0x100bd824b  mov     rcx, [r12+70h]
0x100bd8250  call    ?XretSchemaChanged@CEnvCollection@@QEBA?AW4EXRetType@@AEBVCCompExecCtxt@@PEAVCExecutionCollection@@H@Z; CEnvCollection::XretSchemaChanged(CCompExecCtxt const &,CExecutionCollection *,int)
0x100bd8255  mov     edi, eax
0x100bd8257  test    eax, eax
0x100bd8259  jnz     loc_100BD9BC9
0x100bd825f  cmp     [r15], al
0x100bd8262  jz      short loc_100BD826A
0x100bd8264  mov     eax, [r15+68h]
0x100bd8268  jmp     short loc_100BD8280
0x100bd826a  mov     r8, r15
0x100bd826d  lea     rdx, [rbp+0C00h+var_C38]
0x100bd8271  mov     rcx, [r15+80h]
0x100bd8278  call    ?GetCurCompatLevel@CExecLvlIntCtxt@@AEBA?AVCCompatLevel@@VContextHandle@@@Z; CExecLvlIntCtxt::GetCurCompatLevel(ContextHandle)
0x100bd827d  mov     eax, [rbp+0C00h+var_C38]
0x100bd8280  cmp     eax, 8Ch
0x100bd8285  setnl   bl
0x100bd8288  jge     short loc_100BD82E5
0x100bd828a  cmp     cs:byte_102EDCA9A, 0
0x100bd8291  jnz     short loc_100BD82E5
0x100bd8293  mov     rax, cs:qword_102ECFB10
0x100bd829a  test    byte ptr [rax+9Ah], 20h
0x100bd82a1  jnz     short loc_100BD82EC
0x100bd82a3  mov     r8, gs:58h
0x100bd82ac  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100bd82b3  mov     ecx, [rax]
0x100bd82b5  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100bd82bc  mov     edx, [rax]
0x100bd82be  add     rdx, [r8+rcx*8]
0x100bd82c2  mov     rax, [rdx]
0x100bd82c5  test    rax, rax
0x100bd82c8  jz      short loc_100BD8344
0x100bd82ca  mov     rax, [rax+38h]
0x100bd82ce  mov     rcx, [rax]
0x100bd82d1  test    rcx, rcx
0x100bd82d4  jz      short loc_100BD8344
0x100bd82d6  mov     edx, 4D5h
0x100bd82db  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100bd82e1  test    eax, eax
0x100bd82e3  jz      short loc_100BD8344
0x100bd82e5  mov     rax, cs:qword_102ECFB10
0x100bd82ec  test    bl, bl
0x100bd82ee  jz      short loc_100BD8348
0x100bd82f0  cmp     cs:byte_102EDCA99, 0
0x100bd82f7  jnz     short loc_100BD8344
0x100bd82f9  test    byte ptr [rax+9Ah], 40h
0x100bd8300  jnz     short loc_100BD8344
0x100bd8302  mov     r8, gs:58h
0x100bd830b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100bd8312  mov     ecx, [rax]
0x100bd8314  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100bd831b  mov     edx, [rax]
0x100bd831d  add     rdx, [r8+rcx*8]
0x100bd8321  mov     rax, [rdx]
0x100bd8324  test    rax, rax
0x100bd8327  jz      short loc_100BD8348
0x100bd8329  mov     rax, [rax+38h]
0x100bd832d  mov     rcx, [rax]
0x100bd8330  test    rcx, rcx
0x100bd8333  jz      short loc_100BD8348
0x100bd8335  mov     edx, 4D6h
0x100bd833a  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100bd8340  test    eax, eax
0x100bd8342  jz      short loc_100BD8348
0x100bd8344  mov     al, 1
0x100bd8346  jmp     short loc_100BD834A
0x100bd8348  xor     al, al
0x100bd834a  xor     ebx, ebx
0x100bd834c  mov     [rbp+0C00h+var_C48], rbx
0x100bd8350  test    al, al
0x100bd8352  jz      short loc_100BD83BF
0x100bd8354  mov     rdx, gs:58h
0x100bd835d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100bd8364  mov     ecx, [rax]
0x100bd8366  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100bd836d  mov     ebx, [rax]
0x100bd836f  add     rbx, [rdx+rcx*8]
0x100bd8373  mov     rax, [rbx+100h]
0x100bd837a  test    rax, rax
0x100bd837d  jnz     short loc_100BD838E
0x100bd837f  xor     ecx, ecx
0x100bd8381  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100bd8387  mov     rax, [rbx+100h]
0x100bd838e  mov     rbx, [rax+258h]
0x100bd8395  mov     rcx, rbx
0x100bd8398  call    cs:__imp_?GetDeadlockPriority@SOS_Task@@QEBA?AW4TASK_DEADLOCK_PRIORITY@1@XZ; SOS_Task::GetDeadlockPriority(void)
0x100bd839e  mov     edi, eax
0x100bd83a0  cmp     eax, 0Ah
0x100bd83a3  jz      short loc_100BD83BD
0x100bd83a5  mov     edx, 0Ah
0x100bd83aa  mov     rcx, rbx
0x100bd83ad  call    cs:__imp_?SetDeadlockPriority@SOS_Task@@QEAAXW4TASK_DEADLOCK_PRIORITY@1@@Z; SOS_Task::SetDeadlockPriority(SOS_Task::TASK_DEADLOCK_PRIORITY)
0x100bd83b3  mov     dword ptr [rbp+0C00h+var_C48+4], 1
0x100bd83ba  mov     dword ptr [rbp+0C00h+var_C48], edi
0x100bd83bd  xor     ebx, ebx
0x100bd83bf  lea     rax, ??_7IMEDPrtFunction@@6B@; const IMEDPrtFunction::`vftable'
0x100bd83c6  mov     [rbp+0C00h+var_A0], rax
0x100bd83cd  lea     rax, ??_7CPreAlterPrtFunc@@6B@; const CPreAlterPrtFunc::`vftable'
0x100bd83d4  mov     [rbp+0C00h+var_A0], rax
0x100bd83db  mov     [rbp+0C00h+var_98], rbx
0x100bd83e2  mov     [rbp+0C00h+var_88], rbx
0x100bd83e9  mov     [rbp+0C00h+var_80], rbx
0x100bd83f0  mov     [rbp+0C00h+var_90], ebx
0x100bd83f6  xor     eax, eax
0x100bd83f8  mov     [rbp+0C00h+var_78], rax
0x100bd83ff  mov     [rbp+0C00h+var_70], eax
0x100bd8405  mov     [rbp+0C00h+var_68], rax
0x100bd840c  mov     r8, rsi; struct IMemObj *
0x100bd840f  mov     rdx, r13; struct IMEDPrtFunction *
0x100bd8412  lea     rcx, [rbp+0C00h+var_A0]; this
0x100bd8419  call    ?Init@CPreAlterPrtFunc@@QEAAXPEAVIMEDPrtFunction@@PEAVIMemObj@@@Z; CPreAlterPrtFunc::Init(IMEDPrtFunction *,IMemObj *)
0x100bd841e  cmp     qword ptr [r12+8C8h], 0
0x100bd8427  jnz     short loc_100BD843F
0x100bd8429  mov     edx, 0Eh
0x100bd842e  lea     ecx, [rdx+3Fh]
0x100bd8431  lea     r9d, [rdx-0Dh]
0x100bd8435  lea     r8d, [rdx+2]
0x100bd8439  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100bd843f  movzx   eax, byte ptr [r12+8ACh]
0x100bd8448  test    al, al
0x100bd844a  jnz     short loc_100BD8477
0x100bd844c  cmp     [rbp+0C00h+var_BC], 1
0x100bd8453  jnz     short loc_100BD84A1
0x100bd8455  mov     edx, 10h
0x100bd845a  lea     ecx, [rdx+3Dh]
0x100bd845d  lea     r9d, [rdx-0Eh]
0x100bd8461  mov     r8d, edx
0x100bd8464  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100bd846a  movzx   eax, byte ptr [r12+8ACh]
0x100bd8473  test    al, al
0x100bd8475  jz      short loc_100BD84A1
0x100bd8477  cmp     [rbp+0C00h+var_BC], 3A98h
0x100bd8481  jnz     short loc_100BD84A1
0x100bd8483  mov     dword ptr [rsp+0D00h+var_CE0], 3A98h
  ... truncated ...
```
