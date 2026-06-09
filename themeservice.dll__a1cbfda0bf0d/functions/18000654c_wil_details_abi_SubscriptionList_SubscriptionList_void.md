# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000654c`
- end: `0x18000657a`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000601c`
- `0x18000a818`

## callees

- `0x18000654c`
- `0x180008afc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006573`

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
0x18000654c  push    rbx
0x18000654e  sub     rsp, 20h
0x180006552  mov     rbx, rcx
0x180006555  mov     rcx, [rcx+40h]; this
0x180006559  mov     qword ptr [rbx+40h], 0
0x180006561  test    rcx, rcx
0x180006564  jz      short loc_18000656B
0x180006566  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000656b  mov     rcx, rbx
0x18000656e  add     rsp, 20h
0x180006572  pop     rbx
0x180006573  jmp     cs:__imp_DeleteCriticalSection
```
