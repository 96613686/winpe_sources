# __std_fs_open_handle

- ea: `0x18000f210`
- end: `0x18000f267`
- name: `__std_fs_open_handle`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000f35c`

## callees

- `0x18000f210`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f252`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f243`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f243`

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
0x18000f210  mov     [rsp+arg_0], rbx
0x18000f215  push    rdi
0x18000f216  sub     rsp, 40h
0x18000f21a  mov     rax, rdx
0x18000f21d  xor     edi, edi
0x18000f21f  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x18000f224  mov     rbx, rcx
0x18000f227  mov     [rsp+48h+dwFlagsAndAttributes], r9d; dwFlagsAndAttributes
0x18000f22c  mov     edx, 80h; dwDesiredAccess
0x18000f231  xor     r9d, r9d; lpSecurityAttributes
0x18000f234  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18000f23c  lea     r8d, [rdi+7]; dwShareMode
0x18000f240  mov     rcx, rax; lpFileName
0x18000f243  call    cs:__imp_CreateFileW
0x18000f249  mov     [rbx], rax
0x18000f24c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f250  jnz     short loc_18000F25A
0x18000f252  call    cs:__imp_GetLastError
0x18000f258  mov     edi, eax
0x18000f25a  mov     rbx, [rsp+48h+arg_0]
0x18000f25f  mov     eax, edi
0x18000f261  add     rsp, 40h
0x18000f265  pop     rdi
0x18000f266  retn
```
