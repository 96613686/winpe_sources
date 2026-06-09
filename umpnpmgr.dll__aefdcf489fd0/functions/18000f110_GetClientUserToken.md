# GetClientUserToken

- ea: `0x18000f110`
- end: `0x18000f1fe`
- name: `GetClientUserToken`
- size: `238`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bc30`
- `0x1800121f0`
- `0x1800144b0`
- `0x1800146d0`
- `0x1800148a0`

## callees

- `0x18000f110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f1bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f1bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1e2`
- `RPCRT4!RpcImpersonateClient` at `0x18000f135`
- `RPCRT4!RpcImpersonateClient` at `0x18000f135`
- `RPCRT4!RpcRevertToSelf` at `0x18000f174`
- `RPCRT4!RpcRevertToSelf` at `0x180018e69`
- `RPCRT4!RpcRevertToSelf` at `0x18000f174`
- `RPCRT4!RpcRevertToSelf` at `0x180018e69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f143`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f143`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f159`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f159`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000f1a1`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000f1a1`

## pseudocode

```c
__int64 __fastcall GetClientUserToken(void **a1)
{
  DWORD LastError; // edi
  RPC_STATUS v3; // eax
  HANDLE CurrentThread; // rax
  unsigned int v5; // esi
  void *phNewToken; // [rsp+60h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+10h] BYREF

  LastError = 0;
  phNewToken = 0;
  TokenHandle = 0;
  *a1 = 0;
  v3 = RpcImpersonateClient(0);
  if ( v3 )
  {
    LastError = v3;
LABEL_13:
    v5 = 1;
    goto LABEL_7;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000000u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    phNewToken = 0;
  }
  RpcRevertToSelf();
  if ( LastError )
    goto LABEL_13;
  v5 = 1;
  if ( DuplicateTokenEx(TokenHandle, 0, 0, SecurityImpersonation, TokenPrimary, &phNewToken) )
  {
    *a1 = phNewToken;
  }
  else
  {
    LastError = GetLastError();
    phNewToken = 0;
  }
LABEL_7:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  SetLastError(LastError);
  if ( LastError )
    return 0;
  return v5;
}

```

## disassembly

```asm
0x18000f110  mov     [rsp+arg_10], rbx
0x18000f115  push    rsi
0x18000f116  push    rdi
0x18000f117  push    r14
0x18000f119  sub     rsp, 40h
0x18000f11d  mov     rbx, rcx
0x18000f120  xor     r14d, r14d
0x18000f123  mov     edi, r14d
0x18000f126  mov     [rsp+58h+arg_0], r14
0x18000f12b  mov     [rsp+58h+TokenHandle], r14
0x18000f130  mov     [rcx], r14
0x18000f133  xor     ecx, ecx; BindingHandle
0x18000f135  call    cs:__imp_RpcImpersonateClient
0x18000f13b  test    eax, eax
0x18000f13d  jnz     loc_18000F1D9
0x18000f143  call    cs:__imp_GetCurrentThread
0x18000f149  mov     rcx, rax; ThreadHandle
0x18000f14c  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x18000f151  xor     r8d, r8d; OpenAsSelf
0x18000f154  mov     edx, 2000000h; DesiredAccess
0x18000f159  call    cs:__imp_OpenThreadToken
0x18000f15f  test    eax, eax
0x18000f161  jnz     short loc_18000F174
0x18000f163  call    cs:__imp_GetLastError
0x18000f169  mov     edi, eax
0x18000f16b  mov     [rsp+58h+var_28], eax
0x18000f16f  mov     [rsp+58h+arg_0], r14
0x18000f174  call    cs:__imp_RpcRevertToSelf
0x18000f17a  test    edi, edi
0x18000f17c  jnz     short loc_18000F1DB
0x18000f17e  lea     rax, [rsp+58h+arg_0]
0x18000f183  mov     [rsp+58h+phNewToken], rax; phNewToken
0x18000f188  mov     esi, 1
0x18000f18d  mov     [rsp+58h+TokenType], esi; TokenType
0x18000f191  mov     r9d, 2; ImpersonationLevel
0x18000f197  xor     r8d, r8d; lpTokenAttributes
0x18000f19a  xor     edx, edx; dwDesiredAccess
0x18000f19c  mov     rcx, [rsp+58h+TokenHandle]; hExistingToken
0x18000f1a1  call    cs:__imp_DuplicateTokenEx
0x18000f1a7  test    eax, eax
0x18000f1a9  jz      short loc_18000F1E2
0x18000f1ab  mov     rax, [rsp+58h+arg_0]
0x18000f1b0  mov     [rbx], rax
0x18000f1b3  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18000f1b8  test    rcx, rcx
0x18000f1bb  jnz     short loc_18000F1F1
0x18000f1bd  mov     ecx, edi; dwErrCode
0x18000f1bf  call    cs:__imp_SetLastError
0x18000f1c5  test    edi, edi
0x18000f1c7  jnz     short loc_18000F1F9
0x18000f1c9  mov     eax, esi
0x18000f1cb  mov     rbx, [rsp+58h+arg_10]
0x18000f1d0  add     rsp, 40h
0x18000f1d4  pop     r14
0x18000f1d6  pop     rdi
0x18000f1d7  pop     rsi
0x18000f1d8  retn
0x18000f1d9  mov     edi, eax
0x18000f1db  mov     esi, 1
0x18000f1e0  jmp     short loc_18000F1B3
0x18000f1e2  call    cs:__imp_GetLastError
0x18000f1e8  mov     edi, eax
0x18000f1ea  mov     [rsp+58h+arg_0], r14
0x18000f1ef  jmp     short loc_18000F1B3
0x18000f1f1  call    cs:__imp_CloseHandle
0x18000f1f7  jmp     short loc_18000F1BD
0x18000f1f9  mov     esi, r14d
0x18000f1fc  jmp     short loc_18000F1C9
0x180018e60  push    rbp
0x180018e62  sub     rsp, 30h
0x180018e66  mov     rbp, rdx
0x180018e69  call    cs:__imp_RpcRevertToSelf
0x180018e6f  nop
0x180018e70  add     rsp, 30h
0x180018e74  pop     rbp
0x180018e75  retn
```
