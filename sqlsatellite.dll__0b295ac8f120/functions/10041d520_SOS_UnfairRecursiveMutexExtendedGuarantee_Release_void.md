# SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)

- ea: `0x10041d520`
- end: `0x10041d743`
- name: `?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ`
- size: `547`
- prototype: `void __fastcall(SOS_UnfairRecursiveMutexExtendedGuarantee *__hidden this)`
- caller_count: `65`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x100421be0`
- `0x100426760`
- `0x1004269b0`
- `0x100427e60`
- `0x100428450`
- `0x100428e20`
- `0x10042c7f0`
- `0x10042ca80`
- `0x10042cd20`
- `0x10042cf60`
- `0x10042d3c0`
- `0x10042dd60`
- `0x10042e120`
- `0x10042e690`
- `0x10042eed0`
- `0x10042f890`
- `0x10042fa70`
- `0x10042fdb0`
- `0x100430130`
- `0x100430970`
- `0x100430e50`
- `0x100431170`
- `0x100431af0`
- `0x100431f20`
- `0x100432600`
- `0x100432820`
- `0x100433010`
- `0x100433110`
- `0x100433340`
- `0x100433440`
- `0x100433a70`
- `0x10043a0f0`
- `0x10043ff90`
- `0x100442df0`
- `0x100443700`
- `0x100444130`
- `0x1004447d0`
- `0x100444980`
- `0x1004454b0`
- `0x100445880`
- `0x100445bc0`
- `0x100446500`
- `0x100446730`
- `0x1004490f0`
- `0x1004494a0`
- `0x100449680`
- `0x10044a0a0`
- `0x10044a530`
- `0x10044a720`
- `0x10044a8c0`

## callees

- `0x100402330`
- `0x100402570`
- `0x100402820`
- `0x10041d520`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10041d623`
- `KERNEL32!QueryPerformanceCounter` at `0x10041d677`
- `KERNEL32!QueryPerformanceCounter` at `0x10041d623`
- `KERNEL32!QueryPerformanceCounter` at `0x10041d677`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10041d6e8`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041d613`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041d666`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10041d638`
- `sqldk!?SignalAndResumeBulk@SOS_Scheduler@@SAXPEAVWorkerWaitQueue@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z` at `0x10041d72d`
- `sqldk!?SignalAndResumeBulk@SOS_Scheduler@@SAXPEAVWorkerWaitQueue@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z` at `0x10041d72d`
- `sqldk!SystemThread_TlsIndex` at `0x10041d532`
- `sqldk!SystemThread_TlsIndex` at `0x10041d5e5`
- `sqldk!SystemThread_TlsOffset` at `0x10041d53c`
- `sqldk!SystemThread_TlsOffset` at `0x10041d5ee`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041d556`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041d556`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10041d5c0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041d6f8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041d6f8`

## pseudocode

```c
void __fastcall SOS_UnfairRecursiveMutexExtendedGuarantee::Release(SOS_UnfairRecursiveMutexExtendedGuarantee *this)
{
  bool v2; // zf
  LARGE_INTEGER v3; // rbx
  signed __int64 UniqueThread_low; // rbp
  __int64 v5; // rsi
  __int64 v6; // r8
  char *v7; // rcx
  LARGE_INTEGER v8; // rax
  LONGLONG v9; // rcx
  char *v10; // rdx
  int v11; // r8d
  __int64 v12; // [rsp+20h] [rbp-38h] BYREF
  __int64 *v13; // [rsp+28h] [rbp-30h]
  LARGE_INTEGER PerformanceCount; // [rsp+60h] [rbp+8h] BYREF
  LARGE_INTEGER v15; // [rsp+68h] [rbp+10h] BYREF

  if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset
                  + 256LL) )
    SystemThread::MakeMiniSOSThread(0);
  v2 = (*((_QWORD *)this + 7))-- == 1;
  v13 = &v12;
  v12 = (__int64)&v12;
  if ( v2 )
  {
    *((_QWORD *)this + 5) = 0;
    v3.QuadPart = 0;
    UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *((_DWORD *)this + 6)
      || _InterlockedCompareExchange64((volatile signed __int64 *)this + 3, UniqueThread_low, 0) )
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
      v7 = (char *)this + 24;
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(v7, UniqueThread_low);
      else
        Spinlock<25,1,268435714>::SpinToAcquireOptimistic(v7, v5, UniqueThread_low);
      if ( v5 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v15);
          v8 = v15;
        }
        else
        {
          v8.QuadPart = MEMORY[0x7FFE0008];
        }
        v9 = v8.QuadPart - v3.QuadPart;
        if ( v8.QuadPart < (unsigned __int64)v3.QuadPart )
          v9 = 0;
        *(_QWORD *)(v5 + 3192) += v9;
      }
    }
    v10 = (char *)this + 8;
    if ( *((SOS_UnfairRecursiveMutexExtendedGuarantee **)this + 2) != (SOS_UnfairRecursiveMutexExtendedGuarantee *)((char *)this + 8) )
    {
      *(_QWORD *)(*(_QWORD *)v10 + 8LL) = v13;
      *v13 = *(_QWORD *)v10;
      v13 = (__int64 *)*((_QWORD *)this + 2);
      *v13 = (__int64)&v12;
      *((_QWORD *)this + 2) = (char *)this + 8;
      *(_QWORD *)v10 = v10;
    }
    *((_QWORD *)this + 4) = 0;
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v11 = rand();
      if ( v11 == 5 * (v11 / 5) )
        Spinlock<25,1,268435714>::UpdateStatSnapshot();
    }
    *((_QWORD *)this + 3) = 0;
    SOS_Scheduler::SignalAndResumeBulk(&v12, 0, 0);
  }
}

```

## disassembly

```asm
0x10041d520  push    rdi
0x10041d522  sub     rsp, 50h
0x10041d526  mov     r9, gs:58h
0x10041d52f  mov     rdi, rcx
0x10041d532  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041d539  mov     r8d, [rax]
0x10041d53c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041d543  mov     edx, [rax]
0x10041d545  mov     rax, [r9+r8*8]
0x10041d549  cmp     qword ptr [rax+rdx+100h], 0
0x10041d552  jnz     short loc_10041D55C
0x10041d554  xor     ecx, ecx
0x10041d556  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041d55c  sub     qword ptr [rdi+38h], 1
0x10041d561  lea     rax, [rsp+58h+var_38]
0x10041d566  mov     [rsp+58h+var_30], rax
0x10041d56b  lea     rax, [rsp+58h+var_38]
0x10041d570  mov     [rsp+58h+var_38], rax
0x10041d575  jnz     loc_10041D73D
0x10041d57b  mov     [rsp+58h+arg_18], rbx
0x10041d580  mov     [rsp+58h+var_10], rbp
0x10041d585  mov     [rsp+58h+var_20], r14
0x10041d58a  mov     [rsp+58h+var_28], r15
0x10041d58f  xor     r15d, r15d
0x10041d592  mov     [rdi+28h], r15
0x10041d596  mov     ebx, r15d
0x10041d599  mov     eax, gs:48h
0x10041d5a1  mov     ebp, eax
0x10041d5a3  mov     eax, [rdi+18h]
0x10041d5a6  test    eax, eax
0x10041d5a8  jnz     short loc_10041D5C0
0x10041d5aa  xor     eax, eax
0x10041d5ac  lock cmpxchg [rdi+18h], rbp
0x10041d5b2  mov     eax, r15d
0x10041d5b5  setz    al
0x10041d5b8  test    eax, eax
0x10041d5ba  jnz     loc_10041D6A5
0x10041d5c0  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10041d5c7  mov     [rsp+58h+var_18], rsi
0x10041d5cc  mov     rsi, r15
0x10041d5cf  mov     ecx, [rax]
0x10041d5d1  and     ecx, 84h
0x10041d5d7  cmp     cl, 84h
0x10041d5da  jnz     short loc_10041D638
0x10041d5dc  mov     rdx, gs:58h
0x10041d5e5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041d5ec  mov     ecx, [rax]
0x10041d5ee  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041d5f5  mov     r8d, [rax]
0x10041d5f8  add     r8, [rdx+rcx*8]
0x10041d5fc  jz      short loc_10041D60E
0x10041d5fe  cmp     [r8+110h], r8
0x10041d605  jnz     short loc_10041D60E
0x10041d607  mov     rsi, [r8+100h]
0x10041d60e  test    rsi, rsi
0x10041d611  jz      short loc_10041D638
0x10041d613  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10041d61a  cmp     [rax], ebx
0x10041d61c  jz      short loc_10041D630
0x10041d61e  lea     rcx, [rsp+58h+PerformanceCount]; lpPerformanceCount
0x10041d623  call    cs:__imp_QueryPerformanceCounter
0x10041d629  mov     rbx, qword ptr [rsp+58h+PerformanceCount]
0x10041d62e  jmp     short loc_10041D638
0x10041d630  mov     rbx, ds:7FFE0008h
0x10041d638  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10041d63f  lea     rcx, [rdi+18h]
0x10041d643  cmp     [rax+0C7h], r15b
0x10041d64a  jge     short loc_10041D659
0x10041d64c  mov     r8, rbp
0x10041d64f  mov     rdx, rsi
0x10041d652  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<25,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10041d657  jmp     short loc_10041D661
0x10041d659  mov     rdx, rbp
0x10041d65c  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10041d661  test    rsi, rsi
0x10041d664  jz      short loc_10041D6A0
0x10041d666  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10041d66d  cmp     [rax], r15d
0x10041d670  jz      short loc_10041D684
0x10041d672  lea     rcx, [rsp+58h+arg_8]; lpPerformanceCount
0x10041d677  call    cs:__imp_QueryPerformanceCounter
0x10041d67d  mov     rax, qword ptr [rsp+58h+arg_8]
0x10041d682  jmp     short loc_10041D68C
0x10041d684  mov     rax, ds:7FFE0008h
0x10041d68c  mov     rcx, rax
0x10041d68f  sub     rcx, rbx
0x10041d692  cmp     rax, rbx
0x10041d695  cmovb   rcx, r15
0x10041d699  add     [rsi+0C78h], rcx
0x10041d6a0  mov     rsi, [rsp+58h+var_18]
0x10041d6a5  mov     rbp, [rsp+58h+var_10]
0x10041d6aa  lea     rdx, [rdi+8]
0x10041d6ae  mov     rbx, [rsp+58h+arg_18]
0x10041d6b3  cmp     [rdx+8], rdx
0x10041d6b7  jz      short loc_10041D6E8
0x10041d6b9  mov     rcx, [rdx]
0x10041d6bc  mov     rax, [rsp+58h+var_30]
0x10041d6c1  mov     [rcx+8], rax
0x10041d6c5  mov     rax, [rsp+58h+var_30]
0x10041d6ca  mov     rcx, [rdx]
0x10041d6cd  mov     [rax], rcx
0x10041d6d0  lea     rcx, [rsp+58h+var_38]
0x10041d6d5  mov     rax, [rdx+8]
0x10041d6d9  mov     [rsp+58h+var_30], rax
0x10041d6de  mov     [rax], rcx
0x10041d6e1  mov     [rdx+8], rdx
0x10041d6e5  mov     [rdx], rdx
0x10041d6e8  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10041d6ef  mov     [rdi+20h], r15
0x10041d6f3  cmp     [rax], r15b
0x10041d6f6  jz      short loc_10041D71F
0x10041d6f8  call    cs:__imp_rand
0x10041d6fe  mov     r8d, eax
0x10041d701  mov     eax, 66666667h
0x10041d706  imul    r8d
0x10041d709  sar     edx, 1
0x10041d70b  mov     ecx, edx
0x10041d70d  shr     ecx, 1Fh
0x10041d710  add     edx, ecx
0x10041d712  lea     ecx, [rdx+rdx*4]
0x10041d715  cmp     r8d, ecx
0x10041d718  jnz     short loc_10041D71F
0x10041d71a  call    ?UpdateStatSnapshot@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<25,1,268435714>::UpdateStatSnapshot(void)
0x10041d71f  xor     r8d, r8d
0x10041d722  mov     [rdi+18h], r15
0x10041d726  xor     edx, edx
0x10041d728  lea     rcx, [rsp+58h+var_38]
0x10041d72d  call    cs:__imp_?SignalAndResumeBulk@SOS_Scheduler@@SAXPEAVWorkerWaitQueue@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z; SOS_Scheduler::SignalAndResumeBulk(WorkerWaitQueue *,SOS_QUEUE_PLACE,SOS_RESULT)
0x10041d733  mov     r15, [rsp+58h+var_28]
0x10041d738  mov     r14, [rsp+58h+var_20]
0x10041d73d  add     rsp, 50h
0x10041d741  pop     rdi
0x10041d742  retn
```
