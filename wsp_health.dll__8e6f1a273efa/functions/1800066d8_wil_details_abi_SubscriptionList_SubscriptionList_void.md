# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1800066d8`
- end: `0x18000670b`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006570`
- `0x1800065a0`

## callees

- `0x1800066d8`
- `0x1800072a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800066ff`

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
0x1800066d8  push    rbx
0x1800066da  sub     rsp, 20h
0x1800066de  mov     rbx, rcx
0x1800066e1  mov     rcx, [rcx+40h]; void *
0x1800066e5  mov     qword ptr [rbx+40h], 0
0x1800066ed  test    rcx, rcx
0x1800066f0  jz      short loc_1800066F7
0x1800066f2  call    ??3RefCounted@cxl@@SAXPEAX@Z; cxl::RefCounted::operator delete(void *)
0x1800066f7  mov     rcx, rbx
0x1800066fa  add     rsp, 20h
0x1800066fe  pop     rbx
0x1800066ff  jmp     cs:__imp_DeleteCriticalSection
```
