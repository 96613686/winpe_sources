# Microsoft::Diagnostics::TraceSessionUsage::UpdateTraceSessionDetails(std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,Microsoft::Diagnostics::TraceSessionDetails,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,Microsoft::Diagnostics::TraceSessionDetails>>> &)

- ea: `0x1802df750`
- end: `0x1802dfd75`
- name: `?UpdateTraceSessionDetails@TraceSessionUsage@Diagnostics@Microsoft@@QEAAJAEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UTraceSessionDetails@Diagnostics@Microsoft@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UTraceSessionDetails@Diagnostics@Microsoft@@@std@@@2@@std@@@Z`
- size: `1573`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18025f8e0`
- `0x1802df1e8`

## callees

- `0x18001b60c`
- `0x18001d160`
- `0x180024ee0`
- `0x1800363b4`
- `0x18004ab70`
- `0x180053a84`
- `0x18007fae8`
- `0x18012de40`
- `0x1801bca00`
- `0x1801bcb18`
- `0x1801c7858`
- `0x1802df048`
- `0x1802df140`
- `0x1802df1b0`
- `0x1802df750`

## import_xrefs

- `api-ms-win-perf-legacy-l1-1-0!PerfQueryCounterSetRegistrationInfo` at `0x1802df822`
- `api-ms-win-perf-legacy-l1-1-0!PerfQueryCounterSetRegistrationInfo` at `0x1802df822`
- `api-ms-win-perf-legacy-l1-1-0!PerfQueryCounterData` at `0x1802dfb1f`
- `api-ms-win-perf-legacy-l1-1-0!PerfQueryCounterData` at `0x1802dfb1f`
- `api-ms-win-perf-legacy-l1-1-0!PerfAddCounters` at `0x1802dfaab`
- `api-ms-win-perf-legacy-l1-1-0!PerfAddCounters` at `0x1802dfaab`
- `api-ms-win-perf-legacy-l1-1-0!PerfOpenQueryHandle` at `0x1802df78e`
- `api-ms-win-perf-legacy-l1-1-0!PerfOpenQueryHandle` at `0x1802df78e`

## string_xrefs

- `0x1802df7a9`: `onecore\base\telemetry\utc\service\analysis\tracesessionusage.cpp`
- `0x1802df859`: `onecore\base\telemetry\utc\service\analysis\tracesessionusage.cpp`
- `0x1802dfac6`: `onecore\base\telemetry\utc\service\analysis\tracesessionusage.cpp`
- `0x1802dfb56`: `onecore\base\telemetry\utc\service\analysis\tracesessionusage.cpp`
- `0x1802dfba6`: `onecore\base\telemetry\utc\service\analysis\tracesessionusage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::TraceSessionUsage::UpdateTraceSessionDetails(__int64 a1, __int64 a2)
{
  ULONG v3; // eax
  unsigned int v4; // ebx
  int i; // ebx
  ULONG v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  LPBYTE v10; // r14
  int j; // esi
  BYTE *v12; // rdi
  BYTE *v13; // rbx
  __int64 v14; // rax
  _BYTE *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  ULONG v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rdx
  int k; // ebx
  ULONG v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // rdx
  LPBYTE v26; // rbx
  const char *v27; // r9
  unsigned int v28; // ebx
  __int64 v29; // rdx
  __int64 v30; // r15
  BYTE *v31; // rdi
  int m; // r14d
  int v33; // r11d
  DWORD v34; // esi
  __int64 v35; // r10
  int v36; // r11d
  __int64 v37; // rdx
  __int64 v38; // rax
  __int64 v39; // rdx
  unsigned int pbRegInfo; // [rsp+20h] [rbp-178h]
  unsigned int pbRegInfoa; // [rsp+20h] [rbp-178h]
  _BYTE v42[4]; // [rsp+40h] [rbp-158h] BYREF
  DWORD pcbCounterBlockActual; // [rsp+44h] [rbp-154h] BYREF
  HANDLE phQuery; // [rsp+48h] [rbp-150h] BYREF
  __int128 v45; // [rsp+50h] [rbp-148h] BYREF
  LPBYTE v46; // [rsp+60h] [rbp-138h] BYREF
  int v47; // [rsp+68h] [rbp-130h]
  __int128 v48; // [rsp+80h] [rbp-118h] BYREF
  _QWORD v49[2]; // [rsp+90h] [rbp-108h] BYREF
  _QWORD v50[2]; // [rsp+A0h] [rbp-F8h] BYREF
  _QWORD v51[2]; // [rsp+B0h] [rbp-E8h] BYREF
  _QWORD v52[2]; // [rsp+C0h] [rbp-D8h] BYREF
  _QWORD v53[4]; // [rsp+D0h] [rbp-C8h] BYREF
  _BYTE v54[16]; // [rsp+F0h] [rbp-A8h] BYREF
  __int64 v55; // [rsp+100h] [rbp-98h]
  _BYTE v56[16]; // [rsp+108h] [rbp-90h] BYREF
  _PERF_COUNTER_IDENTIFIER pCounters; // [rsp+118h] [rbp-80h] BYREF
  __int64 v58; // [rsp+140h] [rbp-58h]
  _BYTE v59[32]; // [rsp+148h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  phQuery = 0;
  v3 = PerfOpenQueryHandle(0, &phQuery);
  if ( v3 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x5F,
           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\tracesessionusage.cpp",
           (const char *)v3,
           pbRegInfo);
    wil::details::unique_storage<wil::details::resource_policy<void *,unsigned long (void *),&unsigned long PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,unsigned long (void *),&unsigned long PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phQuery);
    return v4;
  }
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(&v46);
  std::vector<unsigned char>::_Resize<std::_Value_init_tag>(&v46, 400);
  for ( i = 0; ; i = 1 )
  {
    pcbCounterBlockActual = 0;
    v7 = PerfQueryCounterSetRegistrationInfo(
           0,
           &Microsoft::Diagnostics::TraceSessionUsage::k_EventTracingSessionCounterSetGuid,
           PERF_REG_COUNTER_NAME_STRINGS,
           0,
           v46,
           v47 - (_DWORD)v46,
           &pcbCounterBlockActual);
    if ( v7 != 8 )
      break;
    if ( i )
      goto LABEL_8;
    std::vector<unsigned char>::_Resize<std::_Value_init_tag>(&v46, pcbCounterBlockActual);
  }
  if ( v7 )
  {
LABEL_8:
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x7F,
           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\tracesessionusage.cpp",
           (const char *)v7,
           pbRegInfoa);
    std::vector<unsigned char>::_Tidy(&v46, v9);
    wil::details::unique_storage<wil::details::resource_policy<void *,unsigned long (void *),&unsigned long PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,unsigned long (void *),&unsigned long PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phQuery);
    return v8;
  }
  v10 = v46;
  v45 = 0;
  std::_Tree<std::_Tmap_traits<enum OneSettingsDownloadConfigBoolProperty,std::optional<bool>,std::less<enum OneSettingsDownloadConfigBoolProperty>,std::allocator<std::pair<enum OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>,0>>::_Alloc_sentinel_and_proxy(&v45);
  for ( j = 0; j != *((_DWORD *)v10 + 1); ++j )
  {
    v12 = &v10[8 * j + 8];
    if ( (v12[4] & 1) == 0 && *((_DWORD *)v12 + 1) != -1 )
    {
      v13 = &v10[*((unsigned int *)v12 + 1)];
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)&v13[2 * v14] );
      v48 = *(_OWORD *)&Microsoft::Diagnostics::TraceSessionUsage::k_perfCounterName_BufferMemoryUsagePaged;
      v49[0] = v13;
      v49[1] = v14;
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v49, &v48) )
      {
        v42[0] = 0;
        v15 = v59;
LABEL_25:
        std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::Diagnostics::PerfCounterEnum,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::Diagnostics::PerfCounterEnum>>,0>>::emplace<unsigned long const &,enum Microsoft::Diagnostics::PerfCounterEnum::_enumerated>(
          &v45,
          v15,
          &v10[8 * j + 8],
          v42);
        continue;
      }
      v16 = -1;
      do
        ++v16;
      while ( *(_WORD *)&v13[2 * v16] );
      v48 = *(_OWORD *)&Microsoft::Diagnostics::TraceSessionUsage::k_perfCounterName_BufferMemoryUsageNonpaged;
      v50[0] = v13;
      v50[1] = v16;
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v50, &v48) )
      {
        v42[0] = 1;
        v15 = v53;
        goto LABEL_25;
      }
      v17 = -1;
      do
        ++v17;
      while ( *(_WORD *)&v13[2 * v17] );
      v48 = *(_OWORD *)&Microsoft::Diagnostics::TraceSessionUsage::k_perfCounterName_EventsLogged;
      v51[0] = v13;
      v51[1] = v17;
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v51, &v48) )
      {
        v42[0] = 2;
        v15 = v54;
        goto LABEL_25;
      }
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)&v13[2 * v18] );
      v48 = *(_OWORD *)&Microsoft::Diagnostics::TraceSessionUsage::k_perfCounterName_EventsLost;
      v52[0] = v13;
      v52[1] = v18;
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v52, &v48) )
      {
        v42[0] = 3;
        std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::Diagnostics::PerfCounterEnum,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::Diagnostics::PerfCounterEnum>>,0>>::emplace<unsigned long const &,enum Microsoft::Diagnostics::PerfCounterEnum::_enumerated>(
          &v45,
          v56,
          &v10[8 * j + 8],
          v42);
      }
    }
  }
  pCounters.CounterSetGuid = Microsoft::Diagnostics::TraceSessionUsage::k_EventTracingSessionCounterSetGuid;
  pCounters.Status = 0;
  pCounters.Size = 48;
  *(_QWORD *)&pCounters.CounterId = -1;
  *(_QWORD *)&pCounters.Index = 0;
  v58 = 42;
  v19 = PerfAddCounters(phQuery, &pCounters, 0x30u);
  if ( v19 )
  {
    v20 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xC3,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\tracesessionusage.cpp",
            (const char *)v19,
            pbRegInfoa);
    std::_Tree<std::_Tmap_traits<enum OneSettingsDownloadConfigBoolProperty,std::optional<bool>,std::less<enum OneSettingsDownloadConfigBoolProperty>,std::allocator<std::pair<enum OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>,0>>::~_Tree<std::_Tmap_traits<enum OneSettingsDownloadConfigBoolProperty,std::optional<bool>,std::less<enum OneSettingsDownloadConfigBoolProperty>,std::allocator<std::pair<enum OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>,0>>(&v45);
    std::vector<unsigned char>::_Tidy(&v46, v21);
    wil::details::unique_storage<wil::details::resource_policy<void *,unsigned long (void *),&unsigned long PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,unsigned long (void *),&unsigned long PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phQuery);
    return v20;
  }
  else
  {
    for ( k = 0; ; k = 1 )
    {
      pcbCounterBlockActual = 0;
      v23 = PerfQueryCounterData(phQuery, (PPERF_DATA_HEADER)v46, v47 - (_DWORD)v46, &pcbCounterBlockActual);
      if ( v23 != 8 )
        break;
      if ( k )
        goto LABEL_38;
      std::vector<unsigned char>::_Resize<std::_Value_init_tag>(&v46, pcbCounterBlockActual);
    }
    if ( v23 )
    {
LABEL_38:
      v24 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xD0,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\tracesessionusage.cpp",
              (const char *)v23,
              pbRegInfoa);
      std::_Tree<std::_Tmap_traits<enum OneSettingsDownloadConfigBoolProperty,std::optional<bool>,std::less<enum OneSettingsDownloadConfigBoolProperty>,std::allocator<std::pair<enum OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>,0>>::~_Tree<std::_Tmap_traits<enum OneSettingsDownloadConfigBoolProperty,std::optional<bool>,std::less<enum OneSettingsDownloadConfigBoolProperty>,std::allocator<std::pair<enum OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>,0>>(&v45);
      std::vector<unsigned char>::_Tidy(&v46, v25);
      wil::details::unique_storage<wil::details::resource_policy<void *,unsigned long (void *),&unsigned long PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,unsigned long (void *),&unsigned long PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phQuery);
      return v24;
    }
    v26 = v46;
    v27 = (const char *)*((unsigned int *)v46 + 12);
    if ( (_DWORD)v27 )
    {
      v28 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xE5,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\tracesessionusage.cpp",
              v27,
              pbRegInfoa);
      std::_Tree<std::_Tmap_traits<enum OneSettingsDownloadConfigBoolProperty,std::optional<bool>,std::less<enum OneSettingsDownloadConfigBoolProperty>,std::allocator<std::pair<enum OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>,0>>::~_Tree<std::_Tmap_traits<enum OneSettingsDownloadConfigBoolProperty,std::optional<bool>,std::less<enum OneSettingsDownloadConfigBoolProperty>,std::allocator<std::pair<enum OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>,0>>(&v45);
      std::vector<unsigned char>::_Tidy(&v46, v29);
      wil::details::unique_storage<wil::details::resource_policy<void *,unsigned long (void *),&unsigned long PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,unsigned long (void *),&unsigned long PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phQuery);
      return v28;
    }
    else
    {
      if ( *((_DWORD *)v46 + 1) == 1 && *((_DWORD *)v46 + 13) == 6 )
      {
        v30 = *((unsigned int *)v46 + 16);
        v31 = &v46[v30 + 72];
        for ( m = 0; m != *(_DWORD *)&v26[v30 + 68]; ++m )
        {
          std::wstring::wstring(v59);
          v31 += *(unsigned int *)v31;
          v33 = 0;
          if ( *((_DWORD *)v26 + 17) )
          {
            do
            {
              v34 = *(_DWORD *)&v26[4 * v33 + 72];
              pcbCounterBlockActual = v34;
              v31 += *((unsigned int *)v31 + 1);
              std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::_Find_lower_bound<unsigned long>(
                &v45,
                v54,
                &pcbCounterBlockActual);
              v37 = v55;
              if ( *(_BYTE *)(v55 + 25) || v34 < *(_DWORD *)(v55 + 28) )
              {
                v38 = v45;
                v37 = v45;
              }
              else
              {
                v38 = v45;
              }
              if ( v37 != v38 )
              {
                if ( *(_BYTE *)(v37 + 32) )
                {
                  switch ( *(_BYTE *)(v37 + 32) )
                  {
                    case 1:
                      v53[1] = v35;
                      break;
                    case 2:
                      v53[2] = v35;
                      break;
                    case 3:
                      v53[3] = v35;
                      break;
                  }
                }
                else
                {
                  v53[0] = v35;
                }
              }
              v33 = v36 + 1;
            }
            while ( v33 != *((_DWORD *)v26 + 17) );
          }
          std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::Diagnostics::TraceSessionDetails,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::Diagnostics::TraceSessionDetails>>,0>>::_Emplace<std::wstring,Microsoft::Diagnostics::TraceSessionDetails>(
            a2,
            v56,
            v59,
            v53);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
        }
      }
      std::_Tree<std::_Tmap_traits<enum OneSettingsDownloadConfigBoolProperty,std::optional<bool>,std::less<enum OneSettingsDownloadConfigBoolProperty>,std::allocator<std::pair<enum OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>,0>>::~_Tree<std::_Tmap_traits<enum OneSettingsDownloadConfigBoolProperty,std::optional<bool>,std::less<enum OneSettingsDownloadConfigBoolProperty>,std::allocator<std::pair<enum OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>,0>>(&v45);
      std::vector<unsigned char>::_Tidy(&v46, v39);
      wil::details::unique_storage<wil::details::resource_policy<void *,unsigned long (void *),&unsigned long PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,unsigned long (void *),&unsigned long PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phQuery);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1802df750  mov     [rsp+arg_0], rbx
0x1802df755  mov     [rsp+arg_10], rsi
0x1802df75a  push    rdi
0x1802df75b  push    r12
0x1802df75d  push    r13
0x1802df75f  push    r14
0x1802df761  push    r15
0x1802df763  sub     rsp, 170h
0x1802df76a  mov     rax, cs:__security_cookie
0x1802df771  xor     rax, rsp
0x1802df774  mov     [rsp+198h+var_30], rax
0x1802df77c  mov     r12, rdx
0x1802df77f  xor     r13d, r13d
0x1802df782  mov     [rsp+198h+phQuery], r13
0x1802df787  lea     rdx, [rsp+198h+phQuery]; phQuery
0x1802df78c  xor     ecx, ecx; szMachine
0x1802df78e  call    cs:__imp_PerfOpenQueryHandle
0x1802df795  nop     dword ptr [rax+rax+00h]
0x1802df79a  test    eax, eax
0x1802df79c  jz      short loc_1802DF7CC
0x1802df79e  mov     rcx, [rsp+198h]; this
0x1802df7a6  mov     r9d, eax; char *
0x1802df7a9  lea     r8, aOnecoreBaseTel_89; "onecore\\base\\telemetry\\utc\\service"...
0x1802df7b0  lea     edx, [r13+5Fh]; void *
0x1802df7b4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1802df7b9  mov     ebx, eax
0x1802df7bb  lea     rcx, [rsp+198h+phQuery]
0x1802df7c0  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AKPEAX@Z$1?PerfCloseQueryHandle@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,ulong (void *),&PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,ulong (void *),&PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1802df7c5  mov     eax, ebx
0x1802df7c7  jmp     loc_1802DFD47
0x1802df7cc  lea     rcx, [rsp+198h+var_138]; void *
0x1802df7d1  call    ??$?0AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>> const &)
0x1802df7d6  nop
0x1802df7d7  mov     edx, 190h
0x1802df7dc  lea     rcx, [rsp+198h+var_138]
0x1802df7e1  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1802df7e6  mov     ebx, r13d
0x1802df7e9  mov     r15d, 1
0x1802df7ef  mov     [rsp+198h+pcbCounterBlockActual], r13d
0x1802df7f4  mov     rcx, [rsp+198h+var_138]
0x1802df7f9  mov     eax, [rsp+198h+var_130]
0x1802df7fd  sub     eax, ecx
0x1802df7ff  lea     rdx, [rsp+198h+pcbCounterBlockActual]
0x1802df804  mov     [rsp+198h+pcbRegInfoActual], rdx; pcbRegInfoActual
0x1802df809  mov     [rsp+198h+cbRegInfo], eax; cbRegInfo
0x1802df80d  mov     [rsp+198h+pbRegInfo], rcx; unsigned int
0x1802df812  xor     r9d, r9d; requestLangId
0x1802df815  lea     r8d, [r9+5]; requestCode
0x1802df819  lea     rdx, ?k_EventTracingSessionCounterSetGuid@TraceSessionUsage@Diagnostics@Microsoft@@0U_GUID@@B; pCounterSetId
0x1802df820  xor     ecx, ecx; szMachine
0x1802df822  call    cs:__imp_PerfQueryCounterSetRegistrationInfo
0x1802df829  nop     dword ptr [rax+rax+00h]
0x1802df82e  cmp     eax, 8
0x1802df831  jnz     short loc_1802DF84A
0x1802df833  test    ebx, ebx
0x1802df835  jnz     short loc_1802DF84E
0x1802df837  mov     edx, [rsp+198h+pcbCounterBlockActual]
0x1802df83b  lea     rcx, [rsp+198h+var_138]
0x1802df840  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1802df845  mov     ebx, r15d
0x1802df848  jmp     short loc_1802DF7EF
0x1802df84a  test    eax, eax
0x1802df84c  jz      short loc_1802DF888
0x1802df84e  mov     rcx, [rsp+198h]; this
0x1802df856  mov     r9d, eax; char *
0x1802df859  lea     r8, aOnecoreBaseTel_89; "onecore\\base\\telemetry\\utc\\service"...
0x1802df860  mov     edx, 7Fh; void *
0x1802df865  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1802df86a  mov     ebx, eax
0x1802df86c  lea     rcx, [rsp+198h+var_138]
0x1802df871  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1802df876  nop
0x1802df877  lea     rcx, [rsp+198h+phQuery]
0x1802df87c  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AKPEAX@Z$1?PerfCloseQueryHandle@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,ulong (void *),&PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,ulong (void *),&PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1802df881  mov     eax, ebx
0x1802df883  jmp     loc_1802DFD47
0x1802df888  mov     r14, [rsp+198h+var_138]
0x1802df88d  xorps   xmm0, xmm0
0x1802df890  movdqu  [rsp+198h+var_148], xmm0
0x1802df896  lea     rcx, [rsp+198h+var_148]
0x1802df89b  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@W4OneSettingsDownloadConfigBoolProperty@@V?$optional@_N@std@@U?$less@W4OneSettingsDownloadConfigBoolProperty@@@3@V?$allocator@U?$pair@$$CBW4OneSettingsDownloadConfigBoolProperty@@V?$optional@_N@std@@@std@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<OneSettingsDownloadConfigBoolProperty,std::optional<bool>,std::less<OneSettingsDownloadConfigBoolProperty>,std::allocator<std::pair<OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1802df8a0  nop
0x1802df8a1  mov     esi, r13d
0x1802df8a4  cmp     esi, [r14+4]
0x1802df8a8  jz      loc_1802DFA56
0x1802df8ae  mov     edi, esi
0x1802df8b0  inc     rdi
0x1802df8b3  lea     rdi, [r14+rdi*8]
0x1802df8b7  test    [rdi+4], r15b
0x1802df8bb  jnz     loc_1802DFA4E
0x1802df8c1  cmp     dword ptr [rdi+4], 0FFFFFFFFh
0x1802df8c5  jz      loc_1802DFA4E
0x1802df8cb  mov     ebx, [rdi+4]
0x1802df8ce  add     rbx, r14
0x1802df8d1  movups  xmm0, xmmword ptr cs:?k_perfCounterName_BufferMemoryUsagePaged@TraceSessionUsage@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::TraceSessionUsage::k_perfCounterName_BufferMemoryUsagePaged
0x1802df8d8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802df8dc  inc     rax
0x1802df8df  cmp     [rbx+rax*2], r13w
0x1802df8e4  jnz     short loc_1802DF8DC
0x1802df8e6  movdqu  [rsp+198h+var_118], xmm0
0x1802df8ef  mov     [rsp+198h+var_108], rbx
0x1802df8f7  mov     [rsp+198h+var_100], rax
0x1802df8ff  lea     rdx, [rsp+198h+var_118]
0x1802df907  lea     rcx, [rsp+198h+var_108]
0x1802df90f  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1802df914  test    eax, eax
0x1802df916  jnz     short loc_1802DF92A
0x1802df918  mov     [rsp+198h+var_158], r13b
0x1802df91d  lea     rdx, [rsp+198h+var_50]
0x1802df925  jmp     loc_1802DF9D4
0x1802df92a  movups  xmm0, xmmword ptr cs:?k_perfCounterName_BufferMemoryUsageNonpaged@TraceSessionUsage@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::TraceSessionUsage::k_perfCounterName_BufferMemoryUsageNonpaged
0x1802df931  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802df935  inc     rax
0x1802df938  cmp     [rbx+rax*2], r13w
0x1802df93d  jnz     short loc_1802DF935
0x1802df93f  movdqu  [rsp+198h+var_118], xmm0
0x1802df948  mov     [rsp+198h+var_F8], rbx
0x1802df950  mov     [rsp+198h+var_F0], rax
0x1802df958  lea     rdx, [rsp+198h+var_118]
0x1802df960  lea     rcx, [rsp+198h+var_F8]
0x1802df968  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1802df96d  test    eax, eax
0x1802df96f  jnz     short loc_1802DF980
0x1802df971  mov     [rsp+198h+var_158], r15b
0x1802df976  lea     rdx, [rsp+198h+var_C8]
0x1802df97e  jmp     short loc_1802DF9D4
0x1802df980  movups  xmm0, xmmword ptr cs:?k_perfCounterName_EventsLogged@TraceSessionUsage@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::TraceSessionUsage::k_perfCounterName_EventsLogged
0x1802df987  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802df98b  inc     rax
0x1802df98e  cmp     [rbx+rax*2], r13w
0x1802df993  jnz     short loc_1802DF98B
0x1802df995  movdqu  [rsp+198h+var_118], xmm0
0x1802df99e  mov     [rsp+198h+var_E8], rbx
0x1802df9a6  mov     [rsp+198h+var_E0], rax
0x1802df9ae  lea     rdx, [rsp+198h+var_118]
0x1802df9b6  lea     rcx, [rsp+198h+var_E8]
0x1802df9be  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1802df9c3  test    eax, eax
0x1802df9c5  jnz     short loc_1802DF9E8
0x1802df9c7  mov     [rsp+198h+var_158], 2
0x1802df9cc  lea     rdx, [rsp+198h+var_A8]
0x1802df9d4  lea     r9, [rsp+198h+var_158]
0x1802df9d9  mov     r8, rdi
0x1802df9dc  lea     rcx, [rsp+198h+var_148]
0x1802df9e1  call    ??$emplace@AEBKW4_enumerated@PerfCounterEnum@Diagnostics@Microsoft@@@?$_Tree@V?$_Tmap_traits@KVPerfCounterEnum@Diagnostics@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVPerfCounterEnum@Diagnostics@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKVPerfCounterEnum@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@_N@1@AEBK$$QEAW4_enumerated@PerfCounterEnum@Diagnostics@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<ulong,Microsoft::Diagnostics::PerfCounterEnum,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::Diagnostics::PerfCounterEnum>>,0>>::emplace<ulong const &,Microsoft::Diagnostics::PerfCounterEnum::_enumerated>(ulong const &,Microsoft::Diagnostics::PerfCounterEnum::_enumerated &&)
0x1802df9e6  jmp     short loc_1802DFA4E
0x1802df9e8  movups  xmm0, xmmword ptr cs:?k_perfCounterName_EventsLost@TraceSessionUsage@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::TraceSessionUsage::k_perfCounterName_EventsLost
0x1802df9ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802df9f3  inc     rax
0x1802df9f6  cmp     [rbx+rax*2], r13w
0x1802df9fb  jnz     short loc_1802DF9F3
0x1802df9fd  movdqu  [rsp+198h+var_118], xmm0
0x1802dfa06  mov     [rsp+198h+var_D8], rbx
0x1802dfa0e  mov     [rsp+198h+var_D0], rax
0x1802dfa16  lea     rdx, [rsp+198h+var_118]
0x1802dfa1e  lea     rcx, [rsp+198h+var_D8]
0x1802dfa26  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1802dfa2b  test    eax, eax
0x1802dfa2d  jnz     short loc_1802DFA4E
0x1802dfa2f  mov     [rsp+198h+var_158], 3
0x1802dfa34  lea     r9, [rsp+198h+var_158]
0x1802dfa39  mov     r8, rdi
0x1802dfa3c  lea     rdx, [rsp+198h+var_90]
0x1802dfa44  lea     rcx, [rsp+198h+var_148]
0x1802dfa49  call    ??$emplace@AEBKW4_enumerated@PerfCounterEnum@Diagnostics@Microsoft@@@?$_Tree@V?$_Tmap_traits@KVPerfCounterEnum@Diagnostics@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVPerfCounterEnum@Diagnostics@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKVPerfCounterEnum@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@_N@1@AEBK$$QEAW4_enumerated@PerfCounterEnum@Diagnostics@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<ulong,Microsoft::Diagnostics::PerfCounterEnum,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::Diagnostics::PerfCounterEnum>>,0>>::emplace<ulong const &,Microsoft::Diagnostics::PerfCounterEnum::_enumerated>(ulong const &,Microsoft::Diagnostics::PerfCounterEnum::_enumerated &&)
0x1802dfa4e  add     esi, r15d
0x1802dfa51  jmp     loc_1802DF8A4
0x1802dfa56  movups  xmm0, xmmword ptr cs:?k_EventTracingSessionCounterSetGuid@TraceSessionUsage@Diagnostics@Microsoft@@0U_GUID@@B.Data1; _GUID const Microsoft::Diagnostics::TraceSessionUsage::k_EventTracingSessionCounterSetGuid ...
0x1802dfa5d  movdqu  xmmword ptr [rsp+198h+pCounters.CounterSetGuid.Data1], xmm0
0x1802dfa66  mov     [rsp+198h+pCounters.Status], r13d
0x1802dfa6e  mov     r8d, 30h ; '0'; cbCounters
0x1802dfa74  mov     [rsp+198h+pCounters.Size], r8d
0x1802dfa7c  mov     qword ptr [rsp+198h+pCounters.CounterId], 0FFFFFFFFFFFFFFFFh
0x1802dfa88  xor     eax, eax
0x1802dfa8a  mov     qword ptr [rsp+198h+pCounters.Index], rax
0x1802dfa92  mov     [rsp+198h+var_58], 2Ah ; '*'
0x1802dfa9e  lea     rdx, [rsp+198h+pCounters]; pCounters
0x1802dfaa6  mov     rcx, [rsp+198h+phQuery]; hQuery
0x1802dfaab  call    cs:__imp_PerfAddCounters
0x1802dfab2  nop     dword ptr [rax+rax+00h]
0x1802dfab7  test    eax, eax
0x1802dfab9  jz      short loc_1802DFB00
0x1802dfabb  mov     rcx, [rsp+198h]; this
0x1802dfac3  mov     r9d, eax; char *
0x1802dfac6  lea     r8, aOnecoreBaseTel_89; "onecore\\base\\telemetry\\utc\\service"...
0x1802dfacd  mov     edx, 0C3h; void *
0x1802dfad2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1802dfad7  mov     ebx, eax
0x1802dfad9  lea     rcx, [rsp+198h+var_148]
0x1802dfade  call    ??1?$_Tree@V?$_Tmap_traits@W4OneSettingsDownloadConfigBoolProperty@@V?$optional@_N@std@@U?$less@W4OneSettingsDownloadConfigBoolProperty@@@3@V?$allocator@U?$pair@$$CBW4OneSettingsDownloadConfigBoolProperty@@V?$optional@_N@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<OneSettingsDownloadConfigBoolProperty,std::optional<bool>,std::less<OneSettingsDownloadConfigBoolProperty>,std::allocator<std::pair<OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>,0>>::~_Tree<std::_Tmap_traits<OneSettingsDownloadConfigBoolProperty,std::optional<bool>,std::less<OneSettingsDownloadConfigBoolProperty>,std::allocator<std::pair<OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>,0>>(void)
0x1802dfae3  nop
0x1802dfae4  lea     rcx, [rsp+198h+var_138]
0x1802dfae9  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1802dfaee  nop
0x1802dfaef  lea     rcx, [rsp+198h+phQuery]
0x1802dfaf4  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AKPEAX@Z$1?PerfCloseQueryHandle@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,ulong (void *),&PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,ulong (void *),&PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1802dfaf9  mov     eax, ebx
0x1802dfafb  jmp     loc_1802DFD47
0x1802dfb00  mov     ebx, r13d
0x1802dfb03  mov     [rsp+198h+pcbCounterBlockActual], r13d
0x1802dfb08  mov     rdx, [rsp+198h+var_138]; pCounterBlock
0x1802dfb0d  mov     r8d, [rsp+198h+var_130]
0x1802dfb12  sub     r8d, edx; cbCounterBlock
0x1802dfb15  lea     r9, [rsp+198h+pcbCounterBlockActual]; pcbCounterBlockActual
0x1802dfb1a  mov     rcx, [rsp+198h+phQuery]; hQuery
0x1802dfb1f  call    cs:__imp_PerfQueryCounterData
0x1802dfb26  nop     dword ptr [rax+rax+00h]
0x1802dfb2b  cmp     eax, 8
0x1802dfb2e  jnz     short loc_1802DFB47
0x1802dfb30  test    ebx, ebx
0x1802dfb32  jnz     short loc_1802DFB4B
0x1802dfb34  mov     edx, [rsp+198h+pcbCounterBlockActual]
0x1802dfb38  lea     rcx, [rsp+198h+var_138]
0x1802dfb3d  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1802dfb42  mov     ebx, r15d
0x1802dfb45  jmp     short loc_1802DFB03
0x1802dfb47  test    eax, eax
0x1802dfb49  jz      short loc_1802DFB90
0x1802dfb4b  mov     rcx, [rsp+198h]; this
0x1802dfb53  mov     r9d, eax; char *
0x1802dfb56  lea     r8, aOnecoreBaseTel_89; "onecore\\base\\telemetry\\utc\\service"...
0x1802dfb5d  mov     edx, 0D0h; void *
0x1802dfb62  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1802dfb67  mov     ebx, eax
0x1802dfb69  lea     rcx, [rsp+198h+var_148]
0x1802dfb6e  call    ??1?$_Tree@V?$_Tmap_traits@W4OneSettingsDownloadConfigBoolProperty@@V?$optional@_N@std@@U?$less@W4OneSettingsDownloadConfigBoolProperty@@@3@V?$allocator@U?$pair@$$CBW4OneSettingsDownloadConfigBoolProperty@@V?$optional@_N@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<OneSettingsDownloadConfigBoolProperty,std::optional<bool>,std::less<OneSettingsDownloadConfigBoolProperty>,std::allocator<std::pair<OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>,0>>::~_Tree<std::_Tmap_traits<OneSettingsDownloadConfigBoolProperty,std::optional<bool>,std::less<OneSettingsDownloadConfigBoolProperty>,std::allocator<std::pair<OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>,0>>(void)
0x1802dfb73  nop
0x1802dfb74  lea     rcx, [rsp+198h+var_138]
0x1802dfb79  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1802dfb7e  nop
0x1802dfb7f  lea     rcx, [rsp+198h+phQuery]
0x1802dfb84  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AKPEAX@Z$1?PerfCloseQueryHandle@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,ulong (void *),&PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,ulong (void *),&PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1802dfb89  mov     eax, ebx
0x1802dfb8b  jmp     loc_1802DFD47
0x1802dfb90  mov     rbx, [rsp+198h+var_138]
0x1802dfb95  mov     r9d, [rbx+30h]; char *
0x1802dfb99  test    r9d, r9d
0x1802dfb9c  jz      short loc_1802DFBE0
0x1802dfb9e  mov     rcx, [rsp+198h]; this
0x1802dfba6  lea     r8, aOnecoreBaseTel_89; "onecore\\base\\telemetry\\utc\\service"...
0x1802dfbad  mov     edx, 0E5h; void *
0x1802dfbb2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1802dfbb7  mov     ebx, eax
0x1802dfbb9  lea     rcx, [rsp+198h+var_148]
0x1802dfbbe  call    ??1?$_Tree@V?$_Tmap_traits@W4OneSettingsDownloadConfigBoolProperty@@V?$optional@_N@std@@U?$less@W4OneSettingsDownloadConfigBoolProperty@@@3@V?$allocator@U?$pair@$$CBW4OneSettingsDownloadConfigBoolProperty@@V?$optional@_N@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<OneSettingsDownloadConfigBoolProperty,std::optional<bool>,std::less<OneSettingsDownloadConfigBoolProperty>,std::allocator<std::pair<OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>,0>>::~_Tree<std::_Tmap_traits<OneSettingsDownloadConfigBoolProperty,std::optional<bool>,std::less<OneSettingsDownloadConfigBoolProperty>,std::allocator<std::pair<OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>,0>>(void)
0x1802dfbc3  nop
0x1802dfbc4  lea     rcx, [rsp+198h+var_138]
0x1802dfbc9  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1802dfbce  nop
0x1802dfbcf  lea     rcx, [rsp+198h+phQuery]
0x1802dfbd4  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AKPEAX@Z$1?PerfCloseQueryHandle@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,ulong (void *),&PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,ulong (void *),&PerfCloseQueryHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1802dfbd9  mov     eax, ebx
0x1802dfbdb  jmp     loc_1802DFD47
0x1802dfbe0  cmp     [rbx+4], r15d
0x1802dfbe4  jnz     loc_1802DFD1F
0x1802dfbea  cmp     dword ptr [rbx+34h], 6
0x1802dfbee  jnz     loc_1802DFD1F
0x1802dfbf4  mov     r15d, [rbx+40h]
0x1802dfbf8  lea     rdi, [rbx+48h]
0x1802dfbfc  add     rdi, r15
0x1802dfbff  mov     r14d, r13d
0x1802dfc02  cmp     r14d, [r15+rbx+44h]
0x1802dfc07  jz      loc_1802DFD1F
0x1802dfc0d  lea     rdx, [rdi+8]
0x1802dfc11  lea     rcx, [rsp+198h+var_50]
0x1802dfc19  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1802dfc1e  nop
0x1802dfc1f  mov     eax, [rdi]
0x1802dfc21  add     rdi, rax
0x1802dfc24  mov     r11d, r13d
0x1802dfc27  cmp     [rbx+44h], r13d
0x1802dfc2b  jz      loc_1802DFCE9
0x1802dfc31  mov     rcx, rdi
0x1802dfc34  mov     eax, r11d
0x1802dfc37  mov     esi, [rbx+rax*4+48h]
0x1802dfc3b  mov     [rsp+198h+pcbCounterBlockActual], esi
0x1802dfc3f  mov     rdx, rdi
0x1802dfc42  mov     eax, [rdi+4]
0x1802dfc45  add     rdi, rax
0x1802dfc48  cmp     dword ptr [rdx], 4
0x1802dfc4b  jz      short loc_1802DFC5D
0x1802dfc4d  cmp     dword ptr [rdx], 8
0x1802dfc50  jz      short loc_1802DFC57
0x1802dfc52  mov     r10, r13
0x1802dfc55  jmp     short loc_1802DFC61
0x1802dfc57  mov     r10, [rdx+8]
0x1802dfc5b  jmp     short loc_1802DFC61
0x1802dfc5d  mov     r10d, [rdx+8]
0x1802dfc61  lea     r8, [rsp+198h+pcbCounterBlockActual]
0x1802dfc66  lea     rdx, [rsp+198h+var_A8]
0x1802dfc6e  lea     rcx, [rsp+198h+var_148]
0x1802dfc73  call    ??$_Find_lower_bound@K@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@KPEAX@std@@@1@AEBK@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::_Find_lower_bound<ulong>(ulong const &)
0x1802dfc78  mov     rdx, [rsp+198h+var_98]
0x1802dfc80  cmp     [rdx+19h], r13b
0x1802dfc84  jnz     short loc_1802DFC92
0x1802dfc86  cmp     esi, [rdx+1Ch]
0x1802dfc89  jb      short loc_1802DFC92
0x1802dfc8b  mov     rax, qword ptr [rsp+198h+var_148]
0x1802dfc90  jmp     short loc_1802DFC9A
0x1802dfc92  mov     rax, qword ptr [rsp+198h+var_148]
  ... truncated ...
```
