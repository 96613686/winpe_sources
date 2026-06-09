# W32TimeQueryNtpProviderConfiguration

- ea: `0x180050910`
- end: `0x180050b25`
- name: `W32TimeQueryNtpProviderConfiguration`
- size: `533`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180029ad0`
- `0x180050910`
- `0x180050d8c`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x1800509b9`
- `RPCRT4!RpcStringFreeW` at `0x180050a90`
- `RPCRT4!RpcStringFreeW` at `0x1800509b9`
- `RPCRT4!RpcStringFreeW` at `0x180050a90`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800509a6`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180050a7d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800509a6`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180050a7d`
- `RPCRT4!RpcStringBindingComposeW` at `0x180050986`
- `RPCRT4!RpcStringBindingComposeW` at `0x180050a61`
- `RPCRT4!RpcStringBindingComposeW` at `0x180050986`
- `RPCRT4!RpcStringBindingComposeW` at `0x180050a61`
- `RPCRT4!RpcBindingFree` at `0x180050a1b`
- `RPCRT4!RpcBindingFree` at `0x180050ada`
- `RPCRT4!RpcBindingFree` at `0x180050a1b`
- `RPCRT4!RpcBindingFree` at `0x180050ada`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050b0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050b0a`

## pseudocode

```c
__int64 __fastcall W32TimeQueryNtpProviderConfiguration(RPC_WSTR NetworkAddr, unsigned int a2, __int64 a3, HLOCAL *a4)
{
  unsigned int ProviderConfiguration; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp-40h] BYREF
  RPC_WSTR String; // [rsp+40h] [rbp-38h] BYREF
  HLOCAL hMem[6]; // [rsp+48h] [rbp-30h] BYREF

  Binding = 0;
  hMem[0] = 0;
  String = 0;
  if ( !a4 )
    return 2147942487LL;
  ProviderConfiguration = RpcStringBindingComposeW(
                            0,
                            (RPC_WSTR)L"ncacn_np",
                            NetworkAddr,
                            (RPC_WSTR)L"\\PIPE\\W32TIME",
                            0,
                            &String);
  if ( !ProviderConfiguration )
  {
    ProviderConfiguration = RpcBindingFromStringBindingW(String, &Binding);
    RpcStringFreeW(&String);
    SetMyRpcSecurity(Binding);
    if ( !ProviderConfiguration )
    {
      ProviderConfiguration = c_W32TimeQueryProviderConfiguration(Binding, a2, a3, hMem);
      RpcBindingFree(&Binding);
    }
  }
  if ( ProviderConfiguration != 1717 && ProviderConfiguration != 1722 )
    goto LABEL_11;
  ProviderConfiguration = RpcStringBindingComposeW(
                            0,
                            (RPC_WSTR)L"ncacn_np",
                            NetworkAddr,
                            (RPC_WSTR)L"\\PIPE\\W32TIME_ALT",
                            0,
                            &String);
  if ( ProviderConfiguration )
    goto LABEL_11;
  ProviderConfiguration = RpcBindingFromStringBindingW(String, &Binding);
  RpcStringFreeW(&String);
  SetMyRpcSecurity(Binding);
  if ( !ProviderConfiguration )
  {
    ProviderConfiguration = c_W32TimeQueryProviderConfiguration(Binding, a2, a3, hMem);
    RpcBindingFree(&Binding);
LABEL_11:
    if ( !ProviderConfiguration && hMem[0] )
    {
      *a4 = hMem[0];
      hMem[0] = 0;
    }
  }
  if ( hMem[0] )
    LocalFree(hMem[0]);
  return ProviderConfiguration;
}

```

## disassembly

```asm
0x180050910  mov     rax, rsp
0x180050913  mov     [rax+20h], r9
0x180050917  mov     [rax+18h], r8
0x18005091b  mov     [rax+10h], edx
0x18005091e  mov     [rax+8], rcx
0x180050922  push    rbx
0x180050923  push    rsi
0x180050924  push    rdi
0x180050925  push    r14
0x180050927  push    r15
0x180050929  sub     rsp, 50h
0x18005092d  mov     rdi, r9
0x180050930  mov     r14, r8
0x180050933  mov     r15d, edx
0x180050936  mov     rsi, rcx
0x180050939  mov     qword ptr [rax-40h], 0
0x180050941  mov     qword ptr [rax-30h], 0
0x180050949  mov     qword ptr [rax-38h], 0
0x180050951  test    r9, r9
0x180050954  jnz     short loc_180050960
0x180050956  mov     eax, 80070057h
0x18005095b  jmp     loc_180050B18
0x180050960  lea     rax, [rsp+78h+String]
0x180050965  mov     [rsp+78h+StringBinding], rax; StringBinding
0x18005096a  mov     [rsp+78h+Options], 0; Options
0x180050973  lea     r9, Endpoint; "\\PIPE\\W32TIME"
0x18005097a  mov     r8, rcx; NetworkAddr
0x18005097d  lea     rdx, ProtSeq; "ncacn_np"
0x180050984  xor     ecx, ecx; ObjUuid
0x180050986  call    cs:__imp_RpcStringBindingComposeW
0x18005098d  nop     dword ptr [rax+rax+00h]
0x180050992  mov     ebx, eax
0x180050994  test    eax, eax
0x180050996  jnz     loc_180050A27
0x18005099c  lea     rdx, [rsp+78h+Binding]; Binding
0x1800509a1  mov     rcx, [rsp+78h+String]; StringBinding
0x1800509a6  call    cs:__imp_RpcBindingFromStringBindingW
0x1800509ad  nop     dword ptr [rax+rax+00h]
0x1800509b2  mov     ebx, eax
0x1800509b4  lea     rcx, [rsp+78h+String]; String
0x1800509b9  call    cs:__imp_RpcStringFreeW
0x1800509c0  nop     dword ptr [rax+rax+00h]
0x1800509c5  mov     rcx, [rsp+78h+Binding]; Binding
0x1800509ca  call    ?SetMyRpcSecurity@@YAJPEAX@Z; SetMyRpcSecurity(void *)
0x1800509cf  test    ebx, ebx
0x1800509d1  jnz     short loc_180050A27
0x1800509d3  lea     r9, [rsp+78h+hMem]
0x1800509d8  mov     r8, r14
0x1800509db  mov     edx, r15d
0x1800509de  mov     rcx, [rsp+78h+Binding]
0x1800509e3  call    c_W32TimeQueryProviderConfiguration
0x1800509e8  mov     ebx, eax
0x1800509ea  mov     [rsp+78h+var_48], eax
0x1800509ee  jmp     short loc_180050A16
0x1800509f0  mov     ebx, eax
0x1800509f2  mov     [rsp+78h+var_48], eax
0x1800509f6  mov     rdi, [rsp+78h+arg_18]
0x1800509fe  mov     r14, [rsp+78h+arg_10]
0x180050a06  mov     r15d, [rsp+78h+arg_8]
0x180050a0e  mov     rsi, [rsp+78h+arg_0]
0x180050a16  lea     rcx, [rsp+78h+Binding]; Binding
0x180050a1b  call    cs:__imp_RpcBindingFree
0x180050a22  nop     dword ptr [rax+rax+00h]
0x180050a27  cmp     ebx, 6B5h
0x180050a2d  jz      short loc_180050A3B
0x180050a2f  cmp     ebx, 6BAh
0x180050a35  jnz     loc_180050AE6
0x180050a3b  lea     rax, [rsp+78h+String]
0x180050a40  mov     [rsp+78h+StringBinding], rax; StringBinding
0x180050a45  mov     [rsp+78h+Options], 0; Options
0x180050a4e  lea     r9, aPipeW32timeAlt; "\\PIPE\\W32TIME_ALT"
0x180050a55  mov     r8, rsi; NetworkAddr
0x180050a58  lea     rdx, ProtSeq; "ncacn_np"
0x180050a5f  xor     ecx, ecx; ObjUuid
0x180050a61  call    cs:__imp_RpcStringBindingComposeW
0x180050a68  nop     dword ptr [rax+rax+00h]
0x180050a6d  mov     ebx, eax
0x180050a6f  test    eax, eax
0x180050a71  jnz     short loc_180050AE6
0x180050a73  lea     rdx, [rsp+78h+Binding]; Binding
0x180050a78  mov     rcx, [rsp+78h+String]; StringBinding
0x180050a7d  call    cs:__imp_RpcBindingFromStringBindingW
0x180050a84  nop     dword ptr [rax+rax+00h]
0x180050a89  mov     ebx, eax
0x180050a8b  lea     rcx, [rsp+78h+String]; String
0x180050a90  call    cs:__imp_RpcStringFreeW
0x180050a97  nop     dword ptr [rax+rax+00h]
0x180050a9c  mov     rcx, [rsp+78h+Binding]; Binding
0x180050aa1  call    ?SetMyRpcSecurity@@YAJPEAX@Z; SetMyRpcSecurity(void *)
0x180050aa6  test    ebx, ebx
0x180050aa8  jnz     short loc_180050B00
0x180050aaa  lea     r9, [rsp+78h+hMem]
0x180050aaf  mov     r8, r14
0x180050ab2  mov     edx, r15d
0x180050ab5  mov     rcx, [rsp+78h+Binding]
0x180050aba  call    c_W32TimeQueryProviderConfiguration
0x180050abf  mov     ebx, eax
0x180050ac1  mov     [rsp+78h+var_48], eax
0x180050ac5  jmp     short loc_180050AD5
0x180050ac7  mov     ebx, eax
0x180050ac9  mov     [rsp+78h+var_48], eax
0x180050acd  mov     rdi, [rsp+78h+arg_18]
0x180050ad5  lea     rcx, [rsp+78h+Binding]; Binding
0x180050ada  call    cs:__imp_RpcBindingFree
0x180050ae1  nop     dword ptr [rax+rax+00h]
0x180050ae6  test    ebx, ebx
0x180050ae8  jnz     short loc_180050B00
0x180050aea  mov     rcx, [rsp+78h+hMem]
0x180050aef  test    rcx, rcx
0x180050af2  jz      short loc_180050B00
0x180050af4  mov     [rdi], rcx
0x180050af7  mov     [rsp+78h+hMem], 0
0x180050b00  mov     rcx, [rsp+78h+hMem]; hMem
0x180050b05  test    rcx, rcx
0x180050b08  jz      short loc_180050B16
0x180050b0a  call    cs:__imp_LocalFree
0x180050b11  nop     dword ptr [rax+rax+00h]
0x180050b16  mov     eax, ebx
0x180050b18  add     rsp, 50h
0x180050b1c  pop     r15
0x180050b1e  pop     r14
0x180050b20  pop     rdi
0x180050b21  pop     rsi
0x180050b22  pop     rbx
0x180050b23  retn
```
