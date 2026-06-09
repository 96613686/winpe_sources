# LoadHelperDLL

- ea: `0x18000c2e0`
- end: `0x18000c37c`
- name: `LoadHelperDLL`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c17c`

## callees

- `0x18000c1f8`
- `0x18000c2e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c327`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c327`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c315`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c315`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c362`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c338`

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
0x18000c2e0  mov     [rsp+arg_0], rbx
0x18000c2e5  push    rdi
0x18000c2e6  sub     rsp, 20h
0x18000c2ea  xor     ecx, ecx
0x18000c2ec  xor     eax, eax
0x18000c2ee  lock cmpxchg cs:g_hHelper, rcx
0x18000c2f7  jnz     short loc_18000C36E
0x18000c2f9  call    GetHelperDllFullPath
0x18000c2fe  mov     rbx, rax
0x18000c301  test    rax, rax
0x18000c304  jnz     short loc_18000C30D
0x18000c306  mov     eax, 80004005h
0x18000c30b  jmp     short loc_18000C370
0x18000c30d  xor     r8d, r8d; dwFlags
0x18000c310  xor     edx, edx; hFile
0x18000c312  mov     rcx, rbx; lpLibFileName
0x18000c315  call    cs:__imp_LoadLibraryExW
0x18000c31c  nop     dword ptr [rax+rax+00h]
0x18000c321  mov     rcx, rbx; Block
0x18000c324  mov     rdi, rax
0x18000c327  call    cs:__imp_free
0x18000c32e  nop     dword ptr [rax+rax+00h]
0x18000c333  test    rdi, rdi
0x18000c336  jnz     short loc_18000C352
0x18000c338  call    cs:__imp_GetLastError
0x18000c33f  nop     dword ptr [rax+rax+00h]
0x18000c344  test    eax, eax
0x18000c346  jle     short loc_18000C370
0x18000c348  movzx   eax, ax
0x18000c34b  or      eax, 80070000h
0x18000c350  jmp     short loc_18000C370
0x18000c352  xor     eax, eax
0x18000c354  lock cmpxchg cs:g_hHelper, rdi
0x18000c35d  jz      short loc_18000C36E
0x18000c35f  mov     rcx, rdi; hLibModule
0x18000c362  call    cs:__imp_FreeLibrary
0x18000c369  nop     dword ptr [rax+rax+00h]
0x18000c36e  xor     eax, eax
0x18000c370  mov     rbx, [rsp+28h+arg_0]
0x18000c375  add     rsp, 20h
0x18000c379  pop     rdi
0x18000c37a  retn
```
