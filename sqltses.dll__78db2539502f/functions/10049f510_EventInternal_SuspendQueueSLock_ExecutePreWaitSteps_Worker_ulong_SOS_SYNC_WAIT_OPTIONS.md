# EventInternal<SuspendQueueSLock>::ExecutePreWaitSteps(Worker *,ulong,SOS_SYNC_WAIT_OPTIONS)

- ea: `0x10049f510`
- end: `0x10049f74e`
- name: `?ExecutePreWaitSteps@?$EventInternal@USuspendQueueSLock@@@@UEAA?AW4SOS_RESULT@@PEAVWorker@@KW4SOS_SYNC_WAIT_OPTIONS@@@Z`
- size: `574`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x10049f510`
- `0x10049fb80`
- `0x10049fbf0`
- `0x10049fe30`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10049f63c`
- `KERNEL32!QueryPerformanceCounter` at `0x10049f692`
- `KERNEL32!QueryPerformanceCounter` at `0x10049f63c`
- `KERNEL32!QueryPerformanceCounter` at `0x10049f692`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10049f5db`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10049f629`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10049f681`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10049f654`
- `sqldk!?OSYieldNoAbort@Worker@@QEAAXXZ` at `0x10049f59f`
- `sqldk!?OSYieldNoAbort@Worker@@QEAAXXZ` at `0x10049f59f`
- `sqldk!?TrySignal@WorkerWaitContext@@QEAA?AW4WorkerSignalResult@@PEAVMinWaitableBase@@W4WorkerSignalType@@@Z` at `0x10049f6e8`
- `sqldk!?TrySignal@WorkerWaitContext@@QEAA?AW4WorkerSignalResult@@PEAVMinWaitableBase@@W4WorkerSignalType@@@Z` at `0x10049f6e8`
- `sqldk!?EnqueueWait@WorkerWaitContext@@QEAAXPEAVMinWaitableBase@@W4SOS_QUEUE_PLACE@@@Z` at `0x10049f71b`
- `sqldk!?EnqueueWait@WorkerWaitContext@@QEAAXPEAVMinWaitableBase@@W4SOS_QUEUE_PLACE@@@Z` at `0x10049f71b`
- `sqldk!SystemThread_TlsIndex` at `0x10049f5fb`
- `sqldk!SystemThread_TlsOffset` at `0x10049f604`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EventInternal<SuspendQueueSLock>::ExecutePreWaitSteps(__int64 a1, Worker *a2, int a3, int a4)
{
  _QWORD *v6; // rbp
  unsigned int v7; // edi
  unsigned int v8; // r15d
  __int64 v9; // r11
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  LARGE_INTEGER v12; // rbx
  signed __int64 UniqueThread_low; // r12
  __int64 v14; // rbp
  __int64 v15; // r8
  volatile signed __int64 *v16; // rcx
  LARGE_INTEGER v17; // rax
  LONGLONG v18; // rcx
  LARGE_INTEGER v20; // [rsp+20h] [rbp-68h] BYREF
  __int64 v21; // [rsp+28h] [rbp-60h]
  __int64 v22; // [rsp+38h] [rbp-50h] BYREF
  int v23; // [rsp+40h] [rbp-48h]
  _QWORD *v24; // [rsp+90h] [rbp+8h]
  LARGE_INTEGER PerformanceCount; // [rsp+98h] [rbp+10h] BYREF
  int v26; // [rsp+A8h] [rbp+20h]

  v26 = a4;
  v21 = -2;
  v6 = (_QWORD *)((char *)a2 + 1008);
  v24 = (_QWORD *)((char *)a2 + 1008);
  v7 = 0;
  v8 = 0;
  v9 = *((_QWORD *)a2 + 76);
  if ( v9 )
  {
    v10 = __rdtsc();
    v11 = *((_QWORD *)a2 + 104);
    if ( (v10 > v11 || v11 != 0x7FFFFFFFFFFFFFFFLL && v11 - v10 > *(_QWORD *)(v9 + 3568))
      && *(_DWORD *)(a1 + 32) == 1
      && a3 )
    {
      Worker::OSYieldNoAbort(a2);
    }
  }
  v22 = a1 + 24;
  v23 = 0;
  v12.QuadPart = 0;
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( *(_DWORD *)(a1 + 24) || _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 24), UniqueThread_low, 0) )
  {
    v14 = 0;
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
    {
      v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( v15 && *(_QWORD *)(v15 + 272) == v15 )
        v14 = *(_QWORD *)(v15 + 256);
      if ( v14 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v12 = PerformanceCount;
        }
        else
        {
          v12.QuadPart = MEMORY[0x7FFE0008];
        }
      }
    }
    v16 = (volatile signed __int64 *)(a1 + 24);
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(v16, UniqueThread_low);
    else
      Spinlock<25,1,268435714>::SpinToAcquireOptimistic((SpinlockBase *)v16, v14, UniqueThread_low);
    if ( v14 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v20);
        v17 = v20;
      }
      else
      {
        v17.QuadPart = MEMORY[0x7FFE0008];
      }
      v18 = v17.QuadPart - v12.QuadPart;
      if ( v17.QuadPart < (unsigned __int64)v12.QuadPart )
        v18 = 0;
      *(_QWORD *)(v14 + 3192) += v18;
    }
    v6 = v24;
  }
  v23 = 1;
  if ( *(_DWORD *)(a1 + 32) == 1 )
  {
    v8 = 11;
    if ( (unsigned int)WorkerWaitContext::TrySignal(v6, a1, *(_DWORD *)(a1 + 36) != 1) == 1 && *(_DWORD *)(a1 + 36) == 1 )
    {
      *(_QWORD *)(a1 + 40) = 0;
      *(_DWORD *)(a1 + 32) = 0;
    }
  }
  else if ( a3 )
  {
    LOBYTE(v7) = v26 == 0;
    WorkerWaitContext::EnqueueWait(v6, a1, v7);
  }
  else
  {
    v8 = 258;
  }
  SpinlockHolder<25,1,268435714>::~SpinlockHolder<25,1,268435714>(&v22);
  return v8;
}

```

## disassembly

```asm
0x10049f510  mov     [rsp+arg_18], r9d
0x10049f515  push    rbp
0x10049f516  push    rsi
0x10049f517  push    rdi
0x10049f518  push    r12
0x10049f51a  push    r13
0x10049f51c  push    r14
0x10049f51e  push    r15
0x10049f520  sub     rsp, 50h
0x10049f524  mov     [rsp+88h+var_60], 0FFFFFFFFFFFFFFFEh
0x10049f52d  mov     [rsp+88h+arg_10], rbx
0x10049f535  mov     r13d, r8d
0x10049f538  mov     r10, rdx
0x10049f53b  mov     rsi, rcx
0x10049f53e  lea     rbp, [rdx+3F0h]
0x10049f545  mov     [rsp+88h+arg_0], rbp
0x10049f54d  xor     edi, edi
0x10049f54f  mov     r15d, edi
0x10049f552  mov     r11, [rdx+260h]
0x10049f559  test    r11, r11
0x10049f55c  jz      short loc_10049F5A5
0x10049f55e  rdtsc
0x10049f560  shl     rdx, 20h
0x10049f564  or      rax, rdx
0x10049f567  mov     rcx, rax
0x10049f56a  mov     rax, [r10+340h]
0x10049f571  cmp     rcx, rax
0x10049f574  ja      short loc_10049F591
0x10049f576  mov     rdx, 7FFFFFFFFFFFFFFFh
0x10049f580  cmp     rax, rdx
0x10049f583  jz      short loc_10049F5A5
0x10049f585  sub     rax, rcx
0x10049f588  cmp     rax, [r11+0DF0h]
0x10049f58f  jbe     short loc_10049F5A5
0x10049f591  cmp     dword ptr [rsi+20h], 1
0x10049f595  jnz     short loc_10049F5A5
0x10049f597  test    r13d, r13d
0x10049f59a  jz      short loc_10049F5A5
0x10049f59c  mov     rcx, r10
0x10049f59f  call    cs:__imp_?OSYieldNoAbort@Worker@@QEAAXXZ; Worker::OSYieldNoAbort(void)
0x10049f5a5  lea     r14, [rsi+18h]
0x10049f5a9  mov     [rsp+88h+var_50], r14
0x10049f5ae  mov     [rsp+88h+var_48], edi
0x10049f5b2  mov     rbx, rdi
0x10049f5b5  mov     eax, gs:48h
0x10049f5bd  mov     r12d, eax
0x10049f5c0  mov     eax, [r14]
0x10049f5c3  test    eax, eax
0x10049f5c5  jnz     short loc_10049F5DB
0x10049f5c7  xor     eax, eax
0x10049f5c9  lock cmpxchg [r14], r12
0x10049f5ce  mov     eax, edi
0x10049f5d0  setz    al
0x10049f5d3  test    eax, eax
0x10049f5d5  jnz     loc_10049F6C3
0x10049f5db  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10049f5e2  mov     ecx, [rax]
0x10049f5e4  and     ecx, 84h
0x10049f5ea  mov     rbp, rdi
0x10049f5ed  cmp     cl, 84h
0x10049f5f0  jnz     short loc_10049F654
0x10049f5f2  mov     rdx, gs:58h
0x10049f5fb  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10049f602  mov     ecx, [rax]
0x10049f604  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10049f60b  mov     r8d, [rax]
0x10049f60e  add     r8, [rdx+rcx*8]
0x10049f612  jz      short loc_10049F624
0x10049f614  cmp     [r8+110h], r8
0x10049f61b  jnz     short loc_10049F624
0x10049f61d  mov     rbp, [r8+100h]
0x10049f624  test    rbp, rbp
0x10049f627  jz      short loc_10049F654
0x10049f629  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10049f630  cmp     [rax], ebx
0x10049f632  jz      short loc_10049F64C
0x10049f634  lea     rcx, [rsp+88h+PerformanceCount]; lpPerformanceCount
0x10049f63c  call    cs:__imp_QueryPerformanceCounter
0x10049f642  mov     rbx, qword ptr [rsp+88h+PerformanceCount]
0x10049f64a  jmp     short loc_10049F654
0x10049f64c  mov     rbx, ds:7FFE0008h
0x10049f654  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10049f65b  mov     rcx, r14
0x10049f65e  cmp     byte ptr [rax+0C7h], 0
0x10049f665  jge     short loc_10049F674
0x10049f667  mov     r8, r12
0x10049f66a  mov     rdx, rbp
0x10049f66d  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<25,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10049f672  jmp     short loc_10049F67C
0x10049f674  mov     rdx, r12
0x10049f677  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10049f67c  test    rbp, rbp
0x10049f67f  jz      short loc_10049F6BB
0x10049f681  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10049f688  cmp     dword ptr [rax], 0
0x10049f68b  jz      short loc_10049F69F
0x10049f68d  lea     rcx, [rsp+88h+var_68]; lpPerformanceCount
0x10049f692  call    cs:__imp_QueryPerformanceCounter
0x10049f698  mov     rax, qword ptr [rsp+88h+var_68]
0x10049f69d  jmp     short loc_10049F6A7
0x10049f69f  mov     rax, ds:7FFE0008h
0x10049f6a7  mov     rcx, rax
0x10049f6aa  sub     rcx, rbx
0x10049f6ad  cmp     rax, rbx
0x10049f6b0  cmovb   rcx, rdi
0x10049f6b4  add     [rbp+0C78h], rcx
0x10049f6bb  mov     rbp, [rsp+88h+arg_0]
0x10049f6c3  mov     [rsp+88h+var_48], 1
0x10049f6cb  cmp     dword ptr [rsi+20h], 1
0x10049f6cf  jnz     short loc_10049F701
0x10049f6d1  mov     r15d, 0Bh
0x10049f6d7  mov     r8d, edi
0x10049f6da  cmp     dword ptr [rsi+24h], 1
0x10049f6de  setnz   r8b
0x10049f6e2  mov     rdx, rsi
0x10049f6e5  mov     rcx, rbp
0x10049f6e8  call    cs:__imp_?TrySignal@WorkerWaitContext@@QEAA?AW4WorkerSignalResult@@PEAVMinWaitableBase@@W4WorkerSignalType@@@Z; WorkerWaitContext::TrySignal(MinWaitableBase *,WorkerSignalType)
0x10049f6ee  cmp     eax, 1
0x10049f6f1  jnz     short loc_10049F729
0x10049f6f3  cmp     [rsi+24h], eax
0x10049f6f6  jnz     short loc_10049F729
0x10049f6f8  mov     [rsi+28h], rdi
0x10049f6fc  mov     [rsi+20h], edi
0x10049f6ff  jmp     short loc_10049F729
0x10049f701  test    r13d, r13d
0x10049f704  jz      short loc_10049F723
0x10049f706  cmp     [rsp+88h+arg_18], 0
0x10049f70e  setz    dil
0x10049f712  mov     r8d, edi
0x10049f715  mov     rdx, rsi
0x10049f718  mov     rcx, rbp
0x10049f71b  call    cs:__imp_?EnqueueWait@WorkerWaitContext@@QEAAXPEAVMinWaitableBase@@W4SOS_QUEUE_PLACE@@@Z; WorkerWaitContext::EnqueueWait(MinWaitableBase *,SOS_QUEUE_PLACE)
0x10049f721  jmp     short loc_10049F729
0x10049f723  mov     r15d, 102h
0x10049f729  lea     rcx, [rsp+88h+var_50]
0x10049f72e  call    ??1?$SpinlockHolder@$0BJ@$00$0BAAAABAC@@@QEAA@XZ; SpinlockHolder<25,1,268435714>::~SpinlockHolder<25,1,268435714>(void)
0x10049f733  mov     eax, r15d
0x10049f736  mov     rbx, [rsp+88h+arg_10]
0x10049f73e  add     rsp, 50h
0x10049f742  pop     r15
0x10049f744  pop     r14
0x10049f746  pop     r13
0x10049f748  pop     r12
0x10049f74a  pop     rdi
0x10049f74b  pop     rsi
0x10049f74c  pop     rbp
0x10049f74d  retn
```
