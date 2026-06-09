# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_

- ea: `0x180026a88`
- end: `0x180026b48`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180026df4`

## callees

- `0x180026a88`
- `0x180026b50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180026ab9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180026ab9`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180026aa3`

## string_xrefs

- `0x180026aac`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180040348 )
    return DecodePointer((PVOID)qword_1800403E0);
  Library = LoadLibraryExA("atlthunk.dll", 0, 0x800u);
  v2 = Library;
  if ( Library
    && (unsigned __int8)GetProcAddressSingle(Library, "AtlThunk_AllocateData", &qword_1800403E8)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_InitData", &qword_1800403E0)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_DataToCode", &qword_1800403D8)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_FreeData", &qword_1800403D0) )
  {
    _InterlockedOr(v3, 0);
    byte_180040348 = 1;
    return DecodePointer((PVOID)qword_1800403E0);
  }
  return 0;
}

```

## disassembly

```asm
0x180026a88  push    rbx
0x180026a8a  sub     rsp, 20h
0x180026a8e  cmp     cs:byte_180040348, 0
0x180026a95  jz      short loc_180026AAA
0x180026a97  mov     rcx, cs:qword_1800403E0
0x180026a9e  add     rsp, 20h
0x180026aa2  pop     rbx
0x180026aa3  jmp     cs:__imp_DecodePointer
0x180026aaa  xor     edx, edx; hFile
0x180026aac  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x180026ab3  mov     r8d, 800h; dwFlags
0x180026ab9  call    cs:__imp_LoadLibraryExA
0x180026abf  mov     rbx, rax
0x180026ac2  test    rax, rax
0x180026ac5  jz      short loc_180026B40
0x180026ac7  lea     r8, qword_1800403E8
0x180026ace  mov     rcx, rax
0x180026ad1  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x180026ad8  call    GetProcAddressSingle
0x180026add  test    al, al
0x180026adf  jz      short loc_180026B40
0x180026ae1  lea     r8, qword_1800403E0
0x180026ae8  mov     rcx, rbx
0x180026aeb  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x180026af2  call    GetProcAddressSingle
0x180026af7  test    al, al
0x180026af9  jz      short loc_180026B40
0x180026afb  lea     r8, qword_1800403D8
0x180026b02  mov     rcx, rbx
0x180026b05  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x180026b0c  call    GetProcAddressSingle
0x180026b11  test    al, al
0x180026b13  jz      short loc_180026B40
0x180026b15  lea     r8, qword_1800403D0
0x180026b1c  mov     rcx, rbx
0x180026b1f  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x180026b26  call    GetProcAddressSingle
0x180026b2b  test    al, al
0x180026b2d  jz      short loc_180026B40
0x180026b2f  lock or [rsp+28h+var_28], 0
0x180026b34  mov     cs:byte_180040348, 1
0x180026b3b  jmp     loc_180026A97
0x180026b40  xor     eax, eax
0x180026b42  add     rsp, 20h
0x180026b46  pop     rbx
0x180026b47  retn
```
