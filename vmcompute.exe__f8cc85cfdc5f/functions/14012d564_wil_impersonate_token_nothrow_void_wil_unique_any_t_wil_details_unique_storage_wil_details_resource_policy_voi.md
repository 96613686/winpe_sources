# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x14012d564`
- end: `0x14012d655`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `241`
- prototype: `__int64 __fastcall(HANDLE Token)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14012d504`

## callees

- `0x140024030`
- `0x140042468`
- `0x1400a65a0`
- `0x14012d564`
- `0x1401332f0`
- `0x140233160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14012d5ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14012d5ca`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14012d5e9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14012d5e9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14012d5ba`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14012d5ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14012d59d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14012d59d`

## string_xrefs

- `0x14012d603`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::impersonate_token_nothrow(HANDLE Token, __int64 a2)
{
  void **v4; // rbx
  HANDLE CurrentThread; // rax
  const char *v6; // r9
  __int64 v7; // rdx
  unsigned int LastError; // ebx
  __int64 v9; // rdx
  __int64 v11; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v11 = 0;
  v4 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v11);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, v4) || GetLastError() == 1008 )
  {
    if ( SetThreadToken(0, Token) )
    {
      v9 = v11;
      v11 = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::reset(
        a2,
        v9);
      LastError = 0;
      goto LABEL_8;
    }
    v7 = 454;
  }
  else
  {
    v7 = 450;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v7,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                v6);
LABEL_8:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
  return LastError;
}

```

## disassembly

```asm
0x14012d564  mov     r11, rsp
0x14012d567  mov     [r11+18h], rbx
0x14012d56b  mov     [r11+20h], rsi
0x14012d56f  push    rdi
0x14012d570  sub     rsp, 30h
0x14012d574  mov     rax, cs:__security_cookie
0x14012d57b  xor     rax, rsp
0x14012d57e  mov     [rsp+38h+var_10], rax
0x14012d583  mov     rsi, rcx
0x14012d586  mov     qword ptr [r11-18h], 0
0x14012d58e  lea     rcx, [r11-18h]
0x14012d592  mov     rdi, rdx
0x14012d595  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x14012d59a  mov     rbx, rax
0x14012d59d  call    cs:__imp_GetCurrentThread
0x14012d5a4  nop     dword ptr [rax+rax+00h]
0x14012d5a9  mov     r9, rbx; TokenHandle
0x14012d5ac  mov     edx, 0F01FFh; DesiredAccess
0x14012d5b1  mov     rcx, rax; ThreadHandle
0x14012d5b4  mov     r8d, 1; OpenAsSelf
0x14012d5ba  call    cs:__imp_OpenThreadToken
0x14012d5c1  nop     dword ptr [rax+rax+00h]
0x14012d5c6  test    eax, eax
0x14012d5c8  jnz     short loc_14012D5E4
0x14012d5ca  call    cs:__imp_GetLastError
0x14012d5d1  nop     dword ptr [rax+rax+00h]
0x14012d5d6  cmp     eax, 3F0h
0x14012d5db  jz      short loc_14012D5E4
0x14012d5dd  mov     edx, 1C2h
0x14012d5e2  jmp     short loc_14012D5FE
0x14012d5e4  mov     rdx, rsi; Token
0x14012d5e7  xor     ecx, ecx; Thread
0x14012d5e9  call    cs:__imp_SetThreadToken
0x14012d5f0  nop     dword ptr [rax+rax+00h]
0x14012d5f5  test    eax, eax
0x14012d5f7  jnz     short loc_14012D613
0x14012d5f9  mov     edx, 1C6h; void *
0x14012d5fe  mov     rcx, [rsp+38h]; this
0x14012d603  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14012d60a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14012d60f  mov     ebx, eax
0x14012d611  jmp     short loc_14012D62B
0x14012d613  mov     rdx, [rsp+38h+var_18]
0x14012d618  mov     rcx, rdi
0x14012d61b  mov     [rsp+38h+var_18], 0
0x14012d624  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::reset(void *)
0x14012d629  xor     ebx, ebx
0x14012d62b  lea     rcx, [rsp+38h+var_18]; void *
0x14012d630  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14012d635  mov     eax, ebx
0x14012d637  mov     rcx, [rsp+38h+var_10]
0x14012d63c  xor     rcx, rsp; StackCookie
0x14012d63f  call    __security_check_cookie
0x14012d644  mov     rbx, [rsp+38h+arg_10]
0x14012d649  mov     rsi, [rsp+38h+arg_18]
0x14012d64e  add     rsp, 30h
0x14012d652  pop     rdi
0x14012d653  retn
```
