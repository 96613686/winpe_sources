# UtcCreateSessionHandle

- ea: `0x1800027d0`
- end: `0x180002882`
- name: `UtcCreateSessionHandle`
- size: `178`
- prototype: `int __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001400`
- `0x1800027d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180002800`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180002800`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000284d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000284d`
- `RPCRT4!RpcStringFreeW` at `0x180002867`
- `RPCRT4!RpcStringFreeW` at `0x180002867`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000282f`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000282f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800027d0  push    rbx
0x1800027d2  sub     rsp, 70h
0x1800027d6  mov     rax, cs:__security_cookie
0x1800027dd  xor     rax, rsp
0x1800027e0  mov     [rsp+78h+var_18], rax
0x1800027e5  mov     rbx, rcx
0x1800027e8  mov     qword ptr [rcx], 0
0x1800027ef  lea     rcx, [rsp+78h+ProtSeq]
0x1800027f4  mov     edx, 14h
0x1800027f9  lea     r8, aNcalrpc; "ncalrpc"
0x180002800  call    cs:__imp__o_wcscpy_s
0x180002806  lea     rax, [rsp+78h+String]
0x18000280b  mov     [rsp+78h+String], 0
0x180002814  mov     [rsp+78h+StringBinding], rax; StringBinding
0x180002819  lea     rdx, [rsp+78h+ProtSeq]; ProtSeq
0x18000281e  xor     r9d, r9d; Endpoint
0x180002821  mov     [rsp+78h+Options], 0; Options
0x18000282a  xor     r8d, r8d; NetworkAddr
0x18000282d  xor     ecx, ecx; ObjUuid
0x18000282f  call    cs:__imp_RpcStringBindingComposeW
0x180002835  test    eax, eax
0x180002837  jle     short loc_180002843
0x180002839  movzx   eax, ax
0x18000283c  or      eax, 80070000h
0x180002841  test    eax, eax
0x180002843  js      short loc_18000286F
0x180002845  mov     rcx, [rsp+78h+String]; StringBinding
0x18000284a  mov     rdx, rbx; Binding
0x18000284d  call    cs:__imp_RpcBindingFromStringBindingW
0x180002853  mov     ebx, eax
0x180002855  test    eax, eax
0x180002857  jle     short loc_180002862
0x180002859  movzx   ebx, ax
0x18000285c  or      ebx, 80070000h
0x180002862  lea     rcx, [rsp+78h+String]; String
0x180002867  call    cs:__imp_RpcStringFreeW
0x18000286d  mov     eax, ebx
0x18000286f  mov     rcx, [rsp+78h+var_18]
0x180002874  xor     rcx, rsp; StackCookie
0x180002877  call    __security_check_cookie
0x18000287c  add     rsp, 70h
0x180002880  pop     rbx
0x180002881  retn
```
