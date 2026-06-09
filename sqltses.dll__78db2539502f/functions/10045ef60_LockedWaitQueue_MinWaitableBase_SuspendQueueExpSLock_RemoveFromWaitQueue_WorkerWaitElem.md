# LockedWaitQueue<MinWaitableBase,SuspendQueueExpSLock>::RemoveFromWaitQueue(WorkerWaitElem *)

- ea: `0x10045ef60`
- end: `0x10045f0fd`
- name: `?RemoveFromWaitQueue@?$LockedWaitQueue@VMinWaitableBase@@USuspendQueueExpSLock@@@@UEAA?AW4SOS_RESULT@@PEAVWorkerWaitElem@@@Z`
- size: `413`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x10045ef60`
- `0x10045f270`
- `0x10045f450`
- `0x100460570`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10045f01a`
- `KERNEL32!QueryPerformanceCounter` at `0x10045f051`
- `KERNEL32!QueryPerformanceCounter` at `0x10045f01a`
- `KERNEL32!QueryPerformanceCounter` at `0x10045f051`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10045efb4`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10045f0ac`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10045f006`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10045f03d`
- `sqldk!SystemThread_TlsIndex` at `0x10045efd8`
- `sqldk!SystemThread_TlsOffset` at `0x10045efe1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10045f0b8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10045f0b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LockedWaitQueue<MinWaitableBase,SuspendQueueExpSLock>::RemoveFromWaitQueue(__int64 a1, __int64 a2)
{
  volatile signed __int64 *v4; // rdi
  signed __int64 UniqueThread_low; // rsi
  __int64 v6; // rbp
  __int64 v7; // r8
  LARGE_INTEGER v8; // rbx
  LARGE_INTEGER v9; // rcx
  LONGLONG v10; // rax
  __int64 result; // rax
  unsigned int v12; // ebx
  int v13; // eax
  _QWORD *v14; // [rsp+28h] [rbp-50h]
  LARGE_INTEGER PerformanceCount; // [rsp+80h] [rbp+8h] BYREF
  LARGE_INTEGER v16; // [rsp+90h] [rbp+18h] BYREF

  v4 = (volatile signed __int64 *)(a1 + 24);
  v14 = (_QWORD *)(a1 + 24);
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( *(_DWORD *)(a1 + 24) || _InterlockedCompareExchange64(v4, UniqueThread_low, 0) )
  {
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) != 0x84 )
      goto LABEL_17;
    v6 = 0;
    v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    if ( v7 && *(_QWORD *)(v7 + 272) == v7 )
      v6 = *(_QWORD *)(v7 + 256);
    if ( v6 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&PerformanceCount);
        v8 = PerformanceCount;
      }
      else
      {
        v8.QuadPart = MEMORY[0x7FFE0008];
      }
      Spinlock<26,1,268435713>::SpinToAcquireWithExponentialBackoff(v4, UniqueThread_low);
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v16);
        v9 = v16;
      }
      else
      {
        v9.QuadPart = MEMORY[0x7FFE0008];
      }
      v10 = 0;
      if ( v9.QuadPart >= (unsigned __int64)v8.QuadPart )
        v10 = v9.QuadPart - v8.QuadPart;
      *(_QWORD *)(v6 + 3192) += v10;
    }
    else
    {
LABEL_17:
      Spinlock<26,1,268435713>::SpinToAcquireWithExponentialBackoff(v4, UniqueThread_low);
    }
  }
  result = MinWaitableBase::RemoveFromWaitQueue(a1, a2);
  v12 = result;
  if ( v14 )
  {
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v13 = rand();
      if ( v13 == 5 * (v13 / 5) )
        Spinlock<26,1,268435713>::UpdateStatSnapshot();
    }
    *v14 = 0;
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x10045ef60  push    rbx
0x10045ef62  push    rbp
0x10045ef63  push    rsi
0x10045ef64  push    rdi
0x10045ef65  push    r12
0x10045ef67  push    r14
0x10045ef69  push    r15
0x10045ef6b  sub     rsp, 40h
0x10045ef6f  mov     [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh
0x10045ef78  mov     r15, rdx
0x10045ef7b  mov     r14, rcx
0x10045ef7e  lea     rdi, [rcx+18h]
0x10045ef82  mov     [rsp+78h+var_50], rdi
0x10045ef87  xor     r12d, r12d
0x10045ef8a  mov     [rsp+78h+var_48], r12d
0x10045ef8f  mov     eax, gs:48h
0x10045ef97  mov     esi, eax
0x10045ef99  mov     eax, [rdi]
0x10045ef9b  test    eax, eax
0x10045ef9d  jnz     short loc_10045EFB4
0x10045ef9f  xor     eax, eax
0x10045efa1  lock cmpxchg [rdi], rsi
0x10045efa6  mov     eax, r12d
0x10045efa9  setz    al
0x10045efac  test    eax, eax
0x10045efae  jnz     loc_10045F08D
0x10045efb4  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10045efbb  mov     ecx, [rax]
0x10045efbd  and     ecx, 84h
0x10045efc3  cmp     cl, 84h
0x10045efc6  jnz     loc_10045F082
0x10045efcc  mov     rbp, r12
0x10045efcf  mov     rdx, gs:58h
0x10045efd8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10045efdf  mov     ecx, [rax]
0x10045efe1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10045efe8  mov     r8d, [rax]
0x10045efeb  add     r8, [rdx+rcx*8]
0x10045efef  jz      short loc_10045F001
0x10045eff1  cmp     [r8+110h], r8
0x10045eff8  jnz     short loc_10045F001
0x10045effa  mov     rbp, [r8+100h]
0x10045f001  test    rbp, rbp
0x10045f004  jz      short loc_10045F082
0x10045f006  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10045f00d  cmp     dword ptr [rax], 0
0x10045f010  jz      short loc_10045F02A
0x10045f012  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x10045f01a  call    cs:__imp_QueryPerformanceCounter
0x10045f020  mov     rbx, qword ptr [rsp+78h+PerformanceCount]
0x10045f028  jmp     short loc_10045F032
0x10045f02a  mov     rbx, ds:7FFE0008h
0x10045f032  mov     rdx, rsi
0x10045f035  mov     rcx, rdi
0x10045f038  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BK@$00$0BAAAABAB@@@AEAAX_K@Z; Spinlock<26,1,268435713>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10045f03d  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10045f044  cmp     dword ptr [rax], 0
0x10045f047  jz      short loc_10045F061
0x10045f049  lea     rcx, [rsp+78h+arg_10]; lpPerformanceCount
0x10045f051  call    cs:__imp_QueryPerformanceCounter
0x10045f057  mov     rcx, qword ptr [rsp+78h+arg_10]
0x10045f05f  jmp     short loc_10045F069
0x10045f061  mov     rcx, ds:7FFE0008h
0x10045f069  mov     rdx, rcx
0x10045f06c  sub     rdx, rbx
0x10045f06f  mov     rax, r12
0x10045f072  cmp     rcx, rbx
0x10045f075  cmovnb  rax, rdx
0x10045f079  add     [rbp+0C78h], rax
0x10045f080  jmp     short loc_10045F08D
0x10045f082  mov     rdx, rsi
0x10045f085  mov     rcx, rdi
0x10045f088  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BK@$00$0BAAAABAB@@@AEAAX_K@Z; Spinlock<26,1,268435713>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10045f08d  mov     [rsp+78h+var_48], 1
0x10045f095  mov     rdx, r15
0x10045f098  mov     rcx, r14
0x10045f09b  call    ?RemoveFromWaitQueue@MinWaitableBase@@UEAA?AW4SOS_RESULT@@PEAVWorkerWaitElem@@@Z; MinWaitableBase::RemoveFromWaitQueue(WorkerWaitElem *)
0x10045f0a0  mov     ebx, eax
0x10045f0a2  mov     rdi, [rsp+78h+var_50]
0x10045f0a7  test    rdi, rdi
0x10045f0aa  jz      short loc_10045F0EE
0x10045f0ac  mov     rcx, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10045f0b3  cmp     byte ptr [rcx], 0
0x10045f0b6  jz      short loc_10045F0DF
0x10045f0b8  call    cs:__imp_rand
0x10045f0be  mov     r8d, eax
0x10045f0c1  mov     eax, 66666667h
0x10045f0c6  imul    r8d
0x10045f0c9  sar     edx, 1
0x10045f0cb  mov     ecx, edx
0x10045f0cd  shr     ecx, 1Fh
0x10045f0d0  add     edx, ecx
0x10045f0d2  lea     ecx, [rdx+rdx*4]
0x10045f0d5  cmp     r8d, ecx
0x10045f0d8  jnz     short loc_10045F0DF
0x10045f0da  call    ?UpdateStatSnapshot@?$Spinlock@$0BK@$00$0BAAAABAB@@@AEAAXXZ; Spinlock<26,1,268435713>::UpdateStatSnapshot(void)
0x10045f0df  mov     [rdi], r12
0x10045f0e2  mov     [rsp+78h+var_50], r12
0x10045f0e7  mov     [rsp+78h+var_48], r12d
0x10045f0ec  mov     eax, ebx
0x10045f0ee  add     rsp, 40h
0x10045f0f2  pop     r15
0x10045f0f4  pop     r14
0x10045f0f6  pop     r12
0x10045f0f8  pop     rdi
0x10045f0f9  pop     rsi
0x10045f0fa  pop     rbp
0x10045f0fb  pop     rbx
0x10045f0fc  retn
```
