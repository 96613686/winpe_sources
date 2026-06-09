# LocalQueryRpcClientToken(void * *)

- ea: `0x18000c4f4`
- end: `0x18000c5f6`
- name: `?LocalQueryRpcClientToken@@YAKPEAPEAX@Z`
- size: `258`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000c3e4`
- `0x18000c858`
- `0x180027f34`

## callees

- `0x18000bf74`
- `0x18000c4f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c572`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c572`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c548`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c548`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c561`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c561`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000c5b0`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000c5b0`
- `RPCRT4!RpcImpersonateClient` at `0x18000c511`
- `RPCRT4!RpcImpersonateClient` at `0x18000c511`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LocalQueryRpcClientToken(void **a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  TetheringServiceTelemetry *v4; // rcx
  __int64 v5; // rdx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  v2 = RpcImpersonateClient(0);
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 10;
LABEL_14:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_18a7ed7453dd33af20c1feb47c4ff862_Traceguids, v2);
    }
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
    {
      *a1 = TokenHandle;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_18a7ed7453dd33af20c1feb47c4ff862_Traceguids, LastError);
      }
    }
    v2 = RpcRevertToSelfEx(0);
    if ( v2 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 12;
        goto LABEL_14;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000c4f4  mov     [rsp+arg_0], rbx
0x18000c4f9  mov     [rsp+arg_10], rsi
0x18000c4fe  push    rdi
0x18000c4ff  sub     rsp, 20h
0x18000c503  mov     rsi, rcx
0x18000c506  mov     [rsp+28h+TokenHandle], 0
0x18000c50f  xor     ecx, ecx; BindingHandle
0x18000c511  call    cs:__imp_RpcImpersonateClient
0x18000c517  mov     ebx, eax
0x18000c519  test    eax, eax
0x18000c51b  jz      short loc_18000C548
0x18000c51d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c524  lea     rdi, WPP_GLOBAL_Control
0x18000c52b  cmp     rcx, rdi
0x18000c52e  jz      loc_18000C5E4
0x18000c534  test    byte ptr [rcx+1Ch], 1
0x18000c538  jz      loc_18000C5E4
0x18000c53e  mov     edx, 0Ah
0x18000c543  jmp     loc_18000C5D1
0x18000c548  call    cs:__imp_GetCurrentThread
0x18000c54e  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18000c553  mov     edx, 0F01FFh; DesiredAccess
0x18000c558  mov     rcx, rax; ThreadHandle
0x18000c55b  mov     r8d, 1; OpenAsSelf
0x18000c561  call    cs:__imp_OpenThreadToken
0x18000c567  lea     rdi, WPP_GLOBAL_Control
0x18000c56e  test    eax, eax
0x18000c570  jnz     short loc_18000C5A6
0x18000c572  call    cs:__imp_GetLastError
0x18000c578  mov     ebx, eax
0x18000c57a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c581  cmp     rcx, rdi
0x18000c584  jz      short loc_18000C5AE
0x18000c586  test    byte ptr [rcx+1Ch], 1
0x18000c58a  jz      short loc_18000C5AE
0x18000c58c  mov     rcx, [rcx+10h]
0x18000c590  lea     r8, WPP_18a7ed7453dd33af20c1feb47c4ff862_Traceguids
0x18000c597  mov     edx, 0Bh
0x18000c59c  mov     r9d, eax
0x18000c59f  call    WPP_SF_d
0x18000c5a4  jmp     short loc_18000C5AE
0x18000c5a6  mov     rax, [rsp+28h+TokenHandle]
0x18000c5ab  mov     [rsi], rax
0x18000c5ae  xor     ecx, ecx; BindingHandle
0x18000c5b0  call    cs:__imp_RpcRevertToSelfEx
0x18000c5b6  test    eax, eax
0x18000c5b8  jz      short loc_18000C5E4
0x18000c5ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5c1  cmp     rcx, rdi
0x18000c5c4  jz      short loc_18000C5E4
0x18000c5c6  test    byte ptr [rcx+1Ch], 1
0x18000c5ca  jz      short loc_18000C5E4
0x18000c5cc  mov     edx, 0Ch
0x18000c5d1  mov     rcx, [rcx+10h]
0x18000c5d5  lea     r8, WPP_18a7ed7453dd33af20c1feb47c4ff862_Traceguids
0x18000c5dc  mov     r9d, eax
0x18000c5df  call    WPP_SF_d
0x18000c5e4  mov     rsi, [rsp+28h+arg_10]
0x18000c5e9  mov     eax, ebx
0x18000c5eb  mov     rbx, [rsp+28h+arg_0]
0x18000c5f0  add     rsp, 20h
0x18000c5f4  pop     rdi
0x18000c5f5  retn
```
