# _CertifyServerIdentity

- ea: `0x180073020`
- end: `0x18007357a`
- name: `_CertifyServerIdentity`
- size: `1370`
- prototype: `__int64 __usercall@<rax>(RPC_BINDING_HANDLE BindingHandle@<rcx>, int, int, int, int, int, int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int, DWORD dwLevelId, __int64)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a130`
- `0x18000aec4`
- `0x180015618`
- `0x1800158f8`
- `0x180016e7c`
- `0x18001ecf0`
- `0x1800210f8`
- `0x18002faa8`
- `0x18002fcb0`
- `0x180034260`
- `0x1800375e0`
- `0x18004dee8`
- `0x180073020`
- `0x180074dec`
- `0x180076f9c`
- `0x18008172c`
- `0x1800a780c`
- `0x1800b8eac`
- `0x1800b9b90`
- `0x1800c94bc`
- `0x1800d1354`
- `0x1800f5e84`
- `0x1800f7004`
- `0x1800f759c`

## import_xrefs

- `ntdll!NtClose` at `0x180073380`
- `ntdll!NtClose` at `0x1800733a9`
- `ntdll!NtClose` at `0x180073380`
- `ntdll!NtClose` at `0x1800733a9`
- `ntdll!RtlIsMultiSessionSku` at `0x1800734d7`
- `ntdll!RtlIsMultiSessionSku` at `0x1800734d7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180073183`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180073183`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCreateLevel` at `0x180073328`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCreateLevel` at `0x180073328`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCloseLevel` at `0x18007336b`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCloseLevel` at `0x18007336b`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferComputeTokenFromLevel` at `0x180073359`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferComputeTokenFromLevel` at `0x180073359`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQuerySessionVirtualAccountToken` at `0x180073207`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQuerySessionVirtualAccountToken` at `0x180073207`

## string_xrefs

- `0x180073110`: `onecore\com\combase\rpcss\olescm\launchk.cxx`
- `0x180073161`: `onecore\com\combase\rpcss\olescm\launchk.cxx`
- `0x180073262`: `onecore\com\combase\rpcss\olescm\launchk.cxx`
- `0x1800732a9`: `onecore\com\combase\rpcss\olescm\launchk.cxx`
- `0x18007348f`: `onecore\com\combase\rpcss\olescm\launchk.cxx`
- `0x1800734ad`: `Failed to compare actual and expected tokens: AppID:%ws (RunAs Domain:%ws User:%ws) hr:%!HRESULT!`

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
          v29 = (unsigned int)dword_1801574B8;
          if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8) )
            ComTraceMessageT<long>(
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launchk.cxx",
              (unsigned int)"_CertifyServerIdentity",
              2032,
              0,
              (__int64)L"%!HRESULT!",
              v30);
        }
      }
      else if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
        if ( v42 < 0 && (dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
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
0x180073020  push    rbp
0x180073022  push    rbx
0x180073023  push    rsi
0x180073024  push    rdi
0x180073025  push    r12
0x180073027  push    r13
0x180073029  push    r14
0x18007302b  push    r15
0x18007302d  mov     rbp, rsp
0x180073030  sub     rsp, 78h
0x180073034  xor     edi, edi
0x180073036  mov     r14d, r9d
0x180073039  mov     [rbp+InAccessToken], rdi
0x18007303d  mov     r12d, r8d
0x180073040  mov     esi, edx
0x180073042  mov     r10, rcx
0x180073045  test    r8d, r8d
0x180073048  jz      short loc_18007304E
0x18007304a  test    edx, edx
0x18007304c  jz      short loc_180073093
0x18007304e  mov     r15d, [rbp+arg_20]
0x180073052  test    r14d, r14d
0x180073055  jnz     short loc_18007305C
0x180073057  test    r15d, r15d
0x18007305a  jz      short loc_18007306F
0x18007305c  test    esi, esi
0x18007305e  jz      short loc_180073093
0x180073060  test    r14d, r14d
0x180073063  jnz     short loc_18007306A
0x180073065  test    r15d, r15d
0x180073068  jz      short loc_18007306F
0x18007306a  test    r12d, r12d
0x18007306d  jz      short loc_180073093
0x18007306f  mov     eax, [rbp+arg_28]
0x180073072  test    eax, eax
0x180073074  jz      short loc_1800730AA
0x180073076  test    r12d, r12d
0x180073079  jz      short loc_180073093
0x18007307b  test    r14d, r14d
0x18007307e  jnz     short loc_180073085
0x180073080  test    r15d, r15d
0x180073083  jz      short loc_180073093
0x180073085  test    esi, esi
0x180073087  jz      short loc_180073093
0x180073089  mov     ecx, [rbp+arg_38]
0x18007308f  test    ecx, ecx
0x180073091  jz      short loc_1800730C7
0x180073093  mov     eax, 5
0x180073098  add     rsp, 78h
0x18007309c  pop     r15
0x18007309e  pop     r14
0x1800730a0  pop     r13
0x1800730a2  pop     r12
0x1800730a4  pop     rdi
0x1800730a5  pop     rsi
0x1800730a6  pop     rbx
0x1800730a7  pop     rbp
0x1800730a8  retn
0x1800730aa  mov     ecx, [rbp+arg_38]
0x1800730b0  test    ecx, ecx
0x1800730b2  jz      short loc_1800730C7
0x1800730b4  test    r12d, r12d
0x1800730b7  jz      short loc_180073093
0x1800730b9  test    r14d, r14d
0x1800730bc  jnz     short loc_180073093
0x1800730be  test    r15d, r15d
0x1800730c1  jnz     short loc_180073093
0x1800730c3  test    esi, esi
0x1800730c5  jz      short loc_180073093
0x1800730c7  cmp     [rbp+arg_40], edi
0x1800730cd  jz      short loc_1800730EA
0x1800730cf  test    r12d, r12d
0x1800730d2  jnz     short loc_180073093
0x1800730d4  test    r14d, r14d
0x1800730d7  jnz     short loc_180073093
0x1800730d9  test    r15d, r15d
0x1800730dc  jnz     short loc_180073093
0x1800730de  test    esi, esi
0x1800730e0  jnz     short loc_180073093
0x1800730e2  test    eax, eax
0x1800730e4  jnz     short loc_180073093
0x1800730e6  test    ecx, ecx
0x1800730e8  jnz     short loc_180073093
0x1800730ea  cmp     [rbp+arg_30], edi
0x1800730ed  jz      short loc_1800730F3
0x1800730ef  test    eax, eax
0x1800730f1  jz      short loc_180073093
0x1800730f3  xor     r9d, r9d; int *
0x1800730f6  mov     [rbp+var_20], rdi
0x1800730fa  lea     r8, [rbp+var_20]; struct CToken **
0x1800730fe  xor     edx, edx; int
0x180073100  mov     rcx, r10; BindingHandle
0x180073103  call    ?LookupOrCreateTokenForRPCClient@@YAJPEAXHPEAPEAVCToken@@PEAH@Z; LookupOrCreateTokenForRPCClient(void *,int,CToken * *,int *)
0x180073108  test    eax, eax
0x18007310a  jz      short loc_18007313B
0x18007310c  mov     rcx, [rbp+40h]; this
0x180073110  lea     r8, aOnecoreComComb_70; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x180073117  mov     r9d, eax; char *
0x18007311a  mov     edx, 7CBh; void *
0x18007311f  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180073124  mov     rcx, [rbp+var_20]; this
0x180073128  mov     ebx, eax
0x18007312a  test    rcx, rcx
0x18007312d  jz      short loc_180073134
0x18007312f  call    ?Release@CToken@@UEAAKXZ; CToken::Release(void)
0x180073134  mov     eax, ebx
0x180073136  jmp     loc_180073098
0x18007313b  mov     rbx, [rbp+var_20]
0x18007313f  cmp     [rbp+arg_48], edi
0x180073145  jz      short loc_1800731AD
0x180073147  lea     rdx, [rbp+pLevelHandle]; struct _TOKEN_MANDATORY_LABEL **
0x18007314b  mov     [rbp+pLevelHandle], rdi
0x18007314f  mov     rcx, rbx; this
0x180073152  call    ?GetTokenIntegrityLevel@CToken@@UEAAJPEAPEAU_TOKEN_MANDATORY_LABEL@@@Z; CToken::GetTokenIntegrityLevel(_TOKEN_MANDATORY_LABEL * *)
0x180073157  mov     edi, eax
0x180073159  test    eax, eax
0x18007315b  jns     short loc_18007317A
0x18007315d  mov     rcx, [rbp+40h]; this
0x180073161  lea     r8, aOnecoreComComb_70; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x180073168  mov     r9d, eax; char *
0x18007316b  mov     edx, 7D3h; void *
0x180073170  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073175  jmp     loc_1800733B5
0x18007317a  mov     rcx, [rbp+pLevelHandle]
0x18007317e  xor     edx, edx; nSubAuthority
0x180073180  mov     rcx, [rcx]; pSid
0x180073183  call    cs:__imp_GetSidSubAuthority
0x18007318a  nop     dword ptr [rax+rax+00h]
0x18007318f  cmp     dword ptr [rax], 2000h
0x180073195  ja      short loc_1800731AB
0x180073197  mov     rax, [rbp+arg_78]
0x18007319e  xor     edi, edi
0x1800731a0  mov     dword ptr [rax], 0
0x1800731a6  jmp     loc_1800733B5
0x1800731ab  xor     edi, edi
0x1800731ad  test    esi, esi
0x1800731af  jz      short loc_1800731E0
0x1800731b1  mov     rcx, rbx; this
0x1800731b4  call    ?GetSessionId@CToken@@QEAAKXZ; CToken::GetSessionId(void)
0x1800731b9  lea     rdx, [rbp+InAccessToken]; void **
0x1800731bd  mov     ecx, eax; unsigned int
0x1800731bf  mov     r13d, eax
0x1800731c2  call    ?GetOrCreateUserTokenForSession@CSessionUserToken@@SAJKPEAPEAX@Z; CSessionUserToken::GetOrCreateUserTokenForSession(ulong,void * *)
0x1800731c7  test    eax, eax
0x1800731c9  jns     loc_1800732E4
0x1800731cf  lea     rdx, [rbp+InAccessToken]; void **
0x1800731d3  mov     ecx, r13d; unsigned int
0x1800731d6  call    ?GetUserTokenForSession@@YAJKPEAPEAX@Z; GetUserTokenForSession(ulong,void * *)
0x1800731db  jmp     loc_1800732E4
0x1800731e0  cmp     [rbp+arg_40], edi
0x1800731e6  jz      loc_1800732B7
0x1800731ec  mov     rcx, rbx; this
0x1800731ef  call    ?GetSessionId@CToken@@QEAAKXZ; CToken::GetSessionId(void)
0x1800731f4  mov     r13d, eax
0x1800731f7  call    IsUMgrQueryUserContextPresent
0x1800731fc  test    al, al
0x1800731fe  jz      short loc_180073270
0x180073200  lea     rdx, [rbp+InAccessToken]
0x180073204  mov     ecx, r13d
0x180073207  call    cs:__imp_UMgrQuerySessionVirtualAccountToken
0x18007320e  nop     dword ptr [rax+rax+00h]
0x180073213  mov     r8d, eax
0x180073216  test    eax, eax
0x180073218  jns     loc_1800732E4
0x18007321e  mov     ecx, cs:dword_1801574B8
0x180073224  test    ecx, ecx
0x180073226  jnz     short loc_180073241
0x180073228  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18007322e  jz      loc_1800732E4
0x180073234  call    IsWppLevelEnabled
0x180073239  test    al, al
0x18007323b  jz      loc_1800732E4
0x180073241  mov     dword ptr [rsp+78h+var_50], r8d
0x180073246  lea     rax, aHresult; "%!HRESULT!"
0x18007324d  mov     r8d, 7F0h
0x180073253  mov     [rsp+78h+lpReserved], rax
0x180073258  xor     r9d, r9d
0x18007325b  lea     rdx, aCertifyserveri; "_CertifyServerIdentity"
0x180073262  lea     rcx, aOnecoreComComb_70; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x180073269  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18007326e  jmp     short loc_1800732E4
0x180073270  mov     eax, cs:dword_1801574B8
0x180073276  test    eax, eax
0x180073278  jnz     short loc_18007328D
0x18007327a  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x180073280  jz      short loc_1800732E4
0x180073282  xor     ecx, ecx
0x180073284  call    IsWppLevelEnabled
0x180073289  test    al, al
0x18007328b  jz      short loc_1800732E4
0x18007328d  lea     rax, aSessionVirtual; "Session virtual account requested in a "...
0x180073294  xor     r9d, r9d
0x180073297  mov     r8d, 7F8h
0x18007329d  mov     [rsp+78h+lpReserved], rax
0x1800732a2  lea     rdx, aCertifyserveri; "_CertifyServerIdentity"
0x1800732a9  lea     rcx, aOnecoreComComb_70; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x1800732b0  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x1800732b5  jmp     short loc_1800732E4
0x1800732b7  mov     r9, [rbp+arg_60]; unsigned __int16 *
0x1800732be  or      r13d, 0FFFFFFFFh
0x1800732c2  mov     r8, [rbp+arg_58]; unsigned __int16 *
0x1800732c9  xor     ecx, ecx; unsigned int
0x1800732cb  mov     rdx, [rbp+arg_50]; unsigned __int16 *
0x1800732d2  mov     [rsp+78h+var_50], rdi; void *
0x1800732d7  mov     dword ptr [rsp+78h+lpReserved], edi; int
0x1800732db  call    ?GetRunAsToken@@YAPEAXKPEAG00HPEAX@Z; GetRunAsToken(ulong,ushort *,ushort *,ushort *,int,void *)
0x1800732e0  mov     [rbp+InAccessToken], rax
0x1800732e4  cmp     [rbp+InAccessToken], rdi
0x1800732e8  jz      loc_18007356C
0x1800732ee  cmp     [rbp+arg_68], edi
0x1800732f4  jz      loc_1800733C5
0x1800732fa  call    IsSaferCloseLevelPresent
0x1800732ff  test    al, al
0x180073301  jz      loc_1800733C5
0x180073307  mov     edx, [rbp+dwLevelId]; dwLevelId
0x18007330d  lea     r9, [rbp+pLevelHandle]; pLevelHandle
0x180073311  mov     esi, 1
0x180073316  mov     [rbp+pLevelHandle], rdi
0x18007331a  mov     r8d, esi; OpenFlags
0x18007331d  mov     [rbp+OutAccessToken], rdi
0x180073321  mov     ecx, esi; dwScopeId
0x180073323  mov     [rsp+78h+lpReserved], rdi; lpReserved
0x180073328  call    cs:__imp_SaferCreateLevel
0x18007332f  nop     dword ptr [rax+rax+00h]
0x180073334  mov     rdi, [rbp+arg_78]
0x18007333b  mov     [rdi], eax
0x18007333d  test    eax, eax
0x18007333f  jz      short loc_180073377
0x180073341  mov     rdx, [rbp+InAccessToken]; InAccessToken
0x180073345  lea     r8, [rbp+OutAccessToken]; OutAccessToken
0x180073349  mov     rcx, [rbp+pLevelHandle]; LevelHandle
0x18007334d  xor     r9d, r9d; dwFlags
0x180073350  mov     [rsp+78h+lpReserved], 0; lpReserved
0x180073359  call    cs:__imp_SaferComputeTokenFromLevel
0x180073360  nop     dword ptr [rax+rax+00h]
0x180073365  mov     rcx, [rbp+pLevelHandle]; hLevelHandle
0x180073369  mov     [rdi], eax
0x18007336b  call    cs:__imp_SaferCloseLevel
0x180073372  nop     dword ptr [rax+rax+00h]
0x180073377  cmp     dword ptr [rdi], 0
0x18007337a  jz      short loc_180073398
0x18007337c  mov     rcx, [rbp+InAccessToken]; Handle
0x180073380  call    cs:__imp_NtClose
0x180073387  nop     dword ptr [rax+rax+00h]
0x18007338c  mov     rax, [rbp+OutAccessToken]
0x180073390  mov     [rbp+InAccessToken], rax
0x180073394  mov     eax, [rdi]
0x180073396  jmp     short loc_18007339A
0x180073398  xor     eax, eax
0x18007339a  test    eax, eax
0x18007339c  jnz     short loc_1800733D3
0x18007339e  xor     edi, edi
0x1800733a0  mov     rcx, [rbp+InAccessToken]; Handle
0x1800733a4  test    rcx, rcx
0x1800733a7  jz      short loc_1800733B5
0x1800733a9  call    cs:__imp_NtClose
0x1800733b0  nop     dword ptr [rax+rax+00h]
0x1800733b5  lea     rcx, [rbp+var_20]
0x1800733b9  call    ??1?$com_ptr_t@VCToken@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CToken,wil::err_returncode_policy>::~com_ptr_t<CToken,wil::err_returncode_policy>(void)
0x1800733be  mov     eax, edi
0x1800733c0  jmp     loc_180073098
0x1800733c5  mov     rdi, [rbp+arg_78]
0x1800733cc  mov     esi, 1
0x1800733d1  mov     [rdi], esi
0x1800733d3  cmp     [rbp+arg_30], 0
0x1800733d7  jz      short loc_1800733F7
0x1800733d9  test    r14d, r14d
0x1800733dc  mov     rdx, rbx; struct CToken *
0x1800733df  mov     rbx, [rbp+arg_50]
0x1800733e6  mov     r8d, r13d; unsigned int
0x1800733e9  setnz   r9b; bool
0x1800733ed  mov     rcx, rbx; unsigned __int16 *
0x1800733f0  call    ?CertifyPerAppBrokerServer@@YAJPEBGPEAVCToken@@K_N@Z; CertifyPerAppBrokerServer(ushort const *,CToken *,ulong,bool)
0x1800733f5  jmp     short loc_180073415
0x1800733f7  cmp     [rbp+arg_38], 0
0x1800733fe  jz      short loc_18007341A
0x180073400  mov     rdx, rbx; struct CToken *
0x180073403  mov     r8d, r13d; unsigned int
0x180073406  mov     rbx, [rbp+arg_50]
0x18007340d  mov     rcx, rbx; unsigned __int16 *
0x180073410  call    ?CertifyServerWithDesktopWinRTBrokerClaim@@YAJPEBGPEAVCToken@@K@Z; CertifyServerWithDesktopWinRTBrokerClaim(ushort const *,CToken *,ulong)
0x180073415  mov     r8d, eax
0x180073418  jmp     short loc_18007343D
0x18007341a  cmp     [rbp+arg_40], 0
0x180073421  jz      loc_1800734C8
0x180073427  mov     rdx, [rbp+InAccessToken]; void *
0x18007342b  mov     rcx, rbx; this
0x18007342e  call    ?CompareToken@CToken@@QEAAJPEAX@Z; CToken::CompareToken(void *)
0x180073433  mov     r8d, eax
0x180073436  mov     rbx, [rbp+arg_50]
0x18007343d  test    r8d, r8d
0x180073440  jz      loc_18007339E
0x180073446  mov     dword ptr [rdi], 0
0x18007344c  xor     edi, edi
0x18007344e  test    r8d, r8d
0x180073451  jns     loc_1800733A0
0x180073457  mov     eax, cs:dword_1801574B8
0x18007345d  test    eax, eax
0x18007345f  jnz     short loc_18007347C
0x180073461  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
  ... truncated ...
```
