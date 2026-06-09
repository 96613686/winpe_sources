# BindToLRpcService(void * &,ushort const *)

- ea: `0x180005b64`
- end: `0x180005c20`
- name: `?BindToLRpcService@@YAJAEAPEAXPEBG@Z`
- size: `188`
- prototype: `RPC_STATUS __fastcall(RPC_BINDING_HANDLE *Binding, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005960`

## callees

- `0x180005b64`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingW` at `0x180005b92`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180005b92`
- `RPCRT4!RpcBindingFree` at `0x180005c0a`
- `RPCRT4!RpcBindingFree` at `0x180005c0a`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180005bfb`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180005bfb`

## pseudocode

```c
RPC_STATUS __fastcall BindToLRpcService(RPC_BINDING_HANDLE *Binding, const unsigned __int16 *a2)
{
  RPC_STATUS result; // eax
  RPC_BINDING_HANDLE v4; // rcx
  RPC_STATUS v5; // edi
  RPC_SECURITY_QOS SecurityQOS; // [rsp+40h] [rbp-38h] BYREF
  __int128 v7; // [rsp+50h] [rbp-28h]
  __int64 *v8; // [rsp+60h] [rbp-18h]

  *Binding = 0;
  v8 = 0;
  SecurityQOS = 0;
  v7 = 0;
  result = RpcBindingFromStringBindingW((RPC_WSTR)L"ncalrpc:[senssvc]", Binding);
  if ( !result )
  {
    v4 = *Binding;
    SecurityQOS.Version = 3;
    SecurityQOS.ImpersonationType = 3;
    SecurityQOS.IdentityTracking = 1;
    SecurityQOS.Capabilities = 1;
    v8 = qword_18000DE80;
    LODWORD(v7) = 0;
    *((_QWORD *)&v7 + 1) = 0;
    v5 = RpcBindingSetAuthInfoExW(v4, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
    if ( v5 )
      RpcBindingFree(Binding);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180005b64  mov     [rsp+arg_0], rbx
0x180005b69  push    rdi
0x180005b6a  sub     rsp, 70h
0x180005b6e  xor     eax, eax
0x180005b70  xorps   xmm0, xmm0
0x180005b73  mov     [rcx], rax
0x180005b76  mov     rbx, rcx
0x180005b79  mov     rdx, rcx; Binding
0x180005b7c  mov     [rsp+78h+var_18], rax
0x180005b81  lea     rcx, StringBinding; "ncalrpc:[senssvc]"
0x180005b88  movups  xmmword ptr [rsp+78h+var_38.Version], xmm0
0x180005b8d  movups  [rsp+78h+var_28], xmm0
0x180005b92  call    cs:__imp_RpcBindingFromStringBindingW
0x180005b98  test    eax, eax
0x180005b9a  jnz     short loc_180005C12
0x180005b9c  mov     rcx, [rbx]; Binding
0x180005b9f  mov     eax, 3
0x180005ba4  mov     [rsp+78h+var_38.Version], eax
0x180005ba8  xor     edx, edx; ServerPrincName
0x180005baa  mov     [rsp+78h+var_38.ImpersonationType], eax
0x180005bae  mov     eax, 1
0x180005bb3  mov     [rsp+78h+var_38.IdentityTracking], eax
0x180005bb7  mov     [rsp+78h+var_38.Capabilities], eax
0x180005bbb  lea     rax, qword_18000DE80
0x180005bc2  mov     [rsp+78h+var_18], rax
0x180005bc7  lea     r9d, [rdx+0Ah]; AuthnSvc
0x180005bcb  lea     rax, [rsp+78h+var_38]
0x180005bd0  mov     dword ptr [rsp+78h+var_28], 0
0x180005bd8  mov     [rsp+78h+SecurityQOS], rax; SecurityQOS
0x180005bdd  lea     r8d, [rdx+6]; AuthnLevel
0x180005be1  mov     [rsp+78h+AuthzSvc], 0; AuthzSvc
0x180005be9  mov     [rsp+78h+AuthIdentity], 0; AuthIdentity
0x180005bf2  mov     qword ptr [rsp+78h+var_28+8], 0
0x180005bfb  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180005c01  mov     edi, eax
0x180005c03  test    eax, eax
0x180005c05  jz      short loc_180005C10
0x180005c07  mov     rcx, rbx; Binding
0x180005c0a  call    cs:__imp_RpcBindingFree
0x180005c10  mov     eax, edi
0x180005c12  mov     rbx, [rsp+78h+arg_0]
0x180005c1a  add     rsp, 70h
0x180005c1e  pop     rdi
0x180005c1f  retn
```
