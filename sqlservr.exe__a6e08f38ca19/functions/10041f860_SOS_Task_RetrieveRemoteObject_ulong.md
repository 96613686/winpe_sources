# SOS_Task::RetrieveRemoteObject(ulong)

- ea: `0x10041f860`
- end: `0x10041fa1d`
- name: `?RetrieveRemoteObject@SOS_Task@@QEAAPEAXK@Z`
- size: `445`
- prototype: `void *__fastcall(SOS_Task *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x10041f400`

## callees

- `0x100408320`
- `0x100408560`
- `0x100408810`
- `0x10041f860`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10041f91b`
- `KERNEL32!QueryPerformanceCounter` at `0x10041f974`
- `KERNEL32!QueryPerformanceCounter` at `0x10041f91b`
- `KERNEL32!QueryPerformanceCounter` at `0x10041f974`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10041f933`
- `sqldk!SystemThread_TlsOffset` at `0x10041f8e3`
- `sqldk!SystemThread_TlsIndex` at `0x10041f8da`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041f908`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041f960`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10041f9cb`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10041f8ba`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041f9d7`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041f9d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SOS_Task::RetrieveRemoteObject(SOS_Task *this, unsigned int a2)
{
  __int64 v2; // r15
  volatile signed __int64 *v4; // rsi
  LARGE_INTEGER v5; // rbx
  signed __int64 UniqueThread_low; // rbp
  __int64 v7; // rdi
  __int64 v8; // r8
  LARGE_INTEGER v9; // rax
  LONGLONG v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rbx
  int v13; // eax
  _QWORD *v15; // [rsp+28h] [rbp-50h]
  LARGE_INTEGER PerformanceCount; // [rsp+80h] [rbp+8h] BYREF
  LARGE_INTEGER v17; // [rsp+90h] [rbp+18h] BYREF

  v2 = a2;
  v4 = (volatile signed __int64 *)((char *)this + 144);
  v15 = (_QWORD *)((char *)this + 144);
  v5.QuadPart = 0;
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( *((_DWORD *)this + 36) || _InterlockedCompareExchange64(v4, UniqueThread_low, 0) )
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
      Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v4, UniqueThread_low);
    else
      Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v4, v7, UniqueThread_low);
    if ( v7 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v17);
        v9 = v17;
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
  v11 = *((_QWORD *)this + 19);
  if ( v11 )
    v12 = *(_QWORD *)(*(_QWORD *)(v11 + 64) + 8 * v2);
  else
    v12 = 0;
  if ( v15 )
  {
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v13 = rand();
      if ( v13 == 5 * (v13 / 5) )
        Spinlock<11,2,268435714>::UpdateStatSnapshot();
    }
    *v15 = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x10041f860  push    rbx
0x10041f862  push    rbp
0x10041f863  push    rsi
0x10041f864  push    rdi
0x10041f865  push    r12
0x10041f867  push    r14
0x10041f869  push    r15
0x10041f86b  sub     rsp, 40h
0x10041f86f  mov     [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh
0x10041f878  mov     r15d, edx
0x10041f87b  mov     r14, rcx
0x10041f87e  lea     rsi, [rcx+90h]
0x10041f885  mov     [rsp+78h+var_50], rsi
0x10041f88a  xor     r12d, r12d
0x10041f88d  mov     [rsp+78h+var_48], r12d
0x10041f892  mov     ebx, r12d
0x10041f895  mov     eax, gs:48h
0x10041f89d  mov     ebp, eax
0x10041f89f  mov     eax, [rsi]
0x10041f8a1  test    eax, eax
0x10041f8a3  jnz     short loc_10041F8BA
0x10041f8a5  xor     eax, eax
0x10041f8a7  lock cmpxchg [rsi], rbp
0x10041f8ac  mov     eax, r12d
0x10041f8af  setz    al
0x10041f8b2  test    eax, eax
0x10041f8b4  jnz     loc_10041F9A0
0x10041f8ba  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10041f8c1  mov     ecx, [rax]
0x10041f8c3  and     ecx, 84h
0x10041f8c9  mov     rdi, r12
0x10041f8cc  cmp     cl, 84h
0x10041f8cf  jnz     short loc_10041F933
0x10041f8d1  mov     rdx, gs:58h
0x10041f8da  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041f8e1  mov     ecx, [rax]
0x10041f8e3  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041f8ea  mov     r8d, [rax]
0x10041f8ed  add     r8, [rdx+rcx*8]
0x10041f8f1  jz      short loc_10041F903
0x10041f8f3  cmp     [r8+110h], r8
0x10041f8fa  jnz     short loc_10041F903
0x10041f8fc  mov     rdi, [r8+100h]
0x10041f903  test    rdi, rdi
0x10041f906  jz      short loc_10041F933
0x10041f908  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10041f90f  cmp     [rax], ebx
0x10041f911  jz      short loc_10041F92B
0x10041f913  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x10041f91b  call    cs:__imp_QueryPerformanceCounter
0x10041f921  mov     rbx, qword ptr [rsp+78h+PerformanceCount]
0x10041f929  jmp     short loc_10041F933
0x10041f92b  mov     rbx, ds:7FFE0008h
0x10041f933  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10041f93a  mov     rcx, rsi
0x10041f93d  cmp     byte ptr [rax+0C7h], 0
0x10041f944  jge     short loc_10041F953
0x10041f946  mov     r8, rbp
0x10041f949  mov     rdx, rdi
0x10041f94c  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10041f951  jmp     short loc_10041F95B
0x10041f953  mov     rdx, rbp
0x10041f956  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10041f95b  test    rdi, rdi
0x10041f95e  jz      short loc_10041F9A0
0x10041f960  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10041f967  cmp     dword ptr [rax], 0
0x10041f96a  jz      short loc_10041F984
0x10041f96c  lea     rcx, [rsp+78h+arg_10]; lpPerformanceCount
0x10041f974  call    cs:__imp_QueryPerformanceCounter
0x10041f97a  mov     rax, qword ptr [rsp+78h+arg_10]
0x10041f982  jmp     short loc_10041F98C
0x10041f984  mov     rax, ds:7FFE0008h
0x10041f98c  mov     rcx, rax
0x10041f98f  sub     rcx, rbx
0x10041f992  cmp     rax, rbx
0x10041f995  cmovb   rcx, r12
0x10041f999  add     [rdi+0C78h], rcx
0x10041f9a0  mov     [rsp+78h+var_48], 1
0x10041f9a8  mov     rax, [r14+98h]
0x10041f9af  test    rax, rax
0x10041f9b2  jz      short loc_10041F9BE
0x10041f9b4  mov     rax, [rax+40h]
0x10041f9b8  mov     rbx, [rax+r15*8]
0x10041f9bc  jmp     short loc_10041F9C1
0x10041f9be  mov     rbx, r12
0x10041f9c1  mov     rdi, [rsp+78h+var_50]
0x10041f9c6  test    rdi, rdi
0x10041f9c9  jz      short loc_10041FA0B
0x10041f9cb  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10041f9d2  cmp     byte ptr [rax], 0
0x10041f9d5  jz      short loc_10041F9FE
0x10041f9d7  call    cs:__imp_rand
0x10041f9dd  mov     r8d, eax
0x10041f9e0  mov     eax, 66666667h
0x10041f9e5  imul    r8d
0x10041f9e8  sar     edx, 1
0x10041f9ea  mov     ecx, edx
0x10041f9ec  shr     ecx, 1Fh
0x10041f9ef  add     edx, ecx
0x10041f9f1  lea     ecx, [rdx+rdx*4]
0x10041f9f4  cmp     r8d, ecx
0x10041f9f7  jnz     short loc_10041F9FE
0x10041f9f9  call    ?UpdateStatSnapshot@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXXZ; Spinlock<11,2,268435714>::UpdateStatSnapshot(void)
0x10041f9fe  mov     [rdi], r12
0x10041fa01  mov     [rsp+78h+var_50], r12
0x10041fa06  mov     [rsp+78h+var_48], r12d
0x10041fa0b  mov     rax, rbx
0x10041fa0e  add     rsp, 40h
0x10041fa12  pop     r15
0x10041fa14  pop     r14
0x10041fa16  pop     r12
0x10041fa18  pop     rdi
0x10041fa19  pop     rsi
0x10041fa1a  pop     rbp
0x10041fa1b  pop     rbx
0x10041fa1c  retn
```
