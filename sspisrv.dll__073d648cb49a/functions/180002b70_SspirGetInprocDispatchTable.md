# SspirGetInprocDispatchTable

- ea: `0x180002b70`
- end: `0x180002c33`
- name: `SspirGetInprocDispatchTable`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x180002b70`
- `0x1800032c4`
- `0x1800033f0`

## import_xrefs

- `RPCRT4!RpcServerInqCallAttributesW` at `0x180002bca`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180002bca`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002bdc`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002bdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002bee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002bee`

## pseudocode

```c
int __fastcall SspirGetInprocDispatchTable(__int64 a1, _QWORD *a2)
{
  RPC_STATUS v4; // eax
  int v5; // ebx
  _DWORD RpcCallAttributes[2]; // [rsp+20h] [rbp-88h] BYREF
  _BYTE v7[56]; // [rsp+28h] [rbp-80h] BYREF
  int v8; // [rsp+60h] [rbp-48h]

  if ( !gLsapSspiExtension )
    return -1073741637;
  memset_0(v7, 0, 0x68u);
  RpcCallAttributes[0] = 2;
  RpcCallAttributes[1] = 16;
  v4 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  if ( v4 )
    return I_RpcMapWin32Status(v4);
  v5 = v8;
  if ( v5 != GetCurrentProcessId() )
    return -1073741790;
  *a2 = &SspiInprocFunctions;
  return 0;
}

```

## disassembly

```asm
0x180002b70  mov     [rsp+arg_0], rbx
0x180002b75  push    rdi
0x180002b76  sub     rsp, 0A0h
0x180002b7d  mov     rax, cs:__security_cookie
0x180002b84  xor     rax, rsp
0x180002b87  mov     [rsp+0A8h+var_18], rax
0x180002b8f  cmp     cs:gLsapSspiExtension, 0
0x180002b97  mov     rdi, rdx
0x180002b9a  jnz     short loc_180002BA3
0x180002b9c  mov     eax, 0C00000BBh
0x180002ba1  jmp     short loc_180002C11
0x180002ba3  xor     edx, edx; Val
0x180002ba5  lea     rcx, [rsp+0A8h+var_80]; void *
0x180002baa  lea     r8d, [rdx+68h]; Size
0x180002bae  call    memset_0
0x180002bb3  lea     rdx, [rsp+0A8h+RpcCallAttributes]; RpcCallAttributes
0x180002bb8  mov     [rsp+0A8h+RpcCallAttributes], 2
0x180002bc0  xor     ecx, ecx; ClientBinding
0x180002bc2  mov     [rsp+0A8h+var_84], 10h
0x180002bca  call    cs:__imp_RpcServerInqCallAttributesW
0x180002bd1  nop     dword ptr [rax+rax+00h]
0x180002bd6  test    eax, eax
0x180002bd8  jz      short loc_180002BEA
0x180002bda  mov     ecx, eax; Status
0x180002bdc  call    cs:__imp_I_RpcMapWin32Status
0x180002be3  nop     dword ptr [rax+rax+00h]
0x180002be8  jmp     short loc_180002C11
0x180002bea  mov     ebx, [rsp+0A8h+var_48]
0x180002bee  call    cs:__imp_GetCurrentProcessId
0x180002bf5  nop     dword ptr [rax+rax+00h]
0x180002bfa  cmp     ebx, eax
0x180002bfc  jz      short loc_180002C05
0x180002bfe  mov     eax, 0C0000022h
0x180002c03  jmp     short loc_180002C11
0x180002c05  lea     rax, SspiInprocFunctions
0x180002c0c  mov     [rdi], rax
0x180002c0f  xor     eax, eax
0x180002c11  mov     rcx, [rsp+0A8h+var_18]
0x180002c19  xor     rcx, rsp; StackCookie
0x180002c1c  call    __security_check_cookie
0x180002c21  mov     rbx, [rsp+0A8h+arg_0]
0x180002c29  add     rsp, 0A0h
0x180002c30  pop     rdi
0x180002c31  retn
```
