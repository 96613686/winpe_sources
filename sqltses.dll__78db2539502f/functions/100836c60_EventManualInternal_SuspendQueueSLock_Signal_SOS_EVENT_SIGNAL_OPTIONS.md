# EventManualInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)

- ea: `0x100836c60`
- end: `0x100836e25`
- name: `?Signal@?$EventManualInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z`
- size: `453`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x100836030`
- `0x100837f80`

## callees

- `0x10049fb80`
- `0x10049fbf0`
- `0x10049fe30`
- `0x100836c60`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100836d2d`
- `KERNEL32!QueryPerformanceCounter` at `0x100836d86`
- `KERNEL32!QueryPerformanceCounter` at `0x100836d2d`
- `KERNEL32!QueryPerformanceCounter` at `0x100836d86`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100836ccc`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100836d1a`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100836d72`
- `sqldk!?SignalAndResumeBulk@SOS_Scheduler@@SAXPEAVWorkerWaitQueue@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z` at `0x100836e10`
- `sqldk!?SignalAndResumeBulk@SOS_Scheduler@@SAXPEAVWorkerWaitQueue@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z` at `0x100836e10`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100836d45`
- `sqldk!SystemThread_TlsIndex` at `0x100836cec`
- `sqldk!SystemThread_TlsOffset` at `0x100836cf5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EventManualInternal<SuspendQueueSLock>::Signal(__int64 a1, int a2)
{
  BOOL v3; // r15d
  volatile signed __int64 *v4; // rsi
  LARGE_INTEGER v5; // rbx
  signed __int64 UniqueThread_low; // rbp
  __int64 v7; // rdi
  __int64 v8; // r8
  LARGE_INTEGER v9; // rax
  LONGLONG v10; // rcx
  __int64 *v11; // r8
  __int64 v13; // [rsp+28h] [rbp-60h] BYREF
  __int64 *v14; // [rsp+30h] [rbp-58h]
  __int64 v15; // [rsp+38h] [rbp-50h] BYREF
  int v16; // [rsp+40h] [rbp-48h]
  LARGE_INTEGER PerformanceCount; // [rsp+90h] [rbp+8h] BYREF
  LARGE_INTEGER v18; // [rsp+A0h] [rbp+18h] BYREF

  v14 = &v13;
  v13 = (__int64)&v13;
  v3 = a2 != 0;
  v4 = (volatile signed __int64 *)(a1 + 24);
  v15 = a1 + 24;
  v16 = 0;
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
      Spinlock<25,1,268435714>::SpinToAcquireOptimistic((SpinlockBase *)v4, v7, UniqueThread_low);
    if ( v7 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v18);
        v9 = v18;
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
  v16 = 1;
  v11 = (__int64 *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 16) != a1 + 8 )
  {
    *(_QWORD *)(*v11 + 8) = v14;
    *v14 = *v11;
    v14 = *(__int64 **)(a1 + 16);
    *v14 = (__int64)&v13;
    *(_QWORD *)(a1 + 16) = a1 + 8;
    *v11 = (__int64)v11;
  }
  *(_DWORD *)(a1 + 32) = 1;
  SpinlockHolder<25,1,268435714>::~SpinlockHolder<25,1,268435714>(&v15);
  return SOS_Scheduler::SignalAndResumeBulk(&v13, v3, 0);
}

```

## disassembly

```asm
0x100836c60  mov     r11, rsp
0x100836c63  push    rbx
0x100836c64  push    rbp
0x100836c65  push    rsi
0x100836c66  push    rdi
0x100836c67  push    r12
0x100836c69  push    r14
0x100836c6b  push    r15
0x100836c6d  sub     rsp, 50h
0x100836c71  mov     qword ptr [r11-68h], 0FFFFFFFFFFFFFFFEh
0x100836c79  mov     r14, rcx
0x100836c7c  lea     rax, [r11-60h]
0x100836c80  mov     [r11-58h], rax
0x100836c84  lea     rax, [r11-60h]
0x100836c88  mov     [r11-60h], rax
0x100836c8c  xor     r12d, r12d
0x100836c8f  mov     r15d, r12d
0x100836c92  test    edx, edx
0x100836c94  setnz   r15b
0x100836c98  lea     rsi, [rcx+18h]
0x100836c9c  mov     [r11-50h], rsi
0x100836ca0  mov     [r11-48h], r12d
0x100836ca4  mov     ebx, r12d
0x100836ca7  mov     eax, gs:48h
0x100836caf  mov     ebp, eax
0x100836cb1  mov     eax, [rsi]
0x100836cb3  test    eax, eax
0x100836cb5  jnz     short loc_100836CCC
0x100836cb7  xor     eax, eax
0x100836cb9  lock cmpxchg [rsi], rbp
0x100836cbe  mov     eax, r12d
0x100836cc1  setz    al
0x100836cc4  test    eax, eax
0x100836cc6  jnz     loc_100836DB2
0x100836ccc  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100836cd3  mov     ecx, [rax]
0x100836cd5  and     ecx, 84h
0x100836cdb  mov     rdi, r12
0x100836cde  cmp     cl, 84h
0x100836ce1  jnz     short loc_100836D45
0x100836ce3  mov     rdx, gs:58h
0x100836cec  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100836cf3  mov     ecx, [rax]
0x100836cf5  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100836cfc  mov     r8d, [rax]
0x100836cff  add     r8, [rdx+rcx*8]
0x100836d03  jz      short loc_100836D15
0x100836d05  cmp     [r8+110h], r8
0x100836d0c  jnz     short loc_100836D15
0x100836d0e  mov     rdi, [r8+100h]
0x100836d15  test    rdi, rdi
0x100836d18  jz      short loc_100836D45
0x100836d1a  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100836d21  cmp     [rax], ebx
0x100836d23  jz      short loc_100836D3D
0x100836d25  lea     rcx, [rsp+88h+PerformanceCount]; lpPerformanceCount
0x100836d2d  call    cs:__imp_QueryPerformanceCounter
0x100836d33  mov     rbx, qword ptr [rsp+88h+PerformanceCount]
0x100836d3b  jmp     short loc_100836D45
0x100836d3d  mov     rbx, ds:7FFE0008h
0x100836d45  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100836d4c  mov     rcx, rsi
0x100836d4f  cmp     byte ptr [rax+0C7h], 0
0x100836d56  jge     short loc_100836D65
0x100836d58  mov     r8, rbp
0x100836d5b  mov     rdx, rdi
0x100836d5e  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<25,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100836d63  jmp     short loc_100836D6D
0x100836d65  mov     rdx, rbp
0x100836d68  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100836d6d  test    rdi, rdi
0x100836d70  jz      short loc_100836DB2
0x100836d72  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100836d79  cmp     dword ptr [rax], 0
0x100836d7c  jz      short loc_100836D96
0x100836d7e  lea     rcx, [rsp+88h+arg_10]; lpPerformanceCount
0x100836d86  call    cs:__imp_QueryPerformanceCounter
0x100836d8c  mov     rax, qword ptr [rsp+88h+arg_10]
0x100836d94  jmp     short loc_100836D9E
0x100836d96  mov     rax, ds:7FFE0008h
0x100836d9e  mov     rcx, rax
0x100836da1  sub     rcx, rbx
0x100836da4  cmp     rax, rbx
0x100836da7  cmovb   rcx, r12
0x100836dab  add     [rdi+0C78h], rcx
0x100836db2  mov     [rsp+88h+var_48], 1
0x100836dba  lea     r8, [r14+8]
0x100836dbe  cmp     [r8+8], r8
0x100836dc2  jz      short loc_100836DF3
0x100836dc4  mov     rcx, [r8]
0x100836dc7  mov     rax, [rsp+88h+var_58]
0x100836dcc  mov     [rcx+8], rax
0x100836dd0  mov     rcx, [r8]
0x100836dd3  mov     rax, [rsp+88h+var_58]
0x100836dd8  mov     [rax], rcx
0x100836ddb  mov     rax, [r8+8]
0x100836ddf  mov     [rsp+88h+var_58], rax
0x100836de4  lea     rcx, [rsp+88h+var_60]
0x100836de9  mov     [rax], rcx
0x100836dec  mov     [r8+8], r8
0x100836df0  mov     [r8], r8
0x100836df3  mov     dword ptr [r14+20h], 1
0x100836dfb  lea     rcx, [rsp+88h+var_50]
0x100836e00  call    ??1?$SpinlockHolder@$0BJ@$00$0BAAAABAC@@@QEAA@XZ; SpinlockHolder<25,1,268435714>::~SpinlockHolder<25,1,268435714>(void)
0x100836e05  xor     r8d, r8d
0x100836e08  mov     edx, r15d
0x100836e0b  lea     rcx, [rsp+88h+var_60]
0x100836e10  call    cs:__imp_?SignalAndResumeBulk@SOS_Scheduler@@SAXPEAVWorkerWaitQueue@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z; SOS_Scheduler::SignalAndResumeBulk(WorkerWaitQueue *,SOS_QUEUE_PLACE,SOS_RESULT)
0x100836e16  add     rsp, 50h
0x100836e1a  pop     r15
0x100836e1c  pop     r14
0x100836e1e  pop     r12
0x100836e20  pop     rdi
0x100836e21  pop     rsi
0x100836e22  pop     rbp
0x100836e23  pop     rbx
0x100836e24  retn
```
