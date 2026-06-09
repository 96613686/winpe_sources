# CMemo::OptimizeQuery(COptExpr *,CContextProperties const *,bool,bool)

- ea: `0x1004e4e00`
- end: `0x1004e5ad6`
- name: `?OptimizeQuery@CMemo@@QEAAPEAVCOptExpr@@PEAV2@PEBVCContextProperties@@_N2@Z`
- size: `3286`
- prototype: `struct COptExpr *__usercall@<rax>(CMemo *__hidden this@<rcx>, struct COptExpr *@<rdx>, const struct CContextProperties *@<r8>, bool@<r9b>, bool)`
- caller_count: `1`
- callee_count: `38`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1004e7b70`

## callees

- `0x100409440`
- `0x10040bea0`
- `0x10040c110`
- `0x100440350`
- `0x10045cb40`
- `0x10046b3f0`
- `0x10046e5d0`
- `0x1004782b0`
- `0x10047c540`
- `0x1004868d0`
- `0x100499100`
- `0x1004c4f80`
- `0x1004e2edf`
- `0x1004e4e00`
- `0x1004e5ae0`
- `0x1004e5f50`
- `0x1004e6e30`
- `0x1004e76a0`
- `0x1004e7c70`
- `0x1004e84c0`
- `0x1004ea700`
- `0x1004ea940`
- `0x1004ef260`
- `0x1004f0020`
- `0x1005765b0`
- `0x1006d32f0`
- `0x100a26ef0`
- `0x100aac440`
- `0x100aac570`
- `0x1019b8300`
- `0x101b55f00`
- `0x101c08b00`
- `0x101ca23c0`
- `0x101ca63f0`
- `0x101ca7a60`
- `0x101cabf60`
- `0x101cc6300`
- `0x101cc7ba0`

## import_xrefs

- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1004e5566`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x10057a1ec`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10057a1e5`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad4f7`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad55b`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad5dd`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad66f`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad6aa`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad705`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad755`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad7d1`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad872`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad8ae`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cadd0f`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad4f7`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad55b`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad5dd`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad66f`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad6aa`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad705`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad755`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad7d1`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad872`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cad8ae`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x101cadd0f`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad50a`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad56e`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad5ed`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad616`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad63f`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad682`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad6ba`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad715`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad765`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad7e1`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad80a`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad830`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad882`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad8be`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cadd22`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cadd51`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cadd7d`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101caddac`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad50a`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad56e`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad5ed`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad616`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad63f`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad682`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad6ba`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad715`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad765`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad7e1`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad80a`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad830`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad882`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad8be`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cadd22`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cadd51`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cadd7d`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101caddac`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad537`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad590`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad609`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad632`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad653`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad731`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad784`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad7fd`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad823`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad844`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cadd41`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cadd6d`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cadd9c`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101caddc3`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad537`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad590`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad609`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad632`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad653`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad731`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad784`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad7fd`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad823`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cad844`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cadd41`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cadd6d`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101cadd9c`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x101caddc3`
- `sqldk!??1TraceStreamHolder@@QEAA@XZ` at `0x101cad65e`
- `sqldk!??1TraceStreamHolder@@QEAA@XZ` at `0x101cad84f`
- `sqldk!??1TraceStreamHolder@@QEAA@XZ` at `0x101caddce`
- `sqldk!??1TraceStreamHolder@@QEAA@XZ` at `0x101cad65e`
- `sqldk!??1TraceStreamHolder@@QEAA@XZ` at `0x101cad84f`
- `sqldk!??1TraceStreamHolder@@QEAA@XZ` at `0x101caddce`
- `sqldk!??0TraceStreamHolder@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad4ec`
- `sqldk!??0TraceStreamHolder@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad6fa`
- `sqldk!??0TraceStreamHolder@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cadd04`
- `sqldk!??0TraceStreamHolder@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad4ec`
- `sqldk!??0TraceStreamHolder@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cad6fa`
- `sqldk!??0TraceStreamHolder@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x101cadd04`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004e4f22`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004e4f8d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004e503a`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004e50e9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004e533e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100576534`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101cadf61`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101cadfcf`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101cae04c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004e4f22`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004e4f8d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004e503a`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004e50e9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004e533e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100576534`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101cadf61`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101cadfcf`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101cae04c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101cad0de`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101cad162`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101cade10`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101cad0de`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101cad162`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101cade10`
- `sqldk!SystemThread_TlsIndex` at `0x1004e4e81`
- `sqldk!SystemThread_TlsIndex` at `0x1004e4fd7`
- `sqldk!SystemThread_TlsIndex` at `0x1004e5763`
- `sqldk!SystemThread_TlsIndex` at `0x1004e57e1`
- `sqldk!SystemThread_TlsIndex` at `0x1004e58ae`
- `sqldk!SystemThread_TlsIndex` at `0x101cad2f4`
- `sqldk!SystemThread_TlsIndex` at `0x101cad39d`
- `sqldk!SystemThread_TlsIndex` at `0x101cad446`
- `sqldk!SystemThread_TlsIndex` at `0x101cad59f`
- `sqldk!SystemThread_TlsIndex` at `0x101cad793`
- `sqldk!SystemThread_TlsIndex` at `0x101cada28`
- `sqldk!SystemThread_TlsIndex` at `0x101cadaf4`
- `sqldk!SystemThread_TlsIndex` at `0x101cadbc0`
- `sqldk!SystemThread_TlsIndex` at `0x101cadc7f`
- `sqldk!SystemThread_TlsOffset` at `0x1004e4e8a`
- `sqldk!SystemThread_TlsOffset` at `0x1004e4fe0`
- `sqldk!SystemThread_TlsOffset` at `0x1004e576c`
- `sqldk!SystemThread_TlsOffset` at `0x1004e57ea`
- `sqldk!SystemThread_TlsOffset` at `0x1004e58b7`
- `sqldk!SystemThread_TlsOffset` at `0x101cad2fd`
- `sqldk!SystemThread_TlsOffset` at `0x101cad3a6`
- `sqldk!SystemThread_TlsOffset` at `0x101cad44f`
- `sqldk!SystemThread_TlsOffset` at `0x101cad5a8`
- `sqldk!SystemThread_TlsOffset` at `0x101cad79c`
- `sqldk!SystemThread_TlsOffset` at `0x101cada31`
- `sqldk!SystemThread_TlsOffset` at `0x101cadafd`
- `sqldk!SystemThread_TlsOffset` at `0x101cadbc9`
- `sqldk!SystemThread_TlsOffset` at `0x101cadc88`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1004e5a76`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cae0e8`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cae112`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cae139`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cae212`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cae242`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1004e5a76`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cae0e8`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cae112`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cae139`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cae212`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101cae242`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101cad318`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101cad3c1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101cad46a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101cada4c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101cadb18`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101cadbe4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101cad318`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101cad3c1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101cad46a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101cada4c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101cadb18`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101cadbe4`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cad4d3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cad6e1`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cadceb`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cad4d3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cad6e1`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101cadceb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004e52fe`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004e52fe`
- `MSVCP140!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_J@Z` at `0x101cad627`
- `MSVCP140!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_J@Z` at `0x101cad818`
- `MSVCP140!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_J@Z` at `0x101cad627`
- `MSVCP140!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_J@Z` at `0x101cad818`
- `MSVCP140!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z` at `0x101cadd5f`
- `MSVCP140!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z` at `0x101cadd5f`
- `api-ms-win-crt-math-l1-1-0!log1p` at `0x1004e5482`
- `api-ms-win-crt-math-l1-1-0!log1p` at `0x1004e549a`
- `api-ms-win-crt-math-l1-1-0!log1p` at `0x1004e54b2`
- `api-ms-win-crt-math-l1-1-0!log1p` at `0x1004e54ca`
- `api-ms-win-crt-math-l1-1-0!log1p` at `0x1004e54e1`
- `api-ms-win-crt-math-l1-1-0!log1p` at `0x1004e54f9`
- `api-ms-win-crt-math-l1-1-0!log1p` at `0x1004e5482`
- `api-ms-win-crt-math-l1-1-0!log1p` at `0x1004e549a`
- `api-ms-win-crt-math-l1-1-0!log1p` at `0x1004e54b2`

## string_xrefs

- `0x1004e5588`: `OptReplayPreHeuristicsTimeThreshold`

## pseudocode

```c
// Hidden C++ exception states: #wind=64
struct COptExpr *__fastcall CMemo::OptimizeQuery(
        CMemo *this,
        struct COptExpr *a2,
        const struct CContextProperties *a3,
        unsigned __int8 a4,
        bool a5)
{
  const struct CContextProperties *v5; // r12
  struct COptExpr *v6; // rsi
  struct IMemObj *v8; // r15
  __int64 v9; // rcx
  __int64 v10; // rax
  _QWORD *v11; // rcx
  const struct COptCostGoal *v12; // rax
  const struct COptCostGoal *v13; // rdi
  __int64 v14; // xmm0_8
  __int64 v15; // rcx
  __int64 v16; // rax
  _DWORD *v17; // rbx
  __int64 v18; // r8
  __int64 v19; // r8
  struct IMemObj *v20; // rdi
  __int64 v21; // rax
  __int64 v22; // rax
  int v23; // ecx
  bool v24; // zf
  __int64 v25; // rcx
  _DWORD *ObjectDataImpl; // rbx
  unsigned int i; // ebx
  __int64 v28; // rax
  __int64 v29; // rbx
  __int64 v30; // rdx
  __int64 v31; // r15
  _DWORD *v32; // rax
  _DWORD *v33; // r8
  __int64 v34; // rcx
  double v35; // xmm6_8
  int v36; // r13d
  int v37; // r9d
  int v38; // ebx
  __int64 v39; // r8
  __int64 v40; // rcx
  __int64 v41; // rcx
  int v42; // eax
  bool v43; // dl
  unsigned int v44; // ecx
  double *v45; // rbx
  double v46; // xmm10_8
  double v47; // xmm9_8
  double v48; // xmm8_8
  double v49; // xmm7_8
  double v50; // xmm6_8
  double v51; // xmm0_8
  double v52; // xmm6_8
  __int64 v53; // rdi
  __int64 v54; // rcx
  __int64 v55; // rax
  __int64 v56; // r15
  struct CTableGroupProperties *v57; // r13
  __int64 v58; // rbx
  struct COptExpr *v59; // rdx
  _DWORD *v60; // rbx
  struct CTableGroupProperties *v61; // r9
  struct IMemObj *v62; // r13
  __int64 v63; // rax
  __int64 v64; // rcx
  int v65; // r15d
  unsigned __int64 v66; // r13
  struct CTableGroupProperties *v67; // rbx
  struct CSrchStratQuickPlanExclusiveBatch *v68; // r12
  __int64 v69; // rbx
  __int64 v70; // rdx
  struct CSessionTraceFlags *v71; // rcx
  bool v72; // di
  unsigned __int8 v73; // si
  struct CPlanPersReqd *v74; // rbx
  __int64 v75; // rax
  struct CSessionTraceFlags *v76; // rcx
  __int64 v77; // rbx
  __int64 v78; // rcx
  __int64 v79; // rax
  struct CSessionTraceFlags *v80; // rcx
  __int64 v81; // r10
  __int64 v82; // rax
  __int64 v83; // rdi
  __int64 v84; // rbx
  __int64 v85; // rdx
  int v86; // r15d
  __int64 v87; // rax
  struct COptExpr *v88; // rdi
  __int64 v89; // rdx
  double v90; // xmm0_8
  __int64 v91; // rcx
  _QWORD *v92; // rdx
  __int64 v93; // rcx
  const struct COptCostGoal *v94; // rbx
  __int64 v95; // rcx
  struct CPlanPersReqd *v96; // rcx
  bool v98; // al
  __int64 v99; // rbx
  bool v100; // al
  CIndexesMaintainedSeparately *v101; // rax
  CIndexesMaintainedSeparately *v102; // rbx
  __int64 v103; // rax
  int *v104; // rax
  __int64 v105; // rax
  unsigned __int64 v106; // r9
  __int64 v107; // rdx
  bool v108; // al
  unsigned __int64 v109; // rdx
  unsigned __int64 v110; // rdx
  unsigned __int64 v111; // rdx
  __int64 v112; // rax
  __int64 v113; // r8
  __int64 v114; // rdx
  unsigned int v115; // ecx
  unsigned int v116; // eax
  _DWORD *v117; // rdx
  __int64 v118; // rax
  void (__fastcall ***v119)(_QWORD, __int64); // rcx
  __int64 v120; // rdi
  _QWORD *v121; // r9
  __int64 v122; // rax
  unsigned __int64 v123; // rax
  unsigned __int64 v124; // rdx
  __int64 v125; // rcx
  __int64 v126; // rdi
  _QWORD *v127; // r9
  __int64 v128; // rax
  unsigned __int64 v129; // rax
  unsigned __int64 v130; // rdx
  __int64 v131; // rcx
  __int64 v132; // rdi
  _QWORD *v133; // r9
  __int64 v134; // rax
  unsigned __int64 v135; // rax
  unsigned __int64 v136; // rdx
  __int64 v137; // rcx
  struct SOS_TraceStream *Stream; // rbx
  struct SOS_TraceStream *v139; // rbx
  TraceStreamProtector *v140; // rcx
  __int64 v141; // rcx
  __int64 v142; // rax
  __int64 v143; // rdi
  struct SOS_TraceStream *v144; // rsi
  struct SOS_TraceStream *v145; // rbx
  struct SOS_TraceStream *v146; // rbx
  struct SOS_TraceStream *v147; // rbx
  struct SOS_TraceStream *v148; // rbx
  TraceStreamProtector *v149; // rcx
  __int64 v150; // rcx
  __int64 v151; // rax
  __int64 v152; // rdi
  struct SOS_TraceStream *v153; // rsi
  struct SOS_TraceStream *v154; // rbx
  struct SOS_TraceStream *v155; // rbx
  __int64 v156; // rax
  double v157; // xmm0_8
  __int64 v158; // rcx
  _QWORD *v159; // rax
  __int64 v160; // rax
  __int64 v161; // r10
  __int64 v162; // rdi
  _QWORD *v163; // r9
  __int64 v164; // rcx
  __int64 v165; // rax
  unsigned __int64 v166; // rax
  unsigned __int64 v167; // rax
  unsigned __int64 v168; // rdx
  __int64 v169; // r10
  __int64 v170; // rdi
  _QWORD *v171; // r9
  __int64 v172; // rcx
  __int64 v173; // rax
  unsigned __int64 v174; // rax
  unsigned __int64 v175; // rax
  unsigned __int64 v176; // rdx
  __int64 v177; // r10
  __int64 v178; // rdi
  _QWORD *v179; // r9
  __int64 v180; // rcx
  __int64 v181; // rax
  unsigned __int64 v182; // rax
  unsigned __int64 v183; // rax
  unsigned __int64 v184; // rdx
  struct SOS_TraceStream *v185; // rdi
  __int64 *v186; // rax
  int v187; // ecx
  __int64 v188; // rax
  struct IMemObj *v189; // rsi
  struct IMemObj *v190; // rbx
  __int64 v191; // rax
  struct IMemObj *v192; // rdi
  __int64 v193; // rax
  void *v194; // rbx
  void *v195; // rbx
  int v196; // [rsp+28h] [rbp-E0h]
  int v197[2]; // [rsp+28h] [rbp-E0h]
  int v198[2]; // [rsp+28h] [rbp-E0h]
  __int64 *v199; // [rsp+30h] [rbp-D8h]
  __int64 v200; // [rsp+60h] [rbp-A8h]
  bool v201[8]; // [rsp+78h] [rbp-90h] BYREF
  struct CPlanPersReqd *v202; // [rsp+80h] [rbp-88h]
  struct IMemObj *v203; // [rsp+88h] [rbp-80h] BYREF
  int v204; // [rsp+90h] [rbp-78h] BYREF
  struct IMemObj *v205; // [rsp+98h] [rbp-70h]
  char v206[8]; // [rsp+A0h] [rbp-68h] BYREF
  char v207[8]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v208; // [rsp+B0h] [rbp-58h] BYREF
  struct IMemObj *v209; // [rsp+B8h] [rbp-50h]
  struct CTableGroupProperties *v210; // [rsp+C0h] [rbp-48h]
  char v211[8]; // [rsp+C8h] [rbp-40h] BYREF
  void (__fastcall ***v212)(_QWORD, __int64); // [rsp+D0h] [rbp-38h]
  const struct COptCostGoal *v213; // [rsp+D8h] [rbp-30h]
  void **v214; // [rsp+E0h] [rbp-28h] BYREF
  int v215; // [rsp+E8h] [rbp-20h]
  int v216; // [rsp+F0h] [rbp-18h]
  __int64 v217; // [rsp+F8h] [rbp-10h]
  __int64 v218; // [rsp+100h] [rbp-8h] BYREF
  unsigned __int16 v219; // [rsp+108h] [rbp+0h]
  int v220; // [rsp+10Ch] [rbp+4h]
  __int64 v221; // [rsp+110h] [rbp+8h]
  __int64 v222; // [rsp+118h] [rbp+10h]
  int v223; // [rsp+120h] [rbp+18h]
  char v224[8]; // [rsp+128h] [rbp+20h] BYREF
  char v225[8]; // [rsp+130h] [rbp+28h] BYREF
  char v226[8]; // [rsp+138h] [rbp+30h] BYREF
  char v227[8]; // [rsp+140h] [rbp+38h] BYREF
  char v228[8]; // [rsp+148h] [rbp+40h] BYREF
  char v229[8]; // [rsp+150h] [rbp+48h] BYREF
  char v230[8]; // [rsp+158h] [rbp+50h] BYREF
  char v231[8]; // [rsp+160h] [rbp+58h] BYREF
  char v232[8]; // [rsp+168h] [rbp+60h] BYREF
  char v233[8]; // [rsp+170h] [rbp+68h] BYREF
  char v234[8]; // [rsp+178h] [rbp+70h] BYREF
  __int64 v235; // [rsp+180h] [rbp+78h] BYREF
  __int64 v236; // [rsp+188h] [rbp+80h] BYREF
  __int64 v237; // [rsp+190h] [rbp+88h] BYREF
  double v238; // [rsp+198h] [rbp+90h] BYREF
  __int64 v239; // [rsp+1A0h] [rbp+98h] BYREF
  char v240[8]; // [rsp+1A8h] [rbp+A0h] BYREF
  char v241[8]; // [rsp+1B0h] [rbp+A8h] BYREF
  char v242[8]; // [rsp+1B8h] [rbp+B0h] BYREF
  char v243[8]; // [rsp+1C0h] [rbp+B8h] BYREF
  __int64 v244; // [rsp+1C8h] [rbp+C0h] BYREF
  __int64 v245; // [rsp+1D0h] [rbp+C8h] BYREF
  struct SSeparateIndex *v246; // [rsp+1D8h] [rbp+D0h] BYREF
  double v247; // [rsp+1E0h] [rbp+D8h] BYREF
  char v248[8]; // [rsp+1E8h] [rbp+E0h] BYREF
  char v249[8]; // [rsp+1F0h] [rbp+E8h] BYREF
  char v250[8]; // [rsp+1F8h] [rbp+F0h] BYREF
  __int64 v251; // [rsp+200h] [rbp+F8h] BYREF
  int v252; // [rsp+20Ch] [rbp+104h]
  void *v253; // [rsp+210h] [rbp+108h]
  __int64 v254; // [rsp+218h] [rbp+110h]
  int v255; // [rsp+220h] [rbp+118h]
  __m128d v256; // [rsp+228h] [rbp+120h] BYREF
  struct CFSMetaDataNode *v257[2]; // [rsp+238h] [rbp+130h] BYREF
  __int128 v258; // [rsp+248h] [rbp+140h]
  void (__fastcall ***v259)(_QWORD, __int64); // [rsp+258h] [rbp+150h]
  __int64 v260; // [rsp+260h] [rbp+158h]
  int v261; // [rsp+268h] [rbp+160h]
  __int64 v262; // [rsp+270h] [rbp+168h]
  __int128 v263; // [rsp+278h] [rbp+170h]
  __int64 v264; // [rsp+288h] [rbp+180h]
  __int64 v265; // [rsp+290h] [rbp+188h]
  int v266; // [rsp+298h] [rbp+190h]
  char v267; // [rsp+29Ch] [rbp+194h]
  __int64 v268; // [rsp+2A8h] [rbp+1A0h] BYREF
  __int64 v269; // [rsp+2B8h] [rbp+1B0h]
  struct IMemObj *v270; // [rsp+2C0h] [rbp+1B8h]
  __int64 v271; // [rsp+2C8h] [rbp+1C0h]
  struct IMemObj *v272; // [rsp+2D0h] [rbp+1C8h]
  struct IMemObj *v273; // [rsp+2D8h] [rbp+1D0h]
  char v274[8]; // [rsp+2E8h] [rbp+1E0h] BYREF
  int v275; // [rsp+2F0h] [rbp+1E8h]
  int v276; // [rsp+2F8h] [rbp+1F0h]
  _QWORD *v277; // [rsp+300h] [rbp+1F8h]
  char *v278; // [rsp+308h] [rbp+200h]
  __int64 v279; // [rsp+310h] [rbp+208h]
  _QWORD v280[2]; // [rsp+318h] [rbp+210h] BYREF
  char v281; // [rsp+328h] [rbp+220h] BYREF
  __int64 v282; // [rsp+538h] [rbp+430h]
  __int64 v283; // [rsp+540h] [rbp+438h]
  _BYTE v284[3]; // [rsp+548h] [rbp+440h] BYREF
  __int64 v285; // [rsp+54Bh] [rbp+443h]
  unsigned __int64 v286; // [rsp+553h] [rbp+44Bh]
  unsigned __int64 v287; // [rsp+55Bh] [rbp+453h]

  v271 = -2;
  v5 = a3;
  v6 = a2;
  v8 = *(struct IMemObj **)(*((_QWORD *)this + 10) + 32LL);
  v209 = v8;
  v205 = v8;
  v257[0] = 0;
  v9 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL)
                 + 72LL);
  v10 = v9 + 24;
  if ( !v9 )
    v10 = 32;
  v257[1] = *(struct CFSMetaDataNode **)v10;
  v258 = 0;
  v260 = 0;
  v261 = 0;
  v262 = 0;
  v263 = 0;
  v264 = 0;
  v265 = 0;
  v266 = 0;
  v267 = 0;
  *(_DWORD *)&v201[4] = 6139;
  v11 = operator new(0x10u, v8, "sql\\ntdbms\\query\\qeoptim\\engine\\memo.cpp", 6139, 1u);
  v212 = (void (__fastcall ***)(_QWORD, __int64))v11;
  v203 = (struct IMemObj *)v11;
  if ( v11 )
  {
    *v11 = &CTaskList::`vftable';
    v11[1] = 0;
  }
  else
  {
    v11 = 0;
    v212 = 0;
  }
  *(_QWORD *)(*((_QWORD *)this + 10) + 336LL) = v11;
  v256 = _mm_unpacklo_pd((__m128d)*(unsigned __int64 *)&x_cuMax, (__m128d)*(unsigned __int64 *)&x_cuMax);
  *(_DWORD *)&v201[4] = 6151;
  v12 = (const struct COptCostGoal *)operator new(0x38u, v8, "sql\\ntdbms\\query\\qeoptim\\engine\\memo.cpp", 6151, 1u);
  v13 = v12;
  v213 = v12;
  v203 = v12;
  if ( v12 )
  {
    v14 = *(_QWORD *)(*((_QWORD *)this + 10) + 224LL);
    *(_QWORD *)v12 = 0;
    *((_QWORD *)v12 + 1) = 0;
    *((_QWORD *)v12 + 2) = 0;
    *((_BYTE *)v12 + 24) = 0;
    *((_QWORD *)v12 + 4) = 0;
    *((_QWORD *)v12 + 5) = 0;
    *((_QWORD *)v12 + 6) = 0;
    v15 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset
                                + 8LL)
                    + 72LL);
    v16 = v15 + 168;
    if ( !v15 )
      v16 = 176;
    if ( *(char *)v16 < 0 )
      *(_QWORD *)v13 = 0;
    else
      *(_QWORD *)v13 = v14;
  }
  else
  {
    v13 = 0;
    v213 = 0;
  }
  *(_DWORD *)&v201[4] = 6153;
  v17 = operator new(0x70u, v8, "sql\\ntdbms\\query\\qeoptim\\engine\\memo.cpp", 6153, 1u);
  v203 = (struct IMemObj *)v17;
  if ( v17 )
  {
    v18 = *(_QWORD *)(*((_QWORD *)this + 10) + 312LL);
    *(_QWORD *)v17 = &CRefCount::`vftable';
    v17[2] = 1;
    *(_QWORD *)v17 = &COptCostContext::`vftable';
    COptCostVector::CuMultiplyByWeight(&v256, v17 + 4, v18);
    *((_QWORD *)v17 + 3) = v19;
    COptCostGoal::COptCostGoal((COptCostGoal *)(v17 + 8), v13);
    *((_QWORD *)v17 + 11) = x_cardIllegal;
    *((_QWORD *)v17 + 12) = x_cardIllegal;
    *((_QWORD *)v17 + 13) = x_cardIllegal;
    ++COptCostContext::m_count;
  }
  else
  {
    v17 = 0;
  }
  *(_DWORD *)&v201[4] = 6154;
  v20 = (struct IMemObj *)operator new(0x48u, v8, "sql\\ntdbms\\query\\qeoptim\\engine\\memo.cpp", 6154, 1u);
  v203 = v20;
  if ( v20 )
  {
    v21 = *((_QWORD *)this + 10);
    *(_QWORD *)v20 = &CRefCount::`vftable';
    *((_DWORD *)v20 + 2) = 1;
    *(_QWORD *)v20 = &CTaskContext::`vftable';
    *((_QWORD *)v20 + 2) = v21;
    *((_QWORD *)v20 + 3) = 0;
    *((_QWORD *)v20 + 4) = 0;
    *((double *)v20 + 5) = x_cuMax;
    *((_QWORD *)v20 + 6) = 0;
    *((_WORD *)v20 + 28) = 0;
    *((_DWORD *)v20 + 15) = 0;
    ++CTaskContext::m_count;
    *((_QWORD *)v20 + 4) = 0;
    *((_QWORD *)v20 + 3) = v17;
    if ( v17 )
      ++v17[2];
    v22 = *(_QWORD *)(v21 + 304);
    if ( v22 )
      v23 = *(_DWORD *)(v22 + 244);
    else
      v23 = 0;
    *((_DWORD *)v20 + 16) = v23;
    *((_DWORD *)v20 + 17) = 0;
  }
  else
  {
    v20 = 0;
  }
  v24 = v17[2]-- == 1;
  if ( v24 )
    (**(void (__fastcall ***)(void *, __int64))v17)(v17, 1);
  if ( SOS_Task::GetStackAvailableBytes() < 0x18000 )
    ex_raise(86, 21, 17, 2);
  ObjectDataImpl = PerCPUDataImpl::GetObjectDataImpl((PerCPUDataImpl *)&OptimizerUtil::m_perCpuCounters);
  if ( ++*ObjectDataImpl >= 0xAu )
  {
    LOBYTE(v25) = 124;
    OptimizerUtil::YieldAndCheckForMemoryAndAbort(v25);
    *ObjectDataImpl = 0;
  }
  for ( i = 0; i < *((_DWORD *)v6 + 6); ++i )
    COptExpr::DetachPointersIntoMemo(*(COptExpr **)(*((_QWORD *)v6 + 4) + 8LL * (int)i), 0);
  *((_QWORD *)v6 + 14) = 0;
  v201[0] = 0;
  LODWORD(v200) = 0;
  *(_DWORD *)&v201[4] = *(_DWORD *)CMemo::PgexprInclude(this, v6, v20, -1, 0, 0, -1, 0, 0, 0, v201, v200, 0);
  *((_DWORD *)this + 55) = *(_DWORD *)&v201[4];
  if ( *((_QWORD *)this + 55) )
  {
    v215 = 1;
    v214 = &CFingerprintUtilEx::`vftable';
    v216 = 0;
    v217 = 0;
    CFingerprintUtilEx::GenFingerprintForFirstExpressionInGroup(
      (CFingerprintUtilEx *)&v214,
      this,
      *((_DWORD *)this + 55));
    v112 = *((_QWORD *)this + 55);
    if ( !v112 || *(_BYTE *)(v112 + 32) )
    {
      *(_DWORD *)(v112 + 224) = v217;
    }
    else if ( (_DWORD)v217 != *(_DWORD *)(v112 + 224) )
    {
      ex_raise(86, 75, 16, 70);
    }
    v214 = &CRefCount::`vftable';
  }
  v28 = *((_QWORD *)this + 55);
  if ( v28 )
  {
    if ( *(_DWORD *)(v28 + 144) == -1 )
    {
      *(_DWORD *)(v28 + 144) = *((_DWORD *)this + 26);
      v28 = *((_QWORD *)this + 55);
    }
    *(_BYTE *)(v28 + 425) = 1;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 10) + 1056LL) == 3 )
  {
    v113 = *(_QWORD *)(*((_QWORD *)this + 55) + 432LL);
    v114 = *(_QWORD *)(v113 + 16);
    v115 = *(_DWORD *)(v114 + 76);
    if ( v115 )
    {
      v116 = *(_DWORD *)(v113 + 40) + 1;
      if ( v116 >= v115 )
      {
        v117 = 0;
      }
      else
      {
        _mm_lfence();
        v117 = *(_DWORD **)(*(_QWORD *)(v114 + 88) + 8LL * v116);
      }
      if ( !*v117 )
        COptimizationReplayController::ProcessMergeGroupsRecordInReplayScript(v113, 0);
    }
  }
  v29 = *(_QWORD *)(*((_QWORD *)this + 10) + 728LL);
  if ( v29 )
  {
    (**(void (__fastcall ***)(__int64, __int64))v29)(v29, 0xFFFFFFFFLL);
    v251 = *(_QWORD *)this;
    v252 = 0;
    v253 = 0;
    v254 = 0;
    v255 = 0;
    CTHashTable<PLString *,CFnH_PLString,CFnC_PLString,CFnI_Default<PLString *>,CFnD_Ptr<PLString>,CMemObjAlloc<0>>::Resize(
      &v251,
      100);
    Traverse<COptExpr>(v6, v29, &v251, *(_QWORD *)this);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    CTHashTableBase<Pair<void const *,MatExpressionNode const *>,CTMap<void const *,MatExpressionNode const *,CFnH_Pointer,CFnC_Default<void const *>,CFnI_Default<MatExpressionNode const *>,CFnD_Noop<void const *>,CFnD_Noop<MatExpressionNode const *>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<void const *,MatExpressionNode const *,CFnH_Pointer,CFnC_Default<void const *>,CFnI_Default<MatExpressionNode const *>,CFnD_Noop<void const *>,CFnD_Noop<MatExpressionNode const *>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<void const *,MatExpressionNode const *,CFnH_Pointer,CFnC_Default<void const *>,CFnI_Default<MatExpressionNode const *>,CFnD_Noop<void const *>,CFnD_Noop<MatExpressionNode const *>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<void const *,MatExpressionNode const *,CFnH_Pointer,CFnC_Default<void const *>,CFnI_Default<MatExpressionNode const *>,CFnD_Noop<void const *>,CFnD_Noop<MatExpressionNode const *>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::DestroyBuckets(&v251);
    if ( v253 )
      operator delete[](v253);
  }
  v30 = *((_QWORD *)this + 10);
  v31 = *(_QWORD *)(v30 + 192);
  if ( v31 )
  {
    v205 = *(struct IMemObj **)(v30 + 32);
    v204 = 1213;
    v32 = operator new(0x18u, v205, "sql\\ntdbms\\query\\qeoptim\\engine\\replay.h", 1213, 1u);
    v33 = v32;
    v203 = (struct IMemObj *)v32;
    if ( v32 )
    {
      *(_QWORD *)v32 = -1;
      *((_QWORD *)v32 + 1) = -1;
      v32[4] = -1;
      *((_BYTE *)v32 + 20) = 0;
    }
    else
    {
      v33 = 0;
    }
    *(_QWORD *)v31 = v33;
    v34 = *((_QWORD *)this + 10);
    v35 = *(double *)(*(_QWORD *)(v34 + 904) + 360LL);
    v36 = 0;
    v37 = 0;
    LODWORD(v202) = 0;
    v38 = 0;
    if ( *((int *)this + 26) > 0 )
    {
      do
      {
        v39 = *((_QWORD *)this + 12);
        if ( (unsigned int)(v38 / 256) >= *(_DWORD *)(v39 + 12) )
        {
          v40 = 0;
        }
        else
        {
          _mm_lfence();
          v40 = *(_QWORD *)(*(_QWORD *)(v39 + 24) + 8LL * (unsigned int)(v38 / 256));
        }
        v41 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v40 + 8LL * (unsigned int)(v38 % 256)) + 16LL) + 8LL);
        v42 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 24LL))(v41) - 14;
        switch ( v42 )
        {
          case 0:
          case 2:
          case 3:
          case 4:
          case 5:
          case 6:
          case 7:
          case 8:
            ++v36;
            goto LABEL_39;
          case 1:
            v37 = (_DWORD)v202 + 1;
            LODWORD(v202) = (_DWORD)v202 + 1;
            break;
          default:
LABEL_39:
            v37 = (int)v202;
            break;
        }
        ++v38;
      }
      while ( v38 < *((_DWORD *)this + 26) );
      v34 = *((_QWORD *)this + 10);
      v33 = *(_DWORD **)v31;
      v6 = a2;
    }
    v43 = (*(_BYTE *)(v34 + 107) & 0x10) != 0;
    v44 = *((_DWORD *)this + 67);
    *v33 = (int)v35;
    *(_QWORD *)(*(_QWORD *)v31 + 4LL) = v44;
    *(_DWORD *)(*(_QWORD *)v31 + 12LL) = v36;
    *(_DWORD *)(*(_QWORD *)v31 + 16LL) = v37;
    *(_BYTE *)(*(_QWORD *)v31 + 20LL) = v43;
    v5 = a3;
  }
  v45 = *(double **)(*((_QWORD *)this + 10) + 192LL);
  if ( v45 )
  {
    v46 = log1p((double)**(int **)v45);
    v47 = log1p((double)*(int *)(*(_QWORD *)v45 + 4LL));
    v48 = log1p((double)*(int *)(*(_QWORD *)v45 + 8LL));
    v49 = log1p((double)*(int *)(*(_QWORD *)v45 + 12LL));
    v50 = log1p((double)*(int *)(*(_QWORD *)v45 + 16LL));
    v51 = log1p((double)*(unsigned __int8 *)(*(_QWORD *)v45 + 20LL));
    v45[1] = exp_0(
               v51 * 0.6454299999999999
             + v46 * 1.49343
             - 0.17458
             + v47 * 0.54003
             - v48 * 0.79618
             - v49 * 0.07912
             + v50 * 0.55389);
    v52 = DOUBLE_50_0;
    v204 = -1;
    v199 = 0;
    LOBYTE(v196) = 0;
    if ( (*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int))(*(_QWORD *)s_pServerConf + 520LL))(
           s_pServerConf,
           L"OptimizationReplay",
           L"OptReplayPreHeuristicsTimeThreshold",
           &v204,
           v196)
      && v204 >= 0 )
    {
      v52 = (double)v204;
    }
    if ( v52 >= v45[1] )
    {
      if ( *((_QWORD *)this + 55) )
      {
        v118 = *((_QWORD *)this + 10);
        if ( *(_DWORD *)(v118 + 1056) == 2 )
        {
          *(_DWORD *)(v118 + 1056) = 4;
          v119 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 55);
          if ( v119 )
            (**v119)(v119, 1);
          *((_QWORD *)this + 55) = 0;
        }
      }
    }
  }
  v24 = (*((_DWORD *)v20 + 2))-- == 1;
  if ( v24 )
    (**(void (__fastcall ***)(void *, __int64))v20)(v20, 1);
  v202 = 0;
  v205 = 0;
  v53 = (unsigned int)(*(_DWORD *)&v201[4] / 256);
  v54 = *((_QWORD *)this + 12);
  if ( (unsigned int)v53 >= *(_DWORD *)(v54 + 12) )
  {
    v55 = 0;
  }
  else
  {
    _mm_lfence();
    v55 = *(_QWORD *)(*(_QWORD *)(v54 + 24) + 8 * v53);
  }
  v56 = (unsigned int)(*(_DWORD *)&v201[4] % 256);
  v57 = *(struct CTableGroupProperties **)(*(_QWORD *)(v55 + 8 * v56) + 8LL);
  v210 = v57;
  CMemo::SetTimeOut(this);
  v58 = *((_QWORD *)this + 10);
  v59 = *(struct COptExpr **)(v58 + 400);
  if ( v59 )
  {
    v202 = CPlanPersUtil::PplanPersReqdBuild(v209, v59, v57);
    v58 = *((_QWORD *)this + 10);
    if ( (unsigned int)(*(_DWORD *)(v58 + 88) - 2) <= 3 )
    {
      v101 = (CIndexesMaintainedSeparately *)operator new(
                                               8u,
                                               *(struct IMemObj **)this,
                                               "sql\\ntdbms\\query\\qeoptim\\engine\\memo.cpp",
                                               6210,
                                               1u);
      v102 = v101;
      v203 = v101;
      if ( v101 )
        *(_QWORD *)v101 = 0;
      else
        v102 = 0;
      v103 = *((_QWORD *)this + 10);
      v268 = 0;
      v269 = 0;
      v246 = (struct SSeparateIndex *)&v268;
      CIndexesMaintainedSeparately::FindIndexesMaintainedSeparately(
        v102,
        *(struct IMemObj **)this,
        *(struct COptExpr **)(v103 + 400),
        &v246);
      *(_QWORD *)v102 = v269;
      *(_QWORD *)(*((_QWORD *)this + 10) + 392LL) = v102;
      v58 = *((_QWORD *)this + 10);
    }
  }
  v60 = *(_DWORD **)(v58 + 368);
  v61 = v57;
  v62 = v209;
  *(_QWORD *)(*((_QWORD *)this + 10) + 368LL) = (*(__int64 (__fastcall **)(_DWORD *, struct IMemObj *, _QWORD, struct CTableGroupProperties *, _QWORD))(*(_QWORD *)v60 + 24LL))(
                                                  v60,
                                                  v209,
                                                  0,
                                                  v61,
                                                  0);
  (*(void (__fastcall **)(_QWORD, struct IMemObj *))(**(_QWORD **)(*((_QWORD *)this + 10) + 368LL) + 16LL))(
    *(_QWORD *)(*((_QWORD *)this + 10) + 368LL),
    v62);
  v24 = v60[2]-- == 1;
  if ( v24 )
    (**(void (__fastcall ***)(_DWORD *, __int64))v60)(v60, 1);
  v63 = *((_QWORD *)this + 12);
  if ( (unsigned int)v53 >= *(_DWORD *)(v63 + 12) )
  {
    v64 = 0;
  }
  else
  {
    _mm_lfence();
    v64 = *(_QWORD *)(*(_QWORD *)(v63 + 24) + 8 * v53);
  }
  CContextProperties::CopyFrom(*(CContextProperties **)(*(_QWORD *)(v64 + 8 * v56) + 216LL), v62, v5);
  CBlitzFusibleSign::EvaluateFusibleCandidatesIfEnabled((CBlitzFusibleSign *)v257, v6);
  *((_DWORD *)this + 61) = 0;
  v208 = *(_QWORD *)(*((_QWORD *)this + 10) + 536LL);
  *((_DWORD *)this + 119) = 0;
  v65 = 0;
  v66 = 0;
  v67 = v210;
  while ( 1 )
  {
    if ( v65 )
    {
      if ( v65 == 1 )
      {
        if ( (*(_BYTE *)(*((_QWORD *)this + 10) + 106LL) & 2) != 0 )
        {
          v68 = g_psrchstratQuickPlanUqo;
        }
        else
        {
          v100 = COptContext::FExclusiveBatchModePlanStrategyEnabled(*((COptContext **)this + 10));
          v68 = g_psrchstratQuickPlan;
          if ( v100 )
            v68 = g_psrchstratQuickPlanExclusiveBatch;
        }
      }
      else if ( v65 == 2 )
      {
        v68 = g_psrchstratFullOpt;
      }
      else
      {
        v68 = 0;
      }
    }
    else
    {
      v68 = g_psrchstratTPPlan;
    }
    if ( !(**(unsigned __int8 (__fastcall ***)(struct CSrchStratQuickPlanExclusiveBatch *, _QWORD, struct CTableGroupProperties *, _QWORD))v68)(
            v68,
            *((_QWORD *)this + 10),
            v67,
            *(_QWORD *)(*((_QWORD *)this + 10) + 368LL)) )
      goto LABEL_104;
    v69 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 10) + 40LL) + 32LL) + 160LL) + 64LL);
    if ( v69 )
    {
      if ( v65 )
      {
        if ( v65 == 1 )
        {
          if ( *(_QWORD *)(v69 + 72) || *(_QWORD *)(v69 + 192) )
            *(_BYTE *)(v69 + 704) = 0;
          v126 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v127 = *(_QWORD **)(v126 + 256);
          if ( !v127 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v127 = *(_QWORD **)(v126 + 256);
          }
          if ( v127[107] )
          {
            v129 = __rdtsc();
            v130 = v127[108];
            v131 = 0;
            if ( v129 > v130 )
              v131 = v129 - v130;
            v128 = v131 + v127[109];
          }
          else
          {
            v128 = 0;
          }
          *(_QWORD *)(v69 + 72) = v128;
          *(_QWORD *)(v69 + 192) = __rdtsc();
        }
        else if ( v65 == 2 )
        {
          if ( *(_QWORD *)(v69 + 80) || *(_QWORD *)(v69 + 200) )
            *(_BYTE *)(v69 + 704) = 0;
          v120 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v121 = *(_QWORD **)(v120 + 256);
          if ( !v121 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v121 = *(_QWORD **)(v120 + 256);
          }
          if ( v121[107] )
          {
            v123 = __rdtsc();
            v124 = v121[108];
            v125 = 0;
            if ( v123 > v124 )
              v125 = v123 - v124;
            v122 = v125 + v121[109];
          }
          else
          {
            v122 = 0;
          }
          *(_QWORD *)(v69 + 80) = v122;
          *(_QWORD *)(v69 + 200) = __rdtsc();
        }
        else
        {
          *(_BYTE *)(v69 + 704) = 0;
        }
      }
      else
      {
        if ( *(_QWORD *)(v69 + 64) || *(_QWORD *)(v69 + 184) )
          *(_BYTE *)(v69 + 704) = 0;
        v132 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v133 = *(_QWORD **)(v132 + 256);
        if ( !v133 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v133 = *(_QWORD **)(v132 + 256);
        }
        if ( v133[107] )
        {
          v135 = __rdtsc();
          v136 = v133[108];
          v137 = 0;
          if ( v135 > v136 )
            v137 = v135 - v136;
          v134 = v137 + v133[109];
        }
        else
        {
          v134 = 0;
        }
        *(_QWORD *)(v69 + 64) = v134;
        *(_QWORD *)(v69 + 184) = __rdtsc();
      }
    }
    if ( (*((_BYTE *)qword_102ECFB10 + 296) & 0x10) != 0
      || (v70 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
          *(_QWORD *)v70)
      && (v71 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v70 + 56LL)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v71, 0x944u) )
    {
      TraceStreamHolder::TraceStreamHolder((TraceStreamHolder *)v206, (struct SOS_TraceStream *)&g_traceout);
      Stream = TraceStreamHolder::GetStream((TraceStreamHolder *)v206);
      TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v248, Stream);
      std::operator<<<std::char_traits<char>>((char *)Stream + 16, "Memory before stage ");
      TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v248);
      if ( v65 )
      {
        if ( v65 == 1 )
        {
          v145 = TraceStreamHolder::GetStream((TraceStreamHolder *)v206);
          TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v250, v145);
          std::operator<<<std::char_traits<char>>((char *)v145 + 16, "QuickPlan");
          v140 = (TraceStreamProtector *)v250;
        }
        else
        {
          if ( v65 != 2 )
          {
LABEL_214:
            v141 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                         + SystemThread_TlsOffset
                                         + 8LL)
                             + 72LL);
            v142 = v141 + 24;
            if ( !v141 )
              v142 = 32;
            v143 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v142 + 120LL))(*(_QWORD *)v142);
            v144 = TraceStreamHolder::GetStream((TraceStreamHolder *)v206);
            TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v225, v144);
            std::operator<<<std::char_traits<char>>((char *)v144 + 16, ": ");
            TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v225);
            TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v226, v144);
            std::ostream::operator<<((char *)v144 + 16, v143);
            TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v226);
            TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v227, v144);
            endl(v144);
            TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v227);
            TraceStreamHolder::~TraceStreamHolder((TraceStreamHolder *)v206);
            goto LABEL_64;
          }
          v139 = TraceStreamHolder::GetStream((TraceStreamHolder *)v206);
          TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v249, v139);
          std::operator<<<std::char_traits<char>>((char *)v139 + 16, "Full");
          v140 = (TraceStreamProtector *)v249;
        }
      }
      else
      {
        v146 = TraceStreamHolder::GetStream((TraceStreamHolder *)v206);
        TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v224, v146);
        std::operator<<<std::char_traits<char>>((char *)v146 + 16, "TP");
        v140 = (TraceStreamProtector *)v224;
      }
      TraceStreamProtector::~TraceStreamProtector(v140);
      goto LABEL_214;
    }
LABEL_64:
    v199 = &v208;
    v72 = a5;
    LOBYTE(v197[0]) = a5;
    v73 = a4;
    v74 = v202;
    CMemo::PerformOptimizationStage(this, (unsigned int)v65, v202, a4, *(_QWORD *)v197);
    if ( (*((_BYTE *)qword_102ECFB10 + 296) & 0x10) == 0 )
    {
      v75 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset);
      if ( !v75 )
        goto LABEL_67;
      v76 = **(struct CSessionTraceFlags ***)(v75 + 56);
      if ( !v76 || !CSessionTraceFlags::CheckSessionTraceInternal(v76, 0x944u) )
        goto LABEL_67;
    }
    TraceStreamHolder::TraceStreamHolder((TraceStreamHolder *)v207, (struct SOS_TraceStream *)&g_traceout);
    v147 = TraceStreamHolder::GetStream((TraceStreamHolder *)v207);
    TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v228, v147);
    std::operator<<<std::char_traits<char>>((char *)v147 + 16, "Memory after stage ");
    TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v228);
    switch ( v65 )
    {
      case 0:
        v155 = TraceStreamHolder::GetStream((TraceStreamHolder *)v207);
        TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v231, v155);
        std::operator<<<std::char_traits<char>>((char *)v155 + 16, "TP");
        v149 = (TraceStreamProtector *)v231;
        goto LABEL_224;
      case 1:
        v154 = TraceStreamHolder::GetStream((TraceStreamHolder *)v207);
        TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v230, v154);
        std::operator<<<std::char_traits<char>>((char *)v154 + 16, "QuickPlan");
        v149 = (TraceStreamProtector *)v230;
        goto LABEL_224;
      case 2:
        v148 = TraceStreamHolder::GetStream((TraceStreamHolder *)v207);
        TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v229, v148);
        std::operator<<<std::char_traits<char>>((char *)v148 + 16, "Full");
        v149 = (TraceStreamProtector *)v229;
LABEL_224:
        TraceStreamProtector::~TraceStreamProtector(v149);
        break;
    }
    v150 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL)
                     + 72LL);
    v151 = v150 + 24;
    if ( !v150 )
      v151 = 32;
    v152 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v151 + 120LL))(*(_QWORD *)v151);
    v153 = TraceStreamHolder::GetStream((TraceStreamHolder *)v207);
    TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v232, v153);
    std::operator<<<std::char_traits<char>>((char *)v153 + 16, ": ");
    TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v232);
    TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v233, v153);
    std::ostream::operator<<((char *)v153 + 16, v152);
    TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v233);
    TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v234, v153);
    endl(v153);
    TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v234);
    TraceStreamHolder::~TraceStreamHolder((TraceStreamHolder *)v207);
    v74 = v202;
    v72 = a5;
    v73 = a4;
LABEL_67:
    if ( CFeedbackUtil::FInDeepModeOptimization() && (unsigned __int8)CMemo::FExecuteMemoGroups(this, (unsigned int)v65) )
    {
      v208 = *(_QWORD *)(*((_QWORD *)this + 10) + 536LL);
      v199 = &v208;
      LOBYTE(v198[0]) = v72;
      CMemo::PerformOptimizationStage(this, (unsigned int)v65, v74, v73, *(_QWORD *)v198);
    }
    v77 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 10) + 40LL) + 32LL) + 160LL) + 64LL);
    if ( v77 )
    {
      if ( v65 )
      {
        if ( v65 == 1 )
        {
          v169 = *(_QWORD *)(v77 + 72);
          if ( !v169 || !*(_QWORD *)(v77 + 192) )
            *(_BYTE *)(v77 + 704) = 0;
          v170 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v171 = *(_QWORD **)(v170 + 256);
          if ( !v171 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v171 = *(_QWORD **)(v170 + 256);
            v169 = *(_QWORD *)(v77 + 72);
          }
          v172 = 0;
          if ( v171[107] )
          {
            v175 = __rdtsc();
            v176 = v171[108];
            if ( v175 > v176 )
              v172 = v175 - v176;
            v173 = v172 + v171[109];
          }
          else
          {
            v173 = 0;
          }
          *(_QWORD *)(v77 + 312) += v173 - v169;
          v174 = __rdtsc();
          *(_QWORD *)(v77 + 432) += (((unsigned __int64)HIDWORD(v174) << 32) | (unsigned int)v174)
                                  - *(_QWORD *)(v77 + 192);
          *(_QWORD *)(v77 + 72) = 0;
          *(_QWORD *)(v77 + 192) = 0;
          ++*(_DWORD *)(v77 + 516);
        }
        else if ( v65 == 2 )
        {
          v161 = *(_QWORD *)(v77 + 80);
          if ( !v161 || !*(_QWORD *)(v77 + 200) )
            *(_BYTE *)(v77 + 704) = 0;
          v162 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v163 = *(_QWORD **)(v162 + 256);
          if ( !v163 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v163 = *(_QWORD **)(v162 + 256);
            v161 = *(_QWORD *)(v77 + 80);
          }
          v164 = 0;
          if ( v163[107] )
          {
            v167 = __rdtsc();
            v168 = v163[108];
            if ( v167 > v168 )
              v164 = v167 - v168;
            v165 = v164 + v163[109];
          }
          else
          {
            v165 = 0;
          }
          *(_QWORD *)(v77 + 320) += v165 - v161;
          v166 = __rdtsc();
          *(_QWORD *)(v77 + 440) += (((unsigned __int64)HIDWORD(v166) << 32) | (unsigned int)v166)
                                  - *(_QWORD *)(v77 + 200);
          *(_QWORD *)(v77 + 80) = 0;
          *(_QWORD *)(v77 + 200) = 0;
          ++*(_DWORD *)(v77 + 520);
        }
        else
        {
          *(_BYTE *)(v77 + 704) = 0;
        }
      }
      else
      {
        v177 = *(_QWORD *)(v77 + 64);
        if ( !v177 || !*(_QWORD *)(v77 + 184) )
          *(_BYTE *)(v77 + 704) = 0;
        v178 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v179 = *(_QWORD **)(v178 + 256);
        if ( !v179 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v179 = *(_QWORD **)(v178 + 256);
          v177 = *(_QWORD *)(v77 + 64);
        }
        v180 = 0;
        if ( v179[107] )
        {
          v183 = __rdtsc();
          v184 = v179[108];
          if ( v183 > v184 )
            v180 = v183 - v184;
          v181 = v180 + v179[109];
        }
        else
        {
          v181 = 0;
        }
        *(_QWORD *)(v77 + 304) += v181 - v177;
        v182 = __rdtsc();
        *(_QWORD *)(v77 + 424) += (((unsigned __int64)HIDWORD(v182) << 32) | (unsigned int)v182)
                                - *(_QWORD *)(v77 + 184);
        *(_QWORD *)(v77 + 64) = 0;
        *(_QWORD *)(v77 + 184) = 0;
        ++*(_DWORD *)(v77 + 512);
      }
      v156 = *((_QWORD *)this + 54);
      v157 = x_cuMax;
      if ( v156 )
      {
        v158 = *(_QWORD *)(v156 + 48);
        if ( v158 )
        {
          v159 = *(_QWORD **)(v156 + 24);
          v235 = v159[6];
          v236 = v159[5];
          v237 = v159[4];
          COptCost::CuTotalCostToRowGoal(*(_QWORD *)(v158 + 72), &v238, &v237, &v236, &v235, &v208);
          v157 = v238;
        }
      }
      v160 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 10) + 40LL) + 32LL) + 160LL) + 64LL);
      if ( v66 > 2 )
      {
        *(_BYTE *)(v160 + 704) = 0;
      }
      else
      {
        *(_DWORD *)(v160 + 4 * v66 + 540) += *((_DWORD *)this + v66 + 2);
        *(double *)(v160 + 8 * v66 + 560) = v157;
      }
    }
    v239 = v208;
    if ( (*(unsigned __int8 (__fastcall **)(struct CSrchStratQuickPlanExclusiveBatch *, _QWORD, struct CTableGroupProperties *, _QWORD, __int64 *))(*(_QWORD *)v68 + 16LL))(
           v68,
           *((_QWORD *)this + 10),
           v210,
           *(_QWORD *)(*((_QWORD *)this + 10) + 368LL),
           &v239) )
    {
      v78 = *((_QWORD *)this + 10);
      if ( (unsigned int)(*(_DWORD *)(v78 + 352) - 1) > 1 )
        *(_DWORD *)(v78 + 352) = 3;
      if ( (*((_BYTE *)qword_102ECFB10 + 1075) & 0x40) != 0
        || (v79 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset)) != 0
        && (v80 = **(struct CSessionTraceFlags ***)(v79 + 56)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v80, 0x219Eu) )
      {
        TraceStreamHolder::TraceStreamHolder((TraceStreamHolder *)v211, (struct SOS_TraceStream *)&g_traceout);
        v185 = TraceStreamHolder::GetStream((TraceStreamHolder *)v211);
        TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v240, v185);
        std::operator<<<std::char_traits<char>>((char *)v185 + 16, "*** Stop search, level ");
        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v240);
        TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v241, v185);
        std::ostream::operator<<((char *)v185 + 16, (unsigned int)v65);
        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v241);
        TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v242, v185);
        std::operator<<<std::char_traits<char>>((char *)v185 + 16, " ***");
        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v242);
        TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v243, v185);
        endl(v185);
        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v243);
        TraceStreamHolder::~TraceStreamHolder((TraceStreamHolder *)v211);
      }
      goto LABEL_75;
    }
    v98 = *((_DWORD *)this + 63) <= *((_DWORD *)this + 61);
    *((_BYTE *)this + 73) = v98;
    if ( v98 || *((_BYTE *)this + 72) )
    {
      CMemo::ReportEarlyAbort(this);
      goto LABEL_75;
    }
    v99 = *((_QWORD *)this + 10);
    if ( (*(_BYTE *)(v99 + 105) & 8) != 0
      && CDbAndSetOpts::LUserOpt1Get(
           **(CDbAndSetOpts ***)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + SystemThread_TlsIndex)
                                           + SystemThread_TlsOffset)
                               + 64LL),
           0x200000u)
      && *((_QWORD *)this + 54) )
    {
      break;
    }
    *(_DWORD *)(v99 + 96) &= ~0x2000000u;
    v67 = v210;
LABEL_104:
    ++v65;
    ++v66;
    if ( v65 >= 3 )
      goto LABEL_75;
  }
  if ( v65 < 2 )
    *(_DWORD *)(v99 + 352) = 4;
LABEL_75:
  if ( *((_QWORD *)this + 54) )
  {
    v81 = *((_QWORD *)this + 55);
    if ( v81
      && !*(_BYTE *)(v81 + 32)
      && *(_DWORD *)(*(_QWORD *)(v81 + 432) + 36LL) != *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v81 + 432) + 16LL) + 44LL)
                                                     - 1 )
    {
      ex_raise(86, 75, 16, 1);
    }
    CMemo::CaptureOptimizationStage(this, 6, (*(_BYTE *)(*((_QWORD *)this + 10) + 107LL) & 4) != 0, 3);
    v82 = *((_QWORD *)this + 54);
    if ( *(_BYTE *)(v82 + 56) )
      v83 = *(_QWORD *)(v82 + 48);
    else
      v83 = 0;
    v84 = *((_QWORD *)this + 55);
    if ( v84 )
    {
      if ( !*(_BYTE *)(v84 + 32) )
        goto LABEL_288;
      v218 = *(_QWORD *)(v84 + 16);
      v219 = (unsigned __int16)&v218;
      v220 = 0;
      v221 = 0;
      v222 = 0;
      v223 = 0;
      CTHashTable<Pair<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::Resize(
        &v218,
        40);
      *(_QWORD *)(v84 + 136) = COptimizationReplayHelper::PbtCaptureBestExpressions(*(_QWORD *)(v84 + 16), v83, &v218);
      v205 = (struct IMemObj *)&v218;
      CTHashTableBase<Pair<COptExpr *,unsigned __int64>,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::~CTHashTableBase<Pair<COptExpr *,unsigned __int64>,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>(&v218);
      if ( *((_QWORD *)this + 55) )
      {
LABEL_288:
        *(_DWORD *)(*((_QWORD *)this + 10) + 1056LL) = 1;
        *(_BYTE *)(*((_QWORD *)this + 55) + 425LL) = 0;
      }
    }
    v85 = *((_QWORD *)this + 10);
    v86 = (int)v209;
    if ( (*(_BYTE *)(v85 + 180) & 2) != 0 )
    {
      WalkPhysicalTreeForGraphIterate(v209, this, *((struct CTaskContext **)this + 54));
      v85 = *((_QWORD *)this + 10);
    }
    if ( (*(_BYTE *)(v85 + 106) & 2) == 0 || (*(_BYTE *)(v85 + 105) & 4) == 0 )
    {
      if ( *(_QWORD *)(v85 + 928) )
      {
        v186 = *(__int64 **)(*(_QWORD *)(v85 + 80) + 16LL);
        v187 = *((_DWORD *)v186 + 2);
        if ( v187 > 7 )
        {
          if ( v187 > 32 )
            v186 = (__int64 *)*v186;
          if ( (*(_DWORD *)v186 & 0x80) != 0 )
            goto LABEL_295;
        }
      }
      if ( (*(_BYTE *)(v85 + 178) & 8) != 0 && (*(_BYTE *)(v85 + 107) & 4) != 0 )
      {
LABEL_295:
        v188 = *((_QWORD *)this + 55);
        if ( !v188 || *(_BYTE *)(v188 + 32) || *(_DWORD *)(v188 + 244) )
        {
          v189 = (struct IMemObj *)operator new(
                                     0x28u,
                                     *(struct IMemObj **)this,
                                     "sql\\ntdbms\\query\\qeoptim\\engine\\memo.cpp",
                                     6483,
                                     1u);
          v205 = v189;
          if ( v189 )
          {
            *(_QWORD *)v189 = *(_QWORD *)this;
            *((_DWORD *)v189 + 3) = 0;
            *((_QWORD *)v189 + 2) = 0;
            *((_QWORD *)v189 + 3) = 0;
            *((_DWORD *)v189 + 8) = 0;
            CTHashTable<PLString *,CFnH_PLString,CFnC_PLString,CFnI_Default<PLString *>,CFnD_Ptr<PLString>,CMemObjAlloc<0>>::Resize(
              v189,
              101);
          }
          else
          {
            v189 = 0;
          }
          v272 = v189;
          v190 = (struct IMemObj *)operator new(
                                     0x28u,
                                     *(struct IMemObj **)this,
                                     "sql\\ntdbms\\query\\qeoptim\\engine\\memo.cpp",
                                     6484,
                                     1u);
          v205 = v190;
          if ( v190 )
          {
            v191 = *(_QWORD *)this;
            v203 = v190;
            *(_QWORD *)v190 = v191;
            *((_WORD *)v190 + 4) = 6484;
            *((_DWORD *)v190 + 3) = 0;
            *((_QWORD *)v190 + 2) = 0;
            *((_QWORD *)v190 + 3) = 0;
            *((_DWORD *)v190 + 8) = 0;
            CTHashTable<Pair<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::Resize(
              v190,
              40);
          }
          else
          {
            v190 = 0;
          }
          v273 = v190;
          v192 = (struct IMemObj *)operator new(
                                     0x28u,
                                     *(struct IMemObj **)this,
                                     "sql\\ntdbms\\query\\qeoptim\\engine\\memo.cpp",
                                     6491,
                                     1u);
          v205 = v192;
          if ( v192 )
          {
            v193 = *(_QWORD *)this;
            v203 = v192;
            *(_QWORD *)v192 = v193;
            *((_WORD *)v192 + 4) = 6491;
            *((_DWORD *)v192 + 3) = 0;
            *((_QWORD *)v192 + 2) = 0;
            *((_QWORD *)v192 + 3) = 0;
            *((_DWORD *)v192 + 8) = 0;
            CTHashTable<Pair<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::Resize(
              v192,
              11);
          }
          else
          {
            v192 = 0;
          }
          v270 = v192;
          WalkPhysicalTree(v86, (_DWORD)this, *((_QWORD *)this + 54), (_DWORD)v189, (__int64)v190, (__int64)v192);
          if ( v192 )
          {
            CTHashTableBase<Pair<COptExpr *,unsigned __int64>,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::~CTHashTableBase<Pair<COptExpr *,unsigned __int64>,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>(v192);
            operator delete(v192, 0x28u);
          }
          if ( v190 )
          {
            CTHashTableBase<Pair<COptExpr *,unsigned __int64>,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::~CTHashTableBase<Pair<COptExpr *,unsigned __int64>,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>(v190);
            operator delete(v190, 0x28u);
          }
          if ( v189 )
          {
            CTHashTableBase<Pair<COptExpr *,unsigned __int64>,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::~CTHashTableBase<Pair<COptExpr *,unsigned __int64>,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>(v189);
            operator delete(v189, 0x28u);
          }
        }
      }
    }
    v87 = *((_QWORD *)this + 55);
    if ( v87 )
      *(_DWORD *)(*((_QWORD *)this + 10) + 1056LL) = 3 - (*(_BYTE *)(v87 + 32) != 0);
    v88 = CMemo::PexprCopyOut(this, *(int *)&v201[4], *((struct CTaskContext **)this + 54), 1u);
    v89 = *((_QWORD *)this + 54);
    v90 = x_cuMax;
    v91 = *(_QWORD *)(v89 + 48);
    if ( v91 )
    {
      v92 = *(_QWORD **)(v89 + 24);
      v244 = v92[6];
      v245 = v92[5];
      v203 = (struct IMemObj *)v92[4];
      COptCost::CuTotalCostToRowGoal(*(_QWORD *)(v91 + 72), &v247, &v203, &v245, &v244, v199);
      v90 = v247;
    }
    *(double *)(*((_QWORD *)this + 10) + 360LL) = v90;
  }
  else
  {
    v88 = v205;
  }
  v93 = *((_QWORD *)this + 10);
  if ( *(_QWORD *)(v93 + 400) )
  {
    if ( (*(_BYTE *)(v93 + 177) & 8) != 0 )
    {
      v104 = *(int **)(*(_QWORD *)(v93 + 80) + 16LL);
      if ( v104[2] > 34 && (*(_BYTE *)(*(_QWORD *)v104 + 4LL) & 4) != 0 && (qword_102EDCA04 & 0x100000) != 0 )
      {
        v275 = 0x10000;
        v276 = 0;
        v277 = v280;
        v278 = &v281;
        v282 = 0;
        v279 = 0;
        v283 = 0;
        v280[0] = v284;
        v280[1] = 27;
        v284[0] = (*(_BYTE *)(v93 + 179) & 0x10) != 0;
        v105 = *((_QWORD *)this + 54);
        v284[1] = v105 != 0;
        v106 = -1;
        if ( v105 )
        {
          v107 = *(int *)(v105 + 60);
          v108 = (unsigned int)(v107 + 1) <= 7 && dword_102F394C4[v107] == 1;
        }
        else
        {
          v108 = 0;
        }
        v284[2] = v108;
        v285 = *(int *)(v93 + 432);
        v109 = *((_QWORD *)this + 4);
        if ( v109 == -1 )
        {
          v110 = -1;
        }
        else if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          v110 = 1000 * v109 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
        }
        else
        {
          v110 = v109 / 0x2710;
        }
        v286 = v110;
        v111 = *((_QWORD *)this + 5);
        if ( v111 != -1 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
            v106 = 1000 * v111 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
          else
            v106 = v111 / 0x2710;
        }
        v287 = v106;
        XeSqlPkg::quickstage_useplan_statistics::Publish((XeSqlPkg::quickstage_useplan_statistics *)v274);
      }
    }
  }
  if ( v212 )
    (**v212)(v212, 1);
  v94 = v213;
  if ( v213 )
  {
    v95 = *((_QWORD *)v213 + 6);
    if ( v95 )
    {
      v24 = (*(_DWORD *)(v95 + 8))-- == 1;
      if ( v24 )
        (**(void (__fastcall ***)(__int64, __int64))v95)(v95, 1);
    }
    operator delete(v94, 0x38u);
  }
  v96 = v202;
  if ( v202 )
  {
    v24 = (*((_DWORD *)v202 + 2))-- == 1;
    if ( v24 )
      (**(void (__fastcall ***)(struct CPlanPersReqd *, __int64))v96)(v96, 1);
  }
  *(_QWORD *)(*((_QWORD *)this + 10) + 336LL) = 0;
  if ( v267 )
  {
    v194 = (void *)*((_QWORD *)&v258 + 1);
    if ( *((_QWORD *)&v258 + 1) )
    {
      CTHashTableBase<Pair<unsigned __int64,DRgMKLNode *>,CTMap<unsigned __int64,DRgMKLNode *,CFnH_UINT64,CFnC_Default<unsigned __int64>,CFnI_Default<DRgMKLNode *>,CFnD_Noop<unsigned __int64>,CFnD_Ptr<DRgMKLNode>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<unsigned __int64,DRgMKLNode *,CFnH_UINT64,CFnC_Default<unsigned __int64>,CFnI_Default<DRgMKLNode *>,CFnD_Noop<unsigned __int64>,CFnD_Ptr<DRgMKLNode>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<unsigned __int64,DRgMKLNode *,CFnH_UINT64,CFnC_Default<unsigned __int64>,CFnI_Default<DRgMKLNode *>,CFnD_Noop<unsigned __int64>,CFnD_Ptr<DRgMKLNode>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<unsigned __int64,DRgMKLNode *,CFnH_UINT64,CFnC_Default<unsigned __int64>,CFnI_Default<DRgMKLNode *>,CFnD_Noop<unsigned __int64>,CFnD_Ptr<DRgMKLNode>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::~CTHashTableBase<Pair<unsigned __int64,DRgMKLNode *>,CTMap<unsigned __int64,DRgMKLNode *,CFnH_UINT64,CFnC_Default<unsigned __int64>,CFnI_Default<DRgMKLNode *>,CFnD_Noop<unsigned __int64>,CFnD_Ptr<DRgMKLNode>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<unsigned __int64,DRgMKLNode *,CFnH_UINT64,CFnC_Default<unsigned __int64>,CFnI_Default<DRgMKLNode *>,CFnD_Noop<unsigned __int64>,CFnD_Ptr<DRgMKLNode>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<unsigned __int64,DRgMKLNode *,CFnH_UINT64,CFnC_Default<unsigned __int64>,CFnI_Default<DRgMKLNode *>,CFnD_Noop<unsigned __int64>,CFnD_Ptr<DRgMKLNode>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<unsigned __int64,DRgMKLNode *,CFnH_UINT64,CFnC_Default<unsigned __int64>,CFnI_Default<DRgMKLNode *>,CFnD_Noop<unsigned __int64>,CFnD_Ptr<DRgMKLNode>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>(*((_QWORD *)&v258 + 1));
      operator delete(v194, 0x28u);
    }
    v195 = (void *)v258;
    if ( (_QWORD)v258 )
    {
      CTHashTableBase<Pair<COptExpr *,unsigned __int64>,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::~CTHashTableBase<Pair<COptExpr *,unsigned __int64>,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>(v258);
      operator delete(v195, 0x28u);
    }
    if ( v259 )
      (**v259)(v259, 1);
    CBlitzFusibleSign::cleanupSignTree((CBlitzFusibleSign *)v257, v257[0]);
  }
  return v88;
}

```

## disassembly

```asm
0x1004e4e00  mov     rax, rsp
0x1004e4e03  mov     [rax+20h], r9b
0x1004e4e07  mov     [rax+18h], r8
0x1004e4e0b  mov     [rax+10h], rdx
0x1004e4e0f  mov     [rax+8], rcx
0x1004e4e13  push    rbp
0x1004e4e14  push    rbx
0x1004e4e15  push    rsi
0x1004e4e16  push    rdi
0x1004e4e17  push    r12
0x1004e4e19  push    r13
0x1004e4e1b  push    r14
0x1004e4e1d  push    r15
0x1004e4e1f  lea     rbp, [rax-4F8h]
0x1004e4e26  sub     rsp, 5B8h
0x1004e4e2d  mov     [rbp+4F0h+var_330], 0FFFFFFFFFFFFFFFEh
0x1004e4e38  movaps  xmmword ptr [rax-58h], xmm6
0x1004e4e3c  movaps  xmmword ptr [rax-68h], xmm7
0x1004e4e40  movaps  xmmword ptr [rax-78h], xmm8
0x1004e4e45  movaps  xmmword ptr [rax-88h], xmm9
0x1004e4e4d  movaps  xmmword ptr [rax-98h], xmm10
0x1004e4e55  mov     r12, r8
0x1004e4e58  mov     rsi, rdx
0x1004e4e5b  mov     r14, rcx
0x1004e4e5e  mov     rax, [rcx+50h]
0x1004e4e62  mov     r15, [rax+20h]
0x1004e4e66  mov     [rbp+4F0h+var_540], r15
0x1004e4e6a  mov     [rbp+4F0h+var_560], r15
0x1004e4e6e  xor     r13d, r13d
0x1004e4e71  mov     [rbp+4F0h+var_3C0], r13
0x1004e4e78  mov     rdx, gs:58h
0x1004e4e81  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004e4e88  mov     ecx, [rax]
0x1004e4e8a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004e4e91  mov     eax, [rax]
0x1004e4e93  add     rax, [rdx+rcx*8]
0x1004e4e97  mov     rax, [rax+8]
0x1004e4e9b  mov     rcx, [rax+48h]
0x1004e4e9f  lea     rax, [rcx+18h]
0x1004e4ea3  mov     edx, 20h ; ' '
0x1004e4ea8  test    rcx, rcx
0x1004e4eab  cmovz   rax, rdx
0x1004e4eaf  mov     rax, [rax]
0x1004e4eb2  mov     [rbp+4F0h+var_3B8], rax
0x1004e4eb9  xorps   xmm0, xmm0
0x1004e4ebc  movdqa  [rbp+4F0h+var_3B0], xmm0
0x1004e4ec4  mov     [rbp+4F0h+var_398], r13
0x1004e4ecb  mov     [rbp+4F0h+var_390], r13d
0x1004e4ed2  xorps   xmm1, xmm1
0x1004e4ed5  movsd   [rbp+4F0h+var_388], xmm1
0x1004e4edd  movaps  [rbp+4F0h+var_380], xmm0
0x1004e4ee4  movsd   [rbp+4F0h+var_370], xmm1
0x1004e4eec  mov     [rbp+4F0h+var_368], r13
0x1004e4ef3  mov     [rbp+4F0h+var_360], r13d
0x1004e4efa  mov     [rbp+4F0h+var_35C], r13b
0x1004e4f01  mov     dword ptr [rsp+5F0h+var_580+4], 17FBh
0x1004e4f09  mov     byte ptr [rsp+5F0h+var_5D0], 1
0x1004e4f0e  mov     r9d, 17FBh
0x1004e4f14  lea     r8, aSqlNtdbmsQuery_168; "sql\\ntdbms\\query\\qeoptim\\engine\\me"...
0x1004e4f1b  mov     rdx, r15
0x1004e4f1e  lea     ecx, [r13+10h]
0x1004e4f22  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004e4f28  mov     rcx, rax
0x1004e4f2b  mov     [rbp+4F0h+var_528], rax
0x1004e4f2f  mov     [rbp+4F0h+var_570], rax
0x1004e4f33  test    rax, rax
0x1004e4f36  jz      loc_101CAD07C
0x1004e4f3c  lea     rax, ??_7CTaskList@@6B@; const CTaskList::`vftable'
0x1004e4f43  mov     [rcx], rax
0x1004e4f46  mov     [rcx+8], r13
0x1004e4f4a  jmp     short loc_1004E4F4D
0x1004e4f4d  mov     rax, [r14+50h]
0x1004e4f51  mov     [rax+150h], rcx
0x1004e4f58  movsd   xmm0, cs:?x_cuMax@@3VCQODouble@@B; CQODouble const x_cuMax
0x1004e4f60  unpcklpd xmm0, xmm0
0x1004e4f64  movups  [rbp+4F0h+var_3D0], xmm0
0x1004e4f6b  mov     dword ptr [rsp+5F0h+var_580+4], 1807h
0x1004e4f73  mov     byte ptr [rsp+5F0h+var_5D0], 1
0x1004e4f78  mov     r9d, 1807h
0x1004e4f7e  lea     r8, aSqlNtdbmsQuery_168; "sql\\ntdbms\\query\\qeoptim\\engine\\me"...
0x1004e4f85  mov     rdx, r15
0x1004e4f88  mov     ecx, 38h ; '8'
0x1004e4f8d  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004e4f93  mov     rdi, rax
0x1004e4f96  mov     [rbp+4F0h+var_520], rax
0x1004e4f9a  mov     [rbp+4F0h+var_570], rax
0x1004e4f9e  test    rax, rax
0x1004e4fa1  jz      loc_101CAD092
0x1004e4fa7  mov     rax, [r14+50h]
0x1004e4fab  movsd   xmm0, qword ptr [rax+0E0h]
0x1004e4fb3  mov     [rdi], r13
0x1004e4fb6  mov     [rdi+8], r13
0x1004e4fba  mov     [rdi+10h], r13
0x1004e4fbe  mov     byte ptr [rdi+18h], 0
0x1004e4fc2  mov     [rdi+20h], r13
0x1004e4fc6  mov     [rdi+28h], r13
0x1004e4fca  mov     [rdi+30h], r13
0x1004e4fce  mov     rdx, gs:58h
0x1004e4fd7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004e4fde  mov     ecx, [rax]
0x1004e4fe0  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004e4fe7  mov     eax, [rax]
0x1004e4fe9  add     rax, [rdx+rcx*8]
0x1004e4fed  mov     rax, [rax+8]
0x1004e4ff1  mov     rcx, [rax+48h]
0x1004e4ff5  lea     rax, [rcx+0A8h]
0x1004e4ffc  mov     edx, 0B0h
0x1004e5001  test    rcx, rcx
0x1004e5004  cmovz   rax, rdx
0x1004e5008  cmp     byte ptr [rax], 0
0x1004e500b  jl      loc_101CAD089
0x1004e5011  movsd   qword ptr [rdi], xmm0
0x1004e5015  jmp     short loc_1004E5018
0x1004e5018  mov     dword ptr [rsp+5F0h+var_580+4], 1809h
0x1004e5020  mov     byte ptr [rsp+5F0h+var_5D0], 1
0x1004e5025  mov     r9d, 1809h
0x1004e502b  lea     r8, aSqlNtdbmsQuery_168; "sql\\ntdbms\\query\\qeoptim\\engine\\me"...
0x1004e5032  mov     rdx, r15
0x1004e5035  mov     ecx, 70h ; 'p'
0x1004e503a  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004e5040  mov     rbx, rax
0x1004e5043  mov     [rbp+4F0h+var_570], rax
0x1004e5047  lea     rcx, ??_7CRefCount@@6B@; const CRefCount::`vftable'
0x1004e504e  test    rax, rax
0x1004e5051  jz      loc_101CAD09F
0x1004e5057  mov     rax, [r14+50h]
0x1004e505b  mov     r8, [rax+138h]
0x1004e5062  mov     [rbx], rcx
0x1004e5065  mov     dword ptr [rbx+8], 1
0x1004e506c  lea     rax, ??_7COptCostContext@@6B@; const COptCostContext::`vftable'
0x1004e5073  mov     [rbx], rax
0x1004e5076  lea     rdx, [rbx+10h]
0x1004e507a  lea     rcx, [rbp+4F0h+var_3D0]
0x1004e5081  call    ?CuMultiplyByWeight@COptCostVector@@QEBA?AVCQODouble@@PEBV1@@Z; COptCostVector::CuMultiplyByWeight(COptCostVector const *)
0x1004e5086  mov     [rbx+18h], r8
0x1004e508a  lea     rcx, [rbx+20h]; this
0x1004e508e  mov     rdx, rdi; struct COptCostGoal *
0x1004e5091  call    ??0COptCostGoal@@QEAA@AEBV0@@Z; COptCostGoal::COptCostGoal(COptCostGoal const &)
0x1004e5096  nop
0x1004e5097  movsd   xmm0, cs:?x_cardIllegal@@3VCQODouble@@B; CQODouble const x_cardIllegal
0x1004e509f  movsd   qword ptr [rbx+58h], xmm0
0x1004e50a4  movsd   xmm1, cs:?x_cardIllegal@@3VCQODouble@@B; CQODouble const x_cardIllegal
0x1004e50ac  movsd   qword ptr [rbx+60h], xmm1
0x1004e50b1  movsd   xmm0, cs:?x_cardIllegal@@3VCQODouble@@B; CQODouble const x_cardIllegal
0x1004e50b9  movsd   qword ptr [rbx+68h], xmm0
0x1004e50be  inc     cs:?m_count@COptCostContext@@2KA; ulong COptCostContext::m_count
0x1004e50c4  jmp     short loc_1004E50C7
0x1004e50c7  mov     dword ptr [rsp+5F0h+var_580+4], 180Ah
0x1004e50cf  mov     byte ptr [rsp+5F0h+var_5D0], 1
0x1004e50d4  mov     r9d, 180Ah
0x1004e50da  lea     r8, aSqlNtdbmsQuery_168; "sql\\ntdbms\\query\\qeoptim\\engine\\me"...
0x1004e50e1  mov     rdx, r15
0x1004e50e4  mov     ecx, 48h ; 'H'
0x1004e50e9  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004e50ef  mov     rdi, rax
0x1004e50f2  mov     [rbp+4F0h+var_570], rax
0x1004e50f6  test    rax, rax
0x1004e50f9  jz      loc_101CAD0B1
0x1004e50ff  mov     rax, [r14+50h]
0x1004e5103  lea     rcx, ??_7CRefCount@@6B@; const CRefCount::`vftable'
0x1004e510a  mov     [rdi], rcx
0x1004e510d  mov     dword ptr [rdi+8], 1
0x1004e5114  lea     rcx, ??_7CTaskContext@@6B@; const CTaskContext::`vftable'
0x1004e511b  mov     [rdi], rcx
0x1004e511e  mov     [rdi+10h], rax
0x1004e5122  mov     [rdi+18h], r13
0x1004e5126  mov     [rdi+20h], r13
0x1004e512a  movsd   xmm0, cs:?x_cuMax@@3VCQODouble@@B; CQODouble const x_cuMax
0x1004e5132  movsd   qword ptr [rdi+28h], xmm0
0x1004e5137  mov     [rdi+30h], r13
0x1004e513b  mov     word ptr [rdi+38h], 0
0x1004e5141  mov     [rdi+3Ch], r13d
0x1004e5145  inc     cs:?m_count@CTaskContext@@2KA; ulong CTaskContext::m_count
0x1004e514b  mov     [rdi+20h], r13
0x1004e514f  mov     [rdi+18h], rbx
0x1004e5153  test    rbx, rbx
0x1004e5156  jz      short loc_1004E515B
0x1004e5158  inc     dword ptr [rbx+8]
0x1004e515b  mov     rax, [rax+130h]
0x1004e5162  test    rax, rax
0x1004e5165  jz      loc_101CAD0A8
0x1004e516b  mov     ecx, [rax+0F4h]
0x1004e5171  jmp     short loc_1004E5174
0x1004e5174  mov     [rdi+40h], ecx
0x1004e5177  mov     [rdi+44h], r13d
0x1004e517b  jmp     short loc_1004E517E
0x1004e517e  add     dword ptr [rbx+8], 0FFFFFFFFh
0x1004e5182  jz      loc_101CAD0BA
0x1004e5188  call    ?GetStackAvailableBytes@SOS_Task@@SA_KXZ; SOS_Task::GetStackAvailableBytes(void)
0x1004e518d  cmp     rax, 18000h
0x1004e5193  jb      loc_101CAD0CE
0x1004e5199  lea     rcx, ?m_perCpuCounters@OptimizerUtil@@0V?$PerCPUData@VPerCPUYieldCounter@@@@A; this
0x1004e51a0  call    ?GetObjectDataImpl@PerCPUDataImpl@@IEBAPEAXXZ; PerCPUDataImpl::GetObjectDataImpl(void)
0x1004e51a5  mov     rbx, rax
0x1004e51a8  inc     dword ptr [rax]
0x1004e51aa  cmp     dword ptr [rax], 0Ah
0x1004e51ad  jnb     loc_10076706A
0x1004e51b3  mov     ebx, r13d
0x1004e51b6  cmp     [rsi+18h], r13d
0x1004e51ba  jbe     short loc_1004E51D9
0x1004e51bc  nop     dword ptr [rax]
0x1004e51bf  nop
0x1004e51c0  movsxd  rcx, ebx
0x1004e51c3  mov     rax, [rsi+20h]
0x1004e51c7  xor     edx, edx; bool
0x1004e51c9  mov     rcx, [rax+rcx*8]; this
0x1004e51cd  call    ?DetachPointersIntoMemo@COptExpr@@QEAAX_N@Z; COptExpr::DetachPointersIntoMemo(bool)
0x1004e51d2  inc     ebx
0x1004e51d4  cmp     ebx, [rsi+18h]
0x1004e51d7  jb      short loc_1004E51C0
0x1004e51d9  mov     [rsi+70h], r13
0x1004e51dd  mov     [rsp+5F0h+var_580], 0
0x1004e51e2  mov     [rsp+5F0h+var_590], r13; struct CApplyRuleCaptureHelper *
0x1004e51e7  mov     dword ptr [rsp+5F0h+var_598], r13d; __int64
0x1004e51ec  lea     rax, [rsp+5F0h+var_580]
0x1004e51f1  mov     [rsp+5F0h+var_5A0], rax; bool *
0x1004e51f6  mov     [rsp+5F0h+var_5A8], r13; bool *
0x1004e51fb  mov     [rsp+5F0h+var_5B0], r13; bool *
0x1004e5200  mov     [rsp+5F0h+var_5B8], r13; bool *
0x1004e5205  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1004e520c  mov     [rsp+5F0h+var_5C0], r13d; int
0x1004e5211  xor     r15d, r15d
0x1004e5214  mov     dword ptr [rsp+5F0h+var_5C8], r15d; int
0x1004e5219  mov     [rsp+5F0h+var_5D0], r15d; int
0x1004e521e  mov     r9d, r13d; int
0x1004e5221  mov     r8, rdi; struct CTaskContext *
0x1004e5224  mov     rdx, rsi; struct COptExpr *
0x1004e5227  mov     rcx, r14; this
0x1004e522a  call    ?PgexprInclude@CMemo@@QEAAPEAVCGroupExpr@@PEAVCOptExpr@@PEAVCTaskContext@@HHHHPEA_N222HPEAVCApplyRuleCaptureHelper@@@Z; CMemo::PgexprInclude(COptExpr *,CTaskContext *,int,int,int,int,bool *,bool *,bool *,bool *,int,CApplyRuleCaptureHelper *)
0x1004e522f  mov     eax, [rax]
0x1004e5231  mov     dword ptr [rsp+5F0h+var_580+4], eax
0x1004e5235  mov     [r14+0DCh], eax
0x1004e523c  cmp     [r14+1B8h], r15
0x1004e5243  jnz     loc_101CAD0EB
0x1004e5249  mov     ecx, [r14+68h]
0x1004e524d  mov     rax, [r14+1B8h]
0x1004e5254  test    rax, rax
0x1004e5257  jnz     loc_101CAD17E
0x1004e525d  mov     rax, [r14+50h]
0x1004e5261  cmp     dword ptr [rax+420h], 3
0x1004e5268  jz      loc_101CAD1A1
0x1004e526e  mov     rax, [r14+50h]
0x1004e5272  mov     rbx, [rax+2D8h]
0x1004e5279  test    rbx, rbx
0x1004e527c  jz      loc_1004E5304
0x1004e5282  mov     rax, [rbx]
0x1004e5285  mov     edx, r13d
0x1004e5288  mov     rcx, rbx
0x1004e528b  call    qword ptr [rax]
0x1004e528d  mov     rax, [r14]
0x1004e5290  mov     [rbp+4F0h+var_3F8], rax
0x1004e5297  mov     [rbp+4F0h+var_3EC], r15d
0x1004e529e  mov     [rbp+4F0h+var_3E8], r15
0x1004e52a5  mov     [rbp+4F0h+var_3E0], r15
0x1004e52ac  mov     [rbp+4F0h+var_3D8], r15d
0x1004e52b3  xor     r8d, r8d
0x1004e52b6  lea     edx, [r8+64h]
0x1004e52ba  lea     rcx, [rbp+4F0h+var_3F8]
0x1004e52c1  call    ?Resize@?$CTHashTable@PEAUPLString@@VCFnH_PLString@@VCFnC_PLString@@V?$CFnI_Default@PEAUPLString@@@@V?$CFnD_Ptr@UPLString@@@@V?$CMemObjAlloc@$0A@@@@@AEAAXKPEAV?$CMemObjAlloc@$0A@@@@Z; CTHashTable<PLString *,CFnH_PLString,CFnC_PLString,CFnI_Default<PLString *>,CFnD_Ptr<PLString>,CMemObjAlloc<0>>::Resize(ulong,CMemObjAlloc<0> *)
0x1004e52c6  nop
0x1004e52c7  mov     r9, [r14]
0x1004e52ca  lea     r8, [rbp+4F0h+var_3F8]
0x1004e52d1  mov     rdx, rbx
0x1004e52d4  mov     rcx, rsi
0x1004e52d7  call    ??$Traverse@VCOptExpr@@@@YAXPEAVCOptExpr@@PEAUExpressionVisitor@@PEAV?$CTHashTable@PEAVCOptExpr@@VCFnH_Pointer@@V?$CFnC_Default@PEAVCOptExpr@@@@V?$CFnI_Default@PEAVCOptExpr@@@@V?$CFnD_Noop@PEAVCOptExpr@@@@V?$CMemObjAlloc@$0A@@@@@PEAVIMemObj@@@Z; Traverse<COptExpr>(COptExpr *,ExpressionVisitor *,CTHashTable<COptExpr *,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<COptExpr *>,CFnD_Noop<COptExpr *>,CMemObjAlloc<0>> *,IMemObj *)
0x1004e52dc  mov     rax, [rbx]
0x1004e52df  mov     rcx, rbx
0x1004e52e2  call    qword ptr [rax+10h]
0x1004e52e5  nop
0x1004e52e6  lea     rcx, [rbp+4F0h+var_3F8]
0x1004e52ed  call    ?DestroyBuckets@?$CTHashTableBase@U?$Pair@PEBXPEBVMatExpressionNode@@@@VCEntryHashFn@?$CTMap@PEBXPEBVMatExpressionNode@@VCFnH_Pointer@@V?$CFnC_Default@PEBX@@V?$CFnI_Default@PEBVMatExpressionNode@@@@V?$CFnD_Noop@PEBX@@V?$CFnD_Noop@PEBVMatExpressionNode@@@@V?$CMemObjAlloc@$0A@@@@@VCEntryCmpFn@3@VCEntryInvalidFn@3@VCEntryDestroyFn@3@V?$CMemObjAlloc@$0A@@@@@IEAAXXZ; CTHashTableBase<Pair<void const *,MatExpressionNode const *>,CTMap<void const *,MatExpressionNode const *,CFnH_Pointer,CFnC_Default<void const *>,CFnI_Default<MatExpressionNode const *>,CFnD_Noop<void const *>,CFnD_Noop<MatExpressionNode const *>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<void const *,MatExpressionNode const *,CFnH_Pointer,CFnC_Default<void const *>,CFnI_Default<MatExpressionNode const *>,CFnD_Noop<void const *>,CFnD_Noop<MatExpressionNode const *>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<void const *,MatExpressionNode const *,CFnH_Pointer,CFnC_Default<void const *>,CFnI_Default<MatExpressionNode const *>,CFnD_Noop<void const *>,CFnD_Noop<MatExpressionNode const *>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<void const *,MatExpressionNode const *,CFnH_Pointer,CFnC_Default<void const *>,CFnI_Default<MatExpressionNode const *>,CFnD_Noop<void const *>,CFnD_Noop<MatExpressionNode const *>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::DestroyBuckets(void)
0x1004e52f2  mov     rcx, [rbp+4F0h+var_3E8]
0x1004e52f9  test    rcx, rcx
0x1004e52fc  jz      short loc_1004E5304
0x1004e52fe  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004e5304  mov     rdx, [r14+50h]
0x1004e5308  mov     r15, [rdx+0C0h]
0x1004e530f  test    r15, r15
0x1004e5312  jz      loc_1004E5461
0x1004e5318  mov     rdx, [rdx+20h]
0x1004e531c  mov     [rbp+4F0h+var_560], rdx
0x1004e5320  mov     [rbp+4F0h+var_568], 4BDh
0x1004e5327  mov     byte ptr [rsp+5F0h+var_5D0], 1
0x1004e532c  mov     r9d, 4BDh
0x1004e5332  lea     r8, aSqlNtdbmsQuery_52; "sql\\ntdbms\\query\\qeoptim\\engine\\re"...
0x1004e5339  mov     ecx, 18h
0x1004e533e  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004e5344  mov     r8, rax
0x1004e5347  mov     [rbp+4F0h+var_570], rax
0x1004e534b  test    rax, rax
0x1004e534e  jz      loc_101CAD1F8
0x1004e5354  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1004e535b  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x1004e5363  mov     dword ptr [rax+10h], 0FFFFFFFFh
0x1004e536a  mov     byte ptr [rax+14h], 0
0x1004e536e  jmp     short loc_1004E5371
0x1004e5371  mov     [r15], r8
0x1004e5374  mov     rcx, [r14+50h]
0x1004e5378  mov     rax, [rcx+388h]
0x1004e537f  movsd   xmm6, qword ptr [rax+168h]
  ... truncated ...
```
