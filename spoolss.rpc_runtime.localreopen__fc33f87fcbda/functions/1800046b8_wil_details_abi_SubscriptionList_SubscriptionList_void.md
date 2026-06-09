# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1800046b8`
- end: `0x1800046eb`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002718`
- `0x1800076a0`

## callees

- `0x1800046b8`
- `0x1800046f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800046df`

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
0x1800046b8  push    rbx
0x1800046ba  sub     rsp, 20h
0x1800046be  mov     rbx, rcx
0x1800046c1  mov     rcx, [rcx+40h]; this
0x1800046c5  mov     qword ptr [rbx+40h], 0
0x1800046cd  test    rcx, rcx
0x1800046d0  jz      short loc_1800046D7
0x1800046d2  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800046d7  mov     rcx, rbx
0x1800046da  add     rsp, 20h
0x1800046de  pop     rbx
0x1800046df  jmp     cs:__imp_DeleteCriticalSection
```
