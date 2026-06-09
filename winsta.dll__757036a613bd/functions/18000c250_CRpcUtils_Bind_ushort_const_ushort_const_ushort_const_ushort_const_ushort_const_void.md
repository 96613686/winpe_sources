# CRpcUtils::Bind(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)

- ea: `0x18000c250`
- end: `0x18000c2cf`
- name: `?Bind@CRpcUtils@@SAJPEBG0000PEAPEAX@Z`
- size: `127`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, RPC_WSTR, RPC_BINDING_HANDLE *Binding)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c15c`
- `0x18002ae70`
- `0x18002cb5c`

## callees

- `0x180007890`
- `0x18000c250`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x18000c273`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000c273`
- `RPCRT4!RpcStringFreeW` at `0x18000c2a2`
- `RPCRT4!RpcStringFreeW` at `0x18000c2a2`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000c289`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000c289`

## string_xrefs

- `0x18000c2b0`: `Error %d in RpcStringBindingCompose`

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
0x18000c250  push    rbx
0x18000c252  sub     rsp, 40h
0x18000c256  lea     rax, [rsp+48h+String]
0x18000c25b  mov     [rsp+48h+String], 0
0x18000c264  mov     [rsp+48h+StringBinding], rax; StringBinding
0x18000c269  mov     rax, [rsp+48h+arg_20]
0x18000c26e  mov     [rsp+48h+Options], rax; Options
0x18000c273  call    cs:__imp_RpcStringBindingComposeW
0x18000c279  mov     ebx, eax
0x18000c27b  test    eax, eax
0x18000c27d  jnz     short loc_18000C2B0
0x18000c27f  mov     rdx, [rsp+48h+Binding]; Binding
0x18000c284  mov     rcx, [rsp+48h+String]; StringBinding
0x18000c289  call    cs:__imp_RpcBindingFromStringBindingW
0x18000c28f  mov     ebx, eax
0x18000c291  test    eax, eax
0x18000c293  jnz     short loc_18000C2B9
0x18000c295  cmp     [rsp+48h+String], 0
0x18000c29b  jz      short loc_18000C2A8
0x18000c29d  lea     rcx, [rsp+48h+String]; String
0x18000c2a2  call    cs:__imp_RpcStringFreeW
0x18000c2a8  mov     eax, ebx
0x18000c2aa  add     rsp, 40h
0x18000c2ae  pop     rbx
0x18000c2af  retn
0x18000c2b0  lea     rdx, aErrorDInRpcstr; "Error %d in RpcStringBindingCompose"
0x18000c2b7  jmp     short loc_18000C2C0
0x18000c2b9  lea     rdx, aErrorDInRpcbin_0; "Error %d in RpcBindingFromStringBinding"
0x18000c2c0  mov     r8d, eax
0x18000c2c3  mov     ecx, 8; int
0x18000c2c8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c2cd  jmp     short loc_18000C295
```
