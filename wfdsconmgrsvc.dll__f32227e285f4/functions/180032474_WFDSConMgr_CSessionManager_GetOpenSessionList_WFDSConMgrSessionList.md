# WFDSConMgr::CSessionManager::GetOpenSessionList(_WFDSConMgrSessionList * *)

- ea: `0x180032474`
- end: `0x180032f7b`
- name: `?GetOpenSessionList@CSessionManager@WFDSConMgr@@QEBAXPEAPEAU_WFDSConMgrSessionList@@@Z`
- size: `2823`
- prototype: `void __fastcall(WFDSConMgr::CSessionManager *__hidden this, struct _WFDSConMgrSessionList **)`
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c0b4`

## callees

- `0x180002600`
- `0x180002ffc`
- `0x18000444e`
- `0x18000475c`
- `0x180004c7c`
- `0x180004ca8`
- `0x18000665c`
- `0x180006740`
- `0x180006780`
- `0x18000a010`
- `0x18000f120`
- `0x18001a21c`
- `0x18002fb60`
- `0x1800300d4`
- `0x180030258`
- `0x1800306a0`
- `0x18003089c`
- `0x180030b34`
- `0x180032474`
- `0x1800353e0`
- `0x18003588c`
- `0x18003595c`
- `0x18003a100`
- `0x18003a14c`
- `0x18003a274`
- `0x18003a684`
- `0x18003e4f4`
- `0x18003e580`
- `0x18005c888`
- `0x18005f95c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180032f4b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180032f4b`

## string_xrefs

- `0x1800328e9`: `Attempting to set session list offsets such that we will overflow`
- `0x180032e7c`: `Attempting to write to AEP list beyond end`
- `0x180032e1c`: `Attempting to write to status list beyond end`
- `0x1800324ef`: `GetOpenSessionList missing ppSessionList`
- `0x180032508`: `WFDSConMgr::CSessionManager::GetOpenSessionList`
- `0x180032769`: `WFDSConMgr::CSessionManager::GetOpenSessionList`
- `0x180032799`: `WFDSConMgr::CSessionManager::GetOpenSessionList`
- `0x1800327c9`: `WFDSConMgr::CSessionManager::GetOpenSessionList`
- `0x1800327f9`: `WFDSConMgr::CSessionManager::GetOpenSessionList`
- `0x180032829`: `WFDSConMgr::CSessionManager::GetOpenSessionList`
- `0x180032859`: `WFDSConMgr::CSessionManager::GetOpenSessionList`
- `0x180032889`: `WFDSConMgr::CSessionManager::GetOpenSessionList`
- `0x180032902`: `WFDSConMgr::CSessionManager::GetOpenSessionList`
- `0x18003293b`: `WFDSConMgr::CSessionManager::GetOpenSessionList`
- `0x18003296b`: `WFDSConMgr::CSessionManager::GetOpenSessionList`
- `0x18003299b`: `WFDSConMgr::CSessionManager::GetOpenSessionList`
- `0x1800329cb`: `WFDSConMgr::CSessionManager::GetOpenSessionList`
- `0x1800329fb`: `WFDSConMgr::CSessionManager::GetOpenSessionList`
- `0x180032e35`: `WFDSConMgr::CSessionManager::GetOpenSessionList`
- `0x180032e65`: `WFDSConMgr::CSessionManager::GetOpenSessionList`
- `0x180032e95`: `WFDSConMgr::CSessionManager::GetOpenSessionList`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall WFDSConMgr::CSessionManager::GetOpenSessionList(RTL_SRWLOCK *this, struct _WFDSConMgrSessionList **a2)
{
  struct _WFDSConMgrSessionList **v2; // r14
  unsigned int v4; // edi
  unsigned __int64 v5; // rdx
  unsigned int v6; // esi
  unsigned int v7; // r14d
  unsigned int v8; // ebx
  WFDSConMgr::Common *Ptr; // r12
  WFDSConMgr::Common *v10; // rax
  WFDSConMgr::CRemoteDevice *v11; // r13
  unsigned __int64 v12; // rax
  struct WFDSConMgr::CMiracastHelper *MiracastHelper; // rax
  struct WFDSConMgr::CMaUsbHelper *MaUsbHelper; // rax
  unsigned __int64 v15; // r13
  unsigned int v16; // eax
  unsigned __int64 v17; // rsi
  __int64 v18; // rax
  unsigned int v19; // r13d
  unsigned int v20; // esi
  unsigned int v21; // eax
  unsigned int v22; // r12d
  unsigned int *v23; // rax
  void *v24; // rdx
  struct _WFDSConMgrSessionList *v25; // rbx
  int *v26; // r13
  _QWORD *v27; // rax
  _QWORD *v28; // rcx
  int v29; // edi
  WFDSConMgr::CRemoteDevice *v30; // r14
  int v31; // ecx
  __int64 v32; // rax
  const void *v33; // rax
  size_t v34; // r8
  struct WFDSConMgr::CSessionStateMachine *StateMachine; // rax
  WFDSConMgr::CRemoteDevice **v36; // rax
  unsigned int v37; // esi
  unsigned int v38; // r14d
  __int64 v39; // rax
  __int64 v40; // rdi
  __int64 v41; // rax
  __int64 v42; // rax
  unsigned int v43; // r10d
  int v44; // r11d
  __int64 v45; // rsi
  int v46; // edx
  __int64 v47; // rdi
  struct WFDSConMgr::CSessionStateMachine *v48; // rax
  unsigned int v49; // r9d
  int v50; // eax
  const void *v51; // rax
  __int64 v52; // r9
  size_t v53; // r8
  __int64 v54; // rax
  __int64 v55; // r8
  struct WFDSConMgr::CSessionStateMachine *v56; // rax
  unsigned int v57; // r9d
  int v58; // eax
  const void *v59; // rax
  __int64 v60; // r9
  size_t v61; // r8
  __int64 v62; // rax
  __int64 v63; // r8
  PVOID *v64; // rcx
  char v65; // [rsp+38h] [rbp-C8h]
  unsigned int v66; // [rsp+50h] [rbp-B0h]
  unsigned int v67; // [rsp+50h] [rbp-B0h]
  unsigned int v68; // [rsp+50h] [rbp-B0h]
  int v69; // [rsp+54h] [rbp-ACh] BYREF
  int v70; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v71; // [rsp+60h] [rbp-A0h]
  WFDSConMgr::Common *v72; // [rsp+68h] [rbp-98h] BYREF
  WFDSConMgr::CRemoteDevice *v73[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v74; // [rsp+80h] [rbp-80h]
  __int128 v75; // [rsp+88h] [rbp-78h] BYREF
  struct _WFDSConMgrSessionList **v76; // [rsp+98h] [rbp-68h]
  WFDSConMgr::CRemoteDevice *v77; // [rsp+A0h] [rbp-60h] BYREF
  std::_Ref_count_base *v78; // [rsp+A8h] [rbp-58h]
  _QWORD *i; // [rsp+B0h] [rbp-50h]
  __int64 v80; // [rsp+B8h] [rbp-48h]
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-40h] BYREF
  char v82; // [rsp+C8h] [rbp-38h]
  __int64 v83; // [rsp+D0h] [rbp-30h] BYREF
  std::_Ref_count_base *v84; // [rsp+D8h] [rbp-28h]
  _BYTE v85[16]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v86; // [rsp+F8h] [rbp-8h]
  _BYTE v87[16]; // [rsp+108h] [rbp+8h] BYREF
  unsigned int v88; // [rsp+118h] [rbp+18h]
  _BYTE v89[32]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v90[40]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v91[32]; // [rsp+170h] [rbp+70h] BYREF
  int v92; // [rsp+190h] [rbp+90h]
  int v93; // [rsp+194h] [rbp+94h]
  char v94[32]; // [rsp+198h] [rbp+98h] BYREF
  int v95; // [rsp+1B8h] [rbp+B8h]
  int v96; // [rsp+1BCh] [rbp+BCh]
  int v97; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v98[88]; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v99[80]; // [rsp+220h] [rbp+120h] BYREF

  v2 = a2;
  v76 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_1ed754397b2a39d314f3beddc0f07fb6_Traceguids, this);
  }
  if ( !v2 )
    WFDSConMgr::CException::Throw(
      87,
      "WFDSConMgr::CSessionManager::GetOpenSessionList",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
      16,
      L"GetOpenSessionList missing ppSessionList",
      this);
  *v2 = 0;
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(
    (__int64)&SRWLock,
    this + 2);
  v80 = ((char *)this[6].Ptr - (char *)this[5].Ptr) >> 4;
  v4 = v80;
  v75 = 0;
  std::_Tree_std::_Tmap_traits_unsigned_long__WFDSConMgr::CSessionManager::GetOpenSessionList_::_2_::DeviceInterfaceIdPair_std::less_unsigned_long__std::allocator_std::pair_unsigned_long_const___WFDSConMgr::CSessionManager::GetOpenSessionList_::_2_::DeviceInterfaceIdPair____0___::_Alloc_sentinel_and_proxy(&v75);
  if ( v4 )
  {
    v71 = 28LL * v4;
    if ( v71 > 0xFFFFFFFF )
      WFDSConMgr::CException::Throw(
        22,
        "WFDSConMgr::CSessionManager::GetOpenSessionList",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
        62,
        L"Overflow in calculating cbSessionDataSize",
        this);
    v6 = 0;
    v7 = 0;
    v8 = 0;
    Ptr = (WFDSConMgr::Common *)this[5].Ptr;
    v10 = (WFDSConMgr::Common *)this[6].Ptr;
    v72 = v10;
    while ( Ptr != v10 )
    {
      std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(v73, Ptr);
      v11 = v73[0];
      v12 = 2LL
          * (unsigned int)(*(_DWORD *)((*(__int64 (__fastcall **)(WFDSConMgr::CRemoteDevice *))(*(_QWORD *)v73[0] + 40LL))(v73[0])
                                     + 16)
                         + 1);
      if ( v12 > 0xFFFFFFFF )
        WFDSConMgr::CException::Throw(
          22,
          "WFDSConMgr::CSessionManager::GetOpenSessionList",
          "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
          72,
          L"Overflow in calculating cbSessionDataSize",
          this);
      v70 = v6 + v12;
      if ( v6 + (unsigned int)v12 < v6 )
        WFDSConMgr::CException::Throw(
          22,
          "WFDSConMgr::CSessionManager::GetOpenSessionList",
          "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
          75,
          L"Overflow in calculating cbAepIdSize",
          this);
      if ( v7 + 32 < v7 )
        WFDSConMgr::CException::Throw(
          22,
          "WFDSConMgr::CSessionManager::GetOpenSessionList",
          "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
          78,
          L"Overflow in calculating cbTransportListSize",
          this);
      MiracastHelper = WFDSConMgr::CRemoteDevice::GetMiracastHelper(v11);
      std::wstring::wstring(v87, (char *)MiracastHelper + 224);
      MaUsbHelper = WFDSConMgr::CRemoteDevice::GetMaUsbHelper(v11);
      std::wstring::wstring(v85, (char *)MaUsbHelper + 280);
      v15 = 2LL * v88;
      if ( v15 > 0xFFFFFFFF )
        WFDSConMgr::CException::Throw(
          22,
          "WFDSConMgr::CSessionManager::GetOpenSessionList",
          "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
          90,
          L"Overflow in calculating cbMiracastDisplayDeviceInterfaceId",
          this);
      v16 = v8 + v15;
      if ( v8 + (unsigned int)v15 < v8 )
        WFDSConMgr::CException::Throw(
          22,
          "WFDSConMgr::CSessionManager::GetOpenSessionList",
          "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
          93,
          L"Overflow in calculating cbDeviceInterfaceIdListSize+cbMiracastDisplayDeviceInterfaceId",
          this);
      v17 = 2LL * (unsigned int)v86;
      if ( v17 > 0xFFFFFFFF )
        WFDSConMgr::CException::Throw(
          22,
          "WFDSConMgr::CSessionManager::GetOpenSessionList",
          "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
          96,
          L"Overflow in calculating cbMiracastDisplayDeviceInterfaceId",
          this);
      v8 = v17 + v16;
      if ( (unsigned int)v17 + v16 < v16 )
        WFDSConMgr::CException::Throw(
          22,
          "WFDSConMgr::CSessionManager::GetOpenSessionList",
          "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
          99,
          L"Overflow in calculating cbDeviceInterfaceIdListSize+cbMaUsbDeviceInterfaceId",
          this);
      v7 += 32;
      memset_0(v99, 0, sizeof(v99));
      std::wstring::wstring(v91, v87);
      v92 = v15;
      v93 = 0;
      std::wstring::wstring(v94, v85);
      v95 = v17;
      v96 = 0;
      v18 = WFDSConMgr::CSessionManager::GetOpenSessionList_::_2_::DeviceInterfaceIdPair::DeviceInterfaceIdPair(
              v99,
              v91);
      v97 = *((_DWORD *)v73[0] + 10);
      WFDSConMgr::CSessionManager::GetOpenSessionList_::_2_::DeviceInterfaceIdPair::DeviceInterfaceIdPair(v98, v18);
      std::_Tree_std::_Tmap_traits_unsigned_long__WFDSConMgr::CSessionManager::GetOpenSessionList_::_2_::DeviceInterfaceIdPair_std::less_unsigned_long__std::allocator_std::pair_unsigned_long_const___WFDSConMgr::CSessionManager::GetOpenSessionList_::_2_::DeviceInterfaceIdPair____0___::_Emplace_std::pair_unsigned_long__WFDSConMgr::CSessionManager::GetOpenSessionList_::_2_::DeviceInterfaceIdPair___(
        &v75,
        &v83,
        &v97);
      WFDSConMgr::CSessionManager::GetOpenSessionList_::_2_::DeviceInterfaceIdPair::_DeviceInterfaceIdPair(v98);
      WFDSConMgr::CSessionManager::GetOpenSessionList_::_2_::DeviceInterfaceIdPair::_DeviceInterfaceIdPair(v99);
      WFDSConMgr::CSessionManager::GetOpenSessionList_::_2_::DeviceInterfaceIdPair::_DeviceInterfaceIdPair(v91);
      std::wstring::_Tidy_deallocate(v85);
      std::wstring::_Tidy_deallocate(v87);
      if ( v73[1] )
        std::_Ref_count_base::_Decref(v73[1]);
      Ptr = (WFDSConMgr::Common *)((char *)Ptr + 16);
      v6 = v70;
      v10 = v72;
    }
    v19 = v71 + 12;
    v69 = v71 + 12;
    if ( (unsigned int)v71 >= 0xFFFFFFF4 )
      WFDSConMgr::CException::Throw(
        22,
        "WFDSConMgr::CSessionManager::GetOpenSessionList",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
        108,
        L"Overflow in calculating cbTotalSizeNeeded (cbSessionDataSize)",
        this);
    v20 = v19 + v6;
    v70 = v20;
    if ( v20 < v19 )
      WFDSConMgr::CException::Throw(
        22,
        "WFDSConMgr::CSessionManager::GetOpenSessionList",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
        110,
        L"Overflow in calculating cbTotalSizeNeeded (cbAepIdSize)",
        this);
    v21 = v20 + v7;
    if ( v20 + v7 < v20 )
      WFDSConMgr::CException::Throw(
        22,
        "WFDSConMgr::CSessionManager::GetOpenSessionList",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
        112,
        L"Overflow in calculating cbTotalSizeNeeded (cbTransportListSize)",
        this);
    v22 = v21 + v8;
    if ( v21 + v8 < v21 )
      WFDSConMgr::CException::Throw(
        22,
        "WFDSConMgr::CSessionManager::GetOpenSessionList",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
        114,
        L"Overflow in calculating cbTotalSizeNeeded (cbDeviceInterfaceIdListSize)",
        this);
    if ( v7 + v20 + v8 > v22 )
      WFDSConMgr::CException::Throw(
        22,
        "WFDSConMgr::CSessionManager::GetOpenSessionList",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
        123,
        L"Attempting to set session list offsets such that we will overflow",
        this);
    v2 = v76;
  }
  else
  {
    v22 = 12;
    v20 = 12;
    v70 = 12;
    v69 = 12;
  }
  v23 = (unsigned int *)WFDSConMgr::Common::AllocExternalMemory((WFDSConMgr::Common *)v22, v5);
  v25 = (struct _WFDSConMgrSessionList *)v23;
  v72 = (WFDSConMgr::Common *)v23;
  *(_BYTE *)v23 = 1;
  v23[1] = v22;
  v23[2] = v4;
  if ( v4 )
  {
    v66 = v20;
    v26 = (int *)(v23 + 3);
    v27 = this[5].Ptr;
    v28 = this[6].Ptr;
    for ( i = v28; ; v28 = i )
    {
      v71 = (unsigned __int64)v27;
      if ( v27 == v28 )
        break;
      std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(&v77, v27);
      v29 = v69;
      *v26 = v69;
      v30 = v77;
      v31 = 2 * *(_DWORD *)((*(__int64 (__fastcall **)(WFDSConMgr::CRemoteDevice *))(*(_QWORD *)v77 + 40LL))(v77) + 16)
          + 2;
      v26[1] = v31;
      if ( *v26 + v31 > v20 )
        WFDSConMgr::CException::Throw(
          22,
          "WFDSConMgr::CSessionManager::GetOpenSessionList",
          "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
          156,
          L"Attempting to write to AEP list beyond end",
          this);
      v32 = (*(__int64 (__fastcall **)(WFDSConMgr::CRemoteDevice *))(*(_QWORD *)v30 + 40LL))(v30);
      v33 = (const void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
      memcpy_0((char *)v25 + (unsigned int)*v26, v33, v34);
      v74 = v26[1];
      StateMachine = WFDSConMgr::CRemoteDevice::GetStateMachine(v30);
      v26[2] = WFDSConMgr::CSessionStateMachine::GetWFDState(StateMachine);
      v36 = (WFDSConMgr::CRemoteDevice **)std::make_shared<WFDSConMgr::CFakeImpersonationProvider,>(&v83);
      *(_OWORD *)v73 = 0;
      v73[0] = *v36;
      v73[1] = v36[1];
      *v36 = 0;
      v36[1] = 0;
      v26[3] = WFDSConMgr::CRemoteDevice::GetRemoteInputState(v30);
      if ( v84 )
        std::_Ref_count_base::_Decref(v84);
      v26[5] = 2;
      v26[4] = v66;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v37 = v26[3];
        v38 = v26[2];
        v39 = (*(__int64 (__fastcall **)(WFDSConMgr::CRemoteDevice *))(*(_QWORD *)v77 + 40LL))(v77);
        v40 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39);
        v41 = (*(__int64 (__fastcall **)(WFDSConMgr::CRemoteDevice *))(*(_QWORD *)v77 + 32LL))(v77);
        v42 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
        v65 = v38;
        v30 = v77;
        WPP_SF_qqSSLL(*((_QWORD *)WPP_GLOBAL_Control + 2), (char)v77, v42, v40, v65, v37);
        v29 = v69;
      }
      v69 = *((_DWORD *)v30 + 10);
      std::_Tree_std::_Tmap_traits_unsigned_long__WFDSConMgr::CSessionManager::GetOpenSessionList_::_2_::DeviceInterfaceIdPair_std::less_unsigned_long__std::allocator_std::pair_unsigned_long_const___WFDSConMgr::CSessionManager::GetOpenSessionList_::_2_::DeviceInterfaceIdPair____0___::_Find_lower_bound_unsigned_long_(
        &v75,
        v85,
        &v69);
      v45 = v86;
      if ( *(_BYTE *)(v86 + 25) || v43 < *(_DWORD *)(v86 + 32) )
        v45 = v75;
      if ( v45 == (_QWORD)v75 )
        WFDSConMgr::CException::Throw(
          159,
          "WFDSConMgr::CSessionManager::GetOpenSessionList",
          "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
          194,
          L"Could not find device interfaces for device, something went wrong in the size calculation phase",
          this);
      v46 = *(_DWORD *)(v45 + 72) + *(_DWORD *)(v45 + 112) + 32;
      v26[6] = v46;
      if ( v46 + v44 > v22 )
        WFDSConMgr::CException::Throw(
          22,
          "WFDSConMgr::CSessionManager::GetOpenSessionList",
          "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
          202,
          L"Attempting to write to status list beyond end",
          this);
      v69 = v74 + v29;
      std::wstring::wstring(v90, v45 + 40);
      std::wstring::wstring(v89, v45 + 80);
      v67 = v66 + 32;
      v47 = (unsigned int)v26[4];
      *(_DWORD *)((char *)v25 + v47) = 1;
      v48 = WFDSConMgr::CRemoteDevice::GetStateMachine(v30);
      *(_DWORD *)((char *)v25 + v47 + 4) = WFDSConMgr::CSessionStateMachine::GetStackState(v48, 1);
      v49 = v67;
      *(_DWORD *)((char *)v25 + v47 + 8) = v67;
      v50 = *(_DWORD *)(v45 + 72);
      *(_DWORD *)((char *)v25 + v47 + 12) = v50;
      if ( v50 )
      {
        v51 = (const void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
        memcpy_0((char *)v25 + v52, v51, v53);
        v49 = v67;
      }
      v68 = v49 + *(_DWORD *)((char *)v25 + v47 + 12);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v54 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
        WPP_SF_qqLLS(
          *(_QWORD *)(v55 + 16),
          19,
          v55,
          (_DWORD)this,
          (char)v30,
          *(_DWORD *)((char *)v25 + v47),
          *(_DWORD *)((char *)v25 + v47 + 4),
          v54);
      }
      *(_DWORD *)((char *)v25 + v47 + 16) = 2;
      v56 = WFDSConMgr::CRemoteDevice::GetStateMachine(v30);
      *(_DWORD *)((char *)v25 + v47 + 20) = WFDSConMgr::CSessionStateMachine::GetStackState(v56, 2);
      v57 = v68;
      *(_DWORD *)((char *)v25 + v47 + 24) = v68;
      v58 = *(_DWORD *)(v45 + 112);
      *(_DWORD *)((char *)v25 + v47 + 28) = v58;
      if ( v58 )
      {
        v59 = (const void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v89);
        memcpy_0((char *)v25 + v60, v59, v61);
        v57 = v68;
      }
      v66 = v57 + *(_DWORD *)((char *)v25 + v47 + 28);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v62 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v89);
        WPP_SF_qqLLS(
          *(_QWORD *)(v63 + 16),
          20,
          v63,
          (_DWORD)this,
          (char)v30,
          *(_DWORD *)((char *)v25 + v47 + 16),
          *(_DWORD *)((char *)v25 + v47 + 20),
          v62);
      }
      v26 += 7;
      std::wstring::_Tidy_deallocate(v89);
      std::wstring::_Tidy_deallocate(v90);
      if ( v78 )
        std::_Ref_count_base::_Decref(v78);
      v27 = (_QWORD *)(v71 + 16);
      v20 = v70;
    }
    v4 = v80;
    v2 = v76;
  }
  v72 = 0;
  *v2 = v25;
  v64 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_1ed754397b2a39d314f3beddc0f07fb6_Traceguids, this, v4);
      v64 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v64 != &WPP_GLOBAL_Control && *((_BYTE *)v64 + 25) >= 4u && (*((_BYTE *)v64 + 28) & 1) != 0 )
      WPP_SF_q(v64[2], 22, &WPP_1ed754397b2a39d314f3beddc0f07fb6_Traceguids, this);
  }
  std::unique_ptr<unsigned char [0],WFDSConMgr::Common::FreeDeleter>::~unique_ptr<unsigned char [0],WFDSConMgr::Common::FreeDeleter>(
    &v72,
    v24);
  std::_Tree_std::_Tmap_traits_unsigned_long__WFDSConMgr::CSessionManager::GetOpenSessionList_::_2_::DeviceInterfaceIdPair_std::less_unsigned_long__std::allocator_std::pair_unsigned_long_const___WFDSConMgr::CSessionManager::GetOpenSessionList_::_2_::DeviceInterfaceIdPair____0___::__Tree_std::_Tmap_traits_unsigned_long__WFDSConMgr::CSessionManager::GetOpenSessionList_::_2_::DeviceInterfaceIdPair_std::less_unsigned_long__std::allocator_std::pair_unsigned_long_const___WFDSConMgr::CSessionManager::GetOpenSessionList_::_2_::DeviceInterfaceIdPair____0___(&v75);
  if ( v82 && SRWLock )
    ReleaseSRWLockShared(SRWLock);
}

```

## disassembly

```asm
0x180032474  mov     [rsp-8+arg_10], rbx
0x180032479  push    rbp
0x18003247a  push    rsi
0x18003247b  push    rdi
0x18003247c  push    r12
0x18003247e  push    r13
0x180032480  push    r14
0x180032482  push    r15
0x180032484  lea     rbp, [rsp-180h]
0x18003248c  sub     rsp, 280h
0x180032493  mov     rax, cs:__security_cookie
0x18003249a  xor     rax, rsp
0x18003249d  mov     [rbp+1B0h+var_40], rax
0x1800324a4  mov     r14, rdx
0x1800324a7  mov     [rbp+1B0h+var_218], rdx
0x1800324ab  mov     r15, rcx
0x1800324ae  lea     rax, WPP_GLOBAL_Control
0x1800324b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800324bc  cmp     rcx, rax
0x1800324bf  jz      short loc_1800324E5
0x1800324c1  cmp     byte ptr [rcx+19h], 4
0x1800324c5  jb      short loc_1800324E5
0x1800324c7  test    byte ptr [rcx+1Ch], 1
0x1800324cb  jz      short loc_1800324E5
0x1800324cd  mov     edx, 11h
0x1800324d2  mov     r9, r15
0x1800324d5  lea     r8, WPP_1ed754397b2a39d314f3beddc0f07fb6_Traceguids
0x1800324dc  mov     rcx, [rcx+10h]
0x1800324e0  call    WPP_SF_q
0x1800324e5  test    r14, r14
0x1800324e8  jnz     short loc_18003251A
0x1800324ea  mov     [rsp+2B0h+var_288], r15; void *
0x1800324ef  lea     rax, aGetopensession_0; "GetOpenSessionList missing ppSessionLis"...
0x1800324f6  mov     [rsp+2B0h+var_290], rax; unsigned __int16 *
0x1800324fb  mov     r9d, 110h; char
0x180032501  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180032508  lea     rdx, aWfdsconmgrCses_11; "WFDSConMgr::CSessionManager::GetOpenSes"...
0x18003250f  mov     ecx, 80070057h; char
0x180032514  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18003251a  mov     qword ptr [r14], 0
0x180032521  lea     rdx, [r15+10h]
0x180032525  lea     rcx, [rbp+1B0h+SRWLock]
0x180032529  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$00@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(WFDSConMgr::ReadersWriterLock &)
0x18003252e  nop
0x18003252f  mov     rdi, [r15+30h]
0x180032533  sub     rdi, [r15+28h]
0x180032537  sar     rdi, 4
0x18003253b  mov     [rbp+1B0h+var_1F8], rdi
0x18003253f  xorps   xmm0, xmm0
0x180032542  movdqu  [rbp+1B0h+var_228], xmm0
0x180032547  lea     rcx, [rbp+1B0h+var_228]
0x18003254b  call    std___Tree_std___Tmap_traits_unsigned_long__WFDSConMgr__CSessionManager__GetOpenSessionList____2___DeviceInterfaceIdPair_std__less_unsigned_long__std__allocator_std__pair_unsigned_long_const___WFDSConMgr__CSessionManager__GetOpenSessionList____2___DeviceInterfaceIdPair____0______Alloc_sentinel_and_proxy
0x180032550  nop
0x180032551  test    edi, edi
0x180032553  jz      loc_180032A0D
0x180032559  mov     eax, edi
0x18003255b  imul    rax, 1Ch
0x18003255f  mov     [rsp+2B0h+var_250], rax
0x180032564  mov     ecx, 0FFFFFFFFh
0x180032569  cmp     rax, rcx
0x18003256c  ja      loc_1800329DD
0x180032572  xor     esi, esi
0x180032574  xor     r14d, r14d
0x180032577  xor     ebx, ebx
0x180032579  mov     r12, [r15+28h]
0x18003257d  mov     rax, [r15+30h]
0x180032581  mov     [rsp+2B0h+var_248], rax
0x180032586  cmp     r12, rax
0x180032589  jz      loc_18003289B
0x18003258f  mov     rdx, r12
0x180032592  lea     rcx, [rsp+2B0h+var_240]
0x180032597  call    ??0?$shared_ptr@VIConfigHelper@WFDSConMgr@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(std::shared_ptr<WFDSConMgr::IConfigHelper> const &)
0x18003259c  nop
0x18003259d  mov     r13, [rsp+2B0h+var_240]
0x1800325a2  mov     rax, [r13+0]
0x1800325a6  mov     rcx, r13
0x1800325a9  mov     rax, [rax+28h]
0x1800325ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325b2  mov     eax, [rax+10h]
0x1800325b5  inc     eax
0x1800325b7  add     rax, rax
0x1800325ba  mov     ecx, 0FFFFFFFFh
0x1800325bf  cmp     rax, rcx
0x1800325c2  ja      loc_18003286B
0x1800325c8  add     eax, esi
0x1800325ca  mov     [rsp+2B0h+var_258], eax
0x1800325ce  cmp     eax, esi
0x1800325d0  jb      loc_18003283B
0x1800325d6  lea     eax, [r14+20h]
0x1800325da  mov     [rsp+2B0h+var_260], eax
0x1800325de  cmp     eax, r14d
0x1800325e1  jb      loc_18003280B
0x1800325e7  mov     rcx, r13; this
0x1800325ea  call    ?GetMiracastHelper@CRemoteDevice@WFDSConMgr@@QEAAAEAVCMiracastHelper@2@XZ; WFDSConMgr::CRemoteDevice::GetMiracastHelper(void)
0x1800325ef  lea     rdx, [rax+0E0h]
0x1800325f6  lea     rcx, [rbp+1B0h+var_1A8]
0x1800325fa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800325ff  nop
0x180032600  mov     rcx, r13; this
0x180032603  call    ?GetMaUsbHelper@CRemoteDevice@WFDSConMgr@@QEAAAEAVCMaUsbHelper@2@XZ; WFDSConMgr::CRemoteDevice::GetMaUsbHelper(void)
0x180032608  lea     rdx, [rax+118h]
0x18003260f  lea     rcx, [rbp+1B0h+var_1C8]
0x180032613  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180032618  nop
0x180032619  mov     r13d, [rbp+1B0h+var_198]
0x18003261d  add     r13, r13
0x180032620  mov     ecx, 0FFFFFFFFh
0x180032625  cmp     r13, rcx
0x180032628  ja      loc_1800327DB
0x18003262e  lea     eax, [rbx+r13]
0x180032632  cmp     eax, ebx
0x180032634  jb      loc_1800327AB
0x18003263a  mov     esi, dword ptr [rbp+1B0h+var_1B8]
0x18003263d  add     rsi, rsi
0x180032640  cmp     rsi, rcx
0x180032643  ja      loc_18003277B
0x180032649  lea     ebx, [rsi+rax]
0x18003264c  cmp     ebx, eax
0x18003264e  jb      loc_18003274B
0x180032654  mov     eax, [rsp+2B0h+var_258]
0x180032658  mov     [rsp+2B0h+var_258], eax
0x18003265c  mov     r14d, [rsp+2B0h+var_260]
0x180032661  xor     edx, edx; Val
0x180032663  lea     r8d, [rdx+50h]; Size
0x180032667  lea     rcx, [rbp+1B0h+var_90]; void *
0x18003266e  call    memset_0
0x180032673  lea     rdx, [rbp+1B0h+var_1A8]
0x180032677  lea     rcx, [rbp+1B0h+var_140]
0x18003267b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180032680  nop
0x180032681  mov     [rbp+1B0h+var_120], r13d
0x180032688  xor     eax, eax
0x18003268a  mov     [rbp+1B0h+var_11C], eax
0x180032690  lea     rdx, [rbp+1B0h+var_1C8]
0x180032694  lea     rcx, [rbp+1B0h+var_118]
0x18003269b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800326a0  mov     [rbp+1B0h+var_F8], esi
0x1800326a6  xor     eax, eax
0x1800326a8  mov     [rbp+1B0h+var_F4], eax
0x1800326ae  lea     rdx, [rbp+1B0h+var_140]
0x1800326b2  lea     rcx, [rbp+1B0h+var_90]
0x1800326b9  call    _WFDSConMgr__CSessionManager__GetOpenSessionList____2___DeviceInterfaceIdPair__DeviceInterfaceIdPair
0x1800326be  nop
0x1800326bf  mov     rcx, [rsp+2B0h+var_240]
0x1800326c4  mov     ecx, [rcx+28h]
0x1800326c7  mov     [rbp+1B0h+var_F0], ecx
0x1800326cd  mov     rdx, rax
0x1800326d0  lea     rcx, [rbp+1B0h+var_E8]
0x1800326d7  call    _WFDSConMgr__CSessionManager__GetOpenSessionList____2___DeviceInterfaceIdPair__DeviceInterfaceIdPair
0x1800326dc  nop
0x1800326dd  lea     r8, [rbp+1B0h+var_F0]
0x1800326e4  lea     rdx, [rbp+1B0h+var_1E0]
0x1800326e8  lea     rcx, [rbp+1B0h+var_228]
0x1800326ec  call    std___Tree_std___Tmap_traits_unsigned_long__WFDSConMgr__CSessionManager__GetOpenSessionList____2___DeviceInterfaceIdPair_std__less_unsigned_long__std__allocator_std__pair_unsigned_long_const___WFDSConMgr__CSessionManager__GetOpenSessionList____2___DeviceInterfaceIdPair____0______Emplace_std__pair_unsigned_long__WFDSConMgr__CSessionManager__GetOpenSessionList____2___DeviceInterfaceIdPair___
0x1800326f1  nop
0x1800326f2  lea     rcx, [rbp+1B0h+var_E8]
0x1800326f9  call    _WFDSConMgr__CSessionManager__GetOpenSessionList____2___DeviceInterfaceIdPair___DeviceInterfaceIdPair
0x1800326fe  nop
0x1800326ff  lea     rcx, [rbp+1B0h+var_90]
0x180032706  call    _WFDSConMgr__CSessionManager__GetOpenSessionList____2___DeviceInterfaceIdPair___DeviceInterfaceIdPair
0x18003270b  nop
0x18003270c  lea     rcx, [rbp+1B0h+var_140]
0x180032710  call    _WFDSConMgr__CSessionManager__GetOpenSessionList____2___DeviceInterfaceIdPair___DeviceInterfaceIdPair
0x180032715  nop
0x180032716  lea     rcx, [rbp+1B0h+var_1C8]
0x18003271a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003271f  nop
0x180032720  lea     rcx, [rbp+1B0h+var_1A8]
0x180032724  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180032729  nop
0x18003272a  mov     rcx, [rsp+2B0h+var_240+8]; this
0x18003272f  test    rcx, rcx
0x180032732  jz      short loc_180032739
0x180032734  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032739  add     r12, 10h
0x18003273d  mov     esi, [rsp+2B0h+var_258]
0x180032741  mov     rax, [rsp+2B0h+var_248]
0x180032746  jmp     loc_180032586
0x18003274b  mov     [rsp+2B0h+var_288], r15; void *
0x180032750  lea     rax, aOverflowInCalc_11; "Overflow in calculating cbDeviceInterfa"...
0x180032757  mov     [rsp+2B0h+var_290], rax; unsigned __int16 *
0x18003275c  mov     r9d, 163h; char
0x180032762  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180032769  lea     rdx, aWfdsconmgrCses_11; "WFDSConMgr::CSessionManager::GetOpenSes"...
0x180032770  mov     ecx, 80070216h; char
0x180032775  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18003277b  mov     [rsp+2B0h+var_288], r15; void *
0x180032780  lea     rax, aOverflowInCalc_9; "Overflow in calculating cbMiracastDispl"...
0x180032787  mov     [rsp+2B0h+var_290], rax; unsigned __int16 *
0x18003278c  mov     r9d, 160h; char
0x180032792  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180032799  lea     rdx, aWfdsconmgrCses_11; "WFDSConMgr::CSessionManager::GetOpenSes"...
0x1800327a0  mov     ecx, 80070216h; char
0x1800327a5  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800327ab  mov     [rsp+2B0h+var_288], r15; void *
0x1800327b0  lea     rax, aOverflowInCalc_3; "Overflow in calculating cbDeviceInterfa"...
0x1800327b7  mov     [rsp+2B0h+var_290], rax; unsigned __int16 *
0x1800327bc  mov     r9d, 15Dh; char
0x1800327c2  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800327c9  lea     rdx, aWfdsconmgrCses_11; "WFDSConMgr::CSessionManager::GetOpenSes"...
0x1800327d0  mov     ecx, 80070216h; char
0x1800327d5  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800327db  mov     [rsp+2B0h+var_288], r15; void *
0x1800327e0  lea     rax, aOverflowInCalc_9; "Overflow in calculating cbMiracastDispl"...
0x1800327e7  mov     [rsp+2B0h+var_290], rax; unsigned __int16 *
0x1800327ec  mov     r9d, 15Ah; char
0x1800327f2  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800327f9  lea     rdx, aWfdsconmgrCses_11; "WFDSConMgr::CSessionManager::GetOpenSes"...
0x180032800  mov     ecx, 80070216h; char
0x180032805  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18003280b  mov     [rsp+2B0h+var_288], r15; void *
0x180032810  lea     rax, aOverflowInCalc_10; "Overflow in calculating cbTransportList"...
0x180032817  mov     [rsp+2B0h+var_290], rax; unsigned __int16 *
0x18003281c  mov     r9d, 14Eh; char
0x180032822  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180032829  lea     rdx, aWfdsconmgrCses_11; "WFDSConMgr::CSessionManager::GetOpenSes"...
0x180032830  mov     ecx, 80070216h; char
0x180032835  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18003283b  mov     [rsp+2B0h+var_288], r15; void *
0x180032840  lea     rax, aOverflowInCalc_4; "Overflow in calculating cbAepIdSize"
0x180032847  mov     [rsp+2B0h+var_290], rax; unsigned __int16 *
0x18003284c  mov     r9d, 14Bh; char
0x180032852  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180032859  lea     rdx, aWfdsconmgrCses_11; "WFDSConMgr::CSessionManager::GetOpenSes"...
0x180032860  mov     ecx, 80070216h; char
0x180032865  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18003286b  mov     [rsp+2B0h+var_288], r15; void *
0x180032870  lea     rax, aOverflowInCalc; "Overflow in calculating cbSessionDataSi"...
0x180032877  mov     [rsp+2B0h+var_290], rax; unsigned __int16 *
0x18003287c  mov     r9d, 148h; char
0x180032882  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180032889  lea     rdx, aWfdsconmgrCses_11; "WFDSConMgr::CSessionManager::GetOpenSes"...
0x180032890  mov     ecx, 80070216h; char
0x180032895  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18003289b  mov     r13, [rsp+2B0h+var_250]
0x1800328a0  add     r13d, 0Ch
0x1800328a4  mov     [rsp+2B0h+var_25C], r13d
0x1800328a9  mov     r12d, 0Ch
0x1800328af  cmp     r13d, r12d
0x1800328b2  jb      loc_1800329AD
0x1800328b8  add     esi, r13d
0x1800328bb  mov     [rsp+2B0h+var_258], esi
0x1800328bf  cmp     esi, r13d
0x1800328c2  jb      loc_18003297D
0x1800328c8  lea     eax, [rsi+r14]
0x1800328cc  cmp     eax, esi
0x1800328ce  jb      short loc_18003294D
0x1800328d0  lea     r12d, [rax+rbx]
0x1800328d4  cmp     r12d, eax
0x1800328d7  jb      short loc_18003291D
0x1800328d9  lea     eax, [rsi+rbx]
0x1800328dc  add     eax, r14d
0x1800328df  cmp     eax, r12d
0x1800328e2  jbe     short loc_180032914
0x1800328e4  mov     [rsp+2B0h+var_288], r15; void *
0x1800328e9  lea     rax, aAttemptingToSe; "Attempting to set session list offsets "...
0x1800328f0  mov     [rsp+2B0h+var_290], rax; unsigned __int16 *
0x1800328f5  mov     r9d, 17Bh; char
0x1800328fb  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180032902  lea     rdx, aWfdsconmgrCses_11; "WFDSConMgr::CSessionManager::GetOpenSes"...
0x180032909  mov     ecx, 80070216h; char
0x18003290e  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180032914  mov     r14, [rbp+1B0h+var_218]
0x180032918  jmp     loc_180032A20
0x18003291d  mov     [rsp+2B0h+var_288], r15; void *
0x180032922  lea     rax, aOverflowInCalc_8; "Overflow in calculating cbTotalSizeNeed"...
0x180032929  mov     [rsp+2B0h+var_290], rax; unsigned __int16 *
0x18003292e  mov     r9d, 172h; char
0x180032934  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18003293b  lea     rdx, aWfdsconmgrCses_11; "WFDSConMgr::CSessionManager::GetOpenSes"...
0x180032942  mov     ecx, 80070216h; char
0x180032947  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18003294d  mov     [rsp+2B0h+var_288], r15; void *
0x180032952  lea     rax, aOverflowInCalc_0; "Overflow in calculating cbTotalSizeNeed"...
0x180032959  mov     [rsp+2B0h+var_290], rax; unsigned __int16 *
0x18003295e  mov     r9d, 170h; char
0x180032964  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18003296b  lea     rdx, aWfdsconmgrCses_11; "WFDSConMgr::CSessionManager::GetOpenSes"...
0x180032972  mov     ecx, 80070216h; char
0x180032977  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18003297d  mov     [rsp+2B0h+var_288], r15; void *
0x180032982  lea     rax, aOverflowInCalc_12; "Overflow in calculating cbTotalSizeNeed"...
0x180032989  mov     [rsp+2B0h+var_290], rax; unsigned __int16 *
0x18003298e  mov     r9d, 16Eh; char
0x180032994  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18003299b  lea     rdx, aWfdsconmgrCses_11; "WFDSConMgr::CSessionManager::GetOpenSes"...
0x1800329a2  mov     ecx, 80070216h; char
0x1800329a7  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800329ad  mov     [rsp+2B0h+var_288], r15; void *
0x1800329b2  lea     rax, aOverflowInCalc_5; "Overflow in calculating cbTotalSizeNeed"...
0x1800329b9  mov     [rsp+2B0h+var_290], rax; unsigned __int16 *
0x1800329be  mov     r9d, 16Ch; char
0x1800329c4  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800329cb  lea     rdx, aWfdsconmgrCses_11; "WFDSConMgr::CSessionManager::GetOpenSes"...
0x1800329d2  mov     ecx, 80070216h; char
0x1800329d7  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800329dd  mov     [rsp+2B0h+var_288], r15; void *
0x1800329e2  lea     rax, aOverflowInCalc; "Overflow in calculating cbSessionDataSi"...
0x1800329e9  mov     [rsp+2B0h+var_290], rax; unsigned __int16 *
0x1800329ee  mov     r9d, 13Eh; char
  ... truncated ...
```
