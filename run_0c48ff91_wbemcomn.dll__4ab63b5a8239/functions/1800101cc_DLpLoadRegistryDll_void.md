# DLpLoadRegistryDll(void)

- ea: `0x1800101cc`
- end: `0x18001022d`
- name: `?DLpLoadRegistryDll@@YAKXZ`
- size: `97`
- prototype: `unsigned int(void)`
- caller_count: `13`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18000f380`
- `0x18000f5b4`
- `0x18000f670`
- `0x18000fa30`
- `0x18000fac0`
- `0x18000ff54`
- `0x18001001c`
- `0x18001016c`
- `0x18001e2b0`
- `0x180028920`
- `0x180028de4`
- `0x18002b204`
- `0x180043fa4`

## callees

- `0x1800101cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010223`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010223`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800101f2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180010211`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800101f2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180010211`

## string_xrefs

- `0x1800101e7`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18001020a`: `advapi32.dll`

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
0x1800101cc  push    rbx
0x1800101ce  sub     rsp, 20h
0x1800101d2  xor     ebx, ebx
0x1800101d4  cmp     cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInstRegistryDLL
0x1800101db  jz      short loc_1800101E5
0x1800101dd  mov     eax, ebx
0x1800101df  add     rsp, 20h
0x1800101e3  pop     rbx
0x1800101e4  retn
0x1800101e5  xor     edx, edx; hFile
0x1800101e7  lea     rcx, LibFileName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800101ee  lea     r8d, [rdx+8]; dwFlags
0x1800101f2  call    cs:__imp_LoadLibraryExW
0x1800101f8  mov     cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstRegistryDLL
0x1800101ff  test    rax, rax
0x180010202  jnz     short loc_1800101DD
0x180010204  xor     edx, edx; hFile
0x180010206  lea     r8d, [rax+8]; dwFlags
0x18001020a  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180010211  call    cs:__imp_LoadLibraryExW
0x180010217  mov     cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstRegistryDLL
0x18001021e  test    rax, rax
0x180010221  jnz     short loc_1800101DD
0x180010223  call    cs:__imp_GetLastError
0x180010229  mov     ebx, eax
0x18001022b  jmp     short loc_1800101DD
```
