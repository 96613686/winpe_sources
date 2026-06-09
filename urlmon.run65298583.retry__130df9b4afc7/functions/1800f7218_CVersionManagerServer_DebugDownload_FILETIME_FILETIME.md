# CVersionManagerServer::_DebugDownload(_FILETIME *,_FILETIME *)

- ea: `0x1800f7218`
- end: `0x1800f772d`
- name: `?_DebugDownload@CVersionManagerServer@@AEAAJPEAU_FILETIME@@0@Z`
- size: `1301`
- prototype: `int(CVersionManagerServer *__hidden this, struct _FILETIME *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1800f95b8`

## callees

- `0x180044b84`
- `0x18005cc10`
- `0x1800f70dc`
- `0x1800f7218`
- `0x1800f9a6c`
- `0x18011a86c`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7363`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f757e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7606`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f762c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f769b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f76bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7363`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f757e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7606`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f762c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f769b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f76bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f76b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f76b3`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800f755f`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800f755f`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800f72ce`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800f73a5`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800f72ce`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800f73a5`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800f7621`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800f7621`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800f7671`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800f7671`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800f7576`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800f7576`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f75f4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f75f4`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800f72e5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800f73bb`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800f72e5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800f73bb`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x1800f7310`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x1800f73ea`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x1800f7310`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x1800f73ea`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x1800f7359`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x1800f7437`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x1800f7359`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x1800f7437`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f76d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f76de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f76e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f76f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f76d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f76de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f76e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f76f4`

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
  const char *v17; // r8
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
      String = CVersionManagerServer::_WideToAnsi(v7, DateStr, (char **)&pv, &NumberOfBytesWritten);
      if ( String < 0 )
        goto LABEL_60;
      if ( GetTimeFormatW(0x400u, 0, &SystemTime, 0, TimeStr, 260) )
      {
        v11 = CVersionManagerServer::_WideToAnsi(v9, TimeStr, &v37, &v32);
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
    String = CVersionManagerServer::_WideToAnsi(v12, lpDateStr, &v30, &v33);
    if ( String < 0 )
      goto LABEL_60;
    if ( !GetTimeFormatW(0x400u, 0, &Date, 0, v47, 260) )
      goto LABEL_58;
    String = CVersionManagerServer::_WideToAnsi(v13, v47, &v31, &v34);
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
            String = GetString((__int64 *)SettingStore::IEVALUE_urlmon_ExtVerDebugDownloadFilePath[0], pszPath, 260);
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
            String = GetString((__int64 *)SettingStore::IEVALUE_urlmon_ExtVerDebugDownloadFilePath[0], pszPath, 260);
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
0x1800f7218  mov     [rsp-8+arg_0], rbx
0x1800f721d  push    rbp
0x1800f721e  push    rsi
0x1800f721f  push    rdi
0x1800f7220  push    r12
0x1800f7222  push    r13
0x1800f7224  push    r14
0x1800f7226  push    r15
0x1800f7228  lea     rbp, [rsp-0C30h]
0x1800f7230  sub     rsp, 0D30h
0x1800f7237  mov     rax, cs:__security_cookie
0x1800f723e  xor     rax, rsp
0x1800f7241  mov     [rbp+0C60h+var_40], rax
0x1800f7248  xor     r12d, r12d
0x1800f724b  mov     rsi, r8
0x1800f724e  mov     rax, rdx
0x1800f7251  mov     r14, rcx
0x1800f7254  test    rdx, rdx
0x1800f7257  jz      loc_1800F76FE
0x1800f725d  test    r8, r8
0x1800f7260  jz      loc_1800F76FE
0x1800f7266  xorps   xmm0, xmm0
0x1800f7269  xorps   xmm1, xmm1
0x1800f726c  mov     r15d, r12d
0x1800f726f  mov     qword ptr [rsp+0D60h+LocalFileTime.dwLowDateTime], r12
0x1800f7274  mov     edi, 80070000h
0x1800f7279  mov     qword ptr [rbp+0C60h+FileTime.dwLowDateTime], r12
0x1800f727d  mov     r13d, 104h
0x1800f7283  mov     [rsp+0D60h+pv], r12
0x1800f7288  movups  xmmword ptr [rbp+0C60h+SystemTime.wYear], xmm0
0x1800f728c  mov     [rsp+0D60h+NumberOfBytesWritten], r12d
0x1800f7291  movups  xmmword ptr [rbp+0C60h+Date.wYear], xmm1
0x1800f7295  mov     [rsp+0D60h+var_CE8], r12
0x1800f729a  mov     [rsp+0D60h+var_D08], r12d
0x1800f729f  mov     [rsp+0D60h+var_D18], r12
0x1800f72a4  mov     [rsp+0D60h+var_D04], r12d
0x1800f72a9  mov     [rsp+0D60h+var_D10], r12
0x1800f72ae  mov     [rsp+0D60h+var_D00], r12d
0x1800f72b3  cmp     [rdx+4], r12d
0x1800f72b7  jnz     short loc_1800F72C6
0x1800f72b9  cmp     [rdx], r12d
0x1800f72bc  jnz     short loc_1800F72C6
0x1800f72be  mov     dil, r12b
0x1800f72c1  jmp     loc_1800F739E
0x1800f72c6  lea     rdx, [rsp+0D60h+LocalFileTime]; lpLocalFileTime
0x1800f72cb  mov     rcx, rax; lpFileTime
0x1800f72ce  call    cs:__imp_FileTimeToLocalFileTime
0x1800f72d4  test    eax, eax
0x1800f72d6  jz      loc_1800F7363
0x1800f72dc  lea     rdx, [rbp+0C60h+SystemTime]; lpSystemTime
0x1800f72e0  lea     rcx, [rsp+0D60h+LocalFileTime]; lpFileTime
0x1800f72e5  call    cs:__imp_FileTimeToSystemTime
0x1800f72eb  test    eax, eax
0x1800f72ed  jz      short loc_1800F7363
0x1800f72ef  xor     r9d, r9d; lpFormat
0x1800f72f2  mov     [rsp+0D60h+cchDate], r13d; cchDate
0x1800f72f7  lea     rax, [rbp+0C60h+DateStr]
0x1800f72fe  mov     ecx, 400h; Locale
0x1800f7303  lea     r8, [rbp+0C60h+SystemTime]; lpDate
0x1800f7307  mov     [rsp+0D60h+lpDateStr], rax; lpDateStr
0x1800f730c  lea     edx, [r9+1]; dwFlags
0x1800f7310  call    cs:__imp_GetDateFormatW
0x1800f7316  test    eax, eax
0x1800f7318  jz      short loc_1800F7363
0x1800f731a  lea     r9, [rsp+0D60h+NumberOfBytesWritten]; unsigned int *
0x1800f731f  lea     r8, [rsp+0D60h+pv]; char **
0x1800f7324  lea     rdx, [rbp+0C60h+DateStr]; unsigned __int16 *
0x1800f732b  call    ?_WideToAnsi@CVersionManagerServer@@AEAAJPEBGPEAPEADPEAK@Z; CVersionManagerServer::_WideToAnsi(ushort const *,char * *,ulong *)
0x1800f7330  mov     ebx, eax
0x1800f7332  test    eax, eax
0x1800f7334  js      loc_1800F76D0
0x1800f733a  lea     rax, [rbp+0C60h+TimeStr]
0x1800f7341  mov     [rsp+0D60h+cchDate], r13d; cchTime
0x1800f7346  xor     r9d, r9d; lpFormat
0x1800f7349  mov     [rsp+0D60h+lpDateStr], rax; lpTimeStr
0x1800f734e  lea     r8, [rbp+0C60h+SystemTime]; lpTime
0x1800f7352  xor     edx, edx; dwFlags
0x1800f7354  mov     ecx, 400h; Locale
0x1800f7359  call    cs:__imp_GetTimeFormatW
0x1800f735f  test    eax, eax
0x1800f7361  jnz     short loc_1800F7376
0x1800f7363  call    cs:__imp_GetLastError
0x1800f7369  mov     ebx, eax
0x1800f736b  test    eax, eax
0x1800f736d  jle     short loc_1800F7393
0x1800f736f  movzx   ebx, ax
0x1800f7372  or      ebx, edi
0x1800f7374  jmp     short loc_1800F7393
0x1800f7376  lea     r9, [rsp+0D60h+var_D08]; unsigned int *
0x1800f737b  lea     r8, [rsp+0D60h+var_CE8]; char **
0x1800f7380  lea     rdx, [rbp+0C60h+TimeStr]; unsigned __int16 *
0x1800f7387  call    ?_WideToAnsi@CVersionManagerServer@@AEAAJPEBGPEAPEADPEAK@Z; CVersionManagerServer::_WideToAnsi(ushort const *,char * *,ulong *)
0x1800f738c  mov     r15, [rsp+0D60h+var_CE8]
0x1800f7391  mov     ebx, eax
0x1800f7393  mov     dil, 1
0x1800f7396  test    ebx, ebx
0x1800f7398  js      loc_1800F76D0
0x1800f739e  lea     rdx, [rbp+0C60h+FileTime]; lpLocalFileTime
0x1800f73a2  mov     rcx, rsi; lpFileTime
0x1800f73a5  call    cs:__imp_FileTimeToLocalFileTime
0x1800f73ab  test    eax, eax
0x1800f73ad  jz      loc_1800F76BB
0x1800f73b3  lea     rdx, [rbp+0C60h+Date]; lpSystemTime
0x1800f73b7  lea     rcx, [rbp+0C60h+FileTime]; lpFileTime
0x1800f73bb  call    cs:__imp_FileTimeToSystemTime
0x1800f73c1  test    eax, eax
0x1800f73c3  jz      loc_1800F76BB
0x1800f73c9  xor     r9d, r9d; lpFormat
0x1800f73cc  mov     [rsp+0D60h+cchDate], r13d; cchDate
0x1800f73d1  lea     rax, [rbp+0C60h+var_460]
0x1800f73d8  mov     ecx, 400h; Locale
0x1800f73dd  lea     r8, [rbp+0C60h+Date]; lpDate
0x1800f73e1  mov     [rsp+0D60h+lpDateStr], rax; lpDateStr
0x1800f73e6  lea     edx, [r9+1]; dwFlags
0x1800f73ea  call    cs:__imp_GetDateFormatW
0x1800f73f0  test    eax, eax
0x1800f73f2  jz      loc_1800F76BB
0x1800f73f8  lea     r9, [rsp+0D60h+var_D04]; unsigned int *
0x1800f73fd  lea     r8, [rsp+0D60h+var_D18]; char **
0x1800f7402  lea     rdx, [rbp+0C60h+var_460]; unsigned __int16 *
0x1800f7409  call    ?_WideToAnsi@CVersionManagerServer@@AEAAJPEBGPEAPEADPEAK@Z; CVersionManagerServer::_WideToAnsi(ushort const *,char * *,ulong *)
0x1800f740e  mov     ebx, eax
0x1800f7410  test    eax, eax
0x1800f7412  js      loc_1800F76D0
0x1800f7418  lea     rax, [rbp+0C60h+var_250]
0x1800f741f  mov     [rsp+0D60h+cchDate], r13d; cchTime
0x1800f7424  xor     r9d, r9d; lpFormat
0x1800f7427  mov     [rsp+0D60h+lpDateStr], rax; lpTimeStr
0x1800f742c  lea     r8, [rbp+0C60h+Date]; lpTime
0x1800f7430  xor     edx, edx; dwFlags
0x1800f7432  mov     ecx, 400h; Locale
0x1800f7437  call    cs:__imp_GetTimeFormatW
0x1800f743d  test    eax, eax
0x1800f743f  jz      loc_1800F76BB
0x1800f7445  lea     r9, [rsp+0D60h+var_D00]; unsigned int *
0x1800f744a  lea     r8, [rsp+0D60h+var_D10]; char **
0x1800f744f  lea     rdx, [rbp+0C60h+var_250]; unsigned __int16 *
0x1800f7456  call    ?_WideToAnsi@CVersionManagerServer@@AEAAJPEBGPEAPEADPEAK@Z; CVersionManagerServer::_WideToAnsi(ushort const *,char * *,ulong *)
0x1800f745b  mov     ebx, eax
0x1800f745d  test    eax, eax
0x1800f745f  js      loc_1800F76D0
0x1800f7465  mov     ecx, [r14+690h]
0x1800f746c  test    ecx, ecx
0x1800f746e  jz      short loc_1800F749A
0x1800f7470  sub     ecx, 1
0x1800f7473  jz      short loc_1800F7491
0x1800f7475  sub     ecx, 1
0x1800f7478  jz      short loc_1800F7488
0x1800f747a  cmp     ecx, 1
0x1800f747d  jnz     short loc_1800F74B7
0x1800f747f  lea     r8, aFail; "Fail"
0x1800f7486  jmp     short loc_1800F74A1
0x1800f7488  lea     r8, aNotnew; "NotNew"
0x1800f748f  jmp     short loc_1800F74A1
0x1800f7491  lea     r8, aSuccess_2; "Success"
0x1800f7498  jmp     short loc_1800F74A1
0x1800f749a  lea     r8, aNever; "Never"
0x1800f74a1  mov     rdx, r13; unsigned __int64
0x1800f74a4  lea     rcx, [rbp+0C60h+var_CB0]; char *
0x1800f74a8  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800f74ad  mov     ebx, eax
0x1800f74af  test    eax, eax
0x1800f74b1  js      loc_1800F76D0
0x1800f74b7  mov     rax, [rsp+0D60h+var_D18]
0x1800f74bc  lea     r9, [rbp+0C60h+var_CB0]
0x1800f74c0  lea     rcx, [rbp+0C60h+Buffer]; char *
0x1800f74c7  mov     rdx, r13; unsigned __int64
0x1800f74ca  test    dil, dil
0x1800f74cd  jz      short loc_1800F74FB
0x1800f74cf  mov     [rsp+0D60h+var_D28], rax
0x1800f74d4  lea     r8, aSSSSS; "%s,%s %s, %s %s\r\n"
0x1800f74db  mov     rax, [rsp+0D60h+var_D10]
0x1800f74e0  mov     [rsp+0D60h+hTemplateFile], rax
0x1800f74e5  mov     rax, [rsp+0D60h+pv]
0x1800f74ea  mov     qword ptr [rsp+0D60h+cchDate], rax
0x1800f74ef  mov     [rsp+0D60h+lpDateStr], r15
0x1800f74f4  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800f74f9  jmp     short loc_1800F7516
0x1800f74fb  mov     qword ptr [rsp+0D60h+cchDate], rax
0x1800f7500  lea     r8, aSNeverSS; "%s,Never, %s %s\r\n"
0x1800f7507  mov     rax, [rsp+0D60h+var_D10]
0x1800f750c  mov     [rsp+0D60h+lpDateStr], rax
0x1800f7511  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800f7516  mov     ebx, eax
0x1800f7518  test    eax, eax
0x1800f751a  js      loc_1800F76D0
0x1800f7520  mov     rcx, cs:?IEVALUE_urlmon_ExtVerDebugDownloadFilePath@SettingStore@@3U?$VALUEID@PEAG@1@B; SettingStore::VALUEID<ushort *> const SettingStore::IEVALUE_urlmon_ExtVerDebugDownloadFilePath
0x1800f7527  lea     rdx, [rbp+0C60h+pszPath]
0x1800f752e  mov     r8d, r13d
0x1800f7531  call    GetString
0x1800f7536  mov     ebx, eax
0x1800f7538  test    eax, eax
0x1800f753a  js      loc_1800F76D0
0x1800f7540  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800f7544  lea     rax, [rbp+0C60h+pszPath]
0x1800f754b  mov     rdx, rdi
0x1800f754e  inc     rdx; cchPath
0x1800f7551  cmp     [rax+rdx*2], r12w
0x1800f7556  jnz     short loc_1800F754E
0x1800f7558  lea     rcx, [rbp+0C60h+pszPath]; pszPath
0x1800f755f  call    cs:__imp_PathCchRemoveFileSpec
0x1800f7565  mov     ebx, eax
0x1800f7567  test    eax, eax
0x1800f7569  js      loc_1800F76D0
0x1800f756f  lea     rcx, [rbp+0C60h+pszPath]; lpFileName
0x1800f7576  call    cs:__imp_GetFileAttributesW
0x1800f757c  mov     ebx, eax
0x1800f757e  call    cs:__imp_GetLastError
0x1800f7584  or      r14d, 0FFFFFFFFh
0x1800f7588  cmp     ebx, r14d
0x1800f758b  jnz     loc_1800F768B
0x1800f7591  cmp     eax, 2
0x1800f7594  jnz     short loc_1800F75AC
0x1800f7596  lea     rdx, [rbp+0C60h+pszPath]; unsigned __int16 *
0x1800f759d  call    ?_CreateLocalDirectory@CVersionManagerServer@@AEAAJPEBG@Z; CVersionManagerServer::_CreateLocalDirectory(ushort const *)
0x1800f75a2  mov     ebx, eax
0x1800f75a4  test    eax, eax
0x1800f75a6  js      loc_1800F76D0
0x1800f75ac  mov     rcx, cs:?IEVALUE_urlmon_ExtVerDebugDownloadFilePath@SettingStore@@3U?$VALUEID@PEAG@1@B; SettingStore::VALUEID<ushort *> const SettingStore::IEVALUE_urlmon_ExtVerDebugDownloadFilePath
0x1800f75b3  lea     rdx, [rbp+0C60h+pszPath]
0x1800f75ba  mov     r8d, r13d
0x1800f75bd  call    GetString
0x1800f75c2  mov     ebx, eax
0x1800f75c4  test    eax, eax
0x1800f75c6  js      loc_1800F76D0
0x1800f75cc  xor     r9d, r9d; lpSecurityAttributes
0x1800f75cf  mov     [rsp+0D60h+hTemplateFile], r12; hTemplateFile
0x1800f75d4  mov     [rsp+0D60h+cchDate], 80h; dwFlagsAndAttributes
0x1800f75dc  lea     rcx, [rbp+0C60h+pszPath]; lpFileName
0x1800f75e3  mov     edx, 40000000h; dwDesiredAccess
0x1800f75e8  mov     dword ptr [rsp+0D60h+lpDateStr], 4; dwCreationDisposition
0x1800f75f0  lea     r8d, [r9+3]; dwShareMode
0x1800f75f4  call    cs:__imp_CreateFileW
0x1800f75fa  mov     rsi, rax
0x1800f75fd  cmp     rax, rdi
0x1800f7600  jz      loc_1800F76BB
0x1800f7606  call    cs:__imp_GetLastError
0x1800f760c  cmp     eax, 0B7h
0x1800f7611  jnz     short loc_1800F7645
0x1800f7613  mov     r9d, 2; dwMoveMethod
0x1800f7619  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800f761c  xor     edx, edx; lDistanceToMove
0x1800f761e  mov     rcx, rsi; hFile
0x1800f7621  call    cs:__imp_SetFilePointer
0x1800f7627  cmp     eax, r14d
0x1800f762a  jnz     short loc_1800F7645
0x1800f762c  call    cs:__imp_GetLastError
0x1800f7632  mov     ebx, eax
0x1800f7634  test    eax, eax
0x1800f7636  jle     short loc_1800F7641
0x1800f7638  movzx   ebx, ax
0x1800f763b  or      ebx, 80070000h
0x1800f7641  test    ebx, ebx
0x1800f7643  js      short loc_1800F76B0
0x1800f7645  mov     [rsp+0D60h+NumberOfBytesWritten], r12d
0x1800f764a  lea     rax, [rbp+0C60h+Buffer]
0x1800f7651  inc     rdi
0x1800f7654  cmp     [rax+rdi], r12b
0x1800f7658  jnz     short loc_1800F7651
0x1800f765a  mov     r8d, edi; nNumberOfBytesToWrite
0x1800f765d  mov     [rsp+0D60h+lpDateStr], r12; lpOverlapped
0x1800f7662  lea     r9, [rsp+0D60h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800f7667  mov     rcx, rsi; hFile
0x1800f766a  lea     rdx, [rbp+0C60h+Buffer]; lpBuffer
0x1800f7671  call    cs:__imp_WriteFile
0x1800f7677  test    eax, eax
0x1800f7679  jz      short loc_1800F769B
0x1800f767b  mov     eax, [rsp+0D60h+NumberOfBytesWritten]
0x1800f767f  cmp     rax, rdi
0x1800f7682  jz      short loc_1800F76B0
0x1800f7684  mov     ebx, 8007001Dh
0x1800f7689  jmp     short loc_1800F76B0
0x1800f768b  test    bl, 10h
0x1800f768e  jnz     loc_1800F75AC
0x1800f7694  mov     ebx, 800700A1h
0x1800f7699  jmp     short loc_1800F76D0
0x1800f769b  call    cs:__imp_GetLastError
0x1800f76a1  mov     ebx, eax
0x1800f76a3  test    eax, eax
0x1800f76a5  jle     short loc_1800F76B0
0x1800f76a7  movzx   ebx, ax
0x1800f76aa  or      ebx, 80070000h
0x1800f76b0  mov     rcx, rsi; hObject
0x1800f76b3  call    cs:__imp_CloseHandle
0x1800f76b9  jmp     short loc_1800F76D0
0x1800f76bb  call    cs:__imp_GetLastError
0x1800f76c1  mov     ebx, eax
0x1800f76c3  test    eax, eax
0x1800f76c5  jle     short loc_1800F76D0
0x1800f76c7  movzx   ebx, ax
0x1800f76ca  or      ebx, 80070000h
0x1800f76d0  mov     rcx, [rsp+0D60h+pv]; pv
0x1800f76d5  call    cs:__imp_CoTaskMemFree
0x1800f76db  mov     rcx, r15; pv
0x1800f76de  call    cs:__imp_CoTaskMemFree
0x1800f76e4  mov     rcx, [rsp+0D60h+var_D18]; pv
0x1800f76e9  call    cs:__imp_CoTaskMemFree
0x1800f76ef  mov     rcx, [rsp+0D60h+var_D10]; pv
0x1800f76f4  call    cs:__imp_CoTaskMemFree
0x1800f76fa  mov     eax, ebx
  ... truncated ...
```
