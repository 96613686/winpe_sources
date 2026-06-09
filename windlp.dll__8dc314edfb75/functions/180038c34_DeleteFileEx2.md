# DeleteFileEx2

- ea: `0x180038c34`
- end: `0x180039244`
- name: `DeleteFileEx2`
- size: `1552`
- prototype: `_BOOL8 __fastcall(__int64, char)`
- caller_count: `12`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18001455c`
- `0x18002877c`
- `0x180032518`
- `0x180033eb0`
- `0x180034fc8`
- `0x180038b44`
- `0x1800394a8`
- `0x180039a58`
- `0x18003a650`
- `0x18003a800`
- `0x18003aa98`
- `0x18003af20`

## callees

- `0x180001f24`
- `0x180038c34`
- `0x180039394`
- `0x180039424`
- `0x18003c0ec`
- `0x18003c464`
- `0x18003db20`
- `0x18007ed40`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x180038ef8`
- `ntdll!NtSetInformationFile` at `0x180038f32`
- `ntdll!NtSetInformationFile` at `0x180038f8d`
- `ntdll!NtSetInformationFile` at `0x180038ef8`
- `ntdll!NtSetInformationFile` at `0x180038f32`
- `ntdll!NtSetInformationFile` at `0x180038f8d`
- `ntdll!RtlNtStatusToDosError` at `0x180038f08`
- `ntdll!RtlNtStatusToDosError` at `0x180038f49`
- `ntdll!RtlNtStatusToDosError` at `0x180038f9d`
- `ntdll!RtlNtStatusToDosError` at `0x180038f08`
- `ntdll!RtlNtStatusToDosError` at `0x180038f49`
- `ntdll!RtlNtStatusToDosError` at `0x180038f9d`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180038d9a`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180038d9a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x180038e71`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x180038e71`
- `api-ms-win-core-file-l1-1-0!FindNextFileNameW` at `0x180038ea4`
- `api-ms-win-core-file-l1-1-0!FindNextFileNameW` at `0x180038ea4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180038ec8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180038ec8`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180038ddb`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18003903b`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180038ddb`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18003903b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180039161`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180039161`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038ccf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039013`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038ccf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039013`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038dff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038eae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800390db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039128`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003919b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800391d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038dff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038eae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800390db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039128`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003919b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800391d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038e12`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038e12`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038ebc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800390e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039136`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800391a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800391e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038ebc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800390e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039136`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800391a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800391e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039217`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039217`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038d21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039045`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003914b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003916b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038d21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039045`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003914b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003916b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039069`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003913f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039069`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003913f`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180038dba`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180038dba`

## string_xrefs

- `0x18003909a`: `DeleteFileEx: Will not restore attributes on hardlinks of [%s]`
- `0x180039071`: `DeleteFileEx: Unable to allocate hardlink path buffer`
- `0x180038d2a`: `DeleteFileEx: Unable to verify path redirection on [%s]; GLE = 0x%x`
- `0x18003904e`: `DeleteFileEx: Unable to restore attributes on [%s]; GLE = 0x%x`
- `0x180038fd6`: `DeleteFileEx: Trying to set back attributes on hardlink given: %s`
- `0x180038fb0`: `DeleteFileEx: Unable to remove [%s]; GLE = 0x%x`
- `0x180038f5a`: `DeleteFileEx: [%s] is in use; attempting POSIX delete`
- `0x180038d67`: `DeleteFileEx: Spoofing detected deleting [%s] -> [%s]`
- `0x180039106`: `DeleteFileEx: Unable to get information on [%s]; GLE = 0x%x`
- `0x1800390f7`: `DeleteFileEx: Unable to clear out attributes on [%s]; GLE = 0x%x`
- `0x1800390c3`: `DeleteFileEx: Unable to open [%s]; GLE = 0x%x`
- `0x18003917c`: `DeleteFileEx: Unable to open [%s]; GLE = 0x%x`
- `0x1800391f7`: `DeleteFileEx: Unable to form long path name for [%s]; GLE = 0x%x`
- `0x1800391ba`: `DeleteFileEx: Unable to prepare Unicode path for [%s]; GLE = 0x%x`
- `0x180039173`: `DeleteFileEx: Unable to delete [%s]; GLE = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_BOOL8 __fastcall DeleteFileEx2(__int64 a1, char a2)
{
  void *v4; // rax
  void *v5; // r15
  WCHAR *v6; // r14
  DWORD v7; // eax
  HANDLE FileW; // rax
  HANDLE v9; // rbx
  void *v10; // r13
  DWORD LastError; // edi
  DWORD v12; // r15d
  HANDLE ProcessHeap; // rax
  wchar_t *v14; // rax
  wchar_t *v15; // r15
  size_t v16; // rbx
  HANDLE FirstFileNameW; // rbx
  int v18; // eax
  HANDLE v19; // rax
  int v20; // eax
  ULONG v21; // eax
  int v22; // eax
  int v23; // eax
  HANDLE v24; // rax
  void *v25; // r12
  HANDLE v26; // rax
  DWORD v27; // eax
  const wchar_t *v28; // r8
  HANDLE v29; // rax
  DWORD v30; // eax
  const wchar_t *v31; // r8
  HANDLE v32; // rax
  HANDLE v33; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-B9h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-B9h]
  DWORD dwCreationDispositionb[2]; // [rsp+20h] [rbp-B9h]
  DWORD StringLength; // [rsp+40h] [rbp-99h] BYREF
  char v39[4]; // [rsp+44h] [rbp-95h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-91h] BYREF
  DWORD dwShareMode; // [rsp+50h] [rbp-89h]
  __int64 v42; // [rsp+58h] [rbp-81h]
  HANDLE FileHandle; // [rsp+60h] [rbp-79h]
  PWSTR LinkName; // [rsp+68h] [rbp-71h]
  LPVOID v45; // [rsp+70h] [rbp-69h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-61h] BYREF
  _OWORD v47[2]; // [rsp+88h] [rbp-51h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-31h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+B0h] [rbp-29h] BYREF

  v4 = (void *)FormLongPathName();
  v45 = v4;
  v5 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Unable to form long path name for [%s]; GLE = 0x%x", a1, LastError);
    goto LABEL_62;
  }
  v42 = 0;
  v6 = (WCHAR *)PrepareUnicodePathEx((STRSAFE_LPCWSTR)v4);
  if ( !v6 )
  {
    LastError = GetLastError();
    LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Unable to prepare Unicode path for [%s]; GLE = 0x%x", v5, LastError);
    goto LABEL_60;
  }
  v7 = 0;
  if ( (a2 & 1) == 0 )
    v7 = 7;
  dwShareMode = v7;
  FileW = CreateFileW(v6, 0x10180u, v7, 0, 3u, 0x2200000u, 0);
  FileHandle = FileW;
  v9 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    v10 = 0;
    StringLength = 1;
    LastError = 0;
    lpMem = 0;
    if ( (a2 & 0x20) != 0 )
    {
      if ( (unsigned int)VerifyPathRedirectionByHandle(FileW, v6, &StringLength, &lpMem) )
      {
        v12 = StringLength;
      }
      else
      {
        v12 = 0;
        dwCreationDisposition[0] = GetLastError();
        LastError = dwCreationDisposition[0];
        LibLog(
          &g_WdsLibLog,
          0x2000000,
          L"DeleteFileEx: Unable to verify path redirection on [%s]; GLE = 0x%x",
          v6,
          *(_QWORD *)dwCreationDisposition);
      }
      v10 = lpMem;
      if ( !v12 )
      {
        if ( !LastError )
        {
          LastError = 681;
          LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Spoofing detected deleting [%s] -> [%s]", v6, lpMem);
        }
        goto LABEL_49;
      }
    }
    memset(&FileInformation, 0, sizeof(FileInformation));
    v48 = 0;
    memset(v47, 0, sizeof(v47));
    if ( GetFileInformationByHandle(v9, &FileInformation) && GetFileInformationByHandleEx(v9, FileBasicInfo, v47, 0x28u) )
    {
      LODWORD(v48) = 0x2000;
      if ( SetFileInformationByHandle(v9, FileBasicInfo, v47, 0x28u) )
      {
        if ( v42 && FileInformation.nNumberOfLinks > 1 )
        {
          ProcessHeap = GetProcessHeap();
          v14 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, 0x10000u);
          v15 = v14;
          if ( v14 )
          {
            StringLength = 0;
            v16 = (unsigned int)((v42 - (__int64)v6) >> 1);
            StringCchCopyNW(v14, 0x8000u, v6, v16);
            LinkName = &v15[v16];
            lpMem = (LPVOID)(unsigned int)(0x8000 - v16);
            StringLength = 0x8000 - v16;
            FirstFileNameW = FindFirstFileNameW(v6, 0, &StringLength, LinkName);
            if ( FirstFileNameW != (HANDLE)-1LL )
            {
              while ( 1 )
              {
                v18 = wcsicmp_0(v15, v6);
                StringLength = (unsigned int)lpMem;
                if ( v18 )
                  break;
                if ( !FindNextFileNameW(FirstFileNameW, &StringLength, LinkName) )
                {
                  v19 = GetProcessHeap();
                  HeapFree(v19, 0, v15);
                  v15 = 0;
                  break;
                }
              }
              FindClose(FirstFileNameW);
            }
            v9 = FileHandle;
          }
          else
          {
            LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Unable to allocate hardlink path buffer");
          }
        }
        else
        {
          v15 = 0;
          if ( FileInformation.nNumberOfLinks > 1 )
            LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Will not restore attributes on hardlinks of [%s]", v6);
        }
        v39[0] = 1;
        IoStatusBlock = 0;
        v20 = NtSetInformationFile(v9, &IoStatusBlock, v39, 1u, FileDispositionInformation);
        if ( v20 >= 0 )
          goto LABEL_31;
        v21 = RtlNtStatusToDosError(v20);
        StringLength = 1;
        LastError = v21;
        v22 = NtSetInformationFile(v9, &IoStatusBlock, &StringLength, 4u, (FILE_INFORMATION_CLASS)64);
        if ( v22 < 0 )
        {
          if ( v22 == -1073741821 || (LastError = RtlNtStatusToDosError(v22), (a2 & 0x40) == 0) )
          {
LABEL_31:
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
            goto LABEL_33;
          }
          LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: [%s] is in use; attempting POSIX delete", v6);
          StringLength |= 2u;
          v23 = NtSetInformationFile(v9, &IoStatusBlock, &StringLength, 4u, (FILE_INFORMATION_CLASS)64);
          if ( v23 < 0 )
          {
            LastError = RtlNtStatusToDosError(v23);
            goto LABEL_31;
          }
        }
        LastError = 0;
LABEL_33:
        if ( v15 )
        {
          if ( (a2 & 4) == 0 )
            LibLog(&g_WdsLibLog, 0x4000000, L"DeleteFileEx: Trying to set back attributes on hardlink given: %s", v15);
          v24 = CreateFileW(v15, 0x100u, dwShareMode, 0, 3u, 0x2200000u, 0);
          v25 = v24;
          if ( v24 == (HANDLE)-1LL )
          {
            dwCreationDispositionb[0] = GetLastError();
            LibLog(
              &g_WdsLibLog,
              50331648,
              L"DeleteFileEx: Unable to open [%s]; GLE = 0x%x",
              v15,
              *(_QWORD *)dwCreationDispositionb);
          }
          else
          {
            LODWORD(v48) = FileInformation.dwFileAttributes;
            if ( !SetFileInformationByHandle(v24, FileBasicInfo, v47, 0x28u) )
            {
              dwCreationDispositionb[0] = GetLastError();
              LibLog(
                &g_WdsLibLog,
                50331648,
                L"DeleteFileEx: Unable to restore attributes on [%s]; GLE = 0x%x",
                v15,
                *(_QWORD *)dwCreationDispositionb);
            }
            CloseHandle(v25);
          }
          v26 = GetProcessHeap();
          HeapFree(v26, 0, v15);
        }
        goto LABEL_49;
      }
      v27 = GetLastError();
      v28 = L"DeleteFileEx: Unable to clear out attributes on [%s]; GLE = 0x%x";
    }
    else
    {
      v27 = GetLastError();
      v28 = L"DeleteFileEx: Unable to get information on [%s]; GLE = 0x%x";
    }
    dwCreationDisposition[0] = v27;
    LastError = v27;
    LibLog(&g_WdsLibLog, 50331648, v28, v6, *(_QWORD *)dwCreationDisposition);
LABEL_49:
    if ( v10 )
    {
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v10);
    }
    CloseHandle(v9);
    v5 = v45;
    goto LABEL_58;
  }
  v30 = GetLastError();
  LastError = v30;
  if ( v30 != 5 || (a2 & 0x20) != 0 )
  {
    v31 = L"DeleteFileEx: Unable to open [%s]; GLE = 0x%x";
    goto LABEL_57;
  }
  if ( !DeleteFileW(v6) )
  {
    v30 = GetLastError();
    LastError = v30;
    v31 = L"DeleteFileEx: Unable to delete [%s]; GLE = 0x%x";
LABEL_57:
    dwCreationDisposition[0] = v30;
    LibLog(&g_WdsLibLog, 50331648, v31, v6, *(_QWORD *)dwCreationDisposition);
  }
LABEL_58:
  v32 = GetProcessHeap();
  HeapFree(v32, 0, v6);
LABEL_60:
  v33 = GetProcessHeap();
  HeapFree(v33, 0, v5);
LABEL_62:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180038c34  push    rbp
0x180038c36  push    rbx
0x180038c37  push    rsi
0x180038c38  push    rdi
0x180038c39  push    r12
0x180038c3b  push    r13
0x180038c3d  push    r14
0x180038c3f  push    r15
0x180038c41  lea     rbp, [rsp-1Fh]
0x180038c46  sub     rsp, 0F8h
0x180038c4d  mov     rax, cs:__security_cookie
0x180038c54  xor     rax, rsp
0x180038c57  mov     [rbp+57h+var_48], rax
0x180038c5b  mov     r12d, edx
0x180038c5e  mov     rbx, rcx
0x180038c61  call    FormLongPathName
0x180038c66  mov     [rbp+57h+var_C0], rax
0x180038c6a  mov     r15, rax
0x180038c6d  test    rax, rax
0x180038c70  jz      loc_1800391EE
0x180038c76  lea     rdx, [rsp+130h+var_D8]
0x180038c7b  mov     [rsp+130h+var_D8], 0
0x180038c84  mov     rcx, rax; pszSrc
0x180038c87  call    PrepareUnicodePathEx
0x180038c8c  mov     r14, rax
0x180038c8f  test    rax, rax
0x180038c92  jz      loc_1800391B1
0x180038c98  xor     eax, eax
0x180038c9a  mov     [rsp+130h+hTemplateFile], 0; hTemplateFile
0x180038ca3  test    r12b, 1
0x180038ca7  mov     [rsp+130h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180038caf  mov     rcx, r14; lpFileName
0x180038cb2  mov     [rsp+130h+dwCreationDisposition], 3; dwCreationDisposition
0x180038cba  lea     edx, [rax+7]
0x180038cbd  cmovz   eax, edx
0x180038cc0  xor     r9d, r9d; lpSecurityAttributes
0x180038cc3  mov     r8d, eax; dwShareMode
0x180038cc6  mov     [rsp+130h+dwShareMode], eax
0x180038cca  mov     edx, 10180h; dwDesiredAccess
0x180038ccf  call    cs:__imp_CreateFileW
0x180038cd5  mov     [rbp+57h+FileHandle], rax
0x180038cd9  mov     rbx, rax
0x180038cdc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180038ce0  jz      loc_18003914B
0x180038ce6  xor     r13d, r13d
0x180038ce9  mov     [rsp+130h+StringLength], 1
0x180038cf1  xor     edi, edi
0x180038cf3  mov     [rsp+130h+lpMem], r13
0x180038cf8  lea     rsi, g_WdsLibLog
0x180038cff  test    r12b, 20h
0x180038d03  jz      short loc_180038D73
0x180038d05  lea     r9, [rsp+130h+lpMem]
0x180038d0a  mov     rdx, r14
0x180038d0d  lea     r8, [rsp+130h+StringLength]
0x180038d12  mov     rcx, rax
0x180038d15  call    VerifyPathRedirectionByHandle
0x180038d1a  test    eax, eax
0x180038d1c  jnz     short loc_180038D46
0x180038d1e  xor     r15d, r15d
0x180038d21  call    cs:__imp_GetLastError
0x180038d27  mov     r9, r14
0x180038d2a  lea     r8, aDeletefileexUn_5; "DeleteFileEx: Unable to verify path red"...
0x180038d31  mov     edx, 2000000h
0x180038d36  mov     [rsp+130h+dwCreationDisposition], eax
0x180038d3a  mov     rcx, rsi
0x180038d3d  mov     edi, eax
0x180038d3f  call    LibLog
0x180038d44  jmp     short loc_180038D4B
0x180038d46  mov     r15d, [rsp+130h+StringLength]
0x180038d4b  mov     r13, [rsp+130h+lpMem]
0x180038d50  test    r15d, r15d
0x180038d53  jnz     short loc_180038D73
0x180038d55  test    edi, edi
0x180038d57  jnz     loc_180039123
0x180038d5d  mov     edi, 2A9h
0x180038d62  mov     qword ptr [rsp+130h+dwCreationDisposition], r13
0x180038d67  lea     r8, aDeletefileexSp; "DeleteFileEx: Spoofing detected deletin"...
0x180038d6e  jmp     loc_180039113
0x180038d73  xorps   xmm0, xmm0
0x180038d76  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x180038d7a  xor     eax, eax
0x180038d7c  mov     rcx, rbx; hFile
0x180038d7f  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x180038d83  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x180038d86  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180038d8a  mov     [rbp+57h+var_88], rax
0x180038d8e  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x180038d92  movups  [rbp+57h+var_A8], xmm0
0x180038d96  movups  [rbp+57h+var_98], xmm0
0x180038d9a  call    cs:__imp_GetFileInformationByHandle
0x180038da0  test    eax, eax
0x180038da2  jz      loc_180039100
0x180038da8  mov     r15d, 28h ; '('
0x180038dae  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x180038db2  mov     r9d, r15d; dwBufferSize
0x180038db5  xor     edx, edx; FileInformationClass
0x180038db7  mov     rcx, rbx; hFile
0x180038dba  call    cs:__imp_GetFileInformationByHandleEx
0x180038dc0  test    eax, eax
0x180038dc2  jz      loc_180039100
0x180038dc8  mov     r9d, r15d; dwBufferSize
0x180038dcb  mov     dword ptr [rbp+57h+var_88], 2000h
0x180038dd2  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x180038dd6  xor     edx, edx; FileInformationClass
0x180038dd8  mov     rcx, rbx; hFile
0x180038ddb  call    cs:__imp_SetFileInformationByHandle
0x180038de1  test    eax, eax
0x180038de3  jz      loc_1800390F1
0x180038de9  cmp     [rsp+130h+var_D8], 0
0x180038def  jz      loc_18003908A
0x180038df5  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x180038df9  jbe     loc_18003908A
0x180038dff  call    cs:__imp_GetProcessHeap
0x180038e05  lea     edx, [r15-20h]; dwFlags
0x180038e09  mov     r8d, 10000h; dwBytes
0x180038e0f  mov     rcx, rax; hHeap
0x180038e12  call    cs:__imp_HeapAlloc
0x180038e18  mov     r15, rax
0x180038e1b  test    rax, rax
0x180038e1e  jz      loc_180039071
0x180038e24  mov     rcx, [rsp+130h+var_D8]
0x180038e29  mov     r8, r14; pszSrc
0x180038e2c  sub     rcx, r14
0x180038e2f  mov     [rsp+130h+StringLength], 0
0x180038e37  sar     rcx, 1
0x180038e3a  mov     edx, 8000h; cchDest
0x180038e3f  mov     ebx, ecx
0x180038e41  mov     r9d, ecx; cchToCopy
0x180038e44  mov     rcx, rax; pszDest
0x180038e47  call    StringCchCopyNW
0x180038e4c  lea     rcx, [r15+rbx*2]
0x180038e50  mov     eax, 8000h
0x180038e55  sub     eax, ebx
0x180038e57  mov     [rbp+57h+LinkName], rcx
0x180038e5b  mov     r9, rcx; LinkName
0x180038e5e  mov     [rsp+130h+lpMem], rax
0x180038e63  mov     rcx, r14; lpFileName
0x180038e66  mov     [rsp+130h+StringLength], eax
0x180038e6a  lea     r8, [rsp+130h+StringLength]; StringLength
0x180038e6f  xor     edx, edx; dwFlags
0x180038e71  call    cs:__imp_FindFirstFileNameW
0x180038e77  mov     rbx, rax
0x180038e7a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180038e7e  jz      short loc_180038ECE
0x180038e80  mov     rdx, r14; String2
0x180038e83  mov     rcx, r15; String1
0x180038e86  call    _wcsicmp_0
0x180038e8b  mov     rcx, [rsp+130h+lpMem]
0x180038e90  mov     [rsp+130h+StringLength], ecx
0x180038e94  test    eax, eax
0x180038e96  jnz     short loc_180038EC5
0x180038e98  mov     r8, [rbp+57h+LinkName]; LinkName
0x180038e9c  lea     rdx, [rsp+130h+StringLength]; StringLength
0x180038ea1  mov     rcx, rbx; hFindStream
0x180038ea4  call    cs:__imp_FindNextFileNameW
0x180038eaa  test    eax, eax
0x180038eac  jnz     short loc_180038E80
0x180038eae  call    cs:__imp_GetProcessHeap
0x180038eb4  mov     r8, r15; lpMem
0x180038eb7  xor     edx, edx; dwFlags
0x180038eb9  mov     rcx, rax; hHeap
0x180038ebc  call    cs:__imp_HeapFree
0x180038ec2  xor     r15d, r15d
0x180038ec5  mov     rcx, rbx; hFindFile
0x180038ec8  call    cs:__imp_FindClose
0x180038ece  mov     rbx, [rbp+57h+FileHandle]
0x180038ed2  xorps   xmm0, xmm0
0x180038ed5  mov     [rsp+130h+var_EC], 1
0x180038eda  mov     r9d, 1; Length
0x180038ee0  mov     [rsp+130h+dwCreationDisposition], 0Dh; FileInformationClass
0x180038ee8  lea     r8, [rsp+130h+var_EC]; FileInformation
0x180038eed  mov     rcx, rbx; FileHandle
0x180038ef0  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180038ef4  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180038ef8  call    cs:__imp_NtSetInformationFile
0x180038efe  test    eax, eax
0x180038f00  jns     loc_180038FA5
0x180038f06  mov     ecx, eax; Status
0x180038f08  call    cs:__imp_RtlNtStatusToDosError
0x180038f0e  mov     r9d, 4; Length
0x180038f14  mov     [rsp+130h+StringLength], 1
0x180038f1c  lea     r8, [rsp+130h+StringLength]; FileInformation
0x180038f21  mov     [rsp+130h+dwCreationDisposition], 40h ; '@'; FileInformationClass
0x180038f29  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180038f2d  mov     rcx, rbx; FileHandle
0x180038f30  mov     edi, eax
0x180038f32  call    cs:__imp_NtSetInformationFile
0x180038f38  test    eax, eax
0x180038f3a  jns     loc_1800390B3
0x180038f40  cmp     eax, 0C0000003h
0x180038f45  jz      short loc_180038FA5
0x180038f47  mov     ecx, eax; Status
0x180038f49  call    cs:__imp_RtlNtStatusToDosError
0x180038f4f  mov     edi, eax
0x180038f51  test    r12b, 40h
0x180038f55  jz      short loc_180038FA5
0x180038f57  mov     r9, r14
0x180038f5a  lea     r8, aDeletefileexSI; "DeleteFileEx: [%s] is in use; attemptin"...
0x180038f61  mov     edx, 3000000h
0x180038f66  mov     rcx, rsi
0x180038f69  call    LibLog
0x180038f6e  or      [rsp+130h+StringLength], 2
0x180038f73  lea     r8, [rsp+130h+StringLength]; FileInformation
0x180038f78  mov     r9d, 4; Length
0x180038f7e  mov     [rsp+130h+dwCreationDisposition], 40h ; '@'; FileInformationClass
0x180038f86  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180038f8a  mov     rcx, rbx; FileHandle
0x180038f8d  call    cs:__imp_NtSetInformationFile
0x180038f93  test    eax, eax
0x180038f95  jns     loc_1800390B3
0x180038f9b  mov     ecx, eax; Status
0x180038f9d  call    cs:__imp_RtlNtStatusToDosError
0x180038fa3  mov     edi, eax
0x180038fa5  test    edi, edi
0x180038fa7  jz      short loc_180038FC4
0x180038fa9  mov     r9, r14
0x180038fac  mov     [rsp+130h+dwCreationDisposition], edi
0x180038fb0  lea     r8, aDeletefileexUn_2; "DeleteFileEx: Unable to remove [%s]; GL"...
0x180038fb7  mov     edx, 3000000h
0x180038fbc  mov     rcx, rsi
0x180038fbf  call    LibLog
0x180038fc4  test    r15, r15
0x180038fc7  jz      loc_180039123
0x180038fcd  test    r12b, 4
0x180038fd1  jnz     short loc_180038FEA
0x180038fd3  mov     r9, r15
0x180038fd6  lea     r8, aDeletefileexTr; "DeleteFileEx: Trying to set back attrib"...
0x180038fdd  mov     edx, 4000000h
0x180038fe2  mov     rcx, rsi
0x180038fe5  call    LibLog
0x180038fea  mov     r8d, [rsp+130h+dwShareMode]; dwShareMode
0x180038fef  xor     r9d, r9d; lpSecurityAttributes
0x180038ff2  mov     [rsp+130h+hTemplateFile], 0; hTemplateFile
0x180038ffb  mov     edx, 100h; dwDesiredAccess
0x180039000  mov     [rsp+130h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180039008  mov     rcx, r15; lpFileName
0x18003900b  mov     [rsp+130h+dwCreationDisposition], 3; dwCreationDisposition
0x180039013  call    cs:__imp_CreateFileW
0x180039019  mov     r12, rax
0x18003901c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039020  jz      loc_1800390BA
0x180039026  mov     ecx, [rbp+57h+FileInformation.dwFileAttributes]
0x180039029  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x18003902d  mov     dword ptr [rbp+57h+var_88], ecx
0x180039030  mov     r9d, 28h ; '('; dwBufferSize
0x180039036  mov     rcx, rax; hFile
0x180039039  xor     edx, edx; FileInformationClass
0x18003903b  call    cs:__imp_SetFileInformationByHandle
0x180039041  test    eax, eax
0x180039043  jnz     short loc_180039066
0x180039045  call    cs:__imp_GetLastError
0x18003904b  mov     r9, r15
0x18003904e  lea     r8, aDeletefileexUn_0; "DeleteFileEx: Unable to restore attribu"...
0x180039055  mov     edx, 3000000h
0x18003905a  mov     [rsp+130h+dwCreationDisposition], eax
0x18003905e  mov     rcx, rsi
0x180039061  call    LibLog
0x180039066  mov     rcx, r12; hObject
0x180039069  call    cs:__imp_CloseHandle
0x18003906f  jmp     short loc_1800390DB
0x180039071  lea     r8, aDeletefileexUn_7; "DeleteFileEx: Unable to allocate hardli"...
0x180039078  mov     edx, 3000000h
0x18003907d  mov     rcx, rsi
0x180039080  call    LibLog
0x180039085  jmp     loc_180038ED2
0x18003908a  xor     r15d, r15d
0x18003908d  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x180039091  jbe     loc_180038ED2
0x180039097  mov     r9, r14
0x18003909a  lea     r8, aDeletefileexWi; "DeleteFileEx: Will not restore attribut"...
0x1800390a1  mov     edx, 3000000h
0x1800390a6  mov     rcx, rsi
0x1800390a9  call    LibLog
0x1800390ae  jmp     loc_180038ED2
0x1800390b3  xor     edi, edi
0x1800390b5  jmp     loc_180038FC4
0x1800390ba  call    cs:__imp_GetLastError
0x1800390c0  mov     r9, r15
0x1800390c3  lea     r8, aDeletefileexUn_4; "DeleteFileEx: Unable to open [%s]; GLE "...
0x1800390ca  mov     edx, 3000000h
0x1800390cf  mov     [rsp+130h+dwCreationDisposition], eax
0x1800390d3  mov     rcx, rsi
0x1800390d6  call    LibLog
0x1800390db  call    cs:__imp_GetProcessHeap
0x1800390e1  mov     r8, r15; lpMem
0x1800390e4  xor     edx, edx; dwFlags
0x1800390e6  mov     rcx, rax; hHeap
0x1800390e9  call    cs:__imp_HeapFree
0x1800390ef  jmp     short loc_180039123
0x1800390f1  call    cs:__imp_GetLastError
0x1800390f7  lea     r8, aDeletefileexUn; "DeleteFileEx: Unable to clear out attri"...
0x1800390fe  jmp     short loc_18003910D
0x180039100  call    cs:__imp_GetLastError
0x180039106  lea     r8, aDeletefileexUn_6; "DeleteFileEx: Unable to get information"...
0x18003910d  mov     [rsp+130h+dwCreationDisposition], eax
0x180039111  mov     edi, eax
0x180039113  mov     r9, r14
0x180039116  mov     edx, 3000000h
0x18003911b  mov     rcx, rsi
0x18003911e  call    LibLog
  ... truncated ...
```
