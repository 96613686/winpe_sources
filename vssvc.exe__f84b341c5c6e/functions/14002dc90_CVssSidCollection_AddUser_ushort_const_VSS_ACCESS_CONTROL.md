# CVssSidCollection::AddUser(ushort const *,VSS_ACCESS_CONTROL)

- ea: `0x14002dc90`
- end: `0x14002e394`
- name: `?AddUser@CVssSidCollection@@AEAAXPEBGW4VSS_ACCESS_CONTROL@@@Z`
- size: `1796`
- prototype: `void __high(const unsigned __int16 *, enum VSS_ACCESS_CONTROL)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14002b160`

## callees

- `0x1400137c0`
- `0x1400138e0`
- `0x1400139c0`
- `0x140013c60`
- `0x140015e38`
- `0x14002c9f0`
- `0x14002dc90`
- `0x14003a8f0`
- `0x1400921dc`
- `0x1400921e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002de66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002e1b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002de66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002e1b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002e0fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002e105`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002e0fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002e105`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14002e06f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14002e098`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14002e06f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14002e098`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002dd40`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002df60`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002dd40`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002df60`
- `VssTrace!__imp_VssTraceMessage` at `0x14002e263`
- `VssTrace!__imp_VssTraceMessage` at `0x14002e263`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002e019`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002e04e`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002e019`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002e04e`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002dd78`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002dd78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002df1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002df2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002df40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002df52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002e03a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002df1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002df2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002df40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002df52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002e03a`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x14002de5d`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x14002e0d7`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x14002de5d`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x14002e0d7`

## string_xrefs

- `0x14002dcba`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002dea8`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002e127`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002e1ba`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002e26e`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002dcc6`: `CVssSidCollection::AddUser`
- `0x14002deb4`: `CVssSidCollection::AddUser`
- `0x14002e133`: `CVssSidCollection::AddUser`
- `0x14002e1c6`: `CVssSidCollection::AddUser`
- `0x14002e27a`: `CVssSidCollection::AddUser`
- `0x14002e331`: `CVssSidCollection::AddUser`
- `0x14002df02`: `LookupAccountName fails for %s, winerror %d. This key value in VssAccessControl is ignored.`
- `0x14002e18f`: `LookupAccountName fails to give SID size for %s, fReturn %d, winerror %d, dwSid %d, dwDomain %d. This key value is ignored.`
- `0x14002e2c4`: `User %s specified under VssAccessControl key doesn't exist. This key value is ignored.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CVssSidCollection::AddUser(__int64 a1, const WCHAR *a2, int a3)
{
  __int64 v5; // rax
  unsigned int v6; // r12d
  unsigned int v7; // ebx
  __int64 i; // rbx
  void *v9; // rcx
  BOOL v10; // r15d
  DWORD LastError; // eax
  DWORD v12; // edi
  DWORD v13; // r14d
  DWORD v14; // esi
  HLOCAL v15; // rdi
  WCHAR *v16; // r14
  DWORD v17; // ebx
  DWORD v18; // ebx
  LPDWORD cchReferencedDomainName; // [rsp+20h] [rbp-E0h]
  LPDWORD cchReferencedDomainNamea; // [rsp+20h] [rbp-E0h]
  LPDWORD cchReferencedDomainNameb; // [rsp+20h] [rbp-E0h]
  PSID_NAME_USE peUse; // [rsp+28h] [rbp-D8h]
  __int64 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  __int64 v25; // [rsp+40h] [rbp-C0h]
  __int64 pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  enum _SID_NAME_USE v27; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v28; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v29; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v30; // [rsp+70h] [rbp-90h]
  int v31; // [rsp+78h] [rbp-88h]
  int v32; // [rsp+7Ch] [rbp-84h]
  int v33; // [rsp+80h] [rbp-80h]
  LPVOID v34[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v35; // [rsp+98h] [rbp-68h]
  __int128 v36; // [rsp+A8h] [rbp-58h]
  __int128 v37; // [rsp+B8h] [rbp-48h]
  __int128 v38; // [rsp+C8h] [rbp-38h]
  __int128 v39; // [rsp+D8h] [rbp-28h]
  __int128 v40; // [rsp+E8h] [rbp-18h]
  __int64 v41; // [rsp+F8h] [rbp-8h]
  int v42; // [rsp+100h] [rbp+0h]
  unsigned __int64 v43; // [rsp+110h] [rbp+10h] BYREF
  int v44; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v45; // [rsp+120h] [rbp+20h]
  const unsigned __int16 *v46; // [rsp+128h] [rbp+28h]
  unsigned int v47; // [rsp+130h] [rbp+30h]
  unsigned int v48; // [rsp+134h] [rbp+34h]
  const wchar_t *v49; // [rsp+138h] [rbp+38h]
  unsigned int v50; // [rsp+140h] [rbp+40h]
  DWORD TickCount; // [rsp+144h] [rbp+44h]
  unsigned int v52; // [rsp+148h] [rbp+48h]
  LPVOID pv[2]; // [rsp+150h] [rbp+50h]
  LPVOID v54[2]; // [rsp+160h] [rbp+60h]
  __int64 v55; // [rsp+170h] [rbp+70h]
  void **v56; // [rsp+180h] [rbp+80h] BYREF
  HLOCAL v57; // [rsp+188h] [rbp+88h]
  void **v58; // [rsp+190h] [rbp+90h] BYREF
  WCHAR *v59; // [rsp+198h] [rbp+98h]
  DWORD v61; // [rsp+1E8h] [rbp+E8h] BYREF
  DWORD cbSid; // [rsp+1F8h] [rbp+F8h] BYREF

  v28 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v29 = L"CVssSidCollection::AddUser";
  v30 = L"SECSECRC";
  v31 = 1390;
  v32 = 11;
  v33 = 255;
  v42 = 0x1000000;
  *(_OWORD *)v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v44 = 0;
  v49 = L"CVssSidCollection::AddUser";
  v45 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v46 = L"SECSECRC";
  v47 = 1390;
  v48 = 11;
  TickCount = GetTickCount();
  v52 = 255;
  v43 = 0xFFFFFFFF00000000uLL;
  v55 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v54 = 0;
  pExceptionObject = 0;
  if ( (int)VssGetTracingContextPerThread(&pExceptionObject) < 0 || (int)VssSetTracingContextPerThread(&v43) < 0 )
  {
    v5 = v55;
  }
  else
  {
    v5 = pExceptionObject;
    v55 = pExceptionObject;
  }
  if ( v5 )
    v50 = *(_DWORD *)(v5 + 48) + 1;
  else
    v50 = 0;
  v6 = 160;
  v7 = 160;
  if ( v52 != 255 )
    v7 = v52;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v43, v48) )
    VssTraceMessage(v45, v46, v47, v50, v48, v49, L"ENTER", v7, 0);
  for ( i = 0; i != 15; ++i )
  {
    v9 = v34[i];
    if ( v9 )
    {
      CoTaskMemFree(v9);
      v34[i] = 0;
    }
  }
  v57 = 0;
  v56 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  v59 = 0;
  v58 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  v27 = SidTypeInvalid;
  v61 = 0;
  cbSid = 0;
  if ( !a2 || !*a2 )
  {
    v28 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v29 = L"CVssSidCollection::AddUser";
    v30 = L"SECSECRC";
    v31 = 1405;
    v32 = 11;
    v33 = 255;
    v42 = 0x1000000;
    memset_0(v34, 0, 0x78u);
    CVssFunctionTracer::Throw(&v43, &v28, 2147549183LL, L"Invalid user name argument");
  }
  v10 = LookupAccountNameLocalW(a2, 0, &cbSid, 0, &v61, &v27);
  LastError = GetLastError();
  v12 = LastError;
  if ( v10 )
  {
    v13 = cbSid;
LABEL_32:
    v17 = v61;
    v28 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v29 = L"CVssSidCollection::AddUser";
    v30 = L"SECSECRC";
    v31 = 1412;
    v32 = 11;
    v33 = 255;
    v42 = 0x1000000;
    memset_0(v34, 0, 0x78u);
    LODWORD(v24) = v17;
    LODWORD(v23) = v13;
    LODWORD(peUse) = v12;
    LODWORD(cchReferencedDomainName) = v10;
    CVssFunctionTracer::Trace(
      &v43,
      &v28,
      L"LookupAccountName fails to give SID size for %s, fReturn %d, winerror %d, dwSid %d, dwDomain %d. This key value is ignored.",
      a2,
      cchReferencedDomainName,
      peUse,
      v23,
      v24);
LABEL_30:
    CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v43);
    return;
  }
  v13 = cbSid;
  if ( !cbSid || !v61 )
    goto LABEL_32;
  if ( LastError == 1332 )
  {
    v28 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v29 = L"CVssSidCollection::AddUser";
    v30 = L"SECSECRC";
    v31 = 1417;
    v32 = 11;
    v33 = 255;
    v42 = 0x1000000;
    memset_0(v34, 0, 0x78u);
    CVssFunctionTracer::Trace(
      &v43,
      &v28,
      L"User %s specified under VssAccessControl key doesn't exist. This key value is ignored.",
      a2);
    CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v58);
    CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v56);
    goto LABEL_30;
  }
  if ( LastError == 122 )
  {
    v15 = LocalAlloc(0, cbSid);
    v57 = v15;
    if ( !v15 )
    {
      LODWORD(pExceptionObject) = -2147024882;
      throw (long *)&pExceptionObject;
    }
    v16 = (WCHAR *)LocalAlloc(0, 2LL * v61 + 2);
    v59 = v16;
    if ( !v16 )
    {
      LODWORD(pExceptionObject) = -2147024882;
      throw (long *)&pExceptionObject;
    }
    if ( LookupAccountNameLocalW(a2, v15, &cbSid, v16, &v61, &v27) )
    {
      CVssSidCollection::AddSid(a1, v15, a3);
    }
    else
    {
      v18 = GetLastError();
      v28 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v29 = L"CVssSidCollection::AddUser";
      v30 = L"SECSECRC";
      v31 = 1440;
      v32 = 11;
      v33 = 255;
      v42 = 0x1000000;
      memset_0(v34, 0, 0x78u);
      LODWORD(cchReferencedDomainNameb) = v18;
      CVssFunctionTracer::Trace(
        &v43,
        &v28,
        L"LookupAccountName fails unexpectedly for %s, winerror %d. Account ignored.",
        a2,
        cchReferencedDomainNameb);
    }
    LocalFree(v16);
    LocalFree(v15);
    goto LABEL_30;
  }
  v28 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v29 = L"CVssSidCollection::AddUser";
  v30 = L"SECSECRC";
  v31 = 1422;
  v32 = 11;
  v33 = 255;
  v42 = 0x1000000;
  memset_0(v34, 0, 0x78u);
  LODWORD(cchReferencedDomainName) = v12;
  CVssFunctionTracer::Trace(
    &v43,
    &v28,
    L"LookupAccountName fails for %s, winerror %d. This key value in VssAccessControl is ignored.",
    a2,
    cchReferencedDomainName);
  CoTaskMemFree(pv[0]);
  pv[0] = 0;
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v54[0]);
  v54[0] = 0;
  CoTaskMemFree(v54[1]);
  v54[1] = 0;
  v14 = GetTickCount() - TickCount;
  if ( v52 != 255 )
    v6 = v52;
  LODWORD(v25) = v14;
  LODWORD(v24) = v14 % 0x3E8;
  LODWORD(v23) = v14 / 0x3E8 % 0x3C;
  LODWORD(peUse) = v14 / 0xEA60 % 0x3C;
  LODWORD(cchReferencedDomainNamea) = v14 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)&v43,
    L"EXIT",
    v6,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    cchReferencedDomainNamea,
    peUse,
    v23,
    v24,
    v25,
    v44);
  VssSetTracingContextPerThread(v55);
}

```

## disassembly

```asm
0x14002dc90  mov     [rsp-8+arg_10], rbx
0x14002dc95  mov     [rsp-8+arg_0], rcx
0x14002dc9a  push    rbp
0x14002dc9b  push    rsi
0x14002dc9c  push    rdi
0x14002dc9d  push    r12
0x14002dc9f  push    r13
0x14002dca1  push    r14
0x14002dca3  push    r15
0x14002dca5  lea     rbp, [rsp-0A0h]
0x14002dcad  sub     rsp, 1A0h
0x14002dcb4  mov     r13d, r8d
0x14002dcb7  mov     rsi, rdx
0x14002dcba  lea     r15, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x14002dcc1  mov     [rsp+1D0h+var_170], r15
0x14002dcc6  lea     rcx, aCvsssidcollect_4; "CVssSidCollection::AddUser"
0x14002dccd  mov     [rsp+1D0h+var_168], rcx
0x14002dcd2  lea     rdx, aSecsecrc; "SECSECRC"
0x14002dcd9  mov     [rsp+1D0h+var_160], rdx
0x14002dcde  mov     [rsp+1D0h+var_158], 56Eh
0x14002dce6  mov     [rsp+1D0h+var_154], 0Bh
0x14002dcee  mov     [rbp+0D0h+var_150], 0FFh
0x14002dcf5  xor     edi, edi
0x14002dcf7  mov     [rbp+0D0h+var_D0], 1000000h
0x14002dcfe  xorps   xmm0, xmm0
0x14002dd01  xor     eax, eax
0x14002dd03  movups  xmmword ptr [rbp+0D0h+var_148], xmm0
0x14002dd07  movups  [rbp+0D0h+var_138], xmm0
0x14002dd0b  movups  [rbp+0D0h+var_128], xmm0
0x14002dd0f  movups  [rbp+0D0h+var_118], xmm0
0x14002dd13  movups  [rbp+0D0h+var_108], xmm0
0x14002dd17  movups  [rbp+0D0h+var_F8], xmm0
0x14002dd1b  movups  [rbp+0D0h+var_E8], xmm0
0x14002dd1f  mov     [rbp+0D0h+var_D8], rax
0x14002dd23  mov     [rbp+0D0h+var_B8], edi
0x14002dd26  mov     [rbp+0D0h+var_98], rcx
0x14002dd2a  mov     [rbp+0D0h+var_B0], r15
0x14002dd2e  mov     [rbp+0D0h+var_A8], rdx
0x14002dd32  mov     [rbp+0D0h+var_A0], 56Eh
0x14002dd39  mov     [rbp+0D0h+var_9C], 0Bh
0x14002dd40  call    cs:__imp_GetTickCount
0x14002dd46  mov     [rbp+0D0h+var_8C], eax
0x14002dd49  mov     [rbp+0D0h+var_BC], 0FFFFFFFFh
0x14002dd50  mov     [rbp+0D0h+var_88], 0FFh
0x14002dd57  mov     [rbp+0D0h+var_C0], edi
0x14002dd5a  mov     [rbp+0D0h+var_60], rdi
0x14002dd5e  xorps   xmm0, xmm0
0x14002dd61  movdqa  xmmword ptr [rbp+0D0h+pv], xmm0
0x14002dd66  xorps   xmm1, xmm1
0x14002dd69  movdqa  xmmword ptr [rbp+0D0h+var_70], xmm1
0x14002dd6e  mov     [rsp+1D0h+pExceptionObject], rdi
0x14002dd73  lea     rcx, [rsp+1D0h+pExceptionObject]
0x14002dd78  call    cs:__imp_VssGetTracingContextPerThread
0x14002dd7e  test    eax, eax
0x14002dd80  jns     loc_14002E04A
0x14002dd86  mov     rax, [rbp+0D0h+var_60]
0x14002dd8a  test    rax, rax
0x14002dd8d  jz      loc_14002E1AA
0x14002dd93  mov     eax, [rax+30h]
0x14002dd96  inc     eax
0x14002dd98  mov     [rbp+0D0h+var_90], eax
0x14002dd9b  mov     r12d, 0A0h
0x14002dda1  mov     ebx, r12d
0x14002dda4  cmp     [rbp+0D0h+var_88], 0FFh
0x14002ddab  cmovnz  ebx, [rbp+0D0h+var_88]
0x14002ddaf  mov     edx, [rbp+0D0h+var_9C]; unsigned int
0x14002ddb2  lea     rcx, [rbp+0D0h+var_C0]; this
0x14002ddb6  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14002ddbb  test    eax, eax
0x14002ddbd  jnz     loc_14002E22E
0x14002ddc3  mov     rbx, rdi
0x14002ddc6  nop     word ptr [rax+rax+00000000h]
0x14002ddd0  mov     rcx, [rbp+rbx*8+0D0h+var_148]; pv
0x14002ddd5  test    rcx, rcx
0x14002ddd8  jnz     loc_14002E03A
0x14002ddde  inc     rbx
0x14002dde1  cmp     rbx, 0Fh
0x14002dde5  jnz     short loc_14002DDD0
0x14002dde7  mov     [rbp+0D0h+var_48], rdi
0x14002ddee  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x14002ddf5  mov     [rbp+0D0h+var_50], rax
0x14002ddfc  mov     [rbp+0D0h+var_38], rdi
0x14002de03  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x14002de0a  mov     [rbp+0D0h+var_40], rax
0x14002de11  mov     [rsp+1D0h+var_178], 7
0x14002de19  mov     [rbp+0D0h+arg_8], edi
0x14002de1f  mov     [rbp+0D0h+cbSid], edi
0x14002de25  test    rsi, rsi
0x14002de28  jz      loc_14002E32C
0x14002de2e  cmp     word ptr [rsi], 0
0x14002de32  jz      loc_14002E32C
0x14002de38  lea     rax, [rsp+1D0h+var_178]
0x14002de3d  mov     [rsp+1D0h+peUse], rax; peUse
0x14002de42  lea     rax, [rbp+0D0h+arg_8]
0x14002de49  mov     [rsp+1D0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14002de4e  xor     r9d, r9d; ReferencedDomainName
0x14002de51  lea     r8, [rbp+0D0h+cbSid]; cbSid
0x14002de58  xor     edx, edx; Sid
0x14002de5a  mov     rcx, rsi; lpAccountName
0x14002de5d  call    cs:__imp_LookupAccountNameLocalW
0x14002de63  mov     r15d, eax
0x14002de66  call    cs:__imp_GetLastError
0x14002de6c  mov     edi, eax
0x14002de6e  test    r15d, r15d
0x14002de71  jnz     loc_14002E11A
0x14002de77  mov     r14d, [rbp+0D0h+cbSid]
0x14002de7e  test    r14d, r14d
0x14002de81  jz      loc_14002E121
0x14002de87  cmp     [rbp+0D0h+arg_8], r15d
0x14002de8e  jz      loc_14002E121
0x14002de94  cmp     eax, 534h
0x14002de99  jz      loc_14002E26E
0x14002de9f  cmp     eax, 7Ah ; 'z'
0x14002dea2  jz      loc_14002E06A
0x14002dea8  lea     rax, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x14002deaf  mov     [rsp+1D0h+var_170], rax
0x14002deb4  lea     rax, aCvsssidcollect_4; "CVssSidCollection::AddUser"
0x14002debb  mov     [rsp+1D0h+var_168], rax
0x14002dec0  lea     rax, aSecsecrc; "SECSECRC"
0x14002dec7  mov     [rsp+1D0h+var_160], rax
0x14002decc  mov     [rsp+1D0h+var_158], 58Eh
0x14002ded4  mov     [rsp+1D0h+var_154], 0Bh
0x14002dedc  mov     [rbp+0D0h+var_150], 0FFh
0x14002dee3  mov     [rbp+0D0h+var_D0], 1000000h
0x14002deea  xor     edx, edx; Val
0x14002deec  mov     r8d, 78h ; 'x'; Size
0x14002def2  lea     rcx, [rbp+0D0h+var_148]; void *
0x14002def6  call    memset_0
0x14002defb  mov     dword ptr [rsp+1D0h+cchReferencedDomainName], edi
0x14002deff  mov     r9, rsi
0x14002df02  lea     r8, aLookupaccountn_2; "LookupAccountName fails for %s, winerro"...
0x14002df09  lea     rdx, [rsp+1D0h+var_170]
0x14002df0e  lea     rcx, [rbp+0D0h+var_C0]
0x14002df12  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14002df17  nop
0x14002df18  mov     rcx, [rbp+0D0h+pv]; pv
0x14002df1c  call    cs:__imp_CoTaskMemFree
0x14002df22  mov     [rbp+0D0h+pv], 0
0x14002df2a  mov     rcx, [rbp+0D0h+pv+8]; pv
0x14002df2e  call    cs:__imp_CoTaskMemFree
0x14002df34  mov     [rbp+0D0h+pv+8], 0
0x14002df3c  mov     rcx, [rbp+0D0h+var_70]; pv
0x14002df40  call    cs:__imp_CoTaskMemFree
0x14002df46  mov     [rbp+0D0h+var_70], 0
0x14002df4e  mov     rcx, [rbp+0D0h+var_70+8]; pv
0x14002df52  call    cs:__imp_CoTaskMemFree
0x14002df58  mov     [rbp+0D0h+var_70+8], 0
0x14002df60  call    cs:__imp_GetTickCount
0x14002df66  mov     esi, eax
0x14002df68  sub     esi, [rbp+0D0h+var_8C]
0x14002df6b  mov     eax, 10624DD3h
0x14002df70  mul     esi
0x14002df72  mov     edi, edx
0x14002df74  shr     edi, 6
0x14002df77  mov     eax, 88888889h
0x14002df7c  mul     edi
0x14002df7e  shr     edx, 5
0x14002df81  imul    ecx, edx, 3Ch ; '<'
0x14002df84  mov     ebx, edi
0x14002df86  sub     ebx, ecx
0x14002df88  mov     eax, 45E7B273h
0x14002df8d  mul     esi
0x14002df8f  mov     r11d, edx
0x14002df92  shr     r11d, 0Eh
0x14002df96  mov     eax, 88888889h
0x14002df9b  mul     r11d
0x14002df9e  shr     edx, 5
0x14002dfa1  imul    ecx, edx, 3Ch ; '<'
0x14002dfa4  sub     r11d, ecx
0x14002dfa7  mov     eax, 95217CB1h
0x14002dfac  mul     esi
0x14002dfae  mov     r10d, edx
0x14002dfb1  shr     r10d, 15h
0x14002dfb5  mov     eax, 88888889h
0x14002dfba  mul     r10d
0x14002dfbd  shr     edx, 5
0x14002dfc0  imul    eax, edx, 3Ch ; '<'
0x14002dfc3  sub     r10d, eax
0x14002dfc6  mov     r9d, [rbp+0D0h+var_B8]
0x14002dfca  cmp     [rbp+0D0h+var_88], 0FFh
0x14002dfd1  cmovnz  r12d, [rbp+0D0h+var_88]
0x14002dfd6  imul    eax, edi, 3E8h
0x14002dfdc  mov     ecx, esi
0x14002dfde  sub     ecx, eax
0x14002dfe0  mov     [rsp+1D0h+var_188], r9d
0x14002dfe5  mov     dword ptr [rsp+1D0h+var_190], esi
0x14002dfe9  mov     dword ptr [rsp+1D0h+var_198], ecx
0x14002dfed  mov     dword ptr [rsp+1D0h+var_1A0], ebx
0x14002dff1  mov     dword ptr [rsp+1D0h+peUse], r11d
0x14002dff6  mov     dword ptr [rsp+1D0h+cchReferencedDomainName], r10d
0x14002dffb  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x14002e002  mov     r8d, r12d; unsigned int
0x14002e005  lea     rdx, aExit; "EXIT"
0x14002e00c  lea     rcx, [rbp+0D0h+var_C0]; this
0x14002e010  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x14002e015  mov     rcx, [rbp+0D0h+var_60]
0x14002e019  call    cs:__imp_VssSetTracingContextPerThread
0x14002e01f  mov     rbx, [rsp+1D0h+arg_10]
0x14002e027  add     rsp, 1A0h
0x14002e02e  pop     r15
0x14002e030  pop     r14
0x14002e032  pop     r13
0x14002e034  pop     r12
0x14002e036  pop     rdi
0x14002e037  pop     rsi
0x14002e038  pop     rbp
0x14002e039  retn
0x14002e03a  call    cs:__imp_CoTaskMemFree
0x14002e040  mov     [rbp+rbx*8+0D0h+var_148], rdi
0x14002e045  jmp     loc_14002DDDE
0x14002e04a  lea     rcx, [rbp+0D0h+var_C0]
0x14002e04e  call    cs:__imp_VssSetTracingContextPerThread
0x14002e054  test    eax, eax
0x14002e056  js      loc_14002DD86
0x14002e05c  mov     rax, [rsp+1D0h+pExceptionObject]
0x14002e061  mov     [rbp+0D0h+var_60], rax
0x14002e065  jmp     loc_14002DD8A
0x14002e06a  mov     rdx, r14; uBytes
0x14002e06d  xor     ecx, ecx; uFlags
0x14002e06f  call    cs:__imp_LocalAlloc
0x14002e075  mov     rdi, rax
0x14002e078  mov     [rbp+0D0h+var_48], rax
0x14002e07f  test    rax, rax
0x14002e082  jz      loc_14002E2F8
0x14002e088  mov     edx, [rbp+0D0h+arg_8]
0x14002e08e  lea     rdx, ds:2[rdx*2]; uBytes
0x14002e096  xor     ecx, ecx; uFlags
0x14002e098  call    cs:__imp_LocalAlloc
0x14002e09e  mov     r14, rax
0x14002e0a1  mov     [rbp+0D0h+var_38], rax
0x14002e0a8  test    rax, rax
0x14002e0ab  jz      loc_14002E312
0x14002e0b1  lea     rax, [rsp+1D0h+var_178]
0x14002e0b6  mov     [rsp+1D0h+peUse], rax; peUse
0x14002e0bb  lea     rax, [rbp+0D0h+arg_8]
0x14002e0c2  mov     [rsp+1D0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14002e0c7  mov     r9, r14; ReferencedDomainName
0x14002e0ca  lea     r8, [rbp+0D0h+cbSid]; cbSid
0x14002e0d1  mov     rdx, rdi; Sid
0x14002e0d4  mov     rcx, rsi; lpAccountName
0x14002e0d7  call    cs:__imp_LookupAccountNameLocalW
0x14002e0dd  test    eax, eax
0x14002e0df  jz      loc_14002E1B2
0x14002e0e5  mov     r8d, r13d
0x14002e0e8  mov     rdx, rdi
0x14002e0eb  mov     rcx, [rbp+0D0h+arg_0]
0x14002e0f2  call    ?AddSid@CVssSidCollection@@AEAAXPEAXW4VSS_ACCESS_CONTROL@@@Z; CVssSidCollection::AddSid(void *,VSS_ACCESS_CONTROL)
0x14002e0f7  nop
0x14002e0f8  mov     rcx, r14; hMem
0x14002e0fb  call    cs:__imp_LocalFree
0x14002e101  nop
0x14002e102  mov     rcx, rdi; hMem
0x14002e105  call    cs:__imp_LocalFree
0x14002e10b  nop
0x14002e10c  lea     rcx, [rbp+0D0h+var_C0]; this
0x14002e110  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14002e115  jmp     loc_14002E01F
0x14002e11a  mov     r14d, [rbp+0D0h+cbSid]
0x14002e121  mov     ebx, [rbp+0D0h+arg_8]
0x14002e127  lea     rax, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x14002e12e  mov     [rsp+1D0h+var_170], rax
0x14002e133  lea     rax, aCvsssidcollect_4; "CVssSidCollection::AddUser"
0x14002e13a  mov     [rsp+1D0h+var_168], rax
0x14002e13f  lea     rax, aSecsecrc; "SECSECRC"
0x14002e146  mov     [rsp+1D0h+var_160], rax
0x14002e14b  mov     [rsp+1D0h+var_158], 584h
0x14002e153  mov     [rsp+1D0h+var_154], 0Bh
0x14002e15b  mov     [rbp+0D0h+var_150], 0FFh
0x14002e162  mov     [rbp+0D0h+var_D0], 1000000h
0x14002e169  xor     edx, edx; Val
0x14002e16b  mov     r8d, 78h ; 'x'; Size
0x14002e171  lea     rcx, [rbp+0D0h+var_148]; void *
0x14002e175  call    memset_0
0x14002e17a  mov     dword ptr [rsp+1D0h+var_198], ebx
0x14002e17e  mov     dword ptr [rsp+1D0h+var_1A0], r14d
0x14002e183  mov     dword ptr [rsp+1D0h+peUse], edi
0x14002e187  mov     dword ptr [rsp+1D0h+cchReferencedDomainName], r15d
0x14002e18c  mov     r9, rsi
0x14002e18f  lea     r8, aLookupaccountn_1; "LookupAccountName fails to give SID siz"...
0x14002e196  lea     rdx, [rsp+1D0h+var_170]
0x14002e19b  lea     rcx, [rbp+0D0h+var_C0]
0x14002e19f  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14002e1a4  nop
0x14002e1a5  jmp     loc_14002E10C
0x14002e1aa  mov     [rbp+0D0h+var_90], edi
0x14002e1ad  jmp     loc_14002DD9B
0x14002e1b2  call    cs:__imp_GetLastError
0x14002e1b8  mov     ebx, eax
0x14002e1ba  lea     rax, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x14002e1c1  mov     [rsp+1D0h+var_170], rax
0x14002e1c6  lea     rax, aCvsssidcollect_4; "CVssSidCollection::AddUser"
0x14002e1cd  mov     [rsp+1D0h+var_168], rax
0x14002e1d2  lea     rax, aSecsecrc; "SECSECRC"
0x14002e1d9  mov     [rsp+1D0h+var_160], rax
0x14002e1de  mov     [rsp+1D0h+var_158], 5A0h
0x14002e1e6  mov     [rsp+1D0h+var_154], 0Bh
0x14002e1ee  mov     [rbp+0D0h+var_150], 0FFh
0x14002e1f5  mov     [rbp+0D0h+var_D0], 1000000h
0x14002e1fc  xor     edx, edx; Val
0x14002e1fe  mov     r8d, 78h ; 'x'; Size
  ... truncated ...
```
