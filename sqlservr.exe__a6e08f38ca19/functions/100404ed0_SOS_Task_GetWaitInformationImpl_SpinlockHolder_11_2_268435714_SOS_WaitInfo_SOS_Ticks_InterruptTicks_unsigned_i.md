# SOS_Task::GetWaitInformationImpl(SpinlockHolder<11,2,268435714> &,SOS_WaitInfo *,SOS_Ticks<InterruptTicks<unsigned __int64>,-3> *)

- ea: `0x100404ed0`
- end: `0x1004050fa`
- name: `?GetWaitInformationImpl@SOS_Task@@AEAA?AW4SOS_RESULT@@AEAV?$SpinlockHolder@$0L@$01$0BAAAABAC@@@PEAVSOS_WaitInfo@@PEAV?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x100406750`

## callees

- `0x100404ed0`
- `0x100408320`
- `0x100408560`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100404fd3`
- `KERNEL32!QueryPerformanceCounter` at `0x100405029`
- `KERNEL32!QueryPerformanceCounter` at `0x100404fd3`
- `KERNEL32!QueryPerformanceCounter` at `0x100405029`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100404fe8`
- `sqldk!SystemThread_TlsOffset` at `0x100404f9e`
- `sqldk!SystemThread_TlsIndex` at `0x100404f95`
- `sqldk!?WaitForWorkerWaitInfo@SOS_Scheduler@@KAPEBVSOS_WaitInfo@@XZ` at `0x100404efa`
- `sqldk!?WaitForWorkerWaitInfo@SOS_Scheduler@@KAPEBVSOS_WaitInfo@@XZ` at `0x100404efa`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100404fc3`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100405015`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100404f70`

## pseudocode

```c
__int64 __fastcall SOS_Task::GetWaitInformationImpl(__int64 a1, __int64 a2, __int64 a3, char *a4)
{
  char *v4; // r15
  __int64 v8; // rax
  __int64 result; // rax
  volatile signed __int64 *v10; // r14
  LARGE_INTEGER v11; // rbx
  signed __int64 UniqueThread_low; // r12
  __int64 v13; // rsi
  __int64 v14; // r8
  LARGE_INTEGER v15; // rax
  LONGLONG v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  char v20; // [rsp+20h] [rbp-48h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+70h] [rbp+8h] BYREF
  LARGE_INTEGER v22; // [rsp+88h] [rbp+20h] BYREF

  v4 = &v20;
  if ( a4 )
    v4 = a4;
  if ( !*(_DWORD *)(a1 + 184) )
  {
    v8 = SOS_Scheduler::WaitForWorkerWaitInfo();
    *(_OWORD *)a3 = *(_OWORD *)v8;
    *(_OWORD *)(a3 + 16) = *(_OWORD *)(v8 + 16);
    *(_QWORD *)(a3 + 32) = *(_QWORD *)(v8 + 32);
    *(_QWORD *)v4 = *(_QWORD *)(a1 + 56);
    return 0;
  }
  v10 = (volatile signed __int64 *)(a1 + 144);
  *(_QWORD *)a2 = a1 + 144;
  v11.QuadPart = 0;
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( *(_DWORD *)(a1 + 144) || _InterlockedCompareExchange64(v10, UniqueThread_low, 0) )
  {
    v13 = 0;
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
    {
      v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( v14 && *(_QWORD *)(v14 + 272) == v14 )
        v13 = *(_QWORD *)(v14 + 256);
      if ( v13 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v11 = PerformanceCount;
        }
        else
        {
          v11.QuadPart = MEMORY[0x7FFE0008];
        }
      }
    }
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v10, UniqueThread_low);
    else
      Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v10, v13, UniqueThread_low);
    if ( v13 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v22);
        v15 = v22;
      }
      else
      {
        v15.QuadPart = MEMORY[0x7FFE0008];
      }
      v16 = v15.QuadPart - v11.QuadPart;
      if ( v15.QuadPart < (unsigned __int64)v11.QuadPart )
        v16 = 0;
      *(_QWORD *)(v13 + 3192) += v16;
    }
  }
  *(_DWORD *)(a2 + 8) = 1;
  if ( *(_DWORD *)(a1 + 184) != 2 )
  {
    v17 = *(_QWORD *)(a1 + 200);
    if ( v17 )
    {
      v19 = *(_QWORD *)(*(_QWORD *)(a1 + 152) + 136LL);
      goto LABEL_31;
    }
    v18 = *(_QWORD *)(a1 + 256);
    if ( v18 )
    {
      v17 = *(_QWORD *)(a1 + 8 * v18 + 200);
      if ( v17 )
      {
        v19 = *(_QWORD *)(v17 + 40);
LABEL_31:
        *(_QWORD *)v4 = v19;
        result = 0;
        *(_OWORD *)a3 = *(_OWORD *)v17;
        *(_OWORD *)(a3 + 16) = *(_OWORD *)(v17 + 16);
        *(_QWORD *)(a3 + 32) = *(_QWORD *)(v17 + 32);
        return result;
      }
    }
  }
  *(_QWORD *)v4 = 0;
  return 0x80000000LL;
}

```

## disassembly

```asm
0x100404ed0  push    rbp
0x100404ed2  push    rdi
0x100404ed3  push    r13
0x100404ed5  push    r15
0x100404ed7  sub     rsp, 48h
0x100404edb  mov     eax, [rcx+0B8h]
0x100404ee1  lea     r15, [rsp+68h+var_48]
0x100404ee6  test    r9, r9
0x100404ee9  mov     rbp, r8
0x100404eec  mov     r13, rdx
0x100404eef  mov     rdi, rcx
0x100404ef2  cmovnz  r15, r9
0x100404ef6  test    eax, eax
0x100404ef8  jnz     short loc_100404F2D
0x100404efa  call    cs:__imp_?WaitForWorkerWaitInfo@SOS_Scheduler@@KAPEBVSOS_WaitInfo@@XZ; SOS_Scheduler::WaitForWorkerWaitInfo(void)
0x100404f00  movups  xmm0, xmmword ptr [rax]
0x100404f03  movups  xmmword ptr [rbp+0], xmm0
0x100404f07  movups  xmm1, xmmword ptr [rax+10h]
0x100404f0b  movups  xmmword ptr [rbp+10h], xmm1
0x100404f0f  movsd   xmm0, qword ptr [rax+20h]
0x100404f14  movsd   qword ptr [rbp+20h], xmm0
0x100404f19  mov     rax, [rdi+38h]
0x100404f1d  mov     [r15], rax
0x100404f20  xor     eax, eax
0x100404f22  add     rsp, 48h
0x100404f26  pop     r15
0x100404f28  pop     r13
0x100404f2a  pop     rdi
0x100404f2b  pop     rbp
0x100404f2c  retn
0x100404f2d  mov     [rsp+68h+arg_8], rbx
0x100404f32  mov     [rsp+68h+var_30], r12
0x100404f37  mov     [rsp+68h+var_38], r14
0x100404f3c  lea     r14, [rcx+90h]
0x100404f43  mov     [rdx], r14
0x100404f46  xor     edx, edx
0x100404f48  mov     eax, gs:48h
0x100404f50  mov     ebx, edx
0x100404f52  mov     r12d, eax
0x100404f55  mov     eax, [r14]
0x100404f58  test    eax, eax
0x100404f5a  jnz     short loc_100404F70
0x100404f5c  xor     eax, eax
0x100404f5e  lock cmpxchg [r14], r12
0x100404f63  mov     eax, edx
0x100404f65  setz    al
0x100404f68  test    eax, eax
0x100404f6a  jnz     loc_100405063
0x100404f70  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100404f77  mov     [rsp+68h+var_28], rsi
0x100404f7c  mov     rsi, rdx
0x100404f7f  mov     ecx, [rax]
0x100404f81  and     ecx, 84h
0x100404f87  cmp     cl, 84h
0x100404f8a  jnz     short loc_100404FE8
0x100404f8c  mov     rdx, gs:58h
0x100404f95  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100404f9c  mov     ecx, [rax]
0x100404f9e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100404fa5  mov     r8d, [rax]
0x100404fa8  add     r8, [rdx+rcx*8]
0x100404fac  jz      short loc_100404FBE
0x100404fae  cmp     [r8+110h], r8
0x100404fb5  jnz     short loc_100404FBE
0x100404fb7  mov     rsi, [r8+100h]
0x100404fbe  test    rsi, rsi
0x100404fc1  jz      short loc_100404FE8
0x100404fc3  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100404fca  cmp     [rax], ebx
0x100404fcc  jz      short loc_100404FE0
0x100404fce  lea     rcx, [rsp+68h+PerformanceCount]; lpPerformanceCount
0x100404fd3  call    cs:__imp_QueryPerformanceCounter
0x100404fd9  mov     rbx, qword ptr [rsp+68h+PerformanceCount]
0x100404fde  jmp     short loc_100404FE8
0x100404fe0  mov     rbx, ds:7FFE0008h
0x100404fe8  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100404fef  mov     rcx, r14
0x100404ff2  cmp     byte ptr [rax+0C7h], 0
0x100404ff9  jge     short loc_100405008
0x100404ffb  mov     r8, r12
0x100404ffe  mov     rdx, rsi
0x100405001  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100405006  jmp     short loc_100405010
0x100405008  mov     rdx, r12
0x10040500b  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100405010  test    rsi, rsi
0x100405013  jz      short loc_10040505C
0x100405015  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040501c  cmp     dword ptr [rax], 0
0x10040501f  jz      short loc_100405039
0x100405021  lea     rcx, [rsp+68h+arg_18]; lpPerformanceCount
0x100405029  call    cs:__imp_QueryPerformanceCounter
0x10040502f  mov     rax, qword ptr [rsp+68h+arg_18]
0x100405037  jmp     short loc_100405041
0x100405039  mov     rax, ds:7FFE0008h
0x100405041  mov     rcx, rax
0x100405044  mov     edx, 0
0x100405049  sub     rcx, rbx
0x10040504c  cmp     rax, rbx
0x10040504f  cmovb   rcx, rdx
0x100405053  add     [rsi+0C78h], rcx
0x10040505a  jmp     short loc_10040505E
0x10040505c  xor     edx, edx
0x10040505e  mov     rsi, [rsp+68h+var_28]
0x100405063  mov     r14, [rsp+68h+var_38]
0x100405068  mov     r12, [rsp+68h+var_30]
0x10040506d  mov     rbx, [rsp+68h+arg_8]
0x100405072  mov     dword ptr [r13+8], 1
0x10040507a  mov     eax, [rdi+0B8h]
0x100405080  cmp     eax, 2
0x100405083  jz      short loc_1004050E7
0x100405085  mov     rcx, [rdi+0C8h]
0x10040508c  test    rcx, rcx
0x10040508f  jnz     short loc_1004050B0
0x100405091  mov     rcx, [rdi+100h]
0x100405098  test    rcx, rcx
0x10040509b  jz      short loc_1004050E7
0x10040509d  mov     rcx, [rdi+rcx*8+0C8h]
0x1004050a5  test    rcx, rcx
0x1004050a8  jz      short loc_1004050E7
0x1004050aa  mov     rax, [rcx+28h]
0x1004050ae  jmp     short loc_1004050BE
0x1004050b0  mov     rax, [rdi+98h]
0x1004050b7  mov     rax, [rax+88h]
0x1004050be  mov     [r15], rax
0x1004050c1  xor     eax, eax
0x1004050c3  movups  xmm0, xmmword ptr [rcx]
0x1004050c6  movups  xmmword ptr [rbp+0], xmm0
0x1004050ca  movups  xmm1, xmmword ptr [rcx+10h]
0x1004050ce  movups  xmmword ptr [rbp+10h], xmm1
0x1004050d2  movsd   xmm0, qword ptr [rcx+20h]
0x1004050d7  movsd   qword ptr [rbp+20h], xmm0
0x1004050dc  add     rsp, 48h
0x1004050e0  pop     r15
0x1004050e2  pop     r13
0x1004050e4  pop     rdi
0x1004050e5  pop     rbp
0x1004050e6  retn
0x1004050e7  mov     [r15], rdx
0x1004050ea  mov     eax, 80000000h
0x1004050ef  add     rsp, 48h
0x1004050f3  pop     r15
0x1004050f5  pop     r13
0x1004050f7  pop     rdi
0x1004050f8  pop     rbp
0x1004050f9  retn
```
