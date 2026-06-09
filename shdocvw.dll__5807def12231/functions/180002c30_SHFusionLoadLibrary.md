# SHFusionLoadLibrary

- ea: `0x180002c30`
- end: `0x180002c93`
- name: `SHFusionLoadLibrary`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002db0`
- `0x180006880`

## callees

- `0x180002c30`
- `0x180002ca0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002c6b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002c6b`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180002c80`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180002c80`

## string_xrefs

- `0x180002c64`: `comctl32.dll`

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
0x180002c30  mov     [rsp+ulCookie], rcx
0x180002c35  sub     rsp, 28h
0x180002c39  lea     rcx, [rsp+28h+ulCookie]
0x180002c3e  mov     [rsp+28h+ulCookie], 0
0x180002c47  call    SHActivateContext
0x180002c4c  test    eax, eax
0x180002c4e  jnz     short loc_180002C57
0x180002c50  xor     eax, eax
0x180002c52  add     rsp, 28h
0x180002c56  retn
0x180002c57  xor     edx, edx; hFile
0x180002c59  mov     [rsp+28h+var_8], rbx
0x180002c5e  mov     r8d, 4000h; dwFlags
0x180002c64  lea     rcx, LibFileName; "comctl32.dll"
0x180002c6b  call    cs:__imp_LoadLibraryExW
0x180002c71  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x180002c76  mov     rbx, rax
0x180002c79  test    rdx, rdx
0x180002c7c  jz      short loc_180002C86
0x180002c7e  xor     ecx, ecx; dwFlags
0x180002c80  call    cs:__imp_DeactivateActCtx
0x180002c86  mov     rax, rbx
0x180002c89  mov     rbx, [rsp+28h+var_8]
0x180002c8e  add     rsp, 28h
0x180002c92  retn
```
