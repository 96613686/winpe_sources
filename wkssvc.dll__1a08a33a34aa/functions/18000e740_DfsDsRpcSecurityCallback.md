# DfsDsRpcSecurityCallback

- ea: `0x18000e740`
- end: `0x18000e881`
- name: `DfsDsRpcSecurityCallback`
- size: `321`
- prototype: `RPC_IF_CALLBACK_FN`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e740`

## import_xrefs

- `ntdll!DbgPrint` at `0x18000e7df`
- `ntdll!DbgPrint` at `0x18000e814`
- `ntdll!DbgPrint` at `0x18000e867`
- `ntdll!DbgPrint` at `0x18000e7df`
- `ntdll!DbgPrint` at `0x18000e814`
- `ntdll!DbgPrint` at `0x18000e867`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000e7f8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000e7f8`
- `RPCRT4!RpcStringFreeW` at `0x18000e83b`
- `RPCRT4!RpcStringFreeW` at `0x18000e852`
- `RPCRT4!RpcStringFreeW` at `0x18000e83b`
- `RPCRT4!RpcStringFreeW` at `0x18000e852`
- `RPCRT4!RpcStringBindingParseW` at `0x18000e7c4`
- `RPCRT4!RpcStringBindingParseW` at `0x18000e7c4`
- `RPCRT4!RpcBindingServerFromClient` at `0x18000e76c`
- `RPCRT4!RpcBindingServerFromClient` at `0x18000e76c`
- `RPCRT4!RpcBindingFree` at `0x18000e824`
- `RPCRT4!RpcBindingFree` at `0x18000e824`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18000e78e`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18000e78e`

## string_xrefs

- `0x18000e7d8`: `DfsDsRpcSecurityCallback: RpcStringBindingParse error %X\n`
- `0x18000e808`: `DfsDsRpcSecurityCallback: Sequence protocol is not ncalrpc\n`
- `0x18000e860`: `DfsDsRpcSecurityCallback: return Status = %X\n`

## pseudocode

```c
__int64 __fastcall DfsDsRpcSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  unsigned int v3; // ebx
  RPC_STATUS v4; // eax
  RPC_BINDING_HANDLE ServerBinding[2]; // [rsp+30h] [rbp-10h] BYREF
  RPC_WSTR StringBinding; // [rsp+60h] [rbp+20h] BYREF
  RPC_WSTR Protseq; // [rsp+68h] [rbp+28h] BYREF

  ServerBinding[0] = 0;
  StringBinding = 0;
  Protseq = 0;
  if ( RpcBindingServerFromClient(Context, ServerBinding) )
    return 5;
  if ( RpcBindingToStringBindingW(ServerBinding[0], &StringBinding) )
  {
    v3 = 5;
  }
  else
  {
    v4 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
    v3 = v4;
    if ( v4 )
    {
      DbgPrint("DfsDsRpcSecurityCallback: RpcStringBindingParse error %X\n", v4);
    }
    else if ( lstrcmpW(Protseq, L"ncalrpc") )
    {
      v3 = 5;
      DbgPrint("DfsDsRpcSecurityCallback: Sequence protocol is not ncalrpc\n");
    }
  }
  RpcBindingFree(ServerBinding);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  DbgPrint("DfsDsRpcSecurityCallback: return Status = %X\n", v3);
  return v3;
}

```

## disassembly

```asm
0x18000e740  mov     [rsp-8+arg_0], rbx
0x18000e745  push    rbp
0x18000e746  mov     rbp, rsp
0x18000e749  sub     rsp, 40h
0x18000e74d  mov     rcx, rdx; ClientBinding
0x18000e750  mov     [rbp+ServerBinding], 0
0x18000e758  lea     rdx, [rbp+ServerBinding]; ServerBinding
0x18000e75c  mov     [rbp+StringBinding], 0
0x18000e764  mov     [rbp+Protseq], 0
0x18000e76c  call    cs:__imp_RpcBindingServerFromClient
0x18000e773  nop     dword ptr [rax+rax+00h]
0x18000e778  test    eax, eax
0x18000e77a  jz      short loc_18000E786
0x18000e77c  mov     eax, 5
0x18000e781  jmp     loc_18000E875
0x18000e786  mov     rcx, [rbp+ServerBinding]; Binding
0x18000e78a  lea     rdx, [rbp+StringBinding]; StringBinding
0x18000e78e  call    cs:__imp_RpcBindingToStringBindingW
0x18000e795  nop     dword ptr [rax+rax+00h]
0x18000e79a  test    eax, eax
0x18000e79c  jz      short loc_18000E7A5
0x18000e79e  mov     ebx, 5
0x18000e7a3  jmp     short loc_18000E820
0x18000e7a5  mov     rcx, [rbp+StringBinding]; StringBinding
0x18000e7a9  lea     r8, [rbp+Protseq]; Protseq
0x18000e7ad  mov     [rsp+40h+NetworkOptions], 0; NetworkOptions
0x18000e7b6  xor     r9d, r9d; NetworkAddr
0x18000e7b9  xor     edx, edx; ObjUuid
0x18000e7bb  mov     [rsp+40h+Endpoint], 0; Endpoint
0x18000e7c4  call    cs:__imp_RpcStringBindingParseW
0x18000e7cb  nop     dword ptr [rax+rax+00h]
0x18000e7d0  mov     ebx, eax
0x18000e7d2  test    eax, eax
0x18000e7d4  jz      short loc_18000E7ED
0x18000e7d6  mov     edx, eax
0x18000e7d8  lea     rcx, aDfsdsrpcsecuri_1; "DfsDsRpcSecurityCallback: RpcStringBind"...
0x18000e7df  call    cs:__imp_DbgPrint
0x18000e7e6  nop     dword ptr [rax+rax+00h]
0x18000e7eb  jmp     short loc_18000E820
0x18000e7ed  mov     rcx, [rbp+Protseq]; lpString1
0x18000e7f1  lea     rdx, String2; "ncalrpc"
0x18000e7f8  call    cs:__imp_lstrcmpW
0x18000e7ff  nop     dword ptr [rax+rax+00h]
0x18000e804  test    eax, eax
0x18000e806  jz      short loc_18000E820
0x18000e808  lea     rcx, aDfsdsrpcsecuri_0; "DfsDsRpcSecurityCallback: Sequence prot"...
0x18000e80f  mov     ebx, 5
0x18000e814  call    cs:__imp_DbgPrint
0x18000e81b  nop     dword ptr [rax+rax+00h]
0x18000e820  lea     rcx, [rbp+ServerBinding]; Binding
0x18000e824  call    cs:__imp_RpcBindingFree
0x18000e82b  nop     dword ptr [rax+rax+00h]
0x18000e830  cmp     [rbp+StringBinding], 0
0x18000e835  jz      short loc_18000E847
0x18000e837  lea     rcx, [rbp+StringBinding]; String
0x18000e83b  call    cs:__imp_RpcStringFreeW
0x18000e842  nop     dword ptr [rax+rax+00h]
0x18000e847  cmp     [rbp+Protseq], 0
0x18000e84c  jz      short loc_18000E85E
0x18000e84e  lea     rcx, [rbp+Protseq]; String
0x18000e852  call    cs:__imp_RpcStringFreeW
0x18000e859  nop     dword ptr [rax+rax+00h]
0x18000e85e  mov     edx, ebx
0x18000e860  lea     rcx, aDfsdsrpcsecuri; "DfsDsRpcSecurityCallback: return Status"...
0x18000e867  call    cs:__imp_DbgPrint
0x18000e86e  nop     dword ptr [rax+rax+00h]
0x18000e873  mov     eax, ebx
0x18000e875  mov     rbx, [rsp+40h+arg_0]
0x18000e87a  add     rsp, 40h
0x18000e87e  pop     rbp
0x18000e87f  retn
```
