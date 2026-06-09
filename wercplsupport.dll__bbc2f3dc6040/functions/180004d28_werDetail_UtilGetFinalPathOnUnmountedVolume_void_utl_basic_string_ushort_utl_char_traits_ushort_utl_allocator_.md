# _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x180004d28`
- end: `0x180005314`
- name: `?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `1516`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180004970`

## callees

- `0x180001008`
- `0x180001098`
- `0x180001270`
- `0x18000131c`
- `0x180001680`
- `0x180002ad0`
- `0x180004d28`
- `0x180005c28`
- `0x180006754`
- `0x180006828`
- `0x1800068cc`
- `0x1800121b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180004d9f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180004fcf`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180004d9f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180004fcf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004f1e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004f1e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000501e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000501e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000521d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000521d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052e5`

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
  char *v14; // rdx
  const WCHAR *v15; // rcx
  signed int v16; // eax
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  char *v20; // rdx
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
      if ( (unsigned int)dword_18001C008 <= 2 || (qword_18001C018 & 8) == 0 || (qword_18001C020 & 8) != qword_18001C020 )
        goto LABEL_77;
      v14 = byte_180018B11;
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
  if ( (unsigned int)dword_18001C008 > 4 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
  {
    v28 = szFilePath;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      qword_18001C020,
      (unsigned int)&word_18001853E,
      v5,
      v6,
      (__int64)&v28);
  }
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( szFilePath[v8] );
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &lpString1,
                           szFilePath,
                           v8) )
  {
    LastError = -2147024882;
    if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
    {
      LODWORD(v28) = -2147024882;
      v14 = &byte_18001868F;
LABEL_76:
      v38 = 4;
      v37 = &v28;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001C008, v14, 0, 0, 3, v36);
      goto LABEL_77;
    }
    goto LABEL_77;
  }
  LastError = UtilRegGetString(v10, v9, v11, v12, (__int64)&lpFileName, dwFlagsAndAttributes);
  if ( LastError < 0 )
  {
    if ( (unsigned int)dword_18001C008 <= 2 || (qword_18001C018 & 8) == 0 || (qword_18001C020 & 8) != qword_18001C020 )
      goto LABEL_77;
    v14 = (char *)&unk_180018C18;
    goto LABEL_75;
  }
  v15 = lpFileName;
  if ( lpFileName == v31 || *(v31 - 1) != 92 )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(&lpFileName) )
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
    if ( (unsigned int)dword_18001C008 <= 2 )
      goto LABEL_77;
    v19 = qword_18001C020;
    if ( (qword_18001C018 & 8) == 0 || (qword_18001C020 & 8) != qword_18001C020 )
      goto LABEL_77;
    v20 = byte_1800186CB;
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
      if ( (unsigned int)dword_18001C008 <= 2 )
        goto LABEL_77;
      v19 = qword_18001C020;
      if ( (qword_18001C018 & 8) == 0 || (qword_18001C020 & 8) != qword_18001C020 )
        goto LABEL_77;
      v20 = byte_180018899;
LABEL_33:
      v29 = (void *)lpFileName;
      LODWORD(v28) = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
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
    if ( (unsigned int)dword_18001C008 > 4 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
    {
      v29 = (void *)lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        qword_18001C020,
        (unsigned int)byte_180018D01,
        v17,
        v18,
        (__int64)&v29);
    }
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::replace(
                            &lpString1,
                            v22,
                            v7) )
    {
      if ( (unsigned int)dword_18001C008 > 4 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
      {
        v29 = (void *)lpString1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v23,
          (unsigned int)byte_180018B95,
          v24,
          v25,
          (__int64)&v29);
      }
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
        a2,
        &lpString1);
      LastError = 0;
    }
    else
    {
      LastError = -2147024882;
      if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
      {
        LODWORD(v28) = -2147024882;
        v14 = byte_1800187CB;
        goto LABEL_76;
      }
    }
  }
  else
  {
    LastError = -2147024735;
    if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
    {
      v29 = szFilePath;
      v28 = (void *)lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        qword_18001C020,
        (unsigned int)&unk_180018E50,
        v17,
        v18,
        (__int64)&v28,
        (__int64)&v29);
    }
  }
LABEL_77:
  if ( lpString1 != v35 )
    operator delete((void *)lpString1);
  if ( lpFileName != v32 )
    operator delete((void *)lpFileName);
  if ( (unsigned __int64)(FileW + 1) > 1 )
    CloseHandle(FileW);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180004d28  mov     [rsp-8+arg_10], rbx
0x180004d2d  push    rbp
0x180004d2e  push    rdi
0x180004d2f  push    r12
0x180004d31  push    r13
0x180004d33  push    r14
0x180004d35  lea     rbp, [rsp-1E0h]
0x180004d3d  sub     rsp, 2E0h
0x180004d44  mov     rax, cs:__security_cookie
0x180004d4b  xor     rax, rsp
0x180004d4e  mov     [rbp+200h+var_30], rax
0x180004d55  xor     r13d, r13d
0x180004d58  lea     rax, [rsp+300h+var_2A0]
0x180004d5d  mov     [rsp+300h+lpFileName], rax
0x180004d62  mov     r12, rdx
0x180004d65  lea     rax, [rsp+300h+var_2A0]
0x180004d6a  mov     [rsp+300h+var_2A0], r13w
0x180004d70  mov     [rsp+300h+var_2A8], rax
0x180004d75  lea     rdx, [rbp+200h+szFilePath]; lpszFilePath
0x180004d79  lea     rax, [rbp+200h+var_280]
0x180004d7d  mov     [rbp+200h+var_280], r13w
0x180004d82  mov     [rsp+300h+lpString1], rax
0x180004d87  lea     r9d, [r13+2]; dwFlags
0x180004d8b  lea     rax, [rbp+200h+var_280]
0x180004d8f  mov     edi, 104h
0x180004d94  mov     r8d, edi; cchFilePath
0x180004d97  mov     [rsp+300h+var_288], rax
0x180004d9c  mov     ebx, r13d
0x180004d9f  call    cs:__imp_GetFinalPathNameByHandleW
0x180004da5  test    eax, eax
0x180004da7  jz      loc_18000521D
0x180004dad  cmp     eax, edi
0x180004daf  jnb     loc_180005216
0x180004db5  mov     eax, cs:dword_18001C008
0x180004dbb  cmp     eax, 4
0x180004dbe  jbe     short loc_180004DFC
0x180004dc0  mov     rcx, cs:qword_18001C020
0x180004dc7  mov     rax, cs:qword_18001C018
0x180004dce  test    al, 8
0x180004dd0  jz      short loc_180004DFC
0x180004dd2  mov     rax, rcx
0x180004dd5  and     eax, 8
0x180004dd8  cmp     rax, rcx
0x180004ddb  jnz     short loc_180004DFC
0x180004ddd  lea     rax, [rbp+200h+szFilePath]
0x180004de1  mov     [rsp+300h+var_2C0], rax
0x180004de6  lea     rdx, word_18001853E
0x180004ded  lea     rax, [rsp+300h+var_2C0]
0x180004df2  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x180004df7  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180004dfc  or      r14, 0FFFFFFFFFFFFFFFFh
0x180004e00  lea     rax, [rbp+200h+szFilePath]
0x180004e04  mov     r8, r14
0x180004e07  inc     r8
0x180004e0a  cmp     [rax+r8*2], r13w
0x180004e0f  jnz     short loc_180004E07
0x180004e11  lea     rdx, [rbp+200h+szFilePath]
0x180004e15  lea     rcx, [rsp+300h+lpString1]
0x180004e1a  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180004e1f  test    al, al
0x180004e21  jnz     short loc_180004E70
0x180004e23  mov     eax, cs:dword_18001C008
0x180004e29  mov     edi, 8007000Eh
0x180004e2e  cmp     eax, 2
0x180004e31  jbe     loc_1800052A3
0x180004e37  mov     rcx, cs:qword_18001C020
0x180004e3e  mov     rax, cs:qword_18001C018
0x180004e45  test    al, 8
0x180004e47  jz      loc_1800052A3
0x180004e4d  mov     rax, rcx
0x180004e50  and     eax, 8
0x180004e53  cmp     rax, rcx
0x180004e56  jnz     loc_1800052A3
0x180004e5c  mov     dword ptr [rsp+300h+var_2C0], 8007000Eh
0x180004e64  lea     rdx, byte_18001868F
0x180004e6b  jmp     loc_18000526F
0x180004e70  lea     rax, [rsp+300h+lpFileName]
0x180004e75  mov     qword ptr [rsp+300h+dwCreationDisposition], rax; __int64
0x180004e7a  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEBG11PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,ushort const *,ushort const *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,bool,bool)
0x180004e7f  mov     edi, eax
0x180004e81  test    eax, eax
0x180004e83  jns     short loc_180004EC6
0x180004e85  mov     ecx, cs:dword_18001C008
0x180004e8b  cmp     ecx, 2
0x180004e8e  jbe     loc_1800052A3
0x180004e94  mov     rax, cs:qword_18001C020
0x180004e9b  mov     rcx, cs:qword_18001C018
0x180004ea2  test    cl, 8
0x180004ea5  jz      loc_1800052A3
0x180004eab  mov     rcx, rax
0x180004eae  and     ecx, 8
0x180004eb1  cmp     rcx, rax
0x180004eb4  jnz     loc_1800052A3
0x180004eba  lea     rdx, unk_180018C18
0x180004ec1  jmp     loc_18000526B
0x180004ec6  mov     rcx, [rsp+300h+lpFileName]
0x180004ecb  mov     rax, [rsp+300h+var_2A8]
0x180004ed0  cmp     rcx, rax
0x180004ed3  jz      short loc_180004EE0
0x180004ed5  mov     edx, 5Ch ; '\'
0x180004eda  cmp     dx, [rax-2]
0x180004ede  jz      short loc_180004EFD
0x180004ee0  lea     rcx, [rsp+300h+lpFileName]
0x180004ee5  call    ?push_back@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::push_back(ushort)
0x180004eea  test    al, al
0x180004eec  jnz     short loc_180004EF8
0x180004eee  mov     edi, 8007000Eh
0x180004ef3  jmp     loc_1800052A3
0x180004ef8  mov     rcx, [rsp+300h+lpFileName]; lpFileName
0x180004efd  xor     r9d, r9d; lpSecurityAttributes
0x180004f00  mov     [rsp+300h+hTemplateFile], r13; hTemplateFile
0x180004f05  mov     [rsp+300h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x180004f0d  mov     edx, 80h; dwDesiredAccess
0x180004f12  mov     [rsp+300h+dwCreationDisposition], 3; dwCreationDisposition
0x180004f1a  lea     r8d, [r9+1]; dwShareMode
0x180004f1e  call    cs:__imp_CreateFileW
0x180004f24  mov     rbx, rax
0x180004f27  inc     rax
0x180004f2a  cmp     rax, 1
0x180004f2e  ja      loc_180004FBA
0x180004f34  call    cs:__imp_GetLastError
0x180004f3a  mov     edi, eax
0x180004f3c  test    eax, eax
0x180004f3e  jle     short loc_180004F49
0x180004f40  movzx   edi, ax
0x180004f43  or      edi, 80070000h
0x180004f49  test    edi, edi
0x180004f4b  mov     eax, 80004005h
0x180004f50  cmovns  edi, eax
0x180004f53  mov     eax, cs:dword_18001C008
0x180004f59  cmp     eax, 2
0x180004f5c  jbe     loc_1800052A3
0x180004f62  mov     rcx, cs:qword_18001C020
0x180004f69  mov     rax, cs:qword_18001C018
0x180004f70  test    al, 8
0x180004f72  jz      loc_1800052A3
0x180004f78  mov     rax, rcx
0x180004f7b  and     eax, 8
0x180004f7e  cmp     rax, rcx
0x180004f81  jnz     loc_1800052A3
0x180004f87  lea     rdx, byte_1800186CB
0x180004f8e  mov     rax, [rsp+300h+lpFileName]
0x180004f93  mov     [rsp+300h+var_2B8], rax
0x180004f98  lea     rax, [rsp+300h+var_2C0]
0x180004f9d  mov     qword ptr [rsp+300h+dwFlagsAndAttributes], rax
0x180004fa2  lea     rax, [rsp+300h+var_2B8]
0x180004fa7  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x180004fac  mov     dword ptr [rsp+300h+var_2C0], edi
0x180004fb0  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180004fb5  jmp     loc_1800052A3
0x180004fba  mov     edi, 104h
0x180004fbf  lea     rdx, [rbp+200h+szFilePath]; lpszFilePath
0x180004fc3  mov     r8d, edi; cchFilePath
0x180004fc6  mov     r9d, 2; dwFlags
0x180004fcc  mov     rcx, rbx; hFile
0x180004fcf  call    cs:__imp_GetFinalPathNameByHandleW
0x180004fd5  test    eax, eax
0x180004fd7  jz      loc_1800051B7
0x180004fdd  cmp     eax, edi
0x180004fdf  jnb     loc_1800051B0
0x180004fe5  lea     rax, [rbp+200h+szFilePath]
0x180004fe9  inc     r14
0x180004fec  cmp     [rax+r14*2], r13w
0x180004ff1  jnz     short loc_180004FE9
0x180004ff3  mov     rax, [rsp+300h+var_288]
0x180004ff8  mov     rcx, [rsp+300h+lpString1]; lpString1
0x180004ffd  sub     rax, rcx
0x180005000  sar     rax, 1
0x180005003  cmp     rax, r14
0x180005006  jb      loc_18000513F
0x18000500c  mov     r9d, r14d; cchCount2
0x18000500f  mov     [rsp+300h+dwCreationDisposition], 1; bIgnoreCase
0x180005017  lea     r8, [rbp+200h+szFilePath]; lpString2
0x18000501b  mov     edx, r14d; cchCount1
0x18000501e  call    cs:__imp_CompareStringOrdinal
0x180005024  cmp     eax, 2
0x180005027  jnz     loc_18000513F
0x18000502d  mov     eax, cs:dword_18001C008
0x180005033  cmp     eax, 4
0x180005036  jbe     short loc_180005075
0x180005038  mov     rcx, cs:qword_18001C020
0x18000503f  mov     rax, cs:qword_18001C018
0x180005046  test    al, 8
0x180005048  jz      short loc_180005075
0x18000504a  mov     rax, rcx
0x18000504d  and     eax, 8
0x180005050  cmp     rax, rcx
0x180005053  jnz     short loc_180005075
0x180005055  mov     rax, [rsp+300h+lpString1]
0x18000505a  lea     rdx, byte_180018D01
0x180005061  mov     [rsp+300h+var_2B8], rax
0x180005066  lea     rax, [rsp+300h+var_2B8]
0x18000506b  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x180005070  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180005075  mov     rax, [rsp+300h+var_2A8]
0x18000507a  lea     rcx, [rsp+300h+lpString1]
0x18000507f  mov     r9, [rsp+300h+lpFileName]
0x180005084  mov     r8, r14
0x180005087  sub     rax, r9
0x18000508a  sar     rax, 1
0x18000508d  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x180005092  call    ?replace@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_K0PEBG0@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::replace(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x180005097  test    al, al
0x180005099  mov     eax, cs:dword_18001C008
0x18000509f  jnz     short loc_1800050E8
0x1800050a1  mov     edi, 8007000Eh
0x1800050a6  cmp     eax, 2
0x1800050a9  jbe     loc_1800052A3
0x1800050af  mov     rcx, cs:qword_18001C020
0x1800050b6  mov     rax, cs:qword_18001C018
0x1800050bd  test    al, 8
0x1800050bf  jz      loc_1800052A3
0x1800050c5  mov     rax, rcx
0x1800050c8  and     eax, 8
0x1800050cb  cmp     rax, rcx
0x1800050ce  jnz     loc_1800052A3
0x1800050d4  mov     dword ptr [rsp+300h+var_2C0], 8007000Eh
0x1800050dc  lea     rdx, byte_1800187CB
0x1800050e3  jmp     loc_18000526F
0x1800050e8  cmp     eax, 4
0x1800050eb  jbe     short loc_18000512A
0x1800050ed  mov     rdx, cs:qword_18001C020
0x1800050f4  mov     rax, cs:qword_18001C018
0x1800050fb  test    al, 8
0x1800050fd  jz      short loc_18000512A
0x1800050ff  mov     rax, rdx
0x180005102  and     eax, 8
0x180005105  cmp     rax, rdx
0x180005108  jnz     short loc_18000512A
0x18000510a  mov     rax, [rsp+300h+lpString1]
0x18000510f  lea     rdx, byte_180018B95
0x180005116  mov     [rsp+300h+var_2B8], rax
0x18000511b  lea     rax, [rsp+300h+var_2B8]
0x180005120  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x180005125  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000512a  lea     rdx, [rsp+300h+lpString1]
0x18000512f  mov     rcx, r12
0x180005132  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x180005137  mov     edi, r13d
0x18000513a  jmp     loc_1800052A3
0x18000513f  mov     eax, cs:dword_18001C008
0x180005145  mov     edi, 800700A1h
0x18000514a  cmp     eax, 2
0x18000514d  jbe     loc_1800052A3
0x180005153  mov     rcx, cs:qword_18001C020
0x18000515a  mov     rax, cs:qword_18001C018
0x180005161  test    al, 8
0x180005163  jz      loc_1800052A3
0x180005169  mov     rax, rcx
0x18000516c  and     eax, 8
0x18000516f  cmp     rax, rcx
0x180005172  jnz     loc_1800052A3
0x180005178  lea     rax, [rbp+200h+szFilePath]
0x18000517c  mov     [rsp+300h+var_2B8], rax
0x180005181  lea     rdx, unk_180018E50
0x180005188  mov     rax, [rsp+300h+lpString1]
0x18000518d  mov     [rsp+300h+var_2C0], rax
0x180005192  lea     rax, [rsp+300h+var_2B8]
0x180005197  mov     qword ptr [rsp+300h+dwFlagsAndAttributes], rax
0x18000519c  lea     rax, [rsp+300h+var_2C0]
0x1800051a1  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x1800051a6  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800051ab  jmp     loc_1800052A3
0x1800051b0  mov     edi, 6Fh ; 'o'
0x1800051b5  jmp     short loc_1800051C3
0x1800051b7  call    cs:__imp_GetLastError
0x1800051bd  mov     edi, eax
0x1800051bf  test    eax, eax
0x1800051c1  jle     short loc_1800051CC
0x1800051c3  movzx   edi, di
0x1800051c6  or      edi, 80070000h
0x1800051cc  test    edi, edi
0x1800051ce  mov     eax, 80004005h
0x1800051d3  cmovns  edi, eax
0x1800051d6  mov     eax, cs:dword_18001C008
0x1800051dc  cmp     eax, 2
0x1800051df  jbe     loc_1800052A3
0x1800051e5  mov     rcx, cs:qword_18001C020
0x1800051ec  mov     rax, cs:qword_18001C018
0x1800051f3  test    al, 8
0x1800051f5  jz      loc_1800052A3
0x1800051fb  mov     rax, rcx
0x1800051fe  and     eax, 8
0x180005201  cmp     rax, rcx
0x180005204  jnz     loc_1800052A3
0x18000520a  lea     rdx, byte_180018899
0x180005211  jmp     loc_180004F8E
0x180005216  mov     edi, 6Fh ; 'o'
0x18000521b  jmp     short loc_180005229
0x18000521d  call    cs:__imp_GetLastError
0x180005223  mov     edi, eax
0x180005225  test    eax, eax
0x180005227  jle     short loc_180005232
0x180005229  movzx   edi, di
0x18000522c  or      edi, 80070000h
0x180005232  test    edi, edi
0x180005234  mov     eax, 80004005h
0x180005239  cmovns  edi, eax
0x18000523c  mov     eax, cs:dword_18001C008
0x180005242  cmp     eax, 2
  ... truncated ...
```
