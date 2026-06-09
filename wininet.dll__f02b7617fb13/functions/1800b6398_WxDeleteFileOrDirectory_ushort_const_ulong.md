# WxDeleteFileOrDirectory(ushort const *,ulong)

- ea: `0x1800b6398`
- end: `0x1800b64a9`
- name: `?WxDeleteFileOrDirectory@@YAJPEBGK@Z`
- size: `273`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001a7d8`
- `0x1800b5e3c`
- `0x1800b6594`
- `0x1800eb3e8`
- `0x180136748`

## callees

- `0x1800b6398`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b63d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b63d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6447`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b6417`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b6417`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800b646d`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800b646d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800b6439`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800b6439`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b63c2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b63c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b6426`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b6426`

## pseudocode

```c
__int64 __fastcall WxDeleteFileOrDirectory(LPCWSTR lpPathName, int a2)
{
  int v2; // ebx
  BOOL v4; // eax
  DWORD v5; // eax
  HANDLE FileW; // rax
  DWORD v7; // edx
  signed int LastError; // ecx
  bool v10; // sf

  v2 = a2 & 0x10;
  if ( (a2 & 7) == 0 )
    goto LABEL_2;
  v7 = a2 & 0xFFFFFFF8;
  if ( !v7 )
    v7 = 128;
  if ( SetFileAttributesW(lpPathName, v7) )
    goto LABEL_2;
  LastError = GetLastError();
  if ( ((LastError - 2) & 0xFFFFFFFC) == 0 && LastError != 4 )
    return 0;
  v10 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = LastError < 0;
  }
  if ( !v10 )
  {
LABEL_2:
    if ( v2 )
      v4 = RemoveDirectoryW(lpPathName);
    else
      v4 = DeleteFileW(lpPathName);
    if ( !v4 )
    {
      v5 = GetLastError();
      if ( ((v5 - 2) & 0xFFFFFFFC) != 0 || v5 == 4 )
      {
        FileW = CreateFileW(lpPathName, 0x13019Fu, 7u, 0, 3u, v2 != 0 ? 100663296 : 0x4000000, 0);
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
0x1800b6398  mov     [rsp+arg_10], rbx
0x1800b639d  push    rdi
0x1800b639e  sub     rsp, 50h
0x1800b63a2  mov     ebx, edx
0x1800b63a4  mov     [rsp+58h+var_14], 0
0x1800b63ac  and     ebx, 10h
0x1800b63af  mov     rdi, rcx
0x1800b63b2  test    dl, 7
0x1800b63b5  jnz     short loc_1800B642E
0x1800b63b7  mov     rcx, rdi; lpPathName
0x1800b63ba  test    ebx, ebx
0x1800b63bc  jnz     loc_1800B646D
0x1800b63c2  call    cs:__imp_DeleteFileW
0x1800b63c8  test    eax, eax
0x1800b63ca  jnz     loc_1800B645E
0x1800b63d0  call    cs:__imp_GetLastError
0x1800b63d6  lea     ecx, [rax-2]
0x1800b63d9  test    ecx, 0FFFFFFFCh
0x1800b63df  jz      loc_1800B647F
0x1800b63e5  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x1800b63ee  neg     ebx
0x1800b63f0  mov     edx, 13019Fh; dwDesiredAccess
0x1800b63f5  mov     rcx, rdi; lpFileName
0x1800b63f8  sbb     eax, eax
0x1800b63fa  xor     r9d, r9d; lpSecurityAttributes
0x1800b63fd  and     eax, 2000000h
0x1800b6402  add     eax, 4000000h
0x1800b6407  mov     [rsp+58h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1800b640b  lea     r8d, [r9+7]; dwShareMode
0x1800b640f  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x1800b6417  call    cs:__imp_CreateFileW
0x1800b641d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b6421  jz      short loc_1800B6478
0x1800b6423  mov     rcx, rax; hObject
0x1800b6426  call    cs:__imp_CloseHandle
0x1800b642c  jmp     short loc_1800B645E
0x1800b642e  and     edx, 0FFFFFFF8h
0x1800b6431  mov     eax, 80h
0x1800b6436  cmovz   edx, eax; dwFileAttributes
0x1800b6439  call    cs:__imp_SetFileAttributesW
0x1800b643f  test    eax, eax
0x1800b6441  jnz     loc_1800B63B7
0x1800b6447  call    cs:__imp_GetLastError
0x1800b644d  mov     ecx, eax
0x1800b644f  add     eax, 0FFFFFFFEh
0x1800b6452  test    eax, 0FFFFFFFCh
0x1800b6457  jnz     short loc_1800B648A
0x1800b6459  cmp     ecx, 4
0x1800b645c  jz      short loc_1800B648A
0x1800b645e  xor     ecx, ecx
0x1800b6460  mov     rbx, [rsp+58h+arg_10]
0x1800b6465  mov     eax, ecx
0x1800b6467  add     rsp, 50h
0x1800b646b  pop     rdi
0x1800b646c  retn
0x1800b646d  call    cs:__imp_RemoveDirectoryW
0x1800b6473  jmp     loc_1800B63C8
0x1800b6478  mov     ecx, 1
0x1800b647d  jmp     short loc_1800B6460
0x1800b647f  cmp     eax, 4
0x1800b6482  jz      loc_1800B63E5
0x1800b6488  jmp     short loc_1800B645E
0x1800b648a  test    ecx, ecx
0x1800b648c  jle     short loc_1800B6499
0x1800b648e  movzx   ecx, cx
0x1800b6491  or      ecx, 80070000h
0x1800b6497  test    ecx, ecx
0x1800b6499  jns     loc_1800B63B7
0x1800b649f  mov     [rsp+58h+var_14], 16Eh
0x1800b64a7  jmp     short loc_1800B6460
```
