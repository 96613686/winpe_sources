# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x180015544`
- end: `0x18001562f`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `235`
- prototype: `__int64 __fastcall(HANDLE Token)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180015670`

## callees

- `0x180002468`
- `0x18000dc30`
- `0x18001136c`
- `0x1800114c4`
- `0x1800154a4`
- `0x180015544`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180015581`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180015581`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015562`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015562`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800155b0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800155b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015591`

## string_xrefs

- `0x1800155ca`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
0x180015544  mov     [rsp+arg_0], rbx
0x180015549  mov     [rsp+arg_8], rsi
0x18001554e  push    rdi
0x18001554f  sub     rsp, 20h
0x180015553  mov     rdi, rdx
0x180015556  mov     [rsp+28h+TokenHandle], 0
0x18001555f  mov     rbx, rcx
0x180015562  call    cs:__imp_GetCurrentThread
0x180015569  nop     dword ptr [rax+rax+00h]
0x18001556e  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180015573  mov     edx, 0F01FFh; DesiredAccess
0x180015578  mov     rcx, rax; ThreadHandle
0x18001557b  mov     r8d, 1; OpenAsSelf
0x180015581  call    cs:__imp_OpenThreadToken
0x180015588  nop     dword ptr [rax+rax+00h]
0x18001558d  test    eax, eax
0x18001558f  jnz     short loc_1800155AB
0x180015591  call    cs:__imp_GetLastError
0x180015598  nop     dword ptr [rax+rax+00h]
0x18001559d  cmp     eax, 3F0h
0x1800155a2  jz      short loc_1800155AB
0x1800155a4  mov     edx, 1C2h
0x1800155a9  jmp     short loc_1800155C5
0x1800155ab  mov     rdx, rbx; Token
0x1800155ae  xor     ecx, ecx; Thread
0x1800155b0  call    cs:__imp_SetThreadToken
0x1800155b7  nop     dword ptr [rax+rax+00h]
0x1800155bc  test    eax, eax
0x1800155be  jnz     short loc_1800155DA
0x1800155c0  mov     edx, 1C6h; void *
0x1800155c5  mov     rcx, [rsp+28h]; this
0x1800155ca  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800155d1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800155d6  mov     ebx, eax
0x1800155d8  jmp     short loc_180015612
0x1800155da  mov     rbx, [rdi]
0x1800155dd  mov     rsi, [rsp+28h+TokenHandle]
0x1800155e2  mov     [rsp+28h+TokenHandle], 0
0x1800155eb  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800155ef  jz      short loc_18001560D
0x1800155f1  lea     rcx, [rsp+28h+arg_18]; this
0x1800155f6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800155fb  mov     rcx, rbx; hObject
0x1800155fe  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180015603  lea     rcx, [rsp+28h+arg_18]; this
0x180015608  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001560d  mov     [rdi], rsi
0x180015610  xor     ebx, ebx
0x180015612  lea     rcx, [rsp+28h+TokenHandle]
0x180015617  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001561c  mov     rsi, [rsp+28h+arg_8]
0x180015621  mov     eax, ebx
0x180015623  mov     rbx, [rsp+28h+arg_0]
0x180015628  add     rsp, 20h
0x18001562c  pop     rdi
0x18001562d  retn
```
