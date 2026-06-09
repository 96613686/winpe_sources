# ScGetUserContext(void)

- ea: `0x1400291a8`
- end: `0x140029221`
- name: `?ScGetUserContext@@YA_KXZ`
- size: `121`
- prototype: `unsigned __int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140017284`
- `0x140019370`

## callees

- `0x1400291a8`
- `0x14005b040`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400291f4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400291f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400291dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400291dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140029213`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140029213`
- `RPCRT4!RpcImpersonateClient` at `0x1400291d3`
- `RPCRT4!RpcImpersonateClient` at `0x1400291d3`
- `RPCRT4!RpcRevertToSelf` at `0x140029219`
- `RPCRT4!RpcRevertToSelf` at `0x140029219`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x140029208`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x140029208`

## pseudocode

```c
__int64 ScGetUserContext(void)
{
  HANDLE CurrentThread; // rax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF
  __int64 v3; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  v3 = 0;
  if ( (unsigned __int8)IsUMgrQueryUserContextPresent() && !RpcImpersonateClient(0) )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      UMgrQueryUserContext(TokenHandle, &v3);
      CloseHandle(TokenHandle);
    }
    RpcRevertToSelf();
  }
  return v3;
}

```

## disassembly

```asm
0x1400291a8  sub     rsp, 28h
0x1400291ac  mov     [rsp+28h+TokenHandle], 0
0x1400291b5  mov     [rsp+28h+arg_8], 0
0x1400291be  call    IsUMgrQueryUserContextPresent
0x1400291c3  test    al, al
0x1400291c5  jnz     short loc_1400291D1
0x1400291c7  mov     rax, [rsp+28h+arg_8]
0x1400291cc  add     rsp, 28h
0x1400291d0  retn
0x1400291d1  xor     ecx, ecx; BindingHandle
0x1400291d3  call    cs:__imp_RpcImpersonateClient
0x1400291d9  test    eax, eax
0x1400291db  jnz     short loc_1400291C7
0x1400291dd  call    cs:__imp_GetCurrentThread
0x1400291e3  mov     edx, 8; DesiredAccess
0x1400291e8  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1400291ed  mov     rcx, rax; ThreadHandle
0x1400291f0  lea     r8d, [rdx-7]; OpenAsSelf
0x1400291f4  call    cs:__imp_OpenThreadToken
0x1400291fa  test    eax, eax
0x1400291fc  jz      short loc_140029219
0x1400291fe  mov     rcx, [rsp+28h+TokenHandle]
0x140029203  lea     rdx, [rsp+28h+arg_8]
0x140029208  call    cs:__imp_UMgrQueryUserContext
0x14002920e  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x140029213  call    cs:__imp_CloseHandle
0x140029219  call    cs:__imp_RpcRevertToSelf
0x14002921f  jmp     short loc_1400291C7
```
