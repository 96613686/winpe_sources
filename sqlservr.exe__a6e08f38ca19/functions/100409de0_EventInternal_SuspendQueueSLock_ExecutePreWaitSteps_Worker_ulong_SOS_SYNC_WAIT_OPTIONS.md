# EventInternal<SuspendQueueSLock>::ExecutePreWaitSteps(Worker *,ulong,SOS_SYNC_WAIT_OPTIONS)

- ea: `0x100409de0`
- end: `0x10040a074`
- name: `?ExecutePreWaitSteps@?$EventInternal@USuspendQueueSLock@@@@UEAA?AW4SOS_RESULT@@PEAVWorker@@KW4SOS_SYNC_WAIT_OPTIONS@@@Z`
- size: `660`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x100409de0`
- `0x10040a5c0`
- `0x10040a800`
- `0x10040aab0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100409f0e`
- `KERNEL32!QueryPerformanceCounter` at `0x100409f67`
- `KERNEL32!QueryPerformanceCounter` at `0x100409f0e`
- `KERNEL32!QueryPerformanceCounter` at `0x100409f67`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100409f26`
- `sqldk!SystemThread_TlsOffset` at `0x100409ed5`
- `sqldk!SystemThread_TlsIndex` at `0x100409ecc`
- `sqldk!?TrySignal@WorkerWaitContext@@QEAA?AW4WorkerSignalResult@@PEAVMinWaitableBase@@W4WorkerSignalType@@@Z` at `0x100409fc6`
- `sqldk!?TrySignal@WorkerWaitContext@@QEAA?AW4WorkerSignalResult@@PEAVMinWaitableBase@@W4WorkerSignalType@@@Z` at `0x100409fc6`
- `sqldk!?EnqueueWait@WorkerWaitContext@@QEAAXPEAVMinWaitableBase@@W4SOS_QUEUE_PLACE@@@Z` at `0x100409ff8`
- `sqldk!?EnqueueWait@WorkerWaitContext@@QEAAXPEAVMinWaitableBase@@W4SOS_QUEUE_PLACE@@@Z` at `0x100409ff8`
- `sqldk!?OSYieldNoAbort@Worker@@QEAAXXZ` at `0x100409e6b`
- `sqldk!?OSYieldNoAbort@Worker@@QEAAXXZ` at `0x100409e6b`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100409efa`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100409f53`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040a00f`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100409eac`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040a01b`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040a01b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EventInternal<SuspendQueueSLock>::ExecutePreWaitSteps(__int64 a1, Worker *a2, int a3, int a4)
{
  int v4; // esi
  _QWORD *v7; // r13
  __int64 v8; // r8
  unsigned int v9; // ebp
  __int64 v10; // r11
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rax
  LARGE_INTEGER v13; // rbx
  signed __int64 UniqueThread_low; // r15
  __int64 v15; // rsi
  __int64 v16; // r8
  volatile signed __int64 *v17; // rcx
  LARGE_INTEGER v18; // rax
  LONGLONG v19; // rcx
  int v20; // eax
  LARGE_INTEGER PerformanceCount; // [rsp+80h] [rbp+8h] BYREF
  LARGE_INTEGER v23; // [rsp+88h] [rbp+10h] BYREF
  int v24; // [rsp+98h] [rbp+20h]

  v24 = a4;
  v4 = a4;
  v7 = (_QWORD *)((char *)a2 + 1008);
  v8 = 0;
  v9 = 0;
  v10 = *((_QWORD *)a2 + 76);
  if ( v10 )
  {
    v11 = __rdtsc();
    v12 = *((_QWORD *)a2 + 104);
    if ( (v11 > v12 || v12 != 0x7FFFFFFFFFFFFFFFLL && v12 - v11 > *(_QWORD *)(v10 + 3568))
      && *(_DWORD *)(a1 + 32) == 1
      && a3 )
    {
      Worker::OSYieldNoAbort(a2);
      v8 = 0;
    }
  }
  v13.QuadPart = 0;
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( *(_DWORD *)(a1 + 24) || _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 24), UniqueThread_low, 0) )
  {
    v15 = 0;
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
    {
      v16 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( v16 && *(_QWORD *)(v16 + 272) == v16 )
        v15 = *(_QWORD *)(v16 + 256);
      if ( v15 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v13 = PerformanceCount;
        }
        else
        {
          v13.QuadPart = MEMORY[0x7FFE0008];
        }
      }
    }
    v17 = (volatile signed __int64 *)(a1 + 24);
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(v17, UniqueThread_low);
    else
      Spinlock<25,1,268435714>::SpinToAcquireOptimistic(v17, v15, UniqueThread_low);
    if ( v15 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v23);
        v18 = v23;
      }
      else
      {
        v18.QuadPart = MEMORY[0x7FFE0008];
      }
      v19 = v18.QuadPart - v13.QuadPart;
      v8 = 0;
      if ( v18.QuadPart < (unsigned __int64)v13.QuadPart )
        v19 = 0;
      *(_QWORD *)(v15 + 3192) += v19;
    }
    else
    {
      v8 = 0;
    }
    v4 = v24;
  }
  if ( *(_DWORD *)(a1 + 32) == 1 )
  {
    v9 = 11;
    LOBYTE(v8) = *(_DWORD *)(a1 + 36) != 1;
    if ( (unsigned int)WorkerWaitContext::TrySignal(v7, a1, v8) == 1 && *(_DWORD *)(a1 + 36) == 1 )
    {
      *(_QWORD *)(a1 + 40) = 0;
      *(_DWORD *)(a1 + 32) = 0;
    }
  }
  else if ( a3 )
  {
    LOBYTE(v8) = v4 == 0;
    WorkerWaitContext::EnqueueWait(v7, a1, v8);
  }
  else
  {
    v9 = 258;
  }
  if ( a1 != -24 )
  {
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v20 = rand();
      if ( v20 == 5 * (v20 / 5) )
        Spinlock<25,1,268435714>::UpdateStatSnapshot();
    }
    *(_QWORD *)(a1 + 24) = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x100409de0  mov     [rsp+arg_18], r9d
0x100409de5  push    rbp
0x100409de6  push    rsi
0x100409de7  push    rdi
0x100409de8  push    r12
0x100409dea  push    r13
0x100409dec  push    r14
0x100409dee  push    r15
0x100409df0  sub     rsp, 40h
0x100409df4  mov     [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh
0x100409dfd  mov     [rsp+78h+arg_10], rbx
0x100409e05  mov     esi, r9d
0x100409e08  mov     r12d, r8d
0x100409e0b  mov     r10, rdx
0x100409e0e  mov     rdi, rcx
0x100409e11  lea     r13, [rdx+3F0h]
0x100409e18  xor     r8d, r8d
0x100409e1b  mov     ebp, r8d
0x100409e1e  mov     r11, [rdx+260h]
0x100409e25  test    r11, r11
0x100409e28  jz      short loc_100409E74
0x100409e2a  rdtsc
0x100409e2c  shl     rdx, 20h
0x100409e30  or      rax, rdx
0x100409e33  mov     rcx, rax
0x100409e36  mov     rax, [r10+340h]
0x100409e3d  cmp     rcx, rax
0x100409e40  ja      short loc_100409E5D
0x100409e42  mov     rdx, 7FFFFFFFFFFFFFFFh
0x100409e4c  cmp     rax, rdx
0x100409e4f  jz      short loc_100409E74
0x100409e51  sub     rax, rcx
0x100409e54  cmp     rax, [r11+0DF0h]
0x100409e5b  jbe     short loc_100409E74
0x100409e5d  cmp     dword ptr [rdi+20h], 1
0x100409e61  jnz     short loc_100409E74
0x100409e63  test    r12d, r12d
0x100409e66  jz      short loc_100409E74
0x100409e68  mov     rcx, r10
0x100409e6b  call    cs:__imp_?OSYieldNoAbort@Worker@@QEAAXXZ; Worker::OSYieldNoAbort(void)
0x100409e71  xor     r8d, r8d
0x100409e74  lea     r14, [rdi+18h]
0x100409e78  mov     [rsp+78h+var_48], r14
0x100409e7d  mov     [rsp+78h+var_40], r8d
0x100409e82  mov     rbx, r8
0x100409e85  mov     eax, gs:48h
0x100409e8d  mov     r15d, eax
0x100409e90  mov     eax, [r14]
0x100409e93  test    eax, eax
0x100409e95  jnz     short loc_100409EAC
0x100409e97  xor     eax, eax
0x100409e99  lock cmpxchg [r14], r15
0x100409e9e  mov     eax, r8d
0x100409ea1  setz    al
0x100409ea4  test    eax, eax
0x100409ea6  jnz     loc_100409FA5
0x100409eac  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100409eb3  mov     ecx, [rax]
0x100409eb5  and     ecx, 84h
0x100409ebb  mov     rsi, r8
0x100409ebe  cmp     cl, 84h
0x100409ec1  jnz     short loc_100409F26
0x100409ec3  mov     rdx, gs:58h
0x100409ecc  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100409ed3  mov     ecx, [rax]
0x100409ed5  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100409edc  mov     r8d, [rax]
0x100409edf  add     r8, [rdx+rcx*8]
0x100409ee3  jz      short loc_100409EF5
0x100409ee5  cmp     [r8+110h], r8
0x100409eec  jnz     short loc_100409EF5
0x100409eee  mov     rsi, [r8+100h]
0x100409ef5  test    rsi, rsi
0x100409ef8  jz      short loc_100409F26
0x100409efa  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100409f01  cmp     dword ptr [rax], 0
0x100409f04  jz      short loc_100409F1E
0x100409f06  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x100409f0e  call    cs:__imp_QueryPerformanceCounter
0x100409f14  mov     rbx, qword ptr [rsp+78h+PerformanceCount]
0x100409f1c  jmp     short loc_100409F26
0x100409f1e  mov     rbx, ds:7FFE0008h
0x100409f26  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100409f2d  mov     rcx, r14
0x100409f30  cmp     byte ptr [rax+0C7h], 0
0x100409f37  jge     short loc_100409F46
0x100409f39  mov     r8, r15
0x100409f3c  mov     rdx, rsi
0x100409f3f  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<25,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100409f44  jmp     short loc_100409F4E
0x100409f46  mov     rdx, r15
0x100409f49  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100409f4e  test    rsi, rsi
0x100409f51  jz      short loc_100409F9B
0x100409f53  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100409f5a  cmp     dword ptr [rax], 0
0x100409f5d  jz      short loc_100409F77
0x100409f5f  lea     rcx, [rsp+78h+arg_8]; lpPerformanceCount
0x100409f67  call    cs:__imp_QueryPerformanceCounter
0x100409f6d  mov     rax, qword ptr [rsp+78h+arg_8]
0x100409f75  jmp     short loc_100409F7F
0x100409f77  mov     rax, ds:7FFE0008h
0x100409f7f  mov     rcx, rax
0x100409f82  sub     rcx, rbx
0x100409f85  cmp     rax, rbx
0x100409f88  mov     r8d, 0
0x100409f8e  cmovb   rcx, r8
0x100409f92  add     [rsi+0C78h], rcx
0x100409f99  jmp     short loc_100409F9E
0x100409f9b  xor     r8d, r8d
0x100409f9e  mov     esi, [rsp+78h+arg_18]
0x100409fa5  mov     [rsp+78h+var_40], 1
0x100409fad  cmp     dword ptr [rdi+20h], 1
0x100409fb1  jnz     short loc_100409FE7
0x100409fb3  mov     ebp, 0Bh
0x100409fb8  cmp     dword ptr [rdi+24h], 1
0x100409fbc  setnz   r8b
0x100409fc0  mov     rdx, rdi
0x100409fc3  mov     rcx, r13
0x100409fc6  call    cs:__imp_?TrySignal@WorkerWaitContext@@QEAA?AW4WorkerSignalResult@@PEAVMinWaitableBase@@W4WorkerSignalType@@@Z; WorkerWaitContext::TrySignal(MinWaitableBase *,WorkerSignalType)
0x100409fcc  cmp     eax, 1
0x100409fcf  jnz     short loc_10040A005
0x100409fd1  cmp     [rdi+24h], eax
0x100409fd4  jnz     short loc_10040A005
0x100409fd6  mov     qword ptr [rdi+28h], 0
0x100409fde  mov     dword ptr [rdi+20h], 0
0x100409fe5  jmp     short loc_10040A005
0x100409fe7  test    r12d, r12d
0x100409fea  jz      short loc_10040A000
0x100409fec  test    esi, esi
0x100409fee  setz    r8b
0x100409ff2  mov     rdx, rdi
0x100409ff5  mov     rcx, r13
0x100409ff8  call    cs:__imp_?EnqueueWait@WorkerWaitContext@@QEAAXPEAVMinWaitableBase@@W4SOS_QUEUE_PLACE@@@Z; WorkerWaitContext::EnqueueWait(MinWaitableBase *,SOS_QUEUE_PLACE)
0x100409ffe  jmp     short loc_10040A005
0x10040a000  mov     ebp, 102h
0x10040a005  mov     rbx, [rsp+78h+var_48]
0x10040a00a  test    rbx, rbx
0x10040a00d  jz      short loc_10040A05A
0x10040a00f  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10040a016  cmp     byte ptr [rax], 0
0x10040a019  jz      short loc_10040A042
0x10040a01b  call    cs:__imp_rand
0x10040a021  mov     r8d, eax
0x10040a024  mov     eax, 66666667h
0x10040a029  imul    r8d
0x10040a02c  sar     edx, 1
0x10040a02e  mov     ecx, edx
0x10040a030  shr     ecx, 1Fh
0x10040a033  add     edx, ecx
0x10040a035  lea     ecx, [rdx+rdx*4]
0x10040a038  cmp     r8d, ecx
0x10040a03b  jnz     short loc_10040A042
0x10040a03d  call    ?UpdateStatSnapshot@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<25,1,268435714>::UpdateStatSnapshot(void)
0x10040a042  mov     qword ptr [rbx], 0
0x10040a049  mov     [rsp+78h+var_48], 0
0x10040a052  mov     [rsp+78h+var_40], 0
0x10040a05a  mov     eax, ebp
0x10040a05c  mov     rbx, [rsp+78h+arg_10]
0x10040a064  add     rsp, 40h
0x10040a068  pop     r15
0x10040a06a  pop     r14
0x10040a06c  pop     r13
0x10040a06e  pop     r12
0x10040a070  pop     rdi
0x10040a071  pop     rsi
0x10040a072  pop     rbp
0x10040a073  retn
```
