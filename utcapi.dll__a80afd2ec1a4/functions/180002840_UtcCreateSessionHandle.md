# UtcCreateSessionHandle

- ea: `0x180002840`
- end: `0x18000290b`
- name: `UtcCreateSessionHandle`
- size: `203`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001400`
- `0x180002840`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180002870`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180002870`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800028c9`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800028c9`
- `RPCRT4!RpcStringFreeW` at `0x1800028e9`
- `RPCRT4!RpcStringFreeW` at `0x1800028e9`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800028a5`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800028a5`

## pseudocode

```c
int __fastcall UtcCreateSessionHandle(RPC_BINDING_HANDLE *Binding)
{
  int result; // eax
  bool v3; // sf
  RPC_STATUS v4; // eax
  unsigned int v5; // ebx
  RPC_WSTR String; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 ProtSeq[20]; // [rsp+38h] [rbp-40h] BYREF

  *Binding = 0;
  _o_wcscpy_s(ProtSeq, 20, L"ncalrpc");
  String = 0;
  result = RpcStringBindingComposeW(0, ProtSeq, 0, 0, 0, &String);
  v3 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v3 = result < 0;
  }
  if ( !v3 )
  {
    v4 = RpcBindingFromStringBindingW(String, Binding);
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    RpcStringFreeW(&String);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180002840  push    rbx
0x180002842  sub     rsp, 70h
0x180002846  mov     rax, cs:__security_cookie
0x18000284d  xor     rax, rsp
0x180002850  mov     [rsp+78h+var_18], rax
0x180002855  mov     rbx, rcx
0x180002858  mov     qword ptr [rcx], 0
0x18000285f  lea     rcx, [rsp+78h+ProtSeq]
0x180002864  mov     edx, 14h
0x180002869  lea     r8, aNcalrpc; "ncalrpc"
0x180002870  call    cs:__imp__o_wcscpy_s
0x180002877  nop     dword ptr [rax+rax+00h]
0x18000287c  lea     rax, [rsp+78h+String]
0x180002881  mov     [rsp+78h+String], 0
0x18000288a  mov     [rsp+78h+StringBinding], rax; StringBinding
0x18000288f  lea     rdx, [rsp+78h+ProtSeq]; ProtSeq
0x180002894  xor     r9d, r9d; Endpoint
0x180002897  mov     [rsp+78h+Options], 0; Options
0x1800028a0  xor     r8d, r8d; NetworkAddr
0x1800028a3  xor     ecx, ecx; ObjUuid
0x1800028a5  call    cs:__imp_RpcStringBindingComposeW
0x1800028ac  nop     dword ptr [rax+rax+00h]
0x1800028b1  test    eax, eax
0x1800028b3  jle     short loc_1800028BF
0x1800028b5  movzx   eax, ax
0x1800028b8  or      eax, 80070000h
0x1800028bd  test    eax, eax
0x1800028bf  js      short loc_1800028F7
0x1800028c1  mov     rcx, [rsp+78h+String]; StringBinding
0x1800028c6  mov     rdx, rbx; Binding
0x1800028c9  call    cs:__imp_RpcBindingFromStringBindingW
0x1800028d0  nop     dword ptr [rax+rax+00h]
0x1800028d5  mov     ebx, eax
0x1800028d7  test    eax, eax
0x1800028d9  jle     short loc_1800028E4
0x1800028db  movzx   ebx, ax
0x1800028de  or      ebx, 80070000h
0x1800028e4  lea     rcx, [rsp+78h+String]; String
0x1800028e9  call    cs:__imp_RpcStringFreeW
0x1800028f0  nop     dword ptr [rax+rax+00h]
0x1800028f5  mov     eax, ebx
0x1800028f7  mov     rcx, [rsp+78h+var_18]
0x1800028fc  xor     rcx, rsp; StackCookie
0x1800028ff  call    __security_check_cookie
0x180002904  add     rsp, 70h
0x180002908  pop     rbx
0x180002909  retn
```
