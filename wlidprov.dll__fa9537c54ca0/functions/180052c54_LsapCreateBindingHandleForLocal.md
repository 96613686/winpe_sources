# LsapCreateBindingHandleForLocal

- ea: `0x180052c54`
- end: `0x180052d16`
- name: `LsapCreateBindingHandleForLocal`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180052b98`

## callees

- `0x18001a0d0`
- `0x180052c54`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x180052cb8`
- `RPCRT4!RpcBindingCreateW` at `0x180052cb8`
- `RPCRT4!RpcBindingBind` at `0x180052ccd`
- `RPCRT4!RpcBindingBind` at `0x180052ccd`
- `RPCRT4!I_RpcMapWin32Status` at `0x180052cf4`
- `RPCRT4!I_RpcMapWin32Status` at `0x180052cf4`
- `RPCRT4!RpcBindingFree` at `0x180052ce3`
- `RPCRT4!RpcBindingFree` at `0x180052ce3`

## pseudocode

```c
int __fastcall LsapCreateBindingHandleForLocal(unsigned __int16 *a1, void *a2, _QWORD *a3)
{
  RPC_STATUS v5; // ebx
  RPC_BINDING_HANDLE v6; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-50h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+28h] [rbp-48h] BYREF

  Binding = 0;
  memset(&Template, 0, 24);
  Template.StringEndpoint = a1;
  Template.Version = 1;
  Template.ProtocolSequence = 3;
  memset(&Template.u1, 0, 24);
  v5 = RpcBindingCreateW(&Template, (RPC_BINDING_HANDLE_SECURITY_V1_W *)&g_LsapBindingHandleSecurity, 0, &Binding);
  if ( v5 || (v5 = RpcBindingBind(0, Binding, a2)) != 0 )
  {
    RpcBindingFree(&Binding);
    v6 = 0;
    Binding = 0;
  }
  else
  {
    v6 = Binding;
  }
  *a3 = v6;
  return I_RpcMapWin32Status(v5);
}

```

## disassembly

```asm
0x180052c54  mov     [rsp-18h+arg_18], rbx
0x180052c59  push    rbp
0x180052c5a  push    rsi
0x180052c5b  push    rdi
0x180052c5c  mov     rbp, rsp
0x180052c5f  sub     rsp, 70h
0x180052c63  mov     rax, cs:__security_cookie
0x180052c6a  xor     rax, rsp
0x180052c6d  mov     [rbp+var_10], rax
0x180052c71  xorps   xmm0, xmm0
0x180052c74  mov     [rbp+Binding], 0
0x180052c7c  movups  xmmword ptr [rbp+Template.Version], xmm0
0x180052c80  mov     rsi, r8
0x180052c83  mov     rdi, rdx
0x180052c86  movups  xmmword ptr [rbp+Template.NetworkAddress], xmm0
0x180052c8a  mov     [rbp+Template.StringEndpoint], rcx
0x180052c8e  lea     r9, [rbp+Binding]; Binding
0x180052c92  xor     eax, eax
0x180052c94  mov     [rbp+Template.Version], 1
0x180052c9b  lea     rcx, [rbp+Template]; Template
0x180052c9f  mov     qword ptr [rbp+Template.ObjectUuid.Data4], rax
0x180052ca3  xor     r8d, r8d; Options
0x180052ca6  mov     [rbp+Template.ProtocolSequence], 3
0x180052cad  lea     rdx, g_LsapBindingHandleSecurity; Security
0x180052cb4  movups  xmmword ptr [rbp+Template.u1], xmm0
0x180052cb8  call    cs:__imp_RpcBindingCreateW
0x180052cbe  mov     ebx, eax
0x180052cc0  test    eax, eax
0x180052cc2  jnz     short loc_180052CDF
0x180052cc4  mov     rdx, [rbp+Binding]; Binding
0x180052cc8  mov     r8, rdi; IfSpec
0x180052ccb  xor     ecx, ecx; pAsync
0x180052ccd  call    cs:__imp_RpcBindingBind
0x180052cd3  mov     ebx, eax
0x180052cd5  test    eax, eax
0x180052cd7  jnz     short loc_180052CDF
0x180052cd9  mov     rax, [rbp+Binding]
0x180052cdd  jmp     short loc_180052CEF
0x180052cdf  lea     rcx, [rbp+Binding]; Binding
0x180052ce3  call    cs:__imp_RpcBindingFree
0x180052ce9  xor     eax, eax
0x180052ceb  mov     [rbp+Binding], rax
0x180052cef  mov     ecx, ebx; Status
0x180052cf1  mov     [rsi], rax
0x180052cf4  call    cs:__imp_I_RpcMapWin32Status
0x180052cfa  mov     rcx, [rbp+var_10]
0x180052cfe  xor     rcx, rsp; StackCookie
0x180052d01  call    __security_check_cookie
0x180052d06  mov     rbx, [rsp+70h+arg_18]
0x180052d0e  add     rsp, 70h
0x180052d12  pop     rdi
0x180052d13  pop     rsi
0x180052d14  pop     rbp
0x180052d15  retn
```
