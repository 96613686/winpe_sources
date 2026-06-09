# BumpFileTime(ushort const *)

- ea: `0x180044060`
- end: `0x18004412a`
- name: `?BumpFileTime@@YAXPEBG@Z`
- size: `202`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002cc30`

## callees

- `0x180036f50`
- `0x180044060`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004410e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004410e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004409d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004409d`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180044105`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180044105`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800440cc`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800440cc`

## pseudocode

```c
void __fastcall BumpFileTime(const unsigned __int16 *a1)
{
  HANDLE FileW; // rbx
  unsigned __int64 v2; // rdx
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+40h] [rbp-48h] BYREF

  FileW = CreateFileW(a1, 0xC0000000, 7u, 0, 3u, 0, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    memset(&FileInformation, 0, sizeof(FileInformation));
    if ( GetFileInformationByHandle(FileW, &FileInformation) )
    {
      v2 = ((unsigned __int64)FileInformation.ftLastWriteTime.dwHighDateTime << 32)
         + FileInformation.ftLastWriteTime.dwLowDateTime
         + 20000000LL;
      FileInformation.ftLastWriteTime.dwLowDateTime += 20000000;
      FileInformation.ftLastWriteTime.dwHighDateTime = HIDWORD(v2);
      SetFileTime(FileW, 0, 0, &FileInformation.ftLastWriteTime);
    }
    CloseHandle(FileW);
  }
}

```

## disassembly

```asm
0x180044060  push    rbx
0x180044062  sub     rsp, 80h
0x180044069  mov     rax, cs:__security_cookie
0x180044070  xor     rax, rsp
0x180044073  mov     [rsp+88h+var_10], rax
0x180044078  xor     r9d, r9d; lpSecurityAttributes
0x18004407b  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x180044084  mov     [rsp+88h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18004408c  mov     edx, 0C0000000h; dwDesiredAccess
0x180044091  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x180044099  lea     r8d, [r9+7]; dwShareMode
0x18004409d  call    cs:__imp_CreateFileW
0x1800440a3  mov     rbx, rax
0x1800440a6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800440aa  jz      short loc_180044114
0x1800440ac  xorps   xmm0, xmm0
0x1800440af  lea     rdx, [rsp+88h+FileInformation]; lpFileInformation
0x1800440b4  xor     eax, eax
0x1800440b6  mov     rcx, rbx; hFile
0x1800440b9  movups  xmmword ptr [rsp+88h+FileInformation.dwFileAttributes], xmm0
0x1800440be  mov     [rsp+88h+FileInformation.nFileIndexLow], eax
0x1800440c2  movups  xmmword ptr [rsp+88h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800440c7  movups  xmmword ptr [rsp+88h+FileInformation.nFileSizeHigh], xmm0
0x1800440cc  call    cs:__imp_GetFileInformationByHandle
0x1800440d2  test    eax, eax
0x1800440d4  jz      short loc_18004410B
0x1800440d6  mov     ecx, [rsp+88h+FileInformation.ftLastWriteTime.dwHighDateTime]
0x1800440da  lea     r9, [rsp+88h+FileInformation.ftLastWriteTime]; lpLastWriteTime
0x1800440df  mov     edx, [rsp+88h+FileInformation.ftLastWriteTime.dwLowDateTime]
0x1800440e3  xor     r8d, r8d; lpLastAccessTime
0x1800440e6  add     rdx, 1312D00h
0x1800440ed  shl     rcx, 20h
0x1800440f1  add     rdx, rcx
0x1800440f4  mov     rcx, rbx; hFile
0x1800440f7  mov     [rsp+88h+FileInformation.ftLastWriteTime.dwLowDateTime], edx
0x1800440fb  shr     rdx, 20h
0x1800440ff  mov     [rsp+88h+FileInformation.ftLastWriteTime.dwHighDateTime], edx
0x180044103  xor     edx, edx; lpCreationTime
0x180044105  call    cs:__imp_SetFileTime
0x18004410b  mov     rcx, rbx; hObject
0x18004410e  call    cs:__imp_CloseHandle
0x180044114  mov     rcx, [rsp+88h+var_10]
0x180044119  xor     rcx, rsp; StackCookie
0x18004411c  call    __security_check_cookie
0x180044121  add     rsp, 80h
0x180044128  pop     rbx
0x180044129  retn
```
