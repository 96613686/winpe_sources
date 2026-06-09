# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000a3dc`
- end: `0x18000a40a`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800097ac`
- `0x18000d58c`

## callees

- `0x18000a3dc`
- `0x18000deec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a403`

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
0x18000a3dc  push    rbx
0x18000a3de  sub     rsp, 20h
0x18000a3e2  mov     rbx, rcx
0x18000a3e5  mov     rcx, [rcx+40h]; this
0x18000a3e9  mov     qword ptr [rbx+40h], 0
0x18000a3f1  test    rcx, rcx
0x18000a3f4  jz      short loc_18000A3FB
0x18000a3f6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000a3fb  mov     rcx, rbx
0x18000a3fe  add     rsp, 20h
0x18000a402  pop     rbx
0x18000a403  jmp     cs:__imp_DeleteCriticalSection
```
