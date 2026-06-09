# CRpcUtils::Bind(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)

- ea: `0x18000de00`
- end: `0x18000de92`
- name: `?Bind@CRpcUtils@@SAJPEBG0000PEAPEAX@Z`
- size: `146`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, RPC_WSTR, RPC_BINDING_HANDLE *Binding)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dcec`
- `0x18002ccd0`
- `0x18002eeec`

## callees

- `0x180005b40`
- `0x18000de00`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x18000de23`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000de23`
- `RPCRT4!RpcStringFreeW` at `0x18000de5e`
- `RPCRT4!RpcStringFreeW` at `0x18000de5e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000de3f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000de3f`

## string_xrefs

- `0x18000de73`: `Error %d in RpcStringBindingCompose`

## pseudocode

```c
__int64 __fastcall CRpcUtils::Bind(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        RPC_WSTR Options,
        RPC_BINDING_HANDLE *Binding)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  RPC_WSTR String[3]; // [rsp+30h] [rbp-18h] BYREF

  String[0] = 0;
  v6 = RpcStringBindingComposeW(a1, a2, a3, a4, Options, String);
  v7 = v6;
  if ( v6 )
  {
    _DbgPrintMessage(8, "Error %d in RpcStringBindingCompose", v6);
  }
  else
  {
    v8 = RpcBindingFromStringBindingW(String[0], Binding);
    v7 = v8;
    if ( v8 )
      _DbgPrintMessage(8, "Error %d in RpcBindingFromStringBinding", v8);
  }
  if ( String[0] )
    RpcStringFreeW(String);
  return v7;
}

```

## disassembly

```asm
0x18000de00  push    rbx
0x18000de02  sub     rsp, 40h
0x18000de06  lea     rax, [rsp+48h+String]
0x18000de0b  mov     [rsp+48h+String], 0
0x18000de14  mov     [rsp+48h+StringBinding], rax; StringBinding
0x18000de19  mov     rax, [rsp+48h+arg_20]
0x18000de1e  mov     [rsp+48h+Options], rax; Options
0x18000de23  call    cs:__imp_RpcStringBindingComposeW
0x18000de2a  nop     dword ptr [rax+rax+00h]
0x18000de2f  mov     ebx, eax
0x18000de31  test    eax, eax
0x18000de33  jnz     short loc_18000DE73
0x18000de35  mov     rdx, [rsp+48h+Binding]; Binding
0x18000de3a  mov     rcx, [rsp+48h+String]; StringBinding
0x18000de3f  call    cs:__imp_RpcBindingFromStringBindingW
0x18000de46  nop     dword ptr [rax+rax+00h]
0x18000de4b  mov     ebx, eax
0x18000de4d  test    eax, eax
0x18000de4f  jnz     short loc_18000DE7C
0x18000de51  cmp     [rsp+48h+String], 0
0x18000de57  jz      short loc_18000DE6A
0x18000de59  lea     rcx, [rsp+48h+String]; String
0x18000de5e  call    cs:__imp_RpcStringFreeW
0x18000de65  nop     dword ptr [rax+rax+00h]
0x18000de6a  mov     eax, ebx
0x18000de6c  add     rsp, 40h
0x18000de70  pop     rbx
0x18000de71  retn
0x18000de73  lea     rdx, aErrorDInRpcstr; "Error %d in RpcStringBindingCompose"
0x18000de7a  jmp     short loc_18000DE83
0x18000de7c  lea     rdx, aErrorDInRpcbin_0; "Error %d in RpcBindingFromStringBinding"
0x18000de83  mov     r8d, eax
0x18000de86  mov     ecx, 8; int
0x18000de8b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000de90  jmp     short loc_18000DE51
```
