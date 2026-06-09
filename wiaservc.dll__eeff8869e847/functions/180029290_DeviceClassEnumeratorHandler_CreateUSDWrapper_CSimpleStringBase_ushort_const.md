# DeviceClassEnumeratorHandler::CreateUSDWrapper(CSimpleStringBase<ushort> const &)

- ea: `0x180029290`
- end: `0x180029ad7`
- name: `?CreateUSDWrapper@DeviceClassEnumeratorHandler@@UEAAPEAVUSDWrapper@@AEBV?$CSimpleStringBase@G@@@Z`
- size: `2119`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `30`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006740`
- `0x180008b18`
- `0x18000a974`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000f4fc`
- `0x180010a28`
- `0x180010f0c`
- `0x1800113d8`
- `0x1800119c8`
- `0x180011a94`
- `0x180011ad0`
- `0x1800136a4`
- `0x1800174c4`
- `0x180029290`
- `0x18002c410`
- `0x18002c790`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033cc0`
- `0x180045610`
- `0x1800466e8`
- `0x180046838`
- `0x18004829c`
- `0x1800775e4`
- `0x180078010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180029a18`
- `ADVAPI32!RegCloseKey` at `0x180029a18`

## string_xrefs

- `0x180029419`: `DeviceClassEnumeratorHandler::CreateUSDWrapper`
- `0x180029950`: `DeviceClassEnumeratorHandler::CreateUSDWrapper`
- `0x1800299c1`: `DeviceClassEnumeratorHandler::CreateUSDWrapper`
- `0x180029a5d`: `DeviceClassEnumeratorHandler::CreateUSDWrapper`
- `0x18002950f`: `DEVPKEY_WIA_USDClassId = %ws`
- `0x18002953d`: `DEVPKEY_WIA_USDClassId = %ws`
- `0x180029a4a`: `The Device Class Enumerator could not create a USDWrapper for %ws because we failed to find the DeviceInfoSet`
- `0x180029a81`: `The Device Class Enumerator could not create a USDWrapper for %ws because we failed to find the DeviceInfoSet`

## pseudocode

```c
__int64 __fastcall DeviceClassEnumeratorHandler::CreateUSDWrapper(__int64 a1, __int64 a2)
{
  __int64 v3; // r14
  __int64 v5; // r12
  CSimpleReg *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdi
  __int64 InterfaceName; // rax
  int ContainerId; // eax
  int v11; // r15d
  char *v12; // rbx
  void *v13; // rdx
  void *v14; // rax
  int v15; // edx
  int v16; // ecx
  __int64 StringFromInterfacePathProperty; // rax
  char *v18; // rbx
  void *v19; // rdx
  void *v20; // rax
  int v21; // edx
  int v22; // ecx
  unsigned int v23; // eax
  __int64 v24; // rax
  char *v25; // rbx
  void *v26; // rdx
  void *v27; // rax
  int v28; // edx
  int v29; // ecx
  __int64 StringFromInstancePathProperty; // rax
  char *v31; // rbx
  void *v32; // rdx
  void *v33; // rax
  int v34; // edx
  int v35; // ecx
  __int64 v36; // rax
  char *v37; // rbx
  void *v38; // rdx
  void *v39; // rax
  int v40; // edx
  int v41; // ecx
  __int64 v42; // rax
  char *v43; // rbx
  void *v44; // rdx
  void *v45; // rax
  int v46; // edx
  int v47; // ecx
  __int64 v48; // rax
  char *v49; // rbx
  void *v50; // rdx
  void *v51; // rax
  int v52; // edx
  int v53; // ecx
  char *v54; // rbx
  void *v55; // rdx
  char *v56; // rbx
  void *v57; // rdx
  void *v58; // rax
  int v59; // edx
  int v60; // ecx
  __int64 v61; // rcx
  char *v62; // rbx
  void *v63; // rdx
  void *v64; // rax
  int v65; // edx
  int v66; // ecx
  LPVOID lpMem; // [rsp+20h] [rbp-E0h]
  LPVOID lpMema; // [rsp+20h] [rbp-E0h]
  __int64 v70; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h]
  _BYTE v72[16]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v73[44]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v74[38]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v75[352]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v3 = 0;
  v70 = 0;
  ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v72);
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v74, L"DeviceInfoSet");
  v5 = ServiceComponentHolder::Get<DeviceInfoSet>(v72, v74);
  v74[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(v74);
  v74[34] = 0;
  if ( !v5 )
  {
    v62 = (char *)WiaTrace_TraceLogWithSubComp(
                    1,
                    "The Device Class Enumerator could not create a USDWrapper for %ws because we failed to find the DeviceInfoSet",
                    *(_QWORD *)(a2 + 264));
    WriteDbgTraceWarningWI("DeviceClassEnumeratorHandler::CreateUSDWrapper", v62);
    WiaTrcLib::Free((WiaTrcLib *)v62, v63);
    v64 = (void *)WiaTrace_TraceWithSubComp(
                    1,
                    "The Device Class Enumerator could not create a USDWrapper for %ws because we failed to find the DeviceInfoSet",
                    *(_QWORD *)(a2 + 264));
    WiaTrace_ProcessTrace_Ex(v66, v65, (int)"DeviceClassEnumeratorHandler::CreateUSDWrapper", 2, v64);
    goto LABEL_33;
  }
  hKey = (HKEY)DeviceInfoSet::GetDeviceKey(v5, a2);
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v73, &Class);
  CSimpleReg::CSimpleReg((CSimpleReg *)v75, 131097);
  v73[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(v73);
  v6 = CSimpleReg::CSimpleReg((CSimpleReg *)v73, (const struct CSimpleReg *)v75);
  if ( (int)DeviceClassEnumeratorHandler::CreateWrapper(a1, v7, v6, &v70) < 0 )
  {
    v56 = (char *)WiaTrace_TraceLogWithSubComp(1, "Could not get a USD wrapper for %ws", *(_QWORD *)(a2 + 264));
    WriteDbgTraceWarningWI("DeviceClassEnumeratorHandler::CreateUSDWrapper", v56);
    WiaTrcLib::Free((WiaTrcLib *)v56, v57);
    v58 = (void *)WiaTrace_TraceWithSubComp(1, "Could not get a USD wrapper for %ws", *(_QWORD *)(a2 + 264));
    WiaTrace_ProcessTrace_Ex(v60, v59, (int)"DeviceClassEnumeratorHandler::CreateUSDWrapper", 2, v58);
    v3 = v70;
  }
  else
  {
    v3 = v70;
    v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v70 + 152LL))(v70);
    if ( v8 )
    {
      *(_DWORD *)(v8 + 4) = DeviceInfoSet::GetDeviceStatus(v5, a2, 0);
      InterfaceName = DeviceInfoSet::GetInterfaceName(v5, v73, a2);
      CSimpleStringBase<unsigned short>::operator=(v8 + 3304, InterfaceName);
      v73[0] = &CSimpleStringBase<unsigned short>::`vftable';
      CSimpleStringBase<unsigned short>::DeleteStorage(v73);
      ContainerId = GetContainerId(*(const unsigned __int16 **)(v8 + 3568), (struct _GUID *)(v8 + 3600));
      v11 = ContainerId;
      if ( ContainerId < 0 )
      {
        LODWORD(lpMem) = ContainerId;
        v12 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                        0x80000000LL,
                        0,
                        "GetContainerId(%ws) failed. hr = 0x%x",
                        *(_QWORD *)(a2 + 264),
                        lpMem);
        WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::CreateUSDWrapper", v12);
        WiaTrcLib::Free((WiaTrcLib *)v12, v13);
        LODWORD(lpMema) = v11;
        v14 = (void *)WiaTrace_TraceWithSubCompTraceLevel(
                        0x80000000LL,
                        0,
                        "GetContainerId(%ws) failed. hr = 0x%x",
                        *(_QWORD *)(a2 + 264),
                        lpMema);
        WiaTrace_ProcessTrace_Ex(v16, v15, (int)"DeviceClassEnumeratorHandler::CreateUSDWrapper", 4, v14);
      }
      if ( !CSimpleStringBase<unsigned short>::Length(v8 + 640)
        || !wcscmp_0(*(const wchar_t **)(v8 + 904), L"{00000000-0000-0000-0000-000000000000}") )
      {
        StringFromInterfacePathProperty = GetStringFromInterfacePathProperty(
                                            v73,
                                            *(_QWORD *)(v8 + 3568),
                                            DEVPKEY_WIA_USDClassId);
        CSimpleStringBase<unsigned short>::operator=(v8 + 640, StringFromInterfacePathProperty);
        v73[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v73);
        if ( CSimpleStringBase<unsigned short>::Length(v8 + 640) )
        {
          v18 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                          2,
                          0,
                          "DEVPKEY_WIA_USDClassId = %ws",
                          *(_QWORD *)(v8 + 904));
          WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::CreateUSDWrapper", v18);
          WiaTrcLib::Free((WiaTrcLib *)v18, v19);
          v20 = (void *)WiaTrace_TraceWithSubCompTraceLevel(2, 0, "DEVPKEY_WIA_USDClassId = %ws", *(_QWORD *)(v8 + 904));
          WiaTrace_ProcessTrace_Ex(v22, v21, (int)"DeviceClassEnumeratorHandler::CreateUSDWrapper", 4, v20);
          v23 = *(_DWORD *)(v8 + 8) & 0xFFFFFFFE;
          *(_DWORD *)(v8 + 40) = 65537;
          *(_DWORD *)(v8 + 32) = 16777218;
          *(_DWORD *)(v8 + 8) = v23 | 2;
          *(_DWORD *)(v8 + 36) = 16;
        }
        v24 = GetStringFromInterfacePathProperty(v73, *(_QWORD *)(v8 + 3568), &DEVPKEY_Device_InstanceId);
        CSimpleStringBase<unsigned short>::operator=(v8 + 48, v24);
        v73[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v73);
        if ( CSimpleStringBase<unsigned short>::Length(v8 + 48) )
        {
          v25 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                          2,
                          0,
                          "DEVPKEY_Device_InstanceId = %ws",
                          *(_QWORD *)(v8 + 312));
          WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::CreateUSDWrapper", v25);
          WiaTrcLib::Free((WiaTrcLib *)v25, v26);
          v27 = (void *)WiaTrace_TraceWithSubCompTraceLevel(
                          2,
                          0,
                          "DEVPKEY_Device_InstanceId = %ws",
                          *(_QWORD *)(v8 + 312));
          WiaTrace_ProcessTrace_Ex(v29, v28, (int)"DeviceClassEnumeratorHandler::CreateUSDWrapper", 4, v27);
          CSimpleStringBase<unsigned short>::operator=(v8 + 1528, v8 + 48);
          *(_DWORD *)(v8 + 4) |= 4u;
        }
        StringFromInstancePathProperty = GetStringFromInstancePathProperty(
                                           v73,
                                           *(_QWORD *)(v8 + 312),
                                           DEVPKEY_Aep_FriendlyName);
        CSimpleStringBase<unsigned short>::operator=(v8 + 2120, StringFromInstancePathProperty);
        v73[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v73);
        if ( CSimpleStringBase<unsigned short>::Length(v8 + 2120) )
        {
          v31 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                          2,
                          0,
                          "DEVPKEY_Aep_FriendlyName = %ws",
                          *(_QWORD *)(v8 + 2384));
          WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::CreateUSDWrapper", v31);
          WiaTrcLib::Free((WiaTrcLib *)v31, v32);
          v33 = (void *)WiaTrace_TraceWithSubCompTraceLevel(
                          2,
                          0,
                          "DEVPKEY_Aep_FriendlyName = %ws",
                          *(_QWORD *)(v8 + 2384));
          WiaTrace_ProcessTrace_Ex(v35, v34, (int)"DeviceClassEnumeratorHandler::CreateUSDWrapper", 4, v33);
        }
        v36 = GetStringFromInstancePathProperty(v73, *(_QWORD *)(v8 + 312), &DEVPKEY_Device_Manufacturer);
        CSimpleStringBase<unsigned short>::operator=(v8 + 936, v36);
        v73[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v73);
        if ( CSimpleStringBase<unsigned short>::Length(v8 + 936) )
        {
          v37 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                          2,
                          0,
                          "DEVPKEY_Device_Manufacturer = %ws",
                          *(_QWORD *)(v8 + 1200));
          WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::CreateUSDWrapper", v37);
          WiaTrcLib::Free((WiaTrcLib *)v37, v38);
          v39 = (void *)WiaTrace_TraceWithSubCompTraceLevel(
                          2,
                          0,
                          "DEVPKEY_Device_Manufacturer = %ws",
                          *(_QWORD *)(v8 + 1200));
          WiaTrace_ProcessTrace_Ex(v41, v40, (int)"DeviceClassEnumeratorHandler::CreateUSDWrapper", 4, v39);
        }
        v42 = GetStringFromInstancePathProperty(v73, *(_QWORD *)(v8 + 312), &DEVPKEY_Device_DeviceDesc);
        CSimpleStringBase<unsigned short>::operator=(v8 + 1232, v42);
        v73[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v73);
        if ( CSimpleStringBase<unsigned short>::Length(v8 + 1232) )
        {
          v43 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                          2,
                          0,
                          "DEVPKEY_Device_DeviceDesc = %ws",
                          *(_QWORD *)(v8 + 1496));
          WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::CreateUSDWrapper", v43);
          WiaTrcLib::Free((WiaTrcLib *)v43, v44);
          v45 = (void *)WiaTrace_TraceWithSubCompTraceLevel(
                          2,
                          0,
                          "DEVPKEY_Device_DeviceDesc = %ws",
                          *(_QWORD *)(v8 + 1496));
          WiaTrace_ProcessTrace_Ex(v47, v46, (int)"DeviceClassEnumeratorHandler::CreateUSDWrapper", 4, v45);
        }
      }
      if ( !wcscmp_0(*(const wchar_t **)(v8 + 312), L"Device ID not found") )
      {
        v48 = GetStringFromInterfacePathProperty(v73, *(_QWORD *)(v8 + 3568), &DEVPKEY_Device_InstanceId);
        CSimpleStringBase<unsigned short>::operator=(v8 + 48, v48);
        v73[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v73);
      }
      SetDeviceTypeProperty(*(const unsigned __int16 **)(v8 + 3568), *(unsigned __int16 *)(v8 + 42));
      if ( CSimpleStringBase<unsigned short>::Length(v8 + 640)
        && wcscmp_0(*(const wchar_t **)(v8 + 904), L"{00000000-0000-0000-0000-000000000000}")
        && CSimpleStringBase<unsigned short>::Length(v8 + 48)
        && wcscmp_0(*(const wchar_t **)(v8 + 312), L"Device ID not found")
        && CSimpleStringBase<unsigned short>::Length(v8 + 2120) )
      {
        goto LABEL_29;
      }
      v49 = (char *)WiaTrace_TraceLogWithSubComp(
                      1,
                      "USD wrapper for %ws is missing required information!",
                      *(_QWORD *)(a2 + 264));
      WriteDbgTraceWarningWI("DeviceClassEnumeratorHandler::CreateUSDWrapper", v49);
      WiaTrcLib::Free((WiaTrcLib *)v49, v50);
      v51 = (void *)WiaTrace_TraceWithSubComp(
                      1,
                      "USD wrapper for %ws is missing required information!",
                      *(_QWORD *)(a2 + 264));
    }
    else
    {
      v54 = (char *)WiaTrace_TraceLogWithSubComp(1, "%ws has a NULL USDInfo!", *(_QWORD *)(a2 + 264));
      WriteDbgTraceWarningWI("DeviceClassEnumeratorHandler::CreateUSDWrapper", v54);
      WiaTrcLib::Free((WiaTrcLib *)v54, v55);
      v51 = (void *)WiaTrace_TraceWithSubComp(1, "%ws has a NULL USDInfo!", *(_QWORD *)(a2 + 264));
    }
    WiaTrace_ProcessTrace_Ex(v53, v52, (int)"DeviceClassEnumeratorHandler::CreateUSDWrapper", 2, v51);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    v3 = 0;
  }
LABEL_29:
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  v61 = v5 + *(int *)(*(_QWORD *)v5 + 4LL);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
  CSimpleReg::~CSimpleReg((CSimpleReg *)v75);
LABEL_33:
  ServiceComponentHolder::~ServiceComponentHolder((ServiceComponentHolder *)v72);
  return v3;
}

```

## disassembly

```asm
0x180029290  mov     [rsp-8+arg_10], rbx
0x180029295  push    rbp
0x180029296  push    rsi
0x180029297  push    rdi
0x180029298  push    r12
0x18002929a  push    r13
0x18002929c  push    r14
0x18002929e  push    r15
0x1800292a0  lea     rbp, [rsp-350h]
0x1800292a8  sub     rsp, 450h
0x1800292af  mov     rax, cs:__security_cookie
0x1800292b6  xor     rax, rsp
0x1800292b9  mov     [rbp+380h+var_40], rax
0x1800292c0  mov     rbx, rcx
0x1800292c3  xor     r14d, r14d
0x1800292c6  lea     rcx, [rsp+480h+var_440]; this
0x1800292cb  mov     [rsp+480h+var_450], r14
0x1800292d0  mov     r13, rdx
0x1800292d3  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x1800292d8  lea     rdx, aDeviceinfoset; "DeviceInfoSet"
0x1800292df  lea     rcx, [rbp+380h+var_2D0]
0x1800292e6  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800292eb  lea     rdx, [rbp+380h+var_2D0]
0x1800292f2  lea     rcx, [rsp+480h+var_440]
0x1800292f7  call    ??$Get@VDeviceInfoSet@@@ServiceComponentHolder@@QEAAPEAVDeviceInfoSet@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<DeviceInfoSet>(CSimpleStringBase<ushort> const &)
0x1800292fc  lea     rsi, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180029303  mov     r12, rax
0x180029306  lea     rcx, [rbp+380h+var_2D0]
0x18002930d  mov     [rbp+380h+var_2D0], rsi
0x180029314  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180029319  mov     [rbp+380h+var_1C0], r14
0x180029320  test    r12, r12
0x180029323  jz      loc_180029A43
0x180029329  mov     rdx, r13
0x18002932c  mov     rcx, r12
0x18002932f  call    ?GetDeviceKey@DeviceInfoSet@@QEAAPEAUHKEY__@@AEBV?$CSimpleStringBase@G@@@Z; DeviceInfoSet::GetDeviceKey(CSimpleStringBase<ushort> const &)
0x180029334  lea     rdx, Class
0x18002933b  mov     [rsp+480h+hKey], rax
0x180029340  lea     rcx, [rsp+480h+var_430]
0x180029345  mov     rdi, rax
0x180029348  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18002934d  xor     r9d, r9d
0x180029350  mov     dword ptr [rsp+480h+lpMem], 20019h; int
0x180029358  lea     r8, [rsp+480h+var_430]
0x18002935d  mov     rdx, rdi
0x180029360  lea     rcx, [rbp+380h+var_1A0]; this
0x180029367  call    ??0CSimpleReg@@QEAA@PEAUHKEY__@@AEBV?$CSimpleStringBase@G@@_NKPEAU_SECURITY_ATTRIBUTES@@@Z; CSimpleReg::CSimpleReg(HKEY__ *,CSimpleStringBase<ushort> const &,bool,ulong,_SECURITY_ATTRIBUTES *)
0x18002936c  lea     rcx, [rsp+480h+var_430]
0x180029371  mov     [rsp+480h+var_430], rsi
0x180029376  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18002937b  lea     rdx, [rbp+380h+var_1A0]; struct CSimpleReg *
0x180029382  lea     rcx, [rsp+480h+var_430]; this
0x180029387  call    ??0CSimpleReg@@QEAA@AEBV0@@Z; CSimpleReg::CSimpleReg(CSimpleReg const &)
0x18002938c  mov     r8, rax
0x18002938f  lea     r9, [rsp+480h+var_450]
0x180029394  mov     rcx, rbx
0x180029397  call    ?CreateWrapper@DeviceClassEnumeratorHandler@@AEAAJJVCSimpleReg@@PEAPEAVUSDWrapper@@@Z; DeviceClassEnumeratorHandler::CreateWrapper(long,CSimpleReg,USDWrapper * *)
0x18002939c  test    eax, eax
0x18002939e  js      loc_1800299A7
0x1800293a4  mov     r14, [rsp+480h+var_450]
0x1800293a9  mov     rcx, r14
0x1800293ac  mov     rax, [r14]
0x1800293af  mov     rax, [rax+98h]
0x1800293b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800293bb  mov     rdi, rax
0x1800293be  test    rax, rax
0x1800293c1  jz      loc_180029936
0x1800293c7  xor     r8d, r8d
0x1800293ca  mov     rdx, r13
0x1800293cd  mov     rcx, r12
0x1800293d0  call    ?GetDeviceStatus@DeviceInfoSet@@QEAAKAEBV?$CSimpleStringBase@G@@K@Z; DeviceInfoSet::GetDeviceStatus(CSimpleStringBase<ushort> const &,ulong)
0x1800293d5  mov     r8, r13
0x1800293d8  mov     [rdi+4], eax
0x1800293db  lea     rdx, [rsp+480h+var_430]
0x1800293e0  mov     rcx, r12
0x1800293e3  call    ?GetInterfaceName@DeviceInfoSet@@QEAA?AV?$CSimpleStringBase@G@@AEBV2@K@Z; DeviceInfoSet::GetInterfaceName(CSimpleStringBase<ushort> const &,ulong)
0x1800293e8  mov     rdx, rax
0x1800293eb  lea     rcx, [rdi+0CE8h]
0x1800293f2  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x1800293f7  lea     rcx, [rsp+480h+var_430]
0x1800293fc  mov     [rsp+480h+var_430], rsi
0x180029401  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180029406  mov     rcx, [rdi+0DF0h]; unsigned __int16 *
0x18002940d  lea     rdx, [rdi+0E10h]; struct _GUID *
0x180029414  call    ?GetContainerId@@YAJPEBGPEAU_GUID@@@Z; GetContainerId(ushort const *,_GUID *)
0x180029419  lea     rsi, aDeviceclassenu_3; "DeviceClassEnumeratorHandler::CreateUSD"...
0x180029420  mov     r15d, eax
0x180029423  test    eax, eax
0x180029425  jns     short loc_18002948D
0x180029427  mov     r9, [r13+108h]
0x18002942e  lea     r8, aGetcontainerid_0; "GetContainerId(%ws) failed. hr = 0x%x"
0x180029435  xor     edx, edx
0x180029437  mov     dword ptr [rsp+480h+lpMem], eax
0x18002943b  mov     ecx, 80000000h
0x180029440  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180029445  mov     rdx, rax; char *
0x180029448  mov     rcx, rsi; char *
0x18002944b  mov     rbx, rax
0x18002944e  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180029453  mov     rcx, rbx; this
0x180029456  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002945b  mov     r9, [r13+108h]
0x180029462  lea     r8, aGetcontainerid_0; "GetContainerId(%ws) failed. hr = 0x%x"
0x180029469  xor     edx, edx
0x18002946b  mov     dword ptr [rsp+480h+lpMem], r15d
0x180029470  mov     ecx, 80000000h
0x180029475  call    WiaTrace_TraceWithSubCompTraceLevel
0x18002947a  mov     r9d, 4; int
0x180029480  mov     [rsp+480h+lpMem], rax; lpMem
0x180029485  mov     r8, rsi; int
0x180029488  call    WiaTrace_ProcessTrace_Ex
0x18002948d  lea     rbx, [rdi+280h]
0x180029494  mov     rcx, rbx
0x180029497  call    ?Length@?$CSimpleStringBase@G@@QEBA_KXZ; CSimpleStringBase<ushort>::Length(void)
0x18002949c  mov     r15d, 2
0x1800294a2  test    rax, rax
0x1800294a5  jz      short loc_1800294C2
0x1800294a7  mov     rcx, [rdi+388h]; String1
0x1800294ae  lea     rdx, a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x1800294b5  call    wcscmp_0
0x1800294ba  test    eax, eax
0x1800294bc  jnz     loc_180029829
0x1800294c2  mov     rdx, [rdi+0DF0h]
0x1800294c9  lea     r8, DEVPKEY_WIA_USDClassId
0x1800294d0  lea     rcx, [rsp+480h+var_430]
0x1800294d5  call    ?GetStringFromInterfacePathProperty@@YA?AV?$CSimpleStringBase@G@@PEBGPEBU_DEVPROPKEY@@@Z; GetStringFromInterfacePathProperty(ushort const *,_DEVPROPKEY const *)
0x1800294da  mov     rdx, rax
0x1800294dd  mov     rcx, rbx
0x1800294e0  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x1800294e5  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x1800294ec  lea     rcx, [rsp+480h+var_430]
0x1800294f1  mov     [rsp+480h+var_430], rax
0x1800294f6  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800294fb  mov     rcx, rbx
0x1800294fe  call    ?Length@?$CSimpleStringBase@G@@QEBA_KXZ; CSimpleStringBase<ushort>::Length(void)
0x180029503  test    rax, rax
0x180029506  jz      short loc_180029582
0x180029508  mov     r9, [rdi+388h]
0x18002950f  lea     r8, aDevpkeyWiaUsdc; "DEVPKEY_WIA_USDClassId = %ws"
0x180029516  xor     edx, edx
0x180029518  mov     ecx, r15d
0x18002951b  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180029520  mov     rdx, rax; char *
0x180029523  mov     rcx, rsi; char *
0x180029526  mov     rbx, rax
0x180029529  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18002952e  mov     rcx, rbx; this
0x180029531  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180029536  mov     r9, [rdi+388h]
0x18002953d  lea     r8, aDevpkeyWiaUsdc; "DEVPKEY_WIA_USDClassId = %ws"
0x180029544  xor     edx, edx
0x180029546  mov     ecx, r15d
0x180029549  call    WiaTrace_TraceWithSubCompTraceLevel
0x18002954e  mov     r9d, 4; int
0x180029554  mov     [rsp+480h+lpMem], rax; lpMem
0x180029559  mov     r8, rsi; int
0x18002955c  call    WiaTrace_ProcessTrace_Ex
0x180029561  mov     eax, [rdi+8]
0x180029564  and     eax, 0FFFFFFFEh
0x180029567  mov     dword ptr [rdi+28h], 10001h
0x18002956e  or      eax, r15d
0x180029571  mov     dword ptr [rdi+20h], 1000002h
0x180029578  mov     [rdi+8], eax
0x18002957b  mov     dword ptr [rdi+24h], 10h
0x180029582  mov     rdx, [rdi+0DF0h]
0x180029589  lea     r8, DEVPKEY_Device_InstanceId
0x180029590  lea     rcx, [rsp+480h+var_430]
0x180029595  call    ?GetStringFromInterfacePathProperty@@YA?AV?$CSimpleStringBase@G@@PEBGPEBU_DEVPROPKEY@@@Z; GetStringFromInterfacePathProperty(ushort const *,_DEVPROPKEY const *)
0x18002959a  mov     rdx, rax
0x18002959d  lea     rcx, [rdi+30h]
0x1800295a1  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x1800295a6  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x1800295ad  lea     rcx, [rsp+480h+var_430]
0x1800295b2  mov     [rsp+480h+var_430], rax
0x1800295b7  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800295bc  lea     rcx, [rdi+30h]
0x1800295c0  call    ?Length@?$CSimpleStringBase@G@@QEBA_KXZ; CSimpleStringBase<ushort>::Length(void)
0x1800295c5  test    rax, rax
0x1800295c8  jz      short loc_180029637
0x1800295ca  mov     r9, [rdi+138h]
0x1800295d1  lea     r8, aDevpkeyDeviceI; "DEVPKEY_Device_InstanceId = %ws"
0x1800295d8  xor     edx, edx
0x1800295da  mov     ecx, r15d
0x1800295dd  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800295e2  mov     rdx, rax; char *
0x1800295e5  mov     rcx, rsi; char *
0x1800295e8  mov     rbx, rax
0x1800295eb  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800295f0  mov     rcx, rbx; this
0x1800295f3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800295f8  mov     r9, [rdi+138h]
0x1800295ff  lea     r8, aDevpkeyDeviceI; "DEVPKEY_Device_InstanceId = %ws"
0x180029606  xor     edx, edx
0x180029608  mov     ecx, r15d
0x18002960b  call    WiaTrace_TraceWithSubCompTraceLevel
0x180029610  mov     r9d, 4; int
0x180029616  mov     [rsp+480h+lpMem], rax; lpMem
0x18002961b  mov     r8, rsi; int
0x18002961e  call    WiaTrace_ProcessTrace_Ex
0x180029623  lea     rcx, [rdi+5F8h]
0x18002962a  lea     rdx, [rdi+30h]
0x18002962e  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x180029633  or      dword ptr [rdi+4], 4
0x180029637  mov     rdx, [rdi+138h]
0x18002963e  lea     r8, DEVPKEY_Aep_FriendlyName
0x180029645  lea     rcx, [rsp+480h+var_430]
0x18002964a  lea     rbx, [rdi+848h]
0x180029651  call    ?GetStringFromInstancePathProperty@@YA?AV?$CSimpleStringBase@G@@PEBGPEBU_DEVPROPKEY@@@Z; GetStringFromInstancePathProperty(ushort const *,_DEVPROPKEY const *)
0x180029656  mov     rdx, rax
0x180029659  mov     rcx, rbx
0x18002965c  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x180029661  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180029668  lea     rcx, [rsp+480h+var_430]
0x18002966d  mov     [rsp+480h+var_430], rax
0x180029672  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180029677  mov     rcx, rbx
0x18002967a  call    ?Length@?$CSimpleStringBase@G@@QEBA_KXZ; CSimpleStringBase<ushort>::Length(void)
0x18002967f  test    rax, rax
0x180029682  jz      short loc_1800296DD
0x180029684  mov     r9, [rdi+950h]
0x18002968b  lea     r8, aDevpkeyAepFrie; "DEVPKEY_Aep_FriendlyName = %ws"
0x180029692  xor     edx, edx
0x180029694  mov     ecx, r15d
0x180029697  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18002969c  mov     rdx, rax; char *
0x18002969f  mov     rcx, rsi; char *
0x1800296a2  mov     rbx, rax
0x1800296a5  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800296aa  mov     rcx, rbx; this
0x1800296ad  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800296b2  mov     r9, [rdi+950h]
0x1800296b9  lea     r8, aDevpkeyAepFrie; "DEVPKEY_Aep_FriendlyName = %ws"
0x1800296c0  xor     edx, edx
0x1800296c2  mov     ecx, r15d
0x1800296c5  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800296ca  mov     r9d, 4; int
0x1800296d0  mov     [rsp+480h+lpMem], rax; lpMem
0x1800296d5  mov     r8, rsi; int
0x1800296d8  call    WiaTrace_ProcessTrace_Ex
0x1800296dd  mov     rdx, [rdi+138h]
0x1800296e4  lea     r8, DEVPKEY_Device_Manufacturer
0x1800296eb  lea     rcx, [rsp+480h+var_430]
0x1800296f0  lea     rbx, [rdi+3A8h]
0x1800296f7  call    ?GetStringFromInstancePathProperty@@YA?AV?$CSimpleStringBase@G@@PEBGPEBU_DEVPROPKEY@@@Z; GetStringFromInstancePathProperty(ushort const *,_DEVPROPKEY const *)
0x1800296fc  mov     rdx, rax
0x1800296ff  mov     rcx, rbx
0x180029702  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x180029707  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18002970e  lea     rcx, [rsp+480h+var_430]
0x180029713  mov     [rsp+480h+var_430], rax
0x180029718  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18002971d  mov     rcx, rbx
0x180029720  call    ?Length@?$CSimpleStringBase@G@@QEBA_KXZ; CSimpleStringBase<ushort>::Length(void)
0x180029725  test    rax, rax
0x180029728  jz      short loc_180029783
0x18002972a  mov     r9, [rdi+4B0h]
0x180029731  lea     r8, aDevpkeyDeviceM; "DEVPKEY_Device_Manufacturer = %ws"
0x180029738  xor     edx, edx
0x18002973a  mov     ecx, r15d
0x18002973d  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180029742  mov     rdx, rax; char *
0x180029745  mov     rcx, rsi; char *
0x180029748  mov     rbx, rax
0x18002974b  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180029750  mov     rcx, rbx; this
0x180029753  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180029758  mov     r9, [rdi+4B0h]
0x18002975f  lea     r8, aDevpkeyDeviceM; "DEVPKEY_Device_Manufacturer = %ws"
0x180029766  xor     edx, edx
0x180029768  mov     ecx, r15d
0x18002976b  call    WiaTrace_TraceWithSubCompTraceLevel
0x180029770  mov     r9d, 4; int
0x180029776  mov     [rsp+480h+lpMem], rax; lpMem
0x18002977b  mov     r8, rsi; int
0x18002977e  call    WiaTrace_ProcessTrace_Ex
0x180029783  mov     rdx, [rdi+138h]
0x18002978a  lea     r8, DEVPKEY_Device_DeviceDesc
0x180029791  lea     rcx, [rsp+480h+var_430]
0x180029796  lea     rbx, [rdi+4D0h]
0x18002979d  call    ?GetStringFromInstancePathProperty@@YA?AV?$CSimpleStringBase@G@@PEBGPEBU_DEVPROPKEY@@@Z; GetStringFromInstancePathProperty(ushort const *,_DEVPROPKEY const *)
0x1800297a2  mov     rdx, rax
0x1800297a5  mov     rcx, rbx
0x1800297a8  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x1800297ad  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x1800297b4  lea     rcx, [rsp+480h+var_430]
0x1800297b9  mov     [rsp+480h+var_430], rax
0x1800297be  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800297c3  mov     rcx, rbx
0x1800297c6  call    ?Length@?$CSimpleStringBase@G@@QEBA_KXZ; CSimpleStringBase<ushort>::Length(void)
0x1800297cb  test    rax, rax
0x1800297ce  jz      short loc_180029829
0x1800297d0  mov     r9, [rdi+5D8h]
0x1800297d7  lea     r8, aDevpkeyDeviceD; "DEVPKEY_Device_DeviceDesc = %ws"
0x1800297de  xor     edx, edx
0x1800297e0  mov     ecx, r15d
0x1800297e3  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800297e8  mov     rdx, rax; char *
0x1800297eb  mov     rcx, rsi; char *
0x1800297ee  mov     rbx, rax
0x1800297f1  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
  ... truncated ...
```
