# GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_

- ea: `0x14000d254`
- end: `0x14000d348`
- name: `GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000d7f8`

## callees

- `0x14000d254`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000d2a1`
- `KERNEL32!GetProcAddress` at `0x14000d2ca`
- `KERNEL32!GetProcAddress` at `0x14000d2ef`
- `KERNEL32!GetProcAddress` at `0x14000d314`
- `KERNEL32!GetProcAddress` at `0x14000d2a1`
- `KERNEL32!GetProcAddress` at `0x14000d2ca`
- `KERNEL32!GetProcAddress` at `0x14000d2ef`
- `KERNEL32!GetProcAddress` at `0x14000d314`
- `KERNEL32!LoadLibraryExA` at `0x14000d285`
- `KERNEL32!LoadLibraryExA` at `0x14000d285`
- `KERNEL32!DecodePointer` at `0x14000d26f`
- `KERNEL32!EncodePointer` at `0x14000d2b3`
- `KERNEL32!EncodePointer` at `0x14000d2d8`
- `KERNEL32!EncodePointer` at `0x14000d2fd`
- `KERNEL32!EncodePointer` at `0x14000d322`
- `KERNEL32!EncodePointer` at `0x14000d2b3`
- `KERNEL32!EncodePointer` at `0x14000d2d8`
- `KERNEL32!EncodePointer` at `0x14000d2fd`
- `KERNEL32!EncodePointer` at `0x14000d322`

## string_xrefs

- `0x14000d278`: `atlthunk.dll`

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

  if ( byte_140015510 )
    return DecodePointer((PVOID)qword_140015500);
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
            return DecodePointer((PVOID)qword_140015500);
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
0x14000d254  push    rbx
0x14000d256  sub     rsp, 20h
0x14000d25a  cmp     cs:byte_140015510, 0
0x14000d261  jz      short loc_14000D276
0x14000d263  mov     rcx, cs:qword_140015500
0x14000d26a  add     rsp, 20h
0x14000d26e  pop     rbx
0x14000d26f  jmp     cs:__imp_DecodePointer
0x14000d276  xor     edx, edx; hFile
0x14000d278  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x14000d27f  mov     r8d, 800h; dwFlags
0x14000d285  call    cs:__imp_LoadLibraryExA
0x14000d28b  mov     rbx, rax
0x14000d28e  test    rax, rax
0x14000d291  jz      loc_14000D340
0x14000d297  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x14000d29e  mov     rcx, rax; hModule
0x14000d2a1  call    cs:__imp_GetProcAddress
0x14000d2a7  test    rax, rax
0x14000d2aa  jz      loc_14000D340
0x14000d2b0  mov     rcx, rax; Ptr
0x14000d2b3  call    cs:__imp_EncodePointer
0x14000d2b9  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x14000d2c0  mov     rcx, rbx; hModule
0x14000d2c3  mov     cs:qword_140015518, rax
0x14000d2ca  call    cs:__imp_GetProcAddress
0x14000d2d0  test    rax, rax
0x14000d2d3  jz      short loc_14000D340
0x14000d2d5  mov     rcx, rax; Ptr
0x14000d2d8  call    cs:__imp_EncodePointer
0x14000d2de  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x14000d2e5  mov     rcx, rbx; hModule
0x14000d2e8  mov     cs:qword_140015508, rax
0x14000d2ef  call    cs:__imp_GetProcAddress
0x14000d2f5  test    rax, rax
0x14000d2f8  jz      short loc_14000D340
0x14000d2fa  mov     rcx, rax; Ptr
0x14000d2fd  call    cs:__imp_EncodePointer
0x14000d303  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x14000d30a  mov     rcx, rbx; hModule
0x14000d30d  mov     cs:qword_140015500, rax
0x14000d314  call    cs:__imp_GetProcAddress
0x14000d31a  test    rax, rax
0x14000d31d  jz      short loc_14000D340
0x14000d31f  mov     rcx, rax; Ptr
0x14000d322  call    cs:__imp_EncodePointer
0x14000d328  mov     cs:qword_1400154F8, rax
0x14000d32f  lock or [rsp+28h+var_28], 0
0x14000d334  mov     cs:byte_140015510, 1
0x14000d33b  jmp     loc_14000D263
0x14000d340  xor     eax, eax
0x14000d342  add     rsp, 20h
0x14000d346  pop     rbx
0x14000d347  retn
```
