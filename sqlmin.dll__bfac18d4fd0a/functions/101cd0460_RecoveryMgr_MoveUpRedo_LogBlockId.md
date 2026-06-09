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
  __int64 v52; // rdx
  __int64 LastRedoneLSN; // rcx
  __int64 v54; // r14
  __int64 v55; // rdx
  unsigned __int16 v56; // cx
  bool v57; // si
  DirtyPageMgr *v58; // rcx
  DirtyPageMgr *v59; // rcx
  unsigned __int64 v60; // rdx
  __int64 v61; // rdx
  struct PageServerStats **v62; // rdx
  DirtyPageMgr *v63; // rax
  unsigned __int16 v64; // dx
  __int64 v65; // rsi
  struct PageServerStats *v66; // rax
  DirtyPageMgr *v67; // rcx
  DirtyPageMgr *v68; // rcx
  unsigned __int64 v69; // rdx
  DirtyPageMgr *v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // r8
  const struct DBTABLE *v74; // rsi
  struct PageServerStats *v75; // r14
  LSN *v76; // r9
  int v77; // ecx
  struct LogRec *v78; // rsi
  PerProcessGlobals *ClientProcessGlobals; // rax
  struct MemoryClerk **DefaultMemoryClerksForNode; // rsi
  __int64 v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // r8
  __int64 v84; // rax
  DirtyPageMgr *v85; // rcx
  DirtyPageMgr *v86; // rcx
  unsigned __int64 v87; // rdx
  __int64 v88; // rax
  unsigned int v89; // ecx
  DirtyPageMgr *v90; // rax
  ParallelRedoManager *v91; // rcx
  unsigned int (__fastcall ***v92)(_QWORD, struct LogRec *, LSN *, _QWORD); // rcx
  int v93; // edi
  __int64 v94; // rsi
  int v95; // esi
  __int64 v96; // r14
  DirtyPageMgr *v97; // r8
  DirtyPageMgr *v98; // r8
  LSN v99; // rsi
  DirtyPageMgr *v100; // r8
  DirtyPageMgr *v101; // r8
  DirtyPageMgr *v102; // rcx
  DirtyPageMgr *v103; // rcx
  unsigned __int64 v104; // rdx
  const struct LogScanStats *v105; // rax
  __int64 v106; // rax
  __int64 v107; // r11
  unsigned int (__fastcall ***v108)(_QWORD, struct LogRec *, LSN *, _QWORD); // rcx
  __int64 v109; // rax
  struct CSessionTraceFlags *v110; // rcx
  int v111; // edi
  __int64 v112; // rsi
  int v113; // eax
  char v114; // cl
  int v115; // esi
  __int64 v116; // r14
  unsigned __int16 v117; // dx
  LONG HighPart; // ecx
  __int64 v119; // rax
  struct CSessionTraceFlags *v120; // rcx
  char v121; // al
  RecoveryUnit *v122; // r9
  __int64 v123; // rdx
  struct CSessionTraceFlags *v124; // rcx
  int v125; // eax
  bool v126; // al
  __int64 v127; // rax
  __int64 LogOpString; // rax
  DirtyPageMgr *v129; // rax
  DirtyPageMgr *v130; // rcx
  unsigned __int64 v131; // rcx
  unsigned __int64 v132; // rdx
  DirtyPageMgr *v133; // rax
  DirtyPageMgr *v134; // rcx
  DirtyPageMgr *v135; // rcx
  unsigned __int64 v136; // rdx
  unsigned int v137; // eax
  const struct LSN *v138; // rax
  __int64 v139; // rax
  struct CSessionTraceFlags *v140; // rcx
  ParallelRedoManager *v141; // rcx
  __int64 v142; // rax
  __int64 v143; // r9
  DirtyPageMgr *v144; // rcx
  LARGE_INTEGER v145; // rcx
  unsigned __int64 v146; // rdx
  const struct LogScanStats *v147; // rax
  DirtyPageMgr *v148; // rdi
  DirtyPageMgr *v149; // r8
  DirtyPageMgr *v150; // r8
  __int64 v151; // rax
  __int64 v152; // r11
  DirtyPageMgr *v153; // rax
  signed __int64 v154; // rax
  __int64 v155; // rcx
  __int64 v156; // rdi
  struct Worker *v157; // rcx
  DirtyPageMgr *v158; // rax
  signed __int64 v159; // rax
  DirtyPageMgr *v160; // rax
  signed __int64 v161; // rax
  int v162; // esi
  _QWORD *v163; // rbx
  __int64 v164; // rdi
  _QWORD *v165; // r14
  int v166; // eax
  int v167; // edx
  __int64 v168; // rcx
  __int64 v170; // rax
  struct CSessionTraceFlags *v171; // rcx
  int v172; // eax
  struct LogRec *v173; // rdi
  BOOL v176; // ecx
  __int64 *v177; // rax
  unsigned __int16 v178; // ax
  __int64 v179; // r8
  __int64 v180; // rax
  int *v182; // rcx
  __int64 v183; // rcx
  struct LBH *v184; // [rsp+20h] [rbp-7C8h]
  struct LBH *v185; // [rsp+20h] [rbp-7C8h]
  struct LBH *v186; // [rsp+20h] [rbp-7C8h]
  struct Worker *v187; // [rsp+28h] [rbp-7C0h]
  DirtyPageMgr *v188; // [rsp+40h] [rbp-7A8h]
  char v189; // [rsp+48h] [rbp-7A0h]
  char v190; // [rsp+49h] [rbp-79Fh]
  char v191; // [rsp+4Bh] [rbp-79Dh]
  struct LogRec *v192; // [rsp+50h] [rbp-798h]
  DirtyPageMgr *v193; // [rsp+60h] [rbp-788h]
  DirtyPageMgr *v194; // [rsp+60h] [rbp-788h]
  DirtyPageMgr *v195; // [rsp+60h] [rbp-788h]
  DirtyPageMgr *v196; // [rsp+60h] [rbp-788h]
  unsigned int v197; // [rsp+68h] [rbp-780h] BYREF
  LSN v198; // [rsp+70h] [rbp-778h]
  __int64 v199; // [rsp+80h] [rbp-768h]
  unsigned __int16 v200; // [rsp+88h] [rbp-760h]
  int v201; // [rsp+90h] [rbp-758h]
  struct LBH *v202[2]; // [rsp+A0h] [rbp-748h] BYREF
  DirtyPageMgr *v203; // [rsp+B0h] [rbp-738h]
  LARGE_INTEGER v204; // [rsp+C0h] [rbp-728h] BYREF
  LARGE_INTEGER v205; // [rsp+D0h] [rbp-718h] BYREF
  void **v206; // [rsp+D8h] [rbp-710h] BYREF
  __int64 v207; // [rsp+E0h] [rbp-708h]
  int v208; // [rsp+E8h] [rbp-700h]
  __int64 v209; // [rsp+F0h] [rbp-6F8h]
  char v210; // [rsp+F8h] [rbp-6F0h]
  unsigned int v211; // [rsp+100h] [rbp-6E8h] BYREF
  LARGE_INTEGER v212; // [rsp+108h] [rbp-6E0h] BYREF
  __int64 v213; // [rsp+110h] [rbp-6D8h]
  DirtyPageMgr *v214; // [rsp+118h] [rbp-6D0h]
  LSN v215; // [rsp+120h] [rbp-6C8h]
  _QWORD *v216; // [rsp+128h] [rbp-6C0h] BYREF
  unsigned __int64 v217; // [rsp+130h] [rbp-6B8h] BYREF
  DirtyPageMgr *v218; // [rsp+138h] [rbp-6B0h]
  __int64 v219; // [rsp+140h] [rbp-6A8h] BYREF
  __int16 v220; // [rsp+148h] [rbp-6A0h]
  __int64 v221; // [rsp+150h] [rbp-698h] BYREF
  __int16 v222; // [rsp+158h] [rbp-690h]
  __int64 v223; // [rsp+160h] [rbp-688h] BYREF
  __int16 v224; // [rsp+168h] [rbp-680h]
  DirtyPageMgr *v225; // [rsp+170h] [rbp-678h]
  int v226; // [rsp+178h] [rbp-670h]
  __int64 v227; // [rsp+180h] [rbp-668h]
  __int64 v228; // [rsp+188h] [rbp-660h] BYREF
  int v229; // [rsp+190h] [rbp-658h]
  __int64 v230; // [rsp+198h] [rbp-650h] BYREF
  int v231; // [rsp+1A0h] [rbp-648h]
  int v232; // [rsp+1B0h] [rbp-638h] BYREF
  __int16 v233; // [rsp+1B4h] [rbp-634h]
  int v234; // [rsp+1C0h] [rbp-628h] BYREF
  __int16 v235; // [rsp+1C4h] [rbp-624h]
  int v236; // [rsp+1C8h] [rbp-620h] BYREF
  __int16 v237; // [rsp+1CCh] [rbp-61Ch]
  __int64 v238; // [rsp+1D0h] [rbp-618h] BYREF
  DirtyPageMgr *v239; // [rsp+1D8h] [rbp-610h]
  LARGE_INTEGER v240; // [rsp+1E0h] [rbp-608h] BYREF
  LARGE_INTEGER v241; // [rsp+1E8h] [rbp-600h] BYREF
  int v242; // [rsp+1F0h] [rbp-5F8h]
  unsigned int v243; // [rsp+1F4h] [rbp-5F4h] BYREF
  LARGE_INTEGER v244; // [rsp+1F8h] [rbp-5F0h] BYREF
  unsigned int v245; // [rsp+200h] [rbp-5E8h] BYREF
  int v246; // [rsp+208h] [rbp-5E0h]
  DirtyPageMgr *v247; // [rsp+210h] [rbp-5D8h]
  int v248; // [rsp+218h] [rbp-5D0h]
  LARGE_INTEGER PerformanceCount; // [rsp+220h] [rbp-5C8h] BYREF
  LARGE_INTEGER v250; // [rsp+228h] [rbp-5C0h] BYREF
  int v251; // [rsp+230h] [rbp-5B8h] BYREF
  __int16 v252; // [rsp+234h] [rbp-5B4h]
  _BYTE *v253; // [rsp+240h] [rbp-5A8h]
  char v254; // [rsp+248h] [rbp-5A0h]
  _BYTE *v255; // [rsp+250h] [rbp-598h]
  char v256; // [rsp+258h] [rbp-590h]
  int v257; // [rsp+260h] [rbp-588h] BYREF
  __int16 v258; // [rsp+264h] [rbp-584h]
  LSN v259; // [rsp+268h] [rbp-580h] BYREF
  unsigned __int16 v260; // [rsp+270h] [rbp-578h]
  __int16 v261; // [rsp+272h] [rbp-576h]
  __int64 v262; // [rsp+274h] [rbp-574h] BYREF
  __int16 v263; // [rsp+27Ch] [rbp-56Ch]
  __int16 v264; // [rsp+27Eh] [rbp-56Ah]
  _DWORD v265[2]; // [rsp+280h] [rbp-568h] BYREF
  __int16 v266; // [rsp+288h] [rbp-560h]
  __int64 v267; // [rsp+290h] [rbp-558h] BYREF
  __int16 v268; // [rsp+298h] [rbp-550h]
  __int16 v269; // [rsp+29Ah] [rbp-54Eh]
  __int64 v270; // [rsp+2A0h] [rbp-548h] BYREF
  __int16 v271; // [rsp+2A8h] [rbp-540h]
  __int64 v272; // [rsp+2B0h] [rbp-538h] BYREF
  __int16 v273; // [rsp+2B8h] [rbp-530h]
  __int64 v274; // [rsp+2C0h] [rbp-528h] BYREF
  __int16 v275; // [rsp+2C8h] [rbp-520h]
  __int128 v276; // [rsp+2D0h] [rbp-518h] BYREF
  int v277; // [rsp+2E0h] [rbp-508h]
  __int64 v278; // [rsp+2E8h] [rbp-500h] BYREF
  __int16 v279; // [rsp+2F0h] [rbp-4F8h]
  LARGE_INTEGER v280; // [rsp+2F8h] [rbp-4F0h] BYREF
  LARGE_INTEGER v281; // [rsp+300h] [rbp-4E8h] BYREF
  DirtyPageMgr *v282; // [rsp+308h] [rbp-4E0h]
  unsigned __int64 v283; // [rsp+310h] [rbp-4D8h]
  LARGE_INTEGER v284; // [rsp+318h] [rbp-4D0h] BYREF
  LARGE_INTEGER v285; // [rsp+320h] [rbp-4C8h] BYREF
  DirtyPageMgr *v286; // [rsp+328h] [rbp-4C0h]
  LARGE_INTEGER v287; // [rsp+330h] [rbp-4B8h] BYREF
  LARGE_INTEGER v288; // [rsp+338h] [rbp-4B0h] BYREF
  DirtyPageMgr *v289; // [rsp+340h] [rbp-4A8h]
  int v290; // [rsp+348h] [rbp-4A0h]
  LARGE_INTEGER v291; // [rsp+350h] [rbp-498h] BYREF
  LARGE_INTEGER v292; // [rsp+358h] [rbp-490h]
  LARGE_INTEGER v293; // [rsp+360h] [rbp-488h] BYREF
  LARGE_INTEGER v294; // [rsp+368h] [rbp-480h] BYREF
  DirtyPageMgr *v295; // [rsp+370h] [rbp-478h]
  LARGE_INTEGER v296; // [rsp+378h] [rbp-470h] BYREF
  LARGE_INTEGER v297; // [rsp+380h] [rbp-468h]
  DirtyPageMgr *v298; // [rsp+388h] [rbp-460h]
  unsigned __int64 v299; // [rsp+390h] [rbp-458h] BYREF
  LARGE_INTEGER v300; // [rsp+398h] [rbp-450h] BYREF
  DirtyPageMgr *v301; // [rsp+3A0h] [rbp-448h]
  LARGE_INTEGER v302; // [rsp+3A8h] [rbp-440h] BYREF
  LARGE_INTEGER v303; // [rsp+3B0h] [rbp-438h] BYREF
  LARGE_INTEGER v304; // [rsp+3B8h] [rbp-430h] BYREF
  DirtyPageMgr *v305; // [rsp+3C0h] [rbp-428h]
  LARGE_INTEGER v306; // [rsp+3C8h] [rbp-420h] BYREF
  LSN *v307; // [rsp+3D0h] [rbp-418h]
  LARGE_INTEGER v308; // [rsp+3D8h] [rbp-410h] BYREF
  DirtyPageMgr *v309; // [rsp+3E0h] [rbp-408h]
  LARGE_INTEGER v310; // [rsp+3E8h] [rbp-400h] BYREF
  LARGE_INTEGER v311; // [rsp+3F0h] [rbp-3F8h] BYREF
  DirtyPageMgr *v312; // [rsp+3F8h] [rbp-3F0h]
  LARGE_INTEGER v313; // [rsp+400h] [rbp-3E8h] BYREF
  DirtyPageMgr *v314; // [rsp+408h] [rbp-3E0h]
  LARGE_INTEGER v315; // [rsp+410h] [rbp-3D8h] BYREF
  DirtyPageMgr *v316; // [rsp+418h] [rbp-3D0h]
  LSN v317; // [rsp+420h] [rbp-3C8h]
  unsigned __int16 v318; // [rsp+428h] [rbp-3C0h]
  _BYTE v319[16]; // [rsp+430h] [rbp-3B8h] BYREF
  __int128 v320; // [rsp+440h] [rbp-3A8h] BYREF
  int v321; // [rsp+450h] [rbp-398h]
  __int64 v322; // [rsp+460h] [rbp-388h]
  DirtyPageMgr *v323; // [rsp+468h] [rbp-380h]
  DirtyPageMgr *v324; // [rsp+470h] [rbp-378h]
  unsigned __int64 v325; // [rsp+478h] [rbp-370h]
  DirtyPageMgr *v326; // [rsp+480h] [rbp-368h]
  DirtyPageMgr *v327; // [rsp+488h] [rbp-360h]
  DirtyPageMgr *v328; // [rsp+490h] [rbp-358h]
  DirtyPageMgr *v329; // [rsp+498h] [rbp-350h]
  char v330[16]; // [rsp+4A0h] [rbp-348h] BYREF
  __int64 v331; // [rsp+4B0h] [rbp-338h] BYREF
  char v332[12]; // [rsp+4BCh] [rbp-32Ch] BYREF
  char v333[12]; // [rsp+4C8h] [rbp-320h] BYREF
  char v334[12]; // [rsp+4D4h] [rbp-314h] BYREF
  _BYTE v335[40]; // [rsp+4E0h] [rbp-308h] BYREF
  LSN v336; // [rsp+508h] [rbp-2E0h] BYREF
  unsigned __int16 v337; // [rsp+510h] [rbp-2D8h]
  __int64 v338; // [rsp+518h] [rbp-2D0h] BYREF
  unsigned __int16 v339; // [rsp+520h] [rbp-2C8h]
  LSN v340; // [rsp+528h] [rbp-2C0h] BYREF
  __int16 v341; // [rsp+530h] [rbp-2B8h]
  int v342; // [rsp+540h] [rbp-2A8h] BYREF
  __int64 v343; // [rsp+548h] [rbp-2A0h] BYREF
  char v344; // [rsp+550h] [rbp-298h]
  int v345; // [rsp+554h] [rbp-294h]
  __int128 v346; // [rsp+560h] [rbp-288h]
  __int64 v347; // [rsp+570h] [rbp-278h]
  int v348; // [rsp+578h] [rbp-270h]
  __int64 v349; // [rsp+580h] [rbp-268h] BYREF
  int v350; // [rsp+588h] [rbp-260h]
  _DWORD v351[4]; // [rsp+590h] [rbp-258h] BYREF
  _DWORD v352[2]; // [rsp+5A0h] [rbp-248h] BYREF
  __int16 v353; // [rsp+5A8h] [rbp-240h]
  void **v354; // [rsp+5B0h] [rbp-238h]
  __int64 v355; // [rsp+5B8h] [rbp-230h]
  int v356; // [rsp+5C0h] [rbp-228h]
  __int16 v357; // [rsp+5C4h] [rbp-224h]
  __int16 v358; // [rsp+5C6h] [rbp-222h]
  __int64 v359; // [rsp+5C8h] [rbp-220h]
  int v360; // [rsp+5D0h] [rbp-218h]
  _BYTE v361[12]; // [rsp+5D8h] [rbp-210h] BYREF
  char v362[12]; // [rsp+5E4h] [rbp-204h] BYREF
  char v363[12]; // [rsp+5F0h] [rbp-1F8h] BYREF
  char v364[20]; // [rsp+5FCh] [rbp-1ECh] BYREF
  wchar_t v365[48]; // [rsp+610h] [rbp-1D8h] BYREF
  wchar_t v366[48]; // [rsp+670h] [rbp-178h] BYREF
  wchar_t v367[56]; // [rsp+6D0h] [rbp-118h] BYREF
  wchar_t v368[56]; // [rsp+740h] [rbp-A8h] BYREF
  unsigned int v369; // [rsp+7FCh] [rbp+14h]

  v369 = HIDWORD(a2);
  v322 = -2;
  v2 = a2;
  v216 = a1;
  v207 = 0;
  v208 = 1;
  v209 = 0;
  v210 = 0;
  v206 = &SLogIterForward::`vftable';
  v190 = 0;
  v189 = 0;
  v342 = 0;
  v343 = 0;
  v344 = 0;
  v345 = 0;
  v347 = 0;
  v348 = 0;
  v346 = 0;
  v349 = 0;
  v350 = 0;
  v4 = *a1;
  if ( (*(_BYTE *)(*a1 + 7376LL) & 0x20) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, LSN *))(**(_QWORD **)(v4 + 1736) + 368LL))(*(_QWORD *)(v4 + 1736), &v340);
    *(_QWORD *)((char *)a1 + 22132) = v340.QuadPart;
    *((_WORD *)a1 + 11070) = v341;
    RecoveryMgr::SetLastRedoneLSN((RecoveryMgr *)a1, (const struct LSN *)((char *)a1 + 22132));
    if ( (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*a1 + 1736LL) + 656LL))(*(_QWORD *)(*a1 + 1736LL)) )
    {
      v351[2] = 0;
      v351[0] = v2;
      v351[1] = v369;
      v5 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*a1 + 1736LL) + 656LL))(*(_QWORD *)(*a1 + 1736LL));
      LogPoolMgr::OverrideCacheHoldup(v5, 9, v351);
    }
    if ( v343 || (v342 & 1) != 0 )
    {
      if ( (v342 & 1) == 0 )
      {
        PageRef::Unlatch((PageRef *)&v343);
        if ( (_QWORD)v346 )
        {
          operator delete((void *)v346, 0x6FAu);
          *(_QWORD *)&v346 = 0;
        }
      }
      BootPagePtr::Release((BootPagePtr *)&v342, 0);
    }
    if ( (_QWORD)v346 )
    {
      operator delete((void *)v346, 0x6FAu);
      *(_QWORD *)&v346 = 0;
    }
    PageRef::~PageRef((PageRef *)&v343);
    goto LABEL_487;
  }
  v6 = *(_QWORD *)(v4 + 1696);
  if ( *(_WORD *)(v6 + 116) < 2u
    || (v7 = *(LARGE_INTEGER *)(*(_QWORD *)(v6 + 80) + 8LL), v204 = v7, !v7.QuadPart)
    || (*(_BYTE *)(v7.QuadPart + 100) & 4) != 0 )
  {
    v204.QuadPart = 0;
  }
  v8 = (_BYTE *)(v4 + 8307);
  v255 = (_BYTE *)(v4 + 8307);
  v256 = *(_BYTE *)(v4 + 8307);
  *(_BYTE *)(v4 + 8307) = 1;
  v9 = a1[4234];
  if ( v9 )
  {
    *(_DWORD *)(v9 + 368) = 6;
    *(_BYTE *)(a1[3056] + 28LL) = 1;
  }
  v201 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
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
  v253 = v10;
  v254 = *v10;
  *v10 = 1;
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                    + SystemThread_TlsOffset
                                    + 8LL)
                        + 96LL)
            + 1452LL) = *(unsigned __int16 *)(*(_QWORD *)(*a1 + 1712LL) + 40LL);
  v11 = *a1;
  v354 = &TxLogDataReadAhead::`vftable';
  v355 = v11;
  v356 = NullPageId;
  v357 = word_1031997E8;
  v358 = 0;
  if ( !v11 )
    utassert_fail(1u, "recoveryUnit != NULL", "recovery.cpp", 24838, 0);
  v354 = &ForwardLogDataReadAhead::`vftable';
  v198.QuadPart = 0;
  v359 = 0;
  v360 = 0;
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
  v225 = QuadPart;
  v226 = 26;
  v227 = v12 + 56;
  v198.QuadPart = 0;
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
    v219 = *(_QWORD *)((char *)a1 + 22132);
    v220 = *((_WORD *)a1 + 11070);
    LODWORD(v202[0]) = 0;
    WORD2(v202[0]) = 0;
    v18 = *(_QWORD *)(v14 + 1712);
    LODWORD(v185) = *(_DWORD *)(v18 + 928);
    ex_raise(33, 13, 21, 3, v185, v18 + 936, v202, &v219);
  }
  v198.LowPart = *((_DWORD *)a1 + 5533);
  LowPart = v198.LowPart;
  v20 = *((_DWORD *)a1 + 5534);
  v198.HighPart = v20;
  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset
                        + 8LL)
            + 40LL) = -1;
  if ( v2 < LowPart || v2 <= LowPart && v369 < v20 )
  {
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v244);
      v160 = (DirtyPageMgr *)v244.QuadPart;
    }
    else
    {
      v160 = MEMORY[0x7FFE0008];
    }
    if ( v160 < v225 )
      v161 = 0;
    else
      v161 = v160 - v225;
    *(_QWORD *)(v227 + 312) += v161;
    v354 = &IDbCopyRestoreCallback::`vftable';
    if ( !v254 && *v10 )
      *v10 = 0;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1452LL) = v201;
    if ( !v256 && *v8 )
      *v8 = 0;
    if ( v343 || (v342 & 1) != 0 )
    {
      if ( (v342 & 1) == 0 )
      {
        PageRef::Unlatch((PageRef *)&v343);
        if ( (_QWORD)v346 )
        {
          operator delete((void *)v346, 0x6FAu);
          *(_QWORD *)&v346 = 0;
        }
      }
      BootPagePtr::Release((BootPagePtr *)&v342, 0);
    }
    if ( !(_QWORD)v346 )
      goto LABEL_486;
LABEL_485:
    operator delete((void *)v346, 0x6FAu);
    *(_QWORD *)&v346 = 0;
LABEL_486:
    PageRef::~PageRef((PageRef *)&v343);
LABEL_487:
    v206 = &SLogIterForward::`vftable';
    return;
  }
  if ( (*((_DWORD *)a1 + 9) & 0x80) == 0 )
  {
    (*(void (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(*a1 + 1736LL) + 40LL))(*(_QWORD *)(*a1 + 1736LL), &v349);
    LOBYTE(v21) = 1;
    RedoneLSN = RecoveryMgr::GetRedoneLSN(a1, &v262, v21);
    if ( (unsigned int)v349 <= *(_DWORD *)RedoneLSN )
    {
      if ( (_DWORD)v349 != *(_DWORD *)RedoneLSN
        || (v23 = *(_DWORD *)(RedoneLSN + 4), HIDWORD(v349) <= v23)
        && (HIDWORD(v349) != v23 || (unsigned __int16)v350 <= *(_WORD *)(RedoneLSN + 8)) )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v212);
          v24 = (DirtyPageMgr *)v212.QuadPart;
        }
        else
        {
          v24 = MEMORY[0x7FFE0008];
        }
        if ( v24 < v225 )
          v25 = 0;
        else
          v25 = v24 - v225;
        *(_QWORD *)(v227 + 312) += v25;
        v354 = &IDbCopyRestoreCallback::`vftable';
        if ( !v254 && *v10 )
          *v10 = 0;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset
                                          + 8LL)
                              + 96LL)
                  + 1452LL) = v201;
        if ( !v256 && *v8 )
          *v8 = 0;
        if ( v343 || (v342 & 1) != 0 )
        {
          if ( (v342 & 1) == 0 )
          {
            PageRef::Unlatch((PageRef *)&v343);
            if ( (_QWORD)v346 )
            {
              operator delete((void *)v346, 0x6FAu);
              *(_QWORD *)&v346 = 0;
            }
          }
          BootPagePtr::Release((BootPagePtr *)&v342, 0);
        }
        if ( !(_QWORD)v346 )
          goto LABEL_486;
        goto LABEL_485;
      }
    }
  }
  if ( RecoveryUnit::IsTraceEnabled() )
  {
    if ( v369 != -1 || v2 != -1 )
      RecoveryMgr::GetRedoneLSN(a1, v265, 0);
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
        v369 | ((unsigned __int64)v2 << 32),
        *(unsigned int *)(*(_QWORD *)(v29 + 608) + 3688LL));
    }
  }
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&v240);
    v30 = (DirtyPageMgr *)v240.QuadPart;
  }
  else
  {
    v30 = MEMORY[0x7FFE0008];
  }
  v203 = v30;
  if ( (*((_DWORD *)a1 + 9) & 0x80) != 0 )
  {
    LogIterImpl<LogMgr>::InitForeign((unsigned int)&v206, 0, (_DWORD)a1, a1[3080], 1);
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
    v207 = *(_QWORD *)(v31 + 1736);
    v209 = (*(__int64 (__fastcall **)(struct IServerConfiguration *, __int64, __int64, _QWORD))(*(_QWORD *)v207 + 128LL))(
             v33,
             1,
             v207,
             a1[2780]);
    (*(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD, const wchar_t *, int, int))(*(_QWORD *)v209 + 8LL))(
      v209,
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
      (ExcHandler *)v335,
      0,
      0,
      0,
      (int (*)(int, int, int, int, char *))RecoveryExceptionHandler,
      0);
    v199 = 0;
    v200 = 0;
    v212.QuadPart = 0;
    RecoveryMgr::GetRedoneLSN(a1, v361, 0);
    v217 = 0;
    v240.QuadPart = 0;
    BootPagePtr::Init(&v342, 0, *a1, 0);
    BootPagePtr::GetAccess(&v342, 2);
    if ( (v342 & 1) != 0 )
      v38 = v346;
    else
      v38 = *(_QWORD *)v343 + *(unsigned __int16 *)(*(_QWORD *)v343 + 8190LL);
    v199 = *(_QWORD *)(v38 + 588);
    v200 = *(_WORD *)(v38 + 596);
    BootPagePtr::ReleaseAccess((BootPagePtr *)&v342, 0);
    BootPagePtr::Release((BootPagePtr *)&v342, 0);
    if ( (*((_DWORD *)a1 + 9) & 0x80) != 0 )
    {
      AlignedLSN128::GetLSN((struct AlignedLSN128 *)(a1[15] + 1584LL), (struct LSN *)&v274);
      v267 = v274;
      v268 = v275;
      v269 = 0;
      AlignedLSN::AggMax((AlignedLSN *)v361, (const struct AlignedLSN *)&v267);
    }
    v39 = v209;
    (*(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v209 + 128LL))(v209, v361, 2);
    v215 = *(LSN *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 152LL))(v39) + 8);
    if ( dword_103172528
      || (v40 = *(_QWORD *)(*a1 + 1712LL), (*(_BYTE *)(v40 + 60) & 1) != 0) && !*(_QWORD *)(v40 + 640) )
    {
      RecoveryMgr::MayDeferErrorsForPru((RecoveryMgr *)a1, 0, 0);
    }
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
      QueryPerformanceCounter(&v241);
    else
      v241.QuadPart = (LONGLONG)MEMORY[0x7FFE0008];
    v292 = v241;
    v239 = (DirtyPageMgr *)v241.QuadPart;
    v213 = 0;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
      QueryPerformanceCounter(&v250);
    else
      v250.QuadPart = (LONGLONG)MEMORY[0x7FFE0008];
    v188 = (DirtyPageMgr *)v250.QuadPart;
    while ( 1 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v293);
        v41 = (DirtyPageMgr *)v293.QuadPart;
      }
      else
      {
        v41 = MEMORY[0x7FFE0008];
        v188 = MEMORY[0x7FFE0008];
      }
      v218 = v41;
      v192 = (struct LogRec *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v209 + 120LL))(v209);
      if ( !v192 && (*((_DWORD *)a1 + 9) & 0x80) == 0 )
      {
LABEL_394:
        v352[0] = 0;
        v352[1] = 0;
        v353 = 0;
        v141 = (ParallelRedoManager *)a1[4234];
        if ( v141 )
          ParallelRedoManager::DrainRedoWorkers(v141, L"MoveUpRedo End", (const struct LSN *)v352);
        if ( *((_WORD *)a1 + 11064) != *((_WORD *)a1 + 11070)
          || *((_DWORD *)a1 + 5530) != *((_DWORD *)a1 + 5533)
          || *((_DWORD *)a1 + 5531) != *((_DWORD *)a1 + 5534) )
        {
          utassert_fail(1u, "m_AnalyzeLsn == m_CurRedoLsn", "recovery.cpp", 16082, 0);
        }
        v142 = RecoveryMgr::GetRedoneLSN(a1, v334, 0);
        if ( *((_WORD *)a1 + 11064) != *(_WORD *)(v142 + 8)
          || *((_DWORD *)a1 + 5530) != *(_DWORD *)v142
          || *((_DWORD *)a1 + 5531) != *(_DWORD *)(v142 + 4) )
        {
          v270 = *(_QWORD *)((char *)a1 + 22132);
          v271 = *((_WORD *)a1 + 11070);
          v223 = a1[2765];
          v224 = *((_WORD *)a1 + 11064);
          v143 = *(_QWORD *)(*a1 + 1712LL);
          LODWORD(v186) = *(_DWORD *)(v143 + 928);
          ex_raise(33, 2, 21, 2, v186, v143 + 936, &v223, &v270, v188);
        }
        if ( v190 )
        {
          v214 = (DirtyPageMgr *)a1[2928];
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v291);
            v144 = (DirtyPageMgr *)v291.QuadPart;
          }
          else
          {
            v205.QuadPart = (LONGLONG)MEMORY[0x7FFE0008];
            v144 = MEMORY[0x7FFE0008];
          }
          v247 = v144;
          if ( v144 < v214 )
          {
            v145.QuadPart = 0;
            v205.QuadPart = 0;
          }
          else
          {
            v145.QuadPart = v144 - v214;
            v205 = v145;
          }
          v297 = v145;
          if ( v145.QuadPart == -1
            || (!Base_PublicGlobals::sm_invariantTscAvailable
              ? (v146 = v145.QuadPart / 0x2710uLL)
              : (v146 = (unsigned __int64)(1000 * v145.QuadPart)
                      / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart),
                v146 > 0x493E0) )
          {
            v147 = (const struct LogScanStats *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v209 + 152LL))(v209);
            RecoveryStatus::OutputRedoStats((RecoveryStatus *)(a1 + 2871), v147);
            RecoveryStatus::ResetForRedoStart((RecoveryStatus *)(a1 + 2871));
          }
          v148 = *(DirtyPageMgr **)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v209 + 152LL))(v209) + 8);
          v247 = v148;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v294);
            v149 = (DirtyPageMgr *)v294.QuadPart;
            v295 = (DirtyPageMgr *)v294.QuadPart;
          }
          else
          {
            v214 = MEMORY[0x7FFE0008];
            v149 = MEMORY[0x7FFE0008];
            v295 = MEMORY[0x7FFE0008];
            v148 = v247;
          }
          if ( v149 < v203 )
          {
            v150 = 0;
            v214 = 0;
          }
          else
          {
            v150 = (DirtyPageMgr *)(v149 - v203);
            v214 = v150;
          }
          v297.QuadPart = (LONGLONG)v150;
          RecoveryUnit::NoteRedo(*a1, (char *)v148 - v215.QuadPart);
          if ( a1[2780] )
          {
            v151 = RecoveryMgr::GetRedoneLSN(a1, v362, 0);
            (*(void (__fastcall **)(_QWORD, __int64, __int64))(v152 + 72))(a1[2780], 9, v151);
          }
        }
        CAutoFileOpLock::~CAutoFileOpLock((CAutoFileOpLock *)&v212);
        ExcHandler::~ExcHandler((ExcHandler *)v335);
        goto LABEL_554;
      }
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v296);
        v42 = (DirtyPageMgr *)v296.QuadPart;
      }
      else
      {
        v42 = MEMORY[0x7FFE0008];
      }
      v298 = v42;
      if ( v42 < v218 )
      {
        v43 = 0;
        v188 = 0;
      }
      else
      {
        v43 = (DirtyPageMgr *)(v42 - v218);
        v188 = v43;
      }
      v326 = v43;
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
      v213 += v44;
      if ( !v192 )
      {
        if ( (*((_DWORD *)a1 + 9) & 0x80) == 0 )
          utassert_fail(1u, "IsForeignLogApply ()", "recovery.cpp", 15561, 0);
        v219 = 0;
        v220 = 0;
        NextLSN = LogIterImpl<LogMgr>::GetNextLSN(&v206, v330);
        if ( *(_WORD *)(NextLSN + 8) || *(_DWORD *)NextLSN || *(_DWORD *)(NextLSN + 4) )
        {
          if ( byte_10316EA49 || (byte_10317B107 & 2) != 0 )
          {
            v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v209 + 48LL))(v209);
            if ( *(_WORD *)v46 )
              utassert_fail(1u, "lbh->lbk_version == 0", "recovery.cpp", 15582, 0);
            v238 = *(_QWORD *)(v46 + 48);
          }
          else
          {
            utgettime((struct SQLDATEBASE *)&v238, 1, 0);
            if ( SQLDATE::DateAdd((SQLDATE *)&v238, 8, 30) )
              utassert_fail(1u, "O_SUCCESS == logBlockClosingTime.DateAdd(DPSECOND, 30)", "recovery.cpp", 15597, 0);
          }
          LogIterImpl<LogMgr>::GetNextLSN(&v206, &v221);
          v278 = v221;
          v279 = v222;
          RecoveryMgr::UpdateForeignRedoProgress(a1, &v221, &v278, v238);
          if ( byte_10316E9E6 )
          {
            v299 = RbIoXlogLogBlockIdToLinearBsn((unsigned int)v221, HIDWORD(v221), a1[3080]);
            v47 = *a1;
            PageServerStats = RecoveryUnit::GetPageServerStats((RecoveryUnit *)*a1);
            PageServerUpdateForeignRedoHash(PageServerStats, &v299, *(const struct DBTABLE **)(v47 + 1712));
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
        ForeignRedoLsn = FCB::GetForeignRedoLsn(a1[15], v351);
        RecoveryMgr::ReportRbIoRedoProgress(a1, ForeignRedoLsn, 5);
        if ( byte_10316EB21 || (byte_10317B106 & 0x10) != 0 )
          RecoveryMgr::RestoreForeignStalePages((RecoveryMgr *)a1);
        RecoveryUnit::EvaluateForeignCheckpoint((RecoveryUnit *)*a1);
        CheckForTriggerPermanentFault((struct RecoveryUnit *)*a1);
        if ( (byte_10317B104 & 0x10) != 0 )
          goto LABEL_394;
        goto LABEL_149;
      }
      v54 = v209;
      (*(void (__fastcall **)(__int64, LSN *))(*(_QWORD *)v209 + 56LL))(v209, &v336);
      v202[0] = (struct LBH *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v54 + 48LL))(v54);
      v55 = *(_QWORD *)v202[0];
      if ( **(_WORD **)v202[0] < 6u )
        v198.QuadPart = 0;
      else
        v198 = *(LSN *)(v55 + 48);
      v56 = v337;
      if ( !v337 || (v191 = 1, v337 != *(_WORD *)(v55 + 2)) )
        v191 = 0;
      if ( (*((_DWORD *)a1 + 9) & 0x80) != 0 )
      {
        v217 = RbIoXlogLogBlockIdToLinearBsn(v336.LowPart, (unsigned int)v336.HighPart, a1[3080]);
        v56 = v337;
      }
      if ( v56 != 1 )
        goto LABEL_213;
      v240 = v336;
      if ( v2 >= v336.LowPart && (v2 > v336.LowPart || v369 > v336.HighPart) )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v209 + 112LL))(v209, 0);
      v57 = (*((_DWORD *)a1 + 9) & 0x80) != 0;
      if ( *(_BYTE *)(v204.QuadPart + 91) )
        break;
      if ( (*((_DWORD *)a1 + 9) & 0x80) != 0 )
        goto LABEL_168;
LABEL_213:
      if ( (*((_DWORD *)a1 + 9) & 0x80) != 0 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v306);
          v70 = (DirtyPageMgr *)v306.QuadPart;
        }
        else
        {
          v70 = MEMORY[0x7FFE0008];
          v188 = MEMORY[0x7FFE0008];
        }
        v194 = v70;
        if ( IsLogSelectedForForeignLogApply(v192, (const struct LSN *)&v336, (struct FCB *)a1[15]) )
        {
          if ( byte_10316E9E6 )
          {
            v74 = *(const struct DBTABLE **)(*a1 + 1712LL);
            v75 = RecoveryUnit::GetPageServerStats((RecoveryUnit *)*a1);
            PageServerUpdateForeignRedoHash(v75, &v217, v74);
            v71 = 0;
            v73 = 10;
            v246 = 10;
            v76 = &v336;
            v307 = &v336;
            v290 = 0;
            v77 = 0;
            v248 = 0;
            while ( !v77 )
            {
              v71 = _mm_crc32_u64((unsigned int)v71, v336.QuadPart);
              v73 = (unsigned int)(v73 - 8);
              v246 = v73;
              v307 = ++v76;
              v77 = 1;
              v248 = 1;
            }
            v72 = 0;
            v242 = 0;
            while ( (unsigned int)v72 < (unsigned int)v73 )
            {
              v71 = _mm_crc32_u8(v71, *((_BYTE *)&v76->LowPart + (unsigned int)v72));
              v72 = (unsigned int)(v72 + 1);
              v242 = v72;
            }
            *((_DWORD *)v75 + 110) ^= v71;
          }
          if ( *((_BYTE *)v192 + 22) < 0x7Fu )
          {
            v78 = (struct LogRec *)a1[2778];
            if ( !v78 )
            {
              ClientProcessGlobals = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals(v72, v71, v73);
              DefaultMemoryClerksForNode = PerProcessGlobals::GetDefaultMemoryClerksForNode(ClientProcessGlobals, 0);
              SOS_OS::GetClientProcessGlobals(v82, v81, v83);
              v84 = (**((__int64 (__fastcall ***)(__int64, __int64, _QWORD))DefaultMemoryClerksForNode[15] + 8))(
                      (__int64)DefaultMemoryClerksForNode[15] + 64,
                      3,
                      0);
              a1[2778] = v84;
              v78 = (struct LogRec *)v84;
              if ( !v84 )
              {
                utassert_fail(1u, "m_LogRecBufferMemory", "recovery.cpp", 12338, 0);
                v78 = (struct LogRec *)a1[2778];
              }
            }
            RecoveryMgr::RemapForeignLogPageId((RecoveryMgr *)a1, v192, v78);
            v192 = v78;
          }
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v308);
            v85 = (DirtyPageMgr *)v308.QuadPart;
          }
          else
          {
            v85 = MEMORY[0x7FFE0008];
          }
          v309 = v85;
          if ( v85 < v194 )
          {
            v86 = 0;
            v188 = 0;
          }
          else
          {
            v86 = (DirtyPageMgr *)(v85 - v194);
            v188 = v86;
          }
          v329 = v86;
          if ( v86 == (DirtyPageMgr *)-1LL )
          {
            v87 = -1;
          }
          else if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            v87 = (unsigned __int64)(1000000LL * (_QWORD)v86)
                / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
          }
          else
          {
            v87 = (unsigned __int64)v86 / 0xA;
          }
          RecoveryMgr::UpdateLogReplayExecutionTimeStats(a1, 11, v87);
          goto LABEL_243;
        }
      }
      else
      {
LABEL_243:
        v88 = RecoveryMgr::GetRedoneLSN(a1, v332, 0);
        if ( v336.LowPart > *(_DWORD *)v88
          || v336.LowPart == *(_DWORD *)v88
          && ((v89 = *(_DWORD *)(v88 + 4), v336.HighPart > v89) || v336.HighPart == v89 && v337 > *(_WORD *)(v88 + 8)) )
        {
          if ( *(_BYTE *)(*a1 + 8297LL) )
          {
            v91 = (ParallelRedoManager *)a1[4234];
            if ( v91 )
              ParallelRedoManager::DrainRedoWorkers(v91, L"RedoPaused", (const struct LSN *)&v336);
            goto LABEL_394;
          }
          if ( a1[2930] )
          {
            v230 = *a1 + 8360LL;
            v231 = 0;
            TAutoMutex<SOS_Mutex,1>::GetAccess(&v230, 4195132);
            v92 = (unsigned int (__fastcall ***)(_QWORD, struct LogRec *, LSN *, _QWORD))a1[2930];
            if ( v92 && (**v92)(v92, v192, &v336, 0) )
            {
              *((_BYTE *)a1 + 22233) = 1;
              v93 = v231;
              v94 = v230;
              while ( v93 )
              {
                *(_QWORD *)(v94 + 48) = 0;
                EventAutoInternal<SuspendQueueSLock>::Signal(v94, 0);
                v231 = --v93;
              }
              goto LABEL_394;
            }
            v95 = v231;
            v96 = v230;
            while ( v95 )
            {
              *(_QWORD *)(v96 + 48) = 0;
              EventAutoInternal<SuspendQueueSLock>::Signal(v96, 0);
              v231 = --v95;
            }
          }
          v198 = v336;
          if ( v2 < v336.LowPart || v2 <= v336.LowPart && v369 < v336.HighPart )
          {
            v215 = *(LSN *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v209 + 152LL))(v209) + 8);
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
              QueryPerformanceCounter(&v205);
            else
              v205.QuadPart = (LONGLONG)MEMORY[0x7FFE0008];
            v203 = (DirtyPageMgr *)v205.QuadPart;
            goto LABEL_394;
          }
          if ( v337 == 1 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v311);
              v97 = (DirtyPageMgr *)v311.QuadPart;
            }
            else
            {
              v97 = MEMORY[0x7FFE0008];
            }
            v312 = v97;
            RecoveryStatus::NoteLogBlockRead(a1 + 2871, 1);
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v313);
              v98 = (DirtyPageMgr *)v313.QuadPart;
            }
            else
            {
              v98 = MEMORY[0x7FFE0008];
            }
            v314 = v98;
            RecoveryStatus::NoteLogBlockRead(a1 + 2871, 2);
            v99 = *(LSN *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v209 + 152LL))(v209) + 8);
            v198 = v99;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v315);
              v100 = (DirtyPageMgr *)v315.QuadPart;
              v316 = (DirtyPageMgr *)v315.QuadPart;
            }
            else
            {
              v100 = MEMORY[0x7FFE0008];
              v316 = MEMORY[0x7FFE0008];
              v99 = v198;
            }
            if ( v100 < v203 )
              v101 = 0;
            else
              v101 = (DirtyPageMgr *)(v100 - v203);
            v188 = v101;
            RecoveryUnit::NoteRedo(*a1, v99.QuadPart - v215.QuadPart);
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v280);
              v203 = (DirtyPageMgr *)v280.QuadPart;
            }
            else
            {
              v188 = MEMORY[0x7FFE0008];
              v203 = MEMORY[0x7FFE0008];
              v99 = v198;
            }
            v215 = v99;
            if ( v190 )
            {
              v283 = a1[2928];
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v281);
                v102 = (DirtyPageMgr *)v281.QuadPart;
              }
              else
              {
                v102 = MEMORY[0x7FFE0008];
              }
              v282 = v102;
              if ( (unsigned __int64)v102 < v283 )
              {
                v103 = 0;
                v188 = 0;
              }
              else
              {
                v103 = (DirtyPageMgr *)((char *)v102 - v283);
                v188 = v103;
              }
              v327 = v103;
              if ( v103 == (DirtyPageMgr *)-1LL
                || (!Base_PublicGlobals::sm_invariantTscAvailable
                  ? (v104 = (unsigned __int64)v103 / 0x2710)
                  : (v104 = (unsigned __int64)(1000LL * (_QWORD)v103)
                          / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart),
                    v104 > 0x493E0) )
              {
                v105 = (const struct LogScanStats *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v209 + 152LL))(v209);
                RecoveryStatus::OutputRedoStats((RecoveryStatus *)(a1 + 2871), v105);
                RecoveryStatus::ResetForRedoStart((RecoveryStatus *)(a1 + 2871));
                if ( a1[2780] )
                {
                  v106 = RecoveryMgr::GetRedoneLSN(a1, v364, 0);
                  (*(void (__fastcall **)(_QWORD, __int64, __int64))(v107 + 72))(a1[2780], 9, v106);
                }
              }
            }
            if ( (*((_DWORD *)a1 + 9) & 0x80) == 0 )
              RecoveryUnit::EvaluateRecovery((RecoveryUnit *)*a1);
          }
          if ( !*((_WORD *)v192 + 1) )
            utassert_fail(1u, "lp->log_fixedLength > 0", "recovery.cpp", 15907, 0);
          if ( !*((_BYTE *)v192 + 22) )
            utassert_fail(1u, "lp->GetOpCode () != LOP_NULL", "recovery.cpp", 15908, 0);
          if ( a1[2930] )
          {
            v228 = *a1 + 8360LL;
            v229 = 0;
            TAutoMutex<SOS_Mutex,1>::GetAccess(&v228, 4195132);
            v108 = (unsigned int (__fastcall ***)(_QWORD, struct LogRec *, LSN *, _QWORD))a1[2930];
            if ( v108 && (**v108)(v108, v192, &v336, 0) )
            {
              if ( (qword_10317AD29 & 8) != 0
                || (v109 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset)) != 0
                && (v110 = **(struct CSessionTraceFlags ***)(v109 + 56)) != 0
                && CSessionTraceFlags::CheckSessionTraceInternal(v110, 0xD4Bu) )
              {
                PerformanceCount.LowPart = 92;
                v211 = 100;
                GetLsnAsDecimalString((const struct LSN *)&v336, &v211, v367);
                LSN::FormatAsHexString(&v336, v365, (unsigned int *)&PerformanceCount);
                LODWORD(v187) = *((_DWORD *)v192 + 4);
                LODWORD(v186) = *((unsigned __int16 *)v192 + 10);
                traceprint(
                  L"REDO LSN %.*ls (0x%ls), XdesId 0x%04lx:%08lx Before termination LSN reached.\n",
                  (unsigned __int64)v211 >> 1,
                  v367,
                  v365,
                  v186,
                  v187);
              }
              *((_BYTE *)a1 + 22233) = 1;
              v111 = v229;
              v112 = v228;
              while ( v111 )
              {
                *(_QWORD *)(v112 + 48) = 0;
                EventAutoInternal<SuspendQueueSLock>::Signal(v112, 0);
                v229 = --v111;
              }
              goto LABEL_394;
            }
            v113 = (*(__int64 (__fastcall **)(_QWORD, struct LogRec *, LSN *))(*(_QWORD *)a1[2930] + 8LL))(
                     a1[2930],
                     v192,
                     &v336);
            v114 = v189;
            if ( v113 )
              v114 = 1;
            v189 = v114;
            v115 = v229;
            v116 = v228;
            while ( v115 )
            {
              *(_QWORD *)(v116 + 48) = 0;
              EventAutoInternal<SuspendQueueSLock>::Signal(v116, 0);
              v229 = --v115;
            }
          }
          v190 = 1;
          v117 = v337;
          HighPart = v336.HighPart;
          *((_DWORD *)a1 + 5533) = v336.LowPart;
          *((_DWORD *)a1 + 5534) = HighPart;
          *((_WORD *)a1 + 11070) = v117;
          v317 = v336;
          v318 = v337;
          v259 = v336;
          v260 = v337;
          v261 = 0;
          SOS_Atomic<AlignedLSN>::operator=(a1 + 2768, &v259);
          *((_BYTE *)a1 + 22212) = v191;
          v121 = 1;
          if ( (qword_10317AD29 & 0x800000000000000LL) == 0 )
          {
            v119 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset);
            if ( !v119
              || (v120 = **(struct CSessionTraceFlags ***)(v119 + 56)) == 0
              || !CSessionTraceFlags::CheckSessionTraceInternal(v120, 0xD83u) )
            {
              v121 = 0;
            }
          }
          v122 = (RecoveryUnit *)*a1;
          if ( (*(_BYTE *)(*a1 + 7376LL) & 0x40) != 0 )
          {
            if ( byte_10317AE3A < 0
              || (v123 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset,
                  *(_QWORD *)v123)
              && (v124 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v123 + 56LL)) != 0
              && (v125 = CSessionTraceFlags::CheckSessionTraceInternal(v124, 0x15D7u), v122 = (RecoveryUnit *)*a1, v125) )
            {
              RecoveryUnit::PrintTrace(v122, L"TrySwitchToParallelRedo :: Disable Lazy Redo for Auxiliary Replica");
              v122 = (RecoveryUnit *)*a1;
            }
            *((_BYTE *)v122 + 26105) = 0;
          }
          else if ( *((_BYTE *)a1 + 33896) != v121 )
          {
            *((_BYTE *)a1 + 33896) = v121;
            if ( !v121 && !a1[4234] )
            {
              v126 = (byte_10316E943 || (qword_10317AD29 & 0x200000000000000LL) != 0)
                  && (qword_10317AD29 & 0x800000000000000LL) == 0;
              *((_BYTE *)v122 + 26105) = v126;
              RecoveryMgr::StartParallelRedoManager((RecoveryMgr *)a1);
              v127 = a1[4234];
              if ( v127 )
              {
                *(_DWORD *)(v127 + 368) = 6;
                *(_BYTE *)(a1[3056] + 28LL) = 1;
                if ( RecoveryUnit::IsTraceEnabled() )
                {
                  LogOpString = GetLogOpString(*((unsigned __int8 *)v192 + 22));
                  LODWORD(v186) = v337;
                  RecoveryUnit::PrintTrace(
                    (RecoveryUnit *)*a1,
                    L"Switch to parallel redo at lsn [0x%x:0x%x:0x%x]; opCode: %ls",
                    v336.LowPart,
                    (unsigned int)v336.HighPart,
                    v186,
                    LogOpString);
                }
              }
            }
          }
          if ( (*((_DWORD *)a1 + 9) & 0x80) == 0
            && (*((unsigned __int8 *)v192 + 22) == 150 || *((unsigned __int8 *)v192 + 22) == 153) )
          {
            CAutoFileOpLock::Acquire((CAutoFileOpLock *)&v212, *(struct FileMgr **)(*a1 + 1696LL));
          }
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v284);
            v129 = (DirtyPageMgr *)v284.QuadPart;
          }
          else
          {
            v129 = MEMORY[0x7FFE0008];
          }
          v195 = v129;
          RecoveryMgr::AnalyzeLogRecord((RecoveryMgr *)a1, v192, (const struct LSN *)&v336, 1, v202[0]);
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v285);
            v130 = (DirtyPageMgr *)v285.QuadPart;
          }
          else
          {
            v130 = MEMORY[0x7FFE0008];
          }
          v286 = v130;
          if ( v130 < v195 )
            v131 = 0;
          else
            v131 = v130 - v195;
          v325 = v131;
          if ( v131 == -1 )
          {
            v132 = -1;
          }
          else if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            v132 = 1000000 * v131 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
          }
          else
          {
            v132 = v131 / 0xA;
          }
          RecoveryMgr::UpdateLogReplayExecutionTimeStats(a1, 12, v132);
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v287);
            v133 = (DirtyPageMgr *)v287.QuadPart;
          }
          else
          {
            v133 = MEMORY[0x7FFE0008];
          }
          v196 = v133;
          RecoveryMgr::RedoLogRecord((RecoveryMgr *)a1, v192, 1, 0);
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v288);
            v134 = (DirtyPageMgr *)v288.QuadPart;
          }
          else
          {
            v134 = MEMORY[0x7FFE0008];
          }
          v289 = v134;
          if ( v134 < v196 )
          {
            v135 = 0;
            v188 = 0;
          }
          else
          {
            v135 = (DirtyPageMgr *)(v134 - v196);
            v188 = v135;
          }
          v324 = v135;
          if ( v135 == (DirtyPageMgr *)-1LL )
          {
            v136 = -1;
          }
          else if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            v136 = (unsigned __int64)(1000000LL * (_QWORD)v135)
                 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
          }
          else
          {
            v136 = (unsigned __int64)v135 / 0xA;
          }
          RecoveryMgr::UpdateLogReplayExecutionTimeStats(a1, 13, v136);
          CAutoFileOpLock::~CAutoFileOpLock((CAutoFileOpLock *)&v212);
          if ( (*((_DWORD *)a1 + 9) & 0x80) == 0 )
          {
            EmptyVerStateMgr::UpdateStateInRedo(
              (EmptyVerStateMgr *)(*(_QWORD *)(*a1 + 1712LL) + 1536LL),
              (struct RecoveryUnit *)*a1);
            v265[0] = 0;
            v265[1] = 0;
            v266 = 0;
            if ( v200 || v199 )
            {
              LastRedoneLSN = RecoveryUnit::GetLastRedoneLSN(*a1, v333);
              if ( *(_DWORD *)LastRedoneLSN >= (unsigned int)v199 )
              {
                if ( *(_DWORD *)LastRedoneLSN != (_DWORD)v199
                  || (v137 = *(_DWORD *)(LastRedoneLSN + 4), v137 >= HIDWORD(v199))
                  && (v137 != HIDWORD(v199) || *(_WORD *)(LastRedoneLSN + 8) >= v200) )
                {
                  v138 = (const struct LSN *)RecoveryUnit::GetLastRedoneLSN(*a1, v363);
                  HadrRecoveryCallbacks::PageUndoCleared((struct RecoveryUnit *)*a1, v138);
                  LastRedoneLSN = *a1;
                  v262 = *(_QWORD *)(*a1 + 7308LL);
                  v263 = *(_WORD *)(LastRedoneLSN + 7316);
                  v264 = *(_WORD *)(LastRedoneLSN + 7318);
                  v199 = v262;
                  v200 = *(_WORD *)(LastRedoneLSN + 7316);
                }
              }
            }
          }
          if ( v189 )
          {
            if ( (qword_10317AD29 & 8) != 0
              || (v139 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset)) != 0
              && (v140 = **(struct CSessionTraceFlags ***)(v139 + 56)) != 0
              && CSessionTraceFlags::CheckSessionTraceInternal(v140, 0xD4Bu) )
            {
              LODWORD(v202[0]) = 92;
              v197 = 100;
              GetLsnAsDecimalString((const struct LSN *)&v336, &v197, v368);
              LSN::FormatAsHexString(&v336, v366, (unsigned int *)v202);
              LODWORD(v187) = *((_DWORD *)v192 + 4);
              LODWORD(v186) = *((unsigned __int16 *)v192 + 10);
              traceprint(
                L"REDO LSN %.*ls (0x%ls), XdesId 0x%04lx:%08lx Stop after termination LSN reached.\n",
                (unsigned __int64)v197 >> 1,
                v368,
                v366,
                v186,
                v187);
            }
            goto LABEL_394;
          }
LABEL_149:
          LOBYTE(LastRedoneLSN) = -122;
          YieldAndCheckForAbort(LastRedoneLSN, v52);
        }
        else
        {
          v215 = *(LSN *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v209 + 152LL))(v209) + 8);
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v310);
            v90 = (DirtyPageMgr *)v310.QuadPart;
          }
          else
          {
            v90 = MEMORY[0x7FFE0008];
            v188 = MEMORY[0x7FFE0008];
          }
          v203 = v90;
        }
      }
    }
    if ( (*((_DWORD *)a1 + 9) & 0x80) != 0 )
    {
      utassert_fail(1u, "!(isSocratesCompute) || (!isSocratesPageServer)", "recovery.cpp", 15687, 0);
      utassert_fail(1u, "!(isSocratesPageServer) || (!isSocratesCompute)", "recovery.cpp", 15688, 0);
    }
    RecoveryMgr::UpdateLogReplayExecutionTimeStats(a1, 1, v213);
LABEL_168:
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v300);
      v58 = (DirtyPageMgr *)v300.QuadPart;
      v301 = (DirtyPageMgr *)v300.QuadPart;
    }
    else
    {
      v58 = MEMORY[0x7FFE0008];
      v301 = MEMORY[0x7FFE0008];
    }
    if ( v58 < v239 )
    {
      v59 = 0;
      v188 = 0;
    }
    else
    {
      v59 = (DirtyPageMgr *)(v58 - v239);
      v188 = v59;
    }
    v328 = v59;
    if ( v59 == (DirtyPageMgr *)-1LL )
    {
      v60 = -1;
    }
    else if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      v60 = (unsigned __int64)(1000000LL * (_QWORD)v59) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
    }
    else
    {
      v60 = (unsigned __int64)v59 / 0xA;
    }
    RecoveryMgr::UpdateLogReplayExecutionTimeStats(a1, 2, v60 - v213);
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v302);
      v239 = (DirtyPageMgr *)v302.QuadPart;
    }
    else
    {
      v188 = MEMORY[0x7FFE0008];
      v239 = MEMORY[0x7FFE0008];
    }
    v213 = 0;
    RecoveryMgr::ReportRbIoRedoProgress(a1, &v336, 5);
    if ( v57 )
    {
      if ( dword_103172528 )
      {
        v61 = *a1;
        if ( !byte_10316E9EA || (qword_10317B213 & 0x4000000000LL) != 0 )
          v62 = (struct PageServerStats **)(v61 + 8680);
        else
          v62 = *(struct PageServerStats ***)(v61 + 8688);
        EmitPsCkptLagMetrics((struct FCB *)a1[15], *v62);
      }
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v303);
        v63 = (DirtyPageMgr *)v303.QuadPart;
      }
      else
      {
        v63 = MEMORY[0x7FFE0008];
      }
      v193 = v63;
      v340 = v336;
      v341 = v337;
      if ( byte_10316EBBA )
      {
        v64 = *(_WORD *)(*(_QWORD *)v202[0] + 6LL);
        if ( v64 <= *(_WORD *)(*(_QWORD *)v202[0] + 4LL) )
          v64 = *(_WORD *)(*(_QWORD *)v202[0] + 4LL);
        RbIoXlogLinearBsnToLogBlockId(v217 + ((unsigned __int64)v64 >> 9), a1[3080], &v243, &v245);
        v340.QuadPart = __PAIR64__(v245, v243);
        v341 = 1;
      }
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))RecoveryMgr::UpdateForeignRedoProgress)(
        a1,
        &v336,
        &v340,
        (LSN)v198.QuadPart);
      if ( byte_10316E9E6 )
      {
        v65 = *a1;
        v66 = RecoveryUnit::GetPageServerStats((RecoveryUnit *)*a1);
        PageServerUpdateForeignRedoHash(v66, &v217, *(const struct DBTABLE **)(v65 + 1712));
      }
      if ( byte_10316EB21 || (byte_10317B106 & 0x10) != 0 )
        RecoveryMgr::RestoreForeignStalePages((RecoveryMgr *)a1);
      RecoveryUnit::EvaluateForeignCheckpoint((RecoveryUnit *)*a1);
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v304);
        v67 = (DirtyPageMgr *)v304.QuadPart;
      }
      else
      {
        v67 = MEMORY[0x7FFE0008];
      }
      v305 = v67;
      if ( v67 < v193 )
      {
        v68 = 0;
        v188 = 0;
      }
      else
      {
        v68 = (DirtyPageMgr *)(v67 - v193);
        v188 = v68;
      }
      v323 = v68;
      if ( v68 == (DirtyPageMgr *)-1LL )
        v69 = -1;
      else
        v69 = Base_PublicGlobals::sm_invariantTscAvailable
            ? (unsigned __int64)(1000000LL * (_QWORD)v68) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart
            : (unsigned __int64)v68 / 0xA;
      RecoveryMgr::UpdateLogReplayExecutionTimeStats(a1, 10, v69);
      CheckForTriggerPermanentFault((struct RecoveryUnit *)*a1);
      if ( (byte_10317B104 & 0x10) != 0 )
        goto LABEL_394;
    }
    goto LABEL_213;
  }
  catch ( SQLError v276 )
  {
    ExceptionBackout::ExceptionBackout((ExceptionBackout *)v319, (const struct SQLError *)&v276);
    v162 = 21;
    v163 = v216;
    v164 = v216[3079]++ & 3LL;
    v165 = &v163[2 * (unsigned int)v164];
    SOS_Task::GetExceptionInfo((struct WorkerExceptInfo *)(v165 + 3071));
    if ( RecoveryUnit::IsTraceEnabled() )
      RecoveryUnit::PrintTrace(
        (RecoveryUnit *)*v163,
        L"MoveUpRedo failed with error %d, severity %d, address %p.",
        *((unsigned int *)v165 + 6142),
        *((unsigned int *)v165 + 6143),
        v163[2 * v164 + 3072]);
    v166 = v276;
    if ( v277 == 1 )
      v167 = v276;
    else
      v167 = (unsigned __int16)v276;
    if ( v167 != 3617 )
    {
      if ( v277 != 1 )
        v166 = (unsigned __int16)v276;
      if ( v166 != 3602 )
        goto LABEL_506;
    }
    if ( !(unsigned int)SOS_Task::IsCurrentAbortBitSet() )
      goto LABEL_506;
    if ( (*((_DWORD *)v163 + 9) & 0x80) != 0 )
    {
      RecoveryMgr::ShutdownParallelRedoMgr((RecoveryMgr *)v163, 1);
      v320 = v276;
      v321 = v277;
      ex_raisecontrol(&v320);
    }
    v168 = *(_QWORD *)(*v163 + 1712LL);
    if ( (*(_BYTE *)(v168 + 60) & 1) == 0 || *(_QWORD *)(v168 + 640) )
    {
LABEL_506:
      if ( *((_DWORD *)v165 + 6143) == 17 )
        v162 = 17;
      v197 = v162;
      if ( (*((_DWORD *)v163 + 9) & 0x80) != 0 )
      {
        v173 = v192;
      }
      else
      {
        if ( (qword_10317AD29 & 0x200) != 0
          || ((LODWORD(v202[0]) = 0,
               (v170 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset)) != 0)
           && (v171 = **(struct CSessionTraceFlags ***)(v170 + 56)) != 0
            ? (v172 = CSessionTraceFlags::CheckSessionTraceInternal(v171, 0xD51u))
            : (v172 = (int)v202[0]),
              v162 = v197,
              v172) )
        {
          dump_log((struct RecoveryUnit *)*v163, 2, 0);
        }
        v173 = v192;
        if ( v192 )
        {
          if ( word_10318AB38 != *((_WORD *)v192 + 10) || NullXdesId != *((_DWORD *)v192 + 4) )
          {
            v251 = *((_DWORD *)v192 + 4);
            v252 = *((_WORD *)v192 + 10);
            v257 = 0;
            v258 = 0;
            DumpLogForFailures(L"for MoveUpRedo failure - filter XdesId", *v163, 0, (char *)v163 + 22108, &v257, &v251);
          }
        }
        RecXdesTable::GetMinBeginLsn(
          (RecXdesTable *)(v163 + 2932),
          (struct LSN *)&v338,
          1,
          0,
          (struct LSN *)((char *)v163 + 22132));
        v223 = 0;
        v224 = 0;
        if ( !v339 && !v338 )
        {
          v338 = v163[2752];
          v178 = *((_WORD *)v163 + 11012);
        }
        else
        {
          v176 = (unsigned int)v338 < *((_DWORD *)v163 + 5504)
              || (_DWORD)v338 == *((_DWORD *)v163 + 5504)
              && (HIDWORD(v338) < *((_DWORD *)v163 + 5505)
               || HIDWORD(v338) == *((_DWORD *)v163 + 5505) && v339 < *((_WORD *)v163 + 11012));
          v177 = &v338;
          if ( !v176 )
            v177 = v163 + 2752;
          v338 = *v177;
          v178 = *((_WORD *)v177 + 4);
        }
        v339 = v178;
        v232 = NullXdesId;
        v233 = word_10318AB38;
        v234 = 0;
        v235 = 0;
        DumpLogForFailures(L"for MoveUpRedo failure - no filter", *v163, 0, &v338, &v234, &v232);
        LOBYTE(v179) = 1;
        v180 = RecoveryMgr::GetRedoneLSN(v163, &v331, v179);
        if ( *((_WORD *)v163 + 11064) != *(_WORD *)(v180 + 8)
          || *((_DWORD *)v163 + 5530) != *(_DWORD *)v180
          || *((_DWORD *)v163 + 5531) != *(_DWORD *)(v180 + 4) )
        {
          RecoveryUnit::RecoveryFailure((RecoveryUnit *)*v163, v162, 0);
        }
      }
      RecoveryMgr::ShutdownParallelRedoMgr((RecoveryMgr *)v163, 1);
      if ( v173 && *((_BYTE *)v173 + 22) < 0x7Fu )
      {
        v236 = *((_DWORD *)v173 + 6);
        v237 = *((_WORD *)v173 + 14);
        v182 = &v236;
      }
      else
      {
        LODWORD(v216) = 0;
        WORD2(v216) = 0;
        v182 = (int *)&v216;
      }
      v272 = *(_QWORD *)((char *)v163 + 22132);
      v273 = *((_WORD *)v163 + 11070);
      v204.LowPart = *v182;
      WORD2(v204.QuadPart) = *((_WORD *)v182 + 2);
      v183 = *(_QWORD *)(*v163 + 1712LL);
      LODWORD(v184) = *(_DWORD *)(v183 + 928);
      ex_raise(33, 13, v162, 2, v184, v183 + 936, &v204, &v272);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v319);
      goto LABEL_554;
    }
    RecoveryMgr::ShutdownParallelRedoMgr((RecoveryMgr *)v163, 1);
    ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v319);
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v204);
      v153 = (DirtyPageMgr *)v204.QuadPart;
    }
    else
    {
      v153 = MEMORY[0x7FFE0008];
    }
    if ( v153 < v225 )
      v154 = 0;
    else
      v154 = v153 - v225;
    *(_QWORD *)(v227 + 8LL * v226 + 104) += v154;
    v354 = &IDbCopyRestoreCallback::`vftable';
    if ( !v254 && *v253 )
      *v253 = 0;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1452LL) = v201;
    if ( !v256 && *v255 )
      *v255 = 0;
    BootPagePtr::~BootPagePtr((BootPagePtr *)&v342);
    v206 = &SLogIterForward::`vftable';
    v155 = v209;
    if ( v209 )
    {
LABEL_439:
      (**(void (__fastcall ***)(__int64, __int64))v209)(v155, 1);
      v209 = 0;
    }
    return;
  }
LABEL_554:
  v156 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v157 = *(struct Worker **)(v156 + 256);
  if ( !v157 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v157 = *(struct Worker **)(v156 + 256);
  }
  if ( *((_DWORD *)v157 + 139) )
    ExceptionPostCatchActions(v157);
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&v244);
    v158 = (DirtyPageMgr *)v244.QuadPart;
  }
  else
  {
    v158 = MEMORY[0x7FFE0008];
  }
  if ( v158 < v225 )
    v159 = 0;
  else
    v159 = v158 - v225;
  *(_QWORD *)(v227 + 8LL * v226 + 104) += v159;
  v354 = &IDbCopyRestoreCallback::`vftable';
  if ( !v254 && *v253 )
    *v253 = 0;
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                    + SystemThread_TlsOffset
                                    + 8LL)
                        + 96LL)
            + 1452LL) = v201;
  if ( !v256 && *v255 )
    *v255 = 0;
  if ( v343 || (v342 & 1) != 0 )
  {
    if ( (v342 & 1) == 0 )
    {
      PageRef::Unlatch((PageRef *)&v343);
      if ( (_QWORD)v346 )
      {
        operator delete((void *)v346, 0x6FAu);
        *(_QWORD *)&v346 = 0;
      }
    }
    BootPagePtr::Release((BootPagePtr *)&v342, 0);
  }
  if ( (_QWORD)v346 )
  {
    operator delete((void *)v346, 0x6FAu);
    *(_QWORD *)&v346 = 0;
  }
  PageRef::~PageRef((PageRef *)&v343);
  v206 = &SLogIterForward::`vftable';
  v155 = v209;
  if ( v209 )
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
