# CMuiLoader::~CMuiLoader(void)

- ea: `0x1800210d0`
- end: `0x180021125`
- name: `??1CMuiLoader@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(CMuiLoader *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800210d0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800210e2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800210e2`
- `KERNEL32!DeleteCriticalSection` at `0x180021119`
- `KERNEL32!FreeLibrary` at `0x1800210fc`
- `KERNEL32!FreeLibrary` at `0x1800210fc`

## pseudocode

```c
void __fastcall CMuiLoader::~CMuiLoader(CMuiLoader *this)
{
  void *v2; // rcx
  HMODULE v3; // rcx

  v2 = (void *)*((_QWORD *)this + 6);
  if ( v2 )
  {
    operator delete(v2);
    *((_QWORD *)this + 6) = 0;
  }
  v3 = (HMODULE)*((_QWORD *)this + 7);
  if ( v3 )
  {
    FreeLibrary(v3);
    *((_QWORD *)this + 7) = 0;
  }
  *(_DWORD *)this = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1800210d0  push    rbx
0x1800210d2  sub     rsp, 20h
0x1800210d6  mov     rbx, rcx
0x1800210d9  mov     rcx, [rcx+30h]
0x1800210dd  test    rcx, rcx
0x1800210e0  jz      short loc_1800210F3
0x1800210e2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800210e9  nop     dword ptr [rax+rax+00h]
0x1800210ee  and     qword ptr [rbx+30h], 0
0x1800210f3  mov     rcx, [rbx+38h]; hLibModule
0x1800210f7  test    rcx, rcx
0x1800210fa  jz      short loc_18002110D
0x1800210fc  call    cs:__imp_FreeLibrary
0x180021103  nop     dword ptr [rax+rax+00h]
0x180021108  and     qword ptr [rbx+38h], 0
0x18002110d  and     dword ptr [rbx], 0
0x180021110  lea     rcx, [rbx+8]
0x180021114  add     rsp, 20h
0x180021118  pop     rbx
0x180021119  jmp     cs:__imp_DeleteCriticalSection
```
