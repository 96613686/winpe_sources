# DelayLoadCC

- ea: `0x180016524`
- end: `0x18001656e`
- name: `DelayLoadCC`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800161bc`
- `0x180016650`

## callees

- `0x1800162c8`
- `0x180016524`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180016552`
- `KERNEL32!LoadLibraryExW` at `0x180016552`

## string_xrefs

- `0x180016545`: `comctl32.dll`

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
0x180016524  sub     rsp, 28h
0x180016528  cmp     cs:g_hinstCC, 0
0x180016530  jnz     short loc_180016564
0x180016532  call    SHFusionLoadLibrary
0x180016537  mov     cs:g_hinstCC, rax
0x18001653e  test    rax, rax
0x180016541  jnz     short loc_180016564
0x180016543  xor     edx, edx; hFile
0x180016545  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18001654c  mov     r8d, 4000h; dwFlags
0x180016552  call    cs:__imp_LoadLibraryExW
0x180016558  mov     cs:g_hinstCC, rax
0x18001655f  test    rax, rax
0x180016562  jz      short loc_180016569
0x180016564  mov     eax, 1
0x180016569  add     rsp, 28h
0x18001656d  retn
```
