# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180007d9c`
- end: `0x180007dca`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007ca0`
- `0x180007cd0`

## callees

- `0x180007d9c`
- `0x18000882c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007dc3`

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
0x180007d9c  push    rbx
0x180007d9e  sub     rsp, 20h
0x180007da2  mov     rbx, rcx
0x180007da5  mov     rcx, [rcx+40h]; this
0x180007da9  mov     qword ptr [rbx+40h], 0
0x180007db1  test    rcx, rcx
0x180007db4  jz      short loc_180007DBB
0x180007db6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180007dbb  mov     rcx, rbx
0x180007dbe  add     rsp, 20h
0x180007dc2  pop     rbx
0x180007dc3  jmp     cs:__imp_DeleteCriticalSection
```
