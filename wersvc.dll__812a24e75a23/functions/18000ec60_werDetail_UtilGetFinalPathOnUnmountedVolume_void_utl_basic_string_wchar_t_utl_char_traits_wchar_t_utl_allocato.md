# _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x18000ec60`
- end: `0x18000f268`
- name: `?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1544`
- prototype: `__int64 __fastcall(void *, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18000e8a8`

## callees

- `0x18000113c`
- `0x1800011dc`
- `0x18000126c`
- `0x18000134c`
- `0x1800029d0`
- `0x1800029f4`
- `0x180008dac`
- `0x18000ec60`
- `0x18000fff0`
- `0x180011648`
- `0x1800117f4`
- `0x1800118a4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ef72`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ef72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f10b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f171`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f10b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f171`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000ecd7`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000ef23`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000ecd7`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000ef23`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ee72`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ee72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f239`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f239`

## string_xrefs

- `0x18000edc0`: `StorePath`

## pseudocode

```c
__int64 __fastcall _werDetail::UtilGetFinalPathOnUnmountedVolume(void *a1, __int64 a2)
{
  char *FileW; // rbx
  DWORD FinalPathNameByHandleW; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // r8
  signed int LastError; // edi
  char *v10; // rdx
  const WCHAR *v11; // rcx
  signed int v12; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  __int16 *v16; // rdx
  DWORD v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  int *v24; // [rsp+40h] [rbp-C0h] BYREF
  int *v25; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v27; // [rsp+58h] [rbp-A8h]
  _WORD v28[8]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWCH lpString1; // [rsp+70h] [rbp-90h] BYREF
  _WORD *v30; // [rsp+78h] [rbp-88h]
  _WORD v31[8]; // [rsp+80h] [rbp-80h] BYREF
  char v32[32]; // [rsp+90h] [rbp-70h] BYREF
  int **v33; // [rsp+B0h] [rbp-50h]
  __int64 v34; // [rsp+B8h] [rbp-48h]
  WCHAR szFilePath[264]; // [rsp+C0h] [rbp-40h] BYREF

  lpFileName = v28;
  v28[0] = 0;
  v27 = v28;
  v31[0] = 0;
  lpString1 = v31;
  v30 = v31;
  FileW = 0;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(a1, szFilePath, 0x104u, 2u);
  if ( !FinalPathNameByHandleW )
  {
    LastError = GetLastError();
    if ( LastError <= 0 )
    {
LABEL_69:
      if ( LastError >= 0 )
        LastError = -2147467259;
      if ( (unsigned int)dword_180047000 <= 2 || (qword_180047010 & 8) == 0 || (qword_180047018 & 8) != qword_180047018 )
        goto LABEL_77;
      v10 = byte_18003F065;
LABEL_75:
      LODWORD(v24) = LastError;
      goto LABEL_76;
    }
LABEL_68:
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_69;
  }
  if ( FinalPathNameByHandleW >= 0x104 )
  {
    LOWORD(LastError) = 111;
    goto LABEL_68;
  }
  if ( (unsigned int)dword_180047000 > 4 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
  {
    v24 = (int *)szFilePath;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      qword_180047018,
      (__int64)byte_18003F023,
      v5,
      v6,
      &v24);
  }
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( szFilePath[v8] );
  if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
          (__int64)&lpString1,
          szFilePath,
          v8) )
  {
    LastError = -2147024882;
    if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
    {
      LODWORD(v24) = -2147024882;
      v10 = &byte_18003EFE7;
LABEL_76:
      v34 = 4;
      v33 = &v24;
      tlgWriteTransfer_EventWriteTransfer(&dword_180047000, v10, 0, 0, 3, v32);
      goto LABEL_77;
    }
    goto LABEL_77;
  }
  LastError = UtilRegGetString(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\Windows Error Reporting",
                L"StorePath",
                (__int64)&lpFileName,
                dwFlagsAndAttributes);
  if ( LastError < 0 )
  {
    if ( (unsigned int)dword_180047000 <= 2 || (qword_180047010 & 8) == 0 || (qword_180047018 & 8) != qword_180047018 )
      goto LABEL_77;
    v10 = (char *)&dword_18003EFA4;
    goto LABEL_75;
  }
  v11 = lpFileName;
  if ( lpFileName == v27 || *(v27 - 1) != 92 )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             &lpFileName,
                             92) )
    {
      LastError = -2147024882;
      goto LABEL_77;
    }
    v11 = lpFileName;
  }
  FileW = (char *)CreateFileW(v11, 0x80u, 1u, 0, 3u, 0x2000080u, 0);
  if ( FileW == (char *)-1LL || FileW + 1 == (char *)1 )
  {
    v12 = GetLastError();
    LastError = v12;
    if ( v12 > 0 )
      LastError = (unsigned __int16)v12 | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    if ( (unsigned int)dword_180047000 <= 2 )
      goto LABEL_77;
    v15 = qword_180047018;
    if ( (qword_180047010 & 8) == 0 || (qword_180047018 & 8) != qword_180047018 )
      goto LABEL_77;
    v16 = (__int16 *)byte_18003EF55;
    goto LABEL_33;
  }
  v17 = GetFinalPathNameByHandleW(FileW, szFilePath, 0x104u, 2u);
  if ( !v17 )
  {
    LastError = GetLastError();
    if ( LastError <= 0 )
    {
LABEL_60:
      if ( LastError >= 0 )
        LastError = -2147467259;
      if ( (unsigned int)dword_180047000 <= 2 )
        goto LABEL_77;
      v15 = qword_180047018;
      if ( (qword_180047010 & 8) == 0 || (qword_180047018 & 8) != qword_180047018 )
        goto LABEL_77;
      v16 = &word_18003EF06;
LABEL_33:
      v25 = (int *)lpFileName;
      LODWORD(v24) = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v15,
        (__int64)v16,
        v13,
        v14,
        &v25,
        (__int64)&v24);
      goto LABEL_77;
    }
LABEL_59:
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_60;
  }
  if ( v17 >= 0x104 )
  {
    LOWORD(LastError) = 111;
    goto LABEL_59;
  }
  do
    ++v7;
  while ( szFilePath[v7] );
  if ( v30 - lpString1 >= v7 && CompareStringOrdinal(lpString1, v7, szFilePath, v7, 1) == 2 )
  {
    if ( (unsigned int)dword_180047000 > 4 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
    {
      v25 = (int *)lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        qword_180047018,
        (__int64)&unk_18003EEC0,
        v13,
        v14,
        &v25);
    }
    if ( utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(
           (char **)&lpString1,
           v18,
           v7,
           (__int16 *)lpFileName,
           v27 - lpFileName) )
    {
      if ( (unsigned int)dword_180047000 > 4 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
      {
        v25 = (int *)lpString1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
          v19,
          (__int64)byte_18003EE3D,
          v20,
          v21,
          &v25);
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, &lpString1);
      LastError = 0;
    }
    else
    {
      LastError = -2147024882;
      if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
      {
        LODWORD(v24) = -2147024882;
        v10 = (char *)word_18003EE82;
        goto LABEL_76;
      }
    }
  }
  else
  {
    LastError = -2147024735;
    if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
    {
      v25 = (int *)szFilePath;
      v24 = (int *)lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        qword_180047018,
        (__int64)byte_18003EDE9,
        v13,
        v14,
        &v24,
        &v25);
    }
  }
LABEL_77:
  if ( lpString1 != v31 )
    operator delete((void *)lpString1, (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFileName != v28 )
    operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
  if ( (unsigned __int64)(FileW + 1) > 1 )
    CloseHandle(FileW);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000ec60  mov     [rsp-8+arg_10], rbx
0x18000ec65  push    rbp
0x18000ec66  push    rdi
0x18000ec67  push    r12
0x18000ec69  push    r13
0x18000ec6b  push    r14
0x18000ec6d  lea     rbp, [rsp-1E0h]
0x18000ec75  sub     rsp, 2E0h
0x18000ec7c  mov     rax, cs:__security_cookie
0x18000ec83  xor     rax, rsp
0x18000ec86  mov     [rbp+200h+var_30], rax
0x18000ec8d  xor     r13d, r13d
0x18000ec90  lea     rax, [rsp+300h+var_2A0]
0x18000ec95  mov     [rsp+300h+lpFileName], rax
0x18000ec9a  mov     r12, rdx
0x18000ec9d  lea     rax, [rsp+300h+var_2A0]
0x18000eca2  mov     [rsp+300h+var_2A0], r13w
0x18000eca8  mov     [rsp+300h+var_2A8], rax
0x18000ecad  lea     rdx, [rbp+200h+szFilePath]; lpszFilePath
0x18000ecb1  lea     rax, [rbp+200h+var_280]
0x18000ecb5  mov     [rbp+200h+var_280], r13w
0x18000ecba  mov     [rsp+300h+lpString1], rax
0x18000ecbf  lea     r9d, [r13+2]; dwFlags
0x18000ecc3  lea     rax, [rbp+200h+var_280]
0x18000ecc7  mov     edi, 104h
0x18000eccc  mov     r8d, edi; cchFilePath
0x18000eccf  mov     [rsp+300h+var_288], rax
0x18000ecd4  mov     ebx, r13d
0x18000ecd7  call    cs:__imp_GetFinalPathNameByHandleW
0x18000ecdd  test    eax, eax
0x18000ecdf  jz      loc_18000F171
0x18000ece5  cmp     eax, edi
0x18000ece7  jnb     loc_18000F16A
0x18000eced  mov     eax, cs:dword_180047000
0x18000ecf3  cmp     eax, 4
0x18000ecf6  jbe     short loc_18000ED34
0x18000ecf8  mov     rcx, cs:qword_180047018
0x18000ecff  mov     rax, cs:qword_180047010
0x18000ed06  test    al, 8
0x18000ed08  jz      short loc_18000ED34
0x18000ed0a  mov     rax, rcx
0x18000ed0d  and     eax, 8
0x18000ed10  cmp     rax, rcx
0x18000ed13  jnz     short loc_18000ED34
0x18000ed15  lea     rax, [rbp+200h+szFilePath]
0x18000ed19  mov     [rsp+300h+var_2C0], rax
0x18000ed1e  lea     rdx, byte_18003F023
0x18000ed25  lea     rax, [rsp+300h+var_2C0]
0x18000ed2a  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x18000ed2f  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18000ed34  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000ed38  lea     rax, [rbp+200h+szFilePath]
0x18000ed3c  mov     r8, r14
0x18000ed3f  inc     r8
0x18000ed42  cmp     [rax+r8*2], r13w
0x18000ed47  jnz     short loc_18000ED3F
0x18000ed49  lea     rdx, [rbp+200h+szFilePath]
0x18000ed4d  lea     rcx, [rsp+300h+lpString1]
0x18000ed52  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18000ed57  test    al, al
0x18000ed59  jnz     short loc_18000EDA8
0x18000ed5b  mov     eax, cs:dword_180047000
0x18000ed61  mov     edi, 8007000Eh
0x18000ed66  cmp     eax, 2
0x18000ed69  jbe     loc_18000F1F7
0x18000ed6f  mov     rcx, cs:qword_180047018
0x18000ed76  mov     rax, cs:qword_180047010
0x18000ed7d  test    al, 8
0x18000ed7f  jz      loc_18000F1F7
0x18000ed85  mov     rax, rcx
0x18000ed88  and     eax, 8
0x18000ed8b  cmp     rax, rcx
0x18000ed8e  jnz     loc_18000F1F7
0x18000ed94  mov     dword ptr [rsp+300h+var_2C0], 8007000Eh
0x18000ed9c  lea     rdx, byte_18003EFE7
0x18000eda3  jmp     loc_18000F1C3
0x18000eda8  lea     rax, [rsp+300h+lpFileName]
0x18000edad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000edb4  lea     r9, dword_180039414
0x18000edbb  mov     qword ptr [rsp+300h+dwCreationDisposition], rax; __int64
0x18000edc0  lea     r8, aStorepath; "StorePath"
0x18000edc7  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\Windows E"...
0x18000edce  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x18000edd3  mov     edi, eax
0x18000edd5  test    eax, eax
0x18000edd7  jns     short loc_18000EE1A
0x18000edd9  mov     ecx, cs:dword_180047000
0x18000eddf  cmp     ecx, 2
0x18000ede2  jbe     loc_18000F1F7
0x18000ede8  mov     rax, cs:qword_180047018
0x18000edef  mov     rcx, cs:qword_180047010
0x18000edf6  test    cl, 8
0x18000edf9  jz      loc_18000F1F7
0x18000edff  mov     rcx, rax
0x18000ee02  and     ecx, 8
0x18000ee05  cmp     rcx, rax
0x18000ee08  jnz     loc_18000F1F7
0x18000ee0e  lea     rdx, dword_18003EFA4
0x18000ee15  jmp     loc_18000F1BF
0x18000ee1a  mov     rcx, [rsp+300h+lpFileName]
0x18000ee1f  mov     edx, 5Ch ; '\'
0x18000ee24  mov     rax, [rsp+300h+var_2A8]
0x18000ee29  cmp     rcx, rax
0x18000ee2c  jz      short loc_18000EE34
0x18000ee2e  cmp     dx, [rax-2]
0x18000ee32  jz      short loc_18000EE51
0x18000ee34  lea     rcx, [rsp+300h+lpFileName]
0x18000ee39  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x18000ee3e  test    al, al
0x18000ee40  jnz     short loc_18000EE4C
0x18000ee42  mov     edi, 8007000Eh
0x18000ee47  jmp     loc_18000F1F7
0x18000ee4c  mov     rcx, [rsp+300h+lpFileName]; lpFileName
0x18000ee51  xor     r9d, r9d; lpSecurityAttributes
0x18000ee54  mov     [rsp+300h+hTemplateFile], r13; hTemplateFile
0x18000ee59  mov     [rsp+300h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x18000ee61  mov     edx, 80h; dwDesiredAccess
0x18000ee66  mov     [rsp+300h+dwCreationDisposition], 3; dwCreationDisposition
0x18000ee6e  lea     r8d, [r9+1]; dwShareMode
0x18000ee72  call    cs:__imp_CreateFileW
0x18000ee78  mov     rbx, rax
0x18000ee7b  inc     rax
0x18000ee7e  cmp     rax, 1
0x18000ee82  ja      loc_18000EF0E
0x18000ee88  call    cs:__imp_GetLastError
0x18000ee8e  mov     edi, eax
0x18000ee90  test    eax, eax
0x18000ee92  jle     short loc_18000EE9D
0x18000ee94  movzx   edi, ax
0x18000ee97  or      edi, 80070000h
0x18000ee9d  test    edi, edi
0x18000ee9f  mov     eax, 80004005h
0x18000eea4  cmovns  edi, eax
0x18000eea7  mov     eax, cs:dword_180047000
0x18000eead  cmp     eax, 2
0x18000eeb0  jbe     loc_18000F1F7
0x18000eeb6  mov     rcx, cs:qword_180047018
0x18000eebd  mov     rax, cs:qword_180047010
0x18000eec4  test    al, 8
0x18000eec6  jz      loc_18000F1F7
0x18000eecc  mov     rax, rcx
0x18000eecf  and     eax, 8
0x18000eed2  cmp     rax, rcx
0x18000eed5  jnz     loc_18000F1F7
0x18000eedb  lea     rdx, byte_18003EF55
0x18000eee2  mov     rax, [rsp+300h+lpFileName]
0x18000eee7  mov     [rsp+300h+var_2B8], rax
0x18000eeec  lea     rax, [rsp+300h+var_2C0]
0x18000eef1  mov     qword ptr [rsp+300h+dwFlagsAndAttributes], rax
0x18000eef6  lea     rax, [rsp+300h+var_2B8]
0x18000eefb  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x18000ef00  mov     dword ptr [rsp+300h+var_2C0], edi
0x18000ef04  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18000ef09  jmp     loc_18000F1F7
0x18000ef0e  mov     edi, 104h
0x18000ef13  lea     rdx, [rbp+200h+szFilePath]; lpszFilePath
0x18000ef17  mov     r8d, edi; cchFilePath
0x18000ef1a  mov     r9d, 2; dwFlags
0x18000ef20  mov     rcx, rbx; hFile
0x18000ef23  call    cs:__imp_GetFinalPathNameByHandleW
0x18000ef29  test    eax, eax
0x18000ef2b  jz      loc_18000F10B
0x18000ef31  cmp     eax, edi
0x18000ef33  jnb     loc_18000F104
0x18000ef39  lea     rax, [rbp+200h+szFilePath]
0x18000ef3d  inc     r14
0x18000ef40  cmp     [rax+r14*2], r13w
0x18000ef45  jnz     short loc_18000EF3D
0x18000ef47  mov     rax, [rsp+300h+var_288]
0x18000ef4c  mov     rcx, [rsp+300h+lpString1]; lpString1
0x18000ef51  sub     rax, rcx
0x18000ef54  sar     rax, 1
0x18000ef57  cmp     rax, r14
0x18000ef5a  jb      loc_18000F093
0x18000ef60  mov     r9d, r14d; cchCount2
0x18000ef63  mov     [rsp+300h+dwCreationDisposition], 1; bIgnoreCase
0x18000ef6b  lea     r8, [rbp+200h+szFilePath]; lpString2
0x18000ef6f  mov     edx, r14d; cchCount1
0x18000ef72  call    cs:__imp_CompareStringOrdinal
0x18000ef78  cmp     eax, 2
0x18000ef7b  jnz     loc_18000F093
0x18000ef81  mov     eax, cs:dword_180047000
0x18000ef87  cmp     eax, 4
0x18000ef8a  jbe     short loc_18000EFC9
0x18000ef8c  mov     rcx, cs:qword_180047018
0x18000ef93  mov     rax, cs:qword_180047010
0x18000ef9a  test    al, 8
0x18000ef9c  jz      short loc_18000EFC9
0x18000ef9e  mov     rax, rcx
0x18000efa1  and     eax, 8
0x18000efa4  cmp     rax, rcx
0x18000efa7  jnz     short loc_18000EFC9
0x18000efa9  mov     rax, [rsp+300h+lpString1]
0x18000efae  lea     rdx, unk_18003EEC0
0x18000efb5  mov     [rsp+300h+var_2B8], rax
0x18000efba  lea     rax, [rsp+300h+var_2B8]
0x18000efbf  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x18000efc4  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18000efc9  mov     rax, [rsp+300h+var_2A8]
0x18000efce  lea     rcx, [rsp+300h+lpString1]
0x18000efd3  mov     r9, [rsp+300h+lpFileName]
0x18000efd8  mov     r8, r14
0x18000efdb  sub     rax, r9
0x18000efde  sar     rax, 1
0x18000efe1  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x18000efe6  call    ?replace@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K0PEB_W0@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)
0x18000efeb  test    al, al
0x18000efed  mov     eax, cs:dword_180047000
0x18000eff3  jnz     short loc_18000F03C
0x18000eff5  mov     edi, 8007000Eh
0x18000effa  cmp     eax, 2
0x18000effd  jbe     loc_18000F1F7
0x18000f003  mov     rcx, cs:qword_180047018
0x18000f00a  mov     rax, cs:qword_180047010
0x18000f011  test    al, 8
0x18000f013  jz      loc_18000F1F7
0x18000f019  mov     rax, rcx
0x18000f01c  and     eax, 8
0x18000f01f  cmp     rax, rcx
0x18000f022  jnz     loc_18000F1F7
0x18000f028  mov     dword ptr [rsp+300h+var_2C0], 8007000Eh
0x18000f030  lea     rdx, word_18003EE82
0x18000f037  jmp     loc_18000F1C3
0x18000f03c  cmp     eax, 4
0x18000f03f  jbe     short loc_18000F07E
0x18000f041  mov     rdx, cs:qword_180047018
0x18000f048  mov     rax, cs:qword_180047010
0x18000f04f  test    al, 8
0x18000f051  jz      short loc_18000F07E
0x18000f053  mov     rax, rdx
0x18000f056  and     eax, 8
0x18000f059  cmp     rax, rdx
0x18000f05c  jnz     short loc_18000F07E
0x18000f05e  mov     rax, [rsp+300h+lpString1]
0x18000f063  lea     rdx, byte_18003EE3D
0x18000f06a  mov     [rsp+300h+var_2B8], rax
0x18000f06f  lea     rax, [rsp+300h+var_2B8]
0x18000f074  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x18000f079  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18000f07e  lea     rdx, [rsp+300h+lpString1]
0x18000f083  mov     rcx, r12
0x18000f086  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18000f08b  mov     edi, r13d
0x18000f08e  jmp     loc_18000F1F7
0x18000f093  mov     eax, cs:dword_180047000
0x18000f099  mov     edi, 800700A1h
0x18000f09e  cmp     eax, 2
0x18000f0a1  jbe     loc_18000F1F7
0x18000f0a7  mov     rcx, cs:qword_180047018
0x18000f0ae  mov     rax, cs:qword_180047010
0x18000f0b5  test    al, 8
0x18000f0b7  jz      loc_18000F1F7
0x18000f0bd  mov     rax, rcx
0x18000f0c0  and     eax, 8
0x18000f0c3  cmp     rax, rcx
0x18000f0c6  jnz     loc_18000F1F7
0x18000f0cc  lea     rax, [rbp+200h+szFilePath]
0x18000f0d0  mov     [rsp+300h+var_2B8], rax
0x18000f0d5  lea     rdx, byte_18003EDE9
0x18000f0dc  mov     rax, [rsp+300h+lpString1]
0x18000f0e1  mov     [rsp+300h+var_2C0], rax
0x18000f0e6  lea     rax, [rsp+300h+var_2B8]
0x18000f0eb  mov     qword ptr [rsp+300h+dwFlagsAndAttributes], rax
0x18000f0f0  lea     rax, [rsp+300h+var_2C0]
0x18000f0f5  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x18000f0fa  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x18000f0ff  jmp     loc_18000F1F7
0x18000f104  mov     edi, 6Fh ; 'o'
0x18000f109  jmp     short loc_18000F117
0x18000f10b  call    cs:__imp_GetLastError
0x18000f111  mov     edi, eax
0x18000f113  test    eax, eax
0x18000f115  jle     short loc_18000F120
0x18000f117  movzx   edi, di
0x18000f11a  or      edi, 80070000h
0x18000f120  test    edi, edi
0x18000f122  mov     eax, 80004005h
0x18000f127  cmovns  edi, eax
0x18000f12a  mov     eax, cs:dword_180047000
0x18000f130  cmp     eax, 2
0x18000f133  jbe     loc_18000F1F7
0x18000f139  mov     rcx, cs:qword_180047018
0x18000f140  mov     rax, cs:qword_180047010
0x18000f147  test    al, 8
0x18000f149  jz      loc_18000F1F7
0x18000f14f  mov     rax, rcx
0x18000f152  and     eax, 8
0x18000f155  cmp     rax, rcx
0x18000f158  jnz     loc_18000F1F7
0x18000f15e  lea     rdx, word_18003EF06
0x18000f165  jmp     loc_18000EEE2
0x18000f16a  mov     edi, 6Fh ; 'o'
0x18000f16f  jmp     short loc_18000F17D
0x18000f171  call    cs:__imp_GetLastError
0x18000f177  mov     edi, eax
0x18000f179  test    eax, eax
0x18000f17b  jle     short loc_18000F186
0x18000f17d  movzx   edi, di
0x18000f180  or      edi, 80070000h
0x18000f186  test    edi, edi
  ... truncated ...
```
