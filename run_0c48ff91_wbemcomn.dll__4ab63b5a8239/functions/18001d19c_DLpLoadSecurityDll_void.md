# DLpLoadSecurityDll(void)

- ea: `0x18001d19c`
- end: `0x18001d1fd`
- name: `?DLpLoadSecurityDll@@YAKXZ`
- size: `97`
- prototype: `unsigned int(void)`
- caller_count: `45`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009fd0`
- `0x180015a00`
- `0x180015d30`
- `0x18001b2e0`
- `0x18001b3c4`
- `0x18001b5c0`
- `0x18001be80`
- `0x18001c130`
- `0x18001c1e0`
- `0x18001c340`
- `0x18001c4fc`
- `0x18001c658`
- `0x18001c790`
- `0x18001c990`
- `0x18001ca00`
- `0x18001ca88`
- `0x18001cb10`
- `0x18001ccd0`
- `0x18001cd60`
- `0x18001d2d0`
- `0x18001d390`
- `0x18001d6c0`
- `0x180023160`
- `0x180023900`
- `0x180023a60`
- `0x180023b40`
- `0x180023d3c`
- `0x180023dac`
- `0x180024da0`
- `0x180025548`
- `0x180025634`
- `0x180025974`
- `0x180025aa0`
- `0x180025c5c`
- `0x18002a8e0`
- `0x18002aa24`
- `0x18002b370`
- `0x18002bda0`
- `0x18003c720`
- `0x18003cef0`
- `0x18003d310`
- `0x18003f730`
- `0x180043e24`
- `0x180043eac`
- `0x180043f2c`

## callees

- `0x18001d19c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d1f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d1f3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001d1c2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001d1e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001d1c2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001d1e1`

## string_xrefs

- `0x18001d1b7`: `API-MS-Win-Security-Base-L1-1-0.dll`
- `0x18001d1da`: `advapi32.dll`

## pseudocode

```c
__int64 DLpLoadSecurityDll(void)
{
  unsigned int v0; // ebx

  v0 = 0;
  if ( !g_hInstSecurityDLL )
  {
    g_hInstSecurityDLL = LoadLibraryExW(L"API-MS-Win-Security-Base-L1-1-0.dll", 0, 8u);
    if ( !g_hInstSecurityDLL )
    {
      g_hInstSecurityDLL = LoadLibraryExW(L"advapi32.dll", 0, 8u);
      if ( !g_hInstSecurityDLL )
        return GetLastError();
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18001d19c  push    rbx
0x18001d19e  sub     rsp, 20h
0x18001d1a2  xor     ebx, ebx
0x18001d1a4  cmp     cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInstSecurityDLL
0x18001d1ab  jz      short loc_18001D1B5
0x18001d1ad  mov     eax, ebx
0x18001d1af  add     rsp, 20h
0x18001d1b3  pop     rbx
0x18001d1b4  retn
0x18001d1b5  xor     edx, edx; hFile
0x18001d1b7  lea     rcx, aApiMsWinSecuri_0; "API-MS-Win-Security-Base-L1-1-0.dll"
0x18001d1be  lea     r8d, [rdx+8]; dwFlags
0x18001d1c2  call    cs:__imp_LoadLibraryExW
0x18001d1c8  mov     cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstSecurityDLL
0x18001d1cf  test    rax, rax
0x18001d1d2  jnz     short loc_18001D1AD
0x18001d1d4  xor     edx, edx; hFile
0x18001d1d6  lea     r8d, [rax+8]; dwFlags
0x18001d1da  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x18001d1e1  call    cs:__imp_LoadLibraryExW
0x18001d1e7  mov     cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstSecurityDLL
0x18001d1ee  test    rax, rax
0x18001d1f1  jnz     short loc_18001D1AD
0x18001d1f3  call    cs:__imp_GetLastError
0x18001d1f9  mov     ebx, eax
0x18001d1fb  jmp     short loc_18001D1AD
```
