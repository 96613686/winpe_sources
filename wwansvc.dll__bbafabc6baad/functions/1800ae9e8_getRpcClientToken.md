# _getRpcClientToken

- ea: `0x1800ae9e8`
- end: `0x1800aea64`
- name: `_getRpcClientToken`
- size: `124`
- prototype: `RPC_STATUS __fastcall(void **, void *)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800aded4`
- `0x1800adf80`
- `0x1800ae0d4`
- `0x1800ae1c8`
- `0x1800ae7dc`

## callees

- `0x1800ae9e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aea31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aea31`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800aea27`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800aea27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800aea0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800aea0e`
- `RPCRT4!RpcImpersonateClient` at `0x1800aea04`
- `RPCRT4!RpcImpersonateClient` at `0x1800aea04`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800aea3c`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800aea49`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800aea3c`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800aea49`

## pseudocode

```c
RPC_STATUS __fastcall getRpcClientToken(void **a1, void *a2)
{
  RPC_STATUS result; // eax
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  result = RpcImpersonateClient(a2);
  if ( !result )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
    {
      RpcRevertToSelfEx(a2);
      *a1 = TokenHandle;
      return 0;
    }
    else
    {
      LastError = GetLastError();
      RpcRevertToSelfEx(a2);
      return LastError;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800ae9e8  mov     [rsp+arg_0], rbx
0x1800ae9ed  push    rdi
0x1800ae9ee  sub     rsp, 20h
0x1800ae9f2  mov     rbx, rcx
0x1800ae9f5  mov     [rsp+28h+TokenHandle], 0
0x1800ae9fe  mov     rcx, rdx; BindingHandle
0x1800aea01  mov     rdi, rdx
0x1800aea04  call    cs:__imp_RpcImpersonateClient
0x1800aea0a  test    eax, eax
0x1800aea0c  jnz     short loc_1800AEA59
0x1800aea0e  call    cs:__imp_GetCurrentThread
0x1800aea14  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800aea19  mov     edx, 0F01FFh; DesiredAccess
0x1800aea1e  mov     rcx, rax; ThreadHandle
0x1800aea21  mov     r8d, 1; OpenAsSelf
0x1800aea27  call    cs:__imp_OpenThreadToken
0x1800aea2d  test    eax, eax
0x1800aea2f  jnz     short loc_1800AEA46
0x1800aea31  call    cs:__imp_GetLastError
0x1800aea37  mov     rcx, rdi; BindingHandle
0x1800aea3a  mov     ebx, eax
0x1800aea3c  call    cs:__imp_RpcRevertToSelfEx
0x1800aea42  mov     eax, ebx
0x1800aea44  jmp     short loc_1800AEA59
0x1800aea46  mov     rcx, rdi; BindingHandle
0x1800aea49  call    cs:__imp_RpcRevertToSelfEx
0x1800aea4f  mov     rax, [rsp+28h+TokenHandle]
0x1800aea54  mov     [rbx], rax
0x1800aea57  xor     eax, eax
0x1800aea59  mov     rbx, [rsp+28h+arg_0]
0x1800aea5e  add     rsp, 20h
0x1800aea62  pop     rdi
0x1800aea63  retn
```
