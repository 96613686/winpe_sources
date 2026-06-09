# SOS_Task::GetWaitInformationImpl(SpinlockHolder<11,2,268435714> &,SOS_WaitInfo *,SOS_Ticks<InterruptTicks<unsigned __int64>,-3> *)

- ea: `0x100464c60`
- end: `0x100464e8a`
- name: `?GetWaitInformationImpl@SOS_Task@@AEAA?AW4SOS_RESULT@@AEAV?$SpinlockHolder@$0L@$01$0BAAAABAC@@@PEAVSOS_WaitInfo@@PEAV?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1004661f0`

## callees

- `0x10040c7a0`
- `0x10040c9e0`
- `0x100464c60`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100464d63`
- `KERNEL32!QueryPerformanceCounter` at `0x100464db9`
- `KERNEL32!QueryPerformanceCounter` at `0x100464d63`
- `KERNEL32!QueryPerformanceCounter` at `0x100464db9`
- `sqldk!?WaitForWorkerWaitInfo@SOS_Scheduler@@KAPEBVSOS_WaitInfo@@XZ` at `0x100464c8a`
- `sqldk!?WaitForWorkerWaitInfo@SOS_Scheduler@@KAPEBVSOS_WaitInfo@@XZ` at `0x100464c8a`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100464d53`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100464da5`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100464d78`
- `sqldk!SystemThread_TlsIndex` at `0x100464d25`
- `sqldk!SystemThread_TlsOffset` at `0x100464d2e`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100464d00`

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
0x100464c60  push    rbp
0x100464c62  push    rdi
0x100464c63  push    r13
0x100464c65  push    r15
0x100464c67  sub     rsp, 48h
0x100464c6b  mov     eax, [rcx+0B8h]
0x100464c71  lea     r15, [rsp+68h+var_48]
0x100464c76  test    r9, r9
0x100464c79  mov     rbp, r8
0x100464c7c  mov     r13, rdx
0x100464c7f  mov     rdi, rcx
0x100464c82  cmovnz  r15, r9
0x100464c86  test    eax, eax
0x100464c88  jnz     short loc_100464CBD
0x100464c8a  call    cs:__imp_?WaitForWorkerWaitInfo@SOS_Scheduler@@KAPEBVSOS_WaitInfo@@XZ; SOS_Scheduler::WaitForWorkerWaitInfo(void)
0x100464c90  movups  xmm0, xmmword ptr [rax]
0x100464c93  movups  xmmword ptr [rbp+0], xmm0
0x100464c97  movups  xmm1, xmmword ptr [rax+10h]
0x100464c9b  movups  xmmword ptr [rbp+10h], xmm1
0x100464c9f  movsd   xmm0, qword ptr [rax+20h]
0x100464ca4  movsd   qword ptr [rbp+20h], xmm0
0x100464ca9  mov     rax, [rdi+38h]
0x100464cad  mov     [r15], rax
0x100464cb0  xor     eax, eax
0x100464cb2  add     rsp, 48h
0x100464cb6  pop     r15
0x100464cb8  pop     r13
0x100464cba  pop     rdi
0x100464cbb  pop     rbp
0x100464cbc  retn
0x100464cbd  mov     [rsp+68h+arg_8], rbx
0x100464cc2  mov     [rsp+68h+var_30], r12
0x100464cc7  mov     [rsp+68h+var_38], r14
0x100464ccc  lea     r14, [rcx+90h]
0x100464cd3  mov     [rdx], r14
0x100464cd6  xor     edx, edx
0x100464cd8  mov     eax, gs:48h
0x100464ce0  mov     ebx, edx
0x100464ce2  mov     r12d, eax
0x100464ce5  mov     eax, [r14]
0x100464ce8  test    eax, eax
0x100464cea  jnz     short loc_100464D00
0x100464cec  xor     eax, eax
0x100464cee  lock cmpxchg [r14], r12
0x100464cf3  mov     eax, edx
0x100464cf5  setz    al
0x100464cf8  test    eax, eax
0x100464cfa  jnz     loc_100464DF3
0x100464d00  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100464d07  mov     [rsp+68h+var_28], rsi
0x100464d0c  mov     rsi, rdx
0x100464d0f  mov     ecx, [rax]
0x100464d11  and     ecx, 84h
0x100464d17  cmp     cl, 84h
0x100464d1a  jnz     short loc_100464D78
0x100464d1c  mov     rdx, gs:58h
0x100464d25  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100464d2c  mov     ecx, [rax]
0x100464d2e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100464d35  mov     r8d, [rax]
0x100464d38  add     r8, [rdx+rcx*8]
0x100464d3c  jz      short loc_100464D4E
0x100464d3e  cmp     [r8+110h], r8
0x100464d45  jnz     short loc_100464D4E
0x100464d47  mov     rsi, [r8+100h]
0x100464d4e  test    rsi, rsi
0x100464d51  jz      short loc_100464D78
0x100464d53  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100464d5a  cmp     [rax], ebx
0x100464d5c  jz      short loc_100464D70
0x100464d5e  lea     rcx, [rsp+68h+PerformanceCount]; lpPerformanceCount
0x100464d63  call    cs:__imp_QueryPerformanceCounter
0x100464d69  mov     rbx, qword ptr [rsp+68h+PerformanceCount]
0x100464d6e  jmp     short loc_100464D78
0x100464d70  mov     rbx, ds:7FFE0008h
0x100464d78  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100464d7f  mov     rcx, r14
0x100464d82  cmp     byte ptr [rax+0C7h], 0
0x100464d89  jge     short loc_100464D98
0x100464d8b  mov     r8, r12
0x100464d8e  mov     rdx, rsi
0x100464d91  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100464d96  jmp     short loc_100464DA0
0x100464d98  mov     rdx, r12
0x100464d9b  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100464da0  test    rsi, rsi
0x100464da3  jz      short loc_100464DEC
0x100464da5  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100464dac  cmp     dword ptr [rax], 0
0x100464daf  jz      short loc_100464DC9
0x100464db1  lea     rcx, [rsp+68h+arg_18]; lpPerformanceCount
0x100464db9  call    cs:__imp_QueryPerformanceCounter
0x100464dbf  mov     rax, qword ptr [rsp+68h+arg_18]
0x100464dc7  jmp     short loc_100464DD1
0x100464dc9  mov     rax, ds:7FFE0008h
0x100464dd1  mov     rcx, rax
0x100464dd4  mov     edx, 0
0x100464dd9  sub     rcx, rbx
0x100464ddc  cmp     rax, rbx
0x100464ddf  cmovb   rcx, rdx
0x100464de3  add     [rsi+0C78h], rcx
0x100464dea  jmp     short loc_100464DEE
0x100464dec  xor     edx, edx
0x100464dee  mov     rsi, [rsp+68h+var_28]
0x100464df3  mov     r14, [rsp+68h+var_38]
0x100464df8  mov     r12, [rsp+68h+var_30]
0x100464dfd  mov     rbx, [rsp+68h+arg_8]
0x100464e02  mov     dword ptr [r13+8], 1
0x100464e0a  mov     eax, [rdi+0B8h]
0x100464e10  cmp     eax, 2
0x100464e13  jz      short loc_100464E77
0x100464e15  mov     rcx, [rdi+0C8h]
0x100464e1c  test    rcx, rcx
0x100464e1f  jnz     short loc_100464E40
0x100464e21  mov     rcx, [rdi+100h]
0x100464e28  test    rcx, rcx
0x100464e2b  jz      short loc_100464E77
0x100464e2d  mov     rcx, [rdi+rcx*8+0C8h]
0x100464e35  test    rcx, rcx
0x100464e38  jz      short loc_100464E77
0x100464e3a  mov     rax, [rcx+28h]
0x100464e3e  jmp     short loc_100464E4E
0x100464e40  mov     rax, [rdi+98h]
0x100464e47  mov     rax, [rax+88h]
0x100464e4e  mov     [r15], rax
0x100464e51  xor     eax, eax
0x100464e53  movups  xmm0, xmmword ptr [rcx]
0x100464e56  movups  xmmword ptr [rbp+0], xmm0
0x100464e5a  movups  xmm1, xmmword ptr [rcx+10h]
0x100464e5e  movups  xmmword ptr [rbp+10h], xmm1
0x100464e62  movsd   xmm0, qword ptr [rcx+20h]
0x100464e67  movsd   qword ptr [rbp+20h], xmm0
0x100464e6c  add     rsp, 48h
0x100464e70  pop     r15
0x100464e72  pop     r13
0x100464e74  pop     rdi
0x100464e75  pop     rbp
0x100464e76  retn
0x100464e77  mov     [r15], rdx
0x100464e7a  mov     eax, 80000000h
0x100464e7f  add     rsp, 48h
0x100464e83  pop     r15
0x100464e85  pop     r13
0x100464e87  pop     rdi
0x100464e88  pop     rbp
0x100464e89  retn
```
