# _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x1800306e4`
- end: `0x180030947`
- name: `?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `611`
- prototype: `__int64 __fastcall(HANDLE hFile, __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x1800072cc`
- `0x180030408`
- `0x18007fda8`

## callees

- `0x1800021d8`
- `0x18000716c`
- `0x180009b40`
- `0x180009bb4`
- `0x18000dad0`
- `0x18000ea64`
- `0x180023dc4`
- `0x1800303dc`
- `0x1800306e4`
- `0x180030950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003079d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800308db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003079d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800308db`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180030791`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800308b8`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180030791`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800308b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _werDetail::UtilGetFinalPathByHandle(HANDLE hFile, __int64 a2)
{
  unsigned __int64 v4; // rdi
  unsigned int FinalPathOnUnmountedVolume; // ebx
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  char *v9; // rdx
  DWORD FinalPathNameByHandleW; // eax
  DWORD LastError; // eax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int *v15; // rdx
  __int64 v16; // rdx
  unsigned __int64 v17; // rax
  DWORD v18; // eax
  DWORD v19; // eax
  LPWSTR lpszFilePath; // [rsp+30h] [rbp-20h] BYREF
  _WORD *v22; // [rsp+38h] [rbp-18h]
  _WORD v23[8]; // [rsp+40h] [rbp-10h] BYREF
  int v24; // [rsp+80h] [rbp+30h] BYREF
  int v25; // [rsp+88h] [rbp+38h] BYREF

  lpszFilePath = v23;
  LODWORD(v4) = 261;
  v22 = v23;
  v23[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                           &lpszFilePath,
                           261) )
  {
    FinalPathOnUnmountedVolume = -2147024882;
    if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
    {
      v9 = byte_1800C7195;
LABEL_5:
      v25 = v4;
      v24 = -2147024882;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (_DWORD)v9,
        v7,
        v8,
        (__int64)&v25,
        (__int64)&v24);
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, lpszFilePath, v22 - lpszFilePath, 0);
  v4 = FinalPathNameByHandleW;
  if ( !FinalPathNameByHandleW )
  {
    LastError = GetLastError();
    if ( LastError == 3 )
    {
      FinalPathOnUnmountedVolume = _werDetail::UtilGetFinalPathOnUnmountedVolume(hFile, a2);
      goto LABEL_31;
    }
    FinalPathOnUnmountedVolume = ERROR_HR_FROM_WIN32(LastError);
    if ( (unsigned int)dword_1800D9000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
      goto LABEL_31;
    v15 = (int *)&unk_1800C71E0;
    goto LABEL_12;
  }
  v16 = FinalPathNameByHandleW;
  v17 = v22 - lpszFilePath;
  if ( v4 == v17 )
  {
    FinalPathOnUnmountedVolume = -2147418113;
    if ( (unsigned int)dword_1800D9000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
      goto LABEL_31;
    v24 = -2147418113;
    v15 = &dword_1800C7214;
LABEL_13:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v12,
      (_DWORD)v15,
      v13,
      v14,
      (__int64)&v24);
    goto LABEL_31;
  }
  if ( v4 <= v17 )
    goto LABEL_30;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                          &lpszFilePath,
                          v16) )
  {
    v18 = GetFinalPathNameByHandleW(hFile, lpszFilePath, v22 - lpszFilePath, 0);
    if ( !v18 )
    {
      v19 = GetLastError();
LABEL_27:
      FinalPathOnUnmountedVolume = ERROR_HR_FROM_WIN32(v19);
      if ( (unsigned int)dword_1800D9000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
        goto LABEL_31;
      v15 = (int *)&unk_1800C7298;
LABEL_12:
      v24 = FinalPathOnUnmountedVolume;
      goto LABEL_13;
    }
    if ( v18 >= (unsigned __int64)(v22 - lpszFilePath) )
    {
      v19 = 111;
      goto LABEL_27;
    }
LABEL_30:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(&lpszFilePath);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, &lpszFilePath);
    FinalPathOnUnmountedVolume = 0;
    goto LABEL_31;
  }
  FinalPathOnUnmountedVolume = -2147024882;
  if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
  {
    v9 = byte_1800C7251;
    goto LABEL_5;
  }
LABEL_31:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpszFilePath);
  return FinalPathOnUnmountedVolume;
}

```

## disassembly

```asm
0x1800306e4  mov     [rsp-18h+arg_0], rbx
0x1800306e9  push    rbp
0x1800306ea  push    rsi
0x1800306eb  push    rdi
0x1800306ec  mov     rbp, rsp
0x1800306ef  sub     rsp, 50h
0x1800306f3  lea     rax, [rbp+var_10]
0x1800306f7  mov     rsi, rdx
0x1800306fa  mov     [rbp+lpszFilePath], rax
0x1800306fe  mov     rbx, rcx
0x180030701  lea     rax, [rbp+var_10]
0x180030705  mov     edi, 105h
0x18003070a  mov     [rbp+var_18], rax
0x18003070e  lea     rcx, [rbp+lpszFilePath]
0x180030712  xor     eax, eax
0x180030714  mov     edx, edi
0x180030716  mov     [rbp+var_10], ax
0x18003071a  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18003071f  test    al, al
0x180030721  jnz     short loc_18003077D
0x180030723  mov     eax, cs:dword_1800D9000
0x180030729  mov     ebx, 8007000Eh
0x18003072e  cmp     eax, 2
0x180030731  jbe     loc_18003092F
0x180030737  mov     edx, 8
0x18003073c  lea     rcx, dword_1800D9000
0x180030743  call    _tlgKeywordOn
0x180030748  test    al, al
0x18003074a  jz      loc_18003092F
0x180030750  lea     rdx, byte_1800C7195
0x180030757  lea     rax, [rbp+arg_10]
0x18003075b  mov     [rbp+arg_18], edi
0x18003075e  mov     [rsp+50h+var_28], rax
0x180030763  lea     rax, [rbp+arg_18]
0x180030767  mov     [rsp+50h+var_30], rax
0x18003076c  mov     [rbp+arg_10], 8007000Eh
0x180030773  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180030778  jmp     loc_18003092F
0x18003077d  mov     rdx, [rbp+lpszFilePath]; lpszFilePath
0x180030781  xor     r9d, r9d; dwFlags
0x180030784  mov     r8, [rbp+var_18]
0x180030788  mov     rcx, rbx; hFile
0x18003078b  sub     r8, rdx
0x18003078e  sar     r8, 1; cchFilePath
0x180030791  call    cs:__imp_GetFinalPathNameByHandleW
0x180030797  mov     edi, eax
0x180030799  test    eax, eax
0x18003079b  jnz     short loc_180030808
0x18003079d  call    cs:__imp_GetLastError
0x1800307a3  cmp     eax, 3
0x1800307a6  jnz     short loc_1800307BA
0x1800307a8  mov     rdx, rsi
0x1800307ab  mov     rcx, rbx
0x1800307ae  call    ?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800307b3  mov     ebx, eax
0x1800307b5  jmp     loc_18003092F
0x1800307ba  mov     ecx, eax; unsigned int
0x1800307bc  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800307c1  mov     ebx, eax
0x1800307c3  mov     eax, cs:dword_1800D9000
0x1800307c9  cmp     eax, 2
0x1800307cc  jbe     loc_18003092F
0x1800307d2  mov     edx, 8
0x1800307d7  lea     rcx, dword_1800D9000
0x1800307de  call    _tlgKeywordOn
0x1800307e3  test    al, al
0x1800307e5  jz      loc_18003092F
0x1800307eb  lea     rdx, unk_1800C71E0
0x1800307f2  mov     [rbp+arg_10], ebx
0x1800307f5  lea     rax, [rbp+arg_10]
0x1800307f9  mov     [rsp+50h+var_30], rax
0x1800307fe  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180030803  jmp     loc_18003092F
0x180030808  mov     rax, [rbp+var_18]
0x18003080c  mov     rdx, rdi
0x18003080f  sub     rax, [rbp+lpszFilePath]
0x180030813  sar     rax, 1
0x180030816  cmp     rdi, rax
0x180030819  jnz     short loc_180030858
0x18003081b  mov     eax, cs:dword_1800D9000
0x180030821  mov     ebx, 8000FFFFh
0x180030826  cmp     eax, 2
0x180030829  jbe     loc_18003092F
0x18003082f  mov     edx, 8
0x180030834  lea     rcx, dword_1800D9000
0x18003083b  call    _tlgKeywordOn
0x180030840  test    al, al
0x180030842  jz      loc_18003092F
0x180030848  mov     [rbp+arg_10], 8000FFFFh
0x18003084f  lea     rdx, dword_1800C7214
0x180030856  jmp     short loc_1800307F5
0x180030858  jbe     loc_180030916
0x18003085e  lea     rcx, [rbp+lpszFilePath]
0x180030862  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x180030867  test    al, al
0x180030869  jnz     short loc_1800308A4
0x18003086b  mov     eax, cs:dword_1800D9000
0x180030871  mov     ebx, 8007000Eh
0x180030876  cmp     eax, 2
0x180030879  jbe     loc_18003092F
0x18003087f  mov     edx, 8
0x180030884  lea     rcx, dword_1800D9000
0x18003088b  call    _tlgKeywordOn
0x180030890  test    al, al
0x180030892  jz      loc_18003092F
0x180030898  lea     rdx, byte_1800C7251
0x18003089f  jmp     loc_180030757
0x1800308a4  mov     rdx, [rbp+lpszFilePath]; lpszFilePath
0x1800308a8  xor     r9d, r9d; dwFlags
0x1800308ab  mov     r8, [rbp+var_18]
0x1800308af  mov     rcx, rbx; hFile
0x1800308b2  sub     r8, rdx
0x1800308b5  sar     r8, 1; cchFilePath
0x1800308b8  call    cs:__imp_GetFinalPathNameByHandleW
0x1800308be  mov     edi, eax
0x1800308c0  test    eax, eax
0x1800308c2  jz      short loc_1800308DB
0x1800308c4  mov     rcx, [rbp+var_18]
0x1800308c8  sub     rcx, [rbp+lpszFilePath]
0x1800308cc  sar     rcx, 1
0x1800308cf  cmp     rdi, rcx
0x1800308d2  jb      short loc_180030916
0x1800308d4  mov     eax, 6Fh ; 'o'
0x1800308d9  jmp     short loc_1800308E1
0x1800308db  call    cs:__imp_GetLastError
0x1800308e1  mov     ecx, eax; unsigned int
0x1800308e3  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800308e8  mov     ebx, eax
0x1800308ea  mov     eax, cs:dword_1800D9000
0x1800308f0  cmp     eax, 2
0x1800308f3  jbe     short loc_18003092F
0x1800308f5  mov     edx, 8
0x1800308fa  lea     rcx, dword_1800D9000
0x180030901  call    _tlgKeywordOn
0x180030906  test    al, al
0x180030908  jz      short loc_18003092F
0x18003090a  lea     rdx, unk_1800C7298
0x180030911  jmp     loc_1800307F2
0x180030916  mov     edx, edi
0x180030918  lea     rcx, [rbp+lpszFilePath]
0x18003091c  call    ?erase@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV12@_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(unsigned __int64)
0x180030921  lea     rdx, [rbp+lpszFilePath]
0x180030925  mov     rcx, rsi
0x180030928  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18003092d  xor     ebx, ebx
0x18003092f  lea     rcx, [rbp+lpszFilePath]; void *
0x180030933  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180030938  mov     eax, ebx
0x18003093a  mov     rbx, [rsp+50h+arg_0]
0x18003093f  add     rsp, 50h
0x180030943  pop     rdi
0x180030944  pop     rsi
0x180030945  pop     rbp
0x180030946  retn
```
