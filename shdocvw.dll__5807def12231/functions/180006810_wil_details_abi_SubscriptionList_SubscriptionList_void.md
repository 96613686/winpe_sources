# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180006810`
- end: `0x18000683e`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cb4c`

## callees

- `0x180006810`
- `0x18000a6ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006837`

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
0x180006810  push    rbx
0x180006812  sub     rsp, 20h
0x180006816  mov     rbx, rcx
0x180006819  mov     rcx, [rcx+40h]; this
0x18000681d  mov     qword ptr [rbx+40h], 0
0x180006825  test    rcx, rcx
0x180006828  jz      short loc_18000682F
0x18000682a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000682f  mov     rcx, rbx
0x180006832  add     rsp, 20h
0x180006836  pop     rbx
0x180006837  jmp     cs:__imp_DeleteCriticalSection
```
