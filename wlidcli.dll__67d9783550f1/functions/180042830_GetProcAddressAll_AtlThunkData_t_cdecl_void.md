# GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_

- ea: `0x180042830`
- end: `0x1800428f0`
- name: `GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180042c18`

## callees

- `0x180042830`
- `0x180042a88`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180042861`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180042861`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18004284b`

## string_xrefs

- `0x180042854`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_AtlThunkData_t______cdecl___void__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180094CF8 )
    return DecodePointer((PVOID)qword_180094DB8);
  Library = LoadLibraryExA("atlthunk.dll", 0, 0x800u);
  v2 = Library;
  if ( Library
    && (unsigned __int8)GetProcAddressSingle(Library, "AtlThunk_AllocateData", &qword_180094DB8)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_InitData", &qword_180094DB0)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_DataToCode", &qword_180094DA8)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_FreeData", &qword_180094DA0) )
  {
    _InterlockedOr(v3, 0);
    byte_180094CF8 = 1;
    return DecodePointer((PVOID)qword_180094DB8);
  }
  return 0;
}

```

## disassembly

```asm
0x180042830  push    rbx
0x180042832  sub     rsp, 20h
0x180042836  cmp     cs:byte_180094CF8, 0
0x18004283d  jz      short loc_180042852
0x18004283f  mov     rcx, cs:qword_180094DB8
0x180042846  add     rsp, 20h
0x18004284a  pop     rbx
0x18004284b  jmp     cs:__imp_DecodePointer
0x180042852  xor     edx, edx; hFile
0x180042854  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18004285b  mov     r8d, 800h; dwFlags
0x180042861  call    cs:__imp_LoadLibraryExA
0x180042867  mov     rbx, rax
0x18004286a  test    rax, rax
0x18004286d  jz      short loc_1800428E8
0x18004286f  lea     r8, qword_180094DB8
0x180042876  mov     rcx, rax
0x180042879  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x180042880  call    GetProcAddressSingle
0x180042885  test    al, al
0x180042887  jz      short loc_1800428E8
0x180042889  lea     r8, qword_180094DB0
0x180042890  mov     rcx, rbx
0x180042893  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18004289a  call    GetProcAddressSingle
0x18004289f  test    al, al
0x1800428a1  jz      short loc_1800428E8
0x1800428a3  lea     r8, qword_180094DA8
0x1800428aa  mov     rcx, rbx
0x1800428ad  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x1800428b4  call    GetProcAddressSingle
0x1800428b9  test    al, al
0x1800428bb  jz      short loc_1800428E8
0x1800428bd  lea     r8, qword_180094DA0
0x1800428c4  mov     rcx, rbx
0x1800428c7  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x1800428ce  call    GetProcAddressSingle
0x1800428d3  test    al, al
0x1800428d5  jz      short loc_1800428E8
0x1800428d7  lock or [rsp+28h+var_28], 0
0x1800428dc  mov     cs:byte_180094CF8, 1
0x1800428e3  jmp     loc_18004283F
0x1800428e8  xor     eax, eax
0x1800428ea  add     rsp, 20h
0x1800428ee  pop     rbx
0x1800428ef  retn
```
