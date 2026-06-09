# __std_fs_open_handle

- ea: `0x18003fec4`
- end: `0x18003ff1b`
- name: `__std_fs_open_handle`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180040158`
- `0x1800403f0`

## callees

- `0x18003fec4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ff06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ff06`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003fef7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003fef7`

## pseudocode

```c
__int64 __fastcall _std_fs_open_handle(_QWORD *a1, const WCHAR *a2, DWORD a3, DWORD dwFlagsAndAttributes)
{
  unsigned int v4; // edi
  HANDLE FileW; // rax

  v4 = 0;
  FileW = CreateFileW(a2, a3, 7u, 0, 3u, dwFlagsAndAttributes, 0);
  *a1 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  return v4;
}

```

## disassembly

```asm
0x18003fec4  mov     [rsp+arg_0], rbx
0x18003fec9  push    rdi
0x18003feca  sub     rsp, 40h
0x18003fece  mov     eax, r8d
0x18003fed1  mov     r10, rdx
0x18003fed4  xor     edi, edi
0x18003fed6  mov     rbx, rcx
0x18003fed9  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x18003fede  mov     edx, eax; dwDesiredAccess
0x18003fee0  mov     [rsp+48h+dwFlagsAndAttributes], r9d; dwFlagsAndAttributes
0x18003fee5  mov     rcx, r10; lpFileName
0x18003fee8  xor     r9d, r9d; lpSecurityAttributes
0x18003feeb  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18003fef3  lea     r8d, [rdi+7]; dwShareMode
0x18003fef7  call    cs:__imp_CreateFileW
0x18003fefd  mov     [rbx], rax
0x18003ff00  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003ff04  jnz     short loc_18003FF0E
0x18003ff06  call    cs:__imp_GetLastError
0x18003ff0c  mov     edi, eax
0x18003ff0e  mov     rbx, [rsp+48h+arg_0]
0x18003ff13  mov     eax, edi
0x18003ff15  add     rsp, 40h
0x18003ff19  pop     rdi
0x18003ff1a  retn
```
