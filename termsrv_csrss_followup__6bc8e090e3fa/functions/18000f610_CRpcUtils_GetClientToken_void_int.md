# CRpcUtils::GetClientToken(void * *,int)

- ea: `0x18000f610`
- end: `0x18000f74f`
- name: `?GetClientToken@CRpcUtils@@SAJPEAPEAXH@Z`
- size: `319`
- prototype: `__int64 __fastcall(void **, int)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002ad60`
- `0x180030440`
- `0x1800500a0`
- `0x18005ffe0`
- `0x180060420`
- `0x180062ae0`
- `0x180064950`

## callees

- `0x180009940`
- `0x18000f610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f71f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f71f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f631`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f631`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f650`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f650`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f6d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f6d6`
- `RPCRT4!RpcRevertToSelf` at `0x18000f6e4`
- `RPCRT4!RpcRevertToSelf` at `0x18000f6e4`
- `RPCRT4!RpcImpersonateClient` at `0x18000f68f`
- `RPCRT4!RpcImpersonateClient` at `0x18000f68f`

## string_xrefs

- `0x18000f6ae`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18000f6b5`: `CRpcUtils::GetClientToken`
- `0x18000f743`: `OpenThreadToken failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CRpcUtils::GetClientToken(void **a1, int a2)
{
  HANDLE CurrentThread; // rax
  unsigned int v5; // ebx
  void *v6; // rax
  RPC_STATUS v8; // eax
  int v9; // eax
  bool v10; // sf
  signed int LastError; // eax
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  if ( a2 )
    goto LABEL_2;
  v8 = RpcImpersonateClient(0);
  v5 = v8;
  if ( v8 > 0 )
    v5 = (unsigned __int16)v8 | 0x80070000;
  if ( (v5 & 0x80000000) == 0 )
  {
LABEL_2:
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    {
      v5 = 0;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( a2 )
      goto LABEL_5;
    v9 = RpcRevertToSelf();
    v10 = v9 < 0;
    if ( v9 > 0 )
    {
      v9 = (unsigned __int16)v9 | 0x80070000;
      v10 = v9 < 0;
    }
    if ( !v10 )
    {
LABEL_5:
      if ( (v5 & 0x80000000) == 0 )
      {
        v6 = TokenHandle;
        goto LABEL_7;
      }
      _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", v5, "CRpcUtils::GetClientToken");
    }
    else
    {
      _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v9);
      v5 = -2147024891;
    }
  }
  else
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", v5, "CRpcUtils::GetClientToken");
  }
  v6 = TokenHandle;
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    return v5;
  }
LABEL_7:
  *a1 = v6;
  return v5;
}

```

## disassembly

```asm
0x18000f610  mov     [rsp+arg_0], rbx
0x18000f615  mov     [rsp+arg_8], rsi
0x18000f61a  push    rdi
0x18000f61b  sub     rsp, 20h
0x18000f61f  mov     [rsp+28h+TokenHandle], 0
0x18000f628  mov     edi, edx
0x18000f62a  mov     rsi, rcx
0x18000f62d  test    edx, edx
0x18000f62f  jz      short loc_18000F68D
0x18000f631  call    cs:__imp_GetCurrentThread
0x18000f638  nop     dword ptr [rax+rax+00h]
0x18000f63d  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18000f642  mov     edx, 0Eh; DesiredAccess
0x18000f647  mov     rcx, rax; ThreadHandle
0x18000f64a  mov     r8d, 1; OpenAsSelf
0x18000f650  call    cs:__imp_OpenThreadToken
0x18000f657  nop     dword ptr [rax+rax+00h]
0x18000f65c  test    eax, eax
0x18000f65e  jz      loc_18000F71F
0x18000f664  xor     ebx, ebx
0x18000f666  test    edi, edi
0x18000f668  jz      short loc_18000F6E4
0x18000f66a  test    ebx, ebx
0x18000f66c  js      loc_18000F743
0x18000f672  mov     rax, [rsp+28h+TokenHandle]
0x18000f677  mov     [rsi], rax
0x18000f67a  mov     rsi, [rsp+28h+arg_8]
0x18000f67f  mov     eax, ebx
0x18000f681  mov     rbx, [rsp+28h+arg_0]
0x18000f686  add     rsp, 20h
0x18000f68a  pop     rdi
0x18000f68b  retn
0x18000f68d  xor     ecx, ecx; BindingHandle
0x18000f68f  call    cs:__imp_RpcImpersonateClient
0x18000f696  nop     dword ptr [rax+rax+00h]
0x18000f69b  mov     ebx, eax
0x18000f69d  test    eax, eax
0x18000f69f  jle     short loc_18000F6AA
0x18000f6a1  movzx   ebx, ax
0x18000f6a4  or      ebx, 80070000h
0x18000f6aa  test    ebx, ebx
0x18000f6ac  jns     short loc_18000F631
0x18000f6ae  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18000f6b5  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x18000f6bc  mov     r8d, ebx
0x18000f6bf  mov     ecx, 8; int
0x18000f6c4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f6c9  mov     rax, [rsp+28h+TokenHandle]
0x18000f6ce  test    rax, rax
0x18000f6d1  jz      short loc_18000F677
0x18000f6d3  mov     rcx, rax; hObject
0x18000f6d6  call    cs:__imp_CloseHandle
0x18000f6dd  nop     dword ptr [rax+rax+00h]
0x18000f6e2  jmp     short loc_18000F67A
0x18000f6e4  call    cs:__imp_RpcRevertToSelf
0x18000f6eb  nop     dword ptr [rax+rax+00h]
0x18000f6f0  test    eax, eax
0x18000f6f2  jle     short loc_18000F6FE
0x18000f6f4  movzx   eax, ax
0x18000f6f7  or      eax, 80070000h
0x18000f6fc  test    eax, eax
0x18000f6fe  jns     loc_18000F66A
0x18000f704  mov     r8d, eax
0x18000f707  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x18000f70e  mov     ecx, 8; int
0x18000f713  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f718  mov     ebx, 80070005h
0x18000f71d  jmp     short loc_18000F6C9
0x18000f71f  call    cs:__imp_GetLastError
0x18000f726  nop     dword ptr [rax+rax+00h]
0x18000f72b  mov     ebx, eax
0x18000f72d  test    eax, eax
0x18000f72f  jle     loc_18000F666
0x18000f735  movzx   ebx, ax
0x18000f738  or      ebx, 80070000h
0x18000f73e  jmp     loc_18000F666
0x18000f743  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x in %s"
0x18000f74a  jmp     loc_18000F6B5
```
