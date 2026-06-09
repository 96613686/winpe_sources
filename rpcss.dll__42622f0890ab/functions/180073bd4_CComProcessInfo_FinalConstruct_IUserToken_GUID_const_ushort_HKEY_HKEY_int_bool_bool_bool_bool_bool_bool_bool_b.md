# CComProcessInfo::FinalConstruct(IUserToken *,_GUID const &,ushort *,HKEY__ *,HKEY__ *,int,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool)

- ea: `0x180073bd4`
- end: `0x180075abb`
- name: `?FinalConstruct@CComProcessInfo@@QEAAJPEAUIUserToken@@AEBU_GUID@@PEAGPEAUHKEY__@@3H_N44444444444@Z`
- size: `7911`
- prototype: `__int64 __fastcall(CComProcessInfo *this, struct IUserToken *, const struct _GUID *, unsigned __int16 *, HKEY hkey, HKEY, int, bool, bool, bool, bool, bool, bool, bool, bool, bool, bool, bool, bool)`
- caller_count: `1`
- callee_count: `39`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004b560`

## callees

- `0x180005c40`
- `0x18000b310`
- `0x18000b428`
- `0x18000b924`
- `0x18000d858`
- `0x18000ea80`
- `0x18000ed44`
- `0x180016160`
- `0x180018344`
- `0x18001ae64`
- `0x18001af6c`
- `0x18002f66c`
- `0x18002fa6c`
- `0x180034540`
- `0x1800418c0`
- `0x180043850`
- `0x18004778c`
- `0x1800566cc`
- `0x18005e9e8`
- `0x18005fb44`
- `0x18006d90c`
- `0x180073bd4`
- `0x18007ced0`
- `0x18008150c`
- `0x180098b54`
- `0x18009e490`
- `0x1800a1e98`
- `0x1800a228c`
- `0x1800b27e0`
- `0x1800b3128`
- `0x1800cb210`
- `0x1800ccb70`
- `0x1800ce47c`
- `0x1800e7a58`
- `0x1800e7ad0`
- `0x1800e7b3c`
- `0x1800e7ca4`
- `0x1800e7dc0`
- `0x18010b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180073fe3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180073fe3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074117`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800741a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007426c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800742ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074dc6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074117`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800741a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007426c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800742ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074dc6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007462d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074695`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074d65`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007462d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074695`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074d65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180074eb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800751f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180074eb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800751f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074810`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074fb0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074810`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074fb0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007485e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074b13`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074c5f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074d2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074daa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074fed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180075047`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180075231`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007534b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180075409`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800754de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800758ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007485e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074b13`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074c5f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074d2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074daa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074fed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180075047`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180075231`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007534b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180075409`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800754de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800758ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800740e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074156`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800742a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800740e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074156`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800742a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180073e4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180074247`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180073e4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180074247`

## string_xrefs

- `0x180073d5c`: `LocalService`
- `0x180073dbc`: `LocalService`
- `0x180073ca6`: `CComProcessInfo::FinalConstruct`
- `0x180073d1b`: `CComProcessInfo::FinalConstruct`
- `0x180073eb6`: `CComProcessInfo::FinalConstruct`
- `0x180074032`: `CComProcessInfo::FinalConstruct`
- `0x180074361`: `CComProcessInfo::FinalConstruct`
- `0x1800743b4`: `CComProcessInfo::FinalConstruct`
- `0x180074524`: `CComProcessInfo::FinalConstruct`
- `0x18007456e`: `CComProcessInfo::FinalConstruct`
- `0x1800745b2`: `CComProcessInfo::FinalConstruct`
- `0x18007472d`: `CComProcessInfo::FinalConstruct`
- `0x180074e06`: `CComProcessInfo::FinalConstruct`
- `0x180074f09`: `CComProcessInfo::FinalConstruct`
- `0x18007538c`: `CComProcessInfo::FinalConstruct`
- `0x180075478`: `CComProcessInfo::FinalConstruct`
- `0x180073ea1`: `Found local service! (%ws)`
- `0x1800747aa`: `CLSID:%ws APPID:%ws Value:%ws %!HRESULT!`
- `0x180075a80`: `CLSID:%ws APPID:%ws Value:%ws %!HRESULT!`
- `0x180073d36`: `CLSID:%ws APPID:%ws %!HRESULT!`
- `0x180073c94`: `onecore\com\combase\catalog\process.cxx`
- `0x180073d27`: `onecore\com\combase\catalog\process.cxx`
- `0x180073ebd`: `onecore\com\combase\catalog\process.cxx`
- `0x180073f7a`: `onecore\com\combase\catalog\process.cxx`
- `0x180074039`: `onecore\com\combase\catalog\process.cxx`
- `0x18007427d`: `onecore\com\combase\catalog\process.cxx`
- `0x180074368`: `onecore\com\combase\catalog\process.cxx`
- `0x1800743bb`: `onecore\com\combase\catalog\process.cxx`
- `0x18007452b`: `onecore\com\combase\catalog\process.cxx`
- `0x180074575`: `onecore\com\combase\catalog\process.cxx`
- `0x1800745c6`: `onecore\com\combase\catalog\process.cxx`
- `0x180074734`: `onecore\com\combase\catalog\process.cxx`
- `0x180074e11`: `onecore\com\combase\catalog\process.cxx`
- `0x180074f24`: `onecore\com\combase\catalog\process.cxx`
- `0x180075397`: `onecore\com\combase\catalog\process.cxx`
- `0x18007547f`: `onecore\com\combase\catalog\process.cxx`
- `0x180075914`: `onecore\com\combase\catalog\process.cxx`
- `0x18007434c`: `Found surrogate: dllhost`
- `0x18007450f`: `No surrogate, No service.`
- `0x180074a40`: `APPIDREGFLAGS_IUSERVER_UNMODIFIED_SESSION_LOGON_TOKENUSER server must be APPIDREGFLAGS_IUSERVER_UNMODIFIED_LOGON_TOKEN CLSID:%ws APPID:%ws Value:%ws %!HRESULT!`
- `0x1800749c8`: `APPIDREGFLAGS_IUSERVER_UNMODIFIED_CLIENT_LOGON_TOKENUSER server must be APPIDREGFLAGS_IUSERVER_UNMODIFIED_LOGON_TOKEN CLSID:%ws APPID:%ws Value:%ws %!HRESULT!`
- `0x180074949`: `Session Virtual Account server must be AAA CLSID:%ws APPID:%ws Value:%ws %!HRESULT!`
- `0x180074ab5`: `APPIDREGFLAGS_IUSERVER_UNMODIFIED_SESSION_LOGON_TOKENUSER and APPIDREGFLAGS_IUSERVER_UNMODIFIED_CLIENT_LOGON_TOKENUSER are mutually exclusive CLSID:%ws APPID:%ws Value:%ws %!HRESULT!`
- `0x180075936`: `CLSID:%ws APPID:%ws Value:%ws hr:%#x`
- `0x180075040`: `LegacyImpersonationLevel`
- `0x1800751cf`: `LegacyImpersonationLevel`
- `0x180074426`: `DllSurrogateExecutable`
- `0x18007430c`: `DllSurrogate`
- `0x180075a65`: `DllSurrogate`
- `0x180073edc`: `ServiceParameters`
- `0x180073f3b`: `ServiceParameters`

## pseudocode

```c
__int64 __fastcall CComProcessInfo::FinalConstruct(
        CComProcessInfo *this,
        struct IUserToken *a2,
        const struct _GUID *a3,
        unsigned __int16 *a4,
        HKEY hkey,
        HKEY a6,
        int a7,
        bool a8,
        bool a9,
        bool a10,
        bool a11,
        bool a12,
        bool a13,
        bool a14,
        bool a15,
        bool a16,
        bool a17,
        bool a18,
        bool a19)
{
  bool v22; // zf
  struct _GUID v23; // xmm0
  unsigned int RegistryStringValue; // ebx
  CGuidStr *v25; // rax
  const unsigned __int16 **v26; // r14
  CGuidStr *v27; // rax
  int v28; // edx
  int v29; // r9d
  const WCHAR *v30; // rcx
  int v31; // r8d
  __int64 (__fastcall *v32)(RegistrationChangeDetection *, PCNZWCH *); // rbx
  __int64 v33; // rdx
  unsigned __int16 *v34; // r8
  __int64 v35; // r8
  int v36; // r10d
  HKEY v37; // rcx
  const unsigned __int16 *v38; // rcx
  int v39; // eax
  const unsigned __int16 *v40; // rdx
  HKEY v41; // rcx
  const unsigned __int16 *v42; // rdx
  CGuidStr *v43; // rax
  int v44; // edx
  int v45; // ecx
  int v46; // r8d
  int v47; // r9d
  const unsigned __int16 *v48; // rcx
  int ServicePackageNameFromScmRegistration; // eax
  WCHAR *v50; // rsi
  const unsigned __int16 *StringRawBuffer; // rax
  CGuidStr *v52; // rax
  int v53; // edx
  int v54; // ecx
  int v55; // r8d
  int v56; // r9d
  __int64 v57; // r11
  char v58; // r14
  __int64 *v59; // rcx
  const unsigned __int16 *v60; // rcx
  int v61; // eax
  WCHAR *v62; // rsi
  __int64 v63; // rdx
  const unsigned __int16 *v64; // rbx
  unsigned __int64 v65; // rdx
  unsigned __int8 v66; // cl
  __int64 v67; // rcx
  ComTrace *v68; // rcx
  HKEY v69; // r14
  HKEY v70; // rcx
  int v71; // r8d
  __int64 v72; // r8
  CGuidStr *v73; // rax
  int v74; // edx
  int v75; // ecx
  int v76; // r9d
  CGuidStr *v77; // rax
  int v78; // edx
  int v79; // ecx
  int v80; // r9d
  int v81; // r8d
  __int64 v82; // rdx
  unsigned __int16 v83; // ax
  unsigned __int16 *v84; // rcx
  unsigned int v85; // esi
  SIZE_T v86; // rax
  unsigned __int16 *v87; // rax
  unsigned int v88; // eax
  unsigned int v89; // ebx
  SIZE_T v90; // rax
  unsigned __int16 *v91; // rax
  int v92; // eax
  __int64 v93; // r8
  int v94; // r9d
  LSTATUS v95; // eax
  LSTATUS v96; // eax
  CGuidStr *v97; // rax
  int v98; // edx
  int v99; // ecx
  int v100; // r9d
  int v101; // ecx
  CGuidStr *v102; // rax
  int v103; // edx
  int v104; // r9d
  CGuidStr *v105; // rax
  int v106; // edx
  int v107; // r9d
  CGuidStr *v108; // rax
  int v109; // edx
  int v110; // r9d
  CGuidStr *v111; // rax
  int v112; // edx
  int v113; // r9d
  LPCWSTR v114; // r15
  unsigned int v115; // r12d
  LSTATUS v116; // eax
  CGuidStr *v117; // rax
  int v118; // edx
  int v119; // r9d
  CGuidStr *v120; // rax
  int v121; // edx
  int v122; // r9d
  LSTATUS v123; // eax
  CGuidStr *v124; // rax
  int v125; // edx
  int v126; // r9d
  LSTATUS v127; // eax
  BYTE *v128; // r15
  int v129; // r9d
  CGuidStr *v130; // rax
  int v131; // edx
  int v132; // r9d
  CGuidStr *v133; // rax
  int v134; // r9d
  HKEY v135; // r12
  int RegistrySecurityDescriptor; // eax
  LSTATUS v137; // eax
  LPCWSTR v138; // r15
  LSTATUS v139; // eax
  CGuidStr *v140; // rax
  int v141; // edx
  int v142; // r9d
  int v143; // r8d
  CGuidStr *v144; // rax
  int v145; // edx
  int v146; // r9d
  int v147; // r8d
  LSTATUS v148; // eax
  CGuidStr *v149; // rax
  int v150; // edx
  int v151; // r9d
  int v152; // eax
  LSTATUS v153; // eax
  int v154; // r8d
  int v155; // eax
  LSTATUS v156; // eax
  int v157; // r8d
  int v158; // r9d
  LSTATUS v159; // eax
  LPCWSTR v160; // r15
  RegistrationChangeDetection *v161; // rcx
  struct RegistrationChangeDetection::IPerUserCacheInformation **v162; // r9
  CGuidStr *v163; // rax
  int v164; // edx
  int v165; // r9d
  CGuidStr *v166; // rax
  int v167; // edx
  int v168; // r9d
  CGuidStr *v169; // rax
  int v170; // edx
  int v171; // r9d
  CGuidStr *v172; // rax
  int v173; // edx
  int v174; // r9d
  CGuidStr *v175; // rax
  int v176; // edx
  int v177; // r9d
  CGuidStr *v178; // rax
  int v179; // edx
  int v180; // r9d
  CGuidStr *v181; // rax
  int v182; // edx
  int v183; // r9d
  LSTATUS v184; // eax
  const char *v185; // rax
  CGuidStr *v186; // rax
  int v187; // edx
  int v188; // r9d
  CGuidStr *v189; // rax
  int v190; // edx
  int v191; // r9d
  int phkResult; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcbDataa; // [rsp+28h] [rbp-D8h]
  __int64 v196; // [rsp+30h] [rbp-D0h]
  __int64 v197; // [rsp+38h] [rbp-C8h]
  __int64 v198; // [rsp+40h] [rbp-C0h]
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+64h] [rbp-9Ch] BYREF
  LPCWSTR lpSubKey; // [rsp+68h] [rbp-98h]
  PCNZWCH sourceString; // [rsp+70h] [rbp-90h] BYREF
  bool v203; // [rsp+78h] [rbp-88h] BYREF
  bool v204; // [rsp+79h] [rbp-87h] BYREF
  BYTE Data[4]; // [rsp+7Ch] [rbp-84h] BYREF
  HKEY v206; // [rsp+80h] [rbp-80h] BYREF
  HKEY KeyHandle; // [rsp+88h] [rbp-78h]
  HKEY v208; // [rsp+90h] [rbp-70h] BYREF
  RegistrationChangeDetection *v209; // [rsp+98h] [rbp-68h]
  HKEY hKey; // [rsp+A0h] [rbp-60h]
  _BYTE v211[80]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v212[256]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  v209 = a2;
  KeyHandle = hkey;
  hKey = a6;
  cbData = 0;
  Type = 0;
  lpSubKey = a4;
  memset_0(v212, 0, sizeof(v212));
  v22 = gfEnableTracing == 0;
  v23 = *a3;
  v208 = 0;
  *((struct _GUID *)this + 3) = v23;
  *(_DWORD *)Data = 0;
  *((_DWORD *)this + 54) = a7;
  if ( !v22 && (unsigned __int8)IsWppLevelEnabled(3) )
  {
    HIDWORD(v196) = HIDWORD(a3);
    ComTraceMessage(0xFFFFFFFFLL, "onecore\\com\\combase\\catalog\\process.cxx", "CComProcessInfo::FinalConstruct", 136);
  }
  RegistryStringValue = GetRegistryStringValue(hkey, 0, 0, 2u, (unsigned __int16 **)this + 8);
  if ( (int)(RegistryStringValue + 0x80000000) >= 0 && RegistryStringValue != -2147024894 )
  {
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8) )
    {
      v25 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
      ComTraceMessageT<unsigned short *,unsigned short *,long>(
        (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
        (unsigned int)"CComProcessInfo::FinalConstruct",
        146,
        0,
        (__int64)L"CLSID:%ws APPID:%ws %!HRESULT!",
        v25,
        a4,
        RegistryStringValue);
    }
    return RegistryStringValue;
  }
  v26 = (const unsigned __int16 **)((char *)this + 80);
  RegistryStringValue = GetRegistryStringValue(hkey, 0, L"LocalService", 2u, (unsigned __int16 **)this + 10);
  if ( (int)(RegistryStringValue + 0x80000000) >= 0 && RegistryStringValue != -2147024894 )
  {
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
      return RegistryStringValue;
    v27 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
    v30 = L"LocalService";
    v31 = 162;
    goto LABEL_429;
  }
  if ( a19 )
  {
    sourceString = 0;
    v32 = *(__int64 (__fastcall **)(RegistrationChangeDetection *, PCNZWCH *))(*(_QWORD *)v209 + 80LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &sourceString,
      0);
    RegistryStringValue = v32(v209, &sourceString);
    if ( (RegistryStringValue & 0x80000000) != 0 )
      goto LABEL_18;
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      (char *)this + 256,
      0);
    v33 = -1;
    do
      ++v33;
    while ( sourceString[v33] );
    RegistryStringValue = WindowsCreateString(sourceString, v33, (HSTRING *)this + 32);
    if ( (RegistryStringValue & 0x80000000) != 0 )
    {
LABEL_18:
      utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&sourceString);
      return RegistryStringValue;
    }
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&sourceString);
  }
  v34 = (unsigned __int16 *)*v26;
  if ( *v26 )
  {
    if ( *v34 )
    {
      if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
        ComTraceMessageT<unsigned short const *>(
          (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
          (unsigned int)"CComProcessInfo::FinalConstruct",
          185,
          v36,
          (__int64)L"Found local service! (%ws)",
          v35);
      v37 = KeyHandle;
      *((_DWORD *)this + 18) = 1;
      RegistryStringValue = GetRegistryStringValue(v37, 0, L"ServiceParameters", 2u, (unsigned __int16 **)this + 11);
      if ( (int)(RegistryStringValue + 0x80000000) >= 0 && RegistryStringValue != -2147024894 )
      {
        if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
          return RegistryStringValue;
        v27 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
        v30 = L"ServiceParameters";
        v31 = 193;
        goto LABEL_429;
      }
      v38 = *v26;
      v204 = 0;
      v203 = 0;
      v39 = IsUserOrPackagedService(v38, &v204, &v203);
      RegistryStringValue = v39;
      if ( v39 >= 0 )
      {
        if ( v204 )
          *((_DWORD *)this + 48) |= 0x40u;
        if ( a19 )
        {
          if ( !v203 )
          {
            RegistryStringValue = -2147221161;
            if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
            {
              v43 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
              ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,bool,bool,long>(
                v45,
                v44,
                v46,
                v47,
                phkResult,
                (__int64)v43,
                (__int64)a4);
            }
            return RegistryStringValue;
          }
          v48 = *v26;
          sourceString = 0;
          ServicePackageNameFromScmRegistration = CComProcessInfo::GetServicePackageNameFromScmRegistration(
                                                    v48,
                                                    (unsigned __int16 **)&sourceString);
          v50 = (WCHAR *)sourceString;
          if ( ServicePackageNameFromScmRegistration < 0
            || (StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 32), 0),
                !PackageNamesMatch(v50, StringRawBuffer)) )
          {
            RegistryStringValue = -2147221161;
            if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
            {
              WindowsGetStringRawBuffer(*((HSTRING *)this + 32), 0);
              v52 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
              ComTraceMessageT<unsigned short *,unsigned short *,unsigned short *,unsigned short const *,long>(
                v54,
                v53,
                v55,
                v56,
                phkResult,
                (__int64)v52,
                (__int64)a4,
                (__int64)v50,
                v57);
            }
            if ( v50 && v50 != (WCHAR *)&g_wszEmptyString )
              HeapFree(g_hHeap, 0, v50);
            return RegistryStringValue;
          }
          if ( v50 && v50 != (WCHAR *)&g_wszEmptyString )
            HeapFree(g_hHeap, 0, v50);
          *((_DWORD *)this + 48) |= 0x80u;
        }
        else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
               && v203 )
        {
          v58 = 0;
          v59 = qword_18014E9A0;
          while ( *((_QWORD *)this + 6) != *v59 || *((_QWORD *)this + 7) != v59[1] )
          {
            v59 += 2;
            if ( v59 == (__int64 *)&gWIPTbl )
              goto LABEL_72;
          }
          v58 = 1;
LABEL_72:
          v60 = (const unsigned __int16 *)*((_QWORD *)this + 10);
          sourceString = 0;
          v61 = CComProcessInfo::GetServicePackageNameFromScmRegistration(v60, (unsigned __int16 **)&sourceString);
          v62 = (WCHAR *)sourceString;
          RegistryStringValue = v61;
          if ( v61 >= 0 )
          {
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
              (char *)this + 256,
              0);
            v63 = -1;
            do
              ++v63;
            while ( v62[v63] );
            RegistryStringValue = WindowsCreateString(v62, v63, (HSTRING *)this + 32);
          }
          if ( v62 && v62 != (WCHAR *)&g_wszEmptyString )
            HeapFree(g_hHeap, 0, v62);
          if ( (RegistryStringValue & 0x80000000) != 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x12E,
              (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
              (const char *)RegistryStringValue,
              phkResult);
            return RegistryStringValue;
          }
          if ( !v58 )
          {
            v64 = WindowsGetStringRawBuffer(*((HSTRING *)this + 32), 0);
            if ( ComTrace::IsEnabled(v66, v65) )
            {
              wil::details::static_lazy<ComTrace>::get(
                v67,
                _lambda_f8a79a44bba2ee3470b25df359f31864_::_lambda_invoker_cdecl_);
              ComTrace::PackagedServiceComRegistrationInHKLM_(
                v68,
                *((const unsigned __int16 **)this + 10),
                v64,
                (const struct _GUID *)this + 3);
            }
          }
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xC8,
          (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
          (const char *)(unsigned int)v39,
          phkResult);
        if ( RegistryStringValue != -2147023836 )
          return RegistryStringValue;
      }
      goto LABEL_36;
    }
    if ( v34 != (unsigned __int16 *)&g_wszEmptyString )
      HeapFree(g_hHeap, 0, v34);
  }
  v69 = KeyHandle;
  v70 = KeyHandle;
  *((_QWORD *)this + 10) = 0;
  RegistryStringValue = GetRegistryStringValue(v70, 0, L"DllSurrogate", 0, (unsigned __int16 **)this + 15);
  if ( (RegistryStringValue & 0x80000000) != 0 )
  {
    if ( RegistryStringValue != -2147024894 )
    {
      if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
        return RegistryStringValue;
      v27 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
      v30 = L"DllSurrogate";
      v31 = 391;
LABEL_429:
      ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
        (_DWORD)v30,
        v28,
        v31,
        v29,
        (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
        v27,
        a4,
        v30,
        RegistryStringValue);
      return RegistryStringValue;
    }
    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      ComTraceMessageT<>(
        (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
        (unsigned int)"CComProcessInfo::FinalConstruct",
        385,
        v81,
        (__int64)L"No surrogate, No service.");
    *((_DWORD *)this + 18) = 0;
  }
  else if ( *((const unsigned __int16 near *const **)this + 15) == &g_wszEmptyString )
  {
    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      ComTraceMessageT<>(
        (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
        (unsigned int)"CComProcessInfo::FinalConstruct",
        338,
        v71,
        (__int64)L"Found surrogate: dllhost");
    *((_DWORD *)this + 18) = 2;
  }
  else
  {
    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      ComTraceMessageT<unsigned short const *>(
        (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
        (unsigned int)"CComProcessInfo::FinalConstruct",
        344,
        3,
        (__int64)L"Found surrogate: %ws",
        v72);
    *((_DWORD *)this + 18) = 3;
    RegistryStringValue = GetRegistryStringValue(v69, 0, L"DebugSurrogate", 0, (unsigned __int16 **)this + 28);
    if ( (RegistryStringValue & 0x80000000) != 0 )
    {
      if ( RegistryStringValue != -2147024894 )
      {
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v77 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            v79,
            v78,
            356,
            v80,
            (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v77,
            a4,
            L"DebugSurrogate",
            RegistryStringValue);
        }
        return RegistryStringValue;
      }
    }
    else
    {
      *((_DWORD *)this + 61) = 1;
    }
    if ( !*((_DWORD *)this + 61) )
    {
      RegistryStringValue = GetRegistryStringValue(v69, 0, L"DllSurrogateExecutable", 0, (unsigned __int16 **)this + 29);
      if ( (int)(RegistryStringValue + 0x80000000) >= 0 && RegistryStringValue != -2147024894 )
      {
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v73 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            v75,
            v74,
            375,
            v76,
            (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v73,
            a4,
            L"DllSurrogateExecutable",
            RegistryStringValue);
        }
        return RegistryStringValue;
      }
    }
  }
LABEL_36:
  v41 = KeyHandle;
  *((_DWORD *)this + 28) = 2;
  RegistryStringValue = ReadRegistryStringValue(v41, v40, L"RunAs", v212, 0x100u);
  if ( (RegistryStringValue & 0x80000000) != 0 || !v212[0] )
    goto LABEL_140;
  if ( (unsigned int)_o__wcsicmp(v212, L"Interactive User") )
  {
    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      ComTraceMessageT<unsigned short const *>(
        (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
        (unsigned int)"CComProcessInfo::FinalConstruct",
        418,
        3,
        (__int64)L"Found RunAs: %ws",
        v212);
    *((_DWORD *)this + 28) = 0;
    v82 = -1;
    do
      ++v82;
    while ( v212[v82] );
    v83 = v212[0];
    v84 = v212;
    while ( v83 && v83 != 92 )
      v83 = *++v84;
    if ( *v84 )
    {
      v89 = v82 + 1;
      v90 = 2LL * (unsigned int)(v82 + 1);
      if ( !is_mul_ok((unsigned int)(v82 + 1), 2u) )
        v90 = -1;
      v91 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v90);
      *((_QWORD *)this + 13) = v91;
      if ( v91 )
      {
        v88 = StringCchCopyW(v91, v89, v212);
        goto LABEL_139;
      }
    }
    else
    {
      v85 = v82 + 4;
      v86 = 2LL * (unsigned int)(v82 + 4);
      if ( !is_mul_ok((unsigned int)(v82 + 4), 2u) )
        v86 = -1;
      v87 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v86);
      *((_QWORD *)this + 13) = v87;
      if ( v87 )
      {
        RegistryStringValue = StringCchCopyW(v87, v85, &byte_18014E810);
        if ( (RegistryStringValue & 0x80000000) != 0 )
          goto LABEL_140;
        RegistryStringValue = StringCchCatW(*((unsigned __int16 **)this + 13), v85, L"\\");
        if ( (RegistryStringValue & 0x80000000) != 0 )
          goto LABEL_140;
        v88 = StringCchCatW(*((unsigned __int16 **)this + 13), v85, v212);
LABEL_139:
        RegistryStringValue = v88;
        goto LABEL_140;
      }
    }
    return (unsigned int)-2147024882;
  }
  if ( a8 )
  {
    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      ComTraceMessageT<>(
        (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
        (unsigned int)"CComProcessInfo::FinalConstruct",
        407,
        3,
        (__int64)L"Ignoring RunAs: Interactive User");
  }
  else
  {
    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      ComTraceMessageT<>(
        (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
        (unsigned int)"CComProcessInfo::FinalConstruct",
        412,
        3,
        (__int64)L"Found RunAs: Interactive User");
    *((_DWORD *)this + 28) = 1;
  }
LABEL_140:
  if ( a9 )
  {
    v92 = GetRegistryStringValue(KeyHandle, 0, L"ApplicationId", 0, (unsigned __int16 **)this + 31);
    RegistryStringValue = v92;
    if ( v92 < 0 )
    {
      if ( v92 != -2147024894 )
        return RegistryStringValue;
      RegistryStringValue = 0;
    }
    else
    {
      if ( !**((_WORD **)this + 31) )
        return (unsigned int)-2147221165;
      if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
        ComTraceMessageT<unsigned short const *>(
          (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
          (unsigned int)"CComProcessInfo::FinalConstruct",
          489,
          v94,
          (__int64)L"Found ApplicationId: %ws",
          v93);
      *((_DWORD *)this + 28) = 4;
    }
  }
  *((_DWORD *)this + 24) = 0;
  if ( a10 )
  {
    RegistryStringValue = ReadRegistryStringValue(KeyHandle, v42, L"ActivateAtStorage", v212, 0x100u);
    if ( (RegistryStringValue & 0x80000000) != 0 )
    {
      if ( RegistryStringValue != -2147024894 )
      {
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v97 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            v99,
            v98,
            526,
            v100,
            (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v97,
            a4,
            L"ActivateAtStorage",
            RegistryStringValue);
        }
        return RegistryStringValue;
      }
      RegistryStringValue = 0;
    }
    else if ( ((v212[0] - 89) & 0xFFDF) == 0 )
    {
      *((_DWORD *)this + 24) = 1;
    }
  }
  *((_DWORD *)this + 38) = 0;
  v206 = 0;
  *((_QWORD *)this + 18) = 0;
  *((_OWORD *)this + 10) = 0;
  if ( a11 || a12 || a13 )
  {
    v95 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &v206);
    if ( v95 )
    {
      if ( v95 == 2 )
        goto LABEL_263;
      if ( v95 > 0 )
        RegistryStringValue = (unsigned __int16)v95 | 0x80070000;
      else
        RegistryStringValue = v95;
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v133 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
        ComTraceMessageT<unsigned short *,unsigned short const *,unsigned short const *,long>(
          (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
          (unsigned int)"CComProcessInfo::FinalConstruct",
          764,
          v134,
          (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
          v133,
          lpSubKey,
          lpSubKey,
          RegistryStringValue);
      }
      goto LABEL_262;
    }
    if ( a11 )
    {
      cbData = 4;
      LODWORD(sourceString) = 0;
      v96 = RegQueryValueExW(v206, L"AppIDFlags", 0, &Type, (LPBYTE)&sourceString, &cbData);
      if ( v96 )
      {
        if ( v96 == 2 )
        {
          RegistryStringValue = 0;
        }
        else
        {
          if ( v96 > 0 )
            RegistryStringValue = (unsigned __int16)v96 | 0x80070000;
          else
            RegistryStringValue = v96;
          if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          {
            v117 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
            v114 = lpSubKey;
            ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
              (unsigned int)L"AppIDFlags",
              v118,
              573,
              v119,
              (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
              v117,
              lpSubKey,
              L"AppIDFlags",
              RegistryStringValue);
LABEL_195:
            if ( a12 )
            {
              cbData = 4;
              v115 = 0;
              LODWORD(sourceString) = 0;
              v116 = RegQueryValueExW(v206, L"ROTFlags", 0, &Type, (LPBYTE)&sourceString, &cbData);
              if ( v116 )
              {
                if ( v116 == 2 )
                {
                  RegistryStringValue = 0;
                }
                else
                {
                  if ( v116 > 0 )
                    RegistryStringValue = (unsigned __int16)v116 | 0x80070000;
                  else
                    RegistryStringValue = v116;
                  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
                  {
                    v120 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
                    LODWORD(v198) = RegistryStringValue;
                    ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
                      (unsigned int)L"ROTFlags",
                      v121,
                      694,
                      v122,
                      (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
                      v120,
                      v114,
                      L"ROTFlags",
                      v198);
                  }
                }
              }
              else if ( Type == 4 && cbData == 4 )
              {
                *((_DWORD *)this + 36) = (_DWORD)sourceString;
              }
              else
              {
                RegistryStringValue = -2147221165;
              }
              cbData = 4;
              v123 = RegQueryValueExW(v206, L"MGOTFlags", 0, &Type, (LPBYTE)&sourceString, &cbData);
              if ( v123 )
              {
                if ( v123 == 2 )
                {
                  RegistryStringValue = 0;
                }
                else
                {
                  if ( v123 > 0 )
                    RegistryStringValue = (unsigned __int16)v123 | 0x80070000;
                  else
                    RegistryStringValue = v123;
                  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
                  {
                    v124 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
                    LODWORD(v198) = RegistryStringValue;
                    ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
                      (unsigned int)L"MGOTFlags",
                      v125,
                      714,
                      v126,
                      (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
                      v124,
                      v114,
                      L"MGOTFlags",
                      v198);
                  }
                }
              }
              else if ( Type == 4 && cbData == 4 )
              {
                *((_DWORD *)this + 37) = (_DWORD)sourceString;
              }
              else
              {
                RegistryStringValue = -2147221165;
              }
            }
            else
            {
              v115 = 0;
            }
            if ( !a13 )
              goto LABEL_253;
            v127 = RegQueryValueExW(v206, L"ProcessMitigationPolicy", 0, &Type, 0, &cbData);
            if ( v127 != 2 )
            {
              if ( v127 || Type != 3 || cbData <= 1 )
              {
                RegistryStringValue = -2147221165;
                if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
                {
                  v130 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
                  LODWORD(v198) = -2147221165;
                  ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
                    (unsigned int)L"ProcessMitigationPolicy",
                    v131,
                    752,
                    v132,
                    (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
                    v130,
                    v114,
                    L"ProcessMitigationPolicy",
                    v198);
                }
                goto LABEL_253;
              }
              v128 = (BYTE *)HeapAlloc(g_hHeap, 0, cbData);
              if ( !v128 )
              {
                RegistryStringValue = -2147024882;
LABEL_253:
                RegCloseKey(v206);
LABEL_262:
                if ( (RegistryStringValue & 0x80000000) != 0 )
                  return RegistryStringValue;
                goto LABEL_263;
              }
              v115 = RegistryStringValue;
              if ( (RegistryStringValue & 0x80000000) != 0 )
                goto LABEL_253;
              RegistryStringValue = RegQueryValueExW(v206, L"ProcessMitigationPolicy", 0, &Type, v128, &cbData);
              if ( RegistryStringValue )
              {
                HeapFree(g_hHeap, 0, v128);
                if ( (int)RegistryStringValue > 0 )
                  RegistryStringValue = (unsigned __int16)RegistryStringValue | 0x80070000;
                if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
                {
                  LODWORD(v198) = RegistryStringValue;
                  LODWORD(v197) = cbData;
                  LODWORD(v196) = Type;
                  ComTraceMessageT<unsigned short const *,unsigned long,unsigned long,long>(
                    (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
                    (unsigned int)"CComProcessInfo::FinalConstruct",
                    739,
                    v129,
                    (__int64)L"Value:%ws Type:%d Size:%d %!HRESULT!",
                    L"ProcessMitigationPolicy",
                    v196,
                    v197,
                    v198);
                }
                goto LABEL_253;
              }
              *((_DWORD *)this + 40) = cbData;
              *((_QWORD *)this + 21) = v128;
            }
            RegistryStringValue = v115;
            goto LABEL_253;
          }
        }
      }
      else
      {
        if ( Type == 4 && cbData == 4 )
          *((_DWORD *)this + 38) = (_DWORD)sourceString;
        else
          RegistryStringValue = -2147221165;
        v101 = *((_DWORD *)this + 38);
        if ( (v101 & 0x100) != 0 )
        {
          if ( *((_DWORD *)this + 28) != 2 )
          {
            RegistryStringValue = -2147221165;
            if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
            {
              v102 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
              ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
                (unsigned int)L"AppIDFlags",
                v103,
                625,
                v104,
                (__int64)L"Session Virtual Account server must be AAA CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
                v102,
                lpSubKey,
                L"AppIDFlags",
                -2147221165);
            }
            return RegistryStringValue;
          }
          *((_DWORD *)this + 28) = 3;
        }
        if ( (v101 & 0x208) == 0x200 )
        {
          RegistryStringValue = -2147221165;
          if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          {
            v105 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
            ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
              (unsigned int)L"AppIDFlags",
              v106,
              642,
              v107,
              (__int64)L"APPIDREGFLAGS_IUSERVER_UNMODIFIED_CLIENT_LOGON_TOKENUSER server must be APPIDREGFLAGS_IUSERVER_UN"
                        "MODIFIED_LOGON_TOKEN CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
              v105,
              lpSubKey,
              L"AppIDFlags",
              -2147221165);
          }
          return RegistryStringValue;
        }
        if ( (v101 & 0x408) == 0x400 )
        {
          RegistryStringValue = -2147221165;
          if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          {
            v108 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
            ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
              (unsigned int)L"AppIDFlags",
              v109,
              655,
              v110,
              (__int64)L"APPIDREGFLAGS_IUSERVER_UNMODIFIED_SESSION_LOGON_TOKENUSER server must be APPIDREGFLAGS_IUSERVER_U"
                        "NMODIFIED_LOGON_TOKEN CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
              v108,
              lpSubKey,
              L"AppIDFlags",
              -2147221165);
          }
          return RegistryStringValue;
        }
        if ( (v101 & 0x600) == 0x600 )
        {
          RegistryStringValue = -2147221165;
          if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          {
            v111 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
            ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
              (unsigned int)L"AppIDFlags",
              v112,
              668,
              v113,
              (__int64)L"APPIDREGFLAGS_IUSERVER_UNMODIFIED_SESSION_LOGON_TOKENUSER and APPIDREGFLAGS_IUSERVER_UNMODIFIED_C"
                        "LIENT_LOGON_TOKENUSER are mutually exclusive CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
              v111,
              lpSubKey,
              L"AppIDFlags",
              -2147221165);
          }
          return RegistryStringValue;
        }
      }
    }
    v114 = lpSubKey;
    goto LABEL_195;
  }
LABEL_263:
  v135 = KeyHandle;
  RegistrySecurityDescriptor = GetRegistrySecurityDescriptor(
                                 KeyHandle,
                                 v42,
                                 (struct _SECURITY_DESCRIPTOR_RELATIVE **)this + 16,
                                 (unsigned int *)this + 34);
  RegistryStringValue = RegistrySecurityDescriptor;
  if ( RegistrySecurityDescriptor < 0 )
  {
    if ( RegistrySecurityDescriptor != -2147221166 )
    {
      if ( RegistrySecurityDescriptor == -2147221165 )
      {
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v189 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
          LODWORD(v198) = -2147221165;
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            (unsigned int)L"LaunchPermission",
            v190,
            785,
            v191,
            (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v189,
            lpSubKey,
            L"LaunchPermission",
            v198);
        }
        if ( g_bInSCM && gdwInvalidSecurityDescriptorLoggingLevel == 1 )
          LogInvalidSecurityDescriptor(a3, 18213, 7);
      }
      return RegistryStringValue;
    }
    *((_DWORD *)this + 48) |= 2u;
    RegistryStringValue = 0;
  }
  else
  {
    *((_DWORD *)this + 48) |= 1u;
  }
  if ( CComProcessInfo::m_fGotLegacyLevels
    || RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\OLE", 0, 0x20019u, &v208) )
  {
    goto LABEL_307;
  }
  cbData = 4;
  v137 = RegQueryValueExW(v208, L"LegacyAuthenticationLevel", 0, &Type, Data, &cbData);
  if ( v137 )
  {
    if ( v137 == 2 )
    {
      RegistryStringValue = 0;
      goto LABEL_273;
    }
    if ( v137 > 0 )
      RegistryStringValue = (unsigned __int16)v137 | 0x80070000;
    else
      RegistryStringValue = v137;
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
      goto LABEL_273;
    v140 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
    v143 = 821;
    LODWORD(v198) = RegistryStringValue;
  }
  else
  {
    if ( Type == 4 && cbData == 4 )
    {
      CComProcessInfo::m_dwLegacyAuthenticationLevel = *(_DWORD *)Data;
LABEL_273:
      v138 = lpSubKey;
      goto LABEL_274;
    }
    RegistryStringValue = -2147221165;
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
      goto LABEL_273;
    v140 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
    v143 = 811;
    LODWORD(v198) = -2147221165;
  }
  v138 = lpSubKey;
  ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
    (unsigned int)L"LegacyAuthenticationLevel",
    v141,
    v143,
    v142,
    (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
    v140,
    lpSubKey,
    L"LegacyAuthenticationLevel",
    v198);
LABEL_274:
  cbData = 4;
  v139 = RegQueryValueExW(v208, L"LegacyImpersonationLevel", 0, &Type, Data, &cbData);
  if ( v139 )
  {
    if ( v139 == 2 )
    {
      RegistryStringValue = 0;
      goto LABEL_306;
    }
    if ( v139 > 0 )
      RegistryStringValue = (unsigned __int16)v139 | 0x80070000;
    else
      RegistryStringValue = v139;
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v144 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
      v147 = 846;
      LODWORD(v198) = RegistryStringValue;
      goto LABEL_305;
    }
  }
  else
  {
    if ( Type == 4 && cbData == 4 )
    {
      CComProcessInfo::m_dwLegacyImpersonationLevel = *(_DWORD *)Data;
      goto LABEL_306;
    }
    RegistryStringValue = -2147221165;
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v144 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
      v147 = 836;
      LODWORD(v198) = -2147221165;
LABEL_305:
      ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
        (unsigned int)L"LegacyImpersonationLevel",
        v145,
        v147,
        v146,
        (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
        v144,
        v138,
        L"LegacyImpersonationLevel",
        v198);
    }
  }
LABEL_306:
  RegCloseKey(v208);
  if ( (RegistryStringValue & 0x80000000) != 0 )
    return RegistryStringValue;
LABEL_307:
  cbData = 4;
  v148 = RegQueryValueExW(v135, L"AuthenticationLevel", 0, &Type, (LPBYTE)this + 140, &cbData);
  RegistryStringValue = v148;
  if ( !v148 && Type == 4 || cbData == 4 )
  {
    RegistryStringValue = 0;
  }
  else
  {
    if ( !v148 )
    {
      RegistryStringValue = -2147221165;
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v149 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
        LODWORD(v198) = -2147221165;
        ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
          (unsigned int)L"AuthenticationLevel",
          v150,
          865,
          v151,
          (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
          v149,
          lpSubKey,
          L"AuthenticationLevel",
          v198);
      }
      return RegistryStringValue;
    }
    if ( v148 != 2 )
    {
      if ( v148 > 0 )
        RegistryStringValue = (unsigned __int16)v148 | 0x80070000;
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v186 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
        LODWORD(v198) = RegistryStringValue;
        ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
          (unsigned int)L"AuthenticationLevel",
          v187,
          877,
          v188,
          (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
          v186,
          lpSubKey,
          L"AuthenticationLevel",
          v198);
      }
      return RegistryStringValue;
    }
    RegistryStringValue = 0;
    *((_DWORD *)this + 35) = CComProcessInfo::m_dwLegacyAuthenticationLevel;
  }
  if ( a14 )
  {
    v152 = GetRegistryStringValue(v135, 0, L"RemoteServerName", 3u, (unsigned __int16 **)this + 23);
    RegistryStringValue = v152;
    if ( v152 < 0 )
    {
      if ( v152 != -2147024894 )
      {
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v163 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
          LODWORD(v198) = RegistryStringValue;
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            (unsigned int)L"RemoteServerName",
            v164,
            891,
            v165,
            (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v163,
            lpSubKey,
            L"RemoteServerName",
            v198);
        }
        return RegistryStringValue;
      }
      RegistryStringValue = 0;
    }
  }
  if ( a15 )
  {
    LODWORD(sourceString) = 0;
    cbData = 4;
    v153 = RegQueryValueExW(v135, L"SRPTrustLevel", 0, &Type, (LPBYTE)&sourceString, &cbData);
    if ( v153 )
    {
      if ( v153 != 2 )
      {
        if ( v153 > 0 )
          RegistryStringValue = (unsigned __int16)v153 | 0x80070000;
        else
          RegistryStringValue = v153;
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v169 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
          LODWORD(v198) = RegistryStringValue;
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            (unsigned int)L"SRPTrustLevel",
            v170,
            925,
            v171,
            (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v169,
            lpSubKey,
            L"SRPTrustLevel",
            v198);
        }
        return RegistryStringValue;
      }
      RegistryStringValue = 0;
    }
    else
    {
      if ( Type != 4 || cbData != 4 )
      {
        RegistryStringValue = -2147221165;
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v166 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
          LODWORD(v198) = -2147221165;
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            (unsigned int)L"SRPTrustLevel",
            v167,
            913,
            v168,
            (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v166,
            lpSubKey,
            L"SRPTrustLevel",
            v198);
        }
        return RegistryStringValue;
      }
      if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      {
        LODWORD(lpcbData) = (_DWORD)sourceString;
        ComTraceMessageT<int>(
          (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
          (unsigned int)"CComProcessInfo::FinalConstruct",
          905,
          v154,
          (__int64)L"Found SAFER Level: %#x",
          lpcbData);
      }
      v155 = (int)sourceString;
      *((_DWORD *)this + 48) |= 0x10u;
      *((_DWORD *)this + 49) = v155;
    }
  }
  if ( a16 )
  {
    LODWORD(sourceString) = 0;
    cbData = 4;
    v156 = RegQueryValueExW(v135, L"PreferredServerBitness", 0, &Type, (LPBYTE)&sourceString, &cbData);
    if ( v156 )
    {
      if ( v156 != 2 )
      {
        if ( v156 > 0 )
          RegistryStringValue = (unsigned __int16)v156 | 0x80070000;
        else
          RegistryStringValue = v156;
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v175 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
          LODWORD(v198) = RegistryStringValue;
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            (unsigned int)L"PreferredServerBitness",
            v176,
            962,
            v177,
            (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v175,
            lpSubKey,
            L"PreferredServerBitness",
            v198);
        }
        return RegistryStringValue;
      }
      RegistryStringValue = 0;
    }
    else
    {
      if ( Type != 4
        || cbData != 4
        || (v157 = (int)sourceString, (unsigned int)sourceString > 5) && (_DWORD)sourceString != 0x80000000 )
      {
        RegistryStringValue = -2147221165;
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v172 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
          LODWORD(v198) = -2147221165;
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            (unsigned int)L"PreferredServerBitness",
            v173,
            950,
            v174,
            (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v172,
            lpSubKey,
            L"PreferredServerBitness",
            v198);
        }
        return RegistryStringValue;
      }
      if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      {
        LODWORD(lpcbDataa) = v157;
        ComTraceMessageT<int>(
          (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
          (unsigned int)"CComProcessInfo::FinalConstruct",
          942,
          v158,
          (__int64)L"Found PreferredServerBitness: %#x",
          lpcbDataa);
        v157 = (int)sourceString;
      }
      *((_DWORD *)this + 48) |= 0x20u;
      *((_DWORD *)this + 55) = v157;
    }
  }
  if ( !a17 )
  {
    v160 = lpSubKey;
    goto LABEL_397;
  }
  LODWORD(sourceString) = 0;
  cbData = 4;
  v159 = RegQueryValueExW(v135, L"LoadUserSettings", 0, &Type, (LPBYTE)&sourceString, &cbData);
  if ( v159 )
  {
    if ( v159 == 2 )
    {
      RegistryStringValue = 0;
      v160 = lpSubKey;
LABEL_347:
      if ( UseNewCatalogCacheBehavior() )
      {
        if ( !g_bInSCM )
        {
          *((_QWORD *)this + 34) = RegistrationChangeDetection::GetSequence(v161);
          goto LABEL_397;
        }
        ObjectLibrary::ReferencedPtr<RegistrationChangeDetection::IPerUserCacheInformation>::InternalRelease((char *)this + 264);
        RegistryStringValue = RegistrationChangeDetection::GetPerUserCacheInformation(
                                v209,
                                (CComProcessInfo *)((char *)this + 272),
                                (unsigned __int64 *)this + 33,
                                v162);
        if ( (RegistryStringValue & 0x80000000) != 0 )
          goto LABEL_397;
      }
      if ( !a7 )
        RegistryStringValue = GetKeyRefreshInfo(v135, (CComProcessInfo *)((char *)this + 200));
LABEL_397:
      if ( !a18 )
        return RegistryStringValue;
      LODWORD(sourceString) = -1;
      cbData = 4;
      v184 = RegQueryValueExW(v135, L"ProtectionLevel", 0, &Type, (LPBYTE)&sourceString, &cbData);
      if ( v184 )
      {
        if ( v184 == 2 )
          return 0;
        if ( v184 > 0 )
          RegistryStringValue = (unsigned __int16)v184 | 0x80070000;
        else
          RegistryStringValue = v184;
      }
      else
      {
        if ( Type != 4 || cbData != 4 || (_DWORD)sourceString != 2 )
        {
          RegistryStringValue = -2147221165;
          goto LABEL_410;
        }
        *((_DWORD *)this + 44) = 2;
      }
      if ( (RegistryStringValue & 0x80000000) == 0 )
        return RegistryStringValue;
LABEL_410:
      v185 = (const char *)CGuidStr::CGuidStr((CGuidStr *)v211, a3);
      LODWORD(v198) = RegistryStringValue;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x418,
        (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
        (const char *)RegistryStringValue,
        (int)"CLSID:%ws APPID:%ws Value:%ws hr:%#x",
        v185,
        v160,
        L"ProtectionLevel",
        v198);
      return RegistryStringValue;
    }
    if ( v159 > 0 )
      RegistryStringValue = (unsigned __int16)v159 | 0x80070000;
    else
      RegistryStringValue = v159;
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v181 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
      v160 = lpSubKey;
      LODWORD(v198) = RegistryStringValue;
      ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
        (unsigned int)L"LoadUserSettings",
        v182,
        992,
        v183,
        (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
        v181,
        lpSubKey,
        L"LoadUserSettings",
        v198);
LABEL_346:
      if ( (RegistryStringValue & 0x80000000) != 0 )
        goto LABEL_397;
      goto LABEL_347;
    }
LABEL_345:
    v160 = lpSubKey;
    goto LABEL_346;
  }
  if ( Type == 4 && cbData == 4 )
  {
    *((_DWORD *)this + 60) = (_DWORD)sourceString;
    goto LABEL_345;
  }
  RegistryStringValue = -2147221165;
  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
  {
    v178 = CGuidStr::CGuidStr((CGuidStr *)v211, a3);
    LODWORD(v198) = -2147221165;
    ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
      (unsigned int)L"LoadUserSettings",
      v179,
      981,
      v180,
      (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
      v178,
      lpSubKey,
      L"LoadUserSettings",
      v198);
  }
  return RegistryStringValue;
}

```

## disassembly

```asm
0x180073bd4  push    rbp
0x180073bd6  push    rbx
0x180073bd7  push    rsi
0x180073bd8  push    rdi
0x180073bd9  push    r12
0x180073bdb  push    r13
0x180073bdd  push    r14
0x180073bdf  push    r15
0x180073be1  lea     rbp, [rsp-218h]
0x180073be9  sub     rsp, 318h
0x180073bf0  mov     rax, cs:__security_cookie
0x180073bf7  xor     rax, rsp
0x180073bfa  mov     [rbp+250h+var_50], rax
0x180073c01  mov     rax, [rbp+250h+arg_28]
0x180073c08  mov     r13, r8
0x180073c0b  mov     rsi, [rbp+250h+hkey]
0x180073c12  mov     rdi, rcx
0x180073c15  mov     [rbp+250h+var_2B8], rdx
0x180073c19  lea     rcx, [rbp+250h+var_250]; void *
0x180073c1d  xor     r14d, r14d
0x180073c20  mov     [rbp+250h+KeyHandle], rsi
0x180073c24  xor     edx, edx; Val
0x180073c26  mov     [rbp+250h+hKey], rax
0x180073c2a  mov     r8d, 200h; Size
0x180073c30  mov     [rsp+350h+cbData], r14d
0x180073c35  mov     [rsp+350h+Type], r14d
0x180073c3a  mov     r12, r9
0x180073c3d  mov     [rsp+350h+lpSubKey], r9
0x180073c42  call    memset_0
0x180073c47  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x180073c4e  lea     r15, [rdi+30h]
0x180073c52  movups  xmm0, xmmword ptr [r13+0]
0x180073c57  mov     eax, [rbp+250h+arg_30]
0x180073c5d  lea     r8d, [r14+3]
0x180073c61  mov     [rbp+250h+var_2C0], r14
0x180073c65  movdqu  xmmword ptr [r15], xmm0
0x180073c6a  mov     dword ptr [rsp+350h+Data], r14d
0x180073c6f  mov     [rdi+0D8h], eax
0x180073c75  jz      short loc_180073CB5
0x180073c77  mov     ecx, r8d
0x180073c7a  call    IsWppLevelEnabled
0x180073c7f  test    al, al
0x180073c81  jz      short loc_180073CB5
0x180073c83  lea     rax, aAppidGuid; "AppID %!GUID!"
0x180073c8a  mov     [rsp+350h+var_320], r13
0x180073c8f  mov     [rsp+350h+lpcbData], rax
0x180073c94  lea     rdx, aOnecoreComComb_51; "onecore\\com\\combase\\catalog\\process"...
0x180073c9b  mov     dword ptr [rsp+350h+phkResult], r8d
0x180073ca0  mov     r9d, 88h
0x180073ca6  lea     r8, aCcomprocessinf; "CComProcessInfo::FinalConstruct"
0x180073cad  or      ecx, 0FFFFFFFFh
0x180073cb0  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x180073cb5  lea     rax, [rdi+40h]
0x180073cb9  mov     r9d, 2; unsigned int
0x180073cbf  xor     r8d, r8d; lpValue
0x180073cc2  mov     [rsp+350h+phkResult], rax; unsigned __int16 **
0x180073cc7  xor     edx, edx; lpSubKey
0x180073cc9  mov     rcx, rsi; hkey
0x180073ccc  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x180073cd1  mov     ebx, eax
0x180073cd3  mov     eax, 80000000h
0x180073cd8  lea     ecx, [rbx+rax]
0x180073cdb  test    eax, ecx
0x180073cdd  jnz     short loc_180073D52
0x180073cdf  cmp     ebx, 80070002h
0x180073ce5  jz      short loc_180073D52
0x180073ce7  mov     ecx, cs:dword_18014E4B8
0x180073ced  test    ecx, ecx
0x180073cef  jnz     short loc_180073D0B
0x180073cf1  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x180073cf8  jz      loc_180075A96
0x180073cfe  call    IsWppLevelEnabled
0x180073d03  test    al, al
0x180073d05  jz      loc_180075A96
0x180073d0b  mov     rdx, r13; struct _GUID *
0x180073d0e  lea     rcx, [rbp+250h+var_2A0]; this
0x180073d12  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x180073d17  mov     dword ptr [rsp+350h+var_318], ebx
0x180073d1b  lea     rdx, aCcomprocessinf; "CComProcessInfo::FinalConstruct"
0x180073d22  mov     [rsp+350h+var_320], r12
0x180073d27  lea     rcx, aOnecoreComComb_51; "onecore\\com\\combase\\catalog\\process"...
0x180073d2e  mov     [rsp+350h+lpcbData], rax
0x180073d33  xor     r9d, r9d
0x180073d36  lea     rax, aClsidWsAppidWs_1; "CLSID:%ws APPID:%ws %!HRESULT!"
0x180073d3d  mov     r8d, 92h
0x180073d43  mov     [rsp+350h+phkResult], rax
0x180073d48  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x180073d4d  jmp     loc_180075A96
0x180073d52  lea     r14, [rdi+50h]
0x180073d56  mov     r9d, 2; unsigned int
0x180073d5c  lea     r8, ?LocalService@Constants@Catalog@Com@@3QBGB; "LocalService"
0x180073d63  mov     [rsp+350h+phkResult], r14; unsigned __int16 **
0x180073d68  xor     edx, edx; lpSubKey
0x180073d6a  mov     rcx, rsi; hkey
0x180073d6d  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x180073d72  mov     ecx, 80000000h
0x180073d77  mov     ebx, eax
0x180073d79  add     eax, ecx
0x180073d7b  test    ecx, eax
0x180073d7d  jnz     short loc_180073DCE
0x180073d7f  cmp     ebx, 80070002h
0x180073d85  jz      short loc_180073DCE
0x180073d87  mov     eax, cs:dword_18014E4B8
0x180073d8d  xor     r8d, r8d
0x180073d90  test    eax, eax
0x180073d92  jnz     short loc_180073DB0
0x180073d94  cmp     cs:?gfEnableTracing@@3HA, r8d; int gfEnableTracing
0x180073d9b  jz      loc_180075A96
0x180073da1  xor     ecx, ecx
0x180073da3  call    IsWppLevelEnabled
0x180073da8  test    al, al
0x180073daa  jz      loc_180075A96
0x180073db0  mov     rdx, r13; struct _GUID *
0x180073db3  lea     rcx, [rbp+250h+var_2A0]; this
0x180073db7  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x180073dbc  lea     rcx, ?LocalService@Constants@Catalog@Com@@3QBGB; "LocalService"
0x180073dc3  mov     r8d, 0A2h
0x180073dc9  jmp     loc_180075A72
0x180073dce  mov     sil, [rbp+250h+arg_90]
0x180073dd5  xor     r9d, r9d
0x180073dd8  test    sil, sil
0x180073ddb  jz      loc_180073E64
0x180073de1  mov     rax, [rbp+250h+var_2B8]
0x180073de5  lea     rcx, [rsp+350h+sourceString]
0x180073dea  xor     edx, edx
0x180073dec  mov     [rsp+350h+sourceString], r9
0x180073df1  mov     rax, [rax]
0x180073df4  mov     rbx, [rax+50h]
0x180073df8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?PrivMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180073dfd  mov     rcx, [rbp+250h+var_2B8]
0x180073e01  lea     rdx, [rsp+350h+sourceString]
0x180073e06  mov     rax, rbx
0x180073e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073e0e  mov     ebx, eax
0x180073e10  test    eax, eax
0x180073e12  jns     short loc_180073E23
0x180073e14  lea     rcx, [rsp+350h+sourceString]
0x180073e19  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@PEAVCClientOxid@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(void)
0x180073e1e  jmp     loc_180075A96
0x180073e23  lea     rbx, [rdi+100h]
0x180073e2a  xor     edx, edx
0x180073e2c  mov     rcx, rbx
0x180073e2f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180073e34  mov     rcx, [rsp+350h+sourceString]; sourceString
0x180073e39  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180073e3d  xor     eax, eax
0x180073e3f  inc     rdx; length
0x180073e42  cmp     [rcx+rdx*2], ax
0x180073e46  jnz     short loc_180073E3F
0x180073e48  mov     r8, rbx; string
0x180073e4b  call    cs:__imp_WindowsCreateString
0x180073e51  lea     rcx, [rsp+350h+sourceString]
0x180073e56  mov     ebx, eax
0x180073e58  test    eax, eax
0x180073e5a  js      short loc_180073E19
0x180073e5c  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@PEAVCClientOxid@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(void)
0x180073e61  xor     r9d, r9d
0x180073e64  mov     r8, [r14]; lpMem
0x180073e67  lea     rax, ?g_wszEmptyString@@3QBGB; ushort const near * const g_wszEmptyString
0x180073e6e  test    r8, r8
0x180073e71  jz      loc_1800742F2
0x180073e77  cmp     [r8], r9w
0x180073e7b  jz      loc_1800742DE
0x180073e81  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x180073e88  jz      short loc_180073EC9
0x180073e8a  mov     r10d, 3
0x180073e90  mov     ecx, r10d
0x180073e93  call    IsWppLevelEnabled
0x180073e98  test    al, al
0x180073e9a  jz      short loc_180073EC9
0x180073e9c  mov     [rsp+350h+lpcbData], r8
0x180073ea1  lea     rax, aFoundLocalServ; "Found local service! (%ws)"
0x180073ea8  mov     r8d, 0B9h
0x180073eae  mov     [rsp+350h+phkResult], rax
0x180073eb3  mov     r9d, r10d
0x180073eb6  lea     rdx, aCcomprocessinf; "CComProcessInfo::FinalConstruct"
0x180073ebd  lea     rcx, aOnecoreComComb_51; "onecore\\com\\combase\\catalog\\process"...
0x180073ec4  call    ??$ComTraceMessageT@PEBG@@YAXPEBD0HW4TraceLevel@@PEBG2@Z; ComTraceMessageT<ushort const *>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *)
0x180073ec9  mov     rcx, [rbp+250h+KeyHandle]; hkey
0x180073ecd  lea     rax, [rdi+58h]
0x180073ed1  mov     r9d, 2; unsigned int
0x180073ed7  mov     [rsp+350h+phkResult], rax; int
0x180073edc  lea     r8, ?ServiceParameters@Constants@Catalog@Com@@3QBGB; "ServiceParameters"
0x180073ee3  mov     dword ptr [rdi+48h], 1
0x180073eea  xor     edx, edx; lpSubKey
0x180073eec  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x180073ef1  mov     ecx, 80000000h
0x180073ef6  mov     ebx, eax
0x180073ef8  add     eax, ecx
0x180073efa  test    ecx, eax
0x180073efc  jnz     short loc_180073F4D
0x180073efe  cmp     ebx, 80070002h
0x180073f04  jz      short loc_180073F4D
0x180073f06  mov     eax, cs:dword_18014E4B8
0x180073f0c  xor     r8d, r8d
0x180073f0f  test    eax, eax
0x180073f11  jnz     short loc_180073F2F
0x180073f13  cmp     cs:?gfEnableTracing@@3HA, r8d; int gfEnableTracing
0x180073f1a  jz      loc_180075A96
0x180073f20  xor     ecx, ecx
0x180073f22  call    IsWppLevelEnabled
0x180073f27  test    al, al
0x180073f29  jz      loc_180075A96
0x180073f2f  mov     rdx, r13; struct _GUID *
0x180073f32  lea     rcx, [rbp+250h+var_2A0]; this
0x180073f36  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x180073f3b  lea     rcx, ?ServiceParameters@Constants@Catalog@Com@@3QBGB; "ServiceParameters"
0x180073f42  mov     r8d, 0C1h
0x180073f48  jmp     loc_180075A72
0x180073f4d  mov     rcx, [r14]; unsigned __int16 *
0x180073f50  lea     r8, [rsp+350h+var_2D8]; bool *
0x180073f55  xor     eax, eax
0x180073f57  lea     rdx, [rsp+350h+var_2D7]; bool *
0x180073f5c  mov     [rsp+350h+var_2D7], al
0x180073f60  mov     [rsp+350h+var_2D8], al
0x180073f64  call    ?IsUserOrPackagedService@@YAJPEBGPEA_N1@Z; IsUserOrPackagedService(ushort const *,bool *,bool *)
0x180073f69  mov     ebx, eax
0x180073f6b  test    eax, eax
0x180073f6d  jns     loc_18007404A
0x180073f73  mov     rcx, [rbp+258h]; this
0x180073f7a  lea     r8, aOnecoreComComb_51; "onecore\\com\\combase\\catalog\\process"...
0x180073f81  mov     r9d, eax; char *
0x180073f84  mov     edx, 0C8h; void *
0x180073f89  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073f8e  cmp     ebx, 80070424h
0x180073f94  jnz     loc_180075A96
0x180073f9a  xor     r15d, r15d
0x180073f9d  mov     rcx, [rbp+250h+KeyHandle]; HKEY
0x180073fa1  lea     r9, [rbp+250h+var_250]; unsigned __int16 *
0x180073fa5  mov     r14d, 100h
0x180073fab  mov     dword ptr [rdi+70h], 2
0x180073fb2  lea     r8, ?RunAs@Constants@Catalog@Com@@3QBGB; "RunAs"
0x180073fb9  mov     dword ptr [rsp+350h+phkResult], r14d; unsigned int
0x180073fbe  call    ?ReadRegistryStringValue@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; ReadRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x180073fc3  mov     ebx, eax
0x180073fc5  test    eax, eax
0x180073fc7  js      loc_1800746B4
0x180073fcd  cmp     [rbp+250h+var_250], r15w
0x180073fd2  jz      loc_1800746B4
0x180073fd8  lea     rdx, ?Interactive_User@Constants@Catalog@Com@@3QBGB; "Interactive User"
0x180073fdf  lea     rcx, [rbp+250h+var_250]
0x180073fe3  call    cs:__imp__o__wcsicmp
0x180073fe9  test    eax, eax
0x180073feb  jnz     loc_18007458D
0x180073ff1  cmp     [rbp+250h+arg_38], r15b
0x180073ff8  jz      loc_180074540
0x180073ffe  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180074005  jz      loc_1800746B4
0x18007400b  lea     esi, [rax+3]
0x18007400e  mov     ecx, esi
0x180074010  call    IsWppLevelEnabled
0x180074015  test    al, al
0x180074017  jz      loc_1800746B4
0x18007401d  lea     rax, aIgnoringRunasI; "Ignoring RunAs: Interactive User"
0x180074024  mov     r9d, esi
0x180074027  mov     r8d, 197h
0x18007402d  mov     [rsp+350h+phkResult], rax
0x180074032  lea     rdx, aCcomprocessinf; "CComProcessInfo::FinalConstruct"
0x180074039  lea     rcx, aOnecoreComComb_51; "onecore\\com\\combase\\catalog\\process"...
0x180074040  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x180074045  jmp     loc_1800746B4
0x18007404a  xor     ebx, ebx
0x18007404c  cmp     [rsp+350h+var_2D7], bl
0x180074050  jz      short loc_180074059
0x180074052  or      dword ptr [rdi+0C0h], 40h
0x180074059  test    sil, sil
0x18007405c  jz      loc_1800741B4
0x180074062  xor     r15d, r15d
0x180074065  cmp     [rsp+350h+var_2D8], r15b
0x18007406a  jnz     short loc_1800740C1
0x18007406c  mov     eax, cs:dword_18014E4B8
0x180074072  mov     ebx, 80040157h
0x180074077  test    eax, eax
0x180074079  jnz     short loc_180074097
0x18007407b  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180074082  jz      loc_180075A96
0x180074088  xor     ecx, ecx
0x18007408a  call    IsWppLevelEnabled
0x18007408f  test    al, al
0x180074091  jz      loc_180075A96
0x180074097  mov     rdx, r13; struct _GUID *
0x18007409a  lea     rcx, [rbp+250h+var_2A0]; this
0x18007409e  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800740a3  mov     [rsp+350h+var_308], sil
0x1800740a8  mov     byte ptr [rsp+350h+var_310], r15b
0x1800740ad  mov     [rsp+350h+var_320], r12
0x1800740b2  mov     [rsp+350h+lpcbData], rax
0x1800740b7  call    ??$ComTraceMessageT@PEAGPEAGPEBG_N_NJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG32_N4J@Z; ComTraceMessageT<ushort *,ushort *,ushort const *,bool,bool,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,ushort const *,bool,bool,long)
0x1800740bc  jmp     loc_180075A96
0x1800740c1  mov     rcx, [r14]; unsigned __int16 *
0x1800740c4  lea     rdx, [rsp+350h+sourceString]; unsigned __int16 **
0x1800740c9  mov     [rsp+350h+sourceString], r15
0x1800740ce  call    ?GetServicePackageNameFromScmRegistration@CComProcessInfo@@CAJPEBGPEAPEAG@Z; CComProcessInfo::GetServicePackageNameFromScmRegistration(ushort const *,ushort * *)
0x1800740d3  mov     rsi, [rsp+350h+sourceString]
0x1800740d8  test    eax, eax
0x1800740da  js      short loc_18007412A
0x1800740dc  mov     rcx, [rdi+100h]; string
0x1800740e3  xor     edx, edx; length
0x1800740e5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800740eb  mov     rdx, rax; unsigned __int16 *
  ... truncated ...
```
