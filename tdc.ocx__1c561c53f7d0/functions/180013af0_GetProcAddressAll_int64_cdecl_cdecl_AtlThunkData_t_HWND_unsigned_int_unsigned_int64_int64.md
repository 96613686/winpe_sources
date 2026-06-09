# GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_

- ea: `0x180013af0`
- end: `0x180013be4`
- name: `GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180014094`

## callees

- `0x180013af0`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x180013b4f`
- `KERNEL32!EncodePointer` at `0x180013b74`
- `KERNEL32!EncodePointer` at `0x180013b99`
- `KERNEL32!EncodePointer` at `0x180013bbe`
- `KERNEL32!EncodePointer` at `0x180013b4f`
- `KERNEL32!EncodePointer` at `0x180013b74`
- `KERNEL32!EncodePointer` at `0x180013b99`
- `KERNEL32!EncodePointer` at `0x180013bbe`
- `KERNEL32!DecodePointer` at `0x180013b0b`
- `KERNEL32!LoadLibraryExA` at `0x180013b21`
- `KERNEL32!LoadLibraryExA` at `0x180013b21`
- `KERNEL32!GetProcAddress` at `0x180013b3d`
- `KERNEL32!GetProcAddress` at `0x180013b66`
- `KERNEL32!GetProcAddress` at `0x180013b8b`
- `KERNEL32!GetProcAddress` at `0x180013bb0`
- `KERNEL32!GetProcAddress` at `0x180013b3d`
- `KERNEL32!GetProcAddress` at `0x180013b66`
- `KERNEL32!GetProcAddress` at `0x180013b8b`
- `KERNEL32!GetProcAddress` at `0x180013bb0`

## string_xrefs

- `0x180013b14`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll___int64____cdecl____cdecl___AtlThunkData_t_____HWND_____unsigned_int_unsigned___int64___int64__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  signed __int32 v7[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_18001BDD8 )
    return DecodePointer((PVOID)qword_18001BDC8);
  Library = LoadLibraryExA("atlthunk.dll", 0, 0x800u);
  v2 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "AtlThunk_AllocateData");
    if ( ProcAddress )
    {
      qword_18001BDE0 = (__int64)EncodePointer(ProcAddress);
      v4 = GetProcAddress(v2, "AtlThunk_InitData");
      if ( v4 )
      {
        qword_18001BDD0 = (__int64)EncodePointer(v4);
        v5 = GetProcAddress(v2, "AtlThunk_DataToCode");
        if ( v5 )
        {
          qword_18001BDC8 = (__int64)EncodePointer(v5);
          v6 = GetProcAddress(v2, "AtlThunk_FreeData");
          if ( v6 )
          {
            qword_18001BDC0 = (__int64)EncodePointer(v6);
            _InterlockedOr(v7, 0);
            byte_18001BDD8 = 1;
            return DecodePointer((PVOID)qword_18001BDC8);
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
0x180013af0  push    rbx
0x180013af2  sub     rsp, 20h
0x180013af6  cmp     cs:byte_18001BDD8, 0
0x180013afd  jz      short loc_180013B12
0x180013aff  mov     rcx, cs:qword_18001BDC8
0x180013b06  add     rsp, 20h
0x180013b0a  pop     rbx
0x180013b0b  jmp     cs:__imp_DecodePointer
0x180013b12  xor     edx, edx; hFile
0x180013b14  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x180013b1b  mov     r8d, 800h; dwFlags
0x180013b21  call    cs:__imp_LoadLibraryExA
0x180013b27  mov     rbx, rax
0x180013b2a  test    rax, rax
0x180013b2d  jz      loc_180013BDC
0x180013b33  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x180013b3a  mov     rcx, rax; hModule
0x180013b3d  call    cs:__imp_GetProcAddress
0x180013b43  test    rax, rax
0x180013b46  jz      loc_180013BDC
0x180013b4c  mov     rcx, rax; Ptr
0x180013b4f  call    cs:__imp_EncodePointer
0x180013b55  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x180013b5c  mov     rcx, rbx; hModule
0x180013b5f  mov     cs:qword_18001BDE0, rax
0x180013b66  call    cs:__imp_GetProcAddress
0x180013b6c  test    rax, rax
0x180013b6f  jz      short loc_180013BDC
0x180013b71  mov     rcx, rax; Ptr
0x180013b74  call    cs:__imp_EncodePointer
0x180013b7a  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x180013b81  mov     rcx, rbx; hModule
0x180013b84  mov     cs:qword_18001BDD0, rax
0x180013b8b  call    cs:__imp_GetProcAddress
0x180013b91  test    rax, rax
0x180013b94  jz      short loc_180013BDC
0x180013b96  mov     rcx, rax; Ptr
0x180013b99  call    cs:__imp_EncodePointer
0x180013b9f  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x180013ba6  mov     rcx, rbx; hModule
0x180013ba9  mov     cs:qword_18001BDC8, rax
0x180013bb0  call    cs:__imp_GetProcAddress
0x180013bb6  test    rax, rax
0x180013bb9  jz      short loc_180013BDC
0x180013bbb  mov     rcx, rax; Ptr
0x180013bbe  call    cs:__imp_EncodePointer
0x180013bc4  mov     cs:qword_18001BDC0, rax
0x180013bcb  lock or [rsp+28h+var_28], 0
0x180013bd0  mov     cs:byte_18001BDD8, 1
0x180013bd7  jmp     loc_180013AFF
0x180013bdc  xor     eax, eax
0x180013bde  add     rsp, 20h
0x180013be2  pop     rbx
0x180013be3  retn
```
