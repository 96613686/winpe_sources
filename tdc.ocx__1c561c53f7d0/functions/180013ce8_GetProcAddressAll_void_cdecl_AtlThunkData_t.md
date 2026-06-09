# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_

- ea: `0x180013ce8`
- end: `0x180013ddc`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800140d8`

## callees

- `0x180013ce8`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x180013d47`
- `KERNEL32!EncodePointer` at `0x180013d6c`
- `KERNEL32!EncodePointer` at `0x180013d91`
- `KERNEL32!EncodePointer` at `0x180013db6`
- `KERNEL32!EncodePointer` at `0x180013d47`
- `KERNEL32!EncodePointer` at `0x180013d6c`
- `KERNEL32!EncodePointer` at `0x180013d91`
- `KERNEL32!EncodePointer` at `0x180013db6`
- `KERNEL32!DecodePointer` at `0x180013d03`
- `KERNEL32!LoadLibraryExA` at `0x180013d19`
- `KERNEL32!LoadLibraryExA` at `0x180013d19`
- `KERNEL32!GetProcAddress` at `0x180013d35`
- `KERNEL32!GetProcAddress` at `0x180013d5e`
- `KERNEL32!GetProcAddress` at `0x180013d83`
- `KERNEL32!GetProcAddress` at `0x180013da8`
- `KERNEL32!GetProcAddress` at `0x180013d35`
- `KERNEL32!GetProcAddress` at `0x180013d5e`
- `KERNEL32!GetProcAddress` at `0x180013d83`
- `KERNEL32!GetProcAddress` at `0x180013da8`

## string_xrefs

- `0x180013d0c`: `atlthunk.dll`

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

  if ( byte_18001BDD8 )
    return DecodePointer((PVOID)qword_18001BDC0);
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
            return DecodePointer((PVOID)qword_18001BDC0);
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
0x180013ce8  push    rbx
0x180013cea  sub     rsp, 20h
0x180013cee  cmp     cs:byte_18001BDD8, 0
0x180013cf5  jz      short loc_180013D0A
0x180013cf7  mov     rcx, cs:qword_18001BDC0
0x180013cfe  add     rsp, 20h
0x180013d02  pop     rbx
0x180013d03  jmp     cs:__imp_DecodePointer
0x180013d0a  xor     edx, edx; hFile
0x180013d0c  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x180013d13  mov     r8d, 800h; dwFlags
0x180013d19  call    cs:__imp_LoadLibraryExA
0x180013d1f  mov     rbx, rax
0x180013d22  test    rax, rax
0x180013d25  jz      loc_180013DD4
0x180013d2b  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x180013d32  mov     rcx, rax; hModule
0x180013d35  call    cs:__imp_GetProcAddress
0x180013d3b  test    rax, rax
0x180013d3e  jz      loc_180013DD4
0x180013d44  mov     rcx, rax; Ptr
0x180013d47  call    cs:__imp_EncodePointer
0x180013d4d  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x180013d54  mov     rcx, rbx; hModule
0x180013d57  mov     cs:qword_18001BDE0, rax
0x180013d5e  call    cs:__imp_GetProcAddress
0x180013d64  test    rax, rax
0x180013d67  jz      short loc_180013DD4
0x180013d69  mov     rcx, rax; Ptr
0x180013d6c  call    cs:__imp_EncodePointer
0x180013d72  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x180013d79  mov     rcx, rbx; hModule
0x180013d7c  mov     cs:qword_18001BDD0, rax
0x180013d83  call    cs:__imp_GetProcAddress
0x180013d89  test    rax, rax
0x180013d8c  jz      short loc_180013DD4
0x180013d8e  mov     rcx, rax; Ptr
0x180013d91  call    cs:__imp_EncodePointer
0x180013d97  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x180013d9e  mov     rcx, rbx; hModule
0x180013da1  mov     cs:qword_18001BDC8, rax
0x180013da8  call    cs:__imp_GetProcAddress
0x180013dae  test    rax, rax
0x180013db1  jz      short loc_180013DD4
0x180013db3  mov     rcx, rax; Ptr
0x180013db6  call    cs:__imp_EncodePointer
0x180013dbc  mov     cs:qword_18001BDC0, rax
0x180013dc3  lock or [rsp+28h+var_28], 0
0x180013dc8  mov     cs:byte_18001BDD8, 1
0x180013dcf  jmp     loc_180013CF7
0x180013dd4  xor     eax, eax
0x180013dd6  add     rsp, 20h
0x180013dda  pop     rbx
0x180013ddb  retn
```
