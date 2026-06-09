# LockedWaitQueue<WaitableBase,SuspendQueueSLock>::RemoveFromWaitQueue(WorkerWaitElem *)

- ea: `0x100401e80`
- end: `0x10040206f`
- name: `?RemoveFromWaitQueue@?$LockedWaitQueue@VWaitableBase@@USuspendQueueSLock@@@@UEAA?AW4SOS_RESULT@@PEAVWorkerWaitElem@@@Z`
- size: `495`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x100401e80`
- `0x100402330`
- `0x100402570`
- `0x100402820`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100401f39`
- `KERNEL32!QueryPerformanceCounter` at `0x100401f92`
- `KERNEL32!QueryPerformanceCounter` at `0x100401f39`
- `KERNEL32!QueryPerformanceCounter` at `0x100401f92`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040201e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100401f26`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100401f7e`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100401f51`
- `sqldk!SystemThread_TlsIndex` at `0x100401ef8`
- `sqldk!SystemThread_TlsOffset` at `0x100401f01`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100401ed8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040202a`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040202a`

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
0x100401e80  push    rbx
0x100401e82  push    rbp
0x100401e83  push    rsi
0x100401e84  push    rdi
0x100401e85  push    r12
0x100401e87  push    r14
0x100401e89  push    r15
0x100401e8b  sub     rsp, 40h
0x100401e8f  mov     [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh
0x100401e98  mov     rbp, rdx
0x100401e9b  mov     r15, rcx
0x100401e9e  lea     rsi, [rcx+18h]
0x100401ea2  mov     [rsp+78h+var_50], rsi
0x100401ea7  xor     r12d, r12d
0x100401eaa  mov     [rsp+78h+var_48], r12d
0x100401eaf  mov     ebx, r12d
0x100401eb2  mov     eax, gs:48h
0x100401eba  mov     r14d, eax
0x100401ebd  mov     eax, [rsi]
0x100401ebf  test    eax, eax
0x100401ec1  jnz     short loc_100401ED8
0x100401ec3  xor     eax, eax
0x100401ec5  lock cmpxchg [rsi], r14
0x100401eca  mov     eax, r12d
0x100401ecd  setz    al
0x100401ed0  test    eax, eax
0x100401ed2  jnz     loc_100401FC1
0x100401ed8  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100401edf  mov     ecx, [rax]
0x100401ee1  and     ecx, 84h
0x100401ee7  mov     rdi, r12
0x100401eea  cmp     cl, 84h
0x100401eed  jnz     short loc_100401F51
0x100401eef  mov     rdx, gs:58h
0x100401ef8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100401eff  mov     ecx, [rax]
0x100401f01  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100401f08  mov     r8d, [rax]
0x100401f0b  add     r8, [rdx+rcx*8]
0x100401f0f  jz      short loc_100401F21
0x100401f11  cmp     [r8+110h], r8
0x100401f18  jnz     short loc_100401F21
0x100401f1a  mov     rdi, [r8+100h]
0x100401f21  test    rdi, rdi
0x100401f24  jz      short loc_100401F51
0x100401f26  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100401f2d  cmp     [rax], ebx
0x100401f2f  jz      short loc_100401F49
0x100401f31  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x100401f39  call    cs:__imp_QueryPerformanceCounter
0x100401f3f  mov     rbx, qword ptr [rsp+78h+PerformanceCount]
0x100401f47  jmp     short loc_100401F51
0x100401f49  mov     rbx, ds:7FFE0008h
0x100401f51  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100401f58  mov     rcx, rsi
0x100401f5b  cmp     byte ptr [rax+0C7h], 0
0x100401f62  jge     short loc_100401F71
0x100401f64  mov     r8, r14
0x100401f67  mov     rdx, rdi
0x100401f6a  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<25,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100401f6f  jmp     short loc_100401F79
0x100401f71  mov     rdx, r14
0x100401f74  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100401f79  test    rdi, rdi
0x100401f7c  jz      short loc_100401FC1
0x100401f7e  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100401f85  cmp     dword ptr [rax], 0
0x100401f88  jz      short loc_100401FA2
0x100401f8a  lea     rcx, [rsp+78h+arg_10]; lpPerformanceCount
0x100401f92  call    cs:__imp_QueryPerformanceCounter
0x100401f98  mov     rcx, qword ptr [rsp+78h+arg_10]
0x100401fa0  jmp     short loc_100401FAA
0x100401fa2  mov     rcx, ds:7FFE0008h
0x100401faa  mov     rdx, rcx
0x100401fad  sub     rdx, rbx
0x100401fb0  mov     rax, r12
0x100401fb3  cmp     rcx, rbx
0x100401fb6  cmovnb  rax, rdx
0x100401fba  add     [rdi+0C78h], rax
0x100401fc1  mov     [rsp+78h+var_48], 1
0x100401fc9  lea     rax, [r15+8]
0x100401fcd  mov     rdx, [rax+8]
0x100401fd1  cmp     rdx, rax
0x100401fd4  jnz     short loc_100401FDB
0x100401fd6  mov     rdx, r12
0x100401fd9  jmp     short loc_100402008
0x100401fdb  test    rdx, rdx
0x100401fde  jz      short loc_100402008
0x100401fe0  cmp     rdx, rbp
0x100401fe3  jz      short loc_100401FF3
0x100401fe5  mov     rdx, [rdx+8]
0x100401fe9  cmp     rdx, rax
0x100401fec  jnz     short loc_100401FDB
0x100401fee  mov     rdx, r12
0x100401ff1  jmp     short loc_100402008
0x100401ff3  mov     rcx, [rdx+8]
0x100401ff7  mov     rax, [rdx]
0x100401ffa  mov     [rax+8], rcx
0x100401ffe  mov     [rcx], rax
0x100402001  mov     [rdx+8], r12
0x100402005  mov     [rdx], r12
0x100402008  mov     ebx, 80000000h
0x10040200d  test    rdx, rdx
0x100402010  cmovnz  ebx, r12d
0x100402014  mov     rdi, [rsp+78h+var_50]
0x100402019  test    rdi, rdi
0x10040201c  jz      short loc_10040205E
0x10040201e  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x100402025  cmp     byte ptr [rax], 0
0x100402028  jz      short loc_100402051
0x10040202a  call    cs:__imp_rand
0x100402030  mov     r8d, eax
0x100402033  mov     eax, 66666667h
0x100402038  imul    r8d
0x10040203b  sar     edx, 1
0x10040203d  mov     ecx, edx
0x10040203f  shr     ecx, 1Fh
0x100402042  add     edx, ecx
0x100402044  lea     ecx, [rdx+rdx*4]
0x100402047  cmp     r8d, ecx
0x10040204a  jnz     short loc_100402051
0x10040204c  call    ?UpdateStatSnapshot@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<25,1,268435714>::UpdateStatSnapshot(void)
0x100402051  mov     [rdi], r12
0x100402054  mov     [rsp+78h+var_50], r12
0x100402059  mov     [rsp+78h+var_48], r12d
0x10040205e  mov     eax, ebx
0x100402060  add     rsp, 40h
0x100402064  pop     r15
0x100402066  pop     r14
0x100402068  pop     r12
0x10040206a  pop     rdi
0x10040206b  pop     rsi
0x10040206c  pop     rbp
0x10040206d  pop     rbx
0x10040206e  retn
```
