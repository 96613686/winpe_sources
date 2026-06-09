# OpenLocalUnifiedRpc(void *)

- ea: `0x1800139dc`
- end: `0x180013b35`
- name: `?OpenLocalUnifiedRpc@@YAPEAXPEAX@Z`
- size: `345`
- prototype: `void *__fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f5f8`

## callees

- `0x180007890`
- `0x1800139dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013b1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013b1b`
- `RPCRT4!RpcBindingFree` at `0x180013b0b`
- `RPCRT4!RpcBindingFree` at `0x180013b0b`
- `RPCRT4!RpcStringBindingComposeW` at `0x180013a3b`
- `RPCRT4!RpcStringBindingComposeW` at `0x180013a3b`
- `RPCRT4!RpcStringFreeW` at `0x180013a85`
- `RPCRT4!RpcStringFreeW` at `0x180013a85`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180013a5d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180013a5d`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180013ae3`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180013ae3`

## string_xrefs

- `0x180013a28`: `Security=Impersonation Dynamic False`
- `0x180013a4c`: `Error %d in RpcStringBindingCompose`
- `0x180013a8f`: `OpenLocalUnifiedRpc: CRpcUtils::Bind FAILED with error 0x%x`
- `0x180013aef`: `OpenLocalUnifiedRpc: RpcBindingSetAuthInfoExW failed %d`

## pseudocode

```c
RPC_BINDING_HANDLE __fastcall OpenLocalUnifiedRpc(void *a1)
{
  HLOCAL v1; // rsi
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int v4; // eax
  RPC_SECURITY_QOS SecurityQOS[2]; // [rsp+40h] [rbp-30h] BYREF
  HLOCAL v7; // [rsp+60h] [rbp-10h]
  RPC_BINDING_HANDLE Binding; // [rsp+90h] [rbp+20h] BYREF
  RPC_WSTR StringBinding; // [rsp+98h] [rbp+28h] BYREF

  v1 = CPublicBinding::pNetsrvSid;
  Binding = 0;
  v7 = 0;
  StringBinding = 0;
  memset(SecurityQOS, 0, sizeof(SecurityQOS));
  v2 = RpcStringBindingComposeW(
         0,
         (RPC_WSTR)L"ncalrpc",
         0,
         (RPC_WSTR)L"UnifiedApi",
         (RPC_WSTR)L"Security=Impersonation Dynamic False",
         &StringBinding);
  v3 = v2;
  if ( v2 )
  {
    _DbgPrintMessage(8, "Error %d in RpcStringBindingCompose", v2);
  }
  else
  {
    v4 = RpcBindingFromStringBindingW(StringBinding, &Binding);
    v3 = v4;
    if ( v4 )
      _DbgPrintMessage(8, "Error %d in RpcBindingFromStringBinding", v4);
  }
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  if ( v3 )
  {
    _DbgPrintMessage(8, "OpenLocalUnifiedRpc: CRpcUtils::Bind FAILED with error 0x%x", v3);
  }
  else
  {
    SecurityQOS[0].IdentityTracking = 1;
    *(_QWORD *)&SecurityQOS[0].ImpersonationType = 3;
    *(_QWORD *)&SecurityQOS[0].Version = 0x100000003LL;
    *(_QWORD *)&SecurityQOS[1].IdentityTracking = 0;
    v7 = v1;
    v3 = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 0, SecurityQOS);
    if ( !v3 )
      return Binding;
    _DbgPrintMessage(8, "OpenLocalUnifiedRpc: RpcBindingSetAuthInfoExW failed %d", v3);
  }
  if ( Binding )
  {
    RpcBindingFree(&Binding);
    Binding = 0;
  }
  SetLastError(v3);
  return Binding;
}

```

## disassembly

```asm
0x1800139dc  mov     r11, rsp
0x1800139df  mov     [r11+18h], rbx
0x1800139e3  mov     [r11+8], rcx
0x1800139e7  push    rbp
0x1800139e8  push    rsi
0x1800139e9  push    rdi
0x1800139ea  mov     rbp, rsp
0x1800139ed  sub     rsp, 70h
0x1800139f1  mov     rsi, cs:?pNetsrvSid@CPublicBinding@@1PEAXEA; void * CPublicBinding::pNetsrvSid
0x1800139f8  lea     r9, aUnifiedapi; "UnifiedApi"
0x1800139ff  xor     eax, eax
0x180013a01  mov     [rbp+Binding], 0
0x180013a09  mov     [rbp+var_10], rax
0x180013a0d  lea     rdx, ProtSeq; "ncalrpc"
0x180013a14  mov     [rbp+StringBinding], rax
0x180013a18  xorps   xmm0, xmm0
0x180013a1b  lea     rax, [rbp+StringBinding]
0x180013a1f  xor     r8d, r8d; NetworkAddr
0x180013a22  mov     [r11-60h], rax
0x180013a26  xor     ecx, ecx; ObjUuid
0x180013a28  lea     rax, Options; "Security=Impersonation Dynamic False"
0x180013a2f  mov     [r11-68h], rax
0x180013a33  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x180013a37  movups  [rbp+var_20], xmm0
0x180013a3b  call    cs:__imp_RpcStringBindingComposeW
0x180013a41  mov     ebx, eax
0x180013a43  mov     edi, 8
0x180013a48  test    eax, eax
0x180013a4a  jz      short loc_180013A55
0x180013a4c  lea     rdx, aErrorDInRpcstr; "Error %d in RpcStringBindingCompose"
0x180013a53  jmp     short loc_180013A70
0x180013a55  mov     rcx, [rbp+StringBinding]; StringBinding
0x180013a59  lea     rdx, [rbp+Binding]; Binding
0x180013a5d  call    cs:__imp_RpcBindingFromStringBindingW
0x180013a63  mov     ebx, eax
0x180013a65  test    eax, eax
0x180013a67  jz      short loc_180013A7A
0x180013a69  lea     rdx, aErrorDInRpcbin_0; "Error %d in RpcBindingFromStringBinding"
0x180013a70  mov     r8d, eax
0x180013a73  mov     ecx, edi; int
0x180013a75  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013a7a  cmp     [rbp+StringBinding], 0
0x180013a7f  jz      short loc_180013A8B
0x180013a81  lea     rcx, [rbp+StringBinding]; String
0x180013a85  call    cs:__imp_RpcStringFreeW
0x180013a8b  test    ebx, ebx
0x180013a8d  jz      short loc_180013A98
0x180013a8f  lea     rdx, aOpenlocalunifi; "OpenLocalUnifiedRpc: CRpcUtils::Bind FA"...
0x180013a96  jmp     short loc_180013AF6
0x180013a98  mov     rcx, [rbp+Binding]; Binding
0x180013a9c  mov     eax, 1
0x180013aa1  mov     [rbp+var_30.Capabilities], eax
0x180013aa4  xor     edx, edx; ServerPrincName
0x180013aa6  mov     [rbp+var_30.IdentityTracking], eax
0x180013aa9  mov     eax, 3
0x180013aae  mov     qword ptr [rbp+var_30.ImpersonationType], rax
0x180013ab2  mov     [rbp+var_30.Version], eax
0x180013ab5  lea     rax, [rbp+var_30]
0x180013ab9  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x180013abe  lea     r9d, [rdx+0Ah]; AuthnSvc
0x180013ac2  mov     [rsp+70h+AuthzSvc], 0; AuthzSvc
0x180013aca  lea     r8d, [rdx+6]; AuthnLevel
0x180013ace  mov     [rsp+70h+AuthIdentity], 0; AuthIdentity
0x180013ad7  mov     qword ptr [rbp+var_20+8], 0
0x180013adf  mov     [rbp+var_10], rsi
0x180013ae3  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180013ae9  mov     ebx, eax
0x180013aeb  test    eax, eax
0x180013aed  jz      short loc_180013B21
0x180013aef  lea     rdx, aOpenlocalunifi_0; "OpenLocalUnifiedRpc: RpcBindingSetAuthI"...
0x180013af6  mov     r8d, ebx
0x180013af9  mov     ecx, edi; int
0x180013afb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013b00  cmp     [rbp+Binding], 0
0x180013b05  jz      short loc_180013B19
0x180013b07  lea     rcx, [rbp+Binding]; Binding
0x180013b0b  call    cs:__imp_RpcBindingFree
0x180013b11  mov     [rbp+Binding], 0
0x180013b19  mov     ecx, ebx; dwErrCode
0x180013b1b  call    cs:__imp_SetLastError
0x180013b21  mov     rax, [rbp+Binding]
0x180013b25  mov     rbx, [rsp+70h+arg_10]
0x180013b2d  add     rsp, 70h
0x180013b31  pop     rdi
0x180013b32  pop     rsi
0x180013b33  pop     rbp
0x180013b34  retn
```
