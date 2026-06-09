# DelayLoadCC

- ea: `0x180006880`
- end: `0x1800068cf`
- name: `DelayLoadCC`
- size: `79`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002b60`
- `0x180004bc0`
- `0x1800056b4`
- `0x1800057fc`
- `0x1800268b4`

## callees

- `0x180002c30`
- `0x180006880`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800068ae`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800068ae`

## string_xrefs

- `0x1800068a1`: `comctl32.dll`

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
0x180006880  sub     rsp, 28h
0x180006884  cmp     cs:g_hinstCC, 0
0x18000688c  jnz     short loc_1800068C5
0x18000688e  call    SHFusionLoadLibrary
0x180006893  mov     cs:g_hinstCC, rax
0x18000689a  test    rax, rax
0x18000689d  jnz     short loc_1800068C5
0x18000689f  xor     edx, edx; hFile
0x1800068a1  lea     rcx, LibFileName; "comctl32.dll"
0x1800068a8  mov     r8d, 4000h; dwFlags
0x1800068ae  call    cs:__imp_LoadLibraryExW
0x1800068b4  mov     cs:g_hinstCC, rax
0x1800068bb  test    rax, rax
0x1800068be  jnz     short loc_1800068C5
0x1800068c0  add     rsp, 28h
0x1800068c4  retn
0x1800068c5  mov     eax, 1
0x1800068ca  add     rsp, 28h
0x1800068ce  retn
```
