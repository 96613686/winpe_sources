# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180002da0`
- end: `0x180002de6`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `70`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a26c`

## callees

- `0x180002da0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002ddf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002dbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002dbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002dcc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002dcc`

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
0x180002da0  mov     [rsp+arg_0], rbx
0x180002da5  push    rdi
0x180002da6  sub     rsp, 20h
0x180002daa  mov     rdi, [rcx+40h]
0x180002dae  mov     rbx, rcx
0x180002db1  mov     qword ptr [rcx+40h], 0
0x180002db9  test    rdi, rdi
0x180002dbc  jz      short loc_180002DD2
0x180002dbe  call    cs:__imp_GetProcessHeap
0x180002dc4  mov     r8, rdi; lpMem
0x180002dc7  xor     edx, edx; dwFlags
0x180002dc9  mov     rcx, rax; hHeap
0x180002dcc  call    cs:__imp_HeapFree
0x180002dd2  mov     rcx, rbx
0x180002dd5  mov     rbx, [rsp+28h+arg_0]
0x180002dda  add     rsp, 20h
0x180002dde  pop     rdi
0x180002ddf  jmp     cs:__imp_DeleteCriticalSection
```
