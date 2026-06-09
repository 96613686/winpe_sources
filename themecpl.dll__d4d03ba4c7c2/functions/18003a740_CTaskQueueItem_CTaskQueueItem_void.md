# CTaskQueueItem::~CTaskQueueItem(void)

- ea: `0x18003a740`
- end: `0x18003a7a1`
- name: `??1CTaskQueueItem@@EEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CTaskQueueItem *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003abb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a772`

## pseudocode

```c
void __fastcall CTaskQueueItem::~CTaskQueueItem(CTaskQueueItem *this)
{
  *(_QWORD *)this = &CTaskQueueItem::`vftable'{for `IQueueItem2'};
  *((_QWORD *)this + 1) = &CQueueItem::`vftable'{for `IQueryContinue'};
  CoTaskMemFree(*((LPVOID *)this + 4));
  CoTaskMemFree(*((LPVOID *)this + 5));
  *(_QWORD *)this = &CQueueItem::`vftable'{for `IQueueItem2'};
  *((_QWORD *)this + 1) = &CQueueItem::`vftable'{for `IQueryContinue'};
  _InterlockedDecrement(&g_cLocks);
}

```

## disassembly

```asm
0x18003a740  push    rbx
0x18003a742  sub     rsp, 20h
0x18003a746  lea     rax, ??_7CTaskQueueItem@@6BIQueueItem2@@@; const CTaskQueueItem::`vftable'{for `IQueueItem2'}
0x18003a74d  mov     rbx, rcx
0x18003a750  mov     [rcx], rax
0x18003a753  lea     rax, ??_7CQueueItem@@6BIQueryContinue@@@; const CQueueItem::`vftable'{for `IQueryContinue'}
0x18003a75a  mov     [rcx+8], rax
0x18003a75e  mov     rcx, [rcx+20h]; pv
0x18003a762  call    cs:__imp_CoTaskMemFree
0x18003a769  nop     dword ptr [rax+rax+00h]
0x18003a76e  mov     rcx, [rbx+28h]; pv
0x18003a772  call    cs:__imp_CoTaskMemFree
0x18003a779  nop     dword ptr [rax+rax+00h]
0x18003a77e  lea     rax, ??_7CQueueItem@@6BIQueueItem2@@@; const CQueueItem::`vftable'{for `IQueueItem2'}
0x18003a785  mov     [rbx], rax
0x18003a788  lea     rax, ??_7CQueueItem@@6BIQueryContinue@@@; const CQueueItem::`vftable'{for `IQueryContinue'}
0x18003a78f  mov     [rbx+8], rax
0x18003a793  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x18003a79a  add     rsp, 20h
0x18003a79e  pop     rbx
0x18003a79f  retn
```
