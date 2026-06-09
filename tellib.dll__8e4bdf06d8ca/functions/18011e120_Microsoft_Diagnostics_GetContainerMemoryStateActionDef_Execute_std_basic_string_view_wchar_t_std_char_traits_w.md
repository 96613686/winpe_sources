# Microsoft::Diagnostics::GetContainerMemoryStateActionDef::Execute(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,Microsoft::Diagnostics::EscalationWorkItemState &,Microsoft::Diagnostics::ScenarioInst const &)

- ea: `0x18011e120`
- end: `0x18011e6e9`
- name: `?Execute@GetContainerMemoryStateActionDef@Diagnostics@Microsoft@@UEBAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAVEscalationWorkItemState@23@AEBVScenarioInst@23@@Z`
- size: `1481`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001d160`
- `0x180020fbc`
- `0x180024ee0`
- `0x180026ecc`
- `0x180027be0`
- `0x180034d94`
- `0x1800558c0`
- `0x1800571c8`
- `0x180086f40`
- `0x180089d50`
- `0x18008bd1c`
- `0x1800a9f90`
- `0x1800aac70`
- `0x1800b0628`
- `0x180111a68`
- `0x18011e120`
- `0x18011e814`
- `0x18012de40`
- `0x1801c92c8`
- `0x180233734`
- `0x18030ba7c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18011e55b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18011e55b`
- `api-ms-win-containers-cmclient-l1-5-0!CmsOpenContainer` at `0x18011e3e8`
- `api-ms-win-containers-cmclient-l1-5-0!CmsOpenContainer` at `0x18011e3e8`
- `api-ms-win-containers-cmdiagclient-l1-1-1!CmsDiagCollectContainerMemoryState` at `0x18011e582`
- `api-ms-win-containers-cmdiagclient-l1-1-1!CmsDiagCollectContainerMemoryState` at `0x18011e582`

## string_xrefs

- `0x18011e1ea`: `onecore\base\telemetry\utc\service\scenarios\actions\getcontainermemorystateaction.cpp`
- `0x18011e2bf`: `onecore\base\telemetry\utc\service\scenarios\actions\getcontainermemorystateaction.cpp`
- `0x18011e30f`: `onecore\base\telemetry\utc\service\scenarios\actions\getcontainermemorystateaction.cpp`
- `0x18011e398`: `onecore\base\telemetry\utc\service\scenarios\actions\getcontainermemorystateaction.cpp`
- `0x18011e405`: `onecore\base\telemetry\utc\service\scenarios\actions\getcontainermemorystateaction.cpp`
- `0x18011e4c4`: `onecore\base\telemetry\utc\service\scenarios\actions\getcontainermemorystateaction.cpp`
- `0x18011e59f`: `onecore\base\telemetry\utc\service\scenarios\actions\getcontainermemorystateaction.cpp`
- `0x18011e643`: `onecore\base\telemetry\utc\service\scenarios\actions\getcontainermemorystateaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::GetContainerMemoryStateActionDef::Execute(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v9; // rbx
  __int64 v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rsi
  __int64 v13; // rbx
  int v14; // eax
  unsigned int v15; // edi
  int v16; // eax
  unsigned int v17; // edi
  int appended; // eax
  unsigned int v19; // edi
  const WCHAR *v20; // rcx
  char *FileW; // rax
  const char *v22; // r9
  int v23; // eax
  unsigned int v24; // edi
  unsigned int LastError; // ebx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-118h]
  _QWORD v27[2]; // [rsp+40h] [rbp-F8h] BYREF
  __int128 v28; // [rsp+50h] [rbp-E8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-D8h] BYREF
  __int64 v30; // [rsp+68h] [rbp-D0h]
  _QWORD v31[3]; // [rsp+78h] [rbp-C0h] BYREF
  _BYTE v32[16]; // [rsp+90h] [rbp-A8h] BYREF
  GUID v33; // [rsp+A0h] [rbp-98h] BYREF
  _BYTE v34[32]; // [rsp+B0h] [rbp-88h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+D0h] [rbp-68h] BYREF
  _BYTE Src[32]; // [rsp+F0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(&v29);
  std::wstring::wstring(v34);
  v33 = *(GUID *)std::wstring::operator std::wstring_view(a1 + 128, &v28);
  if ( (int)Microsoft::Diagnostics::AgentManager::ConvertAgentIdStringToTelemetryIdString(&v33, v34) < 0 )
  {
    v33 = *(GUID *)std::wstring::operator std::wstring_view(a1 + 128, &v28);
    if ( (int)Microsoft::Diagnostics::EscalationWorkItem::GetMatchingAgentIds(&v33, &v29, a4) < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getcontainermemorystateaction.cpp",
        (const char *)0x87C51036LL,
        dwCreationDisposition);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v34);
      std::vector<std::wstring>::_Tidy(&v29);
      return 2277838902LL;
    }
  }
  else
  {
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(v31);
    v33 = *(GUID *)std::wstring::operator std::wstring_view(v34, &v28);
    v6 = Microsoft::Diagnostics::Utils::Container::EnumerateContainers(&v33, v31);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getcontainermemorystateaction.cpp",
        (const char *)(unsigned int)v6,
        dwCreationDisposition);
      std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::_Tidy(v31);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v34);
      std::vector<std::wstring>::_Tidy(&v29);
      return v7;
    }
    v9 = v31[0];
    v10 = v31[1];
    while ( v9 != v10 )
    {
      v11 = Microsoft::Diagnostics::Utils::String::StringFromGuidW(Src, v9, 0);
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&v29, v11);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      v9 += 16;
    }
    std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::_Tidy(v31);
  }
  v12 = v30;
  v13 = v29;
  if ( v29 == v30 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getcontainermemorystateaction.cpp",
      (const char *)0x80070490LL,
      dwCreationDisposition);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v34);
    std::vector<std::wstring>::_Tidy(&v29);
    return 2147943568LL;
  }
  else
  {
    do
    {
      v33 = GUID_NULL;
      v28 = *(_OWORD *)std::wstring::operator std::wstring_view(v13, v32);
      v14 = Microsoft::Diagnostics::Utils::String::GUIDFromString(&v28, &v33, 0);
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x42,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getcontainermemorystateaction.cpp",
          (const char *)(unsigned int)v14,
          dwCreationDisposition);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v34);
        std::vector<std::wstring>::_Tidy(&v29);
        return v15;
      }
      v27[0] = 0;
      v16 = CmsOpenContainer(&v33, 8, 2, v27);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x48,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getcontainermemorystateaction.cpp",
          (const char *)(unsigned int)v16,
          dwCreationDisposition);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v27);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v34);
        std::vector<std::wstring>::_Tidy(&v29);
        return v17;
      }
      v28 = *(_OWORD *)&Microsoft::Diagnostics::GetContainerMemoryStateActionDef::k_containerMemoryStateFileExtension;
      Microsoft::Diagnostics::operator+(Src);
      std::wstring::wstring(lpFileName);
      std::wstring::_Append<wchar_t>(lpFileName);
      v28 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v31);
      appended = Microsoft::Diagnostics::Utils::String::AppendPath((PWSTR)lpFileName);
      v19 = appended;
      if ( appended < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4E,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getcontainermemorystateaction.cpp",
          (const char *)(unsigned int)appended,
          dwCreationDisposition);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v27);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v34);
        std::vector<std::wstring>::_Tidy(&v29);
        return v19;
      }
      v20 = (const WCHAR *)lpFileName;
      if ( lpFileName[3] > (LPCWSTR)7 )
        v20 = lpFileName[0];
      FileW = (char *)CreateFileW(v20, 0xC0000000, 7u, 0, 1u, 0x80u, 0);
      *(_QWORD *)&v28 = FileW;
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x5E,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getcontainermemorystateaction.cpp",
                      v22);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v27);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v34);
        std::vector<std::wstring>::_Tidy(&v29);
        return LastError;
      }
      v23 = CmsDiagCollectContainerMemoryState(v27[0], FileW);
      v24 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x60,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getcontainermemorystateaction.cpp",
          (const char *)(unsigned int)v23,
          dwCreationDisposition);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v27);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v34);
        std::vector<std::wstring>::_Tidy(&v29);
        return v24;
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v27);
      v13 += 32;
    }
    while ( v13 != v12 );
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v34);
    std::vector<std::wstring>::_Tidy(&v29);
    return 0;
  }
}

```

## disassembly

```asm
0x18011e120  mov     [rsp+arg_10], rbx
0x18011e125  push    rsi
0x18011e126  push    rdi
0x18011e127  push    r14
0x18011e129  sub     rsp, 120h
0x18011e130  mov     rax, cs:__security_cookie
0x18011e137  xor     rax, rsp
0x18011e13a  mov     [rsp+138h+var_28], rax
0x18011e142  mov     rdi, r9
0x18011e145  mov     r14, rdx
0x18011e148  mov     rbx, rcx
0x18011e14b  lea     rcx, [rsp+138h+var_D8]; void *
0x18011e150  call    ??$?0AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>> const &)
0x18011e155  nop
0x18011e156  lea     rcx, [rsp+138h+var_88]; void *
0x18011e15e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18011e163  nop
0x18011e164  lea     rdx, [rsp+138h+var_E8]
0x18011e169  lea     rcx, [rbx+80h]
0x18011e170  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18011e175  movups  xmm0, xmmword ptr [rax]
0x18011e178  movdqu  [rsp+138h+var_98], xmm0
0x18011e181  lea     rdx, [rsp+138h+var_88]
0x18011e189  lea     rcx, [rsp+138h+var_98]
0x18011e191  call    ?ConvertAgentIdStringToTelemetryIdString@AgentManager@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::AgentManager::ConvertAgentIdStringToTelemetryIdString(std::wstring_view,std::wstring &)
0x18011e196  test    eax, eax
0x18011e198  js      loc_18011E279
0x18011e19e  lea     rcx, [rsp+138h+var_C0]; void *
0x18011e1a3  call    ??$?0AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>> const &)
0x18011e1a8  nop
0x18011e1a9  lea     rdx, [rsp+138h+var_E8]
0x18011e1ae  lea     rcx, [rsp+138h+var_88]
0x18011e1b6  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18011e1bb  movups  xmm0, xmmword ptr [rax]
0x18011e1be  movdqu  [rsp+138h+var_98], xmm0
0x18011e1c7  lea     rdx, [rsp+138h+var_C0]
0x18011e1cc  lea     rcx, [rsp+138h+var_98]
0x18011e1d4  call    ?EnumerateContainers@Container@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@6@@Z; Microsoft::Diagnostics::Utils::Container::EnumerateContainers(std::wstring_view,std::vector<_GUID> &)
0x18011e1d9  mov     ebx, eax
0x18011e1db  test    eax, eax
0x18011e1dd  jns     short loc_18011E226
0x18011e1df  mov     rcx, [rsp+138h]; this
0x18011e1e7  mov     r9d, eax; char *
0x18011e1ea  lea     r8, aOnecoreBaseTel_156; "onecore\\base\\telemetry\\utc\\service"...
0x18011e1f1  mov     edx, 2Ah ; '*'; void *
0x18011e1f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011e1fb  nop
0x18011e1fc  lea     rcx, [rsp+138h+var_C0]
0x18011e201  call    ?_Tidy@?$vector@UScenarioDbLookupPair@Diagnostics@Microsoft@@V?$allocator@UScenarioDbLookupPair@Diagnostics@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::_Tidy(void)
0x18011e206  nop
0x18011e207  lea     rcx, [rsp+138h+var_88]; this
0x18011e20f  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18011e214  nop
0x18011e215  lea     rcx, [rsp+138h+var_D8]
0x18011e21a  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18011e21f  mov     eax, ebx
0x18011e221  jmp     loc_18011E6C4
0x18011e226  mov     rbx, [rsp+138h+var_C0]
0x18011e22b  mov     rdi, [rsp+138h+var_B8]
0x18011e233  cmp     rbx, rdi
0x18011e236  jz      short loc_18011E26D
0x18011e238  xor     r8d, r8d
0x18011e23b  mov     rdx, rbx
0x18011e23e  lea     rcx, [rsp+138h+Src]
0x18011e246  call    ?StringFromGuidW@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; Microsoft::Diagnostics::Utils::String::StringFromGuidW(_GUID const &,bool)
0x18011e24b  nop
0x18011e24c  mov     rdx, rax
0x18011e24f  lea     rcx, [rsp+138h+var_D8]
0x18011e254  call    ??$_Emplace_one_at_back@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x18011e259  nop
0x18011e25a  lea     rcx, [rsp+138h+Src]; this
0x18011e262  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18011e267  add     rbx, 10h
0x18011e26b  jmp     short loc_18011E233
0x18011e26d  lea     rcx, [rsp+138h+var_C0]
0x18011e272  call    ?_Tidy@?$vector@UScenarioDbLookupPair@Diagnostics@Microsoft@@V?$allocator@UScenarioDbLookupPair@Diagnostics@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::_Tidy(void)
0x18011e277  jmp     short loc_18011E2F0
0x18011e279  lea     rdx, [rsp+138h+var_E8]
0x18011e27e  lea     rcx, [rbx+80h]
0x18011e285  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18011e28a  movups  xmm0, xmmword ptr [rax]
0x18011e28d  movdqu  [rsp+138h+var_98], xmm0
0x18011e296  mov     r8, rdi
0x18011e299  lea     rdx, [rsp+138h+var_D8]
0x18011e29e  lea     rcx, [rsp+138h+var_98]
0x18011e2a6  call    ?GetMatchingAgentIds@EscalationWorkItem@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@5@AEBVScenarioInst@23@@Z; Microsoft::Diagnostics::EscalationWorkItem::GetMatchingAgentIds(std::wstring_view,std::vector<std::wstring> &,Microsoft::Diagnostics::ScenarioInst const &)
0x18011e2ab  test    eax, eax
0x18011e2ad  jns     short loc_18011E2F0
0x18011e2af  mov     rcx, [rsp+138h]; this
0x18011e2b7  mov     ebx, 87C51036h
0x18011e2bc  mov     r9d, ebx; char *
0x18011e2bf  lea     r8, aOnecoreBaseTel_156; "onecore\\base\\telemetry\\utc\\service"...
0x18011e2c6  mov     edx, 35h ; '5'; void *
0x18011e2cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011e2d0  nop
0x18011e2d1  lea     rcx, [rsp+138h+var_88]; this
0x18011e2d9  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18011e2de  nop
0x18011e2df  lea     rcx, [rsp+138h+var_D8]
0x18011e2e4  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18011e2e9  mov     eax, ebx
0x18011e2eb  jmp     loc_18011E6C4
0x18011e2f0  mov     rsi, [rsp+138h+var_D0]
0x18011e2f5  mov     rbx, [rsp+138h+var_D8]
0x18011e2fa  cmp     rbx, rsi
0x18011e2fd  jnz     short loc_18011E349
0x18011e2ff  mov     rcx, [rsp+138h]; this
0x18011e307  mov     ebx, 80070490h
0x18011e30c  mov     r9d, ebx; char *
0x18011e30f  lea     r8, aOnecoreBaseTel_156; "onecore\\base\\telemetry\\utc\\service"...
0x18011e316  mov     edx, 3Ch ; '<'; void *
0x18011e31b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011e320  nop
0x18011e321  lea     rcx, [rsp+138h+var_88]; this
0x18011e329  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18011e32e  nop
0x18011e32f  lea     rcx, [rsp+138h+var_D8]
0x18011e334  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18011e339  mov     eax, ebx
0x18011e33b  jmp     loc_18011E6C4
0x18011e340  cmp     rbx, rsi
0x18011e343  jz      loc_18011E6A4
0x18011e349  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18011e350  movdqu  [rsp+138h+var_98], xmm0
0x18011e359  lea     rdx, [rsp+138h+var_A8]
0x18011e361  mov     rcx, rbx
0x18011e364  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18011e369  movups  xmm0, xmmword ptr [rax]
0x18011e36c  movdqu  [rsp+138h+var_E8], xmm0
0x18011e372  xor     r8d, r8d
0x18011e375  lea     rdx, [rsp+138h+var_98]
0x18011e37d  lea     rcx, [rsp+138h+var_E8]
0x18011e382  call    ?GUIDFromString@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAU_GUID@@_N@Z; Microsoft::Diagnostics::Utils::String::GUIDFromString(std::wstring_view,_GUID &,bool)
0x18011e387  mov     edi, eax
0x18011e389  test    eax, eax
0x18011e38b  jns     short loc_18011E3C9
0x18011e38d  mov     rcx, [rsp+138h]; this
0x18011e395  mov     r9d, eax; char *
0x18011e398  lea     r8, aOnecoreBaseTel_156; "onecore\\base\\telemetry\\utc\\service"...
0x18011e39f  mov     edx, 42h ; 'B'; void *
0x18011e3a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011e3a9  nop
0x18011e3aa  lea     rcx, [rsp+138h+var_88]; this
0x18011e3b2  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18011e3b7  nop
0x18011e3b8  lea     rcx, [rsp+138h+var_D8]
0x18011e3bd  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18011e3c2  mov     eax, edi
0x18011e3c4  jmp     loc_18011E6C4
0x18011e3c9  mov     [rsp+138h+var_F8], 0
0x18011e3d2  lea     r9, [rsp+138h+var_F8]
0x18011e3d7  mov     edx, 8
0x18011e3dc  lea     r8d, [rdx-6]
0x18011e3e0  lea     rcx, [rsp+138h+var_98]
0x18011e3e8  call    cs:__imp_CmsOpenContainer
0x18011e3ef  nop     dword ptr [rax+rax+00h]
0x18011e3f4  mov     edi, eax
0x18011e3f6  test    eax, eax
0x18011e3f8  jns     short loc_18011E441
0x18011e3fa  mov     rcx, [rsp+138h]; this
0x18011e402  mov     r9d, eax; char *
0x18011e405  lea     r8, aOnecoreBaseTel_156; "onecore\\base\\telemetry\\utc\\service"...
0x18011e40c  mov     edx, 48h ; 'H'; void *
0x18011e411  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011e416  nop
0x18011e417  lea     rcx, [rsp+138h+var_F8]
0x18011e41c  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?CloseCmsContainer@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18011e421  nop
0x18011e422  lea     rcx, [rsp+138h+var_88]; this
0x18011e42a  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18011e42f  nop
0x18011e430  lea     rcx, [rsp+138h+var_D8]
0x18011e435  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18011e43a  mov     eax, edi
0x18011e43c  jmp     loc_18011E6C4
0x18011e441  movups  xmm0, xmmword ptr cs:?k_containerMemoryStateFileExtension@GetContainerMemoryStateActionDef@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::GetContainerMemoryStateActionDef::k_containerMemoryStateFileExtension
0x18011e448  movdqu  [rsp+138h+var_E8], xmm0
0x18011e44e  lea     r8, [rsp+138h+var_E8]
0x18011e453  mov     rdx, rbx
0x18011e456  lea     rcx, [rsp+138h+Src]; Src
0x18011e45e  call    ??HDiagnostics@Microsoft@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; Microsoft::Diagnostics::operator+(std::wstring const &,std::wstring_view)
0x18011e463  nop
0x18011e464  lea     rcx, [rsp+138h+lpFileName]; void *
0x18011e46c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18011e471  nop
0x18011e472  mov     r8, [r14+8]
0x18011e476  mov     rdx, [r14]
0x18011e479  lea     rcx, [rsp+138h+lpFileName]; Src
0x18011e481  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18011e486  lea     rdx, [rsp+138h+var_C0]
0x18011e48b  lea     rcx, [rsp+138h+Src]
0x18011e493  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18011e498  movups  xmm0, xmmword ptr [rax]
0x18011e49b  movdqu  [rsp+138h+var_E8], xmm0
0x18011e4a1  lea     rdx, [rsp+138h+var_E8]
0x18011e4a6  lea     rcx, [rsp+138h+lpFileName]; pszPath
0x18011e4ae  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x18011e4b3  mov     edi, eax
0x18011e4b5  test    eax, eax
0x18011e4b7  jns     short loc_18011E51C
0x18011e4b9  mov     rcx, [rsp+138h]; this
0x18011e4c1  mov     r9d, eax; char *
0x18011e4c4  lea     r8, aOnecoreBaseTel_156; "onecore\\base\\telemetry\\utc\\service"...
0x18011e4cb  mov     edx, 4Eh ; 'N'; void *
0x18011e4d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011e4d5  nop
0x18011e4d6  lea     rcx, [rsp+138h+lpFileName]; this
0x18011e4de  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18011e4e3  nop
0x18011e4e4  lea     rcx, [rsp+138h+Src]; this
0x18011e4ec  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18011e4f1  nop
0x18011e4f2  lea     rcx, [rsp+138h+var_F8]
0x18011e4f7  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?CloseCmsContainer@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18011e4fc  nop
0x18011e4fd  lea     rcx, [rsp+138h+var_88]; this
0x18011e505  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18011e50a  nop
0x18011e50b  lea     rcx, [rsp+138h+var_D8]
0x18011e510  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18011e515  mov     eax, edi
0x18011e517  jmp     loc_18011E6C4
0x18011e51c  lea     rcx, [rsp+138h+lpFileName]
0x18011e524  cmp     [rsp+138h+var_50], 7
0x18011e52d  cmova   rcx, [rsp+138h+lpFileName]; lpFileName
0x18011e536  mov     [rsp+138h+hTemplateFile], 0; hTemplateFile
0x18011e53f  mov     [rsp+138h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18011e547  mov     [rsp+138h+dwCreationDisposition], 1; int
0x18011e54f  xor     r9d, r9d; lpSecurityAttributes
0x18011e552  mov     edx, 0C0000000h; dwDesiredAccess
0x18011e557  lea     r8d, [r9+7]; dwShareMode
0x18011e55b  call    cs:__imp_CreateFileW
0x18011e562  nop     dword ptr [rax+rax+00h]
0x18011e567  mov     qword ptr [rsp+138h+var_E8], rax
0x18011e56c  lea     rcx, [rax-1]
0x18011e570  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18011e574  ja      loc_18011E63B
0x18011e57a  mov     rdx, rax
0x18011e57d  mov     rcx, [rsp+138h+var_F8]
0x18011e582  call    cs:__imp_CmsDiagCollectContainerMemoryState
0x18011e589  nop     dword ptr [rax+rax+00h]
0x18011e58e  mov     edi, eax
0x18011e590  test    eax, eax
0x18011e592  jns     short loc_18011E601
0x18011e594  mov     rcx, [rsp+138h]; this
0x18011e59c  mov     r9d, eax; char *
0x18011e59f  lea     r8, aOnecoreBaseTel_156; "onecore\\base\\telemetry\\utc\\service"...
0x18011e5a6  mov     edx, 60h ; '`'; void *
0x18011e5ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011e5b0  lea     rcx, [rsp+138h+var_E8]
0x18011e5b5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18011e5ba  nop
0x18011e5bb  lea     rcx, [rsp+138h+lpFileName]; this
0x18011e5c3  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18011e5c8  nop
0x18011e5c9  lea     rcx, [rsp+138h+Src]; this
0x18011e5d1  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18011e5d6  nop
0x18011e5d7  lea     rcx, [rsp+138h+var_F8]
0x18011e5dc  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?CloseCmsContainer@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18011e5e1  nop
0x18011e5e2  lea     rcx, [rsp+138h+var_88]; this
0x18011e5ea  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18011e5ef  nop
0x18011e5f0  lea     rcx, [rsp+138h+var_D8]
0x18011e5f5  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18011e5fa  mov     eax, edi
0x18011e5fc  jmp     loc_18011E6C4
0x18011e601  lea     rcx, [rsp+138h+var_E8]
0x18011e606  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18011e60b  nop
0x18011e60c  lea     rcx, [rsp+138h+lpFileName]; this
0x18011e614  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18011e619  nop
0x18011e61a  lea     rcx, [rsp+138h+Src]; this
0x18011e622  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18011e627  nop
0x18011e628  lea     rcx, [rsp+138h+var_F8]
0x18011e62d  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?CloseCmsContainer@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18011e632  add     rbx, 20h ; ' '
0x18011e636  jmp     loc_18011E340
0x18011e63b  mov     rcx, [rsp+138h]; this
0x18011e643  lea     r8, aOnecoreBaseTel_156; "onecore\\base\\telemetry\\utc\\service"...
0x18011e64a  mov     edx, 5Eh ; '^'; void *
0x18011e64f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18011e654  mov     ebx, eax
0x18011e656  lea     rcx, [rsp+138h+var_E8]
0x18011e65b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18011e660  nop
0x18011e661  lea     rcx, [rsp+138h+lpFileName]; this
0x18011e669  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18011e66e  nop
0x18011e66f  lea     rcx, [rsp+138h+Src]; this
0x18011e677  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18011e67c  nop
0x18011e67d  lea     rcx, [rsp+138h+var_F8]
0x18011e682  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?CloseCmsContainer@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&wilp::CloseCmsContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18011e687  nop
0x18011e688  lea     rcx, [rsp+138h+var_88]; this
0x18011e690  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
  ... truncated ...
```
