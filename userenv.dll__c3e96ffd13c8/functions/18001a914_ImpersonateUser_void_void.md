# ImpersonateUser(void *,void * *)

- ea: `0x18001a914`
- end: `0x18001aa20`
- name: `?ImpersonateUser@@YAJPEAXPEAPEAX@Z`
- size: `268`
- prototype: `__int64 __fastcall(HANDLE hToken, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001a6a0`

## callees

- `0x180002418`
- `0x18000cea0`
- `0x18000cfc4`
- `0x18001437c`
- `0x18001a914`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001a96e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001a96e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a955`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a978`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001a9c5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001a9c5`

## string_xrefs

- `0x18001a9a1`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001a9d4`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

## pseudocode

```c
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
0x18001a914  mov     rax, rsp
0x18001a917  mov     [rax+8], rbx
0x18001a91b  mov     [rax+18h], rsi
0x18001a91f  push    rdi; int
0x18001a920  sub     rsp, 20h
0x18001a924  mov     rdi, rdx
0x18001a927  mov     rsi, rcx
0x18001a92a  mov     qword ptr [rdx], 0
0x18001a931  mov     qword ptr [rax+10h], 0
0x18001a939  mov     rcx, [rax+10h]; hObject
0x18001a93d  lea     rax, [rcx-1]
0x18001a941  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a945  ja      short loc_18001A94C
0x18001a947  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18001a94c  mov     [rsp+28h+TokenHandle], 0
0x18001a955  call    cs:__imp_GetCurrentThread
0x18001a95b  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18001a960  mov     edx, 2000Ch; DesiredAccess
0x18001a965  mov     r8d, 1; OpenAsSelf
0x18001a96b  mov     rcx, rax; ThreadHandle
0x18001a96e  call    cs:__imp_OpenThreadToken
0x18001a974  test    eax, eax
0x18001a976  jnz     short loc_18001A9C2
0x18001a978  call    cs:__imp_GetLastError
0x18001a97e  mov     ebx, eax
0x18001a980  test    eax, eax
0x18001a982  jle     short loc_18001A98D
0x18001a984  movzx   ebx, ax
0x18001a987  or      ebx, 80070000h
0x18001a98d  cmp     ebx, 800703F0h
0x18001a993  jz      short loc_18001A9C2
0x18001a995  test    ebx, ebx
0x18001a997  jns     short loc_18001A9C2
0x18001a999  mov     rcx, [rsp+28h]; this
0x18001a99e  mov     r9d, ebx; char *
0x18001a9a1  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a9a8  mov     edx, 2Ah ; '*'; void *
0x18001a9ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a9b2  nop
0x18001a9b3  lea     rcx, [rsp+28h+TokenHandle]
0x18001a9b8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001a9bd  nop
0x18001a9be  mov     eax, ebx
0x18001a9c0  jmp     short loc_18001AA10
0x18001a9c2  mov     rcx, rsi; hToken
0x18001a9c5  call    cs:__imp_ImpersonateLoggedOnUser
0x18001a9cb  test    eax, eax
0x18001a9cd  jnz     short loc_18001A9F2
0x18001a9cf  mov     rcx, [rsp+28h]; this
0x18001a9d4  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a9db  lea     edx, [rax+2Dh]; void *
0x18001a9de  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a9e3  mov     ebx, eax
0x18001a9e5  lea     rcx, [rsp+28h+TokenHandle]
0x18001a9ea  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001a9ef  nop
0x18001a9f0  jmp     short loc_18001A9BE
0x18001a9f2  mov     rax, [rsp+28h+TokenHandle]
0x18001a9f7  mov     [rsp+28h+TokenHandle], 0
0x18001aa00  mov     [rdi], rax
0x18001aa03  lea     rcx, [rsp+28h+TokenHandle]
0x18001aa08  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001aa0d  nop
0x18001aa0e  xor     eax, eax
0x18001aa10  mov     rbx, [rsp+28h+arg_0]
0x18001aa15  mov     rsi, [rsp+28h+arg_10]
0x18001aa1a  add     rsp, 20h
0x18001aa1e  pop     rdi
0x18001aa1f  retn
```
