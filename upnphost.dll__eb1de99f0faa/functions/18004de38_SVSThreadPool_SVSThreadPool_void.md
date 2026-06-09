# SVSThreadPool::~SVSThreadPool(void)

- ea: `0x18004de38`
- end: `0x18004de94`
- name: `??1SVSThreadPool@@QEAA@XZ`
- size: `92`
- prototype: `void __fastcall(SVSThreadPool *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18004df84`

## callees

- `0x180007954`
- `0x18004dd2c`
- `0x18004de38`
- `0x18004e2bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004de8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004de67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004de76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004de67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004de76`

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
0x18004de38  push    rbx
0x18004de3a  sub     rsp, 20h
0x18004de3e  lea     rax, ??_7?$SVSTHeap@_J@@6B@; const SVSTHeap<__int64>::`vftable'
0x18004de45  mov     rbx, rcx
0x18004de48  mov     [rcx], rax
0x18004de4b  call    ?Shutdown@SVSThreadPool@@QEAAKXZ; SVSThreadPool::Shutdown(void)
0x18004de50  mov     rcx, [rbx+40h]; Block
0x18004de54  test    rcx, rcx
0x18004de57  jz      short loc_18004DE5E
0x18004de59  call    svsutil_ReleaseFixedNonEmpty
0x18004de5e  mov     rcx, [rbx+48h]; hObject
0x18004de62  test    rcx, rcx
0x18004de65  jz      short loc_18004DE6D
0x18004de67  call    cs:__imp_CloseHandle
0x18004de6d  mov     rcx, [rbx+50h]; hObject
0x18004de71  test    rcx, rcx
0x18004de74  jz      short loc_18004DE7C
0x18004de76  call    cs:__imp_CloseHandle
0x18004de7c  mov     rcx, rbx
0x18004de7f  call    ??1?$SVSTHeap@_J@@QEAA@XZ; SVSTHeap<__int64>::~SVSTHeap<__int64>(void)
0x18004de84  lea     rcx, [rbx+18h]
0x18004de88  add     rsp, 20h
0x18004de8c  pop     rbx
0x18004de8d  jmp     cs:__imp_DeleteCriticalSection
```
