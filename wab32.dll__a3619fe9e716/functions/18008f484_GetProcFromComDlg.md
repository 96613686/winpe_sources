# _GetProcFromComDlg

- ea: `0x18008f484`
- end: `0x18008f4f6`
- name: `_GetProcFromComDlg`
- size: `114`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000af30`
- `0x18004c67c`
- `0x18008f0ec`

## callees

- `0x18008efe0`
- `0x18008f484`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18008f4c7`
- `KERNEL32!LoadLibraryExW` at `0x18008f4c7`
- `KERNEL32!GetProcAddress` at `0x18008f4e2`
- `KERNEL32!GetProcAddress` at `0x18008f4e2`

## string_xrefs

- `0x18008f4a0`: `comdlg32.dll`
- `0x18008f4ba`: `comdlg32.dll`

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
0x18008f484  mov     [rsp+arg_0], rbx
0x18008f489  push    rdi
0x18008f48a  sub     rsp, 20h
0x18008f48e  mov     rax, cs:g_hinstCD
0x18008f495  mov     rdi, rdx
0x18008f498  mov     rbx, rcx
0x18008f49b  test    rax, rax
0x18008f49e  jnz     short loc_18008F4DC
0x18008f4a0  lea     rcx, aComdlg32Dll; "comdlg32.dll"
0x18008f4a7  call    SHFusionLoadLibrary
0x18008f4ac  mov     cs:g_hinstCD, rax
0x18008f4b3  test    rax, rax
0x18008f4b6  jnz     short loc_18008F4D4
0x18008f4b8  xor     edx, edx; hFile
0x18008f4ba  lea     rcx, aComdlg32Dll; "comdlg32.dll"
0x18008f4c1  mov     r8d, 4000h; dwFlags
0x18008f4c7  call    cs:__imp_LoadLibraryExW
0x18008f4cd  mov     cs:g_hinstCD, rax
0x18008f4d4  mov     rcx, rax
0x18008f4d7  test    rax, rax
0x18008f4da  jz      short loc_18008F4E8
0x18008f4dc  mov     rdx, rdi; lpProcName
0x18008f4df  mov     rcx, rax; hModule
0x18008f4e2  call    cs:__imp_GetProcAddress
0x18008f4e8  mov     [rbx], rax
0x18008f4eb  mov     rbx, [rsp+28h+arg_0]
0x18008f4f0  add     rsp, 20h
0x18008f4f4  pop     rdi
0x18008f4f5  retn
```
