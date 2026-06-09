# StartupAppMonitor::StartMonitor(void)

- ea: `0x18012d7c8`
- end: `0x18012ddec`
- name: `?StartMonitor@StartupAppMonitor@@QEAAXXZ`
- size: `1572`
- prototype: `void __fastcall(StartupAppMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1802ce920`

## callees

- `0x180019a38`
- `0x180043f00`
- `0x180051b5c`
- `0x1800c0910`
- `0x1800d55f0`
- `0x1800d5fec`
- `0x1800d6928`
- `0x1800d7c50`
- `0x1800d7e94`
- `0x1800d7f48`
- `0x18012d7c8`
- `0x18012ddf4`
- `0x18012e2d0`
- `0x18012e3a4`
- `0x180271658`
- `0x1802bb1a4`
- `0x1802c5280`
- `0x1802d66a8`
- `0x1802f406c`
- `0x180339ce4`
- `0x180356360`
- `0x180356970`
- `0x1803bc538`
- `0x1805a2dd8`
- `0x1805a3ee4`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18012dd73`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18012dd73`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18012dd57`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18012dd57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18012da40`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18012da40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18012da67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18012da8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18012da67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18012da8c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18012d80c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18012d80c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012d821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012da5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012d821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012da5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18012da6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18012da6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012d86b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012d86b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18012dc86`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18012dc86`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18012dcd8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18012dcd8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012dda2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012dda2`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18012ddb8`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18012ddb8`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18012d8e7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18012d8e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall StartupAppMonitor::StartMonitor(StartupAppMonitor *this)
{
  int v2; // r15d
  wil::details *v3; // rcx
  HANDLE Event; // rbx
  __int64 v5; // rdx
  HKEY *v6; // rax
  __int64 v7; // rdx
  char *v8; // r13
  char *v9; // rax
  void *v10; // rax
  __int64 v11; // rdi
  __int64 v12; // r14
  __int64 v13; // rax
  _QWORD *v14; // rcx
  _QWORD *v15; // r8
  _QWORD *v16; // rbx
  __int64 *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  std::_Ref_count_base *v20; // rcx
  HKEY v21; // r14
  unsigned int v22; // edx
  DWORD LastError; // ebx
  _QWORD *i; // rbx
  __int64 *v25; // rax
  StartupNotification **v26; // rdi
  __int64 v27; // rcx
  __int64 v28; // rdx
  std::_Ref_count_base *v29; // rcx
  int v30; // r8d
  int v31; // r9d
  _QWORD *v32; // rdx
  _QWORD *v33; // rax
  _QWORD *v34; // r14
  HKEY *v35; // rax
  unsigned int Key; // eax
  unsigned int v37; // eax
  char *v38; // rax
  HKEY v39; // rdx
  __int64 v40; // rcx
  const char *v41; // r9
  int v42; // ecx
  int v43; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-168h]
  unsigned int phkResulta; // [rsp+20h] [rbp-168h]
  bool v46; // [rsp+50h] [rbp-138h]
  int v47; // [rsp+54h] [rbp-134h]
  HKEY hKey; // [rsp+60h] [rbp-128h] BYREF
  _DWORD v49[2]; // [rsp+68h] [rbp-120h] BYREF
  BYTE Data[8]; // [rsp+70h] [rbp-118h] BYREF
  char *v51; // [rsp+78h] [rbp-110h] BYREF
  HKEY v52; // [rsp+80h] [rbp-108h] BYREF
  __int64 v53; // [rsp+88h] [rbp-100h] BYREF
  std::_Ref_count_base *v54; // [rsp+90h] [rbp-F8h]
  _BYTE v55[16]; // [rsp+98h] [rbp-F0h] BYREF
  char v56; // [rsp+A8h] [rbp-E0h] BYREF
  std::_Ref_count_base *v57; // [rsp+B0h] [rbp-D8h]
  _QWORD v58[3]; // [rsp+B8h] [rbp-D0h] BYREF
  __int64 v59; // [rsp+D0h] [rbp-B8h]
  _BYTE v60[112]; // [rsp+D8h] [rbp-B0h] BYREF
  __int64 v61; // [rsp+148h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v2 = 0;
  v47 = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &StartupAppMonitor::s_showNotificationMapUpdateEvent,
      Event);
  }
  else
  {
    wil::details::GetLastErrorFailHr(v3);
  }
  v52 = 0;
  v6 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(
                 &v52,
                 v5);
  *(_DWORD *)Data = RegOpenKeyExW(
                      HKEY_CURRENT_USER,
                      L"Software\\Microsoft\\Windows\\CurrentVersion\\RunNotification",
                      0,
                      0x20019u,
                      v6);
  v46 = *(_DWORD *)Data != 2;
  v8 = (char *)this + 184;
  v9 = (char *)this + 496;
  v51 = (char *)this + 496;
  try
  {
    while ( v8 != v9 )
    {
      v10 = operator new(0x78u);
      v11 = std::_Ref_count_obj2<REGKEYINFO>::_Ref_count_obj2<REGKEYINFO>(v10, v8);
      v58[0] = v11 + 16;
      v58[1] = v11;
      if ( *((_QWORD *)this + 19) == 0x7FFFFFFFFFFFFFFLL )
        std::_Xlength_error("list too long");
      v12 = *((_QWORD *)this + 18);
      v58[2] = (char *)this + 144;
      v59 = 0;
      v13 = std::_Allocate<16,std::_Default_allocate_traits>(32);
      std::shared_ptr<InputAppViewCoodinatorHandler>::shared_ptr<InputAppViewCoodinatorHandler>(v13 + 16, v58);
      ++*((_QWORD *)this + 19);
      v14 = *(_QWORD **)(v12 + 8);
      *v15 = v12;
      v15[1] = v14;
      v59 = 0;
      *(_QWORD *)(v12 + 8) = v15;
      *v14 = v15;
      v16 = (_QWORD *)(v11 + 24);
      v17 = (__int64 *)std::make_shared<StartupRegKeyNotification,HKEY__ * &,std::wstring &,enum StartupAppLocation &,std::wstring &>(
                         (unsigned int)&v56,
                         (int)v11 + 16,
                         (int)v11 + 24,
                         (int)v11 + 56,
                         v11 + 64);
      v18 = *v17;
      v19 = v17[1];
      *v17 = 0;
      v17[1] = 0;
      *(_QWORD *)(v11 + 96) = v18;
      v20 = *(std::_Ref_count_base **)(v11 + 104);
      *(_QWORD *)(v11 + 104) = v19;
      if ( v20 )
        std::_Ref_count_base::_Decref(v20);
      if ( v57 )
        std::_Ref_count_base::_Decref(v57);
      if ( v11 )
        _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
      v53 = v11 + 16;
      v54 = (std::_Ref_count_base *)v11;
      std::shared_ptr<InputAppViewCoodinatorHandler>::shared_ptr<InputAppViewCoodinatorHandler>(v55, &v53);
      wistd::function_void___cdecl_enum_wil::RegistryChangeKind__::function_void___cdecl_enum_wil::RegistryChangeKind____lambda_f9d92d283d219251b39b1fca3d115af1__void_(
        v60,
        v55);
      if ( *(_QWORD *)(v11 + 48) > 7u )
        v16 = (_QWORD *)*v16;
      hKey = 0;
      wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(
        &hKey,
        *(_QWORD *)(v11 + 16),
        v16,
        0,
        v60);
      wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>>::operator=(
        v11 + 112,
        &hKey);
      v21 = hKey;
      if ( hKey )
      {
        AcquireSRWLockExclusive((PSRWLOCK)hKey + 19);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v21 + 37, 0xFFFFFFFF) == 1 )
        {
          if ( v21 != HKEY_PERFORMANCE_NLSTEXT|0x7FFFFF08LL )
          {
            LastError = GetLastError();
            ReleaseSRWLockExclusive((PSRWLOCK)v21 + 19);
            SetLastError(LastError);
          }
          if ( v21 )
            wil::details::registry_watcher_state::`scalar deleting destructor'(
              (wil::details::registry_watcher_state *)v21,
              v22);
        }
        else if ( v21 != HKEY_PERFORMANCE_NLSTEXT|0x7FFFFF08LL )
        {
          ReleaseSRWLockExclusive((PSRWLOCK)v21 + 19);
        }
        v2 = v47;
      }
      if ( v61 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 24LL))(v61);
      StartupNotification::CheckForChange(*(StartupNotification **)(v11 + 96), v46);
      if ( v11 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v11);
      v2 |= 3u;
      v47 = v2;
      if ( v11 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v11);
      v8 += 104;
      v9 = v51;
    }
    for ( i = (_QWORD *)((char *)this + 496); i != (_QWORD *)((char *)this + 672); i += 11 )
    {
      v25 = (__int64 *)std::make_shared<StartupFolderNotification,_GUID &,enum StartupAppLocation &,HKEY__ * &,std::wstring &>(
                         (unsigned int)&v56,
                         (_DWORD)i,
                         (int)i + 16,
                         (int)i + 24,
                         (__int64)(i + 4));
      v26 = (StartupNotification **)(i + 8);
      v27 = *v25;
      v28 = v25[1];
      *v25 = 0;
      v25[1] = 0;
      i[8] = v27;
      v29 = (std::_Ref_count_base *)i[9];
      i[9] = v28;
      if ( v29 )
        std::_Ref_count_base::_Decref(v29);
      if ( v57 )
        std::_Ref_count_base::_Decref(v57);
      std::shared_ptr<InputAppViewCoodinatorHandler>::shared_ptr<InputAppViewCoodinatorHandler>(&v53, i + 8);
      std::shared_ptr<InputAppViewCoodinatorHandler>::shared_ptr<InputAppViewCoodinatorHandler>(v55, &v53);
      wistd::function_void___cdecl_enum_wil::FolderChangeEvent_unsigned_short_const____::function_void___cdecl_enum_wil::FolderChangeEvent_unsigned_short_const______lambda_d30d699a9b0100ad99955a9d234ed237__void_(
        v60,
        v55);
      v32 = (_QWORD *)((char *)*v26 + 64);
      if ( *((_QWORD *)*v26 + 11) > 7u )
        v32 = (_QWORD *)*v32;
      v33 = (_QWORD *)wil::make_folder_change_reader((unsigned int)&v51, (_DWORD)v32, v30, v31, (unsigned int)v60);
      v34 = v33;
      if ( i + 10 != v33 )
      {
        wil::details::unique_storage<wil::details::resource_policy<wil::details::folder_change_reader_state *,void (*)(wil::details::folder_change_reader_state *),&void wil::details::delete_folder_change_reader_state(wil::details::folder_change_reader_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::folder_change_reader_state *,wil::details::folder_change_reader_state *,0,std::nullptr_t>>::reset(
          i + 10,
          *v33);
        *v34 = 0;
      }
      wil::details::unique_storage<wil::details::resource_policy<wil::details::folder_change_reader_state *,void (*)(wil::details::folder_change_reader_state *),&void wil::details::delete_folder_change_reader_state(wil::details::folder_change_reader_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::folder_change_reader_state *,wil::details::folder_change_reader_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::folder_change_reader_state *,void (*)(wil::details::folder_change_reader_state *),&void wil::details::delete_folder_change_reader_state(wil::details::folder_change_reader_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::folder_change_reader_state *,wil::details::folder_change_reader_state *,0,std::nullptr_t>>(&v51);
      wistd::function<bool (long)>::~function<bool (long)>(v60);
      StartupNotification::CheckForChange(*v26, v46);
      if ( v54 )
        std::_Ref_count_base::_Decref(v54);
    }
    if ( *(_DWORD *)Data == 2 )
    {
      hKey = 0;
      v35 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(
                      &hKey,
                      v7);
      Key = RegCreateKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Notifications\\Settings\\Windows.SystemToast.StartupApp",
              0,
              0,
              0,
              0x102u,
              0,
              v35,
              0);
      if ( Key )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0xA1,
          (unsigned int)"pcshell\\twinui\\startupappmonitor\\lib\\startupappmonitorimpl.cpp",
          (const char *)Key,
          phkResulta);
      *(_DWORD *)Data = 0;
      v37 = RegSetValueExW(hKey, L"Enabled", 0, 4u, Data, 4u);
      if ( v37 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0xA4,
          (unsigned int)"pcshell\\twinui\\startupappmonitor\\lib\\startupappmonitorimpl.cpp",
          (const char *)v37,
          (unsigned int)phkResult);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      (char *)this + 176,
      0,
      0);
    v38 = (char *)operator new(0x10u);
    *(_QWORD *)v38 = this;
    *((_QWORD *)v38 + 1) = StartupAppMonitor::StartupToastNotifier;
    v51 = v38;
    LODWORD(phkResult) = 0;
    v39 = (HKEY)_o__beginthreadex(
                  0,
                  0,
                  ____Invoke_V__tuple_P6AXPEAVStartupAppMonitor____EPEAV1__std___0A__00_thread_std__CAIPEAX_Z,
                  v38,
                  phkResult,
                  v49);
    hKey = v39;
    if ( v39 )
    {
      if ( *((_DWORD *)this + 42) )
      {
        _o_terminate(v40, v39);
        __debugbreak();
      }
      v42 = v49[0];
      v43 = v49[1];
      *((_QWORD *)this + 20) = v39;
      *((_DWORD *)this + 42) = v42;
      *((_DWORD *)this + 43) = v43;
      if ( v52 )
        RegCloseKey(v52);
    }
    else
    {
      v49[0] = 0;
      std::_Throw_Cpp_error(6);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xA9,
      (unsigned int)"pcshell\\twinui\\startupappmonitor\\lib\\startupappmonitorimpl.cpp",
      v41);
  }
}

```

## disassembly

```asm
0x18012d7c8  mov     [rsp+arg_8], rbx
0x18012d7cd  mov     [rsp+arg_10], rsi
0x18012d7d2  push    rdi
0x18012d7d3  push    r12
0x18012d7d5  push    r13
0x18012d7d7  push    r14
0x18012d7d9  push    r15
0x18012d7db  sub     rsp, 160h
0x18012d7e2  mov     rax, cs:__security_cookie
0x18012d7e9  xor     rax, rsp
0x18012d7ec  mov     [rsp+188h+var_38], rax
0x18012d7f4  mov     rsi, rcx
0x18012d7f7  xor     r15d, r15d
0x18012d7fa  mov     [rsp+188h+var_134], r15d
0x18012d7ff  mov     r9d, 1F0003h; dwDesiredAccess
0x18012d805  xor     r8d, r8d; dwFlags
0x18012d808  xor     edx, edx; lpName
0x18012d80a  xor     ecx, ecx; lpEventAttributes
0x18012d80c  call    cs:__imp_CreateEventExW
0x18012d812  mov     rbx, rax
0x18012d815  test    rax, rax
0x18012d818  jnz     short loc_18012D821
0x18012d81a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18012d81f  jmp     short loc_18012D836
0x18012d821  call    cs:__imp_GetLastError
0x18012d827  mov     rdx, rbx
0x18012d82a  lea     rcx, ?s_showNotificationMapUpdateEvent@StartupAppMonitor@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@A
0x18012d831  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18012d836  mov     [rsp+188h+var_108], 0
0x18012d842  lea     rcx, [rsp+188h+var_108]
0x18012d84a  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18012d84f  mov     [rsp+188h+phkResult], rax; phkResult
0x18012d854  mov     r9d, 20019h; samDesired
0x18012d85a  xor     r8d, r8d; ulOptions
0x18012d85d  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18012d864  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18012d86b  call    cs:__imp_RegOpenKeyExW
0x18012d871  mov     dword ptr [rsp+188h+Data], eax
0x18012d875  cmp     eax, 2
0x18012d878  setnz   r12b
0x18012d87c  mov     [rsp+188h+var_138], r12b
0x18012d881  lea     r13, [rsi+0B8h]
0x18012d888  lea     rax, [r13+138h]
0x18012d88f  mov     [rsp+188h+var_110], rax
0x18012d894  cmp     r13, rax
0x18012d897  jz      loc_18012DAF1
0x18012d89d  mov     ecx, 78h ; 'x'; Size
0x18012d8a2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012d8a7  mov     rdx, r13
0x18012d8aa  mov     rcx, rax
0x18012d8ad  call    ??$?0AEAUREGKEYINFO@@@?$_Ref_count_obj2@UREGKEYINFO@@@std@@QEAA@AEAUREGKEYINFO@@@Z; std::_Ref_count_obj2<REGKEYINFO>::_Ref_count_obj2<REGKEYINFO>(REGKEYINFO &)
0x18012d8b2  mov     rdi, rax
0x18012d8b5  lea     r12, [rax+10h]
0x18012d8b9  mov     [rsp+188h+var_D0], r12
0x18012d8c1  mov     [rsp+188h+var_C8], rax
0x18012d8c9  lea     rbx, [rsi+90h]
0x18012d8d0  mov     rax, 7FFFFFFFFFFFFFFh
0x18012d8da  cmp     [rbx+8], rax
0x18012d8de  jnz     short loc_18012D8ED
0x18012d8e0  lea     rcx, aListTooLong; "list too long"
0x18012d8e7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18012d8ed  mov     r14, [rbx]
0x18012d8f0  mov     [rsp+188h+var_C0], rbx
0x18012d8f8  mov     [rsp+188h+var_B8], 0
0x18012d904  mov     ecx, 20h ; ' '
0x18012d909  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18012d90e  mov     r8, rax
0x18012d911  lea     rcx, [rax+10h]
0x18012d915  lea     rdx, [rsp+188h+var_D0]
0x18012d91d  call    ??0?$shared_ptr@VInputAppViewCoodinatorHandler@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<InputAppViewCoodinatorHandler>::shared_ptr<InputAppViewCoodinatorHandler>(std::shared_ptr<InputAppViewCoodinatorHandler> const &)
0x18012d922  nop
0x18012d923  inc     qword ptr [rbx+8]
0x18012d927  mov     rcx, [r14+8]
0x18012d92b  mov     [r8], r14
0x18012d92e  mov     [r8+8], rcx
0x18012d932  mov     [rsp+188h+var_B8], 0
0x18012d93e  mov     [r14+8], r8
0x18012d942  mov     [rcx], r8
0x18012d945  lea     rbx, [r12+8]
0x18012d94a  lea     rax, [r12+30h]
0x18012d94f  lea     r9, [r12+28h]
0x18012d954  mov     [rsp+188h+phkResult], rax
0x18012d959  mov     r8, rbx
0x18012d95c  mov     rdx, r12
0x18012d95f  lea     rcx, [rsp+188h+var_E0]
0x18012d967  call    ??$make_shared@VStartupRegKeyNotification@@AEAPEAUHKEY__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAW4StartupAppLocation@@AEAV34@@std@@YA?AV?$shared_ptr@VStartupRegKeyNotification@@@0@AEAPEAUHKEY__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEAW4StartupAppLocation@@1@Z; std::make_shared<StartupRegKeyNotification,HKEY__ * &,std::wstring &,StartupAppLocation &,std::wstring &>(HKEY__ * &,std::wstring &,StartupAppLocation &,std::wstring &)
0x18012d96c  mov     rcx, [rax]
0x18012d96f  mov     rdx, [rax+8]
0x18012d973  xor     r14d, r14d
0x18012d976  mov     [rax], r14
0x18012d979  mov     [rax+8], r14
0x18012d97d  mov     [r12+50h], rcx
0x18012d982  mov     rcx, [r12+58h]; this
0x18012d987  mov     [r12+58h], rdx
0x18012d98c  test    rcx, rcx
0x18012d98f  jz      short loc_18012D996
0x18012d991  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18012d996  mov     rcx, [rsp+188h+var_D8]; this
0x18012d99e  test    rcx, rcx
0x18012d9a1  jz      short loc_18012D9A8
0x18012d9a3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18012d9a8  test    rdi, rdi
0x18012d9ab  jz      short loc_18012D9B1
0x18012d9ad  lock inc dword ptr [rdi+8]
0x18012d9b1  mov     [rsp+188h+var_100], r12
0x18012d9b9  mov     [rsp+188h+var_F8], rdi
0x18012d9c1  lea     rdx, [rsp+188h+var_100]
0x18012d9c9  lea     rcx, [rsp+188h+var_F0]
0x18012d9d1  call    ??0?$shared_ptr@VInputAppViewCoodinatorHandler@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<InputAppViewCoodinatorHandler>::shared_ptr<InputAppViewCoodinatorHandler>(std::shared_ptr<InputAppViewCoodinatorHandler> const &)
0x18012d9d6  lea     rdx, [rsp+188h+var_F0]
0x18012d9de  lea     rcx, [rsp+188h+var_B0]
0x18012d9e6  call    wistd__function_void___cdecl_enum_wil__RegistryChangeKind____function_void___cdecl_enum_wil__RegistryChangeKind____lambda_f9d92d283d219251b39b1fca3d115af1__void_
0x18012d9eb  nop
0x18012d9ec  cmp     qword ptr [rbx+18h], 7
0x18012d9f1  jbe     short loc_18012D9F6
0x18012d9f3  mov     rbx, [rbx]
0x18012d9f6  mov     [rsp+188h+hKey], r14
0x18012d9fb  lea     rax, [rsp+188h+var_B0]
0x18012da03  mov     [rsp+188h+phkResult], rax
0x18012da08  xor     r9d, r9d
0x18012da0b  mov     r8, rbx
0x18012da0e  mov     rdx, [r12]
0x18012da12  lea     rcx, [rsp+188h+hKey]
0x18012da17  call    ?create@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXPEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18012da1c  nop
0x18012da1d  lea     rcx, [r12+60h]
0x18012da22  lea     rdx, [rsp+188h+hKey]
0x18012da27  call    ??4?$unique_any_t@V?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>>::operator=(wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>> &&)
0x18012da2c  mov     r14, [rsp+188h+hKey]
0x18012da31  test    r14, r14
0x18012da34  jz      short loc_18012DA97
0x18012da36  lea     r15, [r14+98h]
0x18012da3d  mov     rcx, r15; SRWLock
0x18012da40  call    cs:__imp_AcquireSRWLockExclusive
0x18012da46  or      eax, 0FFFFFFFFh
0x18012da49  lock xadd [r14+94h], eax
0x18012da52  cmp     eax, 1
0x18012da55  jnz     short loc_18012DA84
0x18012da57  test    r15, r15
0x18012da5a  jz      short loc_18012DA75
0x18012da5c  call    cs:__imp_GetLastError
0x18012da62  mov     ebx, eax
0x18012da64  mov     rcx, r15; SRWLock
0x18012da67  call    cs:__imp_ReleaseSRWLockExclusive
0x18012da6d  mov     ecx, ebx; dwErrCode
0x18012da6f  call    cs:__imp_SetLastError
0x18012da75  test    r14, r14
0x18012da78  jz      short loc_18012DA92
0x18012da7a  mov     rcx, r14; this
0x18012da7d  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18012da82  jmp     short loc_18012DA92
0x18012da84  test    r15, r15
0x18012da87  jz      short loc_18012DA92
0x18012da89  mov     rcx, r15; SRWLock
0x18012da8c  call    cs:__imp_ReleaseSRWLockExclusive
0x18012da92  mov     r15d, [rsp+188h+var_134]
0x18012da97  mov     rcx, [rsp+188h+var_40]
0x18012da9f  test    rcx, rcx
0x18012daa2  jz      short loc_18012DAB0
0x18012daa4  mov     rax, [rcx]
0x18012daa7  mov     rax, [rax+18h]
0x18012daab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012dab0  mov     dl, [rsp+188h+var_138]; bool
0x18012dab4  mov     rcx, [r12+50h]; this
0x18012dab9  call    ?CheckForChange@StartupNotification@@QEAAX_N@Z; StartupNotification::CheckForChange(bool)
0x18012dabe  nop
0x18012dabf  test    rdi, rdi
0x18012dac2  jz      short loc_18012DACD
0x18012dac4  mov     rcx, rdi; this
0x18012dac7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18012dacc  nop
0x18012dacd  or      r15d, 3
0x18012dad1  mov     [rsp+188h+var_134], r15d
0x18012dad6  test    rdi, rdi
0x18012dad9  jz      short loc_18012DAE3
0x18012dadb  mov     rcx, rdi; this
0x18012dade  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18012dae3  add     r13, 68h ; 'h'
0x18012dae7  mov     rax, [rsp+188h+var_110]
0x18012daec  jmp     loc_18012D894
0x18012daf1  lea     rbx, [rsi+1F0h]
0x18012daf8  lea     r15, [rbx+0B0h]
0x18012daff  mov     r12b, [rsp+188h+var_138]
0x18012db04  cmp     rbx, r15
0x18012db07  jz      loc_18012DC2D
0x18012db0d  lea     rax, [rbx+20h]
0x18012db11  lea     r9, [rbx+18h]
0x18012db15  lea     r8, [rbx+10h]
0x18012db19  mov     [rsp+188h+phkResult], rax
0x18012db1e  mov     rdx, rbx
0x18012db21  lea     rcx, [rsp+188h+var_E0]
0x18012db29  call    ??$make_shared@VStartupFolderNotification@@AEAU_GUID@@AEAW4StartupAppLocation@@AEAPEAUHKEY__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@YA?AV?$shared_ptr@VStartupFolderNotification@@@0@AEAU_GUID@@AEAW4StartupAppLocation@@AEAPEAUHKEY__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::make_shared<StartupFolderNotification,_GUID &,StartupAppLocation &,HKEY__ * &,std::wstring &>(_GUID &,StartupAppLocation &,HKEY__ * &,std::wstring &)
0x18012db2e  lea     rdi, [rbx+40h]
0x18012db32  mov     rcx, [rax]
0x18012db35  mov     rdx, [rax+8]
0x18012db39  mov     qword ptr [rax], 0
0x18012db40  mov     qword ptr [rax+8], 0
0x18012db48  mov     [rdi], rcx
0x18012db4b  mov     rcx, [rdi+8]; this
0x18012db4f  mov     [rdi+8], rdx
0x18012db53  test    rcx, rcx
0x18012db56  jz      short loc_18012DB5D
0x18012db58  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18012db5d  mov     rcx, [rsp+188h+var_D8]; this
0x18012db65  test    rcx, rcx
0x18012db68  jz      short loc_18012DB6F
0x18012db6a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18012db6f  mov     rdx, rdi
0x18012db72  lea     rcx, [rsp+188h+var_100]
0x18012db7a  call    ??0?$shared_ptr@VInputAppViewCoodinatorHandler@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<InputAppViewCoodinatorHandler>::shared_ptr<InputAppViewCoodinatorHandler>(std::shared_ptr<InputAppViewCoodinatorHandler> const &)
0x18012db7f  nop
0x18012db80  lea     rdx, [rsp+188h+var_100]
0x18012db88  lea     rcx, [rsp+188h+var_F0]
0x18012db90  call    ??0?$shared_ptr@VInputAppViewCoodinatorHandler@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<InputAppViewCoodinatorHandler>::shared_ptr<InputAppViewCoodinatorHandler>(std::shared_ptr<InputAppViewCoodinatorHandler> const &)
0x18012db95  lea     rdx, [rsp+188h+var_F0]
0x18012db9d  lea     rcx, [rsp+188h+var_B0]
0x18012dba5  call    wistd__function_void___cdecl_enum_wil__FolderChangeEvent_unsigned_short_const______function_void___cdecl_enum_wil__FolderChangeEvent_unsigned_short_const______lambda_d30d699a9b0100ad99955a9d234ed237__void_
0x18012dbaa  nop
0x18012dbab  mov     rdx, [rdi]
0x18012dbae  add     rdx, 40h ; '@'
0x18012dbb2  cmp     qword ptr [rdx+18h], 7
0x18012dbb7  jbe     short loc_18012DBBC
0x18012dbb9  mov     rdx, [rdx]
0x18012dbbc  lea     rax, [rsp+188h+var_B0]
0x18012dbc4  mov     [rsp+188h+phkResult], rax
0x18012dbc9  lea     rcx, [rsp+188h+var_110]
0x18012dbce  call    ?make_folder_change_reader@wil@@YA?AV?$unique_any_t@V?$folder_change_reader_t@V?$unique_storage@U?$resource_policy@PEAUfolder_change_reader_state@details@wil@@P6AXPEAU123@@Z$1?delete_folder_change_reader_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@1@PEBG_NW4FolderChangeEvents@1@$$QEAV?$function@$$A6AXW4FolderChangeEvent@wil@@PEBG@Z@wistd@@@Z; wil::make_folder_change_reader(ushort const *,bool,wil::FolderChangeEvents,wistd::function<void (wil::FolderChangeEvent,ushort const *)> &&)
0x18012dbd3  mov     r14, rax
0x18012dbd6  lea     rcx, [rbx+50h]
0x18012dbda  cmp     rcx, rax
0x18012dbdd  jz      short loc_18012DBEE
0x18012dbdf  mov     rdx, [rax]
0x18012dbe2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUfolder_change_reader_state@details@wil@@P6AXPEAU123@@Z$1?delete_folder_change_reader_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUfolder_change_reader_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::folder_change_reader_state *,void (*)(wil::details::folder_change_reader_state *),&wil::details::delete_folder_change_reader_state(wil::details::folder_change_reader_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::folder_change_reader_state *,wil::details::folder_change_reader_state *,0,std::nullptr_t>>::reset(wil::details::folder_change_reader_state *)
0x18012dbe7  mov     qword ptr [r14], 0
0x18012dbee  lea     rcx, [rsp+188h+var_110]
0x18012dbf3  call    ??1?$unique_storage@U?$resource_policy@PEAUfolder_change_reader_state@details@wil@@P6AXPEAU123@@Z$1?delete_folder_change_reader_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::folder_change_reader_state *,void (*)(wil::details::folder_change_reader_state *),&wil::details::delete_folder_change_reader_state(wil::details::folder_change_reader_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::folder_change_reader_state *,wil::details::folder_change_reader_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::folder_change_reader_state *,void (*)(wil::details::folder_change_reader_state *),&wil::details::delete_folder_change_reader_state(wil::details::folder_change_reader_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::folder_change_reader_state *,wil::details::folder_change_reader_state *,0,std::nullptr_t>>(void)
0x18012dbf8  nop
0x18012dbf9  lea     rcx, [rsp+188h+var_B0]
0x18012dc01  call    ??1?$function@$$A6A_NJ@Z@wistd@@QEAA@XZ; wistd::function<bool (long)>::~function<bool (long)>(void)
0x18012dc06  mov     dl, r12b; bool
0x18012dc09  mov     rcx, [rdi]; this
0x18012dc0c  call    ?CheckForChange@StartupNotification@@QEAAX_N@Z; StartupNotification::CheckForChange(bool)
0x18012dc11  nop
0x18012dc12  mov     rcx, [rsp+188h+var_F8]; this
0x18012dc1a  test    rcx, rcx
0x18012dc1d  jz      short loc_18012DC24
0x18012dc1f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18012dc24  add     rbx, 58h ; 'X'
0x18012dc28  jmp     loc_18012DB04
0x18012dc2d  cmp     dword ptr [rsp+188h+Data], 2
0x18012dc32  jnz     loc_18012DD09
0x18012dc38  mov     [rsp+188h+hKey], 0
0x18012dc41  lea     rcx, [rsp+188h+hKey]
0x18012dc46  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18012dc4b  mov     [rsp+188h+lpdwDisposition], 0; lpdwDisposition
0x18012dc54  mov     [rsp+188h+var_150], rax; phkResult
0x18012dc59  mov     [rsp+188h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18012dc62  mov     [rsp+188h+samDesired], 102h; samDesired
0x18012dc6a  mov     dword ptr [rsp+188h+phkResult], 0; unsigned int
0x18012dc72  xor     r9d, r9d; lpClass
0x18012dc75  xor     r8d, r8d; Reserved
0x18012dc78  lea     rdx, aSoftwareMicros_89; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18012dc7f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18012dc86  call    cs:__imp_RegCreateKeyExW
0x18012dc8c  mov     rcx, [rsp+188h]; this
0x18012dc94  test    eax, eax
0x18012dc96  jz      short loc_18012DCAC
0x18012dc98  mov     r9d, eax; char *
0x18012dc9b  lea     r8, aPcshellTwinuiS_18; "pcshell\\twinui\\startupappmonitor\\lib"...
0x18012dca2  mov     edx, 0A1h; void *
0x18012dca7  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18012dcac  mov     dword ptr [rsp+188h+Data], 0
0x18012dcb4  mov     r9d, 4; dwType
0x18012dcba  mov     [rsp+188h+samDesired], r9d; cbData
0x18012dcbf  lea     rax, [rsp+188h+Data]
0x18012dcc4  mov     [rsp+188h+phkResult], rax; unsigned int
0x18012dcc9  xor     r8d, r8d; Reserved
0x18012dccc  lea     rdx, aEnabled; "Enabled"
0x18012dcd3  mov     rcx, [rsp+188h+hKey]; hKey
0x18012dcd8  call    cs:__imp_RegSetValueExW
0x18012dcde  mov     rcx, [rsp+188h]; this
0x18012dce6  test    eax, eax
0x18012dce8  jz      short loc_18012DCFF
0x18012dcea  mov     r9d, eax; char *
0x18012dced  lea     r8, aPcshellTwinuiS_18; "pcshell\\twinui\\startupappmonitor\\lib"...
0x18012dcf4  mov     edx, 0A4h; void *
0x18012dcf9  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18012dcff  lea     rcx, [rsp+188h+hKey]
0x18012dd04  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012dd09  lea     rcx, [rsi+0B0h]
0x18012dd10  xor     r8d, r8d
0x18012dd13  xor     edx, edx
0x18012dd15  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18012dd1a  mov     ecx, 10h; Size
0x18012dd1f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012dd24  mov     [rax], rsi
0x18012dd27  lea     rcx, ?StartupToastNotifier@StartupAppMonitor@@CAXPEAV1@@Z; StartupAppMonitor::StartupToastNotifier(StartupAppMonitor *)
0x18012dd2e  mov     [rax+8], rcx
0x18012dd32  mov     [rsp+188h+var_110], rax
0x18012dd37  lea     rcx, [rsp+188h+var_120]
  ... truncated ...
```
