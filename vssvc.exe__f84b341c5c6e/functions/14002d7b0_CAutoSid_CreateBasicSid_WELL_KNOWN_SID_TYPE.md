# CAutoSid::CreateBasicSid(WELL_KNOWN_SID_TYPE)

- ea: `0x14002d7b0`
- end: `0x14002dc88`
- name: `?CreateBasicSid@CAutoSid@@QEAAXW4WELL_KNOWN_SID_TYPE@@@Z`
- size: `1240`
- prototype: `void(CAutoSid *__hidden this, enum WELL_KNOWN_SID_TYPE)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14002b160`
- `0x140082290`
- `0x1400b3648`

## callees

- `0x140006020`
- `0x1400138e0`
- `0x140013c60`
- `0x140019e30`
- `0x14002d7b0`
- `0x140070fcc`
- `0x1400921dc`
- `0x1400921e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002db5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002db5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002d988`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002d988`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14002d94d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14002d94d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14002d91c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14002d971`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14002d91c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14002d971`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002d85d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002d9ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002d85d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002d9ca`
- `VssTrace!__imp_VssTraceMessage` at `0x14002dc0f`
- `VssTrace!__imp_VssTraceMessage` at `0x14002dc0f`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002da85`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002dabb`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002da85`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002dabb`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002d89c`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002d89c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002d996`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002d9a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002d9b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002d9c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002daa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002d996`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002d9a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002d9b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002d9c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002daa6`

## string_xrefs

- `0x14002d7d4`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002d7df`: `CAutoSid::CreateBasicSid`
- `0x14002d933`: `CAutoSid::CreateBasicSid`
- `0x14002daf7`: `CAutoSid::CreateBasicSid`
- `0x14002dc2a`: `CreateWellKnownSidType`
- `0x14002dc70`: `CreateWellKnownSidType`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CAutoSid::CreateBasicSid(CAutoSid *this, enum WELL_KNOWN_SID_TYPE a2)
{
  const unsigned __int16 **v4; // rax
  unsigned int v5; // r14d
  unsigned int v6; // ebx
  __int64 i; // rbx
  void *v8; // rcx
  signed int LastError; // eax
  signed int v10; // ebx
  HLOCAL v11; // rax
  HLOCAL v12; // rbx
  void *v13; // rcx
  DWORD v14; // esi
  signed int v15; // eax
  signed int v16; // edi
  CVssDebugInfo *v17; // rax
  CVssDebugInfo *v18; // rax
  __int64 v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+28h] [rbp-D8h]
  __int64 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  __int64 v23; // [rsp+40h] [rbp-C0h]
  _DWORD v24[2]; // [rsp+50h] [rbp-B0h] BYREF
  signed int v25; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v26; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v27; // [rsp+68h] [rbp-98h]
  unsigned int v28; // [rsp+70h] [rbp-90h]
  unsigned int v29; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v30; // [rsp+78h] [rbp-88h]
  unsigned int v31; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  unsigned int v33; // [rsp+88h] [rbp-78h]
  LPVOID pv[2]; // [rsp+90h] [rbp-70h]
  LPVOID v35[2]; // [rsp+A0h] [rbp-60h]
  const unsigned __int16 **v36; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v37; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v38; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v39; // [rsp+D0h] [rbp-30h]
  int v40; // [rsp+D8h] [rbp-28h]
  int v41; // [rsp+DCh] [rbp-24h]
  int v42; // [rsp+E0h] [rbp-20h]
  LPVOID v43[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v44; // [rsp+F8h] [rbp-8h]
  __int128 v45; // [rsp+108h] [rbp+8h]
  __int128 v46; // [rsp+118h] [rbp+18h]
  __int128 v47; // [rsp+128h] [rbp+28h]
  __int128 v48; // [rsp+138h] [rbp+38h]
  __int128 v49; // [rsp+148h] [rbp+48h]
  __int64 v50; // [rsp+158h] [rbp+58h]
  int v51; // [rsp+160h] [rbp+60h]
  void **v52; // [rsp+170h] [rbp+70h]
  HLOCAL v53; // [rsp+178h] [rbp+78h]
  _BYTE v54[224]; // [rsp+180h] [rbp+80h] BYREF
  DWORD cbSid; // [rsp+280h] [rbp+180h] BYREF
  const unsigned __int16 **pExceptionObject; // [rsp+288h] [rbp+188h] BYREF

  v37 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v38 = L"CAutoSid::CreateBasicSid";
  v39 = L"SECSECRC";
  v40 = 879;
  v41 = 11;
  v42 = 255;
  v51 = 0x1000000;
  *(_OWORD *)v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v25 = 0;
  v30 = L"CAutoSid::CreateBasicSid";
  v26 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v27 = L"SECSECRC";
  v28 = 879;
  v29 = 11;
  TickCount = GetTickCount();
  v24[1] = -1;
  v33 = 255;
  v24[0] = 0;
  v36 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v35 = 0;
  pExceptionObject = 0;
  if ( (int)VssGetTracingContextPerThread(&pExceptionObject) < 0 || (int)VssSetTracingContextPerThread(v24) < 0 )
  {
    v4 = v36;
  }
  else
  {
    v4 = pExceptionObject;
    v36 = pExceptionObject;
  }
  if ( v4 )
    v31 = *((_DWORD *)v4 + 12) + 1;
  else
    v31 = 0;
  v5 = 160;
  v6 = 160;
  if ( v33 != 255 )
    v6 = v33;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v24, v29) )
    VssTraceMessage(v26, v27, v28, v31, v29, v30, L"ENTER", v6, 0);
  for ( i = 0; i != 15; ++i )
  {
    v8 = v43[i];
    if ( v8 )
    {
      CoTaskMemFree(v8);
      v43[i] = 0;
    }
  }
  cbSid = 0;
  CreateWellKnownSid(a2, 0, 0, &cbSid);
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError != 122 )
  {
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    v25 = v10;
    v37 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v38 = L"CAutoSid::CreateBasicSid";
    v39 = L"SECSECRC";
    v40 = 892;
    v41 = 11;
    v42 = 255;
    v51 = 0x1000000;
    memset_0(v43, 0, 0x78u);
    pExceptionObject = &v37;
    if ( v10 < 0 )
    {
      v17 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v54, (const struct CVssDebugInfo *)&v37);
      CVssFunctionTracer::TranslateError(v24, v17, (unsigned int)v10, L"CreateWellKnownSidType");
    }
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v37);
  }
  v52 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  v11 = LocalAlloc(0, cbSid);
  v12 = v11;
  v53 = v11;
  if ( !v11 )
  {
    LODWORD(pExceptionObject) = -2147024882;
    throw (long *)&pExceptionObject;
  }
  if ( !CreateWellKnownSid(a2, 0, v11, &cbSid) )
  {
    v15 = GetLastError();
    v16 = v15;
    if ( v15 > 0 )
      v16 = (unsigned __int16)v15 | 0x80070000;
    v25 = v16;
    v37 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v38 = L"CAutoSid::CreateBasicSid";
    v39 = L"SECSECRC";
    v40 = 901;
    v41 = 11;
    v42 = 255;
    v51 = 0x1000000;
    memset_0(v43, 0, 0x78u);
    pExceptionObject = &v37;
    if ( v16 < 0 )
    {
      v18 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v54, (const struct CVssDebugInfo *)&v37);
      CVssFunctionTracer::TranslateError(v24, v18, (unsigned int)v16, L"CreateWellKnownSidType");
    }
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v37);
  }
  v13 = (void *)*((_QWORD *)this + 1);
  if ( v13 )
    LocalFree(v13);
  *((_QWORD *)this + 1) = v12;
  CoTaskMemFree(pv[0]);
  pv[0] = 0;
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v35[0]);
  v35[0] = 0;
  CoTaskMemFree(v35[1]);
  v35[1] = 0;
  v14 = GetTickCount() - TickCount;
  if ( v33 != 255 )
    v5 = v33;
  LODWORD(v23) = v14;
  LODWORD(v22) = v14 % 0x3E8;
  LODWORD(v21) = v14 / 0x3E8 % 0x3C;
  LODWORD(v20) = v14 / 0xEA60 % 0x3C;
  LODWORD(v19) = v14 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v24,
    L"EXIT",
    v5,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v19,
    v20,
    v21,
    v22,
    v23,
    v25);
  VssSetTracingContextPerThread(v36);
}

```

## disassembly

```asm
0x14002d7b0  mov     [rsp-8+arg_0], rbx
0x14002d7b5  push    rbp
0x14002d7b6  push    rsi
0x14002d7b7  push    rdi
0x14002d7b8  push    r12
0x14002d7ba  push    r13
0x14002d7bc  push    r14
0x14002d7be  push    r15
0x14002d7c0  lea     rbp, [rsp-130h]
0x14002d7c8  sub     rsp, 230h
0x14002d7cf  mov     edi, edx
0x14002d7d1  mov     rsi, rcx
0x14002d7d4  lea     r13, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x14002d7db  mov     [rbp+160h+var_1A0], r13
0x14002d7df  lea     rcx, aCautosidCreate; "CAutoSid::CreateBasicSid"
0x14002d7e6  mov     [rbp+160h+var_198], rcx
0x14002d7ea  lea     rdx, aSecsecrc; "SECSECRC"
0x14002d7f1  mov     [rbp+160h+var_190], rdx
0x14002d7f5  mov     [rbp+160h+var_188], 36Fh
0x14002d7fc  mov     [rbp+160h+var_184], 0Bh
0x14002d803  mov     [rbp+160h+var_180], 0FFh
0x14002d80a  xor     r15d, r15d
0x14002d80d  mov     [rbp+160h+var_100], 1000000h
0x14002d814  xorps   xmm0, xmm0
0x14002d817  xor     eax, eax
0x14002d819  movups  xmmword ptr [rbp+160h+var_178], xmm0
0x14002d81d  movups  [rbp+160h+var_168], xmm0
0x14002d821  movups  [rbp+160h+var_158], xmm0
0x14002d825  movups  [rbp+160h+var_148], xmm0
0x14002d829  movups  [rbp+160h+var_138], xmm0
0x14002d82d  movups  [rbp+160h+var_128], xmm0
0x14002d831  movups  [rbp+160h+var_118], xmm0
0x14002d835  mov     [rbp+160h+var_108], rax
0x14002d839  mov     [rsp+260h+var_208], r15d
0x14002d83e  mov     [rsp+260h+var_1E8], rcx
0x14002d843  mov     [rsp+260h+var_200], r13
0x14002d848  mov     [rsp+260h+var_1F8], rdx
0x14002d84d  mov     [rsp+260h+var_1F0], 36Fh
0x14002d855  mov     [rsp+260h+var_1EC], 0Bh
0x14002d85d  call    cs:__imp_GetTickCount
0x14002d863  mov     [rbp+160h+var_1DC], eax
0x14002d866  mov     [rsp+260h+var_20C], 0FFFFFFFFh
0x14002d86e  mov     [rbp+160h+var_1D8], 0FFh
0x14002d875  mov     [rsp+260h+var_210], r15d
0x14002d87a  mov     [rbp+160h+var_1B0], r15
0x14002d87e  xorps   xmm0, xmm0
0x14002d881  movdqa  xmmword ptr [rbp+160h+pv], xmm0
0x14002d886  xorps   xmm1, xmm1
0x14002d889  movdqa  xmmword ptr [rbp+160h+var_1C0], xmm1
0x14002d88e  mov     [rbp+160h+pExceptionObject], r15
0x14002d895  lea     rcx, [rbp+160h+pExceptionObject]
0x14002d89c  call    cs:__imp_VssGetTracingContextPerThread
0x14002d8a2  test    eax, eax
0x14002d8a4  jns     loc_14002DAB6
0x14002d8aa  mov     rax, [rbp+160h+var_1B0]
0x14002d8ae  test    rax, rax
0x14002d8b1  jz      loc_14002DAD9
0x14002d8b7  mov     eax, [rax+30h]
0x14002d8ba  inc     eax
0x14002d8bc  mov     [rbp+160h+var_1E0], eax
0x14002d8bf  mov     r14d, 0A0h
0x14002d8c5  mov     ebx, r14d
0x14002d8c8  cmp     [rbp+160h+var_1D8], 0FFh
0x14002d8cf  cmovnz  ebx, [rbp+160h+var_1D8]
0x14002d8d3  mov     edx, [rsp+260h+var_1EC]; unsigned int
0x14002d8d7  lea     rcx, [rsp+260h+var_210]; this
0x14002d8dc  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14002d8e1  test    eax, eax
0x14002d8e3  jnz     loc_14002DBD5
0x14002d8e9  mov     rbx, r15
0x14002d8ec  nop     dword ptr [rax+00h]
0x14002d8f0  mov     rcx, [rbp+rbx*8+160h+var_178]; pv
0x14002d8f5  test    rcx, rcx
0x14002d8f8  jnz     loc_14002DAA6
0x14002d8fe  inc     rbx
0x14002d901  cmp     rbx, 0Fh
0x14002d905  jnz     short loc_14002D8F0
0x14002d907  mov     [rbp+160h+cbSid], r15d
0x14002d90e  lea     r9, [rbp+160h+cbSid]; cbSid
0x14002d915  xor     r8d, r8d; pSid
0x14002d918  xor     edx, edx; DomainSid
0x14002d91a  mov     ecx, edi; WellKnownSidType
0x14002d91c  call    cs:__imp_CreateWellKnownSid
0x14002d922  call    cs:__imp_GetLastError
0x14002d928  mov     ebx, eax
0x14002d92a  cmp     eax, 7Ah ; 'z'
0x14002d92d  jnz     loc_14002DAE2
0x14002d933  lea     r12, aCautosidCreate; "CAutoSid::CreateBasicSid"
0x14002d93a  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x14002d941  mov     [rbp+160h+var_F0], rax
0x14002d945  mov     edx, [rbp+160h+cbSid]; uBytes
0x14002d94b  xor     ecx, ecx; uFlags
0x14002d94d  call    cs:__imp_LocalAlloc
0x14002d953  mov     rbx, rax
0x14002d956  mov     [rbp+160h+var_E8], rax
0x14002d95a  test    rax, rax
0x14002d95d  jz      loc_14002DC42
0x14002d963  lea     r9, [rbp+160h+cbSid]; cbSid
0x14002d96a  mov     r8, rax; pSid
0x14002d96d  xor     edx, edx; DomainSid
0x14002d96f  mov     ecx, edi; WellKnownSidType
0x14002d971  call    cs:__imp_CreateWellKnownSid
0x14002d977  test    eax, eax
0x14002d979  jz      loc_14002DB5B
0x14002d97f  mov     rcx, [rsi+8]; hMem
0x14002d983  test    rcx, rcx
0x14002d986  jz      short loc_14002D98E
0x14002d988  call    cs:__imp_LocalFree
0x14002d98e  mov     [rsi+8], rbx
0x14002d992  mov     rcx, [rbp+160h+pv]; pv
0x14002d996  call    cs:__imp_CoTaskMemFree
0x14002d99c  mov     [rbp+160h+pv], r15
0x14002d9a0  mov     rcx, [rbp+160h+pv+8]; pv
0x14002d9a4  call    cs:__imp_CoTaskMemFree
0x14002d9aa  mov     [rbp+160h+pv+8], r15
0x14002d9ae  mov     rcx, [rbp+160h+var_1C0]; pv
0x14002d9b2  call    cs:__imp_CoTaskMemFree
0x14002d9b8  mov     [rbp+160h+var_1C0], r15
0x14002d9bc  mov     rcx, [rbp+160h+var_1C0+8]; pv
0x14002d9c0  call    cs:__imp_CoTaskMemFree
0x14002d9c6  mov     [rbp+160h+var_1C0+8], r15
0x14002d9ca  call    cs:__imp_GetTickCount
0x14002d9d0  mov     esi, eax
0x14002d9d2  sub     esi, [rbp+160h+var_1DC]
0x14002d9d5  mov     eax, 10624DD3h
0x14002d9da  mul     esi
0x14002d9dc  mov     edi, edx
0x14002d9de  shr     edi, 6
0x14002d9e1  mov     eax, 88888889h
0x14002d9e6  mul     edi
0x14002d9e8  shr     edx, 5
0x14002d9eb  imul    ecx, edx, 3Ch ; '<'
0x14002d9ee  mov     ebx, edi
0x14002d9f0  sub     ebx, ecx
0x14002d9f2  mov     eax, 45E7B273h
0x14002d9f7  mul     esi
0x14002d9f9  mov     r11d, edx
0x14002d9fc  shr     r11d, 0Eh
0x14002da00  mov     eax, 88888889h
0x14002da05  mul     r11d
0x14002da08  shr     edx, 5
0x14002da0b  imul    ecx, edx, 3Ch ; '<'
0x14002da0e  sub     r11d, ecx
0x14002da11  mov     eax, 95217CB1h
0x14002da16  mul     esi
0x14002da18  mov     r10d, edx
0x14002da1b  shr     r10d, 15h
0x14002da1f  mov     eax, 88888889h
0x14002da24  mul     r10d
0x14002da27  shr     edx, 5
0x14002da2a  imul    eax, edx, 3Ch ; '<'
0x14002da2d  sub     r10d, eax
0x14002da30  mov     r9d, [rsp+260h+var_208]
0x14002da35  cmp     [rbp+160h+var_1D8], 0FFh
0x14002da3c  cmovnz  r14d, [rbp+160h+var_1D8]
0x14002da41  imul    eax, edi, 3E8h
0x14002da47  mov     ecx, esi
0x14002da49  sub     ecx, eax
0x14002da4b  mov     [rsp+260h+var_218], r9d
0x14002da50  mov     dword ptr [rsp+260h+var_220], esi
0x14002da54  mov     dword ptr [rsp+260h+var_228], ecx
0x14002da58  mov     dword ptr [rsp+260h+var_230], ebx
0x14002da5c  mov     dword ptr [rsp+260h+var_238], r11d
0x14002da61  mov     dword ptr [rsp+260h+var_240], r10d
0x14002da66  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x14002da6d  mov     r8d, r14d; unsigned int
0x14002da70  lea     rdx, aExit; "EXIT"
0x14002da77  lea     rcx, [rsp+260h+var_210]; this
0x14002da7c  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x14002da81  mov     rcx, [rbp+160h+var_1B0]
0x14002da85  call    cs:__imp_VssSetTracingContextPerThread
0x14002da8b  mov     rbx, [rsp+260h+arg_0]
0x14002da93  add     rsp, 230h
0x14002da9a  pop     r15
0x14002da9c  pop     r14
0x14002da9e  pop     r13
0x14002daa0  pop     r12
0x14002daa2  pop     rdi
0x14002daa3  pop     rsi
0x14002daa4  pop     rbp
0x14002daa5  retn
0x14002daa6  call    cs:__imp_CoTaskMemFree
0x14002daac  mov     [rbp+rbx*8+160h+var_178], r15
0x14002dab1  jmp     loc_14002D8FE
0x14002dab6  lea     rcx, [rsp+260h+var_210]
0x14002dabb  call    cs:__imp_VssSetTracingContextPerThread
0x14002dac1  test    eax, eax
0x14002dac3  js      loc_14002D8AA
0x14002dac9  mov     rax, [rbp+160h+pExceptionObject]
0x14002dad0  mov     [rbp+160h+var_1B0], rax
0x14002dad4  jmp     loc_14002D8AE
0x14002dad9  mov     [rbp+160h+var_1E0], r15d
0x14002dadd  jmp     loc_14002D8BF
0x14002dae2  test    eax, eax
0x14002dae4  jle     short loc_14002DAEF
0x14002dae6  movzx   ebx, ax
0x14002dae9  or      ebx, 80070000h
0x14002daef  mov     [rsp+260h+var_208], ebx
0x14002daf3  mov     [rbp+160h+var_1A0], r13
0x14002daf7  lea     r12, aCautosidCreate; "CAutoSid::CreateBasicSid"
0x14002dafe  mov     [rbp+160h+var_198], r12
0x14002db02  lea     rax, aSecsecrc; "SECSECRC"
0x14002db09  mov     [rbp+160h+var_190], rax
0x14002db0d  mov     [rbp+160h+var_188], 37Ch
0x14002db14  mov     [rbp+160h+var_184], 0Bh
0x14002db1b  mov     [rbp+160h+var_180], 0FFh
0x14002db22  mov     [rbp+160h+var_100], 1000000h
0x14002db29  xor     edx, edx; Val
0x14002db2b  mov     r8d, 78h ; 'x'; Size
0x14002db31  lea     rcx, [rbp+160h+var_178]; void *
0x14002db35  call    memset_0
0x14002db3a  lea     rax, [rbp+160h+var_1A0]
0x14002db3e  mov     [rbp+160h+pExceptionObject], rax
0x14002db45  test    ebx, ebx
0x14002db47  js      loc_14002DC1A
0x14002db4d  lea     rcx, [rbp+160h+var_1A0]; this
0x14002db51  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14002db56  jmp     loc_14002D93A
0x14002db5b  call    cs:__imp_GetLastError
0x14002db61  mov     edi, eax
0x14002db63  test    eax, eax
0x14002db65  jle     short loc_14002DB70
0x14002db67  movzx   edi, ax
0x14002db6a  or      edi, 80070000h
0x14002db70  mov     [rsp+260h+var_208], edi
0x14002db74  mov     [rbp+160h+var_1A0], r13
0x14002db78  mov     [rbp+160h+var_198], r12
0x14002db7c  lea     rax, aSecsecrc; "SECSECRC"
0x14002db83  mov     [rbp+160h+var_190], rax
0x14002db87  mov     [rbp+160h+var_188], 385h
0x14002db8e  mov     [rbp+160h+var_184], 0Bh
0x14002db95  mov     [rbp+160h+var_180], 0FFh
0x14002db9c  mov     [rbp+160h+var_100], 1000000h
0x14002dba3  xor     edx, edx; Val
0x14002dba5  mov     r8d, 78h ; 'x'; Size
0x14002dbab  lea     rcx, [rbp+160h+var_178]; void *
0x14002dbaf  call    memset_0
0x14002dbb4  lea     rax, [rbp+160h+var_1A0]
0x14002dbb8  mov     [rbp+160h+pExceptionObject], rax
0x14002dbbf  test    edi, edi
0x14002dbc1  js      loc_14002DC60
0x14002dbc7  lea     rcx, [rbp+160h+var_1A0]; this
0x14002dbcb  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14002dbd0  jmp     loc_14002D97F
0x14002dbd5  mov     [rsp+260h+var_220], r15
0x14002dbda  mov     dword ptr [rsp+260h+var_228], ebx
0x14002dbde  lea     rax, aEnter; "ENTER"
0x14002dbe5  mov     [rsp+260h+var_230], rax
0x14002dbea  mov     rax, [rsp+260h+var_1E8]
0x14002dbef  mov     [rsp+260h+var_238], rax
0x14002dbf4  mov     eax, [rsp+260h+var_1EC]
0x14002dbf8  mov     dword ptr [rsp+260h+var_240], eax
0x14002dbfc  mov     r9d, [rbp+160h+var_1E0]
0x14002dc00  mov     r8d, [rsp+260h+var_1F0]
0x14002dc05  mov     rdx, [rsp+260h+var_1F8]
0x14002dc0a  mov     rcx, [rsp+260h+var_200]
0x14002dc0f  call    cs:__imp_VssTraceMessage
0x14002dc15  jmp     loc_14002D8E9
0x14002dc1a  lea     rdx, [rbp+160h+var_1A0]; struct CVssDebugInfo *
0x14002dc1e  lea     rcx, [rbp+160h+var_E0]; this
0x14002dc25  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x14002dc2a  lea     r9, aCreatewellknow_0; "CreateWellKnownSidType"
0x14002dc31  mov     r8d, ebx
0x14002dc34  mov     rdx, rax
0x14002dc37  lea     rcx, [rsp+260h+var_210]
0x14002dc3c  call    ?TranslateError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBG@Z; CVssFunctionTracer::TranslateError(CVssDebugInfo,long,ushort const *)
0x14002dc42  mov     dword ptr [rbp+160h+pExceptionObject], 8007000Eh
0x14002dc4c  lea     rdx, _TI1J; pThrowInfo
0x14002dc53  lea     rcx, [rbp+160h+pExceptionObject]; pExceptionObject
0x14002dc5a  call    _CxxThrowException_0
0x14002dc60  lea     rdx, [rbp+160h+var_1A0]; struct CVssDebugInfo *
0x14002dc64  lea     rcx, [rbp+160h+var_E0]; this
0x14002dc6b  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x14002dc70  lea     r9, aCreatewellknow_0; "CreateWellKnownSidType"
0x14002dc77  mov     r8d, edi
0x14002dc7a  mov     rdx, rax
0x14002dc7d  lea     rcx, [rsp+260h+var_210]
0x14002dc82  call    ?TranslateError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBG@Z; CVssFunctionTracer::TranslateError(CVssDebugInfo,long,ushort const *)
```
