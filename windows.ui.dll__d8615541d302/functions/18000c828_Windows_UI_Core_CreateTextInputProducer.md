# Windows::UI::Core::CreateTextInputProducer

- ea: `0x18000c828`
- end: `0x18000c8b1`
- name: `Windows::UI::Core::CreateTextInputProducer`
- size: `137`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c3c4`
- `0x18006f264`

## callees

- `0x18000c828`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c864`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c864`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c877`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c877`

## string_xrefs

- `0x18000c852`: `windows.ui.core.textinput.dll`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::CreateTextInputProducer(__int64 a1, _QWORD *a2)
{
  FARPROC ProcAddress; // rax
  unsigned int v5; // ebx
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_1801353E8;
  *a2 = 0;
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(__int64, _QWORD *))ProcAddress)(a1, a2);
  v5 = -2147467259;
  Library = LoadLibraryExW(L"windows.ui.core.textinput.dll", 0, 0x800u);
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, (LPCSTR)0x5DC);
    qword_1801353E8 = (__int64)ProcAddress;
  }
  else
  {
    ProcAddress = (FARPROC)qword_1801353E8;
  }
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(__int64, _QWORD *))ProcAddress)(a1, a2);
  return v5;
}

```

## disassembly

```asm
0x18000c828  mov     [rsp+arg_0], rbx
0x18000c82d  mov     [rsp+arg_8], rsi
0x18000c832  push    rdi
0x18000c833  sub     rsp, 20h
0x18000c837  mov     rax, cs:qword_1801353E8
0x18000c83e  mov     rdi, rdx
0x18000c841  mov     qword ptr [rdx], 0
0x18000c848  mov     rsi, rcx
0x18000c84b  test    rax, rax
0x18000c84e  jnz     short loc_18000C892
0x18000c850  xor     edx, edx; hFile
0x18000c852  lea     rcx, LibFileName; "windows.ui.core.textinput.dll"
0x18000c859  mov     r8d, 800h; dwFlags
0x18000c85f  mov     ebx, 80004005h
0x18000c864  call    cs:__imp_LoadLibraryExW
0x18000c86a  test    rax, rax
0x18000c86d  jz      short loc_18000C886
0x18000c86f  mov     edx, 5DCh; lpProcName
0x18000c874  mov     rcx, rax; hModule
0x18000c877  call    cs:__imp_GetProcAddress
0x18000c87d  mov     cs:qword_1801353E8, rax
0x18000c884  jmp     short loc_18000C88D
0x18000c886  mov     rax, cs:qword_1801353E8
0x18000c88d  test    rax, rax
0x18000c890  jz      short loc_18000C89F
0x18000c892  mov     rdx, rdi
0x18000c895  mov     rcx, rsi
0x18000c898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c89d  mov     ebx, eax
0x18000c89f  mov     rsi, [rsp+28h+arg_8]
0x18000c8a4  mov     eax, ebx
0x18000c8a6  mov     rbx, [rsp+28h+arg_0]
0x18000c8ab  add     rsp, 20h
0x18000c8af  pop     rdi
0x18000c8b0  retn
```
