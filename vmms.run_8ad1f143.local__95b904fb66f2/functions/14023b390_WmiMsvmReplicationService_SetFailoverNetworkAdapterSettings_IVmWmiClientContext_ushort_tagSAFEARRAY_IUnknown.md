# WmiMsvmReplicationService::SetFailoverNetworkAdapterSettings(IVmWmiClientContext *,ushort *,tagSAFEARRAY *,IUnknown * *)

- ea: `0x14023b390`
- end: `0x14023c2bd`
- name: `?SetFailoverNetworkAdapterSettings@WmiMsvmReplicationService@@AEAAIPEAUIVmWmiClientContext@@PEAGPEAUtagSAFEARRAY@@PEAPEAUIUnknown@@@Z`
- size: `3885`
- prototype: `unsigned int(WmiMsvmReplicationService *__hidden this, struct IVmWmiClientContext *, unsigned __int16 *, struct tagSAFEARRAY *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1407350e0`

## callees

- `0x14001a000`
- `0x14001a024`
- `0x140022640`
- `0x140032594`
- `0x14004f830`
- `0x14004fd60`
- `0x14005df58`
- `0x14005eee4`
- `0x14007b380`
- `0x14007eed8`
- `0x140081828`
- `0x1400826e0`
- `0x140084120`
- `0x140084480`
- `0x1400b2bdc`
- `0x1400bff44`
- `0x1400bff9c`
- `0x1400c9360`
- `0x1401341d0`
- `0x14023a9cc`
- `0x14023b390`
- `0x140249bb0`
- `0x1402b2fd4`
- `0x1402b3d10`
- `0x1402c7220`
- `0x1402e0d30`
- `0x1403ef91c`
- `0x1403ef94c`
- `0x1404828e0`
- `0x1404d3c44`
- `0x1404d3ea0`
- `0x14074d7b0`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14023b6f4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14023b7af`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14023b837`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14023b8b9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14023b91e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14023ba0d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14023bafc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14023bbeb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14023b6f4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14023b7af`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14023b837`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14023b8b9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14023b91e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14023ba0d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14023bafc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14023bbeb`
- `OLEAUT32!__imp_VariantClear` at `0x14023c036`
- `OLEAUT32!__imp_VariantClear` at `0x14023c036`

## string_xrefs

- `0x14023b830`: `ProtocolIFType`
- `0x14023b4f5`: `onecore\vm\vmms\wmi\wmimsvmreplicationservice.cpp`
- `0x14023b552`: `onecore\vm\vmms\wmi\wmimsvmreplicationservice.cpp`
- `0x14023b5a5`: `onecore\vm\vmms\wmi\wmimsvmreplicationservice.cpp`
- `0x14023b617`: `onecore\vm\vmms\wmi\wmimsvmreplicationservice.cpp`
- `0x14023b686`: `onecore\vm\vmms\wmi\wmimsvmreplicationservice.cpp`
- `0x14023b721`: `onecore\vm\vmms\wmi\wmimsvmreplicationservice.cpp`
- `0x14023b7f0`: `onecore\vm\vmms\wmi\wmimsvmreplicationservice.cpp`
- `0x14023b874`: `onecore\vm\vmms\wmi\wmimsvmreplicationservice.cpp`
- `0x14023b8f6`: `onecore\vm\vmms\wmi\wmimsvmreplicationservice.cpp`
- `0x14023b963`: `onecore\vm\vmms\wmi\wmimsvmreplicationservice.cpp`
- `0x14023ba52`: `onecore\vm\vmms\wmi\wmimsvmreplicationservice.cpp`
- `0x14023bb41`: `onecore\vm\vmms\wmi\wmimsvmreplicationservice.cpp`
- `0x14023bc30`: `onecore\vm\vmms\wmi\wmimsvmreplicationservice.cpp`
- `0x14023bd6d`: `onecore\vm\vmms\wmi\wmimsvmreplicationservice.cpp`
- `0x14023bf72`: `onecore\vm\vmms\wmi\wmimsvmreplicationservice.cpp`
- `0x14023c0be`: `onecore\vm\vmms\wmi\wmimsvmreplicationservice.cpp`
- `0x14023c0ec`: `onecore\vm\vmms\wmi\wmimsvmreplicationservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 __fastcall WmiMsvmReplicationService::SetFailoverNetworkAdapterSettings(
        WmiMsvmReplicationService *this,
        struct IVmWmiClientContext *a2,
        unsigned __int16 *a3,
        struct tagSAFEARRAY *a4,
        struct IUnknown **a5)
{
  unsigned __int16 *v9; // rbx
  __m128i si128; // xmm6
  int v11; // eax
  VmWmiMethodException *v12; // rax
  _QWORD *v13; // rsi
  VmWmiMethodException *v14; // rax
  char *v15; // rcx
  VmWmiMethodException *v16; // rax
  int v17; // eax
  VmWmiMethodException *v18; // rax
  __int64 v19; // rdi
  unsigned int ElementCount; // eax
  VmWmiMethodException *v21; // rax
  __int64 v22; // r14
  VmWmiMethodException *v23; // rax
  unsigned int v24; // r13d
  _QWORD *v25; // r15
  __int64 v26; // rdi
  unsigned int i; // r12d
  VmWmiMethodException *v28; // rax
  VmWmiMethodException *v29; // rax
  VmWmiMethodException *v30; // rax
  VmWmiMethodException *v31; // rax
  unsigned int n; // r14d
  VmWmiMethodException *v33; // rax
  unsigned int m; // r14d
  VmWmiMethodException *v35; // rax
  unsigned int k; // r14d
  VmWmiMethodException *v37; // rax
  unsigned int j; // r14d
  unsigned int v39; // r15d
  VmWmiMethodException *v40; // rax
  char *v41; // rcx
  _QWORD *v42; // rax
  __int64 v43; // rcx
  __int128 *v44; // rdi
  char *v45; // rcx
  __int64 v46; // rax
  struct IVmWmiObject *WmiInstanceForDeviceComponent; // rax
  VmWmiMethodException *v48; // rax
  struct IVmWmiObject *v49; // r9
  __int128 *v50; // r8
  struct tagSAFEARRAY **p_Src; // rcx
  VmWmiMethodException *v52; // rax
  VmWmiMethodException *v53; // rax
  char *v54; // rcx
  __int64 v55; // rax
  struct IVmWmiClientContext *v56; // r15
  struct IUnknown *v57; // r9
  unsigned int v58; // ebx
  const char *v59; // r9
  __int64 result; // rax
  unsigned int v61; // ebx
  struct IVmmsVirtualMachine *v62; // r8
  int v63; // r9d
  struct IVmmsVirtualMachine *v64; // r8
  struct IVmWmiObject *v65; // [rsp+38h] [rbp-350h]
  struct tagSAFEARRAY **v66; // [rsp+20h] [rbp-368h]
  struct IVmWmiObject *v67; // [rsp+38h] [rbp-350h]
  struct tagSAFEARRAY **v68; // [rsp+20h] [rbp-368h]
  struct IVmWmiObject *v69; // [rsp+38h] [rbp-350h]
  unsigned __int8 v70; // [rsp+50h] [rbp-338h]
  unsigned int v71; // [rsp+60h] [rbp-328h]
  unsigned int v72; // [rsp+60h] [rbp-328h]
  struct IVmWmiClientContext *v73; // [rsp+68h] [rbp-320h] BYREF
  _QWORD *v74; // [rsp+70h] [rbp-318h] BYREF
  struct IVmTask *v75; // [rsp+78h] [rbp-310h] BYREF
  int v76; // [rsp+80h] [rbp-308h]
  int v77; // [rsp+84h] [rbp-304h]
  int v78; // [rsp+88h] [rbp-300h]
  struct tagSAFEARRAY *v79; // [rsp+90h] [rbp-2F8h] BYREF
  unsigned __int16 *v80; // [rsp+98h] [rbp-2F0h] BYREF
  struct tagSAFEARRAY *v81; // [rsp+A0h] [rbp-2E8h] BYREF
  unsigned __int16 v82[4]; // [rsp+A8h] [rbp-2E0h] BYREF
  unsigned __int16 *v83; // [rsp+B0h] [rbp-2D8h] BYREF
  __int64 v84; // [rsp+B8h] [rbp-2D0h] BYREF
  WmiMsvmReplicationService *v85; // [rsp+C0h] [rbp-2C8h]
  struct IUnknown **v86; // [rsp+C8h] [rbp-2C0h]
  struct IVmWmiClientContext *v87; // [rsp+D0h] [rbp-2B8h]
  __int64 v88; // [rsp+D8h] [rbp-2B0h]
  VmWmiMethod *v89; // [rsp+E0h] [rbp-2A8h]
  WmiMsvmReplicationService *v90; // [rsp+E8h] [rbp-2A0h]
  _BYTE v91[208]; // [rsp+F0h] [rbp-298h] BYREF
  const VmWmiMethodException *v92; // [rsp+1C0h] [rbp-1C8h] BYREF
  SAFEARRAY *v93; // [rsp+1C8h] [rbp-1C0h] BYREF
  SAFEARRAY *v94; // [rsp+1D0h] [rbp-1B8h] BYREF
  SAFEARRAY *v95; // [rsp+1D8h] [rbp-1B0h] BYREF
  SAFEARRAY *ppsaOut; // [rsp+1E0h] [rbp-1A8h] BYREF
  void *v97; // [rsp+1E8h] [rbp-1A0h] BYREF
  void *v98; // [rsp+1F0h] [rbp-198h] BYREF
  void *v99; // [rsp+1F8h] [rbp-190h] BYREF
  void *v100; // [rsp+200h] [rbp-188h] BYREF
  unsigned __int16 *v101; // [rsp+208h] [rbp-180h] BYREF
  struct _GUID v102; // [rsp+210h] [rbp-178h] BYREF
  __int128 v103; // [rsp+220h] [rbp-168h] BYREF
  __int128 v104; // [rsp+230h] [rbp-158h] BYREF
  __m128i v105; // [rsp+240h] [rbp-148h]
  __int128 v106; // [rsp+250h] [rbp-138h] BYREF
  __m128i v107; // [rsp+260h] [rbp-128h]
  _OWORD v108[2]; // [rsp+270h] [rbp-118h] BYREF
  __int128 Src; // [rsp+290h] [rbp-F8h] BYREF
  __m128i v110; // [rsp+2A0h] [rbp-E8h]
  __int128 v111; // [rsp+2B0h] [rbp-D8h] BYREF
  __int128 v112; // [rsp+2C0h] [rbp-C8h] BYREF
  __int128 v113; // [rsp+2D0h] [rbp-B8h] BYREF
  __m128i v114; // [rsp+2E0h] [rbp-A8h]
  struct _GUID v115; // [rsp+2F0h] [rbp-98h] BYREF
  __int128 v116; // [rsp+300h] [rbp-88h] BYREF
  __int64 v117; // [rsp+310h] [rbp-78h]
  __int64 v118; // [rsp+318h] [rbp-70h]
  VARIANTARG pvarg; // [rsp+320h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+0h]

  v89 = a2;
  v90 = this;
  v85 = this;
  v87 = a2;
  v86 = a5;
  v74 = 0;
  v73 = 0;
  *(_QWORD *)v82 = 0;
  v79 = 0;
  v81 = 0;
  v9 = 0;
  v80 = 0;
  v116 = 0;
  v117 = 0;
  v118 = 7;
  LOWORD(v116) = 0;
  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v110 = si128;
  LOWORD(Src) = 0;
  v108[0] = 0;
  v108[1] = si128;
  LOWORD(v108[0]) = 0;
  v106 = 0;
  v107 = si128;
  LOWORD(v106) = 0;
  v104 = 0;
  v105 = si128;
  LOWORD(v104) = 0;
  ppsaOut = 0;
  v95 = 0;
  v94 = 0;
  v93 = 0;
  v11 = IsFailoverReplicationSKU();
  try
  {
    if ( !v11 )
    {
      v12 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v91, 0x8002u);
      wil::details::ReportFailure_CustomException<VmWmiMethodException>(
        retaddr,
        3849,
        "onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
        v12);
    }
    v13 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 8) + 224LL))(
                      *((_QWORD *)this + 8),
                      a3);
    Vml::VmReferencePtr<VmmsFailoverReplicationManager::FrManagerMigrationEvents,Vml::VmUserReferenceTraits>::Reset(
      &v74,
      0);
    v74 = v13;
    if ( !v13 )
    {
      v14 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v91, 0x8005u);
      wil::details::ReportFailure_CustomException<VmWmiMethodException>(
        retaddr,
        3861,
        "onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
        v14);
    }
    v15 = (char *)v13 + *(int *)(v13[1] + 12LL) + 8;
    if ( !(*(unsigned int (__fastcall **)(char *, struct IVmWmiClientContext *))(*(_QWORD *)v15 + 208LL))(v15, a2) )
    {
      v16 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v91, 0x8001u);
      wil::details::ReportFailure_CustomException<VmWmiMethodException>(
        retaddr,
        3866,
        "onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
        v16);
    }
    LODWORD(v68) = 0;
    VmWmiExecuteMethodImpl::BeginMethod(a2, 76, &v73, a5);
    v17 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v13 + 208LL))(v13, 0);
    if ( (unsigned int)(v17 - 1) > 1 && v17 != 4 )
    {
      v18 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v91, 0x8007u);
      wil::details::ReportFailure_CustomException<VmWmiMethodException>(
        retaddr,
        3877,
        "onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
        v18);
    }
    v103 = 0;
    Vml::VmSafeArrayAccessor::VmSafeArrayAccessor((Vml::VmSafeArrayAccessor *)&v103, a4);
    v19 = *((_QWORD *)&v103 + 1);
    v88 = *((_QWORD *)&v103 + 1);
    ElementCount = Vml::VmSafeArrayAccessor::GetElementCount((Vml::VmSafeArrayAccessor *)&v103);
    v71 = ElementCount;
    if ( !ElementCount )
    {
      v21 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v91, 0x8005u);
      wil::details::ReportFailure_CustomException<VmWmiMethodException>(
        retaddr,
        3886,
        "onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
        v21);
    }
    v76 = 0;
    v70 = 0;
    v77 = 1;
    v22 = 0;
    while ( 1 )
    {
      v78 = v22;
      if ( (unsigned int)v22 >= ElementCount )
        break;
      Vml::VmlWmiParseEmbeddedInstance(*(Vml **)(v19 + 8 * v22), v82, (unsigned __int16 **)&v79, &v81, v68);
      if ( (unsigned int)_o__wcsicmp(*(_QWORD *)v82, L"Msvm_FailoverNetworkAdapterSettingData") )
      {
        v23 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v91, 0x8005u);
        wil::details::ReportFailure_CustomException<VmWmiMethodException>(
          retaddr,
          3897,
          "onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
          v23);
      }
      v24 = Vml::VmSafeArray::GetElementCount((Vml::VmSafeArray *)&v79);
      v112 = 0;
      Vml::VmSafeArrayAccessor::VmSafeArrayAccessor((Vml::VmSafeArrayAccessor *)&v112, v79);
      v25 = (_QWORD *)*((_QWORD *)&v112 + 1);
      v111 = 0;
      Vml::VmSafeArrayAccessor::VmSafeArrayAccessor((Vml::VmSafeArrayAccessor *)&v111, v81);
      v26 = *((_QWORD *)&v111 + 1);
      for ( i = 0; i < v24; ++i )
      {
        if ( (unsigned int)_o__wcsicmp(L"InstanceID", *v25) )
        {
          if ( (unsigned int)_o__wcsicmp(L"ProtocolIFType", *v25) )
          {
            if ( (unsigned int)_o__wcsicmp(L"DHCPEnabled", *v25) )
            {
              if ( (unsigned int)_o__wcsicmp(L"IPAddresses", *v25) )
              {
                if ( (unsigned int)_o__wcsicmp(L"Subnets", *v25) )
                {
                  if ( (unsigned int)_o__wcsicmp(L"DefaultGateways", *v25) )
                  {
                    if ( !(unsigned int)_o__wcsicmp(L"DNSServers", *v25) && *(_WORD *)v26 > 1u )
                    {
                      if ( *(_WORD *)v26 != 8200 )
                      {
                        v37 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v91, 0x8005u);
                        wil::details::ReportFailure_CustomException<VmWmiMethodException>(
                          retaddr,
                          4036,
                          "onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
                          v37);
                      }
                      Vml::VmSafeArray::Assign(&v93, *(SAFEARRAY **)(v26 + 8));
                      for ( j = 0; j < Vml::VmSafeArray::GetElementCount((Vml::VmSafeArray *)&v93); ++j )
                      {
                        if ( j )
                          std::wstring::append(&v104, (void *)L";");
                        v100 = 0;
                        Vml::VmSafeArray::GetElement((Vml::VmSafeArray *)&v93, j, &v100);
                        std::wstring::append(&v104, v100);
                        Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v100);
                      }
                    }
                  }
                  else if ( *(_WORD *)v26 > 1u )
                  {
                    if ( *(_WORD *)v26 != 8200 )
                    {
                      v35 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v91, 0x8005u);
                      wil::details::ReportFailure_CustomException<VmWmiMethodException>(
                        retaddr,
                        4010,
                        "onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
                        v35);
                    }
                    Vml::VmSafeArray::Assign(&v94, *(SAFEARRAY **)(v26 + 8));
                    for ( k = 0; k < Vml::VmSafeArray::GetElementCount((Vml::VmSafeArray *)&v94); ++k )
                    {
                      if ( k )
                        std::wstring::append(&v106, (void *)L";");
                      v99 = 0;
                      Vml::VmSafeArray::GetElement((Vml::VmSafeArray *)&v94, k, &v99);
                      std::wstring::append(&v106, v99);
                      Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v99);
                    }
                  }
                }
                else if ( *(_WORD *)v26 > 1u )
                {
                  if ( *(_WORD *)v26 != 8200 )
                  {
                    v33 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v91, 0x8005u);
                    wil::details::ReportFailure_CustomException<VmWmiMethodException>(
                      retaddr,
                      3984,
                      "onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
                      v33);
                  }
                  Vml::VmSafeArray::Assign(&v95, *(SAFEARRAY **)(v26 + 8));
                  for ( m = 0; m < Vml::VmSafeArray::GetElementCount((Vml::VmSafeArray *)&v95); ++m )
                  {
                    if ( m )
                      std::wstring::append(v108, (void *)L";");
                    v98 = 0;
                    Vml::VmSafeArray::GetElement((Vml::VmSafeArray *)&v95, m, &v98);
                    std::wstring::append(v108, v98);
                    Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v98);
                  }
                }
              }
              else if ( *(_WORD *)v26 > 1u )
              {
                if ( *(_WORD *)v26 != 8200 )
                {
                  v31 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v91, 0x8005u);
                  wil::details::ReportFailure_CustomException<VmWmiMethodException>(
                    retaddr,
                    3958,
                    "onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
                    v31);
                }
                Vml::VmSafeArray::Assign(&ppsaOut, *(SAFEARRAY **)(v26 + 8));
                for ( n = 0; n < Vml::VmSafeArray::GetElementCount((Vml::VmSafeArray *)&ppsaOut); ++n )
                {
                  if ( n )
                    std::wstring::append(&Src, (void *)L";");
                  v97 = 0;
                  Vml::VmSafeArray::GetElement((Vml::VmSafeArray *)&ppsaOut, n, &v97);
                  std::wstring::append(&Src, v97);
                  Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v97);
                }
              }
            }
            else
            {
              if ( *(_WORD *)v26 > 1u && *(_WORD *)v26 != 11 )
              {
                v30 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v91, 0x8005u);
                wil::details::ReportFailure_CustomException<VmWmiMethodException>(
                  retaddr,
                  3946,
                  "onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
                  v30);
              }
              v77 = *(__int16 *)(v26 + 8);
            }
          }
          else
          {
            if ( *(_WORD *)v26 > 1u && *(_WORD *)v26 != 18 )
            {
              v29 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v91, 0x8005u);
              wil::details::ReportFailure_CustomException<VmWmiMethodException>(
                retaddr,
                3932,
                "onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
                v29);
            }
            v76 = 1;
            v70 = ProtocolIFTypeToAddressFamily(*(_WORD *)(v26 + 8));
          }
        }
        else if ( *(_WORD *)v26 > 1u )
        {
          if ( *(_WORD *)v26 != 8 )
          {
            v28 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v91, 0x8005u);
            wil::details::ReportFailure_CustomException<VmWmiMethodException>(
              retaddr,
              3919,
              "onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
              v28);
          }
          Vml::VmBstr::Assign((Vml::VmBstr *)&v80, *(const unsigned __int16 **)(v26 + 8));
          std::wstring::assign(&v116, *(_QWORD *)(v26 + 8));
          v9 = v80;
        }
        ++v25;
        v26 += 24;
      }
      if ( !v117 || !v76 )
      {
        v53 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v91, 0x8005u);
        wil::details::ReportFailure_CustomException<VmWmiMethodException>(
          retaddr,
          4060,
          "onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
          v53);
      }
      v39 = v77;
      if ( !(unsigned int)ValidateGuestNetworkSettings(
                            (const struct IVmmsVirtualMachineObject *)((char *)v13 + *(int *)(v13[1] + 12LL) + 8),
                            v70,
                            v77,
                            ppsaOut,
                            v95,
                            v94,
                            v93) )
      {
        v40 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v91, 0x8005u);
        wil::details::ReportFailure_CustomException<VmWmiMethodException>(
          retaddr,
          4073,
          "onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
          v40);
      }
      v115 = 0;
      v102 = 0;
      WmiMsvmFailoverNetworkAdapterSettingDataResolver::ParseInstanceId(v9, &v115, &v102);
      v41 = (char *)v13 + *(int *)(v13[1] + 12LL) + 8;
      v42 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v41 + 24LL))(v41);
      v43 = *(_QWORD *)&v115.Data1 - *v42;
      if ( *(_QWORD *)&v115.Data1 == *v42 )
        v43 = *(_QWORD *)v115.Data4 - v42[1];
      if ( v43 )
      {
        v52 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v91, 0x8005u);
        wil::details::ReportFailure_CustomException<VmWmiMethodException>(
          retaddr,
          4097,
          "onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
          v52);
      }
      v113 = 0;
      v114 = si128;
      LOWORD(v113) = 0;
      Vml::VmGuid::ToString(&v102, &v113);
      v75 = 0;
      v44 = &v113;
      if ( v114.m128i_i64[1] > 7uLL )
        v44 = (__int128 *)v113;
      v45 = (char *)v13 + *(int *)(v13[1] + 12LL) + 8;
      v46 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v45 + 32LL))(v45);
      Vml::VmBstr::Format((Vml::VmBstr *)&v75, L"Microsoft:%s\\%s", v46, v44);
      v101 = 0;
      Vml::VmBstr::Assign((Vml::VmBstr *)&v101, L"INSTANCEID");
      Vml::VmVariant::VmVariant((Vml::VmVariant *)&pvarg, (const unsigned __int16 *)v75);
      v84 = 0;
      v83 = 0;
      Vml::VmBstr::Assign((Vml::VmBstr *)&v83, L"Msvm_SyntheticEthernetPortSettingData");
      WmiInstanceForDeviceComponent = GetWmiInstanceForDeviceComponent(
                                        (struct IVmmsVirtualMachineObject *)((char *)v13 + *(int *)(v13[1] + 12LL) + 8),
                                        v83,
                                        &v102,
                                        1u,
                                        &v101,
                                        &pvarg,
                                        1);
      Vml::VmComPtr<IICShutdown>::Attach<IICShutdown>(&v84, WmiInstanceForDeviceComponent);
      Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v83);
      if ( !v84 )
      {
        v48 = VmWmiMethodException::VmWmiMethodException((VmWmiMethodException *)v91, 0x8005u);
        wil::details::ReportFailure_CustomException<VmWmiMethodException>(
          retaddr,
          4126,
          "onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
          v48);
      }
      v49 = (struct IVmWmiObject *)&v104;
      if ( v105.m128i_i64[1] > 7uLL )
        v49 = (struct IVmWmiObject *)v104;
      v50 = &v106;
      if ( v107.m128i_i64[1] > 7uLL )
        v50 = (__int128 *)v106;
      p_Src = (struct tagSAFEARRAY **)&Src;
      if ( v110.m128i_i64[1] > 7uLL )
        p_Src = (struct tagSAFEARRAY **)Src;
      v69 = v49;
      v68 = p_Src;
      LOBYTE(v50) = v70;
      (*(void (__fastcall **)(_QWORD *, struct _GUID *, __int128 *, _QWORD))(*v13 + 808LL))(v13, &v102, v50, v39);
      Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v84);
      VariantClear(&pvarg);
      Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v101);
      Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v75);
      std::wstring::_Tidy_deallocate(&v113);
      Vml::VmTypedSafeArrayAccessor<17>::~VmTypedSafeArrayAccessor<17>(&v111);
      Vml::VmTypedSafeArrayAccessor<17>::~VmTypedSafeArrayAccessor<17>(&v112);
      v22 = (unsigned int)(v78 + 1);
      ElementCount = v71;
      v19 = v88;
    }
    v75 = 0;
    v54 = (char *)v13 + *(int *)(v13[1] + 16LL) + 8;
    v55 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v54 + 64LL))(v54);
    Vml::VmComPtr<IICShutdown>::Attach<IICShutdown>(&v75, v55);
    v56 = v89;
    VmWmiMethod::AddAffectedObjectToTask(v89, v73, v75, v57);
    v58 = VmWmiExecuteMethodImpl::EndMethod(
            (WmiMsvmReplicationService *)((char *)v90 + 56),
            v56,
            (struct IVmmsVirtualMachine *)((char *)v13 + *(int *)(v13[1] + 16LL) + 8),
            v73,
            a5,
            0,
            0,
            v69);
    Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v75);
    Vml::VmTypedSafeArrayAccessor<17>::~VmTypedSafeArrayAccessor<17>(&v103);
    Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&v93);
    Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&v94);
    Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&v95);
    Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&ppsaOut);
    std::wstring::_Tidy_deallocate(&v104);
    std::wstring::_Tidy_deallocate(&v106);
    std::wstring::_Tidy_deallocate(v108);
    std::wstring::_Tidy_deallocate(&Src);
    std::wstring::_Tidy_deallocate(&v116);
    Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v80);
    Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&v81);
    Vml::VmSafeArray::~VmSafeArray((Vml::VmSafeArray *)&v79);
    Vml::VmBstr::~VmBstr((Vml::VmBstr *)v82);
    Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v73);
    Vml::VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>(&v74);
    result = v58;
  }
  catch ( const VmWmiMethodException *v92 )
  {
    v61 = (unsigned __int16)*((_DWORD *)v92 + 8);
    LODWORD(v66) = v61;
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0x1035,
      (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
      "status=%u",
      (const char *)v66);
    if ( v74 )
      v62 = (struct IVmmsVirtualMachine *)((char *)v74 + *(int *)(v74[1] + 16LL) + 8);
    else
      v62 = 0;
    v72 = VmWmiExecuteMethodImpl::EndMethod(
            (WmiMsvmReplicationService *)((char *)v85 + 56),
            v87,
            v62,
            v73,
            v86,
            v61,
            0,
            v67);
    goto LABEL_92;
  }
  catch ( ... )
  {
    v63 = wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x1035,
            (unsigned int)"onecore\\vm\\vmms\\wmi\\wmimsvmreplicationservice.cpp",
            v59);
    if ( v74 )
      v64 = (struct IVmmsVirtualMachine *)((char *)v74 + *(int *)(v74[1] + 16LL) + 8);
    else
      v64 = 0;
    v72 = VmWmiExecuteMethodImpl::EndMethod(
            (WmiMsvmReplicationService *)((char *)v85 + 56),
            v87,
            v64,
            v73,
            v86,
            v63,
            0,
            v65);
LABEL_92:
    Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v73);
    Vml::VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>(&v74);
    return v72;
  }
  return result;
}

```

## disassembly

```asm
0x14023b390  mov     r11, rsp
0x14023b393  push    rbx
0x14023b394  push    rsi
0x14023b395  push    rdi
0x14023b396  push    r12
0x14023b398  push    r13
0x14023b39a  push    r14
0x14023b39c  push    r15
0x14023b39e  sub     rsp, 350h
0x14023b3a5  movaps  xmmword ptr [r11-48h], xmm6
0x14023b3aa  mov     rax, cs:__security_cookie
0x14023b3b1  xor     rax, rsp
0x14023b3b4  mov     [rsp+388h+var_50], rax
0x14023b3bc  mov     r14, r9
0x14023b3bf  mov     rdi, r8
0x14023b3c2  mov     r15, rdx
0x14023b3c5  mov     [rsp+388h+var_2A8], rdx
0x14023b3cd  mov     r13, rcx
0x14023b3d0  mov     [rsp+388h+var_2A0], rcx
0x14023b3d8  mov     [rsp+388h+var_2C8], rcx
0x14023b3e0  mov     [rsp+388h+var_2B8], rdx
0x14023b3e8  mov     r12, [rsp+388h+arg_20]
0x14023b3f0  mov     [rsp+388h+var_330], r12
0x14023b3f5  mov     [rsp+388h+var_2C0], r12
0x14023b3fd  xor     esi, esi
0x14023b3ff  mov     [rsp+388h+var_318], rsi
0x14023b404  mov     [rsp+388h+var_320], rsi
0x14023b409  mov     [r11-2E0h], rsi
0x14023b410  mov     [r11-2F8h], rsi
0x14023b417  mov     [r11-2E8h], rsi
0x14023b41e  mov     ebx, esi
0x14023b420  mov     [rsp+388h+var_2F0], rbx
0x14023b428  xorps   xmm0, xmm0
0x14023b42b  movups  [rsp+388h+var_88], xmm0
0x14023b433  mov     [r11-78h], rsi
0x14023b437  mov     qword ptr [r11-70h], 7
0x14023b43f  mov     word ptr [rsp+388h+var_88], si
0x14023b447  movups  [rsp+388h+Src], xmm0
0x14023b44f  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14023b457  movdqu  [rsp+388h+var_E8], xmm6
0x14023b460  mov     word ptr [rsp+388h+Src], si
0x14023b468  movups  [rsp+388h+var_118], xmm0
0x14023b470  movdqu  [rsp+388h+var_108], xmm6
0x14023b479  mov     word ptr [rsp+388h+var_118], si
0x14023b481  movups  [rsp+388h+var_138], xmm0
0x14023b489  movdqu  [rsp+388h+var_128], xmm6
0x14023b492  mov     word ptr [rsp+388h+var_138], si
0x14023b49a  movups  [rsp+388h+var_158], xmm0
0x14023b4a2  movdqu  [rsp+388h+var_148], xmm6
0x14023b4ab  mov     word ptr [rsp+388h+var_158], si
0x14023b4b3  mov     [r11-1A8h], rsi
0x14023b4ba  mov     [r11-1B0h], rsi
0x14023b4c1  mov     [r11-1B8h], rsi
0x14023b4c8  mov     [r11-1C0h], rsi
0x14023b4cf  call    ?IsFailoverReplicationSKU@@YAHXZ; IsFailoverReplicationSKU(void)
0x14023b4d4  test    eax, eax
0x14023b4d6  jnz     short loc_14023B506
0x14023b4d8  mov     edx, 8002h; unsigned int
0x14023b4dd  lea     rcx, [rsp+388h+var_298]; this
0x14023b4e5  call    ??0VmWmiMethodException@@QEAA@I@Z; VmWmiMethodException::VmWmiMethodException(uint)
0x14023b4ea  mov     rcx, [rsp+388h]
0x14023b4f2  mov     r9, rax
0x14023b4f5  lea     r8, aOnecoreVmVmmsW_160; "onecore\\vm\\vmms\\wmi\\wmimsvmreplicat"...
0x14023b4fc  mov     edx, 0F09h
0x14023b501  call    ??$ReportFailure_CustomException@VVmWmiMethodException@@@details@wil@@YAXPEAXIPEBDVVmWmiMethodException@@@Z; wil::details::ReportFailure_CustomException<VmWmiMethodException>(void *,uint,char const *,VmWmiMethodException)
0x14023b506  mov     rcx, [r13+40h]
0x14023b50a  mov     rax, [rcx]
0x14023b50d  mov     rdx, rdi
0x14023b510  mov     rax, [rax+0E0h]
0x14023b517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14023b51c  mov     rsi, rax
0x14023b51f  xor     edx, edx
0x14023b521  lea     rcx, [rsp+388h+var_318]
0x14023b526  call    ?Reset@?$VmReferencePtr@VFrManagerMigrationEvents@VmmsFailoverReplicationManager@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVFrManagerMigrationEvents@VmmsFailoverReplicationManager@@@Z; Vml::VmReferencePtr<VmmsFailoverReplicationManager::FrManagerMigrationEvents,Vml::VmUserReferenceTraits>::Reset(VmmsFailoverReplicationManager::FrManagerMigrationEvents *)
0x14023b52b  mov     [rsp+388h+var_318], rsi
0x14023b530  test    rsi, rsi
0x14023b533  jnz     short loc_14023B563
0x14023b535  mov     edx, 8005h; unsigned int
0x14023b53a  lea     rcx, [rsp+388h+var_298]; this
0x14023b542  call    ??0VmWmiMethodException@@QEAA@I@Z; VmWmiMethodException::VmWmiMethodException(uint)
0x14023b547  mov     rcx, [rsp+388h]
0x14023b54f  mov     r9, rax
0x14023b552  lea     r8, aOnecoreVmVmmsW_160; "onecore\\vm\\vmms\\wmi\\wmimsvmreplicat"...
0x14023b559  mov     edx, 0F15h
0x14023b55e  call    ??$ReportFailure_CustomException@VVmWmiMethodException@@@details@wil@@YAXPEAXIPEBDVVmWmiMethodException@@@Z; wil::details::ReportFailure_CustomException<VmWmiMethodException>(void *,uint,char const *,VmWmiMethodException)
0x14023b563  mov     rax, [rsi+8]
0x14023b567  movsxd  rcx, dword ptr [rax+0Ch]
0x14023b56b  add     rcx, 8
0x14023b56f  add     rcx, rsi
0x14023b572  mov     rax, [rcx]
0x14023b575  mov     rdx, r15
0x14023b578  mov     rax, [rax+0D0h]
0x14023b57f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14023b584  test    eax, eax
0x14023b586  jnz     short loc_14023B5B6
0x14023b588  mov     edx, 8001h; unsigned int
0x14023b58d  lea     rcx, [rsp+388h+var_298]; this
0x14023b595  call    ??0VmWmiMethodException@@QEAA@I@Z; VmWmiMethodException::VmWmiMethodException(uint)
0x14023b59a  mov     rcx, [rsp+388h]
0x14023b5a2  mov     r9, rax
0x14023b5a5  lea     r8, aOnecoreVmVmmsW_160; "onecore\\vm\\vmms\\wmi\\wmimsvmreplicat"...
0x14023b5ac  mov     edx, 0F1Ah
0x14023b5b1  call    ??$ReportFailure_CustomException@VVmWmiMethodException@@@details@wil@@YAXPEAXIPEBDVVmWmiMethodException@@@Z; wil::details::ReportFailure_CustomException<VmWmiMethodException>(void *,uint,char const *,VmWmiMethodException)
0x14023b5b6  mov     dword ptr [rsp+388h+var_368], 0; struct tagSAFEARRAY **
0x14023b5be  mov     r9, r12
0x14023b5c1  lea     r8, [rsp+388h+var_320]
0x14023b5c6  mov     edx, 4Ch ; 'L'
0x14023b5cb  mov     rcx, r15
0x14023b5ce  call    ?BeginMethod@VmWmiExecuteMethodImpl@@KAXPEAUIVmWmiClientContext@@W4__MIDL___MIDL_itf_vmtskitf_0000_0000_0001@@PEAPEAUIVmTask@@PEAPEAUIUnknown@@I@Z; VmWmiExecuteMethodImpl::BeginMethod(IVmWmiClientContext *,__MIDL___MIDL_itf_vmtskitf_0000_0000_0001,IVmTask * *,IUnknown * *,uint)
0x14023b5d3  mov     rax, [rsi]
0x14023b5d6  xor     edx, edx
0x14023b5d8  mov     rcx, rsi
0x14023b5db  mov     rax, [rax+0D0h]
0x14023b5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14023b5e7  lea     ecx, [rax-1]
0x14023b5ea  mov     r13d, 1
0x14023b5f0  cmp     ecx, r13d
0x14023b5f3  jbe     short loc_14023B628
0x14023b5f5  cmp     eax, 4
0x14023b5f8  jz      short loc_14023B628
0x14023b5fa  mov     edx, 8007h; unsigned int
0x14023b5ff  lea     rcx, [rsp+388h+var_298]; this
0x14023b607  call    ??0VmWmiMethodException@@QEAA@I@Z; VmWmiMethodException::VmWmiMethodException(uint)
0x14023b60c  mov     rcx, [rsp+388h]
0x14023b614  mov     r9, rax
0x14023b617  lea     r8, aOnecoreVmVmmsW_160; "onecore\\vm\\vmms\\wmi\\wmimsvmreplicat"...
0x14023b61e  mov     edx, 0F25h
0x14023b623  call    ??$ReportFailure_CustomException@VVmWmiMethodException@@@details@wil@@YAXPEAXIPEBDVVmWmiMethodException@@@Z; wil::details::ReportFailure_CustomException<VmWmiMethodException>(void *,uint,char const *,VmWmiMethodException)
0x14023b628  xorps   xmm0, xmm0
0x14023b62b  movups  [rsp+388h+var_168], xmm0
0x14023b633  mov     rdx, r14; struct tagSAFEARRAY *
0x14023b636  lea     rcx, [rsp+388h+var_168]; this
0x14023b63e  call    ??0VmSafeArrayAccessor@Vml@@QEAA@PEBUtagSAFEARRAY@@@Z; Vml::VmSafeArrayAccessor::VmSafeArrayAccessor(tagSAFEARRAY const *)
0x14023b643  nop
0x14023b644  mov     rdi, qword ptr [rsp+388h+var_168+8]
0x14023b64c  mov     [rsp+388h+var_2B0], rdi
0x14023b654  lea     rcx, [rsp+388h+var_168]; this
0x14023b65c  call    ?GetElementCount@VmSafeArrayAccessor@Vml@@QEBAIXZ; Vml::VmSafeArrayAccessor::GetElementCount(void)
0x14023b661  mov     [rsp+388h+var_328], eax
0x14023b665  test    eax, eax
0x14023b667  jnz     short loc_14023B697
0x14023b669  mov     edx, 8005h; unsigned int
0x14023b66e  lea     rcx, [rsp+388h+var_298]; this
0x14023b676  call    ??0VmWmiMethodException@@QEAA@I@Z; VmWmiMethodException::VmWmiMethodException(uint)
0x14023b67b  mov     rcx, [rsp+388h]
0x14023b683  mov     r9, rax
0x14023b686  lea     r8, aOnecoreVmVmmsW_160; "onecore\\vm\\vmms\\wmi\\wmimsvmreplicat"...
0x14023b68d  mov     edx, 0F2Eh
0x14023b692  call    ??$ReportFailure_CustomException@VVmWmiMethodException@@@details@wil@@YAXPEAXIPEBDVVmWmiMethodException@@@Z; wil::details::ReportFailure_CustomException<VmWmiMethodException>(void *,uint,char const *,VmWmiMethodException)
0x14023b697  xor     ecx, ecx
0x14023b699  mov     [rsp+388h+var_308], ecx
0x14023b6a0  xor     r12b, r12b
0x14023b6a3  mov     [rsp+388h+var_338], r12b
0x14023b6a8  mov     [rsp+388h+var_304], r13d
0x14023b6b0  xor     r14d, r14d
0x14023b6b3  mov     [rsp+388h+var_300], r14d
0x14023b6bb  cmp     r14d, eax
0x14023b6be  jnb     loc_14023C0FE
0x14023b6c4  lea     r9, [rsp+388h+var_2E8]; struct tagSAFEARRAY **
0x14023b6cc  lea     r8, [rsp+388h+var_2F8]; unsigned __int16 **
0x14023b6d4  lea     rdx, [rsp+388h+var_2E0]; unsigned __int16 *
0x14023b6dc  mov     rcx, [rdi+r14*8]; this
0x14023b6e0  call    ?VmlWmiParseEmbeddedInstance@Vml@@YAXPEBGPEAPEAGPEAPEAUtagSAFEARRAY@@2@Z; Vml::VmlWmiParseEmbeddedInstance(ushort const *,ushort * *,tagSAFEARRAY * *,tagSAFEARRAY * *)
0x14023b6e5  lea     rdx, ?MsvmFailoverNetworkAdapterSettingData@@3QBGB; "Msvm_FailoverNetworkAdapterSettingData"
0x14023b6ec  mov     rcx, qword ptr [rsp+388h+var_2E0]
0x14023b6f4  call    cs:__imp__o__wcsicmp
0x14023b6fb  nop     dword ptr [rax+rax+00h]
0x14023b700  test    eax, eax
0x14023b702  jz      short loc_14023B732
0x14023b704  mov     edx, 8005h; unsigned int
0x14023b709  lea     rcx, [rsp+388h+var_298]; this
0x14023b711  call    ??0VmWmiMethodException@@QEAA@I@Z; VmWmiMethodException::VmWmiMethodException(uint)
0x14023b716  mov     rcx, [rsp+388h]
0x14023b71e  mov     r9, rax
0x14023b721  lea     r8, aOnecoreVmVmmsW_160; "onecore\\vm\\vmms\\wmi\\wmimsvmreplicat"...
0x14023b728  mov     edx, 0F39h
0x14023b72d  call    ??$ReportFailure_CustomException@VVmWmiMethodException@@@details@wil@@YAXPEAXIPEBDVVmWmiMethodException@@@Z; wil::details::ReportFailure_CustomException<VmWmiMethodException>(void *,uint,char const *,VmWmiMethodException)
0x14023b732  lea     rcx, [rsp+388h+var_2F8]; this
0x14023b73a  call    ?GetElementCount@VmSafeArray@Vml@@QEBAIXZ; Vml::VmSafeArray::GetElementCount(void)
0x14023b73f  mov     r13d, eax
0x14023b742  xorps   xmm0, xmm0
0x14023b745  movups  [rsp+388h+var_C8], xmm0
0x14023b74d  mov     rdx, [rsp+388h+var_2F8]; struct tagSAFEARRAY *
0x14023b755  lea     rcx, [rsp+388h+var_C8]; this
0x14023b75d  call    ??0VmSafeArrayAccessor@Vml@@QEAA@PEBUtagSAFEARRAY@@@Z; Vml::VmSafeArrayAccessor::VmSafeArrayAccessor(tagSAFEARRAY const *)
0x14023b762  nop
0x14023b763  mov     r15, qword ptr [rsp+388h+var_C8+8]
0x14023b76b  xorps   xmm0, xmm0
0x14023b76e  movups  [rsp+388h+var_D8], xmm0
0x14023b776  mov     rdx, [rsp+388h+var_2E8]; struct tagSAFEARRAY *
0x14023b77e  lea     rcx, [rsp+388h+var_D8]; this
0x14023b786  call    ??0VmSafeArrayAccessor@Vml@@QEAA@PEBUtagSAFEARRAY@@@Z; Vml::VmSafeArrayAccessor::VmSafeArrayAccessor(tagSAFEARRAY const *)
0x14023b78b  nop
0x14023b78c  mov     rdi, qword ptr [rsp+388h+var_D8+8]
0x14023b794  xor     r12d, r12d
0x14023b797  lea     r14d, [r12+1]
0x14023b79c  cmp     r12d, r13d
0x14023b79f  jnb     loc_14023BCD0
0x14023b7a5  mov     rdx, [r15]
0x14023b7a8  lea     rcx, aInstanceid_1; "InstanceID"
0x14023b7af  call    cs:__imp__o__wcsicmp
0x14023b7b6  nop     dword ptr [rax+rax+00h]
0x14023b7bb  test    eax, eax
0x14023b7bd  jnz     short loc_14023B82D
0x14023b7bf  cmp     r14w, [rdi]
0x14023b7c3  jnb     loc_14023B89F
0x14023b7c9  mov     eax, 8
0x14023b7ce  cmp     ax, [rdi]
0x14023b7d1  jz      short loc_14023B801
0x14023b7d3  mov     edx, 8005h; unsigned int
0x14023b7d8  lea     rcx, [rsp+388h+var_298]; this
0x14023b7e0  call    ??0VmWmiMethodException@@QEAA@I@Z; VmWmiMethodException::VmWmiMethodException(uint)
0x14023b7e5  mov     rcx, [rsp+388h]
0x14023b7ed  mov     r9, rax
0x14023b7f0  lea     r8, aOnecoreVmVmmsW_160; "onecore\\vm\\vmms\\wmi\\wmimsvmreplicat"...
0x14023b7f7  mov     edx, 0F4Fh
0x14023b7fc  call    ??$ReportFailure_CustomException@VVmWmiMethodException@@@details@wil@@YAXPEAXIPEBDVVmWmiMethodException@@@Z; wil::details::ReportFailure_CustomException<VmWmiMethodException>(void *,uint,char const *,VmWmiMethodException)
0x14023b801  mov     rdx, [rdi+8]; unsigned __int16 *
0x14023b805  lea     rcx, [rsp+388h+var_2F0]; this
0x14023b80d  call    ?Assign@VmBstr@Vml@@QEAAXPEBG@Z; Vml::VmBstr::Assign(ushort const *)
0x14023b812  mov     rdx, [rdi+8]
0x14023b816  lea     rcx, [rsp+388h+var_88]
0x14023b81e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x14023b823  mov     rbx, [rsp+388h+var_2F0]
0x14023b82b  jmp     short loc_14023B89F
0x14023b82d  mov     rdx, [r15]
0x14023b830  lea     rcx, aProtocoliftype_0; "ProtocolIFType"
0x14023b837  call    cs:__imp__o__wcsicmp
0x14023b83e  nop     dword ptr [rax+rax+00h]
0x14023b843  test    eax, eax
0x14023b845  jnz     short loc_14023B8AF
0x14023b847  lea     ecx, [rax+1]
0x14023b84a  cmp     cx, [rdi]
0x14023b84d  jnb     short loc_14023B885
0x14023b84f  lea     eax, [rcx+11h]
0x14023b852  cmp     ax, [rdi]
0x14023b855  jz      short loc_14023B885
0x14023b857  mov     edx, 8005h; unsigned int
0x14023b85c  lea     rcx, [rsp+388h+var_298]; this
0x14023b864  call    ??0VmWmiMethodException@@QEAA@I@Z; VmWmiMethodException::VmWmiMethodException(uint)
0x14023b869  mov     rcx, [rsp+388h]
0x14023b871  mov     r9, rax
0x14023b874  lea     r8, aOnecoreVmVmmsW_160; "onecore\\vm\\vmms\\wmi\\wmimsvmreplicat"...
0x14023b87b  mov     edx, 0F5Ch
0x14023b880  call    ??$ReportFailure_CustomException@VVmWmiMethodException@@@details@wil@@YAXPEAXIPEBDVVmWmiMethodException@@@Z; wil::details::ReportFailure_CustomException<VmWmiMethodException>(void *,uint,char const *,VmWmiMethodException)
0x14023b885  mov     [rsp+388h+var_308], ecx
0x14023b88c  movzx   ecx, word ptr [rdi+8]; unsigned __int16
0x14023b890  call    ?ProtocolIFTypeToAddressFamily@@YAEG@Z; ProtocolIFTypeToAddressFamily(ushort)
0x14023b895  mov     [rsp+388h+var_338], al
0x14023b899  mov     r14d, 1
0x14023b89f  add     r15, 8
0x14023b8a3  add     rdi, 18h
0x14023b8a7  add     r12d, r14d
0x14023b8aa  jmp     loc_14023B79C
0x14023b8af  mov     rdx, [r15]
0x14023b8b2  lea     rcx, aDhcpenabled; "DHCPEnabled"
0x14023b8b9  call    cs:__imp__o__wcsicmp
0x14023b8c0  nop     dword ptr [rax+rax+00h]
0x14023b8c5  test    eax, eax
0x14023b8c7  jnz     short loc_14023B914
0x14023b8c9  cmp     r14w, [rdi]
0x14023b8cd  jnb     short loc_14023B907
0x14023b8cf  mov     eax, 0Bh
0x14023b8d4  cmp     ax, [rdi]
0x14023b8d7  jz      short loc_14023B907
0x14023b8d9  mov     edx, 8005h; unsigned int
0x14023b8de  lea     rcx, [rsp+388h+var_298]; this
0x14023b8e6  call    ??0VmWmiMethodException@@QEAA@I@Z; VmWmiMethodException::VmWmiMethodException(uint)
0x14023b8eb  mov     rcx, [rsp+388h]
0x14023b8f3  mov     r9, rax
0x14023b8f6  lea     r8, aOnecoreVmVmmsW_160; "onecore\\vm\\vmms\\wmi\\wmimsvmreplicat"...
0x14023b8fd  mov     edx, 0F6Ah
0x14023b902  call    ??$ReportFailure_CustomException@VVmWmiMethodException@@@details@wil@@YAXPEAXIPEBDVVmWmiMethodException@@@Z; wil::details::ReportFailure_CustomException<VmWmiMethodException>(void *,uint,char const *,VmWmiMethodException)
0x14023b907  movsx   eax, word ptr [rdi+8]
0x14023b90b  mov     [rsp+388h+var_304], eax
0x14023b912  jmp     short loc_14023B89F
0x14023b914  mov     rdx, [r15]
0x14023b917  lea     rcx, aIpaddresses; "IPAddresses"
0x14023b91e  call    cs:__imp__o__wcsicmp
0x14023b925  nop     dword ptr [rax+rax+00h]
0x14023b92a  test    eax, eax
0x14023b92c  jnz     loc_14023BA03
0x14023b932  cmp     r14w, [rdi]
0x14023b936  jnb     loc_14023B89F
0x14023b93c  mov     eax, 2008h
0x14023b941  cmp     ax, [rdi]
0x14023b944  jz      short loc_14023B974
0x14023b946  mov     edx, 8005h; unsigned int
0x14023b94b  lea     rcx, [rsp+388h+var_298]; this
0x14023b953  call    ??0VmWmiMethodException@@QEAA@I@Z; VmWmiMethodException::VmWmiMethodException(uint)
0x14023b958  mov     rcx, [rsp+388h]
0x14023b960  mov     r9, rax
0x14023b963  lea     r8, aOnecoreVmVmmsW_160; "onecore\\vm\\vmms\\wmi\\wmimsvmreplicat"...
0x14023b96a  mov     edx, 0F76h
0x14023b96f  call    ??$ReportFailure_CustomException@VVmWmiMethodException@@@details@wil@@YAXPEAXIPEBDVVmWmiMethodException@@@Z; wil::details::ReportFailure_CustomException<VmWmiMethodException>(void *,uint,char const *,VmWmiMethodException)
0x14023b974  mov     rdx, [rdi+8]; psa
0x14023b978  lea     rcx, [rsp+388h+ppsaOut]; ppsaOut
0x14023b980  call    ?Assign@VmSafeArray@Vml@@QEAAXPEAUtagSAFEARRAY@@@Z; Vml::VmSafeArray::Assign(tagSAFEARRAY *)
0x14023b985  xor     r14d, r14d
0x14023b988  lea     rcx, [rsp+388h+ppsaOut]; this
  ... truncated ...
```
