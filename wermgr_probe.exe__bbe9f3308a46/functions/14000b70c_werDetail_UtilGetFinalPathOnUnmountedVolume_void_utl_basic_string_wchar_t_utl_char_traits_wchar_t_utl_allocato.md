# _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x14000b70c`
- end: `0x14000bcf8`
- name: `?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1516`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x14000b354`

## callees

- `0x140001008`
- `0x140001098`
- `0x140001270`
- `0x14000162c`
- `0x140003200`
- `0x140003224`
- `0x140004d70`
- `0x14000b70c`
- `0x14000c488`
- `0x14000db44`
- `0x14000dc18`
- `0x14000dd88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bb9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bc01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bb9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bc01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bcc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bcc9`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000b783`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000b9b3`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000b783`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000b9b3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000b902`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000b902`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000ba02`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000ba02`

## pseudocode

```c
__int64 __fastcall _werDetail::UtilGetFinalPathOnUnmountedVolume(void *a1, __int64 a2)
{
  char *FileW; // rbx
  DWORD FinalPathNameByHandleW; // eax
  int v5; // r8d
  int v6; // r9d
  unsigned __int64 v7; // r14
  __int64 v8; // r8
  int v9; // edx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  signed int LastError; // edi
  void *v14; // rdx
  const WCHAR *v15; // rcx
  signed int v16; // eax
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  void *v20; // rdx
  DWORD v21; // eax
  __int64 v22; // rdx
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  void *v28; // [rsp+40h] [rbp-C0h] BYREF
  void *v29; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v31; // [rsp+58h] [rbp-A8h]
  _WORD v32[8]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWCH lpString1; // [rsp+70h] [rbp-90h] BYREF
  _WORD *v34; // [rsp+78h] [rbp-88h]
  _WORD v35[8]; // [rsp+80h] [rbp-80h] BYREF
  char v36[32]; // [rsp+90h] [rbp-70h] BYREF
  void **v37; // [rsp+B0h] [rbp-50h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  WCHAR szFilePath[264]; // [rsp+C0h] [rbp-40h] BYREF

  lpFileName = v32;
  v32[0] = 0;
  v31 = v32;
  v35[0] = 0;
  lpString1 = v35;
  v34 = v35;
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
      if ( (unsigned int)dword_14002C000 <= 2 || (qword_14002C010 & 8) == 0 || (qword_14002C018 & 8) != qword_14002C018 )
        goto LABEL_77;
      v14 = &unk_140026CA0;
LABEL_75:
      LODWORD(v28) = LastError;
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
  if ( (unsigned int)dword_14002C000 > 4 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
  {
    v28 = szFilePath;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      qword_14002C018,
      (unsigned int)&unk_140026C5E,
      v5,
      v6,
      (__int64)&v28);
  }
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( szFilePath[v8] );
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &lpString1,
                           szFilePath,
                           v8) )
  {
    LastError = -2147024882;
    if ( (unsigned int)dword_14002C000 > 2 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
    {
      LODWORD(v28) = -2147024882;
      v14 = &unk_140026C22;
LABEL_76:
      v38 = 4;
      v37 = &v28;
      tlgWriteTransfer_EventWriteTransfer(&dword_14002C000, v14, 0, 0, 3, v36);
      goto LABEL_77;
    }
    goto LABEL_77;
  }
  LastError = UtilRegGetString(v10, v9, v11, v12, (__int64)&lpFileName, dwFlagsAndAttributes);
  if ( LastError < 0 )
  {
    if ( (unsigned int)dword_14002C000 <= 2 || (qword_14002C010 & 8) == 0 || (qword_14002C018 & 8) != qword_14002C018 )
      goto LABEL_77;
    v14 = &unk_140026BDF;
    goto LABEL_75;
  }
  v15 = lpFileName;
  if ( lpFileName == v31 || *(v31 - 1) != 92 )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             &lpFileName,
                             92) )
    {
      LastError = -2147024882;
      goto LABEL_77;
    }
    v15 = lpFileName;
  }
  FileW = (char *)CreateFileW(v15, 0x80u, 1u, 0, 3u, 0x2000080u, 0);
  if ( FileW == (char *)-1LL || FileW + 1 == (char *)1 )
  {
    v16 = GetLastError();
    LastError = v16;
    if ( v16 > 0 )
      LastError = (unsigned __int16)v16 | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    if ( (unsigned int)dword_14002C000 <= 2 )
      goto LABEL_77;
    v19 = qword_14002C018;
    if ( (qword_14002C010 & 8) == 0 || (qword_14002C018 & 8) != qword_14002C018 )
      goto LABEL_77;
    v20 = &unk_140026B90;
    goto LABEL_33;
  }
  v21 = GetFinalPathNameByHandleW(FileW, szFilePath, 0x104u, 2u);
  if ( !v21 )
  {
    LastError = GetLastError();
    if ( LastError <= 0 )
    {
LABEL_60:
      if ( LastError >= 0 )
        LastError = -2147467259;
      if ( (unsigned int)dword_14002C000 <= 2 )
        goto LABEL_77;
      v19 = qword_14002C018;
      if ( (qword_14002C010 & 8) == 0 || (qword_14002C018 & 8) != qword_14002C018 )
        goto LABEL_77;
      v20 = &unk_140026B41;
LABEL_33:
      v29 = (void *)lpFileName;
      LODWORD(v28) = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v19,
        (_DWORD)v20,
        v17,
        v18,
        (__int64)&v29,
        (__int64)&v28);
      goto LABEL_77;
    }
LABEL_59:
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_60;
  }
  if ( v21 >= 0x104 )
  {
    LOWORD(LastError) = 111;
    goto LABEL_59;
  }
  do
    ++v7;
  while ( szFilePath[v7] );
  if ( v34 - lpString1 >= v7 && CompareStringOrdinal(lpString1, v7, szFilePath, v7, 1) == 2 )
  {
    if ( (unsigned int)dword_14002C000 > 4 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
    {
      v29 = (void *)lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        qword_14002C018,
        (unsigned int)&unk_140026AFB,
        v17,
        v18,
        (__int64)&v29);
    }
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(
                            &lpString1,
                            v22,
                            v7) )
    {
      if ( (unsigned int)dword_14002C000 > 4 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
      {
        v29 = (void *)lpString1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
          v23,
          (unsigned int)&unk_140026A78,
          v24,
          v25,
          (__int64)&v29);
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, &lpString1);
      LastError = 0;
    }
    else
    {
      LastError = -2147024882;
      if ( (unsigned int)dword_14002C000 > 2 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
      {
        LODWORD(v28) = -2147024882;
        v14 = &unk_140026ABD;
        goto LABEL_76;
      }
    }
  }
  else
  {
    LastError = -2147024735;
    if ( (unsigned int)dword_14002C000 > 2 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
    {
      v29 = szFilePath;
      v28 = (void *)lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        qword_14002C018,
        (unsigned int)&unk_140026A24,
        v17,
        v18,
        (__int64)&v28,
        (__int64)&v29);
    }
  }
LABEL_77:
  if ( lpString1 != v35 )
    operator delete((void *)lpString1, (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFileName != v32 )
    operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
  if ( (unsigned __int64)(FileW + 1) > 1 )
    CloseHandle(FileW);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14000b70c  mov     [rsp-8+arg_10], rbx
0x14000b711  push    rbp
0x14000b712  push    rdi
0x14000b713  push    r12
0x14000b715  push    r13
0x14000b717  push    r14
0x14000b719  lea     rbp, [rsp-1E0h]
0x14000b721  sub     rsp, 2E0h
0x14000b728  mov     rax, cs:__security_cookie
0x14000b72f  xor     rax, rsp
0x14000b732  mov     [rbp+200h+var_30], rax
0x14000b739  xor     r13d, r13d
0x14000b73c  lea     rax, [rsp+300h+var_2A0]
0x14000b741  mov     [rsp+300h+lpFileName], rax
0x14000b746  mov     r12, rdx
0x14000b749  lea     rax, [rsp+300h+var_2A0]
0x14000b74e  mov     [rsp+300h+var_2A0], r13w
0x14000b754  mov     [rsp+300h+var_2A8], rax
0x14000b759  lea     rdx, [rbp+200h+szFilePath]; lpszFilePath
0x14000b75d  lea     rax, [rbp+200h+var_280]
0x14000b761  mov     [rbp+200h+var_280], r13w
0x14000b766  mov     [rsp+300h+lpString1], rax
0x14000b76b  lea     r9d, [r13+2]; dwFlags
0x14000b76f  lea     rax, [rbp+200h+var_280]
0x14000b773  mov     edi, 104h
0x14000b778  mov     r8d, edi; cchFilePath
0x14000b77b  mov     [rsp+300h+var_288], rax
0x14000b780  mov     ebx, r13d
0x14000b783  call    cs:__imp_GetFinalPathNameByHandleW
0x14000b789  test    eax, eax
0x14000b78b  jz      loc_14000BC01
0x14000b791  cmp     eax, edi
0x14000b793  jnb     loc_14000BBFA
0x14000b799  mov     eax, cs:dword_14002C000
0x14000b79f  cmp     eax, 4
0x14000b7a2  jbe     short loc_14000B7E0
0x14000b7a4  mov     rcx, cs:qword_14002C018
0x14000b7ab  mov     rax, cs:qword_14002C010
0x14000b7b2  test    al, 8
0x14000b7b4  jz      short loc_14000B7E0
0x14000b7b6  mov     rax, rcx
0x14000b7b9  and     eax, 8
0x14000b7bc  cmp     rax, rcx
0x14000b7bf  jnz     short loc_14000B7E0
0x14000b7c1  lea     rax, [rbp+200h+szFilePath]
0x14000b7c5  mov     [rsp+300h+var_2C0], rax
0x14000b7ca  lea     rdx, unk_140026C5E
0x14000b7d1  lea     rax, [rsp+300h+var_2C0]
0x14000b7d6  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x14000b7db  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x14000b7e0  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000b7e4  lea     rax, [rbp+200h+szFilePath]
0x14000b7e8  mov     r8, r14
0x14000b7eb  inc     r8
0x14000b7ee  cmp     [rax+r8*2], r13w
0x14000b7f3  jnz     short loc_14000B7EB
0x14000b7f5  lea     rdx, [rbp+200h+szFilePath]
0x14000b7f9  lea     rcx, [rsp+300h+lpString1]
0x14000b7fe  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14000b803  test    al, al
0x14000b805  jnz     short loc_14000B854
0x14000b807  mov     eax, cs:dword_14002C000
0x14000b80d  mov     edi, 8007000Eh
0x14000b812  cmp     eax, 2
0x14000b815  jbe     loc_14000BC87
0x14000b81b  mov     rcx, cs:qword_14002C018
0x14000b822  mov     rax, cs:qword_14002C010
0x14000b829  test    al, 8
0x14000b82b  jz      loc_14000BC87
0x14000b831  mov     rax, rcx
0x14000b834  and     eax, 8
0x14000b837  cmp     rax, rcx
0x14000b83a  jnz     loc_14000BC87
0x14000b840  mov     dword ptr [rsp+300h+var_2C0], 8007000Eh
0x14000b848  lea     rdx, unk_140026C22
0x14000b84f  jmp     loc_14000BC53
0x14000b854  lea     rax, [rsp+300h+lpFileName]
0x14000b859  mov     qword ptr [rsp+300h+dwCreationDisposition], rax; __int64
0x14000b85e  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x14000b863  mov     edi, eax
0x14000b865  test    eax, eax
0x14000b867  jns     short loc_14000B8AA
0x14000b869  mov     ecx, cs:dword_14002C000
0x14000b86f  cmp     ecx, 2
0x14000b872  jbe     loc_14000BC87
0x14000b878  mov     rax, cs:qword_14002C018
0x14000b87f  mov     rcx, cs:qword_14002C010
0x14000b886  test    cl, 8
0x14000b889  jz      loc_14000BC87
0x14000b88f  mov     rcx, rax
0x14000b892  and     ecx, 8
0x14000b895  cmp     rcx, rax
0x14000b898  jnz     loc_14000BC87
0x14000b89e  lea     rdx, unk_140026BDF
0x14000b8a5  jmp     loc_14000BC4F
0x14000b8aa  mov     rcx, [rsp+300h+lpFileName]
0x14000b8af  mov     edx, 5Ch ; '\'
0x14000b8b4  mov     rax, [rsp+300h+var_2A8]
0x14000b8b9  cmp     rcx, rax
0x14000b8bc  jz      short loc_14000B8C4
0x14000b8be  cmp     dx, [rax-2]
0x14000b8c2  jz      short loc_14000B8E1
0x14000b8c4  lea     rcx, [rsp+300h+lpFileName]
0x14000b8c9  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x14000b8ce  test    al, al
0x14000b8d0  jnz     short loc_14000B8DC
0x14000b8d2  mov     edi, 8007000Eh
0x14000b8d7  jmp     loc_14000BC87
0x14000b8dc  mov     rcx, [rsp+300h+lpFileName]; lpFileName
0x14000b8e1  xor     r9d, r9d; lpSecurityAttributes
0x14000b8e4  mov     [rsp+300h+hTemplateFile], r13; hTemplateFile
0x14000b8e9  mov     [rsp+300h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x14000b8f1  mov     edx, 80h; dwDesiredAccess
0x14000b8f6  mov     [rsp+300h+dwCreationDisposition], 3; dwCreationDisposition
0x14000b8fe  lea     r8d, [r9+1]; dwShareMode
0x14000b902  call    cs:__imp_CreateFileW
0x14000b908  mov     rbx, rax
0x14000b90b  inc     rax
0x14000b90e  cmp     rax, 1
0x14000b912  ja      loc_14000B99E
0x14000b918  call    cs:__imp_GetLastError
0x14000b91e  mov     edi, eax
0x14000b920  test    eax, eax
0x14000b922  jle     short loc_14000B92D
0x14000b924  movzx   edi, ax
0x14000b927  or      edi, 80070000h
0x14000b92d  test    edi, edi
0x14000b92f  mov     eax, 80004005h
0x14000b934  cmovns  edi, eax
0x14000b937  mov     eax, cs:dword_14002C000
0x14000b93d  cmp     eax, 2
0x14000b940  jbe     loc_14000BC87
0x14000b946  mov     rcx, cs:qword_14002C018
0x14000b94d  mov     rax, cs:qword_14002C010
0x14000b954  test    al, 8
0x14000b956  jz      loc_14000BC87
0x14000b95c  mov     rax, rcx
0x14000b95f  and     eax, 8
0x14000b962  cmp     rax, rcx
0x14000b965  jnz     loc_14000BC87
0x14000b96b  lea     rdx, unk_140026B90
0x14000b972  mov     rax, [rsp+300h+lpFileName]
0x14000b977  mov     [rsp+300h+var_2B8], rax
0x14000b97c  lea     rax, [rsp+300h+var_2C0]
0x14000b981  mov     qword ptr [rsp+300h+dwFlagsAndAttributes], rax
0x14000b986  lea     rax, [rsp+300h+var_2B8]
0x14000b98b  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x14000b990  mov     dword ptr [rsp+300h+var_2C0], edi
0x14000b994  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x14000b999  jmp     loc_14000BC87
0x14000b99e  mov     edi, 104h
0x14000b9a3  lea     rdx, [rbp+200h+szFilePath]; lpszFilePath
0x14000b9a7  mov     r8d, edi; cchFilePath
0x14000b9aa  mov     r9d, 2; dwFlags
0x14000b9b0  mov     rcx, rbx; hFile
0x14000b9b3  call    cs:__imp_GetFinalPathNameByHandleW
0x14000b9b9  test    eax, eax
0x14000b9bb  jz      loc_14000BB9B
0x14000b9c1  cmp     eax, edi
0x14000b9c3  jnb     loc_14000BB94
0x14000b9c9  lea     rax, [rbp+200h+szFilePath]
0x14000b9cd  inc     r14
0x14000b9d0  cmp     [rax+r14*2], r13w
0x14000b9d5  jnz     short loc_14000B9CD
0x14000b9d7  mov     rax, [rsp+300h+var_288]
0x14000b9dc  mov     rcx, [rsp+300h+lpString1]; lpString1
0x14000b9e1  sub     rax, rcx
0x14000b9e4  sar     rax, 1
0x14000b9e7  cmp     rax, r14
0x14000b9ea  jb      loc_14000BB23
0x14000b9f0  mov     r9d, r14d; cchCount2
0x14000b9f3  mov     [rsp+300h+dwCreationDisposition], 1; bIgnoreCase
0x14000b9fb  lea     r8, [rbp+200h+szFilePath]; lpString2
0x14000b9ff  mov     edx, r14d; cchCount1
0x14000ba02  call    cs:__imp_CompareStringOrdinal
0x14000ba08  cmp     eax, 2
0x14000ba0b  jnz     loc_14000BB23
0x14000ba11  mov     eax, cs:dword_14002C000
0x14000ba17  cmp     eax, 4
0x14000ba1a  jbe     short loc_14000BA59
0x14000ba1c  mov     rcx, cs:qword_14002C018
0x14000ba23  mov     rax, cs:qword_14002C010
0x14000ba2a  test    al, 8
0x14000ba2c  jz      short loc_14000BA59
0x14000ba2e  mov     rax, rcx
0x14000ba31  and     eax, 8
0x14000ba34  cmp     rax, rcx
0x14000ba37  jnz     short loc_14000BA59
0x14000ba39  mov     rax, [rsp+300h+lpString1]
0x14000ba3e  lea     rdx, unk_140026AFB
0x14000ba45  mov     [rsp+300h+var_2B8], rax
0x14000ba4a  lea     rax, [rsp+300h+var_2B8]
0x14000ba4f  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x14000ba54  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x14000ba59  mov     rax, [rsp+300h+var_2A8]
0x14000ba5e  lea     rcx, [rsp+300h+lpString1]
0x14000ba63  mov     r9, [rsp+300h+lpFileName]
0x14000ba68  mov     r8, r14
0x14000ba6b  sub     rax, r9
0x14000ba6e  sar     rax, 1
0x14000ba71  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x14000ba76  call    ?replace@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K0PEB_W0@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)
0x14000ba7b  test    al, al
0x14000ba7d  mov     eax, cs:dword_14002C000
0x14000ba83  jnz     short loc_14000BACC
0x14000ba85  mov     edi, 8007000Eh
0x14000ba8a  cmp     eax, 2
0x14000ba8d  jbe     loc_14000BC87
0x14000ba93  mov     rcx, cs:qword_14002C018
0x14000ba9a  mov     rax, cs:qword_14002C010
0x14000baa1  test    al, 8
0x14000baa3  jz      loc_14000BC87
0x14000baa9  mov     rax, rcx
0x14000baac  and     eax, 8
0x14000baaf  cmp     rax, rcx
0x14000bab2  jnz     loc_14000BC87
0x14000bab8  mov     dword ptr [rsp+300h+var_2C0], 8007000Eh
0x14000bac0  lea     rdx, unk_140026ABD
0x14000bac7  jmp     loc_14000BC53
0x14000bacc  cmp     eax, 4
0x14000bacf  jbe     short loc_14000BB0E
0x14000bad1  mov     rdx, cs:qword_14002C018
0x14000bad8  mov     rax, cs:qword_14002C010
0x14000badf  test    al, 8
0x14000bae1  jz      short loc_14000BB0E
0x14000bae3  mov     rax, rdx
0x14000bae6  and     eax, 8
0x14000bae9  cmp     rax, rdx
0x14000baec  jnz     short loc_14000BB0E
0x14000baee  mov     rax, [rsp+300h+lpString1]
0x14000baf3  lea     rdx, unk_140026A78
0x14000bafa  mov     [rsp+300h+var_2B8], rax
0x14000baff  lea     rax, [rsp+300h+var_2B8]
0x14000bb04  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x14000bb09  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x14000bb0e  lea     rdx, [rsp+300h+lpString1]
0x14000bb13  mov     rcx, r12
0x14000bb16  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x14000bb1b  mov     edi, r13d
0x14000bb1e  jmp     loc_14000BC87
0x14000bb23  mov     eax, cs:dword_14002C000
0x14000bb29  mov     edi, 800700A1h
0x14000bb2e  cmp     eax, 2
0x14000bb31  jbe     loc_14000BC87
0x14000bb37  mov     rcx, cs:qword_14002C018
0x14000bb3e  mov     rax, cs:qword_14002C010
0x14000bb45  test    al, 8
0x14000bb47  jz      loc_14000BC87
0x14000bb4d  mov     rax, rcx
0x14000bb50  and     eax, 8
0x14000bb53  cmp     rax, rcx
0x14000bb56  jnz     loc_14000BC87
0x14000bb5c  lea     rax, [rbp+200h+szFilePath]
0x14000bb60  mov     [rsp+300h+var_2B8], rax
0x14000bb65  lea     rdx, unk_140026A24
0x14000bb6c  mov     rax, [rsp+300h+lpString1]
0x14000bb71  mov     [rsp+300h+var_2C0], rax
0x14000bb76  lea     rax, [rsp+300h+var_2B8]
0x14000bb7b  mov     qword ptr [rsp+300h+dwFlagsAndAttributes], rax
0x14000bb80  lea     rax, [rsp+300h+var_2C0]
0x14000bb85  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x14000bb8a  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x14000bb8f  jmp     loc_14000BC87
0x14000bb94  mov     edi, 6Fh ; 'o'
0x14000bb99  jmp     short loc_14000BBA7
0x14000bb9b  call    cs:__imp_GetLastError
0x14000bba1  mov     edi, eax
0x14000bba3  test    eax, eax
0x14000bba5  jle     short loc_14000BBB0
0x14000bba7  movzx   edi, di
0x14000bbaa  or      edi, 80070000h
0x14000bbb0  test    edi, edi
0x14000bbb2  mov     eax, 80004005h
0x14000bbb7  cmovns  edi, eax
0x14000bbba  mov     eax, cs:dword_14002C000
0x14000bbc0  cmp     eax, 2
0x14000bbc3  jbe     loc_14000BC87
0x14000bbc9  mov     rcx, cs:qword_14002C018
0x14000bbd0  mov     rax, cs:qword_14002C010
0x14000bbd7  test    al, 8
0x14000bbd9  jz      loc_14000BC87
0x14000bbdf  mov     rax, rcx
0x14000bbe2  and     eax, 8
0x14000bbe5  cmp     rax, rcx
0x14000bbe8  jnz     loc_14000BC87
0x14000bbee  lea     rdx, unk_140026B41
0x14000bbf5  jmp     loc_14000B972
0x14000bbfa  mov     edi, 6Fh ; 'o'
0x14000bbff  jmp     short loc_14000BC0D
0x14000bc01  call    cs:__imp_GetLastError
0x14000bc07  mov     edi, eax
0x14000bc09  test    eax, eax
0x14000bc0b  jle     short loc_14000BC16
0x14000bc0d  movzx   edi, di
0x14000bc10  or      edi, 80070000h
0x14000bc16  test    edi, edi
0x14000bc18  mov     eax, 80004005h
0x14000bc1d  cmovns  edi, eax
0x14000bc20  mov     eax, cs:dword_14002C000
0x14000bc26  cmp     eax, 2
  ... truncated ...
```
