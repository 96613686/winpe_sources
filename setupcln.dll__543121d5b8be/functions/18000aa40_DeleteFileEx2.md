# DeleteFileEx2

- ea: `0x18000aa40`
- end: `0x18000b03d`
- name: `DeleteFileEx2`
- size: `1533`
- prototype: `_BOOL8 __fastcall(__int64, char)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180007c44`
- `0x18000b230`
- `0x18000b348`
- `0x18000ba70`

## callees

- `0x180008f64`
- `0x1800095d0`
- `0x180009dd4`
- `0x18000a0f0`
- `0x18000aa40`
- `0x18000c580`
- `0x1800131e0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000ac8d`
- `msvcrt!_wcsicmp` at `0x18000ac8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b010`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aeb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aeea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000afaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000afe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aeb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aeea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000afaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000afe7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ac1a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ac1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ac07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000acb7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aed4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000afd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ac07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000acb7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aed4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000afd1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000acc5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aee2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000af2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000afa2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000afdf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000acc5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aee2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000af2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000afa2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000afdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aea4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aea4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af38`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000af5a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000af5a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000aadb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ae52`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000aadb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ae52`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18000aba2`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18000aba2`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x18000ac72`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x18000ac72`
- `api-ms-win-core-file-l1-1-0!FindNextFileNameW` at `0x18000acad`
- `api-ms-win-core-file-l1-1-0!FindNextFileNameW` at `0x18000acad`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000acd3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000acd3`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000abe3`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000ae76`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000abe3`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000ae76`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18000abc2`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18000abc2`
- `ntdll!RtlNtStatusToDosError` at `0x18000ad47`
- `ntdll!RtlNtStatusToDosError` at `0x18000ad88`
- `ntdll!RtlNtStatusToDosError` at `0x18000addc`
- `ntdll!RtlNtStatusToDosError` at `0x18000ad47`
- `ntdll!RtlNtStatusToDosError` at `0x18000ad88`
- `ntdll!RtlNtStatusToDosError` at `0x18000addc`
- `ntdll!NtSetInformationFile` at `0x18000ad37`
- `ntdll!NtSetInformationFile` at `0x18000ad71`
- `ntdll!NtSetInformationFile` at `0x18000adcc`
- `ntdll!NtSetInformationFile` at `0x18000ad37`
- `ntdll!NtSetInformationFile` at `0x18000ad71`
- `ntdll!NtSetInformationFile` at `0x18000adcc`

## string_xrefs

- `0x18000ab32`: `DeleteFileEx: Unable to verify path redirection on [%s]; GLE = 0x%x`
- `0x18000acdb`: `DeleteFileEx: Unable to allocate hardlink path buffer`
- `0x18000acfd`: `DeleteFileEx: Will not restore attributes on hardlinks of [%s]`
- `0x18000ad99`: `DeleteFileEx: [%s] is in use; attempting POSIX delete`
- `0x18000adef`: `DeleteFileEx: Unable to remove [%s]; GLE = 0x%x`
- `0x18000ae15`: `DeleteFileEx: Trying to set back attributes on hardlink given: %s`
- `0x18000ae89`: `DeleteFileEx: Unable to restore attributes on [%s]; GLE = 0x%x`
- `0x18000aebc`: `DeleteFileEx: Unable to open [%s]; GLE = 0x%x`
- `0x18000af75`: `DeleteFileEx: Unable to open [%s]; GLE = 0x%x`
- `0x18000aef0`: `DeleteFileEx: Unable to clear out attributes on [%s]; GLE = 0x%x`
- `0x18000aeff`: `DeleteFileEx: Unable to get information on [%s]; GLE = 0x%x`
- `0x18000ab6f`: `DeleteFileEx: Spoofing detected deleting [%s] -> [%s]`
- `0x18000af6c`: `DeleteFileEx: Unable to delete [%s]; GLE = 0x%x`
- `0x18000afb3`: `DeleteFileEx: Unable to prepare Unicode path for [%s]; GLE = 0x%x`
- `0x18000aff0`: `DeleteFileEx: Unable to form long path name for [%s]; GLE = 0x%x`

## pseudocode

```c
_BOOL8 __fastcall DeleteFileEx2(__int64 a1, char a2)
{
  void *v4; // rax
  void *v5; // r14
  WCHAR *v6; // rsi
  DWORD v7; // eax
  HANDLE FileW; // rax
  void *v9; // r13
  DWORD LastError; // ebx
  DWORD v11; // r14d
  int v12; // eax
  ULONG v13; // eax
  int v14; // eax
  int v15; // eax
  DWORD v16; // eax
  const wchar_t *v17; // r8
  DWORD v18; // eax
  const wchar_t *v19; // r8
  HANDLE ProcessHeap; // rax
  HANDLE v21; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-B9h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-B9h]
  DWORD StringLength; // [rsp+40h] [rbp-99h] BYREF
  char v26[4]; // [rsp+44h] [rbp-95h] BYREF
  HANDLE hFindStream; // [rsp+48h] [rbp-91h]
  DWORD dwShareMode; // [rsp+50h] [rbp-89h]
  __int64 v29; // [rsp+58h] [rbp-81h]
  LPVOID lpMem; // [rsp+70h] [rbp-69h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-61h] BYREF
  _OWORD v32[2]; // [rsp+88h] [rbp-51h] BYREF
  __int64 v33; // [rsp+A8h] [rbp-31h]
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+B0h] [rbp-29h] BYREF

  v4 = (void *)FormLongPathName();
  lpMem = v4;
  v5 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Unable to form long path name for [%s]; GLE = 0x%x", a1, LastError);
    goto LABEL_42;
  }
  v29 = 0;
  v6 = (WCHAR *)PrepareUnicodePathEx((STRSAFE_LPCWSTR)v4);
  if ( !v6 )
  {
    LastError = GetLastError();
    LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Unable to prepare Unicode path for [%s]; GLE = 0x%x", v5, LastError);
    goto LABEL_40;
  }
  v7 = 0;
  if ( (a2 & 1) == 0 )
    v7 = 7;
  dwShareMode = v7;
  FileW = CreateFileW(v6, 0x10180u, v7, 0, 3u, 0x2200000u, 0);
  v9 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v18 = GetLastError();
    LastError = v18;
    if ( v18 != 5 || (a2 & 0x20) != 0 )
    {
      v19 = L"DeleteFileEx: Unable to open [%s]; GLE = 0x%x";
    }
    else
    {
      if ( DeleteFileW(v6) )
        goto LABEL_38;
      v18 = GetLastError();
      LastError = v18;
      v19 = L"DeleteFileEx: Unable to delete [%s]; GLE = 0x%x";
    }
    dwCreationDisposition[0] = v18;
    LibLog(&g_WdsLibLog, 50331648, v19, v6, *(_QWORD *)dwCreationDisposition);
    goto LABEL_38;
  }
  StringLength = 1;
  LastError = 0;
  hFindStream = 0;
  if ( (a2 & 0x20) != 0 )
  {
    if ( (unsigned int)VerifyPathRedirectionByHandle(FileW, v6) )
    {
      v11 = StringLength;
    }
    else
    {
      v11 = 0;
      dwCreationDisposition[0] = GetLastError();
      LastError = dwCreationDisposition[0];
      LibLog(
        &g_WdsLibLog,
        0x2000000,
        L"DeleteFileEx: Unable to verify path redirection on [%s]; GLE = 0x%x",
        v6,
        *(_QWORD *)dwCreationDisposition);
    }
    if ( !v11 )
    {
      if ( !LastError )
      {
        LastError = 681;
        LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Spoofing detected deleting [%s] -> [%s]", v6, hFindStream);
      }
      goto LABEL_31;
    }
  }
  memset(&FileInformation, 0, sizeof(FileInformation));
  v33 = 0;
  memset(v32, 0, sizeof(v32));
  if ( !GetFileInformationByHandle(v9, &FileInformation) || !GetFileInformationByHandleEx(v9, FileBasicInfo, v32, 0x28u) )
  {
    v16 = GetLastError();
    v17 = L"DeleteFileEx: Unable to get information on [%s]; GLE = 0x%x";
    goto LABEL_30;
  }
  LODWORD(v33) = 0x2000;
  if ( !SetFileInformationByHandle(v9, FileBasicInfo, v32, 0x28u) )
  {
    v16 = GetLastError();
    v17 = L"DeleteFileEx: Unable to clear out attributes on [%s]; GLE = 0x%x";
LABEL_30:
    dwCreationDisposition[0] = v16;
    LastError = v16;
    LibLog(&g_WdsLibLog, 50331648, v17, v6, *(_QWORD *)dwCreationDisposition);
    goto LABEL_31;
  }
  if ( FileInformation.nNumberOfLinks > 1 )
    LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Will not restore attributes on hardlinks of [%s]", v6);
  v26[0] = 1;
  IoStatusBlock = 0;
  v12 = NtSetInformationFile(v9, &IoStatusBlock, v26, 1u, FileDispositionInformation);
  if ( v12 >= 0 )
    goto LABEL_24;
  v13 = RtlNtStatusToDosError(v12);
  StringLength = 1;
  LastError = v13;
  v14 = NtSetInformationFile(v9, &IoStatusBlock, &StringLength, 4u, (FILE_INFORMATION_CLASS)64);
  if ( v14 < 0 )
  {
    if ( v14 == -1073741821 || (LastError = RtlNtStatusToDosError(v14), (a2 & 0x40) == 0) )
    {
LABEL_24:
      if ( LastError )
      {
        dwCreationDispositiona[0] = LastError;
        LibLog(
          &g_WdsLibLog,
          50331648,
          L"DeleteFileEx: Unable to remove [%s]; GLE = 0x%x",
          v6,
          *(_QWORD *)dwCreationDispositiona);
      }
      goto LABEL_31;
    }
    LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: [%s] is in use; attempting POSIX delete", v6);
    StringLength |= 2u;
    v15 = NtSetInformationFile(v9, &IoStatusBlock, &StringLength, 4u, (FILE_INFORMATION_CLASS)64);
    if ( v15 < 0 )
    {
      LastError = RtlNtStatusToDosError(v15);
      goto LABEL_24;
    }
  }
  LastError = 0;
LABEL_31:
  CloseHandle(v9);
  v5 = lpMem;
LABEL_38:
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v6);
LABEL_40:
  v21 = GetProcessHeap();
  HeapFree(v21, 0, v5);
LABEL_42:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x18000aa40  push    rbp
0x18000aa42  push    rbx
0x18000aa43  push    rsi
0x18000aa44  push    rdi
0x18000aa45  push    r12
0x18000aa47  push    r13
0x18000aa49  push    r14
0x18000aa4b  push    r15
0x18000aa4d  lea     rbp, [rsp-1Fh]
0x18000aa52  sub     rsp, 0F8h
0x18000aa59  mov     rax, cs:__security_cookie
0x18000aa60  xor     rax, rsp
0x18000aa63  mov     [rbp+57h+var_48], rax
0x18000aa67  mov     r15d, edx
0x18000aa6a  mov     rdi, rcx
0x18000aa6d  call    FormLongPathName
0x18000aa72  mov     [rbp+57h+lpMem], rax
0x18000aa76  mov     r14, rax
0x18000aa79  test    rax, rax
0x18000aa7c  jz      loc_18000AFE7
0x18000aa82  lea     rdx, [rsp+130h+var_D8]
0x18000aa87  mov     [rsp+130h+var_D8], 0
0x18000aa90  mov     rcx, rax; pszSrc
0x18000aa93  call    PrepareUnicodePathEx
0x18000aa98  mov     rsi, rax
0x18000aa9b  test    rax, rax
0x18000aa9e  jz      loc_18000AFAA
0x18000aaa4  xor     eax, eax
0x18000aaa6  mov     [rsp+130h+hTemplateFile], 0; hTemplateFile
0x18000aaaf  test    r15b, 1
0x18000aab3  mov     [rsp+130h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18000aabb  mov     rcx, rsi; lpFileName
0x18000aabe  mov     [rsp+130h+dwCreationDisposition], 3; dwCreationDisposition
0x18000aac6  lea     edx, [rax+7]
0x18000aac9  cmovz   eax, edx
0x18000aacc  xor     r9d, r9d; lpSecurityAttributes
0x18000aacf  mov     r8d, eax; dwShareMode
0x18000aad2  mov     [rsp+130h+dwShareMode], eax
0x18000aad6  mov     edx, 10180h; dwDesiredAccess
0x18000aadb  call    cs:__imp_CreateFileW
0x18000aae1  mov     r13, rax
0x18000aae4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000aae8  jz      loc_18000AF44
0x18000aaee  xor     r12d, r12d
0x18000aaf1  mov     [rsp+130h+StringLength], 1
0x18000aaf9  xor     ebx, ebx
0x18000aafb  mov     [rsp+130h+hFindStream], r12
0x18000ab00  lea     rdi, g_WdsLibLog
0x18000ab07  test    r15b, 20h
0x18000ab0b  jz      short loc_18000AB7B
0x18000ab0d  lea     r9, [rsp+130h+hFindStream]
0x18000ab12  mov     rdx, rsi; lpFileName
0x18000ab15  lea     r8, [rsp+130h+StringLength]
0x18000ab1a  mov     rcx, rax; hFile
0x18000ab1d  call    VerifyPathRedirectionByHandle
0x18000ab22  test    eax, eax
0x18000ab24  jnz     short loc_18000AB4E
0x18000ab26  xor     r14d, r14d
0x18000ab29  call    cs:__imp_GetLastError
0x18000ab2f  mov     r9, rsi
0x18000ab32  lea     r8, aDeletefileexUn_5; "DeleteFileEx: Unable to verify path red"...
0x18000ab39  mov     edx, 2000000h
0x18000ab3e  mov     [rsp+130h+dwCreationDisposition], eax
0x18000ab42  mov     rcx, rdi
0x18000ab45  mov     ebx, eax
0x18000ab47  call    LibLog
0x18000ab4c  jmp     short loc_18000AB53
0x18000ab4e  mov     r14d, [rsp+130h+StringLength]
0x18000ab53  mov     r12, [rsp+130h+hFindStream]
0x18000ab58  test    r14d, r14d
0x18000ab5b  jnz     short loc_18000AB7B
0x18000ab5d  test    ebx, ebx
0x18000ab5f  jnz     loc_18000AF1C
0x18000ab65  mov     ebx, 2A9h
0x18000ab6a  mov     qword ptr [rsp+130h+dwCreationDisposition], r12
0x18000ab6f  lea     r8, aDeletefileexSp; "DeleteFileEx: Spoofing detected deletin"...
0x18000ab76  jmp     loc_18000AF0C
0x18000ab7b  xorps   xmm0, xmm0
0x18000ab7e  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x18000ab82  xor     eax, eax
0x18000ab84  mov     rcx, r13; hFile
0x18000ab87  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x18000ab8b  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x18000ab8e  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18000ab92  mov     [rbp+57h+var_88], rax
0x18000ab96  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x18000ab9a  movups  [rbp+57h+var_A8], xmm0
0x18000ab9e  movups  [rbp+57h+var_98], xmm0
0x18000aba2  call    cs:__imp_GetFileInformationByHandle
0x18000aba8  test    eax, eax
0x18000abaa  jz      loc_18000AEF9
0x18000abb0  mov     r14d, 28h ; '('
0x18000abb6  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x18000abba  mov     r9d, r14d; dwBufferSize
0x18000abbd  xor     edx, edx; FileInformationClass
0x18000abbf  mov     rcx, r13; hFile
0x18000abc2  call    cs:__imp_GetFileInformationByHandleEx
0x18000abc8  test    eax, eax
0x18000abca  jz      loc_18000AEF9
0x18000abd0  mov     r9d, r14d; dwBufferSize
0x18000abd3  mov     dword ptr [rbp+57h+var_88], 2000h
0x18000abda  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x18000abde  xor     edx, edx; FileInformationClass
0x18000abe0  mov     rcx, r13; hFile
0x18000abe3  call    cs:__imp_SetFileInformationByHandle
0x18000abe9  test    eax, eax
0x18000abeb  jz      loc_18000AEEA
0x18000abf1  cmp     [rsp+130h+var_D8], 0
0x18000abf7  jz      loc_18000ACF1
0x18000abfd  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x18000ac01  jbe     loc_18000ACF1
0x18000ac07  call    cs:__imp_GetProcessHeap
0x18000ac0d  lea     edx, [r14-20h]; dwFlags
0x18000ac11  mov     r8d, 10000h; dwBytes
0x18000ac17  mov     rcx, rax; hHeap
0x18000ac1a  call    cs:__imp_HeapAlloc
0x18000ac20  mov     r14, rax
0x18000ac23  test    rax, rax
0x18000ac26  jz      loc_18000ACDB
0x18000ac2c  mov     rcx, [rsp+130h+var_D8]
0x18000ac31  mov     r8, rsi; pszSrc
0x18000ac34  sub     rcx, rsi
0x18000ac37  mov     edx, 8000h; cchDest
0x18000ac3c  sar     rcx, 1
0x18000ac3f  mov     r11d, ecx
0x18000ac42  mov     r9d, ecx; cchToCopy
0x18000ac45  mov     rcx, rax; pszDest
0x18000ac48  call    StringCchCopyNW
0x18000ac4d  lea     rcx, [r14+r11*2]
0x18000ac51  mov     eax, 8000h
0x18000ac56  sub     eax, r11d
0x18000ac59  mov     [rbp+57h+LinkName], rcx
0x18000ac5d  mov     r9, rcx; LinkName
0x18000ac60  mov     [rbp+57h+var_D0], rax
0x18000ac64  mov     rcx, rsi; lpFileName
0x18000ac67  mov     [rsp+130h+StringLength], eax
0x18000ac6b  lea     r8, [rsp+130h+StringLength]; StringLength
0x18000ac70  xor     edx, edx; dwFlags
0x18000ac72  call    cs:__imp_FindFirstFileNameW
0x18000ac78  mov     [rsp+130h+hFindStream], rax
0x18000ac7d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ac81  jz      loc_18000AD11
0x18000ac87  mov     rdx, rsi; String2
0x18000ac8a  mov     rcx, r14; String1
0x18000ac8d  call    cs:__imp__wcsicmp
0x18000ac93  mov     rcx, [rbp+57h+var_D0]
0x18000ac97  mov     [rsp+130h+StringLength], ecx
0x18000ac9b  test    eax, eax
0x18000ac9d  jnz     short loc_18000ACCE
0x18000ac9f  mov     r8, [rbp+57h+LinkName]; LinkName
0x18000aca3  lea     rdx, [rsp+130h+StringLength]; StringLength
0x18000aca8  mov     rcx, [rsp+130h+hFindStream]; hFindStream
0x18000acad  call    cs:__imp_FindNextFileNameW
0x18000acb3  test    eax, eax
0x18000acb5  jnz     short loc_18000AC87
0x18000acb7  call    cs:__imp_GetProcessHeap
0x18000acbd  mov     r8, r14; lpMem
0x18000acc0  xor     edx, edx; dwFlags
0x18000acc2  mov     rcx, rax; hHeap
0x18000acc5  call    cs:__imp_HeapFree
0x18000accb  xor     r14d, r14d
0x18000acce  mov     rcx, [rsp+130h+hFindStream]; hFindFile
0x18000acd3  call    cs:__imp_FindClose
0x18000acd9  jmp     short loc_18000AD11
0x18000acdb  lea     r8, aDeletefileexUn_7; "DeleteFileEx: Unable to allocate hardli"...
0x18000ace2  mov     edx, 3000000h
0x18000ace7  mov     rcx, rdi
0x18000acea  call    LibLog
0x18000acef  jmp     short loc_18000AD11
0x18000acf1  xor     r14d, r14d
0x18000acf4  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x18000acf8  jbe     short loc_18000AD11
0x18000acfa  mov     r9, rsi
0x18000acfd  lea     r8, aDeletefileexWi; "DeleteFileEx: Will not restore attribut"...
0x18000ad04  mov     edx, 3000000h
0x18000ad09  mov     rcx, rdi
0x18000ad0c  call    LibLog
0x18000ad11  xorps   xmm0, xmm0
0x18000ad14  mov     [rsp+130h+var_EC], 1
0x18000ad19  mov     r9d, 1; Length
0x18000ad1f  mov     [rsp+130h+dwCreationDisposition], 0Dh; FileInformationClass
0x18000ad27  lea     r8, [rsp+130h+var_EC]; FileInformation
0x18000ad2c  mov     rcx, r13; FileHandle
0x18000ad2f  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000ad33  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000ad37  call    cs:__imp_NtSetInformationFile
0x18000ad3d  test    eax, eax
0x18000ad3f  jns     loc_18000ADE4
0x18000ad45  mov     ecx, eax; Status
0x18000ad47  call    cs:__imp_RtlNtStatusToDosError
0x18000ad4d  mov     r9d, 4; Length
0x18000ad53  mov     [rsp+130h+StringLength], 1
0x18000ad5b  lea     r8, [rsp+130h+StringLength]; FileInformation
0x18000ad60  mov     [rsp+130h+dwCreationDisposition], 40h ; '@'; FileInformationClass
0x18000ad68  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000ad6c  mov     rcx, r13; FileHandle
0x18000ad6f  mov     ebx, eax
0x18000ad71  call    cs:__imp_NtSetInformationFile
0x18000ad77  test    eax, eax
0x18000ad79  jns     loc_18000AEAC
0x18000ad7f  cmp     eax, 0C0000003h
0x18000ad84  jz      short loc_18000ADE4
0x18000ad86  mov     ecx, eax; Status
0x18000ad88  call    cs:__imp_RtlNtStatusToDosError
0x18000ad8e  mov     ebx, eax
0x18000ad90  test    r15b, 40h
0x18000ad94  jz      short loc_18000ADE4
0x18000ad96  mov     r9, rsi
0x18000ad99  lea     r8, aDeletefileexSI; "DeleteFileEx: [%s] is in use; attemptin"...
0x18000ada0  mov     edx, 3000000h
0x18000ada5  mov     rcx, rdi
0x18000ada8  call    LibLog
0x18000adad  or      [rsp+130h+StringLength], 2
0x18000adb2  lea     r8, [rsp+130h+StringLength]; FileInformation
0x18000adb7  mov     r9d, 4; Length
0x18000adbd  mov     [rsp+130h+dwCreationDisposition], 40h ; '@'; FileInformationClass
0x18000adc5  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000adc9  mov     rcx, r13; FileHandle
0x18000adcc  call    cs:__imp_NtSetInformationFile
0x18000add2  test    eax, eax
0x18000add4  jns     loc_18000AEAC
0x18000adda  mov     ecx, eax; Status
0x18000addc  call    cs:__imp_RtlNtStatusToDosError
0x18000ade2  mov     ebx, eax
0x18000ade4  test    ebx, ebx
0x18000ade6  jz      short loc_18000AE03
0x18000ade8  mov     r9, rsi
0x18000adeb  mov     [rsp+130h+dwCreationDisposition], ebx
0x18000adef  lea     r8, aDeletefileexUn_2; "DeleteFileEx: Unable to remove [%s]; GL"...
0x18000adf6  mov     edx, 3000000h
0x18000adfb  mov     rcx, rdi
0x18000adfe  call    LibLog
0x18000ae03  test    r14, r14
0x18000ae06  jz      loc_18000AF1C
0x18000ae0c  test    r15b, 4
0x18000ae10  jnz     short loc_18000AE29
0x18000ae12  mov     r9, r14
0x18000ae15  lea     r8, aDeletefileexTr; "DeleteFileEx: Trying to set back attrib"...
0x18000ae1c  mov     edx, 4000000h
0x18000ae21  mov     rcx, rdi
0x18000ae24  call    LibLog
0x18000ae29  mov     r8d, [rsp+130h+dwShareMode]; dwShareMode
0x18000ae2e  xor     r9d, r9d; lpSecurityAttributes
0x18000ae31  mov     [rsp+130h+hTemplateFile], 0; hTemplateFile
0x18000ae3a  mov     edx, 100h; dwDesiredAccess
0x18000ae3f  mov     [rsp+130h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18000ae47  mov     rcx, r14; lpFileName
0x18000ae4a  mov     [rsp+130h+dwCreationDisposition], 3; dwCreationDisposition
0x18000ae52  call    cs:__imp_CreateFileW
0x18000ae58  mov     r15, rax
0x18000ae5b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ae5f  jz      short loc_18000AEB3
0x18000ae61  mov     ecx, [rbp+57h+FileInformation.dwFileAttributes]
0x18000ae64  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x18000ae68  mov     dword ptr [rbp+57h+var_88], ecx
0x18000ae6b  mov     r9d, 28h ; '('; dwBufferSize
0x18000ae71  mov     rcx, rax; hFile
0x18000ae74  xor     edx, edx; FileInformationClass
0x18000ae76  call    cs:__imp_SetFileInformationByHandle
0x18000ae7c  test    eax, eax
0x18000ae7e  jnz     short loc_18000AEA1
0x18000ae80  call    cs:__imp_GetLastError
0x18000ae86  mov     r9, r14
0x18000ae89  lea     r8, aDeletefileexUn_0; "DeleteFileEx: Unable to restore attribu"...
0x18000ae90  mov     edx, 3000000h
0x18000ae95  mov     [rsp+130h+dwCreationDisposition], eax
0x18000ae99  mov     rcx, rdi
0x18000ae9c  call    LibLog
0x18000aea1  mov     rcx, r15; hObject
0x18000aea4  call    cs:__imp_CloseHandle
0x18000aeaa  jmp     short loc_18000AED4
0x18000aeac  xor     ebx, ebx
0x18000aeae  jmp     loc_18000AE03
0x18000aeb3  call    cs:__imp_GetLastError
0x18000aeb9  mov     r9, r14
0x18000aebc  lea     r8, aDeletefileexUn_4; "DeleteFileEx: Unable to open [%s]; GLE "...
0x18000aec3  mov     edx, 3000000h
0x18000aec8  mov     [rsp+130h+dwCreationDisposition], eax
0x18000aecc  mov     rcx, rdi
0x18000aecf  call    LibLog
0x18000aed4  call    cs:__imp_GetProcessHeap
0x18000aeda  mov     r8, r14; lpMem
0x18000aedd  xor     edx, edx; dwFlags
0x18000aedf  mov     rcx, rax; hHeap
0x18000aee2  call    cs:__imp_HeapFree
0x18000aee8  jmp     short loc_18000AF1C
0x18000aeea  call    cs:__imp_GetLastError
0x18000aef0  lea     r8, aDeletefileexUn; "DeleteFileEx: Unable to clear out attri"...
0x18000aef7  jmp     short loc_18000AF06
0x18000aef9  call    cs:__imp_GetLastError
0x18000aeff  lea     r8, aDeletefileexUn_6; "DeleteFileEx: Unable to get information"...
0x18000af06  mov     [rsp+130h+dwCreationDisposition], eax
0x18000af0a  mov     ebx, eax
0x18000af0c  mov     r9, rsi
0x18000af0f  mov     edx, 3000000h
0x18000af14  mov     rcx, rdi
0x18000af17  call    LibLog
0x18000af1c  test    r12, r12
0x18000af1f  jz      short loc_18000AF35
0x18000af21  call    cs:__imp_GetProcessHeap
  ... truncated ...
```
