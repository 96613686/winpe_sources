# Microsoft::Diagnostics::UtcWrapperBase::Initialize(void)

- ea: `0x180042544`
- end: `0x1800425f0`
- name: `?Initialize@UtcWrapperBase@Diagnostics@Microsoft@@QEAAJXZ`
- size: `172`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UtcWrapperBase *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180041e1c`

## callees

- `0x180003110`
- `0x180042544`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004256d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004256d`
- `RPCRT4!RpcStringFreeW` at `0x1800425d5`
- `RPCRT4!RpcStringFreeW` at `0x1800425d5`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800425bb`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800425bb`
- `RPCRT4!RpcStringBindingComposeW` at `0x18004259c`
- `RPCRT4!RpcStringBindingComposeW` at `0x18004259c`

## pseudocode

```c
int __fastcall Microsoft::Diagnostics::UtcWrapperBase::Initialize(RPC_BINDING_HANDLE *this)
{
  int result; // eax
  bool v3; // sf
  RPC_STATUS v4; // eax
  unsigned int v5; // ebx
  RPC_WSTR String; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 ProtSeq[20]; // [rsp+38h] [rbp-40h] BYREF

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
    v4 = RpcBindingFromStringBindingW(String, this + 1);
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
0x180042544  push    rbx
0x180042546  sub     rsp, 70h
0x18004254a  mov     rax, cs:__security_cookie
0x180042551  xor     rax, rsp
0x180042554  mov     [rsp+78h+var_18], rax
0x180042559  mov     rbx, rcx
0x18004255c  lea     r8, aNcalrpc; "ncalrpc"
0x180042563  lea     rcx, [rsp+78h+ProtSeq]
0x180042568  mov     edx, 14h
0x18004256d  call    cs:__imp__o_wcscpy_s
0x180042573  lea     rax, [rsp+78h+String]
0x180042578  mov     [rsp+78h+String], 0
0x180042581  mov     [rsp+78h+StringBinding], rax; StringBinding
0x180042586  lea     rdx, [rsp+78h+ProtSeq]; ProtSeq
0x18004258b  xor     r9d, r9d; Endpoint
0x18004258e  mov     [rsp+78h+Options], 0; Options
0x180042597  xor     r8d, r8d; NetworkAddr
0x18004259a  xor     ecx, ecx; ObjUuid
0x18004259c  call    cs:__imp_RpcStringBindingComposeW
0x1800425a2  test    eax, eax
0x1800425a4  jle     short loc_1800425B0
0x1800425a6  movzx   eax, ax
0x1800425a9  or      eax, 80070000h
0x1800425ae  test    eax, eax
0x1800425b0  js      short loc_1800425DD
0x1800425b2  mov     rcx, [rsp+78h+String]; StringBinding
0x1800425b7  lea     rdx, [rbx+8]; Binding
0x1800425bb  call    cs:__imp_RpcBindingFromStringBindingW
0x1800425c1  mov     ebx, eax
0x1800425c3  test    eax, eax
0x1800425c5  jle     short loc_1800425D0
0x1800425c7  movzx   ebx, ax
0x1800425ca  or      ebx, 80070000h
0x1800425d0  lea     rcx, [rsp+78h+String]; String
0x1800425d5  call    cs:__imp_RpcStringFreeW
0x1800425db  mov     eax, ebx
0x1800425dd  mov     rcx, [rsp+78h+var_18]
0x1800425e2  xor     rcx, rsp; StackCookie
0x1800425e5  call    __security_check_cookie
0x1800425ea  add     rsp, 70h
0x1800425ee  pop     rbx
0x1800425ef  retn
```
