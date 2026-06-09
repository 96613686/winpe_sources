# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x1800143b0`
- end: `0x180014482`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `210`
- prototype: `__int64 __fastcall(HANDLE Token, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800144c0`

## callees

- `0x180002418`
- `0x18000cfc4`
- `0x1800104fc`
- `0x1800106b8`
- `0x180014328`
- `0x1800143b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800143e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800143e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800143ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800143ce`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001440a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001440a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143f1`

## string_xrefs

- `0x18001441e`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::impersonate_token_nothrow(HANDLE Token, void **a2)
{
  HANDLE CurrentThread; // rax
  const char *v5; // r9
  __int64 v6; // rdx
  unsigned int LastError; // ebx
  void *v8; // rbx
  void *v9; // rsi
  void *v10; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF
  char v14; // [rsp+48h] [rbp+20h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v6 = 450;
LABEL_6:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v6,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v5);
    goto LABEL_10;
  }
  if ( !SetThreadToken(0, Token) )
  {
    v6 = 454;
    goto LABEL_6;
  }
  v8 = *a2;
  v9 = TokenHandle;
  TokenHandle = 0;
  if ( v8 != (void *)-1LL )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
    wil::details::RevertImpersonateToken(v8, v10);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
  }
  *a2 = v9;
  LastError = 0;
LABEL_10:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800143b0  mov     [rsp+arg_0], rbx
0x1800143b5  mov     [rsp+arg_8], rsi
0x1800143ba  push    rdi
0x1800143bb  sub     rsp, 20h
0x1800143bf  mov     rdi, rdx
0x1800143c2  mov     [rsp+28h+TokenHandle], 0
0x1800143cb  mov     rbx, rcx
0x1800143ce  call    cs:__imp_GetCurrentThread
0x1800143d4  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800143d9  mov     edx, 0F01FFh; DesiredAccess
0x1800143de  mov     rcx, rax; ThreadHandle
0x1800143e1  mov     r8d, 1; OpenAsSelf
0x1800143e7  call    cs:__imp_OpenThreadToken
0x1800143ed  test    eax, eax
0x1800143ef  jnz     short loc_180014405
0x1800143f1  call    cs:__imp_GetLastError
0x1800143f7  cmp     eax, 3F0h
0x1800143fc  jz      short loc_180014405
0x1800143fe  mov     edx, 1C2h
0x180014403  jmp     short loc_180014419
0x180014405  mov     rdx, rbx; Token
0x180014408  xor     ecx, ecx; Thread
0x18001440a  call    cs:__imp_SetThreadToken
0x180014410  test    eax, eax
0x180014412  jnz     short loc_18001442E
0x180014414  mov     edx, 1C6h; void *
0x180014419  mov     rcx, [rsp+28h]; this
0x18001441e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180014425  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001442a  mov     ebx, eax
0x18001442c  jmp     short loc_180014466
0x18001442e  mov     rbx, [rdi]
0x180014431  mov     rsi, [rsp+28h+TokenHandle]
0x180014436  mov     [rsp+28h+TokenHandle], 0
0x18001443f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180014443  jz      short loc_180014461
0x180014445  lea     rcx, [rsp+28h+arg_18]; this
0x18001444a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001444f  mov     rcx, rbx; hObject
0x180014452  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180014457  lea     rcx, [rsp+28h+arg_18]; this
0x18001445c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180014461  mov     [rdi], rsi
0x180014464  xor     ebx, ebx
0x180014466  lea     rcx, [rsp+28h+TokenHandle]
0x18001446b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180014470  mov     rsi, [rsp+28h+arg_8]
0x180014475  mov     eax, ebx
0x180014477  mov     rbx, [rsp+28h+arg_0]
0x18001447c  add     rsp, 20h
0x180014480  pop     rdi
0x180014481  retn
```
