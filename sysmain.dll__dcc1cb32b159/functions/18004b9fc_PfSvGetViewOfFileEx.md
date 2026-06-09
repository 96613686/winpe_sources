# PfSvGetViewOfFileEx

- ea: `0x18004b9fc`
- end: `0x18004bb5d`
- name: `PfSvGetViewOfFileEx`
- size: `353`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800319b8`
- `0x18004b918`
- `0x1800707c4`
- `0x18007ff64`
- `0x180089cac`
- `0x18008a24c`
- `0x180093660`
- `0x1800a9a3c`
- `0x1800adc94`

## callees

- `0x180025f6c`
- `0x18004b9fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bacd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bb3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bb53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bacd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bb3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bb53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004bad8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004bae6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004bad8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004bae6`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18004bb1e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18004bb1e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18004babf`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18004babf`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18004ba85`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18004ba85`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004ba68`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004ba68`

## string_xrefs

- `0x18004ba23`: `// Reading file: %ws...\n`

## pseudocode

```c
__int64 __fastcall PfSvGetViewOfFileEx(__int64 a1, int a2, _QWORD *a3, DWORD *a4)
{
  __int64 v4; // r14
  __int64 v7; // r14
  LPCWSTR v8; // r10
  HANDLE FileW; // rax
  void *v10; // rsi
  void *v11; // rdi
  DWORD FileSize; // ebx
  HANDLE FileMappingW; // rax
  DWORD LastError; // ebx
  LPVOID v16; // rax
  DWORD FileSizeHigh; // [rsp+78h] [rbp+10h] BYREF

  v4 = a2;
  FileSizeHigh = 0;
  PFSV_PRINTF("// Reading file: %ws...\n", a1);
  v7 = 2 * v4;
  FileW = CreateFileW(v8, *(&dwDesiredAccess + 2 * v7), *(&dwDesiredAccess + 2 * v7 + 1), 0, 3u, 0, 0);
  v10 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  v11 = 0;
  FileSize = GetFileSize(FileW, &FileSizeHigh);
  if ( FileSize == -1 && GetLastError() )
  {
LABEL_7:
    LastError = GetLastError();
    goto LABEL_8;
  }
  if ( !FileSizeHigh )
  {
    if ( a4 )
      *a4 = FileSize;
    FileMappingW = CreateFileMappingW(v10, 0, *(&dwDesiredAccess + 2 * v7 + 2), 0, 0, 0);
    v11 = FileMappingW;
    if ( FileMappingW )
    {
      v16 = MapViewOfFile(FileMappingW, *(&dwDesiredAccess + 2 * v7 + 3), 0, 0, 0);
      if ( v16 )
      {
        *a3 = v10;
        LastError = 0;
        a3[1] = v16;
        goto LABEL_9;
      }
    }
    goto LABEL_7;
  }
  LastError = 24;
LABEL_8:
  CloseHandle(v10);
  if ( v11 )
LABEL_9:
    CloseHandle(v11);
  return LastError;
}

```

## disassembly

```asm
0x18004b9fc  mov     [rsp+arg_0], rbx
0x18004ba01  mov     [rsp+arg_10], rbp
0x18004ba06  push    rsi
0x18004ba07  push    rdi
0x18004ba08  push    r13
0x18004ba0a  push    r14
0x18004ba0c  push    r15
0x18004ba0e  sub     rsp, 40h
0x18004ba12  movsxd  r14, edx
0x18004ba15  mov     r10, rcx
0x18004ba18  mov     rdx, rcx
0x18004ba1b  mov     [rsp+68h+FileSizeHigh], 0
0x18004ba23  lea     rcx, aReadingFileWs; "// Reading file: %ws...\n"
0x18004ba2a  mov     r15, r9
0x18004ba2d  mov     rbp, r8
0x18004ba30  call    PFSV_PRINTF
0x18004ba35  add     r14, r14
0x18004ba38  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18004ba41  lea     r13, dwDesiredAccess
0x18004ba48  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18004ba50  xor     r9d, r9d; lpSecurityAttributes
0x18004ba53  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18004ba5b  mov     rcx, r10; lpFileName
0x18004ba5e  mov     r8d, [r13+r14*8+4]; dwShareMode
0x18004ba63  mov     edx, [r13+r14*8+0]; dwDesiredAccess
0x18004ba68  call    cs:__imp_CreateFileW
0x18004ba6e  mov     rsi, rax
0x18004ba71  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004ba75  jz      loc_18004BB53
0x18004ba7b  lea     rdx, [rsp+68h+FileSizeHigh]; lpFileSizeHigh
0x18004ba80  mov     rcx, rax; hFile
0x18004ba83  xor     edi, edi
0x18004ba85  call    cs:__imp_GetFileSize
0x18004ba8b  mov     ebx, eax
0x18004ba8d  cmp     eax, 0FFFFFFFFh
0x18004ba90  jz      loc_18004BB3D
0x18004ba96  cmp     [rsp+68h+FileSizeHigh], edi
0x18004ba9a  jnz     loc_18004BB4C
0x18004baa0  test    r15, r15
0x18004baa3  jnz     loc_18004BB35
0x18004baa9  mov     r8d, [r13+r14*8+8]; flProtect
0x18004baae  xor     r9d, r9d; dwMaximumSizeHigh
0x18004bab1  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rdi; lpName
0x18004bab6  xor     edx, edx; lpFileMappingAttributes
0x18004bab8  mov     rcx, rsi; hFile
0x18004babb  mov     [rsp+68h+dwCreationDisposition], edi; dwMaximumSizeLow
0x18004babf  call    cs:__imp_CreateFileMappingW
0x18004bac5  mov     rdi, rax
0x18004bac8  test    rax, rax
0x18004bacb  jnz     short loc_18004BB07
0x18004bacd  call    cs:__imp_GetLastError
0x18004bad3  mov     ebx, eax
0x18004bad5  mov     rcx, rsi; hObject
0x18004bad8  call    cs:__imp_CloseHandle
0x18004bade  test    rdi, rdi
0x18004bae1  jz      short loc_18004BAEC
0x18004bae3  mov     rcx, rdi; hObject
0x18004bae6  call    cs:__imp_CloseHandle
0x18004baec  lea     r11, [rsp+68h+var_28]
0x18004baf1  mov     eax, ebx
0x18004baf3  mov     rbx, [r11+30h]
0x18004baf7  mov     rbp, [r11+40h]
0x18004bafb  mov     rsp, r11
0x18004bafe  pop     r15
0x18004bb00  pop     r14
0x18004bb02  pop     r13
0x18004bb04  pop     rdi
0x18004bb05  pop     rsi
0x18004bb06  retn
0x18004bb07  mov     edx, [r13+r14*8+0Ch]; dwDesiredAccess
0x18004bb0c  xor     r9d, r9d; dwFileOffsetLow
0x18004bb0f  xor     r8d, r8d; dwFileOffsetHigh
0x18004bb12  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18004bb1b  mov     rcx, rax; hFileMappingObject
0x18004bb1e  call    cs:__imp_MapViewOfFile
0x18004bb24  test    rax, rax
0x18004bb27  jz      short loc_18004BACD
0x18004bb29  mov     [rbp+0], rsi
0x18004bb2d  xor     ebx, ebx
0x18004bb2f  mov     [rbp+8], rax
0x18004bb33  jmp     short loc_18004BAE3
0x18004bb35  mov     [r15], ebx
0x18004bb38  jmp     loc_18004BAA9
0x18004bb3d  call    cs:__imp_GetLastError
0x18004bb43  test    eax, eax
0x18004bb45  jnz     short loc_18004BACD
0x18004bb47  jmp     loc_18004BA96
0x18004bb4c  mov     ebx, 18h
0x18004bb51  jmp     short loc_18004BAD5
0x18004bb53  call    cs:__imp_GetLastError
0x18004bb59  mov     ebx, eax
0x18004bb5b  jmp     short loc_18004BAEC
```
