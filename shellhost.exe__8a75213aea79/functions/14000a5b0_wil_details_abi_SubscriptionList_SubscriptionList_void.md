# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x14000a5b0`
- end: `0x14000a5f6`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `70`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000bc78`

## callees

- `0x14000a5b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000a5ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a5ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a5ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a5dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a5dc`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rdi
  HANDLE ProcessHeap; // rax

  LockSemaphore = this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, LockSemaphore);
  }
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x14000a5b0  mov     [rsp+arg_0], rbx
0x14000a5b5  push    rdi
0x14000a5b6  sub     rsp, 20h
0x14000a5ba  mov     rdi, [rcx+40h]
0x14000a5be  mov     rbx, rcx
0x14000a5c1  mov     qword ptr [rcx+40h], 0
0x14000a5c9  test    rdi, rdi
0x14000a5cc  jz      short loc_14000A5E2
0x14000a5ce  call    cs:__imp_GetProcessHeap
0x14000a5d4  mov     r8, rdi; lpMem
0x14000a5d7  xor     edx, edx; dwFlags
0x14000a5d9  mov     rcx, rax; hHeap
0x14000a5dc  call    cs:__imp_HeapFree
0x14000a5e2  mov     rcx, rbx
0x14000a5e5  mov     rbx, [rsp+28h+arg_0]
0x14000a5ea  add     rsp, 20h
0x14000a5ee  pop     rdi
0x14000a5ef  jmp     cs:__imp_DeleteCriticalSection
```
