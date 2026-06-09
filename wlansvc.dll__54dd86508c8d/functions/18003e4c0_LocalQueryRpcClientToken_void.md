# LocalQueryRpcClientToken(void * *)

- ea: `0x18003e4c0`
- end: `0x18003e664`
- name: `?LocalQueryRpcClientToken@@YAKPEAPEAX@Z`
- size: `420`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `34`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18003c850`
- `0x18003cae8`
- `0x18003ccc8`
- `0x18003ce8c`
- `0x18003d050`
- `0x18003d2a4`
- `0x18003d468`
- `0x18003d630`
- `0x18003de40`
- `0x18003dff0`
- `0x18003e120`
- `0x180083110`
- `0x1800954a0`
- `0x180097450`
- `0x180097c70`
- `0x1800a4970`
- `0x1800f53a0`
- `0x1800fa0b0`
- `0x18012423c`
- `0x1801243f8`
- `0x180124e30`
- `0x180127430`
- `0x180127590`
- `0x180129d30`
- `0x18012a5c0`
- `0x18012a760`
- `0x18012a8c0`
- `0x18012ae50`
- `0x18012b5f0`
- `0x180130120`
- `0x180130ba0`
- `0x1801335e0`
- `0x180133950`
- `0x1801c875c`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18003e4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e5b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e5b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003e506`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003e506`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003e51f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003e51f`
- `RPCRT4!RpcImpersonateClient` at `0x18003e4fa`
- `RPCRT4!RpcImpersonateClient` at `0x18003e4fa`
- `RPCRT4!RpcRevertToSelfEx` at `0x18003e537`
- `RPCRT4!RpcRevertToSelfEx` at `0x18003e537`

## pseudocode

```c
RPC_STATUS __fastcall LocalQueryRpcClientToken(void **a1)
{
  RPC_STATUS result; // eax
  unsigned int v3; // ebx
  HANDLE CurrentThread; // rax
  PVOID *v5; // rcx
  __int64 v6; // rdx
  DWORD LastError; // eax
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 30, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
  }
  result = RpcImpersonateClient(0);
  v3 = result;
  if ( !result )
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
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 32, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, LastError);
      }
    }
    result = RpcRevertToSelfEx(0);
    if ( !result )
      goto LABEL_7;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v3;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 105) && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v6 = 33;
      goto LABEL_26;
    }
    goto LABEL_8;
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 105) && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v6 = 31;
LABEL_26:
      WPP_SF_d(v5[12], v6, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, (unsigned int)result);
LABEL_7:
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_8:
    if ( v5 != &WPP_GLOBAL_Control && *((_BYTE *)v5 + 105) >= 4u && (*((_BYTE *)v5 + 108) & 1) != 0 )
      WPP_SF_d(v5[12], 34, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, v3);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x18003e4c0  mov     [rsp+arg_0], rbx
0x18003e4c5  mov     [rsp+arg_10], rsi
0x18003e4ca  push    rdi
0x18003e4cb  sub     rsp, 20h
0x18003e4cf  mov     rdi, rcx
0x18003e4d2  mov     [rsp+28h+TokenHandle], 0
0x18003e4db  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e4e2  lea     rsi, WPP_GLOBAL_Control
0x18003e4e9  cmp     rcx, rsi
0x18003e4ec  jz      short loc_18003E4F8
0x18003e4ee  cmp     byte ptr [rcx+69h], 4
0x18003e4f2  jnb     loc_18003E58F
0x18003e4f8  xor     ecx, ecx; BindingHandle
0x18003e4fa  call    cs:__imp_RpcImpersonateClient
0x18003e500  mov     ebx, eax
0x18003e502  test    eax, eax
0x18003e504  jnz     short loc_18003E56D
0x18003e506  call    cs:__imp_GetCurrentThread
0x18003e50c  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18003e511  mov     edx, 0F01FFh; DesiredAccess
0x18003e516  mov     rcx, rax; ThreadHandle
0x18003e519  mov     r8d, 1; OpenAsSelf
0x18003e51f  call    cs:__imp_OpenThreadToken
0x18003e525  test    eax, eax
0x18003e527  jz      loc_18003E5B3
0x18003e52d  mov     rax, [rsp+28h+TokenHandle]
0x18003e532  mov     [rdi], rax
0x18003e535  xor     ecx, ecx; BindingHandle
0x18003e537  call    cs:__imp_RpcRevertToSelfEx
0x18003e53d  test    eax, eax
0x18003e53f  jnz     loc_18003E5FC
0x18003e545  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e54c  cmp     rcx, rsi
0x18003e54f  jz      short loc_18003E55B
0x18003e551  cmp     byte ptr [rcx+69h], 4
0x18003e555  jnb     loc_18003E63D
0x18003e55b  mov     eax, ebx
0x18003e55d  mov     rbx, [rsp+28h+arg_0]
0x18003e562  mov     rsi, [rsp+28h+arg_10]
0x18003e567  add     rsp, 20h
0x18003e56b  pop     rdi
0x18003e56c  retn
0x18003e56d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e574  cmp     rcx, rsi
0x18003e577  jz      short loc_18003E55D
0x18003e579  cmp     byte ptr [rcx+69h], 1
0x18003e57d  jb      short loc_18003E54C
0x18003e57f  test    byte ptr [rcx+6Ch], 1
0x18003e583  jz      short loc_18003E54C
0x18003e585  mov     edx, 1Fh
0x18003e58a  jmp     loc_18003E625
0x18003e58f  test    byte ptr [rcx+6Ch], 1
0x18003e593  jz      loc_18003E4F8
0x18003e599  mov     rcx, [rcx+60h]
0x18003e59d  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003e5a4  mov     edx, 1Eh
0x18003e5a9  call    WPP_SF_
0x18003e5ae  jmp     loc_18003E4F8
0x18003e5b3  call    cs:__imp_GetLastError
0x18003e5b9  mov     ebx, eax
0x18003e5bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e5c2  cmp     rcx, rsi
0x18003e5c5  jz      loc_18003E535
0x18003e5cb  cmp     byte ptr [rcx+69h], 1
0x18003e5cf  jb      loc_18003E535
0x18003e5d5  test    byte ptr [rcx+6Ch], 1
0x18003e5d9  jz      loc_18003E535
0x18003e5df  mov     rcx, [rcx+60h]
0x18003e5e3  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003e5ea  mov     edx, 20h ; ' '
0x18003e5ef  mov     r9d, eax
0x18003e5f2  call    WPP_SF_d
0x18003e5f7  jmp     loc_18003E535
0x18003e5fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e603  cmp     rcx, rsi
0x18003e606  jz      loc_18003E55B
0x18003e60c  cmp     byte ptr [rcx+69h], 1
0x18003e610  jb      loc_18003E54C
0x18003e616  test    byte ptr [rcx+6Ch], 1
0x18003e61a  jz      loc_18003E54C
0x18003e620  mov     edx, 21h ; '!'
0x18003e625  mov     rcx, [rcx+60h]
0x18003e629  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003e630  mov     r9d, eax
0x18003e633  call    WPP_SF_d
0x18003e638  jmp     loc_18003E545
0x18003e63d  test    byte ptr [rcx+6Ch], 1
0x18003e641  jz      loc_18003E55B
0x18003e647  mov     rcx, [rcx+60h]
0x18003e64b  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003e652  mov     edx, 22h ; '"'
0x18003e657  mov     r9d, ebx
0x18003e65a  call    WPP_SF_d
0x18003e65f  jmp     loc_18003E55B
```
