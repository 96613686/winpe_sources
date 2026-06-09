# CINetFile::INetAsyncOpen(void)

- ea: `0x18003df30`
- end: `0x18003ec0a`
- name: `?INetAsyncOpen@CINetFile@@UEAAJXZ`
- size: `3290`
- prototype: `__int64 __fastcall(CINetFile *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001054c`
- `0x18003def4`
- `0x18003df30`
- `0x18003ec10`
- `0x18003ede4`
- `0x18003ee48`
- `0x18005d0d4`
- `0x18005d214`
- `0x18005d270`
- `0x18006f8bc`
- `0x180071618`
- `0x18007ae20`
- `0x18009e378`
- `0x18011ba3e`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `msvcrt!_ui64tow_s` at `0x18003e83c`
- `msvcrt!_ui64tow_s` at `0x18003e83c`
- `iertutil!__imp_GetExtValue` at `0x18003e91d`
- `iertutil!__imp_GetExtValue` at `0x18003e91d`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18003e767`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18003e767`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18003df65`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18003e8a5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18003df65`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18003e8a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003dfb2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e114`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e37c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e4d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003dfb2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e114`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e37c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e4d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003df94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e0f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e358`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e4b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003df94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e0f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e358`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e4b7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x18003ebe9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x18003ebe9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003e194`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003e194`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18003e5fb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18003e5fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ebb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ebd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ebb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ebd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003eaa2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003eaa2`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003e39d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003e39d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003e003`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003e003`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003ea82`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003ea82`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003ea55`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003ea55`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003e05e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003e05e`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18003e657`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18003e687`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18003e6bb`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18003e6ef`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18003e657`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18003e687`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18003e6bb`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18003e6ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e1d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e1d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e344`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003eafa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e344`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003eafa`
- `WININET!InternetSetOptionW` at `0x18003eb49`
- `WININET!InternetSetOptionW` at `0x18003eb93`
- `WININET!InternetSetOptionW` at `0x18003eb49`
- `WININET!InternetSetOptionW` at `0x18003eb93`

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
  enum tagBINDSTATUS v54; // edx
  const WCHAR *v55; // rcx
  DWORD v56; // r9d
  const WCHAR *v57; // rcx
  DWORD v58; // r9d
  const WCHAR *v59; // rcx
  DWORD v60; // r9d
  const WCHAR *v61; // rcx
  DWORD v62; // r9d
  int IsFeatureEnabledInternal; // eax
  int v64; // eax
  struct IInternetBindInfo *RefCountedBindInfo; // r15
  unsigned int v66; // r15d
  bool v67; // zf
  int v68; // edx
  int v69; // ecx
  int v70; // eax
  __int64 v71; // rcx
  __int64 v72; // rcx
  int v73; // eax
  const WCHAR *v74; // rax
  HANDLE FileW; // rax
  void *v76; // rbx
  LPVOID v77; // rax
  void *v78; // rcx
  DWORD LastError; // ebx
  const WCHAR *ObjectNameW; // rax
  int lpString2; // [rsp+20h] [rbp-E0h]
  DWORD Buffer; // [rsp+50h] [rbp-B0h] BYREF
  char v83; // [rsp+54h] [rbp-ACh]
  DWORD pcchPath; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v86; // [rsp+68h] [rbp-98h]
  HANDLE hFindFile; // [rsp+70h] [rbp-90h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF
  CHAR MultiByteStr[2]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR WideCharStr[264]; // [rsp+3E0h] [rbp+2E0h] BYREF

  Bool = IEConfiguration_GetBool(536870927);
  v3 = (const OLECHAR *)*((_QWORD *)this + 32);
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 488);
  v83 = Bool;
  v5 = &pszFormat;
  v6 = 0;
  if ( v3 )
    v5 = v3;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  if ( ((*((_DWORD *)this + 132) - 13) & 0xFFFFFFFD) != 0 )
  {
    v71 = *((_QWORD *)this + 55);
    if ( v71 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 8LL))(v71);
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
    v55 = (const WCHAR *)*((_QWORD *)this + 20);
    v56 = (*((_DWORD *)this + 189) & 0x800) << 7;
    pcchPath = 260;
    PathCreateFromUrlW(v55, (PWSTR)this + 548, &pcchPath, v56);
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
    goto LABEL_178;
  }
  if ( (FileAttributesW & 0x10) != 0 )
  {
    v37 = -2146697195;
    goto LABEL_178;
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
        v57 = (const WCHAR *)*((_QWORD *)this + 20);
        v58 = (*((_DWORD *)this + 189) & 0x800) << 7;
        pcchPath = 260;
        PathCreateFromUrlW(v57, (PWSTR)this + 548, &pcchPath, v58);
      }
      hFindFile = FindFirstFileW((LPCWSTR)this + 548, &FindFileData);
      if ( hFindFile != (HANDLE)-1LL )
      {
        v9 = FindFileData.nFileSizeLow | ((unsigned __int64)FindFileData.nFileSizeHigh << 32);
        v86 = 1;
        *((_QWORD *)this + 48) = v9;
        *((_QWORD *)this + 49) = v9;
        pcchPath = 1;
        goto LABEL_16;
      }
      goto LABEL_172;
    }
    dword_180159F48 = IsFeatureEnabledInternal == 0;
    FCK::FEATURE_FILEPROTOCOL_NOFINDFIRST_KB947853 = 0;
  }
  if ( !dword_180159F48 )
    goto LABEL_12;
  v74 = CINetFile::GetObjectNameW(this);
  v86 = 1;
  FileW = CreateFileW(v74, 0x80u, 1u, 0, 3u, 0x80u, 0);
  v76 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
LABEL_172:
    *((_DWORD *)this + 178) = GetLastError();
    v37 = -2146697209;
LABEL_178:
    *((_DWORD *)this + 25) = v37;
    return (unsigned int)v37;
  }
  pcchPath = 0;
  hFindFile = (HANDLE)-1LL;
  pv = 0;
  if ( GetFileSizeEx(FileW, (PLARGE_INTEGER)&pv) )
  {
    v77 = pv;
    *((_QWORD *)this + 48) = pv;
    *((_QWORD *)this + 49) = v77;
  }
  CloseHandle(v76);
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
    v59 = (const WCHAR *)*((_QWORD *)this + 20);
    v60 = (*((_DWORD *)this + 189) & 0x800) << 7;
    Buffer = 260;
    PathCreateFromUrlW(v59, (PWSTR)this + 548, &Buffer, v60);
  }
  if ( !(unsigned int)DoesPathAccessDosDevice((const unsigned __int16 *)this + 548) )
  {
    if ( !*v7 )
    {
      v61 = (const WCHAR *)*((_QWORD *)this + 20);
      v62 = (*((_DWORD *)this + 189) & 0x800) << 7;
      Buffer = 260;
      PathCreateFromUrlW(v61, (PWSTR)this + 548, &Buffer, v62);
    }
    v10 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
    if ( ((*((_DWORD *)this + 132) - 13) & 0xFFFFFFFD) != 0 )
    {
      v72 = *((_QWORD *)this + 55);
      if ( v72 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 8LL))(v72);
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
          v64 = StringCchPrintfW((unsigned __int16 *)MultiByteStr, 0x80u, L"%I64u,%I64u", v41, v40);
          LODWORD(v40) = 0;
          if ( v64 >= 0 )
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
        LODWORD(v86) = 0;
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
                v78 = (void *)*((_QWORD *)this + 44);
                Buffer = 18000000;
                *((_BYTE *)this + 994) = v52 | 8;
                InternetSetOptionW(v78, 6u, &Buffer, 4u);
              }
              if ( v46 >= 0xFFEFFFFF || v48 >= 0xFFEFFFFF )
              {
                *(_WORD *)MultiByteStr = 0;
                v66 = v50 | 0x40;
                if ( (int)StringCchPrintfW((unsigned __int16 *)MultiByteStr, 0x80u, L"%I64u,%I64u", v48, v46) >= 0 )
                  CINet::ReportNotificationW(this, BINDSTATUS_64BIT_PROGRESS, (const unsigned __int16 *)MultiByteStr);
                (*(void (__fastcall **)(CINetFile *, struct IInternetProtocolSink *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)this + 448LL))(
                  this,
                  v51,
                  v66,
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
          if ( (_DWORD)v86 )
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
        v73 = *((_DWORD *)this + 108);
        if ( (v73 & 4) != 0 || (*((_DWORD *)this + 207) & 0x100000) != 0 )
          goto LABEL_151;
        *((_DWORD *)this + 108) = v73 | 4;
      }
      else
      {
        *((_DWORD *)this + 108) |= 4u;
      }
      v49 = 1;
LABEL_151:
      RefCountedSinkNoLock = CINet::GetRefCountedSinkNoLock(this);
      goto LABEL_89;
    }
    pv = 0;
    for ( i = 0; i < 7; ++i )
    {
      v16 = 2 * i;
      v17 = off_18011EA80[2 * i];
      if ( v17 && CompareStringW(0x7Fu, 0x1001u, v14, -1, v17, -1) == 2 )
      {
        v18 = -1;
        do
          ++v18;
        while ( off_18011EA80[v16 + 1][v18] );
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
              v24 = off_18011EA80[v16 + 1];
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
    v67 = *v14 == 46;
    v22 = 0;
    Buffer = 0;
    pv = 0;
    if ( v67 )
    {
      ExtValue = GetExtValue(
                   (__int64 *)SettingStore::IEVALUE_urlmon_MimeExtensionContentType,
                   9,
                   1,
                   0,
                   0,
                   0,
                   &Buffer,
                   1,
                   v14);
      if ( ExtValue >= 0 )
      {
        v70 = _AllocStringWorker<CTCoAllocPolicy>(v69, v68, 0, Buffer, lpString2, (__int64)&pv);
        v22 = pv;
        ExtValue = v70;
        if ( v70 >= 0 )
        {
          ExtValue = GetStringExt(
                       (__int64 *)SettingStore::IEVALUE_urlmon_MimeExtensionContentType,
                       v14,
                       pv,
                       Buffer >> 1);
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
                v54 = BINDSTATUS_VERIFIEDMIMETYPEAVAILABLE;
              }
              else
              {
                v54 = BINDSTATUS_RAWMIMETYPE;
                if ( !v83 )
                  v54 = BINDSTATUS_MIMETYPEAVAILABLE;
              }
              CINet::ReportNotification(this, v54, MultiByteStr);
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
0x18003df30  push    rbp
0x18003df32  push    rbx
0x18003df33  push    rsi
0x18003df34  push    rdi
0x18003df35  push    r12
0x18003df37  push    r13
0x18003df39  push    r14
0x18003df3b  push    r15
0x18003df3d  lea     rbp, [rsp-508h]
0x18003df45  sub     rsp, 608h
0x18003df4c  mov     rax, cs:__security_cookie
0x18003df53  xor     rax, rsp
0x18003df56  mov     [rbp+540h+var_50], rax
0x18003df5d  mov     rsi, rcx
0x18003df60  mov     ecx, 2000000Fh
0x18003df65  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18003df6b  mov     rdx, [rsi+100h]
0x18003df72  lea     rdi, [rsi+1E8h]
0x18003df79  xor     r12d, r12d
0x18003df7c  mov     [rsp+640h+var_5EC], al
0x18003df80  test    rdx, rdx
0x18003df83  lea     r14, pszFormat
0x18003df8a  mov     rcx, rdi; lpCriticalSection
0x18003df8d  mov     ebx, r12d
0x18003df90  cmovnz  r14, rdx
0x18003df94  call    cs:__imp_EnterCriticalSection
0x18003df9a  mov     ecx, [rsi+210h]
0x18003dfa0  sub     ecx, 0Dh
0x18003dfa3  test    ecx, 0FFFFFFFDh
0x18003dfa9  jnz     loc_18003E958
0x18003dfaf  mov     rcx, rdi; lpCriticalSection
0x18003dfb2  call    cs:__imp_LeaveCriticalSection
0x18003dfb8  test    rbx, rbx
0x18003dfbb  jz      short loc_18003DFEA
0x18003dfbd  mov     rax, [rsi]
0x18003dfc0  mov     r9, r14
0x18003dfc3  mov     r8d, 0Bh
0x18003dfc9  mov     rdx, rbx
0x18003dfcc  mov     rcx, rsi
0x18003dfcf  mov     rax, [rax+1B8h]
0x18003dfd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dfdb  mov     rax, [rbx]
0x18003dfde  mov     rcx, rbx
0x18003dfe1  mov     rax, [rax+10h]
0x18003dfe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dfea  lea     r14, [rsi+448h]
0x18003dff1  mov     ebx, 800h
0x18003dff6  cmp     [r14], r12w
0x18003dffa  jz      loc_18003E632
0x18003e000  mov     rcx, r14; lpFileName
0x18003e003  call    cs:__imp_GetFileAttributesW
0x18003e009  mov     ecx, 0FFFFFFFFh
0x18003e00e  cmp     eax, ecx
0x18003e010  jz      loc_18003EBD1
0x18003e016  test    al, 10h
0x18003e018  jnz     loc_18003EBCA
0x18003e01e  mov     rcx, cs:?FEATURE_FILEPROTOCOL_NOFINDFIRST_KB947853@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_FILEPROTOCOL_NOFINDFIRST_KB947853
0x18003e025  test    rcx, rcx
0x18003e028  jnz     loc_18003E767
0x18003e02e  mov     eax, cs:dword_180159F48
0x18003e034  test    eax, eax
0x18003e036  jnz     loc_18003EA22
0x18003e03c  xor     edx, edx; Val
0x18003e03e  lea     rcx, [rbp+540h+FindFileData]; void *
0x18003e042  mov     r8d, 250h; Size
0x18003e048  call    memset_0
0x18003e04d  cmp     [r14], r12w
0x18003e051  jz      loc_18003E662
0x18003e057  lea     rdx, [rbp+540h+FindFileData]; lpFindFileData
0x18003e05b  mov     rcx, r14; lpFileName
0x18003e05e  call    cs:__imp_FindFirstFileW
0x18003e064  or      r13, 0FFFFFFFFFFFFFFFFh
0x18003e068  mov     [rsp+640h+hFindFile], rax
0x18003e06d  cmp     rax, r13
0x18003e070  jz      loc_18003EBB7
0x18003e076  mov     edx, [rbp+540h+FindFileData.nFileSizeHigh]
0x18003e079  lea     eax, [r13+2]
0x18003e07d  mov     ecx, [rbp+540h+FindFileData.nFileSizeLow]
0x18003e080  shl     rdx, 20h
0x18003e084  or      rdx, rcx; bool
0x18003e087  mov     [rsp+640h+var_5D8], rax
0x18003e08c  mov     [rsi+180h], rdx
0x18003e093  mov     [rsi+188h], rdx
0x18003e09a  mov     [rsp+640h+pcchPath], eax
0x18003e09e  mov     eax, 0FFEFFFFFh
0x18003e0a3  cmp     [rsi+180h], rax
0x18003e0aa  jnb     loc_18003E7E3
0x18003e0b0  cmp     [rsi+188h], rax
0x18003e0b7  jnb     loc_18003E7E3
0x18003e0bd  test    dword ptr [rsi+2F4h], 400000h
0x18003e0c7  jnz     loc_18003E824
0x18003e0cd  cmp     [r14], r12w
0x18003e0d1  jz      loc_18003E692
0x18003e0d7  mov     rcx, r14; unsigned __int16 *
0x18003e0da  call    ?DoesPathAccessDosDevice@@YAHPEBG@Z; DoesPathAccessDosDevice(ushort const *)
0x18003e0df  test    eax, eax
0x18003e0e1  jnz     loc_18003E78D
0x18003e0e7  cmp     [r14], r12w
0x18003e0eb  jz      loc_18003E6C6
0x18003e0f1  mov     rcx, rdi; lpCriticalSection
0x18003e0f4  mov     rbx, r12
0x18003e0f7  call    cs:__imp_EnterCriticalSection
0x18003e0fd  mov     eax, [rsi+210h]
0x18003e103  sub     eax, 0Dh
0x18003e106  test    eax, 0FFFFFFFDh
0x18003e10b  jnz     loc_18003E97C
0x18003e111  mov     rcx, rdi; lpCriticalSection
0x18003e114  call    cs:__imp_LeaveCriticalSection
0x18003e11a  test    rbx, rbx
0x18003e11d  jnz     loc_18003E3C8
0x18003e123  mov     rax, r13
0x18003e126  inc     rax
0x18003e129  cmp     [r14+rax*2], r12w
0x18003e12e  jnz     short loc_18003E126
0x18003e130  lea     rcx, [r14+rax*2]
0x18003e134  test    rcx, rcx
0x18003e137  jnz     loc_18003E702
0x18003e13d  cmp     r14, rcx
0x18003e140  sbb     r15, r15
0x18003e143  and     r15, rcx
0x18003e146  test    r15, r15
0x18003e149  jz      loc_18003E352
0x18003e14f  mov     [rsp+640h+pv], r12
0x18003e154  mov     rbx, r12
0x18003e157  xor     r14d, r14d
0x18003e15a  lea     rax, off_18011EA80; ".htm"
0x18003e161  cmp     rbx, 7
0x18003e165  jnb     loc_18003E8A0
0x18003e16b  mov     r12, rbx
0x18003e16e  add     r12, r12
0x18003e171  mov     rax, [rax+r12*8]
0x18003e175  test    rax, rax
0x18003e178  jz      short loc_18003E19F
0x18003e17a  mov     [rsp+640h+cchCount2], r13d; cchCount2
0x18003e17f  mov     r9d, r13d; cchCount1
0x18003e182  mov     r8, r15; lpString1
0x18003e185  mov     [rsp+640h+lpString2], rax; lpString2
0x18003e18a  mov     edx, 1001h; dwCmpFlags
0x18003e18f  mov     ecx, 7Fh; Locale
0x18003e194  call    cs:__imp_CompareStringW
0x18003e19a  add     eax, 0FFFFFFFEh
0x18003e19d  jz      short loc_18003E1A4
0x18003e19f  inc     rbx
0x18003e1a2  jmp     short loc_18003E15A
0x18003e1a4  lea     rax, off_18011EA80; ".htm"
0x18003e1ab  mov     rbx, r13
0x18003e1ae  mov     rax, [rax+r12*8+8]
0x18003e1b3  inc     rbx
0x18003e1b6  cmp     [rax+rbx*2], r14w
0x18003e1bb  jnz     short loc_18003E1B3
0x18003e1bd  inc     rbx
0x18003e1c0  mov     eax, 2
0x18003e1c5  mul     rbx
0x18003e1c8  mov     r13, rax
0x18003e1cb  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18003e1d2  cmovb   r13, rax
0x18003e1d6  mov     rcx, r13; cb
0x18003e1d9  call    cs:__imp_CoTaskMemAlloc
0x18003e1df  mov     r14, rax
0x18003e1e2  test    rax, rax
0x18003e1e5  jz      loc_18003E8A0
0x18003e1eb  mov     r8, r13; Size
0x18003e1ee  xor     edx, edx; Val
0x18003e1f0  mov     rcx, rax; void *
0x18003e1f3  call    memset_0
0x18003e1f8  lfence
0x18003e1fb  test    rbx, rbx
0x18003e1fe  jz      loc_18003EAD7
0x18003e204  cmp     rbx, 7FFFFFFFh
0x18003e20b  ja      loc_18003EACB
0x18003e211  lea     rax, off_18011EA80; ".htm"
0x18003e218  mov     ecx, 7FFFFFFEh
0x18003e21d  mov     rdx, [rax+r12*8+8]
0x18003e222  mov     rax, r14
0x18003e225  xor     r12d, r12d
0x18003e228  test    rcx, rcx
0x18003e22b  jz      short loc_18003E251
0x18003e22d  movzx   r8d, word ptr [rdx]
0x18003e231  test    r8w, r8w
0x18003e235  jz      short loc_18003E251
0x18003e237  mov     [rax], r8w
0x18003e23b  add     rdx, 2
0x18003e23f  mov     r8d, 1
0x18003e245  add     rax, 2
0x18003e249  sub     rcx, r8
0x18003e24c  sub     rbx, r8
0x18003e24f  jnz     short loc_18003E228
0x18003e251  test    rbx, rbx
0x18003e254  lea     rcx, [rax-2]
0x18003e258  cmovnz  rcx, rax
0x18003e25c  mov     [rcx], r12w
0x18003e260  jmp     short loc_18003E28E
0x18003e262  mov     r9d, [rsp+640h+Buffer]
0x18003e267  mov     r8, r14
0x18003e26a  mov     rcx, cs:?IEVALUE_urlmon_MimeExtensionContentType@SettingStore@@3U?$EXTVALUE1ID@PEAG@1@B; SettingStore::EXTVALUE1ID<ushort *> const SettingStore::IEVALUE_urlmon_MimeExtensionContentType
0x18003e271  mov     rdx, r15
0x18003e274  shr     r9d, 1
0x18003e277  call    GetStringExt
0x18003e27c  mov     ebx, eax
0x18003e27e  test    eax, eax
0x18003e280  js      loc_18003EAEE
0x18003e286  test    ebx, ebx
0x18003e288  js      loc_18003E33C
0x18003e28e  mov     rax, r14
0x18003e291  lea     r8, [rbp+540h+WideCharStr]
0x18003e298  mov     edx, 104h
0x18003e29d  mov     r9d, 7FFFFFFEh
0x18003e2a3  mov     r10d, 1
0x18003e2a9  test    r9, r9
0x18003e2ac  jz      short loc_18003E2CA
0x18003e2ae  movzx   ecx, word ptr [rax]
0x18003e2b1  test    cx, cx
0x18003e2b4  jz      short loc_18003E2CA
0x18003e2b6  mov     [r8], cx
0x18003e2ba  add     rax, 2
0x18003e2be  add     r8, 2
0x18003e2c2  sub     r9, r10
0x18003e2c5  sub     rdx, r10
0x18003e2c8  jnz     short loc_18003E2A9
0x18003e2ca  mov     rax, rdx
0x18003e2cd  lea     rcx, [r8-2]
0x18003e2d1  neg     rax
0x18003e2d4  sbb     ebx, ebx
0x18003e2d6  not     ebx
0x18003e2d8  and     ebx, 8007007Ah
0x18003e2de  test    rdx, rdx
0x18003e2e1  cmovnz  rcx, r8
0x18003e2e5  mov     [rcx], r12w
0x18003e2e9  jz      short loc_18003E33C
0x18003e2eb  mov     ecx, 7FFFFFFFh
0x18003e2f0  lea     rax, [rbp+540h+WideCharStr]
0x18003e2f7  mov     edx, ecx
0x18003e2f9  cmp     [rax], r12w
0x18003e2fd  jz      short loc_18003E308
0x18003e2ff  add     rax, 2
0x18003e303  sub     rdx, r10
0x18003e306  jnz     short loc_18003E2F9
0x18003e308  mov     rax, rdx
0x18003e30b  neg     rax
0x18003e30e  mov     rax, rdx
0x18003e311  sbb     ebx, ebx
0x18003e313  sub     rcx, rdx
0x18003e316  not     ebx
0x18003e318  and     ebx, 80070057h
0x18003e31e  neg     rax
0x18003e321  sbb     r8, r8
0x18003e324  and     r8, rcx
0x18003e327  test    rdx, rdx
0x18003e32a  jz      short loc_18003E33C
0x18003e32c  mov     eax, 0FFFFFFFFh
0x18003e331  cmp     rax, r8
0x18003e334  sbb     ebx, ebx
0x18003e336  and     ebx, 80070216h
0x18003e33c  test    r14, r14
0x18003e33f  jz      short loc_18003E34A
0x18003e341  mov     rcx, r14; pv
0x18003e344  call    cs:__imp_CoTaskMemFree
0x18003e34a  test    ebx, ebx
0x18003e34c  jns     loc_18003E5C7
0x18003e352  mov     rcx, rdi; lpCriticalSection
0x18003e355  mov     r13, r12
0x18003e358  call    cs:__imp_EnterCriticalSection
0x18003e35e  mov     rcx, [rsi+1B8h]
0x18003e365  test    rcx, rcx
0x18003e368  jz      short loc_18003E379
0x18003e36a  mov     rax, [rcx]
0x18003e36d  mov     r13, rcx
0x18003e370  mov     rax, [rax+8]
0x18003e374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e379  mov     rcx, rdi; lpCriticalSection
0x18003e37c  call    cs:__imp_LeaveCriticalSection
0x18003e382  test    r13, r13
0x18003e385  jnz     short loc_18003E3FA
0x18003e387  mov     dword ptr [rsi+64h], 800A0001h
0x18003e38e  mov     ebx, r12d
0x18003e391  cmp     [rsp+640h+pcchPath], r12d
0x18003e396  jz      short loc_18003E3A3
0x18003e398  mov     rcx, [rsp+640h+hFindFile]; hFindFile
0x18003e39d  call    cs:__imp_FindClose
0x18003e3a3  mov     eax, ebx
0x18003e3a5  mov     rcx, [rbp+540h+var_50]
0x18003e3ac  xor     rcx, rsp; StackCookie
0x18003e3af  call    __security_check_cookie
0x18003e3b4  add     rsp, 608h
0x18003e3bb  pop     r15
0x18003e3bd  pop     r14
0x18003e3bf  pop     r13
0x18003e3c1  pop     r12
0x18003e3c3  pop     rdi
0x18003e3c4  pop     rsi
0x18003e3c5  pop     rbx
0x18003e3c6  pop     rbp
0x18003e3c7  retn
0x18003e3c8  mov     rax, [rsi]
0x18003e3cb  mov     r9, r14
0x18003e3ce  mov     r8d, 0Eh
0x18003e3d4  mov     rdx, rbx
0x18003e3d7  mov     rcx, rsi
0x18003e3da  mov     rax, [rax+1B8h]
0x18003e3e1  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
