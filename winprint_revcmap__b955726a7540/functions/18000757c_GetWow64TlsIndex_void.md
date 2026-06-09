# GetWow64TlsIndex(void)

- ea: `0x18000757c`
- end: `0x1800075d7`
- name: `?GetWow64TlsIndex@@YAKXZ`
- size: `91`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003d80`

## callees

- `0x18000757c`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800075c7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800075c7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007599`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007599`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800075af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800075af`

## pseudocode

```c
__int64 GetWow64TlsIndex(void)
{
  HMODULE Library; // rax
  HMODULE v1; // rbx
  FARPROC ProcAddress; // rax
  unsigned int v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = -1;
  Library = LoadLibraryExW(L"winspool.drv", 0, 0x800u);
  v1 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, (LPCSTR)0x16C);
    if ( ProcAddress )
      ((void (__fastcall *)(unsigned int *))ProcAddress)(&v4);
    FreeLibrary(v1);
  }
  return v4;
}

```

## disassembly

```asm
0x18000757c  push    rbx
0x18000757e  sub     rsp, 20h
0x180007582  xor     edx, edx; hFile
0x180007584  mov     [rsp+28h+arg_0], 0FFFFFFFFh
0x18000758c  mov     r8d, 800h; dwFlags
0x180007592  lea     rcx, LibFileName; "winspool.drv"
0x180007599  call    cs:__imp_LoadLibraryExW
0x18000759f  mov     rbx, rax
0x1800075a2  test    rax, rax
0x1800075a5  jz      short loc_1800075CD
0x1800075a7  mov     edx, 16Ch; lpProcName
0x1800075ac  mov     rcx, rax; hModule
0x1800075af  call    cs:__imp_GetProcAddress
0x1800075b5  test    rax, rax
0x1800075b8  jz      short loc_1800075C4
0x1800075ba  lea     rcx, [rsp+28h+arg_0]
0x1800075bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075c4  mov     rcx, rbx; hLibModule
0x1800075c7  call    cs:__imp_FreeLibrary
0x1800075cd  mov     eax, [rsp+28h+arg_0]
0x1800075d1  add     rsp, 20h
0x1800075d5  pop     rbx
0x1800075d6  retn
```
