# CUmRdpRpc::CreateBinding(void)

- ea: `0x180004d40`
- end: `0x180004e68`
- name: `?CreateBinding@CUmRdpRpc@@IEAAJXZ`
- size: `296`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006170`
- `0x18000a41c`

## callees

- `0x180004d40`
- `0x18000a01c`
- `0x180047ef0`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x180004db0`
- `RPCRT4!RpcStringBindingComposeW` at `0x180004db0`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180004dc4`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180004dc4`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180004e12`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180004e12`
- `RPCRT4!RpcStringFreeW` at `0x180004e26`
- `RPCRT4!RpcStringFreeW` at `0x180004e26`
- `RPCRT4!RpcBindingFree` at `0x180004e38`
- `RPCRT4!RpcBindingFree` at `0x180004e38`

## pseudocode

```c
__int64 __fastcall CUmRdpRpc::CreateBinding(RPC_BINDING_HANDLE *Binding)
{
  __int64 v1; // r9
  unsigned int v3; // ebx
  RPC_BINDING_HANDLE v4; // rcx
  RPC_WSTR String; // [rsp+40h] [rbp-248h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+48h] [rbp-240h] BYREF
  unsigned __int16 Endpoint[264]; // [rsp+60h] [rbp-228h] BYREF

  v1 = *((unsigned int *)Binding + 2);
  String = 0;
  SecurityQOS = 0;
  StringCchPrintfW(Endpoint, 0x104u, L"UMRdpEndpoint_%d", v1);
  v3 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, Endpoint, 0, &String);
  if ( !v3 )
  {
    v3 = RpcBindingFromStringBindingW(String, Binding);
    if ( !v3 )
    {
      v4 = *Binding;
      *(_QWORD *)&SecurityQOS.Version = 1;
      SecurityQOS.IdentityTracking = 1;
      SecurityQOS.ImpersonationType = 2;
      v3 = RpcBindingSetAuthInfoExW(v4, (RPC_WSTR)L"NT AUTHORITY\\SYSTEM", 6u, 0xAu, 0, 0, &SecurityQOS);
    }
  }
  if ( String )
    RpcStringFreeW(&String);
  if ( v3 && *Binding )
  {
    RpcBindingFree(Binding);
    *Binding = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180004d40  mov     [rsp+arg_8], rbx
0x180004d45  mov     [rsp+arg_10], rsi
0x180004d4a  push    rdi
0x180004d4b  sub     rsp, 280h
0x180004d52  mov     rax, cs:__security_cookie
0x180004d59  xor     rax, rsp
0x180004d5c  mov     [rsp+288h+var_18], rax
0x180004d64  mov     r9d, [rcx+8]
0x180004d68  lea     r8, aUmrdpendpointD; "UMRdpEndpoint_%d"
0x180004d6f  mov     rdi, rcx
0x180004d72  xorps   xmm0, xmm0
0x180004d75  xor     esi, esi
0x180004d77  lea     rcx, [rsp+288h+Endpoint]; unsigned __int16 *
0x180004d7c  mov     edx, 104h; unsigned __int64
0x180004d81  mov     [rsp+288h+String], rsi
0x180004d86  movups  xmmword ptr [rsp+288h+var_240.Version], xmm0
0x180004d8b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004d90  lea     rax, [rsp+288h+String]
0x180004d95  xor     r8d, r8d; NetworkAddr
0x180004d98  mov     [rsp+288h+StringBinding], rax; StringBinding
0x180004d9d  lea     r9, [rsp+288h+Endpoint]; Endpoint
0x180004da2  lea     rdx, aNcalrpc; "ncalrpc"
0x180004da9  mov     [rsp+288h+Options], rsi; Options
0x180004dae  xor     ecx, ecx; ObjUuid
0x180004db0  call    cs:__imp_RpcStringBindingComposeW
0x180004db6  mov     ebx, eax
0x180004db8  test    eax, eax
0x180004dba  jnz     short loc_180004E1A
0x180004dbc  mov     rcx, [rsp+288h+String]; StringBinding
0x180004dc1  mov     rdx, rdi; Binding
0x180004dc4  call    cs:__imp_RpcBindingFromStringBindingW
0x180004dca  mov     ebx, eax
0x180004dcc  test    eax, eax
0x180004dce  jnz     short loc_180004E1A
0x180004dd0  mov     rcx, [rdi]; Binding
0x180004dd3  lea     rax, [rsp+288h+var_240]
0x180004dd8  mov     [rsp+288h+SecurityQOS], rax; SecurityQOS
0x180004ddd  lea     rdx, ServerPrincName; "NT AUTHORITY\\SYSTEM"
0x180004de4  mov     dword ptr [rsp+288h+StringBinding], esi; AuthzSvc
0x180004de8  mov     r9d, 0Ah; AuthnSvc
0x180004dee  mov     r8d, 6; AuthnLevel
0x180004df4  mov     [rsp+288h+Options], rsi; AuthIdentity
0x180004df9  mov     qword ptr [rsp+288h+var_240.Version], 1
0x180004e02  mov     [rsp+288h+var_240.IdentityTracking], 1
0x180004e0a  mov     [rsp+288h+var_240.ImpersonationType], 2
0x180004e12  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180004e18  mov     ebx, eax
0x180004e1a  cmp     [rsp+288h+String], rsi
0x180004e1f  jz      short loc_180004E2C
0x180004e21  lea     rcx, [rsp+288h+String]; String
0x180004e26  call    cs:__imp_RpcStringFreeW
0x180004e2c  test    ebx, ebx
0x180004e2e  jz      short loc_180004E41
0x180004e30  cmp     [rdi], rsi
0x180004e33  jz      short loc_180004E41
0x180004e35  mov     rcx, rdi; Binding
0x180004e38  call    cs:__imp_RpcBindingFree
0x180004e3e  mov     [rdi], rsi
0x180004e41  mov     eax, ebx
0x180004e43  mov     rcx, [rsp+288h+var_18]
0x180004e4b  xor     rcx, rsp; StackCookie
0x180004e4e  call    __security_check_cookie
0x180004e53  lea     r11, [rsp+288h+var_8]
0x180004e5b  mov     rbx, [r11+18h]
0x180004e5f  mov     rsi, [r11+20h]
0x180004e63  mov     rsp, r11
0x180004e66  pop     rdi
0x180004e67  retn
```
