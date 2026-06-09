# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180020854`
- end: `0x180020882`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180020794`
- `0x180029c80`

## callees

- `0x18000a100`
- `0x180020854`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002087b`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rcx

  LockSemaphore = this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    operator delete(LockSemaphore);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180020854  push    rbx
0x180020856  sub     rsp, 20h
0x18002085a  mov     rbx, rcx
0x18002085d  mov     rcx, [rcx+40h]; void *
0x180020861  mov     qword ptr [rbx+40h], 0
0x180020869  test    rcx, rcx
0x18002086c  jz      short loc_180020873
0x18002086e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020873  mov     rcx, rbx
0x180020876  add     rsp, 20h
0x18002087a  pop     rbx
0x18002087b  jmp     cs:__imp_DeleteCriticalSection
```
