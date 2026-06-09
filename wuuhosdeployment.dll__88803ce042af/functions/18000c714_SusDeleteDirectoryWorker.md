# SusDeleteDirectoryWorker

- ea: `0x18000c714`
- end: `0x18000ca25`
- name: `SusDeleteDirectoryWorker`
- size: `785`
- prototype: `__int64 __fastcall(PCNZWCH *, unsigned __int64 *, __int64, __int64, int, LPWIN32_FIND_DATAW lpFindFileData)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path`

## callers

- `0x18000c714`
- `0x18000ca2c`

## callees

- `0x18000956c`
- `0x18000c414`
- `0x18000c714`
- `0x18000cf9c`
- `0x18000d088`
- `0x18000d9e8`
- `0x18000dd4c`
- `0x18000e4d4`
- `0x180042630`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c945`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c945`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c9f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c9f6`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000c9bb`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000c9bb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000c9a0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000c9a0`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c93b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c93b`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18000c7c6`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18000c7c6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c78a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c78a`

## string_xrefs

- `0x18000c7e1`: `Found reparse point at: %ws`
- `0x18000c822`: `Final path verification failed for %ws`
- `0x18000c9c5`: `SusDeleteDirectoryWorker failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=59
__int64 __fastcall SusDeleteDirectoryWorker(
        PCNZWCH *a1,
        unsigned __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        LPWIN32_FIND_DATAW lpFindFileData)
{
  __int64 v7; // r14
  int v8; // r12d
  const WCHAR *v9; // rcx
  __int64 v10; // r13
  char *FileW; // rbx
  int NextFile; // edi
  unsigned __int64 v13; // r9
  int FirstFile; // eax
  unsigned __int64 v15; // r9
  int v16; // edi
  void *v17; // r8
  int v18; // eax
  bool v20; // [rsp+50h] [rbp-69h]
  HANDLE hFindFile; // [rsp+58h] [rbp-61h] BYREF
  unsigned __int64 *v22; // [rsp+60h] [rbp-59h]
  char *v23; // [rsp+68h] [rbp-51h]
  char v24[8]; // [rsp+70h] [rbp-49h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+78h] [rbp-41h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+3Fh]

  v22 = a2;
  v7 = -1;
  hFindFile = (HANDLE)-1LL;
  v8 = 0;
  v9 = *a1;
  v10 = -1;
  do
    ++v10;
  while ( v9[v10] );
  FileW = (char *)CreateFileW(v9, 0x80010000, 1u, 0, 3u, 0x2200000u, 0);
  v23 = FileW;
  v20 = FileW + 1 == 0;
  if ( FileW == (char *)-1LL )
    goto LABEL_4;
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(FileW, &FileInformation) )
    goto LABEL_4;
  if ( (FileInformation.dwFileAttributes & 0x400) != 0 )
  {
    WUTrace(0, 0, 32, 2);
LABEL_4:
    NextFile = 1;
    goto LABEL_32;
  }
  NextFile = VerifyFinalFilePath(FileW, *a1);
  if ( NextFile < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1DF,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
      (const char *)(unsigned int)NextFile,
      (int)"Final path verification failed for %ws",
      (const char *)*a1);
    goto LABEL_36;
  }
  NextFile = WUAppendPathReAlloc((wchar_t **)a1, v22, L"*", v13);
  if ( NextFile < 0 )
    goto LABEL_32;
  memset(lpFindFileData, 0, sizeof(struct _WIN32_FIND_DATAW));
  FirstFile = SusFindFirstFile(*a1, lpFindFileData, &hFindFile);
  NextFile = FirstFile;
  if ( FirstFile < 0 )
  {
    if ( ((FirstFile + 2147024894) & 0xFFFFFFEE) == 0 && FirstFile != -2147024877 )
      NextFile = 0;
    v7 = (__int64)hFindFile;
    goto LABEL_32;
  }
  v7 = (__int64)hFindFile;
  do
  {
    (*a1)[v10] = 0;
    v16 = (int)v22;
    if ( WUAppendPathReAlloc((wchar_t **)a1, v22, lpFindFileData->cFileName, v15) < 0 )
      goto LABEL_28;
    if ( (lpFindFileData->dwFileAttributes & 0x10) == 0 )
    {
      if ( (lpFindFileData->dwFileAttributes & 1) == 0 || SetFileAttributesW(*a1, 0x80u) )
      {
        if ( (int)SusDeleteFileRetryIfSharingViolation(*a1, 0, v17) >= 0 )
          goto LABEL_29;
      }
      else
      {
        GetLastError();
      }
LABEL_28:
      v8 = 1;
      goto LABEL_29;
    }
    if ( (lpFindFileData->dwFileAttributes & 0x400) != 0 && lpFindFileData->dwReserved0 == -1610612733 )
      goto LABEL_28;
    v18 = SusDeleteDirectoryWorker((int)a1, v16, 1, 1, 0, lpFindFileData);
    if ( v18 < 0 || v18 == 1 )
      goto LABEL_28;
LABEL_29:
    NextFile = SusFindNextFile((HANDLE)v7, lpFindFileData);
  }
  while ( NextFile >= 0 );
  FileW = v23;
  if ( NextFile == -2147024878 )
    NextFile = v8 != 0;
LABEL_32:
  (*a1)[v10] = 0;
  if ( v7 != -1 )
    FindClose((HANDLE)v7);
  v24[0] = 1;
  SetFileInformationByHandle(FileW, FileDispositionInfo, v24, 1u);
  if ( NextFile < 0 )
    WUTrace(0, 0, 32, 1);
LABEL_36:
  if ( !v20 && FileW != (char *)-1LL )
    CloseHandle(FileW);
  return (unsigned int)NextFile;
}

```

## disassembly

```asm
0x18000c714  mov     [rsp-8+arg_10], rbx
0x18000c719  push    rbp
0x18000c71a  push    rsi
0x18000c71b  push    rdi
0x18000c71c  push    r12
0x18000c71e  push    r13
0x18000c720  push    r14
0x18000c722  push    r15
0x18000c724  lea     rbp, [rsp-7]
0x18000c729  sub     rsp, 0C0h
0x18000c730  mov     rax, cs:__security_cookie
0x18000c737  xor     rax, rsp
0x18000c73a  mov     [rbp+37h+var_40], rax
0x18000c73e  mov     [rbp+37h+var_90], rdx
0x18000c742  mov     rsi, rcx
0x18000c745  mov     r15, [rbp+37h+lpFindFileData]
0x18000c749  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c74d  mov     r14, rax
0x18000c750  mov     [rbp+37h+hFindFile], rax
0x18000c754  xor     edi, edi
0x18000c756  mov     r12d, edi
0x18000c759  mov     rcx, [rcx]; lpFileName
0x18000c75c  mov     r13, rax
0x18000c75f  inc     r13
0x18000c762  cmp     [rcx+r13*2], di
0x18000c767  jnz     short loc_18000C75F
0x18000c769  mov     [rsp+0F0h+hTemplateFile], rdi; hTemplateFile
0x18000c76e  mov     [rsp+0F0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18000c776  mov     [rsp+0F0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000c77e  xor     r9d, r9d; lpSecurityAttributes
0x18000c781  mov     edx, 80010000h; dwDesiredAccess
0x18000c786  lea     r8d, [r9+1]; dwShareMode
0x18000c78a  call    cs:__imp_CreateFileW
0x18000c790  mov     rbx, rax
0x18000c793  mov     [rbp+37h+var_88], rax
0x18000c797  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c79b  setz    [rbp+37h+var_A0]
0x18000c79f  jnz     short loc_18000C7AB
0x18000c7a1  mov     edi, 1
0x18000c7a6  jmp     loc_18000C98D
0x18000c7ab  xorps   xmm0, xmm0
0x18000c7ae  xor     eax, eax
0x18000c7b0  movups  xmmword ptr [rbp+37h+FileInformation.dwFileAttributes], xmm0
0x18000c7b4  movups  xmmword ptr [rbp+37h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18000c7b8  movups  xmmword ptr [rbp+37h+FileInformation.nFileSizeHigh], xmm0
0x18000c7bc  mov     [rbp+37h+FileInformation.nFileIndexLow], eax
0x18000c7bf  lea     rdx, [rbp+37h+FileInformation]; lpFileInformation
0x18000c7c3  mov     rcx, rbx; hFile
0x18000c7c6  call    cs:__imp_GetFileInformationByHandle
0x18000c7cc  test    eax, eax
0x18000c7ce  jz      short loc_18000C7A1
0x18000c7d0  mov     rdx, [rsi]; lpString1
0x18000c7d3  test    [rbp+37h+FileInformation.dwFileAttributes], 400h
0x18000c7da  jz      short loc_18000C808
0x18000c7dc  mov     [rsp+0F0h+hTemplateFile], rdx
0x18000c7e1  lea     rax, aFoundReparsePo; "Found reparse point at: %ws"
0x18000c7e8  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax
0x18000c7ed  mov     [rsp+0F0h+dwCreationDisposition], 1
0x18000c7f5  xor     edx, edx
0x18000c7f7  xor     ecx, ecx
0x18000c7f9  lea     r9d, [rdx+2]
0x18000c7fd  lea     r8d, [rdx+20h]
0x18000c801  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18000c806  jmp     short loc_18000C7A1
0x18000c808  mov     rcx, rbx; hFile
0x18000c80b  call    ?VerifyFinalFilePath@@YAJPEAXPEB_W@Z; VerifyFinalFilePath(void *,wchar_t const *)
0x18000c810  mov     edi, eax
0x18000c812  test    eax, eax
0x18000c814  jns     short loc_18000C849
0x18000c816  mov     rcx, [rbp+3Fh]; this
0x18000c81a  mov     rax, [rsi]
0x18000c81d  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax; char *
0x18000c822  lea     rax, aFinalPathVerif; "Final path verification failed for %ws"
0x18000c829  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rax; int
0x18000c82e  mov     r9d, edi; char *
0x18000c831  lea     r8, aCW1SSrcClientL_25; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000c838  mov     edx, 1DFh; void *
0x18000c83d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000c842  xor     esi, esi
0x18000c844  jmp     loc_18000C9E7
0x18000c849  lea     r8, asc_18004FB6C; "*"
0x18000c850  mov     rdx, [rbp+37h+var_90]; unsigned __int64 *
0x18000c854  mov     rcx, rsi; wchar_t **
0x18000c857  call    ?WUAppendPathReAlloc@@YAJPEAPEA_WPEA_KPEB_W_K@Z; WUAppendPathReAlloc(wchar_t * *,unsigned __int64 *,wchar_t const *,unsigned __int64)
0x18000c85c  mov     edi, eax
0x18000c85e  test    eax, eax
0x18000c860  js      loc_18000C98D
0x18000c866  xor     edx, edx; Val
0x18000c868  mov     r8d, 250h; Size
0x18000c86e  mov     rcx, r15; void *
0x18000c871  call    memset
0x18000c876  lea     r8, [rbp+37h+hFindFile]; void **
0x18000c87a  mov     rdx, r15; struct _WIN32_FIND_DATAW *
0x18000c87d  mov     rcx, [rsi]; wchar_t *
0x18000c880  call    ?SusFindFirstFile@@YAJPEB_WPEAU_WIN32_FIND_DATAW@@PEAPEAX@Z; SusFindFirstFile(wchar_t const *,_WIN32_FIND_DATAW *,void * *)
0x18000c885  mov     edi, eax
0x18000c887  xor     ecx, ecx
0x18000c889  test    eax, eax
0x18000c88b  jns     short loc_18000C8AC
0x18000c88d  add     eax, 7FF8FFFEh
0x18000c892  test    eax, 0FFFFFFEEh
0x18000c897  jnz     short loc_18000C8A3
0x18000c899  cmp     edi, 80070013h
0x18000c89f  jz      short loc_18000C8A3
0x18000c8a1  mov     edi, ecx
0x18000c8a3  mov     r14, [rbp+37h+hFindFile]
0x18000c8a7  jmp     loc_18000C98D
0x18000c8ac  mov     r14, [rbp+37h+hFindFile]
0x18000c8b0  jmp     short loc_18000C8B4
0x18000c8b2  xor     ecx, ecx
0x18000c8b4  mov     rax, [rsi]
0x18000c8b7  mov     [rax+r13*2], cx
0x18000c8bc  lea     r8, [r15+2Ch]; wchar_t *
0x18000c8c0  mov     rdi, [rbp+37h+var_90]
0x18000c8c4  mov     rdx, rdi; unsigned __int64 *
0x18000c8c7  mov     rcx, rsi; wchar_t **
0x18000c8ca  call    ?WUAppendPathReAlloc@@YAJPEAPEA_WPEA_KPEB_W_K@Z; WUAppendPathReAlloc(wchar_t * *,unsigned __int64 *,wchar_t const *,unsigned __int64)
0x18000c8cf  xor     ecx, ecx
0x18000c8d1  test    eax, eax
0x18000c8d3  js      loc_18000C95B
0x18000c8d9  test    byte ptr [r15], 10h
0x18000c8dd  jz      short loc_18000C92D
0x18000c8df  test    dword ptr [r15], 400h
0x18000c8e6  jz      short loc_18000C8F2
0x18000c8e8  cmp     dword ptr [r15+24h], 0A0000003h
0x18000c8f0  jz      short loc_18000C95B
0x18000c8f2  mov     [rsp+0F0h+var_A8], rcx
0x18000c8f7  mov     [rsp+0F0h+var_B0], ecx
0x18000c8fb  mov     [rsp+0F0h+var_B8], ecx
0x18000c8ff  mov     dword ptr [rsp+0F0h+hTemplateFile], ecx
0x18000c903  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], r15; lpFindFileData
0x18000c908  mov     [rsp+0F0h+dwCreationDisposition], ecx; int
0x18000c90c  mov     eax, 1
0x18000c911  mov     r9d, eax; int
0x18000c914  mov     r8d, eax; int
0x18000c917  mov     rdx, rdi; int
0x18000c91a  mov     rcx, rsi; int
0x18000c91d  call    SusDeleteDirectoryWorker
0x18000c922  test    eax, eax
0x18000c924  js      short loc_18000C95B
0x18000c926  cmp     eax, 1
0x18000c929  jnz     short loc_18000C961
0x18000c92b  jmp     short loc_18000C95B
0x18000c92d  test    byte ptr [r15], 1
0x18000c931  jz      short loc_18000C94D
0x18000c933  mov     edx, 80h; dwFileAttributes
0x18000c938  mov     rcx, [rsi]; lpFileName
0x18000c93b  call    cs:__imp_SetFileAttributesW
0x18000c941  test    eax, eax
0x18000c943  jnz     short loc_18000C94D
0x18000c945  call    cs:__imp_GetLastError
0x18000c94b  jmp     short loc_18000C95B
0x18000c94d  xor     edx, edx; unsigned int
0x18000c94f  mov     rcx, [rsi]; lpString1
0x18000c952  call    ?SusDeleteFileRetryIfSharingViolation@@YAJPEB_WKPEAX@Z; SusDeleteFileRetryIfSharingViolation(wchar_t const *,ulong,void *)
0x18000c957  test    eax, eax
0x18000c959  jns     short loc_18000C961
0x18000c95b  mov     r12d, 1
0x18000c961  mov     rdx, r15; lpFindFileData
0x18000c964  mov     rcx, r14; hFindFile
0x18000c967  call    ?SusFindNextFile@@YAJPEAXPEAU_WIN32_FIND_DATAW@@@Z; SusFindNextFile(void *,_WIN32_FIND_DATAW *)
0x18000c96c  mov     edi, eax
0x18000c96e  xor     eax, eax
0x18000c970  test    edi, edi
0x18000c972  jns     loc_18000C8B2
0x18000c978  cmp     edi, 80070012h
0x18000c97e  mov     rbx, [rbp+37h+var_88]
0x18000c982  jnz     short loc_18000C98D
0x18000c984  mov     edi, eax
0x18000c986  test    r12d, r12d
0x18000c989  setnz   dil
0x18000c98d  mov     rax, [rsi]
0x18000c990  xor     esi, esi
0x18000c992  mov     [rax+r13*2], si
0x18000c997  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18000c99b  jz      short loc_18000C9A6
0x18000c99d  mov     rcx, r14; hFindFile
0x18000c9a0  call    cs:__imp_FindClose
0x18000c9a6  mov     [rbp+37h+var_80], 1
0x18000c9aa  mov     r9d, 1; dwBufferSize
0x18000c9b0  lea     r8, [rbp+37h+var_80]; lpFileInformation
0x18000c9b4  lea     edx, [r9+3]; FileInformationClass
0x18000c9b8  mov     rcx, rbx; hFile
0x18000c9bb  call    cs:__imp_SetFileInformationByHandle
0x18000c9c1  test    edi, edi
0x18000c9c3  jns     short loc_18000C9E7
0x18000c9c5  lea     rax, aSusdeletedirec_0; "SusDeleteDirectoryWorker failed"
0x18000c9cc  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax
0x18000c9d1  mov     [rsp+0F0h+dwCreationDisposition], edi
0x18000c9d5  xor     edx, edx
0x18000c9d7  xor     ecx, ecx
0x18000c9d9  lea     r9d, [rdx+1]
0x18000c9dd  lea     r8d, [rdx+20h]
0x18000c9e1  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18000c9e6  nop
0x18000c9e7  cmp     [rbp+37h+var_A0], sil
0x18000c9eb  jnz     short loc_18000C9FC
0x18000c9ed  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000c9f1  jz      short loc_18000C9FC
0x18000c9f3  mov     rcx, rbx; hObject
0x18000c9f6  call    cs:__imp_CloseHandle
0x18000c9fc  mov     eax, edi
0x18000c9fe  mov     rcx, [rbp+37h+var_40]
0x18000ca02  xor     rcx, rsp; StackCookie
0x18000ca05  call    __security_check_cookie
0x18000ca0a  mov     rbx, [rsp+0F0h+arg_10]
0x18000ca12  add     rsp, 0C0h
0x18000ca19  pop     r15
0x18000ca1b  pop     r14
0x18000ca1d  pop     r13
0x18000ca1f  pop     r12
0x18000ca21  pop     rdi
0x18000ca22  pop     rsi
0x18000ca23  pop     rbp
0x18000ca24  retn
```
