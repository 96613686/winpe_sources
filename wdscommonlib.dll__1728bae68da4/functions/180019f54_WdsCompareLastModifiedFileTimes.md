# WdsCompareLastModifiedFileTimes

- ea: `0x180019f54`
- end: `0x18001a0f0`
- name: `WdsCompareLastModifiedFileTimes`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001ba90`

## callees

- `0x180019f54`
- `0x18001b0cc`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x18001a0a4`
- `KERNEL32!CompareFileTime` at `0x18001a0a4`
- `KERNEL32!GetFileTime` at `0x18001a045`
- `KERNEL32!GetFileTime` at `0x18001a076`
- `KERNEL32!GetFileTime` at `0x18001a045`
- `KERNEL32!GetFileTime` at `0x18001a076`
- `KERNEL32!CreateFileW` at `0x180019f97`
- `KERNEL32!CreateFileW` at `0x180019ffb`
- `KERNEL32!CreateFileW` at `0x180019f97`
- `KERNEL32!CreateFileW` at `0x180019ffb`
- `KERNEL32!GetLastError` at `0x180019fac`
- `KERNEL32!GetLastError` at `0x18001a010`
- `KERNEL32!GetLastError` at `0x18001a055`
- `KERNEL32!GetLastError` at `0x18001a086`
- `KERNEL32!GetLastError` at `0x180019fac`
- `KERNEL32!GetLastError` at `0x18001a010`
- `KERNEL32!GetLastError` at `0x18001a055`
- `KERNEL32!GetLastError` at `0x18001a086`
- `KERNEL32!CloseHandle` at `0x18001a0b6`
- `KERNEL32!CloseHandle` at `0x18001a0cb`
- `KERNEL32!CloseHandle` at `0x18001a0b6`
- `KERNEL32!CloseHandle` at `0x18001a0cb`

## pseudocode

```c
__int64 __fastcall WdsCompareLastModifiedFileTimes(const WCHAR *a1, const WCHAR *a2, LONG *a3)
{
  unsigned int v3; // ebx
  HANDLE FileW; // rsi
  DWORD LastError; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  HANDLE v10; // rdi
  DWORD v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  struct _FILETIME LastWriteTime; // [rsp+40h] [rbp-18h] BYREF
  FILETIME FileTime2; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  LastWriteTime = 0;
  FileTime2 = 0;
  FileW = CreateFileW(a1, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v3 = ElValidateWin32_8(LastError, v8, v9, 3074);
    if ( !v3 )
      return 31;
    return v3;
  }
  v10 = CreateFileW(a2, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( v10 == (HANDLE)-1LL )
  {
    v11 = GetLastError();
    v14 = 3089;
    goto LABEL_6;
  }
  if ( !GetFileTime(FileW, 0, 0, &LastWriteTime) )
  {
    v11 = GetLastError();
    v14 = 3100;
    goto LABEL_6;
  }
  if ( !GetFileTime(v10, 0, 0, &FileTime2) )
  {
    v11 = GetLastError();
    v14 = 3108;
LABEL_6:
    v3 = ElValidateWin32_8(v11, v12, v13, v14);
    if ( !v3 )
      v3 = 31;
    goto LABEL_13;
  }
  *a3 = CompareFileTime(&LastWriteTime, &FileTime2);
LABEL_13:
  CloseHandle(FileW);
  if ( v10 != (HANDLE)-1LL )
    CloseHandle(v10);
  return v3;
}

```

## disassembly

```asm
0x180019f54  mov     rax, rsp
0x180019f57  mov     [rax+8], rbx
0x180019f5b  mov     [rax+10h], rsi
0x180019f5f  mov     [rax+18h], rdi
0x180019f63  push    r14
0x180019f65  sub     rsp, 50h
0x180019f69  xor     ebx, ebx
0x180019f6b  mov     r14, r8
0x180019f6e  and     [rax-28h], rbx
0x180019f72  mov     rdi, rdx
0x180019f75  and     [rax-18h], rbx
0x180019f79  xor     r9d, r9d; lpSecurityAttributes
0x180019f7c  and     [rax+20h], rbx
0x180019f80  mov     edx, 80000000h; dwDesiredAccess
0x180019f85  mov     dword ptr [rax-30h], 80h
0x180019f8c  lea     r8d, [rbx+7]; dwShareMode
0x180019f90  mov     dword ptr [rax-38h], 3
0x180019f97  call    cs:__imp_CreateFileW
0x180019f9e  nop     dword ptr [rax+rax+00h]
0x180019fa3  mov     rsi, rax
0x180019fa6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180019faa  jnz     short loc_180019FD7
0x180019fac  call    cs:__imp_GetLastError
0x180019fb3  nop     dword ptr [rax+rax+00h]
0x180019fb8  mov     ecx, eax
0x180019fba  mov     r9d, 0C02h
0x180019fc0  call    ElValidateWin32_8
0x180019fc5  mov     ebx, eax
0x180019fc7  test    eax, eax
0x180019fc9  jnz     loc_18001A0D7
0x180019fcf  lea     ebx, [rsi+20h]
0x180019fd2  jmp     loc_18001A0D7
0x180019fd7  and     [rsp+58h+var_28], rbx
0x180019fdc  xor     r9d, r9d; lpSecurityAttributes
0x180019fdf  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180019fe7  mov     edx, 80000000h; dwDesiredAccess
0x180019fec  mov     rcx, rdi; lpFileName
0x180019fef  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x180019ff7  lea     r8d, [r9+7]; dwShareMode
0x180019ffb  call    cs:__imp_CreateFileW
0x18001a002  nop     dword ptr [rax+rax+00h]
0x18001a007  mov     rdi, rax
0x18001a00a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a00e  jnz     short loc_18001A038
0x18001a010  call    cs:__imp_GetLastError
0x18001a017  nop     dword ptr [rax+rax+00h]
0x18001a01c  mov     r9d, 0C11h
0x18001a022  mov     ecx, eax
0x18001a024  call    ElValidateWin32_8
0x18001a029  mov     ebx, eax
0x18001a02b  test    eax, eax
0x18001a02d  jnz     loc_18001A0B3
0x18001a033  lea     ebx, [rax+1Fh]
0x18001a036  jmp     short loc_18001A0B3
0x18001a038  lea     r9, [rsp+58h+LastWriteTime]; lpLastWriteTime
0x18001a03d  xor     r8d, r8d; lpLastAccessTime
0x18001a040  xor     edx, edx; lpCreationTime
0x18001a042  mov     rcx, rsi; hFile
0x18001a045  call    cs:__imp_GetFileTime
0x18001a04c  nop     dword ptr [rax+rax+00h]
0x18001a051  test    eax, eax
0x18001a053  jnz     short loc_18001A069
0x18001a055  call    cs:__imp_GetLastError
0x18001a05c  nop     dword ptr [rax+rax+00h]
0x18001a061  mov     r9d, 0C1Ch
0x18001a067  jmp     short loc_18001A022
0x18001a069  lea     r9, [rsp+58h+FileTime2]; lpLastWriteTime
0x18001a06e  xor     r8d, r8d; lpLastAccessTime
0x18001a071  xor     edx, edx; lpCreationTime
0x18001a073  mov     rcx, rdi; hFile
0x18001a076  call    cs:__imp_GetFileTime
0x18001a07d  nop     dword ptr [rax+rax+00h]
0x18001a082  test    eax, eax
0x18001a084  jnz     short loc_18001A09A
0x18001a086  call    cs:__imp_GetLastError
0x18001a08d  nop     dword ptr [rax+rax+00h]
0x18001a092  mov     r9d, 0C24h
0x18001a098  jmp     short loc_18001A022
0x18001a09a  lea     rdx, [rsp+58h+FileTime2]; lpFileTime2
0x18001a09f  lea     rcx, [rsp+58h+LastWriteTime]; lpFileTime1
0x18001a0a4  call    cs:__imp_CompareFileTime
0x18001a0ab  nop     dword ptr [rax+rax+00h]
0x18001a0b0  mov     [r14], eax
0x18001a0b3  mov     rcx, rsi; hObject
0x18001a0b6  call    cs:__imp_CloseHandle
0x18001a0bd  nop     dword ptr [rax+rax+00h]
0x18001a0c2  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001a0c6  jz      short loc_18001A0D7
0x18001a0c8  mov     rcx, rdi; hObject
0x18001a0cb  call    cs:__imp_CloseHandle
0x18001a0d2  nop     dword ptr [rax+rax+00h]
0x18001a0d7  mov     rsi, [rsp+58h+arg_8]
0x18001a0dc  mov     eax, ebx
0x18001a0de  mov     rbx, [rsp+58h+arg_0]
0x18001a0e3  mov     rdi, [rsp+58h+arg_10]
0x18001a0e8  add     rsp, 50h
0x18001a0ec  pop     r14
0x18001a0ee  retn
```
