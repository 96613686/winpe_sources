# SHFusionLoadLibrary

- ea: `0x18002fc04`
- end: `0x18002fc54`
- name: `SHFusionLoadLibrary`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180030044`

## callees

- `0x18002f938`
- `0x18002f9a8`
- `0x18002fc04`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002fc38`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002fc38`

## string_xrefs

- `0x18002fc2b`: `comctl32.dll`

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
0x18002fc04  mov     [rsp+ulCookie], rcx
0x18002fc09  push    rbx
0x18002fc0a  sub     rsp, 20h
0x18002fc0e  lea     rcx, [rsp+28h+ulCookie]
0x18002fc13  mov     [rsp+28h+ulCookie], 0
0x18002fc1c  call    SHActivateContext
0x18002fc21  test    eax, eax
0x18002fc23  jnz     short loc_18002FC29
0x18002fc25  xor     eax, eax
0x18002fc27  jmp     short loc_18002FC4E
0x18002fc29  xor     edx, edx; hFile
0x18002fc2b  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18002fc32  mov     r8d, 4000h; dwFlags
0x18002fc38  call    cs:__imp_LoadLibraryExW
0x18002fc3e  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x18002fc43  mov     rbx, rax
0x18002fc46  call    SHDeactivateContext
0x18002fc4b  mov     rax, rbx
0x18002fc4e  add     rsp, 20h
0x18002fc52  pop     rbx
0x18002fc53  retn
```
