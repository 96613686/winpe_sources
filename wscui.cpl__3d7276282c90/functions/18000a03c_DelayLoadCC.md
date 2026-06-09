# DelayLoadCC

- ea: `0x18000a03c`
- end: `0x18000a086`
- name: `DelayLoadCC`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a150`
- `0x18000a220`

## callees

- `0x18000a03c`
- `0x18000a338`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a06a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a06a`

## string_xrefs

- `0x18000a05d`: `comctl32.dll`

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
0x18000a03c  sub     rsp, 28h
0x18000a040  cmp     cs:g_hinstCC, 0
0x18000a048  jnz     short loc_18000A07C
0x18000a04a  call    SHFusionLoadLibrary
0x18000a04f  mov     cs:g_hinstCC, rax
0x18000a056  test    rax, rax
0x18000a059  jnz     short loc_18000A07C
0x18000a05b  xor     edx, edx; hFile
0x18000a05d  lea     rcx, aComctl32Dll_0; "comctl32.dll"
0x18000a064  mov     r8d, 4000h; dwFlags
0x18000a06a  call    cs:__imp_LoadLibraryExW
0x18000a070  mov     cs:g_hinstCC, rax
0x18000a077  test    rax, rax
0x18000a07a  jz      short loc_18000A081
0x18000a07c  mov     eax, 1
0x18000a081  add     rsp, 28h
0x18000a085  retn
```
