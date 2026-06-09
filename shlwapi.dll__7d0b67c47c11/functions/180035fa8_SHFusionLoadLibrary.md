# SHFusionLoadLibrary

- ea: `0x180035fa8`
- end: `0x180035ff8`
- name: `SHFusionLoadLibrary`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800361f4`

## callees

- `0x180035e08`
- `0x180035e70`
- `0x180035fa8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180035fdc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180035fdc`

## string_xrefs

- `0x180035fcf`: `comctl32.dll`

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
0x180035fa8  mov     [rsp+ulCookie], rcx
0x180035fad  push    rbx
0x180035fae  sub     rsp, 20h
0x180035fb2  lea     rcx, [rsp+28h+ulCookie]
0x180035fb7  mov     [rsp+28h+ulCookie], 0
0x180035fc0  call    SHActivateContext
0x180035fc5  test    eax, eax
0x180035fc7  jnz     short loc_180035FCD
0x180035fc9  xor     eax, eax
0x180035fcb  jmp     short loc_180035FF2
0x180035fcd  xor     edx, edx; hFile
0x180035fcf  lea     rcx, aComctl32Dll_0; "comctl32.dll"
0x180035fd6  mov     r8d, 4000h; dwFlags
0x180035fdc  call    cs:__imp_LoadLibraryExW
0x180035fe2  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x180035fe7  mov     rbx, rax
0x180035fea  call    SHDeactivateContext
0x180035fef  mov     rax, rbx
0x180035ff2  add     rsp, 20h
0x180035ff6  pop     rbx
0x180035ff7  retn
```
