# RecoveryMgr::MoveUpRedo(LogBlockId)

- ea: `0x101cd0460`
- end: `0x101cd30d3`
- name: `?MoveUpRedo@RecoveryMgr@@QEAAXVLogBlockId@@@Z`
- size: `11379`
- prototype: ``
- caller_count: `2`
- callee_count: `58`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x101cede10`
- `0x101cf8cc0`

## callees

- `0x100401380`
- `0x1004013f0`
- `0x100401490`
- `0x100402920`
- `0x10040bd60`
- `0x10040da40`
- `0x10040da80`
- `0x10040fc00`
- `0x100415470`
- `0x10041b5d0`
- `0x1004384c0`
- `0x10043e000`
- `0x1004c4220`
- `0x10056afe0`
- `0x10056b1c0`
- `0x10056b280`
- `0x10056b530`
- `0x1005c6740`
- `0x100aa4250`
- `0x100abe7d0`
- `0x1011ff520`
- `0x1016c6d00`
- `0x1017a48b0`
- `0x10180de20`
- `0x10180dec0`
- `0x101916090`
- `0x1019177f0`
- `0x101afcb10`
- `0x101bd3f70`
- `0x101be6c40`
- `0x101c837a0`
- `0x101cae2c0`
- `0x101cb2900`
- `0x101cb2a60`
- `0x101cb3280`
- `0x101cc0b80`
- `0x101cc5140`
- `0x101cc99c0`
- `0x101cd0000`
- `0x101cd0070`
- `0x101cd0460`
- `0x101cd3ae0`
- `0x101cda780`
- `0x101cde7c0`
- `0x101cdeb90`
- `0x101ce1c20`
- `0x101ce20f0`
- `0x101ce3fa0`
- `0x101ced290`
- `0x101ceef60`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x101cd086b`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd0ac9`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd0ce5`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1016`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1062`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd10b4`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd111c`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd158d`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1652`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd16f9`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd182d`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd18fd`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1ac1`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1bce`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1d41`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1db1`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1e3f`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1ebf`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1f27`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd24d9`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd2534`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd25e1`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd262a`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd28eb`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd2a9b`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd2b9d`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd2c83`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd2df4`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd2f6c`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd086b`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd0ac9`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd0ce5`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1016`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1062`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd10b4`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd111c`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd158d`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1652`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd16f9`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd182d`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd18fd`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1ac1`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1bce`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1d41`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1db1`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1e3f`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1ebf`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd1f27`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd24d9`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd2534`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd25e1`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd262a`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd28eb`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd2a9b`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd2b9d`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd2c83`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd2df4`
- `KERNEL32!QueryPerformanceCounter` at `0x101cd2f6c`
- `sqlTsEs!?DateAdd@SQLDATE@@QEAAJJJ@Z` at `0x101cd125e`
- `sqlTsEs!?DateAdd@SQLDATE@@QEAAJJJ@Z` at `0x101cd125e`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101cd0d1e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd0857`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd0ab5`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd0cd1`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd1002`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd104e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd10a0`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd1108`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd1176`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd1579`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd15f4`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd163d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd16e5`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd1819`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd1884`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd18e9`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd1aad`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd1b18`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd1bba`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd1d2d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd1d9c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd1e2b`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd1eab`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd1f13`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd1f7c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd24c5`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd2520`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd258b`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd25cc`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd2616`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd2681`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd28d7`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd2a87`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd2af9`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd2b89`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd2c6f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd2de0`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101cd2f58`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101cd1182`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101cd1600`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101cd1890`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101cd1b24`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101cd1f88`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101cd2597`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101cd268d`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101cd2b05`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101cd2dd9`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101cd2dd9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd081c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd08e9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd0945`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd11e2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd1284`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd12c2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd1533`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd1555`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd1a8b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd2066`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd2093`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd2997`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd081c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd08e9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd0945`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd11e2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd1284`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd12c2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd1533`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd1555`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd1a8b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd2066`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd2093`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101cd2997`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101cd09e2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101cd2a67`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101cd09e2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101cd2a67`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cd0c65`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cd2148`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cd233f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cd239d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cd2826`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cd0c65`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cd2148`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cd233f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cd239d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cd2826`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101cd1a2b`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101cd1a40`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101cd1a2b`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101cd1a40`
- `sqldk!SystemThread_TlsIndex` at `0x101cd06ff`
- `sqldk!SystemThread_TlsIndex` at `0x101cd0733`
- `sqldk!SystemThread_TlsIndex` at `0x101cd0789`
- `sqldk!SystemThread_TlsIndex` at `0x101cd0a09`
- `sqldk!SystemThread_TlsIndex` at `0x101cd0b33`
- `sqldk!SystemThread_TlsIndex` at `0x101cd0c36`
- `sqldk!SystemThread_TlsIndex` at `0x101cd0c78`
- `sqldk!SystemThread_TlsIndex` at `0x101cd2110`
- `sqldk!SystemThread_TlsIndex` at `0x101cd2310`
- `sqldk!SystemThread_TlsIndex` at `0x101cd236e`
- `sqldk!SystemThread_TlsIndex` at `0x101cd27ef`
- `sqldk!SystemThread_TlsIndex` at `0x101cd2cfa`
- `sqldk!SystemThread_TlsIndex` at `0x101cd2da1`
- `sqldk!SystemThread_TlsIndex` at `0x101cd2e61`
- `sqldk!SystemThread_TlsIndex` at `0x101cd2fd6`
- `sqldk!SystemThread_TlsOffset` at `0x101cd0708`
- `sqldk!SystemThread_TlsOffset` at `0x101cd073c`
- `sqldk!SystemThread_TlsOffset` at `0x101cd0792`
- `sqldk!SystemThread_TlsOffset` at `0x101cd0a12`
- `sqldk!SystemThread_TlsOffset` at `0x101cd0b3c`
- `sqldk!SystemThread_TlsOffset` at `0x101cd0c3f`
- `sqldk!SystemThread_TlsOffset` at `0x101cd0c81`
- `sqldk!SystemThread_TlsOffset` at `0x101cd2119`
- `sqldk!SystemThread_TlsOffset` at `0x101cd2319`
- `sqldk!SystemThread_TlsOffset` at `0x101cd2377`
- `sqldk!SystemThread_TlsOffset` at `0x101cd27f8`
- `sqldk!SystemThread_TlsOffset` at `0x101cd2d03`
- `sqldk!SystemThread_TlsOffset` at `0x101cd2daa`
- `sqldk!SystemThread_TlsOffset` at `0x101cd2e6a`
- `sqldk!SystemThread_TlsOffset` at `0x101cd2fdf`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cd0634`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cd0663`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cd0ba9`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cd0bd8`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cd2edf`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cd2f0e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cd304c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cd307b`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cd0634`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cd0663`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cd0ba9`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cd0bd8`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cd2edf`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cd2f0e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cd304c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cd307b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101cd0c9a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101cd2dc3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101cd0c9a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101cd2dc3`

## string_xrefs

- `0x101cd21d4`: `REDO LSN %.*ls (0x%ls), XdesId 0x%04lx:%08lx Before termination LSN reached.\n`
- `0x101cd0cc2`: `MoveUpRedo through log block 0x%016I64x. scheduler id %d`
- `0x101cd28a9`: `REDO LSN %.*ls (0x%ls), XdesId 0x%04lx:%08lx Stop after termination LSN reached.\n`
- `0x101cd293d`: `MoveUpRedo End`
- `0x101cd154b`: `!(isSocratesPageServer) || (!isSocratesCompute)`
- `0x101cd1529`: `!(isSocratesCompute) || (!isSocratesPageServer)`

## pseudocode

```c
// Hidden C++ exception states: #wind=33 #try_helpers=1
void __fastcall RecoveryMgr::MoveUpRedo(_QWORD *a1, __int64 a2)
{
  DWORD v2; // edi
  __int64 v4; // r14
  __int64 v5; // rax
  __int64 v6; // rax
  LARGE_INTEGER v7; // rcx
  _BYTE *v8; // rsi
  __int64 v9; // rax
  _BYTE *v10; // r12
  __int64 v11; // rcx
  __int64 v12; // r13
  DirtyPageMgr *QuadPart; // rax
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rcx
  DWORD LowPart; // r8d
  unsigned int v20; // r9d
  __int64 v21; // r8
  __int64 RedoneLSN; // rax
  unsigned int v23; // ecx
  DirtyPageMgr *v24; // rax
  signed __int64 v25; // rax
  __int64 v26; // rdx
  struct CSessionTraceFlags *v27; // rcx
  __int64 v28; // rsi
  __int64 v29; // rcx
  DirtyPageMgr *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rsi
  struct IServerConfiguration *v33; // rcx
  unsigned int v34; // r12d
  unsigned int LWSpeed; // eax
  int v36; // ecx
  int v37; // esi
  __int64 v38; // rax
  __int64 v39; // r14
  __int64 v40; // rcx
  DirtyPageMgr *v41; // rax
  DirtyPageMgr *v42; // rcx
  DirtyPageMgr *v43; // rcx
  unsigned __int64 v44; // rdx
  __int64 NextLSN; // rax
  __int64 v46; // rsi
  __int64 v47; // rsi
  struct PageServerStats *PageServerStats; // rax
  __int64 v49; // rdx
  struct PageServerStats **v50; // rdx
  __int64 ForeignRedoLsn; // rax
  __int64 LastRedoneLSN; // rcx
  __int64 v53; // r14
  __int64 v54; // rdx
  unsigned __int16 v55; // cx
  bool v56; // si
  DirtyPageMgr *v57; // rcx
  DirtyPageMgr *v58; // rcx
  unsigned __int64 v59; // rdx
  __int64 v60; // rdx
  struct PageServerStats **v61; // rdx
  DirtyPageMgr *v62; // rax
  unsigned __int16 v63; // dx
  __int64 v64; // rsi
  struct PageServerStats *v65; // rax
  DirtyPageMgr *v66; // rcx
  DirtyPageMgr *v67; // rcx
  unsigned __int64 v68; // rdx
  DirtyPageMgr *v69; // rax
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // r8
  const struct DBTABLE *v73; // rsi
  struct PageServerStats *v74; // r14
  LSN *v75; // r9
  int v76; // ecx
  struct LogRec *v77; // rsi
  PerProcessGlobals *ClientProcessGlobals; // rax
  struct MemoryClerk **DefaultMemoryClerksForNode; // rsi
  __int64 v80; // rdx
  __int64 v81; // rcx
  __int64 v82; // r8
  __int64 v83; // rax
  DirtyPageMgr *v84; // rcx
  DirtyPageMgr *v85; // rcx
  unsigned __int64 v86; // rdx
  __int64 v87; // rax
  unsigned int v88; // ecx
  DirtyPageMgr *v89; // rax
  ParallelRedoManager *v90; // rcx
  unsigned int (__fastcall ***v91)(_QWORD, struct LogRec *, LSN *, _QWORD); // rcx
  int v92; // edi
  __int64 v93; // rsi
  int v94; // esi
  __int64 v95; // r14
  DirtyPageMgr *v96; // r8
  DirtyPageMgr *v97; // r8
  LSN v98; // rsi
  DirtyPageMgr *v99; // r8
  DirtyPageMgr *v100; // r8
  DirtyPageMgr *v101; // rcx
  DirtyPageMgr *v102; // rcx
  unsigned __int64 v103; // rdx
  const struct LogScanStats *v104; // rax
  __int64 v105; // rax
  __int64 v106; // r11
  unsigned int (__fastcall ***v107)(_QWORD, struct LogRec *, LSN *, _QWORD); // rcx
  __int64 v108; // rax
  struct CSessionTraceFlags *v109; // rcx
  int v110; // edi
  __int64 v111; // rsi
  int v112; // eax
  char v113; // cl
  int v114; // esi
  __int64 v115; // r14
  unsigned __int16 v116; // dx
  LONG HighPart; // ecx
  __int64 v118; // rax
  struct CSessionTraceFlags *v119; // rcx
  char v120; // al
  RecoveryUnit *v121; // r9
  __int64 v122; // rdx
  struct CSessionTraceFlags *v123; // rcx
  int v124; // eax
  bool v125; // al
  __int64 v126; // rax
  __int64 LogOpString; // rax
  DirtyPageMgr *v128; // rax
  DirtyPageMgr *v129; // rcx
  unsigned __int64 v130; // rcx
  unsigned __int64 v131; // rdx
  DirtyPageMgr *v132; // rax
  DirtyPageMgr *v133; // rcx
  DirtyPageMgr *v134; // rcx
  unsigned __int64 v135; // rdx
  unsigned int v136; // eax
  const struct LSN *v137; // rax
  __int64 v138; // rax
  struct CSessionTraceFlags *v139; // rcx
  ParallelRedoManager *v140; // rcx
  __int64 v141; // rax
  __int64 v142; // r9
  DirtyPageMgr *v143; // rcx
  LARGE_INTEGER v144; // rcx
  unsigned __int64 v145; // rdx
  const struct LogScanStats *v146; // rax
  DirtyPageMgr *v147; // rdi
  DirtyPageMgr *v148; // r8
  DirtyPageMgr *v149; // r8
  __int64 v150; // rax
  __int64 v151; // r11
  DirtyPageMgr *v152; // rax
  signed __int64 v153; // rax
  __int64 v154; // rcx
  __int64 v155; // rdi
  struct Worker *v156; // rcx
  DirtyPageMgr *v157; // rax
  signed __int64 v158; // rax
  DirtyPageMgr *v159; // rax
  signed __int64 v160; // rax
  int v161; // esi
  _QWORD *v162; // rbx
  __int64 v163; // rdi
  _QWORD *v164; // r14
  int v165; // eax
  int v166; // edx
  __int64 v167; // rcx
  __int64 v169; // rax
  struct CSessionTraceFlags *v170; // rcx
  int v171; // eax
  struct LogRec *v172; // rdi
  BOOL v175; // ecx
  __int64 *v176; // rax
  unsigned __int16 v177; // ax
  __int64 v178; // r8
  __int64 v179; // rax
  int *v181; // rcx
  __int64 v182; // rcx
  struct LBH *v183; // [rsp+20h] [rbp-7C8h]
  struct LBH *v184; // [rsp+20h] [rbp-7C8h]
  struct LBH *v185; // [rsp+20h] [rbp-7C8h]
  struct Worker *v186; // [rsp+28h] [rbp-7C0h]
  DirtyPageMgr *v187; // [rsp+40h] [rbp-7A8h]
  char v188; // [rsp+48h] [rbp-7A0h]
  char v189; // [rsp+49h] [rbp-79Fh]
  char v190; // [rsp+4Bh] [rbp-79Dh]
  struct LogRec *v191; // [rsp+50h] [rbp-798h]
  DirtyPageMgr *v192; // [rsp+60h] [rbp-788h]
  DirtyPageMgr *v193; // [rsp+60h] [rbp-788h]
  DirtyPageMgr *v194; // [rsp+60h] [rbp-788h]
  DirtyPageMgr *v195; // [rsp+60h] [rbp-788h]
  unsigned int v196; // [rsp+68h] [rbp-780h] BYREF
  LSN v197; // [rsp+70h] [rbp-778h]
  __int64 v198; // [rsp+80h] [rbp-768h]
  unsigned __int16 v199; // [rsp+88h] [rbp-760h]
  int v200; // [rsp+90h] [rbp-758h]
  struct LBH *v201[2]; // [rsp+A0h] [rbp-748h] BYREF
  DirtyPageMgr *v202; // [rsp+B0h] [rbp-738h]
  LARGE_INTEGER v203; // [rsp+C0h] [rbp-728h] BYREF
  LARGE_INTEGER v204; // [rsp+D0h] [rbp-718h] BYREF
  void **v205; // [rsp+D8h] [rbp-710h] BYREF
  __int64 v206; // [rsp+E0h] [rbp-708h]
  int v207; // [rsp+E8h] [rbp-700h]
  __int64 v208; // [rsp+F0h] [rbp-6F8h]
  char v209; // [rsp+F8h] [rbp-6F0h]
  unsigned int v210; // [rsp+100h] [rbp-6E8h] BYREF
  LARGE_INTEGER v211; // [rsp+108h] [rbp-6E0h] BYREF
  __int64 v212; // [rsp+110h] [rbp-6D8h]
  DirtyPageMgr *v213; // [rsp+118h] [rbp-6D0h]
  LSN v214; // [rsp+120h] [rbp-6C8h]
  _QWORD *v215; // [rsp+128h] [rbp-6C0h] BYREF
  unsigned __int64 v216; // [rsp+130h] [rbp-6B8h] BYREF
  DirtyPageMgr *v217; // [rsp+138h] [rbp-6B0h]
  __int64 v218; // [rsp+140h] [rbp-6A8h] BYREF
  __int16 v219; // [rsp+148h] [rbp-6A0h]
  __int64 v220; // [rsp+150h] [rbp-698h] BYREF
  __int16 v221; // [rsp+158h] [rbp-690h]
  __int64 v222; // [rsp+160h] [rbp-688h] BYREF
  __int16 v223; // [rsp+168h] [rbp-680h]
  DirtyPageMgr *v224; // [rsp+170h] [rbp-678h]
  int v225; // [rsp+178h] [rbp-670h]
  __int64 v226; // [rsp+180h] [rbp-668h]
  __int64 v227; // [rsp+188h] [rbp-660h] BYREF
  int v228; // [rsp+190h] [rbp-658h]
  __int64 v229; // [rsp+198h] [rbp-650h] BYREF
  int v230; // [rsp+1A0h] [rbp-648h]
  int v231; // [rsp+1B0h] [rbp-638h] BYREF
  __int16 v232; // [rsp+1B4h] [rbp-634h]
  int v233; // [rsp+1C0h] [rbp-628h] BYREF
  __int16 v234; // [rsp+1C4h] [rbp-624h]
  int v235; // [rsp+1C8h] [rbp-620h] BYREF
  __int16 v236; // [rsp+1CCh] [rbp-61Ch]
  __int64 v237; // [rsp+1D0h] [rbp-618h] BYREF
  DirtyPageMgr *v238; // [rsp+1D8h] [rbp-610h]
  LARGE_INTEGER v239; // [rsp+1E0h] [rbp-608h] BYREF
  LARGE_INTEGER v240; // [rsp+1E8h] [rbp-600h] BYREF
  int v241; // [rsp+1F0h] [rbp-5F8h]
  unsigned int v242; // [rsp+1F4h] [rbp-5F4h] BYREF
  LARGE_INTEGER v243; // [rsp+1F8h] [rbp-5F0h] BYREF
  unsigned int v244; // [rsp+200h] [rbp-5E8h] BYREF
  int v245; // [rsp+208h] [rbp-5E0h]
  DirtyPageMgr *v246; // [rsp+210h] [rbp-5D8h]
  int v247; // [rsp+218h] [rbp-5D0h]
  LARGE_INTEGER PerformanceCount; // [rsp+220h] [rbp-5C8h] BYREF
  LARGE_INTEGER v249; // [rsp+228h] [rbp-5C0h] BYREF
  int v250; // [rsp+230h] [rbp-5B8h] BYREF
  __int16 v251; // [rsp+234h] [rbp-5B4h]
  _BYTE *v252; // [rsp+240h] [rbp-5A8h]
  char v253; // [rsp+248h] [rbp-5A0h]
  _BYTE *v254; // [rsp+250h] [rbp-598h]
  char v255; // [rsp+258h] [rbp-590h]
  int v256; // [rsp+260h] [rbp-588h] BYREF
  __int16 v257; // [rsp+264h] [rbp-584h]
  LSN v258; // [rsp+268h] [rbp-580h] BYREF
  unsigned __int16 v259; // [rsp+270h] [rbp-578h]
  __int16 v260; // [rsp+272h] [rbp-576h]
  __int64 v261; // [rsp+274h] [rbp-574h] BYREF
  __int16 v262; // [rsp+27Ch] [rbp-56Ch]
  __int16 v263; // [rsp+27Eh] [rbp-56Ah]
  _DWORD v264[2]; // [rsp+280h] [rbp-568h] BYREF
  __int16 v265; // [rsp+288h] [rbp-560h]
  __int64 v266; // [rsp+290h] [rbp-558h] BYREF
  __int16 v267; // [rsp+298h] [rbp-550h]
  __int16 v268; // [rsp+29Ah] [rbp-54Eh]
  __int64 v269; // [rsp+2A0h] [rbp-548h] BYREF
  __int16 v270; // [rsp+2A8h] [rbp-540h]
  __int64 v271; // [rsp+2B0h] [rbp-538h] BYREF
  __int16 v272; // [rsp+2B8h] [rbp-530h]
  __int64 v273; // [rsp+2C0h] [rbp-528h] BYREF
  __int16 v274; // [rsp+2C8h] [rbp-520h]
  __int128 v275; // [rsp+2D0h] [rbp-518h] BYREF
  int v276; // [rsp+2E0h] [rbp-508h]
  __int64 v277; // [rsp+2E8h] [rbp-500h] BYREF
  __int16 v278; // [rsp+2F0h] [rbp-4F8h]
  LARGE_INTEGER v279; // [rsp+2F8h] [rbp-4F0h] BYREF
  LARGE_INTEGER v280; // [rsp+300h] [rbp-4E8h] BYREF
  DirtyPageMgr *v281; // [rsp+308h] [rbp-4E0h]
  unsigned __int64 v282; // [rsp+310h] [rbp-4D8h]
  LARGE_INTEGER v283; // [rsp+318h] [rbp-4D0h] BYREF
  LARGE_INTEGER v284; // [rsp+320h] [rbp-4C8h] BYREF
  DirtyPageMgr *v285; // [rsp+328h] [rbp-4C0h]
  LARGE_INTEGER v286; // [rsp+330h] [rbp-4B8h] BYREF
  LARGE_INTEGER v287; // [rsp+338h] [rbp-4B0h] BYREF
  DirtyPageMgr *v288; // [rsp+340h] [rbp-4A8h]
  int v289; // [rsp+348h] [rbp-4A0h]
  LARGE_INTEGER v290; // [rsp+350h] [rbp-498h] BYREF
  LARGE_INTEGER v291; // [rsp+358h] [rbp-490h]
  LARGE_INTEGER v292; // [rsp+360h] [rbp-488h] BYREF
  LARGE_INTEGER v293; // [rsp+368h] [rbp-480h] BYREF
  DirtyPageMgr *v294; // [rsp+370h] [rbp-478h]
  LARGE_INTEGER v295; // [rsp+378h] [rbp-470h] BYREF
  LARGE_INTEGER v296; // [rsp+380h] [rbp-468h]
  DirtyPageMgr *v297; // [rsp+388h] [rbp-460h]
  unsigned __int64 v298; // [rsp+390h] [rbp-458h] BYREF
  LARGE_INTEGER v299; // [rsp+398h] [rbp-450h] BYREF
  DirtyPageMgr *v300; // [rsp+3A0h] [rbp-448h]
  LARGE_INTEGER v301; // [rsp+3A8h] [rbp-440h] BYREF
  LARGE_INTEGER v302; // [rsp+3B0h] [rbp-438h] BYREF
  LARGE_INTEGER v303; // [rsp+3B8h] [rbp-430h] BYREF
  DirtyPageMgr *v304; // [rsp+3C0h] [rbp-428h]
  LARGE_INTEGER v305; // [rsp+3C8h] [rbp-420h] BYREF
  LSN *v306; // [rsp+3D0h] [rbp-418h]
  LARGE_INTEGER v307; // [rsp+3D8h] [rbp-410h] BYREF
  DirtyPageMgr *v308; // [rsp+3E0h] [rbp-408h]
  LARGE_INTEGER v309; // [rsp+3E8h] [rbp-400h] BYREF
  LARGE_INTEGER v310; // [rsp+3F0h] [rbp-3F8h] BYREF
  DirtyPageMgr *v311; // [rsp+3F8h] [rbp-3F0h]
  LARGE_INTEGER v312; // [rsp+400h] [rbp-3E8h] BYREF
  DirtyPageMgr *v313; // [rsp+408h] [rbp-3E0h]
  LARGE_INTEGER v314; // [rsp+410h] [rbp-3D8h] BYREF
  DirtyPageMgr *v315; // [rsp+418h] [rbp-3D0h]
  LSN v316; // [rsp+420h] [rbp-3C8h]
  unsigned __int16 v317; // [rsp+428h] [rbp-3C0h]
  _BYTE v318[16]; // [rsp+430h] [rbp-3B8h] BYREF
  __int128 v319; // [rsp+440h] [rbp-3A8h] BYREF
  int v320; // [rsp+450h] [rbp-398h]
  __int64 v321; // [rsp+460h] [rbp-388h]
  DirtyPageMgr *v322; // [rsp+468h] [rbp-380h]
  DirtyPageMgr *v323; // [rsp+470h] [rbp-378h]
  unsigned __int64 v324; // [rsp+478h] [rbp-370h]
  DirtyPageMgr *v325; // [rsp+480h] [rbp-368h]
  DirtyPageMgr *v326; // [rsp+488h] [rbp-360h]
  DirtyPageMgr *v327; // [rsp+490h] [rbp-358h]
  DirtyPageMgr *v328; // [rsp+498h] [rbp-350h]
  char v329[16]; // [rsp+4A0h] [rbp-348h] BYREF
  __int64 v330; // [rsp+4B0h] [rbp-338h] BYREF
  char v331[12]; // [rsp+4BCh] [rbp-32Ch] BYREF
  char v332[12]; // [rsp+4C8h] [rbp-320h] BYREF
  char v333[12]; // [rsp+4D4h] [rbp-314h] BYREF
  _BYTE v334[40]; // [rsp+4E0h] [rbp-308h] BYREF
  LSN v335; // [rsp+508h] [rbp-2E0h] BYREF
  unsigned __int16 v336; // [rsp+510h] [rbp-2D8h]
  __int64 v337; // [rsp+518h] [rbp-2D0h] BYREF
  unsigned __int16 v338; // [rsp+520h] [rbp-2C8h]
  LSN v339; // [rsp+528h] [rbp-2C0h] BYREF
  __int16 v340; // [rsp+530h] [rbp-2B8h]
  int v341; // [rsp+540h] [rbp-2A8h] BYREF
  __int64 v342; // [rsp+548h] [rbp-2A0h] BYREF
  char v343; // [rsp+550h] [rbp-298h]
  int v344; // [rsp+554h] [rbp-294h]
  __int128 v345; // [rsp+560h] [rbp-288h]
  __int64 v346; // [rsp+570h] [rbp-278h]
  int v347; // [rsp+578h] [rbp-270h]
  __int64 v348; // [rsp+580h] [rbp-268h] BYREF
  int v349; // [rsp+588h] [rbp-260h]
  _DWORD v350[4]; // [rsp+590h] [rbp-258h] BYREF
  _DWORD v351[2]; // [rsp+5A0h] [rbp-248h] BYREF
  __int16 v352; // [rsp+5A8h] [rbp-240h]
  void **v353; // [rsp+5B0h] [rbp-238h]
  __int64 v354; // [rsp+5B8h] [rbp-230h]
  int v355; // [rsp+5C0h] [rbp-228h]
  __int16 v356; // [rsp+5C4h] [rbp-224h]
  __int16 v357; // [rsp+5C6h] [rbp-222h]
  __int64 v358; // [rsp+5C8h] [rbp-220h]
  int v359; // [rsp+5D0h] [rbp-218h]
  _BYTE v360[12]; // [rsp+5D8h] [rbp-210h] BYREF
  char v361[12]; // [rsp+5E4h] [rbp-204h] BYREF
  char v362[12]; // [rsp+5F0h] [rbp-1F8h] BYREF
  char v363[20]; // [rsp+5FCh] [rbp-1ECh] BYREF
  wchar_t v364[48]; // [rsp+610h] [rbp-1D8h] BYREF
  wchar_t v365[48]; // [rsp+670h] [rbp-178h] BYREF
  wchar_t v366[56]; // [rsp+6D0h] [rbp-118h] BYREF
  wchar_t v367[56]; // [rsp+740h] [rbp-A8h] BYREF
  unsigned int v368; // [rsp+7FCh] [rbp+14h]

  v368 = HIDWORD(a2);
  v321 = -2;
  v2 = a2;
  v215 = a1;
  v206 = 0;
  v207 = 1;
  v208 = 0;
  v209 = 0;
  v205 = &SLogIterForward::`vftable';
  v189 = 0;
  v188 = 0;
  v341 = 0;
  v342 = 0;
  v343 = 0;
  v344 = 0;
  v346 = 0;
  v347 = 0;
  v345 = 0;
  v348 = 0;
  v349 = 0;
  v4 = *a1;
  if ( (*(_BYTE *)(*a1 + 7376LL) & 0x20) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, LSN *))(**(_QWORD **)(v4 + 1736) + 368LL))(*(_QWORD *)(v4 + 1736), &v339);
    *(_QWORD *)((char *)a1 + 22132) = v339.QuadPart;
    *((_WORD *)a1 + 11070) = v340;
    RecoveryMgr::SetLastRedoneLSN((RecoveryMgr *)a1, (const struct LSN *)((char *)a1 + 22132));
    if ( (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*a1 + 1736LL) + 656LL))(*(_QWORD *)(*a1 + 1736LL)) )
    {
      v350[2] = 0;
      v350[0] = v2;
      v350[1] = v368;
      v5 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*a1 + 1736LL) + 656LL))(*(_QWORD *)(*a1 + 1736LL));
      LogPoolMgr::OverrideCacheHoldup(v5, 9, v350);
    }
    if ( v342 || (v341 & 1) != 0 )
    {
      if ( (v341 & 1) == 0 )
      {
        PageRef::Unlatch((PageRef *)&v342);
        if ( (_QWORD)v345 )
        {
          operator delete((void *)v345, 0x6FAu);
          *(_QWORD *)&v345 = 0;
        }
      }
      BootPagePtr::Release((BootPagePtr *)&v341, 0);
    }
    if ( (_QWORD)v345 )
    {
      operator delete((void *)v345, 0x6FAu);
      *(_QWORD *)&v345 = 0;
    }
    PageRef::~PageRef((PageRef *)&v342);
    goto LABEL_487;
  }
  v6 = *(_QWORD *)(v4 + 1696);
  if ( *(_WORD *)(v6 + 116) < 2u
    || (v7 = *(LARGE_INTEGER *)(*(_QWORD *)(v6 + 80) + 8LL), v203 = v7, !v7.QuadPart)
    || (*(_BYTE *)(v7.QuadPart + 100) & 4) != 0 )
  {
    v203.QuadPart = 0;
  }
  v8 = (_BYTE *)(v4 + 8307);
  v254 = (_BYTE *)(v4 + 8307);
  v255 = *(_BYTE *)(v4 + 8307);
  *(_BYTE *)(v4 + 8307) = 1;
  v9 = a1[4234];
  if ( v9 )
  {
    *(_DWORD *)(v9 + 368) = 6;
    *(_BYTE *)(a1[3056] + 28LL) = 1;
  }
  v200 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + SystemThread_TlsIndex)
                                           + SystemThread_TlsOffset
                                           + 8LL)
                               + 96LL)
                   + 1452LL);
  v10 = (_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                        + SystemThread_TlsOffset
                                        + 8LL)
                            + 96LL)
                + 1177LL);
  v252 = v10;
  v253 = *v10;
  *v10 = 1;
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                    + SystemThread_TlsOffset
                                    + 8LL)
                        + 96LL)
            + 1452LL) = *(unsigned __int16 *)(*(_QWORD *)(*a1 + 1712LL) + 40LL);
  v11 = *a1;
  v353 = &TxLogDataReadAhead::`vftable';
  v354 = v11;
  v355 = NullPageId;
  v356 = word_1031997E8;
  v357 = 0;
  if ( !v11 )
    utassert_fail(1u, "recoveryUnit != NULL", "recovery.cpp", 24838, 0);
  v353 = &ForwardLogDataReadAhead::`vftable';
  v197.QuadPart = 0;
  v358 = 0;
  v359 = 0;
  v12 = *(_QWORD *)(*a1 + 1712LL);
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&PerformanceCount);
    QuadPart = (DirtyPageMgr *)PerformanceCount.QuadPart;
  }
  else
  {
    QuadPart = MEMORY[0x7FFE0008];
  }
  v224 = QuadPart;
  v225 = 26;
  v226 = v12 + 56;
  v197.QuadPart = 0;
  v14 = *a1;
  v15 = *a1;
  if ( *(_QWORD *)(*(_QWORD *)(*a1 + 26096LL) + 64LL) && !RecoveryUnit::IsRbIoDb((RecoveryUnit *)v4) )
  {
    utassert_fail(
      1u,
      "nullptr == GetPru ()->GetHkDbCtxt ()->RestoreParameters || ru->IsRbIoDb()",
      "recovery.cpp",
      15347,
      0);
    v15 = *a1;
    v14 = *a1;
  }
  if ( a1[3079] )
  {
    if ( (*((_DWORD *)a1 + 9) & 0x80) != 0
      || (v16 = *(_QWORD *)(v15 + 1712), (*(_BYTE *)(v16 + 60) & 1) != 0) && !*(_QWORD *)(v16 + 640) )
    {
      utassert_fail(
        1u,
        "(0 == m_ExceptionCount) || (!IsForeignLogApply () && !GetPru ()->IsRbIoDb ())",
        "recovery.cpp",
        15353,
        0);
      v15 = *a1;
      v14 = *a1;
    }
  }
  v17 = *(_DWORD *)(v15 + 1656);
  if ( v17 == 4 || *(_DWORD *)(v15 + 1652) == 4 || v17 == 3 )
  {
    v218 = *(_QWORD *)((char *)a1 + 22132);
    v219 = *((_WORD *)a1 + 11070);
    LODWORD(v201[0]) = 0;
    WORD2(v201[0]) = 0;
    v18 = *(_QWORD *)(v14 + 1712);
    LODWORD(v184) = *(_DWORD *)(v18 + 928);
    ex_raise(33, 13, 21, 3, v184, v18 + 936, v201, &v218);
  }
  v197.LowPart = *((_DWORD *)a1 + 5533);
  LowPart = v197.LowPart;
  v20 = *((_DWORD *)a1 + 5534);
  v197.HighPart = v20;
  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset
                        + 8LL)
            + 40LL) = -1;
  if ( v2 < LowPart || v2 <= LowPart && v368 < v20 )
  {
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v243);
      v159 = (DirtyPageMgr *)v243.QuadPart;
    }
    else
    {
      v159 = MEMORY[0x7FFE0008];
    }
    if ( v159 < v224 )
      v160 = 0;
    else
      v160 = v159 - v224;
    *(_QWORD *)(v226 + 312) += v160;
    v353 = &IDbCopyRestoreCallback::`vftable';
    if ( !v253 && *v10 )
      *v10 = 0;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1452LL) = v200;
    if ( !v255 && *v8 )
      *v8 = 0;
    if ( v342 || (v341 & 1) != 0 )
    {
      if ( (v341 & 1) == 0 )
      {
        PageRef::Unlatch((PageRef *)&v342);
        if ( (_QWORD)v345 )
        {
          operator delete((void *)v345, 0x6FAu);
          *(_QWORD *)&v345 = 0;
        }
      }
      BootPagePtr::Release((BootPagePtr *)&v341, 0);
    }
    if ( !(_QWORD)v345 )
      goto LABEL_486;
LABEL_485:
    operator delete((void *)v345, 0x6FAu);
    *(_QWORD *)&v345 = 0;
LABEL_486:
    PageRef::~PageRef((PageRef *)&v342);
LABEL_487:
    v205 = &SLogIterForward::`vftable';
    return;
  }
  if ( (*((_DWORD *)a1 + 9) & 0x80) == 0 )
  {
    (*(void (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(*a1 + 1736LL) + 40LL))(*(_QWORD *)(*a1 + 1736LL), &v348);
    LOBYTE(v21) = 1;
    RedoneLSN = RecoveryMgr::GetRedoneLSN(a1, &v261, v21);
    if ( (unsigned int)v348 <= *(_DWORD *)RedoneLSN )
    {
      if ( (_DWORD)v348 != *(_DWORD *)RedoneLSN
        || (v23 = *(_DWORD *)(RedoneLSN + 4), HIDWORD(v348) <= v23)
        && (HIDWORD(v348) != v23 || (unsigned __int16)v349 <= *(_WORD *)(RedoneLSN + 8)) )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v211);
          v24 = (DirtyPageMgr *)v211.QuadPart;
        }
        else
        {
          v24 = MEMORY[0x7FFE0008];
        }
        if ( v24 < v224 )
          v25 = 0;
        else
          v25 = v24 - v224;
        *(_QWORD *)(v226 + 312) += v25;
        v353 = &IDbCopyRestoreCallback::`vftable';
        if ( !v253 && *v10 )
          *v10 = 0;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset
                                          + 8LL)
                              + 96LL)
                  + 1452LL) = v200;
        if ( !v255 && *v8 )
          *v8 = 0;
        if ( v342 || (v341 & 1) != 0 )
        {
          if ( (v341 & 1) == 0 )
          {
            PageRef::Unlatch((PageRef *)&v342);
            if ( (_QWORD)v345 )
            {
              operator delete((void *)v345, 0x6FAu);
              *(_QWORD *)&v345 = 0;
            }
          }
          BootPagePtr::Release((BootPagePtr *)&v341, 0);
        }
        if ( !(_QWORD)v345 )
          goto LABEL_486;
        goto LABEL_485;
      }
    }
  }
  if ( RecoveryUnit::IsTraceEnabled() )
  {
    if ( v368 != -1 || v2 != -1 )
      RecoveryMgr::GetRedoneLSN(a1, v264, 0);
    if ( (qword_10317AD29 & 8) != 0
      || (v26 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
          *(_QWORD *)v26)
      && (v27 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v26 + 56LL)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v27, 0xD4Bu) )
    {
      v28 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v29 = *(_QWORD *)(v28 + 256);
      if ( !v29 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v29 = *(_QWORD *)(v28 + 256);
      }
      RecoveryUnit::PrintTrace(
        (RecoveryUnit *)*a1,
        L"MoveUpRedo through log block 0x%016I64x. scheduler id %d",
        v368 | ((unsigned __int64)v2 << 32),
        *(unsigned int *)(*(_QWORD *)(v29 + 608) + 3688LL));
    }
  }
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&v239);
    v30 = (DirtyPageMgr *)v239.QuadPart;
  }
  else
  {
    v30 = MEMORY[0x7FFE0008];
  }
  v202 = v30;
  if ( (*((_DWORD *)a1 + 9) & 0x80) != 0 )
  {
    LogIterImpl<LogMgr>::InitForeign((unsigned int)&v205, 0, (_DWORD)a1, a1[3080], 1);
  }
  else
  {
    v31 = *a1;
    v32 = *(_QWORD *)(*a1 + 1712LL);
    v33 = s_pServerConf;
    if ( *((_DWORD *)s_pServerConf + 2) == 2 )
    {
      v34 = 32;
      if ( (dword_10316ECB0 & 0x10) != 0 )
        v34 = 8;
      if ( *((_DWORD *)a1 + 8) == 3 )
      {
        LWSpeed = BPool::GetLWSpeed(qword_10317B628);
        v36 = v34;
        if ( LWSpeed < 0x78 )
          v36 = 4;
        v34 = v36;
      }
      v31 = *a1;
      v33 = (struct IServerConfiguration *)(unsigned int)(16 * *(_DWORD *)(*(_QWORD *)(*a1 + 1696LL) + 152LL));
      if ( v34 >= (unsigned int)v33 )
        v34 = 16 * *(_DWORD *)(*(_QWORD *)(*a1 + 1696LL) + 152LL);
    }
    else
    {
      v34 = 4;
    }
    v37 = ((*(_DWORD *)(v32 + 48) & 0x841) != 0) + 1;
    v206 = *(_QWORD *)(v31 + 1736);
    v208 = (*(__int64 (__fastcall **)(struct IServerConfiguration *, __int64, __int64, _QWORD))(*(_QWORD *)v206 + 128LL))(
             v33,
             1,
             v206,
             a1[2780]);
    (*(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD, const wchar_t *, int, int))(*(_QWORD *)v208 + 8LL))(
      v208,
      0,
      1,
      4 * v34,
      L"Secondary Redo",
      14,
      v37);
  }
  try
  {
    ExcHandler::ExcHandler(
      (ExcHandler *)v334,
      0,
      0,
      0,
      (int (*)(int, int, int, int, char *))RecoveryExceptionHandler,
      0);
    v198 = 0;
    v199 = 0;
    v211.QuadPart = 0;
    RecoveryMgr::GetRedoneLSN(a1, v360, 0);
    v216 = 0;
    v239.QuadPart = 0;
    BootPagePtr::Init(&v341, 0, *a1, 0);
    BootPagePtr::GetAccess(&v341, 2);
    if ( (v341 & 1) != 0 )
      v38 = v345;
    else
      v38 = *(_QWORD *)v342 + *(unsigned __int16 *)(*(_QWORD *)v342 + 8190LL);
    v198 = *(_QWORD *)(v38 + 588);
    v199 = *(_WORD *)(v38 + 596);
    BootPagePtr::ReleaseAccess((BootPagePtr *)&v341, 0);
    BootPagePtr::Release((BootPagePtr *)&v341, 0);
    if ( (*((_DWORD *)a1 + 9) & 0x80) != 0 )
    {
      AlignedLSN128::GetLSN((struct AlignedLSN128 *)(a1[15] + 1584LL), (struct LSN *)&v273);
      v266 = v273;
      v267 = v274;
      v268 = 0;
      AlignedLSN::AggMax((AlignedLSN *)v360, (const struct AlignedLSN *)&v266);
    }
    v39 = v208;
    (*(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v208 + 128LL))(v208, v360, 2);
    v214 = *(LSN *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 152LL))(v39) + 8);
    if ( dword_103172528
      || (v40 = *(_QWORD *)(*a1 + 1712LL), (*(_BYTE *)(v40 + 60) & 1) != 0) && !*(_QWORD *)(v40 + 640) )
    {
      RecoveryMgr::MayDeferErrorsForPru((RecoveryMgr *)a1, 0, 0);
    }
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
      QueryPerformanceCounter(&v240);
    else
      v240.QuadPart = (LONGLONG)MEMORY[0x7FFE0008];
    v291 = v240;
    v238 = (DirtyPageMgr *)v240.QuadPart;
    v212 = 0;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
      QueryPerformanceCounter(&v249);
    else
      v249.QuadPart = (LONGLONG)MEMORY[0x7FFE0008];
    v187 = (DirtyPageMgr *)v249.QuadPart;
    while ( 1 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v292);
        v41 = (DirtyPageMgr *)v292.QuadPart;
      }
      else
      {
        v41 = MEMORY[0x7FFE0008];
        v187 = MEMORY[0x7FFE0008];
      }
      v217 = v41;
      v191 = (struct LogRec *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v208 + 120LL))(v208);
      if ( !v191 && (*((_DWORD *)a1 + 9) & 0x80) == 0 )
      {
LABEL_394:
        v351[0] = 0;
        v351[1] = 0;
        v352 = 0;
        v140 = (ParallelRedoManager *)a1[4234];
        if ( v140 )
          ParallelRedoManager::DrainRedoWorkers(v140, L"MoveUpRedo End", (const struct LSN *)v351);
        if ( *((_WORD *)a1 + 11064) != *((_WORD *)a1 + 11070)
          || *((_DWORD *)a1 + 5530) != *((_DWORD *)a1 + 5533)
          || *((_DWORD *)a1 + 5531) != *((_DWORD *)a1 + 5534) )
        {
          utassert_fail(1u, "m_AnalyzeLsn == m_CurRedoLsn", "recovery.cpp", 16082, 0);
        }
        v141 = RecoveryMgr::GetRedoneLSN(a1, v333, 0);
        if ( *((_WORD *)a1 + 11064) != *(_WORD *)(v141 + 8)
          || *((_DWORD *)a1 + 5530) != *(_DWORD *)v141
          || *((_DWORD *)a1 + 5531) != *(_DWORD *)(v141 + 4) )
        {
          v269 = *(_QWORD *)((char *)a1 + 22132);
          v270 = *((_WORD *)a1 + 11070);
          v222 = a1[2765];
          v223 = *((_WORD *)a1 + 11064);
          v142 = *(_QWORD *)(*a1 + 1712LL);
          LODWORD(v185) = *(_DWORD *)(v142 + 928);
          ex_raise(33, 2, 21, 2, v185, v142 + 936, &v222, &v269, v187);
        }
        if ( v189 )
        {
          v213 = (DirtyPageMgr *)a1[2928];
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v290);
            v143 = (DirtyPageMgr *)v290.QuadPart;
          }
          else
          {
            v204.QuadPart = (LONGLONG)MEMORY[0x7FFE0008];
            v143 = MEMORY[0x7FFE0008];
          }
          v246 = v143;
          if ( v143 < v213 )
          {
            v144.QuadPart = 0;
            v204.QuadPart = 0;
          }
          else
          {
            v144.QuadPart = v143 - v213;
            v204 = v144;
          }
          v296 = v144;
          if ( v144.QuadPart == -1
            || (!Base_PublicGlobals::sm_invariantTscAvailable
              ? (v145 = v144.QuadPart / 0x2710uLL)
              : (v145 = (unsigned __int64)(1000 * v144.QuadPart)
                      / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart),
                v145 > 0x493E0) )
          {
            v146 = (const struct LogScanStats *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v208 + 152LL))(v208);
            RecoveryStatus::OutputRedoStats((RecoveryStatus *)(a1 + 2871), v146);
            RecoveryStatus::ResetForRedoStart((RecoveryStatus *)(a1 + 2871));
          }
          v147 = *(DirtyPageMgr **)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v208 + 152LL))(v208) + 8);
          v246 = v147;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v293);
            v148 = (DirtyPageMgr *)v293.QuadPart;
            v294 = (DirtyPageMgr *)v293.QuadPart;
          }
          else
          {
            v213 = MEMORY[0x7FFE0008];
            v148 = MEMORY[0x7FFE0008];
            v294 = MEMORY[0x7FFE0008];
            v147 = v246;
          }
          if ( v148 < v202 )
          {
            v149 = 0;
            v213 = 0;
          }
          else
          {
            v149 = (DirtyPageMgr *)(v148 - v202);
            v213 = v149;
          }
          v296.QuadPart = (LONGLONG)v149;
          RecoveryUnit::NoteRedo(*a1, (char *)v147 - v214.QuadPart);
          if ( a1[2780] )
          {
            v150 = RecoveryMgr::GetRedoneLSN(a1, v361, 0);
            (*(void (__fastcall **)(_QWORD, __int64, __int64))(v151 + 72))(a1[2780], 9, v150);
          }
        }
        CAutoFileOpLock::~CAutoFileOpLock((CAutoFileOpLock *)&v211);
        ExcHandler::~ExcHandler((ExcHandler *)v334);
        goto LABEL_554;
      }
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v295);
        v42 = (DirtyPageMgr *)v295.QuadPart;
      }
      else
      {
        v42 = MEMORY[0x7FFE0008];
      }
      v297 = v42;
      if ( v42 < v217 )
      {
        v43 = 0;
        v187 = 0;
      }
      else
      {
        v43 = (DirtyPageMgr *)(v42 - v217);
        v187 = v43;
      }
      v325 = v43;
      if ( v43 == (DirtyPageMgr *)-1LL )
      {
        v44 = -1;
      }
      else if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v44 = (unsigned __int64)(1000000LL * (_QWORD)v43) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
      }
      else
      {
        v44 = (unsigned __int64)v43 / 0xA;
      }
      v212 += v44;
      if ( !v191 )
      {
        if ( (*((_DWORD *)a1 + 9) & 0x80) == 0 )
          utassert_fail(1u, "IsForeignLogApply ()", "recovery.cpp", 15561, 0);
        v218 = 0;
        v219 = 0;
        NextLSN = LogIterImpl<LogMgr>::GetNextLSN(&v205, v329);
        if ( *(_WORD *)(NextLSN + 8) || *(_DWORD *)NextLSN || *(_DWORD *)(NextLSN + 4) )
        {
          if ( byte_10316EA49 || (byte_10317B107 & 2) != 0 )
          {
            v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v208 + 48LL))(v208);
            if ( *(_WORD *)v46 )
              utassert_fail(1u, "lbh->lbk_version == 0", "recovery.cpp", 15582, 0);
            v237 = *(_QWORD *)(v46 + 48);
          }
          else
          {
            utgettime((struct SQLDATEBASE *)&v237, 1, 0);
            if ( SQLDATE::DateAdd((SQLDATE *)&v237, 8, 30) )
              utassert_fail(1u, "O_SUCCESS == logBlockClosingTime.DateAdd(DPSECOND, 30)", "recovery.cpp", 15597, 0);
          }
          LogIterImpl<LogMgr>::GetNextLSN(&v205, &v220);
          v277 = v220;
          v278 = v221;
          RecoveryMgr::UpdateForeignRedoProgress(a1, &v220, &v277, v237);
          if ( byte_10316E9E6 )
          {
            v298 = RbIoXlogLogBlockIdToLinearBsn((unsigned int)v220, HIDWORD(v220), a1[3080]);
            v47 = *a1;
            PageServerStats = RecoveryUnit::GetPageServerStats((RecoveryUnit *)*a1);
            PageServerUpdateForeignRedoHash(PageServerStats, &v298, *(const struct DBTABLE **)(v47 + 1712));
          }
        }
        if ( dword_103172528 )
        {
          v49 = *a1;
          if ( !byte_10316E9EA || (qword_10317B213 & 0x4000000000LL) != 0 )
            v50 = (struct PageServerStats **)(v49 + 8680);
          else
            v50 = *(struct PageServerStats ***)(v49 + 8688);
          EmitPsCkptLagMetrics((struct FCB *)a1[15], *v50);
        }
        ForeignRedoLsn = FCB::GetForeignRedoLsn(a1[15], v350);
        RecoveryMgr::ReportRbIoRedoProgress(a1, ForeignRedoLsn, 5);
        if ( byte_10316EB21 || (byte_10317B106 & 0x10) != 0 )
          RecoveryMgr::RestoreForeignStalePages((RecoveryMgr *)a1);
        RecoveryUnit::EvaluateForeignCheckpoint((RecoveryUnit *)*a1);
        CheckForTriggerPermanentFault((struct RecoveryUnit *)*a1);
        if ( (byte_10317B104 & 0x10) != 0 )
          goto LABEL_394;
        goto LABEL_149;
      }
      v53 = v208;
      (*(void (__fastcall **)(__int64, LSN *))(*(_QWORD *)v208 + 56LL))(v208, &v335);
      v201[0] = (struct LBH *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v53 + 48LL))(v53);
      v54 = *(_QWORD *)v201[0];
      if ( **(_WORD **)v201[0] < 6u )
        v197.QuadPart = 0;
      else
        v197 = *(LSN *)(v54 + 48);
      v55 = v336;
      if ( !v336 || (v190 = 1, v336 != *(_WORD *)(v54 + 2)) )
        v190 = 0;
      if ( (*((_DWORD *)a1 + 9) & 0x80) != 0 )
      {
        v216 = RbIoXlogLogBlockIdToLinearBsn(v335.LowPart, (unsigned int)v335.HighPart, a1[3080]);
        v55 = v336;
      }
      if ( v55 != 1 )
        goto LABEL_213;
      v239 = v335;
      if ( v2 >= v335.LowPart && (v2 > v335.LowPart || v368 > v335.HighPart) )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v208 + 112LL))(v208, 0);
      v56 = (*((_DWORD *)a1 + 9) & 0x80) != 0;
      if ( *(_BYTE *)(v203.QuadPart + 91) )
        break;
      if ( (*((_DWORD *)a1 + 9) & 0x80) != 0 )
        goto LABEL_168;
LABEL_213:
      if ( (*((_DWORD *)a1 + 9) & 0x80) != 0 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v305);
          v69 = (DirtyPageMgr *)v305.QuadPart;
        }
        else
        {
          v69 = MEMORY[0x7FFE0008];
          v187 = MEMORY[0x7FFE0008];
        }
        v193 = v69;
        if ( IsLogSelectedForForeignLogApply(v191, (const struct LSN *)&v335, (struct FCB *)a1[15]) )
        {
          if ( byte_10316E9E6 )
          {
            v73 = *(const struct DBTABLE **)(*a1 + 1712LL);
            v74 = RecoveryUnit::GetPageServerStats((RecoveryUnit *)*a1);
            PageServerUpdateForeignRedoHash(v74, &v216, v73);
            v70 = 0;
            v72 = 10;
            v245 = 10;
            v75 = &v335;
            v306 = &v335;
            v289 = 0;
            v76 = 0;
            v247 = 0;
            while ( !v76 )
            {
              v70 = _mm_crc32_u64((unsigned int)v70, v335.QuadPart);
              v72 = (unsigned int)(v72 - 8);
              v245 = v72;
              v306 = ++v75;
              v76 = 1;
              v247 = 1;
            }
            v71 = 0;
            v241 = 0;
            while ( (unsigned int)v71 < (unsigned int)v72 )
            {
              v70 = _mm_crc32_u8(v70, *((_BYTE *)&v75->LowPart + (unsigned int)v71));
              v71 = (unsigned int)(v71 + 1);
              v241 = v71;
            }
            *((_DWORD *)v74 + 110) ^= v70;
          }
          if ( *((_BYTE *)v191 + 22) < 0x7Fu )
          {
            v77 = (struct LogRec *)a1[2778];
            if ( !v77 )
            {
              ClientProcessGlobals = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals(v71, v70, v72);
              DefaultMemoryClerksForNode = PerProcessGlobals::GetDefaultMemoryClerksForNode(ClientProcessGlobals, 0);
              SOS_OS::GetClientProcessGlobals(v81, v80, v82);
              v83 = (**((__int64 (__fastcall ***)(__int64, __int64, _QWORD))DefaultMemoryClerksForNode[15] + 8))(
                      (__int64)DefaultMemoryClerksForNode[15] + 64,
                      3,
                      0);
              a1[2778] = v83;
              v77 = (struct LogRec *)v83;
              if ( !v83 )
              {
                utassert_fail(1u, "m_LogRecBufferMemory", "recovery.cpp", 12338, 0);
                v77 = (struct LogRec *)a1[2778];
              }
            }
            RecoveryMgr::RemapForeignLogPageId((RecoveryMgr *)a1, v191, v77);
            v191 = v77;
          }
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v307);
            v84 = (DirtyPageMgr *)v307.QuadPart;
          }
          else
          {
            v84 = MEMORY[0x7FFE0008];
          }
          v308 = v84;
          if ( v84 < v193 )
          {
            v85 = 0;
            v187 = 0;
          }
          else
          {
            v85 = (DirtyPageMgr *)(v84 - v193);
            v187 = v85;
          }
          v328 = v85;
          if ( v85 == (DirtyPageMgr *)-1LL )
          {
            v86 = -1;
          }
          else if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            v86 = (unsigned __int64)(1000000LL * (_QWORD)v85)
                / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
          }
          else
          {
            v86 = (unsigned __int64)v85 / 0xA;
          }
          RecoveryMgr::UpdateLogReplayExecutionTimeStats(a1, 11, v86);
          goto LABEL_243;
        }
      }
      else
      {
LABEL_243:
        v87 = RecoveryMgr::GetRedoneLSN(a1, v331, 0);
        if ( v335.LowPart > *(_DWORD *)v87
          || v335.LowPart == *(_DWORD *)v87
          && ((v88 = *(_DWORD *)(v87 + 4), v335.HighPart > v88) || v335.HighPart == v88 && v336 > *(_WORD *)(v87 + 8)) )
        {
          if ( *(_BYTE *)(*a1 + 8297LL) )
          {
            v90 = (ParallelRedoManager *)a1[4234];
            if ( v90 )
              ParallelRedoManager::DrainRedoWorkers(v90, L"RedoPaused", (const struct LSN *)&v335);
            goto LABEL_394;
          }
          if ( a1[2930] )
          {
            v229 = *a1 + 8360LL;
            v230 = 0;
            TAutoMutex<SOS_Mutex,1>::GetAccess(&v229, 4195132);
            v91 = (unsigned int (__fastcall ***)(_QWORD, struct LogRec *, LSN *, _QWORD))a1[2930];
            if ( v91 && (**v91)(v91, v191, &v335, 0) )
            {
              *((_BYTE *)a1 + 22233) = 1;
              v92 = v230;
              v93 = v229;
              while ( v92 )
              {
                *(_QWORD *)(v93 + 48) = 0;
                EventAutoInternal<SuspendQueueSLock>::Signal(v93, 0);
                v230 = --v92;
              }
              goto LABEL_394;
            }
            v94 = v230;
            v95 = v229;
            while ( v94 )
            {
              *(_QWORD *)(v95 + 48) = 0;
              EventAutoInternal<SuspendQueueSLock>::Signal(v95, 0);
              v230 = --v94;
            }
          }
          v197 = v335;
          if ( v2 < v335.LowPart || v2 <= v335.LowPart && v368 < v335.HighPart )
          {
            v214 = *(LSN *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v208 + 152LL))(v208) + 8);
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
              QueryPerformanceCounter(&v204);
            else
              v204.QuadPart = (LONGLONG)MEMORY[0x7FFE0008];
            v202 = (DirtyPageMgr *)v204.QuadPart;
            goto LABEL_394;
          }
          if ( v336 == 1 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v310);
              v96 = (DirtyPageMgr *)v310.QuadPart;
            }
            else
            {
              v96 = MEMORY[0x7FFE0008];
            }
            v311 = v96;
            RecoveryStatus::NoteLogBlockRead(a1 + 2871, 1);
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v312);
              v97 = (DirtyPageMgr *)v312.QuadPart;
            }
            else
            {
              v97 = MEMORY[0x7FFE0008];
            }
            v313 = v97;
            RecoveryStatus::NoteLogBlockRead(a1 + 2871, 2);
            v98 = *(LSN *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v208 + 152LL))(v208) + 8);
            v197 = v98;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v314);
              v99 = (DirtyPageMgr *)v314.QuadPart;
              v315 = (DirtyPageMgr *)v314.QuadPart;
            }
            else
            {
              v99 = MEMORY[0x7FFE0008];
              v315 = MEMORY[0x7FFE0008];
              v98 = v197;
            }
            if ( v99 < v202 )
              v100 = 0;
            else
              v100 = (DirtyPageMgr *)(v99 - v202);
            v187 = v100;
            RecoveryUnit::NoteRedo(*a1, v98.QuadPart - v214.QuadPart);
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v279);
              v202 = (DirtyPageMgr *)v279.QuadPart;
            }
            else
            {
              v187 = MEMORY[0x7FFE0008];
              v202 = MEMORY[0x7FFE0008];
              v98 = v197;
            }
            v214 = v98;
            if ( v189 )
            {
              v282 = a1[2928];
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v280);
                v101 = (DirtyPageMgr *)v280.QuadPart;
              }
              else
              {
                v101 = MEMORY[0x7FFE0008];
              }
              v281 = v101;
              if ( (unsigned __int64)v101 < v282 )
              {
                v102 = 0;
                v187 = 0;
              }
              else
              {
                v102 = (DirtyPageMgr *)((char *)v101 - v282);
                v187 = v102;
              }
              v326 = v102;
              if ( v102 == (DirtyPageMgr *)-1LL
                || (!Base_PublicGlobals::sm_invariantTscAvailable
                  ? (v103 = (unsigned __int64)v102 / 0x2710)
                  : (v103 = (unsigned __int64)(1000LL * (_QWORD)v102)
                          / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart),
                    v103 > 0x493E0) )
              {
                v104 = (const struct LogScanStats *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v208 + 152LL))(v208);
                RecoveryStatus::OutputRedoStats((RecoveryStatus *)(a1 + 2871), v104);
                RecoveryStatus::ResetForRedoStart((RecoveryStatus *)(a1 + 2871));
                if ( a1[2780] )
                {
                  v105 = RecoveryMgr::GetRedoneLSN(a1, v363, 0);
                  (*(void (__fastcall **)(_QWORD, __int64, __int64))(v106 + 72))(a1[2780], 9, v105);
                }
              }
            }
            if ( (*((_DWORD *)a1 + 9) & 0x80) == 0 )
              RecoveryUnit::EvaluateRecovery((RecoveryUnit *)*a1);
          }
          if ( !*((_WORD *)v191 + 1) )
            utassert_fail(1u, "lp->log_fixedLength > 0", "recovery.cpp", 15907, 0);
          if ( !*((_BYTE *)v191 + 22) )
            utassert_fail(1u, "lp->GetOpCode () != LOP_NULL", "recovery.cpp", 15908, 0);
          if ( a1[2930] )
          {
            v227 = *a1 + 8360LL;
            v228 = 0;
            TAutoMutex<SOS_Mutex,1>::GetAccess(&v227, 4195132);
            v107 = (unsigned int (__fastcall ***)(_QWORD, struct LogRec *, LSN *, _QWORD))a1[2930];
            if ( v107 && (**v107)(v107, v191, &v335, 0) )
            {
              if ( (qword_10317AD29 & 8) != 0
                || (v108 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset)) != 0
                && (v109 = **(struct CSessionTraceFlags ***)(v108 + 56)) != 0
                && CSessionTraceFlags::CheckSessionTraceInternal(v109, 0xD4Bu) )
              {
                PerformanceCount.LowPart = 92;
                v210 = 100;
                GetLsnAsDecimalString((const struct LSN *)&v335, &v210, v366);
                LSN::FormatAsHexString(&v335, v364, (unsigned int *)&PerformanceCount);
                LODWORD(v186) = *((_DWORD *)v191 + 4);
                LODWORD(v185) = *((unsigned __int16 *)v191 + 10);
                traceprint(
                  L"REDO LSN %.*ls (0x%ls), XdesId 0x%04lx:%08lx Before termination LSN reached.\n",
                  (unsigned __int64)v210 >> 1,
                  v366,
                  v364,
                  v185,
                  v186);
              }
              *((_BYTE *)a1 + 22233) = 1;
              v110 = v228;
              v111 = v227;
              while ( v110 )
              {
                *(_QWORD *)(v111 + 48) = 0;
                EventAutoInternal<SuspendQueueSLock>::Signal(v111, 0);
                v228 = --v110;
              }
              goto LABEL_394;
            }
            v112 = (*(__int64 (__fastcall **)(_QWORD, struct LogRec *, LSN *))(*(_QWORD *)a1[2930] + 8LL))(
                     a1[2930],
                     v191,
                     &v335);
            v113 = v188;
            if ( v112 )
              v113 = 1;
            v188 = v113;
            v114 = v228;
            v115 = v227;
            while ( v114 )
            {
              *(_QWORD *)(v115 + 48) = 0;
              EventAutoInternal<SuspendQueueSLock>::Signal(v115, 0);
              v228 = --v114;
            }
          }
          v189 = 1;
          v116 = v336;
          HighPart = v335.HighPart;
          *((_DWORD *)a1 + 5533) = v335.LowPart;
          *((_DWORD *)a1 + 5534) = HighPart;
          *((_WORD *)a1 + 11070) = v116;
          v316 = v335;
          v317 = v336;
          v258 = v335;
          v259 = v336;
          v260 = 0;
          SOS_Atomic<AlignedLSN>::operator=(a1 + 2768, &v258);
          *((_BYTE *)a1 + 22212) = v190;
          v120 = 1;
          if ( (qword_10317AD29 & 0x800000000000000LL) == 0 )
          {
            v118 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset);
            if ( !v118
              || (v119 = **(struct CSessionTraceFlags ***)(v118 + 56)) == 0
              || !CSessionTraceFlags::CheckSessionTraceInternal(v119, 0xD83u) )
            {
              v120 = 0;
            }
          }
          v121 = (RecoveryUnit *)*a1;
          if ( (*(_BYTE *)(*a1 + 7376LL) & 0x40) != 0 )
          {
            if ( byte_10317AE3A < 0
              || (v122 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset,
                  *(_QWORD *)v122)
              && (v123 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v122 + 56LL)) != 0
              && (v124 = CSessionTraceFlags::CheckSessionTraceInternal(v123, 0x15D7u), v121 = (RecoveryUnit *)*a1, v124) )
            {
              RecoveryUnit::PrintTrace(v121, L"TrySwitchToParallelRedo :: Disable Lazy Redo for Auxiliary Replica");
              v121 = (RecoveryUnit *)*a1;
            }
            *((_BYTE *)v121 + 26105) = 0;
          }
          else if ( *((_BYTE *)a1 + 33896) != v120 )
          {
            *((_BYTE *)a1 + 33896) = v120;
            if ( !v120 && !a1[4234] )
            {
              v125 = (byte_10316E943 || (qword_10317AD29 & 0x200000000000000LL) != 0)
                  && (qword_10317AD29 & 0x800000000000000LL) == 0;
              *((_BYTE *)v121 + 26105) = v125;
              RecoveryMgr::StartParallelRedoManager((RecoveryMgr *)a1);
              v126 = a1[4234];
              if ( v126 )
              {
                *(_DWORD *)(v126 + 368) = 6;
                *(_BYTE *)(a1[3056] + 28LL) = 1;
                if ( RecoveryUnit::IsTraceEnabled() )
                {
                  LogOpString = GetLogOpString(*((unsigned __int8 *)v191 + 22));
                  LODWORD(v185) = v336;
                  RecoveryUnit::PrintTrace(
                    (RecoveryUnit *)*a1,
                    L"Switch to parallel redo at lsn [0x%x:0x%x:0x%x]; opCode: %ls",
                    v335.LowPart,
                    (unsigned int)v335.HighPart,
                    v185,
                    LogOpString);
                }
              }
            }
          }
          if ( (*((_DWORD *)a1 + 9) & 0x80) == 0
            && (*((unsigned __int8 *)v191 + 22) == 150 || *((unsigned __int8 *)v191 + 22) == 153) )
          {
            CAutoFileOpLock::Acquire((CAutoFileOpLock *)&v211, *(struct FileMgr **)(*a1 + 1696LL));
          }
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v283);
            v128 = (DirtyPageMgr *)v283.QuadPart;
          }
          else
          {
            v128 = MEMORY[0x7FFE0008];
          }
          v194 = v128;
          RecoveryMgr::AnalyzeLogRecord((RecoveryMgr *)a1, v191, (const struct LSN *)&v335, 1, v201[0]);
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v284);
            v129 = (DirtyPageMgr *)v284.QuadPart;
          }
          else
          {
            v129 = MEMORY[0x7FFE0008];
          }
          v285 = v129;
          if ( v129 < v194 )
            v130 = 0;
          else
            v130 = v129 - v194;
          v324 = v130;
          if ( v130 == -1 )
          {
            v131 = -1;
          }
          else if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            v131 = 1000000 * v130 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
          }
          else
          {
            v131 = v130 / 0xA;
          }
          RecoveryMgr::UpdateLogReplayExecutionTimeStats(a1, 12, v131);
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v286);
            v132 = (DirtyPageMgr *)v286.QuadPart;
          }
          else
          {
            v132 = MEMORY[0x7FFE0008];
          }
          v195 = v132;
          RecoveryMgr::RedoLogRecord((RecoveryMgr *)a1, v191, 1, 0);
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v287);
            v133 = (DirtyPageMgr *)v287.QuadPart;
          }
          else
          {
            v133 = MEMORY[0x7FFE0008];
          }
          v288 = v133;
          if ( v133 < v195 )
          {
            v134 = 0;
            v187 = 0;
          }
          else
          {
            v134 = (DirtyPageMgr *)(v133 - v195);
            v187 = v134;
          }
          v323 = v134;
          if ( v134 == (DirtyPageMgr *)-1LL )
          {
            v135 = -1;
          }
          else if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            v135 = (unsigned __int64)(1000000LL * (_QWORD)v134)
                 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
          }
          else
          {
            v135 = (unsigned __int64)v134 / 0xA;
          }
          RecoveryMgr::UpdateLogReplayExecutionTimeStats(a1, 13, v135);
          CAutoFileOpLock::~CAutoFileOpLock((CAutoFileOpLock *)&v211);
          if ( (*((_DWORD *)a1 + 9) & 0x80) == 0 )
          {
            EmptyVerStateMgr::UpdateStateInRedo(
              (EmptyVerStateMgr *)(*(_QWORD *)(*a1 + 1712LL) + 1536LL),
              (struct RecoveryUnit *)*a1);
            v264[0] = 0;
            v264[1] = 0;
            v265 = 0;
            if ( v199 || v198 )
            {
              LastRedoneLSN = RecoveryUnit::GetLastRedoneLSN(*a1, v332);
              if ( *(_DWORD *)LastRedoneLSN >= (unsigned int)v198 )
              {
                if ( *(_DWORD *)LastRedoneLSN != (_DWORD)v198
                  || (v136 = *(_DWORD *)(LastRedoneLSN + 4), v136 >= HIDWORD(v198))
                  && (v136 != HIDWORD(v198) || *(_WORD *)(LastRedoneLSN + 8) >= v199) )
                {
                  v137 = (const struct LSN *)RecoveryUnit::GetLastRedoneLSN(*a1, v362);
                  HadrRecoveryCallbacks::PageUndoCleared((struct RecoveryUnit *)*a1, v137);
                  LastRedoneLSN = *a1;
                  v261 = *(_QWORD *)(*a1 + 7308LL);
                  v262 = *(_WORD *)(LastRedoneLSN + 7316);
                  v263 = *(_WORD *)(LastRedoneLSN + 7318);
                  v198 = v261;
                  v199 = *(_WORD *)(LastRedoneLSN + 7316);
                }
              }
            }
          }
          if ( v188 )
          {
            if ( (qword_10317AD29 & 8) != 0
              || (v138 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset)) != 0
              && (v139 = **(struct CSessionTraceFlags ***)(v138 + 56)) != 0
              && CSessionTraceFlags::CheckSessionTraceInternal(v139, 0xD4Bu) )
            {
              LODWORD(v201[0]) = 92;
              v196 = 100;
              GetLsnAsDecimalString((const struct LSN *)&v335, &v196, v367);
              LSN::FormatAsHexString(&v335, v365, (unsigned int *)v201);
              LODWORD(v186) = *((_DWORD *)v191 + 4);
              LODWORD(v185) = *((unsigned __int16 *)v191 + 10);
              traceprint(
                L"REDO LSN %.*ls (0x%ls), XdesId 0x%04lx:%08lx Stop after termination LSN reached.\n",
                (unsigned __int64)v196 >> 1,
                v367,
                v365,
                v185,
                v186);
            }
            goto LABEL_394;
          }
LABEL_149:
          LOBYTE(LastRedoneLSN) = -122;
          YieldAndCheckForAbort(LastRedoneLSN);
        }
        else
        {
          v214 = *(LSN *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v208 + 152LL))(v208) + 8);
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v309);
            v89 = (DirtyPageMgr *)v309.QuadPart;
          }
          else
          {
            v89 = MEMORY[0x7FFE0008];
            v187 = MEMORY[0x7FFE0008];
          }
          v202 = v89;
        }
      }
    }
    if ( (*((_DWORD *)a1 + 9) & 0x80) != 0 )
    {
      utassert_fail(1u, "!(isSocratesCompute) || (!isSocratesPageServer)", "recovery.cpp", 15687, 0);
      utassert_fail(1u, "!(isSocratesPageServer) || (!isSocratesCompute)", "recovery.cpp", 15688, 0);
    }
    RecoveryMgr::UpdateLogReplayExecutionTimeStats(a1, 1, v212);
LABEL_168:
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v299);
      v57 = (DirtyPageMgr *)v299.QuadPart;
      v300 = (DirtyPageMgr *)v299.QuadPart;
    }
    else
    {
      v57 = MEMORY[0x7FFE0008];
      v300 = MEMORY[0x7FFE0008];
    }
    if ( v57 < v238 )
    {
      v58 = 0;
      v187 = 0;
    }
    else
    {
      v58 = (DirtyPageMgr *)(v57 - v238);
      v187 = v58;
    }
    v327 = v58;
    if ( v58 == (DirtyPageMgr *)-1LL )
    {
      v59 = -1;
    }
    else if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      v59 = (unsigned __int64)(1000000LL * (_QWORD)v58) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
    }
    else
    {
      v59 = (unsigned __int64)v58 / 0xA;
    }
    RecoveryMgr::UpdateLogReplayExecutionTimeStats(a1, 2, v59 - v212);
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v301);
      v238 = (DirtyPageMgr *)v301.QuadPart;
    }
    else
    {
      v187 = MEMORY[0x7FFE0008];
      v238 = MEMORY[0x7FFE0008];
    }
    v212 = 0;
    RecoveryMgr::ReportRbIoRedoProgress(a1, &v335, 5);
    if ( v56 )
    {
      if ( dword_103172528 )
      {
        v60 = *a1;
        if ( !byte_10316E9EA || (qword_10317B213 & 0x4000000000LL) != 0 )
          v61 = (struct PageServerStats **)(v60 + 8680);
        else
          v61 = *(struct PageServerStats ***)(v60 + 8688);
        EmitPsCkptLagMetrics((struct FCB *)a1[15], *v61);
      }
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v302);
        v62 = (DirtyPageMgr *)v302.QuadPart;
      }
      else
      {
        v62 = MEMORY[0x7FFE0008];
      }
      v192 = v62;
      v339 = v335;
      v340 = v336;
      if ( byte_10316EBBA )
      {
        v63 = *(_WORD *)(*(_QWORD *)v201[0] + 6LL);
        if ( v63 <= *(_WORD *)(*(_QWORD *)v201[0] + 4LL) )
          v63 = *(_WORD *)(*(_QWORD *)v201[0] + 4LL);
        RbIoXlogLinearBsnToLogBlockId(v216 + ((unsigned __int64)v63 >> 9), a1[3080], &v242, &v244);
        v339.QuadPart = __PAIR64__(v244, v242);
        v340 = 1;
      }
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))RecoveryMgr::UpdateForeignRedoProgress)(
        a1,
        &v335,
        &v339,
        (LSN)v197.QuadPart);
      if ( byte_10316E9E6 )
      {
        v64 = *a1;
        v65 = RecoveryUnit::GetPageServerStats((RecoveryUnit *)*a1);
        PageServerUpdateForeignRedoHash(v65, &v216, *(const struct DBTABLE **)(v64 + 1712));
      }
      if ( byte_10316EB21 || (byte_10317B106 & 0x10) != 0 )
        RecoveryMgr::RestoreForeignStalePages((RecoveryMgr *)a1);
      RecoveryUnit::EvaluateForeignCheckpoint((RecoveryUnit *)*a1);
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v303);
        v66 = (DirtyPageMgr *)v303.QuadPart;
      }
      else
      {
        v66 = MEMORY[0x7FFE0008];
      }
      v304 = v66;
      if ( v66 < v192 )
      {
        v67 = 0;
        v187 = 0;
      }
      else
      {
        v67 = (DirtyPageMgr *)(v66 - v192);
        v187 = v67;
      }
      v322 = v67;
      if ( v67 == (DirtyPageMgr *)-1LL )
        v68 = -1;
      else
        v68 = Base_PublicGlobals::sm_invariantTscAvailable
            ? (unsigned __int64)(1000000LL * (_QWORD)v67) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart
            : (unsigned __int64)v67 / 0xA;
      RecoveryMgr::UpdateLogReplayExecutionTimeStats(a1, 10, v68);
      CheckForTriggerPermanentFault((struct RecoveryUnit *)*a1);
      if ( (byte_10317B104 & 0x10) != 0 )
        goto LABEL_394;
    }
    goto LABEL_213;
  }
  catch ( SQLError v275 )
  {
    ExceptionBackout::ExceptionBackout((ExceptionBackout *)v318, (const struct SQLError *)&v275);
    v161 = 21;
    v162 = v215;
    v163 = v215[3079]++ & 3LL;
    v164 = &v162[2 * (unsigned int)v163];
    SOS_Task::GetExceptionInfo((struct WorkerExceptInfo *)(v164 + 3071));
    if ( RecoveryUnit::IsTraceEnabled() )
      RecoveryUnit::PrintTrace(
        (RecoveryUnit *)*v162,
        L"MoveUpRedo failed with error %d, severity %d, address %p.",
        *((unsigned int *)v164 + 6142),
        *((unsigned int *)v164 + 6143),
        v162[2 * v163 + 3072]);
    v165 = v275;
    if ( v276 == 1 )
      v166 = v275;
    else
      v166 = (unsigned __int16)v275;
    if ( v166 != 3617 )
    {
      if ( v276 != 1 )
        v165 = (unsigned __int16)v275;
      if ( v165 != 3602 )
        goto LABEL_506;
    }
    if ( !(unsigned int)SOS_Task::IsCurrentAbortBitSet() )
      goto LABEL_506;
    if ( (*((_DWORD *)v162 + 9) & 0x80) != 0 )
    {
      RecoveryMgr::ShutdownParallelRedoMgr((RecoveryMgr *)v162, 1);
      v319 = v275;
      v320 = v276;
      ex_raisecontrol(&v319);
    }
    v167 = *(_QWORD *)(*v162 + 1712LL);
    if ( (*(_BYTE *)(v167 + 60) & 1) == 0 || *(_QWORD *)(v167 + 640) )
    {
LABEL_506:
      if ( *((_DWORD *)v164 + 6143) == 17 )
        v161 = 17;
      v196 = v161;
      if ( (*((_DWORD *)v162 + 9) & 0x80) != 0 )
      {
        v172 = v191;
      }
      else
      {
        if ( (qword_10317AD29 & 0x200) != 0
          || ((LODWORD(v201[0]) = 0,
               (v169 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset)) != 0)
           && (v170 = **(struct CSessionTraceFlags ***)(v169 + 56)) != 0
            ? (v171 = CSessionTraceFlags::CheckSessionTraceInternal(v170, 0xD51u))
            : (v171 = (int)v201[0]),
              v161 = v196,
              v171) )
        {
          dump_log((struct RecoveryUnit *)*v162, 2, 0);
        }
        v172 = v191;
        if ( v191 )
        {
          if ( word_10318AB38 != *((_WORD *)v191 + 10) || NullXdesId != *((_DWORD *)v191 + 4) )
          {
            v250 = *((_DWORD *)v191 + 4);
            v251 = *((_WORD *)v191 + 10);
            v256 = 0;
            v257 = 0;
            DumpLogForFailures(L"for MoveUpRedo failure - filter XdesId", *v162, 0, (char *)v162 + 22108, &v256, &v250);
          }
        }
        RecXdesTable::GetMinBeginLsn(
          (RecXdesTable *)(v162 + 2932),
          (struct LSN *)&v337,
          1,
          0,
          (struct LSN *)((char *)v162 + 22132));
        v222 = 0;
        v223 = 0;
        if ( !v338 && !v337 )
        {
          v337 = v162[2752];
          v177 = *((_WORD *)v162 + 11012);
        }
        else
        {
          v175 = (unsigned int)v337 < *((_DWORD *)v162 + 5504)
              || (_DWORD)v337 == *((_DWORD *)v162 + 5504)
              && (HIDWORD(v337) < *((_DWORD *)v162 + 5505)
               || HIDWORD(v337) == *((_DWORD *)v162 + 5505) && v338 < *((_WORD *)v162 + 11012));
          v176 = &v337;
          if ( !v175 )
            v176 = v162 + 2752;
          v337 = *v176;
          v177 = *((_WORD *)v176 + 4);
        }
        v338 = v177;
        v231 = NullXdesId;
        v232 = word_10318AB38;
        v233 = 0;
        v234 = 0;
        DumpLogForFailures(L"for MoveUpRedo failure - no filter", *v162, 0, &v337, &v233, &v231);
        LOBYTE(v178) = 1;
        v179 = RecoveryMgr::GetRedoneLSN(v162, &v330, v178);
        if ( *((_WORD *)v162 + 11064) != *(_WORD *)(v179 + 8)
          || *((_DWORD *)v162 + 5530) != *(_DWORD *)v179
          || *((_DWORD *)v162 + 5531) != *(_DWORD *)(v179 + 4) )
        {
          RecoveryUnit::RecoveryFailure((RecoveryUnit *)*v162, v161, 0);
        }
      }
      RecoveryMgr::ShutdownParallelRedoMgr((RecoveryMgr *)v162, 1);
      if ( v172 && *((_BYTE *)v172 + 22) < 0x7Fu )
      {
        v235 = *((_DWORD *)v172 + 6);
        v236 = *((_WORD *)v172 + 14);
        v181 = &v235;
      }
      else
      {
        LODWORD(v215) = 0;
        WORD2(v215) = 0;
        v181 = (int *)&v215;
      }
      v271 = *(_QWORD *)((char *)v162 + 22132);
      v272 = *((_WORD *)v162 + 11070);
      v203.LowPart = *v181;
      WORD2(v203.QuadPart) = *((_WORD *)v181 + 2);
      v182 = *(_QWORD *)(*v162 + 1712LL);
      LODWORD(v183) = *(_DWORD *)(v182 + 928);
      ex_raise(33, 13, v161, 2, v183, v182 + 936, &v203, &v271);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v318);
      goto LABEL_554;
    }
    RecoveryMgr::ShutdownParallelRedoMgr((RecoveryMgr *)v162, 1);
    ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v318);
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v203);
      v152 = (DirtyPageMgr *)v203.QuadPart;
    }
    else
    {
      v152 = MEMORY[0x7FFE0008];
    }
    if ( v152 < v224 )
      v153 = 0;
    else
      v153 = v152 - v224;
    *(_QWORD *)(v226 + 8LL * v225 + 104) += v153;
    v353 = &IDbCopyRestoreCallback::`vftable';
    if ( !v253 && *v252 )
      *v252 = 0;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1452LL) = v200;
    if ( !v255 && *v254 )
      *v254 = 0;
    BootPagePtr::~BootPagePtr((BootPagePtr *)&v341);
    v205 = &SLogIterForward::`vftable';
    v154 = v208;
    if ( v208 )
    {
LABEL_439:
      (**(void (__fastcall ***)(__int64, __int64))v208)(v154, 1);
      v208 = 0;
    }
    return;
  }
LABEL_554:
  v155 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v156 = *(struct Worker **)(v155 + 256);
  if ( !v156 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v156 = *(struct Worker **)(v155 + 256);
  }
  if ( *((_DWORD *)v156 + 139) )
    ExceptionPostCatchActions(v156);
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&v243);
    v157 = (DirtyPageMgr *)v243.QuadPart;
  }
  else
  {
    v157 = MEMORY[0x7FFE0008];
  }
  if ( v157 < v224 )
    v158 = 0;
  else
    v158 = v157 - v224;
  *(_QWORD *)(v226 + 8LL * v225 + 104) += v158;
  v353 = &IDbCopyRestoreCallback::`vftable';
  if ( !v253 && *v252 )
    *v252 = 0;
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                    + SystemThread_TlsOffset
                                    + 8LL)
                        + 96LL)
            + 1452LL) = v200;
  if ( !v255 && *v254 )
    *v254 = 0;
  if ( v342 || (v341 & 1) != 0 )
  {
    if ( (v341 & 1) == 0 )
    {
      PageRef::Unlatch((PageRef *)&v342);
      if ( (_QWORD)v345 )
      {
        operator delete((void *)v345, 0x6FAu);
        *(_QWORD *)&v345 = 0;
      }
    }
    BootPagePtr::Release((BootPagePtr *)&v341, 0);
  }
  if ( (_QWORD)v345 )
  {
    operator delete((void *)v345, 0x6FAu);
    *(_QWORD *)&v345 = 0;
  }
  PageRef::~PageRef((PageRef *)&v342);
  v205 = &SLogIterForward::`vftable';
  v154 = v208;
  if ( v208 )
    goto LABEL_439;
  return;
}

```

## disassembly

```asm
0x101cd0460  mov     [rsp+arg_8], rdx
0x101cd0465  mov     r11, rsp
0x101cd0468  push    rdi
0x101cd0469  push    r12
0x101cd046b  push    r13
0x101cd046d  push    r14
0x101cd046f  push    r15
0x101cd0471  sub     rsp, 7C0h
0x101cd0478  mov     qword ptr [r11-388h], 0FFFFFFFFFFFFFFFEh
0x101cd0483  mov     [r11+18h], rbx
0x101cd0487  mov     [r11+20h], rsi
0x101cd048b  mov     rax, cs:__security_cookie
0x101cd0492  xor     rax, rsp
0x101cd0495  mov     [rsp+7E8h+var_38], rax
0x101cd049d  mov     rdi, rdx
0x101cd04a0  mov     r15, rcx
0x101cd04a3  mov     [rsp+7E8h+var_6C0], rcx
0x101cd04ab  xor     ebx, ebx
0x101cd04ad  mov     [rsp+7E8h+var_798], rbx
0x101cd04b2  lea     rax, ??_7LogIter@@6B@; const LogIter::`vftable'
0x101cd04b9  mov     [r11-710h], rax
0x101cd04c0  lea     rsi, ??_7SLogIterForward@@6B@; const SLogIterForward::`vftable'
0x101cd04c7  mov     [r11-710h], rsi
0x101cd04ce  mov     [r11-708h], rbx
0x101cd04d5  mov     r10d, 1
0x101cd04db  mov     [r11-700h], r10d
0x101cd04e2  mov     [r11-6F8h], rbx
0x101cd04e9  mov     [rsp+7E8h+var_6F0], bl
0x101cd04f0  lea     rax, ??_7SLogIterForward@@6B@; const SLogIterForward::`vftable'
0x101cd04f7  mov     [r11-710h], rax
0x101cd04fe  mov     [rsp+7E8h+var_79F], bl
0x101cd0502  mov     [rsp+7E8h+var_7A0], bl
0x101cd0506  mov     [rsp+7E8h+var_2A8], ebx
0x101cd050d  mov     [r11-2A0h], rbx
0x101cd0514  mov     [rsp+7E8h+var_298], bl
0x101cd051b  mov     [rsp+7E8h+var_294], ebx
0x101cd0522  mov     [r11-278h], rbx
0x101cd0529  mov     [rsp+7E8h+var_270], ebx
0x101cd0530  xorps   xmm0, xmm0
0x101cd0533  movdqa  [rsp+7E8h+var_288], xmm0
0x101cd053c  mov     [r11-268h], rbx
0x101cd0543  mov     [rsp+7E8h+var_260], ebx
0x101cd054a  mov     r14, [rcx]
0x101cd054d  test    byte ptr [r14+1CD0h], 20h
0x101cd0555  jz      loc_101CD0684
0x101cd055b  mov     rcx, [r14+6C8h]
0x101cd0562  mov     rax, [rcx]
0x101cd0565  lea     rdx, [r11-2C0h]
0x101cd056c  call    qword ptr [rax+170h]
0x101cd0572  lea     rdx, [r15+5674h]; struct LSN *
0x101cd0579  mov     eax, dword ptr [rsp+7E8h+var_2C0]
0x101cd0580  mov     [rdx], eax
0x101cd0582  mov     eax, dword ptr [rsp+7E8h+var_2C0+4]
0x101cd0589  mov     [rdx+4], eax
0x101cd058c  movzx   eax, [rsp+7E8h+var_2B8]
0x101cd0594  mov     [rdx+8], ax
0x101cd0598  mov     rcx, r15; this
0x101cd059b  call    ?SetLastRedoneLSN@RecoveryMgr@@QEAAXAEBVLSN@@@Z; RecoveryMgr::SetLastRedoneLSN(LSN const &)
0x101cd05a0  mov     rax, [r15]
0x101cd05a3  mov     rcx, [rax+6C8h]
0x101cd05aa  mov     rax, [rcx]
0x101cd05ad  call    qword ptr [rax+290h]
0x101cd05b3  test    rax, rax
0x101cd05b6  jz      short loc_101CD05FB
0x101cd05b8  mov     [rsp+7E8h+var_250], ebx
0x101cd05bf  mov     [rsp+7E8h+var_258], edi
0x101cd05c6  mov     eax, dword ptr [rsp+7E8h+arg_8+4]
0x101cd05cd  mov     [rsp+7E8h+var_254], eax
0x101cd05d4  mov     rax, [r15]
0x101cd05d7  mov     rcx, [rax+6C8h]
0x101cd05de  mov     rax, [rcx]
0x101cd05e1  call    qword ptr [rax+290h]
0x101cd05e7  mov     rcx, rax
0x101cd05ea  lea     r8, [rsp+7E8h+var_258]
0x101cd05f2  lea     edx, [rbx+9]
0x101cd05f5  call    ?OverrideCacheHoldup@LogPoolMgr@@QEAAXW4_TruncationHoldup@@AEBVAlignedLSN@@@Z; LogPoolMgr::OverrideCacheHoldup(_TruncationHoldup,AlignedLSN const &)
0x101cd05fa  nop
0x101cd05fb  mov     eax, [rsp+7E8h+var_2A8]
0x101cd0602  cmp     [rsp+7E8h+var_2A0], 0
0x101cd060b  jnz     short loc_101CD0611
0x101cd060d  test    al, 1
0x101cd060f  jz      short loc_101CD0651
0x101cd0611  test    al, 1
0x101cd0613  jnz     short loc_101CD0642
0x101cd0615  lea     rcx, [rsp+7E8h+var_2A0]; this
0x101cd061d  call    ?Unlatch@PageRef@@QEAAXXZ; PageRef::Unlatch(void)
0x101cd0622  mov     rcx, qword ptr [rsp+7E8h+var_288]
0x101cd062a  test    rcx, rcx
0x101cd062d  jz      short loc_101CD0642
0x101cd062f  mov     edx, 6FAh
0x101cd0634  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x101cd063a  mov     qword ptr [rsp+7E8h+var_288], rbx
0x101cd0642  xor     edx, edx; int
0x101cd0644  lea     rcx, [rsp+7E8h+var_2A8]; this
0x101cd064c  call    ?Release@BootPagePtr@@QEAAXH@Z; BootPagePtr::Release(int)
0x101cd0651  mov     rcx, qword ptr [rsp+7E8h+var_288]
0x101cd0659  test    rcx, rcx
0x101cd065c  jz      short loc_101CD0671
0x101cd065e  mov     edx, 6FAh
0x101cd0663  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x101cd0669  mov     qword ptr [rsp+7E8h+var_288], rbx
0x101cd0671  lea     rcx, [rsp+7E8h+var_2A0]; this
0x101cd0679  call    ??1PageRef@@QEAA@XZ; PageRef::~PageRef(void)
0x101cd067e  nop
0x101cd067f  jmp     loc_101CD309E
0x101cd0684  mov     rax, [r14+6A0h]
0x101cd068b  mov     ecx, 2
0x101cd0690  cmp     cx, [rax+74h]
0x101cd0694  ja      short loc_101CD06B1
0x101cd0696  mov     rax, [rax+50h]
0x101cd069a  mov     rcx, [rax+8]
0x101cd069e  mov     qword ptr [rsp+7E8h+var_728], rcx
0x101cd06a6  test    rcx, rcx
0x101cd06a9  jz      short loc_101CD06B1
0x101cd06ab  test    byte ptr [rcx+64h], 4
0x101cd06af  jz      short loc_101CD06B9
0x101cd06b1  mov     qword ptr [rsp+7E8h+var_728], rbx
0x101cd06b9  lea     rsi, [r14+2073h]
0x101cd06c0  mov     [rsp+7E8h+var_598], rsi
0x101cd06c8  movzx   eax, byte ptr [rsi]
0x101cd06cb  mov     [rsp+7E8h+var_590], al
0x101cd06d2  mov     byte ptr [rsi], 1
0x101cd06d5  mov     rax, [r15+8450h]
0x101cd06dc  test    rax, rax
0x101cd06df  jz      short loc_101CD06F6
0x101cd06e1  mov     dword ptr [rax+170h], 6
0x101cd06eb  mov     rax, [r15+5F80h]
0x101cd06f2  mov     byte ptr [rax+1Ch], 1
0x101cd06f6  mov     rdx, gs:58h
0x101cd06ff  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101cd0706  mov     ecx, [rax]
0x101cd0708  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101cd070f  mov     eax, [rax]
0x101cd0711  add     rax, [rdx+rcx*8]
0x101cd0715  mov     rax, [rax+8]
0x101cd0719  mov     rcx, [rax+60h]
0x101cd071d  mov     eax, [rcx+5ACh]
0x101cd0723  mov     [rsp+7E8h+var_758], eax
0x101cd072a  mov     rdx, gs:58h
0x101cd0733  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101cd073a  mov     ecx, [rax]
0x101cd073c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101cd0743  mov     eax, [rax]
0x101cd0745  add     rax, [rdx+rcx*8]
0x101cd0749  mov     rax, [rax+8]
0x101cd074d  mov     r12, [rax+60h]
0x101cd0751  add     r12, 499h
0x101cd0758  mov     [rsp+7E8h+var_5A8], r12
0x101cd0760  movzx   eax, byte ptr [r12]
0x101cd0765  mov     [rsp+7E8h+var_5A0], al
0x101cd076c  mov     byte ptr [r12], 1
0x101cd0771  mov     rax, [r15]
0x101cd0774  mov     rcx, [rax+6B0h]
0x101cd077b  movzx   r8d, word ptr [rcx+28h]
0x101cd0780  mov     rdx, gs:58h
0x101cd0789  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101cd0790  mov     ecx, [rax]
0x101cd0792  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101cd0799  mov     eax, [rax]
0x101cd079b  add     rax, [rdx+rcx*8]
0x101cd079f  mov     rax, [rax+8]
0x101cd07a3  mov     rcx, [rax+60h]
0x101cd07a7  mov     [rcx+5ACh], r8d
0x101cd07ae  mov     rcx, [r15]
0x101cd07b1  lea     rax, ??_7IDbCopyRestoreCallback@@6B@; const IDbCopyRestoreCallback::`vftable'
0x101cd07b8  mov     [rsp+7E8h+var_238], rax
0x101cd07c0  lea     rax, ??_7TxLogDataReadAhead@@6B@; const TxLogDataReadAhead::`vftable'
0x101cd07c7  mov     [rsp+7E8h+var_238], rax
0x101cd07cf  mov     [rsp+7E8h+var_230], rcx
0x101cd07d7  mov     eax, cs:?NullPageId@@3VPageId@@B; PageId const NullPageId
0x101cd07dd  mov     [rsp+7E8h+var_228], eax
0x101cd07e4  movzx   eax, cs:word_1031997E8
0x101cd07eb  mov     [rsp+7E8h+var_224], ax
0x101cd07f3  mov     [rsp+7E8h+var_222], bx
0x101cd07fb  test    rcx, rcx
0x101cd07fe  jnz     short loc_101CD0823
0x101cd0800  mov     [rsp+7E8h+var_7C8], rbx
0x101cd0805  mov     r9d, 6106h
0x101cd080b  lea     r8, aRecoveryCpp; "recovery.cpp"
0x101cd0812  lea     rdx, aRecoveryunitNu; "recoveryUnit != NULL"
0x101cd0819  mov     ecx, r10d
0x101cd081c  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101cd0822  nop
0x101cd0823  lea     rax, ??_7ForwardLogDataReadAhead@@6B@; const ForwardLogDataReadAhead::`vftable'
0x101cd082a  mov     [rsp+7E8h+var_238], rax
0x101cd0832  mov     qword ptr [rsp+7E8h+var_778], rbx
0x101cd0837  movsd   xmm0, qword ptr [rsp+7E8h+var_778]
0x101cd083d  movsd   [rsp+7E8h+var_220], xmm0
0x101cd0846  mov     [rsp+7E8h+var_218], ebx
0x101cd084d  mov     rax, [r15]
0x101cd0850  mov     r13, [rax+6B0h]
0x101cd0857  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x101cd085e  cmp     dword ptr [rax], 0
0x101cd0861  jz      short loc_101CD087B
0x101cd0863  lea     rcx, [rsp+7E8h+PerformanceCount]; lpPerformanceCount
0x101cd086b  call    cs:__imp_QueryPerformanceCounter
0x101cd0871  mov     rax, qword ptr [rsp+7E8h+PerformanceCount]
0x101cd0879  jmp     short loc_101CD0883
0x101cd087b  mov     rax, ds:7FFE0008h
0x101cd0883  mov     [rsp+7E8h+var_678], rax
0x101cd088b  mov     [rsp+7E8h+var_670], 1Ah
0x101cd0896  lea     rax, [r13+38h]
0x101cd089a  mov     [rsp+7E8h+var_668], rax
0x101cd08a2  mov     qword ptr [rsp+7E8h+var_778], rbx
0x101cd08a7  mov     r8, [r15]
0x101cd08aa  mov     rdx, r8
0x101cd08ad  mov     rax, [r8+65F0h]
0x101cd08b4  cmp     qword ptr [rax+40h], 0
0x101cd08b9  jz      short loc_101CD08F7
0x101cd08bb  mov     rcx, r14; this
0x101cd08be  call    ?IsRbIoDb@RecoveryUnit@@QEBA_NXZ; RecoveryUnit::IsRbIoDb(void)
0x101cd08c3  test    al, al
0x101cd08c5  jnz     short loc_101CD08F7
0x101cd08c7  mov     [rsp+7E8h+var_7C8], rbx
0x101cd08cc  mov     r9d, 3BF3h
0x101cd08d2  lea     r8, aRecoveryCpp; "recovery.cpp"
0x101cd08d9  lea     rdx, aNullptrGetpruG; "nullptr == GetPru ()->GetHkDbCtxt ()->R"...
0x101cd08e0  mov     r13d, 1
0x101cd08e6  mov     ecx, r13d
0x101cd08e9  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101cd08ef  mov     rdx, [r15]
0x101cd08f2  mov     r8, rdx
0x101cd08f5  jmp     short loc_101CD08FD
0x101cd08f7  mov     r13d, 1
0x101cd08fd  cmp     qword ptr [r15+6038h], 0
0x101cd0905  jz      short loc_101CD0951
0x101cd0907  mov     eax, [r15+24h]
0x101cd090b  shr     eax, 7
0x101cd090e  test    al, 1
0x101cd0910  jnz     short loc_101CD0929
0x101cd0912  mov     rax, [rdx+6B0h]
0x101cd0919  test    byte ptr [rax+3Ch], 1
0x101cd091d  jz      short loc_101CD0951
0x101cd091f  cmp     qword ptr [rax+280h], 0
0x101cd0927  jnz     short loc_101CD0951
0x101cd0929  mov     [rsp+7E8h+var_7C8], rbx
0x101cd092e  mov     r9d, 3BF9h
0x101cd0934  lea     r8, aRecoveryCpp; "recovery.cpp"
0x101cd093b  lea     rdx, a0MExceptioncou; "(0 == m_ExceptionCount) || (!IsForeignL"...
0x101cd0942  mov     ecx, r13d
0x101cd0945  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101cd094b  mov     rdx, [r15]
0x101cd094e  mov     r8, rdx
0x101cd0951  mov     eax, [rdx+678h]
0x101cd0957  cmp     eax, 4
0x101cd095a  jz      short loc_101CD096A
0x101cd095c  cmp     dword ptr [rdx+674h], 4
0x101cd0963  jz      short loc_101CD096A
0x101cd0965  cmp     eax, 3
0x101cd0968  jnz     short loc_101CD09E8
0x101cd096a  movsd   xmm0, qword ptr [r15+5674h]
0x101cd0973  movsd   [rsp+7E8h+var_6A8], xmm0
0x101cd097c  movzx   eax, word ptr [r15+567Ch]
0x101cd0984  mov     [rsp+7E8h+var_6A0], ax
0x101cd098c  mov     dword ptr [rsp+7E8h+var_748], ebx
0x101cd0993  mov     word ptr [rsp+7E8h+var_748+4], bx
0x101cd099b  mov     rcx, [r8+6B0h]
0x101cd09a2  lea     rax, [rcx+3A8h]
0x101cd09a9  lea     rdx, [rsp+7E8h+var_6A8]
0x101cd09b1  mov     [rsp+7E8h+var_7B0], rdx
0x101cd09b6  lea     rdx, [rsp+7E8h+var_748]
0x101cd09be  mov     [rsp+7E8h+var_7B8], rdx
0x101cd09c3  mov     [rsp+7E8h+var_7C0], rax
0x101cd09c8  mov     eax, [rcx+3A0h]
0x101cd09ce  mov     dword ptr [rsp+7E8h+var_7C8], eax
0x101cd09d2  mov     edx, 0Dh
0x101cd09d7  lea     ecx, [rdx+14h]
0x101cd09da  lea     r9d, [rdx-0Ah]
0x101cd09de  lea     r8d, [rdx+8]
0x101cd09e2  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101cd09e8  mov     r8d, [r15+5674h]
0x101cd09ef  mov     dword ptr [rsp+7E8h+var_778], r8d
0x101cd09f4  mov     r9d, [r15+5678h]
0x101cd09fb  mov     dword ptr [rsp+7E8h+var_778+4], r9d
0x101cd0a00  mov     rdx, gs:58h
0x101cd0a09  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101cd0a10  mov     ecx, [rax]
0x101cd0a12  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101cd0a19  mov     eax, [rax]
0x101cd0a1b  add     rax, [rdx+rcx*8]
0x101cd0a1f  mov     rax, [rax+8]
0x101cd0a23  mov     dword ptr [rax+28h], 0FFFFFFFFh
0x101cd0a2a  cmp     edi, r8d
0x101cd0a2d  jb      loc_101CD2F58
0x101cd0a33  mov     r14d, dword ptr [rsp+7E8h+arg_8+4]
0x101cd0a3b  ja      short loc_101CD0A46
0x101cd0a3d  cmp     r14d, r9d
0x101cd0a40  jb      loc_101CD2F58
0x101cd0a46  mov     eax, [r15+24h]
0x101cd0a4a  shr     eax, 7
0x101cd0a4d  test    al, 1
0x101cd0a4f  jnz     loc_101CD0BF9
0x101cd0a55  mov     rax, [r15]
0x101cd0a58  mov     rcx, [rax+6C8h]
0x101cd0a5f  mov     rax, [rcx]
0x101cd0a62  lea     rdx, [rsp+7E8h+var_268]
0x101cd0a6a  call    qword ptr [rax+28h]
0x101cd0a6d  mov     r8b, 1
0x101cd0a70  lea     rdx, [rsp+7E8h+var_574]
0x101cd0a78  mov     rcx, r15
  ... truncated ...
```
