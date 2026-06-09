# CMappingManager::CreateMapping(void *,ulong)

- ea: `0x18002a9a8`
- end: `0x18002aa05`
- name: `?CreateMapping@CMappingManager@@QEAAJPEAXK@Z`
- size: `93`
- prototype: `int(CMappingManager *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x180010ee8`

## callees

- `0x18000b3c0`
- `0x18002a9a8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002a9e5`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002a9e5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002a9d2`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002a9d2`

## pseudocode

```c
__int64 __fastcall CMappingManager::CreateMapping(CMappingManager *this, void *a2, DWORD dwMaximumSizeLow)
{
  HANDLE FileMappingW; // rax

  FileMappingW = CreateFileMappingW(a2, 0, 4u, 0, dwMaximumSizeLow, 0);
  if ( !FileMappingW )
    return ResultFromKnownLastError();
  *(_QWORD *)this = FileMappingW;
  *((_QWORD *)this + 1) = GetFileSize(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x18002a9a8  mov     [rsp+arg_0], rbx
0x18002a9ad  push    rdi
0x18002a9ae  sub     rsp, 30h
0x18002a9b2  mov     rdi, rdx
0x18002a9b5  mov     [rsp+38h+lpName], 0; lpName
0x18002a9be  xor     r9d, r9d; dwMaximumSizeHigh
0x18002a9c1  mov     [rsp+38h+dwMaximumSizeLow], r8d; dwMaximumSizeLow
0x18002a9c6  mov     rbx, rcx
0x18002a9c9  xor     edx, edx; lpFileMappingAttributes
0x18002a9cb  mov     rcx, rdi; hFile
0x18002a9ce  lea     r8d, [r9+4]; flProtect
0x18002a9d2  call    cs:__imp_CreateFileMappingW
0x18002a9d8  test    rax, rax
0x18002a9db  jz      short loc_18002A9FE
0x18002a9dd  xor     edx, edx; lpFileSizeHigh
0x18002a9df  mov     [rbx], rax
0x18002a9e2  mov     rcx, rdi; hFile
0x18002a9e5  call    cs:__imp_GetFileSize
0x18002a9eb  mov     eax, eax
0x18002a9ed  mov     [rbx+8], rax
0x18002a9f1  xor     eax, eax
0x18002a9f3  mov     rbx, [rsp+38h+arg_0]
0x18002a9f8  add     rsp, 30h
0x18002a9fc  pop     rdi
0x18002a9fd  retn
0x18002a9fe  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002aa03  jmp     short loc_18002A9F3
```
