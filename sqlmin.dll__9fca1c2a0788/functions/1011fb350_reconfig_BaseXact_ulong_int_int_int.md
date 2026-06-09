# reconfig(BaseXact *,ulong,int,int,int)

- ea: `0x1011fb350`
- end: `0x1011fd26c`
- name: `?reconfig@@YAXPEAVBaseXact@@KHHH@Z`
- size: `7964`
- prototype: `void __fastcall(struct BaseXact *, unsigned int, int, int, int)`
- caller_count: `2`
- callee_count: `37`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x100845180`
- `0x101b939f0`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x100402000`
- `0x100402200`
- `0x1004022e0`
- `0x1004025c0`
- `0x100402920`
- `0x100415c30`
- `0x10041e3e0`
- `0x10041e8f0`
- `0x10042f110`
- `0x10047aa10`
- `0x10047bc10`
- `0x100553e20`
- `0x1007b3be0`
- `0x100844c30`
- `0x100848a30`
- `0x100a52830`
- `0x1011538d0`
- `0x1011fb170`
- `0x1011fb230`
- `0x1011fb350`
- `0x1011fd280`
- `0x1011fd320`
- `0x1011fdbc0`
- `0x1011fde60`
- `0x1011fea10`
- `0x1012014c0`
- `0x101201620`
- `0x101201ca0`
- `0x1017a0350`
- `0x101b900c0`
- `0x10221d370`
- `0x1022211b0`
- `0x10239ade0`
- `0x1023aea90`
- `0x1023aee60`

## import_xrefs

- `sqlTsEs!?CopyOut@CXVariant@@QEBAKPEAEPEBVCTypeInfo@@H@Z` at `0x1011fb8a5`
- `sqlTsEs!?CopyOut@CXVariant@@QEBAKPEAEPEBVCTypeInfo@@H@Z` at `0x1011fb8a5`
- `sqldk!?IsWow64@SOS_OS@@SAHXZ` at `0x1011fb44c`
- `sqldk!?IsWow64@SOS_OS@@SAHXZ` at `0x1011fb44c`
- `sqldk!?UpdateSchedulerIdealWorkerLimit@SOS_OS@@SAXG@Z` at `0x1011fc531`
- `sqldk!?UpdateSchedulerIdealWorkerLimit@SOS_OS@@SAXG@Z` at `0x1011fc531`
- `sqldk!?IsHotAddCpuSupported@SOS_OS@@SAHPEAW4HOT_ADD_CPU_UNSUPPORTED_REASON@1@@Z` at `0x1011fcab5`
- `sqldk!?IsHotAddCpuSupported@SOS_OS@@SAHPEAW4HOT_ADD_CPU_UNSUPPORTED_REASON@1@@Z` at `0x1011fcab5`
- `sqldk!?UpdateProcessorStaticInfo@SOS_OS@@SAXXZ` at `0x1011fcbc6`
- `sqldk!?UpdateProcessorStaticInfo@SOS_OS@@SAXXZ` at `0x1011fcbc6`
- `sqldk!?GetCPUIdFromAffinity@GroupAffinity@@QEBAIXZ` at `0x1011fcf9b`
- `sqldk!?GetCPUIdFromAffinity@GroupAffinity@@QEBAIXZ` at `0x1011fcf9b`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc47a`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc49b`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc4b7`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc4d6`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc4f2`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc50e`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc537`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc558`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc576`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc597`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc5b8`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc5d9`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc5fa`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc61b`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc63c`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc65c`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc67c`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc69c`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc6bc`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc6e2`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc71a`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1011fc745`
- `sqldk!?SafeCopy@SystemAffinity@@QEBA?AV1@XZ` at `0x1011fcbf4`
- `sqldk!?SafeCopy@SystemAffinity@@QEBA?AV1@XZ` at `0x1011fcbf4`
- `sqldk!?sm_CPUInfo@SOS_PublicGlobals@@2PEAVSOS_CPUInfo@@EA` at `0x1011fcfa7`
- `sqldk!?SOS_OS_AffinityType@@3W4OS_AFFINITY@SOS_OS@@A` at `0x1011fcc6a`
- `sqldk!?sm_osSystemAffinity@SOS_PublicGlobals@@2VSystemAffinity@@A` at `0x1011fca73`
- `sqldk!?sm_osSystemAffinity@SOS_PublicGlobals@@2VSystemAffinity@@A` at `0x1011fcd23`
- `sqldk!?sm_AffinityMask@SOS_PublicGlobals@@2VSystemAffinity@@A` at `0x1011fcbed`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1011fb75f`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1011fc88f`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1011fc8ee`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x1011fb7e5`
- `sqldk!?SOS_OS_NumDACCount@@3KA` at `0x1011fba06`
- `sqldk!?Instance@OsNumaConfig@@SAPEAV1@XZ` at `0x1011fca42`
- `sqldk!?Instance@OsNumaConfig@@SAPEAV1@XZ` at `0x1011fca42`
- `sqldk!??9SystemAffinity@@QEBAHAEBV0@@Z` at `0x1011fcdeb`
- `sqldk!??9SystemAffinity@@QEBAHAEBV0@@Z` at `0x1011fcdeb`
- `sqldk!??_5SystemAffinity@@QEAAAEAV0@AEBVGroupAffinity@@@Z` at `0x1011fce5a`
- `sqldk!??_5SystemAffinity@@QEAAAEAV0@AEBVGroupAffinity@@@Z` at `0x1011fce5a`
- `sqldk!??ISystemAffinity@@QEBA?AV0@AEBV0@@Z` at `0x1011fca91`
- `sqldk!??ISystemAffinity@@QEBA?AV0@AEBV0@@Z` at `0x1011fcddb`
- `sqldk!??ISystemAffinity@@QEBA?AV0@AEBV0@@Z` at `0x1011fca91`
- `sqldk!??ISystemAffinity@@QEBA?AV0@AEBV0@@Z` at `0x1011fcddb`
- `sqldk!??SSystemAffinity@@QEBA?AV0@XZ` at `0x1011fca7a`
- `sqldk!??SSystemAffinity@@QEBA?AV0@XZ` at `0x1011fca7a`
- `sqldk!?IsEmpty@SystemAffinity@@QEBAHXZ` at `0x1011fca9e`
- `sqldk!?IsEmpty@SystemAffinity@@QEBAHXZ` at `0x1011fca9e`
- `sqldk!??0SystemAffinityEnum@@QEAA@PEBVSystemAffinity@@@Z` at `0x1011fce13`
- `sqldk!??0SystemAffinityEnum@@QEAA@PEBVSystemAffinity@@@Z` at `0x1011fcf69`
- `sqldk!??0SystemAffinityEnum@@QEAA@PEBVSystemAffinity@@@Z` at `0x1011fce13`
- `sqldk!??0SystemAffinityEnum@@QEAA@PEBVSystemAffinity@@@Z` at `0x1011fcf69`
- `sqldk!?MoveNextBitSet@SystemAffinityEnum@@QEAAHXZ` at `0x1011fce23`
- `sqldk!?MoveNextBitSet@SystemAffinityEnum@@QEAAHXZ` at `0x1011fce69`
- `sqldk!?MoveNextBitSet@SystemAffinityEnum@@QEAAHXZ` at `0x1011fcf76`
- `sqldk!?MoveNextBitSet@SystemAffinityEnum@@QEAAHXZ` at `0x1011fcfcd`
- `sqldk!?MoveNextBitSet@SystemAffinityEnum@@QEAAHXZ` at `0x1011fce23`
- `sqldk!?MoveNextBitSet@SystemAffinityEnum@@QEAAHXZ` at `0x1011fce69`
- `sqldk!?MoveNextBitSet@SystemAffinityEnum@@QEAAHXZ` at `0x1011fcf76`
- `sqldk!?MoveNextBitSet@SystemAffinityEnum@@QEAAHXZ` at `0x1011fcfcd`
- `sqldk!?GetCurrentPosition@SystemAffinityEnum@@QEBA?AVGroupAffinity@@XZ` at `0x1011fce46`
- `sqldk!?GetCurrentPosition@SystemAffinityEnum@@QEBA?AVGroupAffinity@@XZ` at `0x1011fcf8e`
- `sqldk!?GetCurrentPosition@SystemAffinityEnum@@QEBA?AVGroupAffinity@@XZ` at `0x1011fce46`
- `sqldk!?GetCurrentPosition@SystemAffinityEnum@@QEBA?AVGroupAffinity@@XZ` at `0x1011fcf8e`
- `sqldk!?GetCPUCount@SystemAffinity@@QEBAIXZ` at `0x1011fcbb3`
- `sqldk!?GetCPUCount@SystemAffinity@@QEBAIXZ` at `0x1011fcd15`
- `sqldk!?GetCPUCount@SystemAffinity@@QEBAIXZ` at `0x1011fcdbc`
- `sqldk!?GetCPUCount@SystemAffinity@@QEBAIXZ` at `0x1011fcbb3`
- `sqldk!?GetCPUCount@SystemAffinity@@QEBAIXZ` at `0x1011fcd15`
- `sqldk!?GetCPUCount@SystemAffinity@@QEBAIXZ` at `0x1011fcdbc`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x1011fb622`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x1011fb622`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x1011fd053`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x1011fd053`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x1011fca3c`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x1011fca64`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x1011fcbd3`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x1011fcbe0`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x1011fce03`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x1011fca3c`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x1011fca64`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x1011fcbd3`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x1011fcbe0`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x1011fce03`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1011fb56a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1011fcb05`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1011fb56a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1011fcb05`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1011fb429`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1011fb9bf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1011fc32f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1011fc433`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1011fc93a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1011fcf46`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1011fb429`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1011fb9bf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1011fc32f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1011fc433`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1011fc93a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1011fcf46`
- `sqldk!SystemThread_TlsIndex` at `0x1011fb79f`
- `sqldk!SystemThread_TlsIndex` at `0x1011fc84f`
- `sqldk!SystemThread_TlsOffset` at `0x1011fb7a8`
- `sqldk!SystemThread_TlsOffset` at `0x1011fc858`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1011fb7c1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1011fc873`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1011fb7c1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1011fc873`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1011fb680`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1011fb745`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1011fb680`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1011fb745`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1011fb68c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1011fb751`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1011fb68c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1011fb751`
- `sqllang!?SetupDefaultTrace@CTraceController@@SAXH@Z` at `0x1011fbf4c`
- `sqllang!?SetupDefaultTrace@CTraceController@@SAXH@Z` at `0x1011fbf4c`
- `sqllang!?ChangeDacConfiguration@@YAXW4EDacStatus@@@Z` at `0x1011fc75d`
- `sqllang!?ChangeDacConfiguration@@YAXW4EDacStatus@@@Z` at `0x1011fc75d`
- `sqllang!?CheckPermRuleAuditOnly@ISECManager@@SAXW4ESECSecuredOperation@@PEAVIMemObj@@PEAVIMetadataAccess@@KKHW4EObjType@@PEAUAuditEventInfo@@_JU_GUID@@PEAVBatchAuditAdditionalInfo@@HPEAVBaseXact@@K@Z` at `0x1011fbb47`
- `sqllang!?CheckPermRuleAuditOnly@ISECManager@@SAXW4ESECSecuredOperation@@PEAVIMemObj@@PEAVIMetadataAccess@@KKHW4EObjType@@PEAUAuditEventInfo@@_JU_GUID@@PEAVBatchAuditAdditionalInfo@@HPEAVBaseXact@@K@Z` at `0x1011fbb47`

## string_xrefs

- `0x1011fd05d`: `EnqueueTask on SendUpdateExtensibilityRgToManagementService failed! call it inline.`
- `0x1011fd073`: `EnqueueTask on SendUpdateExtensibilityRgToManagementService succeeded.`
- `0x1011fb7d4`: `sql\ntdbms\storeng\common\sereconf.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall reconfig(struct BaseXact *a1, int a2, int a3, int a4, int a5)
{
  struct BaseXact *v5; // r12
  char v6; // di
  int v7; // esi
  unsigned __int16 MasterDbId; // bx
  const wchar_t *v9; // rdi
  __int64 v10; // rbx
  int v11; // edi
  unsigned int v12; // ebx
  int Lock; // eax
  __int64 v14; // rcx
  int v15; // eax
  const void *v16; // rdx
  struct SysConfigPagePtr *ServerConfiguration; // rax
  __int64 v18; // rcx
  _OWORD *v19; // rcx
  int *v20; // rax
  __int64 v21; // rdx
  unsigned __int16 v22; // ax
  __int64 v23; // rax
  FCB *FCB; // rax
  __int64 v25; // rbx
  __int64 v26; // rcx
  __int64 v27; // r13
  __int64 v28; // rsi
  bool v29; // r15
  unsigned __int64 v30; // r14
  int v31; // r13d
  int v32; // r12d
  int v33; // ebx
  int v34; // ebx
  int v35; // ebx
  unsigned int v36; // edx
  unsigned __int16 v37; // bx
  __int16 v38; // bx
  int v39; // edi
  unsigned int v40; // ebx
  unsigned __int16 v41; // ax
  int v42; // ebx
  int v43; // edi
  unsigned __int8 v44; // bl
  int v45; // ebx
  int v46; // edi
  unsigned int v47; // r9d
  int v48; // edi
  __int16 v49; // bx
  int v50; // ebx
  int v51; // edi
  unsigned __int16 v52; // bx
  int v53; // edi
  int v54; // ebx
  int v55; // ebx
  unsigned __int16 v56; // bx
  unsigned __int16 v57; // bx
  unsigned __int16 v58; // bx
  unsigned __int16 v59; // bx
  unsigned __int8 v60; // bl
  __int16 v61; // bx
  int v62; // edi
  unsigned __int8 v63; // bl
  unsigned __int8 v64; // bl
  unsigned __int8 v65; // bl
  unsigned __int8 v66; // bl
  int v67; // ebx
  int v68; // edi
  unsigned __int8 v69; // bl
  unsigned __int8 v70; // bl
  unsigned __int8 v71; // bl
  unsigned __int8 v72; // bl
  int v73; // ebx
  int v74; // ebx
  int v75; // ebx
  int v76; // ebx
  int v77; // ebx
  unsigned __int8 v78; // bl
  unsigned __int8 v79; // bl
  unsigned __int8 v80; // bl
  unsigned __int8 v81; // bl
  unsigned __int8 v82; // bl
  __int64 v83; // rcx
  __int64 v84; // rbx
  __int64 v85; // rcx
  __int64 v86; // rax
  unsigned __int16 v87; // cx
  int v88; // eax
  char v89; // r15
  __int64 v90; // rax
  __int64 v91; // rax
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // rax
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rax
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 v104; // rax
  __int64 v105; // rax
  __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // rax
  __int64 v109; // rax
  unsigned int v110; // edx
  __int64 v111; // rcx
  __int64 v112; // rbx
  __int64 v113; // rcx
  __int64 v114; // rax
  unsigned __int16 v115; // si
  unsigned __int16 v116; // r14
  __int64 v117; // rbx
  __int64 v118; // rax
  struct IMemObj *v119; // rbx
  unsigned __int16 v120; // ax
  __int64 v121; // rax
  unsigned __int16 v122; // ax
  __int64 v123; // rax
  __int64 v124; // rdi
  struct SysConfigPagePtr *v125; // rbx
  struct XDES *v126; // rax
  __int64 v127; // rcx
  __int16 v128; // r8
  int v129; // eax
  int v130; // edx
  struct Page *v131; // rcx
  __int64 v132; // rax
  __int64 v133; // rax
  int IsEmpty; // eax
  int IsHotAddCpuSupported; // edi
  int v136; // ebx
  struct SysConfigPagePtr *v137; // rax
  const struct SystemAffinity *v138; // rbx
  __int128 v139; // xmm0
  __int128 v140; // xmm1
  __int128 v141; // xmm2
  __int128 v142; // xmm3
  __int128 v143; // xmm4
  __int128 v144; // xmm5
  __int128 v145; // xmm6
  __int128 v146; // xmm7
  __int64 v147; // rax
  unsigned int i; // ebx
  unsigned int CPUIdFromAffinity; // eax
  wchar_t *v150; // rbx
  int v151; // eax
  _QWORD *v152; // rbx
  bool v153; // zf
  _QWORD *v154; // rcx
  signed __int32 v155[8]; // [rsp+0h] [rbp-100h] BYREF
  __int64 v156; // [rsp+20h] [rbp-E0h]
  bool v157; // [rsp+70h] [rbp-90h] BYREF
  char v158; // [rsp+71h] [rbp-8Fh]
  int v159; // [rsp+74h] [rbp-8Ch] BYREF
  bool v160; // [rsp+78h] [rbp-88h]
  int v161; // [rsp+7Ch] [rbp-84h] BYREF
  int v162; // [rsp+80h] [rbp-80h]
  int v163; // [rsp+84h] [rbp-7Ch]
  int v164; // [rsp+88h] [rbp-78h]
  int v165; // [rsp+8Ch] [rbp-74h]
  int v166; // [rsp+90h] [rbp-70h] BYREF
  int v167; // [rsp+94h] [rbp-6Ch]
  int v168; // [rsp+98h] [rbp-68h] BYREF
  _QWORD *v169; // [rsp+A0h] [rbp-60h] BYREF
  int v170; // [rsp+A8h] [rbp-58h]
  _QWORD v171[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v172; // [rsp+C0h] [rbp-40h]
  int *v173; // [rsp+D0h] [rbp-30h] BYREF
  struct BaseXact *v174; // [rsp+D8h] [rbp-28h]
  __int64 *v175; // [rsp+E0h] [rbp-20h]
  int v176; // [rsp+E8h] [rbp-18h]
  bool *v177; // [rsp+F0h] [rbp-10h] BYREF
  bool v178; // [rsp+F8h] [rbp-8h]
  int v179; // [rsp+FCh] [rbp-4h]
  char v180; // [rsp+100h] [rbp+0h]
  int v181; // [rsp+108h] [rbp+8h] BYREF
  __int64 v182; // [rsp+110h] [rbp+10h]
  __int64 v183; // [rsp+118h] [rbp+18h]
  __int64 v184; // [rsp+120h] [rbp+20h]
  __int64 v185; // [rsp+128h] [rbp+28h]
  __int64 v186; // [rsp+130h] [rbp+30h]
  GUID v187; // [rsp+140h] [rbp+40h] BYREF
  __int128 v188; // [rsp+150h] [rbp+50h] BYREF
  char v189; // [rsp+160h] [rbp+60h] BYREF
  char v190; // [rsp+161h] [rbp+61h]
  _BYTE v191[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v192[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v193; // [rsp+1C0h] [rbp+C0h]
  __int128 v194; // [rsp+1D0h] [rbp+D0h]
  __int128 v195; // [rsp+1E0h] [rbp+E0h]
  __int128 v196; // [rsp+1F0h] [rbp+F0h]
  __int128 v197; // [rsp+200h] [rbp+100h]
  __int128 v198; // [rsp+210h] [rbp+110h]
  __int128 v199; // [rsp+220h] [rbp+120h]
  __int128 v200; // [rsp+230h] [rbp+130h]
  __int128 v201; // [rsp+240h] [rbp+140h]
  _BYTE v202[32]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v203; // [rsp+270h] [rbp+170h] BYREF
  __int16 v204; // [rsp+278h] [rbp+178h]
  _OWORD v205[8]; // [rsp+280h] [rbp+180h] BYREF
  int v206; // [rsp+300h] [rbp+200h]
  __int128 v207; // [rsp+308h] [rbp+208h] BYREF
  __int128 v208; // [rsp+318h] [rbp+218h]
  __int128 v209; // [rsp+328h] [rbp+228h]
  __int128 v210; // [rsp+338h] [rbp+238h]
  __int128 v211; // [rsp+348h] [rbp+248h]
  __int128 v212; // [rsp+358h] [rbp+258h]
  __int128 v213; // [rsp+368h] [rbp+268h]
  __int128 v214; // [rsp+378h] [rbp+278h]
  unsigned int v215; // [rsp+388h] [rbp+288h]
  __int64 v216; // [rsp+390h] [rbp+290h]
  __int128 v217; // [rsp+3A0h] [rbp+2A0h] BYREF
  __int128 v218; // [rsp+3B0h] [rbp+2B0h]
  __int128 v219; // [rsp+3C0h] [rbp+2C0h]
  __int128 v220; // [rsp+3D0h] [rbp+2D0h]
  __int128 v221; // [rsp+3E0h] [rbp+2E0h]
  __int128 v222; // [rsp+3F0h] [rbp+2F0h]
  __int128 v223; // [rsp+400h] [rbp+300h]
  __int128 v224; // [rsp+410h] [rbp+310h]
  _BYTE v225[16]; // [rsp+420h] [rbp+320h] BYREF
  _BYTE v226[16]; // [rsp+430h] [rbp+330h] BYREF
  _OWORD v227[8]; // [rsp+440h] [rbp+340h] BYREF
  _OWORD v228[8]; // [rsp+4C0h] [rbp+3C0h] BYREF
  _OWORD v229[8]; // [rsp+540h] [rbp+440h] BYREF
  _BYTE v230[128]; // [rsp+5C0h] [rbp+4C0h] BYREF
  _BYTE v231[128]; // [rsp+640h] [rbp+540h] BYREF
  _OWORD v232[15]; // [rsp+6C0h] [rbp+5C0h] BYREF
  __int64 v233; // [rsp+7B0h] [rbp+6B0h]
  _BYTE v234[4095]; // [rsp+7C0h] [rbp+6C0h] BYREF
  char v235; // [rsp+17BFh] [rbp+16BFh] BYREF
  struct Page *v236; // [rsp+37C0h] [rbp+36C0h]
  int v237; // [rsp+37C8h] [rbp+36C8h]
  _BYTE v238[4]; // [rsp+37CCh] [rbp+36CCh] BYREF
  int v239; // [rsp+37D0h] [rbp+36D0h]
  int v240; // [rsp+37DCh] [rbp+36DCh]
  int v241; // [rsp+37E0h] [rbp+36E0h]
  int v242; // [rsp+37E8h] [rbp+36E8h]
  int v243; // [rsp+37ECh] [rbp+36ECh]
  int v244; // [rsp+37F4h] [rbp+36F4h]
  unsigned __int8 v245; // [rsp+380Eh] [rbp+370Eh]
  int v246; // [rsp+3810h] [rbp+3710h]
  unsigned int v247; // [rsp+3814h] [rbp+3714h]
  int v248; // [rsp+3818h] [rbp+3718h]
  int v249; // [rsp+382Ch] [rbp+372Ch]
  int v250; // [rsp+3830h] [rbp+3730h]
  int v251; // [rsp+3834h] [rbp+3734h]
  __int16 v252; // [rsp+384Ah] [rbp+374Ah]
  __int16 v253; // [rsp+385Ch] [rbp+375Ch]
  unsigned __int16 v254; // [rsp+385Eh] [rbp+375Eh]
  __int16 v255; // [rsp+3874h] [rbp+3774h]
  unsigned __int16 v256; // [rsp+3878h] [rbp+3778h]
  __int16 v257; // [rsp+3882h] [rbp+3782h]
  __int16 v258; // [rsp+388Ah] [rbp+378Ah]
  int v259; // [rsp+388Ch] [rbp+378Ch]
  unsigned __int8 v260; // [rsp+38ADh] [rbp+37ADh]
  unsigned __int16 v261; // [rsp+38B0h] [rbp+37B0h]
  unsigned __int16 v262; // [rsp+38B2h] [rbp+37B2h]
  unsigned __int16 v263; // [rsp+38B4h] [rbp+37B4h]
  unsigned __int16 v264; // [rsp+38B6h] [rbp+37B6h]
  unsigned __int8 v265; // [rsp+38BDh] [rbp+37BDh]
  unsigned __int8 v266; // [rsp+38C6h] [rbp+37C6h]
  unsigned __int8 v267; // [rsp+38C7h] [rbp+37C7h]
  unsigned __int8 v268; // [rsp+38CCh] [rbp+37CCh]
  int v269; // [rsp+38D0h] [rbp+37D0h]
  int v270; // [rsp+38DCh] [rbp+37DCh]
  int v271; // [rsp+38E0h] [rbp+37E0h]
  int v272; // [rsp+38E4h] [rbp+37E4h]
  int v273; // [rsp+38E8h] [rbp+37E8h]
  int v274; // [rsp+38ECh] [rbp+37ECh]
  int v275; // [rsp+38F0h] [rbp+37F0h]
  int v276; // [rsp+38F4h] [rbp+37F4h]
  int v277; // [rsp+38F8h] [rbp+37F8h]
  int v278[4]; // [rsp+38FCh] [rbp+37FCh] BYREF
  __int128 v279; // [rsp+390Ch] [rbp+380Ch]
  __int128 v280; // [rsp+391Ch] [rbp+381Ch]
  __int128 v281; // [rsp+392Ch] [rbp+382Ch]
  __int128 v282; // [rsp+393Ch] [rbp+383Ch]
  __int128 v283; // [rsp+394Ch] [rbp+384Ch]
  __int128 v284; // [rsp+395Ch] [rbp+385Ch]
  __int128 v285; // [rsp+396Ch] [rbp+386Ch]
  char v286; // [rsp+3D04h] [rbp+3C04h]
  unsigned __int8 v287; // [rsp+3D05h] [rbp+3C05h]
  char v288; // [rsp+3D06h] [rbp+3C06h]
  unsigned __int8 v289; // [rsp+3D07h] [rbp+3C07h]
  unsigned __int8 v290; // [rsp+3D08h] [rbp+3C08h]
  unsigned __int8 v291; // [rsp+3D09h] [rbp+3C09h]
  char v292; // [rsp+3D0Ah] [rbp+3C0Ah]
  unsigned __int8 v293; // [rsp+3D0Bh] [rbp+3C0Bh]
  unsigned __int8 v294; // [rsp+3D0Ch] [rbp+3C0Ch]
  unsigned __int8 v295; // [rsp+3D0Dh] [rbp+3C0Dh]
  unsigned __int8 v296; // [rsp+3D0Eh] [rbp+3C0Eh]
  unsigned __int8 v297; // [rsp+3D0Fh] [rbp+3C0Fh]
  unsigned __int8 v298; // [rsp+3D10h] [rbp+3C10h]
  bool v299; // [rsp+3D11h] [rbp+3C11h]
  char v300; // [rsp+3D12h] [rbp+3C12h]
  char v301; // [rsp+3D13h] [rbp+3C13h]
  _BYTE v302[128]; // [rsp+3D20h] [rbp+3C20h] BYREF
  _BYTE v303[128]; // [rsp+3DA0h] [rbp+3CA0h] BYREF

  v193 = -2;
  v167 = a4;
  v164 = a3;
  v165 = a2;
  v5 = a1;
  v174 = a1;
  v237 = 0;
  v162 = 0;
  v6 = 0;
  v158 = 0;
  v157 = 0;
  v160 = 0;
  LOBYTE(v163) = 0;
  v7 = dword_10317A9FC & 0x81;
  MasterDbId = GetMasterDbId();
  if ( ((unsigned int)IsReplicatedMasterEnabled() || (unsigned int)IsContainedAGEnabledInstance())
    && (unsigned int)IsContainedAGEnabledInstance()
    && IsContainedAgMasterDBId(MasterDbId) )
  {
    ex_raise(58, 74, 16, 2);
  }
  v169 = &SysConfigPagePtr::sm_ConfigurationLock;
  v170 = 0;
  TAutoMutex<SOS_RecursiveMutex,4294967295>::GetAccess(&v169, 4195019);
  if ( !(unsigned int)SOS_OS::IsWow64() && !a5 )
  {
    v9 = (const wchar_t *)&word_10317A7D2;
    if ( !dword_103172568 )
      v9 = &dword_10317998C;
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
    memset_0(v232, 0, 0xF8u);
    v166 = 1;
    v173 = &v166;
    dword_103171DDC = 0;
    v11 = CFilestreamConfiguration::ReadFromRegistry(
            (CFilestreamConfiguration *)&v173,
            v9,
            (unsigned int)v10,
            (struct FILESTREAM_CONFIG *)v232);
    if ( v11 == -2147023286 )
    {
      dword_103171DDC = 96;
      v11 = 0;
    }
    v181 = 4194781;
    v182 = 0;
    v184 = 0;
    v183 = 0;
    v185 = 0;
    v175 = qword_103171C80;
    v12 = 0;
    v176 = 0;
    Lock = SOS_RWLock::GetLock(qword_103171C80, 2, 0xFFFFFFFFLL, &v181);
    if ( !Lock )
    {
      v12 = 2;
      v176 = 2;
LABEL_22:
      *(_OWORD *)&dword_103171CD8 = v232[0];
      *(_OWORD *)((char *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4
                + 47652072) = v232[1];
      *(_OWORD *)((char *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4
                + 47652088) = v232[2];
      *(_OWORD *)((char *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4
                + 47652104) = v232[3];
      *(_OWORD *)((char *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4
                + 47652120) = v232[4];
      *(_OWORD *)((char *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4
                + 47652136) = v232[5];
      *(_OWORD *)((char *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4
                + 47652152) = v232[6];
      *(_OWORD *)((char *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4
                + 47652168) = v232[7];
      *(_OWORD *)((char *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4
                + 47652184) = v232[8];
      *(_OWORD *)((char *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4
                + 47652200) = v232[9];
      *(_OWORD *)((char *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4
                + 47652216) = v232[10];
      *(_OWORD *)((char *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4
                + 47652232) = v232[11];
      *(_OWORD *)((char *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4
                + 47652248) = v232[12];
      *(_OWORD *)((char *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4
                + 47652264) = v232[13];
      *(_OWORD *)((char *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4
                + 47652280) = v232[14];
      *((_QWORD *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4
      + 5956537) = v233;
      if ( v12 )
      {
        SOS_RWLock::ReleaseLock(qword_103171C80, v12);
        v176 = 0;
      }
      CheckHrFailAndExit(v11, "Filestream init");
      v6 = 0;
      goto LABEL_25;
    }
    v15 = Lock - 2;
    if ( v15 )
    {
      if ( v15 != 1 )
      {
        utassert_fail(1u, "FALSE", "sql\\ntdbms\\storeng\\filestrm\\fstrhlpr.cpp", 1816, "Invalid switch value");
        goto LABEL_22;
      }
      LOBYTE(v14) = -44;
    }
    else
    {
      LOBYTE(v14) = -45;
    }
    RaiseExecutionAbortedError(v14);
    goto LABEL_22;
  }
LABEL_25:
  v236 = (struct Page *)((unsigned __int64)&v235 & 0xFFFFFFFFFFFFF000uLL);
  v16 = (const void *)*((_QWORD *)GetServerConfiguration() + 1536);
  if ( v236 )
  {
    if ( v16 )
    {
      memmove(v236, v16, 0x2000u);
      goto LABEL_30;
    }
    memset_0(v236, 0, 0x2000u);
  }
  *_errno() = 22;
  _invalid_parameter_noinfo();
LABEL_30:
  ServerConfiguration = GetServerConfiguration();
  SysConfigPagePtr::CopyConfigOptions<DS_CONFIG,DS_CONFIG>(v18, v238, (char *)ServerConfiguration + 12300);
  if ( v7 )
  {
    v19 = (_OWORD *)((char *)v236 + *((unsigned __int16 *)v236 + 4095) + 312);
    if ( (struct Page *)((char *)v236 + *((unsigned __int16 *)v236 + 4095)) == (struct Page *)-312LL )
    {
      memset_0(v278, 0, 0x400u);
      *_errno() = 22;
      _invalid_parameter_noinfo();
    }
    else
    {
      v20 = v278;
      v21 = 8;
      do
      {
        *(_OWORD *)v20 = *v19;
        *((_OWORD *)v20 + 1) = v19[1];
        *((_OWORD *)v20 + 2) = v19[2];
        *((_OWORD *)v20 + 3) = v19[3];
        *((_OWORD *)v20 + 4) = v19[4];
        *((_OWORD *)v20 + 5) = v19[5];
        *((_OWORD *)v20 + 6) = v19[6];
        v20 += 32;
        *((_OWORD *)v20 - 1) = v19[7];
        v19 += 8;
        --v21;
      }
      while ( v21 );
    }
  }
  v22 = GetMasterDbId();
  v23 = ((__int64 (__fastcall *)(_QWORD))g_dbtableFactory[4])(v22);
  FCB = (FCB *)FileMgr::GetFCB(*(_QWORD *)(*(_QWORD *)(v23 + 4624) + 1696LL), 1, 0);
  FCB::CopyPageToReplicas(FCB, 0xAu, v236);
  v25 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v26 = *(_QWORD *)(v25 + 256);
  if ( !v26 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v26 = *(_QWORD *)(v25 + 256);
  }
  v27 = g_metadataFactory(*(_QWORD *)(v26 + 1000), v5, "sql\\ntdbms\\storeng\\common\\sereconf.cpp", 596);
  *(_QWORD *)&v172 = v27;
  v186 = v27;
  v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 112LL))(v27);
  v29 = byte_10316E91D != 0;
  v161 = 0;
  (**(void (__fastcall ***)(__int64, _QWORD, __int64))v28)(v28, 0, 1);
  v30 = (unsigned __int64)(8LL * *((_QWORD *)qword_10317B628 + 520)) >> 10;
  if ( (*(unsigned __int8 (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 8LL))(v28, &v161) )
  {
    v31 = v164;
    v32 = v163;
    while ( 1 )
    {
      v159 = 0;
      (*(void (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v28 + 16LL))(v28, (unsigned int)v161, v202);
      CTypeInfo::Init((CTypeInfo *)&v189, v202[1]);
      v190 |= 1u;
      CXVariant::CopyOut((CXVariant *)v202, (unsigned __int8 *)&v159, (const struct CTypeInfo *)&v189, 0);
      if ( (unsigned int)v161 > 0x190 )
      {
        if ( (unsigned int)v161 > 0x5E1 )
        {
          if ( (unsigned int)v161 > 0x4000 )
          {
            switch ( v161 )
            {
              case 16386:
              case 16387:
              case 16388:
              case 16390:
              case 16391:
              case 16392:
                goto LABEL_56;
              case 16394:
                v286 = v159;
                break;
              case 16395:
                v79 = v159;
                v157 |= NeedToFlush(v161, v287, v159);
                v287 = v79;
                break;
              case 16396:
                v288 = v159;
                break;
              case 16397:
                v292 = v159;
                break;
              case 16398:
                v80 = v159;
                v157 |= NeedToFlush(v161, v293, v159);
                v293 = v80;
                break;
              case 16399:
                v78 = v159;
                v157 |= NeedToFlush(v161, v295, v159);
                v295 = v78;
                break;
              case 16400:
                v81 = v159;
                v157 |= NeedToFlush(v161, v297, v159);
                v297 = v81;
                break;
              case 16401:
                v82 = v159;
                v157 |= NeedToFlush(v161, v298, v159);
                v298 = v82;
                break;
              default:
                goto LABEL_55;
            }
          }
          else if ( v161 != 0x4000 )
          {
            switch ( v161 )
            {
              case 1517:
                v44 = v159;
                v157 |= NeedToFlush(v161, v245, v159);
                v245 = v44;
                goto LABEL_56;
              case 1519:
                v45 = v159;
                v157 |= NeedToFlush(v161, v246, v159);
                v246 = v45;
                goto LABEL_56;
              case 1520:
              case 1531:
              case 1534:
              case 1536:
              case 1537:
              case 1538:
              case 1541:
              case 1545:
              case 1547:
              case 1555:
              case 1556:
              case 1557:
              case 1563:
              case 1569:
              case 1573:
              case 1575:
              case 1578:
              case 1579:
              case 1581:
              case 1584:
              case 1589:
              case 1602:
                goto LABEL_56;
              case 1532:
                v257 = v159;
                goto LABEL_56;
              case 1535:
                if ( !v29 )
                {
                  v48 = v159;
                  v157 |= NeedToFlush(v161, v278[0], v159);
                  if ( v278[0] != v48 )
                  {
                    v278[0] = v48;
                    v162 = 1;
                  }
                }
                goto LABEL_56;
              case 1539:
                v49 = v159;
                v157 |= NeedToFlush(v161, v258, v159);
                v258 = v49;
                goto LABEL_56;
              case 1540:
                v46 = v159;
                v157 |= NeedToFlush(v161, v259, v159);
                v47 = v46;
                if ( !v46 )
                  v47 = 1024;
                if ( v46 != v259 && v242 && v47 > v242 )
                {
                  _mm_lfence();
                  LODWORD(v156) = v242;
                  ex_callprint(8605, 10, 3);
                  v46 = v159;
                }
                v259 = v46;
                goto LABEL_56;
              case 1543:
                v50 = v159;
                v157 |= NeedToFlush(v161, v241, v159);
                v241 = v50;
                goto LABEL_56;
              case 1544:
                v51 = v159;
                v157 |= NeedToFlush(v161, v243, v159);
                if ( v243 != v51 && (unsigned int)(*((_DWORD *)qword_10317B628 + 26496) - 5) <= 1 && v51 > (int)v30 )
                {
                  ex_callprint(5866, 10, 1, (unsigned int)v51, v30);
                  scierrlog(0x16EAu, (unsigned int)v159, v30);
                  v51 = v159;
                }
                v243 = v51;
                goto LABEL_56;
              case 1546:
                v52 = v159;
                v157 |= NeedToFlush(v161, v254, v159);
                v254 = v52;
                goto LABEL_56;
              case 1549:
                if ( !v29 )
                {
                  v53 = v159;
                  v157 |= NeedToFlush(v161, v278[1], v159);
                  if ( v278[1] != v53 )
                  {
                    v278[1] = v53;
                    v162 = 1;
                  }
                }
                goto LABEL_56;
              case 1550:
                v54 = v159;
                v157 |= NeedToFlush(v161, v239, v159);
                v239 = v54;
                goto LABEL_56;
              case 1551:
                v55 = v159;
                v157 |= NeedToFlush(v161, v244, v159);
                v244 = v55;
                goto LABEL_56;
              case 1562:
                v60 = v159;
                v157 |= NeedToFlush(v161, v260, v159);
                v260 = v60;
                goto LABEL_56;
              case 1564:
                v56 = v159;
                v157 |= NeedToFlush(v161, v261, v159);
                v261 = v56;
                goto LABEL_56;
              case 1565:
                v57 = v159;
                v157 |= NeedToFlush(v161, v262, v159);
                v262 = v57;
                goto LABEL_56;
              case 1566:
                v58 = v159;
                v157 |= NeedToFlush(v161, v263, v159);
                v263 = v58;
                goto LABEL_56;
              case 1567:
                v59 = v159;
                v157 |= NeedToFlush(v161, v264, v159);
                v264 = v59;
                goto LABEL_56;
              case 1568:
                v61 = v255;
                v62 = v159;
                v157 |= NeedToFlush(v161, v255, v159);
                if ( v61 != (_WORD)v62 )
                {
                  CTraceController::SetupDefaultTrace(v62 == 1);
                  LOWORD(v62) = v159;
                }
                v255 = v62;
                goto LABEL_56;
              case 1570:
                v63 = v159;
                v157 |= NeedToFlush(v161, v265, v159);
                v265 = v63;
                goto LABEL_56;
              case 1576:
                v64 = v159;
                v157 |= NeedToFlush(v161, v266, v159);
                v266 = v64;
                goto LABEL_56;
              case 1577:
                v65 = v159;
                v157 |= NeedToFlush(v161, v267, v159);
                v267 = v65;
                goto LABEL_56;
              case 1580:
                v66 = v159;
                v157 |= NeedToFlush(v161, v268, v159);
                v6 = 1;
                v158 = 1;
                v268 = v66;
                break;
              case 1582:
              case 1583:
                v6 = v158;
                if ( v269 != v159 )
                  v160 = 1;
                break;
              case 1585:
                v71 = v159;
                v157 |= NeedToFlush(v161, v289, v159);
                v289 = v71;
                goto LABEL_56;
              case 1586:
                v67 = v290;
                v68 = v159;
                v157 |= NeedToFlush(v161, v290, v159);
                v32 = (unsigned __int8)v32;
                if ( v67 != v68 )
                  v32 = 1;
                v290 = v68;
                goto LABEL_56;
              case 1587:
                v69 = v159;
                v157 |= NeedToFlush(v161, v291, v159);
                v291 = v69;
                goto LABEL_56;
              case 1588:
                v72 = v159;
                v157 |= NeedToFlush(v161, v294, v159);
                v294 = v72;
                goto LABEL_56;
              case 1590:
                v70 = v159;
                v157 |= NeedToFlush(v161, v296, v159);
                v296 = v70;
                goto LABEL_56;
              case 1591:
                v73 = v159;
                v157 |= NeedToFlush(v161, v270, v159);
                v270 = v73;
                goto LABEL_56;
              case 1592:
                v75 = v159;
                v157 |= NeedToFlush(v161, v271, v159);
                v271 = v75;
                goto LABEL_56;
              case 1593:
                v76 = v159;
                v157 |= NeedToFlush(v161, v272, v159);
                v272 = v76;
                goto LABEL_56;
              case 1594:
                v77 = v159;
                v157 |= NeedToFlush(v161, v273, v159);
                v273 = v77;
                goto LABEL_56;
              case 1595:
                v275 = v159;
                goto LABEL_56;
              case 1596:
                v276 = v159;
                goto LABEL_56;
              case 1597:
                v277 = v159;
                goto LABEL_56;
              case 1598:
                v74 = v159;
                v157 |= NeedToFlush(v161, v274, v159);
                v274 = v74;
                goto LABEL_56;
              case 1599:
                v299 = v159 != 0;
                goto LABEL_56;
              case 1600:
                v300 = v159;
                goto LABEL_56;
              case 1601:
                v301 = v159;
                goto LABEL_56;
              default:
                goto LABEL_55;
            }
            goto LABEL_57;
          }
          goto LABEL_56;
        }
        if ( v161 == 1505 )
        {
          v42 = v159;
          v43 = v242;
          v157 |= NeedToFlush(1505, v242, v159);
          if ( v42 && v42 != v43 && v42 < v259 )
          {
            LODWORD(v156) = v42;
            ex_callprint(8605, 10, 2);
            v42 = v159;
          }
          v242 = v42;
          goto LABEL_56;
        }
        if ( (unsigned int)v161 <= 0x21E )
        {
          switch ( v161 )
          {
            case 542:
              v38 = v159;
              v157 |= NeedToFlush(542, v252, v159);
              v252 = v38;
              goto LABEL_56;
            case 503:
              v37 = v159;
              v157 |= NeedToFlush(503, v256, v159);
              v256 = v37;
              goto LABEL_56;
            case 505:
            case 518:
              goto LABEL_56;
          }
          goto LABEL_55;
        }
        if ( v161 == 544 )
        {
          v39 = v159;
          v157 |= NeedToFlush(544, v248, v159);
          if ( v248 != v39 )
          {
            v40 = 1179595331;
            if ( v39 == 1 )
              v40 = 1313813059;
            v187 = GUID_NULL;
            v41 = GetMasterDbId();
            ISECManager::CheckPermRuleAuditOnly(v40, 0, 0, v41, 0, 1, 0, 0, 0, &v187, 0, 0, 0, -1);
            v39 = v159;
          }
          v248 = v39;
          goto LABEL_56;
        }
        if ( v161 != 1126 )
        {
          if ( v161 == 1127 )
          {
            v157 |= NeedToFlush(1127, v250, v159);
            goto LABEL_56;
          }
LABEL_55:
          LODWORD(v156) = v161;
          ex_raise(58, 3, 10, 1, v156);
        }
      }
      else if ( v161 != 400 )
      {
        switch ( v161 )
        {
          case 'e':
          case 'f':
          case 'm':
          case 'r':
          case 's':
          case 't':
          case '|':
            goto LABEL_56;
          case 'g':
            v33 = v159;
            v157 |= NeedToFlush(v161, v240, v159);
            v240 = v33;
            goto LABEL_56;
          case 'j':
            v34 = v159;
            v157 |= NeedToFlush(v161, v251, v159);
            v251 = v34;
            goto LABEL_56;
          case 'k':
            v35 = v159;
            v157 |= NeedToFlush(v161, v249, v159);
            v249 = v35;
            goto LABEL_56;
          case 'u':
            v6 = v158;
            if ( v31 )
              v253 = (unsigned __int8)v159;
            break;
          default:
            goto LABEL_55;
        }
        goto LABEL_57;
      }
LABEL_56:
      v6 = v158;
LABEL_57:
      if ( !(*(unsigned __int8 (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 8LL))(v28, &v161) )
      {
        v163 = v32;
        v5 = v174;
        v27 = v172;
        break;
      }
    }
  }
  SysConfigPagePtr::Nice((SysConfigPagePtr *)v234);
  if ( v240 )
  {
    v36 = dword_103171DE0;
    if ( dword_103171DE0 >= (int)(SOS_OS_NumDACCount + v240 + 50) )
      v36 = SOS_OS_NumDACCount + v240 + 50;
    v247 = v36;
  }
  else
  {
    v247 = 0;
  }
  if ( !(unsigned int)SysConfigPagePtr::FTest((SysConfigPagePtr *)v234, 0) )
    ex_raise(58, 0, 25, 3);
  if ( (v165 & 4) != 0 )
  {
    v89 = 1;
  }
  else
  {
    v83 = GetMasterDbId();
    switch ( (_DWORD)v83 )
    {
      case 0x7FFC:
        v84 = *((_QWORD *)qword_10316ECA0 + 13);
        break;
      case 0x7FFD:
        v84 = *((_QWORD *)qword_10316ECA0 + 14);
        break;
      case 0x7FFF:
        v84 = *((_QWORD *)qword_10316ECA0 + 11);
        break;
      default:
        if ( (unsigned int)v83 <= *((_DWORD *)qword_10316ECA0 + 19) && (_DWORD)v83 )
        {
          _mm_lfence();
          v84 = *(_QWORD *)(*((_QWORD *)qword_10316ECA0 + 5) + 8 * v83 - 8);
        }
        else
        {
          v84 = 0;
        }
        break;
    }
    v85 = GetMasterDbId();
    switch ( (_DWORD)v85 )
    {
      case 0x7FFC:
        v86 = *((_QWORD *)qword_10316ECA0 + 13);
        break;
      case 0x7FFD:
        v86 = *((_QWORD *)qword_10316ECA0 + 14);
        break;
      case 0x7FFF:
        v86 = *((_QWORD *)qword_10316ECA0 + 11);
        break;
      default:
        if ( (unsigned int)v85 <= *((_DWORD *)qword_10316ECA0 + 19) && (_DWORD)v85 )
        {
          _mm_lfence();
          v86 = *(_QWORD *)(*((_QWORD *)qword_10316ECA0 + 5) + 8 * v85 - 8);
        }
        else
        {
          v86 = 0;
        }
        break;
    }
    v87 = word_10317F774;
    if ( *(_BYTE *)(v84 + 2361) )
      v87 = 904;
    if ( v87 <= *(_WORD *)(*(_QWORD *)(v86 + 4624) + 1662LL) && !byte_10316E91D )
    {
      v88 = AffinityAutoConfiguration::ValidateProcessorAffinityNoX(
              (const struct SystemAffinity *)v278,
              (struct SysConfigPagePtr *)v234);
      if ( v88 )
        ex_raise(58, v88, 16, 2);
    }
    v89 = 0;
  }
  if ( v6 && !a5 )
    v268 = CFilestreamFeatureState::ConfigureFilestreamEngineState(qword_103171C80, v268);
  if ( v164 )
  {
    v90 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
    *(_WORD *)(v90 + 144) = v253;
  }
  v91 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  *(_DWORD *)(v91 + 68) = v246;
  v92 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  *(_DWORD *)(v92 + 192) = v259;
  v93 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  *(_DWORD *)(v93 + 20) = v241;
  v94 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  *(_DWORD *)(v94 + 32) = v243;
  v95 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  if ( v256 != *(_WORD *)(v95 + 172) )
  {
    SOS_OS::UpdateSchedulerIdealWorkerLimit(v256);
    v96 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
    *(_WORD *)(v96 + 172) = v256;
  }
  v97 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  *(_WORD *)(v97 + 126) = v252;
  v98 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  *(_WORD *)(v98 + 190) = v258;
  v99 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  *(_WORD *)(v99 + 228) = v261;
  v100 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  *(_WORD *)(v100 + 230) = v262;
  v101 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  *(_WORD *)(v101 + 232) = v263;
  v102 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  *(_WORD *)(v102 + 234) = v264;
  v103 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  *(_WORD *)(v103 + 168) = v255;
  v104 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  *(_BYTE *)(v104 + 241) = v265;
  v105 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  *(_BYTE *)(v105 + 256) = v268;
  v106 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  *(_BYTE *)(v106 + 1347) = v297;
  v107 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  *(_BYTE *)(v107 + 1348) = v298;
  v108 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
  if ( v266 != *(_BYTE *)(v108 + 250) )
  {
    v109 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
    *(_BYTE *)(v109 + 250) = v266;
    if ( dword_103172528 )
    {
      v110 = (dword_103187508 != 0) + 1;
    }
    else
    {
      if ( *(_BYTE *)((*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf)
                    + 250) )
        v110 = 2;
      else
        v110 = dword_103172568 == 0;
      if ( *((_DWORD *)s_pServerConf + 3) == 1 )
        v110 = 1;
    }
    ChangeDacConfiguration(v110);
  }
  v111 = GetMasterDbId();
  switch ( (_DWORD)v111 )
  {
    case 0x7FFC:
      v112 = *((_QWORD *)qword_10316ECA0 + 13);
      break;
    case 0x7FFD:
      v112 = *((_QWORD *)qword_10316ECA0 + 14);
      break;
    case 0x7FFF:
      v112 = *((_QWORD *)qword_10316ECA0 + 11);
      break;
    default:
      if ( (unsigned int)v111 <= *((_DWORD *)qword_10316ECA0 + 19) && (_DWORD)v111 )
      {
        _mm_lfence();
        v112 = *(_QWORD *)(*((_QWORD *)qword_10316ECA0 + 5) + 8 * v111 - 8);
      }
      else
      {
        v112 = 0;
      }
      break;
  }
  v113 = GetMasterDbId();
  switch ( (_DWORD)v113 )
  {
    case 0x7FFC:
      v114 = *((_QWORD *)qword_10316ECA0 + 13);
      break;
    case 0x7FFD:
      v114 = *((_QWORD *)qword_10316ECA0 + 14);
      break;
    case 0x7FFF:
      v114 = *((_QWORD *)qword_10316ECA0 + 11);
      break;
    default:
      if ( (unsigned int)v113 <= *((_DWORD *)qword_10316ECA0 + 19) && (_DWORD)v113 )
      {
        _mm_lfence();
        v114 = *(_QWORD *)(*((_QWORD *)qword_10316ECA0 + 5) + 8 * v113 - 8);
      }
      else
      {
        v114 = 0;
      }
      break;
  }
  v115 = word_10317F774;
  if ( *(_BYTE *)(v112 + 2361) )
    v115 = 904;
  v116 = *(_WORD *)(*(_QWORD *)(v114 + 4624) + 1662LL);
  if ( v167 )
  {
    v177 = &v157;
    v178 = v115 > v116;
    v179 = v165;
    v180 = v89;
    v117 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v118 = *(_QWORD *)(v117 + 256);
    if ( !v118 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v118 = *(_QWORD *)(v117 + 256);
    }
    v119 = *(struct IMemObj **)(v118 + 1000);
    v120 = GetMasterDbId();
    v121 = ((__int64 (__fastcall *)(_QWORD))g_dbtableFactory[4])(v120);
    v172 = (unsigned __int64)(*(__int64 (__fastcall **)(struct BaseXact *, _QWORD, _QWORD))(*(_QWORD *)v5 + 272LL))(
                               v5,
                               *(unsigned __int16 *)(v121 + 40),
                               *(_QWORD *)(v121 + 4624));
    v188 = v172;
    CMEDCatalogConfig::Reconfig((CMEDCatalogConfig *)&v188, v119, v5, (struct ReconfigParam *)&v177);
    if ( (unsigned int)IsReplicatedMasterEnabled() )
    {
      v122 = GetMasterDbId();
      v123 = ((__int64 (__fastcall *)(_QWORD))g_dbtableFactory[4])(v122);
      if ( dword_1031852C8 )
      {
        if ( *(_WORD *)(v123 + 40) != 1 )
        {
          v124 = *(_QWORD *)(v123 + 4624);
          if ( !v124 )
          {
            LODWORD(v156) = 0;
            ex_raise(9, 30, 21, 1, v156, v123 + 936);
          }
          v125 = GetServerConfiguration();
          v126 = (struct XDES *)(*(__int64 (__fastcall **)(struct BaseXact *, __int64))(*(_QWORD *)v5 + 280LL))(
                                  v5,
                                  v124);
          ReconfigureLog::RecordReconfigureOperation(v126, (struct SysConfigPagePtr *)v234, v125, (struct LSN *)&v203);
          v127 = *((_QWORD *)GetServerConfiguration() + 1536);
          v128 = v204;
          if ( *(_WORD *)(v127 + 48) != v204
            || (v129 = v203, *(_DWORD *)(v127 + 40) != (_DWORD)v203)
            || (v130 = HIDWORD(v203), *(_DWORD *)(v127 + 44) != HIDWORD(v203)) )
          {
            *(_QWORD *)(v127 + 40) = v203;
            *(_WORD *)(v127 + 48) = v204;
            *(_WORD *)(v127 + 4) &= ~0x20u;
            v128 = v204;
            v130 = HIDWORD(v203);
            v129 = v203;
          }
          v131 = v236;
          if ( *((_WORD *)v236 + 24) != v128 || *((_DWORD *)v236 + 10) != v129 || *((_DWORD *)v236 + 11) != v130 )
          {
            *((_QWORD *)v236 + 5) = v203;
            *((_WORD *)v131 + 24) = v204;
            *((_WORD *)v131 + 2) &= ~0x20u;
          }
        }
      }
    }
    SysConfigPagePtr::Write(v234, 0);
  }
  if ( v157 )
    PostReconfigLogicalOptions(v157, v160);
  SystemAffinity::SystemAffinity((SystemAffinity *)v231);
  v132 = OsNumaConfig::Instance();
  if ( (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v132 + 24LL))(v132, v231) )
  {
    v133 = SystemAffinity::operator~(*(_QWORD *)&SOS_PublicGlobals::sm_osSystemAffinity[0], v302);
    SystemAffinity::operator&(v133, v230, v231);
  }
  else
  {
    SystemAffinity::SystemAffinity((SystemAffinity *)v230);
  }
  IsEmpty = SystemAffinity::IsEmpty((SystemAffinity *)v230);
  IsHotAddCpuSupported = IsEmpty == 0;
  if ( !IsEmpty )
  {
    IsHotAddCpuSupported = SOS_OS::IsHotAddCpuSupported((enum SOS_OS::HOT_ADD_CPU_UNSUPPORTED_REASON *)&v168);
    if ( !IsHotAddCpuSupported )
    {
      if ( v168 )
      {
        if ( v168 == 1 )
        {
          scierrlog(0x16DAu);
        }
        else if ( v168 != 2 && (unsigned int)(v168 - 3) >= 2 )
        {
          utassert_fail(1u, "FALSE", "sereconf.cpp", 1235, "Invalid switch value");
        }
      }
      else
      {
        scierrlog(0x16D9u);
      }
    }
  }
  if ( (v162 || IsHotAddCpuSupported) && v115 <= v116 )
  {
    v217 = *(_OWORD *)v278;
    v218 = v279;
    v219 = v280;
    v220 = v281;
    v221 = v282;
    v222 = v283;
    v223 = v284;
    v224 = v285;
    v136 = 1;
    if ( !SystemAffinity::GetCPUCount((SystemAffinity *)&v217) )
      v136 = 2;
    SOS_OS::UpdateProcessorStaticInfo();
    SystemAffinity::SystemAffinity((SystemAffinity *)v205);
    SystemAffinity::SystemAffinity((SystemAffinity *)&v207);
    SystemAffinity::SafeCopy(SOS_PublicGlobals::sm_AffinityMask, v229);
    v205[0] = v229[0];
    v205[1] = v229[1];
    v205[2] = v229[2];
    v205[3] = v229[3];
    v205[4] = v229[4];
    v205[5] = v229[5];
    v205[6] = v229[6];
    v205[7] = v229[7];
    v206 = SOS_OS_AffinityType;
    v207 = v217;
    v208 = v218;
    v209 = v219;
    v210 = v220;
    v211 = v221;
    v212 = v222;
    v213 = v223;
    v214 = v224;
    v215 = v136;
    v216 = 0;
    v137 = GetServerConfiguration();
    if ( (unsigned int)AffinityAutoConfiguration::ValidateProcessorAffinityNoX(
                         (const struct SystemAffinity *)&v207,
                         v137)
      || !SystemAffinity::GetCPUCount((SystemAffinity *)&v207) )
    {
      v227[0] = SOS_PublicGlobals::sm_osSystemAffinity[0];
      v227[1] = SOS_PublicGlobals::sm_osSystemAffinity[1];
      v227[2] = SOS_PublicGlobals::sm_osSystemAffinity[2];
      v227[3] = SOS_PublicGlobals::sm_osSystemAffinity[3];
      v227[4] = SOS_PublicGlobals::sm_osSystemAffinity[4];
      v227[5] = SOS_PublicGlobals::sm_osSystemAffinity[5];
      v227[6] = SOS_PublicGlobals::sm_osSystemAffinity[6];
      v227[7] = SOS_PublicGlobals::sm_osSystemAffinity[7];
      v138 = (const struct SystemAffinity *)&v207;
      if ( dword_103171DE8 )
      {
        if ( !SystemAffinity::GetCPUCount((SystemAffinity *)&v207)
          || (v147 = SystemAffinity::operator&(&v207, v303, v227), (unsigned int)SystemAffinity::operator!=(v147, &v207)) )
        {
          v138 = (const struct SystemAffinity *)v227;
        }
        SystemAffinity::SystemAffinity((SystemAffinity *)v228);
        SystemAffinityEnum::SystemAffinityEnum((SystemAffinityEnum *)v191, v138);
        for ( i = 0; SystemAffinityEnum::MoveNextBitSet((SystemAffinityEnum *)v191); ++i )
        {
          if ( i >= dword_103171DE8 )
            break;
          SystemAffinityEnum::GetCurrentPosition(v191, v225);
          SystemAffinity::operator|=(v228, v225);
        }
        v139 = v228[0];
        v140 = v228[1];
        v141 = v228[2];
        v142 = v228[3];
        v143 = v228[4];
        v144 = v228[5];
        v145 = v228[6];
        v146 = v228[7];
      }
      else
      {
        v139 = SOS_PublicGlobals::sm_osSystemAffinity[0];
        v140 = SOS_PublicGlobals::sm_osSystemAffinity[1];
        v141 = SOS_PublicGlobals::sm_osSystemAffinity[2];
        v142 = SOS_PublicGlobals::sm_osSystemAffinity[3];
        v143 = SOS_PublicGlobals::sm_osSystemAffinity[4];
        v144 = SOS_PublicGlobals::sm_osSystemAffinity[5];
        v145 = SOS_PublicGlobals::sm_osSystemAffinity[6];
        v146 = SOS_PublicGlobals::sm_osSystemAffinity[7];
      }
      v201 = v146;
      v200 = v145;
      v199 = v144;
      v198 = v143;
      v197 = v142;
      v196 = v141;
      v195 = v140;
      v194 = v139;
      v207 = v139;
      v208 = v140;
      v209 = v141;
      v210 = v142;
      v211 = v143;
      v212 = v144;
      v213 = v145;
      v214 = v146;
    }
    if ( !(unsigned int)AffinityAutoConfiguration::ApplyConfigChangesInternal(v205, &v207, v215) )
      ex_raise(58, 55, 16, 1);
    v216 = 0;
    if ( IsHotAddCpuSupported )
    {
      SystemAffinityEnum::SystemAffinityEnum((SystemAffinityEnum *)v192, (const struct SystemAffinity *)v230);
      while ( SystemAffinityEnum::MoveNextBitSet((SystemAffinityEnum *)v192) )
      {
        SystemAffinityEnum::GetCurrentPosition(v192, v226);
        CPUIdFromAffinity = GroupAffinity::GetCPUIdFromAffinity((GroupAffinity *)v226);
        scierrlog(
          0x16D8u,
          *((unsigned int *)SOS_PublicGlobals::sm_CPUInfo + 8 * CPUIdFromAffinity + 2),
          *((unsigned __int16 *)SOS_PublicGlobals::sm_CPUInfo + 16 * CPUIdFromAffinity),
          *((unsigned int *)SOS_PublicGlobals::sm_CPUInfo + 8 * CPUIdFromAffinity + 1));
      }
      PrintNodeConfiguration();
    }
    AffinityAutoConfiguration::~AffinityAutoConfiguration((AffinityAutoConfiguration *)v205);
  }
  if ( byte_10316E894 && dword_1031852C8 && (_BYTE)v163 )
  {
    v150 = L"100";
    if ( v290 )
      v150 = (wchar_t *)L"80";
    LogSystemMetadata(L"Updating Extensibility RgSettings to %s.", v150);
    v171[0] = 0;
    if ( (unsigned int)SOS_OS::EnqueueTask(SendUpdateExtensibilityRgToManagementService, v150, 0, v171, -1) )
    {
      LogSystemMetadata(L"EnqueueTask on SendUpdateExtensibilityRgToManagementService failed! call it inline.");
      SendUpdateExtensibilityRgToManagementService(v150);
    }
    else
    {
      LogSystemMetadata(L"EnqueueTask on SendUpdateExtensibilityRgToManagementService succeeded.");
    }
    CAutoRefc<SOS_Task>::~CAutoRefc<SOS_Task>(v171);
  }
  (**(void (__fastcall ***)(__int64, __int64))v27)(v27, 1);
  v151 = v170;
  if ( v170 )
  {
    v152 = v169;
    do
    {
      v153 = v152[8]-- == 1;
      if ( v153 )
      {
        _InterlockedOr(v155, 0);
        v154 = v169;
        v169[6] = 0;
        v154[7] = 0;
        EventAutoInternal<SuspendQueueSLock>::Signal(v154, 0);
        v151 = v170;
      }
      v153 = v151-- == 1;
      v170 = v151;
    }
    while ( !v153 );
  }
}

```

## disassembly

```asm
0x1011fb350  push    rbp
0x1011fb352  push    rsi
0x1011fb353  push    rdi
0x1011fb354  push    r12
0x1011fb356  push    r13
0x1011fb358  push    r14
0x1011fb35a  push    r15
0x1011fb35c  lea     rbp, [rsp-3D50h]
0x1011fb364  mov     eax, 3E50h
0x1011fb369  call    _alloca_probe
0x1011fb36e  sub     rsp, rax
0x1011fb371  mov     [rbp+3D80h+var_3CC0], 0FFFFFFFFFFFFFFFEh
0x1011fb37c  mov     [rsp+3E80h+arg_10], rbx
0x1011fb384  movaps  [rsp+3E80h+var_40], xmm6
0x1011fb38c  movaps  [rsp+3E80h+var_50], xmm7
0x1011fb394  mov     rax, cs:__security_cookie
0x1011fb39b  xor     rax, rsp
0x1011fb39e  mov     [rbp+3D80h+var_60], rax
0x1011fb3a5  mov     [rbp+3D80h+var_3DEC], r9d
0x1011fb3a9  mov     [rbp+3D80h+var_3DF8], r8d
0x1011fb3ad  mov     [rbp+3D80h+var_3DF4], edx
0x1011fb3b0  mov     r12, rcx
0x1011fb3b3  mov     [rbp+3D80h+var_3DA8], rcx
0x1011fb3b7  xor     r14d, r14d
0x1011fb3ba  mov     [rbp+3D80h+var_6B8], r14d
0x1011fb3c1  mov     [rbp+3D80h+var_3E00], r14d
0x1011fb3c5  xor     dil, dil
0x1011fb3c8  mov     [rsp+3E80h+var_3E0F], dil
0x1011fb3cd  mov     [rsp+3E80h+var_3E10], dil
0x1011fb3d2  mov     [rsp+3E80h+var_3E08], dil
0x1011fb3d7  mov     byte ptr [rbp+3D80h+var_3DFC], dil
0x1011fb3db  mov     esi, cs:dword_10317A9FC
0x1011fb3e1  and     esi, 81h
0x1011fb3e7  call    ?GetMasterDbId@@YAGXZ; GetMasterDbId(void)
0x1011fb3ec  movzx   ebx, ax
0x1011fb3ef  call    ?IsReplicatedMasterEnabled@@YAHXZ; IsReplicatedMasterEnabled(void)
0x1011fb3f4  lea     r15d, [r14+2]
0x1011fb3f8  test    eax, eax
0x1011fb3fa  jnz     short loc_1011FB405
0x1011fb3fc  call    ?IsContainedAGEnabledInstance@@YAHXZ; IsContainedAGEnabledInstance(void)
0x1011fb401  test    eax, eax
0x1011fb403  jz      short loc_1011FB42F
0x1011fb405  call    ?IsContainedAGEnabledInstance@@YAHXZ; IsContainedAGEnabledInstance(void)
0x1011fb40a  test    eax, eax
0x1011fb40c  jz      short loc_1011FB42F
0x1011fb40e  movzx   ecx, bx; unsigned __int16
0x1011fb411  call    ?IsContainedAgMasterDBId@@YA_NG@Z; IsContainedAgMasterDBId(ushort)
0x1011fb416  test    al, al
0x1011fb418  jz      short loc_1011FB42F
0x1011fb41a  mov     r9d, r15d
0x1011fb41d  mov     edx, 4Ah ; 'J'
0x1011fb422  lea     ecx, [rdx-10h]
0x1011fb425  lea     r8d, [rdx-3Ah]
0x1011fb429  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1011fb42f  lea     rax, ?sm_ConfigurationLock@SysConfigPagePtr@@0VSOS_RecursiveMutex@@A; SOS_RecursiveMutex SysConfigPagePtr::sm_ConfigurationLock
0x1011fb436  mov     [rbp+3D80h+var_3DE0], rax
0x1011fb43a  mov     [rbp+3D80h+var_3DD8], r14d
0x1011fb43e  mov     edx, 4002CBh
0x1011fb443  lea     rcx, [rbp+3D80h+var_3DE0]
0x1011fb447  call    ?GetAccess@?$TAutoMutex@VSOS_RecursiveMutex@@$0PPPPPPPP@@@QEAAXI@Z; TAutoMutex<SOS_RecursiveMutex,4294967295>::GetAccess(uint)
0x1011fb44c  call    cs:__imp_?IsWow64@SOS_OS@@SAHXZ; SOS_OS::IsWow64(void)
0x1011fb452  mov     r13d, 1
0x1011fb458  lea     r15, __@@_PchSym_@00@UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq@4B2008FD98C1DD4
0x1011fb45f  test    eax, eax
0x1011fb461  jnz     loc_1011FB63D
0x1011fb467  cmp     [rbp+3D80h+arg_20], eax
0x1011fb46d  jnz     loc_1011FB63D
0x1011fb473  lea     rdi, word_10317A7D2
0x1011fb47a  lea     rax, dword_10317998C
0x1011fb481  cmp     cs:dword_103172568, 0
0x1011fb488  cmovz   rdi, rax
0x1011fb48c  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1011fb493  inc     rbx
0x1011fb496  cmp     word ptr [rdi+rbx*2], 0
0x1011fb49b  jnz     short loc_1011FB493
0x1011fb49d  xor     edx, edx; Val
0x1011fb49f  mov     r8d, 0F8h; Size
0x1011fb4a5  lea     rcx, [rbp+3D80h+var_37C0]; void *
0x1011fb4ac  call    memset_0
0x1011fb4b1  mov     [rbp+3D80h+var_3DF0], r13d
0x1011fb4b5  lea     rax, [rbp+3D80h+var_3DF0]
0x1011fb4b9  mov     [rbp+3D80h+var_3DB0], rax
0x1011fb4bd  mov     cs:dword_103171DDC, r14d
0x1011fb4c4  mov     r8d, ebx; unsigned __int64
0x1011fb4c7  lea     r9, [rbp+3D80h+var_37C0]; struct FILESTREAM_CONFIG *
0x1011fb4ce  mov     rdx, rdi; wchar_t *
0x1011fb4d1  lea     rcx, [rbp+3D80h+var_3DB0]; this
0x1011fb4d5  call    ?ReadFromRegistry@CFilestreamConfiguration@@QEAAJPEB_W_KPEAUFILESTREAM_CONFIG@@@Z; CFilestreamConfiguration::ReadFromRegistry(wchar_t const *,unsigned __int64,FILESTREAM_CONFIG *)
0x1011fb4da  mov     edi, eax
0x1011fb4dc  cmp     eax, 8007064Ah
0x1011fb4e1  jnz     short loc_1011FB4F0
0x1011fb4e3  mov     cs:dword_103171DDC, 60h ; '`'
0x1011fb4ed  mov     edi, r14d
0x1011fb4f0  mov     [rbp+3D80h+var_3D78], 4001DDh
0x1011fb4f7  mov     [rbp+3D80h+var_3D70], r14
0x1011fb4fb  mov     [rbp+3D80h+var_3D60], r14
0x1011fb4ff  mov     [rbp+3D80h+var_3D68], r14
0x1011fb503  mov     [rbp+3D80h+var_3D58], r14
0x1011fb507  lea     rax, qword_103171C80
0x1011fb50e  mov     [rbp+3D80h+var_3DA0], rax
0x1011fb512  mov     ebx, r14d
0x1011fb515  mov     [rbp+3D80h+var_3D98], ebx
0x1011fb518  lea     r9, [rbp+3D80h+var_3D78]
0x1011fb51c  mov     edx, 2
0x1011fb521  mov     r8d, 0FFFFFFFFh
0x1011fb527  mov     rcx, rax
0x1011fb52a  call    ?GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z; SOS_RWLock::GetLock(RWLockMode,ulong,SOS_WaitInfo const *)
0x1011fb52f  test    eax, eax
0x1011fb531  jnz     short loc_1011FB53D
0x1011fb533  mov     ebx, 2
0x1011fb538  mov     [rbp+3D80h+var_3D98], ebx
0x1011fb53b  jmp     short loc_1011FB57D
0x1011fb53d  sub     eax, 2
0x1011fb540  jz      short loc_1011FB576
0x1011fb542  cmp     eax, 1
0x1011fb545  jz      short loc_1011FB572
0x1011fb547  lea     rax, ?szText@?8???$CompileOnDataType@$0A@$00_K@RbpDecode@@CAP6AX_N0HPEA_K1PEBVRbpColumnContextNew@@PEAE@ZW4RbpDataType@@W4RbpEncodingType@@00@Z@4QBDB; "Invalid switch value"
0x1011fb54e  mov     [rsp+3E80h+var_3E60], rax
0x1011fb553  mov     r9d, 718h
0x1011fb559  lea     r8, aSqlNtdbmsStore_838; "sql\\ntdbms\\storeng\\filestrm\\fstrhlp"...
0x1011fb560  lea     rdx, ?szExpression@?CC@???$GetJobPartition@$$CBV_lambda_ae11ec6e04ca7d20c663000a5faff827_@@@CBulkSyncedJobSchedulerBySpinLock@@QEAA?AW4EJobSchedResult@CBulkSyncedJobScheduler@@AEAK0KAEBV_lambda_ae11ec6e04ca7d20c663000a5faff827_@@@Z@4QBDB; "FALSE"
0x1011fb567  mov     ecx, r13d
0x1011fb56a  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1011fb570  jmp     short loc_1011FB57D
0x1011fb572  mov     cl, 0D4h
0x1011fb574  jmp     short loc_1011FB578
0x1011fb576  mov     cl, 0D3h
0x1011fb578  call    ?RaiseExecutionAbortedError@@YAXW4ABORT_AND_LCK_EXCEPTIONS@@@Z; RaiseExecutionAbortedError(ABORT_AND_LCK_EXCEPTIONS)
0x1011fb57d  lea     rcx, rva dword_103171CD8[r15]
0x1011fb584  lea     rax, [rbp+3D80h+var_37C0]
0x1011fb58b  movups  xmm0, xmmword ptr [rax]
0x1011fb58e  movups  xmmword ptr [rcx], xmm0
0x1011fb591  movups  xmm1, xmmword ptr [rax+10h]
0x1011fb595  movups  xmmword ptr [rcx+10h], xmm1
0x1011fb599  movups  xmm0, xmmword ptr [rax+20h]
0x1011fb59d  movups  xmmword ptr [rcx+20h], xmm0
0x1011fb5a1  movups  xmm1, xmmword ptr [rax+30h]
0x1011fb5a5  movups  xmmword ptr [rcx+30h], xmm1
0x1011fb5a9  movups  xmm0, xmmword ptr [rax+40h]
0x1011fb5ad  movups  xmmword ptr [rcx+40h], xmm0
0x1011fb5b1  movups  xmm1, xmmword ptr [rax+50h]
0x1011fb5b5  movups  xmmword ptr [rcx+50h], xmm1
0x1011fb5b9  movups  xmm0, xmmword ptr [rax+60h]
0x1011fb5bd  movups  xmmword ptr [rcx+60h], xmm0
0x1011fb5c1  lea     rcx, [rcx+80h]
0x1011fb5c8  movups  xmm1, xmmword ptr [rax+70h]
0x1011fb5cc  movups  xmmword ptr [rcx-10h], xmm1
0x1011fb5d0  lea     rax, [rax+80h]
0x1011fb5d7  movups  xmm0, xmmword ptr [rax]
0x1011fb5da  movups  xmmword ptr [rcx], xmm0
0x1011fb5dd  movups  xmm1, xmmword ptr [rax+10h]
0x1011fb5e1  movups  xmmword ptr [rcx+10h], xmm1
0x1011fb5e5  movups  xmm0, xmmword ptr [rax+20h]
0x1011fb5e9  movups  xmmword ptr [rcx+20h], xmm0
0x1011fb5ed  movups  xmm1, xmmword ptr [rax+30h]
0x1011fb5f1  movups  xmmword ptr [rcx+30h], xmm1
0x1011fb5f5  movups  xmm0, xmmword ptr [rax+40h]
0x1011fb5f9  movups  xmmword ptr [rcx+40h], xmm0
0x1011fb5fd  movups  xmm1, xmmword ptr [rax+50h]
0x1011fb601  movups  xmmword ptr [rcx+50h], xmm1
0x1011fb605  movups  xmm0, xmmword ptr [rax+60h]
0x1011fb609  movups  xmmword ptr [rcx+60h], xmm0
0x1011fb60d  mov     rax, [rax+70h]
0x1011fb611  mov     [rcx+70h], rax
0x1011fb615  test    ebx, ebx
0x1011fb617  jz      short loc_1011FB62C
0x1011fb619  mov     edx, ebx
0x1011fb61b  lea     rcx, qword_103171C80
0x1011fb622  call    cs:__imp_?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z; SOS_RWLock::ReleaseLock(RWLockMode)
0x1011fb628  mov     [rbp+3D80h+var_3D98], r14d
0x1011fb62c  lea     rdx, aFilestreamInit; "Filestream init"
0x1011fb633  mov     ecx, edi; int
0x1011fb635  call    ?CheckHrFailAndExit@@YAXJPEBD@Z; CheckHrFailAndExit(long,char const *)
0x1011fb63a  xor     dil, dil
0x1011fb63d  lea     rax, [rbp+3D80h+var_26C1]
0x1011fb644  and     rax, 0FFFFFFFFFFFFF000h
0x1011fb64a  mov     [rbp+3D80h+var_6C0], rax
0x1011fb651  call    ?GetServerConfiguration@@YAAEAVSysConfigPagePtr@@XZ; GetServerConfiguration(void)
0x1011fb656  mov     rdx, [rax+3000h]; Val
0x1011fb65d  mov     rcx, [rbp+3D80h+var_6C0]; void *
0x1011fb664  test    rcx, rcx
0x1011fb667  jz      short loc_1011FB680
0x1011fb669  mov     r8d, 2000h; Size
0x1011fb66f  test    rdx, rdx
0x1011fb672  jz      short loc_1011FB67B
0x1011fb674  call    memmove
0x1011fb679  jmp     short loc_1011FB692
0x1011fb67b  call    memset_0
0x1011fb680  call    cs:__imp__errno
0x1011fb686  mov     dword ptr [rax], 16h
0x1011fb68c  call    cs:__imp__invalid_parameter_noinfo
0x1011fb692  call    ?GetServerConfiguration@@YAAEAVSysConfigPagePtr@@XZ; GetServerConfiguration(void)
0x1011fb697  lea     r8, [rax+300Ch]
0x1011fb69e  lea     rdx, [rbp+3D80h+var_6B4]
0x1011fb6a5  call    ??$CopyConfigOptions@VDS_CONFIG@@V1@@SysConfigPagePtr@@QEAAXPEAVDS_CONFIG@@0@Z; SysConfigPagePtr::CopyConfigOptions<DS_CONFIG,DS_CONFIG>(DS_CONFIG *,DS_CONFIG *)
0x1011fb6aa  mov     edx, 400h
0x1011fb6af  test    esi, esi
0x1011fb6b1  jz      loc_1011FB757
0x1011fb6b7  mov     rax, [rbp+3D80h+var_6C0]
0x1011fb6be  movzx   ecx, word ptr [rax+1FFEh]
0x1011fb6c5  add     rcx, rax
0x1011fb6c8  add     rcx, 138h
0x1011fb6cf  jz      short loc_1011FB734
0x1011fb6d1  lea     rax, [rbp+3D80h+var_584]
0x1011fb6d8  mov     edx, 8
0x1011fb6dd  nop     dword ptr [rax]
0x1011fb6e0  movups  xmm0, xmmword ptr [rcx]
0x1011fb6e3  movups  xmmword ptr [rax], xmm0
0x1011fb6e6  movups  xmm1, xmmword ptr [rcx+10h]
0x1011fb6ea  movups  xmmword ptr [rax+10h], xmm1
0x1011fb6ee  movups  xmm0, xmmword ptr [rcx+20h]
0x1011fb6f2  movups  xmmword ptr [rax+20h], xmm0
0x1011fb6f6  movups  xmm1, xmmword ptr [rcx+30h]
0x1011fb6fa  movups  xmmword ptr [rax+30h], xmm1
0x1011fb6fe  movups  xmm0, xmmword ptr [rcx+40h]
0x1011fb702  movups  xmmword ptr [rax+40h], xmm0
0x1011fb706  movups  xmm1, xmmword ptr [rcx+50h]
0x1011fb70a  movups  xmmword ptr [rax+50h], xmm1
0x1011fb70e  movups  xmm0, xmmword ptr [rcx+60h]
0x1011fb712  movups  xmmword ptr [rax+60h], xmm0
0x1011fb716  lea     rax, [rax+80h]
0x1011fb71d  movups  xmm1, xmmword ptr [rcx+70h]
0x1011fb721  movups  xmmword ptr [rax-10h], xmm1
0x1011fb725  lea     rcx, [rcx+80h]
0x1011fb72c  sub     rdx, 1
0x1011fb730  jnz     short loc_1011FB6E0
0x1011fb732  jmp     short loc_1011FB757
0x1011fb734  mov     r8, rdx; Size
0x1011fb737  xor     edx, edx; Val
0x1011fb739  lea     rcx, [rbp+3D80h+var_584]; void *
0x1011fb740  call    memset_0
0x1011fb745  call    cs:__imp__errno
0x1011fb74b  mov     dword ptr [rax], 16h
0x1011fb751  call    cs:__imp__invalid_parameter_noinfo
0x1011fb757  call    ?GetMasterDbId@@YAGXZ; GetMasterDbId(void)
0x1011fb75c  movzx   ecx, ax
0x1011fb75f  mov     rax, cs:__imp_?g_dbtableFactory@@3UDBTableFactory@@A; DBTableFactory g_dbtableFactory
0x1011fb766  call    qword ptr [rax+20h]
0x1011fb769  mov     rcx, [rax+1210h]
0x1011fb770  xor     r8d, r8d
0x1011fb773  mov     edx, r13d
0x1011fb776  mov     rcx, [rcx+6A0h]
0x1011fb77d  call    ?GetFCB@FileMgr@@QEBAPEAVFCB@@JW4LookupFailureMode@@@Z; FileMgr::GetFCB(long,LookupFailureMode)
0x1011fb782  mov     r8, [rbp+3D80h+var_6C0]; struct Page *
0x1011fb789  mov     edx, 0Ah; unsigned int
0x1011fb78e  mov     rcx, rax; this
0x1011fb791  call    ?CopyPageToReplicas@FCB@@QEAAXKPEAVPage@@@Z; FCB::CopyPageToReplicas(ulong,Page *)
0x1011fb796  mov     rdx, gs:58h
0x1011fb79f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1011fb7a6  mov     ecx, [rax]
0x1011fb7a8  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1011fb7af  mov     ebx, [rax]
0x1011fb7b1  add     rbx, [rdx+rcx*8]
0x1011fb7b5  mov     rcx, [rbx+100h]
0x1011fb7bc  test    rcx, rcx
0x1011fb7bf  jnz     short loc_1011FB7CE
0x1011fb7c1  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1011fb7c7  mov     rcx, [rbx+100h]
0x1011fb7ce  mov     r9d, 254h
0x1011fb7d4  lea     r8, aSqlNtdbmsStore_3; "sql\\ntdbms\\storeng\\common\\sereconf."...
0x1011fb7db  mov     rdx, r12
0x1011fb7de  mov     rcx, [rcx+3E8h]
0x1011fb7e5  mov     rax, cs:__imp_?g_metadataFactory@@3UMetadataFactory@@A; MetadataFactory g_metadataFactory
0x1011fb7ec  call    qword ptr [rax]
0x1011fb7ee  mov     r13, rax
0x1011fb7f1  mov     qword ptr [rbp+3D80h+var_3DC0], rax
0x1011fb7f5  mov     [rbp+3D80h+var_3D50], rax
0x1011fb7f9  mov     rdx, [rax]
0x1011fb7fc  mov     rcx, rax
0x1011fb7ff  call    qword ptr [rdx+70h]
0x1011fb802  mov     rsi, rax
0x1011fb805  xor     al, al
0x1011fb807  movzx   r15d, al
0x1011fb80b  cmp     cs:byte_10316E91D, al
0x1011fb811  mov     eax, 1
0x1011fb816  cmovnz  r15d, eax
0x1011fb81a  mov     [rsp+3E80h+var_3E04], r14d
0x1011fb81f  mov     r9, [rsi]
0x1011fb822  movzx   r8d, al
0x1011fb826  xor     edx, edx
0x1011fb828  mov     rcx, rsi
0x1011fb82b  call    qword ptr [r9]
0x1011fb82e  mov     rcx, cs:qword_10317B628
0x1011fb835  mov     r14, [rcx+1040h]
0x1011fb83c  shl     r14, 3
0x1011fb840  shr     r14, 0Ah
0x1011fb844  mov     rax, [rsi]
0x1011fb847  lea     rdx, [rsp+3E80h+var_3E04]
0x1011fb84c  mov     rcx, rsi
0x1011fb84f  call    qword ptr [rax+8]
0x1011fb852  test    al, al
0x1011fb854  jz      loc_1011FB9EC
0x1011fb85a  mov     r13d, [rbp+3D80h+var_3DF8]
0x1011fb85e  mov     r12d, [rbp+3D80h+var_3DFC]
0x1011fb862  mov     [rsp+3E80h+var_3E0C], 0
0x1011fb86a  mov     rax, [rsi]
0x1011fb86d  lea     r8, [rbp+3D80h+var_3C30]
0x1011fb874  mov     edx, [rsp+3E80h+var_3E04]
0x1011fb878  mov     rcx, rsi
0x1011fb87b  call    qword ptr [rax+10h]
  ... truncated ...
```
