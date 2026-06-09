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
  __int64 v38; // rcx
  __int64 i; // r15
  __int64 v40; // rax
  unsigned int v41; // eax
  _QWORD *v42; // rbx
  __int64 v43; // r8
  unsigned int v44; // r13d
  __int64 v45; // rax
  struct IMEDRelation *v46; // r14
  __int64 v47; // rdi
  _QWORD *v48; // r12
  __int64 v49; // rax
  __int64 v50; // rsi
  _QWORD *v51; // rbx
  struct BaseXact *v52; // rax
  int v53; // ebx
  unsigned int v54; // eax
  __int64 v55; // rax
  int v56; // r9d
  __int64 v57; // r11
  __int64 v58; // rcx
  bool v59; // al
  int v60; // ecx
  struct IMemObj *v61; // r15
  CXVariant *v62; // rsi
  unsigned int v63; // edi
  __int64 v64; // r8
  unsigned int v65; // ebx
  unsigned int v66; // r14d
  const struct CXVariant *v67; // rax
  bool v68; // zf
  unsigned int v69; // edi
  unsigned int v70; // r13d
  __int64 v71; // rbx
  __int64 v72; // r8
  __int64 v73; // rbx
  unsigned int v74; // eax
  __int64 v75; // r9
  __int64 v76; // r8
  __int64 v77; // rax
  __int64 v78; // r8
  struct IMEDPrtFunction *v79; // r14
  __int64 v80; // rdx
  __int64 v81; // r8
  __int64 v82; // rsi
  __int64 v83; // r8
  __int64 v84; // rdi
  __int64 v85; // r8
  __int64 v86; // rax
  __int64 v87; // r8
  __int64 v88; // rbx
  unsigned int v89; // eax
  __int64 v90; // rbx
  unsigned int v91; // eax
  __int64 v92; // r14
  __int64 v93; // rsi
  __int64 v94; // r8
  __int64 v95; // rax
  __int64 v96; // r8
  __int64 v97; // rbx
  __int64 v98; // r8
  __int64 v99; // rdi
  __int64 v100; // rbx
  unsigned int v101; // eax
  __int64 v102; // rbx
  unsigned int v103; // eax
  unsigned int v104; // esi
  __int64 v105; // rax
  struct IMEDRelation *v106; // r12
  __int64 v107; // rax
  __int64 v108; // rbx
  __int64 v109; // rax
  struct IMEDIndex *j; // rdx
  struct IMEDIndex *v111; // rdi
  __int64 v112; // rbx
  unsigned int v113; // eax
  __int64 v114; // rax
  __int64 v115; // rbx
  __int64 v116; // rax
  __int64 v117; // rdx
  __int64 v118; // rax
  unsigned int v119; // ebx
  unsigned int v120; // r12d
  unsigned int k; // ebx
  __int64 v122; // rcx
  unsigned int v123; // eax
  unsigned int v124; // ecx
  __int64 v125; // rdx
  __int64 v126; // r14
  unsigned int v127; // esi
  __int64 v128; // r15
  struct IMEDIndex *v129; // rbx
  int v130; // edi
  char v131; // di
  __int64 v132; // rcx
  bool v133; // di
  struct IMEDIndex *v134; // rdx
  unsigned int v135; // ebx
  struct IMEDIndex *v136; // rsi
  int v137; // edi
  bool v138; // r15
  bool v139; // al
  bool v140; // r12
  unsigned int v141; // edi
  char v142; // bl
  __int64 v143; // rcx
  unsigned __int64 v144; // r12
  __int64 v145; // rbx
  __int64 v146; // r10
  unsigned __int64 v147; // rax
  __int64 v148; // rcx
  void *v149; // rdi
  unsigned int v150; // ebx
  unsigned int v151; // eax
  __int64 v152; // rax
  int v153; // eax
  char v154; // r15
  unsigned int v155; // ebx
  unsigned int v156; // eax
  __int64 v157; // rdi
  int v158; // edx
  BOOL v159; // ecx
  __int64 v160; // rax
  int v161; // ecx
  __int64 v162; // rbx
  bool v163; // r15
  CSQLStrings *v164; // rax
  __int64 v165; // r8
  CSQLStrings *v166; // rax
  __int64 v167; // rcx
  __int64 v168; // rcx
  unsigned int v169; // ecx
  unsigned int v170; // ecx
  unsigned int v171; // r15d
  __int64 v172; // r9
  __int64 ModCounterBeforeDrop; // rbx
  __int64 v174; // r9
  unsigned int v175; // ebx
  __int64 v176; // rsi
  struct IMEDIndex *v177; // rdx
  __int64 v178; // rax
  _DWORD *v179; // rax
  int v180; // eax
  __int64 v181; // rbx
  __int64 v182; // rax
  __int64 v183; // rbx
  __int64 v184; // rcx
  struct CXVariant *v186; // [rsp+20h] [rbp-E0h]
  struct CXVariant *v187; // [rsp+20h] [rbp-E0h]
  struct CXVariant *v188; // [rsp+20h] [rbp-E0h]
  wchar_t *v189; // [rsp+28h] [rbp-D8h]
  wchar_t *v190; // [rsp+28h] [rbp-D8h]
  wchar_t *v191; // [rsp+28h] [rbp-D8h]
  wchar_t *Src; // [rsp+30h] [rbp-D0h]
  __int64 v193; // [rsp+38h] [rbp-C8h]
  bool v194[8]; // [rsp+38h] [rbp-C8h]
  bool *v195; // [rsp+40h] [rbp-C0h]
  bool v196; // [rsp+60h] [rbp-A0h]
  unsigned int v197; // [rsp+64h] [rbp-9Ch]
  unsigned int v198; // [rsp+68h] [rbp-98h]
  unsigned int v199; // [rsp+6Ch] [rbp-94h]
  struct IMEDPrtFunction *v201; // [rsp+78h] [rbp-88h]
  __int64 v202; // [rsp+80h] [rbp-80h]
  _BYTE v203[4]; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v204; // [rsp+90h] [rbp-70h]
  unsigned int v205; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v206; // [rsp+98h] [rbp-68h]
  int v207; // [rsp+9Ch] [rbp-64h]
  struct IMemObj *v208; // [rsp+A0h] [rbp-60h]
  __int64 v209; // [rsp+A8h] [rbp-58h]
  unsigned int v210; // [rsp+B0h] [rbp-50h]
  unsigned int v211; // [rsp+B4h] [rbp-4Ch]
  __int64 v212; // [rsp+B8h] [rbp-48h]
  struct CCompExecCtxtStmt *v213; // [rsp+C0h] [rbp-40h]
  int v214; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v215; // [rsp+CCh] [rbp-34h]
  struct IMEDRelation *v216; // [rsp+D0h] [rbp-30h]
  __int64 v217; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v218; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v219; // [rsp+ECh] [rbp-14h]
  int v220; // [rsp+F0h] [rbp-10h]
  __int64 v221; // [rsp+F8h] [rbp-8h]
  _BYTE v222[16]; // [rsp+100h] [rbp+0h] BYREF
  __int16 v223; // [rsp+110h] [rbp+10h]
  unsigned __int8 v224; // [rsp+112h] [rbp+12h]
  unsigned __int8 v225; // [rsp+113h] [rbp+13h]
  int v226; // [rsp+114h] [rbp+14h]
  void **v227; // [rsp+120h] [rbp+20h] BYREF
  __int128 v228; // [rsp+128h] [rbp+28h]
  char v229; // [rsp+138h] [rbp+38h]
  __int64 v230; // [rsp+140h] [rbp+40h]
  int v231; // [rsp+148h] [rbp+48h] BYREF
  char v232; // [rsp+14Ch] [rbp+4Ch]
  _QWORD *v233; // [rsp+150h] [rbp+50h]
  __int64 v234; // [rsp+158h] [rbp+58h]
  char v235; // [rsp+160h] [rbp+60h] BYREF
  _DWORD *v236; // [rsp+168h] [rbp+68h]
  int v237; // [rsp+170h] [rbp+70h]
  __int64 v238; // [rsp+178h] [rbp+78h]
  int v239; // [rsp+180h] [rbp+80h] BYREF
  _DWORD *v240; // [rsp+188h] [rbp+88h]
  int v241; // [rsp+190h] [rbp+90h]
  __int64 v242; // [rsp+198h] [rbp+98h]
  void *v243; // [rsp+1A0h] [rbp+A0h]
  __int64 v244; // [rsp+1A8h] [rbp+A8h]
  bool v245; // [rsp+1B0h] [rbp+B0h]
  int v246; // [rsp+1B8h] [rbp+B8h]
  struct CEsComp *v247; // [rsp+1C0h] [rbp+C0h] BYREF
  int v248; // [rsp+1C8h] [rbp+C8h] BYREF
  int v249; // [rsp+1D0h] [rbp+D0h] BYREF
  void *v250; // [rsp+1D8h] [rbp+D8h]
  int v251; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v252; // [rsp+1E8h] [rbp+E8h]
  int v253; // [rsp+1F8h] [rbp+F8h]
  __int64 v254; // [rsp+200h] [rbp+100h] BYREF
  int v255; // [rsp+208h] [rbp+108h]
  __int64 v256; // [rsp+20Ch] [rbp+10Ch]
  int v257; // [rsp+214h] [rbp+114h]
  int v258; // [rsp+218h] [rbp+118h]
  __int64 v259; // [rsp+21Ch] [rbp+11Ch]
  __int64 v260; // [rsp+228h] [rbp+128h] BYREF
  int v261; // [rsp+230h] [rbp+130h]
  __int64 v262; // [rsp+234h] [rbp+134h]
  int v263; // [rsp+23Ch] [rbp+13Ch]
  int v264; // [rsp+240h] [rbp+140h]
  __int64 v265; // [rsp+244h] [rbp+144h]
  __int64 v266; // [rsp+250h] [rbp+150h] BYREF
  int v267; // [rsp+258h] [rbp+158h]
  __int64 v268; // [rsp+25Ch] [rbp+15Ch]
  int v269; // [rsp+264h] [rbp+164h]
  int v270; // [rsp+268h] [rbp+168h]
  __int64 v271; // [rsp+26Ch] [rbp+16Ch]
  __int64 v272; // [rsp+278h] [rbp+178h] BYREF
  int v273; // [rsp+280h] [rbp+180h]
  _QWORD v274[5]; // [rsp+290h] [rbp+190h] BYREF
  int v275; // [rsp+2B8h] [rbp+1B8h]
  void *v276; // [rsp+2C0h] [rbp+1C0h]
  int v277; // [rsp+2C8h] [rbp+1C8h]
  unsigned int *v278; // [rsp+2D0h] [rbp+1D0h]
  unsigned int v279; // [rsp+2D8h] [rbp+1D8h]
  BOOL v280; // [rsp+2DCh] [rbp+1DCh]
  CSQLStrings *v281; // [rsp+2E0h] [rbp+1E0h]
  __int64 v282; // [rsp+2E8h] [rbp+1E8h]
  __int64 v283; // [rsp+2F0h] [rbp+1F0h]
  bool v284; // [rsp+2F8h] [rbp+1F8h]
  struct IMemObj *v285; // [rsp+300h] [rbp+200h]
  __int128 v286; // [rsp+310h] [rbp+210h] BYREF
  __int128 v287; // [rsp+320h] [rbp+220h]
  __int128 v288; // [rsp+330h] [rbp+230h]
  __int128 v289; // [rsp+340h] [rbp+240h]
  __int128 v290; // [rsp+350h] [rbp+250h]
  __int128 v291; // [rsp+360h] [rbp+260h] BYREF
  __int128 v292; // [rsp+370h] [rbp+270h]
  __int128 v293; // [rsp+380h] [rbp+280h]
  __int128 v294; // [rsp+390h] [rbp+290h]
  __int128 v295; // [rsp+3A0h] [rbp+2A0h]
  _BYTE v296[112]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _BYTE v297[112]; // [rsp+420h] [rbp+320h] BYREF
  _BYTE v298[160]; // [rsp+490h] [rbp+390h] BYREF
  __int64 v299; // [rsp+530h] [rbp+430h]
  __int64 v300; // [rsp+538h] [rbp+438h]
  char v301; // [rsp+540h] [rbp+440h]
  __int64 v302; // [rsp+560h] [rbp+460h]
  _BYTE v303[56]; // [rsp+5A0h] [rbp+4A0h] BYREF
  struct XDES *v304; // [rsp+5D8h] [rbp+4D8h]
  __int128 v305; // [rsp+670h] [rbp+570h]
  char v306; // [rsp+680h] [rbp+580h]
  _BYTE v307[848]; // [rsp+8F0h] [rbp+7F0h] BYREF
  int v308; // [rsp+C40h] [rbp+B40h] BYREF
  unsigned int v309; // [rsp+C44h] [rbp+B44h]
  char v310; // [rsp+C48h] [rbp+B48h]
  unsigned __int8 v311[2]; // [rsp+C50h] [rbp+B50h] BYREF
  unsigned __int8 v312; // [rsp+C54h] [rbp+B54h]
  unsigned __int8 v313; // [rsp+C55h] [rbp+B55h]
  int v314; // [rsp+C58h] [rbp+B58h]
  _QWORD v315[2]; // [rsp+C60h] [rbp+B60h] BYREF
  int v316; // [rsp+C70h] [rbp+B70h]
  __int64 v317; // [rsp+C78h] [rbp+B78h]
  __int64 v318; // [rsp+C80h] [rbp+B80h]
  __int64 v319; // [rsp+C88h] [rbp+B88h]
  int v320; // [rsp+C90h] [rbp+B90h]
  __int64 v321; // [rsp+C98h] [rbp+B98h]
  char v322[8]; // [rsp+CA0h] [rbp+BA0h] BYREF
  int v323; // [rsp+CA8h] [rbp+BA8h]

  v282 = -2;
  v209 = a3;
  v213 = (struct CCompExecCtxtStmt *)a2;
  v7 = a1;
  v8 = *(_QWORD *)(a2 + 144);
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v8 + 496LL))(v8) )
  {
    v9 = (BaseXact *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 432LL))(v8);
    if ( BaseXact::IsSnapshotXact(v9) )
      ex_raise(39, 64, 16, 1);
  }
  v211 = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                       + SystemThread_TlsIndex)
                                                     + SystemThread_TlsOffset)
                                         + 80LL)
                             + 8LL);
  v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(**(_QWORD **)(a3 + 56) + 56LL))(
          *(_QWORD *)(a3 + 56),
          v211,
          0,
          0,
          0,
          0);
  v202 = v10;
  v11 = *(_DWORD *)(v7 + 2216);
  v272 = *(_QWORD *)(v7 + 2208);
  v273 = v11;
  LOBYTE(v12) = 1;
  LOBYTE(v13) = 5;
  v14 = (struct IMEDPrtFunction *)(*(__int64 (__fastcall **)(__int64, __int64 *, __int64, __int64))(*(_QWORD *)v10
                                                                                                  + 640LL))(
                                    v10,
                                    &v272,
                                    v13,
                                    v12);
  v201 = v14;
  if ( !v14 )
  {
    LODWORD(v189) = 13143;
    LODWORD(v186) = 13088;
    ex_raise(151, 51, 16, 1, v186, v189, *(_DWORD *)(v7 + 2216), *(_QWORD *)(v7 + 2208));
  }
  v199 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *))(*(_QWORD *)v14 + 8LL))(v14);
  (*(void (__fastcall **)(struct IMEDPrtFunction *, int *))(*(_QWORD *)v14 + 24LL))(v14, &v308);
  if ( (v310 & 2) != 0 )
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
                           v211,
                           v211,
                           v199,
                           -1,
                           0,
                           1,
                           0,
                           0,
                           0) )
  {
LABEL_10:
    LODWORD(Src) = *(_DWORD *)(v7 + 2216);
    LODWORD(v189) = 13143;
    LODWORD(v186) = 13088;
    ex_raise(151, 51, 16, 1, v186, v189, Src, *(_QWORD *)(v7 + 2208));
  }
  v17 = *(struct IMemObj **)(a4 + 120);
  v208 = v17;
  v285 = v17;
  CExecutionCollection::CExecutionCollection((CExecutionCollection *)v298);
  v18 = *(_QWORD *)(v209 + 128);
  v19 = *(_QWORD *)(v209 + 56);
  CExecutionCollection::AllocateMembers((CExecutionCollection *)v298, *(struct CEnvCollection **)(v7 + 112), v17);
  v300 = v19;
  if ( v19 )
    v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  else
    v20 = 0;
  v299 = v20;
  if ( v18 )
  {
    v302 = v18;
    *(_QWORD *)(v18 + 432) = v298;
  }
  v301 |= 8u;
  v21 = CEnvCollection::XretSchemaChanged(*(_QWORD *)(v7 + 112), a2, v298, -1);
  if ( v21 )
    goto LABEL_277;
  if ( *(_BYTE *)a2 )
  {
    v22 = *(_DWORD *)(a2 + 104);
  }
  else
  {
    CExecLvlIntCtxt::GetCurCompatLevel(*(_QWORD *)(a2 + 128), &v214, a2);
    v22 = v214;
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
  v212 = 0;
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
      v212 = DeadlockPriority | 0x100000000LL;
    }
  }
  v315[0] = &CPreAlterPrtFunc::`vftable';
  v315[1] = 0;
  v317 = 0;
  v318 = 0;
  v316 = 0;
  v319 = 0;
  v320 = 0;
  v321 = 0;
  CPreAlterPrtFunc::Init((CPreAlterPrtFunc *)v315, v14, v17);
  if ( !*(_QWORD *)(v7 + 2248) )
    ex_raise(77, 14, 16, 1);
  if ( *(_BYTE *)(v7 + 2220) || v309 == 1 && (ex_raise(77, 16, 16, 2), *(_BYTE *)(v7 + 2220)) )
  {
    if ( v309 == 15000 )
    {
      LODWORD(v186) = 15000;
      ex_raise(77, 19, 16, 1, v186);
    }
  }
  v34 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *))(*(_QWORD *)v14 + 80LL))(v14);
  if ( v34 )
  {
    LOBYTE(v189) = 1;
    LOBYTE(v186) = 0;
    LOBYTE(v35) = 1;
    v36 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD))(*(_QWORD *)v10 + 120LL))(
            v10,
            v34,
            v35,
            0,
            (_DWORD)v186,
            (_DWORD)v189,
            0,
            0);
    v37 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 40LL))(v36);
    *(_DWORD *)v194 = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 40LL))(v36) + 8);
    LODWORD(v190) = *(_DWORD *)(v7 + 2216);
    ex_raise(37, 29, 16, 3, L"ALTER PARTITION FUNCTION", v190, *(_QWORD *)(v7 + 2208), *(_QWORD *)v194, *v37);
  }
  v254 = 0;
  v256 = 0;
  v257 = 0;
  v259 = 1;
  v258 = -1;
  v255 = -2;
  LOBYTE(v35) = 5;
  for ( i = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *, _QWORD, __int64))(*(_QWORD *)v14 + 72LL))(v14, 0, v35);
        i;
        i = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *, __int64, __int64))(*(_QWORD *)v201 + 72LL))(
              v201,
              i,
              v43) )
  {
    v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)i + 40LL))(i);
    if ( *(_BYTE *)(v7 + 2220) )
    {
      v41 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      if ( v309 >= v41 )
      {
        v42 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)i + 16LL))(i);
        LODWORD(v186) = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)i + 16LL))(i) + 8);
        ex_raise(77, 10, 16, 1, v186, *v42);
      }
    }
    v44 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)i + 56LL))(i, 0);
    if ( v44 )
    {
      do
      {
        LODWORD(Src) = 0;
        LOBYTE(v189) = 1;
        LOBYTE(v186) = 0;
        LOBYTE(v43) = 2;
        v45 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, struct CXVariant *, _DWORD, wchar_t *, _DWORD))(*(_QWORD *)v10 + 120LL))(
                v10,
                v44,
                v43,
                0,
                v186,
                (_DWORD)v189,
                Src,
                0);
        v46 = (struct IMEDRelation *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 120LL))(v45);
        v47 = (**(__int64 (__fastcall ***)(struct IMEDRelation *))v46)(v46);
        v48 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 40LL))(v47);
        (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v47 + 96LL))(v47, v322);
        if ( v323 == 8277 )
        {
          v49 = (*(__int64 (__fastcall **)(struct IMEDRelation *, __int64))(*(_QWORD *)v46 + 232LL))(v46, 1);
          v50 = v49;
          if ( v49 )
          {
            (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v49 + 40LL))(v49, &v254);
            if ( (v254 & 0x1000) != 0 )
            {
              v51 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v50 + 24LL))(v50);
              LODWORD(v195) = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v50 + 24LL))(v50) + 8);
              LODWORD(Src) = *(_DWORD *)(a1 + 2216);
              LODWORD(v186) = *((_DWORD *)v48 + 2);
              ex_raise(77, 25, 16, 1, v186, *v48, Src, *(_QWORD *)(a1 + 2208), v195, *v51);
            }
          }
          CIndexDDL::CIndexDDL((CIndexDDL *)v307, *(struct IMetadataAccess **)(v209 + 56), v46, v208, 0, 0, 0, 0, 0);
          v52 = (struct BaseXact *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v209 + 56) + 16LL))(*(_QWORD *)(v209 + 56));
          CIndexDDL::InvalidateTxtPtrs((CIndexDDL *)v307, v52);
          CIndexDDL::~CIndexDDL((CIndexDDL *)v307);
        }
        v53 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 8LL))(v47);
        v54 = (**(__int64 (__fastcall ***)(__int64))v47)(v47);
        if ( CExecLvlIntCtxt::FTableIsTriggerTarget(*((CExecLvlIntCtxt **)v213 + 16), v54, v53) )
        {
          LODWORD(v189) = *((_DWORD *)v48 + 2);
          ex_raise(17, 13, 16, 10, L"ALTER PARTITION FUNCTION", v189, *v48);
        }
        v44 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)i + 56LL))(i, v44);
        v10 = v202;
      }
      while ( v44 );
      v7 = a1;
    }
    v14 = v201;
    LOBYTE(v43) = 5;
  }
  v251 = 3;
  v252 = 0;
  v253 = 0;
  v247 = *(struct CEsComp **)(v7 + 2248);
  if ( v247 )
    CExprProcessor::Eval(v213, *(struct CExecContext **)(v209 + 128), 1u, &v247, (struct CXVariant *const)&v251);
  if ( *(_BYTE *)(GetXdbServerGlobals(v38) + 12004) && (_BYTE)v251 == 3 )
    ex_raise(224, 44, 16, 2);
  v55 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *, __int64))(*(_QWORD *)v14 + 48LL))(v14, 1);
  (*(void (__fastcall **)(__int64, unsigned __int8 *))(*(_QWORD *)v55 + 8LL))(v55, v311);
  CTypeInfo::Init((CTypeInfo *)v222, v311[0]);
  v58 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + v222[0]);
  if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsNumeric + v58) )
  {
    v224 = v312;
    v225 = v313;
    v223 = (unsigned __int8)byte_102445B17[v312];
  }
  else if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsVarTime + v58) )
  {
    CTypeInfo::SetPrecScaleLenForVarTime(v222, v313);
  }
  else if ( !*((_BYTE *)&CTypeInfo::sxm_rgfIsConstantMaxLength + v58) )
  {
    if ( !v56
      && *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWStringOrBinary + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v57)) == 1 )
    {
      LOWORD(v56) = (*((_BYTE *)&CTypeInfo::sxm_rgfIsWString + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v57)) != 0) + 1;
    }
    v223 = v56;
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + v58) || ((v222[0] - 35) & 0xBF) == 0 )
    {
      v59 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)v222);
      v60 = v226;
      if ( v59 )
        v60 = v314;
      v226 = v60;
    }
  }
  v61 = v208;
  v62 = CheckPrtRangeTypConversion(
          (struct CXVariant *)&v251,
          *(struct CTypeInfo **)(v7 + 2240),
          (struct CTypeInfo *)v222,
          v208,
          1u);
  v63 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *))(*(_QWORD *)v14 + 56LL))(v14);
  v65 = 5;
  v66 = 1;
  v204 = 1;
  if ( v63 )
  {
    _mm_lfence();
    do
    {
      v67 = (const struct CXVariant *)(*(__int64 (__fastcall **)(struct IMEDPrtFunction *, _QWORD, struct IMemObj *))(*(_QWORD *)v14 + 64LL))(
                                        v14,
                                        v66,
                                        v208);
      v65 = CXVariant::CmpCompare(v62, (const struct CTypeInfo *)v222, (const struct CTypeInfo *)v222, v67);
      if ( !*(_BYTE *)(v7 + 2220)
        || (v65 == 2 || v65 == 88) && (LODWORD(v187) = v66, ex_raise(77, 21, 16, 1, v187), !*(_BYTE *)(v7 + 2220)) )
      {
        if ( v65 == 2 )
          break;
        v68 = v65 == 88;
      }
      else
      {
        if ( v65 == 1 )
          break;
        v68 = v65 == 40;
      }
      if ( v68 )
        break;
      ++v66;
    }
    while ( v66 <= v63 );
    v204 = v66;
  }
  if ( !*(_BYTE *)(v7 + 2220) && v65 != 2 && v65 != 88 )
    ex_raise(77, 15, 16, 1);
  v205 = 0;
  v69 = v66 + 1;
  v70 = v66 + 1;
  if ( (v310 & 1) != 0 )
    v69 = v66;
  else
    v70 = v66;
  v197 = v69;
  LOBYTE(v64) = 2;
  v71 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *, _QWORD, __int64))(*(_QWORD *)v201 + 72LL))(v201, 0, v64);
  if ( v71 )
  {
    do
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 40LL))(v71);
      LOBYTE(v72) = 2;
      v71 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *, __int64, __int64))(*(_QWORD *)v201 + 72LL))(
              v201,
              v71,
              v72);
    }
    while ( v71 );
    v61 = v208;
  }
  v73 = *(_QWORD *)v202;
  v74 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *))(*(_QWORD *)v201 + 8LL))(v201);
  LOBYTE(v75) = 1;
  LOBYTE(v76) = 2;
  (*(void (__fastcall **)(__int64, _QWORD, __int64, __int64))(v73 + 648))(v202, v74, v76, v75);
  v77 = *(_QWORD *)v201;
  if ( *(_BYTE *)(v7 + 2220) )
  {
    v78 = v66;
    v79 = v201;
    (*(void (__fastcall **)(struct IMEDPrtFunction *, CXVariant *, __int64))(v77 + 112))(v201, v62, v78);
  }
  else
  {
    v80 = v66;
    v79 = v201;
    (*(void (__fastcall **)(struct IMEDPrtFunction *, __int64))(v77 + 120))(v201, v80);
  }
  (*(void (__fastcall **)(struct IMEDPrtFunction *))(*(_QWORD *)v79 + 96LL))(v79);
  LOBYTE(v81) = 2;
  v82 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *, _QWORD, __int64))(*(_QWORD *)v79 + 72LL))(v79, 0, v81);
  if ( v82 )
  {
    do
    {
      v84 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v82 + 40LL))(v82);
      LOBYTE(v85) = 1;
      v86 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v84 + 24LL))(v84, 1, v85);
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v86 + 24LL))(v86, &v248);
      if ( v248 == 3 )
      {
        if ( *(_BYTE *)(v7 + 2220) )
        {
          v88 = *(_QWORD *)v84;
          v89 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(v88 + 56))(v84, v89, v70);
        }
        else
        {
          if ( !v308 )
          {
            v90 = *(_QWORD *)v84;
            v91 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(v90 + 56))(v84, v70, v91);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 48LL))(v84);
        }
      }
      LOBYTE(v87) = 2;
      v82 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *, __int64, __int64))(*(_QWORD *)v79 + 72LL))(
              v79,
              v82,
              v87);
    }
    while ( v82 );
    v69 = v197;
  }
  LOBYTE(v83) = 2;
  v92 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *, __int64, __int64))(*(_QWORD *)v79 + 72LL))(v79, v82, v83);
  v230 = v92;
  if ( v92 )
  {
    while ( 1 )
    {
      v93 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v92 + 40LL))(v92);
      LOBYTE(v94) = 1;
      v95 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v93 + 24LL))(v93, 1, v94);
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v95 + 24LL))(v95, &v249);
      if ( v249 != 3 )
      {
        v196 = 0;
        if ( !*(_BYTE *)(v7 + 2220) && !v308 )
        {
          LOBYTE(v96) = 1;
          v97 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v93 + 24LL))(v93, v70, v96);
          LOBYTE(v98) = 1;
          v99 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v93 + 24LL))(v93, v69, v98);
          LODWORD(v97) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v97 + 8LL))(v97);
          if ( (_DWORD)v97 == (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v99 + 8LL))(v99) )
            v196 = 1;
        }
        if ( *(_BYTE *)(v7 + 2220) )
        {
          v100 = *(_QWORD *)v93;
          v101 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(v100 + 56))(v93, v101, v70);
        }
        else
        {
          if ( !v308 )
          {
            v102 = *(_QWORD *)v93;
            v103 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(v102 + 56))(v93, v70, v103);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 48LL))(v93);
        }
        v104 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v92 + 56LL))(v92, 0);
        v207 = v104;
        if ( v104 )
          break;
      }
LABEL_265:
      LOBYTE(v96) = 2;
      v92 = (*(__int64 (__fastcall **)(struct IMEDPrtFunction *, __int64, __int64))(*(_QWORD *)v201 + 72LL))(
              v201,
              v92,
              v96);
      v230 = v92;
      v69 = v197;
      if ( !v92 )
        goto LABEL_266;
    }
LABEL_130:
    LOBYTE(v189) = 1;
    LOBYTE(v187) = 0;
    LOBYTE(v96) = 2;
    v105 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _DWORD, wchar_t *, _DWORD, _DWORD))(*(_QWORD *)v202 + 120LL))(
             v202,
             v104,
             v96,
             0,
             (_DWORD)v187,
             v189,
             0,
             0);
    v106 = (struct IMEDRelation *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v105 + 120LL))(v105);
    v216 = v106;
    v107 = (**(__int64 (__fastcall ***)(struct IMEDRelation *))v106)(v106);
    v233 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v107 + 40LL))(v107);
    CIndexDDL::CIndexDDL((CIndexDDL *)v303, *(struct IMetadataAccess **)(v209 + 56), v106, v61, 0, 0, 0, 0, 0);
    v108 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v109 = *(_QWORD *)(v108 + 256);
    if ( !v109 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v109 = *(_QWORD *)(v108 + 256);
    }
    v218 = *(_QWORD *)(v109 + 1000);
    v219 = 0;
    v220 = 4;
    v221 = 0;
    for ( j = 0; ; j = v111 )
    {
      v111 = (struct IMEDIndex *)(*(__int64 (__fastcall **)(struct IMEDRelation *, struct IMEDIndex *, _QWORD))(*(_QWORD *)v106 + 360LL))(
                                   v106,
                                   j,
                                   0);
      if ( !v111 )
      {
        v123 = v219;
        v120 = 0;
        goto LABEL_149;
      }
      v112 = *(_QWORD *)v202;
      v113 = (*(__int64 (__fastcall **)(struct IMEDIndex *))(*(_QWORD *)v111 + 224LL))(v111);
      v114 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(v112 + 680))(v202, v113, 1);
      v115 = v114;
      if ( v114 )
      {
        v116 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v114 + 40LL))(v114);
        if ( v116 )
        {
          LOBYTE(v117) = 1;
          v118 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v116 + 8LL))(v116, v117);
          if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v118 + 8LL))(v118) == v199 )
          {
            v119 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v115 + 8LL))(v115);
            if ( v119 < (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v92 + 8LL))(v92) )
            {
              v120 = 0;
              for ( k = 0; k < v219; ++k )
              {
                v122 = *(_QWORD *)(v221 + 8LL * k);
                if ( v122 )
                {
                  v68 = (*(_DWORD *)(v122 + 8))-- == 1;
                  if ( v68 )
                    (**(void (__fastcall ***)(__int64, __int64))v122)(v122, 1);
                }
              }
              v123 = 0;
              v219 = 0;
LABEL_149:
              v215 = v123;
              if ( !v123 )
                goto LABEL_263;
              v124 = 0;
              v210 = 0;
              v125 = 0;
              v234 = 0;
              while ( 2 )
              {
                if ( v124 >= v123 )
                {
                  v126 = 0;
                }
                else
                {
                  v126 = *(_QWORD *)(v221 + 8 * v125);
                  if ( v126 )
                    v120 = *(_DWORD *)(v126 + 28);
                }
                v198 = v120;
                if ( *(_BYTE *)(a1 + 2220) )
                {
                  v127 = 0;
                  if ( v120 )
                  {
                    v128 = 0;
                    do
                    {
                      if ( v127 >= *(_DWORD *)(v126 + 28) )
                        v129 = 0;
                      else
                        v129 = *(struct IMEDIndex **)(v128 + *(_QWORD *)(v126 + 40));
                      (*(void (__fastcall **)(struct IMEDIndex *, _QWORD, int *))(*(_QWORD *)v129 + 248LL))(
                        v129,
                        v204,
                        &v231);
                      v130 = v231;
                      v241 = 1;
                      v240 = operator new(0x10u, v208, "Sql\\Ntdbms\\msql\\ddl\\tabcreat.cpp", 1288, 3u);
                      *v240 = v130;
                      v240[2] = v70;
                      v240[3] = v70;
                      v240[1] = 13088;
                      v239 = 0;
                      v242 = 0;
                      *(_QWORD *)&v305 = &v239;
                      v306 |= 2u;
                      v131 = v232;
                      if ( v232 )
                      {
                        v237 = 1;
                        v236 = operator new(0x10u, v208, "Sql\\Ntdbms\\msql\\ddl\\XmlCompressionOption.cpp", 534, 3u);
                        *(_BYTE *)v236 = v131;
                        v236[2] = v70;
                        v236[3] = v70;
                        v236[1] = 13088;
                        v235 = 0;
                        v238 = 0;
                        *((_QWORD *)&v305 + 1) = &v235;
                        v306 |= 4u;
                        operator delete[](v236);
                      }
                      v133 = (*(unsigned int (__fastcall **)(struct IMEDIndex *))(*(_QWORD *)v129 + 8LL))(v129) == 1
                          && (SMD::FHasNciOnCci(v216)
                           || ((*(_BYTE *)(qword_102ECFB00 + 48500) & 1) != 0
                            || !*(_DWORD *)(qword_102ECFB00 + 14504) && *(_BYTE *)(GetXdbServerGlobals(v132) + 12004)
                            || *(_BYTE *)(GetXdbServerGlobals(v132) + 12004))
                           && (*(_BYTE *)(GetXdbServerGlobals(v132) + 12004)
                            || *((_BYTE *)qword_102EF3550 + 717)
                            || (*((_BYTE *)qword_102ECFB10 + 1431) & 0x40) != 0))
                          || SMD::FHasOriginalLocator(v129, v204);
                      if ( v127 >= *(_DWORD *)(v126 + 28) )
                        v134 = 0;
                      else
                        v134 = *(struct IMEDIndex **)(v128 + *(_QWORD *)(v126 + 40));
                      CIndexDDL::CreateRowsets((CIndexDDL *)v303, v134, v70);
                      if ( v133 )
                        CIndexDDL::CheckAndAddOriginalLocatorColumn((CIndexDDL *)v303, v129, v70);
                      v305 = 0;
                      operator delete[](v240);
                      ++v127;
                      v128 += 8;
                    }
                    while ( v127 < v120 );
                  }
                }
                v205 = v70;
                v135 = v197;
                v206 = v197;
                if ( *(_DWORD *)(v126 + 28) )
                  v136 = **(struct IMEDIndex ***)(v126 + 40);
                else
                  v136 = 0;
                v137 = v207;
                v138 = DDLAgent::CheckPartitionEmpty(v304, v136, v70, 1, v207);
                v139 = DDLAgent::CheckPartitionEmpty(v304, v136, v197, 1, v137);
                v140 = v139;
                if ( v138 && (v141 = v70, v139) )
                {
LABEL_240:
                  v143 = a1;
                }
                else
                {
                  v142 = 0;
                  v291 = 0;
                  v292 = 0;
                  v293 = 0;
                  v294 = 0;
                  v295 = 0;
                  v286 = 0;
                  v287 = 0;
                  v288 = 0;
                  v289 = 0;
                  v290 = 0;
                  DDLAgent::GetRowsetAndColumnModCounts(v136, v70, (struct RowsetCountsForQp *)&v291, 0, 0, 0);
                  DDLAgent::GetRowsetAndColumnModCounts(v136, v197, (struct RowsetCountsForQp *)&v286, 0, 0, 0);
                  v143 = a1;
                  if ( !*(_BYTE *)(a1 + 2220) )
                  {
                    if ( v196 )
                    {
                      if ( v138 || v140 )
                        v142 = 1;
                    }
                    else
                    {
                      v142 = v138;
                    }
                  }
                  if ( !v142 )
                  {
                    v144 = (*(unsigned int (__fastcall **)(struct IMEDIndex *))(*(_QWORD *)v136 + 136LL))(v136);
                    v145 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset;
                    v146 = *(_QWORD *)(v145 + 256);
                    if ( !v146 )
                    {
                      SystemThread::MakeMiniSOSThread(0);
                      v146 = *(_QWORD *)(v145 + 256);
                    }
                    v147 = 4 * v144;
                    if ( !is_mul_ok(v144, 4u) )
                      v147 = -1;
                    v149 = operator new[](
                             v147,
                             *(struct IMemObj **)(v146 + 1000),
                             "Sql\\Ntdbms\\msql\\ddl\\prtddl.cpp",
                             2071,
                             3u);
                    v250 = v149;
                    v243 = v149;
                    v150 = 1;
                    if ( (_DWORD)v144 )
                    {
                      _mm_lfence();
                      do
                      {
                        v151 = (*(__int64 (__fastcall **)(struct IMEDIndex *, _QWORD))(*(_QWORD *)v136 + 144LL))(
                                 v136,
                                 v150);
                        v152 = (*(__int64 (__fastcall **)(struct IMEDIndex *, _QWORD))(*(_QWORD *)v136 + 64LL))(
                                 v136,
                                 v151);
                        v153 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v152 + 16LL))(v152);
                        v148 = v150 - 1;
                        *((_DWORD *)v149 + v148) = v153;
                        ++v150;
                      }
                      while ( v150 <= (unsigned int)v144 );
                    }
                    v154 = 0;
                    v155 = 0;
                    v156 = v198;
                    if ( v198 )
                    {
                      v157 = 0;
                      do
                      {
                        if ( v155 >= *(_DWORD *)(v126 + 28) )
                        {
                          v148 = 0;
                        }
                        else
                        {
                          v148 = *(_QWORD *)(v157 + *(_QWORD *)(v126 + 40));
                          v156 = v198;
                        }
                        if ( v148 )
                        {
                          v266 = 0;
                          v268 = 0;
                          v269 = 0;
                          v271 = 1;
                          v270 = -1;
                          v267 = -2;
                          (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v148 + 40LL))(v148, &v266);
                          if ( (v266 & 0x200000) != 0 )
                          {
                            v154 = 1;
                            break;
                          }
                          v156 = v198;
                        }
                        ++v155;
                        v157 += 8;
                      }
                      while ( v155 < v156 );
                    }
                    if ( v196 )
                    {
                      if ( *((__int64 *)&v292 + 1) <= *((__int64 *)&v287 + 1)
                        || *(_BYTE *)(GetXdbServerGlobals(v148) + 12004) )
                      {
                        v206 = v197;
                        v141 = v70;
                      }
                      else
                      {
                        v206 = v70;
                        v141 = v197;
                      }
                      v205 = v141;
                      if ( v154 && !*(_BYTE *)(GetXdbServerGlobals(v148) + 12004) )
                      {
                        LODWORD(v188) = *((_DWORD *)v233 + 2);
                        ex_raise(353, 44, 15, 1, v188, *v233);
                      }
                    }
                    else
                    {
                      v141 = v70;
                      if ( v154 && !*(_BYTE *)(GetXdbServerGlobals(v148) + 12004) )
                      {
                        v158 = 46;
                        if ( !*(_BYTE *)(a1 + 2220) )
                          v158 = 45;
                        LODWORD(v188) = *((_DWORD *)v233 + 2);
                        ex_raise(353, v158, 15, 1, v188, *v233);
                        v141 = v70;
                      }
                    }
                    v159 = *(_BYTE *)(a1 + 2220) == 0;
                    v160 = *(_QWORD *)(v209 + 56);
                    v274[0] = &CRelOpSrcRepartition::`vftable';
                    v274[1] = v160;
                    v274[2] = v216;
                    v274[3] = v315;
                    v274[4] = v201;
                    v275 = v144;
                    v276 = v250;
                    v277 = 1;
                    v278 = &v205;
                    v279 = v206;
                    v280 = v159;
                    v244 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                   + SystemThread_TlsIndex)
                                                 + SystemThread_TlsOffset)
                                     + 128LL);
                    v161 = *(_DWORD *)(v244 + 76);
                    v245 = (v161 & 0x2000) != 0;
                    *(_DWORD *)(v244 + 76) = v161 | 0x2000;
                    v162 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                   + SystemThread_TlsIndex)
                                                 + SystemThread_TlsOffset)
                                     + 128LL);
                    v283 = v162;
                    LODWORD(v160) = *(_DWORD *)(v162 + 76);
                    v163 = (v160 & 0x100000) != 0;
                    v284 = v163;
                    *(_DWORD *)(v162 + 76) = v160 | 0x100000;
                    v227 = &CExecDMLInternal::`vftable';
                    v228 = 0;
                    v229 = 1;
                    *(_QWORD *)&v228 = v274;
                    v246 = 8175;
                    v164 = (CSQLStrings *)operator new(0x570u, v208, "Sql\\Ntdbms\\msql\\ddl\\cnstcrt.cpp", 8175, 3u);
                    v281 = v164;
                    if ( v164 )
                      v166 = CSQLStrings::CSQLStrings(v164, 0, 0, 0, (struct ICallerParse *)&v227, 0, 0, 0, 0, 0, 1, 0);
                    else
                      v166 = 0;
                    *((_QWORD *)&v228 + 1) = v166;
                    *((_DWORD *)v166 + 144) |= 0x400u;
                    v167 = *(_QWORD *)(*((_QWORD *)&v228 + 1) + 72LL);
                    if ( !v167 )
                    {
                      v168 = *(_QWORD *)(*((_QWORD *)&v228 + 1) + 416LL);
                      if ( v168 )
                        v167 = *(_QWORD *)(v168 + 88);
                      else
                        v167 = 0;
                    }
                    LOBYTE(v165) = 2;
                    CCache::EventPlanNotCached(v167, 36, v165);
                    if ( (*(unsigned int (__fastcall **)(struct IMEDRelation *))(*(_QWORD *)v216 + 696LL))(v216) )
                      *(_DWORD *)(*((_QWORD *)&v228 + 1) + 580LL) |= 8u;
                    CExecDMLInternal::Execute((CExecDMLInternal *)&v227, v213);
                    v227 = &CExecDMLInternal::`vftable';
                    if ( *((_QWORD *)&v228 + 1) )
                      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)&v228 + 1) + 136LL))(
                        *((_QWORD *)&v228 + 1),
                        1);
                    v169 = *(_DWORD *)(v162 + 76) & 0xFFEFFFFF;
                    if ( v163 )
                      v169 = *(_DWORD *)(v162 + 76) | 0x100000;
                    *(_DWORD *)(v162 + 76) = v169;
                    v170 = *(_DWORD *)(v244 + 76) & 0xFFFFDFFF;
                    if ( v245 )
                      v170 = *(_DWORD *)(v244 + 76) | 0x2000;
                    *(_DWORD *)(v244 + 76) = v170;
                    operator delete[](v243);
                    v135 = v197;
                    goto LABEL_240;
                  }
                  v141 = v70;
                  v135 = v197;
                  if ( v196 && *((_QWORD *)&v292 + 1) != *((_QWORD *)&v287 + 1) && v140 )
                    v141 = v197;
                }
                if ( *(_BYTE *)(v143 + 2220) )
                {
                  v120 = 0;
                }
                else
                {
                  v171 = v135;
                  if ( v141 == v135 )
                    v171 = v70;
                  if ( v171 == v141 )
                  {
                    v120 = 0;
                  }
                  else
                  {
                    AutoLockedHoBtAccess::AutoLockedHoBtAccess((AutoLockedHoBtAccess *)v297);
                    (*(void (__fastcall **)(struct IMEDIndex *, _QWORD, __int64 *, _BYTE *))(*(_QWORD *)v136 + 272LL))(
                      v136,
                      v141,
                      &v217,
                      v203);
                    v120 = 0;
                    LODWORD(v189) = 0;
                    LOBYTE(v172) = 1;
                    AutoLockedHoBtAccess::Init(v297, v304, v217, v172, 0, v189, 1, 0, 0);
                    ModCounterBeforeDrop = AutoLockedHoBtAccess::GetModCounterBeforeDrop((AutoLockedHoBtAccess *)v297);
                    AutoLockedHoBtAccess::Release((AutoLockedHoBtAccess *)v297);
                    AutoLockedHoBtAccess::AutoLockedHoBtAccess((AutoLockedHoBtAccess *)v296);
                    (*(void (__fastcall **)(struct IMEDIndex *, _QWORD, __int64 *, _BYTE *))(*(_QWORD *)v136 + 272LL))(
                      v136,
                      v171,
                      &v217,
                      v203);
                    LODWORD(v191) = 0;
                    LOBYTE(v174) = 1;
                    AutoLockedHoBtAccess::Init(v296, v304, v217, v174, 0, v191, 1, 0, 0);
                    AutoLockedHoBtAccess::BumpAllColumnMods((AutoLockedHoBtAccess *)v296, ModCounterBeforeDrop);
                    AutoLockedHoBtAccess::Release((AutoLockedHoBtAccess *)v296);
                    AutoLockedHoBtAccess::~AutoLockedHoBtAccess((AutoLockedHoBtAccess *)v296);
                    AutoLockedHoBtAccess::~AutoLockedHoBtAccess((AutoLockedHoBtAccess *)v297);
                  }
                  v175 = 0;
                  if ( v198 )
                  {
                    v176 = 0;
                    do
                    {
                      if ( v175 >= *(_DWORD *)(v126 + 28) )
                        v177 = 0;
                      else
                        v177 = *(struct IMEDIndex **)(v176 + *(_QWORD *)(v126 + 40));
                      CIndexDDL::DropRowset((CIndexDDL *)v303, v177, v141, 0);
                      ++v175;
                      v176 += 8;
                    }
                    while ( v175 < v198 );
                  }
                }
                v124 = v210 + 1;
                v210 = v124;
                v125 = ++v234;
                if ( v124 < v215 )
                {
                  v123 = v219;
                  continue;
                }
                break;
              }
              v61 = v208;
              v92 = v230;
              v104 = v207;
LABEL_263:
              CTDynArray<CScalarStatsInfo *,CFnI_Default<CScalarStatsInfo *>,CFnD_Refc<CScalarStatsInfo>,CMemObjAlloc<0>>::~CTDynArray<CScalarStatsInfo *,CFnI_Default<CScalarStatsInfo *>,CFnD_Refc<CScalarStatsInfo>,CMemObjAlloc<0>>(&v218);
              CIndexDDL::~CIndexDDL((CIndexDDL *)v303);
              v104 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v92 + 56LL))(v92, v104);
              v207 = v104;
              if ( !v104 )
              {
                v7 = a1;
                goto LABEL_265;
              }
              goto LABEL_130;
            }
            v260 = 0;
            v262 = 0;
            v263 = 0;
            v265 = 1;
            v264 = -1;
            v261 = -2;
            (*(void (__fastcall **)(struct IMEDIndex *, __int64 *))(*(_QWORD *)v111 + 40LL))(v111, &v260);
            if ( (v260 & 0x2000) == 0 && (v260 & 0x1000) == 0 )
              AddIndexToMatrix((struct DRgPDRgPimidx *)&v218, v111);
          }
        }
      }
    }
  }
LABEL_266:
  if ( ((unsigned __int8)qword_102EDC9FC & 0x10) != 0
    || CommonGlobalState::m_ProfilerTraceEnabled
    && (*(_BYTE *)(qword_102ECFB00 + 80) & 0x10) != 0
    && (v178 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL)) != 0
    && (v179 = *(_DWORD **)(v178 + 48)) != 0
    && !*v179 )
  {
    v180 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v202 + 16LL))(v202);
    LODWORD(v193) = 0;
    CTraceDDL::TraceDDL(
      164,
      v213,
      v180,
      v199,
      18000,
      *(_DWORD *)(v7 + 2216),
      *(const wchar_t **)(v7 + 2208),
      v193,
      0,
      0);
  }
  v181 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v209 + 56) + 16LL))(*(_QWORD *)(v209 + 56));
  v182 = g_dbtableFactory[4](v211);
  (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v181 + 272LL))(
    v181,
    *(unsigned __int16 *)(v182 + 40),
    *(_QWORD *)(v182 + 4624));
  (*(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64, int, int))(*(_QWORD *)qword_102F1B290 + 64LL))(
    qword_102F1B290,
    v211,
    v199,
    2,
    66316,
    1);
  v21 = 0;
  CPreAlterPrtFunc::~CPreAlterPrtFunc((CPreAlterPrtFunc *)v315);
  if ( HIDWORD(v212) )
  {
    v183 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v184 = *(_QWORD *)(v183 + 256);
    if ( !v184 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v184 = *(_QWORD *)(v183 + 256);
    }
    SOS_Task::SetDeadlockPriority(*(_QWORD *)(v184 + 600), (unsigned int)v212);
  }
LABEL_277:
  CExecutionCollection::~CExecutionCollection((CExecutionCollection *)v298);
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
