# LoadHelperDLL

- ea: `0x1800039b0`
- end: `0x180003a33`
- name: `LoadHelperDLL`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000386c`

## callees

- `0x1800038dc`
- `0x1800039b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800039f1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800039f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039fc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003a20`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003a20`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800039e5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800039e5`

## pseudocode

```c
signed int LoadHelperDLL()
{
  const WCHAR *HelperDllFullPath; // rax
  WCHAR *v1; // rbx
  signed int result; // eax
  HMODULE Library; // rdi

  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hHelper, 0, 0) )
    return 0;
  HelperDllFullPath = (const WCHAR *)GetHelperDllFullPath();
  v1 = (WCHAR *)HelperDllFullPath;
  if ( !HelperDllFullPath )
    return -2147467259;
  Library = LoadLibraryExW(HelperDllFullPath, 0, 0);
  free(v1);
  if ( Library )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hHelper, (signed __int64)Library, 0) )
      FreeLibrary(Library);
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800039b0  mov     [rsp+arg_0], rbx
0x1800039b5  push    rdi
0x1800039b6  sub     rsp, 20h
0x1800039ba  xor     ecx, ecx
0x1800039bc  xor     eax, eax
0x1800039be  lock cmpxchg cs:g_hHelper, rcx
0x1800039c7  jnz     short loc_180003A26
0x1800039c9  call    GetHelperDllFullPath
0x1800039ce  mov     rbx, rax
0x1800039d1  test    rax, rax
0x1800039d4  jnz     short loc_1800039DD
0x1800039d6  mov     eax, 80004005h
0x1800039db  jmp     short loc_180003A28
0x1800039dd  xor     r8d, r8d; dwFlags
0x1800039e0  xor     edx, edx; hFile
0x1800039e2  mov     rcx, rbx; lpLibFileName
0x1800039e5  call    cs:__imp_LoadLibraryExW
0x1800039eb  mov     rcx, rbx; Block
0x1800039ee  mov     rdi, rax
0x1800039f1  call    cs:__imp_free
0x1800039f7  test    rdi, rdi
0x1800039fa  jnz     short loc_180003A10
0x1800039fc  call    cs:__imp_GetLastError
0x180003a02  test    eax, eax
0x180003a04  jle     short loc_180003A28
0x180003a06  movzx   eax, ax
0x180003a09  or      eax, 80070000h
0x180003a0e  jmp     short loc_180003A28
0x180003a10  xor     eax, eax
0x180003a12  lock cmpxchg cs:g_hHelper, rdi
0x180003a1b  jz      short loc_180003A26
0x180003a1d  mov     rcx, rdi; hLibModule
0x180003a20  call    cs:__imp_FreeLibrary
0x180003a26  xor     eax, eax
0x180003a28  mov     rbx, [rsp+28h+arg_0]
0x180003a2d  add     rsp, 20h
0x180003a31  pop     rdi
0x180003a32  retn
```
