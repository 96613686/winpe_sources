# GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_

- ea: `0x18000e638`
- end: `0x18000e6f8`
- name: `GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ea20`

## callees

- `0x18000e638`
- `0x18000e890`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000e669`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000e669`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000e653`

## string_xrefs

- `0x18000e65c`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_AtlThunkData_t______cdecl___void__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_18004DAC8 )
    return DecodePointer((PVOID)qword_18004DB60);
  Library = LoadLibraryExA("atlthunk.dll", 0, 0x800u);
  v2 = Library;
  if ( Library
    && (unsigned __int8)GetProcAddressSingle(Library, "AtlThunk_AllocateData", &qword_18004DB60)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_InitData", &qword_18004DB58)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_DataToCode", &qword_18004DB50)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_FreeData", &qword_18004DB48) )
  {
    _InterlockedOr(v3, 0);
    byte_18004DAC8 = 1;
    return DecodePointer((PVOID)qword_18004DB60);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e638  push    rbx
0x18000e63a  sub     rsp, 20h
0x18000e63e  cmp     cs:byte_18004DAC8, 0
0x18000e645  jz      short loc_18000E65A
0x18000e647  mov     rcx, cs:qword_18004DB60
0x18000e64e  add     rsp, 20h
0x18000e652  pop     rbx
0x18000e653  jmp     cs:__imp_DecodePointer
0x18000e65a  xor     edx, edx; hFile
0x18000e65c  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18000e663  mov     r8d, 800h; dwFlags
0x18000e669  call    cs:__imp_LoadLibraryExA
0x18000e66f  mov     rbx, rax
0x18000e672  test    rax, rax
0x18000e675  jz      short loc_18000E6F0
0x18000e677  lea     r8, qword_18004DB60
0x18000e67e  mov     rcx, rax
0x18000e681  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18000e688  call    GetProcAddressSingle
0x18000e68d  test    al, al
0x18000e68f  jz      short loc_18000E6F0
0x18000e691  lea     r8, qword_18004DB58
0x18000e698  mov     rcx, rbx
0x18000e69b  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18000e6a2  call    GetProcAddressSingle
0x18000e6a7  test    al, al
0x18000e6a9  jz      short loc_18000E6F0
0x18000e6ab  lea     r8, qword_18004DB50
0x18000e6b2  mov     rcx, rbx
0x18000e6b5  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18000e6bc  call    GetProcAddressSingle
0x18000e6c1  test    al, al
0x18000e6c3  jz      short loc_18000E6F0
0x18000e6c5  lea     r8, qword_18004DB48
0x18000e6cc  mov     rcx, rbx
0x18000e6cf  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18000e6d6  call    GetProcAddressSingle
0x18000e6db  test    al, al
0x18000e6dd  jz      short loc_18000E6F0
0x18000e6df  lock or [rsp+28h+var_28], 0
0x18000e6e4  mov     cs:byte_18004DAC8, 1
0x18000e6eb  jmp     loc_18000E647
0x18000e6f0  xor     eax, eax
0x18000e6f2  add     rsp, 20h
0x18000e6f6  pop     rbx
0x18000e6f7  retn
```
