# DLpLoadProcThreadsDll(void)

- ea: `0x18001b340`
- end: `0x18001b3be`
- name: `?DLpLoadProcThreadsDll@@YAKXZ`
- size: `126`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015a00`
- `0x18001b1f4`
- `0x18001b264`
- `0x18001bc20`
- `0x18001d584`

## callees

- `0x18001b340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b3ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b3ae`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b35e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b37d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b39c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b35e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b37d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b39c`

## string_xrefs

- `0x18001b395`: `advapi32.dll`
- `0x18001b357`: `api-ms-win-core-processsecurity-l1-1-0.dll`
- `0x18001b376`: `API-MS-Win-Core-ProcessThreads-L1-1-0.dll`

## pseudocode

```c
__int64 DLpLoadProcThreadsDll(void)
{
  unsigned int v0; // ebx

  v0 = 0;
  if ( !g_hInstProcThreadsDLL )
  {
    g_hInstProcThreadsDLL = LoadLibraryExW(L"api-ms-win-core-processsecurity-l1-1-0.dll", 0, 8u);
    if ( !g_hInstProcThreadsDLL )
    {
      g_hInstProcThreadsDLL = LoadLibraryExW(L"API-MS-Win-Core-ProcessThreads-L1-1-0.dll", 0, 8u);
      if ( !g_hInstProcThreadsDLL )
      {
        g_hInstProcThreadsDLL = LoadLibraryExW(L"advapi32.dll", 0, 8u);
        if ( !g_hInstProcThreadsDLL )
          return GetLastError();
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18001b340  push    rbx
0x18001b342  sub     rsp, 20h
0x18001b346  xor     ebx, ebx
0x18001b348  cmp     cs:?g_hInstProcThreadsDLL@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInstProcThreadsDLL
0x18001b34f  jnz     short loc_18001B3B6
0x18001b351  xor     edx, edx; hFile
0x18001b353  lea     r8d, [rbx+8]; dwFlags
0x18001b357  lea     rcx, aApiMsWinCorePr_3; "api-ms-win-core-processsecurity-l1-1-0."...
0x18001b35e  call    cs:__imp_LoadLibraryExW
0x18001b364  mov     cs:?g_hInstProcThreadsDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstProcThreadsDLL
0x18001b36b  test    rax, rax
0x18001b36e  jnz     short loc_18001B3B6
0x18001b370  xor     edx, edx; hFile
0x18001b372  lea     r8d, [rbx+8]; dwFlags
0x18001b376  lea     rcx, aApiMsWinCorePr_2; "API-MS-Win-Core-ProcessThreads-L1-1-0.d"...
0x18001b37d  call    cs:__imp_LoadLibraryExW
0x18001b383  mov     cs:?g_hInstProcThreadsDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstProcThreadsDLL
0x18001b38a  test    rax, rax
0x18001b38d  jnz     short loc_18001B3B6
0x18001b38f  xor     edx, edx; hFile
0x18001b391  lea     r8d, [rbx+8]; dwFlags
0x18001b395  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x18001b39c  call    cs:__imp_LoadLibraryExW
0x18001b3a2  mov     cs:?g_hInstProcThreadsDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstProcThreadsDLL
0x18001b3a9  test    rax, rax
0x18001b3ac  jnz     short loc_18001B3B6
0x18001b3ae  call    cs:__imp_GetLastError
0x18001b3b4  mov     ebx, eax
0x18001b3b6  mov     eax, ebx
0x18001b3b8  add     rsp, 20h
0x18001b3bc  pop     rbx
0x18001b3bd  retn
```
