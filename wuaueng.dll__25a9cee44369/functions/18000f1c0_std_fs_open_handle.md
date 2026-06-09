# __std_fs_open_handle

- ea: `0x18000f1c0`
- end: `0x18000f217`
- name: `__std_fs_open_handle`
- size: `87`
- prototype: `__int64 __fastcall(_QWORD *, const WCHAR *, __int64, DWORD dwFlagsAndAttributes)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000f30c`

## callees

- `0x18000f1c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f202`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f1f3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f1f3`

## pseudocode

```c
__int64 __fastcall _std_fs_open_handle(_QWORD *a1, const WCHAR *a2, __int64 a3, DWORD dwFlagsAndAttributes)
{
  unsigned int v4; // edi
  HANDLE FileW; // rax

  v4 = 0;
  FileW = CreateFileW(a2, 0x80u, 7u, 0, 3u, dwFlagsAndAttributes, 0);
  *a1 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  return v4;
}

```

## disassembly

```asm
0x18000f1c0  mov     [rsp+arg_0], rbx
0x18000f1c5  push    rdi
0x18000f1c6  sub     rsp, 40h
0x18000f1ca  mov     rax, rdx
0x18000f1cd  xor     edi, edi
0x18000f1cf  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x18000f1d4  mov     rbx, rcx
0x18000f1d7  mov     [rsp+48h+dwFlagsAndAttributes], r9d; dwFlagsAndAttributes
0x18000f1dc  mov     edx, 80h; dwDesiredAccess
0x18000f1e1  xor     r9d, r9d; lpSecurityAttributes
0x18000f1e4  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18000f1ec  lea     r8d, [rdi+7]; dwShareMode
0x18000f1f0  mov     rcx, rax; lpFileName
0x18000f1f3  call    cs:__imp_CreateFileW
0x18000f1f9  mov     [rbx], rax
0x18000f1fc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f200  jnz     short loc_18000F20A
0x18000f202  call    cs:__imp_GetLastError
0x18000f208  mov     edi, eax
0x18000f20a  mov     rbx, [rsp+48h+arg_0]
0x18000f20f  mov     eax, edi
0x18000f211  add     rsp, 40h
0x18000f215  pop     rdi
0x18000f216  retn
```
