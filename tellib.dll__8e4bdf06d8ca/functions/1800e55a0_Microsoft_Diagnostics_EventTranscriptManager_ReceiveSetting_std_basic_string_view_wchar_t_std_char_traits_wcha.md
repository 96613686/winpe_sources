# Microsoft::Diagnostics::EventTranscriptManager::ReceiveSetting(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,unsigned __int64,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x1800e55a0`
- end: `0x1800e5ea3`
- name: `?ReceiveSetting@EventTranscriptManager@Diagnostics@Microsoft@@UEAA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_K00_N0@Z`
- size: `2307`
- prototype: ``
- caller_count: `0`
- callee_count: `36`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180015564`
- `0x180015884`
- `0x18001c5b0`
- `0x18001d160`
- `0x180026ecc`
- `0x180031c08`
- `0x180035698`
- `0x180038870`
- `0x18003f14c`
- `0x18004a750`
- `0x18004be98`
- `0x180053a4c`
- `0x180053a84`
- `0x180053bbc`
- `0x180057f58`
- `0x18005a554`
- `0x180078558`
- `0x18007b838`
- `0x1800b77dc`
- `0x1800cea6c`
- `0x1800d0d9c`
- `0x1800d43a8`
- `0x1800dff54`
- `0x1800e55a0`
- `0x1800e5eac`
- `0x1800e5ee0`
- `0x180112cbc`
- `0x18012de40`
- `0x1802c9c48`
- `0x1802ca770`
- `0x1802cb550`
- `0x1802cb584`
- `0x1802cb724`
- `0x1802ccba8`
- `0x1802d61e0`
- `0x1802d9404`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800e5764`
- `msvcp_win!_Mtx_unlock` at `0x1800e57dc`
- `msvcp_win!_Mtx_unlock` at `0x1800e59f9`
- `msvcp_win!_Mtx_unlock` at `0x1800e5be5`
- `msvcp_win!_Mtx_unlock` at `0x1800e5db2`
- `msvcp_win!_Mtx_unlock` at `0x1800e5764`
- `msvcp_win!_Mtx_unlock` at `0x1800e57dc`
- `msvcp_win!_Mtx_unlock` at `0x1800e59f9`
- `msvcp_win!_Mtx_unlock` at `0x1800e5be5`
- `msvcp_win!_Mtx_unlock` at `0x1800e5db2`

## string_xrefs

- `0x1800e56a1`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1800e574f`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1800e588c`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1800e59ae`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1800e5a8c`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1800e5bb0`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1800e5c9b`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1800e5cc7`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1800e5d8f`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1800e5dce`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
char __fastcall Microsoft::Diagnostics::EventTranscriptManager::ReceiveSetting(
        _QWORD *a1,
        __int128 *a2,
        __int64 a3,
        __int128 *a4,
        _QWORD *a5)
{
  _QWORD *v8; // rax
  __int64 v9; // rax
  int v10; // eax
  __int64 v12; // rcx
  int v13; // esi
  int v14; // eax
  _DWORD *v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // r8
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rbx
  __int64 v25; // rbx
  __int64 v26; // r8
  __int64 v27; // rax
  int v28; // eax
  int v29; // eax
  __int64 v30; // rax
  __int64 v31; // rcx
  unsigned __int64 v32; // rax
  __int64 v33; // rax
  int v34[4]; // [rsp+20h] [rbp-138h] BYREF
  _DWORD v35[4]; // [rsp+30h] [rbp-128h] BYREF
  __int128 v36; // [rsp+40h] [rbp-118h] BYREF
  _DWORD v37[4]; // [rsp+50h] [rbp-108h] BYREF
  __int128 v38; // [rsp+60h] [rbp-F8h] BYREF
  _BYTE v39[16]; // [rsp+70h] [rbp-E8h] BYREF
  unsigned __int8 v40[32]; // [rsp+80h] [rbp-D8h] BYREF
  int v41; // [rsp+A0h] [rbp-B8h]
  _BYTE v42[32]; // [rsp+A8h] [rbp-B0h] BYREF
  _BYTE v43[40]; // [rsp+C8h] [rbp-90h] BYREF
  _BYTE v44[32]; // [rsp+F0h] [rbp-68h] BYREF
  _BYTE v45[32]; // [rsp+110h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  *(_OWORD *)v34 = *(_OWORD *)&off_180368130;
  v36 = *a2;
  if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v36, v34) )
  {
    *(_OWORD *)v34 = *(_OWORD *)off_180368120;
    v36 = *a4;
    if ( (unsigned __int8)Microsoft::Diagnostics::Utils::String::IStartsWith(&v36, v34) )
    {
      v8 = (_QWORD *)std::wstring_view::substr(a4, v39, 9, -1);
      v9 = std::wstring::wstring((__int64)v42, v8);
      std::operator+<wchar_t>(v43, L"0x", v9);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v42);
      v35[0] = 0;
      v10 = Microsoft::Diagnostics::Utils::String::ToUIntTStrict<unsigned long>(v43, v35);
      if ( v10 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x413,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)(unsigned int)v10,
          v34[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v43);
        return 1;
      }
      *(_QWORD *)&v36 = L",";
      *((_QWORD *)&v36 + 1) = 1;
      v38 = *(_OWORD *)a5;
      Microsoft::Diagnostics::Utils::String::SplitToSet<std::wstring,std::less<void>>(v34, &v38, &v36);
      *(_QWORD *)&v36 = a1 + 219;
      std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 219));
      v12 = **(_QWORD **)v34;
      *(_QWORD *)&v38 = **(_QWORD **)v34;
      v13 = v35[0];
      while ( !*(_BYTE *)(v12 + 25) )
      {
        v37[0] = 0;
        v14 = Microsoft::Diagnostics::Utils::String::ToUIntTStrict<unsigned long>(v12 + 32, v37);
        if ( v14 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x421,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
            (const char *)(unsigned int)v14,
            v34[0]);
          _Mtx_unlock((_Mtx_t)(a1 + 219));
          std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
            v34,
            v34);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v43);
          return 1;
        }
        v15 = (_DWORD *)a1[201];
        if ( v15 == (_DWORD *)a1[202] )
        {
          std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<unsigned long &,unsigned long &>(
            a1 + 200,
            v15,
            v35,
            v37);
        }
        else
        {
          *v15 = v13;
          v15[1] = v37[0];
          a1[201] += 8LL;
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>>>>,std::_Iterator_base0>::operator++(&v38);
        v12 = v38;
      }
      _Mtx_unlock((_Mtx_t)(a1 + 219));
      std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
        v34,
        v34);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v43);
    }
    else
    {
      *(_OWORD *)v34 = *(_OWORD *)&off_180368150;
      v36 = *a4;
      if ( (unsigned __int8)Microsoft::Diagnostics::Utils::String::IStartsWith(&v36, v34) )
      {
        std::string::string(v40);
        v41 = 0;
        *(_OWORD *)v34 = *a4;
        v36 = *(_OWORD *)&off_180368150;
        v17 = Microsoft::Diagnostics::EventTranscriptManager::ParseTagSetting(v16, &v36, v34, v40);
        if ( v17 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x42D,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
            (const char *)(unsigned int)v17,
            v34[0]);
          std::string::_Tidy_deallocate(v40);
          return 1;
        }
        *(_QWORD *)&v36 = a1 + 219;
        std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 219));
        std::_Tree<std::_Tmap_traits<std::pair<std::string,unsigned long>,std::pair<std::string,std::string>,std::less<std::pair<std::string,unsigned long>>,std::allocator<std::pair<std::pair<std::string,unsigned long> const,std::pair<std::string,std::string>>>,0>>::find(
          a1 + 198,
          &v38,
          v40);
        v19 = v38;
        if ( (_QWORD)v38 == a1[198] )
        {
          std::string::string(v43, &word_1803725C0, v18);
          *(_OWORD *)v34 = *(_OWORD *)a5;
          v20 = Microsoft::Diagnostics::Utils::String::WideStringToMultiByteString(v42, v34);
          std::string::string(v44, v20);
          std::string::string(v45, v43);
          std::_Tree<std::_Tmap_traits<std::pair<std::string,unsigned long>,std::pair<std::string,std::string>,std::less<std::pair<std::string,unsigned long>>,std::allocator<std::pair<std::pair<std::string,unsigned long> const,std::pair<std::string,std::string>>>,0>>::emplace<std::pair<std::string,unsigned long> &,std::pair<std::string,std::string>>(
            a1 + 198,
            v34,
            v40,
            v44);
          std::pair<std::string,std::string>::~pair<std::string,std::string>(v44);
          std::string::_Tidy_deallocate(v42);
          std::string::_Tidy_deallocate(v43);
          if ( !LOBYTE(v34[2]) )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x43A,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
              (const char *)0x800700B7LL,
              v34[0]);
        }
        else
        {
          *(_OWORD *)v34 = *(_OWORD *)a5;
          v21 = Microsoft::Diagnostics::Utils::String::WideStringToMultiByteString(v42, v34);
          std::string::operator=(v19 + 72, v21);
          std::string::_Tidy_deallocate(v42);
        }
      }
      else
      {
        *(_OWORD *)v34 = *(_OWORD *)&off_180368140;
        v36 = *a4;
        if ( !(unsigned __int8)Microsoft::Diagnostics::Utils::String::IStartsWith(&v36, v34) )
        {
          *(_OWORD *)v34 = *(_OWORD *)off_180368110;
          v36 = *a4;
          if ( (unsigned __int8)Microsoft::Diagnostics::Utils::String::IStartsWith(&v36, v34) )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DmaUtcUpdate>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_DmaUtcUpdate>::GetImpl'::`2'::impl) )
            {
              std::wstring_view::substr(a4, v34, 12, -1);
              v35[0] = 0;
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TvsWarningFixes>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_TvsWarningFixes>::GetImpl'::`2'::impl) )
              {
                v28 = Microsoft::Diagnostics::Utils::String::ToUIntTStrict<unsigned long>(v34, v35);
                if ( v28 < 0 )
                {
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x462,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
                    (const char *)(unsigned int)v28,
                    v34[0]);
                  return 1;
                }
              }
              else
              {
                v29 = Microsoft::Diagnostics::Utils::String::ToUIntTStrict<unsigned long>(v34, v35);
                if ( v29 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x469,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
                    (const char *)(unsigned int)v29,
                    v34[0]);
                  return 1;
                }
              }
              *(_QWORD *)&v36 = a1 + 219;
              std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 219));
              v30 = std::wstring::wstring(v42, *a5, a5[1]);
              std::wstring::wstring(v40, v30);
              v41 = v35[0];
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v42);
              v32 = std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring>(
                      v31,
                      v40);
              if ( std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find<std::wstring>(
                     (__int64)(a1 + 211),
                     (__int64)v40,
                     v32) == a1[212] )
              {
                std::_Hash<std::_Uset_traits<std::pair<std::wstring,unsigned long>,std::_Uhash_compare<std::pair<std::wstring,unsigned long>,Microsoft::Diagnostics::EventTranscriptManager::WStringUint32PairHash,Microsoft::Diagnostics::EventTranscriptManager::WStringUint32PairEqual>,std::allocator<std::pair<std::wstring,unsigned long>>,0>>::emplace<std::pair<std::wstring,unsigned long> &>(
                  a1 + 211,
                  v34,
                  v40);
                if ( !LOBYTE(v34[2]) )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x474,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
                    (const char *)0x800700B7LL,
                    v34[0]);
              }
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v40);
              _Mtx_unlock((_Mtx_t)(a1 + 219));
            }
          }
          else
          {
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x47A,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
              (const char *)0x80070057LL,
              v34[0]);
          }
          return 1;
        }
        std::string::string(v40);
        v41 = 0;
        *(_OWORD *)v34 = *a4;
        v36 = *(_OWORD *)&off_180368140;
        v23 = Microsoft::Diagnostics::EventTranscriptManager::ParseTagSetting(v22, &v36, v34, v40);
        if ( v23 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x445,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
            (const char *)(unsigned int)v23,
            v34[0]);
          std::string::_Tidy_deallocate(v40);
          return 1;
        }
        *(_QWORD *)&v36 = a1 + 219;
        std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 219));
        std::_Tree<std::_Tmap_traits<std::pair<std::string,unsigned long>,std::pair<std::string,std::string>,std::less<std::pair<std::string,unsigned long>>,std::allocator<std::pair<std::pair<std::string,unsigned long> const,std::pair<std::string,std::string>>>,0>>::find(
          a1 + 198,
          &v38,
          v40);
        v24 = v38;
        *(_OWORD *)v34 = *(_OWORD *)a5;
        if ( (_QWORD)v38 == a1[198] )
        {
          v25 = Microsoft::Diagnostics::Utils::String::WideStringToMultiByteString(v42, v34);
          std::string::string(v43, &word_1803725C0, v26);
          std::string::string(v44, v43);
          std::string::string(v45, v25);
          std::_Tree<std::_Tmap_traits<std::pair<std::string,unsigned long>,std::pair<std::string,std::string>,std::less<std::pair<std::string,unsigned long>>,std::allocator<std::pair<std::pair<std::string,unsigned long> const,std::pair<std::string,std::string>>>,0>>::emplace<std::pair<std::string,unsigned long> &,std::pair<std::string,std::string>>(
            a1 + 198,
            v34,
            v40,
            v44);
          std::pair<std::string,std::string>::~pair<std::string,std::string>(v44);
          std::string::_Tidy_deallocate(v43);
          std::string::_Tidy_deallocate(v42);
          if ( !LOBYTE(v34[2]) )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x452,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
              (const char *)0x800700B7LL,
              v34[0]);
        }
        else
        {
          v27 = Microsoft::Diagnostics::Utils::String::WideStringToMultiByteString(v42, v34);
          std::string::operator=(v24 + 104, v27);
          std::string::_Tidy_deallocate(v42);
        }
      }
      _Mtx_unlock((_Mtx_t)(a1 + 219));
      std::string::_Tidy_deallocate(v40);
    }
    return 1;
  }
  *(_OWORD *)v34 = *(_OWORD *)&off_1803680F0;
  v36 = *a2;
  if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v36, v34) )
    return 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DmaUtcUpdate>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_DmaUtcUpdate>::GetImpl'::`2'::impl) )
    return 0;
  *(_OWORD *)v34 = *(_OWORD *)&off_180368100;
  v36 = *a4;
  if ( !(unsigned __int8)Microsoft::Diagnostics::Utils::String::IStartsWith(&v36, v34) )
    return 0;
  v33 = std::wstring::wstring(v42, *a5, a5[1]);
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
    a1 + 203,
    v39,
    v33);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v42);
  return 1;
}

```

## disassembly

```asm
0x1800e55a0  mov     [rsp+arg_10], rbx
0x1800e55a5  push    rsi
0x1800e55a6  push    rdi
0x1800e55a7  push    r14
0x1800e55a9  sub     rsp, 140h
0x1800e55b0  mov     rax, cs:__security_cookie
0x1800e55b7  xor     rax, rsp
0x1800e55ba  mov     [rsp+158h+var_28], rax
0x1800e55c2  mov     rbx, r9
0x1800e55c5  mov     r14, rdx
0x1800e55c8  mov     rdi, rcx
0x1800e55cb  mov     rsi, [rsp+158h+arg_20]
0x1800e55d3  movups  xmm0, xmmword ptr cs:off_180368130; "UTCPrivacy"
0x1800e55da  movdqu  xmmword ptr [rsp+158h+var_138], xmm0
0x1800e55e0  movups  xmm0, xmmword ptr [rdx]
0x1800e55e3  movdqu  [rsp+158h+var_118], xmm0
0x1800e55e9  lea     rdx, [rsp+158h+var_138]
0x1800e55ee  lea     rcx, [rsp+158h+var_118]
0x1800e55f3  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1800e55f8  lea     rdx, [rsp+158h+var_138]
0x1800e55fd  lea     rcx, [rsp+158h+var_118]
0x1800e5602  test    eax, eax
0x1800e5604  jnz     loc_1800E5DE6
0x1800e560a  movups  xmm0, xmmword ptr cs:off_180368120; "EventTag"
0x1800e5611  movdqu  xmmword ptr [rsp+158h+var_138], xmm0; int
0x1800e5617  movups  xmm0, xmmword ptr [rbx]
0x1800e561a  movdqu  [rsp+158h+var_118], xmm0
0x1800e5620  call    ?IStartsWith@String@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::IStartsWith(std::wstring_view,std::wstring_view)
0x1800e5625  test    al, al
0x1800e5627  jz      loc_1800E580B
0x1800e562d  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800e5631  lea     r8d, [r9+0Ah]
0x1800e5635  lea     rdx, [rsp+158h+var_E8]
0x1800e563a  mov     rcx, rbx
0x1800e563d  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x1800e5642  mov     rdx, rax
0x1800e5645  lea     rcx, [rsp+158h+var_B0]
0x1800e564d  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1800e5652  nop
0x1800e5653  mov     r8, rax
0x1800e5656  lea     rdx, a0x_0; "0x"
0x1800e565d  lea     rcx, [rsp+158h+var_90]
0x1800e5665  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_W$$QEAV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring &&)
0x1800e566a  nop
0x1800e566b  lea     rcx, [rsp+158h+var_B0]; this
0x1800e5673  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800e5678  mov     [rsp+158h+var_128], 0
0x1800e5680  lea     rdx, [rsp+158h+var_128]
0x1800e5685  lea     rcx, [rsp+158h+var_90]
0x1800e568d  call    ??$ToUIntTStrict@K@String@Utils@Diagnostics@Microsoft@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAKE_N@Z; Microsoft::Diagnostics::Utils::String::ToUIntTStrict<ulong>(std::wstring const &,ulong &,uchar,bool)
0x1800e5692  mov     rcx, [rsp+158h]; this
0x1800e569a  test    eax, eax
0x1800e569c  jns     short loc_1800E56C7
0x1800e569e  mov     r9d, eax; char *
0x1800e56a1  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1800e56a8  mov     edx, 413h; void *
0x1800e56ad  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e56b2  nop
0x1800e56b3  lea     rcx, [rsp+158h+var_90]; this
0x1800e56bb  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800e56c0  mov     al, 1
0x1800e56c2  jmp     loc_1800E5E7E
0x1800e56c7  lea     rax, asc_180377D98; ","
0x1800e56ce  mov     qword ptr [rsp+158h+var_118], rax
0x1800e56d3  mov     qword ptr [rsp+158h+var_118+8], 1
0x1800e56dc  movups  xmm0, xmmword ptr [rsi]
0x1800e56df  movdqu  [rsp+158h+var_F8], xmm0
0x1800e56e5  lea     r8, [rsp+158h+var_118]
0x1800e56ea  lea     rdx, [rsp+158h+var_F8]
0x1800e56ef  lea     rcx, [rsp+158h+var_138]
0x1800e56f4  call    ??$SplitToSet@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@X@2@@String@Utils@Diagnostics@Microsoft@@SA?AV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@X@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@0J@Z; Microsoft::Diagnostics::Utils::String::SplitToSet<std::wstring,std::less<void>>(std::wstring_view,std::wstring_view,long)
0x1800e56f9  nop
0x1800e56fa  lea     rbx, [rdi+6D8h]
0x1800e5701  mov     qword ptr [rsp+158h+var_118], rbx
0x1800e5706  mov     rcx, rbx; this
0x1800e5709  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800e570e  nop
0x1800e570f  mov     rcx, qword ptr [rsp+158h+var_138]
0x1800e5714  mov     rcx, [rcx]
0x1800e5717  mov     qword ptr [rsp+158h+var_F8], rcx
0x1800e571c  mov     esi, [rsp+158h+var_128]
0x1800e5720  cmp     byte ptr [rcx+19h], 0
0x1800e5724  jnz     loc_1800E57D9
0x1800e572a  mov     [rsp+158h+var_108], 0
0x1800e5732  add     rcx, 20h ; ' '
0x1800e5736  lea     rdx, [rsp+158h+var_108]
0x1800e573b  call    ??$ToUIntTStrict@K@String@Utils@Diagnostics@Microsoft@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAKE_N@Z; Microsoft::Diagnostics::Utils::String::ToUIntTStrict<ulong>(std::wstring const &,ulong &,uchar,bool)
0x1800e5740  mov     rcx, [rsp+158h]; this
0x1800e5748  test    eax, eax
0x1800e574a  jns     short loc_1800E5795
0x1800e574c  mov     r9d, eax; char *
0x1800e574f  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1800e5756  mov     edx, 421h; void *
0x1800e575b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e5760  nop
0x1800e5761  mov     rcx, rbx; _Mtx_t
0x1800e5764  call    cs:__imp__Mtx_unlock
0x1800e576b  nop     dword ptr [rax+rax+00h]
0x1800e5770  nop
0x1800e5771  lea     rdx, [rsp+158h+var_138]
0x1800e5776  lea     rcx, [rsp+158h+var_138]
0x1800e577b  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(std::allocator<std::_Tree_node<std::wstring,void *>> &)
0x1800e5780  nop
0x1800e5781  lea     rcx, [rsp+158h+var_90]; this
0x1800e5789  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800e578e  mov     al, 1
0x1800e5790  jmp     loc_1800E5E7E
0x1800e5795  lea     rcx, [rdi+640h]
0x1800e579c  mov     rdx, [rcx+8]
0x1800e57a0  cmp     rdx, [rcx+10h]
0x1800e57a4  jz      short loc_1800E57B6
0x1800e57a6  mov     [rdx], esi
0x1800e57a8  mov     eax, [rsp+158h+var_108]
0x1800e57ac  mov     [rdx+4], eax
0x1800e57af  add     qword ptr [rcx+8], 8
0x1800e57b4  jmp     short loc_1800E57C5
0x1800e57b6  lea     r9, [rsp+158h+var_108]
0x1800e57bb  lea     r8, [rsp+158h+var_128]
0x1800e57c0  call    ??$_Emplace_reallocate@AEAKAEAK@?$vector@U?$pair@KK@std@@V?$allocator@U?$pair@KK@std@@@2@@std@@AEAAPEAU?$pair@KK@1@QEAU21@AEAK1@Z; std::vector<std::pair<ulong,ulong>>::_Emplace_reallocate<ulong &,ulong &>(std::pair<ulong,ulong> * const,ulong &,ulong &)
0x1800e57c5  lea     rcx, [rsp+158h+var_F8]
0x1800e57ca  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@$$CBUProviderGroupInfo@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>>>>,std::_Iterator_base0>::operator++(void)
0x1800e57cf  mov     rcx, qword ptr [rsp+158h+var_F8]
0x1800e57d4  jmp     loc_1800E5720
0x1800e57d9  mov     rcx, rbx; _Mtx_t
0x1800e57dc  call    cs:__imp__Mtx_unlock
0x1800e57e3  nop     dword ptr [rax+rax+00h]
0x1800e57e8  nop
0x1800e57e9  lea     rdx, [rsp+158h+var_138]
0x1800e57ee  lea     rcx, [rsp+158h+var_138]
0x1800e57f3  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(std::allocator<std::_Tree_node<std::wstring,void *>> &)
0x1800e57f8  nop
0x1800e57f9  lea     rcx, [rsp+158h+var_90]; this
0x1800e5801  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800e5806  jmp     loc_1800E5DDF
0x1800e580b  movups  xmm0, xmmword ptr cs:off_180368150; "DataTypeName"
0x1800e5812  movdqu  xmmword ptr [rsp+158h+var_138], xmm0
0x1800e5818  movups  xmm0, xmmword ptr [rbx]
0x1800e581b  movdqu  [rsp+158h+var_118], xmm0
0x1800e5821  lea     rdx, [rsp+158h+var_138]
0x1800e5826  lea     rcx, [rsp+158h+var_118]
0x1800e582b  call    ?IStartsWith@String@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::IStartsWith(std::wstring_view,std::wstring_view)
0x1800e5830  test    al, al
0x1800e5832  jz      loc_1800E5A0B
0x1800e5838  lea     rcx, [rsp+158h+var_D8]
0x1800e5840  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x1800e5845  mov     [rsp+158h+var_B8], 0
0x1800e5850  movups  xmm0, xmmword ptr [rbx]
0x1800e5853  movdqu  xmmword ptr [rsp+158h+var_138], xmm0; int
0x1800e5859  movups  xmm1, xmmword ptr cs:off_180368150; "DataTypeName"
0x1800e5860  movdqu  [rsp+158h+var_118], xmm1
0x1800e5866  lea     r9, [rsp+158h+var_D8]
0x1800e586e  lea     r8, [rsp+158h+var_138]
0x1800e5873  lea     rdx, [rsp+158h+var_118]
0x1800e5878  call    ?ParseTagSetting@EventTranscriptManager@Diagnostics@Microsoft@@AEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@5@@Z; Microsoft::Diagnostics::EventTranscriptManager::ParseTagSetting(std::wstring_view,std::wstring_view,std::pair<std::string,ulong> &)
0x1800e587d  mov     rcx, [rsp+158h]; this
0x1800e5885  test    eax, eax
0x1800e5887  jns     short loc_1800E58B2
0x1800e5889  mov     r9d, eax; char *
0x1800e588c  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1800e5893  mov     edx, 42Dh; void *
0x1800e5898  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e589d  nop
0x1800e589e  lea     rcx, [rsp+158h+var_D8]; void *
0x1800e58a6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e58ab  mov     al, 1
0x1800e58ad  jmp     loc_1800E5E7E
0x1800e58b2  lea     r14, [rdi+6D8h]
0x1800e58b9  mov     qword ptr [rsp+158h+var_118], r14
0x1800e58be  mov     rcx, r14; this
0x1800e58c1  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800e58c6  nop
0x1800e58c7  lea     r8, [rsp+158h+var_D8]
0x1800e58cf  lea     rdx, [rsp+158h+var_F8]
0x1800e58d4  lea     rcx, [rdi+630h]
0x1800e58db  call    ?find@?$_Tree@V?$_Tmap_traits@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@2@U?$less@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@2@@std@@@std@@@std@@@2@AEBU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@2@@Z; std::_Tree<std::_Tmap_traits<std::pair<std::string,ulong>,std::pair<std::string,std::string>,std::less<std::pair<std::string,ulong>>,std::allocator<std::pair<std::pair<std::string,ulong> const,std::pair<std::string,std::string>>>,0>>::find(std::pair<std::string,ulong> const &)
0x1800e58e0  mov     rbx, qword ptr [rsp+158h+var_F8]
0x1800e58e5  cmp     rbx, [rdi+630h]
0x1800e58ec  jnz     loc_1800E59C1
0x1800e58f2  lea     rdx, word_1803725C0
0x1800e58f9  lea     rcx, [rsp+158h+var_90]
0x1800e5901  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800e5906  nop
0x1800e5907  movups  xmm0, xmmword ptr [rsi]
0x1800e590a  movdqu  xmmword ptr [rsp+158h+var_138], xmm0; int
0x1800e5910  lea     rdx, [rsp+158h+var_138]
0x1800e5915  lea     rcx, [rsp+158h+var_B0]
0x1800e591d  call    ?WideStringToMultiByteString@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::WideStringToMultiByteString(std::wstring_view,ulong)
0x1800e5922  nop
0x1800e5923  mov     rdx, rax
0x1800e5926  lea     rcx, [rsp+158h+var_68]
0x1800e592e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x1800e5933  lea     rdx, [rsp+158h+var_90]
0x1800e593b  lea     rcx, [rsp+158h+var_48]
0x1800e5943  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x1800e5948  nop
0x1800e5949  lea     r9, [rsp+158h+var_68]
0x1800e5951  lea     r8, [rsp+158h+var_D8]
0x1800e5959  lea     rdx, [rsp+158h+var_138]
0x1800e595e  lea     rcx, [rdi+630h]
0x1800e5965  call    ??$emplace@AEAU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@2@@?$_Tree@V?$_Tmap_traits@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@2@U?$less@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@2@@std@@@std@@@std@@@std@@_N@1@AEAU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@1@$$QEAU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@1@@Z; std::_Tree<std::_Tmap_traits<std::pair<std::string,ulong>,std::pair<std::string,std::string>,std::less<std::pair<std::string,ulong>>,std::allocator<std::pair<std::pair<std::string,ulong> const,std::pair<std::string,std::string>>>,0>>::emplace<std::pair<std::string,ulong> &,std::pair<std::string,std::string>>(std::pair<std::string,ulong> &,std::pair<std::string,std::string> &&)
0x1800e596a  nop
0x1800e596b  lea     rcx, [rsp+158h+var_68]
0x1800e5973  call    ??1?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::string,std::string>::~pair<std::string,std::string>(void)
0x1800e5978  nop
0x1800e5979  lea     rcx, [rsp+158h+var_B0]; void *
0x1800e5981  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e5986  nop
0x1800e5987  lea     rcx, [rsp+158h+var_90]; void *
0x1800e598f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e5994  cmp     byte ptr [rsp+158h+var_138+8], 0
0x1800e5999  setz    al
0x1800e599c  mov     rcx, [rsp+158h]; this
0x1800e59a4  test    al, al
0x1800e59a6  jz      short loc_1800E59F6
0x1800e59a8  mov     r9d, 800700B7h; char *
0x1800e59ae  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1800e59b5  mov     edx, 43Ah; void *
0x1800e59ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e59bf  jmp     short loc_1800E59F6
0x1800e59c1  movups  xmm0, xmmword ptr [rsi]
0x1800e59c4  movdqu  xmmword ptr [rsp+158h+var_138], xmm0
0x1800e59ca  lea     rdx, [rsp+158h+var_138]
0x1800e59cf  lea     rcx, [rsp+158h+var_B0]
0x1800e59d7  call    ?WideStringToMultiByteString@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::WideStringToMultiByteString(std::wstring_view,ulong)
0x1800e59dc  lea     rcx, [rbx+48h]
0x1800e59e0  mov     rdx, rax
0x1800e59e3  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800e59e8  lea     rcx, [rsp+158h+var_B0]; void *
0x1800e59f0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e59f5  nop
0x1800e59f6  mov     rcx, r14; _Mtx_t
0x1800e59f9  call    cs:__imp__Mtx_unlock
0x1800e5a00  nop     dword ptr [rax+rax+00h]
0x1800e5a05  nop
0x1800e5a06  jmp     loc_1800E5BF2
0x1800e5a0b  movups  xmm0, xmmword ptr cs:off_180368140; "DataTypeDescription"
0x1800e5a12  movdqu  xmmword ptr [rsp+158h+var_138], xmm0
0x1800e5a18  movups  xmm0, xmmword ptr [rbx]
0x1800e5a1b  movdqu  [rsp+158h+var_118], xmm0
0x1800e5a21  lea     rdx, [rsp+158h+var_138]
0x1800e5a26  lea     rcx, [rsp+158h+var_118]
0x1800e5a2b  call    ?IStartsWith@String@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::IStartsWith(std::wstring_view,std::wstring_view)
0x1800e5a30  test    al, al
0x1800e5a32  jz      loc_1800E5C04
0x1800e5a38  lea     rcx, [rsp+158h+var_D8]
0x1800e5a40  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x1800e5a45  mov     [rsp+158h+var_B8], 0
0x1800e5a50  movups  xmm0, xmmword ptr [rbx]
0x1800e5a53  movdqu  xmmword ptr [rsp+158h+var_138], xmm0; int
0x1800e5a59  movups  xmm1, xmmword ptr cs:off_180368140; "DataTypeDescription"
0x1800e5a60  movdqu  [rsp+158h+var_118], xmm1
0x1800e5a66  lea     r9, [rsp+158h+var_D8]
0x1800e5a6e  lea     r8, [rsp+158h+var_138]
0x1800e5a73  lea     rdx, [rsp+158h+var_118]
0x1800e5a78  call    ?ParseTagSetting@EventTranscriptManager@Diagnostics@Microsoft@@AEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@5@@Z; Microsoft::Diagnostics::EventTranscriptManager::ParseTagSetting(std::wstring_view,std::wstring_view,std::pair<std::string,ulong> &)
0x1800e5a7d  mov     rcx, [rsp+158h]; this
0x1800e5a85  test    eax, eax
0x1800e5a87  jns     short loc_1800E5AB2
0x1800e5a89  mov     r9d, eax; char *
0x1800e5a8c  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1800e5a93  mov     edx, 445h; void *
0x1800e5a98  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e5a9d  nop
0x1800e5a9e  lea     rcx, [rsp+158h+var_D8]; void *
0x1800e5aa6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e5aab  mov     al, 1
0x1800e5aad  jmp     loc_1800E5E7E
0x1800e5ab2  lea     r14, [rdi+6D8h]
0x1800e5ab9  mov     qword ptr [rsp+158h+var_118], r14
0x1800e5abe  mov     rcx, r14; this
0x1800e5ac1  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800e5ac6  nop
0x1800e5ac7  lea     r8, [rsp+158h+var_D8]
0x1800e5acf  lea     rdx, [rsp+158h+var_F8]
0x1800e5ad4  lea     rcx, [rdi+630h]
0x1800e5adb  call    ?find@?$_Tree@V?$_Tmap_traits@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@2@U?$less@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@2@@std@@@std@@@std@@@2@AEBU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@2@@Z; std::_Tree<std::_Tmap_traits<std::pair<std::string,ulong>,std::pair<std::string,std::string>,std::less<std::pair<std::string,ulong>>,std::allocator<std::pair<std::pair<std::string,ulong> const,std::pair<std::string,std::string>>>,0>>::find(std::pair<std::string,ulong> const &)
0x1800e5ae0  mov     rbx, qword ptr [rsp+158h+var_F8]
0x1800e5ae5  movups  xmm0, xmmword ptr [rsi]
0x1800e5ae8  lea     rdx, [rsp+158h+var_138]
0x1800e5aed  lea     rcx, [rsp+158h+var_B0]
0x1800e5af5  movdqu  xmmword ptr [rsp+158h+var_138], xmm0; int
0x1800e5afb  cmp     rbx, [rdi+630h]
0x1800e5b02  jnz     loc_1800E5BC3
0x1800e5b08  call    ?WideStringToMultiByteString@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::WideStringToMultiByteString(std::wstring_view,ulong)
0x1800e5b0d  mov     rbx, rax
0x1800e5b10  lea     rdx, word_1803725C0
0x1800e5b17  lea     rcx, [rsp+158h+var_90]
0x1800e5b1f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800e5b24  nop
0x1800e5b25  lea     rdx, [rsp+158h+var_90]
0x1800e5b2d  lea     rcx, [rsp+158h+var_68]
0x1800e5b35  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x1800e5b3a  mov     rdx, rbx
0x1800e5b3d  lea     rcx, [rsp+158h+var_48]
0x1800e5b45  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x1800e5b4a  nop
0x1800e5b4b  lea     r9, [rsp+158h+var_68]
0x1800e5b53  lea     r8, [rsp+158h+var_D8]
0x1800e5b5b  lea     rdx, [rsp+158h+var_138]
0x1800e5b60  lea     rcx, [rdi+630h]
  ... truncated ...
```
