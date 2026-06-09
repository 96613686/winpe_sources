# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18002592c`
- end: `0x18002595b`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180025828`
- `0x180025858`

## callees

- `0x1800227ec`
- `0x18002592c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025954`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18002592c  push    rbx
0x18002592e  sub     rsp, 20h
0x180025932  mov     rbx, rcx
0x180025935  mov     rcx, [rcx+40h]; this
0x180025939  mov     qword ptr [rbx+40h], 0
0x180025941  test    rcx, rcx
0x180025944  jz      short loc_18002594C
0x180025946  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18002594b  nop
0x18002594c  mov     rcx, rbx
0x18002594f  add     rsp, 20h
0x180025953  pop     rbx
0x180025954  jmp     cs:__imp_DeleteCriticalSection
```
