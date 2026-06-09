# CRCMPrivateRpc::staticRpcSecurityCallback(void *,int)

- ea: `0x18005d790`
- end: `0x18005d9ee`
- name: `?staticRpcSecurityCallback@CRCMPrivateRpc@@CAJPEAXH@Z`
- size: `606`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE ClientBinding, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005d760`
- `0x18005d780`

## callees

- `0x180009940`
- `0x180033f60`
- `0x180034e64`
- `0x18005d790`
- `0x1800a27d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005d878`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005d878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d95b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d95b`
- `RPCRT4!RpcRevertToSelf` at `0x18005d98e`
- `RPCRT4!RpcRevertToSelf` at `0x18005d9ce`
- `RPCRT4!RpcRevertToSelf` at `0x18005d98e`
- `RPCRT4!RpcRevertToSelf` at `0x18005d9ce`
- `RPCRT4!RpcImpersonateClient` at `0x18005d90a`
- `RPCRT4!RpcImpersonateClient` at `0x18005d90a`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18005d8ce`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18005d8ce`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18005d7da`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18005d7da`
- `RPCRT4!RpcStringFreeW` at `0x18005d84f`
- `RPCRT4!RpcStringFreeW` at `0x18005d861`
- `RPCRT4!RpcStringFreeW` at `0x18005d88a`
- `RPCRT4!RpcStringFreeW` at `0x18005d84f`
- `RPCRT4!RpcStringFreeW` at `0x18005d861`
- `RPCRT4!RpcStringFreeW` at `0x18005d88a`
- `RPCRT4!RpcStringBindingParseW` at `0x18005d827`
- `RPCRT4!RpcStringBindingParseW` at `0x18005d827`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005d94b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005d94b`

## string_xrefs

- `0x18005d979`: `CheckTokenMembership failed: 0x%x`
- `0x18005d91a`: `Cannot impersonate client: %d`

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
0x18005d790  push    rbp
0x18005d792  push    rbx
0x18005d793  push    rsi
0x18005d794  push    rdi
0x18005d795  lea     rbp, [rsp-3Fh]
0x18005d79a  sub     rsp, 0E8h
0x18005d7a1  mov     rax, cs:__security_cookie
0x18005d7a8  xor     rax, rsp
0x18005d7ab  mov     [rbp+57h+var_30], rax
0x18005d7af  mov     edi, edx
0x18005d7b1  mov     [rbp+57h+StringBinding], 0
0x18005d7b9  xor     edx, edx; Val
0x18005d7bb  mov     [rbp+57h+Protseq], 0
0x18005d7c3  mov     rsi, rcx
0x18005d7c6  lea     rcx, [rbp+57h+RpcCallAttributes]; void *
0x18005d7ca  lea     r8d, [rdx+78h]; Size
0x18005d7ce  call    memset_0
0x18005d7d3  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x18005d7d7  mov     rcx, rsi; Binding
0x18005d7da  call    cs:__imp_RpcBindingToStringBindingW
0x18005d7e1  nop     dword ptr [rax+rax+00h]
0x18005d7e6  test    eax, eax
0x18005d7e8  jz      short loc_18005D808
0x18005d7ea  lea     rdx, aRpcbindingtost; "RpcBindingToStringBinding failed - %d"
0x18005d7f1  mov     r8d, eax
0x18005d7f4  mov     ecx, 8; int
0x18005d7f9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005d7fe  mov     eax, 5
0x18005d803  jmp     loc_18005D99E
0x18005d808  mov     rcx, [rbp+57h+StringBinding]; StringBinding
0x18005d80c  lea     r8, [rbp+57h+Protseq]; Protseq
0x18005d810  mov     [rsp+100h+NetworkOptions], 0; NetworkOptions
0x18005d819  xor     r9d, r9d; NetworkAddr
0x18005d81c  xor     edx, edx; ObjUuid
0x18005d81e  mov     [rsp+100h+Endpoint], 0; Endpoint
0x18005d827  call    cs:__imp_RpcStringBindingParseW
0x18005d82e  nop     dword ptr [rax+rax+00h]
0x18005d833  test    eax, eax
0x18005d835  jz      short loc_18005D85D
0x18005d837  mov     r8d, eax
0x18005d83a  lea     rdx, aRpcstringbindi; "RpcStringBindingParse failed - %d"
0x18005d841  mov     ecx, 8; int
0x18005d846  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005d84b  lea     rcx, [rbp+57h+StringBinding]; String
0x18005d84f  call    cs:__imp_RpcStringFreeW
0x18005d856  nop     dword ptr [rax+rax+00h]
0x18005d85b  jmp     short loc_18005D7FE
0x18005d85d  lea     rcx, [rbp+57h+StringBinding]; String
0x18005d861  call    cs:__imp_RpcStringFreeW
0x18005d868  nop     dword ptr [rax+rax+00h]
0x18005d86d  mov     rcx, [rbp+57h+Protseq]
0x18005d871  lea     rdx, aNcalrpc; "ncalrpc"
0x18005d878  call    cs:__imp__o__wcsicmp
0x18005d87f  nop     dword ptr [rax+rax+00h]
0x18005d884  lea     rcx, [rbp+57h+Protseq]; String
0x18005d888  mov     ebx, eax
0x18005d88a  call    cs:__imp_RpcStringFreeW
0x18005d891  nop     dword ptr [rax+rax+00h]
0x18005d896  test    ebx, ebx
0x18005d898  jz      short loc_18005D8B0
0x18005d89a  lea     rdx, aClientIsNotUsi; "Client is not using LPC!"
0x18005d8a1  mov     ecx, 8; int
0x18005d8a6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005d8ab  jmp     loc_18005D7FE
0x18005d8b0  xor     edx, edx; Val
0x18005d8b2  lea     rcx, [rbp+57h+var_A8]; void *
0x18005d8b6  lea     r8d, [rdx+70h]; Size
0x18005d8ba  call    memset_0
0x18005d8bf  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x18005d8c3  mov     [rbp+57h+RpcCallAttributes], 3
0x18005d8cb  mov     rcx, rsi; ClientBinding
0x18005d8ce  call    cs:__imp_RpcServerInqCallAttributesW
0x18005d8d5  nop     dword ptr [rax+rax+00h]
0x18005d8da  test    eax, eax
0x18005d8dc  jz      short loc_18005D8EA
0x18005d8de  lea     rdx, aRpcserverinqca; "RpcServerInqCallAttributes failed - %d"
0x18005d8e5  jmp     loc_18005D7F1
0x18005d8ea  cmp     [rbp+57h+var_88], 6
0x18005d8ee  jz      short loc_18005D8F9
0x18005d8f0  lea     rdx, aAuthlevelRpcCA; "AuthLevel != RPC_C_AUTHN_LEVEL_PKT_PRIV"...
0x18005d8f7  jmp     short loc_18005D8A1
0x18005d8f9  cmp     [rbp+57h+var_80], 0
0x18005d8fd  jz      short loc_18005D908
0x18005d8ff  lea     rdx, aNullSession; "NULL SESSION!"
0x18005d906  jmp     short loc_18005D8A1
0x18005d908  xor     ecx, ecx; BindingHandle
0x18005d90a  call    cs:__imp_RpcImpersonateClient
0x18005d911  nop     dword ptr [rax+rax+00h]
0x18005d916  test    eax, eax
0x18005d918  jz      short loc_18005D926
0x18005d91a  lea     rdx, aCannotImperson; "Cannot impersonate client: %d"
0x18005d921  jmp     loc_18005D7F1
0x18005d926  call    ?IsCallerSystem@CUtils@@SAJXZ; CUtils::IsCallerSystem(void)
0x18005d92b  test    eax, eax
0x18005d92d  jz      short loc_18005D98E
0x18005d92f  test    edi, edi
0x18005d931  jz      loc_18005D9BD
0x18005d937  mov     rdx, cs:?pAdminSid@CUtils@@0PEAXEA; SidToCheck
0x18005d93e  lea     r8, [rbp+57h+IsMember]; IsMember
0x18005d942  xor     ecx, ecx; TokenHandle
0x18005d944  mov     [rbp+57h+IsMember], 0
0x18005d94b  call    cs:__imp_CheckTokenMembership
0x18005d952  nop     dword ptr [rax+rax+00h]
0x18005d957  test    eax, eax
0x18005d959  jnz     short loc_18005D9B7
0x18005d95b  call    cs:__imp_GetLastError
0x18005d962  nop     dword ptr [rax+rax+00h]
0x18005d967  mov     ebx, eax
0x18005d969  test    eax, eax
0x18005d96b  jle     short loc_18005D976
0x18005d96d  movzx   ebx, ax
0x18005d970  or      ebx, 80070000h
0x18005d976  mov     r8d, ebx
0x18005d979  lea     rdx, aChecktokenmemb; "CheckTokenMembership failed: 0x%x"
0x18005d980  mov     ecx, 8; int
0x18005d985  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005d98a  test    ebx, ebx
0x18005d98c  jnz     short loc_18005D9BD
0x18005d98e  call    cs:__imp_RpcRevertToSelf
0x18005d995  nop     dword ptr [rax+rax+00h]
0x18005d99a  test    eax, eax
0x18005d99c  jnz     short loc_18005D9E2
0x18005d99e  mov     rcx, [rbp+57h+var_30]
0x18005d9a2  xor     rcx, rsp; StackCookie
0x18005d9a5  call    __security_check_cookie
0x18005d9aa  add     rsp, 0E8h
0x18005d9b1  pop     rdi
0x18005d9b2  pop     rsi
0x18005d9b3  pop     rbx
0x18005d9b4  pop     rbp
0x18005d9b5  retn
0x18005d9b7  cmp     [rbp+57h+IsMember], 0
0x18005d9bb  jnz     short loc_18005D98E
0x18005d9bd  lea     rdx, aCallersHaveToB; "Callers have to be system"
0x18005d9c4  mov     ecx, 8; int
0x18005d9c9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005d9ce  call    cs:__imp_RpcRevertToSelf
0x18005d9d5  nop     dword ptr [rax+rax+00h]
0x18005d9da  test    eax, eax
0x18005d9dc  jz      loc_18005D7FE
0x18005d9e2  lea     rdx, aRpcreverttosel_2; "RpcRevertToSelf failed: %d"
0x18005d9e9  jmp     loc_18005D7F1
```
