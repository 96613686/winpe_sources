# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_

- ea: `0x1800429c0`
- end: `0x180042a80`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180042d2c`

## callees

- `0x1800429c0`
- `0x180042a88`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800429f1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800429f1`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800429db`

## string_xrefs

- `0x1800429e4`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180094CF8 )
    return DecodePointer((PVOID)qword_180094DB0);
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
    return DecodePointer((PVOID)qword_180094DB0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800429c0  push    rbx
0x1800429c2  sub     rsp, 20h
0x1800429c6  cmp     cs:byte_180094CF8, 0
0x1800429cd  jz      short loc_1800429E2
0x1800429cf  mov     rcx, cs:qword_180094DB0
0x1800429d6  add     rsp, 20h
0x1800429da  pop     rbx
0x1800429db  jmp     cs:__imp_DecodePointer
0x1800429e2  xor     edx, edx; hFile
0x1800429e4  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x1800429eb  mov     r8d, 800h; dwFlags
0x1800429f1  call    cs:__imp_LoadLibraryExA
0x1800429f7  mov     rbx, rax
0x1800429fa  test    rax, rax
0x1800429fd  jz      short loc_180042A78
0x1800429ff  lea     r8, qword_180094DB8
0x180042a06  mov     rcx, rax
0x180042a09  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x180042a10  call    GetProcAddressSingle
0x180042a15  test    al, al
0x180042a17  jz      short loc_180042A78
0x180042a19  lea     r8, qword_180094DB0
0x180042a20  mov     rcx, rbx
0x180042a23  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x180042a2a  call    GetProcAddressSingle
0x180042a2f  test    al, al
0x180042a31  jz      short loc_180042A78
0x180042a33  lea     r8, qword_180094DA8
0x180042a3a  mov     rcx, rbx
0x180042a3d  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x180042a44  call    GetProcAddressSingle
0x180042a49  test    al, al
0x180042a4b  jz      short loc_180042A78
0x180042a4d  lea     r8, qword_180094DA0
0x180042a54  mov     rcx, rbx
0x180042a57  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x180042a5e  call    GetProcAddressSingle
0x180042a63  test    al, al
0x180042a65  jz      short loc_180042A78
0x180042a67  lock or [rsp+28h+var_28], 0
0x180042a6c  mov     cs:byte_180094CF8, 1
0x180042a73  jmp     loc_1800429CF
0x180042a78  xor     eax, eax
0x180042a7a  add     rsp, 20h
0x180042a7e  pop     rbx
0x180042a7f  retn
```
