# CClientConfigDataCacheManager::InitializePathsAndMutableConfigs(void)

- ea: `0x1800c5e24`
- end: `0x1800c6795`
- name: `?InitializePathsAndMutableConfigs@CClientConfigDataCacheManager@@AEAAJXZ`
- size: `2417`
- prototype: `__int64 __fastcall(CClientConfigDataCacheManager *__hidden this)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c5a90`

## callees

- `0x180001e90`
- `0x180006ac0`
- `0x18000ed04`
- `0x180013510`
- `0x18001426c`
- `0x1800143a4`
- `0x180014640`
- `0x1800151c4`
- `0x180018f80`
- `0x180019690`
- `0x18001cf20`
- `0x180023d24`
- `0x180025c68`
- `0x18002d36c`
- `0x180030a8c`
- `0x18004d8c4`
- `0x180054dc4`
- `0x18005538c`
- `0x18005c814`
- `0x18007cdf8`
- `0x180080650`
- `0x180085fdc`
- `0x180088c64`
- `0x180088ebc`
- `0x1800a3b60`
- `0x1800adf50`
- `0x1800c5e24`
- `0x1800c6834`
- `0x1800c86f4`
- `0x1800c916c`

## import_xrefs

- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800c6541`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800c6567`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800c6541`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800c6567`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x1800c5f95`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x1800c64cd`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x1800c6511`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x1800c5f95`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x1800c64cd`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x1800c6511`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800c5eb3`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800c610b`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800c5eb3`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800c610b`

## string_xrefs

- `0x1800c5ebf`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c5f6d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c5fb3`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c600d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c5e62`: `InitializePathsAndMutableConfigs`
- `0x1800c5fe5`: `\wlidsvcconfig.xml`
- `0x1800c6579`: `LastCopiedConfigVersion`
- `0x1800c602b`: `Client config file is '%ls'.`
- `0x1800c6000`: `Client config directory is '%ls'.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CClientConfigDataCacheManager::InitializePathsAndMutableConfigs(CClientConfigDataCacheManager *this)
{
  HRESULT ShouldCopyConfigFiles; // eax
  unsigned int LastError; // ebx
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rcx
  int v8; // eax
  int v9; // esi
  const WCHAR *Buffer; // rax
  int v11; // eax
  const char *v12; // r9
  _QWORD *v13; // rsi
  __int64 v14; // rcx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  HRESULT v18; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rdx
  int v35; // eax
  wil::details::in1diag3 *v36; // rcx
  __int64 v37; // rcx
  int v38; // eax
  const WCHAR *v39; // rax
  int v40; // eax
  const char *v41; // r9
  __int64 v42; // rdx
  const WCHAR *v43; // rax
  int v44; // eax
  void *v45; // rdx
  unsigned int v46; // r8d
  const char *v47; // r9
  void *v48; // rdx
  unsigned int v49; // r8d
  const char *v50; // r9
  int v51; // eax
  __int64; // rax
  int v53; // ebx
  int v54; // [rsp+20h] [rbp-218h]
  int v55; // [rsp+20h] [rbp-218h]
  int v56; // [rsp+20h] [rbp-218h]
  int v57; // [rsp+20h] [rbp-218h]
  int v58[2]; // [rsp+20h] [rbp-218h]
  char v59[8]; // [rsp+30h] [rbp-208h] BYREF
  int v60[2]; // [rsp+38h] [rbp-200h] BYREF
  char v61[8]; // [rsp+40h] [rbp-1F8h] BYREF
  char v62[8]; // [rsp+48h] [rbp-1F0h] BYREF
  char v63[8]; // [rsp+50h] [rbp-1E8h] BYREF
  LPCWSTR v64; // [rsp+58h] [rbp-1E0h] BYREF
  LPCWSTR lpNewFileName; // [rsp+60h] [rbp-1D8h] BYREF
  PWSTR v66; // [rsp+68h] [rbp-1D0h] BYREF
  LPCWSTR v67; // [rsp+70h] [rbp-1C8h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+78h] [rbp-1C0h] BYREF
  char v69[8]; // [rsp+80h] [rbp-1B8h] BYREF
  PWSTR ppszPath; // [rsp+88h] [rbp-1B0h] BYREF
  __int64 v71; // [rsp+90h] [rbp-1A8h] BYREF
  int v72; // [rsp+98h] [rbp-1A0h] BYREF
  __int64 v73; // [rsp+A0h] [rbp-198h]
  int v74; // [rsp+A8h] [rbp-190h] BYREF
  int v75; // [rsp+ACh] [rbp-18Ch] BYREF
  int v76; // [rsp+B0h] [rbp-188h] BYREF
  char v77[8]; // [rsp+B8h] [rbp-180h] BYREF
  _QWORD v78[42]; // [rsp+C0h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  v59[0] = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
  wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v78,
    "InitializePathsAndMutableConfigs");
  v78[0] = &MSAClientTraceTelemetry::InitializePathsAndMutableConfigs::`vftable';
  MSAClientTraceTelemetry::InitializePathsAndMutableConfigs::StartActivity((MSAClientTraceTelemetry::InitializePathsAndMutableConfigs *)v78);
  ppszPath = 0;
  ShouldCopyConfigFiles = SHGetKnownFolderPath(&FOLDERID_ProgramData, 0, 0, &ppszPath);
  LastError = ShouldCopyConfigFiles;
  if ( ShouldCopyConfigFiles < 0 )
  {
    v4 = 1206;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      (const char *)(unsigned int)ShouldCopyConfigFiles,
      v58[0]);
    goto LABEL_48;
  }
  v5 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
         v60,
         ppszPath);
  ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 16, v5);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v60);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    ((void (*)(void))ATL::CSimpleStringT<unsigned short,0>::PrepareWrite)();
    ATL::CSimpleStringT<unsigned short,0>::Append((char *)this + 16, L"\\");
    ATL::CSimpleStringT<unsigned short,0>::Append((char *)this + 16, L"Microsoft\\IdentityCRL");
    ATL::CSimpleStringT<unsigned short,0>::Append((char *)this + 16, L"\\");
    v6 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim((char *)this + 280);
    ATL::CSimpleStringT<unsigned short,0>::Append((char *)this + 16, v6);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v76) )
    {
      if ( v76 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4C3,
          (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
          (const char *)(unsigned int)v76,
          v57);
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800C673C);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
      MSAClientTraceTelemetry::InitializePathsAndMutableConfigs::~InitializePathsAndMutableConfigs((MSAClientTraceTelemetry::InitializePathsAndMutableConfigs *)v78);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
       = (unsigned int)v76;
LABEL_76:
      ;
    }
  }
  v8 = CClientConfigDataCacheManager::ModifyPathIfXbox(v7, (_QWORD *)this + 2);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C6,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      (const char *)(unsigned int)v8,
      v58[0]);
    LastError = v9;
LABEL_48:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
    MSAClientTraceTelemetry::InitializePathsAndMutableConfigs::~InitializePathsAndMutableConfigs((MSAClientTraceTelemetry::InitializePathsAndMutableConfigs *)v78);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
     = LastError;
    goto LABEL_76;
  }
  Buffer = (const WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer((char *)this + 16);
  v11 = SHCreateDirectoryExW(0, Buffer, 0);
  if ( v11 && v11 != 183 && v11 != 80 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x4CC,
                  (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
                  v12);
    goto LABEL_48;
  }
  if ( __eh34_try(-1, 2) )
  {
    __eh34_scope_strut(2);
    v13 = (_QWORD *)((char *)this + 8);
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite((char *)this + 8, 100);
    ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 8, (char *)this + 16);
    ATL::CSimpleStringT<unsigned short,0>::Append((char *)this + 8, L"\\wlidsvcconfig.xml");
  }
  if ( __eh34_catch(2) )
  {
    if ( __eh34_catch_type(2, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v75) )
    {
      if ( v75 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4D8,
          (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
          (const char *)(unsigned int)v75,
          v56);
      LastError = v75;
      __eh34_try_continuation(2, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800C6708);
      goto LABEL_48;
    }
  }
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
    0x4DBu,
    L"Client config directory is '%ls'.",
    *((_QWORD *)this + 2));
  *(_QWORD *)v58 = *v13;
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
    0x4DCu,
    L"Client config file is '%ls'.");
  ShouldCopyConfigFiles = CClientConfigDataCacheManager::ShouldCopyConfigFiles(v14, v59, (__int64)&v71);
  LastError = ShouldCopyConfigFiles;
  if ( ShouldCopyConfigFiles < 0 )
  {
    v4 = 1248;
    goto LABEL_12;
  }
  if ( v59[0] )
  {
    v72 = 0;
    v73 = 0;
    CAutoRevertToSelf::Revert((CAutoRevertToSelf *)&v72, 0);
    if ( (unsigned int)dword_1801C2080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801C2080, 0x400000000000LL) )
    {
      *(_QWORD *)v60 = v71;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v15,
        (int)&dword_180198C04,
        v16,
        v17,
        (__int64)v60);
    }
    v66 = 0;
    v18 = SHGetKnownFolderPath(&FOLDERID_Windows, 0, 0, &v66);
    LastError = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4F4,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
        (const char *)(unsigned int)v18,
        v58[0]);
LABEL_19:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
      CAutoRevertToSelf::~CAutoRevertToSelf((CAutoRevertToSelf *)&v72);
      goto LABEL_48;
    }
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpExistingFileName);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v67);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpNewFileName);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v64);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v62);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v61);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v63);
    if ( __eh34_try(-1, 4) )
    {
      __eh34_scope_strut(4);
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(&lpExistingFileName, 100);
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(&v67, 100);
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(&lpNewFileName, 100);
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(&v64, 100);
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(v62, 100);
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(v61, 100);
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(v63, 100);
      v19 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              v69,
              ppszPath);
      v20 = ATL::operator+(v60, v19, L"\\Microsoft");
      ATL::CSimpleStringT<unsigned short,0>::operator=(v63, v20);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v60);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v69);
      v21 = ATL::operator+(v60, v63, L"\\IdentityCRL\\production");
      ATL::CSimpleStringT<unsigned short,0>::operator=(v62, v21);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v60);
      v22 = ATL::operator+(v60, v63, L"\\IdentityCRL\\INT");
      ATL::CSimpleStringT<unsigned short,0>::operator=(v61, v22);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v60);
      v23 = ATL::operator+(v60, v62, L"\\wlidsvcconfig.xml");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&lpNewFileName, v23);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v60);
      v24 = ATL::operator+(v60, v61, L"\\wlidsvcconfig.xml");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&v64, v24);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v60);
      v25 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              v77,
              v66);
      v26 = ATL::operator+(v69, v25, L"\\IdentityCRL\\production");
      v27 = ATL::operator+(v60, v26, L"\\wlidsvcconfig.xml");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&lpExistingFileName, v27);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v60);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v69);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v77);
      v28 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              v69,
              v66);
      v29 = ATL::operator+(v60, v28, L"\\IdentityCRL\\INT");
      v30 = ATL::operator+(v77, v29, L"\\wlidsvcconfig.xml");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&v67, v30);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v77);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v60);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v69);
    }
    if ( __eh34_catch(4) )
    {
      if ( __eh34_catch_type(4, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v74) )
      {
        v53 = v74;
        v54 = v74;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
          0x51Fu,
          L"Error creating location strings. 0x%x",
          v54);
        if ( v53 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x520,
            (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
            (const char *)(unsigned int)v53,
            v55);
        __eh34_try_continuation(4, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800C669A);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v63);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v61);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v62);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v64);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpNewFileName);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v67);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpExistingFileName);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
        CAutoRevertToSelf::~CAutoRevertToSelf((CAutoRevertToSelf *)&v72);
        LastError = v74;
        goto LABEL_48;
      }
    }
    v32 = CClientConfigDataCacheManager::ModifyPathIfXbox(v31, &lpNewFileName);
    LastError = v32;
    if ( v32 < 0 )
    {
      v34 = 1316;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
        (const char *)(unsigned int)v32,
        v58[0]);
LABEL_24:
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v63);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v61);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v62);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v64);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpNewFileName);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v67);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpExistingFileName);
      goto LABEL_19;
    }
    v35 = CClientConfigDataCacheManager::ModifyPathIfXbox(v33, &v64);
    v36 = retaddr;
    if ( v35 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x525,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
        (const char *)(unsigned int)v35,
        v58[0]);
    v32 = CClientConfigDataCacheManager::ModifyPathIfXbox((__int64)v36, v62);
    LastError = v32;
    if ( v32 < 0 )
    {
      v34 = 1318;
      goto LABEL_23;
    }
    v38 = CClientConfigDataCacheManager::ModifyPathIfXbox(v37, v61);
    if ( v38 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x527,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
        (const char *)(unsigned int)v38,
        v58[0]);
    v39 = (const WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v62);
    v40 = SHCreateDirectoryExW(0, v39, 0);
    if ( v40 && v40 != 183 && v40 != 80 )
    {
      v42 = 1325;
LABEL_35:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v42,
                    (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
                    v41);
      goto LABEL_24;
    }
    v43 = (const WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v61);
    v44 = SHCreateDirectoryExW(0, v43, 0);
    if ( v44 && v44 != 183 && v44 != 80 )
      wil::details::in1diag3::Log_GetLastError(retaddr, v45, v46, v47);
    if ( !CopyFileW(lpExistingFileName, lpNewFileName, 0) )
    {
      v42 = 1334;
      goto LABEL_35;
    }
    if ( !CopyFileW(v67, v64, 0) )
      wil::details::in1diag3::_Log_GetLastError(retaddr, v48, v49, v50);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      v60,
      L"LastCopiedConfigVersion");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      v69,
      L".DEFAULT\\Software\\Microsoft\\IdentityCRL\\Environment");
    v51 = Reg_SetString(HKEY_USERS);
    if ( v51 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x53E,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
        (const char *)(unsigned int)v51,
        v58[0]);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v69);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v60);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v63);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v61);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v62);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v64);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpNewFileName);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v67);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpExistingFileName);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
    CAutoRevertToSelf::~CAutoRevertToSelf((CAutoRevertToSelf *)&v72);
  }
  wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v78);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
  MSAClientTraceTelemetry::InitializePathsAndMutableConfigs::~InitializePathsAndMutableConfigs((MSAClientTraceTelemetry::InitializePathsAndMutableConfigs *)v78);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
   = 0;
  goto LABEL_76;
}

```

## disassembly

```asm
0x1800c5e24  mov     [rsp+arg_8], rbx
0x1800c5e29  mov     [rsp+arg_10], rsi
0x1800c5e2e  push    rdi
0x1800c5e2f  push    r12
0x1800c5e31  push    r13
0x1800c5e33  sub     rsp, 220h
0x1800c5e3a  mov     rax, cs:__security_cookie
0x1800c5e41  xor     rax, rsp
0x1800c5e44  mov     [rsp+238h+var_28], rax
0x1800c5e4c  mov     rdi, rcx
0x1800c5e4f  mov     [rsp+238h+var_208], 0
0x1800c5e54  lea     rcx, [rsp+238h+var_1A8]
0x1800c5e5c  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c5e61  nop
0x1800c5e62  lea     rdx, aInitializepath; "InitializePathsAndMutableConfigs"
0x1800c5e69  lea     rcx, [rsp+238h+var_178]
0x1800c5e71  call    ??0?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800c5e76  lea     rax, ??_7InitializePathsAndMutableConfigs@MSAClientTraceTelemetry@@6B@; const MSAClientTraceTelemetry::InitializePathsAndMutableConfigs::`vftable'
0x1800c5e7d  mov     [rsp+238h+var_178], rax
0x1800c5e85  lea     rcx, [rsp+238h+var_178]; this
0x1800c5e8d  call    ?StartActivity@InitializePathsAndMutableConfigs@MSAClientTraceTelemetry@@QEAAXXZ; MSAClientTraceTelemetry::InitializePathsAndMutableConfigs::StartActivity(void)
0x1800c5e92  nop
0x1800c5e93  mov     [rsp+238h+ppszPath], 0
0x1800c5e9f  lea     r9, [rsp+238h+ppszPath]; ppszPath
0x1800c5ea7  xor     r8d, r8d; hToken
0x1800c5eaa  xor     edx, edx; dwFlags
0x1800c5eac  lea     rcx, FOLDERID_ProgramData; rfid
0x1800c5eb3  call    cs:__imp_SHGetKnownFolderPath
0x1800c5eb9  mov     ebx, eax
0x1800c5ebb  test    eax, eax
0x1800c5ebd  jns     short loc_1800C5ED0
0x1800c5ebf  lea     r8, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c5ec6  mov     edx, 4B6h
0x1800c5ecb  jmp     loc_1800C6062
0x1800c5ed0  mov     rdx, [rsp+238h+ppszPath]
0x1800c5ed8  lea     rcx, [rsp+238h+var_200]
0x1800c5edd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800c5ee2  nop
0x1800c5ee3  lea     rbx, [rdi+10h]
0x1800c5ee7  mov     rdx, rax
0x1800c5eea  mov     rcx, rbx
0x1800c5eed  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800c5ef2  nop
0x1800c5ef3  lea     rcx, [rsp+238h+var_200]
0x1800c5ef8  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c5efd  nop
0x1800c5efe  mov     r12d, 64h ; 'd'
0x1800c5f04  mov     edx, r12d
0x1800c5f07  mov     rcx, rbx
0x1800c5f0a  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x1800c5f0f  lea     rdx, SubBlock; "\\"
0x1800c5f16  mov     rcx, rbx
0x1800c5f19  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1800c5f1e  lea     rdx, aMicrosoftIdent; "Microsoft\\IdentityCRL"
0x1800c5f25  mov     rcx, rbx
0x1800c5f28  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1800c5f2d  lea     rdx, SubBlock; "\\"
0x1800c5f34  mov     rcx, rbx
0x1800c5f37  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1800c5f3c  lea     rcx, [rdi+118h]
0x1800c5f43  call    ?Trim@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Trim(void)
0x1800c5f48  mov     rdx, rax
0x1800c5f4b  mov     rcx, rbx
0x1800c5f4e  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<ushort,0>::Append(ATL::CSimpleStringT<ushort,0> const &)
0x1800c5f53  nop
0x1800c5f54  mov     rdx, rbx
0x1800c5f57  call    ?ModifyPathIfXbox@CClientConfigDataCacheManager@@AEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CClientConfigDataCacheManager::ModifyPathIfXbox(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800c5f5c  mov     esi, eax
0x1800c5f5e  test    eax, eax
0x1800c5f60  jns     short loc_1800C5F85
0x1800c5f62  mov     rcx, [rsp+238h]; this
0x1800c5f6a  mov     r9d, eax; char *
0x1800c5f6d  lea     r8, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c5f74  mov     edx, 4C6h; void *
0x1800c5f79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c5f7e  mov     ebx, esi
0x1800c5f80  jmp     loc_1800C670F
0x1800c5f85  mov     rcx, rbx
0x1800c5f88  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800c5f8d  mov     rdx, rax; pszPath
0x1800c5f90  xor     r8d, r8d; psa
0x1800c5f93  xor     ecx, ecx; hwnd
0x1800c5f95  call    cs:__imp_SHCreateDirectoryExW
0x1800c5f9b  test    eax, eax
0x1800c5f9d  jz      short loc_1800C5FCB
0x1800c5f9f  cmp     eax, 0B7h
0x1800c5fa4  jz      short loc_1800C5FCB
0x1800c5fa6  cmp     eax, 50h ; 'P'
0x1800c5fa9  jz      short loc_1800C5FCB
0x1800c5fab  mov     rcx, [rsp+238h]; this
0x1800c5fb3  lea     r8, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c5fba  mov     edx, 4CCh; void *
0x1800c5fbf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c5fc4  mov     ebx, eax
0x1800c5fc6  jmp     loc_1800C670F
0x1800c5fcb  lea     rsi, [rdi+8]
0x1800c5fcf  mov     edx, r12d
0x1800c5fd2  mov     rcx, rsi
0x1800c5fd5  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x1800c5fda  mov     rdx, rbx
0x1800c5fdd  mov     rcx, rsi
0x1800c5fe0  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800c5fe5  lea     r13, aWlidsvcconfigX; "\\wlidsvcconfig.xml"
0x1800c5fec  mov     rdx, r13
0x1800c5fef  mov     rcx, rsi
0x1800c5ff2  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1800c5ff7  nop
0x1800c5ff8  mov     rax, [rbx]
0x1800c5ffb  mov     qword ptr [rsp+238h+var_218], rax
0x1800c6000  lea     r9, aClientConfigDi; "Client config directory is '%ls'."
0x1800c6007  mov     r8d, 4DBh; unsigned int
0x1800c600d  lea     rdi, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c6014  mov     rdx, rdi; char *
0x1800c6017  mov     ebx, 5
0x1800c601c  mov     ecx, ebx; unsigned __int8
0x1800c601e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800c6023  mov     rax, [rsi]
0x1800c6026  mov     qword ptr [rsp+238h+var_218], rax; int
0x1800c602b  lea     r9, aClientConfigFi; "Client config file is '%ls'."
0x1800c6032  mov     r8d, 4DCh; unsigned int
0x1800c6038  mov     rdx, rdi; char *
0x1800c603b  mov     ecx, ebx; unsigned __int8
0x1800c603d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800c6042  lea     r8, [rsp+238h+var_1A8]
0x1800c604a  lea     rdx, [rsp+238h+var_208]
0x1800c604f  call    ?ShouldCopyConfigFiles@CClientConfigDataCacheManager@@AEAAJAEA_NAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CClientConfigDataCacheManager::ShouldCopyConfigFiles(bool &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800c6054  mov     ebx, eax
0x1800c6056  test    eax, eax
0x1800c6058  jns     short loc_1800C6077
0x1800c605a  mov     r8, rdi; unsigned int
0x1800c605d  mov     edx, 4E0h; void *
0x1800c6062  mov     r9d, eax; char *
0x1800c6065  mov     rcx, [rsp+238h]; this
0x1800c606d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6072  jmp     loc_1800C670F
0x1800c6077  cmp     [rsp+238h+var_208], 0
0x1800c607c  jz      loc_1800C665C
0x1800c6082  mov     [rsp+238h+var_1A0], 0
0x1800c608d  mov     [rsp+238h+var_198], 0
0x1800c6099  xor     edx, edx; int
0x1800c609b  lea     rcx, [rsp+238h+var_1A0]; this
0x1800c60a3  call    ?Revert@CAutoRevertToSelf@@QEAAHH@Z; CAutoRevertToSelf::Revert(int)
0x1800c60a8  mov     eax, cs:dword_1801C2080
0x1800c60ae  cmp     eax, 5
0x1800c60b1  jbe     short loc_1800C60F1
0x1800c60b3  mov     rdx, 400000000000h
0x1800c60bd  lea     rcx, dword_1801C2080
0x1800c60c4  call    _tlgKeywordOn
0x1800c60c9  test    al, al
0x1800c60cb  jz      short loc_1800C60F1
0x1800c60cd  mov     rax, [rsp+238h+var_1A8]
0x1800c60d5  mov     qword ptr [rsp+238h+var_200], rax
0x1800c60da  lea     rax, [rsp+238h+var_200]
0x1800c60df  mov     qword ptr [rsp+238h+var_218], rax; int
0x1800c60e4  lea     rdx, dword_180198C04
0x1800c60eb  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800c60f0  nop
0x1800c60f1  mov     [rsp+238h+var_1D0], 0
0x1800c60fa  lea     r9, [rsp+238h+var_1D0]; ppszPath
0x1800c60ff  xor     r8d, r8d; hToken
0x1800c6102  xor     edx, edx; dwFlags
0x1800c6104  lea     rcx, FOLDERID_Windows; rfid
0x1800c610b  call    cs:__imp_SHGetKnownFolderPath
0x1800c6111  mov     ebx, eax
0x1800c6113  test    eax, eax
0x1800c6115  jns     short loc_1800C614D
0x1800c6117  mov     rcx, [rsp+238h]; this
0x1800c611f  mov     r9d, eax; char *
0x1800c6122  mov     r8, rdi; unsigned int
0x1800c6125  mov     edx, 4F4h; void *
0x1800c612a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c612f  nop
0x1800c6130  lea     rcx, [rsp+238h+var_1D0]
0x1800c6135  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c613a  nop
0x1800c613b  lea     rcx, [rsp+238h+var_1A0]; this
0x1800c6143  call    ??1CAutoRevertToSelf@@QEAA@XZ; CAutoRevertToSelf::~CAutoRevertToSelf(void)
0x1800c6148  jmp     loc_1800C670F
0x1800c614d  lea     rcx, [rsp+238h+lpExistingFileName]
0x1800c6152  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c6157  nop
0x1800c6158  lea     rcx, [rsp+238h+var_1C8]
0x1800c615d  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c6162  nop
0x1800c6163  lea     rcx, [rsp+238h+lpNewFileName]
0x1800c6168  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c616d  nop
0x1800c616e  lea     rcx, [rsp+238h+var_1E0]
0x1800c6173  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c6178  nop
0x1800c6179  lea     rcx, [rsp+238h+var_1F0]
0x1800c617e  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c6183  nop
0x1800c6184  lea     rcx, [rsp+238h+var_1F8]
0x1800c6189  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c618e  nop
0x1800c618f  lea     rcx, [rsp+238h+var_1E8]
0x1800c6194  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c6199  nop
0x1800c619a  mov     edx, r12d
0x1800c619d  lea     rcx, [rsp+238h+lpExistingFileName]
0x1800c61a2  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x1800c61a7  mov     edx, r12d
0x1800c61aa  lea     rcx, [rsp+238h+var_1C8]
0x1800c61af  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x1800c61b4  mov     edx, r12d
0x1800c61b7  lea     rcx, [rsp+238h+lpNewFileName]
0x1800c61bc  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x1800c61c1  mov     edx, r12d
0x1800c61c4  lea     rcx, [rsp+238h+var_1E0]
0x1800c61c9  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x1800c61ce  mov     edx, r12d
0x1800c61d1  lea     rcx, [rsp+238h+var_1F0]
0x1800c61d6  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x1800c61db  mov     edx, r12d
0x1800c61de  lea     rcx, [rsp+238h+var_1F8]
0x1800c61e3  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x1800c61e8  mov     edx, r12d
0x1800c61eb  lea     rcx, [rsp+238h+var_1E8]
0x1800c61f0  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x1800c61f5  mov     rdx, [rsp+238h+ppszPath]
0x1800c61fd  lea     rcx, [rsp+238h+var_1B8]
0x1800c6205  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800c620a  nop
0x1800c620b  lea     r8, aMicrosoft; "\\Microsoft"
0x1800c6212  mov     rdx, rax
0x1800c6215  lea     rcx, [rsp+238h+var_200]
0x1800c621a  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x1800c621f  nop
0x1800c6220  mov     rdx, rax
0x1800c6223  lea     rcx, [rsp+238h+var_1E8]
0x1800c6228  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800c622d  nop
0x1800c622e  lea     rcx, [rsp+238h+var_200]
0x1800c6233  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c6238  nop
0x1800c6239  lea     rcx, [rsp+238h+var_1B8]
0x1800c6241  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c6246  lea     r8, aIdentitycrlPro; "\\IdentityCRL\\production"
0x1800c624d  lea     rdx, [rsp+238h+var_1E8]
0x1800c6252  lea     rcx, [rsp+238h+var_200]
0x1800c6257  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x1800c625c  nop
0x1800c625d  mov     rdx, rax
0x1800c6260  lea     rcx, [rsp+238h+var_1F0]
0x1800c6265  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800c626a  nop
0x1800c626b  lea     rcx, [rsp+238h+var_200]
0x1800c6270  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c6275  lea     r8, aIdentitycrlInt; "\\IdentityCRL\\INT"
0x1800c627c  lea     rdx, [rsp+238h+var_1E8]
0x1800c6281  lea     rcx, [rsp+238h+var_200]
0x1800c6286  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x1800c628b  nop
0x1800c628c  mov     rdx, rax
0x1800c628f  lea     rcx, [rsp+238h+var_1F8]
0x1800c6294  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800c6299  nop
0x1800c629a  lea     rcx, [rsp+238h+var_200]
0x1800c629f  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c62a4  mov     r8, r13
0x1800c62a7  lea     rdx, [rsp+238h+var_1F0]
0x1800c62ac  lea     rcx, [rsp+238h+var_200]
0x1800c62b1  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x1800c62b6  nop
0x1800c62b7  mov     rdx, rax
0x1800c62ba  lea     rcx, [rsp+238h+lpNewFileName]
0x1800c62bf  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800c62c4  nop
0x1800c62c5  lea     rcx, [rsp+238h+var_200]
0x1800c62ca  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c62cf  mov     r8, r13
0x1800c62d2  lea     rdx, [rsp+238h+var_1F8]
0x1800c62d7  lea     rcx, [rsp+238h+var_200]
0x1800c62dc  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x1800c62e1  nop
0x1800c62e2  mov     rdx, rax
0x1800c62e5  lea     rcx, [rsp+238h+var_1E0]
0x1800c62ea  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800c62ef  nop
0x1800c62f0  lea     rcx, [rsp+238h+var_200]
0x1800c62f5  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c62fa  mov     rdx, [rsp+238h+var_1D0]
0x1800c62ff  lea     rcx, [rsp+238h+var_180]
0x1800c6307  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800c630c  nop
0x1800c630d  lea     r8, aIdentitycrlPro; "\\IdentityCRL\\production"
0x1800c6314  mov     rdx, rax
0x1800c6317  lea     rcx, [rsp+238h+var_1B8]
0x1800c631f  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x1800c6324  nop
0x1800c6325  mov     r8, r13
0x1800c6328  mov     rdx, rax
0x1800c632b  lea     rcx, [rsp+238h+var_200]
0x1800c6330  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x1800c6335  nop
0x1800c6336  mov     rdx, rax
0x1800c6339  lea     rcx, [rsp+238h+lpExistingFileName]
0x1800c633e  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800c6343  nop
  ... truncated ...
```
