# wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x140128674`
- end: `0x140128852`
- name: `?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140128618`

## callees

- `0x140042468`
- `0x1400a6578`
- `0x1400a65a0`
- `0x140128674`
- `0x1401332f0`
- `0x140218618`
- `0x1402453dc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1401287ac`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1401287ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140128734`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140128734`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140128720`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140128720`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140128773`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140128773`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140128703`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140128703`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14012875c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14012875c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140128812`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140128826`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140128812`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140128826`
- `combase!__imp_CoImpersonateClientOfObject` at `0x1401286a2`
- `combase!__imp_CoImpersonateClientOfObject` at `0x1401286a2`

## pseudocode

```c
__int64 __fastcall wil::GetImpersonationTokenForClientOfObject_nothrow(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  bool v7; // bl
  void **v8; // rdi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  const char *v12; // r9
  __int64 v13; // rdx
  void **phNewToken; // rax
  unsigned int v15; // edi
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-28h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-28h]
  void *TokenHandle; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(TokenHandle) = 0;
  v4 = CoImpersonateClientOfObject(a1, &TokenHandle);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)(unsigned int)v4,
      TokenType);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)v5,
      TokenTypea);
    return v5;
  }
  v7 = (_DWORD)TokenHandle != 0;
  v8 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(a3);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, v8) )
    goto LABEL_17;
  LastError = GetLastError();
  if ( !v7 && LastError == 1008 )
  {
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
    {
      v13 = 386;
LABEL_11:
      v5 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v13,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
             v12);
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return v5;
    }
    phNewToken = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(a3);
    if ( !DuplicateTokenEx(TokenHandle, 8u, 0, SecurityImpersonation, TokenImpersonation, phNewToken) )
    {
      v13 = 388;
      goto LABEL_11;
    }
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return 0;
  }
  if ( !LastError )
  {
LABEL_17:
    if ( v7 )
      CoRevertToSelf();
    return 0;
  }
  v15 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x188,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
          (const char *)LastError,
          TokenType);
  if ( v7 )
    CoRevertToSelf();
  return v15;
}

```

## disassembly

```asm
0x140128674  mov     [rsp+arg_8], rbx
0x140128679  mov     [rsp+arg_18], rsi
0x14012867e  push    rdi
0x14012867f  sub     rsp, 40h
0x140128683  mov     rax, cs:__security_cookie
0x14012868a  xor     rax, rsp
0x14012868d  mov     [rsp+48h+var_10], rax
0x140128692  lea     rdx, [rsp+48h+TokenHandle]
0x140128697  mov     dword ptr [rsp+48h+TokenHandle], 0
0x14012869f  mov     rsi, r8
0x1401286a2  call    cs:__imp_CoImpersonateClientOfObject
0x1401286a9  nop     dword ptr [rax+rax+00h]
0x1401286ae  mov     ebx, eax
0x1401286b0  test    eax, eax
0x1401286b2  jns     short loc_1401286ED
0x1401286b4  mov     rcx, [rsp+48h]; this
0x1401286b9  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x1401286c0  mov     r9d, eax; char *
0x1401286c3  mov     edx, 157h; void *
0x1401286c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401286cd  mov     rcx, [rsp+48h]; this
0x1401286d2  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x1401286d9  mov     r9d, ebx; char *
0x1401286dc  mov     edx, 177h; void *
0x1401286e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401286e6  mov     eax, ebx
0x1401286e8  jmp     loc_140128834
0x1401286ed  xor     bl, bl
0x1401286ef  cmp     dword ptr [rsp+48h+TokenHandle], 0
0x1401286f4  jz      short loc_1401286F8
0x1401286f6  mov     bl, 1
0x1401286f8  mov     rcx, rsi
0x1401286fb  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x140128700  mov     rdi, rax
0x140128703  call    cs:__imp_GetCurrentThread
0x14012870a  nop     dword ptr [rax+rax+00h]
0x14012870f  mov     r9, rdi; TokenHandle
0x140128712  mov     edi, 8
0x140128717  mov     edx, edi; DesiredAccess
0x140128719  mov     rcx, rax; ThreadHandle
0x14012871c  lea     r8d, [rdi-7]; OpenAsSelf
0x140128720  call    cs:__imp_OpenThreadToken
0x140128727  nop     dword ptr [rax+rax+00h]
0x14012872c  test    eax, eax
0x14012872e  jnz     loc_140128822
0x140128734  call    cs:__imp_GetLastError
0x14012873b  nop     dword ptr [rax+rax+00h]
0x140128740  test    bl, bl
0x140128742  jnz     loc_1401287EF
0x140128748  cmp     eax, 3F0h
0x14012874d  jnz     loc_1401287EF
0x140128753  mov     [rsp+48h+TokenHandle], 0
0x14012875c  call    cs:__imp_GetCurrentProcess
0x140128763  nop     dword ptr [rax+rax+00h]
0x140128768  mov     rcx, rax; ProcessHandle
0x14012876b  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x140128770  lea     edx, [rdi+2]; DesiredAccess
0x140128773  call    cs:__imp_OpenProcessToken
0x14012877a  nop     dword ptr [rax+rax+00h]
0x14012877f  test    eax, eax
0x140128781  jnz     short loc_14012878A
0x140128783  mov     edx, 182h
0x140128788  jmp     short loc_1401287C1
0x14012878a  mov     rcx, rsi
0x14012878d  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x140128792  mov     rcx, [rsp+48h+TokenHandle]; hExistingToken
0x140128797  mov     r9d, 2; ImpersonationLevel
0x14012879d  mov     [rsp+48h+phNewToken], rax; phNewToken
0x1401287a2  xor     r8d, r8d; lpTokenAttributes
0x1401287a5  mov     edx, edi; dwDesiredAccess
0x1401287a7  mov     [rsp+48h+TokenType], r9d; TokenType
0x1401287ac  call    cs:__imp_DuplicateTokenEx
0x1401287b3  nop     dword ptr [rax+rax+00h]
0x1401287b8  test    eax, eax
0x1401287ba  jnz     short loc_1401287E3
0x1401287bc  mov     edx, 184h; void *
0x1401287c1  mov     rcx, [rsp+48h]; this
0x1401287c6  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x1401287cd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1401287d2  lea     rcx, [rsp+48h+TokenHandle]
0x1401287d7  mov     ebx, eax
0x1401287d9  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1401287de  jmp     loc_1401286E6
0x1401287e3  lea     rcx, [rsp+48h+TokenHandle]
0x1401287e8  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1401287ed  jmp     short loc_140128832
0x1401287ef  test    eax, eax
0x1401287f1  jz      short loc_140128822
0x1401287f3  mov     rcx, [rsp+48h]; this
0x1401287f8  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x1401287ff  mov     r9d, eax; char *
0x140128802  mov     edx, 188h; void *
0x140128807  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14012880c  mov     edi, eax
0x14012880e  test    bl, bl
0x140128810  jz      short loc_14012881E
0x140128812  call    cs:__imp_CoRevertToSelf
0x140128819  nop     dword ptr [rax+rax+00h]
0x14012881e  mov     eax, edi
0x140128820  jmp     short loc_140128834
0x140128822  test    bl, bl
0x140128824  jz      short loc_140128832
0x140128826  call    cs:__imp_CoRevertToSelf
0x14012882d  nop     dword ptr [rax+rax+00h]
0x140128832  xor     eax, eax
0x140128834  mov     rcx, [rsp+48h+var_10]
0x140128839  xor     rcx, rsp; StackCookie
0x14012883c  call    __security_check_cookie
0x140128841  mov     rbx, [rsp+48h+arg_8]
0x140128846  mov     rsi, [rsp+48h+arg_18]
0x14012884b  add     rsp, 40h
0x14012884f  pop     rdi
0x140128850  retn
```
