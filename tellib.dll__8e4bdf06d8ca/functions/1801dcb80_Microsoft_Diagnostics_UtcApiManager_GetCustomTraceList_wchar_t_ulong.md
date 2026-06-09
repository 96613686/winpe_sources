# Microsoft::Diagnostics::UtcApiManager::GetCustomTraceList(wchar_t * * *,ulong *)

- ea: `0x1801dcb80`
- end: `0x1801dd2ad`
- name: `?GetCustomTraceList@UtcApiManager@Diagnostics@Microsoft@@UEAAJPEAPEAPEA_WPEAK@Z`
- size: `1837`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UtcApiManager *__hidden this, wchar_t ***, unsigned int *)`
- caller_count: `0`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002058`
- `0x18001d160`
- `0x180020fbc`
- `0x180026ecc`
- `0x180027be0`
- `0x18003352c`
- `0x180033f3c`
- `0x180035698`
- `0x180048ff4`
- `0x1800498f0`
- `0x18004ab70`
- `0x1800558c0`
- `0x18005af1c`
- `0x18005d050`
- `0x180080054`
- `0x180081a4c`
- `0x1800a0d08`
- `0x1800b83bc`
- `0x1800d0d9c`
- `0x1800d3f44`
- `0x18012de40`
- `0x18012eaf0`
- `0x18012eb08`
- `0x18012fab8`
- `0x180130b0c`
- `0x1801cfb18`
- `0x1801d1518`
- `0x1801d2ee0`
- `0x1801dcb80`
- `0x1801ded08`
- `0x180346010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801dcc42`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801dce42`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801dcf99`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801dcc42`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801dce42`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801dcf99`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1801dcd9d`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1801dcd9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801dcd6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801dcd6a`
- `RPCRT4!RpcRevertToSelf` at `0x1801dcf77`
- `RPCRT4!RpcRevertToSelf` at `0x1801dcf77`

## string_xrefs

- `0x1801dcdb7`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801dd0e6`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801dd1fb`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801dd252`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801dd29b`: `onecore\base\telemetry\utc\service\include\UtcApiManager.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Microsoft::Diagnostics::UtcApiManager::GetCustomTraceList(
        Microsoft::Diagnostics::UtcApiManager *this,
        wchar_t ***a2,
        unsigned int *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  const WCHAR *v7; // rcx
  DWORD FileAttributesW; // eax
  int v9; // r8d
  int v10; // r9d
  _QWORD *v11; // rax
  _QWORD *v12; // rdx
  void *v13; // rbx
  HRESULT v14; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  const WCHAR *v17; // rcx
  DWORD v18; // eax
  Microsoft::Diagnostics::UtcApiManager *v19; // rcx
  int v20; // r8d
  int v21; // r9d
  _QWORD *v22; // rax
  _QWORD *v23; // rdx
  const char *v24; // r9
  const WCHAR *v25; // rcx
  DWORD v26; // eax
  int v27; // r8d
  int v28; // r9d
  _QWORD *v29; // rax
  _QWORD *v30; // rdx
  const void **v31; // rbx
  const void **v32; // rdi
  unsigned __int64 v33; // rbx
  wchar_t **v34; // rax
  __int64 v35; // rsi
  unsigned __int64 v36; // r14
  wchar_t *v37; // rax
  wchar_t *v38; // rcx
  const void *v39; // rdx
  int v41; // [rsp+20h] [rbp-E0h]
  int v42[4]; // [rsp+30h] [rbp-D0h] BYREF
  char v43; // [rsp+41h] [rbp-BFh]
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t **v45; // [rsp+50h] [rbp-B0h] BYREF
  void *Src[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v47; // [rsp+68h] [rbp-98h]
  _BYTE v48[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v49[64]; // [rsp+80h] [rbp-80h] BYREF
  char v50; // [rsp+C0h] [rbp-40h]
  LPCWSTR lpFileName[3]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v52; // [rsp+E0h] [rbp-20h]
  _QWORD v53[3]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v54; // [rsp+100h] [rbp+0h]
  _QWORD v55[2]; // [rsp+108h] [rbp+8h] BYREF
  char v56; // [rsp+118h] [rbp+18h]
  _OWORD v57[2]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v58[7]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD *v59; // [rsp+188h] [rbp+88h]
  _QWORD v60[7]; // [rsp+190h] [rbp+90h] BYREF
  Microsoft::Diagnostics::UtcApiManager *v61; // [rsp+1C8h] [rbp+C8h]
  _QWORD v62[7]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD *v63; // [rsp+208h] [rbp+108h]
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  *(_QWORD *)v42 = 60000;
  std::unique_lock<std::recursive_timed_mutex>::unique_lock<std::recursive_timed_mutex>(v48, (char *)this + 384, v42);
  if ( !v48[8] )
  {
    v5 = -2017128405;
    v6 = 2973;
LABEL_62:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)v5,
      v41);
    goto LABEL_63;
  }
  if ( !a2 || !a3 )
  {
    v5 = -2147024809;
    v6 = 2978;
    goto LABEL_62;
  }
  std::wstring::wstring(v53);
  *(_OWORD *)Src = 0;
  v47 = 0;
  std::wstring::wstring((__int64)lpFileName, &off_1803601B0);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(lpFileName, 1, 0);
  v7 = (const WCHAR *)lpFileName;
  if ( v52 > 7 )
    v7 = lpFileName[0];
  FileAttributesW = GetFileAttributesW(v7);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
  {
    std::wstring::operator=(v53, lpFileName);
    if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x2000) )
    {
      v11 = v53;
      if ( v54 > 7 )
        v11 = (_QWORD *)v53[0];
      *(_QWORD *)v42 = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        (unsigned int)&dword_18042D328,
        (unsigned int)&unk_1803C8816,
        v9,
        v10,
        (__int64)v42);
    }
    v50 = 0;
    v58[0] = off_1803570A8;
    v58[1] = Src;
    v59 = v58;
    *(_OWORD *)v42 = *(_OWORD *)&Microsoft::Diagnostics::UtcApiManager::k_customProfilesFilePattern;
    v57[0] = *(_OWORD *)std::wstring::operator std::wstring_view(v53, v55);
    Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileInPattern(v57, v42, v58, v49);
    if ( v59 )
    {
      v12 = v58;
      LOBYTE(v12) = v59 != v58;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v59 + 32LL))(v59, v12);
    }
  }
  pv = 0;
  if ( (unsigned __int8)IsSHGetKnownFolderPathPresent() )
  {
    v13 = pv;
    if ( pv )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v42);
      CoTaskMemFree(v13);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v42);
    }
    pv = 0;
    v14 = SHGetKnownFolderPath(&FOLDERID_PublicDocuments, 0x8000u, 0, (PWSTR *)&pv);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBC3,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)(unsigned int)v14,
        v41);
  }
  if ( pv )
  {
    v15 = std::wstring::wstring(v57);
    v16 = std::operator+<wchar_t>(v55, v15, L"\\FeedbackHub\\CustomTraceProfiles");
    std::wstring::operator=(lpFileName, v16);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
  }
  else
  {
    std::wstring::_Assign<wchar_t>(
      (char **)lpFileName,
      L"%Public%\\Documents\\FeedbackHub\\CustomTraceProfiles",
      (char *)0x32);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(lpFileName, 1, 0);
  }
  v17 = (const WCHAR *)lpFileName;
  if ( v52 > 7 )
    v17 = lpFileName[0];
  v18 = GetFileAttributesW(v17);
  if ( v18 != -1 && (v18 & 0x10) != 0 )
  {
    std::wstring::operator=(v53, lpFileName);
    if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x2000) )
    {
      v22 = v53;
      if ( v54 > 7 )
        v22 = (_QWORD *)v53[0];
      *(_QWORD *)v42 = v22;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        (unsigned int)&dword_18042D328,
        (unsigned int)&unk_1803C87C3,
        v20,
        v21,
        (__int64)v42);
    }
    v50 = 0;
    v60[0] = off_1803570D8;
    v60[1] = Src;
    v61 = (Microsoft::Diagnostics::UtcApiManager *)v60;
    v57[0] = *(_OWORD *)&Microsoft::Diagnostics::UtcApiManager::k_customProfilesFilePattern;
    *(_OWORD *)v42 = *(_OWORD *)std::wstring::operator std::wstring_view(v53, v55);
    Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileInPattern(v42, v57, v60, v49);
    v19 = v61;
    if ( v61 )
    {
      v23 = v60;
      LOBYTE(v23) = v61 != (Microsoft::Diagnostics::UtcApiManager *)v60;
      (*(void (__fastcall **)(Microsoft::Diagnostics::UtcApiManager *, _QWORD *))(*(_QWORD *)v61 + 32LL))(v61, v23);
    }
  }
  Microsoft::Diagnostics::UtcApiManager::ImpersonateRpcCaller(v19);
  std::wstring::_Assign<wchar_t>(
    (char **)lpFileName,
    L"%USERPROFILE%\\Documents\\FeedbackHub\\CustomTraceProfiles",
    (char *)0x37);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(lpFileName, 1, 0);
  if ( v43 && RpcRevertToSelf() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x21E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcApiManager.h",
      v24);
  v25 = (const WCHAR *)lpFileName;
  if ( v52 > 7 )
    v25 = lpFileName[0];
  v26 = GetFileAttributesW(v25);
  if ( v26 != -1 && (v26 & 0x10) != 0 )
  {
    std::wstring::operator=(v53, lpFileName);
    if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x2000) )
    {
      v29 = v53;
      if ( v54 > 7 )
        v29 = (_QWORD *)v53[0];
      *(_QWORD *)v42 = v29;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        (unsigned int)&dword_18042D328,
        (unsigned int)&unk_1803C86FD,
        v27,
        v28,
        (__int64)v42);
    }
    v50 = 0;
    v62[0] = off_180357018;
    v62[1] = Src;
    v63 = v62;
    v57[0] = *(_OWORD *)&Microsoft::Diagnostics::UtcApiManager::k_customProfilesFilePattern;
    *(_OWORD *)v42 = *(_OWORD *)std::wstring::operator std::wstring_view(v53, v55);
    Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileInPattern(v42, v57, v62, v49);
    if ( v63 )
    {
      v30 = v62;
      LOBYTE(v30) = v63 != v62;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v63 + 32LL))(v63, v30);
    }
  }
  v45 = 0;
  v31 = (const void **)Src[1];
  v32 = (const void **)Src[0];
  if ( Src[0] == Src[1] )
    goto LABEL_58;
  v33 = 8 * (((char *)Src[1] - (char *)Src[0]) >> 5);
  v34 = (wchar_t **)operator new[](v33, (const struct std::nothrow_t *)&std::nothrow);
  v45 = v34;
  if ( v34 )
  {
    memset_0(v34, 0, v33);
    v55[0] = Src;
    v55[1] = &v45;
    v56 = 1;
    v35 = 0;
    v32 = (const void **)Src[0];
    v31 = (const void **)Src[1];
    if ( Src[0] != Src[1] )
    {
      while ( 1 )
      {
        v36 = 2LL * (_QWORD)v32[2] + 2;
        v37 = (wchar_t *)operator new[](v36, (const struct std::nothrow_t *)&std::nothrow);
        v45[v35] = v37;
        v38 = v45[v35];
        if ( !v38 )
          break;
        if ( (unsigned __int64)v32[3] <= 7 )
          v39 = v32;
        else
          v39 = *v32;
        memcpy_0(v38, v39, v36);
        v35 = (unsigned int)(v35 + 1);
        v32 += 4;
        if ( v32 == v31 )
        {
          v31 = (const void **)Src[1];
          v32 = (const void **)Src[0];
          goto LABEL_58;
        }
      }
      v5 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC28,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)0x8007000ELL,
        v41);
      v56 = 0;
      Microsoft::Diagnostics::UtcApiManager::GetCustomTraceList_::_54_::_lambda_4_::operator()(v55);
      goto LABEL_60;
    }
LABEL_58:
    *a2 = v45;
    v45 = 0;
    *a3 = ((char *)v31 - (char *)v32) >> 5;
    __1__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(&pv);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
    std::vector<std::wstring>::_Tidy(Src);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v53);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v48);
    return 0;
  }
  v5 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC0B,
    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
    (const char *)0x8007000ELL,
    v41);
LABEL_60:
  __1__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(&pv);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
  std::vector<std::wstring>::_Tidy(Src);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v53);
LABEL_63:
  std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v48);
  return v5;
}

```

## disassembly

```asm
0x1801dcb80  push    rbp
0x1801dcb82  push    rbx
0x1801dcb83  push    rsi
0x1801dcb84  push    rdi
0x1801dcb85  push    r12
0x1801dcb87  push    r14
0x1801dcb89  push    r15
0x1801dcb8b  lea     rbp, [rsp-120h]
0x1801dcb93  sub     rsp, 220h
0x1801dcb9a  mov     rax, cs:__security_cookie
0x1801dcba1  xor     rax, rsp
0x1801dcba4  mov     [rbp+150h+var_40], rax
0x1801dcbab  mov     r12, r8
0x1801dcbae  mov     r15, rdx
0x1801dcbb1  mov     qword ptr [rsp+250h+var_220], 0EA60h
0x1801dcbba  lea     rdx, [rcx+180h]
0x1801dcbc1  lea     r8, [rsp+250h+var_220]
0x1801dcbc6  lea     rcx, [rsp+250h+var_1E0]
0x1801dcbcb  call    ??$?0_JU?$ratio@$00$0DOI@@std@@@?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@AEAVrecursive_timed_mutex@1@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::unique_lock<std::recursive_timed_mutex>::unique_lock<std::recursive_timed_mutex>(std::recursive_timed_mutex &,std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x1801dcbd0  nop
0x1801dcbd1  cmp     [rsp+250h+var_1D8], 0
0x1801dcbd6  jnz     short loc_1801DCBE7
0x1801dcbd8  mov     ebx, 87C5102Bh
0x1801dcbdd  mov     edx, 0B9Dh
0x1801dcbe2  jmp     loc_1801DD24F
0x1801dcbe7  test    r15, r15
0x1801dcbea  jz      loc_1801DD245
0x1801dcbf0  test    r12, r12
0x1801dcbf3  jz      loc_1801DD245
0x1801dcbf9  lea     rcx, [rbp+150h+var_168]; void *
0x1801dcbfd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801dcc02  nop
0x1801dcc03  xorps   xmm0, xmm0
0x1801dcc06  movdqu  xmmword ptr [rsp+250h+Src], xmm0
0x1801dcc0c  mov     [rsp+250h+var_1E8], 0
0x1801dcc15  lea     rdx, off_1803601B0; "%DiagtrackStorageRoot%\\CustomTraceProf"...
0x1801dcc1c  lea     rcx, [rbp+150h+lpFileName]
0x1801dcc20  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1801dcc25  nop
0x1801dcc26  xor     r8d, r8d
0x1801dcc29  mov     dl, 1
0x1801dcc2b  lea     rcx, [rbp+150h+lpFileName]; lpSrc
0x1801dcc2f  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x1801dcc34  lea     rcx, [rbp+150h+lpFileName]
0x1801dcc38  cmp     [rbp+150h+var_170], 7
0x1801dcc3d  cmova   rcx, [rbp+150h+lpFileName]; lpFileName
0x1801dcc42  call    cs:__imp_GetFileAttributesW
0x1801dcc49  nop     dword ptr [rax+rax+00h]
0x1801dcc4e  mov     sil, 10h
0x1801dcc51  mov     r14d, 2000h
0x1801dcc57  lea     rdi, dword_18042D328
0x1801dcc5e  cmp     eax, 0FFFFFFFFh
0x1801dcc61  jz      loc_1801DCD41
0x1801dcc67  test    sil, al
0x1801dcc6a  jz      loc_1801DCD41
0x1801dcc70  lea     rdx, [rbp+150h+lpFileName]
0x1801dcc74  lea     rcx, [rbp+150h+var_168]
0x1801dcc78  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801dcc7d  mov     eax, cs:dword_18042D328
0x1801dcc83  cmp     eax, 4
0x1801dcc86  jbe     short loc_1801DCCC3
0x1801dcc88  mov     edx, r14d
0x1801dcc8b  mov     rcx, rdi
0x1801dcc8e  call    _tlgKeywordOn
0x1801dcc93  test    al, al
0x1801dcc95  jz      short loc_1801DCCC3
0x1801dcc97  lea     rax, [rbp+150h+var_168]
0x1801dcc9b  cmp     [rbp+150h+var_150], 7
0x1801dcca0  cmova   rax, [rbp+150h+var_168]
0x1801dcca5  mov     qword ptr [rsp+250h+var_220], rax
0x1801dccaa  lea     rax, [rsp+250h+var_220]
0x1801dccaf  mov     qword ptr [rsp+250h+var_230], rax; int
0x1801dccb4  lea     rdx, unk_1803C8816
0x1801dccbb  mov     rcx, rdi
0x1801dccbe  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1801dccc3  mov     [rbp+150h+var_190], 0
0x1801dccc7  lea     rax, off_1803570A8
0x1801dccce  mov     [rbp+150h+var_100], rax
0x1801dccd2  lea     rax, [rsp+250h+Src]
0x1801dccd7  mov     [rbp+150h+var_F8], rax
0x1801dccdb  lea     rax, [rbp+150h+var_100]
0x1801dccdf  mov     [rbp+150h+var_C8], rax
0x1801dcce6  movups  xmm0, xmmword ptr cs:?k_customProfilesFilePattern@UtcApiManager@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::UtcApiManager::k_customProfilesFilePattern
0x1801dcced  movdqu  xmmword ptr [rsp+250h+var_220], xmm0
0x1801dccf3  lea     rdx, [rbp+150h+var_148]
0x1801dccf7  lea     rcx, [rbp+150h+var_168]
0x1801dccfb  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801dcd00  movups  xmm0, xmmword ptr [rax]
0x1801dcd03  movdqu  [rbp+150h+var_120], xmm0
0x1801dcd08  lea     r9, [rbp+150h+var_1D0]
0x1801dcd0c  lea     r8, [rbp+150h+var_100]
0x1801dcd10  lea     rdx, [rsp+250h+var_220]
0x1801dcd15  lea     rcx, [rbp+150h+var_120]
0x1801dcd19  call    ?DoForEachFileInPattern@FileSystem@Utils@Diagnostics@Microsoft@@SAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBV?$function@$$A6A_NAEBVAutoFindFile@@@Z@6@V?$optional@V?$function@$$A6A_NJ@Z@std@@@6@@Z; Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileInPattern(std::wstring_view,std::wstring_view,std::function<bool (AutoFindFile const &)> const &,std::optional<std::function<bool (long)>>)
0x1801dcd1e  nop
0x1801dcd1f  mov     rcx, [rbp+150h+var_C8]
0x1801dcd26  test    rcx, rcx
0x1801dcd29  jz      short loc_1801DCD41
0x1801dcd2b  mov     rax, [rcx]
0x1801dcd2e  lea     rdx, [rbp+150h+var_100]
0x1801dcd32  cmp     rcx, rdx
0x1801dcd35  setnz   dl
0x1801dcd38  mov     rax, [rax+20h]
0x1801dcd3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dcd41  mov     [rsp+250h+pv], 0
0x1801dcd4a  call    IsSHGetKnownFolderPathPresent
0x1801dcd4f  test    al, al
0x1801dcd51  jz      short loc_1801DCDC8
0x1801dcd53  mov     rbx, [rsp+250h+pv]
0x1801dcd58  test    rbx, rbx
0x1801dcd5b  jz      short loc_1801DCD80
0x1801dcd5d  lea     rcx, [rsp+250h+var_220]; this
0x1801dcd62  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801dcd67  mov     rcx, rbx; pv
0x1801dcd6a  call    cs:__imp_CoTaskMemFree
0x1801dcd71  nop     dword ptr [rax+rax+00h]
0x1801dcd76  lea     rcx, [rsp+250h+var_220]; this
0x1801dcd7b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801dcd80  mov     [rsp+250h+pv], 0
0x1801dcd89  lea     r9, [rsp+250h+pv]; ppszPath
0x1801dcd8e  xor     r8d, r8d; hToken
0x1801dcd91  mov     edx, 8000h; dwFlags
0x1801dcd96  lea     rcx, FOLDERID_PublicDocuments; rfid
0x1801dcd9d  call    cs:__imp_SHGetKnownFolderPath
0x1801dcda4  nop     dword ptr [rax+rax+00h]
0x1801dcda9  mov     rcx, [rbp+158h]; this
0x1801dcdb0  test    eax, eax
0x1801dcdb2  jns     short loc_1801DCDC8
0x1801dcdb4  mov     r9d, eax; char *
0x1801dcdb7  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801dcdbe  mov     edx, 0BC3h; void *
0x1801dcdc3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801dcdc8  mov     rdx, [rsp+250h+pv]
0x1801dcdcd  test    rdx, rdx
0x1801dcdd0  jz      short loc_1801DCE10
0x1801dcdd2  lea     rcx, [rbp+150h+var_120]
0x1801dcdd6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801dcddb  nop
0x1801dcddc  lea     r8, aFeedbackhubCus; "\\FeedbackHub\\CustomTraceProfiles"
0x1801dcde3  mov     rdx, rax
0x1801dcde6  lea     rcx, [rbp+150h+var_148]
0x1801dcdea  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x1801dcdef  mov     rdx, rax
0x1801dcdf2  lea     rcx, [rbp+150h+lpFileName]
0x1801dcdf6  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801dcdfb  lea     rcx, [rbp+150h+var_148]; this
0x1801dcdff  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801dce04  nop
0x1801dce05  lea     rcx, [rbp+150h+var_120]; this
0x1801dce09  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801dce0e  jmp     short loc_1801DCE34
0x1801dce10  mov     r8d, 32h ; '2'
0x1801dce16  mov     rdx, cs:off_180360180; "%Public%\\Documents\\FeedbackHub\\Custo"...
0x1801dce1d  lea     rcx, [rbp+150h+lpFileName]
0x1801dce21  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1801dce26  xor     r8d, r8d
0x1801dce29  mov     dl, 1
0x1801dce2b  lea     rcx, [rbp+150h+lpFileName]; lpSrc
0x1801dce2f  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x1801dce34  lea     rcx, [rbp+150h+lpFileName]
0x1801dce38  cmp     [rbp+150h+var_170], 7
0x1801dce3d  cmova   rcx, [rbp+150h+lpFileName]; lpFileName
0x1801dce42  call    cs:__imp_GetFileAttributesW
0x1801dce49  nop     dword ptr [rax+rax+00h]
0x1801dce4e  cmp     eax, 0FFFFFFFFh
0x1801dce51  jz      loc_1801DCF40
0x1801dce57  test    sil, al
0x1801dce5a  jz      loc_1801DCF40
0x1801dce60  lea     rdx, [rbp+150h+lpFileName]
0x1801dce64  lea     rcx, [rbp+150h+var_168]
0x1801dce68  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801dce6d  mov     eax, cs:dword_18042D328
0x1801dce73  cmp     eax, 4
0x1801dce76  jbe     short loc_1801DCEB3
0x1801dce78  mov     rdx, r14
0x1801dce7b  mov     rcx, rdi
0x1801dce7e  call    _tlgKeywordOn
0x1801dce83  test    al, al
0x1801dce85  jz      short loc_1801DCEB3
0x1801dce87  lea     rax, [rbp+150h+var_168]
0x1801dce8b  cmp     [rbp+150h+var_150], 7
0x1801dce90  cmova   rax, [rbp+150h+var_168]
0x1801dce95  mov     qword ptr [rsp+250h+var_220], rax
0x1801dce9a  lea     rax, [rsp+250h+var_220]
0x1801dce9f  mov     qword ptr [rsp+250h+var_230], rax
0x1801dcea4  lea     rdx, unk_1803C87C3
0x1801dceab  mov     rcx, rdi
0x1801dceae  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1801dceb3  mov     [rbp+150h+var_190], 0
0x1801dceb7  lea     rax, off_1803570D8
0x1801dcebe  mov     [rbp+150h+var_C0], rax
0x1801dcec5  lea     rax, [rsp+250h+Src]
0x1801dceca  mov     [rbp+150h+var_B8], rax
0x1801dced1  lea     rax, [rbp+150h+var_C0]
0x1801dced8  mov     [rbp+150h+var_88], rax
0x1801dcedf  movups  xmm0, xmmword ptr cs:?k_customProfilesFilePattern@UtcApiManager@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::UtcApiManager::k_customProfilesFilePattern
0x1801dcee6  movdqu  [rbp+150h+var_120], xmm0
0x1801dceeb  lea     rdx, [rbp+150h+var_148]
0x1801dceef  lea     rcx, [rbp+150h+var_168]
0x1801dcef3  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801dcef8  movups  xmm0, xmmword ptr [rax]
0x1801dcefb  movdqu  xmmword ptr [rsp+250h+var_220], xmm0
0x1801dcf01  lea     r9, [rbp+150h+var_1D0]
0x1801dcf05  lea     r8, [rbp+150h+var_C0]
0x1801dcf0c  lea     rdx, [rbp+150h+var_120]
0x1801dcf10  lea     rcx, [rsp+250h+var_220]
0x1801dcf15  call    ?DoForEachFileInPattern@FileSystem@Utils@Diagnostics@Microsoft@@SAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBV?$function@$$A6A_NAEBVAutoFindFile@@@Z@6@V?$optional@V?$function@$$A6A_NJ@Z@std@@@6@@Z; Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileInPattern(std::wstring_view,std::wstring_view,std::function<bool (AutoFindFile const &)> const &,std::optional<std::function<bool (long)>>)
0x1801dcf1a  nop
0x1801dcf1b  mov     rcx, [rbp+150h+var_88]
0x1801dcf22  test    rcx, rcx
0x1801dcf25  jz      short loc_1801DCF40
0x1801dcf27  mov     rax, [rcx]
0x1801dcf2a  lea     rdx, [rbp+150h+var_C0]
0x1801dcf31  cmp     rcx, rdx
0x1801dcf34  setnz   dl
0x1801dcf37  mov     rax, [rax+20h]
0x1801dcf3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dcf40  lea     rdx, [rsp+250h+var_210]
0x1801dcf45  call    ?ImpersonateRpcCaller@UtcApiManager@Diagnostics@Microsoft@@AEAA@XZ; Microsoft::Diagnostics::UtcApiManager::ImpersonateRpcCaller(void)
0x1801dcf4a  nop
0x1801dcf4b  mov     r8d, 37h ; '7'
0x1801dcf51  mov     rdx, cs:off_180360190; "%USERPROFILE%\\Documents\\FeedbackHub\\"...
0x1801dcf58  lea     rcx, [rbp+150h+lpFileName]
0x1801dcf5c  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1801dcf61  xor     r8d, r8d
0x1801dcf64  mov     dl, 1
0x1801dcf66  lea     rcx, [rbp+150h+lpFileName]; lpSrc
0x1801dcf6a  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x1801dcf6f  nop
0x1801dcf70  cmp     [rsp+250h+var_20F], 0
0x1801dcf75  jz      short loc_1801DCF8B
0x1801dcf77  call    cs:__imp_RpcRevertToSelf
0x1801dcf7e  nop     dword ptr [rax+rax+00h]
0x1801dcf83  test    eax, eax
0x1801dcf85  jnz     loc_1801DD294
0x1801dcf8b  lea     rcx, [rbp+150h+lpFileName]
0x1801dcf8f  cmp     [rbp+150h+var_170], 7
0x1801dcf94  cmova   rcx, [rbp+150h+lpFileName]; lpFileName
0x1801dcf99  call    cs:__imp_GetFileAttributesW
0x1801dcfa0  nop     dword ptr [rax+rax+00h]
0x1801dcfa5  cmp     eax, 0FFFFFFFFh
0x1801dcfa8  jz      loc_1801DD097
0x1801dcfae  test    sil, al
0x1801dcfb1  jz      loc_1801DD097
0x1801dcfb7  lea     rdx, [rbp+150h+lpFileName]
0x1801dcfbb  lea     rcx, [rbp+150h+var_168]
0x1801dcfbf  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801dcfc4  mov     eax, cs:dword_18042D328
0x1801dcfca  cmp     eax, 4
0x1801dcfcd  jbe     short loc_1801DD00A
0x1801dcfcf  mov     rdx, r14
0x1801dcfd2  mov     rcx, rdi
0x1801dcfd5  call    _tlgKeywordOn
0x1801dcfda  test    al, al
0x1801dcfdc  jz      short loc_1801DD00A
0x1801dcfde  lea     rax, [rbp+150h+var_168]
0x1801dcfe2  cmp     [rbp+150h+var_150], 7
0x1801dcfe7  cmova   rax, [rbp+150h+var_168]
0x1801dcfec  mov     qword ptr [rsp+250h+var_220], rax
0x1801dcff1  lea     rax, [rsp+250h+var_220]
0x1801dcff6  mov     qword ptr [rsp+250h+var_230], rax; int
0x1801dcffb  lea     rdx, unk_1803C86FD
0x1801dd002  mov     rcx, rdi
0x1801dd005  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1801dd00a  mov     [rbp+150h+var_190], 0
0x1801dd00e  lea     rax, off_180357018
0x1801dd015  mov     [rbp+150h+var_80], rax
0x1801dd01c  lea     rax, [rsp+250h+Src]
0x1801dd021  mov     [rbp+150h+var_78], rax
0x1801dd028  lea     rax, [rbp+150h+var_80]
0x1801dd02f  mov     [rbp+150h+var_48], rax
0x1801dd036  movups  xmm0, xmmword ptr cs:?k_customProfilesFilePattern@UtcApiManager@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::UtcApiManager::k_customProfilesFilePattern
0x1801dd03d  movdqu  [rbp+150h+var_120], xmm0
0x1801dd042  lea     rdx, [rbp+150h+var_148]
0x1801dd046  lea     rcx, [rbp+150h+var_168]
0x1801dd04a  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801dd04f  movups  xmm0, xmmword ptr [rax]
0x1801dd052  movdqu  xmmword ptr [rsp+250h+var_220], xmm0
0x1801dd058  lea     r9, [rbp+150h+var_1D0]
0x1801dd05c  lea     r8, [rbp+150h+var_80]
0x1801dd063  lea     rdx, [rbp+150h+var_120]
0x1801dd067  lea     rcx, [rsp+250h+var_220]
0x1801dd06c  call    ?DoForEachFileInPattern@FileSystem@Utils@Diagnostics@Microsoft@@SAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBV?$function@$$A6A_NAEBVAutoFindFile@@@Z@6@V?$optional@V?$function@$$A6A_NJ@Z@std@@@6@@Z; Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileInPattern(std::wstring_view,std::wstring_view,std::function<bool (AutoFindFile const &)> const &,std::optional<std::function<bool (long)>>)
0x1801dd071  nop
0x1801dd072  mov     rcx, [rbp+150h+var_48]
0x1801dd079  test    rcx, rcx
0x1801dd07c  jz      short loc_1801DD097
0x1801dd07e  mov     rax, [rcx]
0x1801dd081  lea     rdx, [rbp+150h+var_80]
0x1801dd088  cmp     rcx, rdx
0x1801dd08b  setnz   dl
0x1801dd08e  mov     rax, [rax+20h]
0x1801dd092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dd097  mov     [rsp+250h+var_200], 0
0x1801dd0a0  mov     rbx, [rsp+250h+Src+8]
0x1801dd0a5  mov     rdi, [rsp+250h+Src]
0x1801dd0aa  cmp     rdi, rbx
0x1801dd0ad  jz      loc_1801DD195
0x1801dd0b3  sub     rbx, rdi
0x1801dd0b6  sar     rbx, 5
  ... truncated ...
```
