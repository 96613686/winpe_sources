# SHFusionLoadLibrary

- ea: `0x180027fc0`
- end: `0x180028010`
- name: `SHFusionLoadLibrary`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800280ac`

## callees

- `0x180027d70`
- `0x180027de0`
- `0x180027fc0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180027ff4`
- `KERNEL32!LoadLibraryExW` at `0x180027ff4`

## string_xrefs

- `0x180027fe7`: `comctl32.dll`

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
0x180027fc0  mov     [rsp+ulCookie], rcx
0x180027fc5  push    rbx
0x180027fc6  sub     rsp, 20h
0x180027fca  lea     rcx, [rsp+28h+ulCookie]
0x180027fcf  mov     [rsp+28h+ulCookie], 0
0x180027fd8  call    SHActivateContext
0x180027fdd  test    eax, eax
0x180027fdf  jnz     short loc_180027FE5
0x180027fe1  xor     eax, eax
0x180027fe3  jmp     short loc_18002800A
0x180027fe5  xor     edx, edx; hFile
0x180027fe7  lea     rcx, aComctl32Dll; "comctl32.dll"
0x180027fee  mov     r8d, 4000h; dwFlags
0x180027ff4  call    cs:__imp_LoadLibraryExW
0x180027ffa  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x180027fff  mov     rbx, rax
0x180028002  call    SHDeactivateContext
0x180028007  mov     rax, rbx
0x18002800a  add     rsp, 20h
0x18002800e  pop     rbx
0x18002800f  retn
```
