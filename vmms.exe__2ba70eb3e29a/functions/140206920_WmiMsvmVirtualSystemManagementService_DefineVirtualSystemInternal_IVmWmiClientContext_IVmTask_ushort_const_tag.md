# WmiMsvmVirtualSystemManagementService::DefineVirtualSystemInternal(IVmWmiClientContext *,IVmTask *,ushort const *,tagSAFEARRAY *,ushort const *,int)

- ea: `0x140206920`
- end: `0x140207c09`
- name: `?DefineVirtualSystemInternal@WmiMsvmVirtualSystemManagementService@@AEAAPEAUIVmmsVirtualMachine@@PEAUIVmWmiClientContext@@PEAUIVmTask@@PEBGPEAUtagSAFEARRAY@@2H@Z`
- size: `4841`
- prototype: `struct IVmmsVirtualMachine *(WmiMsvmVirtualSystemManagementService *__hidden this, struct IVmWmiClientContext *, struct IVmTask *, const unsigned __int16 *, struct tagSAFEARRAY *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `50`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1407f7cd4`
- `0x1407f7f64`

## callees

- `0x14001a000`
- `0x14001a024`
- `0x140022640`
- `0x140024af4`
- `0x14003280c`
- `0x1400342a0`
- `0x140034404`
- `0x14004aeac`
- `0x14004d0e8`
- `0x14004fd60`
- `0x14005c630`
- `0x14005df58`
- `0x14005eee4`
- `0x14007b500`
- `0x14007d478`
- `0x14007ee00`
- `0x14007ee50`
- `0x14007ee88`
- `0x14007eed8`
- `0x1400826e0`
- `0x140084120`
- `0x140084480`
- `0x140089c30`
- `0x1400924c8`
- `0x14009acc0`
- `0x1400aa5f0`
- `0x1400b2bdc`
- `0x1400bf3cc`
- `0x1400bf564`
- `0x1400bff44`
- `0x1400bff9c`
- `0x1400e1338`
- `0x1400f3a90`
- `0x14012e8e8`
- `0x140188e18`
- `0x140206920`
- `0x140207c10`
- `0x1402085a8`
- `0x14020869c`
- `0x14021b2d8`
- `0x1403a2278`
- `0x1403ef91c`
- `0x1403ef94c`
- `0x140406d94`
- `0x1404828e0`
- `0x1404a1074`
- `0x14065c5e8`
- `0x1407f567c`
- `0x1407f991c`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140206b2c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140206de6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1402070a3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140206b2c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140206de6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1402070a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140207b5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140207b5e`
- `OLEAUT32!__imp_SysStringLen` at `0x140206cbb`
- `OLEAUT32!__imp_SysStringLen` at `0x140206dcb`
- `OLEAUT32!__imp_SysStringLen` at `0x140206cbb`
- `OLEAUT32!__imp_SysStringLen` at `0x140206dcb`

## string_xrefs

- `0x140206c15`: `ConfigurationDataRoot`
- `0x14020794a`: `/configuration/global_settings/power/host_shutdown/action`
- `0x140206a3b`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x140206aca`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x140206b86`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x140206ca5`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x140207086`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x140207106`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x1402071ea`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x1402072d9`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x140207308`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x140207337`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x1402073d0`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x140207418`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x140207477`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x1402074ba`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x14020750a`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x140207759`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x14020777f`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x1402077f8`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x140207832`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x140207930`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x14020796f`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x14020799e`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x140207b25`: `onecore\vm\vmms\wmi\wmimsvmvirtualsystemmanagementservice.cpp`
- `0x140207ae2`: `Completed WmiMsvmVirtualSystemManagementService::DefineVirtualSystemInternal`
- `0x140206b54`: `WmiMsvmVirtualSystemManagementService::DefineVirtualSystemInternal`
- `0x1402070d4`: `WmiMsvmVirtualSystemManagementService::DefineVirtualSystemInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
struct IVmmsVirtualMachine *__fastcall WmiMsvmVirtualSystemManagementService::DefineVirtualSystemInternal(
        WmiMsvmVirtualSystemManagementService *this,
        struct IVmWmiClientContext *a2,
        struct IVmTask *a3,
        Vml *a4,
        struct tagSAFEARRAY *a5,
        const unsigned __int16 *a6,
        int a7)
{
  struct IVmTask *v8; // rsi
  struct tagSAFEARRAY *v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  struct IVmWmiClientContext *v13; // rdx
  bool v14; // cl
  VmWmiMethodException *v15; // rax
  int v16; // eax
  VmWmiMethodException *v17; // rax
  unsigned int ElementCount; // esi
  VARIANTARG *PropertyValue; // rax
  VARIANTARG *v20; // rax
  __int64 v21; // rax
  __int64 v22; // rsi
  struct IVmWmiClientContext *v23; // rax
  VARIANTARG *v24; // rax
  VARIANTARG *v25; // rax
  __int64 v26; // rax
  __int64 v27; // rsi
  __int64 v28; // rax
  unsigned __int16 *v29; // rsi
  __int64 v30; // rax
  _QWORD *v31; // r8
  _QWORD *v32; // rax
  WmiMsvmVirtualSystemManagementService *v33; // rax
  VmWmiMethodException *v34; // rax
  VmWmiMethodException *v35; // rax
  _QWORD *v36; // r8
  _QWORD *v37; // rax
  WmiMsvmVirtualSystemManagementService *v38; // rax
  VmWmiMethodException *v39; // rax
  _WORD *v40; // rax
  _WORD *v41; // rax
  VmWmiMethodException *v42; // rax
  VmWmiMethodException *v43; // rax
  VmWmiMethodException *v44; // rax
  VmWmiMethodException *v45; // rax
  VmWmiMethodException *v46; // rax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  struct IVmTask *v50; // rsi
  _QWORD *v51; // r14
  char *v52; // rcx
  char *v53; // rcx
  __int64 v54; // r13
  unsigned int v55; // r13d
  char *v56; // rcx
  __int64 v57; // rax
  unsigned __int16 **v58; // rbx
  __int64 v59; // rax
  const struct tagSAFEARRAY *v60; // rax
  unsigned int v61; // edi
  struct tagSAFEARRAY *v62; // r14
  __int64 i; // rbx
  struct IVmmsVirtualMachineObject *v64; // r8
  int v65; // eax
  __int64 v66; // rbx
  __int64 (__fastcall *v67)(__int64, __int64, __int64); // rdi
  char *v68; // rcx
  __int64 v69; // rax
  __int64 v70; // rdi
  int v71; // eax
  char *v72; // rcx
  const struct type_info *v73; // rdx
  __int64 v74; // rcx
  WmiMsvmVirtualSystemManagementService *v75; // rbx
  __int64 v76; // rcx
  int v77; // eax
  int v78; // eax
  __int64 v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rcx
  int v82; // r12d
  __int64 v83; // rcx
  int v84; // esi
  int v85; // r14d
  __int64 v86; // rcx
  int v87; // r15d
  unsigned int v88; // ebx
  __int64 v89; // rcx
  VirtualMachineTelemetry *v90; // rax
  __int64 v91; // rcx
  int v92; // eax
  struct IVmTask *v94; // rbx
  wil *v95; // rcx
  __int64 v96; // r8
  char *v97; // rcx
  unsigned __int16 **v98; // [rsp+20h] [rbp-318h]
  int v99; // [rsp+20h] [rbp-318h]
  int v100; // [rsp+20h] [rbp-318h]
  const struct tagVARIANT *v101; // [rsp+28h] [rbp-310h]
  int v102; // [rsp+30h] [rbp-308h]
  unsigned int v103; // [rsp+48h] [rbp-2F0h]
  WmiMsvmVirtualSystemManagementService *v104; // [rsp+50h] [rbp-2E8h] BYREF
  WmiMsvmVirtualSystemManagementService *v105; // [rsp+58h] [rbp-2E0h]
  struct IVmTask *v106; // [rsp+60h] [rbp-2D8h] BYREF
  struct tagSAFEARRAY *v107; // [rsp+68h] [rbp-2D0h] BYREF
  __int64 v108; // [rsp+70h] [rbp-2C8h] BYREF
  __int64 v109; // [rsp+78h] [rbp-2C0h] BYREF
  struct IVersionManager *v110; // [rsp+80h] [rbp-2B8h] BYREF
  unsigned __int16 v111[4]; // [rsp+88h] [rbp-2B0h] BYREF
  _DWORD v112[2]; // [rsp+90h] [rbp-2A8h] BYREF
  char *v113; // [rsp+98h] [rbp-2A0h]
  __int64 v114; // [rsp+A0h] [rbp-298h]
  __int64 v115; // [rsp+A8h] [rbp-290h] BYREF
  struct tagSAFEARRAY *v116; // [rsp+B0h] [rbp-288h] BYREF
  struct IVmTask *v117; // [rsp+B8h] [rbp-280h]
  _BYTE v118[208]; // [rsp+C0h] [rbp-278h] BYREF
  struct IVmWmiClientContext *v119[2]; // [rsp+190h] [rbp-1A8h] BYREF
  int v120; // [rsp+1A0h] [rbp-198h] BYREF
  unsigned int v121; // [rsp+1A4h] [rbp-194h] BYREF
  __int64 v122; // [rsp+1A8h] [rbp-190h] BYREF
  char *v123[2]; // [rsp+1B0h] [rbp-188h] BYREF
  __int64 v124; // [rsp+1C0h] [rbp-178h] BYREF
  _QWORD v125[3]; // [rsp+1C8h] [rbp-170h] BYREF
  unsigned __int64 v126; // [rsp+1E0h] [rbp-158h]
  struct _GUID *v127; // [rsp+1E8h] [rbp-150h] BYREF
  bool v128; // [rsp+1F0h] [rbp-148h]
  __int16 v129; // [rsp+1F1h] [rbp-147h]
  char v130; // [rsp+1F3h] [rbp-145h]
  int v131; // [rsp+1F4h] [rbp-144h]
  _OWORD v132[2]; // [rsp+1F8h] [rbp-140h] BYREF
  struct tagSAFEARRAY *v133[2]; // [rsp+218h] [rbp-120h] BYREF
  __int128 v134; // [rsp+228h] [rbp-110h] BYREF
  __int64 v135; // [rsp+238h] [rbp-100h]
  unsigned __int64 v136; // [rsp+240h] [rbp-F8h]
  struct _GUID v137; // [rsp+250h] [rbp-E8h] BYREF
  __int128 v138; // [rsp+260h] [rbp-D8h] BYREF
  WCHAR FileName[8]; // [rsp+270h] [rbp-C8h] BYREF
  __m128i si128; // [rsp+280h] [rbp-B8h]
  LPVOID pv[2]; // [rsp+290h] [rbp-A8h] BYREF
  unsigned __int16 v142[40]; // [rsp+2A0h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+0h]

  v108 = (__int64)a4;
  v8 = a3;
  v106 = a3;
  v104 = this;
  v105 = this;
  v117 = a3;
  v133[0] = a5;
  v109 = 0;
  *(_QWORD *)v111 = 0;
  v107 = 0;
  v10 = 0;
  v116 = 0;
  v11 = 0;
  v115 = 0;
  v137 = 0;
  Vml::VmGuid::Create((Vml::VmGuid *)&v137);
  v12 = Vml::GuidToString(FileName, &v137, 0);
  if ( *(_QWORD *)(v12 + 24) > 7u )
    v12 = *(_QWORD *)v12;
  v110 = (struct IVersionManager *)v12;
  HyperVManagementTrace::DefineVirtualSystem<Vml::VmGuid &,unsigned short const *>(&v137, &v110);
  std::wstring::_Tidy_deallocate(FileName);
  if ( !VmmsAuthorizationUtilities::CheckAccess(a2, v13) )
  {
    v15 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v118, 0x8001u);
    wil::details::ReportFailure_CustomException<VmWmiMethodException>(
      retaddr,
      1833,
      "onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
      v15);
  }
  v127 = (struct _GUID *)0xFFFFFFFFLL;
  v128 = 0;
  v129 = 0;
  v130 = 0;
  v131 = 0;
  v132[0] = 0;
  v132[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v132[0]) = 0;
  v110 = 0;
  v16 = VmmsVmVersionFactory::CreateVersionManagerInstance(v14, &v110);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x734,
      (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
      (const char *)(unsigned int)v16,
      (int)v98);
  HIDWORD(v127) = (*(__int64 (__fastcall **)(struct IVersionManager *))(*(_QWORD *)v110 + 40LL))(v110);
  if ( a4 )
  {
    Vml::VmlWmiParseEmbeddedInstance(a4, v111, (unsigned __int16 **)&v107, &v116, (struct tagSAFEARRAY **)v98);
    if ( (unsigned int)_o__wcsicmp(*(_QWORD *)v111, L"Msvm_VirtualSystemSettingData") )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16481) )
        VmlDebugTrace(
          16481,
          L"%hs got unexpected class : %ws!\n",
          "WmiMsvmVirtualSystemManagementService::DefineVirtualSystemInternal",
          *(_QWORD *)v111);
      v17 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v118, 0x8005u);
      wil::details::ReportFailure_CustomException<VmWmiMethodException>(
        retaddr,
        1859,
        "onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
        v17);
    }
    ElementCount = Vml::VmSafeArray::GetElementCount((Vml::VmSafeArray *)&v107);
    *(_OWORD *)v123 = 0;
    Vml::VmSafeArrayAccessor::VmSafeArrayAccessor((Vml::VmSafeArrayAccessor *)v123, v107);
    v138 = 0;
    v10 = v116;
    Vml::VmSafeArrayAccessor::VmSafeArrayAccessor((Vml::VmSafeArrayAccessor *)&v138, v116);
    v112[1] = 0;
    v112[0] = ElementCount;
    v113 = v123[1];
    v114 = *((_QWORD *)&v138 + 1);
    PropertyValue = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                                    v112,
                                    L"ConfigurationDataRoot");
    if ( PropertyValue )
      WmiMsvmVirtualSystemManagementService::ExpandPathProperty(a2, PropertyValue);
    v20 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                          v112,
                          L"GuestStateDataRoot");
    if ( v20 )
      WmiMsvmVirtualSystemManagementService::ExpandPathProperty(a2, v20);
    v21 = Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v112, L"SourceGuestStateFile");
    v22 = v21;
    if ( v21 && *(_WORD *)v21 > 1u )
    {
      if ( *(_WORD *)v21 != 8 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x763,
          (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
          (const char *)0x80041005LL,
          (int)v98);
      if ( SysStringLen(*(BSTR *)(v21 + 8)) )
      {
        std::wstring::wstring(FileName, *(_QWORD *)(v22 + 8));
        *(_OWORD *)v119 = 0;
        v23 = Vml::VmWmiImpersonator::Impersonate(a2);
        v119[0] = v23;
        if ( v23 )
          (*(void (__fastcall **)(struct IVmWmiClientContext *))(*(_QWORD *)v23 + 8LL))(v23);
        LOBYTE(v119[1]) = 1;
        ExpandUserPath(FileName);
        std::wstring::operator=(v132, FileName);
        LOBYTE(v119[1]) = 0;
        Vml::VmWmiImpersonator::~VmWmiImpersonator((Vml::VmWmiImpersonator *)v119);
        std::wstring::_Tidy_deallocate(FileName);
      }
    }
    v24 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                          v112,
                          L"SnapshotDataRoot");
    if ( v24 )
      WmiMsvmVirtualSystemManagementService::ExpandPathProperty(a2, v24);
    v25 = (VARIANTARG *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                          v112,
                          L"SwapFileDataRoot");
    if ( v25 )
      WmiMsvmVirtualSystemManagementService::ExpandPathProperty(a2, v25);
    v26 = Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v112, L"VirtualSystemSubType");
    v27 = v26;
    if ( v26 && *(_WORD *)v26 == 8 && SysStringLen(*(BSTR *)(v26 + 8)) )
    {
      if ( (unsigned int)_o__wcsicmp(*(_QWORD *)(v27 + 8), L"Microsoft:Hyper-V:SubType:1") )
      {
        if ( (unsigned int)_o__wcsicmp(*(_QWORD *)(v27 + 8), L"Microsoft:Hyper-V:SubType:2") )
        {
          if ( (unsigned int)VmlIsDebugTraceEnabled(16481) )
            VmlDebugTrace(
              16481,
              L"%hs got unexpected VirtualSystemSubType : %ws!\n",
              "WmiMsvmVirtualSystemManagementService::DefineVirtualSystemInternal",
              *(_QWORD *)(v27 + 8));
          v35 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v118, 0x8005u);
          wil::details::ReportFailure_CustomException<VmWmiMethodException>(
            retaddr,
            1940,
            "onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
            v35);
        }
        LODWORD(v127) = 1;
      }
      else
      {
        LODWORD(v127) = 0;
      }
    }
    v28 = Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v112, L"Version");
    v29 = (unsigned __int16 *)v28;
    if ( v28 )
    {
      if ( *(_WORD *)v28 != 8 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16481) )
          VmlDebugTrace(16481, L"Version is not expected type! VARTYPE = %u", *v29);
        v42 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v118, 0x8005u);
        wil::details::ReportFailure_CustomException<VmWmiMethodException>(
          retaddr,
          1955,
          "onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
          v42);
      }
      std::wstring::wstring(v125, *(_QWORD *)(v28 + 8));
      HIDWORD(v127) = VersionStringToVMVersion(v125);
      Vml::VmGuid::ToStringInternal(&v137, v142);
      v142[36] = 0;
      v134 = 0;
      v135 = 0;
      v136 = 7;
      LOWORD(v134) = 0;
      v30 = Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(v112, L"ElementName");
      if ( v30 && *(_WORD *)v30 == 8 )
        std::wstring::assign(&v134, *(_QWORD *)(v30 + 8));
      if ( !v135 )
      {
        *(_OWORD *)FileName = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        FileName[0] = 0;
        Vml::VmModuleString::LoadStringW((Vml::VmModuleString *)FileName, 0xC350u);
        *(_OWORD *)v119 = 0;
        std::wstring::operator std::basic_string_view<unsigned short>(FileName, v119);
        std::wstring::_Assign<unsigned short>(&v134, v119[0], v119[1]);
        std::wstring::_Tidy_deallocate(FileName);
      }
      *(_OWORD *)v119 = 0;
      HviGetHypervisorFeatures(v119);
      if ( ((unsigned __int64)v119[0] & 0x100000000LL) != 0 )
      {
        *(_OWORD *)v119 = 0;
        HviGetHypervisorFeatures(v119);
        if ( ((unsigned __int64)v119[0] & 0x100000000000LL) == 0 && HIDWORD(v127) < 0xC00 )
        {
          if ( (unsigned int)VmlIsDebugTraceEnabled(16481) )
          {
            v31 = v125;
            if ( v126 > 7 )
              v31 = (_QWORD *)v125[0];
            VmlDebugTrace(16481, L"Version is not supported for creation on layered host! Version = %ws", v31);
          }
          v32 = v125;
          if ( v126 > 7 )
            v32 = (_QWORD *)v125[0];
          v108 = (__int64)v32;
          v33 = (WmiMsvmVirtualSystemManagementService *)&v134;
          if ( v136 > 7 )
            v33 = (WmiMsvmVirtualSystemManagementService *)v134;
          v104 = v33;
          VmEventWriteAndReport<unsigned short const *,unsigned short (&)[37],unsigned short const * &>(
            (struct _EVENT_DESCRIPTOR *)&MSVM_VMMS_VM_VERSION_NOT_SUPPORTED_ON_LAYERED_HOST,
            (__int64)&v104,
            v142,
            (__int64)&v108);
          v34 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v118, 0x8002u);
          wil::details::ReportFailure_CustomException<VmWmiMethodException>(
            retaddr,
            1996,
            "onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
            v34);
        }
      }
      if ( !VersionManager::IsFullySupportedVersion((unsigned int *)&v127 + 1) )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16481) )
        {
          v36 = v125;
          if ( v126 > 7 )
            v36 = (_QWORD *)v125[0];
          VmlDebugTrace(16481, L"Version is not fully supported! Version = %ws", v36);
        }
        v37 = v125;
        if ( v126 > 7 )
          v37 = (_QWORD *)v125[0];
        v108 = (__int64)v37;
        v38 = (WmiMsvmVirtualSystemManagementService *)&v134;
        if ( v136 > 7 )
          v38 = (WmiMsvmVirtualSystemManagementService *)v134;
        v104 = v38;
        VmEventWriteAndReport<unsigned short const *,unsigned short (&)[37],unsigned short const * &>(
          (struct _EVENT_DESCRIPTOR *)&MSVM_VMMS_VM_VERSION_NOT_SUPPORTED,
          (__int64)&v104,
          v142,
          (__int64)&v108);
        v39 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v118, 0x8005u);
        wil::details::ReportFailure_CustomException<VmWmiMethodException>(
          retaddr,
          2019,
          "onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
          v39);
      }
      std::wstring::_Tidy_deallocate(&v134);
      std::wstring::_Tidy_deallocate(v125);
    }
    v40 = (_WORD *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                     v112,
                     L"GuestStateIsolationEnabled");
    if ( v40 )
    {
      if ( *v40 != 11 )
      {
        v43 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v118, 0x8005u);
        wil::details::ReportFailure_CustomException<VmWmiMethodException>(
          retaddr,
          2030,
          "onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
          v43);
      }
      v128 = v40[4] == 0xFFFF;
    }
    v41 = (_WORD *)Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(
                     v112,
                     L"GuestStateIsolationType");
    if ( v41 )
    {
      if ( *v41 != 18 )
      {
        v44 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v118, 0x8005u);
        wil::details::ReportFailure_CustomException<VmWmiMethodException>(
          retaddr,
          2041,
          "onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
          v44);
      }
      v131 = (unsigned __int16)v41[4];
    }
    Vml::VmTypedSafeArrayAccessor<17>::~VmTypedSafeArrayAccessor<17>(&v138);
    Vml::VmTypedSafeArrayAccessor<17>::~VmTypedSafeArrayAccessor<17>(v123);
    v8 = v106;
  }
  if ( a6 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(**((_QWORD **)v104 + 8) + 144LL))(
            *((_QWORD *)v104 + 8),
            a6);
    Vml::VmReferencePtr<VmmsFailoverReplicationManager::FrManagerMigrationEvents,Vml::VmUserReferenceTraits>::Reset(
      &v115,
      0);
    v115 = v11;
    if ( !v11 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16481) )
        VmlDebugTrace(16481, L"SourceSettingData \"%ws\"referenced an invalid virtual machine!\n", a6);
      v45 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v118, 0x8005u);
      wil::details::ReportFailure_CustomException<VmWmiMethodException>(
        retaddr,
        2060,
        "onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
        v45);
    }
    if ( !(*(unsigned int (__fastcall **)(__int64, struct IVmWmiClientContext *))(*(_QWORD *)v11 + 208LL))(v11, a2) )
    {
      v46 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v118, 0x8001u);
      wil::details::ReportFailure_CustomException<VmWmiMethodException>(
        retaddr,
        2065,
        "onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
        v46);
    }
  }
  v124 = 0;
  v122 = 0;
  v47 = (*(__int64 (__fastcall **)(struct IVmTask *, __int64, __int64, __int64 *))(*(_QWORD *)v8 + 312LL))(
          v8,
          1,
          50,
          &v124);
  if ( v47 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x818,
      (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
      (const char *)(unsigned int)v47,
      (int)v98);
  v48 = (*(__int64 (__fastcall **)(struct IVmTask *, __int64, __int64, __int64 *))(*(_QWORD *)v8 + 312LL))(
          v8,
          41,
          50,
          &v122);
  if ( v48 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x819,
      (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
      (const char *)(unsigned int)v48,
      (int)v98);
  *(_OWORD *)pv = 0;
  v49 = (*(__int64 (__fastcall **)(struct IVmWmiClientContext *, LPVOID *))(*(_QWORD *)a2 + 24LL))(a2, pv);
  if ( v49 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x81F,
      (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
      (const char *)(unsigned int)v49,
      (int)v98);
  v106 = 0;
  v99 = v11;
  v50 = (struct IVmTask *)(*(__int64 (__fastcall **)(_QWORD, struct _GUID *, LPVOID, struct _GUID **))(**((_QWORD **)v104 + 8) + 32LL))(
                            *((_QWORD *)v104 + 8),
                            &v137,
                            pv[0],
                            &v127);
  Vml::VmReferencePtr<VmmsFailoverReplicationManager::FrManagerMigrationEvents,Vml::VmUserReferenceTraits>::Reset(
    &v106,
    0);
  v106 = v50;
  try
  {
    v51 = (_QWORD *)((char *)v50 + 8);
    if ( v11 )
    {
      v52 = (char *)v50 + *(int *)(*v51 + 16LL) + 8;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v52 + 504LL))(v52);
      v53 = (char *)v50 + *(int *)(*v51 + 12LL) + 8;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v53 + 808LL))(v53);
    }
    v54 = v108;
    if ( v108 )
    {
      v55 = Vml::VmSafeArray::GetElementCount((Vml::VmSafeArray *)&v107);
      v119[0] = 0;
      v56 = (char *)v50 + *(int *)(*v51 + 12LL) + 8;
      v57 = (*(__int64 (__fastcall **)(char *, __int64))(*(_QWORD *)v56 + 160LL))(v56, 1);
      Vml::VmComPtr<IICShutdown>::Attach<IICShutdown>(v119, v57);
      v58 = *(unsigned __int16 ***)(Vml::VmSafeArrayAccessor::VmSafeArrayAccessor(
                                      (Vml::VmSafeArrayAccessor *)&v138,
                                      v10)
                                  + 8LL);
      v59 = Vml::VmSafeArrayAccessor::VmSafeArrayAccessor((Vml::VmSafeArrayAccessor *)v123, v107);
      Vml::VmlWmiUpdateObjectInstance(a2, v119[0], (struct IVmWmiObject *)v55, *(_QWORD *)(v59 + 8), v58, v101);
      Vml::VmTypedSafeArrayAccessor<17>::~VmTypedSafeArrayAccessor<17>(v123);
      Vml::VmTypedSafeArrayAccessor<17>::~VmTypedSafeArrayAccessor<17>(&v138);
      Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(v119);
      v54 = v108;
    }
    v60 = v133[0];
    if ( v133[0] )
    {
      *(_OWORD *)v133 = 0;
      Vml::VmSafeArrayAccessor::VmSafeArrayAccessor((Vml::VmSafeArrayAccessor *)v133, v60);
      v61 = Vml::VmSafeArrayAccessor::GetElementCount((Vml::VmSafeArrayAccessor *)v133);
      v62 = v133[1];
      for ( i = 0; (unsigned int)i < v61; i = (unsigned int)(i + 1) )
      {
        if ( v50 )
          v64 = (struct IVmTask *)((char *)v50 + *(int *)(*((_QWORD *)v50 + 1) + 12LL) + 8);
        else
          v64 = 0;
        WmiMsvmVirtualSystemManagementService::AddOrModifyOneResourceSetting(
          v104,
          a2,
          v64,
          *((const unsigned __int16 **)&v62->cDims + i));
      }
      Vml::VmTypedSafeArrayAccessor<17>::~VmTypedSafeArrayAccessor<17>(v133);
    }
    if ( a7 )
    {
      (*(void (__fastcall **)(struct IVmTask *, struct IVmWmiClientContext *, __int64, __int64))(*(_QWORD *)v50 + 80LL))(
        v50,
        a2,
        1,
        v122);
      LODWORD(v119[0]) = 0;
      v65 = (*(__int64 (__fastcall **)(__int64, struct IVmWmiClientContext **))(*(_QWORD *)v122 + 48LL))(v122, v119);
      if ( v65 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x85A,
          (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
          (const char *)(unsigned int)v65,
          v99);
      if ( SLODWORD(v119[0]) < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x85B,
          (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
          (const char *)LODWORD(v119[0]),
          v99);
      v66 = *((_QWORD *)v104 + 8);
      v67 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v66 + 152LL);
      v68 = (char *)v50 + *(int *)(*((_QWORD *)v50 + 1) + 12LL) + 8;
      v69 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v68 + 24LL))(v68);
      v70 = v67(v66, v69, 1);
      Vml::VmReferencePtr<IVmmsVirtualMachine,Vml::VmUserReferenceTraits>::Reset(&v109);
      v109 = v70;
      if ( !v70 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x862,
          (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
          (const char *)0x80004005LL,
          v99);
    }
    else
    {
      v71 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v122 + 96LL))(v122, 1, 0);
      if ( v71 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x867,
          (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
          (const char *)(unsigned int)v71,
          v99);
      v72 = (char *)v50 + *(int *)(*((_QWORD *)v50 + 1) + 12LL) + 8;
      (*(void (__fastcall **)(char *, _QWORD, _QWORD))(*(_QWORD *)v72 + 472LL))(v72, 0, 0);
      Vml::VmSharableObject::AddUserInternal(
        (struct IVmTask *)((char *)v50 + *(int *)(*((_QWORD *)v50 + 1) + 4LL) + 8),
        v73);
      v70 = (__int64)v50 + *(int *)(*((_QWORD *)v50 + 1) + 16LL) + 8;
      v109 = v70;
    }
    v104 = 0;
    v74 = v70 + *(int *)(*(_QWORD *)(v70 + 8) + 12LL) + 8LL;
    v75 = (WmiMsvmVirtualSystemManagementService *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v74 + 120LL))(v74);
    Vml::VmReferencePtr<SavedStateRepository,Vml::VmUserReferenceTraits>::Reset(&v104, 0);
    v104 = v75;
    if ( v54 )
    {
      v76 = v70 + *(int *)(*(_QWORD *)(v70 + 8) + 12LL) + 8LL;
      if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v76 + 840LL))(v76, 0, 0, 0) )
      {
        *(_OWORD *)v123 = 0;
        VmRepositoryAutoLock::VmRepositoryAutoLock(v123, v75, 1);
        if ( SLODWORD(v123[1]) < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x87D,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
            (const char *)LODWORD(v123[1]),
            v99);
        v77 = (*(__int64 (__fastcall **)(WmiMsvmVirtualSystemManagementService *, const unsigned __int16 *, __int64))(*(_QWORD *)v75 + 160LL))(
                v75,
                L"/configuration/global_settings/power/host_shutdown/action",
                2);
        if ( v77 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x881,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
            (const char *)(unsigned int)v77,
            v99);
        v78 = (*(__int64 (__fastcall **)(WmiMsvmVirtualSystemManagementService *))(*(_QWORD *)v75 + 56LL))(v75);
        if ( v78 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x883,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
            (const char *)(unsigned int)v78,
            v99);
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v123);
      }
    }
    v121 = 0;
    v79 = v70 + *(int *)(*(_QWORD *)(v70 + 8) + 12LL) + 8LL;
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v79 + 576LL))(v79, &v121);
    v120 = 0;
    v80 = v70 + *(int *)(*(_QWORD *)(v70 + 8) + 12LL) + 8LL;
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v80 + 592LL))(v80, &v120);
    v81 = v70 + *(int *)(*(_QWORD *)(v70 + 8) + 12LL) + 8LL;
    v82 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v81 + 992LL))(v81);
    v83 = v70 + *(int *)(*(_QWORD *)(v70 + 8) + 12LL) + 8LL;
    v84 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v83 + 984LL))(v83);
    v85 = v120;
    v86 = v70 + *(int *)(*(_QWORD *)(v70 + 8) + 12LL) + 8LL;
    v87 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v86 + 96LL))(v86);
    v88 = v121;
    v89 = v70 + *(int *)(*(_QWORD *)(v70 + 8) + 12LL) + 8LL;
    v90 = (VirtualMachineTelemetry *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v89 + 24LL))(v89);
    VirtualMachineTelemetry::TraceVirtualMachineBasicTelemetry(
      v90,
      (const struct _GUID *)(unsigned int)v127,
      HIDWORD(v127),
      v88,
      v87,
      v85,
      v102,
      v84,
      v82,
      v103);
    v91 = v70 + *(int *)(*(_QWORD *)(v70 + 8) + 12LL) + 8LL;
    (*(void (__fastcall **)(__int64, _DWORD *, const wchar_t *))(*(_QWORD *)v91 + 1024LL))(
      v91,
      v112,
      L"Completed WmiMsvmVirtualSystemManagementService::DefineVirtualSystemInternal");
    v92 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v124 + 96LL))(v124, 0, 0);
    if ( v92 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8A1,
        (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmvirtualsystemmanagementservice.cpp",
        (const char *)(unsigned int)v92,
        v100);
  }
  catch ( ... )
  {
    v94 = v106;
    *(_OWORD *)v123 = *(_OWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)((char *)v106
                                                                                + *(int *)(*((_QWORD *)v106 + 1) + 12LL)
                                                                                + 8)
                                                                    + 24LL))((__int64)v106 + *(int *)(*((_QWORD *)v106 + 1) + 12LL)
                                                                                           + 8);
    v96 = (unsigned int)wil::ResultFromCaughtException(v95);
    if ( v94 )
      v97 = (char *)v94 + *(int *)(*((_QWORD *)v94 + 1) + 12LL) + 8;
    else
      v97 = 0;
    CompleteTask<IVmmsVirtualMachineObject *>(v97, v117, v96, 0);
    Vml::VmReferencePtr<VmmsFailoverReplicationManager::FrManagerMigrationEvents,Vml::VmUserReferenceTraits>::Reset(
      &v106,
      0);
    (*(void (__fastcall **)(_QWORD, char **))(**((_QWORD **)v105 + 8) + 128LL))(*((_QWORD *)v105 + 8), v123);
    throw;
  }
  Vml::VmReferencePtr<SnapshotRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<SnapshotRepository,Vml::VmUserReferenceTraits>(&v104);
  v109 = 0;
  Vml::VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>(&v106);
  CoTaskMemFree(pv[0]);
  Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v122);
  Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v124);
  Vml::VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>(&v110);
  std::wstring::_Tidy_deallocate(v132);
  Vml::VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>(&v115);
  Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&v116);
  Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&v107);
  Vml::VmBstr::~VmBstr((Vml::VmBstr *)v111);
  Vml::VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>(&v109);
  return (struct IVmmsVirtualMachine *)v70;
}

```

## disassembly

```asm
0x140206920  push    rbx
0x140206922  push    rsi
0x140206923  push    rdi
0x140206924  push    r12
0x140206926  push    r13
0x140206928  push    r14
0x14020692a  push    r15
0x14020692c  sub     rsp, 300h
0x140206933  mov     rax, cs:__security_cookie
0x14020693a  xor     rax, rsp
0x14020693d  mov     [rsp+338h+var_48], rax
0x140206945  mov     r14, r9
0x140206948  mov     [rsp+338h+var_2C8], r9
0x14020694d  mov     rsi, r8
0x140206950  mov     [rsp+338h+var_2D8], r8
0x140206955  mov     r12, rdx
0x140206958  mov     [rsp+338h+var_2E8], rcx
0x14020695d  mov     [rsp+338h+var_2E0], rcx
0x140206962  mov     [rsp+338h+var_280], r8
0x14020696a  mov     rax, [rsp+338h+arg_20]
0x140206972  mov     [rsp+338h+var_120], rax
0x14020697a  mov     r13, [rsp+338h+arg_28]
0x140206982  xor     r15d, r15d
0x140206985  mov     [rsp+338h+var_2C0], r15
0x14020698a  mov     qword ptr [rsp+338h+var_2B0], r15
0x140206992  mov     [rsp+338h+var_2D0], r15
0x140206997  mov     edi, r15d
0x14020699a  mov     [rsp+338h+var_288], r15
0x1402069a2  mov     ebx, r15d
0x1402069a5  mov     [rsp+338h+var_290], rbx
0x1402069ad  xorps   xmm0, xmm0
0x1402069b0  movdqa  xmmword ptr [rsp+338h+var_E8.Data1], xmm0
0x1402069b9  lea     rcx, [rsp+338h+var_E8]; this
0x1402069c1  call    ?Create@VmGuid@Vml@@QEAAXXZ; Vml::VmGuid::Create(void)
0x1402069c6  xor     r8d, r8d
0x1402069c9  lea     rdx, [rsp+338h+var_E8]
0x1402069d1  lea     rcx, [rsp+338h+FileName]
0x1402069d9  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1402069de  cmp     qword ptr [rax+18h], 7
0x1402069e3  jbe     short loc_1402069E8
0x1402069e5  mov     rax, [rax]
0x1402069e8  mov     [rsp+338h+var_2B8], rax
0x1402069f0  lea     rdx, [rsp+338h+var_2B8]
0x1402069f8  lea     rcx, [rsp+338h+var_E8]
0x140206a00  call    ??$DefineVirtualSystem@AEAVVmGuid@Vml@@PEBG@HyperVManagementTrace@@SAXAEAVVmGuid@Vml@@$$QEAPEBG@Z; HyperVManagementTrace::DefineVirtualSystem<Vml::VmGuid &,ushort const *>(Vml::VmGuid &,ushort const * &&)
0x140206a05  lea     rcx, [rsp+338h+FileName]
0x140206a0d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140206a12  mov     rcx, r12; this
0x140206a15  call    ?CheckAccess@VmmsAuthorizationUtilities@@YA_NPEAUIVmWmiClientContext@@@Z; VmmsAuthorizationUtilities::CheckAccess(IVmWmiClientContext *)
0x140206a1a  test    al, al
0x140206a1c  jnz     short loc_140206A4D
0x140206a1e  mov     edx, 8001h; unsigned int
0x140206a23  lea     rcx, [rsp+338h+var_278]; this
0x140206a2b  call    ??0VmWmiMethodException@@QEAA@I@Z; VmWmiMethodException::VmWmiMethodException(uint)
0x140206a30  mov     rcx, [rsp+338h]
0x140206a38  mov     r9, rax
0x140206a3b  lea     r8, aOnecoreVmVmmsW_50; "onecore\\vm\\vmms\\wmi\\wmimsvmvirtuals"...
0x140206a42  mov     edx, 729h
0x140206a47  call    ??$ReportFailure_CustomException@VVmWmiMethodException@@@details@wil@@YAXPEAXIPEBDVVmWmiMethodException@@@Z; wil::details::ReportFailure_CustomException<VmWmiMethodException>(void *,uint,char const *,VmWmiMethodException)
0x140206a4d  mov     dword ptr [rsp+338h+var_150], 0FFFFFFFFh
0x140206a58  mov     dword ptr [rsp+338h+var_150+4], r15d
0x140206a60  mov     [rsp+338h+var_148], r15b
0x140206a68  xor     eax, eax
0x140206a6a  mov     [rsp+338h+var_147], ax
0x140206a72  mov     [rsp+338h+var_145], al
0x140206a79  mov     [rsp+338h+var_144], r15d
0x140206a81  xorps   xmm0, xmm0
0x140206a84  movups  [rsp+338h+var_140], xmm0
0x140206a8c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140206a94  movdqu  [rsp+338h+var_130], xmm1
0x140206a9d  mov     word ptr [rsp+338h+var_140], r15w
0x140206aa6  mov     [rsp+338h+var_2B8], r15
0x140206aae  lea     rdx, [rsp+338h+var_2B8]; struct IVersionManager **
0x140206ab6  call    ?CreateVersionManagerInstance@VmmsVmVersionFactory@@SAJ_NPEAPEAUIVersionManager@@@Z; VmmsVmVersionFactory::CreateVersionManagerInstance(bool,IVersionManager * *)
0x140206abb  mov     rcx, [rsp+338h]; this
0x140206ac3  test    eax, eax
0x140206ac5  jns     short loc_140206ADC
0x140206ac7  mov     r9d, eax; char *
0x140206aca  lea     r8, aOnecoreVmVmmsW_50; "onecore\\vm\\vmms\\wmi\\wmimsvmvirtuals"...
0x140206ad1  mov     edx, 734h; void *
0x140206ad6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140206adc  mov     rcx, [rsp+338h+var_2B8]
0x140206ae4  mov     rax, [rcx]
0x140206ae7  mov     rax, [rax+28h]
0x140206aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140206af0  mov     dword ptr [rsp+338h+var_150+4], eax
0x140206af7  test    r14, r14
0x140206afa  jz      loc_140207349
0x140206b00  lea     r9, [rsp+338h+var_288]; struct tagSAFEARRAY **
0x140206b08  lea     r8, [rsp+338h+var_2D0]; unsigned __int16 **
0x140206b0d  lea     rdx, [rsp+338h+var_2B0]; unsigned __int16 *
0x140206b15  mov     rcx, r14; this
0x140206b18  call    ?VmlWmiParseEmbeddedInstance@Vml@@YAXPEBGPEAPEAGPEAPEAUtagSAFEARRAY@@2@Z; Vml::VmlWmiParseEmbeddedInstance(ushort const *,ushort * *,tagSAFEARRAY * *,tagSAFEARRAY * *)
0x140206b1d  lea     rdx, ?MsvmVirtualSystemSettingData@@3QBGB; "Msvm_VirtualSystemSettingData"
0x140206b24  mov     rcx, qword ptr [rsp+338h+var_2B0]
0x140206b2c  call    cs:__imp__o__wcsicmp
0x140206b33  nop     dword ptr [rax+rax+00h]
0x140206b38  test    eax, eax
0x140206b3a  jz      short loc_140206B98
0x140206b3c  mov     ebx, 4061h
0x140206b41  mov     ecx, ebx
0x140206b43  call    VmlIsDebugTraceEnabled
0x140206b48  test    eax, eax
0x140206b4a  jz      short loc_140206B69
0x140206b4c  mov     r9, qword ptr [rsp+338h+var_2B0]
0x140206b54  lea     r8, aWmimsvmvirtual_25; "WmiMsvmVirtualSystemManagementService::"...
0x140206b5b  lea     rdx, aHsGotUnexpecte_31; "%hs got unexpected class : %ws!\n"
0x140206b62  mov     ecx, ebx
0x140206b64  call    VmlDebugTrace
0x140206b69  mov     edx, 8005h; unsigned int
0x140206b6e  lea     rcx, [rsp+338h+var_278]; this
0x140206b76  call    ??0VmWmiMethodException@@QEAA@I@Z; VmWmiMethodException::VmWmiMethodException(uint)
0x140206b7b  mov     rcx, [rsp+338h]
0x140206b83  mov     r9, rax
0x140206b86  lea     r8, aOnecoreVmVmmsW_50; "onecore\\vm\\vmms\\wmi\\wmimsvmvirtuals"...
0x140206b8d  mov     edx, 743h
0x140206b92  call    ??$ReportFailure_CustomException@VVmWmiMethodException@@@details@wil@@YAXPEAXIPEBDVVmWmiMethodException@@@Z; wil::details::ReportFailure_CustomException<VmWmiMethodException>(void *,uint,char const *,VmWmiMethodException)
0x140206b98  lea     rcx, [rsp+338h+var_2D0]; this
0x140206b9d  call    ?GetElementCount@VmSafeArray@Vml@@QEBAIXZ; Vml::VmSafeArray::GetElementCount(void)
0x140206ba2  mov     esi, eax
0x140206ba4  xorps   xmm0, xmm0
0x140206ba7  movups  xmmword ptr [rsp+338h+var_188], xmm0
0x140206baf  mov     rdx, [rsp+338h+var_2D0]; struct tagSAFEARRAY *
0x140206bb4  lea     rcx, [rsp+338h+var_188]; this
0x140206bbc  call    ??0VmSafeArrayAccessor@Vml@@QEAA@PEBUtagSAFEARRAY@@@Z; Vml::VmSafeArrayAccessor::VmSafeArrayAccessor(tagSAFEARRAY const *)
0x140206bc1  nop
0x140206bc2  xorps   xmm0, xmm0
0x140206bc5  movups  [rsp+338h+var_D8], xmm0
0x140206bcd  mov     rdi, [rsp+338h+var_288]
0x140206bd5  mov     rdx, rdi; struct tagSAFEARRAY *
0x140206bd8  lea     rcx, [rsp+338h+var_D8]; this
0x140206be0  call    ??0VmSafeArrayAccessor@Vml@@QEAA@PEBUtagSAFEARRAY@@@Z; Vml::VmSafeArrayAccessor::VmSafeArrayAccessor(tagSAFEARRAY const *)
0x140206be5  nop
0x140206be6  mov     [rsp+338h+var_2A4], r15d
0x140206bee  mov     [rsp+338h+var_2A8], esi
0x140206bf5  mov     rax, [rsp+338h+var_188+8]
0x140206bfd  mov     [rsp+338h+var_2A0], rax
0x140206c05  mov     rax, qword ptr [rsp+338h+var_D8+8]
0x140206c0d  mov     [rsp+338h+var_298], rax
0x140206c15  lea     rdx, aConfigurationd; "ConfigurationDataRoot"
0x140206c1c  lea     rcx, [rsp+338h+var_2A8]
0x140206c24  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x140206c29  test    rax, rax
0x140206c2c  jz      short loc_140206C39
0x140206c2e  mov     rdx, rax; pvarg
0x140206c31  mov     rcx, r12; struct IVmWmiClientContext *
0x140206c34  call    ?ExpandPathProperty@WmiMsvmVirtualSystemManagementService@@CAXPEAUIVmWmiClientContext@@PEAVVmVariant@Vml@@@Z; WmiMsvmVirtualSystemManagementService::ExpandPathProperty(IVmWmiClientContext *,Vml::VmVariant *)
0x140206c39  lea     rdx, aGueststatedata; "GuestStateDataRoot"
0x140206c40  lea     rcx, [rsp+338h+var_2A8]
0x140206c48  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x140206c4d  test    rax, rax
0x140206c50  jz      short loc_140206C5D
0x140206c52  mov     rdx, rax; pvarg
0x140206c55  mov     rcx, r12; struct IVmWmiClientContext *
0x140206c58  call    ?ExpandPathProperty@WmiMsvmVirtualSystemManagementService@@CAXPEAUIVmWmiClientContext@@PEAVVmVariant@Vml@@@Z; WmiMsvmVirtualSystemManagementService::ExpandPathProperty(IVmWmiClientContext *,Vml::VmVariant *)
0x140206c5d  lea     rdx, aSourcegueststa; "SourceGuestStateFile"
0x140206c64  lea     rcx, [rsp+338h+var_2A8]
0x140206c6c  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x140206c71  mov     rsi, rax
0x140206c74  mov     r15d, 1
0x140206c7a  lea     r14d, [r15+7]
0x140206c7e  test    rax, rax
0x140206c81  jz      loc_140206D5D
0x140206c87  cmp     r15w, [rax]
0x140206c8b  jnb     loc_140206D5D
0x140206c91  mov     rcx, [rsp+338h]; this
0x140206c99  cmp     r14w, [rax]
0x140206c9d  jz      short loc_140206CB7
0x140206c9f  mov     r9d, 80041005h; char *
0x140206ca5  lea     r8, aOnecoreVmVmmsW_50; "onecore\\vm\\vmms\\wmi\\wmimsvmvirtuals"...
0x140206cac  mov     edx, 763h; void *
0x140206cb1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140206cb7  mov     rcx, [rax+8]; pbstr
0x140206cbb  call    cs:__imp_SysStringLen
0x140206cc2  nop     dword ptr [rax+rax+00h]
0x140206cc7  test    eax, eax
0x140206cc9  jz      loc_140206D5D
0x140206ccf  mov     rdx, [rsi+8]
0x140206cd3  lea     rcx, [rsp+338h+FileName]
0x140206cdb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140206ce0  nop
0x140206ce1  xorps   xmm0, xmm0
0x140206ce4  movups  xmmword ptr [rsp+338h+var_1A8], xmm0
0x140206cec  mov     rcx, r12; struct IVmWmiClientContext *
0x140206cef  call    ?Impersonate@VmWmiImpersonator@Vml@@CAPEAUIVmWmiClientContext@@PEAU3@@Z; Vml::VmWmiImpersonator::Impersonate(IVmWmiClientContext *)
0x140206cf4  mov     rcx, rax
0x140206cf7  mov     [rsp+338h+var_1A8], rax
0x140206cff  test    rax, rax
0x140206d02  jz      short loc_140206D10
0x140206d04  mov     rax, [rax]
0x140206d07  mov     rax, [rax+8]
0x140206d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140206d10  mov     byte ptr [rsp+338h+var_1A8+8], r15b
0x140206d18  lea     rcx, [rsp+338h+FileName]; lpFileName
0x140206d20  call    ?ExpandUserPath@@YA_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ExpandUserPath(std::wstring &)
0x140206d25  lea     rdx, [rsp+338h+FileName]
0x140206d2d  lea     rcx, [rsp+338h+var_140]
0x140206d35  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140206d3a  mov     byte ptr [rsp+338h+var_1A8+8], 0
0x140206d42  lea     rcx, [rsp+338h+var_1A8]; this
0x140206d4a  call    ??1VmWmiImpersonator@Vml@@QEAA@XZ; Vml::VmWmiImpersonator::~VmWmiImpersonator(void)
0x140206d4f  nop
0x140206d50  lea     rcx, [rsp+338h+FileName]
0x140206d58  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140206d5d  lea     rdx, aSnapshotdataro; "SnapshotDataRoot"
0x140206d64  lea     rcx, [rsp+338h+var_2A8]
0x140206d6c  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x140206d71  test    rax, rax
0x140206d74  jz      short loc_140206D81
0x140206d76  mov     rdx, rax; pvarg
0x140206d79  mov     rcx, r12; struct IVmWmiClientContext *
0x140206d7c  call    ?ExpandPathProperty@WmiMsvmVirtualSystemManagementService@@CAXPEAUIVmWmiClientContext@@PEAVVmVariant@Vml@@@Z; WmiMsvmVirtualSystemManagementService::ExpandPathProperty(IVmWmiClientContext *,Vml::VmVariant *)
0x140206d81  lea     rdx, aSwapfiledataro; "SwapFileDataRoot"
0x140206d88  lea     rcx, [rsp+338h+var_2A8]
0x140206d90  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x140206d95  test    rax, rax
0x140206d98  jz      short loc_140206DA5
0x140206d9a  mov     rdx, rax; pvarg
0x140206d9d  mov     rcx, r12; struct IVmWmiClientContext *
0x140206da0  call    ?ExpandPathProperty@WmiMsvmVirtualSystemManagementService@@CAXPEAUIVmWmiClientContext@@PEAVVmVariant@Vml@@@Z; WmiMsvmVirtualSystemManagementService::ExpandPathProperty(IVmWmiClientContext *,Vml::VmVariant *)
0x140206da5  lea     rdx, aVirtualsystems; "VirtualSystemSubType"
0x140206dac  lea     rcx, [rsp+338h+var_2A8]
0x140206db4  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x140206db9  mov     rsi, rax
0x140206dbc  test    rax, rax
0x140206dbf  jz      short loc_140206E01
0x140206dc1  cmp     [rax], r14w
0x140206dc5  jnz     short loc_140206E01
0x140206dc7  mov     rcx, [rax+8]; pbstr
0x140206dcb  call    cs:__imp_SysStringLen
0x140206dd2  nop     dword ptr [rax+rax+00h]
0x140206dd7  test    eax, eax
0x140206dd9  jz      short loc_140206E01
0x140206ddb  lea     rdx, ?MsvmVirtualSystemSubType1@@3QBGB; "Microsoft:Hyper-V:SubType:1"
0x140206de2  mov     rcx, [rsi+8]
0x140206de6  call    cs:__imp__o__wcsicmp
0x140206ded  nop     dword ptr [rax+rax+00h]
0x140206df2  test    eax, eax
0x140206df4  jnz     loc_140207098
0x140206dfa  mov     dword ptr [rsp+338h+var_150], eax
0x140206e01  lea     rdx, aVersion_1; "Version"
0x140206e08  lea     rcx, [rsp+338h+var_2A8]
0x140206e10  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x140206e15  mov     rsi, rax
0x140206e18  test    rax, rax
0x140206e1b  jz      loc_140207217
0x140206e21  cmp     [rax], r14w
0x140206e25  jnz     loc_14020729A
0x140206e2b  mov     rdx, [rax+8]
0x140206e2f  lea     rcx, [rsp+338h+var_170]
0x140206e37  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140206e3c  nop
0x140206e3d  lea     rcx, [rsp+338h+var_170]
0x140206e45  call    ?VersionStringToVMVersion@@YAIAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; VersionStringToVMVersion(std::wstring const &)
0x140206e4a  mov     dword ptr [rsp+338h+var_150+4], eax
0x140206e51  lea     rdx, [rsp+338h+var_98]; unsigned __int16 *
0x140206e59  lea     rcx, [rsp+338h+var_E8]; struct _GUID *
0x140206e61  call    ?ToStringInternal@VmGuid@Vml@@CAXAEBU_GUID@@PEAG@Z; Vml::VmGuid::ToStringInternal(_GUID const &,ushort *)
0x140206e66  xor     eax, eax
0x140206e68  mov     [rsp+338h+var_50], ax
0x140206e70  xorps   xmm0, xmm0
0x140206e73  movups  [rsp+338h+var_110], xmm0
0x140206e7b  mov     [rsp+338h+var_100], rax
0x140206e83  lea     esi, [rax+7]
0x140206e86  mov     [rsp+338h+var_F8], rsi
0x140206e8e  mov     word ptr [rsp+338h+var_110], ax
0x140206e96  lea     rdx, aElementname; "ElementName"
0x140206e9d  lea     rcx, [rsp+338h+var_2A8]
0x140206ea5  call    ?FindPropertyValue@?$VmWmiPropertySearcher_@UtagVARIANT@@VVmVariant@Vml@@@Vml@@QEBAPEAVVmVariant@2@PEBG@Z; Vml::VmWmiPropertySearcher_<tagVARIANT,Vml::VmVariant>::FindPropertyValue(ushort const *)
0x140206eaa  test    rax, rax
0x140206ead  jz      short loc_140206EC6
0x140206eaf  cmp     [rax], r14w
0x140206eb3  jnz     short loc_140206EC6
0x140206eb5  mov     rdx, [rax+8]
0x140206eb9  lea     rcx, [rsp+338h+var_110]
0x140206ec1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x140206ec6  cmp     [rsp+338h+var_100], 0
0x140206ecf  jnz     loc_140206F58
0x140206ed5  xorps   xmm0, xmm0
0x140206ed8  movups  xmmword ptr [rsp+338h+FileName], xmm0
0x140206ee0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140206ee8  movdqu  [rsp+338h+var_B8], xmm1
0x140206ef1  xor     eax, eax
0x140206ef3  mov     [rsp+338h+FileName], ax
0x140206efb  mov     edx, 0C350h; unsigned int
0x140206f00  lea     rcx, [rsp+338h+FileName]; this
0x140206f08  call    ?LoadStringW@VmModuleString@Vml@@QEAAXI@Z; Vml::VmModuleString::LoadStringW(uint)
0x140206f0d  xorps   xmm0, xmm0
0x140206f10  movups  xmmword ptr [rsp+338h+var_1A8], xmm0
0x140206f18  lea     rdx, [rsp+338h+var_1A8]
0x140206f20  lea     rcx, [rsp+338h+FileName]
0x140206f28  call    ??B?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@1@XZ; std::wstring::operator std::basic_string_view<ushort>(void)
0x140206f2d  mov     r8, [rsp+338h+var_1A8+8]
0x140206f35  mov     rdx, [rsp+338h+var_1A8]
0x140206f3d  lea     rcx, [rsp+338h+var_110]
0x140206f45  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x140206f4a  nop
0x140206f4b  lea     rcx, [rsp+338h+FileName]
0x140206f53  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140206f58  xorps   xmm0, xmm0
  ... truncated ...
```
