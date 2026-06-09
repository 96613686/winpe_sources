# showstats(wchar_t const *,int,wchar_t *,int,EShowstatsOptions,CCompExecCtxtStmt const *,ulong,DBTABLE *,bool,bool,long)

- ea: `0x101c781d0`
- end: `0x101c79603`
- name: `?showstats@@YAXPEB_WHPEA_WHW4EShowstatsOptions@@PEBVCCompExecCtxtStmt@@KPEAVDBTABLE@@_N5J@Z`
- size: `5171`
- prototype: ``
- caller_count: `2`
- callee_count: `29`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x10174b0e0`
- `0x101c77b40`

## callees

- `0x100401070`
- `0x100401090`
- `0x1004012d0`
- `0x100401340`
- `0x100409cb0`
- `0x10040aaa0`
- `0x10040be50`
- `0x1004131b0`
- `0x100415d70`
- `0x1004223e0`
- `0x100445aa0`
- `0x10046d8a0`
- `0x1004d3d40`
- `0x1004d7670`
- `0x1004d7de0`
- `0x10067b4e0`
- `0x10067b590`
- `0x101c5c270`
- `0x101c70f40`
- `0x101c71f40`
- `0x101c72d70`
- `0x101c73cb0`
- `0x101c74270`
- `0x101c74e90`
- `0x101c75750`
- `0x101c75d40`
- `0x101c764c0`
- `0x101c76f60`
- `0x101c781d0`

## import_xrefs

- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x101c784ea`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x101c785d2`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101c78b0f`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101c78bc4`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101c78ef6`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101c791af`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101c793f8`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x101c782de`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101c79485`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101c79485`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101c7864a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101c78768`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101c78939`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101c78a3e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101c78ba4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101c78f5d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101c78fa0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101c79320`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101c793c9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101c7864a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101c78768`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101c78939`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101c78a3e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101c78ba4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101c78f5d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101c78fa0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101c79320`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101c793c9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101c7836d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101c78ce9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101c7836d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101c78ce9`
- `sqldk!SystemThread_TlsIndex` at `0x101c78289`
- `sqldk!SystemThread_TlsIndex` at `0x101c78307`
- `sqldk!SystemThread_TlsIndex` at `0x101c783bd`
- `sqldk!SystemThread_TlsIndex` at `0x101c783f6`
- `sqldk!SystemThread_TlsIndex` at `0x101c7854f`
- `sqldk!SystemThread_TlsIndex` at `0x101c7866a`
- `sqldk!SystemThread_TlsIndex` at `0x101c787a5`
- `sqldk!SystemThread_TlsIndex` at `0x101c78883`
- `sqldk!SystemThread_TlsIndex` at `0x101c78976`
- `sqldk!SystemThread_TlsIndex` at `0x101c78b50`
- `sqldk!SystemThread_TlsIndex` at `0x101c78c05`
- `sqldk!SystemThread_TlsIndex` at `0x101c78c9a`
- `sqldk!SystemThread_TlsIndex` at `0x101c7907e`
- `sqldk!SystemThread_TlsIndex` at `0x101c790d1`
- `sqldk!SystemThread_TlsIndex` at `0x101c791f5`
- `sqldk!SystemThread_TlsIndex` at `0x101c79257`
- `sqldk!SystemThread_TlsIndex` at `0x101c7933f`
- `sqldk!SystemThread_TlsIndex` at `0x101c7944d`
- `sqldk!SystemThread_TlsIndex` at `0x101c79495`
- `sqldk!SystemThread_TlsOffset` at `0x101c7829a`
- `sqldk!SystemThread_TlsOffset` at `0x101c78310`
- `sqldk!SystemThread_TlsOffset` at `0x101c783c6`
- `sqldk!SystemThread_TlsOffset` at `0x101c783ff`
- `sqldk!SystemThread_TlsOffset` at `0x101c78560`
- `sqldk!SystemThread_TlsOffset` at `0x101c7867b`
- `sqldk!SystemThread_TlsOffset` at `0x101c787ae`
- `sqldk!SystemThread_TlsOffset` at `0x101c7888c`
- `sqldk!SystemThread_TlsOffset` at `0x101c7897f`
- `sqldk!SystemThread_TlsOffset` at `0x101c78b59`
- `sqldk!SystemThread_TlsOffset` at `0x101c78c0e`
- `sqldk!SystemThread_TlsOffset` at `0x101c78ca3`
- `sqldk!SystemThread_TlsOffset` at `0x101c79087`
- `sqldk!SystemThread_TlsOffset` at `0x101c790da`
- `sqldk!SystemThread_TlsOffset` at `0x101c791fe`
- `sqldk!SystemThread_TlsOffset` at `0x101c79260`
- `sqldk!SystemThread_TlsOffset` at `0x101c79348`
- `sqldk!SystemThread_TlsOffset` at `0x101c79456`
- `sqldk!SystemThread_TlsOffset` at `0x101c7949e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c7832b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c7859f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c78cbe`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c790f5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c7946f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c7832b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c7859f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c78cbe`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c790f5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101c7946f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c790ad`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c79286`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c79377`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c790ad`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c79286`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101c79377`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c78787`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c78865`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c78958`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c78b32`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c78be7`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c78cff`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c7918f`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c791d7`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c793d8`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c7942f`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c78787`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c78865`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c78958`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c78b32`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c78be7`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c78cff`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c7918f`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c791d7`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c793d8`
- `sqldk!??_V@YAXPEAX@Z` at `0x101c7942f`
- `sqlmin!?UtilDbccGetCheckBaseXact@@YAPEAVBaseXact@@XZ` at `0x101c784d1`
- `sqlmin!?UtilDbccGetCheckBaseXact@@YAPEAVBaseXact@@XZ` at `0x101c784d1`
- `sqlmin!?FDWFidoValidateAndGetCellHashFromTxn@@YA_NPEAVDBTABLE@@PEAH@Z` at `0x101c78f0b`
- `sqlmin!?FDWFidoValidateAndGetCellHashFromTxn@@YA_NPEAVDBTABLE@@PEAH@Z` at `0x101c78f0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
void __fastcall showstats(
        wchar_t *a1,
        int a2,
        const wchar_t *a3,
        unsigned int a4,
        unsigned int a5,
        struct CCompExecCtxtStmt *a6,
        unsigned int a7,
        __int64 a8,
        char a9,
        unsigned __int8 a10,
        unsigned int a11)
{
  unsigned int StatIdxName; // r15d
  unsigned __int64 v13; // rsi
  __int64 v15; // r9
  __int64 v16; // rbx
  __int64 v17; // r10
  unsigned __int64 v18; // rax
  int v19; // eax
  bool v20; // zf
  __int64 v21; // rax
  __int64 v22; // rbx
  struct BaseXact *v23; // rax
  __int64 v24; // rax
  __int64 v25; // r8
  struct IMEDStats *v26; // rax
  __int64 v27; // r9
  __int64 v28; // rdi
  __int64 v29; // rbx
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // r8
  struct IMEDStats *v33; // rbx
  __int64 v34; // r8
  __int64 v35; // rax
  DataVirtualizationResource *v36; // rax
  int v37; // ecx
  struct IMEDObject *v38; // r14
  __int64 v39; // rbx
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rbx
  unsigned int v43; // edi
  unsigned int v44; // edi
  unsigned int i; // esi
  wchar_t *v46; // rdi
  __int64 v47; // rbx
  __int64 v48; // rdx
  unsigned int v49; // esi
  int v50; // eax
  int v51; // eax
  int v52; // eax
  struct IMEDStats *v53; // rdi
  __int64 (__fastcall ***v54)(_QWORD); // rax
  unsigned int v55; // eax
  struct DBTABLE *v56; // rax
  __int64 v57; // rbx
  unsigned int v58; // eax
  struct IMEDIndex *v59; // rax
  __int64 v60; // rdx
  struct CSessionTraceFlags *v61; // rcx
  __int64 v62; // rdi
  __int64 v63; // rdx
  __int64 v64; // rdx
  __int64 v65; // rax
  struct CSessionTraceFlags *v66; // rcx
  unsigned int v67; // esi
  __int64 v68; // rax
  struct CSessionTraceFlags *v69; // rcx
  __int64 v70; // rbx
  struct Worker *v71; // rcx
  unsigned int v72; // edi
  unsigned int v73; // eax
  struct IMEDIndex *v74; // rax
  struct IMEDIndex *v75; // rdi
  int v76; // [rsp+20h] [rbp-1518h]
  struct CCompExecCtxtStmt *v77; // [rsp+20h] [rbp-1518h]
  struct CCompExecCtxtStmt *v78; // [rsp+20h] [rbp-1518h]
  int v79; // [rsp+28h] [rbp-1510h]
  unsigned int v80[2]; // [rsp+38h] [rbp-1500h]
  bool v81; // [rsp+60h] [rbp-14D8h] BYREF
  bool v82; // [rsp+61h] [rbp-14D7h]
  unsigned int v83; // [rsp+64h] [rbp-14D4h]
  unsigned int v84; // [rsp+68h] [rbp-14D0h]
  int v85; // [rsp+6Ch] [rbp-14CCh] BYREF
  __int64 v86; // [rsp+70h] [rbp-14C8h]
  unsigned int v87; // [rsp+78h] [rbp-14C0h]
  struct IMEDStats *v88; // [rsp+80h] [rbp-14B8h]
  bool v89; // [rsp+88h] [rbp-14B0h]
  unsigned int v90; // [rsp+8Ch] [rbp-14ACh]
  _QWORD *v91; // [rsp+90h] [rbp-14A8h]
  __int64 v92; // [rsp+98h] [rbp-14A0h] BYREF
  int v93; // [rsp+A0h] [rbp-1498h]
  __int128 v94; // [rsp+A8h] [rbp-1490h]
  int v95; // [rsp+B8h] [rbp-1480h]
  void *v96; // [rsp+C0h] [rbp-1478h]
  wchar_t *v97; // [rsp+C8h] [rbp-1470h]
  unsigned int v98; // [rsp+D0h] [rbp-1468h] BYREF
  struct CCompExecCtxtStmt *v99; // [rsp+D8h] [rbp-1460h] BYREF
  __int64 v100; // [rsp+E0h] [rbp-1458h]
  __int64 v101; // [rsp+E8h] [rbp-1450h]
  wchar_t *v102; // [rsp+F0h] [rbp-1448h]
  __int64 v103; // [rsp+F8h] [rbp-1440h]
  void *v104; // [rsp+100h] [rbp-1438h]
  const wchar_t *v105; // [rsp+108h] [rbp-1430h]
  struct CCompExecCtxtStmt *v106; // [rsp+110h] [rbp-1428h]
  _BYTE v107[40]; // [rsp+130h] [rbp-1408h] BYREF
  const wchar_t *v108; // [rsp+158h] [rbp-13E0h] BYREF
  unsigned int v109; // [rsp+160h] [rbp-13D8h]
  wchar_t *v110; // [rsp+168h] [rbp-13D0h] BYREF
  unsigned int v111; // [rsp+170h] [rbp-13C8h]
  wchar_t *v112; // [rsp+178h] [rbp-13C0h] BYREF
  unsigned int v113; // [rsp+180h] [rbp-13B8h]
  wchar_t *v114; // [rsp+188h] [rbp-13B0h] BYREF
  unsigned int v115; // [rsp+190h] [rbp-13A8h]
  __int128 v116; // [rsp+198h] [rbp-13A0h] BYREF
  _BYTE v117[24]; // [rsp+1A8h] [rbp-1390h] BYREF
  wchar_t *v118; // [rsp+1C0h] [rbp-1378h]
  int v119; // [rsp+1D4h] [rbp-1364h]
  __int64 v120; // [rsp+210h] [rbp-1328h]
  char v121[8]; // [rsp+218h] [rbp-1320h] BYREF
  int v122; // [rsp+220h] [rbp-1318h]
  char v123[24]; // [rsp+228h] [rbp-1310h] BYREF
  _BYTE v124[352]; // [rsp+240h] [rbp-12F8h] BYREF
  unsigned int v125; // [rsp+3A0h] [rbp-1198h]

  v120 = -2;
  StatIdxName = a4;
  v83 = a4;
  v13 = a2;
  v95 = a2;
  v102 = a1;
  v106 = a6;
  v103 = a8;
  v92 = 0;
  v93 = 1;
  v94 = 0;
  v99 = a6;
  v101 = 0;
  v15 = 8LL * SystemThread_TlsIndex;
  v100 = *(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                               + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v15)
                               + 8LL)
                   + 72LL);
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v15)
                        + SystemThread_TlsOffset
                        + 8LL)
            + 72LL) = &v99;
  ExcHandler::ExcHandler((ExcHandler *)v107, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_prntbackout, 0);
  v16 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v17 = *(_QWORD *)(v16 + 256);
  if ( !v17 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v17 = *(_QWORD *)(v16 + 256);
  }
  v18 = 2 * (v13 >> 1);
  if ( !is_mul_ok(v13 >> 1, 2u) )
    v18 = -1;
  v96 = operator new[](
          v18,
          *(struct IMemObj **)(v17 + 1000),
          "sql\\ntdbms\\query\\qeoptim\\util\\showstat.cpp",
          2528,
          1u);
  v104 = v96;
  v19 = CbParseQuotesW(a1, v13, (wchar_t *)v96, v13);
  WParseName::Parse((WParseName *)v117, (const wchar_t *)v96, v19);
  v93 = 1;
  v91 = *(_QWORD **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset);
  *(_QWORD *)&v94 = v91[18];
  v91 = *(_QWORD **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset);
  v20 = (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v94 + 464LL))(v94) == 0;
  v21 = *(_QWORD *)v94;
  if ( v20 )
  {
    v80[1] = 0;
    (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64))(v21 + 8))(v94, L"showstats", 18);
    LODWORD(v92) = 2;
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, __int64, __int64, char *))(v21 + 232))(v94, 1, 1, (char *)&v92 + 4);
    v93 = 1;
    LODWORD(v92) = 4;
  }
  v86 = 0;
  if ( a10 )
  {
    if ( UtilDbccGetContext() )
      v22 = *((_QWORD *)UtilDbccGetContext() + 7);
    else
      v22 = 0;
    v23 = UtilDbccGetCheckBaseXact();
    v86 = g_metadataFactory(v22, v23, "sql\\ntdbms\\query\\qeoptim\\util\\showstat.cpp", 2550);
    v24 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v86 + 56LL))(
            v86,
            *(unsigned __int16 *)(v103 + 40),
            0,
            0,
            0,
            0);
    v80[0] = 0;
    LOBYTE(v79) = 1;
    LOBYTE(v76) = 0;
    LOBYTE(v25) = 1;
    v26 = (struct IMEDStats *)(*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int, int, _DWORD, unsigned int *))(*(_QWORD *)v24 + 120LL))(
                                v24,
                                a11,
                                v25,
                                0,
                                v76,
                                v79,
                                0,
                                *(unsigned int **)v80);
  }
  else
  {
    v27 = 8LL * SystemThread_TlsIndex;
    v91 = *(_QWORD **)(SystemThread_TlsOffset + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v27));
    v13 = v91[18];
    v28 = SystemThread_TlsOffset + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v27);
    v29 = *(_QWORD *)(v28 + 256);
    if ( !v29 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v29 = *(_QWORD *)(v28 + 256);
    }
    v30 = *(_QWORD *)(v29 + 1000);
    v31 = (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)v13 + 432LL))(v13);
    v86 = g_metadataFactory(v30, v31, "sql\\ntdbms\\query\\qeoptim\\util\\showstat.cpp", 2566);
    LOBYTE(v32) = 1;
    v26 = (struct IMEDStats *)(*(__int64 (__fastcall **)(__int64, _BYTE *, __int64, __int64, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _BYTE))(*(_QWORD *)v86 + 40LL))(
                                v86,
                                v117,
                                v32,
                                6,
                                0,
                                0,
                                0,
                                0,
                                0,
                                0,
                                0);
    LODWORD(v13) = v95;
  }
  v88 = v26;
  v33 = v26;
  if ( !v26 )
  {
    LODWORD(v77) = v13;
    ex_raise(27, 6, 16, 2, v77, a1);
  }
  (*(void (__fastcall **)(struct IMEDStats *, char *))(*(_QWORD *)v33 + 96LL))(v33, v121);
  v34 = 8LL * SystemThread_TlsIndex;
  if ( *(_QWORD *)(SystemThread_TlsOffset + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v34)) )
  {
    if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v34)
                               + SystemThread_TlsOffset)
                   + 128LL)
      && (v35 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v34)
                                      + SystemThread_TlsOffset)
                          + 128LL),
          v20 = (*(_DWORD *)(v35 + 76) & 0x2000) == 0,
          v89 = (*(_DWORD *)(v35 + 76) & 0x2000) != 0,
          !v20)
      || *(_QWORD *)(*(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v34)
                               + SystemThread_TlsOffset)
                   + 72LL)
      && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v34)
                                           + SystemThread_TlsOffset)
                               + 72LL)
                   + 270LL)
        & 2) != 0 )
    {
      v36 = qword_102EF3550;
LABEL_29:
      v37 = v122;
      goto LABEL_30;
    }
  }
  v36 = qword_102EF3550;
  if ( !*((_BYTE *)qword_102EF3550 + 787) )
    goto LABEL_29;
  v37 = v122;
  if ( v122 == 21573 )
  {
    LODWORD(v77) = 30;
    ex_raise(405, 18, 16, 6, v77, L"show_statistics");
    (**(void (__fastcall ***)(__int64, __int64))v86)(v86, 1);
    operator delete[](v96);
    ExcHandler::~ExcHandler((ExcHandler *)v107);
    *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 8LL)
              + 72LL) = v100;
    if ( (_DWORD)v92 )
      CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v92, 0);
    return;
  }
LABEL_30:
  if ( *((_BYTE *)v36 + 456) && (*((_BYTE *)qword_102ECFB10 + 1641) & 8) == 0 )
  {
    if ( v37 != 8277 && v37 != 8275 && v37 != 21577 )
    {
      if ( v37 != 8278 )
      {
        if ( v37 != 21573 )
        {
          (**(void (__fastcall ***)(__int64, __int64))v86)(v86, 1);
          operator delete[](v96);
          ExcHandler::~ExcHandler((ExcHandler *)v107);
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset
                                + 8LL)
                    + 72LL) = v100;
          if ( (_DWORD)v92 )
            CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v92, 0);
          return;
        }
        goto LABEL_51;
      }
LABEL_49:
      v38 = v88;
      (*(void (__fastcall **)(struct IMEDStats *, char *))(*(_QWORD *)v88 + 96LL))(v88, v123);
      (*(void (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v38 + 120LL))(v38);
      v39 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v38 + 40LL))(v38);
      v40 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v38 + 168LL))(v38);
      v41 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 80LL))(v40);
      (*(void (__fastcall **)(__int64, bool *))(*(_QWORD *)v41 + 24LL))(v41, &v81);
      if ( (v81 & 4) == 0 )
      {
        LODWORD(v77) = *(_DWORD *)(v39 + 8);
        ex_raise(27, 80, 16, 1, v77, *(_QWORD *)v39);
      }
      goto LABEL_52;
    }
    goto LABEL_51;
  }
  switch ( v37 )
  {
    case 8277:
    case 8275:
    case 21577:
      goto LABEL_51;
    case 8278:
      goto LABEL_49;
    case 21573:
    case 21588:
LABEL_51:
      v38 = v88;
LABEL_52:
      v42 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v38 + 120LL))(v38);
      v91 = (_QWORD *)v42;
      v43 = (**(__int64 (__fastcall ***)(struct IMEDObject *))v38)(v38);
      v90 = v43;
      v85 = 0;
      CAutoDb::FUse((CAutoDb *)&v85, v43, 0, 1, 1, 0);
      if ( !a3 )
      {
        if ( a5 == 32 )
        {
          ShowStatsPermissionsCheck(v102, v13, v38, 0, v106, v118, 2 * v119, v43);
          SendStatsStream(0);
          if ( v85 )
          {
            v85 = 0;
            ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
          }
          (**(void (__fastcall ***)(__int64, __int64))v86)(v86, 1);
          operator delete[](v96);
          ExcHandler::~ExcHandler((ExcHandler *)v107);
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset
                                + 8LL)
                    + 72LL) = v100;
          if ( (_DWORD)v92 )
            CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v92, 0);
        }
        else
        {
          ex_raise(25, 83, 16, 5);
          if ( v85 )
          {
            v85 = 0;
            ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
          }
          (**(void (__fastcall ***)(__int64, __int64))v86)(v86, 1);
          operator delete[](v96);
          ExcHandler::~ExcHandler((ExcHandler *)v107);
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset
                                + 8LL)
                    + 72LL) = v100;
          if ( (_DWORD)v92 )
            CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v92, 0);
        }
        return;
      }
      v44 = -1;
      v84 = -1;
      v97 = 0;
      for ( i = 1; ; i = v87 + 1 )
      {
        while ( 1 )
        {
          v87 = i;
          if ( i >= 3 )
          {
LABEL_135:
            if ( v44 == -1 )
            {
              LODWORD(v78) = StatIdxName;
              ex_raise(27, 67, 16, 1, v78, a3);
            }
            operator delete[](v97);
            if ( v85 )
            {
              v85 = 0;
              ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
            }
            if ( v86 )
              (**(void (__fastcall ***)(__int64, __int64))v86)(v86, 1);
            CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v92, 0);
            operator delete[](v104);
            ExcHandler::~ExcHandler((ExcHandler *)v107);
            v70 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            v71 = *(struct Worker **)(v70 + 256);
            if ( !v71 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v71 = *(struct Worker **)(v70 + 256);
            }
            if ( *((_DWORD *)v71 + 139) )
              ExceptionPostCatchActions(v71);
            *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                  + SystemThread_TlsOffset
                                  + 8LL)
                      + 72LL) = v100;
            if ( (_DWORD)v92 )
              CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v92, 0);
            return;
          }
          v105 = 0;
          if ( i != 1 )
            break;
          v46 = (wchar_t *)a3;
          v105 = a3;
LABEL_78:
          v114 = v46;
          v115 = StatIdxName;
          v44 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v42 + 320LL))(
                  v42,
                  &v114,
                  0,
                  0);
          v84 = v44;
          if ( v44 == -1 )
          {
            StatIdxName = v83;
            ++i;
          }
          else if ( (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v42 + 256LL))(v42, v44) )
          {
            StatIdxName = v83;
            ++i;
          }
          else
          {
            if ( !(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v42 + 264LL))(v42, v44) )
            {
              v53 = (struct IMEDStats *)(*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v42 + 240LL))(
                                          v42,
                                          v44,
                                          0,
                                          0);
              v88 = v53;
              v54 = (__int64 (__fastcall ***)(_QWORD))(**(__int64 (__fastcall ***)(__int64))v42)(v42);
              v55 = (**v54)(v54);
              v56 = (struct DBTABLE *)g_dbtableFactory[4](v55);
              if ( FDWFidoValidateAndGetCellHashFromTxn(v56, (int *)&v98) )
                (*(void (__fastcall **)(struct IMEDStats *, _QWORD))(*(_QWORD *)v53 + 168LL))(v53, v98);
              if ( (unsigned int)IsVDWFrontendInstance()
                && (*(unsigned int (__fastcall **)(struct IMEDStats *))(*(_QWORD *)v53 + 8LL))(v53) == 99999 )
              {
                ex_raise(165, 42, 16, 5, L"ACE-Cardinality");
              }
              if ( a7 == 1
                || (*(unsigned __int8 (__fastcall **)(struct IMEDStats *, _QWORD))(*(_QWORD *)v53 + 160LL))(v53, a7) )
              {
                StatIdxName = v83;
              }
              else
              {
                StatIdxName = v83;
                LODWORD(v78) = v83;
                ex_raise(27, 67, 16, 2, v78, a3);
              }
              ShowStatsPermissionsCheck(v102, v95, v38, v53, v106, v118, 2 * v119, v90);
              v82 = 0;
              if ( v53 )
              {
                v116 = 0;
                (*(void (__fastcall **)(struct IMEDStats *, __int128 *))(*(_QWORD *)v53 + 24LL))(v53, &v116);
                if ( (BYTE8(v116) & 0x20) == 0 )
                {
                  v57 = (**(__int64 (__fastcall ***)(struct IMEDStats *))v53)(v53);
                  v58 = (*(__int64 (__fastcall **)(struct IMEDStats *))(*(_QWORD *)v53 + 8LL))(v53);
                  v59 = (struct IMEDIndex *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v57 + 232LL))(
                                              v57,
                                              v58);
                  v82 = SMD::FColumnStoreIndex(v59);
                }
              }
              if ( a5 != 32
                || (*((_BYTE *)qword_102ECFB10 + 298) & 0x10) != 0
                || (v60 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset,
                    *(_QWORD *)v60)
                && (v61 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v60 + 56LL)) != 0
                && CSessionTraceFlags::CheckSessionTraceInternal(v61, 0x954u)
                || (v81 = 1, !v82) )
              {
                v81 = 0;
              }
              v62 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              v63 = *(_QWORD *)(v62 + 256);
              if ( !v63 )
              {
                SystemThread::MakeMiniSOSThread(0);
                v63 = *(_QWORD *)(v62 + 256);
              }
              CStatMan::CStatMan((CStatMan *)v124, *(struct IMemObj **)(v63 + 1000), v88, 0, v81);
              v125 = a7;
              v90 = CStatMan::Init(v124, 0);
              if ( a9 )
              {
                PersistStatsStream(v103, v91, v84, v124);
                CStatMan::~CStatMan((CStatMan *)v124);
                operator delete[](v97);
                if ( v85 )
                {
                  v85 = 0;
                  ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
                }
                if ( v86 )
                  (**(void (__fastcall ***)(__int64, __int64))v86)(v86, 1);
                operator delete[](v104);
                ExcHandler::~ExcHandler((ExcHandler *)v107);
                *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 72LL) = v100;
                if ( (_DWORD)v92 )
                  CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v92, 0);
                return;
              }
              if ( a5 == 32
                && (*((_BYTE *)qword_102ECFB10 + 298) & 0x10) == 0
                && ((v65 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset)) == 0
                 || (v66 = **(struct CSessionTraceFlags ***)(v65 + 56)) == 0
                 || !CSessionTraceFlags::CheckSessionTraceInternal(v66, 0x954u))
                || a10 )
              {
                SendStatsStream((struct IStatMan *)v124);
                if ( !a10 )
                {
                  CStatMan::~CStatMan((CStatMan *)v124);
                  v44 = v84;
                  goto LABEL_135;
                }
              }
              v67 = v90 == 1 || CStatMan::FColumnStoreStat((CStatMan *)v124);
              v83 = v67;
              v44 = v84;
              if ( v84 - 2048 <= 0x3FF && v67 )
              {
                LODWORD(v78) = StatIdxName;
                ex_raise(27, 67, 16, 3, v78, a3);
              }
              if ( (*((_BYTE *)qword_102ECFB10 + 298) & 0x10) != 0 )
              {
LABEL_133:
                SendStatCompHistory(v124, v67);
              }
              else
              {
                v68 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset);
                if ( v68 )
                {
                  v69 = **(struct CSessionTraceFlags ***)(v68 + 56);
                  if ( v69 )
                  {
                    if ( CSessionTraceFlags::CheckSessionTraceInternal(v69, 0x954u) )
                    {
                      v44 = v84;
                      v67 = v83;
                      goto LABEL_133;
                    }
                  }
                }
                if ( !a10 && a5 == 16 )
                {
                  SendStatsHdrJoinDensityVector(v124, v86, v83, 0);
                  goto LABEL_151;
                }
                if ( a5 == 8 || (a5 & 1) != 0 || a10 )
                {
                  v72 = v83;
                  SendStatHdr(v124, v64, v83, a10);
                  if ( a5 != 8 )
                    goto LABEL_157;
                  goto LABEL_159;
                }
                v72 = v83;
LABEL_157:
                if ( (a5 & 2) != 0 || a10 )
                {
LABEL_159:
                  SendDensityVector(v124, v72, a10);
                  if ( a5 != 8 )
                    goto LABEL_160;
LABEL_162:
                  SendHistogramSteps(v124, a5, v72, a10);
                }
                else
                {
LABEL_160:
                  if ( (a5 & 0x44) != 0 || a10 )
                    goto LABEL_162;
                }
                if ( !v82 )
                  goto LABEL_151;
                v73 = (*(__int64 (__fastcall **)(struct IMEDStats *))(*(_QWORD *)v88 + 8LL))(v88);
                v74 = (struct IMEDIndex *)(*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v91 + 232LL))(v91, v73);
                v75 = v74;
                if ( (a5 & 0x80u) != 0 || a10 )
                  SendColumnstoreSegmentPages(v74);
                if ( (a5 & 0x100) != 0 || a10 )
                {
                  SendColumnstoreAttachedStructures(v75);
                  v44 = v84;
                }
                else
                {
LABEL_151:
                  v44 = v84;
                }
              }
              CStatMan::~CStatMan((CStatMan *)v124);
              goto LABEL_135;
            }
            StatIdxName = v83;
            ++i;
          }
        }
        v47 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v48 = *(_QWORD *)(v47 + 256);
        if ( !v48 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v48 = *(_QWORD *)(v47 + 256);
        }
        v46 = (wchar_t *)operator new[](
                           0x100u,
                           *(struct IMemObj **)(v48 + 1000),
                           "sql\\ntdbms\\query\\qeoptim\\util\\showstat.cpp",
                           2698,
                           1u);
        if ( v97 != v46 )
          operator delete[](v97);
        v97 = v46;
        v108 = a3;
        v109 = StatIdxName;
        v42 = (__int64)v91;
        v49 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t **, _QWORD))(*v91 + 48LL))(v91, &v108, 0);
        if ( v49 != -1 )
        {
          v105 = v46;
          v38 = v88;
          v50 = (*(__int64 (__fastcall **)(struct IMEDStats *))(*(_QWORD *)v88 + 8LL))(v88);
          StatIdxName = CStatMan::CbGetStatIdxName(v49, v50, v46, 0x80u, 0);
          v110 = v46;
          v111 = StatIdxName;
          v84 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v42 + 320LL))(
                  v42,
                  &v110,
                  0,
                  0);
          if ( v84 == -1 )
          {
            v51 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v38 + 8LL))(v38);
            StatIdxName = CStatMan::CbGetStatIdxName(v49, v51, v46, 0x80u, 1);
            v112 = v46;
            v113 = StatIdxName;
            v84 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v42 + 320LL))(
                    v42,
                    &v112,
                    0,
                    0);
            if ( v84 == -1 )
            {
              v52 = (*(__int64 (__fastcall **)(struct IMEDObject *))(*(_QWORD *)v38 + 8LL))(v38);
              StatIdxName = CStatMan::CbGetStatIdxName(a3, v83, v52, v46, 0x80u, 0);
            }
          }
          i = v87;
          goto LABEL_78;
        }
        v38 = v88;
        v44 = v84;
      }
      break;
  }
  LODWORD(v77) = 2 * v119;
  ex_raise(27, 6, 16, 6, v77, v118);
  (**(void (__fastcall ***)(__int64, __int64))v86)(v86, 1);
  operator delete[](v96);
  ExcHandler::~ExcHandler((ExcHandler *)v107);
  *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset
                        + 8LL)
            + 72LL) = v100;
  if ( (_DWORD)v92 )
    CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v92, 0);
}

```

## disassembly

```asm
0x101c781d0  push    rbx
0x101c781d2  push    rsi
0x101c781d3  push    rdi
0x101c781d4  push    r12
0x101c781d6  push    r13
0x101c781d8  push    r14
0x101c781da  push    r15
0x101c781dc  mov     eax, 1500h
0x101c781e1  call    _alloca_probe
0x101c781e6  sub     rsp, rax
0x101c781e9  mov     [rsp+1538h+var_1328], 0FFFFFFFFFFFFFFFEh
0x101c781f5  mov     rax, cs:__security_cookie
0x101c781fc  xor     rax, rsp
0x101c781ff  mov     [rsp+1538h+var_48], rax
0x101c78207  mov     r15d, r9d
0x101c7820a  mov     [rsp+1538h+var_14D4], r9d
0x101c7820f  mov     r13, r8
0x101c78212  movsxd  rsi, edx
0x101c78215  mov     [rsp+1538h+var_1480], esi
0x101c7821c  mov     r14, rcx
0x101c7821f  mov     [rsp+1538h+var_1448], rcx
0x101c78227  mov     rax, [rsp+1538h+arg_28]
0x101c7822f  mov     [rsp+1538h+var_1428], rax
0x101c78237  mov     rcx, [rsp+1538h+arg_38]
0x101c7823f  mov     [rsp+1538h+var_1440], rcx
0x101c78247  mov     edi, [rsp+1538h+arg_50]
0x101c7824e  xor     r12d, r12d
0x101c78251  mov     [rsp+1538h+var_14A0], r12
0x101c78259  mov     [rsp+1538h+var_1498], 1
0x101c78264  xorps   xmm0, xmm0
0x101c78267  movdqu  [rsp+1538h+var_1490], xmm0
0x101c78270  mov     [rsp+1538h+var_1460], rax
0x101c78278  mov     [rsp+1538h+var_1450], r12
0x101c78280  mov     rdx, gs:58h
0x101c78289  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101c78290  mov     ecx, [rax]
0x101c78292  lea     r9, ds:0[rcx*8]
0x101c7829a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101c782a1  mov     r8d, [rax]
0x101c782a4  mov     rax, [r9+rdx]
0x101c782a8  mov     rcx, [r8+rax+8]
0x101c782ad  mov     rax, [rcx+48h]
0x101c782b1  mov     [rsp+1538h+var_1458], rax
0x101c782b9  mov     rax, gs:58h
0x101c782c2  mov     rcx, [rax+r9]
0x101c782c6  mov     rax, [rcx+r8+8]
0x101c782cb  lea     rcx, [rsp+1538h+var_1460]
0x101c782d3  mov     [rax+48h], rcx
0x101c782d7  xor     edx, edx; unsigned __int16
0x101c782d9  mov     [rsp+1538h+var_1510], r12; struct Worker *
0x101c782de  mov     rax, cs:__imp_?hdl_prntbackout@@YAHHHHHPEAD@Z; hdl_prntbackout(int,int,int,int,char *)
0x101c782e5  mov     [rsp+1538h+var_1518], rax; int (*)(int, int, int, int, char *)
0x101c782ea  xor     r9d, r9d; unsigned __int8
0x101c782ed  xor     r8d, r8d; unsigned __int8
0x101c782f0  lea     rcx, [rsp+1538h+var_1408]; this
0x101c782f8  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x101c782fd  nop
0x101c782fe  mov     rdx, gs:58h
0x101c78307  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101c7830e  mov     ecx, [rax]
0x101c78310  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101c78317  mov     ebx, [rax]
0x101c78319  add     rbx, [rdx+rcx*8]
0x101c7831d  mov     r10, [rbx+100h]
0x101c78324  test    r10, r10
0x101c78327  jnz     short loc_101C78338
0x101c78329  xor     ecx, ecx
0x101c7832b  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101c78331  mov     r10, [rbx+100h]
0x101c78338  mov     rcx, rsi
0x101c7833b  shr     rcx, 1
0x101c7833e  mov     eax, 2
0x101c78343  mul     rcx
0x101c78346  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x101c7834d  cmovo   rax, rcx
0x101c78351  mov     byte ptr [rsp+1538h+var_1518], 1
0x101c78356  mov     r9d, 9E0h
0x101c7835c  lea     r8, aSqlNtdbmsQuery_221; "sql\\ntdbms\\query\\qeoptim\\util\\show"...
0x101c78363  mov     rdx, [r10+3E8h]
0x101c7836a  mov     rcx, rax
0x101c7836d  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x101c78373  mov     rbx, rax
0x101c78376  mov     [rsp+1538h+var_1478], rax
0x101c7837e  mov     [rsp+1538h+var_1438], rax
0x101c78386  mov     r9d, esi; int
0x101c78389  mov     r8, rax; wchar_t *
0x101c7838c  mov     edx, esi; int
0x101c7838e  mov     rcx, r14; wchar_t *
0x101c78391  call    ?CbParseQuotesW@@YAHPEB_WHPEA_WH@Z; CbParseQuotesW(wchar_t const *,int,wchar_t *,int)
0x101c78396  mov     r8d, eax; int
0x101c78399  mov     rdx, rbx; wchar_t *
0x101c7839c  lea     rcx, [rsp+1538h+var_1390]; this
0x101c783a4  call    ?Parse@WParseName@@QEAAXPEB_WH@Z; WParseName::Parse(wchar_t const *,int)
0x101c783a9  mov     [rsp+1538h+var_1498], 1
0x101c783b4  mov     rdx, gs:58h
0x101c783bd  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101c783c4  mov     ecx, [rax]
0x101c783c6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101c783cd  mov     eax, [rax]
0x101c783cf  add     rax, [rdx+rcx*8]
0x101c783d3  mov     rax, [rax]
0x101c783d6  mov     [rsp+1538h+var_14A8], rax
0x101c783de  mov     rax, [rax+90h]
0x101c783e5  mov     qword ptr [rsp+1538h+var_1490], rax
0x101c783ed  mov     rdx, gs:58h
0x101c783f6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101c783fd  mov     ecx, [rax]
0x101c783ff  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101c78406  mov     eax, [rax]
0x101c78408  add     rax, [rdx+rcx*8]
0x101c7840c  mov     rax, [rax]
0x101c7840f  mov     [rsp+1538h+var_14A8], rax
0x101c78417  mov     rcx, qword ptr [rsp+1538h+var_1490]
0x101c7841f  mov     rax, [rcx]
0x101c78422  call    qword ptr [rax+1D0h]
0x101c78428  mov     rcx, qword ptr [rsp+1538h+var_1490]
0x101c78430  test    al, al
0x101c78432  mov     rax, [rcx]
0x101c78435  jz      short loc_101C78465
0x101c78437  lea     r9, [rsp+1538h+var_14A0+4]
0x101c7843f  mov     edx, 1
0x101c78444  mov     r8d, edx
0x101c78447  call    qword ptr [rax+0E8h]
0x101c7844d  mov     [rsp+1538h+var_1498], 1
0x101c78458  mov     dword ptr [rsp+1538h+var_14A0], 4
0x101c78463  jmp     short loc_101C784A3
0x101c78465  mov     [rsp+1538h+var_14F8], r12d
0x101c7846a  mov     qword ptr [rsp+1538h+var_1500], r12
0x101c7846f  mov     byte ptr [rsp+1538h+var_1508], 0
0x101c78474  mov     dword ptr [rsp+1538h+var_1510], 2
0x101c7847c  mov     dword ptr [rsp+1538h+var_1518], 1
0x101c78484  mov     r9d, 1
0x101c7848a  lea     r8d, [r9+11h]
0x101c7848e  lea     rdx, aShowstats; "showstats"
0x101c78495  call    qword ptr [rax+8]
0x101c78498  mov     dword ptr [rsp+1538h+var_14A0], 2
0x101c784a3  mov     [rsp+1538h+var_14C8], r12
0x101c784a8  movzx   r12d, [rsp+1538h+arg_48]
0x101c784b1  test    r12b, r12b
0x101c784b4  jz      loc_101C78546
0x101c784ba  call    ?UtilDbccGetContext@@YAPEAVDbccThreadContext@@XZ; UtilDbccGetContext(void)
0x101c784bf  test    rax, rax
0x101c784c2  jz      short loc_101C784CF
0x101c784c4  call    ?UtilDbccGetContext@@YAPEAVDbccThreadContext@@XZ; UtilDbccGetContext(void)
0x101c784c9  mov     rbx, [rax+38h]
0x101c784cd  jmp     short loc_101C784D1
0x101c784cf  xor     ebx, ebx
0x101c784d1  call    cs:__imp_?UtilDbccGetCheckBaseXact@@YAPEAVBaseXact@@XZ; UtilDbccGetCheckBaseXact(void)
0x101c784d7  mov     r9d, 9F6h
0x101c784dd  lea     r8, aSqlNtdbmsQuery_221; "sql\\ntdbms\\query\\qeoptim\\util\\show"...
0x101c784e4  mov     rdx, rax
0x101c784e7  mov     rcx, rbx
0x101c784ea  mov     rax, cs:__imp_?g_metadataFactory@@3UMetadataFactory@@A; MetadataFactory g_metadataFactory
0x101c784f1  call    qword ptr [rax]
0x101c784f3  mov     [rsp+1538h+var_14C8], rax
0x101c784f8  mov     r10, [rax]
0x101c784fb  mov     rcx, [rsp+1538h+var_1440]
0x101c78503  movzx   edx, word ptr [rcx+28h]
0x101c78507  xor     ebx, ebx
0x101c78509  mov     dword ptr [rsp+1538h+var_1510], ebx
0x101c7850d  mov     dword ptr [rsp+1538h+var_1518], ebx
0x101c78511  xor     r9d, r9d
0x101c78514  xor     r8d, r8d
0x101c78517  mov     rcx, rax
0x101c7851a  call    qword ptr [r10+38h]
0x101c7851e  mov     r10, [rax]
0x101c78521  mov     [rsp+1538h+var_1500], ebx
0x101c78525  mov     [rsp+1538h+var_1508], ebx
0x101c78529  mov     byte ptr [rsp+1538h+var_1510], 1
0x101c7852e  mov     byte ptr [rsp+1538h+var_1518], bl
0x101c78532  xor     r9d, r9d
0x101c78535  mov     r8b, 1
0x101c78538  mov     edx, edi
0x101c7853a  mov     rcx, rax
0x101c7853d  call    qword ptr [r10+78h]
0x101c78541  jmp     loc_101C78623
0x101c78546  mov     rdx, gs:58h
0x101c7854f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101c78556  mov     ecx, [rax]
0x101c78558  lea     r9, ds:0[rcx*8]
0x101c78560  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101c78567  mov     r8d, [rax]
0x101c7856a  mov     rax, [r9+rdx]
0x101c7856e  mov     rcx, [r8+rax]
0x101c78572  mov     [rsp+1538h+var_14A8], rcx
0x101c7857a  mov     rsi, [rcx+90h]
0x101c78581  mov     rax, gs:58h
0x101c7858a  mov     rdi, [rax+r9]
0x101c7858e  add     rdi, r8
0x101c78591  mov     rbx, [rdi+100h]
0x101c78598  test    rbx, rbx
0x101c7859b  jnz     short loc_101C785AC
0x101c7859d  xor     ecx, ecx
0x101c7859f  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101c785a5  mov     rbx, [rdi+100h]
0x101c785ac  mov     rbx, [rbx+3E8h]
0x101c785b3  mov     rax, [rsi]
0x101c785b6  mov     rcx, rsi
0x101c785b9  call    qword ptr [rax+1B0h]
0x101c785bf  mov     r9d, 0A06h
0x101c785c5  lea     r8, aSqlNtdbmsQuery_221; "sql\\ntdbms\\query\\qeoptim\\util\\show"...
0x101c785cc  mov     rdx, rax
0x101c785cf  mov     rcx, rbx
0x101c785d2  mov     rax, cs:__imp_?g_metadataFactory@@3UMetadataFactory@@A; MetadataFactory g_metadataFactory
0x101c785d9  call    qword ptr [rax]
0x101c785db  mov     [rsp+1538h+var_14C8], rax
0x101c785e0  mov     r10, [rax]
0x101c785e3  mov     [rsp+1538h+var_14E8], 0
0x101c785e8  xor     ecx, ecx
0x101c785ea  mov     [rsp+1538h+var_14F0], ecx
0x101c785ee  mov     [rsp+1538h+var_14F8], ecx
0x101c785f2  mov     qword ptr [rsp+1538h+var_1500], rcx
0x101c785f7  mov     qword ptr [rsp+1538h+var_1508], rcx
0x101c785fc  mov     [rsp+1538h+var_1510], rcx
0x101c78601  mov     [rsp+1538h+var_1518], rcx
0x101c78606  lea     r9d, [rcx+6]
0x101c7860a  mov     r8b, 1
0x101c7860d  lea     rdx, [rsp+1538h+var_1390]
0x101c78615  mov     rcx, rax
0x101c78618  call    qword ptr [r10+28h]
0x101c7861c  mov     esi, [rsp+1538h+var_1480]
0x101c78623  mov     [rsp+1538h+var_14B8], rax
0x101c7862b  mov     rbx, rax
0x101c7862e  test    rax, rax
0x101c78631  jnz     short loc_101C78650
0x101c78633  mov     [rsp+1538h+var_1510], r14
0x101c78638  mov     dword ptr [rsp+1538h+var_1518], esi
0x101c7863c  lea     edx, [rax+6]
0x101c7863f  lea     ecx, [rax+1Bh]
0x101c78642  lea     r9d, [rax+2]
0x101c78646  lea     r8d, [rax+10h]
0x101c7864a  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101c78650  mov     rax, [rbx]
0x101c78653  lea     rdx, [rsp+1538h+var_1320]
0x101c7865b  mov     rcx, rbx
0x101c7865e  call    qword ptr [rax+60h]
0x101c78661  mov     rdx, gs:58h
0x101c7866a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101c78671  mov     ecx, [rax]
0x101c78673  lea     r8, ds:0[rcx*8]
0x101c7867b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101c78682  mov     r9d, [rax]
0x101c78685  mov     rax, [r8+rdx]
0x101c78689  cmp     qword ptr [r9+rax], 0
0x101c7868e  jz      loc_101C7871B
0x101c78694  mov     rax, gs:58h
0x101c7869d  mov     rax, [r8+rax]
0x101c786a1  mov     rcx, [rax+r9]
0x101c786a5  cmp     qword ptr [rcx+80h], 0
0x101c786ad  jz      short loc_101C786D9
0x101c786af  mov     rax, gs:58h
0x101c786b8  mov     rax, [r8+rax]
0x101c786bc  mov     rcx, [rax+r9]
0x101c786c0  mov     rax, [rcx+80h]
0x101c786c7  mov     ecx, [rax+4Ch]
0x101c786ca  shr     ecx, 0Dh
0x101c786cd  and     cl, 1
0x101c786d0  mov     [rsp+1538h+var_14B0], cl
0x101c786d7  jnz     short loc_101C7870F
0x101c786d9  mov     rax, gs:58h
0x101c786e2  mov     rax, [r8+rax]
0x101c786e6  mov     rcx, [rax+r9]
0x101c786ea  cmp     qword ptr [rcx+48h], 0
0x101c786ef  jz      short loc_101C7871B
0x101c786f1  mov     rax, gs:58h
0x101c786fa  mov     rax, [r8+rax]
0x101c786fe  mov     rcx, [rax+r9]
0x101c78702  mov     rax, [rcx+48h]
0x101c78706  test    byte ptr [rax+10Eh], 2
0x101c7870d  jz      short loc_101C7871B
0x101c7870f  mov     rax, cs:qword_102EF3550
0x101c78716  jmp     loc_101C787E9
0x101c7871b  mov     rax, cs:qword_102EF3550
0x101c78722  cmp     byte ptr [rax+313h], 0
0x101c78729  jz      loc_101C787E9
0x101c7872f  mov     ecx, [rsp+1538h+var_1318]
0x101c78736  cmp     ecx, 5445h
0x101c7873c  jnz     loc_101C787F0
0x101c78742  lea     rax, aShowStatistics_0; "show_statistics"
0x101c78749  mov     [rsp+1538h+var_1510], rax
0x101c7874e  mov     dword ptr [rsp+1538h+var_1518], 1Eh
0x101c78756  mov     edx, 12h
0x101c7875b  mov     ecx, 195h
0x101c78760  lea     r9d, [rdx-0Ch]
0x101c78764  lea     r8d, [rdx-2]
0x101c78768  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101c7876e  nop
0x101c7876f  mov     rcx, [rsp+1538h+var_14C8]
0x101c78774  mov     rax, [rcx]
0x101c78777  mov     edx, 1
0x101c7877c  call    qword ptr [rax]
0x101c7877e  nop
0x101c7877f  mov     rcx, [rsp+1538h+var_1478]
0x101c78787  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x101c7878d  nop
0x101c7878e  lea     rcx, [rsp+1538h+var_1408]; this
0x101c78796  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x101c7879b  nop
0x101c7879c  mov     r8, gs:58h
0x101c787a5  mov     rax, cs:__imp_SystemThread_TlsIndex
  ... truncated ...
```
