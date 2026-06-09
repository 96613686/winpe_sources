# _GetProcFromComDlg

- ea: `0x180055504`
- end: `0x180055583`
- name: `_GetProcFromComDlg`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180054df4`
- `0x1800551a0`

## callees

- `0x180054d8c`
- `0x180055504`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180055568`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180055568`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180055547`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180055547`

## string_xrefs

- `0x180055520`: `comdlg32.dll`
- `0x18005553a`: `comdlg32.dll`

## pseudocode

```c
HMODULE __fastcall GetProcFromComDlg(HMODULE *a1, const CHAR *a2)
{
  HMODULE result; // rax

  result = g_hinstCD;
  if ( g_hinstCD )
    goto LABEL_5;
  result = (HMODULE)SHFusionLoadLibrary(L"comdlg32.dll");
  g_hinstCD = result;
  if ( !result )
  {
    result = LoadLibraryExW(L"comdlg32.dll", 0, 0x4000u);
    g_hinstCD = result;
  }
  if ( result )
LABEL_5:
    result = (HMODULE)GetProcAddress(result, a2);
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x180055504  mov     [rsp+arg_0], rbx
0x180055509  push    rdi
0x18005550a  sub     rsp, 20h
0x18005550e  mov     rax, cs:g_hinstCD
0x180055515  mov     rdi, rdx
0x180055518  mov     rbx, rcx
0x18005551b  test    rax, rax
0x18005551e  jnz     short loc_180055562
0x180055520  lea     rcx, aComdlg32Dll; "comdlg32.dll"
0x180055527  call    SHFusionLoadLibrary
0x18005552c  mov     cs:g_hinstCD, rax
0x180055533  test    rax, rax
0x180055536  jnz     short loc_18005555A
0x180055538  xor     edx, edx; hFile
0x18005553a  lea     rcx, aComdlg32Dll; "comdlg32.dll"
0x180055541  mov     r8d, 4000h; dwFlags
0x180055547  call    cs:__imp_LoadLibraryExW
0x18005554e  nop     dword ptr [rax+rax+00h]
0x180055553  mov     cs:g_hinstCD, rax
0x18005555a  mov     rcx, rax
0x18005555d  test    rax, rax
0x180055560  jz      short loc_180055574
0x180055562  mov     rdx, rdi; lpProcName
0x180055565  mov     rcx, rax; hModule
0x180055568  call    cs:__imp_GetProcAddress
0x18005556f  nop     dword ptr [rax+rax+00h]
0x180055574  mov     [rbx], rax
0x180055577  mov     rbx, [rsp+28h+arg_0]
0x18005557c  add     rsp, 20h
0x180055580  pop     rdi
0x180055581  retn
```
