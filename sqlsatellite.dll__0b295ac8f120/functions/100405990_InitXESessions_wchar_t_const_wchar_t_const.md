# InitXESessions(wchar_t const *,wchar_t const *)

- ea: `0x100405990`
- end: `0x1004062d6`
- name: `?InitXESessions@@YAJPEB_W0@Z`
- size: `2374`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x100404a00`

## callees

- `0x1004058e0`
- `0x100405990`
- `0x10045d400`
- `0x100469cd0`
- `0x10046a1d0`
- `0x100486af0`

## import_xrefs

- `KERNEL32!GetFileSize` at `0x100405b11`
- `KERNEL32!GetFileSize` at `0x100405b11`
- `KERNEL32!MultiByteToWideChar` at `0x100405c13`
- `KERNEL32!MultiByteToWideChar` at `0x100405ced`
- `KERNEL32!MultiByteToWideChar` at `0x100405c13`
- `KERNEL32!MultiByteToWideChar` at `0x100405ced`
- `KERNEL32!GetFileAttributesW` at `0x100405a5e`
- `KERNEL32!GetFileAttributesW` at `0x100405a5e`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x100405d2b`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x100405df2`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x100405d2b`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x100405df2`
- `KERNEL32!ReadFile` at `0x100405bbf`
- `KERNEL32!ReadFile` at `0x100405bbf`
- `KERNEL32!CloseHandle` at `0x100405f5e`
- `KERNEL32!CloseHandle` at `0x10040619e`
- `KERNEL32!CloseHandle` at `0x1004061eb`
- `KERNEL32!CloseHandle` at `0x100405f5e`
- `KERNEL32!CloseHandle` at `0x10040619e`
- `KERNEL32!CloseHandle` at `0x1004061eb`
- `KERNEL32!GetLastError` at `0x100405c20`
- `KERNEL32!GetLastError` at `0x100405d37`
- `KERNEL32!GetLastError` at `0x100405dfc`
- `KERNEL32!GetLastError` at `0x100405c20`
- `KERNEL32!GetLastError` at `0x100405d37`
- `KERNEL32!GetLastError` at `0x100405dfc`
- `KERNEL32!CreateFileW` at `0x100405ae3`
- `KERNEL32!CreateFileW` at `0x100405ae3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100405bf1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100405d1d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100405e64`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100405bf1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100405d1d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100405e64`
- `sqldk!??_V@YAXPEAX@Z` at `0x100405e17`
- `sqldk!??_V@YAXPEAX@Z` at `0x100405e24`
- `sqldk!??_V@YAXPEAX@Z` at `0x100405e30`
- `sqldk!??_V@YAXPEAX@Z` at `0x100405f41`
- `sqldk!??_V@YAXPEAX@Z` at `0x100405f4d`
- `sqldk!??_V@YAXPEAX@Z` at `0x100405f68`
- `sqldk!??_V@YAXPEAX@Z` at `0x100405e17`
- `sqldk!??_V@YAXPEAX@Z` at `0x100405e24`
- `sqldk!??_V@YAXPEAX@Z` at `0x100405e30`
- `sqldk!??_V@YAXPEAX@Z` at `0x100405f41`
- `sqldk!??_V@YAXPEAX@Z` at `0x100405f4d`
- `sqldk!??_V@YAXPEAX@Z` at `0x100405f68`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100405b8c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100405cab`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100405dc4`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100405b8c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100405cab`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100405dc4`
- `sqldk!SystemThread_TlsIndex` at `0x100405b36`
- `sqldk!SystemThread_TlsIndex` at `0x100405c4a`
- `sqldk!SystemThread_TlsIndex` at `0x100405d62`
- `sqldk!SystemThread_TlsOffset` at `0x100405b3f`
- `sqldk!SystemThread_TlsOffset` at `0x100405c53`
- `sqldk!SystemThread_TlsOffset` at `0x100405d6b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405b5b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405c6e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405d87`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405b5b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405c6e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405d87`
- `ole32!CoInitializeEx` at `0x1004059d4`
- `ole32!CoInitializeEx` at `0x1004059d4`
- `ole32!CoUninitialize` at `0x10040629c`
- `ole32!CoUninitialize` at `0x10040629c`
- `OLEAUT32!__imp_SysAllocString` at `0x100405e89`
- `OLEAUT32!__imp_SysAllocString` at `0x100405e89`
- `OLEAUT32!__imp_SysFreeString` at `0x100405eaf`
- `OLEAUT32!__imp_SysFreeString` at `0x100405eaf`

## string_xrefs

- `0x1004061a6`: `XEvent configuration file size is invalid %u`
- `0x1004061d0`: `XEvent configuration file %s error.\n`
- `0x100405b78`: `Sql\Ntdbms\extensibility\common\configsos\bootxevents.cpp`
- `0x100405c94`: `Sql\Ntdbms\extensibility\common\configsos\bootxevents.cpp`
- `0x100405dad`: `Sql\Ntdbms\extensibility\common\configsos\bootxevents.cpp`
- `0x100405fe9`: `Deleted`
- `0x100405bde`: `"Sql\\Ntdbms\\extensibility\\common\\configsos\\bootxevents.cpp"`
- `0x100405d0a`: `"Sql\\Ntdbms\\extensibility\\common\\configsos\\bootxevents.cpp"`
- `0x100405e51`: `"Sql\\Ntdbms\\extensibility\\common\\configsos\\bootxevents.cpp"`
- `0x100405e58`: `cwExpandedXmlConfig == cwExpandedXmlConfigEstimate`
- `0x100405be5`: `cbXmlConfig == cbXmlConfigRead`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
HRESULT __fastcall InitXESessions(const wchar_t *a1, const wchar_t *a2)
{
  HRESULT result; // eax
  __int64 v4; // rdx
  WCHAR *v5; // rcx
  signed __int64 v6; // rbx
  WCHAR v7; // ax
  WCHAR *v8; // rax
  signed int v9; // edi
  HANDLE FileW; // rax
  void *v11; // r15
  DWORD FileSize; // eax
  __int64 v13; // rbx
  __int64 v14; // r14
  __int64 v15; // rdx
  void *v16; // rax
  void *v17; // r14
  int v18; // eax
  unsigned __int64 v19; // r12
  signed int LastError; // eax
  __int64 v21; // rbx
  __int64 v22; // r10
  unsigned __int64 v23; // rax
  WCHAR *v24; // rax
  const WCHAR *v25; // rbx
  WCHAR *v26; // r13
  int v27; // eax
  DWORD v28; // eax
  unsigned __int64 v29; // rbx
  signed int v30; // eax
  __int64 v31; // r13
  __int64 v32; // r10
  unsigned __int64 v33; // rax
  WCHAR *v34; // rax
  WCHAR *v35; // r12
  DWORD v36; // eax
  signed int v37; // eax
  struct IXMLDOMDocument *v38; // rbx
  int Dom; // r13d
  XE_XMLConfig *v40; // rbx
  struct IXMLDOMDocument *v41; // rbx
  __int64 v42; // rax
  __int64 v43; // rax
  volatile signed __int32 *v44; // rdx
  volatile signed __int32 *v45; // rcx
  __int64 v46; // rax
  volatile signed __int32 *v47; // rdx
  volatile signed __int32 *v48; // rcx
  __int64 v49; // rax
  volatile signed __int32 *v50; // rdx
  volatile signed __int32 *v51; // rcx
  const OLECHAR *v52; // rdx
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // rcx
  volatile signed __int32 *v59; // rax
  volatile signed __int32 *v60; // rcx
  char v61; // [rsp+40h] [rbp-2C8h]
  volatile signed __int32 *v62; // [rsp+48h] [rbp-2C0h] BYREF
  LPCWSTR lpSrc; // [rsp+50h] [rbp-2B8h]
  char v64; // [rsp+58h] [rbp-2B0h] BYREF
  DWORD FileSizeHigh; // [rsp+5Ch] [rbp-2ACh] BYREF
  __int64 v66; // [rsp+60h] [rbp-2A8h] BYREF
  __int64 v67; // [rsp+68h] [rbp-2A0h] BYREF
  __int64 v68; // [rsp+70h] [rbp-298h] BYREF
  DWORD NumberOfBytesRead; // [rsp+78h] [rbp-290h] BYREF
  struct IXMLDOMDocument *v70; // [rsp+80h] [rbp-288h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-280h]
  XE_XMLConfig *v72; // [rsp+90h] [rbp-278h]
  BSTR v73; // [rsp+98h] [rbp-270h]
  __int64 v74; // [rsp+A0h] [rbp-268h]
  char *v75; // [rsp+A8h] [rbp-260h]
  void *v76; // [rsp+B0h] [rbp-258h]
  WCHAR *v77; // [rsp+B8h] [rbp-250h]
  WCHAR *v78; // [rsp+C0h] [rbp-248h]
  WCHAR FileName[264]; // [rsp+D0h] [rbp-238h] BYREF

  v74 = -2;
  result = CoInitializeEx(0, 0);
  if ( result < 0 )
  {
    _mm_lfence();
    return result;
  }
  v75 = &v64;
  v4 = 260;
  v5 = FileName;
  v6 = (char *)a1 - (char *)FileName;
  do
  {
    if ( v4 == -2147483386 )
      break;
    v7 = *(WCHAR *)((char *)v5 + v6);
    if ( !v7 )
      break;
    *v5++ = v7;
    --v4;
  }
  while ( v4 );
  v8 = v5 - 1;
  if ( v4 )
    v8 = v5;
  *v8 = 0;
  v9 = -2147024774;
  if ( v4 )
  {
    if ( GetFileAttributesW(FileName) == -1 )
    {
      v9 = 0;
      goto LABEL_134;
    }
    v62 = 0;
    v66 = 0;
    v68 = 0;
    v67 = 0;
    v61 = 0;
    if ( !qword_10052CD80 )
    {
      qword_10052CD80 = (__int64)&off_1004EDA00;
      xmmword_1004EDC20 = (__int128)XE_XMLConfig_SessionTag;
      v61 = 1;
    }
    v9 = -2147467259;
    FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v11 = FileW;
    hObject = FileW;
    if ( FileW == (HANDLE)-1LL )
      goto LABEL_109;
    FileSizeHigh = 0;
    FileSize = GetFileSize(FileW, &FileSizeHigh);
    v13 = FileSize;
    if ( FileSize == -1 || FileSizeHigh )
    {
      hObject = (HANDLE)-1LL;
      CloseHandle(v11);
      log_unlocalized(L"XEvent configuration file size is invalid %u", (unsigned int)v13);
      goto LABEL_112;
    }
    v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v15 = *(_QWORD *)(v14 + 256);
    if ( !v15 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v15 = *(_QWORD *)(v14 + 256);
    }
    v16 = operator new[](
            (unsigned int)(v13 + 1),
            *(struct IMemObj **)(v15 + 1000),
            1,
            "Sql\\Ntdbms\\extensibility\\common\\configsos\\bootxevents.cpp",
            487,
            6u);
    v17 = v16;
    v76 = v16;
    if ( !v16 )
    {
      v9 = -2147024882;
LABEL_51:
      operator delete[](v17);
LABEL_112:
      if ( hObject != (HANDLE)-1LL )
        CloseHandle(hObject);
      if ( v67 )
      {
        v53 = v67 + 8;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v67 + 8), 0xFFFFFFFF) == 1 )
        {
          v54 = v53 - 8;
          if ( !v53 )
            v54 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 8LL))(v54);
        }
      }
      if ( v68 )
      {
        v55 = v68 + 8;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v68 + 8), 0xFFFFFFFF) == 1 )
        {
          v56 = v55 - 8;
          if ( !v55 )
            v56 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 8LL))(v56);
        }
      }
      if ( v66 )
      {
        v57 = v66 + 8;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v66 + 8), 0xFFFFFFFF) == 1 )
        {
          v58 = v57 - 8;
          if ( !v57 )
            v58 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 8LL))(v58);
        }
      }
      if ( v62 )
      {
        v59 = v62 + 2;
        if ( _InterlockedExchangeAdd(v62 + 2, 0xFFFFFFFF) == 1 )
        {
          v60 = v59 - 2;
          if ( !v59 )
            v60 = 0;
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v60 + 56LL))(v60);
        }
      }
      goto LABEL_134;
    }
    if ( !ReadFile(v11, v16, v13, &NumberOfBytesRead, 0) )
    {
LABEL_67:
      hObject = (HANDLE)-1LL;
      CloseHandle(v11);
      operator delete[](v17);
      if ( v9 >= 0 )
      {
        v42 = *(_QWORD *)qword_10052CD80;
        if ( v61 )
          (*(void (__fastcall **)(__int64, __int64 *))v42)(qword_10052CD80, &v66);
        else
          (*(void (__fastcall **)(__int64, __int64 *, __int64 *, __int64 *))(v42 + 8))(
            qword_10052CD80,
            &v66,
            &v68,
            &v67);
        if ( v67 && (**(unsigned int (__fastcall ***)(__int64, volatile signed __int32 **))v67)(v67, &v62) )
        {
          do
          {
            if ( !v62 )
              break;
            if ( (*(unsigned int (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 24LL))(v62) )
            {
              v43 = (**(__int64 (__fastcall ***)(volatile signed __int32 *))v62)(v62);
              log_unlocalized(L"%s XE session %s\n", L"Deleted", v43 + 56);
            }
            else
            {
              ReportSatelliteXEError(v62);
            }
            if ( v62 )
            {
              v44 = v62 + 2;
              if ( _InterlockedExchangeAdd(v62 + 2, 0xFFFFFFFF) == 1 )
              {
                v45 = v44 - 2;
                if ( !v44 )
                  v45 = 0;
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 56LL))(v45);
              }
            }
            v62 = 0;
          }
          while ( (**(unsigned int (__fastcall ***)(__int64, volatile signed __int32 **))v67)(v67, &v62) );
        }
        if ( v68 && (**(unsigned int (__fastcall ***)(__int64, volatile signed __int32 **))v68)(v68, &v62) )
        {
          do
          {
            if ( !v62 )
              break;
            (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
            if ( (*(unsigned int (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 32LL))(v62) )
            {
              v46 = (**(__int64 (__fastcall ***)(volatile signed __int32 *))v62)(v62);
              log_unlocalized(L"%s XE session %s\n", L"Modified", v46 + 56);
            }
            else
            {
              ReportSatelliteXEError(v62);
            }
            if ( v62 )
            {
              v47 = v62 + 2;
              if ( _InterlockedExchangeAdd(v62 + 2, 0xFFFFFFFF) == 1 )
              {
                v48 = v47 - 2;
                if ( !v47 )
                  v48 = 0;
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 56LL))(v48);
              }
            }
            v62 = 0;
          }
          while ( (**(unsigned int (__fastcall ***)(__int64, volatile signed __int32 **))v68)(v68, &v62) );
        }
        if ( v66 && (**(unsigned int (__fastcall ***)(__int64, volatile signed __int32 **))v66)(v66, &v62) )
        {
          do
          {
            if ( !v62 )
              break;
            if ( (*(unsigned int (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 16LL))(v62) )
            {
              v49 = (**(__int64 (__fastcall ***)(volatile signed __int32 *))v62)(v62);
              log_unlocalized(L"%s XE session %s\n", L"Started", v49 + 56);
            }
            else
            {
              ReportSatelliteXEError(v62);
            }
            if ( v62 )
            {
              v50 = v62 + 2;
              if ( _InterlockedExchangeAdd(v62 + 2, 0xFFFFFFFF) == 1 )
              {
                v51 = v50 - 2;
                if ( !v50 )
                  v51 = 0;
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 56LL))(v51);
              }
            }
            v62 = 0;
          }
          while ( (**(unsigned int (__fastcall ***)(__int64, volatile signed __int32 **))v66)(v66, &v62) );
        }
        v9 = 0;
        goto LABEL_112;
      }
LABEL_109:
      v52 = &word_1004A26DC;
      if ( *(_QWORD *)(qword_10052CD80 + 536) )
        v52 = *(const OLECHAR **)(qword_10052CD80 + 536);
      log_unlocalized(L"XEvent configuration file %s error.\n", v52);
      goto LABEL_112;
    }
    if ( (_DWORD)v13 != NumberOfBytesRead )
      utassert_fail(
        1u,
        "cbXmlConfig == cbXmlConfigRead",
        "\"Sql\\\\Ntdbms\\\\extensibility\\\\common\\\\configsos\\\\bootxevents.cpp\"",
        495,
        0);
    *((_BYTE *)v17 + v13) = 0;
    v18 = MultiByteToWideChar(0xFDE9u, 0, (LPCCH)v17, -1, 0, 0);
    v19 = v18;
    if ( v18 <= 0 )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_51;
    }
    _mm_lfence();
    v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v22 = *(_QWORD *)(v21 + 256);
    if ( !v22 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v22 = *(_QWORD *)(v21 + 256);
    }
    v23 = 2 * v19;
    if ( !is_mul_ok(v19, 2u) )
      v23 = -1;
    v24 = (WCHAR *)operator new[](
                     v23,
                     *(struct IMemObj **)(v22 + 1000),
                     1,
                     "Sql\\Ntdbms\\extensibility\\common\\configsos\\bootxevents.cpp",
                     513,
                     6u);
    v25 = v24;
    lpSrc = v24;
    v77 = v24;
    if ( !v24 )
    {
      v9 = -2147024882;
      v26 = 0;
LABEL_50:
      _mm_lfence();
      operator delete[](v26);
      goto LABEL_51;
    }
    _mm_lfence();
    v27 = MultiByteToWideChar(0xFDE9u, 0, (LPCCH)v17, -1, v24, v19);
    if ( v27 <= 0 )
      goto LABEL_37;
    _mm_lfence();
    if ( v27 != (_DWORD)v19 )
      utassert_fail(
        1u,
        "cwConvertedChars == cChars",
        "\"Sql\\\\Ntdbms\\\\extensibility\\\\common\\\\configsos\\\\bootxevents.cpp\"",
        530,
        0);
    v28 = ExpandEnvironmentStringsW(v25, 0, 0);
    v29 = v28;
    if ( !v28 )
    {
LABEL_37:
      v30 = GetLastError();
      v9 = v30;
      if ( v30 > 0 )
        v9 = (unsigned __int16)v30 | 0x80070000;
      v26 = (WCHAR *)lpSrc;
      goto LABEL_50;
    }
    _mm_lfence();
    v31 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v32 = *(_QWORD *)(v31 + 256);
    if ( !v32 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v32 = *(_QWORD *)(v31 + 256);
    }
    v33 = 2 * v29;
    if ( !is_mul_ok(v29, 2u) )
      v33 = -1;
    v34 = (WCHAR *)operator new[](
                     v33,
                     *(struct IMemObj **)(v32 + 1000),
                     1,
                     "Sql\\Ntdbms\\extensibility\\common\\configsos\\bootxevents.cpp",
                     538,
                     6u);
    v35 = v34;
    v78 = v34;
    v26 = (WCHAR *)lpSrc;
    if ( !v34 )
    {
      v9 = -2147024882;
LABEL_49:
      _mm_lfence();
      operator delete[](v35);
      goto LABEL_50;
    }
    _mm_lfence();
    v36 = ExpandEnvironmentStringsW(lpSrc, v34, v29);
    if ( !v36 )
    {
      v37 = GetLastError();
      v9 = v37;
      if ( v37 > 0 )
        v9 = (unsigned __int16)v37 | 0x80070000;
      goto LABEL_49;
    }
    _mm_lfence();
    if ( v36 != (_DWORD)v29 )
      utassert_fail(
        1u,
        "cwExpandedXmlConfig == cwExpandedXmlConfigEstimate",
        "\"Sql\\\\Ntdbms\\\\extensibility\\\\common\\\\configsos\\\\bootxevents.cpp\"",
        552,
        0);
    v72 = (XE_XMLConfig *)qword_10052CD80;
    v38 = 0;
    v70 = 0;
    Dom = -2147467259;
    v73 = SysAllocString(v35);
    if ( v73 )
    {
      v40 = v72;
      SysFreeString(*((BSTR *)v72 + 66));
      *((_QWORD *)v40 + 66) = v73;
      Dom = XE_XMLConfigBase::CreateDom((OLECHAR *)v40 + 4, (struct IXMLDOMDocument2 **)&v70);
      if ( Dom >= 0 )
      {
        _mm_lfence();
        v41 = v70;
        if ( (unsigned int)XE_XMLConfig::InternalInit(v72, v70) )
        {
          if ( v41 )
            ((void (__fastcall *)(struct IXMLDOMDocument *))v41->lpVtbl->Release)(v41);
          v9 = 0;
        }
        else if ( v41 )
        {
          ((void (__fastcall *)(struct IXMLDOMDocument *))v41->lpVtbl->Release)(v41);
        }
LABEL_66:
        operator delete[](v35);
        operator delete[]((void *)lpSrc);
        goto LABEL_67;
      }
      v38 = v70;
    }
    if ( v38 )
      ((void (__fastcall *)(struct IXMLDOMDocument *))v38->lpVtbl->Release)(v38);
    v9 = Dom;
    goto LABEL_66;
  }
LABEL_134:
  CoUninitialize();
  return v9;
}

```

## disassembly

```asm
0x100405990  mov     rax, rsp
0x100405993  push    r13
0x100405995  push    r14
0x100405997  push    r15
0x100405999  sub     rsp, 2F0h
0x1004059a0  mov     qword ptr [rax-268h], 0FFFFFFFFFFFFFFFEh
0x1004059ab  mov     [rax+8], rbx
0x1004059af  mov     [rax+10h], rsi
0x1004059b3  mov     [rax+18h], rdi
0x1004059b7  mov     [rax+20h], r12
0x1004059bb  mov     rax, cs:__security_cookie
0x1004059c2  xor     rax, rsp
0x1004059c5  mov     [rsp+308h+var_28], rax
0x1004059cd  mov     rbx, rcx
0x1004059d0  xor     edx, edx; dwCoInit
0x1004059d2  xor     ecx, ecx; pvReserved
0x1004059d4  call    cs:__imp_CoInitializeEx
0x1004059da  test    eax, eax
0x1004059dc  jns     short loc_1004059E6
0x1004059de  lfence
0x1004059e1  jmp     loc_1004062A4
0x1004059e6  lea     rax, [rsp+308h+var_2B0]
0x1004059eb  mov     [rsp+308h+var_260], rax
0x1004059f3  mov     edx, 104h
0x1004059f8  lea     rcx, [rsp+308h+FileName]
0x100405a00  lea     rax, [rsp+308h+FileName]
0x100405a08  sub     rbx, rax
0x100405a0b  nop     dword ptr [rax+rax+00h]
0x100405a10  lea     rax, [rdx+7FFFFEFAh]
0x100405a17  test    rax, rax
0x100405a1a  jz      short loc_100405A32
0x100405a1c  movzx   eax, word ptr [rcx+rbx]
0x100405a20  test    ax, ax
0x100405a23  jz      short loc_100405A32
0x100405a25  mov     [rcx], ax
0x100405a28  add     rcx, 2
0x100405a2c  sub     rdx, 1
0x100405a30  jnz     short loc_100405A10
0x100405a32  lea     rax, [rcx-2]
0x100405a36  test    rdx, rdx
0x100405a39  cmovnz  rax, rcx
0x100405a3d  xor     r13d, r13d
0x100405a40  mov     [rax], r13w
0x100405a44  mov     edi, 8007007Ah
0x100405a49  test    rdx, rdx
0x100405a4c  cmovnz  edi, r13d
0x100405a50  jz      loc_10040629C
0x100405a56  lea     rcx, [rsp+308h+FileName]; lpFileName
0x100405a5e  call    cs:__imp_GetFileAttributesW
0x100405a64  cmp     eax, 0FFFFFFFFh
0x100405a67  jnz     short loc_100405A71
0x100405a69  mov     edi, r13d
0x100405a6c  jmp     loc_10040629C
0x100405a71  mov     [rsp+308h+var_2C0], r13
0x100405a76  mov     [rsp+308h+var_2A8], r13
0x100405a7b  mov     [rsp+308h+var_298], r13
0x100405a80  mov     [rsp+308h+var_2A0], r13
0x100405a85  mov     [rsp+308h+var_2C8], 0
0x100405a8a  cmp     cs:qword_10052CD80, 0
0x100405a92  jnz     short loc_100405AB5
0x100405a94  lea     rax, off_1004EDA00
0x100405a9b  mov     cs:qword_10052CD80, rax
0x100405aa2  movups  xmm0, xmmword ptr cs:?XE_XMLConfig_SessionTag@@3U_GUID@@B.Data1; _GUID const XE_XMLConfig_SessionTag ...
0x100405aa9  movaps  cs:xmmword_1004EDC20, xmm0
0x100405ab0  mov     [rsp+308h+var_2C8], 1
0x100405ab5  mov     edi, 80004005h
0x100405aba  mov     [rsp+308h+hTemplateFile], r13; hTemplateFile
0x100405abf  mov     [rsp+308h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x100405ac7  mov     [rsp+308h+dwCreationDisposition], 3; dwCreationDisposition
0x100405acf  xor     r9d, r9d; lpSecurityAttributes
0x100405ad2  mov     edx, 80000000h; dwDesiredAccess
0x100405ad7  lea     r8d, [r9+1]; dwShareMode
0x100405adb  lea     rcx, [rsp+308h+FileName]; lpFileName
0x100405ae3  call    cs:__imp_CreateFileW
0x100405ae9  mov     r15, rax
0x100405aec  mov     [rsp+308h+hObject], rax
0x100405af4  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x100405afb  cmp     rax, rsi
0x100405afe  jz      loc_1004061B4
0x100405b04  mov     [rsp+308h+FileSizeHigh], r13d
0x100405b09  lea     rdx, [rsp+308h+FileSizeHigh]; lpFileSizeHigh
0x100405b0e  mov     rcx, rax; hFile
0x100405b11  call    cs:__imp_GetFileSize
0x100405b17  mov     ebx, eax
0x100405b19  cmp     eax, 0FFFFFFFFh
0x100405b1c  jz      loc_100406193
0x100405b22  cmp     [rsp+308h+FileSizeHigh], 0
0x100405b27  ja      loc_100406193
0x100405b2d  mov     r8, gs:58h
0x100405b36  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x100405b3d  mov     edx, [rcx]
0x100405b3f  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x100405b46  mov     r14d, [rcx]
0x100405b49  add     r14, [r8+rdx*8]
0x100405b4d  mov     rdx, [r14+100h]
0x100405b54  test    rdx, rdx
0x100405b57  jnz     short loc_100405B68
0x100405b59  xor     ecx, ecx
0x100405b5b  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100405b61  mov     rdx, [r14+100h]
0x100405b68  lea     ecx, [rbx+1]
0x100405b6b  mov     byte ptr [rsp+308h+dwFlagsAndAttributes], 6
0x100405b70  mov     [rsp+308h+dwCreationDisposition], 1E7h
0x100405b78  lea     r9, aSqlNtdbmsExten_5; "Sql\\Ntdbms\\extensibility\\common\\con"...
0x100405b7f  mov     r8d, 1
0x100405b85  mov     rdx, [rdx+3E8h]
0x100405b8c  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100405b92  mov     r14, rax
0x100405b95  mov     [rsp+308h+var_258], rax
0x100405b9d  test    rax, rax
0x100405ba0  jnz     short loc_100405BAC
0x100405ba2  mov     edi, 8007000Eh
0x100405ba7  jmp     loc_100405E2D
0x100405bac  mov     qword ptr [rsp+308h+dwCreationDisposition], r13; lpOverlapped
0x100405bb1  lea     r9, [rsp+308h+NumberOfBytesRead]; lpNumberOfBytesRead
0x100405bb6  mov     r8d, ebx; nNumberOfBytesToRead
0x100405bb9  mov     rdx, r14; lpBuffer
0x100405bbc  mov     rcx, r15; hFile
0x100405bbf  call    cs:__imp_ReadFile
0x100405bc5  test    eax, eax
0x100405bc7  jz      loc_100405F53
0x100405bcd  cmp     ebx, [rsp+308h+NumberOfBytesRead]
0x100405bd1  jz      short loc_100405BF7
0x100405bd3  mov     qword ptr [rsp+308h+dwCreationDisposition], r13
0x100405bd8  mov     r9d, 1EFh
0x100405bde  lea     r8, aSqlNtdbmsExten_11; "\"Sql\\\\Ntdbms\\\\extensibility\\\\com"...
0x100405be5  lea     rdx, aCbxmlconfigCbx; "cbXmlConfig == cbXmlConfigRead"
0x100405bec  mov     ecx, 1
0x100405bf1  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100405bf7  mov     byte ptr [rbx+r14], 0
0x100405bfc  mov     [rsp+308h+dwFlagsAndAttributes], r13d; cchWideChar
0x100405c01  mov     qword ptr [rsp+308h+dwCreationDisposition], r13; lpWideCharStr
0x100405c06  mov     r9d, esi; cbMultiByte
0x100405c09  mov     r8, r14; lpMultiByteStr
0x100405c0c  xor     edx, edx; dwFlags
0x100405c0e  mov     ecx, 0FDE9h; CodePage
0x100405c13  call    cs:__imp_MultiByteToWideChar
0x100405c19  movsxd  r12, eax
0x100405c1c  test    eax, eax
0x100405c1e  jg      short loc_100405C3E
0x100405c20  call    cs:__imp_GetLastError
0x100405c26  mov     edi, eax
0x100405c28  test    eax, eax
0x100405c2a  jle     loc_100405E2D
0x100405c30  movzx   edi, ax
0x100405c33  or      edi, 80070000h
0x100405c39  jmp     loc_100405E2D
0x100405c3e  lfence
0x100405c41  mov     rdx, gs:58h
0x100405c4a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100405c51  mov     ecx, [rax]
0x100405c53  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100405c5a  mov     ebx, [rax]
0x100405c5c  add     rbx, [rdx+rcx*8]
0x100405c60  mov     r10, [rbx+100h]
0x100405c67  test    r10, r10
0x100405c6a  jnz     short loc_100405C7B
0x100405c6c  xor     ecx, ecx
0x100405c6e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100405c74  mov     r10, [rbx+100h]
0x100405c7b  mov     eax, 2
0x100405c80  mul     r12
0x100405c83  cmovo   rax, rsi
0x100405c87  mov     byte ptr [rsp+308h+dwFlagsAndAttributes], 6
0x100405c8c  mov     [rsp+308h+dwCreationDisposition], 201h
0x100405c94  lea     r9, aSqlNtdbmsExten_5; "Sql\\Ntdbms\\extensibility\\common\\con"...
0x100405c9b  mov     r8d, 1
0x100405ca1  mov     rdx, [r10+3E8h]
0x100405ca8  mov     rcx, rax
0x100405cab  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100405cb1  mov     rbx, rax
0x100405cb4  mov     [rsp+308h+lpSrc], rax
0x100405cb9  mov     [rsp+308h+var_250], rax
0x100405cc1  test    rax, rax
0x100405cc4  jnz     short loc_100405CD3
0x100405cc6  mov     edi, 8007000Eh
0x100405ccb  mov     r13, rax
0x100405cce  jmp     loc_100405E1E
0x100405cd3  lfence
0x100405cd6  mov     [rsp+308h+dwFlagsAndAttributes], r12d; cchWideChar
0x100405cdb  mov     qword ptr [rsp+308h+dwCreationDisposition], rbx; lpWideCharStr
0x100405ce0  mov     r9d, esi; cbMultiByte
0x100405ce3  mov     r8, r14; lpMultiByteStr
0x100405ce6  xor     edx, edx; dwFlags
0x100405ce8  mov     ecx, 0FDE9h; CodePage
0x100405ced  call    cs:__imp_MultiByteToWideChar
0x100405cf3  test    eax, eax
0x100405cf5  jle     short loc_100405D37
0x100405cf7  lfence
0x100405cfa  cmp     eax, r12d
0x100405cfd  jz      short loc_100405D23
0x100405cff  mov     qword ptr [rsp+308h+dwCreationDisposition], r13
0x100405d04  mov     r9d, 212h
0x100405d0a  lea     r8, aSqlNtdbmsExten_11; "\"Sql\\\\Ntdbms\\\\extensibility\\\\com"...
0x100405d11  lea     rdx, aCwconvertedcha; "cwConvertedChars == cChars"
0x100405d18  mov     ecx, 1
0x100405d1d  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100405d23  xor     r8d, r8d; nSize
0x100405d26  xor     edx, edx; lpDst
0x100405d28  mov     rcx, rbx; lpSrc
0x100405d2b  call    cs:__imp_ExpandEnvironmentStringsW
0x100405d31  mov     ebx, eax
0x100405d33  test    eax, eax
0x100405d35  jnz     short loc_100405D56
0x100405d37  call    cs:__imp_GetLastError
0x100405d3d  test    eax, eax
0x100405d3f  mov     edi, eax
0x100405d41  jle     short loc_100405D4C
0x100405d43  movzx   edi, ax
0x100405d46  or      edi, 80070000h
0x100405d4c  mov     r13, [rsp+308h+lpSrc]
0x100405d51  jmp     loc_100405E1E
0x100405d56  lfence
0x100405d59  mov     rdx, gs:58h
0x100405d62  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100405d69  mov     ecx, [rax]
0x100405d6b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100405d72  mov     r13d, [rax]
0x100405d75  add     r13, [rdx+rcx*8]
0x100405d79  mov     r10, [r13+100h]
0x100405d80  test    r10, r10
0x100405d83  jnz     short loc_100405D94
0x100405d85  xor     ecx, ecx
0x100405d87  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100405d8d  mov     r10, [r13+100h]
0x100405d94  mov     eax, 2
0x100405d99  mul     rbx
0x100405d9c  cmovo   rax, rsi
0x100405da0  mov     byte ptr [rsp+308h+dwFlagsAndAttributes], 6
0x100405da5  mov     [rsp+308h+dwCreationDisposition], 21Ah
0x100405dad  lea     r9, aSqlNtdbmsExten_5; "Sql\\Ntdbms\\extensibility\\common\\con"...
0x100405db4  mov     r8d, 1
0x100405dba  mov     rdx, [r10+3E8h]
0x100405dc1  mov     rcx, rax
0x100405dc4  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100405dca  mov     r12, rax
0x100405dcd  mov     [rsp+308h+var_248], rax
0x100405dd5  mov     r13, [rsp+308h+lpSrc]
0x100405dda  test    rax, rax
0x100405ddd  jnz     short loc_100405DE6
0x100405ddf  mov     edi, 8007000Eh
0x100405de4  jmp     short loc_100405E11
0x100405de6  lfence
0x100405de9  mov     r8d, ebx; nSize
0x100405dec  mov     rdx, r12; lpDst
0x100405def  mov     rcx, r13; lpSrc
0x100405df2  call    cs:__imp_ExpandEnvironmentStringsW
0x100405df8  test    eax, eax
0x100405dfa  jnz     short loc_100405E3B
0x100405dfc  call    cs:__imp_GetLastError
0x100405e02  mov     edi, eax
0x100405e04  test    eax, eax
0x100405e06  jle     short loc_100405E11
0x100405e08  movzx   edi, ax
0x100405e0b  or      edi, 80070000h
0x100405e11  lfence
0x100405e14  mov     rcx, r12
0x100405e17  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100405e1d  nop
0x100405e1e  lfence
0x100405e21  mov     rcx, r13
0x100405e24  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100405e2a  xor     r13d, r13d
0x100405e2d  mov     rcx, r14
0x100405e30  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100405e36  jmp     loc_1004061DD
0x100405e3b  lfence
0x100405e3e  cmp     eax, ebx
0x100405e40  jz      short loc_100405E6A
0x100405e42  mov     qword ptr [rsp+308h+dwCreationDisposition], 0
0x100405e4b  mov     r9d, 228h
0x100405e51  lea     r8, aSqlNtdbmsExten_11; "\"Sql\\\\Ntdbms\\\\extensibility\\\\com"...
0x100405e58  lea     rdx, aCwexpandedxmlc; "cwExpandedXmlConfig == cwExpandedXmlCon"...
0x100405e5f  mov     ecx, 1
0x100405e64  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100405e6a  mov     rax, cs:qword_10052CD80
0x100405e71  mov     [rsp+308h+var_278], rax
0x100405e79  xor     ebx, ebx
0x100405e7b  mov     [rsp+308h+var_288], rbx
0x100405e83  mov     r13d, edi
0x100405e86  mov     rcx, r12; psz
0x100405e89  call    cs:__imp_SysAllocString
0x100405e8f  mov     [rsp+308h+var_270], rax
0x100405e97  test    rax, rax
0x100405e9a  jz      loc_100405F2A
0x100405ea0  mov     rbx, [rsp+308h+var_278]
0x100405ea8  mov     rcx, [rbx+210h]; bstrString
0x100405eaf  call    cs:__imp_SysFreeString
0x100405eb5  mov     rax, [rsp+308h+var_270]
0x100405ebd  mov     [rbx+210h], rax
0x100405ec4  lea     rdx, [rsp+308h+var_288]; struct IXMLDOMDocument2 **
0x100405ecc  lea     rcx, [rbx+8]; psz
0x100405ed0  call    ?CreateDom@XE_XMLConfigBase@@IEAAJPEAPEAUIXMLDOMDocument2@@@Z; XE_XMLConfigBase::CreateDom(IXMLDOMDocument2 * *)
0x100405ed5  mov     r13d, eax
0x100405ed8  test    eax, eax
0x100405eda  js      short loc_100405F22
0x100405edc  lfence
0x100405edf  mov     rbx, [rsp+308h+var_288]
0x100405ee7  mov     rdx, rbx; struct IXMLDOMDocument *
0x100405eea  mov     rcx, [rsp+308h+var_278]; this
  ... truncated ...
```
