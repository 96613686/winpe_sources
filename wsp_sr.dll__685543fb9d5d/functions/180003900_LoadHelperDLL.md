# LoadHelperDLL

- ea: `0x180003900`
- end: `0x18000399c`
- name: `LoadHelperDLL`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000379c`

## callees

- `0x180003818`
- `0x180003900`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003947`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003958`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003982`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003982`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003935`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003935`

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
0x180003900  mov     [rsp+arg_0], rbx
0x180003905  push    rdi
0x180003906  sub     rsp, 20h
0x18000390a  xor     ecx, ecx
0x18000390c  xor     eax, eax
0x18000390e  lock cmpxchg cs:g_hHelper, rcx
0x180003917  jnz     short loc_18000398E
0x180003919  call    GetHelperDllFullPath
0x18000391e  mov     rbx, rax
0x180003921  test    rax, rax
0x180003924  jnz     short loc_18000392D
0x180003926  mov     eax, 80004005h
0x18000392b  jmp     short loc_180003990
0x18000392d  xor     r8d, r8d; dwFlags
0x180003930  xor     edx, edx; hFile
0x180003932  mov     rcx, rbx; lpLibFileName
0x180003935  call    cs:__imp_LoadLibraryExW
0x18000393c  nop     dword ptr [rax+rax+00h]
0x180003941  mov     rcx, rbx; Block
0x180003944  mov     rdi, rax
0x180003947  call    cs:__imp_free
0x18000394e  nop     dword ptr [rax+rax+00h]
0x180003953  test    rdi, rdi
0x180003956  jnz     short loc_180003972
0x180003958  call    cs:__imp_GetLastError
0x18000395f  nop     dword ptr [rax+rax+00h]
0x180003964  test    eax, eax
0x180003966  jle     short loc_180003990
0x180003968  movzx   eax, ax
0x18000396b  or      eax, 80070000h
0x180003970  jmp     short loc_180003990
0x180003972  xor     eax, eax
0x180003974  lock cmpxchg cs:g_hHelper, rdi
0x18000397d  jz      short loc_18000398E
0x18000397f  mov     rcx, rdi; hLibModule
0x180003982  call    cs:__imp_FreeLibrary
0x180003989  nop     dword ptr [rax+rax+00h]
0x18000398e  xor     eax, eax
0x180003990  mov     rbx, [rsp+28h+arg_0]
0x180003995  add     rsp, 20h
0x180003999  pop     rdi
0x18000399a  retn
```
