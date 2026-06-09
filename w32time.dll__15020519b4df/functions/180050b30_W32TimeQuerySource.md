# W32TimeQuerySource

- ea: `0x180050b30`
- end: `0x180050d07`
- name: `W32TimeQuerySource`
- size: `471`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180029ad0`
- `0x180050b30`
- `0x180050e04`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180050bc4`
- `RPCRT4!RpcStringFreeW` at `0x180050c7f`
- `RPCRT4!RpcStringFreeW` at `0x180050bc4`
- `RPCRT4!RpcStringFreeW` at `0x180050c7f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180050bb1`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180050c6c`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180050bb1`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180050c6c`
- `RPCRT4!RpcStringBindingComposeW` at `0x180050b95`
- `RPCRT4!RpcStringBindingComposeW` at `0x180050c50`
- `RPCRT4!RpcStringBindingComposeW` at `0x180050b95`
- `RPCRT4!RpcStringBindingComposeW` at `0x180050c50`
- `RPCRT4!RpcBindingFree` at `0x180050c0a`
- `RPCRT4!RpcBindingFree` at `0x180050cc0`
- `RPCRT4!RpcBindingFree` at `0x180050c0a`
- `RPCRT4!RpcBindingFree` at `0x180050cc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050cf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050cf0`

## pseudocode

```c
__int64 __fastcall W32TimeQuerySource(RPC_WSTR NetworkAddr, HLOCAL *a2)
{
  unsigned int Source; // ebx
  HLOCAL hMem[4]; // [rsp+38h] [rbp-20h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+70h] [rbp+18h] BYREF
  RPC_WSTR String; // [rsp+78h] [rbp+20h] BYREF

  Binding = 0;
  hMem[0] = 0;
  String = 0;
  if ( !a2 )
    return 2147942487LL;
  Source = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", NetworkAddr, (RPC_WSTR)L"\\PIPE\\W32TIME", 0, &String);
  if ( !Source )
  {
    Source = RpcBindingFromStringBindingW(String, &Binding);
    RpcStringFreeW(&String);
    SetMyRpcSecurity(Binding);
    if ( !Source )
    {
      Source = c_W32TimeQuerySource(Binding, hMem);
      RpcBindingFree(&Binding);
    }
  }
  if ( Source != 1717 && Source != 1722 )
    goto LABEL_11;
  Source = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", NetworkAddr, (RPC_WSTR)L"\\PIPE\\W32TIME_ALT", 0, &String);
  if ( Source )
    goto LABEL_11;
  Source = RpcBindingFromStringBindingW(String, &Binding);
  RpcStringFreeW(&String);
  SetMyRpcSecurity(Binding);
  if ( !Source )
  {
    Source = c_W32TimeQuerySource(Binding, hMem);
    RpcBindingFree(&Binding);
LABEL_11:
    if ( !Source && hMem[0] )
    {
      *a2 = hMem[0];
      hMem[0] = 0;
    }
  }
  if ( hMem[0] )
    LocalFree(hMem[0]);
  return Source;
}

```

## disassembly

```asm
0x180050b30  mov     rax, rsp
0x180050b33  mov     [rax+10h], rdx
0x180050b37  mov     [rax+8], rcx
0x180050b3b  push    rbx
0x180050b3c  push    rsi
0x180050b3d  push    rdi
0x180050b3e  sub     rsp, 40h
0x180050b42  mov     rdi, rdx
0x180050b45  mov     rsi, rcx
0x180050b48  mov     qword ptr [rax+18h], 0
0x180050b50  mov     qword ptr [rax-20h], 0
0x180050b58  mov     qword ptr [rax+20h], 0
0x180050b60  test    rdx, rdx
0x180050b63  jnz     short loc_180050B6F
0x180050b65  mov     eax, 80070057h
0x180050b6a  jmp     loc_180050CFE
0x180050b6f  lea     rax, [rsp+58h+String]
0x180050b74  mov     [rsp+58h+StringBinding], rax; StringBinding
0x180050b79  mov     [rsp+58h+Options], 0; Options
0x180050b82  lea     r9, Endpoint; "\\PIPE\\W32TIME"
0x180050b89  mov     r8, rcx; NetworkAddr
0x180050b8c  lea     rdx, ProtSeq; "ncacn_np"
0x180050b93  xor     ecx, ecx; ObjUuid
0x180050b95  call    cs:__imp_RpcStringBindingComposeW
0x180050b9c  nop     dword ptr [rax+rax+00h]
0x180050ba1  mov     ebx, eax
0x180050ba3  test    eax, eax
0x180050ba5  jnz     short loc_180050C16
0x180050ba7  lea     rdx, [rsp+58h+Binding]; Binding
0x180050bac  mov     rcx, [rsp+58h+String]; StringBinding
0x180050bb1  call    cs:__imp_RpcBindingFromStringBindingW
0x180050bb8  nop     dword ptr [rax+rax+00h]
0x180050bbd  mov     ebx, eax
0x180050bbf  lea     rcx, [rsp+58h+String]; String
0x180050bc4  call    cs:__imp_RpcStringFreeW
0x180050bcb  nop     dword ptr [rax+rax+00h]
0x180050bd0  mov     rcx, [rsp+58h+Binding]; Binding
0x180050bd5  call    ?SetMyRpcSecurity@@YAJPEAX@Z; SetMyRpcSecurity(void *)
0x180050bda  test    ebx, ebx
0x180050bdc  jnz     short loc_180050C16
0x180050bde  lea     rdx, [rsp+58h+hMem]
0x180050be3  mov     rcx, [rsp+58h+Binding]
0x180050be8  call    c_W32TimeQuerySource
0x180050bed  mov     ebx, eax
0x180050bef  mov     [rsp+58h+var_28], eax
0x180050bf3  jmp     short loc_180050C05
0x180050bf5  mov     ebx, eax
0x180050bf7  mov     [rsp+58h+var_28], eax
0x180050bfb  mov     rdi, [rsp+58h+arg_8]
0x180050c00  mov     rsi, [rsp+58h+arg_0]
0x180050c05  lea     rcx, [rsp+58h+Binding]; Binding
0x180050c0a  call    cs:__imp_RpcBindingFree
0x180050c11  nop     dword ptr [rax+rax+00h]
0x180050c16  cmp     ebx, 6B5h
0x180050c1c  jz      short loc_180050C2A
0x180050c1e  cmp     ebx, 6BAh
0x180050c24  jnz     loc_180050CCC
0x180050c2a  lea     rax, [rsp+58h+String]
0x180050c2f  mov     [rsp+58h+StringBinding], rax; StringBinding
0x180050c34  mov     [rsp+58h+Options], 0; Options
0x180050c3d  lea     r9, aPipeW32timeAlt; "\\PIPE\\W32TIME_ALT"
0x180050c44  mov     r8, rsi; NetworkAddr
0x180050c47  lea     rdx, ProtSeq; "ncacn_np"
0x180050c4e  xor     ecx, ecx; ObjUuid
0x180050c50  call    cs:__imp_RpcStringBindingComposeW
0x180050c57  nop     dword ptr [rax+rax+00h]
0x180050c5c  mov     ebx, eax
0x180050c5e  test    eax, eax
0x180050c60  jnz     short loc_180050CCC
0x180050c62  lea     rdx, [rsp+58h+Binding]; Binding
0x180050c67  mov     rcx, [rsp+58h+String]; StringBinding
0x180050c6c  call    cs:__imp_RpcBindingFromStringBindingW
0x180050c73  nop     dword ptr [rax+rax+00h]
0x180050c78  mov     ebx, eax
0x180050c7a  lea     rcx, [rsp+58h+String]; String
0x180050c7f  call    cs:__imp_RpcStringFreeW
0x180050c86  nop     dword ptr [rax+rax+00h]
0x180050c8b  mov     rcx, [rsp+58h+Binding]; Binding
0x180050c90  call    ?SetMyRpcSecurity@@YAJPEAX@Z; SetMyRpcSecurity(void *)
0x180050c95  test    ebx, ebx
0x180050c97  jnz     short loc_180050CE6
0x180050c99  lea     rdx, [rsp+58h+hMem]
0x180050c9e  mov     rcx, [rsp+58h+Binding]
0x180050ca3  call    c_W32TimeQuerySource
0x180050ca8  mov     ebx, eax
0x180050caa  mov     [rsp+58h+var_28], eax
0x180050cae  jmp     short loc_180050CBB
0x180050cb0  mov     ebx, eax
0x180050cb2  mov     [rsp+58h+var_28], eax
0x180050cb6  mov     rdi, [rsp+58h+arg_8]
0x180050cbb  lea     rcx, [rsp+58h+Binding]; Binding
0x180050cc0  call    cs:__imp_RpcBindingFree
0x180050cc7  nop     dword ptr [rax+rax+00h]
0x180050ccc  test    ebx, ebx
0x180050cce  jnz     short loc_180050CE6
0x180050cd0  mov     rcx, [rsp+58h+hMem]
0x180050cd5  test    rcx, rcx
0x180050cd8  jz      short loc_180050CE6
0x180050cda  mov     [rdi], rcx
0x180050cdd  mov     [rsp+58h+hMem], 0
0x180050ce6  mov     rcx, [rsp+58h+hMem]; hMem
0x180050ceb  test    rcx, rcx
0x180050cee  jz      short loc_180050CFC
0x180050cf0  call    cs:__imp_LocalFree
0x180050cf7  nop     dword ptr [rax+rax+00h]
0x180050cfc  mov     eax, ebx
0x180050cfe  add     rsp, 40h
0x180050d02  pop     rdi
0x180050d03  pop     rsi
0x180050d04  pop     rbx
0x180050d05  retn
```
