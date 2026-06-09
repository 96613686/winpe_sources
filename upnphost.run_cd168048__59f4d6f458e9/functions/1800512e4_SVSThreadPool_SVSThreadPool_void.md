# SVSThreadPool::~SVSThreadPool(void)

- ea: `0x1800512e4`
- end: `0x180051351`
- name: `??1SVSThreadPool@@QEAA@XZ`
- size: `109`
- prototype: `void __fastcall(SVSThreadPool *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180051448`

## callees

- `0x180034b74`
- `0x1800511d4`
- `0x1800512e4`
- `0x180051798`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051345`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051313`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051328`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051313`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051328`

## pseudocode

```c
void __fastcall SVSThreadPool::~SVSThreadPool(SVSThreadPool *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  *(_QWORD *)this = &SVSTHeap<__int64>::`vftable';
  SVSThreadPool::Shutdown(this);
  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 )
    svsutil_ReleaseFixedNonEmpty(v2);
  v3 = (void *)*((_QWORD *)this + 9);
  if ( v3 )
    CloseHandle(v3);
  v4 = (void *)*((_QWORD *)this + 10);
  if ( v4 )
    CloseHandle(v4);
  SVSTHeap<__int64>::~SVSTHeap<__int64>(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x1800512e4  push    rbx
0x1800512e6  sub     rsp, 20h
0x1800512ea  lea     rax, ??_7?$SVSTHeap@_J@@6B@; const SVSTHeap<__int64>::`vftable'
0x1800512f1  mov     rbx, rcx
0x1800512f4  mov     [rcx], rax
0x1800512f7  call    ?Shutdown@SVSThreadPool@@QEAAKXZ; SVSThreadPool::Shutdown(void)
0x1800512fc  mov     rcx, [rbx+40h]; Block
0x180051300  test    rcx, rcx
0x180051303  jz      short loc_18005130A
0x180051305  call    svsutil_ReleaseFixedNonEmpty
0x18005130a  mov     rcx, [rbx+48h]; hObject
0x18005130e  test    rcx, rcx
0x180051311  jz      short loc_18005131F
0x180051313  call    cs:__imp_CloseHandle
0x18005131a  nop     dword ptr [rax+rax+00h]
0x18005131f  mov     rcx, [rbx+50h]; hObject
0x180051323  test    rcx, rcx
0x180051326  jz      short loc_180051334
0x180051328  call    cs:__imp_CloseHandle
0x18005132f  nop     dword ptr [rax+rax+00h]
0x180051334  mov     rcx, rbx
0x180051337  call    ??1?$SVSTHeap@_J@@QEAA@XZ; SVSTHeap<__int64>::~SVSTHeap<__int64>(void)
0x18005133c  lea     rcx, [rbx+18h]
0x180051340  add     rsp, 20h
0x180051344  pop     rbx
0x180051345  jmp     cs:__imp_DeleteCriticalSection
```
