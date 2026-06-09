# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180004994`
- end: `0x1800049c2`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800047c8`
- `0x1800047f8`

## callees

- `0x180004994`
- `0x18000576c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800049bb`

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
0x180004994  push    rbx
0x180004996  sub     rsp, 20h
0x18000499a  mov     rbx, rcx
0x18000499d  mov     rcx, [rcx+40h]; this
0x1800049a1  mov     qword ptr [rbx+40h], 0
0x1800049a9  test    rcx, rcx
0x1800049ac  jz      short loc_1800049B3
0x1800049ae  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800049b3  mov     rcx, rbx
0x1800049b6  add     rsp, 20h
0x1800049ba  pop     rbx
0x1800049bb  jmp     cs:__imp_DeleteCriticalSection
```
