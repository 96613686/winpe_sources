# CRCMLegacyRpc::staticRCMLegacyRpcSecurityCallback(void *,void *)

- ea: `0x180063870`
- end: `0x180063a94`
- name: `?staticRCMLegacyRpcSecurityCallback@CRCMLegacyRpc@@CAJPEAX0@Z`
- size: `548`
- prototype: `RPC_IF_CALLBACK_FN`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009940`
- `0x18002f2f0`
- `0x180033f60`
- `0x180034e64`
- `0x180063870`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180063956`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006396f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180063956`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006396f`
- `RPCRT4!RpcRevertToSelf` at `0x180063a1b`
- `RPCRT4!RpcRevertToSelf` at `0x180063a2c`
- `RPCRT4!RpcRevertToSelf` at `0x180063a1b`
- `RPCRT4!RpcRevertToSelf` at `0x180063a2c`
- `RPCRT4!RpcImpersonateClient` at `0x1800639e7`
- `RPCRT4!RpcImpersonateClient` at `0x1800639e7`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800639c9`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800639c9`
- `RPCRT4!RpcBindingToStringBindingW` at `0x1800638b8`
- `RPCRT4!RpcBindingToStringBindingW` at `0x1800638b8`
- `RPCRT4!RpcStringFreeW` at `0x18006392d`
- `RPCRT4!RpcStringFreeW` at `0x18006393f`
- `RPCRT4!RpcStringFreeW` at `0x180063981`
- `RPCRT4!RpcStringFreeW` at `0x18006392d`
- `RPCRT4!RpcStringFreeW` at `0x18006393f`
- `RPCRT4!RpcStringFreeW` at `0x180063981`
- `RPCRT4!RpcStringBindingParseW` at `0x180063905`
- `RPCRT4!RpcStringBindingParseW` at `0x180063905`

## string_xrefs

- `0x1800639f7`: `Cannot impersonate client: %d`

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
0x180063870  push    rbp
0x180063872  push    rbx
0x180063873  push    rsi
0x180063874  push    rdi
0x180063875  lea     rbp, [rsp-3Fh]
0x18006387a  sub     rsp, 0D8h
0x180063881  mov     rax, cs:__security_cookie
0x180063888  xor     rax, rsp
0x18006388b  mov     [rbp+57h+var_30], rax
0x18006388f  mov     rsi, rdx
0x180063892  mov     [rbp+57h+StringBinding], 0
0x18006389a  xor     edx, edx; Val
0x18006389c  mov     [rbp+57h+Protseq], 0
0x1800638a4  lea     rcx, [rbp+57h+RpcCallAttributes]; void *
0x1800638a8  lea     r8d, [rdx+78h]; Size
0x1800638ac  call    memset_0
0x1800638b1  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x1800638b5  mov     rcx, rsi; Binding
0x1800638b8  call    cs:__imp_RpcBindingToStringBindingW
0x1800638bf  nop     dword ptr [rax+rax+00h]
0x1800638c4  test    eax, eax
0x1800638c6  jz      short loc_1800638E6
0x1800638c8  lea     rdx, aRpcbindingtost; "RpcBindingToStringBinding failed - %d"
0x1800638cf  mov     r8d, eax
0x1800638d2  mov     ecx, 8; int
0x1800638d7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800638dc  mov     eax, 5
0x1800638e1  jmp     loc_180063A7B
0x1800638e6  mov     rcx, [rbp+57h+StringBinding]; StringBinding
0x1800638ea  lea     r8, [rbp+57h+Protseq]; Protseq
0x1800638ee  mov     [rsp+0F0h+NetworkOptions], 0; NetworkOptions
0x1800638f7  xor     r9d, r9d; NetworkAddr
0x1800638fa  xor     edx, edx; ObjUuid
0x1800638fc  mov     [rsp+0F0h+Endpoint], 0; Endpoint
0x180063905  call    cs:__imp_RpcStringBindingParseW
0x18006390c  nop     dword ptr [rax+rax+00h]
0x180063911  test    eax, eax
0x180063913  jz      short loc_18006393B
0x180063915  mov     r8d, eax
0x180063918  lea     rdx, aRpcstringbindi; "RpcStringBindingParse failed - %d"
0x18006391f  mov     ecx, 8; int
0x180063924  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180063929  lea     rcx, [rbp+57h+StringBinding]; String
0x18006392d  call    cs:__imp_RpcStringFreeW
0x180063934  nop     dword ptr [rax+rax+00h]
0x180063939  jmp     short loc_1800638DC
0x18006393b  lea     rcx, [rbp+57h+StringBinding]; String
0x18006393f  call    cs:__imp_RpcStringFreeW
0x180063946  nop     dword ptr [rax+rax+00h]
0x18006394b  mov     rcx, [rbp+57h+Protseq]
0x18006394f  lea     rdx, aNcalrpc; "ncalrpc"
0x180063956  call    cs:__imp__o__wcsicmp
0x18006395d  nop     dword ptr [rax+rax+00h]
0x180063962  mov     rcx, [rbp+57h+Protseq]
0x180063966  lea     rdx, Protseq; "ncacn_np"
0x18006396d  mov     ebx, eax
0x18006396f  call    cs:__imp__o__wcsicmp
0x180063976  nop     dword ptr [rax+rax+00h]
0x18006397b  lea     rcx, [rbp+57h+Protseq]; String
0x18006397f  mov     edi, eax
0x180063981  call    cs:__imp_RpcStringFreeW
0x180063988  nop     dword ptr [rax+rax+00h]
0x18006398d  test    ebx, ebx
0x18006398f  jz      short loc_1800639AB
0x180063991  test    edi, edi
0x180063993  jz      short loc_1800639AB
0x180063995  lea     rdx, aClientIsNeithe; "Client is neither using named pipe nor "...
0x18006399c  mov     ecx, 8; int
0x1800639a1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800639a6  jmp     loc_1800638DC
0x1800639ab  xor     edx, edx; Val
0x1800639ad  lea     rcx, [rbp+57h+var_A8]; void *
0x1800639b1  lea     r8d, [rdx+70h]; Size
0x1800639b5  call    memset_0
0x1800639ba  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x1800639be  mov     [rbp+57h+RpcCallAttributes], 3
0x1800639c6  mov     rcx, rsi; ClientBinding
0x1800639c9  call    cs:__imp_RpcServerInqCallAttributesW
0x1800639d0  nop     dword ptr [rax+rax+00h]
0x1800639d5  cmp     eax, 6D2h
0x1800639da  jnz     short loc_180063A45
0x1800639dc  cmp     cs:?fEncryptRPCTraffic@CRCMLegacyRpc@@0HA, 0; int CRCMLegacyRpc::fEncryptRPCTraffic
0x1800639e3  jnz     short loc_180063A49
0x1800639e5  xor     ecx, ecx; BindingHandle
0x1800639e7  call    cs:__imp_RpcImpersonateClient
0x1800639ee  nop     dword ptr [rax+rax+00h]
0x1800639f3  test    eax, eax
0x1800639f5  jz      short loc_180063A03
0x1800639f7  lea     rdx, aCannotImperson; "Cannot impersonate client: %d"
0x1800639fe  jmp     loc_1800638CF
0x180063a03  call    ?IsCallerAnonymous@CUtils@@SAJXZ; CUtils::IsCallerAnonymous(void)
0x180063a08  test    eax, eax
0x180063a0a  jnz     short loc_180063A2C
0x180063a0c  lea     rdx, aCallerIsAnonym; "Caller is ANONYMOUS!"
0x180063a13  lea     ecx, [rax+8]; int
0x180063a16  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180063a1b  call    cs:__imp_RpcRevertToSelf
0x180063a22  nop     dword ptr [rax+rax+00h]
0x180063a27  jmp     loc_1800638DC
0x180063a2c  call    cs:__imp_RpcRevertToSelf
0x180063a33  nop     dword ptr [rax+rax+00h]
0x180063a38  xor     ecx, ecx
0x180063a3a  sub     ecx, eax
0x180063a3c  neg     ecx
0x180063a3e  sbb     eax, eax
0x180063a40  and     eax, 5
0x180063a43  jmp     short loc_180063A7B
0x180063a45  test    eax, eax
0x180063a47  jz      short loc_180063A55
0x180063a49  lea     rdx, aRpcserverinqca; "RpcServerInqCallAttributes failed - %d"
0x180063a50  jmp     loc_1800638CF
0x180063a55  cmp     [rbp+57h+var_88], 6
0x180063a59  jz      short loc_180063A67
0x180063a5b  lea     rdx, aAuthlevelRpcCA; "AuthLevel != RPC_C_AUTHN_LEVEL_PKT_PRIV"...
0x180063a62  jmp     loc_18006399C
0x180063a67  cmp     [rbp+57h+var_80], 0
0x180063a6b  jz      short loc_180063A79
0x180063a6d  lea     rdx, aNullSession; "NULL SESSION!"
0x180063a74  jmp     loc_18006399C
0x180063a79  xor     eax, eax
0x180063a7b  mov     rcx, [rbp+57h+var_30]
0x180063a7f  xor     rcx, rsp; StackCookie
0x180063a82  call    __security_check_cookie
0x180063a87  add     rsp, 0D8h
0x180063a8e  pop     rdi
0x180063a8f  pop     rsi
0x180063a90  pop     rbx
0x180063a91  pop     rbp
0x180063a92  retn
```
