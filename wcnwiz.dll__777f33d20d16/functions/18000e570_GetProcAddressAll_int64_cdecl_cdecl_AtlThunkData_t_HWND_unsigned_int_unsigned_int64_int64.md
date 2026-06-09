# GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_

- ea: `0x18000e570`
- end: `0x18000e630`
- name: `GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ea98`

## callees

- `0x18000e570`
- `0x18000e890`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000e5a1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000e5a1`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000e58b`

## string_xrefs

- `0x18000e594`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll___int64____cdecl____cdecl___AtlThunkData_t_____HWND_____unsigned_int_unsigned___int64___int64__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_18004DAC8 )
    return DecodePointer((PVOID)qword_18004DB50);
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
    return DecodePointer((PVOID)qword_18004DB50);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e570  push    rbx
0x18000e572  sub     rsp, 20h
0x18000e576  cmp     cs:byte_18004DAC8, 0
0x18000e57d  jz      short loc_18000E592
0x18000e57f  mov     rcx, cs:qword_18004DB50
0x18000e586  add     rsp, 20h
0x18000e58a  pop     rbx
0x18000e58b  jmp     cs:__imp_DecodePointer
0x18000e592  xor     edx, edx; hFile
0x18000e594  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18000e59b  mov     r8d, 800h; dwFlags
0x18000e5a1  call    cs:__imp_LoadLibraryExA
0x18000e5a7  mov     rbx, rax
0x18000e5aa  test    rax, rax
0x18000e5ad  jz      short loc_18000E628
0x18000e5af  lea     r8, qword_18004DB60
0x18000e5b6  mov     rcx, rax
0x18000e5b9  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18000e5c0  call    GetProcAddressSingle
0x18000e5c5  test    al, al
0x18000e5c7  jz      short loc_18000E628
0x18000e5c9  lea     r8, qword_18004DB58
0x18000e5d0  mov     rcx, rbx
0x18000e5d3  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18000e5da  call    GetProcAddressSingle
0x18000e5df  test    al, al
0x18000e5e1  jz      short loc_18000E628
0x18000e5e3  lea     r8, qword_18004DB50
0x18000e5ea  mov     rcx, rbx
0x18000e5ed  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18000e5f4  call    GetProcAddressSingle
0x18000e5f9  test    al, al
0x18000e5fb  jz      short loc_18000E628
0x18000e5fd  lea     r8, qword_18004DB48
0x18000e604  mov     rcx, rbx
0x18000e607  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18000e60e  call    GetProcAddressSingle
0x18000e613  test    al, al
0x18000e615  jz      short loc_18000E628
0x18000e617  lock or [rsp+28h+var_28], 0
0x18000e61c  mov     cs:byte_18004DAC8, 1
0x18000e623  jmp     loc_18000E57F
0x18000e628  xor     eax, eax
0x18000e62a  add     rsp, 20h
0x18000e62e  pop     rbx
0x18000e62f  retn
```
