# TpmVCardManagerImpl::CheckAccess(void)

- ea: `0x1800261b4`
- end: `0x18002660c`
- name: `?CheckAccess@TpmVCardManagerImpl@@AEAAKXZ`
- size: `1112`
- prototype: `__int64 __fastcall(TpmVCardManagerImpl *this)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800259c8`
- `0x180025b5c`

## callees

- `0x180001ec0`
- `0x1800035a4`
- `0x180003818`
- `0x18000bc48`
- `0x18000c198`
- `0x180016040`
- `0x1800258a0`
- `0x1800258f4`
- `0x180025918`
- `0x180025958`
- `0x180025f80`
- `0x1800261b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002644c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800264be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002652a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002644c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800264be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002652a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002643b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002643b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180026427`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180026427`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002622f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002622f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180026383`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180026383`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800264ad`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180026519`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800264ad`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180026519`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800262f2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800263ca`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800262f2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800263ca`

## string_xrefs

- `0x1800261df`: `TpmVCardManagerImpl::CheckAccess`
- `0x180026273`: `Unable to impersonate the client`
- `0x18002633f`: `Unable to get admin group SID`
- `0x180026417`: `Unable to get network service SID`
- `0x180026488`: `Unable to open current thread token`
- `0x18002655a`: `Unable to check caller service group membership`
- `0x180026594`: `The caller does not have access`

## pseudocode

```c
__int64 __fastcall TpmVCardManagerImpl::CheckAccess(TpmVCardManagerImpl *this)
{
  __int64 v1; // rcx
  int LastError; // edi
  int v3; // r9d
  __int64 v4; // rcx
  _QWORD *v5; // r10
  int v6; // edx
  const char *v7; // rax
  PSID v8; // rsi
  __int64 v9; // rcx
  HANDLE CurrentThread; // rax
  __int64 v11; // rcx
  _QWORD *v12; // r10
  int v13; // edx
  const char *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v18; // [rsp+60h] [rbp-59h] BYREF
  char v19; // [rsp+64h] [rbp-55h] BYREF
  __int16 v20; // [rsp+65h] [rbp-54h]
  PSID pSid; // [rsp+68h] [rbp-51h] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp-49h] BYREF
  WINBOOL IsMember; // [rsp+78h] [rbp-41h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp-39h] BYREF
  int v25; // [rsp+88h] [rbp-31h] BYREF
  _BYTE v26[8]; // [rsp+90h] [rbp-29h] BYREF
  _QWORD *v27; // [rsp+98h] [rbp-21h] BYREF
  _QWORD v28[3]; // [rsp+A0h] [rbp-19h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B8h] [rbp-1h] BYREF
  char v30[40]; // [rsp+C0h] [rbp+7h] BYREF

  v28[0] = v30;
  v18 = 0;
  v28[1] = &v25;
  v28[2] = &v18;
  v25 = 0;
  strcpy(v30, "TpmVCardManagerImpl::CheckAccess");
  lambda_32bdaa063554fd6d017f925d958fb912_::operator()(v28);
  v25 = 1;
  v27 = v28;
  LastError = CoImpersonateClient();
  if ( LastError >= 0 )
  {
    v20 = 258;
    LastError = 5;
    pSid = 0;
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    SidToCheck = 0;
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    {
      WppTraceIndent(v4, 2);
      LastError = GetLastError();
      v18 = LastError;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      v6 = 12;
      v7 = "Unable to get admin group SID";
      goto LABEL_11;
    }
    v8 = pSid;
    if ( pSid )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v26);
      FreeSid(v8);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v26);
    }
    pSid = 0;
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 6u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      WppTraceIndent(v9, 2);
      LastError = GetLastError();
      v18 = LastError;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      v6 = 13;
      v7 = "Unable to get network service SID";
LABEL_11:
      WPP_SF_sDs(
        v5[2],
        v6,
        (unsigned int)WPP_f3132f67e798390788997da23861f0b6_Traceguids,
        (_DWORD)WPP_pszIndent,
        LastError,
        (__int64)v7);
      LastError = v18;
LABEL_43:
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SidToCheck);
      wil::details::ScopeExitFnGuard__lambda_5ce771a75564872c3472b8de38322f77___::operator()(&v19);
      goto LABEL_44;
    }
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    {
      IsMember = 0;
      if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
      {
        if ( IsMember )
          goto LABEL_41;
        if ( CheckTokenMembership(TokenHandle, pSid, &IsMember) )
        {
          if ( !IsMember )
          {
            WppTraceIndent(v16, 2);
            v18 = 5;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_42;
            }
            WPP_SF_sDs(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              (unsigned int)WPP_f3132f67e798390788997da23861f0b6_Traceguids,
              (_DWORD)WPP_pszIndent,
              5,
              (__int64)"The caller does not have access");
          }
          goto LABEL_41;
        }
        WppTraceIndent(v16, 2);
        LastError = GetLastError();
        v18 = LastError;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_42;
        }
        v13 = 16;
        v14 = "Unable to check caller service group membership";
      }
      else
      {
        WppTraceIndent(v15, 2);
        LastError = GetLastError();
        v18 = LastError;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_42;
        }
        v13 = 15;
        v14 = "Unable to check caller admin group membership";
      }
    }
    else
    {
      WppTraceIndent(v11, 2);
      LastError = GetLastError();
      v18 = LastError;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_42;
      }
      v13 = 14;
      v14 = "Unable to open current thread token";
    }
    WPP_SF_sDs(
      v12[2],
      v13,
      (unsigned int)WPP_f3132f67e798390788997da23861f0b6_Traceguids,
      (_DWORD)WPP_pszIndent,
      LastError,
      (__int64)v14);
LABEL_41:
    LastError = v18;
LABEL_42:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_43;
  }
  WppTraceIndent(v1, 2);
  v18 = LastError;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_f3132f67e798390788997da23861f0b6_Traceguids,
      v3,
      LastError,
      (__int64)"Unable to impersonate the client");
    LastError = v18;
  }
LABEL_44:
  WppTraceUnwinder__lambda_32bdaa063554fd6d017f925d958fb912____::_WppTraceUnwinder__lambda_32bdaa063554fd6d017f925d958fb912____(&v27);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800261b4  push    rbp
0x1800261b6  push    rbx
0x1800261b7  push    rsi
0x1800261b8  push    rdi
0x1800261b9  push    r14
0x1800261bb  lea     rbp, [rsp-37h]
0x1800261c0  sub     rsp, 0F0h
0x1800261c7  mov     rax, cs:__security_cookie
0x1800261ce  xor     rax, rsp
0x1800261d1  mov     [rbp+57h+var_28], rax
0x1800261d5  mov     al, byte ptr cs:aTpmvcardmanage_0+20h; ""
0x1800261db  lea     rcx, [rbp+57h+var_70]
0x1800261df  movups  xmm0, xmmword ptr cs:aTpmvcardmanage_0; "TpmVCardManagerImpl::CheckAccess"
0x1800261e6  mov     [rbp+57h+var_50+20h], al
0x1800261e9  lea     rax, [rbp+57h+var_50]
0x1800261ed  movups  xmm1, xmmword ptr cs:aTpmvcardmanage_0+10h; "mpl::CheckAccess"
0x1800261f4  mov     [rbp+57h+var_70], rax
0x1800261f8  xor     r14d, r14d
0x1800261fb  lea     rax, [rbp+57h+var_88]
0x1800261ff  mov     [rbp+57h+var_B0], r14d
0x180026203  mov     [rbp+57h+var_68], rax
0x180026207  lea     rax, [rbp+57h+var_B0]
0x18002620b  mov     [rbp+57h+var_60], rax
0x18002620f  mov     [rbp+57h+var_88], r14d
0x180026213  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x180026217  movups  xmmword ptr [rbp+57h+var_50+10h], xmm1
0x18002621b  call    _lambda_32bdaa063554fd6d017f925d958fb912___operator__
0x180026220  lea     rax, [rbp+57h+var_70]
0x180026224  mov     [rbp+57h+var_88], 1
0x18002622b  mov     [rbp+57h+var_78], rax
0x18002622f  call    cs:__imp_CoImpersonateClient
0x180026235  lea     ebx, [r14+2]
0x180026239  mov     edi, eax
0x18002623b  test    eax, eax
0x18002623d  jns     short loc_18002629E
0x18002623f  mov     edx, ebx
0x180026241  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180026246  mov     [rbp+57h+var_B0], edi
0x180026249  mov     rax, cs:WPP_GLOBAL_Control
0x180026250  lea     rcx, WPP_GLOBAL_Control
0x180026257  cmp     rax, rcx
0x18002625a  jz      loc_1800265E7
0x180026260  test    byte ptr [rax+1Ch], 1
0x180026264  jz      loc_1800265E7
0x18002626a  cmp     [rax+19h], bl
0x18002626d  jb      loc_1800265E7
0x180026273  lea     rcx, aUnableToImpers; "Unable to impersonate the client"
0x18002627a  mov     qword ptr [rsp+110h+nSubAuthority3], rcx
0x18002627f  lea     edx, [rbx+9]
0x180026282  mov     rcx, [rax+10h]
0x180026286  lea     r8, WPP_f3132f67e798390788997da23861f0b6_Traceguids
0x18002628d  mov     [rsp+110h+nSubAuthority2], edi
0x180026291  call    WPP_SF_sds
0x180026296  mov     edi, [rbp+57h+var_B0]
0x180026299  jmp     loc_1800265E7
0x18002629e  lea     rax, [rbp+57h+SidToCheck]
0x1800262a2  mov     [rbp+57h+var_AB], 102h
0x1800262a8  mov     [rsp+110h+pSid], rax; pSid
0x1800262ad  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800262b1  mov     [rsp+110h+nSubAuthority7], r14d; nSubAuthority7
0x1800262b6  mov     edi, 5
0x1800262bb  mov     [rsp+110h+nSubAuthority6], r14d; nSubAuthority6
0x1800262c0  mov     r9d, 220h; nSubAuthority1
0x1800262c6  mov     [rsp+110h+nSubAuthority5], r14d; nSubAuthority5
0x1800262cb  mov     dl, bl; nSubAuthorityCount
0x1800262cd  mov     [rsp+110h+nSubAuthority4], r14d; nSubAuthority4
0x1800262d2  mov     [rsp+110h+nSubAuthority3], r14d; nSubAuthority3
0x1800262d7  lea     r8d, [rdi+1Bh]; nSubAuthority0
0x1800262db  mov     [rsp+110h+nSubAuthority2], r14d; nSubAuthority2
0x1800262e0  mov     [rbp+57h+var_A8], r14
0x1800262e4  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x1800262e8  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800262ee  mov     [rbp+57h+SidToCheck], r14
0x1800262f2  call    cs:__imp_AllocateAndInitializeSid
0x1800262f8  test    eax, eax
0x1800262fa  jnz     short loc_18002636E
0x1800262fc  mov     edx, ebx
0x1800262fe  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180026303  call    cs:__imp_GetLastError
0x180026309  mov     edi, eax
0x18002630b  mov     [rbp+57h+var_B0], eax
0x18002630e  mov     r10, cs:WPP_GLOBAL_Control
0x180026315  lea     rcx, WPP_GLOBAL_Control
0x18002631c  cmp     r10, rcx
0x18002631f  jz      loc_1800265CC
0x180026325  test    byte ptr [r10+1Ch], 1
0x18002632a  jz      loc_1800265CC
0x180026330  cmp     [r10+19h], bl
0x180026334  jb      loc_1800265CC
0x18002633a  mov     edx, 0Ch
0x18002633f  lea     rax, aUnableToGetAdm; "Unable to get admin group SID"
0x180026346  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002634d  lea     r8, WPP_f3132f67e798390788997da23861f0b6_Traceguids
0x180026354  mov     rcx, [r10+10h]
0x180026358  mov     qword ptr [rsp+110h+nSubAuthority3], rax
0x18002635d  mov     [rsp+110h+nSubAuthority2], edi
0x180026361  call    WPP_SF_sDs
0x180026366  mov     edi, [rbp+57h+var_B0]
0x180026369  jmp     loc_1800265CC
0x18002636e  mov     rsi, [rbp+57h+var_A8]
0x180026372  test    rsi, rsi
0x180026375  jz      short loc_180026392
0x180026377  lea     rcx, [rbp+57h+var_80]; this
0x18002637b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180026380  mov     rcx, rsi; pSid
0x180026383  call    cs:__imp_FreeSid
0x180026389  lea     rcx, [rbp+57h+var_80]; this
0x18002638d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180026392  lea     rax, [rbp+57h+var_A8]
0x180026396  mov     [rbp+57h+var_A8], r14
0x18002639a  mov     [rsp+110h+pSid], rax; pSid
0x18002639f  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800263a3  mov     [rsp+110h+nSubAuthority7], r14d; nSubAuthority7
0x1800263a8  xor     r9d, r9d; nSubAuthority1
0x1800263ab  mov     [rsp+110h+nSubAuthority6], r14d; nSubAuthority6
0x1800263b0  mov     dl, 1; nSubAuthorityCount
0x1800263b2  mov     [rsp+110h+nSubAuthority5], r14d; nSubAuthority5
0x1800263b7  mov     [rsp+110h+nSubAuthority4], r14d; nSubAuthority4
0x1800263bc  mov     [rsp+110h+nSubAuthority3], r14d; nSubAuthority3
0x1800263c1  lea     r8d, [r9+6]; nSubAuthority0
0x1800263c5  mov     [rsp+110h+nSubAuthority2], r14d; nSubAuthority2
0x1800263ca  call    cs:__imp_AllocateAndInitializeSid
0x1800263d0  test    eax, eax
0x1800263d2  jnz     short loc_180026423
0x1800263d4  mov     edx, ebx
0x1800263d6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800263db  call    cs:__imp_GetLastError
0x1800263e1  mov     edi, eax
0x1800263e3  mov     [rbp+57h+var_B0], eax
0x1800263e6  mov     r10, cs:WPP_GLOBAL_Control
0x1800263ed  lea     rcx, WPP_GLOBAL_Control
0x1800263f4  cmp     r10, rcx
0x1800263f7  jz      loc_1800265CC
0x1800263fd  test    byte ptr [r10+1Ch], 1
0x180026402  jz      loc_1800265CC
0x180026408  cmp     [r10+19h], bl
0x18002640c  jb      loc_1800265CC
0x180026412  mov     edx, 0Dh
0x180026417  lea     rax, aUnableToGetNet; "Unable to get network service SID"
0x18002641e  jmp     loc_180026346
0x180026423  mov     [rbp+57h+TokenHandle], r14
0x180026427  call    cs:__imp_GetCurrentThread
0x18002642d  xor     r8d, r8d; OpenAsSelf
0x180026430  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180026434  mov     rcx, rax; ThreadHandle
0x180026437  lea     edx, [r8+8]; DesiredAccess
0x18002643b  call    cs:__imp_OpenThreadToken
0x180026441  test    eax, eax
0x180026443  jnz     short loc_18002649D
0x180026445  mov     edx, ebx
0x180026447  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002644c  call    cs:__imp_GetLastError
0x180026452  mov     edi, eax
0x180026454  mov     [rbp+57h+var_B0], eax
0x180026457  mov     r10, cs:WPP_GLOBAL_Control
0x18002645e  lea     rcx, WPP_GLOBAL_Control
0x180026465  cmp     r10, rcx
0x180026468  jz      loc_1800265C3
0x18002646e  test    byte ptr [r10+1Ch], 1
0x180026473  jz      loc_1800265C3
0x180026479  cmp     [r10+19h], bl
0x18002647d  jb      loc_1800265C3
0x180026483  mov     edx, 0Eh
0x180026488  lea     rax, aUnableToOpenCu; "Unable to open current thread token"
0x18002648f  mov     rcx, [r10+10h]
0x180026493  mov     qword ptr [rsp+110h+nSubAuthority3], rax
0x180026498  jmp     loc_1800265A9
0x18002649d  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1800264a1  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800264a5  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800264a9  mov     [rbp+57h+IsMember], r14d
0x1800264ad  call    cs:__imp_CheckTokenMembership
0x1800264b3  test    eax, eax
0x1800264b5  jnz     short loc_180026503
0x1800264b7  mov     edx, ebx
0x1800264b9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800264be  call    cs:__imp_GetLastError
0x1800264c4  mov     edi, eax
0x1800264c6  mov     [rbp+57h+var_B0], eax
0x1800264c9  mov     r10, cs:WPP_GLOBAL_Control
0x1800264d0  lea     rcx, WPP_GLOBAL_Control
0x1800264d7  cmp     r10, rcx
0x1800264da  jz      loc_1800265C3
0x1800264e0  test    byte ptr [r10+1Ch], 1
0x1800264e5  jz      loc_1800265C3
0x1800264eb  cmp     [r10+19h], bl
0x1800264ef  jb      loc_1800265C3
0x1800264f5  mov     edx, 0Fh
0x1800264fa  lea     rax, aUnableToCheckC_0; "Unable to check caller admin group memb"...
0x180026501  jmp     short loc_18002648F
0x180026503  cmp     [rbp+57h+IsMember], r14d
0x180026507  jnz     loc_1800265C0
0x18002650d  mov     rdx, [rbp+57h+var_A8]; SidToCheck
0x180026511  lea     r8, [rbp+57h+IsMember]; IsMember
0x180026515  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180026519  call    cs:__imp_CheckTokenMembership
0x18002651f  test    eax, eax
0x180026521  jnz     short loc_180026566
0x180026523  mov     edx, ebx
0x180026525  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002652a  call    cs:__imp_GetLastError
0x180026530  mov     edi, eax
0x180026532  mov     [rbp+57h+var_B0], eax
0x180026535  mov     r10, cs:WPP_GLOBAL_Control
0x18002653c  lea     rcx, WPP_GLOBAL_Control
0x180026543  cmp     r10, rcx
0x180026546  jz      short loc_1800265C3
0x180026548  test    byte ptr [r10+1Ch], 1
0x18002654d  jz      short loc_1800265C3
0x18002654f  cmp     [r10+19h], bl
0x180026553  jb      short loc_1800265C3
0x180026555  mov     edx, 10h
0x18002655a  lea     rax, aUnableToCheckC; "Unable to check caller service group me"...
0x180026561  jmp     loc_18002648F
0x180026566  cmp     [rbp+57h+IsMember], r14d
0x18002656a  jnz     short loc_1800265C0
0x18002656c  mov     edx, ebx
0x18002656e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180026573  mov     [rbp+57h+var_B0], edi
0x180026576  mov     rax, cs:WPP_GLOBAL_Control
0x18002657d  lea     rcx, WPP_GLOBAL_Control
0x180026584  cmp     rax, rcx
0x180026587  jz      short loc_1800265C3
0x180026589  test    byte ptr [rax+1Ch], 1
0x18002658d  jz      short loc_1800265C3
0x18002658f  cmp     [rax+19h], bl
0x180026592  jb      short loc_1800265C3
0x180026594  lea     rcx, aTheCallerDoesN; "The caller does not have access"
0x18002659b  mov     edx, 11h
0x1800265a0  mov     qword ptr [rsp+110h+nSubAuthority3], rcx
0x1800265a5  mov     rcx, [rax+10h]
0x1800265a9  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800265b0  lea     r8, WPP_f3132f67e798390788997da23861f0b6_Traceguids
0x1800265b7  mov     [rsp+110h+nSubAuthority2], edi
0x1800265bb  call    WPP_SF_sDs
0x1800265c0  mov     edi, [rbp+57h+var_B0]
0x1800265c3  lea     rcx, [rbp+57h+TokenHandle]
0x1800265c7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800265cc  lea     rcx, [rbp+57h+var_A8]
0x1800265d0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800265d5  lea     rcx, [rbp+57h+SidToCheck]
0x1800265d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800265de  lea     rcx, [rbp+57h+var_AC]
0x1800265e2  call    wil__details__ScopeExitFnGuard__lambda_5ce771a75564872c3472b8de38322f77_____operator__
0x1800265e7  lea     rcx, [rbp+57h+var_78]
0x1800265eb  call    WppTraceUnwinder__lambda_32bdaa063554fd6d017f925d958fb912_______WppTraceUnwinder__lambda_32bdaa063554fd6d017f925d958fb912____
0x1800265f0  mov     eax, edi
0x1800265f2  mov     rcx, [rbp+57h+var_28]
0x1800265f6  xor     rcx, rsp; StackCookie
0x1800265f9  call    __security_check_cookie
0x1800265fe  add     rsp, 0F0h
0x180026605  pop     r14
0x180026607  pop     rdi
0x180026608  pop     rsi
0x180026609  pop     rbx
0x18002660a  pop     rbp
0x18002660b  retn
```
