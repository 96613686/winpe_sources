# UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>::LongWait(Worker *,ulong,SOS_WaitInfo const * const)

- ea: `0x10045eb60`
- end: `0x10045ef40`
- name: `?LongWait@?$UnfairRecursiveMutexInternal@USuspendQueueExpSLock@@$0A@@@AEAA?AW4SOS_RESULT@@PEAVWorker@@KQEBVSOS_WaitInfo@@@Z`
- size: `992`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x10044dd90`
- `0x1007dfd50`

## callees

- `0x10045eb60`
- `0x10045f270`
- `0x10045f450`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x10045ec1e`
- `KERNEL32!GetTickCount` at `0x10045ec1e`
- `KERNEL32!QueryPerformanceCounter` at `0x10045ed4d`
- `KERNEL32!QueryPerformanceCounter` at `0x10045ed7d`
- `KERNEL32!QueryPerformanceCounter` at `0x10045ed4d`
- `KERNEL32!QueryPerformanceCounter` at `0x10045ed7d`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10045eceb`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10045edde`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10045ee66`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10045ed3d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10045ed6d`
- `sqldk!?PostWait@SOS_Task@@SAXPEBVSOS_WaitInfo@@W4SOS_RESULT@@@Z` at `0x10045eec6`
- `sqldk!?PostWait@SOS_Task@@SAXPEBVSOS_WaitInfo@@W4SOS_RESULT@@@Z` at `0x10045eec6`
- `sqldk!?Suspend@SOS_Scheduler@@SA?AW4SOS_RESULT@@PEAVWorker@@K@Z` at `0x10045eeb8`
- `sqldk!?Suspend@SOS_Scheduler@@SA?AW4SOS_RESULT@@PEAVWorker@@K@Z` at `0x10045eeb8`
- `sqldk!?PreWait@SOS_Task@@SAXPEBVSOS_WaitInfo@@@Z` at `0x10045eead`
- `sqldk!?PreWait@SOS_Task@@SAXPEBVSOS_WaitInfo@@@Z` at `0x10045eead`
- `sqldk!?EnqueueWait@WorkerWaitContext@@QEAAXPEAVMinWaitableBase@@W4SOS_QUEUE_PLACE@@@Z` at `0x10045ee5f`
- `sqldk!?EnqueueWait@WorkerWaitContext@@QEAAXPEAVMinWaitableBase@@W4SOS_QUEUE_PLACE@@@Z` at `0x10045ee5f`
- `sqldk!?NotifyDoneWaiting@WorkerWaitContext@@QEAAXXZ` at `0x10045eecf`
- `sqldk!?NotifyDoneWaiting@WorkerWaitContext@@QEAAXXZ` at `0x10045ef27`
- `sqldk!?NotifyDoneWaiting@WorkerWaitContext@@QEAAXXZ` at `0x10045eecf`
- `sqldk!?NotifyDoneWaiting@WorkerWaitContext@@QEAAXXZ` at `0x10045ef27`
- `sqldk!SystemThread_TlsIndex` at `0x10045ec5b`
- `sqldk!SystemThread_TlsIndex` at `0x10045ed0f`
- `sqldk!SystemThread_TlsOffset` at `0x10045ec64`
- `sqldk!SystemThread_TlsOffset` at `0x10045ed18`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10045ec7f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10045ec7f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10045edea`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10045ee72`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10045edea`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10045ee72`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>::LongWait(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        const struct SOS_WaitInfo *a4)
{
  unsigned int v4; // r15d
  DWORD v7; // r14d
  __int64 v8; // r12
  __int64 v9; // rax
  bool v10; // bl
  unsigned int v11; // edi
  unsigned int v12; // edi
  DWORD TickCount; // eax
  __int64 v14; // rbx
  __int64 v15; // r14
  int v16; // ecx
  signed __int64 UniqueThread_low; // r15
  __int64 v18; // r12
  __int64 v19; // r8
  LARGE_INTEGER v20; // rbx
  LARGE_INTEGER v21; // rcx
  LONGLONG v22; // rax
  int v23; // r8d
  WorkerWaitContext *v24; // rbx
  int v25; // r8d
  __int64 v27; // [rsp+20h] [rbp-58h]
  LARGE_INTEGER PerformanceCount; // [rsp+28h] [rbp-50h] BYREF
  LARGE_INTEGER v29; // [rsp+30h] [rbp-48h] BYREF
  __int64 v30; // [rsp+38h] [rbp-40h]
  volatile signed __int64 *v31; // [rsp+48h] [rbp-30h]
  int v32; // [rsp+50h] [rbp-28h]
  int v33; // [rsp+58h] [rbp-20h]
  __int64 v34; // [rsp+60h] [rbp-18h]
  DWORD v35; // [rsp+C0h] [rbp+48h]
  WorkerWaitContext *v36; // [rsp+C8h] [rbp+50h]

  v30 = -2;
  v4 = a3;
  v7 = 0;
  v35 = 0;
  v8 = 0;
  v27 = 0;
  if ( a2 == (_QWORD *)-1008LL )
  {
    v36 = 0;
  }
  else
  {
    v36 = (WorkerWaitContext *)(a2 + 126);
    *(_DWORD *)(a2[127] + 800LL) |= 0x800000u;
  }
  v9 = *(_QWORD *)(a1 + 32);
  while ( 2 )
  {
    v10 = v9 == 0;
    while ( 1 )
    {
      if ( v10 )
      {
        v11 = 0;
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 32), (signed __int64)a2, 0) )
        {
          v11 = 0x80000000;
        }
        else
        {
          *(_QWORD *)(a1 + 48) = a2[76];
          *(_QWORD *)(a1 + 56) = 1;
          *(_QWORD *)(a1 + 40) = a2[75];
          a2[21] = 0;
        }
        if ( !v11 )
          goto LABEL_47;
      }
      v12 = -1;
      if ( v4 != -1 )
      {
        TickCount = GetTickCount();
        if ( !v8 )
          v7 = TickCount;
        v35 = v7;
        if ( v4 <= TickCount - v7 || (v12 = v4 + v7 - TickCount) == 0 )
        {
          v11 = 258;
LABEL_47:
          v24 = v36;
          goto LABEL_48;
        }
      }
      v33 = 0;
      v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v15 = *(_QWORD *)(v14 + 256);
      if ( !v15 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v15 = *(_QWORD *)(v14 + 256);
      }
      v34 = v15;
      v16 = *(_DWORD *)(v15 + 616);
      v33 = !(*(_BYTE *)(v15 + 616) & 1);
      *(_DWORD *)(v15 + 616) = v16 | 1;
      v31 = (volatile signed __int64 *)(a1 + 24);
      v32 = 0;
      UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)(a1 + 24) || _InterlockedCompareExchange64(v31, UniqueThread_low, 0) )
      {
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v18 = 0;
          v19 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v19 && *(_QWORD *)(v19 + 272) == v19 )
            v18 = *(_QWORD *)(v19 + 256);
          if ( v18 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&PerformanceCount);
              v20 = PerformanceCount;
            }
            else
            {
              v20.QuadPart = MEMORY[0x7FFE0008];
            }
            Spinlock<26,1,268435713>::SpinToAcquireWithExponentialBackoff(v31, UniqueThread_low);
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v29);
              v21 = v29;
            }
            else
            {
              v21.QuadPart = MEMORY[0x7FFE0008];
            }
            v22 = 0;
            if ( v21.QuadPart >= (unsigned __int64)v20.QuadPart )
              v22 = v21.QuadPart - v20.QuadPart;
            *(_QWORD *)(v18 + 3192) += v22;
            v8 = v27;
          }
          else
          {
            Spinlock<26,1,268435713>::SpinToAcquireWithExponentialBackoff(v31, UniqueThread_low);
            v8 = v27;
          }
        }
        else
        {
          Spinlock<26,1,268435713>::SpinToAcquireWithExponentialBackoff(v31, UniqueThread_low);
        }
      }
      v32 = 1;
      if ( *(_QWORD *)(a1 + 32) )
        break;
      v10 = 1;
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v23 = rand();
        if ( v23 == 5 * (v23 / 5) )
          Spinlock<26,1,268435713>::UpdateStatSnapshot();
      }
      *v31 = 0;
      v31 = 0;
      v32 = 0;
      *(_DWORD *)(v15 + 616) &= ~v33;
      v7 = v35;
      v4 = a3;
    }
    a2[21] = a1 + 40;
    v24 = v36;
    WorkerWaitContext::EnqueueWait(v36, a1, 1);
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v25 = rand();
      if ( v25 == 5 * (v25 / 5) )
        Spinlock<26,1,268435713>::UpdateStatSnapshot();
    }
    *v31 = 0;
    v31 = 0;
    v32 = 0;
    SOS_Task::PreWait(a4);
    v11 = SOS_Scheduler::Suspend(a2, v12);
    SOS_Task::PostWait(a4, v11);
    WorkerWaitContext::NotifyDoneWaiting(v36);
    a2[21] = 0;
    *(_DWORD *)(v15 + 616) &= ~v33;
    if ( !v11 )
    {
      v27 = ++v8;
      v9 = *(_QWORD *)(a1 + 32);
      v7 = v35;
      v4 = a3;
      continue;
    }
    break;
  }
LABEL_48:
  if ( v24 )
  {
    *(_DWORD *)(*((_QWORD *)v24 + 1) + 800LL) &= ~0x800000u;
    WorkerWaitContext::NotifyDoneWaiting(v24);
  }
  return v11;
}

```

## disassembly

```asm
0x10045eb60  mov     [rsp-40h+arg_18], r9
0x10045eb65  mov     [rsp-40h+arg_10], r8d
0x10045eb6a  push    rbp
0x10045eb6b  push    rbx
0x10045eb6c  push    rsi
0x10045eb6d  push    rdi
0x10045eb6e  push    r12
0x10045eb70  push    r13
0x10045eb72  push    r14
0x10045eb74  push    r15
0x10045eb76  mov     rbp, rsp
0x10045eb79  sub     rsp, 78h
0x10045eb7d  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x10045eb85  mov     r15d, r8d
0x10045eb88  mov     r13, rdx
0x10045eb8b  mov     rsi, rcx
0x10045eb8e  xor     r14d, r14d
0x10045eb91  mov     [rbp+arg_0], r14d
0x10045eb95  xor     r12d, r12d
0x10045eb98  mov     [rbp+var_58], r12
0x10045eb9c  lea     rax, [rdx+3F0h]
0x10045eba3  test    rax, rax
0x10045eba6  jz      short loc_10045EBBC
0x10045eba8  mov     [rbp+arg_8], rax
0x10045ebac  mov     rax, [rax+8]
0x10045ebb0  or      dword ptr [rax+320h], 800000h
0x10045ebba  jmp     short loc_10045EBC0
0x10045ebbc  mov     [rbp+arg_8], r12
0x10045ebc0  mov     rax, [rcx+20h]
0x10045ebc4  test    rax, rax
0x10045ebc7  setz    bl
0x10045ebca  nop     word ptr [rax+rax+00h]
0x10045ebd0  test    bl, bl
0x10045ebd2  jz      short loc_10045EC14
0x10045ebd4  xor     edi, edi
0x10045ebd6  xor     eax, eax
0x10045ebd8  lock cmpxchg [rsi+20h], r13
0x10045ebde  jnz     short loc_10045EC07
0x10045ebe0  mov     rax, [r13+260h]
0x10045ebe7  mov     [rsi+30h], rax
0x10045ebeb  mov     qword ptr [rsi+38h], 1
0x10045ebf3  mov     rax, [r13+258h]
0x10045ebfa  mov     [rsi+28h], rax
0x10045ebfe  mov     [r13+0A8h], rdi
0x10045ec05  jmp     short loc_10045EC0C
0x10045ec07  mov     edi, 80000000h
0x10045ec0c  test    edi, edi
0x10045ec0e  jz      loc_10045EF0D
0x10045ec14  mov     edi, 0FFFFFFFFh
0x10045ec19  cmp     r15d, edi
0x10045ec1c  jz      short loc_10045EC4B
0x10045ec1e  call    cs:__imp_GetTickCount
0x10045ec24  test    r12, r12
0x10045ec27  cmovz   r14d, eax
0x10045ec2b  mov     [rbp+arg_0], r14d
0x10045ec2f  mov     ecx, eax
0x10045ec31  sub     ecx, r14d
0x10045ec34  cmp     r15d, ecx
0x10045ec37  jbe     loc_10045EF08
0x10045ec3d  mov     edi, r14d
0x10045ec40  sub     edi, eax
0x10045ec42  add     edi, r15d
0x10045ec45  jz      loc_10045EF08
0x10045ec4b  mov     [rbp+var_20], 0
0x10045ec52  mov     rdx, gs:58h
0x10045ec5b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10045ec62  mov     ecx, [rax]
0x10045ec64  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10045ec6b  mov     ebx, [rax]
0x10045ec6d  add     rbx, [rdx+rcx*8]
0x10045ec71  mov     r14, [rbx+100h]
0x10045ec78  test    r14, r14
0x10045ec7b  jnz     short loc_10045EC8C
0x10045ec7d  xor     ecx, ecx
0x10045ec7f  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10045ec85  mov     r14, [rbx+100h]
0x10045ec8c  mov     [rbp+var_18], r14
0x10045ec90  mov     ecx, [r14+268h]
0x10045ec97  mov     eax, ecx
0x10045ec99  and     eax, 1
0x10045ec9c  xor     eax, 1
0x10045ec9f  mov     [rbp+var_20], eax
0x10045eca2  or      ecx, 1
0x10045eca5  mov     [r14+268h], ecx
0x10045ecac  lea     rax, [rsi+18h]
0x10045ecb0  mov     [rbp+var_30], rax
0x10045ecb4  mov     [rbp+var_28], 0
0x10045ecbb  mov     eax, gs:48h
0x10045ecc3  mov     r15d, eax
0x10045ecc6  mov     rax, [rbp+var_30]
0x10045ecca  mov     ecx, [rax]
0x10045eccc  test    ecx, ecx
0x10045ecce  jnz     short loc_10045ECEB
0x10045ecd0  mov     rcx, [rbp+var_30]
0x10045ecd4  xor     eax, eax
0x10045ecd6  lock cmpxchg [rcx], r15
0x10045ecdb  mov     eax, 0
0x10045ece0  setz    al
0x10045ece3  test    eax, eax
0x10045ece5  jnz     loc_10045EDCC
0x10045eceb  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10045ecf2  mov     ecx, [rax]
0x10045ecf4  and     ecx, 84h
0x10045ecfa  cmp     cl, 84h
0x10045ecfd  jnz     loc_10045EDC0
0x10045ed03  xor     r12d, r12d
0x10045ed06  mov     rdx, gs:58h
0x10045ed0f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10045ed16  mov     ecx, [rax]
0x10045ed18  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10045ed1f  mov     r8d, [rax]
0x10045ed22  add     r8, [rdx+rcx*8]
0x10045ed26  jz      short loc_10045ED38
0x10045ed28  cmp     [r8+110h], r8
0x10045ed2f  jnz     short loc_10045ED38
0x10045ed31  mov     r12, [r8+100h]
0x10045ed38  test    r12, r12
0x10045ed3b  jz      short loc_10045EDAE
0x10045ed3d  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10045ed44  cmp     dword ptr [rax], 0
0x10045ed47  jz      short loc_10045ED59
0x10045ed49  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x10045ed4d  call    cs:__imp_QueryPerformanceCounter
0x10045ed53  mov     rbx, qword ptr [rbp+PerformanceCount]
0x10045ed57  jmp     short loc_10045ED61
0x10045ed59  mov     rbx, ds:7FFE0008h
0x10045ed61  mov     rdx, r15
0x10045ed64  mov     rcx, [rbp+var_30]
0x10045ed68  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BK@$00$0BAAAABAB@@@AEAAX_K@Z; Spinlock<26,1,268435713>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10045ed6d  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10045ed74  cmp     dword ptr [rax], 0
0x10045ed77  jz      short loc_10045ED89
0x10045ed79  lea     rcx, [rbp+var_48]; lpPerformanceCount
0x10045ed7d  call    cs:__imp_QueryPerformanceCounter
0x10045ed83  mov     rcx, qword ptr [rbp+var_48]
0x10045ed87  jmp     short loc_10045ED91
0x10045ed89  mov     rcx, ds:7FFE0008h
0x10045ed91  mov     rdx, rcx
0x10045ed94  sub     rdx, rbx
0x10045ed97  xor     eax, eax
0x10045ed99  cmp     rcx, rbx
0x10045ed9c  cmovnb  rax, rdx
0x10045eda0  add     [r12+0C78h], rax
0x10045eda8  mov     r12, [rbp+var_58]
0x10045edac  jmp     short loc_10045EDCC
0x10045edae  mov     rdx, r15
0x10045edb1  mov     rcx, [rbp+var_30]
0x10045edb5  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BK@$00$0BAAAABAB@@@AEAAX_K@Z; Spinlock<26,1,268435713>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10045edba  mov     r12, [rbp+var_58]
0x10045edbe  jmp     short loc_10045EDCC
0x10045edc0  mov     rdx, r15
0x10045edc3  mov     rcx, [rbp+var_30]
0x10045edc7  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BK@$00$0BAAAABAB@@@AEAAX_K@Z; Spinlock<26,1,268435713>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10045edcc  mov     [rbp+var_28], 1
0x10045edd3  mov     rax, [rsi+20h]
0x10045edd7  test    rax, rax
0x10045edda  jnz     short loc_10045EE44
0x10045eddc  mov     bl, 1
0x10045edde  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10045ede5  cmp     byte ptr [rax], 0
0x10045ede8  jz      short loc_10045EE11
0x10045edea  call    cs:__imp_rand
0x10045edf0  mov     r8d, eax
0x10045edf3  mov     eax, 66666667h
0x10045edf8  imul    r8d
0x10045edfb  sar     edx, 1
0x10045edfd  mov     ecx, edx
0x10045edff  shr     ecx, 1Fh
0x10045ee02  add     edx, ecx
0x10045ee04  lea     ecx, [rdx+rdx*4]
0x10045ee07  cmp     r8d, ecx
0x10045ee0a  jnz     short loc_10045EE11
0x10045ee0c  call    ?UpdateStatSnapshot@?$Spinlock@$0BK@$00$0BAAAABAB@@@AEAAXXZ; Spinlock<26,1,268435713>::UpdateStatSnapshot(void)
0x10045ee11  mov     rax, [rbp+var_30]
0x10045ee15  mov     qword ptr [rax], 0
0x10045ee1c  mov     [rbp+var_30], 0
0x10045ee24  mov     [rbp+var_28], 0
0x10045ee2b  mov     eax, [rbp+var_20]
0x10045ee2e  not     eax
0x10045ee30  and     [r14+268h], eax
0x10045ee37  mov     r14d, [rbp+arg_0]
0x10045ee3b  mov     r15d, [rbp+arg_10]
0x10045ee3f  jmp     loc_10045EBD0
0x10045ee44  lea     rax, [rsi+28h]
0x10045ee48  mov     [r13+0A8h], rax
0x10045ee4f  mov     r8d, 1
0x10045ee55  mov     rdx, rsi
0x10045ee58  mov     rbx, [rbp+arg_8]
0x10045ee5c  mov     rcx, rbx
0x10045ee5f  call    cs:__imp_?EnqueueWait@WorkerWaitContext@@QEAAXPEAVMinWaitableBase@@W4SOS_QUEUE_PLACE@@@Z; WorkerWaitContext::EnqueueWait(MinWaitableBase *,SOS_QUEUE_PLACE)
0x10045ee65  nop
0x10045ee66  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10045ee6d  cmp     byte ptr [rax], 0
0x10045ee70  jz      short loc_10045EE99
0x10045ee72  call    cs:__imp_rand
0x10045ee78  mov     r8d, eax
0x10045ee7b  mov     eax, 66666667h
0x10045ee80  imul    r8d
0x10045ee83  sar     edx, 1
0x10045ee85  mov     ecx, edx
0x10045ee87  shr     ecx, 1Fh
0x10045ee8a  add     edx, ecx
0x10045ee8c  lea     ecx, [rdx+rdx*4]
0x10045ee8f  cmp     r8d, ecx
0x10045ee92  jnz     short loc_10045EE99
0x10045ee94  call    ?UpdateStatSnapshot@?$Spinlock@$0BK@$00$0BAAAABAB@@@AEAAXXZ; Spinlock<26,1,268435713>::UpdateStatSnapshot(void)
0x10045ee99  mov     rax, [rbp+var_30]
0x10045ee9d  xor     ecx, ecx
0x10045ee9f  mov     [rax], rcx
0x10045eea2  mov     [rbp+var_30], rcx
0x10045eea6  mov     [rbp+var_28], ecx
0x10045eea9  mov     rcx, [rbp+arg_18]
0x10045eead  call    cs:__imp_?PreWait@SOS_Task@@SAXPEBVSOS_WaitInfo@@@Z; SOS_Task::PreWait(SOS_WaitInfo const *)
0x10045eeb3  mov     edx, edi
0x10045eeb5  mov     rcx, r13
0x10045eeb8  call    cs:__imp_?Suspend@SOS_Scheduler@@SA?AW4SOS_RESULT@@PEAVWorker@@K@Z; SOS_Scheduler::Suspend(Worker *,ulong)
0x10045eebe  mov     edi, eax
0x10045eec0  mov     edx, eax
0x10045eec2  mov     rcx, [rbp+arg_18]
0x10045eec6  call    cs:__imp_?PostWait@SOS_Task@@SAXPEBVSOS_WaitInfo@@W4SOS_RESULT@@@Z; SOS_Task::PostWait(SOS_WaitInfo const *,SOS_RESULT)
0x10045eecc  mov     rcx, rbx
0x10045eecf  call    cs:__imp_?NotifyDoneWaiting@WorkerWaitContext@@QEAAXXZ; WorkerWaitContext::NotifyDoneWaiting(void)
0x10045eed5  mov     qword ptr [r13+0A8h], 0
0x10045eee0  mov     ecx, [rbp+var_20]
0x10045eee3  not     ecx
0x10045eee5  and     [r14+268h], ecx
0x10045eeec  test    edi, edi
0x10045eeee  jnz     short loc_10045EF11
0x10045eef0  inc     r12
0x10045eef3  mov     [rbp+var_58], r12
0x10045eef7  mov     rax, [rsi+20h]
0x10045eefb  mov     r14d, [rbp+arg_0]
0x10045eeff  mov     r15d, [rbp+arg_10]
0x10045ef03  jmp     loc_10045EBC4
0x10045ef08  mov     edi, 102h
0x10045ef0d  mov     rbx, [rbp+arg_8]
0x10045ef11  test    rbx, rbx
0x10045ef14  jz      short loc_10045EF2D
0x10045ef16  mov     rax, [rbx+8]
0x10045ef1a  and     dword ptr [rax+320h], 0FF7FFFFFh
0x10045ef24  mov     rcx, rbx
0x10045ef27  call    cs:__imp_?NotifyDoneWaiting@WorkerWaitContext@@QEAAXXZ; WorkerWaitContext::NotifyDoneWaiting(void)
0x10045ef2d  mov     eax, edi
0x10045ef2f  add     rsp, 78h
0x10045ef33  pop     r15
0x10045ef35  pop     r14
0x10045ef37  pop     r13
0x10045ef39  pop     r12
0x10045ef3b  pop     rdi
0x10045ef3c  pop     rsi
0x10045ef3d  pop     rbx
0x10045ef3e  pop     rbp
0x10045ef3f  retn
```
