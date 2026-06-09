# CVersionManagerServer::_DebugDownload(_FILETIME *,_FILETIME *)

- ea: `0x180101a3c`
- end: `0x180101fe6`
- name: `?_DebugDownload@CVersionManagerServer@@AEAAJPEAU_FILETIME@@0@Z`
- size: `1450`
- prototype: `__int64 __fastcall(CVersionManagerServer *this, struct _FILETIME *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x180104008`

## callees

- `0x18004d7f0`
- `0x18005789c`
- `0x1801018e0`
- `0x180101a3c`
- `0x1801044f8`
- `0x18012738c`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101ba3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101de8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101e7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101eae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101f29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101f55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101ba3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101de8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101e7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101eae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101f29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101f55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180101f47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180101f47`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180101dbd`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180101dbd`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180101af2`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180101beb`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180101af2`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180101beb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180101e9d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180101e9d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180101ef9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180101ef9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180101dda`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180101dda`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180101e64`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180101e64`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180101b0f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180101c07`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180101b0f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180101c07`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x180101b44`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x180101c3c`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x180101b44`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x180101c3c`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x180101b93`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x180101c8f`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x180101b93`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x180101c8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180101f75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180101f84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180101f95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180101fa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180101f75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180101f84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180101f95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180101fa6`

## pseudocode

```c
__int64 __fastcall CVersionManagerServer::_DebugDownload(
        CVersionManagerServer *this,
        struct _FILETIME *a2,
        struct _FILETIME *a3)
{
  char *v5; // r15
  char v6; // di
  CVersionManagerServer *v7; // rcx
  int String; // ebx
  CVersionManagerServer *v9; // rcx
  signed int LastError; // eax
  int v11; // eax
  CVersionManagerServer *v12; // rcx
  CVersionManagerServer *v13; // rcx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  char *v17; // r8
  int v18; // eax
  __int64 v19; // rdi
  size_t v20; // rdx
  DWORD FileAttributesW; // ebx
  DWORD v22; // eax
  CVersionManagerServer *v23; // rcx
  HANDLE FileW; // rsi
  signed int v25; // eax
  signed int v26; // eax
  signed int v27; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  char *v30; // [rsp+48h] [rbp-B8h] BYREF
  char *v31; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v32; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v33; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v34; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+70h] [rbp-90h] BYREF
  char *v37; // [rsp+78h] [rbp-88h] BYREF
  FILETIME FileTime; // [rsp+80h] [rbp-80h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+88h] [rbp-78h] BYREF
  SYSTEMTIME Date; // [rsp+98h] [rbp-68h] BYREF
  char v41[272]; // [rsp+B0h] [rbp-50h] BYREF
  char Buffer[272]; // [rsp+1C0h] [rbp+C0h] BYREF
  WCHAR pszPath[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR DateStr[264]; // [rsp+4E0h] [rbp+3E0h] BYREF
  WCHAR TimeStr[264]; // [rsp+6F0h] [rbp+5F0h] BYREF
  WCHAR lpDateStr[264]; // [rsp+900h] [rbp+800h] BYREF
  WCHAR v47[264]; // [rsp+B10h] [rbp+A10h] BYREF

  if ( a2 && a3 )
  {
    v5 = 0;
    LocalFileTime = 0;
    FileTime = 0;
    pv = 0;
    SystemTime = 0;
    NumberOfBytesWritten = 0;
    Date = 0;
    v37 = 0;
    v32 = 0;
    v30 = 0;
    v33 = 0;
    v31 = 0;
    v34 = 0;
    if ( a2->dwHighDateTime || a2->dwLowDateTime )
    {
      if ( !FileTimeToLocalFileTime(a2, &LocalFileTime)
        || !FileTimeToSystemTime(&LocalFileTime, &SystemTime)
        || !GetDateFormatW(0x400u, 1u, &SystemTime, 0, DateStr, 260) )
      {
        goto LABEL_11;
      }
      String = CVersionManagerServer::_WideToAnsi(v7, DateStr, &pv, &NumberOfBytesWritten);
      if ( String < 0 )
        goto LABEL_60;
      if ( GetTimeFormatW(0x400u, 0, &SystemTime, 0, TimeStr, 260) )
      {
        v11 = CVersionManagerServer::_WideToAnsi(v9, TimeStr, (LPVOID *)&v37, &v32);
        v5 = v37;
        String = v11;
      }
      else
      {
LABEL_11:
        LastError = GetLastError();
        String = LastError;
        if ( LastError > 0 )
          String = (unsigned __int16)LastError | 0x80070000;
      }
      v6 = 1;
      if ( String < 0 )
        goto LABEL_60;
    }
    else
    {
      v6 = 0;
    }
    if ( !FileTimeToLocalFileTime(a3, &FileTime)
      || !FileTimeToSystemTime(&FileTime, &Date)
      || !GetDateFormatW(0x400u, 1u, &Date, 0, lpDateStr, 260) )
    {
      goto LABEL_58;
    }
    String = CVersionManagerServer::_WideToAnsi(v12, lpDateStr, (LPVOID *)&v30, &v33);
    if ( String < 0 )
      goto LABEL_60;
    if ( !GetTimeFormatW(0x400u, 0, &Date, 0, v47, 260) )
      goto LABEL_58;
    String = CVersionManagerServer::_WideToAnsi(v13, v47, (LPVOID *)&v31, &v34);
    if ( String < 0 )
    {
LABEL_60:
      CoTaskMemFree(pv);
      CoTaskMemFree(v5);
      CoTaskMemFree(v30);
      CoTaskMemFree(v31);
      return (unsigned int)String;
    }
    v14 = *((_DWORD *)this + 420);
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( v15 )
      {
        v16 = v15 - 1;
        if ( v16 )
        {
          if ( v16 != 1 )
          {
LABEL_30:
            if ( v6 )
              v18 = StringCchPrintfA(Buffer, 0x104u, "%s,%s %s, %s %s\r\n", v41, v5, (const char *)pv, v31, v30);
            else
              v18 = StringCchPrintfA(Buffer, 0x104u, "%s,Never, %s %s\r\n", v41, v31, v30);
            String = v18;
            if ( v18 < 0 )
              goto LABEL_60;
            String = GetString(
                       (__int64)SettingStore::IEVALUE_urlmon_ExtVerDebugDownloadFilePath[0],
                       (__int64)pszPath,
                       0x104u);
            if ( String < 0 )
              goto LABEL_60;
            v19 = -1;
            v20 = -1;
            do
              ++v20;
            while ( pszPath[v20] );
            String = PathCchRemoveFileSpec(pszPath, v20);
            if ( String < 0 )
              goto LABEL_60;
            FileAttributesW = GetFileAttributesW(pszPath);
            v22 = GetLastError();
            if ( FileAttributesW == -1 )
            {
              if ( v22 == 2 )
              {
                String = CVersionManagerServer::_CreateLocalDirectory(v23, pszPath);
                if ( String < 0 )
                  goto LABEL_60;
              }
            }
            else if ( (FileAttributesW & 0x10) == 0 )
            {
              String = -2147024735;
              goto LABEL_60;
            }
            String = GetString(
                       (__int64)SettingStore::IEVALUE_urlmon_ExtVerDebugDownloadFilePath[0],
                       (__int64)pszPath,
                       0x104u);
            if ( String >= 0 )
            {
              FileW = CreateFileW(pszPath, 0x40000000u, 3u, 0, 4u, 0x80u, 0);
              if ( FileW != (HANDLE)-1LL )
              {
                if ( GetLastError() != 183 || SetFilePointer(FileW, 0, 0, 2u) != -1 )
                  goto LABEL_48;
                v25 = GetLastError();
                String = v25;
                if ( v25 > 0 )
                  String = (unsigned __int16)v25 | 0x80070000;
                if ( String >= 0 )
                {
LABEL_48:
                  NumberOfBytesWritten = 0;
                  do
                    ++v19;
                  while ( Buffer[v19] );
                  if ( WriteFile(FileW, Buffer, v19, &NumberOfBytesWritten, 0) )
                  {
                    if ( NumberOfBytesWritten != v19 )
                      String = -2147024867;
                  }
                  else
                  {
                    v26 = GetLastError();
                    String = v26;
                    if ( v26 > 0 )
                      String = (unsigned __int16)v26 | 0x80070000;
                  }
                }
                CloseHandle(FileW);
                goto LABEL_60;
              }
LABEL_58:
              v27 = GetLastError();
              String = v27;
              if ( v27 > 0 )
                String = (unsigned __int16)v27 | 0x80070000;
              goto LABEL_60;
            }
            goto LABEL_60;
          }
          v17 = "Fail";
        }
        else
        {
          v17 = "NotNew";
        }
      }
      else
      {
        v17 = "Success";
      }
    }
    else
    {
      v17 = "Never";
    }
    String = StringCchCopyA(v41, 0x104u, v17);
    if ( String < 0 )
      goto LABEL_60;
    goto LABEL_30;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180101a3c  mov     [rsp-8+arg_0], rbx
0x180101a41  push    rbp
0x180101a42  push    rsi
0x180101a43  push    rdi
0x180101a44  push    r12
0x180101a46  push    r13
0x180101a48  push    r14
0x180101a4a  push    r15
0x180101a4c  lea     rbp, [rsp-0C30h]
0x180101a54  sub     rsp, 0D30h
0x180101a5b  mov     rax, cs:__security_cookie
0x180101a62  xor     rax, rsp
0x180101a65  mov     [rbp+0C60h+var_40], rax
0x180101a6c  xor     r12d, r12d
0x180101a6f  mov     rsi, r8
0x180101a72  mov     rax, rdx
0x180101a75  mov     r14, rcx
0x180101a78  test    rdx, rdx
0x180101a7b  jz      loc_180101FB6
0x180101a81  test    r8, r8
0x180101a84  jz      loc_180101FB6
0x180101a8a  xorps   xmm0, xmm0
0x180101a8d  xorps   xmm1, xmm1
0x180101a90  mov     r15d, r12d
0x180101a93  mov     qword ptr [rsp+0D60h+LocalFileTime.dwLowDateTime], r12
0x180101a98  mov     edi, 80070000h
0x180101a9d  mov     qword ptr [rbp+0C60h+FileTime.dwLowDateTime], r12
0x180101aa1  mov     r13d, 104h
0x180101aa7  mov     [rsp+0D60h+pv], r12
0x180101aac  movups  xmmword ptr [rbp+0C60h+SystemTime.wYear], xmm0
0x180101ab0  mov     [rsp+0D60h+NumberOfBytesWritten], r12d
0x180101ab5  movups  xmmword ptr [rbp+0C60h+Date.wYear], xmm1
0x180101ab9  mov     [rsp+0D60h+var_CE8], r12
0x180101abe  mov     [rsp+0D60h+var_D08], r12d
0x180101ac3  mov     [rsp+0D60h+var_D18], r12
0x180101ac8  mov     [rsp+0D60h+var_D04], r12d
0x180101acd  mov     [rsp+0D60h+var_D10], r12
0x180101ad2  mov     [rsp+0D60h+var_D00], r12d
0x180101ad7  cmp     [rdx+4], r12d
0x180101adb  jnz     short loc_180101AEA
0x180101add  cmp     [rdx], r12d
0x180101ae0  jnz     short loc_180101AEA
0x180101ae2  mov     dil, r12b
0x180101ae5  jmp     loc_180101BE4
0x180101aea  lea     rdx, [rsp+0D60h+LocalFileTime]; lpLocalFileTime
0x180101aef  mov     rcx, rax; lpFileTime
0x180101af2  call    cs:__imp_FileTimeToLocalFileTime
0x180101af9  nop     dword ptr [rax+rax+00h]
0x180101afe  test    eax, eax
0x180101b00  jz      loc_180101BA3
0x180101b06  lea     rdx, [rbp+0C60h+SystemTime]; lpSystemTime
0x180101b0a  lea     rcx, [rsp+0D60h+LocalFileTime]; lpFileTime
0x180101b0f  call    cs:__imp_FileTimeToSystemTime
0x180101b16  nop     dword ptr [rax+rax+00h]
0x180101b1b  test    eax, eax
0x180101b1d  jz      loc_180101BA3
0x180101b23  xor     r9d, r9d; lpFormat
0x180101b26  mov     [rsp+0D60h+cchDate], r13d; cchDate
0x180101b2b  lea     rax, [rbp+0C60h+DateStr]
0x180101b32  mov     ecx, 400h; Locale
0x180101b37  lea     r8, [rbp+0C60h+SystemTime]; lpDate
0x180101b3b  mov     [rsp+0D60h+lpDateStr], rax; lpDateStr
0x180101b40  lea     edx, [r9+1]; dwFlags
0x180101b44  call    cs:__imp_GetDateFormatW
0x180101b4b  nop     dword ptr [rax+rax+00h]
0x180101b50  test    eax, eax
0x180101b52  jz      short loc_180101BA3
0x180101b54  lea     r9, [rsp+0D60h+NumberOfBytesWritten]; unsigned int *
0x180101b59  lea     r8, [rsp+0D60h+pv]; char **
0x180101b5e  lea     rdx, [rbp+0C60h+DateStr]; unsigned __int16 *
0x180101b65  call    ?_WideToAnsi@CVersionManagerServer@@AEAAJPEBGPEAPEADPEAK@Z; CVersionManagerServer::_WideToAnsi(ushort const *,char * *,ulong *)
0x180101b6a  mov     ebx, eax
0x180101b6c  test    eax, eax
0x180101b6e  js      loc_180101F70
0x180101b74  lea     rax, [rbp+0C60h+TimeStr]
0x180101b7b  mov     [rsp+0D60h+cchDate], r13d; cchTime
0x180101b80  xor     r9d, r9d; lpFormat
0x180101b83  mov     [rsp+0D60h+lpDateStr], rax; lpTimeStr
0x180101b88  lea     r8, [rbp+0C60h+SystemTime]; lpTime
0x180101b8c  xor     edx, edx; dwFlags
0x180101b8e  mov     ecx, 400h; Locale
0x180101b93  call    cs:__imp_GetTimeFormatW
0x180101b9a  nop     dword ptr [rax+rax+00h]
0x180101b9f  test    eax, eax
0x180101ba1  jnz     short loc_180101BBC
0x180101ba3  call    cs:__imp_GetLastError
0x180101baa  nop     dword ptr [rax+rax+00h]
0x180101baf  mov     ebx, eax
0x180101bb1  test    eax, eax
0x180101bb3  jle     short loc_180101BD9
0x180101bb5  movzx   ebx, ax
0x180101bb8  or      ebx, edi
0x180101bba  jmp     short loc_180101BD9
0x180101bbc  lea     r9, [rsp+0D60h+var_D08]; unsigned int *
0x180101bc1  lea     r8, [rsp+0D60h+var_CE8]; char **
0x180101bc6  lea     rdx, [rbp+0C60h+TimeStr]; unsigned __int16 *
0x180101bcd  call    ?_WideToAnsi@CVersionManagerServer@@AEAAJPEBGPEAPEADPEAK@Z; CVersionManagerServer::_WideToAnsi(ushort const *,char * *,ulong *)
0x180101bd2  mov     r15, [rsp+0D60h+var_CE8]
0x180101bd7  mov     ebx, eax
0x180101bd9  mov     dil, 1
0x180101bdc  test    ebx, ebx
0x180101bde  js      loc_180101F70
0x180101be4  lea     rdx, [rbp+0C60h+FileTime]; lpLocalFileTime
0x180101be8  mov     rcx, rsi; lpFileTime
0x180101beb  call    cs:__imp_FileTimeToLocalFileTime
0x180101bf2  nop     dword ptr [rax+rax+00h]
0x180101bf7  test    eax, eax
0x180101bf9  jz      loc_180101F55
0x180101bff  lea     rdx, [rbp+0C60h+Date]; lpSystemTime
0x180101c03  lea     rcx, [rbp+0C60h+FileTime]; lpFileTime
0x180101c07  call    cs:__imp_FileTimeToSystemTime
0x180101c0e  nop     dword ptr [rax+rax+00h]
0x180101c13  test    eax, eax
0x180101c15  jz      loc_180101F55
0x180101c1b  xor     r9d, r9d; lpFormat
0x180101c1e  mov     [rsp+0D60h+cchDate], r13d; cchDate
0x180101c23  lea     rax, [rbp+0C60h+var_460]
0x180101c2a  mov     ecx, 400h; Locale
0x180101c2f  lea     r8, [rbp+0C60h+Date]; lpDate
0x180101c33  mov     [rsp+0D60h+lpDateStr], rax; lpDateStr
0x180101c38  lea     edx, [r9+1]; dwFlags
0x180101c3c  call    cs:__imp_GetDateFormatW
0x180101c43  nop     dword ptr [rax+rax+00h]
0x180101c48  test    eax, eax
0x180101c4a  jz      loc_180101F55
0x180101c50  lea     r9, [rsp+0D60h+var_D04]; unsigned int *
0x180101c55  lea     r8, [rsp+0D60h+var_D18]; char **
0x180101c5a  lea     rdx, [rbp+0C60h+var_460]; unsigned __int16 *
0x180101c61  call    ?_WideToAnsi@CVersionManagerServer@@AEAAJPEBGPEAPEADPEAK@Z; CVersionManagerServer::_WideToAnsi(ushort const *,char * *,ulong *)
0x180101c66  mov     ebx, eax
0x180101c68  test    eax, eax
0x180101c6a  js      loc_180101F70
0x180101c70  lea     rax, [rbp+0C60h+var_250]
0x180101c77  mov     [rsp+0D60h+cchDate], r13d; cchTime
0x180101c7c  xor     r9d, r9d; lpFormat
0x180101c7f  mov     [rsp+0D60h+lpDateStr], rax; lpTimeStr
0x180101c84  lea     r8, [rbp+0C60h+Date]; lpTime
0x180101c88  xor     edx, edx; dwFlags
0x180101c8a  mov     ecx, 400h; Locale
0x180101c8f  call    cs:__imp_GetTimeFormatW
0x180101c96  nop     dword ptr [rax+rax+00h]
0x180101c9b  test    eax, eax
0x180101c9d  jz      loc_180101F55
0x180101ca3  lea     r9, [rsp+0D60h+var_D00]; unsigned int *
0x180101ca8  lea     r8, [rsp+0D60h+var_D10]; char **
0x180101cad  lea     rdx, [rbp+0C60h+var_250]; unsigned __int16 *
0x180101cb4  call    ?_WideToAnsi@CVersionManagerServer@@AEAAJPEBGPEAPEADPEAK@Z; CVersionManagerServer::_WideToAnsi(ushort const *,char * *,ulong *)
0x180101cb9  mov     ebx, eax
0x180101cbb  test    eax, eax
0x180101cbd  js      loc_180101F70
0x180101cc3  mov     ecx, [r14+690h]
0x180101cca  test    ecx, ecx
0x180101ccc  jz      short loc_180101CF8
0x180101cce  sub     ecx, 1
0x180101cd1  jz      short loc_180101CEF
0x180101cd3  sub     ecx, 1
0x180101cd6  jz      short loc_180101CE6
0x180101cd8  cmp     ecx, 1
0x180101cdb  jnz     short loc_180101D15
0x180101cdd  lea     r8, aFail; "Fail"
0x180101ce4  jmp     short loc_180101CFF
0x180101ce6  lea     r8, aNotnew; "NotNew"
0x180101ced  jmp     short loc_180101CFF
0x180101cef  lea     r8, aSuccess_2; "Success"
0x180101cf6  jmp     short loc_180101CFF
0x180101cf8  lea     r8, aNever; "Never"
0x180101cff  mov     rdx, r13; unsigned __int64
0x180101d02  lea     rcx, [rbp+0C60h+var_CB0]; char *
0x180101d06  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180101d0b  mov     ebx, eax
0x180101d0d  test    eax, eax
0x180101d0f  js      loc_180101F70
0x180101d15  mov     rax, [rsp+0D60h+var_D18]
0x180101d1a  lea     r9, [rbp+0C60h+var_CB0]
0x180101d1e  lea     rcx, [rbp+0C60h+Buffer]; char *
0x180101d25  mov     rdx, r13; unsigned __int64
0x180101d28  test    dil, dil
0x180101d2b  jz      short loc_180101D59
0x180101d2d  mov     [rsp+0D60h+var_D28], rax
0x180101d32  lea     r8, aSSSSS; "%s,%s %s, %s %s\r\n"
0x180101d39  mov     rax, [rsp+0D60h+var_D10]
0x180101d3e  mov     [rsp+0D60h+hTemplateFile], rax
0x180101d43  mov     rax, [rsp+0D60h+pv]
0x180101d48  mov     qword ptr [rsp+0D60h+cchDate], rax
0x180101d4d  mov     [rsp+0D60h+lpDateStr], r15
0x180101d52  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180101d57  jmp     short loc_180101D74
0x180101d59  mov     qword ptr [rsp+0D60h+cchDate], rax
0x180101d5e  lea     r8, aSNeverSS; "%s,Never, %s %s\r\n"
0x180101d65  mov     rax, [rsp+0D60h+var_D10]
0x180101d6a  mov     [rsp+0D60h+lpDateStr], rax
0x180101d6f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180101d74  mov     ebx, eax
0x180101d76  test    eax, eax
0x180101d78  js      loc_180101F70
0x180101d7e  mov     rcx, cs:?IEVALUE_urlmon_ExtVerDebugDownloadFilePath@SettingStore@@3U?$VALUEID@PEAG@1@B; SettingStore::VALUEID<ushort *> const SettingStore::IEVALUE_urlmon_ExtVerDebugDownloadFilePath
0x180101d85  lea     rdx, [rbp+0C60h+pszPath]
0x180101d8c  mov     r8d, r13d
0x180101d8f  call    GetString
0x180101d94  mov     ebx, eax
0x180101d96  test    eax, eax
0x180101d98  js      loc_180101F70
0x180101d9e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180101da2  lea     rax, [rbp+0C60h+pszPath]
0x180101da9  mov     rdx, rdi
0x180101dac  inc     rdx; cchPath
0x180101daf  cmp     [rax+rdx*2], r12w
0x180101db4  jnz     short loc_180101DAC
0x180101db6  lea     rcx, [rbp+0C60h+pszPath]; pszPath
0x180101dbd  call    cs:__imp_PathCchRemoveFileSpec
0x180101dc4  nop     dword ptr [rax+rax+00h]
0x180101dc9  mov     ebx, eax
0x180101dcb  test    eax, eax
0x180101dcd  js      loc_180101F70
0x180101dd3  lea     rcx, [rbp+0C60h+pszPath]; lpFileName
0x180101dda  call    cs:__imp_GetFileAttributesW
0x180101de1  nop     dword ptr [rax+rax+00h]
0x180101de6  mov     ebx, eax
0x180101de8  call    cs:__imp_GetLastError
0x180101def  nop     dword ptr [rax+rax+00h]
0x180101df4  or      r14d, 0FFFFFFFFh
0x180101df8  cmp     ebx, r14d
0x180101dfb  jnz     loc_180101F19
0x180101e01  cmp     eax, 2
0x180101e04  jnz     short loc_180101E1C
0x180101e06  lea     rdx, [rbp+0C60h+pszPath]; unsigned __int16 *
0x180101e0d  call    ?_CreateLocalDirectory@CVersionManagerServer@@AEAAJPEBG@Z; CVersionManagerServer::_CreateLocalDirectory(ushort const *)
0x180101e12  mov     ebx, eax
0x180101e14  test    eax, eax
0x180101e16  js      loc_180101F70
0x180101e1c  mov     rcx, cs:?IEVALUE_urlmon_ExtVerDebugDownloadFilePath@SettingStore@@3U?$VALUEID@PEAG@1@B; SettingStore::VALUEID<ushort *> const SettingStore::IEVALUE_urlmon_ExtVerDebugDownloadFilePath
0x180101e23  lea     rdx, [rbp+0C60h+pszPath]
0x180101e2a  mov     r8d, r13d
0x180101e2d  call    GetString
0x180101e32  mov     ebx, eax
0x180101e34  test    eax, eax
0x180101e36  js      loc_180101F70
0x180101e3c  xor     r9d, r9d; lpSecurityAttributes
0x180101e3f  mov     [rsp+0D60h+hTemplateFile], r12; hTemplateFile
0x180101e44  mov     [rsp+0D60h+cchDate], 80h; dwFlagsAndAttributes
0x180101e4c  lea     rcx, [rbp+0C60h+pszPath]; lpFileName
0x180101e53  mov     edx, 40000000h; dwDesiredAccess
0x180101e58  mov     dword ptr [rsp+0D60h+lpDateStr], 4; dwCreationDisposition
0x180101e60  lea     r8d, [r9+3]; dwShareMode
0x180101e64  call    cs:__imp_CreateFileW
0x180101e6b  nop     dword ptr [rax+rax+00h]
0x180101e70  mov     rsi, rax
0x180101e73  cmp     rax, rdi
0x180101e76  jz      loc_180101F55
0x180101e7c  call    cs:__imp_GetLastError
0x180101e83  nop     dword ptr [rax+rax+00h]
0x180101e88  cmp     eax, 0B7h
0x180101e8d  jnz     short loc_180101ECD
0x180101e8f  mov     r9d, 2; dwMoveMethod
0x180101e95  xor     r8d, r8d; lpDistanceToMoveHigh
0x180101e98  xor     edx, edx; lDistanceToMove
0x180101e9a  mov     rcx, rsi; hFile
0x180101e9d  call    cs:__imp_SetFilePointer
0x180101ea4  nop     dword ptr [rax+rax+00h]
0x180101ea9  cmp     eax, r14d
0x180101eac  jnz     short loc_180101ECD
0x180101eae  call    cs:__imp_GetLastError
0x180101eb5  nop     dword ptr [rax+rax+00h]
0x180101eba  mov     ebx, eax
0x180101ebc  test    eax, eax
0x180101ebe  jle     short loc_180101EC9
0x180101ec0  movzx   ebx, ax
0x180101ec3  or      ebx, 80070000h
0x180101ec9  test    ebx, ebx
0x180101ecb  js      short loc_180101F44
0x180101ecd  mov     [rsp+0D60h+NumberOfBytesWritten], r12d
0x180101ed2  lea     rax, [rbp+0C60h+Buffer]
0x180101ed9  inc     rdi
0x180101edc  cmp     [rax+rdi], r12b
0x180101ee0  jnz     short loc_180101ED9
0x180101ee2  mov     r8d, edi; nNumberOfBytesToWrite
0x180101ee5  mov     [rsp+0D60h+lpDateStr], r12; lpOverlapped
0x180101eea  lea     r9, [rsp+0D60h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180101eef  mov     rcx, rsi; hFile
0x180101ef2  lea     rdx, [rbp+0C60h+Buffer]; lpBuffer
0x180101ef9  call    cs:__imp_WriteFile
0x180101f00  nop     dword ptr [rax+rax+00h]
0x180101f05  test    eax, eax
0x180101f07  jz      short loc_180101F29
0x180101f09  mov     eax, [rsp+0D60h+NumberOfBytesWritten]
0x180101f0d  cmp     rax, rdi
0x180101f10  jz      short loc_180101F44
0x180101f12  mov     ebx, 8007001Dh
0x180101f17  jmp     short loc_180101F44
0x180101f19  test    bl, 10h
0x180101f1c  jnz     loc_180101E1C
0x180101f22  mov     ebx, 800700A1h
0x180101f27  jmp     short loc_180101F70
0x180101f29  call    cs:__imp_GetLastError
0x180101f30  nop     dword ptr [rax+rax+00h]
0x180101f35  mov     ebx, eax
0x180101f37  test    eax, eax
0x180101f39  jle     short loc_180101F44
0x180101f3b  movzx   ebx, ax
0x180101f3e  or      ebx, 80070000h
  ... truncated ...
```
