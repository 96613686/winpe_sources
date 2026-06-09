# EventAutoInternal<SuspendQueueSLock>::SignalAll(void)

- ea: `0x10040d680`
- end: `0x10040d896`
- name: `?SignalAll@?$EventAutoInternal@USuspendQueueSLock@@@@QEAAXXZ`
- size: `534`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `14`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1004089b0`
- `0x100409670`
- `0x100413220`
- `0x100413480`
- `0x1004704c0`
- `0x100470fe0`
- `0x100471430`
- `0x100472000`
- `0x100472490`
- `0x100473980`
- `0x1004739f0`
- `0x100475c00`
- `0x100475fd0`
- `0x10047ef60`

## callees

- `0x100402330`
- `0x100402570`
- `0x100402820`
- `0x10040d680`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10040d746`
- `KERNEL32!QueryPerformanceCounter` at `0x10040d79f`
- `KERNEL32!QueryPerformanceCounter` at `0x10040d746`
- `KERNEL32!QueryPerformanceCounter` at `0x10040d79f`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040d832`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040d733`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040d78b`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10040d75e`
- `sqldk!?SignalAndResumeBulk@SOS_Scheduler@@SAXPEAVWorkerWaitQueue@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z` at `0x10040d87c`
- `sqldk!?SignalAndResumeBulk@SOS_Scheduler@@SAXPEAVWorkerWaitQueue@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z` at `0x10040d87c`
- `sqldk!SystemThread_TlsIndex` at `0x10040d705`
- `sqldk!SystemThread_TlsOffset` at `0x10040d70e`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040d6e5`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040d83e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040d83e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EventAutoInternal<SuspendQueueSLock>::SignalAll(__int64 a1)
{
  volatile signed __int64 *v2; // rsi
  LARGE_INTEGER v3; // rbx
  signed __int64 UniqueThread_low; // r14
  __int64 v5; // rdi
  __int64 v6; // r8
  LARGE_INTEGER v7; // rax
  LONGLONG v8; // rcx
  int v9; // r8d
  __int64 *v10; // rdx
  _QWORD *v11; // rbx
  int v12; // eax
  __int64 v14; // [rsp+28h] [rbp-50h] BYREF
  __int64 *v15; // [rsp+30h] [rbp-48h]
  _QWORD *v16; // [rsp+38h] [rbp-40h]
  int v17; // [rsp+40h] [rbp-38h]
  LARGE_INTEGER PerformanceCount; // [rsp+80h] [rbp+8h] BYREF
  LARGE_INTEGER v19; // [rsp+88h] [rbp+10h] BYREF

  v15 = &v14;
  v14 = (__int64)&v14;
  v2 = (volatile signed __int64 *)(a1 + 24);
  v16 = (_QWORD *)(a1 + 24);
  v17 = 0;
  v3.QuadPart = 0;
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( *(_DWORD *)(a1 + 24) || _InterlockedCompareExchange64(v2, UniqueThread_low, 0) )
  {
    v5 = 0;
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
    {
      v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( v6 && *(_QWORD *)(v6 + 272) == v6 )
        v5 = *(_QWORD *)(v6 + 256);
      if ( v5 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v3 = PerformanceCount;
        }
        else
        {
          v3.QuadPart = MEMORY[0x7FFE0008];
        }
      }
    }
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(v2, UniqueThread_low);
    else
      Spinlock<25,1,268435714>::SpinToAcquireOptimistic(v2, v5, UniqueThread_low);
    if ( v5 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v19);
        v7 = v19;
      }
      else
      {
        v7.QuadPart = MEMORY[0x7FFE0008];
      }
      v8 = v7.QuadPart - v3.QuadPart;
      if ( v7.QuadPart < (unsigned __int64)v3.QuadPart )
        v8 = 0;
      *(_QWORD *)(v5 + 3192) += v8;
    }
  }
  v9 = 1;
  v17 = 1;
  v10 = (__int64 *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 16) != a1 + 8 )
  {
    *(_QWORD *)(*v10 + 8) = v15;
    *v15 = *v10;
    v15 = *(__int64 **)(a1 + 16);
    *v15 = (__int64)&v14;
    *(_QWORD *)(a1 + 16) = a1 + 8;
    *v10 = (__int64)v10;
  }
  if ( v15 == &v14 )
    *(_QWORD *)(a1 + 40) = 1;
  else
    v9 = 0;
  *(_DWORD *)(a1 + 32) = v9;
  v11 = v16;
  if ( v16 )
  {
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v12 = rand();
      if ( v12 == 5 * (v12 / 5) )
        Spinlock<25,1,268435714>::UpdateStatSnapshot();
    }
    *v11 = 0;
    v16 = 0;
    v17 = 0;
  }
  return SOS_Scheduler::SignalAndResumeBulk(&v14, 0, 0);
}

```

## disassembly

```asm
0x10040d680  mov     r11, rsp
0x10040d683  push    rbp
0x10040d684  push    rsi
0x10040d685  push    rdi
0x10040d686  push    r14
0x10040d688  push    r15
0x10040d68a  sub     rsp, 50h
0x10040d68e  mov     qword ptr [r11-58h], 0FFFFFFFFFFFFFFFEh
0x10040d696  mov     [r11+20h], rbx
0x10040d69a  mov     rbp, rcx
0x10040d69d  lea     rax, [r11-50h]
0x10040d6a1  mov     [r11-48h], rax
0x10040d6a5  lea     rax, [r11-50h]
0x10040d6a9  mov     [r11-50h], rax
0x10040d6ad  lea     rsi, [rcx+18h]
0x10040d6b1  mov     [r11-40h], rsi
0x10040d6b5  xor     r15d, r15d
0x10040d6b8  mov     [r11-38h], r15d
0x10040d6bc  mov     ebx, r15d
0x10040d6bf  mov     eax, gs:48h
0x10040d6c7  mov     r14d, eax
0x10040d6ca  mov     eax, [rsi]
0x10040d6cc  test    eax, eax
0x10040d6ce  jnz     short loc_10040D6E5
0x10040d6d0  xor     eax, eax
0x10040d6d2  lock cmpxchg [rsi], r14
0x10040d6d7  mov     eax, r15d
0x10040d6da  setz    al
0x10040d6dd  test    eax, eax
0x10040d6df  jnz     loc_10040D7CB
0x10040d6e5  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040d6ec  mov     ecx, [rax]
0x10040d6ee  and     ecx, 84h
0x10040d6f4  mov     rdi, r15
0x10040d6f7  cmp     cl, 84h
0x10040d6fa  jnz     short loc_10040D75E
0x10040d6fc  mov     rdx, gs:58h
0x10040d705  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040d70c  mov     ecx, [rax]
0x10040d70e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040d715  mov     r8d, [rax]
0x10040d718  add     r8, [rdx+rcx*8]
0x10040d71c  jz      short loc_10040D72E
0x10040d71e  cmp     [r8+110h], r8
0x10040d725  jnz     short loc_10040D72E
0x10040d727  mov     rdi, [r8+100h]
0x10040d72e  test    rdi, rdi
0x10040d731  jz      short loc_10040D75E
0x10040d733  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040d73a  cmp     [rax], ebx
0x10040d73c  jz      short loc_10040D756
0x10040d73e  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x10040d746  call    cs:__imp_QueryPerformanceCounter
0x10040d74c  mov     rbx, qword ptr [rsp+78h+PerformanceCount]
0x10040d754  jmp     short loc_10040D75E
0x10040d756  mov     rbx, ds:7FFE0008h
0x10040d75e  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10040d765  mov     rcx, rsi
0x10040d768  cmp     byte ptr [rax+0C7h], 0
0x10040d76f  jge     short loc_10040D77E
0x10040d771  mov     r8, r14
0x10040d774  mov     rdx, rdi
0x10040d777  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<25,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10040d77c  jmp     short loc_10040D786
0x10040d77e  mov     rdx, r14
0x10040d781  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10040d786  test    rdi, rdi
0x10040d789  jz      short loc_10040D7CB
0x10040d78b  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040d792  cmp     dword ptr [rax], 0
0x10040d795  jz      short loc_10040D7AF
0x10040d797  lea     rcx, [rsp+78h+arg_8]; lpPerformanceCount
0x10040d79f  call    cs:__imp_QueryPerformanceCounter
0x10040d7a5  mov     rax, qword ptr [rsp+78h+arg_8]
0x10040d7ad  jmp     short loc_10040D7B7
0x10040d7af  mov     rax, ds:7FFE0008h
0x10040d7b7  mov     rcx, rax
0x10040d7ba  sub     rcx, rbx
0x10040d7bd  cmp     rax, rbx
0x10040d7c0  cmovb   rcx, r15
0x10040d7c4  add     [rdi+0C78h], rcx
0x10040d7cb  mov     r8d, 1
0x10040d7d1  mov     [rsp+78h+var_38], r8d
0x10040d7d6  lea     rdx, [rbp+8]
0x10040d7da  cmp     [rdx+8], rdx
0x10040d7de  jz      short loc_10040D80F
0x10040d7e0  mov     rcx, [rdx]
0x10040d7e3  mov     rax, [rsp+78h+var_48]
0x10040d7e8  mov     [rcx+8], rax
0x10040d7ec  mov     rcx, [rdx]
0x10040d7ef  mov     rax, [rsp+78h+var_48]
0x10040d7f4  mov     [rax], rcx
0x10040d7f7  mov     rax, [rdx+8]
0x10040d7fb  mov     [rsp+78h+var_48], rax
0x10040d800  lea     rcx, [rsp+78h+var_50]
0x10040d805  mov     [rax], rcx
0x10040d808  mov     [rdx+8], rdx
0x10040d80c  mov     [rdx], rdx
0x10040d80f  lea     rax, [rsp+78h+var_50]
0x10040d814  cmp     [rsp+78h+var_48], rax
0x10040d819  jnz     short loc_10040D821
0x10040d81b  mov     [rbp+28h], r8
0x10040d81f  jmp     short loc_10040D824
0x10040d821  mov     r8d, r15d
0x10040d824  mov     [rbp+20h], r8d
0x10040d828  mov     rbx, [rsp+78h+var_40]
0x10040d82d  test    rbx, rbx
0x10040d830  jz      short loc_10040D872
0x10040d832  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10040d839  cmp     byte ptr [rax], 0
0x10040d83c  jz      short loc_10040D865
0x10040d83e  call    cs:__imp_rand
0x10040d844  mov     r8d, eax
0x10040d847  mov     eax, 66666667h
0x10040d84c  imul    r8d
0x10040d84f  sar     edx, 1
0x10040d851  mov     ecx, edx
0x10040d853  shr     ecx, 1Fh
0x10040d856  add     edx, ecx
0x10040d858  lea     ecx, [rdx+rdx*4]
0x10040d85b  cmp     r8d, ecx
0x10040d85e  jnz     short loc_10040D865
0x10040d860  call    ?UpdateStatSnapshot@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<25,1,268435714>::UpdateStatSnapshot(void)
0x10040d865  mov     [rbx], r15
0x10040d868  mov     [rsp+78h+var_40], r15
0x10040d86d  mov     [rsp+78h+var_38], r15d
0x10040d872  xor     r8d, r8d
0x10040d875  xor     edx, edx
0x10040d877  lea     rcx, [rsp+78h+var_50]
0x10040d87c  call    cs:__imp_?SignalAndResumeBulk@SOS_Scheduler@@SAXPEAVWorkerWaitQueue@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z; SOS_Scheduler::SignalAndResumeBulk(WorkerWaitQueue *,SOS_QUEUE_PLACE,SOS_RESULT)
0x10040d882  mov     rbx, [rsp+78h+arg_18]
0x10040d88a  add     rsp, 50h
0x10040d88e  pop     r15
0x10040d890  pop     r14
0x10040d892  pop     rdi
0x10040d893  pop     rsi
0x10040d894  pop     rbp
0x10040d895  retn
```
