# RoInitializeStrictDelayLoad

- ea: `0x18004f6b8`
- end: `0x18004f720`
- name: `RoInitializeStrictDelayLoad`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800445c4`

## callees

- `0x18004f6b8`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004f718`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004f718`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004f6e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004f6e4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004f6c9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004f6c9`
- `combase!__imp_RoInitializeASTA` at `0x18004f6ef`
- `combase!__imp_RoInitializeASTA` at `0x18004f6ef`

## string_xrefs

- `0x18004f6c2`: `combase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 RoInitializeStrictDelayLoad()
{
  HMODULE LibraryW; // rax
  HMODULE v1; // rbx
  FARPROC ProcAddress; // rax
  unsigned int v3; // edi

  LibraryW = LoadLibraryW(L"combase.dll");
  v1 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0xB3);
    if ( ProcAddress )
    {
      v3 = ((__int64 (__fastcall *)(__int64))ProcAddress)(1);
      goto LABEL_6;
    }
  }
  v3 = RoInitializeASTA();
  if ( v1 )
LABEL_6:
    FreeLibrary(v1);
  return v3;
}

```

## disassembly

```asm
0x18004f6b8  mov     [rsp+arg_8], rbx
0x18004f6bd  push    rdi
0x18004f6be  sub     rsp, 20h
0x18004f6c2  lea     rcx, LibFileName; "combase.dll"
0x18004f6c9  call    cs:__imp_LoadLibraryW
0x18004f6cf  mov     rbx, rax
0x18004f6d2  mov     [rsp+28h+arg_0], rax
0x18004f6d7  test    rax, rax
0x18004f6da  jz      short loc_18004F6EF
0x18004f6dc  mov     edx, 0B3h; lpProcName
0x18004f6e1  mov     rcx, rax; hModule
0x18004f6e4  call    cs:__imp_GetProcAddress
0x18004f6ea  test    rax, rax
0x18004f6ed  jnz     short loc_18004F709
0x18004f6ef  call    cs:__imp_RoInitializeASTA
0x18004f6f5  mov     edi, eax
0x18004f6f7  test    rbx, rbx
0x18004f6fa  jnz     short loc_18004F715
0x18004f6fc  mov     eax, edi
0x18004f6fe  mov     rbx, [rsp+28h+arg_8]
0x18004f703  add     rsp, 20h
0x18004f707  pop     rdi
0x18004f708  retn
0x18004f709  mov     ecx, 1
0x18004f70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f713  mov     edi, eax
0x18004f715  mov     rcx, rbx; hLibModule
0x18004f718  call    cs:__imp_FreeLibrary
0x18004f71e  jmp     short loc_18004F6FC
```
