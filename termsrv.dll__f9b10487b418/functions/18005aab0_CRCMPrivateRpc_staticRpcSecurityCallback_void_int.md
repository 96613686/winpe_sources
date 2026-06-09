# CRCMPrivateRpc::staticRpcSecurityCallback(void *,int)

- ea: `0x18005aab0`
- end: `0x18005acc1`
- name: `?staticRpcSecurityCallback@CRCMPrivateRpc@@CAJPEAXH@Z`
- size: `529`
- prototype: `unsigned int __fastcall(RPC_BINDING_HANDLE ClientBinding, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005aa80`
- `0x18005aaa0`

## callees

- `0x18000a210`
- `0x1800321f0`
- `0x1800330c4`
- `0x18005aab0`
- `0x18009d908`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005ab80`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005ab80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ac41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ac41`
- `RPCRT4!RpcRevertToSelf` at `0x18005ac6e`
- `RPCRT4!RpcRevertToSelf` at `0x18005aca7`
- `RPCRT4!RpcRevertToSelf` at `0x18005ac6e`
- `RPCRT4!RpcRevertToSelf` at `0x18005aca7`
- `RPCRT4!RpcImpersonateClient` at `0x18005ac00`
- `RPCRT4!RpcImpersonateClient` at `0x18005ac00`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18005abca`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18005abca`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18005aafa`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18005aafa`
- `RPCRT4!RpcStringFreeW` at `0x18005ab63`
- `RPCRT4!RpcStringFreeW` at `0x18005ab6f`
- `RPCRT4!RpcStringFreeW` at `0x18005ab8c`
- `RPCRT4!RpcStringFreeW` at `0x18005ab63`
- `RPCRT4!RpcStringFreeW` at `0x18005ab6f`
- `RPCRT4!RpcStringFreeW` at `0x18005ab8c`
- `RPCRT4!RpcStringBindingParseW` at `0x18005ab41`
- `RPCRT4!RpcStringBindingParseW` at `0x18005ab41`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005ac37`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005ac37`

## string_xrefs

- `0x18005ac59`: `CheckTokenMembership failed: 0x%x`
- `0x18005ac0a`: `Cannot impersonate client: %d`

## pseudocode

```c
unsigned int __fastcall CRCMPrivateRpc::staticRpcSecurityCallback(RPC_BINDING_HANDLE ClientBinding, int a2)
{
  unsigned int v4; // eax
  unsigned int result; // eax
  RPC_STATUS v6; // eax
  int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // eax
  signed int LastError; // eax
  unsigned int v11; // ebx
  WINBOOL IsMember; // [rsp+30h] [rbp-79h] BYREF
  RPC_WSTR StringBinding; // [rsp+38h] [rbp-71h] BYREF
  RPC_WSTR Protseq[2]; // [rsp+40h] [rbp-69h] BYREF
  __int64 RpcCallAttributes; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v16[32]; // [rsp+58h] [rbp-51h] BYREF
  int v17; // [rsp+78h] [rbp-31h]
  int v18; // [rsp+80h] [rbp-29h]

  StringBinding = 0;
  Protseq[0] = 0;
  memset_0(&RpcCallAttributes, 0, 0x78u);
  v4 = RpcBindingToStringBindingW(ClientBinding, &StringBinding);
  if ( v4 )
  {
    _DbgPrintMessage(8, "RpcBindingToStringBinding failed - %d", v4);
    return 5;
  }
  v6 = RpcStringBindingParseW(StringBinding, 0, Protseq, 0, 0, 0);
  if ( v6 )
  {
    _DbgPrintMessage(8, "RpcStringBindingParse failed - %d", v6);
    RpcStringFreeW(&StringBinding);
    return 5;
  }
  RpcStringFreeW(&StringBinding);
  v7 = _o__wcsicmp(Protseq[0], L"ncalrpc");
  RpcStringFreeW(Protseq);
  if ( v7 )
  {
    _DbgPrintMessage(8, "Client is not using LPC!");
    return 5;
  }
  memset_0(v16, 0, 0x70u);
  RpcCallAttributes = 3;
  v8 = RpcServerInqCallAttributesW(ClientBinding, &RpcCallAttributes);
  if ( v8 )
  {
    _DbgPrintMessage(8, "RpcServerInqCallAttributes failed - %d", v8);
    return 5;
  }
  if ( v17 != 6 )
  {
    _DbgPrintMessage(8, "AuthLevel != RPC_C_AUTHN_LEVEL_PKT_PRIVACY");
    return 5;
  }
  if ( v18 )
  {
    _DbgPrintMessage(8, "NULL SESSION!");
    return 5;
  }
  v9 = RpcImpersonateClient(0);
  if ( v9 )
  {
    _DbgPrintMessage(8, "Cannot impersonate client: %d", v9);
    return 5;
  }
  if ( (unsigned int)CUtils::IsCallerSystem() )
  {
    if ( a2 )
    {
      IsMember = 0;
      if ( CheckTokenMembership(0, CUtils::pAdminSid, &IsMember) )
      {
        if ( IsMember )
          goto LABEL_22;
      }
      else
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        _DbgPrintMessage(8, "CheckTokenMembership failed: 0x%x", v11);
        if ( !v11 )
          goto LABEL_22;
      }
    }
    _DbgPrintMessage(8, "Callers have to be system");
    result = RpcRevertToSelf();
    if ( !result )
      return 5;
LABEL_26:
    _DbgPrintMessage(8, "RpcRevertToSelf failed: %d", result);
    return 5;
  }
LABEL_22:
  result = RpcRevertToSelf();
  if ( result )
    goto LABEL_26;
  return result;
}

```

## disassembly

```asm
0x18005aab0  push    rbp
0x18005aab2  push    rbx
0x18005aab3  push    rsi
0x18005aab4  push    rdi
0x18005aab5  lea     rbp, [rsp-3Fh]
0x18005aaba  sub     rsp, 0E8h
0x18005aac1  mov     rax, cs:__security_cookie
0x18005aac8  xor     rax, rsp
0x18005aacb  mov     [rbp+57h+var_30], rax
0x18005aacf  mov     edi, edx
0x18005aad1  mov     [rbp+57h+StringBinding], 0
0x18005aad9  xor     edx, edx; Val
0x18005aadb  mov     [rbp+57h+Protseq], 0
0x18005aae3  mov     rsi, rcx
0x18005aae6  lea     rcx, [rbp+57h+RpcCallAttributes]; void *
0x18005aaea  lea     r8d, [rdx+78h]; Size
0x18005aaee  call    memset_0
0x18005aaf3  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x18005aaf7  mov     rcx, rsi; Binding
0x18005aafa  call    cs:__imp_RpcBindingToStringBindingW
0x18005ab00  test    eax, eax
0x18005ab02  jz      short loc_18005AB22
0x18005ab04  lea     rdx, aRpcbindingtost; "RpcBindingToStringBinding failed - %d"
0x18005ab0b  mov     r8d, eax
0x18005ab0e  mov     ecx, 8; int
0x18005ab13  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005ab18  mov     eax, 5
0x18005ab1d  jmp     loc_18005AC78
0x18005ab22  mov     rcx, [rbp+57h+StringBinding]; StringBinding
0x18005ab26  lea     r8, [rbp+57h+Protseq]; Protseq
0x18005ab2a  mov     [rsp+100h+NetworkOptions], 0; NetworkOptions
0x18005ab33  xor     r9d, r9d; NetworkAddr
0x18005ab36  xor     edx, edx; ObjUuid
0x18005ab38  mov     [rsp+100h+Endpoint], 0; Endpoint
0x18005ab41  call    cs:__imp_RpcStringBindingParseW
0x18005ab47  test    eax, eax
0x18005ab49  jz      short loc_18005AB6B
0x18005ab4b  mov     r8d, eax
0x18005ab4e  lea     rdx, aRpcstringbindi; "RpcStringBindingParse failed - %d"
0x18005ab55  mov     ecx, 8; int
0x18005ab5a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005ab5f  lea     rcx, [rbp+57h+StringBinding]; String
0x18005ab63  call    cs:__imp_RpcStringFreeW
0x18005ab69  jmp     short loc_18005AB18
0x18005ab6b  lea     rcx, [rbp+57h+StringBinding]; String
0x18005ab6f  call    cs:__imp_RpcStringFreeW
0x18005ab75  mov     rcx, [rbp+57h+Protseq]
0x18005ab79  lea     rdx, aNcalrpc; "ncalrpc"
0x18005ab80  call    cs:__imp__o__wcsicmp
0x18005ab86  lea     rcx, [rbp+57h+Protseq]; String
0x18005ab8a  mov     ebx, eax
0x18005ab8c  call    cs:__imp_RpcStringFreeW
0x18005ab92  test    ebx, ebx
0x18005ab94  jz      short loc_18005ABAC
0x18005ab96  lea     rdx, aClientIsNotUsi; "Client is not using LPC!"
0x18005ab9d  mov     ecx, 8; int
0x18005aba2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005aba7  jmp     loc_18005AB18
0x18005abac  xor     edx, edx; Val
0x18005abae  lea     rcx, [rbp+57h+var_A8]; void *
0x18005abb2  lea     r8d, [rdx+70h]; Size
0x18005abb6  call    memset_0
0x18005abbb  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x18005abbf  mov     [rbp+57h+RpcCallAttributes], 3
0x18005abc7  mov     rcx, rsi; ClientBinding
0x18005abca  call    cs:__imp_RpcServerInqCallAttributesW
0x18005abd0  test    eax, eax
0x18005abd2  jz      short loc_18005ABE0
0x18005abd4  lea     rdx, aRpcserverinqca; "RpcServerInqCallAttributes failed - %d"
0x18005abdb  jmp     loc_18005AB0B
0x18005abe0  cmp     [rbp+57h+var_88], 6
0x18005abe4  jz      short loc_18005ABEF
0x18005abe6  lea     rdx, aAuthlevelRpcCA; "AuthLevel != RPC_C_AUTHN_LEVEL_PKT_PRIV"...
0x18005abed  jmp     short loc_18005AB9D
0x18005abef  cmp     [rbp+57h+var_80], 0
0x18005abf3  jz      short loc_18005ABFE
0x18005abf5  lea     rdx, aNullSession; "NULL SESSION!"
0x18005abfc  jmp     short loc_18005AB9D
0x18005abfe  xor     ecx, ecx; BindingHandle
0x18005ac00  call    cs:__imp_RpcImpersonateClient
0x18005ac06  test    eax, eax
0x18005ac08  jz      short loc_18005AC16
0x18005ac0a  lea     rdx, aCannotImperson; "Cannot impersonate client: %d"
0x18005ac11  jmp     loc_18005AB0B
0x18005ac16  call    ?IsCallerSystem@CUtils@@SAJXZ; CUtils::IsCallerSystem(void)
0x18005ac1b  test    eax, eax
0x18005ac1d  jz      short loc_18005AC6E
0x18005ac1f  test    edi, edi
0x18005ac21  jz      short loc_18005AC96
0x18005ac23  mov     rdx, cs:?pAdminSid@CUtils@@0PEAXEA; SidToCheck
0x18005ac2a  lea     r8, [rbp+57h+IsMember]; IsMember
0x18005ac2e  xor     ecx, ecx; TokenHandle
0x18005ac30  mov     [rbp+57h+IsMember], 0
0x18005ac37  call    cs:__imp_CheckTokenMembership
0x18005ac3d  test    eax, eax
0x18005ac3f  jnz     short loc_18005AC90
0x18005ac41  call    cs:__imp_GetLastError
0x18005ac47  mov     ebx, eax
0x18005ac49  test    eax, eax
0x18005ac4b  jle     short loc_18005AC56
0x18005ac4d  movzx   ebx, ax
0x18005ac50  or      ebx, 80070000h
0x18005ac56  mov     r8d, ebx
0x18005ac59  lea     rdx, aChecktokenmemb; "CheckTokenMembership failed: 0x%x"
0x18005ac60  mov     ecx, 8; int
0x18005ac65  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005ac6a  test    ebx, ebx
0x18005ac6c  jnz     short loc_18005AC96
0x18005ac6e  call    cs:__imp_RpcRevertToSelf
0x18005ac74  test    eax, eax
0x18005ac76  jnz     short loc_18005ACB5
0x18005ac78  mov     rcx, [rbp+57h+var_30]
0x18005ac7c  xor     rcx, rsp; StackCookie
0x18005ac7f  call    __security_check_cookie
0x18005ac84  add     rsp, 0E8h
0x18005ac8b  pop     rdi
0x18005ac8c  pop     rsi
0x18005ac8d  pop     rbx
0x18005ac8e  pop     rbp
0x18005ac8f  retn
0x18005ac90  cmp     [rbp+57h+IsMember], 0
0x18005ac94  jnz     short loc_18005AC6E
0x18005ac96  lea     rdx, aCallersHaveToB; "Callers have to be system"
0x18005ac9d  mov     ecx, 8; int
0x18005aca2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005aca7  call    cs:__imp_RpcRevertToSelf
0x18005acad  test    eax, eax
0x18005acaf  jz      loc_18005AB18
0x18005acb5  lea     rdx, aRpcreverttosel_2; "RpcRevertToSelf failed: %d"
0x18005acbc  jmp     loc_18005AB0B
```
