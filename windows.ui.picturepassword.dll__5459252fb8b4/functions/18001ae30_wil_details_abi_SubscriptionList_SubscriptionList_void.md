# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18001ae30`
- end: `0x18001ae5e`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ad5c`
- `0x18001ad8c`

## callees

- `0x180006cfc`
- `0x18001ae30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ae57`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this, void *a2)
{
  DirectUI *LockSemaphore; // rcx

  LockSemaphore = (DirectUI *)this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    DirectUI::HFree(LockSemaphore, a2);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18001ae30  push    rbx
0x18001ae32  sub     rsp, 20h
0x18001ae36  mov     rbx, rcx
0x18001ae39  mov     rcx, [rcx+40h]; this
0x18001ae3d  mov     qword ptr [rbx+40h], 0
0x18001ae45  test    rcx, rcx
0x18001ae48  jz      short loc_18001AE4F
0x18001ae4a  call    ?HFree@DirectUI@@YAXPEAX@Z; DirectUI::HFree(void *)
0x18001ae4f  mov     rcx, rbx
0x18001ae52  add     rsp, 20h
0x18001ae56  pop     rbx
0x18001ae57  jmp     cs:__imp_DeleteCriticalSection
```
