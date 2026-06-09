# GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_

- ea: `0x180026830`
- end: `0x1800268f0`
- name: `GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180026d58`

## callees

- `0x180026830`
- `0x180026b50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180026861`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180026861`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18002684b`

## string_xrefs

- `0x180026854`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll___int64____cdecl____cdecl___AtlThunkData_t_____HWND_____unsigned_int_unsigned___int64___int64__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180040348 )
    return DecodePointer((PVOID)qword_1800403D8);
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
    return DecodePointer((PVOID)qword_1800403D8);
  }
  return 0;
}

```

## disassembly

```asm
0x180026830  push    rbx
0x180026832  sub     rsp, 20h
0x180026836  cmp     cs:byte_180040348, 0
0x18002683d  jz      short loc_180026852
0x18002683f  mov     rcx, cs:qword_1800403D8
0x180026846  add     rsp, 20h
0x18002684a  pop     rbx
0x18002684b  jmp     cs:__imp_DecodePointer
0x180026852  xor     edx, edx; hFile
0x180026854  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18002685b  mov     r8d, 800h; dwFlags
0x180026861  call    cs:__imp_LoadLibraryExA
0x180026867  mov     rbx, rax
0x18002686a  test    rax, rax
0x18002686d  jz      short loc_1800268E8
0x18002686f  lea     r8, qword_1800403E8
0x180026876  mov     rcx, rax
0x180026879  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x180026880  call    GetProcAddressSingle
0x180026885  test    al, al
0x180026887  jz      short loc_1800268E8
0x180026889  lea     r8, qword_1800403E0
0x180026890  mov     rcx, rbx
0x180026893  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18002689a  call    GetProcAddressSingle
0x18002689f  test    al, al
0x1800268a1  jz      short loc_1800268E8
0x1800268a3  lea     r8, qword_1800403D8
0x1800268aa  mov     rcx, rbx
0x1800268ad  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x1800268b4  call    GetProcAddressSingle
0x1800268b9  test    al, al
0x1800268bb  jz      short loc_1800268E8
0x1800268bd  lea     r8, qword_1800403D0
0x1800268c4  mov     rcx, rbx
0x1800268c7  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x1800268ce  call    GetProcAddressSingle
0x1800268d3  test    al, al
0x1800268d5  jz      short loc_1800268E8
0x1800268d7  lock or [rsp+28h+var_28], 0
0x1800268dc  mov     cs:byte_180040348, 1
0x1800268e3  jmp     loc_18002683F
0x1800268e8  xor     eax, eax
0x1800268ea  add     rsp, 20h
0x1800268ee  pop     rbx
0x1800268ef  retn
```
