# DLpLoadRegistryDll(void)

- ea: `0x180009ccc`
- end: `0x180009d2b`
- name: `?DLpLoadRegistryDll@@YAKXZ`
- size: `95`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180009c6c`

## callees

- `0x180009ccc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d1b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180009cea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180009d09`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180009cea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180009d09`

## string_xrefs

- `0x180009ce3`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180009d02`: `advapi32.dll`

## pseudocode

```c
__int64 DLpLoadRegistryDll(void)
{
  unsigned int v0; // ebx

  v0 = 0;
  if ( !g_hInstRegistryDLL )
  {
    g_hInstRegistryDLL = LoadLibraryExW(L"API-MS-Win-Core-LocalRegistry-L1-1-0.dll", 0, 8u);
    if ( !g_hInstRegistryDLL )
    {
      g_hInstRegistryDLL = LoadLibraryExW(L"advapi32.dll", 0, 8u);
      if ( !g_hInstRegistryDLL )
        return GetLastError();
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180009ccc  push    rbx
0x180009cce  sub     rsp, 20h
0x180009cd2  xor     ebx, ebx
0x180009cd4  cmp     cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInstRegistryDLL
0x180009cdb  jnz     short loc_180009D23
0x180009cdd  xor     edx, edx; hFile
0x180009cdf  lea     r8d, [rbx+8]; dwFlags
0x180009ce3  lea     rcx, LibFileName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180009cea  call    cs:__imp_LoadLibraryExW
0x180009cf0  mov     cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstRegistryDLL
0x180009cf7  test    rax, rax
0x180009cfa  jnz     short loc_180009D23
0x180009cfc  xor     edx, edx; hFile
0x180009cfe  lea     r8d, [rbx+8]; dwFlags
0x180009d02  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180009d09  call    cs:__imp_LoadLibraryExW
0x180009d0f  mov     cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstRegistryDLL
0x180009d16  test    rax, rax
0x180009d19  jnz     short loc_180009D23
0x180009d1b  call    cs:__imp_GetLastError
0x180009d21  mov     ebx, eax
0x180009d23  mov     eax, ebx
0x180009d25  add     rsp, 20h
0x180009d29  pop     rbx
0x180009d2a  retn
```
