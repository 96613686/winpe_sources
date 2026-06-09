# Microsoft::Diagnostics::ScenariosSqliteTable::ResetDatabase(long,Microsoft::Diagnostics::EnumDetails::ResetType)

- ea: `0x180221e4c`
- end: `0x180222505`
- name: `?ResetDatabase@ScenariosSqliteTable@Diagnostics@Microsoft@@AEAAXJVResetType@EnumDetails@23@@Z`
- size: `1721`
- prototype: ``
- caller_count: `3`
- callee_count: `37`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18021db9c`
- `0x180221d40`
- `0x18033903c`

## callees

- `0x1800035ec`
- `0x180005828`
- `0x18001c970`
- `0x18001cf30`
- `0x18001d160`
- `0x180021010`
- `0x180027be0`
- `0x180030a50`
- `0x180035970`
- `0x18003fd8c`
- `0x1800498f0`
- `0x18005d050`
- `0x180082ce8`
- `0x180086c3c`
- `0x180086e5c`
- `0x180086e78`
- `0x180087044`
- `0x1800908f0`
- `0x1800a0d08`
- `0x1800d0d9c`
- `0x1800dff54`
- `0x1800e11e8`
- `0x1800e296c`
- `0x180112c8c`
- `0x18012de40`
- `0x180161298`
- `0x180177b0c`
- `0x18021d250`
- `0x18021d28c`
- `0x18021d9ec`
- `0x18022062c`
- `0x180221e4c`
- `0x180223030`
- `0x18022306c`
- `0x18022312c`
- `0x1802233ec`
- `0x1802234f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802222a0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802222a0`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18022206b`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18022215d`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18022206b`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18022215d`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterFile` at `0x180222386`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterFile` at `0x1802224b7`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterFile` at `0x180222386`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterFile` at `0x1802224b7`

## string_xrefs

- `0x18022207b`: `onecore\base\telemetry\utc\service\scenarios\base\scenariossqlitetable.cpp`
- `0x18022216d`: `onecore\base\telemetry\utc\service\scenarios\base\scenariossqlitetable.cpp`
- `0x180222356`: `onecore\base\telemetry\utc\service\scenarios\base\scenariossqlitetable.cpp`
- `0x1802223a5`: `onecore\base\telemetry\utc\service\scenarios\base\scenariossqlitetable.cpp`
- `0x180222491`: `onecore\base\telemetry\utc\service\scenarios\base\scenariossqlitetable.cpp`
- `0x1802224d9`: `onecore\base\telemetry\utc\service\scenarios\base\scenariossqlitetable.cpp`
- `0x1802224f2`: `onecore\base\telemetry\utc\service\scenarios\base\scenariossqlitetable.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Microsoft::Diagnostics::ScenariosSqliteTable::ResetDatabase(__int64 a1, unsigned int a2, char a3)
{
  __int64 v6; // rdx
  __int64 v7; // rax
  int v8; // r8d
  int v9; // r9d
  char *v10; // rcx
  _QWORD *v11; // rbx
  __int64 result; // rax
  const char *v13; // r9
  __int64 v14; // rax
  __int64 v15; // rax
  const WCHAR *v16; // rdx
  const WCHAR *v17; // rcx
  const char *v18; // r9
  __int64 v19; // rax
  __int64 v20; // rax
  const WCHAR *v21; // rdx
  const WCHAR *v22; // rcx
  const char *v23; // r9
  int v24; // r8d
  int v25; // r9d
  Microsoft::Diagnostics::ScenarioObjectCache *ScenarioObjectCache; // rax
  Microsoft::Diagnostics::ScenarioObjectCache *v27; // rax
  struct Microsoft::Diagnostics::ScenarioManager *ScenarioManager; // rax
  const WCHAR *v29; // rcx
  HRESULT v30; // eax
  unsigned int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  const WCHAR *v35; // rax
  unsigned int v36; // eax
  int v37; // eax
  const char *v38; // r9
  int v39; // [rsp+20h] [rbp-208h]
  int v40; // [rsp+20h] [rbp-208h]
  int v41; // [rsp+20h] [rbp-208h]
  int v42[4]; // [rsp+30h] [rbp-1F8h] BYREF
  _BYTE v43[16]; // [rsp+40h] [rbp-1E8h] BYREF
  _BYTE v44[16]; // [rsp+50h] [rbp-1D8h] BYREF
  _BYTE v45[240]; // [rsp+60h] [rbp-1C8h] BYREF
  LPCWSTR lpNewFileName[3]; // [rsp+150h] [rbp-D8h] BYREF
  unsigned __int64 v47; // [rsp+168h] [rbp-C0h]
  LPCWSTR lpExistingFileName[3]; // [rsp+170h] [rbp-B8h] BYREF
  unsigned __int64 v49; // [rsp+188h] [rbp-A0h]
  __int64 v50; // [rsp+1A8h] [rbp-80h]
  __int64 v51; // [rsp+1B0h] [rbp-78h] BYREF
  unsigned int v52; // [rsp+1B8h] [rbp-70h]
  _BYTE v53[32]; // [rsp+1C0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  try
  {
    if ( (unsigned __int8)((__int64 (*)(void))wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::__private_IsEnabled)() )
    {
      if ( a3 == 3 )
      {
        _InterlockedAdd((volatile signed __int32 *)(a1 + 304), 1u);
        if ( *(_DWORD *)(a1 + 304) >= 0x14u )
          a3 = 1;
      }
    }
    if ( (unsigned int)dword_18042D328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 16) )
    {
      Microsoft::Diagnostics::EnumDetails::ResetType::initialize();
      LOBYTE(v6) = a3;
      v7 = Microsoft::Diagnostics::EnumDetails::ResetType::_from_value_loop(v42, v6, 0);
      if ( *(_BYTE *)v7 )
        v10 = (&`Microsoft::Diagnostics::EnumDetails::better_enums::_data_ResetType::_name_array'::`2'::value)[*(_QWORD *)(v7 + 8)];
      else
        v10 = 0;
      *(_QWORD *)v42 = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v10,
        (unsigned int)&unk_1803CF150,
        v8,
        v9,
        (__int64)v42);
    }
    std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v43, a1 + 200);
    v11 = *(_QWORD **)(a1 + 280);
    std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>,void *>>>(
      a1 + 280,
      a1 + 280,
      v11[1]);
    v11[1] = v11;
    *v11 = v11;
    v11[2] = v11;
    *(_QWORD *)(a1 + 288) = 0;
    std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::reset(a1 + 40, 0);
    *(_QWORD *)v42 = a1;
    if ( a3 == 2 )
    {
      Microsoft::Diagnostics::ScenariosSqliteTable::ResetDatabase_::_3_::_lambda_1_::operator()(v42);
      return std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v43);
    }
    std::wstring::wstring(lpNewFileName);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::GetImpl'::`2'::impl) )
    {
      if ( a3 == 3 )
      {
LABEL_30:
        Microsoft::Diagnostics::ScenariosSqliteTable::ResetDatabase_::_3_::_lambda_1_::operator()(v42);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::GetImpl'::`2'::impl) )
        {
          if ( a3 )
          {
            if ( a3 == 1 )
            {
              v31 = wil::verify_hresult<long>(a2);
              wil::details::in1diag3::Log_Hr(
                retaddr,
                (void *)0x147,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariossqlitetable.cpp",
                (const char *)v31,
                v39);
              v35 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(lpNewFileName, v32, v33, v34);
              v36 = WerRegisterFile(v35, WerRegFileTypeOther, 1u);
              v37 = wil::verify_hresult<long>(v36);
              if ( v37 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x14A,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariossqlitetable.cpp",
                  (const char *)(unsigned int)v37,
                  v41);
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x14B,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariossqlitetable.cpp",
                v38);
            }
            if ( a3 == 3 && !*(_BYTE *)(a1 + 308) )
            {
              if ( (unsigned int)dword_18042D328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 16) )
              {
                v42[0] = *(_DWORD *)(a1 + 304);
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                  (unsigned int)&dword_18042D328,
                  (unsigned int)&unk_1803CF100,
                  v24,
                  v25,
                  (__int64)v42);
              }
              *(_BYTE *)(a1 + 308) = 1;
              *(_DWORD *)(a1 + 48) = 0;
              Microsoft::Diagnostics::ScenariosSqliteTable::Initialize(
                (Microsoft::Diagnostics::ScenariosSqliteTable *)a1,
                1);
              if ( _InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_18043C030, 0, 0) )
              {
                ScenarioObjectCache = Microsoft::Diagnostics::LifetimeManager::GetScenarioObjectCache((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                Microsoft::Diagnostics::ScenarioObjectCache::Clear(ScenarioObjectCache);
                v27 = Microsoft::Diagnostics::LifetimeManager::GetScenarioObjectCache((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                Microsoft::Diagnostics::ScenarioObjectCache::Clean(v27);
              }
              if ( _InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_18043BF10, 0, 0) )
              {
                ScenarioManager = Microsoft::Diagnostics::LifetimeManager::GetScenarioManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                SetEvent(*((HANDLE *)ScenarioManager + 11));
              }
            }
          }
          else
          {
            v51 = a1;
            v52 = a2;
            std::wstring::wstring(v53, lpNewFileName);
            v50 = 0;
            v50 = std::_Func_impl_no_alloc__Microsoft::Diagnostics::ScenariosSqliteTable::ResetDatabase_::_35_::_lambda_2__void_::_Func_impl_no_alloc__Microsoft::Diagnostics::ScenariosSqliteTable::ResetDatabase_::_35_::_lambda_2__void___Microsoft::Diagnostics::ScenariosSqliteTable::ResetDatabase_::_35_::_lambda_2__0_(
                    lpExistingFileName,
                    &v51);
            Microsoft::Diagnostics::TpSerialWork::Submit((_Mtx_t)(a1 + 80));
            std::function<bool (_GUID const &)>::~function<bool (_GUID const &)>(lpExistingFileName);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v53);
            Microsoft::Diagnostics::ScenariosSqliteTable::Initialize(
              (Microsoft::Diagnostics::ScenariosSqliteTable *)a1,
              1);
          }
        }
        else if ( a3 )
        {
          if ( a3 == 1 )
          {
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x17B,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariossqlitetable.cpp",
              (const char *)a2,
              v39);
            v29 = (const WCHAR *)lpNewFileName;
            if ( v47 > 7 )
              v29 = lpNewFileName[0];
            v30 = WerRegisterFile(v29, WerRegFileTypeOther, 1u);
            if ( v30 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x17E,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariossqlitetable.cpp",
                (const char *)(unsigned int)v30,
                v40);
          }
        }
        else
        {
          v51 = a1;
          v52 = a2;
          std::wstring::wstring(v53, lpNewFileName);
          v50 = 0;
          v50 = std::_Func_impl_no_alloc__Microsoft::Diagnostics::ScenariosSqliteTable::ResetDatabase_::_59_::_lambda_3__void_::_Func_impl_no_alloc__Microsoft::Diagnostics::ScenariosSqliteTable::ResetDatabase_::_59_::_lambda_3__void___Microsoft::Diagnostics::ScenariosSqliteTable::ResetDatabase_::_59_::_lambda_3__0_(
                  lpExistingFileName,
                  &v51);
          Microsoft::Diagnostics::TpSerialWork::Submit((_Mtx_t)(a1 + 80));
          std::function<bool (_GUID const &)>::~function<bool (_GUID const &)>(lpExistingFileName);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v53);
          Microsoft::Diagnostics::ScenariosSqliteTable::Initialize(
            (Microsoft::Diagnostics::ScenariosSqliteTable *)a1,
            1);
        }
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpNewFileName);
        return std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v43);
      }
      std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v44);
      v14 = std::operator<<<wchar_t>(v45, a1 + 8);
      std::operator<<<wchar_t,std::char_traits<wchar_t>>(v14, L"\\EventStore.db");
      std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v44, lpExistingFileName);
      std::operator<<<wchar_t,std::char_traits<wchar_t>>(v45, L".bk");
      v15 = std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v44, &v51);
      std::wstring::operator=(lpNewFileName, v15);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v51);
      v16 = (const WCHAR *)lpNewFileName;
      if ( v47 > 7 )
        v16 = lpNewFileName[0];
      v17 = (const WCHAR *)lpExistingFileName;
      if ( v49 > 7 )
        v17 = lpExistingFileName[0];
      if ( !CopyFileW(v17, v16, 1) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x121,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariossqlitetable.cpp",
          v18);
    }
    else
    {
      std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v44);
      v19 = std::operator<<<wchar_t>(v45, a1 + 8);
      std::operator<<<wchar_t,std::char_traits<wchar_t>>(v19, L"\\EventStore.db");
      std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v44, lpExistingFileName);
      std::operator<<<wchar_t,std::char_traits<wchar_t>>(v45, L".bk");
      v20 = std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v44, &v51);
      std::wstring::operator=(lpNewFileName, v20);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v51);
      v21 = (const WCHAR *)lpNewFileName;
      if ( v47 > 7 )
        v21 = lpNewFileName[0];
      v22 = (const WCHAR *)lpExistingFileName;
      if ( v49 > 7 )
        v22 = lpExistingFileName[0];
      if ( !CopyFileW(v22, v21, 1) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x12C,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariossqlitetable.cpp",
          v23);
    }
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpExistingFileName);
    std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(v44);
    goto LABEL_30;
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariossqlitetable.cpp",
      v13);
  }
  return result;
}

```

## disassembly

```asm
0x180221e4c  push    rbx
0x180221e4e  push    rsi
0x180221e4f  push    rdi
0x180221e50  push    r12
0x180221e52  push    r14
0x180221e54  push    r15
0x180221e56  sub     rsp, 1F8h
0x180221e5d  mov     rax, cs:__security_cookie
0x180221e64  xor     rax, rsp
0x180221e67  mov     [rsp+228h+var_48], rax
0x180221e6f  movzx   r14d, r8b
0x180221e73  mov     r12d, edx
0x180221e76  mov     rsi, rcx
0x180221e79  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ScenarioCacheReconstruction@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ScenarioCacheReconstruction@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioCacheReconstruction> `wil::Feature<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::GetImpl(void)'::`2'::impl
0x180221e80  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ScenarioCacheReconstruction@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::__private_IsEnabled(void)
0x180221e85  mov     r15d, 1
0x180221e8b  test    al, al
0x180221e8d  jz      short loc_180221EAB
0x180221e8f  cmp     r14b, 3
0x180221e93  jnz     short loc_180221EAB
0x180221e95  lock add [rsi+130h], r15d
0x180221e9d  mov     eax, [rsi+130h]
0x180221ea3  nop
0x180221ea4  cmp     eax, 14h
0x180221ea7  cmovnb  r14d, r15d
0x180221eab  mov     eax, cs:dword_18042D328
0x180221eb1  cmp     eax, 5
0x180221eb4  jbe     short loc_180221F13
0x180221eb6  mov     edx, 10h
0x180221ebb  lea     rcx, dword_18042D328
0x180221ec2  call    _tlgKeywordOn
0x180221ec7  test    al, al
0x180221ec9  jz      short loc_180221F13
0x180221ecb  call    ?initialize@ResetType@EnumDetails@Diagnostics@Microsoft@@CAHXZ; Microsoft::Diagnostics::EnumDetails::ResetType::initialize(void)
0x180221ed0  xor     r8d, r8d
0x180221ed3  mov     dl, r14b
0x180221ed6  lea     rcx, [rsp+228h+var_1F8]
0x180221edb  call    ?_from_value_loop@ResetType@EnumDetails@Diagnostics@Microsoft@@CA?AU?$optional@_K@better_enums@@E_K@Z; Microsoft::Diagnostics::EnumDetails::ResetType::_from_value_loop(uchar,unsigned __int64)
0x180221ee0  cmp     byte ptr [rax], 0
0x180221ee3  jz      short loc_180221EF6
0x180221ee5  mov     rax, [rax+8]
0x180221ee9  lea     rcx, ?value@?1??_name_array@_data_ResetType@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA; char const * near * `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ResetType::_name_array(void)'::`2'::value
0x180221ef0  mov     rcx, [rcx+rax*8]
0x180221ef4  jmp     short loc_180221EF8
0x180221ef6  xor     ecx, ecx
0x180221ef8  mov     qword ptr [rsp+228h+var_1F8], rcx
0x180221efd  lea     rax, [rsp+228h+var_1F8]
0x180221f02  mov     qword ptr [rsp+228h+var_208], rax; int
0x180221f07  lea     rdx, unk_1803CF150
0x180221f0e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180221f13  lea     rdx, [rsi+0C8h]
0x180221f1a  lea     rcx, [rsp+228h+var_1E8]
0x180221f1f  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x180221f24  nop
0x180221f25  lea     rdi, [rsi+118h]
0x180221f2c  mov     rbx, [rdi]
0x180221f2f  mov     r8, [rbx+8]
0x180221f33  mov     rdx, rdi
0x180221f36  mov     rcx, rdi
0x180221f39  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>,void *>>>(std::allocator<std::_Tree_node<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>,void *>> &,std::_Tree_node<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>,void *> *)
0x180221f3e  mov     [rbx+8], rbx
0x180221f42  mov     [rbx], rbx
0x180221f45  mov     [rbx+10h], rbx
0x180221f49  mov     qword ptr [rdi+8], 0
0x180221f51  lea     rcx, [rsi+28h]
0x180221f55  xor     edx, edx
0x180221f57  call    ?reset@?$unique_ptr@VSqlConnection@Diagnostics@Microsoft@@U?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@@std@@QEAAXPEAVSqlConnection@Diagnostics@Microsoft@@@Z; std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::reset(Microsoft::Diagnostics::SqlConnection *)
0x180221f5c  mov     qword ptr [rsp+228h+var_1F8], rsi
0x180221f61  mov     edi, 2
0x180221f66  cmp     r14b, dil
0x180221f69  jnz     short loc_180221F85
0x180221f6b  lea     rcx, [rsp+228h+var_1F8]
0x180221f70  call    _Microsoft__Diagnostics__ScenariosSqliteTable__ResetDatabase____3____lambda_1___operator__
0x180221f75  nop
0x180221f76  lea     rcx, [rsp+228h+var_1E8]
0x180221f7b  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180221f80  jmp     loc_18022245C
0x180221f85  lea     rcx, [rsp+228h+lpNewFileName]; void *
0x180221f8d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180221f92  nop
0x180221f93  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ScenarioCacheReconstruction@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ScenarioCacheReconstruction@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioCacheReconstruction> `wil::Feature<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::GetImpl(void)'::`2'::impl
0x180221f9a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ScenarioCacheReconstruction@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::__private_IsEnabled(void)
0x180221f9f  test    al, al
0x180221fa1  jz      loc_1802220A3
0x180221fa7  cmp     r14b, 3
0x180221fab  jz      loc_18022219A
0x180221fb1  lea     rcx, [rsp+228h+var_1D8]
0x180221fb6  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x180221fbb  nop
0x180221fbc  lea     rdx, [rsi+8]
0x180221fc0  lea     rcx, [rsp+228h+var_1C8]
0x180221fc5  call    ??$?6_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::operator<<<wchar_t>(std::wostream &,std::wstring const &)
0x180221fca  lea     rdx, aEventstoreDb; "\\EventStore.db"
0x180221fd1  mov     rcx, rax
0x180221fd4  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180221fd9  lea     rdx, [rsp+228h+lpExistingFileName]
0x180221fe1  lea     rcx, [rsp+228h+var_1D8]
0x180221fe6  call    ?str@?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(void)
0x180221feb  nop
0x180221fec  lea     rdx, aBk; ".bk"
0x180221ff3  lea     rcx, [rsp+228h+var_1C8]
0x180221ff8  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180221ffd  lea     rdx, [rsp+228h+var_78]
0x180222005  lea     rcx, [rsp+228h+var_1D8]
0x18022200a  call    ?str@?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(void)
0x18022200f  mov     rdx, rax
0x180222012  lea     rcx, [rsp+228h+lpNewFileName]
0x18022201a  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18022201f  lea     rcx, [rsp+228h+var_78]; this
0x180222027  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022202c  lea     rdx, [rsp+228h+lpNewFileName]
0x180222034  cmp     [rsp+228h+var_C0], 7
0x18022203d  cmova   rdx, [rsp+228h+lpNewFileName]; lpNewFileName
0x180222046  lea     rcx, [rsp+228h+lpExistingFileName]
0x18022204e  cmp     [rsp+228h+var_A0], 7
0x180222057  cmova   rcx, [rsp+228h+lpExistingFileName]; lpExistingFileName
0x180222060  mov     rbx, [rsp+228h]
0x180222068  mov     r8d, r15d; bFailIfExists
0x18022206b  call    cs:__imp_CopyFileW
0x180222072  nop     dword ptr [rax+rax+00h]
0x180222077  test    eax, eax
0x180222079  jnz     short loc_180222090
0x18022207b  lea     r8, aOnecoreBaseTel_79; "onecore\\base\\telemetry\\utc\\service"...
0x180222082  mov     edx, 121h; void *
0x180222087  mov     rcx, rbx; this
0x18022208a  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18022208f  nop
0x180222090  lea     rcx, [rsp+228h+lpExistingFileName]; this
0x180222098  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022209d  nop
0x18022209e  jmp     loc_180222190
0x1802220a3  lea     rcx, [rsp+228h+var_1D8]
0x1802220a8  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x1802220ad  nop
0x1802220ae  lea     rdx, [rsi+8]
0x1802220b2  lea     rcx, [rsp+228h+var_1C8]
0x1802220b7  call    ??$?6_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::operator<<<wchar_t>(std::wostream &,std::wstring const &)
0x1802220bc  lea     rdx, aEventstoreDb; "\\EventStore.db"
0x1802220c3  mov     rcx, rax
0x1802220c6  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1802220cb  lea     rdx, [rsp+228h+lpExistingFileName]
0x1802220d3  lea     rcx, [rsp+228h+var_1D8]
0x1802220d8  call    ?str@?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(void)
0x1802220dd  nop
0x1802220de  lea     rdx, aBk; ".bk"
0x1802220e5  lea     rcx, [rsp+228h+var_1C8]
0x1802220ea  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1802220ef  lea     rdx, [rsp+228h+var_78]
0x1802220f7  lea     rcx, [rsp+228h+var_1D8]
0x1802220fc  call    ?str@?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(void)
0x180222101  mov     rdx, rax
0x180222104  lea     rcx, [rsp+228h+lpNewFileName]
0x18022210c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180222111  lea     rcx, [rsp+228h+var_78]; this
0x180222119  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022211e  lea     rdx, [rsp+228h+lpNewFileName]
0x180222126  cmp     [rsp+228h+var_C0], 7
0x18022212f  cmova   rdx, [rsp+228h+lpNewFileName]; lpNewFileName
0x180222138  lea     rcx, [rsp+228h+lpExistingFileName]
0x180222140  cmp     [rsp+228h+var_A0], 7
0x180222149  cmova   rcx, [rsp+228h+lpExistingFileName]; lpExistingFileName
0x180222152  mov     rbx, [rsp+228h]
0x18022215a  mov     r8d, r15d; bFailIfExists
0x18022215d  call    cs:__imp_CopyFileW
0x180222164  nop     dword ptr [rax+rax+00h]
0x180222169  test    eax, eax
0x18022216b  jnz     short loc_180222182
0x18022216d  lea     r8, aOnecoreBaseTel_79; "onecore\\base\\telemetry\\utc\\service"...
0x180222174  mov     edx, 12Ch; void *
0x180222179  mov     rcx, rbx; this
0x18022217c  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180222181  nop
0x180222182  lea     rcx, [rsp+228h+lpExistingFileName]; this
0x18022218a  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022218f  nop
0x180222190  lea     rcx, [rsp+228h+var_1D8]
0x180222195  call    ??_D?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAXXZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(void)
0x18022219a  lea     rcx, [rsp+228h+var_1F8]
0x18022219f  call    _Microsoft__Diagnostics__ScenariosSqliteTable__ResetDatabase____3____lambda_1___operator__
0x1802221a4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ScenarioCacheReconstruction@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ScenarioCacheReconstruction@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioCacheReconstruction> `wil::Feature<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::GetImpl(void)'::`2'::impl
0x1802221ab  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ScenarioCacheReconstruction@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::__private_IsEnabled(void)
0x1802221b0  test    al, al
0x1802221b2  jz      loc_18022233D
0x1802221b8  test    r14b, r14b
0x1802221bb  jz      loc_1802222B1
0x1802221c1  cmp     r14b, r15b
0x1802221c4  jz      loc_18022247E
0x1802221ca  cmp     r14b, 3
0x1802221ce  jnz     loc_180222443
0x1802221d4  mov     al, [rsi+134h]
0x1802221da  nop
0x1802221db  test    al, al
0x1802221dd  jnz     loc_180222443
0x1802221e3  mov     eax, cs:dword_18042D328
0x1802221e9  cmp     eax, 5
0x1802221ec  jbe     short loc_18022222B
0x1802221ee  mov     edx, 10h
0x1802221f3  lea     rcx, dword_18042D328
0x1802221fa  call    _tlgKeywordOn
0x1802221ff  test    al, al
0x180222201  jz      short loc_18022222B
0x180222203  mov     eax, [rsi+130h]
0x180222209  nop
0x18022220a  mov     [rsp+228h+var_1F8], eax
0x18022220e  lea     rax, [rsp+228h+var_1F8]
0x180222213  mov     qword ptr [rsp+228h+var_208], rax
0x180222218  lea     rdx, unk_1803CF100
0x18022221f  lea     rcx, dword_18042D328
0x180222226  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18022222b  mov     eax, r15d
0x18022222e  xchg    al, [rsi+134h]
0x180222234  mov     dword ptr [rsi+30h], 0
0x18022223b  mov     dl, r15b; bool
0x18022223e  mov     rcx, rsi; this
0x180222241  call    ?Initialize@ScenariosSqliteTable@Diagnostics@Microsoft@@AEAAX_N@Z; Microsoft::Diagnostics::ScenariosSqliteTable::Initialize(bool)
0x180222246  xor     ecx, ecx
0x180222248  xor     eax, eax
0x18022224a  lock cmpxchg qword ptr cs:xmmword_18043C030, rcx
0x180222253  jz      short loc_18022227D
0x180222255  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x18022225c  call    ?GetScenarioObjectCache@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVScenarioObjectCache@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetScenarioObjectCache(void)
0x180222261  mov     rcx, rax; this
0x180222264  call    ?Clear@ScenarioObjectCache@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::ScenarioObjectCache::Clear(void)
0x180222269  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x180222270  call    ?GetScenarioObjectCache@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVScenarioObjectCache@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetScenarioObjectCache(void)
0x180222275  mov     rcx, rax; this
0x180222278  call    ?Clean@ScenarioObjectCache@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::ScenarioObjectCache::Clean(void)
0x18022227d  xor     edx, edx
0x18022227f  xor     eax, eax
0x180222281  lock cmpxchg qword ptr cs:xmmword_18043BF10, rdx
0x18022228a  jz      loc_180222443
0x180222290  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x180222297  call    ?GetScenarioManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVScenarioManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetScenarioManager(void)
0x18022229c  mov     rcx, [rax+58h]; hEvent
0x1802222a0  call    cs:__imp_SetEvent
0x1802222a7  nop     dword ptr [rax+rax+00h]
0x1802222ac  jmp     loc_180222443
0x1802222b1  mov     [rsp+228h+var_78], rsi
0x1802222b9  mov     [rsp+228h+var_70], r12d
0x1802222c1  lea     rdx, [rsp+228h+lpNewFileName]
0x1802222c9  lea     rcx, [rsp+228h+var_68]
0x1802222d1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1802222d6  nop
0x1802222d7  mov     [rsp+228h+var_80], 0
0x1802222e3  lea     rdx, [rsp+228h+var_78]
0x1802222eb  lea     rcx, [rsp+228h+lpExistingFileName]
0x1802222f3  call    std___Func_impl_no_alloc__Microsoft__Diagnostics__ScenariosSqliteTable__ResetDatabase____35____lambda_2__void____Func_impl_no_alloc__Microsoft__Diagnostics__ScenariosSqliteTable__ResetDatabase____35____lambda_2__void___Microsoft__Diagnostics__ScenariosSqliteTable__ResetDatabase____35____lambda_2__0_
0x1802222f8  mov     [rsp+228h+var_80], rax
0x180222300  lea     rcx, [rsi+50h]; _Mtx_t
0x180222304  lea     rdx, [rsp+228h+lpExistingFileName]
0x18022230c  call    ?Submit@TpSerialWork@Diagnostics@Microsoft@@QEAAXAEBV?$function@$$A6AXXZ@std@@@Z; Microsoft::Diagnostics::TpSerialWork::Submit(std::function<void (void)> const &)
0x180222311  nop
0x180222312  lea     rcx, [rsp+228h+lpExistingFileName]
0x18022231a  call    ??1?$function@$$A6A_NAEBU_GUID@@@Z@std@@QEAA@XZ; std::function<bool (_GUID const &)>::~function<bool (_GUID const &)>(void)
0x18022231f  nop
0x180222320  lea     rcx, [rsp+228h+var_68]; this
0x180222328  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022232d  mov     dl, r15b; bool
0x180222330  mov     rcx, rsi; this
0x180222333  call    ?Initialize@ScenariosSqliteTable@Diagnostics@Microsoft@@AEAAX_N@Z; Microsoft::Diagnostics::ScenariosSqliteTable::Initialize(bool)
0x180222338  jmp     loc_180222443
0x18022233d  test    r14b, r14b
0x180222340  jz      short loc_1802223BB
0x180222342  cmp     r14b, r15b
0x180222345  jnz     loc_180222443
0x18022234b  mov     rcx, [rsp+228h]; this
0x180222353  mov     r9d, r12d; char *
0x180222356  lea     r8, aOnecoreBaseTel_79; "onecore\\base\\telemetry\\utc\\service"...
0x18022235d  mov     edx, 17Bh; void *
0x180222362  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180222367  lea     rcx, [rsp+228h+lpNewFileName]
0x18022236f  cmp     [rsp+228h+var_C0], 7
0x180222378  cmova   rcx, [rsp+228h+lpNewFileName]; pwzFile
0x180222381  mov     r8d, r15d; dwFlags
0x180222384  mov     edx, edi; regFileType
0x180222386  call    cs:__imp_WerRegisterFile
0x18022238d  nop     dword ptr [rax+rax+00h]
0x180222392  mov     rcx, [rsp+228h]; this
0x18022239a  test    eax, eax
0x18022239c  jns     loc_180222443
0x1802223a2  mov     r9d, eax; char *
0x1802223a5  lea     r8, aOnecoreBaseTel_79; "onecore\\base\\telemetry\\utc\\service"...
0x1802223ac  mov     edx, 17Eh; void *
0x1802223b1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1802223b6  jmp     loc_180222443
0x1802223bb  mov     [rsp+228h+var_78], rsi
0x1802223c3  mov     [rsp+228h+var_70], r12d
0x1802223cb  lea     rdx, [rsp+228h+lpNewFileName]
0x1802223d3  lea     rcx, [rsp+228h+var_68]
0x1802223db  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1802223e0  nop
0x1802223e1  mov     [rsp+228h+var_80], 0
0x1802223ed  lea     rdx, [rsp+228h+var_78]
0x1802223f5  lea     rcx, [rsp+228h+lpExistingFileName]
0x1802223fd  call    std___Func_impl_no_alloc__Microsoft__Diagnostics__ScenariosSqliteTable__ResetDatabase____59____lambda_3__void____Func_impl_no_alloc__Microsoft__Diagnostics__ScenariosSqliteTable__ResetDatabase____59____lambda_3__void___Microsoft__Diagnostics__ScenariosSqliteTable__ResetDatabase____59____lambda_3__0_
0x180222402  mov     [rsp+228h+var_80], rax
0x18022240a  lea     rcx, [rsi+50h]; _Mtx_t
0x18022240e  lea     rdx, [rsp+228h+lpExistingFileName]
0x180222416  call    ?Submit@TpSerialWork@Diagnostics@Microsoft@@QEAAXAEBV?$function@$$A6AXXZ@std@@@Z; Microsoft::Diagnostics::TpSerialWork::Submit(std::function<void (void)> const &)
0x18022241b  nop
  ... truncated ...
```
