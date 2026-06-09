# CVssProviderManager::GetProviderItfArrayInternal(long,CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>> * *)

- ea: `0x140006c20`
- end: `0x140007059`
- name: `?GetProviderItfArrayInternal@CVssProviderManager@@SAXJPEAPEAV?$CVssSimpleMap@U_GUID@@V?$CComPtr@UIVssSnapshotProvider@@@ATL@@@@@Z`
- size: `1081`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x140005c38`
- `0x140016db0`

## callees

- `0x140006c20`
- `0x1400138e0`
- `0x140013c60`
- `0x140015e38`
- `0x140043d3c`
- `0x14009197c`
- `0x1400921dc`
- `0x14009de4c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140006cc7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140006e04`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140006cc7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140006e04`
- `VssTrace!__imp_VssTraceMessage` at `0x140006f3f`
- `VssTrace!__imp_VssTraceMessage` at `0x140006f3f`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140006ebf`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140006ede`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140006ebf`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140006ede`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140006d06`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140006d06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006d9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006dd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006dde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006dec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006dfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006d9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006dd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006dde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006dec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006dfa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVssProviderManager::GetProviderItfArrayInternal(int a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  unsigned int v5; // r14d
  unsigned int v6; // ebx
  __int64 i; // rbx
  void *v8; // rcx
  unsigned int v9; // edi
  int j; // eax
  void *v11; // rbx
  DWORD v12; // esi
  _QWORD *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+28h] [rbp-D8h]
  __int64 v18; // [rsp+30h] [rbp-D0h]
  __int64 v19; // [rsp+38h] [rbp-C8h]
  __int64 v20; // [rsp+40h] [rbp-C0h]
  _DWORD v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v22; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v23; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v24; // [rsp+68h] [rbp-98h]
  unsigned int v25; // [rsp+70h] [rbp-90h]
  unsigned int v26; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v27; // [rsp+78h] [rbp-88h]
  unsigned int v28; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  unsigned int v30; // [rsp+88h] [rbp-78h]
  LPVOID v31[2]; // [rsp+90h] [rbp-70h]
  LPVOID v32[2]; // [rsp+A0h] [rbp-60h]
  _QWORD *v33; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v34; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v35; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v36; // [rsp+D0h] [rbp-30h]
  int v37; // [rsp+D8h] [rbp-28h]
  int v38; // [rsp+DCh] [rbp-24h]
  int v39; // [rsp+E0h] [rbp-20h]
  LPVOID pv[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v41; // [rsp+F8h] [rbp-8h]
  __int128 v42; // [rsp+108h] [rbp+8h]
  __int128 v43; // [rsp+118h] [rbp+18h]
  __int128 v44; // [rsp+128h] [rbp+28h]
  __int128 v45; // [rsp+138h] [rbp+38h]
  __int128 v46; // [rsp+148h] [rbp+48h]
  __int64 v47; // [rsp+158h] [rbp+58h]
  int v48; // [rsp+160h] [rbp+60h]
  _QWORD *v49; // [rsp+1C8h] [rbp+C8h] BYREF

  v34 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
  v35 = L"CVssProviderManager::GetProviderItfArrayInternal";
  v36 = L"CORPRVMC";
  v37 = 377;
  v38 = 1;
  v39 = 255;
  v48 = 0x1000000;
  *(_OWORD *)pv = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v22 = 0;
  v27 = L"CVssProviderManager::GetProviderItfArrayInternal";
  v23 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
  v24 = L"CORPRVMC";
  v25 = 377;
  v26 = 1;
  TickCount = GetTickCount();
  v21[1] = -1;
  v30 = 255;
  v21[0] = 0;
  v33 = 0;
  *(_OWORD *)v31 = 0;
  *(_OWORD *)v32 = 0;
  v49 = 0;
  if ( (int)VssGetTracingContextPerThread(&v49) < 0 || (int)VssSetTracingContextPerThread(v21) < 0 )
  {
    v4 = v33;
  }
  else
  {
    v4 = v49;
    v33 = v49;
  }
  if ( v4 )
    v28 = *((_DWORD *)v4 + 12) + 1;
  else
    v28 = 0;
  v5 = 160;
  v6 = 160;
  if ( v30 != 255 )
    v6 = v30;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v21, v26) )
    VssTraceMessage(v23, v24, v25, v28, v26, v27, L"ENTER", v6, 0);
  for ( i = 0; i != 15; ++i )
  {
    v8 = pv[i];
    if ( v8 )
    {
      CoTaskMemFree(v8);
      pv[i] = 0;
    }
  }
  *a2 = 0;
  v9 = a1 & 0xFD3FFFFF;
  if ( a1 == -1 )
    v9 = -1;
  for ( j = 0; j < dword_14014FAF0; ++j )
  {
    if ( *(_DWORD *)(CVssProviderManager::m_mapProviderMapGlobalCache + 4LL * j) == v9 )
    {
      if ( j != -1 )
      {
        v11 = *(void **)(qword_14014FAE8 + 8LL * j);
        if ( v11 )
          goto LABEL_21;
      }
      break;
    }
  }
  v14 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v14;
  v49 = v14;
  if ( !v14 )
  {
    v34 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
    v35 = L"CVssProviderManager::GetProviderItfArrayInternal";
    v36 = L"CORPRVMC";
    v37 = 393;
    v38 = 1;
    v39 = 255;
    v48 = 0x1000000;
    memset_0(pv, 0, 0x78u);
    CVssFunctionTracer::Throw(v21, &v34, 2147942414LL, L"Memory allocation error");
  }
  *v14 = 0;
  v14[1] = 0;
  *((_DWORD *)v14 + 4) = 0;
  if ( !(unsigned int)CVssSimpleMap<long,CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>> *>::Add(
                        v15,
                        v9,
                        (__int64)v14) )
  {
    CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::`scalar deleting destructor'(v11);
    v34 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
    v35 = L"CVssProviderManager::GetProviderItfArrayInternal";
    v36 = L"CORPRVMC";
    v37 = 398;
    v38 = 1;
    v39 = 255;
    v48 = 0x1000000;
    memset_0(pv, 0, 0x78u);
    CVssFunctionTracer::Throw(v21, &v34, 2147942414LL, L"Memory allocation error");
  }
LABEL_21:
  *a2 = v11;
  CoTaskMemFree(v31[0]);
  v31[0] = 0;
  CoTaskMemFree(v31[1]);
  v31[1] = 0;
  CoTaskMemFree(v32[0]);
  v32[0] = 0;
  CoTaskMemFree(v32[1]);
  v32[1] = 0;
  v12 = GetTickCount() - TickCount;
  if ( v30 != 255 )
    v5 = v30;
  LODWORD(v20) = v12;
  LODWORD(v19) = v12 % 0x3E8;
  LODWORD(v18) = v12 / 0x3E8 % 0x3C;
  LODWORD(v17) = v12 / 0xEA60 % 0x3C;
  LODWORD(v16) = v12 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v21,
    L"EXIT",
    v5,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v16,
    v17,
    v18,
    v19,
    v20,
    v22);
  return VssSetTracingContextPerThread(v33);
}

```

## disassembly

```asm
0x140006c20  push    rbp
0x140006c22  push    rbx
0x140006c23  push    rsi
0x140006c24  push    rdi
0x140006c25  push    r12
0x140006c27  push    r13
0x140006c29  push    r14
0x140006c2b  push    r15
0x140006c2d  lea     rbp, [rsp-78h]
0x140006c32  sub     rsp, 178h
0x140006c39  mov     r15, rdx
0x140006c3c  mov     esi, ecx
0x140006c3e  lea     r13, aBaseStorVssMod_13; "base\\stor\\vss\\modules\\coord\\src\\p"...
0x140006c45  mov     [rbp+0B0h+var_F0], r13
0x140006c49  lea     rcx, aCvssproviderma_0; "CVssProviderManager::GetProviderItfArra"...
0x140006c50  mov     [rbp+0B0h+var_E8], rcx
0x140006c54  lea     rdx, aCorprvmc; "CORPRVMC"
0x140006c5b  mov     [rbp+0B0h+var_E0], rdx
0x140006c5f  mov     [rbp+0B0h+var_D8], 179h
0x140006c66  mov     [rbp+0B0h+var_D4], 1
0x140006c6d  mov     [rbp+0B0h+var_D0], 0FFh
0x140006c74  xor     r12d, r12d
0x140006c77  mov     [rbp+0B0h+var_50], 1000000h
0x140006c7e  xorps   xmm0, xmm0
0x140006c81  xor     eax, eax
0x140006c83  movups  xmmword ptr [rbp+0B0h+pv], xmm0
0x140006c87  movups  [rbp+0B0h+var_B8], xmm0
0x140006c8b  movups  [rbp+0B0h+var_A8], xmm0
0x140006c8f  movups  [rbp+0B0h+var_98], xmm0
0x140006c93  movups  [rbp+0B0h+var_88], xmm0
0x140006c97  movups  [rbp+0B0h+var_78], xmm0
0x140006c9b  movups  [rbp+0B0h+var_68], xmm0
0x140006c9f  mov     [rbp+0B0h+var_58], rax
0x140006ca3  mov     [rsp+1B0h+var_158], r12d
0x140006ca8  mov     [rsp+1B0h+var_138], rcx
0x140006cad  mov     [rsp+1B0h+var_150], r13
0x140006cb2  mov     [rsp+1B0h+var_148], rdx
0x140006cb7  mov     [rsp+1B0h+var_140], 179h
0x140006cbf  mov     [rsp+1B0h+var_13C], 1
0x140006cc7  call    cs:__imp_GetTickCount
0x140006ccd  mov     [rbp+0B0h+var_12C], eax
0x140006cd0  mov     [rsp+1B0h+var_15C], 0FFFFFFFFh
0x140006cd8  mov     [rbp+0B0h+var_128], 0FFh
0x140006cdf  mov     [rsp+1B0h+var_160], r12d
0x140006ce4  mov     [rbp+0B0h+var_100], r12
0x140006ce8  xorps   xmm0, xmm0
0x140006ceb  movdqa  xmmword ptr [rbp+0B0h+var_120], xmm0
0x140006cf0  xorps   xmm1, xmm1
0x140006cf3  movdqa  xmmword ptr [rbp+0B0h+var_110], xmm1
0x140006cf8  mov     [rbp+0B0h+arg_8], r12
0x140006cff  lea     rcx, [rbp+0B0h+arg_8]
0x140006d06  call    cs:__imp_VssGetTracingContextPerThread
0x140006d0c  test    eax, eax
0x140006d0e  jns     loc_140006ED9
0x140006d14  mov     rax, [rbp+0B0h+var_100]
0x140006d18  test    rax, rax
0x140006d1b  jz      loc_140006EFC
0x140006d21  mov     eax, [rax+30h]
0x140006d24  inc     eax
0x140006d26  mov     [rbp+0B0h+var_130], eax
0x140006d29  mov     r14d, 0A0h
0x140006d2f  mov     ebx, r14d
0x140006d32  cmp     [rbp+0B0h+var_128], 0FFh
0x140006d39  cmovnz  ebx, [rbp+0B0h+var_128]
0x140006d3d  mov     edx, [rsp+1B0h+var_13C]; unsigned int
0x140006d41  lea     rcx, [rsp+1B0h+var_160]; this
0x140006d46  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140006d4b  test    eax, eax
0x140006d4d  jnz     loc_140006F05
0x140006d53  mov     rbx, r12
0x140006d56  mov     rcx, [rbp+rbx*8+0B0h+pv]; pv
0x140006d5b  test    rcx, rcx
0x140006d5e  jnz     short loc_140006D9F
0x140006d60  inc     rbx
0x140006d63  cmp     rbx, 0Fh
0x140006d67  jnz     short loc_140006D56
0x140006d69  mov     [r15], r12
0x140006d6c  mov     edi, esi
0x140006d6e  and     edi, 0FD3FFFFFh
0x140006d74  cmp     esi, 0FFFFFFFFh
0x140006d77  cmovz   edi, esi
0x140006d7a  mov     eax, r12d
0x140006d7d  mov     edx, cs:dword_14014FAF0
0x140006d83  mov     r8, cs:?m_mapProviderMapGlobalCache@CVssProviderManager@@0V?$CVssSimpleMap@JPEAV?$CVssSimpleMap@U_GUID@@V?$CComPtr@UIVssSnapshotProvider@@@ATL@@@@@@A; CVssSimpleMap<long,CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>> *> CVssProviderManager::m_mapProviderMapGlobalCache
0x140006d8a  cmp     eax, edx
0x140006d8c  jge     loc_140006F4A
0x140006d92  movsxd  rcx, eax
0x140006d95  cmp     [r8+rcx*4], edi
0x140006d99  jz      short loc_140006DAC
0x140006d9b  inc     eax
0x140006d9d  jmp     short loc_140006D8A
0x140006d9f  call    cs:__imp_CoTaskMemFree
0x140006da5  mov     [rbp+rbx*8+0B0h+pv], r12
0x140006daa  jmp     short loc_140006D60
0x140006dac  cmp     eax, 0FFFFFFFFh
0x140006daf  jz      loc_140006F4A
0x140006db5  mov     rax, cs:qword_14014FAE8
0x140006dbc  mov     rbx, [rax+rcx*8]
0x140006dc0  test    rbx, rbx
0x140006dc3  jz      loc_140006F4A
0x140006dc9  mov     [r15], rbx
0x140006dcc  mov     rcx, [rbp+0B0h+var_120]; pv
0x140006dd0  call    cs:__imp_CoTaskMemFree
0x140006dd6  mov     [rbp+0B0h+var_120], r12
0x140006dda  mov     rcx, [rbp+0B0h+var_120+8]; pv
0x140006dde  call    cs:__imp_CoTaskMemFree
0x140006de4  mov     [rbp+0B0h+var_120+8], r12
0x140006de8  mov     rcx, [rbp+0B0h+var_110]; pv
0x140006dec  call    cs:__imp_CoTaskMemFree
0x140006df2  mov     [rbp+0B0h+var_110], r12
0x140006df6  mov     rcx, [rbp+0B0h+var_110+8]; pv
0x140006dfa  call    cs:__imp_CoTaskMemFree
0x140006e00  mov     [rbp+0B0h+var_110+8], r12
0x140006e04  call    cs:__imp_GetTickCount
0x140006e0a  mov     esi, eax
0x140006e0c  sub     esi, [rbp+0B0h+var_12C]
0x140006e0f  mov     eax, 10624DD3h
0x140006e14  mul     esi
0x140006e16  mov     edi, edx
0x140006e18  shr     edi, 6
0x140006e1b  mov     eax, 88888889h
0x140006e20  mul     edi
0x140006e22  shr     edx, 5
0x140006e25  imul    ecx, edx, 3Ch ; '<'
0x140006e28  mov     ebx, edi
0x140006e2a  sub     ebx, ecx
0x140006e2c  mov     eax, 45E7B273h
0x140006e31  mul     esi
0x140006e33  mov     r11d, edx
0x140006e36  shr     r11d, 0Eh
0x140006e3a  mov     eax, 88888889h
0x140006e3f  mul     r11d
0x140006e42  shr     edx, 5
0x140006e45  imul    ecx, edx, 3Ch ; '<'
0x140006e48  sub     r11d, ecx
0x140006e4b  mov     eax, 95217CB1h
0x140006e50  mul     esi
0x140006e52  mov     r10d, edx
0x140006e55  shr     r10d, 15h
0x140006e59  mov     eax, 88888889h
0x140006e5e  mul     r10d
0x140006e61  shr     edx, 5
0x140006e64  imul    eax, edx, 3Ch ; '<'
0x140006e67  sub     r10d, eax
0x140006e6a  mov     r9d, [rsp+1B0h+var_158]
0x140006e6f  cmp     [rbp+0B0h+var_128], 0FFh
0x140006e76  cmovnz  r14d, [rbp+0B0h+var_128]
0x140006e7b  imul    eax, edi, 3E8h
0x140006e81  mov     ecx, esi
0x140006e83  sub     ecx, eax
0x140006e85  mov     [rsp+1B0h+var_168], r9d
0x140006e8a  mov     dword ptr [rsp+1B0h+var_170], esi
0x140006e8e  mov     dword ptr [rsp+1B0h+var_178], ecx
0x140006e92  mov     dword ptr [rsp+1B0h+var_180], ebx
0x140006e96  mov     dword ptr [rsp+1B0h+var_188], r11d
0x140006e9b  mov     dword ptr [rsp+1B0h+var_190], r10d
0x140006ea0  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140006ea7  mov     r8d, r14d; unsigned int
0x140006eaa  lea     rdx, aExit; "EXIT"
0x140006eb1  lea     rcx, [rsp+1B0h+var_160]; this
0x140006eb6  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140006ebb  mov     rcx, [rbp+0B0h+var_100]
0x140006ebf  call    cs:__imp_VssSetTracingContextPerThread
0x140006ec5  add     rsp, 178h
0x140006ecc  pop     r15
0x140006ece  pop     r14
0x140006ed0  pop     r13
0x140006ed2  pop     r12
0x140006ed4  pop     rdi
0x140006ed5  pop     rsi
0x140006ed6  pop     rbx
0x140006ed7  pop     rbp
0x140006ed8  retn
0x140006ed9  lea     rcx, [rsp+1B0h+var_160]
0x140006ede  call    cs:__imp_VssSetTracingContextPerThread
0x140006ee4  test    eax, eax
0x140006ee6  js      loc_140006D14
0x140006eec  mov     rax, [rbp+0B0h+arg_8]
0x140006ef3  mov     [rbp+0B0h+var_100], rax
0x140006ef7  jmp     loc_140006D18
0x140006efc  mov     [rbp+0B0h+var_130], r12d
0x140006f00  jmp     loc_140006D29
0x140006f05  mov     [rsp+1B0h+var_170], r12
0x140006f0a  mov     dword ptr [rsp+1B0h+var_178], ebx
0x140006f0e  lea     rax, aEnter; "ENTER"
0x140006f15  mov     [rsp+1B0h+var_180], rax
0x140006f1a  mov     rax, [rsp+1B0h+var_138]
0x140006f1f  mov     [rsp+1B0h+var_188], rax
0x140006f24  mov     eax, [rsp+1B0h+var_13C]
0x140006f28  mov     dword ptr [rsp+1B0h+var_190], eax
0x140006f2c  mov     r9d, [rbp+0B0h+var_130]
0x140006f30  mov     r8d, [rsp+1B0h+var_140]
0x140006f35  mov     rdx, [rsp+1B0h+var_148]
0x140006f3a  mov     rcx, [rsp+1B0h+var_150]
0x140006f3f  call    cs:__imp_VssTraceMessage
0x140006f45  jmp     loc_140006D53
0x140006f4a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140006f51  mov     ecx, 18h; unsigned __int64
0x140006f56  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140006f5b  mov     rbx, rax
0x140006f5e  mov     [rbp+0B0h+arg_8], rax
0x140006f65  test    rax, rax
0x140006f68  jz      loc_140006FF6
0x140006f6e  mov     [rax], r12
0x140006f71  mov     [rax+8], r12
0x140006f75  mov     [rax+10h], r12d
0x140006f79  mov     r8, rax
0x140006f7c  mov     edx, edi
0x140006f7e  call    ?Add@?$CVssSimpleMap@JPEAV?$CVssSimpleMap@U_GUID@@V?$CComPtr@UIVssSnapshotProvider@@@ATL@@@@@@QEAAHJPEAV?$CVssSimpleMap@U_GUID@@V?$CComPtr@UIVssSnapshotProvider@@@ATL@@@@@Z; CVssSimpleMap<long,CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>> *>::Add(long,CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>> *)
0x140006f83  test    eax, eax
0x140006f85  jnz     loc_140006DC9
0x140006f8b  mov     rcx, rbx; Block
0x140006f8e  call    ??_G?$CVssSimpleMap@U_GUID@@V?$CComPtr@UIVssSnapshotProvider@@@ATL@@@@QEAAPEAXI@Z; CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::`scalar deleting destructor'(uint)
0x140006f93  mov     [rbp+0B0h+var_F0], r13
0x140006f97  lea     rax, aCvssproviderma_0; "CVssProviderManager::GetProviderItfArra"...
0x140006f9e  mov     [rbp+0B0h+var_E8], rax
0x140006fa2  lea     rax, aCorprvmc; "CORPRVMC"
0x140006fa9  mov     [rbp+0B0h+var_E0], rax
0x140006fad  mov     [rbp+0B0h+var_D8], 18Eh
0x140006fb4  mov     [rbp+0B0h+var_D4], 1
0x140006fbb  mov     [rbp+0B0h+var_D0], 0FFh
0x140006fc2  mov     [rbp+0B0h+var_50], 1000000h
0x140006fc9  xor     edx, edx; Val
0x140006fcb  mov     r8d, 78h ; 'x'; Size
0x140006fd1  lea     rcx, [rbp+0B0h+pv]; void *
0x140006fd5  call    memset_0
0x140006fda  lea     r9, aMemoryAllocati; "Memory allocation error"
0x140006fe1  mov     r8d, 8007000Eh
0x140006fe7  lea     rdx, [rbp+0B0h+var_F0]
0x140006feb  lea     rcx, [rsp+1B0h+var_160]
0x140006ff0  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140006ff6  mov     [rbp+0B0h+var_F0], r13
0x140006ffa  lea     rax, aCvssproviderma_0; "CVssProviderManager::GetProviderItfArra"...
0x140007001  mov     [rbp+0B0h+var_E8], rax
0x140007005  lea     rax, aCorprvmc; "CORPRVMC"
0x14000700c  mov     [rbp+0B0h+var_E0], rax
0x140007010  mov     [rbp+0B0h+var_D8], 189h
0x140007017  mov     [rbp+0B0h+var_D4], 1
0x14000701e  mov     [rbp+0B0h+var_D0], 0FFh
0x140007025  mov     [rbp+0B0h+var_50], 1000000h
0x14000702c  xor     edx, edx; Val
0x14000702e  mov     r8d, 78h ; 'x'; Size
0x140007034  lea     rcx, [rbp+0B0h+pv]; void *
0x140007038  call    memset_0
0x14000703d  lea     r9, aMemoryAllocati; "Memory allocation error"
0x140007044  mov     r8d, 8007000Eh
0x14000704a  lea     rdx, [rbp+0B0h+var_F0]
0x14000704e  lea     rcx, [rsp+1B0h+var_160]
0x140007053  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
```
