# CMuiLoader::~CMuiLoader(void)

- ea: `0x1800200d0`
- end: `0x18002011e`
- name: `??1CMuiLoader@@QEAA@XZ`
- size: `78`
- prototype: `void __fastcall(CMuiLoader *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800200d0`
- `0x18002e468`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180020112`
- `KERNEL32!FreeLibrary` at `0x1800200f5`
- `KERNEL32!FreeLibrary` at `0x1800200f5`

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
0x1800200d0  push    rbx
0x1800200d2  sub     rsp, 20h
0x1800200d6  mov     rbx, rcx
0x1800200d9  mov     rcx, [rcx+30h]; lpMem
0x1800200dd  test    rcx, rcx
0x1800200e0  jz      short loc_1800200EC
0x1800200e2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800200e7  and     qword ptr [rbx+30h], 0
0x1800200ec  mov     rcx, [rbx+38h]; hLibModule
0x1800200f0  test    rcx, rcx
0x1800200f3  jz      short loc_180020106
0x1800200f5  call    cs:__imp_FreeLibrary
0x1800200fc  nop     dword ptr [rax+rax+00h]
0x180020101  and     qword ptr [rbx+38h], 0
0x180020106  and     dword ptr [rbx], 0
0x180020109  lea     rcx, [rbx+8]
0x18002010d  add     rsp, 20h
0x180020111  pop     rbx
0x180020112  jmp     cs:__imp_DeleteCriticalSection
```
