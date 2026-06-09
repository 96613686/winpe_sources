# DelayLoadCC

- ea: `0x180030044`
- end: `0x18003008e`
- name: `DelayLoadCC`
- size: `74`
- prototype: `__int64()`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800029d0`
- `0x18001ec6c`
- `0x18002f9c8`
- `0x18002fa78`
- `0x18002faf8`

## callees

- `0x18002fc04`
- `0x180030044`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180030072`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180030072`

## string_xrefs

- `0x180030065`: `comctl32.dll`

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
0x180030044  sub     rsp, 28h
0x180030048  cmp     cs:g_hinstCC, 0
0x180030050  jnz     short loc_180030084
0x180030052  call    SHFusionLoadLibrary
0x180030057  mov     cs:g_hinstCC, rax
0x18003005e  test    rax, rax
0x180030061  jnz     short loc_180030084
0x180030063  xor     edx, edx; hFile
0x180030065  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18003006c  mov     r8d, 4000h; dwFlags
0x180030072  call    cs:__imp_LoadLibraryExW
0x180030078  mov     cs:g_hinstCC, rax
0x18003007f  test    rax, rax
0x180030082  jz      short loc_180030089
0x180030084  mov     eax, 1
0x180030089  add     rsp, 28h
0x18003008d  retn
```
