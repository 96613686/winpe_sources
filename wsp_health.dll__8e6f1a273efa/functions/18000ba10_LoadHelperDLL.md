# LoadHelperDLL

- ea: `0x18000ba10`
- end: `0x18000baac`
- name: `LoadHelperDLL`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b8ac`

## callees

- `0x18000b928`
- `0x18000ba10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ba57`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ba57`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ba45`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ba45`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ba92`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ba92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba68`

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
0x18000ba10  mov     [rsp+arg_0], rbx
0x18000ba15  push    rdi
0x18000ba16  sub     rsp, 20h
0x18000ba1a  xor     ecx, ecx
0x18000ba1c  xor     eax, eax
0x18000ba1e  lock cmpxchg cs:g_hHelper, rcx
0x18000ba27  jnz     short loc_18000BA9E
0x18000ba29  call    GetHelperDllFullPath
0x18000ba2e  mov     rbx, rax
0x18000ba31  test    rax, rax
0x18000ba34  jnz     short loc_18000BA3D
0x18000ba36  mov     eax, 80004005h
0x18000ba3b  jmp     short loc_18000BAA0
0x18000ba3d  xor     r8d, r8d; dwFlags
0x18000ba40  xor     edx, edx; hFile
0x18000ba42  mov     rcx, rbx; lpLibFileName
0x18000ba45  call    cs:__imp_LoadLibraryExW
0x18000ba4c  nop     dword ptr [rax+rax+00h]
0x18000ba51  mov     rcx, rbx; Block
0x18000ba54  mov     rdi, rax
0x18000ba57  call    cs:__imp_free
0x18000ba5e  nop     dword ptr [rax+rax+00h]
0x18000ba63  test    rdi, rdi
0x18000ba66  jnz     short loc_18000BA82
0x18000ba68  call    cs:__imp_GetLastError
0x18000ba6f  nop     dword ptr [rax+rax+00h]
0x18000ba74  test    eax, eax
0x18000ba76  jle     short loc_18000BAA0
0x18000ba78  movzx   eax, ax
0x18000ba7b  or      eax, 80070000h
0x18000ba80  jmp     short loc_18000BAA0
0x18000ba82  xor     eax, eax
0x18000ba84  lock cmpxchg cs:g_hHelper, rdi
0x18000ba8d  jz      short loc_18000BA9E
0x18000ba8f  mov     rcx, rdi; hLibModule
0x18000ba92  call    cs:__imp_FreeLibrary
0x18000ba99  nop     dword ptr [rax+rax+00h]
0x18000ba9e  xor     eax, eax
0x18000baa0  mov     rbx, [rsp+28h+arg_0]
0x18000baa5  add     rsp, 20h
0x18000baa9  pop     rdi
0x18000baaa  retn
```
