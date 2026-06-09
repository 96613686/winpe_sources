# LockedWaitQueue<WaitableBase,SuspendQueueSLock>::RemoveFromWaitQueue(WorkerWaitElem *)

- ea: `0x10049f9a0`
- end: `0x10049fb0d`
- name: `?RemoveFromWaitQueue@?$LockedWaitQueue@VWaitableBase@@USuspendQueueSLock@@@@UEAA?AW4SOS_RESULT@@PEAVWorkerWaitElem@@@Z`
- size: `365`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x100460570`
- `0x10049f9a0`
- `0x10049fb80`
- `0x10049fbf0`
- `0x10049fe30`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10049fa58`
- `KERNEL32!QueryPerformanceCounter` at `0x10049fab1`
- `KERNEL32!QueryPerformanceCounter` at `0x10049fa58`
- `KERNEL32!QueryPerformanceCounter` at `0x10049fab1`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10049f9f7`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10049fa45`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10049fa9d`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10049fa70`
- `sqldk!SystemThread_TlsIndex` at `0x10049fa17`
- `sqldk!SystemThread_TlsOffset` at `0x10049fa20`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LockedWaitQueue<WaitableBase,SuspendQueueSLock>::RemoveFromWaitQueue(__int64 a1, __int64 a2)
{
  volatile signed __int64 *v4; // rsi
  LARGE_INTEGER v5; // rbx
  signed __int64 UniqueThread_low; // rbp
  __int64 v7; // rdi
  __int64 v8; // r8
  LARGE_INTEGER v9; // rax
  LONGLONG v10; // rcx
  unsigned int v11; // ebx
  __int64 v13; // [rsp+28h] [rbp-50h] BYREF
  int v14; // [rsp+30h] [rbp-48h]
  LARGE_INTEGER PerformanceCount; // [rsp+80h] [rbp+8h] BYREF
  LARGE_INTEGER v16; // [rsp+90h] [rbp+18h] BYREF

  v4 = (volatile signed __int64 *)(a1 + 24);
  v13 = a1 + 24;
  v14 = 0;
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
        QueryPerformanceCounter(&v16);
        v9 = v16;
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
  v14 = 1;
  v11 = MinWaitableBase::RemoveFromWaitQueue(a1, a2);
  SpinlockHolder<25,1,268435714>::~SpinlockHolder<25,1,268435714>(&v13);
  return v11;
}

```

## disassembly

```asm
0x10049f9a0  push    rbx
0x10049f9a2  push    rbp
0x10049f9a3  push    rsi
0x10049f9a4  push    rdi
0x10049f9a5  push    r12
0x10049f9a7  push    r14
0x10049f9a9  push    r15
0x10049f9ab  sub     rsp, 40h
0x10049f9af  mov     [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh
0x10049f9b8  mov     r15, rdx
0x10049f9bb  mov     r14, rcx
0x10049f9be  lea     rsi, [rcx+18h]
0x10049f9c2  mov     [rsp+78h+var_50], rsi
0x10049f9c7  xor     r12d, r12d
0x10049f9ca  mov     [rsp+78h+var_48], r12d
0x10049f9cf  mov     ebx, r12d
0x10049f9d2  mov     eax, gs:48h
0x10049f9da  mov     ebp, eax
0x10049f9dc  mov     eax, [rsi]
0x10049f9de  test    eax, eax
0x10049f9e0  jnz     short loc_10049F9F7
0x10049f9e2  xor     eax, eax
0x10049f9e4  lock cmpxchg [rsi], rbp
0x10049f9e9  mov     eax, r12d
0x10049f9ec  setz    al
0x10049f9ef  test    eax, eax
0x10049f9f1  jnz     loc_10049FADD
0x10049f9f7  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10049f9fe  mov     ecx, [rax]
0x10049fa00  and     ecx, 84h
0x10049fa06  mov     rdi, r12
0x10049fa09  cmp     cl, 84h
0x10049fa0c  jnz     short loc_10049FA70
0x10049fa0e  mov     rdx, gs:58h
0x10049fa17  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10049fa1e  mov     ecx, [rax]
0x10049fa20  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10049fa27  mov     r8d, [rax]
0x10049fa2a  add     r8, [rdx+rcx*8]
0x10049fa2e  jz      short loc_10049FA40
0x10049fa30  cmp     [r8+110h], r8
0x10049fa37  jnz     short loc_10049FA40
0x10049fa39  mov     rdi, [r8+100h]
0x10049fa40  test    rdi, rdi
0x10049fa43  jz      short loc_10049FA70
0x10049fa45  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10049fa4c  cmp     [rax], ebx
0x10049fa4e  jz      short loc_10049FA68
0x10049fa50  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x10049fa58  call    cs:__imp_QueryPerformanceCounter
0x10049fa5e  mov     rbx, qword ptr [rsp+78h+PerformanceCount]
0x10049fa66  jmp     short loc_10049FA70
0x10049fa68  mov     rbx, ds:7FFE0008h
0x10049fa70  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10049fa77  mov     rcx, rsi
0x10049fa7a  cmp     byte ptr [rax+0C7h], 0
0x10049fa81  jge     short loc_10049FA90
0x10049fa83  mov     r8, rbp
0x10049fa86  mov     rdx, rdi
0x10049fa89  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<25,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10049fa8e  jmp     short loc_10049FA98
0x10049fa90  mov     rdx, rbp
0x10049fa93  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10049fa98  test    rdi, rdi
0x10049fa9b  jz      short loc_10049FADD
0x10049fa9d  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10049faa4  cmp     dword ptr [rax], 0
0x10049faa7  jz      short loc_10049FAC1
0x10049faa9  lea     rcx, [rsp+78h+arg_10]; lpPerformanceCount
0x10049fab1  call    cs:__imp_QueryPerformanceCounter
0x10049fab7  mov     rax, qword ptr [rsp+78h+arg_10]
0x10049fabf  jmp     short loc_10049FAC9
0x10049fac1  mov     rax, ds:7FFE0008h
0x10049fac9  mov     rcx, rax
0x10049facc  sub     rcx, rbx
0x10049facf  cmp     rax, rbx
0x10049fad2  cmovb   rcx, r12
0x10049fad6  add     [rdi+0C78h], rcx
0x10049fadd  mov     [rsp+78h+var_48], 1
0x10049fae5  mov     rdx, r15
0x10049fae8  mov     rcx, r14
0x10049faeb  call    ?RemoveFromWaitQueue@MinWaitableBase@@UEAA?AW4SOS_RESULT@@PEAVWorkerWaitElem@@@Z; MinWaitableBase::RemoveFromWaitQueue(WorkerWaitElem *)
0x10049faf0  mov     ebx, eax
0x10049faf2  lea     rcx, [rsp+78h+var_50]
0x10049faf7  call    ??1?$SpinlockHolder@$0BJ@$00$0BAAAABAC@@@QEAA@XZ; SpinlockHolder<25,1,268435714>::~SpinlockHolder<25,1,268435714>(void)
0x10049fafc  mov     eax, ebx
0x10049fafe  add     rsp, 40h
0x10049fb02  pop     r15
0x10049fb04  pop     r14
0x10049fb06  pop     r12
0x10049fb08  pop     rdi
0x10049fb09  pop     rsi
0x10049fb0a  pop     rbp
0x10049fb0b  pop     rbx
0x10049fb0c  retn
```
