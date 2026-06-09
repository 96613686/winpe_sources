# FrNetworkSource::AuthenticateKerberos(Vml::VmAccessToken &)

- ea: `0x1405532b4`
- end: `0x1405538e3`
- name: `?AuthenticateKerberos@FrNetworkSource@@IEAAJAEAVVmAccessToken@Vml@@@Z`
- size: `1583`
- prototype: `__int64 __fastcall(FrNetworkSource *__hidden this, struct Vml::VmAccessToken *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14017b944`
- `0x14042784c`

## callees

- `0x140022640`
- `0x1400342a0`
- `0x14004f3c4`
- `0x14005c630`
- `0x1401879a4`
- `0x1401be65c`
- `0x140304790`
- `0x1404828e0`
- `0x14054ba7c`
- `0x1405532b4`
- `0x140553988`
- `0x140554b30`
- `0x1405554c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140553377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140553879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140553377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140553879`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14055382f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140553844`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140553858`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14055382f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140553844`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140553858`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14055346e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140553484`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14055346e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140553484`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140553367`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140553367`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140553869`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140553869`
- `SspiCli!CompleteAuthToken` at `0x140553587`
- `SspiCli!CompleteAuthToken` at `0x140553587`
- `SspiCli!FreeCredentialsHandle` at `0x140553819`
- `SspiCli!FreeCredentialsHandle` at `0x140553819`
- `SspiCli!AcquireCredentialsHandleW` at `0x14055340c`
- `SspiCli!AcquireCredentialsHandleW` at `0x14055340c`
- `SspiCli!DeleteSecurityContext` at `0x1405537fb`
- `SspiCli!DeleteSecurityContext` at `0x1405537fb`
- `SspiCli!InitializeSecurityContextW` at `0x14055352c`
- `SspiCli!InitializeSecurityContextW` at `0x14055352c`

## pseudocode

```c
__int64 __fastcall FrNetworkSource::AuthenticateKerberos(FrNetworkSource *this, HANDLE *a2)
{
  _QWORD *v3; // rdx
  bool v4; // cc
  int v6; // r12d
  __int64 v7; // rcx
  SEC_WCHAR *TargetSpn; // r15
  signed int LastError; // eax
  int MaxAuthenticationTokenSize; // esi
  wchar_t **v11; // rdx
  unsigned __int16 *v12; // rcx
  unsigned int v13; // r14d
  HLOCAL v14; // rax
  struct _SecHandle *p_phNewContext; // rdx
  struct _SecBufferDesc *v16; // rax
  SECURITY_STATUS v17; // eax
  int v18; // ebx
  SECURITY_STATUS v19; // eax
  int v20; // r9d
  int v21; // ecx
  int v22; // ecx
  int v23; // r9d
  _QWORD *v24; // rax
  signed int v25; // eax
  SIZE_T uBytes; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem[2]; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL v29[2]; // [rsp+78h] [rbp-88h] BYREF
  struct _SecBufferDesc pToken; // [rsp+88h] [rbp-78h] BYREF
  __int128 v31; // [rsp+98h] [rbp-68h] BYREF
  unsigned int pfContextAttr; // [rsp+A8h] [rbp-58h] BYREF
  struct _SecHandle phNewContext; // [rsp+B0h] [rbp-50h] BYREF
  struct _SecHandle phCredential; // [rsp+C0h] [rbp-40h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v36[4]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v37[4]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v38[4]; // [rsp+118h] [rbp+18h] BYREF

  ptsExpiry.QuadPart = 0;
  pfContextAttr = 0;
  v3 = (_QWORD *)((char *)this + 128);
  LODWORD(uBytes) = 0;
  v4 = *((_QWORD *)this + 19) <= 7u;
  phCredential = 0;
  v6 = 0;
  phNewContext = 0;
  pToken = 0;
  *(_OWORD *)v29 = 0;
  v31 = 0;
  *(_OWORD *)hMem = 0;
  if ( !v4 )
    v3 = (_QWORD *)*v3;
  std::wstring::wstring(v36, v3);
  hMem[1] = 0;
  phNewContext.dwUpper = -1;
  phNewContext.dwLower = -1;
  phCredential.dwUpper = -1;
  phCredential.dwLower = -1;
  v29[1] = 0;
  TargetSpn = (SEC_WCHAR *)FrNetworkSource::CreateTargetSpn(v7, v36);
  if ( *a2 )
  {
    if ( !ImpersonateLoggedOnUser(*a2) )
    {
      LastError = GetLastError();
      MaxAuthenticationTokenSize = LastError;
      if ( LastError > 0 )
        MaxAuthenticationTokenSize = (unsigned __int16)LastError | 0x80070000;
      if ( !(unsigned int)VmlIsDebugTraceEnabled(16803) )
        goto LABEL_58;
      v11 = &off_140910248;
LABEL_9:
      VmlDebugTraceWithError(16803, v11, (unsigned int)MaxAuthenticationTokenSize);
      goto LABEL_58;
    }
    v6 = 1;
    if ( (unsigned int)VmlIsDebugTraceEnabled(49571) )
      VmlDebugTraceEx(49571, &off_140910260);
  }
  MaxAuthenticationTokenSize = AcquireCredentialsHandleW(
                                 0,
                                 (LPWSTR)L"Kerberos",
                                 2u,
                                 0,
                                 0,
                                 0,
                                 0,
                                 &phCredential,
                                 &ptsExpiry);
  if ( MaxAuthenticationTokenSize < 0 )
  {
    if ( !(unsigned int)VmlIsDebugTraceEnabled(16803) )
      goto LABEL_58;
    v11 = &off_140910320;
    goto LABEL_9;
  }
  MaxAuthenticationTokenSize = FrnUtilities::GetMaxAuthenticationTokenSize(v12, (unsigned int *)&uBytes);
  if ( MaxAuthenticationTokenSize < 0 )
  {
    if ( !(unsigned int)VmlIsDebugTraceEnabled(16803) )
      goto LABEL_58;
    v11 = &off_140910338;
    goto LABEL_9;
  }
  v13 = uBytes;
  hMem[1] = LocalAlloc(0, (unsigned int)uBytes);
  v14 = LocalAlloc(0, v13);
  v29[1] = v14;
  if ( !hMem[1] || !v14 )
  {
    MaxAuthenticationTokenSize = -2147024882;
    if ( (unsigned int)VmlIsDebugTraceEnabled(16803) )
    {
      VmlDebugTraceEx(16803, &off_140910350);
      goto LABEL_58;
    }
    goto LABEL_59;
  }
  *((_QWORD *)&v31 + 1) = hMem;
  HIDWORD(hMem[0]) = 2;
  pToken.pBuffers = (PSecBuffer)v29;
  p_phNewContext = 0;
  v16 = 0;
  *(_QWORD *)&v31 = 0x100000000LL;
  HIDWORD(v29[0]) = 2;
  pToken.cBuffers = 1;
  pToken.ulVersion = 0;
  while ( 1 )
  {
    LODWORD(v29[0]) = v13;
    v17 = InitializeSecurityContextW(
            &phCredential,
            p_phNewContext,
            TargetSpn,
            0x4802u,
            0,
            0x10u,
            v16,
            0,
            &phNewContext,
            &pToken,
            &pfContextAttr,
            0);
    if ( ((v17 - 590610) & 0xFFFFFFFD) != 0 )
    {
      v18 = 0;
    }
    else
    {
      v18 = 1;
      if ( v17 == 590612 )
        break;
    }
    if ( v17 == 590611 )
      break;
    if ( v17 && v17 != 590610 )
    {
      if ( (v17 & 0x1FFF0000) != 0 )
      {
        MaxAuthenticationTokenSize = v17;
        if ( v17 > 0 )
          MaxAuthenticationTokenSize = v17 & 0xFFFFFFF | 0x80000000;
      }
      else if ( v17 > 0 )
      {
        MaxAuthenticationTokenSize = (unsigned __int16)v17 | 0x80070000;
      }
      else
      {
        MaxAuthenticationTokenSize = v17;
      }
      if ( (unsigned int)VmlIsDebugTraceEnabled(16803) )
      {
        v11 = &off_1409102D8;
        goto LABEL_9;
      }
      goto LABEL_58;
    }
LABEL_31:
    if ( LODWORD(v29[0]) )
    {
      MaxAuthenticationTokenSize = FrNetworkSource::SendAuthPacket(this, v29[1], (unsigned int)v29[0]);
      if ( MaxAuthenticationTokenSize < 0 )
      {
        if ( !(unsigned int)VmlIsDebugTraceEnabled(16803) )
          goto LABEL_58;
        v11 = &off_1409102F0;
        goto LABEL_9;
      }
    }
    if ( !v18 )
    {
      if ( (pfContextAttr & 2) != 0 )
        goto LABEL_58;
      MaxAuthenticationTokenSize = -2147467259;
      if ( (unsigned int)VmlIsDebugTraceEnabled(16803) )
        VmlDebugTraceEx(16803, &off_140910150);
      goto LABEL_59;
    }
    LODWORD(uBytes) = v13;
    MaxAuthenticationTokenSize = FrNetworkSource::ReadAuthPacket(this, hMem[1], (unsigned int *)&uBytes);
    if ( MaxAuthenticationTokenSize < 0 )
    {
      if ( !(unsigned int)VmlIsDebugTraceEnabled(16803) )
        goto LABEL_58;
      v11 = &off_140910308;
      goto LABEL_9;
    }
    p_phNewContext = &phNewContext;
    LODWORD(hMem[0]) = uBytes;
    v16 = (struct _SecBufferDesc *)&v31;
  }
  v19 = CompleteAuthToken(&phNewContext, &pToken);
  if ( !v19 )
    goto LABEL_31;
  if ( (v19 & 0x1FFF0000) != 0 )
  {
    MaxAuthenticationTokenSize = v19;
    if ( v19 > 0 )
      MaxAuthenticationTokenSize = v19 & 0xFFFFFFF | 0x80000000;
  }
  else if ( v19 > 0 )
  {
    MaxAuthenticationTokenSize = (unsigned __int16)v19 | 0x80070000;
  }
  else
  {
    MaxAuthenticationTokenSize = v19;
  }
  if ( (unsigned int)VmlIsDebugTraceEnabled(16803) )
  {
    v11 = &off_1409102C0;
    goto LABEL_9;
  }
LABEL_58:
  if ( MaxAuthenticationTokenSize < 0 )
  {
LABEL_59:
    v20 = MaxAuthenticationTokenSize;
    v21 = (unsigned __int16)MaxAuthenticationTokenSize;
    if ( (MaxAuthenticationTokenSize & 0x1FFF0000) != 0x70000 )
      v21 = MaxAuthenticationTokenSize;
    if ( (unsigned int)(v21 - 12001) <= 0xBF )
      v20 = v21;
    _snwprintf_s<16>(v38, 16, L"%%%%%u", v20 & 0xEFFFFFFF);
    v22 = MaxAuthenticationTokenSize;
    v23 = MaxAuthenticationTokenSize;
    if ( (MaxAuthenticationTokenSize & 0x1FFF0000) == 0x70000 )
      v22 = (unsigned __int16)MaxAuthenticationTokenSize;
    if ( (unsigned int)(v22 - 12001) <= 0xBF )
      v23 = v22;
    _snwprintf_s<16>(v37, 16, L"0x%08X", v23 & 0xEFFFFFFF);
    v24 = v36;
    if ( v36[3] > 7u )
      v24 = (_QWORD *)v36[0];
    uBytes = (SIZE_T)v24;
    VmEventWriteAndReport<unsigned short (&)[16],unsigned short (&)[16],unsigned short const *>(
      (struct _EVENT_DESCRIPTOR *)&MSVM_VMMS_FRN_INTEGRATED_AUTH_ERROR,
      5u,
      (__int64)v38,
      (__int64)v37,
      (__int64)&uBytes);
    if ( (unsigned int)VmlIsDebugTraceEnabled(16803) )
      VmlDebugTraceWithError(16803, &off_140910168, (unsigned int)MaxAuthenticationTokenSize);
  }
  if ( phNewContext.dwLower != -1 && phNewContext.dwUpper != -1 )
    DeleteSecurityContext(&phNewContext);
  if ( phCredential.dwLower != -1 && phCredential.dwUpper != -1 )
    FreeCredentialsHandle(&phCredential);
  if ( hMem[1] )
    LocalFree(hMem[1]);
  if ( v29[1] )
    LocalFree(v29[1]);
  if ( TargetSpn )
    LocalFree(TargetSpn);
  if ( v6 && !RevertToSelf() )
  {
    v25 = GetLastError();
    MaxAuthenticationTokenSize = v25;
    if ( v25 > 0 )
      MaxAuthenticationTokenSize = (unsigned __int16)v25 | 0x80070000;
    if ( (unsigned int)VmlIsDebugTraceEnabled(16803) )
      VmlDebugTraceWithError(16803, &off_140910180, (unsigned int)MaxAuthenticationTokenSize);
  }
  std::wstring::_Tidy_deallocate(v36);
  return (unsigned int)MaxAuthenticationTokenSize;
}

```

## disassembly

```asm
0x1405532b4  mov     [rsp-8+arg_10], rbx
0x1405532b9  push    rbp
0x1405532ba  push    rsi
0x1405532bb  push    rdi
0x1405532bc  push    r12
0x1405532be  push    r13
0x1405532c0  push    r14
0x1405532c2  push    r15
0x1405532c4  lea     rbp, [rsp-40h]
0x1405532c9  sub     rsp, 140h
0x1405532d0  mov     rax, cs:__security_cookie
0x1405532d7  xor     rax, rsp
0x1405532da  mov     [rbp+70h+var_38], rax
0x1405532de  xor     r13d, r13d
0x1405532e1  xorps   xmm0, xmm0
0x1405532e4  xorps   xmm1, xmm1
0x1405532e7  mov     qword ptr [rbp+70h+var_A0], r13
0x1405532eb  mov     rbx, rdx
0x1405532ee  mov     [rbp+70h+var_C8], r13d
0x1405532f2  lea     rdx, [rcx+80h]
0x1405532f9  mov     dword ptr [rsp+170h+uBytes], r13d
0x1405532fe  cmp     qword ptr [rdx+18h], 7
0x140553303  mov     rdi, rcx
0x140553306  movups  xmmword ptr [rbp+70h+var_B0.dwLower], xmm0
0x14055330a  mov     r12d, r13d
0x14055330d  movups  xmmword ptr [rbp+70h+phNewContext.dwLower], xmm1
0x140553311  movups  xmmword ptr [rbp+70h+pToken.ulVersion], xmm0
0x140553315  movups  xmmword ptr [rsp+170h+var_F8], xmm1
0x14055331a  movups  [rbp+70h+var_D8], xmm0
0x14055331e  movups  xmmword ptr [rsp+170h+hMem], xmm1
0x140553323  jbe     short loc_140553328
0x140553325  mov     rdx, [rdx]
0x140553328  lea     rcx, [rbp+70h+var_98]
0x14055332c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140553331  or      rax, 0FFFFFFFFFFFFFFFFh
0x140553335  mov     [rsp+170h+hMem+8], r13
0x14055333a  lea     rdx, [rbp+70h+var_98]
0x14055333e  mov     [rbp+70h+phNewContext.dwUpper], rax
0x140553342  mov     [rbp+70h+phNewContext.dwLower], rax
0x140553346  mov     [rbp+70h+var_B0.dwUpper], rax
0x14055334a  mov     [rbp+70h+var_B0.dwLower], rax
0x14055334e  mov     [rbp+70h+var_F8+8], r13
0x140553352  call    ?CreateTargetSpn@FrNetworkSource@@IEAAPEAGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FrNetworkSource::CreateTargetSpn(std::wstring const &)
0x140553357  mov     rcx, [rbx]; hToken
0x14055335a  mov     r15, rax
0x14055335d  mov     ebx, 41A3h
0x140553362  test    rcx, rcx
0x140553365  jz      short loc_1405533DB
0x140553367  call    cs:__imp_ImpersonateLoggedOnUser
0x14055336e  nop     dword ptr [rax+rax+00h]
0x140553373  test    eax, eax
0x140553375  jnz     short loc_1405533B7
0x140553377  call    cs:__imp_GetLastError
0x14055337e  nop     dword ptr [rax+rax+00h]
0x140553383  mov     esi, eax
0x140553385  test    eax, eax
0x140553387  jle     short loc_140553392
0x140553389  movzx   esi, ax
0x14055338c  or      esi, 80070000h
0x140553392  mov     ecx, ebx
0x140553394  call    VmlIsDebugTraceEnabled
0x140553399  test    eax, eax
0x14055339b  jz      loc_140553703
0x1405533a1  lea     rdx, off_140910248; "ImpersonateLoggedOnUser failed."
0x1405533a8  mov     r8d, esi
0x1405533ab  mov     ecx, ebx
0x1405533ad  call    VmlDebugTraceWithError
0x1405533b2  jmp     loc_140553703
0x1405533b7  mov     esi, 0C1A3h
0x1405533bc  mov     r12d, 1
0x1405533c2  mov     ecx, esi
0x1405533c4  call    VmlIsDebugTraceEnabled
0x1405533c9  test    eax, eax
0x1405533cb  jz      short loc_1405533DB
0x1405533cd  lea     rdx, off_140910260; "Impersonated successfully."
0x1405533d4  mov     ecx, esi
0x1405533d6  call    VmlDebugTraceEx
0x1405533db  lea     rax, [rbp+70h+var_A0]
0x1405533df  xor     r9d, r9d; pvLogonId
0x1405533e2  mov     [rsp+170h+ptsExpiry], rax; ptsExpiry
0x1405533e7  lea     rdx, pszPackage; "Kerberos"
0x1405533ee  lea     rax, [rbp+70h+var_B0]
0x1405533f2  xor     ecx, ecx; pszPrincipal
0x1405533f4  mov     [rsp+170h+phCredential], rax; phCredential
0x1405533f9  mov     [rsp+170h+pvGetKeyArgument], r13; pvGetKeyArgument
0x1405533fe  lea     r8d, [r9+2]; fCredentialUse
0x140553402  mov     [rsp+170h+pGetKeyFn], r13; pGetKeyFn
0x140553407  mov     [rsp+170h+pAuthData], r13; pAuthData
0x14055340c  call    cs:__imp_AcquireCredentialsHandleW
0x140553413  nop     dword ptr [rax+rax+00h]
0x140553418  mov     esi, eax
0x14055341a  test    eax, eax
0x14055341c  jns     short loc_140553439
0x14055341e  mov     ecx, ebx
0x140553420  call    VmlIsDebugTraceEnabled
0x140553425  test    eax, eax
0x140553427  jz      loc_140553703
0x14055342d  lea     rdx, off_140910320; "Failed to get local credentials."
0x140553434  jmp     loc_1405533A8
0x140553439  lea     rdx, [rsp+170h+uBytes]; unsigned int *
0x14055343e  call    ?GetMaxAuthenticationTokenSize@FrnUtilities@@SAJPEAGAEAI@Z; FrnUtilities::GetMaxAuthenticationTokenSize(ushort *,uint &)
0x140553443  mov     esi, eax
0x140553445  test    eax, eax
0x140553447  jns     short loc_140553464
0x140553449  mov     ecx, ebx
0x14055344b  call    VmlIsDebugTraceEnabled
0x140553450  test    eax, eax
0x140553452  jz      loc_140553703
0x140553458  lea     rdx, off_140910338; "Failed to retrieve token size."
0x14055345f  jmp     loc_1405533A8
0x140553464  mov     r14d, dword ptr [rsp+170h+uBytes]
0x140553469  xor     ecx, ecx; uFlags
0x14055346b  mov     edx, r14d; uBytes
0x14055346e  call    cs:__imp_LocalAlloc
0x140553475  nop     dword ptr [rax+rax+00h]
0x14055347a  mov     edx, r14d; uBytes
0x14055347d  xor     ecx, ecx; uFlags
0x14055347f  mov     [rsp+170h+hMem+8], rax
0x140553484  call    cs:__imp_LocalAlloc
0x14055348b  nop     dword ptr [rax+rax+00h]
0x140553490  mov     [rbp+70h+var_F8+8], rax
0x140553494  cmp     [rsp+170h+hMem+8], r13
0x140553499  jz      loc_1405536E5
0x14055349f  test    rax, rax
0x1405534a2  jz      loc_1405536E5
0x1405534a8  lea     rax, [rsp+170h+hMem]
0x1405534ad  mov     dword ptr [rbp+70h+var_D8+4], 1
0x1405534b4  mov     qword ptr [rbp+70h+var_D8+8], rax
0x1405534b8  mov     ecx, 2
0x1405534bd  lea     rax, [rsp+170h+var_F8]
0x1405534c2  mov     dword ptr [rsp+170h+hMem+4], ecx
0x1405534c6  mov     [rbp+70h+pToken.pBuffers], rax
0x1405534ca  mov     rdx, r13; phContext
0x1405534cd  mov     rax, r13
0x1405534d0  mov     dword ptr [rbp+70h+var_D8], r13d
0x1405534d4  mov     dword ptr [rsp+170h+var_F8+4], ecx
0x1405534d8  mov     [rbp+70h+pToken.cBuffers], 1
0x1405534df  mov     [rbp+70h+pToken.ulVersion], r13d
0x1405534e3  mov     [rsp+170h+var_118], r13; ptsExpiry
0x1405534e8  lea     rcx, [rbp+70h+var_C8]
0x1405534ec  mov     [rsp+170h+pfContextAttr], rcx; pfContextAttr
0x1405534f1  mov     r9d, 4802h; fContextReq
0x1405534f7  lea     rcx, [rbp+70h+pToken]
0x1405534fb  mov     dword ptr [rsp+170h+var_F8], r14d
0x140553500  mov     [rsp+170h+pOutput], rcx; pOutput
0x140553505  mov     r8, r15; pszTargetName
0x140553508  lea     rcx, [rbp+70h+phNewContext]
0x14055350c  mov     [rsp+170h+ptsExpiry], rcx; phNewContext
0x140553511  lea     rcx, [rbp+70h+var_B0]; phCredential
0x140553515  mov     dword ptr [rsp+170h+phCredential], r13d; Reserved2
0x14055351a  mov     [rsp+170h+pvGetKeyArgument], rax; pInput
0x14055351f  mov     dword ptr [rsp+170h+pGetKeyFn], 10h; TargetDataRep
0x140553527  mov     dword ptr [rsp+170h+pAuthData], r13d; Reserved1
0x14055352c  call    cs:__imp_InitializeSecurityContextW
0x140553533  nop     dword ptr [rax+rax+00h]
0x140553538  lea     ecx, [rax-90312h]
0x14055353e  test    ecx, 0FFFFFFFDh
0x140553544  jz      short loc_14055354B
0x140553546  mov     ebx, r13d
0x140553549  jmp     short loc_140553557
0x14055354b  mov     ebx, 1
0x140553550  cmp     eax, 90314h
0x140553555  jz      short loc_14055357F
0x140553557  cmp     eax, 90313h
0x14055355c  jz      short loc_14055357F
0x14055355e  test    eax, eax
0x140553560  jz      short loc_14055359B
0x140553562  cmp     eax, 90312h
0x140553567  jz      short loc_14055359B
0x140553569  test    eax, 1FFF0000h
0x14055356e  jnz     loc_1405535FC
0x140553574  test    eax, eax
0x140553576  jg      short loc_1405535F1
0x140553578  mov     esi, eax
0x14055357a  jmp     loc_14055360E
0x14055357f  lea     rdx, [rbp+70h+pToken]; pToken
0x140553583  lea     rcx, [rbp+70h+phNewContext]; phContext
0x140553587  call    cs:__imp_CompleteAuthToken
0x14055358e  nop     dword ptr [rax+rax+00h]
0x140553593  test    eax, eax
0x140553595  jnz     loc_14055369D
0x14055359b  mov     r8d, dword ptr [rsp+170h+var_F8]; unsigned int
0x1405535a0  test    r8d, r8d
0x1405535a3  jz      short loc_1405535B7
0x1405535a5  mov     rdx, [rbp+70h+var_F8+8]; void *
0x1405535a9  mov     rcx, rdi; this
0x1405535ac  call    ?SendAuthPacket@FrNetworkSource@@IEAAJPEAXI@Z; FrNetworkSource::SendAuthPacket(void *,uint)
0x1405535b1  mov     esi, eax
0x1405535b3  test    eax, eax
0x1405535b5  js      short loc_14055362E
0x1405535b7  test    ebx, ebx
0x1405535b9  jz      loc_14055366E
0x1405535bf  mov     rdx, [rsp+170h+hMem+8]; void *
0x1405535c4  lea     r8, [rsp+170h+uBytes]; unsigned int *
0x1405535c9  mov     rcx, rdi; this
0x1405535cc  mov     dword ptr [rsp+170h+uBytes], r14d
0x1405535d1  call    ?ReadAuthPacket@FrNetworkSource@@IEAAJPEAXAEAI@Z; FrNetworkSource::ReadAuthPacket(void *,uint &)
0x1405535d6  mov     esi, eax
0x1405535d8  test    eax, eax
0x1405535da  js      short loc_14055364E
0x1405535dc  mov     eax, dword ptr [rsp+170h+uBytes]
0x1405535e0  lea     rdx, [rbp+70h+phNewContext]
0x1405535e4  mov     dword ptr [rsp+170h+hMem], eax
0x1405535e8  lea     rax, [rbp+70h+var_D8]
0x1405535ec  jmp     loc_1405534E3
0x1405535f1  movzx   esi, ax
0x1405535f4  or      esi, 80070000h
0x1405535fa  jmp     short loc_14055360E
0x1405535fc  mov     esi, eax
0x1405535fe  test    eax, eax
0x140553600  jle     short loc_14055360E
0x140553602  and     esi, 0FFFFFFFh
0x140553608  or      esi, 80000000h
0x14055360e  mov     ebx, 41A3h
0x140553613  mov     ecx, ebx
0x140553615  call    VmlIsDebugTraceEnabled
0x14055361a  test    eax, eax
0x14055361c  jz      loc_140553703
0x140553622  lea     rdx, off_1409102D8; "Failed to create authentication token."
0x140553629  jmp     loc_1405533A8
0x14055362e  mov     ebx, 41A3h
0x140553633  mov     ecx, ebx
0x140553635  call    VmlIsDebugTraceEnabled
0x14055363a  test    eax, eax
0x14055363c  jz      loc_140553703
0x140553642  lea     rdx, off_1409102F0; "failed to send authentication token to "...
0x140553649  jmp     loc_1405533A8
0x14055364e  mov     ebx, 41A3h
0x140553653  mov     ecx, ebx
0x140553655  call    VmlIsDebugTraceEnabled
0x14055365a  test    eax, eax
0x14055365c  jz      loc_140553703
0x140553662  lea     rdx, off_140910308; "wait for authentication message from ta"...
0x140553669  jmp     loc_1405533A8
0x14055366e  test    byte ptr [rbp+70h+var_C8], 2
0x140553672  mov     ebx, 41A3h
0x140553677  jnz     loc_140553703
0x14055367d  mov     ecx, ebx
0x14055367f  mov     esi, 80004005h
0x140553684  call    VmlIsDebugTraceEnabled
0x140553689  test    eax, eax
0x14055368b  jz      short loc_14055370B
0x14055368d  lea     rdx, off_140910150; "Mutual authentication of the network co"...
0x140553694  mov     ecx, ebx
0x140553696  call    VmlDebugTraceEx
0x14055369b  jmp     short loc_14055370B
0x14055369d  test    eax, 1FFF0000h
0x1405536a2  jnz     short loc_1405536B7
0x1405536a4  test    eax, eax
0x1405536a6  jg      short loc_1405536AC
0x1405536a8  mov     esi, eax
0x1405536aa  jmp     short loc_1405536C9
0x1405536ac  movzx   esi, ax
0x1405536af  or      esi, 80070000h
0x1405536b5  jmp     short loc_1405536C9
0x1405536b7  mov     esi, eax
0x1405536b9  test    eax, eax
0x1405536bb  jle     short loc_1405536C9
0x1405536bd  and     esi, 0FFFFFFFh
0x1405536c3  or      esi, 80000000h
0x1405536c9  mov     ebx, 41A3h
0x1405536ce  mov     ecx, ebx
0x1405536d0  call    VmlIsDebugTraceEnabled
0x1405536d5  test    eax, eax
0x1405536d7  jz      short loc_140553703
0x1405536d9  lea     rdx, off_1409102C0; "Failed to create authentication token."
0x1405536e0  jmp     loc_1405533A8
0x1405536e5  mov     ecx, ebx
0x1405536e7  mov     esi, 8007000Eh
0x1405536ec  call    VmlIsDebugTraceEnabled
0x1405536f1  test    eax, eax
0x1405536f3  jz      short loc_14055370B
0x1405536f5  lea     rdx, off_140910350; "Failed to allocate token buffer."
0x1405536fc  mov     ecx, ebx
0x1405536fe  call    VmlDebugTraceEx
0x140553703  test    esi, esi
0x140553705  jns     loc_1405537E9
0x14055370b  mov     r9d, esi
0x14055370e  movzx   ebx, si
0x140553711  mov     ecx, ebx
0x140553713  lea     r8, aU_1; "%%%%%u"
0x14055371a  mov     edi, esi
0x14055371c  mov     r13d, 0BFh
0x140553722  and     edi, 1FFF0000h
0x140553728  mov     r14d, 0EFFFFFFFh
0x14055372e  cmp     edi, 70000h
0x140553734  mov     edx, 10h
0x140553739  cmovnz  ecx, esi
0x14055373c  lea     eax, [rcx-2EE1h]
0x140553742  cmp     eax, r13d
0x140553745  cmovbe  r9d, ecx
0x140553749  lea     rcx, [rbp+70h+var_58]
0x14055374d  and     r9d, r14d
0x140553750  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x140553755  cmp     edi, 70000h
0x14055375b  lea     r8, a0x08x; "0x%08X"
0x140553762  mov     ecx, esi
0x140553764  mov     r9d, esi
0x140553767  cmovz   ecx, ebx
0x14055376a  mov     edx, 10h
  ... truncated ...
```
