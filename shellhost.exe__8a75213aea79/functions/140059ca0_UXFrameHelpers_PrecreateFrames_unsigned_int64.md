# UXFrameHelpers::PrecreateFrames(unsigned __int64)

- ea: `0x140059ca0`
- end: `0x140059ce6`
- name: `?PrecreateFrames@UXFrameHelpers@@YAX_K@Z`
- size: `70`
- prototype: `void __fastcall(UXFrameHelpers *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140053d50`

## callees

- `0x140059ca0`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140059ccd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140059ccd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140059cb8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140059cb8`

## string_xrefs

- `0x140059cc3`: `UXFramePrecreate`
- `0x140059cab`: `UXFrame.dll`

## pseudocode

```c
void __fastcall UXFrameHelpers::PrecreateFrames(UXFrameHelpers *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax

  Library = LoadLibraryExW(L"UXFrame.dll", 0, 0x800u);
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "UXFramePrecreate");
    if ( ProcAddress )
      ((void (__fastcall *)(UXFrameHelpers *))ProcAddress)(this);
  }
}

```

## disassembly

```asm
0x140059ca0  push    rbx
0x140059ca2  sub     rsp, 20h
0x140059ca6  mov     rbx, rcx
0x140059ca9  xor     edx, edx; hFile
0x140059cab  lea     rcx, aUxframeDll; "UXFrame.dll"
0x140059cb2  mov     r8d, 800h; dwFlags
0x140059cb8  call    cs:__imp_LoadLibraryExW
0x140059cbe  test    rax, rax
0x140059cc1  jz      short loc_140059CE0
0x140059cc3  lea     rdx, aUxframeprecrea; "UXFramePrecreate"
0x140059cca  mov     rcx, rax; hModule
0x140059ccd  call    cs:__imp_GetProcAddress
0x140059cd3  test    rax, rax
0x140059cd6  jz      short loc_140059CE0
0x140059cd8  mov     rcx, rbx
0x140059cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059ce0  add     rsp, 20h
0x140059ce4  pop     rbx
0x140059ce5  retn
```
