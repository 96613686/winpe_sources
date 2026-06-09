# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_

- ea: `0x14000d548`
- end: `0x14000d63c`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000d89c`

## callees

- `0x14000d548`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000d595`
- `KERNEL32!GetProcAddress` at `0x14000d5be`
- `KERNEL32!GetProcAddress` at `0x14000d5e3`
- `KERNEL32!GetProcAddress` at `0x14000d608`
- `KERNEL32!GetProcAddress` at `0x14000d595`
- `KERNEL32!GetProcAddress` at `0x14000d5be`
- `KERNEL32!GetProcAddress` at `0x14000d5e3`
- `KERNEL32!GetProcAddress` at `0x14000d608`
- `KERNEL32!LoadLibraryExA` at `0x14000d579`
- `KERNEL32!LoadLibraryExA` at `0x14000d579`
- `KERNEL32!DecodePointer` at `0x14000d563`
- `KERNEL32!EncodePointer` at `0x14000d5a7`
- `KERNEL32!EncodePointer` at `0x14000d5cc`
- `KERNEL32!EncodePointer` at `0x14000d5f1`
- `KERNEL32!EncodePointer` at `0x14000d616`
- `KERNEL32!EncodePointer` at `0x14000d5a7`
- `KERNEL32!EncodePointer` at `0x14000d5cc`
- `KERNEL32!EncodePointer` at `0x14000d5f1`
- `KERNEL32!EncodePointer` at `0x14000d616`

## string_xrefs

- `0x14000d56c`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  signed __int32 v7[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_140015510 )
    return DecodePointer((PVOID)qword_140015508);
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
            return DecodePointer((PVOID)qword_140015508);
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
0x14000d548  push    rbx
0x14000d54a  sub     rsp, 20h
0x14000d54e  cmp     cs:byte_140015510, 0
0x14000d555  jz      short loc_14000D56A
0x14000d557  mov     rcx, cs:qword_140015508
0x14000d55e  add     rsp, 20h
0x14000d562  pop     rbx
0x14000d563  jmp     cs:__imp_DecodePointer
0x14000d56a  xor     edx, edx; hFile
0x14000d56c  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x14000d573  mov     r8d, 800h; dwFlags
0x14000d579  call    cs:__imp_LoadLibraryExA
0x14000d57f  mov     rbx, rax
0x14000d582  test    rax, rax
0x14000d585  jz      loc_14000D634
0x14000d58b  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x14000d592  mov     rcx, rax; hModule
0x14000d595  call    cs:__imp_GetProcAddress
0x14000d59b  test    rax, rax
0x14000d59e  jz      loc_14000D634
0x14000d5a4  mov     rcx, rax; Ptr
0x14000d5a7  call    cs:__imp_EncodePointer
0x14000d5ad  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x14000d5b4  mov     rcx, rbx; hModule
0x14000d5b7  mov     cs:qword_140015518, rax
0x14000d5be  call    cs:__imp_GetProcAddress
0x14000d5c4  test    rax, rax
0x14000d5c7  jz      short loc_14000D634
0x14000d5c9  mov     rcx, rax; Ptr
0x14000d5cc  call    cs:__imp_EncodePointer
0x14000d5d2  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x14000d5d9  mov     rcx, rbx; hModule
0x14000d5dc  mov     cs:qword_140015508, rax
0x14000d5e3  call    cs:__imp_GetProcAddress
0x14000d5e9  test    rax, rax
0x14000d5ec  jz      short loc_14000D634
0x14000d5ee  mov     rcx, rax; Ptr
0x14000d5f1  call    cs:__imp_EncodePointer
0x14000d5f7  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x14000d5fe  mov     rcx, rbx; hModule
0x14000d601  mov     cs:qword_140015500, rax
0x14000d608  call    cs:__imp_GetProcAddress
0x14000d60e  test    rax, rax
0x14000d611  jz      short loc_14000D634
0x14000d613  mov     rcx, rax; Ptr
0x14000d616  call    cs:__imp_EncodePointer
0x14000d61c  mov     cs:qword_1400154F8, rax
0x14000d623  lock or [rsp+28h+var_28], 0
0x14000d628  mov     cs:byte_140015510, 1
0x14000d62f  jmp     loc_14000D557
0x14000d634  xor     eax, eax
0x14000d636  add     rsp, 20h
0x14000d63a  pop     rbx
0x14000d63b  retn
```
