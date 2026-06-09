# GarbageCollectionNeeded(int,ulong)

- ea: `0x180030cb8`
- end: `0x180030dea`
- name: `?GarbageCollectionNeeded@@YAHHK@Z`
- size: `306`
- prototype: `__int64 __fastcall(int, unsigned int)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000dc54`
- `0x180013244`
- `0x1800147fc`
- `0x180017c58`
- `0x1800303d0`
- `0x180087000`
- `0x1800966dc`
- `0x18009a2ac`
- `0x1800c0e2c`

## callees

- `0x180030cb8`
- `0x18006e39c`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x180030ceb`
- `ntdll!RtlDllShutdownInProgress` at `0x180030ceb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180030d91`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180030d91`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180030cdf`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180030cdf`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180030d39`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180030d39`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180030d7e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180030d7e`

## pseudocode

```c
__int64 __fastcall GarbageCollectionNeeded(int a1, DWORD a2)
{
  struct RPC_THREAD_POOL_TIMER *v4; // rcx
  bool v5; // zf
  unsigned int v6; // ebx
  _FILETIME pftDueTime; // [rsp+40h] [rbp+18h] BYREF
  struct RPC_THREAD_POOL_TIMER *v9; // [rsp+48h] [rbp+20h] BYREF

  pftDueTime = 0;
  v9 = 0;
  RtlAcquireSRWLockExclusive(&gGarbageCollectionTimerLock);
  if ( RtlDllShutdownInProgress() )
    goto LABEL_11;
  v4 = gGarbageCollectionTimer;
  if ( !gGarbageCollectionTimer )
  {
    if ( !(unsigned int)RPC_THREAD_POOL::CreateTimer((PTP_TIMER_CALLBACK)PerformGarbageCollection, 0, &v9) )
    {
      v4 = v9;
      gGarbageCollectionTimer = v9;
      goto LABEL_3;
    }
LABEL_11:
    v6 = 0;
    goto LABEL_10;
  }
LABEL_3:
  v5 = a1 == 0;
  v6 = 1;
  if ( v5 )
  {
    _InterlockedAdd(&PeriodicGarbageCollectItems, 1u);
    v4 = gGarbageCollectionTimer;
  }
  else
  {
    GarbageCollectionRequested = 1;
  }
  if ( !gGarbageCollectionPeriod || gGarbageCollectionPeriod >= a2 )
    gGarbageCollectionPeriod = a2;
  if ( !IsThreadpoolTimerSet(*(PTP_TIMER *)v4) )
  {
    pftDueTime = (_FILETIME)-(__int64)(10000 * gGarbageCollectionPeriod);
    SetThreadpoolTimer(
      *(PTP_TIMER *)gGarbageCollectionTimer,
      &pftDueTime,
      gGarbageCollectionPeriod,
      gGarbageCollectionPeriod >> 1);
  }
LABEL_10:
  RtlReleaseSRWLockExclusive(&gGarbageCollectionTimerLock);
  return v6;
}

```

## disassembly

```asm
0x180030cb8  mov     [rsp+arg_0], rbx
0x180030cbd  push    rdi
0x180030cbe  sub     rsp, 20h
0x180030cc2  mov     ebx, ecx
0x180030cc4  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0
0x180030ccd  lea     rcx, ?gGarbageCollectionTimerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gGarbageCollectionTimerLock
0x180030cd4  mov     [rsp+28h+arg_18], 0
0x180030cdd  mov     edi, edx
0x180030cdf  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180030ce6  nop     dword ptr [rax+rax+00h]
0x180030ceb  call    cs:__imp_RtlDllShutdownInProgress
0x180030cf2  nop     dword ptr [rax+rax+00h]
0x180030cf7  test    al, al
0x180030cf9  jnz     loc_180030DAB
0x180030cff  mov     rcx, cs:?gGarbageCollectionTimer@@3PEAVRPC_THREAD_POOL_TIMER@@EA; RPC_THREAD_POOL_TIMER * gGarbageCollectionTimer
0x180030d06  test    rcx, rcx
0x180030d09  jz      loc_180030DC2
0x180030d0f  test    ebx, ebx
0x180030d11  mov     ebx, 1
0x180030d16  jz      loc_180030DAF
0x180030d1c  mov     cs:?GarbageCollectionRequested@@3JA, ebx; long GarbageCollectionRequested
0x180030d22  mov     eax, cs:?gGarbageCollectionPeriod@@3KA; ulong gGarbageCollectionPeriod
0x180030d28  test    eax, eax
0x180030d2a  jz      short loc_180030D30
0x180030d2c  cmp     eax, edi
0x180030d2e  jb      short loc_180030D36
0x180030d30  mov     cs:?gGarbageCollectionPeriod@@3KA, edi; ulong gGarbageCollectionPeriod
0x180030d36  mov     rcx, [rcx]; pti
0x180030d39  call    cs:__imp_IsThreadpoolTimerSet
0x180030d40  nop     dword ptr [rax+rax+00h]
0x180030d45  test    eax, eax
0x180030d47  jnz     short loc_180030D8A
0x180030d49  mov     r8d, cs:?gGarbageCollectionPeriod@@3KA; msPeriod
0x180030d50  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180030d55  imul    eax, r8d, 2710h
0x180030d5c  mov     r9d, r8d
0x180030d5f  shr     r9d, 1; msWindowLength
0x180030d62  neg     rax
0x180030d65  mov     rcx, rax
0x180030d68  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x180030d6c  shr     rcx, 20h
0x180030d70  mov     [rsp+28h+pftDueTime.dwHighDateTime], ecx
0x180030d74  mov     rcx, cs:?gGarbageCollectionTimer@@3PEAVRPC_THREAD_POOL_TIMER@@EA; RPC_THREAD_POOL_TIMER * gGarbageCollectionTimer
0x180030d7b  mov     rcx, [rcx]; pti
0x180030d7e  call    cs:__imp_SetThreadpoolTimer
0x180030d85  nop     dword ptr [rax+rax+00h]
0x180030d8a  lea     rcx, ?gGarbageCollectionTimerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gGarbageCollectionTimerLock
0x180030d91  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180030d98  nop     dword ptr [rax+rax+00h]
0x180030d9d  mov     eax, ebx
0x180030d9f  mov     rbx, [rsp+28h+arg_0]
0x180030da4  add     rsp, 20h
0x180030da8  pop     rdi
0x180030da9  retn
0x180030dab  xor     ebx, ebx
0x180030dad  jmp     short loc_180030D8A
0x180030daf  lock add cs:?PeriodicGarbageCollectItems@@3JA, ebx; long PeriodicGarbageCollectItems
0x180030db6  mov     rcx, cs:?gGarbageCollectionTimer@@3PEAVRPC_THREAD_POOL_TIMER@@EA; RPC_THREAD_POOL_TIMER * gGarbageCollectionTimer
0x180030dbd  jmp     loc_180030D22
0x180030dc2  lea     r8, [rsp+28h+arg_18]; struct RPC_THREAD_POOL_TIMER **
0x180030dc7  xor     edx, edx; pv
0x180030dc9  lea     rcx, ?PerformGarbageCollection@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180030dd0  call    ?CreateTimer@RPC_THREAD_POOL@@SAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z1PEAPEAVRPC_THREAD_POOL_TIMER@@@Z; RPC_THREAD_POOL::CreateTimer(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *),void *,RPC_THREAD_POOL_TIMER * *)
0x180030dd5  test    eax, eax
0x180030dd7  jnz     short loc_180030DAB
0x180030dd9  mov     rcx, [rsp+28h+arg_18]
0x180030dde  mov     cs:?gGarbageCollectionTimer@@3PEAVRPC_THREAD_POOL_TIMER@@EA, rcx; RPC_THREAD_POOL_TIMER * gGarbageCollectionTimer
0x180030de5  jmp     loc_180030D0F
```
