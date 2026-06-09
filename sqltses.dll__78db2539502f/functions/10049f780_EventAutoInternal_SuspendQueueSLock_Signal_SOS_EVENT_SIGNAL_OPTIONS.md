# EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)

- ea: `0x10049f780`
- end: `0x10049f999`
- name: `?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z`
- size: `537`
- prototype: ``
- caller_count: `25`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x10041cc30`
- `0x1004a02b0`
- `0x1004a02d0`
- `0x10080f5b0`
- `0x10080f950`
- `0x10080fe70`
- `0x1008103f0`
- `0x100810970`
- `0x100810b70`
- `0x100810f50`
- `0x1008112c0`
- `0x100811630`
- `0x100811a40`
- `0x100811df0`
- `0x100832e40`
- `0x100833df0`
- `0x1008342c0`
- `0x100834420`
- `0x100835630`
- `0x1008356c0`
- `0x100835820`
- `0x100835a00`
- `0x100838200`
- `0x100838470`
- `0x100838ba0`

## callees

- `0x10049f780`
- `0x10049fb80`
- `0x10049fbf0`
- `0x10049fe30`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10049f875`
- `KERNEL32!QueryPerformanceCounter` at `0x10049f8c6`
- `KERNEL32!QueryPerformanceCounter` at `0x10049f875`
- `KERNEL32!QueryPerformanceCounter` at `0x10049f8c6`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10049f818`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10049f866`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10049f8b6`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10049f889`
- `sqldk!?SignalAndGetAll@WorkerWaitQueue@@QEAAHPEAV?$SEList@VWorkerWaitElem@@$0A@@@0H@Z` at `0x10049f907`
- `sqldk!?SignalAndGetAll@WorkerWaitQueue@@QEAAHPEAV?$SEList@VWorkerWaitElem@@$0A@@@0H@Z` at `0x10049f907`
- `sqldk!?ResumeBulk@SOS_Scheduler@@SAXPEAV?$SEList@VWorkerWaitElem@@$0A@@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z` at `0x10049f97b`
- `sqldk!?ResumeBulk@SOS_Scheduler@@SAXPEAV?$SEList@VWorkerWaitElem@@$0A@@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z` at `0x10049f97b`
- `sqldk!SystemThread_TlsIndex` at `0x10049f838`
- `sqldk!SystemThread_TlsOffset` at `0x10049f841`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EventAutoInternal<SuspendQueueSLock>::Signal(__int64 a1, int a2)
{
  BOOL v3; // r12d
  volatile signed __int64 *v4; // r14
  LARGE_INTEGER v5; // rbx
  signed __int64 UniqueThread_low; // r15
  __int64 v7; // rdi
  __int64 v8; // r8
  LARGE_INTEGER v9; // rax
  LONGLONG v10; // rcx
  __int64 *v11; // rax
  _QWORD *v12; // rdx
  __int64 v13; // rcx
  __int64 v15; // [rsp+28h] [rbp-48h] BYREF
  __int64 *v16; // [rsp+30h] [rbp-40h]
  _QWORD v17[2]; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v18[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v19; // [rsp+58h] [rbp-18h] BYREF
  int v20; // [rsp+60h] [rbp-10h]
  LARGE_INTEGER PerformanceCount; // [rsp+B0h] [rbp+40h] BYREF
  LARGE_INTEGER v22; // [rsp+C0h] [rbp+50h] BYREF

  v18[1] = v18;
  v18[0] = v18;
  v17[1] = v17;
  v17[0] = v17;
  v16 = &v15;
  v15 = (__int64)&v15;
  v3 = a2 != 0;
  v4 = (volatile signed __int64 *)(a1 + 24);
  v19 = a1 + 24;
  v20 = 0;
  v5.QuadPart = 0;
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( *(_DWORD *)(a1 + 24) || _InterlockedCompareExchange64(v4, UniqueThread_low, 0) )
  {
    v7 = 0;
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
    {
      v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( v8 && *(_QWORD *)(v8 + 272) == v8 )
        v7 = *(_QWORD *)(v8 + 256);
      if ( v7 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v5 = PerformanceCount;
        }
        else
        {
          v5.QuadPart = MEMORY[0x7FFE0008];
        }
      }
    }
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(v4, UniqueThread_low);
    else
      Spinlock<25,1,268435714>::SpinToAcquireOptimistic(v4, v7, UniqueThread_low);
    if ( v7 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v22);
        v9 = v22;
      }
      else
      {
        v9.QuadPart = MEMORY[0x7FFE0008];
      }
      v10 = v9.QuadPart - v5.QuadPart;
      if ( v9.QuadPart < (unsigned __int64)v5.QuadPart )
        v10 = 0;
      *(_QWORD *)(v7 + 3192) += v10;
    }
  }
  v20 = 1;
  if ( (unsigned int)((__int64 (__fastcall *)(__int64, _QWORD *, __int64 *, __int64, __int64))WorkerWaitQueue::SignalAndGetAll)(
                       a1 + 8,
                       v17,
                       &v15,
                       1,
                       -2) )
  {
    *(_DWORD *)(a1 + 32) = 0;
  }
  else if ( !*(_DWORD *)(a1 + 32) )
  {
    *(_DWORD *)(a1 + 32) = 1;
    *(_QWORD *)(a1 + 40) = 1;
  }
  SpinlockHolder<25,1,268435714>::~SpinlockHolder<25,1,268435714>(&v19);
  while ( 1 )
  {
    v11 = v16;
    if ( v16 == &v15 || !v16 )
      break;
    v12 = (_QWORD *)v16[1];
    v13 = *v16;
    *(_QWORD *)(v13 + 8) = v12;
    *v12 = v13;
    v11[1] = 0;
    *v11 = 0;
    _InterlockedDecrement((volatile signed __int32 *)(v11[2] + 20));
  }
  return SOS_Scheduler::ResumeBulk(v17, v3, 0);
}

```

## disassembly

```asm
0x10049f780  push    rbp
0x10049f782  push    rsi
0x10049f783  push    rdi
0x10049f784  push    r12
0x10049f786  push    r13
0x10049f788  push    r14
0x10049f78a  push    r15
0x10049f78c  mov     rbp, rsp
0x10049f78f  sub     rsp, 70h
0x10049f793  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x10049f79b  mov     [rsp+70h+arg_8], rbx
0x10049f7a3  mov     rsi, rcx
0x10049f7a6  lea     rax, [rbp+var_28]
0x10049f7aa  mov     [rbp+var_20], rax
0x10049f7ae  lea     rax, [rbp+var_28]
0x10049f7b2  mov     [rbp+var_28], rax
0x10049f7b6  lea     rax, [rbp+var_38]
0x10049f7ba  mov     [rbp+var_30], rax
0x10049f7be  lea     rax, [rbp+var_38]
0x10049f7c2  mov     [rbp+var_38], rax
0x10049f7c6  lea     rax, [rbp+var_48]
0x10049f7ca  mov     [rbp+var_40], rax
0x10049f7ce  lea     rax, [rbp+var_48]
0x10049f7d2  mov     [rbp+var_48], rax
0x10049f7d6  xor     r13d, r13d
0x10049f7d9  mov     r12d, r13d
0x10049f7dc  test    edx, edx
0x10049f7de  setnz   r12b
0x10049f7e2  lea     r14, [rcx+18h]
0x10049f7e6  mov     [rbp+var_18], r14
0x10049f7ea  mov     [rbp+var_10], r13d
0x10049f7ee  mov     ebx, r13d
0x10049f7f1  mov     eax, gs:48h
0x10049f7f9  mov     r15d, eax
0x10049f7fc  mov     eax, [r14]
0x10049f7ff  test    eax, eax
0x10049f801  jnz     short loc_10049F818
0x10049f803  xor     eax, eax
0x10049f805  lock cmpxchg [r14], r15
0x10049f80a  mov     eax, r13d
0x10049f80d  setz    al
0x10049f810  test    eax, eax
0x10049f812  jnz     loc_10049F8EE
0x10049f818  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10049f81f  mov     ecx, [rax]
0x10049f821  and     ecx, 84h
0x10049f827  mov     rdi, r13
0x10049f82a  cmp     cl, 84h
0x10049f82d  jnz     short loc_10049F889
0x10049f82f  mov     rdx, gs:58h
0x10049f838  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10049f83f  mov     ecx, [rax]
0x10049f841  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10049f848  mov     r8d, [rax]
0x10049f84b  add     r8, [rdx+rcx*8]
0x10049f84f  jz      short loc_10049F861
0x10049f851  cmp     [r8+110h], r8
0x10049f858  jnz     short loc_10049F861
0x10049f85a  mov     rdi, [r8+100h]
0x10049f861  test    rdi, rdi
0x10049f864  jz      short loc_10049F889
0x10049f866  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10049f86d  cmp     [rax], ebx
0x10049f86f  jz      short loc_10049F881
0x10049f871  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x10049f875  call    cs:__imp_QueryPerformanceCounter
0x10049f87b  mov     rbx, qword ptr [rbp+PerformanceCount]
0x10049f87f  jmp     short loc_10049F889
0x10049f881  mov     rbx, ds:7FFE0008h
0x10049f889  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10049f890  mov     rcx, r14
0x10049f893  cmp     byte ptr [rax+0C7h], 0
0x10049f89a  jge     short loc_10049F8A9
0x10049f89c  mov     r8, r15
0x10049f89f  mov     rdx, rdi
0x10049f8a2  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<25,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10049f8a7  jmp     short loc_10049F8B1
0x10049f8a9  mov     rdx, r15
0x10049f8ac  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10049f8b1  test    rdi, rdi
0x10049f8b4  jz      short loc_10049F8EE
0x10049f8b6  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10049f8bd  cmp     dword ptr [rax], 0
0x10049f8c0  jz      short loc_10049F8D2
0x10049f8c2  lea     rcx, [rbp+arg_10]; lpPerformanceCount
0x10049f8c6  call    cs:__imp_QueryPerformanceCounter
0x10049f8cc  mov     rax, qword ptr [rbp+arg_10]
0x10049f8d0  jmp     short loc_10049F8DA
0x10049f8d2  mov     rax, ds:7FFE0008h
0x10049f8da  mov     rcx, rax
0x10049f8dd  sub     rcx, rbx
0x10049f8e0  cmp     rax, rbx
0x10049f8e3  cmovb   rcx, r13
0x10049f8e7  add     [rdi+0C78h], rcx
0x10049f8ee  mov     [rbp+var_10], 1
0x10049f8f5  lea     rcx, [rsi+8]
0x10049f8f9  mov     r9d, 1
0x10049f8ff  lea     r8, [rbp+var_48]
0x10049f903  lea     rdx, [rbp+var_38]
0x10049f907  call    cs:__imp_?SignalAndGetAll@WorkerWaitQueue@@QEAAHPEAV?$SEList@VWorkerWaitElem@@$0A@@@0H@Z; WorkerWaitQueue::SignalAndGetAll(SEList<WorkerWaitElem,0> *,SEList<WorkerWaitElem,0> *,int)
0x10049f90d  test    eax, eax
0x10049f90f  jz      short loc_10049F917
0x10049f911  mov     [rsi+20h], r13d
0x10049f915  jmp     short loc_10049F92C
0x10049f917  cmp     dword ptr [rsi+20h], 0
0x10049f91b  jnz     short loc_10049F92C
0x10049f91d  mov     dword ptr [rsi+20h], 1
0x10049f924  mov     qword ptr [rsi+28h], 1
0x10049f92c  lea     rcx, [rbp+var_18]
0x10049f930  call    ??1?$SpinlockHolder@$0BJ@$00$0BAAAABAC@@@QEAA@XZ; SpinlockHolder<25,1,268435714>::~SpinlockHolder<25,1,268435714>(void)
0x10049f935  nop     word ptr [rax+rax]
0x10049f93a  nop     word ptr [rax+rax+00h]
0x10049f940  lea     rcx, [rbp+var_48]
0x10049f944  mov     rax, [rbp+var_40]
0x10049f948  cmp     rax, rcx
0x10049f94b  jz      short loc_10049F971
0x10049f94d  test    rax, rax
0x10049f950  jz      short loc_10049F971
0x10049f952  mov     rdx, [rax+8]
0x10049f956  mov     rcx, [rax]
0x10049f959  mov     [rcx+8], rdx
0x10049f95d  mov     [rdx], rcx
0x10049f960  mov     [rax+8], r13
0x10049f964  mov     [rax], r13
0x10049f967  mov     rcx, [rax+10h]
0x10049f96b  lock dec dword ptr [rcx+14h]
0x10049f96f  jmp     short loc_10049F940
0x10049f971  xor     r8d, r8d
0x10049f974  mov     edx, r12d
0x10049f977  lea     rcx, [rbp+var_38]
0x10049f97b  call    cs:__imp_?ResumeBulk@SOS_Scheduler@@SAXPEAV?$SEList@VWorkerWaitElem@@$0A@@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z; SOS_Scheduler::ResumeBulk(SEList<WorkerWaitElem,0> *,SOS_QUEUE_PLACE,SOS_RESULT)
0x10049f981  mov     rbx, [rsp+70h+arg_8]
0x10049f989  add     rsp, 70h
0x10049f98d  pop     r15
0x10049f98f  pop     r14
0x10049f991  pop     r13
0x10049f993  pop     r12
0x10049f995  pop     rdi
0x10049f996  pop     rsi
0x10049f997  pop     rbp
0x10049f998  retn
```
