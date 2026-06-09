# UbpmpTaskHostTerminationCleanup(_UBPM_TASK_HOST_CONTEXT_BLOCK *,void *)

- ea: `0x18000a570`
- end: `0x18000a6d1`
- name: `?UbpmpTaskHostTerminationCleanup@@YAXPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAX@Z`
- size: `353`
- prototype: `void __fastcall(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *, HANDLE WaitHandle)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180002b54`
- `0x18000b6d0`
- `0x180017e88`

## callees

- `0x1800057b0`
- `0x180009750`
- `0x18000a570`
- `0x18000a6e0`
- `0x180032e38`
- `0x18003cbc0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000a607`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000a607`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000a5d1`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000a5d1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a5bb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a5bb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a5fd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a61e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a5fd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a61e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a5c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a5c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a66c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a66c`
- `RPCRT4!RpcAsyncAbortCall` at `0x18000a698`
- `RPCRT4!RpcAsyncAbortCall` at `0x18000a698`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000a59f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000a59f`

## pseudocode

```c
void __fastcall UbpmpTaskHostTerminationCleanup(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *a1, HANDLE WaitHandle)
{
  unsigned int v3; // eax
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v4; // [rsp+50h] [rbp+8h] BYREF
  int v5; // [rsp+60h] [rbp+18h] BYREF
  PRPC_ASYNC_STATE pAsync; // [rsp+68h] [rbp+20h] BYREF

  v4 = a1;
  pAsync = 0;
  v5 = 0;
  if ( !UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    GetLastError();
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 195);
  }
  RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
  dword_18004CF18 = GetCurrentThreadId();
  RtlAcquireSRWLockShared((char *)a1 + 80);
  UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)((char *)a1 + 64));
  UbpmpTaskHostCleanup(a1, &pAsync, &v5);
  *((_DWORD *)a1 + 18) = 0;
  RtlReleaseSRWLockExclusive((char *)a1 + 64);
  RtlReleaseSRWLockShared((char *)a1 + 80);
  dword_18004CF18 = 0;
  RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
  if ( v5 )
    UbpmpDecrementRefAndDelete((__int64 *)&v4, 1);
  if ( pAsync )
  {
    v3 = RpcAsyncAbortCall(pAsync, 0x42Bu);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 196, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v3);
    }
  }
}

```

## disassembly

```asm
0x18000a570  mov     rax, rsp
0x18000a573  mov     [rax+10h], rbx
0x18000a577  mov     [rax+8], rcx
0x18000a57b  push    rsi
0x18000a57c  push    rdi
0x18000a57d  push    r14
0x18000a57f  sub     rsp, 30h
0x18000a583  mov     rbx, rdx
0x18000a586  mov     qword ptr [rax+20h], 0
0x18000a58e  mov     rsi, rcx
0x18000a591  mov     dword ptr [rax+18h], 0
0x18000a598  mov     rcx, rbx; WaitHandle
0x18000a59b  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000a59f  call    cs:__imp_UnregisterWaitEx
0x18000a5a5  lea     r14, WPP_GLOBAL_Control
0x18000a5ac  test    eax, eax
0x18000a5ae  jz      loc_18000A652
0x18000a5b4  lea     rcx, g_TaskHostContextListLock
0x18000a5bb  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000a5c1  call    cs:__imp_GetCurrentThreadId
0x18000a5c7  lea     rcx, [rsi+50h]
0x18000a5cb  mov     cs:dword_18004CF18, eax
0x18000a5d1  call    cs:__imp_RtlAcquireSRWLockShared
0x18000a5d7  lea     rcx, [rsi+40h]; struct _UBPM_SRWLOCK *
0x18000a5db  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18000a5e0  lea     r8, [rsp+48h+arg_10]; int *
0x18000a5e5  mov     rcx, rsi; struct _UBPM_TASK_HOST_CONTEXT_BLOCK *
0x18000a5e8  lea     rdx, [rsp+48h+pAsync]; struct _RPC_ASYNC_STATE **
0x18000a5ed  call    ?UbpmpTaskHostCleanup@@YAXPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAPEAU_RPC_ASYNC_STATE@@PEAH@Z; UbpmpTaskHostCleanup(_UBPM_TASK_HOST_CONTEXT_BLOCK *,_RPC_ASYNC_STATE * *,int *)
0x18000a5f2  lea     rcx, [rsi+40h]
0x18000a5f6  mov     dword ptr [rsi+48h], 0
0x18000a5fd  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000a603  lea     rcx, [rsi+50h]
0x18000a607  call    cs:__imp_RtlReleaseSRWLockShared
0x18000a60d  lea     rcx, g_TaskHostContextListLock
0x18000a614  mov     cs:dword_18004CF18, 0
0x18000a61e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000a624  cmp     [rsp+48h+arg_10], 0
0x18000a629  jz      short loc_18000A63A
0x18000a62b  mov     edx, 1
0x18000a630  lea     rcx, [rsp+48h+arg_0]
0x18000a635  call    UbpmpDecrementRefAndDelete
0x18000a63a  mov     rcx, [rsp+48h+pAsync]; pAsync
0x18000a63f  test    rcx, rcx
0x18000a642  jnz     short loc_18000A693
0x18000a644  mov     rbx, [rsp+48h+arg_8]
0x18000a649  add     rsp, 30h
0x18000a64d  pop     r14
0x18000a64f  pop     rdi
0x18000a650  pop     rsi
0x18000a651  retn
0x18000a652  mov     rax, cs:WPP_GLOBAL_Control
0x18000a659  cmp     rax, r14
0x18000a65c  jz      loc_18000A5B4
0x18000a662  test    byte ptr [rax+1Ch], 1
0x18000a666  jz      loc_18000A5B4
0x18000a66c  call    cs:__imp_GetLastError
0x18000a672  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a679  mov     edx, 0C3h
0x18000a67e  mov     r9, rbx
0x18000a681  mov     [rsp+48h+var_28], eax
0x18000a685  mov     rcx, [rcx+10h]
0x18000a689  call    WPP_SF_qd
0x18000a68e  jmp     loc_18000A5B4
0x18000a693  mov     edx, 42Bh; ExceptionCode
0x18000a698  call    cs:__imp_RpcAsyncAbortCall
0x18000a69e  test    eax, eax
0x18000a6a0  jz      short loc_18000A644
0x18000a6a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6a9  cmp     rcx, r14
0x18000a6ac  jz      short loc_18000A644
0x18000a6ae  test    byte ptr [rcx+1Ch], 1
0x18000a6b2  jz      short loc_18000A644
0x18000a6b4  mov     rcx, [rcx+10h]
0x18000a6b8  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000a6bf  mov     edx, 0C4h
0x18000a6c4  mov     r9d, eax
0x18000a6c7  call    WPP_SF_d
0x18000a6cc  jmp     loc_18000A644
```
