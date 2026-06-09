# __std_fs_open_handle

- ea: `0x180079ebc`
- end: `0x180079f13`
- name: `__std_fs_open_handle`
- size: `87`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180064774`
- `0x18007a150`
- `0x18007a3e8`

## callees

- `0x180079ebc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079efe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079efe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180079eef`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180079eef`

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
0x180079ebc  mov     [rsp+arg_0], rbx
0x180079ec1  push    rdi
0x180079ec2  sub     rsp, 40h
0x180079ec6  mov     eax, r8d
0x180079ec9  mov     r10, rdx
0x180079ecc  xor     edi, edi
0x180079ece  mov     rbx, rcx
0x180079ed1  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x180079ed6  mov     edx, eax; dwDesiredAccess
0x180079ed8  mov     [rsp+48h+dwFlagsAndAttributes], r9d; dwFlagsAndAttributes
0x180079edd  mov     rcx, r10; lpFileName
0x180079ee0  xor     r9d, r9d; lpSecurityAttributes
0x180079ee3  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180079eeb  lea     r8d, [rdi+7]; dwShareMode
0x180079eef  call    cs:__imp_CreateFileW
0x180079ef5  mov     [rbx], rax
0x180079ef8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180079efc  jnz     short loc_180079F06
0x180079efe  call    cs:__imp_GetLastError
0x180079f04  mov     edi, eax
0x180079f06  mov     rbx, [rsp+48h+arg_0]
0x180079f0b  mov     eax, edi
0x180079f0d  add     rsp, 40h
0x180079f11  pop     rdi
0x180079f12  retn
```
