# InstallManifestCommand::Execute(void)

- ea: `0x140001ce0`
- end: `0x140002b93`
- name: `?Execute@InstallManifestCommand@@UEAAXXZ`
- size: `3763`
- prototype: `void __fastcall(InstallManifestCommand *__hidden this)`
- caller_count: `0`
- callee_count: `31`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000116c`
- `0x140001bf0`
- `0x140001ce0`
- `0x140002b9c`
- `0x140002bd0`
- `0x140002c70`
- `0x140004ae0`
- `0x140005600`
- `0x14000cabc`
- `0x14000cc04`
- `0x14000d8c4`
- `0x140010450`
- `0x140011320`
- `0x140011570`
- `0x14001663c`
- `0x1400175f8`
- `0x140018ce4`
- `0x14001ae18`
- `0x140021b00`
- `0x140022510`
- `0x140022cec`
- `0x140023c6c`
- `0x140027480`
- `0x1400276c0`
- `0x1400276f0`
- `0x14002a6d4`
- `0x14002f6c8`
- `0x14002f9f4`
- `0x140031804`
- `0x140031810`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x140001f26`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x140001f26`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140001fb2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140001fb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001d2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001d2d`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140001d70`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140001d70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001dbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001fbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001dbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001fbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002068`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400029e4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400029e4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140002134`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140002134`
- `OLEAUT32!__imp_SysFreeString` at `0x140002991`
- `OLEAUT32!__imp_SysFreeString` at `0x1400029a4`
- `OLEAUT32!__imp_SysFreeString` at `0x140002991`
- `OLEAUT32!__imp_SysFreeString` at `0x1400029a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000204f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000205d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002355`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400028a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000204f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000205d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002355`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400028a6`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140001d3e`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140001d3e`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x1400020ef`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x1400020ef`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x140001db1`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x140001db1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000203f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000203f`
- `ntdll!RtlNtStatusToDosError` at `0x140002b63`
- `ntdll!RtlNtStatusToDosError` at `0x140002b63`
- `ntdll!NtCommitRegistryTransaction` at `0x140002742`
- `ntdll!NtCommitRegistryTransaction` at `0x140002742`
- `ntdll!NtCreateRegistryTransaction` at `0x14000236e`
- `ntdll!NtCreateRegistryTransaction` at `0x14000236e`

## string_xrefs

- `0x140001e5f`: `%SystemRoot%\System32\wevtutil.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall InstallManifestCommand::Execute(InstallManifestCommand *this)
{
  InstallManifestCommand *v1; // rsi
  HANDLE CurrentProcess; // rax
  WINBOOL v3; // eax
  LPWSTR CommandLineW; // rdx
  DWORD LastError; // ebx
  const char *v6; // r8
  PVOID v7; // rbx
  unsigned int v8; // edi
  WCHAR *v9; // rdx
  DWORD v10; // ebx
  const char *v11; // r8
  DWORD v12; // edi
  DWORD v13; // ebx
  const char *v14; // r8
  HRESULT v15; // ebx
  char *v16; // rsi
  InstallManifestCommand *v17; // r13
  wchar_t *v18; // rdx
  void *v19; // rbx
  ManifestProcessor *v20; // rdi
  PVOID *v21; // r10
  __int64 v22; // rcx
  unsigned int v23; // ebx
  _QWORD *v24; // r12
  _QWORD *v25; // rbx
  void *v26; // rax
  __int64 v27; // r8
  __int64 v28; // rax
  ManifestProcessor *v29; // rbx
  ManifestProcessor *v30; // rdx
  wmi::RefBase *v31; // rbx
  wmi::RefBase **v32; // r12
  const wchar_t *v33; // rax
  unsigned int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // r8
  unsigned int v37; // ebx
  PVOID *v38; // rcx
  unsigned int v39; // r8d
  unsigned int v40; // eax
  unsigned int v41; // ebx
  __int64 v42; // rcx
  unsigned int v43; // ebx
  PVOID *v44; // rcx
  ULONG v45; // eax
  const char *v46; // r8
  ChannelConfigException *v47; // rbx
  const wchar_t *ChannelPropertyName; // rax
  const char *bInheritHandles; // [rsp+20h] [rbp-478h]
  const char *bInheritHandlesa; // [rsp+20h] [rbp-478h]
  unsigned int v51; // [rsp+80h] [rbp-418h]
  PVOID OldValue; // [rsp+88h] [rbp-410h] BYREF
  WINBOOL Wow64Process; // [rsp+90h] [rbp-408h] BYREF
  int v54; // [rsp+94h] [rbp-404h]
  ManifestProcessor *v55; // [rsp+98h] [rbp-400h]
  HANDLE hObject; // [rsp+A0h] [rbp-3F8h] BYREF
  HANDLE v57; // [rsp+A8h] [rbp-3F0h]
  char v58; // [rsp+B1h] [rbp-3E7h]
  void *v59; // [rsp+B8h] [rbp-3E0h] BYREF
  char v60[8]; // [rsp+C0h] [rbp-3D8h] BYREF
  _BYTE *v61; // [rsp+C8h] [rbp-3D0h]
  wmi::RefBase *v62[2]; // [rsp+D0h] [rbp-3C8h] BYREF
  ManifestProcessor *v63; // [rsp+E0h] [rbp-3B8h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+F0h] [rbp-3A8h] BYREF
  void **v65; // [rsp+110h] [rbp-388h] BYREF
  int v66; // [rsp+118h] [rbp-380h]
  BSTR bstrString[2]; // [rsp+120h] [rbp-378h]
  void *v68; // [rsp+130h] [rbp-368h] BYREF
  PVOID v69; // [rsp+140h] [rbp-358h]
  _BYTE *v70; // [rsp+148h] [rbp-350h]
  __int64 v71; // [rsp+150h] [rbp-348h]
  void *v72; // [rsp+158h] [rbp-340h]
  char *v73; // [rsp+160h] [rbp-338h]
  InstallManifestCommand *v74; // [rsp+168h] [rbp-330h]
  _QWORD v75[3]; // [rsp+178h] [rbp-320h] BYREF
  unsigned int v76; // [rsp+190h] [rbp-308h]
  __int64 v77; // [rsp+194h] [rbp-304h]
  char v78; // [rsp+19Ch] [rbp-2FCh]
  LPCWSTR lpApplicationName[4]; // [rsp+1A0h] [rbp-2F8h] BYREF
  EvtException *v80; // [rsp+1C0h] [rbp-2D8h] BYREF
  ChannelConfigException *v81; // [rsp+1C8h] [rbp-2D0h] BYREF
  _BYTE v82[32]; // [rsp+1D0h] [rbp-2C8h] BYREF
  _BYTE v83[32]; // [rsp+1F0h] [rbp-2A8h] BYREF
  _BYTE v84[32]; // [rsp+210h] [rbp-288h] BYREF
  _BYTE v85[32]; // [rsp+230h] [rbp-268h] BYREF
  void *v86; // [rsp+250h] [rbp-248h]
  _STARTUPINFOW StartupInfo; // [rsp+260h] [rbp-238h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+2D0h] [rbp-1C8h] BYREF
  _BYTE v89[40]; // [rsp+2F8h] [rbp-1A0h] BYREF
  _BYTE v90[40]; // [rsp+320h] [rbp-178h] BYREF
  _BYTE v91[40]; // [rsp+348h] [rbp-150h] BYREF
  _BYTE v92[40]; // [rsp+370h] [rbp-128h] BYREF
  _BYTE v93[40]; // [rsp+398h] [rbp-100h] BYREF
  _BYTE v94[40]; // [rsp+3C0h] [rbp-D8h] BYREF
  _BYTE v95[40]; // [rsp+3E8h] [rbp-B0h] BYREF
  _BYTE v96[48]; // [rsp+410h] [rbp-88h] BYREF
  WCHAR CommandLine[4]; // [rsp+440h] [rbp-58h] BYREF
  __int64 v98; // [rsp+448h] [rbp-50h]
  unsigned __int64 v99; // [rsp+458h] [rbp-40h]

  v1 = this;
  v74 = this;
  v54 = 1;
  Wow64Process = 0;
  CurrentProcess = GetCurrentProcess();
  if ( IsWow64Process(CurrentProcess, &Wow64Process) )
  {
    v3 = Wow64Process;
  }
  else
  {
    v3 = 0;
    Wow64Process = 0;
  }
  if ( !*((_BYTE *)v1 + 169) && v3 )
  {
    CommandLineW = GetCommandLineW();
    std::wstring::wstring(CommandLine, CommandLineW);
    std::wstring::_Append<wchar_t>(CommandLine);
    OldValue = 0;
    if ( !Wow64DisableWow64FsRedirection(&OldValue) )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids, LastError);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, LastError, v6, 163);
      throw (EvtException *)pExceptionObject;
    }
    v7 = OldValue;
    v69 = OldValue;
    LOBYTE(v70) = 1;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpApplicationName);
    v8 = ExpandEnvStringNoThrow(L"%SystemRoot%\\System32\\wevtutil.exe");
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids, v8);
      }
      v75[0] = word_14003838A;
      v75[1] = 0;
      v75[2] = 0;
      v76 = v8;
      v77 = -1;
      v78 = 0;
      throw (EvtException *)v75;
    }
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    GetStartupInfoW(&StartupInfo);
    StartupInfo.wShowWindow = 4;
    StartupInfo.dwFlags = 128;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( v99 <= 7 )
      v9 = CommandLine;
    else
      v9 = *(WCHAR **)CommandLine;
    if ( !CreateProcessW(lpApplicationName[0], v9, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      v10 = GetLastError();
      if ( !v10 )
        v10 = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids, v10);
      }
      EvtException::EvtException((EvtException *)v89, v10, v11, 191);
      throw (EvtException *)v89;
    }
    v12 = WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
    CloseHandle(ProcessInformation.hThread);
    CloseHandle(ProcessInformation.hProcess);
    if ( v12 == -1 )
    {
      v13 = GetLastError();
      if ( !v13 )
        v13 = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids, v13);
      }
      EvtException::EvtException((EvtException *)v90, v13, v14, 201);
      throw (EvtException *)v90;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpApplicationName);
    Wow64RevertWow64FsRedirection(v7);
    std::wstring::_Tidy_deallocate(CommandLine);
    return;
  }
  v15 = CoInitializeEx(0, 0);
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids,
        (unsigned int)v15);
    }
    v16 = (char *)v1 + 40;
    if ( *((_QWORD *)v16 + 3) > 7u )
      v16 = *(char **)v16;
    EvtException::EvtException((EvtException *)v91, v15, 0, 0, bInheritHandlesa, 210, 0x20u, (const wchar_t *)v16);
    throw (EvtException *)v91;
  }
  v17 = v1;
  v58 = 1;
  v73 = (char *)v1 + 40;
  v62[1] = (InstallManifestCommand *)((char *)v1 + 40);
  if ( *((_QWORD *)v1 + 8) <= 7u )
    v18 = (wchar_t *)((char *)v1 + 40);
  else
    v18 = (wchar_t *)*((_QWORD *)v1 + 5);
  XmlLoad(v60, v18);
  InstallManifestCommand::GetEventsNode(v1, &v59, *(_QWORD *)v60);
  v19 = v59;
  OldValue = v59;
  if ( v59 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v59 + 8LL))(v59);
  v66 = 0;
  v65 = &MsxmlDomElement::`vftable';
  *(_OWORD *)bstrString = 0;
  v68 = v19;
  if ( v19 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 8LL))(v19);
    winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&OldValue);
  }
  v20 = 0;
  v63 = 0;
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>(v85);
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>(v84);
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>(v83);
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>(v82);
  v51 = v54;
  v21 = (PVOID *)WPP_GLOBAL_Control;
  do
  {
    v22 = -1;
    hObject = (HANDLE)-1LL;
    if ( v21 != &WPP_GLOBAL_Control && (*((_DWORD *)v21 + 7) & 0x400000) != 0 && *((_BYTE *)v21 + 25) >= 4u )
    {
      WPP_SF_(v21[2], 25);
      v22 = (__int64)hObject;
    }
    hObject = 0;
    if ( (unsigned __int64)(v22 + 1) > 1 )
      CloseHandle((HANDLE)v22);
    v23 = NtCreateRegistryTransaction(&hObject, 2031679, 0, 0);
    if ( v23 || hObject == (HANDLE)-1LL || (char *)hObject + 1 == HANDLE_FLAG_INHERIT )
    {
      v44 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids, v23);
        v44 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !v23 )
        v23 = -1073741595;
      if ( v44 != &WPP_GLOBAL_Control && (*((_DWORD *)v44 + 7) & 0x400000) != 0 && *((_BYTE *)v44 + 25) >= 2u )
        WPP_SF_d(v44[2], 27, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids, v23);
      v45 = RtlNtStatusToDosError(v23);
      EvtException::EvtException((EvtException *)v95, v45, v46, 241);
      throw (EvtException *)v95;
    }
    utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::clear(v85);
    utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::clear(v84);
    utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::clear(v83);
    utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::clear(v82);
    v55 = (InstallManifestCommand *)((char *)v1 + 136);
    if ( *((_QWORD *)v1 + 20) > 7u )
      v55 = (ManifestProcessor *)*((_QWORD *)v1 + 17);
    v71 = *((_QWORD *)v17 + 19);
    v24 = (_QWORD *)((char *)v1 + 104);
    if ( *((_QWORD *)v1 + 16) > 7u )
      v24 = (_QWORD *)*v24;
    v72 = (void *)*((_QWORD *)v17 + 15);
    v25 = (_QWORD *)((char *)v1 + 72);
    if ( *((_QWORD *)v1 + 12) > 7u )
      v25 = (_QWORD *)*v25;
    v61 = (_BYTE *)*((_QWORD *)v17 + 11);
    v57 = hObject;
    v26 = operator new(0xB0u);
    v86 = v26;
    if ( v26 )
    {
      *(_QWORD *)CommandLine = v55;
      v98 = v71;
      ProcessInformation.hProcess = v24;
      ProcessInformation.hThread = v72;
      v69 = v25;
      v70 = v61;
      v28 = ManifestProcessor::ManifestProcessor(v26, -2147483646, v27, -2147483646);
      v29 = (ManifestProcessor *)v28;
    }
    else
    {
      v29 = 0;
    }
    v55 = v29;
    v30 = v20;
    v20 = v29;
    v63 = v29;
    if ( v30 )
      ((void (*)(void))std::default_delete<ManifestProcessor>::operator())();
    try
    {
      v61 = (char *)v1 + 168;
      if ( *((_BYTE *)v1 + 168) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids);
        }
        ((void (__fastcall *)(void ***, PVOID *))v65[3])(&v65, &OldValue);
        v31 = 0;
        v57 = 0;
        while ( 1 )
        {
          v32 = (wmi::RefBase **)(*(__int64 (__fastcall **)(PVOID, wmi::RefBase **))(*(_QWORD *)OldValue + 8LL))(
                                   OldValue,
                                   v62);
          if ( v31 )
            wmi::RefBase::Release(v31);
          v31 = *v32;
          v57 = *v32;
          *v32 = 0;
          if ( v62[0] )
            wmi::RefBase::Release(v62[0]);
          v62[0] = 0;
          if ( !v31 )
            break;
          v33 = (const wchar_t *)(*(__int64 (__fastcall **)(wmi::RefBase *))(*(_QWORD *)v31 + 16LL))(v31);
          if ( !wcscmp_0(L"provider", v33) )
            ManifestProcessor::ProcessProviderNode(v55, v31);
        }
        if ( OldValue )
          wmi::RefBase::Release((wmi::RefBase *)OldValue);
        OldValue = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids);
        }
        utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>(lpApplicationName);
        ManifestProcessor::Remove(v29, (struct AbstractDomElement *)&v65, (const struct StringSet *)lpApplicationName);
        utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::clear(lpApplicationName);
      }
      v34 = NtCommitRegistryTransaction(hObject, 0);
    }
    catch ( ChannelConfigException *v81 )
    {
      v47 = v81;
      if ( *((_DWORD *)v81 + 5) != 4 )
        throw;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids, 15000);
      }
      ChannelPropertyName = GetChannelPropertyName(*((_DWORD *)v47 + 5));
      EvtException::EvtException((EvtException *)v92, 0x3A98u, 0, 0, bInheritHandles, 286, 0x5Au, ChannelPropertyName);
      throw (EvtException *)v92;
    }
    catch ( EvtException *v80 )
    {
      if ( *((_DWORD *)v80 + 6) == 6701 )
      {
        LODWORD(v55) = -1072103421;
        v20 = v63;
        v37 = -1072103421;
        v1 = v74;
        v17 = v74;
        goto LABEL_113;
      }
      throw;
    }
    v37 = v34;
    if ( !v34 )
    {
      v37 = 0;
      goto LABEL_113;
    }
    if ( v34 != -1072103403 )
    {
      v38 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LODWORD(bInheritHandlesa) = v34;
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v35, v36, v51);
          v38 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v38 != &WPP_GLOBAL_Control && (*((_DWORD *)v38 + 7) & 0x400000) != 0 && *((_BYTE *)v38 + 25) >= 2u )
          WPP_SF_d(v38[2], 33, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids, v37);
      }
      EvtException::EvtException((EvtException *)v96, v37, 0, 0, bInheritHandlesa, 318, 0x3Eu, 0);
      throw (EvtException *)v96;
    }
    v21 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids, v51);
LABEL_113:
      v21 = (PVOID *)WPP_GLOBAL_Control;
    }
    v39 = v51;
    if ( (unsigned __int64)hObject + 1 > 1 )
    {
      CloseHandle(hObject);
      v21 = (PVOID *)WPP_GLOBAL_Control;
      v39 = v51;
    }
    if ( v37 != -1072103403 && v37 != -1072103421 )
      break;
    v54 |= 2u;
    v51 = v39 + 1;
  }
  while ( v39 + 1 <= 3 );
  if ( v37 )
  {
    v43 = v37 | 0x10000000;
    if ( v21 != &WPP_GLOBAL_Control && (*((_DWORD *)v21 + 7) & 0x400000) != 0 && *((_BYTE *)v21 + 25) >= 2u )
      WPP_SF_d(v21[2], 35, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids, v43);
    EvtException::EvtException((EvtException *)v94, v43, 0, 0, bInheritHandlesa, 349, 0x5Du, 0);
    throw (EvtException *)v94;
  }
  v40 = ManifestProcessor::AssertRetractChanges(v20);
  v41 = v40;
  if ( *v61 )
  {
    InstallManifestCommand::ValidateInstalledProviders(v1, (struct MsxmlDomElement *)&v65, v40);
  }
  else if ( v40 && v40 != 126 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids, v40);
    }
    EvtException::EvtException((EvtException *)v93, v41, 0, 0, bInheritHandlesa, 344, 0x3Eu, 0);
    throw (EvtException *)v93;
  }
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::clear(v82);
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::clear(v83);
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::clear(v84);
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::clear(v85);
  if ( v20 )
    std::default_delete<ManifestProcessor>::operator()(v42, v20);
  if ( v68 )
    winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v68);
  if ( bstrString[1] )
    SysFreeString(bstrString[1]);
  if ( bstrString[0] )
    SysFreeString(bstrString[0]);
  v65 = &wmi::RefBase::`vftable';
  if ( v59 )
    winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v59);
  if ( *(_QWORD *)v60 )
    winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(v60);
  CoUninitialize();
}

```

## disassembly

```asm
0x140001ce0  mov     [rsp+arg_8], rbx
0x140001ce5  mov     [rsp+arg_10], rsi
0x140001cea  push    rdi
0x140001ceb  push    r12
0x140001ced  push    r13
0x140001cef  push    r14
0x140001cf1  push    r15
0x140001cf3  sub     rsp, 470h
0x140001cfa  mov     rax, cs:__security_cookie
0x140001d01  xor     rax, rsp
0x140001d04  mov     [rsp+498h+var_38], rax
0x140001d0c  mov     rsi, rcx
0x140001d0f  mov     [rsp+498h+var_330], rcx
0x140001d17  mov     [rsp+498h+var_404], 1
0x140001d22  xor     r14d, r14d
0x140001d25  mov     [rsp+498h+Wow64Process], r14d
0x140001d2d  call    cs:__imp_GetCurrentProcess
0x140001d33  mov     rcx, rax; hProcess
0x140001d36  lea     rdx, [rsp+498h+Wow64Process]; Wow64Process
0x140001d3e  call    cs:__imp_IsWow64Process
0x140001d44  test    eax, eax
0x140001d46  jnz     short loc_140001D54
0x140001d48  mov     eax, r14d
0x140001d4b  mov     [rsp+498h+Wow64Process], eax
0x140001d52  jmp     short loc_140001D5B
0x140001d54  mov     eax, [rsp+498h+Wow64Process]
0x140001d5b  cmp     [rsi+0A9h], r14b
0x140001d62  jnz     loc_140002130
0x140001d68  test    eax, eax
0x140001d6a  jz      loc_140002130
0x140001d70  call    cs:__imp_GetCommandLineW
0x140001d76  mov     rdx, rax
0x140001d79  lea     rcx, [rsp+498h+CommandLine]
0x140001d81  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140001d86  nop
0x140001d87  mov     r8d, 0Bh
0x140001d8d  lea     rdx, aFromwow64; " /fromwow64"
0x140001d94  lea     rcx, [rsp+498h+CommandLine]; Src
0x140001d9c  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x140001da1  mov     [rsp+498h+OldValue], r14
0x140001da9  lea     rcx, [rsp+498h+OldValue]; OldValue
0x140001db1  call    cs:__imp_Wow64DisableWow64FsRedirection
0x140001db7  test    eax, eax
0x140001db9  jnz     short loc_140001E31
0x140001dbb  call    cs:__imp_GetLastError
0x140001dc1  mov     ebx, eax
0x140001dc3  mov     eax, 507h
0x140001dc8  test    ebx, ebx
0x140001dca  cmovz   ebx, eax
0x140001dcd  lea     rax, WPP_GLOBAL_Control
0x140001dd4  mov     rcx, cs:WPP_GLOBAL_Control
0x140001ddb  cmp     rcx, rax
0x140001dde  jz      short loc_140001E07
0x140001de0  test    dword ptr [rcx+1Ch], 400000h
0x140001de7  jz      short loc_140001E07
0x140001de9  cmp     byte ptr [rcx+19h], 2
0x140001ded  jb      short loc_140001E07
0x140001def  mov     edx, 14h
0x140001df4  mov     r9d, ebx
0x140001df7  lea     r8, WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids
0x140001dfe  mov     rcx, [rcx+10h]
0x140001e02  call    WPP_SF_d
0x140001e07  mov     r9d, 0A3h; int
0x140001e0d  mov     edx, ebx; unsigned int
0x140001e0f  lea     rcx, [rsp+498h+pExceptionObject]; this
0x140001e17  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140001e1c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140001e23  lea     rcx, [rsp+498h+pExceptionObject]; pExceptionObject
0x140001e2b  call    _CxxThrowException_0
0x140001e31  mov     rbx, [rsp+498h+OldValue]
0x140001e39  mov     [rsp+498h+var_358], rbx
0x140001e41  mov     byte ptr [rsp+498h+var_350], 1
0x140001e49  lea     rcx, [rsp+498h+lpApplicationName]
0x140001e51  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140001e56  nop
0x140001e57  lea     rdx, [rsp+498h+lpApplicationName]
0x140001e5f  lea     rcx, aSystemrootSyst_0; "%SystemRoot%\\System32\\wevtutil.exe"
0x140001e66  call    ?ExpandEnvStringNoThrow@@YAKPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; ExpandEnvStringNoThrow(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x140001e6b  mov     edi, eax
0x140001e6d  test    eax, eax
0x140001e6f  jz      loc_140001EFE
0x140001e75  lea     rax, WPP_GLOBAL_Control
0x140001e7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e83  cmp     rcx, rax
0x140001e86  jz      short loc_140001EAF
0x140001e88  test    dword ptr [rcx+1Ch], 400000h
0x140001e8f  jz      short loc_140001EAF
0x140001e91  cmp     byte ptr [rcx+19h], 2
0x140001e95  jb      short loc_140001EAF
0x140001e97  mov     edx, 15h
0x140001e9c  mov     r9d, edi
0x140001e9f  lea     r8, WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids
0x140001ea6  mov     rcx, [rcx+10h]
0x140001eaa  call    WPP_SF_d
0x140001eaf  lea     rax, word_14003838A
0x140001eb6  mov     [rsp+498h+var_320], rax
0x140001ebe  mov     [rsp+498h+var_318], r14
0x140001ec6  mov     [rsp+498h+var_310], r14
0x140001ece  mov     [rsp+498h+var_308], edi
0x140001ed5  mov     [rsp+498h+var_304], 0FFFFFFFFFFFFFFFFh
0x140001ee1  mov     [rsp+498h+var_2FC], 0
0x140001ee9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140001ef0  lea     rcx, [rsp+498h+var_320]; pExceptionObject
0x140001ef8  call    _CxxThrowException_0
0x140001efe  xor     edx, edx; Val
0x140001f00  mov     r8d, 64h ; 'd'; Size
0x140001f06  lea     rcx, [rsp+498h+StartupInfo+4]; void *
0x140001f0e  call    memset_0
0x140001f13  mov     [rsp+498h+StartupInfo.cb], 68h ; 'h'
0x140001f1e  lea     rcx, [rsp+498h+StartupInfo]; lpStartupInfo
0x140001f26  call    cs:__imp_GetStartupInfoW
0x140001f2c  mov     eax, 4
0x140001f31  mov     [rsp+498h+StartupInfo.wShowWindow], ax
0x140001f39  mov     [rsp+498h+StartupInfo.dwFlags], 80h
0x140001f44  xorps   xmm0, xmm0
0x140001f47  xor     eax, eax
0x140001f49  movups  xmmword ptr [rsp+498h+ProcessInformation.hProcess], xmm0
0x140001f51  mov     qword ptr [rsp+498h+ProcessInformation.dwProcessId], rax
0x140001f59  cmp     [rsp+498h+var_40], 7
0x140001f62  jbe     short loc_140001F6E
0x140001f64  mov     rdx, qword ptr [rsp+498h+CommandLine]
0x140001f6c  jmp     short loc_140001F76
0x140001f6e  lea     rdx, [rsp+498h+CommandLine]; lpCommandLine
0x140001f76  lea     rax, [rsp+498h+ProcessInformation]
0x140001f7e  mov     [rsp+498h+lpProcessInformation], rax; lpProcessInformation
0x140001f83  lea     rax, [rsp+498h+StartupInfo]
0x140001f8b  mov     [rsp+498h+lpStartupInfo], rax; lpStartupInfo
0x140001f90  mov     [rsp+498h+lpCurrentDirectory], r14; lpCurrentDirectory
0x140001f95  mov     [rsp+498h+lpEnvironment], r14; lpEnvironment
0x140001f9a  mov     [rsp+498h+dwCreationFlags], r14d; dwCreationFlags
0x140001f9f  mov     dword ptr [rsp+498h+bInheritHandles], r14d; bInheritHandles
0x140001fa4  xor     r9d, r9d; lpThreadAttributes
0x140001fa7  xor     r8d, r8d; lpProcessAttributes
0x140001faa  mov     rcx, [rsp+498h+lpApplicationName]; lpApplicationName
0x140001fb2  call    cs:__imp_CreateProcessW
0x140001fb8  test    eax, eax
0x140001fba  jnz     short loc_140002032
0x140001fbc  call    cs:__imp_GetLastError
0x140001fc2  mov     ebx, eax
0x140001fc4  mov     eax, 507h
0x140001fc9  test    ebx, ebx
0x140001fcb  cmovz   ebx, eax
0x140001fce  lea     rax, WPP_GLOBAL_Control
0x140001fd5  mov     rcx, cs:WPP_GLOBAL_Control
0x140001fdc  cmp     rcx, rax
0x140001fdf  jz      short loc_140002008
0x140001fe1  test    dword ptr [rcx+1Ch], 400000h
0x140001fe8  jz      short loc_140002008
0x140001fea  cmp     byte ptr [rcx+19h], 2
0x140001fee  jb      short loc_140002008
0x140001ff0  mov     edx, 16h
0x140001ff5  mov     r9d, ebx
0x140001ff8  lea     r8, WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids
0x140001fff  mov     rcx, [rcx+10h]
0x140002003  call    WPP_SF_d
0x140002008  mov     r9d, 0BFh; int
0x14000200e  mov     edx, ebx; unsigned int
0x140002010  lea     rcx, [rsp+498h+var_1A0]; this
0x140002018  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14000201d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140002024  lea     rcx, [rsp+498h+var_1A0]; pExceptionObject
0x14000202c  call    _CxxThrowException_0
0x140002032  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x140002037  mov     rcx, [rsp+498h+ProcessInformation.hProcess]; hHandle
0x14000203f  call    cs:__imp_WaitForSingleObject
0x140002045  mov     edi, eax
0x140002047  mov     rcx, [rsp+498h+ProcessInformation.hThread]; hObject
0x14000204f  call    cs:__imp_CloseHandle
0x140002055  mov     rcx, [rsp+498h+ProcessInformation.hProcess]; hObject
0x14000205d  call    cs:__imp_CloseHandle
0x140002063  cmp     edi, 0FFFFFFFFh
0x140002066  jnz     short loc_1400020DE
0x140002068  call    cs:__imp_GetLastError
0x14000206e  mov     ebx, eax
0x140002070  mov     eax, 507h
0x140002075  test    ebx, ebx
0x140002077  cmovz   ebx, eax
0x14000207a  lea     rax, WPP_GLOBAL_Control
0x140002081  mov     rcx, cs:WPP_GLOBAL_Control
0x140002088  cmp     rcx, rax
0x14000208b  jz      short loc_1400020B4
0x14000208d  test    dword ptr [rcx+1Ch], 400000h
0x140002094  jz      short loc_1400020B4
0x140002096  cmp     byte ptr [rcx+19h], 2
0x14000209a  jb      short loc_1400020B4
0x14000209c  mov     edx, 17h
0x1400020a1  mov     r9d, ebx
0x1400020a4  lea     r8, WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids
0x1400020ab  mov     rcx, [rcx+10h]
0x1400020af  call    WPP_SF_d
0x1400020b4  mov     r9d, 0C9h; int
0x1400020ba  mov     edx, ebx; unsigned int
0x1400020bc  lea     rcx, [rsp+498h+var_178]; this
0x1400020c4  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x1400020c9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400020d0  lea     rcx, [rsp+498h+var_178]; pExceptionObject
0x1400020d8  call    _CxxThrowException_0
0x1400020de  lea     rcx, [rsp+498h+lpApplicationName]
0x1400020e6  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1400020eb  nop
0x1400020ec  mov     rcx, rbx; OlValue
0x1400020ef  call    cs:__imp_Wow64RevertWow64FsRedirection
0x1400020f5  nop
0x1400020f6  lea     rcx, [rsp+498h+CommandLine]
0x1400020fe  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140002103  mov     rcx, [rsp+498h+var_38]
0x14000210b  xor     rcx, rsp; StackCookie
0x14000210e  call    __security_check_cookie
0x140002113  lea     r11, [rsp+498h+var_28]
0x14000211b  mov     rbx, [r11+38h]
0x14000211f  mov     rsi, [r11+40h]
0x140002123  mov     rsp, r11
0x140002126  pop     r15
0x140002128  pop     r14
0x14000212a  pop     r13
0x14000212c  pop     r12
0x14000212e  pop     rdi
0x14000212f  retn
0x140002130  xor     edx, edx; dwCoInit
0x140002132  xor     ecx, ecx; pvReserved
0x140002134  call    cs:__imp_CoInitializeEx
0x14000213a  mov     ebx, eax
0x14000213c  test    eax, eax
0x14000213e  jns     loc_1400021CB
0x140002144  lea     rax, WPP_GLOBAL_Control
0x14000214b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002152  cmp     rcx, rax
0x140002155  jz      short loc_14000217E
0x140002157  test    dword ptr [rcx+1Ch], 400000h
0x14000215e  jz      short loc_14000217E
0x140002160  cmp     byte ptr [rcx+19h], 2
0x140002164  jb      short loc_14000217E
0x140002166  mov     edx, 18h
0x14000216b  mov     r9d, ebx
0x14000216e  lea     r8, WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids
0x140002175  mov     rcx, [rcx+10h]
0x140002179  call    WPP_SF_d
0x14000217e  add     rsi, 28h ; '('
0x140002182  cmp     qword ptr [rsi+18h], 7
0x140002187  jbe     short loc_14000218C
0x140002189  mov     rsi, [rsi]
0x14000218c  mov     [rsp+498h+lpCurrentDirectory], rsi; Src
0x140002191  mov     dword ptr [rsp+498h+lpEnvironment], 20h ; ' '; unsigned int
0x140002199  mov     [rsp+498h+dwCreationFlags], 0D2h; int
0x1400021a1  xor     r9d, r9d; unsigned int
0x1400021a4  xor     r8d, r8d; unsigned int
0x1400021a7  mov     edx, ebx; unsigned int
0x1400021a9  lea     rcx, [rsp+498h+var_150]; this
0x1400021b1  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x1400021b6  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400021bd  lea     rcx, [rsp+498h+var_150]; pExceptionObject
0x1400021c5  call    _CxxThrowException_0
0x1400021cb  mov     r13, rsi
0x1400021ce  mov     [rsp+498h+var_3E7], 1
0x1400021d6  lea     r15, [rsi+28h]
0x1400021da  mov     [rsp+498h+var_338], r15
0x1400021e2  mov     [rsp+498h+var_3C0], r15
0x1400021ea  cmp     qword ptr [r15+18h], 7
0x1400021ef  jbe     short loc_1400021F6
0x1400021f1  mov     rdx, [r15]
0x1400021f4  jmp     short loc_1400021F9
0x1400021f6  mov     rdx, r15; wchar_t *
0x1400021f9  lea     rcx, [rsp+498h+var_3D8]; char *
0x140002201  call    ?XmlLoad@@YA?AU?$com_ptr@UIXMLDOMDocument3@@@winrt@@PEB_W@Z; XmlLoad(wchar_t const *)
0x140002206  nop
0x140002207  mov     r8, qword ptr [rsp+498h+var_3D8]
0x14000220f  lea     rdx, [rsp+498h+var_3E0]
0x140002217  mov     rcx, rsi
0x14000221a  call    ?GetEventsNode@InstallManifestCommand@@AEAA?AU?$com_ptr@UIXMLDOMElement@@@winrt@@PEAUIXMLDOMDocument3@@@Z; InstallManifestCommand::GetEventsNode(IXMLDOMDocument3 *)
0x14000221f  nop
0x140002220  mov     rbx, [rsp+498h+var_3E0]
0x140002228  mov     [rsp+498h+OldValue], rbx
0x140002230  test    rbx, rbx
0x140002233  jz      short loc_140002245
0x140002235  mov     rax, [rbx]
0x140002238  mov     rcx, rbx
0x14000223b  mov     rax, [rax+8]
0x14000223f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002244  nop
0x140002245  lea     r12, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x14000224c  mov     [rsp+498h+var_388], r12
0x140002254  mov     [rsp+498h+var_380], r14d
0x14000225c  lea     rax, ??_7MsxmlDomElement@@6B@; const MsxmlDomElement::`vftable'
0x140002263  mov     [rsp+498h+var_388], rax
0x14000226b  xorps   xmm0, xmm0
0x14000226e  movdqu  xmmword ptr [rsp+498h+bstrString], xmm0
0x140002277  mov     [rsp+498h+var_368], rbx
0x14000227f  test    rbx, rbx
0x140002282  jz      short loc_140002294
0x140002284  mov     rax, [rbx]
0x140002287  mov     rcx, rbx
0x14000228a  mov     rax, [rax+8]
0x14000228e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002293  nop
0x140002294  test    rbx, rbx
0x140002297  jz      short loc_1400022A7
0x140002299  lea     rcx, [rsp+498h+OldValue]
0x1400022a1  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x1400022a6  nop
0x1400022a7  mov     rdi, r14
  ... truncated ...
```
