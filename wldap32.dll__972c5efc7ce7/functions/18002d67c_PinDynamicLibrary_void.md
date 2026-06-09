# PinDynamicLibrary(void)

- ea: `0x18002d67c`
- end: `0x18002d70e`
- name: `?PinDynamicLibrary@@YAXXZ`
- size: `146`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002e24c`

## callees

- `0x18002d67c`
- `0x180034510`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18002d6bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18002d6bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6e9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18002d6d4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18002d6d4`

## pseudocode

```c
void PinDynamicLibrary(void)
{
  CHAR Filename[1056]; // [rsp+20h] [rbp-438h] BYREF

  if ( g_bLibraryLoadedDynamically && GlobalLdapDllInstance && !g_hPinnedDynamicLibrary )
  {
    if ( GetModuleFileNameA(GlobalLdapDllInstance, Filename, 0x411u) )
      g_hPinnedDynamicLibrary = LoadLibraryA(Filename);
    else
      GetLastError();
  }
}

```

## disassembly

```asm
0x18002d67c  sub     rsp, 458h
0x18002d683  mov     rax, cs:__security_cookie
0x18002d68a  xor     rax, rsp
0x18002d68d  mov     [rsp+458h+var_18], rax
0x18002d695  cmp     cs:?g_bLibraryLoadedDynamically@@3HA, 0; int g_bLibraryLoadedDynamically
0x18002d69c  jz      short loc_18002D6F5
0x18002d69e  mov     rcx, cs:GlobalLdapDllInstance; hModule
0x18002d6a5  test    rcx, rcx
0x18002d6a8  jz      short loc_18002D6F5
0x18002d6aa  cmp     cs:?g_hPinnedDynamicLibrary@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hPinnedDynamicLibrary
0x18002d6b2  jnz     short loc_18002D6F5
0x18002d6b4  mov     r8d, 411h; nSize
0x18002d6ba  lea     rdx, [rsp+458h+Filename]; lpFilename
0x18002d6bf  call    cs:__imp_GetModuleFileNameA
0x18002d6c6  nop     dword ptr [rax+rax+00h]
0x18002d6cb  test    eax, eax
0x18002d6cd  jz      short loc_18002D6E9
0x18002d6cf  lea     rcx, [rsp+458h+Filename]; lpLibFileName
0x18002d6d4  call    cs:__imp_LoadLibraryA
0x18002d6db  nop     dword ptr [rax+rax+00h]
0x18002d6e0  mov     cs:?g_hPinnedDynamicLibrary@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hPinnedDynamicLibrary
0x18002d6e7  jmp     short loc_18002D6F5
0x18002d6e9  call    cs:__imp_GetLastError
0x18002d6f0  nop     dword ptr [rax+rax+00h]
0x18002d6f5  mov     rcx, [rsp+458h+var_18]
0x18002d6fd  xor     rcx, rsp; StackCookie
0x18002d700  call    __security_check_cookie
0x18002d705  add     rsp, 458h
0x18002d70c  retn
```
