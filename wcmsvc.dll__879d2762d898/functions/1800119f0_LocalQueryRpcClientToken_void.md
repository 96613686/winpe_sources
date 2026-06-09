# LocalQueryRpcClientToken(void * *)

- ea: `0x1800119f0`
- end: `0x180011ba9`
- name: `?LocalQueryRpcClientToken@@YAKPEAPEAX@Z`
- size: `441`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800116e0`
- `0x1800aa264`
- `0x1800aa920`
- `0x1800aa9e4`
- `0x1800aaab4`

## callees

- `0x1800119f0`
- `0x180011bb0`
- `0x180011c20`
- `0x1800137a0`
- `0x180084f50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b1f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180011a81`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180011a81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011a68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011a68`
- `RPCRT4!RpcRevertToSelfEx` at `0x180011a99`
- `RPCRT4!RpcRevertToSelfEx` at `0x180011a99`
- `RPCRT4!RpcImpersonateClient` at `0x180011a58`
- `RPCRT4!RpcImpersonateClient` at `0x180011a58`

## string_xrefs

- `0x180011a3b`: `LocalQueryRpcClientToken`
- `0x180011ae2`: `LocalQueryRpcClientToken`

## pseudocode

```c
RPC_STATUS __fastcall LocalQueryRpcClientToken(void **a1)
{
  RPC_STATUS result; // eax
  unsigned int v3; // edi
  HANDLE CurrentThread; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  DWORD LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp-18h] BYREF

  TokenHandle = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      25,
      WPP_59cb1c30c417333f98d499625c161da5_Traceguids,
      "LocalQueryRpcClientToken");
  }
  *a1 = 0;
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
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 27, WPP_59cb1c30c417333f98d499625c161da5_Traceguids, LastError);
      }
    }
    result = RpcRevertToSelfEx(0);
    if ( !result )
      goto LABEL_9;
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v3;
    if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v6 = 28;
      goto LABEL_28;
    }
    goto LABEL_10;
  }
  v5 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v6 = 26;
LABEL_28:
      WPP_SF_d(*(_QWORD *)(v5 + 16), v6, WPP_59cb1c30c417333f98d499625c161da5_Traceguids, (unsigned int)result);
LABEL_9:
      v5 = WPP_GLOBAL_Control;
    }
LABEL_10:
    if ( (_UNKNOWN *)v5 != &WPP_GLOBAL_Control && *(_BYTE *)(v5 + 25) >= 5u && (*(_BYTE *)(v5 + 28) & 1) != 0 )
      WPP_SF_sL(
        *(_QWORD *)(v5 + 16),
        29,
        (unsigned int)WPP_59cb1c30c417333f98d499625c161da5_Traceguids,
        (unsigned int)"LocalQueryRpcClientToken",
        v3);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x1800119f0  mov     [rsp+arg_8], rbx
0x1800119f5  mov     [rsp+arg_10], rsi
0x1800119fa  push    rdi
0x1800119fb  sub     rsp, 40h
0x1800119ff  mov     rax, cs:__security_cookie
0x180011a06  xor     rax, rsp
0x180011a09  mov     [rsp+48h+var_10], rax
0x180011a0e  xor     edi, edi
0x180011a10  mov     rbx, rcx
0x180011a13  mov     [rsp+48h+TokenHandle], rdi
0x180011a18  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a1f  lea     rsi, WPP_GLOBAL_Control
0x180011a26  cmp     rcx, rsi
0x180011a29  jz      short loc_180011A53
0x180011a2b  cmp     byte ptr [rcx+19h], 5
0x180011a2f  jb      short loc_180011A53
0x180011a31  test    byte ptr [rcx+1Ch], 1
0x180011a35  jz      short loc_180011A53
0x180011a37  mov     rcx, [rcx+10h]
0x180011a3b  lea     r9, aLocalqueryrpcc; "LocalQueryRpcClientToken"
0x180011a42  mov     edx, 19h
0x180011a47  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x180011a4e  call    WPP_SF_s
0x180011a53  xor     ecx, ecx; BindingHandle
0x180011a55  mov     [rbx], rdi
0x180011a58  call    cs:__imp_RpcImpersonateClient
0x180011a5e  mov     edi, eax
0x180011a60  test    eax, eax
0x180011a62  jnz     loc_180011B00
0x180011a68  call    cs:__imp_GetCurrentThread
0x180011a6e  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180011a73  mov     edx, 0F01FFh; DesiredAccess
0x180011a78  mov     rcx, rax; ThreadHandle
0x180011a7b  mov     r8d, 1; OpenAsSelf
0x180011a81  call    cs:__imp_OpenThreadToken
0x180011a87  test    eax, eax
0x180011a89  jz      loc_180011B1F
0x180011a8f  mov     rax, [rsp+48h+TokenHandle]
0x180011a94  mov     [rbx], rax
0x180011a97  xor     ecx, ecx; BindingHandle
0x180011a99  call    cs:__imp_RpcRevertToSelfEx
0x180011a9f  test    eax, eax
0x180011aa1  jnz     loc_180011B68
0x180011aa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180011aae  cmp     rcx, rsi
0x180011ab1  jnz     short loc_180011AD2
0x180011ab3  mov     eax, edi
0x180011ab5  mov     rcx, [rsp+48h+var_10]
0x180011aba  xor     rcx, rsp; StackCookie
0x180011abd  call    __security_check_cookie
0x180011ac2  mov     rbx, [rsp+48h+arg_8]
0x180011ac7  mov     rsi, [rsp+48h+arg_10]
0x180011acc  add     rsp, 40h
0x180011ad0  pop     rdi
0x180011ad1  retn
0x180011ad2  cmp     byte ptr [rcx+19h], 5
0x180011ad6  jb      short loc_180011AB3
0x180011ad8  test    byte ptr [rcx+1Ch], 1
0x180011adc  jz      short loc_180011AB3
0x180011ade  mov     rcx, [rcx+10h]
0x180011ae2  lea     r9, aLocalqueryrpcc; "LocalQueryRpcClientToken"
0x180011ae9  mov     edx, 1Dh
0x180011aee  mov     [rsp+48h+var_28], edi
0x180011af2  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x180011af9  call    WPP_SF_sL
0x180011afe  jmp     short loc_180011AB3
0x180011b00  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b07  cmp     rcx, rsi
0x180011b0a  jz      short loc_180011AB5
0x180011b0c  cmp     byte ptr [rcx+19h], 1
0x180011b10  jb      short loc_180011AAE
0x180011b12  test    byte ptr [rcx+1Ch], 1
0x180011b16  jz      short loc_180011AAE
0x180011b18  mov     edx, 1Ah
0x180011b1d  jmp     short loc_180011B91
0x180011b1f  call    cs:__imp_GetLastError
0x180011b25  mov     edi, eax
0x180011b27  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b2e  cmp     rcx, rsi
0x180011b31  jz      loc_180011A97
0x180011b37  cmp     byte ptr [rcx+19h], 1
0x180011b3b  jb      loc_180011A97
0x180011b41  test    byte ptr [rcx+1Ch], 1
0x180011b45  jz      loc_180011A97
0x180011b4b  mov     rcx, [rcx+10h]
0x180011b4f  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x180011b56  mov     edx, 1Bh
0x180011b5b  mov     r9d, eax
0x180011b5e  call    WPP_SF_d
0x180011b63  jmp     loc_180011A97
0x180011b68  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b6f  cmp     rcx, rsi
0x180011b72  jz      loc_180011AB3
0x180011b78  cmp     byte ptr [rcx+19h], 1
0x180011b7c  jb      loc_180011AAE
0x180011b82  test    byte ptr [rcx+1Ch], 1
0x180011b86  jz      loc_180011AAE
0x180011b8c  mov     edx, 1Ch
0x180011b91  mov     rcx, [rcx+10h]
0x180011b95  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x180011b9c  mov     r9d, eax
0x180011b9f  call    WPP_SF_d
0x180011ba4  jmp     loc_180011AA7
```
