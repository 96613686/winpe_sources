# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000db40`
- end: `0x18000db6e`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d9e8`
- `0x18000da18`

## callees

- `0x18000db40`
- `0x18000e6bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000db67`

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
0x18000db40  push    rbx
0x18000db42  sub     rsp, 20h
0x18000db46  mov     rbx, rcx
0x18000db49  mov     rcx, [rcx+40h]; this
0x18000db4d  mov     qword ptr [rbx+40h], 0
0x18000db55  test    rcx, rcx
0x18000db58  jz      short loc_18000DB5F
0x18000db5a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000db5f  mov     rcx, rbx
0x18000db62  add     rsp, 20h
0x18000db66  pop     rbx
0x18000db67  jmp     cs:__imp_DeleteCriticalSection
```
