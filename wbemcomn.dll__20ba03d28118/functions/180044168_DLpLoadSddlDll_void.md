# DLpLoadSddlDll(void)

- ea: `0x180044168`
- end: `0x1800441c7`
- name: `?DLpLoadSddlDll@@YAKXZ`
- size: `95`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003eff4`
- `0x180044070`
- `0x1800440ec`

## callees

- `0x180044168`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800441b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800441b7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180044186`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800441a5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180044186`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800441a5`

## string_xrefs

- `0x18004419e`: `advapi32.dll`
- `0x18004417f`: `api-ms-win-security-sddl-L1-1-0.dll`

## pseudocode

```c
__int64 DLpLoadSddlDll(void)
{
  unsigned int v0; // ebx

  v0 = 0;
  if ( !g_hInstSddlDLL )
  {
    g_hInstSddlDLL = LoadLibraryExW(L"api-ms-win-security-sddl-L1-1-0.dll", 0, 8u);
    if ( !g_hInstSddlDLL )
    {
      g_hInstSddlDLL = LoadLibraryExW(L"advapi32.dll", 0, 8u);
      if ( !g_hInstSddlDLL )
        return GetLastError();
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180044168  push    rbx
0x18004416a  sub     rsp, 20h
0x18004416e  xor     ebx, ebx
0x180044170  cmp     cs:?g_hInstSddlDLL@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInstSddlDLL
0x180044177  jnz     short loc_1800441BF
0x180044179  xor     edx, edx; hFile
0x18004417b  lea     r8d, [rbx+8]; dwFlags
0x18004417f  lea     rcx, aApiMsWinSecuri_1; "api-ms-win-security-sddl-L1-1-0.dll"
0x180044186  call    cs:__imp_LoadLibraryExW
0x18004418c  mov     cs:?g_hInstSddlDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstSddlDLL
0x180044193  test    rax, rax
0x180044196  jnz     short loc_1800441BF
0x180044198  xor     edx, edx; hFile
0x18004419a  lea     r8d, [rbx+8]; dwFlags
0x18004419e  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1800441a5  call    cs:__imp_LoadLibraryExW
0x1800441ab  mov     cs:?g_hInstSddlDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstSddlDLL
0x1800441b2  test    rax, rax
0x1800441b5  jnz     short loc_1800441BF
0x1800441b7  call    cs:__imp_GetLastError
0x1800441bd  mov     ebx, eax
0x1800441bf  mov     eax, ebx
0x1800441c1  add     rsp, 20h
0x1800441c5  pop     rbx
0x1800441c6  retn
```
