# GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_

- ea: `0x180013bec`
- end: `0x180013ce0`
- name: `GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001401c`

## callees

- `0x180013bec`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x180013c4b`
- `KERNEL32!EncodePointer` at `0x180013c70`
- `KERNEL32!EncodePointer` at `0x180013c95`
- `KERNEL32!EncodePointer` at `0x180013cba`
- `KERNEL32!EncodePointer` at `0x180013c4b`
- `KERNEL32!EncodePointer` at `0x180013c70`
- `KERNEL32!EncodePointer` at `0x180013c95`
- `KERNEL32!EncodePointer` at `0x180013cba`
- `KERNEL32!DecodePointer` at `0x180013c07`
- `KERNEL32!LoadLibraryExA` at `0x180013c1d`
- `KERNEL32!LoadLibraryExA` at `0x180013c1d`
- `KERNEL32!GetProcAddress` at `0x180013c39`
- `KERNEL32!GetProcAddress` at `0x180013c62`
- `KERNEL32!GetProcAddress` at `0x180013c87`
- `KERNEL32!GetProcAddress` at `0x180013cac`
- `KERNEL32!GetProcAddress` at `0x180013c39`
- `KERNEL32!GetProcAddress` at `0x180013c62`
- `KERNEL32!GetProcAddress` at `0x180013c87`
- `KERNEL32!GetProcAddress` at `0x180013cac`

## string_xrefs

- `0x180013c10`: `atlthunk.dll`

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

  if ( byte_18001BDD8 )
    return DecodePointer((PVOID)qword_18001BDE0);
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
            return DecodePointer((PVOID)qword_18001BDE0);
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
0x180013bec  push    rbx
0x180013bee  sub     rsp, 20h
0x180013bf2  cmp     cs:byte_18001BDD8, 0
0x180013bf9  jz      short loc_180013C0E
0x180013bfb  mov     rcx, cs:qword_18001BDE0
0x180013c02  add     rsp, 20h
0x180013c06  pop     rbx
0x180013c07  jmp     cs:__imp_DecodePointer
0x180013c0e  xor     edx, edx; hFile
0x180013c10  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x180013c17  mov     r8d, 800h; dwFlags
0x180013c1d  call    cs:__imp_LoadLibraryExA
0x180013c23  mov     rbx, rax
0x180013c26  test    rax, rax
0x180013c29  jz      loc_180013CD8
0x180013c2f  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x180013c36  mov     rcx, rax; hModule
0x180013c39  call    cs:__imp_GetProcAddress
0x180013c3f  test    rax, rax
0x180013c42  jz      loc_180013CD8
0x180013c48  mov     rcx, rax; Ptr
0x180013c4b  call    cs:__imp_EncodePointer
0x180013c51  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x180013c58  mov     rcx, rbx; hModule
0x180013c5b  mov     cs:qword_18001BDE0, rax
0x180013c62  call    cs:__imp_GetProcAddress
0x180013c68  test    rax, rax
0x180013c6b  jz      short loc_180013CD8
0x180013c6d  mov     rcx, rax; Ptr
0x180013c70  call    cs:__imp_EncodePointer
0x180013c76  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x180013c7d  mov     rcx, rbx; hModule
0x180013c80  mov     cs:qword_18001BDD0, rax
0x180013c87  call    cs:__imp_GetProcAddress
0x180013c8d  test    rax, rax
0x180013c90  jz      short loc_180013CD8
0x180013c92  mov     rcx, rax; Ptr
0x180013c95  call    cs:__imp_EncodePointer
0x180013c9b  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x180013ca2  mov     rcx, rbx; hModule
0x180013ca5  mov     cs:qword_18001BDC8, rax
0x180013cac  call    cs:__imp_GetProcAddress
0x180013cb2  test    rax, rax
0x180013cb5  jz      short loc_180013CD8
0x180013cb7  mov     rcx, rax; Ptr
0x180013cba  call    cs:__imp_EncodePointer
0x180013cc0  mov     cs:qword_18001BDC0, rax
0x180013cc7  lock or [rsp+28h+var_28], 0
0x180013ccc  mov     cs:byte_18001BDD8, 1
0x180013cd3  jmp     loc_180013BFB
0x180013cd8  xor     eax, eax
0x180013cda  add     rsp, 20h
0x180013cde  pop     rbx
0x180013cdf  retn
```
