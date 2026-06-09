# Microsoft::Diagnostics::EventTranscriptManager::FetchGeneralEtmStats(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &&,gsl::span<wchar_t const *,-1>,Microsoft::Diagnostics::EventTranscriptManager::GeneralEtmStats &)

- ea: `0x1802d254c`
- end: `0x1802d2e1f`
- name: `?FetchGeneralEtmStats@EventTranscriptManager@Diagnostics@Microsoft@@QEAAJ$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$span@PEB_W$0?0@gsl@@AEAUGeneralEtmStats@123@@Z`
- size: `2259`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::EventTranscriptManager *this)`
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801d7520`

## callees

- `0x180015030`
- `0x18001c5b0`
- `0x180020fbc`
- `0x180026ecc`
- `0x1800551b0`
- `0x1800a04c8`
- `0x1800b99f8`
- `0x1800babec`
- `0x1800bac3c`
- `0x1800bae3c`
- `0x1800bae88`
- `0x1800bc0a0`
- `0x1800e0e94`
- `0x1801c7d58`
- `0x18021d320`
- `0x1802cc660`
- `0x1802cc754`
- `0x1802cd0b0`
- `0x1802cd814`
- `0x1802d254c`
- `0x1802d601c`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1802d2681`
- `msvcp_win!_Mtx_unlock` at `0x1802d26db`
- `msvcp_win!_Mtx_unlock` at `0x1802d276b`
- `msvcp_win!_Mtx_unlock` at `0x1802d281f`
- `msvcp_win!_Mtx_unlock` at `0x1802d28b1`
- `msvcp_win!_Mtx_unlock` at `0x1802d29ea`
- `msvcp_win!_Mtx_unlock` at `0x1802d2ae2`
- `msvcp_win!_Mtx_unlock` at `0x1802d2bdc`
- `msvcp_win!_Mtx_unlock` at `0x1802d2d53`
- `msvcp_win!_Mtx_unlock` at `0x1802d2ded`
- `msvcp_win!_Mtx_unlock` at `0x1802d2681`
- `msvcp_win!_Mtx_unlock` at `0x1802d26db`
- `msvcp_win!_Mtx_unlock` at `0x1802d276b`
- `msvcp_win!_Mtx_unlock` at `0x1802d281f`
- `msvcp_win!_Mtx_unlock` at `0x1802d28b1`
- `msvcp_win!_Mtx_unlock` at `0x1802d29ea`
- `msvcp_win!_Mtx_unlock` at `0x1802d2ae2`
- `msvcp_win!_Mtx_unlock` at `0x1802d2bdc`
- `msvcp_win!_Mtx_unlock` at `0x1802d2d53`
- `msvcp_win!_Mtx_unlock` at `0x1802d2ded`

## string_xrefs

- `0x1802d257f`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d265e`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d26b8`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d273d`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d27e3`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d2875`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d29a0`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d2a8a`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d2b76`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d2ce0`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall Microsoft::Diagnostics::EventTranscriptManager::FetchGeneralEtmStats(
        Microsoft::Diagnostics::EventTranscriptManager *this,
        __int64 a2,
        __int128 *a3,
        __int64 a4)
{
  int ApiConnection; // eax
  unsigned int v9; // edi
  const char *v10; // r9
  __int64 result; // rax
  __int64 v12; // rax
  struct _Mtx_internal_imp_t *v13; // rdi
  int v14; // r9d
  int AnalyticsStatements; // eax
  unsigned int v16; // esi
  int Statements; // eax
  unsigned int v18; // esi
  __int64 v19; // rax
  __int64 v20; // rsi
  __int64 v21; // rax
  __int64 v22; // r14
  int StoreFileSize; // eax
  unsigned int v24; // r15d
  double v25; // xmm0_8
  double v26; // xmm1_8
  double v27; // xmm0_8
  double v28; // xmm1_8
  __int64 v29; // rax
  unsigned __int64 FileTimeAsULL; // r15
  __int64 v31; // rax
  __int64 v32; // r14
  __int64 v33; // rsi
  __int64 v34; // rax
  int v35; // ecx
  unsigned __int64 v36; // rsi
  signed __int64 v37; // rdx
  float v38; // xmm1_4
  float v39; // xmm0_4
  __int64 v40; // rax
  int v41; // [rsp+20h] [rbp-1C8h]
  int v42; // [rsp+20h] [rbp-1C8h]
  _BYTE v43[16]; // [rsp+40h] [rbp-1A8h] BYREF
  unsigned __int64 v44[4]; // [rsp+50h] [rbp-198h] BYREF
  _BYTE v45[32]; // [rsp+70h] [rbp-178h] BYREF
  _BYTE v46[32]; // [rsp+90h] [rbp-158h] BYREF
  _BYTE v47[24]; // [rsp+B0h] [rbp-138h] BYREF
  _BYTE v48[32]; // [rsp+C8h] [rbp-120h] BYREF
  _BYTE v49[32]; // [rsp+E8h] [rbp-100h] BYREF
  _BYTE v50[56]; // [rsp+108h] [rbp-E0h] BYREF
  __int128 v51; // [rsp+140h] [rbp-A8h] BYREF
  _BYTE v52[32]; // [rsp+150h] [rbp-98h] BYREF
  _BYTE v53[24]; // [rsp+170h] [rbp-78h] BYREF
  _BYTE v54[96]; // [rsp+188h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  try
  {
    ApiConnection = Microsoft::Diagnostics::EventTranscriptManager::OpenReadApiConnection(this);
    v9 = ApiConnection;
    if ( ApiConnection >= 0 )
    {
      v51 = *a3;
      v12 = Microsoft::Diagnostics::EventTranscriptManager::BuildProducersFilter(this, v44, &v51);
      std::set<long>::set<long>(v43, v12);
      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v44);
      v13 = (Microsoft::Diagnostics::EventTranscriptManager *)((char *)this + 2504);
      *(_QWORD *)&v51 = (char *)this + 2504;
      std::_Mutex_base::lock((Microsoft::Diagnostics::EventTranscriptManager *)((char *)this + 2504));
      *(_OWORD *)v44 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043C240, v47);
      LOBYTE(v14) = *(_QWORD *)(a2 + 16) != 0;
      Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker::QueryTimeoutTracker(
        (unsigned int)v50,
        (_DWORD)this,
        9,
        v14,
        (__int64)v44,
        0,
        0);
      AnalyticsStatements = Microsoft::Diagnostics::EventTranscriptManager::PrepareDynamicReadAnalyticsStatements(this);
      v16 = AnalyticsStatements;
      if ( AnalyticsStatements >= 0 )
      {
        Statements = Microsoft::Diagnostics::EventTranscriptManager::PrepareStaticReadStatements(this);
        v18 = Statements;
        if ( Statements >= 0 )
        {
          v19 = Microsoft::Diagnostics::SqliteStatement::Bind<>(*((_QWORD *)this + 332), v44);
          Microsoft::Diagnostics::SqliteBoundStatement::Step(v19, v45);
          std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(v44);
          if ( v45[24] )
          {
            v20 = Microsoft::Diagnostics::SqliteQueryResult::Next<unsigned __int64>(v45);
            v21 = Microsoft::Diagnostics::SqliteStatement::Bind<>(*((_QWORD *)this + 333), v47);
            Microsoft::Diagnostics::SqliteBoundStatement::Step(v21, v46);
            std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(v47);
            if ( v46[24] )
            {
              v22 = Microsoft::Diagnostics::SqliteQueryResult::Next<unsigned __int64>(v46);
              v44[0] = 0;
              StoreFileSize = Microsoft::Diagnostics::EventTranscriptManager::GetStoreFileSize(this, v44);
              v24 = StoreFileSize;
              if ( StoreFileSize >= 0 )
              {
                if ( v20 < 0 )
                  v25 = (double)(int)(v20 & 1 | ((unsigned __int64)v20 >> 1))
                      + (double)(int)(v20 & 1 | ((unsigned __int64)v20 >> 1));
                else
                  v25 = (double)(int)v20;
                if ( v22 < 0 )
                  v26 = (double)(int)(v22 & 1 | ((unsigned __int64)v22 >> 1))
                      + (double)(int)(v22 & 1 | ((unsigned __int64)v22 >> 1));
                else
                  v26 = (double)(int)v22;
                v27 = v25 / v26;
                if ( (v44[0] & 0x8000000000000000uLL) != 0LL )
                  v28 = (double)(int)(v44[0] & 1 | (v44[0] >> 1)) + (double)(int)(v44[0] & 1 | (v44[0] >> 1));
                else
                  v28 = (double)SLODWORD(v44[0]);
                *(_QWORD *)a4 = (unsigned int)(int)(v27 * v28);
                v29 = Microsoft::Diagnostics::SqliteStatement::Bind<>(*((_QWORD *)this + 338), v53);
                Microsoft::Diagnostics::SqliteBoundStatement::Step(v29, v49);
                std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(v53);
                if ( v49[24] )
                {
                  *(_QWORD *)(a4 + 8) = Microsoft::Diagnostics::SqliteQueryResult::Next<unsigned __int64>(v49);
                  FileTimeAsULL = Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL();
                  v44[0] = FileTimeAsULL - 6048000000000LL;
                  v31 = Microsoft::Diagnostics::SqliteStatement::Bind<unsigned __int64 const &>(
                          *((_QWORD *)this + 339),
                          v47,
                          v44);
                  Microsoft::Diagnostics::SqliteBoundStatement::Step(v31, v48);
                  std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(v47);
                  if ( v48[24] )
                  {
                    v32 = Microsoft::Diagnostics::SqliteQueryResult::Next<unsigned __int64>(v48);
                    v33 = Microsoft::Diagnostics::SqliteQueryResult::Next<unsigned __int64>(v48);
                    v34 = Microsoft::Diagnostics::SqliteStatement::Bind<unsigned __int64 const &>(
                            *((_QWORD *)this + 337),
                            v53,
                            v44);
                    Microsoft::Diagnostics::SqliteBoundStatement::Step(v34, v52);
                    std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(v53);
                    if ( v52[24] )
                    {
                      v35 = Microsoft::Diagnostics::SqliteQueryResult::Next<long>(v52);
                      if ( v33 <= v32 || (v36 = v33 - v32, v37 = v36 / 0x23C34600, v36 / 0x23C34600 < 0x3C) )
                      {
                        v39 = FLOAT_N1_0;
                      }
                      else
                      {
                        if ( v37 < 0 )
                          v38 = (float)(int)((v36 / 0x23C34600) & 1 | (v36 / 0x47868C00))
                              + (float)(int)((v36 / 0x23C34600) & 1 | (v36 / 0x47868C00));
                        else
                          v38 = (float)(int)v37;
                        v39 = (float)((float)((float)v35 / v38) * 60.0) * 24.0;
                      }
                      *(float *)(a4 + 20) = v39;
                      v44[0] = FileTimeAsULL - 864000000000LL;
                      v40 = Microsoft::Diagnostics::SqliteStatement::Bind<unsigned __int64 const &>(
                              *((_QWORD *)this + 340),
                              v47,
                              v44);
                      Microsoft::Diagnostics::SqliteBoundStatement::Step(v40, v54);
                      std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(v47);
                      if ( v54[24] )
                      {
                        *(_DWORD *)(a4 + 16) = Microsoft::Diagnostics::SqliteQueryResult::Next<long>(v54);
                        v50[48] = 1;
                        std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v54);
                        std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v52);
                        std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v48);
                        std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v49);
                        std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v46);
                        std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v45);
                        Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker::~QueryTimeoutTracker((Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker *)v50);
                        _Mtx_unlock((Microsoft::Diagnostics::EventTranscriptManager *)((char *)this + 2504));
                        std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v43);
                        result = 0;
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x345,
                          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
                          (const char *)0x8000FFFFLL,
                          v42);
                        std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v54);
                        std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v52);
                        std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v48);
                        std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v49);
                        std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v46);
                        std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v45);
                        Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker::~QueryTimeoutTracker((Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker *)v50);
                        _Mtx_unlock(v13);
                        std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v43);
                        result = 2147549183LL;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x339,
                        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
                        (const char *)0x8000FFFFLL,
                        v42);
                      std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v52);
                      std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v48);
                      std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v49);
                      std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v46);
                      std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v45);
                      Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker::~QueryTimeoutTracker((Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker *)v50);
                      _Mtx_unlock(v13);
                      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v43);
                      result = 2147549183LL;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x334,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
                      (const char *)0x8000FFFFLL,
                      v42);
                    std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v48);
                    std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v49);
                    std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v46);
                    std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v45);
                    Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker::~QueryTimeoutTracker((Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker *)v50);
                    _Mtx_unlock(v13);
                    std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v43);
                    result = 2147549183LL;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x329,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
                    (const char *)0x8000FFFFLL,
                    v42);
                  std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v49);
                  std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v46);
                  std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v45);
                  Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker::~QueryTimeoutTracker((Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker *)v50);
                  _Mtx_unlock(v13);
                  std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v43);
                  result = 2147549183LL;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x324,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
                  (const char *)(unsigned int)StoreFileSize,
                  v42);
                std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v46);
                std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v45);
                Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker::~QueryTimeoutTracker((Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker *)v50);
                _Mtx_unlock((Microsoft::Diagnostics::EventTranscriptManager *)((char *)this + 2504));
                std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v43);
                result = v24;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x320,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
                (const char *)0x8000FFFFLL,
                v42);
              std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v46);
              std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v45);
              Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker::~QueryTimeoutTracker((Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker *)v50);
              _Mtx_unlock(v13);
              std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v43);
              result = 2147549183LL;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x31C,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
              (const char *)0x8000FFFFLL,
              v42);
            std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v45);
            Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker::~QueryTimeoutTracker((Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker *)v50);
            _Mtx_unlock(v13);
            std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v43);
            result = 2147549183LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x319,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
            (const char *)(unsigned int)Statements,
            v42);
          Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker::~QueryTimeoutTracker((Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker *)v50);
          _Mtx_unlock((Microsoft::Diagnostics::EventTranscriptManager *)((char *)this + 2504));
          std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v43);
          result = v18;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x318,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)(unsigned int)AnalyticsStatements,
          v42);
        Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker::~QueryTimeoutTracker((Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker *)v50);
        _Mtx_unlock((Microsoft::Diagnostics::EventTranscriptManager *)((char *)this + 2504));
        std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v43);
        result = v16;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x311,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
        (const char *)(unsigned int)ApiConnection,
        v41);
      result = v9;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x34A,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1802d254c  push    rbx
0x1802d254e  push    rsi
0x1802d254f  push    rdi
0x1802d2550  push    r12
0x1802d2552  push    r14
0x1802d2554  push    r15
0x1802d2556  sub     rsp, 1B8h
0x1802d255d  mov     r12, r9
0x1802d2560  mov     rsi, r8
0x1802d2563  mov     r14, rdx
0x1802d2566  mov     rbx, rcx
0x1802d2569  call    ?OpenReadApiConnection@EventTranscriptManager@Diagnostics@Microsoft@@AEAAJXZ; Microsoft::Diagnostics::EventTranscriptManager::OpenReadApiConnection(void)
0x1802d256e  mov     edi, eax
0x1802d2570  test    eax, eax
0x1802d2572  jns     short loc_1802D2597
0x1802d2574  mov     rcx, [rsp+1E8h]; this
0x1802d257c  mov     r9d, eax; char *
0x1802d257f  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1802d2586  mov     edx, 311h; void *
0x1802d258b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802d2590  mov     eax, edi
0x1802d2592  jmp     loc_1802D2E0D
0x1802d2597  movaps  xmm0, xmmword ptr [rsi]
0x1802d259a  movdqa  [rsp+1E8h+var_A8], xmm0
0x1802d25a3  lea     r8, [rsp+1E8h+var_A8]
0x1802d25ab  lea     rdx, [rsp+1E8h+var_198]
0x1802d25b0  mov     rcx, rbx
0x1802d25b3  call    ?BuildProducersFilter@EventTranscriptManager@Diagnostics@Microsoft@@AEAA?AV?$set@JU?$less@J@std@@V?$allocator@J@2@@std@@V?$span@PEB_W$0?0@gsl@@@Z; Microsoft::Diagnostics::EventTranscriptManager::BuildProducersFilter(gsl::span<wchar_t const *,-1>)
0x1802d25b8  nop
0x1802d25b9  mov     rdx, rax
0x1802d25bc  lea     rcx, [rsp+1E8h+var_1A8]
0x1802d25c1  call    ??0?$set@JU?$less@J@std@@V?$allocator@J@2@@std@@QEAA@$$QEAV01@@Z; std::set<long>::set<long>(std::set<long> &&)
0x1802d25c6  nop
0x1802d25c7  lea     rcx, [rsp+1E8h+var_198]
0x1802d25cc  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x1802d25d1  lea     rdi, [rbx+9C8h]
0x1802d25d8  mov     qword ptr [rsp+1E8h+var_A8], rdi
0x1802d25e0  mov     rcx, rdi; this
0x1802d25e3  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1802d25e8  nop
0x1802d25e9  lea     rdx, [rsp+1E8h+var_138]
0x1802d25f1  lea     rcx, unk_18043C240
0x1802d25f8  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802d25fd  mov     r8d, 9
0x1802d2603  movups  xmm0, xmmword ptr [rax]
0x1802d2606  movdqu  xmmword ptr [rsp+1E8h+var_198], xmm0
0x1802d260c  cmp     qword ptr [r14+10h], 0
0x1802d2611  setnz   r9b
0x1802d2615  mov     [rsp+1E8h+var_1B8], 0
0x1802d261a  mov     [rsp+1E8h+var_1C0], 0
0x1802d2622  lea     rax, [rsp+1E8h+var_198]
0x1802d2627  mov     qword ptr [rsp+1E8h+var_1C8], rax; int
0x1802d262c  mov     rdx, rbx
0x1802d262f  lea     rcx, [rsp+1E8h+var_E0]
0x1802d2637  call    ??0QueryTimeoutTracker@EventTranscriptManager@Diagnostics@Microsoft@@QEAA@AEBV123@VQueryKind@EnumDetails@23@_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@K2@Z; Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker::QueryTimeoutTracker(Microsoft::Diagnostics::EventTranscriptManager const &,Microsoft::Diagnostics::EnumDetails::QueryKind,bool,std::wstring_view,ulong,bool)
0x1802d263c  nop
0x1802d263d  lea     r8, [rsp+1E8h+var_1A8]
0x1802d2642  mov     rdx, r14
0x1802d2645  mov     rcx, rbx; this
0x1802d2648  call    ?PrepareDynamicReadAnalyticsStatements@EventTranscriptManager@Diagnostics@Microsoft@@AEAAJ$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$set@JU?$less@J@std@@V?$allocator@J@2@@5@@Z; Microsoft::Diagnostics::EventTranscriptManager::PrepareDynamicReadAnalyticsStatements(std::wstring &&,std::set<long> &)
0x1802d264d  mov     esi, eax
0x1802d264f  test    eax, eax
0x1802d2651  jns     short loc_1802D269F
0x1802d2653  mov     rcx, [rsp+1E8h]; this
0x1802d265b  mov     r9d, eax; char *
0x1802d265e  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1802d2665  mov     edx, 318h; void *
0x1802d266a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802d266f  nop
0x1802d2670  lea     rcx, [rsp+1E8h+var_E0]; this
0x1802d2678  call    ??1QueryTimeoutTracker@EventTranscriptManager@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker::~QueryTimeoutTracker(void)
0x1802d267d  nop
0x1802d267e  mov     rcx, rdi; _Mtx_t
0x1802d2681  call    cs:__imp__Mtx_unlock
0x1802d2688  nop     dword ptr [rax+rax+00h]
0x1802d268d  nop
0x1802d268e  lea     rcx, [rsp+1E8h+var_1A8]
0x1802d2693  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x1802d2698  mov     eax, esi
0x1802d269a  jmp     loc_1802D2E0D
0x1802d269f  mov     rcx, rbx; this
0x1802d26a2  call    ?PrepareStaticReadStatements@EventTranscriptManager@Diagnostics@Microsoft@@AEAAJXZ; Microsoft::Diagnostics::EventTranscriptManager::PrepareStaticReadStatements(void)
0x1802d26a7  mov     esi, eax
0x1802d26a9  test    eax, eax
0x1802d26ab  jns     short loc_1802D26F9
0x1802d26ad  mov     rcx, [rsp+1E8h]; this
0x1802d26b5  mov     r9d, eax; char *
0x1802d26b8  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1802d26bf  mov     edx, 319h; void *
0x1802d26c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802d26c9  nop
0x1802d26ca  lea     rcx, [rsp+1E8h+var_E0]; this
0x1802d26d2  call    ??1QueryTimeoutTracker@EventTranscriptManager@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker::~QueryTimeoutTracker(void)
0x1802d26d7  nop
0x1802d26d8  mov     rcx, rdi; _Mtx_t
0x1802d26db  call    cs:__imp__Mtx_unlock
0x1802d26e2  nop     dword ptr [rax+rax+00h]
0x1802d26e7  nop
0x1802d26e8  lea     rcx, [rsp+1E8h+var_1A8]
0x1802d26ed  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x1802d26f2  mov     eax, esi
0x1802d26f4  jmp     loc_1802D2E0D
0x1802d26f9  lea     rdx, [rsp+1E8h+var_198]
0x1802d26fe  mov     rcx, [rbx+0A60h]
0x1802d2705  call    ??$Bind@$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA?AVSqliteBoundStatement@12@XZ; Microsoft::Diagnostics::SqliteStatement::Bind<>(void)
0x1802d270a  nop
0x1802d270b  lea     rdx, [rsp+1E8h+var_178]
0x1802d2710  mov     rcx, rax
0x1802d2713  call    ?Step@SqliteBoundStatement@Diagnostics@Microsoft@@QEAA?AV?$optional@VSqliteQueryResult@Diagnostics@Microsoft@@@std@@XZ; Microsoft::Diagnostics::SqliteBoundStatement::Step(void)
0x1802d2718  nop
0x1802d2719  lea     rcx, [rsp+1E8h+var_198]; void *
0x1802d271e  call    ??1?$shared_ptr@$$CBUProviderGroupInfo@Diagnostics@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(void)
0x1802d2723  cmp     [rsp+1E8h+var_160], 0
0x1802d272b  jnz     short loc_1802D2789
0x1802d272d  mov     rcx, [rsp+1E8h]; this
0x1802d2735  mov     ebx, 8000FFFFh
0x1802d273a  mov     r9d, ebx; char *
0x1802d273d  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1802d2744  mov     edx, 31Ch; void *
0x1802d2749  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802d274e  nop
0x1802d274f  lea     rcx, [rsp+1E8h+var_178]
0x1802d2754  call    ??1?$_Optional_destruct_base@VSqliteQueryResult@Diagnostics@Microsoft@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(void)
0x1802d2759  nop
0x1802d275a  lea     rcx, [rsp+1E8h+var_E0]; this
0x1802d2762  call    ??1QueryTimeoutTracker@EventTranscriptManager@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker::~QueryTimeoutTracker(void)
0x1802d2767  nop
0x1802d2768  mov     rcx, rdi; _Mtx_t
0x1802d276b  call    cs:__imp__Mtx_unlock
0x1802d2772  nop     dword ptr [rax+rax+00h]
0x1802d2777  nop
0x1802d2778  lea     rcx, [rsp+1E8h+var_1A8]
0x1802d277d  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x1802d2782  mov     eax, ebx
0x1802d2784  jmp     loc_1802D2E0D
0x1802d2789  lea     rcx, [rsp+1E8h+var_178]
0x1802d278e  call    ??$Next@_K@SqliteQueryResult@Diagnostics@Microsoft@@QEAA_KXZ; Microsoft::Diagnostics::SqliteQueryResult::Next<unsigned __int64>(void)
0x1802d2793  mov     rsi, rax
0x1802d2796  lea     rdx, [rsp+1E8h+var_138]
0x1802d279e  mov     rcx, [rbx+0A68h]
0x1802d27a5  call    ??$Bind@$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA?AVSqliteBoundStatement@12@XZ; Microsoft::Diagnostics::SqliteStatement::Bind<>(void)
0x1802d27aa  nop
0x1802d27ab  lea     rdx, [rsp+1E8h+var_158]
0x1802d27b3  mov     rcx, rax
0x1802d27b6  call    ?Step@SqliteBoundStatement@Diagnostics@Microsoft@@QEAA?AV?$optional@VSqliteQueryResult@Diagnostics@Microsoft@@@std@@XZ; Microsoft::Diagnostics::SqliteBoundStatement::Step(void)
0x1802d27bb  nop
0x1802d27bc  lea     rcx, [rsp+1E8h+var_138]; void *
0x1802d27c4  call    ??1?$shared_ptr@$$CBUProviderGroupInfo@Diagnostics@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(void)
0x1802d27c9  cmp     [rsp+1E8h+var_140], 0
0x1802d27d1  jnz     short loc_1802D283D
0x1802d27d3  mov     rcx, [rsp+1E8h]; this
0x1802d27db  mov     ebx, 8000FFFFh
0x1802d27e0  mov     r9d, ebx; char *
0x1802d27e3  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1802d27ea  mov     edx, 320h; void *
0x1802d27ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802d27f4  nop
0x1802d27f5  lea     rcx, [rsp+1E8h+var_158]
0x1802d27fd  call    ??1?$_Optional_destruct_base@VSqliteQueryResult@Diagnostics@Microsoft@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(void)
0x1802d2802  nop
0x1802d2803  lea     rcx, [rsp+1E8h+var_178]
0x1802d2808  call    ??1?$_Optional_destruct_base@VSqliteQueryResult@Diagnostics@Microsoft@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(void)
0x1802d280d  nop
0x1802d280e  lea     rcx, [rsp+1E8h+var_E0]; this
0x1802d2816  call    ??1QueryTimeoutTracker@EventTranscriptManager@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker::~QueryTimeoutTracker(void)
0x1802d281b  nop
0x1802d281c  mov     rcx, rdi; _Mtx_t
0x1802d281f  call    cs:__imp__Mtx_unlock
0x1802d2826  nop     dword ptr [rax+rax+00h]
0x1802d282b  nop
0x1802d282c  lea     rcx, [rsp+1E8h+var_1A8]
0x1802d2831  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x1802d2836  mov     eax, ebx
0x1802d2838  jmp     loc_1802D2E0D
0x1802d283d  lea     rcx, [rsp+1E8h+var_158]
0x1802d2845  call    ??$Next@_K@SqliteQueryResult@Diagnostics@Microsoft@@QEAA_KXZ; Microsoft::Diagnostics::SqliteQueryResult::Next<unsigned __int64>(void)
0x1802d284a  mov     r14, rax
0x1802d284d  mov     [rsp+1E8h+var_198], 0
0x1802d2856  lea     rdx, [rsp+1E8h+var_198]; unsigned __int64 *
0x1802d285b  mov     rcx, rbx; this
0x1802d285e  call    ?GetStoreFileSize@EventTranscriptManager@Diagnostics@Microsoft@@AEAAJAEA_K@Z; Microsoft::Diagnostics::EventTranscriptManager::GetStoreFileSize(unsigned __int64 &)
0x1802d2863  mov     r15d, eax
0x1802d2866  test    eax, eax
0x1802d2868  jns     short loc_1802D28D0
0x1802d286a  mov     rcx, [rsp+1E8h]; this
0x1802d2872  mov     r9d, eax; char *
0x1802d2875  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1802d287c  mov     edx, 324h; void *
0x1802d2881  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802d2886  nop
0x1802d2887  lea     rcx, [rsp+1E8h+var_158]
0x1802d288f  call    ??1?$_Optional_destruct_base@VSqliteQueryResult@Diagnostics@Microsoft@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(void)
0x1802d2894  nop
0x1802d2895  lea     rcx, [rsp+1E8h+var_178]
0x1802d289a  call    ??1?$_Optional_destruct_base@VSqliteQueryResult@Diagnostics@Microsoft@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(void)
0x1802d289f  nop
0x1802d28a0  lea     rcx, [rsp+1E8h+var_E0]; this
0x1802d28a8  call    ??1QueryTimeoutTracker@EventTranscriptManager@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker::~QueryTimeoutTracker(void)
0x1802d28ad  nop
0x1802d28ae  mov     rcx, rdi; _Mtx_t
0x1802d28b1  call    cs:__imp__Mtx_unlock
0x1802d28b8  nop     dword ptr [rax+rax+00h]
0x1802d28bd  nop
0x1802d28be  lea     rcx, [rsp+1E8h+var_1A8]
0x1802d28c3  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x1802d28c8  mov     eax, r15d
0x1802d28cb  jmp     loc_1802D2E0D
0x1802d28d0  xorps   xmm0, xmm0
0x1802d28d3  test    rsi, rsi
0x1802d28d6  js      short loc_1802D28DF
0x1802d28d8  cvtsi2sd xmm0, rsi
0x1802d28dd  jmp     short loc_1802D28F4
0x1802d28df  mov     rax, rsi
0x1802d28e2  shr     rax, 1
0x1802d28e5  and     esi, 1
0x1802d28e8  or      rax, rsi
0x1802d28eb  cvtsi2sd xmm0, rax
0x1802d28f0  addsd   xmm0, xmm0
0x1802d28f4  xorps   xmm1, xmm1
0x1802d28f7  test    r14, r14
0x1802d28fa  js      short loc_1802D2903
0x1802d28fc  cvtsi2sd xmm1, r14
0x1802d2901  jmp     short loc_1802D2919
0x1802d2903  mov     rax, r14
0x1802d2906  shr     rax, 1
0x1802d2909  and     r14d, 1
0x1802d290d  or      rax, r14
0x1802d2910  cvtsi2sd xmm1, rax
0x1802d2915  addsd   xmm1, xmm1
0x1802d2919  divsd   xmm0, xmm1
0x1802d291d  mov     rcx, [rsp+1E8h+var_198]
0x1802d2922  xorps   xmm1, xmm1
0x1802d2925  test    rcx, rcx
0x1802d2928  js      short loc_1802D2931
0x1802d292a  cvtsi2sd xmm1, rcx
0x1802d292f  jmp     short loc_1802D2946
0x1802d2931  mov     rax, rcx
0x1802d2934  shr     rax, 1
0x1802d2937  and     ecx, 1
0x1802d293a  or      rax, rcx
0x1802d293d  cvtsi2sd xmm1, rax
0x1802d2942  addsd   xmm1, xmm1
0x1802d2946  mulsd   xmm0, xmm1
0x1802d294a  cvttsd2si rax, xmm0
0x1802d294f  mov     [r12], rax
0x1802d2953  lea     rdx, [rsp+1E8h+var_78]
0x1802d295b  mov     rcx, [rbx+0A90h]
0x1802d2962  call    ??$Bind@$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA?AVSqliteBoundStatement@12@XZ; Microsoft::Diagnostics::SqliteStatement::Bind<>(void)
0x1802d2967  nop
0x1802d2968  lea     rdx, [rsp+1E8h+var_100]
0x1802d2970  mov     rcx, rax
0x1802d2973  call    ?Step@SqliteBoundStatement@Diagnostics@Microsoft@@QEAA?AV?$optional@VSqliteQueryResult@Diagnostics@Microsoft@@@std@@XZ; Microsoft::Diagnostics::SqliteBoundStatement::Step(void)
0x1802d2978  nop
0x1802d2979  lea     rcx, [rsp+1E8h+var_78]; void *
0x1802d2981  call    ??1?$shared_ptr@$$CBUProviderGroupInfo@Diagnostics@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(void)
0x1802d2986  cmp     [rsp+1E8h+var_E8], 0
0x1802d298e  jnz     short loc_1802D2A08
0x1802d2990  mov     rcx, [rsp+1E8h]; this
0x1802d2998  mov     ebx, 8000FFFFh
0x1802d299d  mov     r9d, ebx; char *
0x1802d29a0  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1802d29a7  mov     edx, 329h; void *
0x1802d29ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802d29b1  nop
0x1802d29b2  lea     rcx, [rsp+1E8h+var_100]
0x1802d29ba  call    ??1?$_Optional_destruct_base@VSqliteQueryResult@Diagnostics@Microsoft@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(void)
0x1802d29bf  nop
0x1802d29c0  lea     rcx, [rsp+1E8h+var_158]
0x1802d29c8  call    ??1?$_Optional_destruct_base@VSqliteQueryResult@Diagnostics@Microsoft@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(void)
0x1802d29cd  nop
0x1802d29ce  lea     rcx, [rsp+1E8h+var_178]
0x1802d29d3  call    ??1?$_Optional_destruct_base@VSqliteQueryResult@Diagnostics@Microsoft@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(void)
0x1802d29d8  nop
0x1802d29d9  lea     rcx, [rsp+1E8h+var_E0]; this
0x1802d29e1  call    ??1QueryTimeoutTracker@EventTranscriptManager@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::EventTranscriptManager::QueryTimeoutTracker::~QueryTimeoutTracker(void)
0x1802d29e6  nop
0x1802d29e7  mov     rcx, rdi; _Mtx_t
0x1802d29ea  call    cs:__imp__Mtx_unlock
0x1802d29f1  nop     dword ptr [rax+rax+00h]
0x1802d29f6  nop
0x1802d29f7  lea     rcx, [rsp+1E8h+var_1A8]
0x1802d29fc  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x1802d2a01  mov     eax, ebx
0x1802d2a03  jmp     loc_1802D2E0D
0x1802d2a08  lea     rcx, [rsp+1E8h+var_100]
0x1802d2a10  call    ??$Next@_K@SqliteQueryResult@Diagnostics@Microsoft@@QEAA_KXZ; Microsoft::Diagnostics::SqliteQueryResult::Next<unsigned __int64>(void)
0x1802d2a15  mov     [r12+8], rax
0x1802d2a1a  call    ?GetFileTimeAsULL@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL(void)
0x1802d2a1f  mov     r15, rax
0x1802d2a22  mov     rcx, 0FFFFFA7FD71BC000h
0x1802d2a2c  add     rcx, rax
0x1802d2a2f  mov     [rsp+1E8h+var_198], rcx
0x1802d2a34  lea     r8, [rsp+1E8h+var_198]
0x1802d2a39  lea     rdx, [rsp+1E8h+var_138]
0x1802d2a41  mov     rcx, [rbx+0A98h]
0x1802d2a48  call    ??$Bind@AEB_K@SqliteStatement@Diagnostics@Microsoft@@QEAA?AVSqliteBoundStatement@12@AEB_K@Z; Microsoft::Diagnostics::SqliteStatement::Bind<unsigned __int64 const &>(unsigned __int64 const &)
0x1802d2a4d  nop
0x1802d2a4e  lea     rdx, [rsp+1E8h+var_120]
0x1802d2a56  mov     rcx, rax
0x1802d2a59  call    ?Step@SqliteBoundStatement@Diagnostics@Microsoft@@QEAA?AV?$optional@VSqliteQueryResult@Diagnostics@Microsoft@@@std@@XZ; Microsoft::Diagnostics::SqliteBoundStatement::Step(void)
  ... truncated ...
```
