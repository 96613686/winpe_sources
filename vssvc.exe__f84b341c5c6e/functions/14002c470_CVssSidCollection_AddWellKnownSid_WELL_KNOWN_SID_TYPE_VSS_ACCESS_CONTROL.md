# CVssSidCollection::AddWellKnownSid(WELL_KNOWN_SID_TYPE,VSS_ACCESS_CONTROL)

- ea: `0x14002c470`
- end: `0x14002c9df`
- name: `?AddWellKnownSid@CVssSidCollection@@AEAAXW4WELL_KNOWN_SID_TYPE@@W4VSS_ACCESS_CONTROL@@@Z`
- size: `1391`
- prototype: `void __high(enum WELL_KNOWN_SID_TYPE, enum VSS_ACCESS_CONTROL)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14002b160`

## callees

- `0x1400138e0`
- `0x1400139c0`
- `0x140013c60`
- `0x140028b48`
- `0x14002c470`
- `0x14002c9f0`
- `0x1400921dc`
- `0x1400921e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c5f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c5f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002c6ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002c6ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14002c610`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14002c610`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14002c5eb`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14002c634`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14002c5eb`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14002c634`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002c51d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002c72c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002c51d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002c72c`
- `VssTrace!__imp_VssTraceMessage` at `0x14002c875`
- `VssTrace!__imp_VssTraceMessage` at `0x14002c875`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002c7e5`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002c813`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002c7e5`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002c813`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002c556`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002c556`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002c6f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002c706`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002c714`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002c722`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002c7ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002c6f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002c706`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002c714`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002c722`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002c7ff`

## string_xrefs

- `0x14002c494`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002c65b`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002c880`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002c8ea`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002c96e`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002c4a0`: `CVssSidCollection::AddWellKnownSid`
- `0x14002c667`: `CVssSidCollection::AddWellKnownSid`
- `0x14002c88c`: `CVssSidCollection::AddWellKnownSid`
- `0x14002c8f6`: `CVssSidCollection::AddWellKnownSid`
- `0x14002c97a`: `CVssSidCollection::AddWellKnownSid`
- `0x14002c6c3`: `Set m_pSidAdmin`
- `0x14002c8d4`: `CreateWellKnownSid(type, NULL, NULL, &dwSid)`
- `0x14002c93e`: `CreateWellKnownSid(type, NULL, NULL, &dwSid)`
- `0x14002c9c9`: `CreateWellKnownSid(type, NULL, pSid, [%ld])`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVssSidCollection::AddWellKnownSid(__int64 a1, WELL_KNOWN_SID_TYPE a2, int a3)
{
  __int64 v6; // rax
  unsigned int v7; // r14d
  unsigned int v8; // ebx
  __int64 i; // rbx
  void *v10; // rcx
  HLOCAL v11; // rax
  void *v12; // rbx
  void *v13; // rax
  void *v14; // rax
  DWORD v15; // esi
  __int64 v17; // [rsp+20h] [rbp-E0h]
  __int64 v18; // [rsp+28h] [rbp-D8h]
  __int64 v19; // [rsp+30h] [rbp-D0h]
  __int64 v20; // [rsp+38h] [rbp-C8h]
  __int64 v21; // [rsp+40h] [rbp-C0h]
  __int64 pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v23; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v24; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v25; // [rsp+68h] [rbp-98h]
  int v26; // [rsp+70h] [rbp-90h]
  int v27; // [rsp+74h] [rbp-8Ch]
  int v28; // [rsp+78h] [rbp-88h]
  LPVOID v29[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v30; // [rsp+90h] [rbp-70h]
  __int128 v31; // [rsp+A0h] [rbp-60h]
  __int128 v32; // [rsp+B0h] [rbp-50h]
  __int128 v33; // [rsp+C0h] [rbp-40h]
  __int128 v34; // [rsp+D0h] [rbp-30h]
  __int128 v35; // [rsp+E0h] [rbp-20h]
  __int64 v36; // [rsp+F0h] [rbp-10h]
  int v37; // [rsp+F8h] [rbp-8h]
  _DWORD v38[2]; // [rsp+100h] [rbp+0h] BYREF
  int v39; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v40; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v41; // [rsp+118h] [rbp+18h]
  unsigned int v42; // [rsp+120h] [rbp+20h]
  unsigned int v43; // [rsp+124h] [rbp+24h]
  const wchar_t *v44; // [rsp+128h] [rbp+28h]
  unsigned int v45; // [rsp+130h] [rbp+30h]
  DWORD TickCount; // [rsp+134h] [rbp+34h]
  unsigned int v47; // [rsp+138h] [rbp+38h]
  LPVOID pv[2]; // [rsp+140h] [rbp+40h]
  LPVOID v49[2]; // [rsp+150h] [rbp+50h]
  __int64 v50; // [rsp+160h] [rbp+60h]
  void **v51; // [rsp+170h] [rbp+70h]
  HLOCAL v52; // [rsp+178h] [rbp+78h]
  DWORD cbSid; // [rsp+1E8h] [rbp+E8h] BYREF

  v23 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v24 = L"CVssSidCollection::AddWellKnownSid";
  v25 = L"SECSECRC";
  v26 = 1348;
  v27 = 11;
  v28 = 255;
  v37 = 0x1000000;
  *(_OWORD *)v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v39 = 0;
  v44 = L"CVssSidCollection::AddWellKnownSid";
  v40 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v41 = L"SECSECRC";
  v42 = 1348;
  v43 = 11;
  TickCount = GetTickCount();
  v38[1] = -1;
  v47 = 255;
  v38[0] = 0;
  v50 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v49 = 0;
  pExceptionObject = 0;
  if ( (int)VssGetTracingContextPerThread(&pExceptionObject) < 0 || (int)VssSetTracingContextPerThread(v38) < 0 )
  {
    v6 = v50;
  }
  else
  {
    v6 = pExceptionObject;
    v50 = pExceptionObject;
  }
  if ( v6 )
    v45 = *(_DWORD *)(v6 + 48) + 1;
  else
    v45 = 0;
  v7 = 160;
  v8 = 160;
  if ( v47 != 255 )
    v8 = v47;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v38, v43) )
    VssTraceMessage(v40, v41, v42, v45, v43, v44, L"ENTER", v8, 0);
  for ( i = 0; i != 15; ++i )
  {
    v10 = v29[i];
    if ( v10 )
    {
      CoTaskMemFree(v10);
      v29[i] = 0;
    }
  }
  v52 = 0;
  v51 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  cbSid = 0;
  if ( CreateWellKnownSid(a2, 0, 0, &cbSid) )
  {
    v23 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v24 = L"CVssSidCollection::AddWellKnownSid";
    v25 = L"SECSECRC";
    v26 = 1358;
    v27 = 11;
    v28 = 255;
    v37 = 0x1000000;
    memset_0(v29, 0, 0x78u);
    CVssFunctionTracer::TranslateWin32Error(v38, &v23, L"CreateWellKnownSid(type, NULL, NULL, &dwSid)");
  }
  if ( GetLastError() != 122 )
  {
    v23 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v24 = L"CVssSidCollection::AddWellKnownSid";
    v25 = L"SECSECRC";
    v26 = 1361;
    v27 = 11;
    v28 = 255;
    v37 = 0x1000000;
    memset_0(v29, 0, 0x78u);
    CVssFunctionTracer::TranslateWin32Error(v38, &v23, L"CreateWellKnownSid(type, NULL, NULL, &dwSid)");
  }
  v11 = LocalAlloc(0, cbSid);
  v12 = v11;
  v52 = v11;
  if ( !v11 )
  {
    LODWORD(pExceptionObject) = -2147024882;
    throw (long *)&pExceptionObject;
  }
  if ( !CreateWellKnownSid(a2, 0, v11, &cbSid) )
  {
    v23 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v24 = L"CVssSidCollection::AddWellKnownSid";
    v25 = L"SECSECRC";
    v26 = 1370;
    v27 = 11;
    v28 = 255;
    v37 = 0x1000000;
    memset_0(v29, 0, 0x78u);
    CVssFunctionTracer::TranslateWin32Error(v38, &v23, L"CreateWellKnownSid(type, NULL, pSid, [%ld])", cbSid);
  }
  CVssSidCollection::AddSid(a1, v12, a3);
  if ( *(_QWORD *)(a1 + 104) )
  {
    v14 = v12;
  }
  else
  {
    v23 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v24 = L"CVssSidCollection::AddWellKnownSid";
    v25 = L"SECSECRC";
    v26 = 1376;
    v27 = 11;
    v28 = 255;
    v37 = 0x1000000;
    *(_OWORD *)v29 = 0;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    CVssFunctionTracer::Trace(v38, &v23, L"Set m_pSidAdmin");
    v13 = v12;
    v12 = 0;
    *(_QWORD *)(a1 + 104) = v13;
    v14 = 0;
  }
  if ( v14 )
    LocalFree(v12);
  CoTaskMemFree(pv[0]);
  pv[0] = 0;
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v49[0]);
  v49[0] = 0;
  CoTaskMemFree(v49[1]);
  v49[1] = 0;
  v15 = GetTickCount() - TickCount;
  if ( v47 != 255 )
    v7 = v47;
  LODWORD(v21) = v15;
  LODWORD(v20) = v15 % 0x3E8;
  LODWORD(v19) = v15 / 0x3E8 % 0x3C;
  LODWORD(v18) = v15 / 0xEA60 % 0x3C;
  LODWORD(v17) = v15 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v38,
    L"EXIT",
    v7,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v17,
    v18,
    v19,
    v20,
    v21,
    v39);
  return VssSetTracingContextPerThread(v50);
}

```

## disassembly

```asm
0x14002c470  push    rbp
0x14002c472  push    rbx
0x14002c473  push    rsi
0x14002c474  push    rdi
0x14002c475  push    r12
0x14002c477  push    r13
0x14002c479  push    r14
0x14002c47b  push    r15
0x14002c47d  lea     rbp, [rsp-88h]
0x14002c485  sub     rsp, 188h
0x14002c48c  mov     r15d, r8d
0x14002c48f  mov     esi, edx
0x14002c491  mov     rdi, rcx
0x14002c494  lea     rcx, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x14002c49b  mov     [rsp+1C0h+var_168], rcx
0x14002c4a0  lea     rdx, aCvsssidcollect; "CVssSidCollection::AddWellKnownSid"
0x14002c4a7  mov     [rsp+1C0h+var_160], rdx
0x14002c4ac  lea     r8, aSecsecrc; "SECSECRC"
0x14002c4b3  mov     [rsp+1C0h+var_158], r8
0x14002c4b8  mov     [rsp+1C0h+var_150], 544h
0x14002c4c0  mov     [rsp+1C0h+var_14C], 0Bh
0x14002c4c8  mov     [rsp+1C0h+var_148], 0FFh
0x14002c4d0  xor     r12d, r12d
0x14002c4d3  mov     [rbp+0C0h+var_C8], 1000000h
0x14002c4da  xorps   xmm0, xmm0
0x14002c4dd  xor     eax, eax
0x14002c4df  movups  xmmword ptr [rbp+0C0h+var_140], xmm0
0x14002c4e3  movups  [rbp+0C0h+var_130], xmm0
0x14002c4e7  movups  [rbp+0C0h+var_120], xmm0
0x14002c4eb  movups  [rbp+0C0h+var_110], xmm0
0x14002c4ef  movups  [rbp+0C0h+var_100], xmm0
0x14002c4f3  movups  [rbp+0C0h+var_F0], xmm0
0x14002c4f7  movups  [rbp+0C0h+var_E0], xmm0
0x14002c4fb  mov     [rbp+0C0h+var_D0], rax
0x14002c4ff  mov     [rbp+0C0h+var_B8], r12d
0x14002c503  mov     [rbp+0C0h+var_98], rdx
0x14002c507  mov     [rbp+0C0h+var_B0], rcx
0x14002c50b  mov     [rbp+0C0h+var_A8], r8
0x14002c50f  mov     [rbp+0C0h+var_A0], 544h
0x14002c516  mov     [rbp+0C0h+var_9C], 0Bh
0x14002c51d  call    cs:__imp_GetTickCount
0x14002c523  mov     [rbp+0C0h+var_8C], eax
0x14002c526  mov     [rbp+0C0h+var_BC], 0FFFFFFFFh
0x14002c52d  mov     [rbp+0C0h+var_88], 0FFh
0x14002c534  mov     [rbp+0C0h+var_C0], r12d
0x14002c538  mov     [rbp+0C0h+var_60], r12
0x14002c53c  xorps   xmm0, xmm0
0x14002c53f  movdqa  xmmword ptr [rbp+0C0h+pv], xmm0
0x14002c544  xorps   xmm1, xmm1
0x14002c547  movdqa  xmmword ptr [rbp+0C0h+var_70], xmm1
0x14002c54c  mov     [rsp+1C0h+pExceptionObject], r12
0x14002c551  lea     rcx, [rsp+1C0h+pExceptionObject]
0x14002c556  call    cs:__imp_VssGetTracingContextPerThread
0x14002c55c  test    eax, eax
0x14002c55e  jns     loc_14002C80F
0x14002c564  mov     rax, [rbp+0C0h+var_60]
0x14002c568  test    rax, rax
0x14002c56b  jz      loc_14002C837
0x14002c571  mov     eax, [rax+30h]
0x14002c574  inc     eax
0x14002c576  mov     [rbp+0C0h+var_90], eax
0x14002c579  mov     r14d, 0A0h
0x14002c57f  mov     ebx, r14d
0x14002c582  cmp     [rbp+0C0h+var_88], 0FFh
0x14002c589  cmovnz  ebx, [rbp+0C0h+var_88]
0x14002c58d  mov     edx, [rbp+0C0h+var_9C]; unsigned int
0x14002c590  lea     rcx, [rbp+0C0h+var_C0]; this
0x14002c594  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14002c599  test    eax, eax
0x14002c59b  jnz     loc_14002C840
0x14002c5a1  mov     rbx, r12
0x14002c5a4  nop     dword ptr [rax+00h]
0x14002c5a8  nop     dword ptr [rax+rax+00000000h]
0x14002c5b0  mov     rcx, [rbp+rbx*8+0C0h+var_140]; pv
0x14002c5b5  test    rcx, rcx
0x14002c5b8  jnz     loc_14002C7FF
0x14002c5be  inc     rbx
0x14002c5c1  cmp     rbx, 0Fh
0x14002c5c5  jnz     short loc_14002C5B0
0x14002c5c7  mov     [rbp+0C0h+var_48], r12
0x14002c5cb  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x14002c5d2  mov     [rbp+0C0h+var_50], rax
0x14002c5d6  mov     [rbp+0C0h+cbSid], r12d
0x14002c5dd  lea     r9, [rbp+0C0h+cbSid]; cbSid
0x14002c5e4  xor     r8d, r8d; pSid
0x14002c5e7  xor     edx, edx; DomainSid
0x14002c5e9  mov     ecx, esi; WellKnownSidType
0x14002c5eb  call    cs:__imp_CreateWellKnownSid
0x14002c5f1  test    eax, eax
0x14002c5f3  jnz     loc_14002C880
0x14002c5f9  call    cs:__imp_GetLastError
0x14002c5ff  cmp     eax, 7Ah ; 'z'
0x14002c602  jnz     loc_14002C8EA
0x14002c608  mov     edx, [rbp+0C0h+cbSid]; uBytes
0x14002c60e  xor     ecx, ecx; uFlags
0x14002c610  call    cs:__imp_LocalAlloc
0x14002c616  mov     rbx, rax
0x14002c619  mov     [rbp+0C0h+var_48], rax
0x14002c61d  test    rax, rax
0x14002c620  jz      loc_14002C954
0x14002c626  lea     r9, [rbp+0C0h+cbSid]; cbSid
0x14002c62d  mov     r8, rax; pSid
0x14002c630  xor     edx, edx; DomainSid
0x14002c632  mov     ecx, esi; WellKnownSidType
0x14002c634  call    cs:__imp_CreateWellKnownSid
0x14002c63a  test    eax, eax
0x14002c63c  jz      loc_14002C96E
0x14002c642  mov     r8d, r15d
0x14002c645  mov     rdx, rbx
0x14002c648  mov     rcx, rdi
0x14002c64b  call    ?AddSid@CVssSidCollection@@AEAAXPEAXW4VSS_ACCESS_CONTROL@@@Z; CVssSidCollection::AddSid(void *,VSS_ACCESS_CONTROL)
0x14002c650  cmp     qword ptr [rdi+68h], 0
0x14002c655  jnz     loc_14002C82F
0x14002c65b  lea     rax, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x14002c662  mov     [rsp+1C0h+var_168], rax
0x14002c667  lea     rax, aCvsssidcollect; "CVssSidCollection::AddWellKnownSid"
0x14002c66e  mov     [rsp+1C0h+var_160], rax
0x14002c673  lea     rax, aSecsecrc; "SECSECRC"
0x14002c67a  mov     [rsp+1C0h+var_158], rax
0x14002c67f  mov     [rsp+1C0h+var_150], 560h
0x14002c687  mov     [rsp+1C0h+var_14C], 0Bh
0x14002c68f  mov     [rsp+1C0h+var_148], 0FFh
0x14002c697  mov     [rbp+0C0h+var_C8], 1000000h
0x14002c69e  xorps   xmm0, xmm0
0x14002c6a1  xor     eax, eax
0x14002c6a3  movups  xmmword ptr [rbp+0C0h+var_140], xmm0
0x14002c6a7  movups  [rbp+0C0h+var_130], xmm0
0x14002c6ab  movups  [rbp+0C0h+var_120], xmm0
0x14002c6af  movups  [rbp+0C0h+var_110], xmm0
0x14002c6b3  movups  [rbp+0C0h+var_100], xmm0
0x14002c6b7  movups  [rbp+0C0h+var_F0], xmm0
0x14002c6bb  movups  [rbp+0C0h+var_E0], xmm0
0x14002c6bf  mov     [rbp+0C0h+var_D0], rax
0x14002c6c3  lea     r8, aSetMPsidadmin; "Set m_pSidAdmin"
0x14002c6ca  lea     rdx, [rsp+1C0h+var_168]
0x14002c6cf  lea     rcx, [rbp+0C0h+var_C0]
0x14002c6d3  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14002c6d8  mov     rax, rbx
0x14002c6db  mov     rbx, r12
0x14002c6de  mov     [rdi+68h], rax
0x14002c6e2  mov     rax, r12
0x14002c6e5  test    rax, rax
0x14002c6e8  jz      short loc_14002C6F4
0x14002c6ea  mov     rcx, rbx; hMem
0x14002c6ed  call    cs:__imp_LocalFree
0x14002c6f3  nop
0x14002c6f4  mov     rcx, [rbp+0C0h+pv]; pv
0x14002c6f8  call    cs:__imp_CoTaskMemFree
0x14002c6fe  mov     [rbp+0C0h+pv], r12
0x14002c702  mov     rcx, [rbp+0C0h+pv+8]; pv
0x14002c706  call    cs:__imp_CoTaskMemFree
0x14002c70c  mov     [rbp+0C0h+pv+8], r12
0x14002c710  mov     rcx, [rbp+0C0h+var_70]; pv
0x14002c714  call    cs:__imp_CoTaskMemFree
0x14002c71a  mov     [rbp+0C0h+var_70], r12
0x14002c71e  mov     rcx, [rbp+0C0h+var_70+8]; pv
0x14002c722  call    cs:__imp_CoTaskMemFree
0x14002c728  mov     [rbp+0C0h+var_70+8], r12
0x14002c72c  call    cs:__imp_GetTickCount
0x14002c732  mov     esi, eax
0x14002c734  sub     esi, [rbp+0C0h+var_8C]
0x14002c737  mov     eax, 10624DD3h
0x14002c73c  mul     esi
0x14002c73e  mov     edi, edx
0x14002c740  shr     edi, 6
0x14002c743  mov     eax, 88888889h
0x14002c748  mul     edi
0x14002c74a  shr     edx, 5
0x14002c74d  imul    ecx, edx, 3Ch ; '<'
0x14002c750  mov     ebx, edi
0x14002c752  sub     ebx, ecx
0x14002c754  mov     eax, 45E7B273h
0x14002c759  mul     esi
0x14002c75b  mov     r11d, edx
0x14002c75e  shr     r11d, 0Eh
0x14002c762  mov     eax, 88888889h
0x14002c767  mul     r11d
0x14002c76a  shr     edx, 5
0x14002c76d  imul    ecx, edx, 3Ch ; '<'
0x14002c770  sub     r11d, ecx
0x14002c773  mov     eax, 95217CB1h
0x14002c778  mul     esi
0x14002c77a  mov     r10d, edx
0x14002c77d  shr     r10d, 15h
0x14002c781  mov     eax, 88888889h
0x14002c786  mul     r10d
0x14002c789  shr     edx, 5
0x14002c78c  imul    eax, edx, 3Ch ; '<'
0x14002c78f  sub     r10d, eax
0x14002c792  mov     r9d, [rbp+0C0h+var_B8]
0x14002c796  cmp     [rbp+0C0h+var_88], 0FFh
0x14002c79d  cmovnz  r14d, [rbp+0C0h+var_88]
0x14002c7a2  imul    eax, edi, 3E8h
0x14002c7a8  mov     ecx, esi
0x14002c7aa  sub     ecx, eax
0x14002c7ac  mov     [rsp+1C0h+var_178], r9d
0x14002c7b1  mov     dword ptr [rsp+1C0h+var_180], esi
0x14002c7b5  mov     dword ptr [rsp+1C0h+var_188], ecx
0x14002c7b9  mov     dword ptr [rsp+1C0h+var_190], ebx
0x14002c7bd  mov     dword ptr [rsp+1C0h+var_198], r11d
0x14002c7c2  mov     dword ptr [rsp+1C0h+var_1A0], r10d
0x14002c7c7  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x14002c7ce  mov     r8d, r14d; unsigned int
0x14002c7d1  lea     rdx, aExit; "EXIT"
0x14002c7d8  lea     rcx, [rbp+0C0h+var_C0]; this
0x14002c7dc  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x14002c7e1  mov     rcx, [rbp+0C0h+var_60]
0x14002c7e5  call    cs:__imp_VssSetTracingContextPerThread
0x14002c7eb  add     rsp, 188h
0x14002c7f2  pop     r15
0x14002c7f4  pop     r14
0x14002c7f6  pop     r13
0x14002c7f8  pop     r12
0x14002c7fa  pop     rdi
0x14002c7fb  pop     rsi
0x14002c7fc  pop     rbx
0x14002c7fd  pop     rbp
0x14002c7fe  retn
0x14002c7ff  call    cs:__imp_CoTaskMemFree
0x14002c805  mov     [rbp+rbx*8+0C0h+var_140], r12
0x14002c80a  jmp     loc_14002C5BE
0x14002c80f  lea     rcx, [rbp+0C0h+var_C0]
0x14002c813  call    cs:__imp_VssSetTracingContextPerThread
0x14002c819  test    eax, eax
0x14002c81b  js      loc_14002C564
0x14002c821  mov     rax, [rsp+1C0h+pExceptionObject]
0x14002c826  mov     [rbp+0C0h+var_60], rax
0x14002c82a  jmp     loc_14002C568
0x14002c82f  mov     rax, rbx
0x14002c832  jmp     loc_14002C6E5
0x14002c837  mov     [rbp+0C0h+var_90], r12d
0x14002c83b  jmp     loc_14002C579
0x14002c840  mov     [rsp+1C0h+var_180], r12
0x14002c845  mov     dword ptr [rsp+1C0h+var_188], ebx
0x14002c849  lea     rax, aEnter; "ENTER"
0x14002c850  mov     [rsp+1C0h+var_190], rax
0x14002c855  mov     rax, [rbp+0C0h+var_98]
0x14002c859  mov     [rsp+1C0h+var_198], rax
0x14002c85e  mov     eax, [rbp+0C0h+var_9C]
0x14002c861  mov     dword ptr [rsp+1C0h+var_1A0], eax
0x14002c865  mov     r9d, [rbp+0C0h+var_90]
0x14002c869  mov     r8d, [rbp+0C0h+var_A0]
0x14002c86d  mov     rdx, [rbp+0C0h+var_A8]
0x14002c871  mov     rcx, [rbp+0C0h+var_B0]
0x14002c875  call    cs:__imp_VssTraceMessage
0x14002c87b  jmp     loc_14002C5A1
0x14002c880  lea     rax, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x14002c887  mov     [rsp+1C0h+var_168], rax
0x14002c88c  lea     rax, aCvsssidcollect; "CVssSidCollection::AddWellKnownSid"
0x14002c893  mov     [rsp+1C0h+var_160], rax
0x14002c898  lea     rax, aSecsecrc; "SECSECRC"
0x14002c89f  mov     [rsp+1C0h+var_158], rax
0x14002c8a4  mov     [rsp+1C0h+var_150], 54Eh
0x14002c8ac  mov     [rsp+1C0h+var_14C], 0Bh
0x14002c8b4  mov     [rsp+1C0h+var_148], 0FFh
0x14002c8bc  mov     [rbp+0C0h+var_C8], 1000000h
0x14002c8c3  xor     edx, edx; Val
0x14002c8c5  mov     r8d, 78h ; 'x'; Size
0x14002c8cb  lea     rcx, [rbp+0C0h+var_140]; void *
0x14002c8cf  call    memset_0
0x14002c8d4  lea     r8, aCreatewellknow_1; "CreateWellKnownSid(type, NULL, NULL, &d"...
0x14002c8db  lea     rdx, [rsp+1C0h+var_168]
0x14002c8e0  lea     rcx, [rbp+0C0h+var_C0]
0x14002c8e4  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x14002c8ea  lea     rax, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x14002c8f1  mov     [rsp+1C0h+var_168], rax
0x14002c8f6  lea     rax, aCvsssidcollect; "CVssSidCollection::AddWellKnownSid"
0x14002c8fd  mov     [rsp+1C0h+var_160], rax
0x14002c902  lea     rax, aSecsecrc; "SECSECRC"
0x14002c909  mov     [rsp+1C0h+var_158], rax
0x14002c90e  mov     [rsp+1C0h+var_150], 551h
0x14002c916  mov     [rsp+1C0h+var_14C], 0Bh
0x14002c91e  mov     [rsp+1C0h+var_148], 0FFh
0x14002c926  mov     [rbp+0C0h+var_C8], 1000000h
0x14002c92d  xor     edx, edx; Val
0x14002c92f  mov     r8d, 78h ; 'x'; Size
0x14002c935  lea     rcx, [rbp+0C0h+var_140]; void *
0x14002c939  call    memset_0
0x14002c93e  lea     r8, aCreatewellknow_1; "CreateWellKnownSid(type, NULL, NULL, &d"...
0x14002c945  lea     rdx, [rsp+1C0h+var_168]
0x14002c94a  lea     rcx, [rbp+0C0h+var_C0]
0x14002c94e  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x14002c954  mov     dword ptr [rsp+1C0h+pExceptionObject], 8007000Eh
0x14002c95c  lea     rdx, _TI1J; pThrowInfo
0x14002c963  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x14002c968  call    _CxxThrowException_0
0x14002c96e  lea     rax, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x14002c975  mov     [rsp+1C0h+var_168], rax
0x14002c97a  lea     rax, aCvsssidcollect; "CVssSidCollection::AddWellKnownSid"
0x14002c981  mov     [rsp+1C0h+var_160], rax
0x14002c986  lea     rax, aSecsecrc; "SECSECRC"
0x14002c98d  mov     [rsp+1C0h+var_158], rax
0x14002c992  mov     [rsp+1C0h+var_150], 55Ah
0x14002c99a  mov     [rsp+1C0h+var_14C], 0Bh
0x14002c9a2  mov     [rsp+1C0h+var_148], 0FFh
0x14002c9aa  mov     [rbp+0C0h+var_C8], 1000000h
0x14002c9b1  xor     edx, edx; Val
0x14002c9b3  mov     r8d, 78h ; 'x'; Size
0x14002c9b9  lea     rcx, [rbp+0C0h+var_140]; void *
0x14002c9bd  call    memset_0
  ... truncated ...
```
