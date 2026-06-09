# CUMRDPService::StartPrnDrvRpcServer(void)

- ea: `0x18000ee50`
- end: `0x18000efd5`
- name: `?StartPrnDrvRpcServer@CUMRDPService@@AEAAJXZ`
- size: `389`
- prototype: `__int64 __fastcall(CUMRDPService *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000e8f0`

## callees

- `0x18000ee50`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eef4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eef4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000efb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000efb0`
- `RPCRT4!RpcServerListen` at `0x18000ef8e`
- `RPCRT4!RpcServerListen` at `0x18000ef8e`
- `RPCRT4!RpcServerRegisterIf3` at `0x18000ef73`
- `RPCRT4!RpcServerRegisterIf3` at `0x18000ef73`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18000ef29`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18000ef29`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000eeea`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000eeea`

## pseudocode

```c
__int64 __fastcall CUMRDPService::StartPrnDrvRpcServer(CUMRDPService *this)
{
  signed int LastError; // eax
  unsigned int v2; // ebx
  bool v3; // cc
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-59h] BYREF
  WCHAR StringSecurityDescriptor[72]; // [rsp+50h] [rbp-49h] BYREF

  wcscpy(StringSecurityDescriptor, L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;R;;;AC)");
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    v2 = LastError;
LABEL_3:
    v3 = LastError <= 0;
    goto LABEL_4;
  }
  LastError = RpcServerUseProtseqEpW(
                (RPC_WSTR)L"ncalrpc",
                0x4D2u,
                (RPC_WSTR)L"TSUMRPD_PRINT_DRV_LPC_API",
                SecurityDescriptor);
  v2 = LastError;
  if ( LastError && LastError != 1740 )
    goto LABEL_3;
  LastError = RpcServerRegisterIf3(
                qword_18004B9E0,
                0,
                0,
                41,
                1234,
                0,
                CUMRDPService::staticPublicRpcSecurityCallback,
                SecurityDescriptor);
  v2 = LastError;
  v3 = LastError <= 0;
  if ( !LastError )
  {
    LastError = RpcServerListen(1u, 0x4D2u, 1u);
    v2 = LastError;
    if ( !LastError || LastError == 1713 )
    {
      v2 = 0;
      goto LABEL_12;
    }
    goto LABEL_3;
  }
LABEL_4:
  if ( !v3 )
    v2 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v2;
}

```

## disassembly

```asm
0x18000ee50  mov     [rsp-8+arg_0], rbx
0x18000ee55  push    rbp
0x18000ee56  lea     rbp, [rsp-57h]
0x18000ee5b  sub     rsp, 0F0h
0x18000ee62  mov     rax, cs:__security_cookie
0x18000ee69  xor     rax, rsp
0x18000ee6c  mov     [rbp+57h+var_10], rax
0x18000ee70  movaps  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18000ee77  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18000ee7b  movaps  xmm1, xmmword ptr cs:aDAGrgwgxWdAGrg+10h; "GWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)("...
0x18000ee82  lea     rcx, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18000ee86  movups  xmmword ptr [rbp+57h+StringSecurityDescriptor], xmm0
0x18000ee8a  xor     r9d, r9d; SecurityDescriptorSize
0x18000ee8d  mov     [rbp+57h+SecurityDescriptor], 0
0x18000ee95  movaps  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg+20h; "D)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;"...
0x18000ee9c  movups  [rbp+57h+var_80], xmm0
0x18000eea0  movaps  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg+40h; "C)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)"
0x18000eea7  lea     edx, [r9+1]; StringSDRevision
0x18000eeab  movups  [rbp+57h+var_90], xmm1
0x18000eeaf  movaps  xmm1, xmmword ptr cs:aDAGrgwgxWdAGrg+30h; "GWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;G"...
0x18000eeb6  movups  [rbp+57h+var_60], xmm0
0x18000eeba  movaps  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg+60h; ";;GA;;;OW)(A;;GR;;;AC)"
0x18000eec1  movups  [rbp+57h+var_70], xmm1
0x18000eec5  movaps  xmm1, xmmword ptr cs:aDAGrgwgxWdAGrg+50h; ";;;BA)(A;;GA;;;OW)(A;;GR;;;AC)"
0x18000eecc  movups  [rbp+57h+var_40], xmm0
0x18000eed0  movups  xmm0, xmmword ptr cs:aDAGrgwgxWdAGrg+7Eh; "R;;;AC)"
0x18000eed7  movups  [rbp+57h+var_50], xmm1
0x18000eedb  movaps  xmm1, xmmword ptr cs:aDAGrgwgxWdAGrg+70h; "W)(A;;GR;;;AC)"
0x18000eee2  movups  [rbp+57h+var_30], xmm1
0x18000eee6  movups  [rbp+57h+var_30+0Eh], xmm0
0x18000eeea  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000eef0  test    eax, eax
0x18000eef2  jnz     short loc_18000EF12
0x18000eef4  call    cs:__imp_GetLastError
0x18000eefa  mov     ebx, eax
0x18000eefc  test    eax, eax
0x18000eefe  jle     loc_18000EFA7
0x18000ef04  movzx   ebx, ax
0x18000ef07  or      ebx, 80070000h
0x18000ef0d  jmp     loc_18000EFA7
0x18000ef12  mov     r9, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18000ef16  lea     r8, Endpoint; "TSUMRPD_PRINT_DRV_LPC_API"
0x18000ef1d  mov     edx, 4D2h; MaxCalls
0x18000ef22  lea     rcx, aNcalrpc; "ncalrpc"
0x18000ef29  call    cs:__imp_RpcServerUseProtseqEpW
0x18000ef2f  mov     ebx, eax
0x18000ef31  test    eax, eax
0x18000ef33  jz      short loc_18000EF3C
0x18000ef35  cmp     eax, 6CCh
0x18000ef3a  jnz     short loc_18000EEFC
0x18000ef3c  mov     rax, [rbp+57h+SecurityDescriptor]
0x18000ef40  lea     rcx, qword_18004B9E0
0x18000ef47  mov     [rsp+0F0h+var_B8], rax
0x18000ef4c  mov     r9d, 29h ; ')'
0x18000ef52  lea     rax, ?staticPublicRpcSecurityCallback@CUMRDPService@@CAJPEAX0@Z; CUMRDPService::staticPublicRpcSecurityCallback(void *,void *)
0x18000ef59  xor     r8d, r8d
0x18000ef5c  mov     [rsp+0F0h+var_C0], rax
0x18000ef61  xor     edx, edx
0x18000ef63  mov     [rsp+0F0h+var_C8], 0
0x18000ef6b  mov     [rsp+0F0h+var_D0], 4D2h
0x18000ef73  call    cs:__imp_RpcServerRegisterIf3
0x18000ef79  mov     ebx, eax
0x18000ef7b  test    eax, eax
0x18000ef7d  jnz     loc_18000EEFE
0x18000ef83  lea     ecx, [rax+1]; MinimumCallThreads
0x18000ef86  mov     edx, 4D2h; MaxCalls
0x18000ef8b  mov     r8d, ecx; DontWait
0x18000ef8e  call    cs:__imp_RpcServerListen
0x18000ef94  mov     ebx, eax
0x18000ef96  test    eax, eax
0x18000ef98  jz      short loc_18000EFA5
0x18000ef9a  cmp     eax, 6B1h
0x18000ef9f  jnz     loc_18000EEFC
0x18000efa5  xor     ebx, ebx
0x18000efa7  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18000efab  test    rcx, rcx
0x18000efae  jz      short loc_18000EFB6
0x18000efb0  call    cs:__imp_LocalFree
0x18000efb6  mov     eax, ebx
0x18000efb8  mov     rcx, [rbp+57h+var_10]
0x18000efbc  xor     rcx, rsp; StackCookie
0x18000efbf  call    __security_check_cookie
0x18000efc4  mov     rbx, [rsp+0F0h+arg_0]
0x18000efcc  add     rsp, 0F0h
0x18000efd3  pop     rbp
0x18000efd4  retn
```
