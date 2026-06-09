# GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_

- ea: `0x1800268f8`
- end: `0x1800269b8`
- name: `GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180026ce0`

## callees

- `0x1800268f8`
- `0x180026b50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180026929`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180026929`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180026913`

## string_xrefs

- `0x18002691c`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_AtlThunkData_t______cdecl___void__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180040348 )
    return DecodePointer((PVOID)qword_1800403E8);
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
    return DecodePointer((PVOID)qword_1800403E8);
  }
  return 0;
}

```

## disassembly

```asm
0x1800268f8  push    rbx
0x1800268fa  sub     rsp, 20h
0x1800268fe  cmp     cs:byte_180040348, 0
0x180026905  jz      short loc_18002691A
0x180026907  mov     rcx, cs:qword_1800403E8
0x18002690e  add     rsp, 20h
0x180026912  pop     rbx
0x180026913  jmp     cs:__imp_DecodePointer
0x18002691a  xor     edx, edx; hFile
0x18002691c  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x180026923  mov     r8d, 800h; dwFlags
0x180026929  call    cs:__imp_LoadLibraryExA
0x18002692f  mov     rbx, rax
0x180026932  test    rax, rax
0x180026935  jz      short loc_1800269B0
0x180026937  lea     r8, qword_1800403E8
0x18002693e  mov     rcx, rax
0x180026941  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x180026948  call    GetProcAddressSingle
0x18002694d  test    al, al
0x18002694f  jz      short loc_1800269B0
0x180026951  lea     r8, qword_1800403E0
0x180026958  mov     rcx, rbx
0x18002695b  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x180026962  call    GetProcAddressSingle
0x180026967  test    al, al
0x180026969  jz      short loc_1800269B0
0x18002696b  lea     r8, qword_1800403D8
0x180026972  mov     rcx, rbx
0x180026975  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18002697c  call    GetProcAddressSingle
0x180026981  test    al, al
0x180026983  jz      short loc_1800269B0
0x180026985  lea     r8, qword_1800403D0
0x18002698c  mov     rcx, rbx
0x18002698f  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x180026996  call    GetProcAddressSingle
0x18002699b  test    al, al
0x18002699d  jz      short loc_1800269B0
0x18002699f  lock or [rsp+28h+var_28], 0
0x1800269a4  mov     cs:byte_180040348, 1
0x1800269ab  jmp     loc_180026907
0x1800269b0  xor     eax, eax
0x1800269b2  add     rsp, 20h
0x1800269b6  pop     rbx
0x1800269b7  retn
```
