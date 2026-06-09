# UtilRecursiveRemoveDirectory(wchar_t const *,int,wchar_t const *,wchar_t const *,int)

- ea: `0x18001bccc`
- end: `0x18001c24f`
- name: `?UtilRecursiveRemoveDirectory@@YAJPEB_WH00H@Z`
- size: `1411`
- prototype: `__int64 __fastcall(const wchar_t *, int, const wchar_t *, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180017f88`
- `0x18001bccc`

## callees

- `0x18000113c`
- `0x1800011dc`
- `0x18000134c`
- `0x180001d40`
- `0x1800029d0`
- `0x1800029f4`
- `0x1800035e8`
- `0x180004a44`
- `0x180012600`
- `0x1800167a4`
- `0x18001bccc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bdbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bdbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf70`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001bdae`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001bdae`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001bf59`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001bf59`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001c113`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001c113`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001c12d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001c228`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001c12d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001c228`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilRecursiveRemoveDirectory(WCHAR *a1, __int64 a2, const wchar_t *a3, const wchar_t *a4)
{
  __int64 v5; // r14
  DWORD FileAttributesW; // eax
  int v8; // r8d
  int v9; // r9d
  signed int LastError; // eax
  signed int v11; // ebx
  int v12; // ecx
  char *v13; // rdx
  HANDLE FirstFileW; // rsi
  signed int v15; // eax
  const wchar_t *v16; // rdx
  int v17; // r8d
  int v18; // r9d
  int v19; // eax
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rcx
  const wchar_t *v23; // rdx
  int v24; // eax
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rcx
  int v28; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v29; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v31[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 cFileName; // [rsp+70h] [rbp-90h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v34; // [rsp+2D0h] [rbp+1D0h] BYREF

  v5 = -1;
  lpFileName[0] = v31;
  lpFileName[1] = v31;
  v31[0] = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 )
  {
    if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180047000, (unsigned __int8 *)word_18003F652, 0, 0, 2u, &v34);
    if ( lpFileName[0] != v31 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942487LL;
  }
  FileAttributesW = GetFileAttributesW(a1);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 >= 0 )
      v11 = -2147467259;
    if ( (unsigned int)dword_180047000 <= 2 )
      goto LABEL_72;
    v12 = qword_180047018;
    if ( (qword_180047010 & 8) == 0 || (qword_180047018 & 8) != qword_180047018 )
      goto LABEL_72;
    v28 = v11;
    v13 = (char *)&word_18003F606;
    goto LABEL_18;
  }
  if ( (FileAttributesW & 0x10) == 0 )
  {
    v11 = -2147024809;
    if ( (unsigned int)dword_180047000 <= 2 )
      goto LABEL_72;
    v12 = qword_180047018;
    if ( (qword_180047010 & 8) == 0 || (qword_180047018 & 8) != qword_180047018 )
      goto LABEL_72;
    v28 = -2147024809;
    v13 = byte_18003F5BB;
LABEL_18:
    v29 = a1;
    goto LABEL_19;
  }
  if ( (FileAttributesW & 0x400) != 0 )
  {
    v11 = -2147024809;
    if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
    {
      v29 = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        qword_180047018,
        (unsigned int)word_18003F57A,
        v8,
        v9,
        (__int64)&v29);
    }
    goto LABEL_72;
  }
  if ( (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName, L"%ls\\*", a1) < 0 )
  {
    v11 = -2147024809;
    if ( (unsigned int)dword_180047000 <= 2 )
      goto LABEL_72;
    v12 = qword_180047018;
    if ( (qword_180047010 & 8) == 0 || (qword_180047018 & 8) != qword_180047018 )
      goto LABEL_72;
    v28 = -2147024809;
    v13 = byte_18003F533;
    goto LABEL_18;
  }
  FirstFileW = FindFirstFileW(lpFileName[0], &FindFileData);
  v5 = (__int64)FirstFileW;
  cFileName = (__int64)FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL )
  {
    v15 = GetLastError();
    v11 = v15;
    if ( v15 > 0 )
      v11 = (unsigned __int16)v15 | 0x80070000;
    if ( v11 >= 0 )
      v11 = -2147467259;
    if ( (unsigned int)dword_180047000 <= 2 )
      goto LABEL_72;
    v12 = qword_180047018;
    if ( (qword_180047010 & 8) == 0 || (qword_180047018 & 8) != qword_180047018 )
      goto LABEL_72;
    v28 = v11;
    v29 = lpFileName[0];
    v13 = byte_18003F4EB;
LABEL_19:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      v12,
      (_DWORD)v13,
      v8,
      v9,
      (__int64)&v29,
      (__int64)&v28);
    goto LABEL_72;
  }
  while ( 1 )
  {
    if ( FindFileData.cFileName[0] != 46
      || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
    {
      v11 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
              lpFileName,
              L"%ls\\%ls",
              a1,
              FindFileData.cFileName);
      if ( v11 < 0 )
      {
        if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
        {
          v28 = v11;
          cFileName = (__int64)FindFileData.cFileName;
          v29 = a1;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
            qword_180047018,
            (unsigned int)byte_18003F499,
            v17,
            v18,
            (__int64)&v29,
            (__int64)&cFileName,
            (__int64)&v28);
        }
        goto LABEL_72;
      }
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        v19 = _werDetail::PreparePathForDeletion(lpFileName[0], v16);
        if ( v19 < 0 && (unsigned int)dword_180047000 > 3 && (qword_180047010 & 8) != 0 )
        {
          v22 = qword_180047018 & 8;
          if ( v22 == qword_180047018 )
          {
            v28 = v19;
            v29 = lpFileName[0];
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
              v22,
              (unsigned int)word_18003F40A,
              v20,
              v21,
              (__int64)&v29,
              (__int64)&v28);
          }
        }
        UtilDeleteFilePath((WCHAR *)lpFileName[0]);
        goto LABEL_61;
      }
      v11 = UtilRecursiveRemoveDirectory(lpFileName[0], 1, 0, 0, 0);
      if ( v11 < 0 )
        break;
    }
LABEL_61:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      v5 = -1;
      cFileName = -1;
      FindClose(FirstFileW);
      v24 = _werDetail::PreparePathForDeletion(a1, v23);
      if ( v24 < 0 && (unsigned int)dword_180047000 > 3 && (qword_180047010 & 8) != 0 )
      {
        v27 = qword_180047018 & 8;
        if ( v27 == qword_180047018 )
        {
          v28 = v24;
          v29 = a1;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
            v27,
            (unsigned int)byte_18003F3C3,
            v25,
            v26,
            (__int64)&v29,
            (__int64)&v28);
        }
      }
      UtilDeleteFilePath(a1);
      v11 = 0;
      goto LABEL_72;
    }
  }
  if ( (unsigned int)dword_180047000 > 2 )
  {
    v12 = qword_180047018;
    if ( (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
    {
      v28 = v11;
      v29 = lpFileName[0];
      v13 = byte_18003F451;
      goto LABEL_19;
    }
  }
LABEL_72:
  if ( lpFileName[0] != v31 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 != -1 )
    FindClose((HANDLE)v5);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001bccc  push    rbp
0x18001bcce  push    rbx
0x18001bccf  push    rsi
0x18001bcd0  push    rdi
0x18001bcd1  push    r14
0x18001bcd3  push    r15
0x18001bcd5  lea     rbp, [rsp-208h]
0x18001bcdd  sub     rsp, 308h
0x18001bce4  mov     rax, cs:__security_cookie
0x18001bceb  xor     rax, rsp
0x18001bcee  mov     [rbp+230h+var_40], rax
0x18001bcf5  mov     rdi, rcx
0x18001bcf8  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001bcfc  lea     rax, [rsp+330h+var_2D0]
0x18001bd01  mov     [rsp+330h+lpFileName], rax
0x18001bd06  lea     rax, [rsp+330h+var_2D0]
0x18001bd0b  mov     [rsp+330h+var_2D8], rax
0x18001bd10  xor     r15d, r15d
0x18001bd13  mov     [rsp+330h+var_2D0], r15w
0x18001bd19  xor     edx, edx; Val
0x18001bd1b  mov     r8d, 250h; Size
0x18001bd21  lea     rcx, [rbp+230h+FindFileData]; void *
0x18001bd25  call    memset_0
0x18001bd2a  test    rdi, rdi
0x18001bd2d  jnz     short loc_18001BDAB
0x18001bd2f  mov     eax, cs:dword_180047000
0x18001bd35  cmp     eax, 2
0x18001bd38  jbe     short loc_18001BD85
0x18001bd3a  mov     rcx, cs:qword_180047018
0x18001bd41  mov     rax, cs:qword_180047010
0x18001bd48  test    al, 8
0x18001bd4a  jz      short loc_18001BD85
0x18001bd4c  mov     rax, rcx
0x18001bd4f  and     eax, 8
0x18001bd52  cmp     rax, rcx
0x18001bd55  jnz     short loc_18001BD85
0x18001bd57  lea     rax, [rbp+230h+var_60]
0x18001bd5e  mov     [rsp+330h+var_308], rax
0x18001bd63  mov     [rsp+330h+var_310], 2
0x18001bd6b  xor     r9d, r9d
0x18001bd6e  xor     r8d, r8d
0x18001bd71  lea     rdx, word_18003F652
0x18001bd78  lea     rcx, dword_180047000
0x18001bd7f  call    _tlgWriteTransfer_EventWriteTransfer
0x18001bd84  nop
0x18001bd85  lea     rax, [rsp+330h+var_2D0]
0x18001bd8a  mov     rcx, [rsp+330h+lpFileName]; void *
0x18001bd8f  cmp     rcx, rax
0x18001bd92  jz      short loc_18001BDA1
0x18001bd94  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001bd9b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001bda0  nop
0x18001bda1  mov     eax, 80070057h
0x18001bda6  jmp     loc_18001C230
0x18001bdab  mov     rcx, rdi; lpFileName
0x18001bdae  call    cs:__imp_GetFileAttributesW
0x18001bdb4  cmp     eax, 0FFFFFFFFh
0x18001bdb7  jnz     loc_18001BE3E
0x18001bdbd  call    cs:__imp_GetLastError
0x18001bdc3  mov     ebx, eax
0x18001bdc5  test    eax, eax
0x18001bdc7  jle     short loc_18001BDD2
0x18001bdc9  movzx   ebx, ax
0x18001bdcc  or      ebx, 80070000h
0x18001bdd2  mov     eax, 80004005h
0x18001bdd7  test    ebx, ebx
0x18001bdd9  cmovns  ebx, eax
0x18001bddc  mov     eax, cs:dword_180047000
0x18001bde2  cmp     eax, 2
0x18001bde5  jbe     loc_18001C203
0x18001bdeb  mov     rcx, cs:qword_180047018
0x18001bdf2  mov     rax, cs:qword_180047010
0x18001bdf9  test    al, 8
0x18001bdfb  jz      loc_18001C203
0x18001be01  mov     rax, rcx
0x18001be04  and     eax, 8
0x18001be07  cmp     rax, rcx
0x18001be0a  jnz     loc_18001C203
0x18001be10  mov     [rsp+330h+var_2F0], ebx
0x18001be14  lea     rdx, word_18003F606
0x18001be1b  mov     [rsp+330h+var_2E8], rdi
0x18001be20  lea     rax, [rsp+330h+var_2F0]
0x18001be25  mov     [rsp+330h+var_308], rax
0x18001be2a  lea     rax, [rsp+330h+var_2E8]
0x18001be2f  mov     qword ptr [rsp+330h+var_310], rax
0x18001be34  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18001be39  jmp     loc_18001C203
0x18001be3e  test    al, 10h
0x18001be40  jnz     short loc_18001BE8C
0x18001be42  mov     ebx, 80070057h
0x18001be47  mov     eax, cs:dword_180047000
0x18001be4d  cmp     eax, 2
0x18001be50  jbe     loc_18001C203
0x18001be56  mov     rcx, cs:qword_180047018
0x18001be5d  mov     rax, cs:qword_180047010
0x18001be64  test    al, 8
0x18001be66  jz      loc_18001C203
0x18001be6c  mov     rax, rcx
0x18001be6f  and     eax, 8
0x18001be72  cmp     rax, rcx
0x18001be75  jnz     loc_18001C203
0x18001be7b  mov     [rsp+330h+var_2F0], 80070057h
0x18001be83  lea     rdx, byte_18003F5BB
0x18001be8a  jmp     short loc_18001BE1B
0x18001be8c  bt      eax, 0Ah
0x18001be90  jnb     short loc_18001BEEB
0x18001be92  mov     ebx, 80070057h
0x18001be97  mov     eax, cs:dword_180047000
0x18001be9d  cmp     eax, 2
0x18001bea0  jbe     loc_18001C203
0x18001bea6  mov     rcx, cs:qword_180047018
0x18001bead  mov     rax, cs:qword_180047010
0x18001beb4  test    al, 8
0x18001beb6  jz      loc_18001C203
0x18001bebc  mov     rax, rcx
0x18001bebf  and     eax, 8
0x18001bec2  cmp     rax, rcx
0x18001bec5  jnz     loc_18001C203
0x18001becb  mov     [rsp+330h+var_2E8], rdi
0x18001bed0  lea     rax, [rsp+330h+var_2E8]
0x18001bed5  mov     qword ptr [rsp+330h+var_310], rax
0x18001beda  lea     rdx, word_18003F57A
0x18001bee1  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18001bee6  jmp     loc_18001C203
0x18001beeb  mov     r8, rdi
0x18001beee  lea     rdx, aLs; "%ls\\*"
0x18001bef5  lea     rcx, [rsp+330h+lpFileName]
0x18001befa  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18001beff  test    eax, eax
0x18001bf01  jns     short loc_18001BF50
0x18001bf03  mov     ebx, 80070057h
0x18001bf08  mov     eax, cs:dword_180047000
0x18001bf0e  cmp     eax, 2
0x18001bf11  jbe     loc_18001C203
0x18001bf17  mov     rcx, cs:qword_180047018
0x18001bf1e  mov     rax, cs:qword_180047010
0x18001bf25  test    al, 8
0x18001bf27  jz      loc_18001C203
0x18001bf2d  mov     rax, rcx
0x18001bf30  and     eax, 8
0x18001bf33  cmp     rax, rcx
0x18001bf36  jnz     loc_18001C203
0x18001bf3c  mov     [rsp+330h+var_2F0], 80070057h
0x18001bf44  lea     rdx, byte_18003F533
0x18001bf4b  jmp     loc_18001BE1B
0x18001bf50  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x18001bf54  mov     rcx, [rsp+330h+lpFileName]; lpFileName
0x18001bf59  call    cs:__imp_FindFirstFileW
0x18001bf5f  mov     rsi, rax
0x18001bf62  mov     r14, rax
0x18001bf65  mov     [rsp+330h+var_2C0], rax
0x18001bf6a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bf6e  jnz     short loc_18001BFDD
0x18001bf70  call    cs:__imp_GetLastError
0x18001bf76  mov     ebx, eax
0x18001bf78  test    eax, eax
0x18001bf7a  jle     short loc_18001BF85
0x18001bf7c  movzx   ebx, ax
0x18001bf7f  or      ebx, 80070000h
0x18001bf85  mov     eax, 80004005h
0x18001bf8a  test    ebx, ebx
0x18001bf8c  cmovns  ebx, eax
0x18001bf8f  mov     eax, cs:dword_180047000
0x18001bf95  cmp     eax, 2
0x18001bf98  jbe     loc_18001C203
0x18001bf9e  mov     rcx, cs:qword_180047018
0x18001bfa5  mov     rax, cs:qword_180047010
0x18001bfac  test    al, 8
0x18001bfae  jz      loc_18001C203
0x18001bfb4  mov     rax, rcx
0x18001bfb7  and     eax, 8
0x18001bfba  cmp     rax, rcx
0x18001bfbd  jnz     loc_18001C203
0x18001bfc3  mov     [rsp+330h+var_2F0], ebx
0x18001bfc7  mov     rax, [rsp+330h+lpFileName]
0x18001bfcc  mov     [rsp+330h+var_2E8], rax
0x18001bfd1  lea     rdx, byte_18003F4EB
0x18001bfd8  jmp     loc_18001BE20
0x18001bfdd  movzx   eax, [rbp+230h+FindFileData.cFileName+2]
0x18001bfe1  cmp     [rbp+230h+FindFileData.cFileName], 2Eh ; '.'
0x18001bfe6  jnz     short loc_18001C009
0x18001bfe8  test    ax, ax
0x18001bfeb  jz      loc_18001C10C
0x18001bff1  cmp     [rbp+230h+FindFileData.cFileName], 2Eh ; '.'
0x18001bff6  jnz     short loc_18001C009
0x18001bff8  cmp     ax, 2Eh ; '.'
0x18001bffc  jnz     short loc_18001C009
0x18001bffe  cmp     [rbp+230h+FindFileData.cFileName+4], r15w
0x18001c003  jz      loc_18001C10C
0x18001c009  lea     r9, [rbp+230h+FindFileData.cFileName]
0x18001c00d  mov     r8, rdi
0x18001c010  lea     rdx, aLsLs; "%ls\\%ls"
0x18001c017  lea     rcx, [rsp+330h+lpFileName]
0x18001c01c  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18001c021  mov     ebx, eax
0x18001c023  test    eax, eax
0x18001c025  js      loc_18001C19E
0x18001c02b  mov     rcx, [rsp+330h+lpFileName]; lpFileName
0x18001c030  test    byte ptr [rbp+230h+FindFileData.dwFileAttributes], 10h
0x18001c034  jz      short loc_18001C0A2
0x18001c036  mov     [rsp+330h+var_310], r15d; int
0x18001c03b  xor     r9d, r9d; wchar_t *
0x18001c03e  xor     r8d, r8d; wchar_t *
0x18001c041  lea     edx, [r9+1]; int
0x18001c045  call    ?UtilRecursiveRemoveDirectory@@YAJPEB_WH00H@Z; UtilRecursiveRemoveDirectory(wchar_t const *,int,wchar_t const *,wchar_t const *,int)
0x18001c04a  mov     ebx, eax
0x18001c04c  test    eax, eax
0x18001c04e  jns     loc_18001C10C
0x18001c054  mov     eax, cs:dword_180047000
0x18001c05a  cmp     eax, 2
0x18001c05d  jbe     loc_18001C203
0x18001c063  mov     rcx, cs:qword_180047018
0x18001c06a  mov     rax, cs:qword_180047010
0x18001c071  test    al, 8
0x18001c073  jz      loc_18001C203
0x18001c079  mov     rax, rcx
0x18001c07c  and     eax, 8
0x18001c07f  cmp     rax, rcx
0x18001c082  jnz     loc_18001C203
0x18001c088  mov     [rsp+330h+var_2F0], ebx
0x18001c08c  mov     rax, [rsp+330h+lpFileName]
0x18001c091  mov     [rsp+330h+var_2E8], rax
0x18001c096  lea     rdx, byte_18003F451
0x18001c09d  jmp     loc_18001BE20
0x18001c0a2  call    ?PreparePathForDeletion@_werDetail@@YAJPEB_W@Z; _werDetail::PreparePathForDeletion(wchar_t const *)
0x18001c0a7  test    eax, eax
0x18001c0a9  jns     short loc_18001C102
0x18001c0ab  mov     ecx, cs:dword_180047000
0x18001c0b1  cmp     ecx, 3
0x18001c0b4  jbe     short loc_18001C102
0x18001c0b6  mov     rdx, cs:qword_180047018
0x18001c0bd  mov     rcx, cs:qword_180047010
0x18001c0c4  test    cl, 8
0x18001c0c7  jz      short loc_18001C102
0x18001c0c9  mov     rcx, rdx
0x18001c0cc  and     ecx, 8
0x18001c0cf  cmp     rcx, rdx
0x18001c0d2  jnz     short loc_18001C102
0x18001c0d4  mov     [rsp+330h+var_2F0], eax
0x18001c0d8  mov     rax, [rsp+330h+lpFileName]
0x18001c0dd  mov     [rsp+330h+var_2E8], rax
0x18001c0e2  lea     rax, [rsp+330h+var_2F0]
0x18001c0e7  mov     [rsp+330h+var_308], rax
0x18001c0ec  lea     rax, [rsp+330h+var_2E8]
0x18001c0f1  mov     qword ptr [rsp+330h+var_310], rax
0x18001c0f6  lea     rdx, word_18003F40A
0x18001c0fd  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18001c102  mov     rcx, [rsp+330h+lpFileName]; wchar_t *
0x18001c107  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x18001c10c  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x18001c110  mov     rcx, rsi; hFindFile
0x18001c113  call    cs:__imp_FindNextFileW
0x18001c119  test    eax, eax
0x18001c11b  jnz     loc_18001BFDD
0x18001c121  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001c125  mov     [rsp+330h+var_2C0], r14
0x18001c12a  mov     rcx, rsi; hFindFile
0x18001c12d  call    cs:__imp_FindClose
0x18001c133  mov     rcx, rdi; lpFileName
0x18001c136  call    ?PreparePathForDeletion@_werDetail@@YAJPEB_W@Z; _werDetail::PreparePathForDeletion(wchar_t const *)
0x18001c13b  test    eax, eax
0x18001c13d  jns     short loc_18001C191
0x18001c13f  mov     ecx, cs:dword_180047000
0x18001c145  cmp     ecx, 3
0x18001c148  jbe     short loc_18001C191
0x18001c14a  mov     rdx, cs:qword_180047018
0x18001c151  mov     rcx, cs:qword_180047010
0x18001c158  test    cl, 8
0x18001c15b  jz      short loc_18001C191
0x18001c15d  mov     rcx, rdx
0x18001c160  and     ecx, 8
0x18001c163  cmp     rcx, rdx
0x18001c166  jnz     short loc_18001C191
0x18001c168  mov     [rsp+330h+var_2F0], eax
0x18001c16c  mov     [rsp+330h+var_2E8], rdi
0x18001c171  lea     rax, [rsp+330h+var_2F0]
0x18001c176  mov     [rsp+330h+var_308], rax
0x18001c17b  lea     rax, [rsp+330h+var_2E8]
0x18001c180  mov     qword ptr [rsp+330h+var_310], rax
0x18001c185  lea     rdx, byte_18003F3C3
0x18001c18c  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18001c191  mov     rcx, rdi; wchar_t *
0x18001c194  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x18001c199  mov     ebx, r15d
0x18001c19c  jmp     short loc_18001C203
0x18001c19e  mov     eax, cs:dword_180047000
0x18001c1a4  cmp     eax, 2
0x18001c1a7  jbe     short loc_18001C203
0x18001c1a9  mov     rcx, cs:qword_180047018
0x18001c1b0  mov     rax, cs:qword_180047010
0x18001c1b7  test    al, 8
0x18001c1b9  jz      short loc_18001C203
0x18001c1bb  mov     rax, rcx
0x18001c1be  and     eax, 8
0x18001c1c1  cmp     rax, rcx
0x18001c1c4  jnz     short loc_18001C203
0x18001c1c6  mov     [rsp+330h+var_2F0], ebx
0x18001c1ca  lea     rax, [rbp+230h+FindFileData.cFileName]
0x18001c1ce  mov     [rsp+330h+var_2C0], rax
0x18001c1d3  mov     [rsp+330h+var_2E8], rdi
  ... truncated ...
```
