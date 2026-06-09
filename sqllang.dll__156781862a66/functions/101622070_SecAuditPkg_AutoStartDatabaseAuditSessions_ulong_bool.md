# SecAuditPkg::AutoStartDatabaseAuditSessions(ulong,bool)

- ea: `0x101622070`
- end: `0x101623c1c`
- name: `?AutoStartDatabaseAuditSessions@SecAuditPkg@@YAHK_N@Z`
- size: `7084`
- prototype: `__int64 __fastcall(SecAuditPkg *__hidden this, unsigned int, bool)`
- caller_count: `2`
- callee_count: `33`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x101319b60`
- `0x101624780`

## callees

- `0x100401070`
- `0x100401090`
- `0x1004012d0`
- `0x100401340`
- `0x1004022e0`
- `0x10040aaa0`
- `0x1007d40d0`
- `0x10083a060`
- `0x100860500`
- `0x100a4f220`
- `0x100a4f2f0`
- `0x100a4f340`
- `0x100a58800`
- `0x100a589b0`
- `0x100a58b60`
- `0x100b35150`
- `0x100cd5db0`
- `0x10138ac10`
- `0x1013bc0f0`
- `0x101621f40`
- `0x101622070`
- `0x101625a10`
- `0x101625cc0`
- `0x101625db0`
- `0x1016265c0`
- `0x101626800`
- `0x1016268d0`
- `0x101628780`
- `0x101628e10`
- `0x101628ee0`
- `0x101629380`
- `0x101e88d30`
- `0x101e88db0`

## import_xrefs

- `SHLWAPI!StrStrW` at `0x101622cca`
- `SHLWAPI!StrStrW` at `0x101622ce7`
- `SHLWAPI!StrStrW` at `0x101622d05`
- `SHLWAPI!StrStrW` at `0x101622ea2`
- `SHLWAPI!StrStrW` at `0x101622cca`
- `SHLWAPI!StrStrW` at `0x101622ce7`
- `SHLWAPI!StrStrW` at `0x101622d05`
- `SHLWAPI!StrStrW` at `0x101622ea2`
- `SHLWAPI!StrCmpW` at `0x101622eae`
- `SHLWAPI!StrCmpW` at `0x101622eae`
- `ole32!CoCreateGuid` at `0x101622fe1`
- `ole32!CoCreateGuid` at `0x101622fe1`
- `ole32!StringFromGUID2` at `0x101622ba1`
- `ole32!StringFromGUID2` at `0x101623037`
- `ole32!StringFromGUID2` at `0x101622ba1`
- `ole32!StringFromGUID2` at `0x101623037`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x101622a26`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101622136`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1016221a4`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101622323`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1016225a0`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101622730`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101622919`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101623bb5`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x101622200`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x1016232c0`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x10162357c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101622be9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101622be9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101622a8a`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101622a8a`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101623556`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101623642`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101623b99`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101623556`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101623642`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101623b99`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016223df`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016223f8`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016223df`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016223f8`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101622420`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101622420`
- `sqldk!SystemThread_TlsIndex` at `0x1016223a7`
- `sqldk!SystemThread_TlsIndex` at `0x101622da7`
- `sqldk!SystemThread_TlsIndex` at `0x1016231d7`
- `sqldk!SystemThread_TlsIndex` at `0x101623327`
- `sqldk!SystemThread_TlsIndex` at `0x101623474`
- `sqldk!SystemThread_TlsIndex` at `0x101623516`
- `sqldk!SystemThread_TlsIndex` at `0x101623602`
- `sqldk!SystemThread_TlsIndex` at `0x101623a62`
- `sqldk!SystemThread_TlsIndex` at `0x101623b61`
- `sqldk!SystemThread_TlsOffset` at `0x1016223b0`
- `sqldk!SystemThread_TlsOffset` at `0x101622db8`
- `sqldk!SystemThread_TlsOffset` at `0x1016231e8`
- `sqldk!SystemThread_TlsOffset` at `0x101623330`
- `sqldk!SystemThread_TlsOffset` at `0x101623485`
- `sqldk!SystemThread_TlsOffset` at `0x10162351f`
- `sqldk!SystemThread_TlsOffset` at `0x10162360b`
- `sqldk!SystemThread_TlsOffset` at `0x101623a73`
- `sqldk!SystemThread_TlsOffset` at `0x101623b6a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101623af8`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101623af8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016223cb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101623538`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101623624`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101623b83`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016223cb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101623538`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101623624`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101623b83`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x1016223ef`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x1016223ef`
- `sqldk!??_V@YAXPEAX@Z` at `0x101623b07`
- `sqldk!??_V@YAXPEAX@Z` at `0x101623b07`
- `sqlmin!?IsRbIoSecondaryRoleOnlyForGeoSecondary@RecoveryUnit@@QEBA_NXZ` at `0x101622386`
- `sqlmin!?IsRbIoSecondaryRoleOnlyForGeoSecondary@RecoveryUnit@@QEBA_NXZ` at `0x101622386`
- `sqlmin!?Release@AutoDbLock@@QEAAXXZ` at `0x101622153`
- `sqlmin!?Release@AutoDbLock@@QEAAXXZ` at `0x101622340`
- `sqlmin!?Release@AutoDbLock@@QEAAXXZ` at `0x1016225be`
- `sqlmin!?Release@AutoDbLock@@QEAAXXZ` at `0x10162274d`
- `sqlmin!?Release@AutoDbLock@@QEAAXXZ` at `0x101622936`
- `sqlmin!?Release@AutoDbLock@@QEAAXXZ` at `0x101623bd2`
- `sqlmin!?Release@AutoDbLock@@QEAAXXZ` at `0x101622153`
- `sqlmin!?Release@AutoDbLock@@QEAAXXZ` at `0x101622340`
- `sqlmin!?Release@AutoDbLock@@QEAAXXZ` at `0x1016225be`
- `sqlmin!?Release@AutoDbLock@@QEAAXXZ` at `0x10162274d`
- `sqlmin!?Release@AutoDbLock@@QEAAXXZ` at `0x101622936`
- `sqlmin!?Release@AutoDbLock@@QEAAXXZ` at `0x101623bd2`
- `sqlmin!?Acquire@AutoDbLock@@QEAA?AW4LCK_RESULT@@KW4LCK_MODE@@K_NW4EDBRefType@@@Z` at `0x10162218a`
- `sqlmin!?Acquire@AutoDbLock@@QEAA?AW4LCK_RESULT@@KW4LCK_MODE@@K_NW4EDBRefType@@@Z` at `0x10162218a`
- `sqlmin!?IsRbIoForwarderMode@RecoveryUnit@@QEBA_NXZ` at `0x101622288`
- `sqlmin!?IsRbIoForwarderMode@RecoveryUnit@@QEBA_NXZ` at `0x101622288`
- `sqlmin!?ShouldEnableAuditing@HadrRecoveryCallbacks@@SA_NKAEAH0@Z` at `0x1016222b1`
- `sqlmin!?ShouldEnableAuditing@HadrRecoveryCallbacks@@SA_NKAEAH0@Z` at `0x1016222b1`
- `sqlmin!?IsVldbSharedStorageSecondary@RecoveryUnit@@QEBA_NXZ` at `0x101622241`
- `sqlmin!?IsVldbSharedStorageSecondary@RecoveryUnit@@QEBA_NXZ` at `0x101622241`
- `sqlmin!?IsCOWReplicaDatabase@DBTABLE@@QEBAHXZ` at `0x10162226a`
- `sqlmin!?IsCOWReplicaDatabase@DBTABLE@@QEBAHXZ` at `0x101622379`
- `sqlmin!?IsCOWReplicaDatabase@DBTABLE@@QEBAHXZ` at `0x10162226a`
- `sqlmin!?IsCOWReplicaDatabase@DBTABLE@@QEBAHXZ` at `0x101622379`
- `sqlmin!?LogicalDbNameInternal@DBTABLE@@QEBAPEB_WXZ` at `0x10162378d`
- `sqlmin!?LogicalDbNameInternal@DBTABLE@@QEBAPEB_WXZ` at `0x10162395e`
- `sqlmin!?LogicalDbNameInternal@DBTABLE@@QEBAPEB_WXZ` at `0x10162378d`
- `sqlmin!?LogicalDbNameInternal@DBTABLE@@QEBAPEB_WXZ` at `0x10162395e`
- `sqlmin!?lck_StandardHandler@@YAXW4LCK_RESULT@@W4ABORT_AND_LCK_EXCEPTIONS@@@Z` at `0x10162219b`
- `sqlmin!?lck_StandardHandler@@YAXW4LCK_RESULT@@W4ABORT_AND_LCK_EXCEPTIONS@@@Z` at `0x10162219b`
- `sqlmin!GetXdbServerGlobals` at `0x101622e8e`
- `sqlmin!GetXdbServerGlobals` at `0x101622e8e`
- `sqlmin!?UpdateTdServiceIsEnabledProperty@HadrRecoveryCallbacks@@SAXK_N@Z` at `0x1016235ce`
- `sqlmin!?UpdateTdServiceIsEnabledProperty@HadrRecoveryCallbacks@@SAXK_N@Z` at `0x1016235ce`
- `sqlmin!?IsHadrSecondaryRoleOnlyForGeoSecondary@HadrRecoveryCallbacks@@SA_NPEAVRecoveryUnit@@@Z` at `0x101622391`
- `sqlmin!?IsHadrSecondaryRoleOnlyForGeoSecondary@HadrRecoveryCallbacks@@SA_NPEAVRecoveryUnit@@@Z` at `0x101622391`

## string_xrefs

- `0x101622d83`: `Database Audit: close geo-replica audit session on becoming primary database. Database ID: %d, Audit ID: %d, Audit Guid: %s, Status:%d`
- `0x101622a19`: `sql\ntdbms\msql\security\src\xe\secauditpkg.cpp`
- `0x101622a7b`: `sql\ntdbms\msql\security\src\xe\secauditpkg.cpp`
- `0x101622bd7`: `sql\ntdbms\msql\security\src\xe\secauditpkg.cpp`
- `0x101622117`: `Database Audit: audit sessions are not started database is not accessible. Database ID: %d`
- `0x101622514`: `Database Audit: auditSessionsWaitToRefreshAutoMutex is already acquired , so there is a thread waiting to refresh audit sessions. Database ID: %lu, error code: %lu`
- `0x1016222d6`: `Database Audit: audit sessions are not started. Database ID: %d, is forwarder: %d, is forwarder on database copy: %d`
- `0x101623ab8`: `Database Audit: AutoStartDatabaseAuditSessions completed, Database ID: %lu`

## pseudocode

```c
// Hidden C++ exception states: #wind=25 #try_helpers=1
__int64 __fastcall SecAuditPkg::AutoStartDatabaseAuditSessions(SecAuditPkg *this, char a2, __int64 a3)
{
  __int64 v3; // r13
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r12
  __int64 v8; // r14
  struct RecoveryUnit *v9; // rdx
  __int64 v10; // r8
  DBTABLE *v11; // rcx
  bool v12; // zf
  unsigned int v13; // eax
  bool ShouldEnableAuditing; // al
  DBTABLE *v15; // rcx
  bool IsHadrSecondaryRoleOnlyForGeoSecondary; // al
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v18; // rcx
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rbx
  PerProcessGlobals *ClientProcessGlobals; // rax
  struct MemoryClerk **DefaultMemoryClerksForNode; // rbx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r8
  __int64 v28; // rcx
  SecAuditPkg *MemObject; // rdi
  int *v30; // r8
  bool v31; // bl
  unsigned int v32; // ecx
  __int64 v33; // r14
  int v34; // ebx
  unsigned int v35; // eax
  int v36; // r15d
  int v37; // r12d
  int v38; // ebx
  __int64 v39; // rdi
  int v40; // ebx
  __int64 v41; // rdi
  unsigned int v42; // eax
  __int64 v43; // r15
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // r14
  SecAuditPkg::AutoAuditGuidsHash *v47; // rax
  SecAuditPkg::AutoAuditGuidsHash *v48; // rcx
  __int64 v49; // rax
  struct IMemObj *v50; // rax
  struct IMemObj *v51; // r12
  GUID v52; // xmm6
  __int64 *v53; // rax
  __int64 *v54; // r9
  SecAuditPkg::AutoAuditGuidsHash *v55; // r8
  __int64 v56; // rdx
  WCHAR *v57; // r15
  bool v58; // bl
  bool v59; // r15
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // r9
  const WCHAR *XdbServerGlobals; // rbx
  PCWSTR v64; // r15
  const WCHAR *v65; // rax
  unsigned int AuditSession; // ebx
  __int64 v67; // r9
  unsigned int v68; // eax
  bool v69; // cl
  __int64 v70; // r8
  __int64 v71; // rbx
  _QWORD *v72; // rax
  unsigned __int8 v73; // al
  void *v74; // r15
  __int64 v75; // r9
  int v76; // eax
  unsigned __int64 v77; // rax
  int v78; // r9d
  __int64 v79; // r9
  __int64 v80; // rbx
  struct Worker *v81; // rcx
  unsigned int v82; // eax
  __int64 v83; // rbx
  struct Worker *v84; // rcx
  _QWORD *v85; // rax
  __int64 v86; // rcx
  _QWORD *v87; // rax
  _QWORD *v88; // rcx
  DBTABLE *v89; // rbx
  const wchar_t *v90; // rax
  _QWORD *v91; // rax
  __int64 v92; // rcx
  _QWORD *v93; // rax
  _QWORD *v94; // rcx
  DBTABLE *v95; // rdx
  const wchar_t *v96; // rax
  struct BaseXact *v97; // rax
  __int64 v98; // r9
  SecAuditPkg::AutoAuditGuidsHash *v99; // rbx
  __int64 v100; // rcx
  __int64 v101; // rbx
  struct Worker *v102; // rcx
  int v103; // [rsp+20h] [rbp-1438h]
  int (*v104)(int, int, int, int, char *); // [rsp+20h] [rbp-1438h]
  int (*v105)(int, int, int, int, char *); // [rsp+20h] [rbp-1438h]
  int (*v106)(int, int, int, int, char *); // [rsp+20h] [rbp-1438h]
  int (*v107)(int, int, int, int, char *); // [rsp+20h] [rbp-1438h]
  struct Worker *v108; // [rsp+28h] [rbp-1430h]
  __int64 v109; // [rsp+30h] [rbp-1428h]
  bool IsVldbSharedStorageSecondary; // [rsp+40h] [rbp-1418h]
  unsigned int v111; // [rsp+44h] [rbp-1414h] BYREF
  unsigned int v112; // [rsp+48h] [rbp-1410h] BYREF
  int v113; // [rsp+4Ch] [rbp-140Ch] BYREF
  bool v114; // [rsp+50h] [rbp-1408h]
  int IsLocalSecondaryReplica; // [rsp+54h] [rbp-1404h]
  unsigned int v116[2]; // [rsp+58h] [rbp-1400h] BYREF
  PCWSTR pszFirst; // [rsp+60h] [rbp-13F8h]
  unsigned int v118; // [rsp+68h] [rbp-13F0h] BYREF
  unsigned int v119; // [rsp+6Ch] [rbp-13ECh]
  unsigned int v120; // [rsp+70h] [rbp-13E8h]
  int v121; // [rsp+78h] [rbp-13E0h]
  unsigned int v122; // [rsp+7Ch] [rbp-13DCh] BYREF
  int v123; // [rsp+80h] [rbp-13D8h]
  unsigned int v124; // [rsp+84h] [rbp-13D4h]
  __int64 v125; // [rsp+88h] [rbp-13D0h]
  int v126; // [rsp+90h] [rbp-13C8h]
  SecAuditPkg *v127; // [rsp+98h] [rbp-13C0h]
  bool v128; // [rsp+A0h] [rbp-13B8h]
  int started; // [rsp+A4h] [rbp-13B4h]
  unsigned int v130; // [rsp+A8h] [rbp-13B0h]
  BOOL v131; // [rsp+ACh] [rbp-13ACh]
  __int64 v132; // [rsp+B0h] [rbp-13A8h]
  wchar_t *v133; // [rsp+B8h] [rbp-13A0h]
  __int64 v134; // [rsp+C0h] [rbp-1398h] BYREF
  _DWORD v135[6]; // [rsp+C8h] [rbp-1390h] BYREF
  unsigned int v136; // [rsp+E0h] [rbp-1378h] BYREF
  int v137; // [rsp+E4h] [rbp-1374h]
  struct IMemObj *v138; // [rsp+E8h] [rbp-1370h]
  SecAuditPkg::AutoAuditGuidsHash *v139; // [rsp+F0h] [rbp-1368h]
  __int64 v140; // [rsp+F8h] [rbp-1360h]
  int v141; // [rsp+100h] [rbp-1358h] BYREF
  int v142; // [rsp+104h] [rbp-1354h]
  __int64 v143; // [rsp+108h] [rbp-1350h]
  struct _GUID *v144; // [rsp+110h] [rbp-1348h] BYREF
  __int64 v145; // [rsp+118h] [rbp-1340h]
  int v146; // [rsp+120h] [rbp-1338h] BYREF
  int v147; // [rsp+124h] [rbp-1334h]
  int v148; // [rsp+128h] [rbp-1330h] BYREF
  int v149; // [rsp+12Ch] [rbp-132Ch]
  int v150; // [rsp+130h] [rbp-1328h] BYREF
  int v151; // [rsp+134h] [rbp-1324h]
  __int64 v152; // [rsp+138h] [rbp-1320h]
  int v153; // [rsp+140h] [rbp-1318h] BYREF
  int v154; // [rsp+144h] [rbp-1314h]
  __int64 v155; // [rsp+148h] [rbp-1310h]
  int v156; // [rsp+150h] [rbp-1308h]
  unsigned int v157; // [rsp+158h] [rbp-1300h]
  int v158; // [rsp+160h] [rbp-12F8h]
  int v159; // [rsp+168h] [rbp-12F0h]
  int v160; // [rsp+170h] [rbp-12E8h]
  int v161; // [rsp+178h] [rbp-12E0h]
  unsigned int v162; // [rsp+180h] [rbp-12D8h]
  __int64 v163; // [rsp+188h] [rbp-12D0h]
  unsigned int v164; // [rsp+190h] [rbp-12C8h]
  __int64 v165; // [rsp+198h] [rbp-12C0h]
  _WORD *v166; // [rsp+1A0h] [rbp-12B8h]
  int v167; // [rsp+1A8h] [rbp-12B0h]
  int v168; // [rsp+1ACh] [rbp-12ACh]
  int v169; // [rsp+1B0h] [rbp-12A8h]
  _BYTE v170[40]; // [rsp+1B8h] [rbp-12A0h] BYREF
  SecAuditPkg::AutoAuditGuidsHash *v171; // [rsp+1E0h] [rbp-1278h]
  __int64 *v172; // [rsp+1E8h] [rbp-1270h]
  __int64 *v173; // [rsp+1F0h] [rbp-1268h]
  __int64 *v174; // [rsp+1F8h] [rbp-1260h]
  __int64 v175; // [rsp+200h] [rbp-1258h]
  __int64 v176; // [rsp+208h] [rbp-1250h]
  __int64 v177; // [rsp+210h] [rbp-1248h]
  __int64 *v178; // [rsp+218h] [rbp-1240h]
  SecAuditPkg *v179; // [rsp+220h] [rbp-1238h]
  __int64 v180; // [rsp+228h] [rbp-1230h]
  __int64 v181; // [rsp+230h] [rbp-1228h]
  struct Worker *v182; // [rsp+238h] [rbp-1220h]
  __int64 v183; // [rsp+240h] [rbp-1218h]
  struct Worker *v184; // [rsp+248h] [rbp-1210h]
  _WORD *v185; // [rsp+250h] [rbp-1208h]
  __int64 v186; // [rsp+258h] [rbp-1200h]
  __int64 *v187; // [rsp+260h] [rbp-11F8h]
  SecAuditPkg *v188; // [rsp+268h] [rbp-11F0h]
  _BYTE v189[16]; // [rsp+270h] [rbp-11E8h] BYREF
  _QWORD v190[9]; // [rsp+280h] [rbp-11D8h] BYREF
  _BYTE v191[24]; // [rsp+2C8h] [rbp-1190h] BYREF
  _BYTE v192[24]; // [rsp+2E0h] [rbp-1178h] BYREF
  _BYTE v193[40]; // [rsp+2F8h] [rbp-1160h] BYREF
  _BYTE v194[48]; // [rsp+320h] [rbp-1138h] BYREF
  char v195[8]; // [rsp+350h] [rbp-1108h] BYREF
  __int16 v196; // [rsp+358h] [rbp-1100h]
  __int16 v197; // [rsp+35Ah] [rbp-10FEh]
  int v198; // [rsp+360h] [rbp-10F8h]
  __int64 **v199; // [rsp+368h] [rbp-10F0h]
  char *v200; // [rsp+370h] [rbp-10E8h]
  __int64 v201; // [rsp+378h] [rbp-10E0h]
  __int64 *v202; // [rsp+380h] [rbp-10D8h] BYREF
  int v203; // [rsp+388h] [rbp-10D0h]
  __int16 v204; // [rsp+38Ch] [rbp-10CCh]
  __int16 v205; // [rsp+38Eh] [rbp-10CAh]
  char v206; // [rsp+390h] [rbp-10C8h] BYREF
  int v207; // [rsp+5A0h] [rbp-EB8h]
  int v208; // [rsp+5A4h] [rbp-EB4h]
  __int64 v209; // [rsp+5A8h] [rbp-EB0h]
  __int64 v210; // [rsp+5B0h] [rbp-EA8h] BYREF
  __int16 v211; // [rsp+5B8h] [rbp-EA0h]
  _BOOL8 v212; // [rsp+5BAh] [rbp-E9Eh]
  char v213[8]; // [rsp+5D0h] [rbp-E88h] BYREF
  __int16 v214; // [rsp+5D8h] [rbp-E80h]
  __int16 v215; // [rsp+5DAh] [rbp-E7Eh]
  int v216; // [rsp+5E0h] [rbp-E78h]
  __int64 **v217; // [rsp+5E8h] [rbp-E70h]
  char *v218; // [rsp+5F0h] [rbp-E68h]
  __int64 v219; // [rsp+5F8h] [rbp-E60h]
  __int64 *v220; // [rsp+600h] [rbp-E58h] BYREF
  int v221; // [rsp+608h] [rbp-E50h]
  __int16 v222; // [rsp+60Ch] [rbp-E4Ch]
  __int16 v223; // [rsp+60Eh] [rbp-E4Ah]
  char v224; // [rsp+610h] [rbp-E48h] BYREF
  int v225; // [rsp+820h] [rbp-C38h]
  int v226; // [rsp+824h] [rbp-C34h]
  __int64 v227; // [rsp+828h] [rbp-C30h]
  __int64 v228; // [rsp+830h] [rbp-C28h] BYREF
  __int16 v229; // [rsp+838h] [rbp-C20h]
  __int64 v230; // [rsp+83Ah] [rbp-C1Eh]
  _BYTE v231[24]; // [rsp+850h] [rbp-C08h] BYREF
  _QWORD *v232; // [rsp+868h] [rbp-BF0h]
  bool v233; // [rsp+AB0h] [rbp-9A8h]
  bool v234; // [rsp+AB1h] [rbp-9A7h]
  __int64 v235; // [rsp+AB2h] [rbp-9A6h]
  __int64 v236; // [rsp+ABAh] [rbp-99Eh]
  _BYTE v237[24]; // [rsp+AF0h] [rbp-968h] BYREF
  _QWORD *v238; // [rsp+B08h] [rbp-950h]
  bool v239; // [rsp+D50h] [rbp-708h]
  bool v240; // [rsp+D51h] [rbp-707h]
  __int64 v241; // [rsp+D52h] [rbp-706h]
  __int64 v242; // [rsp+D5Ah] [rbp-6FEh]
  GUID rguid; // [rsp+D90h] [rbp-6C8h] BYREF
  GUID pguid; // [rsp+DA0h] [rbp-6B8h] BYREF
  int v245; // [rsp+DB0h] [rbp-6A8h] BYREF
  unsigned __int8 v246; // [rsp+DB8h] [rbp-6A0h]
  _BYTE v247[16]; // [rsp+DD0h] [rbp-688h] BYREF
  int v248; // [rsp+DE0h] [rbp-678h]
  int v249; // [rsp+DE4h] [rbp-674h]
  char v250; // [rsp+1128h] [rbp-330h]
  OLECHAR sz[8]; // [rsp+1160h] [rbp-2F8h] BYREF
  __int128 v252; // [rsp+1170h] [rbp-2E8h]
  __int128 v253; // [rsp+1180h] [rbp-2D8h]
  __int128 v254; // [rsp+1190h] [rbp-2C8h]
  __int64 v255; // [rsp+11A0h] [rbp-2B8h]
  int v256; // [rsp+11A8h] [rbp-2B0h]
  __int16 v257; // [rsp+11ACh] [rbp-2ACh]
  OLECHAR v258[8]; // [rsp+11B0h] [rbp-2A8h] BYREF
  __int128 v259; // [rsp+11C0h] [rbp-298h]
  __int128 v260; // [rsp+11D0h] [rbp-288h]
  __int128 v261; // [rsp+11E0h] [rbp-278h]
  __int64 v262; // [rsp+11F0h] [rbp-268h]
  int v263; // [rsp+11F8h] [rbp-260h]
  __int16 v264; // [rsp+11FCh] [rbp-25Ch]
  _WORD v265[264]; // [rsp+1200h] [rbp-258h] BYREF

  v176 = -2;
  v3 = (unsigned int)this;
  v120 = (unsigned int)this;
  v135[0] = -1;
  v135[2] = 0;
  v135[4] = 0;
  v113 = 0;
  if ( byte_102EDCAC2 )
  {
    if ( !CAutoDb::FUse((CAutoDb *)&v113, (unsigned int)this, 0, 1, 0, 0) )
    {
      log_unlocalized_systemmetadata(
        L"Database Audit: audit sessions are not started database is not accessible. Database ID: %d",
        (unsigned int)v3);
      if ( v113 )
      {
        v113 = 0;
        ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
      }
      if ( v135[0] >= 0 )
        AutoDbLock::Release((AutoDbLock *)v135);
      return 0;
    }
  }
  else if ( byte_102EDCAF5 )
  {
    LOBYTE(a3) = 3;
    v5 = AutoDbLock::Acquire(v135, (unsigned int)this, a3, 0xFFFFFFFFLL, 0, 17);
    if ( v5 < 0 )
    {
      _mm_lfence();
      LOBYTE(v6) = 40;
      lck_StandardHandler((unsigned int)v5, v6);
    }
  }
  v7 = g_dbtableFactory[4]((unsigned int)v3);
  v140 = v7;
  v112 = 0;
  IsLocalSecondaryReplica = 0;
  IsVldbSharedStorageSecondary = 0;
  v122 = 0;
  v130 = 1;
  v137 = 0;
  v123 = 0;
  v111 = 0;
  v143 = *(_QWORD *)(v7 + 4624);
  v8 = v143;
  ExcHandler::ExcHandler((ExcHandler *)v170, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_prntbackout, 0);
  v125 = v7 + 808;
  v126 = 0;
  if ( v8 )
    IsVldbSharedStorageSecondary = RecoveryUnit::IsVldbSharedStorageSecondary((RecoveryUnit *)v8);
  if ( !byte_102EDCAF4 )
  {
LABEL_27:
    if ( byte_102EDCAF5 )
    {
      IsLocalSecondaryReplica = SecAuditPkg::IsLocalSecondaryReplica((SecAuditPkg *)v8, v9);
      if ( IsLocalSecondaryReplica )
      {
        if ( v8 )
        {
          v15 = *(DBTABLE **)(v8 + 1712);
          if ( (*((_BYTE *)v15 + 60) & 1) == 0 || DBTABLE::IsCOWReplicaDatabase(v15) )
            IsHadrSecondaryRoleOnlyForGeoSecondary = HadrRecoveryCallbacks::IsHadrSecondaryRoleOnlyForGeoSecondary((struct RecoveryUnit *)v8);
          else
            IsHadrSecondaryRoleOnlyForGeoSecondary = RecoveryUnit::IsRbIoSecondaryRoleOnlyForGeoSecondary((RecoveryUnit *)v8);
          v112 = IsHadrSecondaryRoleOnlyForGeoSecondary;
        }
      }
    }
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v18 = SystemThread_TlsIndex;
    v19 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v20 = *(_QWORD *)(v19 + 256);
    if ( !v20 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v20 = *(_QWORD *)(v19 + 256);
    }
    v21 = *(_QWORD *)(v20 + 992);
    ClientProcessGlobals = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals(v18, ThreadLocalStoragePointer, v10);
    DefaultMemoryClerksForNode = PerProcessGlobals::GetDefaultMemoryClerksForNode(
                                   ClientProcessGlobals,
                                   *(_WORD *)(v21 + 160));
    SOS_OS::GetClientProcessGlobals(v25, v24, v26);
    v27 = (__int64)*DefaultMemoryClerksForNode + 64;
    if ( !*DefaultMemoryClerksForNode )
      v27 = 0;
    LOWORD(v103) = 128;
    MemObject = (SecAuditPkg *)MemoryObjectFactory::CreateMemObject(254, 1, v27, 8, v103);
    v127 = MemObject;
    v179 = MemObject;
    if ( !MemObject )
    {
      LOBYTE(v28) = 83;
      ex_raise_oom(v28);
    }
    if ( byte_102EDCADD )
    {
      if ( !v112 && !IsLocalSecondaryReplica )
      {
        v31 = IsVldbSharedStorageSecondary;
        if ( !IsVldbSharedStorageSecondary )
          goto LABEL_98;
      }
      v32 = 10 * SecAuditPkg::GetUserDatabasesCount();
      if ( v32 >= 0x3C )
      {
        if ( v32 > 0x258 )
          v32 = 600;
      }
      else
      {
        v32 = 60;
      }
      v124 = 1000 * v32;
      v33 = v7 + 864;
      v155 = v7 + 864;
      v34 = 0;
      v156 = 0;
      v35 = SOS_Mutex::Wait(v7 + 864, 0, qword_102FDD108, 0);
      v131 = v35;
      v36 = 0;
      v37 = 0;
      v121 = 0;
      if ( !v35 )
      {
        v34 = 1;
        v156 = 1;
        v36 = 1;
        v37 = 1;
        v121 = 1;
      }
      v164 = v35;
      if ( v35 )
      {
        if ( v35 == 258 )
        {
          log_unlocalized_systemmetadata(
            L"Database Audit: auditSessionsWaitToRefreshAutoMutex is already acquired , so there is a thread waiting to re"
             "fresh audit sessions. Database ID: %lu, error code: %lu",
            (unsigned int)v3,
            258);
          while ( v36 )
          {
            *(_QWORD *)(v33 + 48) = 0;
            EventAutoInternal<SuspendQueueSLock>::Signal(v33, 0);
            v36 = --v34;
            v156 = v34;
          }
          if ( MemObject )
            (*(void (__fastcall **)(SecAuditPkg *))(*(_QWORD *)MemObject + 16LL))(MemObject);
          v38 = v126;
          v39 = v125;
          while ( v38 )
          {
            *(_QWORD *)(v39 + 48) = 0;
            EventAutoInternal<SuspendQueueSLock>::Signal(v39, 0);
            v126 = --v38;
          }
          ExcHandler::~ExcHandler((ExcHandler *)v170);
          if ( v113 )
          {
            v113 = 0;
            ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
          }
          if ( v135[0] >= 0 )
            AutoDbLock::Release((AutoDbLock *)v135);
          return 1;
        }
        else
        {
          log_unlocalized_systemmetadata(
            L"Database Audit: Failed to acquire auditSessionsWaitToRefreshAutoMutex, Database ID: %lu, error code: %lu",
            (unsigned int)v3,
            v35);
          v141 = 3;
          v142 = 256;
          if ( (dword_102F21DBC & 0x100) != 0 )
          {
            v196 = 0;
            v197 = 1;
            v198 = 0;
            v199 = &v202;
            v200 = &v206;
            v207 = 0;
            v208 = 0;
            v201 = 0;
            v209 = 0;
            v202 = &v210;
            v203 = 18;
            v204 = 0;
            v205 = 0;
            v210 = v3;
            v211 = 1;
            v212 = v131;
            XeCloudPkg::audit_auto_start_task_failed::Publish((XeCloudPkg::audit_auto_start_task_failed *)v195);
          }
          while ( v34 )
          {
            *(_QWORD *)(v33 + 48) = 0;
            EventAutoInternal<SuspendQueueSLock>::Signal(v33, 0);
            v156 = --v34;
          }
          if ( MemObject )
            (*(void (__fastcall **)(SecAuditPkg *))(*(_QWORD *)MemObject + 16LL))(MemObject);
          v40 = v126;
          v41 = v125;
          while ( v40 )
          {
            *(_QWORD *)(v41 + 48) = 0;
            EventAutoInternal<SuspendQueueSLock>::Signal(v41, 0);
            v126 = --v40;
          }
          ExcHandler::~ExcHandler((ExcHandler *)v170);
          if ( v113 )
          {
            v113 = 0;
            ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
          }
          if ( v135[0] >= 0 )
            AutoDbLock::Release((AutoDbLock *)v135);
          return 0;
        }
      }
      log_unlocalized_systemmetadata(
        L"Database Audit: auditSessionsWaitToRefreshAutoMutex acquired, Database ID: %lu",
        (unsigned int)v3);
      v42 = SOS_Mutex::Wait(v125, v124, qword_102FDCA20, 0);
      v43 = v42;
      if ( !v42 )
      {
        v126 = 1;
        v37 = v121;
      }
      while ( v37 )
      {
        v186 = v33;
        *(_QWORD *)(v33 + 48) = 0;
        EventAutoInternal<SuspendQueueSLock>::Signal(v33, 0);
        v37 = --v34;
        v156 = v34;
      }
      if ( (_DWORD)v43 )
      {
        log_unlocalized_systemmetadata(
          L"Database Audit: failed to acquire auditSessionsExecRefreshAutoMutex within %d milliseconds, Database ID: %lu, error code: %lu",
          v124,
          (unsigned int)v3,
          (unsigned int)v43);
        v140 = 0x10000000003LL;
        if ( (dword_102F21DBC & 0x100) != 0 )
        {
          v214 = 0;
          v215 = 1;
          v216 = 0;
          v217 = &v220;
          v218 = &v224;
          v225 = 0;
          v226 = 0;
          v219 = 0;
          v227 = 0;
          v220 = &v228;
          v221 = 18;
          v222 = 0;
          v223 = 0;
          v228 = v3;
          v229 = 2;
          v230 = v43;
          XeCloudPkg::audit_auto_start_task_failed::Publish((XeCloudPkg::audit_auto_start_task_failed *)v213);
        }
        if ( MemObject )
          (*(void (__fastcall **)(SecAuditPkg *))(*(_QWORD *)MemObject + 16LL))(MemObject);
        while ( v126 )
        {
          v44 = v125;
          *(_QWORD *)(v125 + 48) = 0;
          EventAutoInternal<SuspendQueueSLock>::Signal(v44, 0);
          --v126;
        }
        ExcHandler::~ExcHandler((ExcHandler *)v170);
        if ( v113 )
        {
          v113 = 0;
          ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
        }
        if ( v135[0] >= 0 )
          AutoDbLock::Release((AutoDbLock *)v135);
        return 0;
      }
      log_unlocalized_systemmetadata(
        L"Database Audit: auditSessionsExecRefreshAutoMutex acquired, Database ID: %lu",
        (unsigned int)v3);
    }
    v31 = IsVldbSharedStorageSecondary;
LABEL_98:
    v144 = 0;
    v136 = 0;
    if ( byte_102EDCADB && (v112 || IsLocalSecondaryReplica || v31) )
      SecAuditPkg::AuditXESessionManager::PopulateListWithAuditSessionsGuidsForDatabase(v3, &v144, &v136);
    wcscpy((wchar_t *)v116, L"田");
    SecurityConfig::GetConfigurationValueInt(
      (SecurityConfig *)L"AppAuditingXESessionTimeout",
      (const wchar_t *)v116,
      v30);
    v139 = 0;
    v187 = &v134;
    v134 = 0;
    AutoSimpleXact::Begin((AutoSimpleXact *)&v134, L"SecAuditPkg::AutoStartDatabaseAuditSessions", 86, 0);
    if ( v134 )
      v45 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v134 + 64LL))(v134);
    else
      v45 = 0;
    v188 = MemObject;
    v163 = g_metadataFactory(MemObject, v45, "sql\\ntdbms\\msql\\security\\src\\xe\\secauditpkg.cpp", 585);
    v46 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v163 + 56LL))(
            v163,
            (unsigned int)v3,
            0,
            0,
            0,
            0);
    v132 = v46;
    v167 = 589;
    v190[4] = MemObject;
    v47 = (SecAuditPkg::AutoAuditGuidsHash *)operator new(
                                               0x28u,
                                               MemObject,
                                               "sql\\ntdbms\\msql\\security\\src\\xe\\secauditpkg.cpp",
                                               589,
                                               3u);
    v190[5] = v47;
    if ( v47 )
      v48 = (SecAuditPkg::AutoAuditGuidsHash *)SecAuditPkg::AutoAuditGuidsHash::AutoAuditGuidsHash(v47, MemObject);
    else
      v48 = 0;
    v49 = v145;
    if ( v48 )
      v49 = 0;
    v145 = v49;
    v139 = v48;
    v111 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          do
          {
            if ( !(*(unsigned __int8 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v46 + 864LL))(v46, &v111) )
            {
              if ( v163 )
                (**(void (__fastcall ***)(__int64, __int64))v163)(v163, 1);
              if ( byte_102EDCADE && v137 )
              {
                if ( v134 )
                  v97 = (struct BaseXact *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v134 + 64LL))(v134);
                else
                  v97 = 0;
                InvalidateAuditCache(v3, v97, 1);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v134 + 32LL))(v134);
              }
              if ( byte_102EDCADB && (v112 || IsLocalSecondaryReplica || IsVldbSharedStorageSecondary) && !v122 )
              {
                CAutoLockTimeout::CAutoLockTimeout((CAutoLockTimeout *)&v141, v116[0]);
                SecAuditPkg::AuditXESessionManager::StopDatabaseAuditSessionsWithNoMetadata(v144, v136, v139);
                if ( v141 )
                {
                  v98 = 8LL * SystemThread_TlsIndex;
                  v166 = *(_WORD **)(SystemThread_TlsOffset
                                   + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v98));
                  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                                    + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v98)
                                                    + 8LL)
                                        + 104LL)
                            + 24LL) = v142;
                  MemObject = v127;
                }
              }
              log_unlocalized_systemmetadata(
                L"Database Audit: AutoStartDatabaseAuditSessions completed, Database ID: %lu",
                (unsigned int)v3);
              if ( v134 )
                (**(void (__fastcall ***)(__int64, __int64))v134)(v134, 1);
              v99 = v139;
              if ( v139 )
              {
                SecAuditPkg::AutoAuditGuidsHash::~AutoAuditGuidsHash(v139);
                operator delete(v99, 0x28u);
              }
              operator delete[](v144);
              if ( MemObject )
                (*(void (__fastcall **)(SecAuditPkg *))(*(_QWORD *)MemObject + 16LL))(MemObject);
              while ( v126 )
              {
                v100 = v125;
                *(_QWORD *)(v125 + 48) = 0;
                EventAutoInternal<SuspendQueueSLock>::Signal(v100, 0);
                --v126;
              }
              ExcHandler::~ExcHandler((ExcHandler *)v170);
              v101 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset;
              v102 = *(struct Worker **)(v101 + 256);
              if ( !v102 )
              {
                SystemThread::MakeMiniSOSThread(0);
                v102 = *(struct Worker **)(v101 + 256);
              }
              if ( *((_DWORD *)v102 + 139) )
                ExceptionPostCatchActions(v102);
              if ( v113 )
              {
                v113 = 0;
                ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
              }
              if ( v135[0] >= 0 )
                AutoDbLock::Release((AutoDbLock *)v135);
              return v130;
            }
            v50 = (struct IMemObj *)(*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v46 + 848LL))(
                                      v46,
                                      v111,
                                      16708,
                                      0);
            v51 = v50;
            v138 = v50;
          }
          while ( !v50 );
          (*(void (__fastcall **)(struct IMemObj *, int *))(*(_QWORD *)v50 + 32LL))(v50, &v245);
          SecAuditPkg::AuditSession::AuditSession((SecAuditPkg::AuditSession *)v247, MemObject);
          rguid = *(GUID *)(*(__int64 (__fastcall **)(struct IMemObj *))(*(_QWORD *)v51 + 16LL))(v51);
          *(_OWORD *)sz = 0;
          v252 = 0;
          v253 = 0;
          v254 = 0;
          v255 = 0;
          v256 = 0;
          v257 = 0;
          StringFromGUID2(&rguid, sz, 39);
          v52 = rguid;
          v171 = v139;
          v168 = 1925;
          v53 = (__int64 *)operator new(
                             0x20u,
                             *(struct IMemObj **)v139,
                             1,
                             "sql\\ntdbms\\msql\\security\\src\\xe\\secauditpkg.cpp",
                             1925,
                             3u);
          v54 = v53;
          v172 = v53;
          if ( v53 )
          {
            v173 = v53;
            *v53 = 0;
            v53[1] = 0;
          }
          else
          {
            v54 = 0;
          }
          v174 = v54;
          if ( v54 )
          {
            *((GUID *)v54 + 1) = v52;
            v55 = v139;
            v175 = v54[2] ^ v54[3];
            v169 = v175 ^ HIDWORD(v175);
            v157 = *((_DWORD *)v139 + 5)
                 & ((((unsigned int)v175 ^ HIDWORD(v175)) >> 10)
                  + (((unsigned int)v175 ^ HIDWORD(v175)) >> 20)
                  + (v175 ^ HIDWORD(v175)));
            v56 = *((_QWORD *)v139 + 1) + 16LL * v157;
            v152 = v56;
            v54[1] = *(_QWORD *)(v56 + 8);
            **(_QWORD **)(v56 + 8) = v54;
            *(_QWORD *)(v56 + 8) = v54;
            *v54 = v56;
            ++*((_DWORD *)v55 + 6);
          }
          v57 = *(WCHAR **)(**(__int64 (__fastcall ***)(struct IMemObj *))v51)(v51);
          pszFirst = v57;
          v133 = v57;
          v131 = v245 == 19541;
          v58 = StrStrW(v57, L"_GeoSecondary") != 0;
          v128 = v58;
          v59 = StrStrW(v57, L"ServerAudit") != 0;
          LOBYTE(v121) = v59;
          v114 = StrStrW(pszFirst, L"ThreatDetection") != 0;
          if ( v112 || IsVldbSharedStorageSecondary )
            break;
          if ( !v58 )
            goto LABEL_135;
          if ( SecAuditPkg::AuditXESessionManager::GetAuditSession(&rguid, (struct SecAuditPkg::AuditSession *)v247) )
          {
            CAutoLockTimeout::CAutoLockTimeout((CAutoLockTimeout *)&v146, v116[0]);
            LODWORD(v104) = SecAuditPkg::AuditXESessionManager::CloseSession(&rguid);
            log_unlocalized_systemmetadata(
              L"Database Audit: close geo-replica audit session on becoming primary database. Database ID: %d, Audit ID: %"
               "d, Audit Guid: %s, Status:%d",
              (unsigned int)v3,
              v111,
              sz,
              v104);
            if ( v146 )
            {
              v62 = 8LL * SystemThread_TlsIndex;
              v152 = *(_QWORD *)(SystemThread_TlsOffset
                               + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v62));
              v158 = v147;
              *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                                + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v62)
                                                + 8LL)
                                    + 104LL)
                        + 24LL) = v147;
              MemObject = v127;
              v46 = v132;
            }
          }
          else
          {
            log_unlocalized_systemmetadata(
              L"Database Audit: skip geo-replica audit session startup on primary database. Database ID: %d, Audit ID: %d, Audit Guid: %s",
              (unsigned int)v3,
              v111,
              sz);
          }
          SecAuditPkg::AuditSession::~AuditSession((SecAuditPkg::AuditSession *)v247);
        }
        if ( v58 )
          break;
        if ( v59 )
        {
          log_unlocalized(
            L"Database Audit: Skip primary server level audit session startup on secondary database since primary server a"
             "udit should not apply on replicas. Database ID: %d, Audit ID: %d, Audit Name: %ls",
            (unsigned int)v3,
            v111,
            pszFirst);
          SecAuditPkg::AuditSession::~AuditSession((SecAuditPkg::AuditSession *)v247);
        }
        else
        {
LABEL_135:
          AuditSession = SecAuditPkg::AuditXESessionManager::GetAuditSession(
                           &rguid,
                           (struct SecAuditPkg::AuditSession *)v247);
          v119 = AuditSession;
          LODWORD(v109) = IsVldbSharedStorageSecondary;
          LODWORD(v108) = v112;
          LODWORD(v104) = v246;
          log_unlocalized_systemmetadata(
            L"Database Audit: Updating Audit ID: %d. Database ID: %d, Is Session Present : %d, Is Audit Enabled: %d, Is GE"
             "O replica: %d, Is Named Replica: %d,",
            v111,
            (unsigned int)v3,
            AuditSession,
            v104,
            v108,
            v109);
          if ( AuditSession )
          {
            if ( !byte_102EDCADE || v248 == (_DWORD)v3 )
            {
              v68 = v112;
              v69 = IsVldbSharedStorageSecondary;
            }
            else
            {
              v68 = v112;
              v69 = IsVldbSharedStorageSecondary;
              if ( !v112 && !IsLocalSecondaryReplica && !IsVldbSharedStorageSecondary )
              {
                LOBYTE(v67) = 1;
                v51 = (struct IMemObj *)(*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v46 + 848LL))(
                                          v46,
                                          v111,
                                          16708,
                                          v67);
                v138 = v51;
                CoCreateGuid(&pguid);
                *(_OWORD *)v258 = 0;
                v259 = 0;
                v260 = 0;
                v261 = 0;
                v262 = 0;
                v263 = 0;
                v264 = 0;
                StringFromGUID2(&pguid, v258, 39);
                v118 = 0;
                while ( (*(unsigned __int8 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v46 + 1392LL))(
                          v46,
                          &v118) )
                {
                  LOBYTE(v70) = 1;
                  v71 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v46 + 1408LL))(v46, v118, v70);
                  v72 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v71 + 24LL))(v71);
                  if ( *v72 == *(_QWORD *)&rguid.Data1 && v72[1] == *(_QWORD *)rguid.Data4 )
                  {
                    if ( (*(unsigned __int8 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v71 + 56LL))(v71, &pguid) )
                      log_unlocalized_systemmetadata(
                        L"Database Audit: Successfully changed audit Guid for Specification ID: d% , Database ID: %d, Audi"
                         "t ID: %d, Guid: %s, New Guid: %s",
                        v118,
                        (unsigned int)v3,
                        v111,
                        sz,
                        v258);
                    else
                      log_unlocalized_systemmetadata(
                        L"Database Audit: Failed to changed audit Guid for Specification ID: d% , Database ID: %d, Audit ID: %d, Guid: %s",
                        v118,
                        (unsigned int)v3,
                        v111,
                        sz);
                  }
                }
                v73 = (*(__int64 (__fastcall **)(struct IMemObj *, GUID *))(*(_QWORD *)v51 + 112LL))(v51, &pguid);
                v137 = v73;
                if ( v73 )
                  log_unlocalized_systemmetadata(
                    L"Database Audit: Successfully changed audit Guid. Database ID: %d, Audit ID: %d, Guid: %s, New Guid: %s",
                    (unsigned int)v3,
                    v111,
                    sz,
                    v258);
                else
                  log_unlocalized_systemmetadata(
                    L"Database Audit: Failed to change audit Guid. Database ID: %d, Audit ID: %d, Guid: %s",
                    (unsigned int)v3,
                    v111,
                    sz);
                rguid = *(GUID *)(*(__int64 (__fastcall **)(struct IMemObj *))(*(_QWORD *)v51 + 16LL))(v51);
                AuditSession = 0;
                v119 = 0;
                goto LABEL_153;
              }
            }
            if ( !byte_102EDCABA || v68 || IsLocalSecondaryReplica || v69 || !v246 )
            {
              CAutoLockTimeout::CAutoLockTimeout((CAutoLockTimeout *)&v148, v116[0]);
              SecAuditPkg::AuditXESessionManager::CloseSession(&rguid);
              AuditSession = 0;
              v119 = 0;
              LODWORD(v105) = IsVldbSharedStorageSecondary;
              log_unlocalized_systemmetadata(
                L"Database Audit: Audit session was stopped, Database ID: %d, Audit ID: %d, Is GEO replica: %d, Is Named Replica: %d,",
                (unsigned int)v3,
                v111,
                v112,
                v105);
              if ( v148 )
              {
                v79 = 8LL * SystemThread_TlsIndex;
                v152 = *(_QWORD *)(SystemThread_TlsOffset
                                 + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v79));
                v159 = v149;
                *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                                  + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v79)
                                                  + 8LL)
                                      + 104LL)
                          + 24LL) = v149;
                MemObject = v127;
                v46 = v132;
                v51 = v138;
                v74 = v133;
                AuditSession = v119;
                goto LABEL_154;
              }
            }
            else if ( *((_BYTE *)qword_102EF3550 + 130) )
            {
              if ( v143 )
                v249 = *(_DWORD *)(v143 + 7256);
              else
                v249 = 0;
            }
          }
LABEL_153:
          v74 = (void *)pszFirst;
LABEL_154:
          if ( a2 )
          {
            if ( AuditSession )
            {
              if ( v250 )
              {
                CAutoLockTimeout::CAutoLockTimeout((CAutoLockTimeout *)&v150, v116[0]);
                SecAuditPkg::AuditXESessionManager::CloseSession(&rguid);
                AuditSession = 0;
                v119 = 0;
                if ( v150 )
                {
                  v75 = 8LL * SystemThread_TlsIndex;
                  v152 = *(_QWORD *)(SystemThread_TlsOffset
                                   + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v75));
                  v160 = v151;
                  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                                    + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v75)
                                                    + 8LL)
                                        + 104LL)
                            + 24LL) = v151;
                  MemObject = v127;
                  v46 = v132;
                  v51 = v138;
                  v74 = v133;
                  AuditSession = v119;
                }
              }
            }
          }
          if ( v246 && !AuditSession )
          {
            v76 = 0;
            if ( v131 )
              v76 = (*(__int64 (__fastcall **)(struct IMemObj *, _WORD *, __int64))(*(_QWORD *)v51 + 72LL))(
                      v51,
                      v265,
                      520);
            v77 = v76 & 0xFFFFFFFE;
            if ( v77 >= 0x20A )
              _report_rangecheckfailure();
            *(_WORD *)((char *)v265 + v77) = 0;
            started = 0;
            v177 = 0;
            try
            {
              _mm_lfence();
              ExcHandler::ExcHandler(
                (ExcHandler *)v193,
                0,
                0,
                0,
                (int (*)(int, int, int, int, char *))hdl_prntbackout,
                0);
              CAutoLockTimeout::CAutoLockTimeout((CAutoLockTimeout *)&v153, v116[0]);
              started = SecAuditPkg::StartAuditSession(v127, v138, (struct IMEDAudit *const)1, v78);
              if ( v153 )
              {
                v178 = (__int64 *)(SystemThread_TlsOffset
                                 + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex));
                v165 = *v178;
                v161 = v154;
                v180 = SystemThread_TlsOffset
                     + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex);
                v181 = *(_QWORD *)(v180 + 8);
                *(_DWORD *)(*(_QWORD *)(v181 + 104) + 24LL) = v154;
              }
              ExcHandler::~ExcHandler((ExcHandler *)v193);
            }
            catch ( SQLError v191 )
            {
              try
              {
                ExceptionBackout::ExceptionBackout((ExceptionBackout *)v189, (const struct SQLError *)v191);
                started = 0;
                ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v189);
              }
              catch ( ShortStackException )
              {
              }
              LODWORD(v3) = v120;
            }
            v80 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            v81 = *(struct Worker **)(v80 + 256);
            if ( !v81 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v81 = *(struct Worker **)(v80 + 256);
            }
            v182 = v81;
            if ( *((_DWORD *)v81 + 139) )
              ExceptionPostCatchActions(v81);
            v12 = started == 0;
            _mm_lfence();
            if ( v12 )
            {
              v130 = 0;
              LODWORD(v106) = IsVldbSharedStorageSecondary;
              log_unlocalized_systemmetadata(
                L"Database Audit: Failed to auto start audit session. Database ID: %d, Audit ID: %d, Is GEO replica: %d, I"
                 "s Named Replica: %d,",
                (unsigned int)v3,
                v111,
                v112,
                v106);
              pszFirst = (PCWSTR)0x8000000003LL;
              if ( (dword_102F21DBC & 0x80u) != 0 )
              {
                _mm_lfence();
                XeCloudPkg::audit_auto_start_failed::audit_auto_start_failed((XeCloudPkg::audit_auto_start_failed *)v237);
                LODWORD(pszFirst) = v112;
                v239 = v112 != 0;
                v240 = IsVldbSharedStorageSecondary;
                v241 = (unsigned int)v3;
                v242 = v111;
                v91 = v238;
                v238[2] = &rguid;
                *((_DWORD *)v91 + 6) = 16;
                *((_WORD *)v91 + 14) = 4;
                *((_WORD *)v91 + 15) = 0;
                v74 = v133;
                XeCloudPkg::audit_auto_start_failed::Setaudit_name((XeCloudPkg::audit_auto_start_failed *)v237, v133);
                v166 = v265;
                v92 = -1;
                do
                  ++v92;
                while ( v265[v92] );
                v93 = v238;
                v238[6] = v265;
                *((_DWORD *)v93 + 14) = 2 * v92;
                *((_WORD *)v93 + 30) = 6;
                *((_WORD *)v93 + 31) = 0;
                v94 = v238;
                v95 = (DBTABLE *)v140;
                v238[8] = v140 + 580;
                *((_DWORD *)v94 + 18) = 16;
                *((_WORD *)v94 + 38) = 7;
                *((_WORD *)v94 + 39) = 0;
                v96 = DBTABLE::LogicalDbNameInternal(v95);
                XeCloudPkg::audit_auto_start_failed::Setlogical_database_name(
                  (XeCloudPkg::audit_auto_start_failed *)v237,
                  v96);
                XeCloudPkg::audit_auto_start_failed::Publish((XeCloudPkg::audit_auto_start_failed *)v237);
                goto LABEL_199;
              }
            }
            else
            {
              v183 = 0;
              try
              {
                ExcHandler::ExcHandler(
                  (ExcHandler *)v194,
                  0,
                  0,
                  0,
                  (int (*)(int, int, int, int, char *))hdl_prntbackout,
                  0);
                if ( v114 && byte_102EDCAC7 && byte_102EDCBEC )
                {
                  _mm_lfence();
                  v82 = (*(__int64 (__fastcall **)(struct IMemObj *))(*(_QWORD *)v138 + 24LL))(v138);
                  HadrRecoveryCallbacks::UpdateTdServiceIsEnabledProperty(v82, 1);
                }
                ExcHandler::~ExcHandler((ExcHandler *)v194);
              }
              catch ( SQLError v192 )
              {
                try
                {
                  _mm_lfence();
                  ExceptionBackout::ExceptionBackout((ExceptionBackout *)v190, (const struct SQLError *)v192);
                  log_unlocalized(
                    L"Threat Detection: failed setting is_td_enabled for DW. Database ID: %lu, Audit ID: %lu, Audit Name: %ls",
                    v120,
                    v111,
                    v133);
                  ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v190);
                }
                catch ( ShortStackException )
                {
                }
                LODWORD(v3) = v120;
              }
              v83 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              v84 = *(struct Worker **)(v83 + 256);
              if ( !v84 )
              {
                SystemThread::MakeMiniSOSThread(0);
                v84 = *(struct Worker **)(v83 + 256);
              }
              v184 = v84;
              if ( *((_DWORD *)v84 + 139) )
                ExceptionPostCatchActions(v84);
              LODWORD(v107) = IsVldbSharedStorageSecondary;
              log_unlocalized_systemmetadata(
                L"Database Audit: Audit session was successfully started. Database ID: %d, Audit ID: %d, Is GEO replica: %"
                 "d, Is Named Replica: %d,",
                (unsigned int)v3,
                v111,
                v112,
                v107);
              v145 = 0x4000000003LL;
              if ( (dword_102F21DBC & 0x40) != 0 )
              {
                _mm_lfence();
                XeCloudPkg::audit_auto_start_failed::audit_auto_start_failed((XeCloudPkg::audit_auto_start_failed *)v231);
                v162 = v112;
                v233 = v112 != 0;
                v234 = IsVldbSharedStorageSecondary;
                v235 = (unsigned int)v3;
                v236 = v111;
                v85 = v232;
                v232[2] = &rguid;
                *((_DWORD *)v85 + 6) = 16;
                *((_WORD *)v85 + 14) = 4;
                *((_WORD *)v85 + 15) = 0;
                v74 = v133;
                XeCloudPkg::audit_auto_start_failed::Setaudit_name((XeCloudPkg::audit_auto_start_failed *)v231, v133);
                v185 = v265;
                v86 = -1;
                do
                  ++v86;
                while ( v265[v86] );
                v87 = v232;
                v232[6] = v265;
                *((_DWORD *)v87 + 14) = 2 * v86;
                *((_WORD *)v87 + 30) = 6;
                *((_WORD *)v87 + 31) = 0;
                v88 = v232;
                v89 = (DBTABLE *)v140;
                v232[8] = v140 + 580;
                *((_DWORD *)v88 + 18) = 16;
                *((_WORD *)v88 + 38) = 7;
                *((_WORD *)v88 + 39) = 0;
                v90 = DBTABLE::LogicalDbNameInternal(v89);
                XeCloudPkg::audit_auto_start_failed::Setlogical_database_name(
                  (XeCloudPkg::audit_auto_start_failed *)v231,
                  v90);
                XeCloudPkg::audit_auto_start_succeeded::Publish((XeCloudPkg::audit_auto_start_succeeded *)v231);
                goto LABEL_199;
              }
            }
            v74 = v133;
LABEL_199:
            v46 = v132;
            MemObject = v127;
          }
          if ( v123 )
          {
            qword_102FDCCE8 = 0;
            EventAutoInternal<SuspendQueueSLock>::Signal(&off_102FDCCB8, 0);
            v123 = 0;
            log_unlocalized(
              L"Database Audit: auditSessionMutex released. Database ID: %lu, Audit ID: %lu, Audit Name: %ls",
              (unsigned int)v3,
              v111,
              v74);
          }
          SecAuditPkg::AuditSession::~AuditSession((SecAuditPkg::AuditSession *)v247);
        }
      }
      if ( !IsVldbSharedStorageSecondary || byte_102EDCAF6 )
      {
        XdbServerGlobals = (const WCHAR *)GetXdbServerGlobals(v61, v60);
        v64 = pszFirst;
        v65 = StrStrW(pszFirst, XdbServerGlobals);
        if ( !StrCmpW(XdbServerGlobals, v65) )
          goto LABEL_135;
        log_unlocalized(
          L"Database Audit: skip geo-replica audit session startup on replica database due to logical server mismatch. Dat"
           "abase ID: %d, Audit ID: %d, Audit Name: %ls",
          (unsigned int)v3,
          v111,
          v64);
        SecAuditPkg::AuditSession::~AuditSession((SecAuditPkg::AuditSession *)v247);
      }
      else
      {
        log_unlocalized(
          L"Database Audit: skip startup of server level audit session for named-replica, because the feature switch [AppA"
           "uditingSupportServerAuditingOnNamedReplicas] is OFF. Database ID: %d, Audit ID: %d, Audit Name: %ls",
          (unsigned int)v3,
          v111,
          pszFirst);
        SecAuditPkg::AuditSession::~AuditSession((SecAuditPkg::AuditSession *)v247);
      }
    }
  }
  if ( v8 )
  {
    v11 = *(DBTABLE **)(v8 + 1712);
    if ( (*((_BYTE *)v11 + 60) & 1) != 0 && !DBTABLE::IsCOWReplicaDatabase(v11) )
    {
      v124 = 1;
      if ( !*(_BYTE *)(v8 + 8272) || (v12 = !RecoveryUnit::IsRbIoForwarderMode((RecoveryUnit *)v8), v13 = 1, v12) )
        v13 = 0;
      v112 = v13;
      v122 = 0;
      goto LABEL_27;
    }
  }
  ShouldEnableAuditing = HadrRecoveryCallbacks::ShouldEnableAuditing(v3, (int *)&v112, (int *)&v122);
  v124 = ShouldEnableAuditing;
  if ( ShouldEnableAuditing )
    goto LABEL_27;
  log_unlocalized_systemmetadata(
    L"Database Audit: audit sessions are not started. Database ID: %d, is forwarder: %d, is forwarder on database copy: %d",
    (unsigned int)v3,
    v112,
    v122);
  ExcHandler::~ExcHandler((ExcHandler *)v170);
  if ( v113 )
  {
    v113 = 0;
    ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
  }
  if ( v135[0] >= 0 )
    AutoDbLock::Release((AutoDbLock *)v135);
  return 1;
}

```

## disassembly

```asm
0x101622070  mov     [rsp+arg_8], dl
0x101622074  push    rdi
0x101622075  push    r12
0x101622077  push    r13
0x101622079  push    r14
0x10162207b  push    r15
0x10162207d  mov     eax, 1430h
0x101622082  call    _alloca_probe
0x101622087  sub     rsp, rax
0x10162208a  mov     [rsp+1458h+var_1250], 0FFFFFFFFFFFFFFFEh
0x101622096  mov     [rsp+1458h+arg_10], rbx
0x10162209e  mov     [rsp+1458h+arg_18], rsi
0x1016220a6  movaps  [rsp+1458h+var_38], xmm6
0x1016220ae  mov     rax, cs:__security_cookie
0x1016220b5  xor     rax, rsp
0x1016220b8  mov     [rsp+1458h+var_48], rax
0x1016220c0  mov     r13d, ecx
0x1016220c3  mov     [rsp+1458h+var_13E8], r13d
0x1016220c8  mov     [rsp+1458h+var_1390], 0FFFFFFFFh
0x1016220d3  xor     esi, esi
0x1016220d5  mov     [rsp+1458h+var_1388], esi
0x1016220dc  mov     [rsp+1458h+var_1380], esi
0x1016220e3  mov     [rsp+1458h+var_140C], esi
0x1016220e7  cmp     cs:byte_102EDCAC2, sil
0x1016220ee  jz      short loc_101622160
0x1016220f0  mov     dword ptr [rsp+1458h+var_1430], esi; unsigned int
0x1016220f4  mov     byte ptr [rsp+1458h+var_1438], sil; bool
0x1016220f9  mov     r9b, 1; bool
0x1016220fc  xor     r8d, r8d; struct BaseXact *
0x1016220ff  mov     edx, r13d; unsigned int
0x101622102  lea     rcx, [rsp+1458h+var_140C]; this
0x101622107  call    ?FUse@CAutoDb@@QEAA_NKPEAVBaseXact@@_N1K@Z; CAutoDb::FUse(ulong,BaseXact *,bool,bool,ulong)
0x10162210c  test    al, al
0x10162210e  jnz     loc_1016221A1
0x101622114  mov     edx, r13d
0x101622117  lea     rcx, aDatabaseAuditA_8; "Database Audit: audit sessions are not "...
0x10162211e  call    ?log_unlocalized_systemmetadata@@YAXPEB_WZZ; log_unlocalized_systemmetadata(wchar_t const *,...)
0x101622123  nop
0x101622124  cmp     [rsp+1458h+var_140C], esi
0x101622128  jz      short loc_101622141
0x10162212a  mov     [rsp+1458h+var_140C], esi
0x10162212e  lea     edx, [rsi+10h]
0x101622131  mov     ecx, 0FFFFFFFFh
0x101622136  mov     rax, cs:__imp_?g_dbtableFactory@@3UDBTableFactory@@A; DBTableFactory g_dbtableFactory
0x10162213d  call    qword ptr [rax+30h]
0x101622140  nop
0x101622141  cmp     [rsp+1458h+var_1390], 0
0x101622149  jl      short loc_101622159
0x10162214b  lea     rcx, [rsp+1458h+var_1390]
0x101622153  call    cs:__imp_?Release@AutoDbLock@@QEAAXXZ; AutoDbLock::Release(void)
0x101622159  xor     eax, eax
0x10162215b  jmp     loc_101623BDF
0x101622160  cmp     cs:byte_102EDCAF5, 0
0x101622167  jz      short loc_1016221A1
0x101622169  mov     dword ptr [rsp+1458h+var_1430], 11h
0x101622171  mov     byte ptr [rsp+1458h+var_1438], 0
0x101622176  mov     r9d, 0FFFFFFFFh
0x10162217c  mov     r8b, 3
0x10162217f  mov     edx, r13d
0x101622182  lea     rcx, [rsp+1458h+var_1390]
0x10162218a  call    cs:__imp_?Acquire@AutoDbLock@@QEAA?AW4LCK_RESULT@@KW4LCK_MODE@@K_NW4EDBRefType@@@Z; AutoDbLock::Acquire(ulong,LCK_MODE,ulong,bool,EDBRefType)
0x101622190  test    eax, eax
0x101622192  jns     short loc_1016221A1
0x101622194  lfence
0x101622197  mov     dl, 28h ; '('
0x101622199  mov     ecx, eax
0x10162219b  call    cs:__imp_?lck_StandardHandler@@YAXW4LCK_RESULT@@W4ABORT_AND_LCK_EXCEPTIONS@@@Z; lck_StandardHandler(LCK_RESULT,ABORT_AND_LCK_EXCEPTIONS)
0x1016221a1  mov     ecx, r13d
0x1016221a4  mov     rax, cs:__imp_?g_dbtableFactory@@3UDBTableFactory@@A; DBTableFactory g_dbtableFactory
0x1016221ab  call    qword ptr [rax+20h]
0x1016221ae  mov     r12, rax
0x1016221b1  mov     [rsp+1458h+var_1360], rax
0x1016221b9  mov     [rsp+1458h+var_1410], esi
0x1016221bd  mov     [rsp+1458h+var_1404], esi
0x1016221c1  mov     [rsp+1458h+var_1418], 0
0x1016221c6  mov     [rsp+1458h+var_13DC], esi
0x1016221ca  mov     r15d, 1
0x1016221d0  mov     [rsp+1458h+var_13B0], r15d
0x1016221d8  mov     [rsp+1458h+var_1374], esi
0x1016221df  mov     [rsp+1458h+var_13D8], esi
0x1016221e6  mov     [rsp+1458h+var_1414], esi
0x1016221ea  mov     r14, [rax+1210h]
0x1016221f1  mov     [rsp+1458h+var_1350], r14
0x1016221f9  xor     edx, edx; unsigned __int16
0x1016221fb  mov     [rsp+1458h+var_1430], rsi; struct Worker *
0x101622200  mov     rax, cs:__imp_?hdl_prntbackout@@YAHHHHHPEAD@Z; hdl_prntbackout(int,int,int,int,char *)
0x101622207  mov     [rsp+1458h+var_1438], rax; int (*)(int, int, int, int, char *)
0x10162220c  xor     r9d, r9d; unsigned __int8
0x10162220f  xor     r8d, r8d; unsigned __int8
0x101622212  lea     rcx, [rsp+1458h+var_12A0]; this
0x10162221a  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x10162221f  nop
0x101622220  lea     rdi, [r12+328h]
0x101622228  mov     [rsp+1458h+var_13D0], rdi
0x101622230  mov     ebx, esi
0x101622232  mov     [rsp+1458h+var_13C8], ebx
0x101622239  test    r14, r14
0x10162223c  jz      short loc_10162224B
0x10162223e  mov     rcx, r14
0x101622241  call    cs:__imp_?IsVldbSharedStorageSecondary@RecoveryUnit@@QEBA_NXZ; RecoveryUnit::IsVldbSharedStorageSecondary(void)
0x101622247  mov     [rsp+1458h+var_1418], al
0x10162224b  cmp     cs:byte_102EDCAF4, 0
0x101622252  jz      loc_10162234E
0x101622258  test    r14, r14
0x10162225b  jz      short loc_1016222A4
0x10162225d  mov     rcx, [r14+6B0h]
0x101622264  test    byte ptr [rcx+3Ch], 1
0x101622268  jz      short loc_1016222A4
0x10162226a  call    cs:__imp_?IsCOWReplicaDatabase@DBTABLE@@QEBAHXZ; DBTABLE::IsCOWReplicaDatabase(void)
0x101622270  test    eax, eax
0x101622272  jnz     short loc_1016222A4
0x101622274  mov     [rsp+1458h+var_13D4], r15d
0x10162227c  cmp     [r14+2050h], al
0x101622283  jz      short loc_101622295
0x101622285  mov     rcx, r14
0x101622288  call    cs:__imp_?IsRbIoForwarderMode@RecoveryUnit@@QEBA_NXZ; RecoveryUnit::IsRbIoForwarderMode(void)
0x10162228e  test    al, al
0x101622290  mov     eax, r15d
0x101622293  jnz     short loc_101622297
0x101622295  mov     eax, esi
0x101622297  mov     [rsp+1458h+var_1410], eax
0x10162229b  mov     [rsp+1458h+var_13DC], esi
0x10162229f  jmp     loc_10162234E
0x1016222a4  lea     r8, [rsp+1458h+var_13DC]
0x1016222a9  lea     rdx, [rsp+1458h+var_1410]
0x1016222ae  mov     ecx, r13d
0x1016222b1  call    cs:__imp_?ShouldEnableAuditing@HadrRecoveryCallbacks@@SA_NKAEAH0@Z; HadrRecoveryCallbacks::ShouldEnableAuditing(ulong,int &,int &)
0x1016222b7  movzx   eax, al
0x1016222ba  mov     [rsp+1458h+var_13D4], eax
0x1016222c1  test    eax, eax
0x1016222c3  jnz     loc_10162234E
0x1016222c9  mov     r9d, [rsp+1458h+var_13DC]
0x1016222ce  mov     r8d, [rsp+1458h+var_1410]
0x1016222d3  mov     edx, r13d
0x1016222d6  lea     rcx, aDatabaseAuditA_5; "Database Audit: audit sessions are not "...
0x1016222dd  call    ?log_unlocalized_systemmetadata@@YAXPEB_WZZ; log_unlocalized_systemmetadata(wchar_t const *,...)
0x1016222e2  nop
0x1016222e3  test    ebx, ebx
0x1016222e5  jz      short loc_101622300
0x1016222e7  mov     [rdi+30h], rsi
0x1016222eb  xor     edx, edx
0x1016222ed  mov     rcx, rdi
0x1016222f0  call    ?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x1016222f5  dec     ebx
0x1016222f7  mov     [rsp+1458h+var_13C8], ebx
0x1016222fe  jmp     short loc_1016222E3
0x101622300  lea     rcx, [rsp+1458h+var_12A0]; this
0x101622308  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x10162230d  nop
0x10162230e  cmp     [rsp+1458h+var_140C], 0
0x101622313  jz      short loc_10162232E
0x101622315  mov     [rsp+1458h+var_140C], esi
0x101622319  mov     edx, 10h
0x10162231e  mov     ecx, 0FFFFFFFFh
0x101622323  mov     rax, cs:__imp_?g_dbtableFactory@@3UDBTableFactory@@A; DBTableFactory g_dbtableFactory
0x10162232a  call    qword ptr [rax+30h]
0x10162232d  nop
0x10162232e  cmp     [rsp+1458h+var_1390], 0
0x101622336  jl      short loc_101622346
0x101622338  lea     rcx, [rsp+1458h+var_1390]
0x101622340  call    cs:__imp_?Release@AutoDbLock@@QEAAXXZ; AutoDbLock::Release(void)
0x101622346  mov     eax, r15d
0x101622349  jmp     loc_101623BDF
0x10162234e  cmp     cs:byte_102EDCAF5, 0
0x101622355  jz      short loc_10162239E
0x101622357  mov     rcx, r14; this
0x10162235a  call    ?IsLocalSecondaryReplica@SecAuditPkg@@YAHPEAVRecoveryUnit@@@Z; SecAuditPkg::IsLocalSecondaryReplica(RecoveryUnit *)
0x10162235f  mov     [rsp+1458h+var_1404], eax
0x101622363  test    eax, eax
0x101622365  jz      short loc_10162239E
0x101622367  test    r14, r14
0x10162236a  jz      short loc_10162239E
0x10162236c  mov     rcx, [r14+6B0h]
0x101622373  test    byte ptr [rcx+3Ch], 1
0x101622377  jz      short loc_10162238E
0x101622379  call    cs:__imp_?IsCOWReplicaDatabase@DBTABLE@@QEBAHXZ; DBTABLE::IsCOWReplicaDatabase(void)
0x10162237f  test    eax, eax
0x101622381  jnz     short loc_10162238E
0x101622383  mov     rcx, r14
0x101622386  call    cs:__imp_?IsRbIoSecondaryRoleOnlyForGeoSecondary@RecoveryUnit@@QEBA_NXZ; RecoveryUnit::IsRbIoSecondaryRoleOnlyForGeoSecondary(void)
0x10162238c  jmp     short loc_101622397
0x10162238e  mov     rcx, r14
0x101622391  call    cs:__imp_?IsHadrSecondaryRoleOnlyForGeoSecondary@HadrRecoveryCallbacks@@SA_NPEAVRecoveryUnit@@@Z; HadrRecoveryCallbacks::IsHadrSecondaryRoleOnlyForGeoSecondary(RecoveryUnit *)
0x101622397  movzx   eax, al
0x10162239a  mov     [rsp+1458h+var_1410], eax
0x10162239e  mov     rdx, gs:58h
0x1016223a7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1016223ae  mov     ecx, [rax]
0x1016223b0  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1016223b7  mov     ebx, [rax]
0x1016223b9  add     rbx, [rdx+rcx*8]
0x1016223bd  mov     rax, [rbx+100h]
0x1016223c4  test    rax, rax
0x1016223c7  jnz     short loc_1016223D8
0x1016223c9  xor     ecx, ecx
0x1016223cb  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1016223d1  mov     rax, [rbx+100h]
0x1016223d8  mov     rbx, [rax+3E0h]
0x1016223df  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x1016223e5  mov     rcx, rax
0x1016223e8  movzx   edx, word ptr [rbx+0A0h]
0x1016223ef  call    cs:__imp_?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z; PerProcessGlobals::GetDefaultMemoryClerksForNode(ushort)
0x1016223f5  mov     rbx, rax
0x1016223f8  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x1016223fe  mov     rax, [rbx]
0x101622401  lea     r8, [rax+40h]
0x101622405  test    rax, rax
0x101622408  cmovz   r8, rsi
0x10162240c  mov     eax, 80h
0x101622411  lea     r9d, [rax-78h]
0x101622415  mov     word ptr [rsp+1458h+var_1438], ax
0x10162241a  mov     edx, r15d
0x10162241d  lea     ecx, [rax+7Eh]
0x101622420  call    cs:__imp_?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z; MemoryObjectFactory::CreateMemObject(SOSHOST_MEMOBJ_ID,ulong,PageAllocator *,short,short)
0x101622426  mov     rdi, rax
0x101622429  mov     [rsp+1458h+var_13C0], rax
0x101622431  mov     [rsp+1458h+var_1238], rax
0x101622439  test    rax, rax
0x10162243c  jnz     short loc_101622445
0x10162243e  mov     cl, 53h ; 'S'
0x101622440  call    ?ex_raise_oom@@YAXW4OOM_EXCEPTIONS@@@Z; ex_raise_oom(OOM_EXCEPTIONS)
0x101622445  cmp     cs:byte_102EDCADD, 0
0x10162244c  jz      loc_101622958
0x101622452  cmp     [rsp+1458h+var_1410], 0
0x101622457  jnz     short loc_10162246D
0x101622459  cmp     [rsp+1458h+var_1404], 0
0x10162245e  jnz     short loc_10162246D
0x101622460  movzx   ebx, [rsp+1458h+var_1418]
0x101622465  test    bl, bl
0x101622467  jz      loc_10162295D
0x10162246d  call    SecAuditPkg__GetUserDatabasesCount
0x101622472  lea     ecx, [rax+rax*4]
0x101622475  add     ecx, ecx
0x101622477  cmp     ecx, 3Ch ; '<'
0x10162247a  jnb     short loc_101622483
0x10162247c  mov     ecx, 3Ch ; '<'
0x101622481  jmp     short loc_10162248D
0x101622483  mov     eax, 258h
0x101622488  cmp     ecx, eax
0x10162248a  cmova   ecx, eax
0x10162248d  imul    eax, ecx, 3E8h
0x101622493  mov     [rsp+1458h+var_13D4], eax
0x10162249a  lea     r14, [r12+360h]
0x1016224a2  mov     [rsp+1458h+var_1310], r14
0x1016224aa  mov     ebx, esi
0x1016224ac  mov     [rsp+1458h+var_1308], ebx
0x1016224b3  xor     r9d, r9d
0x1016224b6  lea     r8, qword_102FDD108
0x1016224bd  xor     edx, edx
0x1016224bf  mov     rcx, r14
0x1016224c2  call    ?Wait@SOS_Mutex@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@@Z; SOS_Mutex::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS)
0x1016224c7  mov     [rsp+1458h+var_13AC], eax
0x1016224ce  mov     r15d, esi
0x1016224d1  mov     r12d, esi
0x1016224d4  mov     [rsp+1458h+var_13E0], esi
0x1016224d8  test    eax, eax
0x1016224da  jnz     short loc_1016224F4
0x1016224dc  mov     ecx, 1
0x1016224e1  mov     ebx, ecx
0x1016224e3  mov     [rsp+1458h+var_1308], ecx
0x1016224ea  mov     r15d, ecx
0x1016224ed  mov     r12d, ecx
0x1016224f0  mov     [rsp+1458h+var_13E0], ecx
0x1016224f4  mov     [rsp+1458h+var_12C8], eax
0x1016224fb  mov     edx, r13d
0x1016224fe  test    eax, eax
0x101622500  jz      loc_10162275A
0x101622506  cmp     eax, 102h
0x10162250b  jnz     loc_1016225CE
0x101622511  mov     r8d, eax
0x101622514  lea     rcx, aDatabaseAuditA_1; "Database Audit: auditSessionsWaitToRefr"...
0x10162251b  call    ?log_unlocalized_systemmetadata@@YAXPEB_WZZ; log_unlocalized_systemmetadata(wchar_t const *,...)
0x101622520  nop
0x101622521  test    r15d, r15d
0x101622524  jz      short loc_101622542
0x101622526  mov     [r14+30h], rsi
0x10162252a  xor     edx, edx
0x10162252c  mov     rcx, r14
0x10162252f  call    ?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x101622534  dec     ebx
0x101622536  mov     r15d, ebx
0x101622539  mov     [rsp+1458h+var_1308], ebx
0x101622540  jmp     short loc_101622521
0x101622542  test    rdi, rdi
0x101622545  jz      short loc_101622551
0x101622547  mov     rax, [rdi]
0x10162254a  mov     rcx, rdi
0x10162254d  call    qword ptr [rax+10h]
0x101622550  nop
0x101622551  mov     ebx, [rsp+1458h+var_13C8]
0x101622558  mov     rdi, [rsp+1458h+var_13D0]
0x101622560  test    ebx, ebx
0x101622562  jz      short loc_10162257D
0x101622564  mov     [rdi+30h], rsi
0x101622568  xor     edx, edx
0x10162256a  mov     rcx, rdi
0x10162256d  call    ?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x101622572  dec     ebx
0x101622574  mov     [rsp+1458h+var_13C8], ebx
0x10162257b  jmp     short loc_101622560
  ... truncated ...
```
