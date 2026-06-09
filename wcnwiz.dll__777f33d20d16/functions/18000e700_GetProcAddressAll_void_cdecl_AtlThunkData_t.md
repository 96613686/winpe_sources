# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_

- ea: `0x18000e700`
- end: `0x18000e7c0`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000eadc`

## callees

- `0x18000e700`
- `0x18000e890`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000e731`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000e731`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000e71b`

## string_xrefs

- `0x18000e724`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_void____cdecl___AtlThunkData_t____()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed __int32 v3[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_18004DAC8 )
    return DecodePointer((PVOID)qword_18004DB48);
  Library = LoadLibraryExA("atlthunk.dll", 0, 0x800u);
  v2 = Library;
  if ( Library
    && (unsigned __int8)GetProcAddressSingle(Library, "AtlThunk_AllocateData", &qword_18004DB60)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_InitData", &qword_18004DB58)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_DataToCode", &qword_18004DB50)
    && (unsigned __int8)GetProcAddressSingle(v2, "AtlThunk_FreeData", &qword_18004DB48) )
  {
    _InterlockedOr(v3, 0);
    byte_18004DAC8 = 1;
    return DecodePointer((PVOID)qword_18004DB48);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e700  push    rbx
0x18000e702  sub     rsp, 20h
0x18000e706  cmp     cs:byte_18004DAC8, 0
0x18000e70d  jz      short loc_18000E722
0x18000e70f  mov     rcx, cs:qword_18004DB48
0x18000e716  add     rsp, 20h
0x18000e71a  pop     rbx
0x18000e71b  jmp     cs:__imp_DecodePointer
0x18000e722  xor     edx, edx; hFile
0x18000e724  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18000e72b  mov     r8d, 800h; dwFlags
0x18000e731  call    cs:__imp_LoadLibraryExA
0x18000e737  mov     rbx, rax
0x18000e73a  test    rax, rax
0x18000e73d  jz      short loc_18000E7B8
0x18000e73f  lea     r8, qword_18004DB60
0x18000e746  mov     rcx, rax
0x18000e749  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18000e750  call    GetProcAddressSingle
0x18000e755  test    al, al
0x18000e757  jz      short loc_18000E7B8
0x18000e759  lea     r8, qword_18004DB58
0x18000e760  mov     rcx, rbx
0x18000e763  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18000e76a  call    GetProcAddressSingle
0x18000e76f  test    al, al
0x18000e771  jz      short loc_18000E7B8
0x18000e773  lea     r8, qword_18004DB50
0x18000e77a  mov     rcx, rbx
0x18000e77d  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18000e784  call    GetProcAddressSingle
0x18000e789  test    al, al
0x18000e78b  jz      short loc_18000E7B8
0x18000e78d  lea     r8, qword_18004DB48
0x18000e794  mov     rcx, rbx
0x18000e797  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18000e79e  call    GetProcAddressSingle
0x18000e7a3  test    al, al
0x18000e7a5  jz      short loc_18000E7B8
0x18000e7a7  lock or [rsp+28h+var_28], 0
0x18000e7ac  mov     cs:byte_18004DAC8, 1
0x18000e7b3  jmp     loc_18000E70F
0x18000e7b8  xor     eax, eax
0x18000e7ba  add     rsp, 20h
0x18000e7be  pop     rbx
0x18000e7bf  retn
```
