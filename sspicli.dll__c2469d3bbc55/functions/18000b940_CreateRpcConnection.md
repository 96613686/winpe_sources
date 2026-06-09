# CreateRpcConnection

- ea: `0x18000b940`
- end: `0x18000b9eb`
- name: `CreateRpcConnection`
- size: `171`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180008730`
- `0x18000b7b0`
- `0x180010380`

## callees

- `0x18000b940`
- `0x18000b9f4`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x1800223de`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800223de`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000b9bb`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000b9bb`
- `RPCRT4!RpcBindingUnbind` at `0x18000b9cc`
- `RPCRT4!RpcBindingUnbind` at `0x18000b9cc`
- `RPCRT4!RpcBindingFree` at `0x18000b9d7`
- `RPCRT4!RpcBindingFree` at `0x18000b9d7`
- `RPCRT4!NdrClientCall3` at `0x18000b9a5`
- `RPCRT4!NdrClientCall3` at `0x18000b9a5`

## pseudocode

```c
__int64 __fastcall CreateRpcConnection(__int64 a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 result; // rax
  CLIENT_CALL_RETURN v10; // rax
  unsigned int Pointer; // ebx
  int v12; // [rsp+28h] [rbp-70h]
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp-40h] BYREF
  CLIENT_CALL_RETURN v14; // [rsp+60h] [rbp-38h]

  Binding = 0;
  result = SecpGetRpcBinding(&Binding);
  if ( (int)result >= 0 )
  {
    v14.Simple = 0;
    v12 = a2;
    v10.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo, 0, 0, Binding, a1, v12, a5, a4, a3).Pointer;
    Pointer = (unsigned int)v10.Pointer;
    v14.Pointer = v10.Pointer;
    RpcBindingUnbind(Binding);
    RpcBindingFree(&Binding);
    return Pointer;
  }
  return result;
}

```

## disassembly

```asm
0x18000b940  push    rbx
0x18000b942  push    rsi
0x18000b943  push    rdi
0x18000b944  push    r14
0x18000b946  push    r15
0x18000b948  sub     rsp, 70h
0x18000b94c  mov     rdi, r9
0x18000b94f  mov     rsi, r8
0x18000b952  mov     r14d, edx
0x18000b955  mov     rbx, rcx
0x18000b958  xor     r15d, r15d
0x18000b95b  mov     [rsp+98h+Binding], r15
0x18000b960  lea     rcx, [rsp+98h+Binding]
0x18000b965  call    SecpGetRpcBinding
0x18000b96a  test    eax, eax
0x18000b96c  js      short loc_18000B9DF
0x18000b96e  mov     [rsp+98h+var_38], r15
0x18000b973  mov     [rsp+98h+var_58], rsi
0x18000b978  mov     [rsp+98h+var_60], rdi
0x18000b97d  mov     rax, [rsp+98h+arg_20]
0x18000b985  mov     [rsp+98h+var_68], rax
0x18000b98a  mov     [rsp+98h+var_70], r14d
0x18000b98f  mov     [rsp+98h+var_78], rbx
0x18000b994  mov     r9, [rsp+98h+Binding]
0x18000b999  xor     r8d, r8d; pReturnValue
0x18000b99c  xor     edx, edx; nProcNum
0x18000b99e  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000b9a5  call    cs:__imp_NdrClientCall3
0x18000b9ab  mov     rbx, rax
0x18000b9ae  mov     [rsp+98h+var_38], rax
0x18000b9b3  mov     [rsp+98h+var_48], eax
0x18000b9b7  jmp     short loc_18000B9C7
0x18000b9b9  mov     ecx, eax; Status
0x18000b9bb  call    cs:__imp_I_RpcMapWin32Status
0x18000b9c1  mov     ebx, eax
0x18000b9c3  mov     [rsp+98h+var_48], eax
0x18000b9c7  mov     rcx, [rsp+98h+Binding]; Binding
0x18000b9cc  call    cs:__imp_RpcBindingUnbind
0x18000b9d2  lea     rcx, [rsp+98h+Binding]; Binding
0x18000b9d7  call    cs:__imp_RpcBindingFree
0x18000b9dd  mov     eax, ebx
0x18000b9df  add     rsp, 70h
0x18000b9e3  pop     r15
0x18000b9e5  pop     r14
0x18000b9e7  pop     rdi
0x18000b9e8  pop     rsi
0x18000b9e9  pop     rbx
0x18000b9ea  retn
0x1800223d0  push    rbp
0x1800223d2  sub     rsp, 50h
0x1800223d6  mov     rbp, rdx
0x1800223d9  mov     rcx, [rcx]
0x1800223dc  mov     ecx, [rcx]; ExceptionCode
0x1800223de  call    cs:__imp_I_RpcExceptionFilter
0x1800223e4  nop
0x1800223e5  add     rsp, 50h
0x1800223e9  pop     rbp
0x1800223ea  retn
```
