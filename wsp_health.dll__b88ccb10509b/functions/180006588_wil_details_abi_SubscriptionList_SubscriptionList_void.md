# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180006588`
- end: `0x1800065b6`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006424`
- `0x180006454`

## callees

- `0x180006588`
- `0x18000704c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800065af`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rcx

  LockSemaphore = this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    cxl::RefCounted::operator delete(LockSemaphore);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180006588  push    rbx
0x18000658a  sub     rsp, 20h
0x18000658e  mov     rbx, rcx
0x180006591  mov     rcx, [rcx+40h]; void *
0x180006595  mov     qword ptr [rbx+40h], 0
0x18000659d  test    rcx, rcx
0x1800065a0  jz      short loc_1800065A7
0x1800065a2  call    ??3RefCounted@cxl@@SAXPEAX@Z; cxl::RefCounted::operator delete(void *)
0x1800065a7  mov     rcx, rbx
0x1800065aa  add     rsp, 20h
0x1800065ae  pop     rbx
0x1800065af  jmp     cs:__imp_DeleteCriticalSection
```
