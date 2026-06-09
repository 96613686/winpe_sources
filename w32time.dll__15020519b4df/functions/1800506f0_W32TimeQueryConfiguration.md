# W32TimeQueryConfiguration

- ea: `0x1800506f0`
- end: `0x1800508c7`
- name: `W32TimeQueryConfiguration`
- size: `471`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180029ad0`
- `0x1800506f0`
- `0x180050d58`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180050784`
- `RPCRT4!RpcStringFreeW` at `0x18005083f`
- `RPCRT4!RpcStringFreeW` at `0x180050784`
- `RPCRT4!RpcStringFreeW` at `0x18005083f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180050771`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18005082c`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180050771`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18005082c`
- `RPCRT4!RpcStringBindingComposeW` at `0x180050755`
- `RPCRT4!RpcStringBindingComposeW` at `0x180050810`
- `RPCRT4!RpcStringBindingComposeW` at `0x180050755`
- `RPCRT4!RpcStringBindingComposeW` at `0x180050810`
- `RPCRT4!RpcBindingFree` at `0x1800507ca`
- `RPCRT4!RpcBindingFree` at `0x180050880`
- `RPCRT4!RpcBindingFree` at `0x1800507ca`
- `RPCRT4!RpcBindingFree` at `0x180050880`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800508b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800508b0`

## pseudocode

```c
__int64 __fastcall W32TimeQueryConfiguration(RPC_WSTR NetworkAddr, HLOCAL *a2)
{
  unsigned int Configuration; // ebx
  HLOCAL hMem[4]; // [rsp+38h] [rbp-20h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+70h] [rbp+18h] BYREF
  RPC_WSTR String; // [rsp+78h] [rbp+20h] BYREF

  Binding = 0;
  hMem[0] = 0;
  String = 0;
  if ( !a2 )
    return 2147942487LL;
  Configuration = RpcStringBindingComposeW(
                    0,
                    (RPC_WSTR)L"ncacn_np",
                    NetworkAddr,
                    (RPC_WSTR)L"\\PIPE\\W32TIME",
                    0,
                    &String);
  if ( !Configuration )
  {
    Configuration = RpcBindingFromStringBindingW(String, &Binding);
    RpcStringFreeW(&String);
    SetMyRpcSecurity(Binding);
    if ( !Configuration )
    {
      Configuration = c_W32TimeQueryConfiguration(Binding, hMem);
      RpcBindingFree(&Binding);
    }
  }
  if ( Configuration != 1717 && Configuration != 1722 )
    goto LABEL_11;
  Configuration = RpcStringBindingComposeW(
                    0,
                    (RPC_WSTR)L"ncacn_np",
                    NetworkAddr,
                    (RPC_WSTR)L"\\PIPE\\W32TIME_ALT",
                    0,
                    &String);
  if ( Configuration )
    goto LABEL_11;
  Configuration = RpcBindingFromStringBindingW(String, &Binding);
  RpcStringFreeW(&String);
  SetMyRpcSecurity(Binding);
  if ( !Configuration )
  {
    Configuration = c_W32TimeQueryConfiguration(Binding, hMem);
    RpcBindingFree(&Binding);
LABEL_11:
    if ( !Configuration && hMem[0] )
    {
      *a2 = hMem[0];
      hMem[0] = 0;
    }
  }
  if ( hMem[0] )
    LocalFree(hMem[0]);
  return Configuration;
}

```

## disassembly

```asm
0x1800506f0  mov     rax, rsp
0x1800506f3  mov     [rax+10h], rdx
0x1800506f7  mov     [rax+8], rcx
0x1800506fb  push    rbx
0x1800506fc  push    rsi
0x1800506fd  push    rdi
0x1800506fe  sub     rsp, 40h
0x180050702  mov     rdi, rdx
0x180050705  mov     rsi, rcx
0x180050708  mov     qword ptr [rax+18h], 0
0x180050710  mov     qword ptr [rax-20h], 0
0x180050718  mov     qword ptr [rax+20h], 0
0x180050720  test    rdx, rdx
0x180050723  jnz     short loc_18005072F
0x180050725  mov     eax, 80070057h
0x18005072a  jmp     loc_1800508BE
0x18005072f  lea     rax, [rsp+58h+String]
0x180050734  mov     [rsp+58h+StringBinding], rax; StringBinding
0x180050739  mov     [rsp+58h+Options], 0; Options
0x180050742  lea     r9, Endpoint; "\\PIPE\\W32TIME"
0x180050749  mov     r8, rcx; NetworkAddr
0x18005074c  lea     rdx, ProtSeq; "ncacn_np"
0x180050753  xor     ecx, ecx; ObjUuid
0x180050755  call    cs:__imp_RpcStringBindingComposeW
0x18005075c  nop     dword ptr [rax+rax+00h]
0x180050761  mov     ebx, eax
0x180050763  test    eax, eax
0x180050765  jnz     short loc_1800507D6
0x180050767  lea     rdx, [rsp+58h+Binding]; Binding
0x18005076c  mov     rcx, [rsp+58h+String]; StringBinding
0x180050771  call    cs:__imp_RpcBindingFromStringBindingW
0x180050778  nop     dword ptr [rax+rax+00h]
0x18005077d  mov     ebx, eax
0x18005077f  lea     rcx, [rsp+58h+String]; String
0x180050784  call    cs:__imp_RpcStringFreeW
0x18005078b  nop     dword ptr [rax+rax+00h]
0x180050790  mov     rcx, [rsp+58h+Binding]; Binding
0x180050795  call    ?SetMyRpcSecurity@@YAJPEAX@Z; SetMyRpcSecurity(void *)
0x18005079a  test    ebx, ebx
0x18005079c  jnz     short loc_1800507D6
0x18005079e  lea     rdx, [rsp+58h+hMem]
0x1800507a3  mov     rcx, [rsp+58h+Binding]
0x1800507a8  call    c_W32TimeQueryConfiguration
0x1800507ad  mov     ebx, eax
0x1800507af  mov     [rsp+58h+var_28], eax
0x1800507b3  jmp     short loc_1800507C5
0x1800507b5  mov     ebx, eax
0x1800507b7  mov     [rsp+58h+var_28], eax
0x1800507bb  mov     rdi, [rsp+58h+arg_8]
0x1800507c0  mov     rsi, [rsp+58h+arg_0]
0x1800507c5  lea     rcx, [rsp+58h+Binding]; Binding
0x1800507ca  call    cs:__imp_RpcBindingFree
0x1800507d1  nop     dword ptr [rax+rax+00h]
0x1800507d6  cmp     ebx, 6B5h
0x1800507dc  jz      short loc_1800507EA
0x1800507de  cmp     ebx, 6BAh
0x1800507e4  jnz     loc_18005088C
0x1800507ea  lea     rax, [rsp+58h+String]
0x1800507ef  mov     [rsp+58h+StringBinding], rax; StringBinding
0x1800507f4  mov     [rsp+58h+Options], 0; Options
0x1800507fd  lea     r9, aPipeW32timeAlt; "\\PIPE\\W32TIME_ALT"
0x180050804  mov     r8, rsi; NetworkAddr
0x180050807  lea     rdx, ProtSeq; "ncacn_np"
0x18005080e  xor     ecx, ecx; ObjUuid
0x180050810  call    cs:__imp_RpcStringBindingComposeW
0x180050817  nop     dword ptr [rax+rax+00h]
0x18005081c  mov     ebx, eax
0x18005081e  test    eax, eax
0x180050820  jnz     short loc_18005088C
0x180050822  lea     rdx, [rsp+58h+Binding]; Binding
0x180050827  mov     rcx, [rsp+58h+String]; StringBinding
0x18005082c  call    cs:__imp_RpcBindingFromStringBindingW
0x180050833  nop     dword ptr [rax+rax+00h]
0x180050838  mov     ebx, eax
0x18005083a  lea     rcx, [rsp+58h+String]; String
0x18005083f  call    cs:__imp_RpcStringFreeW
0x180050846  nop     dword ptr [rax+rax+00h]
0x18005084b  mov     rcx, [rsp+58h+Binding]; Binding
0x180050850  call    ?SetMyRpcSecurity@@YAJPEAX@Z; SetMyRpcSecurity(void *)
0x180050855  test    ebx, ebx
0x180050857  jnz     short loc_1800508A6
0x180050859  lea     rdx, [rsp+58h+hMem]
0x18005085e  mov     rcx, [rsp+58h+Binding]
0x180050863  call    c_W32TimeQueryConfiguration
0x180050868  mov     ebx, eax
0x18005086a  mov     [rsp+58h+var_28], eax
0x18005086e  jmp     short loc_18005087B
0x180050870  mov     ebx, eax
0x180050872  mov     [rsp+58h+var_28], eax
0x180050876  mov     rdi, [rsp+58h+arg_8]
0x18005087b  lea     rcx, [rsp+58h+Binding]; Binding
0x180050880  call    cs:__imp_RpcBindingFree
0x180050887  nop     dword ptr [rax+rax+00h]
0x18005088c  test    ebx, ebx
0x18005088e  jnz     short loc_1800508A6
0x180050890  mov     rcx, [rsp+58h+hMem]
0x180050895  test    rcx, rcx
0x180050898  jz      short loc_1800508A6
0x18005089a  mov     [rdi], rcx
0x18005089d  mov     [rsp+58h+hMem], 0
0x1800508a6  mov     rcx, [rsp+58h+hMem]; hMem
0x1800508ab  test    rcx, rcx
0x1800508ae  jz      short loc_1800508BC
0x1800508b0  call    cs:__imp_LocalFree
0x1800508b7  nop     dword ptr [rax+rax+00h]
0x1800508bc  mov     eax, ebx
0x1800508be  add     rsp, 40h
0x1800508c2  pop     rdi
0x1800508c3  pop     rsi
0x1800508c4  pop     rbx
0x1800508c5  retn
```
