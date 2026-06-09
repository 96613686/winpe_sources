# Microsoft::Diagnostics::Utils::FileSystem::CopyFiles(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,Microsoft::Diagnostics::EscalationWorkItemState *,bool,ulong,ulong *,ulong,bool,int *,std::function<bool (std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)> *,std::function<long (std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)> *)

- ea: `0x18020fc20`
- end: `0x180210a12`
- name: `?CopyFiles@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00PEAVEscalationWorkItemState@34@_NKPEAKK2PEAHPEAV?$function@$$A6A_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z@6@PEAV?$function@$$A6AJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z@6@@Z`
- size: `3570`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *, __int64, char, unsigned int, int *, DWORD dwCopyFlags, char, WINBOOL *, __int64, __int64)`
- caller_count: `5`
- callee_count: `24`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800b0910`
- `0x18020fc20`
- `0x180215d4c`
- `0x18022d4bc`
- `0x1802ed634`

## callees

- `0x18001d160`
- `0x18001d200`
- `0x18001e638`
- `0x180020fbc`
- `0x180026ecc`
- `0x180027be0`
- `0x180035698`
- `0x180053a84`
- `0x180080054`
- `0x180086f40`
- `0x18008bd1c`
- `0x180098d80`
- `0x1800a0654`
- `0x1800aac70`
- `0x1800d0d9c`
- `0x180108668`
- `0x180108864`
- `0x18012de40`
- `0x18012eb08`
- `0x18017c0ac`
- `0x1801c6f34`
- `0x18020fc20`
- `0x180218b98`
- `0x180346010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18021056f`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18021056f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180210100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180210687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021087b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180210100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180210687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021087b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18020fcf9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18020fcf9`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1802103b4`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1802107f1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180210826`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1802103b4`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1802107f1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180210826`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18021084c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18021084c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180210867`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180210867`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1802103da`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1802103da`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1802100ec`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1802100ec`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180210673`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180210673`

## string_xrefs

- `0x1802101ba`: `Created directory: `
- `0x180210123`: `Path exceeded maximum length. Failed to create directory: `
- `0x1802106a8`: `Failed to copy file due to sharing violation: `

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::Utils::FileSystem::CopyFiles(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4,
        char a5,
        unsigned int a6,
        int *a7,
        DWORD dwCopyFlags,
        char a9,
        WINBOOL *a10,
        __int64 a11,
        __int64 a12)
{
  int v15; // eax
  __int64 v16; // rax
  char *FirstFileW; // rbx
  const char *v18; // r9
  __int64 v19; // rax
  __int64 v20; // rax
  int appended; // eax
  unsigned int v22; // esi
  __int64 v24; // rax
  int v25; // eax
  unsigned int v26; // esi
  __int64 v27; // rax
  __int64 v28; // rax
  const WCHAR *v29; // rcx
  const char *v30; // r9
  unsigned int v31; // ebx
  __int128 v32; // xmm6
  __int128 v33; // xmm7
  __int64 v34; // rax
  int v35; // esi
  const WCHAR *v36; // rcx
  const WCHAR *v37; // rcx
  __int64 v38; // r8
  __int128 v39; // xmm0
  __int64 v40; // rax
  __int64 v41; // rcx
  int v42; // eax
  __int64 v43; // r8
  void *v44; // rsi
  char *v45; // rdx
  const WCHAR *v46; // rdx
  const WCHAR *v47; // rcx
  const char *v48; // r9
  unsigned int LastError; // ebx
  const WCHAR *v50; // rcx
  const WCHAR *v51; // rcx
  const WCHAR *v52; // rcx
  const char *v53; // r9
  unsigned int v54; // ebx
  unsigned int v55; // ebx
  int pbCancel; // [rsp+20h] [rbp-558h]
  __int64 v57; // [rsp+60h] [rbp-518h] BYREF
  char *v58; // [rsp+68h] [rbp-510h] BYREF
  int v59[4]; // [rsp+70h] [rbp-508h] BYREF
  int v60[4]; // [rsp+80h] [rbp-4F8h] BYREF
  __int64 v61; // [rsp+90h] [rbp-4E8h]
  __int64 v62; // [rsp+98h] [rbp-4E0h]
  LPBOOL v63; // [rsp+A0h] [rbp-4D8h]
  int v64[4]; // [rsp+B0h] [rbp-4C8h] BYREF
  _QWORD v65[6]; // [rsp+C0h] [rbp-4B8h] BYREF
  _QWORD v66[2]; // [rsp+F0h] [rbp-488h] BYREF
  _QWORD v67[2]; // [rsp+100h] [rbp-478h] BYREF
  _QWORD v68[2]; // [rsp+110h] [rbp-468h] BYREF
  _QWORD v69[2]; // [rsp+120h] [rbp-458h] BYREF
  _QWORD v70[2]; // [rsp+130h] [rbp-448h] BYREF
  __int128 v71; // [rsp+140h] [rbp-438h] BYREF
  __int128 v72; // [rsp+150h] [rbp-428h] BYREF
  _BYTE v73[16]; // [rsp+160h] [rbp-418h] BYREF
  _BYTE v74[16]; // [rsp+170h] [rbp-408h] BYREF
  _BYTE v75[16]; // [rsp+180h] [rbp-3F8h] BYREF
  _BYTE v76[16]; // [rsp+190h] [rbp-3E8h] BYREF
  _BYTE v77[16]; // [rsp+1A0h] [rbp-3D8h] BYREF
  _BYTE v78[16]; // [rsp+1B0h] [rbp-3C8h] BYREF
  _BYTE v79[16]; // [rsp+1C0h] [rbp-3B8h] BYREF
  _BYTE v80[16]; // [rsp+1D0h] [rbp-3A8h] BYREF
  _BYTE v81[16]; // [rsp+1E0h] [rbp-398h] BYREF
  _BYTE v82[16]; // [rsp+1F0h] [rbp-388h] BYREF
  char v83; // [rsp+200h] [rbp-378h] BYREF
  char v84; // [rsp+210h] [rbp-368h] BYREF
  _BYTE v85[16]; // [rsp+220h] [rbp-358h] BYREF
  _BYTE v86[16]; // [rsp+230h] [rbp-348h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+240h] [rbp-338h] BYREF
  unsigned __int64 v88; // [rsp+258h] [rbp-320h]
  LPCWSTR lpPathName[3]; // [rsp+260h] [rbp-318h] BYREF
  unsigned __int64 v90; // [rsp+278h] [rbp-300h]
  _BYTE v91[32]; // [rsp+280h] [rbp-2F8h] BYREF
  _BYTE v92[32]; // [rsp+2A0h] [rbp-2D8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+2C0h] [rbp-2B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+578h] [rbp+0h]

  v63 = a10;
  v62 = a11;
  v61 = a12;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  std::wstring::wstring(lpFileName);
  std::wstring::wstring(lpPathName);
  v15 = 0;
  if ( a7 )
    v15 = *a7;
  LODWORD(v57) = v15;
  v16 = std::wstring::wstring(v91);
  if ( *(_QWORD *)(v16 + 24) > 7u )
    v16 = *(_QWORD *)v16;
  FirstFileW = (char *)FindFirstFileW((LPCWSTR)v16, &FindFileData);
  v58 = FirstFileW;
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v91);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v19 = -1;
        do
          ++v19;
        while ( FindFileData.cFileName[v19] );
        v65[0] = FindFileData.cFileName;
        v65[1] = v19;
        if ( std::wstring_view::find_first_of(v65, L"<>:\"/\\|?*") != -1 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x414,
            (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
            (const char *)0x8007007BLL,
            pbCancel);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpPathName);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
          return 2147942523LL;
        }
        std::wstring::_Assign<wchar_t>(lpFileName, *a2);
        v20 = -1;
        do
          ++v20;
        while ( FindFileData.cFileName[v20] );
        v65[2] = FindFileData.cFileName;
        v65[3] = v20;
        appended = Microsoft::Diagnostics::Utils::String::AppendPath((PWSTR)lpFileName);
        v22 = appended;
        if ( appended < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x417,
            (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
            (const char *)(unsigned int)appended,
            pbCancel);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpPathName);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
          return v22;
        }
        std::wstring::_Assign<wchar_t>(lpPathName, *a3);
        v24 = -1;
        do
          ++v24;
        while ( FindFileData.cFileName[v24] );
        v65[4] = FindFileData.cFileName;
        v65[5] = v24;
        v25 = Microsoft::Diagnostics::Utils::String::AppendPath((PWSTR)lpPathName);
        v26 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x41A,
            (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
            (const char *)(unsigned int)v25,
            pbCancel);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpPathName);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
          return v26;
        }
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
          break;
        *(_OWORD *)v59 = *(_OWORD *)a2;
        *(_OWORD *)v60 = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, v79);
        if ( !(unsigned __int8)Microsoft::Diagnostics::Utils::FileSystem::ValidatePathStartsWith(v60, v59) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x475,
            (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
            (const char *)0x8007010BLL,
            pbCancel);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpPathName);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
          return 2147942667LL;
        }
        *(_OWORD *)v59 = *(_OWORD *)a3;
        *(_OWORD *)v60 = *(_OWORD *)std::wstring::operator std::wstring_view(lpPathName, v80);
        if ( !(unsigned __int8)Microsoft::Diagnostics::Utils::FileSystem::ValidatePathStartsWith(v60, v59) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x476,
            (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
            (const char *)0x8007010BLL,
            pbCancel);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpPathName);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
          return 2147942667LL;
        }
        if ( v61 )
        {
          v39 = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, v81);
          v40 = -1;
          do
            ++v40;
          while ( FindFileData.cFileName[v40] );
          v71 = v39;
          v70[0] = FindFileData.cFileName;
          v70[1] = v40;
          v41 = *(_QWORD *)(v38 + 56);
          if ( !v41 )
            std::_Xbad_function_call();
          v42 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int128 *))(*(_QWORD *)v41 + 16LL))(v41, v70, &v71);
          if ( v42 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x47B,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
              (const char *)(unsigned int)v42,
              pbCancel);
        }
        if ( v62 )
        {
          v72 = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, v82);
          if ( !(unsigned __int8)std::_Func_class<bool,std::wstring_view>::operator()(v43, &v72) )
          {
            if ( !a4 )
              goto LABEL_83;
            v44 = (void *)(a4 + 168);
            Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
            v45 = &v83;
            goto LABEL_68;
          }
        }
        v46 = (const WCHAR *)lpPathName;
        if ( v90 > 7 )
          v46 = lpPathName[0];
        v47 = (const WCHAR *)lpFileName;
        if ( v88 > 7 )
          v47 = lpFileName[0];
        if ( CopyFileExW(v47, v46, 0, 0, v63, dwCopyFlags) )
        {
          if ( a4 )
          {
            Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
            *(_OWORD *)v59 = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, v85);
            Microsoft::Diagnostics::WideStringStream::AppendString((void *)(a4 + 168));
            Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
            *(_OWORD *)v59 = *(_OWORD *)std::wstring::operator std::wstring_view(lpPathName, v86);
            Microsoft::Diagnostics::EscalationWorkItemState::AddCollectedFileToBuilder(a4, v59);
          }
          if ( a9 )
          {
            v50 = (const WCHAR *)lpPathName;
            if ( v90 > 7 )
              v50 = lpPathName[0];
            SetFileAttributesW(v50, 0x80u);
          }
          if ( a5 )
          {
            v51 = (const WCHAR *)lpFileName;
            if ( v88 > 7 )
              v51 = lpFileName[0];
            SetFileAttributesW(v51, 0x80u);
            v52 = (const WCHAR *)lpFileName;
            if ( v88 > 7 )
              v52 = lpFileName[0];
            DeleteFileW(v52);
          }
          LODWORD(v57) = v57 + 1;
        }
        else
        {
          if ( GetLastError() != 32 )
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x498,
                          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                          v48);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v58);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpPathName);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
            return LastError;
          }
          if ( a4 )
          {
            v44 = (void *)(a4 + 168);
            Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
            v45 = &v84;
LABEL_68:
            *(_OWORD *)v59 = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, v45);
            Microsoft::Diagnostics::WideStringStream::AppendString(v44);
            Microsoft::Diagnostics::WideStringStream::operator<<(v44);
          }
        }
LABEL_83:
        if ( !FindNextFileW(FirstFileW, &FindFileData) )
        {
          if ( GetLastError() != 18 )
          {
            v54 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x4D0,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                    v53);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v58);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpPathName);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
            return v54;
          }
          if ( a7 )
            *a7 = v57;
          goto LABEL_88;
        }
        if ( (unsigned int)v57 >= a6 )
        {
          if ( a7 )
            *a7 = v57;
LABEL_88:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpPathName);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
          return 0;
        }
      }
      v27 = -1;
      do
        ++v27;
      while ( FindFileData.cFileName[v27] );
      v66[0] = L".";
      v66[1] = 1;
      v67[0] = FindFileData.cFileName;
      v67[1] = v27;
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v67, v66) )
        goto LABEL_83;
      v28 = -1;
      do
        ++v28;
      while ( FindFileData.cFileName[v28] );
      v68[0] = L"..";
      v68[1] = 2;
      v69[0] = FindFileData.cFileName;
      v69[1] = v28;
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v69, v68) )
        goto LABEL_83;
      *(_OWORD *)v64 = *(_OWORD *)a2;
      *(_OWORD *)v60 = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, v73);
      if ( !(unsigned __int8)Microsoft::Diagnostics::Utils::FileSystem::ValidatePathStartsWith(v60, v64) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x42F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
          (const char *)0x8007010BLL,
          pbCancel);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v58);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpPathName);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
        return 2147942667LL;
      }
      *(_OWORD *)v60 = *(_OWORD *)a3;
      *(_OWORD *)v64 = *(_OWORD *)std::wstring::operator std::wstring_view(lpPathName, v74);
      if ( !(unsigned __int8)Microsoft::Diagnostics::Utils::FileSystem::ValidatePathStartsWith(v64, v60) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x430,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
          (const char *)0x8007010BLL,
          pbCancel);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v58);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpPathName);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
        return 2147942667LL;
      }
      Microsoft::Diagnostics::Utils::String::PrependLongPathUnicodePrefix(lpPathName);
      v29 = (const WCHAR *)lpPathName;
      if ( v90 > 7 )
        v29 = lpPathName[0];
      if ( CreateDirectoryW(v29, 0) )
      {
        if ( a4 )
        {
          Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
          *(_OWORD *)v60 = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, v75);
          Microsoft::Diagnostics::WideStringStream::AppendString((void *)(a4 + 168));
          Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
        }
        std::wstring::_Append<wchar_t>(lpPathName);
        std::wstring::_Append<wchar_t>(lpFileName);
        v32 = *(_OWORD *)std::wstring::operator std::wstring_view(lpPathName, v76);
        v33 = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, v77);
        v34 = std::operator+<wchar_t>(v92, lpFileName, L"*");
        *(_OWORD *)v60 = v32;
        *(_OWORD *)v64 = v33;
        *(_OWORD *)v59 = *(_OWORD *)std::wstring::operator std::wstring_view(v34, v78);
        LOBYTE(pbCancel) = a5;
        v35 = Microsoft::Diagnostics::Utils::FileSystem::CopyFiles(
                (int)v59,
                (int)v64,
                (int)v60,
                a4,
                pbCancel,
                a6,
                (__int64)&v57,
                dwCopyFlags,
                a9,
                (__int64)v63,
                v62,
                v61);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v92);
        if ( v35 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x456,
            (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
            (const char *)(unsigned int)v35,
            pbCancel);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpPathName);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
          return (unsigned int)v35;
        }
        if ( a5 )
        {
          v36 = (const WCHAR *)lpFileName;
          if ( v88 > 7 )
            v36 = lpFileName[0];
          SetFileAttributesW(v36, 0x10u);
          v37 = (const WCHAR *)lpFileName;
          if ( v88 > 7 )
            v37 = lpFileName[0];
          RemoveDirectoryW(v37);
        }
        goto LABEL_83;
      }
      if ( GetLastError() != 206 )
      {
        v31 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x446,
                (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                v30);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v58);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpPathName);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
        return v31;
      }
      if ( a4 )
      {
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
      }
    }
  }
  v55 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x40A,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
          v18);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v58);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpPathName);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
  return v55;
}

```

## disassembly

```asm
0x18020fc20  mov     rax, rsp
0x18020fc23  push    rbx
0x18020fc24  push    rsi
0x18020fc25  push    rdi
0x18020fc26  push    r12
0x18020fc28  push    r13
0x18020fc2a  push    r14
0x18020fc2c  push    r15
0x18020fc2e  sub     rsp, 540h
0x18020fc35  movaps  xmmword ptr [rax-48h], xmm6
0x18020fc39  movaps  xmmword ptr [rax-58h], xmm7
0x18020fc3d  mov     rax, cs:__security_cookie
0x18020fc44  xor     rax, rsp
0x18020fc47  mov     [rsp+578h+var_68], rax
0x18020fc4f  mov     r14, r9
0x18020fc52  mov     r13, r8
0x18020fc55  mov     r12, rdx
0x18020fc58  mov     rbx, rcx
0x18020fc5b  mov     r15, [rsp+578h+arg_30]
0x18020fc63  mov     rax, [rsp+578h+arg_48]
0x18020fc6b  mov     [rsp+578h+var_4D8], rax
0x18020fc73  mov     rax, [rsp+578h+arg_50]
0x18020fc7b  mov     [rsp+578h+var_4E0], rax
0x18020fc83  mov     rax, [rsp+578h+arg_58]
0x18020fc8b  mov     [rsp+578h+var_4E8], rax
0x18020fc93  xor     edx, edx; Val
0x18020fc95  mov     r8d, 250h; Size
0x18020fc9b  lea     rcx, [rsp+578h+FindFileData]; void *
0x18020fca3  call    memset_0
0x18020fca8  lea     rcx, [rsp+578h+lpFileName]; void *
0x18020fcb0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18020fcb5  nop
0x18020fcb6  lea     rcx, [rsp+578h+lpPathName]; void *
0x18020fcbe  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18020fcc3  nop
0x18020fcc4  xor     esi, esi
0x18020fcc6  test    r15, r15
0x18020fcc9  mov     eax, esi
0x18020fccb  jz      short loc_18020FCD0
0x18020fccd  mov     eax, [r15]
0x18020fcd0  mov     dword ptr [rsp+578h+var_518], eax
0x18020fcd4  mov     rdx, rbx
0x18020fcd7  lea     rcx, [rsp+578h+var_2F8]
0x18020fcdf  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18020fce4  cmp     qword ptr [rax+18h], 7
0x18020fce9  jbe     short loc_18020FCEE
0x18020fceb  mov     rax, [rax]
0x18020fcee  lea     rdx, [rsp+578h+FindFileData]; lpFindFileData
0x18020fcf6  mov     rcx, rax; lpFileName
0x18020fcf9  call    cs:__imp_FindFirstFileW
0x18020fd00  nop     dword ptr [rax+rax+00h]
0x18020fd05  mov     rbx, rax
0x18020fd08  mov     [rsp+578h+var_510], rax
0x18020fd0d  lea     rcx, [rsp+578h+var_2F8]; this
0x18020fd15  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18020fd1a  lea     rax, [rbx-1]
0x18020fd1e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18020fd22  ja      loc_180210997
0x18020fd28  lea     rdi, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x18020fd2f  lea     rcx, [rsp+578h+FindFileData.cFileName]
0x18020fd37  or      rax, 0FFFFFFFFFFFFFFFFh
0x18020fd3b  inc     rax
0x18020fd3e  cmp     [rcx+rax*2], si
0x18020fd42  jnz     short loc_18020FD3B
0x18020fd44  lea     rcx, [rsp+578h+FindFileData.cFileName]
0x18020fd4c  mov     [rsp+578h+var_4B8], rcx
0x18020fd54  mov     [rsp+578h+var_4B0], rax
0x18020fd5c  lea     rdx, asc_1803943D8; "<>:\"/\\|?*"
0x18020fd63  lea     rcx, [rsp+578h+var_4B8]
0x18020fd6b  call    ?find_first_of@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA_KQEB_W_K@Z; std::wstring_view::find_first_of(wchar_t const * const,unsigned __int64)
0x18020fd70  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18020fd74  jnz     loc_18021094F
0x18020fd7a  mov     r8, [r12+8]
0x18020fd7f  mov     rdx, [r12]
0x18020fd83  lea     rcx, [rsp+578h+lpFileName]
0x18020fd8b  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18020fd90  lea     rcx, [rsp+578h+FindFileData.cFileName]
0x18020fd98  or      rax, 0FFFFFFFFFFFFFFFFh
0x18020fd9c  inc     rax
0x18020fd9f  cmp     [rcx+rax*2], si
0x18020fda3  jnz     short loc_18020FD9C
0x18020fda5  lea     rcx, [rsp+578h+FindFileData.cFileName]
0x18020fdad  mov     [rsp+578h+var_4A8], rcx
0x18020fdb5  mov     [rsp+578h+var_4A0], rax
0x18020fdbd  lea     rdx, [rsp+578h+var_4A8]
0x18020fdc5  lea     rcx, [rsp+578h+lpFileName]; pszPath
0x18020fdcd  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x18020fdd2  mov     esi, eax
0x18020fdd4  test    eax, eax
0x18020fdd6  jns     short loc_18020FE1E
0x18020fdd8  mov     rcx, [rsp+578h]; this
0x18020fde0  mov     r9d, eax; char *
0x18020fde3  mov     r8, rdi; unsigned int
0x18020fde6  mov     edx, 417h; void *
0x18020fdeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020fdf0  nop
0x18020fdf1  lea     rcx, [rsp+578h+var_510]
0x18020fdf6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18020fdfb  nop
0x18020fdfc  lea     rcx, [rsp+578h+lpPathName]; this
0x18020fe04  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18020fe09  nop
0x18020fe0a  lea     rcx, [rsp+578h+lpFileName]; this
0x18020fe12  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18020fe17  mov     eax, esi
0x18020fe19  jmp     loc_1802109E0
0x18020fe1e  mov     r8, [r13+8]
0x18020fe22  mov     rdx, [r13+0]
0x18020fe26  lea     rcx, [rsp+578h+lpPathName]
0x18020fe2e  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18020fe33  lea     rdx, [rsp+578h+FindFileData.cFileName]
0x18020fe3b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18020fe3f  xor     ecx, ecx
0x18020fe41  inc     rax
0x18020fe44  cmp     [rdx+rax*2], cx
0x18020fe48  jnz     short loc_18020FE41
0x18020fe4a  lea     rcx, [rsp+578h+FindFileData.cFileName]
0x18020fe52  mov     [rsp+578h+var_498], rcx
0x18020fe5a  mov     [rsp+578h+var_490], rax
0x18020fe62  lea     rdx, [rsp+578h+var_498]
0x18020fe6a  lea     rcx, [rsp+578h+lpPathName]; pszPath
0x18020fe72  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x18020fe77  mov     esi, eax
0x18020fe79  test    eax, eax
0x18020fe7b  jns     short loc_18020FEC3
0x18020fe7d  mov     rcx, [rsp+578h]; this
0x18020fe85  mov     r9d, eax; char *
0x18020fe88  mov     r8, rdi; unsigned int
0x18020fe8b  mov     edx, 41Ah; void *
0x18020fe90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020fe95  nop
0x18020fe96  lea     rcx, [rsp+578h+var_510]
0x18020fe9b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18020fea0  nop
0x18020fea1  lea     rcx, [rsp+578h+lpPathName]; this
0x18020fea9  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18020feae  nop
0x18020feaf  lea     rcx, [rsp+578h+lpFileName]; this
0x18020feb7  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18020febc  mov     eax, esi
0x18020febe  jmp     loc_1802109E0
0x18020fec3  test    byte ptr [rsp+578h+FindFileData.dwFileAttributes], 10h
0x18020fecb  jz      loc_1802103EB
0x18020fed1  lea     rcx, [rsp+578h+FindFileData.cFileName]
0x18020fed9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18020fedd  xor     esi, esi
0x18020fedf  inc     rax
0x18020fee2  cmp     [rcx+rax*2], si
0x18020fee6  jnz     short loc_18020FEDF
0x18020fee8  lea     rcx, PathName; "."
0x18020feef  mov     [rsp+578h+var_488], rcx
0x18020fef7  mov     [rsp+578h+var_480], 1
0x18020ff03  lea     rcx, [rsp+578h+FindFileData.cFileName]
0x18020ff0b  mov     [rsp+578h+var_478], rcx
0x18020ff13  mov     [rsp+578h+var_470], rax
0x18020ff1b  lea     rdx, [rsp+578h+var_488]
0x18020ff23  lea     rcx, [rsp+578h+var_478]
0x18020ff2b  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18020ff30  test    eax, eax
0x18020ff32  jz      loc_18021085C
0x18020ff38  lea     rcx, [rsp+578h+FindFileData.cFileName]
0x18020ff40  or      rax, 0FFFFFFFFFFFFFFFFh
0x18020ff44  inc     rax
0x18020ff47  cmp     [rcx+rax*2], si
0x18020ff4b  jnz     short loc_18020FF44
0x18020ff4d  lea     rcx, asc_180394498; ".."
0x18020ff54  mov     [rsp+578h+var_468], rcx
0x18020ff5c  mov     [rsp+578h+var_460], 2
0x18020ff68  lea     rcx, [rsp+578h+FindFileData.cFileName]
0x18020ff70  mov     [rsp+578h+var_458], rcx
0x18020ff78  mov     [rsp+578h+var_450], rax
0x18020ff80  lea     rdx, [rsp+578h+var_468]
0x18020ff88  lea     rcx, [rsp+578h+var_458]
0x18020ff90  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18020ff95  test    eax, eax
0x18020ff97  jz      loc_18021085C
0x18020ff9d  movups  xmm0, xmmword ptr [r12]
0x18020ffa2  movdqu  xmmword ptr [rsp+578h+var_4C8], xmm0
0x18020ffab  lea     rdx, [rsp+578h+var_418]
0x18020ffb3  lea     rcx, [rsp+578h+lpFileName]
0x18020ffbb  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18020ffc0  movups  xmm0, xmmword ptr [rax]
0x18020ffc3  movdqu  xmmword ptr [rsp+578h+var_4F8], xmm0
0x18020ffcc  lea     rdx, [rsp+578h+var_4C8]
0x18020ffd4  lea     rcx, [rsp+578h+var_4F8]
0x18020ffdc  call    ?ValidatePathStartsWith@FileSystem@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::FileSystem::ValidatePathStartsWith(std::wstring_view,std::wstring_view)
0x18020ffe1  test    al, al
0x18020ffe3  jnz     short loc_180210030
0x18020ffe5  mov     rcx, [rsp+578h]; this
0x18020ffed  mov     ebx, 8007010Bh
0x18020fff2  mov     r9d, ebx; char *
0x18020fff5  mov     r8, rdi; unsigned int
0x18020fff8  mov     edx, 42Fh; void *
0x18020fffd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180210002  nop
0x180210003  lea     rcx, [rsp+578h+var_510]
0x180210008  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18021000d  nop
0x18021000e  lea     rcx, [rsp+578h+lpPathName]; this
0x180210016  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18021001b  nop
0x18021001c  lea     rcx, [rsp+578h+lpFileName]; this
0x180210024  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180210029  mov     eax, ebx
0x18021002b  jmp     loc_1802109E0
0x180210030  movups  xmm0, xmmword ptr [r13+0]
0x180210035  movdqu  xmmword ptr [rsp+578h+var_4F8], xmm0
0x18021003e  lea     rdx, [rsp+578h+var_408]
0x180210046  lea     rcx, [rsp+578h+lpPathName]
0x18021004e  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180210053  movups  xmm0, xmmword ptr [rax]
0x180210056  movdqu  xmmword ptr [rsp+578h+var_4C8], xmm0
0x18021005f  lea     rdx, [rsp+578h+var_4F8]
0x180210067  lea     rcx, [rsp+578h+var_4C8]
0x18021006f  call    ?ValidatePathStartsWith@FileSystem@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::FileSystem::ValidatePathStartsWith(std::wstring_view,std::wstring_view)
0x180210074  test    al, al
0x180210076  jnz     short loc_1802100C3
0x180210078  mov     rcx, [rsp+578h]; this
0x180210080  mov     ebx, 8007010Bh
0x180210085  mov     r9d, ebx; char *
0x180210088  mov     r8, rdi; unsigned int
0x18021008b  mov     edx, 430h; void *
0x180210090  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180210095  nop
0x180210096  lea     rcx, [rsp+578h+var_510]
0x18021009b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1802100a0  nop
0x1802100a1  lea     rcx, [rsp+578h+lpPathName]; this
0x1802100a9  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802100ae  nop
0x1802100af  lea     rcx, [rsp+578h+lpFileName]; this
0x1802100b7  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802100bc  mov     eax, ebx
0x1802100be  jmp     loc_1802109E0
0x1802100c3  lea     rcx, [rsp+578h+lpPathName]; Src
0x1802100cb  call    ?PrependLongPathUnicodePrefix@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::PrependLongPathUnicodePrefix(std::wstring &)
0x1802100d0  lea     rcx, [rsp+578h+lpPathName]
0x1802100d8  cmp     [rsp+578h+var_300], 7
0x1802100e1  cmova   rcx, [rsp+578h+lpPathName]; lpPathName
0x1802100ea  xor     edx, edx; lpSecurityAttributes
0x1802100ec  call    cs:__imp_CreateDirectoryW
0x1802100f3  nop     dword ptr [rax+rax+00h]
0x1802100f8  test    eax, eax
0x1802100fa  jnz     loc_1802101AE
0x180210100  call    cs:__imp_GetLastError
0x180210107  nop     dword ptr [rax+rax+00h]
0x18021010c  cmp     eax, 0CEh
0x180210111  jnz     short loc_18021016A
0x180210113  test    r14, r14
0x180210116  jz      loc_18020FD2F
0x18021011c  lea     rsi, [r14+0A8h]
0x180210123  lea     rdx, aPathExceededMa; "Path exceeded maximum length. Failed to"...
0x18021012a  mov     rcx, rsi; Src
0x18021012d  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180210132  lea     rdx, [rsp+578h+lpPathName]
0x18021013a  cmp     [rsp+578h+var_300], 7
0x180210143  cmova   rdx, [rsp+578h+lpPathName]
0x18021014c  mov     rcx, rsi; Src
0x18021014f  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180210154  lea     rdx, asc_1803721B4; "\r\n"
0x18021015b  mov     rcx, rsi; Src
0x18021015e  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180210163  xor     esi, esi
0x180210165  jmp     loc_18020FD2F
0x18021016a  mov     rcx, [rsp+578h]; this
0x180210172  mov     r8, rdi; unsigned int
0x180210175  mov     edx, 446h; void *
0x18021017a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18021017f  mov     ebx, eax
0x180210181  lea     rcx, [rsp+578h+var_510]
0x180210186  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18021018b  nop
0x18021018c  lea     rcx, [rsp+578h+lpPathName]; this
0x180210194  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180210199  nop
0x18021019a  lea     rcx, [rsp+578h+lpFileName]; this
0x1802101a2  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802101a7  mov     eax, ebx
0x1802101a9  jmp     loc_1802109E0
0x1802101ae  test    r14, r14
0x1802101b1  jz      short loc_180210209
0x1802101b3  lea     rsi, [r14+0A8h]
0x1802101ba  lea     rdx, aCreatedDirecto; "Created directory: "
0x1802101c1  mov     rcx, rsi; Src
0x1802101c4  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1802101c9  lea     rdx, [rsp+578h+var_3F8]
0x1802101d1  lea     rcx, [rsp+578h+lpFileName]
0x1802101d9  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802101de  movups  xmm0, xmmword ptr [rax]
0x1802101e1  movdqu  xmmword ptr [rsp+578h+var_4F8], xmm0
0x1802101ea  lea     rdx, [rsp+578h+var_4F8]
0x1802101f2  mov     rcx, rsi; Src
0x1802101f5  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1802101fa  lea     rdx, asc_1803721B4; "\r\n"
0x180210201  mov     rcx, rsi; Src
0x180210204  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180210209  mov     esi, 1
0x18021020e  mov     r8d, esi
0x180210211  lea     rdx, asc_1803772C8; "\\"
0x180210218  lea     rcx, [rsp+578h+lpPathName]; Src
  ... truncated ...
```
