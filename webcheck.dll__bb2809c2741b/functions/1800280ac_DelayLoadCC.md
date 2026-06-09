# DelayLoadCC

- ea: `0x1800280ac`
- end: `0x1800280f6`
- name: `DelayLoadCC`
- size: `74`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c10c`
- `0x180027e00`
- `0x180027eb4`
- `0x180028228`

## callees

- `0x180027fc0`
- `0x1800280ac`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800280da`
- `KERNEL32!LoadLibraryExW` at `0x1800280da`

## string_xrefs

- `0x1800280cd`: `comctl32.dll`

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
0x1800280ac  sub     rsp, 28h
0x1800280b0  cmp     cs:g_hinstCC, 0
0x1800280b8  jnz     short loc_1800280EC
0x1800280ba  call    SHFusionLoadLibrary
0x1800280bf  mov     cs:g_hinstCC, rax
0x1800280c6  test    rax, rax
0x1800280c9  jnz     short loc_1800280EC
0x1800280cb  xor     edx, edx; hFile
0x1800280cd  lea     rcx, aComctl32Dll; "comctl32.dll"
0x1800280d4  mov     r8d, 4000h; dwFlags
0x1800280da  call    cs:__imp_LoadLibraryExW
0x1800280e0  mov     cs:g_hinstCC, rax
0x1800280e7  test    rax, rax
0x1800280ea  jz      short loc_1800280F1
0x1800280ec  mov     eax, 1
0x1800280f1  add     rsp, 28h
0x1800280f5  retn
```
