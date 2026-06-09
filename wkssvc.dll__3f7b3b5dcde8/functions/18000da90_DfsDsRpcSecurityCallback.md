# DfsDsRpcSecurityCallback

- ea: `0x18000da90`
- end: `0x18000db94`
- name: `DfsDsRpcSecurityCallback`
- size: `260`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000da90`

## import_xrefs

- `ntdll!DbgPrint` at `0x18000db1d`
- `ntdll!DbgPrint` at `0x18000db46`
- `ntdll!DbgPrint` at `0x18000db81`
- `ntdll!DbgPrint` at `0x18000db1d`
- `ntdll!DbgPrint` at `0x18000db46`
- `ntdll!DbgPrint` at `0x18000db81`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000db30`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000db30`
- `RPCRT4!RpcStringFreeW` at `0x18000db61`
- `RPCRT4!RpcStringFreeW` at `0x18000db72`
- `RPCRT4!RpcStringFreeW` at `0x18000db61`
- `RPCRT4!RpcStringFreeW` at `0x18000db72`
- `RPCRT4!RpcStringBindingParseW` at `0x18000db08`
- `RPCRT4!RpcStringBindingParseW` at `0x18000db08`
- `RPCRT4!RpcBindingServerFromClient` at `0x18000dabc`
- `RPCRT4!RpcBindingServerFromClient` at `0x18000dabc`
- `RPCRT4!RpcBindingFree` at `0x18000db50`
- `RPCRT4!RpcBindingFree` at `0x18000db50`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18000dad8`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18000dad8`

## string_xrefs

- `0x18000db16`: `DfsDsRpcSecurityCallback: RpcStringBindingParse error %X\n`
- `0x18000db3a`: `DfsDsRpcSecurityCallback: Sequence protocol is not ncalrpc\n`
- `0x18000db7a`: `DfsDsRpcSecurityCallback: return Status = %X\n`

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
0x18000da90  mov     [rsp-8+arg_0], rbx
0x18000da95  push    rbp
0x18000da96  mov     rbp, rsp
0x18000da99  sub     rsp, 40h
0x18000da9d  mov     rcx, rdx; ClientBinding
0x18000daa0  mov     [rbp+ServerBinding], 0
0x18000daa8  lea     rdx, [rbp+ServerBinding]; ServerBinding
0x18000daac  mov     [rbp+StringBinding], 0
0x18000dab4  mov     [rbp+Protseq], 0
0x18000dabc  call    cs:__imp_RpcBindingServerFromClient
0x18000dac2  test    eax, eax
0x18000dac4  jz      short loc_18000DAD0
0x18000dac6  mov     eax, 5
0x18000dacb  jmp     loc_18000DB89
0x18000dad0  mov     rcx, [rbp+ServerBinding]; Binding
0x18000dad4  lea     rdx, [rbp+StringBinding]; StringBinding
0x18000dad8  call    cs:__imp_RpcBindingToStringBindingW
0x18000dade  test    eax, eax
0x18000dae0  jz      short loc_18000DAE9
0x18000dae2  mov     ebx, 5
0x18000dae7  jmp     short loc_18000DB4C
0x18000dae9  mov     rcx, [rbp+StringBinding]; StringBinding
0x18000daed  lea     r8, [rbp+Protseq]; Protseq
0x18000daf1  mov     [rsp+40h+NetworkOptions], 0; NetworkOptions
0x18000dafa  xor     r9d, r9d; NetworkAddr
0x18000dafd  xor     edx, edx; ObjUuid
0x18000daff  mov     [rsp+40h+Endpoint], 0; Endpoint
0x18000db08  call    cs:__imp_RpcStringBindingParseW
0x18000db0e  mov     ebx, eax
0x18000db10  test    eax, eax
0x18000db12  jz      short loc_18000DB25
0x18000db14  mov     edx, eax
0x18000db16  lea     rcx, aDfsdsrpcsecuri_1; "DfsDsRpcSecurityCallback: RpcStringBind"...
0x18000db1d  call    cs:__imp_DbgPrint
0x18000db23  jmp     short loc_18000DB4C
0x18000db25  mov     rcx, [rbp+Protseq]; lpString1
0x18000db29  lea     rdx, String2; "ncalrpc"
0x18000db30  call    cs:__imp_lstrcmpW
0x18000db36  test    eax, eax
0x18000db38  jz      short loc_18000DB4C
0x18000db3a  lea     rcx, aDfsdsrpcsecuri_0; "DfsDsRpcSecurityCallback: Sequence prot"...
0x18000db41  mov     ebx, 5
0x18000db46  call    cs:__imp_DbgPrint
0x18000db4c  lea     rcx, [rbp+ServerBinding]; Binding
0x18000db50  call    cs:__imp_RpcBindingFree
0x18000db56  cmp     [rbp+StringBinding], 0
0x18000db5b  jz      short loc_18000DB67
0x18000db5d  lea     rcx, [rbp+StringBinding]; String
0x18000db61  call    cs:__imp_RpcStringFreeW
0x18000db67  cmp     [rbp+Protseq], 0
0x18000db6c  jz      short loc_18000DB78
0x18000db6e  lea     rcx, [rbp+Protseq]; String
0x18000db72  call    cs:__imp_RpcStringFreeW
0x18000db78  mov     edx, ebx
0x18000db7a  lea     rcx, aDfsdsrpcsecuri; "DfsDsRpcSecurityCallback: return Status"...
0x18000db81  call    cs:__imp_DbgPrint
0x18000db87  mov     eax, ebx
0x18000db89  mov     rbx, [rsp+40h+arg_0]
0x18000db8e  add     rsp, 40h
0x18000db92  pop     rbp
0x18000db93  retn
```
