# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x140004aec`
- end: `0x140004b1f`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004984`
- `0x1400049b4`

## callees

- `0x140004aec`
- `0x140005774`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140004b13`

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
0x140004aec  push    rbx
0x140004aee  sub     rsp, 20h
0x140004af2  mov     rbx, rcx
0x140004af5  mov     rcx, [rcx+40h]; this
0x140004af9  mov     qword ptr [rbx+40h], 0
0x140004b01  test    rcx, rcx
0x140004b04  jz      short loc_140004B0B
0x140004b06  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140004b0b  mov     rcx, rbx
0x140004b0e  add     rsp, 20h
0x140004b12  pop     rbx
0x140004b13  jmp     cs:__imp_DeleteCriticalSection
```
