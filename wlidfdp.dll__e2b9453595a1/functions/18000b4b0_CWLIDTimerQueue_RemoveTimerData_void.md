# CWLIDTimerQueue::RemoveTimerData(void *)

- ea: `0x18000b4b0`
- end: `0x18000b4e1`
- name: `?RemoveTimerData@CWLIDTimerQueue@@CAXPEAX@Z`
- size: `49`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b080`
- `0x18000b820`

## callees

- `0x18000b424`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b4c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b4c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b4da`

## pseudocode

```c
void __fastcall CWLIDTimerQueue::RemoveTimerData(__int64 a1)
{
  __int64 v2; // rcx

  EnterCriticalSection(&CWLIDTimerQueue::s_CriticalSection);
  ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::RemoveKey(
    v2,
    a1);
  LeaveCriticalSection(&CWLIDTimerQueue::s_CriticalSection);
}

```

## disassembly

```asm
0x18000b4b0  push    rbx
0x18000b4b2  sub     rsp, 20h
0x18000b4b6  mov     rbx, rcx
0x18000b4b9  lea     rcx, ?s_CriticalSection@CWLIDTimerQueue@@0VCCritSecLite@@A; lpCriticalSection
0x18000b4c0  call    cs:__imp_EnterCriticalSection
0x18000b4c6  mov     rdx, rbx
0x18000b4c9  call    ?RemoveKey@?$CAtlMap@PEAXV?$CAutoPtr@VCWLIDTimerParam@CWLIDTimerQueue@@@ATL@@V?$CElementTraits@PEAX@2@V?$CAutoPtrElementTraits@VCWLIDTimerParam@CWLIDTimerQueue@@@2@@ATL@@QEAA_NPEAX@Z; ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::RemoveKey(void *)
0x18000b4ce  lea     rcx, ?s_CriticalSection@CWLIDTimerQueue@@0VCCritSecLite@@A; CCritSecLite CWLIDTimerQueue::s_CriticalSection
0x18000b4d5  add     rsp, 20h
0x18000b4d9  pop     rbx
0x18000b4da  jmp     cs:__imp_LeaveCriticalSection
```
