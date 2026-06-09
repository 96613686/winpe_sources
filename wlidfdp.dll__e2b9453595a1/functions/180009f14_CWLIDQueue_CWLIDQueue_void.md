# CWLIDQueue::~CWLIDQueue(void)

- ea: `0x180009f14`
- end: `0x180009f3e`
- name: `??1CWLIDQueue@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b9e0`

## callees

- `0x180009f44`
- `0x18000b31c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009f37`

## pseudocode

```c
void __fastcall CWLIDQueue::~CWLIDQueue(struct _RTL_CRITICAL_SECTION *this)
{
  CWLIDTimerQueue::~CWLIDTimerQueue((CWLIDTimerQueue *)&this[2].LockCount);
  ATL::CAtlList<CAutoRefPtr<CWLIDItem>,ATL::CElementTraits<CAutoRefPtr<CWLIDItem>>>::RemoveAll(&this[1]);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180009f14  push    rbx
0x180009f16  sub     rsp, 20h
0x180009f1a  mov     rbx, rcx
0x180009f1d  add     rcx, 58h ; 'X'; this
0x180009f21  call    ??1CWLIDTimerQueue@@UEAA@XZ; CWLIDTimerQueue::~CWLIDTimerQueue(void)
0x180009f26  lea     rcx, [rbx+28h]
0x180009f2a  call    ?RemoveAll@?$CAtlList@V?$CAutoRefPtr@VCWLIDItem@@@@V?$CElementTraits@V?$CAutoRefPtr@VCWLIDItem@@@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CAutoRefPtr<CWLIDItem>,ATL::CElementTraits<CAutoRefPtr<CWLIDItem>>>::RemoveAll(void)
0x180009f2f  mov     rcx, rbx
0x180009f32  add     rsp, 20h
0x180009f36  pop     rbx
0x180009f37  jmp     cs:__imp_DeleteCriticalSection
```
