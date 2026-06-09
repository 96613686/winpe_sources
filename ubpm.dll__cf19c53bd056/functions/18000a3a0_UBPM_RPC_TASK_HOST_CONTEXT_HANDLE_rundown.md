# UBPM_RPC_TASK_HOST_CONTEXT_HANDLE_rundown

- ea: `0x18000a3a0`
- end: `0x18000a40b`
- name: `UBPM_RPC_TASK_HOST_CONTEXT_HANDLE_rundown`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009f50`
- `0x18000a3a0`
- `0x180035c10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a3ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a3ad`

## pseudocode

```c
PVOID *__fastcall UBPM_RPC_TASK_HOST_CONTEXT_HANDLE_rundown(__int64 a1)
{
  DWORD CurrentThreadId; // eax
  PVOID *result; // rax
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = a1;
  CurrentThreadId = GetCurrentThreadId();
  if ( CurrentThreadId != _InterlockedCompareExchange(
                            (volatile signed __int32 *)(a1 + 324),
                            CurrentThreadId,
                            CurrentThreadId) )
    return (PVOID *)s_UbpmRpcCloseTaskHostChannel(&v4);
  ++*(_DWORD *)(a1 + 328);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    return (PVOID *)WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids);
  return result;
}

```

## disassembly

```asm
0x18000a3a0  mov     [rsp+arg_0], rcx
0x18000a3a5  push    rbx
0x18000a3a6  sub     rsp, 20h
0x18000a3aa  mov     rbx, rcx
0x18000a3ad  call    cs:__imp_GetCurrentThreadId
0x18000a3b3  mov     ecx, eax
0x18000a3b5  lock cmpxchg [rbx+144h], ecx
0x18000a3bd  jz      short loc_18000A3CF
0x18000a3bf  lea     rcx, [rsp+28h+arg_0]
0x18000a3c4  call    s_UbpmRpcCloseTaskHostChannel
0x18000a3c9  add     rsp, 20h
0x18000a3cd  pop     rbx
0x18000a3ce  retn
0x18000a3cf  inc     dword ptr [rbx+148h]
0x18000a3d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3dc  lea     rax, WPP_GLOBAL_Control
0x18000a3e3  cmp     rcx, rax
0x18000a3e6  jz      short loc_18000A3C9
0x18000a3e8  test    byte ptr [rcx+1Ch], 80h
0x18000a3ec  jz      short loc_18000A3C9
0x18000a3ee  mov     rcx, [rcx+10h]
0x18000a3f2  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000a3f9  mov     edx, 18h
0x18000a3fe  mov     r9, rbx
0x18000a401  add     rsp, 20h
0x18000a405  pop     rbx
0x18000a406  jmp     WPP_SF_q
```
