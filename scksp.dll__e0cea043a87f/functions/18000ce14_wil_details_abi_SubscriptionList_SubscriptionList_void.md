# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000ce14`
- end: `0x18000ce42`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ccb8`
- `0x18000cce8`

## callees

- `0x18000ce14`
- `0x18000d9d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ce3b`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rcx

  LockSemaphore = this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    CspFreeH(LockSemaphore);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18000ce14  push    rbx
0x18000ce16  sub     rsp, 20h
0x18000ce1a  mov     rbx, rcx
0x18000ce1d  mov     rcx, [rcx+40h]
0x18000ce21  mov     qword ptr [rbx+40h], 0
0x18000ce29  test    rcx, rcx
0x18000ce2c  jz      short loc_18000CE33
0x18000ce2e  call    CspFreeH
0x18000ce33  mov     rcx, rbx
0x18000ce36  add     rsp, 20h
0x18000ce3a  pop     rbx
0x18000ce3b  jmp     cs:__imp_DeleteCriticalSection
```
