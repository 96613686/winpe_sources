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
  int v55; // edi
  char v56; // r14
  unsigned int v57; // esi
  unsigned int v58; // r12d
  char v59; // cl
  _BYTE *v60; // rsi
  CSbTransportMgr *v61; // rcx
  unsigned __int64 v62; // rcx
  unsigned __int64 v63; // rdx
  __int32 v64; // eax
  __int64 v65; // rsi
  __int64 v66; // rdi
  __int64 v67; // rcx
  __int64 v68; // rsi
  __int64 v69; // rdi
  __int64 v70; // r8
  __int64 v71; // rdi
  __int64 v72; // rdi
  __int64 v73; // rax
  void (__fastcall ***v74)(_QWORD, __int64); // rcx
  __int64 v75; // rbx
  struct Worker *v76; // rcx
  __int64 v77; // rsi
  __int64 v78; // rdi
  __int64 v79; // rcx
  __int64 v80; // rdi
  __int64 v81; // rsi
  __int64 v82; // r8
  __int64 v83; // rsi
  __int64 v84; // rsi
  CSbTransportMgr *v85; // rcx
  unsigned __int64 v86; // rcx
  unsigned __int64 v87; // rdx
  CSbTransportMgr *v88; // rcx
  unsigned __int64 v89; // rcx
  unsigned __int64 v90; // rdx
  TaskStretchTable *v91; // rcx
  TaskStretchTable *v92; // rsi
  __int64 v93; // rax
  DBTABLE *v94; // rdi
  bool v95; // al
  int v96; // ebx
  LARGE_INTEGER v97; // rax
  struct __crt_locale_pointers *DefaultLocale; // rax
  CSbTransportMgr *v100; // rcx
  unsigned __int64 v101; // rcx
  unsigned __int64 v102; // rdx
  int v103; // eax
  CSbTransportMgr *v104; // rcx
  unsigned __int64 v105; // rcx
  unsigned __int64 v106; // rdx
  int v107; // eax
  CSbTransportMgr *v108; // rcx
  unsigned __int64 v109; // rcx
  unsigned __int64 v110; // rdx
  int v111; // eax
  int (*v112)(int, int, int, int, char *); // [rsp+20h] [rbp-3068h]
  int (*v113)(int, int, int, int, char *); // [rsp+20h] [rbp-3068h]
  int v114; // [rsp+20h] [rbp-3068h]
  int v115; // [rsp+20h] [rbp-3068h]
  int v116; // [rsp+28h] [rbp-3060h]
  int v117; // [rsp+28h] [rbp-3060h]
  int v118; // [rsp+28h] [rbp-3060h]
  __int64 v119; // [rsp+30h] [rbp-3058h]
  int v120; // [rsp+38h] [rbp-3050h]
  int v121; // [rsp+38h] [rbp-3050h]
  int v122; // [rsp+40h] [rbp-3048h]
  bool v123; // [rsp+50h] [rbp-3038h]
  unsigned int v124; // [rsp+54h] [rbp-3034h]
  char v125; // [rsp+58h] [rbp-3030h]
  char v126; // [rsp+59h] [rbp-302Fh]
  unsigned int v127; // [rsp+5Ch] [rbp-302Ch]
  char v128; // [rsp+60h] [rbp-3028h]
  char v129; // [rsp+62h] [rbp-3026h]
  char v130; // [rsp+63h] [rbp-3025h]
  int v131; // [rsp+64h] [rbp-3024h]
  unsigned int v132; // [rsp+68h] [rbp-3020h]
  CSbTransportMgr *v133; // [rsp+70h] [rbp-3018h] BYREF
  unsigned int v134; // [rsp+78h] [rbp-3010h]
  int v135; // [rsp+7Ch] [rbp-300Ch]
  int v136; // [rsp+80h] [rbp-3008h]
  TaskStretchTable *v137; // [rsp+88h] [rbp-3000h]
  __int64 v138; // [rsp+90h] [rbp-2FF8h]
  unsigned int v139; // [rsp+98h] [rbp-2FF0h]
  int v140; // [rsp+9Ch] [rbp-2FECh]
  int v141; // [rsp+A0h] [rbp-2FE8h]
  unsigned __int64 v142; // [rsp+A8h] [rbp-2FE0h]
  unsigned __int64 v143; // [rsp+B0h] [rbp-2FD8h]
  void *v144; // [rsp+B8h] [rbp-2FD0h] BYREF
  __int64 v145; // [rsp+C0h] [rbp-2FC8h]
  void (__fastcall ***v146)(_QWORD, __int64); // [rsp+C8h] [rbp-2FC0h] BYREF
  void (__fastcall ***v147)(_QWORD, __int64); // [rsp+D0h] [rbp-2FB8h] BYREF
  unsigned int v148; // [rsp+D8h] [rbp-2FB0h]
  unsigned int v149; // [rsp+DCh] [rbp-2FACh]
  _DWORD v150[3]; // [rsp+E0h] [rbp-2FA8h] BYREF
  int v151; // [rsp+ECh] [rbp-2F9Ch]
  int v152; // [rsp+F0h] [rbp-2F98h]
  __int64 v153; // [rsp+F8h] [rbp-2F90h]
  __int16 v154; // [rsp+100h] [rbp-2F88h]
  __int16 v155; // [rsp+108h] [rbp-2F80h]
  __int16 v156; // [rsp+110h] [rbp-2F78h]
  __int16 v157; // [rsp+118h] [rbp-2F70h]
  __int16 v158; // [rsp+120h] [rbp-2F68h]
  CSbTransportMgr *v159; // [rsp+128h] [rbp-2F60h] BYREF
  CSbTransportMgr *v160; // [rsp+130h] [rbp-2F58h] BYREF
  CSbTransportMgr *v161; // [rsp+138h] [rbp-2F50h] BYREF
  CSbTransportMgr *v162; // [rsp+140h] [rbp-2F48h] BYREF
  CSbTransportMgr *v163; // [rsp+148h] [rbp-2F40h] BYREF
  CSbTransportMgr *v164; // [rsp+150h] [rbp-2F38h] BYREF
  __int16 v165; // [rsp+158h] [rbp-2F30h]
  __int16 v166; // [rsp+160h] [rbp-2F28h]
  unsigned int v167; // [rsp+168h] [rbp-2F20h]
  __int16 v168; // [rsp+170h] [rbp-2F18h]
  unsigned __int64 v169; // [rsp+178h] [rbp-2F10h] BYREF
  unsigned __int64 v170; // [rsp+180h] [rbp-2F08h] BYREF
  unsigned __int64 v171; // [rsp+188h] [rbp-2F00h] BYREF
  unsigned __int64 v172; // [rsp+190h] [rbp-2EF8h] BYREF
  unsigned __int64 v173; // [rsp+198h] [rbp-2EF0h] BYREF
  __int64 v174; // [rsp+1A0h] [rbp-2EE8h]
  TaskStretchTable *v175; // [rsp+1A8h] [rbp-2EE0h]
  void (__fastcall ***v176)(_QWORD, __int64); // [rsp+1B0h] [rbp-2ED8h]
  __int64 v177; // [rsp+1B8h] [rbp-2ED0h]
  int v178; // [rsp+1C0h] [rbp-2EC8h]
  int v179; // [rsp+1C4h] [rbp-2EC4h]
  int v180; // [rsp+1C8h] [rbp-2EC0h]
  int v181; // [rsp+1CCh] [rbp-2EBCh]
  _BYTE *v182; // [rsp+1D0h] [rbp-2EB8h]
  unsigned __int64 v183; // [rsp+1D8h] [rbp-2EB0h] BYREF
  __m128i si128; // [rsp+1E0h] [rbp-2EA8h] BYREF
  int v185; // [rsp+1F0h] [rbp-2E98h]
  int v186; // [rsp+1F8h] [rbp-2E90h]
  int v187; // [rsp+1FCh] [rbp-2E8Ch]
  int v188; // [rsp+200h] [rbp-2E88h]
  int v189; // [rsp+204h] [rbp-2E84h]
  int v190; // [rsp+208h] [rbp-2E80h]
  int v191; // [rsp+20Ch] [rbp-2E7Ch]
  int v192; // [rsp+210h] [rbp-2E78h]
  int v193; // [rsp+214h] [rbp-2E74h]
  int v194; // [rsp+218h] [rbp-2E70h]
  int v195; // [rsp+21Ch] [rbp-2E6Ch]
  int v196; // [rsp+220h] [rbp-2E68h]
  int v197; // [rsp+224h] [rbp-2E64h]
  int v198; // [rsp+228h] [rbp-2E60h]
  int v199; // [rsp+22Ch] [rbp-2E5Ch]
  int v200; // [rsp+230h] [rbp-2E58h]
  int v201; // [rsp+234h] [rbp-2E54h]
  int v202; // [rsp+238h] [rbp-2E50h]
  int v203; // [rsp+23Ch] [rbp-2E4Ch]
  int v204; // [rsp+240h] [rbp-2E48h]
  int v205; // [rsp+244h] [rbp-2E44h]
  int v206; // [rsp+248h] [rbp-2E40h]
  int v207; // [rsp+24Ch] [rbp-2E3Ch]
  __int64 v208; // [rsp+250h] [rbp-2E38h]
  LARGE_INTEGER PerformanceCount; // [rsp+258h] [rbp-2E30h] BYREF
  __int64 v210; // [rsp+260h] [rbp-2E28h] BYREF
  TaskStretchTable *v211; // [rsp+268h] [rbp-2E20h]
  LARGE_INTEGER v212; // [rsp+270h] [rbp-2E18h] BYREF
  int v213; // [rsp+278h] [rbp-2E10h]
  LARGE_INTEGER v214; // [rsp+280h] [rbp-2E08h] BYREF
  int v215; // [rsp+288h] [rbp-2E00h]
  LARGE_INTEGER v216; // [rsp+290h] [rbp-2DF8h] BYREF
  int v217; // [rsp+298h] [rbp-2DF0h]
  LARGE_INTEGER v218; // [rsp+2A0h] [rbp-2DE8h] BYREF
  LARGE_INTEGER v219; // [rsp+2A8h] [rbp-2DE0h] BYREF
  LARGE_INTEGER v220[3]; // [rsp+2B0h] [rbp-2DD8h] BYREF
  int v221; // [rsp+2C8h] [rbp-2DC0h]
  int v222; // [rsp+2CCh] [rbp-2DBCh]
  __int64 v223; // [rsp+2D0h] [rbp-2DB8h] BYREF
  int v224; // [rsp+2D8h] [rbp-2DB0h]
  __int64 v225; // [rsp+2DCh] [rbp-2DACh]
  int v226; // [rsp+2E4h] [rbp-2DA4h]
  int v227; // [rsp+2E8h] [rbp-2DA0h]
  __int64 v228; // [rsp+2ECh] [rbp-2D9Ch]
  int v229; // [rsp+2F8h] [rbp-2D90h] BYREF
  __int64 v230; // [rsp+300h] [rbp-2D88h]
  __int64 v231; // [rsp+308h] [rbp-2D80h]
  __int64 v232; // [rsp+310h] [rbp-2D78h]
  __int64 v233; // [rsp+318h] [rbp-2D70h]
  CSbTransportMgr **v234; // [rsp+320h] [rbp-2D68h]
  CSbTransportMgr **v235; // [rsp+328h] [rbp-2D60h]
  CSbTransportMgr **v236; // [rsp+330h] [rbp-2D58h]
  unsigned __int64 *v237; // [rsp+338h] [rbp-2D50h]
  __int64 v238; // [rsp+340h] [rbp-2D48h]
  __int64 v239; // [rsp+348h] [rbp-2D40h]
  unsigned __int64 *v240; // [rsp+350h] [rbp-2D38h]
  unsigned __int64 v241; // [rsp+358h] [rbp-2D30h]
  _QWORD *v242; // [rsp+360h] [rbp-2D28h]
  __int64 v243; // [rsp+368h] [rbp-2D20h]
  __int64 v244; // [rsp+370h] [rbp-2D18h]
  __int64 v245; // [rsp+378h] [rbp-2D10h]
  _WORD *v246; // [rsp+380h] [rbp-2D08h]
  _DWORD **v247; // [rsp+388h] [rbp-2D00h]
  void (__fastcall ***v248)(_QWORD, __int64); // [rsp+390h] [rbp-2CF8h]
  _QWORD *v249; // [rsp+398h] [rbp-2CF0h]
  __int64 v250; // [rsp+3A0h] [rbp-2CE8h]
  __int64 v251; // [rsp+3A8h] [rbp-2CE0h]
  __int64 v252; // [rsp+3B0h] [rbp-2CD8h]
  _WORD *v253; // [rsp+3B8h] [rbp-2CD0h]
  _DWORD **v254; // [rsp+3C0h] [rbp-2CC8h]
  void (__fastcall ***v255)(_QWORD, __int64); // [rsp+3C8h] [rbp-2CC0h]
  _WORD *v256; // [rsp+3D0h] [rbp-2CB8h]
  _DWORD **v257; // [rsp+3D8h] [rbp-2CB0h]
  CSbTransportMgr **v258; // [rsp+3E0h] [rbp-2CA8h]
  CSbTransportMgr **v259; // [rsp+3E8h] [rbp-2CA0h]
  CSbTransportMgr **v260; // [rsp+3F0h] [rbp-2C98h]
  unsigned __int64 *v261; // [rsp+3F8h] [rbp-2C90h]
  __int64 v262; // [rsp+400h] [rbp-2C88h]
  __int64 v263; // [rsp+408h] [rbp-2C80h]
  unsigned __int64 *v264; // [rsp+410h] [rbp-2C78h]
  unsigned __int64 v265; // [rsp+418h] [rbp-2C70h]
  _WORD *v266; // [rsp+420h] [rbp-2C68h]
  _DWORD **v267; // [rsp+428h] [rbp-2C60h]
  CSbTransportMgr **v268; // [rsp+430h] [rbp-2C58h]
  CSbTransportMgr **v269; // [rsp+438h] [rbp-2C50h]
  CSbTransportMgr **v270; // [rsp+440h] [rbp-2C48h]
  unsigned __int64 *v271; // [rsp+448h] [rbp-2C40h]
  __int64 v272; // [rsp+450h] [rbp-2C38h]
  __int64 v273; // [rsp+458h] [rbp-2C30h]
  unsigned __int64 *v274; // [rsp+460h] [rbp-2C28h]
  unsigned __int64 v275; // [rsp+468h] [rbp-2C20h]
  void *v276; // [rsp+470h] [rbp-2C18h]
  LARGE_INTEGER *v277; // [rsp+478h] [rbp-2C10h]
  __int64 v278; // [rsp+480h] [rbp-2C08h]
  LARGE_INTEGER v279; // [rsp+488h] [rbp-2C00h]
  struct IMetadataAccess *v280; // [rsp+490h] [rbp-2BF8h]
  __int64 v281; // [rsp+498h] [rbp-2BF0h]
  __int64 v282; // [rsp+4A0h] [rbp-2BE8h]
  wchar_t *v283; // [rsp+4A8h] [rbp-2BE0h]
  _WORD *v284; // [rsp+4B0h] [rbp-2BD8h]
  _DWORD **v285; // [rsp+4B8h] [rbp-2BD0h]
  CSbTransportMgr **v286; // [rsp+4C0h] [rbp-2BC8h]
  CSbTransportMgr **v287; // [rsp+4C8h] [rbp-2BC0h]
  CSbTransportMgr **v288; // [rsp+4D0h] [rbp-2BB8h]
  unsigned __int64 *v289; // [rsp+4D8h] [rbp-2BB0h]
  union _LARGE_INTEGER v290; // [rsp+4E0h] [rbp-2BA8h]
  __int64 v291; // [rsp+4E8h] [rbp-2BA0h]
  __int64 v292; // [rsp+4F0h] [rbp-2B98h]
  unsigned __int64 *v293; // [rsp+4F8h] [rbp-2B90h]
  _WORD *v294; // [rsp+500h] [rbp-2B88h]
  _DWORD **v295; // [rsp+508h] [rbp-2B80h]
  CSbTransportMgr **v296; // [rsp+510h] [rbp-2B78h]
  CSbTransportMgr **v297; // [rsp+518h] [rbp-2B70h]
  CSbTransportMgr **v298; // [rsp+520h] [rbp-2B68h]
  unsigned __int64 *v299; // [rsp+528h] [rbp-2B60h]
  union _LARGE_INTEGER v300; // [rsp+530h] [rbp-2B58h]
  __int64 v301; // [rsp+538h] [rbp-2B50h]
  __int64 v302; // [rsp+540h] [rbp-2B48h]
  unsigned __int64 *v303; // [rsp+548h] [rbp-2B40h]
  _WORD *v304; // [rsp+550h] [rbp-2B38h]
  _DWORD **v305; // [rsp+558h] [rbp-2B30h]
  CSbTransportMgr **v306; // [rsp+560h] [rbp-2B28h]
  CSbTransportMgr **v307; // [rsp+568h] [rbp-2B20h]
  CSbTransportMgr **v308; // [rsp+570h] [rbp-2B18h]
  unsigned __int64 *v309; // [rsp+578h] [rbp-2B10h]
  union _LARGE_INTEGER v310; // [rsp+580h] [rbp-2B08h]
  __int64 v311; // [rsp+588h] [rbp-2B00h]
  __int64 v312; // [rsp+590h] [rbp-2AF8h]
  unsigned __int64 *v313; // [rsp+598h] [rbp-2AF0h]
  _QWORD v314[6]; // [rsp+5A0h] [rbp-2AE8h] BYREF
  _BYTE v315[48]; // [rsp+5D0h] [rbp-2AB8h] BYREF
  __int64 v316; // [rsp+600h] [rbp-2A88h] BYREF
  _WORD v317[4]; // [rsp+608h] [rbp-2A80h] BYREF
  int v318; // [rsp+610h] [rbp-2A78h]
  _DWORD **v319; // [rsp+618h] [rbp-2A70h]
  _DWORD *v320; // [rsp+620h] [rbp-2A68h]
  __int64 v321; // [rsp+628h] [rbp-2A60h]
  _DWORD *v322; // [rsp+630h] [rbp-2A58h] BYREF
  int v323; // [rsp+638h] [rbp-2A50h]
  __int16 v324; // [rsp+63Ch] [rbp-2A4Ch]
  __int16 v325; // [rsp+63Eh] [rbp-2A4Ah]
  _DWORD v326[134]; // [rsp+640h] [rbp-2A48h] BYREF
  __int64 v327; // [rsp+858h] [rbp-2830h]
  _DWORD v328[2]; // [rsp+860h] [rbp-2828h] BYREF
  char v329; // [rsp+868h] [rbp-2820h]
  unsigned __int64 v330; // [rsp+869h] [rbp-281Fh]
  int v331; // [rsp+871h] [rbp-2817h]
  int v332; // [rsp+875h] [rbp-2813h]
  __int64 v333; // [rsp+879h] [rbp-280Fh]
  char v334[8]; // [rsp+890h] [rbp-27F8h] BYREF
  _WORD v335[4]; // [rsp+898h] [rbp-27F0h] BYREF
  int v336; // [rsp+8A0h] [rbp-27E8h]
  _DWORD **v337; // [rsp+8A8h] [rbp-27E0h]
  char *v338; // [rsp+8B0h] [rbp-27D8h]
  __int64 v339; // [rsp+8B8h] [rbp-27D0h]
  _DWORD *v340; // [rsp+8C0h] [rbp-27C8h] BYREF
  int v341; // [rsp+8C8h] [rbp-27C0h]
  __int16 v342; // [rsp+8CCh] [rbp-27BCh]
  __int16 v343; // [rsp+8CEh] [rbp-27BAh]
  char v344; // [rsp+8D0h] [rbp-27B8h] BYREF
  int v345; // [rsp+AE0h] [rbp-25A8h]
  int v346; // [rsp+AE4h] [rbp-25A4h]
  __int64 v347; // [rsp+AE8h] [rbp-25A0h]
  _DWORD v348[2]; // [rsp+AF0h] [rbp-2598h] BYREF
  char v349; // [rsp+AF8h] [rbp-2590h]
  unsigned __int64 v350; // [rsp+AF9h] [rbp-258Fh]
  int v351; // [rsp+B01h] [rbp-2587h]
  int v352; // [rsp+B05h] [rbp-2583h]
  __int64 v353; // [rsp+B09h] [rbp-257Fh]
  char v354[8]; // [rsp+B20h] [rbp-2568h] BYREF
  _WORD v355[4]; // [rsp+B28h] [rbp-2560h] BYREF
  int v356; // [rsp+B30h] [rbp-2558h]
  _DWORD **v357; // [rsp+B38h] [rbp-2550h]
  char *v358; // [rsp+B40h] [rbp-2548h]
  __int64 v359; // [rsp+B48h] [rbp-2540h]
  _DWORD *v360; // [rsp+B50h] [rbp-2538h] BYREF
  int v361; // [rsp+B58h] [rbp-2530h]
  __int16 v362; // [rsp+B5Ch] [rbp-252Ch]
  __int16 v363; // [rsp+B5Eh] [rbp-252Ah]
  char v364; // [rsp+B60h] [rbp-2528h] BYREF
  int v365; // [rsp+D70h] [rbp-2318h]
  int v366; // [rsp+D74h] [rbp-2314h]
  __int64 v367; // [rsp+D78h] [rbp-2310h]
  _DWORD v368[2]; // [rsp+D80h] [rbp-2308h] BYREF
  char v369; // [rsp+D88h] [rbp-2300h]
  unsigned __int64 v370; // [rsp+D89h] [rbp-22FFh]
  int v371; // [rsp+D91h] [rbp-22F7h]
  int v372; // [rsp+D95h] [rbp-22F3h]
  __int64 v373; // [rsp+D99h] [rbp-22EFh]
  char v374[8]; // [rsp+DB0h] [rbp-22D8h] BYREF
  _WORD v375[4]; // [rsp+DB8h] [rbp-22D0h] BYREF
  int v376; // [rsp+DC0h] [rbp-22C8h]
  _DWORD **v377; // [rsp+DC8h] [rbp-22C0h]
  char *v378; // [rsp+DD0h] [rbp-22B8h]
  __int64 v379; // [rsp+DD8h] [rbp-22B0h]
  _DWORD *v380; // [rsp+DE0h] [rbp-22A8h] BYREF
  int v381; // [rsp+DE8h] [rbp-22A0h]
  __int16 v382; // [rsp+DECh] [rbp-229Ch]
  __int16 v383; // [rsp+DEEh] [rbp-229Ah]
  char v384; // [rsp+DF0h] [rbp-2298h] BYREF
  int v385; // [rsp+1000h] [rbp-2088h]
  int v386; // [rsp+1004h] [rbp-2084h]
  __int64 v387; // [rsp+1008h] [rbp-2080h]
  _DWORD v388[2]; // [rsp+1010h] [rbp-2078h] BYREF
  char v389; // [rsp+1018h] [rbp-2070h]
  unsigned __int64 v390; // [rsp+1019h] [rbp-206Fh]
  int v391; // [rsp+1021h] [rbp-2067h]
  int v392; // [rsp+1025h] [rbp-2063h]
  __int64 v393; // [rsp+1029h] [rbp-205Fh]
  __int64 v394; // [rsp+1040h] [rbp-2048h] BYREF
  _WORD v395[4]; // [rsp+1048h] [rbp-2040h] BYREF
  int v396; // [rsp+1050h] [rbp-2038h]
  _DWORD **v397; // [rsp+1058h] [rbp-2030h]
  _DWORD *v398; // [rsp+1060h] [rbp-2028h]
  __int64 v399; // [rsp+1068h] [rbp-2020h]
  _DWORD *v400; // [rsp+1070h] [rbp-2018h] BYREF
  int v401; // [rsp+1078h] [rbp-2010h]
  __int16 v402; // [rsp+107Ch] [rbp-200Ch]
  __int16 v403; // [rsp+107Eh] [rbp-200Ah]
  _DWORD v404[134]; // [rsp+1080h] [rbp-2008h] BYREF
  __int64 v405; // [rsp+1298h] [rbp-1DF0h]
  _DWORD v406[2]; // [rsp+12A0h] [rbp-1DE8h] BYREF
  char v407; // [rsp+12A8h] [rbp-1DE0h]
  unsigned __int64 v408; // [rsp+12A9h] [rbp-1DDFh]
  int v409; // [rsp+12B1h] [rbp-1DD7h]
  int v410; // [rsp+12B5h] [rbp-1DD3h]
  __int64 v411; // [rsp+12B9h] [rbp-1DCFh]
  __int64 v412; // [rsp+12D0h] [rbp-1DB8h] BYREF
  _WORD v413[4]; // [rsp+12D8h] [rbp-1DB0h] BYREF
  int v414; // [rsp+12E0h] [rbp-1DA8h]
  _DWORD **v415; // [rsp+12E8h] [rbp-1DA0h]
  _DWORD *v416; // [rsp+12F0h] [rbp-1D98h]
  __int64 v417; // [rsp+12F8h] [rbp-1D90h]
  _DWORD *v418; // [rsp+1300h] [rbp-1D88h] BYREF
  int v419; // [rsp+1308h] [rbp-1D80h]
  __int16 v420; // [rsp+130Ch] [rbp-1D7Ch]
  __int16 v421; // [rsp+130Eh] [rbp-1D7Ah]
  _DWORD v422[134]; // [rsp+1310h] [rbp-1D78h] BYREF
  __int64 v423; // [rsp+1528h] [rbp-1B60h]
  _DWORD v424[2]; // [rsp+1530h] [rbp-1B58h] BYREF
  char v425; // [rsp+1538h] [rbp-1B50h]
  unsigned __int64 v426; // [rsp+1539h] [rbp-1B4Fh]
  int v427; // [rsp+1541h] [rbp-1B47h]
  int v428; // [rsp+1545h] [rbp-1B43h]
  __int64 v429; // [rsp+1549h] [rbp-1B3Fh]
  char v430[8]; // [rsp+1560h] [rbp-1B28h] BYREF
  _WORD v431[4]; // [rsp+1568h] [rbp-1B20h] BYREF
  int v432; // [rsp+1570h] [rbp-1B18h]
  _DWORD **v433; // [rsp+1578h] [rbp-1B10h]
  char *v434; // [rsp+1580h] [rbp-1B08h]
  __int64 v435; // [rsp+1588h] [rbp-1B00h]
  _DWORD *v436; // [rsp+1590h] [rbp-1AF8h] BYREF
  int v437; // [rsp+1598h] [rbp-1AF0h]
  __int16 v438; // [rsp+159Ch] [rbp-1AECh]
  __int16 v439; // [rsp+159Eh] [rbp-1AEAh]
  char v440; // [rsp+15A0h] [rbp-1AE8h] BYREF
  int v441; // [rsp+17B0h] [rbp-18D8h]
  int v442; // [rsp+17B4h] [rbp-18D4h]
  __int64 v443; // [rsp+17B8h] [rbp-18D0h]
  _DWORD v444[4]; // [rsp+17C0h] [rbp-18C8h] BYREF
  char v445[8]; // [rsp+17D0h] [rbp-18B8h] BYREF
  _WORD v446[4]; // [rsp+17D8h] [rbp-18B0h] BYREF
  int v447; // [rsp+17E0h] [rbp-18A8h]
  _DWORD **v448; // [rsp+17E8h] [rbp-18A0h]
  char *v449; // [rsp+17F0h] [rbp-1898h]
  __int64 v450; // [rsp+17F8h] [rbp-1890h]
  _DWORD *v451; // [rsp+1800h] [rbp-1888h] BYREF
  int v452; // [rsp+1808h] [rbp-1880h]
  __int16 v453; // [rsp+180Ch] [rbp-187Ch]
  __int16 v454; // [rsp+180Eh] [rbp-187Ah]
  char v455; // [rsp+1810h] [rbp-1878h] BYREF
  int v456; // [rsp+1A20h] [rbp-1668h]
  int v457; // [rsp+1A24h] [rbp-1664h]
  __int64 v458; // [rsp+1A28h] [rbp-1660h]
  _DWORD v459[4]; // [rsp+1A30h] [rbp-1658h] BYREF
  char v460[8]; // [rsp+1A40h] [rbp-1648h] BYREF
  int v461; // [rsp+1A48h] [rbp-1640h]
  int v462; // [rsp+1A50h] [rbp-1638h]
  _QWORD *v463; // [rsp+1A58h] [rbp-1630h]
  char *v464; // [rsp+1A60h] [rbp-1628h]
  __int64 v465; // [rsp+1A68h] [rbp-1620h]
  _QWORD v466[2]; // [rsp+1A70h] [rbp-1618h] BYREF
  char v467; // [rsp+1A80h] [rbp-1608h] BYREF
  __int64 v468; // [rsp+1C90h] [rbp-13F8h]
  __int64 v469; // [rsp+1C98h] [rbp-13F0h]
  unsigned int v470; // [rsp+1CA0h] [rbp-13E8h] BYREF
  bool v471; // [rsp+1CA4h] [rbp-13E4h]
  bool v472; // [rsp+1CA5h] [rbp-13E3h]
  bool v473; // [rsp+1CA6h] [rbp-13E2h]
  char v474[8]; // [rsp+1CB0h] [rbp-13D8h] BYREF
  int v475; // [rsp+1CB8h] [rbp-13D0h]
  int v476; // [rsp+1CC0h] [rbp-13C8h]
  _QWORD *v477; // [rsp+1CC8h] [rbp-13C0h]
  char *v478; // [rsp+1CD0h] [rbp-13B8h]
  __int64 v479; // [rsp+1CD8h] [rbp-13B0h]
  _QWORD v480[2]; // [rsp+1CE0h] [rbp-13A8h] BYREF
  char v481; // [rsp+1CF0h] [rbp-1398h] BYREF
  __int64 v482; // [rsp+1F00h] [rbp-1188h]
  __int64 v483; // [rsp+1F08h] [rbp-1180h]
  _DWORD v484[4]; // [rsp+1F10h] [rbp-1178h] BYREF
  char v485[8]; // [rsp+1F20h] [rbp-1168h] BYREF
  int v486; // [rsp+1F28h] [rbp-1160h]
  int v487; // [rsp+1F30h] [rbp-1158h]
  _QWORD *v488; // [rsp+1F38h] [rbp-1150h]
  char *v489; // [rsp+1F40h] [rbp-1148h]
  __int64 v490; // [rsp+1F48h] [rbp-1140h]
  _QWORD v491[2]; // [rsp+1F50h] [rbp-1138h] BYREF
  char v492; // [rsp+1F60h] [rbp-1128h] BYREF
  __int64 v493; // [rsp+2170h] [rbp-F18h]
  __int64 v494; // [rsp+2178h] [rbp-F10h]
  _DWORD v495[4]; // [rsp+2180h] [rbp-F08h] BYREF
  char v496[8]; // [rsp+2190h] [rbp-EF8h] BYREF
  int v497; // [rsp+2198h] [rbp-EF0h]
  int v498; // [rsp+21A0h] [rbp-EE8h]
  _QWORD *v499; // [rsp+21A8h] [rbp-EE0h]
  char *v500; // [rsp+21B0h] [rbp-ED8h]
  __int64 v501; // [rsp+21B8h] [rbp-ED0h]
  _QWORD v502[2]; // [rsp+21C0h] [rbp-EC8h] BYREF
  char v503; // [rsp+21D0h] [rbp-EB8h] BYREF
  __int64 v504; // [rsp+23E0h] [rbp-CA8h]
  __int64 v505; // [rsp+23E8h] [rbp-CA0h]
  _DWORD v506[4]; // [rsp+23F0h] [rbp-C98h] BYREF
  char v507[8]; // [rsp+2400h] [rbp-C88h] BYREF
  int v508; // [rsp+2408h] [rbp-C80h]
  int v509; // [rsp+2410h] [rbp-C78h]
  _QWORD *v510; // [rsp+2418h] [rbp-C70h]
  char *v511; // [rsp+2420h] [rbp-C68h]
  __int64 v512; // [rsp+2428h] [rbp-C60h]
  _QWORD v513[2]; // [rsp+2430h] [rbp-C58h] BYREF
  char v514; // [rsp+2440h] [rbp-C48h] BYREF
  __int64 v515; // [rsp+2650h] [rbp-A38h]
  __int64 v516; // [rsp+2658h] [rbp-A30h]
  _DWORD v517[4]; // [rsp+2660h] [rbp-A28h] BYREF
  char v518[8]; // [rsp+2670h] [rbp-A18h] BYREF
  int v519; // [rsp+2678h] [rbp-A10h]
  int v520; // [rsp+2680h] [rbp-A08h]
  _QWORD *v521; // [rsp+2688h] [rbp-A00h]
  char *v522; // [rsp+2690h] [rbp-9F8h]
  __int64 v523; // [rsp+2698h] [rbp-9F0h]
  _QWORD v524[2]; // [rsp+26A0h] [rbp-9E8h] BYREF
  char v525; // [rsp+26B0h] [rbp-9D8h] BYREF
  __int64 v526; // [rsp+28C0h] [rbp-7C8h]
  __int64 v527; // [rsp+28C8h] [rbp-7C0h]
  _DWORD v528[4]; // [rsp+28D0h] [rbp-7B8h] BYREF
  char v529[8]; // [rsp+28E0h] [rbp-7A8h] BYREF
  int v530; // [rsp+28E8h] [rbp-7A0h]
  int v531; // [rsp+28F0h] [rbp-798h]
  _QWORD *v532; // [rsp+28F8h] [rbp-790h]
  char *v533; // [rsp+2900h] [rbp-788h]
  __int64 v534; // [rsp+2908h] [rbp-780h]
  _QWORD v535[2]; // [rsp+2910h] [rbp-778h] BYREF
  char v536; // [rsp+2920h] [rbp-768h] BYREF
  __int64 v537; // [rsp+2B30h] [rbp-558h]
  __int64 v538; // [rsp+2B38h] [rbp-550h]
  _DWORD v539[4]; // [rsp+2B40h] [rbp-548h] BYREF
  char v540[8]; // [rsp+2B50h] [rbp-538h] BYREF
  int v541; // [rsp+2B58h] [rbp-530h]
  int v542; // [rsp+2B60h] [rbp-528h]
  _QWORD *v543; // [rsp+2B68h] [rbp-520h]
  char *v544; // [rsp+2B70h] [rbp-518h]
  __int64 v545; // [rsp+2B78h] [rbp-510h]
  _QWORD v546[2]; // [rsp+2B80h] [rbp-508h] BYREF
  char v547; // [rsp+2B90h] [rbp-4F8h] BYREF
  __int64 v548; // [rsp+2DA0h] [rbp-2E8h]
  __int64 v549; // [rsp+2DA8h] [rbp-2E0h]
  _DWORD v550[4]; // [rsp+2DB0h] [rbp-2D8h] BYREF
  _BYTE v551[16]; // [rsp+2DC0h] [rbp-2C8h] BYREF
  _BYTE v552[80]; // [rsp+2DD0h] [rbp-2B8h] BYREF
  _BYTE v553[48]; // [rsp+2E20h] [rbp-268h] BYREF
  wchar_t v554[256]; // [rsp+2E50h] [rbp-238h] BYREF

  v278 = -2;
  v137 = this;
  v211 = this;
  v175 = this;
  v177 = 0;
  v132 = 0;
  v149 = 10;
  v167 = 3;
  v130 = 0;
  v128 = 0;
  v125 = 0;
  v123 = 0;
  v2 = *((_DWORD *)this + 8);
  v124 = v2;
  v134 = v2;
  v3 = *((_DWORD *)this + 9);
  v127 = v3;
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
  v177 = (**(__int64 (__fastcall ***)(struct IAutoXactFactory *))g_pAutoXactFactory)(g_pAutoXactFactory);
  (*(void (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v177 + 16LL))(v177, L"TaskStretchTable", 32);
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v177 + 72LL))(v177);
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v9 = *(_QWORD *)(v8 + 256);
  if ( !v9 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v9 = *(_QWORD *)(v8 + 256);
  }
  v10 = g_metadataFactory(*(_QWORD *)(v9 + 1000), v7, "sql\\ntdbms\\stretch\\src\\stretchtask.cpp", 2922);
  v176 = (void (__fastcall ***)(_QWORD, __int64))v10;
  v141 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v2 )
  {
    v141 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, int, char, char, char))g_dbtableFactory[5])(
             v11,
             0,
             v2,
             16,
             640,
             1,
             1,
             1);
    if ( v141 )
    {
      v12 = DBMgr::LookupDB(*(DBMgr **)(qword_102ECFB00 + 32), v2);
      v13 = v12;
      v123 = v12
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
  v145 = v14;
  if ( v14 )
  {
    v130 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 1680LL))(v14);
    v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 1704LL))(v15);
    v17 = v16;
    v125 = v16;
    v129 = v16;
    if ( v130 )
    {
      if ( v16 )
      {
        if ( v123 )
        {
          v182 = (char *)this + 41;
          *((_BYTE *)this + 41) = 1;
          LockRes::LockRes((LockRes *)v551);
          LockRes::SetDatabaseResource(v551, v2, 21);
          v18 = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          v19 = *v18;
          v20 = DBMgr::LookupDB(*(DBMgr **)(qword_102ECFB00 + 32), v2);
          v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(v19 + 280))(v18, *((_QWORD *)v20 + 578));
          LockRequest::LockRequest((LockRequest *)v552);
          LockRequest::SetTransactionLockState((LockRequest *)v552, (struct XactLockInfo *)(v21 + 56));
          LockRequest::SetTimeout((LockRequest *)v552, 0);
          LOBYTE(v22) = 3;
          LockRequest::SetMode(v552, v22);
          LockRequest::SetClass((LockRequest *)v552, 0x2000000u);
          if ( (dword_102EDCA0C & 0x40000) != 0 )
          {
            v486 = 0x10000;
            v487 = 0;
            v488 = v491;
            v489 = &v492;
            v493 = 0;
            v490 = 0;
            v494 = 0;
            v491[0] = v495;
            v491[1] = 8;
            v495[0] = v2;
            v495[1] = v3;
            XeSqlPkg::stretch_migration_start_wait_for_lock::Publish((XeSqlPkg::stretch_migration_start_wait_for_lock *)v485);
          }
          if ( (int)lck_lock(v552, v551, 0) < 0 )
          {
            DebugTraceStretchSchema(
              L"TaskStretchTable::ProcessTskPkt (%d, %d, %d) failed to acquire shared lock",
              v2,
              v3,
              *((unsigned __int8 *)v137 + 40));
            if ( (dword_102EDCA0C & 0x100000) != 0 )
            {
              v497 = 0x10000;
              v498 = 0;
              v499 = v502;
              v500 = &v503;
              v504 = 0;
              v501 = 0;
              v505 = 0;
              v502[0] = v506;
              v502[1] = 8;
              v506[0] = v2;
              v506[1] = v3;
              XeSqlPkg::stretch_migration_failed_to_acquire_lock::Publish((XeSqlPkg::stretch_migration_failed_to_acquire_lock *)v496);
            }
LABEL_211:
            LockRequest::~LockRequest((LockRequest *)v552);
            goto LABEL_217;
          }
          if ( (dword_102EDCA0C & 0x80000) != 0 )
          {
            v508 = 0x10000;
            v509 = 0;
            v510 = v513;
            v511 = &v514;
            v515 = 0;
            v512 = 0;
            v516 = 0;
            v513[0] = v517;
            v513[1] = 8;
            v517[0] = v2;
            v517[1] = v3;
            XeSqlPkg::stretch_migration_acquired_lock::Publish((XeSqlPkg::stretch_migration_acquired_lock *)v507);
          }
          v23 = v145;
          v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v145 + 144LL))(v145);
          v174 = v24;
          v25 = *(_QWORD *)v24;
          if ( v3 )
          {
            (*(void (__fastcall **)(__int64, _QWORD, __int64))(v25 + 40))(v24, v3, 8277);
            if ( *((_BYTE *)v137 + 40) )
              goto LABEL_33;
            v26 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 72LL))(v24, 0);
          }
          else
          {
            (*(void (__fastcall **)(__int64, __int64))(v25 + 8))(v24, 8277);
            v26 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 72LL))(v24, 0);
          }
          v127 = v26;
          v3 = v26;
          while ( 1 )
          {
LABEL_33:
            LOBYTE(v116) = 1;
            LOBYTE(v113) = 0;
            LOBYTE(v27) = 1;
            v28 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int (*)(int, int, int, int, char *), int, _DWORD, _DWORD))(*(_QWORD *)v23 + 120LL))(
                    v23,
                    v3,
                    v27,
                    0,
                    v113,
                    v116,
                    0,
                    0);
            v153 = v28;
            v140 = 0;
            if ( !v28 )
              goto LABEL_204;
            v135 = 4999;
            v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 120LL))(v28);
            v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 888LL))(v29);
            v136 = v30;
            v131 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 992LL))(v29);
            v126 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 952LL))(v29);
            v31 = 0;
            if ( v126 && !(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v29 + 392LL))(v29, 0) )
            {
              v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v29 + 360LL))(v29, 0, 0);
              if ( v32 )
              {
                while ( 1 )
                {
                  v223 = 0;
                  v225 = 0;
                  v226 = 0;
                  v228 = 1;
                  v227 = -1;
                  v224 = -2;
                  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 40LL))(v32, &v223);
                  if ( (v223 & 0x10000) != 0 )
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
                      LOBYTE(v116) = 1,
                      LOBYTE(v113) = 0,
                      LOBYTE(v34) = 1,
                      (v35 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _DWORD, int, _DWORD, _DWORD))(*(_QWORD *)v145 + 120LL))(
                               v145,
                               v33,
                               v34,
                               0,
                               (_DWORD)v113,
                               v116,
                               0,
                               0)) == 0)
                  || (v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 120LL))(v35)) == 0
                  || ((*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v36 + 16LL))(v36, v553), (v553[35] & 4) == 0) )
                {
                  v31 = 1;
                  v135 = 9999;
                  goto LABEL_45;
                }
              }
              v31 = 0;
            }
LABEL_45:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v153 + 280LL))(v153);
            if ( v30 == 2 && !v126 )
            {
              v208 = 0;
              v37 = (*(__int64 (__fastcall **)(struct IAutoXactFactory *))(*(_QWORD *)g_pAutoXactFactory + 8LL))(g_pAutoXactFactory);
              v208 = v37;
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
              v280 = v41;
              v42 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              v43 = *(_QWORD *)(v42 + 256);
              if ( !v43 )
              {
                SystemThread::MakeMiniSOSThread(0);
                v43 = *(_QWORD *)(v42 + 256);
              }
              v2 = v124;
              v44 = IRemoteDbProvisioning::Create(*(struct IMemObj **)(v43 + 1000), v41, v124);
              v314[2] = v44;
              (*(void (__fastcall **)(struct IRemoteDbProvisioning *, _QWORD))(*(_QWORD *)v44 + 80LL))(v44, v3);
              (**(void (__fastcall ***)(struct IRemoteDbProvisioning *, __int64))v44)(v44, 1);
              if ( v41 )
                (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v41)(v41, 1);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 32LL))(v37);
              (**(void (__fastcall ***)(__int64, __int64))v37)(v37, 1);
              goto LABEL_211;
            }
            if ( v131 )
            {
              if ( !v126 )
                utassert_fail(1u, "hasRemoteTarget", "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\stretchtask.cpp\"", 3158, 0);
              v45 = v124;
              DebugTraceStretchSchema(
                L"TaskStretchTable::ProcessTskPkt (%d, %d, %d) Data Reconciliation in Progress",
                v124,
                v3,
                *((unsigned __int8 *)v137 + 40));
              v135 = 0;
            }
            else
            {
              LODWORD(v113) = v30;
              v45 = v124;
              DebugTraceStretchSchema(
                L"TaskStretchTable::ProcessTskPkt (%d, %d, %d) migrationDirection = %d",
                v124,
                v3,
                *((unsigned __int8 *)v137 + 40),
                v113);
              if ( v30 == 1 && (unsigned int)SyncStretchMetadata(v124, v3) != 2 )
              {
                v47 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 72LL))(v24, 0);
                v2 = v124;
LABEL_205:
                v127 = v47;
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
                v135 = 500;
              }
            }
            if ( (unsigned int)(v30 - 1) > 1 && v131 != 1 )
            {
              v2 = v124;
LABEL_204:
              _mm_lfence();
              v47 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 72LL))(v24, 0);
              v132 = 0;
              goto LABEL_205;
            }
            v144 = 0;
            if ( dword_102EDCA0C < 0 )
            {
              v475 = 0x10000;
              v476 = 0;
              v477 = v480;
              v478 = &v481;
              v482 = 0;
              v479 = 0;
              v483 = 0;
              v480[0] = v484;
              v480[1] = 12;
              v484[0] = v45;
              v484[1] = v3;
              v484[2] = v30;
              XeSqlPkg::stretch_migration_batch_generation::Publish((XeSqlPkg::stretch_migration_batch_generation *)v474);
            }
            LOBYTE(v116) = 1;
            LOBYTE(v113) = 0;
            LOBYTE(ThreadLocalStoragePointer) = 1;
            v50 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, _QWORD, _DWORD, int, _DWORD, _DWORD))(*(_QWORD *)v145 + 120LL))(
                    v145,
                    v3,
                    ThreadLocalStoragePointer,
                    0,
                    (_DWORD)v113,
                    v116,
                    0,
                    0);
            v314[3] = v50;
            if ( v50 )
            {
              LOBYTE(v122) = v31;
              LOBYTE(v120) = v131 == 1;
              LODWORD(v113) = v30;
              MigrationBatch = GetMigrationBatch(v176, v145, v50, 20000, v113, &v144, &v210, v120, v122);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 280LL))(v50);
              _mm_lfence();
              if ( MigrationBatch >= 0 )
              {
                if ( !v131 )
                {
                  if ( v30 == 1 )
                  {
                    if ( (dword_102EDCA0C & 0x200000) != 0 )
                    {
                      v519 = 0x10000;
                      v520 = 0;
                      v521 = v524;
                      v522 = &v525;
                      v526 = 0;
                      v523 = 0;
                      v527 = 0;
                      v524[0] = v528;
                      v524[1] = 8;
                      v528[0] = v124;
                      v528[1] = v3;
                      XeSqlPkg::stretch_migration_start_migration::Publish((XeSqlPkg::stretch_migration_start_migration *)v518);
                    }
                  }
                  else if ( v30 == 2 && (dword_102EDCA0C & 0x400000) != 0 )
                  {
                    v530 = 0x10000;
                    v531 = 0;
                    v532 = v535;
                    v533 = &v536;
                    v537 = 0;
                    v534 = 0;
                    v538 = 0;
                    v535[0] = v539;
                    v535[1] = 8;
                    v539[0] = v124;
                    v539[1] = v3;
                    XeSqlPkg::stretch_migration_start_unmigration::Publish((XeSqlPkg::stretch_migration_start_unmigration *)v529);
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
                v133 = QuadPart;
                try
                {
                  ExcHandler::ExcHandler(
                    (ExcHandler *)v315,
                    0,
                    0,
                    0,
                    (int (*)(int, int, int, int, char *))hdl_backout,
                    0);
                  v148 = 0;
                  v58 = 0;
                  v139 = 0;
                  si128 = _mm_load_si128((const __m128i *)&_xmm);
                  v185 = 0;
                  v56 = 0;
                  v57 = 0;
                  v55 = v140;
                  v53 = v135;
                  while ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v145 + 1704LL))(v145) )
                  {
                    LOBYTE(v122) = v56;
                    LOBYTE(v121) = 0;
                    LOBYTE(v119) = v131 == 1;
                    v54 = MigrateStretchData(v124, v127, v53, v144, v210, v136, v119, v121, v122, &si128);
                    v55 = v54;
                    v140 = v54;
                    if ( v54 == -2147483647 )
                    {
                      if ( v57 < v167 )
                      {
                        v56 = 0;
                        v229 = 4194400;
                        v230 = 0;
                        v232 = 0;
                        v231 = 0;
                        v233 = 0;
                        SOS_Task::Sleep(1000, &v229);
                        v148 = ++v57;
                        if ( v136 == 1 && !v131 )
                          v135 = v53;
                        goto LABEL_95;
                      }
                    }
                    else if ( v54 > 0 )
                    {
                      v58 += v54;
                      v139 = v58;
                      if ( v131 != 1 )
                        v56 = 1;
                    }
                    ++v132;
                    v148 = 0;
                    v57 = 0;
                    if ( v54 <= 0 && v54 != -2147483647 )
                    {
LABEL_96:
                      v59 = *((_BYTE *)v211 + 41);
                      v60 = v182;
                      goto LABEL_98;
                    }
LABEL_95:
                    if ( v132 >= v149 )
                      goto LABEL_96;
                  }
                  v60 = v182;
                  *v182 = 0;
                  v59 = 0;
LABEL_98:
                  if ( v131 == 1 )
                  {
                    if ( v55 == -5 )
                      utassert_fail(
                        1u,
                        "x_signalToReconcileDataAsRemoteBehindLocal != rowsMigrated",
                        "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\stretchtask.cpp\"",
                        3346,
                        0);
                    if ( v58 )
                    {
                      v153 = 0x10000000DLL;
                      if ( (qword_102EDCA14 & 1) != 0 )
                      {
                        v168 = 1;
                        v314[4] = v335;
                        v335[0] = 0;
                        v335[1] = 1;
                        v336 = 0;
                        v337 = &v340;
                        v338 = &v344;
                        v345 = 0;
                        v346 = 0;
                        v339 = 0;
                        v347 = 0;
                        v314[5] = &v340;
                        v340 = v348;
                        v341 = 33;
                        v342 = 0;
                        v343 = 0;
                        v348[0] = v124;
                        v348[1] = v127;
                        v349 = 1;
                        v234 = &v159;
                        v215 = Base_PublicGlobals::sm_invariantTscAvailable;
                        if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          QueryPerformanceCounter(&v212);
                          v61 = (CSbTransportMgr *)v212.QuadPart;
                          v159 = (CSbTransportMgr *)v212.QuadPart;
                        }
                        else
                        {
                          v142 = (unsigned __int64)MEMORY[0x7FFE0008];
                          v61 = MEMORY[0x7FFE0008];
                          v159 = MEMORY[0x7FFE0008];
                          v55 = v140;
                          v58 = v139;
                        }
                        v235 = &v133;
                        v236 = &v159;
                        if ( v61 < v133 )
                        {
                          v62 = 0;
                          v142 = 0;
                        }
                        else
                        {
                          v62 = v61 - v133;
                          v142 = v62;
                        }
                        v183 = v62;
                        v237 = &v183;
                        if ( v62 == -1 )
                        {
                          v63 = -1;
                        }
                        else
                        {
                          v217 = Base_PublicGlobals::sm_invariantTscAvailable;
                          if ( Base_PublicGlobals::sm_invariantTscAvailable )
                          {
                            v238 = 1;
                            v221 = 3;
                            v222 = 1000;
                            v239 = 1000;
                            v63 = 1000 * v62 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                          }
                          else
                          {
                            v240 = &v183;
                            v186 = -4;
                            v187 = 10000;
                            v63 = v62 / 0x2710;
                            v241 = v62 / 0x2710;
                          }
                        }
                        v350 = v63;
                        v351 = 0;
                        v352 = 0;
                        v353 = v58;
                        XeSqlPkg::stretch_table_data_reconciliation_results_event::Publish((XeSqlPkg::stretch_table_data_reconciliation_results_event *)v334);
                      }
                    }
                    v64 = si128.m128i_i32[0];
                    if ( v185 != 1 )
                      v64 = si128.m128i_u16[0];
                    if ( !v64 && !v55 && *v60 )
                    {
                      v242 = &v147;
                      v147 = 0;
                      AutoSimpleXact::Begin(
                        (AutoSimpleXact *)&v147,
                        L"SetDataReconciliationStateToNotInProgress",
                        82,
                        0);
                      if ( v147 )
                        v65 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v147)[8])(v147);
                      else
                        v65 = 0;
                      v243 = v65;
                      v66 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset;
                      v67 = *(_QWORD *)(v66 + 256);
                      if ( !v67 )
                      {
                        SystemThread::MakeMiniSOSThread(0);
                        v67 = *(_QWORD *)(v66 + 256);
                      }
                      v68 = g_metadataFactory(
                              *(_QWORD *)(v67 + 1000),
                              v65,
                              "sql\\ntdbms\\stretch\\src\\stretchtask.cpp",
                              3382);
                      v244 = v68;
                      if ( !v68 )
                        ex_raise(148, 19, 16, 51);
                      v69 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v68 + 56LL))(
                              v68,
                              v124,
                              0,
                              0,
                              0,
                              0);
                      if ( !v69 )
                        ex_raise(148, 19, 16, 52);
                      LOBYTE(v117) = 1;
                      LOBYTE(v114) = 0;
                      LOBYTE(v70) = 2;
                      v71 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int, int, _DWORD, _DWORD))(*(_QWORD *)v69 + 120LL))(
                              v69,
                              v127,
                              v70,
                              0,
                              v114,
                              v117,
                              0,
                              0);
                      if ( !v71 )
                        ex_raise(148, 19, 16, 53);
                      v72 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v71 + 120LL))(v71);
                      if ( !v72 )
                        ex_raise(148, 19, 16, 54);
                      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v72 + 952LL))(v72) )
                      {
                        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v72 + 1000LL))(v72, 0);
                        if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v72 + 992LL))(v72) )
                        {
                          v73 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v72 + 648LL))(v72);
                          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v73 + 728LL))(v73, 0);
                        }
                      }
                      v245 = v68;
                      (**(void (__fastcall ***)(__int64, __int64))v68)(v68, 1);
                      ((void (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v147)[4])(v147);
                      v142 = 0x10000000000000BLL;
                      if ( (dword_102EDCA0C & 0x1000000) != 0 )
                      {
                        v154 = 1;
                        v246 = v431;
                        v431[0] = 0;
                        v431[1] = 1;
                        v432 = 0;
                        v433 = &v436;
                        v434 = &v440;
                        v441 = 0;
                        v442 = 0;
                        v435 = 0;
                        v443 = 0;
                        v247 = &v436;
                        v436 = v444;
                        v437 = 8;
                        v438 = 0;
                        v439 = 0;
                        v444[0] = v124;
                        v444[1] = v127;
                        XeSqlPkg::stretch_table_complete_data_reconciliation::Publish((XeSqlPkg::stretch_table_complete_data_reconciliation *)v430);
                      }
                      v74 = v147;
                      v248 = v147;
                      goto LABEL_139;
                    }
                    goto LABEL_141;
                  }
                  if ( v55 == -5 && v59 )
                  {
                    if ( v131 )
                      utassert_fail(
                        1u,
                        "x_srt_Remote_Data_Reconciliation_Not_In_Progress == remoteDataReconciliationState",
                        "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\stretchtask.cpp\"",
                        3459,
                        0);
                    v249 = &v146;
                    v146 = 0;
                    AutoSimpleXact::Begin((AutoSimpleXact *)&v146, L"SetDataReconciliationStateToInProgress", 76, 0);
                    if ( v146 )
                      v77 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v146)[8])(v146);
                    else
                      v77 = 0;
                    v250 = v77;
                    v78 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset;
                    v79 = *(_QWORD *)(v78 + 256);
                    if ( !v79 )
                    {
                      SystemThread::MakeMiniSOSThread(0);
                      v79 = *(_QWORD *)(v78 + 256);
                    }
                    v80 = g_metadataFactory(
                            *(_QWORD *)(v79 + 1000),
                            v77,
                            "sql\\ntdbms\\stretch\\src\\stretchtask.cpp",
                            3472);
                    v251 = v80;
                    if ( !v80 )
                      ex_raise(148, 19, 16, 57);
                    v81 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v80 + 56LL))(
                            v80,
                            v124,
                            0,
                            0,
                            0,
                            0);
                    if ( !v81 )
                      ex_raise(148, 19, 16, 58);
                    LOBYTE(v118) = 1;
                    LOBYTE(v115) = 0;
                    LOBYTE(v82) = 2;
                    v83 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int, int, _DWORD, _DWORD))(*(_QWORD *)v81 + 120LL))(
                            v81,
                            v127,
                            v82,
                            0,
                            v115,
                            v118,
                            0,
                            0);
                    if ( !v83 )
                      ex_raise(148, 19, 16, 59);
                    v84 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v83 + 120LL))(v83);
                    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v84 + 952LL))(v84) )
                      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v84 + 1000LL))(v84, 1);
                    v252 = v80;
                    (**(void (__fastcall ***)(__int64, __int64))v80)(v80, 1);
                    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v146)[4])(v146);
                    v178 = 11;
                    v179 = 0x800000;
                    if ( (dword_102EDCA0C & 0x800000) != 0 )
                    {
                      v155 = 1;
                      v253 = v446;
                      v446[0] = 0;
                      v446[1] = 1;
                      v447 = 0;
                      v448 = &v451;
                      v449 = &v455;
                      v456 = 0;
                      v457 = 0;
                      v450 = 0;
                      v458 = 0;
                      v254 = &v451;
                      v451 = v459;
                      v452 = 8;
                      v453 = 0;
                      v454 = 0;
                      v459[0] = v124;
                      v459[1] = v127;
                      XeSqlPkg::stretch_table_start_data_reconciliation::Publish((XeSqlPkg::stretch_table_start_data_reconciliation *)v445);
                    }
                    v74 = v146;
                    v255 = v146;
LABEL_139:
                    if ( v74 )
                      (**v74)(v74, 1);
LABEL_141:
                    v2 = v124;
                  }
                  else if ( v58 && v136 == 1 )
                  {
                    v180 = 12;
                    v181 = 0x40000000;
                    v2 = v124;
                    if ( (dword_102EDCA10 & 0x40000000) != 0 )
                    {
                      v156 = 1;
                      v256 = v355;
                      v355[0] = 0;
                      v355[1] = 1;
                      v356 = 0;
                      v357 = &v360;
                      v358 = &v364;
                      v365 = 0;
                      v366 = 0;
                      v359 = 0;
                      v367 = 0;
                      v257 = &v360;
                      v360 = v368;
                      v361 = 33;
                      v362 = 0;
                      v363 = 0;
                      v368[0] = v124;
                      v368[1] = v127;
                      v369 = 1;
                      v258 = &v160;
                      v188 = Base_PublicGlobals::sm_invariantTscAvailable;
                      if ( Base_PublicGlobals::sm_invariantTscAvailable )
                      {
                        QueryPerformanceCounter(&v214);
                        v85 = (CSbTransportMgr *)v214.QuadPart;
                        v160 = (CSbTransportMgr *)v214.QuadPart;
                      }
                      else
                      {
                        v143 = (unsigned __int64)MEMORY[0x7FFE0008];
                        v85 = MEMORY[0x7FFE0008];
                        v160 = MEMORY[0x7FFE0008];
                        v58 = v139;
                      }
                      v259 = &v133;
                      v260 = &v160;
                      if ( v85 < v133 )
                      {
                        v86 = 0;
                        v143 = 0;
                      }
                      else
                      {
                        v86 = v85 - v133;
                        v143 = v86;
                      }
                      v169 = v86;
                      v261 = &v169;
                      if ( v86 == -1 )
                      {
                        v87 = -1;
                      }
                      else
                      {
                        v190 = Base_PublicGlobals::sm_invariantTscAvailable;
                        if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          v262 = 1;
                          v191 = 3;
                          v192 = 1000;
                          v263 = 1000;
                          v87 = 1000 * v86 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                        }
                        else
                        {
                          v264 = &v169;
                          v204 = -4;
                          v193 = 10000;
                          v87 = v86 / 0x2710;
                          v265 = v86 / 0x2710;
                        }
                      }
                      v370 = v87;
                      v371 = 0;
                      v372 = 0;
                      v373 = v58;
                      XeSqlPkg::stretch_table_row_migration_results_event::Publish((XeSqlPkg::stretch_table_row_migration_results_event *)v354);
                    }
                  }
                  else
                  {
                    if ( v55 != -4 && !v58 )
                      goto LABEL_141;
                    if ( v136 != 2 )
                      goto LABEL_141;
                    v143 = 0x800000000000000CuLL;
                    if ( dword_102EDCA10 >= 0 )
                      goto LABEL_141;
                    v157 = 1;
                    v266 = v375;
                    v375[0] = 0;
                    v375[1] = 1;
                    v376 = 0;
                    v377 = &v380;
                    v378 = &v384;
                    v385 = 0;
                    v386 = 0;
                    v379 = 0;
                    v387 = 0;
                    v267 = &v380;
                    v380 = v388;
                    v381 = 33;
                    v382 = 0;
                    v383 = 0;
                    v2 = v124;
                    v388[0] = v124;
                    v388[1] = v127;
                    v389 = 1;
                    v268 = &v161;
                    v194 = Base_PublicGlobals::sm_invariantTscAvailable;
                    if ( Base_PublicGlobals::sm_invariantTscAvailable )
                    {
                      QueryPerformanceCounter(&v216);
                      v88 = (CSbTransportMgr *)v216.QuadPart;
                      v161 = (CSbTransportMgr *)v216.QuadPart;
                    }
                    else
                    {
                      v138 = (__int64)MEMORY[0x7FFE0008];
                      v88 = MEMORY[0x7FFE0008];
                      v161 = MEMORY[0x7FFE0008];
                      v58 = v139;
                    }
                    v269 = &v133;
                    v270 = &v161;
                    if ( v88 < v133 )
                    {
                      v89 = 0;
                      v138 = 0;
                    }
                    else
                    {
                      v89 = v88 - v133;
                      v138 = v89;
                    }
                    v170 = v89;
                    v271 = &v170;
                    if ( v89 == -1 )
                    {
                      v90 = -1;
                    }
                    else
                    {
                      v195 = Base_PublicGlobals::sm_invariantTscAvailable;
                      if ( Base_PublicGlobals::sm_invariantTscAvailable )
                      {
                        v272 = 1;
                        v196 = 3;
                        v197 = 1000;
                        v273 = 1000;
                        v90 = 1000 * v89 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                      }
                      else
                      {
                        v274 = &v170;
                        v198 = -4;
                        v199 = 10000;
                        v90 = v89 / 0x2710;
                        v275 = v89 / 0x2710;
                      }
                    }
                    v390 = v90;
                    v391 = 0;
                    v392 = 0;
                    v393 = v58;
                    XeSqlPkg::stretch_table_row_unmigration_results_event::Publish((XeSqlPkg::stretch_table_row_unmigration_results_event *)v374);
                  }
                  ExcHandler::~ExcHandler((ExcHandler *)v315);
                }
                catch ( SQLError v150 )
                {
                  try
                  {
                    ExceptionBackout::ExceptionBackout((ExceptionBackout *)v314, (const struct SQLError *)v150);
                    v96 = v150[0];
                    if ( v150[0] / 100 == 29 )
                    {
                      if ( v150[0] == 2905 )
                      {
                        v281 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset;
                        v282 = *(_QWORD *)(v281 + 80);
                        scierrlog(0x439Cu, L"StretchTableTask", (unsigned int)*(__int16 *)(v282 + 72));
                      }
                      else
                      {
                        if ( v152 != 1 )
                          v96 = LOWORD(v150[0]);
                        DefaultLocale = GetDefaultLocale();
                        LODWORD(v112) = v96;
                        if ( (int)StringCchPrintf_lW(v554, 0x100u, L"Exception %d", DefaultLocale, v112) < 0 )
                          utassert_fail(
                            1u,
                            "SUCCEEDED(hr)",
                            "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\stretchtask.cpp\"",
                            3599,
                            0);
                        v283 = v554;
                        scierrlog(0x429Du, L"StretchTableTask", v554);
                      }
LABEL_252:
                      v128 = 1;
                    }
                    else
                    {
                      v277 = (LARGE_INTEGER *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                               + SystemThread_TlsIndex)
                                             + SystemThread_TlsOffset);
                      v97 = *v277;
                      v220[1] = v97;
                      v279 = v97;
                      if ( v97.QuadPart )
                      {
                        v220[2] = v97;
                        if ( *(_BYTE *)(*(_QWORD *)(v97.QuadPart + 56) + 8LL) )
                          goto LABEL_252;
                      }
                    }
                    if ( v131 == 1 )
                    {
                      v138 = 0x10000000DLL;
                      if ( (qword_102EDCA14 & 1) != 0 )
                      {
                        v166 = 1;
                        v284 = v395;
                        v395[0] = 0;
                        v395[1] = 1;
                        v396 = 0;
                        v397 = &v400;
                        v398 = v404;
                        v404[132] = 0;
                        v404[133] = 0;
                        v399 = 0;
                        v405 = 0;
                        v285 = &v400;
                        v400 = v406;
                        v401 = 33;
                        v402 = 0;
                        v403 = 0;
                        v406[0] = v134;
                        v406[1] = v127;
                        v407 = 0;
                        v286 = &v162;
                        if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          QueryPerformanceCounter(&v218);
                          v100 = (CSbTransportMgr *)v218.QuadPart;
                          v162 = (CSbTransportMgr *)v218.QuadPart;
                        }
                        else
                        {
                          v100 = MEMORY[0x7FFE0008];
                          v162 = MEMORY[0x7FFE0008];
                        }
                        v287 = &v133;
                        v288 = &v162;
                        if ( v100 < v133 )
                        {
                          v101 = 0;
                          v138 = 0;
                        }
                        else
                        {
                          v101 = v100 - v133;
                          v138 = v101;
                        }
                        v171 = v101;
                        v289 = &v171;
                        if ( v101 == -1 )
                        {
                          v102 = -1;
                        }
                        else if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          v290 = Base_PublicGlobals::sm_QueryPerformanceFrequency;
                          v291 = 1;
                          v200 = 3;
                          v201 = 1000;
                          v292 = 1000;
                          v102 = 1000 * v101 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                        }
                        else
                        {
                          v293 = &v171;
                          v202 = -4;
                          v203 = 10000;
                          v102 = v101 / 0x2710;
                        }
                        v408 = v102;
                        if ( v152 == 1 )
                          v103 = v150[0];
                        else
                          v103 = LOWORD(v150[0]);
                        v409 = v103;
                        v410 = v151;
                        v411 = 0;
                        XeSqlPkg::stretch_table_data_reconciliation_results_event::Publish((XeSqlPkg::stretch_table_data_reconciliation_results_event *)&v394);
                      }
                    }
                    else if ( v136 == 1 )
                    {
                      v143 = 0x400000000000000CLL;
                      if ( (dword_102EDCA10 & 0x40000000) != 0 )
                      {
                        v158 = 1;
                        v294 = v413;
                        v413[0] = 0;
                        v413[1] = 1;
                        v414 = 0;
                        v415 = &v418;
                        v416 = v422;
                        v422[132] = 0;
                        v422[133] = 0;
                        v417 = 0;
                        v423 = 0;
                        v295 = &v418;
                        v418 = v424;
                        v419 = 33;
                        v420 = 0;
                        v421 = 0;
                        v424[0] = v134;
                        v424[1] = v127;
                        v425 = 0;
                        v296 = &v163;
                        if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          QueryPerformanceCounter(&v219);
                          v104 = (CSbTransportMgr *)v219.QuadPart;
                          v163 = (CSbTransportMgr *)v219.QuadPart;
                        }
                        else
                        {
                          v104 = MEMORY[0x7FFE0008];
                          v163 = MEMORY[0x7FFE0008];
                        }
                        v297 = &v133;
                        v298 = &v163;
                        if ( v104 < v133 )
                        {
                          v105 = 0;
                          v138 = 0;
                        }
                        else
                        {
                          v105 = v104 - v133;
                          v138 = v105;
                        }
                        v172 = v105;
                        v299 = &v172;
                        if ( v105 == -1 )
                        {
                          v106 = -1;
                        }
                        else if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          v300 = Base_PublicGlobals::sm_QueryPerformanceFrequency;
                          v301 = 1;
                          v189 = 3;
                          v205 = 1000;
                          v302 = 1000;
                          v106 = 1000 * v105 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                        }
                        else
                        {
                          v303 = &v172;
                          v206 = -4;
                          v207 = 10000;
                          v106 = v105 / 0x2710;
                        }
                        v426 = v106;
                        if ( v152 == 1 )
                          v107 = v150[0];
                        else
                          v107 = LOWORD(v150[0]);
                        v427 = v107;
                        v428 = v151;
                        v429 = 0;
                        XeSqlPkg::stretch_table_row_migration_results_event::Publish((XeSqlPkg::stretch_table_row_migration_results_event *)&v412);
                      }
                    }
                    else if ( v136 == 2 )
                    {
                      v142 = 0x800000000000000CuLL;
                      if ( dword_102EDCA10 < 0 )
                      {
                        v165 = 1;
                        v304 = v317;
                        v317[0] = 0;
                        v317[1] = 1;
                        v318 = 0;
                        v319 = &v322;
                        v320 = v326;
                        v326[132] = 0;
                        v326[133] = 0;
                        v321 = 0;
                        v327 = 0;
                        v305 = &v322;
                        v322 = v328;
                        v323 = 33;
                        v324 = 0;
                        v325 = 0;
                        v328[0] = v134;
                        v328[1] = v127;
                        v329 = 0;
                        v306 = &v164;
                        if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          QueryPerformanceCounter(v220);
                          v108 = (CSbTransportMgr *)v220[0].QuadPart;
                          v164 = (CSbTransportMgr *)v220[0].QuadPart;
                        }
                        else
                        {
                          v108 = MEMORY[0x7FFE0008];
                          v164 = MEMORY[0x7FFE0008];
                        }
                        v307 = &v133;
                        v308 = &v164;
                        if ( v108 < v133 )
                        {
                          v109 = 0;
                          v138 = 0;
                        }
                        else
                        {
                          v109 = v108 - v133;
                          v138 = v109;
                        }
                        v173 = v109;
                        v309 = &v173;
                        if ( v109 == -1 )
                        {
                          v110 = -1;
                        }
                        else if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          v310 = Base_PublicGlobals::sm_QueryPerformanceFrequency;
                          v311 = 1;
                          v213 = 3;
                          v180 = 1000;
                          v312 = 1000;
                          v110 = 1000 * v109 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                        }
                        else
                        {
                          v313 = &v173;
                          v178 = -4;
                          LODWORD(v153) = 10000;
                          v110 = v109 / 0x2710;
                        }
                        v330 = v110;
                        if ( v152 == 1 )
                          v111 = v150[0];
                        else
                          v111 = LOWORD(v150[0]);
                        v331 = v111;
                        v332 = v151;
                        v333 = 0;
                        XeSqlPkg::stretch_table_row_unmigration_results_event::Publish((XeSqlPkg::stretch_table_row_unmigration_results_event *)&v316);
                      }
                    }
                    ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v314);
                  }
                  catch ( ShortStackException )
                  {
                  }
                  v75 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset;
                  v76 = *(struct Worker **)(v75 + 256);
                  if ( !v76 )
                  {
                    SystemThread::MakeMiniSOSThread(0);
                    v76 = *(struct Worker **)(v75 + 256);
                  }
                  if ( *((_DWORD *)v76 + 139) )
                    ExceptionPostCatchActions(v76);
                  operator delete[](v144);
                  if ( v140 > 0 || v140 == -5 )
                  {
                    v125 = v129;
                    v2 = v134;
                    v124 = v134;
                    v3 = v127;
                    v24 = v174;
                    v91 = v175;
                    v137 = v175;
                    goto LABEL_207;
                  }
                  v125 = v129;
                  v2 = v134;
                  v124 = v134;
                  v24 = v174;
                  v137 = v175;
                  goto LABEL_204;
                }
                v276 = v144;
                operator delete[](v144);
                v3 = v127;
                goto LABEL_211;
              }
            }
            v3 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 72LL))(v24, 0);
            v127 = v3;
            operator delete[](v144);
            v2 = v124;
LABEL_206:
            v91 = v137;
LABEL_207:
            if ( v3 )
            {
              if ( v132 < v149 && !v128 )
              {
                v23 = v145;
                if ( *((_BYTE *)v91 + 41) )
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
    if ( v123 )
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
  if ( v141 )
  {
    v141 = 0;
    g_dbtableFactory[6](0xFFFFFFFFLL, 16);
  }
  v92 = v137;
  *((_BYTE *)v137 + 40) = v132 != 0;
  if ( *((_BYTE *)v92 + 41) )
  {
    v93 = ((__int64 (__fastcall *)(_QWORD))g_dbtableFactory[4])(v2);
    v94 = (DBTABLE *)v93;
    v95 = v93
       && (unsigned int)RecoveryUnit::IsUpdateable(*(RecoveryUnit **)(v93 + 4624))
       && !DBTABLE::IsMarkedReadOnly(v94, 0);
  }
  else
  {
    v95 = v123;
  }
  if ( *((_BYTE *)v92 + 41) && v95 )
  {
    if ( (dword_102EDCA0C & 0x2000) != 0 )
    {
      v541 = 0x10000;
      v542 = 0;
      v543 = v546;
      v544 = &v547;
      v548 = 0;
      v545 = 0;
      v549 = 0;
      v546[0] = v550;
      v546[1] = 8;
      v550[0] = v2;
      v550[1] = v3;
      XeSqlPkg::stretch_migration_requeue_migration::Publish((XeSqlPkg::stretch_migration_requeue_migration *)v540);
    }
    DebugTraceStretchSchema(L"EnqueueNextStretchObject (%d, %d, %d)", v2, v3, 0);
    TaskStretchTable::Enqueue((unsigned __int16)v2, v3, 0);
  }
  else if ( (dword_102EDCA0C & 0x4000) != 0 )
  {
    v461 = 0x10000;
    v462 = 0;
    v463 = v466;
    v464 = &v467;
    v468 = 0;
    v465 = 0;
    v469 = 0;
    v466[0] = &v470;
    v466[1] = 7;
    v470 = v2;
    v471 = !v95;
    v472 = v130 == 0;
    v473 = v125 == 0;
    XeSqlPkg::stretch_migration_dequeue_migration::Publish((XeSqlPkg::stretch_migration_dequeue_migration *)v460);
  }
  if ( v176 )
    (**v176)(v176, 1);
  if ( v177 )
    (**(void (__fastcall ***)(__int64, __int64))v177)(v177, 1);
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
