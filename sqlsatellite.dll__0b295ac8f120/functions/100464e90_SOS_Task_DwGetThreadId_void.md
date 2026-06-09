# SOS_Task::DwGetThreadId(void)

- ea: `0x100464e90`
- end: `0x100465033`
- name: `?DwGetThreadId@SOS_Task@@QEAAKXZ`
- size: `419`
- prototype: `unsigned int __fastcall(SOS_Task *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x100465450`

## callees

- `0x10040c7a0`
- `0x10040c9e0`
- `0x10040cc90`
- `0x100464e90`
- `0x100465040`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100464f45`
- `KERNEL32!QueryPerformanceCounter` at `0x100464f98`
- `KERNEL32!QueryPerformanceCounter` at `0x100464f45`
- `KERNEL32!QueryPerformanceCounter` at `0x100464f98`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100464fdd`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100464f35`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100464f87`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100464f5a`
- `sqldk!SystemThread_TlsIndex` at `0x100464f07`
- `sqldk!SystemThread_TlsOffset` at `0x100464f10`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100464ee7`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100464fe9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100464fe9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SOS_Task::DwGetThreadId(SOS_Task *this)
{
  volatile signed __int64 *v2; // rsi
  LARGE_INTEGER v3; // rbx
  signed __int64 UniqueThread_low; // rbp
  __int64 v5; // rdi
  __int64 v6; // r8
  LARGE_INTEGER v7; // rax
  LONGLONG v8; // rcx
  __int64 result; // rax
  unsigned int v10; // ebx
  int v11; // eax
  _QWORD *v12; // [rsp+28h] [rbp-40h]
  LARGE_INTEGER PerformanceCount; // [rsp+70h] [rbp+8h] BYREF
  LARGE_INTEGER v14; // [rsp+78h] [rbp+10h] BYREF

  v2 = (volatile signed __int64 *)((char *)this + 144);
  v12 = (_QWORD *)((char *)this + 144);
  v3.QuadPart = 0;
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( *((_DWORD *)this + 36) || _InterlockedCompareExchange64(v2, UniqueThread_low, 0) )
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
      Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v2, UniqueThread_low);
    else
      Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v2, v5, UniqueThread_low);
    if ( v5 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v14);
        v7 = v14;
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
  result = SOS_Task::GetThreadIdNoLock(this);
  v10 = result;
  if ( v12 )
  {
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v11 = rand();
      if ( v11 == 5 * (v11 / 5) )
        Spinlock<11,2,268435714>::UpdateStatSnapshot();
    }
    *v12 = 0;
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x100464e90  mov     rax, rsp
0x100464e93  push    rbp
0x100464e94  push    rsi
0x100464e95  push    rdi
0x100464e96  push    r14
0x100464e98  push    r15
0x100464e9a  sub     rsp, 40h
0x100464e9e  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x100464ea6  mov     [rax+20h], rbx
0x100464eaa  mov     r14, rcx
0x100464ead  lea     rsi, [rcx+90h]
0x100464eb4  mov     [rax-40h], rsi
0x100464eb8  xor     r15d, r15d
0x100464ebb  mov     [rax-38h], r15d
0x100464ebf  mov     ebx, r15d
0x100464ec2  mov     eax, gs:48h
0x100464eca  mov     ebp, eax
0x100464ecc  mov     eax, [rsi]
0x100464ece  test    eax, eax
0x100464ed0  jnz     short loc_100464EE7
0x100464ed2  xor     eax, eax
0x100464ed4  lock cmpxchg [rsi], rbp
0x100464ed9  mov     eax, r15d
0x100464edc  setz    al
0x100464edf  test    eax, eax
0x100464ee1  jnz     loc_100464FC1
0x100464ee7  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100464eee  mov     ecx, [rax]
0x100464ef0  and     ecx, 84h
0x100464ef6  mov     rdi, r15
0x100464ef9  cmp     cl, 84h
0x100464efc  jnz     short loc_100464F5A
0x100464efe  mov     rdx, gs:58h
0x100464f07  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100464f0e  mov     ecx, [rax]
0x100464f10  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100464f17  mov     r8d, [rax]
0x100464f1a  add     r8, [rdx+rcx*8]
0x100464f1e  jz      short loc_100464F30
0x100464f20  cmp     [r8+110h], r8
0x100464f27  jnz     short loc_100464F30
0x100464f29  mov     rdi, [r8+100h]
0x100464f30  test    rdi, rdi
0x100464f33  jz      short loc_100464F5A
0x100464f35  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100464f3c  cmp     [rax], ebx
0x100464f3e  jz      short loc_100464F52
0x100464f40  lea     rcx, [rsp+68h+PerformanceCount]; lpPerformanceCount
0x100464f45  call    cs:__imp_QueryPerformanceCounter
0x100464f4b  mov     rbx, qword ptr [rsp+68h+PerformanceCount]
0x100464f50  jmp     short loc_100464F5A
0x100464f52  mov     rbx, ds:7FFE0008h
0x100464f5a  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100464f61  mov     rcx, rsi
0x100464f64  cmp     byte ptr [rax+0C7h], 0
0x100464f6b  jge     short loc_100464F7A
0x100464f6d  mov     r8, rbp
0x100464f70  mov     rdx, rdi
0x100464f73  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100464f78  jmp     short loc_100464F82
0x100464f7a  mov     rdx, rbp
0x100464f7d  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100464f82  test    rdi, rdi
0x100464f85  jz      short loc_100464FC1
0x100464f87  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100464f8e  cmp     dword ptr [rax], 0
0x100464f91  jz      short loc_100464FA5
0x100464f93  lea     rcx, [rsp+68h+arg_8]; lpPerformanceCount
0x100464f98  call    cs:__imp_QueryPerformanceCounter
0x100464f9e  mov     rax, qword ptr [rsp+68h+arg_8]
0x100464fa3  jmp     short loc_100464FAD
0x100464fa5  mov     rax, ds:7FFE0008h
0x100464fad  mov     rcx, rax
0x100464fb0  sub     rcx, rbx
0x100464fb3  cmp     rax, rbx
0x100464fb6  cmovb   rcx, r15
0x100464fba  add     [rdi+0C78h], rcx
0x100464fc1  mov     [rsp+68h+var_38], 1
0x100464fc9  mov     rcx, r14; this
0x100464fcc  call    ?GetThreadIdNoLock@SOS_Task@@AEAAKXZ; SOS_Task::GetThreadIdNoLock(void)
0x100464fd1  mov     ebx, eax
0x100464fd3  mov     rdi, [rsp+68h+var_40]
0x100464fd8  test    rdi, rdi
0x100464fdb  jz      short loc_10046501F
0x100464fdd  mov     rcx, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x100464fe4  cmp     byte ptr [rcx], 0
0x100464fe7  jz      short loc_100465010
0x100464fe9  call    cs:__imp_rand
0x100464fef  mov     r8d, eax
0x100464ff2  mov     eax, 66666667h
0x100464ff7  imul    r8d
0x100464ffa  sar     edx, 1
0x100464ffc  mov     ecx, edx
0x100464ffe  shr     ecx, 1Fh
0x100465001  add     edx, ecx
0x100465003  lea     ecx, [rdx+rdx*4]
0x100465006  cmp     r8d, ecx
0x100465009  jnz     short loc_100465010
0x10046500b  call    ?UpdateStatSnapshot@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXXZ; Spinlock<11,2,268435714>::UpdateStatSnapshot(void)
0x100465010  mov     [rdi], r15
0x100465013  mov     [rsp+68h+var_40], r15
0x100465018  mov     [rsp+68h+var_38], r15d
0x10046501d  mov     eax, ebx
0x10046501f  mov     rbx, [rsp+68h+arg_18]
0x100465027  add     rsp, 40h
0x10046502b  pop     r15
0x10046502d  pop     r14
0x10046502f  pop     rdi
0x100465030  pop     rsi
0x100465031  pop     rbp
0x100465032  retn
```
