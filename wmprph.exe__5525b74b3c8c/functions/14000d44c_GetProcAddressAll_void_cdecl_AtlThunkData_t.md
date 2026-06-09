# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_

- ea: `0x14000d44c`
- end: `0x14000d540`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000d83c`

## callees

- `0x14000d44c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000d499`
- `KERNEL32!GetProcAddress` at `0x14000d4c2`
- `KERNEL32!GetProcAddress` at `0x14000d4e7`
- `KERNEL32!GetProcAddress` at `0x14000d50c`
- `KERNEL32!GetProcAddress` at `0x14000d499`
- `KERNEL32!GetProcAddress` at `0x14000d4c2`
- `KERNEL32!GetProcAddress` at `0x14000d4e7`
- `KERNEL32!GetProcAddress` at `0x14000d50c`
- `KERNEL32!LoadLibraryExA` at `0x14000d47d`
- `KERNEL32!LoadLibraryExA` at `0x14000d47d`
- `KERNEL32!DecodePointer` at `0x14000d467`
- `KERNEL32!EncodePointer` at `0x14000d4ab`
- `KERNEL32!EncodePointer` at `0x14000d4d0`
- `KERNEL32!EncodePointer` at `0x14000d4f5`
- `KERNEL32!EncodePointer` at `0x14000d51a`
- `KERNEL32!EncodePointer` at `0x14000d4ab`
- `KERNEL32!EncodePointer` at `0x14000d4d0`
- `KERNEL32!EncodePointer` at `0x14000d4f5`
- `KERNEL32!EncodePointer` at `0x14000d51a`

## string_xrefs

- `0x14000d470`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_void____cdecl___AtlThunkData_t____()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  signed __int32 v7[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_140015510 )
    return DecodePointer((PVOID)qword_1400154F8);
  Library = LoadLibraryExA("atlthunk.dll", 0, 0x800u);
  v2 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "AtlThunk_AllocateData");
    if ( ProcAddress )
    {
      qword_140015518 = (__int64)EncodePointer(ProcAddress);
      v4 = GetProcAddress(v2, "AtlThunk_InitData");
      if ( v4 )
      {
        qword_140015508 = (__int64)EncodePointer(v4);
        v5 = GetProcAddress(v2, "AtlThunk_DataToCode");
        if ( v5 )
        {
          qword_140015500 = (__int64)EncodePointer(v5);
          v6 = GetProcAddress(v2, "AtlThunk_FreeData");
          if ( v6 )
          {
            qword_1400154F8 = (__int64)EncodePointer(v6);
            _InterlockedOr(v7, 0);
            byte_140015510 = 1;
            return DecodePointer((PVOID)qword_1400154F8);
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000d44c  push    rbx
0x14000d44e  sub     rsp, 20h
0x14000d452  cmp     cs:byte_140015510, 0
0x14000d459  jz      short loc_14000D46E
0x14000d45b  mov     rcx, cs:qword_1400154F8
0x14000d462  add     rsp, 20h
0x14000d466  pop     rbx
0x14000d467  jmp     cs:__imp_DecodePointer
0x14000d46e  xor     edx, edx; hFile
0x14000d470  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x14000d477  mov     r8d, 800h; dwFlags
0x14000d47d  call    cs:__imp_LoadLibraryExA
0x14000d483  mov     rbx, rax
0x14000d486  test    rax, rax
0x14000d489  jz      loc_14000D538
0x14000d48f  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x14000d496  mov     rcx, rax; hModule
0x14000d499  call    cs:__imp_GetProcAddress
0x14000d49f  test    rax, rax
0x14000d4a2  jz      loc_14000D538
0x14000d4a8  mov     rcx, rax; Ptr
0x14000d4ab  call    cs:__imp_EncodePointer
0x14000d4b1  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x14000d4b8  mov     rcx, rbx; hModule
0x14000d4bb  mov     cs:qword_140015518, rax
0x14000d4c2  call    cs:__imp_GetProcAddress
0x14000d4c8  test    rax, rax
0x14000d4cb  jz      short loc_14000D538
0x14000d4cd  mov     rcx, rax; Ptr
0x14000d4d0  call    cs:__imp_EncodePointer
0x14000d4d6  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x14000d4dd  mov     rcx, rbx; hModule
0x14000d4e0  mov     cs:qword_140015508, rax
0x14000d4e7  call    cs:__imp_GetProcAddress
0x14000d4ed  test    rax, rax
0x14000d4f0  jz      short loc_14000D538
0x14000d4f2  mov     rcx, rax; Ptr
0x14000d4f5  call    cs:__imp_EncodePointer
0x14000d4fb  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x14000d502  mov     rcx, rbx; hModule
0x14000d505  mov     cs:qword_140015500, rax
0x14000d50c  call    cs:__imp_GetProcAddress
0x14000d512  test    rax, rax
0x14000d515  jz      short loc_14000D538
0x14000d517  mov     rcx, rax; Ptr
0x14000d51a  call    cs:__imp_EncodePointer
0x14000d520  mov     cs:qword_1400154F8, rax
0x14000d527  lock or [rsp+28h+var_28], 0
0x14000d52c  mov     cs:byte_140015510, 1
0x14000d533  jmp     loc_14000D45B
0x14000d538  xor     eax, eax
0x14000d53a  add     rsp, 20h
0x14000d53e  pop     rbx
0x14000d53f  retn
```
