# OpenLocalUnifiedRpc(void *)

- ea: `0x180014958`
- end: `0x180014ad6`
- name: `?OpenLocalUnifiedRpc@@YAPEAXPEAX@Z`
- size: `382`
- prototype: `void *__fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020c90`

## callees

- `0x180005b40`
- `0x180014958`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014ab5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014ab5`
- `RPCRT4!RpcBindingFree` at `0x180014a9f`
- `RPCRT4!RpcBindingFree` at `0x180014a9f`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800149b7`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800149b7`
- `RPCRT4!RpcStringFreeW` at `0x180014a0d`
- `RPCRT4!RpcStringFreeW` at `0x180014a0d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800149df`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800149df`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180014a71`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180014a71`

## string_xrefs

- `0x1800149a4`: `Security=Impersonation Dynamic False`
- `0x1800149ce`: `Error %d in RpcStringBindingCompose`
- `0x180014a1d`: `OpenLocalUnifiedRpc: CRpcUtils::Bind FAILED with error 0x%x`
- `0x180014a83`: `OpenLocalUnifiedRpc: RpcBindingSetAuthInfoExW failed %d`

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
0x180014958  mov     r11, rsp
0x18001495b  mov     [r11+18h], rbx
0x18001495f  mov     [r11+8], rcx
0x180014963  push    rbp
0x180014964  push    rsi
0x180014965  push    rdi
0x180014966  mov     rbp, rsp
0x180014969  sub     rsp, 70h
0x18001496d  mov     rsi, cs:?pNetsrvSid@CPublicBinding@@1PEAXEA; void * CPublicBinding::pNetsrvSid
0x180014974  lea     r9, aUnifiedapi; "UnifiedApi"
0x18001497b  xor     eax, eax
0x18001497d  mov     [rbp+Binding], 0
0x180014985  mov     [rbp+var_10], rax
0x180014989  lea     rdx, ProtSeq; "ncalrpc"
0x180014990  mov     [rbp+StringBinding], rax
0x180014994  xorps   xmm0, xmm0
0x180014997  lea     rax, [rbp+StringBinding]
0x18001499b  xor     r8d, r8d; NetworkAddr
0x18001499e  mov     [r11-60h], rax
0x1800149a2  xor     ecx, ecx; ObjUuid
0x1800149a4  lea     rax, Options; "Security=Impersonation Dynamic False"
0x1800149ab  mov     [r11-68h], rax
0x1800149af  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x1800149b3  movups  [rbp+var_20], xmm0
0x1800149b7  call    cs:__imp_RpcStringBindingComposeW
0x1800149be  nop     dword ptr [rax+rax+00h]
0x1800149c3  mov     ebx, eax
0x1800149c5  mov     edi, 8
0x1800149ca  test    eax, eax
0x1800149cc  jz      short loc_1800149D7
0x1800149ce  lea     rdx, aErrorDInRpcstr; "Error %d in RpcStringBindingCompose"
0x1800149d5  jmp     short loc_1800149F8
0x1800149d7  mov     rcx, [rbp+StringBinding]; StringBinding
0x1800149db  lea     rdx, [rbp+Binding]; Binding
0x1800149df  call    cs:__imp_RpcBindingFromStringBindingW
0x1800149e6  nop     dword ptr [rax+rax+00h]
0x1800149eb  mov     ebx, eax
0x1800149ed  test    eax, eax
0x1800149ef  jz      short loc_180014A02
0x1800149f1  lea     rdx, aErrorDInRpcbin_0; "Error %d in RpcBindingFromStringBinding"
0x1800149f8  mov     r8d, eax
0x1800149fb  mov     ecx, edi; int
0x1800149fd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014a02  cmp     [rbp+StringBinding], 0
0x180014a07  jz      short loc_180014A19
0x180014a09  lea     rcx, [rbp+StringBinding]; String
0x180014a0d  call    cs:__imp_RpcStringFreeW
0x180014a14  nop     dword ptr [rax+rax+00h]
0x180014a19  test    ebx, ebx
0x180014a1b  jz      short loc_180014A26
0x180014a1d  lea     rdx, aOpenlocalunifi; "OpenLocalUnifiedRpc: CRpcUtils::Bind FA"...
0x180014a24  jmp     short loc_180014A8A
0x180014a26  mov     rcx, [rbp+Binding]; Binding
0x180014a2a  mov     eax, 1
0x180014a2f  mov     [rbp+var_30.Capabilities], eax
0x180014a32  xor     edx, edx; ServerPrincName
0x180014a34  mov     [rbp+var_30.IdentityTracking], eax
0x180014a37  mov     eax, 3
0x180014a3c  mov     qword ptr [rbp+var_30.ImpersonationType], rax
0x180014a40  mov     [rbp+var_30.Version], eax
0x180014a43  lea     rax, [rbp+var_30]
0x180014a47  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x180014a4c  lea     r9d, [rdx+0Ah]; AuthnSvc
0x180014a50  mov     [rsp+70h+AuthzSvc], 0; AuthzSvc
0x180014a58  lea     r8d, [rdx+6]; AuthnLevel
0x180014a5c  mov     [rsp+70h+AuthIdentity], 0; AuthIdentity
0x180014a65  mov     qword ptr [rbp+var_20+8], 0
0x180014a6d  mov     [rbp+var_10], rsi
0x180014a71  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180014a78  nop     dword ptr [rax+rax+00h]
0x180014a7d  mov     ebx, eax
0x180014a7f  test    eax, eax
0x180014a81  jz      short loc_180014AC1
0x180014a83  lea     rdx, aOpenlocalunifi_0; "OpenLocalUnifiedRpc: RpcBindingSetAuthI"...
0x180014a8a  mov     r8d, ebx
0x180014a8d  mov     ecx, edi; int
0x180014a8f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014a94  cmp     [rbp+Binding], 0
0x180014a99  jz      short loc_180014AB3
0x180014a9b  lea     rcx, [rbp+Binding]; Binding
0x180014a9f  call    cs:__imp_RpcBindingFree
0x180014aa6  nop     dword ptr [rax+rax+00h]
0x180014aab  mov     [rbp+Binding], 0
0x180014ab3  mov     ecx, ebx; dwErrCode
0x180014ab5  call    cs:__imp_SetLastError
0x180014abc  nop     dword ptr [rax+rax+00h]
0x180014ac1  mov     rax, [rbp+Binding]
0x180014ac5  mov     rbx, [rsp+70h+arg_10]
0x180014acd  add     rsp, 70h
0x180014ad1  pop     rdi
0x180014ad2  pop     rsi
0x180014ad3  pop     rbp
0x180014ad4  retn
```
