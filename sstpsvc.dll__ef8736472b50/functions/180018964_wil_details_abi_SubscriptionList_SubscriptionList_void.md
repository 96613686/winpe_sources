# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180018964`
- end: `0x180018997`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180018868`
- `0x180018898`

## callees

- `0x180018964`
- `0x180019424`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001898b`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this, void *a2)
{
  wil::details *LockSemaphore; // rcx

  LockSemaphore = (wil::details *)this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    wil::details::FreeProcessHeap(LockSemaphore, a2);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180018964  push    rbx
0x180018966  sub     rsp, 20h
0x18001896a  mov     rbx, rcx
0x18001896d  mov     rcx, [rcx+40h]; this
0x180018971  mov     qword ptr [rbx+40h], 0
0x180018979  test    rcx, rcx
0x18001897c  jz      short loc_180018983
0x18001897e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180018983  mov     rcx, rbx
0x180018986  add     rsp, 20h
0x18001898a  pop     rbx
0x18001898b  jmp     cs:__imp_DeleteCriticalSection
```
