# VmEthernetSwitchManager::EnumerateLogicalAdapters(__MIDL___MIDL_itf_genericvirtualswitchinterface_0000_0000_0001,IEnumVmLogicalAdapter * *)

- ea: `0x1400a5fc0`
- end: `0x1400a6baa`
- name: `?EnumerateLogicalAdapters@VmEthernetSwitchManager@@UEAAJW4__MIDL___MIDL_itf_genericvirtualswitchinterface_0000_0000_0001@@PEAPEAUIEnumVmLogicalAdapter@@@Z`
- size: `3050`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x14001a000`
- `0x14001abd0`
- `0x14001b934`
- `0x14001ded4`
- `0x140020a04`
- `0x140022640`
- `0x140024af4`
- `0x14002d384`
- `0x14002f0e0`
- `0x140034404`
- `0x14005c630`
- `0x1400a5cdc`
- `0x1400a5e28`
- `0x1400a5fc0`
- `0x1400a6bb0`
- `0x1400a6cb4`
- `0x1400a6e80`
- `0x1400a6f84`
- `0x1400a7060`
- `0x1400a7900`
- `0x1400a7970`
- `0x1400a7e24`
- `0x14017902c`
- `0x140188e18`
- `0x140228fa4`
- `0x1404828e0`
- `0x140482b74`
- `0x140482bac`
- `0x1404835a0`
- `0x1404835ac`
- `0x1404ead24`
- `0x1408aa010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400a67a7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400a67a7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400a6313`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400a6a5c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400a6a83`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400a6313`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400a6a5c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400a6a83`
- `vmsif!VmsIfNicEnumerate` at `0x1400a6045`
- `vmsif!VmsIfNicEnumerate` at `0x1400a6045`
- `vmsif!VmsIfMemFree` at `0x1400a6677`
- `vmsif!VmsIfMemFree` at `0x1400a6677`
- `vmsif!VmsIfDriverClose` at `0x1400a67d2`
- `vmsif!VmsIfDriverClose` at `0x1400a67d2`
- `vmsif!VmsIfDriverOpen` at `0x1400a6006`
- `vmsif!VmsIfDriverOpen` at `0x1400a6006`
- `NetSetupApi!NetSetupClose` at `0x1400a616d`
- `NetSetupApi!NetSetupClose` at `0x1400a68ba`
- `NetSetupApi!NetSetupClose` at `0x1400a616d`
- `NetSetupApi!NetSetupClose` at `0x1400a68ba`
- `NetSetupApi!NetSetupInitialize` at `0x1400a60ca`
- `NetSetupApi!NetSetupInitialize` at `0x1400a6846`
- `NetSetupApi!NetSetupInitialize` at `0x1400a60ca`
- `NetSetupApi!NetSetupInitialize` at `0x1400a6846`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall VmEthernetSwitchManager::EnumerateLogicalAdapters(__int64 a1, char a2, __int64 *a3)
{
  __int64 *v3; // r15
  char v4; // si
  int v5; // eax
  unsigned int v6; // eax
  struct _VMS_ENUM_NIC_INFO_OUT *v7; // r14
  int v8; // eax
  VmEthernetSwitchManager *v9; // rcx
  char *v10; // r13
  _BYTE *j; // rdi
  const struct std::nothrow_t *v12; // rdx
  char *v13; // rcx
  unsigned int n; // edi
  struct _VMS_ENUM_NIC_INFO_OUT *v15; // rbx
  __int64 v16; // rax
  const struct type_info *v17; // rdx
  __int64 v18; // rbx
  Vml::VmSharableObject *v19; // rcx
  int v20; // eax
  int ExternalNetworkAdapterVmswitchName; // eax
  unsigned int v22; // r15d
  struct _VMS_ENUM_NIC_INFO_OUT *v23; // r12
  unsigned __int16 **v24; // r14
  unsigned int k; // ebx
  char *v26; // rsi
  unsigned int v27; // r12d
  struct _VMS_ENUM_NIC_INFO_OUT *v28; // r15
  unsigned int m; // ebx
  bool v30; // bl
  struct _VMS_ENUM_NIC_INFO_OUT *v31; // r14
  VmEthernetAdapter *v32; // rax
  const struct type_info *v33; // rdx
  VmEthernetAdapter *v34; // rbx
  Vml::VmSharableObject *v35; // rcx
  __int64 v36; // rbx
  struct _VMS_ENUM_NIC_INFO_OUT *v37; // rax
  __int64 v38; // rax
  __int64 *v39; // rsi
  signed __int64 v40; // r14
  unsigned __int64 v41; // rcx
  unsigned __int64 v42; // rdx
  __int64 v43; // r12
  size_t size_of; // rax
  _QWORD *v45; // r15
  __int64 *v46; // r8
  __int64 *v47; // rdx
  _QWORD *v48; // rcx
  struct _VMS_ENUM_NIC_INFO_OUT *v49; // rax
  __int64 v50; // rax
  __int64 v51; // rbx
  __int64 v52; // rax
  const struct std::nothrow_t *v53; // rdx
  void *v54; // rcx
  const struct std::nothrow_t *v55; // rdx
  unsigned __int16 *v56; // rcx
  __int64 v57; // rbx
  const char *v58; // r9
  __int64 result; // rax
  __int64 v60; // rax
  char *v61; // rsi
  char *v62; // r14
  __int64 v63; // rax
  __int64 *v64; // rdx
  __int64 v65; // rax
  int v66; // eax
  VmEthernetSwitchManager *v67; // rcx
  void *v68; // rdi
  char *i; // rbx
  int NetworkAdapterInstanceGuid; // eax
  const unsigned __int16 *v71; // rdx
  __int64 v72; // rax
  __int64 v73; // r14
  unsigned int ii; // ebx
  __int64 v75; // rax
  unsigned int v76; // [rsp+20h] [rbp-128h]
  const char *v77; // [rsp+20h] [rbp-128h]
  __int64 *v79; // [rsp+38h] [rbp-110h] BYREF
  struct _VMS_ENUM_NIC_INFO_OUT *InternalNicInfo; // [rsp+40h] [rbp-108h] BYREF
  __int64 v81; // [rsp+48h] [rbp-100h] BYREF
  void *v82[2]; // [rsp+50h] [rbp-F8h]
  __int64 v83; // [rsp+60h] [rbp-E8h]
  struct _VMS_ENUM_NIC_INFO_OUT *v84; // [rsp+68h] [rbp-E0h]
  struct _VMS_ENUM_NIC_INFO_OUT *v85; // [rsp+70h] [rbp-D8h]
  void **pExceptionObject; // [rsp+78h] [rbp-D0h] BYREF
  __int128 v87; // [rsp+80h] [rbp-C8h]
  struct _VMS_ENUM_NIC_INFO_OUT *v88; // [rsp+90h] [rbp-B8h] BYREF
  unsigned int v89; // [rsp+98h] [rbp-B0h] BYREF
  void *v90[2]; // [rsp+A0h] [rbp-A8h] BYREF
  VmEthernetSwitchManager *v91; // [rsp+B0h] [rbp-98h]
  __int128 v92; // [rsp+B8h] [rbp-90h] BYREF
  unsigned __int16 *v93[2]; // [rsp+C8h] [rbp-80h] BYREF
  __int64 v94; // [rsp+D8h] [rbp-70h]
  unsigned __int64 v95; // [rsp+E0h] [rbp-68h]
  __int64 v96; // [rsp+E8h] [rbp-60h] BYREF
  __int128 v97; // [rsp+F0h] [rbp-58h] BYREF
  __int64 v98; // [rsp+100h] [rbp-48h]
  unsigned __int64 v99; // [rsp+108h] [rbp-40h]
  VmEthernetSwitchManager *retaddr; // [rsp+148h] [rbp+0h]

  v3 = a3;
  v79 = a3;
  v4 = a2;
  v96 = 0;
  v5 = VmsIfDriverOpen(&v96);
  try
  {
    if ( v5 )
    {
      pExceptionObject = &std::exception::`vftable';
      v87 = 0;
      throw (std::exception *)&pExceptionObject;
    }
    v88 = 0;
    v89 = 0;
    v6 = VmsIfNicEnumerate(v96, &v88, 0, &v89);
    if ( v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x134,
        (unsigned int)"onecore\\vm\\vmms\\ethernet\\vmethernetswitchmanager.cpp",
        (const char *)v6,
        v76);
    v7 = v88;
    v84 = v88;
    v85 = v88;
    *(_OWORD *)v90 = 0;
    v91 = 0;
    if ( (v4 & 1) != 0 )
    {
      v92 = *(unsigned __int64 *)&NetSetupHelper::gm_TraceLoggingProvider;
      NetSetupInitialize(0, (char *)&v92 + 8);
      *(_OWORD *)v82 = 0;
      v83 = 0;
      v66 = NetSetupHelper::EnumerateNetworkAdapters((NetSetupHelper *)&v92);
      v67 = retaddr;
      if ( v66 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x148,
          (unsigned int)"onecore\\vm\\vmms\\ethernet\\vmethernetswitchmanager.cpp",
          (const char *)(unsigned int)v66,
          v76);
      v68 = v82[0];
      for ( i = (char *)v82[0]; i != v82[1]; i += 64 )
      {
        *(_OWORD *)v93 = 0;
        v94 = 0;
        v95 = 7;
        LOWORD(v93[0]) = 0;
        NetworkAdapterInstanceGuid = NetSetupHelper::GetNetworkAdapterInstanceGuid(v67, i + 24, v93);
        if ( NetworkAdapterInstanceGuid < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x153,
            (unsigned int)"onecore\\vm\\vmms\\ethernet\\vmethernetswitchmanager.cpp",
            (const char *)(unsigned int)NetworkAdapterInstanceGuid,
            v76);
        v71 = (const unsigned __int16 *)v93;
        if ( v95 > 7 )
          v71 = v93[0];
        InternalNicInfo = VmEthernetSwitchManager::FindInternalNicInfo(retaddr, v71, v88, v89);
        if ( InternalNicInfo )
        {
          v81 = 0;
          v72 = Vml::VmComMultiInstanceObject<VmEthernetAdapter>::CreateInstance<_VMS_ENUM_NIC_INFO_OUT * &>(&InternalNicInfo);
          Vml::VmComPtr<IVmWmiObject>::Attach<WmiMsvmVirtualSystemReferencePointService>(&v81, v72);
          std::vector<Vml::VmComPtr<IVmLogicalAdapter>>::_Emplace_one_at_back<Vml::VmComPtr<IVmLogicalAdapter> const &>(
            v90,
            &v81);
          Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v81);
        }
        std::wstring::_Tidy_deallocate(v93);
      }
      if ( v68 )
        std::_Deallocate<16>(v68, (v83 - (_QWORD)v68) & 0xFFFFFFFFFFFFFFC0uLL);
      if ( *((_QWORD *)&v92 + 1) )
        NetSetupClose(*((_QWORD *)&v92 + 1));
      v4 = a2;
      v7 = v84;
      v3 = v79;
    }
    if ( (v4 & 2) != 0 )
    {
      v92 = *(unsigned __int64 *)&NetSetupHelper::gm_TraceLoggingProvider;
      NetSetupInitialize(0, (char *)&v92 + 8);
      *(_OWORD *)v82 = 0;
      v83 = 0;
      v8 = NetSetupHelper::EnumerateNetworkAdapters((NetSetupHelper *)&v92);
      v9 = retaddr;
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x16E,
          (unsigned int)"onecore\\vm\\vmms\\ethernet\\vmethernetswitchmanager.cpp",
          (const char *)(unsigned int)v8,
          v76);
      v10 = (char *)v82[0];
      for ( j = v82[0]; j != v82[1]; j += 64 )
      {
        v97 = 0;
        v98 = 0;
        v99 = 7;
        LOWORD(v97) = 0;
        v20 = NetSetupHelper::GetNetworkAdapterInstanceGuid(v9, j + 24, &v97);
        if ( v20 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x179,
            (unsigned int)"onecore\\vm\\vmms\\ethernet\\vmethernetswitchmanager.cpp",
            (const char *)(unsigned int)v20,
            v76);
        v81 = 0;
        if ( (j[16] & 4) != 0 )
        {
          *(_OWORD *)v93 = 0;
          v94 = 0;
          v95 = 7;
          LOWORD(v93[0]) = 0;
          ExternalNetworkAdapterVmswitchName = NetSetupHelper::GetExternalNetworkAdapterVmswitchName(
                                                 retaddr,
                                                 j + 24,
                                                 v93);
          if ( ExternalNetworkAdapterVmswitchName < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x184,
              (unsigned int)"onecore\\vm\\vmms\\ethernet\\vmethernetswitchmanager.cpp",
              (const char *)(unsigned int)ExternalNetworkAdapterVmswitchName,
              v76);
          v22 = v89;
          v23 = v88;
          v24 = v93;
          if ( v95 > 7 )
            v24 = (unsigned __int16 **)v93[0];
          for ( k = 0; ; ++k )
          {
            if ( k >= v22 )
              goto LABEL_43;
            v26 = (char *)v23 + 2612 * k;
            if ( *((_DWORD *)v26 + 193) == 2 && !(unsigned int)_o__wcsnicmp(v24, (char *)v23 + 2612 * k, 128) )
              break;
          }
          if ( v26 )
          {
            v27 = v89;
            v28 = v88;
            for ( m = 0; ; ++m )
            {
              if ( m >= v27 )
              {
                v30 = 0;
                goto LABEL_39;
              }
              v73 = 2612LL * m;
              if ( *(_DWORD *)((char *)v28 + v73 + 772) == 6
                && !(unsigned int)_o__wcsnicmp(v26 + 782, (char *)v28 + v73 + 782, 128)
                && !(unsigned int)_o__wcsnicmp(v26 + 1038, (char *)v28 + v73 + 1038, 128) )
              {
                break;
              }
            }
            v30 = 1;
LABEL_39:
            v31 = (struct _VMS_ENUM_NIC_INFO_OUT *)operator new(0xAF8u);
            InternalNicInfo = v31;
            memset_0(v31, 0, 0xAF8u);
            v32 = VmEthernetAdapter::VmEthernetAdapter(v31, (struct _VMS_ENUM_NIC_INFO_OUT *const)v26, v30);
            v34 = v32;
            if ( v32 )
              v35 = (VmEthernetAdapter *)((char *)v32 + *(int *)(*((_QWORD *)v32 + 1) + 4LL) + 8);
            else
              v35 = 0;
            Vml::VmSharableObject::AddUserInternal(v35, v33);
            if ( v34 )
            {
              v36 = (__int64)v34 + 24;
              goto LABEL_47;
            }
LABEL_46:
            v36 = 0;
            goto LABEL_47;
          }
LABEL_43:
          v37 = (struct _VMS_ENUM_NIC_INFO_OUT *)&v97;
          if ( v99 > 7 )
            v37 = (struct _VMS_ENUM_NIC_INFO_OUT *)v97;
          InternalNicInfo = v37;
          v38 = Vml::VmComMultiInstanceObject<VmEthernetAdapter>::CreateInstance<unsigned short const *>(&InternalNicInfo);
          v36 = v38 + 24;
          if ( !v38 )
            goto LABEL_46;
LABEL_47:
          v81 = v36;
          if ( v95 > 7 )
          {
            v55 = (const struct std::nothrow_t *)(2 * v95 + 2);
            v56 = v93[0];
            if ( (unsigned __int64)v55 >= 0x1000 )
            {
              if ( (unsigned __int64)v93[0] - *((_QWORD *)v93[0] - 1) - 8 > 0x1F )
                __fastfail(5u);
              v55 = (const struct std::nothrow_t *)(2 * v95 + 41);
              v56 = (unsigned __int16 *)*((_QWORD *)v93[0] - 1);
            }
            operator delete(v56, v55);
          }
        }
        else
        {
          if ( (j[16] & 8) == 0 )
          {
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x1A2,
              (unsigned int)"onecore\\vm\\vmms\\ethernet\\vmethernetswitchmanager.cpp",
              (const char *)0x8000FFFFLL,
              v76);
            if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
            {
              v77 = "currentNetworkAdapter->AdapterType";
              VmlDebugTrace(
                0,
                L"%hs(%u) : unexpected integer value : %hs == %d\n",
                "onecore\\vm\\vmms\\ethernet\\vmethernetswitchmanager.cpp",
                418);
            }
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1A3,
              (unsigned int)"onecore\\vm\\vmms\\ethernet\\vmethernetswitchmanager.cpp",
              (const char *)0x8000FFFFLL,
              (int)v77);
          }
          v49 = (struct _VMS_ENUM_NIC_INFO_OUT *)&v97;
          if ( v99 > 7 )
            v49 = (struct _VMS_ENUM_NIC_INFO_OUT *)v97;
          InternalNicInfo = v49;
          v50 = Vml::VmComMultiInstanceObject<VmBridgedAdapter>::CreateInstance<unsigned short const *>(&InternalNicInfo);
          if ( v50 )
            v36 = v50 + 24;
          else
            v36 = 0;
          v81 = v36;
        }
        v39 = (__int64 *)v90[1];
        v9 = v91;
        if ( v90[1] == v91 )
        {
          v40 = ((char *)v90[1] - (char *)v90[0]) >> 3;
          if ( v40 == 0x1FFFFFFFFFFFFFFFLL )
            std::_Xlength_error("vector too long");
          InternalNicInfo = (struct _VMS_ENUM_NIC_INFO_OUT *)(v40 + 1);
          v41 = ((char *)v91 - (char *)v90[0]) >> 3;
          v42 = v41 >> 1;
          if ( v41 > 0x1FFFFFFFFFFFFFFFLL - (v41 >> 1) )
          {
            v43 = 0x1FFFFFFFFFFFFFFFLL;
          }
          else
          {
            v43 = v42 + v41;
            if ( v42 + v41 < v40 + 1 )
              v43 = v40 + 1;
          }
          size_of = std::_Get_size_of_n<8>(v43);
          v45 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
          v45[v40] = v36;
          if ( v36 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
          v46 = (__int64 *)v90[1];
          v47 = (__int64 *)v90[0];
          v48 = v45;
          if ( v39 == v90[1] )
          {
            while ( v47 != v46 )
            {
              v60 = *v47;
              *v47 = 0;
              *v48++ = v60;
              ++v47;
            }
          }
          else
          {
            while ( v47 != v39 )
            {
              v63 = *v47;
              *v47 = 0;
              *v48++ = v63;
              ++v47;
            }
            std::_Destroy_range<std::allocator<Vml::VmComPtr<IUnknown>>>(v48);
            v64 = (__int64 *)v90[1];
            v48 = &v45[v40 + 1];
            while ( v39 != v64 )
            {
              v65 = *v39;
              *v39 = 0;
              *v48++ = v65;
              ++v39;
            }
          }
          std::_Destroy_range<std::allocator<Vml::VmComPtr<IUnknown>>>(v48);
          v61 = (char *)v90[0];
          if ( v90[0] )
          {
            v62 = (char *)v90[1];
            if ( v90[0] != v90[1] )
            {
              do
              {
                Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(v61);
                v61 += 8;
              }
              while ( v61 != v62 );
              v61 = (char *)v90[0];
            }
            std::_Deallocate<16>(v61, (v91 - (VmEthernetSwitchManager *)v61) & 0xFFFFFFFFFFFFFFF8uLL);
          }
          v90[0] = v45;
          v90[1] = &v45[(_QWORD)InternalNicInfo];
          v91 = (VmEthernetSwitchManager *)&v45[v43];
        }
        else
        {
          *(_QWORD *)v90[1] = v36;
          if ( v36 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
          v90[1] = (char *)v90[1] + 8;
        }
        if ( v36 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        if ( v99 > 7 )
        {
          v53 = (const struct std::nothrow_t *)(2 * v99 + 2);
          v54 = (void *)v97;
          if ( (unsigned __int64)v53 >= 0x1000 )
          {
            if ( (unsigned __int64)(v97 - *(_QWORD *)(v97 - 8) - 8) > 0x1F )
              __fastfail(5u);
            v53 = (const struct std::nothrow_t *)(2 * v99 + 41);
            v54 = *(void **)(v97 - 8);
          }
          operator delete(v54, v53);
        }
      }
      if ( v10 )
      {
        v12 = (const struct std::nothrow_t *)((v83 - (_QWORD)v10) & 0xFFFFFFFFFFFFFFC0uLL);
        if ( (unsigned __int64)v12 >= 0x1000 )
        {
          v13 = (char *)*((_QWORD *)v10 - 1);
          if ( (unsigned __int64)(v10 - v13 - 8) > 0x1F )
            __fastfail(5u);
          v12 = (const struct std::nothrow_t *)((char *)v12 + 39);
        }
        else
        {
          v13 = v10;
        }
        operator delete(v13, v12);
      }
      if ( *((_QWORD *)&v92 + 1) )
        NetSetupClose(*((_QWORD *)&v92 + 1));
      v4 = a2;
      v7 = v84;
      v3 = v79;
    }
    if ( (v4 & 8) != 0 )
    {
      for ( n = 0; n < v89; ++n )
      {
        v51 = 0;
        v79 = 0;
        if ( *((_DWORD *)v88 + 653 * n + 193) == 6 )
        {
          InternalNicInfo = (struct _VMS_ENUM_NIC_INFO_OUT *)((char *)v88 + 2612 * n);
          v52 = Vml::VmComMultiInstanceObject<VmEthernetAdapter>::CreateInstance<_VMS_ENUM_NIC_INFO_OUT * &>(&InternalNicInfo);
          v51 = v52 + 24;
          if ( !v52 )
            v51 = 0;
          v79 = (__int64 *)v51;
          if ( v90[1] == v91 )
          {
            std::vector<Vml::VmComPtr<IVmLogicalAdapter>>::_Emplace_reallocate<Vml::VmComPtr<IVmLogicalAdapter> const &>(
              v90,
              v90[1],
              &v79);
            v51 = (__int64)v79;
          }
          else
          {
            *(_QWORD *)v90[1] = v51;
            if ( v51 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v51);
            v90[1] = (char *)v90[1] + 8;
          }
        }
        if ( v51 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      }
    }
    if ( (v4 & 4) != 0 )
    {
      for ( ii = 0; ii < v89; ++ii )
      {
        if ( (unsigned int)(*((_DWORD *)v88 + 653 * ii + 193) - 3) <= 1 )
        {
          v79 = 0;
          InternalNicInfo = (struct _VMS_ENUM_NIC_INFO_OUT *)((char *)v88 + 2612 * ii);
          v75 = Vml::VmComMultiInstanceObject<VmEthernetAdapter>::CreateInstance<_VMS_ENUM_NIC_INFO_OUT * &>(&InternalNicInfo);
          Vml::VmComPtr<IVmWmiObject>::Attach<WmiMsvmVirtualSystemReferencePointService>(&v79, v75);
          std::vector<Vml::VmComPtr<IVmLogicalAdapter>>::_Emplace_one_at_back<Vml::VmComPtr<IVmLogicalAdapter> const &>(
            v90,
            &v79);
          Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v79);
        }
      }
    }
    v15 = (struct _VMS_ENUM_NIC_INFO_OUT *)operator new(0x90u);
    InternalNicInfo = v15;
    memset_0(v15, 0, 0x90u);
    v16 = Vml::VmComEnum<IEnumVmLogicalAdapter,IVmLogicalAdapter *,Vml::VmComPtr<IVmLogicalAdapter>,std::vector<Vml::VmComPtr<IVmLogicalAdapter>>>::VmComEnum<IEnumVmLogicalAdapter,IVmLogicalAdapter *,Vml::VmComPtr<IVmLogicalAdapter>,std::vector<Vml::VmComPtr<IVmLogicalAdapter>>>(
            v15,
            v90);
    v18 = v16;
    if ( v16 )
      v19 = (Vml::VmSharableObject *)(v16 + *(int *)(*(_QWORD *)(v16 + 8) + 4LL) + 8LL);
    else
      v19 = 0;
    Vml::VmSharableObject::AddUserInternal(v19, v17);
    if ( v18 )
      v57 = v18 + 24;
    else
      v57 = 0;
    *v3 = v57;
    std::vector<Vml::VmComPtr<IVmLogicalAdapter>>::_Tidy(v90);
    if ( v7 )
      VmsIfMemFree(v7);
    if ( v96 )
      VmsIfDriverClose();
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1D3,
                           (unsigned int)"onecore\\vm\\vmms\\ethernet\\vmethernetswitchmanager.cpp",
                           v58);
  }
  return result;
}

```

## disassembly

```asm
0x1400a5fc0  mov     r11, rsp
0x1400a5fc3  mov     [r11+8], rbx
0x1400a5fc7  mov     [r11+10h], rsi
0x1400a5fcb  push    rdi
0x1400a5fcc  push    r12
0x1400a5fce  push    r13
0x1400a5fd0  push    r14
0x1400a5fd2  push    r15
0x1400a5fd4  sub     rsp, 120h
0x1400a5fdb  mov     rax, cs:__security_cookie
0x1400a5fe2  xor     rax, rsp
0x1400a5fe5  mov     [rsp+148h+var_38], rax
0x1400a5fed  mov     r15, r8
0x1400a5ff0  mov     [rsp+148h+var_110], r8
0x1400a5ff5  mov     esi, edx
0x1400a5ff7  mov     [rsp+148h+var_118], edx
0x1400a5ffb  xor     r12d, r12d
0x1400a5ffe  mov     [r11-60h], r12
0x1400a6002  lea     rcx, [r11-60h]
0x1400a6006  call    cs:__imp_VmsIfDriverOpen
0x1400a600d  nop     dword ptr [rax+rax+00h]
0x1400a6012  test    eax, eax
0x1400a6014  jnz     loc_1400A6971
0x1400a601a  mov     [rsp+148h+var_B8], r12
0x1400a6022  mov     [rsp+148h+var_B0], r12d
0x1400a602a  lea     r9, [rsp+148h+var_B0]
0x1400a6032  xor     r8d, r8d
0x1400a6035  lea     rdx, [rsp+148h+var_B8]
0x1400a603d  mov     rcx, [rsp+148h+var_60]
0x1400a6045  call    cs:__imp_VmsIfNicEnumerate
0x1400a604c  nop     dword ptr [rax+rax+00h]
0x1400a6051  mov     rcx, [rsp+148h]; this
0x1400a6059  test    eax, eax
0x1400a605b  jnz     loc_1400A699A
0x1400a6061  mov     r14, [rsp+148h+var_B8]
0x1400a6069  mov     [rsp+148h+var_E0], r14
0x1400a606e  mov     [rsp+148h+var_D8], r14
0x1400a6073  xorps   xmm0, xmm0
0x1400a6076  xorps   xmm1, xmm1
0x1400a6079  movdqu  xmmword ptr [rsp+148h+var_A8], xmm1
0x1400a6082  mov     [rsp+148h+var_98], r12
0x1400a608a  test    sil, 1
0x1400a608e  jnz     loc_1400A681D
0x1400a6094  test    sil, 2
0x1400a6098  jz      loc_1400A6187
0x1400a609e  xorps   xmm0, xmm0
0x1400a60a1  movups  [rsp+148h+var_90], xmm0
0x1400a60a9  mov     qword ptr [rsp+148h+var_90+8], r12
0x1400a60b1  mov     rax, cs:?gm_TraceLoggingProvider@NetSetupHelper@@0PEBU_tlgProvider_t@@EB; _tlgProvider_t const * const NetSetupHelper::gm_TraceLoggingProvider
0x1400a60b8  mov     qword ptr [rsp+148h+var_90], rax
0x1400a60c0  lea     rdx, [rsp+148h+var_90+8]
0x1400a60c8  xor     ecx, ecx
0x1400a60ca  call    cs:__imp_NetSetupInitialize
0x1400a60d1  nop     dword ptr [rax+rax+00h]
0x1400a60d6  nop
0x1400a60d7  xorps   xmm1, xmm1
0x1400a60da  movdqu  xmmword ptr [rsp+148h+var_F8], xmm1
0x1400a60e0  mov     [rsp+148h+var_E8], r12
0x1400a60e5  lea     r8, [rsp+148h+var_F8]
0x1400a60ea  mov     edx, 0Ch
0x1400a60ef  lea     rcx, [rsp+148h+var_90]; this
0x1400a60f7  call    ?EnumerateNetworkAdapters@NetSetupHelper@@QEAAJKAEAV?$vector@U_VM_NETWORK_ADAPTER_DESCRIPTOR@@V?$allocator@U_VM_NETWORK_ADAPTER_DESCRIPTOR@@@std@@@std@@@Z; NetSetupHelper::EnumerateNetworkAdapters(ulong,std::vector<_VM_NETWORK_ADAPTER_DESCRIPTOR> &)
0x1400a60fc  mov     rcx, [rsp+148h]; this
0x1400a6104  test    eax, eax
0x1400a6106  jns     short loc_1400A611C
0x1400a6108  mov     r9d, eax; char *
0x1400a610b  lea     r8, aOnecoreVmVmmsE_6; "onecore\\vm\\vmms\\ethernet\\vmethernet"...
0x1400a6112  mov     edx, 16Eh; void *
0x1400a6117  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a611c  mov     r13, [rsp+148h+var_F8]
0x1400a6121  mov     rdi, r13
0x1400a6124  mov     r15, 1FFFFFFFFFFFFFFFh
0x1400a612e  cmp     rdi, [rsp+148h+var_F8+8]
0x1400a6133  jnz     loc_1400A61F8
0x1400a6139  test    r13, r13
0x1400a613c  jz      short loc_1400A6160
0x1400a613e  mov     rdx, [rsp+148h+var_E8]
0x1400a6143  sub     rdx, r13
0x1400a6146  and     rdx, 0FFFFFFFFFFFFFFC0h; struct std::nothrow_t *
0x1400a614a  cmp     rdx, 1000h
0x1400a6151  jnb     loc_1400A67FF
0x1400a6157  mov     rcx, r13; void *
0x1400a615a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400a615f  nop
0x1400a6160  mov     rcx, qword ptr [rsp+148h+var_90+8]
0x1400a6168  test    rcx, rcx
0x1400a616b  jz      short loc_1400A6179
0x1400a616d  call    cs:__imp_NetSetupClose
0x1400a6174  nop     dword ptr [rax+rax+00h]
0x1400a6179  mov     esi, [rsp+148h+var_118]
0x1400a617d  mov     r14, [rsp+148h+var_E0]
0x1400a6182  mov     r15, [rsp+148h+var_110]
0x1400a6187  test    sil, 8
0x1400a618b  jz      short loc_1400A619D
0x1400a618d  mov     edi, r12d
0x1400a6190  cmp     edi, [rsp+148h+var_B0]
0x1400a6197  jb      loc_1400A653C
0x1400a619d  test    sil, 4
0x1400a61a1  jnz     loc_1400A6B30
0x1400a61a7  mov     edi, 90h
0x1400a61ac  mov     ecx, edi; Size
0x1400a61ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400a61b3  mov     rbx, rax
0x1400a61b6  mov     [rsp+148h+var_108], rax
0x1400a61bb  mov     r8d, edi; Size
0x1400a61be  xor     edx, edx; Val
0x1400a61c0  mov     rcx, rax; void *
0x1400a61c3  call    memset_0
0x1400a61c8  lea     rdx, [rsp+148h+var_A8]
0x1400a61d0  mov     rcx, rbx
0x1400a61d3  call    ??0?$VmComEnum@UIEnumVmLogicalAdapter@@PEAUIVmLogicalAdapter@@V?$VmComPtr@UIVmLogicalAdapter@@@Vml@@V?$vector@V?$VmComPtr@UIVmLogicalAdapter@@@Vml@@V?$allocator@V?$VmComPtr@UIVmLogicalAdapter@@@Vml@@@std@@@std@@@Vml@@QEAA@AEBV?$vector@V?$VmComPtr@UIVmLogicalAdapter@@@Vml@@V?$allocator@V?$VmComPtr@UIVmLogicalAdapter@@@Vml@@@std@@@std@@@Z; Vml::VmComEnum<IEnumVmLogicalAdapter,IVmLogicalAdapter *,Vml::VmComPtr<IVmLogicalAdapter>,std::vector<Vml::VmComPtr<IVmLogicalAdapter>>>::VmComEnum<IEnumVmLogicalAdapter,IVmLogicalAdapter *,Vml::VmComPtr<IVmLogicalAdapter>,std::vector<Vml::VmComPtr<IVmLogicalAdapter>>>(std::vector<Vml::VmComPtr<IVmLogicalAdapter>> const &)
0x1400a61d8  mov     rbx, rax
0x1400a61db  test    rax, rax
0x1400a61de  jz      loc_1400A664D
0x1400a61e4  mov     rax, [rax+8]
0x1400a61e8  movsxd  rcx, dword ptr [rax+4]
0x1400a61ec  add     rcx, 8
0x1400a61f0  add     rcx, rbx
0x1400a61f3  jmp     loc_1400A6650
0x1400a61f8  xorps   xmm0, xmm0
0x1400a61fb  movups  [rsp+148h+var_58], xmm0
0x1400a6203  mov     [rsp+148h+var_48], r12
0x1400a620b  mov     [rsp+148h+var_40], 7
0x1400a6217  mov     word ptr [rsp+148h+var_58], r12w
0x1400a6220  lea     r8, [rsp+148h+var_58]
0x1400a6228  lea     rdx, [rdi+18h]
0x1400a622c  call    ?GetNetworkAdapterInstanceGuid@NetSetupHelper@@QEAAJPEBVNetSetupAdapter@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NetSetupHelper::GetNetworkAdapterInstanceGuid(NetSetupAdapter const *,std::wstring &)
0x1400a6231  mov     rcx, [rsp+148h]; this
0x1400a6239  test    eax, eax
0x1400a623b  jns     short loc_1400A6251
0x1400a623d  mov     r9d, eax; char *
0x1400a6240  lea     r8, aOnecoreVmVmmsE_6; "onecore\\vm\\vmms\\ethernet\\vmethernet"...
0x1400a6247  mov     edx, 179h; void *
0x1400a624c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a6251  mov     [rsp+148h+var_100], r12
0x1400a6256  test    byte ptr [rdi+10h], 4
0x1400a625a  jz      loc_1400A64F3
0x1400a6260  xorps   xmm0, xmm0
0x1400a6263  movups  xmmword ptr [rsp+148h+var_80], xmm0
0x1400a626b  mov     [rsp+148h+var_70], r12
0x1400a6273  mov     [rsp+148h+var_68], 7
0x1400a627f  mov     word ptr [rsp+148h+var_80], r12w
0x1400a6288  lea     r8, [rsp+148h+var_80]
0x1400a6290  lea     rdx, [rdi+18h]
0x1400a6294  call    ?GetExternalNetworkAdapterVmswitchName@NetSetupHelper@@QEAAJPEAVNetSetupAdapter@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NetSetupHelper::GetExternalNetworkAdapterVmswitchName(NetSetupAdapter *,std::wstring &)
0x1400a6299  mov     rcx, [rsp+148h]; this
0x1400a62a1  test    eax, eax
0x1400a62a3  jns     short loc_1400A62B9
0x1400a62a5  mov     r9d, eax; char *
0x1400a62a8  lea     r8, aOnecoreVmVmmsE_6; "onecore\\vm\\vmms\\ethernet\\vmethernet"...
0x1400a62af  mov     edx, 184h; void *
0x1400a62b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a62b9  mov     r15d, [rsp+148h+var_B0]
0x1400a62c1  mov     r12, [rsp+148h+var_B8]
0x1400a62c9  lea     r14, [rsp+148h+var_80]
0x1400a62d1  cmp     [rsp+148h+var_68], 7
0x1400a62da  cmova   r14, [rsp+148h+var_80]
0x1400a62e3  xor     ebx, ebx
0x1400a62e5  cmp     ebx, r15d
0x1400a62e8  jnb     loc_1400A639C
0x1400a62ee  mov     eax, ebx
0x1400a62f0  imul    rsi, rax, 0A34h
0x1400a62f7  add     rsi, r12
0x1400a62fa  cmp     dword ptr [rsi+304h], 2
0x1400a6301  jz      short loc_1400A6307
0x1400a6303  inc     ebx
0x1400a6305  jmp     short loc_1400A62E5
0x1400a6307  mov     r8d, 80h
0x1400a630d  mov     rdx, rsi
0x1400a6310  mov     rcx, r14
0x1400a6313  call    cs:__imp__o__wcsnicmp
0x1400a631a  nop     dword ptr [rax+rax+00h]
0x1400a631f  test    eax, eax
0x1400a6321  jnz     short loc_1400A6303
0x1400a6323  xor     r12d, r12d
0x1400a6326  test    rsi, rsi
0x1400a6329  jz      short loc_1400A639F
0x1400a632b  mov     r12d, [rsp+148h+var_B0]
0x1400a6333  mov     r15, [rsp+148h+var_B8]
0x1400a633b  xor     ebx, ebx
0x1400a633d  cmp     ebx, r12d
0x1400a6340  jb      loc_1400A6A31
0x1400a6346  xor     r12d, r12d
0x1400a6349  mov     bl, r12b
0x1400a634c  mov     r15d, 0AF8h
0x1400a6352  mov     ecx, r15d; Size
0x1400a6355  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400a635a  mov     r14, rax
0x1400a635d  mov     [rsp+148h+var_108], rax
0x1400a6362  mov     r8d, r15d; Size
0x1400a6365  xor     edx, edx; Val
0x1400a6367  mov     rcx, rax; void *
0x1400a636a  call    memset_0
0x1400a636f  mov     r8b, bl; bool
0x1400a6372  mov     rdx, rsi; struct _VMS_ENUM_NIC_INFO_OUT *
0x1400a6375  mov     rcx, r14; this
0x1400a6378  call    ??0VmEthernetAdapter@@IEAA@QEAU_VMS_ENUM_NIC_INFO_OUT@@_N@Z; VmEthernetAdapter::VmEthernetAdapter(_VMS_ENUM_NIC_INFO_OUT * const,bool)
0x1400a637d  mov     rbx, rax
0x1400a6380  test    rax, rax
0x1400a6383  jnz     loc_1400A6947
0x1400a6389  mov     rcx, r12; this
0x1400a638c  call    ?AddUserInternal@VmSharableObject@Vml@@AEAAKAEBVtype_info@@@Z; Vml::VmSharableObject::AddUserInternal(type_info const &)
0x1400a6391  test    rbx, rbx
0x1400a6394  jz      short loc_1400A63D1
0x1400a6396  add     rbx, 18h
0x1400a639a  jmp     short loc_1400A63D4
0x1400a639c  xor     r12d, r12d
0x1400a639f  lea     rax, [rsp+148h+var_58]
0x1400a63a7  cmp     [rsp+148h+var_40], 7
0x1400a63b0  cmova   rax, qword ptr [rsp+148h+var_58]
0x1400a63b9  mov     [rsp+148h+var_108], rax
0x1400a63be  lea     rcx, [rsp+148h+var_108]
0x1400a63c3  call    ??$CreateInstance@PEBG@?$VmComMultiInstanceObject@VVmEthernetAdapter@@@Vml@@SAPEAVVmEthernetAdapter@@$$QEAPEBG@Z; Vml::VmComMultiInstanceObject<VmEthernetAdapter>::CreateInstance<ushort const *>(ushort const * &&)
0x1400a63c8  test    rax, rax
0x1400a63cb  lea     rbx, [rax+18h]
0x1400a63cf  jnz     short loc_1400A63D4
0x1400a63d1  mov     rbx, r12
0x1400a63d4  mov     [rsp+148h+var_100], rbx
0x1400a63d9  mov     rdx, [rsp+148h+var_68]
0x1400a63e1  cmp     rdx, 7
0x1400a63e5  ja      loc_1400A660E
0x1400a63eb  mov     r15, 1FFFFFFFFFFFFFFFh
0x1400a63f5  mov     rsi, [rsp+148h+var_A8+8]
0x1400a63fd  mov     rcx, [rsp+148h+var_98]
0x1400a6405  cmp     rsi, rcx
0x1400a6408  jz      short loc_1400A645A
0x1400a640a  mov     [rsi], rbx
0x1400a640d  test    rbx, rbx
0x1400a6410  jz      short loc_1400A6421
0x1400a6412  mov     rax, [rbx]
0x1400a6415  mov     rcx, rbx
0x1400a6418  mov     rax, [rax+8]
0x1400a641c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a6421  add     [rsp+148h+var_A8+8], 8
0x1400a642a  test    rbx, rbx
0x1400a642d  jz      short loc_1400A643F
0x1400a642f  mov     rax, [rbx]
0x1400a6432  mov     rcx, rbx
0x1400a6435  mov     rax, [rax+10h]
0x1400a6439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a643e  nop
0x1400a643f  mov     rdx, [rsp+148h+var_40]
0x1400a6447  cmp     rdx, 7
0x1400a644b  ja      loc_1400A65CF
0x1400a6451  add     rdi, 40h ; '@'
0x1400a6455  jmp     loc_1400A6124
0x1400a645a  mov     r14, rsi
0x1400a645d  sub     r14, [rsp+148h+var_A8]
0x1400a6465  sar     r14, 3
0x1400a6469  cmp     r14, r15
0x1400a646c  jz      loc_1400A67A0
0x1400a6472  lea     r8, [r14+1]
0x1400a6476  mov     [rsp+148h+var_108], r8
0x1400a647b  sub     rcx, [rsp+148h+var_A8]
0x1400a6483  sar     rcx, 3
0x1400a6487  mov     rdx, rcx
0x1400a648a  shr     rdx, 1
0x1400a648d  mov     rax, r15
0x1400a6490  sub     rax, rdx
0x1400a6493  cmp     rcx, rax
0x1400a6496  ja      loc_1400A6AAB
0x1400a649c  lea     r12, [rdx+rcx]
0x1400a64a0  cmp     r12, r8
0x1400a64a3  cmovb   r12, r8
0x1400a64a7  mov     rcx, r12
0x1400a64aa  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x1400a64af  mov     rcx, rax
0x1400a64b2  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1400a64b7  mov     r15, rax
0x1400a64ba  mov     [rax+r14*8], rbx
0x1400a64be  test    rbx, rbx
0x1400a64c1  jz      short loc_1400A64D2
0x1400a64c3  mov     rcx, [rbx]
0x1400a64c6  mov     rax, [rcx+8]
0x1400a64ca  mov     rcx, rbx
0x1400a64cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a64d2  mov     r8, [rsp+148h+var_A8+8]
0x1400a64da  mov     rdx, [rsp+148h+var_A8]
0x1400a64e2  mov     rcx, r15
0x1400a64e5  cmp     rsi, r8
0x1400a64e8  jz      loc_1400A66E8
0x1400a64ee  jmp     loc_1400A6781
0x1400a64f3  test    byte ptr [rdi+10h], 8
0x1400a64f7  jz      loc_1400A6ABA
0x1400a64fd  lea     rax, [rsp+148h+var_58]
0x1400a6505  cmp     [rsp+148h+var_40], 7
0x1400a650e  cmova   rax, qword ptr [rsp+148h+var_58]
0x1400a6517  mov     [rsp+148h+var_108], rax
0x1400a651c  lea     rcx, [rsp+148h+var_108]
0x1400a6521  call    ??$CreateInstance@PEBG@?$VmComMultiInstanceObject@VVmBridgedAdapter@@@Vml@@SAPEAVVmBridgedAdapter@@$$QEAPEBG@Z; Vml::VmComMultiInstanceObject<VmBridgedAdapter>::CreateInstance<ushort const *>(ushort const * &&)
0x1400a6526  test    rax, rax
0x1400a6529  jnz     loc_1400A66CA
0x1400a652f  mov     rbx, r12
0x1400a6532  mov     [rsp+148h+var_100], rbx
0x1400a6537  jmp     loc_1400A63F5
0x1400a653c  mov     rbx, r12
0x1400a653f  mov     [rsp+148h+var_110], rbx
0x1400a6544  mov     eax, edi
0x1400a6546  imul    rdx, rax, 0A34h
0x1400a654d  add     rdx, [rsp+148h+var_B8]
  ... truncated ...
```
