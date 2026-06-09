# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180014e54`
- end: `0x180014e82`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180014db0`
- `0x180029944`

## callees

- `0x180014e54`
- `0x180021bdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014e7b`

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
0x180014e54  push    rbx
0x180014e56  sub     rsp, 20h
0x180014e5a  mov     rbx, rcx
0x180014e5d  mov     rcx, [rcx+40h]; this
0x180014e61  mov     qword ptr [rbx+40h], 0
0x180014e69  test    rcx, rcx
0x180014e6c  jz      short loc_180014E73
0x180014e6e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180014e73  mov     rcx, rbx
0x180014e76  add     rsp, 20h
0x180014e7a  pop     rbx
0x180014e7b  jmp     cs:__imp_DeleteCriticalSection
```
