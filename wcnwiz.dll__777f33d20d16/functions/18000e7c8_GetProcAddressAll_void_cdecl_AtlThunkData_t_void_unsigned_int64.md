# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_

- ea: `0x18000e7c8`
- end: `0x18000e888`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000eb34`

## callees

- `0x18000e7c8`
- `0x18000e890`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000e7f9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000e7f9`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000e7e3`

## string_xrefs

- `0x18000e7ec`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_18004DAC8 )
    return DecodePointer((PVOID)qword_18004DB58);
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
    return DecodePointer((PVOID)qword_18004DB58);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e7c8  push    rbx
0x18000e7ca  sub     rsp, 20h
0x18000e7ce  cmp     cs:byte_18004DAC8, 0
0x18000e7d5  jz      short loc_18000E7EA
0x18000e7d7  mov     rcx, cs:qword_18004DB58
0x18000e7de  add     rsp, 20h
0x18000e7e2  pop     rbx
0x18000e7e3  jmp     cs:__imp_DecodePointer
0x18000e7ea  xor     edx, edx; hFile
0x18000e7ec  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18000e7f3  mov     r8d, 800h; dwFlags
0x18000e7f9  call    cs:__imp_LoadLibraryExA
0x18000e7ff  mov     rbx, rax
0x18000e802  test    rax, rax
0x18000e805  jz      short loc_18000E880
0x18000e807  lea     r8, qword_18004DB60
0x18000e80e  mov     rcx, rax
0x18000e811  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18000e818  call    GetProcAddressSingle
0x18000e81d  test    al, al
0x18000e81f  jz      short loc_18000E880
0x18000e821  lea     r8, qword_18004DB58
0x18000e828  mov     rcx, rbx
0x18000e82b  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18000e832  call    GetProcAddressSingle
0x18000e837  test    al, al
0x18000e839  jz      short loc_18000E880
0x18000e83b  lea     r8, qword_18004DB50
0x18000e842  mov     rcx, rbx
0x18000e845  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18000e84c  call    GetProcAddressSingle
0x18000e851  test    al, al
0x18000e853  jz      short loc_18000E880
0x18000e855  lea     r8, qword_18004DB48
0x18000e85c  mov     rcx, rbx
0x18000e85f  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18000e866  call    GetProcAddressSingle
0x18000e86b  test    al, al
0x18000e86d  jz      short loc_18000E880
0x18000e86f  lock or [rsp+28h+var_28], 0
0x18000e874  mov     cs:byte_18004DAC8, 1
0x18000e87b  jmp     loc_18000E7D7
0x18000e880  xor     eax, eax
0x18000e882  add     rsp, 20h
0x18000e886  pop     rbx
0x18000e887  retn
```
