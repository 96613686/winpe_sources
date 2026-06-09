# WxDeleteFileOrDirectory(ushort const *,ulong)

- ea: `0x1800c7b10`
- end: `0x1800c7c04`
- name: `?WxDeleteFileOrDirectory@@YAJPEBGK@Z`
- size: `244`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180094814`
- `0x1800c7a84`

## callees

- `0x1800c7b10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7b44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7b8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7b44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7b8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c7bef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c7bef`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c7bd3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c7bd3`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800c7b3a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800c7b3a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800c7be4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800c7be4`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800c7b81`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800c7b81`

## pseudocode

```c
__int64 __fastcall WxDeleteFileOrDirectory(LPCWSTR lpFileName, int a2)
{
  int v2; // ebx
  DWORD v4; // edx
  signed int LastError; // ecx
  bool v6; // sf
  BOOL v7; // eax
  DWORD v8; // eax
  HANDLE FileW; // rax

  v2 = a2 & 0x10;
  if ( (a2 & 7) == 0 )
    goto LABEL_10;
  v4 = a2 & 0xFFFFFFF8;
  if ( !v4 )
    v4 = 128;
  if ( SetFileAttributesW(lpFileName, v4) )
    goto LABEL_10;
  LastError = GetLastError();
  if ( ((LastError - 2) & 0xFFFFFFFC) == 0 && LastError != 4 )
    return 0;
  v6 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = LastError < 0;
  }
  if ( !v6 )
  {
LABEL_10:
    if ( v2 )
      v7 = RemoveDirectoryW(lpFileName);
    else
      v7 = DeleteFileW(lpFileName);
    if ( !v7 )
    {
      v8 = GetLastError();
      if ( ((v8 - 2) & 0xFFFFFFFC) != 0 || v8 == 4 )
      {
        FileW = CreateFileW(lpFileName, 0x13019Fu, 7u, 0, 3u, v2 != 0 ? 100663296 : 0x4000000, 0);
        if ( FileW == (HANDLE)-1LL )
          return 1;
        CloseHandle(FileW);
      }
    }
    return 0;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800c7b10  mov     [rsp+arg_10], rbx
0x1800c7b15  push    rdi
0x1800c7b16  sub     rsp, 50h
0x1800c7b1a  mov     ebx, edx
0x1800c7b1c  mov     [rsp+58h+var_14], 0
0x1800c7b24  and     ebx, 10h
0x1800c7b27  mov     rdi, rcx
0x1800c7b2a  test    dl, 7
0x1800c7b2d  jz      short loc_1800C7B7A
0x1800c7b2f  and     edx, 0FFFFFFF8h
0x1800c7b32  mov     eax, 80h
0x1800c7b37  cmovz   edx, eax; dwFileAttributes
0x1800c7b3a  call    cs:__imp_SetFileAttributesW
0x1800c7b40  test    eax, eax
0x1800c7b42  jnz     short loc_1800C7B7A
0x1800c7b44  call    cs:__imp_GetLastError
0x1800c7b4a  mov     ecx, eax
0x1800c7b4c  add     eax, 0FFFFFFFEh
0x1800c7b4f  test    eax, 0FFFFFFFCh
0x1800c7b54  jnz     short loc_1800C7B5F
0x1800c7b56  cmp     ecx, 4
0x1800c7b59  jnz     loc_1800C7BF5
0x1800c7b5f  test    ecx, ecx
0x1800c7b61  jle     short loc_1800C7B6E
0x1800c7b63  movzx   ecx, cx
0x1800c7b66  or      ecx, 80070000h
0x1800c7b6c  test    ecx, ecx
0x1800c7b6e  jns     short loc_1800C7B7A
0x1800c7b70  mov     [rsp+58h+var_14], 16Eh
0x1800c7b78  jmp     short loc_1800C7BF7
0x1800c7b7a  mov     rcx, rdi; lpFileName
0x1800c7b7d  test    ebx, ebx
0x1800c7b7f  jz      short loc_1800C7BE4
0x1800c7b81  call    cs:__imp_RemoveDirectoryW
0x1800c7b87  test    eax, eax
0x1800c7b89  jnz     short loc_1800C7BF5
0x1800c7b8b  call    cs:__imp_GetLastError
0x1800c7b91  lea     ecx, [rax-2]
0x1800c7b94  test    ecx, 0FFFFFFFCh
0x1800c7b9a  jnz     short loc_1800C7BA1
0x1800c7b9c  cmp     eax, 4
0x1800c7b9f  jnz     short loc_1800C7BF5
0x1800c7ba1  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x1800c7baa  neg     ebx
0x1800c7bac  mov     edx, 13019Fh; dwDesiredAccess
0x1800c7bb1  mov     rcx, rdi; lpFileName
0x1800c7bb4  sbb     eax, eax
0x1800c7bb6  xor     r9d, r9d; lpSecurityAttributes
0x1800c7bb9  and     eax, 2000000h
0x1800c7bbe  add     eax, 4000000h
0x1800c7bc3  mov     [rsp+58h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1800c7bc7  lea     r8d, [r9+7]; dwShareMode
0x1800c7bcb  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x1800c7bd3  call    cs:__imp_CreateFileW
0x1800c7bd9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c7bdd  jnz     short loc_1800C7BEC
0x1800c7bdf  lea     ecx, [rax+2]
0x1800c7be2  jmp     short loc_1800C7BF7
0x1800c7be4  call    cs:__imp_DeleteFileW
0x1800c7bea  jmp     short loc_1800C7B87
0x1800c7bec  mov     rcx, rax; hObject
0x1800c7bef  call    cs:__imp_CloseHandle
0x1800c7bf5  xor     ecx, ecx
0x1800c7bf7  mov     rbx, [rsp+58h+arg_10]
0x1800c7bfc  mov     eax, ecx
0x1800c7bfe  add     rsp, 50h
0x1800c7c02  pop     rdi
0x1800c7c03  retn
```
