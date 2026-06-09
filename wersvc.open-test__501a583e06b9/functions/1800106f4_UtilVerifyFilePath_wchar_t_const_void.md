# UtilVerifyFilePath(wchar_t const *,void *)

- ea: `0x1800106f4`
- end: `0x180010efe`
- name: `?UtilVerifyFilePath@@YAJPEB_WPEAX@Z`
- size: `2058`
- prototype: `__int64 __fastcall(wchar_t *, void *, int, int)`
- caller_count: `6`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000e0a0`
- `0x1800101dc`
- `0x180012600`
- `0x180012e94`
- `0x180019728`
- `0x18001b3f8`

## callees

- `0x18000113c`
- `0x1800011dc`
- `0x1800029d0`
- `0x1800029f4`
- `0x180007c48`
- `0x180007cf8`
- `0x18000e8a8`
- `0x18000fd08`
- `0x1800106f4`
- `0x180011648`
- `0x180013df4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800107c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800107c4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800107e5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800107e5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010cba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010cba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800107ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800107ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b0e`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180010afe`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180010bcc`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180010afe`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180010bcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001082b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001082b`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x180010cc8`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x180010cc8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UtilVerifyFilePath(wchar_t *a1, void *a2, int a3, int a4)
{
  int *v5; // r14
  signed int FinalPathByHandle; // edi
  HANDLE CurrentProcess; // rbx
  void **v8; // rax
  signed int LastError; // eax
  signed int IsLowRightsToken; // ebx
  int *v11; // rdx
  __int64 v12; // r15
  __int64 v13; // r8
  char v14; // di
  unsigned int v15; // ebx
  __int64 v16; // rax
  unsigned __int16 v17; // ax
  __int64 v18; // rcx
  unsigned __int16 v19; // cx
  int *v20; // rcx
  __int64 v21; // rax
  unsigned int v22; // eax
  DWORD LongPathNameW; // eax
  DWORD v24; // edi
  signed int v25; // eax
  const struct std::nothrow_t *v26; // rdx
  _WORD *v27; // rsi
  __int64 v28; // r8
  __int64 v29; // r8
  int v30; // eax
  __int64 v31; // rsi
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rax
  unsigned __int16 v38; // ax
  __int64 v39; // rcx
  unsigned __int16 v40; // cx
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v43; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpszShortPath; // [rsp+40h] [rbp-C0h] BYREF
  char *v45; // [rsp+48h] [rbp-B8h]
  __int64 v46; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v47; // [rsp+58h] [rbp-A8h]
  void *v48; // [rsp+60h] [rbp-A0h]
  char *v49; // [rsp+68h] [rbp-98h]
  _WORD v50[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v51; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v52; // [rsp+88h] [rbp-78h] BYREF
  void *v53; // [rsp+90h] [rbp-70h]
  unsigned __int16 v54; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR v55; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v56; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE *p_hObject; // [rsp+C0h] [rbp-40h]
  __int64 v58; // [rsp+C8h] [rbp-38h]
  WCHAR szLongPath[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v60; // [rsp+F0h] [rbp-10h]
  __int64 v61; // [rsp+F8h] [rbp-8h]
  int *v62; // [rsp+100h] [rbp+0h]
  __int64 v63; // [rsp+108h] [rbp+8h]
  _WORD *v64; // [rsp+110h] [rbp+10h]
  __int64 v65; // [rsp+118h] [rbp+18h]
  LPCWSTR v66; // [rsp+120h] [rbp+20h]
  __int64 v67; // [rsp+128h] [rbp+28h]
  LPCWSTR v68; // [rsp+130h] [rbp+30h]
  __int64 v69; // [rsp+138h] [rbp+38h]
  void *v70; // [rsp+140h] [rbp+40h]
  int v71; // [rsp+148h] [rbp+48h]
  int v72; // [rsp+14Ch] [rbp+4Ch]
  HANDLE *v73; // [rsp+150h] [rbp+50h]
  __int64 v74; // [rsp+158h] [rbp+58h]

  v5 = (int *)a1;
  v48 = v50;
  v49 = (char *)v50;
  v50[0] = 0;
  lpszShortPath = (LPCWSTR)&v46;
  v45 = (char *)&v46;
  LOWORD(v46) = 0;
  if ( (unsigned int)dword_180047000 > 4 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
  {
    hObject = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (_DWORD)a1,
      (unsigned int)&unk_18003EC78,
      a3,
      a4,
      (__int64)&hObject);
  }
  FinalPathByHandle = _werDetail::UtilGetFinalPathByHandle(a2);
  if ( FinalPathByHandle == -2147024891 )
  {
    CurrentProcess = GetCurrentProcess();
    hObject = 0;
    v8 = (void **)tlx::replace<tlx::file_handle_traits>(&hObject);
    if ( OpenProcessToken(CurrentProcess, 8u, v8) )
    {
      IsLowRightsToken = UtilIsLowRightsToken(hObject);
    }
    else
    {
      LastError = GetLastError();
      IsLowRightsToken = LastError;
      if ( LastError > 0 )
        IsLowRightsToken = (unsigned __int16)LastError | 0x80070000;
      if ( IsLowRightsToken >= 0 )
        IsLowRightsToken = -2147467259;
    }
    if ( (unsigned __int64)hObject + 1 > 1 )
      CloseHandle(hObject);
    if ( !IsLowRightsToken )
    {
      if ( (unsigned int)dword_180047000 > 4 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
        tlgWriteTransfer_EventWriteTransfer(
          &dword_180047000,
          &byte_18003EC47,
          0,
          0,
          2,
          &v55,
          hObject,
          v43,
          lpszShortPath,
          v45,
          v46,
          v47);
      FinalPathByHandle = 0;
      goto LABEL_104;
    }
    goto LABEL_22;
  }
  if ( FinalPathByHandle < 0 )
  {
LABEL_22:
    if ( (unsigned int)dword_180047000 <= 2 || (qword_180047010 & 8) == 0 || (qword_180047018 & 8) != qword_180047018 )
      goto LABEL_104;
    LODWORD(hObject) = FinalPathByHandle;
    v11 = (int *)byte_18003EC19;
    goto LABEL_26;
  }
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)v5 + v13) );
  if ( !v13 )
  {
    FinalPathByHandle = -2147024809;
    goto LABEL_104;
  }
  if ( v48 == v49 || (v14 = 1, *((_WORD *)v49 - 1) != 92) )
    v14 = 0;
  v15 = 2;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &lpszShortPath,
                           v5) )
  {
    FinalPathByHandle = -2147024882;
    if ( (unsigned int)dword_180047000 <= 2 || (qword_180047010 & 8) == 0 || (qword_180047018 & 8) != qword_180047018 )
      goto LABEL_104;
    LODWORD(hObject) = -2147024882;
    v11 = &dword_18003EBE4;
LABEL_26:
    p_hObject = &hObject;
    v58 = 4;
    tlgWriteTransfer_EventWriteTransfer(
      &dword_180047000,
      v11,
      0,
      0,
      3,
      &v55,
      hObject,
      v43,
      lpszShortPath,
      v45,
      v46,
      v47);
    goto LABEL_104;
  }
  if ( v14
    && (unsigned int)dword_180047000 > 4
    && (qword_180047010 & 8) != 0
    && (qword_180047018 & 8) == qword_180047018 )
  {
    v16 = (v45 - (char *)lpszShortPath) >> 1;
    if ( (unsigned __int16)v16 > 0x7FFFu )
      v17 = -2;
    else
      v17 = 2 * v16;
    v51 = (__int64)lpszShortPath;
    v52 = v17;
    v18 = (v49 - (_BYTE *)v48) >> 1;
    if ( (unsigned __int16)v18 > 0x7FFFu )
      v19 = -2;
    else
      v19 = 2 * v18;
    hObject = v48;
    LOWORD(v43) = v19;
    v66 = &v52;
    v67 = 2;
    v68 = lpszShortPath;
    v69 = v17;
    v62 = (int *)&v43;
    v63 = 2;
    v64 = v48;
    v65 = v19;
    if ( v5 )
    {
      v20 = v5;
      v21 = -1;
      do
        ++v21;
      while ( *((_WORD *)v5 + v21) );
      v22 = 2 * v21 + 2;
    }
    else
    {
      v20 = &dword_180039414;
      v22 = 2;
    }
    v60 = (__int64 *)v20;
    v61 = v22;
    tlgWriteTransfer_EventWriteTransfer(
      &dword_180047000,
      byte_18003EB83,
      0,
      0,
      7,
      szLongPath,
      hObject,
      v43,
      lpszShortPath,
      v45,
      v46,
      v47);
  }
  LongPathNameW = GetLongPathNameW(lpszShortPath, szLongPath, 0x105u);
  v24 = LongPathNameW;
  if ( !LongPathNameW )
  {
    v25 = GetLastError();
    FinalPathByHandle = v25;
    if ( v25 > 0 )
      FinalPathByHandle = (unsigned __int16)v25 | 0x80070000;
    if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
    {
      LODWORD(hObject) = FinalPathByHandle;
      p_hObject = &hObject;
      v58 = 4;
      tlgWriteTransfer_EventWriteTransfer(
        &dword_180047000,
        word_18003EB4A,
        0,
        0,
        3,
        &v55,
        hObject,
        v43,
        lpszShortPath,
        v45,
        v46,
        v47);
    }
    goto LABEL_73;
  }
  if ( LongPathNameW > 0x105 )
  {
    utl::make_unique_for_overwrite<wchar_t [0],0>(&hObject, LongPathNameW);
    v27 = hObject;
    if ( hObject )
    {
      if ( v24 > GetLongPathNameW(lpszShortPath, (LPWSTR)hObject, v24) )
      {
        if ( v27 )
        {
          v28 = -1;
          do
            ++v28;
          while ( v27[v28] );
        }
        v26 = (const struct std::nothrow_t *)(unsigned int)-((unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                                                                &lpszShortPath,
                                                                                v27) == 0);
        FinalPathByHandle = (unsigned int)v26 & 0x8007000E;
      }
      else
      {
        FinalPathByHandle = -2147418113;
      }
    }
    else
    {
      FinalPathByHandle = -2147024882;
    }
    if ( v27 )
      operator delete(v27, v26);
LABEL_73:
    if ( FinalPathByHandle < 0 )
      goto LABEL_104;
    goto LABEL_79;
  }
  v29 = -1;
  do
    ++v29;
  while ( szLongPath[v29] );
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &lpszShortPath,
                           szLongPath) )
  {
    FinalPathByHandle = -2147024882;
    goto LABEL_104;
  }
  FinalPathByHandle = 0;
LABEL_79:
  if ( !lpszShortPath
    || *lpszShortPath != 92
    || lpszShortPath[1] != 92
    || lpszShortPath[2] != 63
    || (v30 = 0, lpszShortPath[3] != 92) )
  {
    v30 = 1;
  }
  v31 = (unsigned int)(4 * v30);
  v32 = (v45 - (char *)lpszShortPath) >> 1;
  if ( v32 != ((v49 - (_BYTE *)v48) >> 1) - v31
    || CompareStringOrdinal(lpszShortPath, v32, (LPCWCH)v48 + v31, v32, 1) != 2 )
  {
    if ( (unsigned int)TelGetWerTelemetryMode() == 3 && (unsigned int)dword_180047000 > 2 )
    {
      v34 = qword_180047018;
      v33 = 0x200000000008LL;
      if ( (qword_180047010 & 0x200000000008LL) != 0 && (qword_180047018 & 0x200000000008LL) == qword_180047018 )
      {
        LODWORD(hObject) = v31;
        v37 = (v49 - (_BYTE *)v48) >> 1;
        if ( (unsigned __int16)v37 > 0x7FFFu )
          v38 = -2;
        else
          v38 = 2 * v37;
        v53 = v48;
        v54 = v38;
        v39 = (v45 - (char *)lpszShortPath) >> 1;
        if ( (unsigned __int16)v39 > 0x7FFFu )
          v40 = -2;
        else
          v40 = 2 * v39;
        v55 = lpszShortPath;
        v56 = v40;
        v51 = 0x1000000;
        v73 = &hObject;
        v74 = 4;
        v68 = &v54;
        v69 = 2;
        v70 = v48;
        v71 = v38;
        v72 = 0;
        v64 = &v56;
        v65 = 2;
        v66 = lpszShortPath;
        v67 = v40;
        if ( v5 )
        {
          do
            ++v12;
          while ( *((_WORD *)v5 + v12) );
          v15 = 2 * v12 + 2;
        }
        else
        {
          v5 = &dword_180039414;
        }
        v62 = v5;
        v63 = v15;
        v60 = &v51;
        v61 = 8;
        tlgWriteTransfer_EventWriteTransfer(
          &dword_180047000,
          &word_18003EAD6,
          0,
          0,
          9,
          szLongPath,
          hObject,
          v43,
          lpszShortPath,
          v45,
          v46,
          v47);
      }
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v34, v33, v35, v36);
    FinalPathByHandle = -2147024735;
  }
LABEL_104:
  if ( (unsigned int)dword_180047000 > 4 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
  {
    LODWORD(hObject) = FinalPathByHandle;
    p_hObject = &hObject;
    v58 = 4;
    tlgWriteTransfer_EventWriteTransfer(
      &dword_180047000,
      byte_18003EAA9,
      0,
      0,
      3,
      &v55,
      hObject,
      v43,
      lpszShortPath,
      v45,
      v46,
      v47);
  }
  if ( lpszShortPath != (LPCWSTR)&v46 )
    operator delete((void *)lpszShortPath, (const struct std::nothrow_t *)&std::nothrow);
  if ( v48 != v50 )
    operator delete(v48, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)FinalPathByHandle;
}

```

## disassembly

```asm
0x1800106f4  mov     [rsp-8+arg_10], rbx
0x1800106f9  push    rbp
0x1800106fa  push    rsi
0x1800106fb  push    rdi
0x1800106fc  push    r12
0x1800106fe  push    r13
0x180010700  push    r14
0x180010702  push    r15
0x180010704  lea     rbp, [rsp-1F0h]
0x18001070c  sub     rsp, 2F0h
0x180010713  mov     rax, cs:__security_cookie
0x18001071a  xor     rax, rsp
0x18001071d  mov     [rbp+220h+var_40], rax
0x180010724  mov     rbx, rdx
0x180010727  mov     r14, rcx
0x18001072a  lea     rax, [rsp+320h+var_2B0]
0x18001072f  mov     [rsp+320h+var_2C0], rax
0x180010734  lea     rax, [rsp+320h+var_2B0]
0x180010739  mov     [rsp+320h+var_2B8], rax
0x18001073e  xor     r12d, r12d
0x180010741  mov     [rsp+320h+var_2B0], r12w
0x180010747  lea     rax, [rsp+320h+var_2D0]
0x18001074c  mov     [rsp+320h+lpszShortPath], rax
0x180010751  lea     rax, [rsp+320h+var_2D0]
0x180010756  mov     [rsp+320h+var_2D8], rax
0x18001075b  mov     word ptr [rsp+320h+var_2D0], r12w
0x180010761  mov     eax, cs:dword_180047000
0x180010767  lea     r13d, [r12+8]
0x18001076c  cmp     eax, 4
0x18001076f  jbe     short loc_1800107AA
0x180010771  mov     rdx, cs:qword_180047018
0x180010778  mov     rax, cs:qword_180047010
0x18001077f  test    r13b, al
0x180010782  jz      short loc_1800107AA
0x180010784  mov     rax, rdx
0x180010787  and     rax, r13
0x18001078a  cmp     rax, rdx
0x18001078d  jnz     short loc_1800107AA
0x18001078f  mov     [rsp+320h+hObject], rcx
0x180010794  lea     rax, [rsp+320h+hObject]
0x180010799  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x18001079e  lea     rdx, unk_18003EC78
0x1800107a5  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1800107aa  lea     rdx, [rsp+320h+var_2C0]
0x1800107af  mov     rcx, rbx; hFile
0x1800107b2  call    ?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800107b7  mov     edi, eax
0x1800107b9  cmp     eax, 80070005h
0x1800107be  jnz     loc_180010890
0x1800107c4  call    cs:__imp_GetCurrentProcess
0x1800107ca  mov     rbx, rax
0x1800107cd  mov     [rsp+320h+hObject], r12
0x1800107d2  lea     rcx, [rsp+320h+hObject]
0x1800107d7  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800107dc  mov     r8, rax; TokenHandle
0x1800107df  mov     edx, r13d; DesiredAccess
0x1800107e2  mov     rcx, rbx; ProcessHandle
0x1800107e5  call    cs:__imp_OpenProcessToken
0x1800107eb  test    eax, eax
0x1800107ed  jnz     short loc_180010810
0x1800107ef  call    cs:__imp_GetLastError
0x1800107f5  mov     ebx, eax
0x1800107f7  test    eax, eax
0x1800107f9  jle     short loc_180010804
0x1800107fb  movzx   ebx, ax
0x1800107fe  or      ebx, 80070000h
0x180010804  mov     eax, 80004005h
0x180010809  test    ebx, ebx
0x18001080b  cmovns  ebx, eax
0x18001080e  jmp     short loc_18001081C
0x180010810  mov     rcx, [rsp+320h+hObject]; TokenHandle
0x180010815  call    ?UtilIsLowRightsToken@@YAJPEAX@Z; UtilIsLowRightsToken(void *)
0x18001081a  mov     ebx, eax
0x18001081c  mov     rcx, [rsp+320h+hObject]; hObject
0x180010821  lea     rdx, [rcx+1]
0x180010825  cmp     rdx, 1
0x180010829  jbe     short loc_180010831
0x18001082b  call    cs:__imp_CloseHandle
0x180010831  test    ebx, ebx
0x180010833  jnz     short loc_180010894
0x180010835  mov     eax, cs:dword_180047000
0x18001083b  cmp     eax, 4
0x18001083e  jbe     short loc_180010888
0x180010840  mov     rcx, cs:qword_180047018
0x180010847  mov     rax, cs:qword_180047010
0x18001084e  test    r13b, al
0x180010851  jz      short loc_180010888
0x180010853  mov     rax, rcx
0x180010856  and     rax, r13
0x180010859  cmp     rax, rcx
0x18001085c  jnz     short loc_180010888
0x18001085e  lea     rax, [rbp+220h+var_280]
0x180010862  mov     [rsp+320h+var_2F8], rax
0x180010867  mov     [rsp+320h+bIgnoreCase], 2
0x18001086f  xor     r9d, r9d
0x180010872  xor     r8d, r8d
0x180010875  lea     rdx, byte_18003EC47
0x18001087c  lea     rcx, dword_180047000
0x180010883  call    _tlgWriteTransfer_EventWriteTransfer
0x180010888  mov     edi, r12d
0x18001088b  jmp     loc_180010E32
0x180010890  test    edi, edi
0x180010892  jns     short loc_180010911
0x180010894  mov     eax, cs:dword_180047000
0x18001089a  mov     ebx, 2
0x18001089f  cmp     eax, ebx
0x1800108a1  jbe     loc_180010E32
0x1800108a7  mov     rcx, cs:qword_180047018
0x1800108ae  mov     rax, cs:qword_180047010
0x1800108b5  test    r13b, al
0x1800108b8  jz      loc_180010E32
0x1800108be  mov     rax, rcx
0x1800108c1  and     rax, r13
0x1800108c4  cmp     rax, rcx
0x1800108c7  jnz     loc_180010E32
0x1800108cd  mov     dword ptr [rsp+320h+hObject], edi
0x1800108d1  lea     rdx, byte_18003EC19
0x1800108d8  lea     rax, [rsp+320h+hObject]
0x1800108dd  mov     [rbp+220h+var_260], rax
0x1800108e1  lea     rax, [rbp+220h+var_280]
0x1800108e5  xor     r9d, r9d
0x1800108e8  mov     [rsp+320h+var_2F8], rax
0x1800108ed  xor     r8d, r8d
0x1800108f0  mov     [rsp+320h+bIgnoreCase], 3
0x1800108f8  mov     [rbp+220h+var_258], 4
0x180010900  lea     rcx, dword_180047000
0x180010907  call    _tlgWriteTransfer_EventWriteTransfer
0x18001090c  jmp     loc_180010E32
0x180010911  or      r15, 0FFFFFFFFFFFFFFFFh
0x180010915  mov     r8, r15
0x180010918  inc     r8
0x18001091b  cmp     [r14+r8*2], r12w
0x180010920  jnz     short loc_180010918
0x180010922  cmp     r8, 1
0x180010926  jnb     short loc_180010932
0x180010928  mov     edi, 80070057h
0x18001092d  jmp     loc_180010E32
0x180010932  mov     ecx, 5Ch ; '\'
0x180010937  mov     rax, [rsp+320h+var_2B8]
0x18001093c  cmp     [rsp+320h+var_2C0], rax
0x180010941  jz      short loc_18001094C
0x180010943  cmp     cx, [rax-2]
0x180010947  mov     dil, 1
0x18001094a  jz      short loc_18001094F
0x18001094c  mov     dil, r12b
0x18001094f  cmp     [r14+r8*2-2], cx
0x180010955  jnz     short loc_18001095F
0x180010957  test    dil, dil
0x18001095a  jnz     short loc_18001095F
0x18001095c  dec     r8
0x18001095f  mov     rdx, r14
0x180010962  lea     rcx, [rsp+320h+lpszShortPath]
0x180010967  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18001096c  mov     ebx, 2
0x180010971  test    al, al
0x180010973  jnz     short loc_1800109C2
0x180010975  mov     edi, 8007000Eh
0x18001097a  mov     eax, cs:dword_180047000
0x180010980  cmp     eax, ebx
0x180010982  jbe     loc_180010E32
0x180010988  mov     rcx, cs:qword_180047018
0x18001098f  mov     rax, cs:qword_180047010
0x180010996  test    r13b, al
0x180010999  jz      loc_180010E32
0x18001099f  mov     rax, rcx
0x1800109a2  and     rax, r13
0x1800109a5  cmp     rax, rcx
0x1800109a8  jnz     loc_180010E32
0x1800109ae  mov     dword ptr [rsp+320h+hObject], 8007000Eh
0x1800109b6  lea     rdx, dword_18003EBE4
0x1800109bd  jmp     loc_1800108D8
0x1800109c2  mov     r10d, 7FFFh
0x1800109c8  mov     r9d, 0FFFEh
0x1800109ce  test    dil, dil
0x1800109d1  jz      loc_180010AED
0x1800109d7  mov     eax, cs:dword_180047000
0x1800109dd  cmp     eax, 4
0x1800109e0  jbe     loc_180010AED
0x1800109e6  mov     rcx, cs:qword_180047018
0x1800109ed  mov     rax, cs:qword_180047010
0x1800109f4  test    r13b, al
0x1800109f7  jz      loc_180010AED
0x1800109fd  mov     rax, rcx
0x180010a00  and     rax, r13
0x180010a03  cmp     rax, rcx
0x180010a06  jnz     loc_180010AED
0x180010a0c  mov     rax, [rsp+320h+var_2D8]
0x180010a11  mov     r8, [rsp+320h+lpszShortPath]
0x180010a16  sub     rax, r8
0x180010a19  sar     rax, 1
0x180010a1c  cmp     ax, r10w
0x180010a20  ja      short loc_180010A27
0x180010a22  add     ax, ax
0x180010a25  jmp     short loc_180010A2B
0x180010a27  movzx   eax, r9w
0x180010a2b  mov     [rbp+220h+var_2A0], r8
0x180010a2f  mov     [rbp+220h+var_298], ax
0x180010a33  mov     rcx, [rsp+320h+var_2B8]
0x180010a38  mov     rdx, [rsp+320h+var_2C0]
0x180010a3d  sub     rcx, rdx
0x180010a40  sar     rcx, 1
0x180010a43  cmp     cx, r10w
0x180010a47  ja      short loc_180010A4E
0x180010a49  add     cx, cx
0x180010a4c  jmp     short loc_180010A52
0x180010a4e  movzx   ecx, r9w
0x180010a52  mov     [rsp+320h+hObject], rdx
0x180010a57  mov     word ptr [rsp+320h+var_2E8], cx
0x180010a5c  lea     r9, [rbp+220h+var_298]
0x180010a60  mov     [rbp+220h+var_200], r9
0x180010a64  mov     [rbp+220h+var_1F8], rbx
0x180010a68  mov     [rbp+220h+var_1F0], r8
0x180010a6c  movzx   eax, ax
0x180010a6f  mov     dword ptr [rbp+220h+var_1E8], eax
0x180010a72  mov     dword ptr [rbp+220h+var_1E8+4], r12d
0x180010a76  lea     rax, [rsp+320h+var_2E8]
0x180010a7b  mov     [rbp+220h+var_220], rax
0x180010a7f  mov     [rbp+220h+var_218], rbx
0x180010a83  mov     [rbp+220h+var_210], rdx
0x180010a87  movzx   eax, cx
0x180010a8a  mov     dword ptr [rbp+220h+var_208], eax
0x180010a8d  mov     dword ptr [rbp+220h+var_208+4], r12d
0x180010a91  test    r14, r14
0x180010a94  jz      short loc_180010AAF
0x180010a96  mov     rcx, r14
0x180010a99  mov     rax, r15
0x180010a9c  inc     rax
0x180010a9f  cmp     [r14+rax*2], r12w
0x180010aa4  jnz     short loc_180010A9C
0x180010aa6  lea     eax, ds:2[rax*2]
0x180010aad  jmp     short loc_180010AB8
0x180010aaf  lea     rcx, dword_180039414
0x180010ab6  mov     eax, ebx
0x180010ab8  mov     [rbp+220h+var_230], rcx
0x180010abc  mov     dword ptr [rbp+220h+var_228], eax
0x180010abf  mov     dword ptr [rbp+220h+var_228+4], r12d
0x180010ac3  lea     rax, [rbp+220h+szLongPath]
0x180010ac7  mov     [rsp+320h+var_2F8], rax
0x180010acc  mov     [rsp+320h+bIgnoreCase], 7
0x180010ad4  xor     r9d, r9d
0x180010ad7  xor     r8d, r8d
0x180010ada  lea     rdx, byte_18003EB83
0x180010ae1  lea     rcx, dword_180047000
0x180010ae8  call    _tlgWriteTransfer_EventWriteTransfer
0x180010aed  mov     esi, 105h
0x180010af2  mov     r8d, esi; cchBuffer
0x180010af5  lea     rdx, [rbp+220h+szLongPath]; lpszLongPath
0x180010af9  mov     rcx, [rsp+320h+lpszShortPath]; lpszShortPath
0x180010afe  call    cs:__imp_GetLongPathNameW
0x180010b04  mov     edi, eax
0x180010b06  test    eax, eax
0x180010b08  jnz     loc_180010B9B
0x180010b0e  call    cs:__imp_GetLastError
0x180010b14  mov     edi, eax
0x180010b16  test    eax, eax
0x180010b18  jle     short loc_180010B23
0x180010b1a  movzx   edi, ax
0x180010b1d  or      edi, 80070000h
0x180010b23  mov     eax, cs:dword_180047000
0x180010b29  cmp     eax, ebx
0x180010b2b  jbe     loc_180010C1B
0x180010b31  mov     rcx, cs:qword_180047018
0x180010b38  mov     rax, cs:qword_180047010
0x180010b3f  test    r13b, al
0x180010b42  jz      loc_180010C1B
0x180010b48  mov     rax, rcx
0x180010b4b  and     rax, r13
0x180010b4e  cmp     rax, rcx
0x180010b51  jnz     loc_180010C1B
0x180010b57  mov     dword ptr [rsp+320h+hObject], edi
0x180010b5b  lea     rax, [rsp+320h+hObject]
0x180010b60  mov     [rbp+220h+var_260], rax
0x180010b64  mov     [rbp+220h+var_258], 4
0x180010b6c  lea     rax, [rbp+220h+var_280]
0x180010b70  mov     [rsp+320h+var_2F8], rax
0x180010b75  mov     [rsp+320h+bIgnoreCase], 3
0x180010b7d  xor     r9d, r9d
0x180010b80  xor     r8d, r8d
0x180010b83  lea     rdx, word_18003EB4A
0x180010b8a  lea     rcx, dword_180047000
0x180010b91  call    _tlgWriteTransfer_EventWriteTransfer
0x180010b96  jmp     loc_180010C1B
0x180010b9b  cmp     edi, esi
0x180010b9d  jbe     loc_180010C25
0x180010ba3  mov     rdx, rdi
0x180010ba6  lea     rcx, [rsp+320h+hObject]
0x180010bab  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180010bb0  mov     rsi, [rsp+320h+hObject]
0x180010bb5  test    rsi, rsi
0x180010bb8  jnz     short loc_180010BC1
0x180010bba  mov     edi, 8007000Eh
0x180010bbf  jmp     short loc_180010C0E
0x180010bc1  mov     r8d, edi; cchBuffer
0x180010bc4  mov     rdx, rsi; lpszLongPath
0x180010bc7  mov     rcx, [rsp+320h+lpszShortPath]; lpszShortPath
0x180010bcc  call    cs:__imp_GetLongPathNameW
0x180010bd2  cmp     edi, eax
0x180010bd4  ja      short loc_180010BDD
0x180010bd6  mov     edi, 8000FFFFh
0x180010bdb  jmp     short loc_180010C0E
  ... truncated ...
```
