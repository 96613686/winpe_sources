# PLSA_LOOKPR_SERVER_NAME_bind

- ea: `0x180011dc0`
- end: `0x180011e46`
- name: `PLSA_LOOKPR_SERVER_NAME_bind`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180011dc0`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180011e21`
- `RPCRT4!RpcStringFreeW` at `0x180011e21`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180011e14`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180011e14`
- `RPCRT4!RpcStringBindingComposeW` at `0x180011dfe`
- `RPCRT4!RpcStringBindingComposeW` at `0x180011dfe`
- `RPCRT4!I_RpcMapWin32Status` at `0x180011e2d`
- `RPCRT4!I_RpcMapWin32Status` at `0x180011e2d`

## pseudocode

```c
RPC_BINDING_HANDLE __fastcall PLSA_LOOKPR_SERVER_NAME_bind(__int64 a1)
{
  RPC_STATUS v1; // ebx
  RPC_WSTR String; // [rsp+40h] [rbp+8h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+48h] [rbp+10h] BYREF

  String = 0;
  Binding = 0;
  if ( a1 )
    return 0;
  if ( ((v1 = RpcStringBindingComposeW(
                0,
                (RPC_WSTR)L"ncalrpc",
                0,
                (RPC_WSTR)L"lsapolicylookup",
                (RPC_WSTR)&Options,
                &String)) != 0
     || (v1 = RpcBindingFromStringBindingW(String, &Binding), RpcStringFreeW(&String), v1))
    && I_RpcMapWin32Status(v1) < 0 )
  {
    return 0;
  }
  else
  {
    return Binding;
  }
}

```

## disassembly

```asm
0x180011dc0  push    rbx
0x180011dc2  sub     rsp, 30h
0x180011dc6  xor     eax, eax
0x180011dc8  mov     [rsp+38h+String], rax
0x180011dcd  mov     [rsp+38h+Binding], rax
0x180011dd2  test    rcx, rcx
0x180011dd5  jnz     short loc_180011E42
0x180011dd7  lea     rax, [rsp+38h+String]
0x180011ddc  xor     r8d, r8d; NetworkAddr
0x180011ddf  mov     [rsp+38h+StringBinding], rax; StringBinding
0x180011de4  lea     r9, aLsapolicylooku; "lsapolicylookup"
0x180011deb  lea     rax, Options
0x180011df2  lea     rdx, Protseq; "ncalrpc"
0x180011df9  mov     [rsp+38h+Options], rax; Options
0x180011dfe  call    cs:__imp_RpcStringBindingComposeW
0x180011e04  mov     ebx, eax
0x180011e06  test    eax, eax
0x180011e08  jnz     short loc_180011E2B
0x180011e0a  mov     rcx, [rsp+38h+String]; StringBinding
0x180011e0f  lea     rdx, [rsp+38h+Binding]; Binding
0x180011e14  call    cs:__imp_RpcBindingFromStringBindingW
0x180011e1a  lea     rcx, [rsp+38h+String]; String
0x180011e1f  mov     ebx, eax
0x180011e21  call    cs:__imp_RpcStringFreeW
0x180011e27  test    ebx, ebx
0x180011e29  jz      short loc_180011E37
0x180011e2b  mov     ecx, ebx; Status
0x180011e2d  call    cs:__imp_I_RpcMapWin32Status
0x180011e33  test    eax, eax
0x180011e35  js      short loc_180011E42
0x180011e37  mov     rax, [rsp+38h+Binding]
0x180011e3c  add     rsp, 30h
0x180011e40  pop     rbx
0x180011e41  retn
0x180011e42  xor     eax, eax
0x180011e44  jmp     short loc_180011E3C
```
