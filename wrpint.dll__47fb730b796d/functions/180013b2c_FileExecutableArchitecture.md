# FileExecutableArchitecture

- ea: `0x180013b2c`
- end: `0x18001404c`
- name: `FileExecutableArchitecture`
- size: `1312`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x180005920`

## callees

- `0x18000a384`
- `0x18000a570`
- `0x18000ed74`
- `0x18000ed98`
- `0x1800118a4`
- `0x1800136a0`
- `0x180013b2c`
- `0x18001b77a`
- `0x18001b7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ed6`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180013e40`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180013e40`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013c72`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013c72`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180013d55`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180013ecc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180013d55`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180013ecc`
- `ntdll!NtClose` at `0x180013d0e`
- `ntdll!NtClose` at `0x180014017`
- `ntdll!NtClose` at `0x180013d0e`
- `ntdll!NtClose` at `0x180014017`

## string_xrefs

- `0x180013ca3`: `Failed to open file: {}`
- `0x180013d76`: `Failed to read DOS header from file: {}`
- `0x180013e01`: `Read invalid DOS header from file: {}`
- `0x180013eed`: `Failed to read NT header from file: {}`
- `0x180013f5d`: `Read invalid NT header from file: {}`

## pseudocode

```c
__int64 __fastcall FileExecutableArchitecture(LPCWSTR lpFileName, _WORD *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  char *FileW; // rax
  char *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  signed int v11; // edi
  __int64 v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // edi
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  signed int LastError; // edi
  __int64 v20; // rcx
  unsigned int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rcx
  unsigned int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rcx
  int v31; // r8d
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rcx
  unsigned int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rcx
  int *v38; // [rsp+40h] [rbp-C0h] BYREF
  int v39[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v40; // [rsp+50h] [rbp-B0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+54h] [rbp-ACh] BYREF
  _WORD Buffer[30]; // [rsp+60h] [rbp-A0h] BYREF
  LONG lDistanceToMove; // [rsp+9Ch] [rbp-64h]
  int v44; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v45; // [rsp+A4h] [rbp-5Ch]
  unsigned __int16 v46; // [rsp+FCh] [rbp-4h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  *(_QWORD *)v39 = lpFileName;
  NumberOfBytesRead = 0;
  memset_0(Buffer, 0, 0x40u);
  memset_0(&v44, 0, 0x108u);
  if ( !lpFileName )
  {
    v4 = -2147024809;
    v40 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file specified");
      v38 = &v40;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)&v40,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v38);
    }
    v5 = 179;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v4);
    return v4;
  }
  if ( !a2 )
  {
    v4 = -2147467261;
    v40 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No architecture result specified");
      v38 = &v40;
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)&v40,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v38);
    }
    v5 = 180;
    goto LABEL_5;
  }
  FileW = (char *)CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v8 = FileW;
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    if ( !ReadFile(FileW, Buffer, 0x40u, &NumberOfBytesRead, 0) )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogPartial<wchar_t const *>(
          v18,
          v17,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to read DOS header from file: {}",
          (__int64)v39);
        if ( LastError > 0 )
          v21 = (unsigned __int16)LastError | 0x80070000;
        else
          v21 = LastError;
        v40 = v21;
        v38 = &v40;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          v20,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
          (__int64)&v38);
      }
      if ( LastError )
      {
        v22 = 190;
LABEL_31:
        v14 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)v22,
                (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
                (const char *)(unsigned int)LastError);
        goto LABEL_18;
      }
      goto LABEL_66;
    }
    if ( Buffer[0] == 23117 )
    {
      if ( SetFilePointer(v8, lDistanceToMove, 0, 0) == -1 )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogPartial<wchar_t const *>(
            v26,
            v25,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to seek the NT header in file: {}",
            (__int64)v39);
          if ( LastError > 0 )
            v28 = (unsigned __int16)LastError | 0x80070000;
          else
            v28 = LastError;
          v40 = v28;
          v38 = &v40;
          LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            v27,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
            (__int64)&v38);
        }
        if ( LastError )
        {
          v22 = 196;
          goto LABEL_31;
        }
LABEL_66:
        if ( NtClose(v8) < 0 )
          __fastfail(7u);
        return 0;
      }
      if ( !ReadFile(v8, &v44, 0x108u, &NumberOfBytesRead, 0) )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogPartial<wchar_t const *>(
            v33,
            v32,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to read NT header from file: {}",
            (__int64)v39);
          if ( LastError > 0 )
            v35 = (unsigned __int16)LastError | 0x80070000;
          else
            v35 = LastError;
          v40 = v35;
          v38 = &v40;
          LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            v34,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
            (__int64)&v38);
        }
        if ( LastError )
        {
          v22 = 199;
          goto LABEL_31;
        }
        goto LABEL_66;
      }
      if ( v44 == 17744 )
      {
        if ( v46 == 1 || v46 == 2 || v46 == 3 || v46 != 5 && v46 != 7 )
        {
          *a2 = v45;
          goto LABEL_66;
        }
        v14 = -2147024885;
        v40 = -2147024885;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogPartial<unsigned short,wchar_t const *>(
            v46 - 5,
            v29,
            v31,
            (unsigned int)&v46,
            (__int64)v39);
          v38 = &v40;
          LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            v37,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)&v38);
        }
        v24 = 221;
      }
      else
      {
        v14 = -2147024885;
        v40 = -2147024885;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogPartial<wchar_t const *>(
            v30,
            v29,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Read invalid NT header from file: {}",
            (__int64)v39);
          v38 = &v40;
          LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            v36,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)&v38);
        }
        v24 = 202;
      }
    }
    else
    {
      v14 = -2147024885;
      v40 = -2147024885;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogPartial<wchar_t const *>(
          v16,
          v15,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Read invalid DOS header from file: {}",
          (__int64)v39);
        v38 = &v40;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          v23,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&v38);
      }
      v24 = 193;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)0x8007000BLL);
    goto LABEL_18;
  }
  v11 = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogPartial<wchar_t const *>(
      v10,
      v9,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to open file: {}",
      (__int64)v39);
    if ( v11 > 0 )
      v13 = (unsigned __int16)v11 | 0x80070000;
    else
      v13 = v11;
    v40 = v13;
    v38 = &v40;
    LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      v12,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
      (__int64)&v38);
  }
  if ( v11 )
  {
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xBA,
            (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
            (const char *)(unsigned int)v11);
    if ( (unsigned __int64)(v8 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      return v14;
LABEL_18:
    if ( NtClose(v8) < 0 )
      __fastfail(7u);
    return v14;
  }
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_66;
  return 0;
}

```

## disassembly

```asm
0x180013b2c  mov     [rsp-8+arg_10], rbx
0x180013b31  push    rbp
0x180013b32  push    rsi
0x180013b33  push    rdi
0x180013b34  lea     rbp, [rsp-0C0h]
0x180013b3c  sub     rsp, 1C0h
0x180013b43  mov     rax, cs:__security_cookie
0x180013b4a  xor     rax, rsp
0x180013b4d  mov     [rbp+0D0h+var_20], rax
0x180013b54  mov     rdi, rdx
0x180013b57  mov     qword ptr [rsp+1D0h+var_188], rcx
0x180013b5c  xor     edx, edx; Val
0x180013b5e  mov     [rsp+1D0h+NumberOfBytesRead], 0
0x180013b66  mov     rbx, rcx
0x180013b69  lea     rcx, [rsp+1D0h+Buffer]; void *
0x180013b6e  lea     r8d, [rdx+40h]; Size
0x180013b72  call    memset_0
0x180013b77  xor     edx, edx; Val
0x180013b79  lea     rcx, [rbp+0D0h+var_130]; void *
0x180013b7d  mov     r8d, 108h; Size
0x180013b83  call    memset_0
0x180013b88  test    rbx, rbx
0x180013b8b  jnz     short loc_180013BF7
0x180013b8d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180013b94  mov     ebx, 80070057h
0x180013b99  mov     [rsp+1D0h+var_180], ebx
0x180013b9d  test    rcx, rcx
0x180013ba0  jz      short loc_180013BD5
0x180013ba2  mov     esi, 3
0x180013ba7  lea     r9, aNoFileSpecifie; "No file specified"
0x180013bae  mov     r8d, esi
0x180013bb1  xor     edx, edx
0x180013bb3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180013bb8  lea     rcx, [rsp+1D0h+var_180]
0x180013bbd  mov     edx, esi
0x180013bbf  lea     r9, [rsp+1D0h+var_190]
0x180013bc4  mov     [rsp+1D0h+var_190], rcx
0x180013bc9  lea     r8, asc_1800233AC; ": {}"
0x180013bd0  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180013bd5  mov     edx, 0B3h; void *
0x180013bda  mov     rcx, [rbp+0D8h]; this
0x180013be1  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180013be8  mov     r9d, ebx; char *
0x180013beb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013bf0  mov     eax, ebx
0x180013bf2  jmp     loc_18001402A
0x180013bf7  test    rdi, rdi
0x180013bfa  jnz     short loc_180013C49
0x180013bfc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180013c03  mov     ebx, 80004003h
0x180013c08  mov     [rsp+1D0h+var_180], ebx
0x180013c0c  test    rcx, rcx
0x180013c0f  jz      short loc_180013C42
0x180013c11  lea     esi, [rdi+3]
0x180013c14  xor     edx, edx
0x180013c16  mov     r8d, esi
0x180013c19  lea     r9, aNoArchitecture; "No architecture result specified"
0x180013c20  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180013c25  lea     rcx, [rsp+1D0h+var_180]
0x180013c2a  mov     edx, esi
0x180013c2c  lea     r9, [rsp+1D0h+var_190]
0x180013c31  mov     [rsp+1D0h+var_190], rcx
0x180013c36  lea     r8, asc_1800233AC; ": {}"
0x180013c3d  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180013c42  mov     edx, 0B4h
0x180013c47  jmp     short loc_180013BDA
0x180013c49  mov     esi, 3
0x180013c4e  mov     [rsp+1D0h+hTemplateFile], 0; hTemplateFile
0x180013c57  mov     [rsp+1D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180013c5f  xor     r9d, r9d; lpSecurityAttributes
0x180013c62  mov     edx, 80000000h; dwDesiredAccess
0x180013c67  mov     [rsp+1D0h+dwCreationDisposition], esi; unsigned int
0x180013c6b  mov     rcx, rbx; lpFileName
0x180013c6e  lea     r8d, [rsi-2]; dwShareMode
0x180013c72  call    cs:__imp_CreateFileW
0x180013c78  mov     rbx, rax
0x180013c7b  lea     rcx, [rax+1]
0x180013c7f  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180013c86  jnz     loc_180013D39
0x180013c8c  call    cs:__imp_GetLastError
0x180013c92  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, 0; LogAdapter::Logger * LogAdapter::g_Logger
0x180013c9a  mov     edi, eax
0x180013c9c  jz      short loc_180013CE0
0x180013c9e  lea     r9, [rsp+1D0h+var_188]
0x180013ca3  lea     r8, aFailedToOpenFi; "Failed to open file: {}"
0x180013caa  call    ??$LogPartial@PEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogPartial<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180013caf  test    edi, edi
0x180013cb1  jg      short loc_180013CB7
0x180013cb3  mov     eax, edi
0x180013cb5  jmp     short loc_180013CBF
0x180013cb7  movzx   eax, di
0x180013cba  or      eax, 80070000h
0x180013cbf  mov     [rsp+1D0h+var_180], eax
0x180013cc3  lea     r9, [rsp+1D0h+var_190]
0x180013cc8  lea     rax, [rsp+1D0h+var_180]
0x180013ccd  mov     edx, esi
0x180013ccf  lea     r8, a0; ": {0}"
0x180013cd6  mov     [rsp+1D0h+var_190], rax
0x180013cdb  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180013ce0  test    edi, edi
0x180013ce2  jz      short loc_180013D26
0x180013ce4  mov     rcx, [rbp+0D8h]; this
0x180013ceb  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180013cf2  mov     r9d, edi; char *
0x180013cf5  mov     edx, 0BAh; void *
0x180013cfa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180013cff  lea     rcx, [rbx-1]
0x180013d03  mov     edi, eax
0x180013d05  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180013d09  ja      short loc_180013D1F
0x180013d0b  mov     rcx, rbx; Handle
0x180013d0e  call    cs:__imp_NtClose
0x180013d14  test    eax, eax
0x180013d16  jns     short loc_180013D1F
0x180013d18  mov     ecx, 7
0x180013d1d  int     29h; Win8: RtlFailFast(ecx)
0x180013d1f  mov     eax, edi
0x180013d21  jmp     loc_18001402A
0x180013d26  lea     rax, [rbx-1]
0x180013d2a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180013d2e  ja      loc_180014028
0x180013d34  jmp     loc_180014014
0x180013d39  lea     r9, [rsp+1D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180013d3e  mov     qword ptr [rsp+1D0h+dwCreationDisposition], 0; unsigned int
0x180013d47  mov     r8d, 40h ; '@'; nNumberOfBytesToRead
0x180013d4d  lea     rdx, [rsp+1D0h+Buffer]; lpBuffer
0x180013d52  mov     rcx, rbx; hFile
0x180013d55  call    cs:__imp_ReadFile
0x180013d5b  test    eax, eax
0x180013d5d  jnz     short loc_180013DDD
0x180013d5f  call    cs:__imp_GetLastError
0x180013d65  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, 0; LogAdapter::Logger * LogAdapter::g_Logger
0x180013d6d  mov     edi, eax
0x180013d6f  jz      short loc_180013DB3
0x180013d71  lea     r9, [rsp+1D0h+var_188]
0x180013d76  lea     r8, aFailedToReadDo; "Failed to read DOS header from file: {}"
0x180013d7d  call    ??$LogPartial@PEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogPartial<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180013d82  test    edi, edi
0x180013d84  jg      short loc_180013D8A
0x180013d86  mov     eax, edi
0x180013d88  jmp     short loc_180013D92
0x180013d8a  movzx   eax, di
0x180013d8d  or      eax, 80070000h
0x180013d92  mov     [rsp+1D0h+var_180], eax
0x180013d96  lea     r9, [rsp+1D0h+var_190]
0x180013d9b  lea     rax, [rsp+1D0h+var_180]
0x180013da0  mov     edx, esi
0x180013da2  lea     r8, a0; ": {0}"
0x180013da9  mov     [rsp+1D0h+var_190], rax
0x180013dae  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180013db3  test    edi, edi
0x180013db5  jz      loc_180014014
0x180013dbb  mov     edx, 0BEh; void *
0x180013dc0  mov     rcx, [rbp+0D8h]; this
0x180013dc7  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180013dce  mov     r9d, edi; char *
0x180013dd1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180013dd6  mov     edi, eax
0x180013dd8  jmp     loc_180013D0B
0x180013ddd  mov     eax, 5A4Dh
0x180013de2  cmp     [rsp+1D0h+Buffer], ax
0x180013de7  jz      short loc_180013E34
0x180013de9  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, 0; LogAdapter::Logger * LogAdapter::g_Logger
0x180013df1  mov     edi, 8007000Bh
0x180013df6  mov     [rsp+1D0h+var_180], edi
0x180013dfa  jz      short loc_180013E2A
0x180013dfc  lea     r9, [rsp+1D0h+var_188]
0x180013e01  lea     r8, aReadInvalidDos; "Read invalid DOS header from file: {}"
0x180013e08  call    ??$LogPartial@PEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogPartial<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180013e0d  lea     rax, [rsp+1D0h+var_180]
0x180013e12  mov     edx, esi
0x180013e14  lea     r9, [rsp+1D0h+var_190]
0x180013e19  mov     [rsp+1D0h+var_190], rax
0x180013e1e  lea     r8, asc_1800233AC; ": {}"
0x180013e25  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180013e2a  mov     edx, 0C1h
0x180013e2f  jmp     loc_180013FF2
0x180013e34  mov     edx, [rbp+0D0h+lDistanceToMove]; lDistanceToMove
0x180013e37  xor     r9d, r9d; dwMoveMethod
0x180013e3a  xor     r8d, r8d; lpDistanceToMoveHigh
0x180013e3d  mov     rcx, rbx; hFile
0x180013e40  call    cs:__imp_SetFilePointer
0x180013e46  cmp     eax, 0FFFFFFFFh
0x180013e49  jnz     short loc_180013EB1
0x180013e4b  call    cs:__imp_GetLastError
0x180013e51  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, 0; LogAdapter::Logger * LogAdapter::g_Logger
0x180013e59  mov     edi, eax
0x180013e5b  jz      short loc_180013E9F
0x180013e5d  lea     r9, [rsp+1D0h+var_188]
0x180013e62  lea     r8, aFailedToSeekTh; "Failed to seek the NT header in file: {"...
0x180013e69  call    ??$LogPartial@PEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogPartial<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180013e6e  test    edi, edi
0x180013e70  jg      short loc_180013E76
0x180013e72  mov     eax, edi
0x180013e74  jmp     short loc_180013E7E
0x180013e76  movzx   eax, di
0x180013e79  or      eax, 80070000h
0x180013e7e  mov     [rsp+1D0h+var_180], eax
0x180013e82  lea     r9, [rsp+1D0h+var_190]
0x180013e87  lea     rax, [rsp+1D0h+var_180]
0x180013e8c  mov     edx, esi
0x180013e8e  lea     r8, a0; ": {0}"
0x180013e95  mov     [rsp+1D0h+var_190], rax
0x180013e9a  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180013e9f  test    edi, edi
0x180013ea1  jz      loc_180014014
0x180013ea7  mov     edx, 0C4h
0x180013eac  jmp     loc_180013DC0
0x180013eb1  lea     r9, [rsp+1D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180013eb6  mov     qword ptr [rsp+1D0h+dwCreationDisposition], 0; lpOverlapped
0x180013ebf  mov     r8d, 108h; nNumberOfBytesToRead
0x180013ec5  lea     rdx, [rbp+0D0h+var_130]; lpBuffer
0x180013ec9  mov     rcx, rbx; hFile
0x180013ecc  call    cs:__imp_ReadFile
0x180013ed2  test    eax, eax
0x180013ed4  jnz     short loc_180013F3C
0x180013ed6  call    cs:__imp_GetLastError
0x180013edc  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, 0; LogAdapter::Logger * LogAdapter::g_Logger
0x180013ee4  mov     edi, eax
0x180013ee6  jz      short loc_180013F2A
0x180013ee8  lea     r9, [rsp+1D0h+var_188]
0x180013eed  lea     r8, aFailedToReadNt; "Failed to read NT header from file: {}"
0x180013ef4  call    ??$LogPartial@PEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogPartial<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180013ef9  test    edi, edi
0x180013efb  jg      short loc_180013F01
0x180013efd  mov     eax, edi
0x180013eff  jmp     short loc_180013F09
0x180013f01  movzx   eax, di
0x180013f04  or      eax, 80070000h
0x180013f09  mov     [rsp+1D0h+var_180], eax
0x180013f0d  lea     r9, [rsp+1D0h+var_190]
0x180013f12  lea     rax, [rsp+1D0h+var_180]
0x180013f17  mov     edx, esi
0x180013f19  lea     r8, a0; ": {0}"
0x180013f20  mov     [rsp+1D0h+var_190], rax
0x180013f25  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180013f2a  test    edi, edi
0x180013f2c  jz      loc_180014014
0x180013f32  mov     edx, 0C7h
0x180013f37  jmp     loc_180013DC0
0x180013f3c  cmp     [rbp+0D0h+var_130], 4550h
0x180013f43  jz      short loc_180013F8D
0x180013f45  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, 0; LogAdapter::Logger * LogAdapter::g_Logger
0x180013f4d  mov     edi, 8007000Bh
0x180013f52  mov     [rsp+1D0h+var_180], edi
0x180013f56  jz      short loc_180013F86
0x180013f58  lea     r9, [rsp+1D0h+var_188]
0x180013f5d  lea     r8, aReadInvalidNtH; "Read invalid NT header from file: {}"
0x180013f64  call    ??$LogPartial@PEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogPartial<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180013f69  lea     rax, [rsp+1D0h+var_180]
0x180013f6e  mov     edx, esi
0x180013f70  lea     r9, [rsp+1D0h+var_190]
0x180013f75  mov     [rsp+1D0h+var_190], rax
0x180013f7a  lea     r8, asc_1800233AC; ": {}"
0x180013f81  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180013f86  mov     edx, 0CAh
0x180013f8b  jmp     short loc_180013FF2
0x180013f8d  movzx   ecx, [rbp+0D0h+var_D4]
0x180013f91  sub     ecx, 1
0x180013f94  jz      short loc_18001400D
0x180013f96  sub     ecx, 1
0x180013f99  jz      short loc_18001400D
0x180013f9b  sub     ecx, 1
0x180013f9e  jz      short loc_18001400D
0x180013fa0  sub     ecx, 2
0x180013fa3  jz      short loc_180013FAA
0x180013fa5  cmp     ecx, 2
0x180013fa8  jnz     short loc_18001400D
0x180013faa  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, 0; LogAdapter::Logger * LogAdapter::g_Logger
0x180013fb2  mov     edi, 8007000Bh
0x180013fb7  mov     [rsp+1D0h+var_180], edi
0x180013fbb  jz      short loc_180013FED
0x180013fbd  lea     rax, [rsp+1D0h+var_188]
0x180013fc2  lea     r9, [rbp+0D0h+var_D4]
0x180013fc6  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax; int
0x180013fcb  call    ??$LogPartial@GPEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBGAEBQEB_W@Z; LogAdapter::Logger::LogPartial<ushort,wchar_t const *>(LogAdapter::LogLevel,char const * const,ushort const &,wchar_t const * const &)
0x180013fd0  lea     rax, [rsp+1D0h+var_180]
0x180013fd5  mov     edx, esi
0x180013fd7  lea     r9, [rsp+1D0h+var_190]
0x180013fdc  mov     [rsp+1D0h+var_190], rax
0x180013fe1  lea     r8, asc_1800233AC; ": {}"
0x180013fe8  call    ??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180013fed  mov     edx, 0DDh; void *
0x180013ff2  mov     rcx, [rbp+0D8h]; this
0x180013ff9  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180014000  mov     r9d, edi; char *
0x180014003  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014008  jmp     loc_180013D0B
0x18001400d  movzx   eax, [rbp+0D0h+var_12C]
0x180014011  mov     [rdi], ax
0x180014014  mov     rcx, rbx; Handle
0x180014017  call    cs:__imp_NtClose
0x18001401d  test    eax, eax
0x18001401f  jns     short loc_180014028
0x180014021  mov     ecx, 7
0x180014026  int     29h; Win8: RtlFailFast(ecx)
0x180014028  xor     eax, eax
0x18001402a  mov     rcx, [rbp+0D0h+var_20]
0x180014031  xor     rcx, rsp; StackCookie
0x180014034  call    __security_check_cookie
  ... truncated ...
```
