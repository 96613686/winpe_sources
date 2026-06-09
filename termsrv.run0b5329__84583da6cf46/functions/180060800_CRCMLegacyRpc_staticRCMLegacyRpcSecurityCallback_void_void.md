# CRCMLegacyRpc::staticRCMLegacyRpcSecurityCallback(void *,void *)

- ea: `0x180060800`
- end: `0x1800609e1`
- name: `?staticRCMLegacyRpcSecurityCallback@CRCMLegacyRpc@@CAJPEAX0@Z`
- size: `481`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a210`
- `0x18002d8d8`
- `0x1800321f0`
- `0x1800330c4`
- `0x180060800`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800608ce`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800608e1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800608ce`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800608e1`
- `RPCRT4!RpcRevertToSelf` at `0x180060975`
- `RPCRT4!RpcRevertToSelf` at `0x180060980`
- `RPCRT4!RpcRevertToSelf` at `0x180060975`
- `RPCRT4!RpcRevertToSelf` at `0x180060980`
- `RPCRT4!RpcImpersonateClient` at `0x180060947`
- `RPCRT4!RpcImpersonateClient` at `0x180060947`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18006092f`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18006092f`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180060848`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180060848`
- `RPCRT4!RpcStringFreeW` at `0x1800608b1`
- `RPCRT4!RpcStringFreeW` at `0x1800608bd`
- `RPCRT4!RpcStringFreeW` at `0x1800608ed`
- `RPCRT4!RpcStringFreeW` at `0x1800608b1`
- `RPCRT4!RpcStringFreeW` at `0x1800608bd`
- `RPCRT4!RpcStringFreeW` at `0x1800608ed`
- `RPCRT4!RpcStringBindingParseW` at `0x18006088f`
- `RPCRT4!RpcStringBindingParseW` at `0x18006088f`

## string_xrefs

- `0x180060951`: `Cannot impersonate client: %d`

## pseudocode

```c
__int64 __fastcall CRCMLegacyRpc::staticRCMLegacyRpcSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  unsigned int v3; // eax
  RPC_STATUS v5; // eax
  int v6; // ebx
  int v7; // edi
  unsigned int v8; // eax
  unsigned int v9; // eax
  RPC_WSTR StringBinding; // [rsp+30h] [rbp-69h] BYREF
  RPC_WSTR Protseq; // [rsp+38h] [rbp-61h] BYREF
  __int64 RpcCallAttributes; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v13[32]; // [rsp+48h] [rbp-51h] BYREF
  int v14; // [rsp+68h] [rbp-31h]
  int v15; // [rsp+70h] [rbp-29h]

  StringBinding = 0;
  Protseq = 0;
  memset_0(&RpcCallAttributes, 0, 0x78u);
  v3 = RpcBindingToStringBindingW(Context, &StringBinding);
  if ( v3 )
  {
    _DbgPrintMessage(8, "RpcBindingToStringBinding failed - %d", v3);
    return 5;
  }
  v5 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
  if ( v5 )
  {
    _DbgPrintMessage(8, "RpcStringBindingParse failed - %d", v5);
    RpcStringFreeW(&StringBinding);
    return 5;
  }
  RpcStringFreeW(&StringBinding);
  v6 = _o__wcsicmp(Protseq, L"ncalrpc");
  v7 = _o__wcsicmp(Protseq, L"ncacn_np");
  RpcStringFreeW(&Protseq);
  if ( v6 && v7 )
  {
    _DbgPrintMessage(8, "Client is neither using named pipe nor LPC!");
    return 5;
  }
  memset_0(v13, 0, 0x70u);
  RpcCallAttributes = 3;
  v8 = RpcServerInqCallAttributesW(Context, &RpcCallAttributes);
  if ( v8 != 1746 )
  {
    if ( !v8 )
    {
      if ( v14 != 6 )
      {
        _DbgPrintMessage(8, "AuthLevel != RPC_C_AUTHN_LEVEL_PKT_PRIVACY");
        return 5;
      }
      if ( v15 )
      {
        _DbgPrintMessage(8, "NULL SESSION!");
        return 5;
      }
      return 0;
    }
LABEL_18:
    _DbgPrintMessage(8, "RpcServerInqCallAttributes failed - %d", v8);
    return 5;
  }
  if ( CRCMLegacyRpc::fEncryptRPCTraffic )
    goto LABEL_18;
  v9 = RpcImpersonateClient(0);
  if ( v9 )
  {
    _DbgPrintMessage(8, "Cannot impersonate client: %d", v9);
    return 5;
  }
  if ( !(unsigned int)CUtils::IsCallerAnonymous() )
  {
    _DbgPrintMessage(8, "Caller is ANONYMOUS!");
    RpcRevertToSelf();
    return 5;
  }
  return RpcRevertToSelf() != 0 ? 5 : 0;
}

```

## disassembly

```asm
0x180060800  push    rbp
0x180060802  push    rbx
0x180060803  push    rsi
0x180060804  push    rdi
0x180060805  lea     rbp, [rsp-3Fh]
0x18006080a  sub     rsp, 0D8h
0x180060811  mov     rax, cs:__security_cookie
0x180060818  xor     rax, rsp
0x18006081b  mov     [rbp+57h+var_30], rax
0x18006081f  mov     rsi, rdx
0x180060822  mov     [rbp+57h+StringBinding], 0
0x18006082a  xor     edx, edx; Val
0x18006082c  mov     [rbp+57h+Protseq], 0
0x180060834  lea     rcx, [rbp+57h+RpcCallAttributes]; void *
0x180060838  lea     r8d, [rdx+78h]; Size
0x18006083c  call    memset_0
0x180060841  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x180060845  mov     rcx, rsi; Binding
0x180060848  call    cs:__imp_RpcBindingToStringBindingW
0x18006084e  test    eax, eax
0x180060850  jz      short loc_180060870
0x180060852  lea     rdx, aRpcbindingtost; "RpcBindingToStringBinding failed - %d"
0x180060859  mov     r8d, eax
0x18006085c  mov     ecx, 8; int
0x180060861  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180060866  mov     eax, 5
0x18006086b  jmp     loc_1800609C9
0x180060870  mov     rcx, [rbp+57h+StringBinding]; StringBinding
0x180060874  lea     r8, [rbp+57h+Protseq]; Protseq
0x180060878  mov     [rsp+0F0h+NetworkOptions], 0; NetworkOptions
0x180060881  xor     r9d, r9d; NetworkAddr
0x180060884  xor     edx, edx; ObjUuid
0x180060886  mov     [rsp+0F0h+Endpoint], 0; Endpoint
0x18006088f  call    cs:__imp_RpcStringBindingParseW
0x180060895  test    eax, eax
0x180060897  jz      short loc_1800608B9
0x180060899  mov     r8d, eax
0x18006089c  lea     rdx, aRpcstringbindi; "RpcStringBindingParse failed - %d"
0x1800608a3  mov     ecx, 8; int
0x1800608a8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800608ad  lea     rcx, [rbp+57h+StringBinding]; String
0x1800608b1  call    cs:__imp_RpcStringFreeW
0x1800608b7  jmp     short loc_180060866
0x1800608b9  lea     rcx, [rbp+57h+StringBinding]; String
0x1800608bd  call    cs:__imp_RpcStringFreeW
0x1800608c3  mov     rcx, [rbp+57h+Protseq]
0x1800608c7  lea     rdx, aNcalrpc; "ncalrpc"
0x1800608ce  call    cs:__imp__o__wcsicmp
0x1800608d4  mov     rcx, [rbp+57h+Protseq]
0x1800608d8  lea     rdx, Protseq; "ncacn_np"
0x1800608df  mov     ebx, eax
0x1800608e1  call    cs:__imp__o__wcsicmp
0x1800608e7  lea     rcx, [rbp+57h+Protseq]; String
0x1800608eb  mov     edi, eax
0x1800608ed  call    cs:__imp_RpcStringFreeW
0x1800608f3  test    ebx, ebx
0x1800608f5  jz      short loc_180060911
0x1800608f7  test    edi, edi
0x1800608f9  jz      short loc_180060911
0x1800608fb  lea     rdx, aClientIsNeithe; "Client is neither using named pipe nor "...
0x180060902  mov     ecx, 8; int
0x180060907  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006090c  jmp     loc_180060866
0x180060911  xor     edx, edx; Val
0x180060913  lea     rcx, [rbp+57h+var_A8]; void *
0x180060917  lea     r8d, [rdx+70h]; Size
0x18006091b  call    memset_0
0x180060920  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x180060924  mov     [rbp+57h+RpcCallAttributes], 3
0x18006092c  mov     rcx, rsi; ClientBinding
0x18006092f  call    cs:__imp_RpcServerInqCallAttributesW
0x180060935  cmp     eax, 6D2h
0x18006093a  jnz     short loc_180060993
0x18006093c  cmp     cs:?fEncryptRPCTraffic@CRCMLegacyRpc@@0HA, 0; int CRCMLegacyRpc::fEncryptRPCTraffic
0x180060943  jnz     short loc_180060997
0x180060945  xor     ecx, ecx; BindingHandle
0x180060947  call    cs:__imp_RpcImpersonateClient
0x18006094d  test    eax, eax
0x18006094f  jz      short loc_18006095D
0x180060951  lea     rdx, aCannotImperson; "Cannot impersonate client: %d"
0x180060958  jmp     loc_180060859
0x18006095d  call    ?IsCallerAnonymous@CUtils@@SAJXZ; CUtils::IsCallerAnonymous(void)
0x180060962  test    eax, eax
0x180060964  jnz     short loc_180060980
0x180060966  lea     rdx, aCallerIsAnonym; "Caller is ANONYMOUS!"
0x18006096d  lea     ecx, [rax+8]; int
0x180060970  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180060975  call    cs:__imp_RpcRevertToSelf
0x18006097b  jmp     loc_180060866
0x180060980  call    cs:__imp_RpcRevertToSelf
0x180060986  xor     ecx, ecx
0x180060988  sub     ecx, eax
0x18006098a  neg     ecx
0x18006098c  sbb     eax, eax
0x18006098e  and     eax, 5
0x180060991  jmp     short loc_1800609C9
0x180060993  test    eax, eax
0x180060995  jz      short loc_1800609A3
0x180060997  lea     rdx, aRpcserverinqca; "RpcServerInqCallAttributes failed - %d"
0x18006099e  jmp     loc_180060859
0x1800609a3  cmp     [rbp+57h+var_88], 6
0x1800609a7  jz      short loc_1800609B5
0x1800609a9  lea     rdx, aAuthlevelRpcCA; "AuthLevel != RPC_C_AUTHN_LEVEL_PKT_PRIV"...
0x1800609b0  jmp     loc_180060902
0x1800609b5  cmp     [rbp+57h+var_80], 0
0x1800609b9  jz      short loc_1800609C7
0x1800609bb  lea     rdx, aNullSession; "NULL SESSION!"
0x1800609c2  jmp     loc_180060902
0x1800609c7  xor     eax, eax
0x1800609c9  mov     rcx, [rbp+57h+var_30]
0x1800609cd  xor     rcx, rsp; StackCookie
0x1800609d0  call    __security_check_cookie
0x1800609d5  add     rsp, 0D8h
0x1800609dc  pop     rdi
0x1800609dd  pop     rsi
0x1800609de  pop     rbx
0x1800609df  pop     rbp
0x1800609e0  retn
```
