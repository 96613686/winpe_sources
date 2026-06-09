# CVssProviderManager::UnloadInternalProvidersArray(void)

- ea: `0x1400376e0`
- end: `0x140037d18`
- name: `?UnloadInternalProvidersArray@CVssProviderManager@@SAXXZ`
- size: `1592`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140007250`
- `0x140037200`

## callees

- `0x1400088fc`
- `0x140011440`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013cb0`
- `0x140015950`
- `0x14001b9c0`
- `0x1400376e0`
- `0x140047574`
- `0x14005b148`
- `0x140091584`
- `0x1400921dc`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400377a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400379bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400377a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400379bb`
- `VssTrace!__imp_VssTraceMessage` at `0x1400378b0`
- `VssTrace!__imp_VssTraceMessage` at `0x140037ad6`
- `VssTrace!__imp_VssTraceMessage` at `0x1400378b0`
- `VssTrace!__imp_VssTraceMessage` at `0x140037ad6`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140037803`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140037a25`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140037803`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140037a25`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400377f4`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140037a13`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400377f4`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140037a13`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x140037c0d`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x140037c0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400378cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140037af5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400378cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140037af5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void CVssProviderManager::UnloadInternalProvidersArray(void)
{
  int v0; // eax
  __int64 v1; // rcx
  int v2; // r12d
  int v3; // edi
  __int64 i; // rdi
  void *v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  __int64 j; // rdi
  void *v9; // rcx
  unsigned int k; // edi
  void *v11; // rdi
  unsigned __int64 v12; // [rsp+50h] [rbp-218h] BYREF
  int v13; // [rsp+58h] [rbp-210h]
  const unsigned __int16 *v14; // [rsp+60h] [rbp-208h]
  const unsigned __int16 *v15; // [rsp+68h] [rbp-200h]
  __int64 v16; // [rsp+70h] [rbp-1F8h]
  const unsigned __int16 *v17; // [rsp+78h] [rbp-1F0h]
  unsigned int v18; // [rsp+80h] [rbp-1E8h]
  DWORD TickCount; // [rsp+84h] [rbp-1E4h]
  int v20; // [rsp+88h] [rbp-1E0h]
  __int128 v21; // [rsp+90h] [rbp-1D8h]
  __int128 v22; // [rsp+A0h] [rbp-1C8h]
  __int64 v23; // [rsp+B0h] [rbp-1B8h]
  const unsigned __int16 *v24; // [rsp+C0h] [rbp-1A8h] BYREF
  const unsigned __int16 *v25; // [rsp+C8h] [rbp-1A0h]
  const unsigned __int16 *v26; // [rsp+D0h] [rbp-198h]
  __int64 v27; // [rsp+D8h] [rbp-190h]
  unsigned int v28; // [rsp+E0h] [rbp-188h]
  int v29; // [rsp+E4h] [rbp-184h]
  LPVOID pv; // [rsp+E8h] [rbp-180h] BYREF
  unsigned int v31; // [rsp+F0h] [rbp-178h]
  DWORD v32; // [rsp+F4h] [rbp-174h]
  int v33; // [rsp+F8h] [rbp-170h]
  __int128 v34; // [rsp+100h] [rbp-168h]
  __int128 v35; // [rsp+110h] [rbp-158h]
  __int64 v36; // [rsp+120h] [rbp-148h]
  int v37; // [rsp+160h] [rbp-108h]
  const unsigned __int16 *v38; // [rsp+170h] [rbp-F8h] BYREF
  wchar_t *v39; // [rsp+178h] [rbp-F0h]
  const unsigned __int16 *v40; // [rsp+180h] [rbp-E8h]
  int v41; // [rsp+188h] [rbp-E0h]
  int v42; // [rsp+18Ch] [rbp-DCh]
  int v43; // [rsp+190h] [rbp-D8h]
  LPVOID v44[15]; // [rsp+198h] [rbp-D0h] BYREF
  int v45; // [rsp+210h] [rbp-58h]
  int v46; // [rsp+218h] [rbp-50h] BYREF
  LPCRITICAL_SECTION v47; // [rsp+220h] [rbp-48h] BYREF
  char v48; // [rsp+228h] [rbp-40h]
  _com_error *v49; // [rsp+230h] [rbp-38h] BYREF
  const std::exception *v50; // [rsp+238h] [rbp-30h] BYREF
  __int64 v51; // [rsp+270h] [rbp+8h] BYREF

  v24 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
  v25 = L"CVssProviderManager::UnloadInternalProvidersArray";
  v26 = L"CORPRVMC";
  v27 = 0x100000478LL;
  v28 = 255;
  v37 = 0x1000000;
  memset_0(&pv, 0, 0x78u);
  v13 = 0;
  v17 = L"CVssProviderManager::UnloadInternalProvidersArray";
  v14 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
  v15 = L"CORPRVMC";
  v16 = 0x100000478LL;
  TickCount = GetTickCount();
  v20 = 255;
  v12 = 0xFFFFFFFF00000000uLL;
  v23 = 0;
  v21 = 0;
  v22 = 0;
  v51 = 0;
  if ( (int)VssGetTracingContextPerThread(&v51) < 0 )
  {
    v1 = v23;
  }
  else
  {
    v0 = VssSetTracingContextPerThread(&v12);
    v1 = v23;
    if ( v0 >= 0 )
      v1 = v51;
    v23 = v1;
  }
  if ( v1 )
    v18 = *(_DWORD *)(v1 + 48) + 1;
  else
    v18 = 0;
  v2 = 160;
  v3 = 160;
  if ( v20 != 255 )
    v3 = v20;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v12) )
    VssTraceMessage(v14, v15, (unsigned int)v16, v18, HIDWORD(v16), v17, L"ENTER", v3, 0);
  if ( HIBYTE(v37) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v5 = *(&pv + i);
      if ( v5 )
      {
        CoTaskMemFree(v5);
        *(&pv + i) = 0;
      }
    }
  }
  v47 = &CVssProviderManager::m_GlobalCS;
  v48 = 0;
  v38 = L"base\\stor\\vss\\inc\\vs_types.hxx";
  v39 = L"CVssAutomaticLock2::CVssAutomaticLock2";
  v40 = L"INCTYPEH";
  v41 = 256;
  v42 = 11;
  v43 = 255;
  v45 = 0x1000000;
  memset_0(v44, 0, sizeof(v44));
  LODWORD(v25) = 0;
  pv = v39;
  v26 = v38;
  v27 = (__int64)v40;
  v28 = v41;
  v29 = v42;
  v32 = GetTickCount();
  v33 = v43;
  v24 = (const unsigned __int16 *)0xFFFFFFFF00000000LL;
  v36 = 0;
  v34 = 0;
  v35 = 0;
  v51 = 0;
  if ( (int)VssGetTracingContextPerThread(&v51) < 0 )
  {
    v7 = v36;
  }
  else
  {
    v6 = VssSetTracingContextPerThread(&v24);
    v7 = v36;
    if ( v6 >= 0 )
      v7 = v51;
    v36 = v7;
  }
  if ( v7 )
    v31 = *(_DWORD *)(v7 + 48) + 1;
  else
    v31 = 0;
  if ( v33 != 255 )
    v2 = v33;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v24) )
    VssTraceMessage(v26, v27, v28, v31, v29, pv, L"ENTER", v2, 0);
  if ( HIBYTE(v45) )
  {
    for ( j = 0; j != 15; ++j )
    {
      v9 = v44[j];
      if ( v9 )
      {
        CoTaskMemFree(v9);
        v44[j] = 0;
      }
    }
  }
  try
  {
    CVssCriticalSection::Lock(&CVssProviderManager::m_GlobalCS);
    v48 = 1;
    CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v24);
    for ( k = 0; k < dword_14014FB10; ++k )
    {
      ATL::CComPtr<IVssSnapshotProvider>::CComPtr<IVssSnapshotProvider>(
        &v51,
        (__int64 *)(qword_14014FB08 + 8LL * (int)k));
      if ( v51 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v51 + 280LL))(v51, 1);
        if ( v13 < 0 )
        {
          v38 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
          v39 = (wchar_t *)L"CVssProviderManager::UnloadInternalProvidersArray";
          v40 = L"CORPRVMC";
          v41 = 1164;
          v42 = 1;
          v43 = 255;
          v45 = 0x1000000;
          memset_0(v44, 0, sizeof(v44));
          CVssFunctionTracer::Trace(&v12, &v38, L"Cannot unload load the internal provider");
          v13 = 0;
        }
      }
      ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v51);
    }
    CoFreeUnusedLibraries();
    CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::RemoveAll(&CVssProviderManager::m_mapProviderItfOnLoadCache);
    v11 = CVssProviderManager::m_pProvidersArray;
    if ( CVssProviderManager::m_pProvidersArray )
    {
      ATL::CSimpleArray<VSS_OBJECT_PROP_Ptr,ATL::CSimpleArrayEqualHelper<VSS_OBJECT_PROP_Ptr>>::~CSimpleArray<VSS_OBJECT_PROP_Ptr,ATL::CSimpleArrayEqualHelper<VSS_OBJECT_PROP_Ptr>>((char *)CVssProviderManager::m_pProvidersArray + 8);
      operator delete(v11);
      CVssProviderManager::m_pProvidersArray = 0;
    }
    CVssAutomaticLock2::~CVssAutomaticLock2(&v47);
  }
  catch ( long v46 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v12,
      v46,
      L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx",
      L"CORPRVMC",
      L"CVssProviderManager::UnloadInternalProvidersArray",
      0x4A2u,
      HIDWORD(v16));
  }
  catch ( _com_error *v49 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v12,
      v49,
      L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx",
      L"CORPRVMC",
      L"CVssProviderManager::UnloadInternalProvidersArray",
      0x4A2u,
      HIDWORD(v16));
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v12,
      L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx",
      L"CORPRVMC",
      L"CVssProviderManager::UnloadInternalProvidersArray",
      0x4A2u,
      HIDWORD(v16));
  }
  catch ( const std::exception *v50 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v12,
      v50,
      L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx",
      L"CORPRVMC",
      L"CVssProviderManager::UnloadInternalProvidersArray",
      0x4A2u,
      HIDWORD(v16));
  }
  if ( v13 < 0 )
  {
    v38 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
    v39 = (wchar_t *)L"CVssProviderManager::UnloadInternalProvidersArray";
    v40 = L"CORPRVMC";
    v41 = 1189;
    v42 = 1;
    v43 = 255;
    v45 = 0x1000000;
    memset_0(v44, 0, sizeof(v44));
    CVssFunctionTracer::Trace(&v12, &v38, L"Exception catched 0x%08lx", (unsigned int)v13);
  }
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v12);
}

```

## disassembly

```asm
0x1400376e0  mov     rax, rsp
0x1400376e3  mov     [rax+18h], rbx
0x1400376e7  mov     [rax+20h], rsi
0x1400376eb  push    rdi
0x1400376ec  push    r12
0x1400376ee  push    r13
0x1400376f0  push    r14
0x1400376f2  push    r15
0x1400376f4  sub     rsp, 240h
0x1400376fb  lea     rsi, aBaseStorVssMod_13; "base\\stor\\vss\\modules\\coord\\src\\p"...
0x140037702  mov     [rax-1A8h], rsi
0x140037709  lea     r14, aCvssproviderma_16; "CVssProviderManager::UnloadInternalProv"...
0x140037710  mov     [rax-1A0h], r14
0x140037717  lea     r15, aCorprvmc; "CORPRVMC"
0x14003771e  mov     [rax-198h], r15
0x140037725  mov     dword ptr [rax-190h], 478h
0x14003772f  mov     dword ptr [rax-18Ch], 1
0x140037739  mov     dword ptr [rax-188h], 0FFh
0x140037743  xor     ebx, ebx
0x140037745  mov     dword ptr [rax-108h], 1000000h
0x14003774f  xor     edx, edx; Val
0x140037751  lea     r8d, [rbx+78h]; Size
0x140037755  lea     rcx, [rax-180h]; void *
0x14003775c  call    memset_0
0x140037761  mov     [rsp+268h+var_210], ebx
0x140037765  mov     rax, [rsp+268h+var_1A0]
0x14003776d  mov     [rsp+268h+var_1F0], rax
0x140037772  mov     rax, [rsp+268h+var_1A8]
0x14003777a  mov     [rsp+268h+var_208], rax
0x14003777f  mov     rax, [rsp+268h+var_198]
0x140037787  mov     [rsp+268h+var_200], rax
0x14003778c  mov     eax, dword ptr [rsp+268h+var_190]
0x140037793  mov     dword ptr [rsp+268h+var_1F8], eax
0x140037797  mov     eax, dword ptr [rsp+268h+var_190+4]
0x14003779e  mov     dword ptr [rsp+268h+var_1F8+4], eax
0x1400377a2  call    cs:__imp_GetTickCount
0x1400377a8  mov     [rsp+268h+var_1E4], eax
0x1400377af  mov     [rsp+268h+var_214], 0FFFFFFFFh
0x1400377b7  mov     eax, [rsp+268h+var_188]
0x1400377be  mov     [rsp+268h+var_1E0], eax
0x1400377c5  mov     [rsp+268h+var_218], ebx
0x1400377c9  mov     [rsp+268h+var_1B8], rbx
0x1400377d1  xorps   xmm0, xmm0
0x1400377d4  movups  [rsp+268h+var_1D8], xmm0
0x1400377dc  movups  [rsp+268h+var_1C8], xmm0
0x1400377e4  mov     [rsp+268h+arg_0], rbx
0x1400377ec  lea     rcx, [rsp+268h+arg_0]
0x1400377f4  call    cs:__imp_VssGetTracingContextPerThread
0x1400377fa  test    eax, eax
0x1400377fc  js      short loc_140037826
0x1400377fe  lea     rcx, [rsp+268h+var_218]
0x140037803  call    cs:__imp_VssSetTracingContextPerThread
0x140037809  mov     rcx, [rsp+268h+var_1B8]
0x140037811  test    eax, eax
0x140037813  cmovns  rcx, [rsp+268h+arg_0]
0x14003781c  mov     [rsp+268h+var_1B8], rcx
0x140037824  jmp     short loc_14003782E
0x140037826  mov     rcx, [rsp+268h+var_1B8]
0x14003782e  test    rcx, rcx
0x140037831  jz      short loc_140037841
0x140037833  mov     eax, [rcx+30h]
0x140037836  inc     eax
0x140037838  mov     [rsp+268h+var_1E8], eax
0x14003783f  jmp     short loc_140037848
0x140037841  mov     [rsp+268h+var_1E8], ebx
0x140037848  mov     r12d, 0A0h
0x14003784e  mov     edi, r12d
0x140037851  cmp     [rsp+268h+var_1E0], 0FFh
0x14003785c  cmovnz  edi, [rsp+268h+var_1E0]
0x140037864  lea     rcx, [rsp+268h+var_218]; this
0x140037869  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14003786e  lea     r13, aEnter; "ENTER"
0x140037875  test    eax, eax
0x140037877  jz      short loc_1400378B6
0x140037879  mov     [rsp+268h+var_228], rbx
0x14003787e  mov     [rsp+268h+var_230], edi
0x140037882  mov     [rsp+268h+var_238], r13
0x140037887  mov     rax, [rsp+268h+var_1F0]
0x14003788c  mov     [rsp+268h+var_240], rax
0x140037891  mov     eax, dword ptr [rsp+268h+var_1F8+4]
0x140037895  mov     [rsp+268h+var_248], eax
0x140037899  mov     r9d, [rsp+268h+var_1E8]
0x1400378a1  mov     r8d, dword ptr [rsp+268h+var_1F8]
0x1400378a6  mov     rdx, [rsp+268h+var_200]
0x1400378ab  mov     rcx, [rsp+268h+var_208]
0x1400378b0  call    cs:__imp_VssTraceMessage
0x1400378b6  cmp     [rsp+268h+var_105], bl
0x1400378bd  jz      short loc_1400378E6
0x1400378bf  mov     rdi, rbx
0x1400378c2  mov     rcx, [rsp+rdi*8+268h+pv]; pv
0x1400378ca  test    rcx, rcx
0x1400378cd  jz      short loc_1400378DD
0x1400378cf  call    cs:__imp_CoTaskMemFree
0x1400378d5  mov     [rsp+rdi*8+268h+pv], rbx
0x1400378dd  inc     rdi
0x1400378e0  cmp     rdi, 0Fh
0x1400378e4  jnz     short loc_1400378C2
0x1400378e6  lea     rax, ?m_GlobalCS@CVssProviderManager@@0VCVssCriticalSection@@A; CVssCriticalSection CVssProviderManager::m_GlobalCS
0x1400378ed  mov     [rsp+268h+var_48], rax
0x1400378f5  mov     [rsp+268h+var_40], bl
0x1400378fc  lea     rax, aBaseStorVssInc_3; "base\\stor\\vss\\inc\\vs_types.hxx"
0x140037903  mov     [rsp+268h+var_F8], rax
0x14003790b  lea     rax, aCvssautomaticl_0; "CVssAutomaticLock2::CVssAutomaticLock2"
0x140037912  mov     [rsp+268h+var_F0], rax
0x14003791a  lea     rax, aInctypeh; "INCTYPEH"
0x140037921  mov     [rsp+268h+var_E8], rax
0x140037929  mov     [rsp+268h+var_E0], 100h
0x140037934  mov     [rsp+268h+var_DC], 0Bh
0x14003793f  mov     [rsp+268h+var_D8], 0FFh
0x14003794a  mov     [rsp+268h+var_58], 1000000h
0x140037955  xor     edx, edx; Val
0x140037957  lea     r8d, [rdx+78h]; Size
0x14003795b  lea     rcx, [rsp+268h+var_D0]; void *
0x140037963  call    memset_0
0x140037968  mov     dword ptr [rsp+268h+var_1A0], ebx
0x14003796f  mov     rax, [rsp+268h+var_F0]
0x140037977  mov     [rsp+268h+pv], rax
0x14003797f  mov     rax, [rsp+268h+var_F8]
0x140037987  mov     [rsp+268h+var_198], rax
0x14003798f  mov     rax, [rsp+268h+var_E8]
0x140037997  mov     [rsp+268h+var_190], rax
0x14003799f  mov     eax, [rsp+268h+var_E0]
0x1400379a6  mov     [rsp+268h+var_188], eax
0x1400379ad  mov     eax, [rsp+268h+var_DC]
0x1400379b4  mov     [rsp+268h+var_184], eax
0x1400379bb  call    cs:__imp_GetTickCount
0x1400379c1  mov     [rsp+268h+var_174], eax
0x1400379c8  mov     dword ptr [rsp+268h+var_1A8+4], 0FFFFFFFFh
0x1400379d3  mov     eax, [rsp+268h+var_D8]
0x1400379da  mov     [rsp+268h+var_170], eax
0x1400379e1  mov     dword ptr [rsp+268h+var_1A8], ebx
0x1400379e8  mov     [rsp+268h+var_148], rbx
0x1400379f0  xorps   xmm0, xmm0
0x1400379f3  movups  [rsp+268h+var_168], xmm0
0x1400379fb  movups  [rsp+268h+var_158], xmm0
0x140037a03  mov     [rsp+268h+arg_0], rbx
0x140037a0b  lea     rcx, [rsp+268h+arg_0]
0x140037a13  call    cs:__imp_VssGetTracingContextPerThread
0x140037a19  test    eax, eax
0x140037a1b  js      short loc_140037A48
0x140037a1d  lea     rcx, [rsp+268h+var_1A8]
0x140037a25  call    cs:__imp_VssSetTracingContextPerThread
0x140037a2b  mov     rcx, [rsp+268h+var_148]
0x140037a33  test    eax, eax
0x140037a35  cmovns  rcx, [rsp+268h+arg_0]
0x140037a3e  mov     [rsp+268h+var_148], rcx
0x140037a46  jmp     short loc_140037A50
0x140037a48  mov     rcx, [rsp+268h+var_148]
0x140037a50  test    rcx, rcx
0x140037a53  jz      short loc_140037A63
0x140037a55  mov     eax, [rcx+30h]
0x140037a58  inc     eax
0x140037a5a  mov     [rsp+268h+var_178], eax
0x140037a61  jmp     short loc_140037A6A
0x140037a63  mov     [rsp+268h+var_178], ebx
0x140037a6a  cmp     [rsp+268h+var_170], 0FFh
0x140037a75  cmovnz  r12d, [rsp+268h+var_170]
0x140037a7e  lea     rcx, [rsp+268h+var_1A8]; this
0x140037a86  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x140037a8b  test    eax, eax
0x140037a8d  jz      short loc_140037ADC
0x140037a8f  mov     [rsp+268h+var_228], rbx
0x140037a94  mov     [rsp+268h+var_230], r12d
0x140037a99  mov     [rsp+268h+var_238], r13
0x140037a9e  mov     rax, [rsp+268h+pv]
0x140037aa6  mov     [rsp+268h+var_240], rax
0x140037aab  mov     eax, [rsp+268h+var_184]
0x140037ab2  mov     [rsp+268h+var_248], eax
0x140037ab6  mov     r9d, [rsp+268h+var_178]
0x140037abe  mov     r8d, [rsp+268h+var_188]
0x140037ac6  mov     rdx, [rsp+268h+var_190]
0x140037ace  mov     rcx, [rsp+268h+var_198]
0x140037ad6  call    cs:__imp_VssTraceMessage
0x140037adc  cmp     byte ptr [rsp+268h+var_58+3], bl
0x140037ae3  jz      short loc_140037B0C
0x140037ae5  mov     rdi, rbx
0x140037ae8  mov     rcx, [rsp+rdi*8+268h+var_D0]; pv
0x140037af0  test    rcx, rcx
0x140037af3  jz      short loc_140037B03
0x140037af5  call    cs:__imp_CoTaskMemFree
0x140037afb  mov     [rsp+rdi*8+268h+var_D0], rbx
0x140037b03  inc     rdi
0x140037b06  cmp     rdi, 0Fh
0x140037b0a  jnz     short loc_140037AE8
0x140037b0c  lea     rcx, ?m_GlobalCS@CVssProviderManager@@0VCVssCriticalSection@@A; lpCriticalSection
0x140037b13  call    ?Lock@CVssCriticalSection@@QEAAXXZ; CVssCriticalSection::Lock(void)
0x140037b18  mov     [rsp+268h+var_40], 1
0x140037b20  lea     rcx, [rsp+268h+var_1A8]; this
0x140037b28  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140037b2d  nop
0x140037b2e  mov     edi, ebx
0x140037b30  cmp     edi, cs:dword_14014FB10
0x140037b36  jnb     loc_140037C0D
0x140037b3c  movsxd  rcx, edi
0x140037b3f  mov     rax, cs:qword_14014FB08
0x140037b46  lea     rdx, [rax+rcx*8]
0x140037b4a  lea     rcx, [rsp+268h+arg_0]
0x140037b52  call    ??0?$CComPtr@UIVssSnapshotProvider@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IVssSnapshotProvider>::CComPtr<IVssSnapshotProvider>(ATL::CComPtr<IVssSnapshotProvider> const &)
0x140037b57  nop
0x140037b58  mov     rcx, [rsp+268h+arg_0]
0x140037b60  test    rcx, rcx
0x140037b63  jz      loc_140037BF9
0x140037b69  mov     rax, [rcx]
0x140037b6c  mov     edx, 1
0x140037b71  mov     rax, [rax+118h]
0x140037b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037b7d  mov     [rsp+268h+var_210], eax
0x140037b81  test    eax, eax
0x140037b83  jns     short loc_140037BF9
0x140037b85  mov     [rsp+268h+var_F8], rsi
0x140037b8d  mov     [rsp+268h+var_F0], r14
0x140037b95  mov     [rsp+268h+var_E8], r15
0x140037b9d  mov     [rsp+268h+var_E0], 48Ch
0x140037ba8  mov     [rsp+268h+var_DC], 1
0x140037bb3  mov     [rsp+268h+var_D8], 0FFh
0x140037bbe  mov     [rsp+268h+var_58], 1000000h
0x140037bc9  xor     edx, edx; Val
0x140037bcb  lea     r8d, [rdx+78h]; Size
0x140037bcf  lea     rcx, [rsp+268h+var_D0]; void *
0x140037bd7  call    memset_0
0x140037bdc  lea     r8, aCannotUnloadLo; "Cannot unload load the internal provide"...
0x140037be3  lea     rdx, [rsp+268h+var_F8]
0x140037beb  lea     rcx, [rsp+268h+var_218]
0x140037bf0  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140037bf5  mov     [rsp+268h+var_210], ebx
0x140037bf9  lea     rcx, [rsp+268h+arg_0]
0x140037c01  call    ??1?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>(void)
0x140037c06  inc     edi
0x140037c08  jmp     loc_140037B30
0x140037c0d  call    cs:__imp_CoFreeUnusedLibraries
0x140037c13  lea     rcx, ?m_mapProviderItfOnLoadCache@CVssProviderManager@@0V?$CVssSimpleMap@U_GUID@@V?$CComPtr@UIVssSnapshotProvider@@@ATL@@@@A; CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>> CVssProviderManager::m_mapProviderItfOnLoadCache
0x140037c1a  call    ?RemoveAll@?$CVssSimpleMap@U_GUID@@V?$CComPtr@UIVssSnapshotProvider@@@ATL@@@@QEAAXXZ; CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::RemoveAll(void)
0x140037c1f  mov     rdi, cs:?m_pProvidersArray@CVssProviderManager@@0PEAVVSS_OBJECT_PROP_Array@@EA; VSS_OBJECT_PROP_Array * CVssProviderManager::m_pProvidersArray
0x140037c26  test    rdi, rdi
0x140037c29  jz      short loc_140037C48
0x140037c2b  lea     rcx, [rdi+8]
0x140037c2f  call    ??1?$CSimpleArray@VVSS_OBJECT_PROP_Ptr@@V?$CSimpleArrayEqualHelper@VVSS_OBJECT_PROP_Ptr@@@ATL@@@ATL@@QEAA@XZ; ATL::CSimpleArray<VSS_OBJECT_PROP_Ptr,ATL::CSimpleArrayEqualHelper<VSS_OBJECT_PROP_Ptr>>::~CSimpleArray<VSS_OBJECT_PROP_Ptr,ATL::CSimpleArrayEqualHelper<VSS_OBJECT_PROP_Ptr>>(void)
0x140037c34  mov     edx, 20h ; ' '
0x140037c39  mov     rcx, rdi; Block
0x140037c3c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140037c41  mov     cs:?m_pProvidersArray@CVssProviderManager@@0PEAVVSS_OBJECT_PROP_Array@@EA, rbx; VSS_OBJECT_PROP_Array * CVssProviderManager::m_pProvidersArray
0x140037c48  lea     rcx, [rsp+268h+var_48]; this
0x140037c50  call    ??1CVssAutomaticLock2@@QEAA@XZ; CVssAutomaticLock2::~CVssAutomaticLock2(void)
0x140037c55  nop
0x140037c56  jmp     short loc_140037C75
0x140037c58  jmp     short loc_140037C5E
0x140037c5a  jmp     short loc_140037C5E
0x140037c5c  jmp     short $+2
0x140037c5e  xor     ebx, ebx
0x140037c60  lea     r15, aCorprvmc; "CORPRVMC"
0x140037c67  lea     r14, aCvssproviderma_16; "CVssProviderManager::UnloadInternalProv"...
0x140037c6e  lea     rsi, aBaseStorVssMod_13; "base\\stor\\vss\\modules\\coord\\src\\p"...
0x140037c75  cmp     [rsp+268h+var_210], ebx
0x140037c79  jge     short loc_140037CF1
0x140037c7b  mov     [rsp+268h+var_F8], rsi
0x140037c83  mov     [rsp+268h+var_F0], r14
0x140037c8b  mov     [rsp+268h+var_E8], r15
0x140037c93  mov     [rsp+268h+var_E0], 4A5h
0x140037c9e  mov     [rsp+268h+var_DC], 1
0x140037ca9  mov     [rsp+268h+var_D8], 0FFh
0x140037cb4  mov     [rsp+268h+var_58], 1000000h
0x140037cbf  xor     edx, edx; Val
0x140037cc1  lea     r8d, [rdx+78h]; Size
0x140037cc5  lea     rcx, [rsp+268h+var_D0]; void *
0x140037ccd  call    memset_0
0x140037cd2  mov     r9d, [rsp+268h+var_210]
0x140037cd7  lea     r8, aExceptionCatch; "Exception catched 0x%08lx"
0x140037cde  lea     rdx, [rsp+268h+var_F8]
0x140037ce6  lea     rcx, [rsp+268h+var_218]
0x140037ceb  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140037cf0  nop
0x140037cf1  lea     rcx, [rsp+268h+var_218]; this
0x140037cf6  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140037cfb  lea     r11, [rsp+268h+var_28]
0x140037d03  mov     rbx, [r11+40h]
0x140037d07  mov     rsi, [r11+48h]
0x140037d0b  mov     rsp, r11
0x140037d0e  pop     r15
0x140037d10  pop     r14
0x140037d12  pop     r13
0x140037d14  pop     r12
0x140037d16  pop     rdi
0x140037d17  retn
```
