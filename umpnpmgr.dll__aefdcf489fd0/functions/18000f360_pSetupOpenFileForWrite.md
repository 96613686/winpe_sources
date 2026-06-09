# pSetupOpenFileForWrite

- ea: `0x18000f360`
- end: `0x18000f452`
- name: `pSetupOpenFileForWrite`
- size: `242`
- prototype: `DWORD __fastcall(LPCWSTR lpFileName, int, __int64, unsigned int, HANDLE *, LONG *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x180018668`

## callees

- `0x18000f360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18000f3da`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18000f3da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f418`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f423`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f423`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000f3f2`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000f3f2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000f40d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000f40d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f3b2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f3b2`

## pseudocode

```c
DWORD __fastcall pSetupOpenFileForWrite(LPCWSTR lpFileName, int a2, __int64 a3, unsigned int a4, HANDLE *a5, LONG *a6)
{
  unsigned int v6; // r14d
  DWORD v7; // edi
  HANDLE FileW; // rax
  DWORD result; // eax
  DWORD v12; // ebp
  LONG FileSize; // eax
  DWORD LastError; // edi

  v6 = 0;
  v7 = a2 | 0xC0000000;
  while ( 1 )
  {
    FileW = CreateFileW(lpFileName, v7, 1u, 0, 4u, 0, 0);
    *a5 = FileW;
    if ( FileW == (HANDLE)-1LL )
      break;
LABEL_6:
    if ( *a5 != (HANDLE)-1LL )
    {
      v12 = 0;
      goto LABEL_8;
    }
  }
  result = GetLastError();
  v12 = result;
  if ( result == 32 )
  {
    if ( v6 >= a4 )
      return result;
    SleepEx(0x32u, 0);
    v6 += 50;
    goto LABEL_6;
  }
  if ( result )
    return result;
LABEL_8:
  FileSize = GetFileSize(*a5, 0);
  *a6 = FileSize;
  if ( SetFilePointer(*a5, FileSize, 0, 0) != -1 )
    return v12;
  LastError = GetLastError();
  CloseHandle(*a5);
  result = LastError;
  *a5 = (HANDLE)-1LL;
  return result;
}

```

## disassembly

```asm
0x18000f360  push    rbx
0x18000f362  push    rsi
0x18000f363  push    rdi
0x18000f364  push    r12
0x18000f366  push    r14
0x18000f368  push    r15
0x18000f36a  sub     rsp, 48h
0x18000f36e  mov     rbx, [rsp+78h+arg_20]
0x18000f376  xor     r12d, r12d
0x18000f379  mov     edi, edx
0x18000f37b  mov     [rsp+78h+arg_0], rbp
0x18000f383  mov     r14d, r12d
0x18000f386  or      edi, 0C0000000h
0x18000f38c  mov     r15d, r9d
0x18000f38f  mov     rsi, rcx
0x18000f392  mov     [rsp+78h+hTemplateFile], r12; hTemplateFile
0x18000f397  xor     r9d, r9d; lpSecurityAttributes
0x18000f39a  mov     [rsp+78h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18000f39f  mov     r8d, 1; dwShareMode
0x18000f3a5  mov     edx, edi; dwDesiredAccess
0x18000f3a7  mov     [rsp+78h+dwCreationDisposition], 4; dwCreationDisposition
0x18000f3af  mov     rcx, rsi; lpFileName
0x18000f3b2  call    cs:__imp_CreateFileW
0x18000f3b8  mov     [rbx], rax
0x18000f3bb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f3bf  jnz     short loc_18000F3E4
0x18000f3c1  call    cs:__imp_GetLastError
0x18000f3c7  mov     ebp, eax
0x18000f3c9  cmp     eax, 20h ; ' '
0x18000f3cc  jnz     short loc_18000F434
0x18000f3ce  cmp     r14d, r15d
0x18000f3d1  jnb     short loc_18000F43C
0x18000f3d3  xor     edx, edx; bAlertable
0x18000f3d5  mov     ecx, 32h ; '2'; dwMilliseconds
0x18000f3da  call    cs:__imp_SleepEx
0x18000f3e0  add     r14d, 32h ; '2'
0x18000f3e4  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18000f3e8  jz      short loc_18000F392
0x18000f3ea  mov     ebp, r12d
0x18000f3ed  mov     rcx, [rbx]; hFile
0x18000f3f0  xor     edx, edx; lpFileSizeHigh
0x18000f3f2  call    cs:__imp_GetFileSize
0x18000f3f8  mov     rcx, [rsp+78h+arg_28]
0x18000f400  xor     r9d, r9d; dwMoveMethod
0x18000f403  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000f406  mov     edx, eax; lDistanceToMove
0x18000f408  mov     [rcx], eax
0x18000f40a  mov     rcx, [rbx]; hFile
0x18000f40d  call    cs:__imp_SetFilePointer
0x18000f413  cmp     eax, 0FFFFFFFFh
0x18000f416  jnz     short loc_18000F43A
0x18000f418  call    cs:__imp_GetLastError
0x18000f41e  mov     rcx, [rbx]; hObject
0x18000f421  mov     edi, eax
0x18000f423  call    cs:__imp_CloseHandle
0x18000f429  mov     eax, edi
0x18000f42b  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18000f432  jmp     short loc_18000F43C
0x18000f434  test    eax, eax
0x18000f436  jnz     short loc_18000F43C
0x18000f438  jmp     short loc_18000F3ED
0x18000f43a  mov     eax, ebp
0x18000f43c  mov     rbp, [rsp+78h+arg_0]
0x18000f444  add     rsp, 48h
0x18000f448  pop     r15
0x18000f44a  pop     r14
0x18000f44c  pop     r12
0x18000f44e  pop     rdi
0x18000f44f  pop     rsi
0x18000f450  pop     rbx
0x18000f451  retn
```
