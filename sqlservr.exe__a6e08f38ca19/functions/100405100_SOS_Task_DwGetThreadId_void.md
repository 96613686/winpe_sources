# SOS_Task::DwGetThreadId(void)

- ea: `0x100405100`
- end: `0x1004052a3`
- name: `?DwGetThreadId@SOS_Task@@QEAAKXZ`
- size: `419`
- prototype: `unsigned int __fastcall(SOS_Task *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x100405b20`

## callees

- `0x100405100`
- `0x1004052b0`
- `0x100408320`
- `0x100408560`
- `0x100408810`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1004051b5`
- `KERNEL32!QueryPerformanceCounter` at `0x100405208`
- `KERNEL32!QueryPerformanceCounter` at `0x1004051b5`
- `KERNEL32!QueryPerformanceCounter` at `0x100405208`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x1004051ca`
- `sqldk!SystemThread_TlsOffset` at `0x100405180`
- `sqldk!SystemThread_TlsIndex` at `0x100405177`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004051a5`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004051f7`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040524d`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100405157`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100405259`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100405259`

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
0x100405100  mov     rax, rsp
0x100405103  push    rbp
0x100405104  push    rsi
0x100405105  push    rdi
0x100405106  push    r14
0x100405108  push    r15
0x10040510a  sub     rsp, 40h
0x10040510e  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x100405116  mov     [rax+20h], rbx
0x10040511a  mov     r14, rcx
0x10040511d  lea     rsi, [rcx+90h]
0x100405124  mov     [rax-40h], rsi
0x100405128  xor     r15d, r15d
0x10040512b  mov     [rax-38h], r15d
0x10040512f  mov     ebx, r15d
0x100405132  mov     eax, gs:48h
0x10040513a  mov     ebp, eax
0x10040513c  mov     eax, [rsi]
0x10040513e  test    eax, eax
0x100405140  jnz     short loc_100405157
0x100405142  xor     eax, eax
0x100405144  lock cmpxchg [rsi], rbp
0x100405149  mov     eax, r15d
0x10040514c  setz    al
0x10040514f  test    eax, eax
0x100405151  jnz     loc_100405231
0x100405157  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040515e  mov     ecx, [rax]
0x100405160  and     ecx, 84h
0x100405166  mov     rdi, r15
0x100405169  cmp     cl, 84h
0x10040516c  jnz     short loc_1004051CA
0x10040516e  mov     rdx, gs:58h
0x100405177  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040517e  mov     ecx, [rax]
0x100405180  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100405187  mov     r8d, [rax]
0x10040518a  add     r8, [rdx+rcx*8]
0x10040518e  jz      short loc_1004051A0
0x100405190  cmp     [r8+110h], r8
0x100405197  jnz     short loc_1004051A0
0x100405199  mov     rdi, [r8+100h]
0x1004051a0  test    rdi, rdi
0x1004051a3  jz      short loc_1004051CA
0x1004051a5  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004051ac  cmp     [rax], ebx
0x1004051ae  jz      short loc_1004051C2
0x1004051b0  lea     rcx, [rsp+68h+PerformanceCount]; lpPerformanceCount
0x1004051b5  call    cs:__imp_QueryPerformanceCounter
0x1004051bb  mov     rbx, qword ptr [rsp+68h+PerformanceCount]
0x1004051c0  jmp     short loc_1004051CA
0x1004051c2  mov     rbx, ds:7FFE0008h
0x1004051ca  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x1004051d1  mov     rcx, rsi
0x1004051d4  cmp     byte ptr [rax+0C7h], 0
0x1004051db  jge     short loc_1004051EA
0x1004051dd  mov     r8, rbp
0x1004051e0  mov     rdx, rdi
0x1004051e3  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x1004051e8  jmp     short loc_1004051F2
0x1004051ea  mov     rdx, rbp
0x1004051ed  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x1004051f2  test    rdi, rdi
0x1004051f5  jz      short loc_100405231
0x1004051f7  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004051fe  cmp     dword ptr [rax], 0
0x100405201  jz      short loc_100405215
0x100405203  lea     rcx, [rsp+68h+arg_8]; lpPerformanceCount
0x100405208  call    cs:__imp_QueryPerformanceCounter
0x10040520e  mov     rax, qword ptr [rsp+68h+arg_8]
0x100405213  jmp     short loc_10040521D
0x100405215  mov     rax, ds:7FFE0008h
0x10040521d  mov     rcx, rax
0x100405220  sub     rcx, rbx
0x100405223  cmp     rax, rbx
0x100405226  cmovb   rcx, r15
0x10040522a  add     [rdi+0C78h], rcx
0x100405231  mov     [rsp+68h+var_38], 1
0x100405239  mov     rcx, r14; this
0x10040523c  call    ?GetThreadIdNoLock@SOS_Task@@AEAAKXZ; SOS_Task::GetThreadIdNoLock(void)
0x100405241  mov     ebx, eax
0x100405243  mov     rdi, [rsp+68h+var_40]
0x100405248  test    rdi, rdi
0x10040524b  jz      short loc_10040528F
0x10040524d  mov     rcx, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x100405254  cmp     byte ptr [rcx], 0
0x100405257  jz      short loc_100405280
0x100405259  call    cs:__imp_rand
0x10040525f  mov     r8d, eax
0x100405262  mov     eax, 66666667h
0x100405267  imul    r8d
0x10040526a  sar     edx, 1
0x10040526c  mov     ecx, edx
0x10040526e  shr     ecx, 1Fh
0x100405271  add     edx, ecx
0x100405273  lea     ecx, [rdx+rdx*4]
0x100405276  cmp     r8d, ecx
0x100405279  jnz     short loc_100405280
0x10040527b  call    ?UpdateStatSnapshot@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXXZ; Spinlock<11,2,268435714>::UpdateStatSnapshot(void)
0x100405280  mov     [rdi], r15
0x100405283  mov     [rsp+68h+var_40], r15
0x100405288  mov     [rsp+68h+var_38], r15d
0x10040528d  mov     eax, ebx
0x10040528f  mov     rbx, [rsp+68h+arg_18]
0x100405297  add     rsp, 40h
0x10040529b  pop     r15
0x10040529d  pop     r14
0x10040529f  pop     rdi
0x1004052a0  pop     rsi
0x1004052a1  pop     rbp
0x1004052a2  retn
```
