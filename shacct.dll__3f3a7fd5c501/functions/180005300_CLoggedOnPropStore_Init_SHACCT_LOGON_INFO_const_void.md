# CLoggedOnPropStore::Init(_SHACCT_LOGON_INFO const *,void *)

- ea: `0x180005300`
- end: `0x180005977`
- name: `?Init@CLoggedOnPropStore@@QEAAJPEBU_SHACCT_LOGON_INFO@@PEAX@Z`
- size: `1655`
- prototype: `int(CLoggedOnPropStore *__hidden this, const struct _SHACCT_LOGON_INFO *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004c90`
- `0x180005060`

## callees

- `0x180004fd0`
- `0x180005300`
- `0x180005d80`
- `0x1800088c0`
- `0x18000bcc0`
- `0x18000c240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005693`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005693`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800053ee`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180005702`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800053ee`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180005702`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800053c8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800053c8`
- `ntdll!RtlInitString` at `0x18000574c`
- `ntdll!RtlInitString` at `0x18000574c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000540e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000540e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005341`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800053d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800058ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800058bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005341`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800053d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800058ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800058bc`
- `SspiCli!LsaCallAuthenticationPackage` at `0x180005798`
- `SspiCli!LsaCallAuthenticationPackage` at `0x180005798`
- `SspiCli!LsaConnectUntrusted` at `0x180005729`
- `SspiCli!LsaConnectUntrusted` at `0x180005729`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800057aa`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800057aa`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18000575e`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18000575e`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800057d3`
- `SspiCli!LsaFreeReturnBuffer` at `0x180005850`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800057d3`
- `SspiCli!LsaFreeReturnBuffer` at `0x180005850`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180005888`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800058f2`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180005888`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800058f2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800054c4`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180005525`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180005594`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800055ea`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800056c2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800054c4`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180005525`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180005594`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800055ea`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800056c2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18000543f`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800054f4`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180005563`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800055d2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180005617`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18000543f`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800054f4`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180005563`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800055d2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180005617`

## pseudocode

```c
__int64 __fastcall CLoggedOnPropStore::Init(CLoggedOnPropStore *this, const struct _SHACCT_LOGON_INFO *a2, void *a3)
{
  const struct _SHACCT_LOGON_INFO *v4; // rdi
  signed int Error; // ebx
  _OWORD *v7; // rax
  __int64 v8; // rcx
  __int128 v9; // xmm0
  DWORD LengthSid; // r14d
  void *v11; // rax
  void *v12; // rdi
  DWORD *v13; // rdx
  void *v14; // rcx
  const wchar_t *v15; // r15
  __int64 v16; // r14
  size_t v17; // rdi
  unsigned __int64 v18; // r12
  DWORD *v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r9
  DWORD *v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r9
  DWORD *v27; // rdx
  LPWSTR v28; // rcx
  DWORD *v29; // rdx
  void *v30; // rcx
  const wchar_t *v31; // r15
  size_t v32; // rdi
  unsigned __int64 v33; // r12
  LPWSTR v34; // rcx
  signed int LastError; // eax
  void *v36; // r8
  int v37; // edi
  __int64 v38; // rdx
  __int64 v39; // rcx
  LPWSTR v40; // rdi
  DWORD v41; // r15d
  __int64 v42; // r8
  __int64 v43; // rdx
  _BYTE *v44; // rax
  void *v45; // rcx
  __int64 result; // rax
  LPVOID v47; // rax
  SIZE_T v48; // rcx
  WCHAR *v49; // rax
  WCHAR *v50; // rdx
  __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // rcx
  DWORD *pBytesReturned; // [rsp+20h] [rbp-A9h]
  DWORD *pBytesReturneda; // [rsp+20h] [rbp-A9h]
  unsigned __int64 *ReturnBufferLength; // [rsp+28h] [rbp-A1h]
  unsigned __int64 *ReturnBufferLengtha; // [rsp+28h] [rbp-A1h]
  unsigned int ProtocolStatus; // [rsp+30h] [rbp-99h]
  unsigned int ProtocolStatusa; // [rsp+30h] [rbp-99h]
  DWORD v61; // [rsp+40h] [rbp-89h] BYREF
  LPWSTR v62; // [rsp+48h] [rbp-81h] BYREF
  DWORD cchReferencedDomainName; // [rsp+50h] [rbp-79h] BYREF
  ULONG AuthenticationPackage; // [rsp+54h] [rbp-75h] BYREF
  void *LsaHandle; // [rsp+58h] [rbp-71h] BYREF
  LPWSTR ppBuffer; // [rsp+60h] [rbp-69h] BYREF
  DWORD v67; // [rsp+68h] [rbp-61h] BYREF
  _STRING DestinationString; // [rsp+70h] [rbp-59h] BYREF
  int ProtocolSubmitBuffer; // [rsp+80h] [rbp-49h] BYREF
  __int128 v70; // [rsp+84h] [rbp-45h]
  _OWORD pDestinationSid[4]; // [rsp+94h] [rbp-35h] BYREF
  int v72; // [rsp+D4h] [rbp+Bh]

  v4 = a2;
  Error = -2147024809;
  if ( !a2 )
    return (unsigned int)Error;
  v7 = CoTaskMemAlloc(0x210u);
  *((_QWORD *)this + 3) = v7;
  if ( !v7 )
    return (unsigned int)-2147024882;
  v8 = 4;
  do
  {
    v7 += 8;
    v9 = *(_OWORD *)v4;
    v4 = (const struct _SHACCT_LOGON_INFO *)((char *)v4 + 128);
    *(v7 - 8) = v9;
    *(v7 - 7) = *((_OWORD *)v4 - 7);
    *(v7 - 6) = *((_OWORD *)v4 - 6);
    *(v7 - 5) = *((_OWORD *)v4 - 5);
    *(v7 - 4) = *((_OWORD *)v4 - 4);
    *(v7 - 3) = *((_OWORD *)v4 - 3);
    *(v7 - 2) = *((_OWORD *)v4 - 2);
    *(v7 - 1) = *((_OWORD *)v4 - 1);
    --v8;
  }
  while ( v8 );
  Error = -2147024882;
  *v7 = *(_OWORD *)v4;
  *((_QWORD *)this + 9) = 0;
  LengthSid = GetLengthSid(a3);
  v11 = CoTaskMemAlloc(LengthSid);
  v12 = v11;
  if ( !v11 )
    return (unsigned int)Error;
  if ( CopySid(LengthSid, v11, a3) )
  {
    *((_QWORD *)this + 9) = v12;
    Error = 0;
    v12 = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
  }
  CoTaskMemFree(v12);
  if ( Error < 0 )
    return (unsigned int)Error;
  v13 = (DWORD *)*((_QWORD *)this + 3);
  ppBuffer = 0;
  v67 = 0;
  if ( WTSQuerySessionInformationW(0, *v13, WTSUserName, &ppBuffer, &v67) )
  {
    v15 = ppBuffer;
    v16 = -1;
    v17 = -1;
    do
      ++v17;
    while ( ppBuffer[v17] );
    *((_QWORD *)this + 10) = 0;
    v18 = v17 + 1;
    if ( v17 + 1 < v17 || (v62 = 0, !is_mul_ok(v18, 2u)) )
    {
      v34 = (LPWSTR)v15;
      Error = -2147024362;
      goto LABEL_45;
    }
    Error = CTCoAllocPolicy::Alloc(v14, (v18 * (unsigned __int128)2uLL) >> 64, 2 * v18, (void **)this + 10);
    if ( Error < 0 )
    {
      v34 = ppBuffer;
      goto LABEL_45;
    }
    StringCchCopyNExW(
      *((STRSAFE_LPWSTR *)this + 10),
      v17 + 1,
      v15,
      v17,
      (size_t)pBytesReturned,
      ReturnBufferLength,
      ProtocolStatus);
    WTSFreeMemory(ppBuffer);
    v19 = (DWORD *)*((_QWORD *)this + 3);
    v62 = 0;
    v61 = 0;
    if ( WTSQuerySessionInformationW(0, *v19, WTSClientName, &v62, &v61) )
    {
      v22 = -1;
      do
        ++v22;
      while ( v62[v22] );
      ReturnBufferLengtha = (unsigned __int64 *)((char *)this + 40);
      Error = _AllocStringWorker<CTCoAllocPolicy>(v21, v20, v62, v22);
      WTSFreeMemory(v62);
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
    if ( Error < 0 )
      goto LABEL_46;
    v23 = (DWORD *)*((_QWORD *)this + 3);
    v62 = 0;
    v61 = 0;
    if ( WTSQuerySessionInformationW(0, *v23, WTSWinStationName, &v62, &v61) )
    {
      v26 = -1;
      do
        ++v26;
      while ( v62[v26] );
      ReturnBufferLengtha = (unsigned __int64 *)((char *)this + 48);
      Error = _AllocStringWorker<CTCoAllocPolicy>(v25, v24, v62, v26);
      WTSFreeMemory(v62);
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
    if ( Error < 0 )
      goto LABEL_46;
    v27 = (DWORD *)*((_QWORD *)this + 3);
    v62 = 0;
    v61 = 0;
    if ( !WTSQuerySessionInformationW(0, *v27, WTSConnectState, &v62, &v61)
      || (v28 = v62,
          *((_DWORD *)this + 14) = *(_DWORD *)v62,
          WTSFreeMemory(v28),
          v29 = (DWORD *)*((_QWORD *)this + 3),
          v62 = 0,
          v61 = 0,
          !WTSQuerySessionInformationW(0, *v29, WTSDomainName, &v62, &v61)) )
    {
      LastError = GetLastError();
      Error = LastError;
      if ( LastError > 0 )
        Error = (unsigned __int16)LastError | 0x80070000;
      if ( Error >= 0 )
        Error = -2147467259;
      goto LABEL_46;
    }
    v31 = v62;
    v32 = -1;
    do
      ++v32;
    while ( v62[v32] );
    *((_QWORD *)this + 11) = 0;
    v33 = v32 + 1;
    if ( v32 + 1 >= v32 && (LsaHandle = 0, is_mul_ok(v33, 2u)) )
    {
      Error = CTCoAllocPolicy::Alloc(v30, (v33 * (unsigned __int128)2uLL) >> 64, 2 * v33, (void **)this + 11);
      if ( Error >= 0 )
      {
        StringCchCopyNExW(
          *((STRSAFE_LPWSTR *)this + 11),
          v32 + 1,
          v31,
          v32,
          (size_t)pBytesReturneda,
          ReturnBufferLengtha,
          ProtocolStatusa);
        v34 = v62;
LABEL_45:
        WTSFreeMemory(v34);
LABEL_46:
        v36 = (void *)*((_QWORD *)this + 9);
        ProtocolSubmitBuffer = 15;
        memset(pDestinationSid, 0, sizeof(pDestinationSid));
        v72 = 0;
        v70 = xmmword_18001B190;
        CopySid(0x44u, pDestinationSid, v36);
        LsaHandle = 0;
        AuthenticationPackage = 0;
        DestinationString = 0;
        v62 = 0;
        v61 = 0;
        cchReferencedDomainName = 0;
        if ( LsaConnectUntrusted(&LsaHandle) < 0 )
          goto LABEL_52;
        RtlInitString(&DestinationString, "CloudAP");
        v37 = LsaLookupAuthenticationPackage(LsaHandle, (PLSA_STRING)&DestinationString, &AuthenticationPackage);
        if ( v37 >= 0 )
        {
          v37 = LsaCallAuthenticationPackage(
                  LsaHandle,
                  AuthenticationPackage,
                  &ProtocolSubmitBuffer,
                  0x58u,
                  (PVOID *)&v62,
                  &v61,
                  (PNTSTATUS)&cchReferencedDomainName);
          if ( v37 >= 0 )
            v37 = cchReferencedDomainName;
        }
        LsaDeregisterLogonProcess(LsaHandle);
        if ( v37 < 0 )
        {
LABEL_52:
          if ( v62 )
            LsaFreeReturnBuffer(v62);
        }
        else
        {
          v40 = v62;
          v41 = v61;
          v62 = 0;
          if ( v40 )
          {
            if ( v40[12] )
            {
              v42 = *((_QWORD *)v40 + 4);
              do
                ++v16;
              while ( *(_WORD *)(v42 + 2 * v16) );
              Error = _AllocStringWorker<CTCoAllocPolicy>(v39, v38, v42, v16);
              if ( Error >= 0 )
                *(_OWORD *)((char *)this + 104) = xmmword_18001B190;
            }
            if ( v41 )
            {
              v43 = v41;
              v44 = v40;
              do
              {
                *v44++ = 0;
                --v43;
              }
              while ( v43 );
            }
            LsaFreeReturnBuffer(v40);
          }
        }
        return (unsigned int)Error;
      }
    }
    else
    {
      Error = -2147024362;
    }
    v34 = v62;
    goto LABEL_45;
  }
  v45 = (void *)*((_QWORD *)this + 9);
  AuthenticationPackage = 0;
  cchReferencedDomainName = 0;
  v61 = 0;
  if ( LookupAccountSidLocalW(v45, 0, &AuthenticationPackage, 0, &cchReferencedDomainName, (PSID_NAME_USE)&v61) )
    return 2147549183LL;
  result = ResultFromKnownLastError();
  if ( (_DWORD)result == -2147024774 )
  {
    v47 = CoTaskMemAlloc(2LL * AuthenticationPackage);
    v48 = 2LL * cchReferencedDomainName;
    *((_QWORD *)this + 10) = v47;
    v49 = (WCHAR *)CoTaskMemAlloc(v48);
    v50 = (WCHAR *)*((_QWORD *)this + 10);
    *((_QWORD *)this + 11) = v49;
    if ( v50 && v49 )
    {
      if ( LookupAccountSidLocalW(
             *((PSID *)this + 9),
             v50,
             &AuthenticationPackage,
             v49,
             &cchReferencedDomainName,
             (PSID_NAME_USE)&v61) )
      {
        result = _AllocStringWorker<CTCoAllocPolicy>(v52, v51, &qword_18001B188, 0);
        if ( (int)result >= 0 )
        {
          result = _AllocStringWorker<CTCoAllocPolicy>(v54, v53, &qword_18001B188, 0);
          if ( (int)result >= 0 )
            *((_DWORD *)this + 14) = 1;
        }
      }
      else
      {
        return ResultFromKnownLastError();
      }
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005300  push    rbp
0x180005302  push    rbx
0x180005303  push    rsi
0x180005304  push    rdi
0x180005305  push    r12
0x180005307  push    r14
0x180005309  push    r15
0x18000530b  lea     rbp, [rsp-27h]
0x180005310  sub     rsp, 0F0h
0x180005317  mov     rax, cs:__security_cookie
0x18000531e  xor     rax, rsp
0x180005321  mov     [rbp+57h+var_40], rax
0x180005325  mov     r15, r8
0x180005328  mov     rdi, rdx
0x18000532b  mov     rsi, rcx
0x18000532e  mov     ebx, 80070057h
0x180005333  test    rdx, rdx
0x180005336  jz      loc_180005957
0x18000533c  mov     ecx, 210h; cb
0x180005341  call    cs:__imp_CoTaskMemAlloc
0x180005347  mov     [rsi+18h], rax
0x18000534b  test    rax, rax
0x18000534e  jz      loc_180005952
0x180005354  mov     ecx, 4
0x180005359  nop     dword ptr [rax+00000000h]
0x180005360  lea     rax, [rax+80h]
0x180005367  movups  xmm0, xmmword ptr [rdi]
0x18000536a  lea     rdi, [rdi+80h]
0x180005371  movups  xmmword ptr [rax-80h], xmm0
0x180005375  movups  xmm1, xmmword ptr [rdi-70h]
0x180005379  movups  xmmword ptr [rax-70h], xmm1
0x18000537d  movups  xmm0, xmmword ptr [rdi-60h]
0x180005381  movups  xmmword ptr [rax-60h], xmm0
0x180005385  movups  xmm1, xmmword ptr [rdi-50h]
0x180005389  movups  xmmword ptr [rax-50h], xmm1
0x18000538d  movups  xmm0, xmmword ptr [rdi-40h]
0x180005391  movups  xmmword ptr [rax-40h], xmm0
0x180005395  movups  xmm1, xmmword ptr [rdi-30h]
0x180005399  movups  xmmword ptr [rax-30h], xmm1
0x18000539d  movups  xmm0, xmmword ptr [rdi-20h]
0x1800053a1  movups  xmmword ptr [rax-20h], xmm0
0x1800053a5  movups  xmm1, xmmword ptr [rdi-10h]
0x1800053a9  movups  xmmword ptr [rax-10h], xmm1
0x1800053ad  sub     rcx, 1
0x1800053b1  jnz     short loc_180005360
0x1800053b3  movups  xmm0, xmmword ptr [rdi]
0x1800053b6  xor     r12d, r12d
0x1800053b9  mov     rcx, r15; pSid
0x1800053bc  mov     ebx, 8007000Eh
0x1800053c1  movups  xmmword ptr [rax], xmm0
0x1800053c4  mov     [rsi+48h], r12
0x1800053c8  call    cs:__imp_GetLengthSid
0x1800053ce  mov     ecx, eax; cb
0x1800053d0  mov     r14d, eax
0x1800053d3  call    cs:__imp_CoTaskMemAlloc
0x1800053d9  mov     rdi, rax
0x1800053dc  test    rax, rax
0x1800053df  jz      loc_180005957
0x1800053e5  mov     r8, r15; pSourceSid
0x1800053e8  mov     rdx, rax; pDestinationSid
0x1800053eb  mov     ecx, r14d; nDestinationSidLength
0x1800053ee  call    cs:__imp_CopySid
0x1800053f4  test    eax, eax
0x1800053f6  jz      short loc_180005404
0x1800053f8  mov     [rsi+48h], rdi
0x1800053fc  mov     ebx, r12d
0x1800053ff  mov     edi, r12d
0x180005402  jmp     short loc_18000540B
0x180005404  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005409  mov     ebx, eax
0x18000540b  mov     rcx, rdi; pv
0x18000540e  call    cs:__imp_CoTaskMemFree
0x180005414  test    ebx, ebx
0x180005416  js      loc_180005957
0x18000541c  mov     rdx, [rsi+18h]
0x180005420  lea     rax, [rbp+57h+var_B8]
0x180005424  mov     [rbp+57h+ppBuffer], r12
0x180005428  lea     r9, [rbp+57h+ppBuffer]; ppBuffer
0x18000542c  mov     [rbp+57h+var_B8], r12d
0x180005430  mov     r8d, 5; WTSInfoClass
0x180005436  xor     ecx, ecx; hServer
0x180005438  mov     [rsp+120h+pBytesReturned], rax; pcchNewDestLength
0x18000543d  mov     edx, [rdx]; SessionId
0x18000543f  call    cs:__imp_WTSQuerySessionInformationW
0x180005445  test    eax, eax
0x180005447  jz      loc_18000585B
0x18000544d  mov     r15, [rbp+57h+ppBuffer]
0x180005451  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180005458  mov     rdi, r14
0x18000545b  mov     [rsp+120h+arg_8], r13
0x180005463  inc     rdi
0x180005466  cmp     [r15+rdi*2], r12w
0x18000546b  jnz     short loc_180005463
0x18000546d  mov     [rsi+50h], r12
0x180005471  lea     r12, [rdi+1]
0x180005475  cmp     r12, rdi
0x180005478  jb      loc_1800056BA
0x18000547e  mov     eax, 2
0x180005483  mov     [rsp+120h+var_D8], 0
0x18000548c  mul     r12
0x18000548f  test    rdx, rdx
0x180005492  jnz     loc_1800056BA
0x180005498  lea     r9, [rsi+50h]; void **
0x18000549c  mov     r8, rax; unsigned __int64
0x18000549f  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800054a4  mov     ebx, eax
0x1800054a6  test    eax, eax
0x1800054a8  js      loc_1800056B4
0x1800054ae  mov     rcx, [rsi+50h]; pszDest
0x1800054b2  mov     r9, rdi; cchToCopy
0x1800054b5  mov     r8, r15; pszSrc
0x1800054b8  mov     rdx, r12; cchDest
0x1800054bb  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800054c0  mov     rcx, [rbp+57h+ppBuffer]; pMemory
0x1800054c4  call    cs:__imp_WTSFreeMemory
0x1800054ca  mov     rdx, [rsi+18h]
0x1800054ce  lea     rax, [rsp+120h+var_E0]
0x1800054d3  xor     r12d, r12d
0x1800054d6  mov     [rsp+120h+pBytesReturned], rax; pBytesReturned
0x1800054db  mov     [rsp+120h+var_D8], r12
0x1800054e0  lea     r9, [rsp+120h+var_D8]; ppBuffer
0x1800054e5  mov     [rsp+120h+var_E0], r12d
0x1800054ea  mov     r8d, 0Ah; WTSInfoClass
0x1800054f0  mov     edx, [rdx]; SessionId
0x1800054f2  xor     ecx, ecx; hServer
0x1800054f4  call    cs:__imp_WTSQuerySessionInformationW
0x1800054fa  test    eax, eax
0x1800054fc  jz      short loc_18000552D
0x1800054fe  mov     r8, [rsp+120h+var_D8]
0x180005503  mov     r9, r14
0x180005506  inc     r9
0x180005509  cmp     [r8+r9*2], r12w
0x18000550e  jnz     short loc_180005506
0x180005510  lea     rax, [rsi+28h]
0x180005514  mov     [rsp+120h+ReturnBufferLength], rax
0x180005519  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18000551e  mov     rcx, [rsp+120h+var_D8]; pMemory
0x180005523  mov     ebx, eax
0x180005525  call    cs:__imp_WTSFreeMemory
0x18000552b  jmp     short loc_180005534
0x18000552d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005532  mov     ebx, eax
0x180005534  test    ebx, ebx
0x180005536  js      loc_1800056CB
0x18000553c  mov     rdx, [rsi+18h]
0x180005540  lea     rax, [rsp+120h+var_E0]
0x180005545  mov     [rsp+120h+var_D8], r12
0x18000554a  lea     r9, [rsp+120h+var_D8]; ppBuffer
0x18000554f  mov     [rsp+120h+var_E0], r12d
0x180005554  mov     r8d, 6; WTSInfoClass
0x18000555a  xor     ecx, ecx; hServer
0x18000555c  mov     [rsp+120h+pBytesReturned], rax; pBytesReturned
0x180005561  mov     edx, [rdx]; SessionId
0x180005563  call    cs:__imp_WTSQuerySessionInformationW
0x180005569  test    eax, eax
0x18000556b  jz      short loc_18000559C
0x18000556d  mov     r8, [rsp+120h+var_D8]
0x180005572  mov     r9, r14
0x180005575  inc     r9
0x180005578  cmp     [r8+r9*2], r12w
0x18000557d  jnz     short loc_180005575
0x18000557f  lea     rax, [rsi+30h]
0x180005583  mov     [rsp+120h+ReturnBufferLength], rax
0x180005588  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18000558d  mov     rcx, [rsp+120h+var_D8]; pMemory
0x180005592  mov     ebx, eax
0x180005594  call    cs:__imp_WTSFreeMemory
0x18000559a  jmp     short loc_1800055A3
0x18000559c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800055a1  mov     ebx, eax
0x1800055a3  test    ebx, ebx
0x1800055a5  js      loc_1800056CB
0x1800055ab  mov     rdx, [rsi+18h]
0x1800055af  lea     rax, [rsp+120h+var_E0]
0x1800055b4  mov     [rsp+120h+var_D8], r12
0x1800055b9  lea     r9, [rsp+120h+var_D8]; ppBuffer
0x1800055be  mov     [rsp+120h+var_E0], r12d
0x1800055c3  mov     r8d, 8; WTSInfoClass
0x1800055c9  xor     ecx, ecx; hServer
0x1800055cb  mov     [rsp+120h+pBytesReturned], rax; pBytesReturned
0x1800055d0  mov     edx, [rdx]; SessionId
0x1800055d2  call    cs:__imp_WTSQuerySessionInformationW
0x1800055d8  test    eax, eax
0x1800055da  jz      loc_180005693
0x1800055e0  mov     rcx, [rsp+120h+var_D8]; pMemory
0x1800055e5  mov     eax, [rcx]
0x1800055e7  mov     [rsi+38h], eax
0x1800055ea  call    cs:__imp_WTSFreeMemory
0x1800055f0  mov     rdx, [rsi+18h]
0x1800055f4  lea     rax, [rsp+120h+var_E0]
0x1800055f9  mov     [rsp+120h+var_D8], r12
0x1800055fe  lea     r9, [rsp+120h+var_D8]; ppBuffer
0x180005603  mov     [rsp+120h+var_E0], r12d
0x180005608  mov     r8d, 7; WTSInfoClass
0x18000560e  xor     ecx, ecx; hServer
0x180005610  mov     [rsp+120h+pBytesReturned], rax; pcchNewDestLength
0x180005615  mov     edx, [rdx]; SessionId
0x180005617  call    cs:__imp_WTSQuerySessionInformationW
0x18000561d  test    eax, eax
0x18000561f  jz      short loc_180005693
0x180005621  mov     r15, [rsp+120h+var_D8]
0x180005626  mov     rdi, r14
0x180005629  nop     dword ptr [rax+00000000h]
0x180005630  inc     rdi
0x180005633  cmp     [r15+rdi*2], r12w
0x180005638  jnz     short loc_180005630
0x18000563a  mov     [rsi+58h], r12
0x18000563e  lea     r12, [rdi+1]
0x180005642  cmp     r12, rdi
0x180005645  jb      short loc_180005687
0x180005647  mov     eax, 2
0x18000564c  mov     [rbp+57h+LsaHandle], 0
0x180005654  mul     r12
0x180005657  test    rdx, rdx
0x18000565a  jnz     short loc_180005687
0x18000565c  lea     r9, [rsi+58h]; void **
0x180005660  mov     r8, rax; unsigned __int64
0x180005663  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180005668  mov     ebx, eax
0x18000566a  test    eax, eax
0x18000566c  js      short loc_18000568C
0x18000566e  mov     rcx, [rsi+58h]; pszDest
0x180005672  mov     r9, rdi; cchToCopy
0x180005675  mov     r8, r15; pszSrc
0x180005678  mov     rdx, r12; cchDest
0x18000567b  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180005680  mov     rcx, [rsp+120h+var_D8]
0x180005685  jmp     short loc_1800056C2
0x180005687  mov     ebx, 80070216h
0x18000568c  mov     rcx, [rsp+120h+var_D8]
0x180005691  jmp     short loc_1800056C2
0x180005693  call    cs:__imp_GetLastError
0x180005699  mov     ebx, eax
0x18000569b  test    eax, eax
0x18000569d  jle     short loc_1800056A8
0x18000569f  movzx   ebx, ax
0x1800056a2  or      ebx, 80070000h
0x1800056a8  test    ebx, ebx
0x1800056aa  mov     eax, 80004005h
0x1800056af  cmovns  ebx, eax
0x1800056b2  jmp     short loc_1800056CB
0x1800056b4  mov     rcx, [rbp+57h+ppBuffer]
0x1800056b8  jmp     short loc_1800056C2
0x1800056ba  mov     rcx, r15; pMemory
0x1800056bd  mov     ebx, 80070216h
0x1800056c2  call    cs:__imp_WTSFreeMemory
0x1800056c8  xor     r12d, r12d
0x1800056cb  mov     r8, [rsi+48h]; pSourceSid
0x1800056cf  lea     rdx, [rbp+57h+pDestinationSid]; pDestinationSid
0x1800056d3  xorps   xmm0, xmm0
0x1800056d6  mov     [rbp+57h+ProtocolSubmitBuffer], 0Fh
0x1800056dd  movups  [rbp+57h+pDestinationSid], xmm0
0x1800056e1  xor     eax, eax
0x1800056e3  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x1800056e8  movups  [rbp+57h+var_7C], xmm0
0x1800056ec  mov     [rbp+57h+var_4C], eax
0x1800056ef  movups  [rbp+57h+var_6C], xmm0
0x1800056f3  movups  [rbp+57h+var_5C], xmm0
0x1800056f7  movups  xmm0, cs:xmmword_18001B190
0x1800056fe  movups  [rbp+57h+var_9C], xmm0
0x180005702  call    cs:__imp_CopySid
0x180005708  xorps   xmm0, xmm0
0x18000570b  mov     [rbp+57h+LsaHandle], r12
0x18000570f  lea     rcx, [rbp+57h+LsaHandle]; LsaHandle
0x180005713  mov     [rbp+57h+AuthenticationPackage], r12d
0x180005717  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000571b  mov     [rsp+120h+var_D8], r12
0x180005720  mov     [rsp+120h+var_E0], r12d
0x180005725  mov     [rbp+57h+cchReferencedDomainName], r12d
0x180005729  call    cs:__imp_LsaConnectUntrusted
0x18000572f  mov     r13, [rsp+120h+arg_8]
0x180005737  mov     edi, eax
0x180005739  test    eax, eax
0x18000573b  js      loc_1800057C5
0x180005741  lea     rdx, SourceString; "CloudAP"
0x180005748  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000574c  call    cs:__imp_RtlInitString
0x180005752  mov     rcx, [rbp+57h+LsaHandle]; LsaHandle
0x180005756  lea     r8, [rbp+57h+AuthenticationPackage]; AuthenticationPackage
0x18000575a  lea     rdx, [rbp+57h+DestinationString]; PackageName
0x18000575e  call    cs:__imp_LsaLookupAuthenticationPackage
0x180005764  mov     edi, eax
0x180005766  test    eax, eax
0x180005768  js      short loc_1800057A6
0x18000576a  mov     edx, [rbp+57h+AuthenticationPackage]; AuthenticationPackage
0x18000576d  lea     rax, [rbp+57h+cchReferencedDomainName]
0x180005771  mov     rcx, [rbp+57h+LsaHandle]; LsaHandle
0x180005775  lea     r8, [rbp+57h+ProtocolSubmitBuffer]; ProtocolSubmitBuffer
0x180005779  mov     qword ptr [rsp+120h+ProtocolStatus], rax; ProtocolStatus
0x18000577e  mov     r9d, 58h ; 'X'; SubmitBufferLength
0x180005784  lea     rax, [rsp+120h+var_E0]
0x180005789  mov     [rsp+120h+ReturnBufferLength], rax; ReturnBufferLength
0x18000578e  lea     rax, [rsp+120h+var_D8]
0x180005793  mov     [rsp+120h+pBytesReturned], rax; ProtocolReturnBuffer
0x180005798  call    cs:__imp_LsaCallAuthenticationPackage
0x18000579e  test    eax, eax
0x1800057a0  mov     edi, eax
0x1800057a2  cmovns  edi, [rbp+57h+cchReferencedDomainName]
0x1800057a6  mov     rcx, [rbp+57h+LsaHandle]; LsaHandle
0x1800057aa  call    cs:__imp_LsaDeregisterLogonProcess
  ... truncated ...
```
