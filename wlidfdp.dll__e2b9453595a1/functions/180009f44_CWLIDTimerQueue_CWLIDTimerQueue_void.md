# CWLIDTimerQueue::~CWLIDTimerQueue(void)

- ea: `0x180009f44`
- end: `0x180009f90`
- name: `??1CWLIDTimerQueue@@UEAA@XZ`
- size: `76`
- prototype: `void __fastcall(CWLIDTimerQueue *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180009f14`
- `0x18000a0c0`

## callees

- `0x180009da8`
- `0x180009f44`
- `0x18000b5b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009f67`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009f7a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009f67`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009f7a`

## pseudocode

```c
void __fastcall CWLIDTimerQueue::~CWLIDTimerQueue(CWLIDTimerQueue *this)
{
  *(_QWORD *)this = &CWLIDTimerQueue::`vftable';
  if ( *((_QWORD *)this + 6) )
    CWLIDTimerQueue::Shutdown(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>((char *)this + 56);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  *(_QWORD *)this = &ITimerQueue::`vftable';
}

```

## disassembly

```asm
0x180009f44  push    rbx
0x180009f46  sub     rsp, 20h
0x180009f4a  mov     rbx, rcx
0x180009f4d  lea     rax, ??_7CWLIDTimerQueue@@6B@; const CWLIDTimerQueue::`vftable'
0x180009f54  mov     [rcx], rax
0x180009f57  cmp     qword ptr [rcx+30h], 0
0x180009f5c  jz      short loc_180009F63
0x180009f5e  call    ?Shutdown@CWLIDTimerQueue@@QEAAXXZ; CWLIDTimerQueue::Shutdown(void)
0x180009f63  lea     rcx, [rbx+50h]; lpCriticalSection
0x180009f67  call    cs:__imp_DeleteCriticalSection
0x180009f6d  lea     rcx, [rbx+38h]
0x180009f71  call    ??1?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAA@XZ; Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(void)
0x180009f76  lea     rcx, [rbx+8]; lpCriticalSection
0x180009f7a  call    cs:__imp_DeleteCriticalSection
0x180009f80  lea     rax, ??_7ITimerQueue@@6B@; const ITimerQueue::`vftable'
0x180009f87  mov     [rbx], rax
0x180009f8a  add     rsp, 20h
0x180009f8e  pop     rbx
0x180009f8f  retn
```
