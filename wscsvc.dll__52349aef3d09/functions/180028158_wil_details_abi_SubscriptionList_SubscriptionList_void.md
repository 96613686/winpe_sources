# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180028158`
- end: `0x180028186`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180023600`
- `0x18002c358`

## callees

- `0x180026b0c`
- `0x180028158`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002817f`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rcx

  LockSemaphore = this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    MemoryFree(LockSemaphore);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180028158  push    rbx
0x18002815a  sub     rsp, 20h
0x18002815e  mov     rbx, rcx
0x180028161  mov     rcx, [rcx+40h]; void *
0x180028165  mov     qword ptr [rbx+40h], 0
0x18002816d  test    rcx, rcx
0x180028170  jz      short loc_180028177
0x180028172  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180028177  mov     rcx, rbx
0x18002817a  add     rsp, 20h
0x18002817e  pop     rbx
0x18002817f  jmp     cs:__imp_DeleteCriticalSection
```
