# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1800364ec`
- end: `0x18003651a`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800363f0`
- `0x180036420`

## callees

- `0x1800364ec`
- `0x180037f0c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180036513`

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
0x1800364ec  push    rbx
0x1800364ee  sub     rsp, 20h
0x1800364f2  mov     rbx, rcx
0x1800364f5  mov     rcx, [rcx+40h]; this
0x1800364f9  mov     qword ptr [rbx+40h], 0
0x180036501  test    rcx, rcx
0x180036504  jz      short loc_18003650B
0x180036506  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18003650b  mov     rcx, rbx
0x18003650e  add     rsp, 20h
0x180036512  pop     rbx
0x180036513  jmp     cs:__imp_DeleteCriticalSection
```
