# CRpcUtils::GetClientToken(void * *,int)

- ea: `0x18000f080`
- end: `0x18000f19a`
- name: `?GetClientToken@CRpcUtils@@SAJPEAPEAXH@Z`
- size: `282`
- prototype: `__int64 __fastcall(void **, int)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180029740`
- `0x18002e920`
- `0x18004da60`
- `0x18005d110`
- `0x18005d530`
- `0x18005fab0`
- `0x180061880`

## callees

- `0x18000a210`
- `0x18000f080`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f170`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f0a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f0a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f0ba`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f0ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f133`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f133`
- `RPCRT4!RpcRevertToSelf` at `0x18000f13b`
- `RPCRT4!RpcRevertToSelf` at `0x18000f13b`
- `RPCRT4!RpcImpersonateClient` at `0x18000f0f2`
- `RPCRT4!RpcImpersonateClient` at `0x18000f0f2`

## string_xrefs

- `0x18000f10b`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18000f112`: `CRpcUtils::GetClientToken`
- `0x18000f18e`: `OpenThreadToken failed: 0x%x in %s`

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
0x18000f080  mov     [rsp+arg_0], rbx
0x18000f085  mov     [rsp+arg_8], rsi
0x18000f08a  push    rdi
0x18000f08b  sub     rsp, 20h
0x18000f08f  mov     [rsp+28h+TokenHandle], 0
0x18000f098  mov     edi, edx
0x18000f09a  mov     rsi, rcx
0x18000f09d  test    edx, edx
0x18000f09f  jz      short loc_18000F0F0
0x18000f0a1  call    cs:__imp_GetCurrentThread
0x18000f0a7  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18000f0ac  mov     edx, 0Eh; DesiredAccess
0x18000f0b1  mov     rcx, rax; ThreadHandle
0x18000f0b4  mov     r8d, 1; OpenAsSelf
0x18000f0ba  call    cs:__imp_OpenThreadToken
0x18000f0c0  test    eax, eax
0x18000f0c2  jz      loc_18000F170
0x18000f0c8  xor     ebx, ebx
0x18000f0ca  test    edi, edi
0x18000f0cc  jz      short loc_18000F13B
0x18000f0ce  test    ebx, ebx
0x18000f0d0  js      loc_18000F18E
0x18000f0d6  mov     rax, [rsp+28h+TokenHandle]
0x18000f0db  mov     [rsi], rax
0x18000f0de  mov     rsi, [rsp+28h+arg_8]
0x18000f0e3  mov     eax, ebx
0x18000f0e5  mov     rbx, [rsp+28h+arg_0]
0x18000f0ea  add     rsp, 20h
0x18000f0ee  pop     rdi
0x18000f0ef  retn
0x18000f0f0  xor     ecx, ecx; BindingHandle
0x18000f0f2  call    cs:__imp_RpcImpersonateClient
0x18000f0f8  mov     ebx, eax
0x18000f0fa  test    eax, eax
0x18000f0fc  jle     short loc_18000F107
0x18000f0fe  movzx   ebx, ax
0x18000f101  or      ebx, 80070000h
0x18000f107  test    ebx, ebx
0x18000f109  jns     short loc_18000F0A1
0x18000f10b  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18000f112  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x18000f119  mov     r8d, ebx
0x18000f11c  mov     ecx, 8; int
0x18000f121  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f126  mov     rax, [rsp+28h+TokenHandle]
0x18000f12b  test    rax, rax
0x18000f12e  jz      short loc_18000F0DB
0x18000f130  mov     rcx, rax; hObject
0x18000f133  call    cs:__imp_CloseHandle
0x18000f139  jmp     short loc_18000F0DE
0x18000f13b  call    cs:__imp_RpcRevertToSelf
0x18000f141  test    eax, eax
0x18000f143  jle     short loc_18000F14F
0x18000f145  movzx   eax, ax
0x18000f148  or      eax, 80070000h
0x18000f14d  test    eax, eax
0x18000f14f  jns     loc_18000F0CE
0x18000f155  mov     r8d, eax
0x18000f158  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x18000f15f  mov     ecx, 8; int
0x18000f164  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f169  mov     ebx, 80070005h
0x18000f16e  jmp     short loc_18000F126
0x18000f170  call    cs:__imp_GetLastError
0x18000f176  mov     ebx, eax
0x18000f178  test    eax, eax
0x18000f17a  jle     loc_18000F0CA
0x18000f180  movzx   ebx, ax
0x18000f183  or      ebx, 80070000h
0x18000f189  jmp     loc_18000F0CA
0x18000f18e  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x in %s"
0x18000f195  jmp     loc_18000F112
```
