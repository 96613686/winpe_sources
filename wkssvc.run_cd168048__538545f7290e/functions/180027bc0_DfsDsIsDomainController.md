# DfsDsIsDomainController

- ea: `0x180027bc0`
- end: `0x180027c87`
- name: `DfsDsIsDomainController`
- size: `199`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, RPC_BINDING_HANDLE BindingHandle@<rdx>, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180027bc0`
- `0x180027c90`

## import_xrefs

- `ntdll!DbgPrint` at `0x180027c0a`
- `ntdll!DbgPrint` at `0x180027c44`
- `ntdll!DbgPrint` at `0x180027c0a`
- `ntdll!DbgPrint` at `0x180027c44`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180027c59`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180027c59`
- `RPCRT4!RpcServerTestCancel` at `0x180027bdd`
- `RPCRT4!RpcServerTestCancel` at `0x180027bdd`
- `RPCRT4!RpcAsyncAbortCall` at `0x180027bf5`
- `RPCRT4!RpcAsyncAbortCall` at `0x180027c71`
- `RPCRT4!RpcAsyncAbortCall` at `0x180027bf5`
- `RPCRT4!RpcAsyncAbortCall` at `0x180027c71`

## pseudocode

```c
RPC_STATUS __fastcall DfsDsIsDomainController(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE BindingHandle,
        __int64 a3,
        __int64 a4,
        _BYTE *a5)
{
  RPC_STATUS v8; // eax
  __int64 v9; // rdi

  *a5 = 0;
  if ( !RpcServerTestCancel(BindingHandle) )
  {
    v8 = RpcAsyncAbortCall(pAsync, 0x71Au);
    DbgPrint("DfsDsIsDomainController: RPC has been cancelled by client %X\n", v8);
    return RpcAsyncCompleteCall(pAsync, 0);
  }
  if ( a4 && a3 )
  {
    v9 = (unsigned int)IsDomainController(a3, a4, a5);
    DbgPrint(
      "DfsDsIsDomainController returns %ws with error %X for domain %ws\n",
      *(_QWORD *)(a4 + 8),
      v9,
      *(_QWORD *)(a3 + 8));
    if ( !(_DWORD)v9 )
      return RpcAsyncCompleteCall(pAsync, 0);
  }
  else
  {
    LODWORD(v9) = 87;
  }
  return RpcAsyncAbortCall(pAsync, v9);
}

```

## disassembly

```asm
0x180027bc0  push    rbx
0x180027bc2  push    rbp
0x180027bc3  push    rsi
0x180027bc4  push    rdi
0x180027bc5  sub     rsp, 28h
0x180027bc9  mov     rdi, [rsp+48h+arg_20]
0x180027bce  mov     rbx, rcx
0x180027bd1  mov     rcx, rdx; BindingHandle
0x180027bd4  mov     rsi, r9
0x180027bd7  mov     rbp, r8
0x180027bda  mov     byte ptr [rdi], 0
0x180027bdd  call    cs:__imp_RpcServerTestCancel
0x180027be4  nop     dword ptr [rax+rax+00h]
0x180027be9  test    eax, eax
0x180027beb  jnz     short loc_180027C18
0x180027bed  mov     edx, 71Ah; ExceptionCode
0x180027bf2  mov     rcx, rbx; pAsync
0x180027bf5  call    cs:__imp_RpcAsyncAbortCall
0x180027bfc  nop     dword ptr [rax+rax+00h]
0x180027c01  mov     edx, eax
0x180027c03  lea     rcx, aDfsdsisdomainc; "DfsDsIsDomainController: RPC has been c"...
0x180027c0a  call    cs:__imp_DbgPrint
0x180027c11  nop     dword ptr [rax+rax+00h]
0x180027c16  jmp     short loc_180027C54
0x180027c18  test    rsi, rsi
0x180027c1b  jz      short loc_180027C67
0x180027c1d  test    rbp, rbp
0x180027c20  jz      short loc_180027C67
0x180027c22  mov     r8, rdi
0x180027c25  mov     rdx, rsi
0x180027c28  mov     rcx, rbp
0x180027c2b  call    IsDomainController
0x180027c30  mov     r9, [rbp+8]
0x180027c34  lea     rcx, aDfsdsisdomainc_0; "DfsDsIsDomainController returns %ws wit"...
0x180027c3b  mov     rdx, [rsi+8]
0x180027c3f  mov     r8d, eax
0x180027c42  mov     edi, eax
0x180027c44  call    cs:__imp_DbgPrint
0x180027c4b  nop     dword ptr [rax+rax+00h]
0x180027c50  test    edi, edi
0x180027c52  jnz     short loc_180027C6C
0x180027c54  xor     edx, edx; Reply
0x180027c56  mov     rcx, rbx; pAsync
0x180027c59  call    cs:__imp_RpcAsyncCompleteCall
0x180027c60  nop     dword ptr [rax+rax+00h]
0x180027c65  jmp     short loc_180027C7D
0x180027c67  mov     edi, 57h ; 'W'
0x180027c6c  mov     edx, edi; ExceptionCode
0x180027c6e  mov     rcx, rbx; pAsync
0x180027c71  call    cs:__imp_RpcAsyncAbortCall
0x180027c78  nop     dword ptr [rax+rax+00h]
0x180027c7d  add     rsp, 28h
0x180027c81  pop     rdi
0x180027c82  pop     rsi
0x180027c83  pop     rbp
0x180027c84  pop     rbx
0x180027c85  retn
```
