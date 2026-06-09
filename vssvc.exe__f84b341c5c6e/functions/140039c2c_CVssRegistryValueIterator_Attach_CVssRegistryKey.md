# CVssRegistryValueIterator::Attach(CVssRegistryKey &)

- ea: `0x140039c2c`
- end: `0x140039f6f`
- name: `?Attach@CVssRegistryValueIterator@@QEAAXAEAVCVssRegistryKey@@@Z`
- size: `835`
- prototype: `void __fastcall(CVssRegistryValueIterator *__hidden this, struct CVssRegistryKey *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000c84c`

## callees

- `0x1400137c0`
- `0x140013cb0`
- `0x140039c2c`
- `0x140049ec4`
- `0x1400921dc`
- `0x1400921e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140039ddd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140039ddd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140039cc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140039cc3`
- `VssTrace!__imp_VssTraceMessage` at `0x140039f46`
- `VssTrace!__imp_VssTraceMessage` at `0x140039f46`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140039e68`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140039e68`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140039cfc`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140039cfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140039e0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140039e0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140039e53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140039e85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140039e91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140039e53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140039e85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140039e91`

## string_xrefs

- `0x140039c49`: `base\stor\vss\modules\registry\registry.cxx`
- `0x140039c54`: `CVssRegistryValueIterator::Attach`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssRegistryValueIterator::Attach(CVssRegistryValueIterator *this, struct CVssRegistryKey *a2)
{
  __int64 v4; // rcx
  int v5; // edi
  __int64 i; // rdi
  void *v7; // rcx
  void *v8; // rcx
  HKEY v9; // rcx
  LSTATUS v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rdi
  void *v13; // rcx
  LPVOID v14; // rax
  int v15; // eax
  __int64 v16; // rbx
  unsigned __int64 v17; // [rsp+60h] [rbp-A0h] BYREF
  int v18; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v19; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v20; // [rsp+78h] [rbp-88h]
  unsigned int v21; // [rsp+80h] [rbp-80h]
  int v22; // [rsp+84h] [rbp-7Ch]
  const wchar_t *v23; // [rsp+88h] [rbp-78h]
  unsigned int v24; // [rsp+90h] [rbp-70h]
  DWORD TickCount; // [rsp+94h] [rbp-6Ch]
  int v26; // [rsp+98h] [rbp-68h]
  __int128 v27; // [rsp+A0h] [rbp-60h]
  __int128 v28; // [rsp+B0h] [rbp-50h]
  __int64 v29; // [rsp+C0h] [rbp-40h]
  const unsigned __int16 *v30; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *v31; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v32; // [rsp+E0h] [rbp-20h]
  int v33; // [rsp+E8h] [rbp-18h]
  int v34; // [rsp+ECh] [rbp-14h]
  int v35; // [rsp+F0h] [rbp-10h]
  LPVOID pv[15]; // [rsp+F8h] [rbp-8h] BYREF
  int v37; // [rsp+170h] [rbp+70h]
  DWORD cbMaxValueNameLen; // [rsp+1C0h] [rbp+C0h] BYREF
  DWORD cValues; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 pExceptionObject; // [rsp+1D0h] [rbp+D0h] BYREF

  v30 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v31 = L"CVssRegistryValueIterator::Attach";
  v32 = L"REGREGSC";
  v33 = 1162;
  v34 = 11;
  v35 = 255;
  v37 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v18 = 0;
  v23 = L"CVssRegistryValueIterator::Attach";
  v19 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v20 = L"REGREGSC";
  v21 = 1162;
  v22 = 11;
  TickCount = GetTickCount();
  v26 = 255;
  v17 = 0xFFFFFFFF00000000uLL;
  v29 = 0;
  v27 = 0;
  v28 = 0;
  pExceptionObject = 0;
  if ( (int)VssGetTracingContextPerThread(&pExceptionObject) >= 0 )
  {
    v15 = VssSetTracingContextPerThread(&v17);
    v4 = v29;
    if ( v15 >= 0 )
      v4 = pExceptionObject;
    v29 = v4;
  }
  else
  {
    v4 = v29;
  }
  if ( v4 )
    v24 = *(_DWORD *)(v4 + 48) + 1;
  else
    v24 = 0;
  v5 = 160;
  if ( v26 != 255 )
    v5 = v26;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v17) )
    VssTraceMessage(v19, v20, v21, v24, v22, v23, L"ENTER", v5, 0);
  if ( HIBYTE(v37) )
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
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 10) = 0;
  v8 = (void *)*((_QWORD *)this + 4);
  if ( v8 )
    CoTaskMemFree(v8);
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 4) = 0;
  *((_DWORD *)this + 11) = 0;
  *((_WORD *)this + 24) = 0;
  v9 = (HKEY)*((_QWORD *)a2 + 1);
  *(_QWORD *)this = v9;
  cValues = 0;
  cbMaxValueNameLen = 0;
  v10 = RegQueryInfoKeyW(v9, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  v11 = v10;
  if ( v10 )
  {
    v16 = *(_QWORD *)this;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    v30 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v31 = L"CVssRegistryValueIterator::Attach";
    v32 = L"REGREGSC";
    v33 = 1186;
    v34 = 11;
    v35 = 255;
    v37 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    CVssFunctionTracer::TranslateGenericError(&v17, &v30, v11, L"RegQueryInfoKeyW(%p, ...)", v16);
  }
  v12 = cbMaxValueNameLen;
  v13 = (void *)*((_QWORD *)this + 4);
  if ( v13 )
    CoTaskMemFree(v13);
  *((_QWORD *)this + 4) = 0;
  v14 = CoTaskMemAlloc(2 * v12 + 2);
  *((_QWORD *)this + 4) = v14;
  if ( !v14 )
  {
    LODWORD(pExceptionObject) = -2147024882;
    throw (long *)&pExceptionObject;
  }
  *((_DWORD *)this + 2) = cValues;
  *((_DWORD *)this + 10) = cbMaxValueNameLen + 1;
  *((_BYTE *)this + 49) = 1;
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v17);
}

```

## disassembly

```asm
0x140039c2c  push    rbp
0x140039c2e  push    rbx
0x140039c2f  push    rsi
0x140039c30  push    rdi
0x140039c31  push    r12
0x140039c33  push    r13
0x140039c35  push    r14
0x140039c37  lea     rbp, [rsp-80h]
0x140039c3c  sub     rsp, 180h
0x140039c43  mov     rsi, rdx
0x140039c46  mov     rbx, rcx
0x140039c49  lea     r12, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x140039c50  mov     [rbp+0B0h+var_E0], r12
0x140039c54  lea     r13, aCvssregistryva_3; "CVssRegistryValueIterator::Attach"
0x140039c5b  mov     [rbp+0B0h+var_D8], r13
0x140039c5f  lea     rax, aRegregsc; "REGREGSC"
0x140039c66  mov     [rbp+0B0h+var_D0], rax
0x140039c6a  mov     [rbp+0B0h+var_C8], 48Ah
0x140039c71  mov     [rbp+0B0h+var_C4], 0Bh
0x140039c78  mov     [rbp+0B0h+var_C0], 0FFh
0x140039c7f  xor     r14d, r14d
0x140039c82  mov     [rbp+0B0h+var_40], 1000000h
0x140039c89  xor     edx, edx; Val
0x140039c8b  lea     r8d, [r14+78h]; Size
0x140039c8f  lea     rcx, [rbp+0B0h+pv]; void *
0x140039c93  call    memset_0
0x140039c98  mov     [rsp+1B0h+var_148], r14d
0x140039c9d  mov     rax, [rbp+0B0h+var_D8]
0x140039ca1  mov     [rbp+0B0h+var_128], rax
0x140039ca5  mov     rax, [rbp+0B0h+var_E0]
0x140039ca9  mov     [rsp+1B0h+var_140], rax
0x140039cae  mov     rax, [rbp+0B0h+var_D0]
0x140039cb2  mov     [rsp+1B0h+var_138], rax
0x140039cb7  mov     eax, [rbp+0B0h+var_C8]
0x140039cba  mov     [rbp+0B0h+var_130], eax
0x140039cbd  mov     eax, [rbp+0B0h+var_C4]
0x140039cc0  mov     [rbp+0B0h+var_12C], eax
0x140039cc3  call    cs:__imp_GetTickCount
0x140039cc9  mov     [rbp+0B0h+var_11C], eax
0x140039ccc  mov     [rsp+1B0h+var_14C], 0FFFFFFFFh
0x140039cd4  mov     eax, [rbp+0B0h+var_C0]
0x140039cd7  mov     [rbp+0B0h+var_118], eax
0x140039cda  mov     [rsp+1B0h+var_150], r14d
0x140039cdf  mov     [rbp+0B0h+var_F0], r14
0x140039ce3  xorps   xmm0, xmm0
0x140039ce6  movups  [rbp+0B0h+var_110], xmm0
0x140039cea  movups  [rbp+0B0h+var_100], xmm0
0x140039cee  mov     [rbp+0B0h+pExceptionObject], r14
0x140039cf5  lea     rcx, [rbp+0B0h+pExceptionObject]
0x140039cfc  call    cs:__imp_VssGetTracingContextPerThread
0x140039d02  test    eax, eax
0x140039d04  jns     loc_140039E63
0x140039d0a  mov     rcx, [rbp+0B0h+var_F0]
0x140039d0e  test    rcx, rcx
0x140039d11  jz      loc_140039E9C
0x140039d17  mov     eax, [rcx+30h]
0x140039d1a  inc     eax
0x140039d1c  mov     [rbp+0B0h+var_120], eax
0x140039d1f  mov     edi, 0A0h
0x140039d24  cmp     [rbp+0B0h+var_118], 0FFh
0x140039d2b  cmovnz  edi, [rbp+0B0h+var_118]
0x140039d2f  lea     rcx, [rsp+1B0h+var_150]; this
0x140039d34  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x140039d39  test    eax, eax
0x140039d3b  jnz     loc_140039F0F
0x140039d41  cmp     byte ptr [rbp+0B0h+var_40+3], r14b
0x140039d45  jz      short loc_140039D61
0x140039d47  mov     rdi, r14
0x140039d4a  mov     rcx, [rbp+rdi*8+0B0h+pv]; pv
0x140039d4f  test    rcx, rcx
0x140039d52  jnz     loc_140039E53
0x140039d58  inc     rdi
0x140039d5b  cmp     rdi, 0Fh
0x140039d5f  jnz     short loc_140039D4A
0x140039d61  mov     [rbx], r14
0x140039d64  mov     [rbx+8], r14
0x140039d68  mov     [rbx+28h], r14d
0x140039d6c  mov     rcx, [rbx+20h]; pv
0x140039d70  test    rcx, rcx
0x140039d73  jnz     loc_140039E85
0x140039d79  mov     [rbx+20h], r14
0x140039d7d  mov     [rbx+10h], r14d
0x140039d81  mov     [rbx+2Ch], r14d
0x140039d85  mov     [rbx+30h], r14w
0x140039d8a  mov     rcx, [rsi+8]; hKey
0x140039d8e  mov     [rbx], rcx
0x140039d91  mov     [rbp+0B0h+cValues], r14d
0x140039d98  mov     [rbp+0B0h+cbMaxValueNameLen], r14d
0x140039d9f  mov     [rsp+1B0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x140039da4  mov     [rsp+1B0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x140039da9  mov     [rsp+1B0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x140039dae  lea     rax, [rbp+0B0h+cbMaxValueNameLen]
0x140039db5  mov     [rsp+1B0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x140039dba  lea     rax, [rbp+0B0h+cValues]
0x140039dc1  mov     [rsp+1B0h+lpcValues], rax; lpcValues
0x140039dc6  mov     [rsp+1B0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x140039dcb  mov     [rsp+1B0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x140039dd0  mov     [rsp+1B0h+lpcSubKeys], r14; lpcSubKeys
0x140039dd5  xor     r9d, r9d; lpReserved
0x140039dd8  xor     r8d, r8d; lpcchClass
0x140039ddb  xor     edx, edx; lpClass
0x140039ddd  call    cs:__imp_RegQueryInfoKeyW
0x140039de3  mov     edi, eax
0x140039de5  test    eax, eax
0x140039de7  jnz     loc_140039EA5
0x140039ded  mov     edi, [rbp+0B0h+cbMaxValueNameLen]
0x140039df3  mov     rcx, [rbx+20h]; pv
0x140039df7  test    rcx, rcx
0x140039dfa  jnz     loc_140039E91
0x140039e00  mov     [rbx+20h], r14
0x140039e04  lea     rcx, ds:2[rdi*2]; cb
0x140039e0c  call    cs:__imp_CoTaskMemAlloc
0x140039e12  mov     [rbx+20h], rax
0x140039e16  test    rax, rax
0x140039e19  jz      loc_140039F51
0x140039e1f  mov     eax, [rbp+0B0h+cValues]
0x140039e25  mov     [rbx+8], eax
0x140039e28  mov     eax, [rbp+0B0h+cbMaxValueNameLen]
0x140039e2e  inc     eax
0x140039e30  mov     [rbx+28h], eax
0x140039e33  mov     byte ptr [rbx+31h], 1
0x140039e37  lea     rcx, [rsp+1B0h+var_150]; this
0x140039e3c  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140039e41  add     rsp, 180h
0x140039e48  pop     r14
0x140039e4a  pop     r13
0x140039e4c  pop     r12
0x140039e4e  pop     rdi
0x140039e4f  pop     rsi
0x140039e50  pop     rbx
0x140039e51  pop     rbp
0x140039e52  retn
0x140039e53  call    cs:__imp_CoTaskMemFree
0x140039e59  mov     [rbp+rdi*8+0B0h+pv], r14
0x140039e5e  jmp     loc_140039D58
0x140039e63  lea     rcx, [rsp+1B0h+var_150]
0x140039e68  call    cs:__imp_VssSetTracingContextPerThread
0x140039e6e  mov     rcx, [rbp+0B0h+var_F0]
0x140039e72  test    eax, eax
0x140039e74  cmovns  rcx, [rbp+0B0h+pExceptionObject]
0x140039e7c  mov     [rbp+0B0h+var_F0], rcx
0x140039e80  jmp     loc_140039D0E
0x140039e85  call    cs:__imp_CoTaskMemFree
0x140039e8b  nop
0x140039e8c  jmp     loc_140039D79
0x140039e91  call    cs:__imp_CoTaskMemFree
0x140039e97  jmp     loc_140039E00
0x140039e9c  mov     [rbp+0B0h+var_120], r14d
0x140039ea0  jmp     loc_140039D1F
0x140039ea5  mov     rbx, [rbx]
0x140039ea8  jle     short loc_140039EB3
0x140039eaa  movzx   edi, ax
0x140039ead  or      edi, 80070000h
0x140039eb3  mov     [rbp+0B0h+var_E0], r12
0x140039eb7  mov     [rbp+0B0h+var_D8], r13
0x140039ebb  lea     rax, aRegregsc; "REGREGSC"
0x140039ec2  mov     [rbp+0B0h+var_D0], rax
0x140039ec6  mov     [rbp+0B0h+var_C8], 4A2h
0x140039ecd  mov     [rbp+0B0h+var_C4], 0Bh
0x140039ed4  mov     [rbp+0B0h+var_C0], 0FFh
0x140039edb  mov     [rbp+0B0h+var_40], 1000000h
0x140039ee2  xor     edx, edx; Val
0x140039ee4  lea     r8d, [rdx+78h]; Size
0x140039ee8  lea     rcx, [rbp+0B0h+pv]; void *
0x140039eec  call    memset_0
0x140039ef1  mov     [rsp+1B0h+lpcSubKeys], rbx
0x140039ef6  lea     r9, aRegqueryinfoke; "RegQueryInfoKeyW(%p, ...)"
0x140039efd  mov     r8d, edi
0x140039f00  lea     rdx, [rbp+0B0h+var_E0]
0x140039f04  lea     rcx, [rsp+1B0h+var_150]
0x140039f09  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x140039f0f  mov     [rsp+1B0h+lpcbMaxValueNameLen], r14
0x140039f14  mov     dword ptr [rsp+1B0h+lpcValues], edi
0x140039f18  lea     rax, aEnter; "ENTER"
0x140039f1f  mov     [rsp+1B0h+lpcbMaxClassLen], rax
0x140039f24  mov     rax, [rbp+0B0h+var_128]
0x140039f28  mov     [rsp+1B0h+lpcbMaxSubKeyLen], rax
0x140039f2d  mov     eax, [rbp+0B0h+var_12C]
0x140039f30  mov     dword ptr [rsp+1B0h+lpcSubKeys], eax
0x140039f34  mov     r9d, [rbp+0B0h+var_120]
0x140039f38  mov     r8d, [rbp+0B0h+var_130]
0x140039f3c  mov     rdx, [rsp+1B0h+var_138]
0x140039f41  mov     rcx, [rsp+1B0h+var_140]
0x140039f46  call    cs:__imp_VssTraceMessage
0x140039f4c  jmp     loc_140039D41
0x140039f51  mov     dword ptr [rbp+0B0h+pExceptionObject], 8007000Eh
0x140039f5b  lea     rdx, _TI1J; pThrowInfo
0x140039f62  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x140039f69  call    _CxxThrowException_0
```
