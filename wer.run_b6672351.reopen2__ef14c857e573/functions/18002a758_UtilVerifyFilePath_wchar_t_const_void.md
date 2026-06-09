# UtilVerifyFilePath(wchar_t const *,void *)

- ea: `0x18002a758`
- end: `0x18002ac52`
- name: `?UtilVerifyFilePath@@YAJPEB_WPEAX@Z`
- size: `1274`
- prototype: `int(const wchar_t *, void *)`
- caller_count: `9`
- callee_count: `19`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180008298`
- `0x180009684`
- `0x18000fc28`
- `0x18001e658`
- `0x18002a5f8`
- `0x180037cb8`
- `0x180040f04`
- `0x180051270`
- `0x1800678d4`

## callees

- `0x180002ae4`
- `0x180002c2c`
- `0x180002db8`
- `0x180003048`
- `0x18000d40c`
- `0x18000da00`
- `0x18000db80`
- `0x18001b044`
- `0x18001e0d0`
- `0x1800235c8`
- `0x18002a758`
- `0x18002e5a4`
- `0x180031cd0`
- `0x180031ff4`
- `0x18003b180`
- `0x18003de9c`
- `0x18004cab0`
- `0x180053300`
- `0x1800682e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002a819`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002a819`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002aafc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002aafc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a9cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a9cc`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18002a9ba`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18002aa52`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18002a9ba`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18002aa52`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x18002ab11`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x18002ab11`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilVerifyFilePath(WCHAR *a1, void *a2)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  signed int FinalPathByHandle; // ebx
  HANDLE CurrentProcess; // rax
  __int64 v9; // rcx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  char *v13; // rdx
  __int64 v14; // r8
  char v15; // bl
  __int64 v16; // rax
  int v17; // ecx
  int v18; // r8d
  __int64 v19; // r9
  DWORD LongPathNameW; // eax
  DWORD v21; // edi
  signed int LastError; // eax
  const wchar_t *v23; // rdx
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  LPWSTR v27; // rbx
  __int64 v28; // rdi
  const WCHAR *v29; // r10
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // rax
  int v35; // r8d
  __int64 v36; // r9
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  LPWSTR lpszLongPath; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpszShortPath; // [rsp+58h] [rbp-A8h] BYREF
  _WORD *v43; // [rsp+60h] [rbp-A0h]
  _WORD v44[8]; // [rsp+68h] [rbp-98h] BYREF
  _WORD *v45; // [rsp+78h] [rbp-88h] BYREF
  _WORD *v46; // [rsp+80h] [rbp-80h]
  _WORD v47[8]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v48[2]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v49[2]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v50[16]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v51[24]; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR szLongPath[264]; // [rsp+E0h] [rbp-20h] BYREF

  v45 = v47;
  v46 = v47;
  v47[0] = 0;
  lpszShortPath = v44;
  v43 = v44;
  v44[0] = 0;
  if ( (unsigned int)dword_1800DE000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
  {
    lpszLongPath = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v4,
      (unsigned int)&word_1800CCD4E,
      v5,
      v6,
      (__int64)&lpszLongPath);
  }
  FinalPathByHandle = _werDetail::UtilGetFinalPathByHandle(a2);
  if ( FinalPathByHandle == -2147024891 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !(unsigned int)UtilIsLowRightsProcess(CurrentProcess) )
    {
      if ( (unsigned int)dword_1800DE000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v9,
          &unk_1800CCD88);
      FinalPathByHandle = 0;
      goto LABEL_52;
    }
    goto LABEL_11;
  }
  if ( FinalPathByHandle < 0 )
  {
LABEL_11:
    if ( (unsigned int)dword_1800DE000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      goto LABEL_52;
    LODWORD(lpszLongPath) = FinalPathByHandle;
    v13 = byte_1800CCDB9;
    goto LABEL_14;
  }
  v14 = -1;
  do
    ++v14;
  while ( a1[v14] );
  if ( !v14 )
  {
    FinalPathByHandle = -2147024809;
    goto LABEL_52;
  }
  v15 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::ends_with(&v45);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &lpszShortPath,
                           a1) )
  {
    FinalPathByHandle = -2147024882;
    if ( (unsigned int)dword_1800DE000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      goto LABEL_52;
    LODWORD(lpszLongPath) = -2147024882;
    v13 = &byte_1800CCDE7;
LABEL_14:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v10,
      (_DWORD)v13,
      v11,
      v12,
      (__int64)&lpszLongPath);
    goto LABEL_52;
  }
  if ( v15 && (unsigned int)dword_1800DE000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
  {
    _tlgWrapBinary<wchar_t,2>(v49, lpszShortPath, (unsigned __int16)(v43 - lpszShortPath));
    v16 = _tlgWrapBinary<wchar_t,2>(v48, v45, (unsigned __int16)(v46 - v45));
    lpszLongPath = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(
      v17,
      (unsigned int)&dword_1800CCE1C,
      v18,
      v19,
      (__int64)&lpszLongPath,
      v16,
      v19);
  }
  LongPathNameW = GetLongPathNameW(lpszShortPath, szLongPath, 0x105u);
  v21 = LongPathNameW;
  if ( !LongPathNameW )
  {
    LastError = GetLastError();
    FinalPathByHandle = LastError;
    if ( LastError > 0 )
      FinalPathByHandle = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
    {
      LODWORD(lpszLongPath) = FinalPathByHandle;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v24,
        (unsigned int)byte_1800CCE7D,
        v25,
        v26,
        (__int64)&lpszLongPath);
    }
LABEL_40:
    if ( FinalPathByHandle < 0 )
      goto LABEL_52;
    goto LABEL_44;
  }
  if ( LongPathNameW > 0x105 )
  {
    utl::make_unique_for_overwrite<wchar_t [0],0>(&lpszLongPath, LongPathNameW);
    v27 = lpszLongPath;
    if ( lpszLongPath )
    {
      if ( v21 > GetLongPathNameW(lpszShortPath, lpszLongPath, v21) )
        FinalPathByHandle = (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                               &lpszShortPath,
                                               v27) == 0
                          ? 0x8007000E
                          : 0;
      else
        FinalPathByHandle = -2147418113;
    }
    else
    {
      FinalPathByHandle = -2147024882;
    }
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&lpszLongPath);
    goto LABEL_40;
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &lpszShortPath,
                           szLongPath) )
  {
    FinalPathByHandle = -2147024882;
    goto LABEL_52;
  }
  FinalPathByHandle = 0;
LABEL_44:
  v28 = (unsigned int)_werDetail::HasExtendedLengthPathPrefix((_werDetail *)lpszShortPath, v23) == 0 ? 4 : 0;
  v30 = v43 - v29;
  if ( v30 != v46 - v45 - v28 || CompareStringOrdinal(v29, v30, &v45[v28], v30, 1) != 2 )
  {
    if ( (unsigned int)TelGetWerTelemetryMode() == 3
      && (unsigned int)dword_1800DE000 > 2
      && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 0x200000000008LL) )
    {
      LODWORD(lpszLongPath) = v28;
      _tlgWrapBinary<wchar_t,2>(v50, v45, (unsigned __int16)(v46 - v45));
      v34 = _tlgWrapBinary<wchar_t,2>(v51, lpszShortPath, (unsigned __int16)(v43 - lpszShortPath));
      v48[0] = a1;
      v49[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(
        (unsigned int)&lpszLongPath,
        (unsigned int)&word_1800CCEB6,
        v35,
        v36,
        (__int64)v49,
        (__int64)v48,
        v34,
        v36,
        (__int64)&lpszLongPath);
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v32, v31, v33);
    FinalPathByHandle = -2147024735;
  }
LABEL_52:
  if ( (unsigned int)dword_1800DE000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
  {
    LODWORD(lpszLongPath) = FinalPathByHandle;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v37,
      (unsigned int)word_1800CCF2A,
      v38,
      v39,
      (__int64)&lpszLongPath);
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpszShortPath);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v45);
  return (unsigned int)FinalPathByHandle;
}

```

## disassembly

```asm
0x18002a758  mov     [rsp-8+arg_10], rbx
0x18002a75d  mov     [rsp-8+arg_18], rsi
0x18002a762  push    rbp
0x18002a763  push    rdi
0x18002a764  push    r12
0x18002a766  push    r14
0x18002a768  push    r15
0x18002a76a  lea     rbp, [rsp-200h]
0x18002a772  sub     rsp, 300h
0x18002a779  mov     rax, cs:__security_cookie
0x18002a780  xor     rax, rsp
0x18002a783  mov     [rbp+220h+var_30], rax
0x18002a78a  mov     rbx, rdx
0x18002a78d  mov     rsi, rcx
0x18002a790  lea     rax, [rbp+220h+var_298]
0x18002a794  mov     [rsp+320h+var_2A8], rax
0x18002a799  lea     rax, [rbp+220h+var_298]
0x18002a79d  mov     [rbp+220h+var_2A0], rax
0x18002a7a1  xor     r14d, r14d
0x18002a7a4  mov     [rbp+220h+var_298], r14w
0x18002a7a9  lea     rax, [rsp+320h+var_2B8]
0x18002a7ae  mov     [rsp+320h+lpszShortPath], rax
0x18002a7b3  lea     rax, [rsp+320h+var_2B8]
0x18002a7b8  mov     [rsp+320h+var_2C0], rax
0x18002a7bd  mov     [rsp+320h+var_2B8], r14w
0x18002a7c3  mov     eax, cs:dword_1800DE000
0x18002a7c9  lea     r12d, [r14+8]
0x18002a7cd  lea     r15, dword_1800DE000
0x18002a7d4  cmp     eax, 4
0x18002a7d7  jbe     short loc_18002A803
0x18002a7d9  mov     edx, r12d
0x18002a7dc  mov     rcx, r15
0x18002a7df  call    _tlgKeywordOn
0x18002a7e4  test    al, al
0x18002a7e6  jz      short loc_18002A803
0x18002a7e8  mov     [rsp+320h+lpszLongPath], rsi
0x18002a7ed  lea     rax, [rsp+320h+lpszLongPath]
0x18002a7f2  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x18002a7f7  lea     rdx, word_1800CCD4E
0x18002a7fe  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18002a803  lea     rdx, [rsp+320h+var_2A8]
0x18002a808  mov     rcx, rbx; hFile
0x18002a80b  call    ?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18002a810  mov     ebx, eax
0x18002a812  cmp     eax, 80070005h
0x18002a817  jnz     short loc_18002A85F
0x18002a819  call    cs:__imp_GetCurrentProcess
0x18002a820  nop     dword ptr [rax+rax+00h]
0x18002a825  mov     rcx, rax; ProcessHandle
0x18002a828  call    ?UtilIsLowRightsProcess@@YAJPEAX@Z; UtilIsLowRightsProcess(void *)
0x18002a82d  test    eax, eax
0x18002a82f  jnz     short loc_18002A863
0x18002a831  mov     eax, cs:dword_1800DE000
0x18002a837  cmp     eax, 4
0x18002a83a  jbe     short loc_18002A857
0x18002a83c  mov     rdx, r12
0x18002a83f  mov     rcx, r15
0x18002a842  call    _tlgKeywordOn
0x18002a847  test    al, al
0x18002a849  jz      short loc_18002A857
0x18002a84b  lea     rdx, unk_1800CCD88
0x18002a852  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18002a857  mov     ebx, r14d
0x18002a85a  jmp     loc_18002ABDA
0x18002a85f  test    ebx, ebx
0x18002a861  jns     short loc_18002A8A4
0x18002a863  mov     eax, cs:dword_1800DE000
0x18002a869  cmp     eax, 2
0x18002a86c  jbe     loc_18002ABDA
0x18002a872  mov     rdx, r12
0x18002a875  mov     rcx, r15
0x18002a878  call    _tlgKeywordOn
0x18002a87d  test    al, al
0x18002a87f  jz      loc_18002ABDA
0x18002a885  mov     dword ptr [rsp+320h+lpszLongPath], ebx
0x18002a889  lea     rdx, byte_1800CCDB9
0x18002a890  lea     rax, [rsp+320h+lpszLongPath]
0x18002a895  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x18002a89a  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002a89f  jmp     loc_18002ABDA
0x18002a8a4  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002a8a8  inc     r8
0x18002a8ab  cmp     [rsi+r8*2], r14w
0x18002a8b0  jnz     short loc_18002A8A8
0x18002a8b2  cmp     r8, 1
0x18002a8b6  jnb     short loc_18002A8C2
0x18002a8b8  mov     ebx, 80070057h
0x18002a8bd  jmp     loc_18002ABDA
0x18002a8c2  lea     rcx, [rsp+320h+var_2A8]
0x18002a8c7  call    ?ends_with@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::ends_with(wchar_t)
0x18002a8cc  mov     bl, al
0x18002a8ce  cmp     word ptr [rsi+r8*2-2], 5Ch ; '\'
0x18002a8d5  jnz     short loc_18002A8DE
0x18002a8d7  test    al, al
0x18002a8d9  jnz     short loc_18002A8DE
0x18002a8db  dec     r8
0x18002a8de  mov     rdx, rsi
0x18002a8e1  lea     rcx, [rsp+320h+lpszShortPath]
0x18002a8e6  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18002a8eb  test    al, al
0x18002a8ed  jnz     short loc_18002A92A
0x18002a8ef  mov     ebx, 8007000Eh
0x18002a8f4  mov     eax, cs:dword_1800DE000
0x18002a8fa  cmp     eax, 2
0x18002a8fd  jbe     loc_18002ABDA
0x18002a903  mov     rdx, r12
0x18002a906  mov     rcx, r15
0x18002a909  call    _tlgKeywordOn
0x18002a90e  test    al, al
0x18002a910  jz      loc_18002ABDA
0x18002a916  mov     dword ptr [rsp+320h+lpszLongPath], 8007000Eh
0x18002a91e  lea     rdx, byte_1800CCDE7
0x18002a925  jmp     loc_18002A890
0x18002a92a  test    bl, bl
0x18002a92c  jz      short loc_18002A9A9
0x18002a92e  mov     eax, cs:dword_1800DE000
0x18002a934  cmp     eax, 4
0x18002a937  jbe     short loc_18002A9A9
0x18002a939  mov     rdx, r12
0x18002a93c  mov     rcx, r15
0x18002a93f  call    _tlgKeywordOn
0x18002a944  test    al, al
0x18002a946  jz      short loc_18002A9A9
0x18002a948  mov     rax, [rsp+320h+var_2C0]
0x18002a94d  mov     rdx, [rsp+320h+lpszShortPath]
0x18002a952  sub     rax, rdx
0x18002a955  sar     rax, 1
0x18002a958  movzx   r8d, ax
0x18002a95c  lea     rcx, [rbp+220h+var_278]
0x18002a960  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x18002a965  mov     r9, rax
0x18002a968  mov     rcx, [rbp+220h+var_2A0]
0x18002a96c  mov     rdx, [rsp+320h+var_2A8]
0x18002a971  sub     rcx, rdx
0x18002a974  sar     rcx, 1
0x18002a977  movzx   r8d, cx
0x18002a97b  lea     rcx, [rbp+220h+var_288]
0x18002a97f  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x18002a984  mov     [rsp+320h+lpszLongPath], rsi
0x18002a989  mov     [rsp+320h+var_2F0], r9
0x18002a98e  mov     [rsp+320h+var_2F8], rax
0x18002a993  lea     rax, [rsp+320h+lpszLongPath]
0x18002a998  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x18002a99d  lea     rdx, dword_1800CCE1C
0x18002a9a4  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperArray@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperArray@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &)
0x18002a9a9  mov     ebx, 105h
0x18002a9ae  mov     r8d, ebx; cchBuffer
0x18002a9b1  lea     rdx, [rbp+220h+szLongPath]; lpszLongPath
0x18002a9b5  mov     rcx, [rsp+320h+lpszShortPath]; lpszShortPath
0x18002a9ba  call    cs:__imp_GetLongPathNameW
0x18002a9c1  nop     dword ptr [rax+rax+00h]
0x18002a9c6  mov     edi, eax
0x18002a9c8  test    eax, eax
0x18002a9ca  jnz     short loc_18002AA25
0x18002a9cc  call    cs:__imp_GetLastError
0x18002a9d3  nop     dword ptr [rax+rax+00h]
0x18002a9d8  mov     ebx, eax
0x18002a9da  test    eax, eax
0x18002a9dc  jle     short loc_18002A9E7
0x18002a9de  movzx   ebx, ax
0x18002a9e1  or      ebx, 80070000h
0x18002a9e7  mov     eax, cs:dword_1800DE000
0x18002a9ed  cmp     eax, 2
0x18002a9f0  jbe     loc_18002AA8D
0x18002a9f6  mov     rdx, r12
0x18002a9f9  mov     rcx, r15
0x18002a9fc  call    _tlgKeywordOn
0x18002aa01  test    al, al
0x18002aa03  jz      loc_18002AA8D
0x18002aa09  mov     dword ptr [rsp+320h+lpszLongPath], ebx
0x18002aa0d  lea     rax, [rsp+320h+lpszLongPath]
0x18002aa12  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x18002aa17  lea     rdx, byte_1800CCE7D
0x18002aa1e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002aa23  jmp     short loc_18002AA8D
0x18002aa25  cmp     edi, ebx
0x18002aa27  jbe     short loc_18002AA97
0x18002aa29  mov     rdx, rdi
0x18002aa2c  lea     rcx, [rsp+320h+lpszLongPath]
0x18002aa31  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x18002aa36  mov     rbx, [rsp+320h+lpszLongPath]
0x18002aa3b  test    rbx, rbx
0x18002aa3e  jnz     short loc_18002AA47
0x18002aa40  mov     ebx, 8007000Eh
0x18002aa45  jmp     short loc_18002AA83
0x18002aa47  mov     r8d, edi; cchBuffer
0x18002aa4a  mov     rdx, rbx; lpszLongPath
0x18002aa4d  mov     rcx, [rsp+320h+lpszShortPath]; lpszShortPath
0x18002aa52  call    cs:__imp_GetLongPathNameW
0x18002aa59  nop     dword ptr [rax+rax+00h]
0x18002aa5e  cmp     edi, eax
0x18002aa60  ja      short loc_18002AA69
0x18002aa62  mov     ebx, 8000FFFFh
0x18002aa67  jmp     short loc_18002AA83
0x18002aa69  mov     rdx, rbx
0x18002aa6c  lea     rcx, [rsp+320h+lpszShortPath]
0x18002aa71  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18002aa76  neg     al
0x18002aa78  sbb     ecx, ecx
0x18002aa7a  not     ecx
0x18002aa7c  mov     ebx, 8007000Eh
0x18002aa81  and     ebx, ecx
0x18002aa83  lea     rcx, [rsp+320h+lpszLongPath]; void *
0x18002aa88  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18002aa8d  test    ebx, ebx
0x18002aa8f  js      loc_18002ABDA
0x18002aa95  jmp     short loc_18002AAB0
0x18002aa97  lea     rdx, [rbp+220h+szLongPath]
0x18002aa9b  lea     rcx, [rsp+320h+lpszShortPath]
0x18002aaa0  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18002aaa5  test    al, al
0x18002aaa7  jz      loc_18002ABD5
0x18002aaad  mov     ebx, r14d
0x18002aab0  mov     r10, [rsp+320h+lpszShortPath]
0x18002aab5  mov     rcx, r10; this
0x18002aab8  call    ?HasExtendedLengthPathPrefix@_werDetail@@YAHPEB_W@Z; _werDetail::HasExtendedLengthPathPrefix(wchar_t const *)
0x18002aabd  neg     eax
0x18002aabf  sbb     ecx, ecx
0x18002aac1  not     ecx
0x18002aac3  and     ecx, 4
0x18002aac6  mov     edi, ecx
0x18002aac8  mov     rdx, [rsp+320h+var_2C0]
0x18002aacd  sub     rdx, r10
0x18002aad0  sar     rdx, 1; cchCount1
0x18002aad3  mov     rax, [rbp+220h+var_2A0]
0x18002aad7  mov     rcx, [rsp+320h+var_2A8]
0x18002aadc  sub     rax, rcx
0x18002aadf  sar     rax, 1
0x18002aae2  sub     rax, rdi
0x18002aae5  cmp     rdx, rax
0x18002aae8  jnz     short loc_18002AB11
0x18002aaea  lea     r8, [rcx+rdi*2]; lpString2
0x18002aaee  mov     [rsp+320h+bIgnoreCase], 1; bIgnoreCase
0x18002aaf6  mov     r9d, edx; cchCount2
0x18002aaf9  mov     rcx, r10; lpString1
0x18002aafc  call    cs:__imp_CompareStringOrdinal
0x18002ab03  nop     dword ptr [rax+rax+00h]
0x18002ab08  cmp     eax, 2
0x18002ab0b  jz      loc_18002ABDA
0x18002ab11  call    cs:__imp_TelGetWerTelemetryMode
0x18002ab18  nop     dword ptr [rax+rax+00h]
0x18002ab1d  cmp     eax, 3
0x18002ab20  jnz     loc_18002ABC9
0x18002ab26  mov     eax, cs:dword_1800DE000
0x18002ab2c  cmp     eax, 2
0x18002ab2f  jbe     loc_18002ABC9
0x18002ab35  mov     rdx, 200000000008h
0x18002ab3f  mov     rcx, r15
0x18002ab42  call    _tlgKeywordOn
0x18002ab47  test    al, al
0x18002ab49  jz      short loc_18002ABC9
0x18002ab4b  mov     dword ptr [rsp+320h+lpszLongPath], edi
0x18002ab4f  mov     rax, [rbp+220h+var_2A0]
0x18002ab53  mov     rdx, [rsp+320h+var_2A8]
0x18002ab58  sub     rax, rdx
0x18002ab5b  sar     rax, 1
0x18002ab5e  movzx   r8d, ax
0x18002ab62  lea     rcx, [rbp+220h+var_268]
0x18002ab66  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x18002ab6b  mov     r9, rax
0x18002ab6e  mov     rcx, [rsp+320h+var_2C0]
0x18002ab73  mov     rdx, [rsp+320h+lpszShortPath]
0x18002ab78  sub     rcx, rdx
0x18002ab7b  sar     rcx, 1
0x18002ab7e  movzx   r8d, cx
0x18002ab82  lea     rcx, [rbp+220h+var_258]
0x18002ab86  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x18002ab8b  mov     [rbp+220h+var_288], rsi
0x18002ab8f  mov     [rbp+220h+var_278], 1000000h
0x18002ab97  lea     rcx, [rsp+320h+lpszLongPath]
0x18002ab9c  mov     [rsp+320h+var_2E0], rcx
0x18002aba1  mov     [rsp+320h+var_2E8], r9
0x18002aba6  mov     [rsp+320h+var_2F0], rax
0x18002abab  lea     rax, [rbp+220h+var_288]
0x18002abaf  mov     [rsp+320h+var_2F8], rax
0x18002abb4  lea     rax, [rbp+220h+var_278]
0x18002abb8  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x18002abbd  lea     rdx, word_1800CCEB6
0x18002abc4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperArray@$00@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperArray@$00@@5AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &)
0x18002abc9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002abce  mov     ebx, 800700A1h
0x18002abd3  jmp     short loc_18002ABDA
0x18002abd5  mov     ebx, 8007000Eh
0x18002abda  mov     eax, cs:dword_1800DE000
0x18002abe0  cmp     eax, 4
0x18002abe3  jbe     short loc_18002AC0F
0x18002abe5  mov     rdx, r12
0x18002abe8  mov     rcx, r15
0x18002abeb  call    _tlgKeywordOn
0x18002abf0  test    al, al
0x18002abf2  jz      short loc_18002AC0F
0x18002abf4  mov     dword ptr [rsp+320h+lpszLongPath], ebx
0x18002abf8  lea     rax, [rsp+320h+lpszLongPath]
0x18002abfd  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x18002ac02  lea     rdx, word_1800CCF2A
0x18002ac09  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002ac0e  nop
0x18002ac0f  lea     rcx, [rsp+320h+lpszShortPath]; void *
0x18002ac14  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002ac19  nop
  ... truncated ...
```
