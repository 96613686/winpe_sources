# CWLIDTimerQueue::~CWLIDTimerQueue(void)

- ea: `0x180023328`
- end: `0x180023374`
- name: `??1CWLIDTimerQueue@@UEAA@XZ`
- size: `76`
- prototype: `void __fastcall(CWLIDTimerQueue *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180023110`
- `0x180023940`
- `0x18005d322`

## callees

- `0x180019778`
- `0x180022eb0`
- `0x180023328`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002334b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002335e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002334b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002335e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180023328  push    rbx
0x18002332a  sub     rsp, 20h
0x18002332e  mov     rbx, rcx
0x180023331  lea     rax, ??_7CWLIDTimerQueue@@6B@; const CWLIDTimerQueue::`vftable'
0x180023338  mov     [rcx], rax
0x18002333b  cmp     qword ptr [rcx+30h], 0
0x180023340  jz      short loc_180023347
0x180023342  call    ?Shutdown@CWLIDTimerQueue@@QEAAXXZ; CWLIDTimerQueue::Shutdown(void)
0x180023347  lea     rcx, [rbx+50h]; lpCriticalSection
0x18002334b  call    cs:__imp_DeleteCriticalSection
0x180023351  lea     rcx, [rbx+38h]
0x180023355  call    ??1?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAA@XZ; Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(void)
0x18002335a  lea     rcx, [rbx+8]; lpCriticalSection
0x18002335e  call    cs:__imp_DeleteCriticalSection
0x180023364  lea     rax, ??_7ITimerQueue@@6B@; const ITimerQueue::`vftable'
0x18002336b  mov     [rbx], rax
0x18002336e  add     rsp, 20h
0x180023372  pop     rbx
0x180023373  retn
```
