# TextLogRenameLogFile

- ea: `0x18001725c`
- end: `0x180017401`
- name: `TextLogRenameLogFile`
- size: `421`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x1800027a0`
- `0x1800056d0`
- `0x18000b160`

## callees

- `0x18000f520`
- `0x18000f82c`
- `0x180016d08`
- `0x180016dd4`
- `0x180016f7c`
- `0x18001725c`
- `0x180017500`
- `0x180018350`
- `0x180018668`
- `0x180018970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800173cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800173cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800172cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800172cf`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18001732b`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18001732b`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800173ad`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800173ad`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800173c3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800173c3`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x180017306`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x180017306`

## pseudocode

```c
__int64 __fastcall TextLogRenameLogFile(__int64 a1, __int64 a2, int a3)
{
  unsigned int v4; // ebx
  DWORD LastError; // edi
  int v6; // r15d
  int v7; // r14d
  int v8; // edx
  __int64 v9; // r8
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+30h] [rbp-278h] BYREF
  WCHAR FileName[264]; // [rsp+70h] [rbp-238h] BYREF

  v4 = 0;
  LastError = 0;
  v6 = 0;
  v7 = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( TextLogGetLogRenameFilename(*(_QWORD *)(a1 + 32), FileName, a3) )
  {
    v6 = 1;
  }
  else if ( !*(_DWORD *)(a1 + 48)
         || !(unsigned int)TextLogGenerateBackupLogFileName(*(STRSAFE_LPCWSTR *)(*(_QWORD *)(a1 + 32) + 16LL), FileName) )
  {
LABEL_4:
    LastError = GetLastError();
    goto LABEL_13;
  }
  if ( !CreateHardLinkW(FileName, *(LPCWSTR *)(*(_QWORD *)(a1 + 32) + 16LL), 0) )
    goto LABEL_4;
  v7 = 1;
  if ( v6 )
    TextLogDeletePendingRenameTag(a1);
  FlushFileBuffers(*(HANDLE *)a1);
  *(_DWORD *)(a1 + 44) = 0;
  pSetupUnmapFileAndSetEOF(*(HANDLE *)a1, *(HANDLE *)(a1 + 8), *(LPCVOID *)(a1 + 16));
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  if ( !pSetupDeleteFileByHandle(*(HANDLE *)a1) )
    goto LABEL_4;
  v7 = 0;
  if ( v6 )
    TextLogSetLogRenameFilename(*(_QWORD *)(a1 + 32));
  TextLogUnmapFile(a1);
  pSetupSetFileCompressionState(FileName, v8, v9);
LABEL_13:
  if ( v7
    && *(_QWORD *)a1 != -1
    && GetFileInformationByHandle(*(HANDLE *)a1, &FileInformation)
    && FileInformation.nNumberOfLinks > 1 )
  {
    DeleteFileW(FileName);
  }
  SetLastError(LastError);
  LOBYTE(v4) = LastError == 0;
  return v4;
}

```

## disassembly

```asm
0x18001725c  mov     [rsp+arg_8], rbx
0x180017261  mov     [rsp+arg_10], rsi
0x180017266  push    rdi
0x180017267  push    r14
0x180017269  push    r15
0x18001726b  sub     rsp, 290h
0x180017272  mov     rax, cs:__security_cookie
0x180017279  xor     rax, rsp
0x18001727c  mov     [rsp+2A8h+var_28], rax
0x180017284  mov     rsi, rcx
0x180017287  mov     [rsp+2A8h+var_280], rcx
0x18001728c  xor     ebx, ebx
0x18001728e  mov     edi, ebx
0x180017290  mov     r15d, ebx
0x180017293  mov     r14d, ebx
0x180017296  mov     [rsp+2A8h+var_284], ebx
0x18001729a  xorps   xmm0, xmm0
0x18001729d  xor     eax, eax
0x18001729f  movups  xmmword ptr [rsp+2A8h+FileInformation.dwFileAttributes], xmm0
0x1800172a4  movups  xmmword ptr [rsp+2A8h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800172a9  movups  xmmword ptr [rsp+2A8h+FileInformation.nFileSizeHigh], xmm0
0x1800172ae  mov     [rsp+2A8h+FileInformation.nFileIndexLow], eax
0x1800172b2  lea     rdx, [rsp+2A8h+FileName]
0x1800172b7  mov     rcx, [rcx+20h]
0x1800172bb  call    TextLogGetLogRenameFilename
0x1800172c0  test    eax, eax
0x1800172c2  jz      short loc_1800172CA
0x1800172c4  lea     r15d, [rbx+1]
0x1800172c8  jmp     short loc_1800172F6
0x1800172ca  cmp     [rsi+30h], ebx
0x1800172cd  jnz     short loc_1800172E0
0x1800172cf  call    cs:__imp_GetLastError
0x1800172d5  mov     edi, eax
0x1800172d7  mov     [rsp+2A8h+var_288], eax
0x1800172db  jmp     loc_180017383
0x1800172e0  mov     rcx, [rsi+20h]
0x1800172e4  lea     rdx, [rsp+2A8h+FileName]; pszDest
0x1800172e9  mov     rcx, [rcx+10h]; pszSrc
0x1800172ed  call    TextLogGenerateBackupLogFileName
0x1800172f2  test    eax, eax
0x1800172f4  jz      short loc_1800172CF
0x1800172f6  mov     rdx, [rsi+20h]
0x1800172fa  xor     r8d, r8d; lpSecurityAttributes
0x1800172fd  mov     rdx, [rdx+10h]; lpExistingFileName
0x180017301  lea     rcx, [rsp+2A8h+FileName]; lpFileName
0x180017306  call    cs:__imp_CreateHardLinkW
0x18001730c  test    eax, eax
0x18001730e  jz      short loc_1800172CF
0x180017310  mov     r14d, 1
0x180017316  mov     [rsp+2A8h+var_284], r14d
0x18001731b  test    r15d, r15d
0x18001731e  jz      short loc_180017328
0x180017320  mov     rcx, rsi
0x180017323  call    TextLogDeletePendingRenameTag
0x180017328  mov     rcx, [rsi]; hFile
0x18001732b  call    cs:__imp_FlushFileBuffers
0x180017331  mov     [rsi+2Ch], ebx
0x180017334  mov     r8, [rsi+10h]; lpBaseAddress
0x180017338  mov     rdx, [rsi+8]; hObject
0x18001733c  mov     rcx, [rsi]; hFile
0x18001733f  call    pSetupUnmapFileAndSetEOF
0x180017344  mov     [rsi+10h], rbx
0x180017348  mov     [rsi+8], rbx
0x18001734c  mov     rcx, [rsi]; FileHandle
0x18001734f  call    pSetupDeleteFileByHandle
0x180017354  test    eax, eax
0x180017356  jz      loc_1800172CF
0x18001735c  mov     r14d, ebx
0x18001735f  mov     [rsp+2A8h+var_284], ebx
0x180017363  test    r15d, r15d
0x180017366  jz      short loc_180017371
0x180017368  mov     rcx, [rsi+20h]
0x18001736c  call    TextLogSetLogRenameFilename
0x180017371  mov     rcx, rsi
0x180017374  call    TextLogUnmapFile
0x180017379  lea     rcx, [rsp+2A8h+FileName]
0x18001737e  call    pSetupSetFileCompressionState
0x180017383  jmp     short loc_18001739A
0x180017385  mov     edi, 54Fh
0x18001738a  mov     [rsp+2A8h+var_288], edi
0x18001738e  xor     ebx, ebx
0x180017390  mov     r14d, [rsp+2A8h+var_284]
0x180017395  mov     rsi, [rsp+2A8h+var_280]
0x18001739a  test    r14d, r14d
0x18001739d  jz      short loc_1800173C9
0x18001739f  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1800173a3  jz      short loc_1800173C9
0x1800173a5  lea     rdx, [rsp+2A8h+FileInformation]; lpFileInformation
0x1800173aa  mov     rcx, [rsi]; hFile
0x1800173ad  call    cs:__imp_GetFileInformationByHandle
0x1800173b3  test    eax, eax
0x1800173b5  jz      short loc_1800173C9
0x1800173b7  cmp     [rsp+2A8h+FileInformation.nNumberOfLinks], 1
0x1800173bc  jbe     short loc_1800173C9
0x1800173be  lea     rcx, [rsp+2A8h+FileName]; lpFileName
0x1800173c3  call    cs:__imp_DeleteFileW
0x1800173c9  mov     ecx, edi; dwErrCode
0x1800173cb  call    cs:__imp_SetLastError
0x1800173d1  test    edi, edi
0x1800173d3  setz    bl
0x1800173d6  mov     eax, ebx
0x1800173d8  mov     rcx, [rsp+2A8h+var_28]
0x1800173e0  xor     rcx, rsp; StackCookie
0x1800173e3  call    __security_check_cookie
0x1800173e8  lea     r11, [rsp+2A8h+var_18]
0x1800173f0  mov     rbx, [r11+28h]
0x1800173f4  mov     rsi, [r11+30h]
0x1800173f8  mov     rsp, r11
0x1800173fb  pop     r15
0x1800173fd  pop     r14
0x1800173ff  pop     rdi
0x180017400  retn
```
