# SHFusionLoadLibrary

- ea: `0x1800162c8`
- end: `0x180016320`
- name: `SHFusionLoadLibrary`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016524`

## callees

- `0x18001614c`
- `0x1800162c8`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x180016311`
- `KERNEL32!DeactivateActCtx` at `0x180016311`
- `KERNEL32!LoadLibraryExW` at `0x1800162fc`
- `KERNEL32!LoadLibraryExW` at `0x1800162fc`

## string_xrefs

- `0x1800162ef`: `comctl32.dll`

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
  if ( ulCookie )
    DeactivateActCtx(0, ulCookie);
  return Library;
}

```

## disassembly

```asm
0x1800162c8  mov     [rsp+ulCookie], rcx
0x1800162cd  push    rbx
0x1800162ce  sub     rsp, 20h
0x1800162d2  lea     rcx, [rsp+28h+ulCookie]
0x1800162d7  mov     [rsp+28h+ulCookie], 0
0x1800162e0  call    SHActivateContext
0x1800162e5  test    eax, eax
0x1800162e7  jnz     short loc_1800162ED
0x1800162e9  xor     eax, eax
0x1800162eb  jmp     short loc_18001631A
0x1800162ed  xor     edx, edx; hFile
0x1800162ef  lea     rcx, aComctl32Dll; "comctl32.dll"
0x1800162f6  mov     r8d, 4000h; dwFlags
0x1800162fc  call    cs:__imp_LoadLibraryExW
0x180016302  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x180016307  mov     rbx, rax
0x18001630a  test    rdx, rdx
0x18001630d  jz      short loc_180016317
0x18001630f  xor     ecx, ecx; dwFlags
0x180016311  call    cs:__imp_DeactivateActCtx
0x180016317  mov     rax, rbx
0x18001631a  add     rsp, 20h
0x18001631e  pop     rbx
0x18001631f  retn
```
