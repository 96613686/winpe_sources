# XmRWGetViewOfFileEx(ushort *,_XMRW_OPEN_CONTEXT *)

- ea: `0x140037e2c`
- end: `0x140037f93`
- name: `?XmRWGetViewOfFileEx@@YAKPEAGPEAU_XMRW_OPEN_CONTEXT@@@Z`
- size: `359`
- prototype: `unsigned int __fastcall(unsigned __int16 *, struct _XMRW_OPEN_CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140037f9c`

## callees

- `0x140037e2c`
- `0x1400400be`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037e72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037f2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037e72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037f2b`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x140037f10`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x140037f10`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140037e60`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140037e60`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x140037e90`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x140037e90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140037f70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140037f7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140037f70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140037f7e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x140037f4b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x140037f4b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x140037f22`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x140037f22`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140037ed5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140037ed5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140037ef8`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140037ef8`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140037f5b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140037f5b`

## pseudocode

```c
__int64 __fastcall XmRWGetViewOfFileEx(unsigned __int16 *a1, struct _XMRW_OPEN_CONTEXT *a2)
{
  void *v2; // rsi
  HANDLE FileW; // rax
  void *v5; // rbp
  char v6; // r14
  DWORD LastError; // ebx
  DWORD FileSize; // ebx
  HANDLE FileMappingW; // rax
  LPVOID v10; // rax
  HGLOBAL v11; // rax
  void *v12; // r15
  DWORD FileSizeHigh; // [rsp+88h] [rbp+10h] BYREF

  v2 = 0;
  FileSizeHigh = 0;
  FileW = CreateFileW(a1, 0x80000000, 0, 0, 3u, 0, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v6 = 0;
LABEL_3:
    LastError = GetLastError();
    goto LABEL_13;
  }
  v6 = 1;
  FileSize = GetFileSize(FileW, &FileSizeHigh);
  if ( FileSize == -1 && GetLastError() )
    goto LABEL_3;
  if ( FileSizeHigh )
  {
    LastError = 24;
  }
  else
  {
    *((_DWORD *)a2 + 2) = FileSize;
    LastError = 8;
    FileMappingW = CreateFileMappingW(v5, 0, 8u, 0, 0, 0);
    v2 = FileMappingW;
    if ( !FileMappingW )
      goto LABEL_3;
    v10 = MapViewOfFile(FileMappingW, 1u, 0, 0, 0);
    *(_QWORD *)a2 = v10;
    if ( !v10 )
      goto LABEL_3;
    v11 = GlobalAlloc(2u, *((unsigned int *)a2 + 2));
    *((_QWORD *)a2 + 2) = v11;
    if ( v11 )
    {
      v12 = GlobalLock(v11);
      LastError = GetLastError();
      if ( v12 )
      {
        memcpy_0(v12, *(const void **)a2, *((unsigned int *)a2 + 2));
        GlobalUnlock(*((HGLOBAL *)a2 + 2));
        LastError = 0;
      }
    }
  }
LABEL_13:
  if ( *(_QWORD *)a2 )
  {
    UnmapViewOfFile(*(LPCVOID *)a2);
    *(_QWORD *)a2 = 0;
  }
  if ( v2 )
    CloseHandle(v2);
  if ( v6 )
    CloseHandle(v5);
  return LastError;
}

```

## disassembly

```asm
0x140037e2c  mov     rax, rsp
0x140037e2f  push    rbx
0x140037e30  push    rbp
0x140037e31  push    rsi
0x140037e32  push    rdi
0x140037e33  push    r14
0x140037e35  push    r15
0x140037e37  sub     rsp, 48h
0x140037e3b  xor     esi, esi
0x140037e3d  mov     dword ptr [rax+10h], 0
0x140037e44  mov     [rax-48h], rsi
0x140037e48  mov     rdi, rdx
0x140037e4b  mov     [rax-50h], esi
0x140037e4e  xor     r9d, r9d; lpSecurityAttributes
0x140037e51  xor     r8d, r8d; dwShareMode
0x140037e54  mov     dword ptr [rax-58h], 3
0x140037e5b  mov     edx, 80000000h; dwDesiredAccess
0x140037e60  call    cs:__imp_CreateFileW
0x140037e66  mov     rbp, rax
0x140037e69  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140037e6d  jnz     short loc_140037E7F
0x140037e6f  xor     r14b, r14b
0x140037e72  call    cs:__imp_GetLastError
0x140037e78  mov     ebx, eax
0x140037e7a  jmp     loc_140037F53
0x140037e7f  lea     rdx, [rsp+78h+FileSizeHigh]; lpFileSizeHigh
0x140037e87  mov     rcx, rbp; hFile
0x140037e8a  mov     r14d, 1
0x140037e90  call    cs:__imp_GetFileSize
0x140037e96  mov     ebx, eax
0x140037e98  cmp     eax, 0FFFFFFFFh
0x140037e9b  jnz     short loc_140037EA7
0x140037e9d  call    cs:__imp_GetLastError
0x140037ea3  test    eax, eax
0x140037ea5  jnz     short loc_140037E72
0x140037ea7  cmp     [rsp+78h+FileSizeHigh], esi
0x140037eae  jz      short loc_140037EBA
0x140037eb0  mov     ebx, 18h
0x140037eb5  jmp     loc_140037F53
0x140037eba  xor     r9d, r9d; dwMaximumSizeHigh
0x140037ebd  mov     [rdi+8], ebx
0x140037ec0  mov     [rsp+78h+lpName], rsi; lpName
0x140037ec5  xor     edx, edx; lpFileMappingAttributes
0x140037ec7  mov     rcx, rbp; hFile
0x140037eca  mov     [rsp+78h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x140037ece  lea     ebx, [r9+8]
0x140037ed2  mov     r8d, ebx; flProtect
0x140037ed5  call    cs:__imp_CreateFileMappingW
0x140037edb  mov     rsi, rax
0x140037ede  test    rax, rax
0x140037ee1  jz      short loc_140037E72
0x140037ee3  xor     r9d, r9d; dwFileOffsetLow
0x140037ee6  mov     qword ptr [rsp+78h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x140037eef  xor     r8d, r8d; dwFileOffsetHigh
0x140037ef2  mov     edx, r14d; dwDesiredAccess
0x140037ef5  mov     rcx, rax; hFileMappingObject
0x140037ef8  call    cs:__imp_MapViewOfFile
0x140037efe  mov     [rdi], rax
0x140037f01  test    rax, rax
0x140037f04  jz      loc_140037E72
0x140037f0a  mov     edx, [rdi+8]; dwBytes
0x140037f0d  lea     ecx, [rbx-6]; uFlags
0x140037f10  call    cs:__imp_GlobalAlloc
0x140037f16  mov     [rdi+10h], rax
0x140037f1a  test    rax, rax
0x140037f1d  jz      short loc_140037F53
0x140037f1f  mov     rcx, rax; hMem
0x140037f22  call    cs:__imp_GlobalLock
0x140037f28  mov     r15, rax
0x140037f2b  call    cs:__imp_GetLastError
0x140037f31  mov     ebx, eax
0x140037f33  test    r15, r15
0x140037f36  jz      short loc_140037F53
0x140037f38  mov     r8d, [rdi+8]; Size
0x140037f3c  mov     rcx, r15; void *
0x140037f3f  mov     rdx, [rdi]; Src
0x140037f42  call    memcpy_0
0x140037f47  mov     rcx, [rdi+10h]; hMem
0x140037f4b  call    cs:__imp_GlobalUnlock
0x140037f51  xor     ebx, ebx
0x140037f53  mov     rcx, [rdi]; lpBaseAddress
0x140037f56  test    rcx, rcx
0x140037f59  jz      short loc_140037F68
0x140037f5b  call    cs:__imp_UnmapViewOfFile
0x140037f61  mov     qword ptr [rdi], 0
0x140037f68  test    rsi, rsi
0x140037f6b  jz      short loc_140037F76
0x140037f6d  mov     rcx, rsi; hObject
0x140037f70  call    cs:__imp_CloseHandle
0x140037f76  test    r14b, r14b
0x140037f79  jz      short loc_140037F84
0x140037f7b  mov     rcx, rbp; hObject
0x140037f7e  call    cs:__imp_CloseHandle
0x140037f84  mov     eax, ebx
0x140037f86  add     rsp, 48h
0x140037f8a  pop     r15
0x140037f8c  pop     r14
0x140037f8e  pop     rdi
0x140037f8f  pop     rsi
0x140037f90  pop     rbp
0x140037f91  pop     rbx
0x140037f92  retn
```
