# UbpmpTaskHostTerminationCleanup(_UBPM_TASK_HOST_CONTEXT_BLOCK *,void *)

- ea: `0x180010220`
- end: `0x1800103b8`
- name: `?UbpmpTaskHostTerminationCleanup@@YAXPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAX@Z`
- size: `408`
- prototype: `void __fastcall(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *, HANDLE WaitHandle)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180003438`
- `0x18000d9bc`
- `0x180010730`

## callees

- `0x180004c30`
- `0x1800060d0`
- `0x180010220`
- `0x1800103c0`
- `0x1800351ec`
- `0x18003f5b4`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800102d5`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800102d5`
- `ntdll!RtlAcquireSRWLockShared` at `0x180010293`
- `ntdll!RtlAcquireSRWLockShared` at `0x180010293`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010271`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010271`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800102c5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800102f2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800102c5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800102f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001027d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001027d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010347`
- `RPCRT4!RpcAsyncAbortCall` at `0x180010379`
- `RPCRT4!RpcAsyncAbortCall` at `0x180010379`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18001024f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18001024f`

## pseudocode

```c
void __fastcall UbpmpTaskHostTerminationCleanup(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *a1, HANDLE WaitHandle)
{
  __int64 v4; // r8
  __int64 v5; // r9
  DWORD LastError; // eax
  __int64 v7; // r8
  unsigned int v8; // eax
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v9; // [rsp+50h] [rbp+8h] BYREF
  int v10; // [rsp+60h] [rbp+18h] BYREF
  PRPC_ASYNC_STATE pAsync; // [rsp+68h] [rbp+20h] BYREF

  v9 = a1;
  pAsync = 0;
  v10 = 0;
  if ( !UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 195, v7, WaitHandle, LastError);
  }
  RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
  dword_180050018 = GetCurrentThreadId();
  RtlAcquireSRWLockShared((char *)a1 + 80);
  UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)((char *)a1 + 64));
  UbpmpTaskHostCleanup(a1, &pAsync, &v10);
  *((_DWORD *)a1 + 18) = 0;
  RtlReleaseSRWLockExclusive((char *)a1 + 64);
  RtlReleaseSRWLockShared((char *)a1 + 80);
  dword_180050018 = 0;
  RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
  if ( v10 )
    UbpmpDecrementRefAndDelete((__int64 *)&v9, 1, v4, v5);
  if ( pAsync )
  {
    v8 = RpcAsyncAbortCall(pAsync, 0x42Bu);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 196, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v8);
    }
  }
}

```

## disassembly

```asm
0x180010220  mov     rax, rsp
0x180010223  mov     [rax+10h], rbx
0x180010227  mov     [rax+8], rcx
0x18001022b  push    rsi
0x18001022c  push    rdi
0x18001022d  push    r14
0x18001022f  sub     rsp, 30h
0x180010233  mov     rbx, rdx
0x180010236  mov     qword ptr [rax+20h], 0
0x18001023e  mov     rsi, rcx
0x180010241  mov     dword ptr [rax+18h], 0
0x180010248  mov     rcx, rbx; WaitHandle
0x18001024b  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18001024f  call    cs:__imp_UnregisterWaitEx
0x180010256  nop     dword ptr [rax+rax+00h]
0x18001025b  lea     r14, WPP_GLOBAL_Control
0x180010262  test    eax, eax
0x180010264  jz      loc_18001032D
0x18001026a  lea     rcx, g_TaskHostContextListLock
0x180010271  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180010278  nop     dword ptr [rax+rax+00h]
0x18001027d  call    cs:__imp_GetCurrentThreadId
0x180010284  nop     dword ptr [rax+rax+00h]
0x180010289  lea     rcx, [rsi+50h]
0x18001028d  mov     cs:dword_180050018, eax
0x180010293  call    cs:__imp_RtlAcquireSRWLockShared
0x18001029a  nop     dword ptr [rax+rax+00h]
0x18001029f  lea     rcx, [rsi+40h]; struct _UBPM_SRWLOCK *
0x1800102a3  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x1800102a8  lea     r8, [rsp+48h+arg_10]; int *
0x1800102ad  mov     rcx, rsi; struct _UBPM_TASK_HOST_CONTEXT_BLOCK *
0x1800102b0  lea     rdx, [rsp+48h+pAsync]; struct _RPC_ASYNC_STATE **
0x1800102b5  call    ?UbpmpTaskHostCleanup@@YAXPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAPEAU_RPC_ASYNC_STATE@@PEAH@Z; UbpmpTaskHostCleanup(_UBPM_TASK_HOST_CONTEXT_BLOCK *,_RPC_ASYNC_STATE * *,int *)
0x1800102ba  lea     rcx, [rsi+40h]
0x1800102be  mov     dword ptr [rsi+48h], 0
0x1800102c5  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800102cc  nop     dword ptr [rax+rax+00h]
0x1800102d1  lea     rcx, [rsi+50h]
0x1800102d5  call    cs:__imp_RtlReleaseSRWLockShared
0x1800102dc  nop     dword ptr [rax+rax+00h]
0x1800102e1  lea     rcx, g_TaskHostContextListLock
0x1800102e8  mov     cs:dword_180050018, 0
0x1800102f2  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800102f9  nop     dword ptr [rax+rax+00h]
0x1800102fe  cmp     [rsp+48h+arg_10], 0
0x180010303  jz      short loc_180010314
0x180010305  mov     edx, 1
0x18001030a  lea     rcx, [rsp+48h+arg_0]
0x18001030f  call    UbpmpDecrementRefAndDelete
0x180010314  mov     rcx, [rsp+48h+pAsync]; pAsync
0x180010319  test    rcx, rcx
0x18001031c  jnz     short loc_180010374
0x18001031e  mov     rbx, [rsp+48h+arg_8]
0x180010323  add     rsp, 30h
0x180010327  pop     r14
0x180010329  pop     rdi
0x18001032a  pop     rsi
0x18001032b  retn
0x18001032d  mov     rax, cs:WPP_GLOBAL_Control
0x180010334  cmp     rax, r14
0x180010337  jz      loc_18001026A
0x18001033d  test    byte ptr [rax+1Ch], 1
0x180010341  jz      loc_18001026A
0x180010347  call    cs:__imp_GetLastError
0x18001034e  nop     dword ptr [rax+rax+00h]
0x180010353  mov     rcx, cs:WPP_GLOBAL_Control
0x18001035a  mov     edx, 0C3h
0x18001035f  mov     r9, rbx
0x180010362  mov     [rsp+48h+var_28], eax
0x180010366  mov     rcx, [rcx+10h]
0x18001036a  call    WPP_SF_qd
0x18001036f  jmp     loc_18001026A
0x180010374  mov     edx, 42Bh; ExceptionCode
0x180010379  call    cs:__imp_RpcAsyncAbortCall
0x180010380  nop     dword ptr [rax+rax+00h]
0x180010385  test    eax, eax
0x180010387  jz      short loc_18001031E
0x180010389  mov     rcx, cs:WPP_GLOBAL_Control
0x180010390  cmp     rcx, r14
0x180010393  jz      short loc_18001031E
0x180010395  test    byte ptr [rcx+1Ch], 1
0x180010399  jz      short loc_18001031E
0x18001039b  mov     rcx, [rcx+10h]
0x18001039f  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x1800103a6  mov     edx, 0C4h
0x1800103ab  mov     r9d, eax
0x1800103ae  call    WPP_SF_d
0x1800103b3  jmp     loc_18001031E
```
