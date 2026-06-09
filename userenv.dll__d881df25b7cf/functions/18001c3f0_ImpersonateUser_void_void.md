# ImpersonateUser(void *,void * *)

- ea: `0x18001c3f0`
- end: `0x18001c515`
- name: `?ImpersonateUser@@YAJPEAXPEAPEAX@Z`
- size: `293`
- prototype: `__int64 __fastcall(HANDLE hToken, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001c16c`

## callees

- `0x180002468`
- `0x18000db08`
- `0x18000dc30`
- `0x180015508`
- `0x18001c3f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001c450`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001c450`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c431`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c460`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c460`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001c4b3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001c4b3`

## string_xrefs

- `0x18001c48f`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001c4c8`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ImpersonateUser(HANDLE hToken, void **a2)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  const char *v8; // r9
  void *v9; // rax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 != -2147023888 && (v6 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
        (const char *)v6,
        v10);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return v6;
    }
  }
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x2D,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
           v8);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return v6;
  }
  v9 = TokenHandle;
  TokenHandle = 0;
  *a2 = v9;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x18001c3f0  mov     rax, rsp
0x18001c3f3  mov     [rax+8], rbx
0x18001c3f7  mov     [rax+18h], rsi
0x18001c3fb  push    rdi; int
0x18001c3fc  sub     rsp, 20h
0x18001c400  mov     rdi, rdx
0x18001c403  mov     rsi, rcx
0x18001c406  mov     qword ptr [rdx], 0
0x18001c40d  mov     qword ptr [rax+10h], 0
0x18001c415  mov     rcx, [rax+10h]; hObject
0x18001c419  lea     rax, [rcx-1]
0x18001c41d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c421  ja      short loc_18001C428
0x18001c423  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18001c428  mov     [rsp+28h+TokenHandle], 0
0x18001c431  call    cs:__imp_GetCurrentThread
0x18001c438  nop     dword ptr [rax+rax+00h]
0x18001c43d  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18001c442  mov     edx, 2000Ch; DesiredAccess
0x18001c447  mov     r8d, 1; OpenAsSelf
0x18001c44d  mov     rcx, rax; ThreadHandle
0x18001c450  call    cs:__imp_OpenThreadToken
0x18001c457  nop     dword ptr [rax+rax+00h]
0x18001c45c  test    eax, eax
0x18001c45e  jnz     short loc_18001C4B0
0x18001c460  call    cs:__imp_GetLastError
0x18001c467  nop     dword ptr [rax+rax+00h]
0x18001c46c  mov     ebx, eax
0x18001c46e  test    eax, eax
0x18001c470  jle     short loc_18001C47B
0x18001c472  movzx   ebx, ax
0x18001c475  or      ebx, 80070000h
0x18001c47b  cmp     ebx, 800703F0h
0x18001c481  jz      short loc_18001C4B0
0x18001c483  test    ebx, ebx
0x18001c485  jns     short loc_18001C4B0
0x18001c487  mov     rcx, [rsp+28h]; this
0x18001c48c  mov     r9d, ebx; char *
0x18001c48f  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001c496  mov     edx, 2Ah ; '*'; void *
0x18001c49b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c4a0  nop
0x18001c4a1  lea     rcx, [rsp+28h+TokenHandle]
0x18001c4a6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001c4ab  nop
0x18001c4ac  mov     eax, ebx
0x18001c4ae  jmp     short loc_18001C504
0x18001c4b0  mov     rcx, rsi; hToken
0x18001c4b3  call    cs:__imp_ImpersonateLoggedOnUser
0x18001c4ba  nop     dword ptr [rax+rax+00h]
0x18001c4bf  test    eax, eax
0x18001c4c1  jnz     short loc_18001C4E6
0x18001c4c3  mov     rcx, [rsp+28h]; this
0x18001c4c8  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001c4cf  lea     edx, [rax+2Dh]; void *
0x18001c4d2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001c4d7  mov     ebx, eax
0x18001c4d9  lea     rcx, [rsp+28h+TokenHandle]
0x18001c4de  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001c4e3  nop
0x18001c4e4  jmp     short loc_18001C4AC
0x18001c4e6  mov     rax, [rsp+28h+TokenHandle]
0x18001c4eb  mov     [rsp+28h+TokenHandle], 0
0x18001c4f4  mov     [rdi], rax
0x18001c4f7  lea     rcx, [rsp+28h+TokenHandle]
0x18001c4fc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001c501  nop
0x18001c502  xor     eax, eax
0x18001c504  mov     rbx, [rsp+28h+arg_0]
0x18001c509  mov     rsi, [rsp+28h+arg_10]
0x18001c50e  add     rsp, 20h
0x18001c512  pop     rdi
0x18001c513  retn
```
