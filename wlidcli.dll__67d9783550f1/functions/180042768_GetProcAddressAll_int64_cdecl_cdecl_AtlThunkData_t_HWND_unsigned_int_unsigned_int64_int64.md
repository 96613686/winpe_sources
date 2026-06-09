# GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_

- ea: `0x180042768`
- end: `0x180042828`
- name: `GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180042c90`

## callees

- `0x180042768`
- `0x180042a88`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180042799`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180042799`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180042783`

## string_xrefs

- `0x18004278c`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll___int64____cdecl____cdecl___AtlThunkData_t_____HWND_____unsigned_int_unsigned___int64___int64__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180094CF8 )
    return DecodePointer((PVOID)qword_180094DA8);
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
    return DecodePointer((PVOID)qword_180094DA8);
  }
  return 0;
}

```

## disassembly

```asm
0x180042768  push    rbx
0x18004276a  sub     rsp, 20h
0x18004276e  cmp     cs:byte_180094CF8, 0
0x180042775  jz      short loc_18004278A
0x180042777  mov     rcx, cs:qword_180094DA8
0x18004277e  add     rsp, 20h
0x180042782  pop     rbx
0x180042783  jmp     cs:__imp_DecodePointer
0x18004278a  xor     edx, edx; hFile
0x18004278c  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x180042793  mov     r8d, 800h; dwFlags
0x180042799  call    cs:__imp_LoadLibraryExA
0x18004279f  mov     rbx, rax
0x1800427a2  test    rax, rax
0x1800427a5  jz      short loc_180042820
0x1800427a7  lea     r8, qword_180094DB8
0x1800427ae  mov     rcx, rax
0x1800427b1  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x1800427b8  call    GetProcAddressSingle
0x1800427bd  test    al, al
0x1800427bf  jz      short loc_180042820
0x1800427c1  lea     r8, qword_180094DB0
0x1800427c8  mov     rcx, rbx
0x1800427cb  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x1800427d2  call    GetProcAddressSingle
0x1800427d7  test    al, al
0x1800427d9  jz      short loc_180042820
0x1800427db  lea     r8, qword_180094DA8
0x1800427e2  mov     rcx, rbx
0x1800427e5  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x1800427ec  call    GetProcAddressSingle
0x1800427f1  test    al, al
0x1800427f3  jz      short loc_180042820
0x1800427f5  lea     r8, qword_180094DA0
0x1800427fc  mov     rcx, rbx
0x1800427ff  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x180042806  call    GetProcAddressSingle
0x18004280b  test    al, al
0x18004280d  jz      short loc_180042820
0x18004280f  lock or [rsp+28h+var_28], 0
0x180042814  mov     cs:byte_180094CF8, 1
0x18004281b  jmp     loc_180042777
0x180042820  xor     eax, eax
0x180042822  add     rsp, 20h
0x180042826  pop     rbx
0x180042827  retn
```
