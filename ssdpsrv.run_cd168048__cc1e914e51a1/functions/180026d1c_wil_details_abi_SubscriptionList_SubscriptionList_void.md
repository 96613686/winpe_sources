# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180026d1c`
- end: `0x180026d4f`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180023694`
- `0x18002a8ac`

## callees

- `0x180026d1c`
- `0x18002b2d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026d43`

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
0x180026d1c  push    rbx
0x180026d1e  sub     rsp, 20h
0x180026d22  mov     rbx, rcx
0x180026d25  mov     rcx, [rcx+40h]; this
0x180026d29  mov     qword ptr [rbx+40h], 0
0x180026d31  test    rcx, rcx
0x180026d34  jz      short loc_180026D3B
0x180026d36  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180026d3b  mov     rcx, rbx
0x180026d3e  add     rsp, 20h
0x180026d42  pop     rbx
0x180026d43  jmp     cs:__imp_DeleteCriticalSection
```
