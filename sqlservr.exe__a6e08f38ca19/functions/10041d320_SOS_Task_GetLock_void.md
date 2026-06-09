# SOS_Task::GetLock(void)

- ea: `0x10041d320`
- end: `0x10041d44a`
- name: `?GetLock@SOS_Task@@AEAAXXZ`
- size: `298`
- prototype: `void __fastcall(SOS_Task *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x100413d90`

## callees

- `0x100408320`
- `0x100408560`
- `0x10041d320`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10041d3bf`
- `KERNEL32!QueryPerformanceCounter` at `0x10041d412`
- `KERNEL32!QueryPerformanceCounter` at `0x10041d3bf`
- `KERNEL32!QueryPerformanceCounter` at `0x10041d412`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10041d3d4`
- `sqldk!SystemThread_TlsOffset` at `0x10041d38a`
- `sqldk!SystemThread_TlsIndex` at `0x10041d381`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041d3af`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041d401`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10041d35c`

## pseudocode

```c
void __fastcall SOS_Task::GetLock(SOS_Task *this)
{
  volatile signed __int64 *v1; // rsi
  signed __int64 UniqueThread_low; // rbp
  LARGE_INTEGER v3; // rbx
  __int64 v4; // rdi
  __int64 v5; // r8
  LARGE_INTEGER v6; // rax
  LONGLONG v7; // rcx
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp+8h] BYREF
  LARGE_INTEGER v9; // [rsp+58h] [rbp+10h] BYREF

  v1 = (volatile signed __int64 *)((char *)this + 144);
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  v3.QuadPart = 0;
  if ( *((_DWORD *)this + 36) || _InterlockedCompareExchange64(v1, UniqueThread_low, 0) )
  {
    v4 = 0;
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
    {
      v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( v5 && *(_QWORD *)(v5 + 272) == v5 )
        v4 = *(_QWORD *)(v5 + 256);
      if ( v4 )
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
      Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v1, UniqueThread_low);
    else
      Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v1, v4, UniqueThread_low);
    if ( v4 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v9);
        v6 = v9;
      }
      else
      {
        v6.QuadPart = MEMORY[0x7FFE0008];
      }
      v7 = v6.QuadPart - v3.QuadPart;
      if ( v6.QuadPart < (unsigned __int64)v3.QuadPart )
        v7 = 0;
      *(_QWORD *)(v4 + 3192) += v7;
    }
  }
}

```

## disassembly

```asm
0x10041d320  push    rbx
0x10041d322  push    rbp
0x10041d323  push    rsi
0x10041d324  push    r14
0x10041d326  sub     rsp, 28h
0x10041d32a  mov     eax, gs:48h
0x10041d332  lea     rsi, [rcx+90h]
0x10041d339  xor     r14d, r14d
0x10041d33c  mov     ebp, eax
0x10041d33e  mov     eax, [rsi]
0x10041d340  mov     ebx, r14d
0x10041d343  test    eax, eax
0x10041d345  jnz     short loc_10041D35C
0x10041d347  xor     eax, eax
0x10041d349  lock cmpxchg [rsi], rbp
0x10041d34e  mov     eax, r14d
0x10041d351  setz    al
0x10041d354  test    eax, eax
0x10041d356  jnz     loc_10041D440
0x10041d35c  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10041d363  mov     [rsp+48h+var_28], rdi
0x10041d368  mov     rdi, r14
0x10041d36b  mov     ecx, [rax]
0x10041d36d  and     ecx, 84h
0x10041d373  cmp     cl, 84h
0x10041d376  jnz     short loc_10041D3D4
0x10041d378  mov     rdx, gs:58h
0x10041d381  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041d388  mov     ecx, [rax]
0x10041d38a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041d391  mov     r8d, [rax]
0x10041d394  add     r8, [rdx+rcx*8]
0x10041d398  jz      short loc_10041D3AA
0x10041d39a  cmp     [r8+110h], r8
0x10041d3a1  jnz     short loc_10041D3AA
0x10041d3a3  mov     rdi, [r8+100h]
0x10041d3aa  test    rdi, rdi
0x10041d3ad  jz      short loc_10041D3D4
0x10041d3af  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10041d3b6  cmp     [rax], ebx
0x10041d3b8  jz      short loc_10041D3CC
0x10041d3ba  lea     rcx, [rsp+48h+PerformanceCount]; lpPerformanceCount
0x10041d3bf  call    cs:__imp_QueryPerformanceCounter
0x10041d3c5  mov     rbx, qword ptr [rsp+48h+PerformanceCount]
0x10041d3ca  jmp     short loc_10041D3D4
0x10041d3cc  mov     rbx, ds:7FFE0008h
0x10041d3d4  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10041d3db  mov     rcx, rsi
0x10041d3de  cmp     [rax+0C7h], r14b
0x10041d3e5  jge     short loc_10041D3F4
0x10041d3e7  mov     r8, rbp
0x10041d3ea  mov     rdx, rdi
0x10041d3ed  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10041d3f2  jmp     short loc_10041D3FC
0x10041d3f4  mov     rdx, rbp
0x10041d3f7  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10041d3fc  test    rdi, rdi
0x10041d3ff  jz      short loc_10041D43B
0x10041d401  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10041d408  cmp     [rax], r14d
0x10041d40b  jz      short loc_10041D41F
0x10041d40d  lea     rcx, [rsp+48h+arg_8]; lpPerformanceCount
0x10041d412  call    cs:__imp_QueryPerformanceCounter
0x10041d418  mov     rax, qword ptr [rsp+48h+arg_8]
0x10041d41d  jmp     short loc_10041D427
0x10041d41f  mov     rax, ds:7FFE0008h
0x10041d427  mov     rcx, rax
0x10041d42a  sub     rcx, rbx
0x10041d42d  cmp     rax, rbx
0x10041d430  cmovb   rcx, r14
0x10041d434  add     [rdi+0C78h], rcx
0x10041d43b  mov     rdi, [rsp+48h+var_28]
0x10041d440  add     rsp, 28h
0x10041d444  pop     r14
0x10041d446  pop     rsi
0x10041d447  pop     rbp
0x10041d448  pop     rbx
0x10041d449  retn
```
