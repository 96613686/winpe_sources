# set_file_time_and_close

- ea: `0x180007df0`
- end: `0x180007eae`
- name: `set_file_time_and_close`
- size: `190`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006630`
- `0x18002f584`

## callees

- `0x180007df0`
- `0x180036f50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007e1d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007e1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007e77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007e77`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180007e6a`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180007e6a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180007e95`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180007e95`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x180007e4e`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x180007e4e`
- `KERNEL32!DosDateTimeToFileTime` at `0x180007e3e`
- `KERNEL32!DosDateTimeToFileTime` at `0x180007e3e`

## pseudocode

```c
int set_file_time_and_close()
{
  _WORD *Value; // rax
  _WORD *v1; // rbx
  DWORD v2; // edx
  FILETIME CreationTime; // [rsp+20h] [rbp-28h] BYREF
  _FILETIME FileTime; // [rsp+28h] [rbp-20h] BYREF

  FileTime = 0;
  CreationTime = 0;
  Value = TlsGetValue(dwUnZIPTlsIndex);
  v1 = Value;
  if ( Value )
  {
    DosDateTimeToFileTime(Value[1982], Value[1981], &FileTime);
    LocalFileTimeToFileTime(&FileTime, &CreationTime);
    SetFileTime(*((HANDLE *)v1 + 9023), &CreationTime, &CreationTime, &CreationTime);
    CloseHandle(*((HANDLE *)v1 + 9023));
    v2 = *((_DWORD *)v1 + 802);
    *((_QWORD *)v1 + 9023) = -1;
    LODWORD(Value) = SetFileAttributesW(v1 + 1084, v2);
  }
  return (int)Value;
}

```

## disassembly

```asm
0x180007df0  push    rbx
0x180007df2  sub     rsp, 40h
0x180007df6  mov     rax, cs:__security_cookie
0x180007dfd  xor     rax, rsp
0x180007e00  mov     [rsp+48h+var_18], rax
0x180007e05  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x180007e0b  mov     qword ptr [rsp+48h+FileTime.dwLowDateTime], 0
0x180007e14  mov     qword ptr [rsp+48h+CreationTime.dwLowDateTime], 0
0x180007e1d  call    cs:__imp_TlsGetValue
0x180007e23  mov     rbx, rax
0x180007e26  test    rax, rax
0x180007e29  jz      short loc_180007E9B
0x180007e2b  movzx   edx, word ptr [rax+0F7Ah]; wFatTime
0x180007e32  lea     r8, [rsp+48h+FileTime]; lpFileTime
0x180007e37  movzx   ecx, word ptr [rax+0F7Ch]; wFatDate
0x180007e3e  call    cs:__imp_DosDateTimeToFileTime
0x180007e44  lea     rdx, [rsp+48h+CreationTime]; lpFileTime
0x180007e49  lea     rcx, [rsp+48h+FileTime]; lpLocalFileTime
0x180007e4e  call    cs:__imp_LocalFileTimeToFileTime
0x180007e54  mov     rcx, [rbx+119F8h]; hFile
0x180007e5b  lea     r9, [rsp+48h+CreationTime]; lpLastWriteTime
0x180007e60  lea     r8, [rsp+48h+CreationTime]; lpLastAccessTime
0x180007e65  lea     rdx, [rsp+48h+CreationTime]; lpCreationTime
0x180007e6a  call    cs:__imp_SetFileTime
0x180007e70  mov     rcx, [rbx+119F8h]; hObject
0x180007e77  call    cs:__imp_CloseHandle
0x180007e7d  mov     edx, [rbx+0C88h]; dwFileAttributes
0x180007e83  lea     rcx, [rbx+878h]; lpFileName
0x180007e8a  mov     qword ptr [rbx+119F8h], 0FFFFFFFFFFFFFFFFh
0x180007e95  call    cs:__imp_SetFileAttributesW
0x180007e9b  mov     rcx, [rsp+48h+var_18]
0x180007ea0  xor     rcx, rsp; StackCookie
0x180007ea3  call    __security_check_cookie
0x180007ea8  add     rsp, 40h
0x180007eac  pop     rbx
0x180007ead  retn
```
