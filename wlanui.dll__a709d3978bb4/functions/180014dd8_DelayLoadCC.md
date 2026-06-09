# DelayLoadCC

- ea: `0x180014dd8`
- end: `0x180014e22`
- name: `DelayLoadCC`
- size: `74`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007448`
- `0x180014b70`
- `0x180014fd0`

## callees

- `0x180014c7c`
- `0x180014dd8`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180014e06`
- `KERNEL32!LoadLibraryExW` at `0x180014e06`

## string_xrefs

- `0x180014df9`: `comctl32.dll`

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
0x180014dd8  sub     rsp, 28h
0x180014ddc  cmp     cs:g_hinstCC, 0
0x180014de4  jnz     short loc_180014E18
0x180014de6  call    SHFusionLoadLibrary
0x180014deb  mov     cs:g_hinstCC, rax
0x180014df2  test    rax, rax
0x180014df5  jnz     short loc_180014E18
0x180014df7  xor     edx, edx; hFile
0x180014df9  lea     rcx, aComctl32Dll; "comctl32.dll"
0x180014e00  mov     r8d, 4000h; dwFlags
0x180014e06  call    cs:__imp_LoadLibraryExW
0x180014e0c  mov     cs:g_hinstCC, rax
0x180014e13  test    rax, rax
0x180014e16  jz      short loc_180014E1D
0x180014e18  mov     eax, 1
0x180014e1d  add     rsp, 28h
0x180014e21  retn
```
