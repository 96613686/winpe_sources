# CSession::Dump(CDStream *,bool)

- ea: `0x101179980`
- end: `0x10117ac17`
- name: `?Dump@CSession@@QEBA_NPEAVCDStream@@_N@Z`
- size: `4759`
- prototype: `bool __fastcall(CSession *__hidden this, struct CDStream *, bool)`
- caller_count: `4`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x100419ac0`
- `0x101667750`
- `0x10170d930`
- `0x10170e4f0`

## callees

- `0x100401070`
- `0x1004012d0`
- `0x100401340`
- `0x100f03340`
- `0x100f03560`
- `0x100f037d0`
- `0x101179980`
- `0x10117bc50`
- `0x10117de90`
- `0x10117f270`
- `0x10117f2c0`
- `0x10117fac0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10117a75f`
- `KERNEL32!QueryPerformanceCounter` at `0x10117a7f5`
- `KERNEL32!QueryPerformanceCounter` at `0x10117a75f`
- `KERNEL32!QueryPerformanceCounter` at `0x10117a7f5`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10117a79c`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10117a6c5`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10117a93a`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10117a743`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10117a7d9`
- `sqldk!?ex_trans_cexcept_nodump@@YAXIPEAU_EXCEPTION_POINTERS@@@Z` at `0x101179a1a`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x101179a3a`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10117ab9d`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10117ab9d`
- `sqldk!?GetVMAccess@SOS_OS@@SAHPEBX_KH@Z` at `0x10117a58b`
- `sqldk!?GetVMAccess@SOS_OS@@SAHPEBX_KH@Z` at `0x10117a627`
- `sqldk!?GetVMAccess@SOS_OS@@SAHPEBX_KH@Z` at `0x10117a88d`
- `sqldk!?GetVMAccess@SOS_OS@@SAHPEBX_KH@Z` at `0x10117aa24`
- `sqldk!?GetVMAccess@SOS_OS@@SAHPEBX_KH@Z` at `0x10117a58b`
- `sqldk!?GetVMAccess@SOS_OS@@SAHPEBX_KH@Z` at `0x10117a627`
- `sqldk!?GetVMAccess@SOS_OS@@SAHPEBX_KH@Z` at `0x10117a88d`
- `sqldk!?GetVMAccess@SOS_OS@@SAHPEBX_KH@Z` at `0x10117aa24`
- `sqldk!SystemThread_TlsIndex` at `0x1011799e4`
- `sqldk!SystemThread_TlsIndex` at `0x101179aa8`
- `sqldk!SystemThread_TlsIndex` at `0x101179b2a`
- `sqldk!SystemThread_TlsIndex` at `0x101179bab`
- `sqldk!SystemThread_TlsIndex` at `0x101179c97`
- `sqldk!SystemThread_TlsIndex` at `0x101179d23`
- `sqldk!SystemThread_TlsIndex` at `0x101179daa`
- `sqldk!SystemThread_TlsIndex` at `0x101179e31`
- `sqldk!SystemThread_TlsIndex` at `0x101179ebd`
- `sqldk!SystemThread_TlsIndex` at `0x101179f44`
- `sqldk!SystemThread_TlsIndex` at `0x101179fd3`
- `sqldk!SystemThread_TlsIndex` at `0x10117a05b`
- `sqldk!SystemThread_TlsIndex` at `0x10117a0e3`
- `sqldk!SystemThread_TlsIndex` at `0x10117a16b`
- `sqldk!SystemThread_TlsIndex` at `0x10117a1f3`
- `sqldk!SystemThread_TlsIndex` at `0x10117a27b`
- `sqldk!SystemThread_TlsIndex` at `0x10117a30b`
- `sqldk!SystemThread_TlsIndex` at `0x10117a393`
- `sqldk!SystemThread_TlsIndex` at `0x10117a41a`
- `sqldk!SystemThread_TlsIndex` at `0x10117a4a2`
- `sqldk!SystemThread_TlsIndex` at `0x10117a529`
- `sqldk!SystemThread_TlsIndex` at `0x10117a5c8`
- `sqldk!SystemThread_TlsIndex` at `0x10117a6f2`
- `sqldk!SystemThread_TlsIndex` at `0x10117a9ae`
- `sqldk!SystemThread_TlsIndex` at `0x10117aa60`
- `sqldk!SystemThread_TlsIndex` at `0x10117ab15`
- `sqldk!SystemThread_TlsIndex` at `0x10117ab65`
- `sqldk!SystemThread_TlsIndex` at `0x10117abad`
- `sqldk!SystemThread_TlsOffset` at `0x1011799ed`
- `sqldk!SystemThread_TlsOffset` at `0x101179ab1`
- `sqldk!SystemThread_TlsOffset` at `0x101179b33`
- `sqldk!SystemThread_TlsOffset` at `0x101179bb4`
- `sqldk!SystemThread_TlsOffset` at `0x101179ca0`
- `sqldk!SystemThread_TlsOffset` at `0x101179d2c`
- `sqldk!SystemThread_TlsOffset` at `0x101179db3`
- `sqldk!SystemThread_TlsOffset` at `0x101179e3a`
- `sqldk!SystemThread_TlsOffset` at `0x101179ec6`
- `sqldk!SystemThread_TlsOffset` at `0x101179f4d`
- `sqldk!SystemThread_TlsOffset` at `0x101179fdc`
- `sqldk!SystemThread_TlsOffset` at `0x10117a064`
- `sqldk!SystemThread_TlsOffset` at `0x10117a0ec`
- `sqldk!SystemThread_TlsOffset` at `0x10117a174`
- `sqldk!SystemThread_TlsOffset` at `0x10117a1fc`
- `sqldk!SystemThread_TlsOffset` at `0x10117a284`
- `sqldk!SystemThread_TlsOffset` at `0x10117a314`
- `sqldk!SystemThread_TlsOffset` at `0x10117a39c`
- `sqldk!SystemThread_TlsOffset` at `0x10117a423`
- `sqldk!SystemThread_TlsOffset` at `0x10117a4ab`
- `sqldk!SystemThread_TlsOffset` at `0x10117a532`
- `sqldk!SystemThread_TlsOffset` at `0x10117a5d1`
- `sqldk!SystemThread_TlsOffset` at `0x10117a6fb`
- `sqldk!SystemThread_TlsOffset` at `0x10117a9b7`
- `sqldk!SystemThread_TlsOffset` at `0x10117aa69`
- `sqldk!SystemThread_TlsOffset` at `0x10117ab1e`
- `sqldk!SystemThread_TlsOffset` at `0x10117ab6e`
- `sqldk!SystemThread_TlsOffset` at `0x10117abb6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179a06`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179acc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179b4e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179bcf`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179cb9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179d45`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179dcc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179e53`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179edf`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179f66`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179ff5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a07d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a105`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a18d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a215`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a29d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a32d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a3b5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a43c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a4c4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a54b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a5ea`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a9d0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117aa82`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117ab37`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117ab87`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117abcf`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179a06`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179acc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179b4e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179bcf`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179cb9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179d45`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179dcc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179e53`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179edf`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179f66`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101179ff5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a07d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a105`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a18d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a215`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a29d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a32d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a3b5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a43c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a4c4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a54b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a5ea`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117a9d0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117aa82`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117ab37`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117ab87`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10117abcf`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101179afd`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101179b7e`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101179c6a`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101179cf6`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101179d7d`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101179e04`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101179e90`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101179f17`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101179fa6`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a02e`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a0b6`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a13e`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a1c6`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a24e`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a2de`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a366`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a3ed`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a475`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a4fc`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101179afd`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101179b7e`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101179c6a`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101179cf6`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101179d7d`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101179e04`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101179e90`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101179f17`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x101179fa6`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a02e`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a0b6`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a13e`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a1c6`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a24e`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a2de`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a366`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a3ed`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a475`
- `sqldk!?Write@CDStream@@QEAAHPEBD0ZZ` at `0x10117a4fc`
- `sqldk!?Flush@CDStream@@QEAAHXZ` at `0x10117aae5`
- `sqldk!?Flush@CDStream@@QEAAHXZ` at `0x10117aae5`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x101179a7b`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x101179a7b`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x101179a8d`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x101179b0f`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x101179b90`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x101179c7c`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x101179d08`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x101179d8f`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x101179e16`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x101179ea2`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x101179f29`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x101179fb8`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x10117a040`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x10117a0c8`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x10117a150`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x10117a1d8`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x10117a260`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x10117a2f0`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x10117a378`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x10117a3ff`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x10117a487`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x10117a50e`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x10117a5ad`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x10117a993`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x10117aa45`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x10117aafa`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x101179a8d`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x101179b0f`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x101179b90`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=2
bool __fastcall CSession::Dump(CSession *this, struct CDStream *a2, char a3)
{
  __int64 v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  int v16; // edi
  __int64 v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rbx
  __int64 v24; // rcx
  __int64 v25; // rbx
  __int64 v26; // rcx
  __int64 v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rbx
  __int64 v30; // rcx
  __int64 v31; // rbx
  __int64 v32; // rcx
  __int64 v33; // rbx
  __int64 v34; // rcx
  __int64 v35; // rbx
  __int64 v36; // rcx
  __int64 v37; // rbx
  __int64 v38; // rcx
  __int64 v39; // rbx
  __int64 v40; // rcx
  __int64 v41; // rbx
  __int64 v42; // rcx
  __int64 v43; // rbx
  __int64 v44; // rcx
  __int64 v45; // rbx
  __int64 v46; // rcx
  __int64 v47; // rbx
  __int64 v48; // rcx
  __int64 v49; // rbx
  __int64 v50; // rcx
  const void *v51; // rcx
  __int64 v52; // rbx
  __int64 v53; // rcx
  const void *v54; // rcx
  bool v55; // zf
  __int64 v56; // rdi
  __int64 v57; // rdi
  CSbTransportMgr *QuadPart; // rax
  CSbTransportMgr *v59; // rax
  signed __int64 v60; // rax
  const void *v61; // rcx
  __int64 v62; // r14
  char *v63; // rdi
  _OWORD *v64; // rax
  char *v65; // rcx
  int v66; // r8d
  __int64 v67; // rbx
  __int64 v68; // rcx
  CSession *i; // rcx
  _QWORD *v70; // rdi
  __int64 v71; // rbx
  __int64 v72; // rcx
  struct SOS_Task *v73; // rax
  __int64 v74; // rbx
  __int64 v75; // rcx
  __int64 v76; // [rsp+30h] [rbp-7F8h]
  bool v77; // [rsp+38h] [rbp-7F0h]
  volatile signed __int64 *v78; // [rsp+40h] [rbp-7E8h]
  _BYTE v79[40]; // [rsp+48h] [rbp-7E0h] BYREF
  int v80; // [rsp+70h] [rbp-7B8h]
  __int64 v81; // [rsp+78h] [rbp-7B0h]
  signed __int64 UniqueThread_low; // [rsp+80h] [rbp-7A8h]
  __int64 v83; // [rsp+88h] [rbp-7A0h]
  __int64 v84; // [rsp+90h] [rbp-798h]
  CSbTransportMgr *v85; // [rsp+98h] [rbp-790h]
  char *v86; // [rsp+A0h] [rbp-788h]
  int v87; // [rsp+A8h] [rbp-780h]
  int v88; // [rsp+ACh] [rbp-77Ch]
  LARGE_INTEGER PerformanceCount; // [rsp+B0h] [rbp-778h] BYREF
  CSbTransportMgr *v90; // [rsp+B8h] [rbp-770h]
  CSbTransportMgr *v91; // [rsp+C0h] [rbp-768h]
  LARGE_INTEGER v92; // [rsp+C8h] [rbp-760h] BYREF
  CSbTransportMgr *v93; // [rsp+D0h] [rbp-758h]
  CSbTransportMgr *v94; // [rsp+D8h] [rbp-750h]
  int v95; // [rsp+E0h] [rbp-748h]
  CSession *v96; // [rsp+E8h] [rbp-740h]
  struct CDStream *v97; // [rsp+F0h] [rbp-738h]
  BOOL v98; // [rsp+F8h] [rbp-730h]
  const void *v99; // [rsp+110h] [rbp-718h]
  const void *v100; // [rsp+118h] [rbp-710h]
  signed __int64 v101; // [rsp+120h] [rbp-708h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+128h] [rbp-700h]
  __int64 v103; // [rsp+130h] [rbp-6F8h]
  char *v104; // [rsp+138h] [rbp-6F0h]
  const void *v105; // [rsp+140h] [rbp-6E8h]
  char *v106; // [rsp+148h] [rbp-6E0h]
  __int64 v107; // [rsp+150h] [rbp-6D8h]
  _BYTE v108[72]; // [rsp+158h] [rbp-6D0h] BYREF
  _BYTE v109[528]; // [rsp+1A0h] [rbp-688h] BYREF
  _BYTE v110[13]; // [rsp+3B0h] [rbp-478h] BYREF
  char v111; // [rsp+3BDh] [rbp-46Bh]
  char v112[1074]; // [rsp+3BEh] [rbp-46Ah] BYREF

  v107 = -2;
  v96 = this;
  v97 = a2;
  if ( !a2 )
    return 0;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  v8 = *(_QWORD *)(v7 + 3208);
  *(_QWORD *)(v7 + 3208) = ex_trans_cexcept_nodump;
  v76 = v8;
  ExcHandler::ExcHandler((ExcHandler *)v79, 0x1Du, 5u, 0, (int (*)(int, int, int, int, char *))hdl_backout, 0);
  CAutoStreamHeader::CAutoStreamHeader((CAutoStreamHeader *)v109);
  if ( CAutoStreamHeader::Init((CAutoStreamHeader *)v109, a2, "CSession @0x%p", this) )
  {
    if ( CDStream::Write(a2, "m_sessionId", "%d", *((__int16 *)this + 8)) )
    {
      if ( CDStream::Write(a2, "m_cRef", "%ld", *((_DWORD *)this + 2)) )
      {
        v16 = 0;
        v80 = 0;
        while ( v16 < 6 )
        {
          qmemcpy(v110, "m_rgcRefType[", sizeof(v110));
          strcpy(v112, "]");
          v111 = v16 + 48;
          v95 = *((_DWORD *)this + v16 + 11);
          if ( !CDStream::Write(a2, v110, "%ld", v95) )
          {
            CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
            ExcHandler::~ExcHandler((ExcHandler *)v79);
            v17 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            v18 = *(_QWORD *)(v17 + 256);
            if ( !v18 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v18 = *(_QWORD *)(v17 + 256);
            }
            *(_QWORD *)(v18 + 3208) = v76;
            return 0;
          }
          v80 = ++v16;
        }
        if ( CDStream::Write(a2, "m_pmo", "0x%p", *((const void **)this + 11)) )
        {
          if ( CDStream::Write(a2, "m_pstackBhfPool", "0x%p", *((const void **)this + 29)) )
          {
            if ( CDStream::Write(a2, "m_dwLoginFlags", "0x%04x", *((_DWORD *)this + 100)) )
            {
              if ( CDStream::Write(a2, "m_fBackground", "%d", *((_BYTE *)this + 269) & 1) )
              {
                if ( CDStream::Write(a2, "m_eConnResetOption", "%d", *((_DWORD *)this + 65)) )
                {
                  if ( CDStream::Write(a2, "m_fUserProc", "%d", (*((unsigned __int8 *)this + 269) >> 1) & 1) )
                  {
                    if ( CDStream::Write(a2, "m_fConnReset", "%d", *((unsigned __int8 *)this + 258)) )
                    {
                      if ( CDStream::Write(a2, "m_fIsConnReset", "%d", *((unsigned __int8 *)this + 259)) )
                      {
                        if ( CDStream::Write(a2, "m_fInLogin", "%d", *((unsigned __int8 *)this + 264)) )
                        {
                          if ( CDStream::Write(a2, "m_fAuditLoginSent", "%d", *((unsigned __int8 *)this + 256)) )
                          {
                            if ( CDStream::Write(a2, "m_fAuditLoginFailedSent", "%d", *((unsigned __int8 *)this + 257)) )
                            {
                              if ( CDStream::Write(
                                     a2,
                                     "m_fReplRelease",
                                     "%d",
                                     (*((unsigned __int8 *)this + 269) >> 3) & 1) )
                              {
                                if ( CDStream::Write(a2, "m_fKill", "%d", *((unsigned __int8 *)this + 984)) )
                                {
                                  if ( CDStream::Write(a2, "m_ulLoginStamp", "%lu", *((_DWORD *)this + 110)) )
                                  {
                                    if ( CDStream::Write(a2, "m_eclClient", "%hu", *((unsigned __int16 *)this + 92)) )
                                    {
                                      if ( CDStream::Write(a2, "m_protType", "%d", *((_DWORD *)this + 159)) )
                                      {
                                        v51 = (const void *)*((_QWORD *)this + 13);
                                        v99 = v51;
                                        if ( v51
                                          && SOS_OS::GetVMAccess(v51, 0x2D0u, 1)
                                          && !CUEnvTransient::Dump(*((CUEnvTransient **)this + 13), a2) )
                                        {
                                          CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
                                          ExcHandler::~ExcHandler((ExcHandler *)v79);
                                          v52 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                + SystemThread_TlsIndex)
                                              + SystemThread_TlsOffset;
                                          v53 = *(_QWORD *)(v52 + 256);
                                          if ( !v53 )
                                          {
                                            SystemThread::MakeMiniSOSThread(0);
                                            v53 = *(_QWORD *)(v52 + 256);
                                          }
                                          *(_QWORD *)(v53 + 3208) = v76;
                                          return 0;
                                        }
                                        else
                                        {
                                          v54 = (const void *)*((_QWORD *)this + 24);
                                          v100 = v54;
                                          if ( v54 && SOS_OS::GetVMAccess(v54, 0x5Eu, 1) )
                                            CDStream::DumpBytes(
                                              a2,
                                              *((const unsigned __int8 **)this + 24),
                                              0,
                                              94,
                                              L"m_pV7LoginRec");
                                          v86 = 0;
                                          v78 = (volatile signed __int64 *)((char *)this + 176);
                                          v85 = 0;
                                          v81 = 0;
                                          UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
                                          if ( *((_DWORD *)this + 44)
                                            || (v101 = _InterlockedCompareExchange64(v78, UniqueThread_low, 0),
                                                v98 = v101 == 0,
                                                v101) )
                                          {
                                            if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
                                            {
                                              v84 = 0;
                                              ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
                                              v55 = ThreadLocalStoragePointer[SystemThread_TlsIndex]
                                                  + SystemThread_TlsOffset == 0;
                                              v56 = ThreadLocalStoragePointer[SystemThread_TlsIndex]
                                                  + SystemThread_TlsOffset;
                                              v103 = v56;
                                              if ( v55 || *(_QWORD *)(v56 + 272) != v56 )
                                              {
                                                v57 = v84;
                                              }
                                              else
                                              {
                                                v57 = *(_QWORD *)(v56 + 256);
                                                v84 = v57;
                                              }
                                            }
                                            else
                                            {
                                              v57 = 0;
                                            }
                                            v81 = v57;
                                            if ( v57 )
                                            {
                                              v87 = Base_PublicGlobals::sm_invariantTscAvailable;
                                              if ( Base_PublicGlobals::sm_invariantTscAvailable )
                                              {
                                                QueryPerformanceCounter(&PerformanceCount);
                                                QuadPart = (CSbTransportMgr *)PerformanceCount.QuadPart;
                                                v91 = (CSbTransportMgr *)PerformanceCount.QuadPart;
                                              }
                                              else
                                              {
                                                QuadPart = MEMORY[0x7FFE0008];
                                                v90 = MEMORY[0x7FFE0008];
                                                v91 = MEMORY[0x7FFE0008];
                                                v57 = v81;
                                              }
                                              v85 = QuadPart;
                                            }
                                            if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
                                              Spinlock<240,3,258>::SpinToAcquireWithExponentialBackoff(
                                                v78,
                                                UniqueThread_low);
                                            else
                                              Spinlock<240,3,258>::SpinToAcquireOptimistic(v78, v57, UniqueThread_low);
                                            if ( v57 )
                                            {
                                              v88 = Base_PublicGlobals::sm_invariantTscAvailable;
                                              if ( Base_PublicGlobals::sm_invariantTscAvailable )
                                              {
                                                QueryPerformanceCounter(&v92);
                                                v59 = (CSbTransportMgr *)v92.QuadPart;
                                                v94 = (CSbTransportMgr *)v92.QuadPart;
                                              }
                                              else
                                              {
                                                v59 = MEMORY[0x7FFE0008];
                                                v93 = MEMORY[0x7FFE0008];
                                                v94 = MEMORY[0x7FFE0008];
                                                v57 = v81;
                                              }
                                              if ( v59 < v85 )
                                                v60 = 0;
                                              else
                                                v60 = v59 - v85;
                                              v104 = (char *)v60;
                                              v83 = v57 + 3192;
                                              *(_QWORD *)(v57 + 3192) += v60;
                                            }
                                          }
                                          v61 = (const void *)*((_QWORD *)this + 12);
                                          v105 = v61;
                                          if ( v61 && (v62 = 8, SOS_OS::GetVMAccess(v61, 8u, 1)) )
                                          {
                                            v63 = &v112[2];
                                            v86 = &v112[2];
                                            v64 = (_OWORD *)*((_QWORD *)this + 12);
                                            v65 = &v112[2];
                                            do
                                            {
                                              *(_OWORD *)v65 = *v64;
                                              *((_OWORD *)v65 + 1) = v64[1];
                                              *((_OWORD *)v65 + 2) = v64[2];
                                              *((_OWORD *)v65 + 3) = v64[3];
                                              *((_OWORD *)v65 + 4) = v64[4];
                                              *((_OWORD *)v65 + 5) = v64[5];
                                              *((_OWORD *)v65 + 6) = v64[6];
                                              v65 += 128;
                                              *((_OWORD *)v65 - 1) = v64[7];
                                              v64 += 8;
                                              --v62;
                                            }
                                            while ( v62 );
                                            *(_OWORD *)v65 = *v64;
                                            *((_OWORD *)v65 + 1) = v64[1];
                                            *((_QWORD *)v65 + 4) = *((_QWORD *)v64 + 4);
                                          }
                                          else
                                          {
                                            v63 = v86;
                                          }
                                          v106 = (char *)this + 176;
                                          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                                          {
                                            v66 = rand();
                                            if ( v66 == 5 * (v66 / 5) )
                                              Spinlock<240,3,258>::UpdateStatSnapshot();
                                          }
                                          *((_QWORD *)this + 22) = 0;
                                          if ( !v63
                                            || (*(unsigned __int8 (__fastcall **)(char *, struct CDStream *))(*(_QWORD *)v63 + 8LL))(
                                                 v63,
                                                 a2) )
                                          {
                                            for ( i = (CSession *)*((_QWORD *)this + 16); ; i = (CSession *)v70[2] )
                                            {
                                              if ( i == (CSession *)((char *)this + 120) )
                                                i = 0;
                                              v70 = 0;
                                              if ( i )
                                                v70 = (_QWORD *)((char *)i - 8);
                                              if ( !v70 || !SOS_OS::GetVMAccess(v70, 0xE8u, 1) )
                                                break;
                                              if ( !CBatch::Dump((CBatch *)v70, a2) )
                                              {
                                                CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
                                                ExcHandler::~ExcHandler((ExcHandler *)v79);
                                                v71 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                      + SystemThread_TlsIndex)
                                                    + SystemThread_TlsOffset;
                                                v72 = *(_QWORD *)(v71 + 256);
                                                if ( !v72 )
                                                {
                                                  SystemThread::MakeMiniSOSThread(0);
                                                  v72 = *(_QWORD *)(v71 + 256);
                                                }
                                                *(_QWORD *)(v72 + 3208) = v76;
                                                return 0;
                                              }
                                            }
                                            if ( a3 )
                                            {
                                              CTaskIteratorForDump::CTaskIteratorForDump(
                                                (CTaskIteratorForDump *)v108,
                                                this,
                                                0);
                                              while ( 1 )
                                              {
                                                v73 = CTaskIteratorForDump::PTaskNext((CTaskIteratorForDump *)v108);
                                                if ( !v73 )
                                                  break;
                                                CTaskIteratorForDump::DumpExecContexts(v73, a2);
                                              }
                                            }
                                            v77 = CDStream::Flush(a2) != 0;
                                            CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
                                            ExcHandler::~ExcHandler((ExcHandler *)v79);
                                            v74 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                  + SystemThread_TlsIndex)
                                                + SystemThread_TlsOffset;
                                            v75 = *(_QWORD *)(v74 + 256);
                                            if ( !v75 )
                                            {
                                              SystemThread::MakeMiniSOSThread(0);
                                              v75 = *(_QWORD *)(v74 + 256);
                                            }
                                            *(_QWORD *)(v75 + 3208) = v76;
                                            return v77;
                                          }
                                          else
                                          {
                                            CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
                                            ExcHandler::~ExcHandler((ExcHandler *)v79);
                                            v67 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                  + SystemThread_TlsIndex)
                                                + SystemThread_TlsOffset;
                                            v68 = *(_QWORD *)(v67 + 256);
                                            if ( !v68 )
                                            {
                                              SystemThread::MakeMiniSOSThread(0);
                                              v68 = *(_QWORD *)(v67 + 256);
                                            }
                                            *(_QWORD *)(v68 + 3208) = v76;
                                            return 0;
                                          }
                                        }
                                      }
                                      else
                                      {
                                        CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
                                        ExcHandler::~ExcHandler((ExcHandler *)v79);
                                        v49 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                              + SystemThread_TlsIndex)
                                            + SystemThread_TlsOffset;
                                        v50 = *(_QWORD *)(v49 + 256);
                                        if ( !v50 )
                                        {
                                          SystemThread::MakeMiniSOSThread(0);
                                          v50 = *(_QWORD *)(v49 + 256);
                                        }
                                        *(_QWORD *)(v50 + 3208) = v76;
                                        return 0;
                                      }
                                    }
                                    else
                                    {
                                      CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
                                      ExcHandler::~ExcHandler((ExcHandler *)v79);
                                      v47 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset;
                                      v48 = *(_QWORD *)(v47 + 256);
                                      if ( !v48 )
                                      {
                                        SystemThread::MakeMiniSOSThread(0);
                                        v48 = *(_QWORD *)(v47 + 256);
                                      }
                                      *(_QWORD *)(v48 + 3208) = v76;
                                      return 0;
                                    }
                                  }
                                  else
                                  {
                                    CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
                                    ExcHandler::~ExcHandler((ExcHandler *)v79);
                                    v45 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                        + SystemThread_TlsOffset;
                                    v46 = *(_QWORD *)(v45 + 256);
                                    if ( !v46 )
                                    {
                                      SystemThread::MakeMiniSOSThread(0);
                                      v46 = *(_QWORD *)(v45 + 256);
                                    }
                                    *(_QWORD *)(v46 + 3208) = v76;
                                    return 0;
                                  }
                                }
                                else
                                {
                                  CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
                                  ExcHandler::~ExcHandler((ExcHandler *)v79);
                                  v43 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset;
                                  v44 = *(_QWORD *)(v43 + 256);
                                  if ( !v44 )
                                  {
                                    SystemThread::MakeMiniSOSThread(0);
                                    v44 = *(_QWORD *)(v43 + 256);
                                  }
                                  *(_QWORD *)(v44 + 3208) = v76;
                                  return 0;
                                }
                              }
                              else
                              {
                                CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
                                ExcHandler::~ExcHandler((ExcHandler *)v79);
                                v41 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                    + SystemThread_TlsOffset;
                                v42 = *(_QWORD *)(v41 + 256);
                                if ( !v42 )
                                {
                                  SystemThread::MakeMiniSOSThread(0);
                                  v42 = *(_QWORD *)(v41 + 256);
                                }
                                *(_QWORD *)(v42 + 3208) = v76;
                                return 0;
                              }
                            }
                            else
                            {
                              CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
                              ExcHandler::~ExcHandler((ExcHandler *)v79);
                              v39 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                  + SystemThread_TlsOffset;
                              v40 = *(_QWORD *)(v39 + 256);
                              if ( !v40 )
                              {
                                SystemThread::MakeMiniSOSThread(0);
                                v40 = *(_QWORD *)(v39 + 256);
                              }
                              *(_QWORD *)(v40 + 3208) = v76;
                              return 0;
                            }
                          }
                          else
                          {
                            CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
                            ExcHandler::~ExcHandler((ExcHandler *)v79);
                            v37 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset;
                            v38 = *(_QWORD *)(v37 + 256);
                            if ( !v38 )
                            {
                              SystemThread::MakeMiniSOSThread(0);
                              v38 = *(_QWORD *)(v37 + 256);
                            }
                            *(_QWORD *)(v38 + 3208) = v76;
                            return 0;
                          }
                        }
                        else
                        {
                          CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
                          ExcHandler::~ExcHandler((ExcHandler *)v79);
                          v35 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset;
                          v36 = *(_QWORD *)(v35 + 256);
                          if ( !v36 )
                          {
                            SystemThread::MakeMiniSOSThread(0);
                            v36 = *(_QWORD *)(v35 + 256);
                          }
                          *(_QWORD *)(v36 + 3208) = v76;
                          return 0;
                        }
                      }
                      else
                      {
                        CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
                        ExcHandler::~ExcHandler((ExcHandler *)v79);
                        v33 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset;
                        v34 = *(_QWORD *)(v33 + 256);
                        if ( !v34 )
                        {
                          SystemThread::MakeMiniSOSThread(0);
                          v34 = *(_QWORD *)(v33 + 256);
                        }
                        *(_QWORD *)(v34 + 3208) = v76;
                        return 0;
                      }
                    }
                    else
                    {
                      CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
                      ExcHandler::~ExcHandler((ExcHandler *)v79);
                      v31 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset;
                      v32 = *(_QWORD *)(v31 + 256);
                      if ( !v32 )
                      {
                        SystemThread::MakeMiniSOSThread(0);
                        v32 = *(_QWORD *)(v31 + 256);
                      }
                      *(_QWORD *)(v32 + 3208) = v76;
                      return 0;
                    }
                  }
                  else
                  {
                    CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
                    ExcHandler::~ExcHandler((ExcHandler *)v79);
                    v29 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset;
                    v30 = *(_QWORD *)(v29 + 256);
                    if ( !v30 )
                    {
                      SystemThread::MakeMiniSOSThread(0);
                      v30 = *(_QWORD *)(v29 + 256);
                    }
                    *(_QWORD *)(v30 + 3208) = v76;
                    return 0;
                  }
                }
                else
                {
                  CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
                  ExcHandler::~ExcHandler((ExcHandler *)v79);
                  v27 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset;
                  v28 = *(_QWORD *)(v27 + 256);
                  if ( !v28 )
                  {
                    SystemThread::MakeMiniSOSThread(0);
                    v28 = *(_QWORD *)(v27 + 256);
                  }
                  *(_QWORD *)(v28 + 3208) = v76;
                  return 0;
                }
              }
              else
              {
                CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
                ExcHandler::~ExcHandler((ExcHandler *)v79);
                v25 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset;
                v26 = *(_QWORD *)(v25 + 256);
                if ( !v26 )
                {
                  SystemThread::MakeMiniSOSThread(0);
                  v26 = *(_QWORD *)(v25 + 256);
                }
                *(_QWORD *)(v26 + 3208) = v76;
                return 0;
              }
            }
            else
            {
              CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
              ExcHandler::~ExcHandler((ExcHandler *)v79);
              v23 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              v24 = *(_QWORD *)(v23 + 256);
              if ( !v24 )
              {
                SystemThread::MakeMiniSOSThread(0);
                v24 = *(_QWORD *)(v23 + 256);
              }
              *(_QWORD *)(v24 + 3208) = v76;
              return 0;
            }
          }
          else
          {
            CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
            ExcHandler::~ExcHandler((ExcHandler *)v79);
            v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            v22 = *(_QWORD *)(v21 + 256);
            if ( !v22 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v22 = *(_QWORD *)(v21 + 256);
            }
            *(_QWORD *)(v22 + 3208) = v76;
            return 0;
          }
        }
        else
        {
          CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
          ExcHandler::~ExcHandler((ExcHandler *)v79);
          v19 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v20 = *(_QWORD *)(v19 + 256);
          if ( !v20 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v20 = *(_QWORD *)(v19 + 256);
          }
          *(_QWORD *)(v20 + 3208) = v76;
          return 0;
        }
      }
      else
      {
        CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
        ExcHandler::~ExcHandler((ExcHandler *)v79);
        v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v15 = *(_QWORD *)(v14 + 256);
        if ( !v15 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v15 = *(_QWORD *)(v14 + 256);
        }
        *(_QWORD *)(v15 + 3208) = v8;
        return 0;
      }
    }
    else
    {
      CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
      ExcHandler::~ExcHandler((ExcHandler *)v79);
      v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v13 = *(_QWORD *)(v12 + 256);
      if ( !v13 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v13 = *(_QWORD *)(v12 + 256);
      }
      *(_QWORD *)(v13 + 3208) = v8;
      return 0;
    }
  }
  else
  {
    CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v109);
    ExcHandler::~ExcHandler((ExcHandler *)v79);
    v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v10 = *(_QWORD *)(v9 + 256);
    if ( !v10 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v10 = *(_QWORD *)(v9 + 256);
    }
    *(_QWORD *)(v10 + 3208) = v8;
    return 0;
  }
}

```

## disassembly

```asm
0x101179980  mov     rax, rsp
0x101179983  push    rdi
0x101179984  push    r12
0x101179986  push    r13
0x101179988  push    r14
0x10117998a  push    r15
0x10117998c  sub     rsp, 800h
0x101179993  mov     qword ptr [rax-6D8h], 0FFFFFFFFFFFFFFFEh
0x10117999e  mov     [rax+18h], rbx
0x1011799a2  mov     [rax+20h], rsi
0x1011799a6  mov     rax, cs:__security_cookie
0x1011799ad  xor     rax, rsp
0x1011799b0  mov     [rsp+828h+var_38], rax
0x1011799b8  movzx   r12d, r8b
0x1011799bc  mov     rbx, rdx
0x1011799bf  mov     rsi, rcx
0x1011799c2  mov     [rsp+828h+var_740], rcx
0x1011799ca  mov     [rsp+828h+var_738], rdx
0x1011799d2  test    rdx, rdx
0x1011799d5  jz      loc_10117ABE8
0x1011799db  mov     rdx, gs:58h
0x1011799e4  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1011799eb  mov     ecx, [rax]
0x1011799ed  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1011799f4  mov     edi, [rax]
0x1011799f6  add     rdi, [rdx+rcx*8]
0x1011799fa  mov     rcx, [rdi+100h]
0x101179a01  test    rcx, rcx
0x101179a04  jnz     short loc_101179A13
0x101179a06  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101179a0c  mov     rcx, [rdi+100h]
0x101179a13  mov     rdi, [rcx+0C88h]
0x101179a1a  mov     rax, cs:__imp_?ex_trans_cexcept_nodump@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; ex_trans_cexcept_nodump(uint,_EXCEPTION_POINTERS *)
0x101179a21  mov     [rcx+0C88h], rax
0x101179a28  mov     [rsp+828h+var_7F8], rdi
0x101179a2d  mov     edx, 1Dh; unsigned __int16
0x101179a32  xor     r13d, r13d
0x101179a35  mov     [rsp+828h+var_800], r13; struct Worker *
0x101179a3a  mov     rax, cs:__imp_?hdl_backout@@YAHHHHHPEAD@Z; hdl_backout(int,int,int,int,char *)
0x101179a41  mov     [rsp+828h+var_808], rax; int (*)(int, int, int, int, char *)
0x101179a46  xor     r9d, r9d; unsigned __int8
0x101179a49  mov     r8b, 5; unsigned __int8
0x101179a4c  lea     rcx, [rsp+828h+var_7E0]; this
0x101179a51  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x101179a56  nop
0x101179a57  lea     rcx, [rsp+828h+var_688]
0x101179a5f  call    cs:__imp_??0CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::CAutoStreamHeader(void)
0x101179a65  nop
0x101179a66  mov     r9, rsi
0x101179a69  lea     r8, aCsession0xP; "CSession @0x%p"
0x101179a70  mov     rdx, rbx
0x101179a73  lea     rcx, [rsp+828h+var_688]
0x101179a7b  call    cs:__imp_?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ; CAutoStreamHeader::Init(CDStream *,char const *,...)
0x101179a81  test    eax, eax
0x101179a83  jnz     short loc_101179AE7
0x101179a85  lea     rcx, [rsp+828h+var_688]
0x101179a8d  call    cs:__imp_??1CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::~CAutoStreamHeader(void)
0x101179a93  nop
0x101179a94  lea     rcx, [rsp+828h+var_7E0]; this
0x101179a99  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x101179a9e  nop
0x101179a9f  mov     rdx, gs:58h
0x101179aa8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101179aaf  mov     ecx, [rax]
0x101179ab1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101179ab8  mov     ebx, [rax]
0x101179aba  add     rbx, [rdx+rcx*8]
0x101179abe  mov     rax, [rbx+100h]
0x101179ac5  test    rax, rax
0x101179ac8  jnz     short loc_101179AD9
0x101179aca  xor     ecx, ecx
0x101179acc  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101179ad2  mov     rax, [rbx+100h]
0x101179ad9  mov     [rax+0C88h], rdi
0x101179ae0  xor     al, al
0x101179ae2  jmp     loc_10117ABEA
0x101179ae7  movsx   r9d, word ptr [rsi+10h]
0x101179aec  lea     r8, aD_5; "%d"
0x101179af3  lea     rdx, aMSessionid; "m_sessionId"
0x101179afa  mov     rcx, rbx
0x101179afd  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x101179b03  test    eax, eax
0x101179b05  jnz     short loc_101179B69
0x101179b07  lea     rcx, [rsp+828h+var_688]
0x101179b0f  call    cs:__imp_??1CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::~CAutoStreamHeader(void)
0x101179b15  nop
0x101179b16  lea     rcx, [rsp+828h+var_7E0]; this
0x101179b1b  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x101179b20  nop
0x101179b21  mov     rdx, gs:58h
0x101179b2a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101179b31  mov     ecx, [rax]
0x101179b33  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101179b3a  mov     ebx, [rax]
0x101179b3c  add     rbx, [rdx+rcx*8]
0x101179b40  mov     rax, [rbx+100h]
0x101179b47  test    rax, rax
0x101179b4a  jnz     short loc_101179B5B
0x101179b4c  xor     ecx, ecx
0x101179b4e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101179b54  mov     rax, [rbx+100h]
0x101179b5b  mov     [rax+0C88h], rdi
0x101179b62  xor     al, al
0x101179b64  jmp     loc_10117ABEA
0x101179b69  mov     r9d, [rsi+8]
0x101179b6d  lea     r8, aLd_0; "%ld"
0x101179b74  lea     rdx, aMCref; "m_cRef"
0x101179b7b  mov     rcx, rbx
0x101179b7e  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x101179b84  test    eax, eax
0x101179b86  jnz     short loc_101179BEA
0x101179b88  lea     rcx, [rsp+828h+var_688]
0x101179b90  call    cs:__imp_??1CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::~CAutoStreamHeader(void)
0x101179b96  nop
0x101179b97  lea     rcx, [rsp+828h+var_7E0]; this
0x101179b9c  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x101179ba1  nop
0x101179ba2  mov     rdx, gs:58h
0x101179bab  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101179bb2  mov     ecx, [rax]
0x101179bb4  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101179bbb  mov     ebx, [rax]
0x101179bbd  add     rbx, [rdx+rcx*8]
0x101179bc1  mov     rax, [rbx+100h]
0x101179bc8  test    rax, rax
0x101179bcb  jnz     short loc_101179BDC
0x101179bcd  xor     ecx, ecx
0x101179bcf  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101179bd5  mov     rax, [rbx+100h]
0x101179bdc  mov     [rax+0C88h], rdi
0x101179be3  xor     al, al
0x101179be5  jmp     loc_10117ABEA
0x101179bea  mov     edi, r13d
0x101179bed  mov     [rsp+828h+var_7B8], r13d
0x101179bf2  mov     rcx, rbx
0x101179bf5  cmp     edi, 6
0x101179bf8  jge     loc_101179CE4
0x101179bfe  movsd   xmm0, qword ptr cs:aMRgcreftypeX; "m_rgcRefType[X]"
0x101179c06  movsd   [rsp+828h+var_478], xmm0
0x101179c0f  mov     eax, dword ptr cs:aMRgcreftypeX+8; "Type[X]"
0x101179c15  mov     [rsp+828h+var_470], eax
0x101179c1c  movzx   eax, word ptr cs:aMRgcreftypeX+0Ch; "[X]"
0x101179c23  mov     [rsp+828h+var_46C], ax
0x101179c2b  movzx   eax, byte ptr cs:aMRgcreftypeX+0Eh; "]"
0x101179c32  mov     [rsp+828h+var_46A], al
0x101179c39  mov     [rsp+828h+var_46A+1], 0
0x101179c41  lea     eax, [rdi+30h]
0x101179c44  mov     byte ptr [rsp+828h+var_46C+1], al
0x101179c4b  movsxd  rax, edi
0x101179c4e  mov     r9d, [rsi+rax*4+2Ch]
0x101179c53  mov     [rsp+828h+var_748], r9d
0x101179c5b  lea     r8, aLd_0; "%ld"
0x101179c62  lea     rdx, [rsp+828h+var_478]
0x101179c6a  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x101179c70  test    eax, eax
0x101179c72  jnz     short loc_101179CD9
0x101179c74  lea     rcx, [rsp+828h+var_688]
0x101179c7c  call    cs:__imp_??1CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::~CAutoStreamHeader(void)
0x101179c82  nop
0x101179c83  lea     rcx, [rsp+828h+var_7E0]; this
0x101179c88  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x101179c8d  nop
0x101179c8e  mov     rdx, gs:58h
0x101179c97  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101179c9e  mov     ecx, [rax]
0x101179ca0  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101179ca7  mov     ebx, [rax]
0x101179ca9  add     rbx, [rdx+rcx*8]
0x101179cad  mov     rcx, [rbx+100h]
0x101179cb4  test    rcx, rcx
0x101179cb7  jnz     short loc_101179CC6
0x101179cb9  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101179cbf  mov     rcx, [rbx+100h]
0x101179cc6  mov     rax, [rsp+828h+var_7F8]
0x101179ccb  mov     [rcx+0C88h], rax
0x101179cd2  xor     al, al
0x101179cd4  jmp     loc_10117ABEA
0x101179cd9  inc     edi
0x101179cdb  mov     [rsp+828h+var_7B8], edi
0x101179cdf  jmp     loc_101179BF2
0x101179ce4  mov     r9, [rsi+58h]
0x101179ce8  lea     r8, a0xP_1; "0x%p"
0x101179cef  lea     rdx, aMPmo; "m_pmo"
0x101179cf6  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x101179cfc  test    eax, eax
0x101179cfe  jnz     short loc_101179D65
0x101179d00  lea     rcx, [rsp+828h+var_688]
0x101179d08  call    cs:__imp_??1CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::~CAutoStreamHeader(void)
0x101179d0e  nop
0x101179d0f  lea     rcx, [rsp+828h+var_7E0]; this
0x101179d14  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x101179d19  nop
0x101179d1a  mov     rdx, gs:58h
0x101179d23  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101179d2a  mov     ecx, [rax]
0x101179d2c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101179d33  mov     ebx, [rax]
0x101179d35  add     rbx, [rdx+rcx*8]
0x101179d39  mov     rcx, [rbx+100h]
0x101179d40  test    rcx, rcx
0x101179d43  jnz     short loc_101179D52
0x101179d45  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101179d4b  mov     rcx, [rbx+100h]
0x101179d52  mov     rax, [rsp+828h+var_7F8]
0x101179d57  mov     [rcx+0C88h], rax
0x101179d5e  xor     al, al
0x101179d60  jmp     loc_10117ABEA
0x101179d65  mov     r9, [rsi+0E8h]
0x101179d6c  lea     r8, a0xP_1; "0x%p"
0x101179d73  lea     rdx, aMPstackbhfpool; "m_pstackBhfPool"
0x101179d7a  mov     rcx, rbx
0x101179d7d  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x101179d83  test    eax, eax
0x101179d85  jnz     short loc_101179DEC
0x101179d87  lea     rcx, [rsp+828h+var_688]
0x101179d8f  call    cs:__imp_??1CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::~CAutoStreamHeader(void)
0x101179d95  nop
0x101179d96  lea     rcx, [rsp+828h+var_7E0]; this
0x101179d9b  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x101179da0  nop
0x101179da1  mov     rdx, gs:58h
0x101179daa  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101179db1  mov     ecx, [rax]
0x101179db3  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101179dba  mov     ebx, [rax]
0x101179dbc  add     rbx, [rdx+rcx*8]
0x101179dc0  mov     rcx, [rbx+100h]
0x101179dc7  test    rcx, rcx
0x101179dca  jnz     short loc_101179DD9
0x101179dcc  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101179dd2  mov     rcx, [rbx+100h]
0x101179dd9  mov     rax, [rsp+828h+var_7F8]
0x101179dde  mov     [rcx+0C88h], rax
0x101179de5  xor     al, al
0x101179de7  jmp     loc_10117ABEA
0x101179dec  mov     r9d, [rsi+190h]
0x101179df3  lea     r8, a0x04x; "0x%04x"
0x101179dfa  lea     rdx, aMDwloginflags; "m_dwLoginFlags"
0x101179e01  mov     rcx, rbx
0x101179e04  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x101179e0a  test    eax, eax
0x101179e0c  jnz     short loc_101179E73
0x101179e0e  lea     rcx, [rsp+828h+var_688]
0x101179e16  call    cs:__imp_??1CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::~CAutoStreamHeader(void)
0x101179e1c  nop
0x101179e1d  lea     rcx, [rsp+828h+var_7E0]; this
0x101179e22  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x101179e27  nop
0x101179e28  mov     rdx, gs:58h
0x101179e31  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101179e38  mov     ecx, [rax]
0x101179e3a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101179e41  mov     ebx, [rax]
0x101179e43  add     rbx, [rdx+rcx*8]
0x101179e47  mov     rcx, [rbx+100h]
0x101179e4e  test    rcx, rcx
0x101179e51  jnz     short loc_101179E60
0x101179e53  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101179e59  mov     rcx, [rbx+100h]
0x101179e60  mov     rax, [rsp+828h+var_7F8]
0x101179e65  mov     [rcx+0C88h], rax
0x101179e6c  xor     al, al
0x101179e6e  jmp     loc_10117ABEA
0x101179e73  movzx   r9d, byte ptr [rsi+10Dh]
0x101179e7b  and     r9d, 1
0x101179e7f  lea     r8, aD_5; "%d"
0x101179e86  lea     rdx, aMFbackground; "m_fBackground"
0x101179e8d  mov     rcx, rbx
0x101179e90  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x101179e96  test    eax, eax
0x101179e98  jnz     short loc_101179EFF
0x101179e9a  lea     rcx, [rsp+828h+var_688]
0x101179ea2  call    cs:__imp_??1CAutoStreamHeader@@QEAA@XZ; CAutoStreamHeader::~CAutoStreamHeader(void)
0x101179ea8  nop
0x101179ea9  lea     rcx, [rsp+828h+var_7E0]; this
0x101179eae  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x101179eb3  nop
0x101179eb4  mov     rdx, gs:58h
0x101179ebd  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101179ec4  mov     ecx, [rax]
0x101179ec6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101179ecd  mov     ebx, [rax]
0x101179ecf  add     rbx, [rdx+rcx*8]
0x101179ed3  mov     rcx, [rbx+100h]
0x101179eda  test    rcx, rcx
0x101179edd  jnz     short loc_101179EEC
0x101179edf  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101179ee5  mov     rcx, [rbx+100h]
0x101179eec  mov     rax, [rsp+828h+var_7F8]
0x101179ef1  mov     [rcx+0C88h], rax
0x101179ef8  xor     al, al
0x101179efa  jmp     loc_10117ABEA
0x101179eff  mov     r9d, [rsi+104h]
0x101179f06  lea     r8, aD_5; "%d"
0x101179f0d  lea     rdx, aMEconnresetopt; "m_eConnResetOption"
0x101179f14  mov     rcx, rbx
0x101179f17  call    cs:__imp_?Write@CDStream@@QEAAHPEBD0ZZ; CDStream::Write(char const *,char const *,...)
0x101179f1d  test    eax, eax
0x101179f1f  jnz     short loc_101179F86
0x101179f21  lea     rcx, [rsp+828h+var_688]
  ... truncated ...
```
