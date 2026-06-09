# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_

- ea: `0x1800428f8`
- end: `0x1800429b8`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180042cd4`

## callees

- `0x1800428f8`
- `0x180042a88`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180042929`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180042929`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180042913`

## string_xrefs

- `0x18004291c`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_void____cdecl___AtlThunkData_t____()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180094CF8 )
    return DecodePointer((PVOID)qword_180094DA0);
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
    return DecodePointer((PVOID)qword_180094DA0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800428f8  push    rbx
0x1800428fa  sub     rsp, 20h
0x1800428fe  cmp     cs:byte_180094CF8, 0
0x180042905  jz      short loc_18004291A
0x180042907  mov     rcx, cs:qword_180094DA0
0x18004290e  add     rsp, 20h
0x180042912  pop     rbx
0x180042913  jmp     cs:__imp_DecodePointer
0x18004291a  xor     edx, edx; hFile
0x18004291c  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x180042923  mov     r8d, 800h; dwFlags
0x180042929  call    cs:__imp_LoadLibraryExA
0x18004292f  mov     rbx, rax
0x180042932  test    rax, rax
0x180042935  jz      short loc_1800429B0
0x180042937  lea     r8, qword_180094DB8
0x18004293e  mov     rcx, rax
0x180042941  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x180042948  call    GetProcAddressSingle
0x18004294d  test    al, al
0x18004294f  jz      short loc_1800429B0
0x180042951  lea     r8, qword_180094DB0
0x180042958  mov     rcx, rbx
0x18004295b  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x180042962  call    GetProcAddressSingle
0x180042967  test    al, al
0x180042969  jz      short loc_1800429B0
0x18004296b  lea     r8, qword_180094DA8
0x180042972  mov     rcx, rbx
0x180042975  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18004297c  call    GetProcAddressSingle
0x180042981  test    al, al
0x180042983  jz      short loc_1800429B0
0x180042985  lea     r8, qword_180094DA0
0x18004298c  mov     rcx, rbx
0x18004298f  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x180042996  call    GetProcAddressSingle
0x18004299b  test    al, al
0x18004299d  jz      short loc_1800429B0
0x18004299f  lock or [rsp+28h+var_28], 0
0x1800429a4  mov     cs:byte_180094CF8, 1
0x1800429ab  jmp     loc_180042907
0x1800429b0  xor     eax, eax
0x1800429b2  add     rsp, 20h
0x1800429b6  pop     rbx
0x1800429b7  retn
```
