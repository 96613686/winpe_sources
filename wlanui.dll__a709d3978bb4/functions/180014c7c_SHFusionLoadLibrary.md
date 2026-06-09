# SHFusionLoadLibrary

- ea: `0x180014c7c`
- end: `0x180014cd4`
- name: `SHFusionLoadLibrary`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014dd8`

## callees

- `0x180014b00`
- `0x180014c7c`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180014cb0`
- `KERNEL32!LoadLibraryExW` at `0x180014cb0`
- `KERNEL32!DeactivateActCtx` at `0x180014cc5`
- `KERNEL32!DeactivateActCtx` at `0x180014cc5`

## string_xrefs

- `0x180014ca3`: `comctl32.dll`

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
0x180014c7c  mov     [rsp+ulCookie], rcx
0x180014c81  push    rbx
0x180014c82  sub     rsp, 20h
0x180014c86  lea     rcx, [rsp+28h+ulCookie]
0x180014c8b  mov     [rsp+28h+ulCookie], 0
0x180014c94  call    SHActivateContext
0x180014c99  test    eax, eax
0x180014c9b  jnz     short loc_180014CA1
0x180014c9d  xor     eax, eax
0x180014c9f  jmp     short loc_180014CCE
0x180014ca1  xor     edx, edx; hFile
0x180014ca3  lea     rcx, aComctl32Dll; "comctl32.dll"
0x180014caa  mov     r8d, 4000h; dwFlags
0x180014cb0  call    cs:__imp_LoadLibraryExW
0x180014cb6  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x180014cbb  mov     rbx, rax
0x180014cbe  test    rdx, rdx
0x180014cc1  jz      short loc_180014CCB
0x180014cc3  xor     ecx, ecx; dwFlags
0x180014cc5  call    cs:__imp_DeactivateActCtx
0x180014ccb  mov     rax, rbx
0x180014cce  add     rsp, 20h
0x180014cd2  pop     rbx
0x180014cd3  retn
```
