# DelayLoadCC

- ea: `0x180027068`
- end: `0x1800270b2`
- name: `DelayLoadCC`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026f04`

## callees

- `0x180027010`
- `0x180027068`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027096`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027096`

## string_xrefs

- `0x180027089`: `comctl32.dll`

## pseudocode

```c
__int64 DelayLoadCC()
{
  __int64 result; // rax

  if ( g_hinstCC )
    return 1;
  g_hinstCC = (__int64)SHFusionLoadLibrary();
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
0x180027068  sub     rsp, 28h
0x18002706c  cmp     cs:g_hinstCC, 0
0x180027074  jnz     short loc_1800270A8
0x180027076  call    SHFusionLoadLibrary
0x18002707b  mov     cs:g_hinstCC, rax
0x180027082  test    rax, rax
0x180027085  jnz     short loc_1800270A8
0x180027087  xor     edx, edx; hFile
0x180027089  lea     rcx, aComctl32Dll_0; "comctl32.dll"
0x180027090  mov     r8d, 4000h; dwFlags
0x180027096  call    cs:__imp_LoadLibraryExW
0x18002709c  mov     cs:g_hinstCC, rax
0x1800270a3  test    rax, rax
0x1800270a6  jz      short loc_1800270AD
0x1800270a8  mov     eax, 1
0x1800270ad  add     rsp, 28h
0x1800270b1  retn
```
