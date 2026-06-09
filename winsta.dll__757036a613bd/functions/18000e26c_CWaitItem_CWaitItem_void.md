# CWaitItem::~CWaitItem(void)

- ea: `0x18000e26c`
- end: `0x18000e2de`
- name: `??1CWaitItem@@UEAA@XZ`
- size: `114`
- prototype: `void __fastcall(CWaitItem *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e148`
- `0x18000e1b8`
- `0x18000e238`
- `0x180028d5c`
- `0x18002ed20`

## callees

- `0x180008290`
- `0x18000e26c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e2bf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e2bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e2d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e2d6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e28f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e28f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e2a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e2a1`

## pseudocode

```c
void __fastcall CWaitItem::~CWaitItem(CWaitItem *this)
{
  bool v1; // zf
  void *v3; // rcx
  void *v4; // rcx
  HMODULE v5; // rcx

  v1 = *((_DWORD *)this + 386) == 0;
  *(_QWORD *)this = &CWaitItem::`vftable';
  if ( !v1 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1504));
  v3 = (void *)*((_QWORD *)this + 187);
  if ( v3 )
    CloseHandle(v3);
  v4 = (void *)*((_QWORD *)this + 197);
  if ( v4 )
    LocalFree(v4);
  v5 = (HMODULE)*((_QWORD *)this + 186);
  if ( v5 )
    FreeLibrary(v5);
  CSmartPublicBinding::~CSmartPublicBinding((CWaitItem *)((char *)this + 1560));
}

```

## disassembly

```asm
0x18000e26c  push    rbx
0x18000e26e  sub     rsp, 20h
0x18000e272  cmp     dword ptr [rcx+608h], 0
0x18000e279  lea     rax, ??_7CWaitItem@@6B@; const CWaitItem::`vftable'
0x18000e280  mov     [rcx], rax
0x18000e283  mov     rbx, rcx
0x18000e286  jz      short loc_18000E295
0x18000e288  add     rcx, 5E0h; lpCriticalSection
0x18000e28f  call    cs:__imp_DeleteCriticalSection
0x18000e295  mov     rcx, [rbx+5D8h]; hObject
0x18000e29c  test    rcx, rcx
0x18000e29f  jz      short loc_18000E2A7
0x18000e2a1  call    cs:__imp_CloseHandle
0x18000e2a7  mov     rcx, [rbx+628h]; hMem
0x18000e2ae  test    rcx, rcx
0x18000e2b1  jnz     short loc_18000E2D6
0x18000e2b3  mov     rcx, [rbx+5D0h]; hLibModule
0x18000e2ba  test    rcx, rcx
0x18000e2bd  jz      short loc_18000E2C5
0x18000e2bf  call    cs:__imp_FreeLibrary
0x18000e2c5  lea     rcx, [rbx+618h]; this
0x18000e2cc  add     rsp, 20h
0x18000e2d0  pop     rbx
0x18000e2d1  jmp     ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000e2d6  call    cs:__imp_LocalFree
0x18000e2dc  jmp     short loc_18000E2B3
```
