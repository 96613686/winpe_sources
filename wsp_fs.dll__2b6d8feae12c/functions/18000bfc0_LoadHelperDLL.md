# LoadHelperDLL

- ea: `0x18000bfc0`
- end: `0x18000c043`
- name: `LoadHelperDLL`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000be7c`

## callees

- `0x18000beec`
- `0x18000bfc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c001`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c001`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000bff5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000bff5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c030`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c00c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c00c`

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
0x18000bfc0  mov     [rsp+arg_0], rbx
0x18000bfc5  push    rdi
0x18000bfc6  sub     rsp, 20h
0x18000bfca  xor     ecx, ecx
0x18000bfcc  xor     eax, eax
0x18000bfce  lock cmpxchg cs:g_hHelper, rcx
0x18000bfd7  jnz     short loc_18000C036
0x18000bfd9  call    GetHelperDllFullPath
0x18000bfde  mov     rbx, rax
0x18000bfe1  test    rax, rax
0x18000bfe4  jnz     short loc_18000BFED
0x18000bfe6  mov     eax, 80004005h
0x18000bfeb  jmp     short loc_18000C038
0x18000bfed  xor     r8d, r8d; dwFlags
0x18000bff0  xor     edx, edx; hFile
0x18000bff2  mov     rcx, rbx; lpLibFileName
0x18000bff5  call    cs:__imp_LoadLibraryExW
0x18000bffb  mov     rcx, rbx; Block
0x18000bffe  mov     rdi, rax
0x18000c001  call    cs:__imp_free
0x18000c007  test    rdi, rdi
0x18000c00a  jnz     short loc_18000C020
0x18000c00c  call    cs:__imp_GetLastError
0x18000c012  test    eax, eax
0x18000c014  jle     short loc_18000C038
0x18000c016  movzx   eax, ax
0x18000c019  or      eax, 80070000h
0x18000c01e  jmp     short loc_18000C038
0x18000c020  xor     eax, eax
0x18000c022  lock cmpxchg cs:g_hHelper, rdi
0x18000c02b  jz      short loc_18000C036
0x18000c02d  mov     rcx, rdi; hLibModule
0x18000c030  call    cs:__imp_FreeLibrary
0x18000c036  xor     eax, eax
0x18000c038  mov     rbx, [rsp+28h+arg_0]
0x18000c03d  add     rsp, 20h
0x18000c041  pop     rdi
0x18000c042  retn
```
