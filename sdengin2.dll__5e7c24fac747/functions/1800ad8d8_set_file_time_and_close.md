# set_file_time_and_close

- ea: `0x1800ad8d8`
- end: `0x1800ad9c5`
- name: `set_file_time_and_close`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800ab35c`
- `0x1800ac900`

## callees

- `0x1800ad8d8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800ad911`
- `KERNEL32!CloseHandle` at `0x1800ad9a0`
- `KERNEL32!CloseHandle` at `0x1800ad911`
- `KERNEL32!CloseHandle` at `0x1800ad9a0`
- `KERNEL32!SetFileTime` at `0x1800ad997`
- `KERNEL32!SetFileTime` at `0x1800ad997`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800ad8f8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800ad8f8`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x1800ad945`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x1800ad945`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800ad976`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800ad976`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x1800ad9af`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x1800ad9af`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x1800ad935`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x1800ad935`

## pseudocode

```c
int set_file_time_and_close()
{
  char *Value; // rax
  char *v1; // rbx
  WORD v2; // dx
  WORD v3; // cx
  HANDLE FileA; // rax
  void *v5; // rdi
  FILETIME CreationTime; // [rsp+50h] [rbp+8h] BYREF
  struct _FILETIME FileTime; // [rsp+58h] [rbp+10h] BYREF

  FileTime = 0;
  CreationTime = 0;
  Value = (char *)TlsGetValue(dwUnZIPTlsIndex);
  v1 = Value;
  if ( Value )
  {
    CloseHandle(*(HANDLE *)(Value + 72178));
    v2 = *((_WORD *)v1 + 2527);
    v3 = *((_WORD *)v1 + 2528);
    *(_QWORD *)(v1 + 72178) = -1;
    DosDateTimeToFileTime(v3, v2, &FileTime);
    LocalFileTimeToFileTime(&FileTime, &CreationTime);
    FileA = CreateFileA(v1 + 4020, 0xC0000000, 1u, 0, 3u, 0x80u, 0);
    v5 = FileA;
    if ( FileA != (HANDLE)-1LL )
    {
      SetFileTime(FileA, &CreationTime, &CreationTime, &CreationTime);
      CloseHandle(v5);
    }
    LODWORD(Value) = SetFileAttributesA(v1 + 4020, *((_DWORD *)v1 + 1135));
  }
  return (int)Value;
}

```

## disassembly

```asm
0x1800ad8d8  mov     rax, rsp
0x1800ad8db  mov     [rax+18h], rbx
0x1800ad8df  mov     [rax+20h], rsi
0x1800ad8e3  push    rdi
0x1800ad8e4  sub     rsp, 40h
0x1800ad8e8  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x1800ad8ee  xor     edi, edi
0x1800ad8f0  mov     [rax+10h], rdi
0x1800ad8f4  mov     [rax+8], rdi
0x1800ad8f8  call    cs:__imp_TlsGetValue
0x1800ad8fe  mov     rbx, rax
0x1800ad901  test    rax, rax
0x1800ad904  jz      loc_1800AD9B5
0x1800ad90a  mov     rcx, [rax+119F2h]; hObject
0x1800ad911  call    cs:__imp_CloseHandle
0x1800ad917  movzx   edx, word ptr [rbx+13BEh]; wFatTime
0x1800ad91e  lea     r8, [rsp+48h+FileTime]; lpFileTime
0x1800ad923  movzx   ecx, word ptr [rbx+13C0h]; wFatDate
0x1800ad92a  mov     qword ptr [rbx+119F2h], 0FFFFFFFFFFFFFFFFh
0x1800ad935  call    cs:__imp_DosDateTimeToFileTime
0x1800ad93b  lea     rdx, [rsp+48h+CreationTime]; lpFileTime
0x1800ad940  lea     rcx, [rsp+48h+FileTime]; lpLocalFileTime
0x1800ad945  call    cs:__imp_LocalFileTimeToFileTime
0x1800ad94b  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x1800ad950  lea     rsi, [rbx+0FB4h]
0x1800ad957  mov     rcx, rsi; lpFileName
0x1800ad95a  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800ad962  xor     r9d, r9d; lpSecurityAttributes
0x1800ad965  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800ad96d  mov     edx, 0C0000000h; dwDesiredAccess
0x1800ad972  lea     r8d, [rdi+1]; dwShareMode
0x1800ad976  call    cs:__imp_CreateFileA
0x1800ad97c  mov     rdi, rax
0x1800ad97f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ad983  jz      short loc_1800AD9A6
0x1800ad985  lea     r9, [rsp+48h+CreationTime]; lpLastWriteTime
0x1800ad98a  mov     rcx, rax; hFile
0x1800ad98d  lea     r8, [rsp+48h+CreationTime]; lpLastAccessTime
0x1800ad992  lea     rdx, [rsp+48h+CreationTime]; lpCreationTime
0x1800ad997  call    cs:__imp_SetFileTime
0x1800ad99d  mov     rcx, rdi; hObject
0x1800ad9a0  call    cs:__imp_CloseHandle
0x1800ad9a6  mov     edx, [rbx+11BCh]; dwFileAttributes
0x1800ad9ac  mov     rcx, rsi; lpFileName
0x1800ad9af  call    cs:__imp_SetFileAttributesA
0x1800ad9b5  mov     rbx, [rsp+48h+arg_10]
0x1800ad9ba  mov     rsi, [rsp+48h+arg_18]
0x1800ad9bf  add     rsp, 40h
0x1800ad9c3  pop     rdi
0x1800ad9c4  retn
```
