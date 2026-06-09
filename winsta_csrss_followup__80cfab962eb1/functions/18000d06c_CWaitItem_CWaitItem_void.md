# CWaitItem::~CWaitItem(void)

- ea: `0x18000d06c`
- end: `0x18000d0f6`
- name: `??1CWaitItem@@UEAA@XZ`
- size: `138`
- prototype: `void __fastcall(CWaitItem *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cfa0`
- `0x18000d030`
- `0x18000d200`
- `0x18002a934`
- `0x1800317d0`

## callees

- `0x1800065f0`
- `0x18000d06c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000d0cb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000d0cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d0e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d0e8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d08f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d08f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d0a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d0a7`

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
0x18000d06c  push    rbx
0x18000d06e  sub     rsp, 20h
0x18000d072  cmp     dword ptr [rcx+608h], 0
0x18000d079  lea     rax, ??_7CWaitItem@@6B@; const CWaitItem::`vftable'
0x18000d080  mov     [rcx], rax
0x18000d083  mov     rbx, rcx
0x18000d086  jz      short loc_18000D09B
0x18000d088  add     rcx, 5E0h; lpCriticalSection
0x18000d08f  call    cs:__imp_DeleteCriticalSection
0x18000d096  nop     dword ptr [rax+rax+00h]
0x18000d09b  mov     rcx, [rbx+5D8h]; hObject
0x18000d0a2  test    rcx, rcx
0x18000d0a5  jz      short loc_18000D0B3
0x18000d0a7  call    cs:__imp_CloseHandle
0x18000d0ae  nop     dword ptr [rax+rax+00h]
0x18000d0b3  mov     rcx, [rbx+628h]; hMem
0x18000d0ba  test    rcx, rcx
0x18000d0bd  jnz     short loc_18000D0E8
0x18000d0bf  mov     rcx, [rbx+5D0h]; hLibModule
0x18000d0c6  test    rcx, rcx
0x18000d0c9  jz      short loc_18000D0D7
0x18000d0cb  call    cs:__imp_FreeLibrary
0x18000d0d2  nop     dword ptr [rax+rax+00h]
0x18000d0d7  lea     rcx, [rbx+618h]; this
0x18000d0de  add     rsp, 20h
0x18000d0e2  pop     rbx
0x18000d0e3  jmp     ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000d0e8  call    cs:__imp_LocalFree
0x18000d0ef  nop     dword ptr [rax+rax+00h]
0x18000d0f4  jmp     short loc_18000D0BF
```
