# Microsoft::Diagnostics::UtcApiManager::SnapMiniTrace(wchar_t const *)

- ea: `0x1801e1cd0`
- end: `0x1801e2405`
- name: `?SnapMiniTrace@UtcApiManager@Diagnostics@Microsoft@@UEAAJPEB_W@Z`
- size: `1845`
- prototype: `int(Microsoft::Diagnostics::UtcApiManager *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001bf4`
- `0x180002058`
- `0x18001d160`
- `0x180020fbc`
- `0x180026ecc`
- `0x180032718`
- `0x180048ff4`
- `0x18004ab70`
- `0x18004be40`
- `0x18005d050`
- `0x18006e7e4`
- `0x18007fae8`
- `0x1800862cc`
- `0x180086f40`
- `0x1800a0d08`
- `0x18012de40`
- `0x1801cc208`
- `0x1801d2b10`
- `0x1801ded08`
- `0x1801e1cd0`
- `0x18026189c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801e1e9f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801e1e9f`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1801e1dfe`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1801e1dfe`
- `RPCRT4!RpcRevertToSelf` at `0x1801e1d9c`
- `RPCRT4!RpcRevertToSelf` at `0x1801e1e58`
- `RPCRT4!RpcRevertToSelf` at `0x1801e1f31`
- `RPCRT4!RpcRevertToSelf` at `0x1801e2023`
- `RPCRT4!RpcRevertToSelf` at `0x1801e2106`
- `RPCRT4!RpcRevertToSelf` at `0x1801e21a2`
- `RPCRT4!RpcRevertToSelf` at `0x1801e2296`
- `RPCRT4!RpcRevertToSelf` at `0x1801e22ed`
- `RPCRT4!RpcRevertToSelf` at `0x1801e1d9c`
- `RPCRT4!RpcRevertToSelf` at `0x1801e1e58`
- `RPCRT4!RpcRevertToSelf` at `0x1801e1f31`
- `RPCRT4!RpcRevertToSelf` at `0x1801e2023`
- `RPCRT4!RpcRevertToSelf` at `0x1801e2106`
- `RPCRT4!RpcRevertToSelf` at `0x1801e21a2`
- `RPCRT4!RpcRevertToSelf` at `0x1801e2296`
- `RPCRT4!RpcRevertToSelf` at `0x1801e22ed`

## string_xrefs

- `0x1801e1d13`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e1d70`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e1e1e`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e1ef7`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e1fd2`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e20b5`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e2151`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e2245`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e233c`: `onecore\base\telemetry\utc\service\include\UtcApiManager.h`
- `0x1801e2356`: `onecore\base\telemetry\utc\service\include\UtcApiManager.h`
- `0x1801e2370`: `onecore\base\telemetry\utc\service\include\UtcApiManager.h`
- `0x1801e238a`: `onecore\base\telemetry\utc\service\include\UtcApiManager.h`
- `0x1801e23a4`: `onecore\base\telemetry\utc\service\include\UtcApiManager.h`
- `0x1801e23be`: `onecore\base\telemetry\utc\service\include\UtcApiManager.h`
- `0x1801e23d8`: `onecore\base\telemetry\utc\service\include\UtcApiManager.h`
- `0x1801e23f2`: `onecore\base\telemetry\utc\service\include\UtcApiManager.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::UtcApiManager::SnapMiniTrace(
        Microsoft::Diagnostics::UtcApiManager *this,
        const wchar_t *a2)
{
  const char *v4; // r9
  WCHAR *v5; // rcx
  const char *v6; // r9
  const WCHAR *v7; // rcx
  const char *v8; // r9
  int v9; // r8d
  int v10; // r9d
  PWSTR *v11; // rax
  unsigned int v12; // ebx
  const char *v13; // r9
  struct Microsoft::Diagnostics::TraceManager *TraceManager; // rdi
  int v15; // eax
  unsigned int v16; // ebx
  const char *v17; // r9
  int appended; // eax
  unsigned int v19; // ebx
  const char *v20; // r9
  __int128 v21; // xmm6
  int v22; // edx
  int v23; // eax
  unsigned int v24; // ebx
  const char *v25; // r9
  const char *v26; // r9
  unsigned int v27; // [rsp+20h] [rbp-E8h]
  int v28; // [rsp+20h] [rbp-E8h]
  char v29; // [rsp+41h] [rbp-C7h]
  PWSTR *v30; // [rsp+48h] [rbp-C0h] BYREF
  char v31; // [rsp+50h] [rbp-B8h]
  __int128 v32; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v33[4]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v34; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v35[16]; // [rsp+90h] [rbp-78h] BYREF
  PWSTR pszPathOut[3]; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int64 v37; // [rsp+B8h] [rbp-50h]
  _BYTE v38[16]; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v39; // [rsp+D0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  if ( a2 )
  {
    Microsoft::Diagnostics::UtcApiManager::ImpersonateRpcCaller(this);
    std::wstring::wstring(v38);
    if ( std::wstring::find_first_of(v38, 47, 0) == -1 )
    {
      std::wstring::wstring(pszPathOut, v39, 0);
      v5 = (WCHAR *)pszPathOut;
      if ( v37 > 7 )
        v5 = pszPathOut[0];
      if ( PathCchCanonicalizeEx(v5, (size_t)pszPathOut[2] + 1, a2, 1u) >= 0 )
      {
        Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)pszPathOut);
        v7 = (const WCHAR *)pszPathOut;
        if ( v37 > 7 )
          v7 = pszPathOut[0];
        if ( GetFileAttributesW(v7) == -1 )
        {
          if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x2000) )
          {
            v11 = pszPathOut;
            if ( v37 > 7 )
              v11 = (PWSTR *)pszPathOut[0];
            *(_QWORD *)v33 = v11;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
              (unsigned int)&dword_18042D328,
              (unsigned int)&unk_1803C99A0,
              v9,
              v10,
              (__int64)v33);
          }
          v30 = pszPathOut;
          v31 = 1;
          if ( _InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_18043BF60, 0, 0) )
          {
            TraceManager = Microsoft::Diagnostics::LifetimeManager::GetTraceManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
            *(_QWORD *)&v34 = *((_QWORD *)TraceManager + 4);
            *((_QWORD *)&v34 + 1) = (char *)TraceManager + 272;
            v32 = *(_OWORD *)&off_1803602D0;
            *(_OWORD *)v33 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPathOut, v35);
            v15 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v33, 0, &v32);
            v16 = v15;
            if ( v15 >= 0 )
            {
              v32 = *(_OWORD *)&Microsoft::Diagnostics::TraceSlot::k_traceSlotOutputNames;
              appended = Microsoft::Diagnostics::Utils::String::AppendPath((PWSTR)pszPathOut);
              v19 = appended;
              if ( appended >= 0 )
              {
                *(_QWORD *)&v32 = 0;
                BYTE8(v32) = 0;
                v21 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPathOut, v35);
                *(_QWORD *)v33 = Microsoft::Diagnostics::TraceSlotSafeWrapper::GetOwnerTraceProfileHash((Microsoft::Diagnostics::TraceSlotSafeWrapper *)&v34);
                v34 = v21;
                LOBYTE(v22) = 2;
                v23 = Microsoft::Diagnostics::TraceManager::SnapSlotTrace(
                        (_DWORD)TraceManager,
                        v22,
                        (unsigned int)&GUID_NULL,
                        (unsigned int)&GUID_NULL,
                        (__int64)v33,
                        (__int64)&v34,
                        0,
                        (__int64)&v32);
                v24 = v23;
                if ( v23 >= 0 )
                {
                  v31 = 0;
                  Microsoft::Diagnostics::UtcApiManager::SnapMiniTrace_::_3_::_lambda_1_::operator()(&v30);
                  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
                  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v38);
                  if ( v29 && RpcRevertToSelf() )
                    wil::details::in1diag3::_FailFast_Unexpected(
                      retaddr,
                      (void *)0x21E,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcApiManager.h",
                      v26);
                  return 0;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x6A,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
                    (const char *)(unsigned int)v23,
                    v28);
                  v31 = 0;
                  Microsoft::Diagnostics::UtcApiManager::SnapMiniTrace_::_3_::_lambda_1_::operator()(&v30);
                  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
                  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v38);
                  if ( v29 && RpcRevertToSelf() )
                    wil::details::in1diag3::_FailFast_Unexpected(
                      retaddr,
                      (void *)0x21E,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcApiManager.h",
                      v25);
                  return v24;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x62,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
                  (const char *)(unsigned int)appended,
                  v27);
                v31 = 0;
                Microsoft::Diagnostics::UtcApiManager::SnapMiniTrace_::_3_::_lambda_1_::operator()(&v30);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v38);
                if ( v29 && RpcRevertToSelf() )
                  wil::details::in1diag3::_FailFast_Unexpected(
                    retaddr,
                    (void *)0x21E,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcApiManager.h",
                    v20);
                return v19;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x61,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
                (const char *)(unsigned int)v15,
                v27);
              v31 = 0;
              Microsoft::Diagnostics::UtcApiManager::SnapMiniTrace_::_3_::_lambda_1_::operator()(&v30);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v38);
              if ( v29 && RpcRevertToSelf() )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x21E,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcApiManager.h",
                  v17);
              return v16;
            }
          }
          else
          {
            v12 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x5B,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
                    (const char *)0x15,
                    v27);
            v31 = 0;
            Microsoft::Diagnostics::UtcApiManager::SnapMiniTrace_::_3_::_lambda_1_::operator()(&v30);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v38);
            if ( v29 && RpcRevertToSelf() )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x21E,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcApiManager.h",
                v13);
            return v12;
          }
        }
        else
        {
          if ( (unsigned int)dword_18042D328 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x2000) )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              &dword_18042D328,
              &unk_1803C99DC);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x44,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
            (const char *)0x80070057LL,
            v27);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v38);
          if ( v29 && RpcRevertToSelf() )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x21E,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcApiManager.h",
              v8);
          return 2147942487LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x35,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          (const char *)0x80070057LL,
          v27);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v38);
        if ( v29 && RpcRevertToSelf() )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x21E,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcApiManager.h",
            v6);
        return 2147942487LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)0x80070057LL,
        v27);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v38);
      if ( v29 )
      {
        if ( RpcRevertToSelf() )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x21E,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcApiManager.h",
            v4);
      }
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v27);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1801e1cd0  mov     rax, rsp
0x1801e1cd3  mov     [rax+8], rbx
0x1801e1cd7  mov     [rax+18h], rsi
0x1801e1cdb  push    rdi
0x1801e1cdc  sub     rsp, 100h
0x1801e1ce3  movaps  xmmword ptr [rax-18h], xmm6
0x1801e1ce7  mov     rax, cs:__security_cookie
0x1801e1cee  xor     rax, rsp
0x1801e1cf1  mov     [rsp+108h+var_28], rax
0x1801e1cf9  mov     rbx, rdx
0x1801e1cfc  xor     esi, esi
0x1801e1cfe  test    rdx, rdx
0x1801e1d01  jnz     short loc_1801E1D29
0x1801e1d03  mov     rcx, [rsp+108h]; this
0x1801e1d0b  mov     ebx, 80070057h
0x1801e1d10  mov     r9d, ebx; char *
0x1801e1d13  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e1d1a  lea     edx, [rsi+22h]; void *
0x1801e1d1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e1d22  mov     eax, ebx
0x1801e1d24  jmp     loc_1801E2309
0x1801e1d29  lea     rdx, [rsp+108h+var_C8]
0x1801e1d2e  call    ?ImpersonateRpcCaller@UtcApiManager@Diagnostics@Microsoft@@AEAA@XZ; Microsoft::Diagnostics::UtcApiManager::ImpersonateRpcCaller(void)
0x1801e1d33  nop
0x1801e1d34  mov     rdx, rbx
0x1801e1d37  lea     rcx, [rsp+108h+var_48]
0x1801e1d3f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801e1d44  nop
0x1801e1d45  mov     edx, 2Fh ; '/'
0x1801e1d4a  xor     r8d, r8d
0x1801e1d4d  lea     rcx, [rsp+108h+var_48]
0x1801e1d55  call    ?find_first_of@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_K_W_K@Z; std::wstring::find_first_of(wchar_t,unsigned __int64)
0x1801e1d5a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801e1d5e  jz      short loc_1801E1DB7
0x1801e1d60  mov     rcx, [rsp+108h]; this
0x1801e1d68  mov     ebx, 80070057h
0x1801e1d6d  mov     r9d, ebx; char *
0x1801e1d70  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e1d77  mov     edx, 2Eh ; '.'; void *
0x1801e1d7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e1d81  nop
0x1801e1d82  lea     rcx, [rsp+108h+var_48]; this
0x1801e1d8a  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e1d8f  nop
0x1801e1d90  cmp     [rsp+108h+var_C8+1], sil
0x1801e1d95  jz      short loc_1801E1DB0
0x1801e1d97  mov     [rsp+108h+var_C8+1], sil
0x1801e1d9c  call    cs:__imp_RpcRevertToSelf
0x1801e1da3  nop     dword ptr [rax+rax+00h]
0x1801e1da8  test    eax, eax
0x1801e1daa  jnz     loc_1801E2334
0x1801e1db0  mov     eax, ebx
0x1801e1db2  jmp     loc_1801E2309
0x1801e1db7  xor     r8d, r8d
0x1801e1dba  mov     rdx, [rsp+108h+var_38]
0x1801e1dc2  lea     rcx, [rsp+108h+pszPathOut]
0x1801e1dca  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x1801e1dcf  nop
0x1801e1dd0  mov     rdx, [rsp+108h+var_58]
0x1801e1dd8  lea     rcx, [rsp+108h+pszPathOut]
0x1801e1de0  cmp     [rsp+108h+var_50], 7
0x1801e1de9  cmova   rcx, [rsp+108h+pszPathOut]; pszPathOut
0x1801e1df2  inc     rdx; cchPathOut
0x1801e1df5  mov     r9d, 1; dwFlags
0x1801e1dfb  mov     r8, rbx; pszPathIn
0x1801e1dfe  call    cs:__imp_PathCchCanonicalizeEx
0x1801e1e05  nop     dword ptr [rax+rax+00h]
0x1801e1e0a  test    eax, eax
0x1801e1e0c  jns     short loc_1801E1E73
0x1801e1e0e  mov     rcx, [rsp+108h]; this
0x1801e1e16  mov     ebx, 80070057h
0x1801e1e1b  mov     r9d, ebx; char *
0x1801e1e1e  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e1e25  mov     edx, 35h ; '5'; void *
0x1801e1e2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e1e2f  nop
0x1801e1e30  lea     rcx, [rsp+108h+pszPathOut]; this
0x1801e1e38  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e1e3d  nop
0x1801e1e3e  lea     rcx, [rsp+108h+var_48]; this
0x1801e1e46  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e1e4b  nop
0x1801e1e4c  cmp     [rsp+108h+var_C8+1], sil
0x1801e1e51  jz      short loc_1801E1E6C
0x1801e1e53  mov     [rsp+108h+var_C8+1], sil
0x1801e1e58  call    cs:__imp_RpcRevertToSelf
0x1801e1e5f  nop     dword ptr [rax+rax+00h]
0x1801e1e64  test    eax, eax
0x1801e1e66  jnz     loc_1801E234E
0x1801e1e6c  mov     eax, ebx
0x1801e1e6e  jmp     loc_1801E2309
0x1801e1e73  xor     r8d, r8d
0x1801e1e76  mov     dl, 1
0x1801e1e78  lea     rcx, [rsp+108h+pszPathOut]; lpSrc
0x1801e1e80  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x1801e1e85  lea     rcx, [rsp+108h+pszPathOut]
0x1801e1e8d  cmp     [rsp+108h+var_50], 7
0x1801e1e96  cmova   rcx, [rsp+108h+pszPathOut]; lpFileName
0x1801e1e9f  call    cs:__imp_GetFileAttributesW
0x1801e1ea6  nop     dword ptr [rax+rax+00h]
0x1801e1eab  cmp     eax, 0FFFFFFFFh
0x1801e1eae  mov     eax, cs:dword_18042D328
0x1801e1eb4  jz      loc_1801E1F4C
0x1801e1eba  cmp     eax, 3
0x1801e1ebd  jbe     short loc_1801E1EE7
0x1801e1ebf  mov     edx, 2000h
0x1801e1ec4  lea     rcx, dword_18042D328
0x1801e1ecb  call    _tlgKeywordOn
0x1801e1ed0  test    al, al
0x1801e1ed2  jz      short loc_1801E1EE7
0x1801e1ed4  lea     rdx, unk_1803C99DC
0x1801e1edb  lea     rcx, dword_18042D328
0x1801e1ee2  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801e1ee7  mov     rcx, [rsp+108h]; this
0x1801e1eef  mov     ebx, 80070057h
0x1801e1ef4  mov     r9d, ebx; char *
0x1801e1ef7  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e1efe  mov     edx, 44h ; 'D'; void *
0x1801e1f03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e1f08  nop
0x1801e1f09  lea     rcx, [rsp+108h+pszPathOut]; this
0x1801e1f11  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e1f16  nop
0x1801e1f17  lea     rcx, [rsp+108h+var_48]; this
0x1801e1f1f  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e1f24  nop
0x1801e1f25  cmp     [rsp+108h+var_C8+1], sil
0x1801e1f2a  jz      short loc_1801E1F45
0x1801e1f2c  mov     [rsp+108h+var_C8+1], sil
0x1801e1f31  call    cs:__imp_RpcRevertToSelf
0x1801e1f38  nop     dword ptr [rax+rax+00h]
0x1801e1f3d  test    eax, eax
0x1801e1f3f  jnz     loc_1801E2368
0x1801e1f45  mov     eax, ebx
0x1801e1f47  jmp     loc_1801E2309
0x1801e1f4c  cmp     eax, 4
0x1801e1f4f  jbe     short loc_1801E1FA2
0x1801e1f51  mov     edx, 2000h
0x1801e1f56  lea     rcx, dword_18042D328
0x1801e1f5d  call    _tlgKeywordOn
0x1801e1f62  test    al, al
0x1801e1f64  jz      short loc_1801E1FA2
0x1801e1f66  lea     rax, [rsp+108h+pszPathOut]
0x1801e1f6e  cmp     [rsp+108h+var_50], 7
0x1801e1f77  cmova   rax, [rsp+108h+pszPathOut]
0x1801e1f80  mov     qword ptr [rsp+108h+var_98], rax
0x1801e1f85  lea     rax, [rsp+108h+var_98]
0x1801e1f8a  mov     qword ptr [rsp+108h+var_E8], rax; int
0x1801e1f8f  lea     rdx, unk_1803C99A0
0x1801e1f96  lea     rcx, dword_18042D328
0x1801e1f9d  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1801e1fa2  lea     rax, [rsp+108h+pszPathOut]
0x1801e1faa  mov     [rsp+108h+var_C0], rax
0x1801e1faf  mov     [rsp+108h+var_B8], 1
0x1801e1fb4  mov     rcx, rsi
0x1801e1fb7  xor     eax, eax
0x1801e1fb9  lock cmpxchg qword ptr cs:xmmword_18043BF60, rcx
0x1801e1fc2  jnz     short loc_1801E203E
0x1801e1fc4  mov     rcx, [rsp+108h]; this
0x1801e1fcc  mov     r9d, 15h; char *
0x1801e1fd2  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e1fd9  lea     edx, [r9+46h]; void *
0x1801e1fdd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801e1fe2  mov     ebx, eax
0x1801e1fe4  cmp     [rsp+108h+var_B8], sil
0x1801e1fe9  jz      short loc_1801E1FFB
0x1801e1feb  mov     [rsp+108h+var_B8], sil
0x1801e1ff0  lea     rcx, [rsp+108h+var_C0]
0x1801e1ff5  call    _Microsoft__Diagnostics__UtcApiManager__SnapMiniTrace____3____lambda_1___operator__
0x1801e1ffa  nop
0x1801e1ffb  lea     rcx, [rsp+108h+pszPathOut]; this
0x1801e2003  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e2008  nop
0x1801e2009  lea     rcx, [rsp+108h+var_48]; this
0x1801e2011  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e2016  nop
0x1801e2017  cmp     [rsp+108h+var_C8+1], sil
0x1801e201c  jz      short loc_1801E2037
0x1801e201e  mov     [rsp+108h+var_C8+1], sil
0x1801e2023  call    cs:__imp_RpcRevertToSelf
0x1801e202a  nop     dword ptr [rax+rax+00h]
0x1801e202f  test    eax, eax
0x1801e2031  jnz     loc_1801E2382
0x1801e2037  mov     eax, ebx
0x1801e2039  jmp     loc_1801E2309
0x1801e203e  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1801e2045  call    ?GetTraceManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTraceManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTraceManager(void)
0x1801e204a  mov     rdi, rax
0x1801e204d  mov     rcx, [rax+20h]
0x1801e2051  mov     qword ptr [rsp+108h+var_88], rcx
0x1801e2059  lea     rcx, [rax+110h]
0x1801e2060  mov     qword ptr [rsp+108h+var_88+8], rcx
0x1801e2068  movups  xmm0, xmmword ptr cs:off_1803602D0; "O:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;;S-1"...
0x1801e206f  movdqu  [rsp+108h+var_A8], xmm0
0x1801e2075  lea     rdx, [rsp+108h+var_78]
0x1801e207d  lea     rcx, [rsp+108h+pszPathOut]
0x1801e2085  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801e208a  movups  xmm0, xmmword ptr [rax]
0x1801e208d  movdqu  xmmword ptr [rsp+108h+var_98], xmm0
0x1801e2093  lea     r8, [rsp+108h+var_A8]
0x1801e2098  xor     edx, edx
0x1801e209a  lea     rcx, [rsp+108h+var_98]
0x1801e209f  call    ?ExpandAndCreateDirectory@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N0@Z; Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(std::wstring_view,bool,std::wstring_view)
0x1801e20a4  mov     ebx, eax
0x1801e20a6  test    eax, eax
0x1801e20a8  jns     short loc_1801E2121
0x1801e20aa  mov     rcx, [rsp+108h]; this
0x1801e20b2  mov     r9d, eax; char *
0x1801e20b5  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e20bc  mov     edx, 61h ; 'a'; void *
0x1801e20c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e20c6  nop
0x1801e20c7  cmp     [rsp+108h+var_B8], sil
0x1801e20cc  jz      short loc_1801E20DE
0x1801e20ce  mov     [rsp+108h+var_B8], sil
0x1801e20d3  lea     rcx, [rsp+108h+var_C0]
0x1801e20d8  call    _Microsoft__Diagnostics__UtcApiManager__SnapMiniTrace____3____lambda_1___operator__
0x1801e20dd  nop
0x1801e20de  lea     rcx, [rsp+108h+pszPathOut]; this
0x1801e20e6  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e20eb  nop
0x1801e20ec  lea     rcx, [rsp+108h+var_48]; this
0x1801e20f4  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e20f9  nop
0x1801e20fa  cmp     [rsp+108h+var_C8+1], sil
0x1801e20ff  jz      short loc_1801E211A
0x1801e2101  mov     [rsp+108h+var_C8+1], sil
0x1801e2106  call    cs:__imp_RpcRevertToSelf
0x1801e210d  nop     dword ptr [rax+rax+00h]
0x1801e2112  test    eax, eax
0x1801e2114  jnz     loc_1801E239C
0x1801e211a  mov     eax, ebx
0x1801e211c  jmp     loc_1801E2309
0x1801e2121  movaps  xmm0, xmmword ptr cs:?k_traceSlotOutputNames@TraceSlot@Diagnostics@Microsoft@@2QBV?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const near * const Microsoft::Diagnostics::TraceSlot::k_traceSlotOutputNames
0x1801e2128  movdqu  [rsp+108h+var_A8], xmm0
0x1801e212e  lea     rdx, [rsp+108h+var_A8]
0x1801e2133  lea     rcx, [rsp+108h+pszPathOut]; pszPath
0x1801e213b  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x1801e2140  mov     ebx, eax
0x1801e2142  test    eax, eax
0x1801e2144  jns     short loc_1801E21BD
0x1801e2146  mov     rcx, [rsp+108h]; this
0x1801e214e  mov     r9d, eax; char *
0x1801e2151  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e2158  mov     edx, 62h ; 'b'; void *
0x1801e215d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e2162  nop
0x1801e2163  cmp     [rsp+108h+var_B8], sil
0x1801e2168  jz      short loc_1801E217A
0x1801e216a  mov     [rsp+108h+var_B8], sil
0x1801e216f  lea     rcx, [rsp+108h+var_C0]
0x1801e2174  call    _Microsoft__Diagnostics__UtcApiManager__SnapMiniTrace____3____lambda_1___operator__
0x1801e2179  nop
0x1801e217a  lea     rcx, [rsp+108h+pszPathOut]; this
0x1801e2182  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e2187  nop
0x1801e2188  lea     rcx, [rsp+108h+var_48]; this
0x1801e2190  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e2195  nop
0x1801e2196  cmp     [rsp+108h+var_C8+1], sil
0x1801e219b  jz      short loc_1801E21B6
0x1801e219d  mov     [rsp+108h+var_C8+1], sil
0x1801e21a2  call    cs:__imp_RpcRevertToSelf
0x1801e21a9  nop     dword ptr [rax+rax+00h]
0x1801e21ae  test    eax, eax
0x1801e21b0  jnz     loc_1801E23B6
0x1801e21b6  mov     eax, ebx
0x1801e21b8  jmp     loc_1801E2309
0x1801e21bd  mov     qword ptr [rsp+108h+var_A8], rsi
0x1801e21c2  mov     byte ptr [rsp+108h+var_A8+8], sil
0x1801e21c7  lea     rdx, [rsp+108h+var_78]
0x1801e21cf  lea     rcx, [rsp+108h+pszPathOut]
0x1801e21d7  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801e21dc  movups  xmm6, xmmword ptr [rax]
0x1801e21df  lea     rcx, [rsp+108h+var_88]; this
0x1801e21e7  call    ?GetOwnerTraceProfileHash@TraceSlotSafeWrapper@Diagnostics@Microsoft@@QEBA_KXZ; Microsoft::Diagnostics::TraceSlotSafeWrapper::GetOwnerTraceProfileHash(void)
0x1801e21ec  mov     qword ptr [rsp+108h+var_98], rax
0x1801e21f1  movdqu  [rsp+108h+var_88], xmm6
0x1801e21fa  lea     rax, [rsp+108h+var_A8]
0x1801e21ff  mov     [rsp+108h+var_D0], rax
0x1801e2204  mov     [rsp+108h+var_D8], rsi
0x1801e2209  lea     rax, [rsp+108h+var_88]
0x1801e2211  mov     [rsp+108h+var_E0], rax
0x1801e2216  lea     rax, [rsp+108h+var_98]
0x1801e221b  mov     qword ptr [rsp+108h+var_E8], rax; int
0x1801e2220  lea     r8, GUID_NULL
0x1801e2227  mov     r9, r8
0x1801e222a  mov     dl, 2
0x1801e222c  mov     rcx, rdi
0x1801e222f  call    ?SnapSlotTrace@TraceManager@Diagnostics@Microsoft@@QEAAJVTraceSlotType@23@AEBU_GUID@@1AEB_KV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_KAEBUSnapTraceMetadata@23@@Z; Microsoft::Diagnostics::TraceManager::SnapSlotTrace(Microsoft::Diagnostics::TraceSlotType,_GUID const &,_GUID const &,unsigned __int64 const &,std::wstring_view,unsigned __int64,Microsoft::Diagnostics::SnapTraceMetadata const &)
0x1801e2234  mov     ebx, eax
0x1801e2236  test    eax, eax
0x1801e2238  jns     short loc_1801E22AE
0x1801e223a  mov     rcx, [rsp+108h]; this
0x1801e2242  mov     r9d, eax; char *
0x1801e2245  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e224c  mov     edx, 6Ah ; 'j'; void *
0x1801e2251  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e2256  nop
0x1801e2257  cmp     [rsp+108h+var_B8], sil
  ... truncated ...
```
