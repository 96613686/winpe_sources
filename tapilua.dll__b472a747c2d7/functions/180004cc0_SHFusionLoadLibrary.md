# SHFusionLoadLibrary

- ea: `0x180004cc0`
- end: `0x180004d18`
- name: `SHFusionLoadLibrary`
- size: `88`
- prototype: `HMODULE()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004d20`

## callees

- `0x180004b44`
- `0x180004cc0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180004cf4`
- `KERNEL32!LoadLibraryExW` at `0x180004cf4`
- `KERNEL32!DeactivateActCtx` at `0x180004d09`
- `KERNEL32!DeactivateActCtx` at `0x180004d09`

## string_xrefs

- `0x180004ce7`: `comctl32.dll`

## pseudocode

```c
HMODULE SHFusionLoadLibrary()
{
  HMODULE Library; // rbx
  ULONG_PTR ulCookie; // [rsp+30h] [rbp+8h] BYREF

  ulCookie = 0;
  if ( !SHActivateContext(&ulCookie) )
    return 0;
  Library = LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
  if ( ulCookie )
    DeactivateActCtx(0, ulCookie);
  return Library;
}

```

## disassembly

```asm
0x180004cc0  mov     [rsp+ulCookie], rcx
0x180004cc5  push    rbx
0x180004cc6  sub     rsp, 20h
0x180004cca  lea     rcx, [rsp+28h+ulCookie]
0x180004ccf  mov     [rsp+28h+ulCookie], 0
0x180004cd8  call    SHActivateContext
0x180004cdd  test    eax, eax
0x180004cdf  jnz     short loc_180004CE5
0x180004ce1  xor     eax, eax
0x180004ce3  jmp     short loc_180004D12
0x180004ce5  xor     edx, edx; hFile
0x180004ce7  lea     rcx, aComctl32Dll; "comctl32.dll"
0x180004cee  mov     r8d, 4000h; dwFlags
0x180004cf4  call    cs:__imp_LoadLibraryExW
0x180004cfa  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x180004cff  mov     rbx, rax
0x180004d02  test    rdx, rdx
0x180004d05  jz      short loc_180004D0F
0x180004d07  xor     ecx, ecx; dwFlags
0x180004d09  call    cs:__imp_DeactivateActCtx
0x180004d0f  mov     rax, rbx
0x180004d12  add     rsp, 20h
0x180004d16  pop     rbx
0x180004d17  retn
```
