# uf::details::IsImpersonating(void)

- ea: `0x1802b6c90`
- end: `0x1802b6d3b`
- name: `?IsImpersonating@details@uf@@YA_NXZ`
- size: `171`
- prototype: `bool __fastcall(uf::details *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1802b92e4`

## callees

- `0x180086f44`
- `0x1800a14f8`
- `0x1801588c4`
- `0x18015cb00`
- `0x1802b6c90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b6cdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b6cdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802b6cba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802b6cba`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802b6cd1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802b6cd1`

## string_xrefs

- `0x1802b6d29`: `ShellCommon\Internal\Shell\Inc\UndockedFlighting\Impersonation.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall uf::details::IsImpersonating(uf::details *this)
{
  HANDLE CurrentThread; // rax
  const char *v2; // r9
  bool v4; // bl
  void *TokenHandle; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v4 = (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return v4;
  }
  else
  {
    if ( GetLastError() != 1008 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x25,
        (unsigned int)"ShellCommon\\Internal\\Shell\\Inc\\UndockedFlighting\\Impersonation.h",
        v2);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return 0;
  }
}

```

## disassembly

```asm
0x1802b6c90  push    rbx
0x1802b6c92  sub     rsp, 30h
0x1802b6c96  mov     rax, cs:__security_cookie
0x1802b6c9d  xor     rax, rsp
0x1802b6ca0  mov     [rsp+38h+var_10], rax
0x1802b6ca5  mov     [rsp+38h+TokenHandle], 0
0x1802b6cae  xor     edx, edx
0x1802b6cb0  lea     rcx, [rsp+38h+TokenHandle]
0x1802b6cb5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802b6cba  call    cs:__imp_GetCurrentThread
0x1802b6cc0  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1802b6cc5  mov     edx, 8; DesiredAccess
0x1802b6cca  lea     r8d, [rdx-7]; OpenAsSelf
0x1802b6cce  mov     rcx, rax; ThreadHandle
0x1802b6cd1  call    cs:__imp_OpenThreadToken
0x1802b6cd7  test    eax, eax
0x1802b6cd9  jnz     short loc_1802B6CF6
0x1802b6cdb  call    cs:__imp_GetLastError
0x1802b6ce1  cmp     eax, 3F0h
0x1802b6ce6  jnz     short loc_1802B6D24
0x1802b6ce8  lea     rcx, [rsp+38h+TokenHandle]
0x1802b6ced  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802b6cf2  xor     al, al
0x1802b6cf4  jmp     short loc_1802B6D11
0x1802b6cf6  mov     rax, [rsp+38h+TokenHandle]
0x1802b6cfb  dec     rax
0x1802b6cfe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1802b6d02  setbe   bl
0x1802b6d05  lea     rcx, [rsp+38h+TokenHandle]
0x1802b6d0a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802b6d0f  mov     al, bl
0x1802b6d11  mov     rcx, [rsp+38h+var_10]
0x1802b6d16  xor     rcx, rsp; StackCookie
0x1802b6d19  call    __security_check_cookie
0x1802b6d1e  add     rsp, 30h
0x1802b6d22  pop     rbx
0x1802b6d23  retn
0x1802b6d24  mov     rcx, [rsp+38h]; this
0x1802b6d29  lea     r8, aShellcommonInt_0; "ShellCommon\\Internal\\Shell\\Inc\\Undo"...
0x1802b6d30  mov     edx, 25h ; '%'; void *
0x1802b6d35  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
