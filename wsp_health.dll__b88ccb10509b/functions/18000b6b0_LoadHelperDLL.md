# LoadHelperDLL

- ea: `0x18000b6b0`
- end: `0x18000b733`
- name: `LoadHelperDLL`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b56c`

## callees

- `0x18000b5dc`
- `0x18000b6b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b6f1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b6f1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000b6e5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000b6e5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b720`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6fc`

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
0x18000b6b0  mov     [rsp+arg_0], rbx
0x18000b6b5  push    rdi
0x18000b6b6  sub     rsp, 20h
0x18000b6ba  xor     ecx, ecx
0x18000b6bc  xor     eax, eax
0x18000b6be  lock cmpxchg cs:g_hHelper, rcx
0x18000b6c7  jnz     short loc_18000B726
0x18000b6c9  call    GetHelperDllFullPath
0x18000b6ce  mov     rbx, rax
0x18000b6d1  test    rax, rax
0x18000b6d4  jnz     short loc_18000B6DD
0x18000b6d6  mov     eax, 80004005h
0x18000b6db  jmp     short loc_18000B728
0x18000b6dd  xor     r8d, r8d; dwFlags
0x18000b6e0  xor     edx, edx; hFile
0x18000b6e2  mov     rcx, rbx; lpLibFileName
0x18000b6e5  call    cs:__imp_LoadLibraryExW
0x18000b6eb  mov     rcx, rbx; Block
0x18000b6ee  mov     rdi, rax
0x18000b6f1  call    cs:__imp_free
0x18000b6f7  test    rdi, rdi
0x18000b6fa  jnz     short loc_18000B710
0x18000b6fc  call    cs:__imp_GetLastError
0x18000b702  test    eax, eax
0x18000b704  jle     short loc_18000B728
0x18000b706  movzx   eax, ax
0x18000b709  or      eax, 80070000h
0x18000b70e  jmp     short loc_18000B728
0x18000b710  xor     eax, eax
0x18000b712  lock cmpxchg cs:g_hHelper, rdi
0x18000b71b  jz      short loc_18000B726
0x18000b71d  mov     rcx, rdi; hLibModule
0x18000b720  call    cs:__imp_FreeLibrary
0x18000b726  xor     eax, eax
0x18000b728  mov     rbx, [rsp+28h+arg_0]
0x18000b72d  add     rsp, 20h
0x18000b731  pop     rdi
0x18000b732  retn
```
