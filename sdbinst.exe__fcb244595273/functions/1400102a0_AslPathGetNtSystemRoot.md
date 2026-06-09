# AslPathGetNtSystemRoot

- ea: `0x1400102a0`
- end: `0x140010313`
- name: `AslPathGetNtSystemRoot`
- size: `115`
- prototype: `__int64()`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000b574`
- `0x14000d8e8`
- `0x14000f3d8`
- `0x1400103d8`
- `0x14001687c`

## callees

- `0x1400102a0`
- `0x14002f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400102e2`
- `KERNEL32!GetProcAddress` at `0x1400102e2`
- `KERNEL32!FreeLibrary` at `0x1400102f8`
- `KERNEL32!FreeLibrary` at `0x1400102f8`
- `KERNEL32!LoadLibraryExW` at `0x1400102ca`
- `KERNEL32!LoadLibraryExW` at `0x1400102ca`

## string_xrefs

- `0x1400102b8`: `ntdll.dll`

## pseudocode

```c
__int64 AslPathGetNtSystemRoot()
{
  __int64 v0; // rbx
  HMODULE Library; // rax
  HMODULE v2; // rdi
  __int64 (*ProcAddress)(void); // rax

  v0 = qword_140042B60;
  if ( !qword_140042B60 )
  {
    v0 = 2147352624;
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v2 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
      if ( ProcAddress )
        v0 = ProcAddress();
      FreeLibrary(v2);
    }
    qword_140042B60 = v0;
  }
  return v0;
}

```

## disassembly

```asm
0x1400102a0  mov     [rsp+arg_0], rbx
0x1400102a5  push    rdi
0x1400102a6  sub     rsp, 20h
0x1400102aa  mov     rbx, cs:qword_140042B60
0x1400102b1  test    rbx, rbx
0x1400102b4  jnz     short loc_140010305
0x1400102b6  xor     edx, edx; hFile
0x1400102b8  lea     rcx, LibFileName; "ntdll.dll"
0x1400102bf  mov     r8d, 800h; dwFlags
0x1400102c5  mov     ebx, 7FFE0030h
0x1400102ca  call    cs:__imp_LoadLibraryExW
0x1400102d0  mov     rdi, rax
0x1400102d3  test    rax, rax
0x1400102d6  jz      short loc_1400102FE
0x1400102d8  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x1400102df  mov     rcx, rax; hModule
0x1400102e2  call    cs:__imp_GetProcAddress
0x1400102e8  test    rax, rax
0x1400102eb  jz      short loc_1400102F5
0x1400102ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400102f2  mov     rbx, rax
0x1400102f5  mov     rcx, rdi; hLibModule
0x1400102f8  call    cs:__imp_FreeLibrary
0x1400102fe  mov     cs:qword_140042B60, rbx
0x140010305  mov     rax, rbx
0x140010308  mov     rbx, [rsp+28h+arg_0]
0x14001030d  add     rsp, 20h
0x140010311  pop     rdi
0x140010312  retn
```
