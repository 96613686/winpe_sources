# UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>::WakeUpWaiters(void)

- ea: `0x10045e890`
- end: `0x10045eb4e`
- name: `?WakeUpWaiters@?$UnfairRecursiveMutexInternal@USuspendQueueExpSLock@@$0A@@@QEAAXXZ`
- size: `702`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10044dd90`
- `0x1007dfd50`

## callees

- `0x100401170`
- `0x10045e890`
- `0x10045f270`
- `0x10045f450`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10045e9a5`
- `KERNEL32!QueryPerformanceCounter` at `0x10045e9d6`
- `KERNEL32!QueryPerformanceCounter` at `0x10045e9a5`
- `KERNEL32!QueryPerformanceCounter` at `0x10045e9d6`
- `sqldk!?sm_SchedNum@SOS_PublicGlobals@@2IA` at `0x10045e8fa`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10045e942`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10045eacd`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10045e994`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10045e9c5`
- `sqldk!?ResumeBulk@SOS_Scheduler@@SAXPEAV?$SEList@VWorkerWaitElem@@$0A@@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z` at `0x10045eb17`
- `sqldk!?ResumeBulk@SOS_Scheduler@@SAXPEAV?$SEList@VWorkerWaitElem@@$0A@@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z` at `0x10045eb17`
- `sqldk!??_5SystemAffinity@@QEAAAEAV0@AEBVNodeAffinity@@@Z` at `0x10045eaae`
- `sqldk!??_5SystemAffinity@@QEAAAEAV0@AEBVNodeAffinity@@@Z` at `0x10045eaae`
- `sqldk!?TryMoveTo@WorkerWaitQueue@@QEAA_NPEAVWorkerWaitElem@@W4WorkerSignalType@@PEAV?$SEList@VWorkerWaitElem@@$0A@@@2@Z` at `0x10045ea9a`
- `sqldk!?TryMoveTo@WorkerWaitQueue@@QEAA_NPEAVWorkerWaitElem@@W4WorkerSignalType@@PEAV?$SEList@VWorkerWaitElem@@$0A@@@2@Z` at `0x10045ea9a`
- `sqldk!??ISystemAffinity@@QEBA_KAEBVNodeAffinity@@@Z` at `0x10045ea7c`
- `sqldk!??ISystemAffinity@@QEBA_KAEBVNodeAffinity@@@Z` at `0x10045ea7c`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x10045e8d2`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x10045e8e0`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x10045e8d2`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x10045e8e0`
- `sqldk!SystemThread_TlsIndex` at `0x10045e966`
- `sqldk!SystemThread_TlsOffset` at `0x10045e96f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10045ead9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10045ead9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>::WakeUpWaiters(__int64 a1)
{
  unsigned int v2; // r15d
  int v3; // edi
  signed __int64 UniqueThread_low; // rbp
  __int64 v5; // r14
  __int64 v6; // r8
  LARGE_INTEGER v7; // rbx
  LARGE_INTEGER v8; // rcx
  LONGLONG v9; // rax
  __int64 v10; // r14
  __int64 v11; // rbx
  __int64 v12; // r13
  __int64 v13; // rcx
  __int64 v14; // rsi
  _BYTE *v15; // rbp
  int v16; // r8d
  _QWORD *v18; // [rsp+30h] [rbp-178h]
  _QWORD v19[2]; // [rsp+40h] [rbp-168h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp-158h] BYREF
  LARGE_INTEGER v21; // [rsp+58h] [rbp-150h] BYREF
  __int64 v22; // [rsp+60h] [rbp-148h]
  _BYTE v23[128]; // [rsp+70h] [rbp-138h] BYREF
  _BYTE v24[128]; // [rsp+F0h] [rbp-B8h] BYREF

  v22 = -2;
  SystemAffinity::SystemAffinity((SystemAffinity *)v23);
  SystemAffinity::SystemAffinity((SystemAffinity *)v24);
  v19[1] = v19;
  v19[0] = v19;
  v2 = 2 * SOS_PublicGlobals::sm_SchedNum;
  v3 = 100;
  v18 = (_QWORD *)(a1 + 24);
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( *(_DWORD *)(a1 + 24) || _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 24), UniqueThread_low, 0) )
  {
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) != 0x84 )
      goto LABEL_17;
    v5 = 0;
    v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    if ( v6 && *(_QWORD *)(v6 + 272) == v6 )
      v5 = *(_QWORD *)(v6 + 256);
    if ( v5 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&PerformanceCount);
        v7 = PerformanceCount;
      }
      else
      {
        v7.QuadPart = MEMORY[0x7FFE0008];
      }
      Spinlock<26,1,268435713>::SpinToAcquireWithExponentialBackoff(a1 + 24, UniqueThread_low);
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v21);
        v8 = v21;
      }
      else
      {
        v8.QuadPart = MEMORY[0x7FFE0008];
      }
      v9 = 0;
      if ( v8.QuadPart >= (unsigned __int64)v7.QuadPart )
        v9 = v8.QuadPart - v7.QuadPart;
      *(_QWORD *)(v5 + 3192) += v9;
    }
    else
    {
LABEL_17:
      Spinlock<26,1,268435713>::SpinToAcquireWithExponentialBackoff(a1 + 24, UniqueThread_low);
    }
  }
  v10 = a1 + 8;
  v11 = *(_QWORD *)(a1 + 16);
  if ( v11 != a1 + 8 && v11 )
  {
    do
    {
      if ( !--v3 )
        break;
      v12 = v11;
      v11 = *(_QWORD *)(v11 + 8);
      if ( v11 == v10 )
        v11 = 0;
      v13 = *(_QWORD *)(*(_QWORD *)(v12 + 16) + 8LL);
      v14 = *(_QWORD *)(v13 + 608);
      v15 = v23;
      if ( (*(_BYTE *)(v13 + 800) & 4) != 0 )
        v15 = v24;
      if ( !SystemAffinity::operator&(v15, v14 + 5136) )
      {
        if ( (unsigned __int8)WorkerWaitQueue::TryMoveTo(v10, v12, 0, v19, 0) )
        {
          SystemAffinity::operator|=(v15, v14 + 5136);
          if ( !--v2 )
            break;
        }
      }
    }
    while ( v11 );
  }
  if ( v18 )
  {
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v16 = rand();
      if ( v16 == 5 * (v16 / 5) )
        Spinlock<26,1,268435713>::UpdateStatSnapshot();
    }
    *v18 = 0;
  }
  return SOS_Scheduler::ResumeBulk(v19, 0, 0);
}

```

## disassembly

```asm
0x10045e890  mov     rax, rsp
0x10045e893  push    rdi
0x10045e894  push    r12
0x10045e896  push    r13
0x10045e898  push    r14
0x10045e89a  push    r15
0x10045e89c  sub     rsp, 180h
0x10045e8a3  mov     [rsp+1A8h+var_148], 0FFFFFFFFFFFFFFFEh
0x10045e8ac  mov     [rax+10h], rbx
0x10045e8b0  mov     [rax+18h], rbp
0x10045e8b4  mov     [rax+20h], rsi
0x10045e8b8  mov     rax, cs:__security_cookie
0x10045e8bf  xor     rax, rsp
0x10045e8c2  mov     [rsp+1A8h+var_38], rax
0x10045e8ca  mov     r13, rcx
0x10045e8cd  lea     rcx, [rsp+1A8h+var_138]
0x10045e8d2  call    cs:__imp_??0SystemAffinity@@QEAA@XZ; SystemAffinity::SystemAffinity(void)
0x10045e8d8  lea     rcx, [rsp+1A8h+var_B8]
0x10045e8e0  call    cs:__imp_??0SystemAffinity@@QEAA@XZ; SystemAffinity::SystemAffinity(void)
0x10045e8e6  lea     rax, [rsp+1A8h+var_168]
0x10045e8eb  mov     [rsp+1A8h+var_160], rax
0x10045e8f0  lea     rax, [rsp+1A8h+var_168]
0x10045e8f5  mov     [rsp+1A8h+var_168], rax
0x10045e8fa  mov     rax, cs:__imp_?sm_SchedNum@SOS_PublicGlobals@@2IA; uint SOS_PublicGlobals::sm_SchedNum
0x10045e901  mov     edx, [rax]
0x10045e903  lea     r15d, [rdx+rdx]
0x10045e907  mov     edi, 64h ; 'd'
0x10045e90c  lea     rsi, [r13+18h]
0x10045e910  mov     [rsp+1A8h+var_178], rsi
0x10045e915  xor     r12d, r12d
0x10045e918  mov     [rsp+1A8h+var_170], r12d
0x10045e91d  mov     eax, gs:48h
0x10045e925  mov     ebp, eax
0x10045e927  mov     eax, [rsi]
0x10045e929  test    eax, eax
0x10045e92b  jnz     short loc_10045E942
0x10045e92d  xor     eax, eax
0x10045e92f  lock cmpxchg [rsi], rbp
0x10045e934  mov     eax, r12d
0x10045e937  setz    al
0x10045e93a  test    eax, eax
0x10045e93c  jnz     loc_10045EA0F
0x10045e942  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10045e949  mov     ecx, [rax]
0x10045e94b  and     ecx, 84h
0x10045e951  cmp     cl, 84h
0x10045e954  jnz     loc_10045EA04
0x10045e95a  mov     r14, r12
0x10045e95d  mov     rdx, gs:58h
0x10045e966  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10045e96d  mov     ecx, [rax]
0x10045e96f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10045e976  mov     r8d, [rax]
0x10045e979  add     r8, [rdx+rcx*8]
0x10045e97d  jz      short loc_10045E98F
0x10045e97f  cmp     [r8+110h], r8
0x10045e986  jnz     short loc_10045E98F
0x10045e988  mov     r14, [r8+100h]
0x10045e98f  test    r14, r14
0x10045e992  jz      short loc_10045EA04
0x10045e994  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10045e99b  cmp     dword ptr [rax], 0
0x10045e99e  jz      short loc_10045E9B2
0x10045e9a0  lea     rcx, [rsp+1A8h+PerformanceCount]; lpPerformanceCount
0x10045e9a5  call    cs:__imp_QueryPerformanceCounter
0x10045e9ab  mov     rbx, qword ptr [rsp+1A8h+PerformanceCount]
0x10045e9b0  jmp     short loc_10045E9BA
0x10045e9b2  mov     rbx, ds:7FFE0008h
0x10045e9ba  mov     rdx, rbp
0x10045e9bd  mov     rcx, rsi
0x10045e9c0  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BK@$00$0BAAAABAB@@@AEAAX_K@Z; Spinlock<26,1,268435713>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10045e9c5  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10045e9cc  cmp     dword ptr [rax], 0
0x10045e9cf  jz      short loc_10045E9E3
0x10045e9d1  lea     rcx, [rsp+1A8h+var_150]; lpPerformanceCount
0x10045e9d6  call    cs:__imp_QueryPerformanceCounter
0x10045e9dc  mov     rcx, qword ptr [rsp+1A8h+var_150]
0x10045e9e1  jmp     short loc_10045E9EB
0x10045e9e3  mov     rcx, ds:7FFE0008h
0x10045e9eb  mov     rdx, rcx
0x10045e9ee  sub     rdx, rbx
0x10045e9f1  mov     rax, r12
0x10045e9f4  cmp     rcx, rbx
0x10045e9f7  cmovnb  rax, rdx
0x10045e9fb  add     [r14+0C78h], rax
0x10045ea02  jmp     short loc_10045EA0F
0x10045ea04  mov     rdx, rbp
0x10045ea07  mov     rcx, rsi
0x10045ea0a  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BK@$00$0BAAAABAB@@@AEAAX_K@Z; Spinlock<26,1,268435713>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10045ea0f  mov     [rsp+1A8h+var_170], 1
0x10045ea17  lea     r14, [r13+8]
0x10045ea1b  mov     rbx, [r14+8]
0x10045ea1f  cmp     rbx, r14
0x10045ea22  jz      loc_10045EAC3
0x10045ea28  test    rbx, rbx
0x10045ea2b  jz      loc_10045EAC3
0x10045ea31  add     edi, 0FFFFFFFFh
0x10045ea34  jz      loc_10045EAC3
0x10045ea3a  mov     r13, rbx
0x10045ea3d  mov     rax, [rbx+8]
0x10045ea41  mov     rbx, rax
0x10045ea44  cmp     rax, r14
0x10045ea47  cmovz   rbx, r12
0x10045ea4b  mov     rax, [r13+10h]
0x10045ea4f  mov     rcx, [rax+8]
0x10045ea53  mov     rsi, [rcx+260h]
0x10045ea5a  test    byte ptr [rcx+320h], 4
0x10045ea61  lea     rbp, [rsp+1A8h+var_138]
0x10045ea66  lea     rax, [rsp+1A8h+var_B8]
0x10045ea6e  cmovnz  rbp, rax
0x10045ea72  lea     rdx, [rsi+1410h]
0x10045ea79  mov     rcx, rbp
0x10045ea7c  call    cs:__imp_??ISystemAffinity@@QEBA_KAEBVNodeAffinity@@@Z; SystemAffinity::operator&(NodeAffinity const &)
0x10045ea82  test    rax, rax
0x10045ea85  jnz     short loc_10045EABA
0x10045ea87  mov     [rsp+1A8h+var_188], r12
0x10045ea8c  lea     r9, [rsp+1A8h+var_168]
0x10045ea91  xor     r8d, r8d
0x10045ea94  mov     rdx, r13
0x10045ea97  mov     rcx, r14
0x10045ea9a  call    cs:__imp_?TryMoveTo@WorkerWaitQueue@@QEAA_NPEAVWorkerWaitElem@@W4WorkerSignalType@@PEAV?$SEList@VWorkerWaitElem@@$0A@@@2@Z; WorkerWaitQueue::TryMoveTo(WorkerWaitElem *,WorkerSignalType,SEList<WorkerWaitElem,0> *,SEList<WorkerWaitElem,0> *)
0x10045eaa0  test    al, al
0x10045eaa2  jz      short loc_10045EABA
0x10045eaa4  lea     rdx, [rsi+1410h]
0x10045eaab  mov     rcx, rbp
0x10045eaae  call    cs:__imp_??_5SystemAffinity@@QEAAAEAV0@AEBVNodeAffinity@@@Z; SystemAffinity::operator|=(NodeAffinity const &)
0x10045eab4  add     r15d, 0FFFFFFFFh
0x10045eab8  jz      short loc_10045EAC3
0x10045eaba  test    rbx, rbx
0x10045eabd  jnz     loc_10045EA31
0x10045eac3  mov     rbx, [rsp+1A8h+var_178]
0x10045eac8  test    rbx, rbx
0x10045eacb  jz      short loc_10045EB0D
0x10045eacd  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10045ead4  cmp     byte ptr [rax], 0
0x10045ead7  jz      short loc_10045EB00
0x10045ead9  call    cs:__imp_rand
0x10045eadf  mov     r8d, eax
0x10045eae2  mov     eax, 66666667h
0x10045eae7  imul    r8d
0x10045eaea  sar     edx, 1
0x10045eaec  mov     ecx, edx
0x10045eaee  shr     ecx, 1Fh
0x10045eaf1  add     edx, ecx
0x10045eaf3  lea     ecx, [rdx+rdx*4]
0x10045eaf6  cmp     r8d, ecx
0x10045eaf9  jnz     short loc_10045EB00
0x10045eafb  call    ?UpdateStatSnapshot@?$Spinlock@$0BK@$00$0BAAAABAB@@@AEAAXXZ; Spinlock<26,1,268435713>::UpdateStatSnapshot(void)
0x10045eb00  mov     [rbx], r12
0x10045eb03  mov     [rsp+1A8h+var_178], r12
0x10045eb08  mov     [rsp+1A8h+var_170], r12d
0x10045eb0d  xor     r8d, r8d
0x10045eb10  xor     edx, edx
0x10045eb12  lea     rcx, [rsp+1A8h+var_168]
0x10045eb17  call    cs:__imp_?ResumeBulk@SOS_Scheduler@@SAXPEAV?$SEList@VWorkerWaitElem@@$0A@@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z; SOS_Scheduler::ResumeBulk(SEList<WorkerWaitElem,0> *,SOS_QUEUE_PLACE,SOS_RESULT)
0x10045eb1d  mov     rcx, [rsp+1A8h+var_38]
0x10045eb25  xor     rcx, rsp; StackCookie
0x10045eb28  call    __security_check_cookie
0x10045eb2d  lea     r11, [rsp+1A8h+var_28]
0x10045eb35  mov     rbx, [r11+38h]
0x10045eb39  mov     rbp, [r11+40h]
0x10045eb3d  mov     rsi, [r11+48h]
0x10045eb41  mov     rsp, r11
0x10045eb44  pop     r15
0x10045eb46  pop     r14
0x10045eb48  pop     r13
0x10045eb4a  pop     r12
0x10045eb4c  pop     rdi
0x10045eb4d  retn
```
