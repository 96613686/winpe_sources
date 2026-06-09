# LsapCreateBindingHandleForLocal

- ea: `0x180014fcc`
- end: `0x18001508d`
- name: `LsapCreateBindingHandleForLocal`
- size: `193`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003eff8`
- `0x18003f020`
- `0x18003f060`

## callees

- `0x180014fcc`
- `0x18001cbd1`
- `0x18004fa50`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18001507f`
- `RPCRT4!RpcBindingFree` at `0x18001507f`
- `RPCRT4!RpcBindingCreateW` at `0x180015030`
- `RPCRT4!RpcBindingCreateW` at `0x180015030`
- `RPCRT4!I_RpcMapWin32Status` at `0x180015059`
- `RPCRT4!I_RpcMapWin32Status` at `0x180015059`

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
  if ( v5 || (v5 = RpcBindingBind_0(0, Binding, a2)) != 0 )
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
0x180014fcc  mov     [rsp-18h+arg_18], rbx
0x180014fd1  push    rbp
0x180014fd2  push    rsi
0x180014fd3  push    rdi
0x180014fd4  mov     rbp, rsp
0x180014fd7  sub     rsp, 70h
0x180014fdb  mov     rax, cs:__security_cookie
0x180014fe2  xor     rax, rsp
0x180014fe5  mov     [rbp+var_10], rax
0x180014fe9  xorps   xmm0, xmm0
0x180014fec  mov     [rbp+Binding], 0
0x180014ff4  movups  xmmword ptr [rbp+Template.Version], xmm0
0x180014ff8  mov     rsi, r8
0x180014ffb  mov     rdi, rdx
0x180014ffe  movups  xmmword ptr [rbp+Template.NetworkAddress], xmm0
0x180015002  mov     [rbp+Template.StringEndpoint], rcx
0x180015006  lea     r9, [rbp+Binding]; Binding
0x18001500a  xor     eax, eax
0x18001500c  mov     [rbp+Template.Version], 1
0x180015013  lea     rcx, [rbp+Template]; Template
0x180015017  mov     qword ptr [rbp+Template.ObjectUuid.Data4], rax
0x18001501b  xor     r8d, r8d; Options
0x18001501e  mov     [rbp+Template.ProtocolSequence], 3
0x180015025  lea     rdx, g_LsapBindingHandleSecurity; Security
0x18001502c  movups  xmmword ptr [rbp+Template.u1], xmm0
0x180015030  call    cs:__imp_RpcBindingCreateW
0x180015036  mov     ebx, eax
0x180015038  test    eax, eax
0x18001503a  jnz     short loc_18001507B
0x18001503c  mov     rdx, [rbp+Binding]; Binding
0x180015040  mov     r8, rdi; IfSpec
0x180015043  xor     ecx, ecx; pAsync
0x180015045  call    RpcBindingBind_0
0x18001504a  mov     ebx, eax
0x18001504c  test    eax, eax
0x18001504e  jnz     short loc_18001507B
0x180015050  mov     rax, [rbp+Binding]
0x180015054  mov     ecx, ebx; Status
0x180015056  mov     [rsi], rax
0x180015059  call    cs:__imp_I_RpcMapWin32Status
0x18001505f  mov     rcx, [rbp+var_10]
0x180015063  xor     rcx, rsp; StackCookie
0x180015066  call    __security_check_cookie
0x18001506b  mov     rbx, [rsp+70h+arg_18]
0x180015073  add     rsp, 70h
0x180015077  pop     rdi
0x180015078  pop     rsi
0x180015079  pop     rbp
0x18001507a  retn
0x18001507b  lea     rcx, [rbp+Binding]; Binding
0x18001507f  call    cs:__imp_RpcBindingFree
0x180015085  xor     eax, eax
0x180015087  mov     [rbp+Binding], rax
0x18001508b  jmp     short loc_180015054
```
