# PfsGetLastWriteTime

- ea: `0x1800195c8`
- end: `0x180019649`
- name: `PfsGetLastWriteTime`
- size: `129`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180018ec0`
- `0x180019dfc`
- `0x180082dc8`

## callees

- `0x1800195c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019627`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019636`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019636`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18001961d`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18001961d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800195f9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800195f9`

## pseudocode

```c
__int64 __fastcall PfsGetLastWriteTime(const WCHAR *a1, struct _FILETIME *a2)
{
  HANDLE FileW; // rax
  void *v4; // rdi
  DWORD LastError; // ebx

  FileW = CreateFileW(a1, 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    return GetLastError();
  }
  else
  {
    if ( GetFileTime(FileW, 0, 0, a2) )
      LastError = 0;
    else
      LastError = GetLastError();
    CloseHandle(v4);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800195c8  mov     rax, rsp
0x1800195cb  mov     [rax+8], rbx
0x1800195cf  push    rdi
0x1800195d0  sub     rsp, 40h
0x1800195d4  mov     qword ptr [rax-18h], 0
0x1800195dc  xor     r9d, r9d; lpSecurityAttributes
0x1800195df  mov     rbx, rdx
0x1800195e2  mov     dword ptr [rax-20h], 2000000h
0x1800195e9  mov     edx, 80000000h; dwDesiredAccess
0x1800195ee  mov     dword ptr [rax-28h], 3
0x1800195f5  lea     r8d, [r9+7]; dwShareMode
0x1800195f9  call    cs:__imp_CreateFileW
0x1800195ff  mov     rdi, rax
0x180019602  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180019606  jnz     short loc_180019612
0x180019608  call    cs:__imp_GetLastError
0x18001960e  mov     ebx, eax
0x180019610  jmp     short loc_18001963C
0x180019612  mov     r9, rbx; lpLastWriteTime
0x180019615  xor     r8d, r8d; lpLastAccessTime
0x180019618  xor     edx, edx; lpCreationTime
0x18001961a  mov     rcx, rdi; hFile
0x18001961d  call    cs:__imp_GetFileTime
0x180019623  test    eax, eax
0x180019625  jnz     short loc_180019631
0x180019627  call    cs:__imp_GetLastError
0x18001962d  mov     ebx, eax
0x18001962f  jmp     short loc_180019633
0x180019631  xor     ebx, ebx
0x180019633  mov     rcx, rdi; hObject
0x180019636  call    cs:__imp_CloseHandle
0x18001963c  mov     eax, ebx
0x18001963e  mov     rbx, [rsp+48h+arg_0]
0x180019643  add     rsp, 40h
0x180019647  pop     rdi
0x180019648  retn
```
