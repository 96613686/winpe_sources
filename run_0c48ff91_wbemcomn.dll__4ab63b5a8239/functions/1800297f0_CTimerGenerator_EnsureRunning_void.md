# CTimerGenerator::EnsureRunning(void)

- ea: `0x1800297f0`
- end: `0x180029864`
- name: `?EnsureRunning@CTimerGenerator@@AEAAXXZ`
- size: `116`
- prototype: `void __fastcall(CTimerGenerator *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800296e0`

## callees

- `0x180016730`
- `0x1800297f0`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029814`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029814`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180029857`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180029857`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTimerGenerator::EnsureRunning(CTimerGenerator *this)
{
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp+10h] BYREF

  CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)this + 64));
  if ( !*((_QWORD *)this + 13) )
  {
    (*(void (__fastcall **)(CTimerGenerator *))(*(_QWORD *)this + 16LL))(this);
    ThreadId = 0;
    *((_QWORD *)this + 13) = CreateThread(0, 0, CTimerGenerator::SchedulerThread, this, 0, &ThreadId);
  }
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x1800297f0  push    rbx
0x1800297f2  sub     rsp, 30h
0x1800297f6  mov     rbx, rcx
0x1800297f9  lea     rdx, [rcx+40h]; struct _RTL_CRITICAL_SECTION *
0x1800297fd  lea     rcx, [rsp+38h+lpCriticalSection]; this
0x180029802  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180029807  nop
0x180029808  cmp     qword ptr [rbx+68h], 0
0x18002980d  jz      short loc_180029820
0x18002980f  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x180029814  call    cs:__imp_LeaveCriticalSection
0x18002981a  add     rsp, 30h
0x18002981e  pop     rbx
0x18002981f  retn
0x180029820  mov     rax, [rbx]
0x180029823  mov     rcx, rbx
0x180029826  mov     rax, [rax+10h]
0x18002982a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002982f  mov     [rsp+38h+ThreadId], 0
0x180029837  lea     rax, [rsp+38h+ThreadId]
0x18002983c  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180029841  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180029849  mov     r9, rbx; lpParameter
0x18002984c  lea     r8, ?SchedulerThread@CTimerGenerator@@CAKPEAX@Z; lpStartAddress
0x180029853  xor     edx, edx; dwStackSize
0x180029855  xor     ecx, ecx; lpThreadAttributes
0x180029857  call    cs:__imp_CreateThread
0x18002985d  mov     [rbx+68h], rax
0x180029861  jmp     short loc_18002980F
```
