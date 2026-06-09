# DAV_IF_HELPER::GetETag(ushort const *,STRU *)

- ea: `0x18000579c`
- end: `0x1800058dd`
- name: `?GetETag@DAV_IF_HELPER@@AEAAJPEBGPEAVSTRU@@@Z`
- size: `321`
- prototype: `int(DAV_IF_HELPER *__hidden this, const unsigned __int16 *, struct STRU *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006ba0`

## callees

- `0x18000579c`
- `0x180019d94`
- `0x18001a914`
- `0x180022520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005845`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005845`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005877`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18000586d`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18000586d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180005836`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180005836`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058b2`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800057e7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800057e7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000585b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000585b`

## pseudocode

```c
__int64 __fastcall DAV_IF_HELPER::GetETag(struct IHttpContext **this, const unsigned __int16 *a2, struct STRU *a3)
{
  __int64 FileW; // rsi
  signed int ETag; // ebx
  signed int LastError; // eax
  signed int v9; // eax
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v12[32]; // [rsp+78h] [rbp-60h] BYREF
  LPCWSTR lpFileName; // [rsp+98h] [rbp-40h]

  memset(&FileInformation, 0, sizeof(FileInformation));
  FileW = -1;
  STRU::STRU((STRU *)v12);
  ETag = MapUriPathToPhysicalPath(this[1], a2, (struct STRU *)v12);
  if ( ETag >= 0 )
  {
    FileW = (__int64)CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x2000006u, 0);
    if ( FileW == -1 )
    {
      LastError = GetLastError();
      ETag = LastError;
      if ( LastError > 0 )
        ETag = (unsigned __int16)LastError | 0x80070000;
    }
  }
  STRU::~STRU((STRU *)v12);
  if ( ETag >= 0 )
  {
    if ( GetFileInformationByHandle((HANDLE)FileW, &FileInformation) )
      goto LABEL_10;
    v9 = GetLastError();
    ETag = v9;
    if ( v9 > 0 )
      ETag = (unsigned __int16)v9 | 0x80070000;
    if ( ETag >= 0 )
    {
LABEL_10:
      if ( (FileInformation.dwFileAttributes & 0x10) != 0 )
        ETag = 1;
      else
        ETag = GenerateETag(FileInformation.ftLastWriteTime, a3);
    }
  }
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return (unsigned int)ETag;
}

```

## disassembly

```asm
0x18000579c  mov     [rsp+arg_18], rbx
0x1800057a1  push    rbp
0x1800057a2  push    rsi
0x1800057a3  push    rdi
0x1800057a4  sub     rsp, 0C0h
0x1800057ab  mov     rax, cs:__security_cookie
0x1800057b2  xor     rax, rsp
0x1800057b5  mov     [rsp+0D8h+var_28], rax
0x1800057bd  xorps   xmm0, xmm0
0x1800057c0  mov     rbx, rcx
0x1800057c3  xor     eax, eax
0x1800057c5  lea     rcx, [rsp+0D8h+var_60]
0x1800057ca  movups  xmmword ptr [rsp+0D8h+FileInformation.dwFileAttributes], xmm0
0x1800057cf  mov     [rsp+0D8h+FileInformation.nFileIndexLow], eax
0x1800057d3  mov     rbp, r8
0x1800057d6  movups  xmmword ptr [rsp+0D8h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800057db  mov     rdi, rdx
0x1800057de  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800057e2  movups  xmmword ptr [rsp+0D8h+FileInformation.nFileSizeHigh], xmm0
0x1800057e7  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800057ed  mov     rcx, [rbx+8]; struct IHttpContext *
0x1800057f1  lea     r8, [rsp+0D8h+var_60]; struct STRU *
0x1800057f6  mov     rdx, rdi; unsigned __int16 *
0x1800057f9  call    ?MapUriPathToPhysicalPath@@YAJPEAVIHttpContext@@PEBGPEAVSTRU@@@Z; MapUriPathToPhysicalPath(IHttpContext *,ushort const *,STRU *)
0x1800057fe  mov     ebx, eax
0x180005800  mov     edi, 80070000h
0x180005805  test    eax, eax
0x180005807  js      short loc_180005856
0x180005809  mov     rcx, [rsp+0D8h+lpFileName]; lpFileName
0x180005811  lea     r8d, [rsi+8]; dwShareMode
0x180005815  mov     [rsp+0D8h+hTemplateFile], 0; hTemplateFile
0x18000581e  xor     r9d, r9d; lpSecurityAttributes
0x180005821  mov     [rsp+0D8h+dwFlagsAndAttributes], 2000006h; dwFlagsAndAttributes
0x180005829  mov     edx, 80000000h; dwDesiredAccess
0x18000582e  mov     [rsp+0D8h+dwCreationDisposition], 3; dwCreationDisposition
0x180005836  call    cs:__imp_CreateFileW
0x18000583c  mov     rsi, rax
0x18000583f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005843  jnz     short loc_180005856
0x180005845  call    cs:__imp_GetLastError
0x18000584b  mov     ebx, eax
0x18000584d  test    eax, eax
0x18000584f  jle     short loc_180005856
0x180005851  movzx   ebx, ax
0x180005854  or      ebx, edi
0x180005856  lea     rcx, [rsp+0D8h+var_60]
0x18000585b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005861  test    ebx, ebx
0x180005863  js      short loc_1800058A9
0x180005865  lea     rdx, [rsp+0D8h+FileInformation]; lpFileInformation
0x18000586a  mov     rcx, rsi; hFile
0x18000586d  call    cs:__imp_GetFileInformationByHandle
0x180005873  test    eax, eax
0x180005875  jnz     short loc_18000588C
0x180005877  call    cs:__imp_GetLastError
0x18000587d  mov     ebx, eax
0x18000587f  test    eax, eax
0x180005881  jle     short loc_180005888
0x180005883  movzx   ebx, ax
0x180005886  or      ebx, edi
0x180005888  test    ebx, ebx
0x18000588a  js      short loc_1800058A9
0x18000588c  test    byte ptr [rsp+0D8h+FileInformation.dwFileAttributes], 10h
0x180005891  jz      short loc_18000589A
0x180005893  mov     ebx, 1
0x180005898  jmp     short loc_1800058A9
0x18000589a  mov     rcx, qword ptr [rsp+0D8h+FileInformation.ftLastWriteTime.dwLowDateTime]; struct _FILETIME
0x18000589f  mov     rdx, rbp; struct STRU *
0x1800058a2  call    ?GenerateETag@@YAJU_FILETIME@@PEAVSTRU@@@Z; GenerateETag(_FILETIME,STRU *)
0x1800058a7  mov     ebx, eax
0x1800058a9  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800058ad  jz      short loc_1800058B8
0x1800058af  mov     rcx, rsi; hObject
0x1800058b2  call    cs:__imp_CloseHandle
0x1800058b8  mov     eax, ebx
0x1800058ba  mov     rcx, [rsp+0D8h+var_28]
0x1800058c2  xor     rcx, rsp; StackCookie
0x1800058c5  call    __security_check_cookie
0x1800058ca  mov     rbx, [rsp+0D8h+arg_18]
0x1800058d2  add     rsp, 0C0h
0x1800058d9  pop     rdi
0x1800058da  pop     rsi
0x1800058db  pop     rbp
0x1800058dc  retn
```
