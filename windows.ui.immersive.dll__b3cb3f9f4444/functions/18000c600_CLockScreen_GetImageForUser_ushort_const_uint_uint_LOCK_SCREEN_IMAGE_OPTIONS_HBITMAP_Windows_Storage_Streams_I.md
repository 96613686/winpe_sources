# CLockScreen::_GetImageForUser(ushort const *,uint,uint,LOCK_SCREEN_IMAGE_OPTIONS,HBITMAP__ * *,Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x18000c600`
- end: `0x18000d9f7`
- name: `?_GetImageForUser@CLockScreen@@QEAAJPEBGIIW4LOCK_SCREEN_IMAGE_OPTIONS@@PEAPEAUHBITMAP__@@PEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z`
- size: `5111`
- prototype: `int __high(const unsigned __int16 *, unsigned int, unsigned int, enum LOCK_SCREEN_IMAGE_OPTIONS, HBITMAP *, struct Windows::Storage::Streams::IRandomAccessStream **)`
- caller_count: `3`
- callee_count: `53`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180031dc0`
- `0x1800b8430`
- `0x1800b8470`

## callees

- `0x1800045a8`
- `0x1800053a0`
- `0x18000b2e4`
- `0x18000b3b0`
- `0x18000b5b8`
- `0x18000b700`
- `0x18000b888`
- `0x18000b9fc`
- `0x18000ba88`
- `0x18000bc90`
- `0x18000bdcc`
- `0x18000c1dc`
- `0x18000c2a0`
- `0x18000c410`
- `0x18000c484`
- `0x18000c600`
- `0x18000da00`
- `0x18000db74`
- `0x180013f14`
- `0x180023ac8`
- `0x180024178`
- `0x180024630`
- `0x180029130`
- `0x18002cd5c`
- `0x18002cdd0`
- `0x180032e0c`
- `0x1800338e4`
- `0x1800343ec`
- `0x180035c94`
- `0x180035f88`
- `0x180035fe0`
- `0x180038dac`
- `0x18003c554`
- `0x18003d244`
- `0x18003ff34`
- `0x180042244`
- `0x180046964`
- `0x18004fed8`
- `0x180054130`
- `0x180054ad4`
- `0x180087920`
- `0x180091d00`
- `0x1800b1888`
- `0x1800b2894`
- `0x1800b293c`
- `0x1800b29e4`
- `0x1800b2a8c`
- `0x1800b2b14`
- `0x1800b668c`
- `0x1800c0768`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d96b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d96b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c8aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d2fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d8ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c8aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d2fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d8ed`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c702`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c702`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000c7b2`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000c7b2`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000ce8c`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000d06c`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000d4ce`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000ce8c`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000d06c`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000d4ce`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18000d52b`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18000d855`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18000d52b`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18000d855`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18000cc4f`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18000cc4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cee3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d0c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cee3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d0c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ccdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d8cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d8dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d90e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ccdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d8cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d8dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d90e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d585`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d79f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d585`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d79f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000c85d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000d26a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000d3b9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000c85d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000d26a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000d3b9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000c984`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000cc72`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000c984`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000cc72`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CLockScreen::_GetImageForUser(
        __int64 a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        RTL_SRWLOCK *a6,
        struct Windows::Storage::Streams::IRandomAccessStream **a7)
{
  unsigned __int16 *v7; // rsi
  CreativeFramework::Policy *v9; // rcx
  unsigned __int16 *v10; // r13
  LSTATUS ValueW; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  bool v14; // sf
  char v15; // r15
  bool v16; // bl
  int LocalSystemUserSid; // r12d
  bool v18; // al
  WCHAR *v19; // rdi
  PSID v20; // rbx
  char v21; // al
  int v22; // ebx
  __int16 v23; // r14
  bool IsSpotlightEnabled; // bl
  int Error; // eax
  int CreativeLockScreenPath; // eax
  int v27; // esi
  __int64 v28; // rdx
  int SecureLockScreenDirectory; // eax
  bool v30; // al
  int v31; // eax
  PSID v32; // rbx
  int SecureInboxLockScreenPath; // eax
  wil::details::in1diag3 *v34; // rcx
  __int64 v35; // rdx
  bool v36; // al
  CLockScreen *v37; // rcx
  unsigned __int16 HistoryEntryAt; // si
  int v39; // eax
  unsigned int i; // eax
  unsigned int j; // ecx
  PSID v42; // rbx
  int v43; // r14d
  PSID v44; // rsi
  unsigned __int64 v45; // rbx
  unsigned __int64 v46; // rsi
  unsigned __int64 v47; // r15
  WCHAR *v48; // rdx
  WCHAR *v49; // rcx
  unsigned __int64 v50; // r8
  __int64 v51; // r9
  WCHAR *v52; // r11
  WCHAR v53; // ax
  __int64 v54; // r10
  WCHAR *v55; // rcx
  __int64 v56; // r15
  bool v57; // cf
  PSID v58; // rsi
  unsigned __int64 v59; // rsi
  _WORD *v60; // rax
  _WORD *v61; // r11
  WCHAR *v62; // rcx
  unsigned __int64 v63; // rdx
  WCHAR *v64; // r8
  __int64 v65; // r9
  WCHAR v66; // ax
  __int64 v67; // r10
  WCHAR *v68; // rcx
  __int64 v69; // rsi
  PSID v70; // rbx
  int v71; // eax
  unsigned __int16 v72; // r14
  PSID v73; // rbx
  int v74; // eax
  bool v75; // si
  const wchar_t *v76; // rcx
  const wchar_t *v77; // rax
  HRESULT v78; // eax
  struct Windows::Storage::Streams::IRandomAccessStream **v79; // r15
  bool v80; // r14
  bool v81; // bl
  HRESULT Instance; // eax
  int ImageWithWIC; // eax
  bool v84; // cl
  unsigned __int16 *v85; // rsi
  unsigned int v86; // ebx
  unsigned int v87; // r12d
  int v88; // eax
  int v89; // eax
  int StreamOfWICBitmapSourceWithOptions; // eax
  GUID *v91; // rbx
  __int64 v92; // rdx
  HRESULT v93; // eax
  LPWSTR v94; // r9
  int OnlyRandomAccessStreamOverStream; // eax
  struct IStream *v96; // rcx
  struct IStream *v97; // rcx
  char v98; // di
  int v99; // eax
  __int64 v100; // rdx
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  LPDWORD pdwTypea; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-E0h]
  int pdwTypec; // [rsp+20h] [rbp-E0h]
  int pdwTyped; // [rsp+20h] [rbp-E0h]
  int pdwTypee; // [rsp+20h] [rbp-E0h]
  bool v108; // [rsp+40h] [rbp-C0h]
  bool v109[7]; // [rsp+41h] [rbp-BFh] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-B8h] BYREF
  char v111; // [rsp+50h] [rbp-B0h]
  unsigned int v112; // [rsp+51h] [rbp-AFh] BYREF
  WINBOOL IsMember[2]; // [rsp+58h] [rbp-A8h] BYREF
  PSID hMem; // [rsp+60h] [rbp-A0h] BYREF
  PSID v115; // [rsp+68h] [rbp-98h] BYREF
  PSID Sid; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v118; // [rsp+80h] [rbp-80h]
  unsigned int v119; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v120; // [rsp+8Ch] [rbp-74h]
  PCWSTR v121; // [rsp+90h] [rbp-70h] BYREF
  LPWSTR StringSid; // [rsp+98h] [rbp-68h] BYREF
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v124; // [rsp+A8h] [rbp-58h]
  struct Windows::Storage::Streams::IRandomAccessStream **v125[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 SidToCheck; // [rsp+C0h] [rbp-40h] BYREF
  int v127; // [rsp+C8h] [rbp-38h]
  void **v128; // [rsp+D0h] [rbp-30h] BYREF
  char v129[264]; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD *v130; // [rsp+1E0h] [rbp+E0h]
  _DWORD *v131; // [rsp+1E8h] [rbp+E8h] BYREF
  char v132[24]; // [rsp+1F0h] [rbp+F0h] BYREF
  int v133; // [rsp+208h] [rbp+108h]
  WCHAR pszPath[264]; // [rsp+220h] [rbp+120h] BYREF
  WCHAR pszFile[264]; // [rsp+430h] [rbp+330h] BYREF
  WCHAR pszMore[64]; // [rsp+640h] [rbp+540h] BYREF
  unsigned __int16 v137[264]; // [rsp+6C0h] [rbp+5C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+928h] [rbp+828h]

  v119 = a4;
  v120 = a3;
  v7 = a2;
  v118 = a2;
  v124 = a1;
  SRWLock = a6;
  v125[0] = a7;
  wil::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    &v128,
    "GetImageForUserActivity");
  v128 = &LockScreenTelemetry::GetImageForUserActivity::`vftable';
  LockScreenTelemetry::GetImageForUserActivity::StartActivity(
    (LockScreenTelemetry::GetImageForUserActivity *)&v128,
    v7 != 0,
    a5,
    a6 != 0,
    a7 != 0);
  v10 = 0;
  if ( a6 )
    a6->Ptr = 0;
  if ( a7 )
    *a7 = 0;
  v121 = 0;
  if ( !CreativeFramework::Policy::IsContentDeliveryPolicyEnforced(v9) )
    goto LABEL_12;
  pcbData[0] = 520;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Policies\\Microsoft\\Windows\\Personalization",
             L"LockScreenImage",
             2u,
             0,
             pszPath,
             pcbData);
  v14 = ValueW < 0;
  if ( ValueW )
  {
    pszPath[0] = 0;
    if ( ValueW > 0 )
      v14 = 1;
  }
  if ( v14 || (int)_AllocString<CTCoAllocPolicy>(v13, v12, pszPath, &v121) < 0 )
  {
LABEL_12:
    v15 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v121,
      0);
    v16 = (int)LockScreenPathFromMDMPolicy((unsigned __int16 **)&v121) >= 0;
  }
  else
  {
    v15 = 1;
    v16 = 0;
  }
  v109[1] = 0;
  v109[3] = 0;
  v111 = 0;
  pv = 0;
  Sid = 0;
  v115 = 0;
  StringSid = 0;
  LocalSystemUserSid = 0;
  pcbData[0] = 0;
  v109[2] = 0;
  SidToCheck = 0x500000000000101LL;
  v127 = 18;
  IsMember[0] = 0;
  v18 = CheckTokenMembership(0, &SidToCheck, IsMember) && IsMember[0];
  v108 = v18;
  LOBYTE(v112) = v18;
  if ( v16 )
  {
    Sid = 0;
    LocalSystemUserSid = CLockScreenHistory::s_GetLocalSystemUserSid(&Sid);
    pcbData[0] = LocalSystemUserSid;
    v19 = (WCHAR *)v121;
    v20 = Sid;
    if ( LocalSystemUserSid >= 0 )
    {
      LocalSystemUserSid = CLockScreenHistory::s_GetSecureLockScreenDirectory(
                             Sid,
                             0x50u,
                             v108,
                             pszFile,
                             (unsigned int)pdwType);
      pcbData[0] = LocalSystemUserSid;
      if ( LocalSystemUserSid >= 0 )
      {
        LocalSystemUserSid = CLockScreenHistory::s_GetSecureCustomLockScreenPath(
                               v20,
                               0x50u,
                               1,
                               0,
                               (unsigned __int16 **)&pv);
        pcbData[0] = LocalSystemUserSid;
        if ( LocalSystemUserSid >= 0 )
        {
          if ( ConvertSidToStringSidW(v20, &StringSid)
            || (LocalSystemUserSid = ResultFromKnownLastError(), pcbData[0] = LocalSystemUserSid,
                                                                 LocalSystemUserSid >= 0) )
          {
            LocalSystemUserSid = CLockScreenHistory::_InitOrUpdateGPImages((CLockScreenHistory *)(a1 + 144), v19);
            pcbData[0] = LocalSystemUserSid;
          }
        }
      }
    }
    LockScreenTelemetry::GetImageForUserActivity::UsePolicyImagePath<long &>(&v128, pcbData);
    if ( v20 )
      LocalFree(v20);
    goto LABEL_26;
  }
  v19 = (WCHAR *)v121;
  v23 = 79;
  if ( v15 || (a5 & 4) == 0 )
    goto LABEL_66;
  if ( !v7 )
    goto LABEL_171;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl'::`2'::impl);
  IsSpotlightEnabled = CLockScreen::_s_IsSpotlightEnabled((CreativeFramework::LockScreenCreativeConfigHelpers *)v7);
  v109[1] = IsSpotlightEnabled;
  v109[0] = IsSpotlightEnabled;
  if ( IsSpotlightEnabled )
  {
    hMem = 0;
    if ( ConvertStringSidToSidW(v7, &hMem) )
      Error = 0;
    else
      Error = ResultFromKnownLastError();
    IsMember[0] = Error;
    if ( Error < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB64,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)Error,
        (int)pdwType);
LABEL_63:
      LockScreenTelemetry::GetImageForUserActivity::UseSpotlightImagePath<long &,bool &,bool &,bool const &>(
        (unsigned int)&v128,
        (unsigned int)IsMember,
        (unsigned int)v109,
        (unsigned int)&v109[3],
        (__int64)&v112);
      if ( hMem )
        LocalFree(hMem);
      goto LABEL_65;
    }
    v109[0] = 0;
    Sid = 0;
    CreativeLockScreenPath = CLockScreenHistory::s_GetCreativeLockScreenPath(
                               (CreativeFramework::LockScreenCreativeConfigHelpers *)v7,
                               (unsigned __int16 **)&Sid,
                               (unsigned __int16 **)&pv,
                               (unsigned __int16 **)&v115,
                               v109);
    v27 = CreativeLockScreenPath;
    IsMember[0] = CreativeLockScreenPath;
    if ( CreativeLockScreenPath >= 0 )
    {
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl'::`2'::impl);
      if ( (a5 & 8) == 0 || v109[0] )
      {
        SecureLockScreenDirectory = CLockScreenHistory::s_GetSecureLockScreenDirectory(
                                      hMem,
                                      0x4Fu,
                                      v108,
                                      pszFile,
                                      pdwTypeb);
        v27 = SecureLockScreenDirectory;
        if ( SecureLockScreenDirectory < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xB6E,
            (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
            (const char *)(unsigned int)SecureLockScreenDirectory,
            pdwTypeb);
        IsMember[0] = v27;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB6B,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)CreativeLockScreenPath,
        pdwTypeb);
    }
    LOBYTE(v28) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage>::GetImpl'::`2'::impl,
      v28);
    v109[3] = (CreativeFramework::LockScreenCreativeConfigHelpers::GetLockImageFlags(v118) & 2) != 0;
    v30 = v108;
    if ( !v109[3] && v108 )
    {
      v31 = StringCchPrintfW(pszPath, 0x104u, L"%s_%c", L"LockScreen");
      if ( v31 >= 0 )
        DeleteSystemDataFolderForUser(hMem, 1u, pszPath);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB77,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)v31,
        79);
      v30 = v108;
    }
    v32 = Sid;
    if ( v27 >= 0 )
    {
      v109[1] = 1;
      v109[0] = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl'::`2'::impl);
      if ( v32 )
      {
        SidToCheck = (__int64)v32;
        LockScreenTelemetry::GetImageForUserActivity::UseSpotlightContentId<unsigned short *>(&v128, &SidToCheck);
      }
      goto LABEL_60;
    }
    v111 = 1;
    SecureInboxLockScreenPath = CLockScreenHistory::s_GetSecureLockScreenDirectory(hMem, 0x5Au, v30, pszFile, pdwTypeb);
    IsMember[0] = SecureInboxLockScreenPath;
    v34 = retaddr;
    if ( SecureInboxLockScreenPath >= 0 )
    {
      SecureInboxLockScreenPath = CLockScreenHistory::s_GetSecureInboxLockScreenPath(0x5Au, (unsigned __int16 **)&pv);
      IsMember[0] = SecureInboxLockScreenPath;
      v34 = retaddr;
      if ( SecureInboxLockScreenPath >= 0 )
      {
        LockScreenTelemetry::GetImageForUserActivity::UseSpotlightContentId<unsigned short const (&)[8]>(&v128);
        v36 = 1;
        v109[2] = a5 & 1;
        goto LABEL_59;
      }
      v35 = 2957;
    }
    else
    {
      v35 = 2954;
    }
    wil::details::in1diag3::_Log_Hr(
      v34,
      (void *)v35,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
      (const char *)(unsigned int)SecureInboxLockScreenPath,
      pdwTypec);
    v36 = 0;
LABEL_59:
    v109[0] = v36;
    v109[1] = v36;
LABEL_60:
    if ( v32 )
      CoTaskMemFree(v32);
    IsSpotlightEnabled = v109[1];
    v7 = v118;
    Sid = v115;
    goto LABEL_63;
  }
LABEL_65:
  if ( IsSpotlightEnabled )
    goto LABEL_188;
LABEL_66:
  if ( !v7 || (unsigned int)SHWindowsPolicy(POLID_NoChangingLockScreen) )
  {
LABEL_171:
    hMem = 0;
    LocalSystemUserSid = CLockScreenHistory::s_GetLocalSystemUserSid(&hMem);
    pcbData[0] = LocalSystemUserSid;
    if ( LocalSystemUserSid < 0 )
    {
LABEL_187:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
      goto LABEL_188;
    }
    v72 = String2[0];
    if ( v15 )
      v72 = 80;
    LOWORD(IsMember[0]) = v72;
    v73 = hMem;
    LocalSystemUserSid = CLockScreenHistory::s_GetSecureLockScreenDirectory(
                           hMem,
                           v72,
                           v108,
                           pszFile,
                           (unsigned int)pdwType);
    pcbData[0] = LocalSystemUserSid;
    if ( LocalSystemUserSid >= 0 )
    {
      v74 = v15
          ? CLockScreenHistory::s_GetSecureCustomLockScreenPath(v73, v72, 1, 0, (unsigned __int16 **)&pv)
          : CLockScreenHistory::s_GetSecureInboxLockScreenPath(v72, (unsigned __int16 **)&pv);
      LocalSystemUserSid = v74;
      pcbData[0] = v74;
      if ( v74 >= 0 )
      {
        if ( ConvertSidToStringSidW(v73, &StringSid) )
        {
          LocalSystemUserSid = 0;
          pcbData[0] = 0;
          goto LABEL_182;
        }
        LocalSystemUserSid = ResultFromKnownLastError();
        pcbData[0] = LocalSystemUserSid;
        if ( LocalSystemUserSid >= 0 )
        {
LABEL_182:
          v109[2] = a5 & 1;
          if ( v15 )
          {
            LocalSystemUserSid = CLockScreenHistory::_InitOrUpdateGPImages((CLockScreenHistory *)(v124 + 144), v19);
            pcbData[0] = LocalSystemUserSid;
          }
          else
          {
            v109[2] = a5 & 1;
          }
          goto LABEL_186;
        }
        v109[2] = a5 & 1;
      }
    }
LABEL_186:
    LockScreenTelemetry::GetImageForUserActivity::UseLocalSystemImagePath<long &,unsigned short const &>(
      &v128,
      pcbData,
      IsMember);
    goto LABEL_187;
  }
  v115 = 0;
  if ( ConvertStringSidToSidW(v7, &v115) )
    LocalSystemUserSid = 0;
  else
    LocalSystemUserSid = ResultFromKnownLastError();
  pcbData[0] = LocalSystemUserSid;
  if ( LocalSystemUserSid >= 0 )
  {
    hMem = 0;
    if ( (int)CLockScreenHistory::_s_GetLockScreenHistoryOrderInternal(v115, 1, (unsigned __int16 **)&hMem) < 0 )
    {
      HistoryEntryAt = String2[0];
    }
    else
    {
      HistoryEntryAt = *(_WORD *)hMem;
      CoTaskMemFree(hMem);
    }
    LOWORD(IsMember[0]) = HistoryEntryAt;
    if ( HistoryEntryAt == 79 )
    {
      v39 = CLockScreen::_RemoveCreativeHistoryEntryForUser(v37, v115);
      if ( v39 >= 0 )
      {
        HistoryEntryAt = CLockScreenHistory::s_GetHistoryEntryAt(0, v115);
        LOWORD(IsMember[0]) = HistoryEntryAt;
        v23 = HistoryEntryAt;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBC3,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)v39,
          (int)pdwType);
      }
    }
    else
    {
      v23 = HistoryEntryAt;
    }
    for ( i = 0; i < 6; ++i )
    {
      if ( HistoryEntryAt == word_1801357F0[20 * i] )
        goto LABEL_152;
    }
    if ( v23 == 80 )
    {
LABEL_152:
      hMem = 0;
      LocalSystemUserSid = CLockScreenHistory::s_GetLocalSystemUserSid(&hMem);
      pcbData[0] = LocalSystemUserSid;
      if ( LocalSystemUserSid >= 0 )
      {
        v70 = hMem;
        LocalSystemUserSid = CLockScreenHistory::s_GetSecureLockScreenDirectory(
                               hMem,
                               HistoryEntryAt,
                               v108,
                               pszFile,
                               (unsigned int)pdwType);
        pcbData[0] = LocalSystemUserSid;
        if ( LocalSystemUserSid >= 0 )
        {
          v71 = v23 == 80
              ? CLockScreenHistory::s_GetSecureCustomLockScreenPath(v70, HistoryEntryAt, 1, 0, (unsigned __int16 **)&pv)
              : CLockScreenHistory::s_GetSecureInboxLockScreenPath(HistoryEntryAt, (unsigned __int16 **)&pv);
          LocalSystemUserSid = v71;
          pcbData[0] = v71;
          if ( v71 >= 0 )
          {
            if ( ConvertSidToStringSidW(v70, &StringSid) )
              LocalSystemUserSid = 0;
            else
              LocalSystemUserSid = ResultFromKnownLastError();
            pcbData[0] = LocalSystemUserSid;
            if ( v23 == 80 || (v109[2] = 1, (a5 & 1) == 0) )
              v109[2] = 0;
            if ( LocalSystemUserSid >= 0 && v23 == 80 && v15 )
            {
              LocalSystemUserSid = CLockScreenHistory::_InitOrUpdateGPImages((CLockScreenHistory *)(v124 + 144), v19);
              pcbData[0] = LocalSystemUserSid;
            }
          }
        }
      }
      LockScreenTelemetry::GetImageForUserActivity::UseInboxImagePath<long &,unsigned short &>(&v128, pcbData, IsMember);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
      goto LABEL_169;
    }
    for ( j = 0; j < 7; ++j )
    {
      if ( HistoryEntryAt == aAbcdefg[j] )
      {
        v42 = v115;
        v43 = HistoryEntryAt;
        LODWORD(pdwType) = HistoryEntryAt;
        LocalSystemUserSid = StringCchPrintfW(pszPath, 0x104u, L"%s_%c", L"LockScreen");
        if ( LocalSystemUserSid >= 0 )
          LocalSystemUserSid = GetSystemDataFolderForUser(v42, pszPath, 1u, pszFile, (__int64)pdwType, v108);
        pcbData[0] = LocalSystemUserSid;
        if ( LocalSystemUserSid >= 0 )
        {
          v44 = v115;
          pv = 0;
          LODWORD(pdwType) = v43;
          LocalSystemUserSid = StringCchPrintfW(v137, 0x104u, L"%s_%c", L"LockScreen");
          v45 = -1;
          if ( LocalSystemUserSid >= 0 )
          {
            LocalSystemUserSid = GetSystemDataFolderForUser(v44, v137, 1u, pszPath, (__int64)pdwType, v108);
            if ( LocalSystemUserSid >= 0 )
            {
              LocalSystemUserSid = PathCchAppend(pszPath, 0x104u, L"LockScreen.jpg");
              if ( LocalSystemUserSid >= 0 )
              {
                v46 = -1;
                do
                  ++v46;
                while ( pszPath[v46] );
                v47 = v46 + 1;
                if ( v46 + 1 >= v46 && (SidToCheck = 0, is_mul_ok(v47, 2u)) )
                {
                  v48 = (WCHAR *)CoTaskMemAlloc(2 * v47);
                  pv = v48;
                  LocalSystemUserSid = 0;
                  if ( v48 )
                  {
                    if ( v47 <= 0x7FFFFFFF )
                    {
                      if ( v46 < 0x7FFFFFFF )
                      {
                        v49 = pszPath;
                        v50 = v46 + 1;
                        v51 = 0;
                        v52 = v48;
                        do
                        {
                          if ( !v46 )
                            break;
                          v53 = *v49;
                          if ( !*v49 )
                            break;
                          ++v49;
                          *v48++ = v53;
                          --v46;
                          ++v51;
                          --v50;
                        }
                        while ( v50 );
                        v54 = v51 - 1;
                        if ( v50 )
                          v54 = v51;
                        v55 = v48 - 1;
                        if ( v50 )
                          v55 = v48;
                        *v55 = 0;
                        if ( v50 )
                        {
                          v57 = v47 == v54;
                          v56 = v47 - v54;
                          if ( !v57 && v56 != 1 && (unsigned __int64)(2 * v56) > 2 )
                            memset_0(&v52[v54 + 1], 0, 2 * v56 - 2);
                        }
                      }
                      else if ( v46 != -1 )
                      {
                        *v48 = 0;
                      }
                    }
                    else
                    {
                      *v48 = 0;
                    }
                  }
                  else
                  {
                    LocalSystemUserSid = -2147024882;
                  }
                }
                else
                {
                  LocalSystemUserSid = -2147024362;
                }
              }
            }
          }
          pcbData[0] = LocalSystemUserSid;
          if ( LocalSystemUserSid >= 0 )
          {
            v58 = v115;
            Sid = 0;
            LODWORD(pdwType) = v43;
            LocalSystemUserSid = StringCchPrintfW(v137, 0x104u, L"%s_%c", L"LockScreen");
            if ( LocalSystemUserSid >= 0 )
            {
              LocalSystemUserSid = GetSystemDataFolderForUser(v58, v137, 1u, pszPath, (__int64)pdwType, v108);
              if ( LocalSystemUserSid >= 0 )
              {
                LocalSystemUserSid = PathCchAppend(pszPath, 0x104u, L"LockScreenPortrait.jpg");
                if ( LocalSystemUserSid >= 0 )
                {
                  do
                    ++v45;
                  while ( pszPath[v45] );
                  v59 = v45 + 1;
                  if ( v45 + 1 >= v45 && (SidToCheck = 0, is_mul_ok(v59, 2u)) )
                  {
                    v60 = CoTaskMemAlloc(2 * v59);
                    v61 = v60;
                    Sid = v60;
                    LocalSystemUserSid = 0;
                    if ( v60 )
                    {
                      if ( v59 <= 0x7FFFFFFF )
                      {
                        if ( v45 < 0x7FFFFFFF )
                        {
                          v62 = pszPath;
                          v63 = v45 + 1;
                          v64 = v60;
                          v65 = 0;
                          do
                          {
                            if ( !v45 )
                              break;
                            v66 = *v62;
                            if ( !*v62 )
                              break;
                            ++v62;
                            *v64++ = v66;
                            --v45;
                            ++v65;
                            --v63;
                          }
                          while ( v63 );
                          v67 = v65 - 1;
                          if ( v63 )
                            v67 = v65;
                          v68 = v64 - 1;
                          if ( v63 )
                            v68 = v64;
                          *v68 = 0;
                          if ( v63 )
                          {
                            v57 = v59 == v67;
                            v69 = v59 - v67;
                            if ( !v57 && v69 != 1 && (unsigned __int64)(2 * v69) > 2 )
                              memset_0(&v61[v67 + 1], 0, 2 * v69 - 2);
                          }
                        }
                        else if ( v45 != -1 )
                        {
                          *v60 = 0;
                        }
                      }
                      else
                      {
                        *v60 = 0;
                      }
                    }
                    else
                    {
                      LocalSystemUserSid = -2147024882;
                    }
                  }
                  else
                  {
                    LocalSystemUserSid = -2147024362;
                  }
                }
              }
            }
            if ( LocalSystemUserSid < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xBEF,
                (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
                (const char *)(unsigned int)LocalSystemUserSid,
                (int)pdwType);
            pcbData[0] = LocalSystemUserSid;
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xBEC,
              (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
              (const char *)(unsigned int)LocalSystemUserSid,
              (int)pdwType);
          }
        }
        LockScreenTelemetry::GetImageForUserActivity::UseCustomImagePath<long &,unsigned short &>(
          &v128,
          pcbData,
          IsMember);
        break;
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBBC,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
      (const char *)(unsigned int)LocalSystemUserSid,
      (int)pdwType);
  }
LABEL_169:
  if ( v115 )
    LocalFree(v115);
LABEL_188:
  v10 = (unsigned __int16 *)Sid;
  if ( !Sid )
  {
LABEL_26:
    v21 = 0;
    goto LABEL_27;
  }
  v21 = 1;
LABEL_27:
  LOBYTE(v112) = v21;
  v109[0] = pv != 0;
  LOBYTE(IsMember[0]) = 1;
  LockScreenTelemetry::GetImageForUserActivity::ImagePathFound<long &,bool,bool,bool>(
    (unsigned int)&v128,
    (unsigned int)pcbData,
    (unsigned int)IsMember,
    (unsigned int)v109,
    (__int64)&v112);
  if ( LocalSystemUserSid < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBFA,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
      (const char *)(unsigned int)LocalSystemUserSid,
      (int)pdwTypea);
    v22 = LocalSystemUserSid;
    goto LABEL_246;
  }
  v75 = (a5 & 2) != 0;
  v76 = &Class;
  if ( (a5 & 2) == 0 )
    v76 = L"_notdimmed";
  v77 = L"_flipped";
  if ( !v109[2] )
    v77 = &Class;
  LODWORD(pdwTypea) = v119;
  v78 = StringCchPrintfW(pszMore, 0x40u, L"LockScreen___%4.4u_%4.4u%s%s.jpg", v120, pdwTypea, v77, v76);
  LocalSystemUserSid = v78;
  if ( v78 >= 0 )
  {
    v78 = PathCchAppend(pszFile, 0x104u, pszMore);
    LocalSystemUserSid = v78;
  }
  v22 = v78;
  *(_QWORD *)pcbData = 0;
  if ( v78 >= 0 )
  {
    v79 = v125[0];
    v80 = v109[1];
    v81 = v109[3];
    if ( v125[0] && (!v109[1] || v109[3] || v111) )
    {
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(pcbData);
      if ( SHCreateStreamOnFileW(pszFile, 0, (IStream **)pcbData) >= 0 )
      {
        LocalSystemUserSid = CreateReadOnlyRandomAccessStreamOverStream(*(struct IStream **)pcbData, v79);
        v22 = LocalSystemUserSid;
        goto LABEL_244;
      }
    }
    *(_QWORD *)IsMember = 0;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(IsMember);
    Instance = CoCreateInstance(
                 &CLSID_WICImagingFactory2,
                 0,
                 1u,
                 &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                 (LPVOID *)IsMember);
    LocalSystemUserSid = Instance;
    if ( Instance < 0 )
    {
      v22 = Instance;
      goto LABEL_243;
    }
    hMem = 0;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&hMem);
    ImageWithWIC = LoadImageWithWIC(
                     *(struct IWICImagingFactory **)IsMember,
                     (__int64)pszFile,
                     2,
                     (struct IWICBitmapSource **)&hMem,
                     0);
    LocalSystemUserSid = ImageWithWIC;
    if ( ImageWithWIC >= 0 && (!v80 || v81) )
    {
      v22 = ImageWithWIC;
      v85 = v118;
      goto LABEL_229;
    }
    v109[0] = 0;
    v115 = 0;
    v86 = v120;
    if ( !v10 )
      goto LABEL_213;
    v87 = v119;
    if ( v120 >= v119 )
      goto LABEL_213;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v115);
    v88 = CLockScreen::_s_LoadAndScaleBitmapSource(
            *(struct IWICImagingFactory **)IsMember,
            v10,
            v86,
            v87,
            v75,
            (struct IWICBitmapSource **)&v115,
            v109);
    LocalSystemUserSid = v88;
    if ( v88 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC2C,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)v88,
        pdwTyped);
    if ( !v115 )
    {
LABEL_213:
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v115);
      v89 = CLockScreen::_s_LoadAndScaleBitmapSource(
              *(struct IWICImagingFactory **)IsMember,
              (const unsigned __int16 *)pv,
              v86,
              v119,
              v75,
              (struct IWICBitmapSource **)&v115,
              v109);
      LocalSystemUserSid = v89;
      if ( v89 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xC31,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)v89,
          pdwTypee);
    }
    v22 = LocalSystemUserSid;
    if ( LocalSystemUserSid >= 0 )
    {
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&hMem);
      StreamOfWICBitmapSourceWithOptions = CLockScreen::_s_FlipBitmapSourceIfNecessary(
                                             *(struct IWICImagingFactory **)IsMember,
                                             (struct IWICBitmapSource *)v115,
                                             v109[2],
                                             (struct IWICBitmapSource **)&hMem);
      LocalSystemUserSid = StreamOfWICBitmapSourceWithOptions;
      if ( StreamOfWICBitmapSourceWithOptions >= 0 )
      {
        v91 = &GUID_ContainerFormatPng;
        if ( !v109[0] )
          v91 = &GUID_ContainerFormatJpeg;
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(pcbData);
        *(GUID *)v125 = GUID_WICPixelFormat32bppBGRA;
        StreamOfWICBitmapSourceWithOptions = GetStreamOfWICBitmapSourceWithOptions(*(_QWORD *)IsMember, hMem, v91, v125);
        LocalSystemUserSid = StreamOfWICBitmapSourceWithOptions;
        if ( StreamOfWICBitmapSourceWithOptions >= 0 && v108 )
        {
          LOBYTE(v92) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage>::GetImpl'::`2'::impl,
            v92);
          Sid = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&Sid);
          v93 = CoCreateInstance(
                  &CLSID_ImageSanitizationBroker,
                  0,
                  1u,
                  &GUID_f43f82aa_4498_463d_80e1_cc44cd4c6c14,
                  &Sid);
          LocalSystemUserSid = v93;
          v85 = v118;
          if ( v93 >= 0 )
          {
            v94 = StringSid;
            if ( !StringSid )
              v94 = v118;
            v93 = (*(__int64 (__fastcall **)(PSID, _QWORD, WCHAR *, LPWSTR, int, _QWORD))(*(_QWORD *)Sid + 32LL))(
                    Sid,
                    *(_QWORD *)pcbData,
                    pszFile,
                    v94,
                    6,
                    0);
            LocalSystemUserSid = v93;
          }
          v22 = v93;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&Sid);
          goto LABEL_228;
        }
      }
      v22 = StreamOfWICBitmapSourceWithOptions;
    }
    v85 = v118;
LABEL_228:
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v115);
LABEL_229:
    if ( v22 < 0 )
    {
LABEL_241:
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&hMem);
LABEL_243:
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(IsMember);
      goto LABEL_244;
    }
    if ( SRWLock )
    {
      OnlyRandomAccessStreamOverStream = ConvertWICBitmapToHBITMAP(
                                           *(struct IWICImagingFactory **)IsMember,
                                           (struct IWICBitmapSource *)hMem,
                                           (HBITMAP *)SRWLock);
LABEL_237:
      v22 = OnlyRandomAccessStreamOverStream;
      LocalSystemUserSid = OnlyRandomAccessStreamOverStream;
      goto LABEL_238;
    }
    if ( v79 )
    {
      v96 = *(struct IStream **)pcbData;
      if ( *(_QWORD *)pcbData )
      {
LABEL_236:
        OnlyRandomAccessStreamOverStream = CreateReadOnlyRandomAccessStreamOverStream(v96, v79);
        goto LABEL_237;
      }
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(pcbData);
      LocalSystemUserSid = SHCreateStreamOnFileW(pszFile, 0, (IStream **)pcbData);
      v22 = LocalSystemUserSid;
      if ( LocalSystemUserSid >= 0 )
      {
        v96 = *(struct IStream **)pcbData;
        goto LABEL_236;
      }
    }
LABEL_238:
    if ( v80 && !v111 )
      CLockScreen::_s_SetSpotlightImageCached(v84, v85);
    goto LABEL_241;
  }
LABEL_244:
  v97 = *(struct IStream **)pcbData;
  if ( *(_QWORD *)pcbData )
  {
    *(_QWORD *)pcbData = 0;
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v97 + 16LL))(v97);
  }
LABEL_246:
  CoTaskMemFree(v10);
  CoTaskMemFree(pv);
  LocalFree(StringSid);
  wil::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    &v128,
    (unsigned int)LocalSystemUserSid);
  if ( v19 )
    CoTaskMemFree(v19);
  v128 = &LockScreenTelemetry::GetImageForUserActivity::`vftable';
  if ( !v131 )
    goto LABEL_256;
  wil::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    &v128,
    &SRWLock);
  if ( v131 && *v131 == 1 )
  {
    v98 = 1;
  }
  else
  {
    v98 = 0;
    wil::details::shared_object<wil::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LockScreenLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v131);
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v98 )
  {
LABEL_256:
    if ( *v130 == 1 )
    {
      v99 = v130[22];
      v100 = 2147942974LL;
      if ( v99 < 0 )
        v100 = (unsigned int)v99;
      wil::ActivityBase<LockScreenLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LockScreenLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v130,
        v100,
        &v119);
      wil::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v128);
    }
  }
  if ( v133 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v132);
  wil::details::shared_object<wil::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LockScreenLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v131);
  wil::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LockScreenLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LockScreenLogging,_TlgReflectorTag_Param0IsProviderType>(v129);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x18000c600  push    rbp
0x18000c602  push    rbx
0x18000c603  push    rsi
0x18000c604  push    rdi
0x18000c605  push    r12
0x18000c607  push    r13
0x18000c609  push    r14
0x18000c60b  push    r15
0x18000c60d  lea     rbp, [rsp-7E8h]
0x18000c615  sub     rsp, 8E8h
0x18000c61c  mov     rax, cs:__security_cookie
0x18000c623  xor     rax, rsp
0x18000c626  mov     [rbp+820h+var_50], rax
0x18000c62d  mov     [rbp+820h+var_898], r9d
0x18000c631  mov     [rbp+820h+var_894], r8d
0x18000c635  mov     rsi, rdx
0x18000c638  mov     [rbp+820h+var_8A0], rdx
0x18000c63c  mov     r14, rcx
0x18000c63f  mov     [rbp+820h+var_878], rcx
0x18000c643  mov     r12, [rbp+820h+arg_28]
0x18000c64a  mov     [rbp+820h+SRWLock], r12
0x18000c64e  mov     r15, [rbp+820h+arg_30]
0x18000c655  mov     [rbp+820h+var_870], r15
0x18000c659  test    r15, r15
0x18000c65c  setnz   dil
0x18000c660  test    r12, r12
0x18000c663  setnz   bl
0x18000c666  lea     rdx, aGetimageforuse; "GetImageForUserActivity"
0x18000c66d  lea     rcx, [rbp+820h+var_850]
0x18000c671  call    ??0?$ActivityBase@VLockScreenLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000c676  lea     rax, ??_7GetImageForUserActivity@LockScreenTelemetry@@6B@; const LockScreenTelemetry::GetImageForUserActivity::`vftable'
0x18000c67d  mov     [rbp+820h+var_850], rax
0x18000c681  test    rsi, rsi
0x18000c684  setnz   dl; bool
0x18000c687  mov     byte ptr [rsp+920h+pdwType], dil; unsigned int
0x18000c68c  movzx   r9d, bl; bool
0x18000c690  mov     edi, [rbp+820h+arg_20]
0x18000c696  mov     r8d, edi; int
0x18000c699  lea     rcx, [rbp+820h+var_850]; this
0x18000c69d  call    ?StartActivity@GetImageForUserActivity@LockScreenTelemetry@@QEAAX_NH00@Z; LockScreenTelemetry::GetImageForUserActivity::StartActivity(bool,int,bool,bool)
0x18000c6a2  nop
0x18000c6a3  xor     r13d, r13d
0x18000c6a6  test    r12, r12
0x18000c6a9  jz      short loc_18000C6AF
0x18000c6ab  mov     [r12], r13
0x18000c6af  test    r15, r15
0x18000c6b2  jz      short loc_18000C6B7
0x18000c6b4  mov     [r15], r13
0x18000c6b7  mov     [rbp+820h+var_890], r13
0x18000c6bb  call    ?IsContentDeliveryPolicyEnforced@Policy@CreativeFramework@@YA_NXZ; CreativeFramework::Policy::IsContentDeliveryPolicyEnforced(void)
0x18000c6c0  test    al, al
0x18000c6c2  jz      short loc_18000C743
0x18000c6c4  mov     [rsp+920h+var_8D8], 208h
0x18000c6cc  lea     rax, [rsp+920h+var_8D8]
0x18000c6d1  mov     [rsp+920h+pcbData], rax; pcbData
0x18000c6d6  lea     rax, [rbp+820h+pszPath]
0x18000c6dd  mov     [rsp+920h+pvData], rax; pvData
0x18000c6e2  mov     [rsp+920h+pdwType], r13; pdwType
0x18000c6e7  mov     r9d, 2; dwFlags
0x18000c6ed  lea     r8, Value; "LockScreenImage"
0x18000c6f4  lea     rdx, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Windows"...
0x18000c6fb  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000c702  call    cs:__imp_RegGetValueW
0x18000c709  nop     dword ptr [rax+rax+00h]
0x18000c70e  test    eax, eax
0x18000c710  jz      short loc_18000C726
0x18000c712  mov     [rbp+820h+pszPath], r13w
0x18000c71a  jle     short loc_18000C726
0x18000c71c  movzx   eax, ax
0x18000c71f  or      eax, 80070000h
0x18000c724  test    eax, eax
0x18000c726  js      short loc_18000C743
0x18000c728  lea     r9, [rbp+820h+var_890]
0x18000c72c  lea     r8, [rbp+820h+pszPath]
0x18000c733  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000c738  test    eax, eax
0x18000c73a  js      short loc_18000C743
0x18000c73c  mov     r15b, 1
0x18000c73f  xor     bl, bl
0x18000c741  jmp     short loc_18000C75F
0x18000c743  xor     r15b, r15b
0x18000c746  xor     edx, edx
0x18000c748  lea     rcx, [rbp+820h+var_890]
0x18000c74c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000c751  lea     rcx, [rbp+820h+var_890]; unsigned __int16 **
0x18000c755  call    ?LockScreenPathFromMDMPolicy@@YAJPEAPEAG@Z; LockScreenPathFromMDMPolicy(ushort * *)
0x18000c75a  test    eax, eax
0x18000c75c  setns   bl
0x18000c75f  mov     [rsp+920h+var_8DF+1], 0
0x18000c764  mov     [rsp+920h+var_8DF+3], 0
0x18000c769  mov     [rsp+920h+var_8D0], 0
0x18000c76e  mov     [rsp+920h+pv], r13
0x18000c773  mov     [rsp+920h+Sid], r13
0x18000c778  mov     [rsp+920h+var_8B8], r13
0x18000c77d  xor     eax, eax
0x18000c77f  mov     [rbp+820h+StringSid], rax
0x18000c783  mov     r12d, eax
0x18000c786  mov     [rsp+920h+var_8D8], eax
0x18000c78a  mov     [rsp+920h+var_8DF+2], al
0x18000c78e  mov     dword ptr [rbp+820h+SidToCheck], 101h
0x18000c795  mov     dword ptr [rbp+820h+SidToCheck+4], 5000000h
0x18000c79c  mov     [rbp+820h+var_858], 12h
0x18000c7a3  mov     [rsp+920h+IsMember], eax
0x18000c7a7  lea     r8, [rsp+920h+IsMember]; IsMember
0x18000c7ac  lea     rdx, [rbp+820h+SidToCheck]; SidToCheck
0x18000c7b0  xor     ecx, ecx; TokenHandle
0x18000c7b2  call    cs:__imp_CheckTokenMembership
0x18000c7b9  nop     dword ptr [rax+rax+00h]
0x18000c7be  test    eax, eax
0x18000c7c0  jz      short loc_18000C7CD
0x18000c7c2  cmp     [rsp+920h+IsMember], r12d
0x18000c7c7  jz      short loc_18000C7CD
0x18000c7c9  mov     al, 1
0x18000c7cb  jmp     short loc_18000C7CF
0x18000c7cd  xor     al, al
0x18000c7cf  mov     [rsp+920h+var_8E0], al
0x18000c7d3  mov     byte ptr [rsp+920h+var_8CF], al
0x18000c7d7  test    bl, bl
0x18000c7d9  jz      loc_18000C91B
0x18000c7df  mov     [rsp+920h+Sid], 0
0x18000c7e8  lea     rcx, [rsp+920h+Sid]; void **
0x18000c7ed  call    ?s_GetLocalSystemUserSid@CLockScreenHistory@@SAJPEAPEAX@Z; CLockScreenHistory::s_GetLocalSystemUserSid(void * *)
0x18000c7f2  mov     r12d, eax
0x18000c7f5  mov     [rsp+920h+var_8D8], eax
0x18000c7f9  mov     rdi, [rbp+820h+var_890]
0x18000c7fd  mov     rbx, [rsp+920h+Sid]
0x18000c802  test    eax, eax
0x18000c804  js      loc_18000C893
0x18000c80a  mov     esi, 50h ; 'P'
0x18000c80f  mov     edx, esi; unsigned __int16
0x18000c811  lea     r9, [rbp+820h+pszFile]; unsigned __int16 *
0x18000c818  movzx   r8d, [rsp+920h+var_8E0]; bool
0x18000c81e  mov     rcx, rbx; void *
0x18000c821  call    ?s_GetSecureLockScreenDirectory@CLockScreenHistory@@SAJPEAXG_NPEAGI@Z; CLockScreenHistory::s_GetSecureLockScreenDirectory(void *,ushort,bool,ushort *,uint)
0x18000c826  mov     r12d, eax
0x18000c829  mov     [rsp+920h+var_8D8], eax
0x18000c82d  test    eax, eax
0x18000c82f  js      short loc_18000C893
0x18000c831  mov     edx, esi; unsigned __int16
0x18000c833  lea     rax, [rsp+920h+pv]
0x18000c838  mov     [rsp+920h+pdwType], rax; unsigned __int16 **
0x18000c83d  xor     r9d, r9d; bool
0x18000c840  mov     r8b, 1; bool
0x18000c843  mov     rcx, rbx; void *
0x18000c846  call    ?s_GetSecureCustomLockScreenPath@CLockScreenHistory@@SAJPEAXG_N1PEAPEAG@Z; CLockScreenHistory::s_GetSecureCustomLockScreenPath(void *,ushort,bool,bool,ushort * *)
0x18000c84b  mov     r12d, eax
0x18000c84e  mov     [rsp+920h+var_8D8], eax
0x18000c852  test    eax, eax
0x18000c854  js      short loc_18000C893
0x18000c856  lea     rdx, [rbp+820h+StringSid]; StringSid
0x18000c85a  mov     rcx, rbx; Sid
0x18000c85d  call    cs:__imp_ConvertSidToStringSidW
0x18000c864  nop     dword ptr [rax+rax+00h]
0x18000c869  test    eax, eax
0x18000c86b  jnz     short loc_18000C87D
0x18000c86d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000c872  mov     r12d, eax
0x18000c875  mov     [rsp+920h+var_8D8], eax
0x18000c879  test    eax, eax
0x18000c87b  js      short loc_18000C893
0x18000c87d  lea     rcx, [r14+90h]; this
0x18000c884  mov     rdx, rdi; pszPath
0x18000c887  call    ?_InitOrUpdateGPImages@CLockScreenHistory@@IEAAJPEBG@Z; CLockScreenHistory::_InitOrUpdateGPImages(ushort const *)
0x18000c88c  mov     r12d, eax
0x18000c88f  mov     [rsp+920h+var_8D8], eax
0x18000c893  lea     rdx, [rsp+920h+var_8D8]
0x18000c898  lea     rcx, [rbp+820h+var_850]
0x18000c89c  call    ??$UsePolicyImagePath@AEAJ@GetImageForUserActivity@LockScreenTelemetry@@QEAAXAEAJ@Z; LockScreenTelemetry::GetImageForUserActivity::UsePolicyImagePath<long &>(long &)
0x18000c8a1  nop
0x18000c8a2  test    rbx, rbx
0x18000c8a5  jz      short loc_18000C8B7
0x18000c8a7  mov     rcx, rbx; hMem
0x18000c8aa  call    cs:__imp_LocalFree
0x18000c8b1  nop     dword ptr [rax+rax+00h]
0x18000c8b6  nop
0x18000c8b7  xor     al, al
0x18000c8b9  mov     byte ptr [rsp+920h+var_8CF], al
0x18000c8bd  cmp     [rsp+920h+pv], 0
0x18000c8c3  setnz   [rsp+920h+var_8DF]
0x18000c8c8  mov     byte ptr [rsp+920h+IsMember], 1
0x18000c8cd  lea     rax, [rsp+920h+var_8CF]
0x18000c8d2  mov     [rsp+920h+pdwType], rax; int
0x18000c8d7  lea     r9, [rsp+920h+var_8DF]
0x18000c8dc  lea     r8, [rsp+920h+IsMember]
0x18000c8e1  lea     rdx, [rsp+920h+var_8D8]
0x18000c8e6  lea     rcx, [rbp+820h+var_850]
0x18000c8ea  call    ??$ImagePathFound@AEAJ_N_N_N@GetImageForUserActivity@LockScreenTelemetry@@QEAAXAEAJ$$QEA_N11@Z; LockScreenTelemetry::GetImageForUserActivity::ImagePathFound<long &,bool,bool,bool>(long &,bool &&,bool &&,bool &&)
0x18000c8ef  mov     rcx, [rbp+828h]; this
0x18000c8f6  test    r12d, r12d
0x18000c8f9  jns     loc_18000D44A
0x18000c8ff  mov     r9d, r12d; char *
0x18000c902  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18000c909  mov     edx, 0BFAh; void *
0x18000c90e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000c913  mov     ebx, r12d
0x18000c916  jmp     loc_18000D8C9
0x18000c91b  movzx   r13d, dil
0x18000c91f  and     r13b, 1
0x18000c923  mov     rdi, [rbp+820h+var_890]
0x18000c927  mov     r14d, 4Fh ; 'O'
0x18000c92d  test    r15b, r15b
0x18000c930  jnz     loc_18000CC3F
0x18000c936  test    byte ptr [rbp+820h+arg_20], 4
0x18000c93d  jz      loc_18000CC3F
0x18000c943  test    rsi, rsi
0x18000c946  jz      loc_18000D30C
0x18000c94c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3> `wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl(void)'::`2'::impl
0x18000c953  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18000c958  mov     rcx, rsi; this
0x18000c95b  call    ?_s_IsSpotlightEnabled@CLockScreen@@KA_NPEBG@Z; CLockScreen::_s_IsSpotlightEnabled(ushort const *)
0x18000c960  movzx   ebx, al
0x18000c963  mov     [rsp+920h+var_8DF+1], al
0x18000c967  mov     [rsp+920h+var_8DF], al
0x18000c96b  test    al, al
0x18000c96d  jz      loc_18000CC37
0x18000c973  mov     [rsp+920h+hMem], 0
0x18000c97c  lea     rdx, [rsp+920h+hMem]; Sid
0x18000c981  mov     rcx, rsi; StringSid
0x18000c984  call    cs:__imp_ConvertStringSidToSidW
0x18000c98b  nop     dword ptr [rax+rax+00h]
0x18000c990  test    eax, eax
0x18000c992  jz      short loc_18000C998
0x18000c994  xor     eax, eax
0x18000c996  jmp     short loc_18000C99D
0x18000c998  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000c99d  mov     [rsp+920h+IsMember], eax
0x18000c9a1  mov     rcx, [rbp+828h]; this
0x18000c9a8  test    eax, eax
0x18000c9aa  jns     short loc_18000C9C5
0x18000c9ac  mov     r9d, eax; char *
0x18000c9af  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18000c9b6  mov     edx, 0B64h; void *
0x18000c9bb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000c9c0  jmp     loc_18000CBFD
0x18000c9c5  mov     [rsp+920h+var_8DF], 0
0x18000c9ca  mov     [rsp+920h+Sid], 0
0x18000c9d3  lea     rax, [rsp+920h+var_8DF]
0x18000c9d8  mov     [rsp+920h+pdwType], rax; int
0x18000c9dd  lea     r9, [rsp+920h+var_8B8]; unsigned __int16 **
0x18000c9e2  lea     r8, [rsp+920h+pv]; unsigned __int16 **
0x18000c9e7  lea     rdx, [rsp+920h+Sid]; unsigned __int16 **
0x18000c9ec  mov     rcx, rsi; this
0x18000c9ef  call    ?s_GetCreativeLockScreenPath@CLockScreenHistory@@SAJPEBGPEAPEAG11PEA_N@Z; CLockScreenHistory::s_GetCreativeLockScreenPath(ushort const *,ushort * *,ushort * *,ushort * *,bool *)
0x18000c9f4  mov     esi, eax
0x18000c9f6  mov     [rsp+920h+IsMember], eax
0x18000c9fa  mov     rcx, [rbp+828h]; this
0x18000ca01  test    eax, eax
0x18000ca03  jns     short loc_18000CA1B
0x18000ca05  mov     r9d, eax; char *
0x18000ca08  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18000ca0f  mov     edx, 0B6Bh; void *
0x18000ca14  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ca19  jmp     short loc_18000CA76
0x18000ca1b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3> `wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl(void)'::`2'::impl
0x18000ca22  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18000ca27  test    byte ptr [rbp+820h+arg_20], 8
0x18000ca2e  jz      short loc_18000CA37
0x18000ca30  cmp     [rsp+920h+var_8DF], 0
0x18000ca35  jz      short loc_18000CA76
0x18000ca37  mov     edx, r14d; unsigned __int16
0x18000ca3a  lea     r9, [rbp+820h+pszFile]; unsigned __int16 *
0x18000ca41  movzx   r8d, [rsp+920h+var_8E0]; bool
0x18000ca47  mov     rcx, [rsp+920h+hMem]; void *
0x18000ca4c  call    ?s_GetSecureLockScreenDirectory@CLockScreenHistory@@SAJPEAXG_NPEAGI@Z; CLockScreenHistory::s_GetSecureLockScreenDirectory(void *,ushort,bool,ushort *,uint)
0x18000ca51  mov     esi, eax
0x18000ca53  mov     rcx, [rbp+828h]; this
0x18000ca5a  test    eax, eax
0x18000ca5c  jns     short loc_18000CA72
0x18000ca5e  mov     r9d, eax; char *
0x18000ca61  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18000ca68  mov     edx, 0B6Eh; void *
0x18000ca6d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ca72  mov     [rsp+920h+IsMember], esi
0x18000ca76  mov     dl, 1
0x18000ca78  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage> `wil::Feature<__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage>::GetImpl(void)'::`2'::impl
0x18000ca7f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000ca84  mov     rcx, [rbp+820h+var_8A0]
0x18000ca88  call    ?GetLockImageFlags@LockScreenCreativeConfigHelpers@CreativeFramework@@YA?AW4LockImageFlags@12@PEBG@Z; CreativeFramework::LockScreenCreativeConfigHelpers::GetLockImageFlags(ushort const *)
0x18000ca8d  bt      eax, 1
0x18000ca91  setb    [rsp+920h+var_8DF+3]
0x18000ca96  bt      eax, 1
0x18000ca9a  movzx   eax, [rsp+920h+var_8E0]
0x18000ca9f  jb      short loc_18000CB15
0x18000caa1  test    al, al
0x18000caa3  jz      short loc_18000CB15
0x18000caa5  mov     dword ptr [rsp+920h+pdwType], r14d
0x18000caaa  lea     r9, aLockscreen; "LockScreen"
0x18000cab1  lea     r8, aSC; "%s_%c"
0x18000cab8  mov     edx, 104h; unsigned __int64
0x18000cabd  lea     rcx, [rbp+820h+pszPath]; unsigned __int16 *
0x18000cac4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000cac9  mov     rcx, [rbp+828h]
0x18000cad0  test    eax, eax
0x18000cad2  jns     short loc_18000CADB
0x18000cad4  mov     edx, 0B77h
0x18000cad9  jmp     short loc_18000CB01
0x18000cadb  lea     r8, [rbp+820h+pszPath]
0x18000cae2  mov     edx, 1
0x18000cae7  mov     rcx, [rsp+920h+hMem]
0x18000caec  call    ?DeleteSystemDataFolderForUser@@YAJPEAXW4SYSTEM_DATA_FOLDER_USER_ACCESS@@PEBG_N@Z; DeleteSystemDataFolderForUser(void *,SYSTEM_DATA_FOLDER_USER_ACCESS,ushort const *,bool)
  ... truncated ...
```
