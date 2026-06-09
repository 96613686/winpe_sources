# W32TimeGetNetlogonServiceBits

- ea: `0x1800503e0`
- end: `0x18005055e`
- name: `W32TimeGetNetlogonServiceBits`
- size: `382`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180029ad0`
- `0x1800503e0`
- `0x180050d10`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x18005046a`
- `RPCRT4!RpcStringFreeW` at `0x180050518`
- `RPCRT4!RpcStringFreeW` at `0x18005046a`
- `RPCRT4!RpcStringFreeW` at `0x180050518`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180050457`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180050505`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180050457`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180050505`
- `RPCRT4!RpcStringBindingComposeW` at `0x18005043b`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800504e9`
- `RPCRT4!RpcStringBindingComposeW` at `0x18005043b`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800504e9`
- `RPCRT4!RpcBindingFree` at `0x1800504a3`
- `RPCRT4!RpcBindingFree` at `0x180050547`
- `RPCRT4!RpcBindingFree` at `0x1800504a3`
- `RPCRT4!RpcBindingFree` at `0x180050547`

## pseudocode

```c
__int64 __fastcall W32TimeGetNetlogonServiceBits(RPC_WSTR NetworkAddr, _DWORD *a2)
{
  unsigned int v5; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp+18h] BYREF
  RPC_WSTR String; // [rsp+68h] [rbp+20h] BYREF

  String = 0;
  Binding = 0;
  if ( !a2 )
    return 87;
  v5 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", NetworkAddr, (RPC_WSTR)L"\\PIPE\\W32TIME", 0, &String);
  if ( !v5 )
  {
    v5 = RpcBindingFromStringBindingW(String, &Binding);
    RpcStringFreeW(&String);
    SetMyRpcSecurity(Binding);
    if ( !v5 )
    {
      *a2 = c_W32TimeGetNetlogonServiceBits(Binding);
      RpcBindingFree(&Binding);
    }
  }
  if ( v5 == 1717 || v5 == 1722 )
  {
    v5 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", NetworkAddr, (RPC_WSTR)L"\\PIPE\\W32TIME_ALT", 0, &String);
    if ( !v5 )
    {
      v5 = RpcBindingFromStringBindingW(String, &Binding);
      RpcStringFreeW(&String);
      SetMyRpcSecurity(Binding);
      if ( !v5 )
      {
        *a2 = c_W32TimeGetNetlogonServiceBits(Binding);
        RpcBindingFree(&Binding);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800503e0  mov     rax, rsp
0x1800503e3  mov     [rax+10h], rdx
0x1800503e7  mov     [rax+8], rcx
0x1800503eb  push    rbx
0x1800503ec  push    rsi
0x1800503ed  push    rdi
0x1800503ee  sub     rsp, 30h
0x1800503f2  mov     rdi, rdx
0x1800503f5  mov     rsi, rcx
0x1800503f8  mov     qword ptr [rax+20h], 0
0x180050400  mov     qword ptr [rax+18h], 0
0x180050408  test    rdx, rdx
0x18005040b  jnz     short loc_180050415
0x18005040d  lea     eax, [rdx+57h]
0x180050410  jmp     loc_180050555
0x180050415  lea     rax, [rsp+48h+String]
0x18005041a  mov     [rsp+48h+StringBinding], rax; StringBinding
0x18005041f  mov     [rsp+48h+Options], 0; Options
0x180050428  lea     r9, Endpoint; "\\PIPE\\W32TIME"
0x18005042f  mov     r8, rcx; NetworkAddr
0x180050432  lea     rdx, ProtSeq; "ncacn_np"
0x180050439  xor     ecx, ecx; ObjUuid
0x18005043b  call    cs:__imp_RpcStringBindingComposeW
0x180050442  nop     dword ptr [rax+rax+00h]
0x180050447  mov     ebx, eax
0x180050449  test    eax, eax
0x18005044b  jnz     short loc_1800504AF
0x18005044d  lea     rdx, [rsp+48h+Binding]; Binding
0x180050452  mov     rcx, [rsp+48h+String]; StringBinding
0x180050457  call    cs:__imp_RpcBindingFromStringBindingW
0x18005045e  nop     dword ptr [rax+rax+00h]
0x180050463  mov     ebx, eax
0x180050465  lea     rcx, [rsp+48h+String]; String
0x18005046a  call    cs:__imp_RpcStringFreeW
0x180050471  nop     dword ptr [rax+rax+00h]
0x180050476  mov     rcx, [rsp+48h+Binding]; Binding
0x18005047b  call    ?SetMyRpcSecurity@@YAJPEAX@Z; SetMyRpcSecurity(void *)
0x180050480  test    ebx, ebx
0x180050482  jnz     short loc_1800504AF
0x180050484  mov     rcx, [rsp+48h+Binding]
0x180050489  call    c_W32TimeGetNetlogonServiceBits
0x18005048e  mov     [rdi], eax
0x180050490  jmp     short loc_18005049E
0x180050492  mov     ebx, eax
0x180050494  mov     rdi, [rsp+48h+arg_8]
0x180050499  mov     rsi, [rsp+48h+arg_0]
0x18005049e  lea     rcx, [rsp+48h+Binding]; Binding
0x1800504a3  call    cs:__imp_RpcBindingFree
0x1800504aa  nop     dword ptr [rax+rax+00h]
0x1800504af  cmp     ebx, 6B5h
0x1800504b5  jz      short loc_1800504C3
0x1800504b7  cmp     ebx, 6BAh
0x1800504bd  jnz     loc_180050553
0x1800504c3  lea     rax, [rsp+48h+String]
0x1800504c8  mov     [rsp+48h+StringBinding], rax; StringBinding
0x1800504cd  mov     [rsp+48h+Options], 0; Options
0x1800504d6  lea     r9, aPipeW32timeAlt; "\\PIPE\\W32TIME_ALT"
0x1800504dd  mov     r8, rsi; NetworkAddr
0x1800504e0  lea     rdx, ProtSeq; "ncacn_np"
0x1800504e7  xor     ecx, ecx; ObjUuid
0x1800504e9  call    cs:__imp_RpcStringBindingComposeW
0x1800504f0  nop     dword ptr [rax+rax+00h]
0x1800504f5  mov     ebx, eax
0x1800504f7  test    eax, eax
0x1800504f9  jnz     short loc_180050553
0x1800504fb  lea     rdx, [rsp+48h+Binding]; Binding
0x180050500  mov     rcx, [rsp+48h+String]; StringBinding
0x180050505  call    cs:__imp_RpcBindingFromStringBindingW
0x18005050c  nop     dword ptr [rax+rax+00h]
0x180050511  mov     ebx, eax
0x180050513  lea     rcx, [rsp+48h+String]; String
0x180050518  call    cs:__imp_RpcStringFreeW
0x18005051f  nop     dword ptr [rax+rax+00h]
0x180050524  mov     rcx, [rsp+48h+Binding]; Binding
0x180050529  call    ?SetMyRpcSecurity@@YAJPEAX@Z; SetMyRpcSecurity(void *)
0x18005052e  test    ebx, ebx
0x180050530  jnz     short loc_180050553
0x180050532  mov     rcx, [rsp+48h+Binding]
0x180050537  call    c_W32TimeGetNetlogonServiceBits
0x18005053c  mov     [rdi], eax
0x18005053e  jmp     short loc_180050542
0x180050540  mov     ebx, eax
0x180050542  lea     rcx, [rsp+48h+Binding]; Binding
0x180050547  call    cs:__imp_RpcBindingFree
0x18005054e  nop     dword ptr [rax+rax+00h]
0x180050553  mov     eax, ebx
0x180050555  add     rsp, 30h
0x180050559  pop     rdi
0x18005055a  pop     rsi
0x18005055b  pop     rbx
0x18005055c  retn
```
