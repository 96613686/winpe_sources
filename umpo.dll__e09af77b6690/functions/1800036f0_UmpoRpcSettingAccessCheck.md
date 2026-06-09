# UmpoRpcSettingAccessCheck

- ea: `0x1800036f0`
- end: `0x1800037a2`
- name: `UmpoRpcSettingAccessCheck`
- size: `178`
- prototype: `DWORD __fastcall(__int64, unsigned int, __int64, unsigned int)`
- caller_count: `20`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002530`
- `0x180002e90`
- `0x180003070`
- `0x180003640`
- `0x180007650`
- `0x18000c780`
- `0x18000d7c0`
- `0x18000d880`
- `0x18000d940`
- `0x18000e640`
- `0x18000e950`
- `0x18000ebf0`
- `0x1800147b0`
- `0x180014810`
- `0x180014950`
- `0x180014a00`
- `0x180014ad0`
- `0x180014d60`
- `0x180014dd0`
- `0x180014e50`

## callees

- `0x1800036f0`
- `0x1800037b0`
- `0x18000f3dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000379a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000379a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000375c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000375c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003743`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003743`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003730`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003730`
- `RPCRT4!RpcRevertToSelf` at `0x180003765`
- `RPCRT4!RpcRevertToSelf` at `0x180003765`
- `RPCRT4!RpcImpersonateClient` at `0x180003719`
- `RPCRT4!RpcImpersonateClient` at `0x180003719`

## pseudocode

```c
DWORD __fastcall UmpoRpcSettingAccessCheck(__int64 a1, unsigned int a2, __int64 a3, unsigned int a4)
{
  RPC_STATUS v7; // ebx
  HANDLE CurrentThread; // rax
  BOOL v10; // r14d
  HANDLE hObject; // [rsp+20h] [rbp-38h] BYREF

  hObject = (HANDLE)-1LL;
  if ( UmpoPowerPolicyInitialized )
  {
    v7 = RpcImpersonateClient(0);
    if ( !v7 )
    {
      CurrentThread = GetCurrentThread();
      v10 = OpenThreadToken(CurrentThread, 8u, 1, &hObject);
      v7 = RpcRevertToSelf();
      if ( v7 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      else
      {
        if ( !v10 )
          return GetLastError();
        v7 = UmpoInternalAccessCheck(a2, a3, hObject, a4);
      }
    }
  }
  else
  {
    v7 = 21;
  }
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  return v7;
}

```

## disassembly

```asm
0x1800036f0  push    rbx
0x1800036f2  push    rbp
0x1800036f3  push    rsi
0x1800036f4  push    rdi
0x1800036f5  push    r14
0x1800036f7  sub     rsp, 30h
0x1800036fb  movzx   eax, cs:UmpoPowerPolicyInitialized
0x180003702  mov     edi, r9d
0x180003705  mov     [rsp+58h+hObject], 0FFFFFFFFFFFFFFFFh
0x18000370e  mov     rsi, r8
0x180003711  mov     ebp, edx
0x180003713  test    al, al
0x180003715  jz      short loc_180003793
0x180003717  xor     ecx, ecx; BindingHandle
0x180003719  call    cs:__imp_RpcImpersonateClient
0x18000371f  mov     ebx, eax
0x180003721  test    eax, eax
0x180003723  jz      short loc_180003743
0x180003725  mov     rcx, [rsp+58h+hObject]; hObject
0x18000372a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000372e  jz      short loc_180003736
0x180003730  call    cs:__imp_CloseHandle
0x180003736  mov     eax, ebx
0x180003738  add     rsp, 30h
0x18000373c  pop     r14
0x18000373e  pop     rdi
0x18000373f  pop     rsi
0x180003740  pop     rbp
0x180003741  pop     rbx
0x180003742  retn
0x180003743  call    cs:__imp_GetCurrentThread
0x180003749  lea     r9, [rsp+58h+hObject]; TokenHandle
0x18000374e  mov     edx, 8; DesiredAccess
0x180003753  mov     rcx, rax; ThreadHandle
0x180003756  mov     r8d, 1; OpenAsSelf
0x18000375c  call    cs:__imp_OpenThreadToken
0x180003762  mov     r14d, eax
0x180003765  call    cs:__imp_RpcRevertToSelf
0x18000376b  mov     ebx, eax
0x18000376d  test    eax, eax
0x18000376f  jnz     short loc_18000378C
0x180003771  test    r14d, r14d
0x180003774  jz      short loc_18000379A
0x180003776  mov     r8, [rsp+58h+hObject]
0x18000377b  mov     r9d, edi
0x18000377e  mov     rdx, rsi
0x180003781  mov     ecx, ebp
0x180003783  call    UmpoInternalAccessCheck
0x180003788  mov     ebx, eax
0x18000378a  jmp     short loc_180003725
0x18000378c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180003791  jmp     short loc_180003725
0x180003793  mov     ebx, 15h
0x180003798  jmp     short loc_180003725
0x18000379a  call    cs:__imp_GetLastError
0x1800037a0  jmp     short loc_180003738
```
