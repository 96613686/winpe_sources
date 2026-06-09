# DelayLoadCC

- ea: `0x180004d20`
- end: `0x180004d6a`
- name: `DelayLoadCC`
- size: `74`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004bb4`

## callees

- `0x180004cc0`
- `0x180004d20`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180004d4e`
- `KERNEL32!LoadLibraryExW` at `0x180004d4e`

## string_xrefs

- `0x180004d41`: `comctl32.dll`

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
  g_hinstCC = result;
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180004d20  sub     rsp, 28h
0x180004d24  cmp     cs:g_hinstCC, 0
0x180004d2c  jnz     short loc_180004D60
0x180004d2e  call    SHFusionLoadLibrary
0x180004d33  mov     cs:g_hinstCC, rax
0x180004d3a  test    rax, rax
0x180004d3d  jnz     short loc_180004D60
0x180004d3f  xor     edx, edx; hFile
0x180004d41  lea     rcx, aComctl32Dll; "comctl32.dll"
0x180004d48  mov     r8d, 4000h; dwFlags
0x180004d4e  call    cs:__imp_LoadLibraryExW
0x180004d54  mov     cs:g_hinstCC, rax
0x180004d5b  test    rax, rax
0x180004d5e  jz      short loc_180004D65
0x180004d60  mov     eax, 1
0x180004d65  add     rsp, 28h
0x180004d69  retn
```
