# Microsoft::Diagnostics::HttpSession::HttpSession(Microsoft::Diagnostics::ProxyOptions,unsigned __int64,Microsoft::Diagnostics::HttpTimeouts *)

- ea: `0x180034a94`
- end: `0x180034d8e`
- name: `??0HttpSession@Diagnostics@Microsoft@@QEAA@VProxyOptions@12@_KPEAUHttpTimeouts@12@@Z`
- size: `762`
- prototype: `_QWORD __high(struct Microsoft::Diagnostics::ProxyOptions, unsigned __int64, struct Microsoft::Diagnostics::HttpTimeouts *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800349f4`

## callees

- `0x180031c08`
- `0x180034a94`
- `0x180034d94`
- `0x18005af1c`
- `0x180089d90`
- `0x1800a0d08`
- `0x1800a1e24`
- `0x1800b83bc`
- `0x1800ce8c0`
- `0x1800d0d9c`
- `0x18012de40`
- `0x18015f810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180034d22`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180034d22`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180034b66`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180034b66`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180034b28`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180034b28`
- `WINHTTP!WinHttpSetTimeouts` at `0x180034c9e`
- `WINHTTP!WinHttpSetTimeouts` at `0x180034c9e`
- `WINHTTP!WinHttpOpen` at `0x180034c0f`
- `WINHTTP!WinHttpOpen` at `0x180034c0f`
- `WINHTTP!WinHttpSetOption` at `0x180034cfd`
- `WINHTTP!WinHttpSetOption` at `0x180034cfd`
- `WINHTTP!WinHttpCloseHandle` at `0x180034c36`
- `WINHTTP!WinHttpCloseHandle` at `0x180034c36`

## string_xrefs

- `0x180034b7a`: `onecore\base\telemetry\utc\include\ImpersonationScope.h`
- `0x180034d36`: `onecore\base\telemetry\utc\include\ImpersonationScope.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Diagnostics::HttpSession::HttpSession(
        __int64 a1,
        Microsoft::Diagnostics::ProxyOptions *a2,
        __int64 a3,
        int *a4)
{
  __int64 v7; // rdx
  const char *v8; // r9
  __int64 v9; // r8
  int UserToken; // eax
  void *v11; // rcx
  const WCHAR *v12; // r8
  DWORD v13; // edx
  void *v14; // rsi
  const char *v15; // r9
  void *v16; // r14
  int v17; // edx
  int v18; // r8d
  int v19; // r9d
  int v20; // eax
  const char *v21; // r9
  DWORD v22; // edx
  _QWORD *i; // rdi
  const char *v24; // r9
  const char *v25; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-50h]
  _BYTE v28[8]; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v29[3]; // [rsp+38h] [rbp-38h] BYREF
  _DWORD v30[6]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v31; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v29[1] = a1;
  v29[2] = a2;
  std::wstring::wstring(a1, a2);
  *(_DWORD *)(a1 + 32) = *(_DWORD *)(v7 + 32);
  std::wstring::wstring(a1 + 40, v7 + 40);
  std::wstring::wstring(a1 + 72, (char *)a2 + 72);
  *(_BYTE *)(a1 + 104) = *((_BYTE *)a2 + 104);
  *(_QWORD *)(a1 + 112) = v9;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  if ( v9 )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a1 + 120,
      0);
    UserToken = UMgrQueryUserToken(*(_QWORD *)(a1 + 112), a1 + 120);
    if ( UserToken < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecore\\base\\telemetry\\http\\lib\\httpsession.cpp",
        (const char *)(unsigned int)UserToken,
        dwFlags);
      *(_QWORD *)(a1 + 112) = 0;
    }
  }
  v11 = *(void **)(a1 + 120);
  v29[0] = 0;
  if ( v11 && !ImpersonateLoggedOnUser(v11) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\ImpersonationScope.h",
      v8);
  if ( *(_BYTE *)(a1 + 104) )
  {
    if ( *(_BYTE *)(a1 + 104) == 1 )
    {
      if ( *(_QWORD *)(a1 + 24) <= 7u )
        v12 = (const WCHAR *)a1;
      else
        v12 = *(const WCHAR **)a1;
      goto LABEL_13;
    }
    if ( *(_BYTE *)(a1 + 104) != 2 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecore\\base\\telemetry\\http\\inc\\ProxyOptions.h",
        v8);
  }
  v12 = 0;
  if ( !*(_BYTE *)(a1 + 104) )
  {
    v13 = 4;
    goto LABEL_21;
  }
  if ( *(_BYTE *)(a1 + 104) == 1 )
  {
LABEL_13:
    v13 = 3;
    goto LABEL_21;
  }
  if ( *(_BYTE *)(a1 + 104) != 2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecore\\base\\telemetry\\http\\inc\\ProxyOptions.h",
      v8);
  v13 = 1;
LABEL_21:
  v14 = WinHttpOpen(L"MSDW", v13, v12, 0, 0x10000000u);
  v16 = *(void **)(a1 + 128);
  if ( v16 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v28);
    WinHttpCloseHandle(v16);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v28);
  }
  *(_QWORD *)(a1 + 128) = v14;
  if ( !v14 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecore\\base\\telemetry\\http\\lib\\httpsession.cpp",
      v15);
  if ( a4 )
  {
    v17 = *a4;
    v18 = a4[1];
    v19 = a4[2];
    v20 = a4[3];
  }
  else
  {
    v17 = 60000;
    v18 = 60000;
    v19 = 30000;
    v20 = 30000;
  }
  if ( !WinHttpSetTimeouts(v14, v17, v18, v19, v20) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecore\\base\\telemetry\\http\\lib\\httpsession.cpp",
      v21);
  v22 = 88;
  v30[0] = 88;
  v30[1] = 1;
  v30[2] = 73;
  v30[3] = 1;
  v30[4] = 84;
  v30[5] = 2048;
  for ( i = v30; ; v22 = *(_DWORD *)i )
  {
    if ( !WinHttpSetOption(*(HINTERNET *)(a1 + 128), v22, (char *)i + 4, 4u) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x38,
        (unsigned int)"onecore\\base\\telemetry\\http\\lib\\httpsession.cpp",
        v24);
    if ( ++i == &v31 )
      break;
  }
  if ( !RevertToSelf() )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\ImpersonationScope.h",
      v25);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v29);
  Microsoft::Diagnostics::ProxyOptions::~ProxyOptions(a2);
  return a1;
}

```

## disassembly

```asm
0x180034a94  mov     [rsp-28h+arg_10], rbx
0x180034a99  push    rbp
0x180034a9a  push    rsi
0x180034a9b  push    rdi
0x180034a9c  push    r14
0x180034a9e  push    r15
0x180034aa0  mov     rbp, rsp
0x180034aa3  sub     rsp, 70h
0x180034aa7  mov     rax, cs:__security_cookie
0x180034aae  xor     rax, rsp
0x180034ab1  mov     [rbp+var_8], rax
0x180034ab5  mov     rdi, r9
0x180034ab8  mov     r15, rdx
0x180034abb  mov     rbx, rcx
0x180034abe  mov     [rbp+var_30], rcx
0x180034ac2  mov     [rbp+var_28], rdx
0x180034ac6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180034acb  mov     ecx, [rdx+20h]
0x180034ace  mov     [rbx+20h], ecx
0x180034ad1  add     rdx, 28h ; '('
0x180034ad5  lea     rcx, [rbx+28h]
0x180034ad9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180034ade  lea     rdx, [r15+48h]
0x180034ae2  lea     rcx, [rbx+48h]
0x180034ae6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180034aeb  mov     al, [r15+68h]
0x180034aef  mov     [rbx+68h], al
0x180034af2  mov     [rbx+70h], r8
0x180034af6  lea     rsi, [rbx+78h]
0x180034afa  mov     qword ptr [rsi], 0
0x180034b01  mov     qword ptr [rbx+80h], 0
0x180034b0c  mov     r14d, 18h
0x180034b12  test    r8, r8
0x180034b15  jz      short loc_180034B56
0x180034b17  xor     edx, edx
0x180034b19  mov     rcx, rsi
0x180034b1c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180034b21  mov     rdx, rsi
0x180034b24  mov     rcx, [rbx+70h]
0x180034b28  call    cs:__imp_UMgrQueryUserToken
0x180034b2f  nop     dword ptr [rax+rax+00h]
0x180034b34  mov     rcx, [rbp+28h]; this
0x180034b38  test    eax, eax
0x180034b3a  jns     short loc_180034B56
0x180034b3c  mov     r9d, eax; char *
0x180034b3f  lea     r8, aOnecoreBaseTel_193; "onecore\\base\\telemetry\\http\\lib\\ht"...
0x180034b46  mov     edx, r14d; void *
0x180034b49  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180034b4e  mov     qword ptr [rbx+70h], 0
0x180034b56  mov     rcx, [rsi]; hToken
0x180034b59  mov     [rbp+var_38], 0
0x180034b61  test    rcx, rcx
0x180034b64  jz      short loc_180034B8A
0x180034b66  call    cs:__imp_ImpersonateLoggedOnUser
0x180034b6d  nop     dword ptr [rax+rax+00h]
0x180034b72  mov     rcx, [rbp+28h]; this
0x180034b76  test    eax, eax
0x180034b78  jnz     short loc_180034B8A
0x180034b7a  lea     r8, aOnecoreBaseTel_176; "onecore\\base\\telemetry\\utc\\include"...
0x180034b81  mov     edx, r14d; void *
0x180034b84  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180034b8a  movzx   ecx, byte ptr [rbx+68h]
0x180034b8e  mov     edx, ecx
0x180034b90  test    ecx, ecx
0x180034b92  jz      short loc_180034BCA
0x180034b94  sub     edx, 1
0x180034b97  jz      short loc_180034BB4
0x180034b99  cmp     edx, 1
0x180034b9c  jz      short loc_180034BCA
0x180034b9e  mov     rcx, [rbp+28h]; this
0x180034ba2  lea     r8, aOnecoreBaseTel_276; "onecore\\base\\telemetry\\http\\inc\\Pr"...
0x180034ba9  mov     edx, 43h ; 'C'; void *
0x180034bae  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180034bb4  cmp     qword ptr [rbx+18h], 7
0x180034bb9  jbe     short loc_180034BC5
0x180034bbb  mov     r8, [rbx]
0x180034bbe  mov     edx, 3
0x180034bc3  jmp     short loc_180034BFD
0x180034bc5  mov     r8, rbx
0x180034bc8  jmp     short loc_180034BBE
0x180034bca  xor     r8d, r8d; pszProxyW
0x180034bcd  test    ecx, ecx
0x180034bcf  jz      short loc_180034BF8
0x180034bd1  sub     ecx, 1
0x180034bd4  jz      short loc_180034BBE
0x180034bd6  cmp     ecx, 1
0x180034bd9  jz      short loc_180034BF1
0x180034bdb  mov     rcx, [rbp+28h]; this
0x180034bdf  lea     r8, aOnecoreBaseTel_276; "onecore\\base\\telemetry\\http\\inc\\Pr"...
0x180034be6  mov     edx, 34h ; '4'; void *
0x180034beb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180034bf1  mov     edx, 1
0x180034bf6  jmp     short loc_180034BFD
0x180034bf8  mov     edx, 4; dwAccessType
0x180034bfd  mov     [rsp+70h+dwFlags], 10000000h; dwFlags
0x180034c05  xor     r9d, r9d; pszProxyBypassW
0x180034c08  lea     rcx, pszAgentW; "MSDW"
0x180034c0f  call    cs:__imp_WinHttpOpen
0x180034c16  nop     dword ptr [rax+rax+00h]
0x180034c1b  mov     rsi, rax
0x180034c1e  mov     r14, [rbx+80h]
0x180034c25  test    r14, r14
0x180034c28  jz      short loc_180034C4B
0x180034c2a  lea     rcx, [rbp+var_40]; this
0x180034c2e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180034c33  mov     rcx, r14; hInternet
0x180034c36  call    cs:__imp_WinHttpCloseHandle
0x180034c3d  nop     dword ptr [rax+rax+00h]
0x180034c42  lea     rcx, [rbp+var_40]; this
0x180034c46  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180034c4b  mov     [rbx+80h], rsi
0x180034c52  test    rsi, rsi
0x180034c55  setz    al
0x180034c58  mov     rcx, [rbp+28h]; this
0x180034c5c  test    al, al
0x180034c5e  jz      short loc_180034C72
0x180034c60  lea     r8, aOnecoreBaseTel_193; "onecore\\base\\telemetry\\http\\lib\\ht"...
0x180034c67  mov     edx, 20h ; ' '; void *
0x180034c6c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180034c72  test    rdi, rdi
0x180034c75  jz      short loc_180034C86
0x180034c77  mov     edx, [rdi]
0x180034c79  mov     r8d, [rdi+4]
0x180034c7d  mov     r9d, [rdi+8]
0x180034c81  mov     eax, [rdi+0Ch]
0x180034c84  jmp     short loc_180034C97
0x180034c86  mov     edx, 0EA60h; nResolveTimeout
0x180034c8b  mov     r8d, edx; nConnectTimeout
0x180034c8e  mov     r9d, 7530h; nSendTimeout
0x180034c94  mov     eax, r9d
0x180034c97  mov     [rsp+70h+dwFlags], eax; nReceiveTimeout
0x180034c9b  mov     rcx, rsi; hInternet
0x180034c9e  call    cs:__imp_WinHttpSetTimeouts
0x180034ca5  nop     dword ptr [rax+rax+00h]
0x180034caa  mov     rcx, [rbp+28h]; this
0x180034cae  test    eax, eax
0x180034cb0  jnz     short loc_180034CC2
0x180034cb2  lea     r8, aOnecoreBaseTel_193; "onecore\\base\\telemetry\\http\\lib\\ht"...
0x180034cb9  lea     edx, [rax+2Dh]; void *
0x180034cbc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180034cc2  mov     edx, 58h ; 'X'; dwOption
0x180034cc7  mov     [rbp+var_20], edx
0x180034cca  lea     eax, [rdx-57h]
0x180034ccd  mov     [rbp+var_1C], eax
0x180034cd0  mov     [rbp+var_18], 49h ; 'I'
0x180034cd7  mov     [rbp+var_14], eax
0x180034cda  mov     [rbp+var_10], 54h ; 'T'
0x180034ce1  mov     [rbp+var_C], 800h
0x180034ce8  lea     rdi, [rbp+var_20]
0x180034cec  lea     r8, [rdi+4]; lpBuffer
0x180034cf0  mov     r9d, 4; dwBufferLength
0x180034cf6  mov     rcx, [rbx+80h]; hInternet
0x180034cfd  call    cs:__imp_WinHttpSetOption
0x180034d04  nop     dword ptr [rax+rax+00h]
0x180034d09  mov     rcx, [rbp+28h]; this
0x180034d0d  test    eax, eax
0x180034d0f  jz      short loc_180034D7C
0x180034d11  add     rdi, 8
0x180034d15  lea     rax, [rbp+var_8]
0x180034d19  cmp     rdi, rax
0x180034d1c  jz      short loc_180034D22
0x180034d1e  mov     edx, [rdi]
0x180034d20  jmp     short loc_180034CEC
0x180034d22  call    cs:__imp_RevertToSelf
0x180034d29  nop     dword ptr [rax+rax+00h]
0x180034d2e  mov     rcx, [rbp+28h]; this
0x180034d32  test    eax, eax
0x180034d34  jnz     short loc_180034D46
0x180034d36  lea     r8, aOnecoreBaseTel_176; "onecore\\base\\telemetry\\utc\\include"...
0x180034d3d  lea     edx, [rax+1Eh]; void *
0x180034d40  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180034d46  lea     rcx, [rbp+var_38]
0x180034d4a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180034d4f  nop
0x180034d50  mov     rcx, r15; this
0x180034d53  call    ??1ProxyOptions@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ProxyOptions::~ProxyOptions(void)
0x180034d58  mov     rax, rbx
0x180034d5b  mov     rcx, [rbp+var_8]
0x180034d5f  xor     rcx, rsp; StackCookie
0x180034d62  call    __security_check_cookie
0x180034d67  mov     rbx, [rsp+70h+arg_10]
0x180034d6f  add     rsp, 70h
0x180034d73  pop     r15
0x180034d75  pop     r14
0x180034d77  pop     rdi
0x180034d78  pop     rsi
0x180034d79  pop     rbp
0x180034d7a  retn
0x180034d7c  lea     r8, aOnecoreBaseTel_193; "onecore\\base\\telemetry\\http\\lib\\ht"...
0x180034d83  mov     edx, 38h ; '8'; void *
0x180034d88  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
