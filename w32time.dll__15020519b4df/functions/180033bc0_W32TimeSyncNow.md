# W32TimeSyncNow

- ea: `0x180033bc0`
- end: `0x180033d74`
- name: `W32TimeSyncNow`
- size: `436`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180029ad0`
- `0x180033bc0`
- `0x180050e38`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180033c49`
- `RPCRT4!RpcStringFreeW` at `0x180033d16`
- `RPCRT4!RpcStringFreeW` at `0x180033c49`
- `RPCRT4!RpcStringFreeW` at `0x180033d16`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180033c36`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180033d03`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180033c36`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180033d03`
- `RPCRT4!RpcStringBindingComposeW` at `0x180033c13`
- `RPCRT4!RpcStringBindingComposeW` at `0x180033ce4`
- `RPCRT4!RpcStringBindingComposeW` at `0x180033c13`
- `RPCRT4!RpcStringBindingComposeW` at `0x180033ce4`
- `RPCRT4!RpcBindingFree` at `0x180033c9e`
- `RPCRT4!RpcBindingFree` at `0x180033d5b`
- `RPCRT4!RpcBindingFree` at `0x180033c9e`
- `RPCRT4!RpcBindingFree` at `0x180033d5b`

## pseudocode

```c
__int64 __fastcall W32TimeSyncNow(RPC_WSTR NetworkAddr, unsigned int a2, unsigned int a3)
{
  unsigned int v6; // ebx
  RPC_WSTR StringBinding[6]; // [rsp+38h] [rbp-30h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+88h] [rbp+20h] BYREF

  StringBinding[0] = 0;
  Binding = 0;
  v6 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", NetworkAddr, (RPC_WSTR)L"\\PIPE\\W32TIME", 0, StringBinding);
  if ( !v6 )
  {
    v6 = RpcBindingFromStringBindingW(StringBinding[0], &Binding);
    RpcStringFreeW(StringBinding);
    SetMyRpcSecurity(Binding);
    if ( !v6 )
    {
      v6 = c_W32TimeSync(Binding, a2, a3);
      RpcBindingFree(&Binding);
    }
  }
  if ( v6 == 1717 || v6 == 1722 )
  {
    v6 = RpcStringBindingComposeW(
           0,
           (RPC_WSTR)L"ncacn_np",
           NetworkAddr,
           (RPC_WSTR)L"\\PIPE\\W32TIME_ALT",
           0,
           StringBinding);
    if ( !v6 )
    {
      v6 = RpcBindingFromStringBindingW(StringBinding[0], &Binding);
      RpcStringFreeW(StringBinding);
      SetMyRpcSecurity(Binding);
      if ( !v6 )
      {
        v6 = c_W32TimeSync(Binding, a2, a3);
        RpcBindingFree(&Binding);
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180033bc0  mov     r11, rsp
0x180033bc3  mov     [r11+18h], r8d
0x180033bc7  mov     [rsp+arg_8], edx
0x180033bcb  mov     [r11+8], rcx
0x180033bcf  push    rbx
0x180033bd0  push    rsi
0x180033bd1  push    rdi
0x180033bd2  push    r14
0x180033bd4  sub     rsp, 48h
0x180033bd8  mov     edi, r8d
0x180033bdb  mov     esi, edx
0x180033bdd  mov     r14, rcx
0x180033be0  mov     qword ptr [r11-30h], 0
0x180033be8  mov     qword ptr [r11+20h], 0
0x180033bf0  lea     rax, [r11-30h]
0x180033bf4  mov     [r11-40h], rax
0x180033bf8  mov     qword ptr [r11-48h], 0
0x180033c00  lea     r9, Endpoint; "\\PIPE\\W32TIME"
0x180033c07  mov     r8, rcx; NetworkAddr
0x180033c0a  lea     rdx, ProtSeq; "ncacn_np"
0x180033c11  xor     ecx, ecx; ObjUuid
0x180033c13  call    cs:__imp_RpcStringBindingComposeW
0x180033c1a  nop     dword ptr [rax+rax+00h]
0x180033c1f  mov     ebx, eax
0x180033c21  test    eax, eax
0x180033c23  jnz     loc_180033CAA
0x180033c29  lea     rdx, [rsp+68h+Binding]; Binding
0x180033c31  mov     rcx, [rsp+68h+StringBinding]; StringBinding
0x180033c36  call    cs:__imp_RpcBindingFromStringBindingW
0x180033c3d  nop     dword ptr [rax+rax+00h]
0x180033c42  mov     ebx, eax
0x180033c44  lea     rcx, [rsp+68h+StringBinding]; String
0x180033c49  call    cs:__imp_RpcStringFreeW
0x180033c50  nop     dword ptr [rax+rax+00h]
0x180033c55  mov     rcx, [rsp+68h+Binding]; Binding
0x180033c5d  call    ?SetMyRpcSecurity@@YAJPEAX@Z; SetMyRpcSecurity(void *)
0x180033c62  test    ebx, ebx
0x180033c64  jnz     short loc_180033CAA
0x180033c66  mov     r8d, edi
0x180033c69  mov     edx, esi
0x180033c6b  mov     rcx, [rsp+68h+Binding]
0x180033c73  call    c_W32TimeSync
0x180033c78  mov     ebx, eax
0x180033c7a  mov     [rsp+68h+var_38], eax
0x180033c7e  jmp     short loc_180033C96
0x180033c80  mov     ebx, eax
0x180033c82  mov     [rsp+68h+var_38], eax
0x180033c86  mov     edi, [rsp+68h+arg_10]
0x180033c8d  mov     esi, [rsp+68h+arg_8]
0x180033c91  mov     r14, [rsp+68h+arg_0]
0x180033c96  lea     rcx, [rsp+68h+Binding]; Binding
0x180033c9e  call    cs:__imp_RpcBindingFree
0x180033ca5  nop     dword ptr [rax+rax+00h]
0x180033caa  cmp     ebx, 6B5h
0x180033cb0  jz      short loc_180033CBE
0x180033cb2  cmp     ebx, 6BAh
0x180033cb8  jnz     loc_180033D67
0x180033cbe  lea     rax, [rsp+68h+StringBinding]
0x180033cc3  mov     [rsp+68h+var_40], rax; StringBinding
0x180033cc8  mov     [rsp+68h+Options], 0; Options
0x180033cd1  lea     r9, aPipeW32timeAlt; "\\PIPE\\W32TIME_ALT"
0x180033cd8  mov     r8, r14; NetworkAddr
0x180033cdb  lea     rdx, ProtSeq; "ncacn_np"
0x180033ce2  xor     ecx, ecx; ObjUuid
0x180033ce4  call    cs:__imp_RpcStringBindingComposeW
0x180033ceb  nop     dword ptr [rax+rax+00h]
0x180033cf0  mov     ebx, eax
0x180033cf2  test    eax, eax
0x180033cf4  jnz     short loc_180033D67
0x180033cf6  lea     rdx, [rsp+68h+Binding]; Binding
0x180033cfe  mov     rcx, [rsp+68h+StringBinding]; StringBinding
0x180033d03  call    cs:__imp_RpcBindingFromStringBindingW
0x180033d0a  nop     dword ptr [rax+rax+00h]
0x180033d0f  mov     ebx, eax
0x180033d11  lea     rcx, [rsp+68h+StringBinding]; String
0x180033d16  call    cs:__imp_RpcStringFreeW
0x180033d1d  nop     dword ptr [rax+rax+00h]
0x180033d22  mov     rcx, [rsp+68h+Binding]; Binding
0x180033d2a  call    ?SetMyRpcSecurity@@YAJPEAX@Z; SetMyRpcSecurity(void *)
0x180033d2f  test    ebx, ebx
0x180033d31  jnz     short loc_180033D67
0x180033d33  mov     r8d, edi
0x180033d36  mov     edx, esi
0x180033d38  mov     rcx, [rsp+68h+Binding]
0x180033d40  call    c_W32TimeSync
0x180033d45  mov     ebx, eax
0x180033d47  mov     [rsp+68h+var_38], eax
0x180033d4b  jmp     short loc_180033D53
0x180033d4d  mov     ebx, eax
0x180033d4f  mov     [rsp+68h+var_38], eax
0x180033d53  lea     rcx, [rsp+68h+Binding]; Binding
0x180033d5b  call    cs:__imp_RpcBindingFree
0x180033d62  nop     dword ptr [rax+rax+00h]
0x180033d67  mov     eax, ebx
0x180033d69  add     rsp, 48h
0x180033d6d  pop     r14
0x180033d6f  pop     rdi
0x180033d70  pop     rsi
0x180033d71  pop     rbx
0x180033d72  retn
```
