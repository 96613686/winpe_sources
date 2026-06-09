# TaskStretchTable::ProcessTskPkt(void)

- ea: `0x101e80e00`
- end: `0x101e82f8f`
- name: `?ProcessTskPkt@TaskStretchTable@@UEAAXXZ`
- size: `8591`
- prototype: `void __fastcall(TaskStretchTable *__hidden this)`
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x100401070`
- `0x100401090`
- `0x1004012d0`
- `0x100401340`
- `0x100401450`
- `0x1004a91c0`
- `0x100a2cdc0`
- `0x100a2cf70`
- `0x100a2d480`
- `0x100a2d630`
- `0x100a2d7e0`
- `0x100a2d990`
- `0x100a2db40`
- `0x100a2dcf0`
- `0x100a2dea0`
- `0x100a2e8c0`
- `0x100a31d10`
- `0x100a31ec0`
- `0x100a32070`
- `0x100b35150`
- `0x101e6e000`
- `0x101e77f30`
- `0x101e7d660`
- `0x101e7ea70`
- `0x101e80310`
- `0x101e80a50`
- `0x101e80e00`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x101e81b91`
- `KERNEL32!QueryPerformanceCounter` at `0x101e81ec5`
- `KERNEL32!QueryPerformanceCounter` at `0x101e82838`
- `KERNEL32!QueryPerformanceCounter` at `0x101e82ad3`
- `KERNEL32!QueryPerformanceCounter` at `0x101e81b91`
- `KERNEL32!QueryPerformanceCounter` at `0x101e81ec5`
- `KERNEL32!QueryPerformanceCounter` at `0x101e82838`
- `KERNEL32!QueryPerformanceCounter` at `0x101e82ad3`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x101e80fe9`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x101e816c5`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x101e82104`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x101e824fe`
- `sqldk!?g_pAutoXactFactory@@3PEAVIAutoXactFactory@@EA` at `0x101e80f5c`
- `sqldk!?g_pAutoXactFactory@@3PEAVIAutoXactFactory@@EA` at `0x101e81637`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101e8103b`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101e82d4c`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101e82d72`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101e80f3c`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101e81f80`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101e828ec`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101e82b87`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101e81b7d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101e81ea9`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101e81f6c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101e8281c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101e828d8`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101e82ab7`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101e82b73`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x101e81bb5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e8184e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e81d9e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e82453`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e8184e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e81d9e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e82453`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101e823bf`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101e823bf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e8212d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e82165`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e821a8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e821cf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e82527`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e82564`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e825ac`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e8212d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e82165`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e821a8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e821cf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e82527`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e82564`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e825ac`
- `sqldk!SystemThread_TlsIndex` at `0x101e80eff`
- `sqldk!SystemThread_TlsIndex` at `0x101e80fa3`
- `sqldk!SystemThread_TlsIndex` at `0x101e8167f`
- `sqldk!SystemThread_TlsIndex` at `0x101e816e2`
- `sqldk!SystemThread_TlsIndex` at `0x101e817eb`
- `sqldk!SystemThread_TlsIndex` at `0x101e820be`
- `sqldk!SystemThread_TlsIndex` at `0x101e82387`
- `sqldk!SystemThread_TlsIndex` at `0x101e824b8`
- `sqldk!SystemThread_TlsOffset` at `0x101e80f08`
- `sqldk!SystemThread_TlsOffset` at `0x101e80fac`
- `sqldk!SystemThread_TlsOffset` at `0x101e81688`
- `sqldk!SystemThread_TlsOffset` at `0x101e816eb`
- `sqldk!SystemThread_TlsOffset` at `0x101e817f4`
- `sqldk!SystemThread_TlsOffset` at `0x101e820c7`
- `sqldk!SystemThread_TlsOffset` at `0x101e82390`
- `sqldk!SystemThread_TlsOffset` at `0x101e824c1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e80fc5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e816a1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e81704`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e820e0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e823a9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e824da`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e80fc5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e816a1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e81704`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e820e0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e823a9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e824da`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101e80f2e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101e8181a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101e80f2e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101e8181a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e81984`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e81a15`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e8236e`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e823ce`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e81984`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e81a15`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e8236e`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e823ce`
- `sqlmin!?LookupDB@DBMgr@@QEBAPEAVDBTABLE@@K@Z` at `0x101e8105e`
- `sqlmin!?LookupDB@DBMgr@@QEBAPEAVDBTABLE@@K@Z` at `0x101e8115e`
- `sqlmin!?LookupDB@DBMgr@@QEBAPEAVDBTABLE@@K@Z` at `0x101e8105e`
- `sqlmin!?LookupDB@DBMgr@@QEBAPEAVDBTABLE@@K@Z` at `0x101e8115e`
- `sqlmin!?IsMarkedReadOnly@DBTABLE@@QEBA_N_N@Z` at `0x101e81081`
- `sqlmin!?IsMarkedReadOnly@DBTABLE@@QEBA_N_N@Z` at `0x101e82d99`
- `sqlmin!?IsMarkedReadOnly@DBTABLE@@QEBA_N_N@Z` at `0x101e81081`
- `sqlmin!?IsMarkedReadOnly@DBTABLE@@QEBA_N_N@Z` at `0x101e82d99`
- `sqlmin!?SetClass@LockRequest@@QEAAXK@Z` at `0x101e811c5`
- `sqlmin!?SetClass@LockRequest@@QEAAXK@Z` at `0x101e811c5`
- `sqlmin!?lck_lock@@YA?AW4LCK_RESULT@@AEAVLockRequest@@AEAVLockRes@@PEAVLockInfo@@@Z` at `0x101e81277`
- `sqlmin!?lck_lock@@YA?AW4LCK_RESULT@@AEAVLockRequest@@AEAVLockRes@@PEAVLockInfo@@@Z` at `0x101e81277`
- `sqlmin!?SetDatabaseResource@LockRes@@QEAAXKW4DBLockSubresource@1@@Z` at `0x101e8113b`
- `sqlmin!?SetDatabaseResource@LockRes@@QEAAXKW4DBLockSubresource@1@@Z` at `0x101e8113b`
- `sqlmin!?SetTransactionLockState@LockRequest@@QEAAXPEAVXactLockInfo@@@Z` at `0x101e81192`
- `sqlmin!?SetTransactionLockState@LockRequest@@QEAAXPEAVXactLockInfo@@@Z` at `0x101e81192`
- `sqlmin!?SetTimeout@LockRequest@@QEAAXK@Z` at `0x101e811a2`
- `sqlmin!?SetTimeout@LockRequest@@QEAAXK@Z` at `0x101e811a2`
- `sqlmin!?SetMode@LockRequest@@QEAAXW4LCK_MODE@@@Z` at `0x101e811b2`
- `sqlmin!?SetMode@LockRequest@@QEAAXW4LCK_MODE@@@Z` at `0x101e811b2`
- `sqlmin!??1LockRequest@@QEAA@XZ` at `0x101e82ccf`
- `sqlmin!??1LockRequest@@QEAA@XZ` at `0x101e82ccf`
- `sqlmin!??0LockRequest@@QEAA@XZ` at `0x101e8117f`
- `sqlmin!??0LockRequest@@QEAA@XZ` at `0x101e8117f`
- `sqlmin!??0LockRes@@QEAA@XZ` at `0x101e81124`
- `sqlmin!??0LockRes@@QEAA@XZ` at `0x101e81124`

## string_xrefs

- `0x101e8186a`: `TaskStretchTable::ProcessTskPkt (%d, %d, %d) Data Reconciliation in Progress`
- `0x101e82d1c`: `TaskStretchTable::ProcessTskPkt (%d, %d, %d) the local database is not updateable`
- `0x101e82cfe`: `TaskStretchTable::ProcessTskPkt (%d, %d, %d) the stretch remote is not connected`
- `0x101e82ce2`: `TaskStretchTable::ProcessTskPkt (%d, %d, %d) no tables stretched`
- `0x101e8179e`: `TaskStretchTable::ProcessTskPkt (%d, %d, %d) migrationDirection = %d`
- `0x101e81298`: `TaskStretchTable::ProcessTskPkt (%d, %d, %d) failed to acquire shared lock`
- `0x101e80f80`: `TaskStretchTable`
- `0x101e80eb8`: `TaskStretchTable::ProcessTskPkt (%d, %d, %d) start`
- `0x101e80fd8`: `sql\ntdbms\stretch\src\stretchtask.cpp`
- `0x101e816b4`: `sql\ntdbms\stretch\src\stretchtask.cpp`
- `0x101e820f3`: `sql\ntdbms\stretch\src\stretchtask.cpp`
- `0x101e824ed`: `sql\ntdbms\stretch\src\stretchtask.cpp`
- `0x101e8183d`: `"sql\\ntdbms\\stretch\\src\\stretchtask.cpp"`
- `0x101e81d8d`: `"sql\\ntdbms\\stretch\\src\\stretchtask.cpp"`
- `0x101e82442`: `"sql\\ntdbms\\stretch\\src\\stretchtask.cpp"`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
void __fastcall TaskStretchTable::ProcessTskPkt(TaskStretchTable *this)
{
  unsigned int v2; // r13d
  unsigned int v3; // r12d
  char v4; // cl
  __int64 v5; // rdx
  struct CSessionTraceFlags *v6; // rcx
  __int64 v7; // rsi
  __int64 v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rsi
  __int64 v11; // rax
  struct DBTABLE *v12; // rax
  DBTABLE *v13; // rdi
  __int64 v14; // rax
  __int64 v15; // r14
  char v16; // al
  char v17; // r14
  __int64 *v18; // rdi
  __int64 v19; // rsi
  struct DBTABLE *v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rdx
  __int64 v23; // rdi
  __int64 v24; // r14
  __int64 v25; // rax
  unsigned int v26; // eax
  __int64 v27; // r8
  __int64 v28; // rax
  __int64 v29; // rsi
  int v30; // r13d
  char v31; // di
  __int64 v32; // rdi
  unsigned int v33; // eax
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rsi
  __int64 v38; // r14
  __int64 v39; // rdi
  __int64 v40; // rcx
  struct IMetadataAccess *v41; // r14
  __int64 v42; // rdi
  __int64 v43; // rcx
  struct IRemoteDbProvisioning *v44; // rdi
  unsigned int v45; // esi
  _QWORD *ThreadLocalStoragePointer; // r8
  unsigned int v47; // eax
  __int64 v48; // rdx
  struct CSessionTraceFlags *v49; // rcx
  __int64 v50; // rsi
  int MigrationBatch; // edi
  CSbTransportMgr *QuadPart; // rax
  unsigned int v53; // r13d
  int v54; // eax
  __int64 v55; // r8
  __int64 v56; // r9
  int v57; // edi
  char v58; // r14
  unsigned int v59; // esi
  unsigned int v60; // r12d
  char v61; // cl
  _BYTE *v62; // rsi
  CSbTransportMgr *v63; // rcx
  unsigned __int64 v64; // rcx
  unsigned __int64 v65; // rdx
  __int32 v66; // eax
  __int64 v67; // rsi
  __int64 v68; // rdi
  __int64 v69; // rcx
  __int64 v70; // rsi
  __int64 v71; // rdi
  __int64 v72; // r8
  __int64 v73; // rdi
  __int64 v74; // rdi
  __int64 v75; // rax
  void (__fastcall ***v76)(_QWORD, __int64); // rcx
  __int64 v77; // rbx
  struct Worker *v78; // rcx
  __int64 v79; // rsi
  __int64 v80; // rdi
  __int64 v81; // rcx
  __int64 v82; // rdi
  __int64 v83; // rsi
  __int64 v84; // r8
  __int64 v85; // rsi
  __int64 v86; // rsi
  CSbTransportMgr *v87; // rcx
  unsigned __int64 v88; // rcx
  unsigned __int64 v89; // rdx
  CSbTransportMgr *v90; // rcx
  unsigned __int64 v91; // rcx
  unsigned __int64 v92; // rdx
  TaskStretchTable *v93; // rcx
  TaskStretchTable *v94; // rsi
  __int64 v95; // rax
  DBTABLE *v96; // rdi
  bool v97; // al
  int v98; // ebx
  LARGE_INTEGER v99; // rax
  struct __crt_locale_pointers *DefaultLocale; // rax
  CSbTransportMgr *v102; // rcx
  unsigned __int64 v103; // rcx
  unsigned __int64 v104; // rdx
  int v105; // eax
  CSbTransportMgr *v106; // rcx
  unsigned __int64 v107; // rcx
  unsigned __int64 v108; // rdx
  int v109; // eax
  CSbTransportMgr *v110; // rcx
  unsigned __int64 v111; // rcx
  unsigned __int64 v112; // rdx
  int v113; // eax
  int (*v114)(int, int, int, int, char *); // [rsp+20h] [rbp-3068h]
  int (*v115)(int, int, int, int, char *); // [rsp+20h] [rbp-3068h]
  int v116; // [rsp+20h] [rbp-3068h]
  int v117; // [rsp+20h] [rbp-3068h]
  int v118; // [rsp+28h] [rbp-3060h]
  int v119; // [rsp+28h] [rbp-3060h]
  int v120; // [rsp+28h] [rbp-3060h]
  __int64 v121; // [rsp+30h] [rbp-3058h]
  int v122; // [rsp+38h] [rbp-3050h]
  int v123; // [rsp+38h] [rbp-3050h]
  int v124; // [rsp+40h] [rbp-3048h]
  bool v125; // [rsp+50h] [rbp-3038h]
  unsigned int v126; // [rsp+54h] [rbp-3034h]
  char v127; // [rsp+58h] [rbp-3030h]
  char v128; // [rsp+59h] [rbp-302Fh]
  unsigned int v129; // [rsp+5Ch] [rbp-302Ch]
  char v130; // [rsp+60h] [rbp-3028h]
  char v131; // [rsp+62h] [rbp-3026h]
  char v132; // [rsp+63h] [rbp-3025h]
  int v133; // [rsp+64h] [rbp-3024h]
  unsigned int v134; // [rsp+68h] [rbp-3020h]
  CSbTransportMgr *v135; // [rsp+70h] [rbp-3018h] BYREF
  unsigned int v136; // [rsp+78h] [rbp-3010h]
  int v137; // [rsp+7Ch] [rbp-300Ch]
  int v138; // [rsp+80h] [rbp-3008h]
  TaskStretchTable *v139; // [rsp+88h] [rbp-3000h]
  __int64 v140; // [rsp+90h] [rbp-2FF8h]
  unsigned int v141; // [rsp+98h] [rbp-2FF0h]
  int v142; // [rsp+9Ch] [rbp-2FECh]
  int v143; // [rsp+A0h] [rbp-2FE8h]
  unsigned __int64 v144; // [rsp+A8h] [rbp-2FE0h]
  unsigned __int64 v145; // [rsp+B0h] [rbp-2FD8h]
  void *v146; // [rsp+B8h] [rbp-2FD0h] BYREF
  __int64 v147; // [rsp+C0h] [rbp-2FC8h]
  void (__fastcall ***v148)(_QWORD, __int64); // [rsp+C8h] [rbp-2FC0h] BYREF
  void (__fastcall ***v149)(_QWORD, __int64); // [rsp+D0h] [rbp-2FB8h] BYREF
  unsigned int v150; // [rsp+D8h] [rbp-2FB0h]
  unsigned int v151; // [rsp+DCh] [rbp-2FACh]
  _DWORD v152[3]; // [rsp+E0h] [rbp-2FA8h] BYREF
  int v153; // [rsp+ECh] [rbp-2F9Ch]
  int v154; // [rsp+F0h] [rbp-2F98h]
  __int64 v155; // [rsp+F8h] [rbp-2F90h]
  __int16 v156; // [rsp+100h] [rbp-2F88h]
  __int16 v157; // [rsp+108h] [rbp-2F80h]
  __int16 v158; // [rsp+110h] [rbp-2F78h]
  __int16 v159; // [rsp+118h] [rbp-2F70h]
  __int16 v160; // [rsp+120h] [rbp-2F68h]
  CSbTransportMgr *v161; // [rsp+128h] [rbp-2F60h] BYREF
  CSbTransportMgr *v162; // [rsp+130h] [rbp-2F58h] BYREF
  CSbTransportMgr *v163; // [rsp+138h] [rbp-2F50h] BYREF
  CSbTransportMgr *v164; // [rsp+140h] [rbp-2F48h] BYREF
  CSbTransportMgr *v165; // [rsp+148h] [rbp-2F40h] BYREF
  CSbTransportMgr *v166; // [rsp+150h] [rbp-2F38h] BYREF
  __int16 v167; // [rsp+158h] [rbp-2F30h]
  __int16 v168; // [rsp+160h] [rbp-2F28h]
  unsigned int v169; // [rsp+168h] [rbp-2F20h]
  __int16 v170; // [rsp+170h] [rbp-2F18h]
  unsigned __int64 v171; // [rsp+178h] [rbp-2F10h] BYREF
  unsigned __int64 v172; // [rsp+180h] [rbp-2F08h] BYREF
  unsigned __int64 v173; // [rsp+188h] [rbp-2F00h] BYREF
  unsigned __int64 v174; // [rsp+190h] [rbp-2EF8h] BYREF
  unsigned __int64 v175; // [rsp+198h] [rbp-2EF0h] BYREF
  __int64 v176; // [rsp+1A0h] [rbp-2EE8h]
  TaskStretchTable *v177; // [rsp+1A8h] [rbp-2EE0h]
  void (__fastcall ***v178)(_QWORD, __int64); // [rsp+1B0h] [rbp-2ED8h]
  __int64 v179; // [rsp+1B8h] [rbp-2ED0h]
  int v180; // [rsp+1C0h] [rbp-2EC8h]
  int v181; // [rsp+1C4h] [rbp-2EC4h]
  int v182; // [rsp+1C8h] [rbp-2EC0h]
  int v183; // [rsp+1CCh] [rbp-2EBCh]
  _BYTE *v184; // [rsp+1D0h] [rbp-2EB8h]
  unsigned __int64 v185; // [rsp+1D8h] [rbp-2EB0h] BYREF
  __m128i si128; // [rsp+1E0h] [rbp-2EA8h] BYREF
  int v187; // [rsp+1F0h] [rbp-2E98h]
  int v188; // [rsp+1F8h] [rbp-2E90h]
  int v189; // [rsp+1FCh] [rbp-2E8Ch]
  int v190; // [rsp+200h] [rbp-2E88h]
  int v191; // [rsp+204h] [rbp-2E84h]
  int v192; // [rsp+208h] [rbp-2E80h]
  int v193; // [rsp+20Ch] [rbp-2E7Ch]
  int v194; // [rsp+210h] [rbp-2E78h]
  int v195; // [rsp+214h] [rbp-2E74h]
  int v196; // [rsp+218h] [rbp-2E70h]
  int v197; // [rsp+21Ch] [rbp-2E6Ch]
  int v198; // [rsp+220h] [rbp-2E68h]
  int v199; // [rsp+224h] [rbp-2E64h]
  int v200; // [rsp+228h] [rbp-2E60h]
  int v201; // [rsp+22Ch] [rbp-2E5Ch]
  int v202; // [rsp+230h] [rbp-2E58h]
  int v203; // [rsp+234h] [rbp-2E54h]
  int v204; // [rsp+238h] [rbp-2E50h]
  int v205; // [rsp+23Ch] [rbp-2E4Ch]
  int v206; // [rsp+240h] [rbp-2E48h]
  int v207; // [rsp+244h] [rbp-2E44h]
  int v208; // [rsp+248h] [rbp-2E40h]
  int v209; // [rsp+24Ch] [rbp-2E3Ch]
  __int64 v210; // [rsp+250h] [rbp-2E38h]
  LARGE_INTEGER PerformanceCount; // [rsp+258h] [rbp-2E30h] BYREF
  __int64 v212; // [rsp+260h] [rbp-2E28h] BYREF
  TaskStretchTable *v213; // [rsp+268h] [rbp-2E20h]
  LARGE_INTEGER v214; // [rsp+270h] [rbp-2E18h] BYREF
  int v215; // [rsp+278h] [rbp-2E10h]
  LARGE_INTEGER v216; // [rsp+280h] [rbp-2E08h] BYREF
  int v217; // [rsp+288h] [rbp-2E00h]
  LARGE_INTEGER v218; // [rsp+290h] [rbp-2DF8h] BYREF
  int v219; // [rsp+298h] [rbp-2DF0h]
  LARGE_INTEGER v220; // [rsp+2A0h] [rbp-2DE8h] BYREF
  LARGE_INTEGER v221; // [rsp+2A8h] [rbp-2DE0h] BYREF
  LARGE_INTEGER v222[3]; // [rsp+2B0h] [rbp-2DD8h] BYREF
  int v223; // [rsp+2C8h] [rbp-2DC0h]
  int v224; // [rsp+2CCh] [rbp-2DBCh]
  __int64 v225; // [rsp+2D0h] [rbp-2DB8h] BYREF
  int v226; // [rsp+2D8h] [rbp-2DB0h]
  __int64 v227; // [rsp+2DCh] [rbp-2DACh]
  int v228; // [rsp+2E4h] [rbp-2DA4h]
  int v229; // [rsp+2E8h] [rbp-2DA0h]
  __int64 v230; // [rsp+2ECh] [rbp-2D9Ch]
  int v231; // [rsp+2F8h] [rbp-2D90h] BYREF
  __int64 v232; // [rsp+300h] [rbp-2D88h]
  __int64 v233; // [rsp+308h] [rbp-2D80h]
  __int64 v234; // [rsp+310h] [rbp-2D78h]
  __int64 v235; // [rsp+318h] [rbp-2D70h]
  CSbTransportMgr **v236; // [rsp+320h] [rbp-2D68h]
  CSbTransportMgr **v237; // [rsp+328h] [rbp-2D60h]
  CSbTransportMgr **v238; // [rsp+330h] [rbp-2D58h]
  unsigned __int64 *v239; // [rsp+338h] [rbp-2D50h]
  __int64 v240; // [rsp+340h] [rbp-2D48h]
  __int64 v241; // [rsp+348h] [rbp-2D40h]
  unsigned __int64 *v242; // [rsp+350h] [rbp-2D38h]
  unsigned __int64 v243; // [rsp+358h] [rbp-2D30h]
  _QWORD *v244; // [rsp+360h] [rbp-2D28h]
  __int64 v245; // [rsp+368h] [rbp-2D20h]
  __int64 v246; // [rsp+370h] [rbp-2D18h]
  __int64 v247; // [rsp+378h] [rbp-2D10h]
  _WORD *v248; // [rsp+380h] [rbp-2D08h]
  _DWORD **v249; // [rsp+388h] [rbp-2D00h]
  void (__fastcall ***v250)(_QWORD, __int64); // [rsp+390h] [rbp-2CF8h]
  _QWORD *v251; // [rsp+398h] [rbp-2CF0h]
  __int64 v252; // [rsp+3A0h] [rbp-2CE8h]
  __int64 v253; // [rsp+3A8h] [rbp-2CE0h]
  __int64 v254; // [rsp+3B0h] [rbp-2CD8h]
  _WORD *v255; // [rsp+3B8h] [rbp-2CD0h]
  _DWORD **v256; // [rsp+3C0h] [rbp-2CC8h]
  void (__fastcall ***v257)(_QWORD, __int64); // [rsp+3C8h] [rbp-2CC0h]
  _WORD *v258; // [rsp+3D0h] [rbp-2CB8h]
  _DWORD **v259; // [rsp+3D8h] [rbp-2CB0h]
  CSbTransportMgr **v260; // [rsp+3E0h] [rbp-2CA8h]
  CSbTransportMgr **v261; // [rsp+3E8h] [rbp-2CA0h]
  CSbTransportMgr **v262; // [rsp+3F0h] [rbp-2C98h]
  unsigned __int64 *v263; // [rsp+3F8h] [rbp-2C90h]
  __int64 v264; // [rsp+400h] [rbp-2C88h]
  __int64 v265; // [rsp+408h] [rbp-2C80h]
  unsigned __int64 *v266; // [rsp+410h] [rbp-2C78h]
  unsigned __int64 v267; // [rsp+418h] [rbp-2C70h]
  _WORD *v268; // [rsp+420h] [rbp-2C68h]
  _DWORD **v269; // [rsp+428h] [rbp-2C60h]
  CSbTransportMgr **v270; // [rsp+430h] [rbp-2C58h]
  CSbTransportMgr **v271; // [rsp+438h] [rbp-2C50h]
  CSbTransportMgr **v272; // [rsp+440h] [rbp-2C48h]
  unsigned __int64 *v273; // [rsp+448h] [rbp-2C40h]
  __int64 v274; // [rsp+450h] [rbp-2C38h]
  __int64 v275; // [rsp+458h] [rbp-2C30h]
  unsigned __int64 *v276; // [rsp+460h] [rbp-2C28h]
  unsigned __int64 v277; // [rsp+468h] [rbp-2C20h]
  void *v278; // [rsp+470h] [rbp-2C18h]
  LARGE_INTEGER *v279; // [rsp+478h] [rbp-2C10h]
  __int64 v280; // [rsp+480h] [rbp-2C08h]
  LARGE_INTEGER v281; // [rsp+488h] [rbp-2C00h]
  struct IMetadataAccess *v282; // [rsp+490h] [rbp-2BF8h]
  __int64 v283; // [rsp+498h] [rbp-2BF0h]
  __int64 v284; // [rsp+4A0h] [rbp-2BE8h]
  wchar_t *v285; // [rsp+4A8h] [rbp-2BE0h]
  _WORD *v286; // [rsp+4B0h] [rbp-2BD8h]
  _DWORD **v287; // [rsp+4B8h] [rbp-2BD0h]
  CSbTransportMgr **v288; // [rsp+4C0h] [rbp-2BC8h]
  CSbTransportMgr **v289; // [rsp+4C8h] [rbp-2BC0h]
  CSbTransportMgr **v290; // [rsp+4D0h] [rbp-2BB8h]
  unsigned __int64 *v291; // [rsp+4D8h] [rbp-2BB0h]
  union _LARGE_INTEGER v292; // [rsp+4E0h] [rbp-2BA8h]
  __int64 v293; // [rsp+4E8h] [rbp-2BA0h]
  __int64 v294; // [rsp+4F0h] [rbp-2B98h]
  unsigned __int64 *v295; // [rsp+4F8h] [rbp-2B90h]
  _WORD *v296; // [rsp+500h] [rbp-2B88h]
  _DWORD **v297; // [rsp+508h] [rbp-2B80h]
  CSbTransportMgr **v298; // [rsp+510h] [rbp-2B78h]
  CSbTransportMgr **v299; // [rsp+518h] [rbp-2B70h]
  CSbTransportMgr **v300; // [rsp+520h] [rbp-2B68h]
  unsigned __int64 *v301; // [rsp+528h] [rbp-2B60h]
  union _LARGE_INTEGER v302; // [rsp+530h] [rbp-2B58h]
  __int64 v303; // [rsp+538h] [rbp-2B50h]
  __int64 v304; // [rsp+540h] [rbp-2B48h]
  unsigned __int64 *v305; // [rsp+548h] [rbp-2B40h]
  _WORD *v306; // [rsp+550h] [rbp-2B38h]
  _DWORD **v307; // [rsp+558h] [rbp-2B30h]
  CSbTransportMgr **v308; // [rsp+560h] [rbp-2B28h]
  CSbTransportMgr **v309; // [rsp+568h] [rbp-2B20h]
  CSbTransportMgr **v310; // [rsp+570h] [rbp-2B18h]
  unsigned __int64 *v311; // [rsp+578h] [rbp-2B10h]
  union _LARGE_INTEGER v312; // [rsp+580h] [rbp-2B08h]
  __int64 v313; // [rsp+588h] [rbp-2B00h]
  __int64 v314; // [rsp+590h] [rbp-2AF8h]
  unsigned __int64 *v315; // [rsp+598h] [rbp-2AF0h]
  _QWORD v316[6]; // [rsp+5A0h] [rbp-2AE8h] BYREF
  _BYTE v317[48]; // [rsp+5D0h] [rbp-2AB8h] BYREF
  __int64 v318; // [rsp+600h] [rbp-2A88h] BYREF
  _WORD v319[4]; // [rsp+608h] [rbp-2A80h] BYREF
  int v320; // [rsp+610h] [rbp-2A78h]
  _DWORD **v321; // [rsp+618h] [rbp-2A70h]
  _DWORD *v322; // [rsp+620h] [rbp-2A68h]
  __int64 v323; // [rsp+628h] [rbp-2A60h]
  _DWORD *v324; // [rsp+630h] [rbp-2A58h] BYREF
  int v325; // [rsp+638h] [rbp-2A50h]
  __int16 v326; // [rsp+63Ch] [rbp-2A4Ch]
  __int16 v327; // [rsp+63Eh] [rbp-2A4Ah]
  _DWORD v328[134]; // [rsp+640h] [rbp-2A48h] BYREF
  __int64 v329; // [rsp+858h] [rbp-2830h]
  _DWORD v330[2]; // [rsp+860h] [rbp-2828h] BYREF
  char v331; // [rsp+868h] [rbp-2820h]
  unsigned __int64 v332; // [rsp+869h] [rbp-281Fh]
  int v333; // [rsp+871h] [rbp-2817h]
  int v334; // [rsp+875h] [rbp-2813h]
  __int64 v335; // [rsp+879h] [rbp-280Fh]
  char v336[8]; // [rsp+890h] [rbp-27F8h] BYREF
  _WORD v337[4]; // [rsp+898h] [rbp-27F0h] BYREF
  int v338; // [rsp+8A0h] [rbp-27E8h]
  _DWORD **v339; // [rsp+8A8h] [rbp-27E0h]
  char *v340; // [rsp+8B0h] [rbp-27D8h]
  __int64 v341; // [rsp+8B8h] [rbp-27D0h]
  _DWORD *v342; // [rsp+8C0h] [rbp-27C8h] BYREF
  int v343; // [rsp+8C8h] [rbp-27C0h]
  __int16 v344; // [rsp+8CCh] [rbp-27BCh]
  __int16 v345; // [rsp+8CEh] [rbp-27BAh]
  char v346; // [rsp+8D0h] [rbp-27B8h] BYREF
  int v347; // [rsp+AE0h] [rbp-25A8h]
  int v348; // [rsp+AE4h] [rbp-25A4h]
  __int64 v349; // [rsp+AE8h] [rbp-25A0h]
  _DWORD v350[2]; // [rsp+AF0h] [rbp-2598h] BYREF
  char v351; // [rsp+AF8h] [rbp-2590h]
  unsigned __int64 v352; // [rsp+AF9h] [rbp-258Fh]
  int v353; // [rsp+B01h] [rbp-2587h]
  int v354; // [rsp+B05h] [rbp-2583h]
  __int64 v355; // [rsp+B09h] [rbp-257Fh]
  char v356[8]; // [rsp+B20h] [rbp-2568h] BYREF
  _WORD v357[4]; // [rsp+B28h] [rbp-2560h] BYREF
  int v358; // [rsp+B30h] [rbp-2558h]
  _DWORD **v359; // [rsp+B38h] [rbp-2550h]
  char *v360; // [rsp+B40h] [rbp-2548h]
  __int64 v361; // [rsp+B48h] [rbp-2540h]
  _DWORD *v362; // [rsp+B50h] [rbp-2538h] BYREF
  int v363; // [rsp+B58h] [rbp-2530h]
  __int16 v364; // [rsp+B5Ch] [rbp-252Ch]
  __int16 v365; // [rsp+B5Eh] [rbp-252Ah]
  char v366; // [rsp+B60h] [rbp-2528h] BYREF
  int v367; // [rsp+D70h] [rbp-2318h]
  int v368; // [rsp+D74h] [rbp-2314h]
  __int64 v369; // [rsp+D78h] [rbp-2310h]
  _DWORD v370[2]; // [rsp+D80h] [rbp-2308h] BYREF
  char v371; // [rsp+D88h] [rbp-2300h]
  unsigned __int64 v372; // [rsp+D89h] [rbp-22FFh]
  int v373; // [rsp+D91h] [rbp-22F7h]
  int v374; // [rsp+D95h] [rbp-22F3h]
  __int64 v375; // [rsp+D99h] [rbp-22EFh]
  char v376[8]; // [rsp+DB0h] [rbp-22D8h] BYREF
  _WORD v377[4]; // [rsp+DB8h] [rbp-22D0h] BYREF
  int v378; // [rsp+DC0h] [rbp-22C8h]
  _DWORD **v379; // [rsp+DC8h] [rbp-22C0h]
  char *v380; // [rsp+DD0h] [rbp-22B8h]
  __int64 v381; // [rsp+DD8h] [rbp-22B0h]
  _DWORD *v382; // [rsp+DE0h] [rbp-22A8h] BYREF
  int v383; // [rsp+DE8h] [rbp-22A0h]
  __int16 v384; // [rsp+DECh] [rbp-229Ch]
  __int16 v385; // [rsp+DEEh] [rbp-229Ah]
  char v386; // [rsp+DF0h] [rbp-2298h] BYREF
  int v387; // [rsp+1000h] [rbp-2088h]
  int v388; // [rsp+1004h] [rbp-2084h]
  __int64 v389; // [rsp+1008h] [rbp-2080h]
  _DWORD v390[2]; // [rsp+1010h] [rbp-2078h] BYREF
  char v391; // [rsp+1018h] [rbp-2070h]
  unsigned __int64 v392; // [rsp+1019h] [rbp-206Fh]
  int v393; // [rsp+1021h] [rbp-2067h]
  int v394; // [rsp+1025h] [rbp-2063h]
  __int64 v395; // [rsp+1029h] [rbp-205Fh]
  __int64 v396; // [rsp+1040h] [rbp-2048h] BYREF
  _WORD v397[4]; // [rsp+1048h] [rbp-2040h] BYREF
  int v398; // [rsp+1050h] [rbp-2038h]
  _DWORD **v399; // [rsp+1058h] [rbp-2030h]
  _DWORD *v400; // [rsp+1060h] [rbp-2028h]
  __int64 v401; // [rsp+1068h] [rbp-2020h]
  _DWORD *v402; // [rsp+1070h] [rbp-2018h] BYREF
  int v403; // [rsp+1078h] [rbp-2010h]
  __int16 v404; // [rsp+107Ch] [rbp-200Ch]
  __int16 v405; // [rsp+107Eh] [rbp-200Ah]
  _DWORD v406[134]; // [rsp+1080h] [rbp-2008h] BYREF
  __int64 v407; // [rsp+1298h] [rbp-1DF0h]
  _DWORD v408[2]; // [rsp+12A0h] [rbp-1DE8h] BYREF
  char v409; // [rsp+12A8h] [rbp-1DE0h]
  unsigned __int64 v410; // [rsp+12A9h] [rbp-1DDFh]
  int v411; // [rsp+12B1h] [rbp-1DD7h]
  int v412; // [rsp+12B5h] [rbp-1DD3h]
  __int64 v413; // [rsp+12B9h] [rbp-1DCFh]
  __int64 v414; // [rsp+12D0h] [rbp-1DB8h] BYREF
  _WORD v415[4]; // [rsp+12D8h] [rbp-1DB0h] BYREF
  int v416; // [rsp+12E0h] [rbp-1DA8h]
  _DWORD **v417; // [rsp+12E8h] [rbp-1DA0h]
  _DWORD *v418; // [rsp+12F0h] [rbp-1D98h]
  __int64 v419; // [rsp+12F8h] [rbp-1D90h]
  _DWORD *v420; // [rsp+1300h] [rbp-1D88h] BYREF
  int v421; // [rsp+1308h] [rbp-1D80h]
  __int16 v422; // [rsp+130Ch] [rbp-1D7Ch]
  __int16 v423; // [rsp+130Eh] [rbp-1D7Ah]
  _DWORD v424[134]; // [rsp+1310h] [rbp-1D78h] BYREF
  __int64 v425; // [rsp+1528h] [rbp-1B60h]
  _DWORD v426[2]; // [rsp+1530h] [rbp-1B58h] BYREF
  char v427; // [rsp+1538h] [rbp-1B50h]
  unsigned __int64 v428; // [rsp+1539h] [rbp-1B4Fh]
  int v429; // [rsp+1541h] [rbp-1B47h]
  int v430; // [rsp+1545h] [rbp-1B43h]
  __int64 v431; // [rsp+1549h] [rbp-1B3Fh]
  char v432[8]; // [rsp+1560h] [rbp-1B28h] BYREF
  _WORD v433[4]; // [rsp+1568h] [rbp-1B20h] BYREF
  int v434; // [rsp+1570h] [rbp-1B18h]
  _DWORD **v435; // [rsp+1578h] [rbp-1B10h]
  char *v436; // [rsp+1580h] [rbp-1B08h]
  __int64 v437; // [rsp+1588h] [rbp-1B00h]
  _DWORD *v438; // [rsp+1590h] [rbp-1AF8h] BYREF
  int v439; // [rsp+1598h] [rbp-1AF0h]
  __int16 v440; // [rsp+159Ch] [rbp-1AECh]
  __int16 v441; // [rsp+159Eh] [rbp-1AEAh]
  char v442; // [rsp+15A0h] [rbp-1AE8h] BYREF
  int v443; // [rsp+17B0h] [rbp-18D8h]
  int v444; // [rsp+17B4h] [rbp-18D4h]
  __int64 v445; // [rsp+17B8h] [rbp-18D0h]
  _DWORD v446[4]; // [rsp+17C0h] [rbp-18C8h] BYREF
  char v447[8]; // [rsp+17D0h] [rbp-18B8h] BYREF
  _WORD v448[4]; // [rsp+17D8h] [rbp-18B0h] BYREF
  int v449; // [rsp+17E0h] [rbp-18A8h]
  _DWORD **v450; // [rsp+17E8h] [rbp-18A0h]
  char *v451; // [rsp+17F0h] [rbp-1898h]
  __int64 v452; // [rsp+17F8h] [rbp-1890h]
  _DWORD *v453; // [rsp+1800h] [rbp-1888h] BYREF
  int v454; // [rsp+1808h] [rbp-1880h]
  __int16 v455; // [rsp+180Ch] [rbp-187Ch]
  __int16 v456; // [rsp+180Eh] [rbp-187Ah]
  char v457; // [rsp+1810h] [rbp-1878h] BYREF
  int v458; // [rsp+1A20h] [rbp-1668h]
  int v459; // [rsp+1A24h] [rbp-1664h]
  __int64 v460; // [rsp+1A28h] [rbp-1660h]
  _DWORD v461[4]; // [rsp+1A30h] [rbp-1658h] BYREF
  char v462[8]; // [rsp+1A40h] [rbp-1648h] BYREF
  int v463; // [rsp+1A48h] [rbp-1640h]
  int v464; // [rsp+1A50h] [rbp-1638h]
  _QWORD *v465; // [rsp+1A58h] [rbp-1630h]
  char *v466; // [rsp+1A60h] [rbp-1628h]
  __int64 v467; // [rsp+1A68h] [rbp-1620h]
  _QWORD v468[2]; // [rsp+1A70h] [rbp-1618h] BYREF
  char v469; // [rsp+1A80h] [rbp-1608h] BYREF
  __int64 v470; // [rsp+1C90h] [rbp-13F8h]
  __int64 v471; // [rsp+1C98h] [rbp-13F0h]
  unsigned int v472; // [rsp+1CA0h] [rbp-13E8h] BYREF
  bool v473; // [rsp+1CA4h] [rbp-13E4h]
  bool v474; // [rsp+1CA5h] [rbp-13E3h]
  bool v475; // [rsp+1CA6h] [rbp-13E2h]
  char v476[8]; // [rsp+1CB0h] [rbp-13D8h] BYREF
  int v477; // [rsp+1CB8h] [rbp-13D0h]
  int v478; // [rsp+1CC0h] [rbp-13C8h]
  _QWORD *v479; // [rsp+1CC8h] [rbp-13C0h]
  char *v480; // [rsp+1CD0h] [rbp-13B8h]
  __int64 v481; // [rsp+1CD8h] [rbp-13B0h]
  _QWORD v482[2]; // [rsp+1CE0h] [rbp-13A8h] BYREF
  char v483; // [rsp+1CF0h] [rbp-1398h] BYREF
  __int64 v484; // [rsp+1F00h] [rbp-1188h]
  __int64 v485; // [rsp+1F08h] [rbp-1180h]
  _DWORD v486[4]; // [rsp+1F10h] [rbp-1178h] BYREF
  char v487[8]; // [rsp+1F20h] [rbp-1168h] BYREF
  int v488; // [rsp+1F28h] [rbp-1160h]
  int v489; // [rsp+1F30h] [rbp-1158h]
  _QWORD *v490; // [rsp+1F38h] [rbp-1150h]
  char *v491; // [rsp+1F40h] [rbp-1148h]
  __int64 v492; // [rsp+1F48h] [rbp-1140h]
  _QWORD v493[2]; // [rsp+1F50h] [rbp-1138h] BYREF
  char v494; // [rsp+1F60h] [rbp-1128h] BYREF
  __int64 v495; // [rsp+2170h] [rbp-F18h]
  __int64 v496; // [rsp+2178h] [rbp-F10h]
  _DWORD v497[4]; // [rsp+2180h] [rbp-F08h] BYREF
  char v498[8]; // [rsp+2190h] [rbp-EF8h] BYREF
  int v499; // [rsp+2198h] [rbp-EF0h]
  int v500; // [rsp+21A0h] [rbp-EE8h]
  _QWORD *v501; // [rsp+21A8h] [rbp-EE0h]
  char *v502; // [rsp+21B0h] [rbp-ED8h]
  __int64 v503; // [rsp+21B8h] [rbp-ED0h]
  _QWORD v504[2]; // [rsp+21C0h] [rbp-EC8h] BYREF
  char v505; // [rsp+21D0h] [rbp-EB8h] BYREF
  __int64 v506; // [rsp+23E0h] [rbp-CA8h]
  __int64 v507; // [rsp+23E8h] [rbp-CA0h]
  _DWORD v508[4]; // [rsp+23F0h] [rbp-C98h] BYREF
  char v509[8]; // [rsp+2400h] [rbp-C88h] BYREF
  int v510; // [rsp+2408h] [rbp-C80h]
  int v511; // [rsp+2410h] [rbp-C78h]
  _QWORD *v512; // [rsp+2418h] [rbp-C70h]
  char *v513; // [rsp+2420h] [rbp-C68h]
  __int64 v514; // [rsp+2428h] [rbp-C60h]
  _QWORD v515[2]; // [rsp+2430h] [rbp-C58h] BYREF
  char v516; // [rsp+2440h] [rbp-C48h] BYREF
  __int64 v517; // [rsp+2650h] [rbp-A38h]
  __int64 v518; // [rsp+2658h] [rbp-A30h]
  _DWORD v519[4]; // [rsp+2660h] [rbp-A28h] BYREF
  char v520[8]; // [rsp+2670h] [rbp-A18h] BYREF
  int v521; // [rsp+2678h] [rbp-A10h]
  int v522; // [rsp+2680h] [rbp-A08h]
  _QWORD *v523; // [rsp+2688h] [rbp-A00h]
  char *v524; // [rsp+2690h] [rbp-9F8h]
  __int64 v525; // [rsp+2698h] [rbp-9F0h]
  _QWORD v526[2]; // [rsp+26A0h] [rbp-9E8h] BYREF
  char v527; // [rsp+26B0h] [rbp-9D8h] BYREF
  __int64 v528; // [rsp+28C0h] [rbp-7C8h]
  __int64 v529; // [rsp+28C8h] [rbp-7C0h]
  _DWORD v530[4]; // [rsp+28D0h] [rbp-7B8h] BYREF
  char v531[8]; // [rsp+28E0h] [rbp-7A8h] BYREF
  int v532; // [rsp+28E8h] [rbp-7A0h]
  int v533; // [rsp+28F0h] [rbp-798h]
  _QWORD *v534; // [rsp+28F8h] [rbp-790h]
  char *v535; // [rsp+2900h] [rbp-788h]
  __int64 v536; // [rsp+2908h] [rbp-780h]
  _QWORD v537[2]; // [rsp+2910h] [rbp-778h] BYREF
  char v538; // [rsp+2920h] [rbp-768h] BYREF
  __int64 v539; // [rsp+2B30h] [rbp-558h]
  __int64 v540; // [rsp+2B38h] [rbp-550h]
  _DWORD v541[4]; // [rsp+2B40h] [rbp-548h] BYREF
  char v542[8]; // [rsp+2B50h] [rbp-538h] BYREF
  int v543; // [rsp+2B58h] [rbp-530h]
  int v544; // [rsp+2B60h] [rbp-528h]
  _QWORD *v545; // [rsp+2B68h] [rbp-520h]
  char *v546; // [rsp+2B70h] [rbp-518h]
  __int64 v547; // [rsp+2B78h] [rbp-510h]
  _QWORD v548[2]; // [rsp+2B80h] [rbp-508h] BYREF
  char v549; // [rsp+2B90h] [rbp-4F8h] BYREF
  __int64 v550; // [rsp+2DA0h] [rbp-2E8h]
  __int64 v551; // [rsp+2DA8h] [rbp-2E0h]
  _DWORD v552[4]; // [rsp+2DB0h] [rbp-2D8h] BYREF
  _BYTE v553[16]; // [rsp+2DC0h] [rbp-2C8h] BYREF
  _BYTE v554[80]; // [rsp+2DD0h] [rbp-2B8h] BYREF
  _BYTE v555[48]; // [rsp+2E20h] [rbp-268h] BYREF
  wchar_t v556[256]; // [rsp+2E50h] [rbp-238h] BYREF

  v280 = -2;
  v139 = this;
  v213 = this;
  v177 = this;
  v179 = 0;
  v134 = 0;
  v151 = 10;
  v169 = 3;
  v132 = 0;
  v130 = 0;
  v127 = 0;
  v125 = 0;
  v2 = *((_DWORD *)this + 8);
  v126 = v2;
  v136 = v2;
  v3 = *((_DWORD *)this + 9);
  v129 = v3;
  DebugTraceStretchSchema(
    L"TaskStretchTable::ProcessTskPkt (%d, %d, %d) start",
    v2,
    v3,
    *((unsigned __int8 *)this + 40));
  if ( !*((_BYTE *)qword_102EF3550 + 1456) )
    return;
  v4 = *((_BYTE *)qword_102ECFB10 + 1300);
  if ( (v4 & 1) != 0 )
    return;
  if ( v4 < 0 )
    return;
  v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  if ( *(_QWORD *)v5 )
  {
    v6 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v5 + 56LL);
    if ( v6 )
    {
      if ( CSessionTraceFlags::CheckSessionTraceInternal(v6, 0x28A7u) )
        return;
    }
  }
  if ( !*(_BYTE *)((*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf)
                 + 1338) )
    return;
  v179 = (**(__int64 (__fastcall ***)(struct IAutoXactFactory *))g_pAutoXactFactory)(g_pAutoXactFactory);
  (*(void (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v179 + 16LL))(v179, L"TaskStretchTable", 32);
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v179 + 72LL))(v179);
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v9 = *(_QWORD *)(v8 + 256);
  if ( !v9 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v9 = *(_QWORD *)(v8 + 256);
  }
  v10 = g_metadataFactory(*(_QWORD *)(v9 + 1000), v7, "sql\\ntdbms\\stretch\\src\\stretchtask.cpp", 2922);
  v178 = (void (__fastcall ***)(_QWORD, __int64))v10;
  v143 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v2 )
  {
    v143 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, int, char, char, char))g_dbtableFactory[5])(
             v11,
             0,
             v2,
             16,
             640,
             1,
             1,
             1);
    if ( v143 )
    {
      v12 = DBMgr::LookupDB(*(DBMgr **)(qword_102ECFB00 + 32), v2);
      v13 = v12;
      v125 = v12
          && (unsigned int)RecoveryUnit::IsUpdateable(*((RecoveryUnit **)v12 + 578))
          && !DBTABLE::IsMarkedReadOnly(v13, 0);
    }
  }
  v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v10 + 56LL))(
          v10,
          v2,
          0,
          0,
          0,
          0);
  v15 = v14;
  v147 = v14;
  if ( v14 )
  {
    v132 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 1680LL))(v14);
    v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 1704LL))(v15);
    v17 = v16;
    v127 = v16;
    v131 = v16;
    if ( v132 )
    {
      if ( v16 )
      {
        if ( v125 )
        {
          v184 = (char *)this + 41;
          *((_BYTE *)this + 41) = 1;
          LockRes::LockRes((LockRes *)v553);
          LockRes::SetDatabaseResource(v553, v2, 21);
          v18 = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          v19 = *v18;
          v20 = DBMgr::LookupDB(*(DBMgr **)(qword_102ECFB00 + 32), v2);
          v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(v19 + 280))(v18, *((_QWORD *)v20 + 578));
          LockRequest::LockRequest((LockRequest *)v554);
          LockRequest::SetTransactionLockState((LockRequest *)v554, (struct XactLockInfo *)(v21 + 56));
          LockRequest::SetTimeout((LockRequest *)v554, 0);
          LOBYTE(v22) = 3;
          LockRequest::SetMode(v554, v22);
          LockRequest::SetClass((LockRequest *)v554, 0x2000000u);
          if ( (dword_102EDCA0C & 0x40000) != 0 )
          {
            v488 = 0x10000;
            v489 = 0;
            v490 = v493;
            v491 = &v494;
            v495 = 0;
            v492 = 0;
            v496 = 0;
            v493[0] = v497;
            v493[1] = 8;
            v497[0] = v2;
            v497[1] = v3;
            XeSqlPkg::stretch_migration_start_wait_for_lock::Publish((XeSqlPkg::stretch_migration_start_wait_for_lock *)v487);
          }
          if ( (int)lck_lock(v554, v553, 0) < 0 )
          {
            DebugTraceStretchSchema(
              L"TaskStretchTable::ProcessTskPkt (%d, %d, %d) failed to acquire shared lock",
              v2,
              v3,
              *((unsigned __int8 *)v139 + 40));
            if ( (dword_102EDCA0C & 0x100000) != 0 )
            {
              v499 = 0x10000;
              v500 = 0;
              v501 = v504;
              v502 = &v505;
              v506 = 0;
              v503 = 0;
              v507 = 0;
              v504[0] = v508;
              v504[1] = 8;
              v508[0] = v2;
              v508[1] = v3;
              XeSqlPkg::stretch_migration_failed_to_acquire_lock::Publish((XeSqlPkg::stretch_migration_failed_to_acquire_lock *)v498);
            }
LABEL_211:
            LockRequest::~LockRequest((LockRequest *)v554);
            goto LABEL_217;
          }
          if ( (dword_102EDCA0C & 0x80000) != 0 )
          {
            v510 = 0x10000;
            v511 = 0;
            v512 = v515;
            v513 = &v516;
            v517 = 0;
            v514 = 0;
            v518 = 0;
            v515[0] = v519;
            v515[1] = 8;
            v519[0] = v2;
            v519[1] = v3;
            XeSqlPkg::stretch_migration_acquired_lock::Publish((XeSqlPkg::stretch_migration_acquired_lock *)v509);
          }
          v23 = v147;
          v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v147 + 144LL))(v147);
          v176 = v24;
          v25 = *(_QWORD *)v24;
          if ( v3 )
          {
            (*(void (__fastcall **)(__int64, _QWORD, __int64))(v25 + 40))(v24, v3, 8277);
            if ( *((_BYTE *)v139 + 40) )
              goto LABEL_33;
            v26 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 72LL))(v24, 0);
          }
          else
          {
            (*(void (__fastcall **)(__int64, __int64))(v25 + 8))(v24, 8277);
            v26 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 72LL))(v24, 0);
          }
          v129 = v26;
          v3 = v26;
          while ( 1 )
          {
LABEL_33:
            LOBYTE(v118) = 1;
            LOBYTE(v115) = 0;
            LOBYTE(v27) = 1;
            v28 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int (*)(int, int, int, int, char *), int, _DWORD, _DWORD))(*(_QWORD *)v23 + 120LL))(
                    v23,
                    v3,
                    v27,
                    0,
                    v115,
                    v118,
                    0,
                    0);
            v155 = v28;
            v142 = 0;
            if ( !v28 )
              goto LABEL_204;
            v137 = 4999;
            v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 120LL))(v28);
            v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 888LL))(v29);
            v138 = v30;
            v133 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 992LL))(v29);
            v128 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 952LL))(v29);
            v31 = 0;
            if ( v128 && !(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v29 + 392LL))(v29, 0) )
            {
              v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v29 + 360LL))(v29, 0, 0);
              if ( v32 )
              {
                while ( 1 )
                {
                  v225 = 0;
                  v227 = 0;
                  v228 = 0;
                  v230 = 1;
                  v229 = -1;
                  v226 = -2;
                  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 40LL))(v32, &v225);
                  if ( (v225 & 0x10000) != 0 )
                    break;
                  v32 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v29 + 360LL))(v29, v32, 0);
                  if ( !v32 )
                    goto LABEL_39;
                }
              }
              else
              {
LABEL_39:
                if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v29 + 728LL))(v29)
                  || (v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 752LL))(v29),
                      LOBYTE(v118) = 1,
                      LOBYTE(v115) = 0,
                      LOBYTE(v34) = 1,
                      (v35 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _DWORD, int, _DWORD, _DWORD))(*(_QWORD *)v147 + 120LL))(
                               v147,
                               v33,
                               v34,
                               0,
                               (_DWORD)v115,
                               v118,
                               0,
                               0)) == 0)
                  || (v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 120LL))(v35)) == 0
                  || ((*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v36 + 16LL))(v36, v555), (v555[35] & 4) == 0) )
                {
                  v31 = 1;
                  v137 = 9999;
                  goto LABEL_45;
                }
              }
              v31 = 0;
            }
LABEL_45:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v155 + 280LL))(v155);
            if ( v30 == 2 && !v128 )
            {
              v210 = 0;
              v37 = (*(__int64 (__fastcall **)(struct IAutoXactFactory *))(*(_QWORD *)g_pAutoXactFactory + 8LL))(g_pAutoXactFactory);
              v210 = v37;
              (*(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v37 + 8LL))(
                v37,
                L"CleanupStretchTableResources",
                56,
                0);
              v38 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 64LL))(v37);
              v39 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              v40 = *(_QWORD *)(v39 + 256);
              if ( !v40 )
              {
                SystemThread::MakeMiniSOSThread(0);
                v40 = *(_QWORD *)(v39 + 256);
              }
              v41 = (struct IMetadataAccess *)g_metadataFactory(
                                                *(_QWORD *)(v40 + 1000),
                                                v38,
                                                "sql\\ntdbms\\stretch\\src\\stretchtask.cpp",
                                                3098);
              v282 = v41;
              v42 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              v43 = *(_QWORD *)(v42 + 256);
              if ( !v43 )
              {
                SystemThread::MakeMiniSOSThread(0);
                v43 = *(_QWORD *)(v42 + 256);
              }
              v2 = v126;
              v44 = IRemoteDbProvisioning::Create(*(struct IMemObj **)(v43 + 1000), v41, v126);
              v316[2] = v44;
              (*(void (__fastcall **)(struct IRemoteDbProvisioning *, _QWORD))(*(_QWORD *)v44 + 80LL))(v44, v3);
              (**(void (__fastcall ***)(struct IRemoteDbProvisioning *, __int64))v44)(v44, 1);
              if ( v41 )
                (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v41)(v41, 1);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 32LL))(v37);
              (**(void (__fastcall ***)(__int64, __int64))v37)(v37, 1);
              goto LABEL_211;
            }
            if ( v133 )
            {
              if ( !v128 )
                utassert_fail(1u, "hasRemoteTarget", "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\stretchtask.cpp\"", 3158, 0);
              v45 = v126;
              DebugTraceStretchSchema(
                L"TaskStretchTable::ProcessTskPkt (%d, %d, %d) Data Reconciliation in Progress",
                v126,
                v3,
                *((unsigned __int8 *)v139 + 40));
              v137 = 0;
            }
            else
            {
              LODWORD(v115) = v30;
              v45 = v126;
              DebugTraceStretchSchema(
                L"TaskStretchTable::ProcessTskPkt (%d, %d, %d) migrationDirection = %d",
                v126,
                v3,
                *((unsigned __int8 *)v139 + 40),
                v115);
              if ( v30 == 1 && (unsigned int)SyncStretchMetadata(v126, v3) != 2 )
              {
                v47 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 72LL))(v24, 0);
                v2 = v126;
LABEL_205:
                v129 = v47;
                v3 = v47;
                goto LABEL_206;
              }
              if ( (*((_BYTE *)qword_102ECFB10 + 1302) & 1) != 0
                || (ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer,
                    v48 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset,
                    *(_QWORD *)v48)
                && (v49 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v48 + 56LL)) != 0
                && CSessionTraceFlags::CheckSessionTraceInternal(v49, 0x28B0u) )
              {
                v137 = 500;
              }
            }
            if ( (unsigned int)(v30 - 1) > 1 && v133 != 1 )
            {
              v2 = v126;
LABEL_204:
              _mm_lfence();
              v47 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 72LL))(v24, 0);
              v134 = 0;
              goto LABEL_205;
            }
            v146 = 0;
            if ( dword_102EDCA0C < 0 )
            {
              v477 = 0x10000;
              v478 = 0;
              v479 = v482;
              v480 = &v483;
              v484 = 0;
              v481 = 0;
              v485 = 0;
              v482[0] = v486;
              v482[1] = 12;
              v486[0] = v45;
              v486[1] = v3;
              v486[2] = v30;
              XeSqlPkg::stretch_migration_batch_generation::Publish((XeSqlPkg::stretch_migration_batch_generation *)v476);
            }
            LOBYTE(v118) = 1;
            LOBYTE(v115) = 0;
            LOBYTE(ThreadLocalStoragePointer) = 1;
            v50 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, _QWORD, _DWORD, int, _DWORD, _DWORD))(*(_QWORD *)v147 + 120LL))(
                    v147,
                    v3,
                    ThreadLocalStoragePointer,
                    0,
                    (_DWORD)v115,
                    v118,
                    0,
                    0);
            v316[3] = v50;
            if ( v50 )
            {
              LOBYTE(v124) = v31;
              LOBYTE(v122) = v133 == 1;
              LODWORD(v115) = v30;
              MigrationBatch = GetMigrationBatch(v178, v147, v50, 20000, v115, &v146, &v212, v122, v124);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 280LL))(v50);
              _mm_lfence();
              if ( MigrationBatch >= 0 )
              {
                if ( !v133 )
                {
                  if ( v30 == 1 )
                  {
                    if ( (dword_102EDCA0C & 0x200000) != 0 )
                    {
                      v521 = 0x10000;
                      v522 = 0;
                      v523 = v526;
                      v524 = &v527;
                      v528 = 0;
                      v525 = 0;
                      v529 = 0;
                      v526[0] = v530;
                      v526[1] = 8;
                      v530[0] = v126;
                      v530[1] = v3;
                      XeSqlPkg::stretch_migration_start_migration::Publish((XeSqlPkg::stretch_migration_start_migration *)v520);
                    }
                  }
                  else if ( v30 == 2 && (dword_102EDCA0C & 0x400000) != 0 )
                  {
                    v532 = 0x10000;
                    v533 = 0;
                    v534 = v537;
                    v535 = &v538;
                    v539 = 0;
                    v536 = 0;
                    v540 = 0;
                    v537[0] = v541;
                    v537[1] = 8;
                    v541[0] = v126;
                    v541[1] = v3;
                    XeSqlPkg::stretch_migration_start_unmigration::Publish((XeSqlPkg::stretch_migration_start_unmigration *)v531);
                  }
                }
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&PerformanceCount);
                  QuadPart = (CSbTransportMgr *)PerformanceCount.QuadPart;
                }
                else
                {
                  QuadPart = MEMORY[0x7FFE0008];
                }
                v135 = QuadPart;
                try
                {
                  ExcHandler::ExcHandler(
                    (ExcHandler *)v317,
                    0,
                    0,
                    0,
                    (int (*)(int, int, int, int, char *))hdl_backout,
                    0);
                  v150 = 0;
                  v60 = 0;
                  v141 = 0;
                  si128 = _mm_load_si128((const __m128i *)&_xmm);
                  v187 = 0;
                  v58 = 0;
                  v59 = 0;
                  v57 = v142;
                  v53 = v137;
                  while ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v147 + 1704LL))(v147) )
                  {
                    LOBYTE(v124) = v58;
                    LOBYTE(v123) = 0;
                    LOBYTE(v121) = v133 == 1;
                    v54 = MigrateStretchData(v126, v129, v53, v146, v212, v138, v121, v123, v124, &si128);
                    v57 = v54;
                    v142 = v54;
                    if ( v54 == -2147483647 )
                    {
                      if ( v59 < v169 )
                      {
                        v58 = 0;
                        v231 = 4194400;
                        v232 = 0;
                        v234 = 0;
                        v233 = 0;
                        v235 = 0;
                        SOS_Task::Sleep(1000, &v231, v55, v56);
                        v150 = ++v59;
                        if ( v138 == 1 && !v133 )
                          v137 = v53;
                        goto LABEL_95;
                      }
                    }
                    else if ( v54 > 0 )
                    {
                      v60 += v54;
                      v141 = v60;
                      if ( v133 != 1 )
                        v58 = 1;
                    }
                    ++v134;
                    v150 = 0;
                    v59 = 0;
                    if ( v54 <= 0 && v54 != -2147483647 )
                    {
LABEL_96:
                      v61 = *((_BYTE *)v213 + 41);
                      v62 = v184;
                      goto LABEL_98;
                    }
LABEL_95:
                    if ( v134 >= v151 )
                      goto LABEL_96;
                  }
                  v62 = v184;
                  *v184 = 0;
                  v61 = 0;
LABEL_98:
                  if ( v133 == 1 )
                  {
                    if ( v57 == -5 )
                      utassert_fail(
                        1u,
                        "x_signalToReconcileDataAsRemoteBehindLocal != rowsMigrated",
                        "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\stretchtask.cpp\"",
                        3346,
                        0);
                    if ( v60 )
                    {
                      v155 = 0x10000000DLL;
                      if ( (qword_102EDCA14 & 1) != 0 )
                      {
                        v170 = 1;
                        v316[4] = v337;
                        v337[0] = 0;
                        v337[1] = 1;
                        v338 = 0;
                        v339 = &v342;
                        v340 = &v346;
                        v347 = 0;
                        v348 = 0;
                        v341 = 0;
                        v349 = 0;
                        v316[5] = &v342;
                        v342 = v350;
                        v343 = 33;
                        v344 = 0;
                        v345 = 0;
                        v350[0] = v126;
                        v350[1] = v129;
                        v351 = 1;
                        v236 = &v161;
                        v217 = Base_PublicGlobals::sm_invariantTscAvailable;
                        if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          QueryPerformanceCounter(&v214);
                          v63 = (CSbTransportMgr *)v214.QuadPart;
                          v161 = (CSbTransportMgr *)v214.QuadPart;
                        }
                        else
                        {
                          v144 = (unsigned __int64)MEMORY[0x7FFE0008];
                          v63 = MEMORY[0x7FFE0008];
                          v161 = MEMORY[0x7FFE0008];
                          v57 = v142;
                          v60 = v141;
                        }
                        v237 = &v135;
                        v238 = &v161;
                        if ( v63 < v135 )
                        {
                          v64 = 0;
                          v144 = 0;
                        }
                        else
                        {
                          v64 = v63 - v135;
                          v144 = v64;
                        }
                        v185 = v64;
                        v239 = &v185;
                        if ( v64 == -1 )
                        {
                          v65 = -1;
                        }
                        else
                        {
                          v219 = Base_PublicGlobals::sm_invariantTscAvailable;
                          if ( Base_PublicGlobals::sm_invariantTscAvailable )
                          {
                            v240 = 1;
                            v223 = 3;
                            v224 = 1000;
                            v241 = 1000;
                            v65 = 1000 * v64 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                          }
                          else
                          {
                            v242 = &v185;
                            v188 = -4;
                            v189 = 10000;
                            v65 = v64 / 0x2710;
                            v243 = v64 / 0x2710;
                          }
                        }
                        v352 = v65;
                        v353 = 0;
                        v354 = 0;
                        v355 = v60;
                        XeSqlPkg::stretch_table_data_reconciliation_results_event::Publish((XeSqlPkg::stretch_table_data_reconciliation_results_event *)v336);
                      }
                    }
                    v66 = si128.m128i_i32[0];
                    if ( v187 != 1 )
                      v66 = si128.m128i_u16[0];
                    if ( !v66 && !v57 && *v62 )
                    {
                      v244 = &v149;
                      v149 = 0;
                      AutoSimpleXact::Begin(
                        (AutoSimpleXact *)&v149,
                        L"SetDataReconciliationStateToNotInProgress",
                        82,
                        0);
                      if ( v149 )
                        v67 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v149)[8])(v149);
                      else
                        v67 = 0;
                      v245 = v67;
                      v68 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset;
                      v69 = *(_QWORD *)(v68 + 256);
                      if ( !v69 )
                      {
                        SystemThread::MakeMiniSOSThread(0);
                        v69 = *(_QWORD *)(v68 + 256);
                      }
                      v70 = g_metadataFactory(
                              *(_QWORD *)(v69 + 1000),
                              v67,
                              "sql\\ntdbms\\stretch\\src\\stretchtask.cpp",
                              3382);
                      v246 = v70;
                      if ( !v70 )
                        ex_raise(148, 19, 16, 51);
                      v71 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v70 + 56LL))(
                              v70,
                              v126,
                              0,
                              0,
                              0,
                              0);
                      if ( !v71 )
                        ex_raise(148, 19, 16, 52);
                      LOBYTE(v119) = 1;
                      LOBYTE(v116) = 0;
                      LOBYTE(v72) = 2;
                      v73 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int, int, _DWORD, _DWORD))(*(_QWORD *)v71 + 120LL))(
                              v71,
                              v129,
                              v72,
                              0,
                              v116,
                              v119,
                              0,
                              0);
                      if ( !v73 )
                        ex_raise(148, 19, 16, 53);
                      v74 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v73 + 120LL))(v73);
                      if ( !v74 )
                        ex_raise(148, 19, 16, 54);
                      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v74 + 952LL))(v74) )
                      {
                        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v74 + 1000LL))(v74, 0);
                        if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v74 + 992LL))(v74) )
                        {
                          v75 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v74 + 648LL))(v74);
                          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v75 + 728LL))(v75, 0);
                        }
                      }
                      v247 = v70;
                      (**(void (__fastcall ***)(__int64, __int64))v70)(v70, 1);
                      ((void (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v149)[4])(v149);
                      v144 = 0x10000000000000BLL;
                      if ( (dword_102EDCA0C & 0x1000000) != 0 )
                      {
                        v156 = 1;
                        v248 = v433;
                        v433[0] = 0;
                        v433[1] = 1;
                        v434 = 0;
                        v435 = &v438;
                        v436 = &v442;
                        v443 = 0;
                        v444 = 0;
                        v437 = 0;
                        v445 = 0;
                        v249 = &v438;
                        v438 = v446;
                        v439 = 8;
                        v440 = 0;
                        v441 = 0;
                        v446[0] = v126;
                        v446[1] = v129;
                        XeSqlPkg::stretch_table_complete_data_reconciliation::Publish((XeSqlPkg::stretch_table_complete_data_reconciliation *)v432);
                      }
                      v76 = v149;
                      v250 = v149;
                      goto LABEL_139;
                    }
                    goto LABEL_141;
                  }
                  if ( v57 == -5 && v61 )
                  {
                    if ( v133 )
                      utassert_fail(
                        1u,
                        "x_srt_Remote_Data_Reconciliation_Not_In_Progress == remoteDataReconciliationState",
                        "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\stretchtask.cpp\"",
                        3459,
                        0);
                    v251 = &v148;
                    v148 = 0;
                    AutoSimpleXact::Begin((AutoSimpleXact *)&v148, L"SetDataReconciliationStateToInProgress", 76, 0);
                    if ( v148 )
                      v79 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v148)[8])(v148);
                    else
                      v79 = 0;
                    v252 = v79;
                    v80 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset;
                    v81 = *(_QWORD *)(v80 + 256);
                    if ( !v81 )
                    {
                      SystemThread::MakeMiniSOSThread(0);
                      v81 = *(_QWORD *)(v80 + 256);
                    }
                    v82 = g_metadataFactory(
                            *(_QWORD *)(v81 + 1000),
                            v79,
                            "sql\\ntdbms\\stretch\\src\\stretchtask.cpp",
                            3472);
                    v253 = v82;
                    if ( !v82 )
                      ex_raise(148, 19, 16, 57);
                    v83 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v82 + 56LL))(
                            v82,
                            v126,
                            0,
                            0,
                            0,
                            0);
                    if ( !v83 )
                      ex_raise(148, 19, 16, 58);
                    LOBYTE(v120) = 1;
                    LOBYTE(v117) = 0;
                    LOBYTE(v84) = 2;
                    v85 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int, int, _DWORD, _DWORD))(*(_QWORD *)v83 + 120LL))(
                            v83,
                            v129,
                            v84,
                            0,
                            v117,
                            v120,
                            0,
                            0);
                    if ( !v85 )
                      ex_raise(148, 19, 16, 59);
                    v86 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v85 + 120LL))(v85);
                    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v86 + 952LL))(v86) )
                      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v86 + 1000LL))(v86, 1);
                    v254 = v82;
                    (**(void (__fastcall ***)(__int64, __int64))v82)(v82, 1);
                    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v148)[4])(v148);
                    v180 = 11;
                    v181 = 0x800000;
                    if ( (dword_102EDCA0C & 0x800000) != 0 )
                    {
                      v157 = 1;
                      v255 = v448;
                      v448[0] = 0;
                      v448[1] = 1;
                      v449 = 0;
                      v450 = &v453;
                      v451 = &v457;
                      v458 = 0;
                      v459 = 0;
                      v452 = 0;
                      v460 = 0;
                      v256 = &v453;
                      v453 = v461;
                      v454 = 8;
                      v455 = 0;
                      v456 = 0;
                      v461[0] = v126;
                      v461[1] = v129;
                      XeSqlPkg::stretch_table_start_data_reconciliation::Publish((XeSqlPkg::stretch_table_start_data_reconciliation *)v447);
                    }
                    v76 = v148;
                    v257 = v148;
LABEL_139:
                    if ( v76 )
                      (**v76)(v76, 1);
LABEL_141:
                    v2 = v126;
                  }
                  else if ( v60 && v138 == 1 )
                  {
                    v182 = 12;
                    v183 = 0x40000000;
                    v2 = v126;
                    if ( (dword_102EDCA10 & 0x40000000) != 0 )
                    {
                      v158 = 1;
                      v258 = v357;
                      v357[0] = 0;
                      v357[1] = 1;
                      v358 = 0;
                      v359 = &v362;
                      v360 = &v366;
                      v367 = 0;
                      v368 = 0;
                      v361 = 0;
                      v369 = 0;
                      v259 = &v362;
                      v362 = v370;
                      v363 = 33;
                      v364 = 0;
                      v365 = 0;
                      v370[0] = v126;
                      v370[1] = v129;
                      v371 = 1;
                      v260 = &v162;
                      v190 = Base_PublicGlobals::sm_invariantTscAvailable;
                      if ( Base_PublicGlobals::sm_invariantTscAvailable )
                      {
                        QueryPerformanceCounter(&v216);
                        v87 = (CSbTransportMgr *)v216.QuadPart;
                        v162 = (CSbTransportMgr *)v216.QuadPart;
                      }
                      else
                      {
                        v145 = (unsigned __int64)MEMORY[0x7FFE0008];
                        v87 = MEMORY[0x7FFE0008];
                        v162 = MEMORY[0x7FFE0008];
                        v60 = v141;
                      }
                      v261 = &v135;
                      v262 = &v162;
                      if ( v87 < v135 )
                      {
                        v88 = 0;
                        v145 = 0;
                      }
                      else
                      {
                        v88 = v87 - v135;
                        v145 = v88;
                      }
                      v171 = v88;
                      v263 = &v171;
                      if ( v88 == -1 )
                      {
                        v89 = -1;
                      }
                      else
                      {
                        v192 = Base_PublicGlobals::sm_invariantTscAvailable;
                        if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          v264 = 1;
                          v193 = 3;
                          v194 = 1000;
                          v265 = 1000;
                          v89 = 1000 * v88 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                        }
                        else
                        {
                          v266 = &v171;
                          v206 = -4;
                          v195 = 10000;
                          v89 = v88 / 0x2710;
                          v267 = v88 / 0x2710;
                        }
                      }
                      v372 = v89;
                      v373 = 0;
                      v374 = 0;
                      v375 = v60;
                      XeSqlPkg::stretch_table_row_migration_results_event::Publish((XeSqlPkg::stretch_table_row_migration_results_event *)v356);
                    }
                  }
                  else
                  {
                    if ( v57 != -4 && !v60 )
                      goto LABEL_141;
                    if ( v138 != 2 )
                      goto LABEL_141;
                    v145 = 0x800000000000000CuLL;
                    if ( dword_102EDCA10 >= 0 )
                      goto LABEL_141;
                    v159 = 1;
                    v268 = v377;
                    v377[0] = 0;
                    v377[1] = 1;
                    v378 = 0;
                    v379 = &v382;
                    v380 = &v386;
                    v387 = 0;
                    v388 = 0;
                    v381 = 0;
                    v389 = 0;
                    v269 = &v382;
                    v382 = v390;
                    v383 = 33;
                    v384 = 0;
                    v385 = 0;
                    v2 = v126;
                    v390[0] = v126;
                    v390[1] = v129;
                    v391 = 1;
                    v270 = &v163;
                    v196 = Base_PublicGlobals::sm_invariantTscAvailable;
                    if ( Base_PublicGlobals::sm_invariantTscAvailable )
                    {
                      QueryPerformanceCounter(&v218);
                      v90 = (CSbTransportMgr *)v218.QuadPart;
                      v163 = (CSbTransportMgr *)v218.QuadPart;
                    }
                    else
                    {
                      v140 = (__int64)MEMORY[0x7FFE0008];
                      v90 = MEMORY[0x7FFE0008];
                      v163 = MEMORY[0x7FFE0008];
                      v60 = v141;
                    }
                    v271 = &v135;
                    v272 = &v163;
                    if ( v90 < v135 )
                    {
                      v91 = 0;
                      v140 = 0;
                    }
                    else
                    {
                      v91 = v90 - v135;
                      v140 = v91;
                    }
                    v172 = v91;
                    v273 = &v172;
                    if ( v91 == -1 )
                    {
                      v92 = -1;
                    }
                    else
                    {
                      v197 = Base_PublicGlobals::sm_invariantTscAvailable;
                      if ( Base_PublicGlobals::sm_invariantTscAvailable )
                      {
                        v274 = 1;
                        v198 = 3;
                        v199 = 1000;
                        v275 = 1000;
                        v92 = 1000 * v91 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                      }
                      else
                      {
                        v276 = &v172;
                        v200 = -4;
                        v201 = 10000;
                        v92 = v91 / 0x2710;
                        v277 = v91 / 0x2710;
                      }
                    }
                    v392 = v92;
                    v393 = 0;
                    v394 = 0;
                    v395 = v60;
                    XeSqlPkg::stretch_table_row_unmigration_results_event::Publish((XeSqlPkg::stretch_table_row_unmigration_results_event *)v376);
                  }
                  ExcHandler::~ExcHandler((ExcHandler *)v317);
                }
                catch ( SQLError v152 )
                {
                  try
                  {
                    ExceptionBackout::ExceptionBackout((ExceptionBackout *)v316, (const struct SQLError *)v152);
                    v98 = v152[0];
                    if ( v152[0] / 100 == 29 )
                    {
                      if ( v152[0] == 2905 )
                      {
                        v283 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset;
                        v284 = *(_QWORD *)(v283 + 80);
                        scierrlog(0x439Cu, L"StretchTableTask", (unsigned int)*(__int16 *)(v284 + 72));
                      }
                      else
                      {
                        if ( v154 != 1 )
                          v98 = LOWORD(v152[0]);
                        DefaultLocale = GetDefaultLocale();
                        LODWORD(v114) = v98;
                        if ( (int)StringCchPrintf_lW(v556, 0x100u, L"Exception %d", DefaultLocale, v114) < 0 )
                          utassert_fail(
                            1u,
                            "SUCCEEDED(hr)",
                            "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\stretchtask.cpp\"",
                            3599,
                            0);
                        v285 = v556;
                        scierrlog(0x429Du, L"StretchTableTask", v556);
                      }
LABEL_252:
                      v130 = 1;
                    }
                    else
                    {
                      v279 = (LARGE_INTEGER *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                               + SystemThread_TlsIndex)
                                             + SystemThread_TlsOffset);
                      v99 = *v279;
                      v222[1] = v99;
                      v281 = v99;
                      if ( v99.QuadPart )
                      {
                        v222[2] = v99;
                        if ( *(_BYTE *)(*(_QWORD *)(v99.QuadPart + 56) + 8LL) )
                          goto LABEL_252;
                      }
                    }
                    if ( v133 == 1 )
                    {
                      v140 = 0x10000000DLL;
                      if ( (qword_102EDCA14 & 1) != 0 )
                      {
                        v168 = 1;
                        v286 = v397;
                        v397[0] = 0;
                        v397[1] = 1;
                        v398 = 0;
                        v399 = &v402;
                        v400 = v406;
                        v406[132] = 0;
                        v406[133] = 0;
                        v401 = 0;
                        v407 = 0;
                        v287 = &v402;
                        v402 = v408;
                        v403 = 33;
                        v404 = 0;
                        v405 = 0;
                        v408[0] = v136;
                        v408[1] = v129;
                        v409 = 0;
                        v288 = &v164;
                        if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          QueryPerformanceCounter(&v220);
                          v102 = (CSbTransportMgr *)v220.QuadPart;
                          v164 = (CSbTransportMgr *)v220.QuadPart;
                        }
                        else
                        {
                          v102 = MEMORY[0x7FFE0008];
                          v164 = MEMORY[0x7FFE0008];
                        }
                        v289 = &v135;
                        v290 = &v164;
                        if ( v102 < v135 )
                        {
                          v103 = 0;
                          v140 = 0;
                        }
                        else
                        {
                          v103 = v102 - v135;
                          v140 = v103;
                        }
                        v173 = v103;
                        v291 = &v173;
                        if ( v103 == -1 )
                        {
                          v104 = -1;
                        }
                        else if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          v292 = Base_PublicGlobals::sm_QueryPerformanceFrequency;
                          v293 = 1;
                          v202 = 3;
                          v203 = 1000;
                          v294 = 1000;
                          v104 = 1000 * v103 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                        }
                        else
                        {
                          v295 = &v173;
                          v204 = -4;
                          v205 = 10000;
                          v104 = v103 / 0x2710;
                        }
                        v410 = v104;
                        if ( v154 == 1 )
                          v105 = v152[0];
                        else
                          v105 = LOWORD(v152[0]);
                        v411 = v105;
                        v412 = v153;
                        v413 = 0;
                        XeSqlPkg::stretch_table_data_reconciliation_results_event::Publish((XeSqlPkg::stretch_table_data_reconciliation_results_event *)&v396);
                      }
                    }
                    else if ( v138 == 1 )
                    {
                      v145 = 0x400000000000000CLL;
                      if ( (dword_102EDCA10 & 0x40000000) != 0 )
                      {
                        v160 = 1;
                        v296 = v415;
                        v415[0] = 0;
                        v415[1] = 1;
                        v416 = 0;
                        v417 = &v420;
                        v418 = v424;
                        v424[132] = 0;
                        v424[133] = 0;
                        v419 = 0;
                        v425 = 0;
                        v297 = &v420;
                        v420 = v426;
                        v421 = 33;
                        v422 = 0;
                        v423 = 0;
                        v426[0] = v136;
                        v426[1] = v129;
                        v427 = 0;
                        v298 = &v165;
                        if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          QueryPerformanceCounter(&v221);
                          v106 = (CSbTransportMgr *)v221.QuadPart;
                          v165 = (CSbTransportMgr *)v221.QuadPart;
                        }
                        else
                        {
                          v106 = MEMORY[0x7FFE0008];
                          v165 = MEMORY[0x7FFE0008];
                        }
                        v299 = &v135;
                        v300 = &v165;
                        if ( v106 < v135 )
                        {
                          v107 = 0;
                          v140 = 0;
                        }
                        else
                        {
                          v107 = v106 - v135;
                          v140 = v107;
                        }
                        v174 = v107;
                        v301 = &v174;
                        if ( v107 == -1 )
                        {
                          v108 = -1;
                        }
                        else if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          v302 = Base_PublicGlobals::sm_QueryPerformanceFrequency;
                          v303 = 1;
                          v191 = 3;
                          v207 = 1000;
                          v304 = 1000;
                          v108 = 1000 * v107 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                        }
                        else
                        {
                          v305 = &v174;
                          v208 = -4;
                          v209 = 10000;
                          v108 = v107 / 0x2710;
                        }
                        v428 = v108;
                        if ( v154 == 1 )
                          v109 = v152[0];
                        else
                          v109 = LOWORD(v152[0]);
                        v429 = v109;
                        v430 = v153;
                        v431 = 0;
                        XeSqlPkg::stretch_table_row_migration_results_event::Publish((XeSqlPkg::stretch_table_row_migration_results_event *)&v414);
                      }
                    }
                    else if ( v138 == 2 )
                    {
                      v144 = 0x800000000000000CuLL;
                      if ( dword_102EDCA10 < 0 )
                      {
                        v167 = 1;
                        v306 = v319;
                        v319[0] = 0;
                        v319[1] = 1;
                        v320 = 0;
                        v321 = &v324;
                        v322 = v328;
                        v328[132] = 0;
                        v328[133] = 0;
                        v323 = 0;
                        v329 = 0;
                        v307 = &v324;
                        v324 = v330;
                        v325 = 33;
                        v326 = 0;
                        v327 = 0;
                        v330[0] = v136;
                        v330[1] = v129;
                        v331 = 0;
                        v308 = &v166;
                        if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          QueryPerformanceCounter(v222);
                          v110 = (CSbTransportMgr *)v222[0].QuadPart;
                          v166 = (CSbTransportMgr *)v222[0].QuadPart;
                        }
                        else
                        {
                          v110 = MEMORY[0x7FFE0008];
                          v166 = MEMORY[0x7FFE0008];
                        }
                        v309 = &v135;
                        v310 = &v166;
                        if ( v110 < v135 )
                        {
                          v111 = 0;
                          v140 = 0;
                        }
                        else
                        {
                          v111 = v110 - v135;
                          v140 = v111;
                        }
                        v175 = v111;
                        v311 = &v175;
                        if ( v111 == -1 )
                        {
                          v112 = -1;
                        }
                        else if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          v312 = Base_PublicGlobals::sm_QueryPerformanceFrequency;
                          v313 = 1;
                          v215 = 3;
                          v182 = 1000;
                          v314 = 1000;
                          v112 = 1000 * v111 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                        }
                        else
                        {
                          v315 = &v175;
                          v180 = -4;
                          LODWORD(v155) = 10000;
                          v112 = v111 / 0x2710;
                        }
                        v332 = v112;
                        if ( v154 == 1 )
                          v113 = v152[0];
                        else
                          v113 = LOWORD(v152[0]);
                        v333 = v113;
                        v334 = v153;
                        v335 = 0;
                        XeSqlPkg::stretch_table_row_unmigration_results_event::Publish((XeSqlPkg::stretch_table_row_unmigration_results_event *)&v318);
                      }
                    }
                    ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v316);
                  }
                  catch ( ShortStackException )
                  {
                  }
                  v77 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset;
                  v78 = *(struct Worker **)(v77 + 256);
                  if ( !v78 )
                  {
                    SystemThread::MakeMiniSOSThread(0);
                    v78 = *(struct Worker **)(v77 + 256);
                  }
                  if ( *((_DWORD *)v78 + 139) )
                    ExceptionPostCatchActions(v78);
                  operator delete[](v146);
                  if ( v142 > 0 || v142 == -5 )
                  {
                    v127 = v131;
                    v2 = v136;
                    v126 = v136;
                    v3 = v129;
                    v24 = v176;
                    v93 = v177;
                    v139 = v177;
                    goto LABEL_207;
                  }
                  v127 = v131;
                  v2 = v136;
                  v126 = v136;
                  v24 = v176;
                  v139 = v177;
                  goto LABEL_204;
                }
                v278 = v146;
                operator delete[](v146);
                v3 = v129;
                goto LABEL_211;
              }
            }
            v3 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 72LL))(v24, 0);
            v129 = v3;
            operator delete[](v146);
            v2 = v126;
LABEL_206:
            v93 = v139;
LABEL_207:
            if ( v3 )
            {
              if ( v134 < v151 && !v130 )
              {
                v23 = v147;
                if ( *((_BYTE *)v93 + 41) )
                  continue;
              }
            }
            goto LABEL_211;
          }
        }
        goto LABEL_215;
      }
    }
    else
    {
      DebugTraceStretchSchema(
        L"TaskStretchTable::ProcessTskPkt (%d, %d, %d) no tables stretched",
        v2,
        v3,
        *((unsigned __int8 *)this + 40));
      if ( v17 )
        goto LABEL_214;
    }
    DebugTraceStretchSchema(
      L"TaskStretchTable::ProcessTskPkt (%d, %d, %d) the stretch remote is not connected",
      v2,
      v3,
      *((unsigned __int8 *)this + 40));
LABEL_214:
    if ( v125 )
    {
LABEL_216:
      v3 = 0;
      goto LABEL_217;
    }
LABEL_215:
    DebugTraceStretchSchema(
      L"TaskStretchTable::ProcessTskPkt (%d, %d, %d) the local database is not updateable",
      v2,
      v3,
      *((unsigned __int8 *)this + 40));
    goto LABEL_216;
  }
LABEL_217:
  if ( v143 )
  {
    v143 = 0;
    ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
  }
  v94 = v139;
  *((_BYTE *)v139 + 40) = v134 != 0;
  if ( *((_BYTE *)v94 + 41) )
  {
    v95 = g_dbtableFactory[4](v2);
    v96 = (DBTABLE *)v95;
    v97 = v95
       && (unsigned int)RecoveryUnit::IsUpdateable(*(RecoveryUnit **)(v95 + 4624))
       && !DBTABLE::IsMarkedReadOnly(v96, 0);
  }
  else
  {
    v97 = v125;
  }
  if ( *((_BYTE *)v94 + 41) && v97 )
  {
    if ( (dword_102EDCA0C & 0x2000) != 0 )
    {
      v543 = 0x10000;
      v544 = 0;
      v545 = v548;
      v546 = &v549;
      v550 = 0;
      v547 = 0;
      v551 = 0;
      v548[0] = v552;
      v548[1] = 8;
      v552[0] = v2;
      v552[1] = v3;
      XeSqlPkg::stretch_migration_requeue_migration::Publish((XeSqlPkg::stretch_migration_requeue_migration *)v542);
    }
    DebugTraceStretchSchema(L"EnqueueNextStretchObject (%d, %d, %d)", v2, v3, 0);
    TaskStretchTable::Enqueue((unsigned __int16)v2, v3, 0);
  }
  else if ( (dword_102EDCA0C & 0x4000) != 0 )
  {
    v463 = 0x10000;
    v464 = 0;
    v465 = v468;
    v466 = &v469;
    v470 = 0;
    v467 = 0;
    v471 = 0;
    v468[0] = &v472;
    v468[1] = 7;
    v472 = v2;
    v473 = !v97;
    v474 = v132 == 0;
    v475 = v127 == 0;
    XeSqlPkg::stretch_migration_dequeue_migration::Publish((XeSqlPkg::stretch_migration_dequeue_migration *)v462);
  }
  if ( v178 )
    (**v178)(v178, 1);
  if ( v179 )
    (**(void (__fastcall ***)(__int64, __int64))v179)(v179, 1);
}

```

## disassembly

```asm
0x101e80e00  push    rdi
0x101e80e02  push    r12
0x101e80e04  push    r13
0x101e80e06  push    r14
0x101e80e08  push    r15
0x101e80e0a  mov     eax, 3060h
0x101e80e0f  call    _alloca_probe
0x101e80e14  sub     rsp, rax
0x101e80e17  mov     [rsp+3088h+var_2C08], 0FFFFFFFFFFFFFFFEh
0x101e80e23  mov     [rsp+3088h+arg_8], rbx
0x101e80e2b  mov     [rsp+3088h+arg_10], rsi
0x101e80e33  mov     rax, cs:__security_cookie
0x101e80e3a  xor     rax, rsp
0x101e80e3d  mov     [rsp+3088h+var_38], rax
0x101e80e45  mov     r15, rcx
0x101e80e48  mov     [rsp+3088h+var_3000], rcx
0x101e80e50  mov     [rsp+3088h+var_2E20], rcx
0x101e80e58  mov     [rsp+3088h+var_2EE0], rcx
0x101e80e60  xor     ebx, ebx
0x101e80e62  mov     [rsp+3088h+var_2ED0], rbx
0x101e80e6a  mov     [rsp+3088h+var_3020], ebx
0x101e80e6e  mov     [rsp+3088h+var_2FAC], 0Ah
0x101e80e79  mov     [rsp+3088h+var_2F20], 3
0x101e80e84  mov     [rsp+3088h+var_3025], bl
0x101e80e88  mov     [rsp+3088h+var_3028], bl
0x101e80e8c  mov     [rsp+3088h+var_3030], bl
0x101e80e90  xor     al, al
0x101e80e92  mov     [rsp+3088h+var_3038], al
0x101e80e96  mov     r13d, [rcx+20h]
0x101e80e9a  mov     [rsp+3088h+var_3034], r13d
0x101e80e9f  mov     [rsp+3088h+var_3010], r13d
0x101e80ea4  mov     r12d, [rcx+24h]
0x101e80ea8  mov     [rsp+3088h+var_302C], r12d
0x101e80ead  movzx   r9d, byte ptr [rcx+28h]
0x101e80eb2  mov     r8d, r12d
0x101e80eb5  mov     edx, r13d
0x101e80eb8  lea     rcx, aTaskstretchtab_5; "TaskStretchTable::ProcessTskPkt (%d, %d"...
0x101e80ebf  call    ?DebugTraceStretchSchema@@YAXPEB_WZZ; DebugTraceStretchSchema(wchar_t const *,...)
0x101e80ec4  mov     rax, cs:qword_102EF3550
0x101e80ecb  cmp     [rax+5B0h], bl
0x101e80ed1  jz      loc_101E82F62
0x101e80ed7  mov     rax, cs:qword_102ECFB10
0x101e80ede  movzx   ecx, byte ptr [rax+514h]
0x101e80ee5  test    cl, 1
0x101e80ee8  jnz     loc_101E82F62
0x101e80eee  test    cl, cl
0x101e80ef0  js      loc_101E82F62
0x101e80ef6  mov     r8, gs:58h
0x101e80eff  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101e80f06  mov     ecx, [rax]
0x101e80f08  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101e80f0f  mov     edx, [rax]
0x101e80f11  add     rdx, [r8+rcx*8]
0x101e80f15  mov     rax, [rdx]
0x101e80f18  test    rax, rax
0x101e80f1b  jz      short loc_101E80F3C
0x101e80f1d  mov     rax, [rax+38h]
0x101e80f21  mov     rcx, [rax]
0x101e80f24  test    rcx, rcx
0x101e80f27  jz      short loc_101E80F3C
0x101e80f29  mov     edx, 28A7h
0x101e80f2e  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x101e80f34  test    eax, eax
0x101e80f36  jnz     loc_101E82F62
0x101e80f3c  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x101e80f43  mov     rcx, [rax]
0x101e80f46  mov     rax, [rcx]
0x101e80f49  call    qword ptr [rax+1F8h]
0x101e80f4f  cmp     byte ptr [rax+53Ah], 0
0x101e80f56  jz      loc_101E82F62
0x101e80f5c  mov     rax, cs:__imp_?g_pAutoXactFactory@@3PEAVIAutoXactFactory@@EA; IAutoXactFactory * g_pAutoXactFactory
0x101e80f63  mov     rcx, [rax]
0x101e80f66  mov     rax, [rcx]
0x101e80f69  call    qword ptr [rax]
0x101e80f6b  mov     rdi, rax
0x101e80f6e  mov     [rsp+3088h+var_2ED0], rax
0x101e80f76  mov     r10, [rax]
0x101e80f79  xor     r9d, r9d
0x101e80f7c  lea     r8d, [r9+20h]
0x101e80f80  lea     rdx, aTaskstretchtab_1; "TaskStretchTable"
0x101e80f87  mov     rcx, rax
0x101e80f8a  call    qword ptr [r10+10h]
0x101e80f8e  mov     rdx, [rdi]
0x101e80f91  mov     rcx, rdi
0x101e80f94  call    qword ptr [rdx+48h]
0x101e80f97  mov     rsi, rax
0x101e80f9a  mov     rdx, gs:58h
0x101e80fa3  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101e80faa  mov     ecx, [rax]
0x101e80fac  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101e80fb3  mov     edi, [rax]
0x101e80fb5  add     rdi, [rdx+rcx*8]
0x101e80fb9  mov     rcx, [rdi+100h]
0x101e80fc0  test    rcx, rcx
0x101e80fc3  jnz     short loc_101E80FD2
0x101e80fc5  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101e80fcb  mov     rcx, [rdi+100h]
0x101e80fd2  mov     r9d, 0B6Ah
0x101e80fd8  lea     r8, aSqlNtdbmsStret_12; "sql\\ntdbms\\stretch\\src\\stretchtask."...
0x101e80fdf  mov     rdx, rsi
0x101e80fe2  mov     rcx, [rcx+3E8h]
0x101e80fe9  mov     rax, cs:__imp_?g_metadataFactory@@3UMetadataFactory@@A; MetadataFactory g_metadataFactory
0x101e80ff0  call    qword ptr [rax]
0x101e80ff2  mov     rsi, rax
0x101e80ff5  mov     [rsp+3088h+var_2ED8], rax
0x101e80ffd  mov     [rsp+3088h+var_2FE8], ebx
0x101e81004  mov     rdx, [rax]
0x101e81007  mov     rcx, rax
0x101e8100a  call    qword ptr [rdx+10h]
0x101e8100d  test    r13d, r13d
0x101e81010  jz      loc_101E81098
0x101e81016  mov     byte ptr [rsp+3088h+var_3050], 1
0x101e8101b  mov     byte ptr [rsp+3088h+var_3058], 1
0x101e81020  mov     byte ptr [rsp+3088h+var_3060], 1
0x101e81025  mov     dword ptr [rsp+3088h+var_3068], 280h
0x101e8102d  mov     r9d, 10h
0x101e81033  mov     r8d, r13d
0x101e81036  xor     edx, edx
0x101e81038  mov     rcx, rax
0x101e8103b  mov     rax, cs:__imp_?g_dbtableFactory@@3UDBTableFactory@@A; DBTableFactory g_dbtableFactory
0x101e81042  call    qword ptr [rax+28h]
0x101e81045  mov     [rsp+3088h+var_2FE8], eax
0x101e8104c  test    eax, eax
0x101e8104e  jz      short loc_101E81098
0x101e81050  mov     edx, r13d
0x101e81053  mov     rcx, cs:qword_102ECFB00
0x101e8105a  mov     rcx, [rcx+20h]
0x101e8105e  call    cs:__imp_?LookupDB@DBMgr@@QEBAPEAVDBTABLE@@K@Z; DBMgr::LookupDB(ulong)
0x101e81064  mov     rdi, rax
0x101e81067  test    rax, rax
0x101e8106a  jz      short loc_101E81092
0x101e8106c  mov     rcx, [rax+1210h]; this
0x101e81073  call    ?IsUpdateable@RecoveryUnit@@QEBAHXZ; RecoveryUnit::IsUpdateable(void)
0x101e81078  test    eax, eax
0x101e8107a  jz      short loc_101E81092
0x101e8107c  xor     edx, edx
0x101e8107e  mov     rcx, rdi
0x101e81081  call    cs:__imp_?IsMarkedReadOnly@DBTABLE@@QEBA_N_N@Z; DBTABLE::IsMarkedReadOnly(bool)
0x101e81087  test    al, al
0x101e81089  jnz     short loc_101E81092
0x101e8108b  mov     [rsp+3088h+var_3038], 1
0x101e81090  jmp     short loc_101E81098
0x101e81092  xor     al, al
0x101e81094  mov     [rsp+3088h+var_3038], al
0x101e81098  mov     rax, [rsi]
0x101e8109b  mov     dword ptr [rsp+3088h+var_3060], ebx
0x101e8109f  mov     dword ptr [rsp+3088h+var_3068], ebx
0x101e810a3  xor     r9d, r9d
0x101e810a6  xor     r8d, r8d
0x101e810a9  mov     edx, r13d
0x101e810ac  mov     rcx, rsi
0x101e810af  call    qword ptr [rax+38h]
0x101e810b2  mov     r14, rax
0x101e810b5  mov     [rsp+3088h+var_2FC8], rax
0x101e810bd  test    rax, rax
0x101e810c0  jz      loc_101E82D2B
0x101e810c6  mov     rdx, [rax]
0x101e810c9  mov     rcx, rax
0x101e810cc  call    qword ptr [rdx+690h]
0x101e810d2  movzx   edi, al
0x101e810d5  mov     [rsp+3088h+var_3025], al
0x101e810d9  mov     rdx, [r14]
0x101e810dc  mov     rcx, r14
0x101e810df  call    qword ptr [rdx+6A8h]
0x101e810e5  movzx   r14d, al
0x101e810e9  mov     [rsp+3088h+var_3030], al
0x101e810ed  mov     [rsp+3088h+var_3026], al
0x101e810f1  test    dil, dil
0x101e810f4  jz      loc_101E82CD7
0x101e810fa  test    al, al
0x101e810fc  jz      loc_101E82CF3
0x101e81102  cmp     [rsp+3088h+var_3038], 0
0x101e81107  jz      loc_101E82D11
0x101e8110d  lea     rcx, [r15+29h]
0x101e81111  mov     [rsp+3088h+var_2EB8], rcx
0x101e81119  mov     byte ptr [rcx], 1
0x101e8111c  lea     rcx, [rsp+3088h+var_2C8]
0x101e81124  call    cs:__imp_??0LockRes@@QEAA@XZ; LockRes::LockRes(void)
0x101e8112a  mov     r8d, 15h
0x101e81130  mov     edx, r13d
0x101e81133  lea     rcx, [rsp+3088h+var_2C8]
0x101e8113b  call    cs:__imp_?SetDatabaseResource@LockRes@@QEAAXKW4DBLockSubresource@1@@Z; LockRes::SetDatabaseResource(ulong,LockRes::DBLockSubresource)
0x101e81141  mov     rax, [rsi]
0x101e81144  mov     rcx, rsi
0x101e81147  call    qword ptr [rax+10h]
0x101e8114a  mov     rdi, rax
0x101e8114d  mov     rsi, [rax]
0x101e81150  mov     edx, r13d
0x101e81153  mov     rcx, cs:qword_102ECFB00
0x101e8115a  mov     rcx, [rcx+20h]
0x101e8115e  call    cs:__imp_?LookupDB@DBMgr@@QEBAPEAVDBTABLE@@K@Z; DBMgr::LookupDB(ulong)
0x101e81164  mov     rdx, [rax+1210h]
0x101e8116b  mov     rcx, rdi
0x101e8116e  call    qword ptr [rsi+118h]
0x101e81174  mov     rdi, rax
0x101e81177  lea     rcx, [rsp+3088h+var_2B8]
0x101e8117f  call    cs:__imp_??0LockRequest@@QEAA@XZ; LockRequest::LockRequest(void)
0x101e81185  nop
0x101e81186  lea     rdx, [rdi+38h]
0x101e8118a  lea     rcx, [rsp+3088h+var_2B8]
0x101e81192  call    cs:__imp_?SetTransactionLockState@LockRequest@@QEAAXPEAVXactLockInfo@@@Z; LockRequest::SetTransactionLockState(XactLockInfo *)
0x101e81198  xor     edx, edx
0x101e8119a  lea     rcx, [rsp+3088h+var_2B8]
0x101e811a2  call    cs:__imp_?SetTimeout@LockRequest@@QEAAXK@Z; LockRequest::SetTimeout(ulong)
0x101e811a8  mov     dl, 3
0x101e811aa  lea     rcx, [rsp+3088h+var_2B8]
0x101e811b2  call    cs:__imp_?SetMode@LockRequest@@QEAAXW4LCK_MODE@@@Z; LockRequest::SetMode(LCK_MODE)
0x101e811b8  mov     edx, 2000000h
0x101e811bd  lea     rcx, [rsp+3088h+var_2B8]
0x101e811c5  call    cs:__imp_?SetClass@LockRequest@@QEAAXK@Z; LockRequest::SetClass(ulong)
0x101e811cb  mov     r15d, 1
0x101e811d1  test    cs:dword_102EDCA0C, 40000h
0x101e811db  jz      loc_101E81264
0x101e811e1  mov     [rsp+3088h+var_1160], 10000h
0x101e811ec  mov     [rsp+3088h+var_1158], ebx
0x101e811f3  lea     rax, [rsp+3088h+var_1138]
0x101e811fb  mov     [rsp+3088h+var_1150], rax
0x101e81203  lea     rax, [rsp+3088h+var_1128]
0x101e8120b  mov     [rsp+3088h+var_1148], rax
0x101e81213  mov     [rsp+3088h+var_F18], rbx
0x101e8121b  mov     [rsp+3088h+var_1140], rbx
0x101e81223  mov     [rsp+3088h+var_F10], rbx
0x101e8122b  lea     rax, [rsp+3088h+var_F08]
0x101e81233  mov     [rsp+3088h+var_1138], rax
0x101e8123b  mov     [rsp+3088h+var_1130], 8
0x101e81247  mov     [rsp+3088h+var_F08], r13d
0x101e8124f  mov     [rsp+3088h+var_F04], r12d
0x101e81257  lea     rcx, [rsp+3088h+var_1168]; this
0x101e8125f  call    ?Publish@stretch_migration_start_wait_for_lock@XeSqlPkg@@QEAAXXZ; XeSqlPkg::stretch_migration_start_wait_for_lock::Publish(void)
0x101e81264  xor     r8d, r8d
0x101e81267  lea     rdx, [rsp+3088h+var_2C8]
0x101e8126f  lea     rcx, [rsp+3088h+var_2B8]
0x101e81277  call    cs:__imp_?lck_lock@@YA?AW4LCK_RESULT@@AEAVLockRequest@@AEAVLockRes@@PEAVLockInfo@@@Z; lck_lock(LockRequest &,LockRes &,LockInfo *)
0x101e8127d  test    eax, eax
0x101e8127f  jns     loc_101E8133C
0x101e81285  mov     rax, [rsp+3088h+var_3000]
0x101e8128d  movzx   r9d, byte ptr [rax+28h]
0x101e81292  mov     r8d, r12d
0x101e81295  mov     edx, r13d
0x101e81298  lea     rcx, aTaskstretchtab_4; "TaskStretchTable::ProcessTskPkt (%d, %d"...
0x101e8129f  call    ?DebugTraceStretchSchema@@YAXPEB_WZZ; DebugTraceStretchSchema(wchar_t const *,...)
0x101e812a4  test    cs:dword_102EDCA0C, 100000h
0x101e812ae  jz      loc_101E82CC7
0x101e812b4  mov     [rsp+3088h+var_EF0], 10000h
0x101e812bf  mov     [rsp+3088h+var_EE8], ebx
0x101e812c6  lea     rax, [rsp+3088h+var_EC8]
0x101e812ce  mov     [rsp+3088h+var_EE0], rax
0x101e812d6  lea     rax, [rsp+3088h+var_EB8]
0x101e812de  mov     [rsp+3088h+var_ED8], rax
0x101e812e6  mov     [rsp+3088h+var_CA8], rbx
0x101e812ee  mov     [rsp+3088h+var_ED0], rbx
0x101e812f6  mov     [rsp+3088h+var_CA0], rbx
0x101e812fe  lea     rax, [rsp+3088h+var_C98]
0x101e81306  mov     [rsp+3088h+var_EC8], rax
0x101e8130e  mov     [rsp+3088h+var_EC0], 8
0x101e8131a  mov     [rsp+3088h+var_C98], r13d
0x101e81322  mov     [rsp+3088h+var_C94], r12d
0x101e8132a  lea     rcx, [rsp+3088h+var_EF8]; this
0x101e81332  call    ?Publish@stretch_migration_failed_to_acquire_lock@XeSqlPkg@@QEAAXXZ; XeSqlPkg::stretch_migration_failed_to_acquire_lock::Publish(void)
0x101e81337  jmp     loc_101E82CC7
0x101e8133c  test    cs:dword_102EDCA0C, 80000h
0x101e81346  jz      loc_101E813CF
0x101e8134c  mov     [rsp+3088h+var_C80], 10000h
0x101e81357  mov     [rsp+3088h+var_C78], ebx
0x101e8135e  lea     rax, [rsp+3088h+var_C58]
0x101e81366  mov     [rsp+3088h+var_C70], rax
0x101e8136e  lea     rax, [rsp+3088h+var_C48]
0x101e81376  mov     [rsp+3088h+var_C68], rax
0x101e8137e  mov     [rsp+3088h+var_A38], rbx
0x101e81386  mov     [rsp+3088h+var_C60], rbx
0x101e8138e  mov     [rsp+3088h+var_A30], rbx
0x101e81396  lea     rax, [rsp+3088h+var_A28]
0x101e8139e  mov     [rsp+3088h+var_C58], rax
0x101e813a6  mov     [rsp+3088h+var_C50], 8
0x101e813b2  mov     [rsp+3088h+var_A28], r13d
0x101e813ba  mov     [rsp+3088h+var_A24], r12d
0x101e813c2  lea     rcx, [rsp+3088h+var_C88]; this
0x101e813ca  call    ?Publish@stretch_migration_acquired_lock@XeSqlPkg@@QEAAXXZ; XeSqlPkg::stretch_migration_acquired_lock::Publish(void)
0x101e813cf  mov     rdi, [rsp+3088h+var_2FC8]
0x101e813d7  mov     rax, [rdi]
0x101e813da  mov     rcx, rdi
0x101e813dd  call    qword ptr [rax+90h]
0x101e813e3  mov     r14, rax
0x101e813e6  mov     [rsp+3088h+var_2EE8], rax
0x101e813ee  mov     rax, [rax]
0x101e813f1  mov     rcx, r14
0x101e813f4  test    r12d, r12d
0x101e813f7  jnz     short loc_101E8140F
0x101e813f9  mov     edx, 2055h
0x101e813fe  call    qword ptr [rax+8]
0x101e81401  mov     r8, [r14]
0x101e81404  xor     edx, edx
0x101e81406  mov     rcx, r14
0x101e81409  call    qword ptr [r8+48h]
0x101e8140d  jmp     short loc_101E81434
0x101e8140f  mov     r8d, 2055h
0x101e81415  mov     edx, r12d
0x101e81418  call    qword ptr [rax+28h]
0x101e8141b  mov     rax, [rsp+3088h+var_3000]
0x101e81423  cmp     byte ptr [rax+28h], 0
  ... truncated ...
```
