# CVssCriticalSection::Lock(void)

- ea: `0x140015950`
- end: `0x140015e30`
- name: `?Lock@CVssCriticalSection@@QEAAXXZ`
- size: `1248`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `8`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140002270`
- `0x140003b70`
- `0x140005050`
- `0x140005c38`
- `0x140016710`
- `0x140016db0`
- `0x1400376e0`
- `0x14003aa10`

## callees

- `0x1400138e0`
- `0x140013c60`
- `0x140015950`
- `0x140046aa0`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140015b07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140015b07`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140015a22`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140015b75`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140015a22`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140015b75`
- `VssTrace!__imp_VssTraceMessage` at `0x140015ce8`
- `VssTrace!__imp_VssTraceMessage` at `0x140015ce8`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140015c40`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140015c7b`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140015c40`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140015c7b`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140015a76`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140015a76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015b25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015b3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015b51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015b67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015c63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015b25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015b3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015b51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015b67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015c63`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssCriticalSection::Lock(LPCRITICAL_SECTION lpCriticalSection)
{
  __int64 v2; // rax
  unsigned int v3; // r14d
  unsigned int v4; // ebx
  __int64 i; // rbx
  void *v6; // rcx
  DWORD v7; // esi
  __int64 v8; // [rsp+20h] [rbp-188h]
  __int64 v9; // [rsp+28h] [rbp-180h]
  __int64 v10; // [rsp+30h] [rbp-178h]
  __int64 v11; // [rsp+38h] [rbp-170h]
  __int64 v12; // [rsp+40h] [rbp-168h]
  _DWORD v13[2]; // [rsp+50h] [rbp-158h] BYREF
  int v14; // [rsp+58h] [rbp-150h]
  const unsigned __int16 *v15; // [rsp+60h] [rbp-148h]
  const unsigned __int16 *v16; // [rsp+68h] [rbp-140h]
  unsigned int v17; // [rsp+70h] [rbp-138h]
  unsigned int v18; // [rsp+74h] [rbp-134h]
  const unsigned __int16 *v19; // [rsp+78h] [rbp-130h]
  unsigned int v20; // [rsp+80h] [rbp-128h]
  DWORD TickCount; // [rsp+84h] [rbp-124h]
  unsigned int v22; // [rsp+88h] [rbp-120h]
  LPVOID pv[2]; // [rsp+90h] [rbp-118h]
  LPVOID v24[2]; // [rsp+A0h] [rbp-108h]
  __int64 v25; // [rsp+B0h] [rbp-F8h]
  const unsigned __int16 *v26; // [rsp+C0h] [rbp-E8h] BYREF
  const unsigned __int16 *v27; // [rsp+C8h] [rbp-E0h]
  const unsigned __int16 *v28; // [rsp+D0h] [rbp-D8h]
  int v29; // [rsp+D8h] [rbp-D0h]
  int v30; // [rsp+DCh] [rbp-CCh]
  int v31; // [rsp+E0h] [rbp-C8h]
  LPVOID v32[2]; // [rsp+E8h] [rbp-C0h] BYREF
  __int128 v33; // [rsp+F8h] [rbp-B0h]
  __int128 v34; // [rsp+108h] [rbp-A0h]
  __int128 v35; // [rsp+118h] [rbp-90h]
  __int128 v36; // [rsp+128h] [rbp-80h]
  __int128 v37; // [rsp+138h] [rbp-70h]
  __int128 v38; // [rsp+148h] [rbp-60h]
  __int64 v39; // [rsp+158h] [rbp-50h]
  int v40; // [rsp+160h] [rbp-48h]
  __int64 v41; // [rsp+1B8h] [rbp+10h] BYREF

  v26 = L"base\\stor\\vss\\inc\\vs_types.hxx";
  v27 = L"CVssCriticalSection::Lock";
  v28 = L"INCTYPEH";
  v29 = 197;
  v30 = 11;
  v31 = 255;
  v40 = 0x1000000;
  *(_OWORD *)v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v14 = 0;
  v19 = L"CVssCriticalSection::Lock";
  v15 = L"base\\stor\\vss\\inc\\vs_types.hxx";
  v16 = L"INCTYPEH";
  v17 = 197;
  v18 = 11;
  TickCount = GetTickCount();
  v13[1] = -1;
  v22 = 255;
  v13[0] = 0;
  v25 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v24 = 0;
  v41 = 0;
  if ( (int)VssGetTracingContextPerThread(&v41) < 0 || (int)VssSetTracingContextPerThread(v13) < 0 )
  {
    v2 = v25;
  }
  else
  {
    v2 = v41;
    v25 = v41;
  }
  if ( v2 )
    v20 = *(_DWORD *)(v2 + 48) + 1;
  else
    v20 = 0;
  v3 = 160;
  v4 = 160;
  if ( v22 != 255 )
    v4 = v22;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v13, v18) )
    VssTraceMessage(v15, v16, v17, v20, v18, v19, L"ENTER", v4, 0);
  for ( i = 0; i != 15; ++i )
  {
    v6 = v32[i];
    if ( v6 )
    {
      CoTaskMemFree(v6);
      v32[i] = 0;
    }
  }
  if ( !LOBYTE(lpCriticalSection[1].DebugInfo) )
  {
    v26 = L"base\\stor\\vss\\inc\\vs_types.hxx";
    v27 = L"CVssCriticalSection::Lock";
    v28 = L"INCTYPEH";
    v29 = 201;
    v30 = 11;
    v31 = 255;
    v40 = 0x1000000;
    memset_0(v32, 0, 0x78u);
    CVssFunctionTracer::ThrowIf(v13, BYTE1(lpCriticalSection[1].DebugInfo), &v26, 2147942414LL, L"Non-initialized CS");
  }
  EnterCriticalSection(lpCriticalSection);
  if ( v14 < 0 )
  {
    v26 = L"base\\stor\\vss\\inc\\vs_types.hxx";
    v27 = L"CVssCriticalSection::Lock";
    v28 = L"INCTYPEH";
    v29 = 212;
    v30 = 11;
    v31 = 255;
    v40 = 0x1000000;
    memset_0(v32, 0, 0x78u);
    CVssFunctionTracer::ThrowIf(
      v13,
      BYTE1(lpCriticalSection[1].DebugInfo),
      &v26,
      2147942414LL,
      L"Error entering into CS");
  }
  _InterlockedIncrement((volatile signed __int32 *)&lpCriticalSection[1].DebugInfo + 1);
  CoTaskMemFree(pv[0]);
  pv[0] = 0;
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v24[0]);
  v24[0] = 0;
  CoTaskMemFree(v24[1]);
  v24[1] = 0;
  v7 = GetTickCount() - TickCount;
  if ( v22 != 255 )
    v3 = v22;
  LODWORD(v12) = v7;
  LODWORD(v11) = v7 % 0x3E8;
  LODWORD(v10) = v7 / 0x3E8 % 0x3C;
  LODWORD(v9) = v7 / 0xEA60 % 0x3C;
  LODWORD(v8) = v7 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v13,
    L"EXIT",
    v3,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v8,
    v9,
    v10,
    v11,
    v12,
    v14);
  VssSetTracingContextPerThread(v25);
}

```

## disassembly

```asm
0x140015950  mov     r11, rsp
0x140015953  mov     [r11+18h], rbx
0x140015957  mov     [r11+20h], rsi
0x14001595b  mov     [r11+8], rcx
0x14001595f  push    rdi
0x140015960  push    r12
0x140015962  push    r13
0x140015964  push    r14
0x140015966  push    r15
0x140015968  sub     rsp, 180h
0x14001596f  mov     rsi, rcx
0x140015972  lea     r15, aBaseStorVssInc_3; "base\\stor\\vss\\inc\\vs_types.hxx"
0x140015979  mov     [r11-0E8h], r15
0x140015980  lea     r12, aCvsscriticalse_1; "CVssCriticalSection::Lock"
0x140015987  mov     [r11-0E0h], r12
0x14001598e  lea     r13, aInctypeh; "INCTYPEH"
0x140015995  mov     [r11-0D8h], r13
0x14001599c  mov     [rsp+1A8h+var_D0], 0C5h
0x1400159a7  mov     [rsp+1A8h+var_CC], 0Bh
0x1400159b2  mov     [rsp+1A8h+var_C8], 0FFh
0x1400159bd  xor     edi, edi
0x1400159bf  mov     dword ptr [r11-48h], 1000000h
0x1400159c7  xorps   xmm0, xmm0
0x1400159ca  xor     eax, eax
0x1400159cc  movups  xmmword ptr [rsp+1A8h+var_C0], xmm0
0x1400159d4  movups  [rsp+1A8h+var_B0], xmm0
0x1400159dc  movups  [rsp+1A8h+var_A0], xmm0
0x1400159e4  movups  [rsp+1A8h+var_90], xmm0
0x1400159ec  movups  xmmword ptr [r11-80h], xmm0
0x1400159f1  movups  xmmword ptr [r11-70h], xmm0
0x1400159f6  movups  xmmword ptr [r11-60h], xmm0
0x1400159fb  mov     [r11-50h], rax
0x1400159ff  mov     [rsp+1A8h+var_150], edi
0x140015a03  mov     [rsp+1A8h+var_130], r12
0x140015a08  mov     [rsp+1A8h+var_148], r15
0x140015a0d  mov     [rsp+1A8h+var_140], r13
0x140015a12  mov     [rsp+1A8h+var_138], 0C5h
0x140015a1a  mov     [rsp+1A8h+var_134], 0Bh
0x140015a22  call    cs:__imp_GetTickCount
0x140015a28  mov     [rsp+1A8h+var_124], eax
0x140015a2f  mov     [rsp+1A8h+var_154], 0FFFFFFFFh
0x140015a37  mov     [rsp+1A8h+var_120], 0FFh
0x140015a42  mov     [rsp+1A8h+var_158], edi
0x140015a46  mov     [rsp+1A8h+var_F8], rdi
0x140015a4e  xorps   xmm0, xmm0
0x140015a51  movdqa  xmmword ptr [rsp+1A8h+pv], xmm0
0x140015a5a  xorps   xmm1, xmm1
0x140015a5d  movdqa  xmmword ptr [rsp+1A8h+var_108], xmm1
0x140015a66  mov     [rsp+1A8h+arg_8], rdi
0x140015a6e  lea     rcx, [rsp+1A8h+arg_8]
0x140015a76  call    cs:__imp_VssGetTracingContextPerThread
0x140015a7c  test    eax, eax
0x140015a7e  jns     loc_140015C76
0x140015a84  mov     rax, [rsp+1A8h+var_F8]
0x140015a8c  test    rax, rax
0x140015a8f  jz      loc_140015C9E
0x140015a95  mov     eax, [rax+30h]
0x140015a98  inc     eax
0x140015a9a  mov     [rsp+1A8h+var_128], eax
0x140015aa1  mov     r14d, 0A0h
0x140015aa7  mov     ebx, r14d
0x140015aaa  cmp     [rsp+1A8h+var_120], 0FFh
0x140015ab5  cmovnz  ebx, [rsp+1A8h+var_120]
0x140015abd  mov     edx, [rsp+1A8h+var_134]; unsigned int
0x140015ac1  lea     rcx, [rsp+1A8h+var_158]; this
0x140015ac6  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140015acb  test    eax, eax
0x140015acd  jnz     loc_140015CAA
0x140015ad3  mov     rbx, rdi
0x140015ad6  nop     word ptr [rax+rax+00000000h]
0x140015ae0  mov     rcx, [rsp+rbx*8+1A8h+var_C0]; pv
0x140015ae8  test    rcx, rcx
0x140015aeb  jnz     loc_140015C63
0x140015af1  inc     rbx
0x140015af4  cmp     rbx, 0Fh
0x140015af8  jnz     short loc_140015AE0
0x140015afa  cmp     byte ptr [rsi+28h], 0
0x140015afe  jz      loc_140015CF3
0x140015b04  mov     rcx, rsi; lpCriticalSection
0x140015b07  call    cs:__imp_EnterCriticalSection
0x140015b0d  nop
0x140015b0e  cmp     [rsp+1A8h+var_150], 0
0x140015b13  jl      loc_140015DA9
0x140015b19  lock inc dword ptr [rsi+2Ch]
0x140015b1d  mov     rcx, [rsp+1A8h+pv]; pv
0x140015b25  call    cs:__imp_CoTaskMemFree
0x140015b2b  mov     [rsp+1A8h+pv], rdi
0x140015b33  mov     rcx, [rsp+1A8h+pv+8]; pv
0x140015b3b  call    cs:__imp_CoTaskMemFree
0x140015b41  mov     [rsp+1A8h+pv+8], rdi
0x140015b49  mov     rcx, [rsp+1A8h+var_108]; pv
0x140015b51  call    cs:__imp_CoTaskMemFree
0x140015b57  mov     [rsp+1A8h+var_108], rdi
0x140015b5f  mov     rcx, [rsp+1A8h+var_108+8]; pv
0x140015b67  call    cs:__imp_CoTaskMemFree
0x140015b6d  mov     [rsp+1A8h+var_108+8], rdi
0x140015b75  call    cs:__imp_GetTickCount
0x140015b7b  mov     esi, eax
0x140015b7d  sub     esi, [rsp+1A8h+var_124]
0x140015b84  mov     eax, 10624DD3h
0x140015b89  mul     esi
0x140015b8b  mov     edi, edx
0x140015b8d  shr     edi, 6
0x140015b90  mov     eax, 88888889h
0x140015b95  mul     edi
0x140015b97  shr     edx, 5
0x140015b9a  imul    ecx, edx, 3Ch ; '<'
0x140015b9d  mov     ebx, edi
0x140015b9f  sub     ebx, ecx
0x140015ba1  mov     eax, 45E7B273h
0x140015ba6  mul     esi
0x140015ba8  mov     r11d, edx
0x140015bab  shr     r11d, 0Eh
0x140015baf  mov     eax, 88888889h
0x140015bb4  mul     r11d
0x140015bb7  shr     edx, 5
0x140015bba  imul    ecx, edx, 3Ch ; '<'
0x140015bbd  sub     r11d, ecx
0x140015bc0  mov     eax, 95217CB1h
0x140015bc5  mul     esi
0x140015bc7  mov     r10d, edx
0x140015bca  shr     r10d, 15h
0x140015bce  mov     eax, 88888889h
0x140015bd3  mul     r10d
0x140015bd6  shr     edx, 5
0x140015bd9  imul    eax, edx, 3Ch ; '<'
0x140015bdc  sub     r10d, eax
0x140015bdf  mov     r9d, [rsp+1A8h+var_150]
0x140015be4  cmp     [rsp+1A8h+var_120], 0FFh
0x140015bef  cmovnz  r14d, [rsp+1A8h+var_120]
0x140015bf8  imul    eax, edi, 3E8h
0x140015bfe  mov     ecx, esi
0x140015c00  sub     ecx, eax
0x140015c02  mov     [rsp+1A8h+var_160], r9d
0x140015c07  mov     dword ptr [rsp+1A8h+var_168], esi
0x140015c0b  mov     dword ptr [rsp+1A8h+var_170], ecx
0x140015c0f  mov     dword ptr [rsp+1A8h+var_178], ebx
0x140015c13  mov     dword ptr [rsp+1A8h+var_180], r11d
0x140015c18  mov     dword ptr [rsp+1A8h+var_188], r10d
0x140015c1d  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140015c24  mov     r8d, r14d; unsigned int
0x140015c27  lea     rdx, aExit; "EXIT"
0x140015c2e  lea     rcx, [rsp+1A8h+var_158]; this
0x140015c33  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140015c38  mov     rcx, [rsp+1A8h+var_F8]
0x140015c40  call    cs:__imp_VssSetTracingContextPerThread
0x140015c46  lea     r11, [rsp+1A8h+var_28]
0x140015c4e  mov     rbx, [r11+40h]
0x140015c52  mov     rsi, [r11+48h]
0x140015c56  mov     rsp, r11
0x140015c59  pop     r15
0x140015c5b  pop     r14
0x140015c5d  pop     r13
0x140015c5f  pop     r12
0x140015c61  pop     rdi
0x140015c62  retn
0x140015c63  call    cs:__imp_CoTaskMemFree
0x140015c69  mov     [rsp+rbx*8+1A8h+var_C0], rdi
0x140015c71  jmp     loc_140015AF1
0x140015c76  lea     rcx, [rsp+1A8h+var_158]
0x140015c7b  call    cs:__imp_VssSetTracingContextPerThread
0x140015c81  test    eax, eax
0x140015c83  js      loc_140015A84
0x140015c89  mov     rax, [rsp+1A8h+arg_8]
0x140015c91  mov     [rsp+1A8h+var_F8], rax
0x140015c99  jmp     loc_140015A8C
0x140015c9e  mov     [rsp+1A8h+var_128], edi
0x140015ca5  jmp     loc_140015AA1
0x140015caa  mov     [rsp+1A8h+var_168], rdi
0x140015caf  mov     dword ptr [rsp+1A8h+var_170], ebx
0x140015cb3  lea     rax, aEnter; "ENTER"
0x140015cba  mov     [rsp+1A8h+var_178], rax
0x140015cbf  mov     rax, [rsp+1A8h+var_130]
0x140015cc4  mov     [rsp+1A8h+var_180], rax
0x140015cc9  mov     eax, [rsp+1A8h+var_134]
0x140015ccd  mov     dword ptr [rsp+1A8h+var_188], eax
0x140015cd1  mov     r9d, [rsp+1A8h+var_128]
0x140015cd9  mov     r8d, [rsp+1A8h+var_138]
0x140015cde  mov     rdx, [rsp+1A8h+var_140]
0x140015ce3  mov     rcx, [rsp+1A8h+var_148]
0x140015ce8  call    cs:__imp_VssTraceMessage
0x140015cee  jmp     loc_140015AD3
0x140015cf3  mov     [rsp+1A8h+var_E8], r15
0x140015cfb  mov     [rsp+1A8h+var_E0], r12
0x140015d03  mov     [rsp+1A8h+var_D8], r13
0x140015d0b  mov     [rsp+1A8h+var_D0], 0C9h
0x140015d16  mov     [rsp+1A8h+var_CC], 0Bh
0x140015d21  mov     [rsp+1A8h+var_C8], 0FFh
0x140015d2c  mov     [rsp+1A8h+var_48], 1000000h
0x140015d37  xor     edx, edx; Val
0x140015d39  mov     r8d, 78h ; 'x'; Size
0x140015d3f  lea     rcx, [rsp+1A8h+var_C0]; void *
0x140015d47  call    memset_0
0x140015d4c  movzx   edx, byte ptr [rsi+29h]
0x140015d50  lea     rax, aNonInitialized; "Non-initialized CS"
0x140015d57  mov     [rsp+1A8h+var_188], rax
0x140015d5c  mov     r9d, 8007000Eh
0x140015d62  lea     r8, [rsp+1A8h+var_E8]
0x140015d6a  lea     rcx, [rsp+1A8h+var_158]
0x140015d6f  call    ?ThrowIf@CVssFunctionTracer@@QEAAXHUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::ThrowIf(int,CVssDebugInfo,long,ushort * const,...)
0x140015d74  jmp     loc_140015B04
0x140015d79  jmp     short loc_140015D7F
0x140015d7b  jmp     short loc_140015D7F
0x140015d7d  jmp     short $+2
0x140015d7f  mov     rsi, [rsp+1A8h+arg_0]
0x140015d87  mov     r14d, 0A0h
0x140015d8d  xor     edi, edi
0x140015d8f  lea     r13, aInctypeh; "INCTYPEH"
0x140015d96  lea     r12, aCvsscriticalse_1; "CVssCriticalSection::Lock"
0x140015d9d  lea     r15, aBaseStorVssInc_3; "base\\stor\\vss\\inc\\vs_types.hxx"
0x140015da4  jmp     loc_140015B0E
0x140015da9  mov     [rsp+1A8h+var_E8], r15
0x140015db1  mov     [rsp+1A8h+var_E0], r12
0x140015db9  mov     [rsp+1A8h+var_D8], r13
0x140015dc1  mov     [rsp+1A8h+var_D0], 0D4h
0x140015dcc  mov     [rsp+1A8h+var_CC], 0Bh
0x140015dd7  mov     [rsp+1A8h+var_C8], 0FFh
0x140015de2  mov     [rsp+1A8h+var_48], 1000000h
0x140015ded  xor     edx, edx; Val
0x140015def  mov     r8d, 78h ; 'x'; Size
0x140015df5  lea     rcx, [rsp+1A8h+var_C0]; void *
0x140015dfd  call    memset_0
0x140015e02  movzx   edx, byte ptr [rsi+29h]
0x140015e06  lea     rax, aErrorEnteringI; "Error entering into CS"
0x140015e0d  mov     [rsp+1A8h+var_188], rax
0x140015e12  mov     r9d, 8007000Eh
0x140015e18  lea     r8, [rsp+1A8h+var_E8]
0x140015e20  lea     rcx, [rsp+1A8h+var_158]
0x140015e25  call    ?ThrowIf@CVssFunctionTracer@@QEAAXHUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::ThrowIf(int,CVssDebugInfo,long,ushort * const,...)
0x140015e2a  jmp     loc_140015B19
```
