# CDlpActionRecoverCrypto::RepairBlock(_ULARGE_INTEGER,_ULARGE_INTEGER)

- ea: `0x180027334`
- end: `0x180027c23`
- name: `?RepairBlock@CDlpActionRecoverCrypto@@AEAAJT_ULARGE_INTEGER@@0@Z`
- size: `2287`
- prototype: `__int64 __fastcall(CDlpActionRecoverCrypto *__hidden this, union _ULARGE_INTEGER, union _ULARGE_INTEGER)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180009c0c`

## callees

- `0x180002898`
- `0x18000aba4`
- `0x18000ea20`
- `0x180012f5c`
- `0x18001fd60`
- `0x180027334`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002755e`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002755e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180027956`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180027956`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800278a2`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800278a2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180027926`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180027926`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180027b3c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180027b3c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180027838`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180027879`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180027838`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180027879`
- `OLEAUT32!__imp_SysFreeString` at `0x180027b55`
- `OLEAUT32!__imp_SysFreeString` at `0x180027bb0`
- `OLEAUT32!__imp_SysFreeString` at `0x180027b55`
- `OLEAUT32!__imp_SysFreeString` at `0x180027bb0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800276fa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800276fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800273ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027736`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027b69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800273ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027736`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027b69`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800273cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800273cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027745`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027b77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027745`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027b77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027acf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027acf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027b8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027b9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027b8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027b9f`

## string_xrefs

- `0x180027404`: `CDlpActionRecoverCrypto::RepairBlock`
- `0x180027b10`: `CDlpActionRecoverCrypto::RepairBlock`
- `0x180027662`: `RecoverCrypto: Transferred repair block from to [%s]`
- `0x18002771f`: `RecoverCrypto: Updating remote source path: [%s] => [%s]`
- `0x18002798b`: `RecoverCrypto: Repaired block at offset [0x%I64X] of size [0x%I64X]`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CDlpActionRecoverCrypto::RepairBlock(
        CDlpActionRecoverCrypto *this,
        union _ULARGE_INTEGER a2,
        union _ULARGE_INTEGER a3)
{
  __int64 v4; // rdi
  __int64 FileW; // rsi
  HANDLE ProcessHeap; // rax
  LPVOID v7; // rax
  void *v8; // r14
  signed int v9; // r15d
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rbx
  int v14; // eax
  __int64 v15; // rbx
  int v16; // eax
  signed int LastError; // eax
  PCNZWCH *v18; // r12
  int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  PCNZWCH v24; // rbx
  HANDLE v25; // rax
  WCHAR *v26; // rbx
  unsigned int v27; // edx
  int StringCch; // eax
  int v29; // eax
  char *v30; // rax
  signed int v31; // eax
  __int64 v32; // rcx
  unsigned __int64 QuadPart; // rbx
  DWORD v34; // r12d
  __int64 v35; // rcx
  signed int v36; // eax
  signed int v37; // eax
  signed int v38; // eax
  signed int v39; // eax
  int v40; // eax
  HANDLE v41; // rax
  PCNZWCH lpString2; // [rsp+20h] [rbp-E0h]
  int lpString2a; // [rsp+20h] [rbp-E0h]
  int cchCount2[2]; // [rsp+28h] [rbp-D8h]
  int cchCount2a; // [rsp+28h] [rbp-D8h]
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  PCNZWCH v48; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v49; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+58h] [rbp-A8h] BYREF
  union _ULARGE_INTEGER v51; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpPathName; // [rsp+68h] [rbp-98h] BYREF
  LARGE_INTEGER liDistanceToMove; // [rsp+70h] [rbp-90h] BYREF
  __int64 v54; // [rsp+78h] [rbp-88h] BYREF
  __int64 v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h] BYREF
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  LPVOID v59; // [rsp+A0h] [rbp-60h]
  __int128 v60; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR TempFileName[264]; // [rsp+C0h] [rbp-40h] BYREF

  liDistanceToMove = (LARGE_INTEGER)a2.QuadPart;
  v51 = a3;
  v54 = 0;
  v50 = 0;
  v48 = 0;
  v4 = -1;
  v57 = -1;
  FileW = -1;
  v58 = -1;
  NumberOfBytesRead = 0;
  v56 = 0;
  lpPathName = 0;
  ++*((_DWORD *)this + 167);
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 0, 0x100000u);
  v8 = v7;
  if ( !v7 )
  {
    v59 = 0;
    v9 = -2147024882;
    v10 = *((_QWORD *)this + 11);
    if ( !v10 )
      goto LABEL_122;
    cchCount2a = -2147024882;
    lpString2a = 2090;
    goto LABEL_4;
  }
  v59 = v7;
  v13 = *((_QWORD *)this + 11);
  v55 = v13;
  if ( v13 )
  {
    v9 = 0;
  }
  else
  {
    v55 = 0;
    v9 = -2147483638;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147483638);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v9);
  if ( v9 >= 0 )
  {
    v60 = WINDLP_TRANSPORT_BITS;
    v14 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64 *))(*(_QWORD *)v13 + 80LL))(v13, &v60, &v54);
    v9 = v14;
    if ( v14 < 0 )
    {
      v10 = *((_QWORD *)this + 11);
      if ( !v10 )
        goto LABEL_122;
      cchCount2a = v14;
      lpString2a = 2095;
      goto LABEL_4;
    }
    v15 = *((_QWORD *)this + 12);
    if ( v15 )
    {
      v9 = 0;
    }
    else
    {
      v9 = -2147483638;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147483638);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v9);
    if ( v9 < 0 )
    {
      v10 = *((_QWORD *)this + 11);
      if ( !v10 )
        goto LABEL_122;
      cchCount2a = v9;
      lpString2a = 2099;
      goto LABEL_4;
    }
    v16 = (*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v15 + 232LL))(v15, &lpPathName);
    v9 = v16;
    if ( v16 < 0 )
    {
      v10 = *((_QWORD *)this + 11);
      if ( !v10 )
        goto LABEL_122;
      cchCount2a = v16;
      lpString2a = 2100;
      goto LABEL_4;
    }
    if ( !GetTempFileNameW(lpPathName, L"TRC", 0, TempFileName) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v9 = -2147467259;
      }
      if ( !*((_QWORD *)this + 11) )
        goto LABEL_122;
      v12 = 0;
      if ( v9 >= 0 )
      {
LABEL_6:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
        goto LABEL_122;
      }
      cchCount2a = v9;
      lpString2a = 2104;
      v10 = *((_QWORD *)this + 11);
LABEL_4:
      v11 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v10,
              4u,
              (__int64)L"%s(%d): Result = 0x%X",
              L"CDlpActionRecoverCrypto::RepairBlock",
              lpString2a,
              cchCount2a);
      v12 = (unsigned int)v11;
      if ( v11 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
      goto LABEL_6;
    }
    v18 = (PCNZWCH *)((char *)this + 568);
    v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, WCHAR *, __int64 *))(*(_QWORD *)v15 + 88LL))(
            v15,
            *((_QWORD *)this + 71),
            TempFileName,
            &v50);
    v9 = v19;
    if ( v19 < 0 )
    {
      v20 = *((_QWORD *)this + 11);
      if ( v20 )
      {
        cchCount2[0] = v19;
        LODWORD(lpString2) = 2112;
        goto LABEL_118;
      }
LABEL_121:
      DeleteFileW(TempFileName);
      goto LABEL_122;
    }
    v21 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, LARGE_INTEGER *, union _ULARGE_INTEGER *, __int64 *))(*(_QWORD *)v54 + 120LL))(
            v54,
            v50,
            v15,
            &liDistanceToMove,
            &v51,
            &v56);
    v9 = v21;
    v20 = *((_QWORD *)this + 11);
    if ( v21 < 0 )
    {
      if ( !v20 )
        goto LABEL_121;
      cchCount2[0] = v21;
      LODWORD(lpString2) = 2120;
LABEL_118:
      v40 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v20,
              4u,
              (__int64)L"%s(%d): Result = 0x%X",
              L"CDlpActionRecoverCrypto::RepairBlock",
              lpString2,
              *(_QWORD *)cchCount2);
      v32 = (unsigned int)v40;
      if ( v40 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v40);
LABEL_120:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v32);
      goto LABEL_121;
    }
    if ( v20 )
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v20,
        2u,
        (__int64)L"RecoverCrypto: Transferred repair block from to [%s]",
        TempFileName);
    if ( v56 != v51.QuadPart )
    {
      v9 = -2147467259;
      v20 = *((_QWORD *)this + 11);
      if ( !v20 )
        goto LABEL_121;
      cchCount2[0] = -2147467259;
      LODWORD(lpString2) = 2126;
      goto LABEL_118;
    }
    v22 = (*(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v50 + 48LL))(v50, &v48);
    v9 = v22;
    if ( v22 < 0 )
    {
      v20 = *((_QWORD *)this + 11);
      if ( !v20 )
        goto LABEL_121;
      cchCount2[0] = v22;
      LODWORD(lpString2) = 2130;
      goto LABEL_118;
    }
    if ( CompareStringW(0x409u, 1u, *v18, -1, v48, -1) == 2 )
    {
LABEL_64:
      FileW = (__int64)CreateFileW(TempFileName, 0x80000000, 3u, 0, 3u, 0xC000000u, 0);
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        FileW = -1;
        v58 = -1;
        v39 = GetLastError();
        v9 = v39;
        if ( v39 )
        {
          if ( v39 > 0 )
            v9 = (unsigned __int16)v39 | 0x80070000;
        }
        else
        {
          v9 = -2147467259;
        }
        if ( !*((_QWORD *)this + 11) )
          goto LABEL_121;
        v32 = 0;
        if ( v9 >= 0 )
          goto LABEL_120;
        cchCount2[0] = v9;
        LODWORD(lpString2) = 2157;
      }
      else
      {
        v58 = FileW;
        v30 = (char *)CreateFileW(*((LPCWSTR *)this + 69), 0x40000000u, 3u, 0, 3u, 0x8000000u, 0);
        if ( (unsigned __int64)(v30 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        {
          v57 = -1;
          v38 = GetLastError();
          v9 = v38;
          if ( v38 )
          {
            if ( v38 > 0 )
              v9 = (unsigned __int16)v38 | 0x80070000;
          }
          else
          {
            v9 = -2147467259;
          }
          if ( !*((_QWORD *)this + 11) )
            goto LABEL_121;
          v32 = 0;
          if ( v9 >= 0 )
            goto LABEL_120;
          cchCount2[0] = v9;
          LODWORD(lpString2) = 2166;
        }
        else
        {
          v4 = (__int64)v30;
          v57 = (__int64)v30;
          if ( SetFilePointerEx(v30, liDistanceToMove, 0, 0) )
          {
            QuadPart = v51.QuadPart;
            if ( !v51.QuadPart )
            {
LABEL_83:
              v35 = *((_QWORD *)this + 11);
              if ( v35 )
                CDlpLogT<CEmptyType>::DlpLogFormat(
                  v35,
                  2u,
                  (__int64)L"RecoverCrypto: Repaired block at offset [0x%I64X] of size [0x%I64X]",
                  liDistanceToMove.QuadPart,
                  QuadPart);
              goto LABEL_121;
            }
            while ( 1 )
            {
              v34 = QuadPart;
              if ( QuadPart > 0x100000 )
                v34 = 0x100000;
              if ( !ReadFile((HANDLE)FileW, v8, v34, &NumberOfBytesRead, 0) )
                break;
              if ( v34 != NumberOfBytesRead )
              {
                v9 = -2147418113;
                v20 = *((_QWORD *)this + 11);
                if ( !v20 )
                  goto LABEL_121;
                cchCount2[0] = -2147418113;
                LODWORD(lpString2) = 2189;
                goto LABEL_118;
              }
              if ( !WriteFile((HANDLE)v4, v8, v34, &NumberOfBytesRead, 0) )
              {
                v36 = GetLastError();
                v9 = v36;
                if ( v36 )
                {
                  if ( v36 > 0 )
                    v9 = (unsigned __int16)v36 | 0x80070000;
                }
                else
                {
                  v9 = -2147467259;
                }
                if ( !*((_QWORD *)this + 11) )
                  goto LABEL_121;
                v32 = 0;
                if ( v9 >= 0 )
                  goto LABEL_120;
                cchCount2[0] = v9;
                LODWORD(lpString2) = 2198;
                goto LABEL_117;
              }
              if ( v34 != NumberOfBytesRead )
              {
                v9 = -2147418113;
                v20 = *((_QWORD *)this + 11);
                if ( !v20 )
                  goto LABEL_121;
                cchCount2[0] = -2147418113;
                LODWORD(lpString2) = 2200;
                goto LABEL_118;
              }
              QuadPart -= v34;
              if ( !QuadPart )
              {
                QuadPart = v51.QuadPart;
                goto LABEL_83;
              }
            }
            v37 = GetLastError();
            v9 = v37;
            if ( v37 )
            {
              if ( v37 > 0 )
                v9 = (unsigned __int16)v37 | 0x80070000;
            }
            else
            {
              v9 = -2147467259;
            }
            if ( !*((_QWORD *)this + 11) )
              goto LABEL_121;
            v32 = 0;
            if ( v9 >= 0 )
              goto LABEL_120;
            cchCount2[0] = v9;
            LODWORD(lpString2) = 2187;
          }
          else
          {
            v31 = GetLastError();
            v9 = v31;
            if ( v31 )
            {
              if ( v31 > 0 )
                v9 = (unsigned __int16)v31 | 0x80070000;
            }
            else
            {
              v9 = -2147467259;
            }
            if ( !*((_QWORD *)this + 11) )
              goto LABEL_121;
            v32 = 0;
            if ( v9 >= 0 )
              goto LABEL_120;
            cchCount2[0] = v9;
            LODWORD(lpString2) = 2169;
          }
        }
      }
LABEL_117:
      v20 = *((_QWORD *)this + 11);
      goto LABEL_118;
    }
    v23 = *((_QWORD *)this + 11);
    if ( v23 )
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v23,
        2u,
        (__int64)L"RecoverCrypto: Updating remote source path: [%s] => [%s]",
        *v18,
        v48);
    v24 = *v18;
    if ( *v18 )
    {
      v25 = GetProcessHeap();
      HeapFree(v25, 0, (LPVOID)(v24 - 2));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      *v18 = 0;
    }
    v26 = (WCHAR *)v48;
    if ( v48 )
    {
      v49 = 0;
      StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v48, &v49);
      v9 = StringCch;
      if ( StringCch < 0 )
        goto LABEL_55;
      v27 = v49;
    }
    else
    {
      v27 = 0;
    }
    StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                  v26,
                  v27,
                  (_QWORD *)this + 71);
    v9 = StringCch;
    if ( StringCch >= 0 )
    {
LABEL_56:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v9);
      if ( v9 < 0 )
      {
        v20 = *((_QWORD *)this + 11);
        if ( !v20 )
          goto LABEL_121;
        cchCount2[0] = v9;
        LODWORD(lpString2) = 2141;
        goto LABEL_118;
      }
      v29 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v55 + 280LL))(v55, 1);
      v9 = v29;
      if ( v29 < 0 )
      {
        v20 = *((_QWORD *)this + 11);
        if ( !v20 )
          goto LABEL_121;
        cchCount2[0] = v29;
        LODWORD(lpString2) = 2145;
        goto LABEL_118;
      }
      goto LABEL_64;
    }
LABEL_55:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
    goto LABEL_56;
  }
  v10 = *((_QWORD *)this + 11);
  if ( v10 )
  {
    cchCount2a = v9;
    lpString2a = 2094;
    goto LABEL_4;
  }
LABEL_122:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v9);
  if ( lpPathName )
  {
    SysFreeString((BSTR)lpPathName);
    lpPathName = 0;
  }
  if ( v8 )
  {
    v41 = GetProcessHeap();
    HeapFree(v41, 0, v8);
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v4);
  if ( v48 )
  {
    SysFreeString((BSTR)v48);
    v48 = 0;
  }
  if ( v50 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    v50 = 0;
  }
  if ( v54 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180027334  mov     [rsp-8+arg_18], rbx
0x180027339  push    rbp
0x18002733a  push    rsi
0x18002733b  push    rdi
0x18002733c  push    r12
0x18002733e  push    r13
0x180027340  push    r14
0x180027342  push    r15
0x180027344  lea     rbp, [rsp-1E0h]
0x18002734c  sub     rsp, 2E0h
0x180027353  mov     rax, cs:__security_cookie
0x18002735a  xor     rax, rsp
0x18002735d  mov     [rbp+210h+var_40], rax
0x180027364  mov     r13, rcx
0x180027367  mov     qword ptr [rsp+310h+liDistanceToMove], rdx
0x18002736c  mov     [rsp+310h+var_2B0], r8
0x180027371  mov     [rsp+310h+var_298], 0
0x18002737a  mov     [rsp+310h+var_2B8], 0
0x180027383  mov     [rsp+310h+var_2C8], 0
0x18002738c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180027390  mov     [rbp+210h+var_280], rdi
0x180027394  mov     rsi, rdi
0x180027397  mov     [rbp+210h+var_278], rdi
0x18002739b  mov     [rsp+310h+NumberOfBytesRead], 0
0x1800273a3  mov     [rbp+210h+var_288], 0
0x1800273ab  mov     [rsp+310h+lpPathName], 0
0x1800273b4  inc     dword ptr [rcx+29Ch]
0x1800273ba  call    cs:__imp_GetProcessHeap
0x1800273c0  mov     rcx, rax; hHeap
0x1800273c3  xor     edx, edx; dwFlags
0x1800273c5  mov     r8d, 100000h; dwBytes
0x1800273cb  call    cs:__imp_HeapAlloc
0x1800273d1  mov     r14, rax
0x1800273d4  test    rax, rax
0x1800273d7  jnz     short loc_18002742A
0x1800273d9  mov     [rbp+210h+var_270], rax
0x1800273dd  mov     r15d, 8007000Eh
0x1800273e3  mov     rcx, [r13+58h]
0x1800273e7  test    rcx, rcx
0x1800273ea  jz      loc_180027B42
0x1800273f0  mov     [rsp+310h+cchCount2], r15d
0x1800273f5  mov     dword ptr [rsp+310h+lpString2], 82Ah
0x1800273fd  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180027404  lea     r9, aCdlpactionreco_10; "CDlpActionRecoverCrypto::RepairBlock"
0x18002740b  mov     edx, 4
0x180027410  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180027415  test    eax, eax
0x180027417  mov     ecx, eax
0x180027419  jns     short loc_180027420
0x18002741b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180027420  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180027425  jmp     loc_180027B42
0x18002742a  mov     [rbp+210h+var_270], r14
0x18002742e  mov     rbx, [r13+58h]
0x180027432  mov     [rbp+210h+var_290], rbx
0x180027436  mov     r12d, 8000000Ah
0x18002743c  test    rbx, rbx
0x18002743f  jnz     short loc_180027452
0x180027441  mov     [rbp+210h+var_290], rbx
0x180027445  mov     r15d, r12d
0x180027448  mov     ecx, r12d
0x18002744b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180027450  jmp     short loc_180027455
0x180027452  xor     r15d, r15d
0x180027455  mov     ecx, r15d
0x180027458  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002745d  test    r15d, r15d
0x180027460  jns     short loc_180027481
0x180027462  mov     rcx, [r13+58h]
0x180027466  test    rcx, rcx
0x180027469  jz      loc_180027B42
0x18002746f  mov     [rsp+310h+cchCount2], r15d
0x180027474  mov     dword ptr [rsp+310h+lpString2], 82Eh
0x18002747c  jmp     loc_1800273FD
0x180027481  movups  xmm0, cs:WINDLP_TRANSPORT_BITS
0x180027488  movdqu  [rbp+210h+var_260], xmm0
0x18002748d  mov     rax, [rbx]
0x180027490  lea     r8, [rsp+310h+var_298]
0x180027495  lea     rdx, [rbp+210h+var_260]
0x180027499  mov     rcx, rbx
0x18002749c  mov     rax, [rax+50h]
0x1800274a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274a5  mov     r15d, eax
0x1800274a8  test    eax, eax
0x1800274aa  jns     short loc_1800274CA
0x1800274ac  mov     rcx, [r13+58h]
0x1800274b0  test    rcx, rcx
0x1800274b3  jz      loc_180027B42
0x1800274b9  mov     [rsp+310h+cchCount2], eax
0x1800274bd  mov     dword ptr [rsp+310h+lpString2], 82Fh
0x1800274c5  jmp     loc_1800273FD
0x1800274ca  mov     rbx, [r13+60h]
0x1800274ce  test    rbx, rbx
0x1800274d1  jnz     short loc_1800274E0
0x1800274d3  mov     r15d, r12d
0x1800274d6  mov     ecx, r12d
0x1800274d9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800274de  jmp     short loc_1800274E3
0x1800274e0  xor     r15d, r15d
0x1800274e3  mov     ecx, r15d
0x1800274e6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800274eb  test    r15d, r15d
0x1800274ee  jns     short loc_18002750F
0x1800274f0  mov     rcx, [r13+58h]
0x1800274f4  test    rcx, rcx
0x1800274f7  jz      loc_180027B42
0x1800274fd  mov     [rsp+310h+cchCount2], r15d
0x180027502  mov     dword ptr [rsp+310h+lpString2], 833h
0x18002750a  jmp     loc_1800273FD
0x18002750f  mov     rax, [rbx]
0x180027512  lea     rdx, [rsp+310h+lpPathName]
0x180027517  mov     rcx, rbx
0x18002751a  mov     rax, [rax+0E8h]
0x180027521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027526  mov     r15d, eax
0x180027529  test    eax, eax
0x18002752b  jns     short loc_18002754B
0x18002752d  mov     rcx, [r13+58h]
0x180027531  test    rcx, rcx
0x180027534  jz      loc_180027B42
0x18002753a  mov     [rsp+310h+cchCount2], eax
0x18002753e  mov     dword ptr [rsp+310h+lpString2], 834h
0x180027546  jmp     loc_1800273FD
0x18002754b  lea     r9, [rbp+210h+TempFileName]; lpTempFileName
0x18002754f  xor     r8d, r8d; uUnique
0x180027552  lea     rdx, aTrc; "TRC"
0x180027559  mov     rcx, [rsp+310h+lpPathName]; lpPathName
0x18002755e  call    cs:__imp_GetTempFileNameW
0x180027564  test    eax, eax
0x180027566  jnz     short loc_1800275B6
0x180027568  call    cs:__imp_GetLastError
0x18002756e  mov     r15d, eax
0x180027571  test    eax, eax
0x180027573  jnz     short loc_18002757D
0x180027575  mov     r15d, 80004005h
0x18002757b  jmp     short loc_18002758A
0x18002757d  jle     short loc_18002758A
0x18002757f  movzx   r15d, ax
0x180027583  or      r15d, 80070000h
0x18002758a  cmp     qword ptr [r13+58h], 0
0x18002758f  jz      loc_180027B42
0x180027595  xor     ecx, ecx
0x180027597  test    r15d, r15d
0x18002759a  jns     loc_180027420
0x1800275a0  mov     [rsp+310h+cchCount2], r15d
0x1800275a5  mov     dword ptr [rsp+310h+lpString2], 838h
0x1800275ad  mov     rcx, [r13+58h]
0x1800275b1  jmp     loc_1800273FD
0x1800275b6  mov     rax, [rbx]
0x1800275b9  lea     r12, [r13+238h]
0x1800275c0  lea     r9, [rsp+310h+var_2B8]
0x1800275c5  lea     r8, [rbp+210h+TempFileName]
0x1800275c9  mov     rdx, [r12]
0x1800275cd  mov     rcx, rbx
0x1800275d0  mov     rax, [rax+58h]
0x1800275d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275d9  mov     r15d, eax
0x1800275dc  test    eax, eax
0x1800275de  jns     short loc_1800275FE
0x1800275e0  mov     rcx, [r13+58h]
0x1800275e4  test    rcx, rcx
0x1800275e7  jz      loc_180027B38
0x1800275ed  mov     [rsp+310h+cchCount2], eax
0x1800275f1  mov     dword ptr [rsp+310h+lpString2], 840h
0x1800275f9  jmp     loc_180027B10
0x1800275fe  mov     rcx, [rsp+310h+var_298]
0x180027603  mov     rax, [rcx]
0x180027606  lea     rdx, [rbp+210h+var_288]
0x18002760a  mov     qword ptr [rsp+310h+cchCount2], rdx
0x18002760f  lea     rdx, [rsp+310h+var_2B0]
0x180027614  mov     [rsp+310h+lpString2], rdx
0x180027619  lea     r9, [rsp+310h+liDistanceToMove]
0x18002761e  mov     r8, rbx
0x180027621  mov     rdx, [rsp+310h+var_2B8]
0x180027626  mov     rax, [rax+78h]
0x18002762a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002762f  mov     r15d, eax
0x180027632  mov     rcx, [r13+58h]
0x180027636  test    eax, eax
0x180027638  jns     short loc_180027654
0x18002763a  test    rcx, rcx
0x18002763d  jz      loc_180027B38
0x180027643  mov     [rsp+310h+cchCount2], eax
0x180027647  mov     dword ptr [rsp+310h+lpString2], 848h
0x18002764f  jmp     loc_180027B10
0x180027654  mov     ebx, 2
0x180027659  test    rcx, rcx
0x18002765c  jz      short loc_180027670
0x18002765e  lea     r9, [rbp+210h+TempFileName]
0x180027662  lea     r8, aRecovercryptoT; "RecoverCrypto: Transferred repair block"...
0x180027669  mov     edx, ebx
0x18002766b  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180027670  mov     rax, [rsp+310h+var_2B0]
0x180027675  cmp     [rbp+210h+var_288], rax
0x180027679  jz      short loc_1800276A0
0x18002767b  mov     r15d, 80004005h
0x180027681  mov     rcx, [r13+58h]
0x180027685  test    rcx, rcx
0x180027688  jz      loc_180027B38
0x18002768e  mov     [rsp+310h+cchCount2], r15d
0x180027693  mov     dword ptr [rsp+310h+lpString2], 84Eh
0x18002769b  jmp     loc_180027B10
0x1800276a0  mov     rcx, [rsp+310h+var_2B8]
0x1800276a5  mov     rax, [rcx]
0x1800276a8  lea     rdx, [rsp+310h+var_2C8]
0x1800276ad  mov     rax, [rax+30h]
0x1800276b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276b6  mov     r15d, eax
0x1800276b9  test    eax, eax
0x1800276bb  jns     short loc_1800276DB
0x1800276bd  mov     rcx, [r13+58h]
0x1800276c1  test    rcx, rcx
0x1800276c4  jz      loc_180027B38
0x1800276ca  mov     [rsp+310h+cchCount2], eax
0x1800276ce  mov     dword ptr [rsp+310h+lpString2], 852h
0x1800276d6  jmp     loc_180027B10
0x1800276db  mov     rax, [rsp+310h+var_2C8]
0x1800276e0  mov     [rsp+310h+cchCount2], edi; cchCount2
0x1800276e4  mov     [rsp+310h+lpString2], rax; lpString2
0x1800276e9  mov     r9d, edi; cchCount1
0x1800276ec  mov     r8, [r12]; lpString1
0x1800276f0  mov     edx, 1; dwCmpFlags
0x1800276f5  mov     ecx, 409h; Locale
0x1800276fa  call    cs:__imp_CompareStringW
0x180027700  cmp     eax, ebx
0x180027702  jz      loc_18002780F
0x180027708  mov     rcx, [r13+58h]
0x18002770c  test    rcx, rcx
0x18002770f  jz      short loc_18002772D
0x180027711  mov     rax, [rsp+310h+var_2C8]
0x180027716  mov     [rsp+310h+lpString2], rax
0x18002771b  mov     r9, [r12]
0x18002771f  lea     r8, aRecovercryptoU; "RecoverCrypto: Updating remote source p"...
0x180027726  mov     edx, ebx
0x180027728  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002772d  mov     rbx, [r12]
0x180027731  test    rbx, rbx
0x180027734  jz      short loc_18002775A
0x180027736  call    cs:__imp_GetProcessHeap
0x18002773c  mov     rcx, rax; hHeap
0x18002773f  lea     r8, [rbx-4]; lpMem
0x180027743  xor     edx, edx; dwFlags
0x180027745  call    cs:__imp_HeapFree
0x18002774b  xor     ecx, ecx
0x18002774d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180027752  mov     qword ptr [r12], 0
0x18002775a  mov     rbx, [rsp+310h+var_2C8]
0x18002775f  test    rbx, rbx
0x180027762  jnz     short loc_1800277AB
0x180027764  xor     edx, edx
0x180027766  mov     r8, r12
0x180027769  mov     rcx, rbx; Src
0x18002776c  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180027771  mov     r15d, eax
0x180027774  test    eax, eax
0x180027776  jns     short loc_18002777F
0x180027778  mov     ecx, eax
0x18002777a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002777f  mov     ecx, r15d
0x180027782  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180027787  test    r15d, r15d
0x18002778a  jns     short loc_1800277D2
0x18002778c  mov     rcx, [r13+58h]
0x180027790  test    rcx, rcx
0x180027793  jz      loc_180027B38
0x180027799  mov     [rsp+310h+cchCount2], r15d
0x18002779e  mov     dword ptr [rsp+310h+lpString2], 85Dh
0x1800277a6  jmp     loc_180027B10
0x1800277ab  mov     [rsp+310h+var_2C0], 0
0x1800277b3  test    rbx, rbx
0x1800277b6  jz      short loc_180027764
0x1800277b8  lea     rdx, [rsp+310h+var_2C0]
0x1800277bd  mov     rcx, rbx
0x1800277c0  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x1800277c5  mov     r15d, eax
0x1800277c8  test    eax, eax
0x1800277ca  js      short loc_180027778
0x1800277cc  mov     edx, [rsp+310h+var_2C0]
0x1800277d0  jmp     short loc_180027766
0x1800277d2  mov     rcx, [rbp+210h+var_290]
0x1800277d6  mov     rax, [rcx]
0x1800277d9  mov     edx, 1
0x1800277de  mov     rax, [rax+118h]
0x1800277e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277ea  mov     r15d, eax
0x1800277ed  test    eax, eax
0x1800277ef  jns     short loc_18002780F
0x1800277f1  mov     rcx, [r13+58h]
0x1800277f5  test    rcx, rcx
0x1800277f8  jz      loc_180027B38
0x1800277fe  mov     [rsp+310h+cchCount2], eax
0x180027802  mov     dword ptr [rsp+310h+lpString2], 861h
0x18002780a  jmp     loc_180027B10
0x18002780f  mov     [rsp+310h+hTemplateFile], 0; hTemplateFile
0x180027818  mov     [rsp+310h+cchCount2], 0C000000h; dwFlagsAndAttributes
0x180027820  mov     ebx, 3
0x180027825  mov     dword ptr [rsp+310h+lpString2], ebx; dwCreationDisposition
0x180027829  xor     r9d, r9d; lpSecurityAttributes
0x18002782c  mov     r8d, ebx; dwShareMode
0x18002782f  mov     edx, 80000000h; dwDesiredAccess
  ... truncated ...
```
