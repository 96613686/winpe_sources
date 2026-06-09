# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_

- ea: `0x1800269c0`
- end: `0x180026a80`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180026d9c`

## callees

- `0x1800269c0`
- `0x180026b50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800269f1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800269f1`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800269db`

## string_xrefs

- `0x1800269e4`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_void____cdecl___AtlThunkData_t____()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180040348 )
    return DecodePointer((PVOID)qword_1800403D0);
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
    return DecodePointer((PVOID)qword_1800403D0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800269c0  push    rbx
0x1800269c2  sub     rsp, 20h
0x1800269c6  cmp     cs:byte_180040348, 0
0x1800269cd  jz      short loc_1800269E2
0x1800269cf  mov     rcx, cs:qword_1800403D0
0x1800269d6  add     rsp, 20h
0x1800269da  pop     rbx
0x1800269db  jmp     cs:__imp_DecodePointer
0x1800269e2  xor     edx, edx; hFile
0x1800269e4  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x1800269eb  mov     r8d, 800h; dwFlags
0x1800269f1  call    cs:__imp_LoadLibraryExA
0x1800269f7  mov     rbx, rax
0x1800269fa  test    rax, rax
0x1800269fd  jz      short loc_180026A78
0x1800269ff  lea     r8, qword_1800403E8
0x180026a06  mov     rcx, rax
0x180026a09  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x180026a10  call    GetProcAddressSingle
0x180026a15  test    al, al
0x180026a17  jz      short loc_180026A78
0x180026a19  lea     r8, qword_1800403E0
0x180026a20  mov     rcx, rbx
0x180026a23  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x180026a2a  call    GetProcAddressSingle
0x180026a2f  test    al, al
0x180026a31  jz      short loc_180026A78
0x180026a33  lea     r8, qword_1800403D8
0x180026a3a  mov     rcx, rbx
0x180026a3d  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x180026a44  call    GetProcAddressSingle
0x180026a49  test    al, al
0x180026a4b  jz      short loc_180026A78
0x180026a4d  lea     r8, qword_1800403D0
0x180026a54  mov     rcx, rbx
0x180026a57  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x180026a5e  call    GetProcAddressSingle
0x180026a63  test    al, al
0x180026a65  jz      short loc_180026A78
0x180026a67  lock or [rsp+28h+var_28], 0
0x180026a6c  mov     cs:byte_180040348, 1
0x180026a73  jmp     loc_1800269CF
0x180026a78  xor     eax, eax
0x180026a7a  add     rsp, 20h
0x180026a7e  pop     rbx
0x180026a7f  retn
```
