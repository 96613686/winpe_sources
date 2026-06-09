# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180010ea8`
- end: `0x180010ed6`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180010dc0`
- `0x18001dfbc`

## callees

- `0x180010ea8`
- `0x180015fe0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010ecf`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rcx

  LockSemaphore = this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    operator delete(LockSemaphore);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180010ea8  push    rbx
0x180010eaa  sub     rsp, 20h
0x180010eae  mov     rbx, rcx
0x180010eb1  mov     rcx, [rcx+40h]; void *
0x180010eb5  mov     qword ptr [rbx+40h], 0
0x180010ebd  test    rcx, rcx
0x180010ec0  jz      short loc_180010EC7
0x180010ec2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010ec7  mov     rcx, rbx
0x180010eca  add     rsp, 20h
0x180010ece  pop     rbx
0x180010ecf  jmp     cs:__imp_DeleteCriticalSection
```
