# CComProcessInfo::FinalConstruct(IUserToken *,_GUID const &,ushort *,HKEY__ *,HKEY__ *,int,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool)

- ea: `0x1800782dc`
- end: `0x18007a284`
- name: `?FinalConstruct@CComProcessInfo@@QEAAJPEAUIUserToken@@AEBU_GUID@@PEAGPEAUHKEY__@@3H_N44444444444@Z`
- size: `8104`
- prototype: `int(CComProcessInfo *__hidden this, struct IUserToken *, const struct _GUID *, unsigned __int16 *, HKEY, HKEY, int, bool, bool, bool, bool, bool, bool, bool, bool, bool, bool, bool, bool)`
- caller_count: `1`
- callee_count: `39`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180057360`

## callees

- `0x1800065a4`
- `0x18000fb8c`
- `0x180010094`
- `0x180011db0`
- `0x18001a374`
- `0x18001c624`
- `0x180024e18`
- `0x1800256dc`
- `0x180025b54`
- `0x180026870`
- `0x180027a0c`
- `0x180034260`
- `0x180039a7c`
- `0x18003deac`
- `0x18003dfc8`
- `0x18004b524`
- `0x1800535d0`
- `0x18005bcb0`
- `0x180063ad0`
- `0x180064c50`
- `0x180071404`
- `0x1800782dc`
- `0x180081158`
- `0x1800858f0`
- `0x18009e160`
- `0x1800a3750`
- `0x1800a7388`
- `0x1800a780c`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x1800d1354`
- `0x1800d2db0`
- `0x1800d4728`
- `0x1800ef0ec`
- `0x1800ef164`
- `0x1800ef1d0`
- `0x1800ef344`
- `0x1800ef460`
- `0x180114010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800786f1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800786f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078831`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800788cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007899e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078a2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079544`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078831`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800788cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007899e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078a2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079544`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078d71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078ddf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800794d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078d71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078ddf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800794d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007963d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079997`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007963d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079997`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180078f60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007973a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180078f60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007973a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180078fb4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079273`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800793c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079496`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079522`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007977d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800797e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800799db`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079afb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079bbf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079c9a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a06d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180078fb4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079273`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800793c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079496`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079522`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007977d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800797e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800799db`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079afb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079bbf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079c9a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a06d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800787f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078876`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800789e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800787f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078876`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800789e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180078553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180078973`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180078553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180078973`

## string_xrefs

- `0x180078464`: `LocalService`
- `0x1800784c4`: `LocalService`
- `0x1800783ae`: `CComProcessInfo::FinalConstruct`
- `0x180078423`: `CComProcessInfo::FinalConstruct`
- `0x1800785c4`: `CComProcessInfo::FinalConstruct`
- `0x180078746`: `CComProcessInfo::FinalConstruct`
- `0x180078aa5`: `CComProcessInfo::FinalConstruct`
- `0x180078af8`: `CComProcessInfo::FinalConstruct`
- `0x180078c68`: `CComProcessInfo::FinalConstruct`
- `0x180078cb2`: `CComProcessInfo::FinalConstruct`
- `0x180078cf6`: `CComProcessInfo::FinalConstruct`
- `0x180078e7d`: `CComProcessInfo::FinalConstruct`
- `0x18007958a`: `CComProcessInfo::FinalConstruct`
- `0x180079693`: `CComProcessInfo::FinalConstruct`
- `0x180079b42`: `CComProcessInfo::FinalConstruct`
- `0x180079c34`: `CComProcessInfo::FinalConstruct`
- `0x18007839c`: `onecore\com\combase\catalog\process.cxx`
- `0x18007842f`: `onecore\com\combase\catalog\process.cxx`
- `0x1800785cb`: `onecore\com\combase\catalog\process.cxx`
- `0x180078688`: `onecore\com\combase\catalog\process.cxx`
- `0x18007874d`: `onecore\com\combase\catalog\process.cxx`
- `0x1800789b5`: `onecore\com\combase\catalog\process.cxx`
- `0x180078aac`: `onecore\com\combase\catalog\process.cxx`
- `0x180078aff`: `onecore\com\combase\catalog\process.cxx`
- `0x180078c6f`: `onecore\com\combase\catalog\process.cxx`
- `0x180078cb9`: `onecore\com\combase\catalog\process.cxx`
- `0x180078d0a`: `onecore\com\combase\catalog\process.cxx`
- `0x180078e84`: `onecore\com\combase\catalog\process.cxx`
- `0x180079595`: `onecore\com\combase\catalog\process.cxx`
- `0x1800796ae`: `onecore\com\combase\catalog\process.cxx`
- `0x180079b4d`: `onecore\com\combase\catalog\process.cxx`
- `0x180079c3b`: `onecore\com\combase\catalog\process.cxx`
- `0x18007a0dc`: `onecore\com\combase\catalog\process.cxx`
- `0x1800785af`: `Found local service! (%ws)`
- `0x18007843e`: `CLSID:%ws APPID:%ws %!HRESULT!`
- `0x180078efa`: `CLSID:%ws APPID:%ws Value:%ws %!HRESULT!`
- `0x18007a248`: `CLSID:%ws APPID:%ws Value:%ws %!HRESULT!`
- `0x180078c53`: `No surrogate, No service.`
- `0x180078a90`: `Found surrogate: dllhost`
- `0x18007919c`: `APPIDREGFLAGS_IUSERVER_UNMODIFIED_SESSION_LOGON_TOKENUSER server must be APPIDREGFLAGS_IUSERVER_UNMODIFIED_LOGON_TOKEN CLSID:%ws APPID:%ws Value:%ws %!HRESULT!`
- `0x180079211`: `APPIDREGFLAGS_IUSERVER_UNMODIFIED_SESSION_LOGON_TOKENUSER and APPIDREGFLAGS_IUSERVER_UNMODIFIED_CLIENT_LOGON_TOKENUSER are mutually exclusive CLSID:%ws APPID:%ws Value:%ws %!HRESULT!`
- `0x1800790a5`: `Session Virtual Account server must be AAA CLSID:%ws APPID:%ws Value:%ws %!HRESULT!`
- `0x180079124`: `APPIDREGFLAGS_IUSERVER_UNMODIFIED_CLIENT_LOGON_TOKENUSER server must be APPIDREGFLAGS_IUSERVER_UNMODIFIED_LOGON_TOKEN CLSID:%ws APPID:%ws Value:%ws %!HRESULT!`
- `0x18007a0fe`: `CLSID:%ws APPID:%ws Value:%ws hr:%#x`
- `0x1800797da`: `LegacyImpersonationLevel`
- `0x180079973`: `LegacyImpersonationLevel`
- `0x180078b6a`: `DllSurrogateExecutable`
- `0x180078a50`: `DllSurrogate`
- `0x18007a22d`: `DllSurrogate`
- `0x1800785ea`: `ServiceParameters`
- `0x180078649`: `ServiceParameters`

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
  int v24; // r8d
  unsigned int RegistryStringValue; // ebx
  CGuidStr *v26; // rax
  const unsigned __int16 **v27; // r14
  CGuidStr *v28; // rax
  int v29; // edx
  int v30; // r9d
  const WCHAR *v31; // rcx
  int v32; // r8d
  __int64 (__fastcall *v33)(RegistrationChangeDetection *, PCNZWCH *); // rbx
  __int64 v34; // rdx
  unsigned __int16 *v35; // r8
  __int64 v36; // r8
  int v37; // r10d
  HKEY v38; // rcx
  const unsigned __int16 *v39; // rcx
  int v40; // eax
  const unsigned __int16 *v41; // rdx
  HKEY v42; // rcx
  const unsigned __int16 *v43; // rdx
  CGuidStr *v44; // rax
  int v45; // edx
  int v46; // ecx
  int v47; // r8d
  int v48; // r9d
  const unsigned __int16 *v49; // rcx
  int ServicePackageNameFromScmRegistration; // eax
  WCHAR *v51; // rsi
  const unsigned __int16 *StringRawBuffer; // rax
  CGuidStr *v53; // rax
  int v54; // edx
  int v55; // ecx
  int v56; // r8d
  int v57; // r9d
  __int64 v58; // r11
  char v59; // r14
  __int64 *v60; // rcx
  const unsigned __int16 *v61; // rcx
  int v62; // eax
  WCHAR *v63; // rsi
  __int64 v64; // rdx
  const unsigned __int16 *v65; // rbx
  unsigned __int64 v66; // rdx
  unsigned __int8 v67; // cl
  __int64 v68; // rcx
  ComTrace *v69; // rcx
  HKEY v70; // r14
  HKEY v71; // rcx
  int v72; // r8d
  __int64 v73; // r8
  CGuidStr *v74; // rax
  int v75; // edx
  int v76; // ecx
  int v77; // r9d
  CGuidStr *v78; // rax
  int v79; // edx
  int v80; // ecx
  int v81; // r9d
  int v82; // r8d
  __int64 v83; // rdx
  unsigned __int16 v84; // ax
  unsigned __int16 *v85; // rcx
  unsigned int v86; // esi
  SIZE_T v87; // rax
  unsigned __int16 *v88; // rax
  unsigned int v89; // eax
  unsigned int v90; // ebx
  SIZE_T v91; // rax
  unsigned __int16 *v92; // rax
  int v93; // eax
  __int64 v94; // r8
  int v95; // r9d
  LSTATUS v96; // eax
  LSTATUS v97; // eax
  CGuidStr *v98; // rax
  int v99; // edx
  int v100; // ecx
  int v101; // r9d
  int v102; // ecx
  CGuidStr *v103; // rax
  int v104; // edx
  int v105; // r9d
  CGuidStr *v106; // rax
  int v107; // edx
  int v108; // r9d
  CGuidStr *v109; // rax
  int v110; // edx
  int v111; // r9d
  CGuidStr *v112; // rax
  int v113; // edx
  int v114; // r9d
  LPCWSTR v115; // r15
  unsigned int v116; // r12d
  LSTATUS v117; // eax
  CGuidStr *v118; // rax
  int v119; // edx
  int v120; // r9d
  CGuidStr *v121; // rax
  int v122; // edx
  int v123; // r9d
  LSTATUS v124; // eax
  CGuidStr *v125; // rax
  int v126; // edx
  int v127; // r9d
  LSTATUS v128; // eax
  BYTE *v129; // r15
  int v130; // r9d
  CGuidStr *v131; // rax
  int v132; // edx
  int v133; // r9d
  CGuidStr *v134; // rax
  int v135; // r9d
  HKEY v136; // r12
  int RegistrySecurityDescriptor; // eax
  LSTATUS v138; // eax
  LPCWSTR v139; // r15
  LSTATUS v140; // eax
  CGuidStr *v141; // rax
  int v142; // edx
  int v143; // r9d
  int v144; // r8d
  CGuidStr *v145; // rax
  int v146; // edx
  int v147; // r9d
  int v148; // r8d
  LSTATUS v149; // eax
  CGuidStr *v150; // rax
  int v151; // edx
  int v152; // r9d
  int v153; // eax
  LSTATUS v154; // eax
  int v155; // r8d
  int v156; // eax
  LSTATUS v157; // eax
  int v158; // r8d
  int v159; // r9d
  LSTATUS v160; // eax
  LPCWSTR v161; // r15
  RegistrationChangeDetection *v162; // rcx
  struct RegistrationChangeDetection::IPerUserCacheInformation **v163; // r9
  CGuidStr *v164; // rax
  int v165; // edx
  int v166; // r9d
  CGuidStr *v167; // rax
  int v168; // edx
  int v169; // r9d
  CGuidStr *v170; // rax
  int v171; // edx
  int v172; // r9d
  CGuidStr *v173; // rax
  int v174; // edx
  int v175; // r9d
  CGuidStr *v176; // rax
  int v177; // edx
  int v178; // r9d
  CGuidStr *v179; // rax
  int v180; // edx
  int v181; // r9d
  CGuidStr *v182; // rax
  int v183; // edx
  int v184; // r9d
  LSTATUS v185; // eax
  const char *v186; // rax
  CGuidStr *v187; // rax
  int v188; // edx
  int v189; // r9d
  CGuidStr *v190; // rax
  int v191; // edx
  int v192; // r9d
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcbDataa; // [rsp+28h] [rbp-D8h]
  __int64 v198; // [rsp+30h] [rbp-D0h]
  __int64 v199; // [rsp+38h] [rbp-C8h]
  __int64 v200; // [rsp+40h] [rbp-C0h]
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+64h] [rbp-9Ch] BYREF
  LPCWSTR lpSubKey; // [rsp+68h] [rbp-98h]
  PCNZWCH sourceString; // [rsp+70h] [rbp-90h] BYREF
  bool v205; // [rsp+78h] [rbp-88h] BYREF
  bool v206; // [rsp+79h] [rbp-87h] BYREF
  BYTE Data[4]; // [rsp+7Ch] [rbp-84h] BYREF
  HKEY v208; // [rsp+80h] [rbp-80h] BYREF
  HKEY KeyHandle; // [rsp+88h] [rbp-78h]
  HKEY v210; // [rsp+90h] [rbp-70h] BYREF
  RegistrationChangeDetection *v211; // [rsp+98h] [rbp-68h]
  HKEY hKey; // [rsp+A0h] [rbp-60h]
  _BYTE v213[80]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v214[256]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  v211 = a2;
  KeyHandle = hkey;
  hKey = a6;
  cbData = 0;
  Type = 0;
  lpSubKey = a4;
  memset_0(v214, 0, sizeof(v214));
  v22 = gfEnableTracing == 0;
  v23 = *a3;
  v210 = 0;
  *((struct _GUID *)this + 3) = v23;
  *(_DWORD *)Data = 0;
  *((_DWORD *)this + 54) = a7;
  if ( !v22 && (unsigned __int8)IsWppLevelEnabled(3) )
  {
    LODWORD(phkResult) = v24;
    ComTraceMessage(
      0xFFFFFFFFLL,
      "onecore\\com\\combase\\catalog\\process.cxx",
      "CComProcessInfo::FinalConstruct",
      136,
      phkResult,
      L"AppID %!GUID!",
      a3);
  }
  RegistryStringValue = GetRegistryStringValue(hkey, 0, 0, 2u, (unsigned __int16 **)this + 8);
  if ( (int)(RegistryStringValue + 0x80000000) >= 0 && RegistryStringValue != -2147024894 )
  {
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8) )
    {
      v26 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
      ComTraceMessageT<unsigned short *,unsigned short *,long>(
        (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
        (unsigned int)"CComProcessInfo::FinalConstruct",
        146,
        0,
        (__int64)L"CLSID:%ws APPID:%ws %!HRESULT!",
        v26,
        a4,
        RegistryStringValue);
    }
    return RegistryStringValue;
  }
  v27 = (const unsigned __int16 **)((char *)this + 80);
  RegistryStringValue = GetRegistryStringValue(hkey, 0, L"LocalService", 2u, (unsigned __int16 **)this + 10);
  if ( (int)(RegistryStringValue + 0x80000000) >= 0 && RegistryStringValue != -2147024894 )
  {
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
      return RegistryStringValue;
    v28 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
    v31 = L"LocalService";
    v32 = 162;
    goto LABEL_429;
  }
  if ( a19 )
  {
    sourceString = 0;
    v33 = *(__int64 (__fastcall **)(RegistrationChangeDetection *, PCNZWCH *))(*(_QWORD *)v211 + 80LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &sourceString,
      0);
    RegistryStringValue = v33(v211, &sourceString);
    if ( (RegistryStringValue & 0x80000000) != 0 )
      goto LABEL_18;
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      (char *)this + 256,
      0);
    v34 = -1;
    do
      ++v34;
    while ( sourceString[v34] );
    RegistryStringValue = WindowsCreateString(sourceString, v34, (HSTRING *)this + 32);
    if ( (RegistryStringValue & 0x80000000) != 0 )
    {
LABEL_18:
      utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&sourceString);
      return RegistryStringValue;
    }
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&sourceString);
  }
  v35 = (unsigned __int16 *)*v27;
  if ( *v27 )
  {
    if ( *v35 )
    {
      if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
        ComTraceMessageT<unsigned short const *>(
          (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
          (unsigned int)"CComProcessInfo::FinalConstruct",
          185,
          v37,
          (__int64)L"Found local service! (%ws)",
          v36);
      v38 = KeyHandle;
      *((_DWORD *)this + 18) = 1;
      RegistryStringValue = GetRegistryStringValue(v38, 0, L"ServiceParameters", 2u, (unsigned __int16 **)this + 11);
      if ( (int)(RegistryStringValue + 0x80000000) >= 0 && RegistryStringValue != -2147024894 )
      {
        if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
          return RegistryStringValue;
        v28 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
        v31 = L"ServiceParameters";
        v32 = 193;
        goto LABEL_429;
      }
      v39 = *v27;
      v206 = 0;
      v205 = 0;
      v40 = IsUserOrPackagedService(v39, &v206, &v205);
      RegistryStringValue = v40;
      if ( v40 >= 0 )
      {
        if ( v206 )
          *((_DWORD *)this + 48) |= 0x40u;
        if ( a19 )
        {
          if ( !v205 )
          {
            RegistryStringValue = -2147221161;
            if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
            {
              v44 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
              ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,bool,bool,long>(
                v46,
                v45,
                v47,
                v48,
                phkResulta,
                (__int64)v44,
                (__int64)a4);
            }
            return RegistryStringValue;
          }
          v49 = *v27;
          sourceString = 0;
          ServicePackageNameFromScmRegistration = CComProcessInfo::GetServicePackageNameFromScmRegistration(
                                                    v49,
                                                    (unsigned __int16 **)&sourceString);
          v51 = (WCHAR *)sourceString;
          if ( ServicePackageNameFromScmRegistration < 0
            || (StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 32), 0),
                !PackageNamesMatch(v51, StringRawBuffer)) )
          {
            RegistryStringValue = -2147221161;
            if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
            {
              WindowsGetStringRawBuffer(*((HSTRING *)this + 32), 0);
              v53 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
              ComTraceMessageT<unsigned short *,unsigned short *,unsigned short *,unsigned short const *,long>(
                v55,
                v54,
                v56,
                v57,
                phkResulta,
                (__int64)v53,
                (__int64)a4,
                (__int64)v51,
                v58);
            }
            if ( v51 && v51 != (WCHAR *)&g_wszEmptyString )
              HeapFree(g_hHeap, 0, v51);
            return RegistryStringValue;
          }
          if ( v51 && v51 != (WCHAR *)&g_wszEmptyString )
            HeapFree(g_hHeap, 0, v51);
          *((_DWORD *)this + 48) |= 0x80u;
        }
        else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
               && v205 )
        {
          v59 = 0;
          v60 = qword_180157AA0;
          while ( *((_QWORD *)this + 6) != *v60 || *((_QWORD *)this + 7) != v60[1] )
          {
            v60 += 2;
            if ( v60 == (__int64 *)&gWIPTbl )
              goto LABEL_72;
          }
          v59 = 1;
LABEL_72:
          v61 = (const unsigned __int16 *)*((_QWORD *)this + 10);
          sourceString = 0;
          v62 = CComProcessInfo::GetServicePackageNameFromScmRegistration(v61, (unsigned __int16 **)&sourceString);
          v63 = (WCHAR *)sourceString;
          RegistryStringValue = v62;
          if ( v62 >= 0 )
          {
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
              (char *)this + 256,
              0);
            v64 = -1;
            do
              ++v64;
            while ( v63[v64] );
            RegistryStringValue = WindowsCreateString(v63, v64, (HSTRING *)this + 32);
          }
          if ( v63 && v63 != (WCHAR *)&g_wszEmptyString )
            HeapFree(g_hHeap, 0, v63);
          if ( (RegistryStringValue & 0x80000000) != 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x12E,
              (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
              (const char *)RegistryStringValue,
              phkResulta);
            return RegistryStringValue;
          }
          if ( !v59 )
          {
            v65 = WindowsGetStringRawBuffer(*((HSTRING *)this + 32), 0);
            if ( ComTrace::IsEnabled(v67, v66) )
            {
              wil::details::static_lazy<ComTrace>::get(
                v68,
                _lambda_f8a79a44bba2ee3470b25df359f31864_::_lambda_invoker_cdecl_);
              ComTrace::PackagedServiceComRegistrationInHKLM_(
                v69,
                *((const unsigned __int16 **)this + 10),
                v65,
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
          (const char *)(unsigned int)v40,
          phkResulta);
        if ( RegistryStringValue != -2147023836 )
          return RegistryStringValue;
      }
      goto LABEL_36;
    }
    if ( v35 != (unsigned __int16 *)&g_wszEmptyString )
      HeapFree(g_hHeap, 0, v35);
  }
  v70 = KeyHandle;
  v71 = KeyHandle;
  *((_QWORD *)this + 10) = 0;
  RegistryStringValue = GetRegistryStringValue(v71, 0, L"DllSurrogate", 0, (unsigned __int16 **)this + 15);
  if ( (RegistryStringValue & 0x80000000) != 0 )
  {
    if ( RegistryStringValue != -2147024894 )
    {
      if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
        return RegistryStringValue;
      v28 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
      v31 = L"DllSurrogate";
      v32 = 391;
LABEL_429:
      ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
        (_DWORD)v31,
        v29,
        v32,
        v30,
        (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
        v28,
        a4,
        v31,
        RegistryStringValue);
      return RegistryStringValue;
    }
    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      ComTraceMessageT<>(
        (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
        (unsigned int)"CComProcessInfo::FinalConstruct",
        385,
        v82,
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
        v72,
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
        v73);
    *((_DWORD *)this + 18) = 3;
    RegistryStringValue = GetRegistryStringValue(v70, 0, L"DebugSurrogate", 0, (unsigned __int16 **)this + 28);
    if ( (RegistryStringValue & 0x80000000) != 0 )
    {
      if ( RegistryStringValue != -2147024894 )
      {
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v78 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            v80,
            v79,
            356,
            v81,
            (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v78,
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
      RegistryStringValue = GetRegistryStringValue(v70, 0, L"DllSurrogateExecutable", 0, (unsigned __int16 **)this + 29);
      if ( (int)(RegistryStringValue + 0x80000000) >= 0 && RegistryStringValue != -2147024894 )
      {
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v74 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            v76,
            v75,
            375,
            v77,
            (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v74,
            a4,
            L"DllSurrogateExecutable",
            RegistryStringValue);
        }
        return RegistryStringValue;
      }
    }
  }
LABEL_36:
  v42 = KeyHandle;
  *((_DWORD *)this + 28) = 2;
  RegistryStringValue = ReadRegistryStringValue(v42, v41, L"RunAs", v214, 0x100u);
  if ( (RegistryStringValue & 0x80000000) != 0 || !v214[0] )
    goto LABEL_140;
  if ( (unsigned int)_o__wcsicmp(v214, L"Interactive User") )
  {
    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      ComTraceMessageT<unsigned short const *>(
        (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
        (unsigned int)"CComProcessInfo::FinalConstruct",
        418,
        3,
        (__int64)L"Found RunAs: %ws",
        v214);
    *((_DWORD *)this + 28) = 0;
    v83 = -1;
    do
      ++v83;
    while ( v214[v83] );
    v84 = v214[0];
    v85 = v214;
    while ( v84 && v84 != 92 )
      v84 = *++v85;
    if ( *v85 )
    {
      v90 = v83 + 1;
      v91 = 2LL * (unsigned int)(v83 + 1);
      if ( !is_mul_ok((unsigned int)(v83 + 1), 2u) )
        v91 = -1;
      v92 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v91);
      *((_QWORD *)this + 13) = v92;
      if ( v92 )
      {
        v89 = StringCchCopyW(v92, v90, v214);
        goto LABEL_139;
      }
    }
    else
    {
      v86 = v83 + 4;
      v87 = 2LL * (unsigned int)(v83 + 4);
      if ( !is_mul_ok((unsigned int)(v83 + 4), 2u) )
        v87 = -1;
      v88 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v87);
      *((_QWORD *)this + 13) = v88;
      if ( v88 )
      {
        RegistryStringValue = StringCchCopyW(v88, v86, &byte_180157910);
        if ( (RegistryStringValue & 0x80000000) != 0 )
          goto LABEL_140;
        RegistryStringValue = StringCchCatW(*((unsigned __int16 **)this + 13), v86, L"\\");
        if ( (RegistryStringValue & 0x80000000) != 0 )
          goto LABEL_140;
        v89 = StringCchCatW(*((unsigned __int16 **)this + 13), v86, v214);
LABEL_139:
        RegistryStringValue = v89;
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
    v93 = GetRegistryStringValue(KeyHandle, 0, L"ApplicationId", 0, (unsigned __int16 **)this + 31);
    RegistryStringValue = v93;
    if ( v93 < 0 )
    {
      if ( v93 != -2147024894 )
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
          v95,
          (__int64)L"Found ApplicationId: %ws",
          v94);
      *((_DWORD *)this + 28) = 4;
    }
  }
  *((_DWORD *)this + 24) = 0;
  if ( a10 )
  {
    RegistryStringValue = ReadRegistryStringValue(KeyHandle, v43, L"ActivateAtStorage", v214, 0x100u);
    if ( (RegistryStringValue & 0x80000000) != 0 )
    {
      if ( RegistryStringValue != -2147024894 )
      {
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v98 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            v100,
            v99,
            526,
            v101,
            (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v98,
            a4,
            L"ActivateAtStorage",
            RegistryStringValue);
        }
        return RegistryStringValue;
      }
      RegistryStringValue = 0;
    }
    else if ( ((v214[0] - 89) & 0xFFDF) == 0 )
    {
      *((_DWORD *)this + 24) = 1;
    }
  }
  *((_DWORD *)this + 38) = 0;
  v208 = 0;
  *((_QWORD *)this + 18) = 0;
  *((_OWORD *)this + 10) = 0;
  if ( a11 || a12 || a13 )
  {
    v96 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &v208);
    if ( v96 )
    {
      if ( v96 == 2 )
        goto LABEL_263;
      if ( v96 > 0 )
        RegistryStringValue = (unsigned __int16)v96 | 0x80070000;
      else
        RegistryStringValue = v96;
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v134 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
        ComTraceMessageT<unsigned short *,unsigned short const *,unsigned short const *,long>(
          (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
          (unsigned int)"CComProcessInfo::FinalConstruct",
          764,
          v135,
          (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
          v134,
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
      v97 = RegQueryValueExW(v208, L"AppIDFlags", 0, &Type, (LPBYTE)&sourceString, &cbData);
      if ( v97 )
      {
        if ( v97 == 2 )
        {
          RegistryStringValue = 0;
        }
        else
        {
          if ( v97 > 0 )
            RegistryStringValue = (unsigned __int16)v97 | 0x80070000;
          else
            RegistryStringValue = v97;
          if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          {
            v118 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
            v115 = lpSubKey;
            ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
              (unsigned int)L"AppIDFlags",
              v119,
              573,
              v120,
              (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
              v118,
              lpSubKey,
              L"AppIDFlags",
              RegistryStringValue);
LABEL_195:
            if ( a12 )
            {
              cbData = 4;
              v116 = 0;
              LODWORD(sourceString) = 0;
              v117 = RegQueryValueExW(v208, L"ROTFlags", 0, &Type, (LPBYTE)&sourceString, &cbData);
              if ( v117 )
              {
                if ( v117 == 2 )
                {
                  RegistryStringValue = 0;
                }
                else
                {
                  if ( v117 > 0 )
                    RegistryStringValue = (unsigned __int16)v117 | 0x80070000;
                  else
                    RegistryStringValue = v117;
                  if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
                  {
                    v121 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
                    LODWORD(v200) = RegistryStringValue;
                    ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
                      (unsigned int)L"ROTFlags",
                      v122,
                      694,
                      v123,
                      (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
                      v121,
                      v115,
                      L"ROTFlags",
                      v200);
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
              v124 = RegQueryValueExW(v208, L"MGOTFlags", 0, &Type, (LPBYTE)&sourceString, &cbData);
              if ( v124 )
              {
                if ( v124 == 2 )
                {
                  RegistryStringValue = 0;
                }
                else
                {
                  if ( v124 > 0 )
                    RegistryStringValue = (unsigned __int16)v124 | 0x80070000;
                  else
                    RegistryStringValue = v124;
                  if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
                  {
                    v125 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
                    LODWORD(v200) = RegistryStringValue;
                    ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
                      (unsigned int)L"MGOTFlags",
                      v126,
                      714,
                      v127,
                      (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
                      v125,
                      v115,
                      L"MGOTFlags",
                      v200);
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
              v116 = 0;
            }
            if ( !a13 )
              goto LABEL_253;
            v128 = RegQueryValueExW(v208, L"ProcessMitigationPolicy", 0, &Type, 0, &cbData);
            if ( v128 != 2 )
            {
              if ( v128 || Type != 3 || cbData <= 1 )
              {
                RegistryStringValue = -2147221165;
                if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
                {
                  v131 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
                  LODWORD(v200) = -2147221165;
                  ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
                    (unsigned int)L"ProcessMitigationPolicy",
                    v132,
                    752,
                    v133,
                    (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
                    v131,
                    v115,
                    L"ProcessMitigationPolicy",
                    v200);
                }
                goto LABEL_253;
              }
              v129 = (BYTE *)HeapAlloc(g_hHeap, 0, cbData);
              if ( !v129 )
              {
                RegistryStringValue = -2147024882;
LABEL_253:
                RegCloseKey(v208);
LABEL_262:
                if ( (RegistryStringValue & 0x80000000) != 0 )
                  return RegistryStringValue;
                goto LABEL_263;
              }
              v116 = RegistryStringValue;
              if ( (RegistryStringValue & 0x80000000) != 0 )
                goto LABEL_253;
              RegistryStringValue = RegQueryValueExW(v208, L"ProcessMitigationPolicy", 0, &Type, v129, &cbData);
              if ( RegistryStringValue )
              {
                HeapFree(g_hHeap, 0, v129);
                if ( (int)RegistryStringValue > 0 )
                  RegistryStringValue = (unsigned __int16)RegistryStringValue | 0x80070000;
                if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
                {
                  LODWORD(v200) = RegistryStringValue;
                  LODWORD(v199) = cbData;
                  LODWORD(v198) = Type;
                  ComTraceMessageT<unsigned short const *,unsigned long,unsigned long,long>(
                    (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
                    (unsigned int)"CComProcessInfo::FinalConstruct",
                    739,
                    v130,
                    (__int64)L"Value:%ws Type:%d Size:%d %!HRESULT!",
                    L"ProcessMitigationPolicy",
                    v198,
                    v199,
                    v200);
                }
                goto LABEL_253;
              }
              *((_DWORD *)this + 40) = cbData;
              *((_QWORD *)this + 21) = v129;
            }
            RegistryStringValue = v116;
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
        v102 = *((_DWORD *)this + 38);
        if ( (v102 & 0x100) != 0 )
        {
          if ( *((_DWORD *)this + 28) != 2 )
          {
            RegistryStringValue = -2147221165;
            if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
            {
              v103 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
              ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
                (unsigned int)L"AppIDFlags",
                v104,
                625,
                v105,
                (__int64)L"Session Virtual Account server must be AAA CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
                v103,
                lpSubKey,
                L"AppIDFlags",
                -2147221165);
            }
            return RegistryStringValue;
          }
          *((_DWORD *)this + 28) = 3;
        }
        if ( (v102 & 0x208) == 0x200 )
        {
          RegistryStringValue = -2147221165;
          if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          {
            v106 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
            ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
              (unsigned int)L"AppIDFlags",
              v107,
              642,
              v108,
              (__int64)L"APPIDREGFLAGS_IUSERVER_UNMODIFIED_CLIENT_LOGON_TOKENUSER server must be APPIDREGFLAGS_IUSERVER_UN"
                        "MODIFIED_LOGON_TOKEN CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
              v106,
              lpSubKey,
              L"AppIDFlags",
              -2147221165);
          }
          return RegistryStringValue;
        }
        if ( (v102 & 0x408) == 0x400 )
        {
          RegistryStringValue = -2147221165;
          if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          {
            v109 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
            ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
              (unsigned int)L"AppIDFlags",
              v110,
              655,
              v111,
              (__int64)L"APPIDREGFLAGS_IUSERVER_UNMODIFIED_SESSION_LOGON_TOKENUSER server must be APPIDREGFLAGS_IUSERVER_U"
                        "NMODIFIED_LOGON_TOKEN CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
              v109,
              lpSubKey,
              L"AppIDFlags",
              -2147221165);
          }
          return RegistryStringValue;
        }
        if ( (v102 & 0x600) == 0x600 )
        {
          RegistryStringValue = -2147221165;
          if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          {
            v112 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
            ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
              (unsigned int)L"AppIDFlags",
              v113,
              668,
              v114,
              (__int64)L"APPIDREGFLAGS_IUSERVER_UNMODIFIED_SESSION_LOGON_TOKENUSER and APPIDREGFLAGS_IUSERVER_UNMODIFIED_C"
                        "LIENT_LOGON_TOKENUSER are mutually exclusive CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
              v112,
              lpSubKey,
              L"AppIDFlags",
              -2147221165);
          }
          return RegistryStringValue;
        }
      }
    }
    v115 = lpSubKey;
    goto LABEL_195;
  }
LABEL_263:
  v136 = KeyHandle;
  RegistrySecurityDescriptor = GetRegistrySecurityDescriptor(
                                 KeyHandle,
                                 v43,
                                 (struct _SECURITY_DESCRIPTOR **)this + 16,
                                 (unsigned int *)this + 34);
  RegistryStringValue = RegistrySecurityDescriptor;
  if ( RegistrySecurityDescriptor < 0 )
  {
    if ( RegistrySecurityDescriptor != -2147221166 )
    {
      if ( RegistrySecurityDescriptor == -2147221165 )
      {
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v190 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
          LODWORD(v200) = -2147221165;
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            (unsigned int)L"LaunchPermission",
            v191,
            785,
            v192,
            (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v190,
            lpSubKey,
            L"LaunchPermission",
            v200);
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
    || RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\OLE", 0, 0x20019u, &v210) )
  {
    goto LABEL_307;
  }
  cbData = 4;
  v138 = RegQueryValueExW(v210, L"LegacyAuthenticationLevel", 0, &Type, Data, &cbData);
  if ( v138 )
  {
    if ( v138 == 2 )
    {
      RegistryStringValue = 0;
      goto LABEL_273;
    }
    if ( v138 > 0 )
      RegistryStringValue = (unsigned __int16)v138 | 0x80070000;
    else
      RegistryStringValue = v138;
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
      goto LABEL_273;
    v141 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
    v144 = 821;
    LODWORD(v200) = RegistryStringValue;
  }
  else
  {
    if ( Type == 4 && cbData == 4 )
    {
      CComProcessInfo::m_dwLegacyAuthenticationLevel = *(_DWORD *)Data;
LABEL_273:
      v139 = lpSubKey;
      goto LABEL_274;
    }
    RegistryStringValue = -2147221165;
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
      goto LABEL_273;
    v141 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
    v144 = 811;
    LODWORD(v200) = -2147221165;
  }
  v139 = lpSubKey;
  ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
    (unsigned int)L"LegacyAuthenticationLevel",
    v142,
    v144,
    v143,
    (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
    v141,
    lpSubKey,
    L"LegacyAuthenticationLevel",
    v200);
LABEL_274:
  cbData = 4;
  v140 = RegQueryValueExW(v210, L"LegacyImpersonationLevel", 0, &Type, Data, &cbData);
  if ( v140 )
  {
    if ( v140 == 2 )
    {
      RegistryStringValue = 0;
      goto LABEL_306;
    }
    if ( v140 > 0 )
      RegistryStringValue = (unsigned __int16)v140 | 0x80070000;
    else
      RegistryStringValue = v140;
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v145 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
      v148 = 846;
      LODWORD(v200) = RegistryStringValue;
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
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v145 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
      v148 = 836;
      LODWORD(v200) = -2147221165;
LABEL_305:
      ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
        (unsigned int)L"LegacyImpersonationLevel",
        v146,
        v148,
        v147,
        (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
        v145,
        v139,
        L"LegacyImpersonationLevel",
        v200);
    }
  }
LABEL_306:
  RegCloseKey(v210);
  if ( (RegistryStringValue & 0x80000000) != 0 )
    return RegistryStringValue;
LABEL_307:
  cbData = 4;
  v149 = RegQueryValueExW(v136, L"AuthenticationLevel", 0, &Type, (LPBYTE)this + 140, &cbData);
  RegistryStringValue = v149;
  if ( !v149 && Type == 4 || cbData == 4 )
  {
    RegistryStringValue = 0;
  }
  else
  {
    if ( !v149 )
    {
      RegistryStringValue = -2147221165;
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v150 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
        LODWORD(v200) = -2147221165;
        ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
          (unsigned int)L"AuthenticationLevel",
          v151,
          865,
          v152,
          (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
          v150,
          lpSubKey,
          L"AuthenticationLevel",
          v200);
      }
      return RegistryStringValue;
    }
    if ( v149 != 2 )
    {
      if ( v149 > 0 )
        RegistryStringValue = (unsigned __int16)v149 | 0x80070000;
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v187 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
        LODWORD(v200) = RegistryStringValue;
        ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
          (unsigned int)L"AuthenticationLevel",
          v188,
          877,
          v189,
          (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
          v187,
          lpSubKey,
          L"AuthenticationLevel",
          v200);
      }
      return RegistryStringValue;
    }
    RegistryStringValue = 0;
    *((_DWORD *)this + 35) = CComProcessInfo::m_dwLegacyAuthenticationLevel;
  }
  if ( a14 )
  {
    v153 = GetRegistryStringValue(v136, 0, L"RemoteServerName", 3u, (unsigned __int16 **)this + 23);
    RegistryStringValue = v153;
    if ( v153 < 0 )
    {
      if ( v153 != -2147024894 )
      {
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v164 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
          LODWORD(v200) = RegistryStringValue;
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            (unsigned int)L"RemoteServerName",
            v165,
            891,
            v166,
            (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v164,
            lpSubKey,
            L"RemoteServerName",
            v200);
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
    v154 = RegQueryValueExW(v136, L"SRPTrustLevel", 0, &Type, (LPBYTE)&sourceString, &cbData);
    if ( v154 )
    {
      if ( v154 != 2 )
      {
        if ( v154 > 0 )
          RegistryStringValue = (unsigned __int16)v154 | 0x80070000;
        else
          RegistryStringValue = v154;
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v170 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
          LODWORD(v200) = RegistryStringValue;
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            (unsigned int)L"SRPTrustLevel",
            v171,
            925,
            v172,
            (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v170,
            lpSubKey,
            L"SRPTrustLevel",
            v200);
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
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v167 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
          LODWORD(v200) = -2147221165;
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            (unsigned int)L"SRPTrustLevel",
            v168,
            913,
            v169,
            (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v167,
            lpSubKey,
            L"SRPTrustLevel",
            v200);
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
          v155,
          (__int64)L"Found SAFER Level: %#x",
          lpcbData);
      }
      v156 = (int)sourceString;
      *((_DWORD *)this + 48) |= 0x10u;
      *((_DWORD *)this + 49) = v156;
    }
  }
  if ( a16 )
  {
    LODWORD(sourceString) = 0;
    cbData = 4;
    v157 = RegQueryValueExW(v136, L"PreferredServerBitness", 0, &Type, (LPBYTE)&sourceString, &cbData);
    if ( v157 )
    {
      if ( v157 != 2 )
      {
        if ( v157 > 0 )
          RegistryStringValue = (unsigned __int16)v157 | 0x80070000;
        else
          RegistryStringValue = v157;
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v176 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
          LODWORD(v200) = RegistryStringValue;
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            (unsigned int)L"PreferredServerBitness",
            v177,
            962,
            v178,
            (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v176,
            lpSubKey,
            L"PreferredServerBitness",
            v200);
        }
        return RegistryStringValue;
      }
      RegistryStringValue = 0;
    }
    else
    {
      if ( Type != 4
        || cbData != 4
        || (v158 = (int)sourceString, (unsigned int)sourceString > 5) && (_DWORD)sourceString != 0x80000000 )
      {
        RegistryStringValue = -2147221165;
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v173 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
          LODWORD(v200) = -2147221165;
          ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
            (unsigned int)L"PreferredServerBitness",
            v174,
            950,
            v175,
            (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
            v173,
            lpSubKey,
            L"PreferredServerBitness",
            v200);
        }
        return RegistryStringValue;
      }
      if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      {
        LODWORD(lpcbDataa) = v158;
        ComTraceMessageT<int>(
          (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
          (unsigned int)"CComProcessInfo::FinalConstruct",
          942,
          v159,
          (__int64)L"Found PreferredServerBitness: %#x",
          lpcbDataa);
        v158 = (int)sourceString;
      }
      *((_DWORD *)this + 48) |= 0x20u;
      *((_DWORD *)this + 55) = v158;
    }
  }
  if ( !a17 )
  {
    v161 = lpSubKey;
    goto LABEL_397;
  }
  LODWORD(sourceString) = 0;
  cbData = 4;
  v160 = RegQueryValueExW(v136, L"LoadUserSettings", 0, &Type, (LPBYTE)&sourceString, &cbData);
  if ( v160 )
  {
    if ( v160 == 2 )
    {
      RegistryStringValue = 0;
      v161 = lpSubKey;
LABEL_347:
      if ( UseNewCatalogCacheBehavior() )
      {
        if ( !g_bInSCM )
        {
          *((_QWORD *)this + 34) = RegistrationChangeDetection::GetSequence(v162);
          goto LABEL_397;
        }
        ObjectLibrary::ReferencedPtr<RegistrationChangeDetection::IPerUserCacheInformation>::InternalRelease((char *)this + 264);
        RegistryStringValue = RegistrationChangeDetection::GetPerUserCacheInformation(
                                v211,
                                (CComProcessInfo *)((char *)this + 272),
                                (unsigned __int64 *)this + 33,
                                v163);
        if ( (RegistryStringValue & 0x80000000) != 0 )
          goto LABEL_397;
      }
      if ( !a7 )
        RegistryStringValue = GetKeyRefreshInfo(v136, (CComProcessInfo *)((char *)this + 200));
LABEL_397:
      if ( !a18 )
        return RegistryStringValue;
      LODWORD(sourceString) = -1;
      cbData = 4;
      v185 = RegQueryValueExW(v136, L"ProtectionLevel", 0, &Type, (LPBYTE)&sourceString, &cbData);
      if ( v185 )
      {
        if ( v185 == 2 )
          return 0;
        if ( v185 > 0 )
          RegistryStringValue = (unsigned __int16)v185 | 0x80070000;
        else
          RegistryStringValue = v185;
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
      v186 = (const char *)CGuidStr::CGuidStr((CGuidStr *)v213, a3);
      LODWORD(v200) = RegistryStringValue;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x418,
        (unsigned int)"onecore\\com\\combase\\catalog\\process.cxx",
        (const char *)RegistryStringValue,
        (int)"CLSID:%ws APPID:%ws Value:%ws hr:%#x",
        v186,
        v161,
        L"ProtectionLevel",
        v200);
      return RegistryStringValue;
    }
    if ( v160 > 0 )
      RegistryStringValue = (unsigned __int16)v160 | 0x80070000;
    else
      RegistryStringValue = v160;
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v182 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
      v161 = lpSubKey;
      LODWORD(v200) = RegistryStringValue;
      ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
        (unsigned int)L"LoadUserSettings",
        v183,
        992,
        v184,
        (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
        v182,
        lpSubKey,
        L"LoadUserSettings",
        v200);
LABEL_346:
      if ( (RegistryStringValue & 0x80000000) != 0 )
        goto LABEL_397;
      goto LABEL_347;
    }
LABEL_345:
    v161 = lpSubKey;
    goto LABEL_346;
  }
  if ( Type == 4 && cbData == 4 )
  {
    *((_DWORD *)this + 60) = (_DWORD)sourceString;
    goto LABEL_345;
  }
  RegistryStringValue = -2147221165;
  if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
  {
    v179 = CGuidStr::CGuidStr((CGuidStr *)v213, a3);
    LODWORD(v200) = -2147221165;
    ComTraceMessageT<unsigned short *,unsigned short *,unsigned short const *,long>(
      (unsigned int)L"LoadUserSettings",
      v180,
      981,
      v181,
      (__int64)L"CLSID:%ws APPID:%ws Value:%ws %!HRESULT!",
      v179,
      lpSubKey,
      L"LoadUserSettings",
      v200);
  }
  return RegistryStringValue;
}

```

## disassembly

```asm
0x1800782dc  push    rbp
0x1800782de  push    rbx
0x1800782df  push    rsi
0x1800782e0  push    rdi
0x1800782e1  push    r12
0x1800782e3  push    r13
0x1800782e5  push    r14
0x1800782e7  push    r15
0x1800782e9  lea     rbp, [rsp-218h]
0x1800782f1  sub     rsp, 318h
0x1800782f8  mov     rax, cs:__security_cookie
0x1800782ff  xor     rax, rsp
0x180078302  mov     [rbp+250h+var_50], rax
0x180078309  mov     rax, [rbp+250h+arg_28]
0x180078310  mov     r13, r8
0x180078313  mov     rsi, [rbp+250h+hkey]
0x18007831a  mov     rdi, rcx
0x18007831d  mov     [rbp+250h+var_2B8], rdx
0x180078321  lea     rcx, [rbp+250h+var_250]; void *
0x180078325  xor     r14d, r14d
0x180078328  mov     [rbp+250h+KeyHandle], rsi
0x18007832c  xor     edx, edx; Val
0x18007832e  mov     [rbp+250h+hKey], rax
0x180078332  mov     r8d, 200h; Size
0x180078338  mov     [rsp+350h+cbData], r14d
0x18007833d  mov     [rsp+350h+Type], r14d
0x180078342  mov     r12, r9
0x180078345  mov     [rsp+350h+lpSubKey], r9
0x18007834a  call    memset_0
0x18007834f  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x180078356  lea     r15, [rdi+30h]
0x18007835a  movups  xmm0, xmmword ptr [r13+0]
0x18007835f  mov     eax, [rbp+250h+arg_30]
0x180078365  lea     r8d, [r14+3]
0x180078369  mov     [rbp+250h+var_2C0], r14
0x18007836d  movdqu  xmmword ptr [r15], xmm0
0x180078372  mov     dword ptr [rsp+350h+Data], r14d
0x180078377  mov     [rdi+0D8h], eax
0x18007837d  jz      short loc_1800783BD
0x18007837f  mov     ecx, r8d
0x180078382  call    IsWppLevelEnabled
0x180078387  test    al, al
0x180078389  jz      short loc_1800783BD
0x18007838b  lea     rax, aAppidGuid; "AppID %!GUID!"
0x180078392  mov     [rsp+350h+var_320], r13
0x180078397  mov     [rsp+350h+lpcbData], rax
0x18007839c  lea     rdx, aOnecoreComComb_51; "onecore\\com\\combase\\catalog\\process"...
0x1800783a3  mov     dword ptr [rsp+350h+phkResult], r8d
0x1800783a8  mov     r9d, 88h
0x1800783ae  lea     r8, aCcomprocessinf; "CComProcessInfo::FinalConstruct"
0x1800783b5  or      ecx, 0FFFFFFFFh
0x1800783b8  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800783bd  lea     rax, [rdi+40h]
0x1800783c1  mov     r9d, 2; unsigned int
0x1800783c7  xor     r8d, r8d; lpValue
0x1800783ca  mov     [rsp+350h+phkResult], rax; unsigned __int16 **
0x1800783cf  xor     edx, edx; lpSubKey
0x1800783d1  mov     rcx, rsi; hkey
0x1800783d4  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x1800783d9  mov     ebx, eax
0x1800783db  mov     eax, 80000000h
0x1800783e0  lea     ecx, [rbx+rax]
0x1800783e3  test    eax, ecx
0x1800783e5  jnz     short loc_18007845A
0x1800783e7  cmp     ebx, 80070002h
0x1800783ed  jz      short loc_18007845A
0x1800783ef  mov     ecx, cs:dword_1801574B8
0x1800783f5  test    ecx, ecx
0x1800783f7  jnz     short loc_180078413
0x1800783f9  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x180078400  jz      loc_18007A25E
0x180078406  call    IsWppLevelEnabled
0x18007840b  test    al, al
0x18007840d  jz      loc_18007A25E
0x180078413  mov     rdx, r13; struct _GUID *
0x180078416  lea     rcx, [rbp+250h+var_2A0]; this
0x18007841a  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x18007841f  mov     dword ptr [rsp+350h+var_318], ebx
0x180078423  lea     rdx, aCcomprocessinf; "CComProcessInfo::FinalConstruct"
0x18007842a  mov     [rsp+350h+var_320], r12
0x18007842f  lea     rcx, aOnecoreComComb_51; "onecore\\com\\combase\\catalog\\process"...
0x180078436  mov     [rsp+350h+lpcbData], rax
0x18007843b  xor     r9d, r9d
0x18007843e  lea     rax, aClsidWsAppidWs_1; "CLSID:%ws APPID:%ws %!HRESULT!"
0x180078445  mov     r8d, 92h
0x18007844b  mov     [rsp+350h+phkResult], rax
0x180078450  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x180078455  jmp     loc_18007A25E
0x18007845a  lea     r14, [rdi+50h]
0x18007845e  mov     r9d, 2; unsigned int
0x180078464  lea     r8, ?LocalService@Constants@Catalog@Com@@3QBGB; "LocalService"
0x18007846b  mov     [rsp+350h+phkResult], r14; unsigned __int16 **
0x180078470  xor     edx, edx; lpSubKey
0x180078472  mov     rcx, rsi; hkey
0x180078475  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x18007847a  mov     ecx, 80000000h
0x18007847f  mov     ebx, eax
0x180078481  add     eax, ecx
0x180078483  test    ecx, eax
0x180078485  jnz     short loc_1800784D6
0x180078487  cmp     ebx, 80070002h
0x18007848d  jz      short loc_1800784D6
0x18007848f  mov     eax, cs:dword_1801574B8
0x180078495  xor     r8d, r8d
0x180078498  test    eax, eax
0x18007849a  jnz     short loc_1800784B8
0x18007849c  cmp     cs:?gfEnableTracing@@3HA, r8d; int gfEnableTracing
0x1800784a3  jz      loc_18007A25E
0x1800784a9  xor     ecx, ecx
0x1800784ab  call    IsWppLevelEnabled
0x1800784b0  test    al, al
0x1800784b2  jz      loc_18007A25E
0x1800784b8  mov     rdx, r13; struct _GUID *
0x1800784bb  lea     rcx, [rbp+250h+var_2A0]; this
0x1800784bf  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800784c4  lea     rcx, ?LocalService@Constants@Catalog@Com@@3QBGB; "LocalService"
0x1800784cb  mov     r8d, 0A2h
0x1800784d1  jmp     loc_18007A23A
0x1800784d6  mov     sil, [rbp+250h+arg_90]
0x1800784dd  xor     r9d, r9d
0x1800784e0  test    sil, sil
0x1800784e3  jz      loc_180078572
0x1800784e9  mov     rax, [rbp+250h+var_2B8]
0x1800784ed  lea     rcx, [rsp+350h+sourceString]
0x1800784f2  xor     edx, edx
0x1800784f4  mov     [rsp+350h+sourceString], r9
0x1800784f9  mov     rax, [rax]
0x1800784fc  mov     rbx, [rax+50h]
0x180078500  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?PrivMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180078505  mov     rcx, [rbp+250h+var_2B8]
0x180078509  lea     rdx, [rsp+350h+sourceString]
0x18007850e  mov     rax, rbx
0x180078511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078516  mov     ebx, eax
0x180078518  test    eax, eax
0x18007851a  jns     short loc_18007852B
0x18007851c  lea     rcx, [rsp+350h+sourceString]
0x180078521  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@PEAVCClientOxid@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(void)
0x180078526  jmp     loc_18007A25E
0x18007852b  lea     rbx, [rdi+100h]
0x180078532  xor     edx, edx
0x180078534  mov     rcx, rbx
0x180078537  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18007853c  mov     rcx, [rsp+350h+sourceString]; sourceString
0x180078541  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180078545  xor     eax, eax
0x180078547  inc     rdx; length
0x18007854a  cmp     [rcx+rdx*2], ax
0x18007854e  jnz     short loc_180078547
0x180078550  mov     r8, rbx; string
0x180078553  call    cs:__imp_WindowsCreateString
0x18007855a  nop     dword ptr [rax+rax+00h]
0x18007855f  lea     rcx, [rsp+350h+sourceString]
0x180078564  mov     ebx, eax
0x180078566  test    eax, eax
0x180078568  js      short loc_180078521
0x18007856a  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@PEAVCClientOxid@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(void)
0x18007856f  xor     r9d, r9d
0x180078572  mov     r8, [r14]; lpMem
0x180078575  lea     rax, ?g_wszEmptyString@@3QBGB; ushort const near * const g_wszEmptyString
0x18007857c  test    r8, r8
0x18007857f  jz      loc_180078A36
0x180078585  cmp     [r8], r9w
0x180078589  jz      loc_180078A1C
0x18007858f  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x180078596  jz      short loc_1800785D7
0x180078598  mov     r10d, 3
0x18007859e  mov     ecx, r10d
0x1800785a1  call    IsWppLevelEnabled
0x1800785a6  test    al, al
0x1800785a8  jz      short loc_1800785D7
0x1800785aa  mov     [rsp+350h+lpcbData], r8
0x1800785af  lea     rax, aFoundLocalServ; "Found local service! (%ws)"
0x1800785b6  mov     r8d, 0B9h
0x1800785bc  mov     [rsp+350h+phkResult], rax
0x1800785c1  mov     r9d, r10d
0x1800785c4  lea     rdx, aCcomprocessinf; "CComProcessInfo::FinalConstruct"
0x1800785cb  lea     rcx, aOnecoreComComb_51; "onecore\\com\\combase\\catalog\\process"...
0x1800785d2  call    ??$ComTraceMessageT@PEBG@@YAXPEBD0HW4TraceLevel@@PEBG2@Z; ComTraceMessageT<ushort const *>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *)
0x1800785d7  mov     rcx, [rbp+250h+KeyHandle]; hkey
0x1800785db  lea     rax, [rdi+58h]
0x1800785df  mov     r9d, 2; unsigned int
0x1800785e5  mov     [rsp+350h+phkResult], rax; int
0x1800785ea  lea     r8, ?ServiceParameters@Constants@Catalog@Com@@3QBGB; "ServiceParameters"
0x1800785f1  mov     dword ptr [rdi+48h], 1
0x1800785f8  xor     edx, edx; lpSubKey
0x1800785fa  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x1800785ff  mov     ecx, 80000000h
0x180078604  mov     ebx, eax
0x180078606  add     eax, ecx
0x180078608  test    ecx, eax
0x18007860a  jnz     short loc_18007865B
0x18007860c  cmp     ebx, 80070002h
0x180078612  jz      short loc_18007865B
0x180078614  mov     eax, cs:dword_1801574B8
0x18007861a  xor     r8d, r8d
0x18007861d  test    eax, eax
0x18007861f  jnz     short loc_18007863D
0x180078621  cmp     cs:?gfEnableTracing@@3HA, r8d; int gfEnableTracing
0x180078628  jz      loc_18007A25E
0x18007862e  xor     ecx, ecx
0x180078630  call    IsWppLevelEnabled
0x180078635  test    al, al
0x180078637  jz      loc_18007A25E
0x18007863d  mov     rdx, r13; struct _GUID *
0x180078640  lea     rcx, [rbp+250h+var_2A0]; this
0x180078644  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x180078649  lea     rcx, ?ServiceParameters@Constants@Catalog@Com@@3QBGB; "ServiceParameters"
0x180078650  mov     r8d, 0C1h
0x180078656  jmp     loc_18007A23A
0x18007865b  mov     rcx, [r14]; unsigned __int16 *
0x18007865e  lea     r8, [rsp+350h+var_2D8]; bool *
0x180078663  xor     eax, eax
0x180078665  lea     rdx, [rsp+350h+var_2D7]; bool *
0x18007866a  mov     [rsp+350h+var_2D7], al
0x18007866e  mov     [rsp+350h+var_2D8], al
0x180078672  call    ?IsUserOrPackagedService@@YAJPEBGPEA_N1@Z; IsUserOrPackagedService(ushort const *,bool *,bool *)
0x180078677  mov     ebx, eax
0x180078679  test    eax, eax
0x18007867b  jns     loc_18007875E
0x180078681  mov     rcx, [rbp+258h]; this
0x180078688  lea     r8, aOnecoreComComb_51; "onecore\\com\\combase\\catalog\\process"...
0x18007868f  mov     r9d, eax; char *
0x180078692  mov     edx, 0C8h; void *
0x180078697  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007869c  cmp     ebx, 80070424h
0x1800786a2  jnz     loc_18007A25E
0x1800786a8  xor     r15d, r15d
0x1800786ab  mov     rcx, [rbp+250h+KeyHandle]; HKEY
0x1800786af  lea     r9, [rbp+250h+var_250]; unsigned __int16 *
0x1800786b3  mov     r14d, 100h
0x1800786b9  mov     dword ptr [rdi+70h], 2
0x1800786c0  lea     r8, ?RunAs@Constants@Catalog@Com@@3QBGB; "RunAs"
0x1800786c7  mov     dword ptr [rsp+350h+phkResult], r14d; unsigned int
0x1800786cc  call    ?ReadRegistryStringValue@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; ReadRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x1800786d1  mov     ebx, eax
0x1800786d3  test    eax, eax
0x1800786d5  js      loc_180078E04
0x1800786db  cmp     [rbp+250h+var_250], r15w
0x1800786e0  jz      loc_180078E04
0x1800786e6  lea     rdx, ?Interactive_User@Constants@Catalog@Com@@3QBGB; "Interactive User"
0x1800786ed  lea     rcx, [rbp+250h+var_250]
0x1800786f1  call    cs:__imp__o__wcsicmp
0x1800786f8  nop     dword ptr [rax+rax+00h]
0x1800786fd  test    eax, eax
0x1800786ff  jnz     loc_180078CD1
0x180078705  cmp     [rbp+250h+arg_38], r15b
0x18007870c  jz      loc_180078C84
0x180078712  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180078719  jz      loc_180078E04
0x18007871f  lea     esi, [rax+3]
0x180078722  mov     ecx, esi
0x180078724  call    IsWppLevelEnabled
0x180078729  test    al, al
0x18007872b  jz      loc_180078E04
0x180078731  lea     rax, aIgnoringRunasI; "Ignoring RunAs: Interactive User"
0x180078738  mov     r9d, esi
0x18007873b  mov     r8d, 197h
0x180078741  mov     [rsp+350h+phkResult], rax
0x180078746  lea     rdx, aCcomprocessinf; "CComProcessInfo::FinalConstruct"
0x18007874d  lea     rcx, aOnecoreComComb_51; "onecore\\com\\combase\\catalog\\process"...
0x180078754  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x180078759  jmp     loc_180078E04
0x18007875e  xor     ebx, ebx
0x180078760  cmp     [rsp+350h+var_2D7], bl
0x180078764  jz      short loc_18007876D
0x180078766  or      dword ptr [rdi+0C0h], 40h
0x18007876d  test    sil, sil
0x180078770  jz      loc_1800788E0
0x180078776  xor     r15d, r15d
0x180078779  cmp     [rsp+350h+var_2D8], r15b
0x18007877e  jnz     short loc_1800787D5
0x180078780  mov     eax, cs:dword_1801574B8
0x180078786  mov     ebx, 80040157h
0x18007878b  test    eax, eax
0x18007878d  jnz     short loc_1800787AB
0x18007878f  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180078796  jz      loc_18007A25E
0x18007879c  xor     ecx, ecx
0x18007879e  call    IsWppLevelEnabled
0x1800787a3  test    al, al
0x1800787a5  jz      loc_18007A25E
0x1800787ab  mov     rdx, r13; struct _GUID *
0x1800787ae  lea     rcx, [rbp+250h+var_2A0]; this
0x1800787b2  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800787b7  mov     [rsp+350h+var_308], sil
0x1800787bc  mov     byte ptr [rsp+350h+var_310], r15b
0x1800787c1  mov     [rsp+350h+var_320], r12
0x1800787c6  mov     [rsp+350h+lpcbData], rax
0x1800787cb  call    ??$ComTraceMessageT@PEAGPEAGPEBG_N_NJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG32_N4J@Z; ComTraceMessageT<ushort *,ushort *,ushort const *,bool,bool,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,ushort const *,bool,bool,long)
0x1800787d0  jmp     loc_18007A25E
0x1800787d5  mov     rcx, [r14]; unsigned __int16 *
0x1800787d8  lea     rdx, [rsp+350h+sourceString]; unsigned __int16 **
0x1800787dd  mov     [rsp+350h+sourceString], r15
0x1800787e2  call    ?GetServicePackageNameFromScmRegistration@CComProcessInfo@@CAJPEBGPEAPEAG@Z; CComProcessInfo::GetServicePackageNameFromScmRegistration(ushort const *,ushort * *)
0x1800787e7  mov     rsi, [rsp+350h+sourceString]
0x1800787ec  test    eax, eax
0x1800787ee  js      short loc_18007884A
0x1800787f0  mov     rcx, [rdi+100h]; string
0x1800787f7  xor     edx, edx; length
  ... truncated ...
```
