# RegistryDeviceEnumerator::CreateUSDWrapper(CSimpleStringBase<ushort> const &)

- ea: `0x180049170`
- end: `0x180049e0d`
- name: `?CreateUSDWrapper@RegistryDeviceEnumerator@@UEAAPEAVUSDWrapper@@AEBV?$CSimpleStringBase@G@@@Z`
- size: `3229`
- prototype: `struct USDWrapper *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000f4fc`
- `0x180011338`
- `0x1800113d8`
- `0x18001148c`
- `0x180011638`
- `0x180011658`
- `0x1800119c8`
- `0x180011a94`
- `0x180011ad0`
- `0x18001247c`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033cc0`
- `0x180046630`
- `0x180048efc`
- `0x180049170`
- `0x18004a10c`
- `0x180078010`

## string_xrefs

- `0x18004924c`: `RegistryDeviceEnumerator::CreateUSDWrapper`
- `0x1800498b1`: `RegistryDeviceEnumerator::CreateUSDWrapper`
- `0x1800498f6`: `RegistryDeviceEnumerator::CreateUSDWrapper`
- `0x180049b3e`: `RegistryDeviceEnumerator::CreateUSDWrapper`
- `0x180049b7c`: `RegistryDeviceEnumerator::CreateUSDWrapper`
- `0x180049c11`: `RegistryDeviceEnumerator::CreateUSDWrapper`
- `0x180049cea`: `RegistryDeviceEnumerator::CreateUSDWrapper`
- `0x180049d1b`: `RegistryDeviceEnumerator::CreateUSDWrapper`
- `0x180049313`: `Unable to set USD type to Registry device type`
- `0x180049338`: `Unable to set USD type to Registry device type`
- `0x180049675`: `CreateFileName`
- `0x180049772`: `HardwareConfig`
- `0x180049892`: `Processing Registry information for device (%ws), known as (%ws)`
- `0x1800498cf`: `Processing Registry information for device (%ws), known as (%ws)`
- `0x180049b26`: `There was a problem opening the DeviceData subkey for the device (%ws), known as (%ws)`
- `0x180049b5c`: `There was a problem opening the DeviceData subkey for the device (%ws), known as (%ws)`
- `0x180049cd8`: `The Registry Device enumerator could not find the wrapper's USDInfo`
- `0x180049d01`: `The Registry Device enumerator could not find the wrapper's USDInfo`
- `0x180049c6c`: `The registry device %ws is regarded as REMOVED, therefore we are returning a NULL USDWrapper for it`
- `0x180049c97`: `The registry device %ws is regarded as REMOVED, therefore we are returning a NULL USDWrapper for it`
- `0x180049d87`: `The Volume Device Enumerator could not create a wrapper for (%ws)`
- `0x180049db2`: `The Volume Device Enumerator could not create a wrapper for (%ws)`
- `0x180049d38`: `The Registry Device enumerator could not create the device wrapper because we are out of memory`
- `0x180049d5a`: `The Registry Device enumerator could not create the device wrapper because we are out of memory`

## pseudocode

```c
struct USDWrapper *__fastcall RegistryDeviceEnumerator::CreateUSDWrapper(__int64 a1, __int64 a2)
{
  __int64 v2; // r9
  struct USDWrapper *v4; // r14
  char *v6; // rbx
  void *v7; // rdx
  void *v8; // rax
  int v9; // edx
  int v10; // ecx
  __int64 v11; // rax
  void (__fastcall *v12)(struct USDWrapper *, _QWORD *); // rbx
  char *v13; // rbx
  void *v14; // rdx
  void *v15; // rax
  int v16; // edx
  int v17; // ecx
  __int64 v18; // rsi
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  unsigned __int16 v26; // ax
  unsigned __int16 v27; // di
  unsigned __int16 v28; // bx
  bool v29; // zf
  const wchar_t *v30; // rdi
  char *v31; // rbx
  void *v32; // rdx
  void *v33; // rax
  int v34; // edx
  int v35; // ecx
  __int64 v36; // rax
  __int64 v37; // rax
  char *v38; // rbx
  void *v39; // rdx
  void *v40; // rax
  int v41; // edx
  int v42; // ecx
  char *v43; // rbx
  void *v44; // rdx
  void *v45; // rax
  int v46; // edx
  int v47; // ecx
  char *v48; // rbx
  void *v49; // rdx
  void *v50; // rax
  int v51; // edx
  int v52; // ecx
  char *v53; // rbx
  void *v54; // rdx
  void *v55; // rax
  int v56; // edx
  int v57; // ecx
  char *v58; // rbx
  void *v59; // rdx
  void *v60; // rax
  int v61; // edx
  int v62; // ecx
  char *v63; // rbx
  void *v64; // rdx
  void *v65; // rax
  int v66; // edx
  int v67; // ecx
  LPVOID lpMem; // [rsp+20h] [rbp-E0h]
  LPVOID lpMema; // [rsp+20h] [rbp-E0h]
  struct USDWrapper *v71; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v72[34]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v73; // [rsp+150h] [rbp+50h]
  _QWORD v74[34]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v75; // [rsp+280h] [rbp+180h]
  _QWORD v76[38]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v77[312]; // [rsp+3D0h] [rbp+2D0h] BYREF
  _QWORD v78[2]; // [rsp+530h] [rbp+430h] BYREF
  __int16 v79; // [rsp+540h] [rbp+440h] BYREF
  __int16 *v80; // [rsp+640h] [rbp+540h]
  __int64 v81; // [rsp+648h] [rbp+548h]
  __int64 v82; // [rsp+650h] [rbp+550h]
  char v83; // [rsp+658h] [rbp+558h]
  const unsigned __int64 *v84; // [rsp+660h] [rbp+560h] BYREF
  __int16 v85; // [rsp+668h] [rbp+568h] BYREF
  __int16 *v86; // [rsp+768h] [rbp+668h]
  __m128i si128; // [rsp+770h] [rbp+670h]
  char v88; // [rsp+780h] [rbp+680h]
  _BYTE v89[352]; // [rsp+790h] [rbp+690h] BYREF

  v2 = *(_QWORD *)(a2 + 264);
  v78[0] = &RegistryDeviceEnumerator::RegDeviceCacheEntry::`vftable';
  v81 = 128;
  v80 = &v79;
  v78[1] = &CSimpleStringBase<unsigned short>::`vftable';
  v79 = 0;
  v4 = 0;
  v84 = &CSimpleStringBase<unsigned short>::`vftable';
  v86 = &v85;
  v71 = 0;
  v85 = 0;
  v82 = 16;
  v83 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v88 = 0;
  v6 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Creating USD wrapper for device with id (%ws)", v2);
  WriteDbgTraceInfoWI("RegistryDeviceEnumerator::CreateUSDWrapper", v6);
  WiaTrcLib::Free((WiaTrcLib *)v6, v7);
  v8 = (void *)WiaTrace_TraceWithSubCompTraceLevel(
                 0,
                 0,
                 "Creating USD wrapper for device with id (%ws)",
                 *(_QWORD *)(a2 + 264));
  WiaTrace_ProcessTrace_Ex(v10, v9, (int)"RegistryDeviceEnumerator::CreateUSDWrapper", 4, v8);
  v11 = CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v72, a2);
  if ( (unsigned __int8)RegistryDeviceEnumerator::LookupCacheEntry(a1, v11, v78) )
  {
    if ( (int)GetNewUSDWrapper(&v71) < 0 )
    {
      v58 = (char *)WiaTrace_TraceLog("The Registry Device enumerator could not create the device wrapper because we are out of memory");
      WriteDbgTraceErrorWI("RegistryDeviceEnumerator::CreateUSDWrapper", v58);
      WiaTrcLib::Free((WiaTrcLib *)v58, v59);
      v60 = (void *)WiaTrace_Trace("The Registry Device enumerator could not create the device wrapper because we are out of memory");
      WiaTrace_ProcessTrace_Ex(v62, v61, (int)"RegistryDeviceEnumerator::CreateUSDWrapper", 1, v60);
      v4 = v71;
    }
    else
    {
      v4 = v71;
      v12 = *(void (__fastcall **)(struct USDWrapper *, _QWORD *))(*(_QWORD *)v71 + 64LL);
      CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v72, &v84);
      v12(v4, v72);
      if ( (*(int (__fastcall **)(struct USDWrapper *, __int64))(*(_QWORD *)v4 + 56LL))(v4, 2) < 0 )
      {
        v13 = (char *)WiaTrace_TraceLogWithSubComp(1, "Unable to set USD type to Registry device type");
        WriteDbgTraceWarningWI("RegistryDeviceEnumerator::CreateUSDWrapper", v13);
        WiaTrcLib::Free((WiaTrcLib *)v13, v14);
        v15 = (void *)WiaTrace_TraceWithSubComp(1, "Unable to set USD type to Registry device type");
        WiaTrace_ProcessTrace_Ex(v17, v16, (int)"RegistryDeviceEnumerator::CreateUSDWrapper", 2, v15);
      }
      CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v74, &v84);
      CSimpleReg::CSimpleReg((CSimpleReg *)v77, 983103);
      v74[0] = &CSimpleStringBase<unsigned short>::`vftable';
      CSimpleStringBase<unsigned short>::DeleteStorage(v74);
      v18 = (*(__int64 (__fastcall **)(struct USDWrapper *))(*(_QWORD *)v4 + 152LL))(v4);
      if ( v18 )
      {
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v72, L"Device ID not found");
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v74, L"DeviceID");
        v19 = CSimpleReg::Query(v77, v76, v74, v72);
        CSimpleStringBase<unsigned short>::operator=(v18 + 48, v19);
        v76[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v76);
        v76[34] = 0;
        v74[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v74);
        v75 = 0;
        v72[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v72);
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(
          v76,
          L"{00000000-0000-0000-0000-000000000000}");
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v74, L"USDClass");
        v20 = CSimpleReg::Query(v77, v72, v74, v76);
        CSimpleStringBase<unsigned short>::operator=(v18 + 640, v20);
        v72[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v72);
        v73 = 0;
        v74[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v74);
        v75 = 0;
        v76[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v76);
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v76, L"No friendly name");
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v74, L"FriendlyName");
        v21 = CSimpleReg::Query(v77, v72, v74, v76);
        CSimpleStringBase<unsigned short>::operator=(v18 + 2120, v21);
        v72[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v72);
        v73 = 0;
        v74[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v74);
        v75 = 0;
        v76[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v76);
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v76, L"No vendor info. provided");
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v74, L"Vendor");
        v22 = CSimpleReg::Query(v77, v72, v74, v76);
        CSimpleStringBase<unsigned short>::operator=(v18 + 936, v22);
        v72[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v72);
        v73 = 0;
        v74[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v74);
        v75 = 0;
        v76[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v76);
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v76, L"No device description provided");
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v74, L"DriverDesc");
        v23 = CSimpleReg::Query(v77, v72, v74, v76);
        CSimpleStringBase<unsigned short>::operator=(v18 + 1232, v23);
        v72[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v72);
        v73 = 0;
        v74[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v74);
        v75 = 0;
        v76[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v76);
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v76, L"Auto");
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v74, L"CreateFileName");
        v24 = CSimpleReg::Query(v77, v72, v74, v76);
        CSimpleStringBase<unsigned short>::operator=(v18 + 1528, v24);
        v72[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v72);
        v73 = 0;
        v74[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v74);
        v75 = 0;
        v76[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v76);
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v76, &Class);
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v74, L"PropertyPages");
        v25 = CSimpleReg::Query(v77, v72, v74, v76);
        CSimpleStringBase<unsigned short>::operator=(v18 + 1824, v25);
        v72[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v72);
        v73 = 0;
        v74[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v74);
        v75 = 0;
        v76[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v76);
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v72, L"HardwareConfig");
        *(_DWORD *)(v18 + 24) = CSimpleReg::Query(v77, v72, 0);
        v72[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v72);
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v72, L"Capabilities");
        *(_DWORD *)(v18 + 36) = CSimpleReg::Query(v77, v72, 0);
        v72[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v72);
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v72, L"DeviceType");
        v26 = CSimpleReg::Query(v77, v72, 0);
        v72[0] = &CSimpleStringBase<unsigned short>::`vftable';
        v27 = v26;
        CSimpleStringBase<unsigned short>::DeleteStorage(v72);
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v72, L"DeviceSubType");
        v28 = CSimpleReg::Query(v77, v72, 0);
        v72[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v72);
        *(_DWORD *)(v18 + 8) = 32;
        v29 = (*(_BYTE *)(v18 + 36) & 0x10) == 0;
        *(_DWORD *)(v18 + 40) = v28 | (v27 << 16);
        if ( !v29 )
          *(_DWORD *)(v18 + 8) = 48;
        v30 = L"115200";
        if ( (*(_BYTE *)(v18 + 24) & 8) == 0 )
          v30 = &Class;
        v31 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                        0,
                        0,
                        "Processing Registry information for device (%ws), known as (%ws)",
                        *(_QWORD *)(v18 + 312),
                        *(_QWORD *)(v18 + 2384));
        WriteDbgTraceInfoWI("RegistryDeviceEnumerator::CreateUSDWrapper", v31);
        WiaTrcLib::Free((WiaTrcLib *)v31, v32);
        v33 = (void *)WiaTrace_TraceWithSubCompTraceLevel(
                        0,
                        0,
                        "Processing Registry information for device (%ws), known as (%ws)",
                        *(_QWORD *)(v18 + 312),
                        *(_QWORD *)(v18 + 2384));
        WiaTrace_ProcessTrace_Ex(v35, v34, (int)"RegistryDeviceEnumerator::CreateUSDWrapper", 4, v33);
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v72, L"DeviceData");
        CSimpleReg::CSimpleReg((CSimpleReg *)v89, 131097);
        v72[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v72);
        if ( CSimpleReg::OK((CSimpleReg *)v89) )
        {
          CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(
            v76,
            L"{00000000-0000-0000-0000-000000000000}");
          CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v74, L"UI Class ID");
          v36 = CSimpleReg::Query(v89, v72, v74, v76);
          CSimpleStringBase<unsigned short>::operator=(v18 + 2712, v36);
          v72[0] = &CSimpleStringBase<unsigned short>::`vftable';
          CSimpleStringBase<unsigned short>::DeleteStorage(v72);
          v74[0] = &CSimpleStringBase<unsigned short>::`vftable';
          v73 = 0;
          CSimpleStringBase<unsigned short>::DeleteStorage(v74);
          v75 = 0;
          v76[0] = &CSimpleStringBase<unsigned short>::`vftable';
          CSimpleStringBase<unsigned short>::DeleteStorage(v76);
          CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v76, v30);
          CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v74, L"BaudRate");
          v37 = CSimpleReg::Query(v89, v72, v74, v76);
          CSimpleStringBase<unsigned short>::operator=(v18 + 2416, v37);
          v72[0] = &CSimpleStringBase<unsigned short>::`vftable';
          CSimpleStringBase<unsigned short>::DeleteStorage(v72);
          v73 = 0;
          v74[0] = &CSimpleStringBase<unsigned short>::`vftable';
          CSimpleStringBase<unsigned short>::DeleteStorage(v74);
          v75 = 0;
          v76[0] = &CSimpleStringBase<unsigned short>::`vftable';
          CSimpleStringBase<unsigned short>::DeleteStorage(v76);
          CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v72, L"LockHoldingTime");
          *(_DWORD *)(v18 + 12) = CSimpleReg::Query(v89, v72, 0);
          v72[0] = &CSimpleStringBase<unsigned short>::`vftable';
          CSimpleStringBase<unsigned short>::DeleteStorage(v72);
          CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v72, L"PollTimeout");
          *(_DWORD *)(v18 + 16) = CSimpleReg::Query(v89, v72, 1000);
          v72[0] = &CSimpleStringBase<unsigned short>::`vftable';
          CSimpleStringBase<unsigned short>::DeleteStorage(v72);
          CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v72, L"DisableNotifications");
          *(_DWORD *)(v18 + 20) = CSimpleReg::Query(v89, v72, 0);
          v72[0] = &CSimpleStringBase<unsigned short>::`vftable';
          CSimpleStringBase<unsigned short>::DeleteStorage(v72);
        }
        else
        {
          v38 = (char *)WiaTrace_TraceLogWithSubComp(
                          0,
                          "There was a problem opening the DeviceData subkey for the device (%ws), known as (%ws)",
                          *(_QWORD *)(v18 + 312),
                          *(_QWORD *)(v18 + 2384));
          WriteDbgTraceWarningWI("RegistryDeviceEnumerator::CreateUSDWrapper", v38);
          WiaTrcLib::Free((WiaTrcLib *)v38, v39);
          v40 = (void *)WiaTrace_TraceWithSubComp(
                          0,
                          "There was a problem opening the DeviceData subkey for the device (%ws), known as (%ws)",
                          *(_QWORD *)(v18 + 312),
                          *(_QWORD *)(v18 + 2384));
          WiaTrace_ProcessTrace_Ex(v42, v41, (int)"RegistryDeviceEnumerator::CreateUSDWrapper", 2, v40);
          CSimpleStringBase<unsigned short>::operator=(v18 + 2712, L"{00000000-0000-0000-0000-000000000000}");
          CSimpleStringBase<unsigned short>::operator=(v18 + 2416, v30);
          *(_QWORD *)(v18 + 16) = 1000;
          *(_DWORD *)(v18 + 12) = 0;
        }
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v72, L"DeviceState");
        *(_DWORD *)(v18 + 4) = CSimpleReg::Query(v77, v72, 0);
        v72[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v72);
        LODWORD(lpMem) = *(_DWORD *)(v18 + 4);
        v43 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                        0,
                        0,
                        "Device state for (%ws): 0x%08X",
                        *(_QWORD *)(v18 + 2384),
                        lpMem);
        WriteDbgTraceInfoWI("RegistryDeviceEnumerator::CreateUSDWrapper", v43);
        WiaTrcLib::Free((WiaTrcLib *)v43, v44);
        LODWORD(lpMema) = *(_DWORD *)(v18 + 4);
        v45 = (void *)WiaTrace_TraceWithSubCompTraceLevel(
                        0,
                        0,
                        "Device state for (%ws): 0x%08X",
                        *(_QWORD *)(v18 + 2384),
                        lpMema);
        WiaTrace_ProcessTrace_Ex(v47, v46, (int)"RegistryDeviceEnumerator::CreateUSDWrapper", 4, v45);
        if ( *(_DWORD *)(v18 + 4) == 2 )
        {
          v48 = (char *)WiaTrace_TraceLogWithSubComp(
                          0,
                          "The registry device %ws is regarded as REMOVED, therefore we are returning a NULL USDWrapper for it",
                          *(_QWORD *)(a2 + 264));
          WriteDbgTraceWarningWI("RegistryDeviceEnumerator::CreateUSDWrapper", v48);
          WiaTrcLib::Free((WiaTrcLib *)v48, v49);
          v50 = (void *)WiaTrace_TraceWithSubComp(
                          0,
                          "The registry device %ws is regarded as REMOVED, therefore we are returning a NULL USDWrapper for it",
                          *(_QWORD *)(a2 + 264));
          WiaTrace_ProcessTrace_Ex(v52, v51, (int)"RegistryDeviceEnumerator::CreateUSDWrapper", 2, v50);
          (*(void (__fastcall **)(struct USDWrapper *))(*(_QWORD *)v4 + 16LL))(v4);
          v4 = 0;
        }
        CSimpleReg::~CSimpleReg((CSimpleReg *)v89);
      }
      else
      {
        v53 = (char *)WiaTrace_TraceLogWithSubComp(
                        1,
                        "The Registry Device enumerator could not find the wrapper's USDInfo");
        WriteDbgTraceWarningWI("RegistryDeviceEnumerator::CreateUSDWrapper", v53);
        WiaTrcLib::Free((WiaTrcLib *)v53, v54);
        v55 = (void *)WiaTrace_TraceWithSubComp(
                        1,
                        "The Registry Device enumerator could not find the wrapper's USDInfo");
        WiaTrace_ProcessTrace_Ex(v57, v56, (int)"RegistryDeviceEnumerator::CreateUSDWrapper", 2, v55);
      }
      CSimpleReg::~CSimpleReg((CSimpleReg *)v77);
    }
  }
  else
  {
    v63 = (char *)WiaTrace_TraceLogWithSubComp(
                    0,
                    "The Volume Device Enumerator could not create a wrapper for (%ws)",
                    *(_QWORD *)(a2 + 264));
    WriteDbgTraceWarningWI("RegistryDeviceEnumerator::CreateUSDWrapper", v63);
    WiaTrcLib::Free((WiaTrcLib *)v63, v64);
    v65 = (void *)WiaTrace_TraceWithSubComp(
                    0,
                    "The Volume Device Enumerator could not create a wrapper for (%ws)",
                    *(_QWORD *)(a2 + 264));
    WiaTrace_ProcessTrace_Ex(v67, v66, (int)"RegistryDeviceEnumerator::CreateUSDWrapper", 2, v65);
  }
  RegistryDeviceEnumerator::RegDeviceCacheEntry::~RegDeviceCacheEntry((RegistryDeviceEnumerator::RegDeviceCacheEntry *)v78);
  return v4;
}

```

## disassembly

```asm
0x180049170  mov     [rsp-8+arg_10], rbx
0x180049175  mov     [rsp-8+arg_18], rsi
0x18004917a  push    rbp
0x18004917b  push    rdi
0x18004917c  push    r12
0x18004917e  push    r13
0x180049180  push    r14
0x180049182  lea     rbp, [rsp-800h]
0x18004918a  sub     rsp, 900h
0x180049191  mov     rax, cs:__security_cookie
0x180049198  xor     rax, rsp
0x18004919b  mov     [rbp+820h+var_30], rax
0x1800491a2  movdqa  xmm0, cs:__xmm@00000000000000100000000000000080
0x1800491aa  lea     rax, ??_7RegDeviceCacheEntry@RegistryDeviceEnumerator@@6B@; const RegistryDeviceEnumerator::RegDeviceCacheEntry::`vftable'
0x1800491b1  mov     r9, [rdx+108h]
0x1800491b8  lea     r8, aCreatingUsdWra; "Creating USD wrapper for device with id"...
0x1800491bf  mov     [rbp+820h+var_3F0], rax
0x1800491c6  mov     rdi, rcx
0x1800491c9  lea     rax, [rbp+820h+var_3E0]
0x1800491d0  mov     [rbp+820h+var_2D8], 80h
0x1800491db  mov     [rbp+820h+var_2E0], rax
0x1800491e2  lea     rcx, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x1800491e9  xor     eax, eax
0x1800491eb  mov     [rbp+820h+var_3E8], rcx
0x1800491f2  mov     [rbp+820h+var_3E0], ax
0x1800491f9  xor     r14d, r14d
0x1800491fc  lea     rax, [rbp+820h+var_2B8]
0x180049203  mov     [rbp+820h+var_2C0], rcx
0x18004920a  mov     [rbp+820h+var_1B8], rax
0x180049211  mov     r13, rdx
0x180049214  xor     eax, eax
0x180049216  mov     [rsp+920h+var_8F0], r14
0x18004921b  xor     edx, edx
0x18004921d  mov     [rbp+820h+var_2B8], ax
0x180049224  xor     ecx, ecx
0x180049226  mov     [rbp+820h+var_2D0], 10h
0x180049231  mov     [rbp+820h+var_2C8], r14b
0x180049238  movdqa  [rbp+820h+var_1B0], xmm0
0x180049240  mov     [rbp+820h+var_1A0], r14b
0x180049247  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18004924c  lea     rsi, aRegistrydevice_2; "RegistryDeviceEnumerator::CreateUSDWrap"...
0x180049253  mov     rdx, rax; char *
0x180049256  mov     rcx, rsi; char *
0x180049259  mov     rbx, rax
0x18004925c  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180049261  mov     rcx, rbx; this
0x180049264  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180049269  mov     r9, [r13+108h]
0x180049270  lea     r8, aCreatingUsdWra; "Creating USD wrapper for device with id"...
0x180049277  xor     edx, edx
0x180049279  xor     ecx, ecx
0x18004927b  call    WiaTrace_TraceWithSubCompTraceLevel
0x180049280  lea     r9d, [r14+4]; int
0x180049284  mov     [rsp+920h+lpMem], rax; lpMem
0x180049289  mov     r8, rsi; int
0x18004928c  call    WiaTrace_ProcessTrace_Ex
0x180049291  mov     rdx, r13
0x180049294  lea     rcx, [rsp+920h+var_8E0]
0x180049299  call    ??0?$CSimpleStringBase@G@@QEAA@AEBV0@@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(CSimpleStringBase<ushort> const &)
0x18004929e  mov     rdx, rax
0x1800492a1  lea     r8, [rbp+820h+var_3F0]
0x1800492a8  mov     rcx, rdi
0x1800492ab  call    ?LookupCacheEntry@RegistryDeviceEnumerator@@AEAA_NV?$CSimpleStringBase@G@@AEAVRegDeviceCacheEntry@1@@Z; RegistryDeviceEnumerator::LookupCacheEntry(CSimpleStringBase<ushort>,RegistryDeviceEnumerator::RegDeviceCacheEntry &)
0x1800492b0  xor     edi, edi
0x1800492b2  test    al, al
0x1800492b4  jz      loc_180049D80
0x1800492ba  lea     rcx, [rsp+920h+var_8F0]; struct USDWrapper **
0x1800492bf  call    ?GetNewUSDWrapper@@YAJPEAPEAVUSDWrapper@@@Z; GetNewUSDWrapper(USDWrapper * *)
0x1800492c4  test    eax, eax
0x1800492c6  js      loc_180049D38
0x1800492cc  mov     r14, [rsp+920h+var_8F0]
0x1800492d1  lea     rdx, [rbp+820h+var_2C0]
0x1800492d8  lea     rcx, [rsp+920h+var_8E0]
0x1800492dd  mov     rax, [r14]
0x1800492e0  mov     rbx, [rax+40h]
0x1800492e4  call    ??0?$CSimpleStringBase@G@@QEAA@AEBV0@@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(CSimpleStringBase<ushort> const &)
0x1800492e9  lea     rdx, [rsp+920h+var_8E0]
0x1800492ee  mov     rcx, r14
0x1800492f1  mov     rax, rbx
0x1800492f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800492f9  mov     rax, [r14]
0x1800492fc  lea     edx, [rdi+2]
0x1800492ff  mov     rcx, r14
0x180049302  mov     rax, [rax+38h]
0x180049306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004930b  lea     r12d, [rdi+1]
0x18004930f  test    eax, eax
0x180049311  jns     short loc_180049358
0x180049313  lea     rdx, aUnableToSetUsd_0; "Unable to set USD type to Registry devi"...
0x18004931a  mov     ecx, r12d
0x18004931d  call    WiaTrace_TraceLogWithSubComp
0x180049322  mov     rdx, rax; char *
0x180049325  mov     rcx, rsi; char *
0x180049328  mov     rbx, rax
0x18004932b  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180049330  mov     rcx, rbx; this
0x180049333  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180049338  lea     rdx, aUnableToSetUsd_0; "Unable to set USD type to Registry devi"...
0x18004933f  mov     ecx, r12d
0x180049342  call    WiaTrace_TraceWithSubComp
0x180049347  lea     r9d, [rdi+2]; int
0x18004934b  mov     [rsp+920h+lpMem], rax; lpMem
0x180049350  mov     r8, rsi; int
0x180049353  call    WiaTrace_ProcessTrace_Ex
0x180049358  lea     rdx, [rbp+820h+var_2C0]
0x18004935f  lea     rcx, [rbp+820h+var_7B0]
0x180049363  call    ??0?$CSimpleStringBase@G@@QEAA@AEBV0@@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(CSimpleStringBase<ushort> const &)
0x180049368  xor     r9d, r9d
0x18004936b  mov     dword ptr [rsp+920h+lpMem], 0F003Fh; int
0x180049373  lea     r8, [rbp+820h+var_7B0]
0x180049377  mov     rdx, 0FFFFFFFF80000002h
0x18004937e  lea     rcx, [rbp+820h+var_550]; this
0x180049385  call    ??0CSimpleReg@@QEAA@PEAUHKEY__@@AEBV?$CSimpleStringBase@G@@_NKPEAU_SECURITY_ATTRIBUTES@@@Z; CSimpleReg::CSimpleReg(HKEY__ *,CSimpleStringBase<ushort> const &,bool,ulong,_SECURITY_ATTRIBUTES *)
0x18004938a  lea     rbx, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180049391  lea     rcx, [rbp+820h+var_7B0]
0x180049395  mov     [rbp+820h+var_7B0], rbx
0x180049399  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18004939e  mov     rax, [r14]
0x1800493a1  mov     rcx, r14
0x1800493a4  mov     rax, [rax+98h]
0x1800493ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800493b0  mov     rsi, rax
0x1800493b3  test    rax, rax
0x1800493b6  jz      loc_180049CD8
0x1800493bc  lea     rdx, aDeviceIdNotFou; "Device ID not found"
0x1800493c3  lea     rcx, [rsp+920h+var_8E0]
0x1800493c8  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800493cd  lea     rdx, ValueName; "DeviceID"
0x1800493d4  lea     rcx, [rbp+820h+var_7B0]
0x1800493d8  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800493dd  lea     r9, [rsp+920h+var_8E0]
0x1800493e2  lea     r8, [rbp+820h+var_7B0]
0x1800493e6  lea     rdx, [rbp+820h+var_680]
0x1800493ed  lea     rcx, [rbp+820h+var_550]
0x1800493f4  call    ?Query@CSimpleReg@@QEBA?AV?$CSimpleStringBase@G@@AEBV2@0@Z; CSimpleReg::Query(CSimpleStringBase<ushort> const &,CSimpleStringBase<ushort> const &)
0x1800493f9  mov     rdx, rax
0x1800493fc  lea     rcx, [rsi+30h]
0x180049400  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x180049405  lea     rcx, [rbp+820h+var_680]
0x18004940c  mov     [rbp+820h+var_680], rbx
0x180049413  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180049418  lea     rcx, [rbp+820h+var_7B0]
0x18004941c  mov     [rbp+820h+var_570], rdi
0x180049423  mov     [rbp+820h+var_7B0], rbx
0x180049427  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18004942c  lea     rcx, [rsp+920h+var_8E0]
0x180049431  mov     [rbp+820h+var_6A0], rdi
0x180049438  mov     [rsp+920h+var_8E0], rbx
0x18004943d  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180049442  lea     rdx, a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180049449  lea     rcx, [rbp+820h+var_680]
0x180049450  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180049455  lea     rdx, aUsdclass; "USDClass"
0x18004945c  lea     rcx, [rbp+820h+var_7B0]
0x180049460  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180049465  lea     r9, [rbp+820h+var_680]
0x18004946c  lea     r8, [rbp+820h+var_7B0]
0x180049470  lea     rdx, [rsp+920h+var_8E0]
0x180049475  lea     rcx, [rbp+820h+var_550]
0x18004947c  call    ?Query@CSimpleReg@@QEBA?AV?$CSimpleStringBase@G@@AEBV2@0@Z; CSimpleReg::Query(CSimpleStringBase<ushort> const &,CSimpleStringBase<ushort> const &)
0x180049481  mov     rdx, rax
0x180049484  lea     rcx, [rsi+280h]
0x18004948b  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x180049490  lea     rcx, [rsp+920h+var_8E0]
0x180049495  mov     [rsp+920h+var_8E0], rbx
0x18004949a  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18004949f  lea     rcx, [rbp+820h+var_7B0]
0x1800494a3  mov     [rbp+820h+var_7D0], rdi
0x1800494a7  mov     [rbp+820h+var_7B0], rbx
0x1800494ab  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800494b0  lea     rcx, [rbp+820h+var_680]
0x1800494b7  mov     [rbp+820h+var_6A0], rdi
0x1800494be  mov     [rbp+820h+var_680], rbx
0x1800494c5  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800494ca  lea     rdx, aNoFriendlyName; "No friendly name"
0x1800494d1  lea     rcx, [rbp+820h+var_680]
0x1800494d8  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800494dd  lea     rdx, aFriendlyname; "FriendlyName"
0x1800494e4  lea     rcx, [rbp+820h+var_7B0]
0x1800494e8  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800494ed  lea     r9, [rbp+820h+var_680]
0x1800494f4  lea     r8, [rbp+820h+var_7B0]
0x1800494f8  lea     rdx, [rsp+920h+var_8E0]
0x1800494fd  lea     rcx, [rbp+820h+var_550]
0x180049504  call    ?Query@CSimpleReg@@QEBA?AV?$CSimpleStringBase@G@@AEBV2@0@Z; CSimpleReg::Query(CSimpleStringBase<ushort> const &,CSimpleStringBase<ushort> const &)
0x180049509  mov     rdx, rax
0x18004950c  lea     rcx, [rsi+848h]
0x180049513  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x180049518  lea     rcx, [rsp+920h+var_8E0]
0x18004951d  mov     [rsp+920h+var_8E0], rbx
0x180049522  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180049527  lea     rcx, [rbp+820h+var_7B0]
0x18004952b  mov     [rbp+820h+var_7D0], rdi
0x18004952f  mov     [rbp+820h+var_7B0], rbx
0x180049533  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180049538  lea     rcx, [rbp+820h+var_680]
0x18004953f  mov     [rbp+820h+var_6A0], rdi
0x180049546  mov     [rbp+820h+var_680], rbx
0x18004954d  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180049552  lea     rdx, aNoVendorInfoPr; "No vendor info. provided"
0x180049559  lea     rcx, [rbp+820h+var_680]
0x180049560  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180049565  lea     rdx, aVendor; "Vendor"
0x18004956c  lea     rcx, [rbp+820h+var_7B0]
0x180049570  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180049575  lea     r9, [rbp+820h+var_680]
0x18004957c  lea     r8, [rbp+820h+var_7B0]
0x180049580  lea     rdx, [rsp+920h+var_8E0]
0x180049585  lea     rcx, [rbp+820h+var_550]
0x18004958c  call    ?Query@CSimpleReg@@QEBA?AV?$CSimpleStringBase@G@@AEBV2@0@Z; CSimpleReg::Query(CSimpleStringBase<ushort> const &,CSimpleStringBase<ushort> const &)
0x180049591  mov     rdx, rax
0x180049594  lea     rcx, [rsi+3A8h]
0x18004959b  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x1800495a0  lea     rcx, [rsp+920h+var_8E0]
0x1800495a5  mov     [rsp+920h+var_8E0], rbx
0x1800495aa  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800495af  lea     rcx, [rbp+820h+var_7B0]
0x1800495b3  mov     [rbp+820h+var_7D0], rdi
0x1800495b7  mov     [rbp+820h+var_7B0], rbx
0x1800495bb  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800495c0  lea     rcx, [rbp+820h+var_680]
0x1800495c7  mov     [rbp+820h+var_6A0], rdi
0x1800495ce  mov     [rbp+820h+var_680], rbx
0x1800495d5  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800495da  lea     rdx, aNoDeviceDescri; "No device description provided"
0x1800495e1  lea     rcx, [rbp+820h+var_680]
0x1800495e8  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800495ed  lea     rdx, aDriverdesc; "DriverDesc"
0x1800495f4  lea     rcx, [rbp+820h+var_7B0]
0x1800495f8  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800495fd  lea     r9, [rbp+820h+var_680]
0x180049604  lea     r8, [rbp+820h+var_7B0]
0x180049608  lea     rdx, [rsp+920h+var_8E0]
0x18004960d  lea     rcx, [rbp+820h+var_550]
0x180049614  call    ?Query@CSimpleReg@@QEBA?AV?$CSimpleStringBase@G@@AEBV2@0@Z; CSimpleReg::Query(CSimpleStringBase<ushort> const &,CSimpleStringBase<ushort> const &)
0x180049619  mov     rdx, rax
0x18004961c  lea     rcx, [rsi+4D0h]
0x180049623  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x180049628  lea     rcx, [rsp+920h+var_8E0]
0x18004962d  mov     [rsp+920h+var_8E0], rbx
0x180049632  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180049637  lea     rcx, [rbp+820h+var_7B0]
0x18004963b  mov     [rbp+820h+var_7D0], rdi
0x18004963f  mov     [rbp+820h+var_7B0], rbx
0x180049643  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180049648  lea     rcx, [rbp+820h+var_680]
0x18004964f  mov     [rbp+820h+var_6A0], rdi
0x180049656  mov     [rbp+820h+var_680], rbx
0x18004965d  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180049662  lea     rdx, aAuto; "Auto"
0x180049669  lea     rcx, [rbp+820h+var_680]
0x180049670  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180049675  lea     rdx, aCreatefilename; "CreateFileName"
0x18004967c  lea     rcx, [rbp+820h+var_7B0]
0x180049680  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180049685  lea     r9, [rbp+820h+var_680]
0x18004968c  lea     r8, [rbp+820h+var_7B0]
0x180049690  lea     rdx, [rsp+920h+var_8E0]
0x180049695  lea     rcx, [rbp+820h+var_550]
0x18004969c  call    ?Query@CSimpleReg@@QEBA?AV?$CSimpleStringBase@G@@AEBV2@0@Z; CSimpleReg::Query(CSimpleStringBase<ushort> const &,CSimpleStringBase<ushort> const &)
0x1800496a1  mov     rdx, rax
0x1800496a4  lea     rcx, [rsi+5F8h]
0x1800496ab  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x1800496b0  lea     rcx, [rsp+920h+var_8E0]
0x1800496b5  mov     [rsp+920h+var_8E0], rbx
0x1800496ba  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800496bf  lea     rcx, [rbp+820h+var_7B0]
0x1800496c3  mov     [rbp+820h+var_7D0], rdi
0x1800496c7  mov     [rbp+820h+var_7B0], rbx
0x1800496cb  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800496d0  lea     rcx, [rbp+820h+var_680]
0x1800496d7  mov     [rbp+820h+var_6A0], rdi
0x1800496de  mov     [rbp+820h+var_680], rbx
0x1800496e5  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800496ea  lea     rdx, Class
0x1800496f1  lea     rcx, [rbp+820h+var_680]
0x1800496f8  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800496fd  lea     rdx, aPropertypages; "PropertyPages"
0x180049704  lea     rcx, [rbp+820h+var_7B0]
0x180049708  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18004970d  lea     r9, [rbp+820h+var_680]
0x180049714  lea     r8, [rbp+820h+var_7B0]
0x180049718  lea     rdx, [rsp+920h+var_8E0]
0x18004971d  lea     rcx, [rbp+820h+var_550]
0x180049724  call    ?Query@CSimpleReg@@QEBA?AV?$CSimpleStringBase@G@@AEBV2@0@Z; CSimpleReg::Query(CSimpleStringBase<ushort> const &,CSimpleStringBase<ushort> const &)
0x180049729  mov     rdx, rax
0x18004972c  lea     rcx, [rsi+720h]
0x180049733  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x180049738  lea     rcx, [rsp+920h+var_8E0]
0x18004973d  mov     [rsp+920h+var_8E0], rbx
0x180049742  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180049747  lea     rcx, [rbp+820h+var_7B0]
0x18004974b  mov     [rbp+820h+var_7D0], rdi
0x18004974f  mov     [rbp+820h+var_7B0], rbx
0x180049753  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180049758  lea     rcx, [rbp+820h+var_680]
0x18004975f  mov     [rbp+820h+var_6A0], rdi
0x180049766  mov     [rbp+820h+var_680], rbx
0x18004976d  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180049772  lea     rdx, aHardwareconfig; "HardwareConfig"
  ... truncated ...
```
