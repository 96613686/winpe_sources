# SHFusionLoadLibrary

- ea: `0x180027010`
- end: `0x180027060`
- name: `SHFusionLoadLibrary`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027068`

## callees

- `0x180026e74`
- `0x180026ee4`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027044`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027044`

## string_xrefs

- `0x180027037`: `comctl32.dll`

## pseudocode

```c
HMODULE SHFusionLoadLibrary()
{
  HMODULE Library; // rbx
  ULONG_PTR ulCookie; // [rsp+30h] [rbp+8h] BYREF

  ulCookie = 0;
  if ( !(unsigned int)SHActivateContext(&ulCookie) )
    return 0;
  Library = LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
  SHDeactivateContext(ulCookie);
  return Library;
}

```

## disassembly

```asm
0x180027010  mov     [rsp+ulCookie], rcx
0x180027015  push    rbx
0x180027016  sub     rsp, 20h
0x18002701a  lea     rcx, [rsp+28h+ulCookie]
0x18002701f  mov     [rsp+28h+ulCookie], 0
0x180027028  call    SHActivateContext
0x18002702d  test    eax, eax
0x18002702f  jnz     short loc_180027035
0x180027031  xor     eax, eax
0x180027033  jmp     short loc_18002705A
0x180027035  xor     edx, edx; hFile
0x180027037  lea     rcx, aComctl32Dll_0; "comctl32.dll"
0x18002703e  mov     r8d, 4000h; dwFlags
0x180027044  call    cs:__imp_LoadLibraryExW
0x18002704a  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x18002704f  mov     rbx, rax
0x180027052  call    SHDeactivateContext
0x180027057  mov     rax, rbx
0x18002705a  add     rsp, 20h
0x18002705e  pop     rbx
0x18002705f  retn
```
