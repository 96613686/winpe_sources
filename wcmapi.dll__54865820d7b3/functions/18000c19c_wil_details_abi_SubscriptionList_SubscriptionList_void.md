# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000c19c`
- end: `0x18000c1cf`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c074`
- `0x18000c0a4`

## callees

- `0x18000c19c`
- `0x18000d0f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c1c3`

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
0x18000c19c  push    rbx
0x18000c19e  sub     rsp, 20h
0x18000c1a2  mov     rbx, rcx
0x18000c1a5  mov     rcx, [rcx+40h]; this
0x18000c1a9  mov     qword ptr [rbx+40h], 0
0x18000c1b1  test    rcx, rcx
0x18000c1b4  jz      short loc_18000C1BB
0x18000c1b6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000c1bb  mov     rcx, rbx
0x18000c1be  add     rsp, 20h
0x18000c1c2  pop     rbx
0x18000c1c3  jmp     cs:__imp_DeleteCriticalSection
```
