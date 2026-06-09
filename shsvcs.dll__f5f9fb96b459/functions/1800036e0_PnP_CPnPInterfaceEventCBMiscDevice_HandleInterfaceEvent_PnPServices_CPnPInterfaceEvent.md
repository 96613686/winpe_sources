# PnP::CPnPInterfaceEventCBMiscDevice::HandleInterfaceEvent(PnPServices::CPnPInterfaceEvent *)

- ea: `0x1800036e0`
- end: `0x18000427c`
- name: `?HandleInterfaceEvent@CPnPInterfaceEventCBMiscDevice@PnP@@UEAAJPEAVCPnPInterfaceEvent@PnPServices@@@Z`
- size: `2972`
- prototype: `__int64 __fastcall(PnP::CPnPInterfaceEventCBMiscDevice *__hidden this, struct PnPServices::CPnPInterfaceEvent *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800014b0`
- `0x1800033f0`
- `0x1800036e0`
- `0x180004290`
- `0x180004400`
- `0x1800046c0`
- `0x180004790`
- `0x180004de0`
- `0x1800140f0`
- `0x18001b404`
- `0x18002ebd4`
- `0x180032c46`
- `0x180032c90`
- `0x180034010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003f4e`
- `msvcrt!_wcsicmp` at `0x180003f4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000407d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000410a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000407d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000410a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000408b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004118`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000408b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004118`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003a49`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003feb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003a49`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003feb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000373e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000373e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003aa8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003efc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003aa8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003efc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003789`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003789`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003cc6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003cc6`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180003e82`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180003e82`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180003d25`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180003d25`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x180004077`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x180004077`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x180003f9d`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x180003f9d`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180003faa`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180003faa`
- `DEVOBJ!DevObjDeleteDeviceInterfaceData` at `0x18000409a`
- `DEVOBJ!DevObjDeleteDeviceInterfaceData` at `0x18000409a`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180004028`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180004028`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180003f70`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180003f70`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x180003d92`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x180003d92`

## pseudocode

```c
__int64 __fastcall PnP::CPnPInterfaceEventCBMiscDevice::HandleInterfaceEvent(
        PnP::CPnPInterfaceEventCBMiscDevice *this,
        struct PnPServices::CPnPInterfaceEvent *a2)
{
  CRefCounted *v2; // rbx
  const WCHAR *v3; // r13
  __int64 v4; // rdx
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  __int64 ValidHead; // rsi
  __int64 v7; // rbx
  __int64 v8; // r14
  __int64 v9; // rdi
  int v10; // r12d
  COMXProc *v11; // rcx
  _WORD *v12; // rdx
  __int64 v13; // rax
  __int64 v14; // r10
  _WORD *v15; // rcx
  int v16; // esi
  __int64 v17; // r8
  __int64 v18; // rdx
  const WCHAR *v19; // r13
  __int64 v20; // r9
  GUID *v21; // rcx
  GUID *v22; // rax
  GUID v23; // xmm0
  char *v24; // rax
  char *v25; // r14
  int v26; // eax
  __int64 v28; // rax
  unsigned __int64 v29; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v31; // rax
  CRefCounted *v32; // rbx
  _QWORD *v33; // rdi
  __int64 v34; // r8
  struct _RTL_CRITICAL_SECTION *v35; // rcx
  CRefCounted *v36; // r14
  struct PnPServices::CPnPInterfaceEvent *v37; // r8
  volatile signed __int32 *v38; // r14
  volatile signed __int32 *v39; // rax
  volatile signed __int32 *v40; // rbx
  COMXProc *v41; // r12
  const WCHAR *v42; // r9
  volatile signed __int32 *v43; // rsi
  _DWORD *v44; // rax
  _DWORD *v45; // rbx
  CRefCounted *v46; // rax
  struct PnP::CMiscDeviceInterface *v47; // rax
  unsigned int v48; // r14d
  int MultiDeviceGroupPropertyData; // eax
  BOOL v50; // r12d
  __int64 v51; // r8
  const WCHAR *v52; // r12
  int v53; // eax
  unsigned int v54; // eax
  __int64 v55; // r13
  __int64 v56; // r15
  __int64 v57; // r14
  __int64 v58; // rdx
  struct _RTL_CRITICAL_SECTION *v59; // rcx
  _QWORD *v60; // rax
  int v61; // r14d
  __int128 v62; // xmm6
  __int64 DeviceInfoList; // rax
  __int64 v64; // rbx
  HANDLE v65; // rax
  _DWORD *v66; // rax
  void *v67; // rsi
  HANDLE v68; // rax
  struct PnP::CMiscDeviceInterface *v69; // rax
  _QWORD *v70; // rax
  _QWORD *v71; // rcx
  void *v72; // rbx
  HANDLE v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  unsigned __int8 *pulLength; // [rsp+20h] [rbp-E0h]
  unsigned int ulFlags; // [rsp+28h] [rbp-D8h]
  ULONG v78[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v79; // [rsp+48h] [rbp-B8h] BYREF
  CRefCounted *v80; // [rsp+50h] [rbp-B0h]
  struct PnP::CMiscDeviceInterface *v81; // [rsp+58h] [rbp-A8h]
  int v82; // [rsp+60h] [rbp-A0h] BYREF
  COMXProc *v83; // [rsp+68h] [rbp-98h]
  GUID rguid; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID v85[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v86; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v87; // [rsp+B0h] [rbp-50h]
  __int128 v88; // [rsp+C0h] [rbp-40h]
  OLECHAR sz[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v90; // [rsp+E0h] [rbp-20h]
  __int128 v91; // [rsp+F0h] [rbp-10h]
  _BYTE v92[30]; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v93[132]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v94[528]; // [rsp+330h] [rbp+230h] BYREF

  v2 = PnP::g_pnelMiscDeviceInterface;
  v3 = (const WCHAR *)((char *)a2 + 20);
  v81 = a2;
  v83 = (struct PnPServices::CPnPInterfaceEvent *)((char *)a2 + 20);
  v80 = PnP::g_pnelMiscDeviceInterface;
  v4 = *((_QWORD *)PnP::g_pnelMiscDeviceInterface + 3);
  v5 = (struct _RTL_CRITICAL_SECTION *)(v4 + 8);
  if ( !v4 )
    v5 = 0;
  EnterCriticalSection(v5);
  ValidHead = CNamedElemList<COMXProc::CAdviseClient>::_GetValidHead((__int64)v2);
  v7 = ValidHead;
  v8 = 0;
  while ( ValidHead && !v8 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(ValidHead + 16) + 24LL));
    v9 = *(_QWORD *)(ValidHead + 16);
    v10 = lstrcmpiW(v3, *(LPCWSTR *)(v9 + 8));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 24), 0xFFFFFFFF) == 1 && v9 != -16 )
      (**(void (__fastcall ***)(__int64, __int64))(v9 + 16))(v9 + 16, 1);
    if ( v10 )
    {
      ValidHead = *(_QWORD *)(ValidHead + 32);
      if ( !ValidHead )
        goto LABEL_9;
      while ( !*(_QWORD *)(ValidHead + 16) )
      {
        ValidHead = *(_QWORD *)(ValidHead + 32);
        if ( !ValidHead )
          goto LABEL_9;
      }
    }
    else
    {
      v8 = ValidHead;
    }
    _InterlockedIncrement((volatile signed __int32 *)(ValidHead + 8));
LABEL_9:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 8), 0xFFFFFFFF) == 1 )
    {
      if ( v7 )
        (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
    }
    v7 = ValidHead;
  }
  if ( v8 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v8 + 16) + 24LL));
    v33 = *(_QWORD **)(v8 + 16);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v8 + 8), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
    v58 = *((_QWORD *)v80 + 3);
    v59 = (struct _RTL_CRITICAL_SECTION *)(v58 + 8);
    if ( !v58 )
      v59 = 0;
    LeaveCriticalSection(v59);
    v16 = 0;
    goto LABEL_64;
  }
  v60 = operator new(0x250u);
  v61 = 0;
  v33 = v60;
  if ( v60 )
  {
    v60[1] = 0;
    *((_DWORD *)v60 + 6) = 1;
    *v60 = &PnP::CMiscDeviceNode::`vftable'{for `CNamedElemHelper'};
    v60[2] = &PnP::CMiscDeviceInterface::`vftable'{for `CRefCounted'};
    v28 = -1;
    *((_DWORD *)v33 + 8) = 0;
    *((_DWORD *)v33 + 144) = 0;
    *(_QWORD *)((char *)v33 + 580) = 1;
    *(GUID *)((char *)v33 + 556) = guidInvalid;
    do
      ++v28;
    while ( v3[v28] );
    v29 = (unsigned int)(v28 + 1);
    ProcessHeap = GetProcessHeap();
    v31 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 2 * v29);
    v33[1] = v31;
    if ( !v31 )
    {
      v16 = -2147024882;
      goto LABEL_54;
    }
    v16 = StringCchCopyW(v31, v29, v3);
    if ( v16 >= 0 )
    {
      v79 = 0;
      v62 = 0;
      if ( _wcsicmp(&String1, v3) )
      {
        v16 = -2147467259;
        DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
        v64 = DeviceInfoList;
        if ( DeviceInfoList == -1 )
          goto LABEL_123;
        memset(v85, 0, sizeof(v85));
        v85[0].Data1 = 32;
        if ( (unsigned int)DevObjOpenDeviceInterface(DeviceInfoList, v3, 0, v85) )
        {
          v86 = 0;
          v87 = 0;
          v88 = 0;
          v65 = GetProcessHeap();
          v66 = HeapAlloc(v65, 8u, 0x210u);
          v67 = v66;
          if ( v66 )
          {
            *v66 = 8;
            LODWORD(v86) = 48;
            if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v64, v85, v66, 528, 0, &v86) )
            {
              v61 = DWORD1(v87);
              v62 = *(_OWORD *)&v85[0].Data2;
            }
            v78[0] = 7;
            v82 = 0;
            ((void (__fastcall *)(__int64, __int128 *, const DEVPROPKEY *, ULONG *, unsigned int *, int, int *, _DWORD))DevObjGetDeviceProperty)(
              v64,
              &v86,
              &DEVPKEY_Device_SessionId,
              v78,
              &v79,
              4,
              &v82,
              0);
            v68 = GetProcessHeap();
            HeapFree(v68, 0, v67);
            v16 = 0;
          }
          else
          {
            v16 = -2147024882;
          }
          DevObjDeleteDeviceInterfaceData(v64, v85);
        }
        DevObjDestroyDeviceInfoList(v64);
        if ( v16 < 0 )
        {
LABEL_123:
          String1 = 0;
          goto LABEL_54;
        }
        if ( (int)StringCchCopyW(&String1, 0x104u, v3) < 0 )
        {
          String1 = 0;
        }
        else
        {
          dword_18003FCB4 = v61;
          xmmword_18003FCB8 = v62;
        }
      }
      else
      {
        v61 = dword_18003FCB4;
      }
      *((_DWORD *)v33 + 144) = v79;
      v69 = v81;
      *((_DWORD *)v33 + 8) = v61;
      *(_OWORD *)((char *)v33 + 556) = *(_OWORD *)((char *)v69 + 556);
      v70 = operator new(0x30u);
      v32 = v80;
      v71 = v70;
      if ( v70 )
      {
        *((_DWORD *)v70 + 2) = 1;
        *v70 = &CElemSlot<Storage::CDisk>::`vftable';
        v70[2] = 0;
        v70[3] = 0;
        v70[4] = 0;
        v70[5] = 0;
        v74 = *((_QWORD *)v32 + 2);
        v71[2] = v33;
        _InterlockedIncrement((volatile signed __int32 *)v33 + 6);
        v71[3] = 0;
        v16 = 0;
        v71[4] = v74;
        v75 = *((_QWORD *)v32 + 2);
        if ( v75 )
        {
          *(_QWORD *)(v75 + 40) = 0;
          *(_QWORD *)(*((_QWORD *)v32 + 2) + 24LL) = v71;
        }
        *((_QWORD *)v32 + 2) = v71;
        v71[5] = v32;
      }
      else
      {
        v16 = -2147024882;
      }
    }
    else
    {
      v72 = (void *)v33[1];
      v73 = GetProcessHeap();
      HeapFree(v73, 0, v72);
LABEL_54:
      v32 = v80;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v33 + 6, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(_QWORD *, __int64))v33[2])(v33 + 2, 1);
    if ( v16 >= 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v33 + 6);
      ++*((_DWORD *)v32 + 8);
      goto LABEL_61;
    }
  }
  else
  {
    v32 = v80;
    v16 = -2147024882;
  }
  v33 = 0;
LABEL_61:
  v34 = *((_QWORD *)v32 + 3);
  v35 = (struct _RTL_CRITICAL_SECTION *)(v34 + 8);
  if ( !v34 )
    v35 = 0;
  LeaveCriticalSection(v35);
  if ( v16 < 0 )
    return (unsigned int)v16;
LABEL_64:
  v36 = (CRefCounted *)(v33 + 4);
  v80 = (CRefCounted *)(v33 + 4);
  v19 = L"DeviceRemoval";
  if ( !memcmp_0(&guidInvalid, (char *)v33 + 556, 0x10u) )
    goto LABEL_69;
  v85[0] = *(struct _GUID *)((char *)v33 + 556);
  if ( v33 )
    v38 = (volatile signed __int32 *)(v33 + 2);
  else
    v38 = 0;
  v39 = (volatile signed __int32 *)operator new(0x20u);
  v40 = v39;
  if ( v39 )
  {
    *((_DWORD *)v39 + 2) = 1;
    *(_QWORD *)v39 = &PnPHelper::CPnPDeviceProperties::`vftable';
    v46 = v80;
    *((_QWORD *)v40 + 3) = 0;
    *((_QWORD *)v40 + 2) = v46;
    _InterlockedIncrement(v38 + 2);
    v47 = v81;
    *((_QWORD *)v40 + 3) = v38;
    v48 = 10;
    rguid = *(GUID *)((char *)v47 + 540);
    MultiDeviceGroupPropertyData = (*(__int64 (__fastcall **)(volatile signed __int32 *, const wchar_t *, unsigned int *, __int64))(*(_QWORD *)v40 + 24LL))(
                                     v40,
                                     L"DeviceHandlers",
                                     v93,
                                     260);
    if ( MultiDeviceGroupPropertyData == -2147467259 )
    {
      LODWORD(pulLength) = 520;
      MultiDeviceGroupPropertyData = Settings::_GetMultiDeviceGroupPropertyData(
                                       (Settings *)v40,
                                       (struct Autoplay::IDeviceProperties *)L"DeviceHandlers",
                                       (const unsigned __int16 *)1,
                                       (unsigned int)v93,
                                       pulLength,
                                       ulFlags);
      if ( MultiDeviceGroupPropertyData == -2147467259 )
      {
        MultiDeviceGroupPropertyData = (*(__int64 (__fastcall **)(volatile signed __int32 *, const WCHAR *, _BYTE *, __int64))(*(_QWORD *)v40 + 24LL))(
                                         v40,
                                         L"DeviceGroup",
                                         v94,
                                         260);
        if ( MultiDeviceGroupPropertyData >= 0 )
        {
          LODWORD(pulLength) = 520;
          MultiDeviceGroupPropertyData = Settings::_GetDeviceGroupPropertyHelper(
                                           (Settings *)v94,
                                           L"DeviceHandlers",
                                           (const unsigned __int16 *)1,
                                           (unsigned int)v93,
                                           pulLength);
        }
        if ( MultiDeviceGroupPropertyData == -2147467259 )
        {
          LODWORD(pulLength) = 520;
          MultiDeviceGroupPropertyData = Settings::_GetDeviceClassPropertyData(
                                           (Settings *)v40,
                                           (struct Autoplay::IDeviceProperties *)L"DeviceHandlers",
                                           (const unsigned __int16 *)1,
                                           (unsigned __int8 *)v93,
                                           pulLength);
        }
      }
    }
    if ( MultiDeviceGroupPropertyData >= 0 )
    {
      v50 = 1;
    }
    else
    {
      if ( MultiDeviceGroupPropertyData == -2147467259 || MultiDeviceGroupPropertyData == -2147024894 )
        MultiDeviceGroupPropertyData = 0;
      v50 = 0;
      if ( MultiDeviceGroupPropertyData < 0 )
      {
LABEL_90:
        v52 = L"DeviceArrival";
        v53 = *((_DWORD *)v33 + 145);
        if ( *((_DWORD *)v81 + 4) != 0x8000 )
          v52 = L"DeviceRemoval";
        if ( v53 == 1 )
        {
          v78[0] = 4;
          if ( !CM_Get_DevNode_Registry_Property_ExW(*(_DWORD *)v80, 0x10u, 0, v33 + 73, v78, 0, 0) )
          {
            *((_DWORD *)v33 + 145) = 2;
            goto LABEL_143;
          }
          *((_DWORD *)v33 + 145) = 3;
        }
        else if ( v53 == 2 )
        {
LABEL_143:
          if ( (v33[73] & 4) != 0 )
            v48 = v48 & 0xFFFFFFF3 | 4;
        }
        v42 = v52;
        LODWORD(pulLength) = *((_DWORD *)v33 + 144);
        v41 = v83;
        COMXProc::AdviseDeviceArrivedOrRemoved(v83, v85, (struct _GUID *)v48, v42, (const unsigned __int16 *)pulLength);
        if ( _InterlockedExchangeAdd(v40 + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v40)(v40, 1);
        v36 = v80;
        goto LABEL_74;
      }
    }
    if ( v50 )
      goto LABEL_107;
    memset(v92, 0, sizeof(v92));
    *(_OWORD *)sz = 0;
    v90 = 0;
    v91 = 0;
    if ( StringFromGUID2(&rguid, sz, 39) >= 0 )
    {
      v87 = 0x77u;
      v79 = 0;
      *(_QWORD *)v78 = 0;
      v86 = DEVPKEY_DeviceContainer_AutoPlay_ContainerAutoplay;
      if ( (int)DevGetObjectProperties(2, sz, 0, 1, &v86, &v79, v78) >= 0 )
      {
        v54 = v79;
        v55 = 0;
        if ( v79 )
        {
          v56 = *(_QWORD *)v78;
          do
          {
            v57 = v56 + 48 * v55;
            if ( *(_DWORD *)(v57 + 16) == 119
              && !memcmp_0((const void *)(v56 + 48 * v55), &DEVPKEY_DeviceContainer_AutoPlay_ContainerAutoplay, 0x10u)
              && *(_DWORD *)(v57 + 32) == 17
              && *(_DWORD *)(v57 + 36) == 1 )
            {
              v50 = **(_BYTE **)(v57 + 40) == 0xFF;
            }
            v54 = v79;
            v55 = (unsigned int)(v55 + 1);
          }
          while ( (unsigned int)v55 < v79 );
          v48 = 10;
        }
        DevFreeObjectProperties(v54, *(_QWORD *)v78, v51);
        v19 = L"DeviceRemoval";
        if ( v50 )
LABEL_107:
          v48 = 9;
      }
    }
    goto LABEL_90;
  }
  v36 = v80;
LABEL_69:
  v41 = v83;
LABEL_74:
  if ( *((_DWORD *)v81 + 4) == 0x8000 )
  {
    v16 = PnP::_ProcessInterfaceArrival((PnP *)v33, (const WCHAR *)v81, v37);
  }
  else if ( *((_DWORD *)v81 + 4) == 32772 )
  {
    v43 = (volatile signed __int32 *)(v33 + 2);
    if ( !v33 )
      v43 = 0;
    v44 = operator new(0x20u);
    v45 = v44;
    if ( v44 )
    {
      v44[2] = 1;
      *(_QWORD *)v44 = &PnPHelper::CPnPDeviceProperties::`vftable';
      *((_QWORD *)v44 + 3) = 0;
      *((_QWORD *)v44 + 2) = v36;
      _InterlockedIncrement(v43 + 2);
      *((_QWORD *)v44 + 3) = v43;
      v24 = (char *)operator new(0x2B8u);
      v25 = v24;
      if ( v24 )
      {
        *((_DWORD *)v24 + 2) = 1;
        v12 = v24 + 32;
        *((_QWORD *)v24 + 85) = 0;
        v20 = 2147483646;
        *(_QWORD *)v24 = &Autoplay::CDispatchDeviceEvent::`vftable';
        v13 = 2147483646;
        v11 = v41;
        v14 = 260;
        do
        {
          if ( !v13 )
            break;
          if ( !*(_WORD *)v11 )
            break;
          *v12 = *(_WORD *)v11;
          v11 = (COMXProc *)((char *)v11 + 2);
          ++v12;
          --v13;
          --v14;
        }
        while ( v14 );
        v15 = v12 - 1;
        v16 = -2147024774;
        v17 = 2147942522LL;
        if ( v14 )
        {
          v15 = v12;
          v17 = 0;
        }
        *v15 = 0;
        if ( v14 )
        {
          v18 = 64;
          v17 = (__int64)(v25 + 552);
          do
          {
            if ( !v20 )
              break;
            if ( !*v19 )
              break;
            *(_WORD *)v17 = *v19++;
            v17 += 2;
            --v20;
            --v18;
          }
          while ( v18 );
          v15 = (_WORD *)(v17 - 2);
          if ( v18 )
          {
            v15 = (_WORD *)v17;
            v16 = 0;
          }
          *v15 = 0;
          if ( v18 )
          {
            v21 = (GUID *)((char *)v81 + 540);
            if ( v45 )
            {
              _InterlockedIncrement(v45 + 2);
              *((_QWORD *)v25 + 85) = v45;
            }
            v22 = &GUID_NULL;
            if ( v21 )
              v22 = v21;
            v23 = *v22;
            *((_DWORD *)v25 + 172) = 1;
            *((GUID *)v25 + 1) = v23;
            v16 = Autoplay::DispatchDeviceEvent((Autoplay *)v25, (struct Autoplay::CDispatchDeviceEvent *)v18);
          }
        }
        else
        {
          v16 = v17;
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v25 + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(char *, __int64, __int64, __int64))v25)(v25, 1, v17, v20);
      }
      else
      {
        v16 = -2147024882;
      }
      if ( _InterlockedExchangeAdd(v45 + 2, 0xFFFFFFFF) == 1 && v45 )
        (**(void (__fastcall ***)(_DWORD *, __int64, __int64, __int64))v45)(v45, 1, v17, v20);
    }
    else
    {
      v16 = -2147024882;
    }
    v26 = CNamedElemList<PnP::CMiscDeviceInterface>::Remove<unsigned short const *>((__int64)v15, (const WCHAR *)v41);
    if ( v26 < 0 )
      v16 = v26;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v33 + 6, 0xFFFFFFFF) == 1 && v33 != (_QWORD *)-16LL )
    (*(void (__fastcall **)(_QWORD *, __int64))v33[2])(v33 + 2, 1);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800036e0  mov     [rsp-8+arg_10], rbx
0x1800036e5  mov     [rsp-8+arg_18], rsi
0x1800036ea  push    rbp
0x1800036eb  push    r12
0x1800036ed  push    r13
0x1800036ef  push    r14
0x1800036f1  push    r15
0x1800036f3  lea     rbp, [rsp-460h]
0x1800036fb  sub     rsp, 560h
0x180003702  mov     rax, cs:__security_cookie
0x180003709  xor     rax, rsp
0x18000370c  mov     [rbp+480h+var_40], rax
0x180003713  mov     rbx, cs:?g_pnelMiscDeviceInterface@PnP@@3PEAV?$CNamedElemList@VCMiscDeviceInterface@PnP@@@@EA; CNamedElemList<PnP::CMiscDeviceInterface> * PnP::g_pnelMiscDeviceInterface
0x18000371a  lea     r13, [rdx+14h]
0x18000371e  xor     eax, eax
0x180003720  mov     [rsp+580h+var_528], rdx
0x180003725  mov     [rsp+580h+var_518], r13
0x18000372a  mov     [rsp+580h+var_530], rbx
0x18000372f  mov     rdx, [rbx+18h]
0x180003733  test    rdx, rdx
0x180003736  lea     rcx, [rdx+8]
0x18000373a  cmovz   rcx, rax; lpCriticalSection
0x18000373e  call    cs:__imp_EnterCriticalSection
0x180003744  mov     rcx, rbx
0x180003747  call    ?_GetValidHead@?$CNamedElemList@VCAdviseClient@COMXProc@@@@AEBAPEAV?$CElemSlot@VCAdviseClient@COMXProc@@@@XZ; CNamedElemList<COMXProc::CAdviseClient>::_GetValidHead(void)
0x18000374c  mov     rsi, rax
0x18000374f  mov     [rsp+580h+arg_0], rdi
0x180003757  mov     rbx, rax
0x18000375a  xor     r14d, r14d
0x18000375d  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180003764  test    rsi, rsi
0x180003767  jz      loc_180003EC1
0x18000376d  test    r14, r14
0x180003770  jnz     loc_180003EC1
0x180003776  mov     rax, [rsi+10h]
0x18000377a  lock inc dword ptr [rax+18h]
0x18000377e  mov     rdi, [rsi+10h]
0x180003782  mov     rcx, r13; lpString1
0x180003785  mov     rdx, [rdi+8]; lpString2
0x180003789  call    cs:__imp_lstrcmpiW
0x18000378f  lea     rcx, [rdi+10h]
0x180003793  mov     edx, r15d
0x180003796  mov     r12d, eax
0x180003799  lock xadd [rcx+8], edx
0x18000379e  cmp     edx, 1
0x1800037a1  jz      short loc_1800037DD
0x1800037a3  test    r12d, r12d
0x1800037a6  jz      short loc_1800037F4
0x1800037a8  mov     rsi, [rsi+20h]
0x1800037ac  test    rsi, rsi
0x1800037af  jnz     short loc_180003806
0x1800037b1  mov     eax, r15d
0x1800037b4  lock xadd [rbx+8], eax
0x1800037b9  cmp     eax, 1
0x1800037bc  jz      short loc_1800037C3
0x1800037be  mov     rbx, rsi
0x1800037c1  jmp     short loc_180003764
0x1800037c3  test    rbx, rbx
0x1800037c6  jz      short loc_1800037BE
0x1800037c8  mov     rax, [rbx]
0x1800037cb  mov     edx, 1
0x1800037d0  mov     rcx, rbx
0x1800037d3  mov     rax, [rax]
0x1800037d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037db  jmp     short loc_1800037BE
0x1800037dd  test    rcx, rcx
0x1800037e0  jz      short loc_1800037A3
0x1800037e2  mov     rdx, [rcx]
0x1800037e5  mov     rax, [rdx]
0x1800037e8  mov     edx, 1
0x1800037ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037f2  jmp     short loc_1800037A3
0x1800037f4  mov     r14, rsi
0x1800037f7  lock inc dword ptr [rsi+8]
0x1800037fb  jmp     short loc_1800037B1
0x1800037fd  mov     rsi, [rsi+20h]
0x180003801  test    rsi, rsi
0x180003804  jz      short loc_1800037B1
0x180003806  cmp     qword ptr [rsi+10h], 0
0x18000380b  jnz     short loc_1800037F7
0x18000380d  jmp     short loc_1800037FD
0x180003810  test    rax, rax
0x180003813  jz      short loc_180003834
0x180003815  movzx   r8d, word ptr [rcx]
0x180003819  test    r8w, r8w
0x18000381d  jz      short loc_180003834
0x18000381f  mov     [rdx], r8w
0x180003823  add     rcx, 2
0x180003827  add     rdx, 2
0x18000382b  dec     rax
0x18000382e  sub     r10, 1
0x180003832  jnz     short loc_180003810
0x180003834  xor     eax, eax
0x180003836  lea     rcx, [rdx-2]
0x18000383a  test    r10, r10
0x18000383d  mov     esi, 8007007Ah
0x180003842  mov     r8d, esi
0x180003845  cmovnz  rcx, rdx
0x180003849  cmovnz  r8d, eax
0x18000384d  mov     [rcx], ax
0x180003850  jz      loc_180004262
0x180003856  mov     edx, 40h ; '@'
0x18000385b  lea     r8, [r14+228h]
0x180003862  test    r9, r9
0x180003865  jz      short loc_180003886
0x180003867  movzx   eax, word ptr [r13+0]
0x18000386c  test    ax, ax
0x18000386f  jz      short loc_180003886
0x180003871  mov     [r8], ax
0x180003875  add     r13, 2
0x180003879  add     r8, 2
0x18000387d  dec     r9
0x180003880  sub     rdx, 1; struct Autoplay::CDispatchDeviceEvent *
0x180003884  jnz     short loc_180003862
0x180003886  xor     eax, eax
0x180003888  lea     rcx, [r8-2]
0x18000388c  test    rdx, rdx
0x18000388f  cmovnz  rcx, r8
0x180003893  cmovnz  esi, eax
0x180003896  mov     [rcx], ax
0x180003899  jz      short loc_1800038E2
0x18000389b  mov     rcx, [rsp+580h+var_528]
0x1800038a0  add     rcx, 21Ch
0x1800038a7  test    rbx, rbx
0x1800038aa  jz      short loc_1800038B7
0x1800038ac  lock inc dword ptr [rbx+8]
0x1800038b0  mov     [r14+2A8h], rbx
0x1800038b7  test    rcx, rcx
0x1800038ba  lea     rax, GUID_NULL
0x1800038c1  cmovnz  rax, rcx
0x1800038c5  mov     rcx, r14; this
0x1800038c8  movups  xmm0, xmmword ptr [rax]
0x1800038cb  mov     dword ptr [r14+2B0h], 1
0x1800038d6  movups  xmmword ptr [r14+10h], xmm0
0x1800038db  call    ?DispatchDeviceEvent@Autoplay@@YAJPEAVCDispatchDeviceEvent@1@@Z; Autoplay::DispatchDeviceEvent(Autoplay::CDispatchDeviceEvent *)
0x1800038e0  mov     esi, eax
0x1800038e2  mov     eax, r15d
0x1800038e5  lock xadd [r14+8], eax
0x1800038eb  cmp     eax, 1
0x1800038ee  jnz     short loc_180003945
0x1800038f0  mov     rax, [r14]
0x1800038f3  mov     edx, 1
0x1800038f8  mov     rcx, r14
0x1800038fb  mov     rax, [rax]
0x1800038fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003903  jmp     short loc_180003945
0x180003905  mov     dword ptr [rax+8], 1
0x18000390c  lea     rax, ??_7CPnPDeviceProperties@PnPHelper@@6B@; const PnPHelper::CPnPDeviceProperties::`vftable'
0x180003913  mov     [rbx], rax
0x180003916  mov     qword ptr [rbx+18h], 0
0x18000391e  mov     [rbx+10h], r14
0x180003922  lock inc dword ptr [rsi+8]
0x180003926  mov     ecx, 2B8h; Size
0x18000392b  mov     [rbx+18h], rsi
0x18000392f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003934  mov     r14, rax
0x180003937  test    rax, rax
0x18000393a  jnz     loc_18000422B
0x180003940  mov     esi, 8007000Eh
0x180003945  mov     eax, r15d
0x180003948  lock xadd [rbx+8], eax
0x18000394d  cmp     eax, 1
0x180003950  jz      short loc_1800039BC
0x180003952  mov     rdx, r12
0x180003955  call    ??$Remove@PEBG@?$CNamedElemList@VCMiscDeviceInterface@PnP@@@@QEAAJQEBG@Z; CNamedElemList<PnP::CMiscDeviceInterface>::Remove<ushort const *>(ushort const * const)
0x18000395a  test    eax, eax
0x18000395c  cmovs   esi, eax
0x18000395f  lea     rcx, [rdi+10h]
0x180003963  lock xadd [rcx+8], r15d
0x180003969  cmp     r15d, 1
0x18000396d  jz      short loc_1800039A5
0x18000396f  mov     rdi, [rsp+580h+arg_0]
0x180003977  mov     eax, esi
0x180003979  mov     rcx, [rbp+480h+var_40]
0x180003980  xor     rcx, rsp; StackCookie
0x180003983  call    __security_check_cookie
0x180003988  lea     r11, [rsp+580h+var_20]
0x180003990  mov     rbx, [r11+40h]
0x180003994  mov     rsi, [r11+48h]
0x180003998  mov     rsp, r11
0x18000399b  pop     r15
0x18000399d  pop     r14
0x18000399f  pop     r13
0x1800039a1  pop     r12
0x1800039a3  pop     rbp
0x1800039a4  retn
0x1800039a5  test    rcx, rcx
0x1800039a8  jz      short loc_18000396F
0x1800039aa  mov     rax, [rcx]
0x1800039ad  mov     edx, 1
0x1800039b2  mov     rax, [rax]
0x1800039b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ba  jmp     short loc_18000396F
0x1800039bc  test    rbx, rbx
0x1800039bf  jz      short loc_180003952
0x1800039c1  mov     rax, [rbx]
0x1800039c4  mov     edx, 1
0x1800039c9  mov     rcx, rbx
0x1800039cc  mov     rax, [rax]
0x1800039cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039d4  jmp     loc_180003952
0x1800039d9  mov     [rax+8], r14
0x1800039dd  mov     dword ptr [rax+18h], 1
0x1800039e4  lea     rax, ??_7CMiscDeviceNode@PnP@@6BCNamedElemHelper@@@; const PnP::CMiscDeviceNode::`vftable'{for `CNamedElemHelper'}
0x1800039eb  mov     [rdi], rax
0x1800039ee  lea     rax, ??_7CMiscDeviceInterface@PnP@@6BCRefCounted@@@; const PnP::CMiscDeviceInterface::`vftable'{for `CRefCounted'}
0x1800039f5  mov     [rdi+10h], rax
0x1800039f9  mov     rax, r15
0x1800039fc  mov     [rdi+20h], r14d
0x180003a00  movups  xmm0, xmmword ptr cs:?guidInvalid@@3U_GUID@@B.Data1; _GUID const guidInvalid ...
0x180003a07  mov     [rdi+240h], r14d
0x180003a0e  mov     qword ptr [rdi+244h], 1
0x180003a19  movups  xmmword ptr [rdi+22Ch], xmm0
0x180003a20  inc     rax
0x180003a23  cmp     [r13+rax*2+0], r14w
0x180003a29  jnz     short loc_180003A20
0x180003a2b  inc     eax
0x180003a2d  movaps  [rsp+580h+var_30], xmm6
0x180003a35  mov     esi, eax
0x180003a37  lea     rbx, [rax+rax]
0x180003a3b  call    cs:__imp_GetProcessHeap
0x180003a41  mov     r8, rbx; dwBytes
0x180003a44  xor     edx, edx; dwFlags
0x180003a46  mov     rcx, rax; hHeap
0x180003a49  call    cs:__imp_HeapAlloc
0x180003a4f  mov     [rdi+8], rax
0x180003a53  test    rax, rax
0x180003a56  jnz     loc_1800040EE
0x180003a5c  mov     esi, 8007000Eh
0x180003a61  mov     rbx, [rsp+580h+var_530]
0x180003a66  mov     eax, r15d
0x180003a69  lock xadd [rdi+18h], eax
0x180003a6e  movaps  xmm6, [rsp+580h+var_30]
0x180003a76  cmp     eax, 1
0x180003a79  jz      loc_180003BC2
0x180003a7f  test    esi, esi
0x180003a81  js      short loc_180003A96
0x180003a83  lock inc dword ptr [rdi+18h]
0x180003a87  inc     dword ptr [rbx+20h]
0x180003a8a  jmp     short loc_180003A99
0x180003a8c  mov     rbx, [rsp+580h+var_530]
0x180003a91  mov     esi, 8007000Eh
0x180003a96  mov     rdi, r14
0x180003a99  mov     r8, [rbx+18h]
0x180003a9d  test    r8, r8
0x180003aa0  lea     rcx, [r8+8]
0x180003aa4  cmovz   rcx, r14; lpCriticalSection
0x180003aa8  call    cs:__imp_LeaveCriticalSection
0x180003aae  test    esi, esi
0x180003ab0  js      loc_18000396F
0x180003ab6  lea     r14, [rdi+20h]
0x180003aba  mov     r8d, 10h; Size
0x180003ac0  lea     rdx, [r14+20Ch]; Buf2
0x180003ac7  mov     [rsp+580h+var_530], r14
0x180003acc  lea     rcx, ?guidInvalid@@3U_GUID@@B; Buf1
0x180003ad3  call    memcmp_0
0x180003ad8  lea     r13, aDeviceremoval; "DeviceRemoval"
0x180003adf  test    eax, eax
0x180003ae1  jz      short loc_180003B17
0x180003ae3  movups  xmm0, xmmword ptr [r14+20Ch]
0x180003aeb  movups  xmmword ptr [rbp+480h+var_500.Data1], xmm0
0x180003aef  test    rdi, rdi
0x180003af2  jz      loc_180003BBA
0x180003af8  lea     r14, [rdi+10h]
0x180003afc  mov     ecx, 20h ; ' '; Size
0x180003b01  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003b06  mov     rbx, rax
0x180003b09  test    rax, rax
0x180003b0c  jnz     loc_180003BDC
0x180003b12  mov     r14, [rsp+580h+var_530]
0x180003b17  mov     r12, [rsp+580h+var_518]
0x180003b1c  jmp     short loc_180003B5B
0x180003b1e  mov     dword ptr [rdi+244h], 3
0x180003b28  mov     eax, [rdi+240h]
0x180003b2e  lea     rdx, [rbp+480h+var_500]; struct _GUID *
0x180003b32  mov     r9, r12; lpString1
0x180003b35  mov     dword ptr [rsp+580h+pulLength], eax; unsigned __int16 *
0x180003b39  mov     r12, [rsp+580h+var_518]
0x180003b3e  mov     r8d, r14d; struct _GUID *
0x180003b41  mov     rcx, r12; this
0x180003b44  call    ?AdviseDeviceArrivedOrRemoved@COMXProc@@YAJPEBGPEAU_GUID@@K0K@Z; COMXProc::AdviseDeviceArrivedOrRemoved(ushort const *,_GUID *,ulong,ushort const *,ulong)
0x180003b49  mov     eax, r15d
0x180003b4c  lock xadd [rbx+8], eax
0x180003b51  cmp     eax, 1
0x180003b54  jz      short loc_180003BA5
0x180003b56  mov     r14, [rsp+580h+var_530]
0x180003b5b  mov     rcx, [rsp+580h+var_528]
0x180003b60  mov     edx, [rcx+10h]
0x180003b63  sub     edx, 8000h
0x180003b69  jz      loc_18000426A
0x180003b6f  cmp     edx, 4
0x180003b72  jnz     loc_18000395F
0x180003b78  xor     eax, eax
0x180003b7a  lea     rsi, [rdi+10h]
0x180003b7e  test    rdi, rdi
0x180003b81  mov     ecx, 20h ; ' '; Size
0x180003b86  cmovz   rsi, rax
0x180003b8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003b8f  mov     rbx, rax
0x180003b92  test    rax, rax
  ... truncated ...
```
