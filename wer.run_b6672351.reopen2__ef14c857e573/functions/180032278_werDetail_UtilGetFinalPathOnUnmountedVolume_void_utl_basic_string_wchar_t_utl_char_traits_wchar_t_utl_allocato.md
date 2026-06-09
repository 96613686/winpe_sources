# _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x180032278`
- end: `0x180032789`
- name: `?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1297`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180031ff4`

## callees

- `0x180007fd8`
- `0x180008004`
- `0x180008e38`
- `0x18000da00`
- `0x18000db80`
- `0x1800172c0`
- `0x18001b044`
- `0x18001c368`
- `0x1800235c8`
- `0x180023d28`
- `0x180025560`
- `0x18002850c`
- `0x180031cd0`
- `0x180032278`
- `0x18004cab0`
- `0x180053300`
- `0x1800627fc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180032553`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180032553`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003247e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003247e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326f3`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800322ed`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800324f8`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800322ed`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800324f8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180032456`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180032456`

## string_xrefs

- `0x1800323b2`: `StorePath`

## pseudocode

```c
__int64 __fastcall _werDetail::UtilGetFinalPathOnUnmountedVolume(void *a1, __int64 a2)
{
  DWORD FinalPathNameByHandleW; // eax
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  int String; // ebx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  char *v11; // rdx
  HANDLE FileW; // rax
  DWORD v13; // eax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  __int16 *v17; // rdx
  DWORD v18; // eax
  unsigned __int64 v19; // rbx
  __int64 v20; // rdx
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  DWORD v30; // eax
  DWORD LastError; // eax
  void *v33; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v34; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-B0h] BYREF
  LPCWCH lpString1; // [rsp+58h] [rbp-A8h] BYREF
  _WORD *v37; // [rsp+60h] [rbp-A0h]
  _WORD v38[8]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+78h] [rbp-88h] BYREF
  _WORD v40[12]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR szFilePath[264]; // [rsp+A0h] [rbp-60h] BYREF

  lpFileName[0] = v40;
  hFile = 0;
  lpFileName[1] = v40;
  v40[0] = 0;
  lpString1 = v38;
  v38[0] = 0;
  v37 = v38;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(a1, szFilePath, 0x104u, 2u);
  if ( !FinalPathNameByHandleW )
  {
    LastError = GetLastError();
LABEL_49:
    String = ERROR_HR_FROM_WIN32(LastError);
    if ( (unsigned int)dword_1800DE000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      goto LABEL_54;
    v11 = byte_1800CBF8D;
LABEL_52:
    LODWORD(v33) = String;
    goto LABEL_53;
  }
  if ( FinalPathNameByHandleW >= 0x104 )
  {
    LastError = 111;
    goto LABEL_49;
  }
  if ( (unsigned int)dword_1800DE000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
  {
    v33 = szFilePath;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v4,
      (unsigned int)byte_1800CBFC9,
      v5,
      v6,
      (__int64)&v33);
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &lpString1,
                           szFilePath) )
  {
    String = -2147024882;
    if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
    {
      LODWORD(v33) = -2147024882;
      v11 = byte_1800CC00B;
LABEL_53:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v8,
        (_DWORD)v11,
        v9,
        v10,
        (__int64)&v33);
      goto LABEL_54;
    }
    goto LABEL_54;
  }
  String = UtilRegGetString(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\Windows Error Reporting",
             L"StorePath",
             (__int64)lpFileName,
             0,
             1);
  if ( String < 0 )
  {
    if ( (unsigned int)dword_1800DE000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      goto LABEL_54;
    v11 = &byte_1800CC047;
    goto LABEL_52;
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::ends_with(lpFileName)
    && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                           lpFileName,
                           92) )
  {
    String = -2147024882;
    goto LABEL_54;
  }
  FileW = CreateFileW(lpFileName[0], 0x80u, 1u, 0, 3u, 0x2000080u, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, FileW);
  if ( (unsigned __int64)hFile + 1 <= 1 )
  {
    v13 = GetLastError();
    String = ERROR_HR_FROM_WIN32(v13);
    if ( (unsigned int)dword_1800DE000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      goto LABEL_54;
    v17 = word_1800CC08A;
    goto LABEL_21;
  }
  v18 = GetFinalPathNameByHandleW(hFile, szFilePath, 0x104u, 2u);
  if ( !v18 )
  {
    v30 = GetLastError();
LABEL_44:
    String = ERROR_HR_FROM_WIN32(v30);
    if ( (unsigned int)dword_1800DE000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      goto LABEL_54;
    v17 = (__int16 *)byte_1800CC0D9;
LABEL_21:
    v34 = lpFileName[0];
    LODWORD(v33) = String;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      v14,
      (_DWORD)v17,
      v15,
      v16,
      (__int64)&v34,
      (__int64)&v33);
    goto LABEL_54;
  }
  if ( v18 >= 0x104 )
  {
    v30 = 111;
    goto LABEL_44;
  }
  v19 = -1;
  do
    ++v19;
  while ( szFilePath[v19] );
  if ( v37 - lpString1 >= v19 && CompareStringOrdinal(lpString1, v19, szFilePath, v19, 1) == 2 )
  {
    if ( (unsigned int)dword_1800DE000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
    {
      v34 = lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        v21,
        (unsigned int)&unk_1800CC128,
        v22,
        v23,
        (__int64)&v34);
    }
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(
                            &lpString1,
                            v20,
                            v19) )
    {
      if ( (unsigned int)dword_1800DE000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      {
        v34 = lpString1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
          v24,
          (unsigned int)&dword_1800CC1AC,
          v25,
          v26,
          (__int64)&v34);
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, &lpString1);
      String = 0;
    }
    else
    {
      String = -2147024882;
      if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      {
        LODWORD(v33) = -2147024882;
        v11 = (char *)&word_1800CC16E;
        goto LABEL_53;
      }
    }
  }
  else
  {
    String = -2147024735;
    if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
    {
      v34 = szFilePath;
      v33 = (void *)lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        v27,
        (unsigned int)byte_1800CC1F1,
        v28,
        v29,
        (__int64)&v33,
        (__int64)&v34);
    }
  }
LABEL_54:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpString1);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180032278  mov     [rsp-8+arg_10], rbx
0x18003227d  push    rbp
0x18003227e  push    rsi
0x18003227f  push    rdi
0x180032280  push    r14
0x180032282  push    r15
0x180032284  lea     rbp, [rsp-1C0h]
0x18003228c  sub     rsp, 2C0h
0x180032293  mov     rax, cs:__security_cookie
0x18003229a  xor     rax, rsp
0x18003229d  mov     [rbp+1E0h+var_30], rax
0x1800322a4  xor     r15d, r15d
0x1800322a7  lea     rax, [rbp+1E0h+var_258]
0x1800322ab  mov     [rsp+2E0h+lpFileName], rax
0x1800322b0  mov     r14, rdx
0x1800322b3  lea     rax, [rbp+1E0h+var_258]
0x1800322b7  mov     [rsp+2E0h+hFile], r15
0x1800322bc  mov     [rbp+1E0h+var_260], rax
0x1800322c0  lea     rdx, [rbp+1E0h+szFilePath]; lpszFilePath
0x1800322c4  lea     rax, [rsp+2E0h+var_278]
0x1800322c9  mov     [rbp+1E0h+var_258], r15w
0x1800322ce  mov     [rsp+2E0h+lpString1], rax
0x1800322d3  lea     r9d, [r15+2]; dwFlags
0x1800322d7  lea     rax, [rsp+2E0h+var_278]
0x1800322dc  mov     [rsp+2E0h+var_278], r15w
0x1800322e2  mov     r8d, 104h; cchFilePath
0x1800322e8  mov     [rsp+2E0h+var_280], rax
0x1800322ed  call    cs:__imp_GetFinalPathNameByHandleW
0x1800322f4  nop     dword ptr [rax+rax+00h]
0x1800322f9  test    eax, eax
0x1800322fb  jz      loc_1800326F3
0x180032301  cmp     eax, 104h
0x180032306  jnb     loc_1800326EC
0x18003230c  mov     eax, cs:dword_1800DE000
0x180032312  lea     edi, [r15+8]
0x180032316  lea     rsi, dword_1800DE000
0x18003231d  cmp     eax, 4
0x180032320  jbe     short loc_18003234F
0x180032322  mov     edx, edi
0x180032324  mov     rcx, rsi
0x180032327  call    _tlgKeywordOn
0x18003232c  test    al, al
0x18003232e  jz      short loc_18003234F
0x180032330  lea     rax, [rbp+1E0h+szFilePath]
0x180032334  mov     [rsp+2E0h+var_2A0], rax
0x180032339  lea     rdx, byte_1800CBFC9
0x180032340  lea     rax, [rsp+2E0h+var_2A0]
0x180032345  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x18003234a  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18003234f  lea     rdx, [rbp+1E0h+szFilePath]
0x180032353  lea     rcx, [rsp+2E0h+lpString1]
0x180032358  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18003235d  test    al, al
0x18003235f  jnz     short loc_18003239C
0x180032361  mov     eax, cs:dword_1800DE000
0x180032367  mov     ebx, 8007000Eh
0x18003236c  cmp     eax, 2
0x18003236f  jbe     loc_180032742
0x180032375  mov     rdx, rdi
0x180032378  mov     rcx, rsi
0x18003237b  call    _tlgKeywordOn
0x180032380  test    al, al
0x180032382  jz      loc_180032742
0x180032388  mov     dword ptr [rsp+2E0h+var_2A0], 8007000Eh
0x180032390  lea     rdx, byte_1800CC00B
0x180032397  jmp     loc_180032733
0x18003239c  mov     byte ptr [rsp+2E0h+hTemplateFile], 1; char
0x1800323a1  lea     rax, [rsp+2E0h+lpFileName]
0x1800323a6  mov     byte ptr [rsp+2E0h+dwFlagsAndAttributes], r15b; char
0x1800323ab  lea     r9, Src
0x1800323b2  lea     r8, aStorepath; "StorePath"
0x1800323b9  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax; __int64
0x1800323be  lea     rdx, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\Windows E"...
0x1800323c5  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800323cc  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x1800323d1  mov     ebx, eax
0x1800323d3  test    eax, eax
0x1800323d5  jns     short loc_180032405
0x1800323d7  mov     ecx, cs:dword_1800DE000
0x1800323dd  cmp     ecx, 2
0x1800323e0  jbe     loc_180032742
0x1800323e6  mov     rdx, rdi
0x1800323e9  mov     rcx, rsi
0x1800323ec  call    _tlgKeywordOn
0x1800323f1  test    al, al
0x1800323f3  jz      loc_180032742
0x1800323f9  lea     rdx, byte_1800CC047
0x180032400  jmp     loc_18003272F
0x180032405  lea     rcx, [rsp+2E0h+lpFileName]
0x18003240a  call    ?ends_with@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::ends_with(wchar_t)
0x18003240f  test    al, al
0x180032411  jnz     short loc_180032430
0x180032413  mov     edx, 5Ch ; '\'
0x180032418  lea     rcx, [rsp+2E0h+lpFileName]
0x18003241d  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x180032422  test    al, al
0x180032424  jnz     short loc_180032430
0x180032426  mov     ebx, 8007000Eh
0x18003242b  jmp     loc_180032742
0x180032430  mov     rcx, [rsp+2E0h+lpFileName]; lpFileName
0x180032435  xor     r9d, r9d; lpSecurityAttributes
0x180032438  mov     [rsp+2E0h+hTemplateFile], r15; hTemplateFile
0x18003243d  mov     edx, 80h; dwDesiredAccess
0x180032442  mov     [rsp+2E0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x18003244a  mov     [rsp+2E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180032452  lea     r8d, [r9+1]; dwShareMode
0x180032456  call    cs:__imp_CreateFileW
0x18003245d  nop     dword ptr [rax+rax+00h]
0x180032462  mov     rdx, rax
0x180032465  lea     rcx, [rsp+2E0h+hFile]
0x18003246a  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18003246f  mov     rcx, [rsp+2E0h+hFile]; hFile
0x180032474  lea     rax, [rcx+1]
0x180032478  cmp     rax, 1
0x18003247c  ja      short loc_1800324E8
0x18003247e  call    cs:__imp_GetLastError
0x180032485  nop     dword ptr [rax+rax+00h]
0x18003248a  mov     ecx, eax; unsigned int
0x18003248c  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180032491  mov     ebx, eax
0x180032493  mov     eax, cs:dword_1800DE000
0x180032499  cmp     eax, 2
0x18003249c  jbe     loc_180032742
0x1800324a2  mov     rdx, rdi
0x1800324a5  mov     rcx, rsi
0x1800324a8  call    _tlgKeywordOn
0x1800324ad  test    al, al
0x1800324af  jz      loc_180032742
0x1800324b5  lea     rdx, word_1800CC08A
0x1800324bc  mov     rax, [rsp+2E0h+lpFileName]
0x1800324c1  mov     [rsp+2E0h+var_298], rax
0x1800324c6  lea     rax, [rsp+2E0h+var_2A0]
0x1800324cb  mov     qword ptr [rsp+2E0h+dwFlagsAndAttributes], rax
0x1800324d0  lea     rax, [rsp+2E0h+var_298]
0x1800324d5  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x1800324da  mov     dword ptr [rsp+2E0h+var_2A0], ebx
0x1800324de  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1800324e3  jmp     loc_180032742
0x1800324e8  mov     r9d, 2; dwFlags
0x1800324ee  lea     rdx, [rbp+1E0h+szFilePath]; lpszFilePath
0x1800324f2  mov     r8d, 104h; cchFilePath
0x1800324f8  call    cs:__imp_GetFinalPathNameByHandleW
0x1800324ff  nop     dword ptr [rax+rax+00h]
0x180032504  test    eax, eax
0x180032506  jz      loc_1800326B1
0x18003250c  cmp     eax, 104h
0x180032511  jnb     loc_1800326AA
0x180032517  lea     rax, [rbp+1E0h+szFilePath]
0x18003251b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003251f  inc     rbx
0x180032522  cmp     [rax+rbx*2], r15w
0x180032527  jnz     short loc_18003251F
0x180032529  mov     rax, [rsp+2E0h+var_280]
0x18003252e  mov     rcx, [rsp+2E0h+lpString1]; lpString1
0x180032533  sub     rax, rcx
0x180032536  sar     rax, 1
0x180032539  cmp     rax, rbx
0x18003253c  jb      loc_18003264B
0x180032542  mov     r9d, ebx; cchCount2
0x180032545  mov     [rsp+2E0h+dwCreationDisposition], 1; bIgnoreCase
0x18003254d  lea     r8, [rbp+1E0h+szFilePath]; lpString2
0x180032551  mov     edx, ebx; cchCount1
0x180032553  call    cs:__imp_CompareStringOrdinal
0x18003255a  nop     dword ptr [rax+rax+00h]
0x18003255f  cmp     eax, 2
0x180032562  jnz     loc_18003264B
0x180032568  mov     eax, cs:dword_1800DE000
0x18003256e  cmp     eax, 4
0x180032571  jbe     short loc_1800325A2
0x180032573  mov     rdx, rdi
0x180032576  mov     rcx, rsi
0x180032579  call    _tlgKeywordOn
0x18003257e  test    al, al
0x180032580  jz      short loc_1800325A2
0x180032582  mov     rax, [rsp+2E0h+lpString1]
0x180032587  lea     rdx, unk_1800CC128
0x18003258e  mov     [rsp+2E0h+var_298], rax
0x180032593  lea     rax, [rsp+2E0h+var_298]
0x180032598  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x18003259d  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1800325a2  mov     rax, [rbp+1E0h+var_260]
0x1800325a6  lea     rcx, [rsp+2E0h+lpString1]
0x1800325ab  mov     r9, [rsp+2E0h+lpFileName]
0x1800325b0  mov     r8, rbx
0x1800325b3  sub     rax, r9
0x1800325b6  sar     rax, 1
0x1800325b9  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x1800325be  call    ?replace@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K0PEB_W0@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)
0x1800325c3  test    al, al
0x1800325c5  mov     eax, cs:dword_1800DE000
0x1800325cb  jnz     short loc_180032602
0x1800325cd  mov     ebx, 8007000Eh
0x1800325d2  cmp     eax, 2
0x1800325d5  jbe     loc_180032742
0x1800325db  mov     rdx, rdi
0x1800325de  mov     rcx, rsi
0x1800325e1  call    _tlgKeywordOn
0x1800325e6  test    al, al
0x1800325e8  jz      loc_180032742
0x1800325ee  mov     dword ptr [rsp+2E0h+var_2A0], 8007000Eh
0x1800325f6  lea     rdx, word_1800CC16E
0x1800325fd  jmp     loc_180032733
0x180032602  cmp     eax, 4
0x180032605  jbe     short loc_180032636
0x180032607  mov     rdx, rdi
0x18003260a  mov     rcx, rsi
0x18003260d  call    _tlgKeywordOn
0x180032612  test    al, al
0x180032614  jz      short loc_180032636
0x180032616  mov     rax, [rsp+2E0h+lpString1]
0x18003261b  lea     rdx, dword_1800CC1AC
0x180032622  mov     [rsp+2E0h+var_298], rax
0x180032627  lea     rax, [rsp+2E0h+var_298]
0x18003262c  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180032631  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180032636  lea     rdx, [rsp+2E0h+lpString1]
0x18003263b  mov     rcx, r14
0x18003263e  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x180032643  mov     ebx, r15d
0x180032646  jmp     loc_180032742
0x18003264b  mov     eax, cs:dword_1800DE000
0x180032651  mov     ebx, 800700A1h
0x180032656  cmp     eax, 2
0x180032659  jbe     loc_180032742
0x18003265f  mov     rdx, rdi
0x180032662  mov     rcx, rsi
0x180032665  call    _tlgKeywordOn
0x18003266a  test    al, al
0x18003266c  jz      loc_180032742
0x180032672  lea     rax, [rbp+1E0h+szFilePath]
0x180032676  mov     [rsp+2E0h+var_298], rax
0x18003267b  lea     rdx, byte_1800CC1F1
0x180032682  mov     rax, [rsp+2E0h+lpString1]
0x180032687  mov     [rsp+2E0h+var_2A0], rax
0x18003268c  lea     rax, [rsp+2E0h+var_298]
0x180032691  mov     qword ptr [rsp+2E0h+dwFlagsAndAttributes], rax
0x180032696  lea     rax, [rsp+2E0h+var_2A0]
0x18003269b  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x1800326a0  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x1800326a5  jmp     loc_180032742
0x1800326aa  mov     eax, 6Fh ; 'o'
0x1800326af  jmp     short loc_1800326BD
0x1800326b1  call    cs:__imp_GetLastError
0x1800326b8  nop     dword ptr [rax+rax+00h]
0x1800326bd  mov     ecx, eax; unsigned int
0x1800326bf  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800326c4  mov     ebx, eax
0x1800326c6  mov     eax, cs:dword_1800DE000
0x1800326cc  cmp     eax, 2
0x1800326cf  jbe     short loc_180032742
0x1800326d1  mov     rdx, rdi
0x1800326d4  mov     rcx, rsi
0x1800326d7  call    _tlgKeywordOn
0x1800326dc  test    al, al
0x1800326de  jz      short loc_180032742
0x1800326e0  lea     rdx, byte_1800CC0D9
0x1800326e7  jmp     loc_1800324BC
0x1800326ec  mov     eax, 6Fh ; 'o'
0x1800326f1  jmp     short loc_1800326FF
0x1800326f3  call    cs:__imp_GetLastError
0x1800326fa  nop     dword ptr [rax+rax+00h]
0x1800326ff  mov     ecx, eax; unsigned int
0x180032701  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180032706  mov     ebx, eax
0x180032708  mov     eax, cs:dword_1800DE000
0x18003270e  cmp     eax, 2
0x180032711  jbe     short loc_180032742
0x180032713  mov     edx, 8
0x180032718  lea     rcx, dword_1800DE000
0x18003271f  call    _tlgKeywordOn
0x180032724  test    al, al
0x180032726  jz      short loc_180032742
0x180032728  lea     rdx, byte_1800CBF8D
0x18003272f  mov     dword ptr [rsp+2E0h+var_2A0], ebx
0x180032733  lea     rax, [rsp+2E0h+var_2A0]
0x180032738  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x18003273d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180032742  lea     rcx, [rsp+2E0h+lpString1]; void *
0x180032747  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18003274c  lea     rcx, [rsp+2E0h+lpFileName]; void *
0x180032751  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180032756  lea     rcx, [rsp+2E0h+hFile]
0x18003275b  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180032760  mov     eax, ebx
0x180032762  mov     rcx, [rbp+1E0h+var_30]
0x180032769  xor     rcx, rsp; StackCookie
0x18003276c  call    __security_check_cookie
0x180032771  mov     rbx, [rsp+2E0h+arg_10]
0x180032779  add     rsp, 2C0h
0x180032780  pop     r15
0x180032782  pop     r14
0x180032784  pop     rdi
0x180032785  pop     rsi
0x180032786  pop     rbp
0x180032787  retn
```
