# UtilGetTempDirPath(wchar_t *,ulong)

- ea: `0x18009a5dc`
- end: `0x18009a837`
- name: `?UtilGetTempDirPath@@YAJPEA_WK@Z`
- size: `603`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x180008298`

## callees

- `0x180002ae4`
- `0x18000db80`
- `0x18001c368`
- `0x1800235c8`
- `0x180023d28`
- `0x180031cd0`
- `0x180031d00`
- `0x18005dd11`
- `0x18006852c`
- `0x18009a5dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a75e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a75e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18009a643`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18009a643`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18009a610`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18009a610`

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
      if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      {
        v26 = v4;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v14,
          (unsigned int)byte_1800CE86D,
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
          if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
          {
            v26 = -2147024809;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              v9,
              (unsigned int)byte_1800CE7F5,
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
      if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      {
        v26 = v4;
        v25 = lpFileName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v5,
          (unsigned int)byte_1800CE829,
          v6,
          v7,
          (__int64)&v25,
          (__int64)&v26);
      }
      *lpFileName = 0;
    }
LABEL_21:
    if ( (unsigned int)dword_1800DE000 > 2 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      {
        v26 = v4;
        v25 = lpFileName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&dword_1800CE7BC,
          v18,
          v19,
          (__int64)&v25,
          (__int64)&v26);
      }
    }
    return v4;
  }
  if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v21,
      byte_1800CE8A1);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18009a5dc  mov     [rsp-18h+arg_10], rbx
0x18009a5e1  mov     [rsp-18h+arg_18], rsi
0x18009a5e6  mov     [rsp-18h+arg_8], edx
0x18009a5ea  push    rbp
0x18009a5eb  push    rdi
0x18009a5ec  push    r15
0x18009a5ee  mov     rbp, rsp
0x18009a5f1  sub     rsp, 50h
0x18009a5f5  xor     r15d, r15d
0x18009a5f8  mov     rdi, rcx
0x18009a5fb  test    rcx, rcx
0x18009a5fe  jz      loc_18009A7F0
0x18009a604  mov     [rcx], r15w
0x18009a608  mov     rdx, rcx
0x18009a60b  mov     ecx, 104h
0x18009a610  call    cs:__imp_GetTempPath2W
0x18009a617  nop     dword ptr [rax+rax+00h]
0x18009a61c  lea     esi, [r15+8]
0x18009a620  test    eax, eax
0x18009a622  jz      loc_18009A75E
0x18009a628  cmp     [rdi], r15w
0x18009a62c  jz      loc_18009A75E
0x18009a632  mov     rcx, rdi; wchar_t *
0x18009a635  call    ?UtilPathIsDirectory@@YA_NPEB_W@Z; UtilPathIsDirectory(wchar_t const *)
0x18009a63a  test    al, al
0x18009a63c  jnz     short loc_18009A6B3
0x18009a63e  xor     edx, edx; lpSecurityAttributes
0x18009a640  mov     rcx, rdi; lpPathName
0x18009a643  call    cs:__imp_CreateDirectoryW
0x18009a64a  nop     dword ptr [rax+rax+00h]
0x18009a64f  test    eax, eax
0x18009a651  jnz     short loc_18009A6B3
0x18009a653  call    cs:__imp_GetLastError
0x18009a65a  nop     dword ptr [rax+rax+00h]
0x18009a65f  mov     ecx, eax; unsigned int
0x18009a661  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009a666  mov     ebx, eax
0x18009a668  mov     eax, cs:dword_1800DE000
0x18009a66e  cmp     eax, 2
0x18009a671  jbe     short loc_18009A6AA
0x18009a673  mov     edx, esi
0x18009a675  lea     rcx, dword_1800DE000
0x18009a67c  call    _tlgKeywordOn
0x18009a681  test    al, al
0x18009a683  jz      short loc_18009A6AA
0x18009a685  lea     rax, [rbp+arg_8]
0x18009a689  mov     [rbp+arg_8], ebx
0x18009a68c  mov     [rsp+50h+var_28], rax
0x18009a691  lea     rdx, byte_1800CE829
0x18009a698  lea     rax, [rbp+arg_0]
0x18009a69c  mov     [rbp+arg_0], rdi
0x18009a6a0  mov     [rsp+50h+var_30], rax
0x18009a6a5  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18009a6aa  mov     [rdi], r15w
0x18009a6ae  jmp     loc_18009A7A9
0x18009a6b3  lea     rax, [rbp+var_10]
0x18009a6b7  mov     [rbp+var_10], r15w
0x18009a6bc  mov     [rbp+Src], rax
0x18009a6c0  lea     rdx, [rbp+Src]
0x18009a6c4  lea     rax, [rbp+var_10]
0x18009a6c8  mov     rcx, rdi; lpFileName
0x18009a6cb  mov     [rbp+var_18], rax
0x18009a6cf  call    ?UtilGetFinalPath@@YAHPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetFinalPath(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18009a6d4  test    eax, eax
0x18009a6d6  jz      short loc_18009A750
0x18009a6d8  mov     rbx, [rbp+var_18]
0x18009a6dc  mov     rdx, [rbp+Src]; Src
0x18009a6e0  sub     rbx, rdx
0x18009a6e3  sar     rbx, 1
0x18009a6e6  cmp     rbx, 104h
0x18009a6ed  jb      short loc_18009A73D
0x18009a6ef  mov     [rdi], r15w
0x18009a6f3  mov     ebx, 80070057h
0x18009a6f8  mov     eax, cs:dword_1800DE000
0x18009a6fe  cmp     eax, 2
0x18009a701  jbe     short loc_18009A732
0x18009a703  mov     rdx, rsi
0x18009a706  lea     rcx, dword_1800DE000
0x18009a70d  call    _tlgKeywordOn
0x18009a712  test    al, al
0x18009a714  jz      short loc_18009A732
0x18009a716  lea     rax, [rbp+arg_8]
0x18009a71a  mov     [rbp+arg_8], 80070057h
0x18009a721  lea     rdx, byte_1800CE7F5
0x18009a728  mov     [rsp+50h+var_30], rax
0x18009a72d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18009a732  lea     rcx, [rbp+Src]; void *
0x18009a736  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009a73b  jmp     short loc_18009A7A9
0x18009a73d  add     rbx, rbx
0x18009a740  mov     rcx, rdi; void *
0x18009a743  mov     r8, rbx; Size
0x18009a746  call    memcpy_0
0x18009a74b  mov     [rbx+rdi], r15w
0x18009a750  lea     rcx, [rbp+Src]; void *
0x18009a754  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009a759  mov     ebx, r15d
0x18009a75c  jmp     short loc_18009A7A9
0x18009a75e  call    cs:__imp_GetLastError
0x18009a765  nop     dword ptr [rax+rax+00h]
0x18009a76a  mov     ecx, eax; unsigned int
0x18009a76c  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009a771  mov     ebx, eax
0x18009a773  mov     eax, cs:dword_1800DE000
0x18009a779  cmp     eax, 2
0x18009a77c  jbe     short loc_18009A7A9
0x18009a77e  mov     rdx, rsi
0x18009a781  lea     rcx, dword_1800DE000
0x18009a788  call    _tlgKeywordOn
0x18009a78d  test    al, al
0x18009a78f  jz      short loc_18009A7A9
0x18009a791  lea     rax, [rbp+arg_8]
0x18009a795  mov     [rbp+arg_8], ebx
0x18009a798  lea     rdx, byte_1800CE86D
0x18009a79f  mov     [rsp+50h+var_30], rax
0x18009a7a4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18009a7a9  mov     eax, cs:dword_1800DE000
0x18009a7af  cmp     eax, 2
0x18009a7b2  jbe     short loc_18009A7EC
0x18009a7b4  mov     rdx, rsi
0x18009a7b7  lea     rcx, dword_1800DE000
0x18009a7be  call    _tlgKeywordOn
0x18009a7c3  test    al, al
0x18009a7c5  jz      short loc_18009A7EC
0x18009a7c7  lea     rax, [rbp+arg_8]
0x18009a7cb  mov     [rbp+arg_8], ebx
0x18009a7ce  mov     [rsp+50h+var_28], rax
0x18009a7d3  lea     rdx, dword_1800CE7BC
0x18009a7da  lea     rax, [rbp+arg_0]
0x18009a7de  mov     [rbp+arg_0], rdi
0x18009a7e2  mov     [rsp+50h+var_30], rax
0x18009a7e7  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18009a7ec  mov     eax, ebx
0x18009a7ee  jmp     short loc_18009A821
0x18009a7f0  mov     eax, cs:dword_1800DE000
0x18009a7f6  cmp     eax, 2
0x18009a7f9  jbe     short loc_18009A81C
0x18009a7fb  mov     edx, 8
0x18009a800  lea     rcx, dword_1800DE000
0x18009a807  call    _tlgKeywordOn
0x18009a80c  test    al, al
0x18009a80e  jz      short loc_18009A81C
0x18009a810  lea     rdx, byte_1800CE8A1
0x18009a817  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18009a81c  mov     eax, 80070057h
0x18009a821  lea     r11, [rsp+50h+var_s0]
0x18009a826  mov     rbx, [r11+30h]
0x18009a82a  mov     rsi, [r11+38h]
0x18009a82e  mov     rsp, r11
0x18009a831  pop     r15
0x18009a833  pop     rdi
0x18009a834  pop     rbp
0x18009a835  retn
```
