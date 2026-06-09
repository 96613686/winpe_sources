# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180016c70`
- end: `0x180016ccb`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `91`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180024e48`
- `0x18003e290`
- `0x18003e2d0`
- `0x18003ef91`
- `0x18003efc0`
- `0x18003fc5a`
- `0x18003fe27`

## callees

- `0x180016c70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016cb9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016cb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016caf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016caf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016ca1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016ca1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(LPCRITICAL_SECTION lpCriticalSection)
{
  HANDLE LockSemaphore; // rbx
  HANDLE ProcessHeap; // rax

  LockSemaphore = lpCriticalSection[1].LockSemaphore;
  lpCriticalSection[1].LockSemaphore = 0;
  if ( LockSemaphore )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, LockSemaphore);
  }
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180016c70  mov     [rsp+arg_18], rbx
0x180016c75  mov     [rsp+arg_0], rcx
0x180016c7a  push    rdi
0x180016c7b  sub     rsp, 20h
0x180016c7f  mov     rdi, rcx
0x180016c82  lea     rax, [rcx+28h]
0x180016c86  mov     [rsp+28h+arg_8], rax
0x180016c8b  mov     [rsp+28h+arg_10], rax
0x180016c90  mov     rbx, [rax+18h]
0x180016c94  mov     qword ptr [rax+18h], 0
0x180016c9c  test    rbx, rbx
0x180016c9f  jz      short loc_180016CB6
0x180016ca1  call    cs:__imp_GetProcessHeap
0x180016ca7  mov     rcx, rax; hHeap
0x180016caa  mov     r8, rbx; lpMem
0x180016cad  xor     edx, edx; dwFlags
0x180016caf  call    cs:__imp_HeapFree
0x180016cb5  nop
0x180016cb6  mov     rcx, rdi; lpCriticalSection
0x180016cb9  call    cs:__imp_DeleteCriticalSection
0x180016cbf  nop
0x180016cc0  mov     rbx, [rsp+28h+arg_18]
0x180016cc5  add     rsp, 20h
0x180016cc9  pop     rdi
0x180016cca  retn
```
