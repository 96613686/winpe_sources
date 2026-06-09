# PLSAPR_SERVER_NAME_bind

- ea: `0x1800136d0`
- end: `0x1800137af`
- name: `PLSAPR_SERVER_NAME_bind`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800136d0`
- `0x1800137b8`
- `0x18001cbd1`
- `0x18004fa50`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x1800137a1`
- `RPCRT4!RpcBindingFree` at `0x1800137a1`
- `RPCRT4!RpcBindingCreateW` at `0x180013740`
- `RPCRT4!RpcBindingCreateW` at `0x180013740`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001376e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001376e`

## pseudocode

```c
RPC_BINDING_HANDLE __fastcall PLSAPR_SERVER_NAME_bind(char *a1, __int64 a2, __int64 a3)
{
  RPC_STATUS v3; // ebx
  RPC_BINDING_HANDLE v4; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-50h] BYREF
  RPC_BINDING_HANDLE v7; // [rsp+28h] [rbp-48h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+30h] [rbp-40h] BYREF

  v7 = 0;
  if ( a1 )
  {
    RpcpBindRpc(a1, a2, a3, &v7);
  }
  else
  {
    Binding = 0;
    memset(&Template, 0, 24);
    Template.Version = 1;
    Template.StringEndpoint = L"LSARPC_ENDPOINT";
    Template.ProtocolSequence = 3;
    memset(&Template.u1, 0, 24);
    v3 = RpcBindingCreateW(&Template, (RPC_BINDING_HANDLE_SECURITY_V1_W *)&g_LsapBindingHandleSecurity, 0, &Binding);
    if ( v3 || (v3 = RpcBindingBind_0(0, Binding, qword_180052460)) != 0 )
    {
      RpcBindingFree(&Binding);
      v4 = 0;
      Binding = 0;
    }
    else
    {
      v4 = Binding;
    }
    v7 = v4;
    I_RpcMapWin32Status(v3);
  }
  return v7;
}

```

## disassembly

```asm
0x1800136d0  mov     [rsp-8+arg_8], rbx
0x1800136d5  push    rbp
0x1800136d6  mov     rbp, rsp
0x1800136d9  sub     rsp, 70h
0x1800136dd  mov     rax, cs:__security_cookie
0x1800136e4  xor     rax, rsp
0x1800136e7  mov     [rbp+var_8], rax
0x1800136eb  mov     [rbp+var_48], 0
0x1800136f3  test    rcx, rcx
0x1800136f6  jnz     loc_180013792
0x1800136fc  xorps   xmm0, xmm0
0x1800136ff  mov     [rbp+Binding], rcx
0x180013703  xor     eax, eax
0x180013705  lea     r9, [rbp+Binding]; Binding
0x180013709  movups  xmmword ptr [rbp+Template.Version], xmm0
0x18001370d  mov     qword ptr [rbp+Template.ObjectUuid.Data4], rax
0x180013711  lea     rdx, g_LsapBindingHandleSecurity; Security
0x180013718  lea     rax, aLsarpcEndpoint; "LSARPC_ENDPOINT"
0x18001371f  mov     [rbp+Template.Version], 1
0x180013726  movups  xmmword ptr [rbp+Template.NetworkAddress], xmm0
0x18001372a  xor     r8d, r8d; Options
0x18001372d  mov     [rbp+Template.StringEndpoint], rax
0x180013731  lea     rcx, [rbp+Template]; Template
0x180013735  mov     [rbp+Template.ProtocolSequence], 3
0x18001373c  movups  xmmword ptr [rbp+Template.u1], xmm0
0x180013740  call    cs:__imp_RpcBindingCreateW
0x180013746  mov     ebx, eax
0x180013748  test    eax, eax
0x18001374a  jnz     short loc_18001379D
0x18001374c  mov     rdx, [rbp+Binding]; Binding
0x180013750  lea     r8, qword_180052460; IfSpec
0x180013757  xor     ecx, ecx; pAsync
0x180013759  call    RpcBindingBind_0
0x18001375e  mov     ebx, eax
0x180013760  test    eax, eax
0x180013762  jnz     short loc_18001379D
0x180013764  mov     rax, [rbp+Binding]
0x180013768  mov     ecx, ebx; Status
0x18001376a  mov     [rbp+var_48], rax
0x18001376e  call    cs:__imp_I_RpcMapWin32Status
0x180013774  mov     rax, [rbp+var_48]
0x180013778  mov     rcx, [rbp+var_8]
0x18001377c  xor     rcx, rsp; StackCookie
0x18001377f  call    __security_check_cookie
0x180013784  mov     rbx, [rsp+70h+arg_8]
0x18001378c  add     rsp, 70h
0x180013790  pop     rbp
0x180013791  retn
0x180013792  lea     r9, [rbp+var_48]
0x180013796  call    RpcpBindRpc
0x18001379b  jmp     short loc_180013774
0x18001379d  lea     rcx, [rbp+Binding]; Binding
0x1800137a1  call    cs:__imp_RpcBindingFree
0x1800137a7  xor     eax, eax
0x1800137a9  mov     [rbp+Binding], rax
0x1800137ad  jmp     short loc_180013768
```
