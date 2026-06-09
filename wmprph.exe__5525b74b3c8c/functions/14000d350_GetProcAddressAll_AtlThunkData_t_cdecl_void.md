# GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_

- ea: `0x14000d350`
- end: `0x14000d444`
- name: `GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000d780`

## callees

- `0x14000d350`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000d39d`
- `KERNEL32!GetProcAddress` at `0x14000d3c6`
- `KERNEL32!GetProcAddress` at `0x14000d3eb`
- `KERNEL32!GetProcAddress` at `0x14000d410`
- `KERNEL32!GetProcAddress` at `0x14000d39d`
- `KERNEL32!GetProcAddress` at `0x14000d3c6`
- `KERNEL32!GetProcAddress` at `0x14000d3eb`
- `KERNEL32!GetProcAddress` at `0x14000d410`
- `KERNEL32!LoadLibraryExA` at `0x14000d381`
- `KERNEL32!LoadLibraryExA` at `0x14000d381`
- `KERNEL32!DecodePointer` at `0x14000d36b`
- `KERNEL32!EncodePointer` at `0x14000d3af`
- `KERNEL32!EncodePointer` at `0x14000d3d4`
- `KERNEL32!EncodePointer` at `0x14000d3f9`
- `KERNEL32!EncodePointer` at `0x14000d41e`
- `KERNEL32!EncodePointer` at `0x14000d3af`
- `KERNEL32!EncodePointer` at `0x14000d3d4`
- `KERNEL32!EncodePointer` at `0x14000d3f9`
- `KERNEL32!EncodePointer` at `0x14000d41e`

## string_xrefs

- `0x14000d374`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_AtlThunkData_t______cdecl___void__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  signed __int32 v7[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_140015510 )
    return DecodePointer((PVOID)qword_140015518);
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
            return DecodePointer((PVOID)qword_140015518);
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
0x14000d350  push    rbx
0x14000d352  sub     rsp, 20h
0x14000d356  cmp     cs:byte_140015510, 0
0x14000d35d  jz      short loc_14000D372
0x14000d35f  mov     rcx, cs:qword_140015518
0x14000d366  add     rsp, 20h
0x14000d36a  pop     rbx
0x14000d36b  jmp     cs:__imp_DecodePointer
0x14000d372  xor     edx, edx; hFile
0x14000d374  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x14000d37b  mov     r8d, 800h; dwFlags
0x14000d381  call    cs:__imp_LoadLibraryExA
0x14000d387  mov     rbx, rax
0x14000d38a  test    rax, rax
0x14000d38d  jz      loc_14000D43C
0x14000d393  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x14000d39a  mov     rcx, rax; hModule
0x14000d39d  call    cs:__imp_GetProcAddress
0x14000d3a3  test    rax, rax
0x14000d3a6  jz      loc_14000D43C
0x14000d3ac  mov     rcx, rax; Ptr
0x14000d3af  call    cs:__imp_EncodePointer
0x14000d3b5  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x14000d3bc  mov     rcx, rbx; hModule
0x14000d3bf  mov     cs:qword_140015518, rax
0x14000d3c6  call    cs:__imp_GetProcAddress
0x14000d3cc  test    rax, rax
0x14000d3cf  jz      short loc_14000D43C
0x14000d3d1  mov     rcx, rax; Ptr
0x14000d3d4  call    cs:__imp_EncodePointer
0x14000d3da  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x14000d3e1  mov     rcx, rbx; hModule
0x14000d3e4  mov     cs:qword_140015508, rax
0x14000d3eb  call    cs:__imp_GetProcAddress
0x14000d3f1  test    rax, rax
0x14000d3f4  jz      short loc_14000D43C
0x14000d3f6  mov     rcx, rax; Ptr
0x14000d3f9  call    cs:__imp_EncodePointer
0x14000d3ff  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x14000d406  mov     rcx, rbx; hModule
0x14000d409  mov     cs:qword_140015500, rax
0x14000d410  call    cs:__imp_GetProcAddress
0x14000d416  test    rax, rax
0x14000d419  jz      short loc_14000D43C
0x14000d41b  mov     rcx, rax; Ptr
0x14000d41e  call    cs:__imp_EncodePointer
0x14000d424  mov     cs:qword_1400154F8, rax
0x14000d42b  lock or [rsp+28h+var_28], 0
0x14000d430  mov     cs:byte_140015510, 1
0x14000d437  jmp     loc_14000D35F
0x14000d43c  xor     eax, eax
0x14000d43e  add     rsp, 20h
0x14000d442  pop     rbx
0x14000d443  retn
```
