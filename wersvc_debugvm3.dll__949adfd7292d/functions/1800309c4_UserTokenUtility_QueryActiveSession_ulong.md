# UserTokenUtility::QueryActiveSession(ulong *)

- ea: `0x1800309c4`
- end: `0x180030a4f`
- name: `?QueryActiveSession@UserTokenUtility@@SAJPEAK@Z`
- size: `139`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002ff0c`

## callees

- `0x1800309c4`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030a20`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030a20`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030a3c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030a3c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800309ec`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800309ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800309ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800309ff`

## string_xrefs

- `0x1800309e5`: `kernel32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserTokenUtility::QueryActiveSession(unsigned int *a1)
{
  HMODULE Library; // rax
  HMODULE v4; // rdi
  signed int LastError; // eax
  unsigned int v6; // ebx
  __int64 (*ProcAddress)(void); // rax

  if ( !a1 )
    return 2147942487LL;
  Library = LoadLibraryExW(L"kernel32.dll", 0, 0x800u);
  v4 = Library;
  if ( Library && (ProcAddress = GetProcAddress(Library, "WTSGetActiveConsoleSessionId")) != 0 )
  {
    *a1 = ProcAddress();
    v6 = 0;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v4 )
    FreeLibrary(v4);
  return v6;
}

```

## disassembly

```asm
0x1800309c4  mov     [rsp+arg_8], rbx
0x1800309c9  push    rdi
0x1800309ca  sub     rsp, 20h
0x1800309ce  mov     rbx, rcx
0x1800309d1  test    rcx, rcx
0x1800309d4  jnz     short loc_1800309DD
0x1800309d6  mov     eax, 80070057h
0x1800309db  jmp     short loc_180030A44
0x1800309dd  xor     edx, edx; hFile
0x1800309df  mov     r8d, 800h; dwFlags
0x1800309e5  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800309ec  call    cs:__imp_LoadLibraryExW
0x1800309f2  mov     rdi, rax
0x1800309f5  mov     [rsp+28h+arg_0], rax
0x1800309fa  test    rax, rax
0x1800309fd  jnz     short loc_180030A16
0x1800309ff  call    cs:__imp_GetLastError
0x180030a05  mov     ebx, eax
0x180030a07  test    eax, eax
0x180030a09  jle     short loc_180030A34
0x180030a0b  movzx   ebx, ax
0x180030a0e  or      ebx, 80070000h
0x180030a14  jmp     short loc_180030A34
0x180030a16  lea     rdx, aWtsgetactiveco; "WTSGetActiveConsoleSessionId"
0x180030a1d  mov     rcx, rdi; hModule
0x180030a20  call    cs:__imp_GetProcAddress
0x180030a26  test    rax, rax
0x180030a29  jz      short loc_1800309FF
0x180030a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a30  mov     [rbx], eax
0x180030a32  xor     ebx, ebx
0x180030a34  test    rdi, rdi
0x180030a37  jz      short loc_180030A42
0x180030a39  mov     rcx, rdi; hLibModule
0x180030a3c  call    cs:__imp_FreeLibrary
0x180030a42  mov     eax, ebx
0x180030a44  mov     rbx, [rsp+28h+arg_8]
0x180030a49  add     rsp, 20h
0x180030a4d  pop     rdi
0x180030a4e  retn
```
