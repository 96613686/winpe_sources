# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18001102c`
- end: `0x18001105a`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180010f6c`
- `0x180014410`

## callees

- `0x18001102c`
- `0x180014b2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011053`

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
0x18001102c  push    rbx
0x18001102e  sub     rsp, 20h
0x180011032  mov     rbx, rcx
0x180011035  mov     rcx, [rcx+40h]; this
0x180011039  mov     qword ptr [rbx+40h], 0
0x180011041  test    rcx, rcx
0x180011044  jz      short loc_18001104B
0x180011046  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001104b  mov     rcx, rbx
0x18001104e  add     rsp, 20h
0x180011052  pop     rbx
0x180011053  jmp     cs:__imp_DeleteCriticalSection
```
