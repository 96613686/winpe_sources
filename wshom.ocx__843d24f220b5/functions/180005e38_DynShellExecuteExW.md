# DynShellExecuteExW

- ea: `0x180005e38`
- end: `0x180005e98`
- name: `DynShellExecuteExW`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800044fc`

## callees

- `0x180005e38`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180005e71`
- `KERNEL32!GetProcAddress` at `0x180005e71`
- `KERNEL32!LoadLibraryExW` at `0x180005e5c`
- `KERNEL32!LoadLibraryExW` at `0x180005e5c`

## string_xrefs

- `0x180005e4f`: `shell32.dll`

## pseudocode

```c
__int64 __fastcall DynShellExecuteExW(__int64 a1)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_180018BB0;
  if ( qword_180018BB0 )
    return ((__int64 (__fastcall *)(__int64))ProcAddress)(a1);
  Library = LoadLibraryExW(L"shell32.dll", 0, 0x800u);
  if ( Library
    && (ProcAddress = GetProcAddress(Library, "ShellExecuteExW"), (qword_180018BB0 = (__int64)ProcAddress) != 0) )
  {
    return ((__int64 (__fastcall *)(__int64))ProcAddress)(a1);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180005e38  push    rbx
0x180005e3a  sub     rsp, 20h
0x180005e3e  mov     rax, cs:qword_180018BB0
0x180005e45  mov     rbx, rcx
0x180005e48  test    rax, rax
0x180005e4b  jnz     short loc_180005E8B
0x180005e4d  xor     edx, edx; hFile
0x180005e4f  lea     rcx, LibFileName; "shell32.dll"
0x180005e56  mov     r8d, 800h; dwFlags
0x180005e5c  call    cs:__imp_LoadLibraryExW
0x180005e62  test    rax, rax
0x180005e65  jz      short loc_180005E83
0x180005e67  lea     rdx, aShellexecuteex; "ShellExecuteExW"
0x180005e6e  mov     rcx, rax; hModule
0x180005e71  call    cs:__imp_GetProcAddress
0x180005e77  mov     cs:qword_180018BB0, rax
0x180005e7e  test    rax, rax
0x180005e81  jnz     short loc_180005E8B
0x180005e83  xor     eax, eax
0x180005e85  add     rsp, 20h
0x180005e89  pop     rbx
0x180005e8a  retn
0x180005e8b  mov     rcx, rbx
0x180005e8e  add     rsp, 20h
0x180005e92  pop     rbx
0x180005e93  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
