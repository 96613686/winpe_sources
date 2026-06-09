# CVssDiag::FlushQueue(void)

- ea: `0x140008094`
- end: `0x140008417`
- name: `?FlushQueue@CVssDiag@@AEAAXXZ`
- size: `899`
- prototype: `void __fastcall(CVssDiag *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140006270`
- `0x14000889c`
- `0x140018130`

## callees

- `0x140008094`
- `0x140008cd0`
- `0x1400138e0`
- `0x140013cb0`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140008156`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140008261`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140008156`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140008261`
- `VssTrace!__imp_VssTraceMessage` at `0x1400083f8`
- `VssTrace!__imp_VssTraceMessage` at `0x1400083f8`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000832c`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140008363`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000832c`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140008363`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400081a8`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400081a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000824a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000834b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000824a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000834b`

## string_xrefs

- `0x1400080ae`: `base\stor\vss\modules\registry\registry.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssDiag::FlushQueue(CVssDiag *this)
{
  __int64 v2; // rcx
  unsigned int v3; // r14d
  unsigned int v4; // edi
  unsigned int v5; // r9d
  __int64 i; // rdi
  void *v7; // rcx
  unsigned int v8; // r15d
  unsigned int v9; // edi
  __int64 j; // rdi
  DWORD v11; // esi
  int v12; // eax
  __int64 v13; // [rsp+20h] [rbp-178h]
  __int64 v14; // [rsp+28h] [rbp-170h]
  __int64 v15; // [rsp+30h] [rbp-168h]
  __int64 v16; // [rsp+38h] [rbp-160h]
  __int64 v17; // [rsp+40h] [rbp-158h]
  _DWORD v18[2]; // [rsp+50h] [rbp-148h] BYREF
  int v19; // [rsp+58h] [rbp-140h]
  const unsigned __int16 *v20; // [rsp+60h] [rbp-138h]
  const unsigned __int16 *v21; // [rsp+68h] [rbp-130h]
  unsigned int v22; // [rsp+70h] [rbp-128h]
  unsigned int v23; // [rsp+74h] [rbp-124h]
  const unsigned __int16 *v24; // [rsp+78h] [rbp-120h]
  unsigned int v25; // [rsp+80h] [rbp-118h]
  DWORD TickCount; // [rsp+84h] [rbp-114h]
  unsigned int v27; // [rsp+88h] [rbp-110h]
  LPVOID pv[2]; // [rsp+90h] [rbp-108h]
  __int128 v29; // [rsp+A0h] [rbp-F8h]
  __int64 v30; // [rsp+B0h] [rbp-E8h]
  int v31; // [rsp+C0h] [rbp-D8h] BYREF
  const std::exception *v32; // [rsp+C8h] [rbp-D0h] BYREF
  _com_error *v33[4]; // [rsp+D0h] [rbp-C8h] BYREF
  int v34; // [rsp+F0h] [rbp-A8h]
  int v35; // [rsp+F4h] [rbp-A4h]
  int v36; // [rsp+F8h] [rbp-A0h]
  LPVOID v37[15]; // [rsp+100h] [rbp-98h] BYREF
  int v38; // [rsp+178h] [rbp-20h]
  __int64 v39; // [rsp+1A0h] [rbp+8h] BYREF

  v33[1] = (_com_error *)L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v33[2] = (_com_error *)L"CVssDiag::FlushQueue";
  v33[3] = (_com_error *)L"REGREGSC";
  v34 = 1399;
  v35 = 11;
  v36 = 255;
  v38 = 0x1000000;
  memset_0(v37, 0, sizeof(v37));
  v19 = 0;
  v24 = L"CVssDiag::FlushQueue";
  v20 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v21 = L"REGREGSC";
  v22 = 1399;
  v23 = 11;
  TickCount = GetTickCount();
  v18[1] = -1;
  v27 = 255;
  v18[0] = 0;
  v30 = 0;
  *(_OWORD *)pv = 0;
  v29 = 0;
  v39 = 0;
  if ( (int)VssGetTracingContextPerThread(&v39) >= 0 )
  {
    v12 = VssSetTracingContextPerThread(v18);
    v2 = v30;
    if ( v12 >= 0 )
      v2 = v39;
    v30 = v2;
  }
  else
  {
    v2 = v30;
  }
  if ( v2 )
    v25 = *(_DWORD *)(v2 + 48) + 1;
  else
    v25 = 0;
  v3 = 160;
  v4 = 160;
  if ( v27 != 255 )
    v4 = v27;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v18) )
    VssTraceMessage(v20, v21, v22, v25, v23, v24, L"ENTER", v4, 0);
  if ( HIBYTE(v38) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v7 = v37[i];
      if ( v7 )
      {
        CoTaskMemFree(v7);
        v37[i] = 0;
      }
    }
  }
  v8 = *((_DWORD *)this + 210);
  *((_DWORD *)this + 210) = 0;
  v9 = 0;
  while ( v9 < v8 )
  {
    try
    {
      CVssRegistryKey::SetBinaryValue(
        this,
        *((const unsigned __int16 **)this + 10 * v9 + 14),
        (unsigned __int8 *)this + 80 * v9 + 40,
        v5);
      ++v9;
    }
    catch ( long v31 )
    {
      CVssFunctionTracer::HandleHresultException(
        (CVssFunctionTracer *)v18,
        v31,
        L"base\\stor\\vss\\modules\\registry\\registry.cxx",
        L"REGREGSC",
        L"CVssDiag::FlushQueue",
        0x585u,
        v23);
      v3 = 160;
      break;
    }
    catch ( _com_error *v33 )
    {
      CVssFunctionTracer::HandleComException(
        (CVssFunctionTracer *)v18,
        v33[0],
        L"base\\stor\\vss\\modules\\registry\\registry.cxx",
        L"REGREGSC",
        L"CVssDiag::FlushQueue",
        0x585u,
        v23);
    }
    catch ( std::bad_alloc )
    {
      CVssFunctionTracer::HandleStdBadAllocException(
        (CVssFunctionTracer *)v18,
        L"base\\stor\\vss\\modules\\registry\\registry.cxx",
        L"REGREGSC",
        L"CVssDiag::FlushQueue",
        0x585u,
        v23);
      v3 = 160;
      break;
    }
    catch ( const std::exception *v32 )
    {
      CVssFunctionTracer::HandleStdGenericException(
        (CVssFunctionTracer *)v18,
        v32,
        L"base\\stor\\vss\\modules\\registry\\registry.cxx",
        L"REGREGSC",
        L"CVssDiag::FlushQueue",
        0x585u,
        v23);
    }
  }
  for ( j = 0; j != 4; ++j )
  {
    CoTaskMemFree(pv[j]);
    pv[j] = 0;
  }
  v11 = GetTickCount() - TickCount;
  if ( v27 != 255 )
    v3 = v27;
  LODWORD(v17) = v11;
  LODWORD(v16) = v11 % 0x3E8;
  LODWORD(v15) = v11 / 0x3E8 % 0x3C;
  LODWORD(v14) = v11 / 0xEA60 % 0x3C;
  LODWORD(v13) = v11 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v18,
    L"EXIT",
    v3,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v13,
    v14,
    v15,
    v16,
    v17,
    v19);
  VssSetTracingContextPerThread(v30);
}

```

## disassembly

```asm
0x140008094  mov     r11, rsp
0x140008097  mov     [r11+10h], rbx
0x14000809b  mov     [r11+18h], rsi
0x14000809f  push    rdi
0x1400080a0  push    r14
0x1400080a2  push    r15
0x1400080a4  sub     rsp, 180h
0x1400080ab  mov     rsi, rcx
0x1400080ae  lea     rax, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x1400080b5  mov     [r11-0C0h], rax
0x1400080bc  lea     rax, aCvssdiagFlushq; "CVssDiag::FlushQueue"
0x1400080c3  mov     [r11-0B8h], rax
0x1400080ca  lea     rax, aRegregsc; "REGREGSC"
0x1400080d1  mov     [r11-0B0h], rax
0x1400080d8  mov     [rsp+198h+var_A8], 577h
0x1400080e3  mov     [rsp+198h+var_A4], 0Bh
0x1400080ee  mov     [rsp+198h+var_A0], 0FFh
0x1400080f9  xor     ebx, ebx
0x1400080fb  mov     dword ptr [r11-20h], 1000000h
0x140008103  xor     edx, edx; Val
0x140008105  lea     r8d, [rbx+78h]; Size
0x140008109  lea     rcx, [r11-98h]; void *
0x140008110  call    memset_0
0x140008115  mov     [rsp+198h+var_140], ebx
0x140008119  mov     rax, [rsp+198h+var_B8]
0x140008121  mov     [rsp+198h+var_120], rax
0x140008126  mov     rax, [rsp+198h+var_C0]
0x14000812e  mov     [rsp+198h+var_138], rax
0x140008133  mov     rax, [rsp+198h+var_B0]
0x14000813b  mov     [rsp+198h+var_130], rax
0x140008140  mov     eax, [rsp+198h+var_A8]
0x140008147  mov     [rsp+198h+var_128], eax
0x14000814b  mov     eax, [rsp+198h+var_A4]
0x140008152  mov     [rsp+198h+var_124], eax
0x140008156  call    cs:__imp_GetTickCount
0x14000815c  mov     [rsp+198h+var_114], eax
0x140008163  mov     [rsp+198h+var_144], 0FFFFFFFFh
0x14000816b  mov     eax, [rsp+198h+var_A0]
0x140008172  mov     [rsp+198h+var_110], eax
0x140008179  mov     [rsp+198h+var_148], ebx
0x14000817d  mov     [rsp+198h+var_E8], rbx
0x140008185  xorps   xmm0, xmm0
0x140008188  movups  xmmword ptr [rsp+198h+pv], xmm0
0x140008190  movups  [rsp+198h+var_F8], xmm0
0x140008198  mov     [rsp+198h+arg_0], rbx
0x1400081a0  lea     rcx, [rsp+198h+arg_0]
0x1400081a8  call    cs:__imp_VssGetTracingContextPerThread
0x1400081ae  test    eax, eax
0x1400081b0  jns     loc_14000835E
0x1400081b6  mov     rcx, [rsp+198h+var_E8]
0x1400081be  test    rcx, rcx
0x1400081c1  jz      loc_1400083AE
0x1400081c7  mov     eax, [rcx+30h]
0x1400081ca  inc     eax
0x1400081cc  mov     [rsp+198h+var_118], eax
0x1400081d3  mov     r14d, 0A0h
0x1400081d9  mov     edi, r14d
0x1400081dc  cmp     [rsp+198h+var_110], 0FFh
0x1400081e7  cmovnz  edi, [rsp+198h+var_110]
0x1400081ef  lea     rcx, [rsp+198h+var_148]; this
0x1400081f4  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x1400081f9  test    eax, eax
0x1400081fb  jnz     loc_1400083BA
0x140008201  cmp     [rsp+198h+var_1D], bl
0x140008208  jz      short loc_140008227
0x14000820a  mov     rdi, rbx
0x14000820d  mov     rcx, [rsp+rdi*8+198h+var_98]; pv
0x140008215  test    rcx, rcx
0x140008218  jnz     loc_14000834B
0x14000821e  inc     rdi
0x140008221  cmp     rdi, 0Fh
0x140008225  jnz     short loc_14000820D
0x140008227  mov     r15d, [rsi+348h]
0x14000822e  mov     [rsi+348h], ebx
0x140008234  mov     edi, ebx
0x140008236  cmp     edi, r15d
0x140008239  jb      loc_140008389
0x14000823f  mov     rdi, rbx
0x140008242  mov     rcx, [rsp+rdi*8+198h+pv]; pv
0x14000824a  call    cs:__imp_CoTaskMemFree
0x140008250  mov     [rsp+rdi*8+198h+pv], rbx
0x140008258  inc     rdi
0x14000825b  cmp     rdi, 4
0x14000825f  jnz     short loc_140008242
0x140008261  call    cs:__imp_GetTickCount
0x140008267  mov     esi, eax
0x140008269  sub     esi, [rsp+198h+var_114]
0x140008270  mov     eax, 10624DD3h
0x140008275  mul     esi
0x140008277  mov     edi, edx
0x140008279  shr     edi, 6
0x14000827c  mov     r8d, 88888889h
0x140008282  mov     eax, r8d
0x140008285  mul     edi
0x140008287  shr     edx, 5
0x14000828a  imul    ecx, edx, 3Ch ; '<'
0x14000828d  mov     ebx, edi
0x14000828f  sub     ebx, ecx
0x140008291  mov     eax, 45E7B273h
0x140008296  mul     esi
0x140008298  mov     r11d, edx
0x14000829b  shr     r11d, 0Eh
0x14000829f  mov     eax, r8d
0x1400082a2  mul     r11d
0x1400082a5  shr     edx, 5
0x1400082a8  imul    ecx, edx, 3Ch ; '<'
0x1400082ab  sub     r11d, ecx
0x1400082ae  mov     eax, 95217CB1h
0x1400082b3  mul     esi
0x1400082b5  mov     r10d, edx
0x1400082b8  shr     r10d, 15h
0x1400082bc  mov     eax, r8d
0x1400082bf  mul     r10d
0x1400082c2  shr     edx, 5
0x1400082c5  imul    eax, edx, 3Ch ; '<'
0x1400082c8  sub     r10d, eax
0x1400082cb  mov     r9d, [rsp+198h+var_140]
0x1400082d0  cmp     [rsp+198h+var_110], 0FFh
0x1400082db  cmovnz  r14d, [rsp+198h+var_110]
0x1400082e4  imul    eax, edi, 3E8h
0x1400082ea  mov     ecx, esi
0x1400082ec  sub     ecx, eax
0x1400082ee  mov     [rsp+198h+var_150], r9d
0x1400082f3  mov     dword ptr [rsp+198h+var_158], esi
0x1400082f7  mov     dword ptr [rsp+198h+var_160], ecx
0x1400082fb  mov     dword ptr [rsp+198h+var_168], ebx
0x1400082ff  mov     dword ptr [rsp+198h+var_170], r11d
0x140008304  mov     dword ptr [rsp+198h+var_178], r10d
0x140008309  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140008310  mov     r8d, r14d; unsigned int
0x140008313  lea     rdx, aExit; "EXIT"
0x14000831a  lea     rcx, [rsp+198h+var_148]; this
0x14000831f  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140008324  mov     rcx, [rsp+198h+var_E8]
0x14000832c  call    cs:__imp_VssSetTracingContextPerThread
0x140008332  lea     r11, [rsp+198h+var_18]
0x14000833a  mov     rbx, [r11+28h]
0x14000833e  mov     rsi, [r11+30h]
0x140008342  mov     rsp, r11
0x140008345  pop     r15
0x140008347  pop     r14
0x140008349  pop     rdi
0x14000834a  retn
0x14000834b  call    cs:__imp_CoTaskMemFree
0x140008351  mov     [rsp+rdi*8+198h+var_98], rbx
0x140008359  jmp     loc_14000821E
0x14000835e  lea     rcx, [rsp+198h+var_148]
0x140008363  call    cs:__imp_VssSetTracingContextPerThread
0x140008369  mov     rcx, [rsp+198h+var_E8]
0x140008371  test    eax, eax
0x140008373  cmovns  rcx, [rsp+198h+arg_0]
0x14000837c  mov     [rsp+198h+var_E8], rcx
0x140008384  jmp     loc_1400081BE
0x140008389  mov     eax, edi
0x14000838b  lea     rdx, [rax+rax*4]
0x14000838f  shl     rdx, 4
0x140008393  lea     r8, [rsi+28h]
0x140008397  add     r8, rdx; unsigned __int8 *
0x14000839a  mov     rdx, [rdx+rsi+70h]; unsigned __int16 *
0x14000839f  mov     rcx, rsi; this
0x1400083a2  call    ?SetBinaryValue@CVssRegistryKey@@QEAAXPEBGPEAEK@Z; CVssRegistryKey::SetBinaryValue(ushort const *,uchar *,ulong)
0x1400083a7  inc     edi
0x1400083a9  jmp     loc_140008236
0x1400083ae  mov     [rsp+198h+var_118], ebx
0x1400083b5  jmp     loc_1400081D3
0x1400083ba  mov     [rsp+198h+var_158], rbx
0x1400083bf  mov     dword ptr [rsp+198h+var_160], edi
0x1400083c3  lea     rax, aEnter; "ENTER"
0x1400083ca  mov     [rsp+198h+var_168], rax
0x1400083cf  mov     rax, [rsp+198h+var_120]
0x1400083d4  mov     [rsp+198h+var_170], rax
0x1400083d9  mov     eax, [rsp+198h+var_124]
0x1400083dd  mov     dword ptr [rsp+198h+var_178], eax
0x1400083e1  mov     r9d, [rsp+198h+var_118]
0x1400083e9  mov     r8d, [rsp+198h+var_128]
0x1400083ee  mov     rdx, [rsp+198h+var_130]
0x1400083f3  mov     rcx, [rsp+198h+var_138]
0x1400083f8  call    cs:__imp_VssTraceMessage
0x1400083fe  jmp     loc_140008201
0x140008403  jmp     short loc_140008409
0x140008405  jmp     short loc_140008409
0x140008407  jmp     short $+2
0x140008409  mov     r14d, 0A0h
0x14000840f  xor     ebx, ebx
0x140008411  jmp     loc_14000823F
```
