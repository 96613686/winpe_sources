# CINetFile::INetAsyncOpen(void)

- ea: `0x18004efc0`
- end: `0x18004fe07`
- name: `?INetAsyncOpen@CINetFile@@UEAAJXZ`
- size: `3655`
- prototype: `__int64 __fastcall(CINetFile *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800162d4`
- `0x18004d734`
- `0x18004e9f4`
- `0x18004ee30`
- `0x18004efc0`
- `0x18004fe10`
- `0x18004fffc`
- `0x180050338`
- `0x18006261c`
- `0x180062764`
- `0x1800627c8`
- `0x180075bc8`
- `0x1800806c0`
- `0x1800a50b0`
- `0x1801285fe`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `msvcrt!_ui64tow_s` at `0x18004f9be`
- `msvcrt!_ui64tow_s` at `0x18004f9be`
- `iertutil!__imp_GetExtValue` at `0x18004faab`
- `iertutil!__imp_GetExtValue` at `0x18004faab`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18004f8e3`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18004f8e3`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18004eff5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18004fa2d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18004eff5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18004fa2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f04e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f1c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f44e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f5bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f736`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f04e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f1c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f44e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f5bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f736`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f02a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f1a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f424`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f596`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f713`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f02a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f1a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f424`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f596`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f713`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x18004fde0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x18004fde0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004f24e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004f24e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004f6e6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004f6e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fda2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fdc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fda2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fdc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fc6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fc6a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18004f475`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18004f475`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004f0a5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004f0a5`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18004fc44`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18004fc44`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004fc11`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004fc11`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004f106`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004f106`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18004f7bb`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18004f7f1`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18004f82b`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18004f865`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18004f7bb`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18004f7f1`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18004f82b`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18004f865`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f299`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f299`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f40a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f76d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fcc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f40a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f76d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fcc8`
- `WININET!InternetSetOptionW` at `0x18004fd28`
- `WININET!InternetSetOptionW` at `0x18004fd78`
- `WININET!InternetSetOptionW` at `0x18004fd28`
- `WININET!InternetSetOptionW` at `0x18004fd78`

## pseudocode

```c
__int64 __fastcall CINetFile::INetAsyncOpen(CINetFile *this)
{
  char Bool; // al
  const OLECHAR *v3; // rdx
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  const OLECHAR *v5; // r14
  __int64 v6; // rbx
  _WORD *v7; // r14
  DWORD FileAttributesW; // eax
  unsigned __int64 v9; // rdx
  __int64 v10; // rbx
  __int64 v11; // rax
  unsigned __int64 v12; // rcx
  bool v13; // cf
  const WCHAR *v14; // r15
  unsigned __int64 i; // rbx
  __int64 v16; // r12
  const WCHAR *v17; // rax
  __int64 v18; // rbx
  unsigned __int64 v19; // rbx
  SIZE_T v20; // r13
  _WORD *v21; // rax
  _WORD *v22; // r14
  __int64 v23; // rcx
  wchar_t *v24; // rdx
  _WORD *v25; // rax
  _WORD *v26; // rcx
  signed int ExtValue; // ebx
  WCHAR *v28; // rax
  WCHAR *v29; // r8
  __int64 v30; // rdx
  __int64 v31; // r9
  WCHAR *v32; // rcx
  WCHAR *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r13
  __int64 v36; // rcx
  int v37; // ebx
  unsigned int v39; // ebx
  unsigned __int64 v40; // r15
  unsigned __int64 v41; // r12
  struct IInternetProtocolSink *RefCountedSink; // r14
  char v43; // cl
  unsigned __int64 v44; // rax
  __int64 v45; // r9
  unsigned __int64 v46; // r12
  struct IInternetProtocolSink *RefCountedSinkNoLock; // rbx
  unsigned __int64 v48; // r14
  int v49; // r15d
  unsigned int v50; // r15d
  struct IInternetProtocolSink *v51; // rdi
  char v52; // al
  unsigned __int64 v53; // rcx
  unsigned __int16 *v54; // r14
  struct IInternetProtocolSink *v55; // rbx
  unsigned __int16 *v56; // rdx
  int v57; // r8d
  int v58; // r9d
  const WCHAR *v59; // rcx
  DWORD v60; // r9d
  const WCHAR *v61; // rcx
  DWORD v62; // r9d
  const WCHAR *v63; // rcx
  DWORD v64; // r9d
  const WCHAR *v65; // rcx
  DWORD v66; // r9d
  int IsFeatureEnabledInternal; // eax
  int v68; // eax
  struct IInternetBindInfo *RefCountedBindInfo; // r15
  unsigned int v70; // r15d
  bool v71; // zf
  int v72; // edx
  int v73; // ecx
  int v74; // eax
  __int64 v75; // rcx
  __int64 v76; // rcx
  int v77; // eax
  const WCHAR *v78; // rax
  HANDLE FileW; // rax
  void *v80; // rbx
  LPVOID v81; // rax
  enum tagBINDSTATUS v82; // edx
  void *v83; // rcx
  DWORD LastError; // ebx
  const WCHAR *ObjectNameW; // rax
  int lpString2; // [rsp+20h] [rbp-E0h]
  DWORD Buffer; // [rsp+50h] [rbp-B0h] BYREF
  char v88; // [rsp+54h] [rbp-ACh]
  DWORD pcchPath; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v91; // [rsp+68h] [rbp-98h]
  HANDLE hFindFile; // [rsp+70h] [rbp-90h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF
  CHAR MultiByteStr[2]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR WideCharStr[264]; // [rsp+3E0h] [rbp+2E0h] BYREF

  Bool = IEConfiguration_GetBool(536870927);
  v3 = (const OLECHAR *)*((_QWORD *)this + 32);
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 488);
  v88 = Bool;
  v5 = &pszFormat;
  v6 = 0;
  if ( v3 )
    v5 = v3;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  if ( ((*((_DWORD *)this + 132) - 13) & 0xFFFFFFFD) != 0 )
  {
    v75 = *((_QWORD *)this + 55);
    if ( v75 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 8LL))(v75);
    v6 = *((_QWORD *)this + 55);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  if ( v6 )
  {
    (*(void (__fastcall **)(CINetFile *, __int64, __int64, const OLECHAR *))(*(_QWORD *)this + 440LL))(this, v6, 11, v5);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  v7 = (_WORD *)((char *)this + 1096);
  if ( !*((_WORD *)this + 548) )
  {
    v59 = (const WCHAR *)*((_QWORD *)this + 20);
    v60 = (*((_DWORD *)this + 189) & 0x800) << 7;
    pcchPath = 260;
    PathCreateFromUrlW(v59, (PWSTR)this + 548, &pcchPath, v60);
  }
  FileAttributesW = GetFileAttributesW((LPCWSTR)this + 548);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    if ( LastError == 2 )
    {
      ObjectNameW = CINetFile::GetObjectNameW(this);
      if ( PathIsUNCServerW(ObjectNameW) )
        LastError = 123;
    }
    *((_DWORD *)this + 178) = LastError;
    v37 = -2146697211;
    goto LABEL_186;
  }
  if ( (FileAttributesW & 0x10) != 0 )
  {
    v37 = -2146697195;
    goto LABEL_186;
  }
  if ( FCK::FEATURE_FILEPROTOCOL_NOFINDFIRST_KB947853 )
  {
    IsFeatureEnabledInternal = CoInternetIsFeatureEnabledInternal();
    if ( IsFeatureEnabledInternal < 0 )
    {
LABEL_12:
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      if ( !*v7 )
      {
        v61 = (const WCHAR *)*((_QWORD *)this + 20);
        v62 = (*((_DWORD *)this + 189) & 0x800) << 7;
        pcchPath = 260;
        PathCreateFromUrlW(v61, (PWSTR)this + 548, &pcchPath, v62);
      }
      hFindFile = FindFirstFileW((LPCWSTR)this + 548, &FindFileData);
      if ( hFindFile != (HANDLE)-1LL )
      {
        v9 = FindFileData.nFileSizeLow | ((unsigned __int64)FindFileData.nFileSizeHigh << 32);
        v91 = 1;
        *((_QWORD *)this + 48) = v9;
        *((_QWORD *)this + 49) = v9;
        pcchPath = 1;
        goto LABEL_16;
      }
      goto LABEL_180;
    }
    dword_180166F48 = IsFeatureEnabledInternal == 0;
    FCK::FEATURE_FILEPROTOCOL_NOFINDFIRST_KB947853 = 0;
  }
  if ( !dword_180166F48 )
    goto LABEL_12;
  v78 = CINetFile::GetObjectNameW(this);
  v91 = 1;
  FileW = CreateFileW(v78, 0x80u, 1u, 0, 3u, 0x80u, 0);
  v80 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
LABEL_180:
    *((_DWORD *)this + 178) = GetLastError();
    v37 = -2146697209;
LABEL_186:
    *((_DWORD *)this + 25) = v37;
    return (unsigned int)v37;
  }
  pcchPath = 0;
  hFindFile = (HANDLE)-1LL;
  pv = 0;
  if ( GetFileSizeEx(FileW, (PLARGE_INTEGER)&pv) )
  {
    v81 = pv;
    *((_QWORD *)this + 48) = pv;
    *((_QWORD *)this + 49) = v81;
  }
  CloseHandle(v80);
LABEL_16:
  if ( *((_QWORD *)this + 48) >= 0xFFEFFFFF || *((_QWORD *)this + 49) >= 0xFFEFFFFF )
  {
    v37 = 0;
    RefCountedBindInfo = CINet::GetRefCountedBindInfo(this, v9);
    if ( !(unsigned int)CINet::IsDownloading64BitEnabled(this, RefCountedBindInfo) )
    {
      v37 = -2146697208;
      *((_DWORD *)this + 25) = -2146697208;
    }
    ((void (__fastcall *)(struct IInternetBindInfo *))RefCountedBindInfo->lpVtbl->Release)(RefCountedBindInfo);
    if ( v37 < 0 )
      goto LABEL_72;
  }
  if ( (*((_DWORD *)this + 189) & 0x400000) != 0 )
  {
    _ui64tow_s(*((_QWORD *)this + 48), (wchar_t *)MultiByteStr, 0x44u, 10);
    CINet::ReportNotificationW(this, BINDSTATUS_RESERVED_6, (const unsigned __int16 *)MultiByteStr);
  }
  if ( !*v7 )
  {
    v63 = (const WCHAR *)*((_QWORD *)this + 20);
    v64 = (*((_DWORD *)this + 189) & 0x800) << 7;
    Buffer = 260;
    PathCreateFromUrlW(v63, (PWSTR)this + 548, &Buffer, v64);
  }
  if ( !(unsigned int)DoesPathAccessDosDevice((const unsigned __int16 *)this + 548) )
  {
    if ( !*v7 )
    {
      v65 = (const WCHAR *)*((_QWORD *)this + 20);
      v66 = (*((_DWORD *)this + 189) & 0x800) << 7;
      Buffer = 260;
      PathCreateFromUrlW(v65, (PWSTR)this + 548, &Buffer, v66);
    }
    v10 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
    if ( ((*((_DWORD *)this + 132) - 13) & 0xFFFFFFFD) != 0 )
    {
      v76 = *((_QWORD *)this + 55);
      if ( v76 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 8LL))(v76);
      v10 = *((_QWORD *)this + 55);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
    if ( v10 )
    {
      (*(void (__fastcall **)(CINetFile *, __int64, __int64, char *))(*(_QWORD *)this + 440LL))(
        this,
        v10,
        14,
        (char *)this + 1096);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    v11 = -1;
    do
      ++v11;
    while ( v7[v11] );
    v12 = (unsigned __int64)&v7[v11];
    if ( v12 )
    {
      v12 -= 2LL;
      v13 = (unsigned __int64)v7 < v12;
      if ( (unsigned __int64)v7 <= v12 )
      {
        do
        {
          if ( *(_WORD *)v12 != 46 && *(_WORD *)v12 != 32 )
            break;
          *(_WORD *)v12 = 0;
          v12 -= 2LL;
        }
        while ( v12 >= (unsigned __int64)v7 );
        v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 488);
        while ( 1 )
        {
          v13 = (unsigned __int64)v7 < v12;
          if ( (unsigned __int64)v7 > v12 )
            break;
          if ( *(_WORD *)v12 == 46 )
            goto LABEL_31;
          if ( *(_WORD *)v12 == 92 || *(_WORD *)v12 == 47 )
          {
            v14 = 0;
            goto LABEL_33;
          }
          v12 -= 2LL;
        }
      }
    }
    else
    {
LABEL_31:
      v13 = (unsigned __int64)v7 < v12;
    }
    v14 = (const WCHAR *)(v12 & -(__int64)v13);
LABEL_33:
    if ( !v14 )
    {
LABEL_68:
      v35 = 0;
      EnterCriticalSection(v4);
      v36 = *((_QWORD *)this + 55);
      if ( v36 )
      {
        v35 = *((_QWORD *)this + 55);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
      }
      LeaveCriticalSection(v4);
      if ( !v35 )
        goto LABEL_71;
      *((_DWORD *)this + 108) |= 4u;
      v39 = *((_DWORD *)this + 108);
      if ( (*((_DWORD *)this + 188) & 0x100000) != 0 )
      {
        v39 |= 0x20u;
        *((_DWORD *)this + 108) = v39;
      }
      v40 = *((_QWORD *)this + 48);
      v41 = *((_QWORD *)this + 49);
      RefCountedSink = CINet::GetRefCountedSink(this);
      if ( RefCountedSink )
      {
        v43 = *((_BYTE *)this + 994);
        v44 = v40;
        if ( v41 > v40 )
          v44 = v41;
        if ( (v43 & 8) == 0 && v44 >= 0x7FFFFFFF )
        {
          Buffer = 18000000;
          *((_BYTE *)this + 994) = v43 | 8;
          InternetSetOptionW(*((HINTERNET *)this + 44), 6u, &Buffer, 4u);
        }
        if ( v40 >= 0xFFEFFFFF || v41 >= 0xFFEFFFFF )
        {
          *(_WORD *)MultiByteStr = 0;
          v39 |= 0x40u;
          v68 = StringCchPrintfW((unsigned __int16 *)MultiByteStr, 0x80u, L"%I64u,%I64u", v41, v40);
          LODWORD(v40) = 0;
          if ( v68 >= 0 )
            CINet::ReportNotificationW(this, BINDSTATUS_64BIT_PROGRESS, (const unsigned __int16 *)MultiByteStr);
          v45 = 0;
        }
        else
        {
          v45 = (unsigned int)v41;
        }
        (*(void (__fastcall **)(CINetFile *, struct IInternetProtocolSink *, _QWORD, __int64, _DWORD))(*(_QWORD *)this + 448LL))(
          this,
          RefCountedSink,
          v39,
          v45,
          v40);
        ((void (__fastcall *)(struct IInternetProtocolSink *))RefCountedSink->lpVtbl->Release)(RefCountedSink);
      }
      v46 = *((_QWORD *)this + 48);
      RefCountedSinkNoLock = 0;
      v48 = *((_QWORD *)this + 49);
      v49 = 0;
      EnterCriticalSection(v4);
      if ( ((*((_DWORD *)this + 132) - 13) & 0xFFFFFFFD) == 0 )
      {
        LODWORD(v91) = 0;
LABEL_89:
        LeaveCriticalSection(v4);
        if ( RefCountedSinkNoLock )
        {
          if ( v49 )
          {
            v50 = *((_DWORD *)this + 108);
            *((_QWORD *)this + 53) = v48;
            v51 = CINet::GetRefCountedSink(this);
            if ( v51 )
            {
              v52 = *((_BYTE *)this + 994);
              v53 = v46;
              if ( v48 > v46 )
                v53 = v48;
              if ( (v52 & 8) == 0 && v53 >= 0x7FFFFFFF )
              {
                v83 = (void *)*((_QWORD *)this + 44);
                Buffer = 18000000;
                *((_BYTE *)this + 994) = v52 | 8;
                InternetSetOptionW(v83, 6u, &Buffer, 4u);
              }
              if ( v46 >= 0xFFEFFFFF || v48 >= 0xFFEFFFFF )
              {
                *(_WORD *)MultiByteStr = 0;
                v70 = v50 | 0x40;
                if ( (int)StringCchPrintfW((unsigned __int16 *)MultiByteStr, 0x80u, L"%I64u,%I64u", v48, v46) >= 0 )
                  CINet::ReportNotificationW(this, BINDSTATUS_64BIT_PROGRESS, (const unsigned __int16 *)MultiByteStr);
                (*(void (__fastcall **)(CINetFile *, struct IInternetProtocolSink *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)this + 448LL))(
                  this,
                  v51,
                  v70,
                  0,
                  0);
              }
              else
              {
                (*(void (__fastcall **)(CINetFile *, struct IInternetProtocolSink *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)this + 448LL))(
                  this,
                  v51,
                  v50,
                  (unsigned int)v48,
                  v46);
              }
              ((void (__fastcall *)(struct IInternetProtocolSink *))v51->lpVtbl->Release)(v51);
            }
          }
          if ( (_DWORD)v91 )
            (*(void (__fastcall **)(CINetFile *, struct IInternetProtocolSink *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 456LL))(
              this,
              RefCountedSinkNoLock,
              0,
              *((unsigned int *)this + 178),
              0);
          ((void (__fastcall *)(struct IInternetProtocolSink *))RefCountedSinkNoLock->lpVtbl->Release)(RefCountedSinkNoLock);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
LABEL_71:
        *((_DWORD *)this + 25) = -2146828287;
        v37 = 0;
        goto LABEL_72;
      }
      *((_DWORD *)this + 116) = 0;
      *((_DWORD *)this + 132) = 13;
      if ( !v48 )
      {
        v48 = *((_QWORD *)this + 49);
        v46 = *((_QWORD *)this + 48);
      }
      if ( v48 == *((_QWORD *)this + 53) && (v48 || v46) || (*((_DWORD *)this + 188) & 0x100000) == 0 )
      {
        v77 = *((_DWORD *)this + 108);
        if ( (v77 & 4) != 0 || (*((_DWORD *)this + 207) & 0x100000) != 0 )
          goto LABEL_156;
        *((_DWORD *)this + 108) = v77 | 4;
      }
      else
      {
        *((_DWORD *)this + 108) |= 4u;
      }
      v49 = 1;
LABEL_156:
      RefCountedSinkNoLock = CINet::GetRefCountedSinkNoLock(this);
      goto LABEL_89;
    }
    pv = 0;
    for ( i = 0; i < 7; ++i )
    {
      v16 = 2 * i;
      v17 = off_18012D020[2 * i];
      if ( v17 && CompareStringW(0x7Fu, 0x1001u, v14, -1, v17, -1) == 2 )
      {
        v18 = -1;
        do
          ++v18;
        while ( off_18012D020[v16 + 1][v18] );
        v19 = v18 + 1;
        v20 = saturated_mul(v19, 2u);
        v21 = CoTaskMemAlloc(v20);
        v22 = v21;
        if ( v21 )
        {
          memset_0(v21, 0, v20);
          _mm_lfence();
          if ( v19 )
          {
            if ( v19 > 0x7FFFFFFF )
            {
              *v22 = 0;
            }
            else
            {
              v23 = 2147483646;
              v24 = off_18012D020[v16 + 1];
              v25 = v22;
              do
              {
                if ( !v23 )
                  break;
                if ( !*v24 )
                  break;
                *v25++ = *v24++;
                --v23;
                --v19;
              }
              while ( v19 );
              v26 = v25 - 1;
              if ( v19 )
                v26 = v25;
              *v26 = 0;
            }
          }
          goto LABEL_53;
        }
        break;
      }
    }
    if ( (unsigned __int8)IEConfiguration_GetBool(536870927) && (int)FindMimeTypeInMap(v14) >= 0 )
    {
      v22 = pv;
      goto LABEL_53;
    }
    v71 = *v14 == 46;
    v22 = 0;
    Buffer = 0;
    pv = 0;
    if ( v71 )
    {
      ExtValue = GetExtValue(SettingStore::IEVALUE_urlmon_MimeExtensionContentType, 9, 1, 0, 0, 0, &Buffer, 1, v14);
      if ( ExtValue >= 0 )
      {
        v74 = _AllocStringWorker<CTCoAllocPolicy>(v73, v72, 0, Buffer, lpString2, (__int64)&pv);
        v22 = pv;
        ExtValue = v74;
        if ( v74 >= 0 )
        {
          ExtValue = GetStringExt(SettingStore::IEVALUE_urlmon_MimeExtensionContentType, v14, pv, Buffer >> 1);
          if ( ExtValue >= 0 )
          {
LABEL_52:
            if ( ExtValue < 0 )
              goto LABEL_65;
LABEL_53:
            v28 = v22;
            v29 = WideCharStr;
            v30 = 260;
            v31 = 2147483646;
            do
            {
              if ( !v31 )
                break;
              if ( !*v28 )
                break;
              *v29++ = *v28++;
              --v31;
              --v30;
            }
            while ( v30 );
            v32 = v29 - 1;
            ExtValue = v30 == 0 ? 0x8007007A : 0;
            if ( v30 )
              v32 = v29;
            *v32 = 0;
            if ( v30 )
            {
              v33 = WideCharStr;
              v34 = 0x7FFFFFFF;
              do
              {
                if ( !*v33 )
                  break;
                ++v33;
                --v34;
              }
              while ( v34 );
              ExtValue = v34 == 0 ? 0x80070057 : 0;
              if ( v34 )
                ExtValue = ((0x7FFFFFFF - v34) & (unsigned __int64)-(__int64)(v34 != 0)) > 0xFFFFFFFF ? 0x80070216 : 0;
            }
LABEL_65:
            if ( v22 )
              CoTaskMemFree(v22);
            if ( ExtValue >= 0 )
            {
              MultiByteStr[0] = 0;
              if ( !WideCharToMultiByte(0, 0, WideCharStr, -1, MultiByteStr, 260, 0, 0) )
                MultiByteStr[0] = 0;
              if ( (*((_DWORD *)this + 188) & 0x100000) != 0 )
              {
                v54 = 0;
                v55 = 0;
                EnterCriticalSection(v4);
                if ( ((*((_DWORD *)this + 132) - 13) & 0xFFFFFFFD) != 0 )
                {
                  v54 = WzA2WDynamic(MultiByteStr, v56, v57, v58);
                  if ( v54 )
                    v55 = CINet::GetRefCountedSinkNoLock(this);
                }
                LeaveCriticalSection(v4);
                if ( v55 )
                  (*(void (__fastcall **)(CINetFile *, struct IInternetProtocolSink *, __int64, unsigned __int16 *))(*(_QWORD *)this + 440LL))(
                    this,
                    v55,
                    22,
                    v54);
                if ( v54 )
                  CoTaskMemFree(v54);
                if ( v55 )
                  ((void (__fastcall *)(struct IInternetProtocolSink *))v55->lpVtbl->Release)(v55);
              }
              else
              {
                v82 = BINDSTATUS_RAWMIMETYPE;
                if ( !v88 )
                  v82 = BINDSTATUS_MIMETYPEAVAILABLE;
                CINet::ReportNotification(this, v82, MultiByteStr);
              }
            }
            goto LABEL_68;
          }
        }
      }
    }
    else
    {
      ExtValue = -2147024809;
    }
    if ( v22 )
    {
      CoTaskMemFree(v22);
      v22 = 0;
    }
    goto LABEL_52;
  }
  v37 = -2146697211;
  *((_DWORD *)this + 178) = 123;
  *((_DWORD *)this + 25) = -2146697211;
LABEL_72:
  if ( pcchPath )
    FindClose(hFindFile);
  return (unsigned int)v37;
}

```

## disassembly

```asm
0x18004efc0  push    rbp
0x18004efc2  push    rbx
0x18004efc3  push    rsi
0x18004efc4  push    rdi
0x18004efc5  push    r12
0x18004efc7  push    r13
0x18004efc9  push    r14
0x18004efcb  push    r15
0x18004efcd  lea     rbp, [rsp-508h]
0x18004efd5  sub     rsp, 608h
0x18004efdc  mov     rax, cs:__security_cookie
0x18004efe3  xor     rax, rsp
0x18004efe6  mov     [rbp+540h+var_50], rax
0x18004efed  mov     rsi, rcx
0x18004eff0  mov     ecx, 2000000Fh
0x18004eff5  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18004effc  nop     dword ptr [rax+rax+00h]
0x18004f001  mov     rdx, [rsi+100h]
0x18004f008  lea     rdi, [rsi+1E8h]
0x18004f00f  xor     r12d, r12d
0x18004f012  mov     [rsp+640h+var_5EC], al
0x18004f016  test    rdx, rdx
0x18004f019  lea     r14, pszFormat
0x18004f020  mov     rcx, rdi; lpCriticalSection
0x18004f023  mov     ebx, r12d
0x18004f026  cmovnz  r14, rdx
0x18004f02a  call    cs:__imp_EnterCriticalSection
0x18004f031  nop     dword ptr [rax+rax+00h]
0x18004f036  mov     ecx, [rsi+210h]
0x18004f03c  sub     ecx, 0Dh
0x18004f03f  test    ecx, 0FFFFFFFDh
0x18004f045  jnz     loc_18004FAEC
0x18004f04b  mov     rcx, rdi; lpCriticalSection
0x18004f04e  call    cs:__imp_LeaveCriticalSection
0x18004f055  nop     dword ptr [rax+rax+00h]
0x18004f05a  test    rbx, rbx
0x18004f05d  jz      short loc_18004F08C
0x18004f05f  mov     rax, [rsi]
0x18004f062  mov     r9, r14
0x18004f065  mov     r8d, 0Bh
0x18004f06b  mov     rdx, rbx
0x18004f06e  mov     rcx, rsi
0x18004f071  mov     rax, [rax+1B8h]
0x18004f078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f07d  mov     rax, [rbx]
0x18004f080  mov     rcx, rbx
0x18004f083  mov     rax, [rax+10h]
0x18004f087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f08c  lea     r14, [rsi+448h]
0x18004f093  mov     ebx, 800h
0x18004f098  cmp     [r14], r12w
0x18004f09c  jz      loc_18004F796
0x18004f0a2  mov     rcx, r14; lpFileName
0x18004f0a5  call    cs:__imp_GetFileAttributesW
0x18004f0ac  nop     dword ptr [rax+rax+00h]
0x18004f0b1  mov     ecx, 0FFFFFFFFh
0x18004f0b6  cmp     eax, ecx
0x18004f0b8  jz      loc_18004FDC2
0x18004f0be  test    al, 10h
0x18004f0c0  jnz     loc_18004FDBB
0x18004f0c6  mov     rcx, cs:?FEATURE_FILEPROTOCOL_NOFINDFIRST_KB947853@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_FILEPROTOCOL_NOFINDFIRST_KB947853
0x18004f0cd  test    rcx, rcx
0x18004f0d0  jnz     loc_18004F8E3
0x18004f0d6  mov     eax, cs:dword_180166F48
0x18004f0dc  test    eax, eax
0x18004f0de  jnz     loc_18004FBDE
0x18004f0e4  xor     edx, edx; Val
0x18004f0e6  lea     rcx, [rbp+540h+FindFileData]; void *
0x18004f0ea  mov     r8d, 250h; Size
0x18004f0f0  call    memset_0
0x18004f0f5  cmp     [r14], r12w
0x18004f0f9  jz      loc_18004F7CC
0x18004f0ff  lea     rdx, [rbp+540h+FindFileData]; lpFindFileData
0x18004f103  mov     rcx, r14; lpFileName
0x18004f106  call    cs:__imp_FindFirstFileW
0x18004f10d  nop     dword ptr [rax+rax+00h]
0x18004f112  or      r13, 0FFFFFFFFFFFFFFFFh
0x18004f116  mov     [rsp+640h+hFindFile], rax
0x18004f11b  cmp     rax, r13
0x18004f11e  jz      loc_18004FDA2
0x18004f124  mov     edx, [rbp+540h+FindFileData.nFileSizeHigh]
0x18004f127  lea     eax, [r13+2]
0x18004f12b  mov     ecx, [rbp+540h+FindFileData.nFileSizeLow]
0x18004f12e  shl     rdx, 20h
0x18004f132  or      rdx, rcx; bool
0x18004f135  mov     [rsp+640h+var_5D8], rax
0x18004f13a  mov     [rsi+180h], rdx
0x18004f141  mov     [rsi+188h], rdx
0x18004f148  mov     [rsp+640h+pcchPath], eax
0x18004f14c  mov     eax, 0FFEFFFFFh
0x18004f151  cmp     [rsi+180h], rax
0x18004f158  jnb     loc_18004F965
0x18004f15e  cmp     [rsi+188h], rax
0x18004f165  jnb     loc_18004F965
0x18004f16b  test    dword ptr [rsi+2F4h], 400000h
0x18004f175  jnz     loc_18004F9A6
0x18004f17b  cmp     [r14], r12w
0x18004f17f  jz      loc_18004F802
0x18004f185  mov     rcx, r14; unsigned __int16 *
0x18004f188  call    ?DoesPathAccessDosDevice@@YAHPEBG@Z; DoesPathAccessDosDevice(ushort const *)
0x18004f18d  test    eax, eax
0x18004f18f  jnz     loc_18004F90F
0x18004f195  cmp     [r14], r12w
0x18004f199  jz      loc_18004F83C
0x18004f19f  mov     rcx, rdi; lpCriticalSection
0x18004f1a2  mov     rbx, r12
0x18004f1a5  call    cs:__imp_EnterCriticalSection
0x18004f1ac  nop     dword ptr [rax+rax+00h]
0x18004f1b1  mov     eax, [rsi+210h]
0x18004f1b7  sub     eax, 0Dh
0x18004f1ba  test    eax, 0FFFFFFFDh
0x18004f1bf  jnz     loc_18004FB10
0x18004f1c5  mov     rcx, rdi; lpCriticalSection
0x18004f1c8  call    cs:__imp_LeaveCriticalSection
0x18004f1cf  nop     dword ptr [rax+rax+00h]
0x18004f1d4  test    rbx, rbx
0x18004f1d7  jnz     loc_18004F4A7
0x18004f1dd  mov     rax, r13
0x18004f1e0  inc     rax
0x18004f1e3  cmp     [r14+rax*2], r12w
0x18004f1e8  jnz     short loc_18004F1E0
0x18004f1ea  lea     rcx, [r14+rax*2]
0x18004f1ee  test    rcx, rcx
0x18004f1f1  jnz     loc_18004F87E
0x18004f1f7  cmp     r14, rcx
0x18004f1fa  sbb     r15, r15
0x18004f1fd  and     r15, rcx
0x18004f200  test    r15, r15
0x18004f203  jz      loc_18004F41E
0x18004f209  mov     [rsp+640h+pv], r12
0x18004f20e  mov     rbx, r12
0x18004f211  xor     r14d, r14d
0x18004f214  lea     rax, off_18012D020; ".htm"
0x18004f21b  cmp     rbx, 7
0x18004f21f  jnb     loc_18004FA28
0x18004f225  mov     r12, rbx
0x18004f228  add     r12, r12
0x18004f22b  mov     rax, [rax+r12*8]
0x18004f22f  test    rax, rax
0x18004f232  jz      short loc_18004F25F
0x18004f234  mov     [rsp+640h+cchCount2], r13d; cchCount2
0x18004f239  mov     r9d, r13d; cchCount1
0x18004f23c  mov     r8, r15; lpString1
0x18004f23f  mov     [rsp+640h+lpString2], rax; lpString2
0x18004f244  mov     edx, 1001h; dwCmpFlags
0x18004f249  mov     ecx, 7Fh; Locale
0x18004f24e  call    cs:__imp_CompareStringW
0x18004f255  nop     dword ptr [rax+rax+00h]
0x18004f25a  add     eax, 0FFFFFFFEh
0x18004f25d  jz      short loc_18004F264
0x18004f25f  inc     rbx
0x18004f262  jmp     short loc_18004F214
0x18004f264  lea     rax, off_18012D020; ".htm"
0x18004f26b  mov     rbx, r13
0x18004f26e  mov     rax, [rax+r12*8+8]
0x18004f273  inc     rbx
0x18004f276  cmp     [rax+rbx*2], r14w
0x18004f27b  jnz     short loc_18004F273
0x18004f27d  inc     rbx
0x18004f280  mov     eax, 2
0x18004f285  mul     rbx
0x18004f288  mov     r13, rax
0x18004f28b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18004f292  cmovb   r13, rax
0x18004f296  mov     rcx, r13; cb
0x18004f299  call    cs:__imp_CoTaskMemAlloc
0x18004f2a0  nop     dword ptr [rax+rax+00h]
0x18004f2a5  mov     r14, rax
0x18004f2a8  test    rax, rax
0x18004f2ab  jz      loc_18004FA28
0x18004f2b1  mov     r8, r13; Size
0x18004f2b4  xor     edx, edx; Val
0x18004f2b6  mov     rcx, rax; void *
0x18004f2b9  call    memset_0
0x18004f2be  lfence
0x18004f2c1  test    rbx, rbx
0x18004f2c4  jz      loc_18004FCA5
0x18004f2ca  cmp     rbx, 7FFFFFFFh
0x18004f2d1  ja      loc_18004FC99
0x18004f2d7  lea     rax, off_18012D020; ".htm"
0x18004f2de  mov     ecx, 7FFFFFFEh
0x18004f2e3  mov     rdx, [rax+r12*8+8]
0x18004f2e8  mov     rax, r14
0x18004f2eb  xor     r12d, r12d
0x18004f2ee  test    rcx, rcx
0x18004f2f1  jz      short loc_18004F317
0x18004f2f3  movzx   r8d, word ptr [rdx]
0x18004f2f7  test    r8w, r8w
0x18004f2fb  jz      short loc_18004F317
0x18004f2fd  mov     [rax], r8w
0x18004f301  add     rdx, 2
0x18004f305  mov     r8d, 1
0x18004f30b  add     rax, 2
0x18004f30f  sub     rcx, r8
0x18004f312  sub     rbx, r8
0x18004f315  jnz     short loc_18004F2EE
0x18004f317  test    rbx, rbx
0x18004f31a  lea     rcx, [rax-2]
0x18004f31e  cmovnz  rcx, rax
0x18004f322  mov     [rcx], r12w
0x18004f326  jmp     short loc_18004F354
0x18004f328  mov     r9d, [rsp+640h+Buffer]
0x18004f32d  mov     r8, r14
0x18004f330  mov     rcx, cs:?IEVALUE_urlmon_MimeExtensionContentType@SettingStore@@3U?$EXTVALUE1ID@PEAG@1@B; SettingStore::EXTVALUE1ID<ushort *> const SettingStore::IEVALUE_urlmon_MimeExtensionContentType
0x18004f337  mov     rdx, r15
0x18004f33a  shr     r9d, 1
0x18004f33d  call    GetStringExt
0x18004f342  mov     ebx, eax
0x18004f344  test    eax, eax
0x18004f346  js      loc_18004FCBC
0x18004f34c  test    ebx, ebx
0x18004f34e  js      loc_18004F402
0x18004f354  mov     rax, r14
0x18004f357  lea     r8, [rbp+540h+WideCharStr]
0x18004f35e  mov     edx, 104h
0x18004f363  mov     r9d, 7FFFFFFEh
0x18004f369  mov     r10d, 1
0x18004f36f  test    r9, r9
0x18004f372  jz      short loc_18004F390
0x18004f374  movzx   ecx, word ptr [rax]
0x18004f377  test    cx, cx
0x18004f37a  jz      short loc_18004F390
0x18004f37c  mov     [r8], cx
0x18004f380  add     rax, 2
0x18004f384  add     r8, 2
0x18004f388  sub     r9, r10
0x18004f38b  sub     rdx, r10
0x18004f38e  jnz     short loc_18004F36F
0x18004f390  mov     rax, rdx
0x18004f393  lea     rcx, [r8-2]
0x18004f397  neg     rax
0x18004f39a  sbb     ebx, ebx
0x18004f39c  not     ebx
0x18004f39e  and     ebx, 8007007Ah
0x18004f3a4  test    rdx, rdx
0x18004f3a7  cmovnz  rcx, r8
0x18004f3ab  mov     [rcx], r12w
0x18004f3af  jz      short loc_18004F402
0x18004f3b1  mov     ecx, 7FFFFFFFh
0x18004f3b6  lea     rax, [rbp+540h+WideCharStr]
0x18004f3bd  mov     edx, ecx
0x18004f3bf  cmp     [rax], r12w
0x18004f3c3  jz      short loc_18004F3CE
0x18004f3c5  add     rax, 2
0x18004f3c9  sub     rdx, r10
0x18004f3cc  jnz     short loc_18004F3BF
0x18004f3ce  mov     rax, rdx
0x18004f3d1  neg     rax
0x18004f3d4  mov     rax, rdx
0x18004f3d7  sbb     ebx, ebx
0x18004f3d9  sub     rcx, rdx
0x18004f3dc  not     ebx
0x18004f3de  and     ebx, 80070057h
0x18004f3e4  neg     rax
0x18004f3e7  sbb     r8, r8
0x18004f3ea  and     r8, rcx
0x18004f3ed  test    rdx, rdx
0x18004f3f0  jz      short loc_18004F402
0x18004f3f2  mov     eax, 0FFFFFFFFh
0x18004f3f7  cmp     rax, r8
0x18004f3fa  sbb     ebx, ebx
0x18004f3fc  and     ebx, 80070216h
0x18004f402  test    r14, r14
0x18004f405  jz      short loc_18004F416
0x18004f407  mov     rcx, r14; pv
0x18004f40a  call    cs:__imp_CoTaskMemFree
0x18004f411  nop     dword ptr [rax+rax+00h]
0x18004f416  test    ebx, ebx
0x18004f418  jns     loc_18004F6B2
0x18004f41e  mov     rcx, rdi; lpCriticalSection
0x18004f421  mov     r13, r12
0x18004f424  call    cs:__imp_EnterCriticalSection
0x18004f42b  nop     dword ptr [rax+rax+00h]
0x18004f430  mov     rcx, [rsi+1B8h]
0x18004f437  test    rcx, rcx
0x18004f43a  jz      short loc_18004F44B
0x18004f43c  mov     rax, [rcx]
0x18004f43f  mov     r13, rcx
0x18004f442  mov     rax, [rax+8]
0x18004f446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f44b  mov     rcx, rdi; lpCriticalSection
0x18004f44e  call    cs:__imp_LeaveCriticalSection
0x18004f455  nop     dword ptr [rax+rax+00h]
0x18004f45a  test    r13, r13
0x18004f45d  jnz     short loc_18004F4D9
0x18004f45f  mov     dword ptr [rsi+64h], 800A0001h
0x18004f466  mov     ebx, r12d
0x18004f469  cmp     [rsp+640h+pcchPath], r12d
0x18004f46e  jz      short loc_18004F481
0x18004f470  mov     rcx, [rsp+640h+hFindFile]; hFindFile
0x18004f475  call    cs:__imp_FindClose
0x18004f47c  nop     dword ptr [rax+rax+00h]
0x18004f481  mov     eax, ebx
0x18004f483  mov     rcx, [rbp+540h+var_50]
0x18004f48a  xor     rcx, rsp; StackCookie
0x18004f48d  call    __security_check_cookie
0x18004f492  add     rsp, 608h
0x18004f499  pop     r15
0x18004f49b  pop     r14
0x18004f49d  pop     r13
  ... truncated ...
```
