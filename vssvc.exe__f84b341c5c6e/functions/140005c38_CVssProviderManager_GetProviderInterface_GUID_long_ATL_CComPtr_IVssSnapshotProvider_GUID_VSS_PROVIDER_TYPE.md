# CVssProviderManager::GetProviderInterface(_GUID,long,ATL::CComPtr<IVssSnapshotProvider> &,_GUID,_VSS_PROVIDER_TYPE)

- ea: `0x140005c38`
- end: `0x140006018`
- name: `?GetProviderInterface@CVssProviderManager@@SAHU_GUID@@JAEAV?$CComPtr@UIVssSnapshotProvider@@@ATL@@0W4_VSS_PROVIDER_TYPE@@@Z`
- size: `992`
- prototype: ``
- caller_count: `10`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001cafc`
- `0x14002eb20`
- `0x140060460`
- `0x14006a3e0`
- `0x14006f180`
- `0x140082290`
- `0x1400844c0`
- `0x140085360`
- `0x14008aa50`
- `0x14009c970`

## callees

- `0x140005c38`
- `0x140006020`
- `0x140006c20`
- `0x140011440`
- `0x1400137c0`
- `0x140013cb0`
- `0x140015950`
- `0x14001818c`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140005ce2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140005e1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140005ce2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140005e1f`
- `VssTrace!__imp_VssTraceMessage` at `0x140005fc7`
- `VssTrace!__imp_VssTraceMessage` at `0x14000600c`
- `VssTrace!__imp_VssTraceMessage` at `0x140005fc7`
- `VssTrace!__imp_VssTraceMessage` at `0x14000600c`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140005f48`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140005f6a`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140005f48`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140005f6a`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140005d1a`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140005e5b`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140005d1a`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140005e5b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVssProviderManager::GetProviderInterface(
        __int128 *a1,
        unsigned int a2,
        __int64 a3,
        __int128 *a4,
        int a5)
{
  __int64 v9; // rcx
  int v10; // ebx
  int v11; // edi
  __int64 v12; // rcx
  unsigned int ProviderInterfaceInternal; // ebx
  int v15; // eax
  int v16; // eax
  const unsigned __int16 *v17; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v18; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v19; // [rsp+60h] [rbp-A0h]
  __int64 v20; // [rsp+68h] [rbp-98h]
  unsigned int v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v23; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v24; // [rsp+80h] [rbp-80h]
  DWORD v25; // [rsp+84h] [rbp-7Ch]
  int v26; // [rsp+88h] [rbp-78h]
  __int128 v27; // [rsp+90h] [rbp-70h]
  __int128 v28; // [rsp+A0h] [rbp-60h]
  __int64 v29; // [rsp+B0h] [rbp-50h]
  int v30; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v31; // [rsp+100h] [rbp+0h] BYREF
  int v32; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v33; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v34; // [rsp+118h] [rbp+18h]
  __int64 v35; // [rsp+120h] [rbp+20h]
  const wchar_t *v36; // [rsp+128h] [rbp+28h]
  unsigned int v37; // [rsp+130h] [rbp+30h]
  DWORD TickCount; // [rsp+134h] [rbp+34h]
  int v39; // [rsp+138h] [rbp+38h]
  __int128 v40; // [rsp+140h] [rbp+40h]
  __int128 v41; // [rsp+150h] [rbp+50h]
  __int64 v42; // [rsp+160h] [rbp+60h]
  LPCRITICAL_SECTION v43; // [rsp+170h] [rbp+70h] BYREF
  char v44; // [rsp+178h] [rbp+78h]
  __int128 v45; // [rsp+180h] [rbp+80h] BYREF
  __int128 v46; // [rsp+190h] [rbp+90h] BYREF
  const unsigned __int16 *v47; // [rsp+1A0h] [rbp+A0h] BYREF
  const wchar_t *v48; // [rsp+1A8h] [rbp+A8h]
  const unsigned __int16 *v49; // [rsp+1B0h] [rbp+B0h]
  int v50; // [rsp+1B8h] [rbp+B8h]
  int v51; // [rsp+1BCh] [rbp+BCh]
  int v52; // [rsp+1C0h] [rbp+C0h]
  _BYTE v53[120]; // [rsp+1C8h] [rbp+C8h] BYREF
  int v54; // [rsp+240h] [rbp+140h]
  __int64 v55; // [rsp+2A0h] [rbp+1A0h] BYREF

  v17 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
  v18 = L"CVssProviderManager::GetProviderInterface";
  v19 = L"CORPRVMC";
  v20 = 0x1000002BDLL;
  v21 = 255;
  v30 = 0x1000000;
  memset_0(&v23, 0, 0x78u);
  v32 = 0;
  v36 = L"CVssProviderManager::GetProviderInterface";
  v33 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
  v34 = L"CORPRVMC";
  v35 = 0x1000002BDLL;
  TickCount = GetTickCount();
  v39 = 255;
  v31 = 0xFFFFFFFF00000000uLL;
  v42 = 0;
  v40 = 0;
  v41 = 0;
  v55 = 0;
  if ( (int)VssGetTracingContextPerThread(&v55) >= 0 )
  {
    v15 = VssSetTracingContextPerThread(&v31);
    v9 = v42;
    if ( v15 >= 0 )
      v9 = v55;
    v42 = v9;
  }
  else
  {
    v9 = v42;
  }
  if ( v9 )
    v37 = *(_DWORD *)(v9 + 48) + 1;
  else
    v37 = 0;
  v10 = 160;
  v11 = 160;
  if ( v39 != 255 )
    v11 = v39;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v31) )
    VssTraceMessage(v33, v34, (unsigned int)v35, v37, HIDWORD(v35), v36, L"ENTER", v11, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v17);
  v43 = &CVssProviderManager::m_GlobalCS;
  v47 = L"base\\stor\\vss\\inc\\vs_types.hxx";
  v48 = L"CVssAutomaticLock2::CVssAutomaticLock2";
  v49 = L"INCTYPEH";
  v50 = 256;
  v51 = 11;
  v52 = 255;
  v54 = 0x1000000;
  memset_0(v53, 0, sizeof(v53));
  LODWORD(v18) = 0;
  v23 = v48;
  v19 = v47;
  v20 = (__int64)v49;
  v21 = v50;
  v22 = v51;
  v25 = GetTickCount();
  v26 = v52;
  v17 = (const unsigned __int16 *)0xFFFFFFFF00000000LL;
  v29 = 0;
  v27 = 0;
  v28 = 0;
  v55 = 0;
  if ( (int)VssGetTracingContextPerThread(&v55) >= 0 )
  {
    v16 = VssSetTracingContextPerThread(&v17);
    v12 = v29;
    if ( v16 >= 0 )
      v12 = v55;
    v29 = v12;
  }
  else
  {
    v12 = v29;
  }
  if ( v12 )
    v24 = *(_DWORD *)(v12 + 48) + 1;
  else
    v24 = 0;
  if ( v26 != 255 )
    v10 = v26;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v17) )
    VssTraceMessage(v19, v20, v21, v24, v22, v23, L"ENTER", v10, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v47);
  CVssCriticalSection::Lock(&CVssProviderManager::m_GlobalCS);
  v44 = 1;
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v17);
  v55 = 0;
  CVssProviderManager::GetProviderItfArrayInternal(a2, &v55);
  v45 = *a4;
  v46 = *a1;
  ProviderInterfaceInternal = CVssProviderManager::GetProviderInterfaceInternal(v55, &v46, a2, &v45, a5, a3);
  CVssAutomaticLock2::~CVssAutomaticLock2(&v43);
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v31);
  return ProviderInterfaceInternal;
}

```

## disassembly

```asm
0x140005c38  push    rbp
0x140005c3a  push    rbx
0x140005c3b  push    rsi
0x140005c3c  push    rdi
0x140005c3d  push    r12
0x140005c3f  push    r13
0x140005c41  push    r14
0x140005c43  push    r15
0x140005c45  lea     rbp, [rsp-158h]
0x140005c4d  sub     rsp, 258h
0x140005c54  mov     r14, r9
0x140005c57  mov     r15, r8
0x140005c5a  mov     esi, edx
0x140005c5c  mov     r12, rcx
0x140005c5f  lea     rax, aBaseStorVssMod_13; "base\\stor\\vss\\modules\\coord\\src\\p"...
0x140005c66  mov     [rsp+290h+var_240], rax
0x140005c6b  lea     rax, aCvssproviderma_3; "CVssProviderManager::GetProviderInterfa"...
0x140005c72  mov     [rsp+290h+var_238], rax
0x140005c77  lea     rax, aCorprvmc; "CORPRVMC"
0x140005c7e  mov     [rsp+290h+var_230], rax
0x140005c83  mov     dword ptr [rsp+290h+var_228], 2BDh
0x140005c8b  mov     dword ptr [rsp+290h+var_228+4], 1
0x140005c93  mov     [rsp+290h+var_220], 0FFh
0x140005c9b  xor     r13d, r13d
0x140005c9e  mov     [rbp+190h+var_1A0], 1000000h
0x140005ca5  xor     edx, edx; Val
0x140005ca7  lea     r8d, [r13+78h]; Size
0x140005cab  lea     rcx, [rsp+290h+var_218]; void *
0x140005cb0  call    memset_0
0x140005cb5  mov     [rbp+190h+var_188], r13d
0x140005cb9  mov     rax, [rsp+290h+var_238]
0x140005cbe  mov     [rbp+190h+var_168], rax
0x140005cc2  mov     rax, [rsp+290h+var_240]
0x140005cc7  mov     [rbp+190h+var_180], rax
0x140005ccb  mov     rax, [rsp+290h+var_230]
0x140005cd0  mov     [rbp+190h+var_178], rax
0x140005cd4  mov     eax, dword ptr [rsp+290h+var_228]
0x140005cd8  mov     dword ptr [rbp+190h+var_170], eax
0x140005cdb  mov     eax, dword ptr [rsp+290h+var_228+4]
0x140005cdf  mov     dword ptr [rbp+190h+var_170+4], eax
0x140005ce2  call    cs:__imp_GetTickCount
0x140005ce8  mov     [rbp+190h+var_15C], eax
0x140005ceb  mov     [rbp+190h+var_18C], 0FFFFFFFFh
0x140005cf2  mov     eax, [rsp+290h+var_220]
0x140005cf6  mov     [rbp+190h+var_158], eax
0x140005cf9  mov     [rbp+190h+var_190], r13d
0x140005cfd  mov     [rbp+190h+var_130], r13
0x140005d01  xorps   xmm0, xmm0
0x140005d04  movups  [rbp+190h+var_150], xmm0
0x140005d08  movups  [rbp+190h+var_140], xmm0
0x140005d0c  mov     [rbp+190h+arg_0], r13
0x140005d13  lea     rcx, [rbp+190h+arg_0]
0x140005d1a  call    cs:__imp_VssGetTracingContextPerThread
0x140005d20  test    eax, eax
0x140005d22  jns     loc_140005F44
0x140005d28  mov     rcx, [rbp+190h+var_130]
0x140005d2c  test    rcx, rcx
0x140005d2f  jz      loc_140005F87
0x140005d35  mov     eax, [rcx+30h]
0x140005d38  inc     eax
0x140005d3a  mov     [rbp+190h+var_160], eax
0x140005d3d  mov     ebx, 0A0h
0x140005d42  mov     edi, ebx
0x140005d44  cmp     [rbp+190h+var_158], 0FFh
0x140005d4b  cmovnz  edi, [rbp+190h+var_158]
0x140005d4f  lea     rcx, [rbp+190h+var_190]; this
0x140005d53  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x140005d58  lea     rcx, aEnter; "ENTER"
0x140005d5f  test    eax, eax
0x140005d61  jnz     loc_140005F99
0x140005d67  lea     rcx, [rsp+290h+var_240]; this
0x140005d6c  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140005d71  nop
0x140005d72  lea     rax, ?m_GlobalCS@CVssProviderManager@@0VCVssCriticalSection@@A; CVssCriticalSection CVssProviderManager::m_GlobalCS
0x140005d79  mov     [rbp+190h+var_120], rax
0x140005d7d  lea     rax, aBaseStorVssInc_3; "base\\stor\\vss\\inc\\vs_types.hxx"
0x140005d84  mov     [rbp+190h+var_F0], rax
0x140005d8b  lea     rax, aCvssautomaticl_0; "CVssAutomaticLock2::CVssAutomaticLock2"
0x140005d92  mov     [rbp+190h+var_E8], rax
0x140005d99  lea     rax, aInctypeh; "INCTYPEH"
0x140005da0  mov     [rbp+190h+var_E0], rax
0x140005da7  mov     [rbp+190h+var_D8], 100h
0x140005db1  mov     [rbp+190h+var_D4], 0Bh
0x140005dbb  mov     edi, 0FFh
0x140005dc0  mov     [rbp+190h+var_D0], edi
0x140005dc6  mov     [rbp+190h+var_50], 1000000h
0x140005dd0  xor     edx, edx; Val
0x140005dd2  lea     r8d, [rdx+78h]; Size
0x140005dd6  lea     rcx, [rbp+190h+var_C8]; void *
0x140005ddd  call    memset_0
0x140005de2  mov     dword ptr [rsp+290h+var_238], r13d
0x140005de7  mov     rax, [rbp+190h+var_E8]
0x140005dee  mov     [rsp+290h+var_218], rax
0x140005df3  mov     rax, [rbp+190h+var_F0]
0x140005dfa  mov     [rsp+290h+var_230], rax
0x140005dff  mov     rax, [rbp+190h+var_E0]
0x140005e06  mov     [rsp+290h+var_228], rax
0x140005e0b  mov     eax, [rbp+190h+var_D8]
0x140005e11  mov     [rsp+290h+var_220], eax
0x140005e15  mov     eax, [rbp+190h+var_D4]
0x140005e1b  mov     [rsp+290h+var_21C], eax
0x140005e1f  call    cs:__imp_GetTickCount
0x140005e25  mov     [rbp+190h+var_20C], eax
0x140005e28  mov     dword ptr [rsp+290h+var_240+4], 0FFFFFFFFh
0x140005e30  mov     eax, [rbp+190h+var_D0]
0x140005e36  mov     [rbp+190h+var_208], eax
0x140005e39  mov     dword ptr [rsp+290h+var_240], r13d
0x140005e3e  mov     [rbp+190h+var_1E0], r13
0x140005e42  xorps   xmm0, xmm0
0x140005e45  movups  [rbp+190h+var_200], xmm0
0x140005e49  movups  [rbp+190h+var_1F0], xmm0
0x140005e4d  mov     [rbp+190h+arg_0], r13
0x140005e54  lea     rcx, [rbp+190h+arg_0]
0x140005e5b  call    cs:__imp_VssGetTracingContextPerThread
0x140005e61  test    eax, eax
0x140005e63  jns     loc_140005F65
0x140005e69  mov     rcx, [rbp+190h+var_1E0]
0x140005e6d  test    rcx, rcx
0x140005e70  jz      loc_140005F90
0x140005e76  mov     eax, [rcx+30h]
0x140005e79  inc     eax
0x140005e7b  mov     [rbp+190h+var_210], eax
0x140005e7e  cmp     [rbp+190h+var_208], edi
0x140005e81  cmovnz  ebx, [rbp+190h+var_208]
0x140005e85  lea     rcx, [rsp+290h+var_240]; this
0x140005e8a  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x140005e8f  test    eax, eax
0x140005e91  jnz     loc_140005FD2
0x140005e97  lea     rcx, [rbp+190h+var_F0]; this
0x140005e9e  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140005ea3  nop
0x140005ea4  lea     rcx, ?m_GlobalCS@CVssProviderManager@@0VCVssCriticalSection@@A; lpCriticalSection
0x140005eab  call    ?Lock@CVssCriticalSection@@QEAAXXZ; CVssCriticalSection::Lock(void)
0x140005eb0  mov     [rbp+190h+var_118], 1
0x140005eb4  lea     rcx, [rsp+290h+var_240]; this
0x140005eb9  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140005ebe  nop
0x140005ebf  mov     [rbp+190h+arg_0], r13
0x140005ec6  lea     rdx, [rbp+190h+arg_0]
0x140005ecd  mov     ecx, esi
0x140005ecf  call    ?GetProviderItfArrayInternal@CVssProviderManager@@SAXJPEAPEAV?$CVssSimpleMap@U_GUID@@V?$CComPtr@UIVssSnapshotProvider@@@ATL@@@@@Z; CVssProviderManager::GetProviderItfArrayInternal(long,CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>> * *)
0x140005ed4  movaps  xmm0, xmmword ptr [r14]
0x140005ed8  movdqa  [rbp+190h+var_110], xmm0
0x140005ee0  movaps  xmm1, xmmword ptr [r12]
0x140005ee5  movdqa  [rbp+190h+var_100], xmm1
0x140005eed  mov     [rsp+290h+var_268], r15
0x140005ef2  mov     eax, [rbp+190h+arg_20]
0x140005ef8  mov     [rsp+290h+var_270], eax
0x140005efc  lea     r9, [rbp+190h+var_110]
0x140005f03  mov     r8d, esi
0x140005f06  lea     rdx, [rbp+190h+var_100]
0x140005f0d  mov     rcx, [rbp+190h+arg_0]
0x140005f14  call    ?GetProviderInterfaceInternal@CVssProviderManager@@CAHAEAV?$CVssSimpleMap@U_GUID@@V?$CComPtr@UIVssSnapshotProvider@@@ATL@@@@U_GUID@@J1W4_VSS_PROVIDER_TYPE@@AEAV?$CComPtr@UIVssSnapshotProvider@@@ATL@@@Z; CVssProviderManager::GetProviderInterfaceInternal(CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>> &,_GUID,long,_GUID,_VSS_PROVIDER_TYPE,ATL::CComPtr<IVssSnapshotProvider> &)
0x140005f19  mov     ebx, eax
0x140005f1b  lea     rcx, [rbp+190h+var_120]; this
0x140005f1f  call    ??1CVssAutomaticLock2@@QEAA@XZ; CVssAutomaticLock2::~CVssAutomaticLock2(void)
0x140005f24  nop
0x140005f25  lea     rcx, [rbp+190h+var_190]; this
0x140005f29  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140005f2e  mov     eax, ebx
0x140005f30  add     rsp, 258h
0x140005f37  pop     r15
0x140005f39  pop     r14
0x140005f3b  pop     r13
0x140005f3d  pop     r12
0x140005f3f  pop     rdi
0x140005f40  pop     rsi
0x140005f41  pop     rbx
0x140005f42  pop     rbp
0x140005f43  retn
0x140005f44  lea     rcx, [rbp+190h+var_190]
0x140005f48  call    cs:__imp_VssSetTracingContextPerThread
0x140005f4e  mov     rcx, [rbp+190h+var_130]
0x140005f52  test    eax, eax
0x140005f54  cmovns  rcx, [rbp+190h+arg_0]
0x140005f5c  mov     [rbp+190h+var_130], rcx
0x140005f60  jmp     loc_140005D2C
0x140005f65  lea     rcx, [rsp+290h+var_240]
0x140005f6a  call    cs:__imp_VssSetTracingContextPerThread
0x140005f70  mov     rcx, [rbp+190h+var_1E0]
0x140005f74  test    eax, eax
0x140005f76  cmovns  rcx, [rbp+190h+arg_0]
0x140005f7e  mov     [rbp+190h+var_1E0], rcx
0x140005f82  jmp     loc_140005E6D
0x140005f87  mov     [rbp+190h+var_160], r13d
0x140005f8b  jmp     loc_140005D3D
0x140005f90  mov     [rbp+190h+var_210], r13d
0x140005f94  jmp     loc_140005E7E
0x140005f99  mov     [rsp+290h+var_250], r13
0x140005f9e  mov     [rsp+290h+var_258], edi
0x140005fa2  mov     [rsp+290h+var_260], rcx
0x140005fa7  mov     rax, [rbp+190h+var_168]
0x140005fab  mov     [rsp+290h+var_268], rax
0x140005fb0  mov     eax, dword ptr [rbp+190h+var_170+4]
0x140005fb3  mov     [rsp+290h+var_270], eax
0x140005fb7  mov     r9d, [rbp+190h+var_160]
0x140005fbb  mov     r8d, dword ptr [rbp+190h+var_170]
0x140005fbf  mov     rdx, [rbp+190h+var_178]
0x140005fc3  mov     rcx, [rbp+190h+var_180]
0x140005fc7  call    cs:__imp_VssTraceMessage
0x140005fcd  jmp     loc_140005D67
0x140005fd2  mov     [rsp+290h+var_250], r13
0x140005fd7  mov     [rsp+290h+var_258], ebx
0x140005fdb  lea     rax, aEnter; "ENTER"
0x140005fe2  mov     [rsp+290h+var_260], rax
0x140005fe7  mov     rax, [rsp+290h+var_218]
0x140005fec  mov     [rsp+290h+var_268], rax
0x140005ff1  mov     eax, [rsp+290h+var_21C]
0x140005ff5  mov     [rsp+290h+var_270], eax
0x140005ff9  mov     r9d, [rbp+190h+var_210]
0x140005ffd  mov     r8d, [rsp+290h+var_220]
0x140006002  mov     rdx, [rsp+290h+var_228]
0x140006007  mov     rcx, [rsp+290h+var_230]
0x14000600c  call    cs:__imp_VssTraceMessage
0x140006012  jmp     loc_140005E97
```
