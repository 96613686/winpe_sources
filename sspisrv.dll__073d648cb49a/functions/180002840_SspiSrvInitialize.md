# SspiSrvInitialize

- ea: `0x180002840`
- end: `0x180002941`
- name: `SspiSrvInitialize`
- size: `257`
- prototype: `int __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000235c`
- `0x180002840`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800028ab`
- `ntdll!RtlFreeHeap` at `0x180002917`
- `ntdll!RtlFreeHeap` at `0x1800028ab`
- `ntdll!RtlFreeHeap` at `0x180002917`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180002887`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180002887`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800028f7`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800028f7`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800028b9`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800028b9`

## pseudocode

```c
int __fastcall SspiSrvInitialize(__int64 a1)
{
  int result; // eax
  void *v3; // rbx
  RPC_STATUS v4; // esi
  void *SecurityDescriptor; // [rsp+58h] [rbp+10h] BYREF

  SecurityDescriptor = 0;
  result = LsapMakeLowBoxRpcSD(&SecurityDescriptor);
  if ( result >= 0 )
  {
    v3 = SecurityDescriptor;
    v4 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, (RPC_WSTR)L"lsasspirpc", SecurityDescriptor);
    if ( v4 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
      return I_RpcMapWin32Status(v4);
    }
    v4 = RpcServerRegisterIf3(qword_180006CA0, 0, 0, 33, 1234, 0x100000, 0, v3);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
    if ( v4 )
      return I_RpcMapWin32Status(v4);
    gLsapSspiExtension = a1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002840  mov     rax, rsp
0x180002843  mov     [rax+8], rbx
0x180002847  mov     [rax+18h], rsi
0x18000284b  push    rdi
0x18000284c  sub     rsp, 40h
0x180002850  mov     rdi, rcx
0x180002853  mov     qword ptr [rax+10h], 0
0x18000285b  lea     rcx, [rax+10h]
0x18000285f  call    LsapMakeLowBoxRpcSD
0x180002864  test    eax, eax
0x180002866  js      loc_180002930
0x18000286c  mov     rbx, [rsp+48h+SecurityDescriptor]
0x180002871  lea     r8, Endpoint; "lsasspirpc"
0x180002878  mov     r9, rbx; SecurityDescriptor
0x18000287b  lea     rcx, Protseq; "ncalrpc"
0x180002882  mov     edx, 0Ah; MaxCalls
0x180002887  call    cs:__imp_RpcServerUseProtseqEpW
0x18000288e  nop     dword ptr [rax+rax+00h]
0x180002893  mov     esi, eax
0x180002895  test    eax, eax
0x180002897  jz      short loc_1800028C7
0x180002899  mov     rcx, gs:60h
0x1800028a2  mov     r8, rbx; P
0x1800028a5  xor     edx, edx; Flags
0x1800028a7  mov     rcx, [rcx+30h]; HeapHandle
0x1800028ab  call    cs:__imp_RtlFreeHeap
0x1800028b2  nop     dword ptr [rax+rax+00h]
0x1800028b7  mov     ecx, esi; Status
0x1800028b9  call    cs:__imp_I_RpcMapWin32Status
0x1800028c0  nop     dword ptr [rax+rax+00h]
0x1800028c5  jmp     short loc_180002930
0x1800028c7  mov     [rsp+48h+var_10], rbx
0x1800028cc  lea     rcx, qword_180006CA0
0x1800028d3  mov     [rsp+48h+var_18], 0
0x1800028dc  mov     r9d, 21h ; '!'
0x1800028e2  mov     [rsp+48h+var_20], 100000h
0x1800028ea  xor     r8d, r8d
0x1800028ed  xor     edx, edx
0x1800028ef  mov     [rsp+48h+var_28], 4D2h
0x1800028f7  call    cs:__imp_RpcServerRegisterIf3
0x1800028fe  nop     dword ptr [rax+rax+00h]
0x180002903  mov     rcx, gs:60h
0x18000290c  mov     r8, rbx; P
0x18000290f  xor     edx, edx; Flags
0x180002911  mov     esi, eax
0x180002913  mov     rcx, [rcx+30h]; HeapHandle
0x180002917  call    cs:__imp_RtlFreeHeap
0x18000291e  nop     dword ptr [rax+rax+00h]
0x180002923  test    esi, esi
0x180002925  jnz     short loc_1800028B7
0x180002927  mov     cs:gLsapSspiExtension, rdi
0x18000292e  xor     eax, eax
0x180002930  mov     rbx, [rsp+48h+arg_0]
0x180002935  mov     rsi, [rsp+48h+arg_10]
0x18000293a  add     rsp, 40h
0x18000293e  pop     rdi
0x18000293f  retn
```
