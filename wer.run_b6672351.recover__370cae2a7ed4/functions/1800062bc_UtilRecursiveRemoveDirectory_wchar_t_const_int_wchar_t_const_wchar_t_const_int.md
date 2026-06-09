# UtilRecursiveRemoveDirectory(wchar_t const *,int,wchar_t const *,wchar_t const *,int)

- ea: `0x1800062bc`
- end: `0x180006885`
- name: `?UtilRecursiveRemoveDirectory@@YAJPEB_WH00H@Z`
- size: `1481`
- prototype: `__int64 __fastcall(const wchar_t *, int, const wchar_t *, const wchar_t *, int)`
- caller_count: `8`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005cd4`
- `0x1800062bc`
- `0x180007878`
- `0x18004f8b8`
- `0x180069360`
- `0x180078ca8`
- `0x18007950c`
- `0x18008f2ec`

## callees

- `0x180002ae4`
- `0x180002b34`
- `0x1800062bc`
- `0x18000db80`
- `0x18000e31c`
- `0x18001b044`
- `0x18001c368`
- `0x18001e658`
- `0x180023d28`
- `0x180028648`
- `0x18002a52c`
- `0x180031cd0`
- `0x180053300`
- `0x180053d3c`
- `0x180066ba8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800065ac`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800065f4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800065ac`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800065f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006378`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006378`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067e7`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800066f1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800066f1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180006501`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180006501`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180006367`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180006367`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilRecursiveRemoveDirectory(const wchar_t *a1, int a2, const wchar_t *a3, const wchar_t *a4)
{
  __int64 v8; // rcx
  int v9; // ebx
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  LPCWSTR *p_cFileName; // rax
  __int16 *v16; // rdx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  HANDLE FirstFileW; // rax
  __int64 v27; // r9
  __int64 v28; // rdx
  const WCHAR *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // r9
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  const wchar_t *v35; // rdx
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  DWORD v42; // eax
  int v44; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *cFileName; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFindFile; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-A8h] BYREF
  _WORD *v48; // [rsp+60h] [rbp-A0h]
  _WORD v49[8]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR v50; // [rsp+78h] [rbp-88h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF

  hFindFile = (HANDLE)-1LL;
  lpFileName = v49;
  v48 = v49;
  v49[0] = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 )
  {
    if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v8,
        &word_1800CCA46);
    v9 = -2147024809;
    goto LABEL_66;
  }
  FileAttributesW = GetFileAttributesW(a1);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    v9 = ERROR_HR_FROM_WIN32(LastError);
    if ( (unsigned int)dword_1800DE000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      goto LABEL_66;
    cFileName = a1;
    p_cFileName = &cFileName;
    v16 = (__int16 *)&byte_1800CCA77;
    goto LABEL_65;
  }
  if ( (FileAttributesW & 0x10) == 0 )
  {
    v9 = -2147024809;
    if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
    {
      v44 = -2147024809;
      cFileName = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v17,
        (unsigned int)byte_1800CCAC3,
        v18,
        v19,
        (__int64)&cFileName,
        (__int64)&v44);
    }
    goto LABEL_66;
  }
  if ( (FileAttributesW & 0x400) != 0 )
  {
    v9 = -2147024809;
    if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
    {
      cFileName = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        v20,
        (unsigned int)&word_1800CCB0E,
        v21,
        v22,
        (__int64)&cFileName);
    }
    goto LABEL_66;
  }
  if ( (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpFileName, L"%ls\\*", a1) < 0 )
  {
    v9 = -2147024809;
    if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
    {
      v44 = -2147024809;
      cFileName = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v23,
        (unsigned int)&byte_1800CCB4F,
        v24,
        v25,
        (__int64)&cFileName,
        (__int64)&v44);
    }
    goto LABEL_66;
  }
  FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
  tlx::unique_any<tlx::find_handle_traits>::reset(&hFindFile, FirstFileW);
  if ( hFindFile == (HANDLE)-1LL )
  {
    v42 = GetLastError();
    v9 = ERROR_HR_FROM_WIN32(v42);
    if ( (unsigned int)dword_1800DE000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      goto LABEL_66;
    v50 = lpFileName;
    p_cFileName = &v50;
    v16 = &word_1800CCB96;
LABEL_65:
    v44 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      v12,
      (_DWORD)v16,
      v13,
      v14,
      (__int64)p_cFileName,
      (__int64)&v44);
    goto LABEL_66;
  }
  while ( 1 )
  {
    if ( FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
    {
      goto LABEL_52;
    }
    v9 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
           &lpFileName,
           L"%ls\\%ls",
           a1,
           FindFileData.cFileName);
    if ( v9 < 0 )
    {
      if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      {
        v44 = v9;
        cFileName = FindFileData.cFileName;
        v50 = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v39,
          (unsigned int)&word_1800CCBDE,
          v40,
          v41,
          (__int64)&v50,
          (__int64)&cFileName,
          (__int64)&v44);
      }
      goto LABEL_66;
    }
    if ( !a3 )
      goto LABEL_33;
    v27 = -1;
    do
      ++v27;
    while ( a3[v27] );
    v28 = (__int64)v48;
    v29 = lpFileName;
    v30 = v48 - lpFileName;
    if ( v30 == v27 )
    {
      if ( CompareStringOrdinal(lpFileName, v30, a3, v27, 1) == 2 )
        goto LABEL_52;
LABEL_33:
      v28 = (__int64)v48;
      v29 = lpFileName;
    }
    if ( a4 )
    {
      v31 = -1;
      do
        ++v31;
      while ( a4[v31] );
      v28 = (v28 - (__int64)v29) >> 1;
      if ( v28 == v31 )
      {
        if ( CompareStringOrdinal(v29, v28, a4, v31, 1) == 2 )
          goto LABEL_52;
        v29 = lpFileName;
      }
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      if ( a2 )
      {
        if ( (int)_werDetail::PreparePathForDeletion(v29, (const wchar_t *)v28) < 0
          && (unsigned int)dword_1800DE000 > 3
          && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
        {
          v44 = v33;
          cFileName = lpFileName;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
            v32,
            (unsigned int)&unk_1800CCC78,
            v33,
            v34,
            (__int64)&cFileName,
            (__int64)&v44);
        }
        v29 = lpFileName;
      }
      UtilDeleteFilePath(v29);
      goto LABEL_52;
    }
    v9 = UtilRecursiveRemoveDirectory(v29, a2, a3, a4, 0);
    if ( v9 < 0 )
      break;
LABEL_52:
    if ( !FindNextFileW(hFindFile, &FindFileData) )
    {
      tlx::unique_any<tlx::find_handle_traits>::reset(&hFindFile, -1);
      if ( a2
        && (int)_werDetail::PreparePathForDeletion(a1, v35) < 0
        && (unsigned int)dword_1800DE000 > 3
        && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      {
        v44 = v37;
        cFileName = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v36,
          (unsigned int)&byte_1800CCCBF,
          v37,
          v38,
          (__int64)&cFileName,
          (__int64)&v44);
      }
      UtilDeleteFilePath(a1);
      v9 = 0;
      goto LABEL_66;
    }
  }
  if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
  {
    cFileName = lpFileName;
    p_cFileName = &cFileName;
    v16 = (__int16 *)&unk_1800CCC30;
    goto LABEL_65;
  }
LABEL_66:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpFileName);
  tlx::unique_any<tlx::find_handle_traits>::~unique_any<tlx::find_handle_traits>(&hFindFile);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800062bc  push    rbp
0x1800062be  push    rbx
0x1800062bf  push    rsi
0x1800062c0  push    r12
0x1800062c2  push    r13
0x1800062c4  push    r14
0x1800062c6  push    r15
0x1800062c8  lea     rbp, [rsp-1E0h]
0x1800062d0  sub     rsp, 2E0h
0x1800062d7  mov     rax, cs:__security_cookie
0x1800062de  xor     rax, rsp
0x1800062e1  mov     [rbp+210h+var_40], rax
0x1800062e8  mov     r12, r9
0x1800062eb  mov     r14, r8
0x1800062ee  mov     r15d, edx
0x1800062f1  mov     rsi, rcx
0x1800062f4  mov     [rsp+310h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x1800062fd  lea     rax, [rsp+310h+var_2A8]
0x180006302  mov     [rsp+310h+lpFileName], rax
0x180006307  lea     rax, [rsp+310h+var_2A8]
0x18000630c  mov     [rsp+310h+var_2B0], rax
0x180006311  xor     r13d, r13d
0x180006314  mov     [rsp+310h+var_2A8], r13w
0x18000631a  xor     edx, edx; Val
0x18000631c  mov     r8d, 250h; Size
0x180006322  lea     rcx, [rbp+210h+FindFileData]; void *
0x180006326  call    memset_0
0x18000632b  test    rsi, rsi
0x18000632e  jnz     short loc_180006364
0x180006330  mov     eax, cs:dword_1800DE000
0x180006336  cmp     eax, 2
0x180006339  jbe     short loc_18000635A
0x18000633b  lea     edx, [rsi+8]
0x18000633e  lea     rcx, dword_1800DE000
0x180006345  call    _tlgKeywordOn
0x18000634a  test    al, al
0x18000634c  jz      short loc_18000635A
0x18000634e  lea     rdx, word_1800CCA46
0x180006355  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000635a  mov     ebx, 80070057h
0x18000635f  jmp     loc_18000684B
0x180006364  mov     rcx, rsi; lpFileName
0x180006367  call    cs:__imp_GetFileAttributesW
0x18000636e  nop     dword ptr [rax+rax+00h]
0x180006373  cmp     eax, 0FFFFFFFFh
0x180006376  jnz     short loc_1800063D5
0x180006378  call    cs:__imp_GetLastError
0x18000637f  nop     dword ptr [rax+rax+00h]
0x180006384  mov     ecx, eax; unsigned int
0x180006386  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000638b  mov     ebx, eax
0x18000638d  mov     eax, cs:dword_1800DE000
0x180006393  cmp     eax, 2
0x180006396  jbe     loc_18000684B
0x18000639c  mov     edx, 8
0x1800063a1  lea     rcx, dword_1800DE000
0x1800063a8  call    _tlgKeywordOn
0x1800063ad  test    al, al
0x1800063af  jz      loc_18000684B
0x1800063b5  mov     [rsp+310h+var_2C8], rsi
0x1800063ba  lea     rax, [rsp+310h+var_2D0]
0x1800063bf  mov     [rsp+310h+var_2E8], rax
0x1800063c4  lea     rax, [rsp+310h+var_2C8]
0x1800063c9  lea     rdx, byte_1800CCA77
0x1800063d0  jmp     loc_18000683C
0x1800063d5  test    al, 10h
0x1800063d7  jnz     short loc_180006433
0x1800063d9  mov     ebx, 80070057h
0x1800063de  mov     eax, cs:dword_1800DE000
0x1800063e4  cmp     eax, 2
0x1800063e7  jbe     loc_18000684B
0x1800063ed  mov     edx, 8
0x1800063f2  lea     rcx, dword_1800DE000
0x1800063f9  call    _tlgKeywordOn
0x1800063fe  test    al, al
0x180006400  jz      loc_18000684B
0x180006406  mov     [rsp+310h+var_2D0], 80070057h
0x18000640e  mov     [rsp+310h+var_2C8], rsi
0x180006413  lea     rax, [rsp+310h+var_2D0]
0x180006418  mov     [rsp+310h+var_2E8], rax
0x18000641d  lea     rax, [rsp+310h+var_2C8]
0x180006422  mov     qword ptr [rsp+310h+bIgnoreCase], rax
0x180006427  lea     rdx, byte_1800CCAC3
0x18000642e  jmp     loc_180006845
0x180006433  bt      eax, 0Ah
0x180006437  jnb     short loc_180006486
0x180006439  mov     ebx, 80070057h
0x18000643e  mov     eax, cs:dword_1800DE000
0x180006444  cmp     eax, 2
0x180006447  jbe     loc_18000684B
0x18000644d  mov     edx, 8
0x180006452  lea     rcx, dword_1800DE000
0x180006459  call    _tlgKeywordOn
0x18000645e  test    al, al
0x180006460  jz      loc_18000684B
0x180006466  mov     [rsp+310h+var_2C8], rsi
0x18000646b  lea     rax, [rsp+310h+var_2C8]
0x180006470  mov     qword ptr [rsp+310h+bIgnoreCase], rax
0x180006475  lea     rdx, word_1800CCB0E
0x18000647c  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180006481  jmp     loc_18000684B
0x180006486  mov     r8, rsi
0x180006489  lea     rdx, aLs; "%ls\\*"
0x180006490  lea     rcx, [rsp+310h+lpFileName]
0x180006495  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18000649a  test    eax, eax
0x18000649c  jns     short loc_1800064F8
0x18000649e  mov     ebx, 80070057h
0x1800064a3  mov     eax, cs:dword_1800DE000
0x1800064a9  cmp     eax, 2
0x1800064ac  jbe     loc_18000684B
0x1800064b2  mov     edx, 8
0x1800064b7  lea     rcx, dword_1800DE000
0x1800064be  call    _tlgKeywordOn
0x1800064c3  test    al, al
0x1800064c5  jz      loc_18000684B
0x1800064cb  mov     [rsp+310h+var_2D0], 80070057h
0x1800064d3  mov     [rsp+310h+var_2C8], rsi
0x1800064d8  lea     rax, [rsp+310h+var_2D0]
0x1800064dd  mov     [rsp+310h+var_2E8], rax
0x1800064e2  lea     rax, [rsp+310h+var_2C8]
0x1800064e7  mov     qword ptr [rsp+310h+bIgnoreCase], rax
0x1800064ec  lea     rdx, byte_1800CCB4F
0x1800064f3  jmp     loc_180006845
0x1800064f8  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x1800064fc  mov     rcx, [rsp+310h+lpFileName]; lpFileName
0x180006501  call    cs:__imp_FindFirstFileW
0x180006508  nop     dword ptr [rax+rax+00h]
0x18000650d  mov     rdx, rax
0x180006510  lea     rcx, [rsp+310h+hFindFile]
0x180006515  call    ?reset@?$unique_any@Ufind_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::find_handle_traits>::reset(void *)
0x18000651a  cmp     [rsp+310h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x180006520  jz      loc_1800067E7
0x180006526  movzx   eax, [rbp+210h+FindFileData.cFileName+2]
0x18000652a  cmp     [rbp+210h+FindFileData.cFileName], 2Eh ; '.'
0x18000652f  jnz     short loc_180006552
0x180006531  test    ax, ax
0x180006534  jz      loc_1800066E8
0x18000653a  cmp     [rbp+210h+FindFileData.cFileName], 2Eh ; '.'
0x18000653f  jnz     short loc_180006552
0x180006541  cmp     ax, 2Eh ; '.'
0x180006545  jnz     short loc_180006552
0x180006547  cmp     [rbp+210h+FindFileData.cFileName+4], r13w
0x18000654c  jz      loc_1800066E8
0x180006552  lea     r9, [rbp+210h+FindFileData.cFileName]
0x180006556  mov     r8, rsi
0x180006559  lea     rdx, aLsLs_1; "%ls\\%ls"
0x180006560  lea     rcx, [rsp+310h+lpFileName]
0x180006565  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18000656a  mov     ebx, eax
0x18000656c  test    eax, eax
0x18000656e  js      loc_180006781
0x180006574  test    r14, r14
0x180006577  jz      short loc_1800065C1
0x180006579  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000657d  inc     r9; cchCount2
0x180006580  cmp     [r14+r9*2], r13w
0x180006585  jnz     short loc_18000657D
0x180006587  mov     rdx, [rsp+310h+var_2B0]
0x18000658c  mov     rax, rdx
0x18000658f  mov     rcx, [rsp+310h+lpFileName]; lpString1
0x180006594  sub     rax, rcx
0x180006597  sar     rax, 1
0x18000659a  cmp     rax, r9
0x18000659d  jnz     short loc_1800065CB
0x18000659f  mov     edx, eax; cchCount1
0x1800065a1  mov     [rsp+310h+bIgnoreCase], 1; bIgnoreCase
0x1800065a9  mov     r8, r14; lpString2
0x1800065ac  call    cs:__imp_CompareStringOrdinal
0x1800065b3  nop     dword ptr [rax+rax+00h]
0x1800065b8  cmp     eax, 2
0x1800065bb  jz      loc_1800066E8
0x1800065c1  mov     rdx, [rsp+310h+var_2B0]
0x1800065c6  mov     rcx, [rsp+310h+lpFileName]; lpString1
0x1800065cb  test    r12, r12
0x1800065ce  jz      short loc_18000660E
0x1800065d0  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800065d4  inc     r9; cchCount2
0x1800065d7  cmp     [r12+r9*2], r13w
0x1800065dc  jnz     short loc_1800065D4
0x1800065de  sub     rdx, rcx
0x1800065e1  sar     rdx, 1; cchCount1
0x1800065e4  cmp     rdx, r9
0x1800065e7  jnz     short loc_18000660E
0x1800065e9  mov     [rsp+310h+bIgnoreCase], 1; bIgnoreCase
0x1800065f1  mov     r8, r12; lpString2
0x1800065f4  call    cs:__imp_CompareStringOrdinal
0x1800065fb  nop     dword ptr [rax+rax+00h]
0x180006600  cmp     eax, 2
0x180006603  jz      loc_1800066E8
0x180006609  mov     rcx, [rsp+310h+lpFileName]; lpFileName
0x18000660e  test    byte ptr [rbp+210h+FindFileData.dwFileAttributes], 10h
0x180006612  jz      short loc_18000667E
0x180006614  mov     [rsp+310h+bIgnoreCase], r13d; int
0x180006619  mov     r9, r12; wchar_t *
0x18000661c  mov     r8, r14; wchar_t *
0x18000661f  mov     edx, r15d; int
0x180006622  call    ?UtilRecursiveRemoveDirectory@@YAJPEB_WH00H@Z; UtilRecursiveRemoveDirectory(wchar_t const *,int,wchar_t const *,wchar_t const *,int)
0x180006627  mov     ebx, eax
0x180006629  test    eax, eax
0x18000662b  jns     loc_1800066E8
0x180006631  mov     eax, cs:dword_1800DE000
0x180006637  cmp     eax, 2
0x18000663a  jbe     loc_18000684B
0x180006640  mov     edx, 8
0x180006645  lea     rcx, dword_1800DE000
0x18000664c  call    _tlgKeywordOn
0x180006651  test    al, al
0x180006653  jz      loc_18000684B
0x180006659  mov     rax, [rsp+310h+lpFileName]
0x18000665e  mov     [rsp+310h+var_2C8], rax
0x180006663  lea     rax, [rsp+310h+var_2D0]
0x180006668  mov     [rsp+310h+var_2E8], rax
0x18000666d  lea     rax, [rsp+310h+var_2C8]
0x180006672  lea     rdx, unk_1800CCC30
0x180006679  jmp     loc_18000683C
0x18000667e  test    r15d, r15d
0x180006681  jz      short loc_1800066E3
0x180006683  call    ?PreparePathForDeletion@_werDetail@@YAJPEB_W@Z; _werDetail::PreparePathForDeletion(wchar_t const *)
0x180006688  mov     r8d, eax
0x18000668b  test    eax, eax
0x18000668d  jns     short loc_1800066DE
0x18000668f  mov     ecx, cs:dword_1800DE000
0x180006695  cmp     ecx, 3
0x180006698  jbe     short loc_1800066DE
0x18000669a  mov     edx, 8
0x18000669f  lea     rcx, dword_1800DE000
0x1800066a6  call    _tlgKeywordOn
0x1800066ab  test    al, al
0x1800066ad  jz      short loc_1800066DE
0x1800066af  mov     [rsp+310h+var_2D0], r8d
0x1800066b4  mov     rax, [rsp+310h+lpFileName]
0x1800066b9  mov     [rsp+310h+var_2C8], rax
0x1800066be  lea     rax, [rsp+310h+var_2D0]
0x1800066c3  mov     [rsp+310h+var_2E8], rax
0x1800066c8  lea     rax, [rsp+310h+var_2C8]
0x1800066cd  mov     qword ptr [rsp+310h+bIgnoreCase], rax
0x1800066d2  lea     rdx, unk_1800CCC78
0x1800066d9  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1800066de  mov     rcx, [rsp+310h+lpFileName]; wchar_t *
0x1800066e3  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x1800066e8  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x1800066ec  mov     rcx, [rsp+310h+hFindFile]; hFindFile
0x1800066f1  call    cs:__imp_FindNextFileW
0x1800066f8  nop     dword ptr [rax+rax+00h]
0x1800066fd  test    eax, eax
0x1800066ff  jnz     loc_180006526
0x180006705  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180006709  lea     rcx, [rsp+310h+hFindFile]
0x18000670e  call    ?reset@?$unique_any@Ufind_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::find_handle_traits>::reset(void *)
0x180006713  test    r15d, r15d
0x180006716  jz      short loc_180006771
0x180006718  mov     rcx, rsi; lpFileName
0x18000671b  call    ?PreparePathForDeletion@_werDetail@@YAJPEB_W@Z; _werDetail::PreparePathForDeletion(wchar_t const *)
0x180006720  mov     r8d, eax
0x180006723  test    eax, eax
0x180006725  jns     short loc_180006771
0x180006727  mov     ecx, cs:dword_1800DE000
0x18000672d  cmp     ecx, 3
0x180006730  jbe     short loc_180006771
0x180006732  mov     edx, 8
0x180006737  lea     rcx, dword_1800DE000
0x18000673e  call    _tlgKeywordOn
0x180006743  test    al, al
0x180006745  jz      short loc_180006771
0x180006747  mov     [rsp+310h+var_2D0], r8d
0x18000674c  mov     [rsp+310h+var_2C8], rsi
0x180006751  lea     rax, [rsp+310h+var_2D0]
0x180006756  mov     [rsp+310h+var_2E8], rax
0x18000675b  lea     rax, [rsp+310h+var_2C8]
0x180006760  mov     qword ptr [rsp+310h+bIgnoreCase], rax
0x180006765  lea     rdx, byte_1800CCCBF
0x18000676c  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180006771  mov     rcx, rsi; wchar_t *
0x180006774  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x180006779  mov     ebx, r13d
0x18000677c  jmp     loc_18000684B
0x180006781  mov     eax, cs:dword_1800DE000
0x180006787  cmp     eax, 2
0x18000678a  jbe     loc_18000684B
0x180006790  mov     edx, 8
0x180006795  lea     rcx, dword_1800DE000
0x18000679c  call    _tlgKeywordOn
0x1800067a1  test    al, al
0x1800067a3  jz      loc_18000684B
0x1800067a9  mov     [rsp+310h+var_2D0], ebx
0x1800067ad  lea     rax, [rbp+210h+FindFileData.cFileName]
0x1800067b1  mov     [rsp+310h+var_2C8], rax
0x1800067b6  mov     [rsp+310h+var_298], rsi
0x1800067bb  lea     rax, [rsp+310h+var_2D0]
0x1800067c0  mov     [rsp+310h+var_2E0], rax
0x1800067c5  lea     rax, [rsp+310h+var_2C8]
0x1800067ca  mov     [rsp+310h+var_2E8], rax
0x1800067cf  lea     rax, [rsp+310h+var_298]
0x1800067d4  mov     qword ptr [rsp+310h+bIgnoreCase], rax
0x1800067d9  lea     rdx, word_1800CCBDE
0x1800067e0  call    ??$Write@U?$_tlgWrapSz@_W@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1800067e5  jmp     short loc_18000684B
0x1800067e7  call    cs:__imp_GetLastError
0x1800067ee  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
