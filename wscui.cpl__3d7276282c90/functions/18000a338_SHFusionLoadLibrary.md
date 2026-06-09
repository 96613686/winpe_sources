# SHFusionLoadLibrary

- ea: `0x18000a338`
- end: `0x18000a388`
- name: `SHFusionLoadLibrary`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a03c`

## callees

- `0x18000a198`
- `0x18000a200`
- `0x18000a338`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a36c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a36c`

## string_xrefs

- `0x18000a35f`: `comctl32.dll`

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
0x18000a338  mov     [rsp+ulCookie], rcx
0x18000a33d  push    rbx
0x18000a33e  sub     rsp, 20h
0x18000a342  lea     rcx, [rsp+28h+ulCookie]
0x18000a347  mov     [rsp+28h+ulCookie], 0
0x18000a350  call    SHActivateContext
0x18000a355  test    eax, eax
0x18000a357  jnz     short loc_18000A35D
0x18000a359  xor     eax, eax
0x18000a35b  jmp     short loc_18000A382
0x18000a35d  xor     edx, edx; hFile
0x18000a35f  lea     rcx, aComctl32Dll_0; "comctl32.dll"
0x18000a366  mov     r8d, 4000h; dwFlags
0x18000a36c  call    cs:__imp_LoadLibraryExW
0x18000a372  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x18000a377  mov     rbx, rax
0x18000a37a  call    SHDeactivateContext
0x18000a37f  mov     rax, rbx
0x18000a382  add     rsp, 20h
0x18000a386  pop     rbx
0x18000a387  retn
```
