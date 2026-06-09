# DfsDsIsDomainController

- ea: `0x180025d70`
- end: `0x180025e12`
- name: `DfsDsIsDomainController`
- size: `162`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, RPC_BINDING_HANDLE BindingHandle, __int64, __int64, _BYTE *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180025d70`
- `0x180025e18`

## import_xrefs

- `ntdll!DbgPrint` at `0x180025dae`
- `ntdll!DbgPrint` at `0x180025de2`
- `ntdll!DbgPrint` at `0x180025dae`
- `ntdll!DbgPrint` at `0x180025de2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180025df1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180025df1`
- `RPCRT4!RpcServerTestCancel` at `0x180025d8d`
- `RPCRT4!RpcServerTestCancel` at `0x180025d8d`
- `RPCRT4!RpcAsyncAbortCall` at `0x180025d9f`
- `RPCRT4!RpcAsyncAbortCall` at `0x180025e03`
- `RPCRT4!RpcAsyncAbortCall` at `0x180025d9f`
- `RPCRT4!RpcAsyncAbortCall` at `0x180025e03`

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
0x180025d70  push    rbx
0x180025d72  push    rbp
0x180025d73  push    rsi
0x180025d74  push    rdi
0x180025d75  sub     rsp, 28h
0x180025d79  mov     rdi, [rsp+48h+arg_20]
0x180025d7e  mov     rbx, rcx
0x180025d81  mov     rcx, rdx; BindingHandle
0x180025d84  mov     rsi, r9
0x180025d87  mov     rbp, r8
0x180025d8a  mov     byte ptr [rdi], 0
0x180025d8d  call    cs:__imp_RpcServerTestCancel
0x180025d93  test    eax, eax
0x180025d95  jnz     short loc_180025DB6
0x180025d97  mov     edx, 71Ah; ExceptionCode
0x180025d9c  mov     rcx, rbx; pAsync
0x180025d9f  call    cs:__imp_RpcAsyncAbortCall
0x180025da5  mov     edx, eax
0x180025da7  lea     rcx, aDfsdsisdomainc; "DfsDsIsDomainController: RPC has been c"...
0x180025dae  call    cs:__imp_DbgPrint
0x180025db4  jmp     short loc_180025DEC
0x180025db6  test    rsi, rsi
0x180025db9  jz      short loc_180025DF9
0x180025dbb  test    rbp, rbp
0x180025dbe  jz      short loc_180025DF9
0x180025dc0  mov     r8, rdi
0x180025dc3  mov     rdx, rsi
0x180025dc6  mov     rcx, rbp
0x180025dc9  call    IsDomainController
0x180025dce  mov     r9, [rbp+8]
0x180025dd2  lea     rcx, aDfsdsisdomainc_0; "DfsDsIsDomainController returns %ws wit"...
0x180025dd9  mov     rdx, [rsi+8]
0x180025ddd  mov     r8d, eax
0x180025de0  mov     edi, eax
0x180025de2  call    cs:__imp_DbgPrint
0x180025de8  test    edi, edi
0x180025dea  jnz     short loc_180025DFE
0x180025dec  xor     edx, edx; Reply
0x180025dee  mov     rcx, rbx; pAsync
0x180025df1  call    cs:__imp_RpcAsyncCompleteCall
0x180025df7  jmp     short loc_180025E09
0x180025df9  mov     edi, 57h ; 'W'
0x180025dfe  mov     edx, edi; ExceptionCode
0x180025e00  mov     rcx, rbx; pAsync
0x180025e03  call    cs:__imp_RpcAsyncAbortCall
0x180025e09  add     rsp, 28h
0x180025e0d  pop     rdi
0x180025e0e  pop     rsi
0x180025e0f  pop     rbp
0x180025e10  pop     rbx
0x180025e11  retn
```
