# CVssAutoString<CVssAutoLocalPtr<ushort *>>::ExpandEnvironmentStringsW(ushort const *)

- ea: `0x14003a09c`
- end: `0x14003a3f6`
- name: `?ExpandEnvironmentStringsW@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z`
- size: `858`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140015fb0`
- `0x140024500`

## callees

- `0x1400137c0`
- `0x140013cb0`
- `0x140028b48`
- `0x14003a09c`
- `0x1400921dc`
- `0x1400921e8`
- `0x14009c900`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14003a1e3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14003a238`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14003a1e3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14003a238`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003a256`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003a256`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14003a21c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14003a21c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003a13d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003a13d`
- `VssTrace!__imp_VssTraceMessage` at `0x14003a2f8`
- `VssTrace!__imp_VssTraceMessage` at `0x14003a2f8`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003a298`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003a298`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003a176`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003a176`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003a283`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003a283`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::ExpandEnvironmentStringsW(
        __int64 a1,
        const WCHAR *a2)
{
  __int64 v4; // rcx
  int v5; // ebx
  __int64 i; // rbx
  void *v7; // rcx
  DWORD v8; // edi
  void *v9; // rbx
  WCHAR *v10; // rax
  DWORD v11; // eax
  int v12; // eax
  __int64 v13; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+58h] [rbp-A8h]
  const wchar_t *v16; // [rsp+60h] [rbp-A0h]
  const wchar_t *v17; // [rsp+68h] [rbp-98h]
  unsigned int v18; // [rsp+70h] [rbp-90h]
  int v19; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v20; // [rsp+78h] [rbp-88h]
  unsigned int v21; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  int v23; // [rsp+88h] [rbp-78h]
  __int128 v24; // [rsp+90h] [rbp-70h]
  __int128 v25; // [rsp+A0h] [rbp-60h]
  __int64 v26; // [rsp+B0h] [rbp-50h]
  const wchar_t *v27; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v28; // [rsp+C8h] [rbp-38h]
  const wchar_t *v29; // [rsp+D0h] [rbp-30h]
  int v30; // [rsp+D8h] [rbp-28h]
  int v31; // [rsp+DCh] [rbp-24h]
  int v32; // [rsp+E0h] [rbp-20h]
  LPVOID pv[15]; // [rsp+E8h] [rbp-18h] BYREF
  int v34; // [rsp+160h] [rbp+60h]
  _QWORD v35[3]; // [rsp+168h] [rbp+68h] BYREF
  __int64 pExceptionObject; // [rsp+1C0h] [rbp+C0h] BYREF

  v27 = L"base\\stor\\vss\\inc\\vs_str.hxx";
  v28 = L"CVssAutoString<class CVssAutoLocalPtr<unsigned short *> >::ExpandEnvironmentStringsW";
  v29 = L"INCSTRH";
  v30 = 271;
  v31 = 11;
  v32 = 255;
  v34 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v15 = 0;
  v20 = L"CVssAutoString<class CVssAutoLocalPtr<unsigned short *> >::ExpandEnvironmentStringsW";
  v16 = L"base\\stor\\vss\\inc\\vs_str.hxx";
  v17 = L"INCSTRH";
  v18 = 271;
  v19 = 11;
  TickCount = GetTickCount();
  v23 = 255;
  v14 = 0xFFFFFFFF00000000uLL;
  v26 = 0;
  v24 = 0;
  v25 = 0;
  pExceptionObject = 0;
  if ( (int)VssGetTracingContextPerThread(&pExceptionObject) >= 0 )
  {
    v12 = VssSetTracingContextPerThread(&v14);
    v4 = v26;
    if ( v12 >= 0 )
      v4 = pExceptionObject;
    v26 = v4;
  }
  else
  {
    v4 = v26;
  }
  if ( v4 )
    v21 = *(_DWORD *)(v4 + 48) + 1;
  else
    v21 = 0;
  v5 = 160;
  if ( v23 != 255 )
    v5 = v23;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v14) )
    VssTraceMessage(v16, v17, v18, v21, v19, v20, L"ENTER", v5, 0);
  if ( HIBYTE(v34) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v7 = pv[i];
      if ( v7 )
      {
        CoTaskMemFree(v7);
        pv[i] = 0;
      }
    }
  }
  v8 = ExpandEnvironmentStringsW(a2, 0, 0);
  if ( !v8 )
  {
    v27 = L"base\\stor\\vss\\inc\\vs_str.hxx";
    v28 = L"CVssAutoString<class CVssAutoLocalPtr<unsigned short *> >::ExpandEnvironmentStringsW";
    v29 = L"INCSTRH";
    v30 = 275;
    v31 = 11;
    v32 = 255;
    v34 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    CVssFunctionTracer::TranslateWin32Error(&v14, &v27, L"ExpandEnvironmentString(%s, NULL, 0)", a2);
  }
  v9 = *(void **)(a1 + 8);
  *(_QWORD *)(a1 + 8) = 0;
  v35[1] = v9;
  v35[0] = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  if ( v8 != 1 )
  {
    v10 = (WCHAR *)LocalAlloc(0, 2LL * (v8 - 1) + 2);
    *(_QWORD *)(a1 + 8) = v10;
    if ( !v10 )
    {
      LODWORD(pExceptionObject) = -2147024882;
      throw (long *)&pExceptionObject;
    }
    v11 = ExpandEnvironmentStringsW(a2, v10, v8);
    if ( !v11 || v11 > v8 )
    {
      CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>::TransferFrom(
        a1,
        v35);
      v27 = L"base\\stor\\vss\\inc\\vs_str.hxx";
      v28 = L"CVssAutoString<class CVssAutoLocalPtr<unsigned short *> >::ExpandEnvironmentStringsW";
      v29 = L"INCSTRH";
      v30 = 287;
      v31 = 11;
      v32 = 255;
      v34 = 0x1000000;
      memset_0(pv, 0, sizeof(pv));
      LODWORD(v13) = v8;
      CVssFunctionTracer::TranslateWin32Error(
        &v14,
        &v27,
        L"ExpandEnvironmentString(%s, %p, %d)",
        a2,
        *(_QWORD *)(a1 + 8),
        v13);
    }
  }
  if ( v9 )
    LocalFree(v9);
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v14);
}

```

## disassembly

```asm
0x14003a09c  mov     [rsp-8+arg_0], rbx
0x14003a0a1  mov     [rsp-8+arg_8], rsi
0x14003a0a6  push    rbp
0x14003a0a7  push    rdi
0x14003a0a8  push    r13
0x14003a0aa  push    r14
0x14003a0ac  push    r15
0x14003a0ae  lea     rbp, [rsp-80h]
0x14003a0b3  sub     rsp, 180h
0x14003a0ba  mov     r14, rdx
0x14003a0bd  mov     rsi, rcx
0x14003a0c0  lea     r13, aBaseStorVssInc_1; "base\\stor\\vss\\inc\\vs_str.hxx"
0x14003a0c7  mov     [rbp+0A0h+var_E0], r13
0x14003a0cb  lea     rax, aCvssautostring; "CVssAutoString<class CVssAutoLocalPtr<u"...
0x14003a0d2  mov     [rbp+0A0h+var_D8], rax
0x14003a0d6  lea     rax, aIncstrh; "INCSTRH"
0x14003a0dd  mov     [rbp+0A0h+var_D0], rax
0x14003a0e1  mov     [rbp+0A0h+var_C8], 10Fh
0x14003a0e8  mov     [rbp+0A0h+var_C4], 0Bh
0x14003a0ef  mov     [rbp+0A0h+var_C0], 0FFh
0x14003a0f6  xor     r15d, r15d
0x14003a0f9  mov     [rbp+0A0h+var_40], 1000000h
0x14003a100  xor     edx, edx; Val
0x14003a102  lea     r8d, [r15+78h]; Size
0x14003a106  lea     rcx, [rbp+0A0h+pv]; void *
0x14003a10a  call    memset_0
0x14003a10f  mov     [rsp+1A0h+var_148], r15d
0x14003a114  mov     rax, [rbp+0A0h+var_D8]
0x14003a118  mov     [rsp+1A0h+var_128], rax
0x14003a11d  mov     rax, [rbp+0A0h+var_E0]
0x14003a121  mov     [rsp+1A0h+var_140], rax
0x14003a126  mov     rax, [rbp+0A0h+var_D0]
0x14003a12a  mov     [rsp+1A0h+var_138], rax
0x14003a12f  mov     eax, [rbp+0A0h+var_C8]
0x14003a132  mov     [rsp+1A0h+var_130], eax
0x14003a136  mov     eax, [rbp+0A0h+var_C4]
0x14003a139  mov     [rsp+1A0h+var_12C], eax
0x14003a13d  call    cs:__imp_GetTickCount
0x14003a143  mov     [rbp+0A0h+var_11C], eax
0x14003a146  mov     [rsp+1A0h+var_14C], 0FFFFFFFFh
0x14003a14e  mov     eax, [rbp+0A0h+var_C0]
0x14003a151  mov     [rbp+0A0h+var_118], eax
0x14003a154  mov     [rsp+1A0h+var_150], r15d
0x14003a159  mov     [rbp+0A0h+var_F0], r15
0x14003a15d  xorps   xmm0, xmm0
0x14003a160  movups  [rbp+0A0h+var_110], xmm0
0x14003a164  movups  [rbp+0A0h+var_100], xmm0
0x14003a168  mov     [rbp+0A0h+pExceptionObject], r15
0x14003a16f  lea     rcx, [rbp+0A0h+pExceptionObject]
0x14003a176  call    cs:__imp_VssGetTracingContextPerThread
0x14003a17c  test    eax, eax
0x14003a17e  jns     loc_14003A293
0x14003a184  mov     rcx, [rbp+0A0h+var_F0]
0x14003a188  test    rcx, rcx
0x14003a18b  jz      loc_14003A2B5
0x14003a191  mov     eax, [rcx+30h]
0x14003a194  inc     eax
0x14003a196  mov     [rbp+0A0h+var_120], eax
0x14003a199  mov     ebx, 0A0h
0x14003a19e  cmp     [rbp+0A0h+var_118], 0FFh
0x14003a1a5  cmovnz  ebx, [rbp+0A0h+var_118]
0x14003a1a9  lea     rcx, [rsp+1A0h+var_150]; this
0x14003a1ae  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14003a1b3  test    eax, eax
0x14003a1b5  jnz     loc_14003A2BE
0x14003a1bb  cmp     byte ptr [rbp+0A0h+var_40+3], r15b
0x14003a1bf  jz      short loc_14003A1DB
0x14003a1c1  mov     rbx, r15
0x14003a1c4  mov     rcx, [rbp+rbx*8+0A0h+pv]; pv
0x14003a1c9  test    rcx, rcx
0x14003a1cc  jnz     loc_14003A283
0x14003a1d2  inc     rbx
0x14003a1d5  cmp     rbx, 0Fh
0x14003a1d9  jnz     short loc_14003A1C4
0x14003a1db  xor     r8d, r8d; nSize
0x14003a1de  xor     edx, edx; lpDst
0x14003a1e0  mov     rcx, r14; lpSrc
0x14003a1e3  call    cs:__imp_ExpandEnvironmentStringsW
0x14003a1e9  mov     edi, eax
0x14003a1eb  test    eax, eax
0x14003a1ed  jz      loc_14003A303
0x14003a1f3  mov     rbx, [rsi+8]
0x14003a1f7  mov     [rsi+8], r15
0x14003a1fb  mov     [rbp+0A0h+var_30], rbx
0x14003a1ff  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x14003a206  mov     [rbp+0A0h+var_38], rax
0x14003a20a  cmp     edi, 1
0x14003a20d  jz      short loc_14003A24E
0x14003a20f  lea     eax, [rdi-1]
0x14003a212  lea     rdx, ds:2[rax*2]; uBytes
0x14003a21a  xor     ecx, ecx; uFlags
0x14003a21c  call    cs:__imp_LocalAlloc
0x14003a222  mov     [rsi+8], rax
0x14003a226  test    rax, rax
0x14003a229  jz      loc_14003A361
0x14003a22f  mov     r8d, edi; nSize
0x14003a232  mov     rdx, rax; lpDst
0x14003a235  mov     rcx, r14; lpSrc
0x14003a238  call    cs:__imp_ExpandEnvironmentStringsW
0x14003a23e  test    eax, eax
0x14003a240  jz      loc_14003A37F
0x14003a246  cmp     eax, edi
0x14003a248  ja      loc_14003A37F
0x14003a24e  test    rbx, rbx
0x14003a251  jz      short loc_14003A25D
0x14003a253  mov     rcx, rbx; hMem
0x14003a256  call    cs:__imp_LocalFree
0x14003a25c  nop
0x14003a25d  lea     rcx, [rsp+1A0h+var_150]; this
0x14003a262  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14003a267  lea     r11, [rsp+1A0h+var_20]
0x14003a26f  mov     rbx, [r11+30h]
0x14003a273  mov     rsi, [r11+38h]
0x14003a277  mov     rsp, r11
0x14003a27a  pop     r15
0x14003a27c  pop     r14
0x14003a27e  pop     r13
0x14003a280  pop     rdi
0x14003a281  pop     rbp
0x14003a282  retn
0x14003a283  call    cs:__imp_CoTaskMemFree
0x14003a289  mov     [rbp+rbx*8+0A0h+pv], r15
0x14003a28e  jmp     loc_14003A1D2
0x14003a293  lea     rcx, [rsp+1A0h+var_150]
0x14003a298  call    cs:__imp_VssSetTracingContextPerThread
0x14003a29e  mov     rcx, [rbp+0A0h+var_F0]
0x14003a2a2  test    eax, eax
0x14003a2a4  cmovns  rcx, [rbp+0A0h+pExceptionObject]
0x14003a2ac  mov     [rbp+0A0h+var_F0], rcx
0x14003a2b0  jmp     loc_14003A188
0x14003a2b5  mov     [rbp+0A0h+var_120], r15d
0x14003a2b9  jmp     loc_14003A199
0x14003a2be  mov     [rsp+1A0h+var_160], r15
0x14003a2c3  mov     [rsp+1A0h+var_168], ebx
0x14003a2c7  lea     rax, aEnter; "ENTER"
0x14003a2ce  mov     [rsp+1A0h+var_170], rax
0x14003a2d3  mov     rax, [rsp+1A0h+var_128]
0x14003a2d8  mov     [rsp+1A0h+var_178], rax
0x14003a2dd  mov     eax, [rsp+1A0h+var_12C]
0x14003a2e1  mov     dword ptr [rsp+1A0h+var_180], eax
0x14003a2e5  mov     r9d, [rbp+0A0h+var_120]
0x14003a2e9  mov     r8d, [rsp+1A0h+var_130]
0x14003a2ee  mov     rdx, [rsp+1A0h+var_138]
0x14003a2f3  mov     rcx, [rsp+1A0h+var_140]
0x14003a2f8  call    cs:__imp_VssTraceMessage
0x14003a2fe  jmp     loc_14003A1BB
0x14003a303  mov     [rbp+0A0h+var_E0], r13
0x14003a307  lea     rax, aCvssautostring; "CVssAutoString<class CVssAutoLocalPtr<u"...
0x14003a30e  mov     [rbp+0A0h+var_D8], rax
0x14003a312  lea     rax, aIncstrh; "INCSTRH"
0x14003a319  mov     [rbp+0A0h+var_D0], rax
0x14003a31d  mov     [rbp+0A0h+var_C8], 113h
0x14003a324  mov     [rbp+0A0h+var_C4], 0Bh
0x14003a32b  mov     [rbp+0A0h+var_C0], 0FFh
0x14003a332  mov     [rbp+0A0h+var_40], 1000000h
0x14003a339  xor     edx, edx; Val
0x14003a33b  lea     r8d, [rdx+78h]; Size
0x14003a33f  lea     rcx, [rbp+0A0h+pv]; void *
0x14003a343  call    memset_0
0x14003a348  mov     r9, r14
0x14003a34b  lea     r8, aExpandenvironm; "ExpandEnvironmentString(%s, NULL, 0)"
0x14003a352  lea     rdx, [rbp+0A0h+var_E0]
0x14003a356  lea     rcx, [rsp+1A0h+var_150]
0x14003a35b  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x14003a361  mov     dword ptr [rbp+0A0h+pExceptionObject], 8007000Eh
0x14003a36b  lea     rdx, _TI1J; pThrowInfo
0x14003a372  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x14003a379  call    _CxxThrowException_0
0x14003a37f  lea     rdx, [rbp+0A0h+var_38]
0x14003a383  mov     rcx, rsi
0x14003a386  call    ?TransferFrom@?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6APEAX_K@Z$1?LocalAllocate@@YAPEAX1@Z@@@@QEAAXAEAV1@@Z; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void * (*)(void *),&LocalFree(void *),void * (*)(unsigned __int64),&LocalAllocate(unsigned __int64)>>::TransferFrom(CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void * (*)(void *),&LocalFree(void *),void * (*)(unsigned __int64),&LocalAllocate(unsigned __int64)>> &)
0x14003a38b  mov     [rbp+0A0h+var_E0], r13
0x14003a38f  lea     rax, aCvssautostring; "CVssAutoString<class CVssAutoLocalPtr<u"...
0x14003a396  mov     [rbp+0A0h+var_D8], rax
0x14003a39a  lea     rax, aIncstrh; "INCSTRH"
0x14003a3a1  mov     [rbp+0A0h+var_D0], rax
0x14003a3a5  mov     [rbp+0A0h+var_C8], 11Fh
0x14003a3ac  mov     [rbp+0A0h+var_C4], 0Bh
0x14003a3b3  mov     [rbp+0A0h+var_C0], 0FFh
0x14003a3ba  mov     [rbp+0A0h+var_40], 1000000h
0x14003a3c1  xor     edx, edx; Val
0x14003a3c3  lea     r8d, [rdx+78h]; Size
0x14003a3c7  lea     rcx, [rbp+0A0h+pv]; void *
0x14003a3cb  call    memset_0
0x14003a3d0  mov     dword ptr [rsp+1A0h+var_178], edi
0x14003a3d4  mov     rax, [rsi+8]
0x14003a3d8  mov     [rsp+1A0h+var_180], rax
0x14003a3dd  mov     r9, r14
0x14003a3e0  lea     r8, aExpandenvironm_0; "ExpandEnvironmentString(%s, %p, %d)"
0x14003a3e7  lea     rdx, [rbp+0A0h+var_E0]
0x14003a3eb  lea     rcx, [rsp+1A0h+var_150]
0x14003a3f0  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
```
