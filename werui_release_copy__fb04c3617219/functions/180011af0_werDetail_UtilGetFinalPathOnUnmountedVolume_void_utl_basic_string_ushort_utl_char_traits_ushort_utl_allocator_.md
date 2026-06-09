# _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x180011af0`
- end: `0x180011f9f`
- name: `?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `1199`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800118a8`

## callees

- `0x180001234`
- `0x180001350`
- `0x1800013e0`
- `0x180001694`
- `0x180001740`
- `0x180003fe4`
- `0x180005ddc`
- `0x180009580`
- `0x1800096d0`
- `0x18000979c`
- `0x18000983c`
- `0x18000f764`
- `0x180011af0`
- `0x180012b0c`
- `0x180013580`
- `0x180016c50`

## import_xrefs

- `KERNEL32!GetFinalPathNameByHandleW` at `0x180011b65`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180011d41`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180011b65`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180011d41`
- `KERNEL32!CreateFileW` at `0x180011cae`
- `KERNEL32!CreateFileW` at `0x180011cae`
- `KERNEL32!GetLastError` at `0x180011cd0`
- `KERNEL32!GetLastError` at `0x180011ede`
- `KERNEL32!GetLastError` at `0x180011f17`
- `KERNEL32!GetLastError` at `0x180011cd0`
- `KERNEL32!GetLastError` at `0x180011ede`
- `KERNEL32!GetLastError` at `0x180011f17`
- `KERNEL32!CompareStringOrdinal` at `0x180011d91`
- `KERNEL32!CompareStringOrdinal` at `0x180011d91`

## pseudocode

```c
__int64 __fastcall _werDetail::UtilGetFinalPathOnUnmountedVolume(void *a1, __int64 a2)
{
  DWORD FinalPathNameByHandleW; // eax
  __int64 v4; // rcx
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  unsigned __int64 v8; // rsi
  __int64 v9; // r8
  int v10; // edx
  __int64 v11; // rcx
  int v12; // r8d
  int v13; // r9d
  int String; // ebx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  char *v18; // rdx
  const WCHAR *v19; // rcx
  HANDLE FileW; // rax
  DWORD v21; // eax
  __int64 v22; // rcx
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  char *v26; // rdx
  DWORD v27; // eax
  LPCWCH v28; // rcx
  __int64 v29; // rdx
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  __int64 v33; // rcx
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  DWORD v40; // eax
  __int64 v41; // rcx
  DWORD LastError; // eax
  __int64 v43; // rcx
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  void *v46; // [rsp+40h] [rbp-C0h] BYREF
  void *v47; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-A8h] BYREF
  const WCHAR *v50; // [rsp+60h] [rbp-A0h]
  _WORD v51[8]; // [rsp+68h] [rbp-98h] BYREF
  LPCWCH lpString1; // [rsp+78h] [rbp-88h] BYREF
  _WORD *v53; // [rsp+80h] [rbp-80h]
  _WORD v54[12]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR szFilePath[264]; // [rsp+A0h] [rbp-60h] BYREF

  lpFileName = v51;
  hFile = 0;
  v50 = v51;
  v51[0] = 0;
  lpString1 = v54;
  v54[0] = 0;
  v53 = v54;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(a1, szFilePath, 0x104u, 2u);
  if ( !FinalPathNameByHandleW )
  {
    LastError = GetLastError();
LABEL_52:
    String = ERROR_HR_FROM_WIN32(LastError);
    if ( (unsigned int)dword_180022000 <= 2 || !(unsigned __int8)tlgKeywordOn(v43, 8) )
      goto LABEL_57;
    v18 = &byte_18001C80F;
LABEL_55:
    LODWORD(v46) = String;
    goto LABEL_56;
  }
  if ( FinalPathNameByHandleW >= 0x104 )
  {
    LastError = 111;
    goto LABEL_52;
  }
  if ( (unsigned int)dword_180022000 > 4 && (unsigned __int8)tlgKeywordOn(v4, 8) )
  {
    v46 = szFilePath;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v5,
      (unsigned int)byte_18001C7CD,
      v6,
      v7,
      (__int64)&v46);
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( szFilePath[v9] );
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &lpString1,
                           szFilePath) )
  {
    String = -2147024882;
    if ( (unsigned int)dword_180022000 > 2 && (unsigned __int8)tlgKeywordOn(v11, 8) )
    {
      LODWORD(v46) = -2147024882;
      v18 = byte_18001C791;
LABEL_56:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v15,
        (_DWORD)v18,
        v16,
        v17,
        (__int64)&v46);
      goto LABEL_57;
    }
    goto LABEL_57;
  }
  String = UtilRegGetString(v11, v10, v12, v13, (__int64)&lpFileName, dwFlagsAndAttributes);
  if ( String < 0 )
  {
    if ( (unsigned int)dword_180022000 <= 2 || !(unsigned __int8)tlgKeywordOn((unsigned int)dword_180022000, 8) )
      goto LABEL_57;
    v18 = (char *)&word_18001C74E;
    goto LABEL_55;
  }
  v19 = lpFileName;
  if ( lpFileName == v50 || *(v50 - 1) != 92 )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(
                             &lpFileName,
                             92) )
    {
      String = -2147024882;
      goto LABEL_57;
    }
    v19 = lpFileName;
  }
  FileW = CreateFileW(v19, 0x80u, 1u, 0, 3u, 0x2000080u, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, FileW);
  if ( (unsigned __int64)hFile + 1 <= 1 )
  {
    v21 = GetLastError();
    String = ERROR_HR_FROM_WIN32(v21);
    if ( (unsigned int)dword_180022000 <= 2 || !(unsigned __int8)tlgKeywordOn(v22, 8) )
      goto LABEL_57;
    v26 = &byte_18001C6FF;
    goto LABEL_25;
  }
  v27 = GetFinalPathNameByHandleW(hFile, szFilePath, 0x104u, 2u);
  if ( !v27 )
  {
    v40 = GetLastError();
LABEL_47:
    String = ERROR_HR_FROM_WIN32(v40);
    if ( (unsigned int)dword_180022000 <= 2 || !(unsigned __int8)tlgKeywordOn(v41, 8) )
      goto LABEL_57;
    v26 = (char *)&unk_18001C6B0;
LABEL_25:
    v47 = (void *)lpFileName;
    LODWORD(v46) = String;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v23,
      (_DWORD)v26,
      v24,
      v25,
      (__int64)&v47,
      (__int64)&v46);
    goto LABEL_57;
  }
  if ( v27 >= 0x104 )
  {
    v40 = 111;
    goto LABEL_47;
  }
  do
    ++v8;
  while ( szFilePath[v8] );
  v28 = lpString1;
  if ( v53 - lpString1 >= v8 && CompareStringOrdinal(lpString1, v8, szFilePath, v8, 1) == 2 )
  {
    if ( (unsigned int)dword_180022000 > 4 && (unsigned __int8)tlgKeywordOn(v28, 8) )
    {
      v47 = (void *)lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v30,
        (unsigned int)word_18001C66A,
        v31,
        v32,
        (__int64)&v47);
    }
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::replace(
                            &lpString1,
                            v29,
                            v8) )
    {
      if ( (unsigned int)dword_180022000 > 4 && (unsigned __int8)tlgKeywordOn(v33, 8) )
      {
        v47 = (void *)lpString1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v34,
          (unsigned int)&byte_18001C5E7,
          v35,
          v36,
          (__int64)&v47);
      }
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
        a2,
        &lpString1);
      String = 0;
    }
    else
    {
      String = -2147024882;
      if ( (unsigned int)dword_180022000 > 2 && (unsigned __int8)tlgKeywordOn(v33, 8) )
      {
        LODWORD(v46) = -2147024882;
        v18 = (char *)&dword_18001C62C;
        goto LABEL_56;
      }
    }
  }
  else
  {
    String = -2147024735;
    if ( (unsigned int)dword_180022000 > 2 && (unsigned __int8)tlgKeywordOn(v28, 8) )
    {
      v47 = szFilePath;
      v46 = (void *)lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v37,
        (unsigned int)byte_18001C593,
        v38,
        v39,
        (__int64)&v46,
        (__int64)&v47);
    }
  }
LABEL_57:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&lpString1);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&lpFileName);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180011af0  mov     [rsp-8+arg_10], rbx
0x180011af5  push    rbp
0x180011af6  push    rsi
0x180011af7  push    rdi
0x180011af8  push    r14
0x180011afa  push    r15
0x180011afc  lea     rbp, [rsp-1C0h]
0x180011b04  sub     rsp, 2C0h
0x180011b0b  mov     rax, cs:__security_cookie
0x180011b12  xor     rax, rsp
0x180011b15  mov     [rbp+1E0h+var_30], rax
0x180011b1c  xor     r15d, r15d
0x180011b1f  lea     rax, [rsp+2E0h+var_278]
0x180011b24  mov     [rsp+2E0h+lpFileName], rax
0x180011b29  mov     r14, rdx
0x180011b2c  lea     rax, [rsp+2E0h+var_278]
0x180011b31  mov     [rsp+2E0h+hFile], r15
0x180011b36  mov     [rsp+2E0h+var_280], rax
0x180011b3b  lea     rdx, [rbp+1E0h+szFilePath]; lpszFilePath
0x180011b3f  lea     rax, [rbp+1E0h+var_258]
0x180011b43  mov     [rsp+2E0h+var_278], r15w
0x180011b49  mov     [rsp+2E0h+lpString1], rax
0x180011b4e  lea     r9d, [r15+2]; dwFlags
0x180011b52  lea     rax, [rbp+1E0h+var_258]
0x180011b56  mov     [rbp+1E0h+var_258], r15w
0x180011b5b  mov     r8d, 104h; cchFilePath
0x180011b61  mov     [rbp+1E0h+var_260], rax
0x180011b65  call    cs:__imp_GetFinalPathNameByHandleW
0x180011b6b  test    eax, eax
0x180011b6d  jz      loc_180011F17
0x180011b73  cmp     eax, 104h
0x180011b78  jnb     loc_180011F10
0x180011b7e  mov     eax, cs:dword_180022000
0x180011b84  lea     edi, [r15+8]
0x180011b88  cmp     eax, 4
0x180011b8b  jbe     short loc_180011BB7
0x180011b8d  mov     edx, edi
0x180011b8f  call    _tlgKeywordOn
0x180011b94  test    al, al
0x180011b96  jz      short loc_180011BB7
0x180011b98  lea     rax, [rbp+1E0h+szFilePath]
0x180011b9c  mov     [rsp+2E0h+var_2A0], rax
0x180011ba1  lea     rdx, byte_18001C7CD
0x180011ba8  lea     rax, [rsp+2E0h+var_2A0]
0x180011bad  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180011bb2  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180011bb7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180011bbb  lea     rax, [rbp+1E0h+szFilePath]
0x180011bbf  mov     r8, rsi
0x180011bc2  inc     r8
0x180011bc5  cmp     [rax+r8*2], r15w
0x180011bca  jnz     short loc_180011BC2
0x180011bcc  lea     rdx, [rbp+1E0h+szFilePath]
0x180011bd0  lea     rcx, [rsp+2E0h+lpString1]
0x180011bd5  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180011bda  test    al, al
0x180011bdc  jnz     short loc_180011C16
0x180011bde  mov     eax, cs:dword_180022000
0x180011be4  mov     ebx, 8007000Eh
0x180011be9  cmp     eax, 2
0x180011bec  jbe     loc_180011F59
0x180011bf2  mov     rdx, rdi
0x180011bf5  call    _tlgKeywordOn
0x180011bfa  test    al, al
0x180011bfc  jz      loc_180011F59
0x180011c02  mov     dword ptr [rsp+2E0h+var_2A0], 8007000Eh
0x180011c0a  lea     rdx, byte_18001C791
0x180011c11  jmp     loc_180011F4A
0x180011c16  lea     rax, [rsp+2E0h+lpFileName]
0x180011c1b  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax; __int64
0x180011c20  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEBG11PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,ushort const *,ushort const *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,bool,bool)
0x180011c25  mov     ebx, eax
0x180011c27  test    eax, eax
0x180011c29  jns     short loc_180011C56
0x180011c2b  mov     ecx, cs:dword_180022000
0x180011c31  cmp     ecx, 2
0x180011c34  jbe     loc_180011F59
0x180011c3a  mov     rdx, rdi
0x180011c3d  call    _tlgKeywordOn
0x180011c42  test    al, al
0x180011c44  jz      loc_180011F59
0x180011c4a  lea     rdx, word_18001C74E
0x180011c51  jmp     loc_180011F46
0x180011c56  mov     rcx, [rsp+2E0h+lpFileName]
0x180011c5b  mov     edx, 5Ch ; '\'
0x180011c60  mov     rax, [rsp+2E0h+var_280]
0x180011c65  cmp     rcx, rax
0x180011c68  jz      short loc_180011C70
0x180011c6a  cmp     dx, [rax-2]
0x180011c6e  jz      short loc_180011C8D
0x180011c70  lea     rcx, [rsp+2E0h+lpFileName]
0x180011c75  call    ?push_back@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::push_back(ushort)
0x180011c7a  test    al, al
0x180011c7c  jnz     short loc_180011C88
0x180011c7e  mov     ebx, 8007000Eh
0x180011c83  jmp     loc_180011F59
0x180011c88  mov     rcx, [rsp+2E0h+lpFileName]; lpFileName
0x180011c8d  xor     r9d, r9d; lpSecurityAttributes
0x180011c90  mov     [rsp+2E0h+hTemplateFile], r15; hTemplateFile
0x180011c95  mov     [rsp+2E0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x180011c9d  mov     edx, 80h; dwDesiredAccess
0x180011ca2  mov     [rsp+2E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180011caa  lea     r8d, [r9+1]; dwShareMode
0x180011cae  call    cs:__imp_CreateFileW
0x180011cb4  mov     rdx, rax
0x180011cb7  lea     rcx, [rsp+2E0h+hFile]
0x180011cbc  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180011cc1  mov     rcx, [rsp+2E0h+hFile]; hFile
0x180011cc6  lea     rax, [rcx+1]
0x180011cca  cmp     rax, 1
0x180011cce  ja      short loc_180011D31
0x180011cd0  call    cs:__imp_GetLastError
0x180011cd6  mov     ecx, eax; unsigned int
0x180011cd8  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180011cdd  mov     ebx, eax
0x180011cdf  mov     eax, cs:dword_180022000
0x180011ce5  cmp     eax, 2
0x180011ce8  jbe     loc_180011F59
0x180011cee  mov     rdx, rdi
0x180011cf1  call    _tlgKeywordOn
0x180011cf6  test    al, al
0x180011cf8  jz      loc_180011F59
0x180011cfe  lea     rdx, byte_18001C6FF
0x180011d05  mov     rax, [rsp+2E0h+lpFileName]
0x180011d0a  mov     [rsp+2E0h+var_298], rax
0x180011d0f  lea     rax, [rsp+2E0h+var_2A0]
0x180011d14  mov     qword ptr [rsp+2E0h+dwFlagsAndAttributes], rax
0x180011d19  lea     rax, [rsp+2E0h+var_298]
0x180011d1e  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180011d23  mov     dword ptr [rsp+2E0h+var_2A0], ebx
0x180011d27  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180011d2c  jmp     loc_180011F59
0x180011d31  mov     r9d, 2; dwFlags
0x180011d37  lea     rdx, [rbp+1E0h+szFilePath]; lpszFilePath
0x180011d3b  mov     r8d, 104h; cchFilePath
0x180011d41  call    cs:__imp_GetFinalPathNameByHandleW
0x180011d47  test    eax, eax
0x180011d49  jz      loc_180011EDE
0x180011d4f  cmp     eax, 104h
0x180011d54  jnb     loc_180011ED7
0x180011d5a  lea     rax, [rbp+1E0h+szFilePath]
0x180011d5e  inc     rsi
0x180011d61  cmp     [rax+rsi*2], r15w
0x180011d66  jnz     short loc_180011D5E
0x180011d68  mov     rax, [rbp+1E0h+var_260]
0x180011d6c  mov     rcx, [rsp+2E0h+lpString1]; lpString1
0x180011d71  sub     rax, rcx
0x180011d74  sar     rax, 1
0x180011d77  cmp     rax, rsi
0x180011d7a  jb      loc_180011E7B
0x180011d80  mov     r9d, esi; cchCount2
0x180011d83  mov     [rsp+2E0h+dwCreationDisposition], 1; bIgnoreCase
0x180011d8b  lea     r8, [rbp+1E0h+szFilePath]; lpString2
0x180011d8f  mov     edx, esi; cchCount1
0x180011d91  call    cs:__imp_CompareStringOrdinal
0x180011d97  cmp     eax, 2
0x180011d9a  jnz     loc_180011E7B
0x180011da0  mov     eax, cs:dword_180022000
0x180011da6  cmp     eax, 4
0x180011da9  jbe     short loc_180011DD7
0x180011dab  mov     rdx, rdi
0x180011dae  call    _tlgKeywordOn
0x180011db3  test    al, al
0x180011db5  jz      short loc_180011DD7
0x180011db7  mov     rax, [rsp+2E0h+lpString1]
0x180011dbc  lea     rdx, word_18001C66A
0x180011dc3  mov     [rsp+2E0h+var_298], rax
0x180011dc8  lea     rax, [rsp+2E0h+var_298]
0x180011dcd  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180011dd2  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180011dd7  mov     rax, [rsp+2E0h+var_280]
0x180011ddc  lea     rcx, [rsp+2E0h+lpString1]
0x180011de1  mov     r9, [rsp+2E0h+lpFileName]
0x180011de6  mov     r8, rsi
0x180011de9  sub     rax, r9
0x180011dec  sar     rax, 1
0x180011def  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180011df4  call    ?replace@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_K0PEBG0@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::replace(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x180011df9  test    al, al
0x180011dfb  mov     eax, cs:dword_180022000
0x180011e01  jnz     short loc_180011E35
0x180011e03  mov     ebx, 8007000Eh
0x180011e08  cmp     eax, 2
0x180011e0b  jbe     loc_180011F59
0x180011e11  mov     rdx, rdi
0x180011e14  call    _tlgKeywordOn
0x180011e19  test    al, al
0x180011e1b  jz      loc_180011F59
0x180011e21  mov     dword ptr [rsp+2E0h+var_2A0], 8007000Eh
0x180011e29  lea     rdx, dword_18001C62C
0x180011e30  jmp     loc_180011F4A
0x180011e35  cmp     eax, 4
0x180011e38  jbe     short loc_180011E66
0x180011e3a  mov     rdx, rdi
0x180011e3d  call    _tlgKeywordOn
0x180011e42  test    al, al
0x180011e44  jz      short loc_180011E66
0x180011e46  mov     rax, [rsp+2E0h+lpString1]
0x180011e4b  lea     rdx, byte_18001C5E7
0x180011e52  mov     [rsp+2E0h+var_298], rax
0x180011e57  lea     rax, [rsp+2E0h+var_298]
0x180011e5c  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180011e61  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180011e66  lea     rdx, [rsp+2E0h+lpString1]
0x180011e6b  mov     rcx, r14
0x180011e6e  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x180011e73  mov     ebx, r15d
0x180011e76  jmp     loc_180011F59
0x180011e7b  mov     eax, cs:dword_180022000
0x180011e81  mov     ebx, 800700A1h
0x180011e86  cmp     eax, 2
0x180011e89  jbe     loc_180011F59
0x180011e8f  mov     rdx, rdi
0x180011e92  call    _tlgKeywordOn
0x180011e97  test    al, al
0x180011e99  jz      loc_180011F59
0x180011e9f  lea     rax, [rbp+1E0h+szFilePath]
0x180011ea3  mov     [rsp+2E0h+var_298], rax
0x180011ea8  lea     rdx, byte_18001C593
0x180011eaf  mov     rax, [rsp+2E0h+lpString1]
0x180011eb4  mov     [rsp+2E0h+var_2A0], rax
0x180011eb9  lea     rax, [rsp+2E0h+var_298]
0x180011ebe  mov     qword ptr [rsp+2E0h+dwFlagsAndAttributes], rax
0x180011ec3  lea     rax, [rsp+2E0h+var_2A0]
0x180011ec8  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180011ecd  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180011ed2  jmp     loc_180011F59
0x180011ed7  mov     eax, 6Fh ; 'o'
0x180011edc  jmp     short loc_180011EE4
0x180011ede  call    cs:__imp_GetLastError
0x180011ee4  mov     ecx, eax; unsigned int
0x180011ee6  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180011eeb  mov     ebx, eax
0x180011eed  mov     eax, cs:dword_180022000
0x180011ef3  cmp     eax, 2
0x180011ef6  jbe     short loc_180011F59
0x180011ef8  mov     rdx, rdi
0x180011efb  call    _tlgKeywordOn
0x180011f00  test    al, al
0x180011f02  jz      short loc_180011F59
0x180011f04  lea     rdx, unk_18001C6B0
0x180011f0b  jmp     loc_180011D05
0x180011f10  mov     eax, 6Fh ; 'o'
0x180011f15  jmp     short loc_180011F1D
0x180011f17  call    cs:__imp_GetLastError
0x180011f1d  mov     ecx, eax; unsigned int
0x180011f1f  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180011f24  mov     ebx, eax
0x180011f26  mov     eax, cs:dword_180022000
0x180011f2c  cmp     eax, 2
0x180011f2f  jbe     short loc_180011F59
0x180011f31  mov     edx, 8
0x180011f36  call    _tlgKeywordOn
0x180011f3b  test    al, al
0x180011f3d  jz      short loc_180011F59
0x180011f3f  lea     rdx, byte_18001C80F
0x180011f46  mov     dword ptr [rsp+2E0h+var_2A0], ebx
0x180011f4a  lea     rax, [rsp+2E0h+var_2A0]
0x180011f4f  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180011f54  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180011f59  lea     rcx, [rsp+2E0h+lpString1]
0x180011f5e  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180011f63  lea     rcx, [rsp+2E0h+lpFileName]
0x180011f68  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180011f6d  lea     rcx, [rsp+2E0h+hFile]
0x180011f72  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180011f77  mov     eax, ebx
0x180011f79  mov     rcx, [rbp+1E0h+var_30]
0x180011f80  xor     rcx, rsp; StackCookie
0x180011f83  call    __security_check_cookie
0x180011f88  mov     rbx, [rsp+2E0h+arg_10]
0x180011f90  add     rsp, 2C0h
0x180011f97  pop     r15
0x180011f99  pop     r14
0x180011f9b  pop     rdi
0x180011f9c  pop     rsi
0x180011f9d  pop     rbp
0x180011f9e  retn
```
