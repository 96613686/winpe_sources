# _CertifyServerIdentity

- ea: `0x18006e800`
- end: `0x18006ed29`
- name: `_CertifyServerIdentity`
- size: `1321`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, int, int, int, int, int, int, int, int, int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int, DWORD dwLevelId, BOOL *)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180009700`
- `0x1800116b8`
- `0x180011954`
- `0x180012dd0`
- `0x180025730`
- `0x180025910`
- `0x180028108`
- `0x18002834c`
- `0x1800297e0`
- `0x18002ba28`
- `0x180034540`
- `0x1800501cc`
- `0x18006e800`
- `0x1800706b0`
- `0x18007a030`
- `0x18007e3d4`
- `0x1800a228c`
- `0x1800b3bac`
- `0x1800b4890`
- `0x1800c3784`
- `0x1800cb210`
- `0x1800ee274`
- `0x1800ef3bc`
- `0x1800ef93c`

## import_xrefs

- `ntdll!NtClose` at `0x18006eb41`
- `ntdll!NtClose` at `0x18006eb64`
- `ntdll!NtClose` at `0x18006eb41`
- `ntdll!NtClose` at `0x18006eb64`
- `ntdll!RtlIsMultiSessionSku` at `0x18006ec8c`
- `ntdll!RtlIsMultiSessionSku` at `0x18006ec8c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18006e962`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18006e962`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCreateLevel` at `0x18006eafb`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCreateLevel` at `0x18006eafb`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCloseLevel` at `0x18006eb32`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCloseLevel` at `0x18006eb32`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferComputeTokenFromLevel` at `0x18006eb26`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferComputeTokenFromLevel` at `0x18006eb26`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQuerySessionVirtualAccountToken` at `0x18006e9e0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQuerySessionVirtualAccountToken` at `0x18006e9e0`

## string_xrefs

- `0x18006e8ef`: `onecore\com\combase\rpcss\olescm\launchk.cxx`
- `0x18006e940`: `onecore\com\combase\rpcss\olescm\launchk.cxx`
- `0x18006ea35`: `onecore\com\combase\rpcss\olescm\launchk.cxx`
- `0x18006ea7c`: `onecore\com\combase\rpcss\olescm\launchk.cxx`
- `0x18006ec44`: `onecore\com\combase\rpcss\olescm\launchk.cxx`
- `0x18006ec62`: `Failed to compare actual and expected tokens: AppID:%ws (RunAs Domain:%ws User:%ws) hr:%!HRESULT!`

## pseudocode

```c
__int64 __fastcall CertifyServerIdentity(
        RPC_BINDING_HANDLE BindingHandle,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        unsigned __int16 *a11,
        unsigned __int16 *a12,
        unsigned __int16 *a13,
        int a14,
        DWORD dwLevelId,
        BOOL *a16)
{
  unsigned int v16; // edi
  int v21; // ecx
  unsigned int v23; // eax
  unsigned int v24; // ebx
  CToken *v25; // rbx
  int TokenIntegrityLevel; // eax
  unsigned int SessionId; // r13d
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  int v31; // eax
  BOOL v32; // eax
  BOOL *v33; // rdi
  BOOL v34; // eax
  SAFER_LEVEL_HANDLE v35; // rcx
  BOOL v36; // eax
  struct CToken *v37; // rdx
  unsigned __int16 *v38; // rbx
  int v39; // eax
  int v40; // r9d
  struct CToken *v41; // rdx
  int v42; // r8d
  unsigned int lpReserved; // [rsp+20h] [rbp-58h]
  HANDLE InAccessToken; // [rsp+50h] [rbp-28h] BYREF
  CToken *v45; // [rsp+58h] [rbp-20h] BYREF
  SAFER_LEVEL_HANDLE pLevelHandle; // [rsp+60h] [rbp-18h] BYREF
  void *OutAccessToken; // [rsp+68h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v16 = 0;
  InAccessToken = 0;
  if ( a3 && !a2 || (a4 || a5) && (!a2 || (a4 || a5) && !a3) )
    return 5;
  if ( a6 )
  {
    if ( !a3 || !a4 && !a5 )
      return 5;
    if ( !a2 )
      return 5;
    v21 = a8;
    if ( a8 )
      return 5;
  }
  else
  {
    v21 = a8;
    if ( a8 && (!a3 || a4 || a5 || !a2) )
      return 5;
  }
  if ( a9 && (a3 || a4 || a5 || a2 || a6 || v21) || a7 && !a6 )
    return 5;
  v45 = 0;
  v23 = LookupOrCreateTokenForRPCClient(BindingHandle, 0, &v45, 0);
  if ( !v23 )
  {
    v25 = v45;
    if ( a10 )
    {
      pLevelHandle = 0;
      TokenIntegrityLevel = CToken::GetTokenIntegrityLevel(v45, (struct _TOKEN_MANDATORY_LABEL **)&pLevelHandle);
      v16 = TokenIntegrityLevel;
      if ( TokenIntegrityLevel < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7D3,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launchk.cxx",
          (const char *)(unsigned int)TokenIntegrityLevel,
          lpReserved);
LABEL_67:
        wil::com_ptr_t<CToken,wil::err_returncode_policy>::~com_ptr_t<CToken,wil::err_returncode_policy>(&v45);
        return v16;
      }
      if ( *GetSidSubAuthority(*(PSID *)pLevelHandle, 0) <= 0x2000 )
      {
        v16 = 0;
        *a16 = 0;
        goto LABEL_67;
      }
      v16 = 0;
    }
    if ( a2 )
    {
      SessionId = CToken::GetSessionId(v25);
      if ( (int)CSessionUserToken::GetOrCreateUserTokenForSession(SessionId, &InAccessToken) < 0 )
        GetUserTokenForSession(SessionId, &InAccessToken);
    }
    else if ( a9 )
    {
      SessionId = CToken::GetSessionId(v25);
      if ( (unsigned __int8)IsUMgrQueryUserContextPresent() )
      {
        v31 = UMgrQuerySessionVirtualAccountToken(SessionId, &InAccessToken);
        v30 = (unsigned int)v31;
        if ( v31 < 0 )
        {
          v29 = (unsigned int)dword_18014E4B8;
          if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8) )
            ComTraceMessageT<long>(
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launchk.cxx",
              (unsigned int)"_CertifyServerIdentity",
              2032,
              0,
              (__int64)L"%!HRESULT!",
              v30);
        }
      }
      else if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        ComTraceMessageT<>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launchk.cxx",
          (unsigned int)"_CertifyServerIdentity",
          2040,
          0,
          (__int64)L"Session virtual account requested in a SKU that does not support the feature");
      }
    }
    else
    {
      SessionId = -1;
      InAccessToken = GetRunAsToken(0, a11, a12, a13, 0, 0);
    }
    if ( !InAccessToken )
    {
      *a16 = 0;
LABEL_65:
      if ( InAccessToken )
        NtClose(InAccessToken);
      goto LABEL_67;
    }
    if ( a14 && (unsigned __int8)IsSaferCloseLevelPresent(v29, v28, v30) )
    {
      pLevelHandle = 0;
      OutAccessToken = 0;
      v32 = SaferCreateLevel(1u, dwLevelId, 1u, &pLevelHandle, 0);
      v33 = a16;
      *a16 = v32;
      if ( v32 )
      {
        v34 = SaferComputeTokenFromLevel(pLevelHandle, InAccessToken, &OutAccessToken, 0, 0);
        v35 = pLevelHandle;
        *a16 = v34;
        SaferCloseLevel(v35);
      }
      if ( *a16 )
      {
        NtClose(InAccessToken);
        InAccessToken = OutAccessToken;
        v36 = *a16;
      }
      else
      {
        v36 = 0;
      }
      if ( !v36 )
        goto LABEL_64;
    }
    else
    {
      v33 = a16;
      *a16 = 1;
    }
    if ( a7 )
    {
      v37 = v25;
      v38 = a11;
      v39 = CertifyPerAppBrokerServer(a11, v37, SessionId, a4 != 0);
LABEL_73:
      v42 = v39;
      goto LABEL_77;
    }
    if ( a8 )
    {
      v41 = v25;
      v38 = a11;
      v39 = CertifyServerWithDesktopWinRTBrokerClaim(a11, v41, SessionId);
      goto LABEL_73;
    }
    if ( a9 )
    {
      v42 = CToken::CompareToken(v25, InAccessToken);
LABEL_76:
      v38 = a11;
LABEL_77:
      if ( v42 )
      {
        *v33 = 0;
        v16 = 0;
        if ( v42 < 0 && (dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
          ComTraceMessageT<unsigned short *,unsigned short const *,unsigned short const *,long>(
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launchk.cxx",
            (unsigned int)"_CertifyServerIdentity",
            2190,
            v40,
            (__int64)L"Failed to compare actual and expected tokens: AppID:%ws (RunAs Domain:%ws User:%ws) hr:%!HRESULT!",
            v38,
            a12,
            a13,
            v42);
        goto LABEL_65;
      }
      goto LABEL_64;
    }
    if ( a3 )
    {
      if ( (a4 || a5) && !(unsigned __int8)RtlIsMultiSessionSku() )
      {
        v42 = !CToken::IsFullTrustInteractiveUser(v25);
        goto LABEL_76;
      }
      v42 = CToken::CompareToken(v25, InAccessToken);
      if ( v42 != 1 )
        goto LABEL_76;
      TraceInteractiveUserUnmodifiedLogonTokenMismatch(a11, InAccessToken, v25);
    }
    else
    {
      v42 = CToken::CompareTokenIdentity(v25, InAccessToken);
      if ( v42 != 1 )
        goto LABEL_76;
      TraceTokenIdentityMismatch(a11, a12, a13, InAccessToken, v25);
    }
    *v33 = 0;
LABEL_64:
    v16 = 0;
    goto LABEL_65;
  }
  v24 = wil::details::in1diag3::Log_Win32(
          retaddr,
          (void *)0x7CB,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launchk.cxx",
          (const char *)v23,
          lpReserved);
  if ( v45 )
    CToken::Release(v45);
  return v24;
}

```

## disassembly

```asm
0x18006e800  push    rbp
0x18006e802  push    rbx
0x18006e803  push    rsi
0x18006e804  push    rdi
0x18006e805  push    r12
0x18006e807  push    r13
0x18006e809  push    r14
0x18006e80b  push    r15
0x18006e80d  mov     rbp, rsp
0x18006e810  sub     rsp, 78h
0x18006e814  xor     edi, edi
0x18006e816  mov     r14d, r9d
0x18006e819  mov     [rbp+InAccessToken], rdi
0x18006e81d  mov     r12d, r8d
0x18006e820  mov     esi, edx
0x18006e822  mov     r10, rcx
0x18006e825  test    r8d, r8d
0x18006e828  jz      short loc_18006E82E
0x18006e82a  test    edx, edx
0x18006e82c  jz      short loc_18006E873
0x18006e82e  mov     r15d, [rbp+arg_20]
0x18006e832  test    r14d, r14d
0x18006e835  jnz     short loc_18006E83C
0x18006e837  test    r15d, r15d
0x18006e83a  jz      short loc_18006E84F
0x18006e83c  test    esi, esi
0x18006e83e  jz      short loc_18006E873
0x18006e840  test    r14d, r14d
0x18006e843  jnz     short loc_18006E84A
0x18006e845  test    r15d, r15d
0x18006e848  jz      short loc_18006E84F
0x18006e84a  test    r12d, r12d
0x18006e84d  jz      short loc_18006E873
0x18006e84f  mov     eax, [rbp+arg_28]
0x18006e852  test    eax, eax
0x18006e854  jz      short loc_18006E889
0x18006e856  test    r12d, r12d
0x18006e859  jz      short loc_18006E873
0x18006e85b  test    r14d, r14d
0x18006e85e  jnz     short loc_18006E865
0x18006e860  test    r15d, r15d
0x18006e863  jz      short loc_18006E873
0x18006e865  test    esi, esi
0x18006e867  jz      short loc_18006E873
0x18006e869  mov     ecx, [rbp+arg_38]
0x18006e86f  test    ecx, ecx
0x18006e871  jz      short loc_18006E8A6
0x18006e873  mov     eax, 5
0x18006e878  add     rsp, 78h
0x18006e87c  pop     r15
0x18006e87e  pop     r14
0x18006e880  pop     r13
0x18006e882  pop     r12
0x18006e884  pop     rdi
0x18006e885  pop     rsi
0x18006e886  pop     rbx
0x18006e887  pop     rbp
0x18006e888  retn
0x18006e889  mov     ecx, [rbp+arg_38]
0x18006e88f  test    ecx, ecx
0x18006e891  jz      short loc_18006E8A6
0x18006e893  test    r12d, r12d
0x18006e896  jz      short loc_18006E873
0x18006e898  test    r14d, r14d
0x18006e89b  jnz     short loc_18006E873
0x18006e89d  test    r15d, r15d
0x18006e8a0  jnz     short loc_18006E873
0x18006e8a2  test    esi, esi
0x18006e8a4  jz      short loc_18006E873
0x18006e8a6  cmp     [rbp+arg_40], edi
0x18006e8ac  jz      short loc_18006E8C9
0x18006e8ae  test    r12d, r12d
0x18006e8b1  jnz     short loc_18006E873
0x18006e8b3  test    r14d, r14d
0x18006e8b6  jnz     short loc_18006E873
0x18006e8b8  test    r15d, r15d
0x18006e8bb  jnz     short loc_18006E873
0x18006e8bd  test    esi, esi
0x18006e8bf  jnz     short loc_18006E873
0x18006e8c1  test    eax, eax
0x18006e8c3  jnz     short loc_18006E873
0x18006e8c5  test    ecx, ecx
0x18006e8c7  jnz     short loc_18006E873
0x18006e8c9  cmp     [rbp+arg_30], edi
0x18006e8cc  jz      short loc_18006E8D2
0x18006e8ce  test    eax, eax
0x18006e8d0  jz      short loc_18006E873
0x18006e8d2  xor     r9d, r9d; int *
0x18006e8d5  mov     [rbp+var_20], rdi
0x18006e8d9  lea     r8, [rbp+var_20]; struct CToken **
0x18006e8dd  xor     edx, edx; int
0x18006e8df  mov     rcx, r10; BindingHandle
0x18006e8e2  call    ?LookupOrCreateTokenForRPCClient@@YAJPEAXHPEAPEAVCToken@@PEAH@Z; LookupOrCreateTokenForRPCClient(void *,int,CToken * *,int *)
0x18006e8e7  test    eax, eax
0x18006e8e9  jz      short loc_18006E91A
0x18006e8eb  mov     rcx, [rbp+40h]; this
0x18006e8ef  lea     r8, aOnecoreComComb_70; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18006e8f6  mov     r9d, eax; char *
0x18006e8f9  mov     edx, 7CBh; void *
0x18006e8fe  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18006e903  mov     rcx, [rbp+var_20]; this
0x18006e907  mov     ebx, eax
0x18006e909  test    rcx, rcx
0x18006e90c  jz      short loc_18006E913
0x18006e90e  call    ?Release@CToken@@UEAAKXZ; CToken::Release(void)
0x18006e913  mov     eax, ebx
0x18006e915  jmp     loc_18006E878
0x18006e91a  mov     rbx, [rbp+var_20]
0x18006e91e  cmp     [rbp+arg_48], edi
0x18006e924  jz      short loc_18006E986
0x18006e926  lea     rdx, [rbp+pLevelHandle]; struct _TOKEN_MANDATORY_LABEL **
0x18006e92a  mov     [rbp+pLevelHandle], rdi
0x18006e92e  mov     rcx, rbx; this
0x18006e931  call    ?GetTokenIntegrityLevel@CToken@@UEAAJPEAPEAU_TOKEN_MANDATORY_LABEL@@@Z; CToken::GetTokenIntegrityLevel(_TOKEN_MANDATORY_LABEL * *)
0x18006e936  mov     edi, eax
0x18006e938  test    eax, eax
0x18006e93a  jns     short loc_18006E959
0x18006e93c  mov     rcx, [rbp+40h]; this
0x18006e940  lea     r8, aOnecoreComComb_70; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18006e947  mov     r9d, eax; char *
0x18006e94a  mov     edx, 7D3h; void *
0x18006e94f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e954  jmp     loc_18006EB6A
0x18006e959  mov     rcx, [rbp+pLevelHandle]
0x18006e95d  xor     edx, edx; nSubAuthority
0x18006e95f  mov     rcx, [rcx]; pSid
0x18006e962  call    cs:__imp_GetSidSubAuthority
0x18006e968  cmp     dword ptr [rax], 2000h
0x18006e96e  ja      short loc_18006E984
0x18006e970  mov     rax, [rbp+arg_78]
0x18006e977  xor     edi, edi
0x18006e979  mov     dword ptr [rax], 0
0x18006e97f  jmp     loc_18006EB6A
0x18006e984  xor     edi, edi
0x18006e986  test    esi, esi
0x18006e988  jz      short loc_18006E9B9
0x18006e98a  mov     rcx, rbx; this
0x18006e98d  call    ?GetSessionId@CToken@@QEAAKXZ; CToken::GetSessionId(void)
0x18006e992  lea     rdx, [rbp+InAccessToken]; void **
0x18006e996  mov     ecx, eax; unsigned int
0x18006e998  mov     r13d, eax
0x18006e99b  call    ?GetOrCreateUserTokenForSession@CSessionUserToken@@SAJKPEAPEAX@Z; CSessionUserToken::GetOrCreateUserTokenForSession(ulong,void * *)
0x18006e9a0  test    eax, eax
0x18006e9a2  jns     loc_18006EAB7
0x18006e9a8  lea     rdx, [rbp+InAccessToken]; void **
0x18006e9ac  mov     ecx, r13d; unsigned int
0x18006e9af  call    ?GetUserTokenForSession@@YAJKPEAPEAX@Z; GetUserTokenForSession(ulong,void * *)
0x18006e9b4  jmp     loc_18006EAB7
0x18006e9b9  cmp     [rbp+arg_40], edi
0x18006e9bf  jz      loc_18006EA8A
0x18006e9c5  mov     rcx, rbx; this
0x18006e9c8  call    ?GetSessionId@CToken@@QEAAKXZ; CToken::GetSessionId(void)
0x18006e9cd  mov     r13d, eax
0x18006e9d0  call    IsUMgrQueryUserContextPresent
0x18006e9d5  test    al, al
0x18006e9d7  jz      short loc_18006EA43
0x18006e9d9  lea     rdx, [rbp+InAccessToken]
0x18006e9dd  mov     ecx, r13d
0x18006e9e0  call    cs:__imp_UMgrQuerySessionVirtualAccountToken
0x18006e9e6  mov     r8d, eax
0x18006e9e9  test    eax, eax
0x18006e9eb  jns     loc_18006EAB7
0x18006e9f1  mov     ecx, cs:dword_18014E4B8
0x18006e9f7  test    ecx, ecx
0x18006e9f9  jnz     short loc_18006EA14
0x18006e9fb  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18006ea01  jz      loc_18006EAB7
0x18006ea07  call    IsWppLevelEnabled
0x18006ea0c  test    al, al
0x18006ea0e  jz      loc_18006EAB7
0x18006ea14  mov     dword ptr [rsp+78h+var_50], r8d
0x18006ea19  lea     rax, aHresult; "%!HRESULT!"
0x18006ea20  mov     r8d, 7F0h
0x18006ea26  mov     [rsp+78h+lpReserved], rax
0x18006ea2b  xor     r9d, r9d
0x18006ea2e  lea     rdx, aCertifyserveri; "_CertifyServerIdentity"
0x18006ea35  lea     rcx, aOnecoreComComb_70; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18006ea3c  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18006ea41  jmp     short loc_18006EAB7
0x18006ea43  mov     eax, cs:dword_18014E4B8
0x18006ea49  test    eax, eax
0x18006ea4b  jnz     short loc_18006EA60
0x18006ea4d  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18006ea53  jz      short loc_18006EAB7
0x18006ea55  xor     ecx, ecx
0x18006ea57  call    IsWppLevelEnabled
0x18006ea5c  test    al, al
0x18006ea5e  jz      short loc_18006EAB7
0x18006ea60  lea     rax, aSessionVirtual; "Session virtual account requested in a "...
0x18006ea67  xor     r9d, r9d
0x18006ea6a  mov     r8d, 7F8h
0x18006ea70  mov     [rsp+78h+lpReserved], rax
0x18006ea75  lea     rdx, aCertifyserveri; "_CertifyServerIdentity"
0x18006ea7c  lea     rcx, aOnecoreComComb_70; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18006ea83  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x18006ea88  jmp     short loc_18006EAB7
0x18006ea8a  mov     r9, [rbp+arg_60]; unsigned __int16 *
0x18006ea91  or      r13d, 0FFFFFFFFh
0x18006ea95  mov     r8, [rbp+arg_58]; unsigned __int16 *
0x18006ea9c  xor     ecx, ecx; unsigned int
0x18006ea9e  mov     rdx, [rbp+arg_50]; unsigned __int16 *
0x18006eaa5  mov     [rsp+78h+var_50], rdi; void *
0x18006eaaa  mov     dword ptr [rsp+78h+lpReserved], edi; int
0x18006eaae  call    ?GetRunAsToken@@YAPEAXKPEAG00HPEAX@Z; GetRunAsToken(ulong,ushort *,ushort *,ushort *,int,void *)
0x18006eab3  mov     [rbp+InAccessToken], rax
0x18006eab7  cmp     [rbp+InAccessToken], rdi
0x18006eabb  jz      loc_18006ED1B
0x18006eac1  cmp     [rbp+arg_68], edi
0x18006eac7  jz      loc_18006EB7A
0x18006eacd  call    IsSaferCloseLevelPresent
0x18006ead2  test    al, al
0x18006ead4  jz      loc_18006EB7A
0x18006eada  mov     edx, [rbp+dwLevelId]; dwLevelId
0x18006eae0  lea     r9, [rbp+pLevelHandle]; pLevelHandle
0x18006eae4  mov     esi, 1
0x18006eae9  mov     [rbp+pLevelHandle], rdi
0x18006eaed  mov     r8d, esi; OpenFlags
0x18006eaf0  mov     [rbp+OutAccessToken], rdi
0x18006eaf4  mov     ecx, esi; dwScopeId
0x18006eaf6  mov     [rsp+78h+lpReserved], rdi; lpReserved
0x18006eafb  call    cs:__imp_SaferCreateLevel
0x18006eb01  mov     rdi, [rbp+arg_78]
0x18006eb08  mov     [rdi], eax
0x18006eb0a  test    eax, eax
0x18006eb0c  jz      short loc_18006EB38
0x18006eb0e  mov     rdx, [rbp+InAccessToken]; InAccessToken
0x18006eb12  lea     r8, [rbp+OutAccessToken]; OutAccessToken
0x18006eb16  mov     rcx, [rbp+pLevelHandle]; LevelHandle
0x18006eb1a  xor     r9d, r9d; dwFlags
0x18006eb1d  mov     [rsp+78h+lpReserved], 0; lpReserved
0x18006eb26  call    cs:__imp_SaferComputeTokenFromLevel
0x18006eb2c  mov     rcx, [rbp+pLevelHandle]; hLevelHandle
0x18006eb30  mov     [rdi], eax
0x18006eb32  call    cs:__imp_SaferCloseLevel
0x18006eb38  cmp     dword ptr [rdi], 0
0x18006eb3b  jz      short loc_18006EB53
0x18006eb3d  mov     rcx, [rbp+InAccessToken]; Handle
0x18006eb41  call    cs:__imp_NtClose
0x18006eb47  mov     rax, [rbp+OutAccessToken]
0x18006eb4b  mov     [rbp+InAccessToken], rax
0x18006eb4f  mov     eax, [rdi]
0x18006eb51  jmp     short loc_18006EB55
0x18006eb53  xor     eax, eax
0x18006eb55  test    eax, eax
0x18006eb57  jnz     short loc_18006EB88
0x18006eb59  xor     edi, edi
0x18006eb5b  mov     rcx, [rbp+InAccessToken]; Handle
0x18006eb5f  test    rcx, rcx
0x18006eb62  jz      short loc_18006EB6A
0x18006eb64  call    cs:__imp_NtClose
0x18006eb6a  lea     rcx, [rbp+var_20]
0x18006eb6e  call    ??1?$com_ptr_t@VCToken@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CToken,wil::err_returncode_policy>::~com_ptr_t<CToken,wil::err_returncode_policy>(void)
0x18006eb73  mov     eax, edi
0x18006eb75  jmp     loc_18006E878
0x18006eb7a  mov     rdi, [rbp+arg_78]
0x18006eb81  mov     esi, 1
0x18006eb86  mov     [rdi], esi
0x18006eb88  cmp     [rbp+arg_30], 0
0x18006eb8c  jz      short loc_18006EBAC
0x18006eb8e  test    r14d, r14d
0x18006eb91  mov     rdx, rbx; struct CToken *
0x18006eb94  mov     rbx, [rbp+arg_50]
0x18006eb9b  mov     r8d, r13d; unsigned int
0x18006eb9e  setnz   r9b; bool
0x18006eba2  mov     rcx, rbx; unsigned __int16 *
0x18006eba5  call    ?CertifyPerAppBrokerServer@@YAJPEBGPEAVCToken@@K_N@Z; CertifyPerAppBrokerServer(ushort const *,CToken *,ulong,bool)
0x18006ebaa  jmp     short loc_18006EBCA
0x18006ebac  cmp     [rbp+arg_38], 0
0x18006ebb3  jz      short loc_18006EBCF
0x18006ebb5  mov     rdx, rbx; struct CToken *
0x18006ebb8  mov     r8d, r13d; unsigned int
0x18006ebbb  mov     rbx, [rbp+arg_50]
0x18006ebc2  mov     rcx, rbx; unsigned __int16 *
0x18006ebc5  call    ?CertifyServerWithDesktopWinRTBrokerClaim@@YAJPEBGPEAVCToken@@K@Z; CertifyServerWithDesktopWinRTBrokerClaim(ushort const *,CToken *,ulong)
0x18006ebca  mov     r8d, eax
0x18006ebcd  jmp     short loc_18006EBF2
0x18006ebcf  cmp     [rbp+arg_40], 0
0x18006ebd6  jz      loc_18006EC7D
0x18006ebdc  mov     rdx, [rbp+InAccessToken]; void *
0x18006ebe0  mov     rcx, rbx; this
0x18006ebe3  call    ?CompareToken@CToken@@QEAAJPEAX@Z; CToken::CompareToken(void *)
0x18006ebe8  mov     r8d, eax
0x18006ebeb  mov     rbx, [rbp+arg_50]
0x18006ebf2  test    r8d, r8d
0x18006ebf5  jz      loc_18006EB59
0x18006ebfb  mov     dword ptr [rdi], 0
0x18006ec01  xor     edi, edi
0x18006ec03  test    r8d, r8d
0x18006ec06  jns     loc_18006EB5B
0x18006ec0c  mov     eax, cs:dword_18014E4B8
0x18006ec12  test    eax, eax
0x18006ec14  jnz     short loc_18006EC31
0x18006ec16  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18006ec1c  jz      loc_18006EB5B
0x18006ec22  xor     ecx, ecx
0x18006ec24  call    IsWppLevelEnabled
0x18006ec29  test    al, al
0x18006ec2b  jz      loc_18006EB5B
0x18006ec31  mov     rax, [rbp+arg_60]
0x18006ec38  lea     rdx, aCertifyserveri; "_CertifyServerIdentity"
  ... truncated ...
```
