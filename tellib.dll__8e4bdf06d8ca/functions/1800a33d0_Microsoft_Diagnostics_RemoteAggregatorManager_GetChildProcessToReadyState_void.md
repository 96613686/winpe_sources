# Microsoft::Diagnostics::RemoteAggregatorManager::GetChildProcessToReadyState(void)

- ea: `0x1800a33d0`
- end: `0x1800a3981`
- name: `?GetChildProcessToReadyState@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAXXZ`
- size: `1457`
- prototype: `void __fastcall(Microsoft::Diagnostics::RemoteAggregatorManager *__hidden this)`
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801c6b70`

## callees

- `0x18001c5b0`
- `0x18001cf30`
- `0x1800333b0`
- `0x180034d94`
- `0x18003fd8c`
- `0x180053218`
- `0x180054ca4`
- `0x18005b974`
- `0x180065dec`
- `0x180089d90`
- `0x180098d5c`
- `0x18009c71c`
- `0x18009e49c`
- `0x1800a0d08`
- `0x1800a33d0`
- `0x1800a60e4`
- `0x1800a8e5c`
- `0x1800a9344`
- `0x1800c2404`
- `0x1800ff66c`
- `0x180105ae4`
- `0x180105c78`
- `0x18012de40`
- `0x18012eb08`
- `0x180161298`
- `0x180168b40`
- `0x180177b0c`
- `0x1801c247c`
- `0x1801c4148`
- `0x1801c4b9c`
- `0x1801c4d48`
- `0x1801c61bc`
- `0x1801c64b0`
- `0x180212f3c`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800a3413`
- `msvcp_win!_Mtx_unlock` at `0x1800a3424`
- `msvcp_win!_Mtx_unlock` at `0x1800a35ca`
- `msvcp_win!_Mtx_unlock` at `0x1800a36a8`
- `msvcp_win!_Mtx_unlock` at `0x1800a3413`
- `msvcp_win!_Mtx_unlock` at `0x1800a3424`
- `msvcp_win!_Mtx_unlock` at `0x1800a35ca`
- `msvcp_win!_Mtx_unlock` at `0x1800a36a8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800a358c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800a359f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800a358c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800a359f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800a3928`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800a3928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a38bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a38bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800a3699`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800a3699`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800a3722`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800a3722`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a3512`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a3512`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800a3653`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800a3653`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a3797`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a3797`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a366b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a366b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800a37e7`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800a37e7`

## string_xrefs

- `0x1800a370d`: `onecore\base\telemetry\utc\service\engine\remoteaggregatormanager.cpp`
- `0x1800a380f`: `onecore\base\telemetry\utc\service\engine\remoteaggregatormanager.cpp`
- `0x1800a386a`: `onecore\base\telemetry\utc\service\engine\remoteaggregatormanager.cpp`
- `0x1800a387f`: `RemoteAggregatorManager_CreateProcessFailed_0`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Microsoft::Diagnostics::RemoteAggregatorManager::GetChildProcessToReadyState(
        Microsoft::Diagnostics::RemoteAggregatorManager *this)
{
  struct _Mtx_internal_imp_t *v2; // rbx
  _QWORD *v3; // rbx
  struct Microsoft::Diagnostics::ScenarioManager *ScenarioManager; // rax
  HANDLE CurrentProcess; // rax
  Microsoft::Diagnostics::RemoteAggregatorManager *v6; // rcx
  void *v7; // rdi
  Microsoft::Diagnostics::RemoteAggregatorManager *v8; // rcx
  void *v9; // rbx
  Microsoft::Diagnostics::RemoteAggregatorManager *v10; // rcx
  HANDLE *v11; // rdi
  void *v12; // rcx
  __int64 v13; // rdx
  const char *v14; // r9
  struct _TP_WAIT *v15; // rcx
  int Key; // eax
  DWORD ProcessId; // eax
  DWORD v18; // r9d
  DWORD v19; // eax
  const char *v20; // r9
  DWORD v21; // eax
  DWORD v22; // eax
  BOOL bInheritHandles; // [rsp+20h] [rbp-E0h]
  __int128 v24; // [rsp+50h] [rbp-B0h] BYREF
  void *v25; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v26[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v27[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v28[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v30[5]; // [rsp+B8h] [rbp-48h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v32[1128]; // [rsp+150h] [rbp+50h] BYREF
  char v33; // [rsp+5B8h] [rbp+4B8h] BYREF
  HANDLE Handles[3]; // [rsp+5F0h] [rbp+4F0h] BYREF
  WCHAR CommandLine[20]; // [rsp+608h] [rbp+508h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+668h] [rbp+568h]

  v2 = (Microsoft::Diagnostics::RemoteAggregatorManager *)((char *)this + 1832);
  std::_Mutex_base::lock((Microsoft::Diagnostics::RemoteAggregatorManager *)((char *)this + 1832));
  if ( *((_BYTE *)this + 1912) )
  {
    _Mtx_unlock(v2);
    return;
  }
  _Mtx_unlock(v2);
  if ( *((_DWORD *)this + 424) )
  {
    std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v28, (char *)this + 2104);
    v3 = (_QWORD *)*((_QWORD *)this + 281);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,Microsoft::Diagnostics::RemoteAggregatorManager::ControlGroup>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::string const,Microsoft::Diagnostics::RemoteAggregatorManager::ControlGroup>,void *>>>(
      (char *)this + 2248,
      (char *)this + 2248,
      v3[1]);
    v3[1] = v3;
    *v3 = v3;
    v3[2] = v3;
    *((_QWORD *)this + 282) = 0;
    Microsoft::Diagnostics::RemoteAggregatorManager::DeserializeControlGroupsFromRegistry(this);
    Microsoft::Diagnostics::RemoteAggregatorManager::RefreshAndCopyActiveForwarders(this, v27);
    std::unique_lock<std::recursive_mutex>::unlock(v28);
    ScenarioManager = Microsoft::Diagnostics::LifetimeManager::GetScenarioManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    Microsoft::Diagnostics::ScenarioManager::NotifyNewRemoteForwarders(ScenarioManager, v27);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<Microsoft::Diagnostics::IForwarder>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<Microsoft::Diagnostics::IForwarder>>,void *>>>(
      v27,
      v27);
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v28);
  }
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  wcscpy(CommandLine, L"AggregatorHostexe");
  CurrentProcess = GetCurrentProcess();
  v7 = Microsoft::Diagnostics::RemoteAggregatorManager::DuplicateInheritable(v6, CurrentProcess, 0x100000u);
  v27[0] = v7;
  v9 = Microsoft::Diagnostics::RemoteAggregatorManager::DuplicateInheritable(v8, *((void **)this + 143), 0);
  v28[0] = v9;
  v25 = Microsoft::Diagnostics::RemoteAggregatorManager::DuplicateInheritable(v10, *((void **)this + 144), 0);
  v30[0] = 0;
  v30[1] = v7;
  v30[2] = v9;
  v30[3] = v25;
  v30[4] = *((_QWORD *)Microsoft::Diagnostics::LifetimeManager::GetAsimovEventSerializer((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager)
           + 1);
  ResetEvent(*((HANDLE *)this + 143));
  ResetEvent(*((HANDLE *)this + 144));
  _InterlockedIncrement((volatile signed __int32 *)this + 424);
  std::_Mutex_base::lock((Microsoft::Diagnostics::RemoteAggregatorManager *)((char *)this + 1968));
  ++*((_DWORD *)this + 522);
  _Mtx_unlock((Microsoft::Diagnostics::RemoteAggregatorManager *)((char *)this + 1968));
  v11 = (HANDLE *)((char *)this + 1160);
  v12 = (void *)*((_QWORD *)this + 145);
  if ( !v12 || Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(v12, 0) )
  {
    StartupInfo.lpReserved2 = (LPBYTE)v30;
    StartupInfo.cbReserved2 = 40;
    if ( !CreateProcessW(0, CommandLine, 0, 0, 1, 0x408u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x14C,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\remoteaggregatormanager.cpp",
        v14);
      v26[0] = L"RemoteAggregatorManager_CreateProcessFailed_0";
      v26[1] = 45;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
        (unsigned int)v32,
        (unsigned int)v26,
        0x1000000,
        0,
        0,
        0,
        0);
      LODWORD(v26[0]) = GetLastError();
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>((unsigned int)v32, (unsigned int)&v33);
      v24 = 0;
      Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(v26, &v24);
      Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v32);
      SetEvent(*((HANDLE *)this + 144));
      Microsoft::Diagnostics::RemoteAggregatorManager::ArmStartTimer(this);
      Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v32);
      goto LABEL_28;
    }
    CloseHandle(ProcessInformation.hThread);
    std::_Mutex_base::lock((Microsoft::Diagnostics::RemoteAggregatorManager *)((char *)this + 1168));
    v15 = (struct _TP_WAIT *)*((_QWORD *)this + 156);
    if ( v15 )
      SetThreadpoolWait(v15, ProcessInformation.hProcess, 0);
    _Mtx_unlock((Microsoft::Diagnostics::RemoteAggregatorManager *)((char *)this + 1168));
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 1160,
      ProcessInformation.hProcess);
    v26[0] = 0;
    v24 = *(_OWORD *)&off_180348978;
    Key = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
    if ( Key < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x15C,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\remoteaggregatormanager.cpp",
        (const char *)(unsigned int)Key,
        bInheritHandles);
    ProcessId = GetProcessId(*v11);
    v24 = *(_OWORD *)&off_18035FE08;
    Microsoft::Diagnostics::Utils::Registry::SetDword(v26[0], &v24, ProcessId);
    v24 = *(_OWORD *)&off_18035FE18;
    Microsoft::Diagnostics::Utils::Registry::SetDword(v26[0], &v24, MEMORY[0x7FFE02C4]);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v26);
    v24 = *(_OWORD *)&off_18035FDF8;
    if ( (unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(&v24) || IsDebuggerPresent() )
      v18 = -1;
    else
      v18 = 300000;
    Handles[0] = *((HANDLE *)this + 143);
    Handles[1] = *((HANDLE *)this + 144);
    Handles[2] = *v11;
    v19 = WaitForMultipleObjects(3u, Handles, 0, v18);
    if ( !v19 )
    {
      Microsoft::Diagnostics::RemoteAggregatorManager::UpdateChildProcessReady(this, 1);
      if ( *((_QWORD *)this + 240) != *((_QWORD *)this + 241) )
        Microsoft::Diagnostics::RemoteAggregatorManager::ArmFlushTimer(this);
      goto LABEL_28;
    }
    v21 = v19 - 1;
    if ( !v21 || (v22 = v21 - 1) == 0 )
    {
      Microsoft::Diagnostics::RemoteAggregatorManager::ArmStartTimer(this);
      goto LABEL_28;
    }
    if ( v22 != 256 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x180,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\remoteaggregatormanager.cpp",
        v20);
    v13 = 2;
  }
  else
  {
    v13 = 0;
  }
  Microsoft::Diagnostics::RemoteAggregatorManager::RestartChildProcess(this, v13);
LABEL_28:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v25);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v28);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v27);
}

```

## disassembly

```asm
0x1800a33d0  push    rbp
0x1800a33d2  push    rbx
0x1800a33d3  push    rsi
0x1800a33d4  push    rdi
0x1800a33d5  lea     rbp, [rsp-548h]
0x1800a33dd  sub     rsp, 648h
0x1800a33e4  mov     rax, cs:__security_cookie
0x1800a33eb  xor     rax, rsp
0x1800a33ee  mov     [rbp+560h+var_30], rax
0x1800a33f5  mov     rsi, rcx
0x1800a33f8  lea     rbx, [rcx+728h]
0x1800a33ff  mov     rcx, rbx; this
0x1800a3402  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800a3407  mov     rcx, rbx; _Mtx_t
0x1800a340a  cmp     byte ptr [rsi+778h], 0
0x1800a3411  jz      short loc_1800A3424
0x1800a3413  call    cs:__imp__Mtx_unlock
0x1800a341a  nop     dword ptr [rax+rax+00h]
0x1800a341f  jmp     loc_1800A3965
0x1800a3424  call    cs:__imp__Mtx_unlock
0x1800a342b  nop     dword ptr [rax+rax+00h]
0x1800a3430  mov     eax, [rsi+6A0h]
0x1800a3436  nop
0x1800a3437  test    eax, eax
0x1800a3439  jz      loc_1800A34CA
0x1800a343f  lea     rdx, [rsi+838h]
0x1800a3446  lea     rcx, [rbp+560h+var_5D0]
0x1800a344a  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x1800a344f  nop
0x1800a3450  lea     rdi, [rsi+8C8h]
0x1800a3457  mov     rbx, [rdi]
0x1800a345a  mov     r8, [rbx+8]
0x1800a345e  mov     rdx, rdi
0x1800a3461  mov     rcx, rdi
0x1800a3464  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UControlGroup@RemoteAggregatorManager@Diagnostics@Microsoft@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UControlGroup@RemoteAggregatorManager@Diagnostics@Microsoft@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UControlGroup@RemoteAggregatorManager@Diagnostics@Microsoft@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UControlGroup@RemoteAggregatorManager@Diagnostics@Microsoft@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,Microsoft::Diagnostics::RemoteAggregatorManager::ControlGroup>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::string const,Microsoft::Diagnostics::RemoteAggregatorManager::ControlGroup>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,Microsoft::Diagnostics::RemoteAggregatorManager::ControlGroup>,void *>> &,std::_Tree_node<std::pair<std::string const,Microsoft::Diagnostics::RemoteAggregatorManager::ControlGroup>,void *> *)
0x1800a3469  mov     [rbx+8], rbx
0x1800a346d  mov     [rbx], rbx
0x1800a3470  mov     [rbx+10h], rbx
0x1800a3474  mov     qword ptr [rdi+8], 0
0x1800a347c  mov     rcx, rsi; this
0x1800a347f  call    ?DeserializeControlGroupsFromRegistry@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::RemoteAggregatorManager::DeserializeControlGroupsFromRegistry(void)
0x1800a3484  lea     rdx, [rbp+560h+var_5E0]
0x1800a3488  mov     rcx, rsi
0x1800a348b  call    ?RefreshAndCopyActiveForwarders@RemoteAggregatorManager@Diagnostics@Microsoft@@QEAA?AVForwarderMap@23@XZ; Microsoft::Diagnostics::RemoteAggregatorManager::RefreshAndCopyActiveForwarders(void)
0x1800a3490  nop
0x1800a3491  lea     rcx, [rbp+560h+var_5D0]
0x1800a3495  call    ?unlock@?$unique_lock@Vrecursive_mutex@std@@@std@@QEAAXXZ; std::unique_lock<std::recursive_mutex>::unlock(void)
0x1800a349a  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1800a34a1  call    ?GetScenarioManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVScenarioManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetScenarioManager(void)
0x1800a34a6  lea     rdx, [rbp+560h+var_5E0]
0x1800a34aa  mov     rcx, rax
0x1800a34ad  call    ?NotifyNewRemoteForwarders@ScenarioManager@Diagnostics@Microsoft@@QEAAX$$QEAVForwarderMap@23@@Z; Microsoft::Diagnostics::ScenarioManager::NotifyNewRemoteForwarders(Microsoft::Diagnostics::ForwarderMap &&)
0x1800a34b2  nop
0x1800a34b3  lea     rdx, [rbp+560h+var_5E0]
0x1800a34b7  lea     rcx, [rbp+560h+var_5E0]
0x1800a34bb  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VIForwarder@Diagnostics@Microsoft@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VIForwarder@Diagnostics@Microsoft@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VIForwarder@Diagnostics@Microsoft@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<Microsoft::Diagnostics::IForwarder>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<Microsoft::Diagnostics::IForwarder>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<Microsoft::Diagnostics::IForwarder>>,void *>> &)
0x1800a34c0  nop
0x1800a34c1  lea     rcx, [rbp+560h+var_5D0]
0x1800a34c5  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1800a34ca  xor     edx, edx; Val
0x1800a34cc  lea     r8d, [rdx+68h]; Size
0x1800a34d0  lea     rcx, [rbp+560h+StartupInfo]; void *
0x1800a34d4  call    memset_0
0x1800a34d9  xorps   xmm0, xmm0
0x1800a34dc  xor     eax, eax
0x1800a34de  movups  xmmword ptr [rbp+560h+ProcessInformation.hProcess], xmm0
0x1800a34e2  mov     qword ptr [rbp+560h+ProcessInformation.dwProcessId], rax
0x1800a34e6  movups  xmm1, xmmword ptr cs:aAggregatorhost; "AggregatorHost.exe"
0x1800a34ed  movups  xmmword ptr [rbp+560h+CommandLine], xmm1
0x1800a34f4  movups  xmm0, xmmword ptr cs:aAggregatorhost+10h; "orHost.exe"
0x1800a34fb  movups  [rbp+560h+var_48], xmm0
0x1800a3502  movsd   xmm1, qword ptr cs:aAggregatorhost+1Eh; "exe"
0x1800a350a  movsd   qword ptr [rbp+560h+var_48+0Eh], xmm1
0x1800a3512  call    cs:__imp_GetCurrentProcess
0x1800a3519  nop     dword ptr [rax+rax+00h]
0x1800a351e  mov     rdx, rax; void *
0x1800a3521  mov     r8d, 100000h; unsigned int
0x1800a3527  call    ?DuplicateInheritable@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAPEAXPEAXK@Z; Microsoft::Diagnostics::RemoteAggregatorManager::DuplicateInheritable(void *,ulong)
0x1800a352c  mov     rdi, rax
0x1800a352f  mov     [rbp+560h+var_5E0], rax
0x1800a3533  xor     r8d, r8d; unsigned int
0x1800a3536  mov     rdx, [rsi+478h]; void *
0x1800a353d  call    ?DuplicateInheritable@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAPEAXPEAXK@Z; Microsoft::Diagnostics::RemoteAggregatorManager::DuplicateInheritable(void *,ulong)
0x1800a3542  mov     rbx, rax
0x1800a3545  mov     [rbp+560h+var_5D0], rax
0x1800a3549  xor     r8d, r8d; unsigned int
0x1800a354c  mov     rdx, [rsi+480h]; void *
0x1800a3553  call    ?DuplicateInheritable@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAPEAXPEAXK@Z; Microsoft::Diagnostics::RemoteAggregatorManager::DuplicateInheritable(void *,ulong)
0x1800a3558  mov     [rsp+660h+var_600], rax
0x1800a355d  mov     [rbp+560h+var_5A8], 0
0x1800a3565  mov     [rbp+560h+var_5A0], rdi
0x1800a3569  mov     [rbp+560h+var_598], rbx
0x1800a356d  mov     [rbp+560h+var_590], rax
0x1800a3571  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1800a3578  call    ?GetAsimovEventSerializer@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVAsimovEventSerializer@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetAsimovEventSerializer(void)
0x1800a357d  mov     rcx, [rax+8]
0x1800a3581  mov     [rbp+560h+var_588], rcx
0x1800a3585  mov     rcx, [rsi+478h]; hEvent
0x1800a358c  call    cs:__imp_ResetEvent
0x1800a3593  nop     dword ptr [rax+rax+00h]
0x1800a3598  mov     rcx, [rsi+480h]; hEvent
0x1800a359f  call    cs:__imp_ResetEvent
0x1800a35a6  nop     dword ptr [rax+rax+00h]
0x1800a35ab  lock inc dword ptr [rsi+6A0h]
0x1800a35b2  lea     rbx, [rsi+7B0h]
0x1800a35b9  mov     rcx, rbx; this
0x1800a35bc  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800a35c1  inc     dword ptr [rsi+828h]
0x1800a35c7  mov     rcx, rbx; _Mtx_t
0x1800a35ca  call    cs:__imp__Mtx_unlock
0x1800a35d1  nop     dword ptr [rax+rax+00h]
0x1800a35d6  lea     rdi, [rsi+488h]
0x1800a35dd  mov     rcx, [rdi]; void *
0x1800a35e0  test    rcx, rcx
0x1800a35e3  jz      short loc_1800A35FF
0x1800a35e5  xor     edx, edx; unsigned int
0x1800a35e7  call    ?WaitOrTimeout@Os@Utils@Diagnostics@Microsoft@@SA_NPEAXK@Z; Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(void *,ulong)
0x1800a35ec  test    al, al
0x1800a35ee  jnz     short loc_1800A35FF
0x1800a35f0  xor     edx, edx
0x1800a35f2  mov     rcx, rsi
0x1800a35f5  call    ?RestartChildProcess@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAXVRestartChildProcessReason@EnumDetails@23@@Z; Microsoft::Diagnostics::RemoteAggregatorManager::RestartChildProcess(Microsoft::Diagnostics::EnumDetails::RestartChildProcessReason)
0x1800a35fa  jmp     loc_1800A3947
0x1800a35ff  lea     rax, [rbp+560h+var_5A8]
0x1800a3603  mov     [rbp+560h+StartupInfo.lpReserved2], rax
0x1800a3607  mov     eax, 28h ; '('
0x1800a360c  mov     [rbp+560h+StartupInfo.cbReserved2], ax
0x1800a3610  lea     rax, [rbp+560h+ProcessInformation]
0x1800a3614  mov     [rsp+660h+lpProcessInformation], rax; lpProcessInformation
0x1800a3619  lea     rax, [rbp+560h+StartupInfo]
0x1800a361d  mov     [rsp+660h+lpStartupInfo], rax; lpStartupInfo
0x1800a3622  mov     [rsp+660h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800a362b  mov     [rsp+660h+lpEnvironment], 0; lpEnvironment
0x1800a3634  mov     [rsp+660h+dwCreationFlags], 408h; dwCreationFlags
0x1800a363c  mov     [rsp+660h+bInheritHandles], 1; bInheritHandles
0x1800a3644  xor     r9d, r9d; lpThreadAttributes
0x1800a3647  xor     r8d, r8d; lpProcessAttributes
0x1800a364a  lea     rdx, [rbp+560h+CommandLine]; lpCommandLine
0x1800a3651  xor     ecx, ecx; lpApplicationName
0x1800a3653  call    cs:__imp_CreateProcessW
0x1800a365a  nop     dword ptr [rax+rax+00h]
0x1800a365f  test    eax, eax
0x1800a3661  jz      loc_1800A3863
0x1800a3667  mov     rcx, [rbp+560h+ProcessInformation.hThread]; hObject
0x1800a366b  call    cs:__imp_CloseHandle
0x1800a3672  nop     dword ptr [rax+rax+00h]
0x1800a3677  lea     rbx, [rsi+490h]
0x1800a367e  mov     rcx, rbx; this
0x1800a3681  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800a3686  mov     rcx, [rsi+4E0h]; pwa
0x1800a368d  test    rcx, rcx
0x1800a3690  jz      short loc_1800A36A5
0x1800a3692  xor     r8d, r8d; pftTimeout
0x1800a3695  mov     rdx, [rbp+560h+ProcessInformation.hProcess]; h
0x1800a3699  call    cs:__imp_SetThreadpoolWait
0x1800a36a0  nop     dword ptr [rax+rax+00h]
0x1800a36a5  mov     rcx, rbx; _Mtx_t
0x1800a36a8  call    cs:__imp__Mtx_unlock
0x1800a36af  nop     dword ptr [rax+rax+00h]
0x1800a36b4  mov     rdx, [rbp+560h+ProcessInformation.hProcess]
0x1800a36b8  mov     rcx, rdi
0x1800a36bb  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800a36c0  mov     [rsp+660h+var_5F0], 0
0x1800a36c9  movups  xmm0, xmmword ptr cs:off_180348978; "%DiagtrackRegistryRoot%\\Aggregation"
0x1800a36d0  movdqu  [rsp+660h+var_610], xmm0
0x1800a36d6  mov     [rsp+660h+dwCreationFlags], 0; DWORD
0x1800a36de  mov     [rsp+660h+bInheritHandles], 0F003Fh; int
0x1800a36e6  xor     r9d, r9d
0x1800a36e9  lea     r8, [rsp+660h+var_5F0]
0x1800a36ee  lea     rdx, [rsp+660h+var_610]
0x1800a36f3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a36fa  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x1800a36ff  mov     rcx, [rbp+568h]; this
0x1800a3706  test    eax, eax
0x1800a3708  jns     short loc_1800A371F
0x1800a370a  mov     r9d, eax; char *
0x1800a370d  lea     r8, aOnecoreBaseTel_275; "onecore\\base\\telemetry\\utc\\service"...
0x1800a3714  mov     edx, 15Ch; void *
0x1800a3719  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800a371f  mov     rcx, [rdi]; Process
0x1800a3722  call    cs:__imp_GetProcessId
0x1800a3729  nop     dword ptr [rax+rax+00h]
0x1800a372e  movups  xmm0, xmmword ptr cs:off_18035FE08; "LastRemoteProcessPid"
0x1800a3735  movdqu  [rsp+660h+var_610], xmm0
0x1800a373b  mov     r8d, eax
0x1800a373e  lea     rdx, [rsp+660h+var_610]
0x1800a3743  mov     rcx, [rsp+660h+var_5F0]
0x1800a3748  call    ?SetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@K@Z; Microsoft::Diagnostics::Utils::Registry::SetDword(HKEY__ *,std::wstring_view,ulong)
0x1800a374d  movups  xmm0, xmmword ptr cs:off_18035FE18; "LastRemoteProcessEpoch"
0x1800a3754  movdqu  [rsp+660h+var_610], xmm0
0x1800a375a  mov     r8d, ds:7FFE02C4h
0x1800a3762  lea     rdx, [rsp+660h+var_610]
0x1800a3767  mov     rcx, [rsp+660h+var_5F0]
0x1800a376c  call    ?SetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@K@Z; Microsoft::Diagnostics::Utils::Registry::SetDword(HKEY__ *,std::wstring_view,ulong)
0x1800a3771  nop
0x1800a3772  lea     rcx, [rsp+660h+var_5F0]
0x1800a3777  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a377c  movups  xmm0, xmmword ptr cs:off_18035FDF8; "DisableWatchdogs"
0x1800a3783  movdqu  [rsp+660h+var_610], xmm0
0x1800a3789  lea     rcx, [rsp+660h+var_610]
0x1800a378e  call    ?IsTestHookEnabled@General@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(std::wstring_view)
0x1800a3793  test    al, al
0x1800a3795  jnz     short loc_1800A37AF
0x1800a3797  call    cs:__imp_IsDebuggerPresent
0x1800a379e  nop     dword ptr [rax+rax+00h]
0x1800a37a3  test    eax, eax
0x1800a37a5  jnz     short loc_1800A37AF
0x1800a37a7  mov     r9d, 493E0h
0x1800a37ad  jmp     short loc_1800A37B3
0x1800a37af  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800a37b3  mov     rax, [rsi+478h]
0x1800a37ba  mov     [rbp+560h+Handles], rax
0x1800a37c1  mov     rax, [rsi+480h]
0x1800a37c8  mov     [rbp+560h+var_68], rax
0x1800a37cf  mov     rax, [rdi]
0x1800a37d2  mov     [rbp+560h+var_60], rax
0x1800a37d9  xor     r8d, r8d; bWaitAll
0x1800a37dc  lea     rdx, [rbp+560h+Handles]; lpHandles
0x1800a37e3  lea     ecx, [r8+3]; nCount
0x1800a37e7  call    cs:__imp_WaitForMultipleObjects
0x1800a37ee  nop     dword ptr [rax+rax+00h]
0x1800a37f3  test    eax, eax
0x1800a37f5  jz      short loc_1800A3838
0x1800a37f7  sub     eax, 1
0x1800a37fa  jz      short loc_1800A382B
0x1800a37fc  sub     eax, 1
0x1800a37ff  jz      short loc_1800A382B
0x1800a3801  cmp     eax, 100h
0x1800a3806  jz      short loc_1800A3821
0x1800a3808  mov     rcx, [rbp+568h]; this
0x1800a380f  lea     r8, aOnecoreBaseTel_275; "onecore\\base\\telemetry\\utc\\service"...
0x1800a3816  mov     edx, 180h; void *
0x1800a381b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800a3821  mov     edx, 2
0x1800a3826  jmp     loc_1800A35F2
0x1800a382b  mov     rcx, rsi; this
0x1800a382e  call    ?ArmStartTimer@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::RemoteAggregatorManager::ArmStartTimer(void)
0x1800a3833  jmp     loc_1800A3947
0x1800a3838  mov     dl, 1; bool
0x1800a383a  mov     rcx, rsi; this
0x1800a383d  call    ?UpdateChildProcessReady@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAX_N@Z; Microsoft::Diagnostics::RemoteAggregatorManager::UpdateChildProcessReady(bool)
0x1800a3842  mov     rax, [rsi+788h]
0x1800a3849  cmp     [rsi+780h], rax
0x1800a3850  jz      loc_1800A3947
0x1800a3856  mov     rcx, rsi; this
0x1800a3859  call    ?ArmFlushTimer@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::RemoteAggregatorManager::ArmFlushTimer(void)
0x1800a385e  jmp     loc_1800A3947
0x1800a3863  mov     rcx, [rbp+568h]; this
0x1800a386a  lea     r8, aOnecoreBaseTel_275; "onecore\\base\\telemetry\\utc\\service"...
0x1800a3871  mov     edx, 14Ch; void *
0x1800a3876  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800a387b  xor     al, al
0x1800a387d  xor     cl, cl
0x1800a387f  lea     rdx, aRemoteaggregat; "RemoteAggregatorManager_CreateProcessFa"...
0x1800a3886  mov     [rsp+660h+var_5F0], rdx
0x1800a388b  mov     [rsp+660h+var_5E8], 2Dh ; '-'
0x1800a3894  mov     r8d, 1000000h
0x1800a389a  mov     byte ptr [rsp+660h+lpEnvironment], al
0x1800a389e  mov     byte ptr [rsp+660h+dwCreationFlags], al
0x1800a38a2  mov     byte ptr [rsp+660h+bInheritHandles], cl
0x1800a38a6  mov     r9, 400000000000h
0x1800a38b0  lea     rdx, [rsp+660h+var_5F0]
0x1800a38b5  lea     rcx, [rbp+560h+var_510]
0x1800a38b9  call    ??0AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@UPrivacyDataType@@_KVTriggerPersistence@12@VTriggerLatency@12@_N@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(std::wstring_view,PrivacyDataType,unsigned __int64,Microsoft::Diagnostics::TriggerPersistence,Microsoft::Diagnostics::TriggerLatency,bool)
0x1800a38be  nop
0x1800a38bf  call    cs:__imp_GetLastError
0x1800a38c6  nop     dword ptr [rax+rax+00h]
0x1800a38cb  mov     dword ptr [rsp+660h+var_5F0], eax
0x1800a38cf  lea     rax, aTerminateproce; "TerminateProcessError"
0x1800a38d6  mov     qword ptr [rsp+660h+var_610], rax
0x1800a38db  mov     qword ptr [rsp+660h+var_610+8], 15h
0x1800a38e4  lea     r9, [rsp+660h+var_5F0]
0x1800a38e9  lea     r8, [rsp+660h+var_610]
0x1800a38ee  lea     rdx, [rbp+560h+var_A8]
0x1800a38f5  lea     rcx, [rbp+560h+var_510]
0x1800a38f9  call    ??$AddField@K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBK@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<ulong>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,ulong const &)
0x1800a38fe  xorps   xmm0, xmm0
0x1800a3901  movdqa  [rsp+660h+var_610], xmm0
0x1800a3907  lea     rdx, [rsp+660h+var_610]
0x1800a390c  lea     rcx, [rsp+660h+var_5F0]
0x1800a3911  call    ??$MakeEnumSet@VPersistSyntheticOptions@Diagnostics@Microsoft@@@Enum@Utils@Diagnostics@Microsoft@@SA?AV?$bitset@$01@std@@V?$initializer_list@VPersistSyntheticOptions@Diagnostics@Microsoft@@@5@@Z; Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(std::initializer_list<Microsoft::Diagnostics::PersistSyntheticOptions>)
0x1800a3916  mov     edx, [rax]
0x1800a3918  lea     rcx, [rbp+560h+var_510]; this
0x1800a391c  call    ?PersistSyntheticEvent@AsimovEventSerializer@Diagnostics@Microsoft@@SAJAEAVAsimovSyntheticEvent@23@V?$bitset@$01@std@@@Z; Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent(Microsoft::Diagnostics::AsimovSyntheticEvent &,std::bitset<2>)
0x1800a3921  mov     rcx, [rsi+480h]; hEvent
0x1800a3928  call    cs:__imp_SetEvent
0x1800a392f  nop     dword ptr [rax+rax+00h]
0x1800a3934  mov     rcx, rsi; this
0x1800a3937  call    ?ArmStartTimer@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::RemoteAggregatorManager::ArmStartTimer(void)
0x1800a393c  nop
0x1800a393d  lea     rcx, [rbp+560h+var_510]; this
0x1800a3941  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x1800a3946  nop
0x1800a3947  lea     rcx, [rsp+660h+var_600]
0x1800a394c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a3951  nop
0x1800a3952  lea     rcx, [rbp+560h+var_5D0]
0x1800a3956  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a395b  nop
0x1800a395c  lea     rcx, [rbp+560h+var_5E0]
  ... truncated ...
```
