# CFsrmPipelineModuleImplWrapper::ProcessBatch(_FsrmPipelinePhase,ulong,_FSRM_PROPERTYBAG_FIELDS * *,_FSRM_PROPERTYBAG_ARRAYS * *,_FSRM_PROPERTY_CACHE * *,_FSRM_IN_FILE_SECURE_PROPERTIES * *,IFsrmBatchedPipelineModuleCallback *,_FSRM_PROPERTYBAG_FIELDS_DELTA * *)

- ea: `0x1800ae4b0`
- end: `0x1800aeafa`
- name: `?ProcessBatch@CFsrmPipelineModuleImplWrapper@@UEAAJW4_FsrmPipelinePhase@@KPEAPEAU_FSRM_PROPERTYBAG_FIELDS@@PEAPEAU_FSRM_PROPERTYBAG_ARRAYS@@PEAPEAU_FSRM_PROPERTY_CACHE@@PEAPEAU_FSRM_IN_FILE_SECURE_PROPERTIES@@PEAUIFsrmBatchedPipelineModuleCallback@@PEAPEAU_FSRM_PROPERTYBAG_FIELDS_DELTA@@@Z`
- size: `1610`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, __int64, __int64, __int64, __int64, IUnknown *pUnk, _QWORD *)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001350`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000ed14`
- `0x180040528`
- `0x18004513c`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180084bc4`
- `0x1800aa9ac`
- `0x1800ab194`
- `0x1800ae4b0`
- `0x1800aeb00`
- `0x1800af5d0`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800ae671`
- `ole32!CoTaskMemAlloc` at `0x1800ae671`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x1800ae62d`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x1800ae62d`
- `KERNEL32!SetThreadpoolTimer` at `0x1800ae86a`
- `KERNEL32!SetThreadpoolTimer` at `0x1800ae8b5`
- `KERNEL32!SetThreadpoolTimer` at `0x1800ae971`
- `KERNEL32!SetThreadpoolTimer` at `0x1800ae86a`
- `KERNEL32!SetThreadpoolTimer` at `0x1800ae8b5`
- `KERNEL32!SetThreadpoolTimer` at `0x1800ae971`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800ae8c7`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800ae983`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800ae8c7`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800ae983`

## string_xrefs

- `0x1800ae530`: `base\fs\fsrm\service\modulewrp\modulewrp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CFsrmPipelineModuleImplWrapper::ProcessBatch(
        __int64 a1,
        int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        IUnknown *pUnk,
        _QWORD *a9)
{
  __int64 v9; // r12
  __int64 v10; // r13
  __int64 v12; // rdi
  _WORD *v13; // rax
  HRESULT v14; // eax
  void *v15; // rax
  void *v16; // r15
  __int64 v17; // rcx
  unsigned int i; // esi
  unsigned int j; // r14d
  __int64 v20; // r10
  __int64 v21; // r12
  __int64 v22; // r11
  __int64 v23; // r9
  __int64 *v24; // rdx
  _QWORD *v25; // rsi
  __int64 v26; // rdx
  void **v27; // r9
  __int64 v28; // rcx
  unsigned int v29; // r14d
  void *v30; // rsi
  char *k; // rdi
  char Hr; // al
  int v34; // eax
  char v35; // al
  char v36; // al
  _QWORD *v39; // [rsp+78h] [rbp-230h] BYREF
  int v40; // [rsp+80h] [rbp-228h] BYREF
  void *v41; // [rsp+88h] [rbp-220h]
  void *v42[2]; // [rsp+90h] [rbp-218h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-208h]
  int v44; // [rsp+B0h] [rbp-1F8h] BYREF
  __int64 v45; // [rsp+B8h] [rbp-1F0h]
  __int64 *v46; // [rsp+C0h] [rbp-1E8h]
  IUnknown *v47; // [rsp+C8h] [rbp-1E0h]
  __int64 v48; // [rsp+D0h] [rbp-1D8h]
  _QWORD *v49; // [rsp+D8h] [rbp-1D0h]
  _com_error *v50; // [rsp+E0h] [rbp-1C8h] BYREF
  const exception *v51; // [rsp+E8h] [rbp-1C0h] BYREF
  _QWORD v52[3]; // [rsp+F0h] [rbp-1B8h] BYREF
  int v53; // [rsp+108h] [rbp-1A0h]
  int v54; // [rsp+10Ch] [rbp-19Ch]
  int v55; // [rsp+110h] [rbp-198h]
  _DWORD v56[26]; // [rsp+118h] [rbp-190h] BYREF
  void *Block[2]; // [rsp+180h] [rbp-128h] BYREF
  __int64 v58; // [rsp+190h] [rbp-118h]
  unsigned __int64 v59; // [rsp+198h] [rbp-110h]
  void **v60; // [rsp+1B0h] [rbp-F8h] BYREF
  HRESULT v61; // [rsp+1B8h] [rbp-F0h]
  unsigned int v62; // [rsp+1DCh] [rbp-CCh]

  v9 = a4;
  v48 = a4;
  v10 = a3;
  v12 = a1;
  v45 = a5;
  v47 = pUnk;
  v49 = a9;
  v39 = v52;
  v52[0] = L"base\\fs\\fsrm\\service\\modulewrp\\modulewrp.cpp";
  v52[1] = L"CFsrmPipelineModuleImplWrapper::ProcessBatch";
  v52[2] = L"MODIMPWC";
  v53 = 480;
  v54 = 24;
  v55 = 255;
  v56[24] = 0x1000000;
  memset_0(v56, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer(&v60, v52, 0);
  *(_OWORD *)v42 = 0;
  v43 = 0;
  *a9 = 0;
  *(_DWORD *)(v12 + 672) = -1;
  if ( *(_QWORD *)(v12 + 656) < 8u )
    v13 = (_WORD *)(v12 + 632);
  else
    v13 = *(_WORD **)(v12 + 632);
  *(_QWORD *)(v12 + 648) = 0;
  *v13 = 0;
  try
  {
    if ( !*(_BYTE *)(v12 + 64) )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v60, -2147200234);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v60, 0x1F0u, Hr, 0);
    }
    v61 = 0;
    if ( *(_QWORD *)(v12 + 616) )
    {
      v14 = CoMarshalInterThreadInterfaceInStream(
              &GUID_b04e1334_9862_4cb1_8fc0_b58c37cbe2a7,
              pUnk,
              (LPSTREAM *)(v12 + 680));
      v61 = v14;
      if ( v14 < 0 )
      {
        v34 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v60, v34);
        v35 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v60, 0x1F7u, v35, 0);
      }
      v61 = v14;
    }
    *(_DWORD *)(v12 + 544) = a2;
    v40 = 0;
    v41 = 0;
    v15 = CoTaskMemAlloc(40 * v10);
    v16 = v15;
    if ( !v15 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v60, -2147024882);
      v36 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v60, 0x20Eu, v36, 0);
    }
    v61 = 0;
    memset_0(v15, 0, 40 * v10);
    v40 = v10;
    v41 = v16;
    if ( a2 == 2 && *(_DWORD *)(v12 + 340) == 1 )
    {
      for ( i = 0; i < (unsigned int)v10; ++i )
        CFsrmPipelineModuleImplWrapper::AddFileId(v17, v42, *(_QWORD *)(v9 + 8LL * i));
      SrmPrefetchNtfsMetaData(v42);
    }
    for ( j = 0; j < (unsigned int)v10; ++j )
    {
      v20 = *(_QWORD *)(v9 + 8LL * j);
      if ( v20 )
      {
        v59 = 7;
        v58 = 0;
        LOWORD(Block[0]) = 0;
        v39 = 0;
        v21 = *(_QWORD *)(v45 + 8LL * j);
        v22 = 0;
        if ( a6 )
          v22 = *(_QWORD *)(a6 + 8LL * j);
        v23 = 0;
        if ( a7 )
          v23 = *(_QWORD *)(a7 + 8LL * j);
        v24 = &CPropertyBagProxy::s_ftNeverModified;
        v46 = &CPropertyBagProxy::s_ftNeverModified;
        if ( *(_DWORD *)(v20 + 56) != -1 && *(_DWORD *)(v20 + 60) != -1 )
        {
          v24 = (__int64 *)(*(_QWORD *)(56LL * *(unsigned int *)(v20 + 56) + *(_QWORD *)(v12 + 136) + 16)
                          + 88LL * *(unsigned int *)(v20 + 60)
                          + 48);
          v46 = v24;
        }
        CPropertyBagProxy::CreateInstance(
          j,
          v20,
          v21,
          v22,
          a2 == 5,
          v23,
          (__int64)v47,
          (__int64)v16 + 40 * j,
          (__int64)v24,
          v12 + 272,
          &v39);
        v25 = v39;
        LOBYTE(v26) = 1;
        CPropertyBagFieldsBase::BuildFullPath(v39 + 11, v26, 0, Block);
        *(_DWORD *)(v12 + 672) = j;
        std::wstring::assign((void *)(v12 + 632));
        if ( *(_QWORD *)(v12 + 616) )
          SetThreadpoolTimer(*(PTP_TIMER *)(v12 + 616), (PFILETIME)(v12 + 624), 0, 0);
        v27 = Block;
        if ( v59 >= 8 )
          v27 = (void **)Block[0];
        CFsrmPipelineModuleImplWrapper::ProcessPropertyBag(v12 - 32, a2, v25, (__int64)v27);
        if ( *(_QWORD *)(v12 + 616) )
        {
          SetThreadpoolTimer(*(PTP_TIMER *)(v12 + 616), 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)(v12 + 616), 1);
        }
        if ( v25 )
          (*(void (__fastcall **)(_QWORD *))(*v25 + 16LL))(v25);
        if ( v59 >= 8 )
          operator delete(Block[0]);
        v59 = 7;
        v58 = 0;
        LOWORD(Block[0]) = 0;
        v9 = v48;
      }
    }
    v41 = 0;
    *v49 = v16;
    CPropertyBagFieldsDeltaBatch::~CPropertyBagFieldsDeltaBatch((CPropertyBagFieldsDeltaBatch *)&v40);
  }
  catch ( long v44 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v60,
      v44,
      L"base\\fs\\fsrm\\service\\modulewrp\\modulewrp.cpp",
      L"MODIMPWC",
      L"CFsrmPipelineModuleImplWrapper::ProcessBatch",
      0x27Fu,
      v62);
    v12 = a1;
  }
  catch ( _com_error *v50 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v60,
      v50,
      L"base\\fs\\fsrm\\service\\modulewrp\\modulewrp.cpp",
      L"MODIMPWC",
      L"CFsrmPipelineModuleImplWrapper::ProcessBatch",
      0x27Fu,
      v62);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v60,
      L"base\\fs\\fsrm\\service\\modulewrp\\modulewrp.cpp",
      L"MODIMPWC",
      L"CFsrmPipelineModuleImplWrapper::ProcessBatch",
      0x27Fu,
      v62);
    v12 = a1;
  }
  catch ( const exception *v51 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v60,
      v51,
      L"base\\fs\\fsrm\\service\\modulewrp\\modulewrp.cpp",
      L"MODIMPWC",
      L"CFsrmPipelineModuleImplWrapper::ProcessBatch",
      0x27Fu,
      v62);
  }
  if ( !*(_BYTE *)(v12 + 64) )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v60, -2147200234);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v60, 0x1F0u, Hr, 0);
  }
  v61 = 0;
  if ( *(_QWORD *)(v12 + 616) )
  {
    v14 = CoMarshalInterThreadInterfaceInStream(
            &GUID_b04e1334_9862_4cb1_8fc0_b58c37cbe2a7,
            pUnk,
            (LPSTREAM *)(v12 + 680));
    v61 = v14;
    if ( v14 < 0 )
    {
      v34 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v60, v34);
      v35 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v60, 0x1F7u, v35, 0);
    }
    v61 = v14;
  }
  *(_DWORD *)(v12 + 544) = a2;
  v40 = 0;
  v41 = 0;
  v15 = CoTaskMemAlloc(40 * v10);
  v16 = v15;
  if ( !v15 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v60, -2147024882);
    v36 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v60, 0x20Eu, v36, 0);
  }
  v61 = 0;
  memset_0(v15, 0, 40 * v10);
}

```

## disassembly

```asm
0x1800ae4b0  mov     r11, rsp
0x1800ae4b3  push    rbx
0x1800ae4b4  push    rsi
0x1800ae4b5  push    rdi
0x1800ae4b6  push    r12
0x1800ae4b8  push    r13
0x1800ae4ba  push    r14
0x1800ae4bc  push    r15
0x1800ae4be  sub     rsp, 270h
0x1800ae4c5  mov     rax, cs:__security_cookie
0x1800ae4cc  xor     rax, rsp
0x1800ae4cf  mov     [rsp+2A8h+var_48], rax
0x1800ae4d7  mov     r12, r9
0x1800ae4da  mov     [rsp+2A8h+var_1D8], r9
0x1800ae4e2  mov     r13d, r8d
0x1800ae4e5  mov     r14d, edx
0x1800ae4e8  mov     [rsp+2A8h+var_248], edx
0x1800ae4ec  mov     rdi, rcx
0x1800ae4ef  mov     [rsp+2A8h+var_240], rcx
0x1800ae4f4  mov     rax, [rsp+2A8h+arg_20]
0x1800ae4fc  mov     [rsp+2A8h+var_1F0], rax
0x1800ae504  mov     r15, [rsp+2A8h+pUnk]
0x1800ae50c  mov     [rsp+2A8h+var_1E0], r15
0x1800ae514  mov     rsi, [rsp+2A8h+arg_40]
0x1800ae51c  mov     [rsp+2A8h+var_1D0], rsi
0x1800ae524  lea     rax, [r11-1B8h]
0x1800ae52b  mov     [rsp+2A8h+var_230], rax
0x1800ae530  lea     rax, aBaseFsFsrmServ_33; "base\\fs\\fsrm\\service\\modulewrp\\mod"...
0x1800ae537  mov     [r11-1B8h], rax
0x1800ae53e  lea     rax, aCfsrmpipelinem_29; "CFsrmPipelineModuleImplWrapper::Process"...
0x1800ae545  mov     [r11-1B0h], rax
0x1800ae54c  lea     rax, aModimpwc; "MODIMPWC"
0x1800ae553  mov     [r11-1A8h], rax
0x1800ae55a  mov     [rsp+2A8h+var_1A0], 1E0h
0x1800ae565  mov     [rsp+2A8h+var_19C], 18h
0x1800ae570  mov     [rsp+2A8h+var_198], 0FFh
0x1800ae57b  xor     ebx, ebx
0x1800ae57d  mov     [rsp+2A8h+var_130], 1000000h
0x1800ae588  xor     edx, edx; Val
0x1800ae58a  lea     r8d, [rbx+60h]; Size
0x1800ae58e  lea     rcx, [r11-190h]; void *
0x1800ae595  call    memset_0
0x1800ae59a  nop
0x1800ae59b  xor     r8d, r8d
0x1800ae59e  lea     rdx, [rsp+2A8h+var_1B8]
0x1800ae5a6  lea     rcx, [rsp+2A8h+var_F8]
0x1800ae5ae  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800ae5b3  nop
0x1800ae5b4  xorps   xmm0, xmm0
0x1800ae5b7  movdqu  xmmword ptr [rsp+2A8h+var_218], xmm0
0x1800ae5c0  mov     [rsp+2A8h+var_208], rbx
0x1800ae5c8  mov     [rsi], rbx
0x1800ae5cb  mov     dword ptr [rdi+2A0h], 0FFFFFFFFh
0x1800ae5d5  lea     rcx, [rdi+278h]
0x1800ae5dc  cmp     qword ptr [rcx+18h], 8
0x1800ae5e1  jb      short loc_1800AE5E8
0x1800ae5e3  mov     rax, [rcx]
0x1800ae5e6  jmp     short loc_1800AE5EB
0x1800ae5e8  mov     rax, rcx
0x1800ae5eb  mov     [rcx+10h], rbx
0x1800ae5ef  mov     [rax], bx
0x1800ae5f2  mov     eax, [rsp+2A8h+var_F0]
0x1800ae5f9  mov     [rsp+2A8h+var_F0], eax
0x1800ae600  cmp     [rdi+40h], bl
0x1800ae603  jz      loc_1800AEA48
0x1800ae609  mov     [rsp+2A8h+var_F0], ebx
0x1800ae610  mov     rax, [rdi+268h]
0x1800ae617  test    rax, rax
0x1800ae61a  jz      short loc_1800AE649
0x1800ae61c  lea     r8, [rdi+2A8h]; ppStm
0x1800ae623  mov     rdx, r15; pUnk
0x1800ae626  lea     rcx, _GUID_b04e1334_9862_4cb1_8fc0_b58c37cbe2a7; riid
0x1800ae62d  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x1800ae633  mov     [rsp+2A8h+var_F0], eax
0x1800ae63a  test    eax, eax
0x1800ae63c  js      loc_1800AEA7F
0x1800ae642  mov     [rsp+2A8h+var_F0], eax
0x1800ae649  mov     [rdi+220h], r14d
0x1800ae650  mov     [rsp+2A8h+var_228], ebx
0x1800ae657  mov     [rsp+2A8h+var_220], rbx
0x1800ae65f  lea     rsi, ds:0[r13*4]
0x1800ae667  add     rsi, r13
0x1800ae66a  shl     rsi, 3
0x1800ae66e  mov     rcx, rsi; cb
0x1800ae671  call    cs:__imp_CoTaskMemAlloc
0x1800ae677  mov     r15, rax
0x1800ae67a  mov     ecx, [rsp+2A8h+var_F0]
0x1800ae681  mov     [rsp+2A8h+var_F0], ecx
0x1800ae688  test    rax, rax
0x1800ae68b  jz      loc_1800AEAC1
0x1800ae691  mov     [rsp+2A8h+var_F0], ebx
0x1800ae698  mov     r8, rsi; Size
0x1800ae69b  xor     edx, edx; Val
0x1800ae69d  mov     rcx, rax; void *
0x1800ae6a0  call    memset_0
0x1800ae6a5  mov     [rsp+2A8h+var_228], r13d
0x1800ae6ad  mov     [rsp+2A8h+var_220], r15
0x1800ae6b5  cmp     r14d, 2
0x1800ae6b9  jnz     short loc_1800AE6F8
0x1800ae6bb  cmp     dword ptr [rdi+154h], 1
0x1800ae6c2  jnz     short loc_1800AE6F8
0x1800ae6c4  mov     esi, ebx
0x1800ae6c6  mov     [rsp+2A8h+var_238], ebx
0x1800ae6ca  cmp     esi, r13d
0x1800ae6cd  jnb     short loc_1800AE6EB
0x1800ae6cf  mov     r8d, esi
0x1800ae6d2  mov     r8, [r12+r8*8]
0x1800ae6d6  lea     rdx, [rsp+2A8h+var_218]
0x1800ae6de  call    ?AddFileId@CFsrmPipelineModuleImplWrapper@@AEAAXAEAV?$vector@UFSRM_VOLUME_FILE_IDS@@V?$allocator@UFSRM_VOLUME_FILE_IDS@@@std@@@std@@PEBU_FSRM_PROPERTYBAG_FIELDS@@@Z; CFsrmPipelineModuleImplWrapper::AddFileId(std::vector<FSRM_VOLUME_FILE_IDS> &,_FSRM_PROPERTYBAG_FIELDS const *)
0x1800ae6e3  inc     esi
0x1800ae6e5  mov     [rsp+2A8h+var_238], esi
0x1800ae6e9  jmp     short loc_1800AE6CA
0x1800ae6eb  lea     rcx, [rsp+2A8h+var_218]
0x1800ae6f3  call    ?SrmPrefetchNtfsMetaData@@YAXAEAV?$vector@UFSRM_VOLUME_FILE_IDS@@V?$allocator@UFSRM_VOLUME_FILE_IDS@@@std@@@std@@@Z; SrmPrefetchNtfsMetaData(std::vector<FSRM_VOLUME_FILE_IDS> &)
0x1800ae6f8  mov     r14d, ebx
0x1800ae6fb  mov     [rsp+2A8h+var_234], ebx
0x1800ae6ff  cmp     r14d, r13d
0x1800ae702  jnb     loc_1800AE92C
0x1800ae708  mov     eax, r14d
0x1800ae70b  mov     r10, [r12+rax*8]
0x1800ae70f  test    r10, r10
0x1800ae712  jnz     short loc_1800AE719
0x1800ae714  jmp     loc_1800AE91F
0x1800ae719  mov     [rsp+2A8h+var_110], 7
0x1800ae725  mov     [rsp+2A8h+var_118], rbx
0x1800ae72d  mov     word ptr [rsp+2A8h+Block], bx
0x1800ae735  mov     [rsp+2A8h+var_230], rbx
0x1800ae73a  mov     rcx, [rsp+2A8h+var_1F0]
0x1800ae742  mov     r12, [rcx+rax*8]
0x1800ae746  mov     rcx, [rsp+2A8h+arg_28]
0x1800ae74e  test    rcx, rcx
0x1800ae751  mov     r11, rbx
0x1800ae754  jz      short loc_1800AE75A
0x1800ae756  mov     r11, [rcx+rax*8]
0x1800ae75a  mov     rcx, [rsp+2A8h+arg_30]
0x1800ae762  test    rcx, rcx
0x1800ae765  mov     r9, rbx
0x1800ae768  jz      short loc_1800AE76E
0x1800ae76a  mov     r9, [rcx+rax*8]
0x1800ae76e  lea     rax, [rax+rax*4]
0x1800ae772  lea     rsi, [r15+rax*8]
0x1800ae776  lea     rdx, ?s_ftNeverModified@CPropertyBagProxy@@2VCSrmFileTime@@B; CSrmFileTime const CPropertyBagProxy::s_ftNeverModified
0x1800ae77d  mov     [rsp+2A8h+var_1E8], rdx
0x1800ae785  cmp     dword ptr [r10+38h], 0FFFFFFFFh
0x1800ae78a  jz      short loc_1800AE7BE
0x1800ae78c  cmp     dword ptr [r10+3Ch], 0FFFFFFFFh
0x1800ae791  jz      short loc_1800AE7BE
0x1800ae793  mov     eax, [r10+38h]
0x1800ae797  imul    r8, rax, 38h ; '8'
0x1800ae79b  mov     rdx, [rdi+88h]
0x1800ae7a2  mov     eax, [r10+3Ch]
0x1800ae7a6  imul    rcx, rax, 58h ; 'X'
0x1800ae7aa  mov     rax, [r8+rdx+10h]
0x1800ae7af  lea     rdx, [rcx+30h]
0x1800ae7b3  add     rdx, rax
0x1800ae7b6  mov     [rsp+2A8h+var_1E8], rdx
0x1800ae7be  lea     rax, [rdi+110h]
0x1800ae7c5  cmp     [rsp+2A8h+var_248], 5
0x1800ae7ca  setz    cl
0x1800ae7cd  lea     r8, [rsp+2A8h+var_230]
0x1800ae7d2  mov     [rsp+2A8h+var_258], r8
0x1800ae7d7  mov     [rsp+2A8h+var_260], rax
0x1800ae7dc  mov     [rsp+2A8h+var_268], rdx
0x1800ae7e1  mov     [rsp+2A8h+var_270], rsi
0x1800ae7e6  mov     rax, [rsp+2A8h+var_1E0]
0x1800ae7ee  mov     [rsp+2A8h+var_278], rax
0x1800ae7f3  mov     [rsp+2A8h+var_280], r9
0x1800ae7f8  mov     [rsp+2A8h+var_288], cl
0x1800ae7fc  mov     r9, r11
0x1800ae7ff  mov     r8, r12
0x1800ae802  mov     rdx, r10
0x1800ae805  mov     ecx, r14d
0x1800ae808  call    ?CreateInstance@CPropertyBagProxy@@SAXKPEBU_FSRM_PROPERTYBAG_FIELDS@@PEBU_FSRM_PROPERTYBAG_ARRAYS@@PEBU_FSRM_PROPERTY_CACHE@@_NPEBU_FSRM_IN_FILE_SECURE_PROPERTIES@@PEAUIFsrmBatchedPipelineModuleCallback@@PEAU_FSRM_PROPERTYBAG_FIELDS_DELTA@@PEBVCSrmFileTime@@PEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@VCSerializedPropertyDefinition@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@VCSerializedPropertyDefinition@@@@@ATL@@@std@@@2@@std@@PEAPEAV?$CComObject@VCPropertyBagProxy@@@ATL@@@Z; CPropertyBagProxy::CreateInstance(ulong,_FSRM_PROPERTYBAG_FIELDS const *,_FSRM_PROPERTYBAG_ARRAYS const *,_FSRM_PROPERTY_CACHE const *,bool,_FSRM_IN_FILE_SECURE_PROPERTIES const *,IFsrmBatchedPipelineModuleCallback *,_FSRM_PROPERTYBAG_FIELDS_DELTA *,CSrmFileTime const *,std::map<std::wstring,ATL::CAdapt<CSrmRefPtr<CSerializedPropertyDefinition>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<CSerializedPropertyDefinition>>>>> *,ATL::CComObject<CPropertyBagProxy> * *)
0x1800ae80d  mov     rsi, [rsp+2A8h+var_230]
0x1800ae812  lea     rcx, [rsi+58h]
0x1800ae816  lea     r9, [rsp+2A8h+Block]
0x1800ae81e  xor     r8d, r8d
0x1800ae821  mov     dl, 1
0x1800ae823  call    ?BuildFullPath@CPropertyBagFieldsBase@@QEBAX_NPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CPropertyBagFieldsBase::BuildFullPath(bool,ushort const *,std::wstring &)
0x1800ae828  mov     [rdi+2A0h], r14d
0x1800ae82f  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800ae833  xor     r8d, r8d
0x1800ae836  lea     rdx, [rsp+2A8h+Block]
0x1800ae83e  lea     rcx, [rdi+278h]; void *
0x1800ae845  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800ae84a  mov     rax, [rdi+268h]
0x1800ae851  test    rax, rax
0x1800ae854  jz      short loc_1800AE870
0x1800ae856  lea     rdx, [rdi+270h]; pftDueTime
0x1800ae85d  xor     r9d, r9d; msWindowLength
0x1800ae860  xor     r8d, r8d; msPeriod
0x1800ae863  mov     rcx, [rdi+268h]; pti
0x1800ae86a  call    cs:__imp_SetThreadpoolTimer
0x1800ae870  lea     rcx, [rdi-20h]
0x1800ae874  lea     r9, [rsp+2A8h+Block]
0x1800ae87c  cmp     [rsp+2A8h+var_110], 8
0x1800ae885  cmovnb  r9, [rsp+2A8h+Block]
0x1800ae88e  mov     r8, rsi
0x1800ae891  mov     edx, [rsp+2A8h+var_248]
0x1800ae895  call    ?ProcessPropertyBag@CFsrmPipelineModuleImplWrapper@@AEAAXW4_FsrmPipelinePhase@@PEAV?$CComObject@VCPropertyBagProxy@@@ATL@@PEBG@Z; CFsrmPipelineModuleImplWrapper::ProcessPropertyBag(_FsrmPipelinePhase,ATL::CComObject<CPropertyBagProxy> *,ushort const *)
0x1800ae89a  mov     rax, [rdi+268h]
0x1800ae8a1  test    rax, rax
0x1800ae8a4  jz      short loc_1800AE8CE
0x1800ae8a6  xor     r9d, r9d; msWindowLength
0x1800ae8a9  xor     r8d, r8d; msPeriod
0x1800ae8ac  xor     edx, edx; pftDueTime
0x1800ae8ae  mov     rcx, [rdi+268h]; pti
0x1800ae8b5  call    cs:__imp_SetThreadpoolTimer
0x1800ae8bb  mov     edx, 1; fCancelPendingCallbacks
0x1800ae8c0  mov     rcx, [rdi+268h]; pti
0x1800ae8c7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800ae8cd  nop
0x1800ae8ce  test    rsi, rsi
0x1800ae8d1  jz      short loc_1800AE8E3
0x1800ae8d3  mov     rax, [rsi]
0x1800ae8d6  mov     rcx, rsi
0x1800ae8d9  mov     rax, [rax+10h]
0x1800ae8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae8e2  nop
0x1800ae8e3  cmp     [rsp+2A8h+var_110], 8
0x1800ae8ec  jb      short loc_1800AE8FB
0x1800ae8ee  mov     rcx, [rsp+2A8h+Block]; Block
0x1800ae8f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ae8fb  mov     [rsp+2A8h+var_110], 7
0x1800ae907  mov     [rsp+2A8h+var_118], rbx
0x1800ae90f  mov     word ptr [rsp+2A8h+Block], bx
0x1800ae917  mov     r12, [rsp+2A8h+var_1D8]
0x1800ae91f  inc     r14d
0x1800ae922  mov     [rsp+2A8h+var_234], r14d
0x1800ae927  jmp     loc_1800AE6FF
0x1800ae92c  mov     [rsp+2A8h+var_220], rbx
0x1800ae934  mov     rax, [rsp+2A8h+var_1D0]
0x1800ae93c  mov     [rax], r15
0x1800ae93f  lea     rcx, [rsp+2A8h+var_228]; this
0x1800ae947  call    ??1CPropertyBagFieldsDeltaBatch@@QEAA@XZ; CPropertyBagFieldsDeltaBatch::~CPropertyBagFieldsDeltaBatch(void)
0x1800ae94c  nop
0x1800ae94d  jmp     short loc_1800AE956
0x1800ae94f  mov     rdi, [rsp+2A8h+var_240]
0x1800ae954  xor     ebx, ebx
0x1800ae956  mov     rax, [rdi+268h]
0x1800ae95d  test    rax, rax
0x1800ae960  jz      short loc_1800AE989
0x1800ae962  xor     r9d, r9d; msWindowLength
0x1800ae965  xor     r8d, r8d; msPeriod
0x1800ae968  xor     edx, edx; pftDueTime
0x1800ae96a  mov     rcx, [rdi+268h]; pti
0x1800ae971  call    cs:__imp_SetThreadpoolTimer
0x1800ae977  mov     edx, 1; fCancelPendingCallbacks
0x1800ae97c  mov     rcx, [rdi+268h]; pti
0x1800ae983  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800ae989  mov     rcx, [rdi+2A8h]
0x1800ae990  test    rcx, rcx
0x1800ae993  jz      short loc_1800AE9A8
0x1800ae995  mov     rax, [rcx]
0x1800ae998  mov     rax, [rax+10h]
0x1800ae99c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae9a1  mov     [rdi+2A8h], rbx
0x1800ae9a8  mov     r14d, [rsp+2A8h+var_F0]
0x1800ae9b0  mov     rsi, [rsp+2A8h+var_218]
0x1800ae9b8  test    rsi, rsi
0x1800ae9bb  jz      short loc_1800AE9E8
0x1800ae9bd  mov     rdi, rsi
0x1800ae9c0  cmp     rsi, [rsp+2A8h+var_218+8]
0x1800ae9c8  jz      short loc_1800AE9E0
0x1800ae9ca  mov     rdx, rdi
0x1800ae9cd  call    ??$_Dest_val@V?$allocator@UFSRM_VOLUME_FILE_IDS@@@std@@UFSRM_VOLUME_FILE_IDS@@@std@@YAXAEAV?$allocator@UFSRM_VOLUME_FILE_IDS@@@0@PEAUFSRM_VOLUME_FILE_IDS@@@Z; std::_Dest_val<std::allocator<FSRM_VOLUME_FILE_IDS>,FSRM_VOLUME_FILE_IDS>(std::allocator<FSRM_VOLUME_FILE_IDS> &,FSRM_VOLUME_FILE_IDS *)
0x1800ae9d2  add     rdi, 50h ; 'P'
0x1800ae9d6  cmp     rdi, [rsp+2A8h+var_218+8]
0x1800ae9de  jnz     short loc_1800AE9CA
0x1800ae9e0  mov     rcx, rsi; Block
0x1800ae9e3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ae9e8  xorps   xmm0, xmm0
0x1800ae9eb  movdqu  xmmword ptr [rsp+2A8h+var_218], xmm0
0x1800ae9f4  mov     [rsp+2A8h+var_208], rbx
0x1800ae9fc  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800aea03  mov     [rsp+2A8h+var_F8], rax
0x1800aea0b  lea     rcx, [rsp+2A8h+var_F8]; this
0x1800aea13  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800aea18  mov     eax, r14d
0x1800aea1b  mov     rcx, [rsp+2A8h+var_48]
0x1800aea23  xor     rcx, rsp; StackCookie
0x1800aea26  call    __security_check_cookie
0x1800aea2b  add     rsp, 270h
0x1800aea32  pop     r15
0x1800aea34  pop     r14
0x1800aea36  pop     r13
0x1800aea38  pop     r12
0x1800aea3a  pop     rdi
0x1800aea3b  pop     rsi
0x1800aea3c  pop     rbx
0x1800aea3d  retn
0x1800aea3e  jmp     loc_1800AE94F
0x1800aea43  jmp     loc_1800AE94F
0x1800aea48  mov     edx, 80045316h; int
0x1800aea4d  lea     rcx, [rsp+2A8h+var_F8]; this
0x1800aea55  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800aea5a  lea     rcx, [rsp+2A8h+var_F8]; this
0x1800aea62  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800aea67  mov     r8d, eax; char
0x1800aea6a  xor     r9d, r9d; unsigned __int16 *
  ... truncated ...
```
