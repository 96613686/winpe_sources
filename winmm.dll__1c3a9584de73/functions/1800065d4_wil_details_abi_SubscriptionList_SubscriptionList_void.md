# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1800065d4`
- end: `0x180006604`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006518`
- `0x1800167e0`

## callees

- `0x1800065d4`
- `0x180006a58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800065f6`

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
0x1800065d4  push    rbx
0x1800065d6  sub     rsp, 20h
0x1800065da  mov     rbx, rcx
0x1800065dd  mov     rcx, [rcx+40h]; this
0x1800065e1  mov     qword ptr [rbx+40h], 0
0x1800065e9  test    rcx, rcx
0x1800065ec  jnz     short loc_1800065FD
0x1800065ee  mov     rcx, rbx
0x1800065f1  add     rsp, 20h
0x1800065f5  pop     rbx
0x1800065f6  jmp     cs:__imp_DeleteCriticalSection
0x1800065fd  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180006602  jmp     short loc_1800065EE
```
