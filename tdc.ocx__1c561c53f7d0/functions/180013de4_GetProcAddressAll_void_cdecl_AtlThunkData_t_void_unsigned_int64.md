# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_

- ea: `0x180013de4`
- end: `0x180013ed8`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180014138`

## callees

- `0x180013de4`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x180013e43`
- `KERNEL32!EncodePointer` at `0x180013e68`
- `KERNEL32!EncodePointer` at `0x180013e8d`
- `KERNEL32!EncodePointer` at `0x180013eb2`
- `KERNEL32!EncodePointer` at `0x180013e43`
- `KERNEL32!EncodePointer` at `0x180013e68`
- `KERNEL32!EncodePointer` at `0x180013e8d`
- `KERNEL32!EncodePointer` at `0x180013eb2`
- `KERNEL32!DecodePointer` at `0x180013dff`
- `KERNEL32!LoadLibraryExA` at `0x180013e15`
- `KERNEL32!LoadLibraryExA` at `0x180013e15`
- `KERNEL32!GetProcAddress` at `0x180013e31`
- `KERNEL32!GetProcAddress` at `0x180013e5a`
- `KERNEL32!GetProcAddress` at `0x180013e7f`
- `KERNEL32!GetProcAddress` at `0x180013ea4`
- `KERNEL32!GetProcAddress` at `0x180013e31`
- `KERNEL32!GetProcAddress` at `0x180013e5a`
- `KERNEL32!GetProcAddress` at `0x180013e7f`
- `KERNEL32!GetProcAddress` at `0x180013ea4`

## string_xrefs

- `0x180013e08`: `atlthunk.dll`

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

  if ( byte_18001BDD8 )
    return DecodePointer((PVOID)qword_18001BDD0);
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
            return DecodePointer((PVOID)qword_18001BDD0);
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
0x180013de4  push    rbx
0x180013de6  sub     rsp, 20h
0x180013dea  cmp     cs:byte_18001BDD8, 0
0x180013df1  jz      short loc_180013E06
0x180013df3  mov     rcx, cs:qword_18001BDD0
0x180013dfa  add     rsp, 20h
0x180013dfe  pop     rbx
0x180013dff  jmp     cs:__imp_DecodePointer
0x180013e06  xor     edx, edx; hFile
0x180013e08  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x180013e0f  mov     r8d, 800h; dwFlags
0x180013e15  call    cs:__imp_LoadLibraryExA
0x180013e1b  mov     rbx, rax
0x180013e1e  test    rax, rax
0x180013e21  jz      loc_180013ED0
0x180013e27  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x180013e2e  mov     rcx, rax; hModule
0x180013e31  call    cs:__imp_GetProcAddress
0x180013e37  test    rax, rax
0x180013e3a  jz      loc_180013ED0
0x180013e40  mov     rcx, rax; Ptr
0x180013e43  call    cs:__imp_EncodePointer
0x180013e49  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x180013e50  mov     rcx, rbx; hModule
0x180013e53  mov     cs:qword_18001BDE0, rax
0x180013e5a  call    cs:__imp_GetProcAddress
0x180013e60  test    rax, rax
0x180013e63  jz      short loc_180013ED0
0x180013e65  mov     rcx, rax; Ptr
0x180013e68  call    cs:__imp_EncodePointer
0x180013e6e  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x180013e75  mov     rcx, rbx; hModule
0x180013e78  mov     cs:qword_18001BDD0, rax
0x180013e7f  call    cs:__imp_GetProcAddress
0x180013e85  test    rax, rax
0x180013e88  jz      short loc_180013ED0
0x180013e8a  mov     rcx, rax; Ptr
0x180013e8d  call    cs:__imp_EncodePointer
0x180013e93  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x180013e9a  mov     rcx, rbx; hModule
0x180013e9d  mov     cs:qword_18001BDC8, rax
0x180013ea4  call    cs:__imp_GetProcAddress
0x180013eaa  test    rax, rax
0x180013ead  jz      short loc_180013ED0
0x180013eaf  mov     rcx, rax; Ptr
0x180013eb2  call    cs:__imp_EncodePointer
0x180013eb8  mov     cs:qword_18001BDC0, rax
0x180013ebf  lock or [rsp+28h+var_28], 0
0x180013ec4  mov     cs:byte_18001BDD8, 1
0x180013ecb  jmp     loc_180013DF3
0x180013ed0  xor     eax, eax
0x180013ed2  add     rsp, 20h
0x180013ed6  pop     rbx
0x180013ed7  retn
```
