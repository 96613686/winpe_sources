# Microsoft::Diagnostics::GetKernelDumpActionDef::Execute(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,Microsoft::Diagnostics::EscalationWorkItemState &,Microsoft::Diagnostics::ScenarioInst const &)

- ea: `0x180306a50`
- end: `0x1803073f7`
- name: `?Execute@GetKernelDumpActionDef@Diagnostics@Microsoft@@UEBAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAVEscalationWorkItemState@23@AEBVScenarioInst@23@@Z`
- size: `2471`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800035ec`
- `0x18000409c`
- `0x18001c5b0`
- `0x18001d160`
- `0x18001d200`
- `0x18001e638`
- `0x18001f1fc`
- `0x180020fbc`
- `0x180026ecc`
- `0x1800326cc`
- `0x180034d94`
- `0x180035698`
- `0x18004cf5c`
- `0x1800551b0`
- `0x1800562b8`
- `0x18005d050`
- `0x180086f40`
- `0x18009c71c`
- `0x1800aea68`
- `0x1800e21c4`
- `0x1800f5954`
- `0x180108668`
- `0x18012de40`
- `0x18012eb08`
- `0x18025f0e8`
- `0x1802b5580`
- `0x1802b55d4`
- `0x180306a50`
- `0x180346010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180306cc1`
- `msvcp_win!_Mtx_unlock` at `0x180306de0`
- `msvcp_win!_Mtx_unlock` at `0x180306e26`
- `msvcp_win!_Mtx_unlock` at `0x180306f71`
- `msvcp_win!_Mtx_unlock` at `0x180306fe9`
- `msvcp_win!_Mtx_unlock` at `0x180307106`
- `msvcp_win!_Mtx_unlock` at `0x1803071a3`
- `msvcp_win!_Mtx_unlock` at `0x1803071e1`
- `msvcp_win!_Mtx_unlock` at `0x180306cc1`
- `msvcp_win!_Mtx_unlock` at `0x180306de0`
- `msvcp_win!_Mtx_unlock` at `0x180306e26`
- `msvcp_win!_Mtx_unlock` at `0x180306f71`
- `msvcp_win!_Mtx_unlock` at `0x180306fe9`
- `msvcp_win!_Mtx_unlock` at `0x180307106`
- `msvcp_win!_Mtx_unlock` at `0x1803071a3`
- `msvcp_win!_Mtx_unlock` at `0x1803071e1`
- `ntdll!NtSystemDebugControl` at `0x180307032`
- `ntdll!NtSystemDebugControl` at `0x180307032`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180306b4c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180306b4c`

## string_xrefs

- `0x180306a97`: `onecore\base\telemetry\utc\service\scenarios\actions\getkerneldumpaction.cpp`
- `0x180306aec`: `onecore\base\telemetry\utc\service\scenarios\actions\getkerneldumpaction.cpp`
- `0x180306cac`: `onecore\base\telemetry\utc\service\scenarios\actions\getkerneldumpaction.cpp`
- `0x180306dc0`: `onecore\base\telemetry\utc\service\scenarios\actions\getkerneldumpaction.cpp`
- `0x180306f58`: `onecore\base\telemetry\utc\service\scenarios\actions\getkerneldumpaction.cpp`
- `0x180306fc9`: `onecore\base\telemetry\utc\service\scenarios\actions\getkerneldumpaction.cpp`
- `0x1803070e2`: `onecore\base\telemetry\utc\service\scenarios\actions\getkerneldumpaction.cpp`
- `0x18030717f`: `onecore\base\telemetry\utc\service\scenarios\actions\getkerneldumpaction.cpp`
- `0x180307366`: `onecore\base\telemetry\utc\service\scenarios\actions\getkerneldumpaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::GetKernelDumpActionDef::Execute(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  int appended; // eax
  unsigned int v9; // ebx
  const WCHAR *v10; // rcx
  unsigned __int64 FileTimeAsULL; // r15
  _QWORD *ScenarioDef; // rax
  __int16 v13; // bx
  unsigned int Qword; // ebx
  unsigned __int64 v15; // rdi
  int v16; // r8d
  int v17; // r9d
  int v18; // eax
  unsigned int v19; // ebx
  int v20; // r8d
  int v21; // r9d
  int updated; // eax
  unsigned int v23; // ebx
  NTSTATUS v24; // edi
  _QWORD *v25; // rax
  __int16 v26; // bx
  int v27; // r9d
  int v28; // eax
  unsigned int v29; // ebx
  int v30; // eax
  unsigned int v31; // ebx
  void *v32; // rcx
  int v33; // r8d
  int v34; // r9d
  int v35; // r8d
  int v36; // r9d
  unsigned int v37; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-128h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-128h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-128h]
  int dwCreationDispositionc; // [rsp+20h] [rbp-128h]
  int dwCreationDispositiond; // [rsp+20h] [rbp-128h]
  int v43[4]; // [rsp+40h] [rbp-108h] BYREF
  _QWORD v44[2]; // [rsp+50h] [rbp-F8h] BYREF
  std::_Ref_count_base *v45[2]; // [rsp+60h] [rbp-E8h] BYREF
  void *TokenHandle[2]; // [rsp+70h] [rbp-D8h] BYREF
  unsigned __int64 v47; // [rsp+80h] [rbp-C8h] BYREF
  __int64 v48; // [rsp+88h] [rbp-C0h] BYREF
  _DWORD InputBuffer[10]; // [rsp+90h] [rbp-B8h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-90h]
  __int64 v51; // [rsp+C0h] [rbp-88h]
  int v52; // [rsp+C8h] [rbp-80h]
  int v53; // [rsp+CCh] [rbp-7Ch]
  void *v54; // [rsp+E0h] [rbp-68h]
  LPCWSTR lpFileName[4]; // [rsp+E8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  if ( !a2[1] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
      (const char *)0x8007010BLL,
      dwCreationDisposition);
    return 2147942667LL;
  }
  std::wstring::wstring((__int64)lpFileName, a2);
  *(_OWORD *)TokenHandle = *(_OWORD *)&Microsoft::Diagnostics::GetKernelDumpActionDef::k_kernelDumpFileName;
  appended = Microsoft::Diagnostics::Utils::String::AppendPath((PWSTR)lpFileName);
  v9 = appended;
  if ( appended < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
      (const char *)(unsigned int)appended,
      dwCreationDisposition);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
    return v9;
  }
  v10 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v10 = lpFileName[0];
  v44[0] = CreateFileW(v10, 0xC0000000, 0, 0, 2u, 0x80u, 0);
  memset_0(InputBuffer, 0, 0x48u);
  InputBuffer[0] = 1;
  v52 = *(_BYTE *)(a1 + 128) == 0 ? 8 : 0;
  v50 = v44[0];
  v51 = 0;
  *(_OWORD *)TokenHandle = *(_OWORD *)&off_180369100;
  if ( (unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(TokenHandle) )
    v52 &= ~8u;
  if ( Microsoft::Diagnostics::Utils::Os::GetTotalPhysicalMemoryInBytes() <= 0x800000000LL )
    v53 |= 1u;
  v54 = &Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex;
  std::_Mutex_base::lock((std::_Mutex_base *)&Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex);
  FileTimeAsULL = Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL();
  v47 = 0;
  v48 = 0;
  ScenarioDef = (_QWORD *)Microsoft::Diagnostics::ScenarioInst::GetScenarioDef(a4, v45);
  v13 = *(_WORD *)(*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*ScenarioDef + 80LL))(*ScenarioDef, v43);
  if ( v45[1] )
    std::_Ref_count_base::_Decref(v45[1]);
  if ( v13 == 1 )
    goto LABEL_30;
  *(_OWORD *)v45 = *(_OWORD *)&off_1803690D0;
  *(_OWORD *)v43 = *(_OWORD *)&off_1803690F0;
  Qword = Microsoft::Diagnostics::Utils::Registry::GetQword(-2147483646, v43, v45, &v48);
  if ( (int)(Qword + 0x80000000) >= 0 && Qword != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
      (const char *)Qword,
      dwCreationDispositiona);
    _Mtx_unlock((_Mtx_t)&Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
    return Qword;
  }
  v15 = FileTimeAsULL - v48;
  if ( FileTimeAsULL - v48 > FileTimeAsULL )
  {
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    if ( (unsigned int)dword_18042D328 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 4) )
    {
      *(_QWORD *)v43 = v15;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        (unsigned int)&dword_18042D328,
        (unsigned int)&unk_1803DFB2F,
        v16,
        v17,
        (__int64)v43);
    }
    *(_OWORD *)v45 = *(_OWORD *)&off_1803690D0;
    *(_OWORD *)v43 = *(_OWORD *)&off_1803690F0;
    v18 = Microsoft::Diagnostics::Utils::Registry::SetQword(-2147483646, (int)v43, (int)v45, FileTimeAsULL, 0);
    v19 = v18;
    if ( v18 >= 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
        (const char *)0x87C51041LL,
        dwCreationDispositionb);
      _Mtx_unlock((_Mtx_t)&Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
      return 2277838913LL;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
        (const char *)(unsigned int)v18,
        dwCreationDispositionb);
      _Mtx_unlock((_Mtx_t)&Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
      return v19;
    }
  }
  if ( v15 > 0xC92A69C000LL
    || (*(_OWORD *)v45 = *(_OWORD *)&off_1803690E0,
        *(_OWORD *)v43 = *(_OWORD *)&off_1803690F0,
        Microsoft::Diagnostics::Utils::Registry::GetQword(-2147483646, v43, v45, &v47),
        v47 < 5) )
  {
LABEL_30:
    TokenHandle[0] = 0;
    LOBYTE(TokenHandle[1]) = 0;
    updated = Microsoft::Diagnostics::ThreadPrivilegeManager::UpdatePrivilege(TokenHandle);
    v23 = updated;
    if ( updated < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
        (const char *)(unsigned int)updated,
        dwCreationDispositiona);
      Microsoft::Diagnostics::ThreadPrivilegeManager::~ThreadPrivilegeManager((Microsoft::Diagnostics::ThreadPrivilegeManager *)TokenHandle);
      _Mtx_unlock((_Mtx_t)&Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
      return v23;
    }
    v24 = NtSystemDebugControl(SysDbgClearUmAttachPid|SysDbgQueryTraceInformation, InputBuffer, 0x48u, 0, 0, 0);
    v25 = (_QWORD *)Microsoft::Diagnostics::ScenarioInst::GetScenarioDef(a4, v45);
    v26 = *(_WORD *)(*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v25 + 80LL))(*v25, v43);
    if ( v45[1] )
      std::_Ref_count_base::_Decref(v45[1]);
    if ( v26 == 1 )
      goto LABEL_42;
    v27 = v47;
    if ( !v47 || !v48 )
    {
      *(_OWORD *)v45 = *(_OWORD *)&off_1803690D0;
      *(_OWORD *)v43 = *(_OWORD *)&off_1803690F0;
      v28 = Microsoft::Diagnostics::Utils::Registry::SetQword(-2147483646, (int)v43, (int)v45, FileTimeAsULL, 0);
      v29 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA2,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
          (const char *)(unsigned int)v28,
          dwCreationDispositiond);
        Microsoft::Diagnostics::ThreadPrivilegeManager::~ThreadPrivilegeManager((Microsoft::Diagnostics::ThreadPrivilegeManager *)TokenHandle);
        _Mtx_unlock((_Mtx_t)&Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
        return v29;
      }
      v27 = v47;
    }
    *(_OWORD *)v45 = *(_OWORD *)&off_1803690E0;
    *(_OWORD *)v43 = *(_OWORD *)&off_1803690F0;
    v30 = Microsoft::Diagnostics::Utils::Registry::SetQword(-2147483646, (int)v43, (int)v45, v27 + 1, 0);
    v31 = v30;
    if ( v30 >= 0 )
    {
LABEL_42:
      Microsoft::Diagnostics::ThreadPrivilegeManager::~ThreadPrivilegeManager((Microsoft::Diagnostics::ThreadPrivilegeManager *)TokenHandle);
      _Mtx_unlock((_Mtx_t)&Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex);
      v32 = (void *)(a3 + 168);
      if ( v24 < 0 )
      {
        Microsoft::Diagnostics::WideStringStream::operator<<(v32);
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
        if ( (unsigned int)dword_18042D328 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 4) )
        {
          v43[0] = v24;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18042D328,
            (unsigned int)&unk_1803DFAA3,
            v35,
            v36,
            (__int64)v43);
        }
        if ( v24 == -1073741248 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCA,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
            (const char *)0x87C52307LL,
            dwCreationDispositionc);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
          return 2277843719LL;
        }
        else
        {
          v37 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0xCE,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
                  (const char *)(unsigned int)v24,
                  dwCreationDispositionc);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
          return v37;
        }
      }
      else
      {
        Microsoft::Diagnostics::WideStringStream::operator<<(v32);
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
        *(_OWORD *)v45 = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, TokenHandle);
        Microsoft::Diagnostics::WideStringStream::AppendString((void *)(a3 + 168));
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
        *(_OWORD *)v45 = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, TokenHandle);
        Microsoft::Diagnostics::EscalationWorkItemState::AddCollectedFileToBuilder(a3, v45);
        if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 4) )
        {
          v43[0] = v24;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18042D328,
            (unsigned int)&unk_1803DFA68,
            v33,
            v34,
            (__int64)v43);
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
        return 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA6,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
        (const char *)(unsigned int)v30,
        dwCreationDispositionc);
      Microsoft::Diagnostics::ThreadPrivilegeManager::~ThreadPrivilegeManager((Microsoft::Diagnostics::ThreadPrivilegeManager *)TokenHandle);
      _Mtx_unlock((_Mtx_t)&Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
      return v31;
    }
  }
  else
  {
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    if ( (unsigned int)dword_18042D328 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 4) )
    {
      *(_QWORD *)v43 = v15;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        (unsigned int)&dword_18042D328,
        (unsigned int)&unk_1803DFADB,
        v20,
        v21,
        (__int64)v43);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
      (const char *)0x87C51041LL,
      dwCreationDispositiona);
    _Mtx_unlock((_Mtx_t)&Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
    return 2277838913LL;
  }
}

```

## disassembly

```asm
0x180306a50  push    rbx
0x180306a52  push    rsi
0x180306a53  push    rdi
0x180306a54  push    r12
0x180306a56  push    r13
0x180306a58  push    r14
0x180306a5a  push    r15
0x180306a5c  sub     rsp, 110h
0x180306a63  mov     rax, cs:__security_cookie
0x180306a6a  xor     rax, rsp
0x180306a6d  mov     [rsp+148h+var_40], rax
0x180306a75  mov     r12, r9
0x180306a78  mov     r14, r8
0x180306a7b  mov     rdi, rcx
0x180306a7e  xor     r13d, r13d
0x180306a81  cmp     [rdx+8], r13
0x180306a85  jnz     short loc_180306AAE
0x180306a87  mov     rcx, [rsp+148h]; this
0x180306a8f  mov     ebx, 8007010Bh
0x180306a94  mov     r9d, ebx; char *
0x180306a97  lea     r8, aOnecoreBaseTel_68; "onecore\\base\\telemetry\\utc\\service"...
0x180306a9e  lea     edx, [r13+1Eh]; void *
0x180306aa2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180306aa7  mov     eax, ebx
0x180306aa9  jmp     loc_1803073D3
0x180306aae  lea     rcx, [rsp+148h+lpFileName]
0x180306ab6  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x180306abb  nop
0x180306abc  movups  xmm0, xmmword ptr cs:?k_kernelDumpFileName@GetKernelDumpActionDef@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::GetKernelDumpActionDef::k_kernelDumpFileName
0x180306ac3  movdqu  xmmword ptr [rsp+148h+TokenHandle], xmm0
0x180306ac9  lea     rdx, [rsp+148h+TokenHandle]
0x180306ace  lea     rcx, [rsp+148h+lpFileName]; pszPath
0x180306ad6  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x180306adb  mov     ebx, eax
0x180306add  test    eax, eax
0x180306adf  jns     short loc_180306B12
0x180306ae1  mov     rcx, [rsp+148h]; this
0x180306ae9  mov     r9d, eax; char *
0x180306aec  lea     r8, aOnecoreBaseTel_68; "onecore\\base\\telemetry\\utc\\service"...
0x180306af3  mov     edx, 20h ; ' '; void *
0x180306af8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180306afd  nop
0x180306afe  lea     rcx, [rsp+148h+lpFileName]; this
0x180306b06  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180306b0b  mov     eax, ebx
0x180306b0d  jmp     loc_1803073D3
0x180306b12  lea     rcx, [rsp+148h+lpFileName]
0x180306b1a  cmp     [rsp+148h+var_48], 7
0x180306b23  cmova   rcx, [rsp+148h+lpFileName]; lpFileName
0x180306b2c  mov     [rsp+148h+hTemplateFile], r13; hTemplateFile
0x180306b31  mov     [rsp+148h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180306b39  mov     [rsp+148h+dwCreationDisposition], 2; int
0x180306b41  xor     r9d, r9d; lpSecurityAttributes
0x180306b44  xor     r8d, r8d; dwShareMode
0x180306b47  mov     edx, 0C0000000h; dwDesiredAccess
0x180306b4c  call    cs:__imp_CreateFileW
0x180306b53  nop     dword ptr [rax+rax+00h]
0x180306b58  mov     rbx, rax
0x180306b5b  mov     [rsp+148h+var_F8], rax
0x180306b60  xor     edx, edx; Val
0x180306b62  lea     r8d, [rdx+48h]; Size
0x180306b66  lea     rcx, [rsp+148h+InputBuffer]; void *
0x180306b6e  call    memset_0
0x180306b73  mov     esi, 1
0x180306b78  mov     [rsp+148h+InputBuffer], esi
0x180306b7f  mov     al, [rdi+80h]
0x180306b85  neg     al
0x180306b87  sbb     ecx, ecx
0x180306b89  not     ecx
0x180306b8b  and     ecx, 8
0x180306b8e  mov     [rsp+148h+var_80], ecx
0x180306b95  mov     [rsp+148h+var_90], rbx
0x180306b9d  mov     [rsp+148h+var_88], r13
0x180306ba5  movups  xmm0, xmmword ptr cs:off_180369100; "CollectKernelDumpsUnderMemoryPressure"
0x180306bac  movdqu  xmmword ptr [rsp+148h+TokenHandle], xmm0
0x180306bb2  lea     rcx, [rsp+148h+TokenHandle]
0x180306bb7  call    ?IsTestHookEnabled@General@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(std::wstring_view)
0x180306bbc  test    al, al
0x180306bbe  jz      short loc_180306BC8
0x180306bc0  and     [rsp+148h+var_80], 0FFFFFFF7h
0x180306bc8  call    ?GetTotalPhysicalMemoryInBytes@Os@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Os::GetTotalPhysicalMemoryInBytes(void)
0x180306bcd  mov     rcx, 800000000h
0x180306bd7  cmp     rax, rcx
0x180306bda  ja      short loc_180306BE3
0x180306bdc  or      [rsp+148h+var_7C], esi
0x180306be3  lea     rdi, ?m_kernelDumpMutex@GetKernelDumpActionDef@Diagnostics@Microsoft@@0Vrecursive_mutex@std@@A; std::recursive_mutex Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex
0x180306bea  mov     [rsp+148h+var_68], rdi
0x180306bf2  mov     rcx, rdi; this
0x180306bf5  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180306bfa  nop
0x180306bfb  call    ?GetFileTimeAsULL@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL(void)
0x180306c00  mov     r15, rax
0x180306c03  mov     [rsp+148h+var_C8], r13
0x180306c0b  mov     [rsp+148h+var_C0], r13
0x180306c13  lea     rdx, [rsp+148h+var_E8]
0x180306c18  mov     rcx, r12
0x180306c1b  call    ?GetScenarioDef@ScenarioInst@Diagnostics@Microsoft@@QEBA?AV?$shared_ptr@$$CBVIScenarioDef@Diagnostics@Microsoft@@@std@@XZ; Microsoft::Diagnostics::ScenarioInst::GetScenarioDef(void)
0x180306c20  nop
0x180306c21  mov     rcx, [rax]
0x180306c24  mov     rdx, [rcx]
0x180306c27  mov     rax, [rdx+50h]
0x180306c2b  lea     rdx, [rsp+148h+var_108]
0x180306c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180306c35  movzx   ebx, word ptr [rax]
0x180306c38  mov     rcx, [rsp+148h+var_E8+8]; this
0x180306c3d  test    rcx, rcx
0x180306c40  jz      short loc_180306C47
0x180306c42  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180306c47  cmp     bx, si
0x180306c4a  mov     rsi, 0FFFFFFFF80000002h
0x180306c51  jz      loc_180306FA4
0x180306c57  movups  xmm0, xmmword ptr cs:off_1803690D0; "FirstKernelDumpTime"
0x180306c5e  movdqu  xmmword ptr [rsp+148h+var_E8], xmm0
0x180306c64  movups  xmm1, xmmword ptr cs:off_1803690F0; "%DiagtrackRegistryRoot%\\Scenarios"
0x180306c6b  movdqu  xmmword ptr [rsp+148h+var_108], xmm1
0x180306c71  lea     r9, [rsp+148h+var_C0]
0x180306c79  lea     r8, [rsp+148h+var_E8]
0x180306c7e  lea     rdx, [rsp+148h+var_108]
0x180306c83  mov     rcx, rsi
0x180306c86  call    ?GetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEA_K@Z; Microsoft::Diagnostics::Utils::Registry::GetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64 &)
0x180306c8b  mov     ebx, eax
0x180306c8d  mov     eax, 80000000h
0x180306c92  lea     edx, [rbx+rax]; unsigned int
0x180306c95  test    eax, edx
0x180306c97  jnz     short loc_180306CED
0x180306c99  cmp     ebx, 80070002h
0x180306c9f  jz      short loc_180306CED
0x180306ca1  mov     rcx, [rsp+148h]; this
0x180306ca9  mov     r9d, ebx; char *
0x180306cac  lea     r8, aOnecoreBaseTel_68; "onecore\\base\\telemetry\\utc\\service"...
0x180306cb3  mov     edx, 55h ; 'U'; void *
0x180306cb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180306cbd  nop
0x180306cbe  mov     rcx, rdi; _Mtx_t
0x180306cc1  call    cs:__imp__Mtx_unlock
0x180306cc8  nop     dword ptr [rax+rax+00h]
0x180306ccd  nop
0x180306cce  lea     rcx, [rsp+148h+var_F8]
0x180306cd3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180306cd8  nop
0x180306cd9  lea     rcx, [rsp+148h+lpFileName]; this
0x180306ce1  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180306ce6  mov     eax, ebx
0x180306ce8  jmp     loc_1803073D3
0x180306ced  mov     rdi, r15
0x180306cf0  sub     rdi, [rsp+148h+var_C0]
0x180306cf8  cmp     rdi, r15
0x180306cfb  jbe     loc_180306E52
0x180306d01  lea     rbx, [r14+0A8h]
0x180306d08  lea     rdx, aTimeIntervalCh; "Time interval check produced an underfl"...
0x180306d0f  mov     rcx, rbx; Src
0x180306d12  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180306d17  lea     rdx, aFiletimeInterv; "Filetime interval: "
0x180306d1e  mov     rcx, rbx; Src
0x180306d21  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180306d26  mov     rdx, rdi
0x180306d29  mov     rcx, rbx; Src
0x180306d2c  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@_K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(unsigned __int64)
0x180306d31  lea     rdx, asc_1803721B4; "\r\n"
0x180306d38  mov     rcx, rbx; Src
0x180306d3b  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180306d40  mov     eax, cs:dword_18042D328
0x180306d46  cmp     eax, 2
0x180306d49  jbe     short loc_180306D82
0x180306d4b  mov     edx, 4
0x180306d50  lea     rcx, dword_18042D328
0x180306d57  call    _tlgKeywordOn
0x180306d5c  test    al, al
0x180306d5e  jz      short loc_180306D82
0x180306d60  mov     qword ptr [rsp+148h+var_108], rdi
0x180306d65  lea     rax, [rsp+148h+var_108]
0x180306d6a  mov     qword ptr [rsp+148h+dwCreationDisposition], rax
0x180306d6f  lea     rdx, unk_1803DFB2F
0x180306d76  lea     rcx, dword_18042D328
0x180306d7d  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180306d82  movups  xmm0, xmmword ptr cs:off_1803690D0; "FirstKernelDumpTime"
0x180306d89  movdqu  xmmword ptr [rsp+148h+var_E8], xmm0
0x180306d8f  movups  xmm1, xmmword ptr cs:off_1803690F0; "%DiagtrackRegistryRoot%\\Scenarios"
0x180306d96  movdqu  xmmword ptr [rsp+148h+var_108], xmm1
0x180306d9c  mov     [rsp+148h+dwCreationDisposition], r13d; int
0x180306da1  mov     r9, r15; int
0x180306da4  lea     r8, [rsp+148h+var_E8]; int
0x180306da9  lea     rdx, [rsp+148h+var_108]; int
0x180306dae  mov     rcx, rsi; int
0x180306db1  call    ?SetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_KK@Z; Microsoft::Diagnostics::Utils::Registry::SetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64,ulong)
0x180306db6  mov     ebx, eax
0x180306db8  mov     rcx, [rsp+148h]; this
0x180306dc0  lea     r8, aOnecoreBaseTel_68; "onecore\\base\\telemetry\\utc\\service"...
0x180306dc7  test    eax, eax
0x180306dc9  jns     short loc_180306E0C
0x180306dcb  mov     r9d, eax; char *
0x180306dce  mov     edx, 6Fh ; 'o'; void *
0x180306dd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180306dd8  nop
0x180306dd9  lea     rcx, ?m_kernelDumpMutex@GetKernelDumpActionDef@Diagnostics@Microsoft@@0Vrecursive_mutex@std@@A; _Mtx_t
0x180306de0  call    cs:__imp__Mtx_unlock
0x180306de7  nop     dword ptr [rax+rax+00h]
0x180306dec  nop
0x180306ded  lea     rcx, [rsp+148h+var_F8]
0x180306df2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180306df7  nop
0x180306df8  lea     rcx, [rsp+148h+lpFileName]; this
0x180306e00  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180306e05  mov     eax, ebx
0x180306e07  jmp     loc_1803073D3
0x180306e0c  mov     ebx, 87C51041h
0x180306e11  mov     r9d, ebx; char *
0x180306e14  mov     edx, 71h ; 'q'; void *
0x180306e19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180306e1e  nop
0x180306e1f  lea     rcx, ?m_kernelDumpMutex@GetKernelDumpActionDef@Diagnostics@Microsoft@@0Vrecursive_mutex@std@@A; _Mtx_t
0x180306e26  call    cs:__imp__Mtx_unlock
0x180306e2d  nop     dword ptr [rax+rax+00h]
0x180306e32  nop
0x180306e33  lea     rcx, [rsp+148h+var_F8]
0x180306e38  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180306e3d  nop
0x180306e3e  lea     rcx, [rsp+148h+lpFileName]; this
0x180306e46  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180306e4b  mov     eax, ebx
0x180306e4d  jmp     loc_1803073D3
0x180306e52  mov     rax, 0C92A69C000h
0x180306e5c  cmp     rdi, rax
0x180306e5f  ja      loc_180306F9D
0x180306e65  movups  xmm0, xmmword ptr cs:off_1803690E0; "KernelDumpCounter"
0x180306e6c  movdqu  xmmword ptr [rsp+148h+var_E8], xmm0
0x180306e72  movups  xmm1, xmmword ptr cs:off_1803690F0; "%DiagtrackRegistryRoot%\\Scenarios"
0x180306e79  movdqu  xmmword ptr [rsp+148h+var_108], xmm1
0x180306e7f  lea     r9, [rsp+148h+var_C8]
0x180306e87  lea     r8, [rsp+148h+var_E8]
0x180306e8c  lea     rdx, [rsp+148h+var_108]
0x180306e91  mov     rcx, rsi
0x180306e94  call    ?GetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEA_K@Z; Microsoft::Diagnostics::Utils::Registry::GetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64 &)
0x180306e99  cmp     [rsp+148h+var_C8], 5
0x180306ea2  jb      loc_180306F9D
0x180306ea8  lea     rbx, [r14+0A8h]
0x180306eaf  lea     rdx, aMaximumKernelD; "Maximum kernel dump per 24 hours limit "...
0x180306eb6  mov     rcx, rbx; Src
0x180306eb9  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180306ebe  lea     rdx, aTimefromfirstd; "TimeFromFirstDump: "
0x180306ec5  mov     rcx, rbx; Src
0x180306ec8  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180306ecd  mov     rdx, rdi
0x180306ed0  mov     rcx, rbx; Src
0x180306ed3  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@_K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(unsigned __int64)
0x180306ed8  lea     rdx, aKerneldumpcoun; "KernelDumpCount: "
0x180306edf  mov     rcx, rbx; Src
0x180306ee2  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180306ee7  mov     rdx, [rsp+148h+var_C8]
0x180306eef  mov     rcx, rbx; Src
0x180306ef2  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@_K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(unsigned __int64)
0x180306ef7  lea     rdx, asc_1803721B4; "\r\n"
0x180306efe  mov     rcx, rbx; Src
0x180306f01  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180306f06  mov     eax, cs:dword_18042D328
0x180306f0c  cmp     eax, 2
0x180306f0f  jbe     short loc_180306F48
0x180306f11  mov     edx, 4
0x180306f16  lea     rcx, dword_18042D328
0x180306f1d  call    _tlgKeywordOn
0x180306f22  test    al, al
0x180306f24  jz      short loc_180306F48
0x180306f26  mov     qword ptr [rsp+148h+var_108], rdi
0x180306f2b  lea     rax, [rsp+148h+var_108]
0x180306f30  mov     qword ptr [rsp+148h+dwCreationDisposition], rax; int
0x180306f35  lea     rdx, unk_1803DFADB
0x180306f3c  lea     rcx, dword_18042D328
0x180306f43  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180306f48  mov     rcx, [rsp+148h]; this
0x180306f50  mov     ebx, 87C51041h
0x180306f55  mov     r9d, ebx; char *
0x180306f58  lea     r8, aOnecoreBaseTel_68; "onecore\\base\\telemetry\\utc\\service"...
0x180306f5f  mov     edx, 87h; void *
0x180306f64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180306f69  nop
0x180306f6a  lea     rcx, ?m_kernelDumpMutex@GetKernelDumpActionDef@Diagnostics@Microsoft@@0Vrecursive_mutex@std@@A; _Mtx_t
0x180306f71  call    cs:__imp__Mtx_unlock
0x180306f78  nop     dword ptr [rax+rax+00h]
0x180306f7d  nop
0x180306f7e  lea     rcx, [rsp+148h+var_F8]
0x180306f83  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180306f88  nop
0x180306f89  lea     rcx, [rsp+148h+lpFileName]; this
0x180306f91  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180306f96  mov     eax, ebx
0x180306f98  jmp     loc_1803073D3
0x180306f9d  lea     rdi, ?m_kernelDumpMutex@GetKernelDumpActionDef@Diagnostics@Microsoft@@0Vrecursive_mutex@std@@A; std::recursive_mutex Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex
0x180306fa4  mov     [rsp+148h+TokenHandle], r13
0x180306fa9  mov     byte ptr [rsp+148h+TokenHandle+8], r13b
0x180306fae  lea     rcx, [rsp+148h+TokenHandle]; TokenHandle
0x180306fb3  call    ?UpdatePrivilege@ThreadPrivilegeManager@Diagnostics@Microsoft@@QEAAJK_N@Z; Microsoft::Diagnostics::ThreadPrivilegeManager::UpdatePrivilege(ulong,bool)
0x180306fb8  mov     ebx, eax
0x180306fba  test    eax, eax
0x180306fbc  jns     short loc_180307015
0x180306fbe  mov     rcx, [rsp+148h]; this
0x180306fc6  mov     r9d, eax; char *
0x180306fc9  lea     r8, aOnecoreBaseTel_68; "onecore\\base\\telemetry\\utc\\service"...
0x180306fd0  mov     edx, 8Eh; void *
0x180306fd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180306fda  nop
  ... truncated ...
```
