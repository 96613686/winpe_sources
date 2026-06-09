# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180024f64`
- end: `0x180024f92`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180021ce0`
- `0x180028ae0`

## callees

- `0x180024f64`
- `0x18002941c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024f8b`

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
0x180024f64  push    rbx
0x180024f66  sub     rsp, 20h
0x180024f6a  mov     rbx, rcx
0x180024f6d  mov     rcx, [rcx+40h]; this
0x180024f71  mov     qword ptr [rbx+40h], 0
0x180024f79  test    rcx, rcx
0x180024f7c  jz      short loc_180024F83
0x180024f7e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180024f83  mov     rcx, rbx
0x180024f86  add     rsp, 20h
0x180024f8a  pop     rbx
0x180024f8b  jmp     cs:__imp_DeleteCriticalSection
```
