# _GetProcFromComCtl32

- ea: `0x180002db0`
- end: `0x180002e1b`
- name: `_GetProcFromComCtl32`
- size: `107`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002a00`
- `0x180003020`
- `0x180003c10`

## callees

- `0x180002c30`
- `0x180002db0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002e09`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002e09`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002de0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002de0`

## string_xrefs

- `0x180002dd3`: `comctl32.dll`

## pseudocode

```c
HMODULE GetProcFromComCtl32()
{
  HMODULE result; // rax

  result = g_hinstCC;
  if ( g_hinstCC )
    goto LABEL_6;
  result = (HMODULE)SHFusionLoadLibrary();
  g_hinstCC = result;
  if ( !result )
  {
    result = LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
    g_hinstCC = result;
  }
  if ( result )
  {
LABEL_6:
    result = (HMODULE)GetProcAddress(result, (LPCSTR)0xEC);
    qword_1800384A8 = (__int64)result;
  }
  else
  {
    qword_1800384A8 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002db0  sub     rsp, 28h
0x180002db4  mov     rax, cs:g_hinstCC
0x180002dbb  test    rax, rax
0x180002dbe  jnz     short loc_180002E01
0x180002dc0  call    SHFusionLoadLibrary
0x180002dc5  mov     cs:g_hinstCC, rax
0x180002dcc  test    rax, rax
0x180002dcf  jnz     short loc_180002DED
0x180002dd1  xor     edx, edx; hFile
0x180002dd3  lea     rcx, LibFileName; "comctl32.dll"
0x180002dda  mov     r8d, 4000h; dwFlags
0x180002de0  call    cs:__imp_LoadLibraryExW
0x180002de6  mov     cs:g_hinstCC, rax
0x180002ded  mov     rcx, rax
0x180002df0  test    rax, rax
0x180002df3  jnz     short loc_180002E01
0x180002df5  mov     cs:qword_1800384A8, rax
0x180002dfc  add     rsp, 28h
0x180002e00  retn
0x180002e01  mov     edx, 0ECh; lpProcName
0x180002e06  mov     rcx, rax; hModule
0x180002e09  call    cs:__imp_GetProcAddress
0x180002e0f  mov     cs:qword_1800384A8, rax
0x180002e16  add     rsp, 28h
0x180002e1a  retn
```
