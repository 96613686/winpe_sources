# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000f4ac`
- end: `0x18000f4da`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f3b0`
- `0x180022f84`

## callees

- `0x18000f4ac`
- `0x1800241e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f4d3`

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
0x18000f4ac  push    rbx
0x18000f4ae  sub     rsp, 20h
0x18000f4b2  mov     rbx, rcx
0x18000f4b5  mov     rcx, [rcx+40h]; this
0x18000f4b9  mov     qword ptr [rbx+40h], 0
0x18000f4c1  test    rcx, rcx
0x18000f4c4  jz      short loc_18000F4CB
0x18000f4c6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000f4cb  mov     rcx, rbx
0x18000f4ce  add     rsp, 20h
0x18000f4d2  pop     rbx
0x18000f4d3  jmp     cs:__imp_DeleteCriticalSection
```
