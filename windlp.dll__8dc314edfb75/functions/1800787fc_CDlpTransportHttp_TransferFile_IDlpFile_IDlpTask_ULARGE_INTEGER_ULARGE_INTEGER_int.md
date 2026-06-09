# CDlpTransportHttp::TransferFile(IDlpFile *,IDlpTask *,_ULARGE_INTEGER *,_ULARGE_INTEGER *,int *)

- ea: `0x1800787fc`
- end: `0x180079380`
- name: `?TransferFile@CDlpTransportHttp@@AEAAJPEAVIDlpFile@@PEAVIDlpTask@@PEAT_ULARGE_INTEGER@@2PEAH@Z`
- size: `2948`
- prototype: `__int64 __usercall@<rax>(CDlpTransportHttp *__hidden this@<rcx>, struct IDlpFile *@<rdx>, struct IDlpTask *@<r8>, union _ULARGE_INTEGER *@<r9>, union _ULARGE_INTEGER *, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180058d80`
- `0x180079390`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x180043e14`
- `0x180049fd8`
- `0x18004b054`
- `0x1800787fc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180078d9e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180078d9e`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180078afb`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180078afb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800791fb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800791fb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800791cc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800791cc`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180078b52`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180078b52`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180078ad5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180078ad5`
- `OLEAUT32!__imp_SysFreeString` at `0x18007932e`
- `OLEAUT32!__imp_SysFreeString` at `0x180079345`
- `OLEAUT32!__imp_SysFreeString` at `0x18007935c`
- `OLEAUT32!__imp_SysFreeString` at `0x18007932e`
- `OLEAUT32!__imp_SysFreeString` at `0x180079345`
- `OLEAUT32!__imp_SysFreeString` at `0x18007935c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007895b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800792ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007895b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800792ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007896c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007896c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800792dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800792dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078b05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078b5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078fd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007904a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800790b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078b05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078b5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078fd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007904a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800790b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079151`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007931e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007931e`
- `WINHTTP!WinHttpReadData` at `0x180078d21`
- `WINHTTP!WinHttpReadData` at `0x180078d21`
- `WINHTTP!WinHttpCloseHandle` at `0x1800792ec`
- `WINHTTP!WinHttpCloseHandle` at `0x180079303`
- `WINHTTP!WinHttpCloseHandle` at `0x1800792ec`
- `WINHTTP!WinHttpCloseHandle` at `0x180079303`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180078cce`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180078cce`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180079290`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180079290`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CDlpTransportHttp::TransferFile(
        CDlpTransportHttp *this,
        struct IDlpFile *a2,
        struct IDlpTask *a3,
        union _ULARGE_INTEGER *a4,
        union _ULARGE_INTEGER *a5,
        int *a6)
{
  __int64 FileW; // rsi
  void *v8; // r14
  unsigned __int64 v9; // rdi
  ULONGLONG v10; // rbx
  ULONGLONG QuadPart; // rax
  int v12; // eax
  signed int v13; // r15d
  __int64 v14; // rcx
  int v15; // eax
  HANDLE ProcessHeap; // rax
  LPVOID v17; // rax
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  DWORD v24; // eax
  signed int v25; // eax
  __int64 v26; // rcx
  signed int v27; // eax
  int v28; // eax
  __int64 v29; // rbx
  int v30; // eax
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // rcx
  int v36; // eax
  __int64 v37; // rcx
  DWORD v38; // r8d
  LONG HighPart; // eax
  __int64 v40; // rbx
  int v41; // ecx
  LONGLONG v42; // rbx
  int v43; // ecx
  int v44; // eax
  int v45; // eax
  int v46; // eax
  __int64 v47; // rcx
  signed int v48; // eax
  int v49; // eax
  signed int v50; // eax
  signed int v51; // eax
  signed int LastError; // eax
  DWORD FileAttributesW; // eax
  BOOL v54; // ebx
  HANDLE v55; // rax
  DWORD dwCreationDisposition[2]; // [rsp+28h] [rbp-B9h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+30h] [rbp-B1h]
  DWORD dwNumberOfBytesAvailable[2]; // [rsp+48h] [rbp-99h] BYREF
  union _LARGE_INTEGER v60; // [rsp+50h] [rbp-91h] BYREF
  __int64 v61; // [rsp+58h] [rbp-89h] BYREF
  union _LARGE_INTEGER v62; // [rsp+60h] [rbp-81h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp-79h] BYREF
  int v64; // [rsp+6Ch] [rbp-75h]
  HINTERNET hRequest; // [rsp+70h] [rbp-71h] BYREF
  LPCWSTR lpString2; // [rsp+78h] [rbp-69h] BYREF
  LPCWSTR lpFileName; // [rsp+80h] [rbp-61h] BYREF
  union _LARGE_INTEGER v68; // [rsp+88h] [rbp-59h] BYREF
  ULONGLONG v69; // [rsp+90h] [rbp-51h] BYREF
  DWORD dwNumberOfBytesToRead[2]; // [rsp+98h] [rbp-49h] BYREF
  LPCWSTR lpString1; // [rsp+A0h] [rbp-41h] BYREF
  __int64 v72; // [rsp+A8h] [rbp-39h]
  HINTERNET hInternet; // [rsp+B0h] [rbp-31h] BYREF
  LPVOID v74; // [rsp+B8h] [rbp-29h]
  __int64 v75; // [rsp+C0h] [rbp-21h]
  __int128 v76; // [rsp+C8h] [rbp-19h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+D8h] [rbp-9h] BYREF

  lpFileName = 0;
  lpString2 = 0;
  lpString1 = 0;
  FileW = -1;
  v75 = -1;
  hInternet = 0;
  hRequest = 0;
  v8 = 0;
  v74 = 0;
  dwNumberOfBytesAvailable[1] = 0;
  dwNumberOfBytesAvailable[0] = 0;
  NumberOfBytesWritten = 0;
  v62.QuadPart = 0;
  v60.QuadPart = 0;
  *(_QWORD *)dwNumberOfBytesToRead = 0;
  v69 = 0;
  v68.QuadPart = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  v76 = 0;
  LODWORD(v61) = 0;
  if ( !a4 || !a5 )
  {
    v9 = 0;
    v72 = 0;
    v12 = (*(__int64 (__fastcall **)(struct IDlpFile *, ULONGLONG *, union _LARGE_INTEGER *))(*(_QWORD *)a2 + 40LL))(
            a2,
            &v69,
            &v68);
    v13 = v12;
    if ( v12 >= 0 )
    {
      v10 = v69;
      v60 = v68;
      v15 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SafeSub<__int64>)(
              v69,
              (union _LARGE_INTEGER)v68.QuadPart,
              &v62);
      v13 = v15;
      if ( v15 >= 0 )
      {
        QuadPart = v62.QuadPart;
        goto LABEL_11;
      }
      v14 = *((_QWORD *)this + 12);
      if ( !v14 )
        goto LABEL_166;
      dwFlagsAndAttributes[0] = v15;
      dwCreationDisposition[0] = 1067;
    }
    else
    {
      v14 = *((_QWORD *)this + 12);
      if ( !v14 )
        goto LABEL_166;
      dwFlagsAndAttributes[0] = v12;
      dwCreationDisposition[0] = 1061;
    }
LABEL_162:
    v49 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v14,
            4u,
            (__int64)L"%s(%d): Result = 0x%X",
            L"CDlpTransportHttp::TransferFile",
            *(_QWORD *)dwCreationDisposition,
            *(_QWORD *)dwFlagsAndAttributes);
LABEL_163:
    v26 = (unsigned int)v49;
    if ( v49 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v49);
    goto LABEL_165;
  }
  v9 = 0;
  v72 = 0;
  v60 = (union _LARGE_INTEGER)a4->QuadPart;
  v10 = a5->QuadPart;
  QuadPart = a5->QuadPart;
  v62 = (union _LARGE_INTEGER)a5->QuadPart;
LABEL_11:
  v64 = 0;
  if ( QuadPart > 0x80000000 )
  {
    v62.QuadPart = 0x80000000LL;
    v64 = 1;
  }
  ProcessHeap = GetProcessHeap();
  v17 = HeapAlloc(ProcessHeap, 0, 0x8000u);
  v8 = v17;
  if ( !v17 )
  {
    v74 = 0;
    v13 = -2147024882;
    v18 = *((_QWORD *)this + 12);
    if ( !v18 )
      goto LABEL_167;
    v19 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v18,
            4u,
            (__int64)L"%s(%d): Result = 0x%X",
            L"CDlpTransportHttp::TransferFile",
            1082,
            -2147024882);
    goto LABEL_16;
  }
  v74 = v17;
  v21 = (*(__int64 (__fastcall **)(struct IDlpFile *, LPCWSTR *))(*(_QWORD *)a2 + 48LL))(a2, &lpString2);
  v13 = v21;
  if ( v21 < 0 )
  {
    v14 = *((_QWORD *)this + 12);
    if ( !v14 )
      goto LABEL_166;
    dwFlagsAndAttributes[0] = v21;
    dwCreationDisposition[0] = 1086;
    goto LABEL_162;
  }
  v22 = CDlpTransportHttp::ConnectToSourceUrl(this, a2, L"GET", &v60, &v62, &hInternet, &hRequest);
  v13 = v22;
  if ( v22 < 0 )
  {
    v14 = *((_QWORD *)this + 12);
    if ( !v14 )
      goto LABEL_166;
    dwFlagsAndAttributes[0] = v22;
    dwCreationDisposition[0] = 1095;
    goto LABEL_162;
  }
  v23 = (*(__int64 (__fastcall **)(struct IDlpFile *, LPCWSTR *))(*(_QWORD *)a2 + 56LL))(a2, &lpFileName);
  v13 = v23;
  if ( v23 < 0 )
  {
    v14 = *((_QWORD *)this + 12);
    if ( !v14 )
      goto LABEL_166;
    dwFlagsAndAttributes[0] = v23;
    dwCreationDisposition[0] = 1099;
    goto LABEL_162;
  }
  if ( !a4 || (v24 = 2, !a5) )
    v24 = 4;
  FileW = (__int64)CreateFileW(lpFileName, 0x40000000u, 5u, 0, v24, 0x8000000u, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    FileW = -1;
    v75 = -1;
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v13 = -2147467259;
    }
    if ( !*((_QWORD *)this + 12) )
      goto LABEL_166;
    v26 = 0;
    if ( v13 >= 0 )
      goto LABEL_165;
    dwFlagsAndAttributes[0] = v13;
    dwCreationDisposition[0] = 1107;
LABEL_161:
    v14 = *((_QWORD *)this + 12);
    goto LABEL_162;
  }
  v75 = FileW;
  if ( !SetFilePointerEx((HANDLE)FileW, (LARGE_INTEGER)v10, 0, 0) )
  {
    v25 = GetLastError();
    v13 = v25;
    if ( v25 )
    {
      if ( v25 > 0 )
        v13 = (unsigned __int16)v25 | 0x80070000;
    }
    else
    {
      v13 = -2147467259;
    }
    if ( !*((_QWORD *)this + 12) )
      goto LABEL_166;
    v26 = 0;
    if ( v13 >= 0 )
      goto LABEL_165;
    dwFlagsAndAttributes[0] = v13;
    dwCreationDisposition[0] = 1114;
    goto LABEL_161;
  }
  if ( !SetEndOfFile((HANDLE)FileW) )
  {
    v27 = GetLastError();
    v13 = v27;
    if ( v27 )
    {
      if ( v27 > 0 )
        v13 = (unsigned __int16)v27 | 0x80070000;
    }
    else
    {
      v13 = -2147467259;
    }
    if ( !*((_QWORD *)this + 12) )
      goto LABEL_166;
    v26 = 0;
    if ( v13 >= 0 )
      goto LABEL_165;
    dwFlagsAndAttributes[0] = v13;
    dwCreationDisposition[0] = 1115;
    goto LABEL_161;
  }
  v28 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SafeSub<__int64>)(
          (union _LARGE_INTEGER)v62.QuadPart,
          0,
          dwNumberOfBytesToRead);
  v13 = v28;
  if ( v28 < 0 )
  {
    v14 = *((_QWORD *)this + 12);
    if ( !v14 )
      goto LABEL_166;
    dwFlagsAndAttributes[0] = v28;
    dwCreationDisposition[0] = 1119;
    goto LABEL_162;
  }
  v29 = *(_QWORD *)dwNumberOfBytesToRead;
  if ( !*(_QWORD *)dwNumberOfBytesToRead )
  {
LABEL_108:
    if ( v64 )
      *a6 = 1;
    goto LABEL_166;
  }
  while ( 1 )
  {
    v30 = CDlpTransportImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownRefChainImpl<IDlpTransport>>>>::CheckUserInterruptEx(
            this,
            1,
            &v61);
    v13 = v30;
    if ( v30 < 0 )
    {
      v31 = *((_QWORD *)this + 12);
      if ( v31 )
      {
        dwFlagsAndAttributes[0] = v30;
        dwCreationDisposition[0] = 2899;
        v32 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v31,
                4u,
                (__int64)L"%s(%d): Result = 0x%X",
                L"CDlpTransportImpl<class CDlpErrorImpl<class CDlpObjectInternalImpl<class CUnknownRefChainImpl<class IDlp"
                 "Transport> > > >::CheckUserInterrupt",
                *(_QWORD *)dwCreationDisposition,
                *(_QWORD *)dwFlagsAndAttributes);
        v33 = (unsigned int)v32;
        if ( v32 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v32);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v33);
      }
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
    if ( v13 < 0 )
    {
      v14 = *((_QWORD *)this + 12);
      if ( v14 )
      {
        dwFlagsAndAttributes[0] = v13;
        dwCreationDisposition[0] = 1124;
        goto LABEL_162;
      }
      goto LABEL_166;
    }
    if ( (_DWORD)v61 == 2 )
    {
      v13 = 0;
      goto LABEL_183;
    }
    v34 = CDlpTransportImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownRefChainImpl<IDlpTransport>>>>::CheckUserInterruptEx(
            this,
            1,
            0);
    v13 = v34;
    if ( v34 < 0 )
    {
      v35 = *((_QWORD *)this + 12);
      if ( v35 )
      {
        dwFlagsAndAttributes[0] = v34;
        dwCreationDisposition[0] = 2899;
        v36 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v35,
                4u,
                (__int64)L"%s(%d): Result = 0x%X",
                L"CDlpTransportImpl<class CDlpErrorImpl<class CDlpObjectInternalImpl<class CUnknownRefChainImpl<class IDlp"
                 "Transport> > > >::CheckUserInterrupt",
                *(_QWORD *)dwCreationDisposition,
                *(_QWORD *)dwFlagsAndAttributes);
        v37 = (unsigned int)v36;
        if ( v36 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v36);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v37);
      }
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
    if ( v13 < 0 )
      break;
    dwNumberOfBytesAvailable[0] = 0;
    if ( !WinHttpQueryDataAvailable(hRequest, dwNumberOfBytesAvailable) )
    {
      v51 = GetLastError();
      v13 = v51;
      if ( v51 )
      {
        if ( v51 > 0 )
          v13 = (unsigned __int16)v51 | 0x80070000;
      }
      else
      {
        v13 = -2147467259;
      }
      if ( !*((_QWORD *)this + 12) )
        goto LABEL_166;
      v26 = 0;
      if ( v13 < 0 )
      {
        dwFlagsAndAttributes[0] = v13;
        dwCreationDisposition[0] = 1138;
        goto LABEL_129;
      }
      goto LABEL_165;
    }
    v38 = dwNumberOfBytesAvailable[0];
    if ( !dwNumberOfBytesAvailable[0] )
    {
      v13 = -2147467259;
      v47 = *((_QWORD *)this + 12);
      if ( !v47 )
        goto LABEL_167;
      dwFlagsAndAttributes[0] = -2147467259;
      dwCreationDisposition[0] = 1141;
      goto LABEL_141;
    }
    dwNumberOfBytesAvailable[1] = 0;
    if ( dwNumberOfBytesAvailable[0] > 0x8000 )
    {
      v38 = 0x8000;
      dwNumberOfBytesAvailable[0] = 0x8000;
    }
    if ( v29 < v38 )
    {
      v38 = v29;
      dwNumberOfBytesAvailable[0] = v29;
    }
    if ( !WinHttpReadData(hRequest, v8, v38, &dwNumberOfBytesAvailable[1]) )
    {
      v50 = GetLastError();
      v13 = v50;
      if ( v50 )
      {
        if ( v50 > 0 )
          v13 = (unsigned __int16)v50 | 0x80070000;
      }
      else
      {
        v13 = -2147467259;
      }
      if ( !*((_QWORD *)this + 12) )
        goto LABEL_166;
      v26 = 0;
      if ( v13 < 0 )
      {
        dwFlagsAndAttributes[0] = v13;
        dwCreationDisposition[0] = 1153;
        goto LABEL_129;
      }
LABEL_165:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v26);
      goto LABEL_166;
    }
    if ( dwNumberOfBytesAvailable[1] != dwNumberOfBytesAvailable[0] )
    {
      v13 = -2147467259;
      v47 = *((_QWORD *)this + 12);
      if ( !v47 )
        goto LABEL_167;
      dwFlagsAndAttributes[0] = -2147467259;
      dwCreationDisposition[0] = 1154;
LABEL_141:
      v19 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v47,
              4u,
              (__int64)L"%s(%d): Result = 0x%X",
              L"CDlpTransportHttp::TransferFile",
              *(_QWORD *)dwCreationDisposition,
              *(_QWORD *)dwFlagsAndAttributes);
LABEL_16:
      v20 = (unsigned int)v19;
      if ( v19 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v19);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v20);
      goto LABEL_167;
    }
    Overlapped.Internal = 0;
    Overlapped.InternalHigh = 0;
    Overlapped.hEvent = 0;
    if ( a4 && a5 )
    {
      Overlapped.Offset = v9;
LABEL_78:
      HighPart = HIDWORD(v72);
      goto LABEL_80;
    }
    Overlapped.Offset = v60.LowPart;
    if ( a4 && a5 )
      goto LABEL_78;
    HighPart = v60.HighPart;
LABEL_80:
    Overlapped.OffsetHigh = HighPart;
    if ( !WriteFile((HANDLE)FileW, v8, dwNumberOfBytesAvailable[1], &NumberOfBytesWritten, &Overlapped) )
    {
      v48 = GetLastError();
      v13 = v48;
      if ( v48 )
      {
        if ( v48 > 0 )
          v13 = (unsigned __int16)v48 | 0x80070000;
      }
      else
      {
        v13 = -2147467259;
      }
      if ( !*((_QWORD *)this + 12) )
        goto LABEL_166;
      v26 = 0;
      if ( v13 >= 0 )
        goto LABEL_165;
      dwFlagsAndAttributes[0] = v13;
      dwCreationDisposition[0] = 1166;
LABEL_129:
      v49 = CDlpLogT<CEmptyType>::DlpLogFormat(
              *((_QWORD *)this + 12),
              4u,
              (__int64)L"%s(%d): Result = 0x%X",
              L"CDlpTransportHttp::TransferFile",
              *(_QWORD *)dwCreationDisposition,
              *(_QWORD *)dwFlagsAndAttributes);
      goto LABEL_163;
    }
    if ( dwNumberOfBytesAvailable[1] != NumberOfBytesWritten )
    {
      v13 = -2147467259;
      v47 = *((_QWORD *)this + 12);
      if ( !v47 )
        goto LABEL_167;
      dwFlagsAndAttributes[0] = -2147467259;
      dwCreationDisposition[0] = 1167;
      goto LABEL_141;
    }
    v40 = v9 + dwNumberOfBytesAvailable[1];
    if ( v40 < v9 )
    {
      v40 = 0;
      v13 = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
    }
    else
    {
      v13 = 0;
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
    if ( v13 >= 0 )
    {
      if ( v40 >= 0 )
      {
        v9 = v40;
        v72 = v40;
        goto LABEL_91;
      }
      v13 = -2147024362;
      v41 = -2147024362;
    }
    else
    {
      v41 = v13;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v41);
LABEL_91:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
    if ( v13 < 0 )
    {
      v14 = *((_QWORD *)this + 12);
      if ( !v14 )
        goto LABEL_166;
      dwFlagsAndAttributes[0] = v13;
      dwCreationDisposition[0] = 1171;
      goto LABEL_162;
    }
    if ( v60.QuadPart < 0 )
    {
      v43 = -2147024809;
      v13 = -2147024809;
    }
    else
    {
      v42 = v60.QuadPart + dwNumberOfBytesAvailable[1];
      if ( (unsigned __int64)v42 < v60.QuadPart )
      {
        v42 = 0;
        v13 = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
      }
      else
      {
        v13 = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
      if ( v13 >= 0 )
      {
        if ( v42 >= 0 )
        {
          v60.QuadPart = v42;
          goto LABEL_103;
        }
        v13 = -2147024362;
        v43 = -2147024362;
      }
      else
      {
        v43 = v13;
      }
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v43);
LABEL_103:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
    if ( v13 < 0 )
    {
      v14 = *((_QWORD *)this + 12);
      if ( !v14 )
        goto LABEL_166;
      dwFlagsAndAttributes[0] = v13;
      dwCreationDisposition[0] = 1172;
      goto LABEL_162;
    }
    v44 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SafeSub<__int64>)(
            (union _LARGE_INTEGER)v62.QuadPart,
            v9,
            dwNumberOfBytesToRead);
    v13 = v44;
    if ( v44 < 0 )
    {
      v14 = *((_QWORD *)this + 12);
      if ( !v14 )
        goto LABEL_166;
      dwFlagsAndAttributes[0] = v44;
      dwCreationDisposition[0] = 1173;
      goto LABEL_162;
    }
    v45 = (*(__int64 (__fastcall **)(struct IDlpFile *, ULONGLONG *, union _LARGE_INTEGER *))(*(_QWORD *)a2 + 40LL))(
            a2,
            &v69,
            &v68);
    v13 = v45;
    if ( v45 < 0 )
    {
      v14 = *((_QWORD *)this + 12);
      if ( !v14 )
        goto LABEL_166;
      dwFlagsAndAttributes[0] = v45;
      dwCreationDisposition[0] = 1177;
      goto LABEL_162;
    }
    v68 = v60;
    v46 = (*(__int64 (__fastcall **)(char *, ULONGLONG))(*((_QWORD *)a2 + 2) + 8LL))((char *)a2 + 16, v69);
    v13 = v46;
    if ( v46 < 0 )
    {
      v14 = *((_QWORD *)this + 12);
      if ( !v14 )
        goto LABEL_166;
      dwFlagsAndAttributes[0] = v46;
      dwCreationDisposition[0] = 1182;
      goto LABEL_162;
    }
    v29 = *(_QWORD *)dwNumberOfBytesToRead;
    if ( !*(_QWORD *)dwNumberOfBytesToRead )
      goto LABEL_108;
  }
  v14 = *((_QWORD *)this + 12);
  if ( v14 )
  {
    dwFlagsAndAttributes[0] = v13;
    dwCreationDisposition[0] = 1132;
    goto LABEL_162;
  }
LABEL_166:
  if ( v13 < 0 )
  {
LABEL_167:
    if ( lpFileName )
    {
      FileAttributesW = GetFileAttributesW(lpFileName);
      v54 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      if ( v54 )
        DeleteFileW(lpFileName);
    }
    if ( (**((int (__fastcall ***)(char *, _QWORD, _QWORD))a2 + 2))((char *)a2 + 16, (unsigned int)v13, 0) >= 0
      && (unsigned int)(v61 - 1) > 1
      && (v76 = (unsigned __int64)a2, a3)
      && (*(int (__fastcall **)(char *, __int64, __int128 *))(*((_QWORD *)a3 + 2) + 24LL))((char *)a3 + 16, 65537, &v76) >= 0
      && DWORD2(v76)
      && lpString2
      && (*(int (__fastcall **)(struct IDlpFile *, LPCWSTR *))(*(_QWORD *)a2 + 48LL))(a2, &lpString1) >= 0
      && lstrcmpW(lpString1, lpString2) )
    {
      v13 = 0;
      *a6 = 1;
    }
    else
    {
      (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)a2 + 2) + 16LL))((char *)a2 + 16, 0xFFFFFFFFLL);
    }
  }
LABEL_183:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
  if ( v8 )
  {
    v55 = GetProcessHeap();
    HeapFree(v55, 0, v8);
  }
  if ( hRequest )
  {
    WinHttpCloseHandle(hRequest);
    hRequest = 0;
  }
  if ( hInternet )
  {
    WinHttpCloseHandle(hInternet);
    hInternet = 0;
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  if ( lpString1 )
  {
    SysFreeString((BSTR)lpString1);
    lpString1 = 0;
  }
  if ( lpString2 )
  {
    SysFreeString((BSTR)lpString2);
    lpString2 = 0;
  }
  if ( lpFileName )
    SysFreeString((BSTR)lpFileName);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800787fc  mov     rax, rsp
0x1800787ff  mov     [rax+8], rbx
0x180078803  mov     [rax+20h], r9
0x180078807  mov     [rax+18h], r8
0x18007880b  mov     [rax+10h], rdx
0x18007880f  push    rbp
0x180078810  push    rsi
0x180078811  push    rdi
0x180078812  push    r12
0x180078814  push    r13
0x180078816  push    r14
0x180078818  push    r15
0x18007881a  lea     rbp, [rax-4Fh]
0x18007881e  sub     rsp, 0F0h
0x180078825  mov     rbx, rdx
0x180078828  mov     r13, rcx
0x18007882b  xor     r15d, r15d
0x18007882e  mov     [rbp+47h+lpFileName], r15
0x180078832  mov     [rbp+47h+lpString2], r15
0x180078836  mov     [rbp+47h+lpString1], r15
0x18007883a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18007883e  mov     [rbp+47h+var_68], rsi
0x180078842  mov     [rbp+47h+hInternet], r15
0x180078846  mov     [rbp+47h+hRequest], r15
0x18007884a  mov     r14d, r15d
0x18007884d  mov     [rbp+47h+var_70], r15
0x180078851  mov     [rsp+120h+dwNumberOfBytesAvailable+4], r15d
0x180078856  mov     [rsp+120h+dwNumberOfBytesAvailable], r15d
0x18007885b  mov     [rbp+47h+NumberOfBytesWritten], r15d
0x18007885f  mov     qword ptr [rsp+120h+var_C8], r15
0x180078864  mov     qword ptr [rsp+120h+var_D8], r15
0x180078869  mov     qword ptr [rbp+47h+dwNumberOfBytesToRead], r15
0x18007886d  mov     [rbp+47h+var_98], r15
0x180078871  mov     [rbp+47h+var_A0], r15
0x180078875  xorps   xmm0, xmm0
0x180078878  movups  xmmword ptr [rbp+47h+Overlapped.Internal], xmm0
0x18007887c  movups  xmmword ptr [rbp+47h+Overlapped.10h], xmm0
0x180078880  movups  [rbp+47h+var_60], xmm0
0x180078884  mov     dword ptr [rsp+120h+var_D0], r15d
0x180078889  mov     r12, [rbp+47h+arg_20]
0x18007888d  test    r9, r9
0x180078890  jz      short loc_1800788B7
0x180078892  test    r12, r12
0x180078895  jz      short loc_1800788B7
0x180078897  mov     edi, r15d
0x18007889a  mov     [rbp+47h+var_80], r15
0x18007889e  mov     rax, [r9]
0x1800788a1  mov     qword ptr [rsp+120h+var_D8], rax
0x1800788a6  mov     rbx, [r12]
0x1800788aa  mov     rax, rbx
0x1800788ad  mov     qword ptr [rsp+120h+var_C8], rbx
0x1800788b2  jmp     loc_180078941
0x1800788b7  mov     rdi, r15
0x1800788ba  mov     [rbp+47h+var_80], r15
0x1800788be  mov     rax, [rdx]
0x1800788c1  lea     r8, [rbp+47h+var_A0]
0x1800788c5  lea     rdx, [rbp+47h+var_98]
0x1800788c9  mov     rcx, rbx
0x1800788cc  mov     rax, [rax+28h]
0x1800788d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800788d5  mov     r15d, eax
0x1800788d8  test    eax, eax
0x1800788da  jns     short loc_1800788FA
0x1800788dc  mov     rcx, [r13+60h]
0x1800788e0  test    rcx, rcx
0x1800788e3  jz      loc_1800791BA
0x1800788e9  mov     [rsp+120h+dwFlagsAndAttributes], eax
0x1800788ed  mov     [rsp+120h+dwCreationDisposition], 425h
0x1800788f5  jmp     loc_180079192
0x1800788fa  mov     rbx, [rbp+47h+var_98]
0x1800788fe  mov     rdx, [rbp+47h+var_A0]
0x180078902  mov     qword ptr [rsp+120h+var_D8], rdx
0x180078907  lea     r8, [rsp+120h+var_C8]
0x18007890c  mov     rcx, rbx
0x18007890f  call    ??$SafeSub@_J@@YAJ_J0PEA_J@Z; SafeSub<__int64>(__int64,__int64,__int64 *)
0x180078914  mov     r15d, eax
0x180078917  test    eax, eax
0x180078919  jns     short loc_180078939
0x18007891b  mov     rcx, [r13+60h]
0x18007891f  test    rcx, rcx
0x180078922  jz      loc_1800791BA
0x180078928  mov     [rsp+120h+dwFlagsAndAttributes], eax
0x18007892c  mov     [rsp+120h+dwCreationDisposition], 42Bh
0x180078934  jmp     loc_180079192
0x180078939  mov     rax, qword ptr [rsp+120h+var_C8]
0x18007893e  xor     r15d, r15d
0x180078941  mov     [rbp+47h+var_BC], r15d
0x180078945  mov     ecx, 80000000h
0x18007894a  cmp     rax, rcx
0x18007894d  jbe     short loc_18007895B
0x18007894f  mov     qword ptr [rsp+120h+var_C8], rcx
0x180078954  mov     [rbp+47h+var_BC], 1
0x18007895b  call    cs:__imp_GetProcessHeap
0x180078961  mov     rcx, rax; hHeap
0x180078964  xor     edx, edx; dwFlags
0x180078966  mov     r8d, 8000h; dwBytes
0x18007896c  call    cs:__imp_HeapAlloc
0x180078972  mov     r14, rax
0x180078975  test    rax, rax
0x180078978  jnz     short loc_1800789CB
0x18007897a  mov     [rbp+47h+var_70], rax
0x18007897e  mov     r15d, 8007000Eh
0x180078984  mov     rcx, [r13+60h]
0x180078988  test    rcx, rcx
0x18007898b  jz      loc_1800791C3
0x180078991  mov     [rsp+120h+dwFlagsAndAttributes], r15d
0x180078996  mov     [rsp+120h+dwCreationDisposition], 43Ah
0x18007899e  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800789a5  lea     r9, aCdlptransporth_0; "CDlpTransportHttp::TransferFile"
0x1800789ac  mov     edx, 4
0x1800789b1  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800789b6  test    eax, eax
0x1800789b8  mov     ecx, eax
0x1800789ba  jns     short loc_1800789C1
0x1800789bc  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800789c1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800789c6  jmp     loc_1800791C3
0x1800789cb  mov     [rbp+47h+var_70], r14
0x1800789cf  mov     rcx, [rbp+47h+arg_8]
0x1800789d3  mov     rax, [rcx]
0x1800789d6  lea     rdx, [rbp+47h+lpString2]
0x1800789da  mov     rax, [rax+30h]
0x1800789de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800789e3  mov     r15d, eax
0x1800789e6  test    eax, eax
0x1800789e8  jns     short loc_180078A08
0x1800789ea  mov     rcx, [r13+60h]
0x1800789ee  test    rcx, rcx
0x1800789f1  jz      loc_1800791BA
0x1800789f7  mov     [rsp+120h+dwFlagsAndAttributes], eax
0x1800789fb  mov     [rsp+120h+dwCreationDisposition], 43Eh
0x180078a03  jmp     loc_180079192
0x180078a08  lea     rax, [rbp+47h+hRequest]
0x180078a0c  mov     qword ptr [rsp+120h+dwFlagsAndAttributes+8], rax; void **
0x180078a11  lea     rax, [rbp+47h+hInternet]
0x180078a15  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rax; void **
0x180078a1a  lea     rax, [rsp+120h+var_C8]
0x180078a1f  mov     qword ptr [rsp+120h+dwCreationDisposition], rax; union _LARGE_INTEGER *
0x180078a24  lea     r9, [rsp+120h+var_D8]; union _LARGE_INTEGER *
0x180078a29  lea     r8, aGet; "GET"
0x180078a30  mov     rdx, [rbp+47h+arg_8]; struct IDlpFile *
0x180078a34  mov     rcx, r13; this
0x180078a37  call    ?ConnectToSourceUrl@CDlpTransportHttp@@AEAAJPEAVIDlpFile@@PEBGPEAT_LARGE_INTEGER@@2PEAPEAX3@Z; CDlpTransportHttp::ConnectToSourceUrl(IDlpFile *,ushort const *,_LARGE_INTEGER *,_LARGE_INTEGER *,void * *,void * *)
0x180078a3c  mov     r15d, eax
0x180078a3f  test    eax, eax
0x180078a41  jns     short loc_180078A61
0x180078a43  mov     rcx, [r13+60h]
0x180078a47  test    rcx, rcx
0x180078a4a  jz      loc_1800791BA
0x180078a50  mov     [rsp+120h+dwFlagsAndAttributes], eax
0x180078a54  mov     [rsp+120h+dwCreationDisposition], 447h
0x180078a5c  jmp     loc_180079192
0x180078a61  mov     rcx, [rbp+47h+arg_8]
0x180078a65  mov     rax, [rcx]
0x180078a68  lea     rdx, [rbp+47h+lpFileName]
0x180078a6c  mov     rax, [rax+38h]
0x180078a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078a75  mov     r15d, eax
0x180078a78  test    eax, eax
0x180078a7a  jns     short loc_180078A9A
0x180078a7c  mov     rcx, [r13+60h]
0x180078a80  test    rcx, rcx
0x180078a83  jz      loc_1800791BA
0x180078a89  mov     [rsp+120h+dwFlagsAndAttributes], eax
0x180078a8d  mov     [rsp+120h+dwCreationDisposition], 44Bh
0x180078a95  jmp     loc_180079192
0x180078a9a  cmp     [rbp+47h+arg_18], 0
0x180078a9f  jz      short loc_180078AAB
0x180078aa1  test    r12, r12
0x180078aa4  mov     eax, 2
0x180078aa9  jnz     short loc_180078AB0
0x180078aab  mov     eax, 4
0x180078ab0  mov     qword ptr [rsp+120h+dwFlagsAndAttributes+8], 0; hTemplateFile
0x180078ab9  mov     [rsp+120h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180078ac1  mov     [rsp+120h+dwCreationDisposition], eax; dwCreationDisposition
0x180078ac5  xor     r9d, r9d; lpSecurityAttributes
0x180078ac8  mov     edx, 40000000h; dwDesiredAccess
0x180078acd  lea     r8d, [r9+5]; dwShareMode
0x180078ad1  mov     rcx, [rbp+47h+lpFileName]; lpFileName
0x180078ad5  call    cs:__imp_CreateFileW
0x180078adb  mov     rsi, rax
0x180078ade  dec     rax
0x180078ae1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180078ae5  ja      loc_180079149
0x180078aeb  mov     [rbp+47h+var_68], rsi
0x180078aef  xor     r9d, r9d; dwMoveMethod
0x180078af2  xor     r8d, r8d; lpNewFilePointer
0x180078af5  mov     rdx, rbx; liDistanceToMove
0x180078af8  mov     rcx, rsi; hFile
0x180078afb  call    cs:__imp_SetFilePointerEx
0x180078b01  test    eax, eax
0x180078b03  jnz     short loc_180078B4F
0x180078b05  call    cs:__imp_GetLastError
0x180078b0b  mov     r15d, eax
0x180078b0e  test    eax, eax
0x180078b10  jnz     short loc_180078B1A
0x180078b12  mov     r15d, 80004005h
0x180078b18  jmp     short loc_180078B27
0x180078b1a  jle     short loc_180078B27
0x180078b1c  movzx   r15d, ax
0x180078b20  or      r15d, 80070000h
0x180078b27  cmp     qword ptr [r13+60h], 0
0x180078b2c  jz      loc_1800791BA
0x180078b32  xor     ecx, ecx
0x180078b34  test    r15d, r15d
0x180078b37  jns     loc_1800791B5
0x180078b3d  mov     [rsp+120h+dwFlagsAndAttributes], r15d
0x180078b42  mov     [rsp+120h+dwCreationDisposition], 45Ah
0x180078b4a  jmp     loc_18007918E
0x180078b4f  mov     rcx, rsi; hFile
0x180078b52  call    cs:__imp_SetEndOfFile
0x180078b58  test    eax, eax
0x180078b5a  jnz     short loc_180078BA6
0x180078b5c  call    cs:__imp_GetLastError
0x180078b62  mov     r15d, eax
0x180078b65  test    eax, eax
0x180078b67  jnz     short loc_180078B71
0x180078b69  mov     r15d, 80004005h
0x180078b6f  jmp     short loc_180078B7E
0x180078b71  jle     short loc_180078B7E
0x180078b73  movzx   r15d, ax
0x180078b77  or      r15d, 80070000h
0x180078b7e  cmp     qword ptr [r13+60h], 0
0x180078b83  jz      loc_1800791BA
0x180078b89  xor     ecx, ecx
0x180078b8b  test    r15d, r15d
0x180078b8e  jns     loc_1800791B5
0x180078b94  mov     [rsp+120h+dwFlagsAndAttributes], r15d
0x180078b99  mov     [rsp+120h+dwCreationDisposition], 45Bh
0x180078ba1  jmp     loc_18007918E
0x180078ba6  lea     r8, [rbp+47h+dwNumberOfBytesToRead]
0x180078baa  xor     edx, edx
0x180078bac  mov     rcx, qword ptr [rsp+120h+var_C8]
0x180078bb1  call    ??$SafeSub@_J@@YAJ_J0PEA_J@Z; SafeSub<__int64>(__int64,__int64,__int64 *)
0x180078bb6  mov     r15d, eax
0x180078bb9  test    eax, eax
0x180078bbb  jns     short loc_180078BDB
0x180078bbd  mov     rcx, [r13+60h]
0x180078bc1  test    rcx, rcx
0x180078bc4  jz      loc_1800791BA
0x180078bca  mov     [rsp+120h+dwFlagsAndAttributes], eax
0x180078bce  mov     [rsp+120h+dwCreationDisposition], 45Fh
0x180078bd6  jmp     loc_180079192
0x180078bdb  mov     rbx, qword ptr [rbp+47h+dwNumberOfBytesToRead]
0x180078bdf  test    rbx, rbx
0x180078be2  jz      loc_180078F0A
0x180078be8  lea     r12, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180078bef  lea     r8, [rsp+120h+var_D0]
0x180078bf4  mov     edx, 1
0x180078bf9  mov     rcx, r13
0x180078bfc  call    ?CheckUserInterruptEx@?$CDlpTransportImpl@V?$CDlpErrorImpl@V?$CDlpObjectInternalImpl@V?$CUnknownRefChainImpl@VIDlpTransport@@@@@@@@@@QEAAJHPEAW4WINDLP_INTERRUPT_REASON@@@Z; CDlpTransportImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownRefChainImpl<IDlpTransport>>>>::CheckUserInterruptEx(int,WINDLP_INTERRUPT_REASON *)
0x180078c01  mov     r15d, eax
0x180078c04  test    eax, eax
0x180078c06  jns     short loc_180078C41
0x180078c08  mov     rcx, [r13+60h]
0x180078c0c  test    rcx, rcx
0x180078c0f  jz      short loc_180078C41
0x180078c11  mov     [rsp+120h+dwFlagsAndAttributes], eax
0x180078c15  mov     [rsp+120h+dwCreationDisposition], 0B53h
0x180078c1d  lea     r9, aCdlptransporti_2; "CDlpTransportImpl<class CDlpErrorImpl<c"...
0x180078c24  mov     r8, r12
0x180078c27  mov     edx, 4
0x180078c2c  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180078c31  mov     ecx, eax
0x180078c33  test    eax, eax
0x180078c35  jns     short loc_180078C3C
0x180078c37  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180078c3c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180078c41  mov     ecx, r15d
0x180078c44  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180078c49  test    r15d, r15d
0x180078c4c  js      loc_18007912A
0x180078c52  cmp     dword ptr [rsp+120h+var_D0], 2
0x180078c57  jz      loc_180079122
0x180078c5d  xor     r8d, r8d
0x180078c60  lea     edx, [r8+1]
0x180078c64  mov     rcx, r13
0x180078c67  call    ?CheckUserInterruptEx@?$CDlpTransportImpl@V?$CDlpErrorImpl@V?$CDlpObjectInternalImpl@V?$CUnknownRefChainImpl@VIDlpTransport@@@@@@@@@@QEAAJHPEAW4WINDLP_INTERRUPT_REASON@@@Z; CDlpTransportImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownRefChainImpl<IDlpTransport>>>>::CheckUserInterruptEx(int,WINDLP_INTERRUPT_REASON *)
0x180078c6c  mov     r15d, eax
0x180078c6f  test    eax, eax
0x180078c71  jns     short loc_180078CAC
0x180078c73  mov     rcx, [r13+60h]
0x180078c77  test    rcx, rcx
0x180078c7a  jz      short loc_180078CAC
0x180078c7c  mov     [rsp+120h+dwFlagsAndAttributes], eax
0x180078c80  mov     [rsp+120h+dwCreationDisposition], 0B53h
0x180078c88  lea     r9, aCdlptransporti_2; "CDlpTransportImpl<class CDlpErrorImpl<c"...
0x180078c8f  mov     r8, r12
0x180078c92  mov     edx, 4
0x180078c97  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180078c9c  mov     ecx, eax
0x180078c9e  test    eax, eax
0x180078ca0  jns     short loc_180078CA7
0x180078ca2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180078ca7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180078cac  mov     ecx, r15d
0x180078caf  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180078cb4  test    r15d, r15d
0x180078cb7  js      loc_180079103
0x180078cbd  mov     [rsp+120h+dwNumberOfBytesAvailable], 0
  ... truncated ...
```
