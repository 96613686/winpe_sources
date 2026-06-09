# LsapCreateBindingHandleForLocal

- ea: `0x180016eb0`
- end: `0x180016f72`
- name: `LsapCreateBindingHandleForLocal`
- size: `194`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014a30`
- `0x180021c10`
- `0x180021c50`
- `0x180021c90`

## callees

- `0x180016eb0`
- `0x180022190`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x180016f50`
- `RPCRT4!I_RpcMapWin32Status` at `0x180016f50`
- `RPCRT4!RpcBindingFree` at `0x180016f3f`
- `RPCRT4!RpcBindingFree` at `0x180016f3f`
- `RPCRT4!RpcBindingBind` at `0x180016f29`
- `RPCRT4!RpcBindingBind` at `0x180016f29`
- `RPCRT4!RpcBindingCreateW` at `0x180016f14`
- `RPCRT4!RpcBindingCreateW` at `0x180016f14`

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
0x180016eb0  mov     [rsp-18h+arg_18], rbx
0x180016eb5  push    rbp
0x180016eb6  push    rsi
0x180016eb7  push    rdi
0x180016eb8  mov     rbp, rsp
0x180016ebb  sub     rsp, 70h
0x180016ebf  mov     rax, cs:__security_cookie
0x180016ec6  xor     rax, rsp
0x180016ec9  mov     [rbp+var_10], rax
0x180016ecd  xorps   xmm0, xmm0
0x180016ed0  mov     [rbp+Binding], 0
0x180016ed8  movups  xmmword ptr [rbp+Template.Version], xmm0
0x180016edc  mov     rsi, r8
0x180016edf  mov     rdi, rdx
0x180016ee2  movups  xmmword ptr [rbp+Template.NetworkAddress], xmm0
0x180016ee6  mov     [rbp+Template.StringEndpoint], rcx
0x180016eea  lea     r9, [rbp+Binding]; Binding
0x180016eee  xor     eax, eax
0x180016ef0  mov     [rbp+Template.Version], 1
0x180016ef7  lea     rcx, [rbp+Template]; Template
0x180016efb  mov     qword ptr [rbp+Template.ObjectUuid.Data4], rax
0x180016eff  xor     r8d, r8d; Options
0x180016f02  mov     [rbp+Template.ProtocolSequence], 3
0x180016f09  lea     rdx, g_LsapBindingHandleSecurity; Security
0x180016f10  movups  xmmword ptr [rbp+Template.u1], xmm0
0x180016f14  call    cs:__imp_RpcBindingCreateW
0x180016f1a  mov     ebx, eax
0x180016f1c  test    eax, eax
0x180016f1e  jnz     short loc_180016F3B
0x180016f20  mov     rdx, [rbp+Binding]; Binding
0x180016f24  mov     r8, rdi; IfSpec
0x180016f27  xor     ecx, ecx; pAsync
0x180016f29  call    cs:__imp_RpcBindingBind
0x180016f2f  mov     ebx, eax
0x180016f31  test    eax, eax
0x180016f33  jnz     short loc_180016F3B
0x180016f35  mov     rax, [rbp+Binding]
0x180016f39  jmp     short loc_180016F4B
0x180016f3b  lea     rcx, [rbp+Binding]; Binding
0x180016f3f  call    cs:__imp_RpcBindingFree
0x180016f45  xor     eax, eax
0x180016f47  mov     [rbp+Binding], rax
0x180016f4b  mov     ecx, ebx; Status
0x180016f4d  mov     [rsi], rax
0x180016f50  call    cs:__imp_I_RpcMapWin32Status
0x180016f56  mov     rcx, [rbp+var_10]
0x180016f5a  xor     rcx, rsp; StackCookie
0x180016f5d  call    __security_check_cookie
0x180016f62  mov     rbx, [rsp+70h+arg_18]
0x180016f6a  add     rsp, 70h
0x180016f6e  pop     rdi
0x180016f6f  pop     rsi
0x180016f70  pop     rbp
0x180016f71  retn
```
