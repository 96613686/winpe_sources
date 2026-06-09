# SvcAddRef(void)

- ea: `0x180035258`
- end: `0x1800352cc`
- name: `?SvcAddRef@@YAXXZ`
- size: `116`
- prototype: `void(void)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c6ec`
- `0x18000d560`
- `0x180033814`
- `0x180034400`
- `0x1800349a8`
- `0x18003a678`
- `0x180040828`
- `0x180070acc`
- `0x180075190`

## callees

- `0x180035258`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003529c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003529c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800352bb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800352bb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003527a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003527a`

## string_xrefs

- `0x180035273`: `combase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void SvcAddRef(void)
{
  HMODULE Library; // rax
  HMODULE v1; // rbx
  bool v2; // di
  FARPROC ProcAddress; // rax

  if ( dword_180150110 )
  {
    Library = LoadLibraryExW(L"combase.dll", 0, 0x800u);
    v1 = Library;
    v2 = Library != 0;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, (LPCSTR)0x43);
      if ( ProcAddress )
        ((void (__fastcall *)(_QWORD))ProcAddress)((unsigned int)dword_180150110);
    }
    if ( v2 )
      FreeLibrary(v1);
  }
}

```

## disassembly

```asm
0x180035258  mov     [rsp+arg_8], rbx
0x18003525d  push    rdi
0x18003525e  sub     rsp, 20h
0x180035262  cmp     cs:dword_180150110, 0
0x180035269  jz      short loc_1800352C1
0x18003526b  xor     edx, edx; hFile
0x18003526d  mov     r8d, 800h; dwFlags
0x180035273  lea     rcx, aCombaseDll; "combase.dll"
0x18003527a  call    cs:__imp_LoadLibraryExW
0x180035280  mov     rbx, rax
0x180035283  mov     [rsp+28h+arg_0], rax
0x180035288  test    rax, rax
0x18003528b  setnz   dil
0x18003528f  test    rax, rax
0x180035292  jz      short loc_1800352B3
0x180035294  mov     edx, 43h ; 'C'; lpProcName
0x180035299  mov     rcx, rax; hModule
0x18003529c  call    cs:__imp_GetProcAddress
0x1800352a2  test    rax, rax
0x1800352a5  jz      short loc_1800352B3
0x1800352a7  mov     ecx, cs:dword_180150110
0x1800352ad  call    _guard_dispatch_icall
0x1800352b2  nop
0x1800352b3  test    dil, dil
0x1800352b6  jz      short loc_1800352C1
0x1800352b8  mov     rcx, rbx; hLibModule
0x1800352bb  call    cs:__imp_FreeLibrary
0x1800352c1  mov     rbx, [rsp+28h+arg_8]
0x1800352c6  add     rsp, 20h
0x1800352ca  pop     rdi
0x1800352cb  retn
```
