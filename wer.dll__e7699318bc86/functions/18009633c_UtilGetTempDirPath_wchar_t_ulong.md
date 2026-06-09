# UtilGetTempDirPath(wchar_t *,ulong)

- ea: `0x18009633c`
- end: `0x18009657e`
- name: `?UtilGetTempDirPath@@YAJPEA_WK@Z`
- size: `578`
- prototype: `__int64 __fastcall(WCHAR *lpFileName, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x18001bbc4`

## callees

- `0x180002acc`
- `0x18000716c`
- `0x18000dad0`
- `0x180023dc4`
- `0x180023e8c`
- `0x1800303dc`
- `0x180030408`
- `0x18005b8d1`
- `0x1800654ec`
- `0x18009633c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800963a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800964ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800963a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800964ac`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18009639d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18009639d`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180096370`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180096370`

## pseudocode

```c
__int64 __fastcall UtilGetTempDirPath(WCHAR *lpFileName, int a2)
{
  DWORD v3; // eax
  unsigned int v4; // ebx
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  unsigned __int64 v8; // rbx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  unsigned __int64 v12; // rbx
  DWORD LastError; // eax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  __int64 v21; // rcx
  void *Src; // [rsp+30h] [rbp-20h] BYREF
  char *v23; // [rsp+38h] [rbp-18h]
  _WORD v24[8]; // [rsp+40h] [rbp-10h] BYREF
  WCHAR *v25; // [rsp+70h] [rbp+20h] BYREF
  int v26; // [rsp+78h] [rbp+28h] BYREF

  v26 = a2;
  if ( lpFileName )
  {
    *lpFileName = 0;
    if ( !(unsigned int)GetTempPath2W(260, lpFileName) || !*lpFileName )
    {
      LastError = GetLastError();
      v4 = ERROR_HR_FROM_WIN32(LastError);
      if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
      {
        v26 = v4;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v14,
          (unsigned int)byte_1800C97BD,
          v15,
          v16,
          (__int64)&v26);
      }
      goto LABEL_21;
    }
    if ( UtilPathIsDirectory(lpFileName) || CreateDirectoryW(lpFileName, 0) )
    {
      v24[0] = 0;
      Src = v24;
      v23 = (char *)v24;
      if ( (unsigned int)UtilGetFinalPath(lpFileName) )
      {
        v8 = (v23 - (_BYTE *)Src) >> 1;
        if ( v8 >= 0x104 )
        {
          *lpFileName = 0;
          v4 = -2147024809;
          if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
          {
            v26 = -2147024809;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              v9,
              (unsigned int)byte_1800C9745,
              v10,
              v11,
              (__int64)&v26);
          }
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&Src);
          goto LABEL_21;
        }
        v12 = v8;
        memcpy_0(lpFileName, Src, v12 * 2);
        lpFileName[v12] = 0;
      }
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&Src);
      v4 = 0;
    }
    else
    {
      v3 = GetLastError();
      v4 = ERROR_HR_FROM_WIN32(v3);
      if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
      {
        v26 = v4;
        v25 = lpFileName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v5,
          (unsigned int)byte_1800C9779,
          v6,
          v7,
          (__int64)&v25,
          (__int64)&v26);
      }
      *lpFileName = 0;
    }
LABEL_21:
    if ( (unsigned int)dword_1800D9000 > 2 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
      {
        v26 = v4;
        v25 = lpFileName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&dword_1800C970C,
          v18,
          v19,
          (__int64)&v25,
          (__int64)&v26);
      }
    }
    return v4;
  }
  if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v21,
      byte_1800C97F1);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18009633c  mov     [rsp-18h+arg_10], rbx
0x180096341  mov     [rsp-18h+arg_18], rsi
0x180096346  mov     [rsp-18h+arg_8], edx
0x18009634a  push    rbp
0x18009634b  push    rdi
0x18009634c  push    r15
0x18009634e  mov     rbp, rsp
0x180096351  sub     rsp, 50h
0x180096355  xor     r15d, r15d
0x180096358  mov     rdi, rcx
0x18009635b  test    rcx, rcx
0x18009635e  jz      loc_180096538
0x180096364  mov     [rcx], r15w
0x180096368  mov     rdx, rcx
0x18009636b  mov     ecx, 104h
0x180096370  call    cs:__imp_GetTempPath2W
0x180096376  lea     esi, [r15+8]
0x18009637a  test    eax, eax
0x18009637c  jz      loc_1800964AC
0x180096382  cmp     [rdi], r15w
0x180096386  jz      loc_1800964AC
0x18009638c  mov     rcx, rdi; wchar_t *
0x18009638f  call    ?UtilPathIsDirectory@@YA_NPEB_W@Z; UtilPathIsDirectory(wchar_t const *)
0x180096394  test    al, al
0x180096396  jnz     short loc_180096401
0x180096398  xor     edx, edx; lpSecurityAttributes
0x18009639a  mov     rcx, rdi; lpPathName
0x18009639d  call    cs:__imp_CreateDirectoryW
0x1800963a3  test    eax, eax
0x1800963a5  jnz     short loc_180096401
0x1800963a7  call    cs:__imp_GetLastError
0x1800963ad  mov     ecx, eax; unsigned int
0x1800963af  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800963b4  mov     ebx, eax
0x1800963b6  mov     eax, cs:dword_1800D9000
0x1800963bc  cmp     eax, 2
0x1800963bf  jbe     short loc_1800963F8
0x1800963c1  mov     edx, esi
0x1800963c3  lea     rcx, dword_1800D9000
0x1800963ca  call    _tlgKeywordOn
0x1800963cf  test    al, al
0x1800963d1  jz      short loc_1800963F8
0x1800963d3  lea     rax, [rbp+arg_8]
0x1800963d7  mov     [rbp+arg_8], ebx
0x1800963da  mov     [rsp+50h+var_28], rax
0x1800963df  lea     rdx, byte_1800C9779
0x1800963e6  lea     rax, [rbp+arg_0]
0x1800963ea  mov     [rbp+arg_0], rdi
0x1800963ee  mov     [rsp+50h+var_30], rax
0x1800963f3  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1800963f8  mov     [rdi], r15w
0x1800963fc  jmp     loc_1800964F1
0x180096401  lea     rax, [rbp+var_10]
0x180096405  mov     [rbp+var_10], r15w
0x18009640a  mov     [rbp+Src], rax
0x18009640e  lea     rdx, [rbp+Src]
0x180096412  lea     rax, [rbp+var_10]
0x180096416  mov     rcx, rdi; lpFileName
0x180096419  mov     [rbp+var_18], rax
0x18009641d  call    ?UtilGetFinalPath@@YAHPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetFinalPath(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180096422  test    eax, eax
0x180096424  jz      short loc_18009649E
0x180096426  mov     rbx, [rbp+var_18]
0x18009642a  mov     rdx, [rbp+Src]; Src
0x18009642e  sub     rbx, rdx
0x180096431  sar     rbx, 1
0x180096434  cmp     rbx, 104h
0x18009643b  jb      short loc_18009648B
0x18009643d  mov     [rdi], r15w
0x180096441  mov     ebx, 80070057h
0x180096446  mov     eax, cs:dword_1800D9000
0x18009644c  cmp     eax, 2
0x18009644f  jbe     short loc_180096480
0x180096451  mov     rdx, rsi
0x180096454  lea     rcx, dword_1800D9000
0x18009645b  call    _tlgKeywordOn
0x180096460  test    al, al
0x180096462  jz      short loc_180096480
0x180096464  lea     rax, [rbp+arg_8]
0x180096468  mov     [rbp+arg_8], 80070057h
0x18009646f  lea     rdx, byte_1800C9745
0x180096476  mov     [rsp+50h+var_30], rax
0x18009647b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180096480  lea     rcx, [rbp+Src]; void *
0x180096484  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180096489  jmp     short loc_1800964F1
0x18009648b  add     rbx, rbx
0x18009648e  mov     rcx, rdi; void *
0x180096491  mov     r8, rbx; Size
0x180096494  call    memcpy_0
0x180096499  mov     [rbx+rdi], r15w
0x18009649e  lea     rcx, [rbp+Src]; void *
0x1800964a2  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800964a7  mov     ebx, r15d
0x1800964aa  jmp     short loc_1800964F1
0x1800964ac  call    cs:__imp_GetLastError
0x1800964b2  mov     ecx, eax; unsigned int
0x1800964b4  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800964b9  mov     ebx, eax
0x1800964bb  mov     eax, cs:dword_1800D9000
0x1800964c1  cmp     eax, 2
0x1800964c4  jbe     short loc_1800964F1
0x1800964c6  mov     rdx, rsi
0x1800964c9  lea     rcx, dword_1800D9000
0x1800964d0  call    _tlgKeywordOn
0x1800964d5  test    al, al
0x1800964d7  jz      short loc_1800964F1
0x1800964d9  lea     rax, [rbp+arg_8]
0x1800964dd  mov     [rbp+arg_8], ebx
0x1800964e0  lea     rdx, byte_1800C97BD
0x1800964e7  mov     [rsp+50h+var_30], rax
0x1800964ec  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800964f1  mov     eax, cs:dword_1800D9000
0x1800964f7  cmp     eax, 2
0x1800964fa  jbe     short loc_180096534
0x1800964fc  mov     rdx, rsi
0x1800964ff  lea     rcx, dword_1800D9000
0x180096506  call    _tlgKeywordOn
0x18009650b  test    al, al
0x18009650d  jz      short loc_180096534
0x18009650f  lea     rax, [rbp+arg_8]
0x180096513  mov     [rbp+arg_8], ebx
0x180096516  mov     [rsp+50h+var_28], rax
0x18009651b  lea     rdx, dword_1800C970C
0x180096522  lea     rax, [rbp+arg_0]
0x180096526  mov     [rbp+arg_0], rdi
0x18009652a  mov     [rsp+50h+var_30], rax
0x18009652f  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180096534  mov     eax, ebx
0x180096536  jmp     short loc_180096569
0x180096538  mov     eax, cs:dword_1800D9000
0x18009653e  cmp     eax, 2
0x180096541  jbe     short loc_180096564
0x180096543  mov     edx, 8
0x180096548  lea     rcx, dword_1800D9000
0x18009654f  call    _tlgKeywordOn
0x180096554  test    al, al
0x180096556  jz      short loc_180096564
0x180096558  lea     rdx, byte_1800C97F1
0x18009655f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180096564  mov     eax, 80070057h
0x180096569  lea     r11, [rsp+50h+var_s0]
0x18009656e  mov     rbx, [r11+30h]
0x180096572  mov     rsi, [r11+38h]
0x180096576  mov     rsp, r11
0x180096579  pop     r15
0x18009657b  pop     rdi
0x18009657c  pop     rbp
0x18009657d  retn
```
