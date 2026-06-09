# DelayLoadCC

- ea: `0x1800361f4`
- end: `0x18003623e`
- name: `DelayLoadCC`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180035e90`
- `0x180036344`

## callees

- `0x180035fa8`
- `0x1800361f4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180036222`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180036222`

## string_xrefs

- `0x180036215`: `comctl32.dll`

## pseudocode

```c
__int64 DelayLoadCC()
{
  __int64 result; // rax

  if ( g_hinstCC )
    return 1;
  g_hinstCC = SHFusionLoadLibrary();
  if ( g_hinstCC )
    return 1;
  result = (__int64)LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
  g_hinstCC = (HMODULE)result;
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x1800361f4  sub     rsp, 28h
0x1800361f8  cmp     cs:g_hinstCC, 0
0x180036200  jnz     short loc_180036234
0x180036202  call    SHFusionLoadLibrary
0x180036207  mov     cs:g_hinstCC, rax
0x18003620e  test    rax, rax
0x180036211  jnz     short loc_180036234
0x180036213  xor     edx, edx; hFile
0x180036215  lea     rcx, aComctl32Dll_0; "comctl32.dll"
0x18003621c  mov     r8d, 4000h; dwFlags
0x180036222  call    cs:__imp_LoadLibraryExW
0x180036228  mov     cs:g_hinstCC, rax
0x18003622f  test    rax, rax
0x180036232  jz      short loc_180036239
0x180036234  mov     eax, 1
0x180036239  add     rsp, 28h
0x18003623d  retn
```
