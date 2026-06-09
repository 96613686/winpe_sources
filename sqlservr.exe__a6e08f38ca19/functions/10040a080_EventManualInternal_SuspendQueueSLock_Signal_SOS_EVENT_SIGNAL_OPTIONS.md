# EventManualInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)

- ea: `0x10040a080`
- end: `0x10040a285`
- name: `?Signal@?$EventManualInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z`
- size: `517`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10040ba70`
- `0x10040bec0`
- `0x100412470`
- `0x100418d20`
- `0x10041a8a0`
- `0x100423f30`
- `0x100424110`

## callees

- `0x10040a080`
- `0x10040a5c0`
- `0x10040a800`
- `0x10040aab0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10040a14d`
- `KERNEL32!QueryPerformanceCounter` at `0x10040a1a6`
- `KERNEL32!QueryPerformanceCounter` at `0x10040a14d`
- `KERNEL32!QueryPerformanceCounter` at `0x10040a1a6`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10040a165`
- `sqldk!SystemThread_TlsOffset` at `0x10040a115`
- `sqldk!SystemThread_TlsIndex` at `0x10040a10c`
- `sqldk!?SignalAndResumeBulk@SOS_Scheduler@@SAXPEAVWorkerWaitQueue@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z` at `0x10040a270`
- `sqldk!?SignalAndResumeBulk@SOS_Scheduler@@SAXPEAVWorkerWaitQueue@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z` at `0x10040a270`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040a13a`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040a192`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040a225`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040a0ec`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040a231`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040a231`

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
  __int64 *v11; // rdx
  _QWORD *v12; // rbx
  int v13; // r8d
  __int64 v15; // [rsp+28h] [rbp-60h] BYREF
  __int64 *v16; // [rsp+30h] [rbp-58h]
  _QWORD *v17; // [rsp+38h] [rbp-50h]
  int v18; // [rsp+40h] [rbp-48h]
  LARGE_INTEGER PerformanceCount; // [rsp+90h] [rbp+8h] BYREF
  LARGE_INTEGER v20; // [rsp+A0h] [rbp+18h] BYREF

  v16 = &v15;
  v15 = (__int64)&v15;
  v3 = a2 != 0;
  v4 = (volatile signed __int64 *)(a1 + 24);
  v17 = (_QWORD *)(a1 + 24);
  v18 = 0;
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
        QueryPerformanceCounter(&v20);
        v9 = v20;
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
  v18 = 1;
  v11 = (__int64 *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 16) != a1 + 8 )
  {
    *(_QWORD *)(*v11 + 8) = v16;
    *v16 = *v11;
    v16 = *(__int64 **)(a1 + 16);
    *v16 = (__int64)&v15;
    *(_QWORD *)(a1 + 16) = a1 + 8;
    *v11 = (__int64)v11;
  }
  *(_DWORD *)(a1 + 32) = 1;
  v12 = v17;
  if ( v17 )
  {
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v13 = rand();
      if ( v13 == 5 * (v13 / 5) )
        Spinlock<25,1,268435714>::UpdateStatSnapshot();
    }
    *v12 = 0;
    v17 = 0;
    v18 = 0;
  }
  return SOS_Scheduler::SignalAndResumeBulk(&v15, v3, 0);
}

```

## disassembly

```asm
0x10040a080  mov     r11, rsp
0x10040a083  push    rbx
0x10040a084  push    rbp
0x10040a085  push    rsi
0x10040a086  push    rdi
0x10040a087  push    r12
0x10040a089  push    r14
0x10040a08b  push    r15
0x10040a08d  sub     rsp, 50h
0x10040a091  mov     qword ptr [r11-68h], 0FFFFFFFFFFFFFFFEh
0x10040a099  mov     r14, rcx
0x10040a09c  lea     rax, [r11-60h]
0x10040a0a0  mov     [r11-58h], rax
0x10040a0a4  lea     rax, [r11-60h]
0x10040a0a8  mov     [r11-60h], rax
0x10040a0ac  xor     r12d, r12d
0x10040a0af  mov     r15d, r12d
0x10040a0b2  test    edx, edx
0x10040a0b4  setnz   r15b
0x10040a0b8  lea     rsi, [rcx+18h]
0x10040a0bc  mov     [r11-50h], rsi
0x10040a0c0  mov     [r11-48h], r12d
0x10040a0c4  mov     ebx, r12d
0x10040a0c7  mov     eax, gs:48h
0x10040a0cf  mov     ebp, eax
0x10040a0d1  mov     eax, [rsi]
0x10040a0d3  test    eax, eax
0x10040a0d5  jnz     short loc_10040A0EC
0x10040a0d7  xor     eax, eax
0x10040a0d9  lock cmpxchg [rsi], rbp
0x10040a0de  mov     eax, r12d
0x10040a0e1  setz    al
0x10040a0e4  test    eax, eax
0x10040a0e6  jnz     loc_10040A1D2
0x10040a0ec  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040a0f3  mov     ecx, [rax]
0x10040a0f5  and     ecx, 84h
0x10040a0fb  mov     rdi, r12
0x10040a0fe  cmp     cl, 84h
0x10040a101  jnz     short loc_10040A165
0x10040a103  mov     rdx, gs:58h
0x10040a10c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040a113  mov     ecx, [rax]
0x10040a115  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040a11c  mov     r8d, [rax]
0x10040a11f  add     r8, [rdx+rcx*8]
0x10040a123  jz      short loc_10040A135
0x10040a125  cmp     [r8+110h], r8
0x10040a12c  jnz     short loc_10040A135
0x10040a12e  mov     rdi, [r8+100h]
0x10040a135  test    rdi, rdi
0x10040a138  jz      short loc_10040A165
0x10040a13a  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040a141  cmp     [rax], ebx
0x10040a143  jz      short loc_10040A15D
0x10040a145  lea     rcx, [rsp+88h+PerformanceCount]; lpPerformanceCount
0x10040a14d  call    cs:__imp_QueryPerformanceCounter
0x10040a153  mov     rbx, qword ptr [rsp+88h+PerformanceCount]
0x10040a15b  jmp     short loc_10040A165
0x10040a15d  mov     rbx, ds:7FFE0008h
0x10040a165  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10040a16c  mov     rcx, rsi
0x10040a16f  cmp     byte ptr [rax+0C7h], 0
0x10040a176  jge     short loc_10040A185
0x10040a178  mov     r8, rbp
0x10040a17b  mov     rdx, rdi
0x10040a17e  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<25,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10040a183  jmp     short loc_10040A18D
0x10040a185  mov     rdx, rbp
0x10040a188  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10040a18d  test    rdi, rdi
0x10040a190  jz      short loc_10040A1D2
0x10040a192  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040a199  cmp     dword ptr [rax], 0
0x10040a19c  jz      short loc_10040A1B6
0x10040a19e  lea     rcx, [rsp+88h+arg_10]; lpPerformanceCount
0x10040a1a6  call    cs:__imp_QueryPerformanceCounter
0x10040a1ac  mov     rax, qword ptr [rsp+88h+arg_10]
0x10040a1b4  jmp     short loc_10040A1BE
0x10040a1b6  mov     rax, ds:7FFE0008h
0x10040a1be  mov     rcx, rax
0x10040a1c1  sub     rcx, rbx
0x10040a1c4  cmp     rax, rbx
0x10040a1c7  cmovb   rcx, r12
0x10040a1cb  add     [rdi+0C78h], rcx
0x10040a1d2  mov     [rsp+88h+var_48], 1
0x10040a1da  lea     rdx, [r14+8]
0x10040a1de  cmp     [rdx+8], rdx
0x10040a1e2  jz      short loc_10040A213
0x10040a1e4  mov     rcx, [rdx]
0x10040a1e7  mov     rax, [rsp+88h+var_58]
0x10040a1ec  mov     [rcx+8], rax
0x10040a1f0  mov     rcx, [rdx]
0x10040a1f3  mov     rax, [rsp+88h+var_58]
0x10040a1f8  mov     [rax], rcx
0x10040a1fb  mov     rax, [rdx+8]
0x10040a1ff  mov     [rsp+88h+var_58], rax
0x10040a204  lea     rcx, [rsp+88h+var_60]
0x10040a209  mov     [rax], rcx
0x10040a20c  mov     [rdx+8], rdx
0x10040a210  mov     [rdx], rdx
0x10040a213  mov     dword ptr [r14+20h], 1
0x10040a21b  mov     rbx, [rsp+88h+var_50]
0x10040a220  test    rbx, rbx
0x10040a223  jz      short loc_10040A265
0x10040a225  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10040a22c  cmp     byte ptr [rax], 0
0x10040a22f  jz      short loc_10040A258
0x10040a231  call    cs:__imp_rand
0x10040a237  mov     r8d, eax
0x10040a23a  mov     eax, 66666667h
0x10040a23f  imul    r8d
0x10040a242  sar     edx, 1
0x10040a244  mov     ecx, edx
0x10040a246  shr     ecx, 1Fh
0x10040a249  add     edx, ecx
0x10040a24b  lea     ecx, [rdx+rdx*4]
0x10040a24e  cmp     r8d, ecx
0x10040a251  jnz     short loc_10040A258
0x10040a253  call    ?UpdateStatSnapshot@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<25,1,268435714>::UpdateStatSnapshot(void)
0x10040a258  mov     [rbx], r12
0x10040a25b  mov     [rsp+88h+var_50], r12
0x10040a260  mov     [rsp+88h+var_48], r12d
0x10040a265  xor     r8d, r8d
0x10040a268  mov     edx, r15d
0x10040a26b  lea     rcx, [rsp+88h+var_60]
0x10040a270  call    cs:__imp_?SignalAndResumeBulk@SOS_Scheduler@@SAXPEAVWorkerWaitQueue@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z; SOS_Scheduler::SignalAndResumeBulk(WorkerWaitQueue *,SOS_QUEUE_PLACE,SOS_RESULT)
0x10040a276  add     rsp, 50h
0x10040a27a  pop     r15
0x10040a27c  pop     r14
0x10040a27e  pop     r12
0x10040a280  pop     rdi
0x10040a281  pop     rsi
0x10040a282  pop     rbp
0x10040a283  pop     rbx
0x10040a284  retn
```
