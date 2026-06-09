# _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x180031ff4`
- end: `0x180032270`
- name: `?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `636`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `3`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x18002a758`
- `0x180031d00`
- `0x180083840`

## callees

- `0x1800021f0`
- `0x18000add4`
- `0x18000ae48`
- `0x18000db80`
- `0x18001c368`
- `0x1800235c8`
- `0x180025560`
- `0x180031cd0`
- `0x180031ff4`
- `0x180032278`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321fd`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800320a1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800321d4`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800320a1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800321d4`

## pseudocode

```c
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
    if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
    {
      v9 = byte_1800CC245;
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
    if ( (unsigned int)dword_1800DE000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      goto LABEL_31;
    v15 = (int *)&unk_1800CC290;
    goto LABEL_12;
  }
  v16 = FinalPathNameByHandleW;
  v17 = v22 - lpszFilePath;
  if ( v4 == v17 )
  {
    FinalPathOnUnmountedVolume = -2147418113;
    if ( (unsigned int)dword_1800DE000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      goto LABEL_31;
    v24 = -2147418113;
    v15 = &dword_1800CC2C4;
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
    LODWORD(v4) = v18;
    if ( !v18 )
    {
      v19 = GetLastError();
LABEL_27:
      FinalPathOnUnmountedVolume = ERROR_HR_FROM_WIN32(v19);
      if ( (unsigned int)dword_1800DE000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
        goto LABEL_31;
      v15 = (int *)&unk_1800CC348;
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
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(&lpszFilePath, (unsigned int)v4);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, &lpszFilePath);
    FinalPathOnUnmountedVolume = 0;
    goto LABEL_31;
  }
  FinalPathOnUnmountedVolume = -2147024882;
  if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
  {
    v9 = byte_1800CC301;
    goto LABEL_5;
  }
LABEL_31:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpszFilePath);
  return FinalPathOnUnmountedVolume;
}

```

## disassembly

```asm
0x180031ff4  mov     [rsp-18h+arg_0], rbx
0x180031ff9  push    rbp
0x180031ffa  push    rsi
0x180031ffb  push    rdi
0x180031ffc  mov     rbp, rsp
0x180031fff  sub     rsp, 50h
0x180032003  lea     rax, [rbp+var_10]
0x180032007  mov     rsi, rdx
0x18003200a  mov     [rbp+lpszFilePath], rax
0x18003200e  mov     rbx, rcx
0x180032011  lea     rax, [rbp+var_10]
0x180032015  mov     edi, 105h
0x18003201a  mov     [rbp+var_18], rax
0x18003201e  lea     rcx, [rbp+lpszFilePath]
0x180032022  xor     eax, eax
0x180032024  mov     edx, edi
0x180032026  mov     [rbp+var_10], ax
0x18003202a  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18003202f  test    al, al
0x180032031  jnz     short loc_18003208D
0x180032033  mov     eax, cs:dword_1800DE000
0x180032039  mov     ebx, 8007000Eh
0x18003203e  cmp     eax, 2
0x180032041  jbe     loc_180032257
0x180032047  mov     edx, 8
0x18003204c  lea     rcx, dword_1800DE000
0x180032053  call    _tlgKeywordOn
0x180032058  test    al, al
0x18003205a  jz      loc_180032257
0x180032060  lea     rdx, byte_1800CC245
0x180032067  lea     rax, [rbp+arg_10]
0x18003206b  mov     [rbp+arg_18], edi
0x18003206e  mov     [rsp+50h+var_28], rax
0x180032073  lea     rax, [rbp+arg_18]
0x180032077  mov     [rsp+50h+var_30], rax
0x18003207c  mov     [rbp+arg_10], 8007000Eh
0x180032083  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180032088  jmp     loc_180032257
0x18003208d  mov     rdx, [rbp+lpszFilePath]; lpszFilePath
0x180032091  xor     r9d, r9d; dwFlags
0x180032094  mov     r8, [rbp+var_18]
0x180032098  mov     rcx, rbx; hFile
0x18003209b  sub     r8, rdx
0x18003209e  sar     r8, 1; cchFilePath
0x1800320a1  call    cs:__imp_GetFinalPathNameByHandleW
0x1800320a8  nop     dword ptr [rax+rax+00h]
0x1800320ad  mov     edi, eax
0x1800320af  test    eax, eax
0x1800320b1  jnz     short loc_180032124
0x1800320b3  call    cs:__imp_GetLastError
0x1800320ba  nop     dword ptr [rax+rax+00h]
0x1800320bf  cmp     eax, 3
0x1800320c2  jnz     short loc_1800320D6
0x1800320c4  mov     rdx, rsi
0x1800320c7  mov     rcx, rbx
0x1800320ca  call    ?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800320cf  mov     ebx, eax
0x1800320d1  jmp     loc_180032257
0x1800320d6  mov     ecx, eax; unsigned int
0x1800320d8  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800320dd  mov     ebx, eax
0x1800320df  mov     eax, cs:dword_1800DE000
0x1800320e5  cmp     eax, 2
0x1800320e8  jbe     loc_180032257
0x1800320ee  mov     edx, 8
0x1800320f3  lea     rcx, dword_1800DE000
0x1800320fa  call    _tlgKeywordOn
0x1800320ff  test    al, al
0x180032101  jz      loc_180032257
0x180032107  lea     rdx, unk_1800CC290
0x18003210e  mov     [rbp+arg_10], ebx
0x180032111  lea     rax, [rbp+arg_10]
0x180032115  mov     [rsp+50h+var_30], rax
0x18003211a  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003211f  jmp     loc_180032257
0x180032124  mov     rax, [rbp+var_18]
0x180032128  mov     rdx, rdi
0x18003212b  sub     rax, [rbp+lpszFilePath]
0x18003212f  sar     rax, 1
0x180032132  cmp     rdi, rax
0x180032135  jnz     short loc_180032174
0x180032137  mov     eax, cs:dword_1800DE000
0x18003213d  mov     ebx, 8000FFFFh
0x180032142  cmp     eax, 2
0x180032145  jbe     loc_180032257
0x18003214b  mov     edx, 8
0x180032150  lea     rcx, dword_1800DE000
0x180032157  call    _tlgKeywordOn
0x18003215c  test    al, al
0x18003215e  jz      loc_180032257
0x180032164  mov     [rbp+arg_10], 8000FFFFh
0x18003216b  lea     rdx, dword_1800CC2C4
0x180032172  jmp     short loc_180032111
0x180032174  jbe     loc_18003223E
0x18003217a  lea     rcx, [rbp+lpszFilePath]
0x18003217e  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x180032183  test    al, al
0x180032185  jnz     short loc_1800321C0
0x180032187  mov     eax, cs:dword_1800DE000
0x18003218d  mov     ebx, 8007000Eh
0x180032192  cmp     eax, 2
0x180032195  jbe     loc_180032257
0x18003219b  mov     edx, 8
0x1800321a0  lea     rcx, dword_1800DE000
0x1800321a7  call    _tlgKeywordOn
0x1800321ac  test    al, al
0x1800321ae  jz      loc_180032257
0x1800321b4  lea     rdx, byte_1800CC301
0x1800321bb  jmp     loc_180032067
0x1800321c0  mov     rdx, [rbp+lpszFilePath]; lpszFilePath
0x1800321c4  xor     r9d, r9d; dwFlags
0x1800321c7  mov     r8, [rbp+var_18]
0x1800321cb  mov     rcx, rbx; hFile
0x1800321ce  sub     r8, rdx
0x1800321d1  sar     r8, 1; cchFilePath
0x1800321d4  call    cs:__imp_GetFinalPathNameByHandleW
0x1800321db  nop     dword ptr [rax+rax+00h]
0x1800321e0  mov     edi, eax
0x1800321e2  test    eax, eax
0x1800321e4  jz      short loc_1800321FD
0x1800321e6  mov     rcx, [rbp+var_18]
0x1800321ea  sub     rcx, [rbp+lpszFilePath]
0x1800321ee  sar     rcx, 1
0x1800321f1  cmp     rdi, rcx
0x1800321f4  jb      short loc_18003223E
0x1800321f6  mov     eax, 6Fh ; 'o'
0x1800321fb  jmp     short loc_180032209
0x1800321fd  call    cs:__imp_GetLastError
0x180032204  nop     dword ptr [rax+rax+00h]
0x180032209  mov     ecx, eax; unsigned int
0x18003220b  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180032210  mov     ebx, eax
0x180032212  mov     eax, cs:dword_1800DE000
0x180032218  cmp     eax, 2
0x18003221b  jbe     short loc_180032257
0x18003221d  mov     edx, 8
0x180032222  lea     rcx, dword_1800DE000
0x180032229  call    _tlgKeywordOn
0x18003222e  test    al, al
0x180032230  jz      short loc_180032257
0x180032232  lea     rdx, unk_1800CC348
0x180032239  jmp     loc_18003210E
0x18003223e  mov     edx, edi
0x180032240  lea     rcx, [rbp+lpszFilePath]
0x180032244  call    ?erase@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV12@_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(unsigned __int64)
0x180032249  lea     rdx, [rbp+lpszFilePath]
0x18003224d  mov     rcx, rsi
0x180032250  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x180032255  xor     ebx, ebx
0x180032257  lea     rcx, [rbp+lpszFilePath]; void *
0x18003225b  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180032260  mov     eax, ebx
0x180032262  mov     rbx, [rsp+50h+arg_0]
0x180032267  add     rsp, 50h
0x18003226b  pop     rdi
0x18003226c  pop     rsi
0x18003226d  pop     rbp
0x18003226e  retn
```
