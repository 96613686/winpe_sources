# LockedWaitQueue<WaitableBase,SuspendQueueSLock>::RemoveFromWaitQueue(WorkerWaitElem *)

- ea: `0x10040a290`
- end: `0x10040a47f`
- name: `?RemoveFromWaitQueue@?$LockedWaitQueue@VWaitableBase@@USuspendQueueSLock@@@@UEAA?AW4SOS_RESULT@@PEAVWorkerWaitElem@@@Z`
- size: `495`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x10040a290`
- `0x10040a5c0`
- `0x10040a800`
- `0x10040aab0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10040a349`
- `KERNEL32!QueryPerformanceCounter` at `0x10040a3a2`
- `KERNEL32!QueryPerformanceCounter` at `0x10040a349`
- `KERNEL32!QueryPerformanceCounter` at `0x10040a3a2`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10040a361`
- `sqldk!SystemThread_TlsOffset` at `0x10040a311`
- `sqldk!SystemThread_TlsIndex` at `0x10040a308`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040a336`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040a38e`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040a42e`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040a2e8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040a43a`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040a43a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LockedWaitQueue<WaitableBase,SuspendQueueSLock>::RemoveFromWaitQueue(__int64 a1, __int64 *a2)
{
  volatile signed __int64 *v4; // rsi
  LARGE_INTEGER v5; // rbx
  signed __int64 UniqueThread_low; // r14
  __int64 v7; // rdi
  __int64 v8; // r8
  LARGE_INTEGER v9; // rcx
  LONGLONG v10; // rax
  __int64 *v11; // rdx
  _QWORD *v12; // rcx
  __int64 v13; // rax
  unsigned int v14; // ebx
  int v15; // eax
  _QWORD *v17; // [rsp+28h] [rbp-50h]
  LARGE_INTEGER PerformanceCount; // [rsp+80h] [rbp+8h] BYREF
  LARGE_INTEGER v19; // [rsp+90h] [rbp+18h] BYREF

  v4 = (volatile signed __int64 *)(a1 + 24);
  v17 = (_QWORD *)(a1 + 24);
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
        QueryPerformanceCounter(&v19);
        v9 = v19;
      }
      else
      {
        v9.QuadPart = MEMORY[0x7FFE0008];
      }
      v10 = 0;
      if ( v9.QuadPart >= (unsigned __int64)v5.QuadPart )
        v10 = v9.QuadPart - v5.QuadPart;
      *(_QWORD *)(v7 + 3192) += v10;
    }
  }
  v11 = *(__int64 **)(a1 + 16);
  if ( v11 == (__int64 *)(a1 + 8) )
  {
    v11 = 0;
  }
  else
  {
    while ( v11 )
    {
      if ( v11 == a2 )
      {
        v12 = (_QWORD *)v11[1];
        v13 = *v11;
        *(_QWORD *)(v13 + 8) = v12;
        *v12 = v13;
        v11[1] = 0;
        *v11 = 0;
        break;
      }
      v11 = (__int64 *)v11[1];
      if ( v11 == (__int64 *)(a1 + 8) )
      {
        v11 = 0;
        break;
      }
    }
  }
  v14 = 0x80000000;
  if ( v11 )
    v14 = 0;
  if ( v17 )
  {
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v15 = rand();
      if ( v15 == 5 * (v15 / 5) )
        Spinlock<25,1,268435714>::UpdateStatSnapshot();
    }
    *v17 = 0;
  }
  return v14;
}

```

## disassembly

```asm
0x10040a290  push    rbx
0x10040a292  push    rbp
0x10040a293  push    rsi
0x10040a294  push    rdi
0x10040a295  push    r12
0x10040a297  push    r14
0x10040a299  push    r15
0x10040a29b  sub     rsp, 40h
0x10040a29f  mov     [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh
0x10040a2a8  mov     rbp, rdx
0x10040a2ab  mov     r15, rcx
0x10040a2ae  lea     rsi, [rcx+18h]
0x10040a2b2  mov     [rsp+78h+var_50], rsi
0x10040a2b7  xor     r12d, r12d
0x10040a2ba  mov     [rsp+78h+var_48], r12d
0x10040a2bf  mov     ebx, r12d
0x10040a2c2  mov     eax, gs:48h
0x10040a2ca  mov     r14d, eax
0x10040a2cd  mov     eax, [rsi]
0x10040a2cf  test    eax, eax
0x10040a2d1  jnz     short loc_10040A2E8
0x10040a2d3  xor     eax, eax
0x10040a2d5  lock cmpxchg [rsi], r14
0x10040a2da  mov     eax, r12d
0x10040a2dd  setz    al
0x10040a2e0  test    eax, eax
0x10040a2e2  jnz     loc_10040A3D1
0x10040a2e8  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040a2ef  mov     ecx, [rax]
0x10040a2f1  and     ecx, 84h
0x10040a2f7  mov     rdi, r12
0x10040a2fa  cmp     cl, 84h
0x10040a2fd  jnz     short loc_10040A361
0x10040a2ff  mov     rdx, gs:58h
0x10040a308  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040a30f  mov     ecx, [rax]
0x10040a311  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040a318  mov     r8d, [rax]
0x10040a31b  add     r8, [rdx+rcx*8]
0x10040a31f  jz      short loc_10040A331
0x10040a321  cmp     [r8+110h], r8
0x10040a328  jnz     short loc_10040A331
0x10040a32a  mov     rdi, [r8+100h]
0x10040a331  test    rdi, rdi
0x10040a334  jz      short loc_10040A361
0x10040a336  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040a33d  cmp     [rax], ebx
0x10040a33f  jz      short loc_10040A359
0x10040a341  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x10040a349  call    cs:__imp_QueryPerformanceCounter
0x10040a34f  mov     rbx, qword ptr [rsp+78h+PerformanceCount]
0x10040a357  jmp     short loc_10040A361
0x10040a359  mov     rbx, ds:7FFE0008h
0x10040a361  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10040a368  mov     rcx, rsi
0x10040a36b  cmp     byte ptr [rax+0C7h], 0
0x10040a372  jge     short loc_10040A381
0x10040a374  mov     r8, r14
0x10040a377  mov     rdx, rdi
0x10040a37a  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<25,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10040a37f  jmp     short loc_10040A389
0x10040a381  mov     rdx, r14
0x10040a384  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10040a389  test    rdi, rdi
0x10040a38c  jz      short loc_10040A3D1
0x10040a38e  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040a395  cmp     dword ptr [rax], 0
0x10040a398  jz      short loc_10040A3B2
0x10040a39a  lea     rcx, [rsp+78h+arg_10]; lpPerformanceCount
0x10040a3a2  call    cs:__imp_QueryPerformanceCounter
0x10040a3a8  mov     rcx, qword ptr [rsp+78h+arg_10]
0x10040a3b0  jmp     short loc_10040A3BA
0x10040a3b2  mov     rcx, ds:7FFE0008h
0x10040a3ba  mov     rdx, rcx
0x10040a3bd  sub     rdx, rbx
0x10040a3c0  mov     rax, r12
0x10040a3c3  cmp     rcx, rbx
0x10040a3c6  cmovnb  rax, rdx
0x10040a3ca  add     [rdi+0C78h], rax
0x10040a3d1  mov     [rsp+78h+var_48], 1
0x10040a3d9  lea     rax, [r15+8]
0x10040a3dd  mov     rdx, [rax+8]
0x10040a3e1  cmp     rdx, rax
0x10040a3e4  jnz     short loc_10040A3EB
0x10040a3e6  mov     rdx, r12
0x10040a3e9  jmp     short loc_10040A418
0x10040a3eb  test    rdx, rdx
0x10040a3ee  jz      short loc_10040A418
0x10040a3f0  cmp     rdx, rbp
0x10040a3f3  jz      short loc_10040A403
0x10040a3f5  mov     rdx, [rdx+8]
0x10040a3f9  cmp     rdx, rax
0x10040a3fc  jnz     short loc_10040A3EB
0x10040a3fe  mov     rdx, r12
0x10040a401  jmp     short loc_10040A418
0x10040a403  mov     rcx, [rdx+8]
0x10040a407  mov     rax, [rdx]
0x10040a40a  mov     [rax+8], rcx
0x10040a40e  mov     [rcx], rax
0x10040a411  mov     [rdx+8], r12
0x10040a415  mov     [rdx], r12
0x10040a418  mov     ebx, 80000000h
0x10040a41d  test    rdx, rdx
0x10040a420  cmovnz  ebx, r12d
0x10040a424  mov     rdi, [rsp+78h+var_50]
0x10040a429  test    rdi, rdi
0x10040a42c  jz      short loc_10040A46E
0x10040a42e  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10040a435  cmp     byte ptr [rax], 0
0x10040a438  jz      short loc_10040A461
0x10040a43a  call    cs:__imp_rand
0x10040a440  mov     r8d, eax
0x10040a443  mov     eax, 66666667h
0x10040a448  imul    r8d
0x10040a44b  sar     edx, 1
0x10040a44d  mov     ecx, edx
0x10040a44f  shr     ecx, 1Fh
0x10040a452  add     edx, ecx
0x10040a454  lea     ecx, [rdx+rdx*4]
0x10040a457  cmp     r8d, ecx
0x10040a45a  jnz     short loc_10040A461
0x10040a45c  call    ?UpdateStatSnapshot@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<25,1,268435714>::UpdateStatSnapshot(void)
0x10040a461  mov     [rdi], r12
0x10040a464  mov     [rsp+78h+var_50], r12
0x10040a469  mov     [rsp+78h+var_48], r12d
0x10040a46e  mov     eax, ebx
0x10040a470  add     rsp, 40h
0x10040a474  pop     r15
0x10040a476  pop     r14
0x10040a478  pop     r12
0x10040a47a  pop     rdi
0x10040a47b  pop     rsi
0x10040a47c  pop     rbp
0x10040a47d  pop     rbx
0x10040a47e  retn
```
