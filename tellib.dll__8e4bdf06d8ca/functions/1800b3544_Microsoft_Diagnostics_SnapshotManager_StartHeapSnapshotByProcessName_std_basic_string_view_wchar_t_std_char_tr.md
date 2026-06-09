# Microsoft::Diagnostics::SnapshotManager::StartHeapSnapshotByProcessName(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,unsigned __int64,bool,bool,Microsoft::Diagnostics::EscalationWorkItemState &,Microsoft::Diagnostics::ScenarioInst const &)

- ea: `0x1800b3544`
- end: `0x1800b4167`
- name: `?StartHeapSnapshotByProcessName@SnapshotManager@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_K_N2AEAVEscalationWorkItemState@23@AEBVScenarioInst@23@@Z`
- size: `3107`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b30d0`

## callees

- `0x180007108`
- `0x18001d160`
- `0x18001d200`
- `0x18001d5ac`
- `0x18001e638`
- `0x180020fbc`
- `0x180026ecc`
- `0x180029954`
- `0x180030a50`
- `0x180032688`
- `0x1800326cc`
- `0x180040b90`
- `0x1800524a8`
- `0x180053a84`
- `0x18005d050`
- `0x18008bd1c`
- `0x1800aea68`
- `0x1800af694`
- `0x1800b1a08`
- `0x1800b2a3c`
- `0x1800b3544`
- `0x1800b46d8`
- `0x1800b4838`
- `0x1800d6f58`
- `0x1800e28dc`
- `0x1800fc1dc`
- `0x18012de40`
- `0x18012eb08`
- `0x1801cff7c`
- `0x1801de718`
- `0x18026620c`
- `0x18026632c`
- `0x180266ef8`
- `0x180346010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3bc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3bc0`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x1800b3bac`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x1800b3bac`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x1800b3995`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x1800b3995`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x1800b3949`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x1800b3949`

## string_xrefs

- `0x1800b35b2`: `onecore\base\telemetry\utc\service\scenarios\tracing\snapshotmanager.cpp`
- `0x1800b3710`: `onecore\base\telemetry\utc\service\scenarios\tracing\snapshotmanager.cpp`
- `0x1800b39b1`: `onecore\base\telemetry\utc\service\scenarios\tracing\snapshotmanager.cpp`
- `0x1800b3bdd`: `onecore\base\telemetry\utc\service\scenarios\tracing\snapshotmanager.cpp`
- `0x1800b3d7a`: `onecore\base\telemetry\utc\service\scenarios\tracing\snapshotmanager.cpp`
- `0x1800b3e87`: `onecore\base\telemetry\utc\service\scenarios\tracing\snapshotmanager.cpp`
- `0x1800b3ff7`: `onecore\base\telemetry\utc\service\scenarios\tracing\snapshotmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::SnapshotManager::StartHeapSnapshotByProcessName(
        Microsoft::Diagnostics::SnapshotManager *a1,
        __m128i *a2,
        __int64 a3,
        char a4,
        char a5,
        _BYTE *a6,
        __int64 a7)
{
  int v10; // esi
  unsigned __int64 v12; // r13
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  char v16; // bl
  _QWORD *v17; // rax
  __int64 v18; // r8
  __int64 v19; // rcx
  int v20; // eax
  unsigned int v21; // esi
  __m128i v22; // xmm6
  _QWORD *ScenarioDef; // rax
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rdx
  __m128i si128; // xmm6
  void *v28; // r8
  void *appended; // rax
  void *v30; // rax
  void *v31; // rax
  char *Toolhelp32Snapshot; // rbx
  const char *v33; // r9
  const char *v34; // r9
  unsigned int LastError; // edi
  __int64 v36; // rax
  __int64 v37; // rdx
  const char *v38; // r9
  __int64 v39; // rbx
  gsl::details *v40; // rcx
  __int64 v41; // r8
  __int64 v42; // rcx
  int v43; // eax
  unsigned int v44; // esi
  __int64 v45; // rsi
  gsl::details *v46; // rcx
  int updated; // eax
  __int64 v48; // rax
  void *v49; // rax
  void *v50; // rax
  void *v51; // rax
  __int64 v52; // rax
  void *v53; // rax
  void *v54; // rax
  void *v55; // rax
  __int64 v56; // rax
  void *v57; // rax
  void *v58; // rax
  int v59; // [rsp+20h] [rbp-388h]
  __int128 v60; // [rsp+40h] [rbp-368h] BYREF
  __int64 v61; // [rsp+50h] [rbp-358h]
  char v62; // [rsp+58h] [rbp-350h] BYREF
  _BYTE v63[7]; // [rsp+59h] [rbp-34Fh] BYREF
  __m128i v64; // [rsp+60h] [rbp-348h] BYREF
  std::_Ref_count_base *v65[2]; // [rsp+70h] [rbp-338h] BYREF
  __m128i v66; // [rsp+80h] [rbp-328h] BYREF
  _QWORD v67[2]; // [rsp+90h] [rbp-318h] BYREF
  Microsoft::Diagnostics::SnapshotManager *v68; // [rsp+A0h] [rbp-308h]
  PROCESSENTRY32W pe; // [rsp+B0h] [rbp-2F8h] BYREF
  __int128 v70; // [rsp+2F0h] [rbp-B8h] BYREF
  __int64 v71; // [rsp+300h] [rbp-A8h]
  __m128i v72; // [rsp+308h] [rbp-A0h]
  _QWORD v73[4]; // [rsp+318h] [rbp-90h] BYREF
  DWORD th32ProcessID; // [rsp+338h] [rbp-70h] BYREF
  _QWORD v75[2]; // [rsp+340h] [rbp-68h] BYREF
  __m128i v76; // [rsp+350h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+0h]

  v68 = a1;
  v10 = 0;
  v64.m128i_i32[0] = 0;
  if ( !a2->m128i_i64[1] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\snapshotmanager.cpp",
      (const char *)0x80070057LL,
      v59);
    return 2147942487LL;
  }
  v66 = *a2;
  Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(a7, v73, &v66);
  v12 = 1000 * a3 + Microsoft::Diagnostics::Utils::Time::QueryUbiTime() / 0x2710;
  v67[0] = v12;
  v60 = 0;
  v61 = 0;
  if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 68) )
  {
    v16 = a5;
    v62 = a5;
    v63[0] = a4;
    v17 = v73;
    if ( v73[3] > 7u )
      v17 = (_QWORD *)v73[0];
    v64.m128i_i64[0] = (__int64)v17;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
      v13,
      (unsigned int)&unk_1803D4CA8,
      v14,
      v15,
      (__int64)&v64,
      (__int64)v63,
      (__int64)&v62);
  }
  else
  {
    v16 = a5;
  }
  if ( v16 )
  {
    if ( a6[19] < a6[18] )
    {
      std::wstring::operator std::wstring_view(v73, &v66);
      v64.m128i_i64[0] = 1;
      v64.m128i_i64[1] = (__int64)&v66;
      LOBYTE(v18) = 1;
      v20 = Microsoft::Diagnostics::SnapshotManager::ConfigureHeapSnapshotByProcessName(v19, &v64, v18);
      v21 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8D,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\snapshotmanager.cpp",
          (const char *)(unsigned int)v20,
          v59);
        if ( (_QWORD)v60 )
        {
          std::_Destroy_range<std::allocator<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>>(
            v60,
            *((_QWORD *)&v60 + 1));
          std::_Deallocate<16>((void *)v60, (const struct std::nothrow_t *)(16 * ((v61 - (__int64)v60) >> 4)));
          v60 = 0;
          v61 = 0;
        }
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
        return v21;
      }
      Microsoft::Diagnostics::LifetimeManager::GetScenarioCounterStorage((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      v22 = v66;
      ScenarioDef = (_QWORD *)Microsoft::Diagnostics::ScenarioInst::GetScenarioDef(a7, v65);
      v24 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*ScenarioDef + 72LL))(*ScenarioDef);
      v64 = v22;
      Microsoft::Diagnostics::ScenarioCounterStorage::SetProcessNameForSnapshotScenarios(v25, v24, &v64);
      if ( v65[1] )
        std::_Ref_count_base::_Decref(v65[1]);
      LODWORD(v70) = 0;
      std::wstring::wstring((char *)&v70 + 8, v73);
      v26 = *((_QWORD *)&v60 + 1);
      if ( *((_QWORD *)&v60 + 1) == v61 )
      {
        std::vector<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>::_Emplace_reallocate<std::pair<int,std::wstring>,unsigned __int64 &>(
          &v60,
          *((_QWORD *)&v60 + 1),
          &v70,
          v67);
        si128 = _mm_load_si128((const __m128i *)&_xmm);
      }
      else
      {
        **((_DWORD **)&v60 + 1) = v70;
        *(_QWORD *)(v26 + 8) = *((_QWORD *)&v70 + 1);
        *(_QWORD *)(v26 + 16) = v71;
        *(__m128i *)(v26 + 24) = v72;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v72 = si128;
        WORD4(v70) = 0;
        *(_QWORD *)(v26 + 40) = v12;
        *((_QWORD *)&v60 + 1) += 48LL;
      }
      v10 = 1;
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)((char *)&v70 + 8));
      Microsoft::Diagnostics::WideStringStream::operator<<(a6 + 168);
      *(_OWORD *)v65 = *(_OWORD *)std::wstring::operator std::wstring_view(v73, &v64);
      appended = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(v28);
      Microsoft::Diagnostics::WideStringStream::operator<<(appended);
      goto LABEL_23;
    }
    v30 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(a6 + 168);
    *(__m128i *)v65 = *a2;
    v31 = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(v30);
    Microsoft::Diagnostics::WideStringStream::operator<<(v31);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
LABEL_23:
  if ( !a4 )
    goto LABEL_74;
  if ( a6[19] >= a6[18] )
  {
    v57 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(a6 + 168);
    *(__m128i *)v65 = *a2;
    v58 = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(v57);
    Microsoft::Diagnostics::WideStringStream::operator<<(v58);
    goto LABEL_74;
  }
  Toolhelp32Snapshot = (char *)CreateToolhelp32Snapshot(2u, 0);
  v64.m128i_i64[0] = (__int64)Toolhelp32Snapshot;
  if ( (unsigned __int64)(Toolhelp32Snapshot - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xA1,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\snapshotmanager.cpp",
                  v33);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(&v64);
    if ( (_QWORD)v60 )
    {
      std::_Destroy_range<std::allocator<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>>(
        v60,
        *((_QWORD *)&v60 + 1));
      std::_Deallocate<16>((void *)v60, (const struct std::nothrow_t *)(16 * ((v61 - (__int64)v60) >> 4)));
      v60 = 0;
      v61 = 0;
    }
LABEL_72:
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
    return LastError;
  }
  memset_0(&pe.cntUsage, 0, 0x234u);
  pe.dwSize = 568;
  if ( !Process32FirstW(Toolhelp32Snapshot, &pe) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xA6,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\snapshotmanager.cpp",
                  v34);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(&v64);
    if ( (_QWORD)v60 )
    {
      std::_Destroy_range<std::allocator<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>>(
        v60,
        *((_QWORD *)&v60 + 1));
      std::_Deallocate<16>((void *)v60, (const struct std::nothrow_t *)(16 * ((v61 - (__int64)v60) >> 4)));
      v60 = 0;
      v61 = 0;
    }
    goto LABEL_72;
  }
  v70 = 0;
  v71 = 0;
  while ( 1 )
  {
    v36 = -1;
    do
      ++v36;
    while ( pe.szExeFile[v36] );
    v66.m128i_i64[0] = (__int64)pe.szExeFile;
    v66.m128i_i64[1] = v36;
    *(__m128i *)v65 = *a2;
    if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v65, &v66) )
      goto LABEL_43;
    if ( a6[19] >= a6[18] )
      break;
    if ( *((_QWORD *)&v70 + 1) == v71 )
    {
      std::vector<enum _TDH_IN_TYPE>::_Emplace_reallocate<enum _TDH_IN_TYPE const &>(
        &v70,
        *((_QWORD *)&v70 + 1),
        &pe.th32ProcessID);
    }
    else
    {
      **((_DWORD **)&v70 + 1) = pe.th32ProcessID;
      *((_QWORD *)&v70 + 1) += 4LL;
    }
    th32ProcessID = pe.th32ProcessID;
    std::wstring::wstring(v75, v73);
    v37 = *((_QWORD *)&v60 + 1);
    if ( *((_QWORD *)&v60 + 1) == v61 )
    {
      std::vector<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>::_Emplace_reallocate<std::pair<int,std::wstring>,unsigned __int64 &>(
        &v60,
        *((_QWORD *)&v60 + 1),
        &th32ProcessID,
        v67);
    }
    else
    {
      **((_DWORD **)&v60 + 1) = th32ProcessID;
      *(_QWORD *)(v37 + 8) = v75[0];
      *(_QWORD *)(v37 + 16) = v75[1];
      *(__m128i *)(v37 + 24) = v76;
      v76 = si128;
      LOWORD(v75[0]) = 0;
      *(_QWORD *)(v37 + 40) = v12;
      *((_QWORD *)&v60 + 1) += 48LL;
    }
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v75);
    if ( ++a6[19] >= a6[18] )
    {
      v48 = Microsoft::Diagnostics::WideStringStream::operator<<(a6 + 168);
      v49 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v48, (unsigned __int8)a6[18]);
      v50 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v49);
      *(__m128i *)v65 = *a2;
      v51 = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(v50);
      v52 = Microsoft::Diagnostics::WideStringStream::operator<<(v51);
      v53 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v52, pe.th32ProcessID);
      goto LABEL_68;
    }
    v10 |= 2u;
LABEL_43:
    if ( !Process32NextW(Toolhelp32Snapshot, &pe) )
      goto LABEL_44;
  }
  v54 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(a6 + 168);
  *(__m128i *)v65 = *a2;
  v55 = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(v54);
  v56 = Microsoft::Diagnostics::WideStringStream::operator<<(v55);
  v53 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v56, pe.th32ProcessID);
LABEL_68:
  Microsoft::Diagnostics::WideStringStream::operator<<(v53);
LABEL_44:
  if ( GetLastError() != 18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCA,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\snapshotmanager.cpp",
                  v38);
    std::vector<enum _TDH_IN_TYPE>::~vector<enum _TDH_IN_TYPE>(&v70);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(&v64);
    if ( (_QWORD)v60 )
    {
      std::_Destroy_range<std::allocator<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>>(
        v60,
        *((_QWORD *)&v60 + 1));
      std::_Deallocate<16>((void *)v60, (const struct std::nothrow_t *)(16 * ((v61 - (__int64)v60) >> 4)));
      v60 = 0;
      v61 = 0;
    }
    goto LABEL_72;
  }
  v39 = v70;
  if ( (_QWORD)v70 == *((_QWORD *)&v70 + 1) )
  {
    std::vector<enum _TDH_IN_TYPE>::~vector<enum _TDH_IN_TYPE>(&v70);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(&v64);
    if ( (_QWORD)v60 )
    {
      std::_Destroy_range<std::allocator<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>>(
        v60,
        *((_QWORD *)&v60 + 1));
      std::_Deallocate<16>((void *)v60, (const struct std::nothrow_t *)(16 * ((v61 - (__int64)v60) >> 4)));
      v60 = 0;
      v61 = 0;
    }
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
    return 1168;
  }
  gsl::details::extent_type<-1>::extent_type<-1>(v67, (__int64)(*((_QWORD *)&v70 + 1) - v70) >> 2);
  v67[1] = v39;
  if ( v67[0] == -1 || !v39 && v67[0] )
  {
    gsl::details::terminate(v40);
    JUMPOUT(0x1800B4165LL);
  }
  *(_OWORD *)v65 = *(_OWORD *)gsl::span<unsigned long const,-1>::span<unsigned long const,-1>(&v66, v67);
  LOBYTE(v41) = 1;
  v43 = Microsoft::Diagnostics::SnapshotManager::ConfigureHeapSnapshotByPid(v42, v65, v41);
  v44 = v43;
  if ( v43 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\snapshotmanager.cpp",
      (const char *)(unsigned int)v43,
      v59);
    std::vector<enum _TDH_IN_TYPE>::~vector<enum _TDH_IN_TYPE>(&v70);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(&v64);
    if ( (_QWORD)v60 )
    {
      std::_Destroy_range<std::allocator<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>>(
        v60,
        *((_QWORD *)&v60 + 1));
      std::_Deallocate<16>((void *)v60, (const struct std::nothrow_t *)(16 * ((v61 - (__int64)v60) >> 4)));
      v60 = 0;
      v61 = 0;
    }
LABEL_58:
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
    return v44;
  }
  v45 = v60;
  gsl::details::extent_type<-1>::extent_type<-1>(
    v65,
    0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v60 + 1) - v60) >> 4));
  if ( v65[0] == (std::_Ref_count_base *)-1LL || !v45 && v65[0] )
  {
    gsl::details::terminate(v46);
    __debugbreak();
  }
  v66.m128i_i64[0] = (__int64)v65[0];
  v66.m128i_i64[1] = v45;
  updated = Microsoft::Diagnostics::SnapshotManager::TryUpdateSnapshotConditionalTimer(v68);
  v44 = updated;
  if ( updated < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\snapshotmanager.cpp",
      (const char *)(unsigned int)updated,
      v59);
    std::vector<enum _TDH_IN_TYPE>::~vector<enum _TDH_IN_TYPE>(&v70);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(&v64);
    if ( (_QWORD)v60 )
    {
      std::_Destroy_range<std::allocator<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>>(
        v60,
        *((_QWORD *)&v60 + 1));
      std::_Deallocate<16>((void *)v60, (const struct std::nothrow_t *)(16 * ((v61 - (__int64)v60) >> 4)));
      v60 = 0;
      v61 = 0;
    }
    goto LABEL_58;
  }
  std::vector<enum _TDH_IN_TYPE>::~vector<enum _TDH_IN_TYPE>(&v70);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(&v64);
LABEL_74:
  Microsoft::Diagnostics::WideStringStream::operator<<(a6 + 168);
  if ( (_QWORD)v60 )
  {
    std::_Destroy_range<std::allocator<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>>(
      v60,
      *((_QWORD *)&v60 + 1));
    std::_Deallocate<16>((void *)v60, (const struct std::nothrow_t *)(16 * ((v61 - (__int64)v60) >> 4)));
    v60 = 0;
    v61 = 0;
  }
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
  return 0;
}

```

## disassembly

```asm
0x1800b3544  mov     rax, rsp
0x1800b3547  mov     [rax+18h], rbx
0x1800b354b  mov     [rax+20h], rsi
0x1800b354f  push    rdi
0x1800b3550  push    r12
0x1800b3552  push    r13
0x1800b3554  push    r14
0x1800b3556  push    r15
0x1800b3558  sub     rsp, 380h
0x1800b355f  movaps  xmmword ptr [rax-38h], xmm6
0x1800b3563  mov     rax, cs:__security_cookie
0x1800b356a  xor     rax, rsp
0x1800b356d  mov     [rsp+3A8h+var_48], rax
0x1800b3575  mov     r12b, r9b
0x1800b3578  mov     rbx, r8
0x1800b357b  mov     r14, rdx
0x1800b357e  mov     [rsp+3A8h+var_308], rcx
0x1800b3586  mov     rdi, [rsp+3A8h+arg_28]
0x1800b358e  mov     r15, [rsp+3A8h+arg_30]
0x1800b3596  xor     esi, esi
0x1800b3598  mov     dword ptr [rsp+3A8h+var_348], esi
0x1800b359c  cmp     [rdx+8], rsi
0x1800b35a0  jnz     short loc_1800B35C8
0x1800b35a2  mov     rcx, [rsp+3A8h]; this
0x1800b35aa  mov     ebx, 80070057h
0x1800b35af  mov     r9d, ebx; char *
0x1800b35b2  lea     r8, aOnecoreBaseTel_206; "onecore\\base\\telemetry\\utc\\service"...
0x1800b35b9  lea     edx, [rsi+78h]; void *
0x1800b35bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b35c1  mov     eax, ebx
0x1800b35c3  jmp     loc_1800B4127
0x1800b35c8  movups  xmm0, xmmword ptr [rdx]
0x1800b35cb  movdqu  [rsp+3A8h+var_328], xmm0
0x1800b35d4  lea     r8, [rsp+3A8h+var_328]
0x1800b35dc  lea     rdx, [rsp+3A8h+var_90]
0x1800b35e4  mov     rcx, r15
0x1800b35e7  call    ?ExpandPropertyIdentifiers@ScenarioInst@Diagnostics@Microsoft@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z; Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(std::wstring_view)
0x1800b35ec  nop
0x1800b35ed  call    ?QueryUbiTime@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::QueryUbiTime(void)
0x1800b35f2  mov     rcx, rax
0x1800b35f5  mov     rax, 346DC5D63886594Bh
0x1800b35ff  mul     rcx
0x1800b3602  mov     r13, rdx
0x1800b3605  shr     r13, 0Bh
0x1800b3609  imul    rax, rbx, 3E8h
0x1800b3610  add     r13, rax
0x1800b3613  mov     [rsp+3A8h+var_318], r13
0x1800b361b  xorps   xmm0, xmm0
0x1800b361e  movdqu  [rsp+3A8h+var_368], xmm0
0x1800b3624  mov     [rsp+3A8h+var_358], 0
0x1800b362d  mov     eax, cs:dword_18042D328
0x1800b3633  cmp     eax, 4
0x1800b3636  jbe     short loc_1800B36A8
0x1800b3638  mov     edx, 44h ; 'D'
0x1800b363d  lea     rcx, dword_18042D328
0x1800b3644  call    _tlgKeywordOn
0x1800b3649  test    al, al
0x1800b364b  jz      short loc_1800B36A8
0x1800b364d  mov     bl, [rsp+3A8h+arg_20]
0x1800b3654  mov     [rsp+3A8h+var_350], bl
0x1800b3658  mov     [rsp+3A8h+var_34F], r12b
0x1800b365d  lea     rax, [rsp+3A8h+var_90]
0x1800b3665  cmp     [rsp+3A8h+var_78], 7
0x1800b366e  cmova   rax, [rsp+3A8h+var_90]
0x1800b3677  mov     qword ptr [rsp+3A8h+var_348], rax
0x1800b367c  lea     rax, [rsp+3A8h+var_350]
0x1800b3681  mov     [rsp+3A8h+var_378], rax
0x1800b3686  lea     rax, [rsp+3A8h+var_34F]
0x1800b368b  mov     [rsp+3A8h+var_380], rax
0x1800b3690  lea     rax, [rsp+3A8h+var_348]
0x1800b3695  mov     [rsp+3A8h+var_388], rax
0x1800b369a  lea     rdx, unk_1803D4CA8
0x1800b36a1  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x1800b36a6  jmp     short loc_1800B36AF
0x1800b36a8  mov     bl, [rsp+3A8h+arg_20]
0x1800b36af  test    bl, bl
0x1800b36b1  jz      loc_1800B3924
0x1800b36b7  mov     al, [rdi+12h]
0x1800b36ba  cmp     [rdi+13h], al
0x1800b36bd  jnb     loc_1800B38EB
0x1800b36c3  lea     rdx, [rsp+3A8h+var_328]
0x1800b36cb  lea     rcx, [rsp+3A8h+var_90]
0x1800b36d3  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800b36d8  mov     qword ptr [rsp+3A8h+var_348], 1
0x1800b36e1  lea     rax, [rsp+3A8h+var_328]
0x1800b36e9  mov     qword ptr [rsp+3A8h+var_348+8], rax
0x1800b36ee  mov     r8b, 1
0x1800b36f1  lea     rdx, [rsp+3A8h+var_348]
0x1800b36f6  call    ?ConfigureHeapSnapshotByProcessName@SnapshotManager@Diagnostics@Microsoft@@AEBAJV?$span@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0?0@gsl@@_N@Z; Microsoft::Diagnostics::SnapshotManager::ConfigureHeapSnapshotByProcessName(gsl::span<std::wstring_view,-1>,bool)
0x1800b36fb  mov     esi, eax
0x1800b36fd  test    eax, eax
0x1800b36ff  jns     loc_1800B3788
0x1800b3705  mov     rcx, [rsp+3A8h]; this
0x1800b370d  mov     r9d, eax; char *
0x1800b3710  lea     r8, aOnecoreBaseTel_206; "onecore\\base\\telemetry\\utc\\service"...
0x1800b3717  mov     edx, 8Dh; void *
0x1800b371c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3721  nop
0x1800b3722  mov     rcx, qword ptr [rsp+3A8h+var_368]
0x1800b3727  test    rcx, rcx
0x1800b372a  jz      short loc_1800B3774
0x1800b372c  mov     rdx, qword ptr [rsp+3A8h+var_368+8]
0x1800b3731  call    ??$_Destroy_range@V?$allocator@U?$pair@U?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@std@@@std@@@std@@YAXPEAU?$pair@U?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@0@QEAU10@AEAV?$allocator@U?$pair@U?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@std@@@0@@Z; std::_Destroy_range<std::allocator<std::pair<std::pair<ulong,std::wstring>,unsigned __int64>>>(std::pair<std::pair<ulong,std::wstring>,unsigned __int64> *,std::pair<std::pair<ulong,std::wstring>,unsigned __int64> * const,std::allocator<std::pair<std::pair<ulong,std::wstring>,unsigned __int64>> &)
0x1800b3736  mov     rcx, qword ptr [rsp+3A8h+var_368]
0x1800b373b  mov     rax, [rsp+3A8h+var_358]
0x1800b3740  sub     rax, rcx
0x1800b3743  sar     rax, 4
0x1800b3747  mov     rbx, 0AAAAAAAAAAAAAAABh
0x1800b3751  imul    rax, rbx
0x1800b3755  lea     rdx, [rax+rax*2]
0x1800b3759  shl     rdx, 4
0x1800b375d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800b3762  xorps   xmm0, xmm0
0x1800b3765  movdqu  [rsp+3A8h+var_368], xmm0
0x1800b376b  mov     [rsp+3A8h+var_358], 0
0x1800b3774  lea     rcx, [rsp+3A8h+var_90]; this
0x1800b377c  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800b3781  mov     eax, esi
0x1800b3783  jmp     loc_1800B4127
0x1800b3788  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1800b378f  call    ?GetScenarioCounterStorage@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVScenarioCounterStorage@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetScenarioCounterStorage(void)
0x1800b3794  movups  xmm6, [rsp+3A8h+var_328]
0x1800b379c  lea     rdx, [rsp+3A8h+var_338]
0x1800b37a1  mov     rcx, r15
0x1800b37a4  call    ?GetScenarioDef@ScenarioInst@Diagnostics@Microsoft@@QEBA?AV?$shared_ptr@$$CBVIScenarioDef@Diagnostics@Microsoft@@@std@@XZ; Microsoft::Diagnostics::ScenarioInst::GetScenarioDef(void)
0x1800b37a9  nop
0x1800b37aa  mov     rcx, [rax]
0x1800b37ad  mov     rax, [rcx]
0x1800b37b0  mov     rax, [rax+48h]
0x1800b37b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b37b9  movdqu  [rsp+3A8h+var_348], xmm6
0x1800b37bf  lea     r8, [rsp+3A8h+var_348]
0x1800b37c4  mov     rdx, rax
0x1800b37c7  call    ?SetProcessNameForSnapshotScenarios@ScenarioCounterStorage@Diagnostics@Microsoft@@QEAAXAEBU_GUID@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::ScenarioCounterStorage::SetProcessNameForSnapshotScenarios(_GUID const &,std::wstring_view)
0x1800b37cc  nop
0x1800b37cd  mov     rcx, [rsp+3A8h+var_338+8]; this
0x1800b37d2  xor     r15d, r15d
0x1800b37d5  test    rcx, rcx
0x1800b37d8  jz      short loc_1800B37DF
0x1800b37da  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b37df  mov     dword ptr [rsp+3A8h+var_B8], r15d
0x1800b37e7  lea     rdx, [rsp+3A8h+var_90]
0x1800b37ef  lea     rcx, [rsp+3A8h+var_B8+8]
0x1800b37f7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b37fc  nop
0x1800b37fd  mov     rdx, qword ptr [rsp+3A8h+var_368+8]
0x1800b3802  cmp     rdx, [rsp+3A8h+var_358]
0x1800b3807  jz      short loc_1800B3868
0x1800b3809  mov     eax, dword ptr [rsp+3A8h+var_B8]
0x1800b3810  mov     [rdx], eax
0x1800b3812  mov     rax, qword ptr [rsp+3A8h+var_B8+8]
0x1800b381a  mov     [rdx+8], rax
0x1800b381e  mov     rax, [rsp+3A8h+var_A8]
0x1800b3826  mov     [rdx+10h], rax
0x1800b382a  mov     rax, qword ptr [rsp+3A8h+var_A0]
0x1800b3832  mov     [rdx+18h], rax
0x1800b3836  mov     rax, qword ptr [rsp+3A8h+var_A0+8]
0x1800b383e  mov     [rdx+20h], rax
0x1800b3842  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800b384a  movdqu  [rsp+3A8h+var_A0], xmm6
0x1800b3853  mov     word ptr [rsp+3A8h+var_B8+8], r15w
0x1800b385c  mov     [rdx+28h], r13
0x1800b3860  add     qword ptr [rsp+3A8h+var_368+8], 30h ; '0'
0x1800b3866  jmp     short loc_1800B388A
0x1800b3868  lea     r9, [rsp+3A8h+var_318]
0x1800b3870  lea     r8, [rsp+3A8h+var_B8]
0x1800b3878  lea     rcx, [rsp+3A8h+var_368]
0x1800b387d  call    ??$_Emplace_reallocate@U?$pair@HV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEA_K@?$vector@U?$pair@U?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@std@@V?$allocator@U?$pair@U?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@std@@@2@@std@@AEAAPEAU?$pair@U?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@1@QEAU21@$$QEAU?$pair@HV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@AEA_K@Z; std::vector<std::pair<std::pair<ulong,std::wstring>,unsigned __int64>>::_Emplace_reallocate<std::pair<int,std::wstring>,unsigned __int64 &>(std::pair<std::pair<ulong,std::wstring>,unsigned __int64> * const,std::pair<int,std::wstring> &&,unsigned __int64 &)
0x1800b3882  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800b388a  mov     esi, 1
0x1800b388f  lea     rcx, [rsp+3A8h+var_B8+8]; this
0x1800b3897  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800b389c  lea     rcx, [rdi+0A8h]; Src
0x1800b38a3  lea     rdx, aSuccessfullySt_1; "Successfully started snapshot, processN"...
0x1800b38aa  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1800b38af  mov     r8, rax
0x1800b38b2  lea     rdx, [rsp+3A8h+var_348]
0x1800b38b7  lea     rcx, [rsp+3A8h+var_90]
0x1800b38bf  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800b38c4  movups  xmm0, xmmword ptr [rax]
0x1800b38c7  movdqu  xmmword ptr [rsp+3A8h+var_338], xmm0
0x1800b38cd  lea     rdx, [rsp+3A8h+var_338]
0x1800b38d2  mov     rcx, r8; Src
0x1800b38d5  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1800b38da  lea     rdx, asc_180375918; ".\r\n"
0x1800b38e1  mov     rcx, rax; Src
0x1800b38e4  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1800b38e9  jmp     short loc_1800B392F
0x1800b38eb  lea     rcx, [rdi+0A8h]; Src
0x1800b38f2  lea     rdx, aSkippingProces_0; "Skipping process snapshot of "
0x1800b38f9  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1800b38fe  movups  xmm0, xmmword ptr [r14]
0x1800b3902  movdqu  xmmword ptr [rsp+3A8h+var_338], xmm0
0x1800b3908  lea     rdx, [rsp+3A8h+var_338]
0x1800b390d  mov     rcx, rax; Src
0x1800b3910  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1800b3915  lea     rdx, aDueToCap; " due to cap.\r\n"
0x1800b391c  mov     rcx, rax; Src
0x1800b391f  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1800b3924  xor     r15d, r15d
0x1800b3927  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800b392f  test    r12b, r12b
0x1800b3932  jz      loc_1800B40B0
0x1800b3938  mov     al, [rdi+12h]
0x1800b393b  cmp     [rdi+13h], al
0x1800b393e  jnb     loc_1800B4077
0x1800b3944  xor     edx, edx; th32ProcessID
0x1800b3946  lea     ecx, [rdx+2]; dwFlags
0x1800b3949  call    cs:__imp_CreateToolhelp32Snapshot
0x1800b3950  nop     dword ptr [rax+rax+00h]
0x1800b3955  mov     rbx, rax
0x1800b3958  mov     qword ptr [rsp+3A8h+var_348], rax
0x1800b395d  dec     rax
0x1800b3960  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800b3964  ja      loc_1800B3FEF
0x1800b396a  xor     edx, edx; Val
0x1800b396c  mov     r8d, 234h; Size
0x1800b3972  lea     rcx, [rsp+3A8h+pe.cntUsage]; void *
0x1800b397a  call    memset_0
0x1800b397f  mov     [rsp+3A8h+pe.dwSize], 238h
0x1800b398a  lea     rdx, [rsp+3A8h+pe]; lppe
0x1800b3992  mov     rcx, rbx; hSnapshot
0x1800b3995  call    cs:__imp_Process32FirstW
0x1800b399c  nop     dword ptr [rax+rax+00h]
0x1800b39a1  test    eax, eax
0x1800b39a3  jnz     loc_1800B3A33
0x1800b39a9  mov     rcx, [rsp+3A8h]; this
0x1800b39b1  lea     r8, aOnecoreBaseTel_206; "onecore\\base\\telemetry\\utc\\service"...
0x1800b39b8  mov     edx, 0A6h; void *
0x1800b39bd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b39c2  mov     edi, eax
0x1800b39c4  lea     rcx, [rsp+3A8h+var_348]
0x1800b39c9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@$$A6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&CloseHandle(void *)>>(void)
0x1800b39ce  nop
0x1800b39cf  mov     rcx, qword ptr [rsp+3A8h+var_368]
0x1800b39d4  test    rcx, rcx
0x1800b39d7  jz      short loc_1800B3A1F
0x1800b39d9  mov     rdx, qword ptr [rsp+3A8h+var_368+8]
0x1800b39de  call    ??$_Destroy_range@V?$allocator@U?$pair@U?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@std@@@std@@@std@@YAXPEAU?$pair@U?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@0@QEAU10@AEAV?$allocator@U?$pair@U?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@std@@@0@@Z; std::_Destroy_range<std::allocator<std::pair<std::pair<ulong,std::wstring>,unsigned __int64>>>(std::pair<std::pair<ulong,std::wstring>,unsigned __int64> *,std::pair<std::pair<ulong,std::wstring>,unsigned __int64> * const,std::allocator<std::pair<std::pair<ulong,std::wstring>,unsigned __int64>> &)
0x1800b39e3  mov     rcx, [rsp+3A8h+var_358]
0x1800b39e8  sub     rcx, qword ptr [rsp+3A8h+var_368]
0x1800b39ed  sar     rcx, 4
0x1800b39f1  mov     rbx, 0AAAAAAAAAAAAAAABh
0x1800b39fb  imul    rcx, rbx
0x1800b39ff  lea     rdx, [rcx+rcx*2]
0x1800b3a03  shl     rdx, 4
0x1800b3a07  mov     rcx, qword ptr [rsp+3A8h+var_368]
0x1800b3a0c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800b3a11  xorps   xmm0, xmm0
0x1800b3a14  movdqu  [rsp+3A8h+var_368], xmm0
0x1800b3a1a  mov     [rsp+3A8h+var_358], r15
0x1800b3a1f  lea     rcx, [rsp+3A8h+var_90]; this
0x1800b3a27  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800b3a2c  mov     eax, edi
0x1800b3a2e  jmp     loc_1800B4127
0x1800b3a33  xorps   xmm0, xmm0
0x1800b3a36  movdqu  [rsp+3A8h+var_B8], xmm0
0x1800b3a3f  mov     [rsp+3A8h+var_A8], r15
0x1800b3a47  lea     rcx, [rsp+3A8h+pe.szExeFile]
0x1800b3a4f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b3a53  inc     rax
0x1800b3a56  cmp     [rcx+rax*2], r15w
0x1800b3a5b  jnz     short loc_1800B3A53
0x1800b3a5d  lea     rcx, [rsp+3A8h+pe.szExeFile]
0x1800b3a65  mov     qword ptr [rsp+3A8h+var_328], rcx
0x1800b3a6d  mov     qword ptr [rsp+3A8h+var_328+8], rax
0x1800b3a75  movups  xmm0, xmmword ptr [r14]
0x1800b3a79  movdqu  xmmword ptr [rsp+3A8h+var_338], xmm0
0x1800b3a7f  lea     rdx, [rsp+3A8h+var_328]
0x1800b3a87  lea     rcx, [rsp+3A8h+var_338]
0x1800b3a8c  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1800b3a91  test    eax, eax
0x1800b3a93  jnz     loc_1800B3BA1
0x1800b3a99  mov     al, [rdi+12h]
0x1800b3a9c  cmp     [rdi+13h], al
0x1800b3a9f  jnb     loc_1800B3F9E
0x1800b3aa5  mov     rdx, qword ptr [rsp+3A8h+var_B8+8]
0x1800b3aad  cmp     rdx, [rsp+3A8h+var_A8]
0x1800b3ab5  jz      short loc_1800B3ACB
0x1800b3ab7  mov     eax, [rsp+3A8h+pe.th32ProcessID]
0x1800b3abe  mov     [rdx], eax
0x1800b3ac0  add     qword ptr [rsp+3A8h+var_B8+8], 4
0x1800b3ac9  jmp     short loc_1800B3AE0
0x1800b3acb  lea     r8, [rsp+3A8h+pe.th32ProcessID]
0x1800b3ad3  lea     rcx, [rsp+3A8h+var_B8]
0x1800b3adb  call    ??$_Emplace_reallocate@AEBW4_TDH_IN_TYPE@@@?$vector@W4_TDH_IN_TYPE@@V?$allocator@W4_TDH_IN_TYPE@@@std@@@std@@AEAAPEAW4_TDH_IN_TYPE@@QEAW42@AEBW42@@Z; std::vector<_TDH_IN_TYPE>::_Emplace_reallocate<_TDH_IN_TYPE const &>(_TDH_IN_TYPE * const,_TDH_IN_TYPE const &)
0x1800b3ae0  mov     eax, [rsp+3A8h+pe.th32ProcessID]
0x1800b3ae7  mov     [rsp+3A8h+var_70], eax
0x1800b3aee  lea     rdx, [rsp+3A8h+var_90]
0x1800b3af6  lea     rcx, [rsp+3A8h+var_68]
0x1800b3afe  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b3b03  nop
0x1800b3b04  mov     rdx, qword ptr [rsp+3A8h+var_368+8]
0x1800b3b09  cmp     rdx, [rsp+3A8h+var_358]
0x1800b3b0e  jz      short loc_1800B3B67
0x1800b3b10  mov     eax, [rsp+3A8h+var_70]
0x1800b3b17  mov     [rdx], eax
0x1800b3b19  mov     rax, [rsp+3A8h+var_68]
0x1800b3b21  mov     [rdx+8], rax
0x1800b3b25  mov     rax, [rsp+3A8h+var_60]
  ... truncated ...
```
